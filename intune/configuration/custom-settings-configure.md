---
title: Microsoft Intune - Azure'da özel cihaz ayarlarını kullanma | Microsoft Docs
description: Microsoft Intune kullanarak Windows Phone, Windows 8.1, Windows 10 ve üzeri, Android, Android Enterprise, macOS ve iOS/ıpados cihazları için özel ayarları kullanmak üzere bir profil ekleyin veya oluşturun
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/18/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d2ca5a120e50819208743564279a5d16c6b4aa2f
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77511523"
---
# <a name="create-a-profile-with-custom-settings-in-intune"></a>Intune'da özel ayarlarla profil oluşturma

## <a name="what-are-custom-profiles"></a>Özel profil nedir?

Microsoft Intune, bir cihazdaki farklı özellikleri denetlemek için pek çok yerleşik ayar içerir. Ayrıca özel profiller de oluşturabilirsiniz. Özel profiller, Intune’da yerleşik olarak bulunmayan cihaz ayarları ve özelliklerini kullanabilmenizi sağlar. Bu profiller, kuruluşunuzdaki cihazlarda denetleyebileceğiniz bazı özellik ve ayarlar içerir. Örneğin, her iOS/ıpados cihazı için aynı özelliği ayarlayan özel bir profil oluşturabilirsiniz.

Yapılandırma profilleri hakkında daha fazla bilgi için bkz. [Microsoft Intune cihaz profili nedir?](device-profiles.md). 

Bu makalede, Android, Android Enterprise, iOS/ıpados, macOS ve Windows için özel profiller oluşturma bağlantıları yer alır.

## <a name="available-platforms"></a>Kullanılabilir platformlar

Özel ayarlar her platform için ayrı yapılandırılır. Örneğin Android ve Windows cihazlarındaki özellikleri denetlemek için, Open Mobile Alliance Tekdüzen Kaynak Tanımlayıcısı (OMA-URI) değerleri girebilirsiniz. Apple cihazlar için [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) veya [Apple Profile Manager](https://support.apple.com/profile-manager) ile oluşturduğunuz bir dosyayı içeri aktarabilirsiniz.

Özel profiller, yerleşik profillere benzer şekilde oluşturulur ve aşağıdaki platformlarda kullanılabilir:

- [Android](../custom-settings-android.md)
- [Android Kurumsal](../custom-settings-android-for-work.md)
- [iOS/ıpados](custom-settings-ios.md)
- [macOS](custom-settings-macos.md)
- [Windows 10](custom-settings-windows-10.md)
- [Windows Holographic for Business](custom-settings-windows-holographic.md)
- [Windows Phone 8.1](custom-settings-windows-phone-8-1.md)

## <a name="next-steps"></a>Sonraki adımlar

Platformunuzu seçin ve kullanmaya başlayın:

- [Android](../custom-settings-android.md)
- [Android Kurumsal](../custom-settings-android-for-work.md)
- [iOS/ıpados](custom-settings-ios.md)
- [macOS](custom-settings-macos.md)
- [Windows 10](custom-settings-windows-10.md)
- [Windows Holographic for Business](custom-settings-windows-holographic.md)
- [Windows Phone 8.1](custom-settings-windows-phone-8-1.md)
