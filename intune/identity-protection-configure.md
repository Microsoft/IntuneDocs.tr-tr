---
title: Windows 10 cihazlarına Microsoft Intune - Azure kullanarak oturum açmak için PIN kullanma | Microsoft Docs
description: Windows iş için Hello bir PIN, parmak izi ve daha fazlasını kullanarak cihazlara oturum açmalarını sağlamak için kullanın. Intune Windows 10 cihazlar için şu ayarlarla bir kimlik koruma yapılandırma profili oluşturma ve kullanıcı grupları ve cihaz grupları için profil atayın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 843806681fcee4ddec175207c2c49d6db95e0f0d
ms.sourcegitcommit: e08a26558174be3ea8f3d20646e577f1493ea21a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54831400"
---
# <a name="use-windows-hello-for-business-on-windows-10-devices-with-microsoft-intune"></a>Windows Hello iş için Windows 10 cihazlarda Microsoft Intune ile kullanma

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Windows iş için Hello Windows cihazlar için parolaları, akıllı kartlar ve sanal akıllı kartları değiştirerek oturum açma yöntemidir. Yöneticiler, yapılandırma ve iş için Windows Hello'yu kullanma Intune yerleşik ayarlarını içerir. Örneğin, bu ayarlar için kullanabilirsiniz:

- Windows iş için Hello'yu cihazlar ve kullanıcılar için etkinleştir
- Bir minimum veya maksimum PIN uzunluğu'dahil olmak üzere, cihaz PIN gereksinimlerini ayarlama
- Kullanıcılar (veya kullanamazsınız) bir parmak izi gibi hareketler izin cihazlara oturum açmak için

Bu özellik şunları çalıştıran cihazlarda geçerlidir:

- Windows 10 ve üzeri
- Windows 10 Mobile
- Windows 10 Holographic for Business

Intune kullanır "yapılandırma profillerini" oluşturabilir ve kuruluşunuzun ihtiyaçları için bu ayarları özelleştirebilirsiniz. Bu özellikler bir profilde ekledikten sonra anında iletme veya kullanıcı ve cihaz grupları, kuruluşunuzda bu ayarları dağıtın.

Bu makalede bir cihaz yapılandırma profilinin nasıl oluşturulacağını gösterir. Tüm ayarların bir listesi ve ne yaptıkları için bkz. [Windows iş için Hello etkinleştirmek için Windows 10 cihaz ayarları](identity-protection-windows-settings.md).

## <a name="create-the-device-profile"></a>Cihaz profili oluşturma

1. İçinde [Azure portalında](https://portal.azure.com)seçin **tüm hizmetleri** > Filtre **Intune** > seçin **Intune**.
2. **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**'u seçin.
3. Aşağıdaki özellikleri girin:

    - **Ad**: Yeni profil için açıklayıcı bir ad girin.
    - **Açıklama**: Profil için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
    - **Platform**: Seçin **Windows 10 ve üzeri**. İş İçin Windows Hello, yalnızca Windows 10 ve üzeri çalıştıran cihazlarda desteklenir.
    - **Profil türü**: Seçin **kimlik koruması**.
    - **İş için Windows Hello yapılandırma**: Nasıl Windows iş için Hello yapılandırmak istediğinizi seçin. Seçenekleriniz şunlardır:

        - **Yapılandırılmamış**: [Sağlayan Windows iş için Hello](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-how-it-works-provisioning) cihazda. Kimlik koruma profillerini yalnızca kullanıcılara atarken cihaz bağlamı varsayılan olarak **Yapılandırılmadı** olur.
        - **Devre dışı bırakılmış**: İş için Windows Hello'yu kullanma istemiyorsanız bu seçeneği belirleyin. Bu seçenek Windows iş için Hello tüm kullanıcılar için devre dışı bırakır.
        - **Etkin**: Bu seçeneği [sağlama]((https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-how-it-works-provisioning))ve Windows Hello for Business ayarları ıntune yapılandırın. Yapılandırmak istediğiniz ayarları girin. Tüm ayarların bir listesi ve ne yaptıkları için bkz:

            - [Windows iş için Hello etkinleştirmek için Windows 10 cihaz ayarları](identity-protection-windows-settings.md)

4. İşiniz bittiğinde **Tamam** > **Oluştur**’u seçerek değişikliklerinizi kaydedin.

Profil oluşturulur ve Profiller listede görünür. Ardından, [atama](device-profile-assign.md) bu profili gruplara.

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/disable-android-camera.png)

-->

## <a name="next-steps"></a>Sonraki adımlar

- Tüm listesini görmek [ayarları ve ne yaptıklarını](identity-protection-windows-settings.md).
- [Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).