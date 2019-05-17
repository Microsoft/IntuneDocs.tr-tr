---
title: Microsoft Intune macOS cihazları için VPN ayarları
titleSuffix: ''
description: MacOS cihazlarda VPN bağlantılarını yapılandırmak için kullanabileceğiniz Intune ayarlarını öğrenin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/6/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f752ec33ca7a69d698ffe2c06c726f3881cc35ce
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2019
ms.locfileid: "59900613"
---
# <a name="configure-vpn-settings-in-microsoft-intune-for-devices-running-macos"></a>macOS çalıştıran cihazlar için Microsoft Intune'da VPN ayarlarını yapılandırın

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bu makale, macOS çalıştıran cihazlarda VPN bağlantılarını yapılandırmak için kullanabileceğiniz Intune ayarları hakkında bilgi sağlar.

Seçtiğiniz ayarlara bağlı olarak, aşağıdaki listede yer alan değerlerden bazıları yapılandırılamaz.

## <a name="base-vpn-settings"></a>Temel VPN ayarları

**Bağlantı adı** - Bu bağlantı için bir ad girin. Cihazlarındaki kullanılabilir VPN bağlantılarına göz atan son kullanıcılar bu adı görür.
- **IP adresi veya FQDN** - Cihazların bağlanacağı VPN sunucusunun IP adresini veya tam etki alanı adını sağlayın. Örnekler: **192.168.1.1**, **vpn.contoso.com**.
- **Kimlik doğrulama yöntemi** - Cihazların VPN sunucusuna kimliklerini nasıl doğrulayacaklarını seçin:
    - **Sertifikalar** - **Kimlik doğrulama sertifikası**’nın altında, bağlantının kimliğini doğrulamak için daha önce oluşturduğunuz SCEP veya PKCS sertifika profilini seçin. Sertifika profilleri hakkındaki diğer ayrıntılar için bkz. [Sertifikaları yapılandırma](certificates-configure.md).
    - **Kullanıcı adı ve parola** - Son kullanıcıların VPN sunucusunda oturum açmak için kullanıcı adı ve parola sağlaması gerekir.
- **Bağlantı türü** - Aşağıdaki satıcı listesinden VPN bağlantı türünü seçin:
    - **Check Point Capsule VPN**
    - **Cisco AnyConnect**
    - **SonicWall Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**
    - **Özel VPN**
- **Bölünmüş tünel** - Trafiğe bağlı olarak hangi bağlantının kullanılacağına cihazların karar vermesini sağlayan bu seçeneği **Etkinleştirin** veya **Devre Dışı Bırakın**. Örneğin, oteldeki bir kullanıcı çalışma dosyalarına erişmek için VPN bağlantısını, web’e göz atmak için ise otelin standart ağını kullanır.

<!--- **Per-app VPN** - Select this option if you want to associate this VPN connection with an iOS or macOS app so that the connection will be opened when the app is run. You can associate the VPN profile with an app when you assign the software. For more information, see [How to assign and monitor apps](apps-deploy.md). --->

## <a name="custom-vpn-settings"></a>Özel VPN ayarları

**Özel VPN**’yi seçtiyseniz şu ek ayarları yapılandırın:

- **VPN tanımlayıcısı** Bu, kullandığınız VPN uygulamasının tanımlayıcısıdır ve VPN sağlayıcınız tarafından verilir.
- **Özel VPN öznitelikleri için anahtar ve değer çiftlerini girin** VPN bağlantınızı özelleştiren **Anahtarlar** ve **Değerler**’i ekleyin veya içeri aktarın. Yinelemek gerekirse, bu değerler normalde VPN sağlayıcınız tarafından verilir.


## <a name="proxy-settings"></a>Proxy ayarları

- **Otomatik yapılandırma betiği** - Proxy sunucusunu yapılandırmak için bir dosya kullanın. Yapılandırma dosyasını içeren **Proxy sunucu URL'sini** girin. Örneğin, şunu girin: `http://proxy.contoso.com`.
- **Adres** - Proxy sunucusu adresini (IP adresi olarak) girin.
- **Bağlantı noktası numarası** - Proxy sunucusuyla ilişkilendirilmiş bağlantı noktası numarasını girin.
