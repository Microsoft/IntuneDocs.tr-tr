---
title: Geliştirme-Microsoft Intune
titleSuffix: ''
description: Geliştirmede Microsoft Intune Özellikler
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/30/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 969e7bc4804e1f66230c76d742bec2c67c2fa006
ms.sourcegitcommit: 99b74d7849fbfc8f5cf99cba33e858eeb9f537aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/31/2019
ms.locfileid: "68670940"
---
# <a name="in-development-for-microsoft-intune---august-2019"></a>Microsoft Intune için geliştirme sırasında-Ağustos 2019

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

### <a name="control-ios-app-uninstall-behavior-at-device-unenrollment----3504144---"></a>Cihaz kaydı kaldırılırken iOS uygulaması kaldırma davranışını denetleme <!-- 3504144 -->
Yöneticiler, cihazın bir kullanıcı veya cihaz grubu düzeyinde kaydı kaldırıldığında cihazda bir uygulamanın kaldırılıp kaldırılmadığını veya korunup korunmadığını yönetebilecektir. 

### <a name="categorize-microsoft-store-for-business-apps----3926922---"></a>Iş uygulamaları için Microsoft Store kategorilere ayırın <!-- 3926922 -->
Iş uygulamaları için Microsoft Store sınıflandırabileceksiniz. Bunu yapmak için **Intune** > **istemci uygulamaları** > **uygulamaları** ' nı seçin > bir Microsoft Store Business App > **uygulama bilgileri** > **kategorisi**seçin. Açılan menüden bir kategori atayın.
### <a name="configure-app-notification-content-for-organization-accounts----2576686---"></a>Kuruluş hesapları için uygulama bildirim içeriğini yapılandırma <!-- 2576686 -->
Android ve iOS cihazlarında Intune uygulama koruma ilkeleri (uygulama), kuruluş hesapları için uygulama bildirim içeriğini denetlemenize olanak tanır. Bu özellik, uygulamalardan destek isteyecek ve UYGULAMANıN etkin olduğu tüm uygulamalarda kullanılamayabilir. UYGULAMA hakkında daha fazla bilgi için bkz. [Uygulama koruma ilkeleri nelerdir?](app-protection-policy.md).

### <a name="available-google-play-app-reporting-for-android-work-profiles----3041956----"></a>Android iş profilleri için kullanılabilir Google Play uygulama raporlaması <!-- 3041956  -->
Android iş profili cihazlarına kullanılabilir uygulama yüklemeleri için, uygulama yükleme durumunu ve yönetilen Google Play uygulamalarının yüklü sürümünü görüntüleyebilirsiniz. Daha fazla bilgi için bkz. [Uygulama koruma ilkelerini izleme](app-protection-policies-monitor.md), [Android Iş profili cihazlarını Intune ile yönetme](android-enterprise-overview.md) ve [uygulama türü ile yönetilen Google Play](apps-add-android-for-work.md#managed-google-play-app-type).

<!-- ***********************************************-->
## <a name="device-configuration"></a>Cihaz yapılandırması

### <a name="some-unsupervised-ios-device-restrictions-will-become-supervised-only-with-the-ios-130-release----4867809----"></a>Denetlenmeyecek bazı iOS cihaz kısıtlamaları yalnızca iOS 13,0 sürümüyle denetimli olacak. <!-- 4867809  -->
Bazı ayarlar, iOS 13,0 sürümü ile yalnızca denetimli cihazlara uygulanır. Bu ayarlar şunlardır:

- Uygulama Mağazası, Belge Görüntüleme, Oyun
  - Uygulama mağazası
  - Açık iTunes, müzik, podcast veya News içeriği
  - Game Center arkadaş ekleme
  - Çok oyunculu oyun
- Yerleşik Uygulamalar
  - Kamera
    - FaceTime
  - Safari
    - İse
- Bulut ve Depolama
  - İCloud 'a yedekleme
  - İCloud Belge eşitlemesini engelle
  - İCloud Anahtarlık eşitlemesini engelle

Bu ayarlar yapılandırıldıysa ve iOS 13,0 sürümünden önce denetlenmeden önce cihazlara atanırsa, ayarlar hala bu denetlenmeden bu cihazlara uygulanır. Cihazlar iOS 13,0 ' e yükseltildikten sonra da hala geçerlidir. Bu kısıtlamalar, yedeklenen ve geri yüklenen denetimli cihazlarda kaldırılır. 

Geçerli ayarları görmek için [iOS cihaz ayarları ' na giderek Intune kullanarak özelliklere izin verin veya kısıtlayın](device-restrictions-ios.md).

Şunun için geçerlidir:  
- iOS 13,0 ve üzeri

### <a name="new-settings-and-changes-to-existing-settings-to-restrict-features-on-ios-and-macos-devices----4867699-4867709----"></a>İOS ve macOS cihazlarındaki özellikleri kısıtlamak için yeni ayarlar ve var olan ayarlarda yapılan değişiklikler <!-- 4867699 4867709  -->
İOS ve MacOS çalıştıran cihazlarda ayarları kısıtlamak için profiller oluşturabileceksiniz (**cihaz yapılandırma** > **profilleri** > platform için**iOS** veya **MacOS** **profili oluşturma** >  > **cihaz kısıtlamalarını**yazın). Aşağıdaki özellikler eklenecek:

- **MacOS** > **cihaz kısıtlamaları** > **bulutu ve depolaması**üzerinde, kullanıcıların bir MacOS cihazında çalışmayı başlatmasını engellemek için yeni **iletim** ayarını kullanın ve başka bir MacOS veya iOS cihazında çalışmaya devam edin.
  Geçerli ayarları görmek için, [Intune kullanarak özelliklere izin vermek veya erişimi kısıtlamak üzere MacOS cihaz ayarları](device-restrictions-macos.md)' na gidin.
- **İOS** > **cihaz kısıtlamalarında**birkaç değişiklik vardır:
  - **Yerleşik uygulamalar** > **iPhone 'umu bul (yalnızca denetimli)** : Uygulamamı bul özelliğinde bu özelliği engelleyen yeni ayar. 
  - **Yerleşik uygulamalar** > **Arkadaşlarımı bul (yalnızca denetimli)** : Uygulamamı bul özelliğinde bu özelliği engelleyen yeni ayar. 
  -  > **Wi-Fi durumunda kablosuz değişiklik (yalnızca denetimli)** : Kullanıcıların cihazda Wi-Fi ' i açmasını veya kapatmasını engelleyen yeni ayar.
  - **Klavye ve sözlük** > **hızlı yolu (yalnızca denetimli)** : QuickPath özelliğini engelleyen yeni ayar.
  - **Bulut ve depolama**: **Etkinlik devamlılığı** iletime olarak yeniden **adlandırıldı.**

  Geçerli ayarları görmek için [iOS cihaz ayarları ' na giderek Intune kullanarak özelliklere izin verin veya kısıtlayın](device-restrictions-ios.md).

Şunun için geçerlidir:  
- macOS 10,15 ve üzeri
- iOS 13 ve üzeri

### <a name="control-the-apps-files-documents-and-folders-that-open-when-user-signs-in-to-macos-devices---3914202----"></a>Kullanıcı macOS cihazlarında oturum açtığında açık olan uygulamaları, dosyaları, belgeleri ve klasörleri denetleyin <!--3914202  -->
MacOS cihazlarındaki özellikleri etkinleştirebilir ve yapılandırabileceksiniz (**cihaz yapılandırma** > **profilleri** > platform > **cihaz özellikleri** için**MacOS** **profili oluşturma** >  profil türü). 

Kullanıcı kayıtlı cihazda oturum açtığında hangi uygulamaların, dosyaların, belgelerin ve klasörlerin açık olduğunu denetlemek için yeni oturum açma öğeleri ayarları olacaktır. 

Geçerli ayarları görmek için [Intune 'Da MacOS cihaz özelliği ayarları](macos-device-features-settings.md)' na gidin.

Şunun için geçerlidir:  
- Mac OS

### <a name="new-features-for-android-enterprise-dedicated-devices-in-multi-app-mode----3755304-3041943-3041946----"></a>Çok uygulama modundaki Android kurumsal adanmış cihazlar için yeni özellikler <!-- 3755304 3041943 3041946  -->
Android kurumsal adanmış cihazlarınızda bilgi noktası stili bir deneyimde özellikleri ve ayarları denetleyebileceksiniz. Bunu yapmak için **cihaz yapılandırma** > **profilleri** > **profil** > oluştur ' u seçin**platform için** **yalnızca cihaz sahibi > ve** profil türü için cihaz kısıtlamaları.

Aşağıdaki özellikler eklenecek:
- **Adanmış cihazlar** > **çoklu uygulama**: **Sanal giriş düğmesi** cihaza çekerek veya ekranda kayan, böylece kullanıcıların taşıyabilmesi için görüntülenebilir.
- **Adanmış cihazlar** > **çoklu uygulama**: **Flashlight erişimi** , kullanıcıların Flashlight kullanmasına izin verir. 
- **Adanmış cihazlar** > **çoklu uygulama**: **Medya birimi denetimi** , kullanıcıların bir kaydırıcı kullanarak cihazın medya birimini denetlemesine olanak tanır. 
- **Adanmış cihazlar** > **çoklu uygulama**:  Ekran koruyucuyu etkinleştirme, özel bir görüntü yükleme ve ekran koruyucusuna ne zaman gösterildiğini denetleme.

Geçerli ayarları görmek için [Android kurumsal cihaz ayarları ' na giderek Intune kullanarak özelliklere izin verin veya kısıtlayın](device-restrictions-android-for-work.md#dedicated-device-settings).

Şunun için geçerlidir:  
- Android kurumsal adanmış cihazlar

### <a name="new-app-and-configuration-profiles-for-android-enterprise-fully-managed-devices----3574215----"></a>Android kurumsal tam olarak yönetilen cihazlar için yeni uygulama ve yapılandırma profilleri <!-- 3574215  -->
Profilleri kullanarak, Android kurumsal tam olarak yönetilen cihazlarınıza VPN, e-posta ve Wi-Fi ayarlarını uygulayan ayarları yapılandırabileceksiniz. Şunları yapabileceksiniz:
- Outlook, Gmail ve dokuz Iş e-posta ayarlarını dağıtmak için uygulama profillerini kullanın.
- Güvenilen kök sertifika ayarlarını dağıtmak için cihaz yapılandırma profillerini kullanın.
- VPN ve Wi-Fi ayarlarını dağıtmak için cihaz yapılandırma profillerini kullanın.

Kullanıcılar, VPN, Wi-Fi ve e-posta profilleri için Kullanıcı adı ve parolasıyla kimlik doğrulaması yapacak. Sertifika tabanlı kimlik doğrulaması şu anda kullanılamıyor. 

Şunun için geçerlidir:  
- Android kurumsal tam yönetilen

### <a name="support-for-ikev2-vpn-profiles-for-ios----1943438---"></a>İOS için IKEv2 VPN profilleri desteği <!-- 1943438 -->
Ikev2 protokolünü kullanarak iOS Native VPN istemcisi için VPN profilleri oluşturabileceksiniz. Ikev2, **cihaz yapılandırma** > **profillerinde** > yeni bir bağlantı türüdür, profil türü > **ayarları**için **VPN** > Platform için**iOS** **oluşturun** > .

Bu VPN profilleri, yerel VPN istemcisini yapılandırır. Bu nedenle, yönetilen cihazlara yüklenmiş veya hiçbir VPN istemci uygulaması gönderilmez. Bu özellik cihazların Intune 'A (MDM kaydı) kaydedilmesini gerektirir.

Yapılandırabileceğiniz geçerli VPN ayarlarını görmek için [Microsoft Intune iOS CIHAZLARıNDA VPN ayarlarını yapılandırma](vpn-settings-ios.md)bölümüne gidin.

Şunun için geçerlidir: iOS

<!-- ***********************************************-->
## <a name="device-enrollment"></a>Cihaz kaydı

### <a name="skip-more-screens-in-setup-assistant---4877451---"></a>Kurulum Yardımcısı 'nda daha fazla ekran atlayın <!--4877451 -->
Aşağıdaki Kurulum Yardımcısı ekranlarını atlamak için Aygıt Kayıt Programı profilleri ayarlayabileceksiniz: 
- Ekran zamanı
- Dokunma KIMLIĞI kurulumu

Bunu yapmak için, **cihaz kaydı** > **Apple kaydı** > **kayıt programı belirteçleri** ' ne gidin > belirteç > **profilleri** seçin > bir profil seçin > **özellikleri** > **Düzenle**  **Kurulum Yardımcısı özelleştirmesi**' nın yanında.
Kurulum Yardımcısı özelleştirmesi hakkında daha fazla bilgi için bkz. [Apple kayıt profili oluşturma ](device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile).

### <a name="android-enrollment-device-administrator-support----4869749----"></a>Android kayıt cihazı yöneticisi desteği <!-- 4869749  -->
Android Cihaz Yöneticisi kayıt seçeneği, Android kayıt sayfasına (**Intune** > **cihaz kaydı** > **Android kaydı**) eklenir. Android Cihaz Yöneticisi, tüm kiracılar için varsayılan olarak hala etkinleştirilecek.  

### <a name="for-ios-devices-customize-the-enrollment-process-privacy-screen-of-the-company-portal----4394993----"></a>İOS cihazları için Şirket Portalı kayıt işlemi gizlilik ekranını özelleştirin <!-- 4394993  -->
Marku kullanarak, son kullanıcıların iOS kaydı sırasında göreceği Şirket Portalı gizlilik ekranını özelleştirebileceksiniz. Özellikle, kuruluşunuzun cihazı göremeyecek veya cihaz üzerinde yapaamayacak işlerin listesini özelleştirebilirsiniz.

<!-- ***********************************************-->
## <a name="device-management"></a>Cihaz yönetimi

### <a name="build-number-included-on-android-device-hardware-page----4461910----"></a>Android cihaz donanımı sayfasına dahil edilen derleme numarası <!-- 4461910  -->
Her Android cihazının donanım sayfasında yeni bir giriş, cihazın işletim sistemi yapı numarasını içerir.

### <a name="configure-automatic-device-clean-up-time-limit-down-to-30-days---4231059----"></a>Otomatik cihaz temizleme süresi limitini 30 güne kadar yapılandırma <!--4231059  -->
Otomatik cihaz temizleme süresi sınırını, son oturum açma işleminden sonra 30 gün (geçerli 90 günlük sınırı yerine) kadar kısa bir süre içinde ayarlayabileceksiniz. Bunu yapmak için, **Intune** > **cihazları** > **Kurulum** > **cihaz temizleme kuralları**' na gidin.

<!-- ***********************************************-->
## <a name="role-based-access-control"></a>Rol tabanlı erişim denetimi

### <a name="default-scope-tag----3702875---"></a>Varsayılan kapsam etiketi <!-- 3702875 -->
Yeni bir yerleşik varsayılan kapsam etiketi mevcut olacaktır. Kapsam etiketlerini destekleyen etiketsiz tüm Intune nesneleri varsayılan kapsam etiketine otomatik olarak atanır. **Varsayılan** kapsam etiketi, günümüzde yönetici deneyimiyle eşliği sağlamak için mevcut tüm rol atamalarına eklenecektir. Yöneticinin varsayılan kapsam etiketleriyle Intune nesnelerini görmesini istemiyorsanız, varsayılan kapsam etiketini rol atamasından kaldırın. Bu özellik, System Center Configuration Manager güvenlik kapsamları özelliğine benzer.

<!-- ***********************************************-->
## <a name="security"></a>Güvenlik

### <a name="import-and-export-security-baselines------3408610------------"></a>Güvenlik temellerini içeri ve dışarı aktarma    <!--3408610          -->  
Güvenlik temellerini dışarı ve içeri aktarma özelliğini ekliyoruz. Bu özellik, özelleştirmelerinizi sizinle yapmanızı ve bunları Intune ortamları arasında paylaşmanızı sağlar.

<!-- ***********************************************-->
## <a name="notices"></a>Bildirimler

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

## <a name="see-also"></a>Ayrıca bkz.
Son geliştirmelere ilişkin ayrıntılar için bkz. [Microsoft Intune’daki Yenilikler](whats-new.md).




