---
title: Kullanıcı Cihaz İlişkisi - Intune Veri Ambarı
titlesuffix: Microsoft Intune
description: UserDeviceAssociation varlığı kuruluşunuzdaki kullanıcı cihaz ilişkilerini içerir.
keywords: Intune Veri Ambarı
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 777484A7-09CE-4409-987F-76B3F87DFE93
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; seodec18
ms.openlocfilehash: 02c579a7371a59a46cfb0017e6aa1a17af92bd03
ms.sourcegitcommit: 1c9ef5cfac2fc024528d2cfc9d590fa68dd58080
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/15/2018
ms.locfileid: "53429568"
---
# <a name="reference-for-user-device-association-entity"></a>Kullanıcı Cihaz İlişkisi varlığı için başvuru

**UserDeviceAssociation** varlığı kuruluşunuzdaki kullanıcı cihaz ilişkilerini içerir.

## <a name="userdeviceassociation"></a>UserDeviceAssociation


|        Ad        |                                           Açıklama                                            |        Örnek         |
|--------------------|--------------------------------------------------------------------------------------------------|------------------------|
|      UserKey       |              Kullanıcının veri ambarındaki benzersiz tanımlayıcısı. (Yedek anahtar).               |          123           |
|     DeviceKey      |                      Cihazın veri ambarındaki benzersiz tanımlayıcısı.                      |          123           |
| CreatedDateTimeUTC |           Kullanıcı cihaz ilişkisinin oluşturulduğu tarih ve saat. UTC biçimini kullanır.           | 23.11.2016 12:00:00 |
|     IsDeleted      | Kullanıcının cihaz kaydını kaldırdığını ve ilişkinin artık geçerli olmadığını gösterir. |       True/False       |
|  EndedDateTimeUTC  |              IsDeleted değerinin <strong>True</strong> olarak değiştirildiği UTC diliminde saat.               | 23.06.2017 12:00:00 |

## <a name="next-steps"></a>Sonraki adımlar

- Daha fazla bilgi edinin [Intune veri ambarı](reports-nav-create-intune-reports.md).