---
title: IntuneManagementExtension Varlığı
titleSuffix: Microsoft Intune
description: Intune Veri Ambarı API’sindeki varlık koleksiyonlarının IntuneManagementExtension Varlığı kategorisi için başvuru konusu.
keywords: Intune Veri Ambarı
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/03/2020
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
ms.openlocfilehash: b2efddc75c5819a25d9ba097cb24726e80df14f2
ms.sourcegitcommit: 8d7406b75ef0d75cc2ed03b1a5e5f74ff10b98c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/03/2020
ms.locfileid: "75654201"
---
# <a name="reference-for-intune-management-extensions"></a>Intune yönetim uzantılarına yönelik başvuru

**Intunemanagemenlersions** kategorisi, mobil cihazlar için şu gibi bilgileri izleyen varlıklar içerir:

- IntuneManagementExtension sürümleri
- IntuneManagementExtension yükleme durumu

## <a name="intunemanagementextensionversions"></a>intuneManagementExtensionVersions

**Intunemanagemenısionversion** varlığı, ıntunemanagemenlersions tarafından kullanılan tüm sürümleri listeler.

| Özellik  | Description | Örnek |
|---------|------------|--------|
| extensionVersionKey |Intunemanagemenmalesions sürümünün benzersiz tanıtıcısı. | 1\. |
| extensionVersion |4 basamaklı sürüm numarası. |1.0.2.0 |

## <a name="intunemanagementextensionhealthstates"></a>intuneManagementExtensionHealthStates

**Intunemanagemenısionhealthstate** , ıntunemanagemensions 'in tüm olası sistem durumlarını listeler.

| Özellik  | Description | Örnek |
|---------|------------|--------|
| extensionStateKey |Sistem durumunun benzersiz tanımlayıcısı. | 2 |
| extensionState |IntuneManagementExtension sistem durumu. | Sağlam |

## <a name="intunemanagementextensions"></a>intuneManagementExtensions

**Intunemanagementextension** , günlük her Windows 10 cihazında ıntunemanagemenlersions sistem durumunu listeler.
Son 60 günün verileri alınır. 


|      Özellik       |                         Description                         | Örnek |
|---------------------|-------------------------------------------------------------|---------|
|       dateKey       |               Tarihin benzersiz tanımlayıcısı.                |   123   |
|      tenantKey      |              Kiracının benzersiz tanımlayıcısı.               |   456   |
|      deviceKey      |              Cihazın benzersiz tanımlayıcısı.               |   789   |
| extensionVersionKey | Intunemanagementextension sürümünün benzersiz tanıtıcısı. |    1\.    |
|  extensionStateKey  |             Sistem durumunun benzersiz tanımlayıcısı.              |    2    |

