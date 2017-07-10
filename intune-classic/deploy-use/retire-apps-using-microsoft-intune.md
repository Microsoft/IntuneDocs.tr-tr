---
title: "Uygulamaları devre dışı bırakma"
description: "Intune’u kullanarak uygulamaların nasıl devre dışı bırakılacağını veya kaldırılacağını öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6fbf0805-1144-4e08-bafd-4f181d932bf2
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1851fa03d36ffe42a49fd557cdd0c2c6250726f4
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="retire-apps-using-microsoft-intune"></a>Microsoft Intune’u kullanarak uygulamaları devre dışı bırakma

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Uygulamayı devre dışı bırakmak için kaldırmanız yeterli olur. Uygulamaları Intune ile dağıtıp yönettiğinizde, bunları kaldırma işlemleri hem mobil cihazlarda ve hem de Windows bilgisayarlarında aynıdır. Bu yordamın başarılı olması için uygulamanın kaldırma işlemini desteklemesi gerekir.

## <a name="uninstall-an-app"></a>Uygulamayı kaldırma

1.  [Microsoft Intune yönetici konsolunda](https://manage.microsoft.com) **Uygulamalar** &gt; **Uygulamalar**’ı seçin.

2.  Kaldırmak istediğiniz uygulamayı (daha önce dağıtılmış olan bir uygulama) seçin ve ardından **Dağıtımı Yönet**’i seçin.

3.  **Dağıtım Eylemi** sayfasında **Onay** sütunundan **Kaldır** ’ı seçin:

Cihaz veya bilgisayar tarafından gerçekleştirilen bir sonraki uygulama denetiminde uygulama kaldırılır.

### <a name="see-also"></a>Ayrıca bkz.
[Microsoft Intune'da uygulamalar ekleme](add-apps.md)
