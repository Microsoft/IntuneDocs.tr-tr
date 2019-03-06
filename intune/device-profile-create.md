---
title: Microsoft Intune - Azure’da cihaz profilleri oluşturma | Microsoft Docs
description: Platform türünü seçme ve Azure portalı içindeki ayarları yapılandırma da dahil olmak üzere Microsoft Intune'da bir cihaz profili ekleyin ve yapılandırın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/18/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8d36f1c36656be6fab8a9566d34b946f80450e97
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57389484"
---
# <a name="create-a-device-profile-in-microsoft-intune"></a>Microsoft Intune’da cihaz profili oluşturma

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## <a name="create-the-profile"></a>Profili oluşturma

1. İçinde [Azure portalında](https://portal.azure.com)seçin **tüm hizmetleri** > Filtre **Intune** > seçin **Intune**.

2. **Cihaz yapılandırması** > **Profiller** > **Profil Oluştur**’u seçin.

3. Aşağıdaki özellikleri girin:

   - **Ad**: Yeni profil için açıklayıcı bir ad girin.
   - **Açıklama**: Profil için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
   - **Platform**: Platform türünü seçin:  

       - **Android**
       - **Android kurumsal**
       - **iOS**
       - **macOS**
       - **Windows Phone 8.1**
       - **Windows 8.1 ve üzeri**
       - **Windows 10 ve üzeri**

   - **Profil türü**: Oluşturmak istediğiniz türü seçin. Liste, seçtiğiniz platforma bağlıdır.
   - **Ayarları**: Aşağıdaki makaleler her profil türü için ayarları açıklar:

       -  [Cihaz özellikleri](device-features-configure.md)
       -  [Cihaz kısıtlamaları](device-restrictions-configure.md)
       -  [Uç nokta koruması](endpoint-protection-configure.md)
       -  [Kimlik koruması](identity-protection-configure.md)  
       -  [Bilgi noktası](kiosk-settings.md)
       -  [E-posta](email-settings-configure.md)
       -  [VPN](vpn-settings-configure.md)
       -  [Wi-Fi](wi-fi-settings-configure.md)
       -  [Windows 10](education-settings-configure.md) ve [iOS](wi-fi-settings-ios.md) için Eğitim
       -  [Windows 10 sürüm yükseltme](edition-upgrade-configure-windows-10.md)
       -  [iOS güncelleştirme ilkeleri](software-updates-ios.md)
       -  [Sertifikalar](certificates-configure.md)
       -  [Windows Bilgi Koruması](windows-information-protection-configure.md)
       -  [Özel](custom-settings-configure.md)

     ![Profil oluştur ekran görüntüsü](./media/create-device-profile.png)

4. Bitince **Oluştur**’u seçin.

Profil oluşturulur ve listede görüntülenir.

## <a name="next-steps"></a>Sonraki adımlar
[Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).
