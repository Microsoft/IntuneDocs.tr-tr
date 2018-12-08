---
title: Erken sürüm
titlesuffix: Microsoft Intune
description: Microsoft Intune erken sürüm
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 12/3/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: ddd1af82c700b0398ca7250f577c712e4a428788
ms.sourcegitcommit: fff179f59bd542677cbd4bf3bacc24bb880e2cb6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/07/2018
ms.locfileid: "53032483"
---
# <a name="the-early-edition-for-microsoft-intune---december-2018"></a>Erken sürüm Microsoft Intune - aralık 2018'e

> [!Note]
> NDA bildirimi: Aşağıdaki değişiklikler, Intune için geliştirilme aşamasındadır. Bu bilgiler NDA kapsamında çok kısıtlı bir kapsamla paylaşılır. Bu bilgilerin hiçbirini sosyal medyada veya Twitter, UserVoice, Reddit vb. gibi kamuya açık web sitelerinde paylaşmayın. 

**Erken sürüm**, NDA altında paylaşılan Microsoft Intune'un gelecek sürümlerinde kullanıma sunulacak yeni özelliklerin bir listesini sunar. Bu bilgiler kısıtlı bir kapsamla verilmektedir ve değiştirilebilir. Bu bilgileri Twitter veya UserVoice’da ya da şirketiniz dışında paylaşmayın. Burada listelenen özelliklerden bazılarının son tarihe yetişememe riski vardır ve gelecek sürüme ertelenebilir. Diğer özellikler, müşterinin kullanımına hazır olduğundan emin olmak için pilot (sürüyor) aşamasında test edilmektedir. Herhangi bir sorunuz veya endişeniz varsa lütfen Microsoft ürün grubu ilgili kişisiyle bağlantı kurun.

Bu sayfa düzenli aralıklarla güncelleştirilir. Ek güncelleştirmeleri daha sonra denetleyin.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Azure portalında Intune

<!-- 1812 start -->

### <a name="android-enterprise-app-we-app-deployment----1171203---"></a>Android Kurumsal uygulama-BİZ uygulama dağıtımı <!-- 1171203 -->
Bir kayıtlı olmayan uygulama koruma İlkesi kayıt olmadan Android cihazlar için (APP-BİZ) dağıtım senaryosu, şunları yapabileceksiniz yönetilen Google Play mağazası uygulamalarını dağıtma ve LOB uygulamaları kullanıcılara için kullanılacak. Özellikle, BT'nin son kullanıcılara cihazlarının güvenlik duruşunu bilinmeyen kaynaklardan yüklemeleri vererek çözmek, son kullanıcılar artık gerektiren bir uygulama kataloğu ve yükleme deneyimi sağlamak. Ayrıca, bu dağıtım senaryosu bir geliştirilmiş son kullanıcı deneyimi sağlar.

### <a name="new-options-to-automatically-connect-and-persist-rules-when-using-dns-settings-on-windows-10-and-later-devices----1333665-2999078---"></a>Otomatik olarak bağlanıp kuralları DNS ayarlarını Windows 10 ve üzeri cihazlarda kullanırken kalıcı hale getirmek için yeni seçenekler <!-- 1333665, 2999078 -->
Windows 10 ve üzeri cihazlarda, etki alanı, contoso.com gibi çözümlemek için DNS sunucularının bir listesini içeren bir VPN yapılandırma profili oluşturmanız mümkün olacaktır. Bu ad çözümlemesi için yeni ayarlar dahil edilir (**cihaz Yapılandırması** > **profilleri** > **profili oluşturma** > Seç **Windows 10 ve üzeri** Platform > Seç **VPN** profil türü için > **DNS ayarlarını** >**Ekle**): 

- **Otomatik olarak bağlan**: zaman **etkin**, bir cihaz, girin, örneğin contoso.com etki alanı ile iletişim kurarken cihaz VPN otomatik olarak bağlanır.
- **Kalıcı**: varsayılan olarak, bu VPN profili kullanarak cihaz bağlı olduğu sürece tüm ad çözümleme İlkesi tablosu (NRPT) kuralları etkindir. Bu ayar olduğunda **etkin** bir NRPT kuralı kural VPN bağlantısını keser veya VPN profilini kaldırılmış olsa bile cihaz üzerinde etkin kalır. El ile yapılabilir kaldırılana kadar kural kalır PowerShell kullanarak.

[Windows 10 VPN ayarları](vpn-settings-windows-10.md) ayarlarının geçerli listesi açıklar. 

### <a name="use-smime-to-encrypt-and-sign-a-users-multiple-devices-----1333642-eeready---"></a>Bir kullanıcının birden fazla cihazını şifrelemek ve imzalamak için S/MIME kullanın <!-- 1333642 eeready -->
Yeni içeri aktarılan sertifika profili kullanarak S/MIME e-posta şifreleme desteklenir (**cihaz Yapılandırması** > **profilleri** > **profilioluşturma** > platformu seçin > **PKCS içe aktarılan sertifikası** profil türü). Intune’da sertifikaları PFX biçiminde içeri aktarabilirsiniz. Intune, aynı sertifikaları tek bir kullanıcı tarafından kaydedilen birden fazla cihaza teslim edebilir. Ayrıca şunları da içerir:

- Yerel iOS e-posta profili, PFX biçiminde içeri aktarılan sertifikaları kullanan S/MIME şifrelemesini etkinleştirmeyi destekler.
- Windows Phone 10 cihazlarındaki yerel posta uygulaması, S/MIME sertifikalarını otomatik olarak kullanır.
- Özel sertifikalar, birden fazla platforma teslim edilebilir. Ancak tüm e-posta uygulamaları, S/MIME’yi desteklemez.
- Diğer platformlarda S/MIME’yi etkinleştirmek için posta uygulamasını el ile yapılandırmanız gerekebilir.  
- S/MIME şifrelemesini destekleyen e-posta uygulamaları, S/MIME e-posta şifrelemesi için sertifika alma işlemini MDM’nin destekleyemeyeceği bir şekilde halleder, ör. yayımcılarının sertifika deposundan okuma.

Desteklenir: Windows, Windows Phone 10, macOS, iOS, Android

### <a name="help-and-support-page-in-the-windows-company-portal-app----1488939---"></a>Yardım ve Destek sayfasının Windows Şirket portalı uygulamasında <!-- 1488939 -->
Windows Şirket portalı uygulamasında yeni bir sayfa eklenir. Yardım ve Destek sayfasına Yardım Masası bilgilerini sağlar. Ayrıca, son kullanıcılara sorunları yaşamaya olay, Şirket portalı günlükleri göndermek mümkün olacaktır. Sayfa, son kullanıcılara yardımcı olmak için bir SSS bölümü de sağlar.

### <a name="use-trusted-network-detection-for-vpn-profiles-on-windows-10-devices----1500165---"></a>Windows 10 cihazlarda VPN profilleri için güvenilen Ağ algılama kullanın <!-- 1500165 -->
Güvenilen ağ algılama kullanırken, VPN profilleri kullanıcı zaten güvenilen bir ağda olduğunda otomatik olarak bir VPN bağlantısı oluşturmasını önlemek mümkün olacaktır. Windows 10 çalıştıran cihazlarda güvenilen Ağ algılama etkinleştirmek için DNS soneklerini eklemek için ve sonraki sürümler (**cihaz Yapılandırması** > **profilleri**  >   **Profil oluşturma** > **Windows 10 ve üzeri** Platform > **VPN** profil türü için).
[Windows 10 VPN ayarları](vpn-settings-windows-10.md) geçerli VPN ayarlarını listeler.

### <a name="the-intune-app-sdk-will-support-256-bit-encryption-keys----1832174---"></a>Intune uygulama SDK'sı, 256 bit şifreleme anahtarları destekleyecek <!-- 1832174 -->
Şifreleme uygulama koruma ilkeleri tarafından etkinleştirilmişse iOS için Intune uygulama SDK'sı, 256 bit şifreleme anahtarları kullanır. SDK'sı, 128 bit anahtar içeriği ve eski SDK sürümleri kullanan uygulamalar ile uyumluluk için destek sağlamak üzere devam eder.

### <a name="enabled-shared-pc-settings-in-intune-profile----1907917---"></a>Intune profilinde etkinleştirilmiş paylaşılan bilgisayar ayarları <!-- 1907917 -->
Şu anda, özel bir OMA-URI ayarını kullanarak Windows 10 Masaüstü cihazlarında bilgisayar paylaşılan ayarları yapılandırabilirsiniz. Paylaşılan bilgisayar ayarları yapılandırmak için yeni bir profil eklenir (**cihaz Yapılandırması** > **profilleri** > **profili oluştur**  >  **Windows 10 ve üzeri** > **paylaşılan çok kullanıcılı cihaz**).
İçin geçerlidir: Windows 10 ve üzeri, Windows Holographic for Business

### <a name="intune-policies-update-authentication-method-and-company-portal-app-installation-----1927359---"></a>Intune ilkeleri, kimlik doğrulama yöntemi ve şirket Portalı Uygulama yüklemesi güncelleştirme  <!-- 1927359 -->
Yüklü olduğunda Intune Şirket portalı uygulaması artık destekler, bazı cihazlarda uygulama Mağazası'ndan. Bu değişiklik, yalnızca kayıt sırasında Apple Kurulum Yardımcısı ile doğrulandığında geçerlidir. Bu değişiklik, yalnızca aracılığıyla kaydedilmiş iOS cihazları etkiler:  
* Apple configurator
* Apple İşletme Yöneticisi
* Apple School Manager
* Apple aygıt kayıt programı (DEP)

Kullanıcıların uygulama Mağazası'ndan Şirket portalı uygulamasını yüklediğinizde ve onun üzerinden bu cihazları kaydetmek deneyin, bunlar bir hatayla karşılaşırsınız. Bu cihazlar, bu, otomatik olarak, kayıt sırasında Intune tarafından gönderildiğinde yalnızca şirket portalını kullanması beklenen. Azure portalında ıntune'da kayıt profilleri, cihazların kimliklerini nasıl doğrulayacaklarını belirtebilirsiniz ve Şirket portalı uygulaması'na alırsanız güncelleştirilecektir. DEP cihaz kullanıcılarınız Şirket portalı olmasını istiyorsanız, tercihlerinizi bir kayıt profili belirtmeniz gerekir. Ayrıca, **Cihazınızı tanımlamanız** Şirket portalı uygulamasında ekran yakında geçersiz olacak.  
Zaten kayıtlı DEP cihazlarında şirket Portalı'nı yüklemek için Intune'a gitmeniz gerekir > istemci uygulamaları ve uygulama yapılandırma ilkeleriyle yönetilen bir uygulama olarak gönderin. Bu adımların hakkında ayrıntılı bilgi gelecekteki belgelere renkle gösterilir.

### <a name="non-administrators-can-enable-bitlocker-on-windows-10-devices-joined-to-azure-ad---2147379---"></a>Yönetici olmayan kullanıcılar Azure AD'ye katılmış Windows 10 cihazlarda BitLocker'ı etkinleştirme<!-- 2147379 -->
Windows 10 cihazlarda BitLocker ayarları etkinleştirdiğinizde (**cihaz Yapılandırması** > **profilleri** > **profili oluşturma**  >  **Windows 10 ve üzeri** Platform > **uç nokta koruma** profil türü için > **Windows şifreleme**), BitLocker ayarları ekleyin. Bu güncelleştirme, şifrelemeyi etkinleştirmek standart kullanıcılar (Yönetici olmayanlar) izin vermek için yeni bir BitLocker ayar içerir. Geçerli ayarları görüntülemek için bkz: [Windows 10 için Endpoint protection ayarları](endpoint-protection-windows-10.md#windows-encryption).

### <a name="intune-app-pin----2298397---"></a>Intune uygulama PIN'i <!-- 2298397 -->
BT yöneticisi olarak, bir son kullanıcının PIN kodunun değiştirilmesi gerekmeden, Intune uygulama kadar bekleyebilirsiniz gün sayısını yapılandırmak mümkün olacaktır. Yeni ayar seçerek Azure portalında kullanıma sunulacak **Intune** > **istemci uygulamaları** > **uygulama koruma ilkeleri**  >  **İlke Oluştur** > **ayarları** > **erişim gereksinimlerini**. Bu özellik, iOS ve Android cihazlarda kullanılabilir. Bu ayar, artı bir tamsayı değeri destekler.

### <a name="new-windows-10-update-settings----2626030-2512994---"></a>Yeni Windows 10 güncelleştirme ayarları <!-- 2626030 2512994 -->
Windows 10 güncelleştirme halkaları için için mümkün olacaktır:
- bir Windows 10 makinede çalışan makineler özgün otomatik güncelleştirme ayarlarını geri *Ekim 2018 güncelleştirmesi*
- yapılandırma ayarı güncelleştirmeleri engellemek ya da kullanıcılarınızın duraklatma güncelleme yüklemesinden olanak sağlar, yeni bir yazılım *ayarları* makinelerinin. 



### <a name="ios-email-profiles-can-use-smime-signing-and-encryption----2662949---"></a>iOS e-posta profilleri, S/MIME imzalama ve şifreleme kullanabilirsiniz. <!-- 2662949 -->
Farklı ayarlar içeren bir e-posta profilini oluşturmak mümkün olacaktır. Bu S/MIME imzalama ve iOS cihazlarında e-posta iletişimleri şifrelemek için kullanılan ayarları içerir (**cihaz Yapılandırması** > **profilleri**  >   **Profil oluşturma** > Seç **iOS** Platform > **e-posta** profil türü için).

[iOS e-posta yapılandırma ayarları](email-settings-ios.md) geçerli ayarlarını listeler.

### <a name="skip-more-setup-assistant-screens-on-an-ios-dep-device----2687509---"></a>İOS DEP cihazı üzerinde daha fazla Kurulum Yardımcısı ekranları atlamak <!-- 2687509 -->
Şu anda atlayabilirsiniz ekranlar yanı sıra, iOS Kurulum Yardımcısı'nı aşağıdaki ekranlarda bir kullanıcı cihaz kaydedilirken atlamak için DEP cihazları ayarlamak mümkün olacaktır: görüntü ton, gizlilik, Android geçiş, giriş düğmesi, iMessage ve FaceTime, ekleme, Geçiş, görünüm, ekran zaman, yazılım güncelleştirmesi, SIM Kurulum izleyin.
Hangi atlamak için ekranları seçmek için Git **cihaz kaydı** > **Apple kaydı** > **kayıt programı belirteçleri** > bir belirteç seçin > **Profilleri** > bir profili seçin > **özellikleri** > **Kurulum Yardımcısı özelleştirme** > seçin **Gizle**  atlamak istediğiniz tüm ekranlar için > **Tamam**.

### <a name="some-bitlocker-settings-support-windows-10-pro-edition---2727036---"></a>Windows 10 Pro sürümü bazı BitLocker ayarları desteği<!-- 2727036 -->
Endpoint protection ayarları BitLocker dahil olmak üzere Windows 10 cihazlarda ayarlar bir yapılandırma profili oluşturmanız mümkün olacaktır. Bu, Windows 10 Professional edition bazı BitLocker ayarları için destek ekler. Geçerli Windows 10 sürüm ayarlarını görmek için bkz: [Windows 10 için Endpoint protection ayarları](endpoint-protection-windows-10.md#windows-encryption).
Intune, Android üreticisi, modeli ve güvenlik düzeltme eki sürümü yanı sıra iOS modeli de dahil olmak üzere alanlar, raporlama ek cihaz sağlayacaktır. Intune, bu alanları seçerek kullanılabilir **istemci uygulamaları** > **uygulama koruma durumu** seçip **uygulama koruma raporu: iOS, Android**. Bu parametreleri yapılandırma Ayrıca, yardımcı olacak **izin ver** cihaz üreticisi (Android) için liste **izin** cihaz modeli (Android ve iOS) ve en düşük Android güvenlik düzeltme eki için listesi Sürüm ayarı. 

### <a name="intune-device-reporting-fields----2748738---"></a>Intune cihaz alanları raporlama <!-- 2748738 -->
Intune, Android üreticisi, modeli ve güvenlik düzeltme eki sürümü yanı sıra iOS modeli de dahil olmak üzere alanlar, raporlama ek cihaz sağlayacaktır. Intune, bu alanları seçerek kullanılabilir **istemci uygulamaları** > **uygulama koruma durumu** seçip **uygulama koruma raporu: iOS, Android**. Bu parametreleri yapılandırma Ayrıca, yardımcı olacak **izin ver** cihaz üreticisi (Android) için liste **izin** cihaz modeli (Android ve iOS) ve en düşük Android güvenlik düzeltme eki için listesi Sürüm ayarı. 

### <a name="shared-device-configuration-is-renamed-to-lock-screen-message-for-ios-devices-in-the-azure-portal----2809362---"></a>Azure portalında iOS cihazları için paylaşılan cihaz yapılandırması kilit ekranı iletisi için yeniden adlandırılır <!-- 2809362 -->
İOS cihazları için bir yapılandırma profili oluşturduğunuzda, sizin eklemek mümkün olacaktır **paylaşılan cihaz Yapılandırması** kilit ekranında belirli bir metin göstermek için ayarları. Bu, aşağıdaki değişiklikleri içerir: 

- **Paylaşılan cihaz Yapılandırması** ayarları Azure portalında "(yalnızca denetimli) kilit ekranı iletisi için" yeniden adlandırılmış (**cihaz Yapılandırması** > **profilleri**  >  **Profili oluşturma** > Seç **iOS** platformuna yönelik > Seç **cihaz özellikleri** profil türü için > **Kilitle Ekran ileti**).
- Kilit ekranı iletileri eklerken, seri numarası, cihaz adı veya başka bir cihaza özgü değer bir değişken olarak ekleyebilirsiniz **varlık etiketi bilgileri**. Örneğin, girdiğiniz `Device name: {{device name}}` veya `Serial number is {{serial number}}` süslü ayraçlar kullanarak. [iOS belirteçleri](app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) kullanılabilecek kullanılabilir belirteçler listeler.

[Kilit ekranında iletilerin gösterilmesi için ayarları](shared-device-settings-ios.md) geçerli ayarlarını listeler.

### <a name="more-detailed-enrollment-restriction-failure-messaging----3111564--"></a>Daha ayrıntılı kayıt kısıtlama hata iletileri <!-- 3111564-->
Kayıt kısıtlamaları karşılanmadı daha ayrıntılı hata iletileri kullanılabilir. Bu iletileri görmek için Git **Intune** > **sorun giderme** > ve kayıt hataları tabloyu gözden geçirin.

### <a name="new-notification-hints-and-keyguard-settings-to-android-enterprise-device-owner-devices----3201839-3201843---"></a>Android Kurumsal cihaz sahibi cihazlar için yeni bildirim, ipuçları ve tuş korumasını ayarları <!-- 3201839 3201843 -->
Bu güncelleştirme, cihaz sahibi olarak çalıştırırken Android Kurumsal cihazlarda çeşitli yeni özellikler içerir. Bu özellikleri kullanmak için Git **cihaz Yapılandırması** > **profilleri** > **profili oluşturma** > içinde **platformu**, seçin **Android Kurumsal** > içinde **profil türü**, seçin **yalnızca cihaz sahibi** > **cihaz Kısıtlamaları**.
Yeni özellikler içerir: 
- Gösteren gelen çağrıları, sistem uyarıları, sistem hataları ve daha fazlası dahil olmak üzere, sistem bildirimleri devre dışı bırak
- Başlangıç öğreticileri ve ilk kez açan uygulamalar için ipuçları Atla önerir
- Gelişmiş Tuş korumasını kamera, bildirimler, parmak izi gibi ayarları kilidini açmak ve daha fazlası devre dışı bırak

Geçerli ayarları görmek için Git [Android Kurumsal cihaz kısıtlama ayarları](device-restrictions-android-for-work.md).

### <a name="android-enterprise-device-owner-devices-can-use-always-on-vpn-connections----3202194---"></a>Android Kurumsal cihaz sahibi cihazlar her zaman açık VPN bağlantıları kullanabilirsiniz. <!-- 3202194 -->
Bu güncelleştirmede Android Kurumsal cihaz sahibi cihazlarda her zaman açık VPN bağlantıları kullanabilirsiniz. Her zaman açık VPN bağlantıları; kullanıcı cihazının kilidini açtığında, cihaz yeniden başlatıldığında veya kablosuz ağ değiştiğinde bağlı kalır veya hemen tekrar bağlanır. Bağlantıyı “kilitli”moduna da alabilirsiniz, böylece VPN bağlantısı etkin olana kadar tüm ağ trafiği engellenir.
Her zaman açık VPN etkinleştirebilirsiniz **cihaz Yapılandırması** > **profilleri** > **profili oluşturma**  >   **Android Kurumsal** Platform > **cihaz kısıtlamaları** yalnızca cihaz sahibi > **bağlantı** ayarları. Geçerli ayarları görmek için Git [Android Kurumsal cihaz kısıtlama ayarları](device-restrictions-android-for-work.md).

### <a name="new-setting-to-end-processes-in-task-manager-on-windows-10-devices----3285177---"></a>Yeni Windows 10 cihazlarında Görev Yöneticisi'nde son işlemler için ayarlama <!-- 3285177 --> 
Bu güncelleştirme, Windows 10 cihazlarda Görev Yöneticisi'ni kullanarak işlemleri sonlandırmak için yeni bir ayar içerir. Bir cihaz yapılandırma profili kullanarak (**cihaz Yapılandırması** > **profilleri** > **profili oluşturma** > içinde **platformu** , seçin **Windows 10** > içinde **profil türü**, seçin **cihaz kısıtlamaları** > **genel** ayarları), izin verme veya engelleme bu ayarı seçin.
Geçerli ayarları görmek için Git [Windows 10 cihaz kısıtlama ayarları](device-restrictions-windows-10.md).
Şunlar için geçerlidir: Windows 10 ve üzeri

### <a name="administrative-templates-are-in-public-preview-and-moved-to-their-own-configuration-profile----3322847---"></a>Yönetim Şablonları genel Önizleme aşamasındadır ve kendi yapılandırma profiline taşınır <!-- 3322847 -->
Intune Yönetim Şablonları (**cihaz Yapılandırması** > **Yönetim Şablonları**) şu anda özel Önizleme aşamasındadır. Bu güncelleştirme ile: Yönetim Şablonları, Intune'da yönetilebilir 300 ayarları içerir. Daha önce bu ayarlar, yalnızca Grup İlkesi Düzenleyicisi'nde vardı.
Yönetim Şablonları genel önizlemede Yönetim Şablonları hareket etmesini **cihaz Yapılandırması** > **Yönetim Şablonları** için **cihaz Yapılandırma** > **profilleri** >**profili oluşturma** > içinde **Platform**, seçin  **Windows 10 ve üzeri**, **profil türü**, seçin **Yönetim Şablonları**.
Raporlama etkinse geçerlidir: Windows 10 ve üzeri


<!-- 1810 start -->

### <a name="use-microsoft-recommended-settings-with-security-baselines----2055484---"></a>Microsoft tarafından önerilen Güvenlik Taban Çizgili ayarları kullanma <!-- 2055484 -->
Intune, Windows Defender ATP ve Office 365 ATP dahil güvenliğe odaklı diğer hizmetlerle tümleşir. Müşteriler, Microsoft 365 hizmetleri çapında ortak bir strateji ve birbiriyle bütünleşen bir dizi uçtan uca güvenlik iş akışı istiyor. Amacımız, stratejileri birbiriyle uyumlu hale getirmek ve güvenlik işlemleri ve sık kullanılan yönetici görevleri arasında bir köprü oluşturan çözümler geliştirmek. Intune olarak bu amaca Microsoft tarafından önerilen bir dizi "Güvenlik taban çizgisini" (**Intune** > **Güvenlik taban çizgileri**) yayımlayarak ulaşmayı hedefliyoruz.  Yöneticiler, doğrudan bu taban çizgilerinden güvenlik ilkeleri oluşturabilecek ve sonra bunları kullanıcılarına dağıtabilecekler. Ayrıca en iyi yöntem olan önerileri kuruluşlarının ihtiyaçlarını karşılayacak şekilde özelleştirebilirler. Intune, cihazların bu taban çizgilerle uyumlu kalmasını sağlar ve yöneticilere uyumlu olmayan kullanıcıları ve cihazları bildirir.

### <a name="scope-tags-for-apps---1081941---"></a>Uygulamalar için kapsam etiketleri <!--1081941 -->
Intune kaynaklarına erişimi sınırlamak için kapsam etiketleri oluşturabileceksiniz. Bir rol atamasına kapsam etiketi ekleyin ve daha sonra kapsam etiketini bir yapılandırma profiline ekleyin. Rolün yalnızca eşleşen kapsam etiketlerine sahip yapılandırma profillerine erişimi olacaktır.
Bir kapsam etiketi oluşturmak için **Intune rolleri** > **Kapsam (Etiketler)** > **Oluştur**’u seçin.
Kapsam etiketini bir rol atamasına eklemek için **Intune rolleri** > **Tüm roller** > **İlke ve Profil Yöneticisi** > **Atamalar** > **Kapsam (Etiketler)**’i seçin.
Kapsam etiketini bir yapılandırma profiline eklemek için **Cihaz yapılandırması** > **Profiller** > bir profil seçin > **Özellikler** > **Kapsam (Etiketler)**’i seçin.

### <a name="tenant-health-dashboard----1124854---"></a>Kiracı Sistem Durumu panosu <!-- 1124854 -->
Intune Kiracı Durumu sayfası tek bir yerde kiracı durumu bilgileri sağlayacaktır. Sayfa 4 bölüme ayrılmıştır:  
- **Kiracı Ayrıntıları**: MDM Yetkiliniz, kiracınızdaki toplam kayıtlı cihaz sayısı ve lisans sayınız gibi bilgileri içerir. Bu bölüm, kiracınız için geçerli hizmet sürümünü de sağlanır.
- **Bağlayıcı Durumu**: Apple VPP, İş için Windows Store ve Sertifika bağlayıcıları gibi yapılandırılmış bağlayıcıların bilgilerini içerir. Bunların geçerli durumu temel alındığında bağlayıcılar *Sağlıklı*, *Uyarı* veya *Sağlıksız* olarak işaretlenir.
- **Intune Hizmet Durumu**: Kiracınız için etkin olayları ve kesintileri içerir. Bu bölümdeki bilgiler doğrudan Office İleti Merkezi'nden ([https://portal.office.com](https://portal.office.com)) alınır.
- **Intune Haberleri**: Kiracınızın en yeni Intune özelliklerini aldığı bildirimleri gibi şeyler dahil, kiracınız için etkin iletileri içerir. Bu bölümdeki bilgiler doğrudan Office İleti Merkezi'nden ([https://portal.office.com](https://portal.office.com)) alınır.


### <a name="deployed-wip-policies-without-user-enrollment----1434452---"></a>Kullanıcı kaydı olmadan dağıtılan WIP ilkeleri <!-- 1434452 -->
Windows Bilgi Koruması (WIP) ilkeleri, MDM kullanıcılarının Windows 10 cihazlarını kaydetmesini gerektirmeden dağıtılabilecektir. Bu yapılandırma, kullanıcıların Windows cihazlarının yönetimini sürdürmesini sağlarken şirketlerin de kurumsal belgelerini WIP yapılandırmasına göre korumasını sağlar. Belgeler bir kez bir WIP ilkesiyle korunduktan sonra korumalı veriler bir Intune yöneticisi tarafından seçmeli olarak silinebilir. Kullanıcı ve cihaz seçilerek ve bir silme isteği gönderilerek WIP İlkesi aracılığıyla korunan tüm veriler kullanılamaz hale getirilir. Azure portalındaki Intune'dan **Mobil uygulama** > **Uygulama seçmeli silme**'yi seçin.


<!-- 1809 start -->  

### <a name="app-protection-policy-app-settings-for-web-data----2662995---"></a>Web verileri için Uygulama Koruma İlkesi (APP) ayarları <!-- 2662995 -->
Gerek Android gerekse iOS cihazlarında Web içeriği için uygulama ilke ayarları, gerek http gerekse https Web bağlantılarını, ayrıca iOS Evrensel Bağlantıları ve Android Uygulama Bağlantıları aracılığıyla veri aktarımını daha iyi işleyecek şekilde güncelleştirilecektir.  

<!-- 1808 start -->

### <a name="apple-vpp-token-used-by-another-mdm----1488946---"></a>Başka bir MDM tarafından kullanılan Apple VPP belirteci <!-- 1488946 -->
Bir Apple toplu satın alınan program (VPP) belirteci hem Intune hem de başka bir MDM tarafından kullanıldığında Intune bunu algılayacak ve ayrıntıları gösterecek.

### <a name="retired-devices-in-the-device-compliance-dashboard----1981119---"></a>Cihaz uyumluluk panosunda kullanımdan kaldırılan cihazlar <!-- 1981119 -->
Gelecek bir güncelleştirme ile kullanımdan kaldırılan cihazlar uyumluluk panosundan da kaldırılacak. Bu durum, uyumluluk numaralarınızı değiştirecek.


### <a name="change-in-the-update-process-for-on-premises-connectors----2277554---"></a>Şirket içi bağlayıcılar için güncelleştirme işleminde değişiklik <!-- 2277554 -->
Müşterilerden gelen geri bildirimlere dayalı olarak şirket içi bağlayıcılarda güncelleştirme işlemi değiştirilecek. Bir şirket içi bağlayıcıyı ilk yüklediğinizde güncelleştirmeler otomatik olarak gerçekleşecek. Bu değişiklik, yeni Microsoft Intune için PFX Sertifika Bağlayıcısı ile başlayacak ve ardından diğer şirket içi bağlayıcı türlerine de sağlanacak. 

<!-- 1807 start -->

### <a name="check-for-configuration-manager-compliance----2192052---"></a>Configuration Manager uyumluluğunu denetleme <!-- 2192052 -->
Gelecekte yapılacak bir güncelleştirmede yeni bir System Center Configuration Manager uyumluluk ayarı olacak (**Cihaz uyumluluğu** > **İlkeler** > **İlke oluştur** > **Windows 10**). Configuration Manager, Intune uyumluluğuna sinyal gönderir. Intune ayarını kullanarak tüm Configuration Manager sinyallerinin “uyumlu” olarak döndürülmesini gerektirebilirsiniz.

Örneğin, tüm yazılım güncelleştirmelerinin cihazlarda yüklü olmasını gerektirirsiniz. Configuration Manager’da bu gereksinim, “Yüklü” durumundadır. Cihazdaki herhangi bir program bilinmeyen bir durumdaysa cihaz, Intune ile uyumlu olmayacaktır.

Windows 10 ve üzeri için geçerlidir



## <a name="notices"></a>Bildirimler

Şu anda etkin bildirim yok.

### <a name="see-also"></a>Ayrıca bkz.
Son geliştirmelere ilişkin ayrıntılar için bkz. [Microsoft Intune’daki Yenilikler](whats-new.md).



