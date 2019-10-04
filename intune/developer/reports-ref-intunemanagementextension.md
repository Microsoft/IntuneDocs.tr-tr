---
title: Intunemanagementextension varlığı
titleSuffix: Microsoft Intune
description: Intune veri ambarı API 'sindeki varlık koleksiyonlarının ıntunemanagementextension varlık kategorisi için başvuru konusu.
keywords: Intune veri ambarı
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/03/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 73DF3B90-6D52-4EF6-AFFD-1873A18C7421
ms.reviewer: dariusz
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 19b63172c8901059239c44aaf56fc49f0d7a01ad
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71940411"
---
# <a name="reference-for-intune-management-extensions"></a>Intune yönetim uzantılarına yönelik başvuru

**Intunemanagemenlersions** kategorisi, mobil cihazlar için şu gibi bilgileri izleyen varlıklar içerir:

- Intunemanagementextension 'ın sürümleri
- Intunemanagementextension yükleme durumu

## <a name="intunemanagementextensionversions"></a>ıntunemanagemenısionversions

**Intunemanagemenısionversion** varlığı, ıntunemanagemenlersions tarafından kullanılan tüm sürümleri listeler.

| Özellik  | Açıklama | Örnek |
|---------|------------|--------|
| ExtensionVersionKey |Intunemanagemenmalesions sürümünün benzersiz tanıtıcısı. | 1\. |
| ExtensionVersion |4 basamaklı sürüm numarası. |1.0.2.0 |

## <a name="intunemanagementextensionhealthstates"></a>ıntunemanagemenısionhealthstates

**Intunemanagemenısionhealthstate** , ıntunemanagemensions 'in tüm olası sistem durumlarını listeler.

| Özellik  | Açıklama | Örnek |
|---------|------------|--------|
| ExtensionStateKey |Sistem durumunun benzersiz tanımlayıcısı. | 2 |
| ExtensionState |Intunemanagementextension sistem durumu. | Sağlam |

## <a name="intunemanagementextensions"></a>ıntunemanagemensions

**Intunemanagementextension** , günlük her Windows 10 cihazında ıntunemanagemenlersions sistem durumunu listeler.
Veriler, son 60 gün boyunca tutulur. 


|      Özellik       |                         Açıklama                         | Örnek |
|---------------------|-------------------------------------------------------------|---------|
|       DateKey       |               Tarihin benzersiz tanımlayıcısı.                |   123   |
|      TenantKey      |              Kiracının benzersiz tanıtıcısı.               |   456   |
|      DeviceKey      |              Cihazın benzersiz tanımlayıcısı.               |   789   |
| ExtensionVersionKey | Intunemanagementextension sürümünün benzersiz tanıtıcısı. |    1\.    |
|  ExtensionStateKey  |             Sistem durumunun benzersiz tanımlayıcısı.              |    2    |

