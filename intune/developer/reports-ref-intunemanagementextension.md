---
title: IntuneManagementExtension Varlığı
titleSuffix: Microsoft Intune
description: Intune Veri Ambarı API’sindeki varlık koleksiyonlarının IntuneManagementExtension Varlığı kategorisi için başvuru konusu.
keywords: Intune Veri Ambarı
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/03/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 73DF3B90-6D52-4EF6-AFFD-1873A18C7421
ms.reviewer: dariusz
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: ae99e747f9c0540418c15f24fbe0c27c585f869c
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72490311"
---
# <a name="reference-for-intune-management-extensions"></a>Intune yönetim uzantılarına yönelik başvuru

**Intunemanagemenlersions** kategorisi, mobil cihazlar için şu gibi bilgileri izleyen varlıklar içerir:

- IntuneManagementExtension sürümleri
- IntuneManagementExtension yükleme durumu

## <a name="intunemanagementextensionversions"></a>intuneManagementExtensionVersions

**Intunemanagemenısionversion** varlığı, ıntunemanagemenlersions tarafından kullanılan tüm sürümleri listeler.

| Özellik  | Description | Örnek |
|---------|------------|--------|
| extensionVersionKey |Intunemanagemenmalesions sürümünün benzersiz tanıtıcısı. | 1 |
| extensionVersion |4 basamaklı sürüm numarası. |1.0.2.0 |

## <a name="intunemanagementextensionhealthstates"></a>intuneManagementExtensionHealthStates

**Intunemanagemenısionhealthstate** , ıntunemanagemensions 'in tüm olası sistem durumlarını listeler.

| Özellik  | Description | Örnek |
|---------|------------|--------|
| extensionStateKey |Sistem durumunun benzersiz tanımlayıcısı. | 2 |
| extensionState |IntuneManagementExtension sistem durumu. | Sorunsuz |

## <a name="intunemanagementextensions"></a>intuneManagementExtensions

**Intunemanagementextension** , günlük her Windows 10 cihazında ıntunemanagemenlersions sistem durumunu listeler.
Son 60 günün verileri alınır. 


|      Özellik       |                         Description                         | Örnek |
|---------------------|-------------------------------------------------------------|---------|
|       dateKey       |               Tarihin benzersiz tanımlayıcısı.                |   123   |
|      tenantKey      |              Kiracının benzersiz tanımlayıcısı.               |   456   |
|      deviceKey      |              Cihazın benzersiz tanımlayıcısı.               |   789   |
| extensionVersionKey | Intunemanagementextension sürümünün benzersiz tanıtıcısı. |    1    |
|  extensionStateKey  |             Sistem durumunun benzersiz tanımlayıcısı.              |    2    |

