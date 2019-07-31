---
title: Microsoft Intune şirket içi Exchange bağlayıcısını ayarlama
titleSuffix: Microsoft Intune
description: Şirket içi Exchange bağlayıcısını kullanarak Intune kaydı ve Exchange Active Sync (EAS) temelinde Exchange posta kutularına cihaz erişimini yönetin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/22/2019
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
ms.openlocfilehash: 5cf6299f46ed8db4fdca02947ce15a920816d110
ms.sourcegitcommit: c715c93bb242f4fe44bbdf2fd585909854ed72b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68660936"
---
# <a name="set-up-the-intune-on-premises-exchange-connector-in-microsoft-intune"></a>Microsoft Intune 'de Intune şirket içi Exchange bağlayıcısını ayarlama
Bu makaledeki bilgiler, Intune için Exchange Active Sync şirket içi bağlayıcıyı yüklemenize ve izlemenize yardımcı olur.  Şirket içi Exchange [posta kutularına erişime izin vermek veya erişimi engellemek için](conditional-access-exchange-create.md), şirket içi Exchange bağlayıcısını koşullu erişim ilkelerinizle birlikte kullanırsınız. 

Bir cihaz şirket içi Exchange 'e erişmeye çalıştığında, Exchange Connector, Intune ile cihaz kaydını denetlemek ve cihaz uyumluluk ilkelerinizle uyumluluk sağlamak için Exchange Server 'daki Exchange Active Sync (EAS) kayıtlarını Intune kayıtlarına eşler. Koşullu erişim ilkelerinize bağlı olarak, cihaza erişim izni verilebilir veya engellenebilir. Daha fazla bilgi için bkz. [Intune Ile koşullu erişim kullanmanın yaygın yolları nelerdir?](conditional-access-intune-common-ways-use.md)

Intune, abonelik başına birden çok şirket içi Exchange Bağlayıcısı yüklemeyi destekler. Birden fazla şirket içi Exchange kuruluşunuz varsa, her biri için ayrı bir bağlayıcı oluşturabilirsiniz. Ancak, her bir Exchange kuruluşunu kullanmak için yalnızca bir bağlayıcı yüklenebilir. 

Intune 'un Şirket içi Exchange Server ile iletişim kurmasını sağlayan bir bağlantı kurmak için aşağıdaki genel adımlar verilmiştir:

1. Intune şirket içi Exchange bağlayıcısını Intune portalından indirin.
2. Şirket içi Exchange kuruluşundaki bir bilgisayarda Exchange bağlayıcısını yükleyin ve yapılandırın.
3. Exchange bağlantısını doğrulayın.
4. Intune 'a bağlanmak istediğiniz her ek Exchange kuruluşu için bu adımları tekrarlayın.

## <a name="intune-on-premises-exchange-connector-requirements"></a>Intune şirket içi Exchange bağlayıcısı gereksinimleri
Exchange 'e bağlanmak için bağlayıcı tarafından kullanılabilecek bir Intune lisansı olan bir hesap gerekir. Bu hesap, bağlayıcıyı yüklediğinizde belirtilir.  

Aşağıdaki tabloda şirket içi Exchange bağlayıcısını yüklediğiniz bilgisayara ilişkin gereksinimler listelenmiştir.  

|  Gereksinim  |   Daha fazla bilgi     |
|---------------|------------------------|
|  İşletim sistemleri        | Intune; Windows Server 2008 SP2 64 bit, Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2 veya Windows Server 2016’nın herhangi bir sürümünü çalıştıran bilgisayarlarda şirket içi Exchange bağlayıcısını destekler.<br /><br />Bağlayıcı hiçbir sunucu çekirdeği yüklemesinde desteklenmez.  |
| Microsoft Exchange          | Şirket içi bağlayıcılar için Microsoft Exchange 2010 SP3 veya üzeri ya da eski Exchange Online Ayrılmış gerekir. Exchange Online Dedicated ortamınızın <strong>yeni</strong> yapılandırmada mı yoksa <strong>eski</strong> yapılandırmada mı olduğunu belirlemek için hesap yöneticinize başvurun. |
| Mobil cihaz yönetimi yetkilisi           | [Mobil cihaz yönetimi yetkilisi olarak Intune’u ayarlama](mdm-authority-set.md). |
| Donanım              | Bağlayıcıyı yüklediğiniz bilgisayar 2 GB RAM ve 10 GB boş disk alanı ile birlikte 1,6 GHz CPU gerektirir. |
|  Active Directory eşitlemesi             | Intune’u Exchange Server'a bağlamak üzere bağlayıcıyı kullanabilmeniz için yerel kullanıcılarınızın ve güvenlik gruplarınızın Azure Active Directory örneğinizle eşitlenebilmesi amacıyla [Active Directory eşitlemesini ayarlamanız](users-add.md) gerekir. |
| Ek yazılım         | Bağlayıcıyı barındıran bilgisayara Microsoft .NET Framework 4.5 ve Windows PowerShell 2.0 tam yüklemesi yapılmalıdır. |
| Ağ               | Bağlayıcıyı yüklediğiniz bilgisayar, Exchange Server'ı barındıran etki alanı ile güven ilişkisi olan bir etki alanında olmalıdır.<br /><br />Bilgisayar, 80 ve 443 numaralı Bağlantı Noktaları üzerinden güvenlik duvarları ve proxy sunucular aracılığıyla Intune hizmetine erişmesine olanak sağlayacak yapılandırmalar gerektirir. Intune tarafından kullanılan etki alanları manage.microsoft.com, &#42;manage.microsoft.com ve &#42;.manage.microsoft.com’dur. |

### <a name="exchange-cmdlet-requirements"></a>Exchange cmdlet gereksinimleri

Şirket içi Exchange Bağlayıcısı tarafından kullanılacak bir Active Directory Kullanıcı hesabı oluşturun. Hesabın aşağıdaki gerekli Windows PowerShell Exchange cmdlet'lerini çalıştırma izni olması gerekir:


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

## <a name="download-the-on-premises-exchange-connector-software-installation-package"></a>Şirket içi Exchange bağlayıcısı yazılım yükleme paketini indirme

1. Şirket içi Exchange bağlayıcısı için desteklenen bir Windows Server işletim sisteminde [Azure Portal](https://portal.azure.com)’ı açın ve şirket içi Exchange sunucusunda yönetici olan ve Exchange Server’ı kullanma lisansı bulunan bir kullanıcı hesabıyla oturum açın.

2. **Intune** > **Exchange erişimi** 'ne git  

3. **Kurulum**altında **Exchange ActiveSync şirket içi Bağlayıcısı**' nı seçin ve ardından **Ekle**' yi seçin.

4. **Bağlayıcı Ekle** sayfasında şirket **içi bağlayıcıyı indir**' i seçin. Şirket içi Exchange Bağlayıcısı, açılabilen veya kaydedilebilen sıkıştırılmış (. zip) bir klasörde yer alır. **Dosya İndirme** iletişim kutusunda **Kaydet**'i seçerek sıkıştırılmış klasörü güvenli bir konuma depolayın.

    > [!IMPORTANT]
    > Şirket içi Exchange bağlayıcısı klasöründeki dosyaları yeniden adlandırmayın veya taşımayın. Klasörün içeriğini taşımak veya yeniden adlandırmak, Exchange bağlayıcısı yüklemesinin başarısız olmasına neden olur.

## <a name="install-and-configure-the-intune-on-premises-exchange-connector"></a>Intune şirket içi Exchange bağlayıcısını yükleme ve yapılandırma
Intune şirket içi Exchange bağlayıcısını yüklemek için aşağıdaki adımları gerçekleştirin. Birden çok Exchange kuruluşunuz varsa, ayarlamak istediğiniz her Exchange bağlayıcısı için bu adımları yineleyin.

1. Şirket içi Exchange bağlayıcısı için desteklenen işletim sistemlerinden birinde, **Exchange_Connector_Setup.zip** içindeki dosyaları güvenli bir konuma ayıklayın.

2. Dosyalar ayıklandıktan sonra, şirket içi Exchange bağlayıcısı yüklemek için ayıklanan klasörü açın ve **Exchange_Connector_Setup.exe** dosyasına çift tıklayın.

   > [!IMPORTANT]
   > Hedef klasör güvenli bir konum değilse, şirket içi bağlayıcılarınızı yüklemeyi bitirdikten sonra **MicrosoftIntune.accountcert** sertifika dosyasını silmelisiniz.

3. **Microsoft Intune Exchange Connector** iletişim kutusunda, **Şirket içi Microsoft Exchange Server** veya **Barındırılan Microsoft Exchange Server** seçeneklerinden birini belirleyin.

   ![Exchange Server türünü nerede seçeceğinizi gösteren resim](./media/intune-sa-exchange-connector-config.png)

   Şirket içi Exchange sunucusu için, **İstemci Erişimi Sunucu** rolünü barındıran Exchange sunucusunun sunucu adını veya tam etki alanı adını belirtin.

   Barındırılan bir Exchange sunucusu için, Exchange sunucusunun adresini belirtin. Barındırılan Exchange sunucusunun URL'sini bulmak için:

   1. Office 365 için Web Üzerinde Outlook'u açın.

   2. Sol üst taraftaki **?** simgesini ve ardından **Hakkında**’yı seçin.

   3.           **POP Dış Sunucu** değerini bulun.

   4. Barındırılan Exchange sunucunuzun proxy sunucusu ayarlarını belirtmek için **Proxy Sunucusu**'nu seçin.
       1.           **Mobil cihaz bilgileri eşitlenirken proxy sunucusu kullan**'ı seçin.

       2. Sunucuya erişmek için kullanılan **proxy sunucusu adı** ve **bağlantı noktası numarasını** belirtin.

       3. Proxy sunucusuna erişmek için kullanıcı kimlik bilgilerinin sağlanması gerekiyorsa, **Proxy sunucusuna bağlanmak için kimlik bilgilerini kullan**'ı seçin. Ardından **etki alanı\kullanıcı** ve **parola** girin.

       4. **Tamam**’ı seçin.

4. **Kullanıcı (Etki alanı\kullanıcı)** ve **Parola** alanlarında Exchange sunucunuza bağlanmak için gereken kimlik bilgilerini sağlayın. Belirttiğiniz hesap, Intune 'U kullanmak için bir lisansa sahip olmalıdır. 

5. Kullanıcıların Exchange Server posta kutularına bildirim göndermek için gereken kimlik bilgilerini sağlayın. Bu kullanıcı yalnızca bildirimlere ayrılabilir. Bildirimleri kullanıcının e-posta ile bildirim gönderebilmesi için bir Exchange posta kutusu olması gerekir. Bu bildirimleri Intune’da Koşullu Erişim ilkeleriyle yapılandırabilirsiniz.  

   Otomatik Bulma hizmeti ve Exchange Web Hizmetleri'nin Exchange İstemci Erişimi Sunucusu'nda yapılandırıldığından emin olun. Daha fazla bilgi için bkz. [İstemci Erişimi sunucusu](https://technet.microsoft.com/library/dd298114.aspx).

6. **Parola** alanında, Intune’un Exchange Server'a erişmesini etkinleştirmek için bu hesabın parolasını sağlayın.

7. **Bağlan**’ı seçin.

   > [!NOTE]
   > Bağlantının yapılandırılması birkaç dakika sürebilir.

Yapılandırma sırasında Exchange bağlayıcısı İnternet erişimini sağlamak için proxy ayarlarınızı depolar. Ara sunucu ayarlarınız değişiyorsa, Exchange bağlayıcısını güncelleştirilmiş proxy ayarlarını Exchange Connector 'a uygulamak için yeniden yapılandırmanız gerekir.

Exchange bağlayıcısı bağlantıyı ayarladıktan sonra, Exchange'de yönetilen kullanıcılarla ilişkili mobil cihazlar otomatik olarak eşitlenir ve Exchange bağlayıcısına eklenir. Bu eşitlemenin tamamlanması biraz sürebilir.

> [!NOTE]
> Şirket içi Exchange bağlayıcısını yüklediyseniz ve ileride Exchange bağlantısını silerseniz, Şirket içi Exchange bağlayıcısını yüklü olduğu bilgisayardan kaldırmanız gerekir.



## <a name="install-connectors-for-multiple-exchange-organizations"></a>Birden çok Exchange kuruluşu için bağlayıcıları yükleme
Intune abonelik başına birden çok şirket içi Exchange bağlayıcısını destekler. Birden çok Exchange kuruluşu olan bir kiracı için, her bir Exchange kuruluşu için bir bağlayıcı ayarlayabilir, ancak tek bir kuruluş için yalnızca tek bir bağlayıcı oluşturabilirsiniz. 

Birden çok Exchange kuruluşa bağlanmak için bağlayıcı yükleyeceksiniz,. zip klasörünü bir kez indirin ve ardından yüklediğiniz her bağlayıcı için aynı indirmeyi yeniden kullanın. Her ek bağlayıcı için, bir önceki bölümdeki adımları izleyerek Kurulum programını Exchange kuruluşundaki bir sunucuda ayıklayın ve çalıştırın.

Aşağıdaki bölümlerde açıklanan yüksek kullanılabilirlik, izleme ve el ile eşitleme özellikleri, Intune 'a bağlanan her bir Exchange kuruluşu için desteklenir.

## <a name="on-premises-exchange-connector-high-availability-support"></a>Şirket içi Exchange bağlayıcısı yüksek kullanılabilirlik desteği 
Şirket içi Exchange Connector için yüksek kullanılabilirlik, bağlayıcının kullandığı Exchange Istemci erişimi sunucusu (CAS) kullanılamaz hale geldiği anlamına gelir, bağlayıcının bu Exchange kuruluşu için farklı CA 'LAR kullanmak üzere geçiş yapabilir. Exchange bağlayıcısının kendisi yüksek kullanılabilirliği desteklemez. Bağlayıcı başarısız olursa, otomatik yük devretme yoktur ve [Yeni bir bağlayıcı yükleyerek](#reinstall-the-on-premises-exchange-connector)Bu bağlayıcıyı değiştirmeniz gerekir. 

Bağlayıcı, belirtilen CA 'ları kullanarak Exchange 'e başarılı bir bağlantı oluşturduktan sonra, yük devretmeyi gerçekleştirmek için bu Exchange kuruluşu için ek CASs 'yi bulur. Ek CASs hakkında bilgi, bağlayıcının varsa, birincil CA 'LAR kullanılabilir hale gelene kadar başka bir CA 'ya yük devretmesine olanak sağlar. Varsayılan olarak, ek CASs 'leri bulma etkindir. Aşağıdaki yordamı kullanarak yük devretmeyi devre dışı bırakabilirsiniz:  
1. Exchange bağlayıcısının yüklü olduğu sunucuda%*ProgramData*% \ Microsoft\windows Intune Exchange Connector ' a gidin. 
2. Bir metin düzenleyicisi kullanarak **OnPremisesExchangeConnectorServiceConfiguration.xml** dosyasını açın.
3. Özelliği devre dışı bırakmak için &lt;IsCasFailoverEnabled&gt;**true**&lt;/IsCasFailoverEnabled&gt; değerini &lt;IsCasFailoverEnabled&gt;**false**&lt;/IsCasFailoverEnabled&gt; olarak değiştirin.  
 
## <a name="optional-performance-tuning-for-the-exchange-connector"></a>Exchange Connector için isteğe bağlı performans ayarı  

Exchange ActiveSync ile 5.000 veya daha fazla cihazı destekettiğinizde, bağlayıcının performansını artırmak için isteğe bağlı bir ayar yapılandırabilirsiniz. Exchange 'in bir PowerShell komutu çalışma alanının birden çok örneğini kullanmasını etkinleştirerek daha yüksek performans elde edilir. 

Bu değişikliği yapmadan önce, Exchange bağlayıcısını çalıştırmak için kullandığınız hesabın diğer Exchange yönetim amaçları için kullanılmadığından emin olun. Bunun nedeni, Exchange 'in hesap başına sınırlı sayıda çalışma alanına sahip olması ve çoğu bağlayıcının bağlayıcı tarafından kullanılması anlamına gelir. 

Bu performans değişikliği, daha eski veya daha yavaş donanımlar üzerinde çalışan bağlayıcılar için uygun değildir.  

1. Bağlayıcının yüklendiği sunucuda, bağlayıcılar yükleme dizinini açın.  Varsayılan konum *C:\ProgramData\Microsoft\Windows Intune Exchange Connector*' dır. 
2. *OnPremisesExchangeConnectorServiceConfiguration. xml*dosyasını düzenleyin.
3. **Enableparallelcommandsupport** öğesini bulun ve değeri **true**olarak ayarlayın:  
     
   \<Enableparallelcommandsupport > true\</enableparallelcommandsupport >
4. Dosyayı kaydedin ve ardından Microsoft Intune Exchange Connector hizmetini yeniden başlatın.

## <a name="reinstall-the-on-premises-exchange-connector"></a>Şirket içi Exchange bağlayıcısını yeniden yükleme
Bir Exchange bağlayıcısını yeniden yüklemeniz gerekebilir. Tek bir bağlayıcı her Exchange kuruluşuna bağlanmak üzere desteklendiğinden, bir kuruluş için ikinci bir bağlayıcı yüklerseniz, yüklediğiniz yeni bağlayıcı özgün bağlayıcının yerini alır.

1. Yeni bağlayıcıyı yüklemeye başlamak için [Intune şirket Içi Exchange bağlayıcısını yükleme ve yapılandırma](#install-and-configure-the-intune-on-premises-exchange-connector) adımlarını kullanın. 
2. İstendiğinde, yeni bağlayıcıyı yüklemek için **Değiştir** ' i seçin.  
   ![Bağlayıcının yerine geçecek yapılandırma istemi](./media/exchange-connector-install/prompt-to-replace.png)

3. Önceki yordamı kullanarak adımları kullanmaya devam edin ve Intune 'da yeniden oturum açın.
4. Son ekranla birlikte sunulursa, yüklemeyi tamamladıktan sonra **Kapat** ' ı seçin.  
   ![Kurulumu Tamam](./media/exchange-connector-install/successful-reinstall.png)
 

## <a name="monitor-the-exchange-connector-activity"></a>Exchange bağlayıcısı etkinliğini izleme

Exchange bağlayıcısını başarıyla yapılandırdıktan sonra, bağlantıların durumunu ve son başarılı eşitleme denemesini görebilirsiniz. Exchange Connector bağlantısını doğrulamak için:

1. Intune panosunda **Exchange erişimi**' ni seçin.
2. Her Exchange bağlayıcısının bağlantı durumunu doğrulamak için **Şirket Içi Exchange erişimi '** ni seçin.

Ayrıca son başarılı eşitleme denemesinin tarih ve saatini kontrol edebilirsiniz.
--> 

### <a name="system-center-operations-manager-management-pack"></a>System Center Operations Manager yönetim paketi

Intune 1710 sürümünden başlayarak [Exchange Connector ve Intune için Operations Manager yönetim paketini](https://www.microsoft.com/download/details.aspx?id=55990&751be11f-ede8-5a0c-058c-2ee190a24fa6=True&e6b34bbe-475b-1abd-2c51-b5034bcdd6d2=True&fa43d42b-25b5-4a42-fe9b-1634f450f5ee=True)kullanabilirsiniz. Yönetim paketinin kullanılması, sorunları gidermeniz gerektiğinde Exchange bağlayıcısını izlemenin farklı yollarını sağlar.

## <a name="manually-force-a-quick-sync-or-full-sync"></a>Hızlı eşitlemeyi veya tam eşitlemeyi el ile zorlama
Şirket içi Exchange Bağlayıcısı, EAS ve Intune cihaz kayıtlarını düzenli olarak otomatik olarak eşitler. Bir cihazın uyumluluk durumu değişirse, otomatik eşitleme işlemi, cihaz erişiminin engellenmesi veya izin verilmesi için düzenli olarak kayıtları güncelleştirir.

- **Hızlı eşitleme** günde birkaç kez düzenli aralıklarla yapılır. Hızlı eşitleme, son eşitlemeden bu yana değiştirilen Intune lisanslı ve şirket içi Exchange koşullu erişim hedefli kullanıcıların cihaz bilgilerini alır.

- **Tam eşitleme** varsayılan olarak günde bir kez gerçekleştirilir. Tam eşitleme, tüm Intune-lisanslanmış ve şirket içi Exchange koşullu erişim hedefli kullanıcılara ait cihaz bilgilerini alır. Tam eşitlemede Exchange sunucu bilgileri de alınır ve Azure portalında Intune tarafından belirtilen yapılandırmanın Exchange Server'da güncelleştirilmesi sağlanır. 


Intune panosundaki **Hızlı Eşitleme** veya **Tam Eşitleme** seçeneğini kullanarak bağlayıcıyı eşitleme çalıştırmaya zorlamak için aşağıdaki adımları izleyebilirsiniz:

   1. Intune panosunda **Exchange erişimi**' ni seçin.
   2. **Şirket Içi Exchange erişimi '** ni seçin.
   3. Eşitlemek istediğiniz bağlayıcıyı seçin ve sonra da **Hızlı Eşitleme**'yi veya **Tam Eşitleme**'yi seçin.

## <a name="next-steps"></a>Sonraki adımlar
[Şirket içi Exchange için koşullu erişim ilkesi oluşturma](conditional-access-exchange-create.md)
