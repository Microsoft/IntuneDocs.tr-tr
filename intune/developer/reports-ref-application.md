---
title: Uygulama varlıkları için başvuru
titleSuffix: Microsoft Intune
description: Intune Veri Ambarı API’sindeki varlık koleksiyonlarının Uygulama kategorisi için başvuru konusu.
keywords: Intune Veri Ambarı
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/02/2020
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
ms.openlocfilehash: 2c87d9b423eeb96acbc984040ef49e44c1853a18
ms.sourcegitcommit: 8d7406b75ef0d75cc2ed03b1a5e5f74ff10b98c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/03/2020
ms.locfileid: "75654252"
---
# <a name="reference-for-application-entities"></a>Uygulama varlıkları için başvuru

**Uygulama** kategorisi, gibi bilgileri izleyen cihazlar için varlıklar içerir:

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
| uploadState |Uygulamanın karşıya yüklenme durumu. |1\. |
| appTypeKey |Aşağıdaki bölümde açıklanan AppType özelliğine başvuru. | |
| vppProgramTypeKey |Aşağıda açıklanan VppProgramType özelliğine başvuru. | |
| creationTime |Düzeltmenin oluşturulduğu zaman. |23.11.2016 12:00:00 |
| modifiedTime |Bu düzeltmeyle ilgili herhangi bir şeyin en son değiştirildiği an. |23.11.2016 12:00:00 |
| boyut |İkili boyutu. | |
| startDateInclusiveUTC |Bu uygulama düzeltmesi, veri ambarında oluşturulduğunda tarih ve UTC diliminde saat. |23.11.2016 12:00:00 |
| endDateExclusiveUTC |Bu uygulama düzeltmesi kullanımdan kalktığında tarih ve UTC diliminde saat. |23.11.2016 12:00:00 |
| IsCurrent |Uygulama sürümünün, veri ambarında mevcut olup olmadığını gösterir. |Doğru/Yanlış |
| rowLastModifiedDateTimeUTC |Bu uygulama sürümü, veri ambarında son değiştirildiğinde tarih ve UTC diliminde saat. |23.11.2016 12:00:00 |

## <a name="apptypes"></a>appTypes

**appTypes** varlığı, bir uygulamanın yükleme kaynağını listeler.

| Özellik  | Description |
|---------|------------|
| Apptypeıd |Tür kimliği |
| appTypeKey |Anahtar için yedek anahtar |
| appTypeName |Uygulama türü |

### <a name="example"></a>Örnek

| AppTypeID  | Name | Description |
|---------|------------|--------|
| 0 |Android mağazası uygulaması | Bir Android mağazası uygulaması. |
| 1\. |Android LOB uygulaması | Bir Android iş kolu uygulaması. |
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
| Vppprogramtypeıd | Tür kimliği. |
| vppProgramTypeKey | Anahtar için vekil anahtar. |
| vppProgramTypeName | VPP Program türü. |

### <a name="example"></a>Örnek

| VppProgramID  | Name | Description |
|---------|------------|--------|
| 3DDA2474-470B-4503-9830-2665C21C1945 | Microsoft | Microsoft’un VPP programı. |
| 00000000-0000-0000-0000-000000000000 | Henüz kullanılamıyor | Varsayılan değer, No VPP. |
| B54814E0-68EA-4BA4-8088-B5AAB58E737B | Apple | Apple’ın VPP programı. |



## <a name="applicationinventories"></a>Applicationenvanterler

**Applicationınventory** varlığı, envanter koleksiyonu sırasında cihazda bulunan uygulamaları listeler.

| Özellik  | Description |
|---------|------------|
| deviceKey | Bu, Intune cihaz kimliğini içeren Cihaz tablosuna bir başvurudur. |
| dateKey | Envanterin alındığı günü gösteren tarih tablosuna başvuru. |
| applicationName | Uygulama adı. |
| applicationVersion | Uygulamanın sürümü. |
| Paketleme Taboyutu | Uygulamanın bayt cinsinden boyutu. |

## <a name="mobileappinstallstates"></a>mobileAppInstallStates

**Mobileappınstallstate** varlığı, bir mobil uygulamanın cihaz, Kullanıcı veya her ikisini de içeren bir gruba atandıktan sonra yüklenmesi durumunu temsil eder.

| Özellik | Description |
|---|---|
| Appınstallstatekey | Hesabınız için uygulama yükleme durumunun benzersiz kimliği. |
| Appınstallstate | Uygulama yükleme durumunun Enum değeri. |
| Appınstallstatename | Uygulama yükleme durumunun adı. |



