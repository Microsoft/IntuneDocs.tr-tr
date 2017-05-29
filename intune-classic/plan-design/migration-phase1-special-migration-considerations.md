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
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 7e0adb862d8c60805b3b34406e193df5a93be381
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---

# <a name="phase-1-special-migration-considerations"></a>1. Aşama: Geçiş konusunda dikkat edilmesi gereken önemli noktalar

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Geçerli MDM sağlayıcısı ortamınıza bağlı olarak uygulanabilen özel geçiş durumları vardır.

## <a name="factory-reset-for-apples-device-enrollment-program-dep"></a>Apple Aygıt Kayıt Programı (DEP) için fabrika ayarlarına sıfırlama

Apple Aygıt Kayıt Programı (DEP), son kullanıcı tarafından kaldırılamayan cihaz yapılandırmaları uygular. DEP’in gelişmiş yönetim özelliklerini korumak üzere cihazın Intune’a kaydedilebilmesi için fabrika ayarlarına sıfırlanarak kutudan çıktığı (yeni) haline getirilmesi gerekir.

Intune’da cihaz yönetmek üzere DEP kullanmaya devam etmek için:

1.  [DEP’i Intune'a](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune) ekleme

2.  Apple DEP hesabınıza gidin ve mevcut MDM sağlayıcınızdan Intune’a [DEP cihaz seri numaralarını yeniden atayın](https://help.apple.com/deployment/business/#/tesf9562af26).

3.  DEP hesabınızı Intune ile [eşitleyin](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune)

4.  Intune’daki seri numaralarına, uygun DEP kayıt profillerini [oluşturup atayın](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune).

5.  Cihazları fabrika ayarlarına sıfırlayın (geçerli MDM sağlayıcınız aracılığıyla uzaktan ya da her cihazda elle)

6.  Cihazları son kullanıcılara dağıtın.

## <a name="next-steps"></a>Sonraki adımlar 

[2. Aşama: Geçiş kampanyası](/intune-classic/plan-design/migration-phase2-migration-campaign)

