---
title: "Kullanıcı - Intune Veri Ambarı | Microsoft Docs"
description: "Intune Veri Ambarı API’sindeki varlık koleksiyonlarının Kullanıcı kategorisi için başvuru konusu."
keywords: "Intune Veri Ambarı"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 11/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: C10E6752-E925-40AD-ABBF-6B621FB7AFC4
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6f321a3a9ac09c004639a3db15df280fbdb5be3c
ms.sourcegitcommit: d26930f45ba9e6292a49bcb08defb5b3f14b704b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="reference-for-current-user-entity"></a>Mevcut kullanıcı varlığı için başvuru

**Geçerli Kullanıcı** kategorisi veri modelinde kullanıcı ve aracı özelliklerini içerir. **Geçerli Kullanıcı** varlık koleksiyonu, şu anda etkin olan kullanıcılar ile sınırlıdır. Varlık şu anda bir lisans atanmış tüm Azure Active Directory kullanıcılarını içerir. Lisans, bir Intune lisansı, bir Hybrid lisans veya Microsoft Office 365 lisansı olabilir. Bir kullanıcı kaldırılmışsa, veri toplama süresi için gösterilmeyecektir. Kullanıcı durumu değişiklikleri geçmişini içeren bir koleksiyon için bkz: [Kullanıcı varlığı için referans](reports-ref-user.md).


## <a name="user"></a>Kullanıcı

**Kullanıcı** varlığı, kuruluşunuzda kendisine lisans atanmış olan tüm Azure Active Directory (Azure AD) kullanıcılarını listeler.

| Özellik  | Açıklama | Örnek |
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