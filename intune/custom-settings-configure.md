---
title: "Microsoft Intune - Azure'da özel cihaz ayarlarını kullanma | Microsoft Docs"
description: "Microsoft Intune kullanarak Windows, Android ve iOS cihazlarına yönelik özel ayarları kullanmak için profil ekleme veya oluşturma"
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: adecb332c91f17cf92362295b6b0c81445f5acaf
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2018
---
# <a name="create-a-profile-with-custom-settings-in-intune"></a>Intune'da özel ayarlarla profil oluşturma

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune size gereken veya istediğiniz yerleşik ayarların hepsini içermeyebilir. Öte yandan başka cihaz profillerinde sağlanan bir ayarı kullanmak da isteyebilirsiniz. Bu ayarları eklemek için, bir cihaz profili oluşturun ve bu profili özel cihaz ayarlarıyla yapılandırın.

Bu makalede, özel ayarlarla profil oluşturma işleminin temel adımları listelenir. Ayrıca, farklı platformlarda özel ayarlar oluşturma konusunun ayrıntılarını içeren bağlantılar da verilir.

## <a name="custom-settings-on-different-platforms"></a>Farklı platformlarda özel ayarlar
Özel ayarlar her platform için ayrı yapılandırılır. Örneğin Android ve Windows cihazlarındaki özellikleri denetlemek için, Open Mobile Alliance Tekdüzen Kaynak Tanımlayıcısı (OMA-URI) değerleri girebilirsiniz. Apple cihazları için, [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)’la oluşturduğunuz bir dosyayı içeri aktarabilirsiniz.

## <a name="create-the-profile"></a>Profili oluşturma

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
3. **Cihaz yapılandırması**’nı seçin, **Profiller**’i seçin ve ardından **Profil oluştur**’u seçin.
4. Özel profil için **Ad** ve **Açıklama** girin.
5. **Platform** açılan listesinden, özel ayarların uygulanacağı cihaz platformunu seçin. Aşağıdaki platformlardan birini seçebilirsiniz:

    - **Android**
    - **Android for Work**
    - **Android**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 ve üzeri**
    - **Windows 10 ve üzeri**

6. **Profil** türü açılan listesinden **Özel**’i seçin.
7. Seçtiğiniz platforma bağlı olarak, yapılandırabileceğiniz ayarlar farklılık gösterir. Aşağıdaki bağlantılarda, her platformun özel ayarlarıyla ilgili daha fazla ayrıntı sağlanır:

    - [Android ayarları](custom-settings-android.md)
    - [iOS ayarları](custom-settings-ios.md)
    - [macOS ayarları](custom-settings-macos.md)
    - [Windows Phone 8.1 ayarları](custom-settings-windows-phone-8-1.md)
    - [Windows 10 ayarları](custom-settings-windows-10.md)
    - [Windows Holographic for Business ayarları](custom-settings-windows-holographic.md)
    - [Android for Work ayarları](custom-settings-android-for-work.md)

8. İşiniz bittiğinde **Oluştur**’u seçin.

Profil oluşturulur ve profil listesinde görüntülenir. Bu profili gruplara atamak için bkz. [Cihaz profillerini atama](device-profile-assign.md).
