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
ms.openlocfilehash: 6c88dca505c3ef9d9d552e55e9991679f5f5e0fa
ms.sourcegitcommit: 5968a38c302394d4b0cf81156e7b52531cdec107
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/23/2019
ms.locfileid: "71198829"
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

### <a name="company-portal-app-installation-status-messages----2514416----"></a>Uygulama yükleme durum iletilerini Şirket Portalı <!-- 2514416  -->
Şirket Portalı uygulama son kullanıcılara ek uygulama yükleme durumu iletileri gösterecektir. Yeni Win32 bağımlılık özellikleri için aşağıdaki koşullar geçerli olacaktır:
- Uygulama yüklenemedi. Yönetici tarafından tanımlanan bağımlılıklar karşılanmadı.
- Uygulama başarıyla yüklendi, ancak yeniden başlatma gerekiyor.
- Uygulama yükleme sürecinde, ancak devam etmek için yeniden başlatma gerekiyor.

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

### <a name="configure-app-notification-content-for-organization-accounts----2576686---"></a>Kuruluş hesapları için uygulama bildirim içeriğini yapılandırma <!-- 2576686 -->
Android ve iOS cihazlarında Intune uygulama koruma ilkeleri (uygulama), kuruluş hesapları için uygulama bildirim içeriğini denetlemenize olanak tanır. Bu özellik, uygulamalardan destek isteyecek ve UYGULAMANıN etkin olduğu tüm uygulamalarda kullanılamayabilir. UYGULAMA hakkında daha fazla bilgi için bkz. [Uygulama koruma ilkeleri nelerdir?](app-protection-policy.md).

### <a name="available-google-play-app-reporting-for-android-work-profiles----3041956----"></a>Android iş profilleri için kullanılabilir Google Play uygulama raporlaması <!-- 3041956  -->
Android iş profili cihazlarına kullanılabilir uygulama yüklemeleri için, uygulama yükleme durumunu ve yönetilen Google Play uygulamalarının yüklü sürümünü görüntüleyebilirsiniz. Daha fazla bilgi için bkz. [Uygulama koruma ilkelerini izleme](app-protection-policies-monitor.md), [Android Iş profili cihazlarını Intune ile yönetme](android-enterprise-overview.md) ve [uygulama türü ile yönetilen Google Play](apps-add-android-for-work.md#managed-google-play-app-types).

<!-- ***********************************************-->
<!--## Device configuration-->

<!-- ***********************************************-->
## <a name="device-enrollment"></a>Cihaz kaydı

### <a name="for-ios-devices-customize-the-enrollment-process-privacy-screen-of-the-company-portal----4394993----"></a>İOS cihazları için Şirket Portalı kayıt işlemi gizlilik ekranını özelleştirin <!-- 4394993  -->
Marku kullanarak, son kullanıcıların iOS kaydı sırasında göreceği Şirket Portalı gizlilik ekranını özelleştirebileceksiniz. Özellikle, kuruluşunuzun cihazı göremeyecek veya cihaz üzerinde yapaamayacak işlerin listesini özelleştirebilirsiniz.

<!-- ***********************************************-->
## <a name="device-management"></a>Cihaz yönetimi

### <a name="deploy-software-updates-to-macos-devices----3194876---"></a>MacOS cihazlarına yazılım güncelleştirmeleri dağıtma <!-- 3194876 -->
MacOS cihazları gruplarına yazılım güncelleştirmeleri dağıtabileceksiniz. Bu özellik kritik, bellenim, yapılandırma dosyası ve diğer güncelleştirmeleri içerir. Güncelleştirmeleri bir sonraki cihaz iadede gönderebilecek veya zaman içinde güncelleştirmeleri dağıtmak için haftalık bir zamanlama seçebileceğiniz şekilde ayarlayabilirsiniz. Bu, standart çalışma saatleri dışında veya yardım masanıza tam olarak çalıştırıldığında cihazları güncelleştirmek istediğinizde yardımcı olur. Ayrıca güncelleştirmelerin dağıtıldığı tüm macOS cihazlarının ayrıntılı bir raporunu alırsınız. Belirli güncelleştirmelerin durumlarını görmek için, raporu cihaz başına temelinde inceleyebilirsiniz.

<!-- ***********************************************-->
## <a name="monitor-and-troubleshoot"></a>İzleme ve sorun giderme

### <a name="updated-support-experience-------5012398------"></a>Güncelleştirilmiş destek deneyimi   <!--  5012398    -->
Geliştirmeye devam etmenin bir parçası olarak, Intune için konsol içi destek deneyimini güncelleştiriyoruz.  Genel sorunlar için konsol içi aramayı ve geri bildirimleri geliştireceğiz ve desteğe başvurmak için iş akışını kolaylaştırıyoruz.     

<!-- ***********************************************-->
<!--## Security-->


<!-- ***********************************************-->
## <a name="notices"></a>Bildirimler

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

## <a name="see-also"></a>Ayrıca bkz.
Son geliştirmelere ilişkin ayrıntılar için bkz. [Microsoft Intune’daki Yenilikler](whats-new.md).




