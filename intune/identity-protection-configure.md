---
title: Microsoft Intune-Azure kullanarak Windows 10 cihazlarda oturum açmak için PIN kullanma | Microsoft Docs
description: Kullanıcıların bir PIN, parmak izi ve daha fazlasını kullanarak cihazlarda oturum açmalarına olanak tanımak için Iş için Windows Hello 'Yu kullanın. Bu ayarlarla Windows 10 cihazları için Intune 'da bir kimlik koruması yapılandırma profili oluşturun ve profili Kullanıcı gruplarına ve cihaz gruplarına atayın.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/29/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b6dd7f33aa38a8d3ab4afb2c06952c08093fa64d
ms.sourcegitcommit: 119962948045079022aa48f968dde3e961d7cd0c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/12/2019
ms.locfileid: "71301771"
---
# <a name="use-windows-hello-for-business-on-windows-10-devices-with-microsoft-intune"></a>Microsoft Intune ile Windows 10 cihazlarda Iş için Windows Hello 'Yu kullanma

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Iş için Windows Hello, parolaları, akıllı kartları ve sanal akıllı kartları değiştirerek Windows cihazlarda oturum açmaya yönelik bir yöntemdir. Intune, yöneticilerin Iş için Windows Hello 'Yu yapılandırıp kullanabilmesi için yerleşik ayarları içerir. Örneğin, bu ayarları kullanarak şunları yapabilirsiniz:

- Cihazlar ve kullanıcılar için Iş için Windows Hello 'Yu etkinleştir
- Minimum veya maksimum PIN uzunluğu dahil cihaz PIN gereksinimlerini ayarla
- Kullanıcıların cihazlarda oturum açmasını sağlayan (veya kullanabilecek) parmak izi gibi hareketlere izin ver

Bu özellik şunları çalıştıran cihazlarda geçerlidir:

- Windows 10 ve üzeri
- Windows 10 Mobile
- Windows 10 Holographic for Business

Intune, kuruluşunuzun ihtiyaçlarına göre bu ayarları oluşturmak ve özelleştirmek için "yapılandırma profillerini" kullanır. Bu özellikleri bir profilde ekledikten sonra bu ayarları kuruluşunuzdaki Kullanıcı ve cihaz gruplarına gönderin veya dağıtın.

Bu makalede bir cihaz yapılandırma profili oluşturma konusu gösterilmektedir. Tüm ayarların bir listesi ve ne yapacaklarınız için Windows 10 cihaz ayarları ' na bakın ve [iş Için Windows Hello 'yu etkinleştirin](identity-protection-windows-settings.md).

## <a name="create-the-device-profile"></a>Cihaz profili oluşturma

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**'u seçin.
3. Aşağıdaki özellikleri girin:

    - **Ad**: Yeni profil için açıklayıcı bir ad girin.
    - **Açıklama**: Profil için açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
    - **Platform**: **Windows 10 ve üstünü**seçin. İş İçin Windows Hello, yalnızca Windows 10 ve üzeri çalıştıran cihazlarda desteklenir.
    - **Profil türü**: **Kimlik koruması**' nı seçin.
    - **İş Için Windows Hello 'Yu Yapılandır**: Iş için Windows Hello 'yu nasıl yapılandırmak istediğinizi seçin. Seçenekleriniz şunlardır:

        - **Yapılandırılmadı**: Cihazda [iş Için Windows Hello 'Yu sağlar](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-how-it-works-provisioning) . Kimlik koruma profillerini yalnızca kullanıcılara atarken cihaz bağlamı varsayılan olarak **Yapılandırılmadı** olur.
        - **Devre dışı**: Iş için Windows Hello 'Yu kullanmak istemiyorsanız bu seçeneği belirleyin. Bu seçenek tüm kullanıcılar için Iş için Windows Hello 'Yu devre dışı bırakır.
        - **Etkin**: Intune 'da Iş için Windows Hello ayarlarını [sağlamak](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-how-it-works-provisioning)ve yapılandırmak için bu seçeneği belirleyin. Yapılandırmak istediğiniz ayarları girin. Tüm ayarların bir listesi ve ne yapacaklarınız için, bkz.:

            - [Iş için Windows Hello 'Yu etkinleştirmek için Windows 10 cihaz ayarları](identity-protection-windows-settings.md)

4. İşiniz bittiğinde **Tamam** > **Oluştur**’u seçerek değişikliklerinizi kaydedin.

Profil oluşturulur ve profiller listesinde görüntülenir. Daha sonra, gereksinimlerinizi karşılamak için bu profili Kullanıcı ve cihaz gruplarına [atayın](device-profile-assign.md) .

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/disable-android-camera.png)

-->

## <a name="next-steps"></a>Sonraki adımlar

- Tüm ayarların bir listesini [ve ne yaptığını](identity-protection-windows-settings.md)görün.
- [Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).
