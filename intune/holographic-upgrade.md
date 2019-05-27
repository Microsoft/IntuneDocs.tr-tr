---
title: Windows Holographic for Business için yükseltme
titleSuffix: Microsoft Intune
description: Windows Holographic çalıştıran cihazları nasıl Windows Holographic for Business’a yükselteceğinizi öğrenin
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: c268785e3cce7477203e78f321af15c5067d51ae
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66041764"
---
# <a name="upgrade-devices-running-windows-holographic-to-windows-holographic-for-business"></a>Windows Holographic çalıştıran cihazları Windows Holographic for Business’a yükseltme

Microsoft Intune, cihazların yönetilmesine ve korunmasına yardımcı olmak üzere birçok ayarlarını içerir. Bu makale, listeler ve Windows Holographic for Business Windows Holographic cihazları yükseltmek için ayarları açıklar. Bu ayarlar, ıntune'a gönderilen veya cihazlara dağıttığınız yükseltme yapılandırma profilinde oluşturulur.

Mobil cihaz Yönetimi (MDM) çözümünüzün bir parçası olarak, Windows Holographic cihazları yükseltmek için bu ayarları kullanın. Microsoft HoloLens için ticari yükseltme için gerekli lisans almak için Suite satın alabilirsiniz. Daha fazla bilgi için bkz. [Windows Holographic for Business özelliklerini etkinleştirme](https://docs.microsoft.com/hololens/hololens-upgrade-enterprise).

Bu özellik hakkında daha fazla bilgi için bkz. [etkinleştir S modu veya Windows 10 yükseltme sürümlerini](edition-upgrade-configure-windows-10.md).

## <a name="before-you-begin"></a>Başlamadan önce

[Bir cihaz yapılandırma profili oluşturma](edition-upgrade-configure-windows-10.md#create-the-profile).

## <a name="edition-upgrade"></a>Sürüm yükseltme

- **Yükseltilecek sürüm**: Seçin **Windows 10 Holographic iş**.
- **Lisans dosyası**: Göz atın ve size sağlanan XML lisans dosyasını seçin.

  ![İş lisans bilgileri için Holographic içeren XML dosya adı girin](media/Holographic-edition-upgrade.png)
 
## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturulur, ancak, hiçbir şey henüz yapmadan. Mutlaka [profili atama](device-profile-assign.md), ve [atamanın durumunu izlemenize](device-profile-monitor.md).

Sürüm yükseltme profillerini oluşturabilirsiniz [Windows 10 ve üzeri](edition-upgrade-windows-settings.md) cihazlar.
