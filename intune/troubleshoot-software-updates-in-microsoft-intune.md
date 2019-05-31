---
title: Microsoft Intune - Azure yazılım güncelleştirmesi sorunlarını giderme | Microsoft Docs
description: Microsoft Intune’da yazılım güncelleştirmesi sorunlarını çözün.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/29/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: d17b70f4-17b4-4d89-88fd-70fa4f34fbea
ROBOTS: ''
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: ee5ed6339efff4b3e32a9c10ac756d7f8bec6260
ms.sourcegitcommit: a97b6139770719afbd713501f8e50f39636bc202
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/30/2019
ms.locfileid: "66402628"
---
# <a name="troubleshoot-software-updates-in-microsoft-intune"></a>Microsoft Intune’da yazılım güncelleştirmesi sorunlarını giderme

Microsoft Intune yazılım güncelleştirmesi sorunlarını çözmeye yardımcı olur. Hata kodlarını ve açıklamalarını listesini görmek için Git [yazılım güncelleştirme Aracısı hata kodları Microsoft Intune](software-update-agent-error-codes.md).

## <a name="windows-7-devices-with-many-superseded-updates-stop-reporting-to-intune"></a>Birçok yenisiyle değiştirilen güncelleştirmeleri Durdur Intune'a Raporlama ile Windows 7 cihazları

Microsoft Intune istemcilerinin aşağıdaki belirtilerden birini veya karşılaşabilirsiniz:

- Cihazlar Intune'a raporlama aniden durdurun.  
- Cihazlar, yüksek CPU kullanımı deneyimi.
- Uygulamalar, Intune aracılığıyla yüklendiğinde yavaş yükleniyor.
- Microsoft Intune Center şu hatayı gösterir: `An error occurred while updating your computer. Error found: Code 0x800705b4`.
- Intune Yönetici Konsolu > Gruplar > Tüm cihazlar > durumunu gösterir: `One or more agents that are installed on this computer have errors. The information for this computer may not be accurate or up-to-date.`

Bu sorun yenisiyle (güncelleştirmeleri başka bir güncelleştirmeyle değiştirilir) güncelleştirmeler uzun bir süre için reddedilen henüz oluşabilir. Uygulama yükleme gibi bazı işlemler sırasında güncelleştirmeler ve ardılları doğru bir şekilde eşlenir, böylece tüm güncelleştirmeleri sırayla yerini Windows denetler. Yenisiyle değiştirilen güncelleştirmeler listesi çok büyük olursa işlem yükü ve gereken süre nedeniyle bu denetim görevi yüksek CPU kullanımına neden olabilir. Bu sorun öncelikle nedeniyle çok sayıda Windows 7 için yenisiyle değiştirilen güncelleştirmeler Windows 7 cihazları etkiler. Daha yeni işletim sistemlerini çok kullanılabilir yenisiyle değiştirilen güncelleştirmeleri olmayabilir ve bu sorun için açık olmayabilir.

**Çözümleme**

1. Oturum [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Seçin **yazılım güncelleştirmelerini**.
3. Microsoft Office gibi uygulamalar için etkilenen istemcilere yüklenmiş olan ya da Windows 7'ye uygulanabilecek, yenisiyle değiştirilmiş tüm güncelleştirmeleri reddedin.
4. Etkilenen istemcileri yeniden başlatın.

Windows 7 çalıştırıyorsanız şu güncelleştirmenin yüklü olduğundan emin olun:[3050265 Windows Update istemcisi Windows 7 için: Haziran 2015](https://support.microsoft.com/kb/3050265).

## <a name="next-steps"></a>Sonraki adımlar

Alma [destekleyen Microsoft gelen Yardım](get-support.md), veya [topluluk forumları](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune).