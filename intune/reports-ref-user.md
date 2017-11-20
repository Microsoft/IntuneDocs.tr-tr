---
title: "Kullanıcı - Intune Veri Ambarı | Microsoft Docs"
description: "Intune Veri Ambarı API’sindeki varlık koleksiyonlarının Kullanıcı kategorisi için başvuru konusu."
keywords: "Intune Veri Ambarı"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: C29A6EEA-72B7-427E-9601-E05B408F3BB0
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 8088127f5968c0b4f07f83b1dad02ba90f4e6b9a
ms.sourcegitcommit: e9f9fccccef691333143b7523d1b325ee7d1915a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/02/2017
---
# <a name="reference-for-user-entity"></a>Kullanıcı varlığı için başvuru

**Kullanıcı** kategorisi, veri modelindeki kullanıcı ve aracı özelliklerini tanımlayan **Kullanıcı** kategorisini içerir.

**Kullanıcı**

**Kullanıcı** varlığı, kuruluşunuzda kendisine lisans atanmış olan tüm Azure Active Directory (Azure AD) kullanıcılarını listeler.

| Özellik  | Açıklama | Örnek |
|---------|------------|--------|
| UserKey |Veri ambarındaki kullanıcının benzersiz tanımlayıcısı - vekil anahtar. |123 |
| UserId |Kullanıcının benzersiz tanımlayıcısı - UserKey’e benzer ancak doğal anahtardır. |b66bc706-ffff-7437-0340-032819502773 |
| UserEmail |Kullanıcının e-posta adresi. |John@constoso.com |
| GörünenAd |Kullanıcının görünen adı. |John |
| IntuneLicensed |Kullanıcının Intune lisansı olup olmadığını belirtir. |Doğru/Yanlış |
| IsDeleted |Kullanıcı kaydının güncelleştirilip güncelleştirilmediğini gösterir.  True- bu tabloda kullanıcının güncelleştirilmiş alanlarla birlikte yeni bir kaydı vardır. False- kullanıcı için en son kayıt. |Doğru/Yanlış |
| StartDateInclusiveUTC |Veri ambarında kullanıcının oluşturulduğu tarih ve UTC diliminde saat. |23.11.2016 12:00:00 |
| EndDateExclusiveUTC |IsDeleted değerinin True olarak değiştirildiği tarih ve UTC diliminde saat. |23.11.2016 12:00:00 |
| IsCurrent |Bu kullanıcı kaydının, veri ambarında mevcut olup olmadığını gösterir. |Doğru/Yanlış |
| RowLastModifiedDateTimeUTC |Kullanıcının veri ambarında son değiştirildiği tarih ve UTC diliminde saat. |23.11.2016 12:00:00 |

