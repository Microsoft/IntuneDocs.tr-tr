---
title: Uygulama varlıkları için başvuru
titleSuffix: Microsoft Intune
description: Intune veri ambarı API 'sindeki varlık koleksiyonlarının uygulama kategorisi için başvuru konusu.
keywords: Intune veri ambarı
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/02/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: A92DEF30-5D01-4774-9917-E26F5F0E2E68
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1e737f1cce594b5dd40b2f43048ba37578f5d7c9
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71940433"
---
# <a name="reference-for-application-entities"></a>Uygulama varlıkları için başvuru

**Uygulama** kategorisi, mobil cihazlar için şu gibi bilgileri izleyen varlıklar içerir:

- Uygulamanın sürümleri
- Uygulamanın yükleme kaynağı
- Bir uygulamayı oluşturan geliştiricilerin türü
- Bir uygulama için yönetilen yazılım türleri, örneğin **sepet** veya **Masaüstü**
- Uygulamanın toplu satın alma programı (VPP) durumu

## <a name="apprevisions"></a>Apprevizyonlar

**Apprevision** varlığı, tüm uygulama sürümlerini listeler.

| Özellik  | Açıklama | Örnek |
|---------|------------|--------|
| AppKey |Uygulamanın benzersiz tanımlayıcısı. |123 |
| Uygulama |Uygulamanın benzersiz tanımlayıcısı-AppKey ile benzerdir, ancak bu anahtar doğal bir uygulamadır. |b66bc706-ffff-7437-0340-032819502773 |
| Uncaya |İkilinin karşıya yüklenmesi sırasında yönetici tarafından belirtilen sürüm. |2 |
| Başlığın |Uygulamanın başlığı. |Excel |
| 'In |Uygulamanın yayımcısı. |Microsoft |
| UploadState |Uygulamanın durumunu karşıya yükleyin. |1\. |
| AppTypeKey |Aşağıdaki bölümde açıklanan AppType öğesine başvuru. | |
| VppProgramTypeKey |Aşağıda açıklanan VppProgramType öğesine başvuru. | |
| CreationTime |Bu düzeltmenin oluşturulduğu zaman. |11/23/2016 12:00:00 |
| ModifiedTime |Bu düzeltme ile ilgili herhangi bir şeyin değiştirildiği son zaman. |11/23/2016 12:00:00 |
| size |İkilinin boyutu. | |
| StartDate, Iveutc |Bu uygulama düzeltmesinin veri ambarında oluşturulduğu tarih ve saat (UTC). |11/23/2016 12:00:00 |
| EndDateExclusiveUTC |Bu uygulama düzeltmesi kullanımdan kalktığında UTC Tarih ve saat. |11/23/2016 12:00:00 |
| IsCurrent |Bu uygulama sürümünün, veri ambarında güncel olup olmadığını gösterir. |Doğru/yanlış |
| RowLastModifiedDateTimeUTC |Bu uygulama sürümünün, veri ambarında son değiştirildiği tarih ve saat (UTC). |11/23/2016 12:00:00 |

## <a name="apptypes"></a>AppTypes

**Apptype** varlığı, bir uygulamanın yükleme kaynağını listeler.

| Özellik  | Açıklama |
|---------|------------|
| Apptypeıd |Türün KIMLIĞI |
| AppTypeKey |Anahtar için yedek anahtar |
| AppTypeName |Uygulama türü |

### <a name="example"></a>Örnek

| Apptypeıd  | Name | Açıklama |
|---------|------------|--------|
| 0 |Android Mağazası uygulaması | Android Mağazası uygulaması. |
| 1\. |Android LOB uygulaması | Android iş kolu uygulaması. |
| 2 |Yönetilen Android Mağazası uygulaması (MAM) | Yönetimi etkin bir Android Mağazası uygulaması. |
| 3 |iOS Mağazası uygulaması | Bir iOS Mağazası uygulaması. |
| 4 |iOS LOB uygulaması | İOS iş kolu uygulaması. |
| 5 |Yönetilen iOS Mağazası uygulaması (MAM?) | Yönetim etkin olan bir ıossan uygulaması. |
| 6 |O365 Pro Plus Suite | Windows 10 için Office 365 Pro Plus Suite. |
| 7 |Web uygulaması | Bir Web uygulaması. |
| 8 |Windows Phone 8,1 Mağazası uygulaması | Windows Phone 8,1 Mağazası uygulaması. |
| 9 |Windows Mağazası uygulaması | Bir Windows Mağazası uygulaması. |
| 10 |Windows LOB uygulamaları | Bir Windows AppX iş kolu uygulaması. |
| 11 |Windows Mobile MSI | MSI iş kolu uygulaması. |
| 12 |Windows Phone LOB uygulaması | Bir Windows Phone iş kolu uygulaması. |


## <a name="vppprogramtypes"></a>VppProgramTypes

**Vppprogramtype** varlığı, bir uygulama IÇIN olası VPP program türlerini listeler.

| Özellik  | Açıklama |
|---------|------------|
| Vppprogramtypeıd | Türün KIMLIĞI. |
| VppProgramTypeKey | Anahtar için yedek anahtar. |
| VppProgramTypeName | VPP program türü. |

### <a name="example"></a>Örnek

| Vppprogramıd  | Name | Açıklama |
|---------|------------|--------|
| 3DDAV2474-470B-4503-9830-2665C21C1945 | Microsoft | Microsoft 'un VPP programı. |
| 00000000-0000-0000-0000-000000000000 | Henüz kullanılamıyor | Varsayılan değer, VPP yok. |
| B54814E0-68EA-4BA4-8088-B5AAB58E737B | Apple | Apple 'ın VPP programı. |



## <a name="applicationinventories"></a>Applicationenvanterler

**Applicationınventory** varlığı, envanter koleksiyonu sırasında cihazda bulunan uygulamaları listeler.

| Özellik  | Açıklama |
|---------|------------|
| DeviceKey | Bu, Intune cihaz KIMLIĞINI içeren cihaz tablosuna bir başvurudur. |
| DateKey | Sayım gününü gösteren tarih tablosuna başvuru. |
| ApplicationName | Uygulama adı. |
| ApplicationVersion | Uygulamanın sürümü. |
| Paketleme Taboyutu | Uygulamanın bayt cinsinden boyutu. |

## <a name="mobileappinstallstates"></a>Mobileappınstallstates

**Mobileappınstallstate** varlığı, bir mobil uygulamanın cihaz, Kullanıcı veya her ikisini de içeren bir gruba atandıktan sonra yüklenmesi durumunu temsil eder.

| Özellik | Açıklama |
|---|---|
| Appınstallstatekey | Hesabınız için uygulama yüklemesi durumunun benzersiz KIMLIĞI. |
| Appınstallstate | Uygulama yüklemesi durumunun Enum değeri. |
| Appınstallstatename | Uygulama yüklemesi durumunun adı. |



