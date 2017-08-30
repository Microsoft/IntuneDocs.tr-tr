---
title: "Intune ile cihazları yönetme"
titleSuffix: Intune on Azure
description: "Intune ile yönettiğiniz cihazları görmeyi ve bu cihazlar üzerinde çeşitli işlemler yapmayı öğrenin.\""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5d78b4a87eaa366b7bb00356c4b98d609620dcf3
ms.sourcegitcommit: 4dc5bed94cc965a54eacac2d87fb2d49c9300c3a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2017
---
# <a name="what-is-microsoft-intune-device-management"></a>Microsoft Intune cihaz yönetimi nedir?


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**Cihazlar** iş yükü, yönettiğiniz cihazlarla ilgili bilgi sahibi olmanızı sağlar ve bu cihazlar üzerinde uzak görevler gerçekleştirmenize olanak tanır. İş yüküne erişmek için:

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihazlar**’ı seçin.
4. Cihaz bilgilerini görüntüleyebilir ve listelenen uzak cihaz eylemlerini gerçekleştirebilirsiniz.

## <a name="available-device-actions"></a>Kullanılabilir cihaz eylemleri
Kullanılabilir eylemler, cihaz platformuna ve cihazın yapılandırmasına bağlıdır.

- [Cihaz envanterini görüntüleme](device-inventory.md)
- Uzak cihaz eylemleri gerçekleştirme:
    - [Şirket verilerini kaldır](devices-wipe.md#remove-company-data)
    - [Fabrika sıfırlaması](devices-wipe.md#factory-reset)
    - [Uzaktan kilitleme](device-remote-lock.md) 
    - [Geçiş Kodunu Sıfırla](device-passcode-reset.md)
    - [Etkinleştirme Kilidini Atlama](device-activation-lock-bypass.md) (yalnızca iOS)
    - [Yeni Başlangıç](device-fresh-start.md) (yalnızca Windows)
    - [Kayıp modu](device-lost-mode.md) (yalnızca iOS)
    - [Cihaz bulma](device-locate.md) (yalnızca iOS)
    - [Yeniden başlatma](device-restart.md) (yalnızca Windows)
    - [Windows 10 PIN sıfırlama](device-windows-pin-reset.md)
    - [Android için uzaktan denetim](device-profile-android-teamviewer.md)
    - [Cihazı eşitleme](device-sync.md)


## <a name="next-steps"></a>Sonraki adımlar

- Yönettiğiniz cihazlarda gerçekleştirilen eylemlerin durumunu görmek için **Cihaz Eylemleri**’ni seçin.
![Cihaz eylemlerini izleme](./media/monitor-device-actions.png)
