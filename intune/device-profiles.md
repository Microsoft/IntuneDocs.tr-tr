---
title: Microsoft Intune - Azure’da cihaz profilleri | Microsoft Docs
description: Özellikler, kısıtlamalar, e-posta, wifi, VPN, eğitim, sertifikalar, Windows 10, BitLocker ve Windows defender, Windows Bilgi Koruması ve Azure portalındaki özel cihaz yapılandırma ayarları gibi farklı Microsoft Intune cihaz profillerine genel bakış. Şirketinizdeki verileri ve cihazları yönetmek ve korumak için bu profili kullanın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/22/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e92a10f51fb403c802c1c6d3ea79ccf49a1e93fb
ms.sourcegitcommit: a22309174e617e59ab0cdd0a55abde38711a5f35
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/23/2018
---
# <a name="what-are-microsoft-intune-device-profiles"></a>Microsoft Intune cihaz profilleri nedir?

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Microsoft Intune, kuruluşunuzdaki farklı cihazlarda etkinleştirebileceğiniz veya devre dışı bırakabileceğiniz ayarları ve özellikleri içerir. Bu ayarlar ve özellikler, profiller kullanılarak yönetilir. Bazı profil örnekleri şunlardır: 

- Kurumsal WiFi'nize farklı cihazlara erişim sağlayan bir WiFi profili
- Kurumsal ağınızda VPN sunucunuza farklı cihaz erişimi veren bir VPN profili

Bu konu, cihazlarınız için oluşturabileceğiniz farklı profillere genel bir bakış sunar. Cihazlardaki bazı özelliklere izin vermek veya bunları engellemek için bu profilleri kullanın.

## <a name="before-you-begin"></a>Başlamadan önce
Kullanılabilir özellikleri görmek için [Azure portalı](https://portal.azure.com)'nı açın ve Intune kaynağınızı açın. 

**Cihaz yapılandırması** aşağıdaki seçenekleri içerir:

- **Genel Bakış**: Profillerinizin durumunu listeler, kullanıcılara ve cihazlara atadığınız profiller hakkında ek ayrıntılar sağlar
- **Yönet**: Cihaz profilleri oluşturun ve profil içinde çalışmak üzere özel [PowerShell betiklerini](intune-management-extension.md) karşıya yükleyin
- **İzle**: Bir profilin başarı veya başarısızlık durumunu denetleyin ve ayrıca profillerinize ilişkin günlükleri görüntüleyin
- **Kurulum**: Bir sertifika yetkilisi (SCEP veya PFX) ekleyin veya profilde Telekomünikasyon Gider Yönetimi’ni etkinleştirin

## <a name="create-the-profile"></a>Profili oluşturma

[Cihaz profilleri oluşturma](device-profile-create.md), bir profil oluşturmak için adım adım yönergeler sağlar. 

## <a name="device-features-profile"></a>Cihaz özellikleri profili

[Cihaz özellikleri](device-features-configure.md), iOS ve macOS cihazlarda AirPrint, bildirimler ve paylaşılan cihaz yapılandırmaları gibi özellikleri denetler.

Bu özellik şunları destekler:  
- iOS 
- Mac OS

## <a name="device-restrictions-profile"></a>Cihaz kısıtlamaları profili
[Cihaz kısıtlamaları](device-restrictions-configure.md) cihazlarda güvenlik, donanım, veri paylaşımı ve daha fazla ayarı denetler. Örneğin, iOS cihaz kullanıcılarının cihazın kamerasını kullanmasını engelleyen bir cihaz kısıtlama profili oluşturun. 

Bu özellik şunları destekler: 

- Android
- iOS
- Mac OS
- Windows 10
- Windows 10 Team

## <a name="email-profile"></a>E-posta profili
[E-posta ayarları](email-settings-configure.md) profili, cihazlarda Exchange ActiveSync e-posta ayarları oluşturur, atar ve izler. E-posta profilleri tutarlılık sağlar, destek çağrılarını azaltır ve son kullanıcıların, herhangi bir kurulum yapmalarına gerek kalmadan kendi cihazlarından şirket e-postasına erişmelerini sağlar. 

Bu özellik şunları destekler: 

- Android
- iOS
- Windows Phone 8.1
- Windows 10

## <a name="wi-fi-profile"></a>Wi-Fi profili
[Wi-Fi ayarları](wi-fi-settings-configure.md), kullanıcılar ve cihazlar için kablosuz ağ ayarları atar. Bir Wi-Fi profili atadığınızda, kullanıcılar kurumsal Wi-Fi ağınıza, ağı kendileri yapılandırmak zorunda kalmadan erişim elde eder. 

Bu özellik şunları destekler: 

- Android
- iOS
- Mac OS
- Windows 8.1 (yalnızca içeri aktarma)

## <a name="vpn-profile"></a>VPN profili
[VPN ayarları](vpn-settings-configure.md), kuruluşunuzdaki kullanıcılara ve cihazlara VPN profilleri atar, böylece ağa kolayca ve güvenli bir şekilde bağlanabilirler. 

Sanal özel ağlar (VPN’ler), kullanıcılara şirket ağınıza güvenli uzaktan erişim vermenize olanak tanır. Cihazlar VPN sunucusuyla bir bağlantı başlatmak için bir VPN bağlantısı profili kullanır. 

Bu özellik şunları destekler: 

- Android
- iOS
- Mac OS
- Windows Phone 8.1
- Windows 8.1
- Windows 10

## <a name="education-profile"></a>Eğitim profili
[Eğitim ayarları](education-settings-configure.md), [Windows Sınav Zamanı uygulamasının](https://education.microsoft.com/gettrained/win10takeatest) seçeneklerini yapılandırır. Bu seçenekleri yapılandırdığınızda, sınav tamamlanana kadar cihazda başka uygulama çalıştırılamaz.

## <a name="certificates-profile"></a>Sertifika profili
[Sertifikalar](certificates-configure.md), cihazlara atanabilen ve Wi-Fi, VPN ve e-posta profillerinin kimliğini doğrulamak için kullanılan güvenilen, SCEP ve PKCS sertifikalarını yapılandırır.

Bu özellik şunları destekler: 

- Android
- iOS
- Windows Phone 8.1
- Windows 8.1
- Windows 10

## <a name="edition-upgrade-profile"></a>Sürüm yükseltme profili
[Windows 10 sürüm yükseltmeleri](edition-upgrade-configure-windows-10.md), Windows 10'un bazı sürümlerini çalıştıran cihazları otomatik olarak yeni bir sürüme yükseltmenizi sağlar.

Bu özellik şunları destekler: Yalnızca Windows 10

## <a name="endpoint-protection-profile"></a>Endpoint protection profili
[Windows 10 için Endpoint protection ayarları](endpoint-protection-windows-10.md) Windows 10 cihazları için BitLocker'ı ve Windows Defender ayarlarını yapılandırır.

Microsoft Intune'a Windows Defender Gelişmiş Tehdit Koruması'nı (WDATP) eklemek için bkz. [Mobil Cihaz Yönetimi (MDM) araçlarını kullanarak uç noktaları yapılandırma](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/configure-endpoints-mdm-windows-defender-advanced-threat-protection).

Bu özellik şunları destekler: Yalnızca Windows 10

## <a name="windows-information-protection-profile"></a>Windows Bilgi Koruması profili
[Windows Bilgi Koruması](windows-information-protection-configure.md), çalışanın deneyimine müdahale etmeden veri sızıntılarına karşı koruma sağlamaya yardımcı olur. Ayrıca, çalışanların işte kullandıkları kuruluşa ait cihazlardaki ve kişisel cihazlardaki kazayla veri sızıntılarına karşı kurumsal uygulamaların ve verilerin korunmasına yardımcı olur. Bunu ortamınızda veya diğer uygulamalarda değişiklik yapmaya gerek kalmadan yapar.

Bu özellik şunları destekler: Yalnızca Windows 10

## <a name="custom-profile"></a>Özel profil
[Özel ayarlar](custom-settings-configure.md), Intune’da yerleşik olarak sağlanmayan cihaz ayarlarını atamanıza olanak tanır. Örneğin, Android cihazlarda, OMA-URI değerleri girebilirsiniz. iOS cihazları için, Apple Configurator’da oluşturduğunuz bir yapılandırma dosyasını içeri aktarabilirsiniz. 

Bu özellik şunları destekler:

- Android
- iOS
- Mac OS
- Windows Phone 8.1