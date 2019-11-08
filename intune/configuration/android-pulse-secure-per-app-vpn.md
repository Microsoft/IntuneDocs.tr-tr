---
title: Android için özel uygulama başına VPN profili
titleSuffix: Microsoft Intune
description: Microsoft Intune tarafından yönetilen Android cihazları için uygulama başına VPN profili oluşturmayı öğrenin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d035ebf5-85f4-4001-a249-75d24325061a
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f044d42a36717e970abba37009df2e3d0516a046
ms.sourcegitcommit: 1a7f04c80548e035be82308d2618492f6542d3c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73756742"
---
# <a name="use-a-microsoft-intune-custom-profile-to-create-a-per-app-vpn-profile-for-android-devices"></a>Microsoft Intune özel profili kullanarak Android cihazları için uygulama başına VPN profili oluşturma

[!INCLUDE[azure_portal](../includes/azure_portal.md)]

Intune tarafından yönetilen Android 5.0 ve üzeri cihazlar için uygulama başına VPN profili oluşturabilirsiniz. İlk olarak, Pulse Secure veya Citrix bağlantı türlerinden birini kullanan bir VPN profili oluşturun. Ardından, VPN profilini belirli uygulamalarla ilişkilendiren özel bir yapılandırma ilkesi oluşturun.

İlkeyi Android cihazınıza veya kullanıcı gruplarına atadıktan sonra kullanıcılar, Pulse Secure veya Citrix VPN istemcisini başlatmalıdır. VPN istemcisi bundan sonra yalnızca belirtilen uygulamalardan gelen trafiğin VPN bağlantısını kullanmasına izin verir.

> [!NOTE]
>
> Bu profil için yalnızca Pulse Secure ve Citrix bağlantı türleri desteklenir.

## <a name="step-1-create-a-vpn-profile"></a>1\. Adım: VPN profili oluşturma

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. **Profil oluşturma** > **yapılandırma profilleri** > **cihazları** seçin.
3. Aşağıdaki özellikleri girin:

    - **Ad**: profil için açıklayıcı bir ad girin. Profillerinizi daha sonra kolayca tanıyacak şekilde adlandırın. Örneğin, iyi bir profil adı, **tüm şirket Için Android uygulama BAŞıNA VPN profilidir**.
    - **Açıklama**: Profil için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
    - **Platform**: **Android**' i seçin.
    - **Profil türü**: **VPN**' yi seçin.

4. **Ayarlar** > **Yapılandır**’ı seçin, ardından [VPN ayarlarını yapılandırma](vpn-settings-configure.md) ve [Android cihazları için Intune VPN ayarları](vpn-settings-android.md) konularında belirtilen ayarlara göre VPN profilini yapılandırın.

VPN profilini oluştururken, belirttiğiniz **Bağlantı Adı** değerini bir yere not edin. Bu ad sonraki adımda gerekli olacaktır. Örneğin, **UygulamaVpnProfilim**.

## <a name="step-2-create-a-custom-configuration-policy"></a>2\. Adım: Özel yapılandırma ilkesi oluşturma

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. **Profil oluşturma** > **yapılandırma profilleri** > **cihazları** seçin.
3. Aşağıdaki özellikleri girin:

    - **Ad**: özel profil için açıklayıcı bir ad girin. Profillerinizi daha sonra kolayca tanıyacak şekilde adlandırın. Örneğin, iyi bir profil adı, **tüm şirket Için özel OMA-URI ANDROID VPN profilidir**.
    - **Açıklama**: Profil için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
    - **Platform**: **Android**' i seçin.
    - **Profil türü**: **özel**' i seçin.

4. **Ayarlar** > **Yapılandır**’ı seçin.
5. **Özel OMA-URI Ayarları** bölmesinde **Ekle**’yi seçin.
    - **Ad**: ayarınız için bir ad girin.
    - **Açıklama**: Profil için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
    - **OMA-URI**: `./Vendor/MSFT/VPN/Profile/*Name*/PackageList`girin; burada *ad* , 1. adım 'da not ettiğiniz bağlantı adıdır. Bu örnekte, dize `./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/PackageList`.
    - **Veri türü**: **dize**girin.
    - **Değer**: profille ilişkilendirilecek paketlerin noktalı virgülle ayrılmış bir listesini girin. Örneğin, Excel 'In ve Google Chrome tarayıcısının VPN bağlantısını kullanmasını istiyorsanız, `com.microsoft.office.excel;com.android.chrome`girin.

![Örnek Android uygulama başına VPN özel ilkesi](./media/android-pulse-secure-per-app-vpn/android_per_app_vpn_oma_uri.png)

### <a name="set-your-app-list-to-blacklist-or-whitelist-optional"></a>Uygulama listenizi kara liste veya beyaz liste olarak ayarlama (isteğe bağlı)

**Kara** liste DEĞERINI kullanarak VPN bağlantısını *kullanamaz* uygulamaların bir listesini girebilirsiniz. Diğer tüm uygulamalar VPN üzerinden bağlanır. Veya, VPN bağlantısını kullanan uygulamaların bir listesini girmek için **beyaz liste** değerini *de kullanabilirsiniz.* Listede olmayan uygulamalar VPN üzerinden bağlanmazlar.

1. **Özel OMA-URI Ayarları** bölmesinde **Ekle**’yi seçin.
2. Bir ayar adı girin.
3. **OMA-URI**' de `./Vendor/MSFT/VPN/Profile/*Name*/Mode`girin; burada *ad* , 1. adım 'da not ettiğiniz VPN profili adıdır. Örneğimizde dize `./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/Mode`.
4. **Veri türü**' nde **dize**girin.
5. **Değer** alanına **KARA LİSTE** veya **BEYAZ LİSTE** girin.

## <a name="step-3-assign-both-policies"></a>3\. Adım: Her iki ilkeyi de atama

Gerekli kullanıcılara veya cihazlara [her iki cihaz profilini de atayın](device-profile-assign.md) .
