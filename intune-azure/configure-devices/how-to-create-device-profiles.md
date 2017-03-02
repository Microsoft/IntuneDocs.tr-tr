---
title: "Intune cihaz yapılandırma profillerini oluşturma | Intune Azure önizlemesi | Microsoft Docs"
description: "Intune Azure önizlemesi: Intune cihaz yapılandırma profillerini oluşturmayı öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: 908169c47d9eaa583c775c8ed06acea233040e50
ms.lasthandoff: 02/16/2017


---

# <a name="how-to-create-device-configuration-profiles-in-microsoft-intune"></a>Microsoft Intune’da cihaz yapılandırma profilleri oluşturma

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


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
        -  [Cihaz kısıtlama ayarları](/intune-azure/configure-devices/how-to-configure-device-restrictions)
        -  [E-posta ayarları](/intune-azure/configure-devices/how-to-configure-email-settings)
        -  [VPN ayarları](/intune-azure/configure-devices/how-to-configure-vpn-settings)
        -  [Wi-Fi ayarları](/intune-azure/configure-devices/how-to-configure-wi-fi-settings)
        -  [Windows 10 sürüm yükseltme ayarları](/intune-azure/configure-devices/how-to-configure-windows-10-edition-upgrade)
        -  [Sertifika ayarları](/intune-azure/configure-devices/how-to-configure-certificates)
        -  [Windows Bilgi Koruması ayarları](/intune-azure/configure-devices/how-to-configure-windows-information-protection)
        -  [Eğitim ayarları](/intune-azure/configure-devices/education-settings-for-ios.md)
        -  [Özel ayarlar](/intune-azure/configure-devices/how-to-configure-custom-settings)

    ![Cihaz profilini oluşturma](./media/create-device-profile.png)
4. Ayarları yapılandırmayı bitirdikten sonra, **Profil Oluştur** dikey penceresinde **Oluştur**’u seçin.

Profil oluşturulur ve profil listesi dikey penceresinde görüntülenir.
Devam edip bu profili gruplara atamak isterseniz, bkz. [Cihaz profillerini atama](how-to-assign-device-profiles.md).


### <a name="next-steps"></a>Sonraki adımlar
Cihaz profillerini atama hakkında bilgi için bkz. [Microsoft Intune ile cihaz profillerini atama](/intune-azure/configure-devices/how-to-assign-device-profiles).

