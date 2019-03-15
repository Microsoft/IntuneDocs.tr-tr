---
title: Geçerli Kullanıcı - Intune Veri Ambarı
titlesuffix: Microsoft Intune
description: Intune veri ambarı API'sindeki varlık koleksiyonlarının geçerli kullanıcı kategorisi için başvuru konusu.
keywords: Intune Veri Ambarı
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/11/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: C10E6752-E925-40AD-ABBF-6B621FB7AFC4
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4e6a543e835e67c55be4d62cb0290a096d3a65ee
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57565783"
---
# <a name="reference-for-current-user-entity"></a>Geçerli Kullanıcı varlığı için başvuru

**Geçerli Kullanıcı** kategorisi veri modelinde kullanıcı özelliklerini içerir. **Geçerli Kullanıcı** varlık koleksiyonu, şu anda etkin olan kullanıcılar ile sınırlıdır. Varlık şu anda bir lisans atanmış tüm Azure Active Directory kullanıcılarını içerir. Lisans, bir Intune lisansı, bir Hybrid lisans veya Microsoft Office 365 lisansı olabilir. Kaldırılmış olan kullanıcı, Geçerli Kullanıcı koleksiyonunda gösterilmeyecektir. Kullanıcı durumu değişiklikleri geçmişini içeren bir koleksiyon için bkz: [Kullanıcı varlığı için referans](reports-ref-user.md).


## <a name="current-user"></a>Geçerli Kullanıcı

**Geçerli Kullanıcı** varlığı, kuruluşunuzda kendisine lisans atanmış olan tüm Azure Active Directory (Azure AD) kullanıcılarını listeler.

| Özellik  | Açıklama | Örnek |
|---------|------------|--------|
| UserKey |Veri ambarındaki kullanıcının benzersiz tanımlayıcısı - vekil anahtar. |123 |
| UserId |Kullanıcının benzersiz tanımlayıcısı - UserKey’e benzer ancak doğal anahtardır. |b66bc706-ffff-7437-0340-032819502773 |
| UserEmail |Kullanıcının e-posta adresi. |John@constoso.com |
| UPN | Kullanıcının kullanıcı asıl adı. | John@constoso.com |
| displayName |Kullanıcının görünen adı. |John |
| IntuneLicensed |Kullanıcının Intune lisansı olup olmadığını belirtir. |True/False |
| StartDateInclusiveUTC |Veri ambarında kullanıcının oluşturulduğu tarih ve UTC diliminde saat. |23.11.2016 12:00:00 |
| RowLastModifiedDateTimeUTC |Kullanıcının veri ambarında son değiştirildiği tarih ve UTC diliminde saat. |23.11.2016 12:00:00 |

## <a name="next-steps"></a>Sonraki adımlar
 - Kullanıcı verilerini şu anda etkin olmayan kullanıcılara genişletmek için **Kullanıcılar** varlık koleksiyonunu kullanabilirsiniz. Daha fazla bilgi için bkz. [Kullanıcı varlığı için referans](reports-ref-user.md).
 - Veri ambarının kullanıcının ömrünü Intune'de nasıl izlediği hakkında daha fazla bilgi için bkz. [Intune Veri Ambarı'nda kullanıcı ömrü gösterimi](reports-ref-user-timeline.md).
