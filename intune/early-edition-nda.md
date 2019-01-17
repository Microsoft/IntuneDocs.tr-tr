---
title: Erken sürüm - Intune
titlesuffix: ''
description: Microsoft Intune erken sürüm
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/16/2019
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
ms.openlocfilehash: db2ebe82713f13283c0d9e263496971565312bf4
ms.sourcegitcommit: 5a7f4617d11f32956161189b7e95ee8771098e0a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/17/2019
ms.locfileid: "54361890"
---
# <a name="the-early-edition-for-microsoft-intune---january-2019"></a>Erken sürüm Microsoft Intune - Ocak 2019

> [!Note]
> NDA bildirimi: Intune için aşağıdaki değişiklikler geliştirilme aşamasındadır. Bu bilgiler NDA kapsamında çok kısıtlı bir kapsamla paylaşılır. Bu bilgilerin hiçbirini sosyal medyada veya Twitter, UserVoice, Reddit vb. gibi kamuya açık web sitelerinde paylaşmayın. 

**Erken sürüm**, NDA altında paylaşılan Microsoft Intune'un gelecek sürümlerinde kullanıma sunulacak yeni özelliklerin bir listesini sunar. Bu bilgiler kısıtlı bir kapsamla verilmektedir ve değiştirilebilir. Bu bilgileri Twitter veya UserVoice’da ya da şirketiniz dışında paylaşmayın. Burada listelenen özelliklerden bazılarının son tarihe yetişememe riski vardır ve gelecek sürüme ertelenebilir. Diğer özellikler, müşterinin kullanımına hazır olduğundan emin olmak için pilot (sürüyor) aşamasında test edilmektedir. Herhangi bir sorunuz veya endişeniz varsa lütfen Microsoft ürün grubu ilgili kişisiyle bağlantı kurun.

Bu sayfa düzenli aralıklarla güncelleştirilir. Ek güncelleştirmeleri daha sonra denetleyin.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Azure portalında Intune

<!-- 1901 start -->

### <a name="android-enterprise-apps----1352553----"></a>Android kurumsal uygulamalar <!-- 1352553  -->
Yönetilen Google Play uygulamaları Microsoft Intune silmek mümkün olacaktır. Yönetilen Google Play uygulama silmek için Azure portal ve select Intune açılır **istemci uygulamaları** > **uygulamaları**. Uygulama listesinden, yönetilen Google Play uygulaması'nın sağındaki üç nokta simgesini (...) seçin ve ardından **Sil** görüntülenen listeden. Uygulama listesinden bir yönetilen Google Play uygulaması sildiğinizde, yönetilen Google Play uygulaması otomatik olarak onaylanmadı.

### <a name="managed-google-play-app-type----1352580---"></a>Yönetilen Google Play uygulaması türü <!-- 1352580 -->
**Yönetilen Google Play** uygulama türü, özellikle eklemenize olanak sağlayacaktır [yönetilen Google Play uygulamaları](https://play.google.com/work/search?q=microsoft&c=apps) ıntune. Intune Yöneticisi olarak, şimdi göz atın, arama, onaylama, eşitleme ve onaylı bir yönetilen Google Play ıntune'daki uygulamaları atamak mümkün olacaktır. Yönetilen Google Play konsolunu için ayrı olarak göz atmak artık ihtiyacınız ve artık yeniden kimlik doğrulamaya zorlayabilir gerekir. Intune'da seçin **istemci uygulamaları** > **uygulamaları** > **Ekle**. İçinde **uygulama türü** listesinden **yönetilen Google Play** uygulama türü olarak.

### <a name="preview-of-support-for-android-corporate-owned-fully-managed-devices----1574342----"></a>Şirkete ait ve tamamen yönetilen Android cihazları için destek önizlemesi <!-- 1574342  -->
Intune, tam olarak yönetilen Android cihazları, bir kuruluşa ait destekleyeceği yeri sıkı bir şekilde tarafından yönetilen cihazları "cihaz sahibi" senaryo BT ve tek tek kullanıcılarla bağlı. Bu durum, yöneticilerin tüm cihazı yönetebilir, ilke denetimlerini iş profilleri kullanılamaz genişletilmiş bir aralığını zorla olanak sağlar ve kullanıcıları, yalnızca yönetilen Google Play uygulamaları yüklemek için sınırlar. Ayarlamak için tam olarak yönetilen Android cihazları, gider **cihaz kaydı** > **Android kaydını** > **şirkete, tam olarak yönetilen kullanıcı cihazları** . Bu özelliğin önizlemede olduğunu lütfen unutmayın. Sertifikalar, uyumluluk ve koşullu erişim gibi bazı Intune özellikleri ile şu anda kullanılabilir olmayan Android tam olarak yönetilen kullanıcı cihazları.

### <a name="deployment-of-online-licensed-microsoft-store-for-business-apps----1672660----"></a>İş uygulamalarına yönelik çevrimiçi lisanslı Microsoft Store dağıtımı <!-- 1672660  -->
Gerekli çevrimiçi lisanslı Microsoft Store cihaz bağlamında kurumsal uygulamalar için atayamazsınız olacaktır. Bu şekilde bir iş uygulaması için Microsoft Store dağıtımı, cihazdaki tüm kullanıcılar için yüklenecek uygulamayı etkinleştirir. Bu yalnızca Windows 10 RS4 + Masaüstü cihazları için geçerlidir. Cihaz bağlamında yükleme seçeneği, istemci uygulamaları atama sayfasında MSFB çevrimiçi lisanslı uygulamaları için kullanılabilir.

### <a name="configure-profile-to-skip-some-screens-during-setup-assistant----2276470----"></a>Kurulum Yardımcısı sırasında bazı ekranları atlamak için profil yapılandırma <!-- 2276470  -->
MacOS kayıt profili oluşturduğunuzda, bir kullanıcı Kurulum Yardımcısı gittiğinde aşağıdaki ekranlardan herhangi birinde atlamak için yapılandırmak mümkün olacaktır:
- Android Geçişi
- Görüntü Tonu
- Gizlilik
- iCloudStorage

### <a name="assign-autopilot-profiles-to-the-all-devices-virtual-group---2715522----"></a>Tüm cihazlar sanal grubuna Autopilot profilleri atama <!--2715522  -->
Tüm cihazlar sanal grubuna Autopilot profilleri atayabileceksiniz. Bunu yapmak için **Cihaz kaydı** > **Windows kaydı** > **Dağıtım Profilleri**'i seçin > bir profil seçin > **Atamalar**'ı seçin > **Atama hedefi** altından **Tüm cihazlar**'ı seçin. Autopilot profilleri hakkında daha fazla bilgi için bkz. [Windows AutoPilot kullanarak Windows cihazları kaydetme](enrollment-autopilot.md).

### <a name="customize-wallpaper-on-supervised-ios-devices-using-a-device-configuration-profile----2809324----"></a>Duvar kağıdı denetimli iOS cihazlarında cihaz yapılandırma profili kullanarak özelleştirme <!-- 2809324  -->
İOS cihazları için cihaz yapılandırma profili oluşturduğunuzda, izin ve bazı ayarları kısıtlamak mümkün olmayacak **cihaz Yapılandırması** > **profilleri**  >  **Profil oluşturma** > **iOS** Platform > **cihaz kısıtlamaları** profil türü için. Bu güncelleştirme yeni eklemeler **duvar kağıdı** .png, .jpg veya .jpeg görüntü duvar kağıdı olarak kullanmak yönetici izin ayarları resmi önizleme ve kullanıcıların duvar kağıdı değiştirmesini engelleyin. Duvar kağıdı ayarları yalnızca denetimli cihazlar için geçerlidir. Geçerli ayarların listesi için bkz. [iOS cihaz kısıtlama ayarları](device-restrictions-ios.md).

### <a name="toast-notifications-for-win32-apps----3136566-----"></a>Win32 uygulamaları için kutlama bildirimleri <!-- 3136566   -->
Uygulama ataması başına gösteren son kullanıcı bildirimleri bastır mümkün olacaktır. Intune'dan seçin **istemci uygulamaları** > **uygulamaları** > uygulamayı seçin > **Assignemnts** > **grupları dahil**. 

### <a name="contact-sharing-via-bluetooth-is-removed-in-device-restrictions--device-owner-for-android-enterprise----3598396---"></a>Bluetooth ile kişi paylaşımı cihaz kısıtlamaları kaldırılmış > Android Kurumsal cihaz sahibi <!-- 3598396 -->
Kurumsal Android cihazlar için cihaz kısıtlama profili oluşturduğunuzda, var olan bir **Bluetooth aracılığıyla kişi paylaşımı** ayarı. Bu güncelleştirmede, **Bluetooth aracılığıyla kişi paylaşımı** ayarı kaldırılacak (**cihaz Yapılandırması** > **profilleri**  >  **Profil oluşturma** > **Android Kurumsal** Platform > **cihaz kısıtlamaları > cihaz sahibi** profil türü için >  **Genel**). 

**Bluetooth aracılığıyla kişi paylaşımı** ayarı Android Kurumsal cihaz sahibi yönetimi için desteklenmez. Bu ayar kaldırıldığında, bu ayar etkinleştirildikten ve yapılandırıldıktan sonra ortamınızda olsa bile bu nedenle, herhangi bir cihaz veya kiracıları, etkilemez.

Geçerli ayarları listesini görmek için Git [izin vermek veya özellikleri kısıtlamak için Android Kurumsal cihaz ayarları](device-restrictions-android-for-work.md).

Uygulama hedefi: Android Kurumsal cihaz sahibi

<!-- 1812 start -->

### <a name="android-enterprise-app-we-app-deployment----1171203---"></a>Android Kurumsal uygulama-BİZ uygulama dağıtımı <!-- 1171203 -->
Bir kayıtlı olmayan uygulama koruma İlkesi kayıt olmadan Android cihazlar için (APP-BİZ) dağıtım senaryosu, şunları yapabileceksiniz yönetilen Google Play mağazası uygulamalarını dağıtma ve LOB uygulamaları kullanıcılara için kullanılacak. Özellikle, BT'nin son kullanıcılara cihazlarının güvenlik duruşunu bilinmeyen kaynaklardan yüklemeleri vererek çözmek, son kullanıcılar artık gerektiren bir uygulama kataloğu ve yükleme deneyimi sağlamak. Ayrıca, bu dağıtım senaryosu bir geliştirilmiş son kullanıcı deneyimi sağlar.

### <a name="the-intune-app-sdk-will-support-256-bit-encryption-keys----1832174---"></a>Intune uygulama SDK'sı, 256 bit şifreleme anahtarları destekleyecek <!-- 1832174 -->
Android için Intune uygulama SDK'sı, şifreleme uygulama koruma ilkeleri tarafından etkinleştirilmişse 256 bit şifreleme anahtarları kullanır. SDK'sı, 128 bit anahtar içeriği ve eski SDK sürümleri kullanan uygulamalar ile uyumluluk için destek sağlamak üzere devam eder.


### <a name="intune-policies-update-authentication-method-and-company-portal-app-installation-----1927359---"></a>Intune ilkeleri, kimlik doğrulama yöntemi ve şirket Portalı Uygulama yüklemesi güncelleştirme  <!-- 1927359 -->
Kurulum Yardımcısı ile Apple'nın Kurumsal cihaz kayıt yöntemleri biri aracılığıyla kayıtlı cihazlarda, el ile uygulama Mağazası'ndan son kullanıcılar tarafından yüklendiğinde, Intune Şirket portalı artık destekleyecektir. Bu değişiklik, yalnızca kayıt sırasında Apple Kurulum Yardımcısı ile doğrulandığında geçerlidir. Bu değişiklik, yalnızca aracılığıyla kaydedilmiş iOS cihazları etkiler:  
* Apple configurator
* Apple İşletme Yöneticisi
* Apple School Manager
* Apple aygıt kayıt programı (DEP)

Kullanıcıların uygulama Mağazası'ndan Şirket portalı uygulamasını yüklediğinizde ve onun üzerinden bu cihazları kaydetmek deneyin, bunlar bir hatayla karşılaşırsınız. Bu cihazlar, bu, otomatik olarak, kayıt sırasında Intune tarafından gönderildiğinde yalnızca şirket portalını kullanması beklenen. Azure portalında ıntune'da kayıt profilleri, cihazların kimliklerini nasıl doğrulayacaklarını belirtebilirsiniz ve Şirket portalı uygulaması'na alırsanız güncelleştirilecektir. DEP cihaz kullanıcılarınız Şirket portalı olmasını istiyorsanız, tercihlerinizi bir kayıt profili belirtmeniz gerekir. Ayrıca, **Cihazınızı tanımlamanız** Şirket portalı uygulamasında ekran yakında geçersiz olacak.  
Zaten kayıtlı DEP cihazlarında şirket Portalı'nı yüklemek için Intune'a gitmeniz gerekir > istemci uygulamaları ve uygulama yapılandırma ilkeleriyle yönetilen bir uygulama olarak gönderin. Bu adımların hakkında ayrıntılı bilgi gelecekteki belgelere renkle gösterilir.

### <a name="non-administrators-can-enable-bitlocker-on-windows-10-devices-joined-to-azure-ad---2147379---"></a>Yönetici olmayan kullanıcılar Azure AD'ye katılmış Windows 10 cihazlarda BitLocker'ı etkinleştirme<!-- 2147379 -->
Windows 10 cihazlarda BitLocker ayarları etkinleştirdiğinizde (**cihaz Yapılandırması** > **profilleri** > **profili oluşturma**  >  **Windows 10 ve üzeri** Platform > **uç nokta koruma** profil türü için > **Windows şifreleme**), BitLocker ayarları ekleyin. Bu güncelleştirme, şifrelemeyi etkinleştirmek standart kullanıcılar (Yönetici olmayanlar) izin vermek için yeni bir BitLocker ayar içerir. Geçerli ayarları görüntülemek için bkz: [Windows 10 için Endpoint protection ayarları](endpoint-protection-windows-10.md#windows-encryption).


### <a name="additional-settings-for-outlook----3301182---"></a>Outlook için ek ayarlar <!-- 3301182 -->
Artık iOS için Outlook ve Intune kullanarak Android için ek ayarlar da yapılandırabilirsiniz.  Ayarlar aşağıdakileri içerir:
- Yalnızca iOS ve Android Outlook'ta kullanılacak iş veya Okul hesaplarını izin ver
- Office 365 modern kimlik doğrulamayı dağıtmak ve hibrit modern kimlik doğrulaması şirket hesapları
- Kullanım `SAMAccountName` username alan temel kimlik doğrulaması seçildiğinde e-posta profili için
- Kaydedilecek kişiler izin ver
- Dış alıcılara posta ipuçları yapılandırın
- Yapılandırma **odaklanmış gelen kutusu**
- İOS için Outlook erişmeye Biyometri gerektirir 
- Bloğu dış görüntüleri

> [!NOTE]
> Erişim için Kurumsal kimlikleri yönetmek için Intune uygulama koruma ilkeleri kullanıyorsanız değil etkinleştirmeyi düşünebilirsiniz **Biyometri gerektiren**. Daha fazla bilgi için **erişim için Kurumsal kimlik bilgilerini gerektir** için [iOS erişim gereksinimleri](app-protection-policy-settings-ios.md#access-settings) ve [Android erişim gereksinimlerini](app-protection-policy-settings-android.md#access-settings).

### <a name="administrative-templates-are-in-public-preview-and-moved-to-their-own-configuration-profile----3322847---"></a>Yönetim Şablonları genel Önizleme aşamasındadır ve kendi yapılandırma profiline taşınır <!-- 3322847 -->
Intune Yönetim Şablonları (**cihaz Yapılandırması** > **Yönetim Şablonları**) şu anda özel Önizleme aşamasındadır. Bu güncelleştirme ile: Yönetim Şablonları, Intune'da yönetilebilir 300 ayarları içerir. Daha önce bu ayarlar, yalnızca Grup İlkesi Düzenleyicisi'nde vardı.
Yönetim Şablonları genel önizlemede Yönetim Şablonları hareket etmesini **cihaz Yapılandırması** > **Yönetim Şablonları** için **cihaz Yapılandırma** > **profilleri** >**profili oluşturma** > içinde **Platform**, seçin  **Windows 10 ve üzeri**, **profil türü**, seçin **Yönetim Şablonları**.
Raporlama etkinse geçerlidir: Windows 10 ve üzeri

### <a name="intune-macos-company-portal-dark-mode----3300524---"></a>Intune macOS Şirket portalı koyu modu <!-- 3300524 -->
Intune macOS Şirket portalı, macOS için artık koyu modunu destekler. Bir macOS 10.14 + cihazda koyu modunu etkinleştirdiğinizde, Şirket portalı görünümünü ayarlar yansıtma için bu modu renkleri.

<!-- 1810 start -->

### <a name="use-microsoft-recommended-settings-with-security-baselines----2055484---"></a>Microsoft tarafından önerilen Güvenlik Taban Çizgili ayarları kullanma <!-- 2055484 -->
Intune, Windows Defender ATP ve Office 365 ATP dahil güvenliğe odaklı diğer hizmetlerle tümleşir. Müşteriler, Microsoft 365 hizmetleri çapında ortak bir strateji ve birbiriyle bütünleşen bir dizi uçtan uca güvenlik iş akışı istiyor. Amacımız, stratejileri birbiriyle uyumlu hale getirmek ve güvenlik işlemleri ve sık kullanılan yönetici görevleri arasında bir köprü oluşturan çözümler geliştirmek. Intune olarak bu amaca Microsoft tarafından önerilen bir dizi "Güvenlik taban çizgisini" (**Intune** > **Güvenlik taban çizgileri**) yayımlayarak ulaşmayı hedefliyoruz.  Yöneticiler, doğrudan bu taban çizgilerinden güvenlik ilkeleri oluşturabilecek ve sonra bunları kullanıcılarına dağıtabilecekler. Ayrıca en iyi yöntem olan önerileri kuruluşlarının ihtiyaçlarını karşılayacak şekilde özelleştirebilirler. Intune, cihazların bu taban çizgilerle uyumlu kalmasını sağlar ve yöneticilere uyumlu olmayan kullanıcıları ve cihazları bildirir.

### <a name="selective-wipe-support-for-wip-without-enrollment-devices----1434452---"></a>Kayıt olmadan WIP cihazlar için seçmeli temizleme desteği <!-- 1434452 -->
Kayıt olmadan Windows bilgi Koruması (WIP-BİZ) Windows 10 cihazlarda tam MDM kaydı gerek kalmadan Kurumsal verileri korumak müşterilerin olanak tanır. Bir WIP ile korunan belgeleri sonra-BİZ ilke, korunan verilerin bir Intune Yöneticisi tarafından seçmeli temizlenmesine. Kullanıcı ve cihaz seçerek ve WIP ile korunan tüm verileri bir silme isteği gönderiliyor-BİZ İlkesi kullanılamaz olacak. Azure portalındaki Intune'dan **Mobil uygulama** > **Uygulama seçmeli silme**'yi seçin.

<!-- 1809 start -->  

### <a name="app-protection-policy-app-settings-for-web-data----2662995---"></a>Web verileri için Uygulama Koruma İlkesi (APP) ayarları <!-- 2662995 -->
Gerek Android gerekse iOS cihazlarında Web içeriği için uygulama ilke ayarları, gerek http gerekse https Web bağlantılarını, ayrıca iOS Evrensel Bağlantıları ve Android Uygulama Bağlantıları aracılığıyla veri aktarımını daha iyi işleyecek şekilde güncelleştirilecektir.  

<!-- 1808 start -->

### <a name="apple-vpp-token-used-by-another-mdm----1488946---"></a>Başka bir MDM tarafından kullanılan Apple VPP belirteci <!-- 1488946 -->
Bir Apple toplu satın alınan program (VPP) belirteci hem Intune hem de başka bir MDM tarafından kullanıldığında Intune bunu algılayacak ve ayrıntıları gösterecek.

### <a name="retired-devices-in-the-device-compliance-dashboard----1981119---"></a>Cihaz uyumluluk panosunda kullanımdan kaldırılan cihazlar <!-- 1981119 -->
Gelecek bir güncelleştirme ile kullanımdan kaldırılan cihazlar uyumluluk panosundan da kaldırılacak. Bu durum, uyumluluk numaralarınızı değiştirecek.



<!-- 1807 start -->

### <a name="check-for-configuration-manager-compliance----2192052---"></a>Configuration Manager uyumluluğunu denetleme <!-- 2192052 -->
Gelecekte yapılacak bir güncelleştirmede yeni bir System Center Configuration Manager uyumluluk ayarı olacak (**Cihaz uyumluluğu** > **İlkeler** > **İlke oluştur** > **Windows 10**). Configuration Manager, Intune uyumluluğuna sinyal gönderir. Intune ayarını kullanarak tüm Configuration Manager sinyallerinin “uyumlu” olarak döndürülmesini gerektirebilirsiniz.

Örneğin, tüm yazılım güncelleştirmelerinin cihazlarda yüklü olmasını gerektirirsiniz. Configuration Manager’da bu gereksinim, “Yüklü” durumundadır. Cihazdaki herhangi bir program bilinmeyen bir durumdaysa cihaz, Intune ile uyumlu olmayacaktır.

Windows 10 ve üzeri için geçerlidir



## <a name="notices"></a>Bildirimler

Şu anda etkin bildirim yok.

### <a name="see-also"></a>Ayrıca bkz.
Son geliştirmelere ilişkin ayrıntılar için bkz. [Microsoft Intune’daki Yenilikler](whats-new.md).



