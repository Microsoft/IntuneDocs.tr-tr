---
title: "Intune Veri Ambarını kullanma | Microsoft Docs"
description: "Kuruluşunuzun mobil ortamı hakkında öngörü sağlayan raporlar derlemek için Intune Veri Ambarını kullanın."
keywords: "Intune Veri Ambarı"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 57019B11-DF9B-4D8A-95FE-254C75398DDE
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e399c36d4c6a855766ee956b3ca24c503a1f974b
ms.sourcegitcommit: e57512698a479df0d25ece6ece4492ec0e4f0f3e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/19/2017
---
# <a name="use-the-intune-data-warehouse"></a>Intune Veri Ambarını kullanma

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Kuruluşunuzun mobil ortamı hakkında öngörü sağlayan raporlar derlemek için Intune Veri Ambarını kullanın. Örneğin bazı raporlar şunları barındırır:
-   Lisans alımlarınızı iyileştirebilmeniz için Intune’a kaydolan kullanıcı eğilimleri
-   Mobil cihazların durumunu gözden geçirebilmeniz için uygulama ve işletim sistemlerinin çözümlemesi
-   İlke güncelleştirmelerini sorunsuz bir şekilde kullanıma sunabilmeniz için kayıt ve cihaz uyumluluğu eğilimleri

Veri Ambarı, mobil ortamınız hakkında Azure portalına kıyasla daha fazla bilgiye erişmenizi sağlar. Intune Veri Ambarı ile şunlara erişebilirsiniz:

  -  Geçmiş Intune verileri
  -  Günlük olarak yenilenen veriler
  -  OData standardı kullanan bir veri modeli

> [!Important]  
> Beta sürümünü kullanarak Veri Ambarı’nın en son işlevlerini deneyebilirsiniz. Beta sürümünü kullanabilmeniz için URL’nizin `api-version=beta` sorgu parametresini içermesi gerekir. Özellikler, desteklenen bir hizmet olarak herkesin kullanımına açılmadan önce beta sürümünde sunulur. Intune yeni özellikler ekledikçe beta sürümünün davranışında ve veri anlaşmalarında değişiklikler olabilir. Beta sürümüne bağımlı herhangi bir özel kod veya raporlama araçları, devam eden güncelleştirmelerle birlikte kesilebilir. <!-- If you experience problems with the beta service, follow [link to feedback process]() to report the issue or provide feedback.-->

**Sonraki adımlar**

- Bir bağlantı edinin ve öngörü almak için Power BI’ı kullanın. Yönergeler için bkz. [Intune Veri Ambarına Power BI ile bağlanma](reports-proc-get-a-link-powerbi.md).
- Bağlantınız ile Power BI kullanarak özel bir rapor hazırlayın. Yönergeler için bkz. [OData akışına Power BI ile bir rapor oluşturma](reports-proc-create-with-odata.md).
- Intune Veri Ambarı API’si, veri modeli ve varlıklar arasındaki ilişkiler hakkında daha fazla bilgi için<!-- , and an example of creating a custom client to retrieve data,--> bkz. [Intune Veri Ambarı API’si](reports-nav-intune-data-warehouse.md).