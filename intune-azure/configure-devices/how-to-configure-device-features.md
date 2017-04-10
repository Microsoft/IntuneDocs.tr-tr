---
title: "Intune cihaz özelliği ayarlarını yapılandırma"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Yönettiğiniz cihazlarda özellikleri yapılandırmak için Intune’u kullanmayı öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: ca4f1adc5704ecd66d2af7823f95ca63ec20469e
ms.openlocfilehash: dd53e547a8f834eff528e79cf2506be1e6c2dc2a
ms.lasthandoff: 03/17/2017


---

# <a name="how-to-configure-device-feature-settings-in-microsoft-intune"></a>Microsoft Intune’da cihaz özelliği ayarlarını yapılandırma

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Cihaz kısıtlamaları, iOS ve macOS cihazlarda AirPrint, bildirimler ve paylaşılan cihaz yapılandırmaları gibi özellikleri denetlemenize olanak tanır.

Bu konu başlığı altında verilen bilgileri kullanarak cihaz özelliği profillerini yapılandırmanın temellerini öğrenin ve sonra cihaza özgü bilgiler için her platformla ilgili olarak sağlanan konuları okuyun.

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>Cihaz kısıtlama ayarlarını içeren bir cihaz profili oluşturma

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **Diğer** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihaz yapılandırması**’nı seçin.
2. **Cihaz Yapılandırması** dikey penceresinde **Yönet** > **Profiller**’i seçin.
3. Profiller dikey penceresinde **Profil Oluştur**’u seçin.
4. **Profil Oluştur** dikey penceresinde, cihaz özellikleri profili için **Ad** ve **Açıklama** girin.
5. **Platform** açılan listesinden, ayarları uygulamak istediğiniz cihaz platformunu seçin. Şu anda, cihaz özellikleri için aşağıdaki platformlardan birini seçebilirsiniz:
    - **Android**
    - **macOS**
6. **Profil türü** açılan listesinden **Cihaz özellikleri**’ni seçin. 
7. Seçtiğiniz platforma bağlı olarak , yapılandırabileceğiniz ayarlar farklılık gösterir. Her platformun ayrıntılı ayarları için aşağıdaki konulardan birine gidin:
    - [iOS ayarları](device-features-for-ios.md)
    - [macOS ayarları](device-features-for-macos.md)

8. Bitirdiğinizde, **Profil Oluştur** dikey penceresine gidin ve **Oluştur**’a basın.

Profil oluşturulur ve profil listesi dikey penceresinde görüntülenir.
Devam edip bu profili gruplara atamak isterseniz, bkz. [Cihaz profillerini atama](how-to-assign-device-profiles.md).




