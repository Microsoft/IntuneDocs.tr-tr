---
title: Microsoft Intune - Azure’da cihaz profilleri | Microsoft Docs
description: Özellikler, kısıtlamalar, e-posta, wifi, VPN, eğitim, sertifikalar, Windows 10, BitLocker ve Windows defender, Windows Bilgi Koruması ve Azure portalındaki özel cihaz yapılandırma ayarları gibi farklı Microsoft Intune cihaz profillerine genel bakış. Şirketinizdeki verileri ve cihazları yönetmek ve korumak için bu profili kullanın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/19/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.openlocfilehash: c9a3146b1ad5f6f7c439d2e49cf534e14d154f76
ms.sourcegitcommit: ecd6aebe50b1440a282dfdda771e37fbb8750d42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2018
ms.locfileid: "52728710"
---
# <a name="what-are-microsoft-intune-device-profiles"></a>Microsoft Intune cihaz profilleri nedir?

Microsoft Intune, kuruluşunuzdaki farklı cihazlarda etkinleştirebileceğiniz veya devre dışı bırakabileceğiniz ayarları ve özellikleri içerir. Bu ayarlar ve özellikler, profiller kullanılarak yönetilir. Bazı profil örnekleri şunlardır: 

- Kurumsal WiFi'nize farklı cihazlara erişim sağlayan bir WiFi profili
- Kurumsal ağınızda VPN sunucunuza farklı cihaz erişimi veren bir VPN profili

Bu makalede, cihazlarınız için oluşturabileceğiniz farklı profillere genel bir bakış sağlanır. Cihazlardaki bazı özelliklere izin vermek veya bunları engellemek için bu profilleri kullanın.

## <a name="before-you-begin"></a>Başlamadan önce

Kullanılabilir özellikleri görmek için [Azure portalı](https://portal.azure.com)'nı açın ve Intune kaynağınızı açın. 

**Cihaz yapılandırması** aşağıdaki seçenekleri içerir:

- **Genel Bakış**: Profillerinizin durumunu listeler, kullanıcılara ve cihazlara atadığınız profiller hakkında ek ayrıntılar sağlar
- **Yönet**: Cihaz profilleri oluşturun ve profil içinde çalışmak üzere özel [PowerShell betiklerini](intune-management-extension.md) karşıya yükleyin
- **İzle**: Bir profilin başarı veya başarısızlık durumunu denetleyin ve ayrıca profillerinize ilişkin günlükleri görüntüleyin
- **Kurulum**: Bir sertifika yetkilisi (SCEP veya PFX) ekleyin veya profilde Telekomünikasyon Gider Yönetimi’ni etkinleştirin

## <a name="create-the-profile"></a>Profili oluşturma

[Cihaz profilleri oluşturma](device-profile-create.md), bir profil oluşturmak için adım adım yönergeler sağlar. 

## <a name="device-features---ios-and-macos"></a>Cihaz özellikleri - iOS ve macOS

[Cihaz özellikleri](device-features-configure.md), iOS ve macOS cihazlarda AirPrint, bildirimler ve paylaşılan cihaz yapılandırmaları gibi özellikleri denetler.

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
- Windows 10
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

Bilgi noktası ayarları için cihaz kısıtlamaları olarak da kullanılabilir [Android](device-restrictions-android.md#kiosk), [Android Kurumsal](device-restrictions-android-for-work.md#kiosk-settings), ve [ios](device-restrictions-ios.md#kiosk-supervised-only).

## <a name="email"></a>E-posta

[E-posta ayarları](email-settings-configure.md) oluşturur, atar ve cihazlarda Exchange ActiveSync e-posta ayarlarını izler. Profilleri Yardım tutarlılık ile e-posta, destek çağrılarını azaltır ve son kullanıcılara erişim şirket e-postasına herhangi bir kurulum yapmalarına gerek kalmadan kişisel cihazlarından sağlar. 

Bu özellik şunları destekler: 

- Android
- iOS
- Windows Phone 8.1
- Windows 10

## <a name="vpn"></a>VPN

[VPN ayarları](vpn-settings-configure.md), kuruluşunuzdaki kullanıcılara ve cihazlara VPN profilleri atar, böylece ağa kolayca ve güvenli bir şekilde bağlanabilirler. 

Sanal özel ağlar (VPN’ler), kullanıcılara şirket ağınıza güvenli uzaktan erişim vermenize olanak tanır. Cihazlar VPN sunucunuzla bağlantı başlatmak için VPN bağlantısı profilini kullanır. 

Bu özellik şunları destekler: 

- Android
- iOS
- Mac OS
- Windows Phone 8.1
- Windows 8.1
- Windows 10

## <a name="wi-fi"></a>Wi-Fi

[Wi-Fi ayarları](wi-fi-settings-configure.md), kullanıcılar ve cihazlar için kablosuz ağ ayarları atar. Bir Wi-Fi profili atadığınızda, kullanıcılar kurumsal Wi-Fi ağınıza, ağı kendileri yapılandırmak zorunda kalmadan erişim elde eder. 

Bu özellik şunları destekler: 

- Android
- iOS
- Mac OS
- Windows 8.1 (yalnızca içeri aktarma)

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

Bu özellik şunları destekler:
- iOS

## <a name="certificates"></a>Sertifikalar

[Sertifikaları](certificates-configure.md) yapılandırır güvenilen, SCEP ve PKCS sertifikaları cihazlara atanabilen ve Wi-Fi, VPN, kimlik doğrulaması ve e-posta profillerini için kullanılır.

Bu özellik şunları destekler: 

- Android
- iOS
- Windows Phone 8.1
- Windows 8.1
- Windows 10

## <a name="windows-information-protection-profile"></a>Windows Bilgi Koruması profili

[Windows Bilgi Koruması](windows-information-protection-configure.md), çalışanın deneyimine müdahale etmeden veri sızıntılarına karşı koruma sağlamaya yardımcı olur. Ayrıca, kurumsal uygulamalar ve veriler kuruluşa ait cihazlardaki ve çalışanların İşte kullandıkları kişisel cihazlardaki kazayla veri sızıntılarına karşı korunmasına yardımcı olur. Windows Information Protection'ı kullanarak, ortamınızda veya diğer uygulamalar için shanges gerektirmez.

Bu özellik şunları destekler:
- Windows 10 ve üzeri

## <a name="custom-profile"></a>Özel profil

[Özel ayarlar](custom-settings-configure.md) yöneticilerin Intune'da yerleşik olarak olmayan cihaz ayarlarını atamanıza olanak verir. Örneğin, Android cihazlarda, OMA-URI değerleri girebilirsiniz. iOS cihazları için, Apple Configurator’da oluşturduğunuz bir yapılandırma dosyasını içeri aktarabilirsiniz. 

Bu özellik şunları destekler:

- Android
- iOS
- Mac OS
- Windows Phone 8.1

## <a name="manage-and-troubleshoot"></a>Yönetme ve sorun giderme

[Profillerinizi yöneterek](device-profile-monitor.md) cihazların ve atanan profillerin durumunu denetleyin. Ayrıca, çakışma yaratan ayarları ve bu ayarları içeren profilleri görerek çakışmaların çözümlenmesine yardımcı olun. [Genel sorunlar ve çözümleri](device-profile-troubleshoot.md) soru- cevap iş profilleriyle bir profil silindiğinde, ne de dahil olmak üzere cihazları ve daha fazlası için gönderilecek hangi nedenleri bildirimleri yardımcı olmak için sağlar.
