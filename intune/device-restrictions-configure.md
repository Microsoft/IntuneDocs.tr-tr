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
ms.openlocfilehash: 7ab60e64927db5537a106c1257a5624670771f86
ms.sourcegitcommit: e08a26558174be3ea8f3d20646e577f1493ea21a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54831420"
---
# <a name="configure-device-restriction-settings-in-microsoft-intune"></a>Microsoft Intune’da cihaz kısıtlama ayarlarını yapılandırma

Cihaz kısıtlamaları, bir dizi kategori altında yönettiğiniz çok çeşitli ayarları ve özellikleri denetlemenize olanak tanır, örneğin:
- Güvenlik
- Tarayıcı
- Donanım
- Veri paylaşımı ayarları

Örneğin, iOS cihazı kullanıcılarının cihaz kamerasına erişmesini engelleyen bir cihaz kısıtlama profili oluşturabilirsiniz.

Cihaz kısıtlama profili temel bilgilerini öğrenin ve cihazlara özgü özellikler hakkında bilgi edinmek için her platform için daha fazla makale okuyun.

## <a name="create-the-profile"></a>Profili oluşturma

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
6. Seçtiğiniz platforma bağlı olarak, yapılandırabileceğiniz ayarlar farklılık gösterir. Ayrıntılı ayarları platformunuzu seçin:

    - [Android ayarları](device-restrictions-android.md)
    - [Android Kurumsal ayarları](device-restrictions-android-for-work.md)
    - [iOS ayarları](device-restrictions-ios.md)
    - [macOS ayarları](device-restrictions-macos.md)
    - [Windows Phone 8.1 ayarları](device-restrictions-windows-phone-8-1.md)
    - [Windows 8.1](device-restrictions-windows-8-1.md)
    - [Windows 10 ayarları](device-restrictions-windows-10.md)
    - [Windows 10 Team ayarları](device-restrictions-windows-10-teams.md)
    - [Windows Holographic for Business ayarları](device-restrictions-windows-holographic.md)

7. İşiniz bittiğinde **Tamam** > **Oluştur**’u seçerek değişikliklerinizi kaydedin.

Profil oluşturulur ve profil listesinde gösterilir.

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturulduktan sonra atanmak üzere hazırdır. Ardından, [profili atama](device-profile-assign.md) ve [atamanın durumunu izlemenize](device-profile-monitor.md).

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/disable-android-camera.png)

-->
