---
title: "Microsoft Intune ile cihazları yönetme"
titleSuffix: 
description: "Intune ile yönettiğiniz cihazları gözden geçirin ve bu cihazlar üzerinde çeşitli işlemler yapın."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/21/2018
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2e69f47e841cb44ab646431d5bd81b9c1d874c64
ms.sourcegitcommit: aafed032492c1b5861d7097a335f9bbb29ce3221
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/02/2018
---
# <a name="what-is-microsoft-intune-device-management"></a>Microsoft Intune cihaz yönetimi nedir?


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

BT yöneticisi olarak, yönetilen cihazların son kullanıcılarınızın işlerini yapması için gereken kaynakları sağladığından ve aynı zamanda verilerin risklerden korunduğundan emin olmanız gerekir.

**Cihazlar** iş yükü, yönettiğiniz cihazlarla ilgili bilgi sahibi olmanızı sağlar ve bu cihazlar üzerinde uzak görevler gerçekleştirmenize olanak tanır. İş yüküne erişmek için:

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune**’da **Cihazlar**’ı seçin.
4. Cihaz bilgilerini görüntüleyebilir ve aşağıdaki uzak cihaz eylemlerini gerçekleştirebilirsiniz:
    - **Genel bakış** - Yönetebileceğiniz kayıtlı cihazların anlık görüntüsü.
    - **Tüm cihazlar** - Yönettiğiniz kayıtlı cihazların listesi. Görüntülenen bilgileri geliştirmek için **Filtre** veya **Sütunlar**’ı seçin. [Cihaz envanterini görüntülemek](device-inventory.md) için bir cihaz seçin.
    - **Azure AD cihazları** - Azure Active Directory (AD) ile kaydedilen veya bu hizmete katılan cihazların listesi. [Azure AD cihaz yönetimi](https://docs.microsoft.com/azure/active-directory/device-management-introduction) hakkında daha fazla bilgi edinin.
    - **Cihaz eylemleri** - Eylem, eylemin durumu, eylemi kimin başlattığı ve süresi dahil olmak üzere cihazda gerçekleştirilen uzak eylemlerin geçmişi.

        ![Cihaz eylemlerini izleme ekran görüntüsü](./media/monitor-device-actions.png)

    - **Denetim günlükleri** - Denetim günlükleri size, Microsoft Intune'da değişiklik yaratan etkinliklerin kaydını sağlar. [Denetim günlükleri](monitor-audit-logs.md) hakkında daha fazla bilgi edinin.
    - **TeamViewer Bağlayıcısı** - TeamViewer hizmeti, Intune ile yönetilen Android cihazlarda kullanıcıların BT yöneticilerinden uzaktan yardım almasını sağlar. [TeamViewer](device-profile-android-teamviewer.md) hakkında daha fazla bilgi edinin.
    - **Yardım ve Destek** - Sorun giderin, destek isteyin veya Intune durumunu görüntüleyin.  
    
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

- Yönettiğiniz cihazlarda gerçekleştirilen eylemlerin durumunu görmek için **Cihaz eylemleri**’ni seçin.
