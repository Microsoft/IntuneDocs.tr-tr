---
title: "Kullanıcı Cihaz İlişkisi - Intune Veri Ambarı | Microsoft Docs"
description: "Intune Veri Ambarı API’sindeki değişikliklerin bir listesi."
keywords: "Intune Veri Ambarı"
author: Erikre
ms.author: erikre
manager: angrobe
ms.date: 10/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 777484A7-09CE-4409-987F-76B3F87DFE93
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 095395be4c86780ad65ba1e24b856f6eef8d41ae
ms.sourcegitcommit: d44c32aad3e84f6c0b296bdb010981d3a818befb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/16/2018
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
