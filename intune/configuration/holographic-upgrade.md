---
title: Windows holographic for Business 'a yükseltme
titleSuffix: Microsoft Intune
description: Windows holographic çalıştıran cihazları Windows holographic for Business 'a nasıl uayarlayacağınızı öğrenin
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
ms.openlocfilehash: 6d569d34da1568d0e412d689d98d4a22b00e6545
ms.sourcegitcommit: 45d7c76e760c5117bf134fb57f7e248e5b6c4ad5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72314530"
---
# <a name="upgrade-devices-running-windows-holographic-to-windows-holographic-for-business"></a>Windows holographic çalıştıran cihazları Windows holographic for Business 'a yükseltme

Microsoft Intune cihazlarınızı yönetmenize ve korumanıza yardımcı olacak birçok ayar içerir. Bu makalede Windows holographic cihazlarını Windows holographic for Business 'a yükseltme ayarlarını listeler ve açıklanmaktadır. Bu ayarlar, Intune 'da gönderilen veya cihazlara dağıtılan bir yükseltme yapılandırma profilinde oluşturulur.

Mobil cihaz yönetimi (MDM) çözümünüzün bir parçası olarak, Windows holographic cihazlarınızı yükseltmek için bu ayarları kullanın. Microsoft HoloLens için, yükseltme için gerekli lisansı almak üzere ticari paketi satın alabilirsiniz. Daha fazla bilgi için bkz. [Windows holographic for Business özelliklerini açma](https://docs.microsoft.com/hololens/hololens1-upgrade-enterprise).

Bu özellik hakkında daha fazla bilgi için bkz. [Windows 10 sürümlerini yükseltme veya S modunu etkinleştirme](../edition-upgrade-configure-windows-10.md).

## <a name="before-you-begin"></a>Başlamadan önce

[Bir cihaz yapılandırma profili oluşturun](edition-upgrade-configure-windows-10.md#create-the-profile).

## <a name="edition-upgrade"></a>Sürüm yükseltme

- **Yükseltilecek sürüm**: **iş Için Windows 10 holographic**' u seçin.
- **Lisans dosyası**: sıze sunulan XML Lisans dosyasına gidin ve seçin.

  ![Holographic for Business lisans bilgilerini içeren XML dosya adını girin](./media/holographic-upgrade/Holographic-edition-upgrade.png)
 
## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturuldu, ancak henüz bir şey yapmamış olabilir. [Profili atadığınızdan](device-profile-assign.md)emin olun ve [durumunu izleyin](../device-profile-monitor.md).

Ayrıca, [Windows 10 ve üzeri](edition-upgrade-windows-settings.md) cihazlar için sürüm yükseltme profilleri de oluşturabilirsiniz.
