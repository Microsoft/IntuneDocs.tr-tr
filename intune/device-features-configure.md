---
title: "Microsoft Intune cihaz özellik ayarlarını yapılandırma"
titleSuffix: 
description: "Microsoft Intune’u yönettiğiniz cihazlarda özellik yapılandırmak için kullanmayı öğrenin."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/2/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6cd646976deb1599c4cbc9154b6f2a487029dd79
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2018
---
#<a name="configure-device-feature-settings-in-microsoft-intune"></a>Microsoft Intune’da cihaz özelliği ayarlarını yapılandırma

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Cihaz özellikleri, iOS ve macOS cihazlarda AirPrint, bildirimler ve paylaşılan cihaz yapılandırmaları gibi özellikleri denetlemenize olanak tanır.

Bu makalede verilen bilgileri kullanarak cihaz özelliği profillerini yapılandırmanın temellerini öğrenin ve sonra cihaza özgü bilgiler için her platformla ilgili olarak sağlanan ek makaleleri okuyun.

## <a name="create-a-device-profile-containing-device-feature-settings"></a>Cihaz özelliği ayarlarını içeren bir cihaz profili oluşturma

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** sayfasında, **Cihaz yapılandırması**’nı seçin.
2. **Yönet** bölümü altındaki **Cihaz yapılandırması** sayfasından **Profiler**’i seçin.
3. Profiller sayfasında **Profil oluştur**’u seçin.
4. **Profil oluştur** sayfasında, cihaz özellikleri profili için **Ad** ve **Açıklama** girin.
5. **Platform** açılan listesinden, ayarları uygulamak istediğiniz cihaz platformunu seçin. Şu anda, cihaz özellikleri için aşağıdaki platformlardan birini seçebilirsiniz:
    - **iOS**
    - **macOS**
6. **Profil türü** açılan listesinden **Cihaz özellikleri**’ni seçin. 
7. Seçtiğiniz platforma bağlı olarak, yapılandırabileceğiniz ayarlar farklılık gösterir. Her platformun ayrıntılı ayarları için aşağıdaki makalelerden birine gidin:
    - [iOS ve MacOS cihazları için AirPrint ayarları](air-print-settings-ios-macos.md)
    - [iOS için AirPlay ayarları](airplay-settings-ios.md)
    - [iOS için Giriş ekranı düzen ayarları](home-screen-settings-ios.md)
    - [iOS için uygulama bildirimi ayarları](app-notification-settings-ios.md)
    - [iOS için paylaşılan cihaz yapılandırma ayarları](shared-device-settings-ios.md)
    - [Intune'u iOS cihazında Çoklu Oturum Açma için](sso-ios.md) yapılandırma
    - [iOS için web içerik filtresi ayarları](web-content-filter-settings-ios.md)

8. İşiniz bittiğinde **Tamam**’ı seçin, **Profil oluştur** sayfasına dönün ve **Oluştur**'u seçin.

Profil oluşturulur ve profil listesi sayfasında görüntülenir.
## <a name="next-steps"></a>Sonraki adımlar

Bu profili gruplara atamak isterseniz bkz. [Cihaz profillerini atama](device-profile-assign.md).



