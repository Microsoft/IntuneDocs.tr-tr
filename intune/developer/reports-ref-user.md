---
title: Kullanıcı - Intune Veri Ambarı
titleSuffix: Microsoft Intune
description: Intune Veri Ambarı API’sindeki varlık koleksiyonlarının Kullanıcı kategorisi için başvuru konusu.
keywords: Intune Veri Ambarı
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/03/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: C29A6EEA-72B7-427E-9601-E05B408F3BB0
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 202d9e53ff21e5677a212012d37b0e909cc8c562
ms.sourcegitcommit: 8d7406b75ef0d75cc2ed03b1a5e5f74ff10b98c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/03/2020
ms.locfileid: "75654099"
---
# <a name="reference-for-user-entity"></a>Kullanıcı varlığı için başvuru

**Kullanıcılar** kategorisi, veri modelindeki Kullanıcı özelliklerini tanımlayan **Kullanıcı** varlığını içerir.

## <a name="users"></a>kullanıcılar

**user** varlığı, kuruluşunuzda kendisine lisans atanmış olan tüm Azure Active Directory (Azure AD) kullanıcılarını listeler.

**Kullanıcı** varlık koleksiyonu, kullanıcı verilerini içerir. Bu kayıtlar, kullanıcı kaldırıldıysa dahi, veri toplama döneminde kullanıcı durumlarını içerir. Örneğin, bir kullanıcı Intune'a eklenebilir ve son bir ay içerisinde kaldırılabilir. Bu kullanıcı, raporun olduğu saatte bulunmasa da kullanıcı ve durum, önceki ayın verilerinde bulunuyor. Kullanıcının verilerinizdeki varlığının süresini gösterecek bir rapor oluşturabilirsiniz.

|          Özellik          |                                                                                                           Description                                                                                                          |                Örnek               |
|:--------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:------------------------------------:|
| userKey                    | Veri ambarındaki kullanıcının benzersiz tanımlayıcısı - vekil anahtar.                                                                                                                                                         | 123                                  |
| userId                     | Kullanıcının benzersiz tanımlayıcısı - UserKey’e benzerdir ancak doğal bir anahtardır.                                                                                                                                                    | b66bc706-ffff-7437-0340-032819502773 |
| Kullanıcı e-postası                  | Kullanıcının e-posta adresi.                                                                                                                                                                                                     | John@constoso.com                    |
| userPrincipalName                        | Kullanıcının kullanıcı asıl adı.                                                                                                                                                                                               | John@constoso.com                    |
| displayName                | Kullanıcının görünen adı.                                                                                                                                                                                                      | John                                 |
| ıntunelisanslanmış             | Kullanıcının Intune lisansı olup olmadığını belirtir.                                                                                                                                                                              | Doğru/Yanlış                           |
| isDeleted                  | Kullanıcının tüm lisanslarının geçerliliğini yitirip yitirmediğini ve kullanıcının buna bağlı olarak Intune’dan kaldırılıp kaldırılmadığını belirtir. Tek bir kayıt için bu bayrak değişmez. Bunun yerine, yeni bir kullanıcı durumu için yeni bir kayıt oluşturulur. | Doğru/Yanlış                           |
| RowLastModifiedDateTimeUTC | Kaydın veri ambarında son değiştirilme tarihi ve saati (UTC)                                                                                                                                                 | 23.11.2016 0:00                      |


## <a name="next-steps"></a>Sonraki adımlar
- Kullanıcı verilerini şu anda etkin olan kullanıcılarla sınırlamak için **Geçerli Kullanıcı** varlık koleksiyonunu kullanabilirsiniz. Daha fazla bilgi için bkz. [Geçerli kullanıcı varlığı için referans](../reports-ref-current-user.md).
- Veri ambarının kullanıcının ömrünü Intune’da nasıl izlediği hakkında daha fazla bilgi edinmek için bkz. [Intune Veri Ambarı’nda kullanıcı ömrü gösterimi](reports-ref-user-timeline.md).
