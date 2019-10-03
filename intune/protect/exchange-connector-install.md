---
title: Microsoft Intune Exchange Connector ayarlama
titleSuffix: Microsoft Intune
description: Intune kaydı ve Exchange Active Sync (EAS) temelinde Exchange posta kutularına cihaz erişimini yönetmek için şirket içi Intune Exchange bağlayıcısını kullanın.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 09/28/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a0376ea1-eb13-4f13-84da-7fd92d8cd63c
ms.reviewer: demerson
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 12c190cad923569e15fd32fe7e5f7f6bd2a45302
ms.sourcegitcommit: f04e21ec459998922ba9c7091ab5f8efafd8a01c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71814137"
---
# <a name="set-up-the-on-premises-intune-exchange-connector"></a>Şirket içi Intune Exchange bağlayıcısını ayarlama
Intune, Exchange 'e erişimi korumaya yardımcı olmak için Microsoft Intune Exchange Connector olarak bilinen şirket içi bir bileşeni kullanır. Buna Intune konsolunun bazı konumlarında *Exchange ActiveSync şirket içi Bağlayıcısı* da denir. Bu makaledeki bilgiler, [Şirket Içi Exchange posta kutularına izin vermek veya erişimi engellemek Için koşullu erişim ilkelerinizle](conditional-access-exchange-create.md)birlikte kullandığınız Intune Exchange bağlayıcısını yüklemenize ve izlemenize yardımcı olabilir. 

Bağlayıcı Şirket içi donanımlarınıza yüklenip çalışır ve Exchange 'e bağlanan cihazları bulmaktan, cihaz bilgilerini Intune hizmetine bağlamaya ve cihazların kayıtlı olup olmadığına bağlı olarak cihazlara izin vermeye veya engellemeye sorumludur ve uyumlu. Bu iletişimler HTTPS protokolü kullanılarak yapılır.

Bir cihaz şirket içi Exchange 'e erişmeye çalıştığında, Exchange Connector, Intune ile cihaz kaydını denetlemek ve cihaz uyumluluk ilkelerinizle uyumluluk sağlamak için Exchange Server 'daki Exchange Active Sync (EAS) kayıtlarını Intune kayıtlarına eşler. Koşullu erişim ilkelerinize bağlı olarak, cihaza erişim izni verilebilir veya engellenebilir. Daha fazla bilgi için bkz. [Intune Ile koşullu erişim kullanmanın yaygın yolları nelerdir?](conditional-access-intune-common-ways-use.md)

Hem *bulma* hem de *izin verme ve engelleme* işlemleri standart Exchange PowerShell cmdlet 'leri kullanılarak yapılır. Bu oOperations 'ler, Exchange Connector başlangıçta yüklendiğinde belirtilen hizmet hesabını kullanır. 

Intune, abonelik başına birden çok Intune Exchange Bağlayıcısı yüklemeyi destekler. Birden fazla şirket içi Exchange kuruluşunuz varsa, her biri için ayrı bir bağlayıcı oluşturabilirsiniz. Ancak, her bir Exchange kuruluşu ile kullanılmak üzere yalnızca bir bağlayıcı yüklenebilir.  

Intune 'un Şirket içi Exchange Server ile iletişim kurmasını sağlayan bir bağlantı kurmak için aşağıdaki genel adımlar verilmiştir:

1. Şirket içi bağlayıcıyı Intune portalından indirin.
2. Exchange bağlayıcısını şirket içi Exchange kuruluşundaki bir bilgisayara yükleyip yapılandırın.
3. Exchange bağlantısını doğrulayın.
4. Intune 'a bağlanmak istediğiniz her ek Exchange kuruluşu için bu adımları tekrarlayın.

## <a name="intune-exchange-connector-requirements"></a>Intune Exchange Connector gereksinimleri

Exchange 'e bağlanmak için bağlayıcı tarafından kullanılabilecek bir Intune lisansı olan bir hesap gerekir. Bu hesap, bağlayıcıyı yüklediğinizde belirtilir.  

Aşağıdaki tabloda, Intune Exchange bağlayıcısını yüklediğiniz bilgisayar için gereksinimler listelenmektedir.  

|  Gereksinim  |   Daha fazla bilgi     |
|---------------|------------------------|
|  İşletim sistemleri        | Intune, Windows Server 2008 SP2 64-bit, Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2 veya Windows Server 2016 'ın herhangi bir sürümünü çalıştıran bir bilgisayarda Intune Exchange bağlayıcısını destekler.<br /><br />Bağlayıcı hiçbir sunucu çekirdeği yüklemesinde desteklenmez.  |
| Microsoft Exchange          | Şirket içi bağlayıcılar, Microsoft Exchange 2010 SP3 veya üzeri ya da eski Exchange Online ayrılmış gerektirir. Exchange Online ayrılmış ortamınızın <strong>Yeni</strong> mi yoksa <strong>eski</strong> yapılandırmada mı olduğunu anlamak için hesap yöneticinize başvurun. |
| Mobil cihaz yönetimi yetkilisi           | [Mobil cihaz yönetimi yetkilisini Intune olarak ayarlayın](../fundamentals/mdm-authority-set.md). |
| Donanım              | Bağlayıcıyı yüklediğiniz bilgisayar 2 GB RAM ve 10 GB boş disk alanı ile 1,6 GHz CPU gerektirir. |
|  Active Directory eşitleme             | Intune 'U Exchange Server 'a bağlamak üzere bağlayıcısını kullanabilmeniz için, yerel kullanıcılarınızın ve güvenlik gruplarınızın Azure Active Directory örneğiniz ile eşitlenmesi için [Active Directory eşitlemesi ayarlamanız](../fundamentals/users-add.md) gerekir. |
| Ek yazılım         | Microsoft .NET Framework 4,5 ve Windows PowerShell 2,0 ' nin tam yüklemesi, bağlayıcıyı barındıran bilgisayarda yüklü olmalıdır. |
| Ağ               | Bağlayıcıyı yüklediğiniz bilgisayar, Exchange Server 'ı barındıran etki alanı ile güven ilişkisi olan bir etki alanında olmalıdır.<br /><br />Bilgisayar, BT 'nin 80 ve 443 bağlantı noktaları üzerinden güvenlik duvarları ve proxy sunucular aracılığıyla Intune hizmetine erişmesini sağlamak için yapılandırma gerektirir. Intune tarafından kullanılan etki alanları şunlardır: <br> **-** Manage.Microsoft.com <br> **-** &#42;Manage.Microsoft.com<br> **-** &#42;. Manage.Microsoft.com <br><br> Intune Exchange Bağlayıcısı aşağıdaki hizmetlerle iletişim kurar: <br> **-** Intune hizmeti: HTTPS bağlantı noktası 443 <br> **-** Exchange Istemci erişim sunucusu (CAS): WinRM hizmeti bağlantı noktası 443<br> **-** Exchange otomatik bulma 443<br> **-** Exchange WebServices (EWS) 443  |

### <a name="exchange-cmdlet-requirements"></a>Exchange cmdlet gereksinimleri

Intune Exchange Bağlayıcısı tarafından kullanılacak bir Active Directory Kullanıcı hesabı oluşturun. Hesabın aşağıdaki Windows PowerShell Exchange cmdlet 'lerini çalıştırma izni olmalıdır:  

- Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings
- Get-CasMailbox, Set-CasMailbox
- Get-ActiveSyncMailboxPolicy, Set-ActiveSyncMailboxPolicy, New-ActiveSyncMailboxPolicy, Remove-ActiveSyncMailboxPolicy
- Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule
- Get-ActiveSyncDeviceStatistics
- Get-ActiveSyncDevice
- Get-ExchangeServer
- Get-ActiveSyncDeviceClass
- Get-Recipient
- Clear-ActiveSyncDevice, Remove-ActiveSyncDevice
- Set-ADServerSettings
- Get-Command

## <a name="download-the-intune-exchange-connector-software-installation-package"></a>Intune Exchange Connector yazılım yükleme paketini indirme

1. Intune Exchange bağlayıcısını destekleyebilen bir Windows Server 'da, [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) 'da şirket içi Exchange sunucusunda yönetici olan ve Exchange Server 'ı kullanma lisansı bulunan bir kullanıcı hesabıyla oturum açın.

2. @No__t **Intune**'a git-1**Exchange erişimi**  

3. **Kurulum**altında **Exchange ActiveSync şirket içi Bağlayıcısı**' nı seçin ve ardından **Ekle**' yi seçin.

4. **Bağlayıcı Ekle** sayfasında şirket **içi bağlayıcıyı indir**' i seçin. Intune Exchange Bağlayıcısı, açılabilen veya kaydedilebilen sıkıştırılmış (. zip) bir klasörde yer alabilir. **Dosya indirme** iletişim kutusunda, sıkıştırılmış klasörü güvenli bir konuma depolamak için **Kaydet** ' i seçin.


## <a name="install-and-configure-the-intune-exchange-connector"></a>Intune Exchange bağlayıcısını yükleyip yapılandırma

Intune Exchange bağlayıcısını yüklemek için aşağıdaki adımları uygulayın. Birden çok Exchange kurumınız varsa, ayarlamak istediğiniz her ek Exchange Connector için bu adımları tekrarlayın.

1. Intune Exchange Connector için desteklenen bir işletim sisteminde, **Exchange_Connector_Setup. zip** içindeki dosyaları güvenli bir konuma ayıklayın.
   > [!IMPORTANT]
   > Exchange_Connector_Setup klasöründeki dosyaları yeniden adlandırmayın veya taşımayın. Klasörün içeriğini taşımak veya yeniden adlandırmak bağlayıcı yüklemesinin başarısız olmasına neden olur.

2. Dosyalar ayıklandıktan sonra, ayıklanan klasörü açın ve bağlayıcıyı yüklemek için **Exchange_Connector_Setup. exe** dosyasına çift tıklayın.

   > [!IMPORTANT]
   > Hedef klasör güvenli bir konum değilse, şirket içi bağlayıcılarınızı yüklemeyi tamamladığınızda, **Microsofınayarla. ACCOUNTCERT** sertifika dosyasını silmelisiniz.

3. **Microsoft Intune Exchange Connector** iletişim kutusunda, **Şirket Içi Microsoft Exchange Server** veya **barındırılan Microsoft Exchange Server**seçeneklerinden birini belirleyin.

   ![Exchange Server türünün nerede seçileceğini gösteren resim](./media/exchange-connector-install/intune-sa-exchange-connector-config.png)

   Şirket içi Exchange sunucusu için, **Istemci erişimi sunucu** rolünü barındıran Exchange sunucusunun sunucu adını veya tam etki alanı adını belirtin.

   Barındırılan bir Exchange sunucusu için Exchange Server adresini sağlayın. Barındırılan Exchange Server URL 'sini bulmak için:

   1. Office 365 için Web üzerinde Outlook 'U açın.

   2. Seçin **?** simgesine tıklayın ve ardından **hakkında**' yı seçin.

   3. **Pop dış sunucu** değerini bulun.

   4. Barındırılan Exchange sunucunuzun proxy sunucusu ayarlarını belirtmek için **proxy sunucusu** ' nu seçin.
       1. **Mobil cihaz bilgilerini eşitlerken proxy sunucusu kullan**' ı seçin.

       2. Sunucuya erişmek için kullanılacak **proxy sunucu adını** ve **bağlantı noktası numarasını** girin.

       3. Proxy sunucusuna erişmek için Kullanıcı kimlik bilgilerinin sağlanması gerekiyorsa, **proxy sunucusuna bağlanmak için kimlik bilgilerini kullan**' ı seçin. Ardından **etkialanı \ Kullanıcı** ve **parolayı**girin.

       4. **Tamam**’ı seçin.

4. **Kullanıcı (etki alanı \ Kullanıcı)** ve **parola** alanlarında, Exchange sunucunuza bağlanmak için gereken kimlik bilgilerini girin. Belirttiğiniz hesap, Intune 'U kullanmak için bir lisansa sahip olmalıdır. 

5. Kullanıcının Exchange Server posta kutusuna bildirim göndermek için gereken kimlik bilgilerini sağlayın. Bu Kullanıcı yalnızca bildirimlere ayrılmış olabilir. Bildirimleri kullanıcının e-posta ile bildirim gönderebilmesi için bir Exchange posta kutusu olması gerekir. Bu bildirimleri Intune 'da koşullu erişim ilkeleriyle yapılandırabilirsiniz.  

   Otomatik bulma hizmeti ve Exchange Web Hizmetleri 'nin Exchange Istemci erişimi sunucusu 'nda yapılandırıldığından emin olun. Daha fazla bilgi için bkz. [Istemci erişimi sunucusu](https://technet.microsoft.com/library/dd298114.aspx).

6. Intune 'un Exchange sunucusuna erişmesini sağlamak için **parola** alanına bu hesabın parolasını girin.

   > [!NOTE]
   > Bağlantının başarılı olması için, kiracıya oturum açmak için kullandığınız hesabın en az Intune Hizmet Yöneticisi olması gerekir. Bu olmadan şu hatayla başarısız bir bağlantı alacaksınız: "uzak sunucu bir hata döndürdü: (400) hatalı Istek".

7. **Bağlan**’ı seçin.

   > [!NOTE]
   > Bağlantının yapılandırılması birkaç dakika sürebilir.

Yapılandırma sırasında Exchange Connector, Internet erişimini sağlamak için proxy ayarlarınızı depolar. Ara sunucu ayarlarınız değişiyorsa Exchange bağlayıcısını, güncelleştirilmiş proxy ayarlarını Exchange Connector 'a uygulamak için yeniden yapılandırın.

Exchange Connector bağlantıyı ayarladıktan sonra, Exchange 'de yönetilen kullanıcılarla ilişkili mobil cihazlar otomatik olarak eşitlenir ve Exchange Connector 'a eklenir. Bu eşitlemenin tamamlanması biraz zaman alabilir.

> [!NOTE]
> Intune Exchange bağlayıcısını yüklediyseniz ve bir noktada Exchange bağlantısını silerseniz, bağlayıcıyı yüklendiği bilgisayardan kaldırmanız gerekir...



## <a name="install-connectors-for-multiple-exchange-organizations"></a>Birden çok Exchange kuruluşu için bağlayıcıları yükler

Intune, abonelik başına birden çok Intune Exchange bağlayıcılarını destekler. Birden çok Exchange kuruluşu olan bir kiracı için, her bir Exchange kuruluşu için bir bağlayıcı ayarlayabilir, ancak tek bir kuruluş için yalnızca tek bir bağlayıcı oluşturabilirsiniz. 

Birden çok Exchange kuruluşa bağlanmak için bağlayıcı yükleyeceksiniz,. zip klasörünü bir kez indirin ve ardından yüklediğiniz her bağlayıcı için aynı indirmeyi yeniden kullanın. Her ek bağlayıcı için, bir önceki bölümdeki adımları izleyerek Kurulum programını Exchange kuruluşundaki bir sunucuda ayıklayın ve çalıştırın.

Aşağıdaki bölümlerde açıklanan yüksek kullanılabilirlik, izleme ve el ile eşitleme özellikleri, Intune 'a bağlanan her bir Exchange kuruluşu için desteklenir.

## <a name="on-premises-intune-exchange-connector-high-availability-support"></a>Şirket içi Intune Exchange Connector yüksek kullanılabilirlik desteği 

Şirket içi bağlayıcı için yüksek kullanılabilirlik, bağlayıcının kullandığı Exchange Istemci erişimi sunucusu (CAS) kullanılamaz hale geldiği anlamına gelir, bağlayıcının bu Exchange kuruluşu için farklı CA 'LAR kullanması için üzerine geçiş yapılabilir. Exchange bağlayıcısının kendisi yüksek kullanılabilirliği desteklemez. Bağlayıcı başarısız olursa, otomatik yük devretme yoktur ve [Yeni bir bağlayıcı yükleyerek](#reinstall-the-intune-exchange-connector)Bu bağlayıcıyı değiştirmeniz gerekir. 

Bağlayıcı, belirtilen CA 'ları kullanarak Exchange 'e başarılı bir bağlantı oluşturduktan sonra, yük devretmeyi gerçekleştirmek için bu Exchange kuruluşu için ek CASs 'yi bulur. Ek CASs hakkında bilgi, bağlayıcının varsa, birincil CA 'LAR kullanılabilir hale gelene kadar başka bir CA 'ya yük devretmesine olanak sağlar. Varsayılan olarak, ek CASs 'leri bulma etkindir. Aşağıdaki yordamı kullanarak yük devretmeyi devre dışı bırakabilirsiniz:  
1. Exchange bağlayıcısının yüklü olduğu sunucuda%*ProgramData*% \ Microsoft\windows Intune Exchange Connector ' a gidin. 
2. Bir metin düzenleyicisi kullanarak **OnPremisesExchangeConnectorServiceConfiguration. xml**' yi açın.
3. Özelliği devre dışı bırakmak için &lt;IsCasFailoverEnabled @ no__t-1**true**&lt;/ıscasfailoverenabled @ no__t-4 ' ü &lt;iscasfailoverenabled @ no__t-6**false**&lt;/ıscasfailoverenabled @ no__t-9 ' a değiştirin.  
 
## <a name="optional-performance-tuning-for-the-exchange-connector"></a>Exchange Connector için isteğe bağlı performans ayarı  

Exchange ActiveSync ile 5.000 veya daha fazla cihazı destekettiğinizde, bağlayıcının performansını artırmak için isteğe bağlı bir ayar yapılandırabilirsiniz. Exchange 'in bir PowerShell komutu çalışma alanının birden çok örneğini kullanmasını etkinleştirerek daha yüksek performans elde edilir. 

Bu değişikliği yapmadan önce, Exchange bağlayıcısını çalıştırmak için kullandığınız hesabın diğer Exchange yönetim amaçları için kullanılmadığından emin olun. Bunun nedeni, Exchange 'in hesap başına sınırlı sayıda çalışma alanına sahip olması ve çoğu bağlayıcı tarafından kullanılır. 

Bu performans değişikliği, daha eski veya daha yavaş donanımlar üzerinde çalışan bağlayıcılar için uygun değildir.  

1. Bağlayıcının yüklendiği sunucuda, bağlayıcılar yükleme dizinini açın.  Varsayılan konum *C:\ProgramData\Microsoft\Windows Intune Exchange Connector*' dır. 
2. *OnPremisesExchangeConnectorServiceConfiguration. xml*dosyasını düzenleyin.
3. **Enableparallelcommandsupport** öğesini bulun ve değeri **true**olarak ayarlayın:  
     
   \<EnableParallelCommandSupport > true @ no__t-1/EnableParallelCommandSupport >
4. Dosyayı kaydedin ve ardından Microsoft Intune Exchange Connector hizmetini yeniden başlatın.

## <a name="reinstall-the-intune-exchange-connector"></a>Intune Exchange bağlayıcısını yeniden yükleme

Bir Intune Exchange bağlayıcısını yeniden yüklemeniz gerekebilir. Tek bir bağlayıcı her Exchange kuruluşuna bağlanmak üzere desteklendiğinden, bir kuruluş için ikinci bir bağlayıcı yüklerseniz, yüklediğiniz yeni bağlayıcı özgün bağlayıcının yerini alır.

1. Yeni bağlayıcıyı yüklemeyi başlatmak için [Intune Exchange bağlayıcısını yükleme ve yapılandırma](#install-and-configure-the-intune-exchange-connector) adımlarını kullanın. 
2. İstendiğinde, yeni bağlayıcıyı yüklemek için **Değiştir** ' i seçin.  
   Bağlayıcıyı değiştirmek için ![Yapılandırma istemi @ no__t-1

3. Önceki yordamı kullanarak adımları kullanmaya devam edin ve Intune 'da yeniden oturum açın.
4. Son ekranla birlikte sunulursa, yüklemeyi tamamladıktan sonra **Kapat** ' ı seçin.  
   ![ tam kurulum @ no__t-1
 

## <a name="monitor-the-exchange-connector-activity"></a>Exchange Connector etkinliğini izleme

Exchange bağlayıcısını başarıyla yapılandırdıktan sonra, bağlantıların durumunu ve son başarılı eşitleme denemesini görebilirsiniz. Exchange Connector bağlantısını doğrulamak için:

1. Intune panosunda **Exchange erişimi**' ni seçin.
2. Her Exchange bağlayıcısının bağlantı durumunu doğrulamak için **Şirket Içi Exchange erişimi '** ni seçin.

Ayrıca son başarılı eşitleme denemesinin saat ve tarihini de denetleyebilirsiniz.
--> 

### <a name="system-center-operations-manager-management-pack"></a>System Center Operations Manager yönetim paketi

Intune 1710 sürümünden başlayarak [Exchange Connector ve Intune için Operations Manager yönetim paketini](https://www.microsoft.com/download/details.aspx?id=55990&751be11f-ede8-5a0c-058c-2ee190a24fa6=True&e6b34bbe-475b-1abd-2c51-b5034bcdd6d2=True&fa43d42b-25b5-4a42-fe9b-1634f450f5ee=True)kullanabilirsiniz. Yönetim paketinin kullanılması, sorunları gidermeniz gerektiğinde Exchange bağlayıcısını izlemenin farklı yollarını sağlar.

## <a name="manually-force-a-quick-sync-or-full-sync"></a>Hızlı eşitlemeye veya tam eşitlemeye el ile zorlama

Bir Intune Exchange Bağlayıcısı, EAS ve Intune cihaz kayıtlarını düzenli olarak otomatik olarak eşitler. Bir cihazın uyumluluk durumu değişirse, otomatik eşitleme işlemi, cihaz erişiminin engellenmesi veya izin verilmesi için düzenli olarak kayıtları güncelleştirir.

- **Hızlı eşitleme** , günde birkaç kez düzenli aralıklarla gerçekleşir. Hızlı eşitleme, son eşitlemeden bu yana değiştirilen Intune lisanslı ve şirket içi Exchange koşullu erişim hedefli kullanıcıların cihaz bilgilerini alır.

- Her gün varsayılan olarak **tam eşitleme** gerçekleşir. Tam eşitleme, tüm Intune-lisanslanmış ve şirket içi Exchange koşullu erişim hedefli kullanıcılara ait cihaz bilgilerini alır. Tam eşitleme, Exchange Server bilgilerini de alır ve Azure portal Intune tarafından belirtilen yapılandırmanın Exchange Server üzerinde güncellemeinden emin olmanızı sağlar. 


Intune panosunda, aşağıdaki adımlarla **hızlı eşitleme** veya **tam eşitleme** seçeneklerini kullanarak bir bağlayıcıyı eşitleme çalıştırmaya zorlayabilirsiniz:

   1. Intune panosunda **Exchange erişimi**' ni seçin.
   2. **Şirket Içi Exchange erişimi '** ni seçin.
   3. Eşitlemek istediğiniz bağlayıcıyı seçin ve ardından **hızlı eşitleme** veya **tam eşitleme**' yi seçin.

## <a name="next-steps"></a>Sonraki adımlar

[Şirket içi Exchange için koşullu erişim ilkesi oluşturma](conditional-access-exchange-create.md)
