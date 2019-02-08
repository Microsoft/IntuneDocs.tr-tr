---
title: Cihazları Microsoft Intune - Azure ile kilitleme | Microsoft Docs
description: PIN veya parola ile korunan bir cihazı kilitlemek için Microsoft Intune'daki Uzaktan kilitleme eylemini kullanın.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3b67f285-229d-4a0f-ae34-0402a20b4518
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ced5bf8a982e2dbf65ff0577ca2f17529febcb62
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55851517"
---
# <a name="remotely-lock-devices-with-intune"></a>Intune ile cihazları uzaktan kilitleme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

**Uzaktan kilitleme** cihaz eylemi, cihazı kilitler. Cihazın kilidini açmak için cihaz sahibi geçiş kodunu girer. PIN veya parolası bulunan cihazları uzaktan kilitleyebilirsiniz. PIN veya parolası olmayan cihazlar uzaktan kilitlenemez.

## <a name="supported-platforms"></a>Desteklenen platformlar

**Uzaktan kilitleme**, aşağıdaki platformlarda desteklenir:

- Android
- Android kurumsal bilgi noktası cihazları
- Android kurumsal iş profili cihazlar
- iOS
- Mac OS
- Windows 10 Mobile
- Windows Phone 8.1 ve üzeri

Şu platformlarda **Uzaktan kilitleme** desteklenmez:
- Windows 10 masaüstü

> [!NOTE]
> macOS cihazlar için 6 basamaklı bir kurtarma PIN’i ayarlarsınız. Cihaz kilitliyken, **Cihaz genel bakışı** başka bir cihaz eylemi gönderilene kadar PIN’i görüntüler.

## <a name="remote-lock-a-device"></a>Cihazı uzaktan kilitleme

1. [Azure Portal](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve ardından **Microsoft Intune**’u seçin.
3. **Cihazlar** > **Tüm cihazlar**’ı seçin.
4. Cihaz listesinde bir cihaz seçin ve ardından **Uzaktan kilitle** eylemini seçin.

## <a name="next-steps"></a>Sonraki adımlar

- Bu eylemin durumunu görmek için **Microsoft Intune** > **Cihazlar** > **Cihaz eylemleri**'ni yapın. 
- Cihazlarınızı yönetmenize yardımcı olabilecek diğer eylemler için bkz. [Kullanılabilir eylemler](device-management.md).
