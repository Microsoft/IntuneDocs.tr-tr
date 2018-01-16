---
title: "Kullanıcı - Intune Veri Ambarı | Microsoft Docs"
description: "Intune Veri Ambarı API’sindeki varlık koleksiyonlarının Kullanıcı kategorisi için başvuru konusu."
keywords: "Intune Veri Ambarı"
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 12/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: C29A6EEA-72B7-427E-9601-E05B408F3BB0
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 917c9585ffe17f9d090c519f716d284aa1b932b8
ms.sourcegitcommit: b2467a653ffd36c2248a30b69cb88e3dc7cca2ed
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/14/2017
---
# <a name="reference-for-user-entity"></a>Kullanıcı varlığı için başvuru

**Kullanıcı** kategorisi, veri modelindeki kullanıcı özelliklerini tanımlayan **Kullanıcı** kategorisini içerir.

## <a name="user"></a>Kullanıcı

**Kullanıcı** varlığı, kuruluşunuzda kendisine lisans atanmış olan tüm Azure Active Directory (Azure AD) kullanıcılarını listeler.

**Kullanıcı** varlık koleksiyonu kullanıcı verilerini içerir. Bu kayıtlar, kullanıcı kaldırıldıysa dahi, veri toplama döneminde kullanıcı durumlarını içerir. Örneğin, bir kullanıcı Intune'a eklenebilir ve son bir ay içerisinde kaldırılabilir. Bu kullanıcı raporun olduğu saatte bulunmamakla birlikte, kullanıcı ve durum önceki ayın verilerinde bulunur. Kullanıcının verilerinizdeki varlığının süresini gösterecek bir rapor oluşturabilirsiniz.

| Özellik  | Description | Örnek |
|---------|------------|--------|
| UserKey |Veri ambarındaki kullanıcının benzersiz tanımlayıcısı - vekil anahtar. |123 |
| UserId |Kullanıcının benzersiz tanımlayıcısı - UserKey’e benzer ancak doğal anahtardır. |b66bc706-ffff-7437-0340-032819502773 |
| UserEmail |Kullanıcının e-posta adresi. |John@constoso.com |
| UPN | Kullanıcının kullanıcı asıl adı. | John@constoso.com |
| GörünenAd |Kullanıcının görünen adı. |John |
| IntuneLicensed |Kullanıcının Intune lisansı olup olmadığını belirtir. |Doğru/Yanlış |
| IsDeleted | Kullanıcının tüm lisanslarının geçerliliğini yitirip geçmediğini ve kullanıcının bu nedenle Intune'dan çıkıp çıkmadığını belirtir. Tek bir kayıt için bu bayrak değişmez. Bunun yerine, yeni bir kullanıcı durumu için yeni bir kayıt oluşturulur. |Doğru/Yanlış |
| StartDateInclusiveUTC |IsDeleted = FALSE ise kullanıcıya bir lisans atandığında ve Intune'da bir varlık olmaya başladığında UTC’deki DateTime. IsDeleted = TRUE ise kullanıcıların lisansları dolduğunda ve Intune'dan kaldırıldığında UTC’deki DateTime. |23.11.2016 12:00:00 |
| EndDateExclusiveUTC |IsDeleted = FALSE ise kullanıcıların lisansları dolduğunda ve Intune'dan kaldırıldığında UTC’deki DateTime. Lisansın bir önceki gün içerisinde süresi doldu. IsDeleted = TRUE ise kullanıcı yeni bir lisans aldığında ve Intune'da yeniden oluşturulduğunda UTC’deki DateTime.  |23.11.2016 12:00:00 |
| IsCurrent |Bu kayıt son kullanıcı durumunu temsil edip etmediğini gösterir. Tek bir kullanıcı için birden çok kayıt mevcut olabilir, ancak bunlardan yalnızca biri geçerli durumu temsil eder.  |Doğru/Yanlış |
| RowLastModifiedDateTimeUTC |Kaydın veri ambarında son değiştirildiği tarih ve UTC diliminde saat  |23.11.2016 12:00:00 |

## <a name="next-steps"></a>Sonraki adımlar
 - Kullanıcı verilerini şu anda etkin olan kullanıcılarla sınırlamak için **Geçerli Kullanıcı** varlık koleksiyonunu kullanabilirsiniz. Daha fazla bilgi için bkz. [Geçerli kullanıcı varlığı için referans](reports-ref-current-user.md).
 - Veri ambarının kullanıcının ömrünü Intune'de nasıl izlediği hakkında daha fazla bilgi edinmek için bkz. [Intune Veri Ambarı'nda kullanıcı ömrü gösterimi](reports-ref-user-timeline.md).
