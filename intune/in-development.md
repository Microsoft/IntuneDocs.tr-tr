---
title: Geliştirme - Intune
titlesuffix: ''
description: Geliştirme Intune özellikleri
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/04/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9c377a8558b1f318b4ddad735b6368a291e34516
ms.sourcegitcommit: 3abc3bb93a95a81154146325c26c119a784e7487
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57756828"
---
# <a name="in-development-for-microsoft-intune---march-2019"></a>Microsoft Intune - Mart 2019 geliştirme

İçinde hazırlık ve planlama, bu sayfa yardımcı olmak için Intune kullanıcı Arabirimi güncelleştirmeleri ve özelliklerinin listesi geliştirme aşamasındadır ancak henüz serbest. Buna ek olarak:

- Bir değişiklik önce harekete gerekecektir tahmin, biz firmalar Office ileti Merkezi'nde post yayınlayacaksınız.
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
 
## <a name="intune-in-the-azure-portal"></a>Azure portalında Intune


<!-- 1903 start-->

### <a name="encryption-report-----2351538---"></a>Şifreleme raporu  <!-- 2351538 -->
Cihazlarınızı şifreleme durumu hakkındaki ayrıntıları görüntülemek için yeni bir şifreleme rapor kullanmanız mümkün olacaktır. Kullanılabilir ayrıntı cihazlar TPM sürümü, şifreleme hazırlık ve durumu, hata raporlama ve daha fazlasını içerir.  

### <a name="access-bitlocker-recovery-keys-from-the-intune-portal-----2351547----"></a>BitLocker kurtarma anahtarlarını Intune portalından erişim  <!-- 2351547  -->
Gelen Azure Active Directory (AAD) BitLocker anahtarı kimliği ve BitLocker kurtarma anahtarları hakkında ayrıntılar görüntüleyebileceğiniz cihazlarında, yeni bir giriş noktası ekliyoruz.

### <a name="scope-tags-for-app-configuration-policies---2371891---"></a>Kapsam etiketleri için uygulama yapılandırma ilkeleri <!--2371891 -->
Kişiler de bu kapsam etiketi atanan rollerle yalnızca uygulama yapılandırma İlkesi erişimi için bir uygulama yapılandırma ilkesi için bir kapsam etiketi ekleyin mümkün olacaktır. Uygulama yapılandırma ilkesini yalnızca hedeflenen veya aynı kapsam etiketi atanan uygulamalarla ilişkili.

### <a name="assign-autopilot-profiles-to-the-all-devices-virtual-group---2715522---"></a>Tüm cihazlar sanal grubuna Autopilot profilleri atama <!--2715522 -->
Tüm cihazlar sanal grubuna Autopilot profilleri atayabileceksiniz. Bunu yapmak için **Cihaz kaydı** > **Windows kaydı** > **Dağıtım Profilleri**'i seçin > bir profil seçin > **Atamalar**'ı seçin > **Atama hedefi** altından **Tüm cihazlar**'ı seçin. Autopilot profilleri hakkında daha fazla bilgi için bkz. [Windows AutoPilot kullanarak Windows cihazları kaydetme](enrollment-autopilot.md).

### <a name="install-available-apps-using-the-company-portal-app-after-windows-bulk-enrollment----2751523----"></a>Windows toplu kaydı sonra Şirket portalı uygulamasını kullanırken kullanılabilir uygulamaları yüklemesi <!-- 2751523  -->
Intune kullanarak kayıtlı Windows cihazları [Windows toplu kayıt](windows-bulk-enroll.md) (sağlama paketlerinin) kullanılabilir uygulamaları yüklemesi için Şirket portalı uygulamasını kullanmanız mümkün olacaktır. Şirket portalı uygulaması hakkında daha fazla bilgi için bkz. [el ile Windows 10 Şirket portalı ekleme](store-apps-company-portal-app.md) ve [Microsoft Intune Şirket portalı uygulamasını yapılandırma](company-portal-app.md).

### <a name="scope-tags-for-ios-app-provisioning-profiles---2934430---"></a>Kapsam etiketleri için iOS uygulama sağlama profilleri <!--2934430 -->
Kapsam etiketi, bir iOS uygulama sağlama profili ekleyebilirsiniz, böylece yalnızca kişiler de bu kapsam etiketi atanan rollerle iOS uygulama sağlama profili erişimi mümkün olacaktır. 

### <a name="office-deployment-tool-odt-xml-for-office-proplus-deployment----3192477----"></a>Office dağıtım aracı (ODT) Office ProPlus dağıtım için XML <!-- 3192477  -->
Office dağıtım aracı (ODT) XML örneği Office Pro Plus Intune Yönetici konsolunda oluştururken sağlamanız. Mevcut Intune kullanıcı Arabirimi seçenekleri ihtiyaçlarınızı karşılamıyorsa Bunun büyük sağlamadığından olanak tanır. 

###  <a name="block-users-from-scanning-for-windows-updates-------3316758------"></a>Windows güncelleştirmeleri için tarama kullanıcıların engelle    <!-- 3316758    -->
Kullanıcıların Windows güncelleştirmeleri için tarama engeller, kullanabileceğiniz ayarı bir yeni Windows güncelleştirme halkası ekliyoruz. Bu ayar, portalın içinde kullanılabilir durumda olmaz ancak Intune Graph API'si kullanılarak yapılandırılabilir.

### <a name="windows-update-notifications-----3316782---"></a>Windows güncelleştirme bildirimleri  <!-- 3316782 -->
Kullanıcıların görmesi Windows güncelleştirme bildirimleri yapılandırmak için bu sayede, Windows güncelleştirme halkası yapılandırmaları için destek ekliyoruz. Bu ayar, portalın içinde kullanılabilir durumda olmaz ancak Intune Graph API'si kullanılarak yapılandırılabilir.

### <a name="changes-to-company-portal-enrollment-for-ios-12-device-users---3448635---"></a>İOS için Şirket portalı kaydı için 12 cihaz kullanıcılarının değiştirir. <!--3448635 -->  
İOS için Şirket portalı uygulamasının kayıt ekranları ve Apple iOS 12.2 yayımlanan MDM kayıt değişiklikleri hizalamak için adımları güncelleştiriliyor. Güncelleştirilmiş iş akışı, kullanıcılar artık ister:

- Safari (aracılığıyla Safari) şirket Portalı Web sitesini açın ve Şirket portalı uygulamasında döndürmeden önce yönetim profili yüklemek izin verin. 
- Yönetim profili cihaza yüklemek üzere ayarlar uygulamasını açın.
- Şirket portalı uygulamasının kaydı döndürür.  

Bu değişikliklerin nasıl hazırlama hakkında daha fazla bilgi için bkz. [Microsoft Tech Community post](https://techcommunity.microsoft.com/). Bu sırada, şirket Portalı'nda yeni iOS kayıtları desteklemek için adımları güncelleştirdik [iOS Cihazınızı Intune'a kaydetme](https://docs.microsoft.com/en-us/intune/ios-enroll). Bu docs değişiklikler, Apple iOS sürüm 12.2 yayımlandıktan sonra canlı olacaktır. 

### <a name="support-for-additional-connectors-on-the-tenant-status-page----3617202-------"></a>Kiracı durumu sayfasında ek bağlayıcı desteği <!-- 3617202     -->
Kiracı durumu sayfası dahil olmak üzere, ek bağlayıcıları için durum bilgilerini görüntüler *Windows Defender Gelişmiş tehdit koruması* (ATP) ve diğer Mobile Threat Defense bağlayıcıları.

### <a name="granting-intune-read-only-access-to-some-azure-active-directory-roles----3637917---"></a>Intune verme yalnızca bazı Azure Active Directory rolleri için okuma erişimi <!-- 3637917 -->
Biz Intune yalnızca aşağıdaki Azure AD rollerine okuma erişimi veriyor. Azure AD rolleri ile verilen izinler, Intune rol tabanlı erişim denetimi (RBAC) izinler yerini alır.

Yalnızca Intune denetim verilerine erişim okuyun:

- Uyumluluk Yöneticisi
- Uyumluluk veri Yöneticisi

Yalnızca tüm Intune verilerine erişim okuyun:

- Güvenlik Yöneticisi
- Güvenlik işleci
- Güvenlik okuyucusu
- Genel okuyucusu

### <a name="easier-access-to-diagnostic-settings------3804627-----"></a>Daha kolay erişim için tanılama ayarları   <!-- 3804627   -->
Yeni bir seçenek ekliyoruz **denetim günlükleri** dikey penceresinde her denetim günlüğü iş yükünde, doğrudan açmak için kullanabileceğiniz Intune konsolundaki her *tanılama ayarları* sayfası.

### <a name="create-and-use-device-configuration-profiles-on-android-zebra-devices-in-intune----3895244----"></a>Oluşturma ve Zebra Android cihazlarda ıntune cihaz yapılandırma profillerini kullanma <!-- 3895244  -->
Intune, Android Zebra cihazların yapılandırılmasını destekler. Özellikle, sizin için mümkün olacaktır: 

- Bir cihaz yapılandırma profili oluşturma ve ayarlar StageNow tarafından oluşturulan Mobility Uzantıları (MX) profilleri kullanarak Zebra Android cihazları için geçerlidir (**cihaz Yapılandırması** > **profilleri**  >  **Profili oluşturma** > **Android** platform için).

Uygulama hedefi:  
- Android

<!-- 1901 start -->

### <a name="deployment-of-online-licensed-microsoft-store-for-business-apps----1672660----"></a>İş uygulamalarına yönelik çevrimiçi lisanslı Microsoft Store dağıtımı <!-- 1672660  -->
Gerekli çevrimiçi lisanslı Microsoft Store cihaz bağlamında kurumsal uygulamalar için atayamazsınız olacaktır. Bu şekilde bir iş uygulaması için Microsoft Store dağıtımı, cihazdaki tüm kullanıcılar için yüklenecek uygulamayı etkinleştirir. Bu yalnızca Windows 10 RS4 + Masaüstü cihazları için geçerlidir. Cihaz bağlamında yükleme seçeneği, istemci uygulamaları atama sayfasında MSFB çevrimiçi lisanslı uygulamaları için kullanılabilir.

## <a name="notices"></a>Bildirimler

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

### <a name="see-also"></a>Ayrıca bkz.
Son geliştirmelere ilişkin ayrıntılar için bkz. [Microsoft Intune’daki Yenilikler](whats-new.md).
