---
title: Exchange tarafından yönetilen mobil cihazlar için temizleme
description: Microsoft Intune, Intune Exchange Connector ile Exchange ActiveSync (EAS) kullanılarak yönetilen mobil cihazları temizlemenize veya sıfırlamanıza olanak tanır
keywords: ''
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e116b620-1e12-4b5c-9905-2f7acf2ae530
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: lancecra
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 753e5e9dac7199dff18d110808524f05aa669036
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31016093"
---
# <a name="wipe-for-exchange-managed-mobile-devices"></a>Exchange tarafından yönetilen mobil cihazlar için temizleme 

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Microsoft Intune, Intune Exchange Bağlayıcısı’yla Exchange ActiveSync (EAS) kullanılarak yönetilen mobil cihazları temizlemenize veya sıfırlamanıza olanak tanır. Aşağıdaki tabloda Exchange ActiveSync aracılığıyla sağlanan temizleme özellikleri açıklanmaktadır:


|      Temizleme türü       |              Windows 8.1 ve Windows RT 8.1              |                            iOS                             |                          Android                          |
|-------------------------|----------------------------------------------------------|------------------------------------------------------------|-----------------------------------------------------------|
|        Tam temizleme        |          Posta hesabını ve önbelleğe alınan postaları kaldırır.           |                      XFabrika sıfırlaması.                       |                      Fabrika sıfırlaması.                       |
|  Seçici temizleme/e-posta   |                  E-posta hesabını kaldırır.                  |                       Desteklenmez.                       |                      Desteklenmez.                       |
| Seçici temizleme/ilkeler | İlke zorlama kaldırılır, ancak ayarlar değiştirilmez | Xİlke zorlama kaldırılır, ancak ayarlar değiştirilmez. | İlke zorlaması kaldırılır, ancak ayarlar değiştirilmez. |

