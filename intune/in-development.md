---
title: Geliştirme-Microsoft Intune
titleSuffix: ''
description: Geliştirmede Microsoft Intune Özellikler
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/30/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6ab2e258553c049223806ddf199976c84ff6bcba
ms.sourcegitcommit: 89a973bbfa1702b2d275af6814874e4305bdcb77
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2019
ms.locfileid: "71140683"
---
# <a name="in-development-for-microsoft-intune---september-2019"></a>Microsoft Intune için geliştirme sırasında-Eylül 2019

Hazırlık ve planlamada yardımcı olması için, bu sayfada Intune Kullanıcı Arabirimi güncelleştirmeleri ve geliştirme aşamasında olan ancak henüz yayınlanmayan özellikler listelenir. Buna ek olarak:

- Bir değişiklikten önce işlem yapmanız gerektiğini düşünüyorsanız, tamamlayıcı bir Office Ileti merkezi gönderisini yayımlayacağız.
- Bir özellik üretimde başlatıldığında, önizleme veya genel kullanıma açık olarak, özellik açıklaması bu sayfayı ve yenilikler [sayfasına](whats-new.md)taşınır.
- Bu sayfa ve yenilikler [sayfası](whats-new.md) düzenli aralıklarla güncelleştirilir. Ek güncelleştirmeleri daha sonra denetleyin.
- Stratejik teslim edilebilirler ve zaman çizelgeleri için [M365 yol haritasını](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS) inceleyin.

> [!Note]
> Bu öğeler, gelecek sürümlerde sunulan Intune özellikleri hakkında Microsoft 'un geçerli beklentilerini yansıtır. Tarihler ve bireysel Özellikler değişebilir. Geliştirmede tüm öğelerin bu sayfada bir özellik açıklaması yoktur.

**RSS akışı**: Aşağıdaki URL 'YI kopyalayıp akış okuyucunuzun içine yapıştırarak Bu sayfa güncelleştirildikten sonra bildirim alın:`https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`

<!--
## What's coming to Intune in the Azure portal 
## What's coming to Intune apps
## Notices
-->

<!-- Common categories:  
#### App management
#### Device configuration
#### Device enrollment
#### Device management
#### Intune apps
#### Monitor and troubleshoot
#### Role-based access control
#### Security

-->
 
<!-- ***********************************************-->
## <a name="app-management"></a>Uygulama yönetimi

### <a name="managed-google-play-private-lob-apps----1464182----"></a>Yönetilen Google Play özel LOB uygulamaları <!-- 1464182  -->
Intune, BT yöneticilerinin Intune konsoluna katıştırılmış bir iframe aracılığıyla özel Android LOB uygulamalarını yönetilen Google Play yayımlamasına izin verir.  Şu anda, BT yöneticilerinin birçok adım gerektiren ve çok zaman tüketen, LOB uygulamalarını doğrudan Google Play yayımlama konsoluna yayımlaması gerekir.  Bu yeni özellik, Intune konsolundan ayrılmak zorunda kalmadan LOB uygulamalarının en az bir adım kümesiyle kolayca yayımlanmasını sağlar.  Yönetilen Google Play kullanan Android kurumsal yönetim senaryolarından herhangi biri bu özellikten yararlanabilir (iş profili, adanmış, tam olarak yönetilen ve kayıtlı olmayan cihazlar).  Intune 'da, **istemci uygulamaları** > **uygulamalar** > **Ekle**' yi seçin. Ardından, **uygulama türü** listesinden **yönetilen Google Play** ' yi seçin. Yönetilen Google Play uygulamalar hakkında daha fazla bilgi için bkz. [Intune Ile Android Enterprise cihazlarına yönetilen Google Play uygulamaları ekleme](apps-add-android-for-work.md).

### <a name="company-portal-app-installation-status-messages----2514416----"></a>Uygulama yükleme durum iletilerini Şirket Portalı <!-- 2514416  -->
Şirket Portalı uygulama son kullanıcılara ek uygulama yükleme durumu iletileri gösterecektir. Yeni Win32 bağımlılık özellikleri için aşağıdaki koşullar geçerli olacaktır:
- Uygulama yüklenemedi. Yönetici tarafından tanımlanan bağımlılıklar karşılanmadı.
- Uygulama başarıyla yüklendi, ancak yeniden başlatma gerekiyor.
- Uygulama yükleme sürecinde, ancak devam etmek için yeniden başlatma gerekiyor.

### <a name="managed-google-play-iframe-support----2871756----"></a>Yönetilen Google Play iFrame desteği <!-- 2871756  -->
Intune, yönetilen Google Play iframe 'i aracılığıyla doğrudan Intune konsolunda Web bağlantıları ekleme ve yönetme desteği sağlar.  Bu, BT yöneticilerinin bir URL ve simge grafiği göndermesini sağlar ve ardından bu bağlantıları düzenli Android uygulamaları gibi cihazlara dağıtır. Yönetilen Google Play kullanan Android kurumsal yönetim senaryolarından herhangi biri bu özellikten yararlanabilir (iş profili, adanmış, tam olarak yönetilen ve kayıtlı olmayan cihazlar).  Intune 'da, **istemci uygulamaları** > **uygulamalar** > **Ekle**' yi seçin. Ardından, **uygulama türü** listesinden **yönetilen Google Play** ' yi seçin. Yönetilen Google Play uygulamalar hakkında daha fazla bilgi için bkz. [Intune Ile Android Enterprise cihazlarına yönetilen Google Play uygulamaları ekleme](apps-add-android-for-work.md).

### <a name="macos-support-for-vpp-apps----3173501----"></a>VPP uygulamaları için macOS desteği <!-- 3173501  -->
Apple Business Manager 'ı kullanarak satın aldığınız macOS uygulamaları, Apple VPP belirteçleri Intune 'da eşitlendiğinde konsolunda görüntülenir. Konsolunu kullanarak, gruplar için cihaz ve Kullanıcı tabanlı lisanslar atayabilir, iptal edebilir ve yeniden atayabilirsiniz. Microsoft Intune, şirketinizde kullanılmak üzere satın alınan VPP uygulamalarını şu şekilde yönetmenize yardımcı olur:
- Uygulama mağazasından lisans bilgilerini raporlama.
- Kaç lisans kullandığınızı izleme.
- Uygulamanın sahip olduğunuzdan daha fazla kopyasını yüklemenizi engelleme.
Intune ve VPP hakkında daha fazla bilgi için bkz. [Microsoft Intune ile toplu satın alınan uygulamaları ve kitapları yönetme](vpp-apps.md).

### <a name="macos-support-for-web-apps----3174427----"></a>Web uygulamaları için macOS desteği <!-- 3174427  -->
MacOS Şirket Portalı kullanarak, Web üzerinde bir URL 'ye kısayol eklemenize olanak sağlayan Web Apps 'i yükleyebilirsiniz. Son kullanıcılar, macOS Şirket Portalı bir Web uygulaması için uygulama ayrıntıları sayfasından **Install** eylemine erişebilir. **Web bağlantısı** uygulama türü hakkında daha fazla bilgi için bkz. [Microsoft Intune uygulama ekleme](apps-add.md).

#### <a name="assign-microsoft-edge-beta-for-macos----4678761----"></a>MacOS için Microsoft Edge Beta ata <!-- 4678761  -->
MacOS cihazları için Microsoft Edge Beta 'nın en son sürümünü Intune 'a ekleyebilir ve atayabilirsiniz. Intune 'da, **istemci uygulamaları** > **uygulamalar** > **uygulama** > Ekle**Microsoft Edge-MacOS**' u seçin. Ardından, Microsoft Edge Beta 'yı amaçlanan gruplara atayın. Microsoft otomatik güncelleştirme (MAU), Microsoft Edge 'i güncel tutar. Microsoft Edge hakkında daha fazla bilgi için, [Microsoft Intune Ile Microsoft Edge kullanarak Web erişimini yönetme](manage-microsoft-edge.md)makalesine bakın.

### <a name="read-and-write-graph-api-operations-for-intune-apps----5031704----"></a>Intune uygulamaları için okuma ve yazma Graph API işlemleri <!-- 5031704  -->
Uygulamalar, Kullanıcı kimlik bilgileri olmadan uygulama kimliği 'ni kullanarak hem okuma hem de yazma işlemleri ile Intune Graph API çağırabilecektir. Intune için Microsoft Graph API 'sine erişme hakkında daha fazla bilgi için, bkz. [Microsoft Graph Intune Ile çalışma](https://docs.microsoft.com/graph/api/resources/intune-graph-overview?view=graph-rest-1.0).

### <a name="configure-app-notification-content-for-organization-accounts----2576686---"></a>Kuruluş hesapları için uygulama bildirim içeriğini yapılandırma <!-- 2576686 -->
Android ve iOS cihazlarında Intune uygulama koruma ilkeleri (uygulama), kuruluş hesapları için uygulama bildirim içeriğini denetlemenize olanak tanır. Bu özellik, uygulamalardan destek isteyecek ve UYGULAMANıN etkin olduğu tüm uygulamalarda kullanılamayabilir. UYGULAMA hakkında daha fazla bilgi için bkz. [Uygulama koruma ilkeleri nelerdir?](app-protection-policy.md).

### <a name="available-google-play-app-reporting-for-android-work-profiles----3041956----"></a>Android iş profilleri için kullanılabilir Google Play uygulama raporlaması <!-- 3041956  -->
Android iş profili cihazlarına kullanılabilir uygulama yüklemeleri için, uygulama yükleme durumunu ve yönetilen Google Play uygulamalarının yüklü sürümünü görüntüleyebilirsiniz. Daha fazla bilgi için bkz. [Uygulama koruma ilkelerini izleme](app-protection-policies-monitor.md), [Android Iş profili cihazlarını Intune ile yönetme](android-enterprise-overview.md) ve [uygulama türü ile yönetilen Google Play](apps-add-android-for-work.md#managed-google-play-app-type).

<!-- ***********************************************-->
## <a name="device-configuration"></a>Cihaz yapılandırması

### <a name="device-features-device-restrictions-and-extension-profiles-for-ios-and-macos-settings-are-shown-by-enrollment-type----4886161----"></a>İOS ve macOS ayarları için cihaz özellikleri, cihaz kısıtlamaları ve uzantı profilleri kayıt türüne göre gösteriliyor <!-- 4886161  -->

Intune 'da iOS ve MacOS cihazları için**profiller oluşturursunuz (**  > **cihaz yapılandırma** > **profilleri** > **iOS** veya **MacOS** for platform > **cihaz özellikleri** , **Cihaz kısıtlamaları**veya profil türü **uzantıları** ). Şu anda, bu profillerdeki kullanılabilir ayarlar listelenir. 

Gelecekteki bir güncelleştirmede, Intune portalındaki kullanılabilir ayarlar, uygulanan kayıt türüne göre kategorize edilir:

- iOS
  - Tüm kayıt türleri
  - Cihaz kaydı ve otomatik cihaz kaydı
  - Otomatik cihaz kaydı

- Mac OS
  - Tüm kayıt türleri
  - Cihaz kaydı
  - Kullanıcı onaylı ve otomatik cihaz kaydı
  - Otomatik cihaz kaydı

Şunun için geçerlidir:

- iOS
  - [Cihaz özellikleri](ios-device-features-settings.md)
  - [Cihaz kısıtlamaları](device-restrictions-ios.md)

- Mac OS
  - [Cihaz özellikleri](macos-device-features-settings.md)
  - [Cihaz kısıtlamaları](device-restrictions-macos.md)
  - [Uzantıları](kernel-extensions-settings-macos.md)

### <a name="new-voice-control-settings-for-supervised-ios-devices-running-in-kiosk-mode----4892835----"></a>Denetimli iOS cihazları için bilgi noktası modunda çalışan yeni ses denetimi ayarları <!-- 4892835  -->

Intune 'da denetimli iOS cihazlarını bir bilgi noktası veya adanmış cihaz olarak çalıştırmak için ilkeler oluşturabilirsiniz (**cihaz yapılandırma** > **profilleri** > platform için**profil** > oluşturma**iOS** >> **bilgi noktası (yalnızca denetimli)** profil türü için cihaz kısıtlamaları. 

Gelecekteki bir güncelleştirmede, denetleyebilmeniz için yeni ayarlar olacaktır:

- **Ses denetimi**: Bilgi noktası modundayken cihazda ses denetimini mümkün değildir.
- **Ses denetimi değişikliği**: Kullanıcıların, bilgi noktası modundayken cihazdaki ses denetimi ayarını değiştirmesine izin verin.

Geçerli ayarları görmek için [IOS bilgi noktası (yalnızca denetimli) ayarları](device-restrictions-ios.md#kiosk-supervised-only)' na gidin.

Şunun için geçerlidir:

- iOS 13,0 ve üzeri

### <a name="use-single-sign-on-for-apps-and-websites-on-your-ios-and-macos-devices----4893175----"></a>İOS ve macOS cihazlarınızdaki uygulamalar ve Web siteleri için çoklu oturum açma kullanın <!-- 4893175  -->
Gelecekteki bir güncelleştirmede iOS ve MacOS cihazları için yeni bir çoklu oturum açma ayarları bulunur (**cihaz yapılandırma** > **profilleri** > **iOS** veya **MacOS** **profili oluşturma** >  Platform > profil türü için **cihaz özellikleri** ).

Özellikle de Kerberos kimlik doğrulaması kullanan uygulamalar ve Web siteleri için çoklu oturum açma deneyimi yapılandırmak üzere bu ayarları kullanın. Genel kimlik bilgisi çoklu oturum açma uygulaması uzantısı ve Apple 'ın yerleşik Kerberos uzantısı arasında seçim yapabilirsiniz.

Yapılandırabileceğiniz geçerli cihaz özelliklerini görmek için [iOS cihaz özelliklerine](ios-device-features-settings.md) ve [MacOS cihaz özelliklerine](macos-device-features-settings.md)gidin.

Şunun için geçerlidir:

- iOS 13,0 ve üzeri
- macOS 10,15 ve üzeri

### <a name="associate-domains-to-apps-on-macos-1015-devices----4898079----"></a>MacOS 10.15 + cihazlarında etki alanlarını uygulamalarla ilişkilendirme <!-- 4898079  -->
MacOS cihazlarında, farklı özellikler yapılandırabilir ve bu özellikleri bir ilke kullanarak cihazlarınıza gönderebilirsiniz (**cihaz yapılandırma** > **profilleri** > **profil** > oluşturma**MacOS** Platform > profil türü için **cihaz özellikleri** ). Gelecekteki bir güncelleştirmede, etki alanlarını uygulamalarınızla ilişkilendirebileceksiniz. Bu özellik, uygulama ile ilgili web siteleriyle kimlik bilgilerinin paylaşılmasını sağlar ve Apple 'ın çoklu oturum açma uzantısı, evrensel bağlantılar ve parola otomatik doldurma ile kullanılabilir. 

Yapılandırabileceğiniz geçerli özellikleri görmek için [Intune 'Da MacOS cihaz özelliği ayarları](macos-device-features-settings.md)' na gidin.

Şunun için geçerlidir:

- macOS 10,15 ve üzeri

### <a name="use-itunes-and-apps-in-the-itunes-app-store-url-when-showing-or-hiding-apps-on-ios-supervised-devices----4928474----"></a>İOS denetimli cihazlarda uygulamaları gösterirken veya gizlerken iTunes App Store URL 'sindeki "iTunes" ve "Apps" kullanın <!-- 4928474  --> 
Intune 'da, denetimli iOS cihazlarınızda uygulamaları göstermek veya gizlemek için ilkeler oluşturabilirsiniz (**cihaz yapılandırma** > **profilleri** > platform > cihaz için**profil** > oluşturma**iOS**profil türü kısıtlamaları > **uygulamaları göster veya gizle (yalnızca denetimli)** ). 

İTunes App Store URL `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8`'sini (gibi) girebilirsiniz. Gelecekteki bir güncelleştirmede, hem `apps` `itunes` hem de URL 'de kullanabilirsiniz, örneğin:

- `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8`
- `https://apps.apple.com/us/app/work-folders/id950878067?mt=8`

Bu ayarlar hakkında daha fazla bilgi için bkz. [uygulamaları gösterme veya gizleme (yalnızca denetimli)](device-restrictions-ios.md#show-or-hide-apps-supervised-only).

Şunun için geçerlidir:

- iOS

### <a name="support-for-ikev2-vpn-profiles-for-ios----1943438---"></a>İOS için IKEv2 VPN profilleri desteği <!-- 1943438 -->
Ikev2 protokolünü kullanarak iOS Native VPN istemcisi için VPN profilleri oluşturabileceksiniz. Ikev2, **cihaz yapılandırma** > **profillerinde** > yeni bir bağlantı türüdür, profil türü > **ayarları**için **VPN** > Platform için**iOS** **oluşturun** > .

Bu VPN profilleri, yerel VPN istemcisini yapılandırır. Bu nedenle, yönetilen cihazlara yüklenmiş veya hiçbir VPN istemci uygulaması gönderilmez. Bu özellik cihazların Intune 'A (MDM kaydı) kaydedilmesini gerektirir.

Yapılandırabileceğiniz geçerli VPN ayarlarını görmek için [Microsoft Intune iOS CIHAZLARıNDA VPN ayarlarını yapılandırma](vpn-settings-ios.md)bölümüne gidin.

Şunun için geçerlidir: iOS


<!-- ***********************************************-->
## <a name="device-enrollment"></a>Cihaz kaydı

### <a name="new-tenants-will-default-away-from-android-device-administrator-management----4869790----"></a>Yeni kiracılar varsayılan olarak Android Cihaz Yöneticisi yönetiminden uzaklaşacaktır <!-- 4869790  -->
Android 'in Cihaz Yöneticisi özellikleri, Android Enterprise tarafından değiştirildi. Bu nedenle, bunun yerine Android Enterprise 'ı yeni kayıtlar için kullanmanızı öneririz. Gelecekteki bir güncelleştirmede, yeni kiracıların Cihaz Yöneticisi yönetimini kullanmak için Android kaydında aşağıdaki önkoşul adımlarını tamamlaması gerekir: Cihaz yönetim >  >  > ayrıcalıklarıylaIntune cihaz kaydı Android kaydı kişisel ve şirkete ait cihazlara git cihaz kullanma >  **cihazları yönetmek için yönetici**.

Mevcut kiracılar ortamlarında hiçbir değişikliğe karşılaşmayacak. 

Intune 'da Android Cihaz Yöneticisi hakkında daha fazla bilgi için bkz. [Android Cihaz Yöneticisi kaydı](https://docs.microsoft.com/intune/android-enroll-device-administrator).

### <a name="for-ios-devices-customize-the-enrollment-process-privacy-screen-of-the-company-portal----4394993----"></a>İOS cihazları için Şirket Portalı kayıt işlemi gizlilik ekranını özelleştirin <!-- 4394993  -->
Marku kullanarak, son kullanıcıların iOS kaydı sırasında göreceği Şirket Portalı gizlilik ekranını özelleştirebileceksiniz. Özellikle, kuruluşunuzun cihazı göremeyecek veya cihaz üzerinde yapaamayacak işlerin listesini özelleştirebilirsiniz.

<!-- ***********************************************-->
## <a name="device-management"></a>Cihaz yönetimi

### <a name="deploy-software-updates-to-macos-devices----3194876---"></a>MacOS cihazlarına yazılım güncelleştirmeleri dağıtma <!-- 3194876 -->
MacOS cihazları gruplarına yazılım güncelleştirmeleri dağıtabileceksiniz. Bu özellik kritik, bellenim, yapılandırma dosyası ve diğer güncelleştirmeleri içerir. Güncelleştirmeleri bir sonraki cihaz iadede gönderebilecek veya zaman içinde güncelleştirmeleri dağıtmak için haftalık bir zamanlama seçebileceğiniz şekilde ayarlayabilirsiniz. Bu, standart çalışma saatleri dışında veya yardım masanıza tam olarak çalıştırıldığında cihazları güncelleştirmek istediğinizde yardımcı olur. Ayrıca güncelleştirmelerin dağıtıldığı tüm macOS cihazlarının ayrıntılı bir raporunu alırsınız. Belirli güncelleştirmelerin durumlarını görmek için, raporu cihaz başına temelinde inceleyebilirsiniz.

### <a name="send-custom-notifications-to-a-device----4928910----"></a>Cihaza özel bildirimler gönderme <!-- 4928910  -->
Şirket Portalı veya Intune uygulamasının yüklü olduğu belirli cihazlara özel bildirimler gönderebileceksiniz. Bunu yapmak için, **Intune** > **cihazlar** > **tüm cihazlar** > bir cihaz seçin > **daha fazla** > **özel bildirim gönder**' e gidin. 

### <a name="updates-to-android-enterprise-fully-managed-features----3464667-5227935-4062195-4631425-4631440---"></a>Android kurumsal tam olarak yönetilen özellikler için güncelleştirmeler <!-- 3464667, 5227935, 4062195, 4631425, 4631440 -->

Android tam olarak yönetilen cihazlar için aşağıdaki desteği ekleyeceğiz:

- Tam olarak yönetilen Android için SCEP sertifikaları, cihaz sahibi olarak yönetilen cihazlarda sertifika kimlik doğrulaması için kullanılabilir. SCEP sertifikaları Iş profili cihazlarında zaten destekleniyor.  Cihaz sahibi için SCEP sertifikalarıyla şunları yapabilirsiniz: <!-- 5227935 -->
    - Android Enterprise 'ın YAPıLACAKLAR bölümünde SCEP profili oluşturma
    - kimlik doğrulaması için SCEP sertifikalarını Wi-Fi profili için bağlama
    - kimlik doğrulaması için SCEP sertifikalarını VPN profillerine bağlama
    - kimlik doğrulaması için SCEP sertifikalarını e-posta profillerine bağlama (uygulama yapılandırması aracılığıyla)
- Sistem uygulamaları, Android kurumsal cihazlarda desteklenecektir. Intune 'da, **istemci uygulamaları** > **uygulamalar** > **Ekle**' yi seçerek bir Android kurumsal sistem uygulaması ekleyeceksiniz. **Uygulama türü** listesinde, **Android kurumsal sistem uygulaması**' nı seçin. Intune'a uygulamaları ekleme hakkında daha fazla bilgi için bkz. [Microsoft Intune'a uygulama ekleme](apps-add.md). <!-- 4062195 -->
- **Cihaz uyumluluğu** > **Android kurumsal** > **cihaz sahibi**bölümünde, Google SafetyNET kanıtlama düzeyini ayarlayan bir uyumluluk ilkesi oluşturabileceksiniz.   <!-- 4631425 -->
- Android kurumsal tam olarak yönetilen cihazlarda, mobil tehdit savunma sağlayıcıları desteklenecektir. **Cihaz uyumluluğu** > **Android kurumsal** > **cihaz sahibi**' de, kabul edilebilir tehdit düzeyi seçebilirsiniz. <!-- 4631440 --> [Intune kullanarak cihazları uyumlu veya uyumsuz olarak işaretlemek Için Android kurumsal ayarları](compliance-policy-create-android-for-work.md#device-owner) geçerli ayarları listeler.


Şunun için geçerlidir: 
- Android kurumsal tam yönetilen cihazlar

<!-- ***********************************************-->
## <a name="monitor-and-troubleshoot"></a>İzleme ve sorun giderme

### <a name="updated-support-experience-------5012398------"></a>Güncelleştirilmiş destek deneyimi   <!--  5012398    -->
Geliştirmeye devam etmenin bir parçası olarak, Intune için konsol içi destek deneyimini güncelleştiriyoruz.  Genel sorunlar için konsol içi aramayı ve geri bildirimleri geliştireceğiz ve desteğe başvurmak için iş akışını kolaylaştırıyoruz.     

<!-- ***********************************************-->
## <a name="security"></a>Güvenlik

### <a name="tamper-protection-for-windows-defender-antivirus-----4705448---------"></a>Windows Defender virüsten koruma için yetkisiz koruma  <!-- 4705448       -->
Intune 'un Windows Defender virüsten koruma için yönetebileceği ayarlara yetkisiz *koruma* ekleyeceğiz. Kullanılabilir korumayı açmak veya kapatmak için Windows 10 Endpoint Protection için bir cihaz yapılandırma profili kullanabileceksiniz.  Daha fazla koruma hakkında daha fazla bilgi için bkz. Windows belgelerindeki [güvenlik ayarlarını önleme korumasıyla](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection) değiştirme. 


<!-- ***********************************************-->
## <a name="notices"></a>Bildirimler

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

## <a name="see-also"></a>Ayrıca bkz.
Son geliştirmelere ilişkin ayrıntılar için bkz. [Microsoft Intune’daki Yenilikler](whats-new.md).




