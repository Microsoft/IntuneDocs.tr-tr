---
title: Microsoft Intune-Azure 'da yazılım güncelleştirmelerinin sorunlarını giderme | Microsoft Docs
description: Microsoft Intune’da yazılım güncelleştirmesi sorunlarını çözün.
keywords: ''
author: Brenduns
ms.author: brenduns
manager: dougeby
ms.date: 05/29/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: d17b70f4-17b4-4d89-88fd-70fa4f34fbea
ROBOTS: ''
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7da927754971fb66a5d8442d0cdf18e0ebfbcd4a
ms.sourcegitcommit: 78cebd3571fed72a3a99e9d33770ef3d932ae8ca
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74059071"
---
# <a name="troubleshoot-software-updates-in-microsoft-intune"></a>Microsoft Intune’da yazılım güncelleştirmesi sorunlarını giderme

Microsoft Intune 'de yazılım güncelleştirme sorunlarını çözmeye yardımcı olun. Hata kodlarının ve açıklamalarının listesini görmek için [Microsoft Intune ' de yazılım güncelleştirme Aracısı hata kodları](../protect/software-update-agent-error-codes.md)' na gidin.

## <a name="windows-7-devices-with-many-superseded-updates-stop-reporting-to-intune"></a>Birçok yenisiyle değiştirilen Windows 7 cihazları Intune 'a raporlamayı durdurur

Microsoft Intune istemcileri aşağıdaki belirtilerden birini veya daha fazlasını yaşayabilirler:

- Cihazlar aniden Intune 'a raporlamayı durdurur.  
- Cihazlar yüksek CPU kullanımı yaşar.
- Uygulamalar, Intune aracılığıyla yüklendiğinde yavaş yüklenir.
- Microsoft Intune Center şu hatayı gösterir: `An error occurred while updating your computer. Error found: Code 0x800705b4`.
- Intune yönetici konsolu, gruplar > Tüm Cihazlar > durum > gösterir. `One or more agents that are installed on this computer have errors. The information for this computer may not be accurate or up-to-date.`

Bu sorun, yenisiyle değiştirilen güncelleştirmeler (güncelleştirmeler başka bir güncelleştirmeyle değiştirilirse) uzun bir süre reddedilmemişse oluşabilir. Bir uygulamayı yükleme gibi belirli işlemlerde Windows, güncelleştirmelerin ve ardıllarını doğru şekilde eşlenmelidir şekilde sırayla yenisiyle değiştirilen tüm güncelleştirmeleri denetler. Yenisiyle değiştirilen güncelleştirmelerin listesi çok büyük alırsa, bu denetim görevi, işlem yükü ve gereken süre nedeniyle yüksek CPU kullanımına neden olabilir. Bu sorun, Windows 7 ' de bulunan çok sayıda yenisiyle değiştirilen çok sayıda güncelleştirme nedeniyle Windows 7 cihazlarını etkiler. Daha yeni işletim sistemleri, yenisiyle değiştirilen çok sayıda güncelleştirmeye sahip olmayabilir ve bu soruna maruz kalabilir.

**Çözünürlüğüne**

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. **Yazılım güncelleştirmelerini**seçin.
3. Windows 7 ' ye veya etkilenen istemcilere yüklenmiş Microsoft Office gibi uygulamalara uygulanabilecek yenisiyle değiştirilen tüm güncelleştirmeleri reddedin.
4. Etkilenen istemcileri yeniden başlatın.

Windows 7 çalıştırıyorsanız, aşağıdaki güncelleştirmenin yüklü olduğundan emin olun:[3050265 Windows Update Windows 7 Için istemcisi: haziran 2015](https://support.microsoft.com/kb/3050265).

## <a name="next-steps"></a>Sonraki adımlar

[Microsoft 'un destek yardımına](get-support.md)ulaşın veya [topluluk forumlarını](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune)kullanın.