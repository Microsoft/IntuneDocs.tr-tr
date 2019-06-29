---
title: Geliştirme - Intune
titleSuffix: ''
description: Geliştirme Intune özellikleri
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/28/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 633bf52084ad261f768cb4e59aaf4ce0ab5cd5bc
ms.sourcegitcommit: 46f4d3d160e18aeab9de7477eedc8351fbb78c85
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2019
ms.locfileid: "67468721"
---
# <a name="in-development-for-microsoft-intune---july-2019"></a>Microsoft Intune - Temmuz 2019 geliştirme

İçinde hazırlık ve planlama, bu sayfa yardımcı olmak için Intune kullanıcı Arabirimi güncelleştirmeleri ve özelliklerinin listesi geliştirme aşamasındadır ancak henüz serbest. Buna ek olarak:

- Bir değişiklik önce harekete gerekecektir tahmin, biz tamamlayıcı bir Office ileti Merkezi'nde gönderi yayınlayacaksınız.
- Ne zaman bir özellik, üretimde ya da önizleme olarak başlatılır veya genel kullanıma sunulan özellik açıklaması bu sayfayı kapatmak ve üzerine taşınır [yenilikler](whats-new.md).
- Bu sayfada ve [yenilikler](whats-new.md) düzenli olarak güncelleştirilir. Ek güncelleştirmeleri daha sonra denetleyin.
- Başvurmak [M365 yol haritası](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS) stratejik teslim edilebilirleri ve zaman çizelgeleri için.

> [!Note]
> Bu öğeler, gelecekteki bir sürümde sunulacak Intune özellikleri hakkında daha fazla geçerli beklentileri Microsoft'un yansıtır. Tarih ve tek tek özellikler değişebilir. Geliştirme tüm öğeler, bu sayfada bir özellik açıklaması içerir.

**RSS akışı**: Bu sayfa aşağıdaki URL'yi kullanarak akış okuyucuya yapıştırarak güncelleştirildiğinde bildirim alın: `https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`

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

### <a name="device-users-can-view-all-managed-apps-theyve-installed-or-tried-to-install----2352913---"></a>Cihaz kullanıcılarının yüklü veya yüklemeyi denedi tüm yönetilen uygulamalar görüntüleyebilirsiniz. <!-- 2352913 -->
Bir kullanıcı cihazında yüklü (gerekli ve kullanılabilir) tüm yönetilen uygulamalar için Şirket portalı Windows listeler. Kullanıcılar, denenen görüntülemek ve bekleyen uygulama yüklemelerini ve bunların geçerli durumlarını mümkün olacaktır. Kuruluşunuzun uygulamalarını gerekli veya kullanılabilir duruma getirilmez, kullanıcılar şirket uygulama yüklenmiş olduğunu açıklayan bir ileti görür. Kullanıcılar ayrıca sıralamak veya uygulamalarını yükleme durumuna göre filtre uygulamak mümkün olacaktır.

### <a name="customized-notifications-for-users-and-groups-------16766574-----"></a>Kullanıcılar ve gruplar için özelleştirilmiş bildirimleri    <!-- 16766574   -->
İOS ve Android cihazlarda Intune ile yönettiğiniz kullanıcılar Şirket portalı uygulamasından özel geçici anında iletme bildirimleri göndermek mümkün olan en kısa sürede olacaktır. Bu özel bildirimleri belirli Intune özelliklerine bağlı değil ve gerektiren bazı göndermek istediğiniz genel bildirimleri dahil olmak üzere herhangi bir amaçla kullanılabilir veya tüm çalışanlar.  

### <a name="configure-app-notification-content-for-organization-accounts----2576686---"></a>Uygulama bildirimi içeriği kuruluş hesapları için yapılandırma <!-- 2576686 -->
Android ve iOS cihazlarında Intune uygulama koruma ilkelerini (APP), kuruluş hesapları için denetimi uygulama bildirimi içeriği için izin verir. Bu özellik, uygulamalardan desteği gerektirir ve tüm APP etkin uygulamalar için kullanılamıyor olabilir. Uygulama hakkında daha fazla bilgi için bkz. [uygulama koruma ilkeleri nelerdir?](app-protection-policy.md).

### <a name="available-google-play-app-reporting-for-android-work-profiles----3041956----"></a>Android iş profilleri için raporlama kullanılabilir Google Play uygulaması <!-- 3041956  -->
Android iş profili cihazları üzerinde kullanılabilir uygulama yüklemeleri için yönetilen Google Play uygulamaları'nın yüklü sürümü yanı sıra, uygulama yükleme durumunu görüntüleyebilirsiniz. Daha fazla bilgi için [uygulama koruma ilkelerini izleme](app-protection-policies-monitor.md), [yönetme Android iş profili cihazları Intune ile](android-enterprise-overview.md) ve [yönetilen Google Play uygulama türü](apps-add-android-for-work.md#managed-google-play-app-type).

<!-- ***********************************************-->
## <a name="device-configuration"></a>Cihaz yapılandırması


### <a name="support-for-ikev2-vpn-profiles-for-ios----1943438---"></a>İOS için Ikev2 VPN profilleri için destek <!-- 1943438 -->
Ikev2 protokolü kullanarak iOS yerel VPN istemcisi için VPN profillerini oluşturmak mümkün olacaktır. Ikev2, yeni bir bağlantı türü olduğundan **cihaz Yapılandırması** > **profilleri** > **profili oluşturma** > **iOS**  Platform > **VPN** profil türü için > **ayarları**.

Bu VPN profillerini yerel VPN istemcisini yapılandırın. Bu nedenle, hiçbir VPN istemci uygulamaları yüklü veya yönetilen cihazlara gönderildi. Bu özellik cihazlar gerektirir kaydedilmesi gereken Intune'a (MDM kaydı).

Yapılandırabileceğiniz geçerli VPN ayarları görmek için Git [Microsoft Intune iOS cihazlarında VPN yapılandırma ayarları](vpn-settings-ios.md).

Şunun için geçerlidir: iOS

### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910---"></a>"Uygulanabilirlik kuralları" kullandığınızda Windows 10 cihaz yapılandırma profilleri oluşturma <!-- 2549910 -->
Windows 10 cihaz yapılandırma profilleri oluşturma (**cihaz Yapılandırması** > **profilleri** > **profili oluşturma**  >  **Windows 10** platform için). Oluşturma tutulacak bir **Uygulanabilirlik kuralı** profili yalnızca bir belirli sürüm veya belirli bir sürüme uygular. Örneğin, bazı BitLocker ayarları sağlayan bir profil oluşturun. Profili eklediğinizde profil, yalnızca Windows 10 Enterprise çalıştıran cihazlar için uygular bir geçerlilik kuralı kullanın.

Şunun için geçerlidir: 
- Windows 10 ve üzeri

### <a name="administrative-templates-for-group-policy---------3510695---"></a>Grup İlkesi Yönetim Şablonları     <!--  3510695 -->
Bulutta cihazlar için güvenlik geliştirmeye yardımcı olmak için biz Windows bilgisayarlar için select Grup İlkesi ayarlarını yapılandırmak için Intune'u kullanmayı olanak tanıyan Yönetim Şablonları yayımlar.  Bu şablonlar, Office, Windows ve OneDrive 2500 ek ayarlar kadar sağlamak için ilke yapılandırma hizmet sağlayıcısı (CSP) kullanın.

### <a name="manage-filevault-for-macos-------3858502--1210104-----"></a>MacOS için filevault özelliğini yönetme   <!--  3858502 + 1210104   -->
MacOS cihazları için anahtar şifreleme filevault özelliğini yönetmek için Intune endpoint protection cihaz yapılandırma profili kullanmak mümkün olacaktır. Bu, görüntüleme ve kurumsal cihazlarınıza şifreleme anahtarlarını döndürme, emanet içerir. Son kullanıcıların şirket Portalı Web sitesi üzerinden bu anahtarları almak mümkün olacaktır.

### <a name="advanced-settings-for-windows-defender-firewall-------1311949-------"></a>Windows Defender Güvenlik Duvarı için Gelişmiş ayarları   <!--  1311949     -->
Genel önizleme olarak, yakında istemciler için Windows Defender'ın özel bir güvenlik duvarı kurallarını yönetmek için Intune kullanmak mümkün olacaktır.  

### <a name="new-configuration-designer-when-creating-an-oemconfig-profile-for-android-enterprise----3712769----"></a>Android Enterprise için OEMConfig profili oluştururken, yeni yapılandırma Tasarımcısı <!-- 3712769  -->
Intune'da OEMConfig uygulama kullanan bir cihaz yapılandırma profili oluşturabilirsiniz (cihaz yapılandırması > profiller > profil oluşturma > Android Kurumsal platform için > OEMConfig profil türü için). Bunu yaptığınızda, bir şablon ve değerlerini değiştirmenizi ile JSON Düzenleyicisi açılır. Bu güncelleştirme, başlıklarını, açıklamaları ve daha fazlası dahil olmak üzere uygulamada, katıştırılmış ayrıntıları gösteren Gelişmiş bir kullanıcı deneyiminin ile bir yapılandırma Tasarımcısı içerir. JSON düzenleyicisini hala kullanılabilir ve yapılandırma Tasarımcısı'nda yaptığınız tüm değişiklikleri gösterir.

Geçerli ayarları görmek için Git [kullanın ve OEMConfig ile Android kuruluş cihazlarını yönetmek](android-oem-configuration-overview.md).

Şunun için geçerlidir: Android Kurumsal


<!-- ***********************************************-->
## <a name="device-management"></a>Cihaz yönetimi

### <a name="improve-device-location---3855417---"></a>Cihaz konumu geliştirin<!-- 3855417 -->
Kullanarak bir cihaz için tam koordinatları yakınlaştırmak mümkün olacaktır **cihazı Bul** eylem. Kayıp iOS cihazlarını bulma hakkında daha fazla bilgi için bkz. [kayıp iOS cihazlarını bulma](device-locate.md).

### <a name="configure-automatic-device-clean-up-time-limit-down-to-30-days---4231059----"></a>Otomatik cihaz temizleme süresi sınırı 30 gün kadar yapılandırın <!--4231059  -->
Otomatik cihaz temizleme süresi sınırı (yerine, geçerli sınır 90 gün) 30 gün sonra son oturum açma olarak kısa ayarlama mümkün olacaktır. Bunu yapmak için Git **Intune** > **cihazları** > **Kurulum** > **cihaz temiz kuralları'kurmak**.


<!-- ***********************************************-->
## <a name="security"></a>Güvenlik

### <a name="import-and-export-security-baselines------3408610------------"></a>Güvenlik temellerini içeri ve dışarı aktarma    <!--3408610          -->  
Özelliği, özelleştirmelerinizle alın ve bunları Intune ortamlar arasında paylaşmak için güvenlik temellerini içeri ve dışarı ekliyoruz.



<!-- ***********************************************-->
## <a name="notices"></a>Bildirimler

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

## <a name="see-also"></a>Ayrıca bkz.
Son geliştirmelere ilişkin ayrıntılar için bkz. [Microsoft Intune’daki Yenilikler](whats-new.md).


