---
title: "Cihaz uyumluluğunu izleme"
titlesuffix: Azure portal
description: "Cihaz uyumluluğunu izleme hakkında bilgi edinin.\""
keywords: 
author: andredm7
ms.author: andredm
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
ms.openlocfilehash: 9cd8bb0486164dd9dfe020261da9079ea5a68633
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
---
# <a name="how-to-monitor-device-compliance-in-intune"></a>Intune'da cihaz uyumluluğunu izleme

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**Genel Bakış** dikey penceresinde **uyumluluk profillerinizin** durumunun özetini görüntüleyebilirsiniz.
Detaya gitmek için grafiklere tıklayarak etkileşimli çalışabilirsiniz. Yapılandırılmış birden çok uyumluluk profiliniz varsa, ilke dikey penceresine gidip **Yönet** bölümünde **Raporlar**’ı seçerek her ilkenin durumunu da görüntüleyebilirsiniz.  Bulunan raporların ayrıntıları aşağıda listelenmiştir.

##  <a name="device-compliance"></a>Cihaz uyumluluğu

Cihaz uyumluluğu raporunun özetlenmiş görünümü, size aşağıdaki değerlendirmelerden biriyle raporlanan cihaz sayısı hakkında toplu bilgileri gösterir:

- **Uyumlu**: Cihaz belirttiğiniz uyumluluk profili ayarlarına göre kısa süre önce uyumluluk açısından değerlendirilmiş ve uyumlu olduğu saptanmıştır.
- **Uyumsuz**: Cihaz değerlendirilmiş ve uyumsuz olduğu saptanmıştır.  Profilde bir yetkisiz kullanım süresi belirtilmişse, yetkisiz kullanım süresi sona erdiğinden cihaz uyumsuz duruma gelmiştir.
- **Yetkisiz kullanım süresi**: Cihaz değerlendirilmiş ve uyumsuz olduğu saptanmıştır. Bununla birlikte, cihaz gerçekten uyumsuz olarak işaretlenmeden önce yetkisiz kullanım süresi geçerli olacaktır.

Tek tek cihazlar ve kullanıcılarla ilgili diğer ayrıntıları görmek için, her bölümde detaya gidebilirsiniz.

## <a name="setting-compliance"></a>Ayar uyumluluğu

Ayar uyumluluğu raporu, her uyumluluk ayarı için aşağıdakiler gibi ayrıntıları sağlar:

- Ayarla uyumsuz olan cihazların sayısı.
- Ayarın geçerli olduğu platform.

Bu ayarların etkinleştirildiği profiller hakkında daha fazla bilgiye ulaşmak ve ayarın değerini görmek için, her ayarda detaya gidebilirsiniz.
