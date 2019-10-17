---
title: Microsoft Intune Exchange bağlayıcısını ayarlama
titleSuffix: Microsoft Intune
description: Intune kaydı ve Exchange ActiveSync (EAS) temelinde Exchange posta kutularına cihaz erişimini yönetmek için şirket içi Intune Exchange bağlayıcısını kullanın.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 09/28/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a0376ea1-eb13-4f13-84da-7fd92d8cd63c
ms.reviewer: demerson
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 30b5debc6e1ab113a08d8930f96f6cbc9bf12b48
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72509525"
---
# <a name="set-up-the-on-premises-intune-exchange-connector"></a>Şirket içi Intune Exchange bağlayıcısını ayarlama
Intune, Exchange 'e erişimi korumaya yardımcı olmak için Microsoft Intune Exchange Connector olarak bilinen şirket içi bir bileşeni kullanır. Bu bağlayıcıya Intune konsolunun bazı konumlarında *Exchange ActiveSync şirket içi Bağlayıcısı* da denir. 

Bu makaledeki bilgiler, Intune Exchange bağlayıcısını yüklemenize ve izlemenize yardımcı olabilir. Şirket içi Exchange posta kutularına erişime izin vermek veya erişimi engellemek için bağlayıcıyı [koşullu erişim ilkelerinizle](conditional-access-exchange-create.md) birlikte kullanabilirsiniz. 

Bağlayıcı, şirket içi donanımınızda yüklü ve çalışır. Exchange 'e bağlanan ve cihaz bilgilerini Intune hizmetine bağlayan cihazları bulur. Bağlayıcı cihazların kayıtlı ve uyumlu olmasına bağlı olarak cihazlara izin verir veya engeller. Bu iletişimler HTTPS protokolünü kullanır.

Bir cihaz şirket içi Exchange Server 'a erişmeyi denediğinde, Exchange Connector Exchange Server 'daki Exchange ActiveSync (EAS) kayıtlarını Intune 'a, cihazın Intune 'a kaydolduğu ve cihazınızın ilkelerine uyduğundan emin olmak için Intune kayıtlarına eşler. Koşullu erişim ilkelerinize bağlı olarak, cihaza izin verilebilir veya engellenebilir. Daha fazla bilgi için bkz. [Intune ile koşullu erişim kullanmanın yaygın yolları nelerdir?](conditional-access-intune-common-ways-use.md)

Hem *bulma* hem de *izin verme ve engelleme* işlemleri standart Exchange PowerShell cmdlet 'leri kullanılarak yapılır. Bu işlemler, Exchange Connector başlangıçta yüklendiğinde belirtilen hizmet hesabını kullanır. 

Intune, abonelik başına birden çok Intune Exchange Bağlayıcısı yüklemeyi destekler. Birden fazla şirket içi Exchange kuruluşunuz varsa, her biri için ayrı bir bağlayıcı oluşturabilirsiniz. Ancak, her bir Exchange kuruluşu için yalnızca bir bağlayıcı yüklenebilir.  

Intune 'un Şirket içi Exchange Server ile iletişim kurmasını sağlayan bir bağlantı ayarlamak için bu genel adımları izleyin:

1. Şirket içi bağlayıcıyı Intune portalından indirin.
2. Şirket içi Exchange kuruluşundaki bir bilgisayarda Exchange bağlayıcısını yükleyin ve yapılandırın.
3. Exchange bağlantısını doğrulayın.
4. Intune 'a bağlanmak istediğiniz her ek Exchange kuruluşu için bu adımları tekrarlayın.

## <a name="intune-exchange-connector-requirements"></a>Intune Exchange Connector gereksinimleri

Exchange 'e bağlanmak için, bağlayıcının kullanabileceği bir Intune lisansı olan bir hesabınız olması gerekir. Bağlayıcıyı yüklerken hesabı belirlersiniz.  

Aşağıdaki tabloda, Intune Exchange bağlayıcısını yüklediğiniz bilgisayar için gereksinimler listelenmektedir.  

|  Gereksinim  |   Daha fazla bilgi     |
|---------------|------------------------|
|  Operating systems        | Intune, Windows Server 2008 SP2 64-bit, Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2 veya Windows Server 2016 'ın herhangi bir sürümünü çalıştıran bir bilgisayarda Intune Exchange bağlayıcısını destekler.<br /><br />Bağlayıcı hiçbir sunucu çekirdeği yüklemesinde desteklenmez.  |
| Microsoft Exchange          | Şirket içi bağlayıcılar için Microsoft Exchange 2010 SP3 veya üzeri ya da eski Exchange Online Ayrılmış gerekir. Exchange Online Dedicated ortamınızın *yeni* yapılandırmada mı yoksa *eski* yapılandırmada mı olduğunu belirlemek için hesap yöneticinize başvurun. |
| Mobil cihaz yönetimi yetkilisi           | [Mobil cihaz yönetimi yetkilisi olarak Intune’u ayarlama](../fundamentals/mdm-authority-set.md). |
| Donanım              | Bağlayıcıyı yüklediğiniz bilgisayar 2 GB RAM ve 10 GB boş disk alanı ile birlikte 1,6 GHz CPU gerektirir. |
|  Active Directory eşitlemesi             | Intune 'U Exchange Server 'a bağlamak için bağlayıcıyı kullanmadan önce [Active Directory eşitlemeyi ayarlayın](../fundamentals/users-add.md). Yerel kullanıcılarınızın ve güvenlik gruplarınızın Azure Active Directory örneğinizle eşitlenmesi gerekir. |
| Ek yazılım         | Bağlayıcıyı barındıran bilgisayarda Microsoft .NET Framework 4,5 ve Windows PowerShell 2,0 ' nin tam yüklemesi yapılmalıdır. |
| Ağ               | Bağlayıcıyı yüklediğiniz bilgisayar, Exchange Server 'ı barındıran etki alanı ile güven ilişkisi olan bir etki alanında olmalıdır.<br /><br />Bilgisayarı, güvenlik duvarları ve proxy sunucuları 80 ve 443 bağlantı noktaları üzerinden Intune hizmetine erişmesine izin verecek şekilde yapılandırın. Intune şu etki alanlarını kullanır: <br> -manage.microsoft.com <br> @no__t -0\*manage.microsoft.com<br> @no__t -0\*.manage.microsoft.com <br><br> Intune Exchange Bağlayıcısı aşağıdaki hizmetlerle iletişim kurar: <br> -Intune hizmeti: HTTPS bağlantı noktası 443 <br> -Exchange Istemci erişimi sunucusu (CAS): WinRM hizmeti bağlantı noktası 443<br> -Exchange otomatik bulma 443<br> -Exchange Web Hizmetleri (EWS) 443  |

### <a name="exchange-cmdlet-requirements"></a>Exchange cmdlet gereksinimleri

Intune Exchange Connector için Active Directory Kullanıcı hesabı oluşturun. Hesabın aşağıdaki Windows PowerShell Exchange cmdlet 'lerini çalıştırma izni olmalıdır:  

- `Get-ActiveSyncOrganizationSettings`, `Set-ActiveSyncOrganizationSettings`
- `Get-CasMailbox`, `Set-CasMailbox`
- `Get-ActiveSyncMailboxPolicy`, `Set-ActiveSyncMailboxPolicy`, `New-ActiveSyncMailboxPolicy`, `Remove-ActiveSyncMailboxPolicy`
- `Get-ActiveSyncDeviceAccessRule`, `Set-ActiveSyncDeviceAccessRule`, `New-ActiveSyncDeviceAccessRule`, `Remove-ActiveSyncDeviceAccessRule`
- `Get-ActiveSyncDeviceStatistics`
- `Get-ActiveSyncDevice`
- `Get-ExchangeServer`
- `Get-ActiveSyncDeviceClass`
- `Get-Recipient`
- `Clear-ActiveSyncDevice`, `Remove-ActiveSyncDevice`
- `Set-ADServerSettings`
- `Get-Command`

## <a name="download-the-installation-package"></a>Yükleme paketini indirin

1. Intune Exchange bağlayıcısını destekleyebilen bir Windows Server 'da [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın. Şirket içi Exchange sunucusunda yönetici olan ve Exchange Server 'ı kullanma lisansı olan bir hesabı kullanın.

2. **Intune** > **Exchange erişimi**'ne gidin.  

3. **Kurulum**altında **Exchange ActiveSync şirket içi Bağlayıcısı** ' nı seçin ve ardından **Ekle**' yi seçin.

4. **Bağlayıcı Ekle** sayfasında şirket **içi bağlayıcıyı indir**' i seçin. Intune Exchange Bağlayıcısı, açılabilen veya kaydedilebilen sıkıştırılmış (. zip) bir klasörde yer alabilir. **Dosya indirme** iletişim kutusunda, sıkıştırılmış klasörü güvenli bir konumda depolamak için **Kaydet** ' i seçin.


## <a name="install-and-configure-the-intune-exchange-connector"></a>Intune Exchange bağlayıcısını yükleyip yapılandırma

Intune Exchange bağlayıcısını yüklemek için bu adımları izleyin. Birden çok Exchange kurumınız varsa, ayarlamak istediğiniz her Exchange Connector için adımları tekrarlayın.

1. Intune Exchange Connector için desteklenen bir işletim sisteminde, **Exchange_Connector_Setup. zip** içindeki dosyaları güvenli bir konuma ayıklayın.
   > [!IMPORTANT]
   > *Exchange_Connector_Setup* klasöründeki dosyaları yeniden adlandırmayın veya taşımayın. Bu değişiklikler bağlayıcı yüklemesinin başarısız olmasına neden olur.

2. Dosyalar ayıklandıktan sonra, ayıklanan klasörü açın ve bağlayıcıyı yüklemek için **Exchange_Connector_Setup. exe** dosyasına çift tıklayın.

   > [!IMPORTANT]
   > Hedef klasör güvenli bir konum değilse, şirket içi bağlayıcılarınızı yüklemeyi bitirdiğinizde, *Microsoftınayarla. ACCOUNTCERT* sertifika dosyasını silin.

3. **Microsoft Intune Exchange Connector** iletişim kutusunda, **Şirket içi Microsoft Exchange Server** veya **Barındırılan Microsoft Exchange Server** seçeneklerinden birini belirleyin.

   ![Exchange Server türünü nerede seçeceğinizi gösteren resim](./media/exchange-connector-install/intune-sa-exchange-connector-config.png)

   Şirket içi Exchange sunucusu için, **İstemci Erişimi Sunucu** rolünü barındıran Exchange sunucusunun sunucu adını veya tam etki alanı adını belirtin.

   Barındırılan bir Exchange sunucusu için, Exchange sunucusunun adresini belirtin. Barındırılan Exchange sunucusunun URL'sini bulmak için:

   1. Office 365 için Outlook 'U açın.

   2. Sol üst taraftaki **?** simgesine tıklayın ve ardından **hakkında**' yı seçin.

   3. **POP Dış Sunucu** değerini bulun.

   4. Barındırılan Exchange sunucunuzun proxy sunucusu ayarlarını belirtmek için **Proxy Sunucusu**'nu seçin.

       1. **Mobil cihaz bilgileri eşitlenirken proxy sunucusu kullan**'ı seçin.

       1. Sunucuya erişmek için kullanılan **proxy sunucusu adı** ve **bağlantı noktası numarasını** belirtin.

       1. Proxy sunucusuna erişmek için Kullanıcı kimlik bilgileri gerekliyse, **proxy sunucusuna bağlanmak için kimlik bilgilerini kullan**' ı seçin. Ardından **etki alanı\kullanıcı** ve **parola** girin.

       1. **Tamam**’ı seçin.

4. **Kullanıcı (etki alanı \ Kullanıcı)** ve **parola** alanlarında, Exchange sunucunuza bağlanmak için kimlik bilgilerini girin. Belirttiğiniz hesap, Intune 'U kullanmak için bir lisansa sahip olmalıdır. 

5. Kullanıcının Exchange Server posta kutusuna bildirim göndermek için kimlik bilgilerini sağlayın. Bu kullanıcı yalnızca bildirimlere ayrılabilir. Bildirimleri kullanıcının e-posta ile bildirim gönderebilmesi için bir Exchange posta kutusu olması gerekir. Bu bildirimleri Intune 'da koşullu erişim ilkeleri kullanarak yapılandırabilirsiniz.  

   Otomatik bulma hizmeti ve Exchange Web Hizmetleri 'nin Exchange CA 'larda yapılandırıldığından emin olun. Daha fazla bilgi için bkz. [İstemci Erişimi sunucusu](https://technet.microsoft.com/library/dd298114.aspx).

6. Intune 'un Exchange sunucusuna erişmesini sağlamak için **parola** alanına bu hesabın parolasını girin.

   > [!NOTE]
   > Kiracıda oturum açmak için kullandığınız hesabın en az bir Intune Hizmet Yöneticisi olması gerekir. Bu yönetici hesabı olmadan, "uzak sunucu bir hata döndürdü: (400) hatalı Istek" hatasıyla başarısız bir bağlantı alacaksınız.

7. **Bağlan**’ı seçin.

   > [!NOTE]
   > Bağlantının yapılandırılması birkaç dakika sürebilir.

Yapılandırma sırasında Exchange Connector, internet erişimini sağlamak için proxy ayarlarınızı depolar. Ara sunucu ayarlarınız değişiyorsa Exchange bağlayıcısını, güncelleştirilmiş proxy ayarlarını Exchange Connector 'a uygulamak için yeniden yapılandırın.

Exchange Connector bağlantıyı ayarladıktan sonra, Exchange tarafından yönetilen kullanıcılarla ilişkili mobil cihazlar otomatik olarak eşitlenir ve Exchange Connector 'a eklenir. Bu eşitlemenin tamamlanması biraz zaman alabilir.

> [!NOTE]
> Intune Exchange bağlayıcısını yüklerseniz ve daha sonra Exchange bağlantısını silmeniz gerekiyorsa, bağlayıcıyı yüklendiği bilgisayardan kaldırmanız gerekir.



## <a name="install-connectors-for-multiple-exchange-organizations"></a>Birden çok Exchange kuruluşu için bağlayıcıları yükleme

Intune, abonelik başına birden çok Intune Exchange bağlayıcılarını destekler. Birden çok Exchange kuruluşu olan bir kiracı için, her bir Exchange kuruluşu için yalnızca bir bağlayıcı ayarlayabilirsiniz. 

Birden çok Exchange kuruluşa bağlanmak üzere bağlayıcılar yüklemek için,. zip klasörünü bir kez indirin. Yüklediğiniz her bağlayıcı için aynı indirmeyi yeniden kullanın. Her ek bağlayıcı için, bir önceki bölümdeki adımları izleyerek Kurulum programını Exchange kuruluşundaki bir sunucuda ayıklayın ve çalıştırın.

Intune 'a bağlanan her bir Exchange kuruluşu, yüksek kullanılabilirlik, izleme ve el ile eşitlemeyi destekler. Aşağıdaki bölümlerde bu özellikler açıklanır.

## <a name="on-premises-intune-exchange-connector-high-availability-support"></a>Şirket içi Intune Exchange Connector yüksek kullanılabilirlik desteği  

Şirket içi bağlayıcı için, yüksek kullanılabilirlik, bağlayıcının kullandığı Exchange CA 'ları kullanılamaz hale gelirse, bağlayıcının söz konusu Exchange kuruluşu için farklı bir CA 'ya geçiş yapılabilir olduğu anlamına gelir. Exchange bağlayıcısının kendisi yüksek kullanılabilirliği desteklemez. Bağlayıcı başarısız olursa, otomatik yük devretme yoktur. Başarısız olan bağlayıcının yerini almak için [Yeni bir bağlayıcı yüklemelisiniz](#reinstall-the-intune-exchange-connector) . 

Yük devretmek için bağlayıcı, Exchange 'e başarılı bir bağlantı oluşturmak için belirtilen CAS 'yi kullanır. Daha sonra bu Exchange kuruluşu için ek CASs 'yi bulur. Bu bulma, birincil CA 'LAR kullanılabilir hale gelene kadar bağlayıcının başka bir CA 'ya yük devredebilmesine olanak sağlar. 

Varsayılan olarak, ek CASs 'leri bulma etkindir. Yük devretmeyi kapatmanız gerekirse:  
1. Exchange bağlayıcısının yüklü olduğu sunucuda **%*ProgramData*% \ Microsoft\windows Intune Exchange Connector**' a gidin. 
2. Bir metin düzenleyicisi kullanarak **OnPremisesExchangeConnectorServiceConfiguration.xml** dosyasını açın.
3. **@No__t-1iscasfailoverenabled >*true*\</ıscasfailoverenabled >** **\<ıscasfailoverenabled >*false*\</ıscasfailoverenabled >** olarak değiştirin.  
 
## <a name="performance-tune-the-exchange-connector-optional"></a>Performans-Exchange bağlayıcısını ayarlama (isteğe bağlı)

Exchange ActiveSync, 5.000 veya daha fazla cihazı desteklediğinde, bağlayıcının performansını artırmak için isteğe bağlı bir ayar yapılandırabilirsiniz. Exchange 'in bir PowerShell komutu çalışma alanının birden çok örneğini kullanmasını etkinleştirerek performansı geliştirebilirsiniz. 

Bu değişikliği yapmadan önce, Exchange bağlayıcısını çalıştırmak için kullandığınız hesabın diğer Exchange yönetim amaçları için kullanılmadığından emin olun. Bir Exchange hesabında sınırlı sayıda çalışma alanı vardır ve bağlayıcı bunlardan çoğunu kullanır. 

Performans ayarlama, daha eski veya daha yavaş donanımlar üzerinde çalışan bağlayıcılar için uygun değildir.  

Exchange Connector performansını geliştirmek için: 

1. Bağlayıcının yüklendiği sunucuda, bağlayıcının yükleme dizinini açın.  Varsayılan konum *C:\ProgramData\Microsoft\Windows Intune Exchange Connector*' dır. 
2. *OnPremisesExchangeConnectorServiceConfiguration. xml*dosyasını düzenleyin.
3. **Enableparallelcommandsupport** öğesini bulun ve değeri **true**olarak ayarlayın:  
     
   \<EnableParallelCommandSupport > true @ no__t-1/EnableParallelCommandSupport >
4. Dosyayı kaydedin ve ardından Microsoft Intune Exchange Connector hizmetini yeniden başlatın.

## <a name="reinstall-the-intune-exchange-connector"></a>Intune Exchange bağlayıcısını yeniden yükleme

Bir Intune Exchange bağlayıcısını yeniden yüklemeniz gerekebilir. Her bir Exchange kuruluşuna yalnızca tek bir bağlayıcı bağlanabildikleri için, kuruluş için ikinci bir bağlayıcı yüklerseniz, yüklediğiniz yeni bağlayıcı özgün bağlayıcının yerini alır.

1. Yeni bağlayıcıyı yüklemek için [Exchange Connector 'ı yüklemek ve yapılandırmak](#install-and-configure-the-intune-exchange-connector) bölümündeki adımları izleyin. 
2. İstendiğinde, yeni bağlayıcıyı yüklemek için **Değiştir** ' i seçin.  
   Bağlayıcıyı değiştirmek için ![Yapılandırma uyarısı @ no__t-1

3. [Intune Exchange bağlayıcısını yükleyip yapılandırma](#install-and-configure-the-intune-exchange-connector) bölümünden adımlara devam edin ve Intune 'da yeniden oturum açın.
4. Son pencerede, yüklemeyi tamamlaması için **Kapat** ' ı seçin.  
   ![Son kurulum @ no__t-1
 

## <a name="monitor-an-exchange-connector"></a>Exchange bağlayıcısını izleme

Exchange bağlayıcısını başarıyla yapılandırdıktan sonra, bağlantıların durumunu ve son başarılı eşitleme denemesini görebilirsiniz. 

Exchange Connector bağlantısını doğrulamak için:

1. Intune panosunda **Exchange erişimi**' ni seçin.
2. Her Exchange bağlayıcısının bağlantı durumunu doğrulamak için **Şirket Içi Exchange erişimi '** ni seçin.

Ayrıca son başarılı eşitleme denemesinin tarih ve saatini kontrol edebilirsiniz.

Intune 1710 sürümünden başlayarak [Exchange Connector ve Intune için System Center Operations Manager yönetim paketini](https://www.microsoft.com/download/details.aspx?id=55990&751be11f-ede8-5a0c-058c-2ee190a24fa6=True&e6b34bbe-475b-1abd-2c51-b5034bcdd6d2=True&fa43d42b-25b5-4a42-fe9b-1634f450f5ee=True)kullanabilirsiniz. Yönetim Paketi, sorun gidermeniz gerektiğinde Exchange bağlayıcısını izlemek için farklı yollar sunar.

## <a name="manually-force-a-quick-sync-or-full-sync"></a>Hızlı eşitlemeyi veya tam eşitlemeyi el ile zorlama

Bir Intune Exchange Bağlayıcısı, EAS ve Intune cihaz kayıtlarını düzenli olarak otomatik olarak eşitler. Bir cihazın uyumluluk durumu değişirse, otomatik eşitleme işlemi, cihaz erişiminin engellenmesi veya izin verilmesi için düzenli olarak kayıtları güncelleştirir.

- **Hızlı eşitleme** , günde birkaç kez düzenli aralıklarla gerçekleşir. Hızlı eşitleme, koşullu erişim için hedeflenen ve son eşitlemeden bu yana değiştirilen Intune lisanslı ve şirket içi Exchange kullanıcılarına yönelik cihaz bilgilerini alır.

- Her gün varsayılan olarak bir **tam eşitleme** gerçekleşir. Tam eşitleme, koşullu erişim için hedeflenen tüm Intune lisanslanmış ve şirket içi Exchange kullanıcılarına ait cihaz bilgilerini alır. Tam eşitleme, Exchange Server bilgilerini de alır ve Intune 'un Azure portal belirttiği yapılandırmanın Exchange Server 'da güncelleştirilmesini sağlar. 


Intune panosunda **hızlı eşitleme** veya **tam eşitleme** seçeneklerini kullanarak bir bağlayıcıyı eşitleme çalıştırmaya zorlayabilirsiniz:

   1. Intune panosunda **Exchange erişimi**' ni seçin.
   2. **Şirket Içi Exchange erişimi '** ni seçin.
   3. Eşitlemek istediğiniz bağlayıcıyı seçin ve sonra da **Hızlı Eşitleme**'yi veya **Tam Eşitleme**'yi seçin.

## <a name="next-steps"></a>Sonraki adımlar

Şirket [Içi Exchange sunucuları için koşullu erişim ilkesi](conditional-access-exchange-create.md)oluşturun.
