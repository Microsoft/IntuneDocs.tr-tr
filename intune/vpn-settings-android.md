---
title: Microsoft Intune'da Android cihazları için VPN ayarlarını yapılandırma - Azure | Microsoft Docs
description: Android ve Android for Work cihazları için VPN yapılandırma profili oluştururken bağlantı adını girin, VPN sunucusunun IP adresini veya FQDN’sini girin, kullanıcıların VPN sunucusunda nasıl kimlik doğrulayacağını belirleyin ve daha sonra Citrix, SonicWall, Check Point Capsule, Pulse Secure ve Microsoft Edge bağlantı türlerini seçin.
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
ms.collection: M365-identity-device-management
ms.openlocfilehash: f37d19beddd96fdad63c61d83b0012869a7f9cd3
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55843723"
---
# <a name="configure-vpn-settings-for-devices-running-android-in-intune"></a>Intune’da Android çalıştıran cihazlar için VPN ayarları yapılandırma

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bu makale, Android çalıştıran cihazlarda VPN bağlantılarını yapılandırmak için kullanabileceğiniz Intune ayarları hakkında bilgi sağlar.

Aşağıdaki platformlar için VPN ayarları yapılandırabilirsiniz:

- [Android](#android-vpn-settings)
- [Android kurumsal](#android-enterprise-vpn-settings)

Seçtiğiniz ayarlara bağlı olarak, aşağıdaki değerlerden bazıları yapılandırılamaz.

## <a name="android-vpn-settings"></a>Android VPN ayarları

- **Bağlantı adı**: Bu bağlantı için bir ad girin. Cihazlarındaki kullanılabilir VPN bağlantılarına göz atan son kullanıcılar bu adı görür.
- **IP adresi veya FQDN**: IP adresi veya cihazların bağlandığı VPN sunucusunun tam etki alanı adı (FQDN) girin. Örneğin, **192.168.1.1** veya **vpn.contoso.com** yazın.

  - **Kimlik doğrulama yöntemi**: Cihazların VPN sunucusuna kimliklerini nasıl doğrulayacaklarını seçin. Seçenekleriniz şunlardır:

    - **Sertifikaları**: Bağlantı kimliğini doğrulamak için bir var olan SCEP veya PKCS sertifika profilini seçin. [Sertifikaları yapılandırın](certificates-configure.md), sertifika profili oluşturma adımlarını listeler.
    - **Kullanıcı adı ve parola**: VPN sunucusunda oturum açarken, son kullanıcıların bir kullanıcı adı ve parola girmeniz istenir.

- **Bağlantı türü**: VPN bağlantı türünü seçin. Seçenekleriniz şunlardır:

  - **Check Point Capsule VPN**
  - **Cisco AnyConnect**
  - **SonicWall Mobile Connect**
  - **F5 Edge Client**
  - **Pulse Secure**
  - **Citrix**

- **Parmak izi** (denetimi yalnızca Point Capsule VPN): Gibi bir dize girin **Contoso parmak izi kodu**VPN sunucusunun güvenilir olduğunu doğrulamak için. Parmak izi, bağlanırken aynı parmak izine sahip herhangi bir sunucuya güvenmesi için istemciye gönderilebilir. Cihazda parmak izi yoksa, parmak izini göstererek kullanıcıdan VPN sunucusuna güvenmesini ister. Kullanıcı parmak izini el ile doğrular ve bağlanmak için güven seçeneğini belirtir.
- **Citrix VPN öznitelikleri için anahtar ve değer çiftlerini girin** (yalnızca Citrix): Citrix tarafından sağlanan anahtar ve değer çiftlerini girin. Bu değerler VPN bağlantısının özelliklerini yapılandırır.

## <a name="android-enterprise-vpn-settings"></a>Android Kurumsal VPN ayarları

- **Bağlantı adı**: Bu bağlantı için bir ad girin. Cihazlarındaki kullanılabilir VPN bağlantılarına göz atan son kullanıcılar bu adı görür.
- **IP adresi veya FQDN**: IP adresi veya cihazların bağlandığı VPN sunucusunun tam etki alanı adı (FQDN) girin. Örneğin, **192.168.1.1** veya **vpn.contoso.com** yazın.

  - **Kimlik doğrulama yöntemi**: Cihazların VPN sunucusuna kimliklerini nasıl doğrulayacaklarını seçin. Seçenekleriniz şunlardır:
  
    - **Sertifikaları**: Bağlantı kimliğini doğrulamak için bir var olan SCEP veya PKCS sertifika profilini seçin. [Sertifikaları yapılandırın](certificates-configure.md), sertifika profili oluşturma adımlarını listeler.
    - **Kullanıcı adı ve parola**: VPN sunucusunda oturum açarken, son kullanıcıların bir kullanıcı adı ve parola girmeniz istenir.

- **Bağlantı türü**: VPN bağlantı türünü seçin. Seçenekleriniz şunlardır:

  - **Check Point Capsule VPN**
  - **Cisco AnyConnect**
  - **SonicWall Mobile Connect**
  - **F5'e erişim**
  - **Pulse Secure**

## <a name="next-steps"></a>Sonraki adımlar
[Intune’da VPN profilleri](vpn-settings-configure.md)
