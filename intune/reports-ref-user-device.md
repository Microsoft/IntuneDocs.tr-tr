---
title: Kullanıcı Cihaz İlişkisi - Intune Veri Ambarı
titleSuffix: Microsoft Intune
description: UserDeviceAssociation varlığı, kuruluşunuzdaki Kullanıcı cihaz ilişkilendirmelerini içerir.
keywords: Intune Veri Ambarı
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/23/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 777484A7-09CE-4409-987F-76B3F87DFE93
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4593fd5e76bf51b11ef9796bacc8c562241eaca2
ms.sourcegitcommit: c8cb314256c4896e838918f015ffaefb8f00ace5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/23/2019
ms.locfileid: "70001739"
---
# <a name="reference-for-user-device-association-entity"></a>Kullanıcı Cihaz İlişkisi varlığı için başvuru

**Userdeviceassociation** varlığı, kuruluşunuzdaki Kullanıcı cihaz ilişkilendirmelerini içerir.

## <a name="userdeviceassociations"></a>userDeviceAssociations


|        Name        |                                           Açıklama                                            |        Örnek         |
|--------------------|--------------------------------------------------------------------------------------------------|------------------------|
|      userKey       |              Kullanıcının veri ambarındaki benzersiz tanımlayıcısı. (Yedek anahtar).               |          123           |
|     deviceKey      |                      Cihazın veri ambarındaki benzersiz tanımlayıcısı.                      |          123           |
| createdDateTimeUTC |           Kullanıcı cihaz ilişkisinin oluşturulduğu tarih ve saat. UTC biçimini kullanır.           | 23.11.2016 12:00:00 |
|     IsDeleted      | Kullanıcının cihaz kaydını kaldırdığını ve ilişkinin artık geçerli olmadığını gösterir. |       True/False       |
|  endedDateTimeUTC  |              IsDeleted değerinin <strong>True</strong> olarak değiştirildiği UTC diliminde saat.               | 23.06.2017 12:00:00 |

## <a name="next-steps"></a>Sonraki adımlar

- [Intune veri ambarı](reports-nav-create-intune-reports.md)hakkında daha fazla bilgi edinin.
