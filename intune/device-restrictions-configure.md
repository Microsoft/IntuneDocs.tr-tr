---
title: "Intune cihaz kısıtlama ayarlarını yapılandırma"
titleSuffix: Azure portal
description: "Intune’u, yönettiğiniz cihazlarda ayar ve özellikleri yapılandırmak için kullanmayı öğrenin.\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 552e098438e7515c1a4b82a0a8dcb941c69ac81e
ms.sourcegitcommit: 3b397b1dcb780e2f82a3d8fba693773f1a9fcde1
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/12/2017
---
# <a name="how-to-configure-device-restriction-settings-in-microsoft-intune"></a>Microsoft Intune’da cihaz kısıtlama ayarlarını yapılandırma

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Cihaz kısıtlamaları; güvenlik, tarayıcı, donanım ve veri paylaşım ayarları gibi bir dizi kategori altında yönettiğiniz çok çeşitli ayarları ve özellikleri denetlemenize olanak tanır. Örneğin, iOS cihazı kullanıcılarının cihaz kamerasına erişmesini engelleyen bir cihaz kısıtlama profili oluşturabilirsiniz.

Bu konu başlığı altında verilen bilgileri kullanarak cihaz kısıtlama profillerini yapılandırmanın temellerini öğrenin ve sonra cihaza özgü bilgiler için her platformla ilgili olarak sağlanan konuları okuyun.

Cihaz kısıtlama ayarlarını içeren bir cihaz profili oluşturmak için:

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihazları yapılandır**’ı seçin.
2. **Cihaz Yapılandırması** dikey penceresinde **Yönet** > **Profiller**’i seçin.
3. Profiller dikey penceresinde **Profil Oluştur**’u seçin.
4. **Profil Oluştur** dikey penceresinde, cihaz kısıtlama profili için **Ad** ve **Açıklama** girin.
5. **Platform** açılan listesinden, özel ayarları uygulamak istediğiniz cihaz platformunu seçin. Şu anda, cihaz kısıtlama ayarları için aşağıdaki platformlardan birini seçebilirsiniz:
    - **Outlook Web Access (OWA)**
    - **Android**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 ve üzeri**
    - **Windows 10 ve üzeri**
6. **Profil türü** açılan listesinden **Cihaz kısıtlamaları**’nı seçin. Surface Hub gibi Windows 10 Team cihazları için cihaz kısıtlama profili oluşturuyorsanız, **Cihaz kısıtlamaları (Windows 10 Team)** öğesini seçin.
7. Seçtiğiniz platforma bağlı olarak, yapılandırabileceğiniz ayarlar farklılık gösterir. Her platformun ayrıntılı ayarları için aşağıdaki konulardan birine gidin:
    - [Android ayarları](device-restrictions-android.md)
    - [iOS ayarları](device-restrictions-ios.md)
    - [macOS ayarları](device-restrictions-macos.md)
    - [Windows Phone 8.1 ayarları](device-restrictions-windows-phone-8-1.md)
    - [Windows 8.1](device-restrictions-windows-8-1.md)
    - [Windows 10 ayarları](device-restrictions-windows-10.md)
    - [Windows 10 Team ayarları](device-restrictions-windows-10-teams.md)
    - [Android for Work ayarları](device-restrictions-android-for-work.md)
8. Bitirdiğinizde **Profil Oluştur** dikey penceresine dönün ve **Oluştur**’a basın.

Profil oluşturulur ve profil listesi dikey penceresinde görüntülenir.
Devam edip bu profili gruplara atamak isterseniz, bkz. [Cihaz profillerini atama](device-profile-assign.md).

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/disable-android-camera.png)

-->