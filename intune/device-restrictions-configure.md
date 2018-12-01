---
title: Microsoft Intune - Azure’da cihaz kısıtlama ayarlarını yapılandırma | Microsoft Docs
description: Microsoft Intune’da Android, macOS, iOS, Windows Phone ve Windows 10 cihazlarda özellikleri kısıtlamak için bir cihaz profili ekleme
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/20/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 11b241a14ed70a2e999fa505449cd12cdd1e025e
ms.sourcegitcommit: ecd6aebe50b1440a282dfdda771e37fbb8750d42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2018
ms.locfileid: "52728795"
---
# <a name="configure-device-restriction-settings-in-microsoft-intune"></a>Microsoft Intune’da cihaz kısıtlama ayarlarını yapılandırma

Cihaz kısıtlamaları, bir dizi kategori altında yönettiğiniz çok çeşitli ayarları ve özellikleri denetlemenize olanak tanır, örneğin:
- Güvenlik
- Tarayıcı
- Donanım
- Veri paylaşımı ayarları

Örneğin, iOS cihazı kullanıcılarının cihaz kamerasına erişmesini engelleyen bir cihaz kısıtlama profili oluşturabilirsiniz.

Cihaz kısıtlama profili temel bilgilerini öğrenin ve cihazlara özgü özellikler hakkında bilgi edinmek için her platform için daha fazla makale okuyun.

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>Cihaz kısıtlama ayarlarını içeren bir cihaz profili oluşturma

1. İçinde için [Azure portalında](https://portal.azure.com)seçin **tüm hizmetleri** > Filtre **Intune** > seçin **Intune**.
2. **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**'u seçin.
3. Cihaz kısıtlama profili için bir **Ad** ve **Açıklama** girin.
4. **Platform** açılan listesinden, özel ayarları uygulamak istediğiniz cihaz platformunu seçin. Şu anda, cihaz kısıtlama ayarları için aşağıdaki platformlardan birini seçebilirsiniz:

    - **Android**
    - **Android kurumsal**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 ve üzeri**
    - **Windows 10 ve üzeri**

5. Açılan **Profil** türü listesinden **Cihaz kısıtlamaları**’nı seçin. Bir cihaz oluşturmak için kısıtlamaları profili Surface Hub gibi Windows 10 Team cihazlarının sonra seçin **cihaz kısıtlamaları (Windows 10 Team)**.
6. Seçtiğiniz platforma bağlı olarak, yapılandırabileceğiniz ayarlar farklılık gösterir. Platformunuzu seçin ayrıntılı ayarları:

    - [Android ayarları](device-restrictions-android.md)
    - [Android Kurumsal ayarları](device-restrictions-android-for-work.md)
    - [iOS ayarları](device-restrictions-ios.md)
    - [macOS ayarları](device-restrictions-macos.md)
    - [Windows Phone 8.1 ayarları](device-restrictions-windows-phone-8-1.md)
    - [Windows 8.1](device-restrictions-windows-8-1.md)
    - [Windows 10 ayarları](device-restrictions-windows-10.md)
    - [Windows 10 Team ayarları](device-restrictions-windows-10-teams.md)
    - [Windows Holographic for Business ayarları](device-restrictions-windows-holographic.md)

7. İşiniz bittiğinde, geri dönüp **profili oluşturma** sayfasında ve seçin **Oluştur**.

Profil oluşturulur ve profil listesi sayfasında görüntülenir. 

## <a name="next-step"></a>Sonraki adım

Profil oluşturulduktan sonra atanmak üzere hazırdır. Bkz: [cihaz profillerini atama](device-profile-assign.md) adımlar için. 

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/disable-android-camera.png)

-->
