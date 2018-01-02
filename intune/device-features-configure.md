---
title: "Intune cihaz özelliği ayarlarını yapılandırma"
titleSuffix: Azure portal
description: "Intune’u yönettiğiniz cihazlarda özellik yapılandırmak için kullanmayı öğrenin.\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/7/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ea280ac6858485aa4e3d64d11835f002c5bb35ca
ms.sourcegitcommit: 3b397b1dcb780e2f82a3d8fba693773f1a9fcde1
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/12/2017
---
# <a name="how-to-configure-device-feature-settings-in-microsoft-intune"></a>Microsoft Intune’da cihaz özelliği ayarlarını yapılandırma

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Cihaz kısıtlamaları, iOS ve macOS cihazlarda AirPrint, bildirimler ve paylaşılan cihaz yapılandırmaları gibi özellikleri denetlemenize olanak tanır.

Bu konu başlığı altında verilen bilgileri kullanarak cihaz özelliği profillerini yapılandırmanın temellerini öğrenin ve sonra cihaza özgü bilgiler için her platformla ilgili olarak sağlanan konuları okuyun.

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>Cihaz kısıtlama ayarlarını içeren bir cihaz profili oluşturma

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihaz yapılandırması**’nı seçin.
2. **Cihaz Yapılandırması** dikey penceresinde **Yönet** > **Profiller**’i seçin.
3. Profiller dikey penceresinde **Profil Oluştur**’u seçin.
4. **Profil Oluştur** dikey penceresinde, cihaz özellikleri profili için **Ad** ve **Açıklama** girin.
5. **Platform** açılan listesinden, ayarları uygulamak istediğiniz cihaz platformunu seçin. Şu anda, cihaz özellikleri için aşağıdaki platformlardan birini seçebilirsiniz:
    - **Android**
    - **macOS**
6. **Profil türü** açılan listesinden **Cihaz özellikleri**’ni seçin. 
7. Seçtiğiniz platforma bağlı olarak, yapılandırabileceğiniz ayarlar farklılık gösterir. Her platformun ayrıntılı ayarları için aşağıdaki konulardan birine gidin:
    - [iOS ve MacOS cihazları için AirPrint ayarları](air-print-settings-ios-macos.md)
    - [iOS için AirPlay ayarları](airplay-settings-ios.md)
    - [iOS için Giriş ekranı düzen ayarları](home-screen-settings-ios.md)
    - [iOS için uygulama bildirimi ayarları](app-notification-settings-ios.md)
    - [iOS için paylaşılan cihaz yapılandırma ayarları](shared-device-settings-ios.md)
    - [Intune'u iOS cihazında Çoklu Oturum Açma için](sso-ios.md) yapılandırma
    - [iOS için web içerik filtresi ayarları](web-content-filter-settings-ios.md)

8. Bitirdiğinizde **Profil Oluştur** dikey penceresine dönün ve **Oluştur**'a tıklayın.

Profil oluşturulur ve profil listesi dikey penceresinde görüntülenir.
Devam edip bu profili gruplara atamak isterseniz, bkz. [Cihaz profillerini atama](device-profile-assign.md).



