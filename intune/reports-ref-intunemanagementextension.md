---
title: IntuneManagementExtension Varlığı
titlesuffix: Microsoft Intune
description: Intune Veri Ambarı API’sindeki varlık koleksiyonlarının IntuneManagementExtension Varlığı kategorisi için başvuru konusu.
keywords: Intune Veri Ambarı
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/02/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 73DF3B90-6D52-4EF6-AFFD-1873A18C7421
ms.reviewer: dariusz
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5e4a15158deed81e40ca5916f7322a8f4744a2b8
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57393591"
---
# <a name="reference-for-intune-management-extension"></a>Intune Yönetim Uzantısı için başvuru

**IntuneManagementExtension** kategorisi, mobil cihazlar için aşağıdaki gibi bilgileri izleyen varlıklar içerir:

  -  IntuneManagementExtension sürümleri
  -  IntuneManagementExtension yükleme durumu

## <a name="intunemanagementextensionversion"></a>IntuneManagementExtensionVersion

**IntuneManagementExtensionVersion** varlığı, IntuneManagementExtension tarafından kullanılan tüm sürümleri listeler.

| Özellik  | Açıklama | Örnek |
|---------|------------|--------|
| ExtensionVersionKey |IntuneManagementExtension sürümünün benzersiz tanımlayıcısı. | 1. |
| ExtensionVersion |4 basamaklı sürüm numarası. |1.0.2.0 |

## <a name="intunemanagementextensionhealthstate"></a>IntuneManagementExtensionHealthState

**IntuneManagementExtensionHealthState**, IntuneManagementExtension varlığının olası tüm sistem durumlarını listeler.

| Özellik  | Açıklama | Örnek |
|---------|------------|--------|
| ExtensionStateKey |Sistem durumunun benzersiz tanımlayıcısı. | 2 |
| ExtensionState |IntuneManagementExtension sistem durumu. | Sorunsuz |

## <a name="intunemanagementextension"></a>IntuneManagementExtension

**IntuneManagementExtension**, günlük olarak her bir Windows 10 cihazın IntuneManagementExtension durumunu listeler.
Son 60 günün verileri alınır. 


|      Özellik       |                         Açıklama                         | Örnek |
|---------------------|-------------------------------------------------------------|---------|
|       DateKey       |               Tarihin benzersiz tanımlayıcısı.                |   123   |
|      TenantKey      |              Kiracının benzersiz tanımlayıcısı.               |   456   |
|      DeviceKey      |              Cihazın benzersiz tanımlayıcısı.               |   789   |
| ExtensionVersionKey | IntuneManagementExtension sürümünün benzersiz tanımlayıcısı. |    1.    |
|  ExtensionStateKey  |             Sistem durumunun benzersiz tanımlayıcısı.              |    2    |

