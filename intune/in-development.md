---
title: Geliştirme - Intune
titleSuffix: ''
description: Geliştirme Intune özellikleri
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/15/2019
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
ms.openlocfilehash: 004ebad5276575fe9f5b580d13db188f297424fb
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61513684"
---
# <a name="in-development-for-microsoft-intune---april-2019"></a>Microsoft Intune - Nisan 2019 geliştirme

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
 
## <a name="intune-in-the-azure-portal"></a>Azure portalında Intune

<!-- 1904 start-->

### <a name="advanced-settings-for-windows-defender-firewall----1311949---"></a>Windows Defender Güvenlik Duvarı için Gelişmiş ayarları <!-- 1311949 -->
Yakında istemciler için Windows Defender'ın özel bir güvenlik duvarı kurallarını yönetmek için Intune kullanmak mümkün olacaktır. Kural, uygulamalar, ağ adresleri ve bağlantı noktalarına gelen ve giden davranış belirtebilirsiniz. 

### <a name="require-app-protection-conditional-access----1634317---"></a>Uygulama koruma koşullu erişim gerektirir  <!--1634317 -->
Kullanılacak mümkün olacaktır *gerektiren uygulama koruma İlkesi*, hangi ilke onaylar kullanıcıların koşullu erişim ile koruduğunuz veri erişimini engellemek için oturum açma tamamlanmadan önce bir kullanıcının uygulamaya uygulanır. İlke güvencesi ilk kullanım deneyimi yavaş, ancak ağ sorunları, yönetim yanlış yapılandırmalarını veya uygulama koruma ilkeleri önleme kasıtlı çalışmalarını karşı korumak için yardımcı olur. 

### <a name="configure-settings-for-kernel-extensions-on-macos-devices----2043024---"></a>MacOS cihazlarında çekirdek uzantıları için ayarları yapılandırma <!-- 2043024 -->
MacOS cihazlarında cihaz yapılandırma profili oluşturabilirsiniz (**cihaz Yapılandırması** > **profilleri** > **profili oluşturma** > seçin **macOS** platform için). Yeni bir Grup ayarlarını yapılandırmak ve çekirdek uzantıları cihazlarınızda kullanmanıza sağlayacaktır.

İçin geçerlidir: macOS 10.13.2 ve üzeri

### <a name="device-users-can-view-all-managed-apps-theyve-installed-or-tried-to-install----2352913---"></a>Cihaz kullanıcılarının yüklü veya yüklemeyi denedi tüm yönetilen uygulamalar görüntüleyebilirsiniz. <!-- 2352913 -->
Tüm yönetilen uygulamalar için Şirket portalı Windows listeler&ndash; hem gerekli hem de kullanılabilir&ndash; bir kullanıcı cihazında yüklü. Kullanıcılar, denenen görüntülemek ve bekleyen uygulama yüklemelerini ve bunların geçerli durumlarını mümkün olacaktır. Kuruluşunuzun uygulamalarını gerekli veya kullanılabilir duruma getirilmez, kullanıcılar şirket uygulama yüklenmiş olduğunu açıklayan bir ileti görür. Kullanıcılar ayrıca sıralamak veya uygulamalarını yükleme durumuna göre filtre uygulamak mümkün olacaktır.

### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910---"></a>"Uygulanabilirlik kuralları" kullandığınızda Windows 10 cihaz yapılandırma profilleri oluşturma <!-- 2549910 -->
Windows 10 cihaz yapılandırma profilleri oluşturma (**cihaz Yapılandırması** > **profilleri** > **profili oluşturma**  >  **Windows 10** platform için). Oluşturma tutulacak bir **Uygulanabilirlik kuralı** profili yalnızca bir belirli sürüm veya belirli bir sürüme uygular. Örneğin, bazı BitLocker ayarları sağlayan bir profil oluşturun. Profili eklediğinizde profil, yalnızca Windows 10 Enterprise çalıştıran cihazlar için uygular bir geçerlilik kuralı kullanın.

Şunun için geçerlidir: 
- Windows 10 ve üzeri

###  <a name="intune-security-tasks-for-defender-atp-in-public-preview----3208597---"></a>Intune güvenlik görevleri için Defender ATP (genel Önizleme) <!-- 3208597 -->
Genel önizleme olarak kullanıma sunulacak, Intune hemen güvenlik görevlerini yeni duyurulan Microsoft Defender tehdit ve güvenlik açığı yönetimi için ekler.  Bu tümleştirme sayesinde güvenlik işlemleri yöneticileri Windows Defender ATP (WDATP) Intune yöneticileri için ortaya çıkan tehditleri için önerilen düzeltmeler daha etkili bir şekilde iletişim kurabilir. Güvenlik görevlerini eklenmesi, keşfedin, öncelik sırasına sokmanıza ve uç noktası Güvenlik Açıkları ve yanlış yapılandırmalarını düzeltmek için risk tabanlı bir yaklaşım ekler.

Intune'da güvenlik görevler hakkında daha fazla bilgi için ilgili blog gönderisine bakın [Microsoft Defender ATP'nin güvenlik açığı yönetimi ve tehdit genişletmek için Intune güvenlik görevlerini kullanarak](https://techcommunity.microsoft.com/t5/Enterprise-Mobility-Security/Microsoft-Intune-security-tasks-extend-Microsoft-Defender-ATP-s/ba-p/369857). 

### <a name="windows-defender-advanced-threat-protection-baseline----3754134---"></a>Windows Defender Gelişmiş tehdit koruması temeli <!-- 3754134 -->
Windows Defender Gelişmiş tehdit koruması ayarları yapılandırmanıza yardımcı olması için yeni temeli eklemek için ekleyeceğiz.


### <a name="ios-third-party-keyboards----4111843---"></a>iOS üçüncü taraf klavyeler <!-- 4111843 -->
Intune uygulama koruma İlkesi (uygulama) için destek **üçüncü taraf klavyeler** ayarı, bir iOS platform değişikliği nedeniyle sona erecek. Intune Yönetici konsolunda bu ayarı yapılandırmak mümkün olmayacaktır ve Intune uygulama SDK'sı istemcide uygulanmaz.

<!-- 1903 start-->

### <a name="windows-update-notifications----3316782---"></a>Windows güncelleştirme bildirimleri <!-- 3316782 -->
Kullanıcıların görmesi Windows güncelleştirme bildirimleri yapılandırmak için bu sayede, Windows güncelleştirme halkası yapılandırmaları için destek ekliyoruz. Bu ayar, portalın içinde kullanılabilir durumda olmaz ancak Intune Graph API'si kullanılarak yapılandırılabilir.

### <a name="easier-access-to-diagnostic-settings----3804627---"></a>Daha kolay erişim için tanılama ayarları <!-- 3804627 -->
Yeni bir seçenek ekliyoruz **denetim günlükleri** dikey penceresinde, doğrudan açmak için kullanabileceğiniz Intune konsolundaki her bir denetim günlüğüne iş yükünün *tanılama ayarları* sayfası.

## <a name="notices"></a>Bildirimler

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

### <a name="see-also"></a>Ayrıca bkz.
Son geliştirmelere ilişkin ayrıntılar için bkz. [Microsoft Intune’daki Yenilikler](whats-new.md).


