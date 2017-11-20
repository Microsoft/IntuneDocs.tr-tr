---
title: "IntuneManagementExtension Varlığı | Microsoft Docs"
description: "Intune Veri Ambarı API’sindeki varlık koleksiyonlarının IntuneManagementExtension Varlığı kategorisi için başvuru konusu."
keywords: "Intune Veri Ambarı"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 11/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 73DF3B90-6D52-4EF6-AFFD-1873A18C7421
ms.reviewer: dariusz
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 30908e4dbb55e16db0e253330175f65fb127d523
ms.sourcegitcommit: 5279a0bb8c5aef79aa57aa247ad95888ffe5a12b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/08/2017
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

| Özellik  | Açıklama | Örnek |
|---------|------------|--------|
| DateKey |Tarihin benzersiz tanımlayıcısı. | 123 |
| TenantKey |Kiracının benzersiz tanımlayıcısı. | 456 |
| DeviceKey |Cihazın benzersiz tanımlayıcısı. | 789 |
| ExtensionVersionKey |IntuneManagementExtension sürümünün benzersiz tanımlayıcısı. | 1 |
| ExtensionStateKey|Sistem durumunun benzersiz tanımlayıcısı. | 2 |