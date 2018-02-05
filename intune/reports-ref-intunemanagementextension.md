---
title: "IntuneManagementExtension Varlığı | Microsoft Docs"
description: "Intune Veri Ambarı API’sindeki varlık koleksiyonlarının IntuneManagementExtension Varlığı kategorisi için başvuru konusu."
keywords: "Intune Veri Ambarı"
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 73DF3B90-6D52-4EF6-AFFD-1873A18C7421
ms.reviewer: dariusz
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 93a5fde5f0c6ac870104ab90035e119757064cb3
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
---
# <a name="reference-for-intune-management-extension"></a>Intune Yönetim Uzantısı için başvuru

**IntuneManagementExtension** kategorisi, mobil cihazlar için aşağıdaki gibi bilgileri izleyen varlıklar içerir:

  -  IntuneManagementExtension sürümleri
  -  IntuneManagementExtension yükleme durumu

## <a name="intunemanagementextensionversion"></a>IntuneManagementExtensionVersion

**IntuneManagementExtensionVersion** varlığı, IntuneManagementExtension tarafından kullanılan tüm sürümleri listeler.

| Özellik  | Description | Örnek |
|---------|------------|--------|
| ExtensionVersionKey |IntuneManagementExtension sürümünün benzersiz tanımlayıcısı. | 1 |
| ExtensionVersion |4 basamaklı sürüm numarası. |1.0.2.0 |

## <a name="intunemanagementextensionhealthstate"></a>IntuneManagementExtensionHealthState

**IntuneManagementExtensionHealthState**, IntuneManagementExtension varlığının olası tüm sistem durumlarını listeler.

| Özellik  | Description | Örnek |
|---------|------------|--------|
| ExtensionStateKey |Sistem durumunun benzersiz tanımlayıcısı. | 2 |
| ExtensionState |IntuneManagementExtension sistem durumu. | Sağlıklı |

## <a name="intunemanagementextension"></a>IntuneManagementExtension

**IntuneManagementExtension**, günlük olarak her bir Windows 10 cihazın IntuneManagementExtension durumunu listeler.
Son 60 günün verileri alınır. 

| Özellik  | Description | Örnek |
|---------|------------|--------|
| DateKey |Tarihin benzersiz tanımlayıcısı. | 123 |
| TenantKey |Kiracının benzersiz tanımlayıcısı. | 456 |
| DeviceKey |Cihazın benzersiz tanımlayıcısı. | 789 |
| ExtensionVersionKey |IntuneManagementExtension sürümünün benzersiz tanımlayıcısı. | 1 |
| ExtensionStateKey|Sistem durumunun benzersiz tanımlayıcısı. | 2 |