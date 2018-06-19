---
title: Microsoft Intune - Azure’da cihaz kısıtlama ayarlarını yapılandırma | Microsoft Docs
description: Microsoft Intune’da Android, macOS, iOS, Windows Phone ve Windows 10 cihazlarda özellikleri kısıtlamak için bir cihaz profili ekleme
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 13f93f9fcf813c2e86809d2cc20991d2fd635187
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31024626"
---
# <a name="configure-device-restriction-settings-in-microsoft-intune"></a>Microsoft Intune’da cihaz kısıtlama ayarlarını yapılandırma

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Cihaz kısıtlamaları, bir dizi kategori altında yönettiğiniz çok çeşitli ayarları ve özellikleri denetlemenize olanak tanır, örneğin:
- Güvenlik
- Tarayıcı
- Donanım
- Veri paylaşımı ayarları

Örneğin, iOS cihazı kullanıcılarının cihaz kamerasına erişmesini engelleyen bir cihaz kısıtlama profili oluşturabilirsiniz.

Cihaz kısıtlama profili temel bilgilerini öğrenin ve cihazlara özgü özellikler hakkında bilgi edinmek için her platform için daha fazla makale okuyun.

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>Cihaz kısıtlama ayarlarını içeren bir cihaz profili oluşturma

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
3. **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**'u seçin.
4. Cihaz kısıtlama profili için bir **Ad** ve **Açıklama** girin.
5. **Platform** açılan listesinden, özel ayarları uygulamak istediğiniz cihaz platformunu seçin. Şu anda, cihaz kısıtlama ayarları için aşağıdaki platformlardan birini seçebilirsiniz:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 ve üzeri**
    - **Windows 10 ve üzeri**
6. Açılan **Profil** türü listesinden **Cihaz kısıtlamaları**’nı seçin. Surface Hub gibi Windows 10 Team cihazları için cihaz kısıtlama profili oluşturuyorsanız, **Cihaz kısıtlamaları (Windows 10 Team)** öğesini seçin.
7. Seçtiğiniz platforma bağlı olarak, yapılandırabileceğiniz ayarlar farklılık gösterir. Her platformun ayrıntılı ayarları için aşağıdaki konulardan birine gidin:
    - [Android ayarları](device-restrictions-android.md)
    - [iOS ayarları](device-restrictions-ios.md)
    - [macOS ayarları](device-restrictions-macos.md)
    - [Windows Phone 8.1 ayarları](device-restrictions-windows-phone-8-1.md)
    - [Windows 8.1](device-restrictions-windows-8-1.md)
    - [Windows 10 ayarları](device-restrictions-windows-10.md)
    - [Windows 10 Team ayarları](device-restrictions-windows-10-teams.md)
    - [Windows Holographic for Business ayarları](device-restrictions-windows-holographic.md)
    - [Android for Work ayarları](device-restrictions-android-for-work.md)
8. Bitirdiğinizde **Profil oluştur** sayfasına dönün ve **Oluştur**'a tıklayın.

Profil oluşturulur ve profil listesi sayfasında görüntülenir.
Devam edip bu profili gruplara atamak isterseniz, bkz. [Cihaz profillerini atama](device-profile-assign.md).

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/disable-android-camera.png)

-->
