---
title: "Geçiş konusunda dikkat edilmesi gereken önemli noktalar | Microsoft Docs"
description: "Bu makalenin amacı, bir geçiş kampanyasına başlamadan önce müşterilere geçiş konusunda dikkat edilmesi gereken önemli noktaları sağlamaktır."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f29d2894-e98b-4f2c-b444-a8ccc1b7efdd
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab5aa4e12d951d818c5afb4e1ac5e866b05733fb
ms.openlocfilehash: 634e84312fa1a93eb85bf70e1593ca11359b72ff
ms.lasthandoff: 03/27/2017


---

# <a name="phase-1-special-migration-considerations"></a>1. Aşama: Geçiş konusunda dikkat edilmesi gereken önemli noktalar

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Geçerli MDM sağlayıcısı ortamınıza bağlı olarak uygulanabilen özel geçiş durumları vardır.

## <a name="factory-reset-for-apples-device-enrollment-program-dep"></a>Apple Aygıt Kayıt Programı (DEP) için fabrika ayarlarına sıfırlama

Apple Aygıt Kayıt Programı (DEP), son kullanıcı tarafından kaldırılamayan cihaz yapılandırmaları uygular. DEP’in gelişmiş yönetim özelliklerini korumak üzere cihazın Intune’a kaydedilebilmesi için fabrika ayarlarına sıfırlanarak kutudan çıktığı (yeni) haline getirilmesi gerekir.

Intune’da cihaz yönetmek üzere DEP kullanmaya devam etmek için:

1.  [DEP’i Intune'a](https://docs.microsoft.com/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) ekleme

2.  Apple DEP hesabınıza gidin ve mevcut MDM sağlayıcınızdan Intune’a [DEP cihaz seri numaralarını yeniden atayın](https://help.apple.com/deployment/business/#/tesf9562af26).

3.  DEP hesabınızı Intune ile [eşitleyin](https://docs.microsoft.com/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune)

4.  Intune’daki seri numaralarına, uygun DEP kayıt profillerini [oluşturup atayın](https://docs.microsoft.com/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune).

5.  Cihazları fabrika ayarlarına sıfırlayın (geçerli MDM sağlayıcınız aracılığıyla uzaktan ya da her cihazda elle)

6.  Cihazları son kullanıcılara dağıtın.

## <a name="next-steps"></a>Sonraki adımlar 

[2. Aşama: Geçiş kampanyası](https://docs.microsoft.com/intune/plan-design/migration-phase2-migration-campaign)

