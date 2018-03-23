---
title: Kullanıcı Cihaz İlişkisi - Intune Veri Ambarı
titlesuffix: Microsoft Intune
description: Intune Veri Ambarı API’sindeki değişikliklerin bir listesi.
keywords: Intune Veri Ambarı
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 777484A7-09CE-4409-987F-76B3F87DFE93
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: de14444376cb2998f17f406f084c428523ef4e4f
ms.sourcegitcommit: 21db583d6a9d3c15a8a8ee5579309dff1cfe1f8b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2018
---
# <a name="user-device-association"></a>Kullanıcı Cihaz İlişkisi

**UserDeviceAssociation** varlığı kuruluşunuzdaki kullanıcı cihaz ilişkilerini içerir.

| Ad               | Description                                                                                      | Örnek                |
|--------------------|--------------------------------------------------------------------------------------------------|------------------------|
| UserKey            | Kullanıcının veri ambarındaki benzersiz tanımlayıcısı. (Yedek anahtar).                              | 123                    |
| DeviceKey          | Cihazın veri ambarındaki benzersiz tanımlayıcısı.                                            | 123                    |
| CreatedDateTimeUTC | Kullanıcı cihaz ilişkisinin oluşturulduğu tarih ve saat. UTC biçimini kullanır.                                | 23.11.2016 12:00:00 |
| IsDeleted          | Kullanıcının cihaz kaydını kaldırdığını ve ilişkinin artık geçerli olmadığını gösterir. | Doğru/Yanlış             |
| EndedDateTimeUTC   | IsDeleted değerinin **True** olarak değiştirildiği UTC diliminde saat.                                              | 23.06.2017 12:00:00 |
