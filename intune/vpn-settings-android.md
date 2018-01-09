---
title: "Android cihazları için Intune VPN ayarları"
titlesuffix: Azure portal
description: "Android cihazlarda VPN bağlantılarını yapılandırmak için kullanabileceğiniz Intune ayarları hakkında bilgi edinin"
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 16c056ca-320e-4107-ad03-a0cf96c28885
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 17aa425a7daad35860eb4694e9bf798dc655992c
ms.sourcegitcommit: a3a744ea55f38a360ca9f788c77a5b3018d1add5
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/30/2017
---
# <a name="vpn-settings-for-android-devices-in-microsoft-intune"></a>Microsoft Intune’da Android cihazları için VPN ayarları

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Bir Intune yöneticisi olarak aşağıdaki platformlar için VPN ayarları yapılandırabilirsiniz:

- [Android](#android-vpn-settings)
- [Android for Work](#android-for-work-vpn-settings)

Seçtiğiniz ayarlara bağlı olarak, aşağıda listelenen değerlerden bazıları yapılandırılamaz.

## <a name="android-vpn-settings"></a>Android VPN ayarları
**Bağlantı adı** - Bu bağlantı için bir ad girin. Cihazlarındaki kullanılabilir VPN bağlantılarına göz atan son kullanıcılar bu adı görür.
- **IP adresi veya FQDN** - Cihazların bağlanacağı VPN sunucusunun IP adresini veya tam etki alanı adını sağlayın. Örnekler: **192.168.1.1**, **vpn.contoso.com**.
- **Kimlik doğrulama yöntemi** - Cihazların VPN sunucusuna kimliklerini nasıl doğrulayacaklarını seçin:
    - **Sertifikalar** - Bağlantının kimliğini doğrulamak için daha önce oluşturduğunuz SCEP veya PKCS sertifika profilini seçin. Sertifika profilleri hakkındaki diğer ayrıntılar için bkz. [Sertifikaları yapılandırma](certificates-configure.md).
    - **Kullanıcı adı ve parola** - Son kullanıcıların VPN sunucusunda oturum açmak için kullanıcı adı ve parola sağlaması gerekir.
- **Bağlantı türü** - Aşağıdaki satıcı listesinden VPN bağlantı türünü seçin:
    - **Check Point Capsule VPN**
    - **Cisco AnyConnect**
    - **Dell SonicWALL Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**
    - **Citrix**

- **Parmak izi** (yalnızca Check Point Capsule VPN) - VPN sunucusunun güvenilir olduğunu doğrulamak için kullanılacak bir dize (örneğin "Contoso Parmak İzi Kodu") belirtin. Parmak izi, bağlanırken aynı parmak izini sunan herhangi bir sunucuya güvenmesi için istemciye gönderilebilir. Cihazda henüz parmak izi yoksa, parmak izini gösterirken kullanıcıdan bağlandığı VPN sunucusuna güvenmesini ister (kullanıcı parmak izini el ile doğrular ve bağlanmak için güven’i seçer).
- **Citrix VPN öznitelikleri için anahtar ve değer çiftleri girin** (yalnızca Citrix) - VPN bağlantısının özelliklerini yapılandırmak için, Citrix tarafından sağlanan anahtar ve değer çiftlerini girin.

## <a name="android-for-work-vpn-settings"></a>Android for Work VPN ayarları

**Bağlantı adı** - Bu bağlantı için bir ad girin. Cihazlarındaki kullanılabilir VPN bağlantılarına göz atan son kullanıcılar bu adı görür.
- **IP adresi veya FQDN** - Cihazların bağlanacağı VPN sunucusunun IP adresini veya tam etki alanı adını sağlayın. Örnekler: **192.168.1.1**, **vpn.contoso.com**.
- **Kimlik doğrulama yöntemi** - Cihazların VPN sunucusuna kimliklerini nasıl doğrulayacaklarını seçin:
    - **Sertifikalar** - Bağlantının kimliğini doğrulamak için daha önce oluşturduğunuz SCEP veya PKCS sertifika profilini seçin. Sertifika profilleri hakkındaki diğer ayrıntılar için bkz. [Sertifikaları yapılandırma](certificates-configure.md).
    - **Kullanıcı adı ve parola** - Son kullanıcıların VPN sunucusunda oturum açmak için kullanıcı adı ve parola sağlaması gerekir.
- **Bağlantı türü** - Aşağıdaki satıcı listesinden VPN bağlantı türünü seçin:
    - **Check Point Capsule VPN**
    - **Cisco AnyConnect**
    - **Dell SonicWALL Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**

- **Bölünmüş tünel** - Belirli bir web trafiğinin, diğer trafik İnternet kullanırken VPN bağlantısını kullanmasına izin vermek için etkinleştirin. Tüm trafiğin etkin olduğunda VPN kullanmasını istiyorsanız, bu ayarı devre dışı bırakın.
