---
title: "Kullanıcı | Microsoft Docs"
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
ms.openlocfilehash: 2b9739299c52c668117116f54c08715f1218d130
ms.sourcegitcommit: addf6a40caa22c22adfd2e2eff7d666cd1877e3c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/04/2017
---
# <a name="reference-for-user-entity"></a>Kullanıcı varlığı için başvuru

**Kullanıcı** kategorisi, veri modelindeki kullanıcı ve aracı özelliklerini tanımlayan **Kullanıcı** kategorisini içerir.

**Kullanıcı**

**Kullanıcı** varlığı, kuruluşunuzda kendisine lisans atanmış olan tüm Azure Active Directory (Azure AD) kullanıcılarını listeler.

| Özellik  | Açıklama | Örnek |
|---------|------------|--------|
| UserKey |Veri ambarındaki kullanıcının benzersiz tanımlayıcısı - vekil anahtar |123 |
| UserId |Kullanıcının benzersiz tanımlayıcısı - UserKey’e benzer ancak doğal anahtardır |b66bc706-ffff-7437-0340-032819502773 |
| UserEmail |Kullanıcının e-posta adresi |John@constoso.com |
| GörünenAd |Kullanıcının görünen adı |John |
| IntuneLicensed |Kullanıcının Intune lisansı olup olmadığını belirtir. |Doğru/Yanlış |
| IsDeleted |Kullanıcı kaydının güncelleştirilip güncelleştirilmediğini gösterir.  True- bu tabloda kullanıcının güncelleştirilmiş alanlarla birlikte yeni bir kaydı vardır. False- kullanıcı için en son kayıt. |Doğru/Yanlış |
| StartDateInclusiveUTC |veri ambarında kullanıcının oluşturulduğu UTC tarih ve saati |23.11.2016 12:00:00 |
| EndDateExclusiveUTC |IsDeleted özelliğinin True olarak değiştirildiği UTC tarih ve saati |23.11.2016 12:00:00 |
| IsCurrent |Kullanıcı kaydının, veri ambarında mevcut olup olmadığını gösterir |Doğru/Yanlış |
| RowLastModifiedDateTimeUTC |Kullanıcının veri ambarında son değiştirildiği UTC tarih ve saati |23.11.2016 12:00:00 |

