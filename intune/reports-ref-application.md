---
title: Uygulama | Microsoft Docs
description: "Intune Veri Ambarı API’sindeki varlık koleksiyonlarının Uygulama kategorisi için başvuru konusu."
keywords: "Intune Veri Ambarı"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: A92DEF30-5D01-4774-9917-E26F5F0E2E68
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: cd684feec1df6b20f9349052496a21895527710b
ms.sourcegitcommit: 0d9bfd92bf5958261ed83b1f150bf207b7ba7e56
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/21/2017
---
# <a name="reference-for-application-entities"></a>Uygulama varlıkları için başvuru

**Uygulama** kategorisi, mobil cihazlar için aşağıdaki gibi bilgileri izleyen varlıklar içerir:

  -  Uygulamanın sürümleri
  -  Uygulamanın yükleme kaynağı
  -  Uygulamayı oluşturan geliştirici türü
  -  Uygulamanın yönetilen yazılım türleri, örneğin **sepet** veya **masaüstü**
  -  Uygulamanın Volume Purchasing Program (VPP) durumu

## <a name="apprevision"></a>AppRevision

**AppRevision** varlığı, uygulamaların tüm sürümlerini listeler.

| Özellik  | Açıklama | Örnek |
|---------|------------|--------|
| AppKey |Uygulamanın benzersiz tanımlayıcısı |123 |
| ApplicationId |Uygulamanın benzersiz tanımlayıcısı - AppKey’e benzer ancak doğal anahtardır. |b66bc706-ffff-7437-0340-032819502773 |
| Revizyon |İkili karşıya yüklenirken yönetici tarafından bahsedilen sürüm |2 |
| Başlık |Uygulama başlığı |Excel |
| Yayımcı |Uygulama yayımcısı |Microsoft |
| UploadState |Uygulamanın karşıya yükleme durumu |1 |
| AppTypeKey |Aşağıdaki bölümde açıklanan AppType özelliğine başvuru. | |
| VppProgramTypeKey |Aşağıda açıklanan VppProgramType özelliğine başvuru | |
| CreationTime |Düzeltmenin oluşturulduğu zaman |23.11.2016 12:00:00 |
| ModifiedTime |Bu düzeltmeyle ilgili herhangi bir şeyin en son değiştirildiği an |23.11.2016 12:00:00 |
| Boyut |İkili boyutu | |
| StartDateInclusiveUTC |Bu uygulama düzeltmesi veri ambarında oluşturulduğunda UTC tarih ve saati |23.11.2016 12:00:00 |
| EndDateExclusiveUTC |Bu uygulama düzeltmesi kullanımdan kalktığında UTC tarih ve saati |23.11.2016 12:00:00 |
| IsCurrent |Uygulama sürümünün, veri ambarında mevcut olup olmadığını gösterir |Doğru/Yanlış |
| RowLastModifiedDateTimeUTC |Bu uygulama sürümü veri ambarında son değiştirildiğinde UTC’de tarih ve saat |23.11.2016 12:00:00 |

## <a name="apptypes"></a>AppTypes

**AppTypes** varlığı, bir uygulamanın yükleme kaynağını listeler.

| Özellik  | Açıklama |
|---------|------------|
| AppTypeID |Tür kimliği |
| AppTypeKey |Anahtar için yedek anahtar |
| AppTypeName |Uygulama türü |

## <a name="example"></a>Örnek

| AppTypeID  | Ad | Açıklama |
|---------|------------|--------|
| 0 |Android mağazası uygulaması |Bir Android mağazası uygulaması |
| 1 |Android LOB uygulaması |Bir Android iş kolu uygulaması |
| 2 |Yönetilen Android mağazası uygulaması (MAM) |Yönetimi etkin bir Android mağazası uygulaması |
| 3 |iOS mağazası uygulaması |Bir iOS mağazası uygulaması |
| 4 |iOS LOB uygulaması |Bir iOS iş kolu uygulaması |
| 5 |Yönetilen iOS mağazası uygulaması (MAM?) |Yönetimi etkin bir iOS mağazası uygulaması |
| 6 |O365 Pro Plus Suite |Windows 10 için Office 365 Pro Plus Suite |
| 7 |Web uygulaması |Bir web uygulaması |
| 8 |Windows Phone 8.1 mağazası uygulaması |Bir Windows Phone 8.1 mağazası uygulaması |
| 9 |Windows mağazası uygulaması |Bir Windows mağazası uygulaması |
| 10 |Windows LOB uygulaması |Bir Windows AppX iş kolu uygulaması |
| 11 |Windows Mobile MSI |Bir MSI iş kolu uygulaması |
| 12 |Windows Phone LOB uygulaması |Bir Windows Phone iş kolu uygulaması |


## <a name="vppprogramtypes"></a>VppProgramTypes

**VppProgramTypes** varlığı, bir uygulama için olası VPP program türlerini listeler.

| Özellik  | Açıklama |
|---------|------------|
| VppProgramTypeID |Tür kimliği |
| VppProgramTypeKey |Anahtar için yedek anahtar |
| VppProgramTypeName |VPP program türü |

## <a name="example"></a>Örnek

| VppProgramID  | Ad | Açıklama |
|---------|------------|--------|
| 3DDA2474-470B-4503-9830-2665C21C1945 |Microsoft |Microsoft’un VPP programı |
| 00000000-0000-0000-0000-000000000000 |Henüz kullanılamıyor |Varsayılan değer, No VPP |
| B54814E0-68EA-4BA4-8088-B5AAB58E737B |Apple |Apple’ın VPP programı |



## <a name="applicationinventory"></a>ApplicationInventory

**ApplicationInventory** varlığı, envanter toplandığında cihazda bulunan uygulamaları listeler.

| Özellik  | Açıklama |
|---------|------------|
| DeviceKey |Bu, Intune cihaz kimliğini içeren Cihaz tablosuna bir başvurudur |
| DateKey |Envanterin alındığı günü gösteren tarih tablosuna başvuru |
| ApplicationName |Uygulama Adı |
| ApplicationVersion |Uygulamanın sürümü |
| BundleSize |Uygulamanın bayt cinsinden boyutu |
