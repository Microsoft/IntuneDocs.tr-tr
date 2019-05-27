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
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f29d2894-e98b-4f2c-b444-a8ccc1b7efdd
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6f700a93c9640381e33b4b1d1fd442f9442acbe1
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66050532"
---
# <a name="special-migration-considerations"></a>Geçiş konusunda dikkat edilmesi gereken önemli noktalar

Geçiş konusunda, mevcut MDM sağlayıcısı ortamınıza bağlı olarak geçerli olabilecek bazı önemli noktalar vardır.

## <a name="wipe-for-apples-device-enrollment-program-dep"></a>Apple’ın Aygıt Kayıt Programı (DEP) için Silme

Apple Aygıt Kayıt Programı (DEP), son kullanıcı tarafından kaldırılamayan cihaz yapılandırmaları uygular. DEP’in gelişmiş yönetim özelliklerini korumak üzere cihazın Intune’a kaydedilebilmesi için silinerek kullanıma hazır (yeni) duruma getirilmesi gerekir.

Intune'da cihaz yönetmede DEP kullanmaya devam etmek için, [Cihaz Kayıt Programı ile iOS cihaz kaydı ayarlarını yapın](device-enrollment-program-enroll-ios.md).


## <a name="next-steps"></a>Sonraki adımlar

[2. Aşama: Geçiş kampanyası](migration-guide-campaign.md)
