---
# required metadata

title: Önceki sürümler | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 45dad14a-d412-488d-bb1e-ad990ea503df

# optional metadata

ROBOTS: noindex,nofollow
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Önceki Intune sürümleri

## Nisan 2016
Bu özelliklerin tümü, karma müşteriler için de desteklenmektedir (Intune ile tümleşik Configuration Manager).
### Uygulama yönetimi
- **MAM kullanıcı uyumu.**
Artık Azure Active Directory (AAD) kiracınızdaki herhangi bir kullanıcı için, uygulama yönetimi ilkelerinizin [durumunu](monitor-mobile-app-management-policies-with-Microsoft-Intune.md) görüntüleyebilirsiniz. Buna aşağıdakiler dahildir:
   - Cihazlar
   - Cihazdaki uygulamalar

   Durum değerleri:

   **İade**: İlkenin kullanıcıya dağıtıldığını ve uygulamanın iş bağlamında kullanıldığını ve ilkeyi başarıyla aldığını gösterir.

    **İade değil**: İlkenin kullanıcıya dağıtıldığını, ancak uygulamanın o zamandan bu yana iş bağlamında kullanılmadığını gösterir.


- **Outlook kişilerinin eşitlenmesini önlemek için MAM denetimleri (Android).**
Cihaz kaydı olmadan [mobil uygulama yönetimi](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) için yeni bir ayar vardır. Bu ayar, bir uygulamanın Android cihazlarda kişileri yerel adres defterine eşitlemesini engellemenizi sağlar. Bu ayar etkinleştirildiğinde, hedeflenen uygulamalar artık kişileri yerel adres defterine kaydedemeyecektir. Bu ayar devre dışı bırakıldığında, hedeflenen uygulamalar kişileri yerel adres defterine kaydedebilecektir. [Bir cihazı veya uygulamayı uzaktan temizlediğinizde](wipe-managed-company-app-data-with-Microsoft-Intune.md), yerel adres defterine zaten kaydedilmiş kişiler kaldırılacaktır. Bu yeni ayar başlangıçta Android cihazlarda Outlook uygulaması tarafından desteklenmektedir.

### Cihaz yönetimi
- **Şirkete ait cihazlar için telefon numarası kimliği.** “Şirket” olarak sınıflandırılmış telefonlar artık, örneğin bir mobil cihaz envanter raporu çalıştırdığınızda, tam telefon numaralarıyla tanımlanır. BYOD telefon numaraları, **** ile gizlenmeye devam edilecektir, yalnızca 4 hane görüntülenmektedir.


### Şirket portalı güncelleştirmeleri
**Android Şirket portalı uygulaması** Cihazlarını Intune’a kaydetmeyen ve doğru sertifika yüklememiş kullanıcılar, Android Şirket Portalı uygulamasına oturum açamaz ve "Cihazınızda gerekli bir sertifika eksik olduğundan oturum açılamıyor." iletisini görür. İleti, kullanıcıların sertifikayı yüklemek için yönergeleri görmek üzere dokunabileceği bir "Bu durum nasıl çözümlenir" bağlantısı içerir. Son kullanıcıların sorunu çözümlemek için izlediği adımları görmek için, bkz. [Cihazınızda gerekli bir sertifika eksik](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_cert_missing).

**iOS Şirket Portalı uygulaması** Listelenen uygulamalar, listelenen cihazlar ve BT iletişim bilgilerini içeren ana ekran içeriğini yenilemek üzere, çekerek yenileme eylemi için destek eklenmiştir. Çekerek yenileme eylemi, uyum veya ilk bilgilerini denetlemez, bu, geçerli cihazınız için döşeme seçilerek ve **Eşitle** düğmesine dokunularak yapılabilir.

**Windows 10 Mobile ve Windows Phone 8.1 Şirket Portalı uygulaması** Son kullanıcılar iş kolu uygulamaları yüklediğinde artık iyileştirilmiş bir uygulama yükleme deneyimi görecektir. Uygulama yüklemesi uzun sürüyorsa, kullanıcılar, eşitleme işleminin devam etmesini zorlamak için cihazlarını el ile eşitleyebilir. Son kullanıcı yönergelerini gözden geçirmek için, bkz. [Uygulama yüklemelerini hızlandırmak için cihazınızı el ile eşitleme](https://technet.microsoft.com/library/mt427782.aspx#BKMK_win10m_wp81_sync_manually).

**Şirket Portalı web sitesi** Windows 10 Mobile ve Windows Phone 8.1 kullanıcıları iş kolu uygulamaları yüklediğinde, artık yüklemelerinin durumu hakkında daha fazla ayrıntı sağlayan aşağıdaki yeni durumları görecektir:

* **Cihazın eşitlenmesi bekleniyor** – kullanıcı "Yükle" öğesine dokunmuştur ve cihaz şimdi Intune altyapısıyla eşitlemeye çalışıyordur. Yüklemenin tamamlanabilmesi için eşitleme gereklidir. "Cihazın eşitlenmesi bekleniyor" iletisi aynı zamanda bir bağlantıdır, kullanıcılar, eşitleme işlemi çok uzun sürüyorsa veya duruyorsa buna dokunarak cihazlarını Intune ile nasıl el ile eşitleyeceklerine dair [yönergeleri](https://technet.microsoft.com/library/mt590895.aspx#BKMK_iwp_sync_manually) görebilir.
* **İndiriliyor** – kullanıcının indirme isteği işlenmektedir ve cihaz uygulamayı indiriyor ve yüklüyordur.

Bu durumlar eklenmeden önce, bir uygulamanın yüklenmesi uzun sürdüğünde, yalnızca, ekranda saatlerce kalabilecek “Yükleniyor” durumu gördükleri için kullanıcıların kafası karışıyordu. Yeni durumların eklenmesi, destek çağırmak yerine, kullanıcıların artık “Cihazın eşitlenmesi bekleniyor" bağlantısına dokunabileceği ve eşitleme işleminin devam etmesini zorlamak için yönergeleri izleyebileceği anlamına geliyor.


## Mart 2016
### 29 Mart 2016 itibariyle yenilikler
Windows 10 genel yapılandırma ilkesine güncelleştirme hariç olmak üzere, 29 Mart 2016’da sunulan tüm özellikler, karma müşteriler için de desteklenmektedir (Intune ile tümleşik Configuration Manager). Windows 10 genel yapılandırma ilkesi güncelleştirmesi için karma desteği yakında geliyor. Bu özelliklerden bazılarının, Configuration Manager'ın en son sürümünü gerektiğini lütfen unutmayın.

### Uygulama yönetimi
- **Outlook kişilerinin eşitlenmesini önlemek için MAM denetimleri (iOS).** Cihaz kaydı olmadan mobil uygulama yönetimi için yeni bir ayar vardır. Bu ayar, bir uygulamanın iOS cihazlarda kişileri yerel adres defterine eşitlemesini engellemenizi sağlar. Bu ayar etkinleştirildiğinde, uygulama artık kişileri yerel adres defterine kaydedemeyecektir. Bu ayar devre dışı bırakıldığında, uygulama kişileri yerel adres defterine kaydedebilecektir. Bir cihazı seçmeli olarak temizlediğinizde, yerel adres defterine zaten kaydedilmiş tüm kişiler kaldırılacaktır. Bu yeni ayar, iOS cihazlarda Outlook uygulaması tarafından desteklenmektedir. Bu ve diğer ayarlar hakkında daha fazla ayrıntı için, bkz. [MAM ilkeleri oluşturma ve dağıtma](https://technet.microsoft.com/en-us/library/dn292747.aspx).

### Erişim denetimi
- **Skype Kurumsal Çevrimiçi Sürüm, koşullu erişimi destekler.** Skype Kurumsal Çevrimiçi Sürüm için, yalnızca yönetilen ve uyumlu iOS ve Android cihazları tarafından erişilebileceği şekilde, bir koşullu erişim ilkesi ayarlayabilirsiniz. iOS ve Android’de Skype Kurumsal Çevrimiçi mobil uygulamasında oturum açmaya çalışan son kullanıcılardan, oturum açma işlemini tamamlanabilmek için Intune’a kaydolmaları ve tüm uyumsuzluk sorunlarını çözmeleri istenecektir. Ayrıntılar için, bkz. [Skype Kurumsal Çevrimiçi Sürümüne erişimi yönetme](https://technet.microsoft.com/en-us/library/mt695297.aspx).

### Cihaz yönetimi
- **iOS 9.3 için Intune desteği.** 21 Mart Pazartesi günü Apple, iOS 9.3’ün kullanıma sunulduğunu duyurdu. Microsoft Intune’un, Apple'nın en son mobil işletim sistemi sürümü ile uyumlu olmasını sağlamak için çalışmalarımızı sürdürüyorduk ve [Intune’un 9.3 iOS cihazlarını yönetmeyi desteklediğini duyurmaktan memnuniyet duyuyoruz](https://blogs.technet.microsoft.com/microsoftintune/2016/03/23/microsoft-intune-provides-support-for-ios-9-3/).

  Kullanıcılar cihazlarını iOS 9.3 sürümüne yükselttiklerinde, şu anda iOS cihazlarını yönetmeye dair mevcut tüm Intune özellikleri sorunsuz bir şekilde çalışmaya devam edecektir. Ayrıca, iOS 9.3 bugün karma müşteriler için de desteklenmektedir (Intune ile tümleşik Configuration Manager).

- **Windows 10 genel yapılandırma ilkesi artık, kaydolmuş Windows 10 bilgisayarlarda Windows Defender’ı yönetmek için ayarlar içermektedir.** Ayrıntılar için, bkz. [Microsoft Intune’da Windows 10 yapılandırma ilkesi ayarları](https://technet.microsoft.com/en-us/library/mt404697.aspx).


### Şirket portalı

- **Windows uygulama paketleri doğrudan Şirket Portalı web sitesinden kullanılabilir.** Windows 8, Windows 8.1 ve Windows RT bilgisayarları artık Windows uygulama paketlerini (.appx uzantılı) doğrudan Şirket Portalı web sitesinden yükleyebilir. Daha önce, uygulamaları yüklemek için, Şirket Portalı uygulamasını dağıtmanız ya da kullanıcıların cihazlarına Şirket Portalı uygulamasını yüklemesi gerekiyordu.

- **Kullanıcıların, Şirket Portalı web sitesinden cihazlarını uzaktan kilitleyebilir.** Kullanıcıların, cihazları kaybolduğunda veya çalındığında cihazlarını Portal’dan uzaktan kilitlemesine olanak sağlamak için Şirket Portalı web sitesine yeni bir Uzaktan Kilitleme seçeneği eklenmiştir. Bkz. [son kullanıcı yönergeleri](https://technet.microsoft.com/library/mt590895.aspx/?wt.mc_id=ui#BKMK_iwp_remote_lock). Aşağıdaki tabloda, Intune Standalone ve Intune ile Configuration Manager için Uzaktan Kilitleme platform desteği listelenmektedir.

|Platform | Destek ayrıntıları|
|---------|----------------|
|Android |Desteklenir|
|iOS |Desteklenir|
|Windows 10 Mobile |Yalnızca telefonda bir parola grubu varsa desteklenir|
|Windows 10 Masaüstü |Desteklenmez|
|Windows Phone 8.1 |Yalnızca telefonda bir parola grubu varsa desteklenir|
|Windows Phone 8.0 |Desteklenmez|
|Bilgisayar (Windows 8.0 ve öncesi) |Desteklenmez|
|Bilgisayar (Windows 8.1) |Desteklenmez|

### 10 Mart 2016 itibariyle yenilikler

### Uygulama yönetimi

- **Üçüncü taraf bir MDM çözümüne kayıtlı cihazlar için iOS "Birlikte açma" yönetiminden yararlanın** iOS "Birlikte açma" yönetiminden yararlanmak için üçüncü taraf mobil cihaz yönetimi (MDM) satıcınızı kullanabilirsiniz. Yapılandırma profili ayarlarında kısıtlamalar belirleyebilir ve uygulamayı [iOS uygulamaları arasında veri aktarımını yönetme](manage-data-transfer-between-ios-apps-with-microsoft-intune.md) kullanarak dağıtabilirsiniz.

     Bu yaklaşımın iki ana faydası vardır:

     1. Kullanıcıların Bulut Hizmetleri veya diğer uygulamalardan herhangi bir kurumsal veriye erişebilmesi için iş hesaplarıyla oturum açması gerekir. Bunun yapılması, verilere erişildiğinde mobil uygulama yönetimi (MAM) ilkelerinin yerinde olmasını sağlar.

     2. Yönetilen e-posta profilleri ve bir üçüncü taraf MDM çözümü aracılığıyla dağıtılmış diğer yönetilen uygulamalar, Intune MAM ilkelerine sahip uygulamalarla dosya ve veri paylaşabilir.

- **Microsoft Outlook uygulamasını Intune'a kayıtlı olmayan cihazlar için MAM ilkeleriyle yönetin** Microsoft Outlook uygulamasını bundan böyle Intune’a kayıtlı olmayan cihazlarda Intune mobil uygulama yönetimi ilkesiyle yönetebilirsiniz. MAM özellikleriyle güncelleştirilmiş Microsoft Outlook uygulaması hem [iOS](https://itunes.apple.com/us/app/microsoft-outlook-email-calendar/id951937596?mt=8) hem de [Android](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook) cihazlarda kullanılabilir. Bir MAM ilkesi oluşturmak için [Mobil uygulama yönetimi ilkeleri oluşturma ve dağıtma](https://technet.microsoft.com/library/mt627829.aspx) konusundaki yönergeleri kullanın.  


- **Mobil uygulama yapılandırma ilkeleri, iOS uygulamalarına yönelik kullanıcı ayrıntılarını belirtmek için daha fazla esneklik sağlar** iOS uygulamasının açıldığında ihtiyaç duyabileceği kullanıcı ayarlarını sağlayabilirsiniz. Örneğin, bir ağ bağlantı noktası veya kullanıcı adı belirtebilirsiniz. Ayrıntılar için bkz. [iOS uygulamalarını Microsoft Intune’da mobil uygulama yapılandırma ilkeleriyle yapılandırma](configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune.md).


- **Microsoft Intune için Adobe Reader’ı kuruluşunuzda Intune ile yönetilen iOS cihazlarına dağıtın** iOS için Adobe Reader uygulaması artık Intune mobil uygulama yönetimi ilkesiyle kayıtlı cihazlar üzerinde yönetilebilir.

- **Dağıtılmış web kliplerinin yönetilen tarayıcıda açıldığından emin olun** Yalnızca iOS ve Android cihazlarda yönetilen tarayıcı kullanılarak açılabilen hedeflenen web kliplerini dağıtabilirsiniz. Örneğin, bağlantıları Şirket Portalı üzerinden şirket kaynaklarına dağıtırsınız ve kullanıcılar bağlantılara gittiğinde bağlantılar MAM ilkesi tarafından yönetilebildikleri yönetilen tarayıcıda doğrudan açılır. Ayrıntılar için bkz. [Uygulama dağıtma](deploy-apps.md).


- **Intune yönetici konsolundan Windows 10 cihazlara yönelik İş İçin Windows Mağazası uygulamalarını bulun, yönetin ve dağıtın** Intune’da uygulamaları bulmak, yönetmek ve yönettiğiniz Windows 10 cihazlara dağıtmak üzere İş İçin Windows Mağazası desteği sağlanır. İş İçin Windows Mağazası bu uygulamaları Intune yönetici konsolundan (diğer uygulamaları yönetmek için kullandığınız konsol) dağıtma ve izleme sürecini yönetmenize olanak sağlar. Özellikle, İş İçin Windows Mağazası “çevrimiçi lisanslı uygulamaların” içerik ve lisansını yönetir. Ayrıntılar için bkz. [İş için Windows Mağazası'ndan satın aldığınız uygulamaları yönetme](manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune.md).


### Cihaz yönetimi
- **iOS cihazları için PFX sertifikalarının dağıtımı** Intune yöneticileri iOS cihazlarda Wi-Fi, e-posta ve VPN kimlik doğrulamasına yönelik iOS PFX sertifikaları oluşturup dağıtabilir. Bu özellik Android ve Windows 10 cihazlarda zaten mevcuttur. Ayrıntılar için bkz. [Sertifika profillerini kullanarak şirket kaynaklarına erişimi etkinleştirme](secure-resource-access-with-certificate-profiles.md).


- **Uygulamaları ve ilkeleri kullanıcı kategorisi seçimine göre farklı cihaz gruplarına uygulayın** Intune administrators can now define custom device categories for users to select from during enrollment. Örneğin yöneticiler, kullanıcılarının "Yazar Kasa" veya "Dağıtım Kamyonu" ya da "Stok Odası" için kullanılan bir cihaz kaydettiğini belirtmesini isteyebilir. Seçilen kategori, cihazın kayıtlı cihaza farklı uygulamalar ve ilkeler dağıtmak için kullanılabilecek bir Intune cihaz grubunun üyesi olmasına neden olur. Ayrıntılar için bkz. [Cihazları cihaz grubu eşleme ile kategorilere ayırma](categorize-devices-with-device-group-mapping-in-microsoft-intune.md).

### Microsoft Şirket Portalı değişiklikleri ve güncelleştirmeleri
Bu sürümde, Şirket Portalı’nda aşağıdaki değişiklikler yapılmıştır.

**Android Şirket Portalı uygulaması**

* Kullanıcılarınız mobil uygulama yönetimi (MAM) tarafından yönetilen bir uygulama başlattığında, şirketi tarafından uygulamanın yönetildiğini bildiren bir ileti görürler. Kullanıcılar bundan böyle “Daha Fazla Bilgi” bağlantısına dokunarak “yönetilen uygulamaların” ne anlama geldiği hakkında buradan [daha fazla bilgi](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_use_mgd_apps) alabilirler. Ayrıca “Bir Daha Gösterme” seçeneğine dokunarak, uygulamayı başlattıklarında iletinin bir daha görüntülenmemesini sağlayabilirler.
* Kullanıcılara kayıt işleminde kılavuzluk eden, kullanıcıların neden kaydolması gerektiği ve BT yöneticilerinin kayıtlı cihazlarda neleri görebileceği ve göremeyeceği hakkında daha fazla bilgi veren yeni ekranlar eklenmiştir. Ayrıntılar için, [kayıt yönergelerine](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_enroll_devc) bakın.
* Kayıt hata iletileri artık Şirket Portalı uygulamasında görüntülenmektedir. Daha önce bu iletiler Şirket Portalı web sitesinde görüntüleniyordu. Bu değişikliğin yapılması tüm hata iletilerinin bundan böyle iki farklı yerde değil, tek bir yerde görüneceği anlamına gelmektedir.


**iOS Şirket Portalı uygulaması**
* Kullanıcılarınız mobil uygulama yönetimi (MAM) tarafından yönetilen bir uygulama başlattığında, şirketi tarafından uygulamanın yönetildiğini bildiren bir ileti görürler. Kullanıcılar bundan böyle “Daha Fazla Bilgi” bağlantısına dokunarak “yönetilen uygulamaların” ne anlama geldiği hakkında buradan [daha fazla bilgi](https://technet.microsoft.com/library/mt598622.aspx#BKMK_ios_use_mgd_apps) alabilirler. Ayrıca “Bir Daha Gösterme” seçeneğine dokunarak, uygulamayı başlattıklarında iletinin bir daha görüntülenmemesini sağlayabilirler.
* Kullanıcılara kayıt işleminde kılavuzluk eden, kullanıcıların neden kaydolması gerektiği ve BT yöneticilerinin kayıtlı cihazlarda neleri görebileceği ve göremeyeceği hakkında daha fazla bilgi veren yeni ekranlar eklenmiştir. Ayrıntılar için, [kayıt yönergelerine](https://technet.microsoft.com/library/mt598622.aspx#BKMK_enroll_ios_device) bakın.
* Kayıt hata iletileri artık Şirket Portalı uygulamasında görüntülenmektedir. Daha önce bu iletiler Şirket Portalı web sitesinde görüntüleniyordu. Bu değişikliğin yapılması tüm hata iletilerinin bundan böyle iki farklı yerde değil, tek bir yerde görüneceği anlamına gelmektedir.




## Şubat 2016
### Microsoft Şirket Portalı değişiklikleri ve güncelleştirmeleri

Bu sürümde, Şirket Portalı’nda aşağıdaki değişiklikler yapılmıştır.

#### Android Şirket Portalı uygulaması
- Kullanıcılara kayıt işleminde kılavuzluk eden, kullanıcıların neden kaydolması gerektiği ve BT yöneticilerinin kayıtlı cihazlarda neleri görebileceği ve göremeyeceği hakkında daha fazla bilgi veren yeni ekranlar eklenmiştir. Ayrıntılar için, [kayıt yönergelerine](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_enroll_devc) bakın.
- Kayıt hata iletileri artık Şirket Portalı uygulamasında görüntülenmektedir. Daha önce bu iletiler Şirket Portalı web sitesinde görüntüleniyordu. Bu değişikliğin yapılması tüm hata iletilerinin bundan böyle iki farklı yerde değil, tek bir yerde görüneceği anlamına gelmektedir.

#### iOS Şirket Portalı uygulaması
 - Kullanıcılara kayıt işleminde kılavuzluk eden, kullanıcıların neden kaydolması gerektiği ve BT yöneticilerinin kayıtlı cihazlarda neleri görebileceği ve göremeyeceği hakkında daha fazla bilgi veren yeni ekranlar eklenmiştir. Ayrıntılar için, [kayıt yönergelerine](https://technet.microsoft.com/library/mt598622.aspx#BKMK_enroll_ios_device) bakın.

 - Kayıt hata iletileri artık Şirket Portalı uygulamasında görüntülenmektedir. Daha önce bu iletiler Şirket Portalı web sitesinde görüntüleniyordu. Bu değişikliğin yapılması tüm hata iletilerinin bundan böyle iki farklı yerde değil, tek bir yerde görüneceği anlamına gelmektedir.


## Ocak 2016

### Windows 10 özelliklerinden yararlanın
* **Durum Kanıtlama Hizmeti ile koşullu erişim** Intune yöneticileri artık Intune Yönetici konsolunda Windows 10 Cihaz Durumu Kanıtlama durumunu görüntüleyebilir. Cihaz durumu kanıtlama, yöneticinin istemci bilgisayarlarda güvenilir BIOS, TPM ve önyükleme yazılımı yapılandırmaları olduğundan emin olmasına imkan tanır. Cihaz durumu kanıtlamayı desteklemek için istemci cihazların TPM 2 etkinken Windows 10 çalıştırıyor olması gerekir. Cihaz durumu kanıtlama aşağıdakilerin her biri için etkinleştirilmiş cihaz sayısını görüntüler:
    * Erken başlatılan kötü amaçlı yazılımdan koruma
    * BitLocker
    * Güvenli Önyükleme
    * Kod Bütünlüğü

    Cihaz durumu ayarı, toplanan veri noktaları ve durum kanıtlama rapor hakkında daha fazla bilgi için bkz. [Microsoft Intune için cihaz uyumluluk ilkelerine giriş](introduction-to-device-compliance-policies-in-microsoft-intune.md). [HAS hizmet ayrıntıları](https://msdn.microsoft.com/en-us/library/dn934876.aspx), hizmeti kapsamlı olarak açıklar.

* **Windows 10 İş için Passport İlkesi ve sertifika yönetimi** Intune ile, bir parola, akıllı kart ya da sanal akıllı kartı değiştirmek için Windows 10’da Active Directory’yi veya bir Azure Active Directory hesabını kullanan alternatif oturum açma yöntemi [İş İçin Microsoft Passport’u tümleştirebilirsiniz](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md). Passport oturum açmak için parola yerine kullanıcı hareketi kullanmanıza imkan tanır. Kullanıcı hareketi basit bir PIN, Windows Hello gibi bir biyometrik kimlik doğrulaması ya da parmak izi okuyucu gibi harici bir cihaz olabilir.

* **Belirli uygulamalar için VPN** VPN üzerinden şirket ağınıza otomatik olarak bağlanan uygulamaları seçebilirsiniz. VPN profilini ayarlarken, Kullanıcıların Microsoft Intune ile VPN profilleri kullanarak bağlanmasına yardımcı olun bölümünde anlatıldığı gibi uygulama listesi oluşturun.

* **Windows 10 Tam Silme desteği** Intune yönetici konsolu ile Intune’a kaydedilmiş Windows 10 masaüstü cihazlarına artık uzaktan tam silme uygulayabilirsiniz. Windows 10 tam silme, cihazı fabrika ayarlarına sıfırlar.


### Apple Toplu Satın Alma Programı (VPP) güncelleştirmesi
Intune bundan böyle [İş için Apple Toplu Satın Alma Programı (VPP) ile satın aldığınız uygulamaları yönetmenize](manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune.md) yardımcı olabilir. Buna lisans bilgilerinin Apple ile Intune arasında eşitlenmesi ve her bir uygulamanın kaç tane kopyasını dağıttığınızı izlemeyi içerir.

### Şirkete ait cihazları tanımlamak için IMEI numaralarını kullanın
Bundan böyle şirkete ait mobil cihazları tanımlamaya yardımcı olmak üzere bir IMEI numarasına sahip mobil cihaz platformları için [uluslararası mobil donanım kimliği (IMEI) numaralarını](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md) içeri aktarabilirsiniz. Intune’a kaydedildikten sonra, içeri aktarılan IMEI numaralarına sahip cihazlar kişiye ait cihazlara uygulananlardan farklı ilkeleri uygulamak için kullanılabilecek Şirket cihazları olarak etiketlenir.

### Intune MAM ilkeleriyle artık daha fazla uygulama uyumludur
Artık Microsoft iş ortaklarının daha fazla uygulaması Intune mobil uygulama yönetimi (MAM) ilkeleriyle uyumludur (Intune tarafından yönetilen cihazlar için):
* Box for EMM (Box Inc) – yalnızca iOS
* Adobe Reader (Adobe) – yalnızca Android
* Foxit PDF Reader (Foxit Corporation) – iOS ve Android


### IE9 desteği Ocak’ta sona erecektir
Internet Explorer 9, Şubat 2016 tarihinden itibaren Microsoft Intune şirket portalı web sitesine, Intune hesabı portalına ve Intune yönetim konsoluna erişim için resmi bir tarayıcı olarak desteklenmeyecektir. Internet Explorer 10 veya sonraki bir sürüme geçiş yapmanız gerekecektir.

## Aralık 2015
### Microsoft Şirket Portalı değişiklikleri ve güncelleştirmeleri
Bu sürümde, Şirket Portalı’nda aşağıdaki değişiklikler yapılmıştır.

**Android Şirket Portalı uygulaması**

Yeni Google gereksinimlerine uyum sağlamak için aşağıdaki değişiklikler yapılmıştır. Android 6.0 ve üstü cihazlarda kullanıcılara iki yeni ileti görüntülenir:
* Şirket Portalı’nın telefon çağrıları yapmasına ve çağrıları yönetmesine izin verilsin mi?
* Şirket Portalı’nın cihazınızdaki fotoğraflara, medyaya ve dosyalara erişmesine izin verilsin mi?

Bu iki iletiyle ilgili ayrıntılı bilgi için aşağıdaki tablolara bakın.



İleti metni  |Şirket Portalı’nın telefon çağrıları yapmasına ve çağrıları yönetmesine izin verilsin mi?  
---------|---------
İleti açıklaması     |  Kullanıcının cihaz telefon numarası ile IMEI numarasının Intune hizmetine gönderilmesini ve Donanım sayfasındaki Yönetim konsolunda görüntülenmesini sağlar.   </br></br>**NOT: Şirket Portalı uygulaması hiçbir zaman telefon çağrıları yapmaz veya çağrıları yönetmez!** İleti metni Google tarafından denetlenir ve değiştirilemez. </br></br>**Donanım** sayfasını görmek için, **Gruplar** > **Tüm mobil cihazlar** > **Cihazlar**’a gidin. Kullanıcının cihazını seçin ve **Özellikleri Görüntüle** > **Donanım**’a gidin.    
İletinin nerede ve ne zaman görüneceği  | İleti, kullanıcılar cihazlarını kaydetmeye başlamak için Şirket Portalı uygulamasında ilk kez oturum açtığında görüntülenir.|         
Kullanıcılar erişime izin verirse ne olur  |  Cihazın telefon numarası ile IMEI numarası, Yönetim konsolundaki Donanım sayfasında görüntülenir. |         
Kullanıcılar erişimi reddederse ne olur     | Şirket Portalı uygulamasını kullanmaya ve cihazlarını kaydetmeye devam edebilirler, ancak Yönetim konsolundaki Donanım sayfasında kullanıcı cihazının telefon numarası ile IMEI numarası boş olarak görüntülenir.       </br></br> Kullanıcılar, erişimi reddettikten sonra Şirket Portalı uygulamasında ikinci kez oturum açtığında, kullanıcıların iletinin bir daha görüntülenmemesini seçebilmesi için **Bir daha sorma** onay kutusu görüntülenir.</br></br>Kullanıcılar erişime izin verip daha sonra erişimi reddederse ileti, kullanıcılar kayıt işleminin ardından Şirket Portalı uygulamasında bir sonraki sefer oturum açtığında görüntülenir.</br></br>Kullanıcılar daha sonra erişime izin vermeye karar verirse, **Ayarlar** > **Uygulamalar** > **Şirket Portalı** > **İzinler** > **Telefon**’a gidebilir ve ardından izni etkinleştirebilirler.
Daha fazla bilgi     |  Kullanıcılarınız için: [Şirket Portalı’nda oturum açma](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_signin_cp)  </br></br>BT Uzmanları için: Bu tablodaki bilgilere [Kullanıcılarınızın Şirket Portalı uygulaması iletilerini anlamalarına yardımcı olma](https://technet.microsoft.com/library/dn948527.aspx#BKMK_help_users_understd_msgs) bölümünden de erişilebilir   

İleti metni  |Şirket Portalı’nın cihazınızdaki fotoğraflara, medyaya ve dosyalara erişmesine izin verilsin mi?  
---------|---------
İleti açıklaması     |  Cihazın, veri günlüklerini cihazdaki SD kartına yazmasını sağlar ve böylece günlüklerin bir USB kablosu aracılığıyla taşınmasına olanak tanır.   </br></br>**NOT: Şirket Portalı uygulaması hiçbir zaman kullanıcının fotoğraflarına, medyasına ve dosyalarına erişmez!** İleti metni Google tarafından denetlenir ve değiştirilemez.     
İletinin nerede ve ne zaman görüneceği  | İleti, kullanıcılar veri günlüklerini BT yöneticilerine göndermek üzere **Veri Gönder** seçeneğine dokunduğunda görüntülenir.|         
Kullanıcılar erişime izin verirse ne olur  |  Günlükler SD karta kopyalanır. |         
Kullanıcılar erişimi reddederse ne olur     | Kullanıcılar veri günlüklerini göndermeye devam edebilir, ancak günlükler cihazın SD kartına kopyalanmaz.       </br></br> Kullanıcılar, erişimi reddettikten sonra Şirket Portalı uygulamasında ikinci kez oturum açtığında, kullanıcıların iletinin bir daha görüntülenmemesini seçebilmesi için **Bir daha sorma** onay kutusu görüntülenir.</br></br>Kullanıcılar erişime izin verip daha sonra erişimi reddederse ileti, kullanıcılar günlükleri tekrar göndermeye çalıştığında görüntülenir.</br></br>Kullanıcılar daha sonra erişime izin vermeye karar verirse, **Ayarlar** > **Uygulamalar** > **Şirket Portalı** > **İzinler** > **Mağaza**’ya gidebilir ve ardından izni etkinleştirebilirler.
Daha fazla bilgi     |  Kullanıcılarınız için: [Tanılama veri günlüklerini e-posta aracılığıyla BT yöneticinize gönderme](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_send_diag_logs)  </br></br>BT Uzmanları için: Bu tablodaki bilgilere [Kullanıcılarınızın Şirket Portalı uygulaması iletilerini anlamalarına yardımcı olma](https://technet.microsoft.com/library/dn948527.aspx#BKMK_help_users_understd_msgs) bölümünden de erişilebilir   


**iOS Şirket Portalı uygulaması**
* Kullanıcılar, tanılama günlüklerini BT yöneticisine göndermek için artık Microsoft Outlook’u veya diğer e-posta uygulamalarını kullanabilir. Daha önce bunun için yalnızca yerel uygulama kullanılabiliyordu.
* Apple’ın Aygıt Kayıt Programı (DEP) ve kurumsal olarak kaydedilen cihazlar için sunulan destek geliştirilmiştir. Ayrıntılar için bkz. [Kaydetmeye çalışırken cihazınızı tanımlamanız isteniyor](https://technet.microsoft.com/library/mt598622.aspx#BKMK_ios_id_your_device).
* Kullanıcıya ait kayıtlı cihazlar listesinde, kullanıcının şu anda kullanmakta olduğu cihazın yanında yeşil bir onay işareti görüntülenir. Bu onay işareti eklenmeden önce kullanıcılar, kullanmakta oldukları kayıtlı cihazı görme olanağına sahip değildi.

**Windows Şirket Portalı uygulaması**

Microsoft, ürün ve hizmetlerini geliştirmek için şirket portalının performansı ve kullanımı hakkında anonim bilgileri otomatik olarak toplar. Son kullanıcılar cihazlarının Kullanım Verileri ayarını kullanarak veri toplamayı devre dışı bırakabilir, ancak yöneticilerin veri toplama üzerinde hiçbir denetimi yoktur ve son kullanıcının bu ayar ile ilgili seçimini değiştiremezler.



## Kasım 2015
### Uygulama yönetimi
Intune, şirket verilerinin tüketici uygulamalarına veya hizmetlerine sızmasını önlemeye yardımcı olan mobil uygulama yönetimi (MAM) ilkelerini destekler. Tarihsel olarak, bu ilkeler yalnızca mobil cihaz yönetimi (MDM) için Intune’a da kaydedilmiş cihazlarda çalışan mobil uygulamalar üzerinde uygulanabiliyordu.

Bu ayın güncelleştirmesiyle Intune, MAM yeteneklerini yeni cihaz sınıflarına genişletmektedir. MAM ilkelerini Intune'a kayıtlı cihazlara ek olarak bundan böyle aşağıdakilere uygulayabilirsiniz:
* başka bir mobil cihaz yönetimi (MDM) çözümü tarafından yönetilen cihazlar
* herhangi bir cihaz yönetimi sistemine kayıtlı olmayan cihazlar, genellikle kendi cihazını getir (BYO)

Bu yeni MAM özellikleri hakkında daha fazla bilgiyi aşağıdaki blog gönderilerinde bulabilirsiniz:
* [Yönetilen mobil üretkenliği geliştirme](http://blogs.technet.com/b/microsoftintune/archive/2015/11/17/enhancing-managed-mobile-productivity.aspx)
* [Yeni Microsoft Enterprise Mobility özellikleriyle tanışın](http://blogs.technet.com/b/microsoftintune/archive/2015/11/17/enhancing-managed-mobile-productivity.aspx)

Ayrıca, Intune'un MAM özellikleri hakkında öne çıkan bazı noktalar ve ek bilgiler şunlardır:
* Şirket verileri Office Mobile uygulamaları, Intune SDK’sını benimseyen üçüncü taraf uygulamalar veya Intune tarafından sarmalanan iş kolu uygulamaları dahil olmak üzere Intune için tanıtılan uygulamaların içindeki tüketici verilerinden ayrı tutulur.
* Şirket verileri şirket uygulamalarında paylaşılabilirken (**kes/kopyala/yapıştır**), kişisel uygulamalarla paylaşılması engellenir. Daha fazla bilgi için bkz. [MAM ilkeleri uygulama verilerini nasıl korur](https://technet.microsoft.com/library/mt627825.aspx). [İş amaçlı ve kişisel görevler için Microsoft Word uygulamasını kullanma](https://technet.microsoft.com/library/mt627827.aspx) adlı bu örnek senaryo, şirket verilerinin kişisel uygulamalarla paylaşılmasının nasıl önlendiğini göstermektedir.
* Uygulama Başına PIN, farklı kaydetme denetimleri ve uygulamalar arasında yönetilen veri paylaşımı gibi temel veri kaybı önleme ilkeleri. Tüm ilkelerin listesi için bkz. [Microsoft Intune ile mobil uygulama yönetimi ilkeleri oluşturma ve dağıtma](https://technet.microsoft.com/library/mt627829.aspx).
* Word, Excel, PowerPoint, Outlook, OneNote ve OneDrive İş uygulamalarının hepsi bu yeni özelliklere sahiptir ve cihaz kaydı ile birlikte ya da cihaz kaydı olmadan yönetilebilir. Veri kaybı önleme özellikleri Apple Store veya Google Play mağazasındaki standart Office uygulamalarına yerel olarak yerleştirilmiştir ve uygulama sarmalama ya da dışarıdan yükleme gerektirmez.
* Nasıl başlayacağınızı öğrenmek için bkz. [Azure portalında mobil uygulama yönetimi ilkelerini kullanmaya başlama](https://technet.microsoft.com/library/mt627830.aspx). Mobil uygulama yönetimi ilkelerini yapılandırma ve dağıtma hakkında bilgi almak için bkz. [Microsoft Intune ile mobil uygulama yönetimi ilkeleri oluşturma ve dağıtma](https://technet.microsoft.com/library/mt627829.aspx).
* Son kullanıcılar uygulamada şirket bilgileriyle kimlik doğrulaması yaptıklarında veri kaybı koruma özellikleri otomatik olarak ayarlanır. [Microsoft Intune mobil uygulama yönetimi ilkeleri ile ilişkili uygulamalar için son kullanıcı deneyimi](https://technet.microsoft.com/library/mt627827.aspx) konusunda iOS ve Android cihazlarında OneDrive erişimine ilişkin bazı örnek senaryolar verilmiştir.
* iOS ve Android cihazlar üzerinde çalışır.

[Microsoft Intune mobil uygulama yönetimi ilkeleri ile birlikte kullanabileceğiniz Microsoft uygulamaları](https://technet.microsoft.com/library/dn708489.aspx) listesi en son uygulamaları gösterecek şekilde güncelleştirilmiştir.

### Cihaz yönetimi
 **Mac OS X cihaz yönetimi** Intune ile bundan böyle Mac OS X cihazlarını kaydedip yönetebilirsiniz. Mac OS X cihazlarınız ile aşağıdakileri yapabilirsiniz:
* Intune tarafından yönetilecek cihazları kaydetme. Bkz. [Microsoft Intune ile iOS ve Mac yönetimini ayarlama](https://technet.microsoft.com/library/dn408185.aspx).
* Genel bir yapılandırma ilkesi ile cihaz ayarlarını denetleme. Bkz. [Microsoft Intune’da Mac OS X yapılandırma ilkesi ayarları](https://technet.microsoft.com/library/mt627823.aspx).
* Apple Configurator ile oluşturduğunuz Mac OS X ayarlarını dağıtma. Bkz. [Microsoft Intune’da Mac OS X özel ilke ayarları](https://technet.microsoft.com/library/mt627820.aspx).
* Mac OS X cihazlarından donanım ve yazılım envanteri toplama. Bkz. [Microsoft Intune’da envanterle cihazlarınızı anlama](https://technet.microsoft.com/library/jj733634.aspx).
* Yönettiğiniz Mac OS X cihazlarıyla ilgili ayrıntıları gösteren yeni raporlar çalıştırma. Bkz. [Raporları kullanarak Microsoft Intune işlemlerini anlayın](https://technet.microsoft.com/library/dn646977.aspx).

**Windows 10 cihazları için yeni Edge tarayıcı ayarları** Microsoft Edge tarayıcısının ayarlarını ve özelliklerini yönetmenize olanak sağlayan Windows 10 genel yapılandırma ilkesine yeni ayarlar eklenmiştir. Bkz. [Microsoft Intune’da Windows 10 yapılandırma ilkesi ayarları](https://technet.microsoft.com/library/mt404697.aspx).

**E-posta profilleri** Windows 10 masaüstü ve Windows 10 mobil cihazlar için yeni bir e-posta profilleri ilkesi eklenmiştir. Bkz. [Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](https://technet.microsoft.com/library/dn646984.aspx).

**Yeni uyumluluk ilkesi ayarları** Uyumluluk ilkeleri listesine aşağıdaki yeni güvenlik ve sistem ilkesi ayarları eklenmiştir:
* Şirket kaynaklarınıza erişen Windows 8.1 veya üzeri cihazlarda en son güncelleştirmelerin yüklü olduğundan emin olmak için **Otomatik güncelleştirmeleri zorunlu kıl** ayarını kullanın. Ayrıca otomatik olarak yüklenecek güncelleştirmelerin türünü belirtebilirsiniz; tüm güncelleştirmeler yüklenmek üzere önemli olarak işaretlenebilir veya tüm güncelleştirmeler önemli ya da önerilen olarak işaretlenir. Uyumluluk ilkesi ayarlarının tam listesi için bkz. [Microsoft Intune için cihaz uyumluluk ilkelerini yönetme](https://technet.microsoft.com/library/dn705843.aspx).
* Yeni **Cihaz boşta durumundan çıktığında parola gerektir** ayarı ile birlikte var olan **Parola istenmeden önce geçen işlem yapılmayan dakika sayısı** ayarı, son kullanıcının belirli bir süredir etkin olmayan bir cihazı kullanmak üzere parola girmesini gerektiren bir uyumluluk ayarı oluşturmanıza imkan tanır.

**Yeni koşullu erişim ilkesi seçenekleri** Koşullu erişim ilkelerini yeni veya var olan koşullu erişim ilkelerindeki **tüm kullanıcılara** uygulayabilirsiniz. Intune ve Office 365 lisansına sahip tüm kullanıcıların cihazlarını kaydetmesi gerekir ve cihaz platformu Intune tarafından desteklenmiyorsa [Active Directory kimlik doğrulama tabanlı oturum açma (modern kimlik doğrulaması)](https://blogs.office.com/2014/11/12/office-2013-updated-authentication-enabling-multi-factor-authentication-saml-identity-providers/) kullanan istemci uygulamalar için erişim engellenir.

Koşullu erişim ilkesinin **tüm platformlar** geçerli olduğunu da belirtebilirsiniz.  [Active Directory kimlik doğrulama tabanlı oturum açma (modern kimlik doğrulaması)](https://blogs.office.com/2014/11/12/office-2013-updated-authentication-enabling-multi-factor-authentication-saml-identity-providers/) kullanan tüm istemci uygulamalar koşullu erişim ilkesine tabidir ve platform Intune tarafından desteklenmiyorsa engellenir.

### Microsoft Şirket Portalı değişiklikleri ve güncelleştirmeleri
Bu sürümde şirket portalı uygulamalarında aşağıdaki değişiklikler yapılmıştır:

* **Android**: Android Şirket Portalı uygulamasına, kullanıcıların Şirket Portalı uygulamasının amacını anlamasına yardımcı olmak üzere bir Hoş Geldiniz ekranı eklenmiştir. Bu ekran, şirketleri Intune abonesi olmayan kullanıcılar tarafından uygulamanın indirilmesini azaltmaya yöneliktir.

* **iOS**: Intune artık kullanarak Mac OS X cihazlarının destekler [Şirket portalı Web sitesini](https://portal.manage.microsoft.com). Yönergeler için bkz. [Mac OS X cihazınızı Intune’a kaydetme](https://technet.microsoft.com/library/mt598622.aspx).

* **Şirket Portalı web sitesi**: Cihazlarını Intune’a kaydeden kullanıcılar artık, Şirket Portalı web sitesindeki **Geçiş Kodunu Sıfırlama** seçeneğini kullanarak geçiş kodlarını sıfırlayabilir. Kullanıcıların geçiş kodları, daha önce yalnızca BT yöneticileri tarafından sıfırlanabiliyordu. Geçiş Kodunu Sıfırlama seçeneği Windows 8.1 ve Windows RT cihazlarında desteklenmez ve seçenek, yalnızca cihazların mobil cihaz yönetimine (MDM) veya Exchange ActiveSync içeren MDM’ye kayıtlı olması durumunda görüntülenir.Geçiş Kodunu Sıfırlama seçeneği Windows 8.1 ve Windows RT cihazlarında desteklenmez ve seçenek, yalnızca cihazların mobil cihaz yönetimine (MDM) veya Exchange ActiveSync içeren MDM’ye kayıtlı olması durumunda görüntülenir. Kullanıcı yönergeleri için bkz. [Geçiş kodunuzu sıfırlama](https://technet.microsoft.com/library/mt590895.aspx).

### Genel Yönetici lisansındaki değişiklikler
Ekim ayında Genel Yöneticilerin (Kiracı Yöneticiler olarak da bilinir) ayrı bir Intune veya Enterprise Mobility Suite (EMS) lisansı olmadan günlük yönetim görevlerine devam edebileceği paylaşılmıştı. Ancak, Genel Yöneticiler kendi cihazlarını veya bir şirket cihazını kaydetme gibi amaçlarla hizmeti kullanmak ya da Intune Şirket Portalı’nı kullanmak isterse diğer tüm kullanıcılar gibi bir Intune veya EMS lisansına ihtiyaç duyacaklardır. Birkaç ek ayrıntı aşağıda verilmiştir.
* Intune Şirket Portalı’nda son kullanıcılar şunları yapabilir:
    * cihazlarını kaydetme
    * cihazlarının durumunu görüntüleme
    * bir Genel Yöneticinin kuruluşa dağıttığı yazılımları indirme
    * Genel Yönetici tarafından BT departmanına nasıl başvurulacağıyla ilgili yayımlanan bağlantıları bulma

    [Şirket Portalı hakkında bilgi edinme](https://technet.microsoft.com/library/dn646966.aspx#BKMK_CompanyPortal) ve [Şirket Portalı’nı özelleştirme yolları](https://technet.microsoft.com/library/dn646983.aspx#BKMK_ConfigureCompanyPortal) hakkında.
* Bir kuruluş adına Intune veya EMS satın almak üzere kaydolan kişi otomatik olarak kiracısındaki ilk Genel Yönetici olur. Bu sonbaharda Intune, [Office 365 Portalı](http://portal.office.com/)’na geçiş ve [Intune Hesap Portalı](http://account.manage.microsoft.com/)’nın kullanımdan kaldırılmasının bir parçası olarak bu ilk Genel Yönetici’ye bir Intune veya EMS lisansını otomatik olarak atamaya başlamıştır. Eklenen diğer tüm Genel Yöneticiler ayrı bir Intune veya EMS lisansı olmadan günlük yönetim görevlerini gerçekleştirmeye devam edebilir. Son kullanıcı olarak hareket edilmesi ve kendi (ya da şirket) cihazının kaydedilmesi veya şirket portalından yazılım indirilmesi ise diğer tüm kullanıcılarda olduğu gibi bir lisans ihtiyacı doğurur.
* Değişiklik aşamalı olacak ve Ocak 2016'da başlayacaktır.
* Microsoft İş Ortakları için bu değişiklik müşteriler adına hizmeti yönetme özelliğini etkilemeyecektir. Son kullanıcı görevlerinde bir kullanıcının bir cihazı kaydetmesi ve Şirket Portalı’na erişip buradan yazılım indirmesi için Intune veya EMS lisansına sahip olması gerekir.

Bu değişiklik hakkında sorularınız varsa Intune destek ekibinize başvurmaktan çekinmeyin:
* [Microsoft Intune destek kanalları](https://technet.microsoft.com/library/jj839713.aspx)
* [Topluluk desteği](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod)

Tasarım Değişikliği İstekleri (DCR) veya hatalar dahil olmak üzere Microsoft Intune ile ilgili genel görüşler için [Intune kullanıcı sesi](https://microsoftintune.uservoice.com/) sayfasını ziyaret edin.


### Intune belgelerindeki yenilikler -- Kasım 2015
**Yeni içerik**
* [Microsoft Intune’da Mac OS X yapılandırma ilkesi ayarları](https://technet.microsoft.com/library/mt627823.aspx): Mac OS X cihazlarının ayarlarını ve özelliklerini denetleme.
* [Microsoft Intune’da Mac OS X özel ilke ayarları](https://technet.microsoft.com/library/mt627820.aspx): Apple Configurator aracını kullanarak oluşturduğunuz Mac OS X cihaz ayarlarını dağıtma.
* [Microsoft Intune ile veri kaybı önleme uygulama ilkelerini yapılandırma](https://technet.microsoft.com/library/mt627825.aspx): Mobil uygulama yönetimi ilkelerinin desteklediği senaryolar ve ilkenin verileri korumak için nasıl çalıştığı hakkında bilgi içerir.
* [Azure portalında mobil uygulama yönetimi ilkelerini kullanmaya başlama](https://technet.microsoft.com/library/mt627830.aspx): Mobil uygulama yönetimi ilkeleri için Azure önizleme portalını kullanmaya başlamaya yönelik gereksinimler.
* [Microsoft Intune ile mobil uygulama yönetimi ilkeleri oluşturma ve dağıtma](https://technet.microsoft.com/library/mt627829.aspx): Azure önizleme portalında mobil uygulama yönetimi ilkelerinin nasıl oluşturulacağıyla ilgili bir adım adım kılavuz içerir.
* [Microsoft Intune ile mobil uygulama yönetimi ilkelerini izleme](https://technet.microsoft.com/library/mt627824.aspx): Azure önizleme portalını kullanarak mobil uygulama yönetimi ilkelerinizi nasıl izleyebileceğinize ilişkin bilgiler.
* [Microsoft Intune mobil uygulama yönetimi ilkeleri ve iOS Birlikte Açma](https://technet.microsoft.com/library/mt627821.aspx): Mobil uygulama yönetimi ilkelerinin iOS Birlikte Açma özelliğiyle nasıl çalıştığına yönelik bilgiler.
* [Microsoft Intune mobil uygulama yönetimi ilkeleri ile ilişkili uygulamalar için son kullanıcı deneyimi](https://technet.microsoft.com/library/mt627827.aspx): Mobil uygulama yönetimi ilkesiyle ilişkili uygulamalar kullanılırken son kullanıcı deneyiminin nasıl olduğu.
* [Microsoft Intune ile yönetilen şirket uygulama verilerini silme](https://technet.microsoft.com/library/mt627826.aspx): Şirket uygulama verilerini nasıl kaldırabileceğiniz.

**Güncelleştirilmiş içerik**
* [Microsoft Intune’da Windows 10 yapılandırma ilkesi ayarları](https://technet.microsoft.com/library/mt404697.aspx): Yeni Edge tarayıcısı ayarları eklendi.
* [Microsoft Intune ile iOS ve Mac yönetimini ayarlama](http://technet.microsoft.com/library/dn408185.aspx): Mac OS X cihazlarının nasıl kaydedileceği hakkında bilgiler eklendi.
* [Microsoft Intune’da envanterle cihazlarınızı anlama](https://technet.microsoft.com/library/jj733634.aspx): Mac OS X cihazlarından toplanan envanter hakkında bilgiler eklendi. Ayrıca, tüm cihaz platformları için en son bilgilerle konu güncelleştirildi.
* [Raporları kullanarak Microsoft Intune işlemlerini anlayın](https://technet.microsoft.com/library/dn646977.aspx): Yönetilen Mac OS X cihazlarınızla ilgili bilgileri görüntülemek için kullanılan iki yeni rapor hakkında bilgiler eklendi.
* [Microsoft Intune için cihaz uyumluluk ilkelerini yönetme](https://technet.microsoft.com/library/dn705843.aspx): Otomatik güncelleştirmeleri zorunlu kılma ve bir cihaz boşta durumundan döndüğünde parola gerektirme için yeni uyumluluk ilkeleri hakkında bilgiler eklendi.
* [Microsoft Intune ile e-posta erişimini yönetme](https://technet.microsoft.com/library/dn705841.aspx): Koşullu erişimi tüm platformlara ve tüm kullanıcılara uygulama özelliği hakkında bilgiler eklendi.
* [Microsoft Intune ile SharePoint Online erişimini yönetme](https://technet.microsoft.com/library/dn705844.aspx): Koşullu erişimi tüm platformlara ve tüm kullanıcılara uygulama özelliği hakkında bilgiler eklendi.

## Ekim 2015

### Exchange şirket içi koşullu erişimi güncelleştirmeleri
**Genel Exchange kuralı engelleme veya karantinaya alma şeklinde ayarlandığında Intune’a kayıtlı uyumlu cihazlar için Exchange Active Sync e-postasına artık erişebilirsiniz** Bundan önce, kayıtlı ve uyumlu cihazlarda e-posta erişimine izin vermek için varsayılan genel Exchange kuralını **İzin Ver** olarak ayarlamanız gerekiyordu.

Bu hizmet güncelleştirmesiyle, koşullu erişim için artık bu ayar gerekli değildir. Exchange ortamınız varsayılan genel kuralınızın **Engelle/Karantinaya Al** olarak ayarlanmasını gerektiriyorsa, Exchange şirket içi koşullu erişim ilkesi sayfasında **Varsayılan Kuralı Geçersiz Kıl** onay kutusunu işaretlemeniz yeterli olur. [Microsoft Intune ile e-posta erişimini yönetme](https://technet.microsoft.com/library/dn705841.aspx) konu başlığı altında, kurallar ve bunlardan kaynaklanan son kullanıcı bildirimleriyle ilgili daha ayrıntılı bilgi bulabilirsiniz.

**Yeni tek tıklamalı karantina deneyimi** Tek tıklamayla kayıt olanağı sağlamak için, karantina e-postası deneyimini basitleştirdik. Bu hizmet güncelleştirmesiyle, son kullanıcılar karantina e-postasında tek bir bağlantıya tıklayarak Şirket Portalı uygulamasında kayıt işlemini tamamlayabilecek.
### Mobil cihaz ve uygulama yönetimi güncelleştirmeleri
**Android** Artık tüm Intune yönetim özellikleri bu blog gönderisinde açıklandığı gibi Android 6.0’ı (Marshmallow) desteklemektedir: [Microsoft Intune Android Marshmallow için 0. Gün Desteği Sağlıyor](http://blogs.technet.com/b/microsoftintune/archive/2015/10/09/microsoft-intune-to-provide-day-0-support-for-android-marshmallow.aspx).

**iOS** Bundan böyle iOS 7.1’den önceki sürümleri çalıştıran iOS cihazlarında yeni uygulama dağıtımları oluşturamazsınız. iOS 7.1’den önceki sürümleri çalıştıran cihazlara yönelik var olan tüm uygulama dağıtımları çalışmaya ve Intune tarafından yönetilmeye devam edecektir.

**Windows 10**, **Windows uygulama paketi** bundan böyle yazılım yükleyici türünü kullanarak Windows 10 Universal uygulamalarının dağıtımını desteklemektedir. Ayrıntılar ve gereksinimler için bkz. [Microsoft Intune'da uygulama dağıtımına başlayın](http://technet.microsoft.com/en-US/library/dn646955.aspx).


### Microsoft Şirket Portalı uygulamalarındaki değişiklikler ve güncelleştirmeler
Bu sürümde şirket portalı uygulamalarında şu değişiklikler yapılmıştır: **iOS** Kullanıcıların BT yöneticilerine tanılama günlükleri göndermesini kolaylaştırmak için Şirket Portalı uygulamasına yeni düğmeler eklenmiştir:

|Düğme adı|Göründüğü yer|
|------------|---------------|
|Rapor|Hata uyarı iletileri|
|Tanılama Raporu Gönder|Şirket Portalı uygulamasının Hakkında ekranı|


>[!div class="step-by-step"]

>[&larr; **Intune’daki yenilikler**](whats-new-in-microsoft-intune.md)    


<!--HONumber=May16_HO3-->


