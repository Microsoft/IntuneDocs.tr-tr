---
title: Cihaz özellikleri ve ayarları Microsoft Intune - Azure | Microsoft Docs
description: Farklı Microsoft Intune cihaz profilleri de dahil olmak üzere genel bakış özellikler, sınırlamalar, Wi-Fi, VPN, e-posta eğitim, sertifikalar, Windows 10, BitLocker ve Windows defender, Windows Information Protection, Yönetim Şablonları, yükseltme ve Azure portalındaki özel cihaz yapılandırma ayarları. Bu profiller, yönetmek ve verileri ve cihazları şirketinizin korumak için kullanın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/29/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 016b59a915058c3f2d0647a72e3ead224a010500
ms.sourcegitcommit: e5f501b396cb8743a8a9dea33381a16caadc51a9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2019
ms.locfileid: "56742458"
---
# <a name="apply-features-settings-on-your-devices-using-device-profiles-in-microsoft-intune"></a>Cihaz profillerini kullanarak Intune cihazlarınızda özellikleri ayarlar uygulanır

Microsoft Intune ayarları ve özellikleri etkinleştirebilir veya kuruluşunuzdaki farklı cihazlarda devre dışı bırak'ı içerir. Bu ayarlar ve Özellikler "yapılandırma profillerini" eklenir. Profilleri, farklı cihazlar için oluşturabileceğiniz farklı platformları dahil olmak üzere iOS, Android, Windows ve Intune profili, kuruluşunuzdaki cihazlara uygulamak için kullanın.

Bazı profil örnekleri şunlardır:

- Windows 10 cihazlarda Internet Explorer'da profil şablonu engelleyen ActiveX denetimlerini kullanın.
- İOS ve macOS cihazlarda AirPrint yazıcıları kuruluşunuzda kullandığınız açmasına imkan tanıyın.
- İzin verme veya cihazda bluetooth için erişimi engelleme.
- Şirket ağınıza farklı cihazlara erişim sağlayan bir WiFi veya VPN profili oluşturun.
- Yüklendiklerinde dahil olmak üzere, yazılım güncelleştirmelerini yönetir.
- Bir Android cihazı, bir uygulama çalıştırmasına veya daha fazla uygulama çalıştırma adanmış bilgi noktası cihazı çalıştırın.

Bu makalede, profil oluşturma adımları listelenir ve profilleri oluşturabileceğiniz farklı türde genel bir bakış sağlar. İzin vermek veya bazı özellikler cihazlara önlemek için bu profilleri kullanın.

## <a name="create-the-profile"></a>Profili oluşturma

1. İçinde [Azure portalında](https://portal.azure.com)seçin **tüm hizmetleri** > Filtre **Intune** > seçin **Intune**.

2. **Cihaz yapılandırması**’nı seçin. Aşağıdaki seçenekleriniz vardır:

    - **Genel Bakış**: Profillerinizin durumunu listeler ve kullanıcılara ve cihazlara atadığınız Profiller hakkında ek ayrıntılar sağlar.
    - **Yönetme**: Cihaz profilleri oluşturma, özel yükleme [PowerShell betikleri](intune-management-extension.md) profil içinde çalışmak ve veri planları kullanarak cihazlara [Esım](esim-device-configuration.md).
    - **İzleyici**: Bir profilin başarı veya başarısızlık durumunu denetleyin ve ayrıca profillerinize ilişkin günlükleri görüntüleyin.
    - **Kurulum**: Bir SCEP veya PFX sertifika yetkilisi ekleyin veya etkinleştirme [Telekom Gider Yönetimi](telecom-expenses-monitor.md) profilinde.

3. Seçin **profilleri** > **profili oluşturma**. Aşağıdaki özellikleri girin:

   - **Ad**: Profil için açıklayıcı bir ad girin.
   - **Açıklama**: Profil için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
   - **Platform**: Cihazlarınızın platformu seçin. Seçenekleriniz şunlardır:  

       - **Android**
       - **Android kurumsal**
       - **iOS**
       - **macOS**
       - **Windows Phone 8.1**
       - **Windows 8.1 ve üzeri**
       - **Windows 10 ve üzeri**

   - **Profil türü**: Oluşturmak istediğiniz ayarlarının türünü seçin. Gösterilen listesi bağımlı **platform** seçtiğiniz:

       - [Yönetim Şablonları](administrative-templates-windows.md)
       - [Özel](custom-settings-configure.md)
       - [Teslim iyileştirme](delivery-optimization-windows.md)
       - [Cihaz özellikleri](device-features-configure.md)
       - [Cihaz kısıtlamaları](device-restrictions-configure.md)
       - [Sürüm yükseltme ve modu anahtarı](edition-upgrade-configure-windows-10.md)
       - [Eğitim](education-settings-configure.md)
       - [E-posta](email-settings-configure.md)
       - [Uç nokta koruması](endpoint-protection-configure.md)
       - [Kimlik koruması](identity-protection-configure.md)  
       - [Bilgi noktası](kiosk-settings.md)
       - [PKCS sertifikası](certficates-pfx-configure.md)
       - [SCEP sertifikası](certificates-scep-configure.md)
       - [Güvenilir sertifika](certificates-configure.md)
       - [Güncelleştirme ilkeleri](software-updates-ios.md)
       - [VPN](vpn-settings-configure.md)
       - [Wi-Fi](wi-fi-settings-configure.md)
       - [Windows Defender ATP](advanced-threat-protection.md)
       - [Windows Bilgi Koruması](windows-information-protection-configure.md)

     Örneğin, **iOS** platformu, profil türü seçeneklerinizi aşağıdakine benzer:

     ![Intune'da iOS profili oluşturma](./media/create-device-profile.png)

4. Seçin **ayarları**. Ayarları, kategoriye göre düzenlenir. Yapılandırabileceğiniz ayarların listesi görmek için bir kategori seçin.

5. İşiniz bittiğinde seçin **Tamam** > **Oluştur** yaptığınız değişiklikleri kaydedin.

Farklı bir profil türleri hakkında daha fazla bilgi edinmek için bu makalenin sonraki bölümleri inceleyin.

## <a name="administrative-templates-preview"></a>Yönetim Şablonları (Önizleme)

[Yönetim Şablonları](administrative-templates-windows.md) yüzlerce Internet Explorer, OneDrive, Uzak Masaüstü, Word, Excel ve diğer Office programları ve çok daha fazlası için yapılandıran ayarları içerir.

Bu şablonları Yöneticiler ayarları Grup İlkesi'ne benzer kolay ve Basitleştirilmiş bir görünümünü sağlar, ancak bunlar %100 bulut tabanlı. 

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
- iOS
- Windows Phone 8.1
- Windows 10 ve üzeri

## <a name="vpn"></a>VPN

[VPN ayarları](vpn-settings-configure.md), kuruluşunuzdaki kullanıcılara ve cihazlara VPN profilleri atar, böylece ağa kolayca ve güvenli bir şekilde bağlanabilirler. 

Sanal özel ağlar (VPN’ler), kullanıcılara şirket ağınıza güvenli uzaktan erişim vermenize olanak tanır. Cihazlar VPN sunucunuzla bağlantı başlatmak için VPN bağlantısı profilini kullanır. 

Bu özellik şunları destekler: 

- Android
- iOS
- Mac OS
- Windows Phone 8.1
- Windows 8.1
- Windows 10 ve üzeri

## <a name="wi-fi"></a>Wi-Fi

[Wi-Fi ayarları](wi-fi-settings-configure.md), kullanıcılar ve cihazlar için kablosuz ağ ayarları atar. Bir Wi-Fi profili atadığınızda, kullanıcılar kurumsal Wi-Fi ağınıza, ağı kendileri yapılandırmak zorunda kalmadan erişim elde eder. 

Bu özellik şunları destekler: 

- Android
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

[Sertifikaları](certificates-configure.md) yapılandırır güvenilen, SCEP ve PKCS sertifikaları cihazlara atanabilen ve Wi-Fi, VPN, kimlik doğrulaması ve e-posta profillerini için kullanılır.

Bu özellik şunları destekler: 

- Android
- iOS
- Windows Phone 8.1
- Windows 8.1
- Windows 10 ve üzeri

## <a name="windows-information-protection-profile"></a>Windows Bilgi Koruması profili

[Windows Bilgi Koruması](windows-information-protection-configure.md), çalışanın deneyimine müdahale etmeden veri sızıntılarına karşı koruma sağlamaya yardımcı olur. Ayrıca, kurumsal uygulamalar ve veriler kuruluşa ait cihazlardaki ve çalışanların İşte kullandıkları kişisel cihazlardaki kazayla veri sızıntılarına karşı korunmasına yardımcı olur. Windows Information Protection'ı kullanarak, ortamınızda veya diğer uygulamalar için değişiklik yapılması gerekmez.

Bu özellik şunları destekler:

- Windows 10 ve üzeri

## <a name="shared-multi-user-device"></a>Paylaşılan çok kullanıcılı cihaz

[Windows 10](shared-user-device-settings-windows.md) ve [Windows Holographic for Business](shared-user-device-settings-windows-holographic.md) birden çok kullanıcıyla olarak da bilinen paylaşılan cihazlar veya paylaşılan bilgisayarlar cihazları yönetmek için ayarlar içerir. Kullanıcı cihazı açtığında, kullanıcı uyku seçenekleri değiştirebilir veya cihazdaki dosyaların kaydedin, seçin. Başka bir örnekte, etkin olmayan kimlik alanı kaydetmek için Windows HoloLens cihazlardan silen bir ilke oluşturabilirsiniz.

Bu paylaşılan birden çok kullanıcı cihaz ayarları, yöneticinin, bazı cihaz özelliklerini denetlemek izin ve bu paylaşılan cihazları Intune kullanarak yönetmek.

Bu özellik şunları destekler:

- Windows 10 ve üzeri
- Windows 10 Holographic for Business

## <a name="custom-profile"></a>Özel profil

[Özel ayarlar](custom-settings-configure.md) yöneticilerin Intune'da yerleşik olarak olmayan cihaz ayarlarını atamanıza olanak verir. Örneğin, Android cihazlarda, OMA-URI değerleri girebilirsiniz. iOS cihazları için, Apple Configurator’da oluşturduğunuz bir yapılandırma dosyasını içeri aktarabilirsiniz. 

Bu özellik şunları destekler:

- Android
- iOS
- Mac OS
- Windows Phone 8.1

## <a name="manage-and-troubleshoot"></a>Yönetme ve sorun giderme

[Profillerinizi yöneterek](device-profile-monitor.md) cihazların ve atanan profillerin durumunu denetleyin. Ayrıca, çakışma yaratan ayarları ve bu ayarları içeren profilleri görerek çakışmaların çözümlenmesine yardımcı olun. [Genel sorunlar ve çözümleri](device-profile-troubleshoot.md) soru- cevap iş profilleriyle bir profil silindiğinde, ne de dahil olmak üzere cihazları ve daha fazlası için gönderilecek hangi nedenleri bildirimleri yardımcı olmak için sağlar.

## <a name="next-steps"></a>Sonraki adımlar
Platformunuzu seçin ve kullanmaya başlayın:

