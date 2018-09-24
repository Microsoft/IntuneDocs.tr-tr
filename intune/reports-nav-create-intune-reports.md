---
title: Intune Veri Ambarını kullanma
titlesuffix: Microsoft Intune
description: Kuruluşunuzun mobil ortamı hakkında öngörü sağlayan raporlar derlemek için Intune Veri Ambarını kullanın.
keywords: Intune Veri Ambarı
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 57019B11-DF9B-4D8A-95FE-254C75398DDE
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b82129c66015601640f0954b5248a1c9a80374f3
ms.sourcegitcommit: 443b4cb3390da47bf1e497b1f0c0137a5ddda7bd
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43821142"
---
# <a name="use-the-intune-data-warehouse"></a>Intune Veri Ambarını kullanma

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Kuruluşunuzun mobil ortamı hakkında öngörü sağlayan raporlar derlemek için Intune Veri Ambarını kullanın. Örneğin bazı raporlar şunları barındırır:
-   Lisans alımlarınızı iyileştirebilmeniz için Intune’a kaydolan kullanıcı eğilimleri
-   Mobil cihazların durumunu gözden geçirebilmeniz için uygulama ve işletim sistemlerinin çözümlemesi
-   İlke güncelleştirmelerini sorunsuz bir şekilde kullanıma sunabilmeniz için kayıt ve cihaz uyumluluğu eğilimleri

Veri Ambarı, mobil ortamınız hakkında Azure portalına kıyasla daha fazla bilgiye erişmenizi sağlar. Intune Veri Ambarı ile şunlara erişebilirsiniz:

  -  Geçmiş Intune verileri
  -  Günlük olarak yenilenen veriler
  -  OData standardı kullanan bir veri modeli

> [!Note]
> System Center Configuration Manager ve Microsoft Intune ile bir karma mobil cihaz yönetimi (MDM) kullanıyorsanız, verilerinizi SCCM’den almak istersiniz. Intune Veri Ambarı yalnızca Intune verilerini içerir. Özel raporlarınız için bir SCCM Power BI panosu kullanabilirsiniz. Daha fazla bilgi için bkz. “[System Center Configuration Manager için Power BI çözüm şablonu duyurusu]( https://powerbi.microsoft.com/blog/sccm-solution-template)” ve “[Dynamics 365 için Power BI içeriği](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/power-bi-home-page)”.

> [!Important]  
> Artık sorgu parametresini ayarlayarak Intune Veri Ambarı’nın v1.0 sürümünü kullanabilirsiniz `api-version=v1.0`. Veri Ambarı’ndaki koleksiyonlara yapılan güncelleştirmeler ek olarak yapılır, yani mevcut senaryoları bozmaz.<br><br>
> Beta sürümünü kullanarak Veri Ambarı’nın en yeni işlevlerini deneyebilirsiniz. Beta sürümünü kullanabilmeniz için URL’nizin sorgu parametresini içermesi gerekir `api-version=beta`. Özellikler, desteklenen bir hizmet olarak herkesin kullanımına açılmadan önce beta sürümünde sunulur. Intune yeni özellikler ekledikçe beta sürümünün davranışında ve veri anlaşmalarında değişiklikler olabilir. Beta sürümüne bağımlı herhangi bir özel kod veya raporlama araçları, devam eden güncelleştirmelerle birlikte kesilebilir.

**Sonraki adımlar**

- Bir bağlantı edinin ve öngörü almak için Power BI’ı kullanın. Yönergeler için bkz. [Intune Veri Ambarına Power BI ile bağlanma](reports-proc-get-a-link-powerbi.md).
- Bağlantınız ile Power BI kullanarak özel bir rapor hazırlayın. Yönergeler için bkz. [OData akışına Power BI ile bir rapor oluşturma](reports-proc-create-with-odata.md).
- Intune Veri Ambarı API’si, veri modeli ve varlıklar arasındaki ilişkiler hakkında daha fazla bilgi için<!-- , and an example of creating a custom client to retrieve data,--> bkz. [Intune Veri Ambarı API’si](reports-nav-intune-data-warehouse.md).