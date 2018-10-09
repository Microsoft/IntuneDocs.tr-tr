---
title: IntuneManagementExtension Varlığı
titlesuffix: Microsoft Intune
description: Intune Veri Ambarı API’sindeki varlık koleksiyonlarının IntuneManagementExtension Varlığı kategorisi için başvuru konusu.
keywords: Intune Veri Ambarı
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/04/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 73DF3B90-6D52-4EF6-AFFD-1873A18C7421
ms.reviewer: dariusz
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 02594a4442b91f59b3cea9e9fee5de8b39a6d19c
ms.sourcegitcommit: 28262384ec94e43970cc7a33e5d9063972bdf468
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48799515"
---
# <a name="reference-for-intune-management-extension"></a>Intune Yönetim Uzantısı için başvuru

**IntuneManagementExtension** kategorisi, mobil cihazlar için aşağıdaki gibi bilgileri izleyen varlıklar içerir:

  -  IntuneManagementExtension sürümleri
  -  IntuneManagementExtension yükleme durumu

## <a name="intunemanagementextensionversion"></a>IntuneManagementExtensionVersion

**IntuneManagementExtensionVersion** varlığı, IntuneManagementExtension tarafından kullanılan tüm sürümleri listeler.

| Özellik  | Açıklama | Örnek |
|---------|------------|--------|
| ExtensionVersionKey |IntuneManagementExtension sürümünün benzersiz tanımlayıcısı. | 1 |
| ExtensionVersion |4 basamaklı sürüm numarası. |1.0.2.0 |

## <a name="intunemanagementextensionhealthstate"></a>IntuneManagementExtensionHealthState

**IntuneManagementExtensionHealthState**, IntuneManagementExtension varlığının olası tüm sistem durumlarını listeler.

| Özellik  | Açıklama | Örnek |
|---------|------------|--------|
| ExtensionStateKey |Sistem durumunun benzersiz tanımlayıcısı. | 2 |
| ExtensionState |IntuneManagementExtension sistem durumu. | Sağlıklı |

## <a name="intunemanagementextension"></a>IntuneManagementExtension

**IntuneManagementExtension**, günlük olarak her bir Windows 10 cihazın IntuneManagementExtension durumunu listeler.
Son 60 günün verileri alınır. 


|      Özellik       |                         Açıklama                         | Örnek |
|---------------------|-------------------------------------------------------------|---------|
|       DateKey       |               Tarihin benzersiz tanımlayıcısı.                |   123   |
|      TenantKey      |              Kiracının benzersiz tanımlayıcısı.               |   456   |
|      DeviceKey      |              Cihazın benzersiz tanımlayıcısı.               |   789   |
| ExtensionVersionKey | IntuneManagementExtension sürümünün benzersiz tanımlayıcısı. |    1    |
|  ExtensionStateKey  |             Sistem durumunun benzersiz tanımlayıcısı.              |    2    |

