---
title: "Kullanıcı Cihaz İlişkisi | Microsoft Docs"
description: "Intune Veri Ambarı API’sindeki varlık koleksiyonunun Kullanıcı Cihaz İlişkisi kategorisi için başvuru konusu."
keywords: "Intune Veri Ambarı"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 09/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: BCDBABCB-A7B1-42F2-BDD1-D055E33F2239
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 490e29f87c65875a385472e6abe9400363383f9b
ms.sourcegitcommit: bb2c181fd6de929cf1e5d3856e048d617eb72063
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2017
---
# <a name="reference-for-user-device-association-entity"></a>Kullanıcı Cihaz İlişkisi varlığı için başvuru

**Kullanıcı Cihaz İlişkisi** kategorisi, kuruluştaki cihaz ilişkilerini tanımlamak için kullanılan **Kullanıcı Cihaz İlişkisi** varlığını barındırır.

**Kullanıcı Cihaz İlişkisi**

**Kullanıcı Cihaz İlişkisi** varlığı, kuruluşta tanımlı cihaz ilişkilerini temsil eder.

| Ad               | Açıklama                                                                                      | Örnek                |
|--------------------|--------------------------------------------------------------------------------------------------|------------------------|
| UserKey            | Veri ambarındaki kullanıcının benzersiz tanımlayıcısı - vekil anahtar.                             | 123                    |
| DeviceKey          | Cihazın veri ambarındaki benzersiz tanımlayıcısı.                                           | 123                    |
| CreatedDateTimeUTC | Kullanıcı cihaz ilişkisinin oluşturulduğu tarih ve UTC diliminde saat.                               | 23.11.2016 12:00:00 |
| IsDeleted          | Kullanıcının cihaz kaydını kaldırdığını ve ilişkinin artık geçerli olmadığını gösterir. | True                   |
| EndedDateTimeUTC   | IsDeleted değerinin **True** olarak değiştirildiği UTC diliminde saat.                                         | 23.06.2017 12:00:00 |