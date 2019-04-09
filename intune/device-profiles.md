---
title: Cihaz özellikleri ve ayarları Microsoft Intune - Azure | Microsoft Docs
description: Farklı Microsoft Intune cihaz profilleri genel bakış. Azure portalında özellikleri, kısıtlamalar, e-posta, Wi-Fi, VPN, eğitim, sertifikalar, yükseltme Windows 10, BitLocker ve Windows defender, Windows Information Protection, Yönetim Şablonları ve özel cihaz yapılandırma ayarları hakkında bilgi alın. Bu profiller, yönetmek ve verileri ve cihazları şirketinizin korumak için kullanın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/08/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4dc68071886b8f2a0852feb69bf78c2c265f046d
ms.sourcegitcommit: 364a7dbc7eaa414c7a9c39cf53eb4250e1ad3151
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59292504"
---
# <a name="apply-features-and-settings-on-your-devices-using-device-profiles-in-microsoft-intune"></a>Intune cihaz profillerini kullanarak cihazlarınızda özellikleri ve ayarları uygula

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Microsoft Intune ayarları ve özellikleri etkinleştirebilir veya kuruluşunuzdaki farklı cihazlarda devre dışı bırak'ı içerir. Bu ayarlar ve Özellikler "yapılandırma profillerini" eklenir. Farklı cihaz ve iOS, Android ve Windows gibi farklı platformlar için profiller oluşturabilirsiniz. Ardından, uygulama veya "profili cihazlara atamayı" için Intune'u kullanın.

Mobil cihaz Yönetimi (MDM) çözümünüzün bir parçası olarak farklı görevleri tamamlamak için bu yapılandırma profillerini kullanın. Bazı profil örnekleri şunlardır:

- Windows 10 cihazlarda Internet Explorer'da profil şablonu engelleyen ActiveX denetimlerini kullanın.
- İOS ve macOS cihazlarda AirPrint yazıcıları kuruluşunuzda kullandığınız açmasına imkan tanıyın.
- İzin verme veya cihazda bluetooth için erişimi engelleme.
- Şirket ağınıza farklı cihazlara erişim sağlayan bir WiFi veya VPN profili oluşturun.
- Bunlar yüklendiğinde dahil olmak üzere, yazılım güncelleştirmelerini yönetir.
- Bir Android cihazı, bir uygulama çalıştırmasına veya daha fazla uygulama çalıştırma adanmış bilgi noktası cihazı çalıştırın.

Bu makalede profilleri oluşturabileceğiniz farklı türde genel bir bakış sağlar. İzin vermek veya bazı özellikler cihazlara önlemek için bu profilleri kullanın.

## <a name="administrative-templates-preview"></a>Yönetim Şablonları (Önizleme)

[Yönetim Şablonları](administrative-templates-windows.md) yüzlerce Internet Explorer, OneDrive, Uzak Masaüstü, Word, Excel ve diğer Office programları için yapılandıran ayarları içerir.

Bu şablonlar Yöneticiler ayarları Grup İlkesi'ne benzer basitleştirilmiş bir görünümünü sağlar, ancak % 100 bulut tabanlı oldukları.

Bu özellik şunları destekler:

- Windows 10 ve üzeri

## <a name="device-features"></a>Cihaz özellikleri

[Cihaz özellikleri](device-features-configure.md) iOS ve macOS cihazlarda AirPrint, bildirimler ve kilit ekranı iletileri gibi özellikleri denetler.

Bu özellik şunları destekler:

- iOS 
- Mac OS

## <a name="device-restrictions"></a>Cihaz kısıtlamaları

[Cihaz kısıtlamaları](device-restrictions-configure.md) cihazlarda güvenlik, donanım, veri paylaşımı ve daha fazla ayarı denetler. Örneğin, iOS cihaz kullanıcılarının cihazın kamerasını kullanmasını engelleyen bir cihaz kısıtlama profili oluşturun. 

Bu özellik şunları destekler:

- Android
- Android Kurumsal
- iOS
- Mac OS
- Windows 10 ve üzeri
- Windows 10 ekibi

## <a name="delivery-optimization"></a>Teslim iyileştirme

[Teslim iyileştirme](delivery-optimization-windows.md) teslim yazılım güncelleştirmeleri için daha iyi bir deneyim sağlar. Bu ayarları değiştirme **yazılım güncelleştirmelerini** > **Windows 10 güncelleştirme halkası** ayarları.

Kuruluşunuzdaki cihazlar için yazılım güncelleştirmelerinin nasıl yükleneceğini kontrol etmek için bu ayarları kullanın. Örneğin, kullanıcıların kendi güncelleştirmeleri almak veya teslim iyileştirme bulut Hizmetleri bir cihaz profili kullanarak güncelleştirmeleri almak izin verebilirsiniz.

Bu özellik şunları destekler:

- Windows 10 ve üzeri

## <a name="endpoint-protection"></a>Endpoint protection

[Windows 10 için Endpoint protection ayarları](endpoint-protection-windows-10.md) Windows 10 cihazları için BitLocker'ı ve Windows Defender ayarlarını yapılandırır.

Microsoft Intune'a Windows Defender Gelişmiş Tehdit Koruması'nı (WDATP) eklemek için bkz. [Mobil Cihaz Yönetimi (MDM) araçlarını kullanarak uç noktaları yapılandırma](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/configure-endpoints-mdm-windows-defender-advanced-threat-protection).

Bu özellik şunları destekler:

- Windows 10 ve üzeri

## <a name="identity-protection"></a>Kimlik koruması

[Kimlik koruması](identity-protection-configure.md), Windows 10 ve Windows 10 Mobile cihazlarda İş İçin Windows Hello deneyimini denetler. İş İçin Windows Hello’yu kullanıcı ve cihazlar için kullanılabilir kılmak ve cihaz PIN’i ve hareketlerini belirtmek için bu ayarları yapılandırın.  

Bu özellik şunları destekler:  

- Windows 10 ve üzeri
- Windows 10 Holographic for Business  

## <a name="kiosk"></a>Bilgi noktası

[Bilgi noktası ayarları](kiosk-settings.md) bir uygulama çalıştırmasına veya birçok uygulamaları çalıştırmak için bir cihaz profili yapılandırır. Ayrıca bilgi noktanızda başlat menüsü ve web tarayıcısı gibi diğer özellikleri de özelleştirebilirsiniz.

Bu özellik şunları destekler:

- Windows 10 ve üzeri

Bilgi noktası ayarları için cihaz kısıtlamaları olarak da kullanılabilir [Android](device-restrictions-android.md#kiosk), [Android Kurumsal](device-restrictions-android-for-work.md#dedicated-device-settings), ve [ios](device-restrictions-ios.md#kiosk-supervised-only).

## <a name="email"></a>Email

[E-posta ayarları](email-settings-configure.md) oluşturur, atar ve cihazlarda Exchange ActiveSync e-posta ayarlarını izler. Profilleri Yardım tutarlılık ile e-posta, destek çağrılarını azaltır ve son kullanıcılara erişim şirket e-postasına herhangi bir kurulum yapmalarına gerek kalmadan kişisel cihazlarından sağlar. 

Bu özellik şunları destekler: 

- Android
- Android Kurumsal
- iOS
- Windows Phone 8.1
- Windows 10 ve üzeri

## <a name="vpn"></a>VPN

[VPN ayarları](vpn-settings-configure.md), kuruluşunuzdaki kullanıcılara ve cihazlara VPN profilleri atar, böylece ağa kolayca ve güvenli bir şekilde bağlanabilirler. 

Sanal özel ağlar (VPN’ler), kullanıcılara şirket ağınıza güvenli uzaktan erişim vermenize olanak tanır. Cihazlar VPN sunucunuzla bağlantı başlatmak için VPN bağlantısı profilini kullanır. 

Bu özellik şunları destekler: 

- Android
- Android Kurumsal
- iOS
- Mac OS
- Windows Phone 8.1
- Windows 8.1
- Windows 10 ve üzeri

## <a name="wi-fi"></a>Wi-Fi

[Wi-Fi ayarları](wi-fi-settings-configure.md), kullanıcılar ve cihazlar için kablosuz ağ ayarları atar. Bir Wi-Fi profili atadığınızda, kullanıcılar kurumsal Wi-Fi ağınıza, ağı kendileri yapılandırmak zorunda kalmadan erişim elde eder. 

Bu özellik şunları destekler: 

- Android
- Android Kurumsal
- iOS
- Mac OS
- Windows 8.1 (yalnızca içeri aktarma)
- Windows 10 ve üzeri

## <a name="esim-cellular---public-preview"></a>eSIM hücresel - Genel önizleme

[Esım hücresel profilleri](esim-device-configuration.md) Internet ve veri erişimi için yönetilen cihazlarınızda hücresel veri planları yapılandırma yöneticilerin sağlar. Etkinleştirme kodlarını mobil operatörünüze aldıktan sonra bu etkinleştirme kodlarını almak ve ardından, Esım uyumlu cihazlara atamak için Intune'u kullanın.

Bu özellik şunları destekler:
- Windows 10 Fall Creators Update ve üzeri

## <a name="education"></a>Eğitim

[Eğitim ayarları - Windows 10](education-settings-configure.md), [Windows Sınav Zamanı uygulamasının](https://education.microsoft.com/gettrained/win10takeatest) seçeneklerini yapılandırır. Bu seçenekleri yapılandırdığınızda, sınav tamamlanana kadar cihazda başka uygulama çalıştırılamaz.

[Eğitim ayarları - iOS](education-settings-configure-ios-shared.md) sınıfta öğrenimi yönlendirmek ve öğrenci cihazlarını denetlemek için iOS Classroom uygulamasını kullanır. İPad cihazları, çok sayıda Öğrenciler tek bir cihazı paylaşacak şekilde yapılandırabilirsiniz.

## <a name="edition-upgrade"></a>Sürüm yükseltme

[Windows 10 sürüm yükseltmeleri](edition-upgrade-configure-windows-10.md), Windows 10'un bazı sürümlerini çalıştıran cihazları otomatik olarak yeni bir sürüme yükseltmenizi sağlar.

Bu özellik şunları destekler: 
- Windows 10 ve üzeri

## <a name="update-policies"></a>Güncelleştirme ilkeleri

[iOS güncelleştirme ilkeleri](software-updates-ios.md), iOS cihazlarınıza yazılım güncelleştirmelerini yüklemek için iOS ilkelerini nasıl oluşturacağınızı ve atayacağınızı gösterir. Ayrıca yükleme durumunu da gözden geçirebilirsiniz.

Windows cihazlarda güncelleştirme ilkeleri için bkz: [teslim iyileştirme](delivery-optimization-windows.md). 

Bu özellik şunları destekler:
- iOS

## <a name="certificates"></a>Sertifikalar

[Sertifikaları](certificates-configure.md) yapılandırma güvenilen, SCEP ve PKCS sertifikaları cihazlara atanır. Bu sertifikalar, Wi-Fi, VPN, kimlik doğrulaması ve e-posta profillerini.

Bu özellik şunları destekler: 

- Android
- Android Kurumsal
- iOS
- Mac OS
- Windows Phone 8.1
- Windows 8.1
- Windows 10 ve üzeri

## <a name="windows-information-protection-profile"></a>Windows Bilgi Koruması profili

[Windows Bilgi Koruması](windows-information-protection-configure.md), çalışanın deneyimine müdahale etmeden veri sızıntılarına karşı koruma sağlamaya yardımcı olur. Ayrıca, kurumsal uygulamalar ve veriler kuruluşa ait cihazlardaki ve çalışanların İşte kullandıkları kişisel cihazlardaki kazayla veri sızıntılarına karşı korunmasına yardımcı olur. Windows Information Protection'ı kullanarak, ortamınızda veya diğer uygulamalar için değişiklik yapılması gerekmez.

Bu özellik şunları destekler:

- Windows 10 ve üzeri

## <a name="shared-multi-user-device"></a>Paylaşılan çok kullanıcılı cihaz

[Windows 10](shared-user-device-settings-windows.md) ve [Windows Holographic for Business](shared-user-device-settings-windows-holographic.md) birden çok kullanıcıyla olarak da bilinen paylaşılan cihazlar veya paylaşılan bilgisayarlar cihazları yönetmek için ayarlar içerir. Kullanıcı cihazı açtığında, kullanıcı uyku seçenekleri değiştirebilir veya cihazdaki dosyaların kaydedin, seçin. Başka bir örnekte, alan, etkin olmayan kimlik bilgilerini Windows HoloLens cihazlardan silen bir profil oluşturabilirsiniz.

Bu paylaşılan birden çok kullanıcı cihaz ayarları, yöneticinin, bazı cihaz özelliklerini denetlemek izin ve bu paylaşılan cihazları Intune kullanarak yönetmek.

Bu özellik şunları destekler:

- Windows 10 ve üzeri
- Windows 10 Holographic for Business

## <a name="zebra-mobility-extensions-mx"></a>Zebra Mobility Uzantıları (MX)

[Zebra Mobility Uzantıları (MX)](android-zebra-mx-overview.md) yöneticilerin kullanın ve ıntune'da Zebra cihazları yönetmenize olanak sağlar. Ayarlarınızla StageNow profilleri oluşturmak ve ardından atayabilir ve bu profiller Zebra cihazlarınıza dağıtmak için Intune kullanın. [StageNow günlükleri ve sık karşılaşılan sorunları](android-zebra-mx-logs-troubleshoot.md) profilleriyle ilgili sorunları giderme ve StageNow kullanırken bazı olası sorunları görmek için harika bir kaynaktır.

Bu özellik şunları destekler:

- Android

## <a name="custom-profile"></a>Özel profil

[Özel ayarlar](custom-settings-configure.md) yöneticilerin Intune'da yerleşik olarak bulunmaz cihaz ayarlarını atamanıza olanak tanır. Android cihazlarda, OMA-URI değerleri girebilirsiniz. iOS cihazları için, Apple Configurator’da oluşturduğunuz bir yapılandırma dosyasını içeri aktarabilirsiniz.

Bu özellik şunları destekler:

- Android
- Android Kurumsal
- iOS
- Mac OS
- Windows Phone 8.1

## <a name="manage-and-troubleshoot"></a>Yönetme ve sorun giderme

[Profillerinizi yöneterek](device-profile-monitor.md) cihazların ve atanan profillerin durumunu denetleyin. Ayrıca bir çakışma ve bu ayarları içeren profilleriniz neden ayarları görerek çakışmaları yardımcı olur. [Genel sorunlar ve çözümleri](device-profile-troubleshoot.md) iş profilleri yöneticilere yardımcı olur. Bu, silerken bir profili hangi cihazları ve daha fazlası için gönderilecek bildirimler neden ne açıklar.

## <a name="next-steps"></a>Sonraki adımlar

Platformunuzu seçin ve çalışmaya başlayın.
