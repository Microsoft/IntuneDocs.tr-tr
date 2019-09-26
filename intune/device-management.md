---
title: Microsoft Intune - Azure ile cihaz yönetme | Microsoft Docs
description: Microsoft Intune ile yönettiğiniz cihazları gözden geçirin. Cihazlar listesini cvs biçimine aktarın, Azure Active Directory katılımlı cihazlarınızı görüntüleyin, cihazdaki eylemlerin değişiklik günlüğünü gözden geçirin, BT yöneticilerinin Android cihazlarda uzaktan sorun gidermeleri için TeamViewer Connector’ı kullanın ve cihazlarınızda çalıştırabileceğiniz tüm eylemleri görüntüleyin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/19/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: a68a6ef0224cde88d0414b5225610448b01218f1
ms.sourcegitcommit: c19584b36448bbd4c8638d7cab552fe9b3eb3408
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/20/2019
ms.locfileid: "71304757"
---
# <a name="what-is-microsoft-intune-device-management"></a>Microsoft Intune cihaz yönetimi nedir?

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

BT yöneticisi olarak, kullanıcılarınızın işlerini yapması için gereken kaynakların yönetilen cihazlar tarafından sağlandığından ve aynı zamanda verilerin risklerden korunduğundan emin olmanız gerekir.

**Cihazlar** iş yükü, yönettiğiniz cihazlarla ilgili bilgi sahibi olmanızı sağlar ve bu cihazlar üzerinde uzak görevler gerçekleştirmenize olanak tanır.

## <a name="get-to-your-devices"></a>Cihazlarınıza ulaşma

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
3. **Cihazlar**’ı seçin. Burada ayrı ayrı tüm cihazlar hakkında ayrıntılı bilgiler ve bu cihazlarla yapabilecekleriniz görüntülenir. Yapabilecekleriniz şöyledir:

   - **Genel Bakış**, kayıtlı cihazların görsel anlık görüntüsünü ve kaç tane cihazın Android, iOS vb. gibi farklı platformlar kullandığını gösterir.
   - **Tüm cihazlar**, yönettiğiniz kayıtlı cihazların listesini gösterir.

     **Dışarı Aktar** özelliğini kullanarak tüm cihazların .csv listesini oluşturabilirsiniz. Listenin sınırları 10.000 (Internet Explorer) ve 30.000’dir (Microsoft Edge, Chrome).

     Donanım ayrıntıları, yüklü uygulamalar, uyumluluk ilkesi durumu ve daha fazlası dahil olmak üzere [Bu cihazla ilgili ek ayrıntıları görüntülemek](device-inventory.md)için herhangi bir cihaz seçin.

   - **Azure AD cihazları**, Azure Active Directory (AD) ile kaydedilen veya bu hizmete katılan cihazların listesini gösterir. [Azure AD cihaz yönetimi](https://docs.microsoft.com/azure/active-directory/device-management-introduction) hakkında daha fazla bilgi edinin.
   - **Cihaz eylemleri**; eylem, eylemin durumu, eylemi kimin başlattığı ve süresi dahil olmak üzere cihazda gerçekleştirilen uzak eylemlerin geçmişini gösterir.

     ![Cihaz eylemlerini izleme ekran görüntüsü](./media/monitor-device-actions.png)

   - **Denetim günlükleri**, Intune’da değişiklik yaratan etkinliklerin kaydıdır. [Denetim günlükleri](monitor-audit-logs.md) daha fazla ayrıntı sağlar.
   - **TeamViewer Bağlayıcısı**, Intune ile yönetilen Android cihazlarda kullanıcıların BT yöneticilerinden uzaktan yardım almasını sağlayan bir hizmettir. [TeamViewer](teamviewer-support.md) hakkında daha fazla bilgi edinin.
   - **Yardım ve Destek**; sorun giderme ipuçları, destek isteği veya Intune durumunu denetleme için bir kısayol sağlar.

## <a name="available-device-actions"></a>Kullanılabilir cihaz eylemleri
Kullanılabilir eylemler, cihaz platformuna ve cihazın yapılandırmasına bağlıdır.

- [Cihaz envanterini görüntüleme](device-inventory.md)
- Uzak cihaz eylemlerini çalıştırın:
  - [Devre Dışı Bırak](devices-wipe.md#retire)
  - [Silme](devices-wipe.md#wipe)
  - [Uzaktan kilitleme](device-remote-lock.md)
  - [Geçiş Kodunu Sıfırla](device-passcode-reset.md)
  - [Etkinleştirme Kilidini Atlama](device-activation-lock-bypass.md) (yalnızca iOS)
  - [Yeni Başlangıç](device-fresh-start.md) (yalnızca Windows)
  - [Kayıp modu](device-lost-mode.md) (yalnızca iOS)
  - [Cihaz bulma](device-locate.md) (yalnızca iOS)
  - [Yeniden başlatma](device-restart.md) (yalnızca Windows)
  - [Windows 10 PIN sıfırlama](device-windows-pin-reset.md)
  - [Android için uzaktan denetim](teamviewer-support.md)
  - [Cihazı eşitleme](device-sync.md)
  - [Özel bildirim gönder](custom-notifications.md#send-a-custom-notification-to-a-single-device) (Android, iOS)

## <a name="next-steps"></a>Sonraki adımlar

- **Tüm Cihazlar**’da bir cihaz seçerek o cihaz için daha fazla ayrıntı görüntüleyin.
- Yönettiğiniz cihazlarda gerçekleştirilen eylemlerin durumunu görmek için **Cihaz eylemleri**’ni seçin.
