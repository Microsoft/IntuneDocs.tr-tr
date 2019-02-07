---
title: Erken sürüm - Intune
titlesuffix: ''
description: Microsoft Intune erken sürüm
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/04/2019
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
ms.openlocfilehash: 92644eeed28911d0d49ec2aa20fcfed4a6553486
ms.sourcegitcommit: fddf90a6aa17b09005723653a0c9a520856bb2ea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/06/2019
ms.locfileid: "55781513"
---
# <a name="the-early-edition-for-microsoft-intune---february-2019"></a>Erken sürüm Microsoft Intune - Şubat 2019

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
<!-- 1902 start-->

### <a name="powershell-scripts-can-run-in-a-64-bit-host-on-64-bit-devices----1862675----"></a>PowerShell betiklerini bir 64-bit ana bilgisayar, 64 bit cihazlarda çalıştırabilirsiniz <!-- 1862675  -->
Bir cihaz yapılandırma profili için bir PowerShell Betiği eklediğinizde, betik, 32-bit, 64-bit işletim sistemlerinde bile her zaman yürütür. Bu güncelleştirme ile bir yönetici komut dosyası bir 64 bit PowerShell ana bilgisayar 64 bit cihazlarda çalıştırabilirsiniz (**cihaz Yapılandırması** > **PowerShell betikleri**  >   **Ekleme** > **yapılandırma** > **64 bit PowerShell konağı betiği**).
PowerShell kullanma hakkında daha fazla ayrıntı için bkz. [ıntune'da PowerShell betiklerini](intune-management-extension.md).
Uygulama hedefi: Windows 10 ve üzeri

### <a name="rename-an-enrolled-windows-device----1911112----"></a>Kayıtlı Windows cihazı yeniden adlandır <!-- 1911112  -->
Kayıtlı Windows 10 cihazı yeniden adlandırmak mümkün olacaktır (RS4 veya üzeri). Yapmak için **Intune** > **cihazları** > **tüm cihazlar** > bir cihaz seçin > **yeniden adlandırma cihaz**.

### <a name="assign-scep-certificates-to-a-userless-macos-device-------2340521-----"></a>SCEP sertifikaları için bir Kullanıcısız macOS cihaz atama    <!-- 2340521   -->
Basit sertifika kayıt Protokolü (SCEP) sertifikaları için bir Kullanıcısız macOS cihaz atayın ve sertifika, Wi-Fi veya VPN profilleri ile ilişkilendirmek mümkün olacaktır. Bu zaten sahibiz için mevcut desteği genişletir [sertifikaları Windows, iOS ve Android çalıştıran kullanıcısı olmayan cihazlara atamak](certificates-scep-configure.md#create-a-scep-certificate-profile).

### <a name="intune-conditional-access-ui-update------2432313----"></a>Intune koşullu erişim kullanıcı arabirimini güncelleştirme   <!-- 2432313  -->
Intune konsolunda koşullu erişim için kullanıcı Arabirimi için geliştirmeler yapıyoruz. Bunlar:
- Intune değiştirin *koşullu erişim* dikey penceresinden Azure Active Directory içeren dikey pencere. Bu, çeşitli ayarları ve yapılandırmaları olan bir Azure AD teknoloji kalır koşullu erişim için erişebilirsiniz sağlar.
- Dışında yeniden konumlandırmakta *Exchange hizmeti Bağlayıcısı* şu anda nedir için Kurulum *şirket içi erişim* dikey penceresi. Biz de bu dikey pencereyi yeniden adlandırıyorsunuz *Exchange erişimi*. Bu değişiklik, yapılandırma ve izleme için Exchange online ve şirket içi ilgili ayrıntıları birleştirecek.

### <a name="intune-will-leverage-google-play-protect-apis-on-android-devices----2577355----"></a>Intune, Android cihazlarda Google Play koruma API'lerini özelliğinden yararlanır <!-- 2577355  -->
Bazı BT yöneticileri, bir KCG yatay, burada son kullanıcıların kök dizini değiştirme veya jailbreaking, cep telefonu sonlandırabiliriz kalmaktadır. Bu davranış, bazen de hatalı niyetli olsa da, son kullanıcı cihazlarında kuruluşunuzun verilerini korumak için ayarlanan birçok Intune ilkeleri, bir geçiş sonuçlanır. Bu nedenle, Intune kayıtlı ve kayıtsız cihazlar için kök ve jailbreak uygulanmasını algılama sağlar. Bu sürümle birlikte, Intune artık Google Play koruma kayıtlı olmayan cihazlar için mevcut bizim kök algılama denetimleri eklemek için API'leri özelliğinden yararlanır. Google oluşan kök algılama denetimlerin tamamen paylaşmaz, ancak kullanıcılar, cihazlarını daha yeni işletim sistemi güncelleştirmelerini eski cihazlarda alabilmek için herhangi bir nedenle cihaz özelleştirmesinde kökü algılamak için bu API'leri bekliyoruz. Bu kullanıcılar daha sonra kurumsal verilere erişimi engellenebilir veya Kurumsal hesaplarını etkin ilke uygulamalarından silinecek. Ek değer, BT yöneticisinin Intune uygulama koruması dikey penceresi içinde çeşitli raporlama güncelleştirmeler artık sahip - "Bayrak eklenen kullanıcılar" raporu hangi kullanıcıların algılanan gösterir Google Play Protect'ın SafetyNet API tarama ile rapor "potansiyel olarak zararlı uygulamalar" olacaktır hangi uygulamaların Google'nın doğrulayın uygulamaları tarama API aracılığıyla algılanan gösterir. Bu özellik, Android'de kullanılabilir. 

### <a name="win32-app-information-available-in-troubleshooting-blade----2617342------"></a>Win32 uygulama bilgileri sorun giderme dikey penceresinde kullanılabilir <!-- 2617342    -->
Intune uygulama için bir Win32 uygulaması yükleme hatası günlük dosyalarını toplamak mümkün olacaktır **sorun giderme** dikey penceresi. Uygulama yükleme sorunlarını giderme hakkında daha fazla bilgi için bkz. [uygulaması yükleme sorunlarını giderme](troubleshoot-app-install.md).

### <a name="kiosk-browser-and-microsoft-edge-browser-apps-can-run-on-windows-10-devices-in-kiosk-mode----2935135----"></a>Bilgi noktası tarayıcı ve Microsoft Edge tarayıcı uygulamaları, bilgi noktası modu, Windows 10 cihazlarında çalıştırabilirsiniz <!-- 2935135  -->
Bir uygulama ya da birden fazla uygulama çalıştırmak için Windows 10 cihazları bilgi noktası modunda kullanabilirsiniz. Bu güncelleştirme, bilgi noktası modunda tarayıcı uygulamalarında kullanmanın bazı değişiklikler içerir. dahil olmak üzere:

- Microsoft Edge tarayıcı veya bilgi noktası cihazı uygulamaları çalıştırmak için bilgi noktası tarayıcı ekleyin (**cihaz Yapılandırması** > **profilleri** > **yeni profili**  >  **Windows 10 ve üzeri** Platform > **bilgi noktası** profil türü için).
- Bilgi noktası modunda çalıştırmak için veya açılamıyor için Microsoft Edge kısıtlama (**cihaz Yapılandırması** > **profilleri** > **yeni profili**  >  **Windows 10 ve üzeri** Platform > **cihaz kısıtlamaları** profil türü için > **Microsoft Edge tarayıcı**). Bilgi noktası modunda çalıştırmak değil, Microsoft Edge ayarlarını son kullanıcılar tarafından değiştirilebilir.

Geçerli ayarların listesi için bkz:

- [Windows 10 ve üzeri cihaz ayarları bir bilgi noktası çalıştırmak için](kiosk-settings-windows.md)
- [Microsoft Edge tarayıcı cihaz kısıtlamaları](device-restrictions-windows-10.md#microsoft-edge-browser)

Uygulama hedefi: Windows 10 ve üzeri

### <a name="auto-assign-scope-tags-to-resources-created-by-an-admin-with-that-scope----3173823----"></a>Kapsam etiketleri, kapsamlı bir yönetici tarafından oluşturulan kaynakları için otomatik olarak ata <!-- 3173823  -->
Yönetici kaynak oluşturduğunda, bu yeni kaynaklara Yönetim için atanan bir kapsam etiketleri otomatik olarak atanır.

### <a name="new-device-restriction-settings-for-ios-and-macos-devices----3448774---"></a>İOS ve macOS cihazları için yeni cihaz kısıtlama ayarları <!-- 3448774 -->
Bazı ayarları ve iOS ve macOS çalıştıran cihazlarda özellikleri kısıtlamak (**cihaz Yapılandırması** > **profilleri** > **yeni profili**  >  **iOS** veya **macOS** Platform > **cihaz kısıtlamaları** profil türü için). Bu güncelleştirme, daha fazla özellik ve ayar ekran saat, Esım ayarları ve yazılım güncelleştirmeleri, içeriği önbelleğe alma, engelleme kullanıcının görünürlüğünü geciktirme hücresel planları, değiştirme ve daha fazlası dahil olmak üzere kontrol edebilirsiniz ayarlara ekler.
Erişimi, ayarları ve geçerli özellikleri görmek için bkz:
- [iOS cihaz kısıtlama ayarları](device-restrictions-ios.md)
- [macOS cihaz kısıtlama ayarları](device-restrictions-macos.md)

Uygulama hedefi:
- iOS
- Mac OS

### <a name="failed-enrollment-report-moves-to-the-device-enrollment-blade----3560202---"></a>Cihaz kaydı dikey penceresine başarısız kayıt rapor taşır <!-- 3560202 -->
**Başarısız kayıtları** rapor taşınır **İzleyici** bölümünü **cihaz kaydı** dikey penceresi. İki yeni sütun (kayıt yöntemi ve işletim sistemi sürümü) de eklenir.

### <a name="change-kiosk-to-dedicated-devices----3598402----"></a>"Bilgi noktası" Değiştir "İçin adanmış cihazlar" <!-- 3598402  -->
Android ifadeyle hizalamak için **bilgi noktası** değiştirilecek **adanmış cihazlar** cihaz yapılandırma profilleri altında **Android Kurumsal**  >   **Cihaz sahibi** > **cihaz kısıtlamaları**.

### <a name="safari-and-delaying-user-software-update-visibility-ios-settings-are-moving-in-the-intune-ui----3640850--3803313----"></a>Görünürlük iOS ayarları Intune kullanıcı Arabiriminde taşıyor Safari ve geciktirme kullanıcı yazılım güncelleştirme <!-- 3640850, , 3803313  -->
İOS cihazları için Safari ayarlarını ve yazılım güncelleştirmelerini yapılandırma. Bu güncelleştirmede, bu ayarlar, Intune kullanıcı arabiriminin farklı bölümlerine taşınıyor:

- Safari ayarları taşıma kaynağı **Safari** (**cihaz Yapılandırması** > **profilleri** > **yeni profili**  >  **iOS** Platform > **cihaz kısıtlamaları** profil türü için) için **yerleşik uygulamaları**. 
- **Denetimli iOS cihazları için kullanıcı yazılım güncelleştirme görünürlüğü geciktirme** ayarı (**yazılım güncelleştirmelerini** > **güncelleştirme ilkelerini iOS için**) içintaşıma **Cihaz kısıtlamaları** > **genel**.

Geçerli ayarların listesi için bkz. [iOS cihaz kısıtlamaları](device-restrictions-ios.md) ve [iOS yazılım güncelleştirmeleri](software-updates-ios.md).

Uygulama hedefi: 
- iOS

### <a name="enabling-restrictions-in-the-device-settings-is-renamed-to-screen-time-on-ios-devices----3699164----"></a>Cihaz ayarlarında kısıtlamaları etkinleştirme ekran süresini iOS cihazlarında yeniden adlandırılır <!-- 3699164  -->
Yapılandırabileceğiniz **cihaz ayarlarında kısıtlamaları etkinleştirme** üzerinde iOS cihazlarının denetimli (**cihaz Yapılandırması** > **profilleri**  >  **Yeni profili** > **iOS** Platform > **cihaz kısıtlamaları** profil türü için > **genel**). Bu güncelleştirmede, bu ayarı olarak yeniden adlandırıldı **ekran (yalnızca denetimli) zaman**. Aynı durum geçerlidir. Özellikle: 

- iOS 11.4.1 ve önceki sürümleri: **Blok** son kullanıcıların cihaz ayarlarında kısıtlamaları kendi ayarından engeller. 
- iOS 12.0 ve daha sonra: **Blok** son kullanıcılar kendi önlenmiş **ekran zaman** cihaz ayarlarında, içerik ve gizlilik kısıtlamaları da dahil olmak üzere. İOS 12.0 yükseltilmiş cihazları, cihaz ayarlarında kısıtlamaları sekmesinde artık görmezsiniz. Bu ayarlar **ekran zaman**. 

Geçerli ayarların listesi için bkz. [iOS cihaz kısıtlamaları](device-restrictions-ios.md).

Uygulama hedefi: 
- iOS

### <a name="app-status-details-for-ios-apps----3761235----"></a>İOS uygulamaları için uygulama durumu ayrıntıları <!-- 3761235  -->
Yeni uygulama yükleme hata iletileri için aşağıdaki ilgili olacaktır:
- Paylaşılan iPad üzerinde yüklerken VPP uygulamaları için hata
- App Store'da devre dışı bırakıldığında hatası
- Uygulama için VPP lisans bulunamadı hatası
- MDM sağlayıcısıyla sistemi uygulamaları yükleme hatası
- Cihaz kayıp modu veya bilgi noktası modunda olduğunda, uygulama yükleme hatası
- Kullanıcı için App Store oturum açmamış, uygulama yükleme hatası

Intune'da seçin **istemci uygulamaları** > **uygulamaları** > "Uygulama adı" > **cihaz yükleme durumu**. Yeni hata iletileri de kullanılabilir olacak **durumu ayrıntıları** sütun.

<!-- 1901 start -->

### <a name="deployment-of-online-licensed-microsoft-store-for-business-apps----1672660----"></a>İş uygulamalarına yönelik çevrimiçi lisanslı Microsoft Store dağıtımı <!-- 1672660  -->
Gerekli çevrimiçi lisanslı Microsoft Store cihaz bağlamında kurumsal uygulamalar için atayamazsınız olacaktır. Bu şekilde bir iş uygulaması için Microsoft Store dağıtımı, cihazdaki tüm kullanıcılar için yüklenecek uygulamayı etkinleştirir. Bu yalnızca Windows 10 RS4 + Masaüstü cihazları için geçerlidir. Cihaz bağlamında yükleme seçeneği, istemci uygulamaları atama sayfasında MSFB çevrimiçi lisanslı uygulamaları için kullanılabilir.

<!-- 1812 start -->

### <a name="android-enterprise-app-we-app-deployment----1171203---"></a>Android Kurumsal uygulama-BİZ uygulama dağıtımı <!-- 1171203 -->
Bir kayıtlı olmayan uygulama koruma İlkesi kayıt olmadan Android cihazlar için (APP-BİZ) dağıtım senaryosu, şunları yapabileceksiniz yönetilen Google Play mağazası uygulamalarını dağıtma ve LOB uygulamaları kullanıcılara için kullanılacak. Özellikle, BT'nin son kullanıcılara cihazlarının güvenlik duruşunu bilinmeyen kaynaklardan yüklemeleri vererek çözmek, son kullanıcılar artık gerektiren bir uygulama kataloğu ve yükleme deneyimi sağlamak. Ayrıca, bu dağıtım senaryosu bir geliştirilmiş son kullanıcı deneyimi sağlar.

### <a name="intune-policies-update-authentication-method-and-company-portal-app-installation-----1927359---"></a>Intune ilkeleri, kimlik doğrulama yöntemi ve şirket Portalı Uygulama yüklemesi güncelleştirme  <!-- 1927359 -->
Kurulum Yardımcısı ile Apple'nın Kurumsal cihaz kayıt yöntemleri biri aracılığıyla kayıtlı cihazlarda, el ile uygulama Mağazası'ndan son kullanıcılar tarafından yüklendiğinde, Intune Şirket portalı artık destekleyecektir. Bu değişiklik, yalnızca kayıt sırasında Apple Kurulum Yardımcısı ile doğrulandığında geçerlidir. Bu değişiklik, yalnızca aracılığıyla kaydedilmiş iOS cihazları etkiler:  
* Apple configurator
* Apple İşletme Yöneticisi
* Apple School Manager
* Apple aygıt kayıt programı (DEP)

Kullanıcıların uygulama Mağazası'ndan Şirket portalı uygulamasını yüklediğinizde ve onun üzerinden bu cihazları kaydetmek deneyin, bunlar bir hatayla karşılaşırsınız. Bu cihazlar, bu, otomatik olarak, kayıt sırasında Intune tarafından gönderildiğinde yalnızca şirket portalını kullanması beklenen. Azure portalında ıntune'da kayıt profilleri, cihazların kimliklerini nasıl doğrulayacaklarını belirtebilirsiniz ve Şirket portalı uygulaması'na alırsanız güncelleştirilecektir. DEP cihaz kullanıcılarınız Şirket portalı olmasını istiyorsanız, tercihlerinizi bir kayıt profili belirtmeniz gerekir. Ayrıca, **Cihazınızı tanımlamanız** Şirket portalı uygulamasında ekran yakında geçersiz olacak.  
Zaten kayıtlı DEP cihazlarında şirket Portalı'nı yüklemek için Intune'a gitmeniz gerekir > istemci uygulamaları ve uygulama yapılandırma ilkeleriyle yönetilen bir uygulama olarak gönderin. Bu adımların hakkında ayrıntılı bilgi gelecekteki belgelere renkle gösterilir.

### <a name="administrative-templates-are-in-public-preview-and-moved-to-their-own-configuration-profile----3322847---"></a>Yönetim Şablonları genel Önizleme aşamasındadır ve kendi yapılandırma profiline taşınır <!-- 3322847 -->
Intune Yönetim Şablonları (**cihaz Yapılandırması** > **Yönetim Şablonları**) şu anda özel Önizleme aşamasındadır. Bu güncelleştirme ile: Yönetim Şablonları, Intune'da yönetilebilir 300 ayarları içerir. Daha önce bu ayarlar, yalnızca Grup İlkesi Düzenleyicisi'nde vardı.
Yönetim Şablonları genel önizlemede Yönetim Şablonları hareket etmesini **cihaz Yapılandırması** > **Yönetim Şablonları** için **cihaz Yapılandırma** > **profilleri** >**profili oluşturma** > içinde **Platform**, seçin  **Windows 10 ve üzeri**, **profil türü**, seçin **Yönetim Şablonları**.
Raporlama etkinse geçerlidir: Windows 10 ve üzeri

### <a name="intune-macos-company-portal-dark-mode----3300524---"></a>Intune macOS Şirket portalı koyu modu <!-- 3300524 -->
Intune macOS Şirket portalı, macOS için artık koyu modunu destekler. Bir macOS 10.14 + cihazda koyu modunu etkinleştirdiğinizde, Şirket portalı görünümünü mod yansıtan renkleri için ayarlanır.

<!-- 1809 start -->  

### <a name="app-protection-policy-app-settings-for-web-data----2662995---"></a>Web verileri için Uygulama Koruma İlkesi (APP) ayarları <!-- 2662995 -->
Gerek Android gerekse iOS cihazlarında Web içeriği için uygulama ilke ayarları, gerek http gerekse https Web bağlantılarını, ayrıca iOS Evrensel Bağlantıları ve Android Uygulama Bağlantıları aracılığıyla veri aktarımını daha iyi işleyecek şekilde güncelleştirilecektir.  

<!-- 1808 start -->

### <a name="apple-vpp-token-used-by-another-mdm----1488946---"></a>Başka bir MDM tarafından kullanılan Apple VPP belirteci <!-- 1488946 -->
Bir Apple toplu satın alınan program (VPP) belirteci hem Intune hem de başka bir MDM tarafından kullanıldığında Intune bunu algılayacak ve ayrıntıları gösterecek.

### <a name="retired-devices-in-the-device-compliance-dashboard----1981119---"></a>Cihaz uyumluluk panosunda kullanımdan kaldırılan cihazlar <!-- 1981119 -->
Gelecek bir güncelleştirme ile kullanımdan kaldırılan cihazlar uyumluluk panosundan da kaldırılacak. Bu durum, uyumluluk numaralarınızı değiştirecek.

## <a name="notices"></a>Bildirimler

Şu anda etkin bildirim yok.

### <a name="see-also"></a>Ayrıca bkz.
Son geliştirmelere ilişkin ayrıntılar için bkz. [Microsoft Intune’daki Yenilikler](whats-new.md).