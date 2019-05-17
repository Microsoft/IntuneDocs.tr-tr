---
title: Geliştirme - Intune
titleSuffix: ''
description: Geliştirme Intune özellikleri
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/29/2019
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
ms.openlocfilehash: 3645d07fe9a703f182e05bc9a7f9fbb93c413ddc
ms.sourcegitcommit: dfcf80a91792715404dc021c8684866c8b0a27e1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2019
ms.locfileid: "65816236"
---
# <a name="in-development-for-microsoft-intune---may-2019"></a>Microsoft Intune - Mayıs 2019 geliştirme

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


<!-- 1905 start-->


### <a name="baseline-support-for-keyword-search-----3082036-----------"></a>Anahtar sözcüğü için temel desteği arayın  <!-- 3082036         -->
Oluşturma veya bir güvenlik taban çizgisi profil düzenleme sırasında yakında kullanmak mümkün olacaktır *arama* konsolda görüntüleme ayarları filtrelemek için.   

### <a name="reset-and-wipe-devices-in-bulk-by-using-the-graph-api----3295288---"></a>Sıfırla ve Graph API'sini kullanarak cihazları toplu olarak temizleme <!-- 3295288 -->
Sıfırlama ve Graph API'sini kullanarak toplu olarak en fazla 100 cihazları temizlemek mümkün olacaktır.

<!-- 1904 start-->

### <a name="device-users-can-view-all-managed-apps-theyve-installed-or-tried-to-install----2352913---"></a>Cihaz kullanıcılarının yüklü veya yüklemeyi denedi tüm yönetilen uygulamalar görüntüleyebilirsiniz. <!-- 2352913 -->
Tüm yönetilen uygulamalar için Şirket portalı Windows listeler&ndash; hem gerekli hem de kullanılabilir&ndash; bir kullanıcı cihazında yüklü. Kullanıcılar, denenen görüntülemek ve bekleyen uygulama yüklemelerini ve bunların geçerli durumlarını mümkün olacaktır. Kuruluşunuzun uygulamalarını gerekli veya kullanılabilir duruma getirilmez, kullanıcılar şirket uygulama yüklenmiş olduğunu açıklayan bir ileti görür. Kullanıcılar ayrıca sıralamak veya uygulamalarını yükleme durumuna göre filtre uygulamak mümkün olacaktır.

### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910---"></a>"Uygulanabilirlik kuralları" kullandığınızda Windows 10 cihaz yapılandırma profilleri oluşturma <!-- 2549910 -->
Windows 10 cihaz yapılandırma profilleri oluşturma (**cihaz Yapılandırması** > **profilleri** > **profili oluşturma**  >  **Windows 10** platform için). Oluşturma tutulacak bir **Uygulanabilirlik kuralı** profili yalnızca bir belirli sürüm veya belirli bir sürüme uygular. Örneğin, bazı BitLocker ayarları sağlayan bir profil oluşturun. Profili eklediğinizde profil, yalnızca Windows 10 Enterprise çalıştıran cihazlar için uygular bir geçerlilik kuralı kullanın.

Şunun için geçerlidir: 
- Windows 10 ve üzeri



## <a name="notices"></a>Bildirimler

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

### <a name="see-also"></a>Ayrıca bkz.
Son geliştirmelere ilişkin ayrıntılar için bkz. [Microsoft Intune’daki Yenilikler](whats-new.md).


