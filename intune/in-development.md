---
title: Geliştirme-Microsoft Intune
titleSuffix: ''
description: Geliştirmede Microsoft Intune Özellikler
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3c2b9429bf5b50ac5e416c4a7b356627e9cc9fb1
ms.sourcegitcommit: f75386986d24e7d5dd63a3f1a0a014cb52056063
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69560112"
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

### <a name="configure-app-notification-content-for-organization-accounts----2576686---"></a>Kuruluş hesapları için uygulama bildirim içeriğini yapılandırma <!-- 2576686 -->
Android ve iOS cihazlarında Intune uygulama koruma ilkeleri (uygulama), kuruluş hesapları için uygulama bildirim içeriğini denetlemenize olanak tanır. Bu özellik, uygulamalardan destek isteyecek ve UYGULAMANıN etkin olduğu tüm uygulamalarda kullanılamayabilir. UYGULAMA hakkında daha fazla bilgi için bkz. [Uygulama koruma ilkeleri nelerdir?](app-protection-policy.md).

### <a name="available-google-play-app-reporting-for-android-work-profiles----3041956----"></a>Android iş profilleri için kullanılabilir Google Play uygulama raporlaması <!-- 3041956  -->
Android iş profili cihazlarına kullanılabilir uygulama yüklemeleri için, uygulama yükleme durumunu ve yönetilen Google Play uygulamalarının yüklü sürümünü görüntüleyebilirsiniz. Daha fazla bilgi için bkz. [Uygulama koruma ilkelerini izleme](app-protection-policies-monitor.md), [Android Iş profili cihazlarını Intune ile yönetme](android-enterprise-overview.md) ve [uygulama türü ile yönetilen Google Play](apps-add-android-for-work.md#managed-google-play-app-type).

<!-- ***********************************************-->
## <a name="device-configuration"></a>Cihaz yapılandırması

### <a name="support-for-ikev2-vpn-profiles-for-ios----1943438---"></a>İOS için IKEv2 VPN profilleri desteği <!-- 1943438 -->
Ikev2 protokolünü kullanarak iOS Native VPN istemcisi için VPN profilleri oluşturabileceksiniz. Ikev2, **cihaz yapılandırma** > **profillerinde** > yeni bir bağlantı türüdür, profil türü > **ayarları**için **VPN** > Platform için**iOS** **oluşturun** > .

Bu VPN profilleri, yerel VPN istemcisini yapılandırır. Bu nedenle, yönetilen cihazlara yüklenmiş veya hiçbir VPN istemci uygulaması gönderilmez. Bu özellik cihazların Intune 'A (MDM kaydı) kaydedilmesini gerektirir.

Yapılandırabileceğiniz geçerli VPN ayarlarını görmek için [Microsoft Intune iOS CIHAZLARıNDA VPN ayarlarını yapılandırma](vpn-settings-ios.md)bölümüne gidin.

Şunun için geçerlidir: iOS

<!-- ***********************************************-->
## <a name="device-enrollment"></a>Cihaz kaydı

### <a name="for-ios-devices-customize-the-enrollment-process-privacy-screen-of-the-company-portal----4394993----"></a>İOS cihazları için Şirket Portalı kayıt işlemi gizlilik ekranını özelleştirin <!-- 4394993  -->
Marku kullanarak, son kullanıcıların iOS kaydı sırasında göreceği Şirket Portalı gizlilik ekranını özelleştirebileceksiniz. Özellikle, kuruluşunuzun cihazı göremeyecek veya cihaz üzerinde yapaamayacak işlerin listesini özelleştirebilirsiniz.

<!-- ***********************************************-->
## <a name="security"></a>Güvenlik

### <a name="import-and-export-security-baselines------3408610------------"></a>Güvenlik temellerini içeri ve dışarı aktarma    <!--3408610          -->  
Güvenlik temellerini dışarı ve içeri aktarma özelliğini ekliyoruz. Bu özellik, özelleştirmelerinizi sizinle yapmanızı ve bunları Intune ortamları arasında paylaşmanızı sağlar.

<!-- ***********************************************-->
## <a name="notices"></a>Bildirimler

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

## <a name="see-also"></a>Ayrıca bkz.
Son geliştirmelere ilişkin ayrıntılar için bkz. [Microsoft Intune’daki Yenilikler](whats-new.md).




