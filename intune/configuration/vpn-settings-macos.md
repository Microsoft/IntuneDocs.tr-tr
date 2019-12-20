---
title: VPN ayarlarını Microsoft Intune-Azure 'da macOS cihazlarına yapılandırma | Microsoft Docs
description: Bağlantı ayrıntıları, bölünmüş tünel, tanımlayıcı, anahtar ve değer çiftleri ile özel VPN ayarları, bir yapılandırma betiği, IP veya FQDN adresi ve TCP bağlantı noktası içeren bir sanal özel ağ (VPN) yapılandırma profili ekleyin veya oluşturun. MacOS çalıştıran cihazlarda Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/09/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e0bb2cb757e944369642807f117683dad3a9805a
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/19/2019
ms.locfileid: "75206270"
---
# <a name="add-vpn-settings-on-macos-devices-in-microsoft-intune"></a>Microsoft Intune 'de macOS cihazlarına VPN ayarları ekleme



Bu makale, macOS çalıştıran cihazlarda VPN bağlantılarını yapılandırmak için kullanabileceğiniz Intune ayarları hakkında bilgi sağlar.

Seçtiğiniz ayarlara bağlı olarak, aşağıdaki listede yer alan değerlerden bazıları yapılandırılamaz.

## <a name="before-you-begin"></a>Başlamadan önce

[Bir cihaz yapılandırma profili oluşturma](vpn-settings-configure.md).

> [!NOTE]
> Bu ayarlar tüm kayıt türleri için kullanılabilir. Kayıt türleri hakkında daha fazla bilgi için bkz. [MacOS kaydı](../enrollment/macos-enroll.md).

## <a name="base-vpn-settings"></a>Temel VPN ayarları

**Bağlantı adı**: Bu bağlantı için bir ad girin. Cihazlarındaki kullanılabilir VPN bağlantılarına göz atan son kullanıcılar bu adı görür.
- **IP adresi veya FQDN**: CIHAZLARıN bağlanacağı VPN sunucusunun IP adresini veya tam etki alanı adını belirtin. Örnekler: **192.168.1.1**, **vpn.contoso.com**.
- **Kimlik doğrulama yöntemi**: Cihazların VPN sunucusunda kimliklerini nasıl doğrulayacaklarını seçin:
  - **Sertifikalar**: **kimlik doğrulama sertifikası**altında, bağlantının kimliğini doğrulamak için daha önce oluşturduğunuz bir SCEP veya PKCS sertifika profilini seçin. Sertifika profilleri hakkındaki daha fazla bilgi için bkz. [Sertifikaları yapılandırma](../protect/certificates-configure.md).
  - **Kullanıcı adı ve parola**: son kullanıcılar VPN sunucusunda oturum açmak için bir Kullanıcı adı ve parola sağlamalıdır.
- **Bağlantı türü**: Aşağıdaki satıcı listesinden VPN bağlantı türünü seçin:
  - **Check Point Capsule VPN**
  - **Cisco AnyConnect**
  - **SonicWall Mobile Connect**
  - **F5 Edge Client**
  - **Pulse Secure**
  - **Özel VPN**
- **Bölünmüş tünel**: cihazların trafiğe bağlı olarak hangi bağlantının kullanılacağına karar vermesine olanak sağlayan bu seçeneği **etkinleştirin** veya **devre dışı bırakın** . Örneğin, oteldeki bir kullanıcı çalışma dosyalarına erişmek için VPN bağlantısını, web’e göz atmak için ise otelin standart ağını kullanır.

<!--- **Per-app VPN** - Select this option if you want to associate this VPN connection with an iOS or macOS app so that the connection will be opened when the app is run. You can associate the VPN profile with an app when you assign the software. For more information, see [How to assign and monitor apps](../apps/apps-deploy.md). --->

## <a name="custom-vpn-settings"></a>Özel VPN ayarları

**Özel VPN**’yi seçtiyseniz şu ek ayarları yapılandırın:

- **VPN tanımlayıcısı**: kullanmakta olduğunuz VPN uygulaması için bir tanımlayıcı girin. Bu tanımlayıcı, VPN sağlayıcınız tarafından sağlanır.
- **Özel VPN öznitelikleri için anahtar ve değer çiftlerini girin**: VPN bağlantınızı özelleştiren **Anahtarlar** ve **Değerler**’i ekleyin veya içeri aktarın. Bu değerler genellikle VPN sağlayıcınız tarafından sağlanır.

## <a name="proxy-settings"></a>Proxy ayarları

- **Otomatik yapılandırma betiği**: Proxy sunucusunu yapılandırmak için bir dosya kullanın. Yapılandırma dosyasını içeren **Proxy sunucu URL'sini** girin. Örneğin, şunu girin: `http://proxy.contoso.com`.
- **Adres**: proxy sunucu adresini (bir IP adresi olarak) girin.
- **Bağlantı noktası numarası**: Proxy sunucusuyla ilişkilendirilmiş bağlantı noktası numarasını girin.

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturulur ancak henüz herhangi bir işlem gerçekleştirmez. Ardından [profili atayın](device-profile-assign.md) ve [durumunu izleyin](device-profile-monitor.md).

[Android](vpn-settings-android.md), [Android Enterprise](vpn-settings-android-enterprise.md), [IOS](vpn-settings-ios.md)ve [Windows 10](vpn-settings-windows-10.md) cihazlarında VPN ayarlarını yapılandırın.
