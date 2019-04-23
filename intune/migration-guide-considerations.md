---
title: Geçiş konusunda dikkat edilmesi gereken önemli noktalar
titleSuffix: Microsoft Intune
description: Bu makalede, Microsoft Intune’a geçiş sürecini başlatmadan önce geçiş konusunda dikkat edilmesi gereken önemli noktalar sağlanmaktadır.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f29d2894-e98b-4f2c-b444-a8ccc1b7efdd
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 15a3130263e19f8d6bef55427bf9a53f8e8b42ef
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61508387"
---
# <a name="special-migration-considerations"></a>Geçiş konusunda dikkat edilmesi gereken önemli noktalar

Geçiş konusunda, mevcut MDM sağlayıcısı ortamınıza bağlı olarak geçerli olabilecek bazı önemli noktalar vardır.

## <a name="wipe-for-apples-device-enrollment-program-dep"></a>Apple’ın Aygıt Kayıt Programı (DEP) için Silme

Apple Aygıt Kayıt Programı (DEP), son kullanıcı tarafından kaldırılamayan cihaz yapılandırmaları uygular. DEP’in gelişmiş yönetim özelliklerini korumak üzere cihazın Intune’a kaydedilebilmesi için silinerek kullanıma hazır (yeni) duruma getirilmesi gerekir.

Intune'da cihaz yönetmede DEP kullanmaya devam etmek için, [Cihaz Kayıt Programı ile iOS cihaz kaydı ayarlarını yapın](device-enrollment-program-enroll-ios.md).


## <a name="next-steps"></a>Sonraki adımlar

[2. Aşama: Geçiş kampanyası](migration-guide-campaign.md)
