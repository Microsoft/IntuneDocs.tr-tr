---
title: Microsoft Intune şirket içi Exchange bağlayıcısını ayarlama
titleSuffix: ''
description: Şirket içi Exchange bağlayıcısını kullanarak Intune kaydı ve Exchange Active Sync (EAS) temelinde Exchange posta kutularına cihaz erişimini yönetin.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 03/08/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a0376ea1-eb13-4f13-84da-7fd92d8cd63c
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7de97ac8a9149d2574bbc97df67408f85b243a11
ms.sourcegitcommit: 97b9f966f23895495b4c8a685f1397b78cc01d57
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34744695"
---
# <a name="set-up-the-intune-on-premises-exchange-connector-in-microsoft-intune-azure"></a>Microsoft Intune Azure’da Intune şirket içi Exchange bağlayıcısını ayarlama

Şirket içi Exchange Server ortamında, Exchange şirket içi posta kutularına erişime izin vermek veya bu erişimi engellemek için Intune koşullu erişimi kullanılabilir. Exchange Active Sync şirket içi bağlayıcılarını kullanarak Intune'u Exchange kuruluşlarınıza bağlayın ve cihaz uyumluluk ilkeleriyle birlikte Intune koşullu erişimini ayarlayın. Ardından, bir cihaz Exchange'e bağlanmayı denediğinde Intune cihazın Intune'a kayıtlı ve uyumlu olup olmadığını saptar. Hangi cihazların Intune'a kayıtlı olduğunu saptamak için, şirket içi Exchange bağlayıcısı Exchange Server'daki Exchange Active Sync (EAS) kayıtlarını Intune kayıtlarına eşler. Bunun nasıl çalıştığı hakkında daha fazla bilgi için bkz. [Intune ile koşullu erişimi kullanmanın yaygın yolları nelerdir?](conditional-access-intune-common-ways-use.md)

> [!IMPORTANT]
> Intune artık abonelik başına birden çok şirket içi Exchange bağlayıcısını destekler. Birden çok şirket içi Exchange kuruluşunuz varsa, her Exchange kuruluşu için ayrı bağlayıcılar ayarlayabilirsiniz.

Microsoft Intune’un şirket içi Exchange Server ile iletişim kurmasını sağlayan bir bağlantı ayarlama işleminin genel adımları şöyledir:

1.  Intune şirket içi Exchange bağlayıcısını Azure portalından indirin.
2.  Şirket içi Exchange kuruluşundaki bir bilgisayarda Exchange bağlayıcısını yükleyin ve yapılandırın.
3.  Exchange bağlantısını doğrulayın.
4. Intune'a bağlamak istediğiniz her Exchange kuruluşu için bu adımları yineleyin.

## <a name="intune-on-premises-exchange-connector-requirements"></a>Intune şirket içi Exchange bağlayıcısı gereksinimleri
Aşağıdaki tabloda şirket içi Exchange bağlayıcısını yüklediğiniz bilgisayara ilişkin gereksinimler listelenmiştir.


|            Gereksinim             |                                                                                                                                                                                                        Daha fazla bilgi                                                                                                                                                                                                        |
|------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|         İşletim sistemleri          |                                                               Intune; Windows Server 2008 SP2 64 bit, Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2 veya Windows Server 2016’nın herhangi bir sürümünü çalıştıran bilgisayarlarda şirket içi Exchange bağlayıcısını destekler.<br /><br />Bağlayıcı hiçbir Sunucu Çekirdeği yüklemesinde desteklenmez.                                                                |
|         Microsoft Exchange         |                                                                           Şirket içi bağlayıcılar için Microsoft Exchange 2010 SP1 veya üzeri ya da eski Exchange Online Dedicated gerekir. Exchange Online Dedicated ortamınızın <strong>yeni</strong> yapılandırmada mı yoksa <strong>eski</strong> yapılandırmada mı olduğunu belirlemek için hesap yöneticinize başvurun.                                                                           |
| Mobil cihaz yönetimi yetkilisi |                                                                                                                              [Mobil cihaz yönetimi yetkilisi olarak Intune’u ayarlama](https://docs.microsoft.com/intune-classic/deploy-use/prerequisites-for-enrollment#step-2-mdm-authority-set).                                                                                                                               |
|              Donanım              |                                                                                                                                                     Bağlayıcıyı yüklediğiniz bilgisayar 2 GB RAM ve 10 GB boş disk alanı ile birlikte 1,6 GHz CPU gerektirir.                                                                                                                                                      |
|  Active Directory eşitlemesi  |                                                                                      Intune’u Exchange Server'a bağlamak üzere bağlayıcıyı kullanabilmeniz için yerel kullanıcılarınızın ve güvenlik gruplarınızın Azure Active Directory örneğinizle eşitlenebilmesi amacıyla [Active Directory eşitlemesini ayarlamanız](users-add.md) gerekir.                                                                                      |
|        Ek yazılım         |                                                                                                                                           Bağlayıcıyı barındıran bilgisayara Microsoft .NET Framework 4.5 ve Windows PowerShell 2.0 tam yüklemesi yapılmalıdır.                                                                                                                                           |
|              Ağ               | Bağlayıcıyı yüklediğiniz bilgisayar, Exchange Server'ı barındıran etki alanı ile güven ilişkisi olan bir etki alanında olmalıdır.<br /><br />Bilgisayar, 80 ve 443 numaralı Bağlantı Noktaları üzerinden güvenlik duvarları ve proxy sunucular aracılığıyla Intune hizmetine erişmesine olanak sağlayacak yapılandırmalar gerektirir. Intune tarafından kullanılan etki alanları manage.microsoft.com, &#42;manage.microsoft.com ve &#42;.manage.microsoft.com’dur. |

### <a name="exchange-cmdlet-requirements"></a>Exchange cmdlet gereksinimleri

Şirket içi Exchange bağlayıcısı tarafından kullanılacak bir Active Directory kullanıcı hesabı oluşturmanız gerekir. Hesabın aşağıdaki gerekli Windows PowerShell Exchange cmdlet'lerini çalıştırma izni olması gerekir:


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

1. Şirket içi Exchange bağlayıcısı için desteklenen bir Windows Server işletim sisteminde [Azure Portal](http://portal.azure.com)’ı açın ve şirket içi Exchange sunucusunda yönetici olan ve Exchange Server’ı kullanma lisansı bulunan bir kullanıcı hesabıyla oturum açın.

2. Soldaki menüden **Tüm hizmetler**’i seçtikten sonra metin kutusu filtresine **Intune** yazın.

3. **Intune**’u seçin ve Intune Panosu açıldığında **Şirket içi erişim**’i seçin.

4. **Kurulum**'un altında, **Exchange ActiveSync bağlayıcıları**’nı ve **Şirket içi bağlayıcıyı indir**’i seçin.

5.  Şirket içi Exchange bağlayıcısı, açılabilen veya kaydedilebilen sıkıştırılmış (.zip) bir klasörde yer alır. **Dosya İndirme** iletişim kutusunda **Kaydet**'i seçerek sıkıştırılmış klasörü güvenli bir konuma depolayın.

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

   Şirket içi Exchange sunucusu için **İstemci Erişimi Sunucu** rolünü barındıran Exchange sunucusunun sunucu adını veya tam etki alanı adını belirtin.

   Barındırılan bir Exchange sunucusu için, Exchange sunucusunun adresini belirtin. Barındırılan Exchange sunucusunun URL'sini bulmak için:

   1. Office 365 için Web Üzerinde Outlook'u açın.

   2. Sol üst taraftaki **?** simgesini ve ardından **Hakkında**’yı seçin.

   3. **POP Dış Sunucu** değerini bulun.

   4. Barındırılan Exchange sunucunuzun proxy sunucusu ayarlarını belirtmek için **Proxy Sunucusu**'nu seçin.
       1. **Mobil cihaz bilgileri eşitlenirken proxy sunucusu kullan**'ı seçin.

       2. Sunucuya erişmek için kullanılan **proxy sunucusu adı** ve **bağlantı noktası numarasını** belirtin.

       3. Proxy sunucusuna erişmek için kullanıcı kimlik bilgilerinin sağlanması gerekiyorsa, **Proxy sunucusuna bağlanmak için kimlik bilgilerini kullan**'ı seçin. Ardından **etki alanı\kullanıcı** ve **parola** girin.

       4. **Tamam**’ı seçin.

   5. **Kullanıcı (Etki alanı\kullanıcı)** ve **Parola** alanlarında Exchange sunucunuza bağlanmak için gereken kimlik bilgilerini sağlayın.

   6.  Kullanıcıların Exchange Server posta kutularına bildirim göndermek için gereken kimlik bilgilerini sağlayın. Bu kullanıcı yalnızca bildirimlere ayrılabilir. Bildirim kullanıcısına, e-postayla bildirim gönderebilmesi için bir Exchange posta kutusu gerekir. Bu bildirimleri Intune’da koşullu erişim ilkeleriyle yapılandırabilirsiniz.  

       Otomatik Bulma hizmeti ve Exchange Web Hizmetleri'nin Exchange İstemci Erişimi Sunucusu'nda yapılandırıldığından emin olun. Daha fazla bilgi için bkz. [İstemci Erişimi sunucusu](https://technet.microsoft.com/library/dd298114.aspx).

   7.  **Parola** alanında, Intune’un Exchange Server'a erişmesini etkinleştirmek için bu hesabın parolasını sağlayın.

   8. **Bağlan**’ı seçin.

   > [!NOTE]
   > Bağlantının yapılandırılması birkaç dakika sürebilir.

Yapılandırma sırasında Exchange bağlayıcısı İnternet erişimini sağlamak için proxy ayarlarınızı depolar. Proxy ayarlarınız değişirse, güncelleştirilen proxy ayarlarını Exchange bağlayıcısına uygulamak için Exchange bağlayıcısını yeniden yapılandırmanız gerekir.

Exchange bağlayıcısı bağlantıyı ayarladıktan sonra, Exchange'de yönetilen kullanıcılarla ilişkili mobil cihazlar otomatik olarak eşitlenir ve Exchange bağlayıcısına eklenir. Bu eşitlemenin tamamlanması biraz sürebilir.

> [!NOTE]
> Şirket içi Exchange bağlayıcısını yüklediyseniz ve ileride Exchange bağlantısını silerseniz, Şirket içi Exchange bağlayıcısını yüklü olduğu bilgisayardan kaldırmanız gerekir.

## <a name="install-connectors-for-multiple-exchange-organizations"></a>Birden çok Exchange kuruluşu için bağlayıcıları yükleme
Intune abonelik başına birden çok şirket içi Exchange bağlayıcısını destekler. Birden çok Exchange kuruluşu olan bir kiracı için, her Exchange kuruluşuna bir bağlayıcı ayarlayabilirsiniz. Bir kez .zip klasörünü indirin ve ardından her Exchange kuruluşu için önceki bölümde verilen adımları izleyerek kuruluştaki sunucuda kurulum programını ayıklayın ve çalıştırın.

Aşağıdaki bölümlerde açıklanan yüksek kullanılabilirlik, izleme ve el ile eşitleme özellikleri, Intune'a bağlanan her Exchange kuruluşu için desteklenir.

## <a name="on-premises-exchange-connector-high-availability-support"></a>Şirket içi Exchange bağlayıcısı yüksek kullanılabilirlik desteği 
Exchange bağlayıcısı belirtilen CAS'yi kullanarak Exchange bağlantısı oluşturduktan sonra, bağlayıcı diğer CAS'leri bulabilir. Birincil CAS kullanılamaz duruma gelirse, birincil CAS kullanılabilir duruma gelene kadar varsa bağlayıcı başka bir CAS'ye yük devreder. Bu özellik varsayılan olarak açıktır. Aşağıdaki yordamı kullanarak bu özelliği kapatabilirsiniz:
1. Exchange Connector'ın yüklü olduğu sunucuda %*ProgramData*%\Microsoft\Windows Intune Exchange Connector konumuna gidin. 
2. Bir metin düzenleyicisi kullanarak **OnPremisesExchangeConnectorServiceConfiguration.xml** dosyasını açın.
3. Özelliği devre dışı bırakmak için &lt;IsCasFailoverEnabled&gt;**true**&lt;/IsCasFailoverEnabled&gt; değerini &lt;IsCasFailoverEnabled&gt;**false**&lt;/IsCasFailoverEnabled&gt; olarak değiştirin.    


## <a name="monitor-the-exchange-connector-activity"></a>Exchange bağlayıcısı etkinliğini izleme

Exchange bağlayıcılarını başarıyla yapılandırdıktan sonra, bağlantıların durumunu ve son başarılı eşitleme girişimini görüntüleyebilirsiniz. Exchange bağlayıcısı bağlantılarını doğrulamak için:

1. Intune Panosu’nda, **Şirket içi erişim**’i seçin.
2. **Kurulum**'un altında **Exchange ActiveSync bağlayıcıları**'nı seçerek her Exchange bağlayıcısı için bağlantı durumunu doğrulayın.

Ayrıca son başarılı eşitleme denemesinin tarih ve saatini kontrol edebilirsiniz.

### <a name="system-center-operations-manager-scom-management-pack"></a>System Center Operations Manager (SCOM) yönetim paketi

Intune 1710 sürümünden itibaren [Exchange bağlayıcısı ve Intune için SCOM yönetim paketi](https://www.microsoft.com/download/details.aspx?id=55990&751be11f-ede8-5a0c-058c-2ee190a24fa6=True&e6b34bbe-475b-1abd-2c51-b5034bcdd6d2=True&fa43d42b-25b5-4a42-fe9b-1634f450f5ee=True) kullanabilirsiniz. Bu yönetim paketi, sorun gidermeniz gerektiğinde Exchange bağlayıcısını izlemek için size farklı yollar sunar.

## <a name="manually-force-a-quick-sync-or-full-sync"></a>Hızlı eşitlemeyi veya tam eşitlemeyi el ile zorlama
Şirket içi Exchange bağlayıcısı EAS ile Intune cihaz kayıtlarını düzenli aralıklarla eşitler. Cihazın uyumluluk durumu değişirse, otomatik eşitleme işlemi kayıtları düzenli aralıklarla eşitler. Bu şekilde, cihazın erişimi uygun şekilde engellenebilir veya erişimine izin verilebilir.

   - **Hızlı eşitleme** günde birkaç kez düzenli aralıklarla yapılır. Hızlı eşitleme, Intune lisanslı olan, şirket içi Exchange koşullu erişimi için hedeflenen ve son eşitlemeden sonra değiştirilmiş olan kullanıcıların cihaz bilgilerini alır.

   - **Tam eşitleme** varsayılan olarak günde bir kez gerçekleştirilir. Tam eşitleme, Intune lisanslı olan ve şirket içi Exchange koşullu erişimi için hedeflenen kullanıcıların cihaz bilgilerini alır. Tam eşitlemede Exchange sunucu bilgileri de alınır ve Azure portalında Intune tarafından belirtilen yapılandırmanın Exchange Server'da güncelleştirilmesi sağlanır. 

Intune panosundaki **Hızlı Eşitleme** veya **Tam Eşitleme** seçeneğini kullanarak bağlayıcıyı eşitleme çalıştırmaya zorlamak için aşağıdaki adımları izleyebilirsiniz:

   1. Intune panosunda **Şirket içi erişim**’i seçin.
   2. **Kurulum**'un altında **Exchange Active Sync Bağlayıcıları**'nı seçin.
   3. Eşitlemek istediğiniz bağlayıcıyı seçin ve sonra da **Hızlı Eşitleme**'yi veya **Tam Eşitleme**'yi seçin.

## <a name="next-steps"></a>Sonraki adımlar
[Şirket içi Exchange için koşullu erişim ilkesi oluşturma](conditional-access-exchange-create.md)
