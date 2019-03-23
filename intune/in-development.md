---
title: Geliştirme - Intune
titlesuffix: ''
description: Geliştirme Intune özellikleri
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/20/2019
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
ms.openlocfilehash: 5612ae0ea6c1495fdf12e85bbed80e54bc3f287f
ms.sourcegitcommit: 1069b3b1ed593c94af725300aafd52610c7d8f04
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2019
ms.locfileid: "58394652"
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

### <a name="scope-tags-for-app-configuration-policies---2371891---"></a>Kapsam etiketleri için uygulama yapılandırma ilkeleri <!--2371891 -->
Kişiler de bu kapsam etiketi atanan rollerle yalnızca uygulama yapılandırma İlkesi erişimi için bir uygulama yapılandırma ilkesi için bir kapsam etiketi ekleyin mümkün olacaktır. Uygulama yapılandırma ilkesini yalnızca hedeflenen veya aynı kapsam etiketi atanan uygulamalarla ilişkili.

### <a name="assign-autopilot-profiles-to-the-all-devices-virtual-group---2715522---"></a>AutoPilot profilleri tüm cihazları sanal gruba atayın. <!--2715522 -->
Tüm cihazlar sanal grubuna Autopilot profilleri atayabileceksiniz. Bunu yapmak için **Cihaz kaydı** > **Windows kaydı** > **Dağıtım Profilleri**'i seçin > bir profil seçin > **Atamalar**'ı seçin > **Atama hedefi** altından **Tüm cihazlar**'ı seçin. Autopilot profilleri hakkında daha fazla bilgi için bkz. [Windows AutoPilot kullanarak Windows cihazları kaydetme](enrollment-autopilot.md).

###  <a name="block-users-from-scanning-for-windows-updates-------3316758------"></a>Windows güncelleştirmeleri için tarama kullanıcıların engelle    <!-- 3316758    -->
Kullanıcıların Windows güncelleştirmeleri için tarama engeller, kullanabileceğiniz ayarı bir yeni Windows güncelleştirme halkası ekliyoruz. Bu ayar, portalın içinde kullanılabilir durumda olmaz ancak Intune Graph API'si kullanılarak yapılandırılabilir.

### <a name="windows-update-notifications-----3316782---"></a>Windows güncelleştirme bildirimleri  <!-- 3316782 -->
Kullanıcıların görmesi Windows güncelleştirme bildirimleri yapılandırmak için bu sayede, Windows güncelleştirme halkası yapılandırmaları için destek ekliyoruz. Bu ayar, portalın içinde kullanılabilir durumda olmaz ancak Intune Graph API'si kullanılarak yapılandırılabilir.

### <a name="changes-to-company-portal-enrollment-for-ios-12-device-users---3448635---"></a>İOS için Şirket portalı kaydı için 12 cihaz kullanıcılarının değiştirir. <!--3448635 -->  
İOS için Şirket portalı uygulamasının kayıt ekranları ve Apple iOS 12.2 yayımlanan MDM kayıt değişiklikleri hizalamak için adımları güncelleştiriliyor. Güncelleştirilmiş iş akışı, kullanıcılar artık ister:

- Safari (aracılığıyla Safari) şirket Portalı Web sitesini açın ve Şirket portalı uygulamasında döndürmeden önce yönetim profili yüklemek izin verin. 
- Yönetim profili cihaza yüklemek üzere ayarlar uygulamasını açın.
- Şirket portalı uygulamasının kaydı döndürür.  

Bu değişikliklerin nasıl hazırlama hakkında daha fazla bilgi için bkz. [Microsoft Tech Community post](https://aka.ms/CP_changes_iOS12). Bu sırada, şirket Portalı'nda yeni iOS kayıtları desteklemek için adımları güncelleştirdik [iOS Cihazınızı Intune'a kaydetme](https://docs.microsoft.com/en-us/intune/ios-enroll). Apple iOS sürüm 12.2 yayımlandıktan sonra bu belge değişiklikleri Canlı olacaktır. 

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
