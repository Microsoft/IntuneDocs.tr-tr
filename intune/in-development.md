---
title: Geliştirme-Microsoft Intune
titleSuffix: ''
description: Geliştirmede Microsoft Intune Özellikler
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/03/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 47e1a3870e1da1514ad07e8dad5c6117ffc108a9
ms.sourcegitcommit: ce9cae824a79223eab3c291fd5d5e377efac84cb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2019
ms.locfileid: "67842711"
---
# <a name="in-development-for-microsoft-intune---july-2019"></a>Microsoft Intune için geliştirme sırasında-Temmuz 2019

Hazırlık ve planlamada yardımcı olması için, bu sayfada Intune Kullanıcı Arabirimi güncelleştirmeleri ve geliştirme aşamasında olan ancak henüz yayınlanmayan özellikler listelenir. Buna ek olarak:

- Bir değişiklikten önce işlem yapmanız gerektiğini tahmin ediyorsanız, tamamlayıcı bir Office Ileti merkezi gönderisini yayımlayacağız.
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


### <a name="customized-notifications-for-users-and-groups-------16766574-----"></a>Kullanıcılar ve gruplar için özelleştirilmiş bildirimler    <!-- 16766574   -->
Yakında, Intune ile yönettiğiniz iOS ve Android cihazlarda kullanıcılara Şirket Portalı uygulamadan özel geçici anında iletme bildirimleri gönderebileceksiniz. Bu özel bildirimler belirli Intune özelliklerine bağlı değildir ve herhangi bir amaçla veya çalışanlarınıza göndermek istediğiniz genel bildirimler dahil olmak üzere, ihtiyacınız olan herhangi bir amaçla kullanılabilir.  

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

### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910---"></a>Windows 10 cihaz yapılandırma profilleri oluştururken "uygulanabilirlik kuralları" nı kullanın <!-- 2549910 -->
Windows 10 cihaz yapılandırma profilleri oluşturun (**cihaz yapılandırma** > **profilleri** > platform için**Windows 10** **profili** > oluşturur). Profil yalnızca belirli bir sürüm veya belirli bir sürüm için geçerli olacak şekilde bir **uygulanabilirlik kuralı** oluşturabileceksiniz. Örneğin, bazı BitLocker ayarlarını sağlayan bir profil oluşturursunuz. Profili ekledikten sonra, profilin yalnızca Windows 10 Enterprise çalıştıran cihazlara uygulanması için bir uygulanabilirlik kuralı kullanın.

Şunun için geçerlidir: 
- Windows 10 ve üzeri

### <a name="manage-filevault-for-macos-------3858502--1210104-----"></a>MacOS için dosya kasasını yönetme   <!--  3858502 + 1210104   -->
MacOS cihazları için dosya Kasası anahtar şifrelemesini yönetmek üzere bir Intune Endpoint Protection cihaz yapılandırma profili kullanabilirsiniz. Bu, kurumsal cihazlarınızın şifreleme anahtarlarını Emanet, görüntüleme ve döndürme bilgilerini içerir. Son kullanıcılar bu anahtarları Şirket Portalı Web sitesinden alabilecektir.

### <a name="advanced-settings-for-windows-defender-firewall-------1311949-------"></a>Windows Defender güvenlik duvarı için Gelişmiş ayarlar   <!--  1311949     -->
Genel önizleme olarak, Windows Defender istemcileri üzerinde özel güvenlik duvarı kurallarını yönetmek için yakında Intune 'u kullanabilirsiniz.  

### <a name="new-configuration-designer-when-creating-an-oemconfig-profile-for-android-enterprise----3712769----"></a>Android Enterprise için bir OEMConfig profili oluştururken yeni yapılandırma Tasarımcısı <!-- 3712769  -->
Intune 'da, bir OEMConfig uygulaması kullanan bir cihaz yapılandırma profili oluşturabilirsiniz (cihaz yapılandırma > profilleri > > SDK için Android Enterprise > profil türü için OEMConfig). Bunu yaptığınızda bir JSON Düzenleyicisi, değiştirmeniz için bir şablon ve değerlerle açılır. Bu güncelleştirme; başlıklar, açıklamalar ve daha fazlası dahil olmak üzere uygulamada Embedded ayrıntıları gösteren gelişmiş bir kullanıcı deneyimine sahip bir yapılandırma Tasarımcısı içerir. JSON Düzenleyicisi hala kullanılabilir ve yapılandırma tasarımcısında yaptığınız tüm değişiklikleri gösterir.

Geçerli ayarları görmek için, bkz. [OEMConfig Ile Android kurumsal cihazlarını kullanma ve yönetme](android-oem-configuration-overview.md).

Şunun için geçerlidir: Android Kurumsal


<!-- ***********************************************-->
## <a name="device-management"></a>Cihaz yönetimi

### <a name="improve-device-location---3855417---"></a>Cihaz konumunu iyileştirme<!-- 3855417 -->
**Cihazı bul** eylemini kullanarak bir cihazın tam koordinatlarına yaklaşabileceksiniz. Kayıp iOS cihazlarını bulma hakkında daha fazla bilgi için bkz. [kayıp iOS cihazlarını bulma](device-locate.md).

### <a name="configure-automatic-device-clean-up-time-limit-down-to-30-days---4231059----"></a>Otomatik cihaz temizleme süresi limitini 30 güne kadar yapılandırma <!--4231059  -->
Otomatik cihaz temizleme süresi sınırını, son oturum açma işleminden sonra 30 gün (geçerli 90 günlük sınırı yerine) kadar kısa bir süre içinde ayarlayabileceksiniz. Bunu yapmak için, **Intune** > **cihazları** > **Kurulum** > **cihaz temizleme kuralları**' na gidin.


<!-- ***********************************************-->
## <a name="security"></a>Güvenlik

### <a name="import-and-export-security-baselines------3408610------------"></a>Güvenlik temellerini içeri ve dışarı aktarma    <!--3408610          -->  
Güvenlik temellerini dışarı ve içeri aktarma özelliğini ekleyeceğiz, böylece özelleştirmelerinizi sizinle alabilir ve bunları Intune ortamları arasında paylaşabilirsiniz.



<!-- ***********************************************-->
## <a name="notices"></a>Bildirimler

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

## <a name="see-also"></a>Ayrıca bkz.
Son geliştirmelere ilişkin ayrıntılar için bkz. [Microsoft Intune’daki Yenilikler](whats-new.md).


