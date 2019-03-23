---
title: Microsoft Intune ayarlama şirket içi Exchange Bağlayıcısı | Microsoft Intune
description: Şirket içi Exchange bağlayıcısını kullanarak Intune kaydı ve Exchange Active Sync (EAS) temelinde Exchange posta kutularına cihaz erişimini yönetin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/22/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a0376ea1-eb13-4f13-84da-7fd92d8cd63c
ms.reviewer: demerson
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: deb3e57876dffdc19129a5d845872d90d5833aaf
ms.sourcegitcommit: 1069b3b1ed593c94af725300aafd52610c7d8f04
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2019
ms.locfileid: "58394701"
---
# <a name="set-up-the-intune-on-premises-exchange-connector-in-microsoft-intune"></a>Intune şirket içi Exchange connector, Microsoft Intune ayarlama
Bu makaledeki bilgiler yükleyin ve ardından Exchange Active Sync şirket içi Bağlayıcısı için Intune izlemenize yardımcı olur.  Intune şirket içi Exchange bağlayıcısıyla kullanan, [izin vermek veya Exchange erişimi engellemek için koşullu erişim ilkeleri şirket içi posta kutularını](conditional-access-exchange-create.md). 

Bir cihaz, şirket içi Exchange erişmeyi denediğinde, Exchange Bağlayıcısı, Exchange Active Sync (EAS) Intune ile cihaz kaydı ve uyumluluk için cihaz uyumluluk ilkelerini denetlemek için Intune kayıt sunucusu Exchange kaydeder eşler. Koşullu erişim ilkelerine bağlı olarak, cihazın erişimine izin, veya engellendi. Daha fazla bilgi için [Intune ile koşullu erişim kullanmanın yaygın yolları nelerdir?](conditional-access-intune-common-ways-use.md)

Intune, abonelik başına birden çok şirket içi Exchange Bağlayıcısı yüklenmesini destekler. Birden fazla şirket içi Exchange kuruluşu varsa, her biri için ayrı bir Bağlayıcısı'nı ayarlayabilirsiniz. Ancak, yalnızca tek bir bağlayıcıyı olabilir yüklenmiş tek tek her Exchange kuruluşu için kullanın. 

İletişim kurmak Intune şirket içi Exchange Server ile sağlayan bir bağlantı ayarlamak için genel adımlar şunlardır:

1. Intune şirket içi Exchange Bağlayıcısı, Intune portalından indirin.
2. Şirket içi Exchange kuruluşundaki bir bilgisayarda Exchange bağlayıcısını yükleyin ve yapılandırın.
3. Exchange bağlantısını doğrulayın.
4. Intune'a bağlamak istediğiniz her ek Exchange kuruluşu için bu adımları yineleyin.

## <a name="intune-on-premises-exchange-connector-requirements"></a>Intune şirket içi Exchange bağlayıcısı gereksinimleri
Bağlayıcı tarafından Exchange'e bağlanmak için kullanılan bir Intune lisansı olan bir hesap gerekir. Bağlayıcısını yüklediğinizde, hesabı belirtilir.  

Aşağıdaki tabloda şirket içi Exchange bağlayıcısını yüklediğiniz bilgisayara ilişkin gereksinimler listelenmiştir.  

|  Gereksinim  |   Daha fazla bilgi     |
|---------------|------------------------|
|  İşletim sistemleri        | Intune; Windows Server 2008 SP2 64 bit, Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2 veya Windows Server 2016’nın herhangi bir sürümünü çalıştıran bilgisayarlarda şirket içi Exchange bağlayıcısını destekler.<br /><br />Bağlayıcı hiçbir Sunucu Çekirdeği yüklemesinde desteklenmez.  |
| Microsoft Exchange          | Şirket içi bağlayıcılar için Microsoft Exchange 2010 SP3 veya üzeri ya da eski Exchange Online Ayrılmış gerekir. Exchange Online Dedicated ortamınızın <strong>yeni</strong> yapılandırmada mı yoksa <strong>eski</strong> yapılandırmada mı olduğunu belirlemek için hesap yöneticinize başvurun. |
| Mobil cihaz yönetimi yetkilisi           | [Mobil cihaz yönetimi yetkilisi olarak Intune’u ayarlama](mdm-authority-set.md). |
| Donanım              | Bağlayıcıyı yüklediğiniz bilgisayar 2 GB RAM ve 10 GB boş disk alanı ile birlikte 1,6 GHz CPU gerektirir. |
|  Active Directory eşitlemesi             | Intune’u Exchange Server'a bağlamak üzere bağlayıcıyı kullanabilmeniz için yerel kullanıcılarınızın ve güvenlik gruplarınızın Azure Active Directory örneğinizle eşitlenebilmesi amacıyla [Active Directory eşitlemesini ayarlamanız](users-add.md) gerekir. |
| Ek yazılım         | Bağlayıcıyı barındıran bilgisayara Microsoft .NET Framework 4.5 ve Windows PowerShell 2.0 tam yüklemesi yapılmalıdır. |
| Ağ               | Bağlayıcıyı yüklediğiniz bilgisayar, Exchange Server'ı barındıran etki alanı ile güven ilişkisi olan bir etki alanında olmalıdır.<br /><br />Bilgisayar, 80 ve 443 numaralı Bağlantı Noktaları üzerinden güvenlik duvarları ve proxy sunucular aracılığıyla Intune hizmetine erişmesine olanak sağlayacak yapılandırmalar gerektirir. Intune tarafından kullanılan etki alanları manage.microsoft.com, &#42;manage.microsoft.com ve &#42;.manage.microsoft.com’dur. |

### <a name="exchange-cmdlet-requirements"></a>Exchange cmdlet gereksinimleri

Şirket içi Exchange Bağlayıcısı tarafından kullanılacak olan bir Active Directory kullanıcı hesabı oluşturun. Hesabın aşağıdaki gerekli Windows PowerShell Exchange cmdlet'lerini çalıştırma izni olması gerekir:


 -   Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings
 -   Get-CasMailbox, Set-CasMailbox
 -   Get-ActiveSyncMailboxPolicy, Set-ActiveSyncMailboxPolicy, New-ActiveSyncMailboxPolicy, Remove-ActiveSyncMailboxPolicy
 -   Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule
 -   Get-ActiveSyncDeviceStatistics
 -   Get-ActiveSyncDevice
 -   Get-ExchangeServer
 -   Get-ActiveSyncDeviceClass
 -   Get-Recipient
 -   Clear-ActiveSyncDevice, Remove-ActiveSyncDevice
 -   Set-ADServerSettings
 -   Get-Command

## <a name="download-the-on-premises-exchange-connector-software-installation-package"></a>Şirket içi Exchange bağlayıcısı yazılım yükleme paketini indirme

1. Şirket içi Exchange bağlayıcısı için desteklenen bir Windows Server işletim sisteminde [Azure portal](https://portal.azure.com)’ı açın ve şirket içi Exchange sunucusunda yönetici olan ve Exchange Server’ı kullanma lisansı bulunan bir kullanıcı hesabıyla oturum açın.

2. Git **Intune** > **Exchange erişimi**  

3. Altında **Kurulum**, seçin **Exchange ActiveSync şirket içi Bağlayıcısı**ve ardından **Ekle**.

4. Üzerinde **ekleme bağlayıcı** sayfasında **şirket içi bağlayıcıyı indir**. Şirket içi Exchange Bağlayıcısı'nı açık veya kaydedilebilen bir sıkıştırılmış (.zip) klasörde ' dir. **Dosya İndirme** iletişim kutusunda **Kaydet**'i seçerek sıkıştırılmış klasörü güvenli bir konuma depolayın.

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

   3. **POP Dış Sunucu** değerini bulun.

   4. Barındırılan Exchange sunucunuzun proxy sunucusu ayarlarını belirtmek için **Proxy Sunucusu**'nu seçin.
       1. **Mobil cihaz bilgileri eşitlenirken proxy sunucusu kullan**'ı seçin.

       2. Sunucuya erişmek için kullanılan **proxy sunucusu adı** ve **bağlantı noktası numarasını** belirtin.

       3. Proxy sunucusuna erişmek için kullanıcı kimlik bilgilerinin sağlanması gerekiyorsa, **Proxy sunucusuna bağlanmak için kimlik bilgilerini kullan**'ı seçin. Ardından **etki alanı\kullanıcı** ve **parola** girin.

       4. **Tamam**’ı seçin.

4. **Kullanıcı (Etki alanı\kullanıcı)** ve **Parola** alanlarında Exchange sunucunuza bağlanmak için gereken kimlik bilgilerini sağlayın. Belirttiğiniz hesabın Intune'ı kullanma Lisansı olmalıdır. 

5. Kullanıcıların Exchange Server posta kutularına bildirim göndermek için gereken kimlik bilgilerini sağlayın. Bu kullanıcı yalnızca bildirimlere ayrılabilir. Bildirim kullanıcısına, e-posta ile bildirim göndermek için bir Exchange posta kutusu gerekir. Bu bildirimleri Intune’da koşullu erişim ilkeleriyle yapılandırabilirsiniz.  

       Ensure that the Autodiscover service and Exchange Web Services are configured on the Exchange Client Access Server. For more information, see [Client Access server](https://technet.microsoft.com/library/dd298114.aspx).

6. **Parola** alanında, Intune’un Exchange Server'a erişmesini etkinleştirmek için bu hesabın parolasını sağlayın.

7. **Bağlan**’ı seçin.

   > [!NOTE]
   > Bağlantının yapılandırılması birkaç dakika sürebilir.

Yapılandırma sırasında Exchange bağlayıcısı İnternet erişimini sağlamak için proxy ayarlarınızı depolar. Proxy ayarlarınız değişirse, güncelleştirilen proxy ayarlarını Exchange Connector'a uygulamak için Exchange connector'ı yeniden yapılandırmanız gerekir.

Exchange bağlayıcısı bağlantıyı ayarladıktan sonra, Exchange'de yönetilen kullanıcılarla ilişkili mobil cihazlar otomatik olarak eşitlenir ve Exchange bağlayıcısına eklenir. Bu eşitlemenin tamamlanması biraz sürebilir.

> [!NOTE]
> Şirket içi Exchange bağlayıcısını yüklediyseniz ve ileride Exchange bağlantısını silerseniz, Şirket içi Exchange bağlayıcısını yüklü olduğu bilgisayardan kaldırmanız gerekir.



## <a name="install-connectors-for-multiple-exchange-organizations"></a>Birden çok Exchange kuruluşu için bağlayıcıları yükleme
Intune abonelik başına birden çok şirket içi Exchange bağlayıcısını destekler. Birden çok Exchange kuruluşu ile bir kiracı için bir bağlayıcı her Exchange kuruluşu, ancak tek bir kuruluş için yalnızca tek bir bağlayıcıyı ayarlayabilirsiniz. 

Bağlanmak için birden çok Exchange kuruluşu için bağlayıcılar yükleyeceksiniz değilse, bir kez .zip klasörünü indirin ve daha sonra aynı yüklediğiniz her bağlayıcı için indirme yeniden. Her bir ek bağlayıcı için ayıklayın ve Exchange kuruluşunuzdaki bir sunucuda Kurulum programını çalıştırmak için önceki bölümdeki adımları izleyin.

Yüksek kullanılabilirlik, izleme ve el ile eşitleme aşağıdaki bölümlerde açıklanan özellikler, Intune'a bağlanır her Exchange kuruluşu için desteklenir.

## <a name="on-premises-exchange-connector-high-availability-support"></a>Şirket içi Exchange bağlayıcısı yüksek kullanılabilirlik desteği 
Yüksek kullanılabilirlik için Exchange istemci erişimi sunucusu (bağlayıcıyı kullanan kullanılamaz hale CAS) gereken şirket içi Exchange Bağlayıcısı anlamına gelir bağlayıcıyı, Exchange kuruluşu için farklı bir CA'ları kullanmak için geçebilirsiniz. Exchange Bağlayıcısı yüksek kullanılabilirliği desteklemez. Bağlayıcı başarısız olursa, hiçbir otomatik yük devretme bu bağlayıcı tarafından değiştirmelisiniz varsa ve [yeni bir bağlayıcı yükleme](#reinstall-the-on-premises-exchange-connector). 

Bağlayıcısı belirtilen CAS'yi kullanarak Exchange başarılı bir bağlantı oluşturduktan sonra Yük devretme gerçekleştirmek için bağlayıcıyı, Exchange kuruluşu için ek CASs bulur. Birincil CAS kullanılabilir duruma gelene kadar varsa ek CASs bilgisi bağlayıcı başka bir CAS'ye Yük Devretmesini sağlar. Varsayılan olarak, ek CASs bulunmasını etkinleştirilir. Aşağıdaki yordamı kullanarak, yük devretme kapatabilirsiniz:  
1. Exchange Bağlayıcısı'nın yüklü olduğu sunucuda % Git*ProgramData*%\Microsoft\Windows Intune Exchange Connector. 
2. Bir metin düzenleyicisi kullanarak **OnPremisesExchangeConnectorServiceConfiguration.xml** dosyasını açın.
3. Özelliği devre dışı bırakmak için &lt;IsCasFailoverEnabled&gt;**true**&lt;/IsCasFailoverEnabled&gt; değerini &lt;IsCasFailoverEnabled&gt;**false**&lt;/IsCasFailoverEnabled&gt; olarak değiştirin.    
 

## <a name="reinstall-the-on-premises-exchange-connector"></a>Şirket içi Exchange Bağlayıcısı'nı yeniden yükleyin
Bir Exchange connector'ı yeniden yüklemeniz gerekebilir. Bir kuruluş için ikinci bir bağlayıcı yüklerseniz her Exchange kuruluşu için bağlanmak için tek bir bağlayıcıyı desteklenmediği için yüklediğiniz yeni bağlayıcı özgün bağlayıcının yerini alır.

1. Adımları uygulayın [yükleyin ve Intune şirket içi Exchange bağlayıcısını yapılandırma](#install-and-configure-the-intune-on-premises-exchange-connector) yeni bağlayıcı yüklemesini başlatmak için. 
2. Sorulduğunda, **değiştirin** yeni bağlayıcıyı yüklemek için.  
   ![Bir bağlayıcı değiştirilecek yapılandırma istemi](./media/exchange-connector-install/prompt-to-replace.png)

3. Adımlar, önceki yordam form ve Intune'a tekrar oturum kullanmaya devam edin.
4. Son ekran yansıtılırken seçin **Kapat** tıklayarak yüklemeyi tamamlayın.  
   ![Kurulumu tamamlayın](./media/exchange-connector-install/successful-reinstall.png)
 

## <a name="monitor-the-exchange-connector-activity"></a>Exchange bağlayıcısı etkinliğini izleme

Exchange Bağlayıcısı'nı başarıyla yapılandırdıktan sonra bağlantılar ve son başarılı eşitleme denemesinin durumunu görüntüleyebilirsiniz. Exchange connector bağlantısını doğrulamak için:

1. Intune panosunda seçin **Exchange erişimi**.
2. Seçin **şirket içi Exchange erişimi** her Exchange connector için bağlantı durumunu doğrulayın.

Ayrıca son başarılı eşitleme denemesinin tarih ve saatini kontrol edebilirsiniz.
--> 

### <a name="system-center-operations-manager-management-pack"></a>System Center Operations Manager Yönetim Paketi

Intune 1710 sürümünden itibaren kullanabilirsiniz [Exchange Bağlayıcısı ve Intune için Operations Manager Yönetim Paketi](https://www.microsoft.com/download/details.aspx?id=55990&751be11f-ede8-5a0c-058c-2ee190a24fa6=True&e6b34bbe-475b-1abd-2c51-b5034bcdd6d2=True&fa43d42b-25b5-4a42-fe9b-1634f450f5ee=True). Yönetim Paketi kullanarak sorunları gidermek gerektiğinde Exchange bağlayıcısını izlemek farklı yollar sunar.

## <a name="manually-force-a-quick-sync-or-full-sync"></a>Hızlı eşitlemeyi veya tam eşitlemeyi el ile zorlama
Bir şirket içi Exchange connector EAS ve Intune cihaz kayıtları düzenli aralıklarla otomatik olarak eşitler. Bir cihazın uyumluluk durumunu değişirse, böylece cihaz erişimi engellendi veya izin verilen otomatik eşitleme işlemini düzenli olarak kayıtları güncelleştirir.

   - **Hızlı eşitleme** günde birkaç kez düzenli aralıklarla yapılır. Hızlı eşitleme, Intune lisanslı olan, şirket içi Exchange koşullu erişimi için hedeflenen ve son eşitlemeden sonra değiştirilmiş olan kullanıcıların cihaz bilgilerini alır.

   - **Tam eşitleme** varsayılan olarak günde bir kez gerçekleştirilir. Tam eşitleme, Intune lisanslı olan ve şirket içi Exchange koşullu erişimi için hedeflenen kullanıcıların cihaz bilgilerini alır. Tam eşitlemede Exchange sunucu bilgileri de alınır ve Azure portalında Intune tarafından belirtilen yapılandırmanın Exchange Server'da güncelleştirilmesi sağlanır. 


Intune panosundaki **Hızlı Eşitleme** veya **Tam Eşitleme** seçeneğini kullanarak bağlayıcıyı eşitleme çalıştırmaya zorlamak için aşağıdaki adımları izleyebilirsiniz:

   1. Intune panosunda seçin **Exchange erişimi**.
   2. Seçin **şirket içi Exchange erişimi**.
   3. Eşitlemek istediğiniz bağlayıcıyı seçin ve sonra da **Hızlı Eşitleme**'yi veya **Tam Eşitleme**'yi seçin.

## <a name="next-steps"></a>Sonraki adımlar
[Şirket içi Exchange için koşullu erişim ilkesi oluşturma](conditional-access-exchange-create.md)
