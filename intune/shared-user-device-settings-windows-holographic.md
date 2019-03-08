---
title: Windows Holographic iş paylaşılan cihaz ayarları - Microsoft Intune - Azure | Microsoft Docs
description: Ekleyebilir ve Windows Holographic for Business, paylaşılan veya Microsoft Intune birden çok kullanıcı tarafından kullanılan cihazları yapılandırmak için kullanabilirsiniz. Hesap yönetimi ayarları ve Microsoft HoloLens de dahil olmak üzere cihazlarda ne bakın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/09/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 151ceaa40f2993d3160b9de34eee92e53c35925d
ms.sourcegitcommit: 9a4c5b6c2ce511edaeace25426a23f180cb71e15
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/07/2019
ms.locfileid: "57565868"
---
# <a name="windows-holographic-for-business-settings-to-manage-shared-devices-using-intune"></a>Windows Holographic for Business paylaşılan cihazları Intune kullanarak yönetmek için ayarlar

Windows Holographic for Business cihazlar, Microsoft HoloLens gibi birden çok kullanıcı tarafından kullanılabilir. Birden çok kullanıcıya sahip cihazlar, paylaşılan cihazlar olarak adlandırılır ve bir mobil cihaz Yönetimi (MDM) çözümleri parçasıdır.

Microsoft Intune kullanarak, kullanıcılar paylaşılan bu cihazlara bir konuk hesabıyla oturum açabilir. Cihaz kullandıkları gibi bunlar yalnızca izin özellikleri erişim elde edin.

Bu makalede, listeler ve bir Windows Holographic for Business cihaz yapılandırma profili kullanmak ayarları açıklanır. Intune'da profili oluşturduğunuzda, ardından dağıtın veya profili, kuruluşunuzdaki cihaz gruplarına atayabilirsiniz. Bir cihaz grubuna karma cihaz türleri ve işletim sistemi sürümleri ile bu profil atayabilirsiniz.

Intune bu özellik hakkında daha fazla bilgi için bkz. [denetim erişimi, hesapları ve paylaşılan bir bilgisayar veya birden çok kullanıcı cihazlarda güç özellikleri](shared-user-device-settings.md). Windows CSP hakkında daha fazla bilgi için bkz. [hesap yönetimi CSP](https://docs.microsoft.com/windows/client-management/mdm/accountmanagement-csp).

## <a name="before-your-begin"></a>Önce başlangıç

[Profil oluşturma](shared-user-device-settings.md).

## <a name="shared-multi-user-device-settings"></a>Paylaşılan birden çok kullanıcı cihaz ayarları

> [!NOTE]
> Yalnızca Microsoft HoloLens de dahil olmak üzere, Windows Holographic for Business çalıştıran cihazları destekler **hesap yönetimi** ayarları. Intune ile gösterilen diğer ayarlardan herhangi birini yapılandırırsanız dahil olmak üzere **paylaşılan bilgisayar modu**, bu cihazlar üzerinde hiçbir etkisi yoktur.

- **Hesap Yönetimi**: Kümesine **etkinleştirme** AD ve Azure AD yerel hesaplar konuklar tarafından oluşturulan ve hesapları otomatik olarak silmek için. Bu hesaplar, kullanıcı cihazı kapatıp açtığında veya Sistem Bakımı çalıştığında silinir. Etkin olduğunda, ayrıca ayarlayın:
  - **Hesap silme**: Hesapları ne zaman silineceğini seçin: **Depolama alanı eşik adresindeki**, **depolama alanı eşiği ve etkin olmayan eşik**, veya **hemen sonra oturumu kapatın**. Şunları da girin:
    - **Başlangıç Sil threshold(%)**: Disk alanının yüzdesi (0-100) girin. Toplam disk depolama alanı girdiğiniz değerin altına düştüğünde, önbelleğe alınan hesapları da silinir. Sürekli olarak disk alanını boşaltmak için hesapları da silinir. Tanımladığımız etkin olmayan hesaplar önce silinir.
    - **Delete threshold(%) Durdur**: Disk alanının yüzdesi (0-100) girin. Toplam disk depolama alanı girdiğiniz değer karşıladığında silme durdurur.

  Kümesine **devre dışı** yerel AD, tutmak ve konuklar tarafından oluşturulan Azure AD hesapları.

  > [!NOTE]
  > Microsoft HoloLens cihazları yalnızca Destek **hesap yönetimi** ayarları.

## <a name="next-steps"></a>Sonraki adımlar

- [Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).
- Ayarlarını görmek [Windows 10 ve üzeri sürümlerde](shared-user-device-settings-windows.md).
