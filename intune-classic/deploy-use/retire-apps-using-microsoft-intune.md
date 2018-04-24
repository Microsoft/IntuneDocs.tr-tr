---
title: Uygulamaları devre dışı bırakma
description: Intune’u kullanarak uygulamaların nasıl devre dışı bırakılacağını veya kaldırılacağını öğrenin.
keywords: ''
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6fbf0805-1144-4e08-bafd-4f181d932bf2
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: a3fadf497e5db147d12ecf1e32343e94222c65e9
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="retire-apps-using-microsoft-intune"></a>Microsoft Intune’u kullanarak uygulamaları devre dışı bırakma

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Uygulamayı devre dışı bırakmak için kaldırmanız yeterli olur. Uygulamaları Intune ile dağıtıp yönettiğinizde, bunları kaldırma işlemleri hem mobil cihazlarda ve hem de Windows bilgisayarlarında aynıdır. Bu yordamın başarılı olması için uygulamanın kaldırma işlemini desteklemesi gerekir.

## <a name="uninstall-an-app"></a>Uygulamayı kaldırma

1.  [Microsoft Intune yönetici konsolunda](https://manage.microsoft.com) **Uygulamalar** &gt; **Uygulamalar**’ı seçin.

2.  Kaldırmak istediğiniz uygulamayı (daha önce dağıtılmış olan bir uygulama) seçin ve ardından **Dağıtımı Yönet**’i seçin.

3.  **Dağıtım Eylemi** sayfasında **Onay** sütunundan **Kaldır** ’ı seçin:

Cihaz veya bilgisayar tarafından gerçekleştirilen bir sonraki uygulama denetiminde uygulama kaldırılır.

### <a name="see-also"></a>Ayrıca bkz:
[Microsoft Intune'da uygulamalar ekleme](add-apps.md)
