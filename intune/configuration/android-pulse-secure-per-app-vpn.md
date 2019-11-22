---
title: Android için özel uygulama başına VPN profili
titleSuffix: Microsoft Intune
description: Microsoft Intune tarafından yönetilen Android cihazları için uygulama başına VPN profili oluşturmayı öğrenin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d035ebf5-85f4-4001-a249-75d24325061a
ms.reviewer: tycast
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 62f418e396c5030a47ea0bcb31914cd4e1069c40
ms.sourcegitcommit: eb2e420b304c7da9d3be5ef49a676cba66766d2b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74319850"
---
# <a name="use-a-microsoft-intune-custom-profile-to-create-a-per-app-vpn-profile-for-android-devices"></a>Microsoft Intune özel profili kullanarak Android cihazları için uygulama başına VPN profili oluşturma

Intune tarafından yönetilen Android 5.0 ve üzeri cihazlar için uygulama başına VPN profili oluşturabilirsiniz. İlk olarak, Pulse Secure veya Citrix bağlantı türlerinden birini kullanan bir VPN profili oluşturun. Ardından, VPN profilini belirli uygulamalarla ilişkilendiren özel bir yapılandırma ilkesi oluşturun.

> [!NOTE]
> To use per-app VPN on Android Enterprise devices, you can also use these steps. But, it's recommended to use an [app configuration policy](../apps/app-configuration-policies-use-android.md) for your VPN client app.

İlkeyi Android cihazınıza veya kullanıcı gruplarına atadıktan sonra kullanıcılar, Pulse Secure veya Citrix VPN istemcisini başlatmalıdır. VPN istemcisi bundan sonra yalnızca belirtilen uygulamalardan gelen trafiğin VPN bağlantısını kullanmasına izin verir.

> [!NOTE]
>
> Bu profil için yalnızca Pulse Secure ve Citrix bağlantı türleri desteklenir.

## <a name="step-1-create-a-vpn-profile"></a>1\. Adım: VPN profili oluşturma

1. Sign in to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Select **Devices** > **Configuration profiles** > **Create profile**.
3. Aşağıdaki özellikleri girin:

    - **Name**: Enter a descriptive name for the profile. Profillerinizi daha sonra kolayca tanıyacak şekilde adlandırın. For example, a good profile name is **Android per-app VPN profile for entire company**.
    - **Açıklama**: Profil için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
    - **Platform**: Select **Android**.
    - **Profile type**: Select **VPN**.

4. **Ayarlar** > **Yapılandır**’ı seçin. Then, configure the VPN profile. For more information, see [How to configure VPN settings](vpn-settings-configure.md) and [Intune VPN settings for Android devices](vpn-settings-android.md).

VPN profilini oluştururken, belirttiğiniz **Bağlantı Adı** değerini bir yere not edin. Bu ad sonraki adımda gerekli olacaktır. Örneğin, **UygulamaVpnProfilim**.

## <a name="step-2-create-a-custom-configuration-policy"></a>2\. Adım: Özel yapılandırma ilkesi oluşturma

1. Sign in to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Select **Devices** > **Configuration profiles** > **Create profile**.
3. Aşağıdaki özellikleri girin:

    - **Name**: Enter a descriptive name for the custom profile. Profillerinizi daha sonra kolayca tanıyacak şekilde adlandırın. For example, a good profile name is **Custom OMA-URI Android VPN profile for entire company**.
    - **Açıklama**: Profil için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
    - **Platform**: Select **Android**.
    - **Profile type**: Select **Custom**.

4. **Ayarlar** > **Yapılandır**’ı seçin.
5. **Özel OMA-URI Ayarları** bölmesinde **Ekle**’yi seçin.
    - **Name**: Enter a name for your setting.
    - **Açıklama**: Profil için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
    - **OMA-URI**: Enter `./Vendor/MSFT/VPN/Profile/*Name*/PackageList`, where *Name* is the connection name you noted in Step 1. In this example, the string is `./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/PackageList`.
    - **Data type**: Enter **String**.
    - **Value**: Enter a semicolon-separated list of packages to associate with the profile. For example, if you want Excel and the Google Chrome browser to use the VPN connection, enter `com.microsoft.office.excel;com.android.chrome`.

![Örnek Android uygulama başına VPN özel ilkesi](./media/android-pulse-secure-per-app-vpn/android_per_app_vpn_oma_uri.png)

### <a name="set-your-app-list-to-blacklist-or-whitelist-optional"></a>Uygulama listenizi kara liste veya beyaz liste olarak ayarlama (isteğe bağlı)

Use the **BLACKLIST** value to enter a list of apps that *cannot* use the VPN connection. Diğer tüm uygulamalar VPN üzerinden bağlanır. Or, use the **WHITELIST** value to enter a list of apps that *can* use the VPN connection. Apps that aren't on the list don't connect through the VPN.

1. **Özel OMA-URI Ayarları** bölmesinde **Ekle**’yi seçin.
2. Bir ayar adı girin.
3. In **OMA-URI**, enter `./Vendor/MSFT/VPN/Profile/*Name*/Mode`, where *Name* is the VPN profile name you noted in Step 1. In our example, the string is `./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/Mode`.
4. In **Data type**, enter **String**.
5. **Değer** alanına **KARA LİSTE** veya **BEYAZ LİSTE** girin.

## <a name="step-3-assign-both-policies"></a>3\. Adım: Her iki ilkeyi de atama

[Assign both device profiles](device-profile-assign.md) to the required users or devices.
