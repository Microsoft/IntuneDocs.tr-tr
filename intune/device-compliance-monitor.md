---
title: "Cihaz uyumluluğunu izleme"
titlesuffix: Microsoft Intune
description: "Cihaz uyumluluğunu izleme hakkında bilgi edinin.\""
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0790934b-48b9-435b-a8aa-e83ed5b73191
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 708ed5a335d3475c213a536da9072afb1ad32ef9
ms.sourcegitcommit: aafed032492c1b5861d7097a335f9bbb29ce3221
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/02/2018
---
# <a name="monitor-device-compliance-in-intune"></a>Intune'da cihaz uyumluluğunu izleme

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**Genel Bakış** dikey penceresinde **uyumluluk profillerinizin** durumunun özetini görüntüleyebilirsiniz.
Detaya gitmek için grafiklere tıklayarak etkileşimli çalışabilirsiniz. Yapılandırılmış birden çok uyumluluk profiliniz varsa, ilke durumunu **Yönet** > **Raporlar** altındaki ilke dikey penceresinde görebilirsiniz.

##  <a name="device-compliance"></a>Cihaz uyumluluğu

Cihaz uyumluluğu raporunun özet görünümü, aşağıdaki durumlardan birinde raporlama yapan cihaz sayısı hakkında toplu bilgileri listeler:

- **Uyumlu**: Cihaz yakın zamanda değerlendirilmiş olup, belirttiğiniz uyumluluk profili ayarları ile uyumludur.
- **Uyumsuz**: Cihaz değerlendirilmiş ve uyumsuz olduğu saptanmıştır.  Profilde bir yetkisiz kullanım süresi belirtilmişse, yetkisiz kullanım süresi sona erdiğinden cihaz uyumsuz duruma gelmiştir.
- **Yetkisiz kullanım süresi**: Cihaz değerlendirilmiş ve uyumsuz olduğu saptanmıştır. Bununla birlikte, cihaz uyumsuz olarak işaretlenmeden önce yetkisiz kullanım süresi geçerli olacaktır.

Tek tek cihazlar ve kullanıcılarla ilgili diğer ayrıntıları görmek için, her bölümde detaya gidebilirsiniz.

## <a name="setting-compliance"></a>Ayar uyumluluğu

Ayar uyumluluğu raporu, her uyumluluk ayarı için aşağıdakiler gibi ayrıntıları sağlar:

- Ayarla uyumsuz olan cihazların sayısı.
- Ayarın geçerli olduğu platform.

Bu ayarların etkinleştirildiği profiller hakkında daha fazla bilgiye ulaşmak ve ayarın değerini görmek için, her ayarda detaya gidebilirsiniz.
