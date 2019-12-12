---
title: Windows holographic Iş paylaşılan cihaz ayarları-Microsoft Intune-Azure | Microsoft Docs
description: Paylaşılan veya Microsoft Intune birden çok kullanıcı tarafından kullanılan cihazları yapılandırmak için Windows holographic for Business ekleyin ve kullanın. Microsoft HoloLens dahil olmak üzere hesap yönetimi ayarlarının listesini ve cihazlarda ne yaptığını görün.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/09/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: f9c89712539d4e5bd78cc317af2af396f8ca7006
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72492228"
---
# <a name="windows-holographic-for-business-settings-to-manage-shared-devices-using-intune"></a>Intune kullanarak paylaşılan cihazları yönetmek için Windows holographic for Business ayarları

Microsoft HoloLens gibi Windows holographic for Business cihazları birden çok kullanıcı tarafından kullanılabilir. Birden çok kullanıcısı olan cihazlara paylaşılan cihaz denir ve mobil cihaz yönetimi (MDM) çözümlerinin bir parçasıdır.

Microsoft Intune kullanarak, kullanıcılar bu paylaşılan cihazlarda Konuk hesabıyla oturum açabilirler. Cihaz kullandıkları için, yalnızca izin verilen özelliklere erişim sağlar.

Bu makalede, bir Windows holographic for Business cihaz yapılandırma profilinde kullandığınız ayarlar listelenir ve açıklanmaktadır. Profil Intune 'da oluşturulduğunda, profili dağıtırsınız veya kuruluşunuzdaki cihaz gruplarına atarsınız. Ayrıca, bu profili karma cihaz türleri ve işletim sistemi sürümleri ile bir cihaz grubuna da atayabilirsiniz.

Intune 'da bu özellik hakkında daha fazla bilgi için bkz. [PAYLAŞıLAN bilgisayar veya birden çok Kullanıcı cihazlarındaki erişimi, hesapları ve güç özelliklerini denetleme](shared-user-device-settings.md). Windows CSP hakkında daha fazla bilgi için bkz. [AccountManagement CSP](https://docs.microsoft.com/windows/client-management/mdm/accountmanagement-csp).

## <a name="before-your-begin"></a>Başlamadan önce

[Profili oluşturun](shared-user-device-settings.md).

## <a name="shared-multi-user-device-settings"></a>Paylaşılan çok kullanıcılı cihaz ayarları

> [!NOTE]
> Microsoft HoloLens de dahil olmak üzere Windows holographic for Business çalıştıran cihazlar yalnızca **Hesap yönetimi** ayarlarını destekler. Intune 'da gösterilen, **PAYLAŞıLAN bilgisayar modu**dahil diğer ayarlardan herhangi birini yapılandırırsanız, bu cihazlar üzerinde hiçbir etkisi olmaz.

- **Hesap yönetimi**: konuklar tarafından oluşturulan yerel hesapları ve ad ve Azure AD hesaplarını otomatik olarak silmek için **etkinleştirin** . Kullanıcı cihazda oturumu kapattığında veya sistem bakımı çalıştırıldığında, bu hesaplar silinir. Etkinleştirildiğinde, aşağıdakileri de ayarlayın:
  - **Hesap silme**: hesapların ne zaman silineceğini seçin: **depolama alanı eşiğine**, **depolama alanı eşiğine ve etkin olmayan eşiğe**veya **oturum kapatıldıktan hemen sonra**. Ayrıca şunu girin:
    - **Delete eşiğini Başlat (%)** : disk alanı yüzdesi (0-100) girin. Toplam disk/depolama alanı girdiğiniz değerin altına düştüğünde, önbelleğe alınmış hesaplar silinir. Disk alanı kazanmak için hesapları sürekli olarak siler. En uzun devre dışı olan hesaplar önce silinir.
    - **Silme eşiğini Durdur (%)** : disk alanı yüzdesi (0-100) girin. Toplam disk/depolama alanı girdiğiniz değeri karşılıyorsa, silme işlemini sonlandırır.

  Konuklar tarafından oluşturulan yerel, AD ve Azure AD hesaplarını tutmak için **devre dışı** olarak ayarlayın.

  > [!NOTE]
  > Microsoft HoloLens cihazları yalnızca **Hesap yönetimi** ayarlarını destekler.

## <a name="next-steps"></a>Sonraki adımlar

- [Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).
- Bkz. [Windows 10 ve üzeri](shared-user-device-settings-windows.md)için ayarlar.
