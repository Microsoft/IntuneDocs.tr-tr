---
title: "Geçerli Kullanıcı - Intune Veri Ambarı | Microsoft Docs"
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
ms.assetid: C10E6752-E925-40AD-ABBF-6B621FB7AFC4
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: cabf39f603ac93a0716594c44174908e7c999e5c
ms.sourcegitcommit: b2467a653ffd36c2248a30b69cb88e3dc7cca2ed
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/14/2017
---
# <a name="reference-for-current-user-entity"></a>Geçerli Kullanıcı varlığı için başvuru

**Geçerli Kullanıcı** kategorisi veri modelinde kullanıcı özelliklerini içerir. **Geçerli Kullanıcı** varlık koleksiyonu, şu anda etkin olan kullanıcılar ile sınırlıdır. Varlık şu anda bir lisans atanmış tüm Azure Active Directory kullanıcılarını içerir. Lisans, bir Intune lisansı, bir Hybrid lisans veya Microsoft Office 365 lisansı olabilir. Kaldırılmış olan kullanıcı, Geçerli Kullanıcı koleksiyonunda gösterilmeyecektir. Kullanıcı durumu değişiklikleri geçmişini içeren bir koleksiyon için bkz: [Kullanıcı varlığı için referans](reports-ref-user.md).


## <a name="current-user"></a>Geçerli Kullanıcı

**Geçerli Kullanıcı** varlığı, kuruluşunuzda kendisine lisans atanmış olan tüm Azure Active Directory (Azure AD) kullanıcılarını listeler.

| Özellik  | Description | Örnek |
|---------|------------|--------|
| UserKey |Veri ambarındaki kullanıcının benzersiz tanımlayıcısı - vekil anahtar. |123 |
| UserId |Kullanıcının benzersiz tanımlayıcısı - UserKey’e benzer ancak doğal anahtardır. |b66bc706-ffff-7437-0340-032819502773 |
| UserEmail |Kullanıcının e-posta adresi. |John@constoso.com |
| UPN | Kullanıcının kullanıcı asıl adı. | John@constoso.com |
| GörünenAd |Kullanıcının görünen adı. |John |
| IntuneLicensed |Kullanıcının Intune lisansı olup olmadığını belirtir. |Doğru/Yanlış |
| StartDateInclusiveUTC |Veri ambarında kullanıcının oluşturulduğu tarih ve UTC diliminde saat. |23.11.2016 12:00:00 |
| RowLastModifiedDateTimeUTC |Kullanıcının veri ambarında son değiştirildiği tarih ve UTC diliminde saat. |23.11.2016 12:00:00 |

## <a name="next-steps"></a>Sonraki adımlar
 - Kullanıcı verilerini şu anda etkin olmayan kullanıcılara genişletmek için **Kullanıcılar** varlık koleksiyonunu kullanabilirsiniz. Daha fazla bilgi için bkz. [Kullanıcı varlığı için referans](reports-ref-user.md).
 - Veri ambarının kullanıcının ömrünü Intune'de nasıl izlediği hakkında daha fazla bilgi için bkz. [Intune Veri Ambarı'nda kullanıcı ömrü gösterimi](reports-ref-user-timeline.md).
