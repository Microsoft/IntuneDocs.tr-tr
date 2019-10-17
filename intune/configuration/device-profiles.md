---
title: Microsoft Intune'daki cihaz özellikleri ve ayarları - Azure | Microsoft Docs
description: Farklı Microsoft Intune cihaz profillerine genel bakış. Özellikler, kısıtlamalar, e-posta, wifi, VPN, eğitim, sertifikalar, Windows 10, BitLocker ve Windows Defender, Windows Bilgi Koruması, yönetim şablonları ve Azure portalındaki özel cihaz yapılandırma ayarları hakkında bilgi edinin. Şirketinizdeki verileri ve cihazları yönetmek ve korumak için bu profilleri kullanın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 31a55f5749b35139368b6c3543fd8ff95db6100d
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72506829"
---
# <a name="apply-features-and-settings-on-your-devices-using-device-profiles-in-microsoft-intune"></a>Microsoft Intune'daki cihaz profillerini kullanarak cihazlarınıza özellik ve ayar uygulama

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Microsoft Intune, kuruluşunuzdaki farklı cihazlarda etkinleştirebileceğiniz veya devre dışı bırakabileceğiniz ayarları ve özellikleri içerir. Bu ayarlar ve özellikler "yapılandırma profillerine" eklenir. iOS, Android ve Windows dahil olmak üzere farklı cihazlar ve platformlar için profil oluşturabilirsiniz. Ardından Intune'u kullanarak bu profilleri cihazlara "atayabilirsiniz".

Mobil cihaz yönetimi (MDM) çözümünüzün bir parçası olarak bu yapılandırma profillerini kullanarak farklı görevler gerçekleştirebilirsiniz. Bazı profil örnekleri şunlardır:

- Windows 10 cihazlarda Internet Explorer'daki ActiveX denetimlerini engelleyen bir profil şablonu kullanabilirsiniz.
- iOS ve macOS cihazlarda kullanıcıların kuruluşunuzdaki AirPrint özellikli yazıcıları kullanmasını sağlayabilirsiniz.
- Cihazların Bluetooth özelliğine erişim verebilir veya engelleyebilirsiniz.
- Kurumsal ağınıza farklı cihaz erişimi veren bir WiFi veya VPN profili oluşturabilirsiniz.
- Yazılım güncelleştirmelerini ve yükleme zamanlarını yönetebilirsiniz.
- Bir Android cihazını bir veya birden çok uygulamayı çalıştıran ayrılmış bilgi noktası cihazı olarak çalıştırabilirsiniz.

Bu makalede oluşturabileceğiniz profil türlerine genel bir bakış sağlanmaktadır. Cihazlardaki bazı özelliklere izin vermek veya bunları engellemek için bu profilleri kullanabilirsiniz.

## <a name="administrative-templates"></a>Yönetim şablonları

[Yönetim şablonları](administrative-templates-windows.md) Internet Explorer, OneDrive, uzak masaüstü, Word, Excel ve diğer Office programları için yapılandırabileceğiniz yüzlerce ayarı içerir.

Yöneticiler, bu şablonlar sayesinde grup ilkelerine benzeyen ancak tamamen bulut tabanlı olan basitleştirilmiş bir görünüme sahip olur.

Bu özellik şunları destekler:

- Windows 10 ve üzeri

## <a name="certificates"></a>Sertifikalar

[Sertifikalar](../protect/certificates-configure.md), cihazlara atanan güvenilir, SCEP ve PKCS sertifikalarını yapılandırır. Bu sertifikalar WiFi, VPN ve e-posta profilleri için kimlik doğrulaması sağlar.

Bu özellik şunları destekler: 

- Android
- Android Kurumsal
- iOS/ıpados
- Mac OS
- WVPN profillerinidows Phone 8.1
- Windows 8.1
- Windows 10 ve üzeri

## <a name="custom-profile"></a>Özel profil

[Özel ayarlar](../custom-settings-configure.md), yöneticilerin Intune'da yerleşik olarak sağlanmayan cihaz ayarlarını atamasına olanak tanır. Android cihazlarda, OMA-URI değerleri girebilirsiniz. iOS cihazları için, Apple Configurator’da oluşturduğunuz bir yapılandırma dosyasını içeri aktarabilirsiniz.

Bu özellik şunları destekler:

- Android
- Android Kurumsal
- iOS/ıpados
- Mac OS
- WVPN profillerinidows Phone 8.1

## <a name="delivery-optimization"></a>Teslim iyileştirme

[Teslim iyileştirme](../delivery-optimization-windows.md), yazılım güncelleştirmelerini teslim etmek için daha iyi bir deneyim sunar. Bu ayarlar, **Yazılım Güncelleştirmeleri** > **Windows 10 güncelleştirme halkası** ayarlarının yerini alır.

Bu ayarları kullanarak yazılım güncelleştirmelerinin kuruluşunuzdaki ayarlara nasıl indirileceğini denetleyebilirsiniz. Örneğin kullanıcıların kendi güncelleştirmelerini yapmalarına izin verebilir veya teslim iyileştirme bulut hizmetlerini bir cihaz profilinde kullanarak güncelleştirmeleri almalarını sağlayabilirsiniz.

Bu özellik şunları destekler:

- Windows 10 ve üzeri

## <a name="device-features"></a>Cihaz özellikleri

[Cihaz özellikleri](../device-features-configure.md), iOS ve macOS cihazlarda AirPrint, bildirimler ve kilit ekranı iletileri gibi özellikleri denetler.

Bu özellik şunları destekler:

- iOS/ıpados
- Mac OS

## <a name="device-restrictions"></a>Cihaz kısıtlamaları

[Cihaz kısıtlamaları](device-restrictions-configure.md) cihazlarda güvenlik, donanım, veri paylaşımı ve daha fazla ayarı denetler. Örneğin, iOS cihaz kullanıcılarının cihazın kamerasını kullanmasını engelleyen bir cihaz kısıtlama profili oluşturun. 

Bu özellik şunları destekler:

- Android
- Android kurumsal
- iOS/ıpados
- Mac OS
- Windows 10 ve üzeri
- Windows 10 ekibi

## <a name="edition-upgrade"></a>Sürüm yükseltme

[Windows 10 sürüm yükseltmeleri](edition-upgrade-configure-windows-10.md), Windows 10'un bazı sürümlerini çalıştıran cihazları otomatik olarak yeni bir sürüme yükseltmenizi sağlar.

Bu özellik şunları destekler:

- Windows 10 ve üzeri

## <a name="education"></a>Eğitim

[Eğitim ayarları - Windows 10](education-settings-configure.md), [Windows Sınav Zamanı uygulamasının](https://education.microsoft.com/gettrained/win10takeatest) seçeneklerini yapılandırır. Bu seçenekleri yapılandırdığınızda, sınav tamamlanana kadar cihazda başka uygulama çalıştırılamaz.

[Eğitim ayarları - iOS](../fundamentals/education-settings-configure-ios-shared.md) sınıfta öğrenimi yönlendirmek ve öğrenci cihazlarını denetlemek için iOS Classroom uygulamasını kullanır. iPad cihazlarını, çok sayıda öğrencinin aynı cihazı paylaşmasını sağlamak için yapılandırabilirsiniz.

## <a name="email"></a>E-posta

[E-posta ayarları](email-settings-configure.md), cihazlarda Exchange ActiveSync e-posta ayarları oluşturur, atar ve izler. E-posta profilleri tutarlılık konusunda yardımcı olur, destek çağrılarını azaltır ve son kullanıcıların, herhangi bir kurulum yapmalarına gerek kalmadan kendi cihazlarından şirket e-postasına erişmelerini sağlar. 

Bu özellik şunları destekler: 

- Android
- Android Kurumsal
- iOS/ıpados
- WVPN profillerinidows Phone 8.1
- Windows 10 ve üzeri

## <a name="endpoint-protection"></a>Endpoint protection

[Windows 10 için Endpoint protection ayarları](../protect/endpoint-protection-windows-10.md) Windows 10 cihazları için BitLocker'ı ve Windows Defender ayarlarını yapılandırır.

Microsoft Intune ile Microsoft Defender Gelişmiş tehdit koruması (WDADTP) eklemek için bkz. [mobil cihaz yönetimi (MDM) araçlarını kullanarak uç noktaları yapılandırma](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints-mdm).

Bu özellik şunları destekler:

- Windows 10 ve üzeri

## <a name="esim-cellular---public-preview"></a>eSIM hücresel - Genel önizleme

[eSIM hücresel profilleri](esim-device-configuration.md), yöneticilere İnternet ve veri erişimi için yönetilen cihazlarınızda mobil İnternet tarifelerini yapılandırma olanağı sağlar. Mobil operatörünüzden etkinleştirme kodlarını aldıktan sonra bu etkinleştirme kodlarını içeri aktarmak ve ardından eSIM uyumlu cihazlarınıza atamak için Intune’u kullanabilirsiniz.

Bu özellik şunları destekler:

- Windows 10 Fall Creators Update ve üzeri

## <a name="extensions"></a>Uzantılardan

[Çekirdek uzantıları](kernel-extensions-overview-macos.md) , yöneticilerin MacOS cihazlarında çekirdek düzeyinde özellik veya program eklemesine olanak tanır. Bu ayarları, belirli bir geliştirici veya iş ortağındaki tüm uzantılara güvenmek veya belirli çekirdek uzantılarına izin vermek üzere yapılandırın.

Bu özellik şunları destekler:

- Mac OS

## <a name="identity-protection"></a>Kimlik koruması

[Kimlik koruması](../protect/identity-protection-configure.md), Windows 10 ve Windows 10 Mobile cihazlarda İş İçin Windows Hello deneyimini denetler. İş İçin Windows Hello’yu kullanıcı ve cihazlar için kullanılabilir kılmak ve cihaz PIN’i ve hareketlerini belirtmek için bu ayarları yapılandırın.  

Bu özellik şunları destekler:  

- Windows 10 ve üzeri
- Windows 10 Holographic for Business  

## <a name="kiosk"></a>Bilgi noktası

[Bilgi noktası ayarları](kiosk-settings.md) profili, cihazı tek uygulama veya birden çok uygulama çalıştıracak şekilde yapılandırır. Ayrıca bilgi noktanızda başlat menüsü ve web tarayıcısı gibi diğer özellikleri de özelleştirebilirsiniz.

Bu özellik şunları destekler:

- Windows 10 ve üzeri

Bilgi noktası ayarları [Android](device-restrictions-android.md#kiosk), [Android Kurumsal](device-restrictions-android-for-work.md#dedicated-device-settings) ve [ios](device-restrictions-ios.md#kiosk) için cihaz kısıtlaması olarak da kullanılabilir.

## <a name="oemconfig"></a>OEMConfig

[OEMConfig](android-oem-configuration-overview.md), OEM'lerin (orijinal ekipman üreticileri) ve EMM'lerin (kurumsal mobil yönetim), OEM'e özgü özellikleri Android Kurumsal cihazlarda standart bir şekilde geliştirme ve destekleme imkanı sunan bir standarttır. OEMConfig ile bir OEM, OEM'e özgü yönetim özelliklerini tanımlayan bir şema oluşturur ve bunu Google Play'e yüklenen bir uygulamaya ekler. Intune, uygulamadaki şemayı okur ve Intune yöneticilerinin şemada bu ayarları yapılandırmasını sağlar.

Bu özellik şunları destekler:

- Android Kurumsal (OEMConfig)

## <a name="powershell-scripts"></a>PowerShell betikleri

[Windows 10 cihazlarında PowerShell betikleri](../apps/intune-management-extension.md) , Intune 'da PowerShell betiklerinizi karşıya yüklemek Için Intune yönetim uzantısını kullanır ve ardından bu betikleri cihazlarınızda çalıştırır. Ayrıca, uzantıyı kullanmak için gerekenleri, Intune 'a nasıl ekleneceğini ve diğer önemli bilgileri görün.


Bu özellik şunları destekler:

- Windows 10 ve üzeri
- Windows 10 Holographic for Business

## <a name="shared-multi-user-device"></a>Paylaşılan çok kullanıcılı cihaz

[Windows 10](shared-user-device-settings-windows.md) ve [Windows Holographic for Business](shared-user-device-settings-windows-holographic.md), paylaşılan cihazlar veya paylaşılan bilgisayarlar olarak da bilinen ve birden fazla kişinin kullandığı cihazları yönetmek için kullanabileceğiniz ayarlar sunar. Cihazda oturum açan kullanıcıların uykuya geçme seçeneklerini değiştirme veya cihaza dosya kaydetme konusunda yetki sahibi olup olmayacağını belirleyebilirsiniz. Bir diğer örnekte de yer kazanmak için Windows HoloLens cihazlardaki etkin olmayan kimlik bilgilerini silen bir profil oluşturabilirsiniz.

Bu paylaşılan çok kullanıcılı cihaz ayarları, yöneticilere cihazın bazı özelliklerini denetleme ve bu paylaşılan cihazları Intune kullanarak yönetme imkanı tanır.

Bu özellik şunları destekler:

- Windows 10 ve üzeri
- Windows 10 Holographic for Business

## <a name="update-policies"></a>Güncelleştirme ilkeleri

[iOS güncelleştirme ilkeleri](../software-updates-ios.md), iOS cihazlarınıza yazılım güncelleştirmelerini yüklemek için iOS ilkelerini nasıl oluşturacağınızı ve atayacağınızı gösterir. Ayrıca yükleme durumunu da gözden geçirebilirsiniz.

Windows cihazlardaki güncelleştirme ilkeleri hakkında bilgi için bkz. [Teslim iyileştirme](../delivery-optimization-windows.md). 

Bu özellik şunları destekler:

- iOS/ıpados

## <a name="vpn"></a>VPN

[VPN ayarları](vpn-settings-configure.md), kuruluşunuzdaki kullanıcılara ve cihazlara VPN profilleri atar, böylece ağa kolayca ve güvenli bir şekilde bağlanabilirler. 

Sanal özel ağlar (VPN’ler), kullanıcılara şirket ağınıza güvenli uzaktan erişim vermenize olanak tanır. Cihazlar VPN sunucunuzla bağlantı başlatmak için VPN bağlantısı profilini kullanır. 

Bu özellik şunları destekler: 

- Android
- Android Kurumsal
- iOS/ıpados
- Mac OS
- WVPN profillerinidows Phone 8.1
- Windows 8.1
- Windows 10 ve üzeri

## <a name="wi-fi"></a>Wi-Fi

[Wi-Fi ayarları](wi-fi-settings-configure.md), kullanıcılar ve cihazlar için kablosuz ağ ayarları atar. Bir Wi-Fi profili atadığınızda, kullanıcılar kurumsal Wi-Fi ağınıza, ağı kendileri yapılandırmak zorunda kalmadan erişim elde eder. 

Bu özellik şunları destekler: 

- Android
- Android Kurumsal
- iOS/ıpados
- Mac OS
- Windows 8.1 (yalnızca içeri aktarma)
- Windows 10 ve üzeri

## <a name="windows-information-protection-profile"></a>Windows Bilgi Koruması profili

[Windows Bilgi Koruması](../protect/windows-information-protection-configure.md), çalışanın deneyimine müdahale etmeden veri sızıntılarına karşı koruma sağlamaya yardımcı olur. Ayrıca, çalışanların işte kullandıkları kuruluşa ait cihazlardaki ve kişisel cihazlardaki kazayla veri sızıntılarına karşı kurumsal uygulamaların ve verilerin korunmasına yardımcı olur. Windows Bilgi Koruması'nı kullanmak için ortamınızda veya uygulamalarınızda değişiklik yapmanız gerekmez.

Bu özellik şunları destekler:

- Windows 10 ve üzeri

## <a name="zebra-mobility-extensions-mx"></a>Zebra Mobility Uzantıları (MX)

[Zebra Mobility Uzantıları (MX)](android-zebra-mx-overview.md), yöneticilerin Zebra cihazları Intune'dan kullanmasını ve yönetmesini sağlar. Ayarlarınızla StageNow profilleri oluşturabilir ve ardından Intune'u kullanarak bu profilleri Zebra cihazlarınıza atayabilir ve dağıtabilirsiniz. [StageNow günlükleri ve yaygın sorunlar](android-zebra-mx-logs-troubleshoot.md) sayfasında profillerle ilgili sorun giderme adımlarını ve StageNow kullanırken karşılaşabileceğiniz potansiyel sorunları inceleyebilirsiniz.

Bu özellik şunları destekler:

- Android (Mobility Uzantıları)

## <a name="manage-and-troubleshoot"></a>Yönetme ve sorun giderme

[Profillerinizi yöneterek](../device-profile-monitor.md) cihazların ve atanan profillerin durumunu denetleyin. Ayrıca, çakışma yaratan ayarları ve bu ayarları içeren profilleri görerek çakışmaların çözümlenmesine yardımcı olun. [Sık karşılaşılan sorunlar ve çözümleri](device-profile-troubleshoot.md) sayfası, yöneticilere profiller üzerinde çalışma konusunda yardımcı olur. Profil sildiğinizde gerçekleşen işlemleri, cihazlara bildirim gönderilmesine neden olan işlemleri ve daha fazlasını anlatmaktadır.

## <a name="next-steps"></a>Sonraki adımlar

Platformunuzu seçin ve kullanmaya başlayın.
