---
title: Kullanıcı Cihaz İlişkisi - Intune Veri Ambarı
titlesuffix: Microsoft Intune
description: Intune Veri Ambarı API’sindeki değişikliklerin bir listesi.
keywords: Intune Veri Ambarı
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 777484A7-09CE-4409-987F-76B3F87DFE93
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0829bbcb661822c5d00ba4ca1e5d31ece301ef02
ms.sourcegitcommit: 445a54dc6826a549d770a9953549ae2191d391c2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45727433"
---
# <a name="user-device-association"></a>Kullanıcı Cihaz İlişkisi

**UserDeviceAssociation** varlığı kuruluşunuzdaki kullanıcı cihaz ilişkilerini içerir.


|        Ad        |                                           Açıklama                                            |        Örnek         |
|--------------------|--------------------------------------------------------------------------------------------------|------------------------|
|      UserKey       |              Kullanıcının veri ambarındaki benzersiz tanımlayıcısı. (Yedek anahtar).               |          123           |
|     DeviceKey      |                      Cihazın veri ambarındaki benzersiz tanımlayıcısı.                      |          123           |
| CreatedDateTimeUTC |           Kullanıcı cihaz ilişkisinin oluşturulduğu tarih ve saat. UTC biçimini kullanır.           | 23.11.2016 12:00:00 |
|     IsDeleted      | Kullanıcının cihaz kaydını kaldırdığını ve ilişkinin artık geçerli olmadığını gösterir. |       Doğru/Yanlış       |
|  EndedDateTimeUTC  |              IsDeleted değerinin <strong>True</strong> olarak değiştirildiği UTC diliminde saat.               | 23.06.2017 12:00:00 |

