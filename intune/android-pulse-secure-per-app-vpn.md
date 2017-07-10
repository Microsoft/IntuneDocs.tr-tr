---
title: "Android Pulse Secure için uygulama başına VPN profili"
titleSuffix: Intune on Azure
description: "Intune tarafından yönetilen Android cihazları için uygulama başına VPN profili oluşturmayı öğrenin.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d035ebf5-85f4-4001-a249-75d24325061a
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f0e3a8363eb25ba3a3b2c16f15b8188acb694938
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="use-a-microsoft-intune-custom-profile-to-create-a-per-app-vpn-profile-for-android-devices"></a>Microsoft Intune özel profili kullanarak Android cihazları için uygulama başına VPN profili oluşturma

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune tarafından yönetilen Android 5.0 ve üzeri cihazlar için uygulama başına VPN profili oluşturabilirsiniz. İlk olarak, Pulse Secure bağlantı türünü kullanan bir VPN profili oluşturun. Ardından, VPN profilini belirli uygulamalarla ilişkilendiren özel bir yapılandırma ilkesi oluşturun.

İlkeyi Android cihazınıza veya kullanıcı gruplarına atadıktan sonra kullanıcılar PulseSecure VPN’i başlatmalıdır. PulseSecure bundan sonra yalnızca belirtilen uygulamalardan gelen trafiğin VPN bağlantısını kullanmasına izin verir.

> [!NOTE]
>
> Bu profil için yalnızca Pulse Secure bağlantı türü desteklenir.


## <a name="step-1-create-a-vpn-profile"></a>1. Adım: VPN profili oluşturma


1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihaz yapılandırması**’nı seçin.
2. **Cihaz Yapılandırması** dikey penceresinde **Yönet** > **Profiller**’i seçin.
2. Profil listesi dikey penceresinde **Profil Oluştur**’u seçin.
3. **Profil Oluştur** dikey penceresinde, VPN profili için **Ad** ve isteğe bağlı bir **Açıklama** girin.
4. **Platform** açılan listesinden **Android**’i seçin.
5. **Profil türü** açılan listesinden **VPN**’yi seçin.
3. **Ayarlar** > **Yapılandır**’ı seçin, ardından [VPN ayarlarını yapılandırma](vpn-settings-configure.md) ve [Android cihazları için Intune VPN ayarları](vpn-settings-android.md) konularında belirtilen ayarlara göre VPN profilini yapılandırın.

VPN profilini oluştururken, belirttiğiniz **Bağlantı Adı** değerini bir yere not edin. Bu ad sonraki adımda gerekli olacaktır. Örneğin, **UygulamaVpnProfilim**.

## <a name="step-2-create-a-custom-configuration-policy"></a>2. Adım: Özel yapılandırma ilkesi oluşturma

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihaz yapılandırması**’nı seçin.
2. **Cihaz Yapılandırması** dikey penceresinde **Yönet** > **Profiller**’i seçin.
3. Profiller dikey penceresinde **Profil Oluştur**’a tıklayın.
4. **Profil Oluştur** dikey penceresinde, özel profil için **Ad** ve **Açıklama** girin.
5. **Platform** açılan listesinden **Android**’i seçin.
6. **Profil türü** açılan listesinden **Özel**’i seçin.
7. **Ayarlar** > **Yapılandır**’ı seçin.
3. **Özel OMA-URI Ayarları** dikey penceresinde **Ekle**’yi seçin.
    - Bir ayar adı girin.
    - **Veri türü** olarak **Dize**’yi belirtin.
    - **OMA-URI** için şu dizeyi belirtin: **./Vendor/MSFT/VPN/Profile/*Ad*/PackageList**; burada *Ad*, 1. Adım’da not ettiğiniz VPN profili adıdır. Bu örnekte, dize şöyle olabilir: **./Vendor/MSFT/VPN/Profile/UygulamaVpnProfilim/PaketListesi**.
    - **Değer** için, profille ilişkilendirilecek paketlerin noktalı virgülle ayrılmış bir listesini oluşturun. Örneğin, Excel’in ve Google Chrome tarayıcısının VPN bağlantısını kullanmasını istiyorsanız, **com.microsoft.office.excel;com.android.chrome** girin.

![Örnek Android uygulama başına VPN özel ilkesi](./media/android_per_app_vpn_oma_uri.png)

### <a name="set-your-app-list-to-blacklist-or-whitelist-optional"></a>Uygulama listenizi kara liste veya beyaz liste olarak ayarlama (isteğe bağlı)
  **KARA LİSTE** değerini kullanarak, VPN bağlantısını *kullanamayacak* uygulamaların listesini belirtebilirsiniz. Diğer tüm uygulamalar VPN üzerinden bağlanır.
Alternatif olarak, **BEYAZ LİSTE** değerini kullanabilir ve VPN bağlantısını *kullanabilecek* uygulamaların listesini belirtebilirsiniz. Listede yer almayan uygulamalar VPN üzerinden bağlanmaz.
  1.    **Özel OMA-URI Ayarları** dikey penceresinde **Ekle**’yi seçin.
  2.    Bir ayar adı girin.
  3.    **Veri türü** olarak **Dize**’yi belirtin.
  4.    **OMA-URI** için şu dizeyi kullanın: **./Vendor/MSFT/VPN/Profile/*Ad*/Mode**; burada *Ad*, 1. Adım’da not ettiğiniz VPN profili adıdır. Bizim örneğimizde, dize şöyle olabilir: **./Vendor/MSFT/VPN/Profile/UygulamamVpnProfili/Mode**.
  5.    **Değer** alanı için **KARA LİSTE** veya **BEYAZ LİSTE** girin.



## <a name="step-3-assign-both-policies"></a>3. Adım: Her iki ilkeyi de atama

Gerekli kullanıcılara veya cihazlara her iki profili de atamak için, [Cihaz profillerini atama](device-profile-assign.md) başlığı altında verilen yönergeleri kullanın.
