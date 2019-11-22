---
title: Reference for Application entities
titleSuffix: Microsoft Intune
description: Intune Veri Ambarı API’sindeki varlık koleksiyonlarının Uygulama kategorisi için başvuru konusu.
keywords: Intune Veri Ambarı
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/21/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: A92DEF30-5D01-4774-9917-E26F5F0E2E68
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: a4a8fa34673340e4adca7b64707d8c79d4808460
ms.sourcegitcommit: 1cf063c98e1caae00a6e6fab821cc3254562bca9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74290957"
---
# <a name="reference-for-application-entities"></a>Uygulama varlıkları için başvuru

The **Application** category contains entities for devices that track information such as:

- Uygulamanın sürümleri
- Uygulamanın yükleme kaynağı
- Uygulamayı oluşturan geliştirici türü
- Uygulamanın yönetilen yazılım türleri, örneğin **sepet** veya **masaüstü**
- Uygulamanın Volume Purchasing Program (VPP) durumu

## <a name="apprevisions"></a>appRevisions

**appRevision** varlığı, uygulamaların tüm sürümlerini listeler.

| Özellik  | Description | Örnek |
|---------|------------|--------|
| appKey |Uygulamanın benzersiz tanımlayıcısı. |123 |
| applicationId |Uygulamanın benzersiz tanımlayıcısı - AppKey’e benzer ancak doğal anahtardır. |b66bc706-ffff-7437-0340-032819502773 |
| revision |İkili karşıya yüklenirken yönetici tarafından bahsedilen sürüm. |2 |
| title |Uygulama başlığı. |Excel |
| publisher |Uygulama yayımcısı. |Microsoft |
| uploadState |Uygulamanın karşıya yüklenme durumu. |1 |
| appTypeKey |Aşağıdaki bölümde açıklanan AppType özelliğine başvuru. | |
| vppProgramTypeKey |Aşağıda açıklanan VppProgramType özelliğine başvuru. | |
| creationTime |Düzeltmenin oluşturulduğu zaman. |23.11.2016 12:00:00 |
| modifiedTime |Bu düzeltmeyle ilgili herhangi bir şeyin en son değiştirildiği an. |23.11.2016 12:00:00 |
| boyut |İkili boyutu. | |
| startDateInclusiveUTC |Bu uygulama düzeltmesi, veri ambarında oluşturulduğunda tarih ve UTC diliminde saat. |23.11.2016 12:00:00 |
| endDateExclusiveUTC |Bu uygulama düzeltmesi kullanımdan kalktığında tarih ve UTC diliminde saat. |23.11.2016 12:00:00 |
| isCurrent |Uygulama sürümünün, veri ambarında mevcut olup olmadığını gösterir. |Doğru/Yanlış |
| rowLastModifiedDateTimeUTC |Bu uygulama sürümü, veri ambarında son değiştirildiğinde tarih ve UTC diliminde saat. |23.11.2016 12:00:00 |

## <a name="apptypes"></a>appTypes

**appTypes** varlığı, bir uygulamanın yükleme kaynağını listeler.

| Özellik  | Description |
|---------|------------|
| appTypeID |Tür kimliği |
| appTypeKey |Anahtar için yedek anahtar |
| appTypeName |Uygulama türü |

### <a name="example"></a>Örnek

| AppTypeID  | Ad | Description |
|---------|------------|--------|
| 0 |Android mağazası uygulaması | Bir Android mağazası uygulaması. |
| 1 |Android LOB uygulaması | Bir Android iş kolu uygulaması. |
| 2 |Yönetilen Android mağazası uygulaması (MAM) | Yönetimi etkin bir Android mağazası uygulaması. |
| 3 |iOS mağazası uygulaması | Bir iOS mağazası uygulaması. |
| 4 |iOS LOB uygulaması | Bir iOS iş kolu uygulaması. |
| 5 |Yönetilen iOS mağazası uygulaması (MAM?) | Yönetimi etkin bir iOS mağazası uygulaması. |
| 6 |O365 Pro Plus Suite | Windows 10 için Office 365 Pro Plus Suite. |
| 7 |Web uygulaması | Bir web uygulaması. |
| 8 |Windows Phone 8.1 mağazası uygulaması | Bir Windows Phone 8.1 mağazası uygulaması. |
| 9 |Windows mağazası uygulaması | Bir Windows mağazası uygulaması. |
| 10 |Windows LOB uygulaması | Bir Windows AppX iş kolu uygulaması. |
| 11 |Windows Mobile MSI | Bir MSI iş kolu uygulaması. |
| 12 |Windows Phone LOB uygulaması | Bir Windows Phone iş kolu uygulaması. |


## <a name="vppprogramtypes"></a>vppProgramTypes

**vppProgramType** varlığı, bir uygulama için olası VPP program türlerini listeler.

| Özellik  | Description |
|---------|------------|
| vppProgramTypeID | Tür kimliği. |
| vppProgramTypeKey | Anahtar için vekil anahtar. |
| vppProgramTypeName | VPP Program türü. |

### <a name="example"></a>Örnek

| VppProgramID  | Ad | Description |
|---------|------------|--------|
| 3DDA2474-470B-4503-9830-2665C21C1945 | Microsoft | Microsoft’un VPP programı. |
| 00000000-0000-0000-0000-000000000000 | Henüz kullanılamıyor | Varsayılan değer, No VPP. |
| B54814E0-68EA-4BA4-8088-B5AAB58E737B | Apple | Apple’ın VPP programı. |



## <a name="applicationinventories"></a>applicationInventories

The **applicationInventory** entity lists the applications found on the device at the time of inventory collection.

| Özellik  | Description |
|---------|------------|
| deviceKey | Bu, Intune cihaz kimliğini içeren Cihaz tablosuna bir başvurudur. |
| dateKey | Envanterin alındığı günü gösteren tarih tablosuna başvuru. |
| applicationName | Uygulama adı. |
| applicationVersion | Uygulamanın sürümü. |
| bundleSize | Uygulamanın bayt cinsinden boyutu. |

## <a name="mobileappinstallstates"></a>mobileAppInstallStates

The **mobileAppInstallState** entity represents the install state for a mobile application after it has been assigned to a group containing devices, users or both.

| Özellik | Description |
|---|---|
| appInstallStateKey | Hesabınız için uygulama yükleme durumunun benzersiz kimliği. |
| appInstallState | Uygulama yükleme durumunun Enum değeri. |
| appInstallStateName | Uygulama yükleme durumunun adı. |



