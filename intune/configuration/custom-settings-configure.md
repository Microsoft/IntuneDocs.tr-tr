---
title: Microsoft Intune - Azure'da özel cihaz ayarlarını kullanma | Microsoft Docs
description: Microsoft Intune kullanarak Windows Phone, Windows 8.1, Windows 10 ve üzeri, Android, Android Enterprise, macOS ve iOS cihazları için özel ayarları kullanmak üzere bir profil ekleyin veya oluşturun
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/23/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 87c35fdaddec591b57b9b7c28f94560ff52a93b0
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72506943"
---
# <a name="create-a-profile-with-custom-settings-in-intune"></a>Intune'da özel ayarlarla profil oluşturma

## <a name="what-are-custom-profiles"></a>Özel profil nedir?

Microsoft Intune, bir cihazdaki farklı özellikleri denetlemek için pek çok yerleşik ayar içerir. Ayrıca özel profiller de oluşturabilirsiniz. Özel profiller, Intune’da yerleşik olarak bulunmayan cihaz ayarları ve özelliklerini kullanabilmenizi sağlar. Bu profiller, kuruluşunuzdaki cihazlarda denetleyebileceğiniz bazı özellik ve ayarlar içerir. Örneğin tüm iOS cihazlar için aynı özelliği ayarlayan bir özel profil oluşturabilirsiniz.

Yapılandırma profilleri hakkında daha fazla bilgi için bkz. [Microsoft Intune cihaz profili nedir?](device-profiles.md). 

Bu makale; Android, Android Kurumsal, iOS, macOS ve Windows için özel profiller oluşturmaya yönelik bağlantılar içerir.

## <a name="available-platforms"></a>Kullanılabilir platformlar

Özel ayarlar her platform için ayrı yapılandırılır. Örneğin Android ve Windows cihazlarındaki özellikleri denetlemek için, Open Mobile Alliance Tekdüzen Kaynak Tanımlayıcısı (OMA-URI) değerleri girebilirsiniz. Apple cihazlar için [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) veya [Apple Profile Manager](https://support.apple.com/profile-manager) ile oluşturduğunuz bir dosyayı içeri aktarabilirsiniz.

Özel profiller, yerleşik profillere benzer şekilde oluşturulur ve aşağıdaki platformlarda kullanılabilir:

- [Outlook Web Access (OWA)](../custom-settings-android.md)
- [Android Kurumsal](../custom-settings-android-for-work.md)
- [iOS/ıpados](custom-settings-ios.md)
- [macOS](custom-settings-macos.md)
- [Windows 10](custom-settings-windows-10.md)
- [Windows Holographic for Business](custom-settings-windows-holographic.md)
- [Windows Phone 8.1](custom-settings-windows-phone-8-1.md)

## <a name="next-steps"></a>Sonraki adımlar

Platformunuzu seçin ve kullanmaya başlayın:

- [Outlook Web Access (OWA)](../custom-settings-android.md)
- [Android Kurumsal](../custom-settings-android-for-work.md)
- [iOS/ıpados](custom-settings-ios.md)
- [macOS](custom-settings-macos.md)
- [Windows 10](custom-settings-windows-10.md)
- [Windows Holographic for Business](custom-settings-windows-holographic.md)
- [Windows Phone 8.1](custom-settings-windows-phone-8-1.md)
