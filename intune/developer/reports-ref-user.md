---
title: Kullanıcı-Intune veri ambarı
titleSuffix: Microsoft Intune
description: Intune veri ambarı API 'sindeki varlık koleksiyonlarının Kullanıcı kategorisi için başvuru konusu.
keywords: Intune veri ambarı
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/02/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: C29A6EEA-72B7-427E-9601-E05B408F3BB0
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 444ed3ad156e81a15eec0b86bb670eb63b5b04e7
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71939920"
---
# <a name="reference-for-user-entity"></a>Kullanıcı varlığı için başvuru

**Kullanıcılar** kategorisi, veri modelindeki Kullanıcı özelliklerini tanımlayan **Kullanıcı** varlığını içerir.

## <a name="users"></a>kullanıcılar

**Kullanıcı** varlığı, kuruluşunuzda lisanslanan Lisansların atandığı tüm Azure Active Directory (Azure AD) kullanıcılarını listeler.

Kullanıcı **varlık koleksiyonu** , Kullanıcı verilerini içerir. Bu kayıtlar, Kullanıcı kaldırılmış olsa bile veri toplama süresi boyunca Kullanıcı durumlarını içerir. Örneğin, bir Kullanıcı Intune 'a eklenebilir ve son ayın kursu sırasında kaldırılabilir. Bu Kullanıcı rapor sırasında mevcut olmasa da, önceki ayın verilerinde Kullanıcı ve durum bulunur. Verilerdeki geçmiş olma süresini gösteren bir rapor oluşturabilirsiniz.

|          Özellik          |                                                                                                           Açıklama                                                                                                          |                Örnek               |
|:--------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:------------------------------------:|
| UserKey                    | Veri ambarındaki kullanıcının benzersiz tanımlayıcısı-vekil anahtar.                                                                                                                                                         | 123                                  |
| UserID                     | Kullanıcının benzersiz tanımlayıcısı-UserKey 'e benzer ancak doğal bir anahtardır.                                                                                                                                                    | b66bc706-ffff-7437-0340-032819502773 |
| Kullanıcı e-postası                  | Kullanıcının e-posta adresi.                                                                                                                                                                                                     | John@constoso.com                    |
| userPrincipalName                        | Kullanıcının Kullanıcı asıl adı.                                                                                                                                                                                               | John@constoso.com                    |
| DisplayName                | Kullanıcının görünen adı.                                                                                                                                                                                                      | \                                 |
| Intunelisanslanmış             | Bu kullanıcının Intune lisanslı olup olmadığını belirtir.                                                                                                                                                                              | Doğru/yanlış                           |
| IsDeleted                  | Tüm Kullanıcı lisanslarının kullanım dışı olup olmadığını ve kullanıcının bu nedenle Intune 'dan kaldırılıp kaldırılmadığını belirtir. Tek bir kayıt için bu bayrak değişmez. Bunun yerine, yeni bir Kullanıcı durumu için yeni bir kayıt oluşturulur. | Doğru/yanlış                           |
| RowLastModifiedDateTimeUTC | Kayıt, veri ambarında son değiştirildiği tarih ve saat (UTC)                                                                                                                                                 | 11/23/2016 0:00                      |


## <a name="next-steps"></a>Sonraki adımlar
- **Geçerli Kullanıcı** varlığı koleksiyonunu, Kullanıcı verilerini Şu anda etkin olan kullanıcılarla sınırlandırmak için kullanabilirsiniz. Daha fazla bilgi için bkz. [geçerli kullanıcı varlığı Için başvuru](../reports-ref-current-user.md).
- Veri ambarının Intune 'da bir kullanıcının ömrünü nasıl izlediği hakkında daha fazla bilgi edinmek için bkz. [Intune veri ambarındaki Kullanıcı ömrü gösterimi](reports-ref-user-timeline.md).
