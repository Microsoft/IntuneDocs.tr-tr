---
title: "Microsoft Intune - Azure’da cihaz profilleri oluşturma | Microsoft Docs"
description: "Platform türünü seçme ve Azure portalı içindeki ayarları yapılandırma da dahil olmak üzere Microsoft Intune'da bir cihaz profili ekleme veya yapılandırma"
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/01/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e4e1febb5f12de038d2ddd543be883f71ef79005
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2018
---
# <a name="create-a-device-profile-in-microsoft-intune"></a>Microsoft Intune’da cihaz profili oluşturma

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="create-the-profile"></a>Profili oluşturma
1. [Azure portalında](https://portal.azure.com), **Tüm Hizmetler**’i seçin ve **Microsoft Intune** araması yapın.

2. **Microsoft Intune**’da, **Cihaz yapılandırması**’nı seçin, **Profiller**’i seçin ve ardından **Profil Oluştur**’u seçin.

3. Aşağıdaki özellikleri girin:

    - **Ad**: Yeni profil için açıklayıcı bir ad girin
    - **Açıklama**: İsteğe bağlıdır ancak önerilir. Profil için bir açıklama girin.
    - **Platform**: Platform türünü seçin:  

        - **Android**
        - **Android for Work**
        - **Android**
        - **macOS**
        - **Windows Phone 8.1**
        - **Windows 8.1 ve üzeri**
        - **Windows 10 ve üzeri**

    - **Profil türü**: Oluşturmak istediğiniz türü seçin. Liste, seçtiğiniz platforma bağlıdır.
    - **Ayarlar**: Aşağıdaki konu başlıkları her profil türü için ayarları açıklar:

        -  [Cihaz özelliği ayarları](device-features-configure.md)
        -  [Cihaz kısıtlama ayarları](device-restrictions-configure.md)
        -  [E-posta ayarları](email-settings-configure.md)
        -  [VPN ayarları](vpn-settings-configure.md)
        -  [Wi-Fi ayarları](wi-fi-settings-configure.md)
        -  [Windows 10 sürüm yükseltme ayarları](edition-upgrade-configure-windows-10.md)
        -  [Sertifika ayarları](certificates-configure.md)
        -  [Windows Bilgi Koruması ayarları](windows-information-protection-configure.md)
        -  [Eğitim ayarları](education-settings-configure.md)
        -  [Özel ayarlar](custom-settings-configure.md)

    ![Bir cihaz profili oluşturmak için ayarları girin](./media/create-device-profile.png)

4. Bitince **Oluştur**’u seçin.

Profil oluşturulur ve listede görüntülenir. Bu profili gruplara atamak için bkz. [Cihaz profillerini atama](device-profile-assign.md).


## <a name="next-steps"></a>Sonraki adımlar
Cihaz profillerini atamak için bkz. [Microsoft Intune ile cihaz profillerini atama](device-profile-assign.md).
