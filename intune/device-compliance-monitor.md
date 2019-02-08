---
title: Cihaz uyumluluğunu izleme
titlesuffix: Microsoft Intune
description: Cihaz uyumluluğunu izleme hakkında bilgi edinin."
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/07/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 0790934b-48b9-435b-a8aa-e83ed5b73191
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 534e8316e584259a818130ea9f83c88b44b67fee
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55848092"
---
# <a name="monitor-device-compliance-in-intune"></a>Intune'da cihaz uyumluluğunu izleme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

**Genel Bakış** dikey penceresinde **uyumluluk profillerinizin** durumunun özetini görüntüleyebilirsiniz.
Detaya gitmek için grafiklere tıklayarak etkileşimli çalışabilirsiniz. Yapılandırılmış birden çok uyumluluk profiliniz varsa, ilke durumunu **Yönet** > **Raporlar** altındaki ilke dikey penceresinde görebilirsiniz.

##  <a name="device-compliance"></a>Cihaz uyumluluğu

Cihaz uyumluluğu raporunun özet görünümü, aşağıdaki durumlardan birinde raporlama yapan cihaz sayısı hakkında toplu bilgileri listeler:

- **Uyumlu**: Cihaz yakın zamanda Değerlendirilmiş ve belirttiğiniz uyumluluk profili ayarları ile uyumludur.
- **Uyumsuz**: Cihaz Değerlendirilmiş ve uyumsuz olduğu saptanmıştır.  Profilde bir yetkisiz kullanım süresi belirtilmişse, yetkisiz kullanım süresi sona erdiğinden cihaz uyumsuz duruma gelmiştir.
- **Yetkisiz kullanım süresi**: Cihaz Değerlendirilmiş ve uyumsuz olduğu saptanmıştır. Bununla birlikte, cihaz uyumsuz olarak işaretlenmeden önce yetkisiz kullanım süresi geçerli olacaktır.

Tek tek cihazlar ve kullanıcılarla ilgili diğer ayrıntıları görmek için, her bölümde detaya gidebilirsiniz.

## <a name="setting-compliance"></a>Ayar uyumluluğu

Ayar uyumluluğu raporu, her uyumluluk ayarı için aşağıdakiler gibi ayrıntıları sağlar:

- Ayarla uyumsuz olan cihazların sayısı.
- Ayarın geçerli olduğu platform.

Bu ayarların etkinleştirildiği profiller hakkında daha fazla bilgiye ulaşmak ve ayarın değerini görmek için, her ayarda detaya gidebilirsiniz.
