---
title: Microsoft Intune - Azure’daki yenilikler | Microsoft Docs
titleSuffix: ''
description: Intune Azure portalındaki yenilikleri keşfedin
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/22/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: e3064a73cd9c56275363cce8c99190c4f5c98192
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "60164201"
---
# <a name="whats-new-in-microsoft-intune"></a>Microsoft Intune'daki yenilikler

Microsoft Intune’daki haftalık yenilikleri öğrenin. Ayrıca bulabilirsiniz [yaklaşan değişiklikleri](in-development.md), [önemli bildirimler](#notices)ve hakkında bilgi [eski sürümler](whats-new-archive.md). 

> [!Note]
> Bazı özelliklerin piyasaya çıkması birkaç haftayı bulabilir ve tüm özellikler ilk hafta bütün müşterilerimize sunulmamış olabilir.

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

<!-- ########################## -->

## <a name="week-of-april-22-2019"></a>22 Nisan 2019 haftası

### <a name="use-compliance-manager-to-create-assessments-for-microsoft-intune---4404750---"></a>Microsoft Intune değerlendirmeler oluşturmak için Uyumluluk Yöneticisi'ni kullanın<!-- 4404750 -->

[Uyumluluk Yöneticisi](https://servicetrust.microsoft.com/ComplianceManager) (başka bir Microsoft sitesi açılır) bir iş akışı tabanlı risk değerlendirmesi Microsoft hizmet güveni portalı aracıdır. İzleme, atamak ve Microsoft Hizmetleri ile ilgili kuruluşunuzun Mevzuata uygunluk etkinliklerinin doğrulamak sağlar. Office 365, Azure, Dynamics, Profesyonel Hizmetler ve Intune ile kendi uyumluluk değerlendirme oluşturabilirsiniz. Intune iki değerlendirmeleri kullanılamaz; FFIEC ve GDPR sahiptir.

Uyumluluk Yöneticisi denetimleri - Microsoft tarafından yönetilen denetimleri ve kuruluşunuz tarafından yönetilen bölmek çalışmalarınızı odaklanmanıza yardımcı olur. Değerlendirmeler tamamlayın ve ardından dışarı aktarmak ve değerlendirmeler yazdırma.

[Federal Finans kuruluşları İnceleme Council (FFIEC)](https://www.microsoft.com/trustcenter/compliance/FFIEC) (başka bir Microsoft sitesi açılır) uyumluluk FFIEC tarafından verilen çevrimiçi bankacılık standartları kümesidir. Bu, Intune kullanan Finans kuruluşları için en çok istenen değerlendirme olur. Bunu nasıl Intune FFIEC siber güvenlik yönergeleri ilgili genel bulut iş yüklerini karşılayacak yorumlar. Intune'un FFIEC değerlendirmesi ikinci FFIEC değerlendirmeyi uyumluluk Yöneticisi'nde durumda.

Aşağıdaki örnekte, döküm FFIEC denetimleri için görebilirsiniz. Microsoft, 64 denetimleri kapsar. Kalan 12 denetimler için sorumlu olursunuz.

![Bir örnek Intune değerlendirme müşteri Eylemler ve Microsoft Eylemler dahil olmak üzere FFIEC için bkz.](./media/intune-ffiec-assessment-status.png)

[Genel veri koruma yönetmeliği (GDPR)](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-overview) (başka bir Microsoft sitesi açılır) bir Avrupa Birliği (AB) modülünü yasadır haklarını kişiler ve verileri korumaya yardımcı olur. GDPR gizlilik düzenlemeleriyle yardımcı olması için en çok istenen değerlendirmesi ' dir. 

Aşağıdaki örnekte, GDPR denetimleri için dökümünü görürsünüz. Microsoft, 49 denetimleri kapsar. Kalan 66 denetimler için sorumlu olursunuz.

![Bir örnek Intune değerlendirmesi GDPR'ye müşteri Eylemler ve Microsoft Eylemler dahil olmak üzere, bkz.](./media/intune-assessment-status.png)

## <a name="week-of-april-15-2019"></a>15 Nisan 2019 haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="openssl-encryption-for-android-app-protection-policies----3747362---"></a>Android uygulama koruma ilkeleri için OpenSSL şifreleme <!-- 3747362 -->
Android cihazlarda Intune uygulama koruma ilkelerini (APP) artık FIPS 140-2 ile uyumlu olan bir OpenSSL şifreleme kitaplığını kullanır. Daha fazla bilgi için [şifreleme](app-protection-policy-settings-android.md#encryption) bölümünü [Android uygulama koruma İlkesi ayarları Microsoft Intune](app-protection-policy-settings-android.md).

#### <a name="enable-win32-app-dependencies----2617348----"></a>Win32 Uygulama bağımlılıklarını etkinleştirin <!-- 2617348  -->
Yönetici olarak, diğer uygulamalarda Win32 uygulamanızı yüklemeden önce bağımlılıkları olarak yüklendiğini gerektirebilir. Özellikle, Win32 Uygulama yüklenmeden önce cihaz bağımlı uygulamalarını yüklemeniz gerekir. Intune'da seçin **istemci uygulamaları** > **uygulamaları** > **Ekle** görüntülenecek **uygulama Ekle** dikey penceresi. Seçin **Windows uygulaması (Win32)** olarak **uygulama türü**. Uygulamayı ekledikten sonra seçebileceğiniz **bağımlılıkları** Win32 Uygulama yüklenmeden önce yüklenmesi gereken bağımlı uygulamaları eklemek için. Daha fazla bilgi için [tek başına Intune - Win32 Uygulama Yönetimi](apps-win32-app-management.md).

#### <a name="app-version-installation-information-for-microsoft-store-for-business-apps----3537391-----"></a>İş kolu uygulamaları için Microsoft Store için uygulama sürüm yükleme bilgileri <!-- 3537391   -->
Uygulama yükleme raporları, iş kolu uygulamaları için Microsoft Store uygulaması sürüm bilgilerini içerir. Intune'da seçin **istemci uygulamaları** > **uygulamaları**. Seçin bir **için iş kolu uygulamasını Microsoft Store** seçip **cihaz yükleme durumu** altında **İzleyici** bölümü.

#### <a name="additions-to-win32-apps-requirement-rules----3676883-----"></a>Win32 uygulamaları gereksinim kuralları eklemeler <!-- 3676883   -->
Gereksinim kuralları PowerShell betikleri, kayıt defteri değerlerini ve dosya sistemi bilgileri tabanlı oluşturabilirsiniz. Intune'da seçin **istemci uygulamaları** > **uygulamaları** > **Ekle**. Ardından **Windows uygulaması (Win32)** olarak **uygulama türü** içinde **uygulama Ekle** dikey penceresi.  Seçin **gereksinimleri** > **Ekle** ek gereksinim kurallarını yapılandırmak için. Ardından, ya da seçin **dosya türü**, **kayıt defteri**, veya **betik** olarak **gereksinim türü**. Daha fazla bilgi için [Win32 Uygulama Yönetimi](apps-win32-app-management.md).

 #### <a name="configure-your-win32-apps-to-be-installed-on-intune-enrolled-azure-ad-joined-devices----3695227----"></a>Intune'a kayıtlı üzerinde yüklenmesi, Win32 uygulamalarını yapılandırma Azure AD'ye katılmış cihazlar <!-- 3695227  -->
Intune'a kayıtlı üzerinde yüklenmesi, Win32 uygulamaları atayabilirsiniz Azure AD'ye katılmış cihazlar. Intune'da Win32 uygulamalar hakkında daha fazla bilgi için bkz. [Win32 Uygulama Yönetimi](apps-win32-app-management.md).

#### <a name="device-overview-shows-primary-user---794259----"></a>Birincil kullanıcı cihaz genel bakışı gösterir <!--794259  -->
Birincil de kullanıcı aygıt benzeşimi kullanıcı (UDA) adlı kullanıcı, cihaz genel bakış sayfası gösterilir. Bir cihaz için birincil kullanıcı görmek için **Intune** > **cihazları** > **tüm cihazlar** > bir cihaz seçin. Birincil kullanıcıya en görüneceğini **genel bakış** sayfası.

#### <a name="additional-managed-google-play-app-reporting-for-android-enterprise-work-profile-devices----4105925----"></a>Android kurumsal iş profili cihazları için raporlama ek yönetilen Google Play uygulaması <!-- 4105925  -->
Android kurumsal iş profili cihazlara dağıttığınız yönetilen Google Play uygulamaları için bir cihaza yüklenen uygulamanın belirli sürüm numarası görüntüleyebilirsiniz. Bu, yalnızca gerekli uygulamalar için geçerlidir. Gelecekteki bir sürümde aynı işlevselliği kullanılabilir uygulamalar için etkinleştirilir. 

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="set-login-settings-and-control-restart-options-on-macos-devices----1210083----"></a>Oturum açma ayarlarını ve macOS cihazlarında yeniden başlatma seçeneklerini denetleme <!-- 1210083  -->
MacOS cihazlarında cihaz yapılandırma profili oluşturabilirsiniz (**cihaz Yapılandırması** > **profilleri** > **profili oluşturma** > seçin **macOS** Platform > **cihaz özellikleri** profil türü için). Bu güncelleştirme gibi özel bir başlık gösteren yeni oturum açma penceresi ayarları içerir, nasıl kullanıcılar oturum açın, göstermek veya güç ayarlarını ve daha fazlasını gizlemek seçin.

Bu ayarları görmek için Git [macOS cihaz özelliği ayarlarını](macos-device-features-settings.md).

#### <a name="configure-wifi-on-android-enterprise-device-owner-dedicated-devices-running-in-multi-app-kiosk-mode---3041940----"></a>WiFi Android kuruluş, birden çok uygulamalı bilgi noktası modunda çalışan ayrılmış cihaz sahibi aygıtları yapılandırın. <!--3041940  -->
Android Enterprise, cihazı çoklu uygulama bilgi noktası modunda ayrılmış bir cihaz olarak çalışırken sahip ayarları etkinleştirebilirsiniz. Bu güncelleştirme, yapılandırmak ve Wi-Fi ağlarına bağlanmak kullanıcıların etkinleştirebilirsiniz (**Intune** > **cihaz Yapılandırması** > **profilleri**  >  **Profili oluşturma** > **Android Kurumsal** Platform > **yalnızca cihaz sahibi, cihaz kısıtlamaları** profil türü için >  **Adanmış cihazlar** > **bilgi noktası modu**: **Multi-App** > **WiFi Yapılandırması**). 

Yapılandırabileceğiniz ayarlar görmek için Git [izin vermek veya özellikleri kısıtlamak için Android Kurumsal cihaz ayarları](device-restrictions-android-for-work.md).

Şunun için geçerlidir: Çoklu uygulama bilgi noktası modunda çalışan android ayrılmış Kurumsal cihazlar


#### <a name="configure-bluetooth-and-pairing-on-android-enterprise-device-owner-dedicated-devices-running-in-multi-app-kiosk-mode----3041941----"></a>Bluetooth ve ayrılmış cihazları çoklu uygulama bilgi noktası modunda çalışan Android kuruluş, cihaz sahibi eşleştirme yapılandırın <!-- 3041941  -->
Android Enterprise, cihazı çoklu uygulama bilgi noktası modunda ayrılmış bir cihaz olarak çalışırken sahip ayarları etkinleştirebilirsiniz. Bu güncelleştirmede, Bluetooth etkinleştirmek son kullanıcılara izin ver ve cihazların Bluetooth üzerinden eşleştirin (**Intune** > **cihaz Yapılandırması** > **profilleri**  >  **Profili oluşturma** > **Android Kurumsal** Platform > **yalnızca cihaz sahibi, cihaz kısıtlamaları** profili türü > **adanmış cihazlar** > **bilgi noktası modu**: **Multi-App** > **Bluetooth yapılandırma**). 

Yapılandırabileceğiniz ayarlar görmek için Git [izin vermek veya özellikleri kısıtlamak için Android Kurumsal cihaz ayarları](device-restrictions-android-for-work.md).

Şunun için geçerlidir: Çoklu uygulama bilgi noktası modunda çalışan android ayrılmış Kurumsal cihazlar

#### <a name="create-and-use-oemconfig-device-configuration-profiles-in-intune----3305883----"></a>Oluşturma ve Intune'da OEMConfig cihaz yapılandırma profillerini kullanma <!-- 3305883  -->
Bu güncelleştirme, Intune OEMConfig ile Android Kurumsal cihazların yapılandırılmasını destekler. Özellikle, bir cihaz yapılandırma profili oluşturabilir ve ayarları OEMConfig kullanarak kurumsal Android cihazlar için geçerlidir (**cihaz Yapılandırması** > **profilleri**  >  **Profili oluşturma** > **Android Kurumsal** platform için).

OEM'leri şu anda bir OEM başına temelinde desteğidir. İstediğiniz OEMConfig uygulama OEMConfig uygulamalar listesinde kullanılabilir değilse, ilgili kişi `IntuneOEMConfig@microsoft.com`.

Bu özellik hakkında daha fazla bilgi için şuraya gidin [kullanmak ve Microsoft Intune OEMConfig ile Android Kurumsal cihaz yönetmek](android-oem-configuration-overview.md).

Şunun için geçerlidir: Android Kurumsal

#### <a name="windows-update-notifications-----3316758-3316782----"></a>Windows güncelleştirme bildirimleri  <!-- 3316758, 3316782  -->
İki ekledik *kullanıcı deneyimi ayarlarını* ayarları Windows Update'e halka yapılandırmalar gelen Intune konsolundan yönetebilirsiniz. Artık şunları yapabilirsiniz:
- Kullanıcılara izin ver veya engelle [Windows güncelleştirmeleri için tarama](windows-update-settings.md#block-user-from-scanning-for-windows-updates).
- Yönetme [Windows güncelleştirme bildirimi düzeyine](windows-update-settings.md#windows-update-notification-level) kullanıcılar görür.

#### <a name="new-device-restriction-settings-for-android-enterprise-device-owner----3574254----"></a>Android Enterprise, cihaz sahibi için yeni cihaz kısıtlama ayarları <!-- 3574254  -->
Android Kurumsal cihazlarda izin vermek veya özellikler, parola kuralları ayarla ve daha fazla kısıtlamak için cihaz kısıtlama profili oluşturabilirsiniz (**cihaz Yapılandırması** > **profilleri**  >  **Profili oluşturma** > seçin **Android Kurumsal** Platform > **yalnızca cihaz sahibi > cihaz kısıtlamaları** profil türü için). 

Bu güncelleştirme, yeni parola ayarları içerir, tam olarak yönetilen cihazları ve daha fazlası için Google Play Store uygulamaları için tam erişim sağlar. Geçerli ayarları listesini görmek için Git [izin vermek veya özellikleri kısıtlamak için Android Kurumsal cihaz ayarları](device-restrictions-android-for-work.md). 

Şunun için geçerlidir: Android Kurumsal tam olarak yönetilen cihazlar

#### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy----3617671---"></a>Bir Windows 10 cihaz uyumluluk İlkesi, TPM yonga denetle <!-- 3617671 -->

Bu özellik ertelendi ve gelecekteki bir sürümde eklenmelidir.

#### <a name="updated-ui-changes-for-microsoft-edge-browser-on-windows-10-and-later-devices----3775833-----"></a>Windows 10 ve üzeri cihazlarda Microsoft Edge tarayıcısı için güncelleştirilmiş kullanıcı Arabirimi değişiklikleri <!-- 3775833   -->
Bir cihaz yapılandırma profili oluşturduğunuzda, izin verebilir veya Windows 10 ve üzeri cihazlarda Microsoft Edge kısıtlamanıza (**cihaz Yapılandırması** > **profilleri**  >  **Profili oluşturma** > **Windows 10 ve üzeri** bir platform için > **cihaz kısıtlamaları** profil türü için >  **Microsoft Edge tarayıcısı**). Bu güncelleştirme, Microsoft Edge ayarlarını daha açıklayıcı ve daha kolay anlaşılır. 

Bu özellikleri görmek için Git [Microsoft Edge tarayıcı cihaz kısıtlama ayarları](device-restrictions-windows-10.md#microsoft-edge-browser).

Şunun için geçerlidir: Windows 10 ve üzeri

#### <a name="expanded-support-for-android-enterprise-fully-managed-devices--preview-------3903241-3903244-3903246-----"></a>Android Enterprise için genişletilmiş destek tam olarak yönetilen cihazlar (Önizleme)  <!--   3903241, 3903244, 3903246   -->
Yine de bir genel önizlemede olan desteğimiz tam olarak yönetilen Android Kurumsal cihaz biz Genişletilmiş ([2019'ın Ocak ilk duyurulan](whats-new.md#week-of-january-14-2019) şunlar için: 

- Cihazlarda, tamamen yönetilen ve özel oluşturduğunuz [uyumluluk ilkeleri](compliance-policy-create-android-for-work.md) parola kuralları ve işletim sistemi gereksinimleri dahil edilecek (**cihaz uyumluluğu**  >   **İlkeleri** > **ilkesi oluşturma** > **Android Kurumsal** Platform > **cihaz sahibi** için Profil türü). 

  Adanmış cihazlarda, cihazı olarak gösterebilir **uyumlu**. Koşullu erişim, adanmış cihazlarda kullanılamaz. Herhangi bir görev veya ayrılmış cihazları atanan ilkelerinizle uyumlu almak için Eylemler tamamladığınızdan emin olun.

- [Koşullu erişim](conditional-access.md) -koşullu erişim Android için geçerli olan ilkeleri de geçerli Android Enterprise için tam olarak yönetilen cihazlar. Kullanıcılar artık kaydedebilir tam olarak yönetilen cihazlarını Azure Active Directory kullanarak **Intune uygulama**. Daha sonra bkz ve kurumsal kaynaklara erişmek için uyumluluk sorunları çözün.

- Android tam olarak yönetilen olarak adlandırılan cihazlar için yeni bir son kullanıcı uygulaması olduğundan yeni son kullanıcı uygulama (Microsoft Intune uygulama) - **Intune**. Bu yeni uygulamaya basit ve modern ve işlevsel olarak Şirket portalı uygulaması, ancak tam olarak yönetilen cihazlara benzer sağlar. Daha fazla bilgi için [Google play'de Microsoft Intune uygulama](https://play.google.com/store/apps/details?id=com.microsoft.intune).

Ayarlamak için Android tam olarak yönetilen cihazlar, Git **cihaz kaydı** > **Android kaydını** > **şirkete, tam olarak yönetilen kullanıcı cihazları**. Destek için tam olarak yönetilen Android cihazları hala Önizleme aşamasındadır ve bazı Intune özellikleri tam olarak işlevsel olmayabilir.  

Bu önizleme sürümü hakkında daha fazla bilgi için blog gönderimize göz atabilirsiniz, [Intune - Preview 2 Android kuruluş tam olarak yönetilen cihazlar için](https://aka.ms/preview2_AE_fullymanaged).


### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="configure-profile-to-skip-some-screens-during-setup-assistant----2276470--wnstaged--"></a>Bazı ekranlar Kurulum Yardımcısı sırasında atlanacak profili yapılandırma <!-- 2276470  wnstaged-->
MacOS kayıt profili oluşturduğunuzda, bir kullanıcı Kurulum Yardımcısı gittiğinde aşağıdaki ekranlardan herhangi birinde atlamak için yapılandırabilirsiniz:
- Görünüm
- Görüntü Tonu
- Yeni bir profil oluşturun ya da bir profil düzenleme iCloudStorage seçili ekranlar Apple MDM sunucusu ile eşitleme gerek atlayın.  Kullanıcılar, böylece gecikme profili değişiklikleri çekme cihazların el ile eşitleme verebilir.
Daha fazla bilgi için [macOS cihazlarını cihaz kayıt programı veya Apple School Manager ile otomatik olarak kaydetme](device-enrollment-program-enroll-macos.md).

#### <a name="bulk-device-naming-when-enrolling-corporate-ios-devices--3566569----"></a>Toplu cihaz Kurumsal iOS cihazlarını kaydetme işleminde adlandırma<!--3566569  -->
Apple'nın Kurumsal kayıt yöntemleri (DEP/ABM/ASM) birini kullanırken, otomatik olarak ad gelen iOS cihazları için cihaz adı biçimi ayarlayabilirsiniz. Şablonunuzda seri numarasını ve cihaz türünü içeren bir biçim belirtebilirsiniz. Bunu yapmak için **Intune** > **cihaz kaydı** > **Apple kaydı** > **kayıt programı belirteçleri** > **bir belirteç seçin** >**profili oluşturma** > **aygıt adlandırma biçimi**. Var olan profilleri düzenleyebilirsiniz ancak yalnızca yeni eşitlenen cihazlar uygulanan adı gerekir.

#### <a name="updated-default-timeout-message-on-enrollment-status-page----3959331---"></a>Kayıt durumu sayfasında güncelleştirilmiş varsayılan zaman aşımı iletisi <!-- 3959331 -->
Kayıt durumu sayfası (ESP) ESP profilinde belirtilen zaman aşımı değerini aşarsa, kullanıcıların gördüğü varsayılan zaman aşımı iletisi güncelleştirdik. Yeni varsayılan ileti metni yazın hangi kullanıcıların görebileceği ve bunların ESP dağıtımla gerçekleştirilecek sonraki eylemler anlamalarına yardımcı olur.  

### <a name="device-management"></a>Cihaz yönetimi

#### <a name="retire-noncompliant-devices-----1827291-----"></a>Uyumlu olmayan cihazları devre dışı bırakma  <!-- 1827291   -->
Bu özellik ertelendi ve gelecekteki bir sürümde gelir.


### <a name="monitor-and-troubleshoot"></a>İzleme ve sorun giderme

#### <a name="intune-data-warehouse-v10-changes-reflecting-back-to-beta----4403765---"></a>Intune veri ambarı V1.0 değişiklikleri beta için yansıtma <!-- 4403765 -->
V1.0, ilk olarak 1808 içinde sunulmuştur, önemli bazı açılardan'ı Beta'dan API farklıydı. 1903 bu değişiklikleri geri beta API sürümüne yansıtılır. Beta API sürümünü kullanan önemli raporlarınız varsa, bu raporları önemli değişiklikler önlemek için V1.0 geçiş kesinlikle öneririz. Daha fazla bilgi için [değişiklik günlüğü için Intune veri ambarı API'si](reports-changelog.md#1903-part-2).

#### <a name="monitor-security-baseline-status-public-preview----3082047---"></a>(Genel Önizleme) güvenlik durumunu izleme <!-- 3082047 --> 
Eklediğimiz bir [Kategori başına görünümü](security-baselines-monitor.md#per-category-view) güvenlik temellerini izleme. (Güvenlik temellerini Önizleme'de kalır). Kategori başına görünümü her kategori taban çizgisi birlikte her durum grubuna için bu kategoriye giren cihazların yüzdesini görüntüler. Artık, kaç cihazın bireysel kategorisi eşleşmezse, yanlış veya uygulanamaz görebilirsiniz.

### <a name="role-based-access-control"></a>Rol tabanlı erişim denetimi

#### <a name="scope-tags-for-apple-vpp-tokens---2371886----"></a>Kapsam etiketleri Apple VPP belirteçleri <!--2371886  -->
Kapsam etiketleri, artık Apple VPP belirteçleri ekleyebilirsiniz. Bu etikete sahip Apple VPP belirtecinin yalnızca aynı kapsam etiketi ile atanan kullanıcılar erişebilir. VPP uygulamalarını ve o belirteç ile satın alınan e-Kitaplar, kapsam etiketleri devralır. Kapsam etiketleri hakkında daha fazla bilgi için bkz: [kullanım RBAC ve kapsam etiketleri](scope-tags.md).







## <a name="week-of-april-1-2019"></a>1 Nisan 2019 haftası

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="updated-certificate-connectors-----icm-113304612---"></a>Güncelleştirilmiş sertifika bağlayıcılar  <!-- ICM 113304612 -->
Güncelleştirmeler için hem de yayımladık [Intune sertifika Bağlayıcısı ve PFX sertifika Bağlayıcısı'nı](certficates-pfx-configure.md#whats-new-for-connectors). Yeni sürümleri bazı bilinen sorunlar düzeltildi.  

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="user-experience-update-for-the-company-portal-app-for-ios----2536024---"></a>İOS için Şirket portalı uygulaması için kullanıcı deneyimi güncelleştirmesi <!-- 2536024 -->
İOS cihazları için Şirket portalı uygulamasının giriş sayfası yeniden tasarlandı. Bu değişiklik, giriş sayfası iOS kullanıcı Arabirimi desenleri daha iyi izleyin ve ayrıca uygulamaları ve e-Kitaplar için geliştirilmiş bulunabilirliği sağlamak.

#### <a name="changes-to-company-portal-enrollment-for-ios-12-device-users---3448635---"></a>İOS için Şirket portalı kaydı için 12 cihaz kullanıcılarının değiştirir. <!--3448635 -->  
İOS kayıt ekranlar ve adımlar için Şirket portalı, Apple iOS 12.2 yayımlanan MDM kayıt değişikliklerle hizalamak için güncelleştirildi. Güncelleştirilmiş iş akışı, kullanıcıların ister:  

* Şirket portalı Web sitesini açın ve Şirket portalı uygulamasında döndürmeden önce yönetim profili yüklemek Safari izin verir.  
* Yönetim profili cihaza yüklemek üzere ayarlar uygulamasını açın.
* Şirket portalı uygulamasının kaydı döndürür.  

Güncelleştirilmiş kayıt adımları ve ekranlar için bkz: [iOS Cihazınızı Intune'a kaydetme](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios).  

## <a name="week-of-march-25-2019"></a>25 Mart 2019 haftası

### <a name="monitor-and-troubleshoot"></a>İzleme ve sorun giderme

### <a name="support-for-the-power-bi-compliance-app-from-the-data-warehouse-blade-in-microsoft-intune----4260871---"></a>Power BI uyumluluğu uygulamayı Microsoft Intune veri ambarı dikey penceresinden desteği <!-- 4260871 -->
Daha önce **indirme Power BI dosyasını** bağlantısını **Intune veri ambarı** dikey indirilen bir Intune veri ambarı rapor (.pbix dosyası). Bu raporu Power BI uyumluluğu uygulama ile değiştirilmiştir. Power BI uyumluluğu uygulama özel yükleme veya Kurulum gerektirmez. Bu doğrudan Power BI çevrimiçi portalda açın ve özellikle, kimlik bilgileri temelinde, Intune kiracınıza verileri görüntüler. Intune'da seçin **Intune veri ambarı ayarlama** Intune dikey penceresinin sağ tarafındaki bağlantı. ' A tıklayarak **Al Power BI uygulaması**. Daha fazla bilgi için [Power BI ile veri ambarına bağlanma](reports-proc-get-a-link-powerbi.md).

## <a name="week-of-march-18-2019"></a>18 Mart 2019 haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="deploy-microsoft-visio-and-microsoft-project----3725386----"></a>Microsoft Visio ve Microsoft Project'te dağıtma <!-- 3725386  -->
Bu uygulamalar için lisanslarına sahipseniz artık Microsoft Visio Pro için Office 365 ve Microsoft Project Online masaüstü istemcisi Windows 10 cihazlara Microsoft Intune kullanarak bağımsız uygulama olarak dağıtabilirsiniz. Intune'dan seçin **istemci uygulamaları** > **uygulamaları** > **Ekle** görüntülenecek **uygulama Ekle** dikey penceresi. Üzerinde **uygulama Ekle** dikey penceresinde **Windows 10** olarak **uygulama türü**. Ardından, **uygulama paketini Yapılandır** yüklenecek uygulamaları seçin. Windows 10 cihazlar için Office 365 uygulamaları hakkında daha fazla bilgi için bkz: [atama Office 365 uygulamalarını Windows 10 cihazlarına Intune](apps-add-office365.md).

#### <a name="microsoft-visio-pro-for-office-365-product-name-change----3593653----"></a>Microsoft Visio Pro için Office 365 ürün adı değişikliği <!-- 3593653  -->
**Office 365 için Microsoft Visio Pro** artık olarak biliniyor **Microsoft Visio Online Plan 2**.  Microsoft Visio hakkında daha fazla bilgi için bkz: [Visio Online Plan 2](https://products.office.com/visio/visio-online-plan-2). Windows 10 cihazlar için Office 365 uygulamaları hakkında daha fazla bilgi için bkz: [atama Office 365 uygulamalarını Windows 10 cihazlarına Intune](apps-add-office365.md).

#### <a name="intune-app-protection-policy-app-character-limit-setting----3291302----"></a>Intune uygulama koruma İlkesi (uygulama) karakter sınırını ayarlama <!-- 3291302  -->
Intune yöneticileri, Intune uygulama için bir özel durum belirtebilirsiniz **kısıtlama kesme, kopyalama ve yapıştırma diğer uygulamalarla** ilke ayarı.  Yönetici olarak, yönetilen bir uygulamadan kopyalanan veya kesin olabilir karakter sayısını belirtebilirsiniz. Bu ayar belirtilen sayıda karakteri "kısıtlama kesme, kopyalama ve yapıştırma diğer uygulamalarla" bağımsız olarak herhangi bir uygulamaya paylaşılmasına izin ayarı. Android için Intune şirket Portalı Uygulama sürümü, sürüm 5.0.4364.0 gerektirdiğine dikkat edin veya üzeri. Daha fazla bilgi için [iOS veri koruma](app-protection-policy-settings-ios.md#data-protection), [Android veri koruma](app-protection-policy-settings-android.md#data-protection), ve [istemci uygulama koruma günlüklerini gözden geçirme](app-protection-policy-settings-log.md#app-protection-policy-settings).

#### <a name="office-deployment-tool-odt-xml-for-office-proplus-deployment----3192477-----"></a>Office dağıtım aracı (ODT) Office ProPlus dağıtım için XML <!-- 3192477   -->
Office dağıtım aracı (ODT) XML örneği Office Pro Plus Intune Yönetici konsolunda oluştururken sağlamak mümkün olacaktır. Mevcut Intune kullanıcı Arabirimi seçenekleri ihtiyaçlarınızı karşılamıyorsa Bunun büyük sağlamadığından olanak tanır. Daha fazla bilgi için [atama Office 365 uygulamalarını Windows 10 cihazlarına Intune](https://docs.microsoft.com/intune/apps-add-office365) ve [Office Dağıtım Aracı'nı yapılandırma seçenekleri](https://docs.microsoft.com/DeployOffice/configuration-options-for-the-office-2016-deployment-tool).

#### <a name="app-icons-will-now-be-displayed-with-an-automatically-generated-background----1429026----"></a>Uygulama simgeleri artık otomatik olarak oluşturulmuş bir arka plan ile görüntülenir <!-- 1429026  -->
Windows Şirket portalı uygulamasında uygulama simgeleri artık baskın renge göre (algılanamazsa) tabanlı bir otomatik olarak oluşturulmuş bir arka plan ile görüntülenecektir. Uygun olduğunda, bu arka plan daha önce uygulama kutucuklarında görünen gri kenarlıkların yerine geçer. Kullanıcılar Şirket portalı 10.3.3451.0 daha sonraki sürümlerinde bu değişikliği görür.

#### <a name="install-available-apps-using-the-company-portal-app-after-windows-bulk-enrollment----2751523-----"></a>Windows toplu kaydı sonra Şirket portalı uygulamasını kullanırken kullanılabilir uygulamaları yüklemesi <!-- 2751523   -->
Intune kullanarak kayıtlı Windows cihazları [Windows toplu kayıt](windows-bulk-enroll.md) (sağlama paketlerinin) kullanılabilir uygulamaları yüklemesi için Şirket portalı uygulamasını kullanmanız mümkün olacaktır. Şirket portalı uygulaması hakkında daha fazla bilgi için bkz. [el ile Windows 10 Şirket portalı ekleme](store-apps-company-portal-app.md) ve [Microsoft Intune Şirket portalı uygulamasını yapılandırma](company-portal-app.md).

> [!Note]
> Bu özellik henüz tam olarak tüm müşterilere dağıtılmaz. Toplu kayıtlı cihazlarda şirket portalını kullanması mümkün değilse, bu değişiklik, hesabınıza dağıtılırken beklemeniz gerekebilir.

#### <a name="the-microsoft-teams-app-can-be-selected-as-part-of-the-office-app-suite----3828932----"></a>Microsoft Teams uygulaması Office uygulama paketinin bir parçası seçilebilir <!-- 3828932  -->
Microsoft Teams uygulaması dahil edilecek veya hariç Office Pro Plus uygulama paketi yüklemesinin bir parçası. Bu özellik için derleme numarası 16.0.11328.20116+ Office Pro Plus çalışır. Kullanıcı, oturumu kapatın ve sonra cihaz yüklemenin tamamlanması için oturum açın. Intune'da seçin **istemci uygulamaları** > **uygulamaları** > **Ekle**. Birini **Office 365 paketi** uygulama türleri ve ardından **uygulama paketini Yapılandır**.

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="automatically-start-an-app-when-running-multiple-apps-in-kiosk-mode-on-windows-10-and-later-devices----2351390---"></a>Windows 10 ve üzeri cihazlar üzerinde birden fazla uygulama bilgi noktası modunda çalışan bir uygulama otomatik olarak Başlat <!-- 2351390 -->

Windows 10 ve üzeri cihazlarda, cihaz bilgi noktası modunda çalıştırmak ve pek çok uygulamaları çalıştırma. Bu güncelleştirmede, var. bir **AutoLaunch** ayarı (**cihaz Yapılandırması** > **profilleri** > **profilioluşturma**  >  **Windows 10 ve üzeri** Platform > **bilgi noktası** profil türü için > **çoklu uygulama bilgi noktası**). Cihaza kullanıcı oturum açtığı zaman uygulama otomatik olarak başlatmak için bu ayarı kullanın.

Bir listesi ve açıklamaları tüm bilgi noktası ayarları görmek için bkz: [Windows 10 ve üzeri cihaz ayarları ıntune'da bilgi noktası olarak çalıştırılacak](kiosk-settings-windows.md).

Şunun için geçerlidir: Windows 10 ve üzeri

#### <a name="operational-logs-also-show-details-on-non-compliant-devices----4063755----"></a>İşlem günlüklerinde de uyumlu olmayan cihazların ayrıntılarını göster <!-- 4063755  -->
Yönlendirme Intune özelliklerini Azure İzleyici açtığında, işlem günlüklerinde de yönlendirebilirsiniz. Bu güncelleştirme, işlem günlüklerinde uyumlu olmayan cihazların bilgileri de sağlar. 

Bu özellik hakkında daha fazla bilgi için bkz. [depolama, olay hub'ları veya Intune log analytics'te günlük verilerini gönderme](review-logs-using-azure-monitor.md).

#### <a name="route-logs-to-azure-monitor-in-more-intune-workloads----3804627---"></a>Daha fazla Intune iş yükleri için Azure İzleyici yolu günlükleri <!-- 3804627 -->
Intune'da olayları hubs, depolama, Denetim ve operasyonel günlükler yönlendirmek ve analytics Azure İzleyici'de oturum (**Intune** > **izleme** > **tanılama ayarları**). Bu güncelleştirmede, bu günlükleri uyumluluk, yapılandırmaları, istemci uygulamaları ve diğer gibi daha fazla Intune iş yükleri yönlendirebilirsiniz. 

Azure İzleyici günlüklerine yönlendirme hakkında daha fazla bilgi için bkz: [olay hub'ları, depolama için günlük verileri gönderin veya günlük analizi](review-logs-using-azure-monitor.md).

#### <a name="create-and-use-mobility-extensions-on-android-zebra-devices-in-intune----3305880-----"></a>Oluşturma ve ıntune'da Android Zebra cihazlarda mobility uzantıları kullanma <!-- 3305880   -->
Bu güncelleştirme, Intune, Android Zebra cihazların yapılandırılmasını destekler. Özellikle, bir cihaz yapılandırma profili oluşturabilir ve ayarlar StageNow tarafından oluşturulan Mobility Uzantıları (MX) profilleri kullanarak Zebra Android cihazları için geçerlidir (**cihaz Yapılandırması**  >   **Profilleri** > **profili oluşturma** > **Android** platformuna yönelik > **MX profili (yalnızca Zebra)** profili türü).

Bu özellik hakkında daha fazla bilgi için bkz. [kullanın ve Intune mobility uzantılarında Zebra cihazları yönetme](android-zebra-mx-overview.md).

Şunun için geçerlidir: Android

### <a name="device-management"></a>Cihaz yönetimi

#### <a name="encryption-report-for-windows-10-devices-in-public-preview---2351538---"></a>Windows 10 cihazları için şifreleme raporu (genel önizlemede)<!-- 2351538 -->  
Yeni [şifreleme raporu (Önizleme)](encryption-monitor.md) Windows 10 cihazlarınızın şifreleme durumu hakkındaki ayrıntıları görüntülemek için. Mevcut ayrıntıları, cihazlar TPM sürümü, şifreleme hazırlık ve durumu, hata raporlama ve daha fazlasını içerir.  

#### <a name="access-bitlocker-recovery-keys-from-the-intune-portal-in-public-preview----2351547-----"></a>Intune portalında (genel Önizleme) erişim BitLocker kurtarma anahtarları <!-- 2351547   -->  
Artık Intune'a kullanabilirsiniz [ayrıntıları görüntüle](encryption-monitor.md) BitLocker anahtarı kimliği ve BitLocker kurtarma anahtarları, Azure Active Directory'den hakkında.

#### <a name="microsoft-edge-support-for-intune-scenarios-on-ios-and-android-devices----3411007---"></a>İOS ve Android cihazlarda Intune senaryolarını desteğini Microsoft Edge <!-- 3411007 -->
Microsoft Edge tüm Intune Managed Browser ile son kullanıcı deneyimi geliştirmelerine ek olarak aynı yönetim senaryolarını destekler. İkili kimlik, uygulama koruma İlkesi tümleştirmesi, Azure uygulama proxy'si tümleştirmesi ve yönetilen Sık Kullanılanlar ve giriş sayfası kısayolları Intune ilkeleri ile etkinleştirilen Microsoft Edge Kurumsal özellikler içerir. Daha fazla bilgi için [Microsoft Edge desteği](app-configuration-managed-browser.md#microsoft-edge-support).

#### <a name="exchange-onlineintune-connector-deprecate-support-for-eas-only-devices---3105122----"></a>Exchange Online/Intune Bağlayıcısı kullanımdan EAS yalnızca cihazlar için destek <!--3105122  -->
Intune konsolunda artık görüntüleme destekler ve Intune Bağlayıcısı ile Exchange Online'a yalnızca EAS cihazları yönetmeye bağlı. Bunun yerine aşağıdaki seçenekleriniz vardır:
- Mobil cihaz Yönetimi (MDM) cihazlarını kaydetme
- Cihazlarınızı yönetmek için Intune uygulama koruma ilkelerini kullanma
- Açıklandığı gibi Exchange denetimleri kullanın [istemcileri ve Exchange Online mobil](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/clients-and-mobile-in-exchange-online)

### <a name="search-the-all-devices-page-for-an-exact-device-by-using-name---4254930---"></a>[Name]'ı kullanarak tam bir cihaz için tüm cihazlar sayfasında arama <!--4254930 -->
Artık, bir tam cihaz adı için arama yapabilirsiniz. Git **Intune** > **cihazları** > **tüm cihazlar** > cihaz adıyla Ara kutusuna çevreleyen {} aramak için bir tam eşleşme. Örneğin, **{Device12345}**.

### <a name="monitor-and-troubleshoot"></a>İzleme ve sorun giderme

#### <a name="support-for-additional-connectors-on-the-tenant-status-page----3617202----"></a>Kiracı durumu sayfasında ek bağlayıcı desteği <!-- 3617202  -->
[Kiracı durumu sayfası](tenant-status.md) artık dahil olmak üzere, ek bağlayıcıları için durum bilgilerini görüntüler *Windows Defender Gelişmiş tehdit koruması* (ATP) ve diğer Mobile Threat Defense bağlayıcıları.

### <a name="role-based-access-control"></a>Rol tabanlı erişim denetimi

#### <a name="granting-intune-read-only-access-to-some-azure-active-directory-roles----3637917----"></a>Intune verme yalnızca bazı Azure Active Directory rolleri için okuma erişimi <!-- 3637917  -->
Intune, yalnızca erişim için aşağıdaki Azure AD rolleri verildi okuyun. Azure AD rolleri ile verilen izinler, Intune rol tabanlı erişim denetimi (RBAC) izinler yerini alır.

Yalnızca Intune denetim verilerine erişim okuyun:

- Uyumluluk Yöneticisi
- Uyumluluk veri Yöneticisi

Yalnızca tüm Intune verilerine erişim okuyun:

- Güvenlik Yöneticisi
- Güvenlik işleci
- Güvenlik okuyucusu

Daha fazla bilgi için [rol tabanlı erişim denetimi](role-based-access-control.md).

#### <a name="scope-tags-for-ios-app-provisioning-profiles---2934430-----"></a>Kapsam etiketleri için iOS uygulama sağlama profilleri <!--2934430   -->
Böylece yalnızca kişiler de bu kapsam etiketi atanan rollerle iOS uygulama sağlama profili erişimi, bir iOS uygulama sağlama profili bir kapsam etiketi ekleyebilirsiniz. Daha fazla bilgi için [kullanım RBAC ve kapsam etiketleri](scope-tags.md).

#### <a name="scope-tags-for-app-configuration-policies---2371891-----"></a>Kapsam etiketleri için uygulama yapılandırma ilkeleri <!--2371891   -->
Böylece kişiler de bu kapsam etiketi atanan rollerle yalnızca uygulama yapılandırma İlkesi erişimi, bir uygulama yapılandırma ilkesi için bir kapsam etiketi ekleyebilirsiniz. Uygulama yapılandırma ilkesini yalnızca hedeflenen veya aynı kapsam etiketi atanan uygulamalarla ilişkili. Daha fazla bilgi için [kullanım RBAC ve kapsam etiketleri](scope-tags.md).

### <a name="microsoft-edge-support-for-intune-scenarios-on-ios-and-android-devices----3411007---"></a>İOS ve Android cihazlarda Intune senaryolarını desteğini Microsoft Edge <!-- 3411007 -->
Microsoft Edge tüm Intune Managed Browser ile son kullanıcı deneyimi geliştirmelerine ek olarak aynı yönetim senaryolarını destekler. İkili kimlik, uygulama koruma İlkesi tümleştirmesi, Azure uygulama proxy'si tümleştirmesi ve yönetilen Sık Kullanılanlar ve giriş sayfası kısayolları Intune ilkeleri ile etkinleştirilen Microsoft Edge Kurumsal özellikler içerir. Daha fazla bilgi için [Microsoft Edge desteği](app-configuration-managed-browser.md#microsoft-edge-support).

## <a name="week-of-february-25-2019"></a>25 Şubat 2019 haftası

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="intune-powershell-module----951068----"></a>Intune PowerShell Modülü <!-- 951068  -->
Microsoft Graph aracılığıyla Intune API için destek sağlar, Intune PowerShell modülünü kullanıma sunulduğunu [Microsoft PowerShell Gallery](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1902.1.10).

- [Bu modül hakkında ayrıntılı bilgi kullanın](https://github.com/Microsoft/Intune-PowerShell-SDK/blob/master/README.md)
- [Bu modül kullanılarak senaryo örnekleri](https://github.com/Microsoft/Intune-PowerShell-SDK/blob/master/Samples/README.md)

#### <a name="improved-support-for-delivery-optimization----3183757----"></a>Teslim iyileştirme için gelişmiş destek  <!--3183757  -->
Biz teslim iyileştirme'yi yapılandırmak için Intune desteği genişletilmiş. Artık genişletilmiş bir listesini yapılandırabilirsiniz [teslim iyileştirme ayarlarını](delivery-optimization-settings.md) ve doğrudan Intune konsolundan cihazlarınıza hedefleyebilirsiniz.


## <a name="week-of-february-18-2019"></a>18 Şubat 2019 haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="intune-will-leverage-google-play-protect-apis-on-android-devices----2577355-----"></a>Intune, Android cihazlarda Google Play koruma API'lerini özelliğinden yararlanır <!-- 2577355   -->
Bazı BT yöneticileri, bir KCG yatay, burada son kullanıcıların kök dizini değiştirme veya jailbreaking, cep telefonu sonlandırabiliriz kalmaktadır. Bu davranış, bazen de hatalı niyetli olsa da, son kullanıcı cihazlarında kuruluşunuzun verilerini korumak için ayarlanan birçok Intune ilkeleri, bir geçiş sonuçlanır. Bu nedenle, Intune kayıtlı ve kayıtsız cihazlar için kök ve jailbreak uygulanmasını algılama sağlar. Bu sürümle birlikte, Intune artık Google Play koruma kayıtlı olmayan cihazlar için mevcut bizim kök algılama denetimleri eklemek için API'leri özelliğinden yararlanır. Google oluşan kök algılama denetimlerin tamamen paylaşmaz, ancak kullanıcılar, cihazlarını daha yeni işletim sistemi güncelleştirmelerini eski cihazlarda alabilmek için herhangi bir nedenle cihaz özelleştirmesinde kökü algılamak için bu API'leri bekliyoruz. Bu kullanıcılar daha sonra kurumsal verilere erişimi engellenebilir veya Kurumsal hesaplarını etkin ilke uygulamalarından silinecek. Ek değer, BT yöneticisinin Intune uygulama koruması dikey penceresi içinde çeşitli raporlama güncelleştirmeler artık sahip - "Bayrak eklenen kullanıcılar" raporu hangi kullanıcıların algılanan gösterir Google Play Protect'ın SafetyNet API tarama ile rapor "potansiyel olarak zararlı uygulamalar" olacaktır hangi uygulamaların Google'nın doğrulayın uygulamaları tarama API aracılığıyla algılanan gösterir. Bu özellik, Android'de kullanılabilir.

#### <a name="win32-app-information-available-in-troubleshooting-blade----2617342-----"></a>Win32 uygulama bilgileri sorun giderme dikey penceresinde kullanılabilir <!-- 2617342   -->
Intune uygulama hatası günlük dosyaları için bir Win32 uygulaması yüklemesi artık toplayabilir **sorun giderme** dikey penceresi. Uygulama yükleme sorunlarını giderme hakkında daha fazla bilgi için bkz. [uygulaması yükleme sorunlarını giderme](troubleshoot-app-install.md) ve [uygulama sorunlarını giderme Win32](apps-win32-app-management.md#troubleshoot-win32-app-issues).

#### <a name="app-status-details-for-ios-apps----3761235-----"></a>İOS uygulamaları için uygulama durumu ayrıntıları <!-- 3761235   -->
Yeni uygulama yükleme hata iletileri için aşağıdaki ilgili vardır:
- Paylaşılan iPad üzerinde yüklerken VPP uygulamaları için hata
- App Store'da devre dışı bırakıldığında hatası
- Uygulama için VPP lisans bulunamadı hatası
- MDM sağlayıcısıyla sistemi uygulamaları yükleme hatası
- Cihaz kayıp modu veya bilgi noktası modunda olduğunda, uygulama yükleme hatası
- Kullanıcı için App Store oturum açmamış, uygulama yükleme hatası

Intune'da seçin **istemci uygulamaları** > **uygulamaları** > "Uygulama adı" > **cihaz yükleme durumu**. Yeni hata iletileri de kullanılabilir olacak **durumu ayrıntıları** sütun.

#### <a name="new-app-categories-screen-in-the-company-portal-app-for-windows-10---3834780----"></a>Windows 10 için Şirket portalı uygulamasında yeni uygulama kategorileri ekran<!-- 3834780  -->
Adlı yeni bir ekran **uygulama kategorileri** Windows 10 için Şirket portalı uygulaması gezinme ve seçim deneyimini iyileştirmek üzere eklendi. Kullanıcılar artık kategoriler altında gibi sıralanan uygulamalarını görmek **öne çıkan**, **eğitim**, ve **üretkenlik**. Bu değişikliği Şirket portalı sürümleri 10.3.3451.0 görünür ve daha sonra. Yeni ekran görüntülemek için bkz: [uygulama kullanıcı Arabirimindeki yenilikler](https://docs.microsoft.com/intune/whats-new-app-ui). Şirket portalı'nda uygulama hakkında daha fazla bilgi için bkz. [yüklemek ve paylaşmak cihazınızdaki uygulamaların](/intune-user-help/install-apps-cpapp-windows).  

#### <a name="power-bi-compliance-app----1455231-doc-work-item---"></a>Power BI uyumluluk uygulaması <!-- 1455231 doc-work-item -->
Power BI çevrimiçi kullanarak Intune veri ambarı'nızı erişim [Intune uyumluluk (veri ambarı)](https://app.powerbi.com/groups/me/getapps/services/Intune_dw_compliance) uygulama. Bu Power BI uygulaması ile artık erişmek ve herhangi bir kurulum yapmadan ve web tarayıcınızı çıkmadan önceden oluşturulmuş raporları paylaşabilirsiniz. Ek bilgi için bkz: [değişiklik günlüğü - Power BI uyumluluğu uygulama](reports-changelog.md#power-bi-compliance-app).


### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="powershell-scripts-can-run-in-a-64-bit-host-on-64-bit-devices----1862675-----"></a>PowerShell betiklerini bir 64-bit ana bilgisayar, 64 bit cihazlarda çalıştırabilirsiniz <!-- 1862675   -->
Bir cihaz yapılandırma profili için bir PowerShell Betiği eklediğinizde, betik, 32-bit, 64-bit işletim sistemlerinde bile her zaman yürütür. Bu güncelleştirme ile bir yönetici komut dosyası bir 64 bit PowerShell ana bilgisayar 64 bit cihazlarda çalıştırabilirsiniz (**cihaz Yapılandırması** > **PowerShell betikleri**  >   **Ekleme** > **yapılandırma** > **64 bit PowerShell konağı betiği**).

PowerShell kullanma hakkında daha fazla ayrıntı için bkz. [ıntune'da PowerShell betiklerini](intune-management-extension.md).

Şunun için geçerlidir: Windows 10 ve üzeri

#### <a name="macos-users-are-prompted-to-update-their-password----1873216---"></a>macOS kullanıcılarını parolasını güncelleştirmesi istenir <!-- 1873216 -->
Intune zorlama **ChangeAtNextAuth** macOS cihazlarında ayarlama. Bu ayar, son kullanıcılar ve cihazlar uyumluluk parola ilkeleri veya cihaz kısıtlama parola profilleri etkiler. Son kullanıcılara parolalarını güncelleştirmek için bir kez istenir. Her bir kullanıcı için cihaz oturum açma gibi kimlik doğrulaması gerektiren bir görev ilk çalıştırıldığında bu istem oluşur. Kullanıcılar ayrıca herhangi bir şey yapmak isteyen Anahtarlık erişimi gibi yönetim ayrıcalıklarını gerektirdiğinde parolasını güncelleştirmesi istenecek. 

Yeni veya var olan bir parola ilke değişikliklerinin yönetici tarafından son kullanıcıların parolalarını yeniden güncelleştirmeyi ister.

Şunun için geçerlidir:  
Mac OS

#### <a name="assign-scep-certificates-to-a-userless-macos-device-----2340521----"></a>SCEP sertifikaları için bir Kullanıcısız macOS cihaz atama  <!-- 2340521  -->
Kullanıcı benzeşimi olmayan cihazlar da dahil olmak üzere, macOS cihazları için cihaz öznitelikleri kullanarak basit sertifika kayıt Protokolü (SCEP) sertifikaları atayın ve sertifika profilinin Wi-Fi veya VPN profilleri ile ilişkilendirin. Bu zaten sahibiz için desteği genişletir [SCEP sertifikaları ve kullanıcı benzeşimi olmadan cihazlara atama](certificates-scep-configure.md#create-a-scep-certificate-profile) Windows, iOS ve Android çalıştırın.  Bu güncelleştirme, bir sertifika türü seçme seçeneği ekler *cihaz* macOS için bir SCEP sertifika profili yapılandırırken.

Şunun için geçerlidir: 
- Mac OS

#### <a name="intune-conditional-access-ui-update------2432313-----"></a>Intune koşullu erişim kullanıcı arabirimini güncelleştirme   <!-- 2432313   -->
Intune konsolunda koşullu erişim için kullanıcı arabirimi geliştirmeleri yaptık. Bunlar:
-  Intune yerine *koşullu erişim* dikey penceresinden Azure Active Directory içeren dikey pencere. Bu erişim ayarları ve yapılandırmaları için tam aralığına sahip olacaksınız sağlar [koşullu erişim](conditional-access.md) (hangi kalacak bir Azure AD teknolojisi) içinde Intune konsolunda. 
- Biz yeniden adlandırdıktan *şirket içi erişim* dikey penceresine *Exchange erişimi*ve yeniden konumlandırılması *Exchange hizmeti Bağlayıcısı* kurulumunu yeniden adlandırılan bu dikey pencere.  Bu değişikliğin nerede birleştirir, [yapılandırmak ve izlemek için Exchange online ve şirket içi ilgili ayrıntıları](exchange-connector-install.md).  

#### <a name="kiosk-browser-and-microsoft-edge-browser-apps-can-run-on-windows-10-devices-in-kiosk-mode----2935135-----"></a>Bilgi noktası tarayıcı ve Microsoft Edge tarayıcı uygulamaları, bilgi noktası modu, Windows 10 cihazlarında çalıştırabilirsiniz <!-- 2935135   -->
Bir uygulama veya birçok uygulamalarını çalıştırmak için Windows 10 cihazları bilgi noktası modunda kullanabilirsiniz. Bu güncelleştirme, bilgi noktası modunda tarayıcı uygulamalarında kullanmanın bazı değişiklikler içerir. dahil olmak üzere:

- Microsoft Edge tarayıcı veya bilgi noktası cihazı uygulamaları çalıştırmak için bilgi noktası tarayıcı ekleyin (**cihaz Yapılandırması** > **profilleri** > **yeni profili**  >  **Windows 10 ve üzeri** Platform > **bilgi noktası** profil türü için).
- İzin vermek veya kısıtlamak yeni özellikler ve ayarlar kullanılabilir (**cihaz Yapılandırması** > **profilleri** > **yeni profili**  >  **Windows 10 ve üzeri** Platform > **cihaz kısıtlamaları** profil türü için) dahil:

  - Microsoft Edge tarayıcı:
  - Microsoft Edge bilgi noktası modunu kullan
  - Boşta kalma süresinden sonra tarayıcıyı yenileyin

 - Sık Kullanılanlar ve ara:
  - Arama motoru değişiklik izin ver

Bu ayarların listesi için bkz:

- [Windows 10 ve üzeri cihaz ayarları bir bilgi noktası çalıştırmak için](kiosk-settings-windows.md)
- [Microsoft Edge tarayıcı cihaz kısıtlamaları](device-restrictions-windows-10.md#microsoft-edge-browser)
- [Sık Kullanılanlar ve arama cihaz kısıtlamaları](device-restrictions-windows-10.md##favorites-and-search)

Şunun için geçerlidir: Windows 10 ve üzeri

#### <a name="new-device-restriction-settings-for-ios-and-macos-devices----3448774-----"></a>İOS ve macOS cihazları için yeni cihaz kısıtlama ayarları <!-- 3448774   -->
Bazı ayarları ve iOS ve macOS çalıştıran cihazlarda özellikleri kısıtlamak (**cihaz Yapılandırması** > **profilleri** > **yeni profili**  >  **iOS** veya **macOS** Platform > **cihaz kısıtlamaları** profil türü için). Bu güncelleştirme, daha fazla özellikleri ve ayarlarını denetleyebileceğiniz, ayar ekran süresi dahil olmak üzere, Esım ayarları ve cep telefonu planları ve daha fazla iOS cihazlarında değiştirme ekler. Ayrıca, yazılım güncelleştirmeleri ve macOS cihazlarda içeriği önbelleğe alma engelleme kullanıcının görünürlüğünü geciktirme. 

Erişimi, ayarları ve özellikleri görmek için bkz:

- [iOS cihaz kısıtlama ayarları](device-restrictions-ios.md)
- [macOS cihaz kısıtlama ayarları](device-restrictions-macos.md)

Şunun için geçerlidir:

- iOS
- Mac OS

#### <a name="kiosk-devices-are-now-called-dedicated-devices-on-android-enterprise-devices----3598402-----"></a>"Bilgi noktası" cihazları artık "Android kuruluş cihazlarının cihazları ayrılmış" olarak adlandırılır <!-- 3598402   -->
Android ifadeyle hizalamak için **bilgi noktası** değiştirilir **adanmış cihazlar** Android Kurumsal cihazlarda (**cihaz Yapılandırması**  >  **Profilleri** > **profili oluşturma** > ** Android Kurumsal Platform > **yalnızca cihaz sahibi** > **cihaz Kısıtlamaları** > **adanmış cihazlar**).

Kullanılabilir ayarlar görmek için Git [izin vermek veya özellikleri kısıtlamak için cihaz ayarları](device-restrictions-android-for-work.md#dedicated-device-settings).

Şunun için geçerlidir:  
Android Kurumsal

#### <a name="safari-and-delaying-user-software-update-visibility-ios-settings-are-moving-in-the-intune-ui----3640850-3803313-----"></a>Görünürlük iOS ayarları Intune kullanıcı Arabiriminde taşıyor Safari ve geciktirme kullanıcı yazılım güncelleştirme <!-- 3640850, 3803313   -->
İOS cihazları için Safari ayarlarını ve yazılım güncelleştirmelerini yapılandırma. Bu güncelleştirmede, bu ayarlar, Intune kullanıcı arabiriminin farklı bölümlerine taşınıyor:

- Taşıma kaynağı Safari ayarları **Safari** (**cihaz Yapılandırması** > **profilleri** > **yeni profili**  >  **iOS** Platform > **cihaz kısıtlamaları** profil türü için) için  **[yerleşik uygulamaları](device-restrictions-ios.md#built-in-apps)**.
- **Denetimli iOS cihazları için kullanıcı yazılım güncelleştirme görünürlüğü geciktirme** ayarı (**yazılım güncelleştirmelerini** > **güncelleştirme ilkelerini iOS için**) içintaşıma **Cihaz kısıtlamaları** > **[genel](device-restrictions-ios.md#general)**.  Mevcut ilkeleri etkisi hakkında daha fazla bilgi için bkz: [iOS yazılım güncelleştirmeleri](software-updates-ios.md#configure-the-policy). 

Ayarlar listesi için bkz:

- [iOS cihaz kısıtlamaları](device-restrictions-ios.md) 
- [iOS yazılım güncelleştirmeleri](software-updates-ios.md)

Bu özellik şu platformlarda geçerlidir: 

- iOS

#### <a name="enabling-restrictions-in-the-device-settings-is-renamed-to-screen-time-on-ios-devices----3699164-----"></a>Cihaz ayarlarında kısıtlamaları etkinleştirme ekran süresini iOS cihazlarında yeniden adlandırılır <!-- 3699164   -->
Yapılandırabileceğiniz **cihaz ayarlarında kısıtlamaları etkinleştirme** üzerinde iOS cihazlarının denetimli (**cihaz Yapılandırması** > **profilleri**  >  **Yeni profili** > **iOS** Platform > **cihaz kısıtlamaları** profil türü için > **genel**). Bu güncelleştirmede, bu ayarı olarak yeniden adlandırıldı **ekran (yalnızca denetimli) zaman**. 

Aynı durum geçerlidir. Özellikle: 

- iOS 11.4.1 ve önceki sürümleri: **Blok** son kullanıcıların cihaz ayarlarında kısıtlamaları kendi ayarından engeller. 
- iOS 12.0 ve daha sonra: **Blok** son kullanıcılar kendi önlenmiş **ekran zaman** cihaz ayarlarında, içerik ve gizlilik kısıtlamaları da dahil olmak üzere. İOS 12.0 yükseltilmiş cihazları, cihaz ayarlarında kısıtlamaları sekmesinde artık görmezsiniz. Bu ayarlar **ekran zaman**. 

Ayarlar listesi için bkz. [iOS cihaz kısıtlamaları](device-restrictions-ios.md#general).

Şunun için geçerlidir: 
- iOS


### <a name="device-management"></a>Cihaz yönetimi

#### <a name="rename-an-enrolled-windows-device----1911112----"></a>Kayıtlı Windows cihazı yeniden adlandır <!-- 1911112  -->
Kayıtlı Windows 10 cihazı artık yeniden adlandırabilirsiniz (RS4 veya üzeri). Yapmak için **Intune** > **cihazları** > **tüm cihazlar** > bir cihaz seçin > **yeniden adlandırma cihaz**. Bu özellik, yeniden adlandırma karma Azure AD Windows cihazları şu anda desteklemiyor.

#### <a name="auto-assign-scope-tags-to-resources-created-by-an-admin-with-that-scope----3173823----"></a>Kapsam etiketleri, kapsamlı bir yönetici tarafından oluşturulan kaynakları için otomatik olarak ata <!-- 3173823  -->
Yönetici kaynak oluşturduğunda, bu yeni kaynaklara Yönetim için atanan bir kapsam etiketleri otomatik olarak atanır.

### <a name="monitor-and-troubleshoot"></a>İzleme ve sorun giderme

#### <a name="failed-enrollment-report-moves-to-the-device-enrollment-blade----3560202----"></a>Cihaz kaydı dikey penceresine başarısız kayıt rapor taşır <!-- 3560202  -->
**Başarısız kayıtları** rapor taşındı **İzleyici** bölümünü **cihaz kaydı** dikey penceresi. (Kayıt yöntemi ve işletim sistemi sürümü) iki yeni sütunlar ekledik.

#### <a name="company-portal-abandonment-report-renamed-to-incomplete-user-enrollments---3815076-eemiss---"></a>Şirket portalı abandonment raporu için eksik kullanıcı kayıtları olarak yeniden adlandırıldı <!--3815076 eemiss -->
**Şirket portalı abandonment** rapor adlandırıldı **eksik kullanıcı kayıtları**.


<!-- ########################## -->
## <a name="week-of-february-4-2019"></a>4 Şubat 2019 haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="intune-macos-company-portal-dark-mode----3300524----"></a>Intune macOS Şirket portalı koyu modu <!-- 3300524  -->
Intune macOS Şirket portalı, macOS için artık koyu modunu destekler. Bir macOS 10.14 + cihazda koyu modunu etkinleştirdiğinizde, Şirket portalı görünümünü mod yansıtan renkleri için ayarlanır.

<!-- ########################## -->
## <a name="week-of-january-21-2019"></a>21 Ocak 2019 haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="toast-notifications-for-win32-apps----3136566-----"></a>Win32 uygulamaları için kutlama bildirimleri <!-- 3136566   -->
Uygulama ataması başına gösteren son kullanıcı bildirimleri gösterilmemesini sağlayabilirsiniz. Intune'dan seçin **istemci uygulamaları** > **uygulamaları** > uygulamayı seçin > **atamaları** > **grupları dahil**. 

#### <a name="intune-app-protection-policies-ui-update----3251427----"></a>Intune uygulama koruma ilkeleri UI güncelleştirmesi <!-- 3251427  -->
Özelliğin ayarları için etiketleri ve anlamak her kolaylaştırmak Intune uygulama koruması için düğmeler değiştirdik. Değişikliklerden bazıları şunlardır:  
- Denetimleri değiştirildi **Evet** / **hiçbir** için öncelikle denetimleri **blok** / **izin** ve **devre dışı** / **etkinleştirme** kontrol eder. Etiketler de güncelleştirilir.  
- Ayarları biçimlendirilir, yan yana ayarı ve etiketini olacak şekilde daha iyi Gezinti sağlamak için denetimi.   

Varsayılan ayarlar ve ayar aynı kalır, ancak bu değişiklik anlamak, kodlarda gezinin ve seçili uygulama koruma ilkeleri kolayca uygulamak için daha fazla ayarları kullanmasına izin verir. Bilgi için [iOS ayarları](app-protection-policy-settings-ios.md) ve [Android ayarları](app-protection-policy-settings-android.md).

### <a name="additional-settings-for-outlook----3301182----"></a>Outlook için ek ayarlar <!-- 3301182  -->
Artık iOS için Outlook ve Intune kullanarak Android için aşağıdaki ek ayarlar da yapılandırabilirsiniz:

- Yalnızca iOS ve Android Outlook'ta kullanılacak iş veya Okul hesaplarını izin ver
- Office 365 modern kimlik doğrulamayı dağıtmak ve hibrit modern kimlik doğrulaması şirket hesapları
- Kullanım `SAMAccountName` username alan temel kimlik doğrulaması seçildiğinde e-posta profili için
- Kaydedilecek kişiler izin ver
- Dış alıcılara posta ipuçları yapılandırın
- Yapılandırma **odaklanmış gelen kutusu**
- İOS için Outlook erişmeye Biyometri gerektirir
- Bloğu dış görüntüleri

> [!NOTE]
> Erişim için Kurumsal kimlikleri yönetmek için Intune uygulama koruma ilkeleri kullanıyorsanız değil etkinleştirmeyi düşünebilirsiniz **Biyometri gerektiren**. Daha fazla bilgi için **erişim için Kurumsal kimlik bilgilerini gerektir** için [iOS erişim ayarlarını](app-protection-policy-settings-ios.md#access-requirements) ve [Android erişim ayarları](app-protection-policy-settings-android.md#access-requirements).

Daha fazla bilgi için [Microsoft Outlook yapılandırma ayarlarını](app-configuration-policies-outlook.md).

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

#### <a name="check-for-configuration-manager-compliance----2192052--eepublished----"></a>Configuration Manager uyumluluğu denetle <!-- 2192052  eepublished  -->
Bu güncelleştirme, yeni bir System Center Configuration Manager Uyumluluk ayarı içerir (**cihaz uyumluluğu** > **ilkeleri** > **İlkesioluşturma**  >  **Windows 10 ve üzeri** > **Configuration Manager Uyumluluk**). Configuration Manager, Intune uyumluluğuna sinyal gönderir. Bu ayarı kullanarak, "uyumlu" döndürülecek tüm Configuration Manager sinyaller gerektirebilir.

Örneğin, tüm yazılım güncelleştirmelerinin cihazlarda yüklü olmasını gerektirirsiniz. Configuration Manager’da bu gereksinim, “Yüklü” durumundadır. Cihazdaki tüm programları bilinmeyen bir durumda, cihazı Intune'da uyumlu olmadığını.

[Configuration Manager Uyumluluk](compliance-policy-create-windows.md#configuration-manager-compliance) Bu ayar açıklar.

Şunun için geçerlidir: Windows 10 ve üzeri

#### <a name="customize-wallpaper-on-supervised-ios-devices-using-a-device-configuration-profile----2809324-----"></a>Duvar kağıdı denetimli iOS cihazlarında cihaz yapılandırma profili kullanarak özelleştirme <!-- 2809324   -->
İOS cihazları için cihaz yapılandırma profili oluşturduğunuzda, bazı özellikler özelleştirebilirsiniz (**cihaz Yapılandırması** > **profilleri** > **oluştur profili** > **iOS** Platform > **cihaz özellikleri** profil türü için). Bu güncelleştirme yeni eklemeler **duvar kağıdı** giriş ekranına veya kilit ekranında bir .png, .jpg veya .jpeg görüntüsü kullanmak yönetici izin ayarları. Bu duvar kağıdı ayarları yalnızca denetimli cihazlar için geçerlidir. 

Bu ayarların listesi için bkz. [iOS cihaz özelliği ayarlarını](ios-device-features-settings.md).

#### <a name="windows-10-kiosk-is-generally-available----3594661----"></a>Windows 10 bilgi noktası kullanıma sunuldu <!-- 3594661  -->
Bu güncelleştirme, Windows 10 ve üzeri cihazlarda bilgi noktası özelliği genel kullanıma (GA) ' dir. Ekleme ve yapılandırma tüm ayarları görmek için bkz: [bilgi noktası ayarları (Windows 10 ve üzeri)](kiosk-settings.md).

#### <a name="contact-sharing-via-bluetooth-is-removed-in-device-restrictions--device-owner-for-android-enterprise----3598396-----"></a>Bluetooth ile kişi paylaşımı cihaz kısıtlamaları kaldırılmış > Android Kurumsal cihaz sahibi <!-- 3598396   -->
Kurumsal Android cihazlar için cihaz kısıtlama profili oluşturduğunuzda, var olan bir **Bluetooth aracılığıyla kişi paylaşımı** ayarı. Bu güncelleştirmede, **Bluetooth aracılığıyla kişi paylaşımı** ayarı kaldırıldı (**cihaz Yapılandırması** > **profilleri**  >   **Profil oluşturma** > **Android Kurumsal** Platform > **cihaz kısıtlamaları > cihaz sahibi** profil türü için > **genel** ). 

**Bluetooth aracılığıyla kişi paylaşımı** ayarı Android Kurumsal cihaz sahibi yönetimi için desteklenmez. Bu ayar kaldırıldığında, bu ayar etkinleştirildikten ve yapılandırıldıktan sonra ortamınızda olsa bile bu nedenle, herhangi bir cihaz veya kiracıları, etkilemez.

Geçerli ayarları listesini görmek için Git [izin vermek veya özellikleri kısıtlamak için Android Kurumsal cihaz ayarları](device-restrictions-android-for-work.md).

Şunun için geçerlidir: Android Kurumsal cihaz sahibi

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

<!-- ########################## -->
## <a name="week-of-january-14-2019"></a>14 Ocak 2019 haftası

### <a name="preview-of-support-for-android-corporate-owned-fully-managed-devices----1574342----"></a>Şirkete ait ve tamamen yönetilen Android cihazları için destek önizlemesi <!-- 1574342  -->
Tam olarak yönetilen Android cihazlar, bir kuruluşa ait destekler artık Intune yeri sıkı bir şekilde tarafından yönetilen cihazları "cihaz sahibi" senaryo BT ve tek tek kullanıcılarla bağlı. Bu durum, yöneticilerin tüm cihazı yönetebilir, ilke denetimlerini iş profilleri kullanılamaz genişletilmiş bir aralığını zorla olanak sağlar ve kullanıcıları, yalnızca yönetilen Google Play uygulamaları yüklemek için sınırlar. Daha fazla bilgi için [Intune'u ayarlama Android kayıt tam olarak yönetilen cihazlar](android-fully-managed-enroll.md) ve [adanmış cihazlar veya tam olarak yönetilen cihazları kaydetme](android-dedicated-devices-fully-managed-enroll.md).  Bu özelliğin önizlemede olduğunu lütfen unutmayın. Sertifikalar, uyumluluk ve koşullu erişim gibi bazı Intune özellikleri ile şu anda kullanılabilir olmayan Android tam olarak yönetilen kullanıcı cihazları.

<!-- ########################## -->
## <a name="week-of-january-7-2019"></a>7 Ocak 2019 haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="intune-app-pin----2298397---"></a>Intune uygulama PIN'i <!-- 2298397 -->
BT yöneticisi olarak, bir son kullanıcının PIN kodunun değiştirilmesi gerekmeden, Intune uygulama kadar bekleyebilirsiniz gün sayısını yapılandırabilirsiniz. Yeni ayar *PIN sıfırlamayı kaç gün sonra* ve seçerek Azure Portalı'nda kullanılabilir **Intune** > **istemci uygulamaları**  >   **Uygulama koruma ilkeleri** > **ilke Oluştur** > **ayarları** > **erişim gereksinimlerini**. Kullanılabilir [iOS](app-protection-policy-settings-ios.md) ve [Android](app-protection-policy-settings-android.md) cihazları, bu özellik, artı bir tamsayı değeri destekler.


#### <a name="intune-device-reporting-fields----2748738---"></a>Intune cihaz alanları raporlama <!-- 2748738 -->
Intune, ek cihaz alanları, uygulama kayıt kimliği, Android üreticisi, modeli ve güvenlik düzeltme eki sürümü yanı sıra iOS model dahil olmak üzere raporlama sağlar. Intune, bu alanlar seçerek kullanılabilir **istemci uygulamaları** > **uygulama koruma durumu** seçip **uygulama koruma raporu: iOS, Android**. Bu parametreleri yapılandırma Ayrıca, yardımcı olacak **izin ver** cihaz üreticisi (Android) için liste **izin** cihaz modeli (Android ve iOS) ve en düşük Android güvenlik düzeltme eki için listesi Sürüm ayarı. 


### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="administrative-templates-are-in-public-preview-and-moved-to-their-own-configuration-profile----3322847---"></a>Yönetim Şablonları genel Önizleme aşamasındadır ve kendi yapılandırma profiline taşınır <!-- 3322847 -->

Intune Yönetim Şablonları (**cihaz Yapılandırması** > **Yönetim Şablonları**) şu anda genel Önizleme aşamasındadır. Bu güncelleştirme ile:

- Yönetim Şablonları, Intune'da yönetilebilir 300 ayarları içerir. Daha önce bu ayarlar, yalnızca Grup İlkesi Düzenleyicisi'nde vardı.
- Yönetim Şablonları genel önizlemede kullanılabilir.
- Yönetim Şablonları hareket etmesini **cihaz Yapılandırması** > **Yönetim Şablonları** için **cihaz Yapılandırması**  >   **Profilleri** > **profili oluşturma** > içinde **Platform**, seçin **Windows 10 ve üzeri** > içinde **profili tür**, seçin **Yönetim Şablonları**.
- Raporlama etkindir

Daha fazla bilgi için bu özellik hakkında Git [Grup İlkesi ayarlarını yapılandırmak için Windows 10 şablonları](administrative-templates-windows.md).

Şunun için geçerlidir: Windows 10 ve üzeri

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
Şunun için geçerlidir: Windows 10 ve üzeri, Windows Holographic for Business

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

- Gösteren gelen çağrıları, sistem uyarıları, sistem hataları ve daha fazlası dahil olmak üzere, sistem bildirimleri devre dışı bırakın.
- Başlangıç öğreticileri ve ilk kez açan uygulamalar için ipuçları Atla önerir.
- Gelişmiş Tuş korumasını kamera, bildirimler, parmak izi gibi ayarları kilidini açmak ve daha fazlası devre dışı bırakın.


Ayarları görmek için Git [Android Kurumsal cihaz kısıtlama ayarları](device-restrictions-android-for-work.md).

#### <a name="android-enterprise-device-owner-devices-can-use-always-on-vpn-connections----3202194---"></a>Android Kurumsal cihaz sahibi cihazlar her zaman açık VPN bağlantıları kullanabilirsiniz. <!-- 3202194 -->
Bu güncelleştirmede Android Kurumsal cihaz sahibi cihazlarda her zaman açık VPN bağlantıları kullanabilirsiniz. Her zaman açık VPN bağlantıları; kullanıcı cihazının kilidini açtığında, cihaz yeniden başlatıldığında veya kablosuz ağ değiştiğinde bağlı kalır veya hemen tekrar bağlanır. Bağlantıyı “kilitli”moduna da alabilirsiniz, böylece VPN bağlantısı etkin olana kadar tüm ağ trafiği engellenir.
Her zaman açık VPN etkinleştirebilirsiniz **cihaz Yapılandırması** > **profilleri** > **profili oluşturma**  >   **Android Kurumsal** Platform > **cihaz kısıtlamaları** yalnızca cihaz sahibi > **bağlantı** ayarları. Ayarları görmek için Git [Android Kurumsal cihaz kısıtlama ayarları](device-restrictions-android-for-work.md).

#### <a name="new-setting-to-end-processes-in-task-manager-on-windows-10-devices----3285177---"></a>Yeni Windows 10 cihazlarında Görev Yöneticisi'nde son işlemler için ayarlama <!-- 3285177 --> 
Bu güncelleştirme, Windows 10 cihazlarda Görev Yöneticisi'ni kullanarak işlemleri sonlandırmak için yeni bir ayar içerir. Bir cihaz yapılandırma profili kullanarak (**cihaz Yapılandırması** > **profilleri** > **profili oluşturma** > içinde **platformu** , seçin **Windows 10** > içinde **profil türü**, seçin **cihaz kısıtlamaları** > **genel** ayarları), izin verme veya engelleme bu ayarı seçin.
Bu ayarları görmek için Git [Windows 10 cihaz kısıtlama ayarları](device-restrictions-windows-10.md).
Şunun için geçerlidir: Windows 10 ve üzeri


### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="more-detailed-enrollment-restriction-failure-messaging----3111564---"></a>Daha ayrıntılı kayıt kısıtlama hata iletileri <!-- 3111564 -->
Daha ayrıntılı hata iletileri, kayıt kısıtlamaları karşılanmadı seçtiğinizde kullanılabilir. Bu iletileri görmek için Git **Intune** > **sorun giderme** > ve kayıt hataları tabloyu gözden geçirin. Daha fazla bilgi için [kayıt hatalarının listesi](help-desk-operators.md#enrollment-failure-reference).

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
Rolleri ve uygulamalar için erişimi sınırlandırmak için kapsamı etiketleri oluşturabilirsiniz. Böylece kişiler de bu kapsam etiketi atanan rollerle yalnızca uygulama erişimi için bir uygulama bir kapsam etiketi ekleyebilirsiniz. Şu anda, yönetilen Google Play veya Apple Volume Purchase Program (VPP) kullanarak satın aldığınız uygulamaları Intune'a eklenen uygulamaları kapsam etiketleri atama yapılamaz (ancak desteği gelecekte gelir). Daha fazla bilgi için [kapsam etiketleri filtresi ilkeleri kullanan](scope-tags.md).

<!-- ########################## -->
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

<!-- ########################## -->
## <a name="week-of-november-26-2018"></a>26 Kasım 2018 haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="uninstalling-apps-on-corporate-owned-supervised-ios-devices----1281677---"></a>Denetimli iOS şirkete ait cihazlara uygulamaları kaldırma <!-- 1281677 -->

Şirkete denetimli iOS cihazlarında herhangi bir uygulamayı kaldırabilirsiniz. **Kaldırma** atama türüyle kullanıcı veya cihaz gruplarını hedefleyerek herhangi bir uygulamayı kaldırabilirsiniz. Kişisel veya denetimsiz iOS cihazlarında yalnızca Intune kullanarak yüklenen uygulamaları kaldırabilirsiniz.

#### <a name="downloading-intune-win32-app-content----2617320---"></a>Intune Win32 uygulama içeriği indiriliyor <!-- 2617320 -->
Windows 10 RS3 ve üzerindeki istemciler Windows 10 istemci üzerinde bir teslim iyileştirme bileşenini kullanarak Intune Win32 uygulama içeriği karşıdan yükler. Teslim iyileştirme, varsayılan olarak açık eşler arası işlevsellik sağlar. Dağıtım iyileştirme Grup İlkesi ve gelecek Intune MDM aracılığıyla yapılandırılabilir Daha fazla bilgi için [Windows 10 için teslim iyileştirme](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization). 

#### <a name="end-user-device-and-app-content-menu----2771453---"></a>Son kullanıcının cihaz ve uygulama içerik menüsü <!-- 2771453 -->
Son kullanıcılar artık bağlam menüsü üzerinde cihaz ve uygulamaları bir cihazı yeniden adlandırma ya da uyumluluk denetimi gibi yaygın eylemleri tetiklemek için kullanabilirsiniz.

#### <a name="set-custom-background-in-managed-home-screen-app-----3041945---"></a>Giriş ekranı yönetilen uygulamada özel bir arka plan ayarlayın  <!-- 3041945 -->
Arka plan Android kuruluş, birden çok uygulamalı bilgi noktası modu cihazlarına giriş ekranı yönetilen uygulamayı özelleştirme olanak sağlayan bir ayar ekliyoruz.  **Özel URL arka planı**’nı yapılandırmak için Azure portalı > Cihaz yapılandırması’ndaki Intune’a gidin. Geçerli cihaz yapılandırma profilini seçin veya bilgi noktası ayarlarını yapılandırmak için yeni profil oluşturun.
Bilgi noktası ayarları görmek için bkz: [Android Kurumsal cihaz kısıtlamaları](device-restrictions-android-for-work.md).

#### <a name="app-protection-policy-assignment-save-and-apply----3104570---"></a>Uygulama koruma İlkesi ataması kaydetme ve uygulama <!-- 3104570 -->
Artık daha iyi üzerinde denetiminiz, [uygulama koruma ilke atamalarını](app-protection-policies.md#deploy-a-policy-to-users). Seçtiğinizde, *atamaları* ayarlamak veya bir ilke atamalarını düzenlemek için **Kaydet** değişikliği uygulamadan önce yapılandırma. Kullanım **at** tüm değişiklikleri temizlemek için dahil etme için değişiklikleri kaydetmeden yaptığınız veya dışlama listeler.  Gerektiren kaydetme veya atma tarafından bir uygulama koruma ilkesi yalnızca düşündüğünüz kullanıcılara atanır.

#### <a name="new-microsoft-edge-browser-settings-for-windows-10-and-later----3174639---"></a>Yeni Windows 10 ve üzeri için Microsoft Edge tarayıcı ayarları <!-- 3174639 -->
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

#### <a name="select-apps-tracked-on-the-enrollment-status-page---2531007---"></a>Kayıt durumu sayfasında izlenen select uygulamaları<!-- 2531007 -->
Hangi uygulamaların kayıt durumu sayfasında izlenen seçebilirsiniz. Bu uygulamalar yüklenene kadar kullanıcı cihazı kullanamaz. Daha fazla bilgi için [ayarlama bir kayıt durumu sayfası](windows-enrollment-status.md).

#### <a name="search-for-autopilot-device-by-serial-number---2595788---"></a>Autopilot cihaz seri numarasına göre ara <!--2595788 -->
Artık, Autopilot cihazları seri numarasına göre arayabilirsiniz. Bunu yapmak için **cihaz kaydı** > **Windows kayıt** > **cihazları** > bir seri numarası yazın **göre ara seri numarası** kutusu > Enter tuşuna basın.

#### <a name="track-installation-of-office-proplus---2620217---"></a>Office ProPlus yüklenmesini izleyin <!--2620217 -->
Kullanıcılar, yükleme işleminin ilerlemesini izleyebilirsiniz [Office ProPlus](apps-add-office365.md) kullanarak [kayıt durumu sayfası](windows-enrollment-status.md). Daha fazla bilgi için [ayarlama bir kayıt durumu sayfası](windows-enrollment-status.md).

#### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low----2237572---"></a>Süresi dolan VPP belirteci veya Şirket portalı için uyarıları çalışan düşük lisans <!-- 2237572 -->
Intune Şirket portalı DEP kaydı sırasında önceden sağlamak için Volume Purchase Program (VPP) kullanıyorsanız, VPP belirtecinin süresi dolmak üzere olduğunda ve Şirket portalı için lisans azalıyor uyaracaktır.

### <a name="macos-device-enrollment-program-support-for-apple-school-manager-accounts---3006133---"></a>macOS aygıt kayıt programı, Apple School Manager hesabı için destek <!--3006133 -->
Intune macOS cihazları için Apple School Manager hesabı cihaz kayıt programı kullanarak destekler.  Daha fazla bilgi için [Apple School Manager ile macOS cihazlara veya cihaz kayıt programı otomatik olarak kaydetme](device-enrollment-program-enroll-macos.md).

### <a name="new-intune-device-subscription-sku---3312071--"></a>Yeni Intune cihaz Aboneliği SKU <!--3312071-->
Kuruluşlarda cihaz yönetim maliyetini düşürmeye yardımcı olmak için yeni, cihaz tabanlı bir abonelik SKU’su kullanıma sunulmuştur. Bu Intune cihaz SKU’su cihaz başına aylık olarak lisanslandırılır. Fiyat ise lisanslama programına göre değişir. Microsoft 365 Yönetim Merkezi aracılığıyla doğrudan ve aracılığıyla kullanılabilir [Kurumsal Anlaşma](https://www.microsoft.com/licensing/licensing-programs/enterprise?activetab=enterprise-tab:primaryr2) (EA) [Microsoft Products and Services sözleşmesi](https://www.microsoft.com/licensing/mpsa/default) (MPSA) [Microsoft Open Anlaşmaları](https://partner.microsoft.com/licensing/licensing-agreements), ve [bulut çözümü sağlayıcısı](https://www.microsoftpartnercommunity.com/t5/Partnership-101/What-is-the-Cloud-Solution-Provider-CSP-program/td-p/2453) (CSP).

### <a name="device-management"></a>Cihaz yönetimi

#### <a name="temporarily-pause-kiosk-mode-on-android-devices-to-make-changes----3041935---"></a>Geçici olarak değişiklikler yapmak için Android cihazlarda bilgi noktası modu Duraklat <!-- 3041935 -->
Android cihazlarını çok uygulamalı bilgi noktası modunda kullanırken bir BT uzmanının cihazda değişiklikler yapması gerekebilir. Bu güncelleştirme, geçici olarak bilgi noktası modu bir PIN kullanarak duraklatmak ve cihazın tamamını erişmek bir BT yöneticisi izin veren yeni çoklu uygulama bilgi noktası ayarları içerir.
Bilgi noktası ayarları görmek için bkz: [Android Kurumsal cihaz kısıtlamaları](device-restrictions-android-for-work.md).

#### <a name="enable-virtual-home-button-on-android-enterprise-kiosk-devices-----3042021---"></a>Android kurumsal bilgi noktası cihazları üzerinde sanal giriş düğmesini etkinleştir  <!-- 3042021 -->
Yeni bir ayar, kullanıcıların Yönetilen Giriş Ekranı uygulaması ve çok uygulamalı bilgi noktası cihazlarındaki diğer atanan uygulamalar arasında bir yazılım tuşuna dokunarak geçiş yapmalarını sağlar. Bu ayar, özellikle kullanıcının bilgi noktası uygulaması “geri” düğmesine uygun şekilde yanıt vermediği durumlarda yararlı olur. Bu ayarı şirkete ait, tek kullanımlı Android cihazlarında yapılandırabilirsiniz. **Sanal giriş düğmesi**’ni etkinleştirmek veya devre dışı bırakmak için Azure portalı > Cihaz yapılandırması’ndaki Intune’a gidin. Geçerli cihaz yapılandırma profilini seçin veya bilgi noktası ayarlarını yapılandırmak için yeni profil oluşturun.
Bilgi noktası ayarları görmek için bkz: [Android Kurumsal cihaz kısıtlamaları](device-restrictions-android-for-work.md).

<!-- ########################## -->
## <a name="week-of-november-12-2018"></a>12 Kasım 2018 haftası

### <a name="network-access-control-nac-support-for-citrix-sso-for-ios----3259404---"></a>İOS için Citrix SSO için erişim denetimi (NAC) desteği ağ <!-- 3259404 -->

Citrix Citrix Citrix SSO için ağ erişim denetimi (NAC) ıntune iOS izin vermek için ağ geçidi için bir güncelleştirme yayımladı. Intune'da bir cihaz kimliği bir VPN profili içinde dahil kabul etmek ve ardından bu profili iOS cihazlarınıza gönderin. Citrix bu işlevselliği kullanmak için ağ geçidi için en son güncelleştirmesini yüklemeniz gerekir.

[İOS cihazlarında VPN ayarlarını yapılandırma](vpn-settings-ios.md#base-vpn-settings) NAC, bazı ek gereksinimleri de dahil olmak üzere kullanma hakkında daha fazla bilgi sağlar. 

<!-- ########################## -->
## <a name="week-of-november-5-2018"></a>5 Kasım 2018 Haftası

### <a name="support-for-ios-12-oauth-in-ios-email-profiles---2155106---"></a>İOS için 12 OAuth iOS e-posta profillerini destekler. <!--2155106 -->

Intune’un iOS e-posta profilleri, iOS 12 Open Authorization (OAuth) standardını destekliyor. Bu özelliği görmek için yeni bir profil oluşturun (platform olarak **Cihaz Yapılandırması** > **Profiller** > **Profil oluştur** > **iOS** > platform için > **E-posta** profil türü için) veya mevcut bir iOS e-posta profilini güncelleştirin. Kullanıcılara dağıtılmış olan bir profilde OAuth etkinleştirirseniz, kullanıcılardan tekrar kimlik doğrulaması yapmaları ve e-postalarını tekrar indirmeleri istenir.

[iOS e-posta profilleri](email-settings-ios.md) makalesinde bir e-posta profilinde OAuth kullanma hakkında daha fazla bilgi vardır.

### <a name="autopilot-support-for-hybrid-azure-active-directory-joined-devices-preview----1048100--"></a>AutoPilot katılan cihazlar (Önizleme) Azure Active Directory karma için destek <!-- 1048100-->
Artık karma Azure Active Directory’ye katılmış olan cihazları Autopilot kullanarak ayarlayabilirsiniz. Hibrit Autopilot özelliğini kullanmak için cihazların kuruluşunuzun ağına katılmış olması gerekir. Daha fazla bilgi için bkz. [Karma Azure Active Directory’ye katılmış olan cihazları Intune ve Windows Autopilot kullanarak dağıtma](windows-autopilot-hybrid.md).
Bu özellik, kullanıcı tabanının kullanımına gelecek birkaç gün içinde sunulacaktır. Bu nedenle, bu özellik hesabınız için kullanılabilir olana kadar bu adımları uygulayamayabilirsiniz.

<!-- ########################## -->
## <a name="week-of-october-29-2018"></a>29 Ekim 2018 haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="require-non-biometric-pin-after-a-specified-timeout----1506985---"></a>Belirtilen bir zaman aşımından sonra biyometrik olmayan PIN gerektir <!-- 1506985 -->
Intune, yöneticinin belirttiği zaman aşımından sonra biyometrik olmayan bir PIN gerektirir, böylece şirket verilerine erişim için biyometrik tanımlama kullanımını kısıtlama yoluyla Mobil Uygulama Yönetimi’nin (MAM) etkinleştirildiği uygulamalarda gelişmiş güvenlik sağlar. Bu ayar, APP/MAM etkin uygulamalara erişmek için Touch ID (iOS), Face ID (iOS), Android Biometric, veya geleceğin diğer kimlik doğrulama yöntemlerinden yararlanan kullanıcıları etkiler. Bu ayarlar, birden çok parmak izine veya başka biyometrik erişim yöntemlerine sahip bir cihazın şirket verilerini yanlış kullanıcıya gösterebildiği durumları ortadan kaldırarak, Intune yöneticilerinin kullanıcı erişimi üzerinde daha ayrıntılı denetim sahibi olmasına olanak tanır. Azure portalında **Microsoft Intune**'u açın. **İstemci uygulamaları** > **Uygulama koruma ilkeleri** > **İlke ekle** > **Ayarlar**’ı seçin. Belirli ayarlar için **Erişim** bölümünü bulun. Erişim ayarları hakkında daha fazla bilgi için bkz. [iOS ayarları](app-protection-policy-settings-ios.md#access-requirements) ve [Android ayarları](app-protection-policy-settings-android.md#access-requirements).

#### <a name="intune-app-data-transfer-settings-on-ios-mdm-enrolled-devices----2244713---"></a>Intune uygulama veri aktarımı ayarları iOS MDM kayıtlı cihazlar <!-- 2244713 -->
iOS MDM kayıtlı cihazlarda Intune APP veri aktarımı ayarlarının denetimini, kayıtlı kullanıcının kimliğini (Kullanıcı Asıl Adı (UPN) olarak da bilinir) belirtme işleminden ayrı tutabilirsiniz. IntuneMAMUPN kullanmayan yöneticiler, davranış değişikliği gözlemlemeyecektir. Bu işlev kullanılabilir olduğunda, kayıtlı cihazlarda veri aktarımı davranışını denetlemek için IntuneMAMUPN kullanan yöneticiler yeni ayarları gözden geçirmeli ve APP ayarlarını gerektiği gibi güncelleştirmelidir.

#### <a name="windows-10-win32-apps----2617325---"></a>Windows 10 Win32 uygulamaları <!-- 2617325 -->
Win32 uygulamalarınızı cihazdaki tüm kullanıcılar için yüklemek yerine kullanıcı bağlamında ayrı ayrı kullanıcılar için yüklenecek şekilde yapılandırabilirsiniz.

#### <a name="windows-win32-apps-and-powershell-scripts----2617330---"></a>Win32 Windows uygulamaları ve PowerShell betikleri <!-- 2617330 -->
Artık son kullanıcıların Win32 uygulamalarını yüklemek veya PowerShell betiklerini yürütmek için cihazda oturum açmış olmaları gerekmez. 

#### <a name="troubleshooting-client-app-installation----1363711---"></a>İstemci uygulama yükleme sorunlarını giderme <!-- 1363711 -->
**Sorun giderme** dikey penceresinde **Uygulama yükleme** etiketli sütunu gözden geçirerek istemci uygulamaların yüklenmesiyle ilgili sorunları giderebilirsiniz. **Sorun giderme** dikey penceresini görüntülemek için Intune portalındaki **Yardım ve destek** bölümünün altından **Sorun giderme**’yi seçin.

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="network-access-control-support-on-ios-vpn-clients----1333693---"></a>İOS VPN istemcilerde ağ erişim denetimi desteği <!-- 1333693 -->
Bu güncelleştirmeyle, iOS için Cisco AnyConnect, F5 Access ve Citrix SSO’ya yönelik bir VPN yapılandırma profili oluştururken Ağ Erişim Denetimini (NAC) etkinleştirmek için kullanabileceğiniz yeni bir ayar kullanıma sunuldu. Bu ayar, cihazın NAC kimliğinin VPN profiline dahil edilmesini sağlar. Şu anda bu yeni NAC kimliğini destekleyen bir VPN istemcisi veya NAC iş ortağı çözümü yok, ancak olduğunda sizi [destek blog gönderimiz](ttps://aka.ms/iOS12_and_vpn) yoluyla bilgilendireceğiz.

NAC’yi kullanmak için şunları yapmanız gerekir:
1. Intune’un cihaz kimliklerini VPN profillerine dahil etmesini seçmek
2. Doğrudan NAC sağlayıcınız tarafından sağlanan yönergelere göre NAC sağlayıcı yazılımı/ürün yazılımınızı güncelleştirmek

Bu ayarın bir iOS VPN profilindeki kullanımı hakkında bilgi için bkz. [Microsoft Intune’da iOS cihazlara VPN ayarları ekleme](vpn-settings-ios.md). Ağ erişim denetimi hakkında daha fazla bilgi için bkz. [Ağ erişim denetimini (NAC) Intune ile tümleştirme](network-access-control-integrate.md). 

Şunun için geçerlidir: iOS

#### <a name="remove-an-email-profile-from-a-device-even-when-theres-only-one-email-profile----1818139---"></a>Yalnızca bir e-posta profili olduğunda bile bir CİHAZDAN bir e-posta profilini Kaldır <!-- 1818139 -->
Önceden, cihazda sadece bir e-posta profilinin *olması* durumunda bu e-posta profilini cihazdan kaldırmak mümkün değildi. Bu güncelleştirme ile bu davranış değişiyor. Artık cihazdaki tek e-posta profilini bile kaldırabilirsiniz. Ayrıntılar için bkz. [Intune kullanarak cihazlara e-posta ayarları ekleme](email-settings-configure.md).

#### <a name="powershell-scripts-and-aad----2309469---"></a>PowerShell betikleri ve AAD <!-- 2309469 -->
Intune’da PowerShell betikleri AAD cihaz güvenlik gruplarına hedeflenebilir.

#### <a name="new-required-password-type-default-setting-for-android-android-enterprise---2649963---"></a>Android için yeni "gerekli parola türü" varsayılan ayar Android Kurumsal<!-- 2649963 -->
Yeni bir uyumluluk ilkesi oluşturduğunuzda (**Intune** > **Cihaz uyumluluğu** > **İlkeler** > **İlke oluştur** > **Android** veya Platform > Sistem Güvenliği için **Android kurumsal**), **Gerekli parola türü** varsayılan değeri değişir:

Kaynak: Cihaz varsayılanı için: En az sayısal

Şunun için geçerlidir: Android, Android Kurumsal

Bu ayarları görmek için [Android](compliance-policy-create-android.md) veya [Android Kurumsal](compliance-policy-create-android-for-work.md)’a gidin.

#### <a name="use-a-pre-shared-key-in-a-windows-10-wi-fi-profile----2662938---"></a>Bir Windows 10 Wi-Fi profilinde önceden paylaşılan anahtar kullanın <!-- 2662938 -->
Bu güncelleştirmeyle birlikte Windows 10’da bir Wi-Fi yapılandırma profilinin kimliğini doğrulamak için WPA/WPA2 Kişisel güvenlik protokolü ile birlikte bir önceden paylaşılan anahtar (PSK) kullanabilirsiniz. Ayrıca 10 Ekim 2018 güncelleştirmesiyle Windows 10 cihazlarda bir tarifeli ağ için maliyet yapılandırmasını da belirtebilirsiniz.

Şu anda önceden paylaşılan anahtarları kullanmak için bir Wi-Fi profilini içeri aktarmanız veya özel bir profil oluşturmanız gerekiyor. [Windows 10 için Wi-Fi ayarları](wi-fi-settings-windows.md) makalesi, geçerli ayarları listeler. 

#### <a name="remove-pkcs-and-scep-certificates-from-your-devices----3218390---"></a>Cihazlarınızdan PKCS ve SCEP sertifikalarını kaldırma <!-- 3218390 -->
Bazı senaryolarda, bir gruptan ilke kaldırılması, bir yapılandırma veya uyumluluk dağıtımının silinmesi veya mevcut SCEP veya PKCS profillerinin yönetici tarafından güncelleştirilmesi durumlarında bile PKCS ve SCEP sertifikaları cihazlarda kalıyordu. Bu güncelleştirme ile bu davranış değişiyor. PKCS ve SCEP sertifikalarının cihazda kaldığı veya bu sertifikaların cihazdan kaldırıldığı bazı senaryolar da vardır. Bu senaryolar için bkz. [Microsoft Intune’da SCEP ve PKCS sertifikalarını kaldırma](remove-certificates.md).

#### <a name="use-gatekeeper-on-macos-devices-for-compliance----2504381---"></a>Ağ geçidi macOS cihazlar için Uyumluluk kullanın <!-- 2504381 -->
Bu güncelleştirme, cihazları uyumluluk açısından değerlendirmek için macOS Gatekeeper özelliğini içerir. Gatekeeper özelliğini ayarlamak için bkz. [macOS cihazlara cihaz uyumluluk ilkesi ekleme](compliance-policy-create-mac-os.md).


### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="enrollment-abandonment-report----1382924---"></a>Kayıt abandonment raporu <!-- 1382924 -->
Bırakılmış kayıtların ayrıntılarını sağlayan yeni bir rapor, **Cihaz kaydı** > **İzle** altında bulunabilir. Daha fazla bilgi için bkz. [Şirket portalı bırakma raporu](enrollment-report-company-portal-abandon.md).

#### <a name="new-azure-active-directory-terms-of-use-feature----2870393---"></a>Yeni Azure Active Directory koşulları kullanım özelliği <!-- 2870393 -->
Azure Active Directory’de mevcut Intune hüküm ve koşulları yerine kullanabileceğiniz bir kullanım koşulları özelliği vardır. Azure AD kullanım koşulları özelliği, hangi koşulların ne zaman gösterileceği konusunda daha fazla esneklik, daha iyi yerelleştirme desteği, koşulların ekrana çizilmesi üzerinde daha fazla denetim ve daha iyi raporlama sağlamaktadır. Azure AD kullanım koşulları özelliği, Enterprise Mobility + Security E3 paketinin de parçası olan Azure Active Directory Premium P1'i gerektirir. Daha fazla bilgi edinmek için bkz. [Kullanıcı erişimi için şirketinizin hüküm ve koşullarını yönetme makalesi](terms-and-conditions-create.md).

#### <a name="android-device-owner-mode-support---3188762--"></a>Android cihaz sahibi modu desteği <!--3188762-->
Samsung Knox Mobil Kaydı için Intune artık cihazları Android Cihaz Sahibi yönetim modunda kaydetmeyi destekliyor. WiFi veya hücresel ağ kullanan kullanıcılar, cihazlarını ilk kez açtıklarında yalnızca birkaç dokunuşla kayıt yapabilir. Daha fazla bilgi için bkz. [Android cihazları Samsung’un Knox Mobil Kayıt özelliğini kullanarak otomatik kaydetme](android-samsung-knox-mobile-enroll.md).

### <a name="device-management"></a>Cihaz yönetimi
#### <a name="new-settings-for-software-updates------1907869---"></a>Yazılım güncelleştirmeleri için yeni ayarlar   <!-- 1907869 -->  
- Bazı bildirimler en son yazılım güncelleştirmeleri yüklemesini tamamlamak üzere gereken yeniden başlatma hakkında uyarı son kullanıcılara artık yapılandırabilirsiniz.   
- KCG senaryolarını destekleyen bir yeniden başlatma için uyarı istemini iş saatleri dışında gerçekleşen bir yeniden başlatma artık yapılandırabilirsiniz.

#### <a name="group-windows-autopilot-enrolled-devices-by-correlator-id----2075110---"></a>Windows Autopilot kayıtlı cihazlar İlişkilendirici Kimliğine göre gruplandırma <!-- 2075110 -->
Intune, Configuration Manager aracılığıyla [mevcut cihazlar için Autopilot](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/New-Windows-Autopilot-capabilities-and-expanded-partner-support/ba-p/260430) kullanılarak kaydedilmiş Windows cihazları ilişkilendirici kimliğine göre gruplamayı artık destekliyor. İlişkilendirici kimliği, Autopilot yapılandırma dosyasının bir parametresidir. Intune, [Azure Active Directory cihaz özniteliği enrollmentProfileName](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#using-attributes-to-create-rules-for-device-objects) değerini “OfflineAutopilotprofile-<correlator ID>” değerine eşit olacak şekilde otomatik olarak ayarlar. Bu, çevrimdışı Autopilot kayıtları için enrollmentprofileName özniteliği aracılığıyla ilişkilendirici kimliğine göre rasgele Azure AD dinamik grupları oluşturulmasına izin verir. Daha fazla bilgi için bkz. [Mevcut cihazlar için Windows Autopilot](enrollment-autopilot.md#windows-autopilot-for-existing-devices).

#### <a name="intune-app-protection-policies----2984657---"></a>Intune uygulama koruma ilkeleri <!-- 2984657 -->
Intune uygulama koruma ilkeleri, Microsoft Outlook ve Microsoft Word gibi Intune tarafından korunan uygulamalar için çeşitli veri koruma ayarlarını yapılandırmanıza olanak sağlar. Ayrı ayrı ayarların bulunmasını kolaylaştırmak için hem [iOS](app-protection-policy-settings-ios.md) hem de [Android](app-protection-policy-settings-android.md) üzerinde bu ayarların görünümünde ve işlevinde değişiklik yaptık. İlke ayarları üç kategoriye ayrılır:
- **Verileri yeniden konumlandırma** - Bu grup kesme, kopyalama, yapıştırma ve farklı kaydetme kısıtlamaları gibi veri kaybı önleme (DLP) denetimlerini içerir. Bu ayarlar, kullanıcıların uygulamalarda verilerle nasıl etkileşim kurduğunu belirler.
- **Erişim gereksinimleri** - Bu grup, son kullanıcının uygulamalara iş bağlamında nasıl eriştiğini belirleyen uygulama başına PIN seçenekleri içerir.  
- **Koşullu başlatma** - Bu grup en düşük işletim sistemi ayarları, jailbreak uygulanmış ve kök erişim izni verilmiş cihazları algılama ve çevrimdışı yetkisiz kullanım süreleri gibi ayarları içerir.  
  
Ayarların işlevselliği değişmedi, ancak ilke yazma akışında çalışırken bu ayarları bulmanız artık daha kolay.

### <a name="intune-apps"></a>Intune uygulamaları

#### <a name="intune-will-support-a-maximum-package-size-of-8-gb-for-lob-apps----1727158---"></a>Intune, LOB uygulamaları için 8 GB en büyük paketin boyutuna destekleyecektir <!-- 1727158 -->
Intune, İş kolu (LOB) uygulamaları için izin verilen en fazla paket boyutunu 8 GB’a yükseltti. Daha fazla bilgi için bkz. [Microsoft Intune’a uygulama ekleme](apps-add.md).

#### <a name="add-custom-brand-image-for-company-portal-app----1916266---"></a>Şirket portalı uygulaması için özel marka resmi Ekle <!-- 1916266 -->
Microsoft Intune yöneticisi olarak, iOS Şirket Portalı uygulamasındaki kullanıcı profil sayfasında bir arka plan görüntüsü olarak kullanılacak özel bir marka görüntüsünü karşıya yükleyebilirsiniz. Şirket Portalı uygulamasını yapılandırma hakkında daha fazla bilgi için bkz. [Microsoft Intune Şirket Portalı uygulamasını yapılandırma](company-portal-app.md).

#### <a name="intune-will-maintain-the-office-localized-language-when-updating-office-on-end-users-machines----2971030---"></a>Intune Office yerelleştirilmiş dili, Office, son kullanıcıların makineleri güncelleştirirken korur <!-- 2971030 -->
Intune son kullanıcı makinenize Office yüklediğinde, son kullanıcılar önceki .MSI Office yüklemeleri ile aldıkları aynı dil paketini otomatik olarak alır. Daha fazla bilgi için bkz. [Microsoft Intune ile Office 365 uygulamalarını Windows 10 cihazlara atama](apps-add-office365.md).

### <a name="monitor-and-troubleshoot"></a>İzleme ve sorun giderme

#### <a name="new-intune-support-experience-in-the-microsoft-365-device-management-portal----3076965---"></a>Microsoft 365 cihaz Yönetim Portalı'nda yeni bir Intune destek deneyimi <!-- 3076965 -->
[Microsoft 365 Cihaz Yönetim portalında]( http://devicemanagement.microsoft.com) Intune için yeni bir Yardım ve Destek deneyimini kullanıma sunuyoruz. Yeni deneyim, sorununuzu kendi kelimelerinizle açıklamanıza ve sorun giderme içgörüleri ile Web tabanlı düzeltme içeriği almanıza olanak tanır. Bu çözümler, kullanıcı sorgularıyla şekillenen bir kural tabanlı makine öğrenimi algoritması aracılığıyla sunulur.  

Soruna özgü yönergelere ek olarak yeni olay oluşturma iş akışını kullanarak e-posta veya telefon yoluyla bir destek olayı açabilirsiniz.  

Dağıtıma dahil edilen müşteriler için bu yeni deneyim, Yardım ve Desteği açtığınızda bulunduğunuz konsol alanına dayalı, statik bir önceden belirlenmiş seçenekler kümesine yönelik geçerli Yardım ve Destek deneyiminin yerini alır.  

*Bu yeni Yardım ve Destek deneyimi, bazı kiracıların (tamamının değil) kullanımına sunulmaktadır ve Cihaz Yönetimi portalında kullanılabilir. Yeni deneyime katılacak kişiler, uygun Intune kiracıları arasından rastgele seçilir. Dağıtım kapsamı genişledikçe yeni kiracılar eklenecektir.*  

Daha fazla bilgi için [Yardım ve destek deneyimi](get-support.md#help-and-support-experience) nasıl Intune için destek alma.  

### <a name="powershell-module-for-intune--preview-available----951068---"></a>Intune – Önizleme için PowerShell Modülü <!-- 951068 -->
Intune API’si için Microsoft Graph yoluyla destek sağlayan yeni bir PowerShell modülü artık [GitHub]( https://aka.ms/intunepowershell)’da önizleme olarak kullanılabilir. Bu modülü kullanma hakkında daha fazla ayrıntı için modülün bulunduğu konumdaki README dosyasına bakın. 


<!-- ########################## -->
## <a name="week-of-october-15-2018"></a>15 Ekim 2018 haftası

### <a name="pin-prompt-when-you-change-fingerprints-or-face-id-on-an-ios-device-----2637704----"></a>Bir iOS cihazında kimliği yüz tanıma veya parmak izleri değiştirdiğinizde PIN istemi  <!-- 2637704  -->
Artık, kullanıcılar iOS cihazlarında biyometrik değişiklikler yaptığında PIN istenir. Bunlara kayıtlı parmak izleri veya yüz kimliğinde yapılan değişiklikler dahildir. İstemin zamanlaması, *(dakika) içinde erişim gereksinimlerini yeniden denetle* zaman aşımının yapılandırmasına bağlıdır.  Ayarlanmamışsa kullanıcıdan bir PIN ayarlaması istenir. 
 
Bu özellik yalnızca iOS için kullanılabilir ve iOS için Intune APP SDK’sı sürüm 9.0.1 veya üzeri sürümleri tümleştiren uygulamaların katılımını gerektirir. Hedeflenen uygulamalarda davranışın zorlanabilmesi için SDK tümleştirmesi gereklidir. Bu tümleştirme, sıralı bir şekilde gerçekleşir ve belirli uygulama ekiplerine bağımlıdır. Katılan uygulamalardan bazıları WXP, Outlook, Managed Browser ve Yammer’dır.


<!-- ########################## -->
## <a name="week-of-october-1-2018"></a>1 Ekim 2018 haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="access-to-key-profile-properties-using-the-company-portal-app----772203---"></a>Şirket portalı uygulamasını kullanarak anahtar profilini özelliklerine erişim <!-- 772203 -->
Son kullanıcılar artık parola sıfırlama gibi önemli hesap özellikleri ve eylemlerine Şirket portalı uygulamasından erişebilir. 

#### <a name="3rd-party-keyboards-can-be-blocked-by-app-settings-on-ios----1248481---"></a>3. taraf klavyeler iOS uygulama ayarları tarafından engellendi <!-- 1248481 -->
iOS cihazlarda Intune yöneticileri, ilke korumalı uygulamalarda kuruluş verilerine erişilirken üçüncü taraf klavyelerin kullanımını engelleyebilir. Uygulama Koruma İlkesi (APP) üçüncü taraf klavyelerini engelleyecek şekilde ayarlandığında, cihaz kullanıcısı üçüncü taraf klavyesini kullanarak şirket verileriyle ilk kez etkileşim kurarken bir ileti alır. Yerel klavye dışındaki tüm seçenekler engellenir ve cihaz kullanıcıları bunları görmez. Cihaz kullanıcıları iletişim kutusu iletisini tek bir kez görür. 

#### <a name="user-account-access-of-intune-apps-on-managed-android-and-ios-devices----1248496---"></a>Yönetilen Android ve iOS cihazlarında Intune uygulama kullanıcı hesabı erişimi <!-- 1248496 -->
Microsoft Intune yöneticisi olarak yönetilen cihazlarda hangi kullanıcı hesaplarının Microsoft Office uygulamalarına eklendiğini denetleyebilirsiniz. Erişimi yalnızca izin verilen kullanıcı hesaplarıyla sınırlayabilecek ve kayıtlı cihazlarda kişisel hesapları engelleyebilirsiniz. 

#### <a name="outlook-ios-and-android-app-configuration-policy---1828527---"></a>Outlook iOS ve Android uygulama yapılandırma İlkesi <!--1828527 -->
Artık iOS ve Android’de, ActiveSync protokolüyle Temel kimlik doğrulamasından yararlanan şirket içi kullanıcılar için bir Outlook iOS ve Android uygulama yapılandırma ilkesi oluşturabilirsiniz. Ek yapılandırma ayarları, iOS ve Android için Outlook’ta etkinleştirildikçe eklenecektir.

#### <a name="office-365-pro-plus-language-packs----1833450---"></a>Office 365 Pro Plus dil paketleri <!-- 1833450 -->
Intune yöneticisi olarak, Intune aracılığıyla yönetilen Office 365 Pro Plus uygulamaları için ek dillerin dağıtımını yapabileceksiniz. Kullanılabilir diller listesi, dil paketinin **Tür** bilgisini içerir (çekirdek, kısmı ve yazım denetleme). Azure portalında **Microsoft Intune** > **İstemci uygulamaları** > **Uygulamalar** > **Ekle**’yi seçin. **Uygulama ekle** dikey penceresindeki **Uygulama türü** listesinde **Office 365 Paketi** altından **Windows 10**'u seçin. **Uygulama Paketi Ayarları** dikey penceresinde **Diller**'i seçin.

####  <a name="windows-line-of-business-lob-apps-file-extensions----1884873---"></a>Windows iş kolu (LOB) uygulamaları dosya uzantıları <!-- 1884873 -->
Windows LOB uygulamaları için dosya uzantıları artık içerecektir *.msi*, *.appx*, *.appxbundle*, *.msix*, ve *. msixbundle*. Microsoft Intune’da, **İstemci uygulamaları** > **Uygulamalar** > **Ekle**’yi seçerek bir uygulama ekleyebilirsiniz. **Bölme ekle** bölmesi görüntülenir ve **Uygulama türünü** seçmenize olanak tanır. Windows LOB uygulamaları için uygulama türü olarak **İş kolu uygulamasını** seçin, **Uygulama paketi dosyasını** seçin ve uygun uzantıya sahip bir yükleme dosyası girin.

#### <a name="windows-10-app-deployment-using-intune----2309001---"></a>Intune kullanarak Windows 10 uygulama dağıtımı <!-- 2309001 -->
Yöneticiler, iş kolu (LOB) uygulamaları ve İş için Microsoft Store uygulamaları için mevcut destekten yararlanarak kuruluşlarındaki uygulamaların çoğunu Intune ile Windows 10 cihazlarındaki son kullanıcılara dağıtabilir. Yöneticiler, Windows 10 kullanıcıları için MSI, Setup.exe veya MSP gibi çeşitli biçimlerdeki uygulamalar ekleyebilir, yükleyebilir ve kaldırabilir. Intune, indirme ve yükleme öncesinde gereksinim kurallarını değerlendirerek, işlemin durumunu veya yeniden başlatma gereğini Windows 10 Eylem Merkezi aracılığıyla son kullanıcılara bildirebilir. Bu işlevsellik, sonuçta, bu iş yükünü Intune'a ve buluta kaydırmak isteyen kuruluşların engellemesini kaldırmış olur. Bu özellik şu anda genel önizleme aşamasındadır ve önümüzdeki birkaç ay içinde özelliğe önemli yeni olanaklar eklemeyi bekliyoruz. 

#### <a name="app-protection-policy-app-settings-for-web-data----2662995---"></a>Web veri için uygulama koruma İlkesi (uygulama) ayarları <!-- 2662995 -->
Gerek Android gerekse iOS cihazlarında Web içeriği için uygulama ilke ayarları, gerek http gerekse https Web bağlantılarını, ayrıca iOS Evrensel Bağlantıları ve Android Uygulama Bağlantıları aracılığıyla veri aktarımını daha iyi işleyecek şekilde güncelleştirilecektir. 

#### <a name="end-user-device-and-app-content-menu----2771453---"></a>Son kullanıcının cihaz ve uygulama içerik menüsü <!-- 2771453 -->
Son kullanıcılar artık cihaz yeniden adlandırma veya uyumluluk denetleme gibi sık kullanılan eylemleri tetiklemek için cihazdaki açılır menüyü kullanabilir. 

#### <a name="windows-company-portal-keyboard-shortcuts----2771518---"></a>Windows Şirket Portalı klavye kısayolları <!-- 2771518 -->
Son kullanıcılar artık Windows Şirket Portalı’nda klavye kısayollarını (hızlandırıcılar) kullanarak uygulama ve cihaz eylemlerini tetikleyebilir.

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="create-dns-suffixes-in-vpn-configuration-profiles-on-devices-running-windows-10---1333668---"></a>DNS son eklerini Windows 10 çalıştıran cihazlarda VPN yapılandırma profilleri oluşturma<!-- 1333668 -->
Bir VPN cihaz yapılandırma profili oluşturduğunuzda (**Cihaz yapılandırması** > **Profiller** > **Profil oluştur** > **Windows 10 ve üzeri** platform > **VPN** profil türü) bazı DNS ayarları girersiniz. Bu güncelleştirme ile Intune'da birden çok **DNS soneki** de girebilirsiniz. DNS son ekleri kullanırken bir ağ kaynağını tam etki alanı adı (FQDN) yerine kısa adını kullanarak arayabilirsiniz. Bu güncelleştirme ayrıca Intune’da DNS son eklerinin sırasını değiştirmenize de imkan verir.
[Windows 10 VPN ayarları](vpn-settings-windows-10.md#dns-settings) makalesi, geçerli DNS ayarlarını listeler.
Şunun için geçerlidir: Windows 10 cihazlar

#### <a name="support-for-always-on-vpn-for-android-enterprise-work-profiles----1333705---"></a>Android kurumsal iş profilleri için her zaman açık VPN desteği <!-- 1333705 -->
Bu güncelleştirmede yönetilen iş profilleri olan Android kurumsal cihazlarda Her Zaman Açık VPN bağlantıları kullanabilirsiniz. Her zaman açık VPN bağlantıları; kullanıcı cihazının kilidini açtığında, cihaz yeniden başlatıldığında veya kablosuz ağ değiştiğinde bağlı kalır veya hemen tekrar bağlanır. Bağlantıyı “kilitli”moduna da alabilirsiniz, böylece VPN bağlantısı etkin olana kadar tüm ağ trafiği engellenir.
Her Zaman Açık VPN'yi platform için **Cihaz yapılandırması** > **Profiller** > **Profil oluşturma**  >  **Android kurumsal**'da > **Cihaz kısıtlamaları** > **Bağlantı** ayarlarında etkinleştirebilirsiniz.

#### <a name="issue-scep-certificates-to-user-less-devices----1744554---"></a>SCEP sertifikaları vermek için Kullanıcısız cihazlar <!-- 1744554 -->
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

Şunun için geçerlidir: Windows 10 ve üzeri ve iOS, Wi-Fi için desteklenir

#### <a name="remotely-lock-uncompliant-devices----2064495---"></a>Uncompliant cihazları uzaktan kilitleme <!-- 2064495 -->
Cihazın uyumlu olmadığı durumlarda, uyumluluk ilkesinde cihazı uzaktan kilitleyen bir eylem oluşturabilirsiniz. Intune > **Cihaz uyumluluğu**'nda yeni bir ilke oluşturun veya mevcut bir ilkeyi > **Özellikler**'i seçin. **Uyumsuzluğa yönelik eylemler** > **Ekle**’yi ve cihazı uzaktan kilitlemeyi seçin.
Şu platformlarda desteklenir: 
- Android
- iOS
- Mac OS
- Windows 10 Mobile 
- Windows Phone 8.1 ve üzeri 

#### <a name="windows-10-and-later-kiosk-profile-improvements-in-the-azure-portal----2748224---"></a>Windows 10 ve Azure portalında sonraki Kiosk profili geliştirmeleri <!-- 2748224 -->
Bu güncelleştirmede Windows 10 Bilgi Noktası cihaz yapılandırma profilinde (platform için **Cihaz yapılandırması** > **Profiller** > **Profil oluştur** > **Windows 10 ve üzeri**, profil türü için > **Bilgi noktası önizlemesi**) yapılan aşağıdaki iyileştirmeler bulunur: 
- Şu anda aynı cihazda birden fazla bilgi noktası profili oluşturabiliyorsunuz. Bu güncelleştirme ile Intune, cihaz başına yalnızca bir bilgi noktası profilini destekleyecek. Tek bir cihazda birden fazla bilgi noktası profiline ihtiyacınız varsa bir Özel URI kullanabilirsiniz.
- **Çok uygulamalı bilgi noktası** profilinde, uygulama kılavuzundaki **Başlangıç menüsü düzeni** için uygulama kutucuğu boyutunu ve sırasını seçebilirsiniz. Daha fazla özelleştirme isterseniz bir XML dosyasını karşıya yükleyebilirsiniz.
- Bilgi Noktası Tarayıcısı ayarları, **Bilgi Noktası** ayarlarına taşınıyor. Şu anda **Bilgi Noktası web tarayıcısı** ayarlarının Azure portalında kendi kategorisi var.
Şunun için geçerlidir: Windows 10 ve üzeri




### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="apply-autopilot-profile-to-enrolled-win-10-devices-not-already-registered-for-autopilot----1558983---"></a>Autopilot profili için kayıtlı Win 10 cihazlar için Autopilot zaten kayıtlı uygulama <!-- 1558983 -->
Kayıtlı olduğu halde Autopilot’a kayıtlı olmayan Win 10 cihazlara Autopilot profili uygulayabilirsiniz. Autopilot profilinde **Hedeflenen tüm cihazları Autopilot’a dönüştür** seçeneğini belirterek Autopilot olmayan cihazları Autopilot dağıtım hizmetine otomatik olarak kaydedin. Kaydın işlenmesi için 48 saat kadar bekleyin. Cihazın kaydı kaldırıldığında ve cihaz sıfırlandığında Autopilot, cihazı sağlar.

#### <a name="create-and-assign-multiple-enrollment-status--page-profiles-to-azure-ad-groups----2526564---"></a>Oluşturma ve Azure AD gruplarına birden çok kayıt durumu sayfası profili atama <!-- 2526564 -->
Artık Azure ADD grupları için birden fazla Kayıt Durumu Sayfası profili [oluşturup atayabilirsiniz](windows-enrollment-status.md).

#### <a name="migration-from-device-enrollment-program-to-apple-business-manager-in-intune---2748613--"></a>Cihaz kayıt programı geçiş için ıntune'da Apple İşletme Yöneticisi <!--2748613-->
Apple Business Manager (ABM), Intune’da çalışır ve hesabınızı Aygıt Kayıt Programı’ndan (DEP) ABM’ye yükseltebilirsiniz. Intune’da bu işlem aynıdır. Apple hesabınızı DEP’den ABM’ye yükseltmek için şu adrese gidin: [ https://support.apple.com/en-us/HT208817]( https://support.apple.com/en-us/HT208817).

### <a name="alert-and-enrollment-status-tabs-on-the-device-enrollment-overview-page---2748656--"></a>Cihaz kayıt genel bakış sayfasında uyarı ve kayıt durumu sekmeleri <!--2748656-->
Uyarılar ve kayıt hataları artık Cihaz kaydı genel bakış sayfasında ayrı sekmelerde görüntülenir.

### <a name="device-management"></a>Cihaz yönetimi

#### <a name="restricts-apps-and-block-access-to-company-resources-on-android-devices----2451462----"></a>Android cihazlarda şirket kaynaklarına uygulamaları ve erişimi kısıtlayan <!-- 2451462  -->  
**Cihaz uyumluluğu** > **İlkeler** > **İlke oluştur** > **Android** > **Sistem Güvenliği**'nde *Cihaz Güvenliği* bölümünde **Kısıtlı uygulamalar** adlı yeni bir ayar vardır. **Kısıtlı uygulamalar** ayarı, üzerinde belirli uygulamalar yüklü olduğunda cihazın şirket kaynaklarına erişimini engelleyecek bir uyumluluk ilkesi kullanır. Cihaz, kısıtlı uygulamalar kaldırılana kadar uyumsuz sayılır.
Şunun için geçerlidir: 
- Android

<!-- ########################### -->
## <a name="notices"></a>Bildirimler

[!INCLUDE [Intune notices](./includes/intune-notices.md)]
