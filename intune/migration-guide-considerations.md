---
title: Geçiş konusunda dikkat edilmesi gereken önemli noktalar
titlesuffix: Microsoft Intune
description: Bu makalede, Microsoft Intune’a geçiş sürecini başlatmadan önce geçiş konusunda dikkat edilmesi gereken önemli noktalar sağlanmaktadır.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f29d2894-e98b-4f2c-b444-a8ccc1b7efdd
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: 23619048faca4cdf9d64b15b0db7c09cb958a082
ms.sourcegitcommit: 4d314df59747800169090b3a870ffbacfab1f5ed
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/30/2018
ms.locfileid: "43314049"
---
# <a name="special-migration-considerations"></a>Geçiş konusunda dikkat edilmesi gereken önemli noktalar

Geçiş konusunda, mevcut MDM sağlayıcısı ortamınıza bağlı olarak geçerli olabilecek bazı önemli noktalar vardır.

## <a name="wipe-for-apples-device-enrollment-program-dep"></a>Apple’ın Aygıt Kayıt Programı (DEP) için Silme

Apple Aygıt Kayıt Programı (DEP), son kullanıcı tarafından kaldırılamayan cihaz yapılandırmaları uygular. DEP’in gelişmiş yönetim özelliklerini korumak üzere cihazın Intune’a kaydedilebilmesi için silinerek kullanıma hazır (yeni) duruma getirilmesi gerekir.

Intune'da cihaz yönetmede DEP kullanmaya devam etmek için, [Cihaz Kayıt Programı ile iOS cihaz kaydı ayarlarını yapın](device-enrollment-program-enroll-ios.md).


## <a name="next-steps"></a>Sonraki adımlar

[2. Aşama: Geçiş kampanyası](migration-guide-campaign.md)
