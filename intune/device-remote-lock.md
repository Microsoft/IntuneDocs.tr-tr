---
title: "Cihazları Microsoft Intune - Azure ile kilitleme | Microsoft Docs"
description: "PIN veya parola ile korunan bir cihazı kilitlemek için Microsoft Intune'daki Uzaktan Kilitleme eylemini kullanın."
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b67f285-229d-4a0f-ae34-0402a20b4518
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 59a55de54a5a18f5fd1080fefa15c0e4801a1456
ms.sourcegitcommit: 9cf05d3cb8099e4a238dae9b561920801ad5cdc6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/09/2018
---
# <a name="remotely-lock-devices-with-intune"></a>Intune ile cihazları uzaktan kilitleme

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**Uzaktan kilitleme**, cihazı kilitler. Kilidi açmak için cihaz sahibi geçiş kodunu girer. PIN veya parolası bulunan cihazları uzaktan kilitleyebilirsiniz. PIN veya geçiş kodu olmayan cihazlar uzaktan kilitlenemez.

## <a name="supported-platforms"></a>Desteklenen platformlar

Uzaktan kilit, aşağıdaki platformlarda desteklenir:

- Android
- iOS
- Mac OS
- Windows 10 Mobile
- Windows Phone 8.1 ve üzeri

Aşağıdakiler için **desteklenmez**:
- Windows 10 masaüstü

> [!NOTE]
> macOS cihazlar için 6 basamaklı bir kurtarma PIN’i ayarlarsınız. Kilitliyken, **Cihaz genel bakışı**, başka bir cihaz eylemi gönderilene kadar PIN’i görüntüler.

## <a name="remote-lock-a-device"></a>Cihazı uzaktan kilitleme

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
3. **Cihazlar**’ı ve ardından **Tüm cihazlar**’ı seçin.
4. Cihaz listesinden bir cihaz seçin ve ardından **Uzaktan kilitle** eylemini seçin.

## <a name="next-steps"></a>Sonraki adımlar

Bu eylemin durumunu görmek için **Cihaz eylemleri**’ni (Microsoft Intune > Cihazlar) açın. [Kullanılabilir eylemler](device-management.md) bölümünde cihazlarınızı yönetmeye yardımcı olacak daha fazla eylem görebilirsiniz.