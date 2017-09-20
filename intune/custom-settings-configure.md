---
title: "Intune özel cihaz ayarlarını yapılandırma"
titleSuffix: Azure portal
description: "Intune'u, yönettiğiniz cihazlarda özel ayar yapılandırmak için kullanmayı öğrenin.\""
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 607b517ae65309c2d01fa0d173e513c029a6869d
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/15/2017
---
# <a name="how-to-configure-custom-device-settings-in-microsoft-intune"></a>Microsoft Intune’da özel cihaz ayarlarını yapılandırma

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="when-to-use-custom-settings"></a>Özel ayarlar ne zaman kullanılır

Yapılandırmak istediğiniz ayarlar Intune’da yerleşik olarak bulunmadığında ve diğer cihaz profillerinden sağlanmadığında, özel cihaz ayarları yararlı olabilir.
Özel ayarlar her platform için ayrı yapılandırılır. Örneğin Android ve Windows cihazlarıyla, cihazlardaki özellikleri denetlemek için Open Mobile Alliance Uniform Resource Identifier (OMA-URI) değerleri belirtebilirsiniz. Apple cihazları için, [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)’la oluşturduğunuz bir dosyayı içeri aktarabilirsiniz.

Bu konu başlığı altında verilen bilgileri kullanarak profilleri özel ayarlarla yapılandırmanın temellerini öğrenin ve sonra cihaza özgü bilgiler için her platformla ilgili olarak sağlanan konuları okuyun.

## <a name="create-a-device-profile-containing-custom-settings"></a>Özel ayarlar içeren bir cihaz profili oluşturma

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihaz yapılandırması**’nı seçin.
2. **Cihaz Yapılandırması** dikey penceresinde **Yönet** > **Profiller**’i seçin.
3. Profiller dikey penceresinde **Profil Oluştur**’u seçin.
4. **Profil Oluştur** dikey penceresinde, özel profil için **Ad** ve **Açıklama** girin.
5. **Platform** açılan listesinden, özel ayarları uygulamak istediğiniz cihaz platformunu seçin. Şu anda, özel cihaz ayarları için aşağıdaki platformlardan birini seçebilirsiniz:
    - **Outlook Web Access (OWA)**
    - **Android**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 10 ve üzeri**
6. **Profil** türü açılan listesinden **Özel**’i seçin.
7. Seçtiğiniz platforma bağlı olarak, yapılandırabileceğiniz ayarlar farklılık gösterir. Her platformun ayrıntılı ayarları için aşağıdaki konulardan birine gidin:
    - [Android ayarları](custom-settings-android.md)
    - [iOS ayarları](custom-settings-ios.md)
    - [macOS ayarları](custom-settings-macos.md)
    - [Windows Phone 8.1 ayarları](custom-settings-windows-phone-8-1.md)
    - [Windows 10 ayarları](custom-settings-windows-10.md)
    - [Android for Work ayarları](custom-settings-android-for-work.md)
8. Bitirdiğinizde **Profil Oluştur** dikey penceresine dönün ve **Oluştur**’a basın.

Profil oluşturulur ve profil listesi dikey penceresinde görüntülenir.
Devam edip bu profili gruplara atamak isterseniz, bkz. [Cihaz profillerini atama](device-profile-assign.md).
