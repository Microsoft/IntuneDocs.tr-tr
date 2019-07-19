---
title: IntuneManagementExtension Varlığı
titleSuffix: Microsoft Intune
description: Intune Veri Ambarı API’sindeki varlık koleksiyonlarının IntuneManagementExtension Varlığı kategorisi için başvuru konusu.
keywords: Intune Veri Ambarı
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/08/2019
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
ms.openlocfilehash: 70802626c79f11748e81c39afdd8bc8c5d0622b3
ms.sourcegitcommit: c3ac858bbadb63d248ed54069e48160d703bbaf2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/18/2019
ms.locfileid: "68313781"
---
# <a name="reference-for-intune-management-extensions"></a>Intune yönetim uzantılarına yönelik başvuru

**Intunemanagemenlersions** kategorisi, mobil cihazlar için şu gibi bilgileri izleyen varlıklar içerir:

- IntuneManagementExtension sürümleri
- IntuneManagementExtension yükleme durumu

## <a name="intunemanagementextensionversions"></a>intuneManagementExtensionVersions

**Intunemanagemenısionversion** varlığı, ıntunemanagemenlersions tarafından kullanılan tüm sürümleri listeler.

| Özellik  | Açıklama | Örnek |
|---------|------------|--------|
| ExtensionVersionKey |Intunemanagemenmalesions sürümünün benzersiz tanıtıcısı. | 1\. |
| ExtensionVersion |4 basamaklı sürüm numarası. |1.0.2.0 |

## <a name="intunemanagementextensionhealthstates"></a>intuneManagementExtensionHealthStates

**Intunemanagemenısionhealthstate** , ıntunemanagemensions 'in tüm olası sistem durumlarını listeler.

| Özellik  | Açıklama | Örnek |
|---------|------------|--------|
| ExtensionStateKey |Sistem durumunun benzersiz tanımlayıcısı. | 2 |
| ExtensionState |IntuneManagementExtension sistem durumu. | Sorunsuz |

## <a name="intunemanagementextensions"></a>intuneManagementExtensions

**Intunemanagementextension** , günlük her Windows 10 cihazında ıntunemanagemenlersions sistem durumunu listeler.
Son 60 günün verileri alınır. 


|      Özellik       |                         Açıklama                         | Örnek |
|---------------------|-------------------------------------------------------------|---------|
|       dateKey       |               Tarihin benzersiz tanımlayıcısı.                |   123   |
|      TenantKey      |              Kiracının benzersiz tanımlayıcısı.               |   456   |
|      DeviceKey      |              Cihazın benzersiz tanımlayıcısı.               |   789   |
| ExtensionVersionKey | Intunemanagementextension sürümünün benzersiz tanıtıcısı. |    1    |
|  ExtensionStateKey  |             Sistem durumunun benzersiz tanımlayıcısı.              |    2    |

