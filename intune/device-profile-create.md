---
title: "Intune cihaz yapılandırma profillerini oluşturma | Intune Azure önizlemesi"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Intune cihaz yapılandırma profillerini oluşturmayı öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: a719b3f53076a55f1e888a9ddf8e98c7074dd25f
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---

# <a name="how-to-create-device-configuration-profiles-in-microsoft-intune"></a>Microsoft Intune’da cihaz yapılandırma profilleri oluşturma

[!INCLUDE[azure_preview](./includes/azure_preview.md)]


1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihazları yapılandır**’ı seçin.
2. **Cihaz Yapılandırması** dikey penceresinde **Yönet** > **Profiller**’i seçin.
2. Profil listesinin gösterildiği dikey pencerede **Profil Oluştur**’u seçin.
3. **Profil Oluştur** dikey penceresinde aşağıdakileri belirtin:
    - **Ad** - Yeni profil için açıklayıcı bir ad girin.
    - **Açıklama** -  Profil için isteğe bağlı bir açıklama girin.
    - **Platform** -  Oluşturmak istediğiniz profilin platform türünü seçin.
    - **Profil türü** - Oluşturmak istediğiniz profil türünü seçin. Kullanılabilir türler listesi, seçtiğiniz platforma göre değişiklik gösterir.
    - **Ayarlar** - Her profil türünün ayarları hakkında bilgi için, aşağıdaki konu başlıklarını seçin:
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

    ![Cihaz profilini oluşturma](./media/create-device-profile.png)
4. Ayarları yapılandırmayı bitirdikten sonra, **Profil Oluştur** dikey penceresinde **Oluştur**’u seçin.

Profil oluşturulur ve profil listesi dikey penceresinde görüntülenir.
Devam edip bu profili gruplara atamak isterseniz, bkz. [Cihaz profillerini atama](device-profile-assign.md).


### <a name="next-steps"></a>Sonraki adımlar
Cihaz profillerini atama hakkında bilgi için bkz. [Microsoft Intune ile cihaz profillerini atama](device-profile-assign.md).

