---
title: Kullanıcı - Intune Veri Ambarı
titleSuffix: Microsoft Intune
description: Intune Veri Ambarı API’sindeki varlık koleksiyonlarının Kullanıcı kategorisi için başvuru konusu.
keywords: Intune Veri Ambarı
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/09/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: C29A6EEA-72B7-427E-9601-E05B408F3BB0
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4e650f8cb713d76c44d3f3399612ee5fd6d02426
ms.sourcegitcommit: 601327125ac8ae912d8159422de8aac7dbdc25f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59429153"
---
# <a name="reference-for-user-entity"></a>Kullanıcı varlığı için başvuru

**Kullanıcı** kategorisi, veri modelindeki kullanıcı özelliklerini tanımlayan **Kullanıcı** kategorisini içerir.

## <a name="user"></a>Kullanıcı

**Kullanıcı** varlığı, kuruluşunuzda kendisine lisans atanmış olan tüm Azure Active Directory (Azure AD) kullanıcılarını listeler.

**Kullanıcı** varlık koleksiyonu kullanıcı verilerini içerir. Bu kayıtlar, kullanıcı kaldırıldıysa dahi, veri toplama döneminde kullanıcı durumlarını içerir. Örneğin, bir kullanıcı Intune'a eklenebilir ve son bir ay içerisinde kaldırılabilir. Bu kullanıcı, raporun olduğu saatte bulunmasa da kullanıcı ve durum, önceki ayın verilerinde bulunuyor. Kullanıcının verilerinizdeki varlığının süresini gösterecek bir rapor oluşturabilirsiniz.

|          Özellik          |                                                                                                           Açıklama                                                                                                          |                Örnek               |
|:--------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:------------------------------------:|
| UserKey                    | Veri ambarındaki kullanıcının benzersiz tanımlayıcısı - vekil anahtar.                                                                                                                                                         | 123                                  |
| UserId                     | Kullanıcının benzersiz tanımlayıcısı - UserKey’e benzerdir ancak doğal bir anahtardır.                                                                                                                                                    | b66bc706-ffff-7437-0340-032819502773 |
| UserEmail                  | Kullanıcının e-posta adresi.                                                                                                                                                                                                     | John@constoso.com                    |
| userPrincipalName                        | Kullanıcının kullanıcı asıl adı.                                                                                                                                                                                               | John@constoso.com                    |
| displayName                | Kullanıcının görünen adı.                                                                                                                                                                                                      | John                                 |
| IntuneLicensed             | Kullanıcının Intune lisansı olup olmadığını belirtir.                                                                                                                                                                              | Doğru/Yanlış                           |
| IsDeleted                  | Kullanıcının tüm lisanslarının geçerliliğini yitirip yitirmediğini ve kullanıcının buna bağlı olarak Intune’dan kaldırılıp kaldırılmadığını belirtir. Tek bir kayıt için bu bayrak değişmez. Bunun yerine, yeni bir kullanıcı durumu için yeni bir kayıt oluşturulur. | True/False                           |
| RowLastModifiedDateTimeUTC | Kaydın veri ambarında son değiştirilme tarihi ve saati (UTC)                                                                                                                                                 | 23.11.2016 0:00                      |


## <a name="next-steps"></a>Sonraki adımlar
 - Kullanıcı verilerini şu anda etkin olan kullanıcılarla sınırlamak için **Geçerli Kullanıcı** varlık koleksiyonunu kullanabilirsiniz. Daha fazla bilgi için bkz. [Geçerli kullanıcı varlığı için referans](reports-ref-current-user.md).
 - Veri ambarının kullanıcının ömrünü Intune’da nasıl izlediği hakkında daha fazla bilgi edinmek için bkz. [Intune Veri Ambarı’nda kullanıcı ömrü gösterimi](reports-ref-user-timeline.md).
