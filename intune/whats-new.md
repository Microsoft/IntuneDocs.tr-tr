---
title: Microsoft Intune - Azure’daki yenilikler | Microsoft Docs
titlesuffix: ''
description: Intune Azure portalındaki yenilikleri keşfedin
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/04/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.openlocfilehash: 996b4d85da41b480d73d7a79011e2bbd732ea334
ms.sourcegitcommit: dde9e1e1d15c412751a186410c2a04974ff1b102
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/04/2019
ms.locfileid: "55690844"
---
# <a name="whats-new-in-microsoft-intune"></a>Microsoft Intune'daki yenilikler
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Microsoft Intune’daki haftalık yenilikleri öğrenin. Yaklaşan değişiklikler, [önemli bildirimler](#notices) ve [geçmiş yayınlar](whats-new-archive.md) hakkında bilgiler de alabilirsiniz. 

> [!Note]
> Bazı özelliklerin piyasaya çıkması birkaç haftayı bulabilir ve tüm özellikler ilk hafta bütün müşterilerimize sunulmamış olabilir.
>
> Karma mobil cihaz yönetimindeki (MDM) yeni işlevler hakkında bilgi için, [karma Yenilikler sayfasını](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) gözden geçirin.

**RSS akışı**: Bu sayfa aşağıdaki URL'yi kullanarak akış okuyucuya yapıştırarak güncelleştirildiğinde bildirim alın: `https://docs.microsoft.com/api/search/rss?search=%22What%27s+new+in+microsoft+intune%3F+-+Azure%22&locale=en-us`

<!-- Common categories:  
### App management
### Device configuration
### Device enrollment
### Device management
### Intune apps
### Monitor and troubleshoot
### Role-based access control

-->     
## <a name="week-of-february-4-2019"></a>4 Şubat 2019 haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="intune-macos-company-portal-dark-mode----3300524-eeready---"></a>Intune macOS Şirket portalı koyu modu <!-- 3300524 eeready -->
Intune macOS Şirket portalı, macOS için artık koyu modunu destekler. Bir macOS 10.14 + cihazda koyu modunu etkinleştirdiğinizde, Şirket portalı görünümünü mod yansıtan renkleri için ayarlanır.

## <a name="week-of-january-21-2019"></a>21 Ocak 2019 haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="toast-notifications-for-win32-apps----3136566-----"></a>Win32 uygulamaları için kutlama bildirimleri <!-- 3136566   -->
Uygulama ataması başına gösteren son kullanıcı bildirimleri gösterilmemesini sağlayabilirsiniz. Intune'dan seçin **istemci uygulamaları** > **uygulamaları** > uygulamayı seçin > **atamaları** > **grupları dahil**. 

#### <a name="intune-app-protection-policies-ui-update----3251427----"></a>Intune uygulama koruma ilkeleri kullanıcı arabirimi güncelleştirmesi <!-- 3251427  -->
Özelliğin ayarları için etiketleri ve anlamak her kolaylaştırmak Intune uygulama koruması için düğmeler değiştirdik. Değişikliklerden bazıları şunlardır:  
- Denetimleri değiştirildi **Evet** / **hiçbir** için öncelikle denetimleri **blok** / **izin** ve **devre dışı** / **etkinleştirme** kontrol eder. Etiketler de güncelleştirilir.  
- Ayarları biçimlendirilir, yan yana ayarı ve etiketini olacak şekilde daha iyi Gezinti sağlamak için denetimi.   

Varsayılan ayarlar ve ayar aynı kalır, ancak bu değişiklik anlamak, kodlarda gezinin ve seçili uygulama koruma ilkeleri kolayca uygulamak için daha fazla ayarları kullanmasına izin verir. Bilgi için [iOS ayarları](app-protection-policy-settings-ios.md) ve [Android ayarları](app-protection-policy-settings-android.md).

#### <a name="additional-settings-for-outlook----3301182----"></a>Outlook için ek ayarlar <!-- 3301182  -->
Artık iOS için Outlook ve Intune kullanarak Android için followiong ek ayarlar da yapılandırabilirsiniz:
- Yalnızca iOS ve Android Outlook'ta kullanılacak iş veya Okul hesaplarını izin ver
- Office 365 modern kimlik doğrulamayı dağıtmak ve hibrit modern kimlik doğrulaması şirket hesapları
- Kullanım `SAMAccountName` username alan temel kimlik doğrulaması seçildiğinde e-posta profili için

Aşağıdaki ayarlar, yine de yavaş yavaş kullanıma sunuluyor ve yakında Konsolunuzda kullanıma sunulacaktır:
- Kaydedilecek kişiler izin ver
- Dış alıcılara posta ipuçları yapılandırın
- Yapılandırma **odaklanmış gelen kutusu**
- İOS için Outlook erişmeye Biyometri gerektirir

Aşağıdaki ayar Intune konsolunda görünür, ancak yapılandırıldığında, beklendiği gibi çalışmaz. Bu sorun yakında çözülecektir:
- Bloğu dış görüntüleri

> [!NOTE]
> Erişim için Kurumsal kimlikleri yönetmek için Intune uygulama koruma ilkeleri kullanıyorsanız değil etkinleştirmeyi düşünebilirsiniz **Biyometri gerektiren**. Daha fazla bilgi için **erişim için Kurumsal kimlik bilgilerini gerektir** için [iOS erişim ayarlarını](app-protection-policy-settings-ios.md#access-requirements) ve [Android erişim ayarları](app-protection-policy-settings-android.md#access-requirements).

#### <a name="delete-android-enterprise-apps----1352553---"></a>Android Kurumsal uygulamaları Sil <!-- 1352553 -->
Yönetilen Google Play uygulamaları Microsoft Intune silebilirsiniz. Yönetilen Google Play uygulama silmek için Azure portal ve select Intune açın **istemci uygulamaları** > **uygulamaları**. Uygulama listesinden yönetilen Google Play uygulaması'nın sağındaki üç nokta (...) seçin ve ardından **Sil** görüntülenen listeden. Uygulama listesinden bir yönetilen Google Play uygulaması sildiğinizde, yönetilen Google Play uygulaması otomatik olarak onaylanmadı.

#### <a name="managed-google-play-app-type----1352580---"></a>Yönetilen Google Play uygulaması türü <!-- 1352580 -->
**Yönetilen Google Play** uygulama türü, özellikle eklemenize olanak sağlayacaktır [yönetilen Google Play uygulamaları](https://play.google.com/work/search?q=microsoft&c=apps) ıntune. Intune Yöneticisi olarak, artık göz atabilir, arama, onaylama, eşitleme ve onaylı bir yönetilen Google Play uygulamaları Intune içerisindeki atayın.  Yönetilen Google Play konsolunu için ayrı olarak göz atmak artık ihtiyacınız ve yeniden kimlik doğrulamaya zorlayabilir artık yok.  Intune'da seçin **istemci uygulamaları** > **uygulamaları** > **Ekle**. İçinde **uygulama türü** listesinden **yönetilen Google Play** uygulama türü olarak.

### <a name="default-android-pin-keyboard----3802457---"></a>Varsayılan Android PIN klavye <!-- 3802457 -->
Intune uygulama koruma İlkesi (uygulama) PIN, PIN 'Sayısal' türüne sahip Android cihazlarında ayarladığınız son kullanıcılar için artık sabit Android klavye daha önce tasarlanan kullanıcı Arabirimi yerine varsayılan Android klavye görürler. Varsayılan klavye iki PIN türleri 'Sayısal' ve/veya 'Parola' için hem Android hem de iOS, kullanırken tutarlı olması için bu değişiklik yapılmıştır. Android'de uygulama PIN'i gibi son kullanıcıya erişim ayarları hakkında daha fazla bilgi için bkz. [Android erişim gereksinimlerini](app-protection-policy-settings-android.md#access-requirements).

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="use-microsoft-recommended-settings-with-security-baselines-public-preview----2055484-----"></a>Güvenlik temellerini (genel Önizleme) ile Microsoft tarafından önerilen ayarları kullanma <!-- 2055484   -->

Intune, Windows Defender ATP ve Office 365 ATP dahil güvenliğe odaklı diğer hizmetlerle tümleşir. Müşteriler, Microsoft 365 hizmetleri çapında ortak bir strateji ve birbiriyle bütünleşen bir dizi uçtan uca güvenlik iş akışı istiyor. Amacımız, stratejileri birbiriyle uyumlu hale getirmek ve güvenlik işlemleri ve sık kullanılan yönetici görevleri arasında bir köprü oluşturan çözümler geliştirmek. Intune olarak bu amaca Microsoft tarafından önerilen bir dizi "Güvenlik taban çizgisini" (**Intune** > **Güvenlik taban çizgileri**) yayımlayarak ulaşmayı hedefliyoruz.  Bir yönetici, doğrudan bu taban çizgisi arasından güvenlik ilkeleri oluşturmak ve bunları kullanıcılarına dağıtabilirsiniz. Ayrıca, kuruluşunuzun ihtiyaçlarını en iyi yöntem önerileri de özelleştirebilirsiniz. Intune, cihazların bu taban çizgilerle uyumlu kalmasını sağlar ve yöneticilere uyumlu olmayan kullanıcıları ve cihazları bildirir.

Bu özellik genel Önizleme aşamasında olduğundan, oluşturulan herhangi bir profil artık genel kullanıma (GA) için güvenlik temellerini şablonları taşımaz. Bu önizleme şablonları, üretim ortamınızda kullanmayı planlıyorsanız olmamalıdır.

Güvenlik taban çizgileri hakkında daha fazla bilgi için bkz. [Intune Windows 10 Güvenlik taban çizgisi oluşturma](security-baselines-monitor.md).

Bu özellik şu platformlarda geçerlidir: Windows 10 ve üzeri

#### <a name="non-administrators-can-enable-bitlocker-on-windows-10-devices-joined-to-azure-ad---2147379-----"></a>Yönetici olmayan kullanıcılar Azure AD'ye katılmış Windows 10 cihazlarda BitLocker'ı etkinleştirme<!-- 2147379   -->
Windows 10 cihazlarda BitLocker ayarları etkinleştirdiğinizde (**cihaz Yapılandırması** > **profilleri** > **profili oluşturma**  >  **Windows 10 ve üzeri** Platform > **uç nokta koruma** profil türü için > **Windows şifreleme**), BitLocker ayarları ekleyin. 

Bu güncelleştirme, şifrelemeyi etkinleştirmek standart kullanıcılar (Yönetici olmayanlar) izin vermek için yeni bir BitLocker ayar içerir. 

Ayarları görmek için Git [Windows 10 için Endpoint protection ayarları](endpoint-protection-windows-10.md#windows-encryption).

#### <a name="check-for-configuration-manager-compliance----2192052--eepublished----"></a>Configuration Manager uyumluluğunu denetleme <!-- 2192052  eepublished  -->
Bu güncelleştirme, yeni bir System Center Configuration Manager Uyumluluk ayarı içerir (**cihaz uyumluluğu** > **ilkeleri** > **İlkesioluşturma**  >  **Windows 10 ve üzeri** > **Configuration Manager Uyumluluk**). Configuration Manager, Intune uyumluluğuna sinyal gönderir. Bu ayarı kullanarak, "uyumlu" döndürülecek tüm Configuration Manager sinyaller gerektirebilir.

Örneğin, tüm yazılım güncelleştirmelerinin cihazlarda yüklü olmasını gerektirirsiniz. Configuration Manager’da bu gereksinim, “Yüklü” durumundadır. Cihazdaki tüm programları bilinmeyen bir durumda, cihazı Intune'da uyumlu olmadığını.

[Configuration Manager Uyumluluk](compliance-policy-create-windows.md#configuration-manager-compliance) Bu ayar açıklar.

Uygulama hedefi: Windows 10 ve üzeri

#### <a name="customize-wallpaper-on-supervised-ios-devices-using-a-device-configuration-profile----2809324-----"></a>Duvar kağıdı denetimli iOS cihazlarında cihaz yapılandırma profili kullanarak özelleştirme <!-- 2809324   -->
İOS cihazları için cihaz yapılandırma profili oluşturduğunuzda, bazı özellikler özelleştirebilirsiniz (**cihaz Yapılandırması** > **profilleri** > **oluştur profili** > **iOS** Platform > **cihaz özellikleri** profil türü için). Bu güncelleştirme yeni eklemeler **duvar kağıdı** giriş ekranına veya kilit ekranında bir .png, .jpg veya .jpeg görüntüsü kullanmak yönetici izin ayarları. Bu duvar kağıdı ayarları yalnızca denetimli cihazlar için geçerlidir. 

Bu ayarların listesi için bkz. [iOS cihaz özelliği ayarlarını](ios-device-features-settings.md).

#### <a name="windows-10-kiosk-is-generally-available----3594661----"></a>Windows 10 bilgi noktası kullanıma sunuldu <!-- 3594661  -->
Bu güncelleştirme, Windows 10 ve üzeri cihazlarda bilgi noktası özelliği genel kullanıma (GA) ' dir. Ekleme ve yapılandırma tüm ayarları görmek için bkz: [bilgi noktası ayarları (Windows 10 ve üzeri)](kiosk-settings.md).

#### <a name="contact-sharing-via-bluetooth-is-removed-in-device-restrictions--device-owner-for-android-enterprise----3598396-----"></a>Bluetooth ile kişi paylaşımı cihaz kısıtlamaları kaldırılmış > Android Kurumsal cihaz sahibi <!-- 3598396   -->
Kurumsal Android cihazlar için cihaz kısıtlama profili oluşturduğunuzda, var olan bir **Bluetooth aracılığıyla kişi paylaşımı** ayarı. Bu güncelleştirmede, **Bluetooth aracılığıyla kişi paylaşımı** ayarı kaldırıldı (**cihaz Yapılandırması** > **profilleri**  >   **Profil oluşturma** > **Android Kurumsal** Platform > **cihaz kısıtlamaları > cihaz sahibi** profil türü için > **genel** ). 

**Bluetooth aracılığıyla kişi paylaşımı** ayarı Android Kurumsal cihaz sahibi yönetimi için desteklenmez. Bu ayar kaldırıldığında, bu ayar etkinleştirildikten ve yapılandırıldıktan sonra ortamınızda olsa bile bu nedenle, herhangi bir cihaz veya kiracıları, etkilemez.

Geçerli ayarları listesini görmek için Git [izin vermek veya özellikleri kısıtlamak için Android Kurumsal cihaz ayarları](device-restrictions-android-for-work.md).

Uygulama hedefi: Android Kurumsal cihaz sahibi

### <a name="device-management"></a>Cihaz yönetimi

#### <a name="selective-wipe-support-for-wip-without-enrollment-devices----1434452---"></a>Kayıt olmadan WIP cihazlar için seçmeli temizleme desteği <!-- 1434452 -->
Kayıt olmadan Windows bilgi Koruması (WIP-BİZ) Windows 10 cihazlarda tam MDM kaydı gerek kalmadan Kurumsal verileri korumak müşterilerin olanak tanır. Bir WIP ile korunan belgeleri sonra-BİZ ilke, korunan verilerin bir Intune Yöneticisi tarafından seçmeli temizlenmesine. Kullanıcı ve cihaz seçerek ve WIP ile korunan tüm verileri bir silme isteği gönderiliyor-BİZ İlkesi kullanılamaz olacak. Azure portalındaki Intune'dan **Mobil uygulama** > **Uygulama seçmeli silme**'yi seçin.

### <a name="monitor-and-troubleshoot"></a>İzleme ve sorun giderme

#### <a name="new-operational-logs-and-ability-to-send-logs-to-azure-monitor-services----3762211----"></a>Yeni işlem günlüklerini ve Azure İzleyici Hizmetleri günlükleri gönderme olanağı <!-- 3762211  -->
Intune, değişiklikler yapıldıkça olayları izleyen yerleşik denetim günlüğü sahiptir. Bu güncelleştirme, yeni günlük özellikleri içerir: 
- Kullanıcılar ve cihazlar üzerinde ayrıntıları göster operasyonel günlükler (Önizleme) başarı dahil olmak üzere, kayıtlı ve girişimleri başarısız oldu.
- Denetim günlükleri ve işlem günlüklerini Azure depolama hesapları, olay hub'ları da dahil olmak üzere İzleyici gönderilebilir ve log analytics. Bu hizmetler, depolamak, Splunk ve QRadar gibi analizi kullanma ve günlüğe kaydetme görselleştirilmiş alma olanak tanır.

[Olay hub'ları, depolama için günlük verileri gönderin veya Intune'da oturum analytics](review-logs-using-azure-monitor.md) bu özellik hakkında daha fazla bilgi sağlar.

### <a name="skip-more-setup-assistant-screens-on-an-ios-dep-device----2687509----"></a>İOS DEP cihazı üzerinde daha fazla Kurulum Yardımcısı ekranları atlamak <!-- 2687509  -->
Şu anda atlayabilirsiniz ekranlar ek olarak, bir kullanıcı cihaz kaydedilirken Kurulum Yardımcısı'nı aşağıdaki ekranlarda atlamak için DEP cihazları iOS ayarlayabilirsiniz: Sesi, gizlilik, Android geçişi, giriş düğmesi, iMessage & FaceTime, ekleme, Watch geçişi, görünüm, ekran zaman, yazılım güncelleştirmesi, SIM Kurulum görüntüler.
Hangi atlamak için ekranları seçmek için Git **cihaz kaydı** > **Apple kaydı** > **kayıt programı belirteçleri** > bir belirteç seçin > **Profilleri** > bir profili seçin > **özellikleri** > **Kurulum Yardımcısı özelleştirme** > seçin **Gizle**  atlamak istediğiniz tüm ekranlar için > **Tamam**.
Yeni bir profil oluşturun ya da bir profil düzenleme, seçili ekranlar Apple MDM sunucusu ile eşitleme gerek atlayın. Kullanıcılar, böylece gecikme profili değişiklikleri çekme cihazların el ile eşitleme verebilir.

#### <a name="android-enterprise-app-we-app-deployment----1171203---"></a>Android Kurumsal uygulama-BİZ uygulama dağıtımı <!-- 1171203 -->
Bir kayıtlı olmayan uygulama koruma İlkesi kayıt olmadan Android cihazlar için (APP-BİZ) dağıtım senaryosu, şunları yapabilirsiniz artık yönetilen Google Play'e mağaza uygulamaları ve LOB uygulamaları kullanıcılara kullanın. Özellikle, son kullanıcıların cihazlarında güvenlik duruşunu bilinmeyen kaynaklardan yüklemeleri vererek çözmek, son kullanıcılar artık gerektiren bir uygulama kataloğu ve yükleme deneyimi ile sağlayabilir. Ayrıca, bu dağıtım senaryosu bir geliştirilmiş son kullanıcı deneyimi sağlar.

## <a name="week-of-january-14-2019"></a>14 Ocak 2019 haftası

### <a name="preview-of-support-for-android-corporate-owned-fully-managed-devices----1574342----"></a>Şirkete ait ve tamamen yönetilen Android cihazları için destek önizlemesi <!-- 1574342  -->
Tam olarak yönetilen Android cihazlar, bir kuruluşa ait destekler artık Intune yeri sıkı bir şekilde tarafından yönetilen cihazları "cihaz sahibi" senaryo BT ve tek tek kullanıcılarla bağlı. Bu durum, yöneticilerin tüm cihazı yönetebilir, ilke denetimlerini iş profilleri kullanılamaz genişletilmiş bir aralığını zorla olanak sağlar ve kullanıcıları, yalnızca yönetilen Google Play uygulamaları yüklemek için sınırlar. Daha fazla bilgi için [Intune'u ayarlama Android kayıt tam olarak yönetilen cihazlar](android-fully-managed-enroll.md) ve [adanmış cihazlar veya tam olarak yönetilen cihazları kaydetme](android-dedicated-devices-fully-managed-enroll.md).  Bu özelliğin önizlemede olduğunu lütfen unutmayın. Sertifikalar, uyumluluk ve koşullu erişim gibi bazı Intune özellikleri ile şu anda kullanılabilir olmayan Android tam olarak yönetilen kullanıcı cihazları.

## <a name="week-of-january-7-2019"></a>7 Ocak 2019 haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="intune-app-pin----2298397---"></a>Intune uygulama PIN'i <!-- 2298397 -->
BT yöneticisi olarak, bir son kullanıcının PIN kodunun değiştirilmesi gerekmeden, Intune uygulama kadar bekleyebilirsiniz gün sayısını yapılandırabilirsiniz. Yeni ayar *PIN sıfırlamayı kaç gün sonra* ve seçerek Azure Portalı'nda kullanılabilir **Intune** > **istemci uygulamaları**  >   **Uygulama koruma ilkeleri** > **ilke Oluştur** > **ayarları** > **erişim gereksinimlerini**. Kullanılabilir [iOS](app-protection-policy-settings-ios.md) ve [Android](app-protection-policy-settings-android.md) cihazları, bu özellik, artı bir tamsayı değeri destekler.


#### <a name="intune-device-reporting-fields----2748738---"></a>Intune cihaz alanları raporlama <!-- 2748738 -->
Intune, ek cihaz alanları, uygulama kayıt kimliği, Android üreticisi, modeli ve güvenlik düzeltme eki sürümü yanı sıra iOS model dahil olmak üzere raporlama sağlar. Intune, bu alanlar seçerek kullanılabilir **istemci uygulamaları** > **uygulama koruma durumu** seçip **uygulama koruma raporu: iOS, Android**. Bu parametreleri yapılandırma Ayrıca, yardımcı olacak **izin ver** cihaz üreticisi (Android) için liste **izin** cihaz modeli (Android ve iOS) ve en düşük Android güvenlik düzeltme eki için listesi Sürüm ayarı. 


### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="administrative-templates-are-in-public-preview-and-moved-to-their-own-configuration-profile----3322847---"></a>Yönetim Şablonları genel Önizleme aşamasındadır ve kendi yapılandırma profiline taşınır <!-- 3322847 -->

Intune Yönetim Şablonları (**cihaz Yapılandırması** > **Yönetim Şablonları**) şu anda özel Önizleme aşamasındadır. Bu güncelleştirme ile:

- Yönetim Şablonları, Intune'da yönetilebilir 300 ayarları içerir. Daha önce bu ayarlar, yalnızca Grup İlkesi Düzenleyicisi'nde vardı.
- Yönetim Şablonları genel önizlemede kullanılabilir.
- Yönetim Şablonları hareket etmesini **cihaz Yapılandırması** > **Yönetim Şablonları** için **cihaz Yapılandırması**  >   **Profilleri** > **profili oluşturma** > içinde **Platform**, seçin **Windows 10 ve üzeri** > içinde **profili tür**, seçin **Yönetim Şablonları**.
- Raporlama etkindir

Daha fazla bilgi için bu özellik hakkında Git [Grup İlkesi ayarlarını yapılandırmak için Windows 10 şablonları](administrative-templates-windows.md).

Uygulama hedefi: Windows 10 ve üzeri

#### <a name="use-smime-to-encrypt-and-sign-multiple-devices-for-a-user-----1333642---"></a>Bir kullanıcı için birden çok cihaz imzalamak ve şifrelemek için S/MIME kullan  <!-- 1333642 -->
Bu güncelleştirme, içeri aktarılmış yeni bir sertifika profili kullanan S/MIME e-posta şifrelemesi içerir (**Cihaz yapılandırması** > **Profiller** > **Profil oluşturun** > platform seçin > **PKCS içeri aktarılan sertifika** profil türü). Intune’da sertifikaları PFX biçiminde içeri aktarabilirsiniz. Intune, aynı sertifikaları tek bir kullanıcı tarafından kaydedilen birden fazla cihaza teslim edebilir. Ayrıca şunları da içerir:
- Yerel iOS e-posta profili, PFX biçiminde içeri aktarılan sertifikaları kullanan S/MIME şifrelemesini etkinleştirmeyi destekler.
- Windows Phone 10 cihazlarındaki yerel posta uygulaması, S/MIME sertifikalarını otomatik olarak kullanır.
- Özel sertifikalar, birden fazla platforma teslim edilebilir. Ancak tüm e-posta uygulamaları, S/MIME’yi desteklemez.
- Diğer platformlarda S/MIME’yi etkinleştirmek için posta uygulamasını el ile yapılandırmanız gerekebilir.  
- S/MIME şifrelemesini destekleyen e-posta uygulamaları, S/MIME e-posta şifrelemesi için sertifika alma işlemini MDM’nin destekleyemeyeceği bir şekilde halleder, ör. yayımcılarının sertifika deposundan okuma.
Bu özellik hakkında daha fazla bilgi için bkz. [imzalamak ve şifrelemek e-posta için S/MIME genel bakış](certificates-s-mime-encryption-sign.md).
Şu platformlarda desteklenir: Windows, Windows Phone 10, macOS, iOS, Android

#### <a name="new-options-to-automatically-connect-and-persist-rules-when-using-dns-settings-on-windows-10-and-later-devices----1333665-2999078---"></a>Otomatik olarak bağlanıp kuralları DNS ayarlarını Windows 10 ve üzeri cihazlarda kullanırken kalıcı hale getirmek için yeni seçenekler <!-- 1333665, 2999078 -->
Windows 10 ve üzeri cihazlarda, etki alanı, contoso.com gibi çözümlemek için DNS sunucularının bir listesini içeren bir VPN yapılandırma profili oluşturabilirsiniz. Bu güncelleştirme, ad çözümlemesi için yeni ayarları içerir (**cihaz Yapılandırması** > **profilleri** > **profili oluşturma** > Seç **Windows 10 ve üzeri** Platform > Seç **VPN** profil türü için > **DNS ayarlarını** >**Ekle**): 
- **Otomatik olarak bağlan**: Zaman **etkin**, bir cihaz, girin, örneğin contoso.com etki alanı ile iletişim kurarken cihaz VPN otomatik olarak bağlanır.
- **Kalıcı**: Bu VPN profili kullanarak cihaz bağlı olduğu sürece varsayılan olarak, tüm ad çözümleme İlkesi tablosu (NRPT) kuralları etkindir. Bu ayar olduğunda **etkin** bile VPN kesildiğinde bir NRPT kuralı kural cihazda etkin kalır. VPN profili kaldırılana veya kural manuel olarak kaldırılana kadar yapılabilir kadar kural kalır PowerShell kullanarak.
[Windows 10 VPN ayarları](vpn-settings-windows-10.md) ayarlar açıklanmaktadır. 

#### <a name="use-trusted-network-detection-for-vpn-profiles-on-windows-10-devices----1500165---"></a>Windows 10 cihazlarda VPN profilleri için güvenilen Ağ algılama kullanın <!-- 1500165 -->
Güvenilen ağ algılama kullanırken, VPN profilleri kullanıcı zaten güvenilen bir ağda olduğunda otomatik olarak bir VPN bağlantısı oluşturmasını engelleyebilirsiniz. Bu güncelleştirmeyle Windows 10 ve üstünü çalıştıran cihazlarda güvenilen Ağ algılama etkinleştirmek için DNS son eklerini ekleyebilirsiniz (**cihaz Yapılandırması** > **profilleri**  >  **Profil oluşturma** > **Windows 10 ve üzeri** Platform > **VPN** profil türü için).
[Windows 10 VPN ayarları](vpn-settings-windows-10.md) geçerli VPN ayarlarını listeler.

#### <a name="manage-windows-holographic-for-business-devices-used-by-multiple-users----1907917-1063203---"></a>Birden çok kullanıcı tarafından kullanılan cihazları Windows Holographic for Business ' ı yönetme <!-- 1907917, 1063203 -->
Şu anda, paylaşılan bilgisayar ayarlarını Windows 10 ve Windows Holographic for Business cihazlar kullanarak özel bir OMA-URI ayarı yapılandırabilirsiniz. Bu güncelleştirmeyle, paylaşılan cihaz ayarları yapılandırmak için yeni bir profil eklenir (**cihaz Yapılandırması** > **profilleri** > **profili oluştur**  >  **Windows 10 ve üzeri** > **paylaşılan çok kullanıcılı cihaz**).
Bu özellik hakkında daha fazla bilgi için şuraya gidin [paylaşılan cihazları yönetmek için Intune ayarları](shared-user-device-settings.md).
Uygulama hedefi: Windows 10 ve üzeri, Windows Holographic for Business

#### <a name="new-windows-10-update-settings---2626030--2512994----"></a>Yeni Windows 10 güncelleştirme ayarları <!--2626030  2512994  -->
İçin [Windows 10 güncelleştirme halkaları](windows-update-for-business-configure.md), yapılandırabilirsiniz:
- **Otomatik Güncelleştirme davranışı** -yeni bir seçenek kullanın *Varsayılana Sıfırla* özgün otomatik güncelleştirme ayarları bir Windows 10 çalıştıran makineleri makinede geri *Ekim 2018 güncelleştirmesi*
- **Kullanıcıyı engelle duraklatma Windows Update'ten** -yapılandırma ayarı güncelleştirmeleri engellemek ya da kullanıcılarınızın duraklatma güncelleme yüklemesinden olanak sağlar, yeni bir yazılım *ayarları* makinelerinin. 

#### <a name="ios-email-profiles-can-use-smime-signing-and-encryption----2662949---"></a>iOS e-posta profilleri, S/MIME imzalama ve şifreleme kullanabilirsiniz. <!-- 2662949 -->
Farklı ayarları içeren bir e-posta profili oluşturabilirsiniz. Bu güncelleştirme, S/MIME imzalama ve iOS cihazlarında e-posta iletişimleri şifrelemek için kullanılan ayarları içerir (**cihaz Yapılandırması** > **profilleri**  >  **Profil oluşturma** > Seç **iOS** Platform > **e-posta** profil türü için).
[iOS e-posta yapılandırma ayarları](email-settings-ios.md) ayarlar listelenir.

#### <a name="some-bitlocker-settings-support-windows-10-pro-edition---2727036---"></a>Windows 10 Pro sürümü bazı BitLocker ayarları desteği<!-- 2727036 -->
Endpoint protection ayarları BitLocker dahil olmak üzere Windows 10 cihazlarda ayarlar bir yapılandırma profili oluşturabilirsiniz. Bu güncelleştirme, Windows 10 Professional edition bazı BitLocker ayarları için destek ekler. Bu koruma ayarlarını görmek için Git [Windows 10 için Endpoint protection ayarları](endpoint-protection-windows-10.md#windows-encryption).

#### <a name="shared-device-configuration-is-renamed-to-lock-screen-message-for-ios-devices-in-the-azure-portal---2809362---"></a>Azure portalında iOS cihazları için paylaşılan cihaz yapılandırması kilit ekranı iletisi için yeniden adlandırılır<!-- 2809362 -->
İOS cihazları için bir yapılandırma profili oluşturduğunuzda, ekleyebileceğiniz **paylaşılan cihaz Yapılandırması** kilit ekranında belirli bir metin göstermek için ayarları. Bu güncelleştirme aşağıdaki değişiklikleri içerir: 
- **Paylaşılan cihaz Yapılandırması** ayarları Azure portalında "(yalnızca denetimli) kilit ekranı iletisi için" yeniden adlandırılmış (**cihaz Yapılandırması** > **profilleri**  >  **Profili oluşturma** > Seç **iOS** platformuna yönelik > Seç **cihaz özellikleri** profil türü için > **Kilitle Ekran ileti**).
- Kilit ekranı iletileri eklerken, seri numarası, cihaz adı veya başka bir cihaza özgü değer bir değişken olarak ekleyebilirsiniz **varlık etiketi bilgileri** ve **kilit ekranı dipnotu**. Örneğin, girdiğiniz `Device name: {{devicename}}` veya `Serial number is {{serialnumber}}` süslü ayraçlar kullanarak. [iOS belirteçleri](app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) kullanılabilecek kullanılabilir belirteçler listeler.
[Kilit ekranında iletilerin gösterilmesi için ayarları](shared-device-settings-ios.md) ayarlar listelenir.

#### <a name="new-app-store-doc-viewing-gaming-device-restriction-settings-added-to-ios-devices----2827760--"></a>Yeni App Store, belge görüntüleme, oyun cihaz kısıtlama ayarları iOS cihazlarına eklendi <!-- 2827760-->
İçinde **cihaz Yapılandırması** > **profilleri** > **profili oluşturma** > **iOS** için Platform > **cihaz kısıtlamaları** profil türü için > **App Store, belge görüntüleme, oyun**, aşağıdaki ayarlar eklendi: Kişiler yönetilmeyen kişiler hesapları bu ayarları görmek için Git, yönetilen kişiler hesaplarından okumak için izin yönetilmeyen uygulamaları yazmak yönetilen uygulamalar izin [iOS cihaz kısıtlamaları](device-restrictions-ios.md#app-store-doc-viewing-gaming).

#### <a name="new-notification-hints-and-keyguard-settings-to-android-enterprise-device-owner-devices----3201839-3201843---"></a>Android Kurumsal cihaz sahibi cihazlar için yeni bildirim, ipuçları ve tuş korumasını ayarları <!-- 3201839 3201843 -->
Bu güncelleştirme, cihaz sahibi olarak çalıştırırken Android Kurumsal cihazlarda çeşitli yeni özellikler içerir. Bu özellikleri kullanmak için Git **cihaz Yapılandırması** > **profilleri** > **profili oluşturma** > içinde **platformu**, seçin **Android Kurumsal** > içinde **profil türü**, seçin **yalnızca cihaz sahibi** > **cihaz Kısıtlamaları**.
Yeni özellikler içerir: 
- Gösteren gelen çağrıları, sistem uyarıları, sistem hataları ve daha fazlası dahil olmak üzere, sistem bildirimleri devre dışı bırak
- Başlangıç öğreticileri ve ilk kez açan uygulamalar için ipuçları Atla önerir
- Gelişmiş Tuş korumasını ayarlarını devre dışı bırakmak, kamera, bildirimler gibi parmak iziyle kilit açma ve ayarları görmek için daha fazla Git [Android Kurumsal cihaz kısıtlama ayarları](device-restrictions-android-for-work.md).

#### <a name="android-enterprise-device-owner-devices-can-use-always-on-vpn-connections----3202194---"></a>Android Kurumsal cihaz sahibi cihazlar her zaman açık VPN bağlantıları kullanabilirsiniz. <!-- 3202194 -->
Bu güncelleştirmede Android Kurumsal cihaz sahibi cihazlarda her zaman açık VPN bağlantıları kullanabilirsiniz. Her zaman açık VPN bağlantıları; kullanıcı cihazının kilidini açtığında, cihaz yeniden başlatıldığında veya kablosuz ağ değiştiğinde bağlı kalır veya hemen tekrar bağlanır. Bağlantıyı “kilitli”moduna da alabilirsiniz, böylece VPN bağlantısı etkin olana kadar tüm ağ trafiği engellenir.
Her zaman açık VPN etkinleştirebilirsiniz **cihaz Yapılandırması** > **profilleri** > **profili oluşturma**  >   **Android Kurumsal** Platform > **cihaz kısıtlamaları** yalnızca cihaz sahibi > **bağlantı** ayarları. Ayarları görmek için Git [Android Kurumsal cihaz kısıtlama ayarları](device-restrictions-android-for-work.md).

#### <a name="new-setting-to-end-processes-in-task-manager-on-windows-10-devices----3285177---"></a>Yeni Windows 10 cihazlarında Görev Yöneticisi'nde son işlemler için ayarlama <!-- 3285177 --> 
Bu güncelleştirme, Windows 10 cihazlarda Görev Yöneticisi'ni kullanarak işlemleri sonlandırmak için yeni bir ayar içerir. Bir cihaz yapılandırma profili kullanarak (**cihaz Yapılandırması** > **profilleri** > **profili oluşturma** > içinde **platformu** , seçin **Windows 10** > içinde **profil türü**, seçin **cihaz kısıtlamaları** > **genel** ayarları), izin verme veya engelleme bu ayarı seçin.
Bu ayarları görmek için Git [Windows 10 cihaz kısıtlama ayarları](device-restrictions-windows-10.md).
Uygulama hedefi: Windows 10 ve üzeri


### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="more-detailed-enrollment-restriction-failure-messaging----3111564---"></a>Daha ayrıntılı kayıt kısıtlama hata iletileri <!-- 3111564 -->
Daha ayrıntılı hata iletileri, kayıt kısıtlamaları karşılanmadı seçtiğinizde kullanılabilir. Bu iletileri görmek için Git **Intune** > **sorun giderme** > ve kayıt hataları tabloyu gözden geçirin. Daha fazla bilgi için [kayıt hatalarının listesi](help-desk-operators.md#configuration-policies-reference).



### <a name="monitor-and-troubleshoot"></a>İzleme ve sorun giderme

#### <a name="tenant-status-dashboard-----1124854---"></a>Kiracı durumu Panosu  <!-- 1124854 -->
Yeni [Kiracı durumu sayfası](tenant-status.md) görüntüleyebileceğiniz durumu ve ilgili ayrıntıları kiracınız için tek bir konum sağlar.  Pano dört alana ayrılır:
- **Kiracı ayrıntıları** -Kiracı adı ve konumu içeren daha fazla bilgi görüntüler MDM yetkilinizi toplam kayıtlı cihazlara kiracınızdaki ve lisansınızı sayar. Bu bölümde, kiracınız için geçerli hizmet sürümü de listelenir.
- **Bağlayıcı durumu** -yapılandırdıysanız ve ayrıca hangi henüz etkin listeleyebilirsiniz kullanılabilir bağlayıcılar hakkında daha fazla bilgi görüntüler.  
   Her bağlayıcı geçerli durumuna bağlı olarak, bunlar sağlıklı, uyarı veya sağlıksız işaretlenir. Detaylandırma ve ayrıntıları görüntülemek veya daha fazla bilgi için bu yapılandırma için bir bağlayıcı seçin.
-  **Intune hizmet durumu** -kiracınız için etkin olaylar veya kesinti ayrıntılarını görüntüler. Bu bölümdeki bilgiler, Office ileti Merkezi'nden doğrudan alınır.
-  **Intune haber** -kiracınız için etkin bir ileti görüntüler. Kiracınıza en yeni Intune özellikleri aldığında, iletileri bildirimleri gibi şeyleri içerir.  Bu bölümdeki bilgiler, Office ileti Merkezi'nden doğrudan alınır.

#### <a name="new-help-and-support-experience-in-company-portal-for-windows-10----1488939--"></a>Yeni Yardım ve destek deneyimi Windows 10 için Şirket portalı <!-- 1488939-->
Yeni Şirket portalı Yardım ve Destek sayfasında ilgili sorunları gidermek ve uygulama ve erişim sorunları için yardım iste kullanıcılara yardımcı olur. Yeni sayfasından, hata ve tanılama günlüğü ayrıntıları e-posta ve kuruluşun Yardım Masası ayarıntılarını bulun. Bunlar, bir SSS bölümü ile ilgili Intune belgelerine bağlantılar da bulabilirsiniz. 

#### <a name="new-help-and-support-experience-for-intune------3307080---"></a>Intune için yeni Yardım ve destek deneyimi   <!-- #3307080 -->
Yeni Yardım ve destek deneyimi görmek için tüm kiracılar sonraki birkaç gün içinde görüşlerine sunuyoruz. Bu yeni deneyim, Intune için kullanılabilir ve Intune dikey pencerelerinde kullanırken erişilebilir [Azure portalında](https://portal.azure.com/).
Yeni deneyim, sorununuzu kendi kelimelerinizle açıklamanıza ve sorun giderme içgörüleri ile Web tabanlı düzeltme içeriği almanıza olanak tanır. Bu çözümler sunulan bir kural tabanlı makine öğrenme algoritmasına, kullanıcı tarafından Yönetilen vazgeçilmez. Sorun özgü yönergeler ek olarak, e-posta veya telefon ile bir destek olayı açmak için yeni durum oluşturma iş akışı kullanın. Bu yeni deneyim, önceki Yardım ve destek deneyimi, Yardım ve Destek açtığınızda olan alan konsolunun dayalı önceden seçili seçenekler statik bir kümesini değiştirir. Daha fazla bilgi için [Intune için destek alma](get-support.md).

### <a name="role-based-access-control"></a>Rol tabanlı erişim denetimi

#### <a name="scope-tags-for-apps----1081941---"></a>Uygulamalar için kapsam etiketleri <!-- 1081941 -->
Rolleri ve uygulamalar için erişimi sınırlandırmak için kapsamı etiketleri oluşturabilirsiniz. Böylece kişiler de bu kapsam etiketi atanan rollerle yalnızca uygulama erişimi için bir uygulama bir kapsam etiketi ekleyebilirsiniz. Apple Volume Purchase Program (VPP) kullanarak satın aldığınız uygulamaları, kapsam etiketleri atanamaz.  Daha fazla bilgi için [kapsam etiketleri filtresi ilkeleri kullanan](scope-tags.md).



## <a name="week-of-december-10-2018"></a>10 Aralık 2018 haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="updates-for-application-transport-security----748318---"></a>Uygulama taşıma güvenliği için güncelleştirmeler <!-- 748318 -->

Aktarım Katmanı Güvenliği (Intune, varsayılan olarak daha güvenli olduğundan emin olun ve Microsoft Office 365 gibi diğer Microsoft hizmetleriyle hizalamak için sınıfının en iyisi şifreleme sağlamak için TLS) 1.2 + Intune destekler. Bu gereksinimi karşılamak için iOS ve macOS Şirket portalı, TLS 1.2 + gerektiren Apple'nın güncelleştirilmiş uygulama taşıma güvenliği (ATS) gereksinimleri zorlar. ATS, HTTPS üzerinden yapılan tüm uygulama iletişimlerinde daha sıkı güvenlik uygulamak için kullanılır. Bu değişiklik, iOS ve macOS Şirket portalı uygulamaları kullanan Intune müşterilerini etkiler. Daha fazla bilgi için [Intune destek blogu](https://aka.ms/compportalats).

#### <a name="the-intune-app-sdk-will-support-256-bit-encryption-keys----1832174---"></a>Intune uygulama SDK'sı, 256 bit şifreleme anahtarları destekleyecek <!-- 1832174 -->
Şifreleme uygulama koruma ilkeleri tarafından etkinleştirilmişse Android için Intune uygulama SDK'sı artık 256 bit şifreleme anahtarları kullanır. SDK'sı, 128 bit anahtar içeriği ve eski SDK sürümleri kullanan uygulamalar ile uyumluluk için destek sağlamak üzere devam eder.

### <a name="microsoft-auto-update-version-450-required-for-macos-devices----3503442---"></a>Microsoft otomatik güncelleştirme sürümü macOS cihazlar için gereken 4.5.0 <!-- 3503442 -->
Şirket portalı ve diğer Office uygulamaları için güncelleştirmeleri almaya devam etmek için Intune tarafından yönetilen macOS cihazları için Microsoft otomatik güncelleştirme 4.5.0 yükseltmeniz gerekir. Kullanıcılar bu sürümü, Office uygulamaları için zaten sahip olabilirsiniz.

### <a name="intune-requires-macos-1012-or-later----2827778---"></a>Intune, macOS 10.12 veya üzerini gerektirir. <!-- 2827778 -->
Intune artık macOS 10.12 veya sonraki bir sürümü gerektirir. Önceki macOS sürümlerini kullanarak cihazlarını Intune'a kaydetmek için Şirket portalı kullanamazsınız. Destek Yardımı ve yeni özellikleri almak için kullanıcıların macOS 10.12 veya üzeri için cihazını yükseltmeyi ve Şirket portalı en son sürüme yükseltin.

## <a name="week-of-november-26-2018"></a>26 Kasım 2018 haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="uninstalling-apps-on-corporate-owned-supervised-ios-devices----1281677---"></a>Şirkete ait, denetimli iOS cihazlarından uygulamaları kaldırma <!-- 1281677 -->

Şirkete denetimli iOS cihazlarında herhangi bir uygulamayı kaldırabilirsiniz. **Kaldırma** atama türüyle kullanıcı veya cihaz gruplarını hedefleyerek herhangi bir uygulamayı kaldırabilirsiniz. Kişisel veya denetimsiz iOS cihazlarında yalnızca Intune kullanarak yüklenen uygulamaları kaldırabilirsiniz.

#### <a name="downloading-intune-win32-app-content----2617320---"></a>Intune Win32 uygulama içeriği indiriliyor <!-- 2617320 -->
Windows 10 RS3 ve üzerindeki istemciler Windows 10 istemci üzerinde bir teslim iyileştirme bileşenini kullanarak Intune Win32 uygulama içeriği karşıdan yükler. Teslim iyileştirme, varsayılan olarak açık eşler arası işlevsellik sağlar. Dağıtım iyileştirme Grup İlkesi ve gelecek Intune MDM aracılığıyla yapılandırılabilir Daha fazla bilgi için [Windows 10 için teslim iyileştirme](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization). 

#### <a name="end-user-device-and-app-content-menu----2771453---"></a>Son kullanıcı cihaz ve uygulama içeriği menüsü <!-- 2771453 -->
Son kullanıcılar artık bağlam menüsü üzerinde cihaz ve uygulamaları bir cihazı yeniden adlandırma ya da uyumluluk denetimi gibi yaygın eylemleri tetiklemek için kullanabilirsiniz.

#### <a name="set-custom-background-in-managed-home-screen-app-----3041945---"></a>Yönetilen Giriş Ekranı uygulamasında özel arka plan ayarlama  <!-- 3041945 -->
Arka plan Android kuruluş, birden çok uygulamalı bilgi noktası modu cihazlarına giriş ekranı yönetilen uygulamayı özelleştirme olanak sağlayan bir ayar ekliyoruz.  **Özel URL arka planı**’nı yapılandırmak için Azure portalı > Cihaz yapılandırması’ndaki Intune’a gidin. Geçerli cihaz yapılandırma profilini seçin veya bilgi noktası ayarlarını yapılandırmak için yeni profil oluşturun.
Bilgi noktası ayarları görmek için bkz: [Android Kurumsal cihaz kısıtlamaları](device-restrictions-android-for-work.md).

#### <a name="app-protection-policy-assignment-save-and-apply----3104570---"></a>Uygulama koruma ilkesi atamasını kaydetme ve uygulama <!-- 3104570 -->
Artık daha iyi üzerinde denetiminiz, [uygulama koruma ilke atamalarını](app-protection-policies.md#deploy-a-policy-to-users). Seçtiğinizde, *atamaları* ayarlamak veya bir ilke atamalarını düzenlemek için **Kaydet** değişikliği uygulamadan önce yapılandırma. Kullanım **at** tüm değişiklikleri temizlemek için dahil etme için değişiklikleri kaydetmeden yaptığınız veya dışlama listeler.  Gerektiren kaydetme veya atma tarafından bir uygulama koruma ilkesi yalnızca düşündüğünüz kullanıcılara atanır.

#### <a name="new-microsoft-edge-browser-settings-for-windows-10-and-later----3174639---"></a>Windows 10 ve üzeri için yeni Microsoft Edge tarayıcı ayarları <!-- 3174639 -->
Bu güncelleştirme denetimi yardımcı olmak ve cihazlarınızın Microsoft Edge tarayıcısı yönetmek için yeni ayarları içerir. Bu ayarların listesi için bkz. [(ve üzeri) için Windows 10 cihaz kısıtlama](device-restrictions-windows-10.md#microsoft-edge-browser).

#### <a name="new-apps-support-with-app-protection-policies----3330037---"></a>Yeni uygulamaları ile uygulama koruma ilkelerini destekler <!-- 3330037 -->
Artık aşağıdaki uygulamaları ile yönetebileceğiniz [Intune uygulama koruma ilkeleri](app-protection-policies.md):
- Stream (iOS)
- YAPILACAKLAR (Android, iOS)
- PowerApps (Android, iOS)
- Akış (Android, iOS)

Kurumsal veri ve kontrol veri aktarımı için Intune ilkeyle yönetilen diğer uygulamalar gibi bu uygulamaları korumak için uygulama koruma ilkelerini kullanın. Not: Akış henüz konsolda görünür değilse, oluşturduğunuzda veya düzenlediğinizde akış ve uygulama koruma ilkeleri eklersiniz. Bunu yapmak için **+ daha fazla uygulama** seçeneğini ve ardından belirtin *uygulama kimliği* giriş alanını akış. Android kullanım için *com.microsoft.flow*, ve iOS kullanımı için *com.microsoft.procsimo*.


### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="ios-and-macos-version-numbers-and-build-numbers-are-shown----1892471---"></a>iOS ve macOS sürüm numaraları ve derleme numaraları gösterilir <!-- 1892471 -->
**Cihaz uyumluluğu** > **Cihaz uyumluluğu**’nda iOS ve macOS işletim sistemi sürümleri gösteriliyor ve uyumluluk ilkelerinde kullanılabilir durumda. Bu güncelleştirme içerir, her iki platform için yapılandırılabilir derleme numarası.
Güvenlik güncelleştirmeleri kullanıma sunulduğunda Apple genellikle sürüm numarasını olduğu gibi bırakır ancak derleme numarasını güncelleştirir. Bir uyumluluk ilkesinde derleme numarasını kullanarak güvenlik açığı güncelleştirmesinin yüklenip yüklenmediğini kolayca denetleyebilirsiniz.
Bu özelliği kullanmak için bkz: [iOS](compliance-policy-create-ios.md#device-health) ve [macOS](compliance-policy-create-mac-os.md#device-properties) uyumluluk ilkeleri.

#### <a name="update-rings-are-being-replaced-with-delivery-optimization-settings-for-windows-10-and-later----2753807---"></a>Teslim iyileştirme ayarları ile Windows 10 ve üzeri için güncelleştirme halkaları değiştirildi <!-- 2753807 -->
Teslim iyileştirme Windows 10 ve üzeri için yeni bir yapılandırma profili ' dir. Bu özellik, kuruluşunuzdaki cihazlara yazılım güncelleştirmeleri iletmek için daha kolaylaştırılmış bir deneyim sunar. Bu güncelleştirme ayrıca ayarları içinde bir yapılandırma profili kullanarak yeni ve var olan güncelleştirme halkaları sunmanıza yardımcı olur.
Teslim iyileştirme yapılandırma profili yapılandırmak için bkz [Windows 10 (ve üzeri) delivery optimization ayarları](delivery-optimization-windows.md).

#### <a name="new-device-restriction-settings-added-to-ios-and-macos-devices----2827760---"></a>İOS ve macOS cihazları için eklenen yeni cihaz kısıtlama ayarları <!-- 2827760 -->
Bu güncelleştirme ile iOS 12 yayımlanan iOS ve macOS cihazları için yeni ayarları içerir:

**iOS ayarları**: 
- Genel: Blok uygulama kaldırma (yalnızca denetimli)
- Genel: Blok USB kısıtlı modu (yalnızca denetimli)
- Genel: Zorla otomatik tarih ve saat (yalnızca denetimli)
- Parola: Blok parola otomatik doldurma (yalnızca denetimli)
- Parola: (Yalnızca denetimli) parola yakınlık isteklerini engelleyin
- Parola: (Yalnızca denetimli) parola Paylaşımı Engelle

**macOS ayarları**: 
- Parola: Blok parola otomatik doldurma
- Parola: Parola yakınlık isteklerini engelleyin
- Parola: Parola Paylaşımı Engelle

Bu ayarlar hakkında daha fazla bilgi için bkz: [iOS](device-restrictions-ios.md) ve [macOS](device-restrictions-macos.md) cihaz kısıtlama ayarları.

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="select-apps-tracked-on-the-enrollment-status-page---2531007---"></a>Kayıt Durumu Sayfasıda izlenen uygulamaları seçme <!-- 2531007 -->
Hangi uygulamaların kayıt durumu sayfasında izlenen seçebilirsiniz. Bu uygulamalar yüklenene kadar kullanıcı cihazı kullanamaz. Daha fazla bilgi için [ayarlama bir kayıt durumu sayfası](windows-enrollment-status.md).

#### <a name="search-for-autopilot-device-by-serial-number---2595788---"></a>Autopilot cihaz seri numarasına göre ara <!--2595788 -->
Artık, Autopilot cihazları seri numarasına göre arayabilirsiniz. Bunu yapmak için **cihaz kaydı** > **Windows kayıt** > **cihazları** > bir seri numarası yazın **göre ara seri numarası** kutusu > Enter tuşuna basın.

#### <a name="track-installation-of-office-proplus---2620217---"></a>Office ProPlus yüklemesini izleme <!--2620217 -->
Kullanıcılar, yükleme işleminin ilerlemesini izleyebilirsiniz [Office ProPlus](apps-add-office365.md) kullanarak [kayıt durumu sayfası](windows-enrollment-status.md). Daha fazla bilgi için [ayarlama bir kayıt durumu sayfası](windows-enrollment-status.md).

#### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low----2237572---"></a>Süresi dolan VPP belirteci veya yetersiz Şirket portalı lisansı uyarıları <!-- 2237572 -->
Intune Şirket portalı DEP kaydı sırasında önceden sağlamak için Volume Purchase Program (VPP) kullanıyorsanız, VPP belirtecinin süresi dolmak üzere olduğunda ve Şirket portalı için lisans azalıyor uyaracaktır.

### <a name="macos-device-enrollment-program-support-for-apple-school-manager-accounts---3006133---"></a>Apple School Manager hesapları için macOS Aygıt Kayıt Programı desteği <!--3006133 -->
Intune macOS cihazları için Apple School Manager hesabı cihaz kayıt programı kullanarak destekler.  Daha fazla bilgi için [Apple School Manager ile macOS cihazlara veya cihaz kayıt programı otomatik olarak kaydetme](device-enrollment-program-enroll-macos.md).

### <a name="new-intune-device-subscription-sku---3312071--"></a>Yeni Intune cihaz Aboneliği SKU <!--3312071-->
Kuruluşlarda cihaz yönetim maliyetini düşürmeye yardımcı olmak için yeni, cihaz tabanlı bir abonelik SKU’su kullanıma sunulmuştur. Bu Intune cihaz SKU’su cihaz başına aylık olarak lisanslandırılır. Fiyat ise lisanslama programına göre değişir. Office Yönetim Portalı aracılığıyla doğrudan ve aracılığıyla kullanılabilir [Kurumsal Anlaşma](https://www.microsoft.com/licensing/licensing-programs/enterprise?activetab=enterprise-tab:primaryr2) (EA) [Microsoft Products and Services sözleşmesi](https://www.microsoft.com/licensing/mpsa/default) (MPSA) [Microsoft açık anlaşmaları ](https://partner.microsoft.com/licensing/licensing-agreements), ve [bulut çözümü sağlayıcısı](https://www.microsoftpartnercommunity.com/t5/Partnership-101/What-is-the-Cloud-Solution-Provider-CSP-program/td-p/2453) (CSP).

### <a name="device-management"></a>Cihaz yönetimi

#### <a name="temporarily-pause-kiosk-mode-on-android-devices-to-make-changes----3041935---"></a>Değişiklikleri yapmak için Android cihazlarda bilgi noktası modunu geçici olarak duraklatma <!-- 3041935 -->
Android cihazlarını çok uygulamalı bilgi noktası modunda kullanırken bir BT uzmanının cihazda değişiklikler yapması gerekebilir. Bu güncelleştirme, geçici olarak bilgi noktası modu bir PIN kullanarak duraklatmak ve cihazın tamamını erişmek bir BT yöneticisi izin veren yeni çoklu uygulama bilgi noktası ayarları içerir.
Bilgi noktası ayarları görmek için bkz: [Android Kurumsal cihaz kısıtlamaları](device-restrictions-android-for-work.md).

#### <a name="enable-virtual-home-button-on-android-enterprise-kiosk-devices-----3042021---"></a>Android Kurumsal bilgi noktası cihazlarında sanal giriş düğmesini etkinleştirme  <!-- 3042021 -->
Yeni bir ayar, kullanıcıların Yönetilen Giriş Ekranı uygulaması ve çok uygulamalı bilgi noktası cihazlarındaki diğer atanan uygulamalar arasında bir yazılım tuşuna dokunarak geçiş yapmalarını sağlar. Bu ayar, özellikle kullanıcının bilgi noktası uygulaması “geri” düğmesine uygun şekilde yanıt vermediği durumlarda yararlı olur. Bu ayarı şirkete ait, tek kullanımlı Android cihazlarında yapılandırabilirsiniz. **Sanal giriş düğmesi**’ni etkinleştirmek veya devre dışı bırakmak için Azure portalı > Cihaz yapılandırması’ndaki Intune’a gidin. Geçerli cihaz yapılandırma profilini seçin veya bilgi noktası ayarlarını yapılandırmak için yeni profil oluşturun.
Bilgi noktası ayarları görmek için bkz: [Android Kurumsal cihaz kısıtlamaları](device-restrictions-android-for-work.md).

## <a name="week-of-november-12-2018"></a>12 Kasım 2018 haftası

### <a name="network-access-control-nac-support-for-citrix-sso-for-ios----3259404---"></a>İOS için Citrix SSO için erişim denetimi (NAC) desteği ağ <!-- 3259404 -->

Citrix Citrix Citrix SSO için ağ erişim denetimi (NAC) ıntune iOS izin vermek için ağ geçidi için bir güncelleştirme yayımladı. Intune'da bir cihaz kimliği bir VPN profili içinde dahil kabul etmek ve ardından bu profili iOS cihazlarınıza gönderin. Citrix bu işlevselliği kullanmak için ağ geçidi için en son güncelleştirmesini yüklemeniz gerekir.

[İOS cihazlarında VPN ayarlarını yapılandırma](vpn-settings-ios.md#base-vpn-settings) NAC, bazı ek gereksinimleri de dahil olmak üzere kullanma hakkında daha fazla bilgi sağlar. 

## <a name="week-of-november-5-2018"></a>5 Kasım 2018 Haftası

### <a name="support-for-ios-12-oauth-in-ios-email-profiles---2155106---"></a>iOS e-posta profillerinde iOS 12 OAuth için destek <!--2155106 -->

Intune’un iOS e-posta profilleri, iOS 12 Open Authorization (OAuth) standardını destekliyor. Bu özelliği görmek için yeni bir profil oluşturun (platform olarak **Cihaz Yapılandırması** > **Profiller** > **Profil oluştur** > **iOS** > platform için > **E-posta** profil türü için) veya mevcut bir iOS e-posta profilini güncelleştirin. Kullanıcılara dağıtılmış olan bir profilde OAuth etkinleştirirseniz, kullanıcılardan tekrar kimlik doğrulaması yapmaları ve e-postalarını tekrar indirmeleri istenir.

[iOS e-posta profilleri](email-settings-ios.md) makalesinde bir e-posta profilinde OAuth kullanma hakkında daha fazla bilgi vardır.

### <a name="autopilot-support-for-hybrid-azure-active-directory-joined-devices-preview----1048100--"></a>Karma Azure Active Directory’ye katılmış olan cihazlar için Autopilot desteği (Önizleme) <!-- 1048100-->
Artık karma Azure Active Directory’ye katılmış olan cihazları Autopilot kullanarak ayarlayabilirsiniz. Hibrit Autopilot özelliğini kullanmak için cihazların kuruluşunuzun ağına katılmış olması gerekir. Daha fazla bilgi için bkz. [Karma Azure Active Directory’ye katılmış olan cihazları Intune ve Windows Autopilot kullanarak dağıtma](windows-autopilot-hybrid.md).
Bu özellik, kullanıcı tabanının kullanımına gelecek birkaç gün içinde sunulacaktır. Bu nedenle, bu özellik hesabınız için kullanılabilir olana kadar bu adımları uygulayamayabilirsiniz.

## <a name="week-of-october-29-2018"></a>29 Ekim 2018 haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="require-non-biometric-pin-after-a-specified-timeout----1506985---"></a>Belirtilen zaman aşımından sonra biyometrik olmayan PIN gerektirme <!-- 1506985 -->
Intune, yöneticinin belirttiği zaman aşımından sonra biyometrik olmayan bir PIN gerektirir, böylece şirket verilerine erişim için biyometrik tanımlama kullanımını kısıtlama yoluyla Mobil Uygulama Yönetimi’nin (MAM) etkinleştirildiği uygulamalarda gelişmiş güvenlik sağlar. Bu ayar, APP/MAM etkin uygulamalara erişmek için Touch ID (iOS), Face ID (iOS), Android Biometric, veya geleceğin diğer kimlik doğrulama yöntemlerinden yararlanan kullanıcıları etkiler. Bu ayarlar, birden çok parmak izine veya başka biyometrik erişim yöntemlerine sahip bir cihazın şirket verilerini yanlış kullanıcıya gösterebildiği durumları ortadan kaldırarak, Intune yöneticilerinin kullanıcı erişimi üzerinde daha ayrıntılı denetim sahibi olmasına olanak tanır. Azure portalında **Microsoft Intune**'u açın. **İstemci uygulamaları** > **Uygulama koruma ilkeleri** > **İlke ekle** > **Ayarlar**’ı seçin. Belirli ayarlar için **Erişim** bölümünü bulun. Erişim ayarları hakkında daha fazla bilgi için bkz. [iOS ayarları](app-protection-policy-settings-ios.md#access-requirements) ve [Android ayarları](app-protection-policy-settings-android.md#access-requirements).

#### <a name="intune-app-data-transfer-settings-on-ios-mdm-enrolled-devices----2244713---"></a>iOS MDM kayıtlı cihazlarda Intune APP veri aktarımı ayarları <!-- 2244713 -->
iOS MDM kayıtlı cihazlarda Intune APP veri aktarımı ayarlarının denetimini, kayıtlı kullanıcının kimliğini (Kullanıcı Asıl Adı (UPN) olarak da bilinir) belirtme işleminden ayrı tutabilirsiniz. IntuneMAMUPN kullanmayan yöneticiler, davranış değişikliği gözlemlemeyecektir. Bu işlev kullanılabilir olduğunda, kayıtlı cihazlarda veri aktarımı davranışını denetlemek için IntuneMAMUPN kullanan yöneticiler yeni ayarları gözden geçirmeli ve APP ayarlarını gerektiği gibi güncelleştirmelidir.

#### <a name="windows-10-win32-apps----2617325---"></a>Windows 10 Win32 uygulamaları <!-- 2617325 -->
Win32 uygulamalarınızı cihazdaki tüm kullanıcılar için yüklemek yerine kullanıcı bağlamında ayrı ayrı kullanıcılar için yüklenecek şekilde yapılandırabilirsiniz.

#### <a name="windows-win32-apps-and-powershell-scripts----2617330---"></a>Windows Win32 uygulamaları ve PowerShell betikleri <!-- 2617330 -->
Artık son kullanıcıların Win32 uygulamalarını yüklemek veya PowerShell betiklerini yürütmek için cihazda oturum açmış olmaları gerekmez. 

#### <a name="troubleshooting-client-app-installation----1363711---"></a>İstemci uygulaması yükleme sorunlarını giderme <!-- 1363711 -->
**Sorun giderme** dikey penceresinde **Uygulama yükleme** etiketli sütunu gözden geçirerek istemci uygulamaların yüklenmesiyle ilgili sorunları giderebilirsiniz. **Sorun giderme** dikey penceresini görüntülemek için Intune portalındaki **Yardım ve destek** bölümünün altından **Sorun giderme**’yi seçin.

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="network-access-control-support-on-ios-vpn-clients----1333693---"></a>iOS VPN istemcilerinde ağ erişim denetimi desteği <!-- 1333693 -->
Bu güncelleştirmeyle, iOS için Cisco AnyConnect, F5 Access ve Citrix SSO’ya yönelik bir VPN yapılandırma profili oluştururken Ağ Erişim Denetimini (NAC) etkinleştirmek için kullanabileceğiniz yeni bir ayar kullanıma sunuldu. Bu ayar, cihazın NAC kimliğinin VPN profiline dahil edilmesini sağlar. Şu anda bu yeni NAC kimliğini destekleyen bir VPN istemcisi veya NAC iş ortağı çözümü yok, ancak olduğunda sizi [destek blog gönderimiz](ttps://aka.ms/iOS12_and_vpn) yoluyla bilgilendireceğiz.

NAC’yi kullanmak için şunları yapmanız gerekir:
1. Intune’un cihaz kimliklerini VPN profillerine dahil etmesini seçmek
2. Doğrudan NAC sağlayıcınız tarafından sağlanan yönergelere göre NAC sağlayıcı yazılımı/ürün yazılımınızı güncelleştirmek

Bu ayarın bir iOS VPN profilindeki kullanımı hakkında bilgi için bkz. [Microsoft Intune’da iOS cihazlara VPN ayarları ekleme](vpn-settings-ios.md). Ağ erişim denetimi hakkında daha fazla bilgi için bkz. [Ağ erişim denetimini (NAC) Intune ile tümleştirme](network-access-control-integrate.md). 

Şunun için geçerlidir: iOS

#### <a name="remove-an-email-profile-from-a-device-even-when-theres-only-one-email-profile----1818139---"></a>Cihazda sadece bir e-posta profilinin olduğu durumlar dahil olmak üzere e-posta profilini kaldırma <!-- 1818139 -->
Önceden, cihazda sadece bir e-posta profilinin *olması* durumunda bu e-posta profilini cihazdan kaldırmak mümkün değildi. Bu güncelleştirme ile bu davranış değişiyor. Artık cihazdaki tek e-posta profilini bile kaldırabilirsiniz. Ayrıntılar için bkz. [Intune kullanarak cihazlara e-posta ayarları ekleme](email-settings-configure.md).

#### <a name="powershell-scripts-and-aad----2309469---"></a>PowerShell betikleri ve AAD <!-- 2309469 -->
Intune’da PowerShell betikleri AAD cihaz güvenlik gruplarına hedeflenebilir.

#### <a name="new-required-password-type-default-setting-for-android-android-enterprise---2649963---"></a>Android, Android kurumsal için yeni "Gerekli parola türü" varsayılan ayarı<!-- 2649963 -->
Yeni bir uyumluluk ilkesi oluşturduğunuzda (**Intune** > **Cihaz uyumluluğu** > **İlkeler** > **İlke oluştur** > **Android** veya Platform > Sistem Güvenliği için **Android kurumsal**), **Gerekli parola türü** varsayılan değeri değişir:

Kaynak: Cihaz varsayılanı için: En az sayısal

Uygulama hedefi: Android, Android Kurumsal

Bu ayarları görmek için [Android](compliance-policy-create-android.md) veya [Android Kurumsal](compliance-policy-create-android-for-work.md)’a gidin.

#### <a name="use-a-pre-shared-key-in-a-windows-10-wi-fi-profile----2662938---"></a>Bir Windows 10 Wi-Fi profilinde önceden paylaşılan anahtar kullanma <!-- 2662938 -->
Bu güncelleştirmeyle birlikte Windows 10’da bir Wi-Fi yapılandırma profilinin kimliğini doğrulamak için WPA/WPA2 Kişisel güvenlik protokolü ile birlikte bir önceden paylaşılan anahtar (PSK) kullanabilirsiniz. Ayrıca 10 Ekim 2018 güncelleştirmesiyle Windows 10 cihazlarda bir tarifeli ağ için maliyet yapılandırmasını da belirtebilirsiniz.

Şu anda önceden paylaşılan anahtarları kullanmak için bir Wi-Fi profilini içeri aktarmanız veya özel bir profil oluşturmanız gerekiyor. [Windows 10 için Wi-Fi ayarları](wi-fi-settings-windows.md) makalesi, geçerli ayarları listeler. 

#### <a name="remove-pkcs-and-scep-certificates-from-your-devices----3218390---"></a>Cihazlarınızdan PKCS ve SCEP sertifikalarını kaldırma <!-- 3218390 -->
Bazı senaryolarda, bir gruptan ilke kaldırılması, bir yapılandırma veya uyumluluk dağıtımının silinmesi veya mevcut SCEP veya PKCS profillerinin yönetici tarafından güncelleştirilmesi durumlarında bile PKCS ve SCEP sertifikaları cihazlarda kalıyordu. Bu güncelleştirme ile bu davranış değişiyor. PKCS ve SCEP sertifikalarının cihazda kaldığı veya bu sertifikaların cihazdan kaldırıldığı bazı senaryolar da vardır. Bu senaryolar için bkz. [Microsoft Intune’da SCEP ve PKCS sertifikalarını kaldırma](remove-certificates.md).

#### <a name="use-gatekeeper-on-macos-devices-for-compliance----2504381---"></a>macOS cihazlarda uyumluluk için Gatekeeper kullanma <!-- 2504381 -->
Bu güncelleştirme, cihazları uyumluluk açısından değerlendirmek için macOS Gatekeeper özelliğini içerir. Gatekeeper özelliğini ayarlamak için bkz. [macOS cihazlara cihaz uyumluluk ilkesi ekleme](compliance-policy-create-mac-os.md).


### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="enrollment-abandonment-report----1382924---"></a>Kayıttan vazgeçme raporu <!-- 1382924 -->
Bırakılmış kayıtların ayrıntılarını sağlayan yeni bir rapor, **Cihaz kaydı** > **İzle** altında bulunabilir. Daha fazla bilgi için bkz. [Şirket portalı bırakma raporu](enrollment-report-company-portal-abandon.md).

#### <a name="new-azure-active-directory-terms-of-use-feature----2870393---"></a>Yeni Azure Active Directory kullanım koşulları özelliği <!-- 2870393 -->
Azure Active Directory’de mevcut Intune hüküm ve koşulları yerine kullanabileceğiniz bir kullanım koşulları özelliği vardır. Azure AD kullanım koşulları özelliği, hangi koşulların ne zaman gösterileceği konusunda daha fazla esneklik, daha iyi yerelleştirme desteği, koşulların ekrana çizilmesi üzerinde daha fazla denetim ve daha iyi raporlama sağlamaktadır. Azure AD kullanım koşulları özelliği, Enterprise Mobility + Security E3 paketinin de parçası olan Azure Active Directory Premium P1'i gerektirir. Daha fazla bilgi edinmek için bkz. [Kullanıcı erişimi için şirketinizin hüküm ve koşullarını yönetme makalesi](terms-and-conditions-create.md).

#### <a name="android-device-owner-mode-support---3188762--"></a>Android Cihaz Sahibi modu desteği <!--3188762-->
Samsung Knox Mobil Kaydı için Intune artık cihazları Android Cihaz Sahibi yönetim modunda kaydetmeyi destekliyor. WiFi veya hücresel ağ kullanan kullanıcılar, cihazlarını ilk kez açtıklarında yalnızca birkaç dokunuşla kayıt yapabilir. Daha fazla bilgi için bkz. [Android cihazları Samsung’un Knox Mobil Kayıt özelliğini kullanarak otomatik kaydetme](android-samsung-knox-mobile-enroll.md).

### <a name="device-management"></a>Cihaz yönetimi
#### <a name="new-settings-for-software-updates------1907869---"></a>Yazılım güncelleştirmeleri için yeni ayarlar   <!-- 1907869 -->  
- Bazı bildirimler en son yazılım güncelleştirmeleri yüklemesini tamamlamak üzere gereken yeniden başlatma hakkında uyarı son kullanıcılara artık yapılandırabilirsiniz.   
- KCG senaryolarını destekleyen bir yeniden başlatma için uyarı istemini iş saatleri dışında gerçekleşen bir yeniden başlatma artık yapılandırabilirsiniz.

#### <a name="group-windows-autopilot-enrolled-devices-by-correlator-id----2075110---"></a>Windows Autopilot kayıtlı cihazları ilişkilendirici kimliğine göre gruplama <!-- 2075110 -->
Intune, Configuration Manager aracılığıyla [mevcut cihazlar için Autopilot](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/New-Windows-Autopilot-capabilities-and-expanded-partner-support/ba-p/260430) kullanılarak kaydedilmiş Windows cihazları ilişkilendirici kimliğine göre gruplamayı artık destekliyor. İlişkilendirici kimliği, Autopilot yapılandırma dosyasının bir parametresidir. Intune, [Azure Active Directory cihaz özniteliği enrollmentProfileName](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#using-attributes-to-create-rules-for-device-objects) değerini “OfflineAutopilotprofile-<correlator ID>” değerine eşit olacak şekilde otomatik olarak ayarlar. Bu, çevrimdışı Autopilot kayıtları için enrollmentprofileName özniteliği aracılığıyla ilişkilendirici kimliğine göre rasgele Azure AD dinamik grupları oluşturulmasına izin verir. Daha fazla bilgi için bkz. [Mevcut cihazlar için Windows Autopilot](enrollment-autopilot.md#windows-autopilot-for-existing-devices).

#### <a name="intune-app-protection-policies----2984657---"></a>Intune uygulama koruma ilkeleri <!-- 2984657 -->
Intune uygulama koruma ilkeleri, Microsoft Outlook ve Microsoft Word gibi Intune tarafından korunan uygulamalar için çeşitli veri koruma ayarlarını yapılandırmanıza olanak sağlar. Ayrı ayrı ayarların bulunmasını kolaylaştırmak için hem [iOS](app-protection-policy-settings-ios.md) hem de [Android](app-protection-policy-settings-android.md) üzerinde bu ayarların görünümünde ve işlevinde değişiklik yaptık. İlke ayarları üç kategoriye ayrılır:
- **Verileri yeniden konumlandırma** - Bu grup kesme, kopyalama, yapıştırma ve farklı kaydetme kısıtlamaları gibi veri kaybı önleme (DLP) denetimlerini içerir. Bu ayarlar, kullanıcıların uygulamalarda verilerle nasıl etkileşim kurduğunu belirler.
- **Erişim gereksinimleri** - Bu grup, son kullanıcının uygulamalara iş bağlamında nasıl eriştiğini belirleyen uygulama başına PIN seçenekleri içerir.  
- **Koşullu başlatma** - Bu grup en düşük işletim sistemi ayarları, jailbreak uygulanmış ve kök erişim izni verilmiş cihazları algılama ve çevrimdışı yetkisiz kullanım süreleri gibi ayarları içerir.  
  
Ayarların işlevselliği değişmedi, ancak ilke yazma akışında çalışırken bu ayarları bulmanız artık daha kolay.

### <a name="intune-apps"></a>Intune uygulamaları

#### <a name="intune-will-support-a-maximum-package-size-of-8-gb-for-lob-apps----1727158---"></a>Intune, LOB uygulamaları için en fazla 8 GB’lık paket boyutunu destekler<!-- 1727158 -->
Intune, İş kolu (LOB) uygulamaları için izin verilen en fazla paket boyutunu 8 GB’a yükseltti. Daha fazla bilgi için bkz. [Microsoft Intune’a uygulama ekleme](apps-add.md).

#### <a name="add-custom-brand-image-for-company-portal-app----1916266---"></a>Şirket Portalı uygulaması için özel marka resmi ekleme <!-- 1916266 -->
Microsoft Intune yöneticisi olarak, iOS Şirket Portalı uygulamasındaki kullanıcı profil sayfasında bir arka plan görüntüsü olarak kullanılacak özel bir marka görüntüsünü karşıya yükleyebilirsiniz. Şirket Portalı uygulamasını yapılandırma hakkında daha fazla bilgi için bkz. [Microsoft Intune Şirket Portalı uygulamasını yapılandırma](company-portal-app.md).

#### <a name="intune-will-maintain-the-office-localized-language-when-updating-office-on-end-users-machines----2971030---"></a>Intune, son kullanıcı makinelerinde Office'i güncelleştirirken yerelleştirilmiş Office dilini korur <!-- 2971030 -->
Intune son kullanıcı makinenize Office yüklediğinde, son kullanıcılar önceki .MSI Office yüklemeleri ile aldıkları aynı dil paketini otomatik olarak alır. Daha fazla bilgi için bkz. [Microsoft Intune ile Office 365 uygulamalarını Windows 10 cihazlara atama](apps-add-office365.md).

### <a name="monitor-and-troubleshoot"></a>İzleme ve sorun giderme

#### <a name="new-intune-support-experience-in-the-microsoft-365-device-management-portal----3076965---"></a>Microsoft 365 Cihaz Yönetim portalında yeni Intune Desteği deneyimi <!-- 3076965 -->
[Microsoft 365 Cihaz Yönetim portalında]( http://devicemanagement.microsoft.com) Intune için yeni bir Yardım ve Destek deneyimini kullanıma sunuyoruz. Yeni deneyim, sorununuzu kendi kelimelerinizle açıklamanıza ve sorun giderme içgörüleri ile Web tabanlı düzeltme içeriği almanıza olanak tanır. Bu çözümler, kullanıcı sorgularıyla şekillenen bir kural tabanlı makine öğrenimi algoritması aracılığıyla sunulur.  

Soruna özgü yönergelere ek olarak yeni olay oluşturma iş akışını kullanarak e-posta veya telefon yoluyla bir destek olayı açabilirsiniz.  

Dağıtıma dahil edilen müşteriler için bu yeni deneyim, Yardım ve Desteği açtığınızda bulunduğunuz konsol alanına dayalı, statik bir önceden belirlenmiş seçenekler kümesine yönelik geçerli Yardım ve Destek deneyiminin yerini alır.  

*Bu yeni Yardım ve Destek deneyimi, bazı kiracıların (tamamının değil) kullanımına sunulmaktadır ve Cihaz Yönetimi portalında kullanılabilir. Yeni deneyime katılacak kişiler, uygun Intune kiracıları arasından rastgele seçilir. Dağıtım kapsamı genişledikçe yeni kiracılar eklenecektir.*  

Daha fazla bilgi için [Yardım ve destek deneyimi](get-support.md#help-and-support-experience) nasıl Intune için destek alma.  

### <a name="powershell-module-for-intune--preview-available----951068---"></a>Intune için PowerShell modülü - Önizleme kullanılabilir <!-- 951068 -->
Intune API’si için Microsoft Graph yoluyla destek sağlayan yeni bir PowerShell modülü artık [GitHub]( https://aka.ms/intunepowershell)’da önizleme olarak kullanılabilir. Bu modülü kullanma hakkında daha fazla ayrıntı için modülün bulunduğu konumdaki README dosyasına bakın. 


## <a name="week-of-october-15-2018"></a>15 Ekim 2018 haftası

### <a name="pin-prompt-when-you-change-fingerprints-or-face-id-on-an-ios-device-----2637704----"></a>Bir iOS cihazda parmak izlerini veya yüz kimliğini değiştirdiğinizde PIN istemi <!-- 2637704  -->
Artık, kullanıcılar iOS cihazlarında biyometrik değişiklikler yaptığında PIN istenir. Bunlara kayıtlı parmak izleri veya yüz kimliğinde yapılan değişiklikler dahildir. İstemin zamanlaması, *(dakika) içinde erişim gereksinimlerini yeniden denetle* zaman aşımının yapılandırmasına bağlıdır.  Ayarlanmamışsa kullanıcıdan bir PIN ayarlaması istenir. 
 
Bu özellik yalnızca iOS için kullanılabilir ve iOS için Intune APP SDK’sı sürüm 9.0.1 veya üzeri sürümleri tümleştiren uygulamaların katılımını gerektirir. Hedeflenen uygulamalarda davranışın zorlanabilmesi için SDK tümleştirmesi gereklidir. Bu tümleştirme, sıralı bir şekilde gerçekleşir ve belirli uygulama ekiplerine bağımlıdır. Katılan uygulamalardan bazıları WXP, Outlook, Managed Browser ve Yammer’dır.


## <a name="week-of-october-1-2018"></a>1 Ekim 2018 haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="access-to-key-profile-properties-using-the-company-portal-app----772203---"></a>Şirket portalı uygulamasını kullanarak anahtar profil özelliklerine erişim <!-- 772203 -->
Son kullanıcılar artık parola sıfırlama gibi önemli hesap özellikleri ve eylemlerine Şirket portalı uygulamasından erişebilir. 

#### <a name="3rd-party-keyboards-can-be-blocked-by-app-settings-on-ios----1248481---"></a>iOS'ta üçüncü taraf klavyeler APP ayarlarıyla engellenebilir <!-- 1248481 -->
iOS cihazlarda Intune yöneticileri, ilke korumalı uygulamalarda kuruluş verilerine erişilirken üçüncü taraf klavyelerin kullanımını engelleyebilir. Uygulama Koruma İlkesi (APP) üçüncü taraf klavyelerini engelleyecek şekilde ayarlandığında, cihaz kullanıcısı üçüncü taraf klavyesini kullanarak şirket verileriyle ilk kez etkileşim kurarken bir ileti alır. Yerel klavye dışındaki tüm seçenekler engellenir ve cihaz kullanıcıları bunları görmez. Cihaz kullanıcıları iletişim kutusu iletisini tek bir kez görür. 

#### <a name="user-account-access-of-intune-apps-on-managed-android-and-ios-devices----1248496---"></a>Yönetilen Android ve iOS cihazlarda Intune uygulamalarına kullanıcı hesabı erişimi <!-- 1248496 -->
Microsoft Intune yöneticisi olarak yönetilen cihazlarda hangi kullanıcı hesaplarının Microsoft Office uygulamalarına eklendiğini denetleyebilirsiniz. Erişimi yalnızca izin verilen kullanıcı hesaplarıyla sınırlayabilecek ve kayıtlı cihazlarda kişisel hesapları engelleyebilirsiniz. 

#### <a name="outlook-ios-and-android-app-configuration-policy---1828527---"></a>Outlook iOS ve Android uygulama yapılandırma ilkesi <!--1828527 -->
Artık iOS ve Android’de, ActiveSync protokolüyle Temel kimlik doğrulamasından yararlanan şirket içi kullanıcılar için bir Outlook iOS ve Android uygulama yapılandırma ilkesi oluşturabilirsiniz. Ek yapılandırma ayarları, iOS ve Android için Outlook’ta etkinleştirildikçe eklenecektir.

#### <a name="office-365-pro-plus-language-packs----1833450---"></a>Office 365 Pro Plus dil paketleri <!-- 1833450 -->
Intune yöneticisi olarak, Intune aracılığıyla yönetilen Office 365 Pro Plus uygulamaları için ek dillerin dağıtımını yapabileceksiniz. Kullanılabilir diller listesi, dil paketinin **Tür** bilgisini içerir (çekirdek, kısmı ve yazım denetleme). Azure portalında **Microsoft Intune** > **İstemci uygulamaları** > **Uygulamalar** > **Ekle**’yi seçin. **Uygulama ekle** dikey penceresindeki **Uygulama türü** listesinde **Office 365 Paketi** altından **Windows 10**'u seçin. **Uygulama Paketi Ayarları** dikey penceresinde **Diller**'i seçin.

####  <a name="windows-line-of-business-lob-apps-file-extensions----1884873---"></a>Windows iş kolu (LOB) uygulamaları dosya uzantıları <!-- 1884873 -->
Windows LOB uygulamaları için dosya uzantıları artık *.msi*, *.appx*, *.appxbundle*, *.msix* ve *.msixbundle*’ı içerecek. Microsoft Intune’da, **İstemci uygulamaları** > **Uygulamalar** > **Ekle**’yi seçerek bir uygulama ekleyebilirsiniz. **Bölme ekle** bölmesi görüntülenir ve **Uygulama türünü** seçmenize olanak tanır. Windows LOB uygulamaları için uygulama türü olarak **İş kolu uygulamasını** seçin, **Uygulama paketi dosyasını** seçin ve uygun uzantıya sahip bir yükleme dosyası girin.

#### <a name="windows-10-app-deployment-using-intune----2309001---"></a>Intune kullanarak Windows 10 uygulama dağıtımı <!-- 2309001 -->
Yöneticiler, iş kolu (LOB) uygulamaları ve İş için Microsoft Store uygulamaları için mevcut destekten yararlanarak kuruluşlarındaki uygulamaların çoğunu Intune ile Windows 10 cihazlarındaki son kullanıcılara dağıtabilir. Yöneticiler, Windows 10 kullanıcıları için MSI, Setup.exe veya MSP gibi çeşitli biçimlerdeki uygulamalar ekleyebilir, yükleyebilir ve kaldırabilir. Intune, indirme ve yükleme öncesinde gereksinim kurallarını değerlendirerek, işlemin durumunu veya yeniden başlatma gereğini Windows 10 Eylem Merkezi aracılığıyla son kullanıcılara bildirebilir. Bu işlevsellik, sonuçta, bu iş yükünü Intune'a ve buluta kaydırmak isteyen kuruluşların engellemesini kaldırmış olur. Bu özellik şu anda genel önizleme aşamasındadır ve önümüzdeki birkaç ay içinde özelliğe önemli yeni olanaklar eklemeyi bekliyoruz. 

#### <a name="end-user-device-and-app-content-menu----2771453---"></a>Son kullanıcı cihaz ve uygulama içeriği menüsü <!-- 2771453 -->
Son kullanıcılar artık cihaz yeniden adlandırma veya uyumluluk denetleme gibi sık kullanılan eylemleri tetiklemek için cihazdaki açılır menüyü kullanabilir. 

#### <a name="windows-company-portal-keyboard-shortcuts----2771518---"></a>Windows Şirket Portalı klavye kısayolları <!-- 2771518 -->
Son kullanıcılar artık Windows Şirket Portalı’nda klavye kısayollarını (hızlandırıcılar) kullanarak uygulama ve cihaz eylemlerini tetikleyebilir.

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="create-dns-suffixes-in-vpn-configuration-profiles-on-devices-running-windows-10---1333668---"></a>Windows 10 çalıştıran cihazlardaki VPN yapılandırma profillerinde DNS son ekleri oluşturma<!-- 1333668 -->
Bir VPN cihaz yapılandırma profili oluşturduğunuzda (**Cihaz yapılandırması** > **Profiller** > **Profil oluştur** > **Windows 10 ve üzeri** platform > **VPN** profil türü) bazı DNS ayarları girersiniz. Bu güncelleştirme ile Intune'da birden çok **DNS soneki** de girebilirsiniz. DNS son ekleri kullanırken bir ağ kaynağını tam etki alanı adı (FQDN) yerine kısa adını kullanarak arayabilirsiniz. Bu güncelleştirme ayrıca Intune’da DNS son eklerinin sırasını değiştirmenize de imkan verir.
[Windows 10 VPN ayarları](vpn-settings-windows-10.md#dns-settings) makalesi, geçerli DNS ayarlarını listeler.
Uygulama hedefi: Windows 10 cihazlar

#### <a name="support-for-always-on-vpn-for-android-enterprise-work-profiles----1333705---"></a>Android kurumsal iş profillerinde her zaman açık VPN desteği <!-- 1333705 -->
Bu güncelleştirmede yönetilen iş profilleri olan Android kurumsal cihazlarda Her Zaman Açık VPN bağlantıları kullanabilirsiniz. Her zaman açık VPN bağlantıları; kullanıcı cihazının kilidini açtığında, cihaz yeniden başlatıldığında veya kablosuz ağ değiştiğinde bağlı kalır veya hemen tekrar bağlanır. Bağlantıyı “kilitli”moduna da alabilirsiniz, böylece VPN bağlantısı etkin olana kadar tüm ağ trafiği engellenir.
Her Zaman Açık VPN'yi platform için **Cihaz yapılandırması** > **Profiller** > **Profil oluşturma**  >  **Android kurumsal**'da > **Cihaz kısıtlamaları** > **Bağlantı** ayarlarında etkinleştirebilirsiniz.

#### <a name="issue-scep-certificates-to-user-less-devices----1744554---"></a>Kullanıcısız cihazlara SCEP sertifikaları verme <!-- 1744554 -->
Şu anda sertifikalar kullanıcılara atanmaktadır. Bu güncelleştirme ile bilgi noktaları gibi kullanıcısız olanlar da dahil olmak üzere cihazlara SCEP sertifikaları çıkarılabilir (platform için **Cihaz yapılandırması** > **Profiller** > **Profil oluştur** > **Windows 10 ve üzeri** > profil için **SCEP sertifikası**). Diğer güncelleştirmeler:
- SCEP profilindeki **Konu** özelliği, artık özel bir metin kutusundadır ve yeni değişkenler içerebilir. 
- SCEP profilindeki **Konu diğer adı (SAN)** özelliği artık tablo biçimindedir ve yeni değişkenler içerebilir. Yöneticiler tabloda bir öznitelik ekleyebilir ve değeri özel bir metin kutusunda doldurabilir. SAN, aşağıdaki öznitelikleri destekleyecek: 
  - DNS
  - E-posta adresi
  - UPN

  Bu yeni değişkenler, özel bir değer metin kutusunda statik metin ile eklenebilir. Örneğin DNS özniteliği `DNS = {{AzureADDeviceId}}.domain.com` olarak eklenebilir.

  > [!NOTE]
  > Küme ayraçları, noktalı virgül ve düz çizgi işareti “ { } ; | ” SAN statik metninde kullanılmaz. Küme ayraçları, `Subject` veya `Subject alternative name` olarak kabul edilmek için yalnızca yeni cihaz sertifika değişkenlerinden birini kapatmalıdır. 

Yeni cihaz sertifika değişkenleri:  

```
"{{AAD_Device_ID}}",
"{{Device_Serial}}",
"{{Device_IMEI}}",
"{{SerialNumber}}",
"{{IMEINumber}}",
"{{AzureADDeviceId}}",
"{{WiFiMacAddress}}",
"{{IMEI}}",
"{{DeviceName}}",
"{{FullyQualifiedDomainName}}",
"{{MEID}}",
```

> [!NOTE]
>  - `{{FullyQualifiedDomainName}}` yalnızca Windows ve etki alanına katılmış cihazlarda kullanılır. 
>  -  Bir cihaz sertifikası için konu veya SAN’da IMEI, Seri Numarası ve Tam Etki Alanı Adı gibi cihaz özellikleri belirtirken cihaza erişimi olan biri tarafından kandırma amaçlı olarak farklı özellikler verilebileceğine dikkat edin. 

[Bir SCEP sertifika profili oluşturma](certificates-scep-configure.md#create-a-scep-certificate-profile) makalesi, bir SCEP yapılandırma profili oluştururken geçerli değişkenleri listeler. 

Uygulama hedefi: Windows 10 ve üzeri ve iOS, Wi-Fi için desteklenir

#### <a name="remotely-lock-uncompliant-devices----2064495---"></a>Uyumsuz cihazları uzaktan kilitleme <!-- 2064495 -->
Cihazın uyumlu olmadığı durumlarda, uyumluluk ilkesinde cihazı uzaktan kilitleyen bir eylem oluşturabilirsiniz. Intune > **Cihaz uyumluluğu**'nda yeni bir ilke oluşturun veya mevcut bir ilkeyi > **Özellikler**'i seçin. **Uyumsuzluğa yönelik eylemler** > **Ekle**’yi ve cihazı uzaktan kilitlemeyi seçin.
Şu platformlarda desteklenir: 
- Android
- iOS
- Mac OS
- Windows 10 Mobile 
- Windows Phone 8.1 ve üzeri 

#### <a name="windows-10-and-later-kiosk-profile-improvements-in-the-azure-portal----2748224---"></a>Azure portalında Windows 10 ve üzeri Bilgi Noktası geliştirmeleri <!-- 2748224 -->
Bu güncelleştirmede Windows 10 Bilgi Noktası cihaz yapılandırma profilinde (platform için **Cihaz yapılandırması** > **Profiller** > **Profil oluştur** > **Windows 10 ve üzeri**, profil türü için > **Bilgi noktası önizlemesi**) yapılan aşağıdaki iyileştirmeler bulunur: 
- Şu anda aynı cihazda birden fazla bilgi noktası profili oluşturabiliyorsunuz. Bu güncelleştirme ile Intune, cihaz başına yalnızca bir bilgi noktası profilini destekleyecek. Tek bir cihazda birden fazla bilgi noktası profiline ihtiyacınız varsa bir Özel URI kullanabilirsiniz.
- **Çok uygulamalı bilgi noktası** profilinde, uygulama kılavuzundaki **Başlangıç menüsü düzeni** için uygulama kutucuğu boyutunu ve sırasını seçebilirsiniz. Daha fazla özelleştirme isterseniz bir XML dosyasını karşıya yükleyebilirsiniz.
- Bilgi Noktası Tarayıcısı ayarları, **Bilgi Noktası** ayarlarına taşınıyor. Şu anda **Bilgi Noktası web tarayıcısı** ayarlarının Azure portalında kendi kategorisi var.
Uygulama hedefi: Windows 10 ve üzeri




### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="apply-autopilot-profile-to-enrolled-win-10-devices-not-already-registered-for-autopilot----1558983---"></a>Autopilot’a kayıtlı olmayan kayıtlı Win 10 cihazlara Autopilot profili uygulama <!-- 1558983 -->
Kayıtlı olduğu halde Autopilot’a kayıtlı olmayan Win 10 cihazlara Autopilot profili uygulayabilirsiniz. Autopilot profilinde **Hedeflenen tüm cihazları Autopilot’a dönüştür** seçeneğini belirterek Autopilot olmayan cihazları Autopilot dağıtım hizmetine otomatik olarak kaydedin. Kaydın işlenmesi için 48 saat kadar bekleyin. Cihazın kaydı kaldırıldığında ve cihaz sıfırlandığında Autopilot, cihazı sağlar.

#### <a name="create-and-assign-multiple-enrollment-status--page-profiles-to-azure-ad-groups----2526564---"></a>Azure AD gruplarına birden fazla Kayıt Durumu Sayfası profili oluşturma ve atama <!-- 2526564 -->
Artık Azure ADD grupları için birden fazla Kayıt Durumu Sayfası profili [oluşturup atayabilirsiniz](windows-enrollment-status.md).

#### <a name="migration-from-device-enrollment-program-to-apple-business-manager-in-intune---2748613--"></a>Intune’da Aygıt Kayıt Programı’ndan Apple Business Manager’a geçiş <!--2748613-->
Apple Business Manager (ABM), Intune’da çalışır ve hesabınızı Aygıt Kayıt Programı’ndan (DEP) ABM’ye yükseltebilirsiniz. Intune’da bu işlem aynıdır. Apple hesabınızı DEP’den ABM’ye yükseltmek için şu adrese gidin: [ https://support.apple.com/en-us/HT208817]( https://support.apple.com/en-us/HT208817).

### <a name="alert-and-enrollment-status-tabs-on-the-device-enrollment-overview-page---2748656--"></a>Cihaz kaydı genel bakış sayfasında uyarı ve kayıt durumu sekmeleri <!--2748656-->
Uyarılar ve kayıt hataları artık Cihaz kaydı genel bakış sayfasında ayrı sekmelerde görüntülenir.

### <a name="device-management"></a>Cihaz yönetimi

#### <a name="restricts-apps-and-block-access-to-company-resources-on-android-devices----2451462----"></a>Android cihazlarda uygulamaları kısıtlar ve şirket kaynaklarına erişimi engeller <!-- 2451462  -->  
**Cihaz uyumluluğu** > **İlkeler** > **İlke oluştur** > **Android** > **Sistem Güvenliği**'nde *Cihaz Güvenliği* bölümünde **Kısıtlı uygulamalar** adlı yeni bir ayar vardır. **Kısıtlı uygulamalar** ayarı, üzerinde belirli uygulamalar yüklü olduğunda cihazın şirket kaynaklarına erişimini engelleyecek bir uyumluluk ilkesi kullanır. Cihaz, kısıtlı uygulamalar kaldırılana kadar uyumsuz sayılır.
Uygulama hedefi: 
- Android




## <a name="week-of-september-24-2018"></a>24 Eylül 2018 haftası

### <a name="microsoft-365-device-management-administration-center----3078424---"></a>Microsoft 365 Cihaz Yönetimi yönetim merkezi <!-- 3078424 -->
Microsoft 365'in vadettiği en önemli şeylerden biri basitleştirilmiş yönetimdir ve Intune ve Azure AD koşullu erişim gibi uçtan uca senaryoları sunmak için yıllardır yaptığımız çalışmalarla arka uç Microsoft 365 hizmetlerini tümleştirdik. Yönetim deneyimini birleştirmenin, basitleştirmenin ve tümleştirmenin yeri yeni [Microsoft 365 yönetim merkezidir](http://devicemanagement.microsoft.com). Cihaz Yönetimi için uzman çalışma alanı, kuruluşunuz için gereken tüm cihaz ve uygulama yönetim bilgi ve görevlerine kolay erişim sağlar. Buranın kurumsal son kullanıcı bilgi işlem ekipleri için birinci bulut çalışma alanı haline gelmesini bekliyoruz.

### <a name="support-for-more-third-party-certification-authorities-ca----3093107---"></a>Daha çok sayıda sertifika yetkilisine (CA) destek <!-- 3093107 -->
Basit Sertifika Kayıt Protokolü'nü (SCEP) kullanarak artık Windows, iOS, Android ve macOS kullanan mobil cihazlarda yeni sertifika verebilir ve mevcut sertifikaları yenileyebilirsiniz.

### <a name="intune-moves-to-support-ios-10-and-later----2454656---"></a>Intune, iOS 10 ve üzeri sürümleri desteklemeye geçiyor <!-- 2454656 -->  
Intune kaydı, Şirket Portalı ve yönetilen tarayıcı artık yalnızca iOS 10 ve üzerini çalıştıran iOS cihazları desteklemektedir. Kuruluşunuzda bundan etkilenen cihaz veya kullanıcıları denetlemek için Azure portalında Intune > **Cihazlar** > **Tüm cihazlar**'a gidin. İşletim sistemine göre filtreleyin, sonra işletim sistemi sürümü ayrıntılarının çıkması için **Sütunlar**'a tıklayın. Bu kullanıcılardan cihazlarını desteklenen bir işletim sistemi sürümüne yükseltmelerini isteyin.  

Aşağıda listelenen cihazlardan birine sahipseniz veya bunlardan birini kaydetmek istiyorsanız, bunların yalnızca iOS 9 ve öncesini desteklediğini bilmelisiniz.  Intune Şirket Portalı'na erişmeye devam etmek için bu cihazları iOS 10 ve üzerini destekleyen cihazlara yükseltmeniz gerekir:  

* iPhone 4S 
* iPod Touch  
* iPad 2 
* iPad (3. Nesil) 
* iPad Mini (1. Nesil)  

## <a name="week-of-september-17-2018"></a>17 Eylül 2018 haftası

### <a name="app-management"></a>Uygulama yönetimi

### <a name="remove-duplication-of-app-protection-status-tiles----3083391---"></a>Yinelenen uygulama koruması durum kutucuklarını kaldırma <!-- 3083391 -->
**iOS için kullanıcı durumu** ve **Android için kullanıcı durumu** kutucuklarının ikisi de **İstemci Uygulamalar - Genel Bakış** sayfasında ve **İstemci Uygulamalar - Uygulama koruma durumu** sayfasında vardı. Durum kutucukları, yineleme olmaması için **İstemci Uygulamalar - Genel Bakış** sayfasından kaldırılmıştır. 

## <a name="week-of-august-27-2018"></a>27 Ağustos 2018 Haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="packet-tunnel-support-for-ios-per-app-vpn-profiles-for-custom-and-pulse-secure-connection-types----1520957---"></a>Özel ve Pulse Secure bağlantı türleri için iOS uygulama başına VPN profilleri için paket tüneli desteği <!-- 1520957 -->
iOS uygulama başına VPN profillerini kullanırken uygulama katman tüneli (uygulama-proxy) veya paket düzeyi tünel (paket-tünel) kullanabilirsiniz. Bu seçenekler, aşağıdaki bağlantı türleri ile kullanılabilir:
- Özel VPN
- Pulse Secure Hangi değeri kullanmanız gerektiğini bilmiyorsanız VPN sağlayıcınızın belgelerine başvurun.

#### <a name="delay-when-ios-software-updates-are-shown-on-the-device----1949583---"></a>Cihazda iOS yazılım güncelleştirmelerinin gösterilmesini geciktirme <!-- 1949583 -->
Intune > **Yazılım Güncelleştirmeleri** > **iOS güncelleştirme ilkeleri**’nde cihazların güncelleştirme yüklemesini istemediğiniz gün ve saatleri yapılandırabilirsiniz. Gelecek bir güncelleştirme ile bir yazılım güncelleştirmesinin cihazda görüntülenmesini 1-90 gün kadar geciktirebileceksiniz. 
[Microsoft Intune’da iOS güncelleştirme ilkelerini yapılandırma](software-updates-ios.md) makalesi, geçerli ayarları listeler.

#### <a name="office-365-proplus-version----2213968---"></a>Office 365 ProPlus sürümü <!-- 2213968 -->
Intune kullanarak Office 365 ProPlus uygulamalarını Windows 10 cihazlara atarken Office sürümünü seçebilirsiniz. Azure portalında **Microsoft Intune** > **Uygulamalar** > **Uygulama ekle**’yi seçin. Daha sonra açılan **Tür** listesinden **Office 365 ProPlus Paketi (Windows 10)**’u seçin. İlişkili dikey pencereyi görüntülemek için **Uygulama Paketi Ayarları**’nı seçin. **Güncelleştirme Kanalı** için bir değer ayarlayın, örneğin **Aylık**. İsteğe bağlı olarak **Evet**’i seçin ve son kullanıcı cihazlarından diğer Office (msi) sürümünü kaldırın. Son kullanıcı cihazlarında seçili kanal için belirli bir Office sürümü yüklemek için **Belirli**’yi seçin. Bu noktada Office’in **Belirli bir sürüm**ünü seçip kullanabilirsiniz. Kullanılabilir sürümler zaman içerisinde değişir. Bu neden yeni bir dağıtım oluştururken kullanılabilir sürümler daha yeni olabilir ve bazı eski sürümleri bulamayabilirsiniz. Mevcut dağıtımlar eski sürümü dağıtmaya devam eder ancak her kanaldaki sürüm listesi sürekli olarak güncelleştirilir. Daha fazla bilgi için bkz. [Office 365 ProPlus güncelleştirme kanallarına genel bakış](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus).

#### <a name="support-for-register-dns-setting-for-windows-10-vpn----2282852---"></a>Windows 10 VPN için DNS ayarı kaydetme desteği <!-- 2282852 -->
Bu güncelleştirme ile Windows 10 VPN profillerini, VPN arabirimine atanmış IP adreslerini özel profil kullanmaya ihtiyaç duymadan dinamik olarak dahili DNS’e kaydedecek şekilde yapılandırabilirsiniz.
Kullanabileceğiniz geçerli VPN profil ayarları hakkında bilgi için bkz. [Windows 10 VPN ayarları](vpn-settings-windows-10.md). 

#### <a name="the-macos-company-portal-installer-now-includes-the-version-number-in-the-installer-file-name---2652728--"></a>macOS Şirket Portalı yükleyicisi artık sürüm numarası ve yükleyici dosya adını içeriyor <!--2652728-->

#### <a name="ios-automatic-app-updates----2729759---"></a>iOS otomatik uygulama güncelleştirmeleri <!-- 2729759 -->
Otomatik uygulama güncelleştirmeleri, iOS sürüm 11.0 ve üzerinde cihaz ve kullanıcı lisanslı uygulamalar için kullanılabilir.




### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="windows-hello-will-target-users-and-devices----1106609---"></a>Windows Hello, kullanıcıları ve cihazları hedefleyecek <!-- 1106609 -->
Bir [İş İçin Windows Hello](windows-hello.md) ilkesi oluşturduğunuzda bu ilke, kuruluştaki tüm kullanıcılara (kiracı genelinde) uygulanır. Bu güncelleştirmeyle ilke, bir cihaz yapılandırma ilkesi kullanılarak belirli kullanıcılara veya belirli cihazlara da (**Cihaz Yapılandırması** > **Profiller** > **Profil oluştur** > **Kimlik Koruma** > **İş İçin Windows Hello**) uygulanabilecek.
Azure portalında Intune’da Windows Hello yapılandırması ve ayarları artık hem **Cihaz kaydı** hem de **Cihaz yapılandırması** bölümlerinde bulunuyor. **Cihaz kaydı**, kuruluşun tamamını (kiracı genelinde) hedefler ve Windows AutoPilot (OOBE) destekler. **Cihaz yapılandırması**, iade sırasında uygulanan bir ilkeyi kullanarak cihazları ve kullanıcıları hedefler.
Bu özellik şu platformlarda geçerlidir:  
- Windows 10 ve üzeri
- Windows 10 Holographic for Business

#### <a name="zscaler-is-an-available-connection-for-vpn-profiles-on-ios----1769858---"></a>iOS’ta VPN profilleri için Zscaler bağlantısı kullanılabilir <!-- 1769858 -->
Bir iOS VPN cihaz yapılandırma profili oluşturduğunuzda (**Cihaz yapılandırması** > **Profiller** > **Profil oluştur** > **iOS** platform > **VPN** profil türü) Cisco, Citrix vb. gibi birkaç bağlantı türü vardır. Bu güncelleştirme ile Zscaler da bir bağlantı türü olarak eklendi. 
[iOS çalıştıran cihazlar için VPN ayarları](vpn-settings-ios.md), kullanılabilir bağlantı türlerini listeler.

#### <a name="fips-mode-for-enterprise-wi-fi-profiles-for-windows-10----1879077---"></a>Windows 10 için Kurumsal Wi-Fi profilleri için FIPS modu <!-- 1879077 -->
Intune Azure portalında Windows 10 için Kurumsal Wi-Fi profilleri için artık Federal Bilgi İşleme Standardı (FIPS) modunu etkinleştirebilirsiniz. FIPS modunu Wi-Fi profillerinizde etkinleştirirseniz Wi-Fi altyapınızda etkinleştirmeyi de unutmayın.
[Intune’da Windows 10 ve üzeri cihazlar için Wi-Fi ayarları](wi-fi-settings-windows.md) makalesi, bir Wi-Fi profilini nasıl oluşturacağınızı gösterir.

#### <a name="control-s-mode-on-windows-10-and-later-devices---public-preview----1958649---"></a>Windows 10 ve üzeri cihazlarda S modunu denetleme - genel önizleme <!-- 1958649 -->
Bu özellik güncelleştirmesi ile Windows 10 cihazı S modundan çıkaran veya kullanıcıların cihazı S modundan çıkarmasını önleyen bir cihaz yapılandırma profili oluşturabilirsiniz. Bu özellik Intune’da **Cihaz yapılandırması** > **Profiller** >  **Windows 10 ve üzeri** > **Sürüm yükseltme ve mod değiştirme** altındadır.
[S modunda Windows 10’a giriş](https://www.microsoft.com/windows/s-mode) makalesi, S modu hakkında daha fazla bilgi sağlar.
Şunlar için geçerlidir: En son [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) derlemesi (önizlemedeyken).


#### <a name="windows-defender-atp-configuration-package-automatically-added-to-configuration-profile----2144658---"></a>Windows Defender ATP yapılandırma paketi, otomatik olarak yapılandırma profiline eklenir <!-- 2144658 -->
Eskiden Intune’da [Gelişmiş Tehdit Koruması ve ekleme](advanced-threat-protection.md#onboard-devices-using-a-configuration-profile) cihazları kullanırken bir yapılandırma paketini indirip bunu yapılandırma profilinize ekliyordunuz. Bu güncelleştirme ile Intune, paketi otomatik olarak Windows Defender Güvenlik Merkezi’nden alır ve profilinize ekler.
Windows 10 ve üzeri için geçerlidir.

#### <a name="require-users-to-connect-during-device-setup---2311457--"></a>Cihaz kurulumu sırasında kullanıcıların bağlanmasını gerektirme <!--2311457-->
Artık Windows 10 kurulumu sırasında Ağ sayfasından ileri gitmeden önce cihazın bir ağa bağlanmasını gerektirecek cihaz profilleri ayarlayabilirsiniz. Bu özellik önizlemedeyken bu ayarı kullanmak için Windows Insider derleme 1809 veya sonrası gerekir.
Şunlar için geçerlidir: En son [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) derlemesi (önizlemedeyken).


#### <a name="restricts-apps-and-block-access-to-company-resources-on-ios-and-android-enterprise-devices----2451462---"></a>iOS ve Android Kurumsal cihazlarında uygulamaları kısıtlama ve şirket kaynaklarına erişimi engelleme <!-- 2451462 -->
**Cihaz uyumluluğu** > **İlkeler** > **İlke oluştur** > **iOS** > **Sistem Güvenliği**’nde yeni **Kısıtlı uygulamalar** ayarı var. Bu yeni ayar, bazı uygulamalar cihaza yüklendiğinde cihazın şirket kaynaklarına erişimini engelleyecek bir uyumluluk ilkesi kullanır. Cihaz, kısıtlı uygulamalar kaldırılana kadar uyumsuz sayılır.
Şunun için geçerlidir: iOS

#### <a name="modern-vpn-support-updates-for-ios----2459928-1819876-and-2650856---"></a>iOS için modern VPN destek güncelleştirmeleri <!-- 2459928, 1819876, and 2650856 -->
Bu güncelleştirme, aşağıdaki iOS VPN istemcileri için destek ekliyor: 
- F5 Erişimi (sürüm 3.0.1 ve üzeri)
- Citrix SSO
- Palo Alto Networks GlobalProtect sürüm 5.0 ve üzeri Bu güncelleştirmede ayrıca:
- iOS için mevcut**F5 Access** bağlantı türü, **F5 Access Eski** olarak yeniden adlandırıldı.
- iOS için mevcut**Palo Alto Networks GlobalProtect** bağlantı türü, **Palo Alto Networks GlobalProtect (eski)** olarak yeniden adlandırıldı.
Bu bağlantı türlerine sahip mevcut profiller, eski VPN istemcileriyle çalışmaya devam edecek. iOS ile Cisco Eski AnyConnect, F5 Access Eski, Citrix VPN veya Palo Alto Networks GlobalProtect sürüm 4.1 ve öncesi kullanıyorsanız yeni uygulamalara geçmelisiniz. iOS 12 sonrası iOS cihazlarda VPN erişiminin kullanılabilir olmasını sağlamak için bunu en kısa zamanda yapmalısınız.
iOS 12 ve VPN profilleri hakkında daha fazla bilgi için bkz. [Microsoft Intune Destek Ekibi Blogu](https://go.microsoft.com/fwlink/?linkid=2013806).

#### <a name="export-azure-classic-portal-compliance-policies-to-recreate-these-policies-in-the-intune-azure-portal----2469637---"></a>Klasik Azure portalı uyumluluk ilkelerini dışarı aktararak bunları Intune Azure portalında yeniden oluşturma <!-- 2469637 -->
Azure klasik portalında oluşturulan ilkeler artık kullanım dışı olacak. Mevcut uyumluluk ilkelerini gözden geçirebilir ve silebilirsiniz ancak güncelleştiremezsiniz. Bazı mevcut uyumluluk ilkelerini geçerli Intune Azure portalına geçirmek istiyorsanız bunları virgülle ayrılmış bir dosyayla (*.csv* dosyası) dışarı aktarabilirsiniz. Daha sonra Intune Azure portalında bu ilkeleri yeniden oluşturmak için dosyadaki ayrıntıları kullanabilirsiniz.

> [!IMPORTANT]
> Azure klasik portalı kullanımdan kalktıktan sonra uyumluluk ilkelerinize erişme veya bunları görüntüleme şansınız olmayacak. Bu sebeple Azure klasik portalı kullanımdan kaldırılmadan önce ilkelerinizi dışarı aktarıp Azure portalında yeniden oluşturduğunuzdan emin olun.

#### <a name="better-mobile---new-mobile-threat-defense-partner----22662717---"></a>Better Mobile - Yeni Mobil Tehdit Savunması iş ortağı <!-- 22662717 -->
Microsoft Intune ile tümleştirilen bir Mobil Tehdit Savunması çözümü olan Better Mobile tarafından yapılan risk değerlendirmesine göre koşullu erişim kullanarak mobil cihazlardan şirket kaynaklarına erişimi denetleyebilirsiniz.

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="lock-the-company-portal-in-single-app-mode-until-user-sign-in---1067692---"></a>Kullanıcı oturum açana kadar Şirket Portalı’nı tek uygulama modunda kilitleme <!--1067692 --> 
DEP kaydı sırasında bir kullanıcının kimliğini Kurulum Yardımcısı yerine Şirket Portalı ile doğrularsanız, artık Şirket Portalı’nı Tekli Uygulama modunda çalıştırma seçeneğiniz var. Bu seçenek, Kurulum Yardımcısı tamamlandıktan hemen sonra cihazı kilitler; böylece kullanıcının cihaza erişmek için oturum açması gerekir. Bu işlem, cihazın eklenmesinin tamamlanmasını ve kullanıcısı olmadan yalnız bırakılmış duruma gelmemesini sağlar.

#### <a name="assign-a-user-and-friendly-name-to-an-autopilot-device---1346521---"></a>Autopilot cihazına kullanıcı ve kolay ad atama <!--1346521 -->
Artık [tek bir Autopilot cihazına kullanıcı atayabilirsiniz](enrollment-autopilot.md). Yöneticiler ayrıca cihazlarını AutoPilot ile ayarlayan kullanıcıları karşılaması için kolay adlar verebilecekler.
Şunlar için geçerlidir: En son [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) derlemesi (önizlemedeyken).

#### <a name="use-vpp-device-licenses-to-pre-provision-the-company-portal-during-dep-enrollment----1608345---"></a>DEP kaydı sırasında Şirket Portalı’nın ön sağlamasını yapmak için VPP cihaz lisanslarını kullanın <!-- 1608345 -->
Artık Aygıt Kayıt Programı (DEP) kayıtları sırasında Şirket Portalı’nın ön sağlamasını yapmak için Volume Purchase Program (VPP) cihaz lisanslarını kullanabileceksiniz. Bunu yapmak için [bir kayıt profili oluşturduğunuzda veya düzenlediğinizde](device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile), Şirket Portalı’nı yüklemek için kullanmak istediğiniz VPP belirtecini belirtin. Belirtecinizin süresinin dolmadığından ve Şirket Portalı uygulaması için yeterli lisansınız olduğundan emin olun. Belirtecin süresi dolduğu veya yeterli lisans olmadığı durumlarda, Intune bunun yerine Uygulama Mağazası Şirket Portalı’na istek gönderir (bu, Apple kimliği ister).

#### <a name="confirmation-required-to-delete-vpp-token-that-is-being-used-for-company-portal-pre-provisioning----2237634---"></a>Şirket Portalı ön sağlaması için kullanılan bir VPP belirtecini silmek için onay gerekir <!-- 2237634 -->
DEP kaydı sırasında Şirket Portalı’nın ön sağlaması için bir Volume Purchase Program (VPP) belirteci kullanılıyorsa artık bunu silmek için onay gerekir.

#### <a name="block-windows-personal-device-enrollments----1849498---"></a>Windows kişisel cihaz kayıtlarını engelleme <!-- 1849498 -->
[Windows kişisel cihazları engelleyerek](enrollment-restrictions-set.md#set-device-type-restrictions) Intune [mobil cihaz yönetimine](windows-enroll.md) kaydolmasını önleyebilirsiniz. Bu özellikle [Intune PC aracısı](manage-windows-pcs-with-microsoft-intune.md) ile kaydedilen cihazlar engellenemez. Bu özellik, önümüzdeki birkaç hafta içerisinde yayımlanacak, bu nedenle kullanıcı arabiriminde özelliği hemen göremeyebilirsiniz.

#### <a name="specify-machine-name-patterns-in-an-autopilot-profile---1849855--"></a>Autopilot profilinde makine adı desenleri belirtme <!--1849855-->
Autopilot kaydı sırasında [bilgisayar adı](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) oluşturmak ve ayarlamak için [bir bilgisayar adı şablonu](enrollment-autopilot.md#create-an-autopilot-deployment-profile) belirtebilirsiniz. Şunlar için geçerlidir: En son [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) derlemesi (önizlemedeyken).


#### <a name="for-windows-autopilot-profiles-hide-the-change-account-options-on-the-company-sign-in-page-and-domain-error-page---1901669---"></a>Windows Autopilot profilleri için şirket oturum açma sayfasında ve etki alanı hata sayfasında hesap değiştirme seçeneklerini gizleme <!--1901669 -->
Yöneticilerin şirket oturum açma ve etki alanı hata sayfalarında hesap değiştirme seçeneklerini gizlemelerine imkan veren [yeni Windows Autopilot profil seçenekleri](enrollment-autopilot.md#create-an-autopilot-deployment-profile) mevcut. Bu seçenekleri gizlemek, Azure Active Directory’de Şirket Markasının yapılandırılmasını gerektirir. Şunlar için geçerlidir: En son [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) derlemesi (önizlemedeyken).



### <a name="device-management"></a>Cihaz yönetimi

#### <a name="delete-jamf-devices----2653306--"></a>Jamf cihazlarını silme <!-- 2653306-->
**Cihazlar**’a gidip JAMF cihazını ve daha sonra **Sil**’i seçerek JAMF tarafından yönetilen cihazları silebilirsiniz.

#### <a name="change-terminology-to-retire-and-wipe----2175759---"></a>Terminolojiyi "kullanım dışı bırakma" ve "temizleme" olarak değiştirin <!-- 2175759 -->
Graph API ile tutarlılığı sağlamak için Intune kullanıcı arabirimi ve belgelerine aşağıdaki terim değişiklikleri yansıtıldı:
- **Şirket verilerini kaldırma** terimi, “kullanımdan kaldırma” olarak değiştirilecek
- **Fabrika sıfırlaması** terimi **temizleme** olarak değiştirilecek

#### <a name="confirmation-dialog-if-admin-tries-to-delete-mdm-push-certificate----297909500--"></a>Yönetici MDM Anında İletme Sertifikası’nı silmeye çalıştığında onay iletişim kutusu <!-- 297909500-->
Apple MDM Anında İletme Sertifikası silinmeye çalışılırsa, ilgili iOS ve macOS cihaz sayısını gösteren bir onay iletişim kutusu görüntülenir. Sertifika silinirse bu cihazların yeniden kaydedilmesi gerekir.

### <a name="additional-security-settings-for-windows-installer----2282430---"></a>Windows Installer için ek güvenlik ayarları <!-- 2282430 -->
Kullanıcıların uygulama yüklemelerini denetlemesine olanak sağlayabilirsiniz. Etkinleştirilirse, aksi takdirde güvenlik ihlali nedeniyle durdurulabilecek olan yüklemelerin devam etmesine izin verilebilir. Windows Installer'ı sistemde herhangi bir program yüklerken yükseltilmiş izinler kullanmaya yönlendirebilirsiniz. Buna ek olarak, Windows Bilgi Koruması (WIP) öğelerinin dizine alınmasını ve bunlar hakkındaki meta verilerin şifrelenmemiş bir konumda depolanmasını etkinleştirebilirsiniz. İlke devre dışı bırakıldığında, WIP korumalı öğelerin dizini oluşturulmaz ve Cortana veya dosya gezgini sonuçlarında görünmez. Bu seçeneklerin işlevselliği varsayılan olarak devre dışı bırakılmıştır. 

### <a name="new-user-experience-update-for-the-company-portal-website---2000968---"></a>Şirket Portalı web sitesi için yeni kullanıcı deneyimi güncelleştirmesi <!--2000968 -->
Müşterilerden gelen geri bildirim temelinde Şirket Portalı web sitesine yeni özellikler ekledik. Cihazlarınızın mevcut işlevselliğinde ve kullanılabilirliğinde önemli gelişmeler göreceksiniz. Sitenin &ndash;cihaz ayrıntıları, geri bildirim ve destek, cihaza genel bakış gibi&ndash; alanlarında yeni, modern, hızlı yanıt veren bir tasarım bulunuyor. Şunları da göreceksiniz:

- Tüm cihaz platformları arasında rahat iş akışları
- Geliştirilmiş cihaz kimlik ve kayıt akışları
- Daha yararlı hata iletileri
- Daha rahat bir dil, daha az teknik jargon
- Doğrudan uygulama bağlantıları paylaşabilme seçeneği
- Büyük uygulama katalogları için iyileştirilmiş performans
- Tüm kullanıcılar için artırılmış erişilebilirlik  

[Intune Şirket Portalı belgeleri](https://docs.microsoft.com/intune-user-help/using-the-intune-company-portal-website) de bu değişiklikleri yansıtacak şekilde güncelleştirildi. Uygulama iyileştirmelerine dair bir örnek görmek isterseniz bkz. [Intune son kullanıcı uygulamaları için kullanıcı arabirimi güncelleştirmeleri](whats-new-app-ui.md).  

### <a name="monitor-and-troubleshoot"></a>İzleme ve sorun giderme

#### <a name="enhanced-jailbreak-detection-in-compliance-reporting---2198738---"></a>Uyumluluk raporlamada gelişmiş jailbreak algılama <!-- 2198738 -->
Gelişmiş jailbreak algılama ayarı durumları, artık yönetici konsolundaki tüm uyumluluk raporlarında görünüyor.

### <a name="role-based-access-control"></a>Rol tabanlı erişim denetimi

#### <a name="scope-tags-for-policies---1081974---"></a>İlkeler için kapsam etiketleri <!--1081974 -->
Intune kaynaklarına erişimi sınırlamak için [kapsam etiketleri oluşturabilirsiniz](scope-tags.md). Bir rol atamasına kapsam etiketi ekleyin ve daha sonra kapsam etiketini bir yapılandırma profiline ekleyin. Rolün yalnızca eşleşen kapsam etiketlerine sahip yapılandırma profillerine erişimi olacaktır.

## <a name="week-of-august-14-2018"></a>14 Ağustos 2018 Haftası

### <a name="macos-support-for-apple-device-enrollment-program----747651---"></a>Apple Aygıt Kayıt Programı için macOS desteği <!-- 747651 -->
Intune, macOS cihazlarının Apple Aygıt Kayıt Programı'na (DEP) kaydedilmesini artık destekleniyor. Daha fazla bilgi için bkz. [macOS cihazlarını Apple’ın Aygıt Kayıt Programı ile otomatik olarak kaydetme](device-enrollment-program-enroll-macos.md).

## <a name="week-of-july-23-2018"></a>23 Temmuz 2018 haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="line-of-business-lob-app-support-for-macos----1895847---"></a>macOS için iş kolu (LOB) uygulamaları desteği <!-- 1895847 -->
Microsoft Intune, macOS LOB uygulamalarının **Gerekli** veya **Kayıt sonrasında kullanılabilir** olarak dağıtılmasına olanak tanır. Son kullanıcılar, uygulamaları macOS için Şirket Portalı’ndan veya [Şirket Portalı web sitesinden](https://portal.manage.microsoft.com) **Kullanılabilir** olarak edinebilir.

#### <a name="ios-built-in-app-support-for-kiosk-mode----2051098---"></a>Bilgi noktası modu için yerleşik iOS uygulama desteği <!-- 2051098 -->
Mağaza Uygulamaları ve Yönetilen Uygulamalara ek olarak artık iOS cihazında bilgi noktası modunda çalışan Safari gibi Yerleşik Uygulamaları da seçebilirsiniz.

#### <a name="edit-your-office-365-pro-plus-app-deployments----2150145---"></a>Office 365 Pro Plus uygulama dağıtımlarınızı düzenleme <!-- 2150145 -->
Microsoft Intune yöneticisi olarak, Office 365 Pro Plus uygulama dağıtımlarınızı düzenleme olanağınız artar. Ayrıca paketin özelliklerinden herhangi birini değiştirmek için artık dağıtımlarınızı silmeniz gerekmez. Azure portalında **Microsoft Intune** > **İstemci uygulamaları** > **Uygulamalar**’ı seçin. Uygulama listesinden Office 365 Pro Plus Suite ürününüz seçin.  


#### <a name="updated-intune-app-sdk-for-android-is-now-available----2744271--"></a>Güncelleştirilmiş Android için Intune Uygulama SDK'sı artık kullanıma sunuldu <!-- 2744271-->

Android P sürümünü desteklemek amacıyla Android için Intune Uygulama SDK'sının güncelleştirilmiş sürümü kullanıma sunuldu. Bir uygulama geliştiricisiyseniz ve Android için Intune SDK'sını kullanıyorsanız, Android uygulamalarınızdaki Intune işlevselliğinin Android P cihazlarında beklendiği gibi çalışmaya devam edebilmesi için Intune uygulama SDK'sının güncelleştirilmiş sürümünü yüklemelisiniz. Intune Uygulama SDK'sının bu sürümü, SDK güncelleştirmelerini gerçekleştiren yerleşik bir eklenti sağlar. Tümleştirilmiş mevcut kodu yeniden yazmanız gerekmez. Ayrıntılar için bkz. [Android için Intune SDK'sı](https://github.com/msintuneappsdk/ms-intune-app-sdk-android). Intune için eski rozetleme stilini kullanıyorsanız, evrak çantası simgesini kullanmanızı öneririz. Markalama ayrıntıları için [bu GitHub deposuna](https://github.com/msintuneappsdk/intune-app-partner-badge) bakın.


### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="create-device-compliance-policy-using-firewall-settings-on-macos-devices----1497640---"></a>macOS cihazlarında Güvenlik Duvarı ayarlarını kullanarak cihaz uyumluluk ilkesi oluşturma <!-- 1497640 -->
Yeni bir macOS uyumluluk ilkesi oluşturduğunuzda (**Cihaz uyumluluğu** > **İlkeler** > **İlke oluştur** > **Platform: macOS** > **Sistem güvenliği**), bazı yeni **Güvenlik Duvarı** ayarları sağlanır: 

- **Güvenlik Duvarı**: Gelen bağlantıları yapılandırma ortamınıza işlenir.
- **Gelen bağlantıları**: **Blok** DHCP, Bonjour ve IPSec gibi temel internet Hizmetleri için gerekli olanlar dışındaki tüm gelen bağlantıları. Bu ayar tüm paylaşım hizmetlerini de engeller.
- **Gizli mod**: **Etkinleştirme** cihaz yoklama isteklerine yanıt vermesini önlemek için gizli modu. Cihaz, yetkilendirilmiş uygulamalardan gelen istekleri yanıtlamaya devam eder.

Şunlar için geçerlidir: macOS 10.12 ve üstü

#### <a name="new-wi-fi-device-configuration-profile-for-windows-10-and-later----1879077---"></a>Windows 10 ve üzeri için yeni Wi-Fi cihaz yapılandırma profili <!-- 1879077 -->
Şu anda XML dosyalarını kullanarak Wi-Fi profillerini içeri ve dışarı aktarabilirsiniz. Bu güncelleştirmeyle, tıpkı bazı diğer platformlarda olduğu gibi Intune’da doğrudan Wi-Fi cihaz yapılandırma profili oluşturabilirsiniz.

Profili oluşturmak için **Cihaz Yapılandırması** > **Profiller** > **Profil Oluştur** > **Windows 10 ve üzeri** > **Wi-Fi** seçeneklerini açın. 

Windows 10 ve üzeri için geçerlidir.

#### <a name="kiosk---obsolete-is-grayed-out-and-cant-be-changed----2149998---"></a>Bilgi noktası - eski seçenek gri renkte ve değiştirilemez <!-- 2149998 -->
[Bilgi noktası özelliği](device-restrictions-windows-10.md#kiosk-preview---obsolete) (**Cihaz Yapılandırması** > **Profiller** > **Profil oluştur** > **Windows 10 ve üzeri** > **Cihaz kısıtlamaları**) artık kullanılmıyor ve [Windows 10 ve üzeri için bilgi noktası ayarları](kiosk-settings.md) ile değiştirildi. Bu güncelleştirmeyle **Bilgi Noktası - Eski** özelliği gri gösterilir ve kullanıcı arabirimi değiştirilemez veya güncelleştirilemez. 

Bilgi noktası modunu etkinleştirmek için bkz. [Windows 10 ve üzeri için bilgi noktası ayarları](kiosk-settings.md).

Windows 10 ve üzeri, Windows Holographic for Business için geçerlidir

#### <a name="apis-to-use-3rd-party-certification-authorities----2184013---"></a>3. taraf sertifika yetkilileri kullanacak API’ler <!-- 2184013 -->
Bu güncelleştirmede, üçüncü taraf sertifika yetkililerinin Intune ve SCEP ile tümleştirilmesini etkinleştirecek bir Java API’si yer alır. Ardından kullanıcılar, SCEP sertifikasını bir profil ekleyebilir ve MDM kullanarak cihazlara uygulayabilir.

Intune şu anda [Active Directory Sertifika Hizmetleri kullanarak SCEP isteklerini](certificates-scep-configure.md) destekler.

#### <a name="toggle-to-show-or-not-show-the-end-session-button-on-a-kiosk-browser----2455253---"></a>Bir Bilgi Noktası tarayıcısında Oturumu Sonlandır düğmesini gösterme veya gizleme geçişi <!-- 2455253 -->
Artık Bilgi Noktası tarayıcılarını Oturumu Sonlandır düğmesini gösterecek veya gizleyecek şekilde yapılandırabilirsiniz. Denetim seçeneğini **Cihaz yapılandırması** > **Bilgi noktası (önizleme)** > **Bilgi Noktası Web Tarayıcısı**’ndan görebilirsiniz. Açılırsa kullanıcı bir düğmeye tıkladığında uygulama, oturumu sonlandırma için onay ister. Onaylandığında tarayıcı, tüm göz atma verilerini temizler ve varsayılan URL’ye geri gider.

#### <a name="create-an-esim-cellular-configuration-profile----2564077---"></a>eSIM hücresel yapılandırma profili oluşturma <!-- 2564077 -->
**Cihaz yapılandırmasında** bir eSIM hücresel profili oluşturabilirsiniz. Cep telefonu operatörünüz tarafından sağlanan hücresel etkinleştirme kodlarını içeren bir dosyayı içeri aktarabilirsiniz. Ardından bu profilleri, Surface Pro LTE ve diğer eSIM özellikli cihazlar gibi eSIM LTE etkinleştirilmiş Windows 10 cihazlara dağıtabilirsiniz.

[Cihazınızın eSIM profillerini destekleyip desteklemediğini](https://support.microsoft.com/help/4020763/windows-10-use-esim-for-cellular-data) görmek için kontrol edin.

Windows 10 ve üzeri için geçerlidir. 




### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="automatically-mark-android-devices-enrolled-by-using-samsung-knox-mobile-enrollment-as-corporate----2404851---"></a>Samsung Knox Mobil Kayıt kullanarak “şirket” olarak kaydedilen Android cihazlarını otomatik olarak işaretleyin. <!-- 2404851 -->
Varsayılan olarak Samsung Knox Mobil Kayıt kullanarak kaydedilen Android cihazları, **Cihaz Sahipliği** altında **şirket** olarak işaretlenir. Şirket cihazlarını Knox Mobil Kayıt kullanarak kaydetmeden önce IMEI veya seri numaraları kullanarak el ile belirlemeniz gerekmez.

### <a name="device-management"></a>Cihaz yönetimi

#### <a name="bulk-delete-devices-on-devices-blade----1793693---"></a>Cihazlar dikey penceresinde cihazları toplu silme <!-- 1793693 -->

Şimdi Cihazlar dikey penceresinde tek seferde birden fazla cihazı silebilirsiniz. **Cihazlar** > **Tüm cihazlar** > silmek istediğiniz cihazları seçin > **Sil**'i seçin. Silinemeyen cihazlar için bir uyarı görüntülenir.

## <a name="week-of-july-16-2018"></a>16 Temmuz 2018 haftası  

### <a name="more-opportunities-to-sync-in-the-company-portal-app-for-windows"></a>Windows için Şirket Portalı uygulamasında daha fazla eşitleme fırsatı  
Windows için Şirket Portalı uygulaması artık eşitlemeyi doğrudan Windows görev çubuğu ve Başlat menüsünden başlatmanıza olanak tanır. Göreviniz yalnızca cihazları eşitlemek veya şirket kaynaklarına erişim sağlamak olduğunda, bu özellik çok kullanışlıdır. Yeni özelliğe erişmek için görev çubuğunuza veya Başlat menünüze sabitlenmiş Şirket portalı simgesine sağ tıklayın. Menü seçeneklerinde (atlama listesi olarak da bilinir) **Bu cihazı eşitle**’yi seçin. Şirket Portalı, **Ayarlar** sayfasında açılır ve eşitlemenizi başlatır. Yeni işlevselliğe göz atmak için bkz. [Kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md).   

### <a name="new-browsing-experiences-in-the-company-portal-app-for-windows"></a>Windows için Şirket Portalı uygulamasında yeni göz atma deneyimleri  

Artık Windows için Şirket Portalı uygulamasında uygulamalara göz atarken veya uygulama ararken mevcut **Kutucuklar** görünümü ile yeni eklenen **Ayrıntılar** görünümü arasında geçiş yapabilirsiniz. Yeni görünümde ad, yayımcı, yayım tarihi ve yükleme durumu gibi uygulama ayrıntıları listelenir.  

**Uygulamalar** sayfasının **Yüklemeler** görünümü, tamamlanmış ve devam eden uygulama yüklemeleri hakkındaki ayrıntıları görmenizi sağlar. Yeni görünümün neye benzediğine göz atmak için bkz. [Kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md).  
### <a name="improved-company-portal-app-experience-for-device-enrollment-managers"></a>Cihaz kayıt yöneticileri için geliştirilmiş Şirket Portalı uygulaması deneyimi  
Bir cihaz kayıt yöneticisi (DEM) Windows için Şirket Portalı uygulamasında oturum açtığında, uygulama artık yalnızca yöneticinin geçerli, çalışan cihazını listeleyecek. Bu yenilik, uygulama DEM tarafından kaydedilen tüm cihazları göstermeye çalıştığında yaşanan zaman aşımı sorunlarını azaltacak.  


## <a name="week-of-july-9-2018"></a>9 Temmuz 2018 haftası

### <a name="app-management"></a>Uygulama yönetimi

### <a name="block-app-access-based-on-unapproved-device-vendors-and-models-----1425689----"></a>Onaylanmamış cihaz satıcıları ve modellerine göre uygulama erişimini engelleme <!-- 1425689 ! -->
Intune BT yöneticisi, belirlenen Android üreticileri ve/veya iOS modelleri listesini Intune Uygulama Koruması İlkeleri yoluyla zorlayabilir. BT yöneticisi, Android ilkeleri için noktalı virgülle ayrılmış bir üretici listesi ve aynı şekilde iOS ilkeleri için bir cihaz modelleri listesi sağlayabilecek. Intune Uygulama Koruması İlkeleri, yalnızca Android ve iOS için geçerlidir. Bu belirtilen listede gerçekleştirilebilen iki ayrı eylem vardır:
- Belirtilmemiş cihazlarda uygulama erişimini engelleme.
- Veya belirtilmemiş cihazlarda şirket verilerini seçmeli olarak silme. 

İlke gereksinimleri karşılanmazsa kullanıcı, hedeflenen uygulamaya erişemeyecek. Ayarlara bağlı olarak kullanıcı engellenebilir veya uygulama dahilinde kullanıcının şirket verileri seçmeli olarak silinir. iOS cihazlarında, bu özelliğin hedeflenen uygulamalarda zorlanması için Intune APP SDK'nin tümleştirilmesi amacıyla uygulamaların (WXP, Outlook, Managed Browser, Yammer gibi) katılımı gerekir. Bu tümleştirme, sıralı bir şekilde gerçekleşir ve belirli uygulama ekiplerine bağımlıdır. Android’de bu özellik, Şirket Portalı’nın en son sürümünü gerektirir. 

Son kullanıcı cihazlarında Intune istemcisi, Intune’un Uygulama Koruma İlkeleri dikey penceresinde belirtilen dizelerin basit eşleştirmesine dayalı olarak eylem gerçekleştirir. Bu, tamamen cihazın rapor ettiği değere bağlıdır. Bu nedenle BT yöneticisinin amaçlanan davranışın doğru olduğundan emin olması önerilir. Bu ayar, küçük bir kullanıcı grubuna hedeflenen çeşitli cihaz üreticileri ve modellerinde sınanarak doğruluğundan emin olunabilir. Microsoft Intune’da uygulama koruma ilkelerini görüntülemek ve ilke eklemek için **İstemci uygulamaları** > **Uygulama koruma ilkeleri**’ni seçin. Uygulama koruma ilkeleri hakkında daha fazla bilgi için bkz. [Uygulama koruma ilkeleri nedir?](app-protection-policy.md) ve [Intune’da uygulama koruma ilkesi erişim eylemlerini kullanarak verileri seçmeli olarak silme](app-protection-policies-access-actions.md).

### <a name="access-to-macos-company-portal-pre-release-build----1734766---"></a>macOS Şirket Portalı yayın öncesi derlemesine erişim <!-- 1734766 -->
Insider programına katılarak, Microsoft AutoUpdate'i kullanıp derlemeleri erken almak için kaydolabilirsiniz. Kaydolmanız, güncelleştirilmiş Şirket Portalı'nı son kullanıcılarınıza sağlanmadan önce kullanmanıza olanak tanıyacaktır. Daha fazla bilgi için, [Microsoft Intune bloguna](https://blogs.technet.microsoft.com/intunesupport/2018/07/13/use-microsoft-autoupdate-for-early-access-to-the-macos-company-portal-app/) bakın.

## <a name="week-of-july-2-2018"></a>2 Temmuz 2018 Haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="monitor-ios--app-configuration-status-per-device----880037---"></a>Cihaz başına iOS uygulama yapılandırması durumunu izleme <!-- 880037 -->
Microsoft Intune yöneticisi olarak, yönetilen her cihaz için iOS uygulama yapılandırması durumunu izleyebilirsiniz. Azure portalında **Microsoft Intune**'dan **Cihazlar** > **Tüm cihazlar**'ı seçin. Yönetilen cihaz listesinden belirli bir cihazı seçerek o cihazın dikey penceresini görüntüleyin. Cihaz dikey penceresinde **Uygulama yapılandırması**'nı seçin.

#### <a name="access-actions-for-app-protection-policies----1483510---"></a>Uygulama koruma ilkeleri için eylemlere erişme <!-- 1483510 -->
Uyumsuz cihazları açık olarak silmek, engellemek veya uyarmak üzere uygulama koruma ilkeleri yapılandırabilirsiniz. *Silme* eylemi, bir cihazdan şirketinizin verilerini kaldırır. Silme işlemi gerçekleştirildiğinde, cihazın kullanıcısına silme nedeni ve düzeltme adımları bildirilir. En düşük işletim sistemi sürümü gibi bazı ayarlarda, engelleme ve silme gibi birden fazla eylem gerçekleştirebileceksiniz. Bu eylemlerin uygulama başlatıldığında tetiklendiğine dikkat edin.

#### <a name="selective-wipe-of-organizations-app-data----1507030---"></a>Kuruluşun uygulama verilerini seçmeli silme <!-- 1507030 -->
Uygulama Koruma İlkeleri (APP) Erişim ayarlarının koşullarına uyulmadığında, şimdi yöneticiler yeni bir eylem olarak kuruluş verilerinin seçmeli silinmesini yapılandırabilir.  Bu özellik yöneticilerin önceden yapılandırılmış ölçütler temelinde hassas kuruluş verilerini otomatik olarak korumasına ve uygulamalardan kaldırmasına yardımcı olur.

#### <a name="revoking-an-ios-app-purchased-through-vpp----1777384---"></a>VPP üzerinden satın alınan iOS uygulamasını iptal etme <!-- 1777384 -->
Microsoft Intune yöneticisi olarak, Volume Purchase Program (VPP) üzerinden satın alınan seçili iOS uygulamasının tüm lisanslarını iptal edebilirsiniz. Kullanıcı lisanslı uygulamanın artık kendisine atanmış durumda olmadığını kullanıcıya bildirebilirsiniz. Bir uygulama lisansını iptal etmek ilgili VPP uygulamasını cihazdan kaldırmaz. Bir VPP uygulamasını kaldırmak için, atama işlemini **Kaldır** olarak değiştirmelisiniz. Geri kazanılan lisans sayısı, Intune'un **Uygulama** iş yükündeki **Lisanslı Uygulamalar** düğümünde yansıtılacak. iOS VPP uygulamalarıyla ilgili daha fazla bilgi için bkz. [Microsoft Intune ile Volume Purchase Program üzerinden satın alınan iOS uygulamalarını yönetme](vpp-apps-ios.md).

#### <a name="updates-to-out-of-compliance-messages-in-company-portal-app----1832222---"></a>Şirket Portalı uygulamasında uyumsuzluk iletilerine güncelleştirmeler <!-- 1832222 -->
Cihaz uyumlu olmadığında cihaz kullanıcılarının gördüğü iletileri düzelttik. İletiler özgün anlamlarını koruyor ancak daha kolay bir dil ve daha az teknik terminoloji ile güncelleştirildi. Ayrıca belge bağlantılarını ve bunları güncel tutmaya yönelik düzeltme adımlarını da yeniledik.
Aşağıda öncesi ve sonrası gösterilen metin, göreceğiniz ileti iyileştirmelerinin bir örneğidir:
- **Önce**: *Bu cihaz Intune hizmetine BT yöneticiniz tarafından gerekli belirtilen bir zaman dönemi içindeki bağlantı kurmadı. Bu sorunu çözmek için lütfen cihazınızda şirket portalı uygulamasını açın ve Uyumluluğu Denetle düğmesine tıklayın.*
- **Sonra**: *Cihazınız bir süredir kuruluşunuz oturum iade. Bağlantıyı yeniden kurmak üzere cihazınızda Şirket Portalı uygulamasını açın ve cihazınız için Ayarları Denetle’ye dokunun.*

#### <a name="revoke-ios-vpp-app-license----1863797---"></a>iOS VPP uygulama lisansını iptal etme <!-- 1863797 -->
Yönetici olarak, bir kullanıcı veya cihaza atanmış olan iOS VPP uygulama lisansını geri kazanabilirsiniz. iOS VPP uygulamasını kaldırmak uygulama lisansını geri kazanmanıza da olanak tanıyacak. Uygulamayı kaldırmadan önce, kullanıcının veya cihazın uygulamayla hedeflenen gruptan kaldırılması gerekir. Kullanıcı veya cihazın gruptan kaldırılması, uygulamanın yeniden yüklenmesini önler. Bu adımlar tamamlandıktan sonra, uygulama lisansını başka bir kullanıcı veya cihaza atamayı seçebilirsiniz. iOS VPP uygulama lisansları hakkında daha fazla bilgi için bkz. [Microsoft Intune'da toplu satın alınan iOS uygulamalarını yönetme](vpp-apps-ios.md).

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="select-device-categories-by-using-the-access-work-or-school-settings----1058963-eenotready---"></a>İş Yeri veya Okula Erişme ayarlarını kullanarak cihaz kategorilerini seçme <!-- 1058963 eenotready --> 
[Cihaz grubu eşlemeyi](https://docs.microsoft.com/intune/device-group-mapping) etkinleştirdiyseniz, Windows 10'daki kullanıcılardan şimdi **Ayarlar** > **Hesaplar** > **İş yeri veya okula eriş** altındaki **Bağlan** düğmesi aracılığıyla kaydolduktan sona cihaz kategorisini seçmeleri istenecek. 

#### <a name="use-samaccountname-as-the-account-username-for-email-profiles----1500307---"></a>E-posta profilleri için hesap kullanıcı adı olarak sAMAccountName kullanın <!-- 1500307 -->
Android, iOS ve Windows 10'da e-posta profillerinin hesap kullanıcı adı olarak şirket içi **sAMAccountName** adını kullanabilirsiniz. Ayrıca Azure Active Directory'de (Azure AD) `domain`.veya `ntdomain` özniteliğinden etki alanını da alabilirsiniz. Bunun yerine özel bir statik etki alanı girebilirsiniz.

Bu özelliği kullanmak için, şirket içi Active Directory ortamınızdan Azure AD'ye `sAMAccountName` özniteliğini eşitlemeniz gerekir.

Şunlar için geçerlidir: [Android](email-settings-android.md), [iOS](email-settings-ios.md), [Windows 10 ve üzeri](email-settings-windows-10.md)

#### <a name="see-device-configuration-profiles-in-conflict----1556983---"></a>Çakışması olan cihaz yapılandırma profillerini görme <!-- 1556983 -->
**Cihaz Yapılandırması**’nda mevcut profillerin bir listesi gösterilir. Bu güncelleştirme ile çakışması olan profiller hakkında ayrıntılar sağlayan yeni bir sütun eklenir. Çakışması olan ayarı ve profili görmek için çakışan bir satırı seçebilirsiniz. 

[Yapılandırma profillerini yönetme](device-profile-monitor.md#view-conflicts) başlığı altında daha fazla bilgi edinebilirsiniz.

#### <a name="new-status-for-devices-in-device-compliance----2308882---"></a>Cihaz uyumluluğunda cihazlar için yeni durum <!-- 2308882 -->
**Cihaz uyumluluğu** > **İlkeler**'de bir ilke seçin ve **Genel Bakış**’ı seçin; aşağıdaki yeni durumlar eklenir:
- Başarılı oldu
- hata
- çakışma
- Beklemede
- uygulanamaz Farklı bir platformun cihaz sayısını gösteren bir resim de görüntülenir. Örneğin bir iOS profiline bakıyorsanız, yeni kutucuk yine bu profile atanmış olan iOS dışı cihazların sayısını gösterir. Bkz. [Cihaz uyumluluk ilkeleri](compliance-policy-monitor.md#view-status-of-device-policies).

#### <a name="device-compliance-supports-3rd-party-anti-virus-solutions----2325484---"></a>Cihaz uyumluluğu üçüncü taraf virüsten koruma çözümlerini destekler <!-- 2325484 -->
Cihaz uyumluluk ilkesi oluşturduğunuzda (**cihaz uyumluluğu** > **ilkeleri** > **ilkesi oluşturma**  >  **Platformu: Windows 10 ve üzeri** > **ayarları** > **sistem güvenliği**), vardır yeni **[cihaz güvenliği](compliance-policy-create-windows.md#windows-10-and-later-policy-settings)** seçenekleri: 
- **Virüsten koruma**: Ayarlandığında **gerektiren**, uyumluluk Windows Symantec ve Windows Defender gibi Güvenlik Merkezi ile kaydedilen virüsten koruma çözümleri kullanarak denetleyebilirsiniz. 
- **Casus yazılımdan koruma**: Ayarlandığında **gerektiren**, uyumluluk Windows Symantec ve Windows Defender gibi Güvenlik Merkezi ile kaydedilen casus yazılımdan koruma çözümlerini kullanarak denetleyebilirsiniz. 

Uygulama hedefi: Windows 10 ve üzeri 

### <a name="device-enrollment"></a>Cihaz kaydı

####  <a name="devices-without-profiles-column-in-the-list-of-enrollment-program-tokens----1853904---"></a>Kayıt programı belirteçleri listesinde profil sütunu olmayan cihazlar <!-- 1853904 -->
Kayıt programı belirteçleri listesinde, profil atanmamış olan cihazların sayısını gösteren yeni bir sütun vardır. Bu, yöneticilerin bu cihazları kullanıcılara teslim etmeden önce bunlara profil atamasına yardımcı olur. Yeni sütunu görmek için, **Cihaz kaydı** > **Apple kaydı** > **Kayıt programı belirteçleri**'ne gidin.

### <a name="device-management"></a>Cihaz yönetimi

#### <a name="google-name-changes-for-android-for-work-and-play-for-work---842873---"></a>Android for Work ve Play for Work için Google ad değişiklikleri <!--842873 -->
Intune, "Android for Work" terminolojisini Google marka değişikliklerini yansıtacak şekilde güncelleştirdi. "Android for Work" ve "Play for Work" terimleri artık kullanılmıyor. Bağlama göre farklı bir terminoloji kullanılıyor:
- "Android kurumsal", genel olarak modern Android yönetim yığınına karşılık gelir.
- "İş profili" veya "Profil Sahibi", iş profilleriyle yönetilen KCG cihazlarına karşılık gelir.
- "Yönetilen Google Play", Google uygulama mağazasına karşılık gelir.

#### <a name="rules-for-removing-devices----1609459---"></a>Cihaz kaldırma kuralları <!-- 1609459 -->
Ayarladığınız süre boyunca (gün) iade edilmeyen cihazları otomatik olarak kaldırmanıza olanak tanıyan yeni kurallar kullanılabilir. Yeni kuralı görmek için **Intune** bölmesine gidin, **Cihazlar**’ı ve **Cihaz temizleme kuralları**’nı seçin.

#### <a name="corporate-owned-single-use-support-for-android-devices----1630973---"></a>Android cihazlar için şirkete ait, tek kullanım desteği <!-- 1630973 -->

Intune şimdi üst düzeyde yönetilen, kilitlenen, bilgi noktası stilindeki Android cihazlarını destekler. Bu sayede yöneticiler cihazın kullanımını tek uygulamayla veya küçük bir uygulama kümesiyle kilitleyebilir ve kullanıcıların cihazda başka uygulamaları etkinleştirmesini veya başka eylemler gerçekleştirmesini engelleyebilir. Android kiosku ayarlamak için, Intune > **Cihaz kaydı** > **Android kaydı** > **Kiosk ve görev cihazı kayıtları**'na gidin. Daha fazla bilgi için bkz. [Android kurumsal kiosk cihazlarının kaydını ayarlama](android-kiosk-enroll.md).

#### <a name="per-row-review-of-duplicate-corporate-device-identifiers-uploaded----2203794--"></a>Karşıya yüklenmiş yinelen şirket cihazı tanımlayıcılarını satır temelinde gözden geçirme <!-- 2203794-->
Şirket kimliklerini karşıya yüklerken, Intune şimdi tüm yinelemelerin listesini sağlar ve size mevcut bilgileri değiştirme veya koruma seçeneği verir. **Cihaz kaydı** > **Şirket Cihazı Tanımlayıcıları** > **Tanımlayıcıları Ekle**'yi seçtikten sonra yinelemeler varsa rapor görüntülenecek. 

#### <a name="manually-add-corporate-device-identifiers----2203803---"></a>Şirket cihazı tanımlayıcılarını el ile ekleme <!-- 2203803 -->
Şimdi şirket cihazı kimliklerini el ile ekleyebilirsiniz. **Cihaz kaydı** > **Şirket Cihazı Tanımlayıcıları** > **Ekle**'yi seçin. 

## <a name="week-of-june-25-2018"></a>25 Haziran 2018 Haftası

### <a name="pradeo---new-mobile-threat-defense-partner----1169249---"></a>Pradeo - Yeni Mobile Threat Defense iş ortağı <!-- 1169249 -->

Microsoft Intune ile tümleşik çalışan Mobile Threat Defense çözümü Pradeo tarafından gerçekleştirilen risk değerlendirmesine dayalı koşullu erişimi kullanarak mobil cihazlardan şirket kaynaklarına erişimi denetleyebilirsiniz.

## <a name="week-of-june-18-2018"></a>18 Haziran 2018 haftası

### <a name="microsoft-edge-mobile-support-for-intune-app-protection-policies----1817882---"></a>Intune uygulama koruma ilkeleri için Microsoft Edge mobil desteği <!-- 1817882 -->

Mobil cihazlar için Microsoft Edge tarayıcısı, artık Intune’da tanımlanan uygulama koruma ilkelerini destekliyor.

## <a name="week-of-june-11-2018"></a>11 Haziran 2018 haftası

### <a name="use-fips-mode-with-the-ndes-certificate-connector----1333688---"></a>NDES Sertifika bağlayıcısında FIPS modunu kullanma <!-- 1333688 -->
NDES Sertifika bağlayıcısını Federal Bilgi İşleme Standardı (FIPS) modu etkin bir bilgisayara yüklediğinizde, sertifika verme ve iptal etme işlemleri beklendiği gibi çalışmıyordu. Bu güncelleştirmeyle birlikte FIPS desteği, NDES Sertifika bağlayıcısına eklenmiştir. 

Bu güncelleştirme ayrıca şunları içerir:

- NDES Sertifika bağlayıcısı; Windows Server 2016 ve Windows Server 2012 R2’ye otomatik olarak dahil edilen .NET 4.5 Framework’ü gerektirir. Önceden .NET 3.5 Framework, gereken en düşük sürümdü.
- TLS 1.2 desteği, NDES Sertifika Bağlayıcısına dahil edilmiştir. Bu nedenle NDES Sertifika bağlayıcısı yüklü olan sunucu TLS 1.2’yi destekliyorsa TLS 1.2 kullanılır. Sunucu TLS 1.2 desteklemiyorsa TLS 1.1 kullanılır. Şu anda TLS 1.1, cihazlar ve sunucu arasında kimlik doğrulaması için kullanılmaktadır.

Daha fazla bilgi için bkz. [SCEP sertifikalarını yapılandırma ve kullanma](certificates-scep-configure.md) ve [PKCS sertifikalarını yapılandırma ve kullanma](certficates-pfx-configure.md).

## <a name="week-of-june-4-2018"></a>4 Haziran 2018 haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="retrieve-the-associated-app-user-model-id-aumid-for-microsoft-store-for-business-apps-in-kiosk-mode----1560077----"></a>İş İçin Microsoft Store uygulamaları için bilgi noktası modunda ilişkili uygulama kullanıcı model kimliğini (AUMID) alma <!-- 1560077 ! -->
Intune artık bilgi noktası profilinde daha iyi bir yapılandırma sağlamak amacıyla İş İçin Microsoft Store (WSfB) uygulamaları için uygulama kullanıcı model kimliğini (AUMID) alabilir.

İş İçin Microsoft Store uygulamaları hakkında daha fazla bilgi için bkz. [İş İçin Microsoft Store’dan uygulamaları yönetme](windows-store-for-business.md).

#### <a name="new-company-portal-branding-page----1916370---"></a>Yeni Şirket Portalı markalama sayfası <!-- 1916370 -->
Şirket Portalı markalama sayfasının yeni bir düzeni, iletileri ve araç ipuçları vardır.


### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="support-for-palo-alto-networks-globalprotect-vpn-profiles----1333680----"></a>Palo Alto Networks GlobalProtect VPN profilleri için destek <!-- 1333680 ! -->
Bu güncelleştirme ile Intune’da VPN profilleri için VPN bağlantısı olarak Palo Alto Networks GlobalProtect’i seçebilirsiniz (**Cihaz yapılandırması** > **Profiller** > **Profil oluştur** > **Profil türü** > **VPN**). Bu sürümde aşağıdaki platformlar desteklenir: 

- iOS
- Windows 10

#### <a name="additions-to-local-device-security-options-settings----1403702---"></a>Yerel Cihaz Güvenliği Seçenekleri ayarlarına ekler <!-- 1403702 -->
Artık Windows 10 cihazları için ek Yerel Cihaz Güvenliği Seçenekleri ayarları yapılandırabilirsiniz. Ek ayarlar; Microsoft Ağ İstemcisi, Microsoft Ağ Sunucusu, Ağ erişimi ve güvenlik ve Etkileşimli oturum açma bölümlerinde kullanılabilir. Bu ayarları, bir Windows 10 cihaz yapılandırma ilkesi oluşturduğunuzda Endpoint Protection kategorisinde bulabilirsiniz.

#### <a name="enable-kiosk-mode-on-windows-10-devices----1560072----"></a>Windows 10 cihazlarda bilgi noktası modunu etkinleştirme <!-- 1560072 ! -->
Windows 10 cihazlarda bir yapılandırma profili oluşturabilir ve bilgi noktası modunu etkinleştirebilirsiniz (**Cihaz Yapılandırması** > **Profiller** > **Profil oluştur** > **Windows 10** > **Cihaz Kısıtlamaları** > **Bilgi noktası**). Bu güncelleştirmede **Bilgi noktası (önizleme)** ayarı, **Bilgi noktası (kullanılmayan)** olarak yeniden adlandırıldı. **Bilgi noktası (kullanılmayan)**, artık kullanım için önerilmese de Temmuz güncelleştirmesine kadar işlevselliğini koruyacaktır. **Bilgi noktası (kullanılmayan)**, yeni **Bilgi noktası** türü (**Profil oluştur** > **Windows 10** > **Bilgi noktası (önizleme)**) ile değiştirilmiştir. Bu yeni tür, Windows 10 RS4 ve üzeri sürümlerde Bilgi Noktalarını yapılandırmak üzere ayarlar içerecektir.

Windows 10 ve üzeri için geçerlidir.

#### <a name="device-profile-graphical-user-chart-is-back----2160133---"></a>Cihaz profili kullanıcı grafiği geri geldi <!-- 2160133 -->
Cihaz profili grafiğinde (**Cihaz yapılandırması** > **Profiller** > mevcut bir profil seçin > **Genel bakış**) gösterilen sayısal değerleri geliştirirken, kullanıcı grafiği geçici olarak kaldırılmıştı.

Bu güncelleştirmeyle birlikte kullanıcı grafiği geri geldi ve Azure portalında gösteriliyor.

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="support-for-windows-autopilot-enrollment-without-user-authentication----1165118---"></a>Kullanıcı kimlik doğrulaması olmadan Windows Autopilot kaydı desteği <!-- 1165118 -->
Intune şimdi kullanıcı kimlik doğrulaması olmadan Windows Autopilot kaydını destekliyor. Bu, Windows Autopilot dağıtım profilinde "Autopilot Dağıtım modu" değerinin "Kendi Kendine Dağıtım" olduğu yeni bir seçenektir.  Bu kayıt türünü başarıyla tamamlamak için cihaz, Windows 10 Insider Preview Derleme 17672 veya üzeri çalıştırmalı ve TPM 2.0 yongasına sahip olmalıdır. Kullanıcı kimlik doğrulaması gerekmediğinden, bu seçeneği yalnızca üzerinde fiziksel denetim sahibi olduğunuz cihazlara atamalısınız.

#### <a name="new-languageregion-setting-when-configuring-oobe-for-autopilot----1821766---"></a>Autopilot için OOBE yapılandırırken yeni dil / bölge ayarı <!-- 1821766 -->
Autopilot profilleri için İlk Çalıştırma Deneyimi sırasında dili ve bölgeyi ayarlamak için yeni bir yapılandırma ayarı kullanılabilir. Yeni ayarı görmek için, **Cihaz kaydı** > **Windows kaydı** > **Dağıtım profilleri** > **Profil oluştur** > **Dağıtım modu** = **Kendi kendine dağıtım** > **Varsayılanlar yapılandırıldı** öğesini seçin.

#### <a name="new-setting-for-configuring-device-keyboard----1821768---"></a>Cihaz klavyesini yapılandırmak için yeni ayar <!-- 1821768 -->
Autopilot profilleri için İlk Çalıştırma Deneyimi sırasında klavyeyi yapılandırmak için yeni bir ayar kullanılabilir olacak. Yeni ayarı görmek için, **Cihaz kaydı** > **Windows kaydı** > **Dağıtım profilleri** > **Profil oluştur** > **Dağıtım modu** = **Kendi kendine dağıtım** > **Varsayılanlar yapılandırıldı** öğesini seçin.

#### <a name="autopilot-profiles-moving-to-group-targeting----1877935---"></a>Autopilot profilleri grup hedeflemeye taşınıyor <!-- 1877935 -->
AutoPilot dağıtım profilleri AutoPilot cihazları içeren Azure AD gruplarına atanabilir.

### <a name="device-management"></a>Cihaz yönetimi

#### <a name="set-compliance-by-device-location----851881----"></a>Cihaz konumuna göre uyumluluk ayarlama <!-- 851881 ! -->
Bazı durumlarda, ağ bağlantısı tarafından belirlenen bir konumdan şirket kaynaklarına erişimi kısıtlamak isteyebilirsiniz. Artık cihazın IP adresine bağlı olarak bir uyumluluk ilkesi (**Cihaz uyumluluğu** > **Konumlar**) oluşturabilirsiniz. Cihaz, IP aralığı dışına çıktığında şirket kaynaklarına erişemez.

Uygulama hedefi: Android cihazlar 6.0 ve üzeri, güncelleştirilmiş Şirket Portalı uygulaması ile

#### <a name="prevent-consumer-apps-and-experiences-on-windows-10-enterprise-rs4-autopilot-devices---1621980---"></a>Windows 10 Enterprise RS4 Autopilot cihazlarda tüketici uygulamaları ve deneyimlerini engelleme<!-- 1621980 -->
Windows 10 Enterprise RS4 AutoPilot cihazlarınızda tüketici uygulama ve deneyimlerinin yüklenmesini önleyebileceksiniz. Bu özelliği görmek için **Intune** > **Cihaz yapılandırması** > **Profiller** > **Profil oluştur** > **Platform** = **Windows 10 veya üzeri** > **Profil türü** = **Cihaz kısıtlamaları** > **Yapılandır** > **Windows Spot** > **Tüketici özellikleri**'ne gidin. 

#### <a name="uninstall-the-latest-from-windows-10-software-updates----1732948---"></a>En son Windows 10 yazılım güncelleştirmesini kaldırma <!-- 1732948 -->
Windows 10 makinelerinizde çalışmanın kesilmesine neden olan bir sorun keşfederseniz, en son özellik güncelleştirmesini veya en son kalite güncelleştirmesini kaldırmayı (geri almayı) seçebilirsiniz. Özellik veya kalite güncelleştirmesini kaldırma işlemi yalnızca hizmetin içinde açıldığı hizmet kanalında kullanılabilir. Kaldırma işlemi Windows 10 makinelerinizde önceki güncelleştirmeyi geri yüklemeye yönelik bir ilkeyi tetikler. Özellik güncelleştirmeleri için, en son sürümü kaldırma işleminin uygulanabilme süresini 2-60 gün arasıyla sınırlandırabilirsiniz. Yazılım güncelleştirmesini kaldırma seçeneklerini ayarlamak için, Azure portalının içindeki **Microsoft Intune** dikey penceresinden **Yazılım güncelleştirmeleri**'ni seçin. Ardından, **Yazılım güncelleştirmeleri** dikey penceresinden **Windows 10 Güncelleştirme Kademeleri**'ni seçin. Daha sonra da **Genel Bakış** bölümünde **Kaldır** seçeneğini belirtebilirsiniz.

#### <a name="search-all-devices-for-imei-and-serial-number----1793685---"></a>IMEI ve seri numarası için tüm cihazlarda arama yapma <!-- 1793685 -->
Artık Tüm cihazlar dikey penceresinde IMEI ve seri numaraları için arama yapabilirsiniz (e-posta, UPN, cihaz adı ve yönetim adı da hala kullanılabilir). Intune'da **Cihazlar** > **Tüm cihazlar**'ı seçin ve arama kutusuna aramanızı girin.

#### <a name="management-name-field-will-be-editable----1875989---"></a>Yönetim adı alanı düzenlenebilir olacak <!-- 1875989 -->
Artık bir cihazın **Özellikler** dikey penceresindeki yönetim adı alanını düzenleyebilirsiniz. Bu alanı düzenlemek için **Cihazlar** > **Tüm cihazlar** > cihazı seçin > **Özellikler** seçeneğini belirleyin. Bir cihazı benzersiz olarak tanımlamak için yönetim adı alanını kullanabilirsiniz.

#### <a name="new-all-devices-filter-device-category----1878520---"></a>Yeni tüm cihazları Filtresi: Cihaz kategorisi <!-- 1878520 -->
Şimdi **Tüm cihazlar** listesini cihaz kategorisine göre filtreleyebilirsiniz. Bunu yapmak için, **Cihazlar** > **Tüm cihazlar** > **Filtre** > **Cihaz kategorisi**'ni seçin.

#### <a name="use-teamviewer-to-screen-share-ios-and-macos-devices----1985547---"></a>iOS ve MacOS cihazlarda ekran paylaşımı için TeamViewer kullanma <!-- 1985547 -->
Artık yöneticiler, [TeamViewer](device-profile-android-teamviewer.md)’a bağlanıp iOS ve macOS cihazlarla bir ekran paylaşma oturumu başlatabilir. iPhone, iPad ve macOS kullanıcıları, diğer herhangi bir masaüstü veya mobil cihazla ekranlarını canlı olarak paylaşabilecek. 

#### <a name="multiple-exchange-connector-support----2070451---"></a>Birden çok Exchange Connector desteği <!-- 2070451 -->
Artık kiracı başına tek bir Microsoft Intune Exchange Connector’la sınırlı değilsiniz. Intune, birden çok Exchange Connector’ı desteklediği için Intune koşullu erişimini birden çok şirket içi Exchange kuruluşunda ayarlayabilirsiniz.

Intune şirket içi Exchange bağlayıcısıyla, cihazın Intune'a kayıtlı olup olmadığına ve Intune cihaz uyumluluk ilkelerine uyup uymadığına bağlı olarak şirket içi Exchange posta kutularınıza cihaz erişimini ayarlayabilirsiniz. Bağlayıcıyı ayarlamak için, Intune şirket içi Exchange bağlayıcısını Azure portalından indirir ve Exchange kuruluşunuzdaki bir sunucuya yüklersiniz. Microsoft Intune panosunda **Şirket içi erişim**'i seçin ve ardından **Kurulum**'un altında **Exchange ActiveSync bağlayıcısı**'nı seçin. Exchange şirket içi bağlayıcısını indirin ve Exchange kuruluşunuzdaki bir sunucuya yükleyin. Artık kiracı başına tek Exchange bağlayıcısıyla sınırlı olmadığınıza göre, başka Exchange kuruluşlarınız varsa her ek Exchange kuruluşu için aynı süreci izleyip bağlayıcı indirebilir ve yükleyebilirsiniz.

#### <a name="new-device-hardware-detail-ccid----2156657---"></a>Yeni cihaz donanım Ayrıntısı: CCID <!-- 2156657 -->
Çip Kartı Arabirim Cihazı (CCID) bilgileri şimdi her cihaza eklendi. Bunu görmek için, **Cihazlar** > **Tüm cihazlar**'ı seçin, bir cihaz belirtin, **Donanım**'ı seçin ve **Ağ ayrıntıları**>'nın altına bakın.

#### <a name="assign-all-users-and-all-devices-as-scope-groups----2196803---"></a>Tüm kullanıcıları ve tüm cihazları kapsam grupları olarak atama <!-- 2196803 -->
Şimdi tüm kullanıcıları, tüm cihazları ve tüm kullanıcılar ile tüm cihazları kapsam gruplarına atayabilirsiniz. Bunu yapmak için **Intune rolleri** > **Tüm roller** > **İlke ve profil yöneticisi** > **Atamalar** > atama seçin > **Kapsam (gruplar)** öğesini seçin.

#### <a name="udid-information-now-included-for-ios-and-macos-devices----2219806---"></a>Şimdi iOS ve macOS cihazlar için UDID bilgileri eklendi <!-- 2219806 -->
iOS ve macOS cihazlarının Benzersiz Cihaz Tanımlayıcısını (UDID) görmek için, **Cihazlar** > **Tüm cihazlar** > cihaz seçin > **Donanım**'a gidin. UDID yalnızca şirket cihazları için sağlanır (şirket cihazları **Cihazlar** > **Tüm cihazlar** > bir cihaz seçin > **Özellikler** > **Cihaz sahipliği** altında ayarlanır).

### <a name="intune-apps"></a>Intune uygulamaları

#### <a name="improved-troubleshooting-for-app-installation----928990---"></a>Uygulama yüklemesi için geliştirilmiş sorun giderme <!-- 928990 -->
Microsoft Intune MDM ile yönetilen cihazlarda bazen uygulama yüklemeleri başarısız olabilir. Bu uygulamaların yüklemesi başarısız olduğunda, başarısızlık sebebini anlamak ve sorunu gidermek zor olabilir. Uygulama Sorun Giderme özelliklerimizin bir Genel Önizlemesini yayınlıyoruz. Tüm cihazlarda **Yönetilen Uygulamalar** adlı yeni bir düğüm göreceksiniz. Bu düğümde Intune MDM yoluyla teslim edilen uygulamalar listelenir. Burada uygulama yükleme durumlarının bir listesini bulacaksınız. Bir uygulamayı seçtiğinizde, o uygulamaya özel sorun giderme görünümünü açmış olacaksınız. Sorun giderme görünümünde uygulamanın oluşturulma, değiştirilme, hedeflenme ve cihaza teslim edilme tarihleri gibi uçtan uca yaşam döngüsünü bulabileceksiniz. Buna ek olarak, uygulama yüklemesinin başarısız olması durumunda size bir hata kodu ve hatanın sebebiyle ilgili yardım olacak bir ileti sunulacak. 

#### <a name="intune-app-protection-policies-and-microsoft-edge----1818968---"></a>Intune uygulama koruma ilkeleri ve Microsoft Edge <!-- 1818968 -->
Mobil cihazlar (iOS ve Android) için Microsoft Edge tarayıcısı, artık Microsoft Intune uygulama koruma ilkelerini destekliyor. Şirket Azure AD hesaplarıyla Edge uygulamasında oturum açan iOS ve Android cihazı kullanıcıları, Intune tarafından korunacak. iOS cihazlarında **Web içeriği için yönetilen tarayıcı iste** ilkesi, Microsoft Edge yönetildiğinde kullanıcıların bu tarayıcıda bağlantı açmasına olanak tanıyacak.

## <a name="week-of-may-14-2018"></a>14 Mayıs 2018 Haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="require-installation-of-policies-apps-certificate-and-network-profiles----1553555---"></a>İlkelerin, uygulamaların, sertifika ve ağ profillerinin yüklenmesini gerektirme <!-- 1553555 -->

Intune, AutoPilot cihazlar sağlanırken ilkeleri, uygulamaları ve sertifika ve ağ profillerini yükleyene kadar yöneticiler; son kullanıcıların Windows 10 RS4 masaüstüne erişimini engelleyebilecek. Daha fazla bilgi için bkz. [Kayıt durum sayfası ayarlama](windows-enrollment-status.md).

#### <a name="configuring-your-app-protection-policies----2144597-part-2---"></a>Uygulama koruma ilkelerinizi yapılandırma <!-- 2144597 Part 2 -->

Azure portalında, Intune Uygulama Koruması hizmet dikey penceresine gitmek yerine artık yalnızca Intune’a gidersiniz. Intune içinde artık uygulama koruma ilkeleri için yalnızca bir konum bulunur. Tüm uygulama koruma ilkelerinizin Intune’da **Uygulama koruma ilkeleri** altındaki **Mobil uygulama** dikey penceresinde olduğuna dikkat edin. Bu tümleştirme, bulut yönetim idaresini basitleştirmenize yardımcı olur. Tüm uygulama koruma ilkelerinin zaten Intune’da olduğunu ve önceden yapılandırılan tüm ilkelerinizi değiştirebileceğinizi unutmayın. Intune Uygulama İlkesi Koruma (APP) ve Koşullu Erişim (CA) ilkeleri artık **Microsoft Intune** dikey penceresinin **Yönet** bölümü altında veya **Azure Active Directory** dikey penceresinin **Güvenlik** bölümü altında bulunan **Koşullu Erişim** bölümü altındadır. Koşullu erişim ilkelerini değiştirme hakkında daha fazla bilgi için bkz. [Azure Active Directory’de koşullu erişim](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal). Daha fazla bilgi için bkz. [Uygulama koruma ilkeleri nedir?](app-protection-policy.md)

## <a name="week-of-may-7-2018"></a>7 Mayıs 2018 Haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="samsung-knox-mobile-enrollment-support---1112863--"></a>Samsung Knox mobil kayıt desteği <!--1112863-->

Intune’u Samsung Knox Mobil Kayıt (KME) ile birlikte kullanarak çok sayıda şirkete ait Android cihazları kaydedebilirsiniz. WiFi veya hücresel ağ kullanan kullanıcılar, cihazlarını ilk kez açtıklarında yalnızca birkaç dokunuşla kayıt yapabilir. Knox Dağıtım Uygulaması’nı kullanırken Bluetooth veya NFC yoluyla cihazlar kaydedilebilir. Daha fazla bilgi için bkz. [Android cihazları Samsung’un Knox Mobil Kayıt özelliğini kullanarak otomatik kaydetme](android-samsung-knox-mobile-enroll.md).

#### <a name="requesting-help-in-the-company-portal-for-windows-10----1874137---"></a>Windows 10 için Şirket Portalı uygulamasında yardım isteme <!-- 1874137 -->

Kullanıcı bir sorun hakkında yardım almak için iş akışı başlattığında Windows 10 için Şirket Portalı uygulaması artık uygulama günlüklerini doğrudan Microsoft’a gönderecek. Böylece Microsoft’a bildirilen sorunların giderilmesi ve çözülmesi daha kolay olacak.

## <a name="week-of-april-23-2018"></a>23 Nisan 2018 Haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="passcode-support-for-mam-pin-on-android---1438086---"></a>Android’de MAM PIN’i için geçiş kodu desteği<!-- 1438086 -->

Intune yöneticileri, sayısal MAM PIN’i yerine geçiş kodu zorlamak için bir uygulama başlatma gereksinimi ayarlayabilir. Bu gereksinim ayarlanırsa kullanıcının, MAM etkin uygulamalara erişim almadan önce bir geçiş kodu ayarlaması ve istendiğinde bunu kullanması gerekir. Geçiş kodu, en az bir özel karakter veya büyük/küçük harf içeren sayısal PIN’dir. Intune, sayısal PIN’e benzer bir şekilde geçiş kodunu destekler. Uzunluk alt sınırı belirler ve yönetici konsolunda karakter ile dizi tekrarlarına izin verir. Bu özellik, Android’de Şirket Portalı’nın en son sürümünü gerektirir. Bu özellik, iOS için zaten kullanılabilir durumdadır.

#### <a name="line-of-business-lob-app-support-for-macos----1473977---"></a>macOS için iş kolu (LOB) uygulamaları desteği <!-- 1473977 -->
Microsoft Intune, macOS LOB uygulamalarını Azure portalından yükleme olanağı sağlayacak. GitHub’da bulunan araç tarafından ön işlemden geçtikten sonra macOS LOB uygulamasını Intune’a ekleyebileceksiniz. Azure portalının **Intune** dikey penceresinden **İstemci uygulamaları**’nı seçin. **İstemci uygulamaları** dikey penceresinde **Uygulamalar** > **Ekle**’yi seçin. **Uygulama Ekle** dikey penceresinde, **İş kolu uygulaması**’nı seçin. 

#### <a name="built-in-all-users-and-all-devices-group-for-android-enterprise-work-profile-app-assignment----1813073---"></a>Android Kurumsal iş profili uygulama ataması için yerleşik Tüm Kullanıcılar ve Tüm Cihazlar Grubu <!-- 1813073 -->
Android Kurumsal iş profili uygulama ataması için yerleşik **Tüm Kullanıcılar** ve **Tüm Cihazlar** gruplarından yararlanabilirsiniz. Daha fazla bilgi için bkz. [Microsoft Intune’da uygulama atamalarını dahil etme ve dışlama](apps-inc-exl-assignments.md).

#### <a name="intune-will-reinstall-required-apps-that-are-uninstalled-by-users----1947010---"></a>Intune, kullanıcılar tarafından kaldırılan gerekli uygulamaları yeniden yükleyecek <!-- 1947010 -->
Son kullanıcı gerekli bir uygulamayı kaldırırsa Intune, 7 günlük yeniden değerlendirme döngüsünü beklemek yerine 24 saat içerisinde bu uygulamayı otomatik olarak yeniden yükler.

### <a name="device-configuration"></a>Cihaz yapılandırması

####  <a name="device-profile-chart-and-status-list-show-all-devices-in-a-group----1449153---"></a>Cihaz profil grafiği ve durum listesi bir gruptaki tüm cihazları gösterir <!-- 1449153 -->
Bir cihaz profili yapılandırdığınızda (**Cihaz yapılandırması** > **Profiller**), iOS gibi bir cihaz profili seçersiniz. Bu profili, iOS ve iOS olmayan cihazlar barındıran bir gruba atarsınız. Grafikteki sayı, profilin uygulandığı iOS *ve* iOS olmayan cihazları gösterir (**Cihaz yapılandırması** > **Profiller** > mevcut bir profili seçin > **Genel bakış**). **Genel bakış** sekmesinde grafiği seçtiğinizde, **Cihaz durumu** yalnızca gruptaki iOS cihazları değil, tüm cihazları listeler. 

Bu güncelleştirme ile grafik (**Cihaz yapılandırması** > **Profiller** > mevcut bir profili seçin > **Genel bakış**) yalnızca belirli bir cihaz profili sayısını gösterir. Örneğin yapılandırma cihaz profili iOS cihazlarda geçerliyse grafik yalnızca iOS cihaz sayısını gösterecek. Grafik seçilip **Cihaz durumu** açıldığında yalnızca iOS cihazlar listelenecek.

Bu güncelleştirme hazırlanırken kullanıcı grafiği geçici olarak kaldırılmıştır. 

#### <a name="always-on-vpn-for-windows-10---1333666---"></a>Windows 10 için Her Zaman Açık VPN <!--1333666 -->

Şu anda [Her Zaman Açık](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-auto-trigger-profile#always-on), OMA-URI kullanarak oluşturulmuş özel bir sanal özel ağ (VPN) profili ile Windows 10 cihazlarda kullanılabiliyor.

Bu güncelleştirmeyle yöneticiler, Windows 10 VPN profilleri için Her Zaman Açık’ı doğrudan Azure portalındaki Intune’da etkinleştirebilir. Her Zaman Açık VPN profilleri şu durumlarda otomatik olarak bağlanacak:

- Kullanıcılar cihazlarında oturum açtığında
- Cihazdaki ağ değiştiğinde
- Cihaz ekranı kapandıktan sonra yeniden açıldığında

#### <a name="new-printer-settings-for-education-profiles----1308900---"></a>Eğitim profilleri için yeni yazıcı ayarları <!-- 1308900 -->

Eğitim profilleri için yeni ayarlar altında kullanılabilir **Yazıcılar** kategorisi: **Yazıcılar**, **varsayılan yazıcı**, **yeni Yazıcı Ekle**.

#### <a name="show-caller-id-in-personal-profile---android-enterprise-work-profile---1098984---"></a>Kişisel profilde arayan kimliğini gösterme - Android Kurumsal iş profili <!--1098984 -->
Bir cihazda kişisel profil kullanan son kullanıcılar, işle ilgili bir kişiden gelen aramalarda arayan kimliğini göremeyebilir. 

Bu güncelleştirme ile **Android Kurumsal** > **Cihaz kısıtlamaları** > **İş profili ayarları** kısmına bunun için yeni bir ayar geldi:
- Kişisel profilde iş kişisi arayan kimliğini görüntüleme

Etkinleştirildiğinde (yapılandırılmadığında), iş kişisi arayan ayrıntıları kişisel profilde görüntülenir. Engellendiğinde ise iş kişisi arayan numarası kişisel profilde görüntülenmez. 

Uygulama hedefi: Android OS v6.0 ve üzeri sürümlerde Android iş profili cihazları

#### <a name="new-windows-defender-credential-guard-settings-added-to-endpoint-protection-settings---1102252-----from-1802-and-1804--"></a>Endpoint Protection ayarlarına yeni Windows Defender Credential Guard ayarları eklendi <!--1102252 --><!--from 1802 and 1804-->

Bu güncelleştirmeyle, [Windows Defender Credential Guard](https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard) (**Cihaz yapılandırması** > **Profiller** > **Endpoint Protection**) aşağıdaki ayarları içerir: 

- **Windows Defender Credential Guard**: Sanallaştırma tabanlı güvenlik ile Credential Guard açar. Bu özelliğin etkinleştirilmesi, **Güvenli Önyükleme ile Platform Güvenlik Düzeyi** ve **Sanallaştırma Tabanlı Güvenlik** ayarının her ikisi de etkinleştirildiğinde bir sonraki önyüklemede kimlik bilgilerinin korunmasına yardımcı olur. Şu seçenekler mevcuttur:
  - **Devre dışı bırakılmış**: Credential Guard daha önce ile açılmışsa **kilit olmadan etkin**"Credential Guard uzaktan kapatır seçeneği.

  - **UEFI kilidi ile etkin**: Credential Guard bir kayıt defteri anahtarı kullanarak veya Grup İlkesi kullanılarak devre dışı bırakılamaz, sağlar. Bu ayarı kullandıktan sonra Credential Guard'ı devre dışı bırakmak için, Grup İlkesi'ni "Devre Dışı" olarak ayarlamalısınız. Ardından, fiziksel olarak kullanıcısı olan her bilgisayardan güvenlik işlevselliğini kaldırın. Bu adımlar UEFI'de kalıcı olan yapılandırmayı temizler. UEFI yapılandırması devam ettiği sürece, Credential Guard etkindir.

  - **Kilit olmadan etkin**: Credential Guard ' ın Grup İlkesi kullanılarak uzaktan devre dışı bırakılmasına olanak verir. Bu ayarı kullanan cihazların en az Windows 10 (Sürüm 1511) çalıştırıyor olması gerekir.

Credential Guard yapılandırılırken aşağıdaki bağımlı teknolojiler otomatik olarak etkinleştirilir: 

  - **Sanallaştırma tabanlı güvenlik (VBS) etkinleştirme**: Sanallaştırma tabanlı güvenlik (VBS) sonraki önyüklemede açar. Sanallaştırma tabanlı güvenlik, güvenlik hizmetlerine destek sağlamak için Windows Hiper Yöneticisi'ni kullanır ve Güvenli Önyükleme gerektirir.
  - **Güvenli Önyükleme doğrudan bellek erişimi (DMA) ile**: Güvenli Önyükleme ve doğrudan bellek erişimi ile VBS açar. DMA koruması, donanım desteği gerektirir ve yalnızca düzgün yapılandırılmış cihazlarda etkinleştirilir. 

#### <a name="use-a-custom-subject-name-on-scep-certificate----2064190---"></a>SCEP sertifikasında özel bir konu adı kullanma <!-- 2064190 -->
Bir SCEP sertifika profilinde özel bir konuda **OnPremisesSamAccountName** ortak adını kullanabilirsiniz. Örneğin `CN={OnPremisesSamAccountName})` kullanabilirsiniz.

####  <a name="block-camera-and-screen-captures-on-android-enterprise-work-profiles----1098977---"></a>Android Kurumsal iş profillerinde kamera ve ekran yakalamayı engelleme <!-- 1098977 -->
Android cihazlar için cihaz kısıtlamaları yapılandırırken iki yeni engelleme özelliği kullanılabilir: 
- Kamera: Cihazdaki tüm kameralara erişimi engeller
- Ekran yakalama: Ekran yakalamayı engeller ve ayrıca güvenli bir video çıkışına sahip olmayan görüntü cihazlarında gösterilen içeriği engeller

Android Kurumsal iş profili cihazlarda geçerlidir.


### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="new-enrollment-steps-for-users-on-devices-with-macos-high-sierra-10132---1734567---"></a>macOS High Sierra 10.13.2+ cihazların kullanıcıları için yeni kayıt adımları <!--1734567 -->
macOS High Sierra 10.13.2, “Kullanıcı Onaylı” MDM kaydı kavramını sundu. Onaylı kayıtlar, Intune’un güvenlik açısından hassas bazı ayarları yönetmesine izin verir. Daha fazla bilgi için Apple’ın destek belgelerine bakın: https://support.apple.com/HT208019.

macOS Şirket Portalı kullanarak kaydedilen cihazlar, son kullanıcı Sistem Tercihleri’ni açıp kendisi onay sağlamadığı sürece “Kullanıcı Onaylı Değil” olarak değerlendirilir. Bu nedenle macOS Şirket Portalı, macOS 10.13.2 ve üzeri cihazlardaki kullanıcıları artık kayıt işleminin sonunda kayıtlarını kendileri onaylamaları için yönlendiriyor. Kayıtlı bir cihaz, kullanıcı onaylı hale gelirse Intune yönetici konsolu bunu rapor eder.



### <a name="device-management"></a>Cihaz yönetimi

#### <a name="advanced-threat-protection-atp-and-intune-are-fully-integrated----1629303---"></a>Gelişmiş Tehdit Koruması (ATP) ve Intune tamamen tümleştirilmiştir <!-- 1629303 -->

[Gelişmiş Tehdit Koruması (ATP)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/dashboard-windows-defender-advanced-threat-protection), Windows 10 cihazların risk düzeyini gösterir. Windows Defender Güvenlik Merkezi'nde (ATP portalı), Microsoft Intune'a bir bağlantı oluşturabilirsiniz. Oluşturulduktan sonra, kabul edilebilir tehdit düzeyini saptamak için bir Intune uyumluluk ilkesi kullanılır. Tehdit düzeyi aşılırsa, Azure Active Directory (AD) koşullu erişim ilkesi kuruluşunuz içindeki farklı uygulamalara erişimi engelleyebilir.

Bu özellik Windows 10 cihazlarınızda ATP'nin dosyaları taramasına, tehditleri algılamasına ve riskleri raporlamasına olanak tanır.

Bkz. [Intune’da ATP’yi koşullu erişim ile etkinleştirme](advanced-threat-protection.md).

#### <a name="support-for-user-less-devices----1637553---"></a>Kullanıcısız cihazlar için destek <!-- 1637553 -->
Intune, Microsoft Surface Hub gibi bir kullanıcısız cihazda uyumluluk değerlendirme işlevini destekler. Uyumluluk ilkesi, belirli cihazları hedefleyebilir. Böylece ilişkili kullanıcısı olmayan cihazlar için uyumluluk (ve uyumsuzluk) belirlenebilir.

#### <a name="delete-autopilot-devices----1713650---"></a>Autopilot cihazları silme <!-- 1713650 -->
Intune yöneticileri, [Autopilot cihazlarını silebilir](enrollment-autopilot.md#delete-autopilot-devices).

#### <a name="improved-device-deletion-experience---1832333---"></a>Geliştirilmiş cihaz silme deneyimi <!--1832333 -->
Artık [bir cihazı Intune’dan silmeden](devices-wipe.md#delete-devices-from-the-intune-portal) önce şirket verilerini kaldırmanız veya cihazı fabrika ayarlarına sıfırlamanız istenmez.

Yeni deneyimi görmek için Intune’da oturum açın ve şunları seçin: **Cihazlar** > **Tüm cihazlar** > cihazın adı > **Sil**.

Yine de onayı silmek/devre dışı bırakmak istiyorsanız **Sil** demeden önce standart yaşam döngüsü yolunu izleyip **Şirket verilerini kaldır** ve **Fabrika Sıfırlaması** seçeneklerini kullanabilirsiniz. 

#### <a name="play-sounds-on-ios-when-in-lost-mode----1947769---"></a>Kayıp modundayken iOS cihazda ses çalma <!-- 1947769 -->
Denetimli iOS cihazları, Mobil Cihaz Yönetimi (MDM) [Kayıp Modu](device-lost-mode.md)’ndayken bir [ses çalabilirsiniz](device-locate.md#activate-lost-mode-sound-alert-on-an-ios-device) (**Cihazlar** > **Tüm cihazlar** > bir iOS cihaz seçin > **Genel Bakış** > **Diğer**). Ses, cihaz Kayıp modundan çıkarılana veya kullanıcı sesi cihazda devre dışı bırakana kadar çalmaya devam eder. iOS 9.3 ve üzeri cihazlarda geçerlidir.

#### <a name="block-or-allow-web-results-in-searches-made-on-an-intune-device---1972804--"></a>Intune cihazında yapılan aramalarda web sonuçlarını engelleme veya bu sonuçlara izin verme <!--1972804-->

Yöneticiler şimdi cihazda yapılan aramalarda web sonuçlarını engelleyebilir.

#### <a name="improved-error-messaging-for-apple-mdm-push-certificate-upload-failure----2172331---"></a>Apple MDM Anında İletme Sertifikası karşıya yükleme başarısızlığı için iyileştirilmiş hata iletisi <!-- 2172331 -->

Hata iletisi, mevcut bir MDM sertifikası yenilenirken aynı Apple kimliğinin kullanılması gerektiğini açıklar.

#### <a name="test-the-company-portal-for-macos-on-virtual-machines----2216679---"></a>Sanal makinelerde macOS için Şirket Portalı'nı test etme <!-- 2216679 -->

BT yöneticilerinin Parallels Desktop ve VMware Fusion'daki sanal makinelerde macOS için Şirket Portalı uygulamasını test etmelerine yardımcı olacak kılavuzlar yayımladık. [Sanal macOS makinelerini test için kaydetme](macos-enroll.md#enroll-virtual-macos-machines-for-testing) başlığı altında daha fazla bilgi bulabilirsiniz.


### <a name="user-interface"></a>Kullanıcı arabirimi

#### <a name="improved-device-tiles-in-the-windows-10-company-portal---2213364---"></a>Windows 10 Şirket Portalı'nda geliştirilmiş cihaz kutucuları <!--2213364 -->

Kutucuklar görme sorunu olan kullanıcılar açısından daha erişilebilir olacak ve ekran okuma araçlarının daha iyi çalışmasını sağlayacak şekilde güncelleştirildi.

#### <a name="send-diagnostic-reports-in-company-portal-app-for-macos----2216677---"></a>macOS için Şirket Portalı uygulamasında tanılama raporu gönderme <!-- 2216677 -->
macOS cihazları için Şirket Portalı uygulaması, kullanıcıların Intune il ilgili hataları raporlama şeklini iyileştirmek için güncelleştirildi. Şirket Portalı uygulamasından çalışanlarınız şunları yapabilir:

- Tanılama raporlarını doğrudan Microsoft geliştirici ekibine gönderme.
- Bir olay kimliğini şirketinizin destek BT ekibine e-posta ile gönderme.

Daha fazla bilgi için bkz. [macOS için hataları gönderme](/intune-user-help/send-errors-macos).

#### <a name="intune-adapts-to-fluent-design-system-in-the-company-portal-app-for-windows-10----1195010---"></a>Intune, Windows 10 için Şirket Portalı uygulamasında Fluent Design System'e uyum sağlar <!-- 1195010 -->
Windows 10 için Intune Şirket Portalı, [Fluent Design System'in gezinti görünümü](https://docs.microsoft.com/windows/uwp/design/basics/navigation-basics) ile güncelleştirildi. Uygulamanın yan tarafı boyunca tüm en üst düzey sayfaların statik, dikey bir listesini göreceksiniz. Sayfaları hızla görüntülemek ve aralarında geçiş yapmak için herhangi bir bağlantıya tıklayın. Bu, Intune'da sürekli daha iyi uyarlanmış, anlayışlı ve tanıdık bir deneyim oluşturma çabalarımız kapsamında göreceğiniz birkaç güncelleştirmeden ilkidir. Güncelleştirilmiş görünümü görmek için [Uygulama kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md)’e gidin.

## <a name="week-of-april-16-2018"></a>16 Nisan 2018 Haftası

#### <a name="use-cisco-anyconnect-client-for-ios----1333708---"></a>iOS için Cisco AnyConnect istemcisini kullanma <!-- 1333708 -->

İOS için yeni bir VPN profili oluşturduğunuzda da artık iki seçenek vardır: **Cisco AnyConnect** ve **Cisco eski AnyConnect**. Cisco AnyConnect profilleri 4.0.7x ve daha yeni sürümleri destekler. Mevcut iOS Cisco AnyConnect VPN profilleri **Cisco Eski AnyConnect** olarak etiketlenir ve Cisco AnyConnect 4.0.5x ve daha eski sürümlerle bugün olduğu gibi çalışmaya devam eder.

> [!NOTE]
> Bu değişiklik yalnızca iOS'ye yöneliktir. Android, Android Kurumsal iş profilleri ve macOS platformlarında yine tek Cisco AnyConnect seçeneği olacaktır.

#### <a name="jamf-enrolled-macos-devices-can-now-register-with-intune----2370684---"></a>Jamf'ye kayıtlı macOS cihazları artık Intune ile kaydedilebilir <!-- 2370684 -->

macOS şirket portalının 1.3 ve 1.4 sürümleri Jamf cihazlarını Intune ile başarılı bir şekilde kaydedemiyordu. macOS portalının 1.4.2 sürümünde bu sorun çözüldü.


## <a name="week-of-april-9-2018"></a>9 Nisan 2018 Haftası  
#### <a name="updated-help-experience-in-company-portal-app-for-android----1631531---"></a>Android için Şirket Portalı uygulamasında güncelleştirilmiş yardım deneyimi <!-- 1631531 -->

Android platformuna yönelik en iyi uygulamalarla uyumlu olacak şekilde, Android için Şirket Portalı uygulamasında yardım deneyimini güncelleştirdik. Artık kullanıcılar uygulamada bir sorunla karşılaştıklarında **Menü** > **Yardım**’a dokunarak şunları yapabilir:
- Microsoft’a tanılama günlükleri yükleme.
- Sorunu açıklayan ve olay kimliğini içeren bir e-postayı şirket destek bölümünden birine gönderme.  

Güncelleştirilmiş deneyimi görmek için [E-posta ile günlük gönder](/intune-user-help/send-logs-to-your-it-admin-by-email-android) ve [Microsoft’a hata gönder](/intune-user-help/send-logs-to-microsoft-android)’e gidin.


#### <a name="new-enrollment-failure-trend-chart-and-failure-reasons-table----1471783---"></a>Yeni kayıt hatası eğilim grafiği ve hatanın nedenleri tablosu <!-- 1471783 -->

Kayıt Genel Bakış sayfasında kayıt hatalarının eğilimini ve hataların ilk beş sebebini görüntüleyebilirsiniz. Grafiğe veya tabloya tıklayarak sorun giderme tavsiyeleri ve düzeltme önerileri almak üzere ayrıntıları inceleyebilirsiniz.

#### <a name="update-where-to-configure-your-app-protection-policies----2144597---"></a>Uygulama koruma ilkelerinizi nerede yapılandıracağınızı güncelleştirme <!-- 2144597 -->

Azure portalındaki Microsoft Intune hizmetinde sizi geçici olarak **Intune Uygulama Koruma** hizmeti dikey penceresinden **Mobil uygulama** dikey penceresine yeniden yönlendireceğiz. Tüm uygulama koruma ilkelerinizin zaten Intune’da uygulama yapılandırması altındaki **Mobil uygulama** dikey penceresinde olduğuna dikkat edin. Intune Uygulama Koruması yerine yalnızca Intune’a gideceksiniz. Nisan 2018’de yeniden yönlendirmeyi durduracak ve **Intune Uygulama Koruması** hizmeti dikey penceresini tamamen kaldıracağız, böylece Intune’daki uygulama koruma ilkeleri yalnızca bir konumda bulunacak. 

**Bu değişiklik beni nasıl etkileyecek?**
Bu değişiklik, hem tek başına Intune müşterilerini hem de karma (Configuration Manager ile Intune) müşterileri etkileyecek. Bu tümleştirme, bulut yönetim idaresini basitleştirmenize yardımcı olacak.

**Bu değişikliğe hazırlanmak için ne yapmam gerek?**
Lütfen **Intune Uygulama Koruması** yerine **Intune**’u sık kullanılan olarak etiketleyin ve Intune içerisindeki **Mobil** uygulama dikey penceresinde bulunan Uygulama koruma ilkesi iş akışını inceleyin. Kısa bir süreliğine yenilen yönlendireceğiz ancak daha sonra **Uygulama Koruma** dikey penceresini kaldıracağız. Tüm uygulama koruma ilkelerinin zaten Intune’da olduğunu ve tüm koşullu erişim ilkelerinizi değiştirebileceğinizi unutmayın. Koşullu erişim ilkelerini değiştirme hakkında daha fazla bilgi için bkz. [Azure Active Directory’de koşullu erişim](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal). Daha fazla bilgi için bkz. [Uygulama koruma ilkeleri nedir?](app-protection-policy.md) 


## <a name="week-of-april-2-2018"></a>2 Nisan 2018 Haftası

### <a name="intune-apps"></a>Intune uygulamaları

#### <a name="user-experience-update-for-the-company-portal-app-for-ios---1412866---"></a>iOS için Şirket Portalı uygulamasında kullanıcı deneyimi güncelleştirmesi <!--1412866 -->
iOS için Şirket Portalı uygulamasına büyük bir kullanıcı deneyimi güncelleştirmesi yayımladık. Güncelleştirme, modern bir görünüm ve his sağlayan yepyeni bir görsel tasarım sunmaktadır. Uygulamanın işlevselliğini korurken kullanılabilirliğini ve erişilebilirliğini artırdık.  

Şunları da göreceksiniz:
- iPhone X desteği.
- Kullanıcıların zamandan tasarruf etmesi için daha hızlı uygulama açma ve yükleme yanıtları.
- Kullanıcılara en güncel durum bilgilerini sağlamak için ek ilerleme çubukları.
- Herhangi bir sorunla karşılaşıldığında bunun daha kolay bildirilmesi için günlükleri karşıya yükleme işleminde iyileştirme.  

Güncelleştirilmiş görünümü görmek için [Uygulama kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md)’e gidin.

#### <a name="protect-on-premises-exchange-data-using-intune-app-and-ca----1056954---"></a>Intune APP ve CA kullanarak şirket içi Exchange verilerini koruma <!-- 1056954 -->
Şirket içi Exchange verilerine erişimi Outlook Mobile ile korumak için artık Intune Uygulama İlke Koruması (APP) ve Koşullu Erişim (CA) kullanabilirsiniz. Azure portalına bir uygulama koruma ilkesi eklemek veya ilkeyi değiştirmek için **Microsoft Intune** > **İstemci uygulamaları** > **Uygulama koruma ilkeleri**’ni seçin. Bu özelliği kullanmadan önce [iOS ve Android için Outlook gereksinimlerini](https://technet.microsoft.com/en-us/library/mt846639(v=exchg.160).aspx) karşıladığınızdan emin olun.

## <a name="notices"></a>Bildirimler

### <a name="upcoming-password-enforcement-change-for-macos-10142-in-intune---1873216--"></a>Intune'da macOS 10.14.2 değişiklik gelecek parola zorlama <!--1873216-->
İçinde MC145129 Temmuz ayında Apple'nın yeni tümleştirmek için Intune planları "Değişiklik parola, sonraki Auth" ayarı yukarıda ve macOS 10.13 sürümleri çalıştıran cihazlar için yayımlanan paylaşılmıştı. Şu anda bu ayar için macOS 10.14.2 Şubat ayında Dışarı Aktar planlıyoruz ve büyük. 

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
10.14.2 macOS çalıştıran cihazlar sahip olmayı planlıyor veya varsa bu, etkiler ve daha büyük. Intune, Apple kullanıma sunulan "Değişiklik parola en yeni Auth" ayarı, kullanıcıların parolalarını bir parola ilkesi gönderildiğinde, uyumlu bir güncelleştirme zorunlu kılabilirsiniz. Biz bu yeni Apple özellik tümleştirdiğinizde parolalarını zaten uyumlu olsa bile parolalarını güncelleştirmek için bir istek, macOS kullanıcılarını alır. Bir parola zaten uyumlu olan ve parolalardan karşı bir gereksinim yoksa, daha sonra son kullanıcıların mevcut parolalarını güncelleştiremezsiniz olacağını unutmayın. Son kullanıcılara çalıştığınızda kimlik doğrulaması veya kendi cihazında oturum açmak parolasını güncelleştirmesi isteği yalnızca görürsünüz. Cihaz uyumlu olarak işaretlenene kadar şirket kaynaklarına engellerseniz, son kullanıcılarınızın 10.14.2 MacOS cihazlarında, kullanıcının parolasını sıfırlamasını kadar e-posta ya da SharePoint siteleri gibi şirket kaynaklarına erişmeniz engellenebilir bildirin. Gelecekte tüm güncelleştirmeleri yapılandırma ve uyumluluğunu parola ilkeleri için hedeflenen kullanıcılara parolalarını güncelleştirmek için zorlar. Bu değişikliği uygulamadan önce müşteri araştırma son kullanıcıların genellikle parolalarını bir parola ile veya uyumluluğun korunması için parolalarını sıfırlayamaz isteğinizi aldıktan sonra güncelleştirilir beri müşterilerin çoğu bu değişiklikten etkilenmez gösterilir.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapabilirim?
Yardım masanıza bildirin izin vermek isteyebilirsiniz. Bu değişiklik kullanıma sunulduğunda Bu yenilikler güncelleştireceğiz. Bu macOS cihaz parola ilkesi uygulanmasını istemiyorsanız, biz powerbı.com'u önerilir veya var olan macOS ilkenizi silin.

###<a name="plan-for-change-update-to-ios-setting-for-supervised-devices-in-the-intune-console"></a>Değişiklik planı: Intune konsolunda denetimli cihazlar için iOS ayarını güncelleştirme  
Intune hizmetine Şubat güncelleştirmesiyle, denetimli iOS cihazları için 'cihaz ayarlarında Kısıtlamaları Etkinleştirme' ayarı "Ekran süresi (yalnızca denetimli)" olarak adlandırılıyor. Bu değişiklikten sonra son kullanıcı deneyimi iOS sürümüne göre değişir.

####<a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
"(Yalnızca denetimli) cihaz ayarlarında kısıtlamaları etkinleştirme" ayarını "deneyimi için cihazlara (Apple kayıt programları ile kaydedilen cihazlar) denetimli (yalnızca denetimli) ekran zaman", burada'nın yeniden adlandırıldıktan sonra: 

İOS 11.4 ve önceki cihazlar için: Bu ayar, kullanıcıların önce olarak cihaz kısıtlamalarını değiştirmesini önlemek için kullanılabilir. Son kullanıcı deneyiminde bir değişiklik tarafından görülmez.
 
12 ve daha sonra iOS cihazlar için: Son kullanıcılar artık ayarları kısıtlamaları sekmesinde bakın > Genel > cihaz Yönetimi > Yönetim profili > kısıtlamaları.
Bunun yerine, bu ayarları bir parçası olacak > Genel > Ekran zaman. "Blok" için bu ayarın yapılandırılması da içeriği ve gizlilik kısıtlamaları içeren kullanıcıların cihazlarında, ekran saat ayarlarını değiştirmesini engeller.

####<a name="what-can-i-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapabilirim?
İOS 12 ve sonraki sürümler için yükseltilen cihazlar için deneyiminde değişiklik unutmayın, son kullanıcı kılavuzu güncelleştirin.


###<a name="plan-for-change-workflow-changes-for-ios-12-enrollment-in-intune"></a>Değişiklik planı: Intune'da iOS 12 kayıt için iş akışı değişiklikleri
Apple iOS cihazlarında mobil cihaz Yönetimi (MDM) hizmetlerine kaydetme ile ilgili bazı değişiklikler açıkladı. Değişiklik büyük olasılıkla tüm gelecek iOS sürümleri yanı sıra iOS spring 2019 sürümü görülür.

####<a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
Son kullanıcılarınızın cihazlarını iOS 12 Bu yeni sürümüne içinde spring yükseltirseniz, bilmeniz değiştirilmiş bir iş akışı ve ıntune'a kaydı için ek adımlar atmanız gerekir. Apple bu değişiklikleri getirir, son kullanıcıların gerekir: • bir yönetim profili • Git ayarlarına indirmek için Şirket portalı uygulamasında kayıt işlemi başlar > Genel > profiller • doğru profili seçin ve tıklayın • Dönüş Şirket portalı kaydı yüklemek için 

Önceden kaydedilen cihazların kaydı ve yeni bir kayıt gerekiyor sürece yeni yükseltme iOS sürüm etkilenmez.
Kayıt deneyimi 12,1 veya önceki iOS çalıştıran cihazlarda, Apple tarafından bu yeni sürümle birlikte değiştirmez.

####<a name="what-can-i-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapabilirim?
Belgelerinize ve, son kullanıcı kılavuzu yükseltmek planlamanız gerekir. Bu değişiklikler bilmeniz, Yardım Masası izin isteyebilirsiniz. Sizi ileti merkezi bilgilendirmeyi saklayacağız ve bu değişiklik Canlı olduğunda müşterilerimize yenilikler.

Ekran görüntüleri ve beklenen kayıt akışını video ile bir destek blog gönderisi için ek bilgi tıklayın.

####<a name="additional-information"></a>Ek bilgi
https://aka.ms/iOS_enrollment_changes

### <a name="plan-for-change-user-experience-update-to-intune-company-portal-app-for-ios"></a>Değişiklik planı: İOS için Intune Şirket portalı uygulamasında kullanıcı deneyimi güncelleştirmesi
Bir kullanıcı deneyimi güncelleştirmesi iOS Şirket portalı uygulaması için Intune yakında yayımlar paylaşmak heyecan duyuyoruz. Güncelleştirme Gelişmiş Filtreler ve daha hızlı erişim için uygulamalar ve Kitaplar visual yeniden giriş sayfasının özellik.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
Bulunacak geçerli iOS Şirket portalı işlevselliği, bakımı sırasında bu kullanıcı deneyimi güncelleştirmesi:
- Yerel iOS görünüm ile bir giriş sayfası 
- İçerik listeleri ve içerik türünü (uygulamaları veya e-Kitaplar) ve kullanılabilirlik (cihaz Yönetimi gerekli veya Kayıtsız kullanılabilir) göre filtreleme özelliği dahil olmak üzere arama filtreleme yetenekleri
- E-Kitaplar arama özelliği
- Arama Geçmişi uygulamaları ve e-Kitaplar için Apple TestFlight programı bir parçası kullanıyorsanız kullanılabilir hale geldiğinde, Intune'un güncelleştirilmiş iOS Şirket portalı uygulamasının yayım öncesi sürümü hakkında bildirim alırsınız. Apple TestFlight programı parçası değilseniz çok geç kaydetmek için değil. Kaydetme, son kullanıcılarınız için kullanılabilir olmadan önce güncelleştirilmiş Şirket portalı uygulamasını kullanmaya olanak sağlar. Ayrıca doğrudan Intune ekibine geri bildirim sağlamak için fırsatınız vardır.  

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapabilirim?
Herhangi bir eylemde bulunmanız gerekmez; Bu değişiklikler, gelecek iOS CP uygulama sürümde kullanıma sunulacaktır. 

#### <a name="additional-information"></a>Ek bilgi
[https://aka.ms/cp_update_iOS](https://aka.ms/cp_update_iOS)


### <a name="plan-for-change-exchange-online-to-intune-connector-will-not-be-available-in-intune----3105122---"></a>Değişiklik planı: Exchange Online için Intune Bağlayıcısı Intune tarafından kullanılamaz <!-- 3105122 -->
Exchange Online ve koşullu erişim ile deneyiminizi kolaylaştırmak için biz Exchange Online için Intune 'Hizmet' bağlayıcısını devre dışı bırakacağız.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
'Hizmet' bağlayıcı işlevini ortamınızda kullanmakta olduğunuz, Kayıtlarımıza göre bu yana bu iletiyi alıyorsunuz. 'Hizmet' Bağlayıcısı, Exchange Online için Exchange Active Sync yalnızca cihazların Intune yönetimini destekler ve şirket içi altyapı desteklemez. Koşullu erişim (CA) için gerekli olduğu konsolunda görüntülenme şeklini nedeniyle bu bağlayıcı görünür olduğunda gerçekte, bu CA için gerekli değildir. Intune hizmetine Şubat güncelleştirmesiyle konsolda bu netleştirmek için yeni bağlayıcılar belirlemek için bu düğmeyi devre dışı bırakırız. Ardından, Mart 2019 ' tüm mevcut Exchange Online için Intune bağlayıcıları devre dışı bırakılır.

Ortamınızda bu bağlayıcılar kullanıyorsanız, izlemek ve Mart ayında bağlayıcıları devre dışı bıraktıktan sonra Intune'da Exchange Active Sync yalnızca cihazları temizlemek mümkün olmayacaktır. Bu değişiklik sırasında son kullanıcılarınıza beklenen hiçbir etkisi yoktur.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapabilirim?

Hizmetten hizmete bağlayıcı ayarlama ve Exchange Active Sync yalnızca cihazınız varsa, cihazlarınızı yönetmek için diğer yöntemler geçin. Aşağıdaki seçenekleriniz vardır:

- Mobil cihaz Yönetimi (MDM) cihazlarını kaydetme
- Cihazlarınızı yönetmek için Intune uygulama koruma ilkelerini kullanma
- Burada belgelerinde belirtildiği gibi Exchange denetimleri kullanın. 

#### <a name="additional-information"></a>Ek bilgi
[Intune ve Exchange Online için Exchange hizmeti Bağlayıcısı'nı yapılandırma](https://docs.microsoft.com/intune/exchange-service-connector-configure)



### <a name="plan-for-change-performance-updates-to-intune-for-education---1750215--"></a>Değişiklik planı: Eğitim için Intune performans güncelleştirmeleri <!--1750215-->
Eğitim için Intune’da kullanıcılarınıza veya cihazlarınıza ayar atamanız sırasında hızı ve güvenilirliği artırmak için bazı güncelleştirmeler ekliyoruz. Bu değişikliğin bir parçası olarak Kasım sonuna doğru ilke veya ayar atamalarınızı yeni gruplara taşıyacağız.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?

Müşteri eğitim için Intune iki dinamik Azure Active Directory (Azure AD) grupları vardır: "Tüm kullanıcılar" ve "Tüm cihazlar". Güncelleştirmeler sonrasında bu “Tüm Kullanıcılar” ve “Tüm Cihazlar” Azure AD grupları, Eğitim için Intune konsolunda görünür olmayacak. Ancak Azure konsolunda Intune’da görünür olmaya devam edecek ve “Tüm Kullanıcılar (Eski, kullanmayın)” ve “Tüm Cihazlar (Eski, kullanmayın)” olarak yeniden adlandırılacak.

Güncelleştirmeler çıktıktan sonra Intune’da uygulama ve ayar atamak için Azure AD grupları kullanmanıza gerek kalmayacak. Bunun yerine Ayarlar atamalarınızı Eğitim için Intune’da sizin için oluşturacağımız ve önceki gibi “Tüm Kullanıcılar” ve “Tüm Cihazlar” olarak görünen yeni gruplara taşıyacağız. Bu değişiklikler arka uçta olduğu için Eğitim için Intune konsolunda bir farklılık olmayacaktır. Değişikliklerin son kullanıcılarınız veya kayıtlı cihazlarınız üzerinde herhangi bir etkisi olması beklenmemektedir. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapmam gerek?
Biz ilke atamalarınızı taşırken sizin hiçbir şey yapmanıza gerek yoktur. Şu anda Eğitim için Intune konsolunda ilke atıyorsanız atamaya devam edin.

Şu anda Azure’da Intune üzerinde yukarıda bahsedilen Azure AD gruplarına ilke atıyorsanız, bunları Eğitim için Intune konsolundaki Tüm Kullanıcılar ve Tüm Cihazlar gruplarına atamaya başlayın. Azure AD gruplarının konsolda eski olarak yeniden adlandırıldığını görürseniz Azure AD’de ilke atamayı bırakın. Yeniden adlandırılan grupları şu anda başka bir amaçla kullanmıyorsanız silin.


### <a name="take-action-please-update-your-android-device-restriction-or-compliance-policy-password-settings-in-intune"></a>Eylemi gerçekleştir: Lütfen, Android cihaz kısıtlama veya uyumluluk İlkesi parola ayarlarını ıntune'da güncelleştirin
Intune, Android 4.4 ve üstü cihazlarında sağlanan "cihaz varsayılanı" parola türünü kaldıracak. Android platformlarıyla cihaz varsayılanları arasındaki farklardan dolayı, bu ilke cihaz tarafından genellikle isteğe bağlı olarak kabul edilir. Bu ayarın Android'de ne zaman zorunlu tutulacağı konusundaki karışıklığı gidermek için, önümüzdeki sürümlerden birinde kullanıcı arabiriminden bu ayarı kaldıracağız. 
#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
- Cihazlarda parolanın gerekli olmasını amaçlıyorsanız, "cihaz varsayılanı" kullanmak yerine Android platformu profillerinizi düzenleyip gerekli parola türünü açıkça ifade etmenizi öneririz.
- Amacınız parola oluşturup oluşturmama kararını son kullanıcıya bırakmaksa, “Yapılandırılmadı” düğmesini seçin. Bu ayarı kullanıcı arabiriminden kaldırdığınızda, ayar hala ayarlanmış durumdaysa, profili bir sonraki düzenleyişinizde "Cihaz varsayılanı" dışında bir değer seçmeniz istenir.
Bu değişikliğe hazırlanmak için ne yapmam gerek?
Android'inizde ve Android kurumsal cihaz kısıtlaması ve uyumluluk ilkelerinde parola ayarlarını gözden geçirin. Bunlar, Uyumluluk ilkeleri için Sistem güvenliğinin altında ve Cihaz kısıtlamaları için Cihaz parolası veya İş profili ayarları altında listelenir. Ek bilgilerde, diğer ayrıntıların bağlantısı ve bu ayarların yapılandırıldığı ekranların görüntüleri vardır.
#### <a name="additional-information"></a>Ek bilgiler
https://aka.ms/PasswordSettings 

