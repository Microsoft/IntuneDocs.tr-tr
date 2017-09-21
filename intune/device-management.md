---
title: "Intune ile cihazları yönetme"
titleSuffix: Intune on Azure
description: "Intune ile yönettiğiniz cihazları görmeyi ve bu cihazlar üzerinde çeşitli işlemler yapmayı öğrenin.\""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/31/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0686b3ece3a929cb06a29f4e58046872b70ec926
ms.sourcegitcommit: b8987b8dfb009ea55678d7f640ac5f18a6ab167e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2017
---
# <a name="what-is-microsoft-intune-device-management"></a>Microsoft Intune cihaz yönetimi nedir?


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

BT yöneticisi olarak, yönetilen cihazların son kullanıcılarınızın işlerini yapması için gereken kaynakları sağladığından ve aynı zamanda verilerin risklerden korunduğundan emin olmanız gerekir.

**Cihazlar** iş yükü, yönettiğiniz cihazlarla ilgili bilgi sahibi olmanızı sağlar ve bu cihazlar üzerinde uzak görevler gerçekleştirmenize olanak tanır. İş yüküne erişmek için:

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune**’da **Cihazlar**’ı seçin.
4. Cihaz bilgilerini görüntüleyebilir ve aşağıdaki uzak cihaz eylemlerini gerçekleştirebilirsiniz:
    - **Genel bakış** - Yönetebileceğiniz kayıtlı cihazların anlık görüntüsü.
    - **Tüm cihazlar** - Yönettiğiniz kayıtlı cihazların listesi. Görüntülenen bilgileri geliştirmek için **Filtre** veya **Sütunlar**’ı seçin. [Cihaz envanterini görüntülemek](device-inventory.md) için bir cihaz seçin.
    - **Azure AD cihazları** - Azure Active Directory (AD) ile kaydedilen veya bu hizmete katılan cihazların listesi. [Azure AD cihaz yönetimi](https://docs.microsoft.com/azure/active-directory/device-management-introduction) hakkında daha fazla bilgi edinin.
    - **Cihaz eylemleri** - Eylem, eylemin durumu, eylemi kimin başlattığı ve süresi dahil olmak üzere cihazda gerçekleştirilen uzak eylemlerin geçmişi.

    ![Cihaz eylemlerini izleme](./media/monitor-device-actions.png)

    - **TeamViewer** - TeamViewer hizmeti, Intune ile yönetilen Android cihazlarda kullanıcıların BT yöneticilerinden uzaktan yardım almasını sağlar. [TeamViewer](device-profile-android-teamviewer.md) hakkında daha fazla bilgi edinin.

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
