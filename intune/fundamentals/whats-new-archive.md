---
title: Microsoft Intune - Azure’da önceki aylarda yapılan yenilikler | Microsoft Docs
titleSuffix: ''
description: Intune’daki yenilikler sayfasından eski duyuruları gözden geçirme
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/5/2019
ms.topic: archived
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 9ba01d60-4a03-4e3e-9aba-8be905c0054c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6a6b5585501851bb52db70ca222f8cfff7ad0597
ms.sourcegitcommit: 2c8a41ee95a3fde150667a377770e51b621ead65
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/06/2019
ms.locfileid: "73635460"
---
# <a name="whats-new-in-the-microsoft-intune---previous-months"></a>Microsoft Intune’daki yenilikler - önceki aylar

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

<!-- ########################## -->
## <a name="april-2019"></a>2019 Nisan

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Uygulama yönetimi
#### <a name="user-experience-update-for-the-company-portal-app-for-ios---2536024---"></a>iOS için Şirket Portalı uygulamasında kullanıcı deneyimi güncelleştirmesi<!-- 2536024 -->
İOS cihazları için Şirket Portalı uygulamasının ana sayfası yeniden tasarlanmıştır. Bu değişiklik ile, giriş sayfası iOS Kullanıcı arabirimi desenlerini daha iyi izler ve ayrıca uygulamalar ve e-kitaplar için geliştirilmiş bulunabilirliği sağlar.

#### <a name="changes-to-company-portal-enrollment-for-ios-12-device-users--3448635---"></a>İOS 12 cihaz kullanıcıları için Şirket Portalı kaydında yapılan değişiklikler<!--3448635 -->
İOS kayıt ekranları ve adımları için Şirket Portalı, Apple iOS 12,2 ' de yayınlanan MDM kaydı değişiklikleriyle uyum sağlamak üzere güncelleştirilmiştir. Güncelleştirilmiş iş akışı kullanıcılardan şunları yapmanızı ister:  

* Safari 'nin Şirket Portalı Web sitesini açmasına ve Şirket Portalı uygulamasına döndürmeden önce yönetim profilini indirmesine izin verin.  
* Yönetim profilini cihazlarına yüklemek için Ayarlar uygulamasını açın.
* Kaydı tamamlamaya yönelik Şirket Portalı uygulamasına geri dönün.  

Güncelleştirilmiş kayıt adımları ve ekranları için bkz. [iOS cihazını Intune 'A kaydetme](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios).

#### <a name="openssl-encryption-for-android-app-protection-policies---3747362---"></a>Android uygulama koruma ilkeleri için OpenSSL şifrelemesi<!-- 3747362 -->
Android cihazlarda Intune uygulama koruma ilkeleri (uygulama) artık FIPS 140-2 uyumlu bir OpenSSL şifreleme kitaplığı kullanıyor. Daha fazla bilgi için [Microsoft Intune Android uygulama koruma ilkesi ayarlarının](../apps/app-protection-policy-settings-android.md) [şifreleme](../apps/app-protection-policy-settings-android.md#encryption) bölümüne bakın.

#### <a name="enable-win32-app-dependencies---2617348----"></a>Win32 uygulama bağımlılıklarını etkinleştir<!-- 2617348  -->
Yönetici olarak, Win32 uygulamanızı yüklemeden önce diğer uygulamaların bağımlılık olarak yüklenmesini zorunlu kılabilirsiniz. Özellikle, cihazın Win32 uygulamasını yüklemeden önce bağımlı uygulamaları yüklemesi gerekir. Intune 'da, **Uygulama Ekle** dikey penceresini göstermek için **istemci uygulamaları** > **uygulamalar** > **Ekle** ' yi seçin. **Uygulama türü**olarak **Windows uygulaması (Win32)** seçeneğini belirleyin. Uygulamayı ekledikten sonra, Win32 uygulaması yüklenmeden önce yüklenmesi gereken bağımlı uygulamaları eklemek için **Bağımlılıklar** ' ı seçebilirsiniz. Daha fazla bilgi için bkz. [Intune tek başına-Win32 uygulama yönetimi](./../apps/app-management.md). 

#### <a name="app-version-installation-information-for-microsoft-store-for-business-apps---3537391-----"></a>Iş uygulamaları için Microsoft Store uygulama sürümü yükleme bilgileri<!-- 3537391   -->
Uygulama yükleme raporları Microsoft Store Iş uygulamaları için uygulama sürümü bilgilerini içerir. Intune 'da, **istemci uygulamaları** > **uygulamalar**' ı seçin. **İş için bir Microsoft Store** seçin ve ardından **izleyici** bölümünde **cihaz yüklemesi durumu** ' nu seçin.

#### <a name="additions-to-win32-apps-requirement-rules---3676883-----"></a>Win32 uygulamaları gereksinim kurallarına ekler<!-- 3676883   -->
PowerShell betikleri, kayıt defteri değerleri ve dosya sistemi bilgilerini temel alan gereksinim kuralları oluşturabilirsiniz. Intune 'da, **istemci uygulamaları** > **uygulama** > **Ekle**' yi seçin. Ardından **Uygulama Ekle** dikey penceresinde **uygulama türü** olarak **Windows uygulaması (Win32)** seçeneğini belirleyin.  Ek gereksinim kurallarını**yapılandırmak için  > ** **gereksinimler** ' i seçin. Daha sonra, **Gereksinim türü**olarak **dosya türü**, **kayıt defteri**veya **komut dosyası** seçeneklerinden birini belirleyin. Daha fazla bilgi için bkz. [Win32 uygulama yönetimi](./../apps/app-management.md).

#### <a name="configure-your-win32-apps-to-be-installed-on-intune-enrolled-azure-ad-joined-devices---3695227----"></a>Win32 uygulamalarınızı Intune 'a kayıtlı Azure AD 'ye katılmış cihazlara yüklenecek şekilde yapılandırma<!-- 3695227  -->
Win32 uygulamalarınızı, Intune 'a kayıtlı Azure AD 'ye katılmış cihazlara yüklenecek şekilde atayabilirsiniz. Intune 'da Win32 uygulamaları hakkında daha fazla bilgi için bkz. [Win32 uygulama yönetimi](./../apps/app-management.md).

#### <a name="device-overview-shows-primary-user--3794259----"></a>Cihaza genel bakış birincil kullanıcıyı gösterir<!--3794259  -->
Cihaza genel bakış sayfası, Kullanıcı cihaz benzeşimi kullanıcısı (UDA) olarak da bilinen birincil kullanıcıyı gösterir. Bir cihazın birincil kullanıcısını görmek için **ıntune**  > **cihazları**  > **tüm cihazlar** ' ı seçin > bir cihaz seçin. Birincil Kullanıcı **genel bakış** sayfasının en üstünde görünür.

#### <a name="additional-managed-google-play-app-reporting-for-android-enterprise-work-profile-devices---4105925----"></a>Android Kurumsal iş profili cihazları için ek Yönetilen Google Play uygulaması raporlaması<!-- 4105925  -->
Android Kurumsal iş profili cihazlarına dağıtılan Yönetilen Google Play uygulamaları için, cihazda yüklü olan uygulamanın sürüm numarasını görüntüleyebilirsiniz. Bu yalnızca gerekli uygulamalar için geçerlidir.  

#### <a name="ios-third-party-keyboards---4111843-----"></a>iOS üçüncü taraf klavyeleri<!-- 4111843   -->
İOS platformu değişikliği nedeniyle, iOS için **üçüncü taraf klavye** ayarları için Intune uygulama koruma IlkesI (App) desteği artık desteklenmiyor. Bu ayarı Intune yönetici konsolunda yapılandıramayacak ve Intune uygulama SDK 'sında istemci üzerinde zorlanmaz.


<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="updated-certificate-connectors---icm-113304612---"></a>Güncelleştirilmiş sertifika bağlayıcıları<!-- ICM 113304612 -->
[Microsoft Intune için hem Intune sertifika Bağlayıcısı hem de PFX Sertifika Bağlayıcısı](../protect/certficates-pfx-configure.md#whats-new-for-connectors)için güncelleştirmeler yayımladık. Yeni yayınlar bazı bilinen sorunları düzeltir.

#### <a name="set-login-settings-and-control-restart-options-on-macos-devices---1210083----"></a>MacOS cihazlarında oturum açma ayarlarını ve denetim yeniden başlatma seçeneklerini ayarlama<!-- 1210083  -->
MacOS cihazlarında, bir cihaz yapılandırma profili (**cihaz yapılandırma** > **profilleri**oluşturabilirsiniz  > **Profil oluştur** >, platform için **MacOS** > **cihaz özellikleri** ' ni seçin). Bu güncelleştirme, özel bir başlık gösterme, kullanıcıların oturum açma şeklini seçme, güç ayarlarını gösterme veya gizleme gibi yeni oturum açma penceresi ayarlarını içerir.

Bu ayarları görmek için, [MacOS cihaz özelliği ayarları](../configuration/macos-device-features-settings.md)' na gidin.

#### <a name="configure-wifi-on-android-enterprise-device-owner-dedicated-devices-running-in-multi-app-kiosk-mode--3041940----"></a>Çok uygulama bilgi noktası modunda çalışan Android Enterprise, cihaz sahibi adanmış cihazları üzerinde WiFi yapılandırma<!--3041940  -->
Çok uygulama bilgi noktası modunda adanmış bir cihaz olarak çalışırken Android Enterprise, cihaz sahibi ayarlarını etkinleştirebilirsiniz. Bu güncelleştirmede, kullanıcıların, platform için**Android Enterprise**  > **profil oluşturmak**  > , WiFi ağlarını (**Intune**  > **cihaz yapılandırma**  > **profillerini** yapılandırıp bağlantı kurmasını sağlayabilirsiniz >  **Yalnızca cihaz sahibi,** profil türü Için cihaz kısıtlamaları > **adanmış cihazlar** 1**bilgi noktası modu**: **çok uygulamayla** 4**WiFi yapılandırması**).

Yapılandırabileceğiniz tüm ayarları görmek için [Android kurumsal cihaz ayarları ' na giderek özelliklere izin verin veya kısıtlayın](../configuration/device-restrictions-android-for-work.md).

Uygulama hedefi: çok uygulamayla bilgi noktası modunda çalışan Android kurumsal adanmış cihazlar

#### <a name="configure-bluetooth-and-pairing-on-android-enterprise-device-owner-dedicated-devices-running-in-multi-app-kiosk-mode---3041941----"></a>Android Enterprise 'ta Bluetooth ve eşleştirme, çok uygulama bilgi noktası modunda çalışan cihaz sahibi adanmış cihazları yapılandırma<!-- 3041941  -->
Çok uygulama bilgi noktası modunda adanmış bir cihaz olarak çalışırken Android Enterprise, cihaz sahibi ayarlarını etkinleştirebilirsiniz. Bu güncelleştirmede, son kullanıcıların Bluetooth 'u etkinleştirmesine ve cihazları Bluetooth üzerinden eşleştirmesine izin verebilirsiniz (**ıntune** > **cihaz yapılandırması** > **profilleri** > **profil oluşturma** > **Android Enterprise** yalnızca platform > **cihaz sahibi,** profil türü için cihaz kısıtlamaları > **adanmış cihazlar**1**bilgi noktası modu**: **çok uygulama**4**Bluetooth yapılandırması**).

Yapılandırabileceğiniz tüm ayarları görmek için [Android kurumsal cihaz ayarları ' na giderek özelliklere izin verin veya kısıtlayın](../configuration/device-restrictions-android-for-work.md).

Uygulama hedefi: çok uygulamayla bilgi noktası modunda çalışan Android kurumsal adanmış cihazlar

#### <a name="create-and-use-oemconfig-device-configuration-profiles-in-intune---3305883----"></a>Intune 'da OEMConfig cihaz yapılandırma profilleri oluşturma ve kullanma<!-- 3305883  -->
Bu güncelleştirmede, Intune, OEMConfig ile Android kurumsal cihazlarını yapılandırmayı destekler. Özellikle, bir cihaz yapılandırma profili oluşturabilir ve OEMConfig kullanarak Android kurumsal cihazlara ayarlar uygulayabilirsiniz (**cihaz yapılandırma** > **profilleri** > **Profil oluştur** > **Android Enterprise** platform için).

OEM desteği şu anda OEM başına temelde. İstediğiniz bir OEMConfig uygulaması OEMConfig Apps listesinde yoksa, `IntuneOEMConfig@microsoft.com` ' a başvurun.

Bu özellik hakkında daha fazla bilgi edinmek için [Microsoft Intune ' de OEMConfig Ile Android kurumsal cihazlarını kullanma ve yönetme](../configuration/android-oem-configuration-overview.md)bölümüne gidin.

Uygulama hedefi: Android Enterprise

#### <a name="windows-update-notifications---3316758-3316782----"></a>Windows Update bildirimleri<!-- 3316758, 3316782  -->
Intune konsolu içinden yönetebileceğiniz Windows Update halka yapılandırmalarına iki *Kullanıcı deneyimi ayarı* ekledik. Şimdi şunları yapabilirsiniz:
- Kullanıcıların [Windows güncelleştirmelerini taramasına](../protect/windows-update-settings.md)engel veya izin verir.
- Kullanıcıların göreceği [Windows Update bildirim düzeyini](../protect/windows-update-settings.md) yönetin.

#### <a name="new-device-restriction-settings-for-android-enterprise-device-owner---3574254----"></a>Android Enterprise için yeni cihaz kısıtlama ayarları, cihaz sahibi<!-- 3574254  -->
Android kurumsal cihazlarda, özelliklere izin vermek veya kısıtlamak, parola kuralları ayarlamak ve daha fazlasını yapmak için bir cihaz kısıtlama profili oluşturabilirsiniz (**cihaz yapılandırma** > **profilleri** > **Profil oluştur** > Android seçin  **Enterprise** for platform > **cihaz sahibi yalnızca profil türü için cihaz kısıtlamalarını >** ). 

Bu güncelleştirme, yeni parola ayarlarını içerir, tam olarak yönetilen cihazlarda Google Play Store uygulamalara tam erişim sağlar ve daha fazlasını sağlar. Ayarların geçerli listesini görmek için [Android kurumsal cihaz ayarları ' na giderek özelliklere izin verin veya kısıtlayın](../configuration/device-restrictions-android-for-work.md). 

Uygulama hedefi: Android kurumsal tam yönetilen cihazlar

#### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy---3617671---"></a>Windows 10 cihaz uyumluluk ilkesinde TPM yonga kümesini denetleme<!-- 3617671 -->

Bu özellik gecikiyor ve daha sonra yayınlanabilecek şekilde planlanmaktadır.

#### <a name="updated-ui-changes-for-microsoft-edge-browser-on-windows-10-and-later-devices---3775833-----"></a>Windows 10 ve üzeri cihazlarda Microsoft Edge tarayıcısı için güncelleştirilmiş UI değişiklikleri<!-- 3775833   -->
Bir cihaz yapılandırma profili oluşturduğunuzda, Windows 10 ve üzeri cihazlarda Microsoft Edge özelliklerine izin verebilir veya kısıtlayabilirsiniz (**cihaz yapılandırma** > **profilleri** > **Profil oluştur** > **Windows 10 ve üzeri** platform için, **Microsoft Edge Browser**> profil türü için **cihaz kısıtlamalarını** >. Bu güncelleştirmede, Microsoft Edge ayarları daha açıklayıcı ve anlaşılması daha kolay.

Bu özellikleri görmek için [Microsoft Edge tarayıcı cihaz kısıtlama ayarları](../configuration/device-restrictions-windows-10.md#microsoft-edge-browser)' na gidin.

Şunlar için geçerlidir: Windows 10 ve üzeri

#### <a name="expanded-support-for-android-enterprise-fully-managed-devices--preview-----3903241-3903244-3903246-----"></a>Android kurumsal tam olarak yönetilen cihazlar için genişletilmiş destek (Önizleme)<!--   3903241, 3903244, 3903246   -->
Hala genel önizlemede, Android kurumsal tam olarak yönetilen cihazlar desteğimizi, önce 2019 Ocak ' de duyurduğumuz, aşağıdakileri dahil edecek şekilde genişlettik:

- Tam olarak yönetilen ve ayrılmış cihazlarda, parola kuralları ve [](../protect/compliance-policy-create-android-for-work.md) işletim sistemi gereksinimleri (**cihaz uyumluluğu** > **Ilkeleri** > **ilke oluştur** > **Android** Platform için Enterprise > profil türü Için **cihaz sahibi** ).

  Adanmış cihazlarda, cihaz **uyumlu değil**olarak gösterilebilir. Koşullu erişim adanmış cihazlarda kullanılamaz. Ayrılmış cihazların atanan ilkelerinizle uyumlu olmasını sağlamak için gerekli görevleri veya eylemleri gerçekleştirdiğinizden emin olun.

- [Koşullu erişim](../protect/conditional-access.md) -Android 'e uygulanan koşullu erişim Ilkeleri, Android kurumsal tam olarak yönetilen cihazlar için de geçerlidir. Kullanıcılar artık **Microsoft Intune uygulamasını**kullanarak tam olarak yönetilen cihazlarını Azure Active Directory kaydedebilir. Daha sonra, bkz. ve kuruluş kaynaklarına erişmek için tüm uyumluluk sorunlarını çözün.

- Yeni Son Kullanıcı uygulaması (Microsoft Intune uygulaması)-Android tam olarak yönetilen ve **Microsoft Intune**adlı cihazlar için yeni bir son kullanıcı uygulaması vardır. Bu yeni uygulama hafif ve modern bir uygulamadır, ancak tam olarak yönetilen cihazlar için Şirket Portalı uygulama olarak benzer işlevsellik sağlar. Daha fazla bilgi için bkz. [Google Play Microsoft Intune uygulama](https://play.google.com/store/apps/details?id=com.microsoft.intune).

Android tam olarak yönetilen cihazları ayarlamak için **cihaz kaydı** > **Android kaydı** > **şirkete ait, tam olarak yönetilen Kullanıcı cihazları**' na gidin. Tam olarak yönetilen Android cihazlar için destek önizlemede kalır ve bazı Intune özellikleri tam olarak işlevsel olmayabilir.  

Bu önizleme hakkında daha fazla bilgi edinmek için bkz. blog, [Android kurumsal tam olarak yönetilen cihazlar için Microsoft Intune-Preview 2](https://aka.ms/preview2_AE_fullymanaged).

#### <a name="use-compliance-manager-to-create-assessments-for-microsoft-intune---4404750---"></a>Uyumluluk Yöneticisi 'Ni kullanarak Microsoft Intune için değerlendirmeler oluşturma<!-- 4404750 -->

[Uyumluluk Yöneticisi](https://servicetrust.microsoft.com/ComplianceManager) (başka bir Microsoft site açar), Microsoft hizmet güveni portalındaki iş akışı tabanlı risk değerlendirmesi aracıdır. Kuruluşunuzun Microsoft hizmetleriyle ilgili yasal uyumluluk etkinliklerini izlemenize, atamanıza ve doğrulamanıza olanak sağlar. Office 365, Azure, Dynamics, Professional Hizmetleri ve Intune ile kendi uyumluluk değerlendirmenizi oluşturabilirsiniz. Intune 'da kullanılabilir iki değerlendirme vardır-FFIEC ve GDPR.

Uyumluluk Yöneticisi, Microsoft tarafından yönetilen denetimleri ve kuruluşunuz tarafından yönetilen denetimleri kırarak çabalarınıza odaklanmanıza yardımcı olur. Değerlendirmeleri tamamlayabilir ve sonra değerlendirmeleri dışa aktarabilir ve yazdırabilirsiniz.

[Federal Finans kurumları Inceleme Council (FFIEC)](https://www.microsoft.com/trustcenter/compliance/FFIEC) (başka bir Microsoft site açar) uyumluluk, ffiec tarafından verilen çevrimiçi bankacılık için bir standartlar kümesidir. Bu, Intune kullanan finansal kurumlar için en çok istenen değerlendirmede yapılır. Intune 'un genel bulut iş yükleri ile ilgili FFIEC siber güvenlik yönergelerine nasıl yardımcı olduğunu yorumlar. Intune 'un FFIEC değerlendirmesi, uyumluluk Yöneticisi 'nde ikinci FFIEC değerlendirmesi olur.

Aşağıdaki örnekte, FFIEC denetimlerinin dökümünü görebilirsiniz. Microsoft, 64 denetimlerini içerir. Kalan 12 denetimden sorumlu olursunuz.

![Müşteri eylemleri ve Microsoft eylemleri dahil olmak üzere FFIEC için örnek bir Intune değerlendirmesi konusuna bakın](./media/whats-new/intune-ffiec-assessment-status.png)

[Genel veri koruma yönetmeliği (GDPR)](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-overview) (başka bir Microsoft sitesini açar), kişilerin ve bunların verilerinin haklarının korunmasına yardımcı olan bir Avrupa BIRLIĞI (AB) yasasıdır. GDPR gizlilik düzenlemelerine uyum sağlamaya yardımcı olmak için en istenen değerlendirmesi. 

Aşağıdaki örnekte, GDPR denetimlerinin dökümünü görürsünüz. Microsoft, 49 denetimlerini içerir. Kalan 66 denetimlerinden sorumlu olursunuz.

![Müşteri eylemleri ve Microsoft eylemleri dahil olmak üzere GDPR için örnek Intune değerlendirmesi konusuna bakın](./media/whats-new/intune-assessment-status.png)


<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="configure-profile-to-skip-some-screens-during-setup-assistant---2276470----"></a>Kurulum Yardımcısı sırasında bazı ekranları atlamak için profili yapılandırın<!-- 2276470  -->
Bir macOS kayıt profili oluşturduğunuzda, bir Kullanıcı Kurulum Yardımcısı 'ndan geçtiğinde aşağıdaki ekranlardan birini atlayacak şekilde yapılandırabilirsiniz:
- Görünümünde
- Görüntü Tonu
- ıhoparlör depolama yeni bir profil oluşturursanız veya bir profili düzenlerseniz, seçili atlama ekranlarının Apple MDM sunucusuyla eşitlenmesi gerekir.  Kullanıcılar, profil değişikliklerini çekerken bir gecikme olmaması için cihazların el ile eşitlenmesini verebilir.
Daha fazla bilgi için bkz. [macOS cihazlarını aygıt kayıt programı veya Apple Okul Yöneticisi Ile otomatik olarak kaydetme](../enrollment/device-enrollment-program-enroll-macos.md).

#### <a name="bulk-device-naming-when-enrolling-corporate-ios-devices--3566569----"></a>Kurumsal iOS cihazları kaydedilirken toplu cihaz adlandırma<!--3566569  -->
Apple 'ın şirket kayıt yöntemlerinden birini (DEP/ABı/ASM) kullanırken, gelen iOS cihazlarını otomatik olarak adlandırmak için bir cihaz adı biçimi ayarlayabilirsiniz. Şablonunuzda cihaz türünü ve seri numarasını içeren bir biçim belirtebilirsiniz. Bunu yapmak için **ıntune** > **cihaz kaydı** > **Apple kayıt** > **kayıt programı belirteçleri** > **bir belirteç seçin** >**profil oluşturma**1**cihaz adlandırma biçim**. Mevcut profilleri düzenleyebilirsiniz, ancak yalnızca yeni eşitlenen cihazlara uygulanan ad alınacaktır.

#### <a name="updated-default-timeout-message-on-enrollment-status-page---3959331---"></a>Kayıt durumu sayfasında varsayılan zaman aşımı iletisi güncelleştirildi<!-- 3959331 -->
Kullanıcıların, kayıt durumu sayfası (ESP), ESP profilinde belirtilen zaman aşımı değerini aştığında göreceğiniz varsayılan zaman aşımı iletisini güncelleştirdik. Yeni varsayılan ileti, kullanıcıların gördükleri ve ESP dağıtımıyla ilgili sonraki eylemleri anlamalarına yardımcı olur.  

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Cihaz yönetimi

#### <a name="retire-noncompliant-devices---1827291-----"></a>Uyumsuz cihazları devre dışı bırak<!-- 1827291   -->
Bu özellik gecikti ve gelecek bir sürüm için planlanmıştır.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="monitor-and-troubleshoot"></a>İzleme ve sorun giderme

#### <a name="intune-data-warehouse-v10-changes-reflecting-back-to-beta---4403765---"></a>Intune veri ambarı V 1.0, Beta 'ya geri yansıtarak değişir<!-- 4403765 -->
V 1.0 ilk olarak 1808 sürümünde sunulunca Beta API 'sinden bazı önemli yollarla farklıydı. 1903 ' de, bu değişiklikler Beta API sürümüne geri yansıtılır. Beta API sürümünü kullanan önemli raporlarınız varsa, değişikliklerden kaçınmak için bu raporların V 1.0 'a geçişini kesinlikle öneririz. Daha fazla bilgi için bkz. [Intune veri ambarı API 'si Için değişiklik günlüğü](../developer/reports-changelog.md#1903-part-2).

#### <a name="monitor-security-baseline-status-public-preview----3082047---"></a>Güvenlik temel durumunu izleme (Genel Önizleme) <!-- 3082047 --> 
Güvenlik temellerini izlemeye [Kategori başına bir görünüm](../protect/security-baselines-monitor.md#per-category-view) ekledik. (Güvenlik temelleri önizlemede kalır). Kategori başına görünüm, bu kategori için her bir durum grubuna giren cihazların yüzdesiyle birlikte, her bir kategoriyi taban çizgisinden görüntüler. Artık, kaç cihazın tek tek kategoriler ile eşleşip eşleşmediği, yanlış yapılandırılmış veya geçerli olmadığı hakkında bilgi alabilirsiniz.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="role-based-access-control"></a>Rol tabanlı erişim denetimi

#### <a name="scope-tags-for-apple-vpp-tokens--2371886----"></a>Apple VPP belirteçleri için kapsam etiketleri<!--2371886  -->
Artık, Apple VPP belirteçlerine kapsam etiketleri ekleyebilirsiniz. Yalnızca aynı kapsam etiketiyle atanan kullanıcılar, bu etiketle birlikte Apple VPP belirtecine erişebilir. Bu belirteçle satın alınan VPP uygulamaları ve ekitapları, kapsam etiketlerini de alır. Kapsam etiketleri hakkında daha fazla bilgi için bkz. [RBAC ve kapsam etiketlerini kullanma](scope-tags.md).

<!-- ########################## -->
## <a name="march-2019"></a>Mart 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Uygulama yönetimi
#### <a name="deploy-microsoft-visio-and-microsoft-project---3725386----"></a>Microsoft Visio ve Microsoft Project 'i dağıtma<!-- 3725386  -->
Artık bu uygulamalar için lisanslarınız varsa, Microsoft Intune kullanarak Windows 10 cihazlarına bağımsız uygulamalar olarak Microsoft Visio 365 Pro 'yu ve Microsoft Project Online masaüstü Istemcisini dağıtabilirsiniz. Intune 'da, **Uygulama Ekle** dikey penceresini göstermek için **istemci uygulamaları** > **uygulamalar** > **Ekle** ' yi seçin. **Uygulama Ekle** dikey penceresinde, **uygulama türü**olarak **Windows 10** ' u seçin. Ardından, yüklenecek uygulamaları seçmek için **uygulama paketini Yapılandır** ' ı seçin. Windows 10 cihazları için Office 365 uygulamaları hakkında daha fazla bilgi için bkz. [Microsoft Intune Ile office 365 uygulamalarını Windows 10 cihazlarına atama](../apps/apps-add-office365.md).

#### <a name="microsoft-visio-pro-for-office-365-product-name-change---3593653----"></a>Office 365 için Microsoft Visio Pro ürün adı değişikliği<!-- 3593653  -->
**Office 365 Için Microsoft Visio Pro** , artık **Microsoft Visio Online Plan 2**olarak bilinirdi.  Microsoft Visio hakkında daha fazla bilgi için bkz. [Visio Online Plan 2](https://products.office.com/visio/visio-online-plan-2). Windows 10 cihazları için Office 365 uygulamaları hakkında daha fazla bilgi için bkz. [Microsoft Intune Ile office 365 uygulamalarını Windows 10 cihazlarına atama](../apps/apps-add-office365.md).

#### <a name="intune-app-protection-policy-app-character-limit-setting---3291302----"></a>Intune uygulama koruma ilkesi (uygulama) karakter sınırı ayarı<!-- 3291302  -->
Intune yöneticileri, Intune UYGULAMASıNıN **diğer uygulamalarla kesme, kopyalama ve yapıştırmayı kısıtla** ilke ayarıyla bir özel durum belirtebilir.  Yönetici olarak, yönetilen bir uygulamadan kesilmiş veya kopyalanmış olabilecek karakter sayısını belirtebilirsiniz. Bu ayar, "diğer uygulamalarla kesme, kopyalama ve yapıştırmayı kısıtla" ayarına bakmaksızın, belirtilen sayıda karakteri herhangi bir uygulamaya paylaşmaya izin verir. Android için Intune Şirket Portalı uygulama sürümünün sürüm 5.0.4364.0 veya üstünü gerektirdiğini unutmayın. Daha fazla bilgi için bkz. [iOS veri koruma](../apps/app-protection-policy-settings-ios.md#data-protection), [Android veri koruma](../apps/app-protection-policy-settings-android.md#data-protection)ve [Istemci uygulama koruma günlüklerini gözden geçirme](../apps/app-protection-policy-settings-log.md#app-protection-policy-settings).

#### <a name="office-deployment-tool-odt-xml-for-office-proplus-deployment---3192477-----"></a>Office ProPlus dağıtımı için Office dağıtım aracı (ODT) XML<!-- 3192477   -->
Intune yönetim konsolunda Office Pro Plus 'ın bir örneğini oluştururken Office dağıtım aracı (ODT) XML sağlayabileceksiniz. Bu, mevcut Intune kullanıcı arabirimi seçeneklerinin gereksinimlerinizi karşılamazsa daha özelleştirme daha büyük bir seçenek sağlar. Daha fazla bilgi için bkz. Office [dağıtım aracı için Microsoft Intune ve yapılandırma seçenekleriyle](https://docs.microsoft.com/DeployOffice/configuration-options-for-the-office-2016-deployment-tool) [Office 365 uygulamalarını Windows 10 cihazlarına atama](../apps/apps-add-office365.md) .

#### <a name="app-icons-will-now-be-displayed-with-an-automatically-generated-background---1429026----"></a>Uygulama simgeleri artık otomatik olarak oluşturulan bir arka planda görüntülenir<!-- 1429026  -->
Windows Şirket Portalı uygulamasında, uygulama simgeleri artık simgenin baskın rengine (algılanıyorsa) bağlı olarak otomatik olarak oluşturulan bir arka planla birlikte görüntülenir. Bu arka plan uygun olduğunda, daha önce uygulama kutucuklarında görünen gri kenarlığın yerini alır. Kullanıcılar, bu değişikliği 10.3.3451.0 ' den sonraki Şirket Portalı sürümlerinde görür.

#### <a name="install-available-apps-using-the-company-portal-app-after-windows-bulk-enrollment---2751523-----"></a>Windows toplu kayıt sonrasında Şirket Portalı uygulamasını kullanarak kullanılabilir uygulamaları yükler<!-- 2751523   -->
[Windows Toplu kaydı](../enrollment/windows-bulk-enroll.md) (sağlama paketleri) kullanılarak Intune 'a kaydedilen Windows cihazları, kullanılabilir uygulamaları yüklemek için şirket portalı uygulamasını kullanabilir. Şirket Portalı uygulaması hakkında daha fazla bilgi için bkz. [Windows 10 Şirket portalı el ile ekleme](../apps/store-apps-company-portal-app.md) ve [Microsoft Intune şirket portalı uygulamasını yapılandırma](../apps/company-portal-app.md).

#### <a name="the-microsoft-teams-app-can-be-selected-as-part-of-the-office-app-suite---3828932----"></a>Microsoft ekipleri uygulaması Office uygulama paketi 'nin bir parçası olarak seçilebilir<!-- 3828932  -->
Microsoft ekipleri uygulaması, Office Pro Plus App Suite yüklemesinin bir parçası olarak dahil edilebilir veya hariç tutulamaz. Bu özellik Office Pro Plus derleme numarası 16.0.11328.20116 + için geçerlidir. Yüklemenin tamamlanabilmesi için kullanıcının oturumu kapatıp cihazda oturum açması gerekir. Intune 'da, **istemci uygulamaları** > **uygulama** > **Ekle**' yi seçin. **Office 365 Suite** uygulama türlerinden birini seçin ve ardından **uygulama paketini Yapılandır**' ı seçin.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="automatically-start-an-app-when-running-multiple-apps-in-kiosk-mode-on-windows-10-and-later-devices---2351390---"></a>Windows 10 ve üzeri cihazlarda bilgi noktası modunda birden çok uygulama çalıştırırken otomatik olarak bir uygulama Başlat<!-- 2351390 -->

Windows 10 ve üzeri cihazlarda, bir cihazı bilgi noktası modunda çalıştırabilir ve birçok uygulama çalıştırabilirsiniz. Bu güncelleştirmede bir **oto başlatma** ayarı (**cihaz yapılandırma** > **profilleri** >  profil**oluşturmak**için Platform > **bilgi** > **noktası  >  Windows 10 ve üzeri). Birden çok uygulama bilgi noktası**). Kullanıcı cihazda oturum açtığında uygulamayı otomatik olarak başlatmak için bu ayarı kullanın.

Tüm bilgi noktası ayarlarının listesini ve açıklamasını görmek için bkz. [Windows 10 ve üzeri cihaz ayarları Intune 'da bilgi noktası olarak çalışacak şekilde](../configuration/kiosk-settings-windows.md).

Şunlar için geçerlidir: Windows 10 ve üzeri

#### <a name="operational-logs-also-show-details-on-non-compliant-devices---4063755----"></a>İşlemsel günlüklerde Ayrıca uyumlu olmayan cihazlarda ayrıntılar gösterilir<!-- 4063755  -->
Intune günlüklerini Azure izleyici özelliklerine yönlendirdiğinizde, işletimsel günlükleri de yönlendirebilirsiniz. Bu güncelleştirmede, işletimsel Günlükler uyumlu olmayan cihazlar hakkında bilgi de sağlar.

Bu özellik hakkında daha fazla bilgi için bkz. [Intune 'da günlük verilerini depolama, Olay Hub 'larına veya Log Analytics 'e gönderme](../review-logs-using-azure-monitor.md).

#### <a name="route-logs-to-azure-monitor-in-more-intune-workloads---3804627---"></a>Daha fazla Intune iş yüklerinde günlükleri Azure Izleyici 'ye yönlendirme<!-- 3804627 -->
Intune 'da, denetim ve işletimsel günlükleri Azure Izleyici 'de Olay Hub 'ları, depolama ve Log Analytics 'e yönlendirebilir (**ıntune** > **izleme** > **Tanılama ayarları**). Bu güncelleştirmede, bu günlükleri uyumluluk, konfigürasyonlar, istemci uygulamaları ve daha fazlası dahil olmak üzere daha fazla Intune iş yüküne yönlendirebilirsiniz.

Günlükleri Azure Izleyici 'ye yönlendirme hakkında daha fazla bilgi edinmek için bkz. [depolama, Olay Hub 'ları veya Log Analytics 'e günlük verileri gönderme](../review-logs-using-azure-monitor.md).

#### <a name="create-and-use-mobility-extensions-on-android-zebra-devices-in-intune---3305880-----"></a>Intune 'da Android Zeköşeli cihazlarda Mobility uzantıları oluşturma ve kullanma<!-- 3305880   -->
Bu güncelleştirmede Intune, Android Zeköşeli cihazlarını yapılandırmayı destekler. Özellikle, bir cihaz yapılandırma profili oluşturabilir ve StageNow (**cihaz yapılandırma** > **profilleri** > **profil oluşturma tarafından oluşturulan Mobility uzantıları (MX) profillerini kullanarak Android zeköşeli cihazlarına ayarları uygulayabilirsiniz**  > **Android** for platform > **MX profile (yalnızca zeköşeli)** profil türü için).

Bu özellik hakkında daha fazla bilgi için bkz. [Intune 'da Mobility uzantıları Ile Zeköşeli cihazları kullanma ve yönetme](../configuration/android-zebra-mx-overview.md).

Uygulama hedefi: Android

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Cihaz yönetimi
#### <a name="encryption-report-for-windows-10-devices-in-public-preview---2351538---"></a>Windows 10 cihazları için şifreleme raporu (genel önizlemede)<!-- 2351538 -->
Windows 10 cihazlarınızın şifreleme durumuyla ilgili ayrıntıları görüntülemek için yeni [şifreleme raporu (Önizleme)](../protect/encryption-monitor.md) kullanın. Kullanılabilir Ayrıntılar arasında bir cihaz TPM sürümü, şifreleme hazırlığı ve durumu, hata raporlama ve daha fazlası bulunur.  

#### <a name="access-bitlocker-recovery-keys-from-the-intune-portal-in-public-preview---2351547-----"></a>Intune portalından BitLocker Kurtarma anahtarlarına erişme (genel önizlemede)<!-- 2351547   -->
Artık Azure Active Directory 'tan BitLocker anahtar KIMLIĞI ve BitLocker kurtarma anahtarları hakkındaki [ayrıntıları görüntülemek](../protect/encryption-monitor.md) için Intune 'u kullanabilirsiniz.

#### <a name="microsoft-edge-support-for-intune-scenarios-on-ios-and-android-devices---3411007---"></a>İOS ve Android cihazlarda Intune senaryoları için Microsoft Edge desteği<!-- 3411007 -->
Microsoft Edge, son kullanıcı deneyimine yönelik geliştirmelerin eklenmesiyle birlikte Intune Managed Browser aynı yönetim senaryolarını destekleyecektir. Intune ilkeleri tarafından etkinleştirilen Microsoft Edge kurumsal özellikleri arasında çift kimlik, uygulama koruma ilkesi tümleştirmesi, Azure uygulama proxy tümleştirmesi ve yönetilen sık kullanılanlar ve giriş sayfası kısayolları bulunur. Daha fazla bilgi için bkz. [Microsoft Edge desteği](../apps/app-configuration-managed-browser.md#microsoft-edge-support).

#### <a name="exchange-onlineintune-connector-deprecate-support-for-eas-only-devices--3105122----"></a>Exchange Online/Intune Bağlayıcısı, yalnızca EAS cihazları için desteği kullanımdan kaldırır<!--3105122  -->
Intune Konsolu artık Intune Bağlayıcısı ile Exchange Online 'a bağlı olan EAS cihazların görüntülenmesini ve yönetilmesini desteklememektedir. Bunun yerine, aşağıdaki seçeneklere sahip olursunuz:
- Cihazları mobil cihaz yönetimine (MDM) kaydetme
- Cihazlarınızı yönetmek için Intune Uygulama Koruması Ilkeleri kullanma
- Exchange [Online 'Da istemciler ve mobil](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/clients-and-mobile-in-exchange-online) bölümünde özetlenen Exchange denetimlerini kullanın

#### <a name="search-the-all-devices-page-for-an-exact-device-by-using-name--4254930---"></a>Tüm cihazlar sayfasında [ad] kullanarak tam bir cihaz arayın<!--4254930 -->
Artık tam bir cihaz adı araması yapabilirsiniz. **Intune** > **cihazlara**git  > **tüm cihazlar** arama kutusunda >, tam bir eşleşme aramak için cihaz adını {} ile çevreleyin. Örneğin, **{Device12345}** .

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="monitor-and-troubleshoot"></a>İzleme ve sorun giderme

#### <a name="support-for-additional-connectors-on-the-tenant-status-page---3617202----"></a>Kiracı durum sayfasında ek bağlayıcılar için destek<!-- 3617202  -->
[Kiracı durumu sayfası](../tenant-status.md) artık *Windows Defender Gelişmiş tehdit koruması* (ATP) ve diğer Mobile Threat Defense bağlayıcıları dahil olmak üzere ek bağlayıcıların durum bilgilerini görüntüler.

#### <a name="support-for-the-power-bi-compliance-app-from-the-data-warehouse-blade-in-microsoft-intune---4260871---"></a>Microsoft Intune veri ambarı dikey penceresinden Power BI uyumluluk uygulaması desteği<!-- 4260871 -->
Daha önce, **Intune veri ambarı** dikey penceresindeki **Power BI dosya yükleme** bağlantısı bir Intune veri ambarı raporu (. pbix dosyası) indirilmiştir. Bu rapor Power BI uyumluluk uygulamasıyla değiştirilmiştir. Power BI uyumluluk uygulaması özel yükleme veya kurulum gerektirmez. Power BI çevrimiçi portalda doğrudan açılır ve kimlik bilgilerinizi temel alarak Intune kiracınız için özel olarak verileri görüntüler. Intune ' da, Intune dikey penceresinin sağ tarafındaki **Intune veri ambarını ayarla** bağlantısını seçin. Ardından **Power BI uygulamayı al**' a tıklayın. Daha fazla bilgi için bkz. [Power BI veri ambarına bağlanma](../developer/reports-proc-get-a-link-powerbi.md).


<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="role-based-access-control"></a>Rol tabanlı erişim denetimi

#### <a name="granting-intune-read-only-access-to-some-azure-active-directory-roles---3637917----"></a>Intune 'un bazı Azure Active Directory rollerine salt okuma erişimi verme<!-- 3637917  -->
Intune salt okuma erişimi aşağıdaki Azure AD rollerine verildi. Azure AD rolleriyle verilen izinler, Intune rol tabanlı erişim denetimi (RBAC) ile verilen izinlerin yerini alır.

Intune denetim verilerine salt okuma erişimi:

- Uyumluluk Yöneticisi
- Uyumluluk verileri Yöneticisi

Tüm Intune verilerine salt okuma erişimi:

- Güvenlik Yöneticisi
- Güvenlik operatörü
- Güvenlik okuyucusu

Daha fazla bilgi için bkz. [rol tabanlı erişim denetimi](role-based-access-control.md).

#### <a name="scope-tags-for-ios-app-provisioning-profiles--2934430-----"></a>İOS uygulama sağlama profillerinin kapsam etiketleri<!--2934430   -->
Bir iOS uygulama sağlama profiline bir kapsam etiketi ekleyebilirsiniz, böylece yalnızca rollere sahip olan kişilerin iOS uygulama sağlama profiline erişimi vardır. Daha fazla bilgi için bkz. [RBAC ve kapsam etiketlerini kullanma](scope-tags.md).

#### <a name="scope-tags-for-app-configuration-policies--2371891-----"></a>Uygulama yapılandırma ilkeleri için kapsam etiketleri<!--2371891   -->
Bir uygulama yapılandırma ilkesine kapsam etiketi ekleyebilirsiniz, böylece yalnızca rollere sahip olan kişilerin uygulama yapılandırma ilkesine erişimi vardır. Uygulama yapılandırma ilkesi yalnızca aynı kapsam etiketine atanmış olan uygulamaları hedefleyebilir veya bunlarla ilişkilendirilebilir. Daha fazla bilgi için bkz. [RBAC ve kapsam etiketlerini kullanma](scope-tags.md).

#### <a name="microsoft-edge-support-for-intune-scenarios-on-ios-and-android-devices---3411007---"></a>İOS ve Android cihazlarda Intune senaryoları için Microsoft Edge desteği<!-- 3411007 -->
Microsoft Edge, son kullanıcı deneyimine yönelik geliştirmelerin eklenmesiyle birlikte Intune Managed Browser aynı yönetim senaryolarını destekleyecektir. Intune ilkeleri tarafından etkinleştirilen Microsoft Edge kurumsal özellikleri arasında çift kimlik, uygulama koruma ilkesi tümleştirmesi, Azure uygulama proxy tümleştirmesi ve yönetilen sık kullanılanlar ve giriş sayfası kısayolları bulunur. Daha fazla bilgi için bkz. [Microsoft Edge desteği](../apps/app-configuration-managed-browser.md#microsoft-edge-support).




<!-- ########################## -->
## <a name="february-2019"></a>Şubat 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Uygulama yönetimi
#### <a name="intune-macos-company-portal-dark-mode---3300524----"></a>Şirket Portalı koyu modda Intune macOS<!-- 3300524  -->
Intune macOS Şirket Portalı artık macOS için koyu modu desteklemektedir. MacOS 10.14 + cihazında koyu modu etkinleştirdiğinizde Şirket Portalı, görünümü bu modu yansıtan renklerle ayarlar.

#### <a name="intune-will-leverage-google-play-protect-apis-on-android-devices---2577355-----"></a>Intune, Android cihazlarda API 'Leri koruma Google Play faydalanır<!-- 2577355   -->
Bazı BT yöneticileri, son kullanıcıların mobil telefonlarını veya jailbreaking bir şekilde sona erdirmek için bir KCG yataya sahip olur. Bu davranış, bazen de çok daha fazla olmasa da, Son Kullanıcı cihazlarındaki kuruluşun verilerini korumak için ayarlanmış birçok Intune ilkesinin atlanmasına neden olur. Bu nedenle, Intune hem kayıtlı hem de kayıtlı olmayan cihazlar için kök ve jailbreak algılama sağlar. Bu sürümde, Intune artık kayıtlı olmayan cihazlar için mevcut kök algılama denetimlerimize eklemek üzere API 'Leri Google Play korur. Google, kök algılama denetimlerinden tamamen paylaşmadığı sürece, bu API 'Lerin cihazlarını, cihaz özelleştirmesinden, eski cihazlarda daha yeni işletim sistemi güncelleştirmelerini alabilmesi için kendilerine ait olan kullanıcıları algılamasını bekledik. Daha sonra bu kullanıcıların şirket verilerine erişimi engellenebilir veya şirket hesapları ilke etkin uygulamalarından silinebilirler. Daha fazla değer için, BT yöneticisinin artık Intune Uygulama Koruması dikey penceresinde birkaç raporlama güncelleştirmesi olacaktır. "bayraklı kullanıcılar" raporu, Google Play Protect 'ın SafetyNet API taraması aracılığıyla hangi kullanıcıların algılandığını gösterir, "olası zararlı uygulamalar" raporu Google 'ın uygulama API 'SI taramasını doğrulama aracılığıyla hangi uygulamaların algılandığını gösterir. Bu özellik Android 'de kullanılabilir.

#### <a name="win32-app-information-available-in-troubleshooting-blade---2617342-----"></a>Sorun giderme dikey penceresinde kullanılabilir Win32 uygulama bilgileri<!-- 2617342   -->
Artık, Intune uygulama **sorun giderme** dikey penceresinden bir Win32 uygulama yüklemesi için hata günlüğü dosyalarını toplayabilirsiniz. Uygulama yükleme sorunlarını giderme hakkında daha fazla bilgi için bkz. [uygulama yükleme sorunlarını giderme](./../apps/troubleshoot-app-install.md) ve [Win32 uygulama sorunlarını giderme](./../apps/troubleshoot-app-install.md#win32-app-installation-troubleshooting).

#### <a name="app-status-details-for-ios-apps---3761235-----"></a>İOS uygulamaları için uygulama durumu ayrıntıları<!-- 3761235   -->
Aşağıdakiler ile ilgili yeni uygulama yükleme hatası iletileri vardır:
- Paylaşılan iPad üzerine yüklerken VPP uygulamaları için hata
- Uygulama Mağazası devre dışı bırakıldığında hata
- Uygulama için VPP lisansı bulunamadı
- MDM sağlayıcısı ile sistem uygulamalarını yüklemede hata
- Cihaz kayıp modundayken veya bilgi noktası modundayken uygulamalar yüklenememesi
- Kullanıcı uygulama mağazası 'nda oturum açmamışsa uygulamanın yüklenmesi başarısız oldu

Intune 'da, **istemci uygulamaları**  > **uygulamalar** > "uygulama adı" > **cihaz yüklemesi durumu**' nu seçin. Yeni hata iletileri **durum ayrıntıları** sütununda kullanıma sunulacaktır.

#### <a name="new-app-categories-screen-in-the-company-portal-app-for-windows-10---3834780----"></a>Windows 10 için Şirket Portalı uygulamasındaki yeni uygulama kategorileri ekranı<!-- 3834780  -->
Windows 10 için Şirket Portalı ' de uygulama gözatma ve seçim deneyimini geliştirmek için **uygulama kategorileri** adlı yeni bir ekran eklenmiştir. Kullanıcılar, uygulamalarını **öne çıkan**, **eğitim**ve **üretkenlik**gibi Kategoriler altında sıralanmış olarak görecektir. Bu değişiklik, 10.3.3451.0 ve sonraki sürümlerde Şirket Portalı görüntülenir. Yeni ekranı görüntülemek için bkz. [uygulama kullanıcı arabirimindeki](whats-new-app-ui.md)yenilikler. Şirket Portalı uygulamalar hakkında daha fazla bilgi için bkz. [cihazınızdaki uygulamaları yükleyip paylaşma](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows).  

#### <a name="power-bi-compliance-app---1455231-doc-work-item---"></a>Uyumluluk uygulaması Power BI<!-- 1455231 doc-work-item -->
Intune [Uyumluluk (veri ambarı)](https://aka.ms/intune/datawarehouseapi/getpowerbiapp) uygulamasını kullanarak Power BI çevrimiçi ortamda Intune veri ambarınıza erişin. Bu Power BI uygulamayla, artık önceden oluşturulmuş raporlara herhangi bir kurulum olmadan ve Web tarayıcınızdan çıkmadan erişebilir ve bunları paylaşabilirsiniz. Daha fazla bilgi için bkz. [günlük Power BI uyumluluk uygulamasını değiştirme](../developer/reports-changelog.md#power-bi-compliance-app).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="powershell-scripts-can-run-in-a-64-bit-host-on-64-bit-devices---1862675-----"></a>PowerShell betikleri, 64 bit cihazlarda 64 bitlik bir konakta çalışabilir<!-- 1862675   -->
Bir cihaz yapılandırma profiline bir PowerShell betiği eklediğinizde, komut dosyası her zaman 64 bit işletim sistemlerinde bile 32 bit içinde yürütülür. Bu güncelleştirmeyle, bir yönetici, komut dosyasını 64 bit cihazlarda 64 bitlik bir PowerShell konağında çalıştırabilir (**cihaz yapılandırma** > **PowerShell betikleri** > **Add** > **yapılandırma** > **komut dosyasını 64 bit içinde Çalıştır PowerShell ana bilgisayarı**).

PowerShell kullanma hakkında daha fazla ayrıntı için bkz. [Intune 'Da PowerShell betikleri](../apps/intune-management-extension.md).

Şunlar için geçerlidir: Windows 10 ve üzeri

#### <a name="macos-users-are-prompted-to-update-their-password---1873216---"></a>macOS kullanıcılarının parolasını güncelleştirmesi istenir<!-- 1873216 -->
Intune, macOS cihazlarında **Changeatnextauth** ayarını zorlarken. Bu ayar, uyumluluk parolası ilkeleri veya cihaz kısıtlama parolası profilleri olan son kullanıcıları ve cihazları etkiler. Son kullanıcılara parolasını güncelleştirmek için bir kez sorulur. Bu istem, bir Kullanıcı, cihazda oturum açma gibi kimlik doğrulaması gerektiren bir görevi ilk kez çalıştırdığında oluşur. Kullanıcıların, anahtar zinciri erişimi istemek gibi yönetim ayrıcalıkları gerektiren her şeyi yaparken parolalarını güncelleştirmesi de istenebilir.

Yönetici tarafından yeni veya var olan parola ilkesi değişiklikleri, son kullanıcılara parolasını güncelleştirmek üzere yeniden bir kez daha.

Uygulama hedefi:  
Mac OS

#### <a name="assign-scep-certificates-to-a-userless-macos-device---2340521------"></a>Kullanıcısız macOS cihazına SCEP sertifikaları atama<!-- 2340521    -->
Kullanıcı benzeşimi olmayan cihazlar dahil olmak üzere macOS cihazlarına cihaz özniteliklerini kullanarak Basit Sertifika Kayıt Protokolü (SCEP) sertifikaları atayabilir ve sertifika profilini Wi-Fi veya VPN profilleriyle ilişkilendirebilirsiniz. Bu, Windows, iOS ve Android çalıştıran [Kullanıcı benzeşimi ile ve olmayan CIHAZLARA SCEP sertifikaları atamak](../protect/certificates-profile-scep.md) için zaten sahip olduğumuz desteği genişletir.  Bu güncelleştirme, macOS için bir SCEP sertifika profili yapılandırırken *cihazın* sertifika türünü seçme seçeneğini ekler.

Uygulama hedefi:
- Mac OS

#### <a name="intune-conditional-access-ui-update---2432313-----"></a>Intune koşullu erişim kullanıcı arabirimi güncelleştirmesi<!-- 2432313   -->
Intune konsolunda koşullu erişim için Kullanıcı arabiriminde geliştirmeler yaptık. Bunlar şunları içerir:
- Intune *koşullu erişim* dikey penceresi Azure Active Directory dikey penceresinde değiştirildi. Bu, Intune konsolunun içinden [koşullu erişime](../protect/conditional-access.md) (Azure AD teknolojisi olarak kalır) yönelik ayarların ve yapılandırmaların tam aralığına erişmenizi sağlar. 
- *Şirket içi erişim* dikey penceresini *Exchange erişimi*olarak yeniden adlandırdık ve *Exchange hizmeti Bağlayıcısı* kurulumunu bu yeniden adlandırılmış dikey pencereye yeniden konumlandırdık.  Bu değişiklik, [Exchange Online ve şirket içi ile ilgili ayrıntıları yapılandırdığınız ve](../protect/exchange-connector-install.md)izlediğiniz yerleri birleştirir.  

#### <a name="kiosk-browser-and-microsoft-edge-browser-apps-can-run-on-windows-10-devices-in-kiosk-mode---2935135-----"></a>Bilgi noktası tarayıcısı ve Microsoft Edge tarayıcı uygulamaları, Windows 10 cihazlarında bilgi noktası modunda çalışabilir<!-- 2935135   -->
Windows 10 cihazlarını bilgi noktası modunda kullanarak bir uygulamayı veya birçok uygulamayı çalıştırabilirsiniz. Bu güncelleştirme, aşağıdakiler dahil olmak üzere tarayıcı uygulamalarını bilgi noktası modunda kullanmak için çeşitli değişiklikler içerir:

- Bilgi noktası cihazında (**cihaz yapılandırma** > **profilleri** > **Yeni profil** > **Windows 10 ve üzeri** profil türü Için platform > **bilgi noktası** için Microsoft Edge tarayıcı veya bilgi noktası tarayıcısı 'nı ekleyin ).
- Yeni özellikler ve ayarlar, izin verme veya kısıtlama (**cihaz yapılandırma** > **profilleri** > **Yeni profil** > **Windows 10 ve üzeri** profil türü için Platform > **cihaz kısıtlamaları** ) için kullanılabilir. işaretleriyle

- Microsoft Edge tarayıcısı:
  - Microsoft Edge bilgi noktası modunu kullan
  - Boşta kalma zamanından sonra tarayıcıyı yenile

- Sık Kullanılanlar ve arama:
  - Arama altyapısında değişikliklere izin ver

Bu ayarların listesi için bkz.:

- [Bilgi noktası olarak çalıştırılacak Windows 10 ve üzeri cihaz ayarları](../configuration/kiosk-settings-windows.md)
- [Microsoft Edge tarayıcı cihaz kısıtlamaları](../configuration/device-restrictions-windows-10.md#microsoft-edge-browser)
- [Sık Kullanılanlar ve arama cihaz kısıtlamaları](../configuration/device-restrictions-windows-10.md##favorites-and-search)

Şunlar için geçerlidir: Windows 10 ve üzeri

#### <a name="new-device-restriction-settings-for-ios-and-macos-devices---3448774-----"></a>İOS ve macOS cihazları için yeni cihaz kısıtlama ayarları<!-- 3448774   -->
İOS ve macOS çalıştıran cihazlarda bazı ayarları ve özellikleri kısıtlayabilirsiniz (**cihaz yapılandırma** > **profilleri** > **Yeni profil** > **IOS** veya **MacOS** for platform > **cihaz kısıtlamaları** profil türü için). Bu güncelleştirme, iOS cihazlarında ekran zamanını ayarlama, esım ayarlarını ve hücresel planları değiştirme dahil olmak üzere denetleyebilmeniz için daha fazla özellik ve ayar ekler. Ayrıca, kullanıcının yazılım güncelleştirmelerinin görünürlüğünü erteleyerek macOS cihazlarında içerik önbelleğe almayı engelleyerek.

Kısıtlayabilecek özellikleri ve ayarları görmek için bkz.:

- [iOS cihaz kısıtlama ayarları](../configuration/device-restrictions-ios.md)
- [macOS cihaz kısıtlama ayarları](../configuration/device-restrictions-macos.md)

Uygulama hedefi:

- iOS
- Mac OS

#### <a name="kiosk-devices-are-now-called-dedicated-devices-on-android-enterprise-devices---3598402-----"></a>"Bilgi noktası" cihazları artık Android kurumsal cihazlarda "adanmış cihazlar" olarak adlandırılır<!-- 3598402   -->
Android terimlerle hizalamak için, **bilgi noktası** , Android Kurumsal cihazları için **adanmış cihazlara** (**cihaz yapılandırma**  > **profilleri**  > **profil oluşturma** > * * Android Enterprise for platform ' a değiştirilmiştir > **Cihaz sahibi yalnızca** **adanmış cihazlar**0**cihaz kısıtlamalarını**  > .

Kullanılabilir ayarları görmek için cihaz ayarları ' na giderek [özelliklere izin verin veya kısıtlayın](../configuration/device-restrictions-android-for-work.md#dedicated-device-settings).

Uygulama hedefi:  
Android Kurumsal

#### <a name="safari-and-delaying-user-software-update-visibility-ios-settings-are-moving-in-the-intune-ui---3640850-3803313-----"></a>Safari ve erteleme Kullanıcı yazılımı güncelleştirme görünürlüğü iOS ayarları, Intune kullanıcı arabiriminde taşınıyor<!-- 3640850, 3803313   -->
İOS cihazları için Safari ayarlarını ayarlayabilir ve yazılım güncelleştirmelerini yapılandırabilirsiniz. Bu güncelleştirmede, bu ayarlar Intune kullanıcı arabiriminin farklı bölümlerine taşınıyor:

- Safari ayarları **Safari** 'den (**cihaz yapılandırma** > **profilleri** > **Yeni profil** > **iOS** , profil türü için Platform > **cihaz kısıtlamaları** ) **[yerleşik uygulamalara](../configuration/device-restrictions-ios.md#built-in-apps)** taşınır.
- **Denetimli iOS cihazları için Kullanıcı yazılım güncelleştirme görünürlüğünü geciktirme** ayarı (IOS için**yazılım güncelleştirmeleri** > **güncelleştirme ilkeleri**) **cihaz kısıtlamalarına**taşınıyor  >  **[genel](../configuration/device-restrictions-ios.md#general)** .  Var olan ilkelere etkisi hakkında ayrıntılar için bkz. [iOS yazılım güncelleştirmeleri](../protect/software-updates-ios.md#configure-the-policy).

Ayarların listesi için bkz.:

- [iOS cihaz kısıtlamaları](../configuration/device-restrictions-ios.md) 
- [iOS yazılım güncelleştirmeleri](../protect/software-updates-ios.md)

Bu özellik şu platformlarda geçerlidir:

- iOS

#### <a name="enabling-restrictions-in-the-device-settings-is-renamed-to-screen-time-on-ios-devices---3699164-----"></a>Cihaz ayarlarında kısıtlamaları etkinleştirme, iOS cihazlarında ekran zamanına göre yeniden adlandırılır<!-- 3699164   -->
Denetimli iOS cihazlarında **cihaz ayarlarında etkinleştirme kısıtlamalarını** yapılandırabilirsiniz (**cihaz yapılandırma** > **profilleri** > **Yeni profil** >  Platform > için**iOS** **cihaz** profil türü için kısıtlamalar > **genel**). Bu güncelleştirmede, bu ayar ekran zamanı olarak yeniden adlandırılır **(yalnızca denetimli)** .

Davranış aynıdır. Engelle

- iOS 11.4.1 ve önceki sürümler: **Block** , son kullanıcıların cihaz ayarlarında kendi kısıtlamalarını değiştirmesini engeller. 
- iOS 12,0 ve üzeri: **blok** , son kullanıcıların, içerik & Gizlilik kısıtlamaları da dahil olmak üzere cihaz ayarları 'Nda kendi **Ekran zamanını** ayarlamalarını engeller. İOS 12,0 ' e yükseltilen cihazlar artık cihaz ayarlarındaki kısıtlamalar sekmesini görmez. Bu ayarlar **Ekran Saati** altındadır. 

Ayarların listesi için bkz. [iOS cihaz kısıtlamaları](../configuration/device-restrictions-ios.md#general).

Uygulama hedefi:
- iOS


#### <a name="intune-powershell-module---951068----"></a>Intune PowerShell modülü<!-- 951068  -->
Intune API 'SI için Microsoft Graph aracılığıyla destek sağlayan Intune PowerShell modülü, [Microsoft PowerShell Galerisi](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1902.1.10)artık kullanılabilir.

- [Bu modülün nasıl kullanıldığı hakkında ayrıntılar](https://github.com/Microsoft/Intune-PowerShell-SDK/blob/master/README.md)
- [Bu modülü kullanan senaryo örnekleri](https://github.com/Microsoft/Intune-PowerShell-SDK/blob/master/Samples/README.md)

#### <a name="improved-support-for-delivery-optimization--3183757----"></a>Teslim iyileştirme için geliştirilmiş destek<!--3183757  -->
Teslim iyileştirme 'yi yapılandırmak için Intune 'da desteği genişlettik. Artık, bir [dağıtım iyileştirme ayarlarının](../configuration/delivery-optimization-settings.md) genişletilmiş bir listesini yapılandırabilir ve doğrudan Intune konsolundan cihazlarınıza hedefleyebilirsiniz.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Cihaz yönetimi

#### <a name="rename-an-enrolled-windows-device---1911112----"></a>Kayıtlı bir Windows cihazını yeniden adlandırma<!-- 1911112  -->
Artık kayıtlı bir Windows 10 cihazını (RS4 veya üzeri) yeniden adlandırabilirsiniz. Bunu yapmak için **ıntune**  > **cihazları** ** >  cihaz** seçin > cihazı **Yeniden Adlandır**> bir cihaz seçin. Bu özellik şu anda karma Azure AD Windows cihazlarının yeniden adlandırılmasını desteklemiyor.

#### <a name="auto-assign-scope-tags-to-resources-created-by-an-admin-with-that-scope---3173823----"></a>Kapsam etiketlerini bu kapsama sahip bir yönetici tarafından oluşturulan kaynaklara otomatik olarak ata<!-- 3173823  -->
Yönetici bir kaynak oluşturduğunda, yöneticiye atanan tüm kapsam etiketleri bu yeni kaynaklara otomatik olarak atanır.

### <a name="monitor-and-troubleshoot"></a>İzleme ve sorun giderme

#### <a name="failed-enrollment-report-moves-to-the-device-enrollment-blade---3560202----"></a>Başarısız kayıt raporu cihaz kayıt dikey penceresine taşınıyor<!-- 3560202  -->
**Başarısız** kayıtları raporu, **cihaz kaydı** dikey **penceresinin izleyici** bölümüne taşınmıştır. İki yeni sütun (kayıt yöntemi ve işletim sistemi sürümü) eklenmiştir.

#### <a name="company-portal-abandonment-report-renamed-to-incomplete-user-enrollments--3815076-eemiss---"></a>Şirket Portalı bırakma raporu, tamamlanmamış Kullanıcı kayıtlarına yeniden adlandırıldı<!--3815076 eemiss -->
**Şirket portalı bırakma** raporu, **tamamlanmamış Kullanıcı**kayıtları olarak yeniden adlandırıldı.






<!-- ########################## -->
## <a name="january-2019"></a>Ocak 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Uygulama yönetimi

#### <a name="intune-app-pin---2298397---"></a>Intune uygulama PIN 'ı<!-- 2298397 -->
BT Yöneticisi olarak, bir son kullanıcının Intune uygulama PIN 'inin değişmesi için bekleyeceği gün sayısını yapılandırabilirsiniz. Yeni ayar, *gün sayısından sonra PIN sıfırlamadır* ve **Intune**  > **istemci uygulamaları**  > **Uygulama koruma ilkeleri** ' ni seçerek Azure Portal, ilke  > **ayarları** **Oluştur**  >  0**erişim gereksinimleri**. [İOS](../apps/app-protection-policy-settings-ios.md) ve [Android](../apps/app-protection-policy-settings-android.md) cihazlarda kullanılabilir, bu özellik pozitif bir tamsayı değeri destekler.

#### <a name="intune-device-reporting-fields---2748738---"></a>Intune cihaz raporlama alanları<!-- 2748738 -->
Intune, uygulama kayıt KIMLIĞI, Android üreticisi, model ve güvenlik düzeltme eki sürümü ve iOS modelinin yanı sıra ek cihaz raporlama alanları sağlar. Intune 'da bu alanlar, **istemci uygulamaları** > **Uygulama koruma durumu** ' nu seçip **Uygulama koruma raporu: iOS, Android '** i seçerek kullanılabilir. Ayrıca, bu parametreler cihaz üreticisi için **Izin verilenler** listesi (Android), cihaz modeli Için **izin verilenler** listesi (Android ve iOS) ve en düşük Android güvenlik düzeltme eki sürümü ayarını yapılandırmanıza yardımcı olur.

#### <a name="toast-notifications-for-win32-apps---3136566-----"></a>Win32 uygulamaları için bildirim bildirimleri<!-- 3136566   -->
Her uygulama ataması için son kullanıcı bildirim bildirimlerini göstermeyi bastırın. Intune 'da, **istemci uygulamaları** > **uygulamalar** ' ı seçin > Uygulama > **atamaları** > **Ekle grupları**' nı seçin.

#### <a name="intune-app-protection-policies-ui-update---3251427----"></a>Intune uygulama koruma ilkeleri kullanıcı arabirimi güncelleştirmesi<!-- 3251427  -->
Intune uygulama koruması için ayarların ve düğmelerin etiketlerini, her birinin anlaşılması kolay hale getirmek üzere değiştirdik. Bazı değişiklikler şunları içerir:  
- Denetimler **evet**  / , birincil olarak **engellenme**  / **izin ver** ve **devre dışı bırak** ** /  denetimleri** **etkinleştirir** . Etiketler de güncelleştirilir.  
- Ayarlar yeniden biçimlendirilir, bu nedenle daha iyi gezinti sağlamak için ayar ve etiketi denetimin içinde yan yana olur.

Varsayılan ayarlar ve ayar sayısı aynı kalır, ancak bu değişiklik kullanıcının seçili uygulama koruma ilkelerini uygulamak için ayarları daha kolay anlamasına, gezinmeye ve kullanmasına olanak sağlar. Bilgi için bkz. [iOS ayarları](../apps/app-protection-policy-settings-ios.md) ve [Android ayarları](../apps/app-protection-policy-settings-android.md).

#### <a name="additional-settings-for-outlook---3301182----"></a>Outlook için ek ayarlar<!-- 3301182  -->
Artık Intune kullanarak iOS ve Android için Outlook için aşağıdaki ek ayarları yapılandırabilirsiniz:

- İOS ve Android 'de Outlook 'ta yalnızca iş veya okul hesaplarının kullanılmasına izin ver
- Office 365 ve karma modern kimlik doğrulaması şirket içi hesaplar için modern kimlik doğrulaması dağıtma
- Temel kimlik doğrulaması seçildiğinde e-posta profilindeki Kullanıcı adı alanı için `SAMAccountName` kullanın
- Kişilerin kaydedilmesine izin ver
- Dış alıcıları yapılandırma posta Ipuçları
- **Odaklanmış gelen kutusu** yapılandırma
- İOS için Outlook 'a erişmek üzere Biyometri iste
- Dış görüntüleri engelle

> [!NOTE]
> Şirket kimliklerine erişimi yönetmek için Intune Uygulama Koruması ilkeleri kullanıyorsanız, **Biyometri gerektir**' i etkinleştirmemelisiniz. Daha fazla bilgi için bkz. [IOS erişim ayarları](../apps/app-protection-policy-settings-ios.md#access-requirements) ve [Android erişim ayarları](../apps/app-protection-policy-settings-android.md#access-requirements)için **erişim için kurumsal kimlik bilgileri gerektir** .

Daha fazla bilgi için bkz. [Microsoft Outlook yapılandırma ayarları](../apps/app-configuration-policies-outlook.md).

#### <a name="delete-android-enterprise-apps---1352553---"></a>Android kurumsal uygulamalarını silme<!-- 1352553 -->
Microsoft Intune yönetilen Google Play uygulamalarını silebilirsiniz. Yönetilen Google Play uygulamasını silmek için Azure portalında Microsoft Intune'u açın ve **İstemci uygulamaları** > **Uygulamalar**'ı seçin. Uygulama listesinden, yönetilen Google Play uygulamasının sağ tarafındaki üç noktayı (...) seçin ve görüntülenen listeden **Sil**'i seçin. Uygulama listesinden yönetilen Google Play uygulamasını sildikten sonra, yönetilen Google Play uygulamasının onayı otomatik olarak kaldırılır.

#### <a name="managed-google-play-app-type---1352580---"></a>Yönetilen Google Play uygulama türü<!-- 1352580 -->
**Yönetilen Google Play** uygulama türü, Intune 'a [yönetilen Google Play uygulamalarını](https://play.google.com/work/search?q=microsoft&c=apps) özel olarak eklemenize olanak tanır. Intune Yöneticisi olarak artık Intune 'da onaylanan yönetilen Google Play uygulamalarına gözatıp arayabilir, bunları onaylayabilir, eşitleyebilir ve atayabilirsiniz.  Artık ayrıca yönetilen Google Play konsoluna göz atmanız ve yeniden kimlik doğrulaması yapmanız gerekmez.  Intune 'da, **istemci uygulamaları** > **uygulama** > **Ekle**' yi seçin. **Uygulama türü** listesinde, uygulama türü olarak **yönetilen Google Play** ' yi seçin.

#### <a name="default-android-pin-keyboard---3802457---"></a>Varsayılan Android PIN klavyesi<!-- 3802457 -->
Android cihazlarında ' numeric ' PIN türüyle Intune Uygulama Koruması Ilkesi (uygulama) PIN 'i ayarlamış olan son kullanıcılar için, daha önce tasarlanmış olan sabit Android Klavye Kullanıcı arabirimi yerine varsayılan Android klavye görüntülenir. Bu değişiklik, hem Android hem de iOS 'ta varsayılan klavye kullanılırken ' numeric ' ve/veya ' geçiş kodu ' olan her iki PIN türü için de tutarlı hale getirilir. Android 'de uygulama PIN 'i gibi son kullanıcı erişimi ayarları hakkında daha fazla bilgi için bkz. [Android erişim gereksinimleri](../apps/app-protection-policy-settings-android.md#access-requirements).


<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="administrative-templates-are-in-public-preview-and-moved-to-their-own-configuration-profile----3322847---"></a>Yönetim Şablonları genel önizlemede ve kendi yapılandırma profilinize taşınır <!-- 3322847 -->

Intune 'daki Yönetim Şablonları (**cihaz yapılandırma** > **Yönetim Şablonları**) Şu anda genel önizlemededir. Bu güncelleştirmeyle:

- Yönetim Şablonları, Intune 'da yönetilebilen 300 ayarlarını içerir. Daha önce bu ayarlar yalnızca Grup İlkesi Düzenleyicisi 'nde yer almaktadır.
- Yönetim Şablonları genel önizlemede kullanılabilir.
- Yönetim Şablonları **cihaz yapılandırma** > **Yönetim şablonlarından** **cihaz yapılandırmasına**taşınıyor  > **profiller** >  bir platformda**profil oluşturma** > ' iseçin  **Windows 10 ve üzeri** > **profil türünde**, **Yönetim Şablonları**' nı seçin.
- Raporlama etkin

Bu özellik hakkında daha fazla bilgi edinmek için, [Grup İlkesi ayarlarını yapılandırmak üzere Windows 10 şablonlarına](../configuration/administrative-templates-windows.md)gidin.

Şunlar için geçerlidir: Windows 10 ve üzeri

#### <a name="use-smime-to-encrypt-and-sign-multiple-devices-for-a-user---1333642---"></a>Bir kullanıcı için birden çok cihazı şifrelemek ve imzalamak için S/MIME kullanın<!-- 1333642 -->
Bu güncelleştirme, içeri aktarılmış yeni bir sertifika profili kullanan S/MIME e-posta şifrelemesi içerir (**Cihaz yapılandırması** > **Profiller** > **Profil oluşturun** > platform seçin > **PKCS içeri aktarılan sertifika** profil türü). Intune’da sertifikaları PFX biçiminde içeri aktarabilirsiniz. Intune, aynı sertifikaları tek bir kullanıcı tarafından kaydedilen birden fazla cihaza teslim edebilir. Ayrıca şunları da içerir:
- Yerel iOS e-posta profili, PFX biçiminde içeri aktarılan sertifikaları kullanan S/MIME şifrelemesini etkinleştirmeyi destekler.
- Windows Phone 10 cihazlarındaki yerel posta uygulaması otomatik olarak S/MIME sertifikasını kullanır.
- Özel sertifikalar, birden fazla platforma teslim edilebilir. Ancak tüm e-posta uygulamaları, S/MIME’yi desteklemez.
- Diğer platformlarda S/MIME’yi etkinleştirmek için posta uygulamasını el ile yapılandırmanız gerekebilir.  
- S/MIME şifrelemesini destekleyen e-posta uygulamaları, S/MIME e-posta şifrelemesi için sertifika alma işlemini MDM’nin destekleyemeyeceği bir şekilde halleder, ör. yayımcılarının sertifika deposundan okuma.
Bu özellik hakkında daha fazla bilgi için bkz. [S/MIME Overview e-postayı imzalama ve şifreleme](../protect/certificates-s-mime-encryption-sign.md).
Desteklenir: Windows, Windows Phone 10, macOS, iOS, Android

#### <a name="new-options-to-automatically-connect-and-persist-rules-when-using-dns-settings-on-windows-10-and-later-devices---1333665-2999078---"></a>Windows 10 ve üzeri cihazlarda DNS ayarlarını kullanırken kuralların otomatik olarak bağlanmasına ve kalıcı hale getirilmesi için yeni seçenekler<!-- 1333665, 2999078 -->
Windows 10 ve üzeri cihazlarda, contoso.com gibi etki alanlarını çözümlemek için DNS sunucularının bir listesini içeren bir VPN yapılandırma profili oluşturabilirsiniz. Bu güncelleştirme, ad çözümlemesi için yeni ayarlar içerir (**cihaz yapılandırma** > **profilleri** > **Profil oluştur** > Platform için **Windows 10 ve üstünü** seçin > profil türü için **VPN** seçin > **DNS ayarlar** >**ekleme**): 
- **Otomatik olarak bağlan**: **etkinleştirildiğinde**, cihaz girdiğiniz bir etki alanına (contoso.com gibi) BAĞLANDıĞıNDA cihaz otomatik olarak VPN 'e bağlanır.
- **Persistent**: varsayılan olarak, CIHAZ bu VPN profili kullanılarak bağlandığı sürece tüm ad çözümleme ilkesi tablosu (NRPT) kuralları etkin olur. Bu ayar bir NRPT kuralında **etkinleştirildiğinde** , VPN bağlantısı kesilse bile kural cihazda etkin kalır. Kural, VPN profili kaldırılana kadar veya kural el ile kaldırılana kadar veya PowerShell kullanılarak yapılabileceği sürece kalır.
[Windows 10 VPN ayarları](../configuration/vpn-settings-windows-10.md) , ayarları açıklar.

#### <a name="use-trusted-network-detection-for-vpn-profiles-on-windows-10-devices---1500165---"></a>Windows 10 cihazlarda VPN profilleri için güvenilen ağ algılamayı kullanma<!-- 1500165 -->
Güvenilen ağ algılama kullanırken, Kullanıcı zaten güvenilir bir ağda olduğunda VPN profillerinin otomatik olarak bir VPN bağlantısı oluşturmasını engelleyebilirsiniz. Bu güncelleştirmeyle, Windows 10 ve üzeri sürümlerini çalıştıran cihazlarda güvenilen ağ algılamasını etkinleştirmek için DNS sonekleri ekleyebilirsiniz (**cihaz yapılandırma** > **profilleri** > **Profil oluştur** > **Windows 10 ve üzeri** için profil türü için Platform > **VPN** ).
[Windows 10 VPN ayarları](../configuration/vpn-settings-windows-10.md) geçerli VPN ayarlarını listeler.

#### <a name="manage-windows-holographic-for-business-devices-used-by-multiple-users---1907917-1063203---"></a>Birden çok kullanıcı tarafından kullanılan Windows holographic for Business cihazlarını yönetme<!-- 1907917, 1063203 -->
Şu anda, özel bir OMA-URI ayarı kullanarak Windows 10 ve Windows holographic for Business cihazlarında paylaşılan bılgısayar ayarlarını yapılandırabilirsiniz. Bu güncelleştirmeyle paylaşılan cihaz ayarlarını yapılandırmak için yeni bir profil eklenir (**cihaz yapılandırma** > **profilleri** > **Profil oluştur** > **Windows 10 ve üzeri** > **paylaşılan çok kullanıcılı cihaz**).
Bu özellik hakkında daha fazla bilgi edinmek için, [paylaşılan cihazları yönetmek üzere Intune ayarları](../configuration/shared-user-device-settings.md)' na gidin.
Uygulama hedefi: Windows 10 ve üzeri, Windows holographic for Business

#### <a name="new-windows-10-update-settings--2626030--2512994----"></a>Yeni Windows 10 güncelleştirme ayarları<!--2626030  2512994  -->
[Windows 10 güncelleştirme halkalarınız](../protect/windows-update-for-business-configure.md)için şunları yapılandırabilirsiniz:
- **Otomatik Güncelleştirme davranışı** - *Ekim 2018 güncelleştirmesini* çalıştıran makinelerde bir Windows 10 makinesinde özgün otomatik güncelleştirme ayarlarını geri yüklemek için yeni bir seçenek kullanın, *varsayılana sıfırlayın*
- **Kullanıcının Windows güncelleştirmelerini duraklatmasını engelle** -kullanıcılarınızın güncelleştirme yüklemesini kendi makinelerinin *ayarlarından* duraklatmalarına Izin veren yeni bir yazılım güncelleştirmeleri ayarı yapılandırın.

#### <a name="ios-email-profiles-can-use-smime-signing-and-encryption---2662949---"></a>iOS e-posta profilleri, S/MIME imzalama ve şifrelemeyi kullanabilir<!-- 2662949 -->
Farklı ayarlar içeren bir e-posta profili oluşturabilirsiniz. Bu güncelleştirme, iOS cihazlarında e-posta iletişimleri imzalama ve şifreleme için kullanılabilen S/MIME ayarlarını içerir (**cihaz yapılandırma** > **profilleri** > **Profil oluştur** > Platform için **iOS** 'u seçin >  **Profil türü için e-posta** .
[iOS e-posta yapılandırma ayarları](../configuration/email-settings-ios.md) ayarları listeler.

#### <a name="some-bitlocker-settings-support-windows-10-pro-edition---2727036---"></a>Bazı BitLocker ayarları Windows 10 Pro Edition 'ı destekler<!-- 2727036 -->
BitLocker da dahil olmak üzere Windows 10 cihazlarında Endpoint Protection ayarlarını ayarlayan bir yapılandırma profili oluşturabilirsiniz. Bu güncelleştirme, bazı BitLocker ayarları için Windows 10 Professional Edition desteği ekler.
Bu koruma ayarlarını görmek için [Windows 10 Için Endpoint Protection ayarları](../protect/endpoint-protection-windows-10.md#windows-encryption)' na gidin.

#### <a name="shared-device-configuration-is-renamed-to-lock-screen-message-for-ios-devices-in-the-azure-portal---2809362---"></a>Paylaşılan cihaz yapılandırması, Azure portal iOS cihazları için kilit ekranı Iletisi olarak yeniden adlandırıldı<!-- 2809362 -->
İOS cihazları için bir yapılandırma profili oluşturduğunuzda, kilit ekranında belirli bir metni göstermek üzere **paylaşılan cihaz yapılandırma** ayarları ekleyebilirsiniz. Bu güncelleştirme aşağıdaki değişiklikleri içerir: 
- Azure portal **paylaşılan cihaz yapılandırma** ayarları "kilit ekranı iletisi (yalnızca denetimli)" olarak yeniden adlandırılır (**cihaz yapılandırması** > **profiller** > **Profil oluştur** > Platform için **iOS** seçin > Profil türü için **cihaz özellikleri** > **kilit ekran iletisi**) seçin.
- Kilit ekranı iletileri eklerken, **varlık etiketi bilgileri** ve **kilit ekranı dipnotu**içinde değişken olarak bir seri numarası, cihaz adı veya cihaza özgü bir değer ekleyebilirsiniz. Örneğin, `Device name: {{devicename}}` veya `Serial number is {{serialnumber}}` girerek süslü ayraçları kullanabilirsiniz. [iOS belirteçleri](../apps/app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) , kullanılabilecek belirteçleri listeler.
[Kilit ekranında iletileri görüntüleme ayarları](../configuration/ios-device-features-settings.md#lock-screen-message) , ayarları listeler.

#### <a name="new-app-store-doc-viewing-gaming-device-restriction-settings-added-to-ios-devices---2827760--"></a>İOS cihazlarına yeni uygulama Mağazası, belge görüntüleme, oyun cihaz kısıtlama ayarları eklendi<!-- 2827760-->
**Cihaz yapılandırma**  > **profiller**  >  profil**oluşturma**  >  platform Için**iOS** > **cihaz kısıtlamaları** > **Uygulama Mağazası, belge görüntüleme, oyun, oyunlar**için aşağıdaki ayarlar Eklendi: yönetilen uygulamaların, yönetilmeyen kişiler hesaplarına kişi yazmasına Izin ver ayarı, yönetilmeyen uygulamaların yönetilen kişiler hesaplarından okunmasını sağlar bu ayarları görmek Için [iOS cihaz kısıtlamalarına](../configuration/device-restrictions-ios.md#app-store-doc-viewing-gaming)gidin.

#### <a name="new-notification-hints-and-keyguard-settings-to-android-enterprise-device-owner-devices---3201839-3201843---"></a>Android kurumsal cihaz sahibi cihazlara yeni bildirim, ipucu ve keyguard ayarları<!-- 3201839 3201843 -->
Bu güncelleştirme, cihaz sahibi olarak çalışırken Android kurumsal cihazlarda çeşitli yeni özellikler içerir. Bu özellikleri kullanmak için **cihaz yapılandırma** > **profiller** >  **platformda** **Profil oluştur** > ' yi seçin, **Android kurumsal** > **profil türü**' ni seçin, **yalnızca cihaz sahibi**' i seçin @no__ t-9**cihaz kısıtlamaları**.

Yeni özellikler şunları içerir:

- Gelen çağrılar, sistem uyarıları, sistem hataları ve daha fazlasını içeren sistem bildirimlerinin gösterilmesini devre dışı bırakın.
- İlk kez açılan uygulamalar için başlangıç öğreticilerini ve ipuçlarını atla ' yı önerir.
- Kamera, bildirimler, parmak izi kilidi açma ve daha fazlası gibi gelişmiş keyguard ayarlarını devre dışı bırakın.

Ayarları görmek için [Android kurumsal cihaz kısıtlama ayarları](../configuration/device-restrictions-android-for-work.md)' na gidin.

#### <a name="android-enterprise-device-owner-devices-can-use-always-on-vpn-connections---3202194---"></a>Android kurumsal cihaz sahibi cihazları her zaman VPN bağlantılarında kullanılabilir<!-- 3202194 -->
Bu güncelleştirmede, Android kurumsal cihaz sahibi cihazlarda her zaman açık VPN bağlantılarını kullanabilirsiniz. Her zaman açık VPN bağlantıları; kullanıcı cihazının kilidini açtığında, cihaz yeniden başlatıldığında veya kablosuz ağ değiştiğinde bağlı kalır veya hemen tekrar bağlanır. Bağlantıyı “kilitli”moduna da alabilirsiniz, böylece VPN bağlantısı etkin olana kadar tüm ağ trafiği engellenir.
**Cihaz yapılandırma** > **profillerdeki**her zaman VPN 'yi etkinleştirebilirsiniz  > **profil oluşturma** > **Android Enterprise** for platform > **cihaz** sahibi yalnızca **Bağlantı >** ayarlar. Ayarları görmek için [Android kurumsal cihaz kısıtlama ayarları](../configuration/device-restrictions-android-for-work.md)' na gidin.

#### <a name="new-setting-to-end-processes-in-task-manager-on-windows-10-devices---3285177---"></a>Windows 10 cihazlarında Görev Yöneticisi 'nde son işlemlerin yeni ayarı<!-- 3285177 --> 
Bu güncelleştirme, Windows 10 cihazlarında Görev Yöneticisi 'ni kullanarak son işlemlere yönelik yeni bir ayar içerir. Cihaz yapılandırma profili (**cihaz yapılandırma**  > **profilleri** kullanarak  > **profil oluşturma** > **platformda**, **profil türü**' nde **Windows > 10** ' u seçin, **cihaz kısıtlamaları** ' nı seçin. **genel** ayarları  > ), bu ayarı izin vermeyi veya engellemeniz tercih edersiniz.
Bu ayarları görmek için [Windows 10 cihaz kısıtlama ayarları](../configuration/device-restrictions-windows-10.md)' na gidin.
Şunlar için geçerlidir: Windows 10 ve üzeri

#### <a name="use-microsoft-recommended-settings-with-security-baselines-public-preview---2055484-----"></a>Microsoft tarafından önerilen ayarları güvenlik temellerinde kullanın (Genel Önizleme)<!-- 2055484   -->

Intune, Windows Defender ATP ve Office 365 ATP dahil güvenliğe odaklı diğer hizmetlerle tümleşir. Müşteriler, Microsoft 365 hizmetleri çapında ortak bir strateji ve birbiriyle bütünleşen bir dizi uçtan uca güvenlik iş akışı istiyor. Amacımız, stratejileri birbiriyle uyumlu hale getirmek ve güvenlik işlemleri ve sık kullanılan yönetici görevleri arasında bir köprü oluşturan çözümler geliştirmek. Intune olarak bu amaca Microsoft tarafından önerilen bir dizi "Güvenlik taban çizgisini" (**Intune** > **Güvenlik taban çizgileri**) yayımlayarak ulaşmayı hedefliyoruz.  Yönetici doğrudan bu temellerden güvenlik ilkeleri oluşturabilir ve bunları kullanıcılarına dağıtabilir. Kuruluşunuzun ihtiyaçlarını karşılamak için en iyi yöntem önerilerini de özelleştirebilirsiniz. Intune, cihazların bu taban çizgilerle uyumlu kalmasını sağlar ve yöneticilere uyumlu olmayan kullanıcıları ve cihazları bildirir.

Bu özellik genel önizlemede olduğundan, şimdi oluşturulan tüm profiller, genel kullanıma açık olan güvenlik temelleri şablonlarına (GA) geçmeyecektir. Üretim ortamınızda bu önizleme şablonlarını kullanmayı planlamalısınız.

Güvenlik temelleri hakkında daha fazla bilgi edinmek için bkz. [Intune 'Da Windows 10 güvenlik temeli oluşturma](../protect/security-baselines-monitor.md).

Bu özellik için geçerlidir: Windows 10 ve üzeri

#### <a name="non-administrators-can-enable-bitlocker-on-windows-10-devices-joined-to-azure-ad---2147379-----"></a>Yönetici olmayanlar, Azure AD 'ye katılmış Windows 10 cihazlarında BitLocker 'ı etkinleştirebilir<!-- 2147379   -->
Windows 10 cihazlarında BitLocker ayarlarını etkinleştirdiğinizde (**cihaz yapılandırma**  > **profilleri**  >  profil için**Windows 10 ve üzeri** > için**Profil oluştur**  >  profil türü için **uç nokta koruması** > **Windows şifrelemesi**), BitLocker ayarlarını eklersiniz.

Bu güncelleştirme, standart kullanıcıların (yönetici olmayanlar) şifrelemeyi etkinleştirmesine izin veren yeni bir BitLocker ayarı içerir.

Ayarları görmek için [Windows 10 Için Endpoint Protection ayarları](../protect/endpoint-protection-windows-10.md#windows-encryption)' na gidin.

#### <a name="check-for-configuration-manager-compliance---2192052--eepublished----"></a>Configuration Manager uyumluluğunu denetle<!-- 2192052  eepublished  -->
Bu güncelleştirme, yeni bir System Center Configuration Manager uyumluluk ayarı içerir (**cihaz uyumluluk** > **ilkeleri** > **Ilke oluştur** > **Windows 10 ve üzeri** > **Configuration Manager Uyumluluk**). Configuration Manager, Intune uyumluluğuna sinyal gönderir. Bu ayarı kullanarak, tüm Configuration Manager sinyallerinin "uyumlu" döndürmesini zorunlu kılabilirsiniz.

Örneğin, tüm yazılım güncelleştirmelerinin cihazlarda yüklü olmasını gerektirirsiniz. Configuration Manager’da bu gereksinim, “Yüklü” durumundadır. Cihazdaki herhangi bir program bilinmeyen durumdaysa, cihaz Intune 'da uyumlu değildir.

[Configuration Manager uyumluluğu](../protect/compliance-policy-create-windows.md#configuration-manager-compliance) bu ayarı açıklar.

Şunlar için geçerlidir: Windows 10 ve üzeri

#### <a name="customize-wallpaper-on-supervised-ios-devices-using-a-device-configuration-profile---2809324-----"></a>Denetimli iOS cihazlarında bir cihaz yapılandırma profili kullanarak duvar kağıdını özelleştirme<!-- 2809324   -->
İOS cihazları için bir cihaz yapılandırma profili oluştururken, bazı özellikleri (**cihaz yapılandırma**  > **profilleri**  > , platform > **cihaz özellikleri** için**iOS**  > **profili oluşturma** ' yı özelleştirebilirsiniz. profil türü için). Bu güncelleştirme, yöneticinin ana ekranda veya kilit ekranında bir. png,. jpg veya. JPEG görüntüsü kullanmasına izin veren yeni **duvar kağıdı** ayarlarını içerir. Bu duvar kağıdı ayarları yalnızca denetimli cihazlar için geçerlidir. 

Bu ayarların listesi için bkz. [iOS cihaz özelliği ayarları](../configuration/ios-device-features-settings.md).

#### <a name="windows-10-kiosk-is-generally-available---3594661----"></a>Windows 10 bilgi noktası genel kullanıma sunuldu<!-- 3594661  -->
Bu güncelleştirmede, Windows 10 ve üzeri cihazlarda bilgi noktası özelliği genel kullanıma sunuldu (GA). Ekleyebileceğiniz ve yapılandırabileceğiniz tüm ayarları görmek için bkz. [Windows 10 Için bilgi noktası ayarları (ve üzeri)](../configuration/kiosk-settings.md).

#### <a name="contact-sharing-via-bluetooth-is-removed-in-device-restrictions--device-owner-for-android-enterprise---3598396-----"></a>Bluetooth aracılığıyla kişi paylaşımı, Android Enterprise için cihaz sahibi > cihaz kısıtlamalarında kaldırılmıştır<!-- 3598396   -->
Android kurumsal cihazlar için bir cihaz kısıtlamaları profili oluşturduğunuzda, **Bluetooth ayarı aracılığıyla bir Iletişim paylaşımı** vardır. Bu güncelleştirmede, **Bluetooth Ile kişi paylaşımı** ayarı kaldırılır (**cihaz yapılandırma** > **profilleri** > **profil oluşturma** > **Android Enterprise** for platform > **cihaz kısıtlamaları** Profil türü için > **genel**) cihaz sahibi >.

**Bluetooth Ile kişi paylaşımı** ayarı, Android kurumsal cihaz sahibi yönetimi için desteklenmez. Bu ayar kaldırıldığında, bu ayar etkin ve ortamınızda yapılandırılmış olsa bile, hiçbir cihazı veya kiracıyı etkilemez.

Ayarların geçerli listesini görmek için [Android kurumsal cihaz ayarları ' na giderek özelliklere izin verin veya kısıtlayın](../configuration/device-restrictions-android-for-work.md).

Uygulama hedefi: Android kurumsal cihaz sahibi


<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="more-detailed-enrollment-restriction-failure-messaging---3111564---"></a>Daha ayrıntılı kayıt kısıtlaması hata iletileri<!-- 3111564 -->
Kayıt kısıtlamaları karşılanmazsa daha ayrıntılı hata iletileri kullanılabilir. Bu iletileri görmek için **ıntune** >  >**sorun giderme** ' ye gidin ve kayıt hataları tablosunu denetleyin. Daha fazla bilgi için [kayıt hatalarının listesine](help-desk-operators.md#enrollment-failure-reference)bakın.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Cihaz yönetimi
#### <a name="preview-of-support-for-android-corporate-owned-fully-managed-devices---1574342----"></a>Android şirkete ait, tam olarak yönetilen cihazlar için destek önizlemesi<!-- 1574342  -->
Intune artık cihazların tamamen yönettiği ve bireysel kullanıcılarla ilişkili olduğu şirkete ait bir "cihaz sahibi" senaryosu olan tam olarak yönetilen Android cihazlarını desteklemektedir. Bu, yöneticilerin tüm cihazı yönetmesine, iş profillerinin genişletilmiş bir dizi ilke denetimine zorlayacağına ve kullanıcıların yalnızca yönetilen Google Play uygulama yüklemesini kısıtlamalarına olanak tanır. Daha fazla bilgi için bkz. [Android tam olarak yönetilen cihazların Intune kaydını ayarlama](../enrollment/android-fully-managed-enroll.md) ve [adanmış cihazlarınızı veya tam olarak yönetilen cihazları kaydetme](../enrollment/android-dedicated-devices-fully-managed-enroll.md).  Bu özelliğin önizlemede olduğunu lütfen unutmayın. Sertifikalar, uyumluluk ve koşullu erişim gibi bazı Intune özellikleri şu anda Android tam olarak yönetilen Kullanıcı cihazlarıyla birlikte kullanılamaz.

#### <a name="selective-wipe-support-for-wip-without-enrollment-devices---1434452---"></a>Kayıt cihazları olmadan WıP için seçmeli temizleme desteği<!-- 1434452 -->
Kayıt olmadan Windows Information Protection (WıP-WE), tüm MDM kaydına gerek duymadan müşterilerin Windows 10 cihazlarında kurumsal verilerini korumalarına olanak sağlar. Belgeler bir WıP-WE ilkesiyle korunduktan sonra, korunan veriler bir Intune Yöneticisi tarafından seçmeli olarak silinebilir. Kullanıcı ve cihazı seçip silme isteği gönderdiğinizde, WıP-WE ilkesi aracılığıyla korunan tüm veriler kullanılamaz hale gelir. Azure portalındaki Intune'dan **Mobil uygulama** > **Uygulama seçmeli silme**'yi seçin.


<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="monitor-and-troubleshoot"></a>İzleme ve sorun giderme

#### <a name="tenant-status-dashboard---1124854---"></a>Kiracı durumu panosu<!-- 1124854 -->
Yeni [kiracı durumu sayfası](tenant-status.md) , kiracınızın durumunu ve ilgili ayrıntılarını görüntüleyebileceğiniz tek bir konum sağlar.  Pano dört alana ayrılmıştır:
- **Kiracı ayrıntıları** -kiracı adınızı ve konumunuzu, MDM yetkilinizi, kiracınızdaki toplam kayıtlı cihazları ve lisans sayılarınızı içeren bilgileri görüntüler. Bu bölüm, kiracınız için geçerli hizmet sürümünü de listeler.
- **Bağlayıcı durumu** -yapılandırdığınız kullanılabilir bağlayıcılar hakkındaki bilgileri görüntüler ve henüz etkinleştirmediyseniz, bu bilgileri de listeleyebilir.  
   Her bağlayıcının geçerli durumuna bağlı olarak, bunlar sağlıklı, uyarı veya sağlıksız olarak işaretlenir. Detaya gitmek ve ayrıntıları görüntülemek veya ilgili ek bilgileri yapılandırmak için bir bağlayıcı seçin.
- **Intune hizmet durumu** -kiracınız için etkin olaylar veya kesintiler hakkındaki ayrıntıları görüntüler. Bu bölümdeki bilgiler doğrudan Office Ileti merkezinden alınır.
- **Intune haberleri** -kiracınız için etkin iletileri görüntüler. Kiracınız en son Intune özelliklerini aldığında, iletiler bildirimler gibi şeyler içerir.  Bu bölümdeki bilgiler doğrudan Office Ileti merkezinden alınır.

#### <a name="new-help-and-support-experience-in-company-portal-for-windows-10---1488939--"></a>Windows 10 için Şirket Portalı yeni yardım ve destek deneyimi<!-- 1488939-->
Yeni Şirket Portalı yardım & destek sayfası, kullanıcıların uygulama ve erişim sorunlarına yönelik sorun giderme ve yardım istemesine yardımcı olur. Yeni sayfadan hata ve tanılama günlüğü ayrıntılarına e-posta gönderebilir ve kuruluşunuzun yardım masası ayrıntılarını bulabilirsiniz. Ayrıca ilgili Intune belgelerinin bağlantılarıyla birlikte bir SSS bölümü de bulacaksınız.

#### <a name="new-help-and-support-experience-for-intune---3307080---"></a>Intune için yeni yardım ve destek deneyimi<!-- #3307080 -->
Sonraki birkaç güne kadar tüm kiracılara yönelik yeni yardım ve destek deneyimini kullanıma sunuyoruz. Bu yeni deneyim Intune için kullanılabilir ve [Azure Portal](https://portal.azure.com/)Intune Blade kullanılırken erişilebilir.
Yeni deneyim, sorununuzu kendi kelimelerinizle açıklamanıza ve sorun giderme içgörüleri ile Web tabanlı düzeltme içeriği almanıza olanak tanır. Bu çözümler, Kullanıcı tarafından yönetilen kural tabanlı makine öğrenimi algoritması aracılığıyla sunulur. Soruna özgü kılavuza ek olarak, yeni durum oluşturma iş akışını kullanarak e-posta veya telefon ile bir destek talebi açabilirsiniz. Bu yeni deneyim, yardım ve destek ' i açtığınızda kullandığınız konsolun alanını temel alan, önceden seçilmiş bir statik seçenekler kümesinin önceki yardım ve destek deneyiminin yerini alır.
Daha fazla bilgi için bkz. [Microsoft Intune için destek alma](get-support.md).

#### <a name="new-operational-logs-and-ability-to-send-logs-to-azure-monitor-services---3762211----"></a>Yeni işletimsel Günlükler ve Azure Izleyici hizmetlerine günlük gönderme yeteneği<!-- 3762211  -->
Intune 'da değişiklikler yapıldığından olayları izleyen yerleşik denetim günlüğü vardır. Bu güncelleştirme, aşağıdakiler de dahil olmak üzere yeni günlük özellikleri içerir: 
- Başarılı ve başarısız denemeler dahil olmak üzere, kayıtlı kullanıcılar ve cihazlarla ilgili ayrıntıları gösteren işletimsel Günlükler (Önizleme).
- Denetim günlükleri ve işletimsel Günlükler, depolama hesapları, Olay Hub 'ları ve Log Analytics de dahil olmak üzere Azure Izleyici 'ye gönderilebilir. Bu hizmetler, splunk ve QRadar gibi analizler kullanmanızı ve günlük verilerinizin görselleştirmelerini almanızı sağlar.

[Intune 'da günlük verilerini depolama, Olay Hub 'ları veya Log Analytics 'e gönderme](../review-logs-using-azure-monitor.md) , bu özellik hakkında daha fazla bilgi sağlar.

#### <a name="skip-more-setup-assistant-screens-on-an-ios-dep-device---2687509----"></a>İOS DEP cihazında daha fazla Kurulum Yardımcısı ekranı atlayın<!-- 2687509  -->
Şu anda atlayabileceği ekranlarına ek olarak, iOS DEP cihazlarını, bir Kullanıcı cihazı kaydettiğinde Kurulum Yardımcısı 'ndaki aşağıdaki ekranları atlayacak şekilde ayarlayabilirsiniz: ekran tonu, gizlilik, Android geçişi, giriş düğmesi, IMessage & çok yönlü saat, ekleme, Izleme Geçiş, görünüm, ekran süresi, yazılım güncelleştirmesi, SIM kurulumu.
Atlanacak ekranları seçmek için, **cihaz kaydı** > **Apple kaydı** > **kayıt programı belirteçleri** > bir belirteç > **profilleri** seçin > bir profil > **Özellikler** > **Kurulum Yardımcı özelleştirme** > **Tamam**> atlamak Istediğiniz ekranlar için **Gizle** ' yi seçin.
Yeni bir profil oluşturursanız veya bir profili düzenlerseniz, seçili atlama ekranlarının Apple MDM sunucusuyla eşitlenmesi gerekir. Kullanıcılar, profil değişikliklerini çekerken bir gecikme olmaması için cihazların el ile eşitlenmesini verebilir.

#### <a name="android-enterprise-app-we-app-deployment---1171203---"></a>Android Enterprise APP-WE uygulaması dağıtımı<!-- 1171203 -->
Kayıt (APP-WE) dağıtım senaryosu olmayan kayıtlı olmayan bir uygulama koruma Ilkesinde Android cihazlarda, artık kullanıcılara Mağaza uygulamaları ve LOB uygulamaları dağıtmak için yönetilen Google Play kullanabilirsiniz. Özellikle, son kullanıcılara artık son kullanıcıların cihazların güvenlik duruşunu, bilinmeyen kaynaklardan yüklemelere izin vererek koruyabilmesine gerek duymayacak bir uygulama kataloğu ve yükleme deneyimi sağlayabilirsiniz. Ayrıca, bu dağıtım senaryosu gelişmiş bir son kullanıcı deneyimi sağlar.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="role-based-access-control"></a>Rol tabanlı erişim denetimi

#### <a name="scope-tags-for-apps---1081941---"></a>Uygulamalar için kapsam etiketleri<!-- 1081941 -->
Roller ve uygulamalar için erişimi sınırlandırmak üzere kapsam etiketleri oluşturabilirsiniz. Bir uygulamaya kapsam etiketi ekleyebilirsiniz, böylece bu kapsam etiketini yalnızca rollere sahip kişilerin uygulamaya erişimi vardır. Şu anda, yönetilen Google Play veya Apple Volume Purchase Program (VPP) kullanılarak satın alınan uygulamalardan Intune 'a eklenen uygulamalara kapsam etiketleri atanamaz (gelecekteki destek planlanmaktadır). Daha fazla bilgi için bkz. [ilkeleri filtrelemek için kapsam etiketlerini kullanma](scope-tags.md).




<!-- ########################## -->
## <a name="december-2018"></a>Aralık 2018

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="updates-for-application-transport-security---748318---"></a>Uygulama taşıma güvenliği için güncelleştirmeler<!-- 748318 -->

Microsoft Intune, Intune 'un varsayılan olarak daha güvenli olmasını sağlamak ve Microsoft Office 365 gibi diğer Microsoft hizmetleriyle hizalamak için, Aktarım Katmanı Güvenliği 'ni (TLS) 1.2 + 'yi destekler. Bu gereksinimi karşılamak için iOS ve macOS şirket portalları, Apple 'ın güncelleştirilmiş uygulama taşıma güvenliği (ATS) gereksinimlerini (Ayrıca, TLS 1.2 + gerektiren) zorlayacaktır. ATS, HTTPS üzerinden yapılan tüm uygulama iletişimlerinde daha sıkı güvenlik uygulamak için kullanılır. Bu değişiklik, iOS ve macOS Şirket Portalı uygulamalarını kullanarak Intune müşterilerini etkiler. Daha fazla bilgi için bkz. [Intune destek blogu](https://aka.ms/compportalats).

#### <a name="the-intune-app-sdk-will-support-256-bit-encryption-keys---1832174---"></a>Intune uygulama SDK 'Sı 256 bit şifreleme anahtarlarını destekleyecektir<!-- 1832174 -->
Android için Intune uygulama SDK 'Sı artık şifreleme uygulama koruma Ilkeleri tarafından etkinleştirildiğinde 256 bit şifreleme anahtarlarını kullanır. SDK, eski SDK sürümlerini kullanan içerik ve uygulamalarla uyumluluk için 128 bitlik anahtarlar desteği sağlamaya devam edecektir.

#### <a name="microsoft-auto-update-version-450-required-for-macos-devices---3503442---"></a>MacOS cihazları için Microsoft Auto Update sürüm 4.5.0 gereklidir<!-- 3503442 -->
Şirket Portalı ve diğer Office uygulamalarına yönelik güncelleştirmeleri almaya devam etmek için Intune tarafından yönetilen macOS cihazlarının Microsoft Auto Update 4.5.0 'e yükseltilmesi gerekir. Kullanıcılar Office uygulamaları için bu sürüme zaten sahip olabilir.

### <a name="device-management"></a>Cihaz yönetimi

#### <a name="intune-requires-macos-1012-or-later---2827778---"></a>Intune macOS 10,12 veya üstünü gerektirir<!-- 2827778 -->
Intune artık macOS sürüm 10,12 veya üstünü gerektiriyor. Önceki macOS sürümlerini kullanan cihazlar Intune 'a kaydolmak için Şirket Portalı kullanamaz. Destek yardımını ve yeni özellikleri almak için, kullanıcıların cihazlarını macOS 10,12 veya sonraki bir sürüme yükseltmeleri ve Şirket Portalı en son sürüme yükseltmesi gerekir.

<!-- ########################## -->
## <a name="november-2018"></a>2018 Kasım

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="uninstalling-apps-on-corporate-owned-supervised-ios-devices---1281677---"></a>Şirkete ait denetimli iOS cihazlarında uygulamaları kaldırma<!-- 1281677 -->
Şirkete ait denetimli iOS cihazlarında herhangi bir uygulamayı kaldırabilirsiniz. **Kaldırma** atama türüyle kullanıcı veya cihaz gruplarını hedefleyerek herhangi bir uygulamayı kaldırabilirsiniz. Kişisel veya denetimsiz iOS cihazlarında yalnızca Intune kullanarak yüklenen uygulamaları kaldırabilirsiniz.

#### <a name="downloading-intune-win32-app-content---2617320---"></a>Intune Win32 uygulama içeriği indiriliyor<!-- 2617320 -->
Windows 10 RS3 ve üzeri istemciler, Windows 10 istemcisinde teslim Iyileştirme bileşeni kullanarak Intune Win32 uygulama içeriğini indirir. Teslim iyileştirme, varsayılan olarak açık olan eşler arası işlevsellik sağlar. Dağıtım iyileştirmesi Şu anda Grup İlkesi tarafından yapılandırılabilir. Daha fazla bilgi için bkz. [Windows 10 Için teslim iyileştirmesi](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization).

#### <a name="end-user-device-and-app-content-menu---2771453---"></a>Son Kullanıcı cihaz ve uygulama içeriği menüsü<!-- 2771453 -->
Son kullanıcılar artık cihaz ve uygulamalar üzerinde bağlam menüsünü kullanarak bir cihazı yeniden adlandırma veya uyumluluğu denetleme gibi yaygın eylemleri tetikleyebilirler.

#### <a name="set-custom-background-in-managed-home-screen-app----3041945---"></a>Yönetilen giriş ekranı uygulamasında özel arka plan ayarla <!-- 3041945 -->
Android Enterprise, çok uygulama, bilgi noktası modundaki cihazlarda yönetilen giriş ekranı uygulamasının arka plan görünümünü özelleştirmenizi sağlayan bir ayar ekliyoruz.  **Özel URL arka planı**’nı yapılandırmak için Azure portalı > Cihaz yapılandırması’ndaki Intune’a gidin. Geçerli cihaz yapılandırma profilini seçin veya bilgi noktası ayarlarını yapılandırmak için yeni profil oluşturun.
Bilgi noktası ayarlarını görmek için bkz. [Android kurumsal cihaz kısıtlamaları](../configuration/device-restrictions-android-for-work.md).

#### <a name="app-protection-policy-assignment-save-and-apply---3104570---"></a>Uygulama koruma ilkesi ataması Kaydet ve Uygula<!-- 3104570 -->
Artık [Uygulama koruma ilkesi atamalarınız](../apps/app-protection-policies.md)üzerinde daha iyi denetime sahipsiniz. Bir ilkenin atamalarını ayarlamak veya düzenlemek için *atamalar* ' ı seçtiğinizde, değişikliğin geçerli olması Için yapılandırmanızı **kaydetmelisiniz** . Ekleme veya dışlama listelerinde değişiklik yapmadan yaptığınız tüm değişiklikleri temizlemek için **at** ' i kullanın.  Kaydetmeyi veya atmayı zorunlu kılarak yalnızca sizin istediğiniz kullanıcılara bir uygulama koruma ilkesi atanır.

#### <a name="new-microsoft-edge-browser-settings-for-windows-10-and-later---3174639---"></a>Windows 10 ve üzeri için yeni Microsoft Edge tarayıcı ayarları<!-- 3174639 -->
Bu güncelleştirme, cihazlarınızda Microsoft Edge tarayıcısını denetlemeye ve yönetmeye yardımcı olacak yeni ayarlar içerir. Bu ayarların listesi için bkz. [Windows 10 Için cihaz kısıtlaması (ve daha yeni)](../configuration/device-restrictions-windows-10.md#microsoft-edge-browser).

#### <a name="new-apps-support-with-app-protection-policies---3330037---"></a>Uygulama koruma ilkeleriyle yeni uygulama desteği<!-- 3330037 -->
Artık aşağıdaki uygulamaları [Intune uygulama koruma ilkeleriyle](../apps/app-protection-policies.md)yönetebilirsiniz:
- Stream (iOS)
- YAPıLACAKLAR (Android, iOS)
- PowerApps (Android, iOS)
- Flow (Android, iOS)

Şirket verilerini korumak ve Intune ilkesi tarafından yönetilen diğer uygulamalar gibi bu uygulamalar için veri aktarımını denetlemek için uygulama koruma ilkelerini kullanın. Not: akış henüz konsolda görünmüyorsa, uygulama koruma ilkeleri oluştururken veya düzenlerken akış eklersiniz. Bunu yapmak için **+ diğer uygulamalar** seçeneğini kullanın ve giriş alanında Flow IÇIN *uygulama kimliği* ' ni belirtin. Android için *com. Microsoft. Flow*ve iOS için *com. Microsoft. procsımo*kullanın.


### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="support-for-ios-12-oauth-in-ios-email-profiles--2155106---"></a>İOS için iOS e-posta profillerinde iOS 12 OAuth desteği<!--2155106 -->
Intune’un iOS e-posta profilleri, iOS 12 Open Authorization (OAuth) standardını destekliyor. Bu özelliği görmek için yeni bir profil oluşturun (platform olarak **Cihaz Yapılandırması** > **Profiller** > **Profil oluştur** > **iOS** > platform için > **E-posta** profil türü için) veya mevcut bir iOS e-posta profilini güncelleştirin. Kullanıcılara dağıtılmış olan bir profilde OAuth etkinleştirirseniz, kullanıcılardan tekrar kimlik doğrulaması yapmaları ve e-postalarını tekrar indirmeleri istenir.

[iOS e-posta profilleri](../configuration/email-settings-ios.md) makalesinde bir e-posta profilinde OAuth kullanma hakkında daha fazla bilgi vardır.

#### <a name="network-access-control-nac-support-for-citrix-sso-for-ios---3259404---"></a>İOS için Citrix SSO için ağ Access Control (NAC) desteği<!-- 3259404 -->
Citrix, Intune 'da iOS için Citrix SSO için ağ Access Control (NAC) izin vermek üzere Citrix Gateway 'e bir güncelleştirme yayımlamıştır. Intune 'da bir VPN profiline cihaz KIMLIĞI eklemek ve ardından bu profili iOS cihazlarınıza göndermek için kabul edebilirsiniz. Bu işlevselliği kullanmak için Citrix Gateway 'e en son güncelleştirmeyi yüklemeniz gerekir.

[İOS CIHAZLARıNDA VPN ayarlarını yapılandırma](../configuration/vpn-settings-ios.md#base-vpn-settings) bazı ek gereksinimler de dahil olmak üzere NAC kullanma hakkında daha fazla bilgi sağlar. 

#### <a name="ios-and-macos-version-numbers-and-build-numbers-are-shown---1892471---"></a>iOS ve macOS sürüm numaraları ve derleme numaraları gösterilir<!-- 1892471 -->
**Cihaz uyumluluğu** > **Cihaz uyumluluğu**’nda iOS ve macOS işletim sistemi sürümleri gösteriliyor ve uyumluluk ilkelerinde kullanılabilir durumda. Bu güncelleştirme, her iki platformda de yapılandırılabilir olan yapı numarasını içerir.
Güvenlik güncelleştirmeleri kullanıma sunulduğunda Apple genellikle sürüm numarasını olduğu gibi bırakır ancak derleme numarasını güncelleştirir. Bir uyumluluk ilkesinde derleme numarasını kullanarak güvenlik açığı güncelleştirmesinin yüklenip yüklenmediğini kolayca denetleyebilirsiniz.
Bu özelliği kullanmak için bkz. [iOS](../protect/compliance-policy-create-ios.md#device-health) ve [MacOS](../protect/compliance-policy-create-mac-os.md#device-properties) uyumluluk ilkeleri.

#### <a name="update-rings-are-being-replaced-with-delivery-optimization-settings-for-windows-10-and-later---2753807---"></a>Güncelleştirme halkaları Windows 10 ve üzeri için teslim Iyileştirme ayarları ile değiştiriliyor<!-- 2753807 -->
Teslim iyileştirme, Windows 10 ve üzeri için yeni bir yapılandırma profilidir. Bu özellik, kuruluşunuzdaki cihazlara yazılım güncelleştirmeleri sunmaya yönelik daha kolaylaştırılmış bir deneyim sunar. Bu güncelleştirme ayrıca bir yapılandırma profili kullanarak yeni ve mevcut güncelleştirme halkaları için ayarları teslim etmenize yardımcı olur.
Teslim iyileştirme yapılandırma profilini yapılandırmak için, bkz. [Windows 10 (ve daha yeni) teslim iyileştirme ayarları](../configuration/delivery-optimization-windows.md).

#### <a name="new-device-restriction-settings-added-to-ios-and-macos-devices---2827760---"></a>İOS ve macOS cihazlarına yeni cihaz kısıtlama ayarları eklendi<!-- 2827760 -->
Bu güncelleştirme iOS ve macOS cihazlarınız için iOS 12 ile yayınlanan yeni ayarları içerir:

**iOS ayarları**: 
- Genel: Uygulama kaldırmayı engelle (yalnızca denetimli)
- Genel: blok USB kısıtlı modu (yalnızca denetimli)
- Genel: otomatik tarih ve saati zorla (yalnızca denetimli)
- Parola: blok parola otomatik doldurma (yalnızca denetimli)
- Parola: parola yakınlık isteklerini engelle (yalnızca denetimli)
- Parola: parola paylaşımını engelle (yalnızca denetimli)

**MacOS ayarları**: 
- Parola: blok parola otomatik doldurma
- Parola: parola yakınlığı isteklerini engelle
- Parola: parola paylaşımını engelle

Bu ayarlar hakkında daha fazla bilgi edinmek için bkz. [iOS](../configuration/device-restrictions-ios.md) ve [MacOS](../configuration/device-restrictions-macos.md) cihaz kısıtlama ayarları.

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="autopilot-support-for-hybrid-azure-active-directory-joined-devices-preview---1048100--"></a>Karma Azure Active Directory katılmış cihazlar için Autopilot desteği (Önizleme)<!-- 1048100-->
Artık karma Azure Active Directory’ye katılmış olan cihazları Autopilot kullanarak ayarlayabilirsiniz. Hibrit Autopilot özelliğini kullanmak için cihazların kuruluşunuzun ağına katılmış olması gerekir. Daha fazla bilgi için bkz. [Karma Azure Active Directory’ye katılmış olan cihazları Intune ve Windows Autopilot kullanarak dağıtma](../enrollment/windows-autopilot-hybrid.md).
Bu özellik, gelecek birkaç gün içinde kullanıcı tabanının kullanımına sunulacaktır. Dolayısıyla bu özellik hesabınız için kullanılabilir olana kadar bu adımları uygulayamayabilirsiniz.

#### <a name="select-apps-tracked-on-the-enrollment-status-page---2531007---"></a>Kayıt durumu sayfasında izlenen uygulamaları seçin<!-- 2531007 -->
Kayıt durumu sayfasında hangi uygulamaların izleneceğini seçebilirsiniz. Bu uygulamalar yüklenene kadar, Kullanıcı cihazı kullanamaz. Daha fazla bilgi için bkz. [kayıt durumu sayfası ayarlama](../enrollment/windows-enrollment-status.md).

#### <a name="search-for-autopilot-device-by-serial-number--2595788---"></a>Autopilot cihazı seri numarasına göre ara<!--2595788 -->
Artık, Autopilot cihazlarını seri numarasına göre arayabilirsiniz. Bunu yapmak için, **cihaz kaydı** > **Windows kaydı** > **cihazları** ' nı seçin > **seri numarasına göre ara** kutusuna bir seri numarası yazın > Enter tuşuna basın.

#### <a name="track-installation-of-office-proplus--2620217---"></a>Office ProPlus yüklemesini izleyin<!--2620217 -->
Kullanıcılar, [kayıt durumu sayfasını](../enrollment/windows-enrollment-status.md)kullanarak, [Office ProPlus](../apps/apps-add-office365.md) 'ın yükleme ilerlemesini izleyebilir. Daha fazla bilgi için bkz. [kayıt durumu sayfası ayarlama](../enrollment/windows-enrollment-status.md).

#### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low---2237572---"></a>Süresi dolan VPP belirteci veya Şirket Portalı lisansı düşük çalışıyor uyarıları<!-- 2237572 -->
DEP kaydı sırasında Şirket Portalı önceden sağlamak için toplu satın alma programı 'nı (VPP) kullanıyorsanız, Intune, VPP belirtecinin sona ermek üzereyken ve Şirket Portalı lisansları düşük çalıştığında sizi uyarır.

#### <a name="macos-device-enrollment-program-support-for-apple-school-manager-accounts--3006133---"></a>macOS Aygıt Kayıt Programı Apple Okul Yöneticisi hesapları için destek<!--3006133 -->
Intune artık, Apple Okul Yöneticisi hesapları için macOS cihazlarında Aygıt Kayıt Programı kullanımını desteklemektedir.  Daha fazla bilgi için bkz. [macOS cihazlarını Apple Okul Yöneticisi veya aygıt kayıt programı Ile otomatik olarak kaydetme](../enrollment/device-enrollment-program-enroll-macos.md).

#### <a name="new-intune-device-subscription-sku--3312071--"></a>Yeni Intune cihaz aboneliği SKU 'SU<!--3312071-->
Kuruluşlarda cihaz yönetim maliyetini düşürmeye yardımcı olmak için yeni, cihaz tabanlı bir abonelik SKU’su kullanıma sunulmuştur. Bu Intune cihaz SKU’su cihaz başına aylık olarak lisanslandırılır. Fiyat ise lisanslama programına göre değişir. Doğrudan Microsoft 365 Yönetim Merkezi aracılığıyla ve [Kurumsal Anlaşma](https://www.microsoft.com/licensing/licensing-programs/enterprise?activetab=enterprise-tab:primaryr2) (EA), [Microsoft ürün ve hizmet sözleşmesi](https://www.microsoft.com/licensing/mpsa/default) (MPSA), [Microsoft açık anlaşmalar](https://partner.microsoft.com/licensing/licensing-agreements)ve [bulut çözümü sağlayıcısı](https://www.microsoftpartnercommunity.com/t5/Partnership-101/What-is-the-Cloud-Solution-Provider-CSP-program/td-p/2453) (CSP) aracılığıyla kullanılabilir .

### <a name="device-management"></a>Cihaz yönetimi

#### <a name="temporarily-pause-kiosk-mode-on-android-devices-to-make-changes---3041935---"></a>Değişiklik yapmak için Android cihazlarda bilgi noktası modunu geçici olarak duraklatma<!-- 3041935 -->
Android cihazlarını çok uygulamalı bilgi noktası modunda kullanırken bir BT uzmanının cihazda değişiklikler yapması gerekebilir. Bu güncelleştirme, bir BT yöneticisinin PIN kullanarak bilgi noktası modunu geçici olarak duraklatmasını ve tüm cihaza erişmesini sağlayan yeni çok uygulama bilgi noktası ayarları içerir.
Bilgi noktası ayarlarını görmek için bkz. [Android kurumsal cihaz kısıtlamaları](../configuration/device-restrictions-android-for-work.md).

#### <a name="enable-virtual-home-button-on-android-enterprise-kiosk-devices----3042021---"></a>Android kurumsal bilgi noktası cihazlarda sanal giriş düğmesini etkinleştirme <!-- 3042021 -->
Yeni bir ayar, kullanıcıların Yönetilen Giriş Ekranı uygulaması ve çok uygulamalı bilgi noktası cihazlarındaki diğer atanan uygulamalar arasında bir yazılım tuşuna dokunarak geçiş yapmalarını sağlar. Bu ayar, özellikle kullanıcının bilgi noktası uygulaması “geri” düğmesine uygun şekilde yanıt vermediği durumlarda yararlı olur. Bu ayarı şirkete ait, tek kullanımlı Android cihazlarında yapılandırabilirsiniz. **Sanal giriş düğmesi**’ni etkinleştirmek veya devre dışı bırakmak için Azure portalı > Cihaz yapılandırması’ndaki Intune’a gidin. Geçerli cihaz yapılandırma profilini seçin veya bilgi noktası ayarlarını yapılandırmak için yeni profil oluşturun.
Bilgi noktası ayarlarını görmek için bkz. [Android kurumsal cihaz kısıtlamaları](../configuration/device-restrictions-android-for-work.md).




<!-- ########################## -->
## <a name="october-2018"></a>2018 Ekim

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="access-to-key-profile-properties-using-the-company-portal-app---772203---"></a>Şirket Portalı uygulamasını kullanarak anahtar profili özelliklerine erişim<!-- 772203 -->
Son kullanıcılar artık parola sıfırlama gibi önemli hesap özellikleri ve eylemlerine Şirket portalı uygulamasından erişebilir. 

#### <a name="3rd-party-keyboards-can-be-blocked-by-app-settings-on-ios---1248481---"></a>üçüncü taraf klavyeler, iOS üzerindeki uygulama ayarları tarafından engellenebilir<!-- 1248481 -->
iOS cihazlarda Intune yöneticileri, ilke korumalı uygulamalarda kuruluş verilerine erişilirken üçüncü taraf klavyelerin kullanımını engelleyebilir. Uygulama Koruma İlkesi (APP) üçüncü taraf klavyelerini engelleyecek şekilde ayarlandığında, cihaz kullanıcısı üçüncü taraf klavyesini kullanarak şirket verileriyle ilk kez etkileşim kurarken bir ileti alır. Yerel klavye dışındaki tüm seçenekler engellenir ve cihaz kullanıcıları bunları görmez. Cihaz kullanıcıları iletişim kutusu iletisini tek bir kez görür. 

#### <a name="user-account-access-of-intune-apps-on-managed-android-and-ios-devices---1248496---"></a>Yönetilen Android ve iOS cihazlarda Intune uygulamalarına Kullanıcı hesabı erişimi<!-- 1248496 -->
Microsoft Intune yöneticisi olarak yönetilen cihazlarda hangi kullanıcı hesaplarının Microsoft Office uygulamalarına eklendiğini denetleyebilirsiniz. Erişimi yalnızca izin verilen kullanıcı hesaplarıyla sınırlayabilecek ve kayıtlı cihazlarda kişisel hesapları engelleyebilirsiniz. 

#### <a name="outlook-ios-and-android-app-configuration-policy--1828527---"></a>Outlook iOS ve Android uygulama yapılandırma ilkesi<!--1828527 -->
Artık iOS ve Android’de, ActiveSync protokolüyle Temel kimlik doğrulamasından yararlanan şirket içi kullanıcılar için bir Outlook iOS ve Android uygulama yapılandırma ilkesi oluşturabilirsiniz. Ek yapılandırma ayarları, iOS ve Android için Outlook’ta etkinleştirildikçe eklenecektir.

#### <a name="office-365-pro-plus-language-packs---1833450---"></a>Office 365 Pro Plus dil paketleri<!-- 1833450 -->
Intune yöneticisi olarak, Intune aracılığıyla yönetilen Office 365 Pro Plus uygulamaları için ek dillerin dağıtımını yapabileceksiniz. Kullanılabilir diller listesi, dil paketinin **Tür** bilgisini içerir (çekirdek, kısmı ve yazım denetleme). Azure portalında **Microsoft Intune** > **İstemci uygulamaları** > **Uygulamalar** > **Ekle**’yi seçin. **Uygulama ekle** dikey penceresindeki **Uygulama türü** listesinde **Office 365 Paketi** altından **Windows 10**'u seçin. **Uygulama Paketi Ayarları** dikey penceresinde **Diller**'i seçin.

#### <a name="windows-line-of-business-lob-apps-file-extensions---1884873---"></a>Windows iş kolu (LOB) uygulamaları dosya uzantıları<!-- 1884873 -->
Windows LOB uygulamalarına yönelik dosya uzantıları artık *. msi*, *. appx*, *. appxdemeti*, *. msix*ve *. msixdemeti*içerir. Microsoft Intune’da, **İstemci uygulamaları** > **Uygulamalar** > **Ekle**’yi seçerek bir uygulama ekleyebilirsiniz. **Bölme ekle** bölmesi görüntülenir ve **Uygulama türünü** seçmenize olanak tanır. Windows LOB uygulamaları için uygulama türü olarak **İş kolu uygulamasını** seçin, **Uygulama paketi dosyasını** seçin ve uygun uzantıya sahip bir yükleme dosyası girin.

#### <a name="windows-10-app-deployment-using-intune---2309001---"></a>Intune kullanarak Windows 10 uygulama dağıtımı<!-- 2309001 -->
Yöneticiler, iş kolu (LOB) uygulamaları ve İş için Microsoft Store uygulamaları için mevcut destekten yararlanarak kuruluşlarındaki uygulamaların çoğunu Intune ile Windows 10 cihazlarındaki son kullanıcılara dağıtabilir. Yöneticiler, Windows 10 kullanıcıları için MSI, Setup.exe veya MSP gibi çeşitli biçimlerdeki uygulamalar ekleyebilir, yükleyebilir ve kaldırabilir. Intune, indirme ve yükleme öncesinde gereksinim kurallarını değerlendirerek, işlemin durumunu veya yeniden başlatma gereğini Windows 10 Eylem Merkezi aracılığıyla son kullanıcılara bildirebilir. Bu işlevsellik, sonuçta, bu iş yükünü Intune'a ve buluta kaydırmak isteyen kuruluşların engellemesini kaldırmış olur. Bu özellik şu anda genel önizleme aşamasındadır ve önümüzdeki birkaç ay içinde özelliğe önemli yeni olanaklar eklemeyi bekliyoruz. 

#### <a name="app-protection-policy-app-settings-for-web-data---2662995---"></a>Web verileri için uygulama koruma Ilkesi (uygulama) ayarları<!-- 2662995 -->
Gerek Android gerekse iOS cihazlarında Web içeriği için uygulama ilke ayarları, gerek http gerekse https Web bağlantılarını, ayrıca iOS Evrensel Bağlantıları ve Android Uygulama Bağlantıları aracılığıyla veri aktarımını daha iyi işleyecek şekilde güncelleştirilecektir. 

#### <a name="end-user-device-and-app-content-menu---2771453---"></a>Son Kullanıcı cihaz ve uygulama içeriği menüsü<!-- 2771453 -->
Son kullanıcılar artık cihaz yeniden adlandırma veya uyumluluk denetleme gibi sık kullanılan eylemleri tetiklemek için cihazdaki açılır menüyü kullanabilir. 

#### <a name="windows-company-portal-keyboard-shortcuts---2771518---"></a>Windows Şirket Portalı klavye kısayolları<!-- 2771518 -->
Son kullanıcılar artık Windows Şirket Portalı’nda klavye kısayollarını (hızlandırıcılar) kullanarak uygulama ve cihaz eylemlerini tetikleyebilir.

#### <a name="require-non-biometric-pin-after-a-specified-timeout---1506985---"></a>Belirtilen zaman aşımından sonra biyometrik olmayan PIN gerektir<!-- 1506985 -->
Intune, yöneticinin belirttiği zaman aşımından sonra biyometrik olmayan bir PIN gerektirir, böylece şirket verilerine erişim için biyometrik tanımlama kullanımını kısıtlama yoluyla Mobil Uygulama Yönetimi’nin (MAM) etkinleştirildiği uygulamalarda gelişmiş güvenlik sağlar. Bu ayar, APP/MAM etkin uygulamalara erişmek için Touch ID (iOS), Face ID (iOS), Android Biometric, veya geleceğin diğer kimlik doğrulama yöntemlerinden yararlanan kullanıcıları etkiler. Bu ayarlar, birden çok parmak izine veya başka biyometrik erişim yöntemlerine sahip bir cihazın şirket verilerini yanlış kullanıcıya gösterebildiği durumları ortadan kaldırarak, Intune yöneticilerinin kullanıcı erişimi üzerinde daha ayrıntılı denetim sahibi olmasına olanak tanır. Azure portalında **Microsoft Intune**'u açın. **İstemci uygulamaları** > **Uygulama koruma ilkeleri** > **İlke ekle** > **Ayarlar**’ı seçin. Belirli ayarlar için **Erişim** bölümünü bulun. Erişim ayarları hakkında daha fazla bilgi için bkz. [iOS ayarları](../apps/app-protection-policy-settings-ios.md#access-requirements) ve [Android ayarları](../apps/app-protection-policy-settings-android.md#access-requirements).

#### <a name="intune-app-data-transfer-settings-on-ios-mdm-enrolled-devices---2244713---"></a>İOS MDM 'ye kayıtlı cihazlarda Intune uygulama veri aktarımı ayarları<!-- 2244713 -->
iOS MDM kayıtlı cihazlarda Intune APP veri aktarımı ayarlarının denetimini, kayıtlı kullanıcının kimliğini (Kullanıcı Asıl Adı (UPN) olarak da bilinir) belirtme işleminden ayrı tutabilirsiniz. IntuneMAMUPN kullanmayan yöneticiler, davranış değişikliği gözlemlemeyecektir. Bu işlev kullanılabilir olduğunda, kayıtlı cihazlarda veri aktarımı davranışını denetlemek için IntuneMAMUPN kullanan yöneticiler yeni ayarları gözden geçirmeli ve APP ayarlarını gerektiği gibi güncelleştirmelidir.

#### <a name="windows-10-win32-apps---2617325---"></a>Windows 10 Win32 uygulamaları<!-- 2617325 -->
Win32 uygulamalarınızı cihazdaki tüm kullanıcılar için yüklemek yerine kullanıcı bağlamında ayrı ayrı kullanıcılar için yüklenecek şekilde yapılandırabilirsiniz.

#### <a name="windows-win32-apps-and-powershell-scripts---2617330---"></a>Windows Win32 uygulamaları ve PowerShell betikleri<!-- 2617330 -->
Artık son kullanıcıların Win32 uygulamalarını yüklemek veya PowerShell betiklerini yürütmek için cihazda oturum açmış olmaları gerekmez. 

#### <a name="troubleshooting-client-app-installation---1363711---"></a>İstemci uygulaması yüklemesinde sorun giderme<!-- 1363711 -->
**Sorun giderme** dikey penceresinde **Uygulama yükleme** etiketli sütunu gözden geçirerek istemci uygulamaların yüklenmesiyle ilgili sorunları giderebilirsiniz. **Sorun giderme** dikey penceresini görüntülemek için Intune portalındaki **Yardım ve destek** bölümünün altından **Sorun giderme**’yi seçin.

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="create-dns-suffixes-in-vpn-configuration-profiles-on-devices-running-windows-10---1333668---"></a>Windows 10 çalıştıran cihazlarda VPN yapılandırma profillerinde DNS sonekleri oluşturma<!-- 1333668 -->
Bir VPN cihaz yapılandırma profili oluşturduğunuzda (**Cihaz yapılandırması** > **Profiller** > **Profil oluştur** > **Windows 10 ve üzeri** platform > **VPN** profil türü) bazı DNS ayarları girersiniz. Bu güncelleştirme ile Intune'da birden çok **DNS soneki** de girebilirsiniz. DNS son ekleri kullanırken bir ağ kaynağını tam etki alanı adı (FQDN) yerine kısa adını kullanarak arayabilirsiniz. Bu güncelleştirme ayrıca Intune’da DNS son eklerinin sırasını değiştirmenize de imkan verir.
[Windows 10 VPN ayarları](../configuration/vpn-settings-windows-10.md#dns-settings) makalesi, geçerli DNS ayarlarını listeler.
Şunlar için geçerlidir: Windows 10 cihazlar

#### <a name="support-for-always-on-vpn-for-android-enterprise-work-profiles---1333705---"></a>Android kurumsal iş profilleri için Always on VPN desteği<!-- 1333705 -->
Bu güncelleştirmede yönetilen iş profilleri olan Android kurumsal cihazlarda Her Zaman Açık VPN bağlantıları kullanabilirsiniz. Her zaman açık VPN bağlantıları; kullanıcı cihazının kilidini açtığında, cihaz yeniden başlatıldığında veya kablosuz ağ değiştiğinde bağlı kalır veya hemen tekrar bağlanır. Bağlantıyı “kilitli”moduna da alabilirsiniz, böylece VPN bağlantısı etkin olana kadar tüm ağ trafiği engellenir.
Her Zaman Açık VPN'yi platform için **Cihaz yapılandırması** > **Profiller** > **Profil oluşturma**  >  **Android kurumsal**'da > **Cihaz kısıtlamaları** > **Bağlantı** ayarlarında etkinleştirebilirsiniz.

#### <a name="issue-scep-certificates-to-user-less-devices---1744554---"></a>Kullanıcı-daha az cihazlara SCEP sertifikaları verme<!-- 1744554 -->
Şu anda sertifikalar kullanıcılara atanmaktadır. Bu güncelleştirme ile bilgi noktaları gibi kullanıcısız olanlar da dahil olmak üzere cihazlara SCEP sertifikaları çıkarılabilir (platform için **Cihaz yapılandırması** > **Profiller** > **Profil oluştur** > **Windows 10 ve üzeri** > profil için **SCEP sertifikası**). Diğer güncelleştirmeler:
- SCEP profilindeki **Konu** özelliği, artık özel bir metin kutusundadır ve yeni değişkenler içerebilir. 
- SCEP profilindeki **Konu diğer adı (SAN)** özelliği artık tablo biçimindedir ve yeni değişkenler içerebilir. Yöneticiler tabloda bir öznitelik ekleyebilir ve değeri özel bir metin kutusunda doldurabilir. SAN, aşağıdaki öznitelikleri destekleyecek: 
  - DNS
  - E-posta adresi
  - 'LE

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
> - `{{FullyQualifiedDomainName}}` yalnızca Windows ve etki alanına katılmış cihazlarda kullanılır. 
> - Bir cihaz sertifikası için konu veya SAN’da IMEI, Seri Numarası ve Tam Etki Alanı Adı gibi cihaz özellikleri belirtirken cihaza erişimi olan biri tarafından kandırma amaçlı olarak farklı özellikler verilebileceğine dikkat edin. 

[Bir SCEP sertifika profili oluşturma](../protect/certificates-profile-scep.md#create-a-scep-certificate-profile) makalesi, bir SCEP yapılandırma profili oluştururken geçerli değişkenleri listeler. 

Şunlar için geçerlidir: Windows 10 ve üzeri ve iOS, Wi-Fi desteklenir

#### <a name="remotely-lock-uncompliant-devices---2064495---"></a>Uyumlu olmayan cihazları uzaktan kilitleme<!-- 2064495 -->
Cihazın uyumlu olmadığı durumlarda, uyumluluk ilkesinde cihazı uzaktan kilitleyen bir eylem oluşturabilirsiniz. Intune > **Cihaz uyumluluğu**'nda yeni bir ilke oluşturun veya mevcut bir ilkeyi > **Özellikler**'i seçin. **Uyumsuzluğa yönelik eylemler** > **Ekle**’yi ve cihazı uzaktan kilitlemeyi seçin.
Şu platformlarda desteklenir: 
- Android
- iOS
- Mac OS
- Windows 10 Mobile 
- Windows Phone 8.1 ve üzeri 

#### <a name="windows-10-and-later-kiosk-profile-improvements-in-the-azure-portal---2748224---"></a>Azure portal Windows 10 ve üzeri bilgi noktası profili geliştirmeleri<!-- 2748224 -->
Bu güncelleştirmede Windows 10 Bilgi Noktası cihaz yapılandırma profilinde (platform için **Cihaz yapılandırması** > **Profiller** > **Profil oluştur** > **Windows 10 ve üzeri**, profil türü için > **Bilgi noktası önizlemesi**) yapılan aşağıdaki iyileştirmeler bulunur: 
- Şu anda aynı cihazda birden fazla bilgi noktası profili oluşturabiliyorsunuz. Bu güncelleştirme ile Intune, cihaz başına yalnızca bir bilgi noktası profilini destekleyecek. Tek bir cihazda birden fazla bilgi noktası profiline ihtiyacınız varsa bir Özel URI kullanabilirsiniz.
- **Çok uygulamalı bilgi noktası** profilinde, uygulama kılavuzundaki **Başlangıç menüsü düzeni** için uygulama kutucuğu boyutunu ve sırasını seçebilirsiniz. Daha fazla özelleştirme isterseniz bir XML dosyasını karşıya yükleyebilirsiniz.
- Bilgi Noktası Tarayıcısı ayarları, **Bilgi Noktası** ayarlarına taşınıyor. Şu anda **Bilgi Noktası web tarayıcısı** ayarlarının Azure portalında kendi kategorisi var.
Şunlar için geçerlidir: Windows 10 ve üzeri

#### <a name="pin-prompt-when-you-change-fingerprints-or-face-id-on-an-ios-device----2637704----"></a>Bir iOS cihazında parmak izlerini veya yüz KIMLIĞINI değiştirdiğinizde PIN istemi <!-- 2637704  -->
Artık, kullanıcılar iOS cihazlarında biyometrik değişiklikler yaptığında PIN istenir. Bunlara kayıtlı parmak izleri veya yüz kimliğinde yapılan değişiklikler dahildir. İstemin zamanlaması, *(dakika) içinde erişim gereksinimlerini yeniden denetle* zaman aşımının yapılandırmasına bağlıdır.  Ayarlanmamışsa kullanıcıdan bir PIN ayarlaması istenir. 
 
Bu özellik yalnızca iOS için kullanılabilir ve iOS için Intune APP SDK’sı sürüm 9.0.1 veya üzeri sürümleri tümleştiren uygulamaların katılımını gerektirir. Hedeflenen uygulamalarda davranışın zorlanabilmesi için SDK tümleştirmesi gereklidir. Bu tümleştirme, sıralı bir şekilde gerçekleşir ve belirli uygulama ekiplerine bağımlıdır. Katılan uygulamalardan bazıları WXP, Outlook, Managed Browser ve Yammer’dır.

#### <a name="network-access-control-support-on-ios-vpn-clients---1333693---"></a>İOS VPN istemcilerinde Ağ erişim denetimi desteği<!-- 1333693 -->
Bu güncelleştirmeyle, iOS için Cisco AnyConnect, F5 Access ve Citrix SSO’ya yönelik bir VPN yapılandırma profili oluştururken Ağ Erişim Denetimini (NAC) etkinleştirmek için kullanabileceğiniz yeni bir ayar kullanıma sunuldu. Bu ayar, cihazın NAC kimliğinin VPN profiline dahil edilmesini sağlar. Şu anda bu yeni NAC kimliğini destekleyen bir VPN istemcisi veya NAC iş ortağı çözümü yok, ancak olduğunda sizi [destek blog gönderimiz](ttps://aka.ms/iOS12_and_vpn) yoluyla bilgilendireceğiz.

NAC’yi kullanmak için şunları yapmanız gerekir:
1. Intune’un cihaz kimliklerini VPN profillerine dahil etmesini seçmek
2. Doğrudan NAC sağlayıcınız tarafından sağlanan yönergelere göre NAC sağlayıcı yazılımı/ürün yazılımınızı güncelleştirmek

Bu ayarın bir iOS VPN profilindeki kullanımı hakkında bilgi için bkz. [Microsoft Intune’da iOS cihazlara VPN ayarları ekleme](../configuration/vpn-settings-ios.md). Ağ erişim denetimi hakkında daha fazla bilgi için bkz. [Ağ erişim denetimini (NAC) Intune ile tümleştirme](../protect/network-access-control-integrate.md). 

Şunun için geçerlidir: iOS

#### <a name="remove-an-email-profile-from-a-device-even-when-theres-only-one-email-profile---1818139---"></a>Yalnızca bir e-posta profili olduğunda bile cihazdan e-posta profilini kaldırma<!-- 1818139 -->
Önceden, cihazda sadece bir e-posta profilinin *olması* durumunda bu e-posta profilini cihazdan kaldırmak mümkün değildi. Bu güncelleştirme ile bu davranış değişiyor. Artık cihazdaki tek e-posta profilini bile kaldırabilirsiniz. Ayrıntılar için bkz. [Intune kullanarak cihazlara e-posta ayarları ekleme](../configuration/email-settings-configure.md).

#### <a name="powershell-scripts-and-aad---2309469---"></a>PowerShell betikleri ve AAD<!-- 2309469 -->
Intune’da PowerShell betikleri AAD cihaz güvenlik grupları tarafından hedeflenebilir.

#### <a name="new-required-password-type-default-setting-for-android-android-enterprise---2649963---"></a>Android, Android Enterprise için yeni "gerekli parola türü" varsayılan ayarı<!-- 2649963 -->
Yeni bir uyumluluk ilkesi oluşturduğunuzda (**Intune** > **Cihaz uyumluluğu** > **İlkeler** > **İlke oluştur** > **Android** veya Platform > Sistem Güvenliği için **Android kurumsal**), **Gerekli parola türü** varsayılan değeri değişir:

Cihaz varsayılanı’ndan En az sayısal’a

Şunlar için geçerlidir: Android, Android Kurumsal

Bu ayarları görmek için [Android](../protect/compliance-policy-create-android.md) veya [Android Kurumsal](../protect/compliance-policy-create-android-for-work.md)’a gidin.

#### <a name="use-a-pre-shared-key-in-a-windows-10-wi-fi-profile---2662938---"></a>Windows 10 Wi-Fi profilinde önceden paylaşılan anahtar kullanma<!-- 2662938 -->
Bu güncelleştirmeyle birlikte Windows 10’da bir Wi-Fi yapılandırma profilinin kimliğini doğrulamak için WPA/WPA2 Kişisel güvenlik protokolü ile birlikte bir önceden paylaşılan anahtar (PSK) kullanabilirsiniz. Ayrıca 10 Ekim 2018 güncelleştirmesiyle Windows 10 cihazlarda bir tarifeli ağ için maliyet yapılandırmasını da belirtebilirsiniz.

Şu anda önceden paylaşılan anahtarları kullanmak için bir Wi-Fi profilini içeri aktarmanız veya özel bir profil oluşturmanız gerekiyor. [Windows 10 için Wi-Fi ayarları](../configuration/wi-fi-settings-windows.md) makalesi, geçerli ayarları listeler. 

#### <a name="remove-pkcs-and-scep-certificates-from-your-devices---3218390---"></a>Cihazlarınızdan PKCS ve SCEP sertifikalarını kaldırın<!-- 3218390 -->
Bazı senaryolarda, bir gruptan ilke kaldırılması, bir yapılandırma veya uyumluluk dağıtımının silinmesi veya mevcut SCEP veya PKCS profillerinin yönetici tarafından güncelleştirilmesi durumlarında bile PKCS ve SCEP sertifikaları cihazlarda kalıyordu. Bu güncelleştirme ile bu davranış değişiyor. PKCS ve SCEP sertifikalarının cihazda kaldığı veya bu sertifikaların cihazdan kaldırıldığı bazı senaryolar da vardır. Bu senaryolar için bkz. [Microsoft Intune’da SCEP ve PKCS sertifikalarını kaldırma](../protect/remove-certificates.md).

#### <a name="use-gatekeeper-on-macos-devices-for-compliance---2504381---"></a>Uyumluluk için macOS cihazlarda geçit kullanma<!-- 2504381 -->
Bu güncelleştirme, cihazları uyumluluk açısından değerlendirmek için macOS Gatekeeper özelliğini içerir. Gatekeeper özelliğini ayarlamak için bkz. [macOS cihazlara cihaz uyumluluk ilkesi ekleme](../protect/compliance-policy-create-mac-os.md).


### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="apply-autopilot-profile-to-enrolled-win-10-devices-not-already-registered-for-autopilot---1558983---"></a>Autopilot için kaydedilmemiş olan kayıtlı Win 10 cihazlarına Autopilot profili Uygula<!-- 1558983 -->
Kayıtlı olduğu halde Autopilot’a kayıtlı olmayan Win 10 cihazlara Autopilot profili uygulayabilirsiniz. Autopilot profilinde **Hedeflenen tüm cihazları Autopilot’a dönüştür** seçeneğini belirterek Autopilot olmayan cihazları Autopilot dağıtım hizmetine otomatik olarak kaydedin. Kaydın işlenmesi için 48 saat kadar bekleyin. Cihazın kaydı kaldırıldığında ve cihaz sıfırlandığında Autopilot, cihazı sağlar.

#### <a name="create-and-assign-multiple-enrollment-status--page-profiles-to-azure-ad-groups---2526564---"></a>Birden çok kayıt durumu sayfası profilini Azure AD gruplarına oluşturma ve atama<!-- 2526564 -->
Artık Azure ADD grupları için birden fazla Kayıt Durumu Sayfası profili [oluşturup atayabilirsiniz](../enrollment/windows-enrollment-status.md).

#### <a name="migration-from-device-enrollment-program-to-apple-business-manager-in-intune--2748613--"></a>Aygıt Kayıt Programı Intune 'da Apple Business Manager 'a geçiş<!--2748613-->
Apple Business Manager (ABM), Intune’da çalışır ve hesabınızı Aygıt Kayıt Programı’ndan (DEP) ABM’ye yükseltebilirsiniz. Intune’da bu işlem aynıdır. Apple hesabınızı DEP 'den ABD 'ye yükseltmek için [https://support.apple.com/HT208817]( https://support.apple.com/HT208817)' e gidin.

#### <a name="alert-and-enrollment-status-tabs-on-the-device-enrollment-overview-page--2748656--"></a>Cihaz kaydına Genel Bakış sayfasında uyarı ve kayıt durumu sekmeleri<!--2748656-->
Uyarılar ve kayıt hataları artık Cihaz kaydı genel bakış sayfasında ayrı sekmelerde görüntülenir.

#### <a name="enrollment-abandonment-report---1382924---"></a>Kayıt bırakma raporu<!-- 1382924 -->
Bırakılmış kayıtların ayrıntılarını sağlayan yeni bir rapor, **Cihaz kaydı** > **İzle** altında bulunabilir. Daha fazla bilgi için bkz. [Şirket portalı bırakma raporu](../enrollment/enrollment-report-company-portal-abandon.md).

#### <a name="new-azure-active-directory-terms-of-use-feature---2870393---"></a>Yeni Azure Active Directory kullanım koşulları özelliği<!-- 2870393 -->
Azure Active Directory’de mevcut Intune hüküm ve koşulları yerine kullanabileceğiniz bir kullanım koşulları özelliği vardır. Azure AD kullanım koşulları özelliği, hangi koşulların ne zaman gösterileceği konusunda daha fazla esneklik, daha iyi yerelleştirme desteği, koşulların ekrana çizilmesi üzerinde daha fazla denetim ve daha iyi raporlama sağlamaktadır. Azure AD kullanım koşulları özelliği, Enterprise Mobility + Security E3 paketinin de parçası olan Azure Active Directory Premium P1'i gerektirir. Daha fazla bilgi edinmek için bkz. [Kullanıcı erişimi için şirketinizin hüküm ve koşullarını yönetme makalesi](../enrollment/terms-and-conditions-create.md).

#### <a name="android-device-owner-mode-support--3188762--"></a>Android cihaz sahibi modu desteği<!--3188762-->
Samsung Knox Mobil Kaydı için Intune artık cihazları Android Cihaz Sahibi yönetim modunda kaydetmeyi destekliyor. WiFi veya hücresel ağ kullanan kullanıcılar, cihazlarını ilk kez açtıklarında yalnızca birkaç dokunuşla kayıt yapabilir. Daha fazla bilgi için bkz. [Android cihazları Samsung’un Knox Mobil Kayıt özelliğini kullanarak otomatik kaydetme](../enrollment/android-samsung-knox-mobile-enroll.md).

### <a name="device-management"></a>Cihaz yönetimi
#### <a name="new-settings-for-software-updates-----1907869---"></a>Yazılım güncelleştirmeleri için yeni ayarlar  <!-- 1907869 -->  
- Artık son kullanıcılara uyarı veren bazı bildirimleri, en son yazılım güncelleştirmelerini yüklemeyi bitirmek için gereken yeniden başlatmalar hakkında daha fazla bilgi yapılandırabilirsiniz.   
- Artık, KCG senaryolarını destekleyen iş saatleri dışında gerçekleşen yeniden başlatmalar için yeniden başlatma uyarı istemi yapılandırabilirsiniz.

#### <a name="group-windows-autopilot-enrolled-devices-by-correlator-id---2075110---"></a>Windows Autopilot-kayıtlı cihazlarını ilişkilendirici KIMLIĞINE göre Gruplandır<!-- 2075110 -->
Intune, Configuration Manager aracılığıyla [mevcut cihazlar için Autopilot](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/New-Windows-Autopilot-capabilities-and-expanded-partner-support/ba-p/260430) kullanılarak kaydedilmiş Windows cihazları ilişkilendirici kimliğine göre gruplamayı artık destekliyor. İlişkilendirici kimliği, Autopilot yapılandırma dosyasının bir parametresidir. Intune, [Azure Active Directory cihaz özniteliği enrollmentProfileName](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#rules-for-devices) değerini “OfflineAutopilotprofile-<correlator ID>” değerine eşit olacak şekilde otomatik olarak ayarlar. Bu, çevrimdışı Autopilot kayıtları için enrollmentprofileName özniteliği aracılığıyla ilişkilendirici kimliğine göre rasgele Azure AD dinamik grupları oluşturulmasına izin verir. Daha fazla bilgi için bkz. [Mevcut cihazlar için Windows Autopilot](../enrollment/enrollment-autopilot.md#windows-autopilot-for-existing-devices).

#### <a name="intune-app-protection-policies---2984657---"></a>Intune uygulama koruma ilkeleri<!-- 2984657 -->
Intune uygulama koruma ilkeleri, Microsoft Outlook ve Microsoft Word gibi Intune tarafından korunan uygulamalar için çeşitli veri koruma ayarlarını yapılandırmanıza olanak sağlar. Ayrı ayrı ayarların bulunmasını kolaylaştırmak için hem [iOS](../apps/app-protection-policy-settings-ios.md) hem de [Android](../apps/app-protection-policy-settings-android.md) üzerinde bu ayarların görünümünde ve işlevinde değişiklik yaptık. İlke ayarları üç kategoriye ayrılır:
- **Verileri yeniden konumlandırma** - Bu grup kesme, kopyalama, yapıştırma ve farklı kaydetme kısıtlamaları gibi veri kaybı önleme (DLP) denetimlerini içerir. Bu ayarlar, kullanıcıların uygulamalarda verilerle nasıl etkileşim kurduğunu belirler.
- **Erişim gereksinimleri** - Bu grup, son kullanıcının uygulamalara iş bağlamında nasıl eriştiğini belirleyen uygulama başına PIN seçenekleri içerir.  
- **Koşullu başlatma** - Bu grup; en düşük işletim sistemi ayarları, jailbreak uygulanmış ve kök erişim izni verilmiş cihazları algılama ve çevrimdışı yetkisiz kullanım süreleri gibi ayarları içerir.  
  
Ayarların işlevselliği değişmedi, ancak ilke yazma akışında çalışırken bu ayarları bulmanız artık daha kolay.

#### <a name="restricts-apps-and-block-access-to-company-resources-on-android-devices---2451462----"></a>Android cihazlarda uygulamaları kısıtlar ve şirket kaynaklarına erişimi engelleyin<!-- 2451462  -->  
**Cihaz uyumluluğu** > **İlkeler** > **İlke oluştur** > **Android** > **Sistem Güvenliği**'nde *Cihaz Güvenliği* bölümünde **Kısıtlı uygulamalar** adlı yeni bir ayar vardır. **Kısıtlı uygulamalar** ayarı, üzerinde belirli uygulamalar yüklü olduğunda cihazın şirket kaynaklarına erişimini engelleyecek bir uyumluluk ilkesi kullanır. Cihaz, kısıtlı uygulamalar kaldırılana kadar uyumsuz sayılır.
Uygulama hedefi: 
- Android

### <a name="intune-apps"></a>Intune uygulamaları

#### <a name="intune-will-support-a-maximum-package-size-of-8-gb-for-lob-apps---1727158---"></a>Intune, LOB uygulamaları için en fazla 8 GB paket boyutunu destekleyecektir<!-- 1727158 -->
Intune, İş kolu (LOB) uygulamaları için izin verilen en fazla paket boyutunu 8 GB’a yükseltti. Daha fazla bilgi için bkz. [Microsoft Intune’a uygulama ekleme](../apps/apps-add.md).

#### <a name="add-custom-brand-image-for-company-portal-app---1916266---"></a>Şirket Portalı uygulaması için özel marka görüntüsü ekleme<!-- 1916266 -->
Microsoft Intune yöneticisi olarak, iOS Şirket Portalı uygulamasındaki kullanıcı profil sayfasında bir arka plan görüntüsü olarak kullanılacak özel bir marka görüntüsünü karşıya yükleyebilirsiniz. Şirket Portalı uygulamasını yapılandırma hakkında daha fazla bilgi için bkz. [Microsoft Intune Şirket Portalı uygulamasını yapılandırma](../apps/company-portal-app.md).

#### <a name="intune-will-maintain-the-office-localized-language-when-updating-office-on-end-users-machines---2971030---"></a>Intune, son kullanıcılar makinelerinde Office 'i güncelleştirirken Office yerelleştirilmiş dilini koruyacaktır<!-- 2971030 -->
Intune son kullanıcı makinenize Office yüklediğinde, son kullanıcılar önceki .MSI Office yüklemeleri ile aldıkları aynı dil paketini otomatik olarak alır. Daha fazla bilgi için bkz. [Microsoft Intune ile Office 365 uygulamalarını Windows 10 cihazlara atama](../apps/apps-add-office365.md).

### <a name="monitor-and-troubleshoot"></a>İzleme ve sorun giderme

#### <a name="new-intune-support-experience-in-the-microsoft-365-device-management-portal---3076965---"></a>Microsoft 365 cihaz yönetimi portalında yeni Intune destek deneyimi<!-- 3076965 -->
[Microsoft 365 Cihaz Yönetim portalında]( https://devicemanagement.microsoft.com) Intune için yeni bir Yardım ve Destek deneyimini kullanıma sunuyoruz. Yeni deneyim, sorununuzu kendi kelimelerinizle açıklamanıza ve sorun giderme içgörüleri ile Web tabanlı düzeltme içeriği almanıza olanak tanır. Bu çözümler, kullanıcı sorgularıyla şekillenen bir kural tabanlı makine öğrenimi algoritması aracılığıyla sunulur.  

Soruna özgü yönergelere ek olarak yeni olay oluşturma iş akışını kullanarak e-posta veya telefon yoluyla bir destek olayı açabilirsiniz.  

Dağıtıma dahil edilen müşteriler için bu yeni deneyim, Yardım ve Desteği açtığınızda bulunduğunuz konsol alanına dayalı, statik bir önceden belirlenmiş seçenekler kümesine yönelik geçerli Yardım ve Destek deneyiminin yerini alır.  

*Bu yeni yardım ve destek deneyimi, tüm kiracılara değil, ancak cihaz yönetim portalında kullanılabilir. Bu yeni deneyim için katılımcılar, kullanılabilir Intune kiracılarından rastgele seçilir. Dağıtımı genişlettiğimiz için yeni kiracılar eklenecektir.*  

Daha fazla bilgi için bkz. destek alma konusunda [Yardım ve destek deneyimi](get-support.md#help-and-support-experience) Microsoft Intune.  

#### <a name="powershell-module-for-intune--preview-available---951068---"></a>Intune için PowerShell modülü – önizleme kullanılabilir<!-- 951068 -->
Intune API’si için Microsoft Graph yoluyla destek sağlayan yeni bir PowerShell modülü artık [GitHub](https://aka.ms/intunepowershell)’da önizleme olarak kullanılabilir. Bu modülü kullanma hakkında daha fazla ayrıntı için modülün bulunduğu konumdaki README dosyasına bakın.

<!-- ########################## -->
## <a name="september-2018"></a>Eylül 2018

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="remove-duplication-of-app-protection-status-tiles---3083391---"></a>Yinelenen uygulama koruması durum kutucuklarını kaldırma<!-- 3083391 -->
**iOS için kullanıcı durumu** ve **Android için kullanıcı durumu** kutucuklarının ikisi de **İstemci Uygulamalar - Genel Bakış** sayfasında ve **İstemci Uygulamalar - Uygulama koruma durumu** sayfasında vardı. Durum kutucukları, yineleme olmaması için **İstemci Uygulamalar - Genel Bakış** sayfasından kaldırılmıştır. 

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="support-for-more-third-party-certification-authorities-ca---3093107---"></a>Daha çok sayıda sertifika yetkilisine (CA) destek<!-- 3093107 -->
Basit Sertifika Kayıt Protokolü'nü (SCEP) kullanarak artık Windows, iOS, Android ve macOS kullanan mobil cihazlarda yeni sertifika verebilir ve mevcut sertifikaları yenileyebilirsiniz.

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="intune-moves-to-support-ios-10-and-later---2454656---"></a>Intune, iOS 10 ve üzeri sürümleri desteklemeye geçiyor<!-- 2454656 -->  
Intune kaydı, Şirket Portalı ve yönetilen tarayıcı artık yalnızca iOS 10 ve üzerini çalıştıran iOS cihazları desteklemektedir. Kuruluşunuzda bundan etkilenen cihaz veya kullanıcıları denetlemek için Azure portalında Intune > **Cihazlar** > **Tüm cihazlar**'a gidin. İşletim sistemine göre filtreleyin, sonra işletim sistemi sürümü ayrıntılarının çıkması için **Sütunlar**'a tıklayın. Bu kullanıcılardan cihazlarını desteklenen bir işletim sistemi sürümüne yükseltmelerini isteyin.  

Aşağıda listelenen cihazlardan birine sahipseniz veya bunlardan birini kaydetmek istiyorsanız, bunların yalnızca iOS 9 ve öncesini desteklediğini bilmelisiniz.  Intune Şirket Portalı'na erişmeye devam etmek için bu cihazları iOS 10 ve üzerini destekleyen cihazlara yükseltmeniz gerekir:  

* iPhone 4S 
* iPod Touch  
* iPad 2 
* iPad (3. Nesil) 
* iPad Mini (1. Nesil)  

### <a name="device-management"></a>Cihaz yönetimi

#### <a name="microsoft-365-device-management-administration-center---3078424---"></a>Microsoft 365 Cihaz Yönetimi yönetim merkezi<!-- 3078424 -->
Microsoft 365 ilden biri basitleştirilmiştir ve arka uç Microsoft 365 hizmetlerini Intune ve Azure AD koşullu erişim gibi uçtan uca senaryolar sunacak şekilde tümleştirdik. Yönetim deneyimini birleştirmenin, basitleştirmenin ve tümleştirmenin yeri yeni [Microsoft 365 yönetim merkezidir](https://devicemanagement.microsoft.com). Cihaz Yönetimi için uzman çalışma alanı, kuruluşunuz için gereken tüm cihaz ve uygulama yönetim bilgi ve görevlerine kolay erişim sağlar. Buranın kurumsal son kullanıcı bilgi işlem ekipleri için birinci bulut çalışma alanı haline gelmesini bekliyoruz.


<!-- ########################## -->
## <a name="august-2018"></a>Ağustos 2018

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="packet-tunnel-support-for-ios-per-app-vpn-profiles-for-custom-and-pulse-secure-connection-types---1520957---"></a>Özel ve Pulse Secure bağlantı türleri için iOS uygulama başına VPN profilleri için paket tüneli desteği<!-- 1520957 -->
iOS uygulama başına VPN profillerini kullanırken uygulama katman tüneli (uygulama-proxy) veya paket düzeyi tünel (paket-tünel) kullanabilirsiniz. Bu seçenekler, aşağıdaki bağlantı türleri ile kullanılabilir:
- Özel VPN
- Pulse Secure Hangi değeri kullanmanız gerektiğini bilmiyorsanız VPN sağlayıcınızın belgelerine başvurun.

#### <a name="delay-when-ios-software-updates-are-shown-on-the-device---1949583---"></a>Cihazda iOS yazılım güncelleştirmelerinin gösterilmesini geciktirme<!-- 1949583 -->
Intune > **Yazılım Güncelleştirmeleri** > **iOS güncelleştirme ilkeleri**’nde cihazların güncelleştirme yüklemesini istemediğiniz gün ve saatleri yapılandırabilirsiniz. Gelecek bir güncelleştirme ile bir yazılım güncelleştirmesinin cihazda görüntülenmesini 1-90 gün kadar geciktirebileceksiniz. 
[Microsoft Intune’da iOS güncelleştirme ilkelerini yapılandırma](../protect/software-updates-ios.md) makalesi, geçerli ayarları listeler.

#### <a name="office-365-proplus-version---2213968---"></a>Office 365 ProPlus sürümü<!-- 2213968 -->
Intune kullanarak Office 365 ProPlus uygulamalarını Windows 10 cihazlara atarken Office sürümünü seçebilirsiniz. Azure portalında **Microsoft Intune** > **Uygulamalar** > **Uygulama ekle**’yi seçin. Daha sonra açılan **Tür** listesinden **Office 365 ProPlus Paketi (Windows 10)** ’u seçin. İlişkili dikey pencereyi görüntülemek için **Uygulama Paketi Ayarları**’nı seçin. **Güncelleştirme Kanalı** için bir değer ayarlayın, örneğin **Aylık**. İsteğe bağlı olarak **Evet**’i seçin ve son kullanıcı cihazlarından diğer Office (msi) sürümünü kaldırın. Son kullanıcı cihazlarında seçili kanal için belirli bir Office sürümü yüklemek için **Belirli**’yi seçin. Bu noktada Office’in **Belirli bir sürüm**ünü seçip kullanabilirsiniz. Kullanılabilir sürümler zaman içerisinde değişir. Bu neden yeni bir dağıtım oluştururken kullanılabilir sürümler daha yeni olabilir ve bazı eski sürümleri bulamayabilirsiniz. Mevcut dağıtımlar eski sürümü dağıtmaya devam eder ancak her kanaldaki sürüm listesi sürekli olarak güncelleştirilir. Daha fazla bilgi için bkz. [Office 365 ProPlus güncelleştirme kanallarına genel bakış](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus).

#### <a name="support-for-register-dns-setting-for-windows-10-vpn---2282852---"></a>Windows 10 VPN için DNS ayarı kaydetme desteği<!-- 2282852 -->
Bu güncelleştirme ile Windows 10 VPN profillerini, VPN arabirimine atanmış IP adreslerini özel profil kullanmaya ihtiyaç duymadan dinamik olarak dahili DNS’e kaydedecek şekilde yapılandırabilirsiniz.
Kullanabileceğiniz geçerli VPN profil ayarları hakkında bilgi için bkz. [Windows 10 VPN ayarları](../configuration/vpn-settings-windows-10.md).

#### <a name="the-macos-company-portal-installer-now-includes-the-version-number-in-the-installer-file-name--2652728--"></a>macOS Şirket Portalı yükleyicisi artık sürüm numarası ve yükleyici dosya adını içeriyor<!--2652728-->

#### <a name="ios-automatic-app-updates---2729759---"></a>iOS otomatik uygulama güncelleştirmeleri<!-- 2729759 -->
Otomatik uygulama güncelleştirmeleri, iOS sürüm 11.0 ve üzerinde cihaz ve kullanıcı lisanslı uygulamalar için kullanılabilir.

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="windows-hello-will-target-users-and-devices---1106609---"></a>Windows Hello, kullanıcıları ve cihazları hedefleyecek<!-- 1106609 -->
Bir [İş İçin Windows Hello](../protect/windows-hello.md) ilkesi oluşturduğunuzda bu ilke, kuruluştaki tüm kullanıcılara (kiracı genelinde) uygulanır. Bu güncelleştirmeyle ilke, bir cihaz yapılandırma ilkesi kullanılarak belirli kullanıcılara veya belirli cihazlara da (**Cihaz Yapılandırması** > **Profiller** > **Profil oluştur** > **Kimlik Koruma** > **İş İçin Windows Hello**) uygulanabilecek.
Azure portalında Intune’da Windows Hello yapılandırması ve ayarları artık hem **Cihaz kaydı** hem de **Cihaz yapılandırması** bölümlerinde bulunuyor. **Cihaz kaydı**, kuruluşun tamamını (kiracı genelinde) hedefler ve Windows AutoPilot (OOBE) destekler. **Cihaz yapılandırması**, iade sırasında uygulanan bir ilkeyi kullanarak cihazları ve kullanıcıları hedefler.
Bu özellik şu platformlarda geçerlidir:  
- Windows 10 ve üzeri
- Windows 10 Holographic for Business

#### <a name="zscaler-is-an-available-connection-for-vpn-profiles-on-ios---1769858---"></a>iOS’ta VPN profilleri için Zscaler bağlantısı kullanılabilir<!-- 1769858 -->
Bir iOS VPN cihaz yapılandırma profili oluşturduğunuzda (**Cihaz yapılandırması** > **Profiller** > **Profil oluştur** > **iOS** platform > **VPN** profil türü) Cisco, Citrix vb. gibi birkaç bağlantı türü vardır. Bu güncelleştirme ile Zscaler da bir bağlantı türü olarak eklendi. 
[iOS çalıştıran cihazlar için VPN ayarları](../configuration/vpn-settings-ios.md), kullanılabilir bağlantı türlerini listeler.

#### <a name="fips-mode-for-enterprise-wi-fi-profiles-for-windows-10---1879077---"></a>Windows 10 için Kurumsal Wi-Fi profilleri için FIPS modu<!-- 1879077 -->
Intune Azure portalında Windows 10 için Kurumsal Wi-Fi profilleri için artık Federal Bilgi İşleme Standardı (FIPS) modunu etkinleştirebilirsiniz. FIPS modunu Wi-Fi profillerinizde etkinleştirirseniz Wi-Fi altyapınızda etkinleştirmeyi de unutmayın.
[Intune’da Windows 10 ve üzeri cihazlar için Wi-Fi ayarları](../configuration/wi-fi-settings-windows.md) makalesi, bir Wi-Fi profilini nasıl oluşturacağınızı gösterir.

#### <a name="control-s-mode-on-windows-10-and-later-devices---public-preview---1958649---"></a>Windows 10 ve üzeri cihazlarda S modunu denetleme - genel önizleme<!-- 1958649 -->
Bu özellik güncelleştirmesi ile Windows 10 cihazı S modundan çıkaran veya kullanıcıların cihazı S modundan çıkarmasını önleyen bir cihaz yapılandırma profili oluşturabilirsiniz. Bu özellik Intune’da **Cihaz yapılandırması** > **Profiller** >  **Windows 10 ve üzeri** > **Sürüm yükseltme ve mod değiştirme** altındadır.
[S modunda Windows 10’a giriş](https://www.microsoft.com/windows/s-mode) makalesi, S modu hakkında daha fazla bilgi sağlar.
Şunlar için geçerlidir: En son [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) derlemesi (önizlemedeyken).

#### <a name="windows-defender-atp-configuration-package-automatically-added-to-configuration-profile---2144658---"></a>Windows Defender ATP yapılandırma paketi, otomatik olarak yapılandırma profiline eklenir<!-- 2144658 -->
Eskiden Intune’da [Gelişmiş Tehdit Koruması ve ekleme](../protect/advanced-threat-protection.md#onboard-devices-by-using-a-configuration-profile) cihazları kullanırken bir yapılandırma paketini indirip bunu yapılandırma profilinize ekliyordunuz. Bu güncelleştirme ile Intune, paketi otomatik olarak Windows Defender Güvenlik Merkezi’nden alır ve profilinize ekler.
Windows 10 ve üzeri için geçerlidir.

#### <a name="require-users-to-connect-during-device-setup--2311457--"></a>Cihaz kurulumu sırasında kullanıcıların bağlanmasını gerektirme<!--2311457-->
Artık Windows 10 kurulumu sırasında Ağ sayfasından ileri gitmeden önce cihazın bir ağa bağlanmasını gerektirecek cihaz profilleri ayarlayabilirsiniz. Bu özellik önizlemedeyken bu ayarı kullanmak için Windows Insider derleme 1809 veya sonrası gerekir.
Şunlar için geçerlidir: En son [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) derlemesi (önizlemedeyken).

#### <a name="restricts-apps-and-block-access-to-company-resources-on-ios-and-android-enterprise-devices---2451462---"></a>iOS ve Android Kurumsal cihazlarında uygulamaları kısıtlama ve şirket kaynaklarına erişimi engelleme<!-- 2451462 -->
**Cihaz uyumluluğu** > **İlkeler** > **İlke oluştur** > **iOS** > **Sistem Güvenliği**’nde yeni **Kısıtlı uygulamalar** ayarı var. Bu yeni ayar, bazı uygulamalar cihaza yüklendiğinde cihazın şirket kaynaklarına erişimini engelleyecek bir uyumluluk ilkesi kullanır. Cihaz, kısıtlı uygulamalar kaldırılana kadar uyumsuz sayılır.
Şunun için geçerlidir: iOS

#### <a name="modern-vpn-support-updates-for-ios---2459928-1819876-and-2650856---"></a>iOS için modern VPN destek güncelleştirmeleri<!-- 2459928, 1819876, and 2650856 -->
Bu güncelleştirme, aşağıdaki iOS VPN istemcileri için destek ekliyor:
- F5 Erişimi (sürüm 3.0.1 ve üzeri)
- Citrix SSO
- Palo Alto Networks GlobalProtect sürüm 5.0 ve üzeri Bu güncelleştirmede ayrıca:
- iOS için mevcut**F5 Access** bağlantı türü, **F5 Access Eski** olarak yeniden adlandırıldı.
- iOS için mevcut**Palo Alto Networks GlobalProtect** bağlantı türü, **Palo Alto Networks GlobalProtect (eski)** olarak yeniden adlandırıldı.
Bu bağlantı türlerine sahip mevcut profiller, eski VPN istemcileriyle çalışmaya devam edecek. iOS ile Cisco Eski AnyConnect, F5 Access Eski, Citrix VPN veya Palo Alto Networks GlobalProtect sürüm 4.1 ve öncesi kullanıyorsanız yeni uygulamalara geçmelisiniz. iOS 12 sonrası iOS cihazlarda VPN erişiminin kullanılabilir olmasını sağlamak için bunu en kısa zamanda yapmalısınız.
iOS 12 ve VPN profilleri hakkında daha fazla bilgi için bkz. [Microsoft Intune Destek Ekibi Blogu](https://go.microsoft.com/fwlink/?linkid=2013806).

#### <a name="export-azure-classic-portal-compliance-policies-to-recreate-these-policies-in-the-intune-azure-portal---2469637---"></a>Klasik Azure portalı uyumluluk ilkelerini dışarı aktararak bunları Intune Azure portalında yeniden oluşturma<!-- 2469637 -->
Azure klasik portalında oluşturulan ilkeler artık kullanım dışı olacak. Mevcut uyumluluk ilkelerini gözden geçirebilir ve silebilirsiniz ancak güncelleştiremezsiniz. Bazı mevcut uyumluluk ilkelerini geçerli Intune Azure portalına geçirmek istiyorsanız bunları virgülle ayrılmış bir dosyayla ( *.csv* dosyası) dışarı aktarabilirsiniz. Daha sonra Intune Azure portalında bu ilkeleri yeniden oluşturmak için dosyadaki ayrıntıları kullanabilirsiniz.

> [!IMPORTANT]
> Azure klasik portalı kullanımdan kalktıktan sonra uyumluluk ilkelerinize erişme veya bunları görüntüleme şansınız olmayacak. Bu sebeple Azure klasik portalı kullanımdan kaldırılmadan önce ilkelerinizi dışarı aktarıp Azure portalında yeniden oluşturduğunuzdan emin olun.

#### <a name="better-mobile---new-mobile-threat-defense-partner---22662717---"></a>Better Mobile - Yeni Mobil Tehdit Savunması iş ortağı<!-- 22662717 -->
Microsoft Intune ile tümleştirilen bir mobil tehdit savunması çözümü olan daha Iyi mobil tarafından gerçekleştirilen risk değerlendirmesine dayalı koşullu erişimi kullanarak mobil cihaz erişimini kontrol edebilirsiniz.

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="lock-the-company-portal-in-single-app-mode-until-user-sign-in--1067692---"></a>Kullanıcı oturum açana kadar Şirket Portalı’nı tek uygulama modunda kilitleme<!--1067692 --> 
DEP kaydı sırasında bir kullanıcının kimliğini Kurulum Yardımcısı yerine Şirket Portalı ile doğrularsanız, artık Şirket Portalı’nı Tekli Uygulama modunda çalıştırma seçeneğiniz var. Bu seçenek, Kurulum Yardımcısı tamamlandıktan hemen sonra cihazı kilitler; böylece kullanıcının cihaza erişmek için oturum açması gerekir. Bu işlem, cihazın eklenmesinin tamamlanmasını ve kullanıcısı olmadan yalnız bırakılmış duruma gelmemesini sağlar.

#### <a name="assign-a-user-and-friendly-name-to-an-autopilot-device--1346521---"></a>Autopilot cihazına kullanıcı ve kolay ad atama<!--1346521 -->
Artık [tek bir Autopilot cihazına kullanıcı atayabilirsiniz](../enrollment/enrollment-autopilot.md). Yöneticiler ayrıca cihazlarını AutoPilot ile ayarlayan kullanıcıları karşılaması için kolay adlar verebilecekler.
Şunlar için geçerlidir: En son [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) derlemesi (önizlemedeyken).

#### <a name="use-vpp-device-licenses-to-pre-provision-the-company-portal-during-dep-enrollment---1608345---"></a>DEP kaydı sırasında Şirket Portalı’nın ön sağlamasını yapmak için VPP cihaz lisanslarını kullanın<!-- 1608345 -->
Artık Aygıt Kayıt Programı (DEP) kayıtları sırasında Şirket Portalı’nın ön sağlamasını yapmak için Volume Purchase Program (VPP) cihaz lisanslarını kullanabileceksiniz. Bunu yapmak için [bir kayıt profili oluşturduğunuzda veya düzenlediğinizde](../enrollment/device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile), Şirket Portalı’nı yüklemek için kullanmak istediğiniz VPP belirtecini belirtin. Belirtecinizin süresinin dolmadığından ve Şirket Portalı uygulaması için yeterli lisansınız olduğundan emin olun. Belirtecin süresi dolduğu veya yeterli lisans olmadığı durumlarda, Intune bunun yerine Uygulama Mağazası Şirket Portalı’na istek gönderir (bu, Apple kimliği ister).

#### <a name="confirmation-required-to-delete-vpp-token-that-is-being-used-for-company-portal-pre-provisioning---2237634---"></a>Şirket Portalı ön sağlaması için kullanılan bir VPP belirtecini silmek için onay gerekir<!-- 2237634 -->
DEP kaydı sırasında Şirket Portalı’nın ön sağlaması için bir Volume Purchase Program (VPP) belirteci kullanılıyorsa artık bunu silmek için onay gerekir.

#### <a name="block-windows-personal-device-enrollments---1849498---"></a>Windows kişisel cihaz kayıtlarını engelleme<!-- 1849498 -->
[Windows kişisel cihazları engelleyerek](../enrollment/enrollment-restrictions-set.md) Intune [mobil cihaz yönetimine](../enrollment/windows-enroll.md) kaydolmasını önleyebilirsiniz. Bu özellikle [Intune PC aracısı](../manage-windows-pcs-with-microsoft-intune.md) ile kaydedilen cihazlar engellenemez. Bu özellik, önümüzdeki birkaç hafta içerisinde yayımlanacak, bu nedenle kullanıcı arabiriminde özelliği hemen göremeyebilirsiniz.

#### <a name="specify-machine-name-patterns-in-an-autopilot-profile--1849855--"></a>Autopilot profilinde makine adı desenleri belirtme<!--1849855-->
Autopilot kaydı sırasında [bilgisayar adı](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) oluşturmak ve ayarlamak için [bir bilgisayar adı şablonu](../enrollment/enrollment-autopilot.md#create-an-autopilot-deployment-profile) belirtebilirsiniz. Şunlar için geçerlidir: En son [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) derlemesi (önizlemedeyken).

#### <a name="for-windows-autopilot-profiles-hide-the-change-account-options-on-the-company-sign-in-page-and-domain-error-page--1901669---"></a>Windows Autopilot profilleri için şirket oturum açma sayfasında ve etki alanı hata sayfasında hesap değiştirme seçeneklerini gizleme<!--1901669 -->
Yöneticilerin şirket oturum açma ve etki alanı hata sayfalarında hesap değiştirme seçeneklerini gizlemelerine imkan veren [yeni Windows Autopilot profil seçenekleri](../enrollment/enrollment-autopilot.md#create-an-autopilot-deployment-profile) mevcut. Bu seçenekleri gizlemek, Azure Active Directory’de Şirket Markasının yapılandırılmasını gerektirir. Şunlar için geçerlidir: En son [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) derlemesi (önizlemedeyken).

### <a name="macos-support-for-apple-device-enrollment-program---747651---"></a>Apple Aygıt Kayıt Programı için macOS desteği<!-- 747651 -->
Intune, macOS cihazlarının Apple Aygıt Kayıt Programı'na (DEP) kaydedilmesini artık destekleniyor. Daha fazla bilgi için bkz. [macOS cihazlarını Apple’ın Aygıt Kayıt Programı ile otomatik olarak kaydetme](../enrollment/device-enrollment-program-enroll-macos.md).

### <a name="device-management"></a>Cihaz yönetimi

#### <a name="delete-jamf-devices---2653306--"></a>Jamf cihazlarını silme<!-- 2653306-->
**Cihazlar**’a gidip JAMF cihazını ve daha sonra **Sil**’i seçerek JAMF tarafından yönetilen cihazları silebilirsiniz.

#### <a name="change-terminology-to-retire-and-wipe---2175759---"></a>Terminolojiyi "kullanım dışı bırakma" ve "temizleme" olarak değiştirin<!-- 2175759 -->
Graph API ile tutarlılığı sağlamak için Intune kullanıcı arabirimi ve belgelerine aşağıdaki terim değişiklikleri yansıtıldı:
- **Şirket verilerini kaldırma** terimi, “kullanımdan kaldırma” olarak değiştirilecek
- **Fabrika sıfırlaması** terimi **temizleme** olarak değiştirilecek

#### <a name="confirmation-dialog-if-admin-tries-to-delete-mdm-push-certificate---297909500--"></a>Yönetici MDM Anında İletme Sertifikası’nı silmeye çalıştığında onay iletişim kutusu<!-- 297909500-->
Apple MDM Anında İletme Sertifikası silinmeye çalışılırsa, ilgili iOS ve macOS cihaz sayısını gösteren bir onay iletişim kutusu görüntülenir. Sertifika silinirse bu cihazların yeniden kaydedilmesi gerekir.

#### <a name="additional-security-settings-for-windows-installer---2282430---"></a>Windows Installer için ek güvenlik ayarları<!-- 2282430 -->
Kullanıcıların uygulama yüklemelerini denetlemesine olanak sağlayabilirsiniz. Etkinleştirilirse, aksi takdirde güvenlik ihlali nedeniyle durdurulabilecek olan yüklemelerin devam etmesine izin verilebilir. Windows Installer'ı sistemde herhangi bir program yüklerken yükseltilmiş izinler kullanmaya yönlendirebilirsiniz. Buna ek olarak, Windows Bilgi Koruması (WIP) öğelerinin dizine alınmasını ve bunlar hakkındaki meta verilerin şifrelenmemiş bir konumda depolanmasını etkinleştirebilirsiniz. İlke devre dışı bırakıldığında, WIP korumalı öğelerin dizini oluşturulmaz ve Cortana veya dosya gezgini sonuçlarında görünmez. Bu seçeneklerin işlevselliği varsayılan olarak devre dışı bırakılmıştır. 

#### <a name="new-user-experience-update-for-the-company-portal-website--2000968---"></a>Şirket Portalı web sitesi için yeni kullanıcı deneyimi güncelleştirmesi<!--2000968 -->
Müşterilerden gelen geri bildirim temelinde Şirket Portalı web sitesine yeni özellikler ekledik. Cihazlarınızın mevcut işlevselliğinde ve kullanılabilirliğinde önemli gelişmeler göreceksiniz. Sitenin &ndash;cihaz ayrıntıları, geri bildirim ve destek, cihaza genel bakış gibi&ndash; alanlarında yeni, modern, hızlı yanıt veren bir tasarım bulunuyor. Şunları da göreceksiniz:

- Tüm cihaz platformları arasında rahat iş akışları
- Geliştirilmiş cihaz kimlik ve kayıt akışları
- Daha yararlı hata iletileri
- Daha rahat bir dil, daha az teknik jargon
- Doğrudan uygulama bağlantıları paylaşabilme seçeneği
- Büyük uygulama katalogları için iyileştirilmiş performans
- Tüm kullanıcılar için artırılmış erişilebilirlik  

[Intune Şirket Portalı belgeleri](https://docs.microsoft.com/intune-user-help/using-the-intune-company-portal-website) de bu değişiklikleri yansıtacak şekilde güncelleştirildi. Uygulama iyileştirmelerine dair bir örnek görmek isterseniz bkz. [Intune son kullanıcı uygulamaları için kullanıcı arabirimi güncelleştirmeleri](../whats-new-app-ui.md).  

### <a name="monitor-and-troubleshoot"></a>İzleme ve sorun giderme

#### <a name="enhanced-jailbreak-detection-in-compliance-reporting---2198738---"></a>Uyumluluk raporlamada gelişmiş jailbreak algılama<!-- 2198738 -->
Gelişmiş jailbreak algılama ayarı durumları, artık yönetici konsolundaki tüm uyumluluk raporlarında görünüyor.

### <a name="role-based-access-control"></a>Rol tabanlı erişim denetimi

#### <a name="scope-tags-for-policies--1081974---"></a>İlkeler için kapsam etiketleri<!--1081974 -->
Intune kaynaklarına erişimi sınırlamak için [kapsam etiketleri oluşturabilirsiniz](scope-tags.md). Bir rol atamasına kapsam etiketi ekleyin ve daha sonra kapsam etiketini bir yapılandırma profiline ekleyin. Rolün yalnızca eşleşen kapsam etiketlerine sahip yapılandırma profillerine erişimi olacaktır.





<!-- ########################## -->
## <a name="july-2018"></a>Temmuz 2018

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="line-of-business-lob-app-support-for-macos---1895847---"></a>macOS için iş kolu (LOB) uygulamaları desteği<!-- 1895847 -->
Microsoft Intune, macOS LOB uygulamalarının **Gerekli** veya **Kayıt sonrasında kullanılabilir** olarak dağıtılmasına imkan verir. Son kullanıcılar, uygulamaları macOS için Şirket Portalı’ndan veya [Şirket Portalı web sitesinden](https://portal.manage.microsoft.com) **Kullanılabilir** olarak edinebilir.

#### <a name="ios-built-in-app-support-for-kiosk-mode---2051098---"></a>Bilgi noktası modu için yerleşik iOS uygulama desteği<!-- 2051098 -->
Mağaza Uygulamaları ve Yönetilen Uygulamalara ek olarak artık iOS cihazında bilgi noktası modunda çalışan Safari gibi Yerleşik Uygulamaları da seçebilirsiniz.

#### <a name="edit-your-office-365-pro-plus-app-deployments---2150145---"></a>Office 365 Pro Plus uygulama dağıtımlarınızı düzenleme<!-- 2150145 -->
Microsoft Intune yöneticisi olarak, Office 365 Pro Plus uygulama dağıtımlarınızı düzenleme olanağınız artar. Ayrıca paketin özelliklerinden herhangi birini değiştirmek için artık dağıtımlarınızı silmeniz gerekmez. Azure portalında **Microsoft Intune** > **İstemci uygulamaları** > **Uygulamalar**’ı seçin. Uygulama listesinden Office 365 Pro Plus Suite ürününüz seçin.  

#### <a name="updated-intune-app-sdk-for-android-is-now-available---2744271--"></a>Güncelleştirilmiş Android için Intune Uygulama SDK'sı artık kullanıma sunuldu<!-- 2744271-->
Android P sürümünü desteklemek amacıyla Android için Intune Uygulama SDK'sının güncelleştirilmiş sürümü kullanıma sunuldu. Bir uygulama geliştiricisiyseniz ve Android için Intune SDK'sını kullanıyorsanız, Android uygulamalarınızdaki Intune işlevselliğinin Android P cihazlarında beklendiği gibi çalışmaya devam edebilmesi için Intune uygulama SDK'sının güncelleştirilmiş sürümünü yüklemelisiniz. Intune Uygulama SDK'sının bu sürümü, SDK güncelleştirmelerini gerçekleştiren yerleşik bir eklenti sağlar. Tümleştirilmiş mevcut kodu yeniden yazmanız gerekmez. Ayrıntılar için bkz. [Android için Intune SDK'sı](https://github.com/msintuneappsdk/ms-intune-app-sdk-android). Intune için eski rozetleme stilini kullanıyorsanız, evrak çantası simgesini kullanmanızı öneririz. Markalama ayrıntıları için [bu GitHub deposuna](https://github.com/msintuneappsdk/intune-app-partner-badge) bakın.

#### <a name="more-opportunities-to-sync-in-the-company-portal-app-for-windows"></a>Windows için Şirket Portalı uygulamasında daha fazla eşitleme fırsatı  
Windows için Şirket Portalı uygulaması artık eşitlemeyi doğrudan Windows görev çubuğu ve Başlat menüsünden başlatmanıza olanak tanır. Göreviniz yalnızca cihazları eşitlemek veya şirket kaynaklarına erişim sağlamak olduğunda, bu özellik çok kullanışlıdır. Yeni özelliğe erişmek için görev çubuğunuza veya Başlat menünüze sabitlenmiş Şirket portalı simgesine sağ tıklayın. Menü seçeneklerinde (atlama listesi olarak da bilinir) **Bu cihazı eşitle**’yi seçin. Şirket Portalı, **Ayarlar** sayfası açılır ve eşitleme işlemini başlatır. Yeni işlevlere göz atmak için bkz. [Kullanıcı arabirimindeki](../whats-new-app-ui.md)yenilikler.   

#### <a name="new-browsing-experiences-in-the-company-portal-app-for-windows"></a>Windows için Şirket Portalı uygulamasında yeni göz atma deneyimleri  
Artık Windows için Şirket Portalı uygulamasında uygulamalara göz atarken veya uygulama ararken mevcut **Kutucuklar** görünümü ile yeni eklenen **Ayrıntılar** görünümü arasında geçiş yapabilirsiniz. Yeni görünümde ad, yayımcı, yayım tarihi ve yükleme durumu gibi uygulama ayrıntıları listelenir.  

**Uygulamalar** sayfasının **Yüklemeler** görünümü, tamamlanmış ve devam eden uygulama yüklemeleri hakkındaki ayrıntıları görmenizi sağlar. Yeni görünümün neye benzediğine göz atmak için bkz. [Kullanıcı arabirimindeki yenilikler](../whats-new-app-ui.md).  

#### <a name="improved-company-portal-app-experience-for-device-enrollment-managers"></a>Cihaz kayıt yöneticileri için geliştirilmiş Şirket Portalı uygulaması deneyimi  
Bir cihaz kayıt yöneticisi (DEM) Windows için Şirket Portalı uygulamasında oturum açtığında, uygulama artık yalnızca yöneticinin geçerli, çalışan cihazını listeleyecek. Bu yenilik, uygulama DEM tarafından kaydedilen tüm cihazları göstermeye çalıştığında yaşanan zaman aşımı sorunlarını azaltacak.  

#### <a name="block-app-access-based-on-unapproved-device-vendors-and-models----1425689----"></a>Onaylanmamış cihaz satıcıları ve modellerine göre uygulama erişimini engelleme <!-- 1425689 ! -->
Intune BT yöneticisi, belirlenen Android üreticileri ve/veya iOS modelleri listesini Intune Uygulama Koruması İlkeleri yoluyla zorlayabilir. BT yöneticisi, Android ilkeleri için noktalı virgülle ayrılmış bir üretici listesi ve aynı şekilde iOS ilkeleri için bir cihaz modelleri listesi sağlayabilecek. Intune Uygulama Koruması İlkeleri, yalnızca Android ve iOS için geçerlidir. Bu belirtilen listede gerçekleştirilebilen iki ayrı eylem vardır:
- Belirtilmemiş cihazlarda uygulama erişimini engelleme.
- Veya belirtilmemiş cihazlarda şirket verilerini seçmeli olarak silme. 

İlke gereksinimleri karşılanmazsa kullanıcı, hedeflenen uygulamaya erişemeyecek. Ayarlara bağlı olarak kullanıcı engellenebilir veya uygulama dahilinde kullanıcının şirket verileri seçmeli olarak silinir. iOS cihazlarında, bu özelliğin hedeflenen uygulamalarda zorlanması için Intune APP SDK'nin tümleştirilmesi amacıyla uygulamaların (WXP, Outlook, Managed Browser, Yammer gibi) katılımı gerekir. Bu tümleştirme, sıralı bir şekilde gerçekleşir ve belirli uygulama ekiplerine bağımlıdır. Android’de bu özellik, Şirket Portalı’nın en son sürümünü gerektirir. 

Son kullanıcı cihazlarında Intune istemcisi, Intune’un Uygulama Koruma İlkeleri dikey penceresinde belirtilen dizelerin basit eşleştirmesine dayalı olarak eylem gerçekleştirir. Bu, tamamen cihazın rapor ettiği değere bağlıdır. Bu nedenle BT yöneticisinin amaçlanan davranışın doğru olduğundan emin olması önerilir. Bu ayar, küçük bir kullanıcı grubuna hedeflenen çeşitli cihaz üreticileri ve modellerinde sınanarak doğruluğundan emin olunabilir. Microsoft Intune’da uygulama koruma ilkelerini görüntülemek ve ilke eklemek için **İstemci uygulamaları** > **Uygulama koruma ilkeleri**’ni seçin. Uygulama koruma ilkeleri hakkında daha fazla bilgi için bkz. [Uygulama koruma ilkeleri nedir?](../apps/app-protection-policy.md) ve [Intune’da uygulama koruma ilkesi erişim eylemlerini kullanarak verileri seçmeli olarak silme](../apps/app-protection-policies-access-actions.md).

#### <a name="access-to-macos-company-portal-pre-release-build---1734766---"></a>macOS Şirket Portalı yayın öncesi derlemesine erişim<!-- 1734766 -->
Insider programına katılarak, Microsoft AutoUpdate'i kullanıp derlemeleri erken almak için kaydolabilirsiniz. Kaydolmanız, güncelleştirilmiş Şirket Portalı'nı son kullanıcılarınıza sağlanmadan önce kullanmanıza olanak tanıyacaktır. Daha fazla bilgi için, [Microsoft Intune bloguna](https://blogs.technet.microsoft.com/intunesupport/2018/07/13/use-microsoft-autoupdate-for-early-access-to-the-macos-company-portal-app/) bakın.

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="create-device-compliance-policy-using-firewall-settings-on-macos-devices---1497640---"></a>macOS cihazlarında Güvenlik Duvarı ayarlarını kullanarak cihaz uyumluluk ilkesi oluşturma<!-- 1497640 -->
Yeni bir macOS uyumluluk ilkesi oluşturduğunuzda (**Cihaz uyumluluğu** > **İlkeler** > **İlke oluştur** > **Platform: macOS** > **Sistem güvenliği**), bazı yeni **Güvenlik Duvarı** ayarları sağlanır: 

- **Güvenlik Duvarı**: Gelen bağlantıların ortamınızda nasıl işleneceğini yapılandırın.
- **Gelen bağlantılar**: DHCP, Bonjour ve IPSec gibi temel İnternet hizmetleri için gerekenler dışında tüm gelen bağlantıları **engelleyin**. Bu ayar tüm paylaşım hizmetlerini de engeller.
- **Gizli Mod**: Cihazın yoklama isteklerine yanıt vermesini önlemek için gizli modu **etkinleştirin**. Cihaz, yetkilendirilmiş uygulamalardan gelen istekleri yanıtlamaya devam eder.

Şunlar için geçerlidir: macOS 10.12 ve üstü

#### <a name="new-wi-fi-device-configuration-profile-for-windows-10-and-later---1879077---"></a>Windows 10 ve üzeri için yeni Wi-Fi cihaz yapılandırma profili<!-- 1879077 -->
Şu anda XML dosyalarını kullanarak Wi-Fi profillerini içeri ve dışarı aktarabilirsiniz. Bu güncelleştirmeyle, tıpkı bazı diğer platformlarda olduğu gibi Intune’da doğrudan Wi-Fi cihaz yapılandırma profili oluşturabilirsiniz.

Profili oluşturmak için **Cihaz Yapılandırması** > **Profiller** > **Profil Oluştur** > **Windows 10 ve üzeri** > **Wi-Fi** seçeneklerini açın. 

Windows 10 ve üzeri için geçerlidir.

#### <a name="kiosk---obsolete-is-grayed-out-and-cant-be-changed---2149998---"></a>Bilgi noktası - eski seçenek gri gösterilir ve değiştirilemez<!-- 2149998 -->
Bilgi noktası (önizleme) özelliği (**Cihaz yapılandırması** > **Profiller** > **Profil oluştur** > **Windows 10 ve üzeri** > **Cihaz kısıtlamaları**) artık kullanılmıyor ve [Windows 10 ve üzeri için bilgi noktası ayarları](../configuration/kiosk-settings.md) ile değiştirildi. Bu güncelleştirmeyle **Bilgi Noktası - Eski** özelliği gri gösterilir ve kullanıcı arabirimi değiştirilemez veya güncelleştirilemez. 

Bilgi noktası modunu etkinleştirmek için bkz. [Windows 10 ve üzeri için bilgi noktası ayarları](../configuration/kiosk-settings.md).

Windows 10 ve üzeri, Windows Holographic for Business için geçerlidir

#### <a name="apis-to-use-3rd-party-certification-authorities---2184013---"></a>Üçüncü taraf sertifika yetkilileri kullanacak API’ler<!-- 2184013 -->
Bu güncelleştirmede, üçüncü taraf sertifika yetkililerinin Intune ve SCEP ile tümleştirilmesini etkinleştirecek bir Java API’si yer alır. Ardından kullanıcılar, SCEP sertifikasını bir profil ekleyebilir ve MDM kullanarak cihazlara uygulayabilir.

Intune şu anda [Active Directory Sertifika Hizmetleri kullanarak SCEP isteklerini](../protect/certificates-scep-configure.md) destekler.

#### <a name="toggle-to-show-or-not-show-the-end-session-button-on-a-kiosk-browser---2455253---"></a>Bir Bilgi Noktası tarayıcısında Oturumu Sonlandır düğmesini gösterme veya gizleme geçişi<!-- 2455253 -->
Artık Bilgi Noktası tarayıcılarını Oturumu Sonlandır düğmesini gösterecek veya gizleyecek şekilde yapılandırabilirsiniz. Denetim seçeneğini **Cihaz yapılandırması** > **Bilgi noktası (önizleme)**  > **Bilgi Noktası Web Tarayıcısı**’ndan görebilirsiniz. Açılırsa kullanıcı bir düğmeye tıkladığında uygulama, oturumu sonlandırma için onay ister. Onaylandığında tarayıcı, tüm göz atma verilerini temizler ve varsayılan URL’ye geri gider.

#### <a name="create-an-esim-cellular-configuration-profile---2564077---"></a>eSIM hücresel yapılandırma profili oluşturma<!-- 2564077 -->
**Cihaz yapılandırmasında** bir eSIM hücresel profili oluşturabilirsiniz. Cep telefonu operatörünüz tarafından sağlanan hücresel etkinleştirme kodlarını içeren bir dosyayı içeri aktarabilirsiniz. Ardından bu profilleri, Surface Pro LTE ve diğer eSIM özellikli cihazlar gibi eSIM LTE etkinleştirilmiş Windows 10 cihazlara dağıtabilirsiniz.

[Cihazınızın eSIM profillerini destekleyip desteklemediğini](https://support.microsoft.com/help/4020763/windows-10-use-esim-for-cellular-data) görmek için kontrol edin.

Windows 10 ve üzeri için geçerlidir.

#### <a name="select-device-categories-by-using-the-access-work-or-school-settings---1058963-eenotready---"></a>İş Yeri veya Okula Erişme ayarlarını kullanarak cihaz kategorilerini seçme<!-- 1058963 eenotready --> 
[Cihaz grubu eşlemeyi](../enrollment/device-group-mapping.md) etkinleştirdiyseniz, Windows 10'daki kullanıcılardan şimdi **Ayarlar** > **Hesaplar** > **İş yeri veya okula eriş** altındaki **Bağlan** düğmesi aracılığıyla kaydolduktan sona cihaz kategorisini seçmeleri istenecek. 

#### <a name="use-samaccountname-as-the-account-username-for-email-profiles---1500307---"></a>E-posta profilleri için hesap kullanıcı adı olarak sAMAccountName kullanın<!-- 1500307 -->
Android, iOS ve Windows 10'da e-posta profillerinin hesap kullanıcı adı olarak şirket içi **sAMAccountName** adını kullanabilirsiniz. Ayrıca Azure Active Directory'de (Azure AD) `domain`.veya `ntdomain` özniteliğinden etki alanını da alabilirsiniz. Bunun yerine özel bir statik etki alanı girebilirsiniz.

Bu özelliği kullanmak için, şirket içi Active Directory ortamınızdan Azure AD'ye `sAMAccountName` özniteliğini eşitlemeniz gerekir.

Şunlar için geçerlidir: [Android](../configuration/email-settings-android.md), [iOS](../configuration/email-settings-ios.md), [Windows 10 ve üzeri](../configuration/email-settings-windows-10.md)

#### <a name="see-device-configuration-profiles-in-conflict---1556983---"></a>Çakışması olan cihaz yapılandırma profillerini görme<!-- 1556983 -->
**Cihaz Yapılandırması**’nda mevcut profillerin bir listesi gösterilir. Bu güncelleştirme ile çakışması olan profiller hakkında ayrıntılar sağlayan yeni bir sütun eklenir. Çakışması olan ayarı ve profili görmek için çakışan bir satırı seçebilirsiniz. 

[Yapılandırma profillerini yönetme](../configuration/device-profile-monitor.md#view-conflicts) başlığı altında daha fazla bilgi edinebilirsiniz.

#### <a name="new-status-for-devices-in-device-compliance---2308882---"></a>Cihaz uyumluluğunda cihazlar için yeni durum<!-- 2308882 -->
**Cihaz uyumluluğu** > **İlkeler**'de bir ilke seçin ve **Genel Bakış**’ı seçin; aşağıdaki yeni durumlar eklenir:
- başarılı
- hata
- çakışma
- Yayınlan
- uygulanamaz Farklı bir platformun cihaz sayısını gösteren bir resim de görüntülenir. Örneğin bir iOS profiline bakıyorsanız, yeni kutucuk yine bu profile atanmış olan iOS dışı cihazların sayısını gösterir. Bkz. [Cihaz uyumluluk ilkeleri](../protect/compliance-policy-monitor.md#view-status-of-device-policies).

#### <a name="device-compliance-supports-3rd-party-anti-virus-solutions---2325484---"></a>Cihaz uyumluluğu üçüncü taraf virüsten koruma çözümlerini destekler<!-- 2325484 -->
Yeni bir cihaz uyumluluğu ilkesi oluşturduğunuzda (**Cihaz uyumluluğu** > **İlkeler** > **İlke oluştur** > **Platform: Windows 10 ve üzeri** > **Ayarlar** > **Sistem Güvenliği**) yeni **[Cihaz Güvenliği](../protect/compliance-policy-create-windows.md)** seçenekleri olur: 
- **Virüsten koruma**: **Gerektir** olarak ayarlandığında, Windows Güvenlik Merkezi’ne kaydedilmiş Symantec ve Windows Defender gibi virüsten koruma çözümlerini kullanarak uyumluluğu denetleyebilirsiniz. 
- **Casus yazılımdan koruma**: **Gerektir** olarak ayarlandığında, Windows Güvenlik Merkezi’ne kaydedilmiş Symantec ve Windows Defender gibi casus yazılımdan koruma çözümlerini kullanarak uyumluluğu denetleyebilirsiniz. 

Şunlar için geçerlidir: Windows 10 ve üzeri 

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="automatically-mark-android-devices-enrolled-by-using-samsung-knox-mobile-enrollment-as-corporate---2404851---"></a>Samsung Knox Mobil Kayıt kullanarak “şirket” olarak kaydedilen Android cihazlarını otomatik olarak işaretleyin.<!-- 2404851 -->
Varsayılan olarak Samsung Knox Mobil Kayıt kullanarak kaydedilen Android cihazları, **Cihaz Sahipliği** altında **şirket** olarak işaretlenir. Şirket cihazlarını Knox Mobil Kayıt kullanarak kaydetmeden önce IMEI veya seri numaraları kullanarak el ile belirlemeniz gerekmez.

#### <a name="devices-without-profiles-column-in-the-list-of-enrollment-program-tokens---1853904---"></a>Kayıt programı belirteçleri listesinde profil sütunu olmayan cihazlar<!-- 1853904 -->
Kayıt programı belirteçleri listesinde, profil atanmamış olan cihazların sayısını gösteren yeni bir sütun vardır. Bu, yöneticilerin bu cihazları kullanıcılara teslim etmeden önce bunlara profil atamasına yardımcı olur. Yeni sütunu görmek için, **Cihaz kaydı** > **Apple kaydı** > **Kayıt programı belirteçleri**'ne gidin.

### <a name="device-management"></a>Cihaz yönetimi

#### <a name="bulk-delete-devices-on-devices-blade---1793693---"></a>Cihazlar dikey penceresinde cihazları toplu silme<!-- 1793693 -->
Şimdi Cihazlar dikey penceresinde tek seferde birden fazla cihazı silebilirsiniz. **Cihazlar** > **Tüm cihazlar** > silmek istediğiniz cihazları seçin > **Sil**'i seçin. Silinemeyen cihazlar için bir uyarı görüntülenir.

#### <a name="google-name-changes-for-android-for-work-and-play-for-work--842873---"></a>Android for Work ve Play for Work için Google ad değişiklikleri<!--842873 -->
Intune, "Android for Work" terminolojisini Google marka değişikliklerini yansıtacak şekilde güncelleştirdi. "Android for Work" ve "Play for Work" terimleri artık kullanılmıyor. Bağlama göre farklı bir terminoloji kullanılıyor:
- "Android kurumsal", genel olarak modern Android yönetim yığınına karşılık gelir.
- "İş profili" veya "Profil Sahibi", iş profilleriyle yönetilen KCG cihazlarına karşılık gelir.
- "Yönetilen Google Play", Google uygulama mağazasına karşılık gelir.

#### <a name="rules-for-removing-devices---1609459---"></a>Cihaz kaldırma kuralları<!-- 1609459 -->
Ayarladığınız süre boyunca (gün) iade edilmeyen cihazları otomatik olarak kaldırmanıza olanak tanıyan yeni kurallar kullanılabilir. Yeni kuralı görmek için **Intune** bölmesine gidin, **Cihazlar**’ı ve **Cihaz temizleme kuralları**’nı seçin.

#### <a name="corporate-owned-single-use-support-for-android-devices---1630973---"></a>Android cihazlar için şirkete ait, tek kullanım desteği<!-- 1630973 -->

Intune şimdi üst düzeyde yönetilen, kilitlenen, bilgi noktası stilindeki Android cihazlarını destekler. Bu sayede yöneticiler cihazın kullanımını tek uygulamayla veya küçük bir uygulama kümesiyle kilitleyebilir ve kullanıcıların cihazda başka uygulamaları etkinleştirmesini veya başka eylemler gerçekleştirmesini engelleyebilir. Android kiosku ayarlamak için, Intune > **Cihaz kaydı** > **Android kaydı** > **Kiosk ve görev cihazı kayıtları**'na gidin. Daha fazla bilgi için bkz. [Android kurumsal kiosk cihazlarının kaydını ayarlama](../enrollment/android-kiosk-enroll.md).

#### <a name="per-row-review-of-duplicate-corporate-device-identifiers-uploaded---2203794--"></a>Karşıya yüklenmiş yinelen şirket cihazı tanımlayıcılarını satır temelinde gözden geçirme<!-- 2203794-->
Şirket kimliklerini karşıya yüklerken, Intune şimdi tüm yinelemelerin listesini sağlar ve size mevcut bilgileri değiştirme veya koruma seçeneği verir. **Cihaz kaydı** > **Şirket Cihazı Tanımlayıcıları** > **Tanımlayıcıları Ekle**'yi seçtikten sonra yinelemeler varsa rapor görüntülenecek. 

#### <a name="manually-add-corporate-device-identifiers---2203803---"></a>Şirket cihazı tanımlayıcılarını el ile ekleme<!-- 2203803 -->
Şimdi şirket cihazı kimliklerini el ile ekleyebilirsiniz. **Cihaz kaydı** > **Şirket Cihazı Tanımlayıcıları** > **Ekle**'yi seçin. 


<!-- ########################## -->
## <a name="june-2018"></a>Haziran 2018

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="microsoft-edge-mobile-support-for-intune-app-protection-policies---1817882---"></a>Intune uygulama koruma ilkeleri için Microsoft Edge mobil desteği<!-- 1817882 -->
Mobil cihazlar için Microsoft Edge tarayıcısı, artık Intune’da tanımlanan uygulama koruma ilkelerini destekliyor.

#### <a name="retrieve-the-associated-app-user-model-id-aumid-for-microsoft-store-for-business-apps-in-kiosk-mode---1560077----"></a>İş İçin Microsoft Store uygulamaları için bilgi noktası modunda ilişkili uygulama kullanıcı model kimliğini (AUMID) alma<!-- 1560077 ! -->
Intune artık bilgi noktası profilinde daha iyi bir yapılandırma sağlamak amacıyla İş İçin Microsoft Store (WSfB) uygulamaları için uygulama kullanıcı model kimliklerini (AUMID) alabilir.

İş İçin Microsoft Store uygulamaları hakkında daha fazla bilgi için bkz. [İş İçin Microsoft Store’dan uygulamaları yönetme](../apps/windows-store-for-business.md).

#### <a name="new-company-portal-branding-page---1916370---"></a>Yeni Şirket Portalı markalama sayfası<!-- 1916370 -->
Şirket Portalı markalama sayfasının yeni bir düzeni, iletileri ve araç ipuçları vardır.


### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="pradeo---new-mobile-threat-defense-partner---1169249---"></a>Pradeo - Yeni Mobile Threat Defense iş ortağı<!-- 1169249 -->
Microsoft Intune ile tümleşen bir mobil tehdit savunması çözümü olan Pradeo tarafından gerçekleştirilen risk değerlendirmesine dayalı koşullu erişimi kullanarak mobil cihaz erişimini kontrol edebilirsiniz.

#### <a name="use-fips-mode-with-the-ndes-certificate-connector---1333688---"></a>NDES Sertifika bağlayıcısında FIPS modunu kullanma<!-- 1333688 -->
NDES Sertifika bağlayıcısını Federal Bilgi İşleme Standardı (FIPS) modu etkin bir bilgisayara yüklediğinizde, sertifika verme ve iptal etme işlemleri beklendiği gibi çalışmıyordu. Bu güncelleştirmeyle birlikte FIPS desteği, NDES Sertifika bağlayıcısına eklenmiştir. 

Bu güncelleştirme ayrıca şunları içerir:

- NDES Sertifika bağlayıcısı; Windows Server 2016 ve Windows Server 2012 R2’ye otomatik olarak dahil edilen .NET 4.5 Framework’ü gerektirir. Önceden .NET 3.5 Framework, gereken en düşük sürümdü.
- TLS 1.2 desteği, NDES Sertifika Bağlayıcısına dahil edilmiştir. Bu nedenle NDES Sertifika bağlayıcısı yüklü olan sunucu TLS 1.2’yi destekliyorsa TLS 1.2 kullanılır. Sunucu TLS 1.2 desteklemiyorsa TLS 1.1 kullanılır. Şu anda TLS 1.1, cihazlar ve sunucu arasında kimlik doğrulaması için kullanılmaktadır.

Daha fazla bilgi için bkz. [SCEP sertifikalarını yapılandırma ve kullanma](../protect/certificates-scep-configure.md) ve [PKCS sertifikalarını yapılandırma ve kullanma](../protect/certficates-pfx-configure.md).

#### <a name="support-for-palo-alto-networks-globalprotect-vpn-profiles---1333680----"></a>Palo Alto Networks GlobalProtect VPN profilleri için destek<!-- 1333680 ! -->
Bu güncelleştirme ile Intune’da VPN profilleri için VPN bağlantısı olarak Palo Alto Networks GlobalProtect’i seçebilirsiniz (**Cihaz yapılandırması** > **Profiller** > **Profil oluştur** > **Profil türü** > **VPN**). Bu sürümde aşağıdaki platformlar desteklenir: 

- iOS
- Windows 10

#### <a name="additions-to-local-device-security-options-settings---1403702---"></a>Yerel Cihaz Güvenliği Seçenekleri ayarlarına ekler<!-- 1403702 -->
Artık Windows 10 cihazları için ek Yerel Cihaz Güvenliği Seçenekleri ayarları yapılandırabilirsiniz. Ek ayarlar; Microsoft Ağ İstemcisi, Microsoft Ağ Sunucusu, Ağ erişimi ve güvenlik ve Etkileşimli oturum açma bölümlerinde kullanılabilir. Bu ayarları, bir Windows 10 cihaz yapılandırma ilkesi oluşturduğunuzda Endpoint Protection kategorisinde bulabilirsiniz.

#### <a name="enable-kiosk-mode-on-windows-10-devices---1560072----"></a>Windows 10 cihazlarda bilgi noktası modunu etkinleştirme<!-- 1560072 ! -->
Windows 10 cihazlarda bir yapılandırma profili oluşturabilir ve bilgi noktası modunu etkinleştirebilirsiniz (**Cihaz Yapılandırması** > **Profiller** > **Profil oluştur** > **Windows 10** > **Cihaz Kısıtlamaları** > **Bilgi noktası**). Bu güncelleştirmede **Bilgi noktası (önizleme)** ayarı, **Bilgi noktası (kullanılmayan)** olarak yeniden adlandırıldı. **Bilgi noktası (kullanılmayan)** , artık kullanım için önerilmese de Temmuz güncelleştirmesine kadar işlevselliğini koruyacaktır. **Bilgi noktası (kullanılmayan)** , yeni **Bilgi noktası** türü (**Profil oluştur** > **Windows 10** > **Bilgi noktası (önizleme)** ) ile değiştirilmiştir. Bu yeni tür, Windows 10 RS4 ve üzeri sürümlerde Bilgi Noktalarını yapılandırmak üzere ayarlar içerecektir.

Windows 10 ve üzeri için geçerlidir.

#### <a name="device-profile-graphical-user-chart-is-back---2160133---"></a>Cihaz profili kullanıcı grafiği geri geldi<!-- 2160133 -->
Cihaz profili grafiğinde (**Cihaz yapılandırması** > **Profiller** > mevcut bir profil seçin > **Genel bakış**) gösterilen sayısal değerleri geliştirirken, kullanıcı grafiği geçici olarak kaldırılmıştı.

Bu güncelleştirmeyle birlikte kullanıcı grafiği geri geldi ve Azure portalında gösteriliyor.

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="support-for-windows-autopilot-enrollment-without-user-authentication---1165118---"></a>Kullanıcı kimlik doğrulaması olmadan Windows Autopilot kaydı desteği<!-- 1165118 -->
Intune şimdi kullanıcı kimlik doğrulaması olmadan Windows Autopilot kaydını destekliyor. Bu, Windows Autopilot dağıtım profilinde "Autopilot Dağıtım modu" değerinin "Kendi Kendine Dağıtım" olduğu yeni bir seçenektir.  Bu kayıt türünü başarıyla tamamlamak için cihaz, Windows 10 Insider Preview Derleme 17672 veya üzeri çalıştırmalı ve TPM 2.0 yongasına sahip olmalıdır. Kullanıcı kimlik doğrulaması gerekmediğinden, bu seçeneği yalnızca üzerinde fiziksel denetim sahibi olduğunuz cihazlara atamalısınız.

#### <a name="new-languageregion-setting-when-configuring-oobe-for-autopilot---1821766---"></a>Autopilot için OOBE yapılandırırken yeni dil/bölge ayarı<!-- 1821766 -->
Autopilot profilleri için İlk Çalıştırma Deneyimi sırasında dili ve bölgeyi ayarlamak için yeni bir yapılandırma ayarı kullanılabilir. Yeni ayarı görmek için, **Cihaz kaydı** > **Windows kaydı** > **Dağıtım profilleri** > **Profil oluştur** > **Dağıtım modu** = **Kendi kendine dağıtım** > **Varsayılanlar yapılandırıldı** öğesini seçin.

#### <a name="new-setting-for-configuring-device-keyboard---1821768---"></a>Cihaz klavyesini yapılandırmak için yeni ayar<!-- 1821768 -->
Autopilot profilleri için İlk Çalıştırma Deneyimi sırasında klavyeyi yapılandırmak için yeni bir ayar kullanılabilir olacak. Yeni ayarı görmek için, **Cihaz kaydı** > **Windows kaydı** > **Dağıtım profilleri** > **Profil oluştur** > **Dağıtım modu** = **Kendi kendine dağıtım** > **Varsayılanlar yapılandırıldı** öğesini seçin.

#### <a name="autopilot-profiles-moving-to-group-targeting---1877935---"></a>Autopilot profilleri grup hedeflemeye taşınıyor<!-- 1877935 -->
AutoPilot dağıtım profilleri AutoPilot cihazları içeren Azure AD gruplarına atanabilir.

### <a name="device-management"></a>Cihaz yönetimi

#### <a name="set-compliance-by-device-location---851881----"></a>Cihaz konumuna göre uyumluluk ayarlama<!-- 851881 ! -->
Bazı durumlarda, ağ bağlantısı tarafından belirlenen bir konumdan şirket kaynaklarına erişimi kısıtlamak isteyebilirsiniz. Artık cihazın IP adresine bağlı olarak bir uyumluluk ilkesi (**Cihaz uyumluluğu** > **Konumlar**) oluşturabilirsiniz. Cihaz, IP aralığı dışına çıktığında şirket kaynaklarına erişemez.

Uygulandığı öğe: Android cihazlar 6.0 ve üzeri, güncelleştirilmiş Şirket Portalı uygulaması ile

#### <a name="prevent-consumer-apps-and-experiences-on-windows-10-enterprise-rs4-autopilot-devices---1621980---"></a>Windows 10 Enterprise RS4 Autopilot cihazlarda tüketici uygulamaları ve deneyimlerini engelleme<!-- 1621980 -->
Windows 10 Enterprise RS4 AutoPilot cihazlarınızda tüketici uygulama ve deneyimlerinin yüklenmesini önleyebileceksiniz. Bu özelliği görmek için **Intune** > **Cihaz yapılandırması** > **Profiller** > **Profil oluştur** > **Platform** = **Windows 10 veya üzeri** > **Profil türü** = **Cihaz kısıtlamaları** > **Yapılandır** > **Windows Spot** > **Tüketici özellikleri**'ne gidin. 

#### <a name="uninstall-the-latest-from-windows-10-software-updates---1732948---"></a>En son Windows 10 yazılım güncelleştirmesini kaldırma<!-- 1732948 -->
Windows 10 makinelerinizde çalışmanın kesilmesine neden olan bir sorun keşfederseniz, en son özellik güncelleştirmesini veya en son kalite güncelleştirmesini kaldırmayı (geri almayı) seçebilirsiniz. Özellik veya kalite güncelleştirmesini kaldırma işlemi yalnızca hizmetin içinde açıldığı hizmet kanalında kullanılabilir. Kaldırma işlemi Windows 10 makinelerinizde önceki güncelleştirmeyi geri yüklemeye yönelik bir ilkeyi tetikler. Özellik güncelleştirmeleri için, en son sürümü kaldırma işleminin uygulanabilme süresini 2-60 gün arasıyla sınırlandırabilirsiniz. Yazılım güncelleştirmesini kaldırma seçeneklerini ayarlamak için, Azure portalının içindeki **Microsoft Intune** dikey penceresinden **Yazılım güncelleştirmeleri**'ni seçin. Ardından, **Yazılım güncelleştirmeleri** dikey penceresinden **Windows 10 Güncelleştirme Kademeleri**'ni seçin. Daha sonra da **Genel Bakış** bölümünde **Kaldır** seçeneğini belirtebilirsiniz.

#### <a name="search-all-devices-for-imei-and-serial-number---1793685---"></a>IMEI ve seri numarası için tüm cihazlarda arama yapma<!-- 1793685 -->
Artık Tüm cihazlar dikey penceresinde IMEI ve seri numaraları için arama yapabilirsiniz (e-posta, UPN, cihaz adı ve yönetim adı da hala kullanılabilir). Intune'da **Cihazlar** > **Tüm cihazlar**'ı seçin ve arama kutusuna aramanızı girin.

#### <a name="management-name-field-will-be-editable---1875989---"></a>Yönetim adı alanı düzenlenebilir olacak<!-- 1875989 -->
Artık bir cihazın **Özellikler** dikey penceresindeki yönetim adı alanını düzenleyebilirsiniz. Bu alanı düzenlemek için **Cihazlar** > **Tüm cihazlar** > cihazı seçin > **Özellikler** seçeneğini belirleyin. Bir cihazı benzersiz olarak tanımlamak için yönetim adı alanını kullanabilirsiniz.

#### <a name="new-all-devices-filter-device-category---1878520---"></a>Yeni tüm cihazlar filtresi: cihaz kategorisi<!-- 1878520 -->
Şimdi **Tüm cihazlar** listesini cihaz kategorisine göre filtreleyebilirsiniz. Bunu yapmak için, **Cihazlar** > **Tüm cihazlar** > **Filtre** > **Cihaz kategorisi**'ni seçin.

#### <a name="use-teamviewer-to-screen-share-ios-and-macos-devices---1985547---"></a>iOS ve MacOS cihazlarda ekran paylaşımı için TeamViewer kullanma<!-- 1985547 -->
Artık yöneticiler, [TeamViewer](../remote-actions/teamviewer-support.md)’a bağlanıp iOS ve macOS cihazlarla bir ekran paylaşma oturumu başlatabilir. iPhone, iPad ve macOS kullanıcıları, diğer herhangi bir masaüstü veya mobil cihazla ekranlarını canlı olarak paylaşabilecek. 

#### <a name="multiple-exchange-connector-support---2070451---"></a>Birden çok Exchange Connector desteği<!-- 2070451 -->
Artık kiracı başına tek bir Microsoft Intune Exchange Connector’la sınırlı değilsiniz. Intune, Intune koşullu erişimini birden çok şirket içi Exchange kuruluşu ile ayarlayabilmeniz için artık birden çok Exchange Bağlayıcısı desteklemektedir.

Intune şirket içi Exchange bağlayıcısıyla, cihazın Intune'a kayıtlı olup olmadığına ve Intune cihaz uyumluluk ilkelerine uyup uymadığına bağlı olarak şirket içi Exchange posta kutularınıza cihaz erişimini ayarlayabilirsiniz. Bağlayıcıyı ayarlamak için, Intune şirket içi Exchange bağlayıcısını Azure portalından indirir ve Exchange kuruluşunuzdaki bir sunucuya yüklersiniz. Microsoft Intune panosunda **Şirket içi erişim**'i seçin ve ardından **Kurulum**'un altında **Exchange ActiveSync bağlayıcısı**'nı seçin. Exchange şirket içi bağlayıcısını indirin ve Exchange kuruluşunuzdaki bir sunucuya yükleyin. Artık kiracı başına tek Exchange bağlayıcısıyla sınırlı olmadığınıza göre, başka Exchange kuruluşlarınız varsa her ek Exchange kuruluşu için aynı süreci izleyip bağlayıcı indirebilir ve yükleyebilirsiniz.

#### <a name="new-device-hardware-detail-ccid---2156657---"></a>Yeni cihaz donanım ayrıntısı: CCıD<!-- 2156657 -->
Çip Kartı Arabirim Cihazı (CCID) bilgileri şimdi her cihaza eklendi. Bunu görmek için, **Cihazlar** > **Tüm cihazlar**'ı seçin, bir cihaz belirtin, **Donanım**'ı seçin ve **Ağ ayrıntıları**>'nın altına bakın.

#### <a name="assign-all-users-and-all-devices-as-scope-groups---2196803---"></a>Tüm kullanıcıları ve tüm cihazları kapsam grupları olarak atama<!-- 2196803 -->
Şimdi tüm kullanıcıları, tüm cihazları ve tüm kullanıcılar ile tüm cihazları kapsam gruplarına atayabilirsiniz. Bunu yapmak için **Intune rolleri** > **Tüm roller** > **İlke ve profil yöneticisi** > **Atamalar** > atama seçin > **Kapsam (gruplar)** öğesini seçin.

#### <a name="udid-information-now-included-for-ios-and-macos-devices---2219806---"></a>Şimdi iOS ve macOS cihazlar için UDID bilgileri eklendi<!-- 2219806 -->
iOS ve macOS cihazlarının Benzersiz Cihaz Tanımlayıcısını (UDID) görmek için, **Cihazlar** > **Tüm cihazlar** > cihaz seçin > **Donanım**'a gidin. UDID yalnızca şirket cihazları için sağlanır (şirket cihazları **Cihazlar** > **Tüm cihazlar** > bir cihaz seçin > **Özellikler** > **Cihaz sahipliği** altında ayarlanır).

### <a name="intune-apps"></a>Intune uygulamaları

#### <a name="improved-troubleshooting-for-app-installation---928990---"></a>Uygulama yüklemesi için geliştirilmiş sorun giderme<!-- 928990 -->
Microsoft Intune MDM ile yönetilen cihazlarda bazen uygulama yüklemeleri başarısız olabilir. Bu uygulamaların yüklemesi başarısız olduğunda, başarısızlık sebebini anlamak ve sorunu gidermek zor olabilir. Uygulama Sorun Giderme özelliklerimizin bir Genel Önizlemesini yayınlıyoruz. Tüm cihazlarda **Yönetilen Uygulamalar** adlı yeni bir düğüm göreceksiniz. Bu düğümde Intune MDM yoluyla teslim edilen uygulamalar listelenir. Burada uygulama yükleme durumlarının bir listesini bulacaksınız. Bir uygulamayı seçtiğinizde, o uygulamaya özel sorun giderme görünümünü açmış olacaksınız. Sorun giderme görünümünde uygulamanın oluşturulma, değiştirilme, hedeflenme ve cihaza teslim edilme tarihleri gibi uçtan uca yaşam döngüsünü bulabileceksiniz. Buna ek olarak, uygulama yüklemesinin başarısız olması durumunda size bir hata kodu ve hatanın sebebiyle ilgili yardım olacak bir ileti sunulacak. 

#### <a name="intune-app-protection-policies-and-microsoft-edge---1818968---"></a>Intune uygulama koruma ilkeleri ve Microsoft Edge<!-- 1818968 -->
Mobil cihazlar (iOS ve Android) için Microsoft Edge tarayıcısı, artık Microsoft Intune uygulama koruma ilkelerini destekliyor. Şirket Azure AD hesaplarıyla Microsoft Edge uygulamasında oturum açan iOS ve Android cihazı kullanıcıları, Intune tarafından korunacak. iOS cihazlarında **Web içeriği için yönetilen tarayıcı iste** ilkesi, Microsoft Edge yönetildiğinde kullanıcıların bu tarayıcıda bağlantı açmasına olanak tanıyacak.

<!-- ########################## -->
## <a name="may-2018"></a>Mayıs 2018

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="configuring-your-app-protection-policies---2144597-part-2---"></a>Uygulama koruma ilkelerinizi yapılandırma<!-- 2144597 Part 2 -->

Azure portalında, Intune Uygulama Koruması hizmet dikey penceresine gitmek yerine artık yalnızca Intune’a gidersiniz. Intune içinde artık uygulama koruma ilkeleri için yalnızca bir konum bulunur. Tüm uygulama koruma ilkelerinizin Intune’da **Uygulama koruma ilkeleri** altındaki **Mobil uygulama** dikey penceresinde olduğuna dikkat edin. Bu tümleştirme, bulut yönetim idaresini basitleştirmenize yardımcı olur. Tüm uygulama koruma ilkelerinin zaten Intune’da olduğunu ve önceden yapılandırılan tüm ilkelerinizi değiştirebileceğinizi unutmayın. Intune uygulama Ilkesi koruması (uygulama) ve koşullu erişim (CA) ilkeleri artık **Microsoft Intune** dikey penceresindeki **Yönet** bölümünde veya Içindeki **güvenlik** bölümünde bulunan **koşullu erişim**aşamasındadır.  **Azure Active Directory** dikey pencere. Koşullu erişim ilkelerini değiştirme hakkında daha fazla bilgi için bkz. [Azure Active Directory Koşullu erişim](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal). Daha fazla bilgi için bkz. [Uygulama koruma ilkeleri nedir?](../apps/app-protection-policy.md)

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="require-installation-of-policies-apps-certificate-and-network-profiles---1553555---"></a>İlkelerin, uygulamaların, sertifika ve ağ profillerinin yüklenmesini gerektirme<!-- 1553555 -->
Intune, AutoPilot cihazlar sağlanırken ilkeleri, uygulamaları ve sertifika ve ağ profillerini yükleyene kadar yöneticiler son kullanıcıların Windows 10 RS4 masaüstüne erişimini engelleyebilecek. Daha fazla bilgi için bkz. [Kayıt durum sayfası ayarlama](../enrollment/windows-enrollment-status.md).

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="samsung-knox-mobile-enrollment-support--1112863--"></a>Samsung Knox mobil kayıt desteği<!--1112863-->
Intune’u Samsung Knox Mobil Kayıt (KME) ile birlikte kullanarak çok sayıda şirkete ait Android cihazları kaydedebilirsiniz. WiFi veya hücresel ağ kullanan kullanıcılar, cihazlarını ilk kez açtıklarında yalnızca birkaç dokunuşla kayıt yapabilir. Knox Dağıtım Uygulaması’nı kullanırken Bluetooth veya NFC yoluyla cihazlar kaydedilebilir. Daha fazla bilgi için bkz. [Android cihazları Samsung’un Knox Mobil Kayıt özelliğini kullanarak otomatik kaydetme](../enrollment/android-samsung-knox-mobile-enroll.md).

### <a name="monitor-and-troubleshoot"></a>İzleme ve sorun giderme 

#### <a name="requesting-help-in-the-company-portal-for-windows-10---1874137---"></a>Windows 10 için Şirket Portalı uygulamasında yardım isteme<!-- 1874137 -->
Kullanıcı bir sorun hakkında yardım almak için iş akışı başlattığında Windows 10 için Şirket Portalı uygulaması artık uygulama günlüklerini doğrudan Microsoft’a gönderecek. Böylece Microsoft’a bildirilen sorunların giderilmesi ve çözülmesi daha kolay olacak.

<!-- ########################## -->
## <a name="april-2018"></a>Nisan 2018

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="passcode-support-for-mam-pin-on-android---1438086---"></a>Android’de MAM PIN’i için geçiş kodu desteği<!-- 1438086 -->

Intune yöneticileri, sayısal MAM PIN’i yerine geçiş kodu zorlamak için bir uygulama başlatma gereksinimi ayarlayabilir. Bu gereksinim ayarlanırsa kullanıcının, MAM etkin uygulamalara erişim almadan önce bir geçiş kodu ayarlaması ve istendiğinde bunu kullanması gerekir. Geçiş kodu, en az bir özel karakter veya büyük/küçük harf içeren sayısal PIN’dir. Intune, sayısal PIN’e benzer bir şekilde geçiş kodunu destekler. Uzunluk alt sınırı belirler ve yönetici konsolunda karakter ile dizi tekrarlarına izin verir. Bu özellik, Android’de Şirket Portalı’nın en son sürümünü gerektirir. Bu özellik, iOS için zaten kullanılabilir durumdadır.

#### <a name="line-of-business-lob-app-support-for-macos---1473977---"></a>macOS için iş kolu (LOB) uygulamaları desteği<!-- 1473977 -->
Microsoft Intune, macOS LOB uygulamalarını Azure portalından yükleme olanağı sağlayacak. GitHub’da bulunan araç tarafından ön işlemden geçtikten sonra macOS LOB uygulamasını Intune’a ekleyebileceksiniz. Azure portalının **Intune** dikey penceresinden **İstemci uygulamaları**’nı seçin. **İstemci uygulamaları** dikey penceresinde **Uygulamalar** > **Ekle**’yi seçin. **Uygulama Ekle** dikey penceresinde, **İş kolu uygulaması**’nı seçin. 

#### <a name="built-in-all-users-and-all-devices-group-for-android-enterprise-work-profile-app-assignment---1813073---"></a>Android Kurumsal iş profili uygulama ataması için yerleşik Tüm Kullanıcılar ve Tüm Cihazlar Grubu<!-- 1813073 -->
Android Kurumsal iş profili uygulama ataması için yerleşik **Tüm Kullanıcılar** ve **Tüm Cihazlar** gruplarından yararlanabilirsiniz. Daha fazla bilgi için bkz. [Microsoft Intune’da uygulama atamalarını dahil etme ve dışlama](../apps/apps-inc-exl-assignments.md).

#### <a name="intune-will-reinstall-required-apps-that-are-uninstalled-by-users---1947010---"></a>Intune, kullanıcılar tarafından kaldırılan gerekli uygulamaları yeniden yükleyecek<!-- 1947010 -->
Son kullanıcı gerekli bir uygulamayı kaldırırsa Intune, 7 günlük yeniden değerlendirme döngüsünü beklemek yerine 24 saat içerisinde bu uygulamayı otomatik olarak yeniden yükler.

#### <a name="update-where-to-configure-your-app-protection-policies---2144597---"></a>Uygulama koruma ilkelerinizi nerede yapılandıracağınızı güncelleştirme<!-- 2144597 -->

Azure portalındaki Microsoft Intune hizmetinde sizi geçici olarak **Intune Uygulama Koruma** hizmeti dikey penceresinden **Mobil uygulama** dikey penceresine yeniden yönlendireceğiz. Tüm uygulama koruma ilkelerinizin zaten Intune’da uygulama yapılandırması altındaki **Mobil uygulama** dikey penceresinde olduğuna dikkat edin. Intune Uygulama Koruması yerine yalnızca Intune’a gideceksiniz. Nisan 2018’de yeniden yönlendirmeyi durduracak ve **Intune Uygulama Koruması** hizmeti dikey penceresini tamamen kaldıracağız, böylece Intune’daki uygulama koruma ilkeleri yalnızca bir konumda bulunacak. 

**Bu değişiklik beni nasıl etkileyecek?**
Bu değişiklik, hem tek başına Intune müşterilerini hem de karma (Configuration Manager ile Intune) müşterileri etkileyecek. Bu tümleştirme, bulut yönetim idaresini basitleştirmenize yardımcı olacak.

**Bu değişikliğe hazırlanmak için ne yapmam gerek?**
Lütfen **Intune Uygulama Koruması** yerine **Intune**’u sık kullanılan olarak etiketleyin ve Intune içerisindeki **Mobil** uygulama dikey penceresinde bulunan Uygulama koruma ilkesi iş akışını inceleyin. Kısa bir süreliğine yenilen yönlendireceğiz ancak daha sonra **Uygulama Koruma** dikey penceresini kaldıracağız. Tüm uygulama koruma ilkelerinin zaten Intune 'da olduğunu ve koşullu erişim ilkelerinizin herhangi birini değiştirebileceğinizi unutmayın. Koşullu erişim ilkelerini değiştirme hakkında daha fazla bilgi için bkz. [Azure Active Directory Koşullu erişim](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal). Daha fazla bilgi için bkz. [Uygulama koruma ilkeleri nedir?](../apps/app-protection-policy.md) 

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="device-profile-chart-and-status-list-show-all-devices-in-a-group---1449153---"></a>Cihaz profil grafiği ve durum listesi bir gruptaki tüm cihazları gösterir<!-- 1449153 -->
Bir cihaz profili yapılandırdığınızda (**Cihaz yapılandırması** > **Profiller**), iOS gibi bir cihaz profili seçersiniz. Bu profili, iOS ve iOS olmayan cihazlar barındıran bir gruba atarsınız. Grafikteki sayı, profilin uygulandığı iOS *ve* iOS olmayan cihazları gösterir (**Cihaz yapılandırması** > **Profiller** > mevcut bir profili seçin > **Genel bakış**). **Genel bakış** sekmesinde grafiği seçtiğinizde, **Cihaz durumu** yalnızca gruptaki iOS cihazları değil, tüm cihazları listeler. 

Bu güncelleştirme ile grafik (**Cihaz yapılandırması** > **Profiller** > mevcut bir profili seçin > **Genel bakış**) yalnızca belirli bir cihaz profili sayısını gösterir. Örneğin yapılandırma cihaz profili iOS cihazlarda geçerliyse grafik yalnızca iOS cihaz sayısını gösterecek. Grafik seçilip **Cihaz durumu** açıldığında yalnızca iOS cihazlar listelenecek.

Bu güncelleştirme hazırlanırken kullanıcı grafiği geçici olarak kaldırılmıştır. 

#### <a name="always-on-vpn-for-windows-10--1333666---"></a>Windows 10 için Her Zaman Açık VPN<!--1333666 -->

Şu anda [Her Zaman Açık](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-auto-trigger-profile#always-on), OMA-URI kullanarak oluşturulmuş özel bir sanal özel ağ (VPN) profili ile Windows 10 cihazlarda kullanılabiliyor.

Bu güncelleştirmeyle yöneticiler, Windows 10 VPN profilleri için Her Zaman Açık’ı doğrudan Azure portalındaki Intune’da etkinleştirebilir. Her Zaman Açık VPN profilleri şu durumlarda otomatik olarak bağlanacak:

- Kullanıcılar cihazlarında oturum açtığında
- Cihazdaki ağ değiştiğinde
- Cihaz ekranı kapandıktan sonra yeniden açıldığında

#### <a name="new-printer-settings-for-education-profiles---1308900---"></a>Eğitim profilleri için yeni yazıcı ayarları<!-- 1308900 -->

Eğitim profilleri için yeni ayarlar, **Yazıcılar** kategori: **Yazıcılar**, **Varsayılan yazıcı**, **Yeni yazıcı ekle** altında sağlanır.

#### <a name="show-caller-id-in-personal-profile---android-enterprise-work-profile--1098984---"></a>Kişisel profilde arayan kimliğini gösterme - Android Kurumsal iş profili<!--1098984 -->
Bir cihazda kişisel profil kullanan son kullanıcılar, işle ilgili bir kişiden gelen aramalarda arayan kimliğini göremeyebilir. 

Bu güncelleştirme ile **Android Kurumsal** > **Cihaz kısıtlamaları** > **İş profili ayarları** kısmına bunun için yeni bir ayar geldi:
- Kişisel profilde iş kişisi arayan kimliğini görüntüleme

Etkinleştirildiğinde (yapılandırılmadığında), iş kişisi arayan ayrıntıları kişisel profilde görüntülenir. Engellendiğinde ise iş kişisi arayan numarası kişisel profilde görüntülenmez. 

Şunlar için geçerlidir: Android OS v6.0 ve üzeri sürümlerde Android iş profili cihazları

#### <a name="new-windows-defender-credential-guard-settings-added-to-endpoint-protection-settings--1102252-----from-1802-and-1804--"></a>Endpoint Protection ayarlarına yeni Windows Defender Credential Guard ayarları eklendi<!--1102252 --><!--from 1802 and 1804-->

Bu güncelleştirmeyle, [Windows Defender Credential Guard](https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard) (**Cihaz yapılandırması** > **Profiller** > **Endpoint Protection**) aşağıdaki ayarları içerir: 

- **Windows Defender Credential Guard**: Credential Guard'ı sanallaştırma tabanlı güvenlikle açar. Bu özelliğin etkinleştirilmesi, **Güvenli Önyükleme ile Platform Güvenlik Düzeyi** ve **Sanallaştırma Tabanlı Güvenlik** ayarının her ikisi de etkinleştirildiğinde bir sonraki önyüklemede kimlik bilgilerinin korunmasına yardımcı olur. Şu seçenekler mevcuttur:
  - **Devre Dışı**: Credential Guard daha önce **Kilitsiz etkin**" seçeneğiyle açıldıysa, Credential Guard'ı uzaktan kapatır.

  - **UEFI kilidi ile etkin**: Credential Guard’ın kayıt defteri anahtarı veya Grup İlkesi kullanılarak devre dışı bırakılamamasını sağlar. Bu ayarı kullandıktan sonra Credential Guard'ı devre dışı bırakmak için, Grup İlkesi'ni "Devre Dışı" olarak ayarlamalısınız. Ardından, fiziksel olarak kullanıcısı olan her bilgisayardan güvenlik işlevselliğini kaldırın. Bu adımlar UEFI'de kalıcı olan yapılandırmayı temizler. UEFI yapılandırması devam ettiği sürece, Credential Guard etkindir.

  - **Kilitsiz etkin**: Credential Guard’ın Grup İlkesi kullanılarak uzaktan devre dışı bırakılmasına olanak tanır. Bu ayarı kullanan cihazların en az Windows 10 (Sürüm 1511) çalıştırıyor olması gerekir.

Credential Guard yapılandırılırken aşağıdaki bağımlı teknolojiler otomatik olarak etkinleştirilir: 

- **Sanallaştırma Tabanlı Güvenliği (VBS) etkinleştir**: Bir sonraki yeniden başlatmada sanallaştırma tabanlı güvenliği (VBS) açar. Sanallaştırma tabanlı güvenlik, güvenlik hizmetlerine destek sağlamak için Windows Hiper Yöneticisi'ni kullanır ve Güvenli Önyükleme gerektirir.
- **Doğrudan Bellek Erişimi (DMA) ile Güvenli Önyükleme**: VBS'yi Güvenli Önyükleme ve doğrudan bellek erişimi ile açar. DMA koruması, donanım desteği gerektirir ve yalnızca düzgün yapılandırılmış cihazlarda etkinleştirilir. 

#### <a name="use-a-custom-subject-name-on-scep-certificate---2064190---"></a>SCEP sertifikasında özel bir konu adı kullanma<!-- 2064190 -->
Bir SCEP sertifika profilinde özel bir konuda **OnPremisesSamAccountName** ortak adını kullanabilirsiniz. Örneğin `CN={OnPremisesSamAccountName})` kullanabilirsiniz.

#### <a name="block-camera-and-screen-captures-on-android-enterprise-work-profiles---1098977---"></a>Android Kurumsal iş profillerinde kamera ve ekran yakalamayı engelleme<!-- 1098977 -->
Android cihazlar için cihaz kısıtlamaları yapılandırırken iki yeni engelleme özelliği kullanılabilir: 
- Kamera: Cihazdaki tüm kameralara erişimi engeller
- Ekran yakalama: Ekran yakalamayı ve güvenli bir video çıkışına sahip olmayan görüntü cihazlarında gösterilen içeriği engeller

Android Kurumsal iş profili cihazlarda geçerlidir.

#### <a name="use-cisco-anyconnect-client-for-ios---1333708---"></a>iOS için Cisco AnyConnect istemcisini kullanma<!-- 1333708 -->

iOS için yeni bir VPN profili oluştururken, şimdi iki seçenek vardır: **Cisco AnyConnect** ve **Cisco Eski AnyConnect**. Cisco AnyConnect profilleri 4.0.7x ve daha yeni sürümleri destekler. Mevcut iOS Cisco AnyConnect VPN profilleri **Cisco Eski AnyConnect** olarak etiketlenir ve Cisco AnyConnect 4.0.5x ve daha eski sürümlerle bugün olduğu gibi çalışmaya devam eder.

> [!NOTE]
> Bu değişiklik yalnızca iOS'ye yöneliktir. Android, Android Kurumsal iş profilleri ve macOS platformlarında yine tek Cisco AnyConnect seçeneği olacaktır.


### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="new-enrollment-steps-for-users-on-devices-with-macos-high-sierra-10132--1734567---"></a>macOS High Sierra 10.13.2+ cihazların kullanıcıları için yeni kayıt adımları<!--1734567 -->
macOS High Sierra 10.13.2, “Kullanıcı Onaylı” MDM kaydı kavramını sundu. Onaylı kayıtlar, Intune’un güvenlik açısından hassas bazı ayarları yönetmesine izin verir. Daha fazla bilgi için Apple’ın destek belgelerine bakın: https://support.apple.com/HT208019.

macOS Şirket Portalı kullanarak kaydedilen cihazlar, son kullanıcı Sistem Tercihleri’ni açıp kendisi onay sağlamadığı sürece “Kullanıcı Onaylı Değil” olarak değerlendirilir. Bu nedenle macOS Şirket Portalı, macOS 10.13.2 ve üzeri cihazlardaki kullanıcıları artık kayıt işleminin sonunda kayıtlarını kendileri onaylamaları için yönlendiriyor. Kayıtlı bir cihaz, kullanıcı onaylı hale gelirse Intune yönetici konsolu bunu rapor eder.

#### <a name="jamf-enrolled-macos-devices-can-now-register-with-intune---2370684---"></a>Jamf'ye kayıtlı macOS cihazları artık Intune ile kaydedilebilir<!-- 2370684 -->
macOS şirket portalının 1.3 ve 1.4 sürümleri Jamf cihazlarını Intune ile başarılı bir şekilde kaydedemiyordu. macOS portalının 1.4.2 sürümünde bu sorun çözüldü.

#### <a name="updated-help-experience-in-company-portal-app-for-android---1631531---"></a>Android için Şirket Portalı uygulamasında güncelleştirilmiş yardım deneyimi<!-- 1631531 -->
Android platformuna yönelik en iyi uygulamalarla uyumlu olacak şekilde, Android için Şirket Portalı uygulamasında yardım deneyimini güncelleştirdik. Artık kullanıcılar uygulamada bir sorunla karşılaştıklarında **Menü** > **Yardım**’a dokunarak şunları yapabilir:
- Microsoft’a tanılama günlükleri yükleme.
- Sorunu açıklayan ve olay kimliğini içeren bir e-postayı şirket destek bölümünden birine gönderme.  

Güncelleştirilmiş deneyimi görmek için [E-posta ile günlük gönder](/intune-user-help/send-logs-to-your-it-admin-by-email-android) ve [Microsoft’a hata gönder](/intune-user-help/send-logs-to-microsoft-android)’e gidin.


#### <a name="new-enrollment-failure-trend-chart-and-failure-reasons-table---1471783---"></a>Yeni kayıt hatası eğilim grafiği ve hatanın nedenleri tablosu<!-- 1471783 -->
Kayıt Genel Bakış sayfasında kayıt hatalarının eğilimini ve hataların ilk beş sebebini görüntüleyebilirsiniz. Grafiğe veya tabloya tıklayarak sorun giderme tavsiyeleri ve düzeltme önerileri almak üzere ayrıntıları inceleyebilirsiniz.


### <a name="device-management"></a>Cihaz yönetimi

#### <a name="advanced-threat-protection-atp-and-intune-are-fully-integrated---1629303---"></a>Gelişmiş Tehdit Koruması (ATP) ve Intune tamamen tümleştirilmiştir<!-- 1629303 -->

[Gelişmiş Tehdit Koruması (ATP)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/dashboard-windows-defender-advanced-threat-protection), Windows 10 cihazların risk düzeyini gösterir. Windows Defender Güvenlik Merkezi'nde (ATP portalı), Microsoft Intune'a bir bağlantı oluşturabilirsiniz. Oluşturulduktan sonra, kabul edilebilir tehdit düzeyini saptamak için bir Intune uyumluluk ilkesi kullanılır. Tehdit düzeyi aşılırsa, bir Azure Active Directory (AD) koşullu erişim ilkesi daha sonra kuruluşunuzdaki farklı uygulamalara erişimi engelleyebilir.

Bu özellik Windows 10 cihazlarınızda ATP'nin dosyaları taramasına, tehditleri algılamasına ve riskleri raporlamasına olanak tanır.

Bkz. [Intune 'Da koşullu ERIŞIMLE ATP 'Yi etkinleştirme](../protect/advanced-threat-protection.md).

#### <a name="support-for-user-less-devices---1637553---"></a>Kullanıcısız cihazlar için destek<!-- 1637553 -->
Intune, Microsoft Surface Hub gibi bir kullanıcısız cihazda uyumluluk değerlendirme işlevini destekler. Uyumluluk ilkesi, belirli cihazları hedefleyebilir. Böylece ilişkili kullanıcısı olmayan cihazlar için uyumluluk (ve uyumsuzluk) belirlenebilir.

#### <a name="delete-autopilot-devices---1713650---"></a>Autopilot cihazlarını silme<!-- 1713650 -->
Intune yöneticileri, [Autopilot cihazlarını silebilir](../enrollment/enrollment-autopilot.md#delete-autopilot-devices).

#### <a name="improved-device-deletion-experience--1832333---"></a>Geliştirilmiş cihaz silme deneyimi<!--1832333 -->
Artık [bir cihazı Intune’dan silmeden](../remote-actions/devices-wipe.md#delete-devices-from-the-intune-portal) önce şirket verilerini kaldırmanız veya cihazı fabrika ayarlarına sıfırlamanız istenmez.

Yeni deneyimi görmek için Intune’da oturum açın ve şunları seçin: **Cihazlar** > **Tüm cihazlar** > cihazın adı > **Sil**.

Yine de onayı silmek/devre dışı bırakmak istiyorsanız **Sil** demeden önce standart yaşam döngüsü yolunu izleyip **Şirket verilerini kaldır** ve **Fabrika Sıfırlaması** seçeneklerini kullanabilirsiniz. 

#### <a name="play-sounds-on-ios-when-in-lost-mode---1947769---"></a>Kayıp modundayken iOS cihazda ses çalma<!-- 1947769 -->
Denetimli iOS cihazları, Mobil Cihaz Yönetimi (MDM) [Kayıp Modu](../remote-actions/device-lost-mode.md)’ndayken bir [ses çalabilirsiniz](../remote-actions/device-locate.md#activate-lost-mode-sound-alert-on-an-ios-device) (**Cihazlar** > **Tüm cihazlar** > bir iOS cihaz seçin > **Genel Bakış** > **Diğer**). Ses, cihaz Kayıp modundan çıkarılana veya kullanıcı sesi cihazda devre dışı bırakana kadar çalmaya devam eder. iOS 9.3 ve üzeri cihazlarda geçerlidir.

#### <a name="block-or-allow-web-results-in-searches-made-on-an-intune-device--1972804--"></a>Intune cihazında yapılan aramalarda web sonuçlarını engelleme veya bu sonuçlara izin verme<!--1972804-->

Yöneticiler şimdi cihazda yapılan aramalarda web sonuçlarını engelleyebilir.

#### <a name="improved-error-messaging-for-apple-mdm-push-certificate-upload-failure---2172331---"></a>Apple MDM Anında İletme Sertifikası karşıya yükleme başarısızlığı için iyileştirilmiş hata iletisi<!-- 2172331 -->

Hata iletisi, mevcut bir MDM sertifikası yenilenirken aynı Apple kimliğinin kullanılması gerektiğini açıklar.

#### <a name="test-the-company-portal-for-macos-on-virtual-machines---2216679---"></a>Sanal makinelerde macOS için Şirket Portalı'nı test etme<!-- 2216679 -->

BT yöneticilerinin Parallels Desktop ve VMware Fusion'daki sanal makinelerde macOS için Şirket Portalı uygulamasını test etmelerine yardımcı olacak kılavuzlar yayımladık. [Sanal macOS makinelerini test için kaydetme](../enrollment/macos-enroll.md#enroll-virtual-macos-machines-for-testing) başlığı altında daha fazla bilgi bulabilirsiniz.

### <a name="intune-apps"></a>Intune uygulamaları

#### <a name="user-experience-update-for-the-company-portal-app-for-ios--1412866---"></a>iOS için Şirket Portalı uygulamasında kullanıcı deneyimi güncelleştirmesi<!--1412866 -->
iOS için Şirket Portalı uygulamasına büyük bir kullanıcı deneyimi güncelleştirmesi yayımladık. Güncelleştirme, modern bir görünüm ve his sağlayan yepyeni bir görsel tasarım sunmaktadır. Uygulamanın işlevselliğini korurken kullanılabilirliğini ve erişilebilirliğini artırdık.  

Şunları da göreceksiniz:
- iPhone X desteği.
- Kullanıcıların zamandan tasarruf etmesi için daha hızlı uygulama açma ve yükleme yanıtları.
- Kullanıcılara en güncel durum bilgilerini sağlamak için ek ilerleme çubukları.
- Herhangi bir sorunla karşılaşıldığında bunun daha kolay bildirilmesi için günlükleri karşıya yükleme işleminde iyileştirme.  

Güncelleştirilmiş görünümü görmek için [Uygulama kullanıcı arabirimindeki yenilikler](../whats-new-app-ui.md)’e gidin.

#### <a name="protect-on-premises-exchange-data-using-intune-app-and-ca---1056954---"></a>Intune APP ve CA kullanarak şirket içi Exchange verilerini koruma<!-- 1056954 -->
Şirket içi Exchange verilerine erişimi Outlook Mobile ile korumak için artık Intune Uygulama İlke Koruması (APP) ve Koşullu Erişim (CA) kullanabilirsiniz. Azure portalına bir uygulama koruma ilkesi eklemek veya ilkeyi değiştirmek için **Microsoft Intune** > **İstemci uygulamaları** > **Uygulama koruma ilkeleri**’ni seçin. Bu özelliği kullanmadan önce [iOS ve Android için Outlook gereksinimlerini](https://technet.microsoft.com/library/mt846639(v=exchg.160).aspx) karşıladığınızdan emin olun.


### <a name="user-interface"></a>Kullanıcı arabirimi

#### <a name="improved-device-tiles-in-the-windows-10-company-portal--2213364---"></a>Windows 10 Şirket Portalı'nda geliştirilmiş cihaz kutucuları<!--2213364 -->

Kutucuklar görme sorunu olan kullanıcılar açısından daha erişilebilir olacak ve ekran okuma araçlarının daha iyi çalışmasını sağlayacak şekilde güncelleştirildi.

#### <a name="send-diagnostic-reports-in-company-portal-app-for-macos---2216677---"></a>macOS için Şirket Portalı uygulamasında tanılama raporu gönderme<!-- 2216677 -->
macOS cihazları için Şirket Portalı uygulaması, kullanıcıların Intune il ilgili hataları raporlama şeklini iyileştirmek için güncelleştirildi. Şirket Portalı uygulamasından çalışanlarınız şunları yapabilir:

- Tanılama raporlarını doğrudan Microsoft geliştirici ekibine gönderme.
- Bir olay kimliğini şirketinizin destek BT ekibine e-posta ile gönderme.

Daha fazla bilgi için bkz. [macOS için hataları gönderme](/intune-user-help/send-errors-macos).

#### <a name="intune-adapts-to-fluent-design-system-in-the-company-portal-app-for-windows-10---1195010---"></a>Intune, Windows 10 için Şirket Portalı uygulamasında Fluent Design System'e uyum sağlar<!-- 1195010 -->
Windows 10 için Intune Şirket Portalı, [Fluent Design System'in gezinti görünümü](https://docs.microsoft.com/windows/uwp/design/basics/navigation-basics) ile güncelleştirildi. Uygulamanın yan tarafı boyunca tüm en üst düzey sayfaların statik, dikey bir listesini göreceksiniz. Sayfaları hızla görüntülemek ve aralarında geçiş yapmak için herhangi bir bağlantıya tıklayın. Bu, Intune'da sürekli daha iyi uyarlanmış, anlayışlı ve tanıdık bir deneyim oluşturma çabalarımız kapsamında göreceğiniz birkaç güncelleştirmeden ilkidir. Güncelleştirilmiş görünümü görmek için [Uygulama kullanıcı arabirimindeki yenilikler](../whats-new-app-ui.md)’e gidin.

<!-- ########################## -->
## <a name="march-2018"></a>Mart 2018

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="alerts-for-expiring-ios-line-of-business-lob-apps-for-microsoft-intune---748789---"></a>Microsoft Intune için süresi dolan iOS iş kolu (LOB) uygulamaları uyarıları<!-- 748789 -->

Azure portalında Intune, süresi dolmak üzere olan iOS iş kolu uygulamaları konusunda sizi uyaracaktır. iOS iş kolu uygulamasının yeni sürümü karşıya yüklenince, Intune süre sonu bildirimini uygulama listesinden kaldırır. Bu süre dolumu bildirimi yalnızca yeni yüklenmiş iOS iş kolu uygulamaları için etkin olacaktır. iOS LOB uygulama sağlama profilinin süresinin dolmasına 30 gün kala bir uyarı görünür. Süre dolduğunda uyarı, Süresi Doldu olarak değişir.

#### <a name="customize-your-company-portal-themes-with-hex-codes--1049561---"></a>Şirket Portalı temalarınızı onaltılık kodlarla özelleştirme<!--1049561 -->

Onaltılık kodlar kullanarak Şirket Portalı uygulamalarında tema rengini özelleştirebilirsiniz. Onaltılık kodunuzu girdiğinizde Intune, metin rengi ile arka plan rengi arasında en yüksek düzeyde kontrast sağlayan metin rengini belirler. **İstemci uygulamaları** > **Şirket Portalı**’nda metin renginin ve bu renk ile şirket logonuzun önizlemesini görüntüleyebilirsiniz.

### <a name="including-and-excluding-app-assignment-based-on-groups-for-android-enterprise---1813081---"></a>Android Enterprise için gruplar temelinde uygulama atamasını dahil etme ve hariç tutma<!-- 1813081 -->

Android Enterprise (önceki adıyla Android for Work), grupları dahil etme ve hariç tutmayı destekler ancak önceden oluşturulmuş **Tüm Kullanıcılar** ve **Tüm Cihazlar** yerleşik gruplarını desteklemez. Daha fazla bilgi için bkz. [Microsoft Intune’da uygulama atamalarını dahil etme ve dışlama](../apps/apps-inc-exl-assignments.md).


### <a name="device-management"></a>Cihaz yönetimi

### <a name="export-all-devices-into-csv-files-in-ie-microsoft-edge-or-chrome---2258071---"></a>IE, Microsoft Edge veya Chrome’da tüm cihazları CSV dosyalarına aktarma<!-- 2258071 -->
**Cihazlar** > **Tüm cihazlar**’da cihazları CSV biçimli bir listeye **Dışarı Aktarabilirsiniz**. 10.000’den fazla cihazı olan Internet Explorer (IE) kullanıcıları, cihazlarını birden çok dosyaya başarıyla aktarabilirler. Her dosyada en fazla 10.000 cihaz bulunur.

30.000’den fazla cihazı olan Microsoft Edge ve Chrome kullanıcıları, cihazlarını birden çok dosyaya başarıyla aktarabilirler. Her dosyada en fazla 30.000 cihaz bulunur.

[Cihazları yönet](../remote-actions/device-management.md), yönettiğiniz cihazlarla ne yapabileceğiniz hakkında daha fazla ayrıntı sağlar.

#### <a name="new-security-enhancements-in-the-intune-service----1637539---"></a>Intune hizmetinde yeni güvenlik geliştirmeleri <!-- 1637539 -->   

Tek başına Intune müşterilerinin hiçbir ilke atanmamış cihazlarını **Uyumlu** (güvenlik özelliği kapalı) veya **Uyumsuz** (güvenlik özelliği açık) olarak değerlendirmesine imkan veren bir iki durumlu düğme sunduk. Böylece yalnızca cihaz uyumluluğu değerlendirildikten sonra kaynaklara erişim verilmesi sağlanacaktır.

Bu özellik, önceden atanmış uyumluluk ilkeleriniz olup olmadığına bağlı olarak sizi farklı etkileyecektir.

- Cihazlarına hiçbir uyumluluk ilkesi atanmamış yeni veya mevcut bir hesabınız varsa durum otomatik olarak **Uyumlu** şeklinde ayarlanacaktır. Konsolda bu özellik, varsayılan olarak kapalıdır. Son kullanıcılar bundan etkilenmez.
- Cihazlarına uyumluluk ilkesi atanmış mevcut bir hesabınız varsa durum otomatik olarak **Uyumsuz** şeklinde ayarlanacaktır. Özellik, Mart güncelleştirmesi dağıtılırken varsayılan olarak açıktır.

Uyumluluk ilkelerini Koşullu Erişim (CA) ile birlikte kullanıyorsanız ve bu özelliği açtıysanız kendisine en az bir uyumluluk ilkesi atanmamış cihazlarınız artık CA tarafından engellenir. Bu cihazlarla ilişkili olup bu zamana kadar e-postaya erişme izni olan kullanıcılar, tüm cihazlara en az bir uyumluluk ilkesi atamadığınız sürece erişimlerini kaybeder.   

Varsayılan ikili durum, Intune hizmeti Mart güncelleştirmeleri ile hemen kullanıcı arabiriminde gösterilmeye başlasa da bu ikili durumun doğrudan uygulanmadığına dikkat edin. Hesabınızda çalışan bir ikili durum olana kadar durumda yaptığınız değişiklikler cihaz uyumluluğunu etkilemez. Hesabınızı ayarladığımızda İleti merkezi yoluyla sizi bilgilendireceğiz. Bu işlem, Intune hizmetiniz Mart sürümüne güncelleştirildikten sonra birkaç gün sürebilir.

**Ek bilgiler**: [https://aka.ms/compliance_policies](https://aka.ms/compliance_policies)

#### <a name="enhanced-jailbreak-detection---846515---"></a>Gelişmiş jailbreak algılama<!-- 846515 -->

Gelişmiş jailbreak algılama, Intune’un jailbreak uygulanmış cihazları değerlendirme yöntemini geliştiren yeni bir uyumluluk ayarıdır. Ayar, cihazın Intune’a daha sık iade edilmesine neden olur; bu da cihazın konum hizmetlerini kullanır ve pil kullanımını etkiler.

#### <a name="reset-passwords-for-android-o-devices---1238299---"></a>Android O cihazlar için parola sıfırlama<!-- 1238299 -->
İş profiline sahip kayıtlı Android 8.0 cihazlar için parolaları sıfırlayabileceksiniz. Bir Android 8.0 cihaza “Parola sıfırla” isteği gönderdiğinizde cihaz, geçerli kullanıcıya yeni bir cihaz kilidi açma parolası veya yönetilen profil sınaması ayarlar. Parola veya sınama gönderilir ve hemen uygulanır.

#### <a name="targeting-compliance-policies-to-devices-in-device-groups--1307012---"></a>Uyumluluk ilkelerinde cihaz gruplarındaki cihazları hedefleme<!--1307012 -->

Uyumluluk ilkelerinde kullanıcı gruplarındaki kullanıcıları hedefleyebilirsiniz. Bu güncelleştirme ile uyumluluk ilkelerinde cihaz gruplarındaki cihazları hedefleyebilirsiniz. Cihaz gruplarının parçası olarak hedeflenen cihazlar, hiçbir uyumluluk eylemi almayacaktır.

#### <a name="new-management-name-column---1333586---"></a>Yeni Yönetim adı sütunu<!-- 1333586 -->
 Cihazlar dikey penceresine **Yönetim adı** adlı yeni bir sütun eklendi. Bu, aşağıdaki formül temelinde her cihaza atanan, otomatik olarak oluşturulmuş ve düzenlenemez bir addır:
- Tüm cihazlar için varsayılan ad: <username><em><devicetype></em><enrollmenttimestamp>
- Toplu eklenen cihazlar: <PaketKimliği/ProfilKimliği><em><DeviceType></em><EnrollmentTime>

Bu, cihazlar dikey penceresinde isteğe bağlı bir sütundur. Varsayılan olarak sağlanmaz ve bu sütuna yalnızca sütun seçici üzerinden erişilebilir. Cihaz adı bu yeni sütundan etkilenmez.

#### <a name="ios-devices-are-prompted-for-a-pin-every-15-minutes--1550837---"></a>15 dakikada bir iOS cihazlardan PIN istenir<!--1550837 -->
Bir iOS cihaza uyumluluk veya yapılandırma ilkesi uygulandıktan sonra her 15 dakikada bir kullanıcılardan bir PIN ayarlamaları istenir. PIN ayarlanana kadar kullanıcılara bu istem gönderilir.

#### <a name="schedule-your-automatic-updates--1805514---"></a>Otomatik güncelleştirmelerinizi zamanlama<!--1805514 -->
Intune, [Windows Güncelleştirme Halkası ayarları](../protect/windows-update-for-business-configure.md) kullanarak otomatik güncelleştirme yüklemelerini denetlemenize olanak verir. Bu güncelleştirme ile tekrar eden güncelleştirmeleri hafta, gün ve saat olarak zamanlayabilirsiniz.

#### <a name="use-fully-distinguished-name-as-subject-for-scep-certificate--2221763---"></a>SCEP sertifikası için konu olarak tam ayırt edici ad kullanma<!--2221763 -->
Bir SCEP sertifika profili oluşturduğunuzda Konu Adı girersiniz. Bu güncelleştirme ile konu olarak tam ayırt edici ad kullanabilirsiniz. **Konu Adı** için **Özel**’i seçin ve `CN={{OnPrem_Distinguished_Name}}` girin. `{{OnPrem_Distinguished_Name}}` değişkenini kullanmak için [Azure Active Directory (AD)](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) kullanarak `onpremisesdistingishedname` kullanıcı özniteliğini Azure AD’nizle eşitlediğinizden emin olun.

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="enable-bluetooth-contact-sharing---android-for-work--1098983---"></a>Bluetooth kişi paylaşımını etkinleştirme - Android for Work<!--1098983 -->
Varsayılan olarak Android, iş profilindeki kişilerin Bluetooth cihazlarıyla eşitlenmesini önler. Bunun sonucunda iş profili kişileri, Bluetooth cihazlarındaki arayan kimliğinde görüntülenmez.

Bu güncelleştirme ile **Android for Work** > **Cihaz kısıtlamaları** > **İş profili ayarları** kısmına bunun için yeni bir ayar geldi:
- Bluetooth ile kişi paylaşımı

Intune yöneticisi, paylaşıma izin vermek için bu ayarları yapılandırabilir. Bu; bir cihazı, eller serbest kullanım için arayan kimliğini gösteren ve arabada kullanılan bir Bluetooth cihazıyla eşitlerken kullanışlıdır. Etkinleştirildiğinde iş profili kişileri görüntülenir. Etkinleştirilmediğinde iş profili kişileri görüntülenmez.

#### <a name="configure-gatekeeper-to-control-macos-app-download-source---1690459---"></a>macOS uygulama indirme kaynağını denetlemek için Ağ Geçidi Denetleyicisi'ni yapılandırma<!-- 1690459 -->

Uygulamaların nereden indirilebileceğini denetleyerek cihazları uygulamalardan korumak için Ağ Geçidi Denetleyicisini yapılandırabilirsiniz. Yapılandırabileceğiniz indirme kaynakları şunlardır: **Mac App Store**, **Mac App Store ve tanımlanan geliştiriciler** veya **Her Yer**. Ayrıca kullanıcıların bu Ağ Geçidi Denetleyicisi denetimlerini geçersiz kılmak için Control tuşuna tıklayarak uygulama yükleyip yükleyemeyeceklerini de yapılandırabilirsiniz.

Bu ayarlar **Cihaz yapılandırması** -> **Profil oluştur** -> **macOS** -> **Uç nokta koruma** altında bulunabilir.

#### <a name="configure-the-mac-application-firewall---1690461---"></a>Mac uygulaması güvenlik duvarını yapılandırma<!-- 1690461 -->

Mac uygulaması güvenlik duvarını yapılandırabilirsiniz. Bunu kullanarak bağlantıları her bağlantı noktası temelinde değil her uygulama temelinde denetleyebilirsiniz. Güvenlik duvarı korumasının avantajlarından yararlanmanızı kolaylaştırır ve geçerli uygulamalar için açılmış ağ bağlantı noktalarında istenmeyen uygulamaların denetimi ele geçirmesini önlemeye yardımcı olur.

Bu özellik **Cihaz yapılandırması** -> **Profil oluştur** -> **macOS** -> **Uç nokta koruma** altında bulunabilir.

Güvenlik Duvarı ayarını etkinleştirdikten sonra, güvenlik duvarını yapılandırmak için şu iki stratejiyi kullanabilirsiniz:

- Tüm gelen bağlantıları engelleme

   Hedeflenen cihazlar için tüm gelen bağlantıları engelleyebilirsiniz. Bunu yapmayı seçerseniz tüm uygulamalar için gelen bağlantılar engellenir.

- Belirli uygulamalara izin verme veya engelleme

   Belirli uygulamaların gelen bağlantıları almasına izin verebilir veya bunu engelleyebilirsiniz. Ayrıca yoklama isteklerine yönelik yanıtları engellemek için gizli modu da etkinleştirebilirsiniz.

#### <a name="detailed-error-codes-and-messages---1376342---"></a>Ayrıntılı hata kodları ve iletileri<!-- 1376342 -->

Cihaz Yapılandırmanızda, hata kodlarını ve hata iletilerini daha ayrıntılı görebilirsiniz. Bu geliştirilmiş raporlamada ayarlar, bu ayarların durumu ve sorun giderme ayrıntıları gösterilir.

##### <a name="more-information"></a>Daha fazla bilgi

- Tüm gelen bağlantıları engelleme

   Bu, tüm paylaşım hizmetlerinin (Dosya Paylaşımı ve Ekran Paylaşımı gibi) genel bağlantıları almasını engeller. Gelen bağlantıları almasına izin verilen sistem hizmetleri şunlardır:
  - configd - DHCP ve diğer ağ yapılandırma hizmetlerini gerçekleştirir
  - mDNSResponder - Bonjour'u gerçekleştirir
  - Pcoon-IPSec uygular

    Paylaşım hizmetlerini kullanmak için, **Gelen bağlantılar**'ın **Yapılandırılmadı** olarak ayarlandığından emin olun (**Engelle** olarak ayarlanmamalıdır).

- Gizli mod

   Bilgisayarın yoklama isteklerine yanıt vermesini önlemek için bunu etkinleştirin. Bilgisayar, yetkili uygulamalardan gelen istekleri yanıtlamaya devam eder. ICMP (ping) gibi beklenmedik istekler yoksayılır.

#### <a name="disable-checks-on-device-restart--1805490---"></a>Cihazı yeniden başlatma sırasında denetimleri devre dışı bırakma<!--1805490 -->
Intune, size [yazılım güncelleştirmelerini yönetme](../protect/windows-update-for-business-configure.md) denetimi sağlar. Bu güncelleştirme ile <strong>Yeniden başlatma denetimleri</strong> özelliği kullanılabilir ve varsayılan olarak etkindir. Bir cihazı yeniden başlattığınızda yapılan denetimleri (etkin kullanıcılar, pil düzeyleri vb. gibi) atlamak için <strong>Atla</strong>’yı seçin.

#### <a name="new-windows-10-insider-preview-channels-available-for-deployment-rings---1746293---"></a>Yeni Windows 10 Insider Önizleme kanalları dağıtım halkaları için kullanılabilir<!-- 1746293 -->
Artık bir Windows 10 dağıtım halkası seçtiğinizde şu Windows 10 Insider Önizleme bakım kanallarını belirleme seçeneğiniz var:
- Windows Insider derlemesi &#8208; Hızlı
- Windows Insider derlemesi &#8208; Yavaş
- Windows Insider derlemesini yayımlama 

Bu kanallar hakkında daha fazla bilgi için bkz. [Insider Önizleme Derlemelerini Yönetme](https://insider.windows.com/for-business-organization-admin/).   
Intune’da dağıtım kanalları oluşturma hakkında daha fazla bilgi için bkz. [Intune’da yazılım güncelleştirmelerini yönetme](../protect/windows-update-for-business-configure.md).

### <a name="new-windows-defender-exploit-guard-settings---1631893---"></a>Yeni Windows Defender Exploit Guard ayarları<!-- 1631893 -->

Altı yeni <strong>Saldırı Yüzeyi Azaltma</strong> ayarı ve genişletilmiş <strong>Denetimli klasör erişimi: Klasör koruması</strong> işlevleri artık kullanılabilir. Bu ayarlar şurada bulunabilir: Cihaz yapılandırması\Profiller\
Profil oluştur\Endpoint protection\Windows Defender Exploit Guard.

#### <a name="attack-surface-reduction"></a>Saldırı Yüzeyini Azaltma

|Ayar adı  |Ayar seçenekleri  |Description  |
|---------|---------|---------|
|Gelişmiş fidye yazılımı koruması|Etkin, Denetle, Yapılandırılmadı|Agresif fidye yazılımı koruması kullanır.|
|Windows yerel güvenlik yetkilisi alt sisteminden kimlik bilgisi çalma eylemlerine bayrak ekleme|Etkin, Denetle, Yapılandırılmadı|Windows yerel güvenlik yetkilisi alt sisteminden kimlik bilgisi çalma eylemlerine bayrak ekler (lsass.exe).|
|PSExec ve WMI komutlarından işlem oluşturma|Engelle, Denetle, Yapılandırılmadı|PSExec ve WMI komutlarından kaynaklanan işlem oluşturmalarını engeller.|
|USB’den çalışan güvenilmeyen ve imzasız işlemler|Engelle, Denetle, Yapılandırılmadı|USB’den çalışan güvenilmeyen ve imzasız işlemleri engeller.|
|Bir yaygınlık, yaş veya güvenilenler listesi kriterine uymayan yürütülebilir dosyalar|Engelle, Denetle, Yapılandırılmadı|Bir yaygınlık, yaş veya güvenilenler listesi kriterine uymadıkları sürece yürütülebilir dosyaları engeller.|

#### <a name="controlled-folder-access"></a>Denetlenen klasör erişimi

|              Ayar adı               |                                                              Ayar seçenekleri                                                              | Description |
|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|-------------|
| Klasör koruması (zaten uygulanmış) | Yapılandırılmamış, Etkinleştir, Yalnızca denetle (zaten uygulanmış)<br><br> <strong>Yeni</strong><br>Disk değişikliğini engelle, Disk değişikliğini denetle |             |

Dosya ve klasörleri kötü amaçlı uygulamaların yetkisiz değişikliklerinden korur.<br><br>**Etkinleştir**: Güvenilmeyen uygulamaların korumalı klasörlerdeki dosyaları değiştirmesini veya silmesini ve disk kesimlerine yazmasını engeller.<br><br>
**Yalnızca disk değişikliğini engelle**:<br>Güvenilmeyen uygulamaların, disk kesimlerine yazmasını engeller. Güvenilmeyen uygulamalar hala korumalı klasörlerdeki dosyaları değiştirebilir veya silebilir.|

### <a name="intune-apps"></a>Intune uygulamaları

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview---710595---"></a>Azure Active Directory web siteleri, Intune Managed Browser uygulaması gerektirebilir ve Managed Browser’da (Genel Önizleme) Çoklu Oturum Açma’yı destekler<!-- 710595 -->

Azure Active Directory (Azure AD) kullanarak artık mobil cihazlarda web sitelerine erişimi Intune Managed Browser uygulaması ile kısıtlayabilirsiniz. Web sitesi verileri, Managed Browser’da güvende ve son kullanıcının kişisel verilerinden ayrı bir yerde olacaktır. Managed Browser ayrıca Azure AD ile korunan sitelerde Çoklu Oturum Açma işlevlerini de destekleyecektir. Managed Browser’da oturum açmak veya Intune tarafından yönetilen başka bir uygulamanın bulunduğu bir cihazda Managed Browser’ı kullanmak, kullanıcıların kimlik bilgilerini girmelerine gerek kalmaksızın Managed Browser’ın Azure AD ile korunan sitelere erişmesine olanak tanır. Bu özellik, Outlook Web Access (OWA) ve SharePoint Online’ın yanı sıra Azure Uygulama Proxy’si yoluyla erişilen intranet kaynakları gibi diğer kurumsal sitelerde de geçerlidir. Daha fazla bilgi için bkz. [Azure Active Directory Koşullu erişim Içindeki erişim denetimleri](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-controls).

#### <a name="company-portal-app-for-android-visual-updates--976944---"></a>Android için Şirket Portalı uygulaması görsel güncelleştirmeleri<!--976944 -->

Android için Şirket Portalı uygulamasını, Android'in [Materyal Tasarım](https://material.io/) yönergelerine uyacak şekilde güncelleştirdik. Yeni simgelerin resimlerini [Uygulama kullanıcı arabirimindeki yenilikler](../whats-new-app-ui.md) makalesinde görebilirsiniz.

#### <a name="company-portal-enrollment-improved---1874230-eeready--"></a>Şirket Portalı kaydı geliştirildi<!-- 1874230 eeready-->
Windows 10 derleme 1703’te ve üstünde Şirket Portalı’nı kullanarak cihaz kaydı yapan kullanıcılar, artık uygulamadan çıkmadan kaydın ilk adımını tamamlayabilirler.
#### <a name="hololens-and-surface-hub-now-appear-in-device-lists--1725868---"></a>Artık cihaz listelerinde HoloLens ve Surface Hub gösteriliyor<!--1725868 -->
Intune’a kayıtlı HoloLens ve Surface Hub cihazlarının Android için Şirket Portalı uygulamasına gösterilmesi amacıyla destek ekledik.

#### <a name="custom-book-categories-for-volume-purchase-program-vpp-ebooks---1488911---"></a>Toplu satın alma programı (VPP) eKitapları için Özel Kitap kategorileri<!-- 1488911 -->
Özel eKitap kategorileri oluşturabilir ve VPP eKitaplarını bu özel eKitap kategorilerine ekleyebilirsiniz. Bundan sonra son kullanıcılar yeni oluşturulan eKitap kategorilerini ve bu kategorilere atanmış olan kitapları görebilecek. Daha fazla bilgi için bkz. [Toplu satın alınan uygulama ve kitapları Microsoft Intune ile yönetme](../apps/vpp-apps.md).  

#### <a name="support-changes-for-company-portal-app-for-windows-send-feedback-option---2070166---"></a>Windows için Şirket Portalı’nda geri bildirim gönderme seçeneğinde destek değişiklikleri<!-- 2070166 -->
30 Nisan 2018 tarihinden itibaren Windows için Şirket Portalı uygulamasındaki **Geri Bildirim Gönder** seçeneği, yalnızca Windows 10 Yıldönümü Güncelleştirmesi (1607) ve üzerini çalıştıran cihazlarda kullanılabilecek. Geri bildirim gönderme seçeneği, artık Windows için Şirket Portalı uygulamasını şu sürümlerle birlikte kullanırken desteklenmeyecek:  
- Windows 10, 1507 sürümü  
- Windows 10, 1511 sürümü  
- WVPN profillerinidows Phone 8.1 

Cihazınız Windows 10 RS1 ve üzeri çalıştırıyorsa Store’daki Windows Şirket Portalı uygulamasının en son sürümünü indirin. Desteklenmeyen bir sürüm çalıştırıyorsanız lütfen şu kanallar yoluyla geri bildirim göndermeye devam edin: 
- Windows 10’daki Geri Bildirim Merkezi uygulaması
- E-posta WinCPfeedback@microsoft.com  

#### <a name="new-windows-defender-application-guard-settings---1631890---"></a>Yeni Windows Defender Application Guard ayarları<!-- 1631890 -->

- **Grafik hızlandırmayı etkinleştirme**: Yöneticiler, Windows Defender Application Guard için bir sanal grafik işlemcisi etkinleştirebilir. Bu ayar, CPU’nun vGPU’ya işlenen grafikleri boşaltmasına olanak sağlar. Bu, yoğun grafikli sitelerde çalışırken veya kapsayıcı dahilinde video izlerken performansı iyileştirebilir.

- **SaveFilestoHost**: Yöneticiler, dosyaların kapsayıcıda çalışan Microsoft Edge’den konak dosya sistemine geçmesine izin verebilir. Bunu açmak, kullanıcıların kapsayıcıda çalışan Microsoft Edge’den konak dosya sistemine dosya indirmesine imkan sağlar.

#### <a name="mam-protection-policies-targeted-based-on-management-state---1665993---"></a>Yönetim durumu temelinde hedeflenen MAM koruma ilkeleri<!-- 1665993 -->
MAM ilkelerinin hedefini, cihazın yönetim durumuna bağlı olarak belirleyebilirsiniz:
- **Android cihazlar** - Yönetilmeyen cihazları, Intune’da yönetilen cihazları ve Intune’da yönetilen Android Enterprise Profillerini (eski adıyla Android for Work) hedefleyebilirsiniz.
- **iOS cihazlar** - Yönetilmeyen cihazları (yalnızca MAM) veya Intune’da yönetilen cihazları hedefleyebilirsiniz.

    > [!NOTE]
    > - Bu işlev için iOS desteği, Nisan 2018 içerisinde sunulacak.

Daha fazla bilgi için bkz. [Cihaz yönetim durumuna bağlı olarak uygulama koruma ilkeleri hedefleme](../apps/app-protection-policies.md).

#### <a name="improvements-to-the-language-in-the-company-portal-app-for-windows---1683758---"></a>Windows için Şirket Portalı uygulamasında dil iyileştirmeleri<!-- 1683758 -->
Daha kullanıcı dostu ve şirketinize özgü olabilmesi için Windows 10 için Şirket Portalı’nda dili iyileştirdik. Yaptıklarımızı gösteren bir örnek görüntü için [uygulama kullanıcı arabirimindeki yeniliklere](../whats-new-app-ui.md) bakın.

#### <a name="new-additions-to-our-docs-about-user-privacy---1440709---"></a>Kullanıcı gizliliği belgelerimize yeni eklemeler<!-- 1440709 -->
Kullanıcılarımıza verileri ve gizlilikleri üzerinde daha fazla denetim kazandırma çabalarımızın bir parçası olarak, Şirket Portalı tarafından yerel olarak depolanan verilerin nasıl görüntüleneceğini ve kaldırılacağını açıklayan güncelleştirmeler yayımladık. Bu güncelleştirmeleri bulabileceğiniz yerler şöyledir:

- **Android**: [Android cihazınızı Intune’dan kaldırma](/intune-user-help/unenroll-your-device-from-intune-android)
- **Android, kullanıcı kullanım koşullarını reddettiyse**: [“Kullanım Koşulları”nı reddettiyseniz cihaz yönetiminizi kaldırma](/intune-user-help/unenroll-your-device-from-intune-if-you-declined-terms-of-use-android)
- **iOS**: [iOS cihazınızı Intune’dan kaldırma](/intune-user-help/unenroll-your-device-from-intune-ios)
- **Windows**: [Windows cihazınızı Intune’dan kaldırma](/intune-user-help/unenroll-your-device-from-intune-windows)

<!-- ########################## -->
## <a name="february-2018"></a>Şubat 2018

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts---747685---"></a>Birden çok Apple DEP / Apple School Manager hesabı için Intune desteği<!-- 747685 -->

Intune, artık sayıları 100’e varan farklı [Apple Aygıt Kayıt Programı (DEP)](../enrollment/device-enrollment-program-enroll-ios.md) veya [Apple School Manager](../enrollment/apple-school-manager-set-up-ios.md) hesabından cihazların kaydını destekliyor. Karşıya yüklenen her belirteç kayıt profilleri ve cihazlar için ayrı olarak yönetilebilir. Karşıya yüklenen DEP/School Manager belirteçlerinin her biri için farklı bir kayıt profili otomatik olarak atanabilir. Birden çok School Manager belirteci karşıya yüklenirse, Microsoft School Data Sync ile bir kerede tek bir belirteç paylaşılabilir.

Geçişten sonra, Graph üzerinden Apple DEP veya ASM yönetimi için beta Graph API'leri ve yayımlanan betikler artık çalışmayacak. Yeni beta Graph API'leri geliştirme aşamasındadır ve geçiş sonrasında yayınlanacaktır.

#### <a name="see-enrollment-restrictions-per-user---1634444-eeready-wnready---"></a>Kullanıcı başına kayıt kısıtlamalarına bakın<!-- 1634444 eeready wnready -->
Artık **Sorun Giderme** dikey penceresinde **Atamalar** listesinden **Kayıt kısıtlamaları**’nı seçerek her kullanıcı için geçerli olan [kayıt kısıtlamalarını](../enrollment/enrollment-restrictions-set.md) görebilirsiniz.

#### <a name="new-option-for-user-authentication-for-apple-bulk-enrollment---747625-eeready---"></a>Apple toplu kaydında kullanıcı kimlik doğrulaması için yeni seçenek<!-- 747625 eeready -->

> [!NOTE]
> Yeni kiracılar bu seçeneği hemen görecektir. Mevcut kiracılar için ise bu özellik, Nisan ayı içerisinde sunulacaktır. Bu dağıtım tamamlanana kadar, bu yeni özelliklere erişemeyebilirsiniz.

Intune, artık aşağıdaki kayıt yöntemlerinde size Şirket Portalı uygulamasını kullanarak cihazların kimliğini doğrulama seçeneği sağlıyor:

- Apple Cihaz Kaydı Programı
- Apple School Manager
- Apple Configurator Kaydı

Şirket portalı seçeneği kullanılırken, bu kayıt yöntemlerini engellemeden Azure Active Directory çok faktörlü kimlik doğrulaması zorunlu tutulabilir.

Şirket portalı seçeneği kullanılırken, Intune kullanıcı benzeşimi kaydı için iOS Kurulum Yardımcısı'nda kullanıcı kimlik doğrulamasını atlar. Bu, cihazın başlangıçta kullanıcısız bir cihaz olarak kaydedildiği ve dolayısıyla kullanıcı gruplarının yapılandırmaları veya ilkelerini almadığı anlamına gelir. Cihaz, yalnızca cihaz gruplarının yapılandırmalarını ve ilkelerini alır. Bununla birlikte, Intune Şirket Portalı uygulamasını Cihaz üzerine otomatik olarak yükleyecek. Şirket Portalı uygulamasını başlatan ve bu uygulamada oturum açan ilk kullanıcı, Intune'da cihazla ilişkilendirilecek. Bu noktada kullanıcı, kendi kullanıcı gruplarının yapılandırmalarını ve ilkelerini alacak. Yeniden kayıt yapılmadan kullanıcı ilişkisi değiştirilemez.

#### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts---747685-eeready---"></a>Birden çok Apple DEP / Apple School Manager hesabı için Intune desteği<!-- 747685 eeready -->

Intune, artık sayıları 100'e varan farklı Apple Aygıt Kayıt Programı (DEP) veya Apple School Manager hesabından cihazların kaydını destekliyor. Karşıya yüklenen her belirteç kayıt profilleri ve cihazlar için ayrı olarak yönetilebilir. Karşıya yüklenen DEP/School Manager belirteçlerinin her biri için farklı bir kayıt profili otomatik olarak atanabilir. Birden çok School Manager belirteci karşıya yüklenirse, Microsoft School Data Sync ile bir kerede tek bir belirteç paylaşılabilir.

Geçişten sonra, Graph üzerinden Apple DEP veya ASM yönetimi için beta Graph API'leri ve yayımlanan betikler artık çalışmayacak. Yeni beta Graph API'leri geliştirme aşamasındadır ve geçiş sonrasında yayınlanacaktır.

### <a name="remote-printing-over-a-secure-network---1709994----"></a>Güvenli bir ağ üzerinden uzaktan yazdırma<!-- 1709994  -->
PrinterOn’un kablosuz mobil yazdırma çözümleri kullanıcıların güvenli bir ağ üzerinden istedikleri yerde ve istedikleri zaman uzaktan yazdırma işlemi yapmalarını sağlayacak. PrinterOn, hem iOS hem de Android için Intune APP SDK'sıyla tümleştirilecek. Yönetim konsolundaki Intune **Uygulama koruma ilkeleri** dikey penceresi aracılığıyla uygulama koruma ilkelerinde bu uygulamayı hedefleyebileceksiniz. Son kullanıcılar 'PrinterOn for Microsoft' uygulamasını kendi Intune ekosistemlerinde kullanmak üzere Play Store veya iTunes üzerinden indirebilecek.

### <a name="macos-company-portal-support-for-enrollments-that-use-the-device-enrollment-manager---1352411---"></a>macOS Aygıt Kayıt Yöneticisi’ni kullanan kayıtlar için Şirket Portalı desteği<!-- 1352411 -->

macOS Şirket Portalı’na kaydolurken kullanıcılar, artık Cihaz Kayıt Yöneticisi’ni kullanabilirler.

### <a name="device-management"></a>Cihaz yönetimi

#### <a name="windows-defender-health-status-and-threat-status-reports--854704---"></a>Windows Defender sistem durumu ve tehdit durumu raporları<!--854704 -->

Windows Defender’ın sistem durumunu anlamak, Windows bilgisayarları yönetmenin anahtarıdır.  Bu güncelleştirmeyle Intune, Windows Defender aracısının sistem durumuna yeni raporlar ve eylemler ekler. [Cihaz Uyumluluğu iş yükünde](../protect/compliance-policy-monitor.md) bir durum toplama raporu kullanarak, aşağıdakilerden herhangi birine gereksinim duyan cihazları görebilirsiniz:
- imza güncelleştirmesi
- Uygulamasını
- el ile müdahale
- tam tarama
- müdahale gerektiren diğer aracı durumları

Her bir durum kategorisi için ayrıntılı bir rapor ile ilgilenilmesi gereken bireysel bilgisayarlar veya **Temiz** olarak raporlananlar listelenir.

#### <a name="new-privacy-settings-for-device-restrictions--1308926---"></a>Cihaz kısıtlamaları için yeni gizlilik ayarları<!--1308926 -->
Cihazlar için [iki yeni gizlilik ayarı](../configuration/device-restrictions-windows-10.md#privacy) artık kullanılabilir:
- **Kullanıcı etkinliklerini yayımla**: Bunu **Engelle** şeklinde ayarlayarak, görev değiştiricide paylaşılan deneyimleri ve yakın zamanda kullanılan kaynakların bulunmasını önleyin.
- **Yalnızca yerel etkinlikler**: Bunu **Engelle** şeklinde ayarlayarak, görev değiştiricide yalnızca yerel etkinliklere bağlı olan paylaşılan deneyimleri ve yakın zamanda kullanılan kaynakların bulunmasını önleyin.

#### <a name="new-settings-for-the-microsoft-edge-browser--1469166---"></a>Microsoft Edge tarayıcısı için yeni ayarlar<!--1469166 -->
Microsoft Edge tarayıcısı kullanan cihazlar için [iki yeni ayar](../configuration/device-restrictions-windows-10.md#microsoft-edge-browser) artık kullanılabilir: **Sık kullanılanlar dosyasının yolu** ve **Sık Kullanılanlarda değişiklikler**.

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="protocol-exceptions-for-applications--1035509---"></a>Uygulamalar için protokol özel durumları<!--1035509 -->

Belirli yönetilmeyen uygulamaları açmak için Intune Mobil Uygulama Yönetimi (MAM) veri aktarımı ilkesinde artık özel durumlar oluşturabilirsiniz. Bu tür uygulamaların BT tarafından güvenilen uygulamalar olması gerekir. Oluşturduğunuz özel durumlar dışında, veri aktarımı ilkeniz **yalnızca yönetilen uygulamalar** olarak ayarlı olduğu sürece veri aktarımınız Intune tarafından yönetilen uygulamalarla kısıtlıdır. Protokoller (iOS) veya paketler (Android) kullanarak kısıtlamalar oluşturabilirsiniz.

Örneğin MAM veri aktarımı ilkesine Webex paketini özel durum olarak ekleyebilirsiniz. Böylece, yönetilen bir Outlook e-posta iletisindeki Webex bağlantıları, doğrudan Webex uygulamasında açılacaktır. Veri aktarımı, diğer yönetilmeyen uygulamalarda kısıtlı olmaya devam edecektir. Daha fazla bilgi için bkz. [Uygulamalar için veri aktarım ilkesi özel durumları](../apps/app-protection-policies-exception.md).

#### <a name="windows-information-protection-wip-encrypted-data-in-windows-search-results---1469193---"></a>Windows arama sonuçlarında Windows Bilgi Koruması (WIP) ile şifrelenmiş veriler<!-- 1469193 -->
Windows Bilgi Koruması (WIP) ilkesindeki bir ayar, artık Windows arama sonuçlarına WIP ile şifrelenmiş verilerin dahil edilip edilmeyeceğini denetlemenize olanak tanıyor. Windows Bilgi Koruması ilkesinin **Gelişmiş ayarlar** kısmında **Windows Search Dizin Oluşturucu’nun şifrelenmiş öğeleri aramasına izin ver**’i seçerek bu uygulama koruma ilkesi seçeneğini belirleyin. Uygulama koruma ilkesi, *Windows 10* platformuna ayarlanmalı ve uygulama ilkesi **Kayıt durumu**, **Kayıt ile** olarak ayarlanmalıdır. Daha fazla bilgi için bkz. [Windows Search Dizin Oluşturucu’nun şifrelenmiş öğeleri aramasına izin ver](../apps/windows-information-protection-policy-create.md#allow-windows-search-indexer-to-search-encrypted-items).

#### <a name="configuring-a-self-updating-mobile-msi-app---1740840---"></a>Kendi kendini güncelleştiren bir MSI uygulaması yapılandırma<!-- 1740840 -->
Sürüm denetim işlemini yoksaymak için bilinen bir kendi kendini güncelleştiren MSI uygulaması yapılandırabilirsiniz. Bu yetenek, bir yarış durumuna girmeyi önlemek açısından kullanışlıdır. Bu tür bir yarış durumu örneğin uygulama, uygulama geliştiricisi tarafından otomatik olarak güncelleştirilirken diğer yandan Intune tarafından da güncelleştirildiği durumlarda ortaya çıkabilir. Her iki taraf da bir Windows istemcisinde uygulamanın bir sürümünü zorlamaya çalışabilir, böylece bir çakışma ortaya çıkabilir. Otomatik olarak güncelleştirilen bu MSI uygulamaları için **Uygulama bilgileri** dikey penceresindeki **Uygulama sürümünü yoksay**  ayarını yapılandırabilirsiniz. Bu ayar **Evet** olarak değiştirildiğinde, Microsoft Intune, Windows istemcisinde yüklü olan uygulama sürümünü yoksayar.

#### <a name="related-sets-of-app-licenses-supported-in-intune---1864117---"></a>Intune’da desteklenen ilgili uygulama lisans kümeleri<!-- 1864117 -->
Azure portalında Intune, ilgili uygulama lisans kümelerini artık kullanıcı arabiriminde tek bir uygulama öğesi olarak destekliyor. Buna ek olarak, İş İçin Microsoft Store’dan eşitlenmiş Çevrimdışı Lisanslanan uygulamalar da tek bir uygulama girdisi olarak birleştirilecek ve ayrı ayrı paketlerdeki dağıtım ayrıntıları bu tek girdiye taşınacak. Azure portalında ilgili uygulama lisans kümelerini görüntülemek için **İstemci uygulamaları** dikey penceresinden **Uygulama lisansları**’nı seçin.

### <a name="device-configuration"></a>Cihaz yapılandırması
#### <a name="windows-information-protection-wip-file-extensions-for-automatic-encryption---1463582---"></a>Otomatik şifreleme için Windows Bilgi Koruması (WIP) dosya uzantıları<!-- 1463582 -->
Windows Bilgi Koruması (WIP) ilkesindeki bir ayar, WIP politikasında tanımlanan şekilde şirket sınırında bir Sunucu İleti Bloğu (SMB) paylaşımından kopyalarken hangi dosya uzantılarının otomatik olarak şifreleneceğini belirtmenize artık izin veriyor.

#### <a name="configure-resource-account-settings-for-surface-hubs"></a>Surface Hub’lar için kaynak hesap ayarlarını yapılandırma

Surface Hub’lar için kaynak hesap ayarlarını artık uzaktan yapılandırabilirsiniz.

Kaynak hesabı, Skype/Exchange ile kimlik doğrulaması yapmak için bir Surface Hub tarafından kullanılır; böylece bir toplantıya katılabilir.
Surface Hub’ın toplantıdaki konferans odası olarak görünmesi için eşsiz bir kaynak hesabı oluşturmak isteyebilirsiniz.
Örneğin, **Konferans Salonu B41/6233** kaynak hesabı.

> [!NOTE]
> - Alanları boş bırakırsanız cihazın önceden yapılandırılmış özniteliklerini geçersiz kılarsınız.
>
> - Kaynak Hesap özellikleri, Surface Hub’da dinamik olarak değişebilir. Örneğin, parola dönüşü açıksa. Bu nedenle, Azure konsolundaki değerlerin cihazdaki gerçekliği yansıtması biraz zaman alabilir.
>
>   Surface Hub’daki geçerli yapılandırmaları anlamak için Kaynak Hesap bilgileri donanım envanterine (7 günlük aralığı vardır) veya salt okunur özelliklere dahil edilebilir. Uzak eylem gerçekleştikten sonra doğruluğu artırmak için, Surface Hub hesabını/parametrelerini güncelleştirmek üzere eylemi çalıştırdıktan hemen sonra parametrelerin durumunu alabilirsiniz.

##### <a name="attack-surface-reduction"></a>Saldırı Yüzeyini Azaltma

|Ayar adı  |Ayar seçenekleri  |Description  |
|---------|---------|---------|
|Parola korumalı yürütülebilir içeriğin e-postadan yürütülmesi|Engelle, Denetle, Yapılandırılmadı|E-posta üzerinden indirilen parola korumalı yürütülebilir dosyaların çalıştırılmasını engelleyin.|
|Gelişmiş fidye yazılımı koruması|Etkin, Denetle, Yapılandırılmadı|Agresif fidye yazılımı koruması kullanır.|
|Windows yerel güvenlik yetkilisi alt sisteminden kimlik bilgisi çalma eylemlerine bayrak ekleme|Etkin, Denetle, Yapılandırılmadı|Windows yerel güvenlik yetkilisi alt sisteminden kimlik bilgisi çalma eylemlerine bayrak ekler (lsass.exe).|
|PSExec ve WMI komutlarından işlem oluşturma|Engelle, Denetle, Yapılandırılmadı|PSExec ve WMI komutlarından kaynaklanan işlem oluşturmalarını engeller.|
|USB’den çalışan güvenilmeyen ve imzasız işlemler|Engelle, Denetle, Yapılandırılmadı|USB’den çalışan güvenilmeyen ve imzasız işlemleri engeller.|
|Bir yaygınlık, yaş veya güvenilenler listesi kriterine uymayan yürütülebilir dosyalar|Engelle, Denetle, Yapılandırılmadı|Bir yaygınlık, yaş veya güvenilenler listesi kriterine uymadıkları sürece yürütülebilir dosyaları engeller.|

##### <a name="controlled-folder-access"></a>Denetlenen klasör erişimi

|              Ayar adı               |                                                              Ayar seçenekleri                                                              | Description |
|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|-------------|
| Klasör koruması (zaten uygulanmış) | Yapılandırılmamış, Etkinleştir, Yalnızca denetle (zaten uygulanmış)<br><br> <strong>Yeni</strong><br>Disk değişikliğini engelle, Disk değişikliğini denetle |             |

Dosya ve klasörleri kötü amaçlı uygulamaların yetkisiz değişikliklerinden korur.<br><br>**Etkinleştir**: Güvenilmeyen uygulamaların korumalı klasörlerdeki dosyaları değiştirmesini veya silmesini ve disk kesimlerine yazmasını engeller.<br><br>
**Yalnızca disk değişikliğini engelle**:<br>Güvenilmeyen uygulamaların, disk kesimlerine yazmasını engeller. Güvenilmeyen uygulamalar hala korumalı klasörlerdeki dosyaları değiştirebilir veya silebilir.|

#### <a name="additions-to-system-security-settings-for-windows-10-and-later-compliance-policies--1704133--"></a>Windows 10 ve üzeri uyumluluk ilkeleri için Sistem Güvenliği ayarlarına eklemeler<!--1704133-->

Güvenlik Duvarı ve Windows Defender Virüsten Koruma dahil olmak üzere Windows 10 uyumluluk ayarlarına bazı eklemeler geldi.

### <a name="intune-apps"></a>Intune uygulamaları

#### <a name="support-for-offline-apps-from-the-microsoft-store-for-business--1222672--"></a>İş İçin Microsoft Mağazası uygulamaları için çevrimdışı desteği<!--1222672-->
İş için Microsoft Store’dan satın aldığınız çevrimdışı uygulamalar, artık Azure portalına eşitlenir. Bu uygulamaları cihaz gruplarına veya kullanıcı gruplarına dağıtabilirsiniz. Çevrimdışı uygulamalar, mağaza tarafından değil Intune tarafından yüklenir.

#### <a name="prevent-end-users-from-manually-adding-or-removing-accounts-in-the-work-profile---1728700---"></a>Son kullanıcıların iş profiline el ile hesap eklemesini veya profilden hesap kaldırmasını önleme<!-- 1728700 -->

Bir Android for Work profiline Gmail uygulamasını dağıttığınızda, artık Android for Work cihaz kısıtlama profilindeki **Hesap ekle veya kaldır** ayarını kullanarak son kullanıcıların iş profilinde hesap ekleme veya kaldırma işlemleri yapmasını önleyebilirsiniz.

<!-- ########################## -->
## <a name="january-2018"></a>Ocak 2018

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="alerts-for-expired-tokens-and-tokens-that-will-soon-expire---1639263---"></a>Süresi dolan ve dolmak üzere olan belirteçler için uyarılar<!-- 1639263 -->
Genel bakış sayfasında süresi dolan ve dolmak üzere olan belirteçler için artık uyarılar gösteriliyor. Tek bir belirtecin uyarısına tıkladığınızda, belirtecin ayrıntılar sayfasına gideceksiniz.  Birden çok belirteç içeren bir uyarıya tıklarsanız, durumlarıyla birlikte tüm belirteçlerin listesine gideceksiniz. Yöneticilerin, süreleri dolmadan önce belirteçleri yenilemesi gerekir.

### <a name="device-management"></a>Cihaz yönetimi

#### <a name="remote-erase-command-support-for-macos-devices---1438084---"></a>macOS cihazlar için uzaktan “Sil” komutu desteği<!-- 1438084 -->

macOS cihazlar için yöneticiler uzaktan Sil komutu gönderebilir.

> [!IMPORTANT]
> Sil komutu geri alınamaz ve dikkatli kullanılmalıdır.

Sil komutu işletim sistemi de içinde olmak üzere cihazdan tüm verileri kaldırır. Cihaz ayrıca Intune yönetiminden de kaldırılır. Kullanıcıya hiçbir uyarı gönderilmez ve komut gönderildiğinde silme işlemi hemen gerçekleştirilir.

6 basamaklı bir kurtarma PIN’i yapılandırmanız gerekir. Bu PIN silinmiş olan cihazın kilidini açmak için kullanılabilir ve bu noktada işletim sisteminin yeniden yüklemesi başlar. Silme işlemi başlatıldıktan sonra, Intune'da cihazın genel bakış dikey penceresindeki durum çubuğunda PIN gösterilir. Silme işlemi devam ettiği sürece PIN görüntüde kalacak. Silme işlemi tamamlandıktan sonra, cihaz Intune yönetiminden tamamen kaybolur. Herhangi birinin cihazı geri yükleyen kullanabilmesi için kurtarma PIN'ini bir yere kaydettiğinizden emin olun.

#### <a name="revoke-licenses-for-an-ios-volume-purchasing-program-token---820870---"></a>Bir iOS Toplu Satın Alma Programı belirteci için lisansları iptal et<!-- 820870 -->
Belirli bir VPP Belirteci için tüm iOS Volume Purchasing Program (VPP) uygulamalarının lisansını iptal edebilirsiniz.

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="revoking-ios-volume-purchase-program-apps----820863---"></a>iOS - Toplu Satın Alma Programı uygulamalarını iptal etme <!-- 820863 -->
Bir veya daha fazla iOS Volume Purchase Program (VPP) uygulaması olan belirli bir cihaz için, cihazla ilişkili cihaza dayalı uygulama lisansını iptal edebilirsiniz. Bir uygulama lisansını iptal etmek ilgili VPP uygulamasını cihazdan kaldırmaz. Bir VPP uygulamasını kaldırmak için, atama işlemini **Kaldır** olarak değiştirmelisiniz. Daha fazla bilgi için bkz. [Microsoft Intune ile toplu satın alma programından satın alınan iOS uygulamalarını yönetme](../apps/vpp-apps-ios.md).

#### <a name="assign-office-365-mobile-apps-to-ios-and-android-devices-using-built-in-app-type---1332318---"></a>Yerleşik uygulama türü kullanarak Office 365 mobil uygulamaları iOS ve Android cihazlara atama<!-- 1332318 -->
**Yerleşik** uygulama türü yönettiğiniz iOS ve Android cihazlar için Office 365 uygulamaları oluşturmayı ve atamayı kolaylaştırır. Bu uygulamalar Word, Excel, PowerPoint ve OneDrive gibi 0365 uygulamalarını içerir. Uygulama türüne belirli uygulamalar atayabilir ve uygulama bilgileri yapılandırmasını düzenleyebilirsiniz.

#### <a name="including-and-excluding-app-assignment-based-on-groups---1406920---"></a>Gruplar temelinde uygulama atamasını dahil etme ve hariç tutma<!-- 1406920 -->

Uygulama ataması sırasında ve bir atama türü seçtikten sonra, hem dahil edilecek hem de hariç tutulacak grupları seçebilirsiniz.

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="you-can-assign-an-application-configuration-policy-to-groups-by-including-and-excluding-assignments----1480316---"></a>Atamaları dahil ederek veya dışlayarak gruplara bir uygulama yapılandırma ilkesi atayabilirsiniz <!-- 1480316 -->

Dahil etme ve dışlama atamaları bileşimini kullanarak kullanıcı ve cihaz gruplarına bir uygulama yapılandırma ilkesi atayabilirsiniz. Atamalar, özel seçili gruplar olarak veya sanal bir grup şeklinde seçilebilir. Bir sanal grup **Tüm Kullanıcılar**, **Tüm Cihazlar** ve **Tüm Kullanıcılar + Tüm Cihazlar** şeklinde olabilir.

#### <a name="support-for-windows-10-edition-upgrade-policy-----903672archived-1119689---"></a>Windows 10 sürüm yükseltme ilkesi desteği  <!-- 903672(archived), 1119689 -->  
Windows 10 cihazları; Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education ve Windows 10 Professional Education N’e yükselten bir Windows 10 sürüm yükseltme ilkesi oluşturabilirsiniz. Windows 10 sürüm yükseltmeleri hakkında daha fazla bilgi için bkz. [Windows 10 sürüm yükseltmelerini yapılandırma](../configuration/edition-upgrade-configure-windows-10.md).

#### <a name="conditional-access-policies-for-intune-is-only-available-from-the-azure-portal----1737088-1634311---"></a>Intune için Koşullu Erişim ilkeleri yalnızca Azure Portal'dan sağlanır <!-- 1737088 1634311 -->

Bu yayından başlayarak, Koşullu Erişim ilkelerinizi yalnızca [Azure Portalı](https://portal.azure.com)’ndaki **Azure Active Directory** > **Koşullu Erişim**’de yapılandırabilir ve yönetebilirsiniz. Size kolaylık olması için, Azure Portal'daki Intune'da **Intune** > **Koşullu Erişim** konumundan da erişebilirsiniz.

#### <a name="updates-to-compliance-emails--1637547---"></a>Uyumluluk e-postalarında güncelleştirmeler<!--1637547 -->

Uyumsuz bir cihazı raporlamak amacıyla e-posta gönderildiğinde, bu e-postaya uyumsuz cihaz hakkındaki ayrıntılar da eklenir.

### <a name="intune-apps"></a>Intune uygulamaları

#### <a name="new-functionality-for-the-resolve-action-for-android-devices--1583480--"></a>Android cihazlarda “Çözümle” eylemi için yeni işlev<!--1583480-->

Android için Şirket Portalı uygulaması, **Cihaz ayarlarını güncelleştir** için “Çözümle” eylemini [cihaz şifreleme sorunlarını](/intune-user-help/encrypt-your-device-android) çözümlemek üzere genişletiyor.

#### <a name="remote-lock-available-in-company-portal-app-for-windows-10--676506--"></a>Windows 10 için Şirket Portalı uygulamasında uzaktan kilitleme kullanılabilir<!--676506-->
Son kullanıcılar artık, Windows 10 için Şirket Portalı uygulamasını kullanarak cihazlarını uzaktan kilitleyebilirler. Bu, etkin olarak kullanmakta oldukları yerel cihazda görüntülenmez.

#### <a name="easier-resolution-of-compliance-issues-for-the-company-portal-app-for-windows-10--676546--"></a>Windows 10 için Şirket Portalı'ndaki uyumluluk sorunlarının daha kolay çözümü<!--676546-->
Windows cihazı olan son kullanıcılar, Şirket Portalı uygulamasında uyumsuzluk nedenine dokunabilecek. Buna dokunmaları mümkün olduğunda, ayarlar uygulamasında sorunu çözebilecekleri konuma gidecekler.

<!-- ########################## -->
## <a name="december-2017"></a>Aralık 2017

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="new-automatic-redeployment-setting---1469168---"></a>Yeni otomatik yeniden dağıtım ayarı<!-- 1469168 -->
**Otomatik yeniden dağıtım** ayarı, yönetici haklarına sahip olan kullanıcıların cihaz kilidi ekranında **CTRL + Win + R** tuşunu kullanarak tüm kullanıcı verilerini ve ayarlarını silmelerini sağlar. Cihaz otomatik olarak yeniden yapılandırılacak ve yönetime yeniden kaydedilir. Bu ayar, Windows 10 > Aygıt kısıtlamaları > Genel > Otomatik yeniden dağıtma altında bulunabilir. Ayrıntılar için bkz. [Windows 10 için Intune cihaz kısıtlama ayarları](../configuration/device-restrictions-windows-10.md#general).

#### <a name="support-for-additional-source-editions-in-the-windows-10-edition-upgrade-policy----903672--1119689---"></a>Windows 10 sürüm yükseltme ilkesinde ek kaynak sürümleri desteği <!-- 903672,  1119689 -->
Artık başka Windows 10 sürümlerinden (Windows 10 Pro, Windows 10 Pro Education, Windows 10 Cloud, vb.) yükseltme yapmak için Windows 10 sürüm yükseltme ilkesini kullanabilirsiniz. Bu sürümden önce, desteklenen sürüm yükseltme yolları daha sınırlıydı. Ayrıntılar için bkz. [Windows 10 sürüm yükseltmelerini yapılandırma](../configuration/edition-upgrade-configure-windows-10.md).

#### <a name="new-windows-defender-security-center-wdsc-device-configuration-profile-settings---1335507---"></a>Yeni Windows Defender Güvenlik Merkezi (WDSC) cihaz yapılandırma profili ayarları<!-- 1335507 -->

Intune, cihaz yapılandırma profili ayarlarının Uç nokta koruma altında **Windows Defender Güvenlik Merkezi** adında yeni bir bölüm ekler. BT yöneticileri, son kullanıcıların Windows Defender Güvenlik Merkezi uygulamasının hangi sütunlarına erişebileceklerini yapılandırabilirler. Bir BT yöneticisi Windows Defender Güvenlik Merkezi uygulamasında bir sütun gizlerse, gizli sütunlarla ilgili hiçbir bildirim kullanıcının cihazında görüntülenmez.

Yöneticilerin Windows Defender Güvenlik Merkezi aygıt yapılandırma profili ayarlarından gizleyebilecekleri sütunlar şunlardır:
- Virüs ve tehdit koruması
- Cihaz performans ve sistem durumu
- Güvenlik duvarı ve ağ korumaları
- Uygulama ve tarayıcı denetimi
- Aile seçenekleri

BT yöneticileri, kullanıcıların hangi bildirimleri aldığını da özelleştirebilir. Örneğin, kullanıcıların WDSC'deki görünür sütunlar tarafından oluşturulan tüm bildirimleri alıp almayacaklarını veya yalnızca kritik bildirimleri alıp almayacaklarını yapılandırabilirsiniz. Kritik olmayan bildirimlere, Windows Defender Antivirus etkinliğinin periyodik özetleri ve taramalar tamamlandığında verilen bildirimler dahildir. Diğer tüm bildirimler kritik olarak kabul edilir. Ayrıca, bildirim içeriğini kendiniz de özelleştirebilirsiniz, örneğin, kullanıcıların cihazlarında görünen bildirimlere eklemek için BT iletişim bilgilerini sağlayabilirsiniz.

#### <a name="multiple-connector-support-for-scep-and-pfx-certificate-handling---1361755---"></a>SCEP ve PFX sertifika işleme için birden çok bağlayıcı desteği<!-- 1361755 -->

Şirket içi NDES bağlayıcısı kullanan müşteriler, artık tek bir kiracıda birden fazla bağlayıcıyı yapılandırarak sertifikaları cihazlara teslim edebilir.

Bu yeni yetenek aşağıdaki senaryoyu destekler:

- **Yüksek kullanılabilirlik**

Her bir NDES bağlayıcısı, Intune'dan sertifika istekleri çeker.  Bir NDES Bağlayıcısı çevrimdışı olursa, diğer bağlayıcı istekleri işlemeye devam edebilir.

#### <a name="customer-subject-name-can-use-aad_device_id-variable----1468599---"></a>Özel konu adı AAD_DEVICE_ID değişkenini kullanabilir <!-- 1468599 -->

Intune'da SCEP sertifika profili oluşturduğunuzda, artık özel konu adını oluştururken AAD_DEVICE_ID değişkenini kullanabilirsiniz.   Bu SCEP profili kullanılarak sertifika istendiğinde, değişkenin yerini sertifika isteğinde bulunan cihazın AAD cihaz kimliği alır.


### <a name="device-management"></a>Cihaz yönetimi

#### <a name="manage-jamf-enrolled-macos-devices-with-intunes-device-compliance-engine---1592747---"></a>Jamf'e kayıtlı makro cihazları Intune cihaz uyumluluk motoruyla yönetme<!-- 1592747 -->
Artık, Intune konsolunda tanımlanan ilkelere uyumu değerlendirecek olan MacOS cihaz durumu bilgilerini Intune'a göndermek için Jamf kullanabilirsiniz. Cihaz uyumluluk durumuna ve diğer koşullara (konum, Kullanıcı riski vb.) bağlı olarak, koşullu erişim, Azure AD ile bağlantılı bulut ve şirket içi uygulamalara ve Office 365 dahil olmak üzere şirket içi uygulamalara erişen macOS cihazları için uyumluluğu zorlayacaktır. [Jamf tümleştirmesini ayarlama](../protect/conditional-access-integrate-jamf.md) ve [Jamf tarafından yönetilen cihazlarda uyumluluğu zorlama](../protect/conditional-access-assign-jamf.md) hakkında daha fazla bilgi edinin.

#### <a name="new-ios-device-action-----1424701---"></a>Yeni iOS cihaz eylemi  <!-- 1424701 -->

Şimdi IOS 10.3 denetlenen cihazlarını kapatabilirsiniz. Bu eylem, son kullanıcıya herhangi bir uyarı yapılmadan cihazı hemen kapatır. **Cihaz** iş yükünde bir cihaz seçtiğinde, cihaz özelliklerinde **Kapat (yalnızca denetimli)** eylemi bulunabilir.

#### <a name="disallow-datetime-changes-to-samsung-knox-devices---1468103---"></a>Samsung Knox cihazlarında tarih/saat değişikliklerine izin vermeme<!-- 1468103 -->

Samsung Knox cihazlarında tarih ve saat değişikliklerini engellemenize olanak tanıyan yeni bir özellik ekledik. Bunu, **Cihaz yapılandırma profilleri** > **Cihaz kısıtlamaları (Android)**  > **Genel** altında bulabilirsiniz.

#### <a name="surface-hub-resource-account-supported---1566442----"></a>Surface Hub kaynak hesabını destekler<!-- 1566442  -->

Yeni bir cihaz eylemi eklendi; böylece yöneticiler bir Surface Hub ile ilişkili kaynak hesabını tanımlayıp güncelleyebilir.

Kaynak hesabı, Skype/Exchange ile kimlik doğrulaması yapmak için bir Surface Hub tarafından kullanılır; böylece bir toplantıya katılabilir. Eşsiz bir kaynak hesabı oluşturabilir; böylece Surface Hub toplantıdaki konferans odası olarak görünür. Örneğin, kaynak hesabı *Konferans Salonu B41/6233* olarak görünebilir. Surface Hub için kaynak hesabı (cihaz hesabı olarak bilinir), genellikle Konferans odası konumu için ve diğer kaynak hesabı parametreleri değiştirilmesi gerektiğinde yapılandırılması gerekir.

Yöneticiler bir cihazdaki kaynak hesabını güncelleştirmek istediği zaman, cihazla ilişkili geçerli Active Directory/Azure Active Directory kimlik bilgilerini sağlamaları gerekir. Cihaz için parola rotasyonu açıksa, yöneticiler parolayı bulmak için Azure Active Directory'ye gitmelidir.

> [!NOTE]
> Tüm alanlar bir paket halinde gönderilir ve daha önce yapılandırılmış olan tüm alanların üzerine yazılır. Boş alanlar var olan alanların üzerine yazılır.

Yöneticilerin yapılandırabileceği ayarlar şunlardır:

- **Kaynak hesabı**
  - **Active Directory kullanıcısı**

    EtkiAlanıAdı\KullanıcıAdı veya Kullanıcı Asıl Adı (UPN):user@domainname.com

  - **Parola**

- **İsteğe bağlı kaynak hesabı parametreleri** (belirtilen kaynak hesabını kullanarak ayarlanması gerekir)

  - **Parola rotasyon süresi**

    Güvenlik nedeniyle, hesap şifresinin her hafta Surface Hub tarafından güncellenmesini sağlar. Bu etkinleştirildikten sonra parametreleri yapılandırmak için, Azure Active Directory'deki hesapta önce parolanın sıfırlanması gerekir.

  - **SIP (Oturum Başlatma Protokolü) adresi**

    Yalnızca otomatik bulma başarısız olduğunda kullanılır.

  - **E-posta**

    Cihaz/kaynak hesabının e-posta adresi.

  - **Exchange sunucusu**

    Yalnızca otomatik bulma başarısız olduğunda gereklidir.

  - **Takvim eşitleme**

    Takvim eşitleme ve diğer Exchange server hizmetlerini etkinleştirilip etkinleştirilmeyeceğini belirtir. Örneğin: Toplantı eşitleme.

#### <a name="install-office-apps-on-macos-devices---1494311---"></a>MacOS cihazlarda Office uygulamalarını yükleyin<!-- 1494311 -->
Artık Office uygulamalarını macOS cihazlara yükleyebilirsiniz. Bu yeni uygulama türü, Word, Excel, PowerPoint, Outlook ve OneNote yüklemeye izin verir. Bu uygulamalar, uygulamalarınızı güvenli ve güncel tutmaya yardımcı olmak için ayrıca Microsoft AutoUpdate (MAU) ile gelir.

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="delete-an-ios--volume-purchasing-program-token---820879---"></a>Bir iOS Toplu Satın Alma Programı belirtecini silin<!-- 820879 -->
Konsolu kullanarak iOS Toplu Satın Alma Programı (VPP) belirtecini silebilirsiniz. VPP belirteci kopya örnekleriniz olduğunda bu gerekli olabilir.

### <a name="intune-apps"></a>Intune uygulamaları


### <a name="role-based-access-control"></a>Rol tabanlı erişim denetimi

#### <a name="a-new-entity-collection-named-current-user-is-limited-to-currently-active-user-data---1667026---"></a>Geçerli Kullanıcı adlı yeni bir varlık koleksiyonu şu anda etkin olan kullanıcı verisi ile sınırlıdır<!-- 1667026 -->

**Kullanıcılar** varlık koleksiyonu, kuruluşunuzda kendisine lisans atanmış olan tüm Azure Active Directory (Azure AD) kullanıcılarını içerir. Örneğin, bir kullanıcı Intune'a eklenebilir ve son bir ay içerisinde kaldırılabilir. Bu kullanıcı raporun olduğu saatte bulunmamakla birlikte, verilerde kullanıcı ve durumu bulunur. Kullanıcının verilerinizdeki varlığının süresini gösterecek bir rapor oluşturabilirsiniz.

Buna karşılık, yeni **Geçerli Kullanıcı** varlık koleksiyonu yalnızca kaldırılmamış olan kullanıcıları içerir. **Geçerli kullanıcı** varlık koleksiyonu yalnızca etkin kullanıcıları içerir. **Geçerli Kullanıcı** öğesi hakkında daha fazla bilgi edinmek için bkz. [Geçerli kullanıcı varlığı için başvuru](../developer/reports-ref-data-model.md).

### <a name="updated-graph-apis---1736360---"></a>Güncelleştirilmiş Graph API'leri<!-- 1736360 -->

Bu sürümde, beta aşamasında olan Intune için Graph API'lerinden birkaçını güncelleştirdik. Daha fazla bilgi için lütfen aylık [Graph API değişiklik günlüğünü](https://developer.microsoft.com/graph/docs/concepts/changelog) gözden geçirin.

### <a name="monitor-and-troubleshoot"></a>İzleme ve sorun giderme

#### <a name="intune-supports-windows-information-protection-wip-denied-apps---1479103---"></a>Intune, Windows Information Protection (WIP) tarafından reddedilen uygulamaları destekler<!-- 1479103 -->
Intune'da reddedilen uygulamaları belirtebilirsiniz. Uygulama reddedilirse, şirket bilgilerine erişimi engellenir; aslında izin verilen uygulamalar listesinin tam tersidir. Daha fazla bilgi için bkz. [Windows Information Protection için önerilen reddedilenler listesi](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp?f=255&MSPPError=-2147217396#recommended-deny-list-for-windows-information-protection).

<!-- ########################## -->
## <a name="november-2017"></a>Kasım 2017

### <a name="troubleshoot-enrollment-issues----746324---"></a>Kayıt sorunlarını giderme <!-- 746324 -->

**Sorun Giderme** çalışma alanı, şimdi kullanıcı kayıt sorunlarını gösterir. Sorunun ayrıntıları ve önerilen düzeltme adımları, yönetici ve yardım masası çalışanlarının sorunları çözmesine yardımcı olabilir. Bazı kayıt sorunları burada yer almaz ve bazı hatalar için düzeltme önerileri bulunmayabilir.

### <a name="group-assigned-enrollment-restrictions---747598---"></a>Gruba atanan kayıt kısıtlamaları<!-- 747598 -->

Bir Intune yöneticisi olarak, artık [kullanıcı grupları için özel Cihaz Türü ve Cihaz Sınırı kayıt sınırlamaları oluşturabilirsiniz](../enrollment/enrollment-restrictions-set.md).

Intune Azure portalı, her kısıtlama türü için en fazla 25 örnek oluşturmanıza olanak sağlar. Bunlar daha sonra kullanıcı gruplarına atanabilir. Grup tarafından atanan kısıtlamalar varsayılan kısıtlamaları geçersiz kılar.

Bir kısıtlama türünün tüm örnekleri kesin bir şekilde sıralanmış bir listede tutulur. Bu sıra, çakışmaları çözümlemek için bir öncelik değerini tanımlar. Birden fazla kısıtlama örneğinden etkilenen bir kullanıcı, yalnızca en yüksek öncelik değerine sahip örnek tarafından kısıtlanır. Belirli bir örneği listede farklı bir konuma sürükleyerek örneğin önceliğini değiştirebilirsiniz.

Bu işlevsellik, Android for Work ayarlarının Android For Work kayıt menüsünden Kayıt Kısıtlamaları menüsüne geçişi ile birlikte yayımlanacak. Bu geçiş birkaç gün sürebileceğinden, grup atamasının Kayıt Kısıtlamaları için etkinleştirildiğini görmeden önce hesabınız Kasım yayınının diğer bölümleri için güncelleştirilebilir.

### <a name="support-for-multiple-network-device-enrollment-service-ndes-connectors---1528104---"></a>Çoklu Ağ Cihazı Kayıt Hizmeti (NDES) bağlayıcısı desteği<!-- 1528104 -->

NDES, etki alanı kimlik bilgileri olmadan çalışan mobil cihazların Basit Sertifika Kayıt Protokolü’nü (SCEP) temel alarak sertifikaları edinmesini sağlar.
Bu güncelleştirme ile birden çok NDES bağlayıcısı desteklenir.

### <a name="manage-android-for-work-devices-independently-from-android-devices---1490731-eeready--"></a>Android for Work cihazlarını Android cihazlardan ayrı olarak yönetme<!-- 1490731 EEready-->

Intune, Android for Work cihazlarının Android platformundan bağımsız olarak kaydını yönetmeyi destekler. Bu ayarlar **Cihaz Kaydı** > **Kayıt kısıtlamaları** > **Cihaz Türü Kısıtlamaları** altında yönetilir. (Eskiden **Cihaz Kaydı** > **Android for Work Kaydı** > **Android for Work Kayıt Ayarları** altında bulunuyordu.)

Varsayılan olarak, Android for Work cihaz ayarlarınız Android cihazlarınız için ayarlarınızla aynı olur. Ancak Android for Work ayarlarınızı değiştirdikten sonra artık bu durum oluşmaz.

Kişisel Android for Work kaydını engellerseniz, yalnızca kurumsal Android cihazlar Android for Work olarak kaydolabilir.

Yeni ayarlarla çalışırken şu noktaları göz önünde bulundurun:

#### <a name="if-you-have-never-previously-onboarded-android-for-work-enrollment"></a>Daha önce hiç Android for Work kaydı eklemediyseniz

Yeni Android for Work platformu varsayılan Cihaz Türü Kısıtlamalarında engellidir. Özelliği ekledikten sonra, cihazların Android for Work ile kaydolmasına izin verebilirsiniz. Bunu yapmak için varsayılan ayarı değiştirin veya varsayılan Cihaz Türü Kısıtlamasının yerine geçen yeni bir Cihaz Türü Kısıtlaması oluşturun.

#### <a name="if-you-have-onboarded-android-for-work-enrollment"></a>Android for Work kaydı eklediyseniz

Daha önceden eklediyseniz durumunuz seçtiğiniz ayara bağlıdır:

| Ayar | Varsayılan Cihaz Türü Kısıtlamasında Android for Work durumu | Notlar |
| --- | --- | --- |
| **Tüm cihazları Android olarak yönetme** | Engellendiğini | Tüm Android cihazların Android for Work ile kaydolması gerekir. |
| **Desteklenen cihazları Android for Work olarak yönetme** | İzin Verildi | Android for Work’ü destekleyen tüm Android cihazların Android for Work ile kaydolması gerekir. |
| **Yalnızca bu gruplardaki kullanıcılar için desteklenen cihazları Android for Work olarak yönetme** | Engellendiğini | Varsayılan ayarı geçersiz kılmak için ayrı bir Cihaz Türü Kısıtlama ilkesi oluşturuldu. Bu ilke önceden Android for Work kaydına izin vermek için seçtiğiniz grupları tanımlar. Seçili gruplardaki kullanıcıların Android for Work cihazlarını kaydetmesine izin verilir. Diğer tüm kullanıcıların Android for Work ile kaydolması kısıtlanır. |

Tüm durumlarda, hedeflenen düzenlemeniz korunur. Ortamınızda Android for Work’e genel olarak veya grup başına verilen izinleri tutmak için herhangi bir eylem gerçekleştirmeniz gerekmez.

### <a name="google-play-protect-support-on-android---908720---"></a>Android’de Google Play Protect desteği<!-- 908720 -->

Android Oreo sürümüyle Google, kuruluşların güvenli uygulamalar çalıştırmasına ve Android görüntülerinin güvenliğini sağlamasına imkan veren Google Play Protect adlı bir güvenlik özellikleri paketi piyasaya sunuyor. Intune, artol SafetyNet uzak kanıtlama dahil olmak üzere Google Play Protect özelliklerini destekliyor. Yöneticiler, Google Play Protect’ın yapılandırılması ve iyi durumda olmasını gerektiren uyumluluk ilke gereksinimleri ayarlayabilir.
**SafetyNet cihaz kanıtlama** ayarı, cihazın iyi durumda olduğu ve güvenliğinin aşılmadığını doğrulamak için cihazın bir Google hizmetiyle bağlanmasını gerektirir. Yöneticiler ayrıca, yüklenen uygulamaların Google Play hizmetleri tarafından doğrulanmasını gerektiren bir Android for Work yapılandırma profili ayarı da ayarlayabilir. Bir cihaz Google Play koruma gereksinimleriyle uyumlu değilse, koşullu erişim kullanıcıların şirket kaynaklarına erişimini engelleyebilir.

- [Google Play Koruması'nı etkinleştirmek için cihaz uyumluluk ilkesi oluşturmayı](../protect/compliance-policy-create-android.md) öğrenin.

### <a name="text-protocol-allowed-from-managed-apps---1414050----"></a>Yönetilen Uygulamalar'dan izin verilen metin protokolü<!-- 1414050  -->

Intune Uygulama SDK’sı tarafından yönetilen uygulamalar SMS mesajları gönderebilir.


### <a name="app-install-report-updated-to-include-install-pending-status---1249446---"></a>Uygulama yükleme raporu Yükleme Bekletiliyor durumunu içerecek şekilde güncelleştirildi<!-- 1249446 -->  

Her uygulama için **İstemci uygulamaları** iş yükünde **Uygulama** listesi üzerinden erişilebilen **Uygulama yükleme durumu** raporu, şimdi Kullanıcılar ve Cihazlar için **Yükleme Bekletiliyor** sayısını içeriyor.

### <a name="ios-11-app-inventory-api-for-mobile-threat-detection---1391759---"></a>Mobil Tehdit Algılama için iOS 11 uygulama envanteri API’si<!-- 1391759 -->

Intune, kişisel ve kuruluşa ait cihazlardan uygulama envanter bilgilerini toplayarak Lookout for Work gibi Mobil Tehdit Algılama (MTD) sağlayıcıları için kullanılabilir hale getirir. iOS 11+ cihazlarının kullanıcılarından uygulama envanteri toplayabilirsiniz.

**Uygulama envanteri**  
Şirkete ait iOS 11+ ve kişisel cihazlar için envanterler MTD hizmet sağlayıcınıza gönderilir. Uygulama envanterindeki veriler şunları içerir:

- Uygulama Kimliği
- Uygulama Sürümü
- Uygulama Kısa Sürümü
- Uygulama Adı
- Uygulama Paketi Boyutu
- Uygulama Dinamik Boyutu
- Uygulamanın doğrulanıp doğrulanmadığı
- Uygulamanın yönetilip yönetilmediği

### <a name="migrate-hybrid-mdm-users-and-devices-to-intune-standalone---1463747-wnready---"></a>Karma MDM kullanıcıları ve cihazlarını tek başına Intune 'a geçirme<!-- 1463747 wnready -->
Kullanıcıları ve onların cihazlarını karma MDM’den Azure Portal’daki Intune’a geçirmek için yeni süreçler ve araçlar artık kullanılabilir. Bunlar sayesinde aşağıdaki görevleri yapabilirsiniz:
- İlkeleri ve profilleri Configuration Manager konsolundan Azure Portal'daki Intune'a kopyalama
- Kullanıcıların bir alt kümesini Azure Portal'da Intune'a taşırken kalanlarını karma MDM'de bırakma
- Cihazları yeniden kaydetmeye gerek kalmadan Azure Portal'daki Intune'a geçirme

Ayrıntılar için bkz. [Karma MDM kullanıcıları ve cihazlarını tek başına Intune'a geçirme](https://docs.microsoft.com/sccm/mdm/deploy-use/migrate-hybridmdm-to-intunesa).

### <a name="on-premises-exchange-connector-high-availability-support----676614---"></a>Şirket içi Exchange bağlayıcısı yüksek kullanılabilirlik desteği <!-- 676614 -->
Exchange Connector, belirtilen Istemci erişim sunucusu (CAS) kullanarak Exchange 'e bir bağlantı oluşturduktan sonra, bağlayıcının artık diğer CASs 'leri bulma özelliği vardır. Birincil CAS kullanılamaz duruma gelirse, birincil CAS kullanılabilir duruma gelene kadar varsa bağlayıcı başka bir CAS’ye yük devreder. Ayrıntılar için bkz. [Yüksek kullanılabilirlik desteği ile şirket içi Exchange bağlayıcısı](../protect/exchange-connector-install.md#on-premises-intune-exchange-connector-high-availability-support).

### <a name="remotely-restart-ios-device-supervised-only---1424595---"></a>iOS cihazı uzaktan yeniden başlatma (yalnızca denetimli)<!-- 1424595 -->

Artık bir cihaz eylemi kullanarak, denetimli bir iOS 10.3+ cihazı yeniden başlatma için tetikleyebilirsiniz. Cihazı yeniden başlatma eylemini kullanma hakkında daha fazla bilgi için bkz. [Intune ile cihazları uzaktan yeniden başlatma](../remote-actions/device-restart.md).

> [!Note]
> Bu komut, denetlenen cihazlar ve **Cihaz Kilidi** erişim hakkı gerektirir. Cihaz hemen yeniden başlatılır. Geçiş koduyla kilitli iOS cihazlar yeniden başlatmadan sonra bir Wi-Fi ağına yeniden katılmaz; yeniden başlatıldıktan sonra sunucu ile iletişim kuramayabilir.

### <a name="single-sign-on-support-for-ios---1333645---"></a>iOS için Çoklu Oturum Açma desteği<!-- 1333645 -->  

iOS kullanıcıları için Çoklu Oturum Açma kullanabilirsiniz. Çoklu Oturum Açma yükünde kullanıcı kimlik bilgilerini aramak için kodlanan iOS uygulamaları bu yük yapılandırması güncelleştirmesi ile işlevseldir. Asıl Ad ve Bölgeyi yapılandırmak için UPN ve Intune Cihaz Kimliğini de kullanabilirsiniz. Ayrıntılar için bkz. [Intune'u iOS cihazında çoklu oturum açma için yapılandırma](../configuration/ios-device-features-settings.md#single-sign-on).

### <a name="add-find-my-iphone-for-personal-devices--1427287--"></a>Kişisel cihazlar için "iPhone’umu Bul" özelliği ekleme<!--1427287-->
Artık iOS cihazlarda Etkinleştirme Kilidi’nin açık olup olmadığını görüntüleyebilirsiniz. Bu özellik önceden Intune’da klasik portalda bulunuyordu.

### <a name="remotely-lock-managed-macos-device-with-intune---1437691---"></a>Intune ile yönetilen macOS cihazları uzaktan kilitleme<!-- 1437691 -->

Kayıp bir macOS cihazı kilitleyebilir ve 6 basamaklı bir kurtarma PIN’i ayarlayabilirsiniz. Kilitliyken, **Cihaza genel bakış** dikey penceresi başka bir cihaz eylemi gönderilene kadar PIN’i görüntüler.

Daha fazla bilgi için bkz. [Intune ile yönetilen cihazları uzaktan kilitleme](../remote-actions/device-remote-lock.md).

### <a name="new-scep-profile-details-supported---1559808---"></a>Desteklenen yeni SCEP profili ayrıntıları<!-- 1559808 -->

Yöneticiler artık Windows, iOS, macOS ve Android platformlarında SCEP profili oluştururken ek ayarlar yapabilir.  Yöneticiler IMEI, seri numarası veya konu adı biçiminde e-posta dahil ortak ad ayarlayabilir.

<!-- #### Update to what device details your company may see -1616825
The Company Portal app for Android can now use geofencing to protect access to company resources. It uses network details such as IP address, default gateway address, and Domain Name System (DNS) to determine whether to allow access to protected company resources. -->

### <a name="retain-data-during-a-factory-reset---1588489---"></a>Fabrika sıfırlaması sırasında verileri tutma <!--1588489 -->
Windows 10 sürüm 1709 ve üstünü fabrika ayarlarına sıfırlarken, yeni bir özellik sağlanır. Yöneticiler fabrika sıfırlaması sırasında cihaz kaydı ve diğer sağlanan verilerin cihazda tutulup tutulmayacağını belirtebilir.

Fabrika sıfırlamasında aşağıdaki veriler tutulur:
- Cihazla ilişkilendirilen kullanıcı hesapları
- Makine durumu (etki alanına katılım, Azure Active Directory’ye katılım)
- MDM kaydı
- OEM tarafından yüklenen uygulamalar (mağaza ve Win32 uygulamaları)
- Kullanıcı profili
- Kullanıcı profili dışındaki kullanıcı verileri
- Kullanıcı otomatik oturum açma

Şu veriler korunmaz:
- Kullanıcı dosyaları
- Kullanıcı tarafından yüklenen uygulamalar (mağaza ve Win32 uygulamaları)
- Varsayılan olmayan cihaz ayarları


### <a name="window-10-update-ring-assignments-are-displayed---1621837---"></a>Windows 10 güncelleştirme halkası atamaları görüntülenir<!-- 1621837 -->
**Sorun giderirken**, görüntülediğiniz kullanıcı için Windows 10 güncelleştirme halkası atamalarını görebilirsiniz.  

### <a name="windows-defender-advanced-threat-protection-reporting-frequency-settings----1455974----"></a>Windows Defender Gelişmiş Tehdit Koruması raporlama sıklığı ayarları <!-- 1455974  -->
Windows Defender Gelişmiş Tehdit Koruması (WDATP) hizmeti yöneticilerin yönetilen cihazlar için raporlama sıklığını yönetmesine olanak sağlar. Yeni **Telemetri raporlama sıklığını hızlandır** seçeneğiyle, WDATP daha sık veri toplar ve riskleri değerlendirir. Raporlama için varsayılan ayar, hızı ve performansı en iyi duruma getirir. Raporlama sıklığını artırmak yüksek riskli cihazlar için yararlı olabilir. Bu ayar, **Cihaz yapılandırmaları** içinde **Windows Defender ATP** profilinde bulunabilir.

### <a name="audit-updates---1412961---"></a>Güncelleştirmeleri denetleme<!-- 1412961 -->  
Intune denetimi, Intune’la ilgili değişiklik işlemlerinin bir kaydını sağlar.  Tüm oluşturma, güncelleştirme, silme ve uzak görev işlemleri yakalanır ve bir yıl süreyle tutulur.  Azure portalı her iş yükü içinde son 30 günlük denetim verilerinin bir görünümünü sağlar ve bunlar filtrelenebilir.  Karşılık gelen bir Graph API, geçen yıl için depolanan denetim verilerinin alınmasına olanak sağlar.

Denetim **İZLEYİCİ** grubu altında bulunur. Her bir iş yükü için bir **Denetim Günlükleri** menü öğesi bulunur.

### <a name="company-portal-app-for-macos-is-available--1541700--"></a>Şirket Portalı uygulaması macOS için kullanılabilir<!--1541700-->
MacOS'daki Intune Şirketi Portalı, kayıtlı oldukları tüm cihazlar için kullanıcılarınıza gereken tüm bilgileri ve uyum bildirimlerini temiz bir şekilde görüntülemek için iyileştirilmiş güncel bir tecrübeye sahiptir. Ve Intune Şirketi Portalı bir cihaza dağıtıldığında, macOS için Microsoft AutoUpdate kendisine güncelleme sağlayacaktır. Yeni macOS için Intune Şirket Portalı’nı, bir macOS cihazından Intune Şirketi Portalı web sitesine girerek indirebilirsiniz.

### <a name="microsoft-planner-is-now-part-of-the-mobile-app-management-mam-list-of-approved-apps----1248473---"></a>Microsoft Planner, artık mobil uygulama yönetimi (MAM) onaylı uygulamalar listesinin bir parçasıdır <!-- 1248473 -->
IOS ve Android için Microsoft Planner uygulaması artık mobil uygulama yönetimi (MAM) için onaylanan uygulamaların bir parçasıdır. Uygulama, tüm kiracılara Azure portalındaki Intune App Protection dikey penceresi aracılığıyla yapılandırılabilir.
- [Onaylı uygulamaların MAM listesi](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) hakkında daha fazla bilgi edin.

### <a name="per-app-vpn-requirement-update-frequency-on-ios-devices-----1547061---"></a>iOS cihazlarında Uygulama Başına VPN gereksinimi güncelleştirme sıklığı  <!-- 1547061 -->  
Yöneticiler, artık iOS cihazlarındaki uygulamalar için Uygulama Başına VPN gereksinimlerini kaldırabilir; etkilenen cihazlar genellikle bir sonraki Intune iade etme işleminden sonra olacak ve bu da genellikle 15 dakika içinde gerçekleşecektir.  

### <a name="support-for-system-center-operations-manager-management-pack-for-exchange-connector---885457---"></a>Exchange Bağlayıcı için System Center Operations Manager yönetim paketi desteği<!-- 885457 -->
Exchange bağlayıcı için Sistem Merkezi İşlemleri Yöneticisi yönetim paketi, Exchange bağlayıcı günlüklerini ayrıştırmanıza yardımcı olmak için kullanılabilir. Bu özellik, sorun gidermeniz gerektiğinde Exchange bağlayıcıyı izlemek için size farklı yollar sunar.

### <a name="co-management-for-windows-10-devices----1243445---"></a>Windows 10 cihazları için ortak yönetim <!-- 1243445 -->
Ortak yönetim, geleneksel yönetimden modern yönetime bir köprü sağlar ve aşamalı bir yaklaşım ile bu geçişi yapmanızı sağlayan bir yol sunar. Ortak yönetim temelde Windows 10 cihazların, Configuration Manager ve Microsoft Intune tarafından eş zamanlı olarak yönetildiği ve Active Directory (AD) ile Azure Active Directory’ye (Azure AD) katıldığı bir çözümdür.  Bu yapılandırma size, her şeyi aynı anda taşıyamadığınız durumlarda kuruluşunuza uygun bir tempoda zaman içinde modernleştireceğiniz bir yol sunar.  

### <a name="restrict-windows-enrollment-by-os-version---245498---"></a>Windows Kaydını işletim sistemi sürümüyle kısıtlama<!-- 245498 -->
Bir Intune yöneticisi olarak cihaz kayıtları için Windows 10 en düşük ve en yüksek sürümleri belirtebilirsiniz. Bu kısıtlamaları, **Platform Yapılandırmaları** dikey penceresinde ayarlayabilirsiniz.

Intune, Windows 8.1 bilgisayarlar ve telefonların kaydını desteklemeye devam edecektir. Ancak yalnızca Windows 10 sürümleri için en düşük ve en yüksek sınırlar ayarlanabilir. 8\.1 cihazların kaydına izin vermek için en düşük sınırı boş bırakın.

### <a name="alerts-for-windows-autopilot-unassigned-devices----1631236---"></a>Windows AutoPilot’ta atanmamış cihazlar için uyarılar <!-- 1631236 -->
**Microsoft Intune** > **Cihaz kaydı** > **Genel bakış** sayfasında Windows AutoPilot atanmamış cihazlar için yeni bir uyarı mevcut. Bu uyarı, AutoPilot programından kaç tane cihaza AutoPilot dağıtım profili atanmamış olduğunu gösterir. Uyarıdaki bilgileri kullanarak profiller oluşturun ve bunları profil atanmamış cihazlara atayın. Uyarıya tıkladığınızda, Windows AutoPilot cihazların tam listesini ve cihazlar hakkında ayrıntılı bilgileri görürsünüz. Daha fazla bilgi için bkz. [Windows AutoPilot dağıtım programını kullanarak Windows cihazları kaydetme](../enrollment/enrollment-autopilot.md).


### <a name="refresh-button-for-devices-list------1333581---"></a>Cihazlar listesi için Yenile düğmesi   <!-- 1333581 -->
Cihazlar listesi otomatik olarak yenilenmediği için, yeni Yenile düğmesini kullanarak listede görüntülenen cihazları güncelleyebilirsiniz.

### <a name="support-for-symantec-cloud-certification-authority-ca----1333638---"></a>Symantec Cloud Sertifika Yetkilisi (CA) desteği <!-- 1333638 -->    
Intune artık Symantec Cloud CA’yı desteklemektedir. Böylece Intune Sertifika Bağlayıcısı, Symantec Cloud’dan Intune ile yönetilen cihazlara PKCS sertifikaları verebilir. Intune Sertifika Bağlayıcısı’nı Microsoft Sertifika Yetkilisi (CA) ile kullanıyorsanız, Symantec CA desteğini eklemesi için mevcut Intune Sertifika Bağlayıcısı kurulumunu kullanabilirsiniz.

### <a name="new-items-added-to-device-inventory----1404455---"></a>Cihaz envanterine yeni öğeler eklendi  <!--1404455 -->
[Kayıtlı cihazların aldığı envanterde](../remote-actions/device-inventory.md) artık aşağıdaki yeni öğeler kullanılabilir:

- WIFI Mac adresi
- Toplam depolama alanı
- Toplam boş alanı
- MEID
- Abone operatör

### <a name="set-access-for-apps-by-minimum-android-security-patch-on-the-device---1278463---"></a>Uygulamalara erişimi cihazdaki en düşük Android güvenlik düzeltme ekine göre ayarlama<!-- 1278463 -->   
Yönetici, yönetilen bir hesap altındaki yönetilen bir uygulamaya erişim kazanmak için cihazda yüklü olması gereken en düşük Android güvenlik düzeltme ekini belirleyebilir.

> [!Note]  
> Bu özellik, yalnızca Android 6.0+ cihazlarda Google tarafından yayınlanan düzeltme eklerini kısıtlar.

### <a name="app-conditional-launch-support---1193313---"></a>Uygulama koşullu başlatma desteği<!-- 1193313 -->
Artık BT yöneticileri, uygulama başlatıldığında mobil uygulama yönetiminde (MAM) sayısal PIN yerine bir geçiş kodu kullanılmasını zorlamak için Azure yönetici portalında bir gereksinim ayarlayabilir. Bu gereksinim ayarlanırsa kullanıcının, MAM etkin uygulamalara erişim almadan önce bir geçiş kodu ayarlaması ve istendiğinde bunu kullanması gerekir. Geçiş kodu, en az bir özel karakter veya büyük/küçük harf içeren sayısal PIN’dir. Intune’un bu sürümünde bu özellik, **yalnızca iOS’ta** geçerli olacaktır. Intune, sayısal PIN’e benzer bir geçiş kodunu destekler, uzunluk alt sınırı belirler ve karakter ile dizi tekrarlarına izin verir. Bu özellik, Intune App SDK'yi hedef kod uygulamalarında uygulanacak parola ayarlarının yapılması için bu özelliğe ait kodla tümleştirmek için uygulamaların (WXP, Outlook, Managed Browser, Yammer) katılımını gerektirir.

### <a name="app-version-number-for-line-of-business-in-device-install-status-report---1233999---"></a>Cihaz yükleme durum raporunda iş kolu için uygulama sürüm numarası<!-- 1233999 -->
Bu sürümle birlikte cihaz yükleme durum raporu, iOS ve Android için iş kolu uygulamalarında uygulama sürüm numarasını görüntüler. Bu bilgiyi kullanarak uygulamalarınızda sorun giderebilir veya eski uygulama sürümleri çalıştıran cihazları bulabilirsiniz.

### <a name="admins-can-now-configure-the-firewall-settings-on-a-device-using-a-device-configuration-profile---951708---"></a>Yöneticiler artık bir cihazda cihaz yapılandırma profili kullanarak Güvenlik Duvarı ayarlarını yapılandırabilir<!-- 951708 -->   
Yöneticiler, cihazlar için güvenlik duvarını etkinleştirebilir ve etki alanı, özel ve ortak ağlar için çeşitli protokoller yapılandırabilir.  Bu güvenlik duvarı ayarlarını “Uç nokta koruma” profilinde bulabilirsiniz.

### <a name="windows-defender-application-guard-helps-protect-devices-from-untrusted-websites-as-defined-by-your-organization---958257---"></a>Windows Defender Application Guard, cihazları kuruluşunuz tarafından belirlenen güvenilmeyen web sitelerinden korumaya yardımcı olur<!-- 958257 -->   
Yöneticiler, bir Windows Bilgi Koruması iş akışını veya cihaz yapılandırmaları altındaki yeni “Ağ sınırı” profilini kullanarak siteleri “güvenilir” veya “kurumsal” olarak tanımlayabilir. Bir 64 bit Windows 10 cihazın güvenilir ağ sınırında listelenmemiş tüm siteler, Microsoft Edge ile görüntülenmeleri durumunda bir Hyper-V sanal bilgisayarındaki tarayıcıda açılır.

Application Guard’ı, “Uç nokta koruma” profilindeki cihaz yapılandırma profillerinde bulabilirsiniz. Yöneticiler buradan, sanallaştırılmış tarayıcı ile konak makine, güvenilmeyen siteler ile güvenilir siteler ve sanallaştırılmış tarayıcıda oluşturulan verileri depolama arasındaki etkileşimi yapılandırabilir. Bir cihazda Application Guard’ı kullanmak için önce bir ağ sınırı yapılandırılmalıdır. Bir cihaz için yalnızca bir ağ sınırı tanımlamak önemlidir.  

### <a name="windows-defender-application-control-on-windows-10-enterprise-provides-mode-to-trust-only-authorized-apps---1031096---"></a>Windows 10 Enterprise’da Windows Defender Uygulama Denetimi, yalnızca yetkilendirilmiş uygulamalara güvenme modu sağlar<!-- 1031096 -->    
Her gün oluşturulan binlerce yeni kötü amaçlı dosya karşısında virüsten koruma imza tabanlı algılama kullanmak artık yeni saldırılara karşı yeterli korumayı sağlayamıyor. Windows 10 Enterprise’da Windows Defender Uygulama Denetimi'ni kullanarak cihaz yapılandırmasını, uygulamaların bir virüsten koruma veya başka bir güvenlik çözümü tarafından engellenmediği durumda güvenilir olduğu bir moddan, işletim sisteminin yalnızca kuruluşunuzun yetkilendirdiği güvenilir uygulamalara güvendiği bir moda değiştirebilirsiniz. Uygulamalara güveni Windows Defender Uygulama Denetimi'nde atarsınız.

Intune kullanarak uygulama denetleme ilkelerini “yalnızca denetim” modunda veya zorlama modunda yapılandırabilirsiniz. Uygulamalar, “yalnızca denetim” modunda çalıştırıldığında engellenmez. “Yalnızca denetim” modu, tüm olayları yerel istemci günlüklerine kaydeder. Ayrıca, yalnızca Windows bileşenleri ve Microsoft Mağazası uygulamalarının mı yoksa Intelligent Security Graph tarafından tanımlanan diğer itibarlı uygulamaların da mı çalışmaya izni olacağını yapılandırabilirsiniz.

### <a name="window-defender-exploit-guard-is-a-new-set-of-intrusion-prevention-capabilities-for-windows-10---1063615---"></a>Windows Defender Exploit Guard, Windows 10 için yeni bir yetkisiz erişim önleme işlevleri dizisi<!-- 1063615 -->   
Windows Defender Exploit Guard; uygulamaların kötüye kullanımını azaltacak özel kurallar içerir, makro ve betik tehditlerini önler, düşük itibarlı IP adreslerine yapılan ağ bağlantılarını otomatik olarak önler ve fidye yazılımı ile bilinmeyen tehditlere karşı verileri korur. Windows Defender Exploit Guard aşağıdaki bileşenlerden oluşur:

- **Saldırı Yüzeyi Azaltma** makro, betik ve e-posta tehditlerini önlemenize yardımcı kurallar sağlar.
- **Denetimli Klasör erişimi** korumalı klasörlerin içeriklerine erişimi otomatik olarak engeller.
- **Ağ Filtresi** herhangi bir uygulamanın düşük itibarlı bir IP/etki alanına bağlantı yapmasını engeller
- **Exploit Protection** bir uygulamanın kötüye kullanılmasını önlemek üzere kullanılabilecek bellek, denetim akışı ve ilke kısıtlamaları sağlar.

### <a name="manage-powershell-scripts-in-intune-for-windows-10-devices---790537---"></a>Windows 10 cihazlar için Intune’da PowerShell betiklerini yönetme<!-- 790537 -->

Intune yönetim uzantısı, Intune’da PowerShell betiklerini Windows 10 cihazlarda çalıştırmak için karşıya yüklemenize olanak sağlar. Uzantı, Windows 10 mobil cihaz yönetimi (MDM) özelliklerini tamamlar ve modern yönetime geçiş yapmanızı kolaylaştırır. Ayrıntılar için bkz. [Windows 10 cihazlar için Intune’da PowerShell betiklerini yönetme](../apps/intune-management-extension.md).

### <a name="new-device-restriction-settings-for-windows-10--------1308850---"></a>Windows 10 için yeni cihaz kısıtlama ayarları     <!-- 1308850 -->
- Mesajlaşma (yalnızca mobil) - sınamayı ve MMS iletilerini devre dışı bırakır
- Parola - FIPS’yi ve kimlik doğrulaması için ikincil Windows Hello cihazların kullanımını etkinleştirme ayarları 
- Görüntü - eski uygulamalar için GDI Ölçeklendirmeyi açma ve kapama ayarları

### <a name="windows-10-kiosk-mode-device-restrictions---1308872---"></a>Windows 10 bilgi noktası modu cihaz kısıtlamaları<!-- 1308872 -->   
Windows 10 cihaz kullanıcılarını bilgi noktası moduna kısıtlayabilirsiniz, böylece kullanıcılar önceden tanımlı bir uygulamalar dizisiyle sınırlanır.  Bunun için bir Windows 10 cihaz kısıtlama profili oluşturun ve Bilgi Noktası ayarlarını ayarlayın.

Bilgi noktası modu şu iki modu destekler: **tek uygulama** (kullanıcının yalnızca bir uygulama çalıştırmasına izin verir) veya **çok uygulama** (bir dizi uygulamaya erişme izni verir).  Kullanıcı hesabı ve cihaz adını siz belirlersiniz, böylece desteklenen uygulamalar belirlenir.  Kullanıcı oturum açtığında belirlenen uygulamalarla sınırlı olur.  Daha fazla bilgi için bkz. [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp). 

Bilgi noktası modu şunları gerektirir:

- MDM yetkilisi Intune olmalıdır.
- Uygulamalar hedef cihazda yüklü olmalıdır.
- Cihaz [doğru bir şekilde sağlanmalıdır](https://docs.microsoft.com/windows/configuration/set-up-a-kiosk-for-windows-10-for-desktop-editions).

### <a name="new-device-configuration-profile-for-creating-network-boundaries---1311967---"></a>Ağ sınırları oluşturmak için yeni cihaz yapılandırma profili<!-- 1311967 -->   
**Ağ sınırı** adı verilen yeni cihaz yapılandırma profilini diğer cihaz yapılandırma profillerinizin yanında bulabilirsiniz. Bu profili kullanarak kurumsal ve güvenilir olarak değerlendirilmesini istediğiniz çevrimiçi kaynakları tanımlayabilirsiniz. Windows Defender Application Guard ve Windows Bilgi Koruması gibi özelliklerin cihazda kullanılabilmesi için *önce* bir ağ sınırı tanımlamanız gerekir. Her cihaz için yalnızca bir ağ sınırı tanımlamanız önemlidir.

Güvenilir olarak değerlendirilmesini istediğiniz kuruluş bulut kaynakları, IP adresi aralıkları ve dahili proxy sunucularını tanımlayabilirsiniz. Tanımlandıktan sonra bu ağ sınırı, Windows Defender Application Guard ve Windows Bilgi Koruması gibi diğer özellikler tarafından kullanılır.

### <a name="two-additional-settings-for-windows-defender-antivirus---1338409---"></a>Windows Defender Virüsten Koruma için iki ek ayar<!-- 1338409 -->  
**Dosya engelleme düzeyi**

| | |
|---|---|
| Yapılandırılmadı | **Yapılandırılmadı**, varsayılan Windows Defender Virüsten Koruma engelleme düzeyini kullanır ve güvenli klasörleri algılama riskini artırmadan güçlü bir algılama sağlar. |
| Yüksek | **Yüksek** güçlü bir algılama düzeyi sağlar.
| Yüksek +  | **Yüksek +** Yüksek düzeyine istemci performansını etkileyebilecek ek koruma önlemleri getirir.
| Sıfır tolerans  | **Sıfır tolerans** tüm bilinmeyen yürütülebilir dosyaları engeller. |

**Yüksek** düzeyini ayarlamak, düşük ihtimalle de olsa bazı güvenli dosyaların algılanmasına yol açabilir.
Dosya engelleme düzeyini varsayılan **Yapılandırmadı** düzeyine ayarlamanızı öneririz.

**Bulut tarafından dosya tarama için zaman aşımı uzantısı**  

| | |
|--|--|
| Saniye sayısı (0-50) | Windows Defender Virüsten Koruma’nın buluttan sonuç beklerken bir klasörü engellemesi için geçmesi gereken en uzun süreyi belirtin. Varsayılan süre 10 saniyedir: burada belirtilen ek süre (en fazla 50 saniyeye kadar) bu 10 saniyenin üzerine eklenir. Çoğu zaman tarama, belirtilen en uzun süreden daha kısa zamanda biter. Bu süreyi artırmak, bulutun şüpheli klasörleri ayrıntılı olarak araştırmasına olanak verir. Bu ayarı etkinleştirip fazladan en az 20 saniye belirtmenizi öneririz. |

### <a name="citrix-vpn-added-for-windows-10-devices---1512457---"></a>Windows 10 cihazlar için Citrix VPN eklendi<!-- 1512457 -->  
Windows 10 cihazlar için Citrix VPN’i yapılandırabilirsiniz. Windows 10 ve üzeri sürümler için bir VPN yapılandırırken, **Temel VPN** dikey penceresinde bulunan *Bağlantı türü seçin* listesinden Citrix VPN’i seçebilirsiniz.

> [!Note]
> Citrix yapılandırması iOS ve Android için zaten mevcuttu.

### <a name="wi-fi-connections-support-pre-shared-keys-on-ios---1550823---"></a>Wi-Fi bağlantıları iOS’ta önceden paylaşılan anahtarları destekliyor<!-- 1550823 -->
Müşteriler, Wi-Fi profillerini, iOS cihazlarda WPA/WPA2 Kişisel bağlantıları için önceden paylaşılan anahtarları (PSK) kullanacak şekilde yapılandırabilirler. Bu profiller, kullanıcının cihazı Intune’a kaydedildiğinde cihaza gönderilir.

Profil cihaza gönderildikten sonraki adım, profil yapılandırmasına bağlıdır.  Otomatik olarak bağlanmaya ayarlıysa, ağa ihtiyaç olduğunda otomatik olarak bağlanır.  Profil el ile bağlanıyorsa, kullanıcı bağlantıyı el ile etkinleştirmelidir.  

### <a name="access-to-managed-app-logs-for-ios---1469920---"></a>iOS için yönetilen uygulama günlüklerine erişim<!-- 1469920 -->
Managed Browser yüklü olan son kullanıcılar artık tüm Microsoft uygulamalarının yönetim durumunu görüntüleyebilir ve yönetilen iOS uygulamalarında sorun giderme için günlük gönderebilirler.

Bir iOS cihaz üzerinde Managed Browser’da sorun giderme modunu nasıl etkinleştireceğini öğrenmek için bkz. [iOS’a Managed Browser kullanarak yönetilen uygulama günlüklerine erişme](../apps/app-configuration-managed-browser.md#how-to-access-to-managed-app-logs-using-the-managed-browser-on-ios).

### <a name="improvements-to-device-setup-workflow-in-the-company-portal-for-ios-in-version-290---1417174---"></a>Sürüm 2.9.0'da iOS için Şirket Portalı'nda cihaz kurulum iş akışındaki iyileştirmeler<!-- 1417174 -->

iOS için Şirket Portalı uygulamasında cihaz kurulum iş akışı geliştirildi. Dil artık daha kullanıcı dostu ve mümkün olan yerlerde ekranları birleştirdik. Kurulum metninde şirket adınızın kullanılmasıyla diliniz, firmanıza özel hale geldi. Bu güncelleştirilmiş iş akışını  [Uygulama UI sayfasındaki yenilikler](../whats-new-app-ui.md) sayfasında görebilirsiniz.


### <a name="user-entity-contains-latest-user-data-in-data-warehouse-data-model---1544273---"></a>Kullanıcı varlığı Veri Ambarı veri modelinde en son kullanıcı verilerini içeriyor<!-- 1544273 -->
Intune Veri Ambarı eri modelinin ilk sürümü yalnızca son geçmiş Intune verilerini içeriyordu. Rapor oluşturucular bir kullanıcının geçerli durumunu yakalayamadı. Bu güncelleştirmede, **Kullanıcı varlığı** en son kullanıcı verileriyle doldurulur.

<!-- ########################## -->
## <a name="october-2017"></a>Ekim 2017

### <a name="ios-and-android-line-of-business-app-version-number-is-visible---1380712---"></a>iOS ve Android iş kolu uygulaması sürüm numarası görünürdür<!-- 1380712 -->

Intune’da uygulamalar artık iOS ve Android iş kolu uygulamaları için sürüm numarasını görüntüler. Numara, Azure portalındaki uygulama listesinde ve uygulama genel bakış dikey penceresinde görüntülenir. Son kullanıcılar, uygulama numarasını Şirket Portalı uygulamasında ve web portalında görebilir.

__Tam sürüm numarası__ Tam sürüm numarası, uygulamanın belirli bir sürümünü tanımlar. Numara _Sürüm_(_Derleme_) olarak görünür. Örneğin, 2.2(2.2.17560800)

Tam sürüm numarası iki bileşenden oluşur:

- **Sürüm**  
  Sürüm numarası uygulamanın insan tarafından okunabilir yayın numarasıdır. Bu, son kullanıcılar tarafından uygulamanın farklı yayınlarını tanımlamak için kullanılır.

- **Derleme Numarası**  
  Derleme numarası, uygulama algılamada ve uygulamayı programlı olarak yönetmek için kullanılabilen dahili bir numaradır. Derleme numarası, uygulamanın koddaki değişikliklere başvuran bir yinelemesini ifade eder.

[Microsoft Intune Uygulama SDK’sını kullanmaya başlama](../developer/app-sdk-get-started.md#line-of-business-app-version-numbers) içinde sürüm numaraları ve iş kolu uygulamaları geliştirme hakkında daha fazla bilgi edinin.

### <a name="device-and-app-management-integration---677972---"></a>Cihaz ve uygulama yönetim tümleştirmesi<!-- 677972 -->   
Artık Intune’un mobil cihaz yönetimi (MDM) ve mobil uygulama yönetimi (MAM) işlevleri Azure portalından erişilebilir olduğu için Intune, uygulama ve cihaz yönetiminde BT yönetici deneyimini tümleştirmeye başladı. Bu değişikliklerin amacı, cihaz ve uygulama yönetimi deneyiminizi kolaylaştırmaktır.

[Intune destek ekibi blogundan](https://blogs.technet.microsoft.com/intunesupport/2017/09/19/support-tip-setting-up-communication-between-mam-managed-and-mdm-managed-apps/) MDM ve MAM değişiklikleri hakkında daha fazla bilgi edinebilirsiniz.

### <a name="new-enrollment-alerts-for-apple-devices---1471790---"></a>Apple cihazları için yeni kayıt uyarıları<!-- 1471790 -->
Kayıt için genel bakış sayfası, BT yöneticileri için Apple cihazlarının yönetimiyle ilgili kullanışlı uyarılar gösterir. Uyarılar, Apple MDM anında iletme sertifikasının süresi neredeyse dolduğunda veya dolduğunda; Aygıt Kayıt Programı belirtecinin süresi neredeyse dolduğunda veya dolduğunda ve Aygıt Kayıt Programında atanmamış cihazlar olduğunda Genel Bakış sayfasında görüntülenir.

### <a name="support-token-replacement-for-app-configuration-without-device-enrollment---1080364---"></a>Cihaz kaydı olmadan uygulama yapılandırması için belirteç değiştirme desteği<!-- 1080364 -->

Kayıtlı olmayan cihazlardaki uygulamaların uygulama yapılandırmalarında dinamik değerler için belirteçleri kullanabilirsiniz. Daha fazla bilgi için bkz. [Cihaz kaydı olmadan yönetilen uygulamalar için uygulama yapılandırma ilkeleri ekleme](../apps/app-configuration-policies-managed-app.md).

### <a name="updates-to-the-company-portal-app-for-windows-10--1299474--"></a>Windows 10 için Şirket Portalı uygulamasındaki güncelleştirmeler<!--1299474-->
Windows 10 için Şirketi Portalı uygulamasındaki Ayarlar sayfası, ayarların ve amaçlanan kullanıcı işlemlerinin tüm ayarlarda daha tutarlı olmasını sağlamak için güncelleştirildi. Ayrıca, diğer Windows uygulamalarının düzeniyle eşleşecek şekilde güncelleştirildi. Önce/sonra resimlerini [Uygulama UI'sındaki yenilikler](../whats-new-app-ui.md) sayfasında bulabilirsiniz.

### <a name="inform-end-users-what-device-information-can-be-seen-for-windows-10-devices--1337920--"></a>Son kullanıcılara Windows 10 cihazlarında hangi cihaz bilgisinin görülebileceğini bildirin<!--1337920-->
Windows 10 için Şirket Portalı uygulamasındaki Cihaz Ayrıntıları ekranına **Sahiplik Türü** ekledik. Bu, kullanıcıların doğrudan bu sayfadan Intune Son Kullanıcı belgelerinden gizlilik hakkında daha fazla bilgi bulmasına olanak tanır. Ayrıca, bu bilgileri **hakkında** ekranında bulabilirsiniz.

### <a name="feedback-prompts-for-the-company-portal-app-for-android--1165249--"></a>Android için Şirket Portalı uygulaması için geri bildirim istekleri<!--1165249-->
Android için Şirket Portalı uygulaması şimdi son kullanıcı geri bildirimi istiyor. Bu geri bildirim doğrudan Microsoft’a gönderilir ve son kullanıcılara uygulamayı genel Google Play Store’da gözden geçirme olanağı tanır. Geri bildirim gerekli değildir ve kullanıcılar, uygulamayı kullanmaya devam edebilmesi için kolayca kapatılabilir.

<!-- #### Update to what device details an organization can see 1616825
The Company Portal app for Android can now use geofencing to protect access to company resources. It uses network details such as IP address, default gateway address, and Domain Name System (DNS) to determine whether to allow access to protected company resources.-->

### <a name="helping-your-users-help-themselves-with-the-company-portal-app-for-android---1573324-1573150-1558616-1564878---"></a>Kullanıcılarınızın Android için Şirket Portalı uygulamasını kullanmasına yardımcı olma<!-- 1573324, 1573150, 1558616, 1564878 -->

Android için Şirket Portalı uygulaması, son kullanıcıların yeni kullanım durumlarını anlamaları ve mümkün olduğunda kendi kendilerine çözümlemeleri için yönergeler ekledi.
- Son kullanıcılar ekleyebilecekleri en fazla cihaz sayısına ulaştıysa bir cihazı kaldırmak üzere [Azure Active Directory portalına](https://account.activedirectory.windowsazure.com/r/#/profile) yönlendirilir.
- Son kullanıcılara [Samsung Knox cihazlarında etkinleştirme hatalarını düzeltmek](https://go.microsoft.com/fwlink/?linkid=859718) veya [güç tasarrufu modunu devre dışı bırakmak](/intune-user-help/power-saving-mode-android) için izlenecek adımlar verilir. Bu çözümlerden biri sorunları çözmezse [günlükleri Microsoft’a göndermeye](/intune-user-help/send-logs-to-microsoft-android) yönelik bir açıklama sağlarız.

### <a name="new-resolve-action-available-for-android-devices---1583480---"></a>Android cihazlar için yeni 'Çözümleme' eylemi kullanılabilir<!-- 1583480 -->

Android için Şirket Portalı uygulaması _Cihaz ayarlarını güncelleştirme_ sayfasında bir 'Çözümleme' eylemi tanıtıyor. Bu seçeneği belirlemek son kullanıcıyı doğrudan cihazlarının uyumsuz olmasına neden olan ayara götürür. Android için Şirket Portalı uygulaması şu anda bu eylemi [cihaz geçiş kodu](/intune-user-help/set-your-pin-or-password-android), [USB hata ayıklama](/intune-user-help/you-need-to-turn-off-usb-debugging-android) ve [Bilinmeyen Kaynaklar](/intune-user-help/you-need-to-turn-off-unknown-sources-android) ayarları için destekler.

### <a name="device-setup-progress-indicator-in-android-company-portal---1565657---"></a>Android Şirket Portalı uygulamasında cihaz kurulumu ilerleme göstergesi<!-- 1565657 -->
Android için Şirket Portalı uygulaması, bir kullanıcı cihazını kaydettiğinde bir cihaz kurulumu ilerleme göstergesi gösterir. Gösterge, "Cihazınız ayarlanıyor...", ardından "Cihazınız kaydediliyor...", ardından "Cihazınızı kaydetme tamamlanıyor..." ve daha sonra "Cihaz kurulumu tamamlanıyor..." ile başlayan yeni durumlar gösterir.

### <a name="certificate-based-authentication-support-on-the-company-portal-for-ios--1029830--"></a>iOS için Şirket Portalı’nda sertifika tabanlı kimlik doğrulaması desteği<!--1029830-->
iOS için Şirket Portalı’na sertifika tabanlı kimlik doğrulaması (CBA) desteği ekledik. CBA kullanan kullanıcılar kullanıcı adını girer ve “Bir sertifika ile oturum aç” bağlantısına dokunur. CBA, Android ve Windows için Şirket Portalı’nda zaten destekleniyordu. [Şirket Portalı uygulamasında oturum açma](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal) sayfasından daha fazla bilgi edinebilirsiniz.

### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment---1334712---"></a>Kayıt durumuna bakılmaksızın kullanılabilir olan uygulamalar artık kayıt istemi yapılmadan yüklenebilir.<!-- 1334712 -->

Android Şirket Portalı uygulamasındaki kayıt durumuna bakılmaksızın kullanılabilir olan şirket uygulamaları, artık kayıt için istem yapılmadan yüklenebilir.

### <a name="windows-autopilot-deployment-program-support-in-microsoft-intune----747617----"></a>Microsoft Intune’da Windows AutoPilot Dağıtım Programı desteği <!-- 747617  -->
Artık Microsoft Intune’u Windows AutoPilot Dağıtım Programı ile birlikte kullanarak, BT birimine gerek kalmaksızın kullanıcılarınıza şirket cihazları sağlayabilirsiniz. İlk kez çalıştırma deneyimini (OOBE) özelleştirebilir ve kullanıcılarınızın cihazlarını Azure AD’ye katarak Intune’a kaydetmesi için yol gösterebilirsiniz. Microsoft Intune ve Windows AutoPilot birlikte çalıştığında işletim sistemi görüntülerinin dağıtım, bakım ve yönetim ihtiyacını ortadan kaldırır. Ayrıntılar için bkz. [Windows AutoPilot Dağıtım Programını kullanarak Windows cihazları kaydetme](../enrollment/enrollment-autopilot.md).

### <a name="quickstart-for-device-enrollment----1425655---"></a>Cihaz kaydı için hızlı başlangıç <!-- 1425655 --> 
**Cihaz kaydı** için artık hızlı başlangıç kullanılabilir. Hızlı başlangıç, platformları yönetmek ve kayıt işlemini yapılandırmak için bir başvuru tablosu sağlar. Her bir öğenin kısa açıklaması ve adım adım yönergeler içeren belgelere bağlantılar, başlangıcı basitleştirmek için kullanışlı belgeler sağlar.

### <a name="device-categorization---1427491---"></a>Cihazları kategorilere ayırma<!-- 1427491 -->
**Cihazlar > Genel Bakış** dikey penceresinde bulunan kayıtlı cihazlar platform grafiği cihazları Android, iOS, macOS, Windows ve Windows Mobile platformlarına göre düzenler.  Diğer işletim sistemlerini çalıştıran cihazlar “Diğer” başlığı altında toplanır.  Bu cihazlar arasında Blackberry, NOKIA ve diğerleri tarafından üretilen cihazlar vardır.  

Kiracınızda hangi cihazların etkilendiğini öğrenmek için **Yönet > Tüm cihazları**’ı seçin ve **Filtrele**’yi kullanarak **İşletim Sistemi** alanını sınırlayın.

### <a name="zimperium---new-mobile-threat-defense-partner-----954681---"></a>Zimperium - Yeni Mobil Tehdit Savunması iş ortağı  <!-- 954681 -->  
Microsoft Intune ile tümleştirilen bir mobil tehdit savunması çözümü olan Zemium tarafından gerçekleştirilen risk değerlendirmesine dayalı koşullu erişimi kullanarak mobil cihaz erişimini kontrol edebilirsiniz.

#### <a name="how-integration-with-intune-works"></a>Intune ile tümleştirme nasıl çalışır?
Risk, Zimperium çalıştıran cihazlardan toplanan telemetriye göre değerlendirilir. Intune cihaz uyumluluk ilkeleri aracılığıyla etkinleştirilen zem riskli risk değerlendirmesi temelinde EMS koşullu erişim ilkelerini yapılandırabilirsiniz. Bu, uyumlu olmayan cihazların algılanan tehditlere dayalı olarak şirket kaynaklarına erişmesine izin vermek veya erişimi engellemek için kullanabilirsiniz.

### <a name="new-settings-for-windows-10-device-restriction-profile-----978575-1308849---"></a>Windows 10 cihaz kısıtlama profili için yeni ayarlar <!--- 978575, 1308849, -->  
Windows Defender SmartScreen kategorisinde Windows 10 cihaz kısıtlama profiline yeni ayarlar ekliyoruz.

Windows 10 cihaz kısıtlama profili hakkında ayrıntılar için bkz. [Windows 10 ve üzeri cihaz kısıtlama ayarları](../configuration/device-restrictions-windows-10.md).

### <a name="remote-support-for-windows-and-windows-mobile-devices-----1070473---"></a>Windows ve Windows Mobile cihazlar için uzak destek  <!-- 1070473 -->  
Artık Intune, Windows ve Windows Mobile cihazlar çalıştıran kullanıcılarınıza uzaktan yardım etmenizi sağlamak için ayrıca satın alınan [TeamViewer](https://www.teamviewer.com) yazılımını kullanabilir.

### <a name="scan-devices-with-windows-defender---1280988--1280990-----"></a>Windows Defender ile cihazları tarama<!-- 1280988  1280990   -->
Artık yönetilen Windows 10 cihazlarda Windows Defender Virüsten Koruma ile **Hızlı Tarama**, **Tam Tarama** ve **İmza güncelleştirme** işlemlerini gerçekleştirebilirsiniz. Cihazın genel bakış dikey penceresinden cihazda çalıştırılacak eylemi seçin. Komut cihaza gönderilmeden önce eylemi onaylamanız istenir. 

**Hızlı tarama**: Hızlı tarama, kayıt defteri anahtarı ve bilinen Windows başlangıç klasörleri gibi kötü amaçlı yazılımların başladığı konumları tarar. Bir hızlı tarama ortalama beş dakika sürer. Bir dosya açıldığında, kapandığında ve bir kullanıcı bir klasöre gittiğinde dosyaları tarayan **Her zaman açık gerçek zamanlı koruma** ayarıyla birlikte kullanıldığında hızlı tarama, sistemde veya çekirdekte olması mümkün kötü amaçlı yazılımlara karşı koruma sağlamaya yardımcı olur. Tarama bittiğinde kullanıcılar, sonuçları cihazlarında görebilir. 

**Tam tarama**: Tam tarama, etkin olmayan bileşenleri bulunan ve daha kapsamlı bir temizlik gerektiren kötü amaçlı yazılım tehditleriyle karşı karşıya kalan cihazlarda gereklidir ve isteğe bağlı taramalar yapmaya yarar. Tam taramanın tamamlanması bir saati bulabilir. Tarama bittiğinde kullanıcılar, sonuçları cihazlarında görebilir. 

**İmza güncelleştirme**: İmza güncelleştirme komutu, Windows Defender Virüsten Koruma kötü amaçlı yazılım tanımlarını ve imzalarını güncelleştirir. Böylece Windows Defender Virüsten Koruma’nın kötü amaçlı yazılımı algılamada her zaman etkili olması sağlanır. Bu özellik yalnızca Windows 10 cihazlar içindir ve cihaz İnternet bağlantısı gerektirir. 

### <a name="the-enabledisable-button-is-removed-from-the-intune-certificate-authority-page-of-the-intune-azure-portal----1400455---"></a>Intune Azure portalının Intune Sertifika Yetkilisi sayfasından Etkinleştir/Devre Dışı Bırak düğmesi kaldırıldı <!-- 1400455 -->
 Intune’da sertifika bağlayıcısını ayarlama adımlarından birini kaldırıyoruz. Şu an sertifika bağlayıcısını indirip Intune konsolunda etkinleştiriyorsunuz. Ancak bağlayıcıyı Intune konsolunda devre dışı bıraktığınızda bağlayıcı, sertifika vermeye devam ediyor.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
Ekim ayından itibaren, Etkinleştir/Devre Dışı Bırak düğmesi Azure portalının Intune Sertifika Yetkilisi sayfasında görünmeyecek. Bağlayıcı işlevselliği aynı kalacak. Bağlayıcılar Intune’a kaydedilen cihazlara dağıtılmaya devam edecek. Sertifika bağlayıcısını indirmeye ve yüklemeye devam edebileceksiniz. Sertifikaların verilmesini durdurmak için artık sertifika bağlayıcısını devre dışı bırakmak yerine kaldırmanız gerekecek.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapmam gerek?
Mevcut durumda sertifika bağlayıcınız devre dışıysa bunu kaldırmanız gerekir.

### <a name="new-settings-for-windows-10-team-device-restriction-profile------1308838---"></a>Windows 10 Team cihaz kısıtlama profili için yeni ayarlar  <!--- 1308838 -->
Bu sürümde, Surface Hub cihazları denetlemenizi kolaylaştırmak için Windows 10 Team cihaz kısıtlama profiline pek çok yeni ayar ekledik.

Bu profil hakkında daha fazla bilgi için bkz. [Windows 10 Team cihaz kısıtlama ayarları](../configuration/device-restrictions-windows-10-teams.md).

### <a name="prevent-users-of-android-devices-from-changing-their-device-date-and-time----1333292---"></a>Android cihaz kullanıcılarının cihaz tarih ve saatini değiştirmelerini önleme <!-- 1333292 -->
Android cihaz kullanıcılarının cihaz tarih ve saatini değiştirmelerini önlemek için bir [Android özel cihaz ilkesi](../configuration/custom-settings-android.md) kullanabilirsiniz.

Bunun için bir Android özel ilkesini ./Vendor/MSFT/PolicyManager/My/System/AllowDateTimeChange ayar URI’si ile yapılandırın, bunu **TRUE** olarak ayarlayın ve gerekli gruplara atayın.

### <a name="bitlocker-device-configuration---1397398---"></a>BitLocker cihaz yapılandırması<!-- 1397398 -->
**Windows Şifreleme > Temel Ayarlar** yeni bir **Başka bir disk şifrelemesi için uyarı** ayarı barındırır. Bu ayar, kullanıcının cihazında kullanımda olabilecek bir diğer disk şifrelemesi için [uyarı istemini](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#allowwarningforotherdiskencryption) devre dışı bırakmanızı sağlar.  Uyarı istemi, cihazda BitLocker ayarlamadan önce son kullanıcı onayı gerektirir ve son kullanıcı tarafından onaylanana kadar BitLocker kurulumunu engeller.  Bu yeni ayar, son kullanıcı uyarısını devre dışı bırakır.


### <a name="volume-purchase-program-for-business-apps-will-now-sync-to-your-intune-tenant---800882---"></a>Volume Purchase Program for Business uygulamaları artık Intune kiracınızla eşitlenecek<!-- 800882 -->  
Üçüncü taraf geliştiriciler, iTunes Connect’te belirtilen yetkilendirilmiş Volume Purchase Program for Business (VPP) üyelerine özel olarak uygulama dağıtabilir. Bu İş için VPP üyeleri, Volume Purchase Program App Store’da oturum açabilir ve uygulamalarını satın alabilir.

Bu sürümle birlikte, son kullanıcı tarafından satın alınan iş için VPP uygulamaları, kullanıcının Intune kiracılarıyla eşitlenmeye başlayacak.

### <a name="select-apple-countryregion-store-to-sync-vpp-apps----1332311---"></a>VPP uygulamalarını eşitlemek için Apple ülke/bölge deposunu seçin <!-- 1332311 -->  
VPP belirtecinizi karşıya yüklerken Volume Purchase program (VPP) ülke/bölge deposunu yapılandırabilirsiniz. Intune, VPP uygulamalarını belirtilen VPP ülke/bölge deposundan tüm yerel ayarlar için eşitler.

> [!NOTE]  
> Intune, günümüzde yalnızca Intune kiracısının oluşturulduğu Intune yerel ayarıyla eşleşen VPP ülke/bölge deposundan VPP uygulamalarını eşitler.


### <a name="block-copy-and-paste-between-work-and-personal-profiles-in-android-for-work---1098994---"></a>Android for Work’te iş hesapları ve kişisel hesaplar arasında kopyalama ve yapıştırmayı engelleme<!-- 1098994 -->
Bu sürümle birlikte, Android for Work iş profilini kopyalama ve yapıştırmayı engelleyecek şekilde yapılandırabilirsiniz. Bu yeni ayarı **İş profili ayarları** altında bulunan **Android for Work** Platformunun **Cihaz kısıtlamaları** profilinde bulabilirsiniz.

### <a name="create-ios-apps-limited-to-specific-regional-apple-app-stores---1281692---"></a>Belirli bölgesel Apple App Store’lar ile sınırlı iOS uygulamaları oluşturma<!-- 1281692 -->
Apple App Store yönetilen uygulamasının oluşturulması sırasında ülke/bölge yerel ayarını belirleyebileceksiniz.

> [!Note]  
> Şu anda yalnızca ABD ülke/bölge deposunda bulunan Apple App Store yönetilen uygulamaları oluşturabilirsiniz.

### <a name="update-ios-vpp-user-and-device-licensed-apps----1305564---"></a>iOS VPP kullanıcı ve cihaz lisanslı uygulamaları güncelleştirme <!-- 1305564 -->  
Intune hizmeti yoluyla belirteç için satın alınmış tüm uygulamaları güncelleştirmek için bu iOS VPP belirtecini yapılandırabileceksiniz. Intune, uygulama mağazasındaki VPP uygulama güncelleştirmelerini algılayacak ve cihaz iade edildiğinde bunları cihaza otomatik olarak gönderecektir.

Bir VPP belirteci ayarlama ve otomatik güncelleştirmeyi etkinleştirme adımları için bkz. [Volume Purchase Program yoluyla satın alınmış iOS uygulamalarını Microsoft Intune ile yönetme] (/intune/vpp-apps-ios).


### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model---1187917---"></a>Intune Veri Ambarı veri modeline kullanıcı cihaz ilişkisi varlığı eklendi<!-- 1187917 -->
Artık kullanıcı ve cihaz varlık koleksiyonlarını ilişkilendiren kullanıcı cihaz ilişki bilgilerini kullanarak rapor ve veri görselleştirmeleri oluşturabilirsiniz. OData uç noktası veya özel bir istemci geliştirme yoluyla Veri Ambarı Intune sayfasından alınan Power BI dosyasından (PBIX) veri modeline erişebilirsiniz.

### <a name="review-policy-compliance-for-windows-10-update-rings---1067886---"></a>Windows 10 güncelleştirme halkaları için ilke uyumluluğunu gözden geçirme<!-- 1067886 -->
Yazılım güncelleştirmeleri > Güncelleştirme halkası başına dağıtımı durumu bölümünden Windows 10 güncelleştirme halkalarınız için bir ilke raporu görüntüleyebileceksiniz. İlke raporu, yapılandırdığınız güncelleştirme halkaları için dağıtım durumunu da içerir. 

### <a name="new-report-that-lists-ios-devices-with-older-ios-versions-----1352223---"></a>Eski iOS sürümleri ile iOS cihazlarını listeleyen yeni rapor  <!-- 1352223 -->
**Güncel olmayan iOS Cihazları** raporu, **Yazılım güncelleştirmeleri** çalışma alanında kullanılabilir. Raporda, bir iOS güncelleştirme ilkesi tarafından hedeflenen ve kullanılabilir güncelleştirmelere sahip denetimli iOS cihazların listesini görüntüleyebilirsiniz. Her cihaz için cihazın neden otomatik olarak güncelleştirilmediğiyle ilgili bir durum görüntüleyebilirsiniz. 

### <a name="view-app-protection-policy-assignments-for-troubleshooting----1475003---"></a>Sorun giderme için uygulama koruma ilke atamalarını görüntüleme<!--  1475003 -->
Gelecek sürümde, sorun giderme dikey penceresinde bulunan **Atamalar** açılan listesine **Uygulama koruma ilkesi** seçeneği eklenecek. Artık, uygulama koruma ilkelerini seçerek seçili kullanıcılara atanan uygulama koruma ilkelerini görebileceksiniz.



### <a name="improvements-to-device-setup-workflow-in-company-portal--1490692--"></a>Şirket Portalı’nda cihaz kurulum iş akışı iyileştirmeleri<!--1490692-->
Android için Şirket Portalı uygulamasında cihaz kurulum iş akışını iyileştirdik. Dil kolay anlaşılır ve şirketinize özgü bir durumdadır ve ekranlar mümkün olduğunca birleştirilmiştir. Bunları [uygulama kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md#week-of-october-2-2017) sayfasında görebilirsiniz.

### <a name="improved-guidance-around-the-request-for-access-to-contacts-on-android-devices--1484985--"></a>Android cihazlarda kişilere erişim isteği için iyileştirilmiş rehber<!--1484985-->

Android için Şirket Portalı uygulaması genellikle son kullanıcının Kişiler izni vermesini gerektirir. Son Kullanıcı bu erişimi reddederse, bundan sonra koşullu erişim sağlamak için bunları uyaran bir uygulama içi bildirim görür. 

### <a name="secure-startup-remediation-for-android--1490712--"></a>Android için güvenli başlangıç düzeltmesi<!--1490712-->

Android cihazı olan son kullanıcılar, Şirket Portalı uygulamasında uyumsuzluk sebebine dokunabilecek. Buna dokunmaları mümkün olduğunda, ayarlar uygulamasında sorunu çözebilecekleri konuma gidecekler. 

### <a name="additional-push-notifications-for-end-users-on-the-company-portal-app-for-android-oreo--1475932--"></a>Android Oreo için Şirket Portalı uygulamasındaki son kullanıcılara yönelik eklenen anında iletme bildirimleri<!--1475932-->

Android Oreo için Şirket Portalı uygulaması, Intune hizmetinden ilke alma gibi arka plan görevleri gerçekleştirdiğinde, son kullanıcılar bununla ilgili ilave bildirimler görür. Bu, Şirket Portalı’nın cihazlarda ne zaman yönetim görevleri gerçekleştirdiği hakkında son kullanıcılara daha fazla şeffaflık sağlar. Bu, Android Oreo için Şirket Portalı uygulamasındaki genel [Şirket Portalı kullanıcı arabirimi iyileştirmesinin](https://blogs.technet.microsoft.com/intunesupport/2017/08/21/android-8-0-o-behaviour-changes-and-microsoft-intune) bir parçasıdır. 

Android Oreo’da yeni kullanıcı arabirimi öğeleri için etkinleştirilmiş daha fazla iyileştirme mevcuttur.  Son kullanıcılar, Şirket Portalı’nın Intune hizmetinden ilke almak gibi arka plan görevleri gerçekleştirdiğine dair ilave bildirimler alacaktır.  Bu, Şirket Portalı’nın cihazda ne zaman yönetim görevleri gerçekleştirdiği hakkında son kullanıcılara daha fazla şeffaflık sağlar.

### <a name="new-behaviors-for-the-company-portal-app-for-android-with-work-profiles---1485783---"></a>İş profilleri bulunan Android için Şirket Portalı uygulamasında yeni davranışlar<!-- 1485783 -->

Bir Android for Work cihazını iş profiliyle kaydettiğinizde cihazda yönetim görevlerini gerçekleştiren uygulama, iş profilindeki Şirket Portalı’dır. 

Kişisel profilde MAM özellikli uygulama kullanmıyorsanız Android için Şirket Portalı uygulamasının artık hiçbir kullanımı yoktur. İş profili deneyimini iyileştirmek için Intune, başarılı bir iş profili kaydından sonra kişisel Şirket Portalı uygulamasını otomatik olarak saklar.

İstediğiniz zaman [Play Store’da Şirket Portalı](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) araması yapıp **Etkinleştir**’e dokunarak kişisel profilinizde Android için Şirket Portalı uygulamasını etkinleştirebilirsiniz.

### <a name="company-portal-for-windows-81-and-windows-phone-81-moving-to-sustaining-mode--1428681--"></a>Windows 8.1 ve Windows Phone 8.1 için Şirket Portalı, dayanıklılık moduna geçiyor<!--1428681-->

Ekim 2017’den itibaren Windows 8.1 ve Windows Phone 8.1 için Şirket Portalı uygulamaları, dayanıklılık moduna geçecek. Yani kayıt ve uyumluluk gibi mevcut senaryolar bu platformlarda desteklenmeye devam edecek. Bu uygulamalar Microsoft Mağazası gibi mevcut yayın kanallarından hala indirilebilir. 

Dayanıklılık moduna geçtikten sonra bu uygulamalar, yalnızca kritik güvenlik güncelleştirmelerini alacak. Bu uygulamalar için ek güncelleştirmeler veya özellikler yayımlanmayacak. Yeni özellikler için cihazları Windows 10 veya Windows 10 Mobile’a güncelleştirmenizi öneririz. 


### <a name="block-unsupported-samsung-knox-device-enrollment----1490695---"></a>Desteklenmeyen Samsung Knox cihaz kaydını engelleme <!-- 1490695 -->

Şirket Portalı uygulaması, yalnızca desteklenen Samsung Knox cihazları kaydetmeye çalışır. MDM kaydını önleyen Knox etkinleştirme hatalarının önüne geçmek için, yalnızca cihazın [Samsung tarafından yayınlanan cihazlar listesinde](https://www.samsungknox.com/knox-supported-devices/knox-workspace) yer aldığı durumlarda cihaz kaydı denenir. Samsung cihazların Knox destekleyen model numaraları olabilir ancak diğerlerinin olamaz. Satın alma dağıtma işlemlerinden önce, cihazınızın kurumsal bayisinden Knox uyumluluğunu doğrulayın. [Android ve Samsung Knox Standard ilke ayarları](supported-devices-browsers.md#intune-supported-web-browsers)’nda doğrulanan cihazların tam listesini bulabilirsiniz.

### <a name="end-of-support-for-android-43-and-lower---1171126-1326920---"></a>Android 4.3 ve altı sürümler için desteğin son bulması<!-- 1171126, 1326920 -->
Yönetilen uygulamalar ve Android için Şirket Portalı uygulaması, şirket kaynaklarına erişim için Android 4.4 ve üzeri sürümleri gerektirecek. Aralık ayında ise tüm kayıtlı cihazlar zorla devre dışı bırakılacak ve böylece şirket kaynaklarına erişimi kaybedeceklerdir. MDM’siz uygulama koruma ilkeleri kullanıyorsanız uygulamalar güncelleştirme almayacak ve deneyimlerinin kalitesi zamanla düşecek.

### <a name="inform-end-users-what-device-information-can-be-seen-on-enrolled-devices--1165314--"></a>Kayıtlı cihazlarda hangi cihaz bilgilerinin görülebileceği hakkında son kullanıcıları bilgilendirme<!--1165314-->
Tüm Şirket Portalı uygulamalarında Cihaz Ayrıntıları ekranına **Sahiplik Türü** ekliyoruz. Böylece kullanıcılar, doğrudan [Şirketiniz hangi bilgileri görebilir?](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune) makalesinden gizlilik hakkında bilgi edinebilecekler. Bu değişiklik, yakın zamanda tüm Şirket Portalı uygulamalarında sunulacak. iOS için bu değişikliği [Eylül](#september-2017) ayı içinde duyurduk.

<!-- ########################## -->
## <a name="september-2017"></a>Eylül 2017

### <a name="intune-supports-ios-11--1428975--"></a>Intune, iOS 11’i destekliyor<!--1428975-->
Intune, iOS 11’i destekliyor. Bu, daha önce [Intune Destek bloğunda](https://blogs.technet.microsoft.com/intunesupport/2017/09/12/support-tip-intune-support-for-ios-11/) duyurulmuştu.

### <a name="end-of-support-for-ios-80---1164477---"></a>iOS 8.0 desteğinin sona ermesi<!-- 1164477 -->
Yönetilen uygulamalar ve iOS için Şirket Portalı uygulaması, şirket kaynaklarına erişim için iOS 9.0 ve üzeri sürümleri gerektirecek. Eylül ayından önce güncelleştirmeyen cihazlar, Şirket Portalı veya diğer uygulamalara erişemeyecek. 

### <a name="refresh-action-added-to-the-company-portal-app-for-windows-10--1132468--"></a>Windows 10 için Şirket Portalı uygulamasına yenileme eylemi eklendi<!--1132468-->
Windows 10 için Şirket Portalı uygulaması, mobil cihazlarda aşağı çekerek veya masaüstü cihazlarda F5’e basarak kullanıcılara uygulamadaki verileri yenileme imkanı sunar.

### <a name="inform-end-users-what-device-information-can-be-seen-for-ios--739894--"></a>iOS için hangi cihaz bilgilerinin görülebileceği hakkında son kullanıcıları bilgilendirme<!--739894-->

iOS için Şirket Portalı’nda Cihaz Ayrıntıları ekranına **Sahiplik Türü** ekledik. Bu, kullanıcıların doğrudan bu sayfadan Intune Son Kullanıcı belgelerinden gizlilik hakkında daha fazla bilgi bulmasına olanak tanır. Ayrıca, bu bilgileri hakkında ekranında bulabilirsiniz.

### <a name="allow-end-users-to-access-the-company-portal-app-for-android-without-enrollment---1169910---"></a>Son kullanıcıların kayıt yapmadan Android için Şirket Portalı uygulamasına erişmelerine izin verme<!---1169910--->

Son kullanıcılar yakın zamanda cihazlarını kaydetmeden Android için Şirket Portalı uygulamasına erişebilecek. Uygulama Koruma İlkeleri kullanan kuruluşlardaki son kullanıcılar artık Şirket Portalı uygulamasını açtıklarında cihazlarını kaydetmelerine yönelik komut istemleri almayacaklar. Son kullanıcılar ayrıca cihaz kaydı yapmaksızın Şirket Portalı’dan uygulama yükleyebilecek. 


### <a name="easier-to-understand-phrasing-for-the-company-portal-app-for-android---1396349---"></a>Android için Şirket Portalı uygulamasında daha kolay anlaşılır bir dil<!---1396349--->  

Android için Şirket Portalı uygulamasında kayıt işlemi, son kullanıcıların kaydını kolaylaştırmak adına yeni metinlerle düzenlendi. Özel kayıt belgeleriniz varsa bunları, değişiklikleri yansıtması için güncelleştirmelisiniz. [Intune son kullanıcı uygulamaları için kullanıcı arabirimi güncelleştirmeleri](whats-new-app-ui.md#week-of-september-11-2017) sayfamızda örnek görüntüleri bulabilirsiniz.

### <a name="windows-10-company-portal-app-added-to-windows-information-protection-allow-policy---677129---"></a>Windows 10 Şirket Portalı uygulaması, Windows Bilgi Koruması izin ilkesine eklendi<!-- 677129 -->

Windows 10 Şirket Portalı uygulaması, Windows Bilgi Koruması’nı (WIP) destekleyecek şekilde güncelleştirildi. Uygulama, WIP izin ilkesine eklenebilecek. Bu değişiklik ile uygulamanın **Muaf** listesine eklenme gerekliliği ortadan kalkacak.


<!-- ########################## -->
## <a name="august-2017"></a>Ağustos 2017

### <a name="improvements-to-device-overview---1404453---"></a>Cihaz önizlemesi iyileştirmeleri<!-- 1404453 -->  
Cihaz önizlemesi iyileştirmeleri artık kayıtlı cihazları gösterirken Exchange ActiveSync tarafından yönetilen cihazları göstermiyor. Exchange ActiveSync cihazları, kayıtlı cihazlarla aynı yönetim seçeneklerine sahip değil. Azure portalında Intune’da kayıtlı cihaz sayısını ve platforma göre kayıtlı cihaz sayısını görüntülemek için, **Cihazlar** > **Genel Bakış**‘a gidin.

### <a name="improvements-to-device-inventory-collected-by-intune"></a>Intune tarafından toplanan cihaz envanteri geliştirmeleri
<!-- 961134, 1104426, 1281327, 1333543 -->
Bu sürümde, yönettiğiniz cihazlar tarafından toplanan envanter bilgilerinde aşağıdaki iyileştirmeleri yaptık:
 
- Android cihazlarda artık her cihaz için cihaz envanterine son düzeltme eki düzeyini gösteren bir sütun ekleyebilirsiniz. Bunu görmek için cihaz listenize **Güvenlik düzeltme eki düzeyi** sütununu ekleyin.
- Cihaz görünümünü filtrelerken artık cihazları kayıt tarihlerine göre filtreleyebilirsiniz. Örneğin, yalnızca belirttiğiniz bir tarihten sonra kaydedilen cihazları görüntüleyebilirsiniz.
- **Son Yer Bildirim Tarihi** öğesi tarafından kullanılan filtrede iyileştirmeler yaptık.
- Cihaz listesinde artık şirkete ait cihazların telefon numaralarını görüntüleyebilirsiniz.
Ayrıca, filtre bölmesini kullanarak cihazları telefon numarasına göre arayabilirsiniz.

Cihaz envanteri hakkında daha fazla ayrıntı için bkz. [Intune cihaz envanterini görüntüleme](../remote-actions/device-inventory.md).

### <a name="conditional-access-support-for-macos-devices"></a>MacOS cihazlar için koşullu erişim desteği 
<!-- 720172 -->
Artık, Mac cihazların Intune 'a kaydedilmesini ve cihaz uyumluluk ilkeleriyle uyumlu olmasını gerektiren bir koşullu erişim ilkesi ayarlayabilirsiniz. Örneğin kullanıcılar, macOS için Intune Şirket Portalı uygulamasını indirebilir ve Mac cihazlarını Intune’a kaydedebilir. Intune ise PIN, şifreleme, işletim sistemi sürümü ve Sistem Bütünlüğü gibi gereksinimleri kullanarak Mac cihazın uyumlu olup olmadığını değerlendirir.

- [MacOS cihazları Için koşullu erişim desteği](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)hakkında daha fazla bilgi edinin.

### <a name="company-portal-app-for-macos-is-in-public-preview---1484796---"></a>macOS için Intune Şirket Portalı uygulaması genel önizlemede<!---1484796--->
MacOS için Şirket Portalı uygulaması artık Enterprise Mobility + Security koşullu erişim için genel önizlemenin bir parçası olarak kullanılabilir. Bu sürüm, macOS 10.11 ve üzerini destekler. Buradan edinin: [https://aka.ms/macOScompanyportal](https://aka.ms/macOScompanyportal). 


### <a name="new-device-restriction-settings-for-windows-10"></a>Windows 10 için yeni cihaz kısıtlama ayarları    
<!--1063965, 1308850  -->
Bu sürümde, [Windows 10 cihaz kısıtlama profili](/intune/device-restrictions-windows-10) için aşağıdaki kategorilere yeni ayarlar ekledik:

- Windows Defender SmartScreen
- Uygulama mağazası

### <a name="updates-to-the-windows-10-endpoint-protection-device-profile-for-bitlocker-settings"></a>BitLocker ayarları için Windows 10 uç nokta koruma cihaz profili güncelleştirmeleri
<!--1459533 -->    
Bu sürümde, BitLocker’ın Windows 10 uç nokta koruma cihaz profilinde çalışması konusunda aşağıdaki iyileştirmeleri yaptık:
 
- BitLocker **işletim sistemi sürücüsü ayarları**' nın altında, **BITLOCKER uyumlu olmayan TPM yongasıyla**, daha önce **Engelle**' yi seçtiğinizde bu durum, BitLocker 'ın gerçekten izin vermesine neden olur. Artık bunu, seçildiğinde BitLocker’ı engelleyecek şekilde düzelttik.
- **BitLocker işletim sistemi sürücüsü ayarları**' nın altında, **sertifika tabanlı veri kurtarma aracısı**ayarı için artık sertifika tabanlı veri kurtarma aracısını açıkça engelleyebilirsiniz. Ancak varsayılan olarak bu aracıya izin verilir.
- **BitLocker sabit veri sürücü ayarları** altında **Veri kurtarma aracısı** ayarında artık kurtarma aracısını engelleyebilirsiniz.
Daha fazla bilgi için bkz. [Windows 10 ve üzeri sürümler için Endpoint Protection ayarları](../protect/endpoint-protection-windows-10.md).


### <a name="new-signed-in-experience-for-android-company-portal-users-and-app-protection-policy-users---621669---"></a>Android Şirket Portalı ve Uygulama Koruma İlkesi kullanıcıları için yeni oturum açma deneyimi<!-- 621669 -->
Son kullanıcılar artık Android Şirket Portalı’nı kullanarak cihazlarını kaydetmeden uygulamalara göz atabilir, cihazları yönetebilir ve BT iletişim bilgilerini görüntüleyebilir. Ayrıca, son kullanıcı zaten Intune Uygulama Koruma İlkeleri ile korunan bir uygulama kullanıyorsa ve Android Şirket Portalı'nı başlatırsa artık cihazı kaydetmek için bir istem almaz.

### <a name="new-setting-in-the-android-company-portal-app-to-toggle-battery-optimization--1405990--"></a>Android Şirket Portalı uygulamasında pil iyileştirmesini değiştirmek için yeni bir ayar<!--1405990-->
Android için Şirket Portalı uygulamasında **Ayarlar** sayfası, kullanıcıların Şirket Portalı ve Microsoft Authenticator uygulamaları için pil iyileştirmesini kolaylıkla kapatmalarına izin veren yeni bir ayara sahip. Ayarda gösterilen uygulama adı, hangi uygulamanın iş hesabını yönettiğine bağlı olarak değişecektir. E-posta ve veri eşitleyen iş uygulamalarının daha iyi çalışması için kullanıcıların pil iyileştirmesini kapatmalarını öneririz. 

### <a name="multi-identity-support-for-onenote-for-ios--------1234281---"></a>iOS için OneNote’ta çoklu kimlik desteği     <!-- 1234281 -->
Son kullanıcılar artık, iOS için Microsoft OneNote ile farklı hesaplar (iş ve kişisel) kullanabilir. Kullanıcıların kişisel not defterlerini etkilemeksizin iş not defterlerinde şirket verilerine uygulama koruma ilkeleri uygulanabilir. Örneğin bir ilke, bir kullanıcının iş not defterlerinde istediği bilgileri bulmasına izin verirken iş not defterlerinden kişisel not defterine şirket verilerini kopyalayıp yapıştırmasını engelleyebilir.
 
- Intune ile [uygulama koruması ve çoklu kimlik](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) destekleyen uygulamalar hakkında daha fazla bilgi edinin.

### <a name="new-settings-to-allow-and-block-apps-on-samsung-knox-standard-devices"></a>Samsung Knox Standard cihazlarda uygulamalara izin vermek veya bunları engellemek için yeni ayarlar
<!-- 1305423 822899-->  
Bu sürümde, aşağıdaki uygulama listelerini belirtmenizi sağlayan yeni [cihaz kısıtlama ayarları](../configuration/device-restrictions-android.md) ekliyoruz:
 
- Kullanıcıların yüklemesine izin verilen uygulamalar
- Kullanıcıların çalıştırması engellenen uygulamalar
- Cihazda kullanıcıdan gizlenen uygulamalar
 
Uygulamayı URL, paket adı ile veya yönettiğiniz uygulamalar listesinden belirtebilirsiniz.

### <a name="new-azure-ad-app-based-conditional-access-policy-ui-link-from-intune"></a>Intune 'dan yeni Azure AD uygulama tabanlı koşullu erişim ilkesi kullanıcı arabirimi bağlantısı
<!-- 1016201 -->
BT yöneticileri artık Azure AD iş yükünde yeni koşullu erişim ilkesi kullanıcı arabirimi aracılığıyla uygulama tabanlı koşullu ilkeler ayarlayabilir. Azure portal Intune Uygulama Koruması bölümünde yer alan uygulama tabanlı koşullu erişim, zamanında kalır ve yan yana zorlanır. Ayrıca, Intune iş yükünde yeni koşullu erişim ilkesi Kullanıcı arabirimine de kolaylık olan bir bağlantı vardır.

- [Azure AD 'de uygulama tabanlı koşullu erişim](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-technical-reference)hakkında daha fazla bilgi edinin.

<!-- ########################## -->
## <a name="july-2017"></a>Temmuz 2017

### <a name="restrict-android-and-ios-device-enrollment-restriction-by-os-version-----1333256--1245463----"></a>İşletim sistemi sürümüne göre Android ve iOS cihaz kaydını kısıtlama <!--- 1333256,  1245463 --->
Intune artık iOS ve Android kaydını işletim sistemi sürüm numarasına göre kısıtlamayı desteklemektedir. BT yöneticisi bundan sonra, **Cihaz Türü Kısıtlaması**'nın altından kaydı en düşük ve en yüksek işletim sistemi değerleri arasında bir platform yapılandırmasını sınırlamak üzere ayarlayabilir. Android işletim sistemi sürümleri Büyük.Küçük.Derleme.Düzeltme olarak belirtilmelidir. Burada Küçük, Derleme ve Düzeltme isteğe bağlıdır. iOS sürümleri ise Büyük.Küçük.Derleme olarak belirtilmelidir; burada Küçük ve Derleme isteğe bağlıdır. [Cihaz kaydı kısıtlamaları](../enrollment/enrollment-restrictions-set.md) hakkında daha fazla bilgi edinin.

>[!NOTE]
>Kayıt işlemini Apple kayıt programları veya Apple Configurator ile kısıtlamayın.

### <a name="restrict-android-ios-and-macos-device-personally-owned-device-enrollment-----1333272--1333275-1245709----"></a>Kişilere ait Android, iOS ve macOS cihaz kaydını kısıtlama <!--- 1333272,  1333275, 1245709 --->
Intune, şirket cihazı IMEI numaralarını güvenilir listeye ekleyerek kişisel cihaz kaydını kısıtlayabilir. Intune artık bu işlevi cihaz seri numarası kullanan iOS, Android ve macOS için genişletmiştir. Intune’a seri numaralarını yükleyerek cihazların şirkete ait olduğunu önceden bildirmiş olursunuz. Kayıt kısıtlamalarını kullanarak kişişel (KCG) cihazları engelleyebilir ve yalnızca şirkete ait cihazların kaydına izin verebilirsiniz. [Cihaz kaydı kısıtlamaları](../enrollment/enrollment-restrictions-set.md) hakkında daha fazla bilgi edinin.

Seri numaralarını içeri aktarmak için **Cihaz kaydı** > **Kurumsal cihaz tanımlayıcıları**’na gidin, **Ekle**’ye tıklayın ve bir .CSV dosyası yükleyin (üst bilgi, seri numarası ve IMEI numaraları gibi ayrıntılar için iki sütun). Kişisel cihazları kısıtlamak için **Cihaz kaydı** > **Kayıt kısıtlamaları**’na gidin. **Cihaz Türü Kısıtlamaları** altında **Varsayılan**’ı ve daha sonra **Platform Yapılandırmaları**’nı seçin. iOS, Android ve macOS kişisel cihazlar için **İzin Ver** veya **Engelle** seçeneklerinden birini belirtebilirsiniz.


### <a name="new-device-action-to-force-devices-to-sync-with-intune---711369---"></a>Cihazları Intune ile eşitlemeye zorlayan yeni bir cihaz eylemi<!-- 711369 -->
Bu sürümde, seçili cihazı Intune’da hemen bildirim yapmaya zorlayan yeni bir cihaz eylemi ekledik. Bir cihaz iade edildiğinde, kendisine atanan beklemedeki eylem veya ilkeleri hemen alır.  Bu eylem, atadığınız ilkeleri bir sonraki zamanlanmış iadeyi beklemenize gerek kalmadan hızla doğrulamanız ve ilkelerin sorunlarını gidermenize yardımcı olur.
Ayrıntılar için bkz. [Cihaz eşitleme](../remote-actions/device-sync.md)

### <a name="force-supervised-ios-devices-to-automatically-install-the-latest-available-software-update---777100---"></a>Denetimli iOS cihazları, son yazılım güncelleştirmesini yüklemeye zorlama<!-- 777100 -->
Denetimli iOS cihazları mevcut son yazılım güncelleştirmesini otomatik olarak yüklemeye zorlayabileceğiniz Yazılım güncelleştirmeleri çalışma alanında yeni bir ilke kullanılabilir durumdadır. Ayrıntılar için bkz. [iOS güncelleştirme ilkelerini yapılandırma](/intune/software-updates-ios)

### <a name="check-point-sandblast-mobile---new-mobile-threat-defense-partner----954651-1172027---"></a>Check Point SandBlast Mobile - Yeni Mobil Tehdit Savunması iş ortağı <!-- 954651, 1172027 -->
Microsoft Intune ile tümleşen bir mobil tehdit savunması çözümü olan denetim noktası SandBlast Mobile tarafından gerçekleştirilen risk değerlendirmesine dayalı koşullu erişimi kullanarak mobil cihaz erişimini kontrol edebilirsiniz.

#### <a name="how-integration-with-intune-works"></a>Intune ile tümleştirme nasıl çalışır?
Risk, Checkpoint SandBlast Mobile çalıştıran cihazlardan toplanan telemetriye göre değerlendirilir. Intune cihaz uyumluluk ilkeleri aracılığıyla etkinleştirilen denetim noktası SandBlast Mobile risk değerlendirmesini temel alan EMS koşullu erişim ilkelerini yapılandırabilirsiniz. Algılanan tehditlere dayalı olarak uyumlu olmayan cihazların şirket kaynaklarına erişmesine izin verebilir ya da erişimi engelleyebilirsiniz.


### <a name="deploy-an-app-as-available-in-the-microsoft-store-for-business---748101---"></a>Bir uygulamayı İş için Microsoft Mağazası’nda kullanılabilir olarak dağıtma<!-- 748101 -->
Bu sürümle birlikte, yöneticiler artık İş için Microsoft Mağazası’nı kullanılabilir olarak atayabilir. Kullanılabilir olarak ayarlandığında, son kullanıcılar Microsoft Mağazası’na yönlendirilmeden uygulamayı Şirket Portalı uygulamasından veya web sitesinden yükleyebilir.

### <a name="ui-updates-to-the-company-portal-website--1313244-part-1--"></a>Şirket Portalı web sitesine kullanıcı arabirimi güncelleştirmeleri<!--1313244 part 1-->
Son kullanıcı deneyimini geliştirmek için [Şirket Portalı Web sitesinin](https://portal.manage.microsoft.com) kullanıcı arabiriminde bazı güncelleştirmeler yaptık.

- __Uygulama kutucuklarında yapılan geliştirmeler__: Uygulama simgeleri artık simgedeki baskın renge göre (algılanabilirse) otomatik olarak oluşturulmuş bir arka plan ile görüntülenecektir. Uygun olduğunda, bu arka plan daha önce uygulama kutucuklarında görünen gri kenarlıkların yerine geçer.

    Şirket Portalı web sitesi, gelecek bir sürümde mümkün olduğunda büyük simgeler gösterecektir. BT yöneticilerinin en az 120x120 piksel boyutuna sahip yüksek çözünürlüklü simgeler kullanarak uygulama yayımlamalarını öneririz. 

- __Gezinti değişiklikleri__ Gezinti çubuğu öğeleri, sol üstteki hamburger menüsüne taşındı. Kategoriler sayfası kaldırıldı. Kullanıcılar artık gözatma sırasında içeriği kategorilere göre filtreleyebilir.

- __Öne Çıkan Uygulama Güncelleştirmeleri__: Kullanıcıların öne çıkarmak istediğiniz uygulamalara göz atabileceği siteye ayrı bir sayfa ekledik ve giriş sayfasındaki Öne Çıkan sekmesinde bazı kullanıcı arabirimi değişiklikleri yaptık.

### <a name="ibooks-support-for-the-company-portal-website--1231841--"></a>Şirket Portalı web sitesine yönelik iBooks desteği<!--1231841-->
Şirket Portalı web sitesine, kullanıcıların iBooks’a göz atıp kitap indirmesine olanak tanıyan özel bir sayfa ekledik. 


### <a name="additional-help-desk-troubleshooting-details-----applies-to-1263399-1326964-1341642----"></a>Ek yardım masası sorun giderme ayrıntıları<!---  Applies to 1263399, 1326964, 1341642 --->
Intune, sorun giderme ekranını güncelleştirdi ve yöneticilerle yardım masası çalışanları için sağladığı bilgileri artırdı. Artık, kullanıcı tabanlı grup üyeliği için tüm atamaları özetleyen bir **Atamalar** tablosu görebilirsiniz. Liste şunları içerir:
- Mobil uygulamalar
- Uyumluluk ilkeleri
- Yapılandırma profilleri

Ayrıca **Cihazlar** tablosu artık **Azure AD katılım türü** ve**Azure AD uyumlu** sütunlarını içeriyor. Daha fazla bilgi için bkz. [kullanıcıların sorunlarını gidermeye yardım etme](../help-desk-operators.md).



### <a name="intune-data-warehouse-public-preview"></a>Intune Veri Ambarı (Genel Önizleme)
Intune Veri Ambarı, kiracınızın geçmiş bilgilerini görüntülemenizi sağlamak için her gün veri örnekleri sağlar. Verilere bir Power BI dosyası (PBIX), birçok analiz aracıyla uyumlu bir OData bağlantısı kullanarak veya REST API’si ile etkileşimde bulunarak erişebilirsiniz. Daha fazla bilgi için bkz. [Intune Veri Ambarı’nı Kullanma](../developer/reports-nav-create-intune-reports.md).


### <a name="light-and-dark-modes-available-for-the-company-portal-app-for-windows-10---676547---"></a>Windows 10 için Şirket Portalı uygulamasında açık ve koyu modlar kullanılabilir<!---676547--->
Windows 10 için Şirket Portalı uygulamasında son kullanıcılar, renk modunu özelleştirebilecek. Kullanıcılar bu değişikliği Şirket Portalı uygulamasının Ayarlar kısmından yapabilir. Değişiklik, kullanıcı uygulamayı yeniden başlattığında görünecektir. Windows 10 sürüm 1607 ve üzeri için uygulama modu varsayılan olarak sistem ayarında olacaktır. Windows 10 sürüm 1511 ve öncesi için uygulama modu varsayılan olarak açık modda olacaktır.

### <a name="enable-end-users-to-tag-their-device-group-in-the-company-portal-app-for-windows-10---807046--"></a>Windows 10 için Şirket Portalı uygulamasında son kullanıcıların cihaz gruplarını etiketlemelerine izin verme<!---807046-->
Son kullanıcılar, artık doğrudan Windows 10 için Şirket Portalı uygulamasında cihazlarının hangi gruba ait olduğunu etiketleyerek cihaz gruplarını belirleyebilir.

<!-- ########################## -->
## <a name="june-2017"></a>Haziran 2017

### <a name="new-role-based-administration-access-for-intune-admins-----1099990---"></a>Intune yöneticileri için yeni rol tabanlı yönetim erişimi  <!-- 1099990 -->  
Azure AD koşullu erişim ilkelerini görüntülemek, oluşturmak, değiştirmek ve silmek için yeni bir koşullu erişim Yöneticisi rolü ekleniyor. Daha önce yalnızca genel yöneticiler ve güvenlik yöneticileri bu izne sahipti. Bu rol izniyle, koşullu erişim ilkelerine erişimi olacak şekilde Intune yöneticileri verilebilir.


### <a name="tag-corporate-owned-devices-with-serial-number---1215070---"></a>Şirkete ait cihazları seri numarasıyla etiketleme<!-- 1215070 -->  
Intune artık iOS, macOS ve Android seri numaralarını Kurumsal Cihaz Tanımlayıcıları olarak karşıya yüklemeyi destekliyor. Seri numaralar kayıt sırasında doğrulanmadığı için bu numaraları henüz kişisel cihazların kaydedilmesini engellemek için kullanamazsınız. Kişisel cihazları seri numarasına göre engelleme, yakın bir gelecekte çıkacak.


### <a name="new-remote-actions-for-ios-devices---854689---"></a>iOS cihazları için yeni uzak eylemler<!-- 854689 -->
Bu sürümde, Apple Classroom uygulamasını yöneten paylaşılan iPad cihazlar için iki yeni uzak cihaz eylemi ekledik:

- [Geçerli kullanıcının oturumunu kapat](../remote-actions/device-logout-user.md) - Seçtiğiniz bir iOS cihazının geçerli kullanıcısının oturumunu kapatır.
- [Kullanıcı kaldır](../remote-actions/device-remove-user.md) - Bir iOS cihazdaki yerel önbellekten seçtiğiniz bir kullanıcıyı siler.


### <a name="support-for-shared-ipads-with-the-ios-classroom-app---1044681---"></a>iOS Classroom uygulaması ile paylaşılan iPad'ler için destek<!-- 1044681 -->
Bu sürümde, iOS Classroom uygulamasının kapsamını, paylaşılan iPad’lerde yönetilen Apple kimliklerini kullanarak oturum açan öğrencileri de içerecek şekilde genişlettik.


### <a name="changes-to-intune-built-in-apps---1332306---"></a>Intune yerleşik uygulamalarındaki yenilikler<!-- 1332306 -->
Eskiden Intune’da hızlıca atayabileceğiniz birkaç yerleşik uygulama vardı. Geri bildirimlerinize dayanarak bu listeyi kaldırdık, artık yerleşik uygulamaları görmeyeceksiniz.
Ancak herhangi bir yerleşik uygulamayı önceden atadıysanız bu uygulamalar, uygulama listesinde görünmeye devam edecektir. Bu cihazları gerektiği gibi atamaya devam edebilirsiniz.
Sonraki bir sürümde, Azure portalında yerleşik uygulama seçme ve atama için daha kolay bir yöntem eklemeyi planlıyoruz.

### <a name="easier-installation-of-office-365-apps----1121362----"></a>Office 365 uygulamalarında yükleme kolaylığı<!--- 1121362 --->
Yeni **Office 365 ProPlus** uygulama türü, Office 365 ProPlus 2016 uygulamalarını Windows 10’un en son sürümünü çalıştıran yönettiğiniz cihazlara atamayı kolaylaştırır. Bunun yanı sıra, Microsoft Project ve Microsoft Visio lisanslarınız varsa bu uygulamaları yükleyebilirsiniz. İstediğiniz uygulamalar birlikte paketlenir ve Intune konsolundaki uygulamalar listesinde tek uygulama olarak gösterilir.
Daha fazla bilgi için bkz. [Windows 10 için Office 365 uygulamaları ekleme](../apps/apps-add-office365.md).


### <a name="support-for-offline-apps-from-the-microsoft-store-for-business----777044----"></a>İş İçin Microsoft Mağazası uygulamaları için çevrimdışı desteği<!--- 777044 --->
İş için Microsoft Mağazası’ndan satın aldığınız çevrimdışı uygulamalar, artık Azure portalına eşitlenecektir. Daha sonra bu uygulamaları cihaz gruplarına veya kullanıcı gruplarına dağıtabilirsiniz. Çevrimdışı uygulamalar, mağaza tarafından değil Intune tarafından yüklenir.

### <a name="microsoft-teams-is-now-part-of-the-app-based-ca-list-of-approved-apps-----1257019---"></a>Microsoft Teams artık onaylı uygulamaların Uygulama temelli CA listesinin bir parçasıdır  <!-- 1257019 -->
İOS ve Android için Microsoft ekipleri uygulaması artık Exchange ve SharePoint Online için uygulama tabanlı koşullu erişim ilkelerine yönelik onaylanan uygulamaların bir parçasıdır. Uygulama, şu anda uygulama tabanlı koşullu erişim kullanan tüm kiracılara Azure portal Intune Uygulama Koruması dikey penceresinde yapılandırılabilir.

### <a name="managed-browser-and-app-proxy-integration---1287310---"></a>Managed Browser ve uygulama ara sunucu tümleştirmesi<!-- 1287310 -->
Intune Managed Browser artık Azure AD Uygulama Proxy’si hizmeti ile tümleştirilebilir ve bu sayede kullanıcılar uzaktan çalışsalar bile dahili web sitelerine erişebilirler. Tarayıcıyı kullanırken her zaman yaptığınız gibi site URL’sini girmeniz yeterlidir, Managed Browser bu isteği uygulama proxy’si web ağ geçidine yönlendirecektir. Daha fazla bilgi için bkz. [Managed Browser ilkeleri kullanarak İnternet erişimini yönetme](../apps/app-configuration-managed-browser.md).

### <a name="new-app-configuration-settings-for-the-intune-managed-browser---682951---"></a>Intune'la Managed Browser için yeni uygulama ayarları<!-- 682951 -->
Bu sürümde, iOS ve Android için Intune Managed Browser uygulamasına ilave yapılandırmalar ekledik. Artık tarayıcının varsayılan giriş sayfasını ve yer işaretlerini yapılandırmak için bir uygulama yapılandırma ilkesi kullanabilirsiniz.
Daha fazla bilgi için bkz. [Managed Browser ilkeleri kullanarak İnternet erişimini yönetme](../apps/app-configuration-managed-browser.md)

### <a name="bitlocker-settings-for-windows-10----951707---"></a>Windows 10 için BitLocker ayarları <!-- 951707 -->
Artık yeni bir Intune cihaz profili kullanarak Windows 10 cihazlar için BitLocker ayarlarını yapılandırabilirsiniz. Örneğin cihazların şifreli olmasını gerekli kılabilir ve BitLocker açık olduğunda uygulanacak başka ayarlar da yapılandırabilirsiniz.
Daha fazla bilgi için bkz. [Windows 10 ve üzeri sürümler için Endpoint Protection ayarları](../protect/endpoint-protection-windows-10.md).

### <a name="new-settings-for-windows-10-device-restriction-profile----978527--978550-978569-1050031-1058611-----"></a>Windows 10 cihaz kısıtlama profili için yeni ayarlar<!--- 978527,  978550, 978569, 1050031, 1058611,  --->
Bu sürümde, Windows 10 cihaz kısıtlama profili için aşağıdaki kategorilere yeni ayarlar ekledik:

- Windows Defender
- Hücresel ve bağlantı
- Kilit ekranı deneyimi
- Gizlilik
- Ara
- Windows Spot
- Microsoft Edge tarayıcısı

Windows 10 ayarları hakkında daha fazla bilgi için bkz. [Windows 10 ve üzeri sürümler için cihaz kısıtlama ayarları](../configuration/device-restrictions-windows-10.md).


### <a name="company-portal-app-for-android-now-has-a-new-end-user-experience-for-app-protection-policies--1305217--"></a>Android için Şirket Portalı uygulamasının artık Uygulama Koruma İlkeleri için yeni bir son kullanıcı deneyimi var<!--1305217-->
Müşteri geri bildirimi doğrultusunda, Android için Şirket Portalı uygulamasını bir **Şirket İçeriğine Eriş** düğmesi gösterecek şekilde değiştirdik. Amaç, son kullanıcıların yalnızca, Intune mobil uygulama yönetiminin bir özelliği olan Uygulama Koruma İlkelerini destekleyen uygulamalara erişmek için gereksiz yere kayıt işlemi yapmalarını engellemektir. Bu değişiklikleri, [uygulama kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md) sayfasında görebilirsiniz.

### <a name="new-menu-action-to-easily-remove-company-portal--1164569--"></a>Şirket Portalını kolayca kaldırmak için yeni menü eylemi<!--1164569-->
Kullanıcı geri bildirimi doğrultusunda, Android için Şirket Portalı uygulaması, Şirket Portalını cihazınızdan kaldırmak için yeni bir menü eylemi ekledi. Bu eylem cihazı Intune yönetiminden kaldırır, böylece uygulama cihazdan kullanıcı tarafından kaldırılabilir. Bu değişiklikleri [Uygulamanın kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md) sayfasında ve [Android son kullanıcı belgelerinde](/intune-user-help/unenroll-your-device-from-intune-android) görebilirsiniz.

### <a name="improvements-to-app-syncing-with-windows-10-creators-update--676505--"></a>Windows 10 Creators Güncelleştirmesi ile uygulama eşitleme geliştirmeleri<!--676505-->
Windows 10 için Şirket Portalı uygulaması, Windows 10 Creators Update (sürüm 1703) içeren cihazlarda uygulama yükleme istekleri için eşitlemeyi artık otomatik olarak başlatacak. Bu, “Eşitleme Bekleniyor” durumu sırasında bekletilen uygulama yüklemeleri sorununu azaltacak. Buna ek olarak, kullanıcılar uygulamanın içinden el ile eşitleme başlatabilecek. Bu değişiklikleri, [uygulama kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md) sayfasında görebilirsiniz.

### <a name="new-guided-experience-for-windows-10-company-portal---1058938---"></a>Windows 10 Şirket Portalı için kullanıcının yönlendirildiği yeni deneyim<!---1058938--->
Windows 10 için Şirket Portalı uygulaması, tanımlanmamış veya kaydedilmemiş cihazlar için kullanıcının adım adım yönlendirildiği bir Intune deneyimi içerecek. Yeni deneyim, kullanıcıya Azure Active Directory kaydı sürecinde (Koşullu Erişim özelliklerinde gereklidir) ve MDM kaydı sürecinde (cihaz yönetim özellikleri için gereklidir) kılavuzluk eden adım adım yönergeler sağlıyor. Kılavuzluk destekli deneyime Şirket Portalı giriş sayfasından erişilebilecek. Kullanıcılar, cihaz kaydettirme ve kaydolma işlemlerini tamamlamasa da uygulamayı kullanmaya devam edebilecek, ancak sınırlı bir işlevsellikleri olacak.

Bu güncelleştirme yalnızca Windows 10 Yıldönümü Güncelleştirmesi (derleme 1607) veya üzerini çalıştıran cihazlarda görünür. Bu değişiklikleri, [uygulama kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md) sayfasında görebilirsiniz.


### <a name="microsoft-intune-and-conditional-access-admin-consoles-are-generally-available"></a>Microsoft Intune ve Koşullu Erişim yönetici konsolları genel olarak kullanılabilir
Azure portalında Intune yönetici konsolu ve Koşullu Erişim yönetici konsolunun genel olarak kullanılabilir olduğunu duyuruyoruz. Azure portalında Intune aracılığıyla, artık tüm Intune MAM ve MDM özelliklerini birleştirilmiş tek bir yönetim deneyiminde yönetebilir ve Azure AD gruplandırma ve hedefleme özelliğinden yararlanabilirsiniz. Azure 'da koşullu erişim, Azure AD ve Intune üzerinde zengin özellikleri tek bir birleştirilmiş konsolda birlikte sunar. Yönetim deneyimi açısından ise Azure platformuna geçmek modern tarayıcıları kullanmanıza olanak tanır.

Intune artık portal.azure.com adresindeki Azure portalında **önizleme** etiketi olmadan da görünür durumdadır.

İleti merkezinde gruplarınızın geçişini yapmamız için eylemde bulunmanızı isteyen ileti serilerinden birini almadıysanız şu anda mevcut müşterilerin yapması gereken bir eylem yoktur. Tarafımızdaki hatalardan dolayı geçişinizin daha uzun sürdüğünü belirten bir ileti merkezi bildirimi de almış olabilirsiniz. Etkilenen tüm müşterilerin geçişini tamamlamak üzere titizlikle çalışmaya devam ediyoruz.

### <a name="improvements-to-the-app-tiles-in-the-company-portal-app-for-ios"></a>iOS için Şirket Portalı uygulamasındaki uygulama kutucukları geliştirmeleri
Şirket Portalı için ayarladığınız marka rengini yansıtmak için giriş sayfasındaki uygulama kutucuklarının tasarımı güncelleştirildi. Daha fazla bilgi için bkz. [Uygulamanın kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md).

### <a name="account-picker-now-available-for-the-company-portal-app-for-ios"></a>iOS Şirket Portalı uygulaması için artık hesap seçici kullanılabilir
iOS cihazı kullanıcıları diğer Microsoft uygulamalarında oturum açmak için iş veya okul hesaplarını kullanıyorsa Şirket Portalı uygulamasında oturum açtıklarında yeni hesap seçiciyi görebilirler. Daha fazla bilgi için bkz. [Uygulamanın kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md).

<!-- ########################## -->
## <a name="may-2017"></a>Mayıs 2017

### <a name="change-your-mdm-authority-without-unenrolling-managed-devices--1103950--"></a>Yönetilen cihazların kaydını kaldırmadan MDM yetkilinizi değiştirme<!--1103950-->
Artık Microsoft Desteği’ne başvurmak ve mevcut yönetilen cihazlarınızın kaydını kaldırıp yeniden kaydetmek zorunda kalmadan MDM yetkilinizi değiştirebilirsiniz. Configuration Manager konsolunda, [MDM yetkilinizi değiştirerek](/sccm/mdm/deploy-use/change-mdm-authority) Configuration Manager’a Ayarla (karma) ile Microsoft Intune (tek başına) seçenekleri arasında geçiş yapabilirsiniz.


### <a name="improved-notification-for-samsung-knox-startup-pins--1087143--"></a>Samsung Knox başlangıç PIN’leri için geliştirilmiş bildirim<!--1087143-->
Şifrelemeyle uyumlu olması için son kullanıcıların Samsung Knox cihazlarında başlangıç PIN’i ayarlamaları gerektiğinde, son kullanıcılara gösterilen bildirime dokunulduğunda bildirimleri Ayarlar uygulamasında doğru yere yerleştirir.  Daha önce, bildirim son kullanıcıyı parola değiştirme ekranına getiriyordu.

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="apple-school-manager-asm-support-with-shared-ipad---748864-770395--"></a>Paylaşılan iPad ile Apple School Manager (ASM) desteği<!-- 748864, 770395-->

Intune, iOS cihazlarında hazır kayıt sağlamak için Apple Aygıt Kayıt Programı yerine artık Apple School Manager’ı (ASM) destekler. Paylaşılan iPad’lerde Classroom uygulamasını kullanmak ve Microsoft School Data Sync (SDS) yoluyla ASM’den Azure Active Directory’ye veri eşitlemeyi etkinleştirmek için ASM’nin kullanıma alınması gereklidir. Daha fazla bilgi için bkz. [Apple School Manager ile iOS cihaz kaydını etkinleştirme](../enrollment/apple-school-manager-set-up-ios.md).

> [!NOTE]
> Paylaşılan iPad’leri Classroom uygulaması ile birlikte çalışmak üzere yapılandırmak Azure’da henüz kullanılamayan iOS Eğitim yapılandırmaları gerektirir.  Bu işlev yakında eklenecektir.

### <a name="device-management"></a>Cihaz yönetimi

#### <a name="provide-remote-assistance-to-android-devices-using-teamviewer---675418---"></a>TeamViewer kullanarak Android cihazları için uzaktan yardım sağlama<!-- 675418 -->

Intune, Android cihaz çalıştıran kullanıcılarınıza uzaktan yardım etmenizi sağlamak için artık ayrı satın alınan [TeamViewer](https://www.teamviewer.com) yazılımını kullanabilir. Daha fazla bilgi için bkz. [Intune ile yönetilen Android cihazlar için uzaktan yardım sağlama](../remote-actions/teamviewer-support.md).

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="new-app-protection-policies-conditions-for-mam---679864---"></a>MAM için yeni uygulama koruma ilkesi koşulları<!-- 679864 -->

Artık kayıt kullanıcıları olmadan MAM için aşağıdaki ilkeleri zorunlu tutan bir gereksinim ayarlayabilirsiniz:

- En düşük uygulama sürümü
- En düşük işletim sistemi sürümü
- Hedeflenen uygulamanın en düşük Intune APP SDK’sı sürümü (yalnızca iOS)

Bu özellik hem Android hem de iOS’ta kullanılabilir. Intune; işletim sistemi platformu sürümleri, uygulama sürümleri ve Intune APP SDK’sı için en düşük sürüm zorlamasını destekler. iOS’ta, SDK’nın tümleştirildiği uygulamalar da SDK düzeyinde en düşük sürüm zorlaması ayarlayabilir. Yukarıda açıklanan üç farklı düzeyde uygulama koruma ilkesi aracılığıyla belirlenen en düşük gereksinimler karşılanmazsa kullanıcı hedeflenen uygulamaya erişemez. Bu noktada, kullanıcı hesabını kaldırabilir (çok kimlikli uygulamalarda), uygulamayı kapatabilir veya işletim sistemi veya uygulama sürümünü güncelleştirebilir.

İşletim sistemi veya uygulama yükseltmesi öneren ve engelleyici olmayan bir bildirim sağlamak için ek ayarlar da yapılandırabilirsiniz. Bu bildirim kapatılabilir ve uygulama normal şekilde kullanılabilir.

Daha fazla bilgi için bkz. [iOS uygulama koruma ilkesi ayarları](../apps/app-protection-policy-settings-ios.md) ve [Android uygulama koruma ilkesi ayarları](../apps/app-protection-policy-settings-android.md).

#### <a name="configure-app-configurations-for-android-for-work---621621---"></a>Android for Work için uygulama yapılandırmaları ayarlayın<!-- 621621 -->
Mağazadaki bazı Android uygulamaları, bir BT yöneticisinin bir uygulamanın iş profilinde nasıl çalışacağını denetlemesine izin veren yönetilen yapılandırma seçeneklerini destekler. Intune ile artık bir uygulama tarafından desteklenen yapılandırmaları görüntüleyebilir ve bunları bir yapılandırma tasarımcısı veya JSON düzenleyicisi ile Azure portalından yapılandırabilirsiniz. Daha fazla bilgi için bkz. [Android for Work için uygulama yapılandırmaları kullanma](../apps/app-configuration-policies-use-android.md).

#### <a name="new-app-configuration-capability-for-mam-without-enrollment---677969---"></a>Kayıt olmadan MAM için yeni uygulama yapılandırma özelliği<!-- 677969 -->
Artık kayıt kanalı olmadan MAM ile uygulama yapılandırma ilkeleri oluşturabilirsiniz. Bu özellik, mobil cihaz yönetimi (MDM) uygulama yapılandırmasında kullanılabilir uygulama yapılandırma ilkelerine eşdeğerdir. Kayıt olmadan MAM kullanılan uygulama yapılandırması örneği için bkz. [Microsoft Intune'la Managed Browser ilkelerini kullanarak İnternet erişimini yönetme](../apps/app-configuration-managed-browser.md).

#### <a name="configure-allowed-and-blocked-url-lists-for-the-managed-browser---682960---"></a>Managed Browser için izin verilen ve engellenen URL listelerini yapılandırma<!-- 682960 -->
Artık Azure portalındaki uygulama yapılandırma ayarlarını kullanarak Intune Managed Browser için izin verilen ve engellenen etki alanları ve URL’ler listesi yapılandırabilirsiniz. Bu ayarlar yönetilen bir cihazda mı yoksa yönetilmeyen bir cihazda mı kullanıldığına bakılmaksızın yapılandırılabilir. Daha fazla bilgi için bkz. [Microsoft Intune'la Managed Browser ilkelerini kullanarak İnternet erişimini yönetme](../apps/app-configuration-managed-browser.md).

#### <a name="app-protection-policy-helpdesk-view---1069473---"></a>Uygulama koruma ilkesi yardım masası görünümü<!-- 1069473 -->
BT Yardım Masası kullanıcıları, artık kullanıcı lisans durumu ve Sorun Giderme dikey penceresinde kullanıcılara atanan uygulama koruma ilkesi uygulamalarının durumunu denetleyebilir. Ayrıntılar için bkz. [Sorun giderme](./help-desk-operators.md).

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="control-website-visits-on-ios-devices---723832---"></a>iOS cihazlarda web sitesi ziyaretlerini denetleme<!-- 723832 -->
iOS cihazı kullanıcılarının ziyaret edebileceği web sitelerini aşağıdaki iki yöntemden birini kullanarak denetleyebilirsiniz:

- Apple'ın yerleşik web içeriği filtresini kullanarak izin verilen ve engellenen URL'leri ekleyin.

- Safari tarayıcısı tarafından yalnızca belirli web sitelerine erişilmesine izin verin. Belirttiğiniz siteler için Safari'de yer işaretleri oluşturulur.

Daha fazla bilgi için bkz. [iOS cihazları için web içeriği filtresi ayarları](../configuration/ios-device-features-settings.md#web-content-filter).

#### <a name="preconfigure-device-permissions-for-android-for-work-apps---621614---"></a>Android for Work uygulamaları için cihaz izinlerini önceden yapılandırma<!-- 621614 -->
Android for Work cihazı iş profillerine dağıtılan uygulamalarda, artık tek tek uygulamalar için izin durumunu yapılandırabilirsiniz.  Varsayılan olarak, konuma veya cihaz kamerasına erişim gibi cihaz izinlerine ihtiyacı olan Android uygulamaları kullanıcıdan izinleri kabul etmesini veya reddetmesini ister.  Örneğin, uygulama cihazın mikrofonunu kullanıyorsa, son kullanıcıdan mikrofonu kullanmak için uygulamaya izin vermesi istenir. Bu özellik, son kullanıcılar için izinleri tanımlamanıza olanak tanır.  İzinleri a) kullanıcıya bildirimde bulunmadan otomatik olarak reddedilecek şekilde b) kullanıcıya bildirimde bulunmadan otomatik olarak onaylanacak şekilde veya c) kullanıcıya kabul etmesi veya reddetmesi için sorulacak şekilde yapılandırabilirsiniz. Daha fazla bilgi için bkz. [Microsoft Intune’da Android for Work cihaz kısıtlama ayarları](../configuration/device-restrictions-android-for-work.md).

#### <a name="define-app-specific-pin-for-android-for-work-devices---728976-1102534---"></a>Android for Work cihazlarında uygulamaya özgü PIN’i tanımlama<!-- 728976, 1102534 -->
Android for Work cihazı olarak yönetilen ve bir iş profili bulunan Android 7.0 ve üzeri cihazlarda, yöneticinin yalnızca iş profilindeki uygulamalar için geçerli olacak bir geçiş kodu ilkesi tanımlamasına izin verilir.  Şu seçenekler mevcuttur:

- Yalnızca cihaz genelinde bir geçiş kodu ilkesi tanımlama - Bu, kullanıcının tüm cihaz kilidini açmak için kullanması gereken geçiş kodudur.
- Yalnızca bir iş profili geçiş kodu ilkesi tanımlama - İş profilindeki bir uygulama her açıldığında kullanıcılardan geçiş kodunu girmesi istenir.
- Hem cihaz hem iş profili ilkesi tanımlama - BT yöneticisinin farklı güç düzeylerinde hem cihaz geçiş kodu ilkesi hem de iş profili geçiş kodu ilkesi tanımlama seçeneği vardır (örneğin, cihazın kilidini açmak için dört basamaklı bir PIN, ancak herhangi bir iş uygulamasını açmak için altı basamaklı bir PIN).

Daha fazla bilgi için bkz. [Microsoft Intune’da Android for Work cihaz kısıtlama ayarları](../configuration/device-restrictions-android-for-work.md).

> [!NOTE]
> Bu özellik yalnızca Android 7.0 ve üzeri sürümlerde kullanılabilir.  Varsayılan olarak, son kullanıcı ayrı tanımlanmış iki PIN kullanabilir veya tanımlanmış olan iki PIN’den en güçlü olanı seçebilir.

#### <a name="new-settings-for-windows-10-devices---978585---"></a>Windows 10 cihazları için yeni ayarlar<!-- 978585 -->
Kablosuz ekranlar, cihaz bulma, görev geçişi ve SIM kartı hata iletileri gibi özellikleri denetleyen yeni [Windows cihaz kısıtlama ayarları](../configuration/device-restrictions-windows-10.md) ekledik.

#### <a name="updates-to-certificate-configuration---918991-and-823198---"></a>Sertifika yapılandırması güncelleştirmeleri<!-- 918991 and 823198 -->
Bir SCEP sertifika profili oluştururken, <strong>Konu adı biçimi</strong> için <strong>Özel</strong> seçeneği iOS, Android ve Windows cihazları için kullanılabilir. Bu güncelleştirmeden önce, <strong>Özel</strong> alanı yalnızca iOS cihazları için kullanılabiliyordu. Daha fazla bilgi için bkz. [SCEP sertifika profili oluşturma](../protect/certificates-profile-scep.md).

Bir PKCS sertifika profili oluştururken, **Konu diğer adı** için **Özel Azure AD özniteliği** kullanılabilir. **Departman** seçeneği, **Özel Azure AD özniteliği** seçtiğinizde kullanılabilir. Daha fazla bilgi için bkz. [PKCS sertifika profili oluşturma](../protect/certficates-pfx-configure.md#create-a-pkcs-certificate-profile).

#### <a name="configure-multiple-apps-that-can-run-when-an-android-device-is-in-kiosk-mode---662059---"></a>Bir Android cihazı bilgi noktası modunda olduğunda çalışabilen birden çok uygulama yapılandırma<!-- 662059 -->
Bir Android cihazı bilgi noktası modundayken, önceden çalışmasına izin verilen yalnızca bir uygulama yapılandırmanıza izin veriliyordu. Artık uygulama kimliği, mağaza kimliği veya zaten yönettiğiniz Android uygulamasını seçerek birden fazla uygulamayı yapılandırabilirsiniz. Daha fazla bilgi için bkz. [Bilgi noktası modu ayarları](../configuration/device-restrictions-android.md#kiosk).

<!-- ########################## -->
## <a name="april-2017"></a>Nisan 2017

### <a name="support-for-managing-the-apple-classroom-app"></a>Apple Classroom uygulamasını yönetme desteği
Artık iOS Classroom uygulamasını iPad cihazlarında yönetebilirsiniz. Doğru sınıf ve öğrenci verileriyle Classroom uygulamasını öğretmenin iPad cihazına kurun ve sınıfa kayıtlı öğrencilerin iPad cihazlarını uygulamayı kullanarak denetlemek için yapılandırın.
Ayrıntılar için bkz. [iOS eğitim ayarlarını yapılandırma](education-settings-configure-ios.md).

### <a name="support-for-managed-configuration-options-for-android-apps---621621---"></a>Android uygulamaları için yönetilen yapılandırma seçenekleri desteği<!-- 621621 -->
Playstore’da yer alan ve yönetilen yapılandırma seçeneklerini destekleyen Android uygulamaları, artık Intune tarafından yapılandırılabilir.  Bu özellik, BT ekibinin bir uygulama tarafından desteklenen yapılandırma değerlerinin listesini görüntülemesini sağlar ve bu değerlerin yapılandırılması için kılavuzlu bir birinci sınıf kullanıcı arabirimi sunar.

### <a name="new-android-policy-for-complex-pins---722069---"></a>Karmaşık PIN'ler için yeni Android ilkesi<!-- 722069 -->
Artık Android 5.0 ve üzeri çalıştıran cihazların Android cihaz profilinde Sayısal karmaşık türünde [parola](../configuration/device-restrictions-android.md#password) gereksinimi belirleyebilirsiniz.  Bu ayarı kullanarak cihaz kullanıcılarının 1111 veya 1234 gibi tekrar eden ya da ardışık rakamlardan oluşan PIN'ler oluşturmasını engelleyebilirsiniz.

### <a name="additional-support-for-android-for-work-devices"></a>Android for Work cihazları için ek destek
- **Parola ve iş profili ayarlarını yönetin**<!-- 612808 -->

  Bu yeni Android for Work cihaz kısıtlama ilkesi artık yönettiğiniz Android for Work cihazlarında parola ve iş profili ayarlarını yönetmenizi sağlar.

- **İş profili ve kişisel profil arasında veri paylaşımına izin ver**<!-- 1045102 -->

Bu Android for Work cihaz kısıtlama profili artık iş ve kişisel profiller arasında veri paylaşımını yapılandırmanıza yardımcı olan yeni seçenekler sunar.

- **İş ve kişisel profiller arasında kopyalama ve yapıştırma işlemlerini kısıtlama**<!-- 1046094 -->

  Android for Work cihazları için yeni bir özel cihaz profili, artık iş ve kişisel uygulamalar arasında kopyala ve yapıştır eylemlerini kısıtlayabilmenizi sağlar.

Daha fazla bilgi için bkz. [Android for Work için cihaz kısıtlamaları](../configuration/device-restrictions-android-for-work.md).

### <a name="assign-lob-apps-to-ios-and-android-devices---1057568---"></a>iOS ve Android cihazlara LOB uygulamaları atama<!-- 1057568 -->
Artık [iOS](../apps/lob-apps-ios.md) (.ipa dosyaları) ve [Android](../apps/lob-apps-android.md) (.apk dosyaları) için iş kolu (LOB) uygulamalarını kullanıcılara veya cihazlara atayabilirsiniz.


### <a name="new-device-policies-for-ios---723774-723815-723826-723830---"></a>iOS için yeni cihaz ilkeleri<!-- 723774, 723815, 723826, 723830 -->
- **Giriş ekranındaki uygulamalar** - Kullanıcıların [iOS cihazlarının giriş ekranında](../configuration/ios-device-features-settings.md#home-screen-layout) göreceği uygulamaları denetler. Bu ilke, Giriş ekranının düzenini değiştirir ancak herhangi bir uygulama dağıtmaz.

- **AirPrint cihazlarıyla bağlantı** - Bir iOS cihazı son kullanıcılarının bağlanabileceği [AirPrint cihazlarını](../configuration/ios-device-features-settings.md#airprint) (ağ yazıcılarını) denetler.

- **AirPlay cihazlarıyla bağlantı** - Bir iOS cihazı son kullanıcılarının bağlanabileceği [AirPlay cihazlarını](../configuration/ios-device-features-settings.md) (Apple TV gibi) denetler.

- **Özel kilit ekranı iletisi** - Kullanıcıların iOS cihazlarının kilit ekranında varsayılan kilit ekranı iletisi yerine göreceği özel bir ileti yapılandırır. Daha fazla bilgi için bkz. [iOS cihazlarında kayıp modunu etkinleştirme](../remote-actions/device-lost-mode.md)

### <a name="restrict-push-notifications-for-ios-apps---723767---"></a>iOS uygulamaları için anında iletme bildirimlerini kısıtlama<!-- 723767 -->
Bir Intune cihaz kısıtlama profilinde iOS cihazlar için artık aşağıdaki [bildirim ayarlarını](../configuration/ios-device-features-settings.md#app-notifications) yapılandırabilirsiniz:

- Belirli bir uygulama için bildirimleri tamamen açma veya kapatma.
- Belirli bir uygulama için bildirim merkezindeki bildirimleri açma veya kapatma.
- Uyarı için **Yok**, **Başlık** veya **Uyarı** türünü belirleme.
- Bu uygulama için rozetlere izin verilip verilmeyeceğini belirleme.
- Bildirim seslerine izin verilip verilmeyeceğini belirleme.

### <a name="configure-ios-apps-to-run-in-single-app-mode-autonomously---737837---"></a>iOS uygulamalarını otonom tek uygulama modunda çalışacak şekilde yapılandırma<!-- 737837 -->
Bir Intune cihaz profili kullanarak belirtilen uygulamaları artık [otonom tek uygulama modunda](../configuration/device-restrictions-ios.md#autonomous-single-app-mode) çalışacak şekilde iOS cihazlarını yapılandırabilirsiniz. Bu mod yapılandırılıp uygulama çalıştırıldığında cihaz yalnızca belirtilen uygulamayı çalıştıracak şekilde kilitlenir. Buna örnek olarak kullanıcıların cihazda test çözmesini sağlayan bir uygulama verilebilir. Uygulamanın eylemleri tamamlandığında veya bu ilkeyi kaldırdığınızda cihaz normal durumuna geri döner.

### <a name="configure-trusted-domains-for-email-and-web-browsing-on-ios-devices---723765---"></a>iOS cihazlarda e-posta ve web üzerinde gezinme için güvenilen etki alanlarını yapılandırma<!-- 723765 -->
Artık bir iOS cihaz kısıtlama profilinden aşağıdaki [etki alanı ayarlarını](../configuration/device-restrictions-ios.md#domains) yapılandırabilirsiniz:

- **İşaretlenmemiş e-posta etki alanları** - Son kullanıcı tarafından gönderilen veya alınan ve burada belirttiğiniz etki alanlarıyla eşleşmeyen e-postalar, güvenilmeyen olarak işaretlenir.

- **Yönetilen web etki alanları** - Burada belirttiğiniz URL'lerden indirilen belgeler, yönetilen belgeler olarak değerlendirilir (yalnızca Safari).  

- **Safari otomatik parola doldurma etki alanları (yalnızca denetimli)** - Kullanıcılar yalnızca burada belirttiğiniz desenlerle eşleşen URL'lerdeki parolaları Safari'ye kaydedebilir. Bu ayarı kullanabilmeniz için cihazın denetimli modda olması ve birden fazla kullanıcı için yapılandırılmış olmaması gerekir. (iOS 9.3 ve üzeri)


### <a name="vpp-apps-available-in-ios-company-portal---748782---"></a>iOS Şirket Portalında VPP uygulamaları kullanılabilir<!-- 748782 -->
iOS toplu satın alınan (VPP) uygulamalarını son kullanıcılara artık **Kullanılabilir** yüklemeler olarak atayabilirsiniz. Son kullanıcıların uygulamayı yükleyebilmek için bir Apple Store hesabına sahip olmaları gerekir.

### <a name="synchronize-ebooks-from-apple-vpp-store---800878---"></a>Apple VPP Store'dan alınan eKitapları eşitleme<!-- 800878 -->
Apple Volume Purchase Program mağazasından satın aldığınız kitapları artık Intune ile [eşitleyebilir](../apps/vpp-apps-ios.md) ve kullanıcılara atayabilirsiniz.

### <a name="multi-user-management-for-samsung-knox-standard-devices---971988---"></a>Samsung Knox Standard cihazları için birden çok kullanıcı yönetimi<!-- 971988 -->
Samsung Knox Standard çalıştıran cihazlarda artık Intune ile [birden çok kullanıcı yönetimi](../enrollment/android-enroll.md) gerçekleştirilebilir. Başka bir deyişle kullanıcılar Azure Active Directory kimlik bilgilerini kullanarak cihazda oturum açıp kapatabilir ve cihaz kullanım durumundan bağımsız olarak merkezden yönetilir.  Son kullanıcılar oturum açtığında uygulamalara erişir ve kendilerine uygulanan ilkeleri alır. Kullanıcılar oturumu kapattığında tüm veriler silinir.

### <a name="additional-windows-device-restriction-settings---818566---"></a>Ek Windows cihaz kısıtlama ayarları<!-- 818566 -->
Ek Microsoft Edge tarayıcısı desteği, cihaz kilit ekranı özelleştirmesi, başlat menüsü özelleştirmeleri, Windows Spot araması duvar kağıdı ve proxy ayarı gibi ek [Windows cihaz kısıtlama ayarları](../configuration/device-restrictions-windows-10.md) için destek ekledik.

### <a name="multi-user-support-for-windows-10-creators-update---822547---"></a>Windows 10 Creators Update için birden çok kullanıcı desteği<!-- 822547 -->
Windows 10 Creators Update çalıştıran ve Azure Active Directory etki alanına katılmış olan cihazlar için [birden çok kullanıcı yönetimi](../enrollment/windows-enroll.md) desteği ekledik. Bu, değişik standart kullanıcılar cihazlarında Azure AD kimlik bilgileriyle oturum açtıklarında, kullanıcı adlarına atanan tüm uygulama ve ilkeleri alacakları anlamına gelir. Kullanıcılar, uygulama yükleme gibi self servis senaryoları için Şirket Portalını şu anda kullanamaz.

### <a name="fresh-start-for-windows-10-pcs---1004830---"></a>Windows 10 PC'ler için Fresh Start<!-- 1004830 -->
Windows 10 PC'ler için yeni bir [Fresh Start cihaz eylemi](../remote-actions/device-fresh-start.md) artık kullanılabilir.  Bu eylemi düzenlediğinizde PC'ye önceden yüklenmiş olan uygulamalar kaldırılır ve PC otomatik olarak en son Windows sürümüne güncelleştirilir. Bu eylem genellikle yeni bir PC ile gelen önceden yüklü OEM uygulamalarının kaldırılmasına yardımcı olması için kullanılabilir. Bu cihaz eylemi düzenlendiğinde kullanıcı verilerinin tutulup tutulmayacağını yapılandırabilirsiniz.

### <a name="additional-windows-10-upgrade-paths---903672---"></a>Ek Windows 10 yükseltme yolları<!-- 903672 -->
Artık, cihazları aşağıdaki ek Windows 10 sürümlerine yükseltmek için bir [sürüm yükseltme ilkesi](../configuration/edition-upgrade-configure-windows-10.md) oluşturabilirsiniz:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N

### <a name="bulk-enroll-windows-10-devices---747607---"></a>Windows 10 cihazlarını toplu kaydetme<!-- 747607 -->
Artık, Windows Yapılandırma Tasarımcısı (WCD) kullanarak Windows 10 Creators Update çalıştıran çok sayıda cihazın Azure Active Directory ve Intune’a katılmasını sağlayabilirsiniz. Azure AD kiracınız için [Toplu MDM kaydını](../enrollment/windows-bulk-enroll.md) etkinleştirmek için Windows Yapılandırma Tasarımcısı kullanarak cihazların Azure AD kiracınıza katılmasını sağlayan bir sağlama paketi oluşturun ve paketi toplu kaydetmek ve yönetmek istediğiniz şirkete ait cihazlara uygulayın. Paket cihazlarınıza uygulandıktan sonra cihazlar Azure AD’ye katılır, Intune’a kaydolur ve Azure AD kullanıcılarınızın oturum açmasına hazır hale gelir.  Azure AD kullanıcıları, bu cihazlarda standart kullanıcılardır ve atanan ilkeleri ve gerekli uygulamaları alırlar. Self servis ve Şirket Portalı senaryoları şu anda desteklenmemektedir.

### <a name="new-mam-settings-for-pin-and-managed-storage-locations---581122-736644---"></a>PIN ve yönetilen depolama konumları için yeni MAM ayarları<!-- 581122, 736644 -->
Mobil uygulama yönetimi (MAM) senaryolarında size yardımcı olacak iki yeni uygulama ayarı artık mevcuttur:

- **Cihaz PIN'i yönetildiğinde uygulama PIN'ini devre dışı bırak** - Kaydedilen cihazda bir cihaz PIN'i olup olmadığını algılar ve varsa uygulama koruma ilkeleri tarafından tetiklenen uygulama PIN'ini atlar. Bu ayar, kayıtlı cihazda MAM özellikli bir uygulamayı açan kullanıcılara gösterilen PIN istemi sayısının azaltılmasını sağlar. Bu özellik hem Android hem de iOS için kullanılabilir.

- **Şirket verilerinin kaydedilebileceği depolama hizmetlerini seçin** - Şirket verilerinin kaydedileceği depolama konumlarını belirtmenizi sağlar. Kullanıcılar seçilen depolama konumu hizmetlerine veri kaydedebilir ve listede olmayan diğer tüm depolama konumu hizmetleri engellenir.

  Desteklenen depolama konumu hizmetlerin listesi:

  - OneDrive
  - İş SharePoint Online
  - Yerel depolama

### <a name="help-desk-troubleshooting-portal---907448---"></a>Yardım masası sorun giderme portalı<!-- 907448 -->
Yeni [sorun giderme portalı](../help-desk-operators.md), yardım masası operatörlerinin ve Intune yöneticilerinin, kullanıcıları ve cihazlarını görüntülemesine ve Intune teknik sorunlarını çözmek için görevler gerçekleştirmelerine izin verir.

<!-- ########################## -->
## <a name="march-2017"></a>Mart 2017

### <a name="support-for-ios-lost-mode--431695--"></a>iOS Kayıp Modu desteği<!--431695-->
Intune, iOS 9.3 ve üzeri cihazlar için **Kayıp Modu** desteği ekledi. Artık bir cihazı kilitleyerek tüm kullanımını önleyebilir, cihaz kilit ekranında bir ileti ve iletişim telefon numarası görüntüleyebilirsiniz.

Bir yönetici Kayıp Modu’nu devre dışı bırakmadıkça son kullanıcılar cihazın kilidini açamaz. Kayıp modu etkin olduğunda, **Cihazı bul** eylemini kullanarak cihazın coğrafi konumunu Intune konsolundaki bir haritada görüntüleyebilirsiniz.

Cihazın DEP aracılığıyla kaydedilen ve denetimli modda olan, şirkete ait bir iOS cihazı olması gerekir.

Daha fazla bilgi için bkz. [Microsoft Intune cihaz yönetimi nedir](../remote-actions/device-management.md)?

### <a name="improvements-to-device-actions-report--677150--"></a>Cihaz Eylemler raporu geliştirmeleri<!--677150-->
Performansı artırmak için Cihaz Eylemler raporunda geliştirmeler yaptık. Bundan sonra ek olarak rapor durumuna göre filtre uygulayabilirsiniz. Örneğin, yalnızca tamamlanan cihaz eylemlerini gösterecek şekilde rapora filtre uygulayabilirsiniz."

### <a name="custom-app-categories--748805--"></a>Özel uygulama kategorileri<!--748805-->
Artık Intune’a eklediğiniz uygulamalar için kategoriler oluşturabilir, düzenleyebilir ve atayabilirsiniz. Şu anda kategoriler yalnızca İngilizce olarak belirtilebilir.
Bkz. [Intune'a uygulama ekleme](../apps/apps-add.md).

### <a name="assign-lob-apps-to-users-with-unenrolled-devices--748823--"></a>Kaydedilmemiş cihaz kullanıcılarına LOB uygulamaları atama<!--748823-->
Cihazları Intune'a kayıtlı olsun ya da olmasın, artık kullanıcılara mağazadan iş kolu uygulamaları atayabilirsiniz. Kullanıcıların cihazları Intune’a kayıtlı değilse yüklemek için Şirket Portalı uygulaması yerine Şirket Portalı web sitesine gitmeleri gerekir.

### <a name="new-compliance-reports--846671--"></a>Yeni uyumluluk raporları<!--846671-->
Artık şirketinizdeki cihazların uyumluluk durumunu size sağlayan ve kullanıcılarınızın karşılaştığı uyumluluk sorunlarını hızlı bir şekilde gidermenize olanak tanıyan uyumluluk raporlarına sahipsiniz. Aşağıdaki konular hakkındaki bilgileri görüntüleyebilirsiniz:

- Cihazların genel uyumluluk durumu
- Ayrı bir ayarın uyumluluk durumu
- Ayrı bir ilkenin uyumluluk durumu

Bu raporları ayrıca bir cihazı incelemek ve cihazı etkileyen belirli ayar ve ilkeleri görüntülemek için de kullanabilirsiniz.

<!--- You can now create an edition upgrade policy to upgrade devices to the following additional Windows 10 editions:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N --->

### <a name="direct-access-to-apple-enrollment-scenarios--951869--"></a>Apple kayıt senaryolarına doğrudan erişim<!--951869-->
Intune, Azure portalındaki Cihaz Kaydetme iş yükünü kullanarak Apple kayıt senaryolarına doğrudan erişimi Ocak 2017 sonrasında oluşturulan Intune hesapları için etkinleştirdi. Daha önce, Apple kayıt önizleme sürümüne yalnızca Azure portalı bağlantıları ile erişilebiliyordu. Bu özelliklerin Azure’da kullanılabilmesi için, Ocak 2017 öncesi oluşturulan Intune hesaplarında tek seferlik bir geçiş yapılması gerekir. Geçiş için zaman çizelgesi henüz açıklanmamıştır, ancak konuya ilişkin ayrıntılar olabildiğince çabuk duyurulacaktır. Mevcut hesabınız önizleme sürümüne erişemiyorsa, yeni deneyimi test etmek için bir deneme hesabı oluşturmanızı kesinlikle öneririz.


<!-- ########################## -->
## <a name="february-2017"></a>Şubat 2017

### <a name="ability-to-restrict-mobile-device-enrollment--747600-795782--"></a>Mobil cihaz kaydını kısıtlama özelliği<!--747600, 795782-->
Intune, katılmasına izin verilecek mobil cihaz platformlarını denetleyen yeni kayıt kısıtlamaları ekliyor. Intune, mobil cihaz platformlarını iOS, macOS, Android, Windows ve Windows Mobile şeklinde ayırıyor.

- Mobil cihaz kaydının kısıtlanması, bilgisayar istemcisi kaydını etkilemez.  
- Yalnızca iOS ve Android için kişisel cihazların kaydedilmesini engelleyen ek seçenek vardır.

Intune, BT yöneticileri [bu makalede](../enrollment/device-enrollment.md) anlatılan şekilde kuruluş cihazı olarak işaretlemediği sürece tüm yeni cihazları kişisel cihaz olarak işaretler.

### <a name="view-all-actions-on-managed-devices--677150--"></a>Yönetilen cihazlardaki tüm eylemleri görüntüleme<!--677150-->
Yeni __Cihaz Eylemleri__ raporu cihazları fabrika ayarlarına sıfırlama gibi uzaktan gerçekleştirilen eylemleri kimin yaptığını ve ilgili eylemin durumunu göstermektedir. Bkz. [Cihaz yönetimi nedir?](../remote-actions/device-management.md)

### <a name="non-managed-devices-can-access-assigned-apps--664691--"></a>Yönetilmeyen cihazlar atanmış uygulamalara erişebilir<!--664691-->
Şirket Portalı web sitesinde yapılan tasarım değişikliklerinin bir parçası olarak iOS ve Android kullanıcılar yönetilmeyen cihazlarında kendilerine "kayıtsız kullanılabilir" olarak atanmış uygulamaları yükleyebilecek. Kullanıcılar Intune kimlik bilgilerini kullanarak Şirket Portalı web sitesine girebilecek ve kendilerine atanan uygulamaların listesini görebilecek. "Kayıtsız kullanılabilir" uygulamaların uygulama paketleri Şirket Portalı web sitesinden indirilebilir. Yükleme için kayıt gerektiren uygulamalar bu değişikten etkilenmeyecek ve bu uygulamaları yüklemek isteyen kullanıcılardan cihazlarını kaydetmeleri istenecektir.

### <a name="custom-app-categories--748805--"></a>Özel uygulama kategorileri<!--748805-->
Artık Intune’a eklediğiniz uygulamalar için kategoriler oluşturabilir, düzenleyebilir ve atayabilirsiniz. Şu anda kategoriler yalnızca İngilizce olarak belirtilebilir.
Bkz. [Intune'a uygulama ekleme](../apps/apps-add.md).

### <a name="display-device-categories--814654--"></a>Cihaz kategorilerini görüntüleme<!--814654-->
Artık cihaz kategorisini cihaz listesinde ayrı bir sütunda görüntüleyebilirsiniz. Kategoriyi ayrıca cihaz özellikleri dikey penceresinin özellikler bölümünden de düzenleyebilirsiniz. Bkz. [Intune'a uygulama ekleme](../apps/apps-add.md).

### <a name="configure-windows-update-for-business-settings--776716--"></a>İşletmeler için Windows Update ayarlarını yapılandırma<!--776716-->

Hizmet olarak Windows, Windows 10 güncelleştirmeleri sağlamanın yeni yoludur. Windows 10’dan itibaren tüm yeni Özellik Güncelleştirmeleri ve Kalite Güncelleştirmeleri, önceki güncelleştirmelerin hepsinde yer alan içerikleri de kapsayacaktır. Böylece, en son güncelleştirmeyi yüklediğiniz sürece Windows 10 cihazlarınızın tamamen güncel olduğundan emin olabilirsiniz. Önceki Windows sürümlerinin aksine, artık güncelleştirmelerin tamamını yüklemeniz gerekir. Güncelleştirmenin yalnızca bir parçası yüklenemez.

İşletmeler için Windows Update’i kullanarak güncelleştirme yönetimi deneyimini, cihaz grupları için tek tek güncelleştirmelerin onaylanması gerekmeyecek şekilde basitleştirebilirsiniz. Ortamlarınızdaki riski yönetmek amacıyla hala bir güncelleştirme dağıtım stratejisi yapılandırabilirsiniz. Böyle yaptığınızda Windows Update güncelleştirmelerin doğru zamanda yüklenmesini sağlayacaktır. Microsoft Intune, cihazlarda güncelleştirme ayarlarının yapılandırılabilmesini sağlar ve güncelleştirme yüklemelerini erteleme olanağı tanır. Intune, güncelleştirmeleri değil yalnızca güncelleştirme ilkesi atamalarını depolar. Cihazlar, güncelleştirmeler için doğrudan Windows Update’e erişir. **Windows 10 güncelleştirme kademelerini** yapılandırmak ve yönetmek için Intune’u kullanın. Güncelleştirme kademesi, Windows 10 güncelleştirmelerinin ne zaman ve nasıl yükleneceğini yapılandıran bir dizi ayar içerir. Daha ayrıntılı bilgiler için bkz. [İşletmeler için Windows Update ayarlarını yapılandırma](../protect/windows-update-for-business-configure.md).
