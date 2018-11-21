---
title: Microsoft Intune'da Android cihazları için VPN ayarlarını yapılandırma - Azure | Microsoft Docs
description: Android ve Android for Work cihazları için VPN yapılandırma profili oluştururken bağlantı adını girin, VPN sunucusunun IP adresini veya FQDN’sini girin, kullanıcıların VPN sunucusunda nasıl kimlik doğrulayacağını belirleyin ve daha sonra Citrix, SonicWall, Check Point Capsule, Pulse Secure ve Microsoft Edge bağlantı türlerini seçin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 7/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: ac4b7821f132c92b247538e4ea6131f517da7698
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52187703"
---
# <a name="configure-vpn-settings-for-devices-running-android-in-intune"></a>Intune’da Android çalıştıran cihazlar için VPN ayarları yapılandırma

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bu makale, Android çalıştıran cihazlarda VPN bağlantılarını yapılandırmak için kullanabileceğiniz Intune ayarları hakkında bilgi sağlar.

Aşağıdaki platformlar için VPN ayarları yapılandırabilirsiniz:

- [Android](#android-vpn-settings)
- [Android for Work](#android-for-work-vpn-settings)

Seçtiğiniz ayarlara bağlı olarak, aşağıdaki değerlerden bazıları yapılandırılamaz.

## <a name="android-vpn-settings"></a>Android VPN ayarları

- **Bağlantı adı**: Bu bağlantı için bir ad girin. Cihazlarındaki kullanılabilir VPN bağlantılarına göz atan son kullanıcılar bu adı görür.
- **IP adresi veya FQDN**: Cihazların bağlandığı VPN sunucusunun IP adresini veya tam etki alanı adını (FQDN) girin. Örneğin, **192.168.1.1** veya **vpn.contoso.com** yazın.

  - **Kimlik doğrulama yöntemi**: Cihazların VPN sunucusunda kimliklerini nasıl doğrulayacaklarını seçin. Seçenekleriniz şunlardır:

    - **Sertifikalar**: Bağlantının kimliğini doğrulamak için mevcut bir SCEP veya PKCS sertifika profili seçin. [Sertifikaları yapılandırın](certificates-configure.md), sertifika profili oluşturma adımlarını listeler.
    - **Kullanıcı adı ve parola**: VPN sunucusunda oturum açarken son kullanıcılardan kullanıcı adı ve parola girmeleri istenir.

- **Bağlantı türü**: VPN bağlantısının türünü seçin. Seçenekleriniz şunlardır:

  - **Check Point Capsule VPN**
  - **Cisco AnyConnect**
  - **SonicWall Mobile Connect**
  - **F5 Edge Client**
  - **Pulse Secure**
  - **Citrix**

- **Parmak izi** (yalnızca Check Point Capsule VPN): VPN sunucusunun güvenilir olduğunu doğrulamak için **Contoso Parmak İzi Kodu** gibi bir dize girin. Parmak izi, bağlanırken aynı parmak izine sahip herhangi bir sunucuya güvenmesi için istemciye gönderilebilir. Cihazda parmak izi yoksa, parmak izini göstererek kullanıcıdan VPN sunucusuna güvenmesini ister. Kullanıcı parmak izini el ile doğrular ve bağlanmak için güven seçeneğini belirtir.
- **Citrix VPN öznitelikleri için anahtar ve değer çiftleri girin** (yalnızca Citrix): Citrix tarafından sağlanan anahtar ve değer çiftlerini girin. Bu değerler VPN bağlantısının özelliklerini yapılandırır.

## <a name="android-for-work-vpn-settings"></a>Android for Work VPN ayarları

- **Bağlantı adı**: Bu bağlantı için bir ad girin. Cihazlarındaki kullanılabilir VPN bağlantılarına göz atan son kullanıcılar bu adı görür.
- **IP adresi veya FQDN**: Cihazların bağlandığı VPN sunucusunun IP adresini veya tam etki alanı adını (FQDN) girin. Örneğin, **192.168.1.1** veya **vpn.contoso.com** yazın.

  - **Kimlik doğrulama yöntemi**: Cihazların VPN sunucusunda kimliklerini nasıl doğrulayacaklarını seçin. Seçenekleriniz şunlardır:
  
    - **Sertifikalar**: Bağlantının kimliğini doğrulamak için mevcut bir SCEP veya PKCS sertifika profili seçin. [Sertifikaları yapılandırın](certificates-configure.md), sertifika profili oluşturma adımlarını listeler.
    - **Kullanıcı adı ve parola**: VPN sunucusunda oturum açarken son kullanıcılardan kullanıcı adı ve parola girmeleri istenir.

- **Bağlantı türü**: VPN bağlantısının türünü seçin. Seçenekleriniz şunlardır:

  - **Check Point Capsule VPN**
  - **Cisco AnyConnect**
  - **SonicWall Mobile Connect**
  - **F5 Edge Client**
  - **Pulse Secure**

## <a name="next-steps"></a>Sonraki adımlar
[Intune’da VPN profilleri](vpn-settings-configure.md)
