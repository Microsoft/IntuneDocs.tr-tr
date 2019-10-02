---
title: Android için özel uygulama başına VPN profili
titleSuffix: Microsoft Intune
description: Microsoft Intune tarafından yönetilen Android cihazları için uygulama başına VPN profili oluşturmayı öğrenin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/05/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d035ebf5-85f4-4001-a249-75d24325061a
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0e8635abe2b1f927147d5a30085efb9884ec7813
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71730945"
---
# <a name="use-a-microsoft-intune-custom-profile-to-create-a-per-app-vpn-profile-for-android-devices"></a>Microsoft Intune özel profili kullanarak Android cihazları için uygulama başına VPN profili oluşturma

[!INCLUDE[azure_portal](../includes/azure_portal.md)]

Intune tarafından yönetilen Android 5.0 ve üzeri cihazlar için uygulama başına VPN profili oluşturabilirsiniz. İlk olarak, Pulse Secure veya Citrix bağlantı türlerinden birini kullanan bir VPN profili oluşturun. Ardından, VPN profilini belirli uygulamalarla ilişkilendiren özel bir yapılandırma ilkesi oluşturun.

İlkeyi Android cihazınıza veya kullanıcı gruplarına atadıktan sonra kullanıcılar, Pulse Secure veya Citrix VPN istemcisini başlatmalıdır. VPN istemcisi bundan sonra yalnızca belirtilen uygulamalardan gelen trafiğin VPN bağlantısını kullanmasına izin verir.

> [!NOTE]
>
> Bu profil için yalnızca Pulse Secure ve Citrix bağlantı türleri desteklenir.


## <a name="step-1-create-a-vpn-profile"></a>1\. Adım: VPN profili oluşturma


1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
3. **Intune** bölmesinde, **Cihaz yapılandırması**’nı seçin.
2. **Yönet** bölümü altındaki **Cihaz yapılandırması** bölmesinden **Profiller**’i seçin.
2. Profil listesi bölmesinde **Profil oluştur**’u seçin.
3. **Profil oluştur** bölmesinde, VPN profili için **Ad** ve isteğe bağlı bir **Açıklama** girin.
4. **Platform** açılan listesinden **Android**’i seçin.
5. **Profil türü** açılan listesinden **VPN**’yi seçin.
3. **Ayarlar** > **Yapılandır**’ı seçin, ardından [VPN ayarlarını yapılandırma](vpn-settings-configure.md) ve [Android cihazları için Intune VPN ayarları](vpn-settings-android.md) konularında belirtilen ayarlara göre VPN profilini yapılandırın.

VPN profilini oluştururken, belirttiğiniz **Bağlantı Adı** değerini bir yere not edin. Bu ad sonraki adımda gerekli olacaktır. Örneğin, **UygulamaVpnProfilim**.

## <a name="step-2-create-a-custom-configuration-policy"></a>2\. Adım: Özel yapılandırma ilkesi oluşturma

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
3. **Intune** bölmesinde, **Cihaz yapılandırması**’nı seçin.
2. **Yönet** bölümü altındaki **Cihaz yapılandırması** bölmesinden **Profiller**’i seçin.
3. Profiller bölmesinde **Profil Oluştur**’a tıklayın.
4. **Profil Oluştur** bölmesinde, özel profil için **Ad** ve **Açıklama** girin.
5. **Platform** açılan listesinden **Android**’i seçin.
6. **Profil türü** açılan listesinden **Özel**’i seçin.
7. **Ayarlar** > **Yapılandır**’ı seçin.
3. **Özel OMA-URI Ayarları** bölmesinde **Ekle**’yi seçin.
    - Bir ayar adı girin.
    - **OMA-URI** için şu dizeyi belirtin: **./Vendor/MSFT/VPN/Profile/*Ad*/PackageList**, burada *Ad* 1. Adım’da not ettiğiniz bağlantı adıdır. Bu örnekte, dize şöyle olabilir: **./Vendor/MSFT/VPN/Profile/UygulamaVpnProfilim/PaketListesi**.
    - **Veri türü** olarak **Dize**’yi belirtin.
    - **Değer** için, profille ilişkilendirilecek paketlerin noktalı virgülle ayrılmış bir listesini oluşturun. Örneğin, Excel’in ve Google Chrome tarayıcısının VPN bağlantısını kullanmasını istiyorsanız, **com.microsoft.office.excel;com.android.chrome** girin.

![Örnek Android uygulama başına VPN özel ilkesi](./media/android-pulse-secure-per-app-vpn/android_per_app_vpn_oma_uri.png)

### <a name="set-your-app-list-to-blacklist-or-whitelist-optional"></a>Uygulama listenizi kara liste veya beyaz liste olarak ayarlama (isteğe bağlı)
  **KARA LİSTE** değerini kullanarak, VPN bağlantısını *kullanamayacak* uygulamaların listesini belirtebilirsiniz. Diğer tüm uygulamalar VPN üzerinden bağlanır.
Alternatif olarak, **BEYAZ LİSTE** değerini kullanabilir ve VPN bağlantısını *kullanabilecek* uygulamaların listesini belirtebilirsiniz. Listede yer almayan uygulamalar VPN üzerinden bağlanmaz.
  1. **Özel OMA-URI Ayarları** bölmesinde **Ekle**’yi seçin.
  2. Bir ayar adı girin.
  3. **OMA-URI** için şu dizeyi kullanın: **./Vendor/MSFT/VPN/Profile/*Ad*/Mode**; burada *Ad*, 1. Adım’da not ettiğiniz VPN profili adıdır. Bizim örneğimizde, dize şöyle olabilir: **./Vendor/MSFT/VPN/Profile/UygulamamVpnProfili/Mode**.
  4. **Veri türü** olarak **Dize**’yi belirtin.
  5. **Değer** alanı için **KARA LİSTE** veya **BEYAZ LİSTE** girin.



## <a name="step-3-assign-both-policies"></a>3\. Adım: Her iki ilkeyi de atama

Gerekli kullanıcılara veya cihazlara her iki profili de atamak için, [Cihaz profillerini atama](device-profile-assign.md) başlığı altında verilen yönergeleri kullanın.
