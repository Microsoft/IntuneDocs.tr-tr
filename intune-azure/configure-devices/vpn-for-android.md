---
title: "Android cihazlar için Intune VPN ayarları | Intune Azure önizlemesi | Microsoft Docs"
description: "Intune Azure önizlemesi: Android cihazlarda VPN bağlantılarını yapılandırmak için kullanabileceğiniz Intune ayarlarını öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 16c056ca-320e-4107-ad03-a0cf96c28885
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6cd3069a63bd657d1c9f5e33b96db39a3b3f98d2
ms.openlocfilehash: f93ab44889837fe8acc5dd5287b63f3b30678159


---

# <a name="vpn-settings-for-android-devices-in-intune-azure-preview"></a>Intune Azure önizlemesinde Android cihazlar için VPN ayarları

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Seçtiğiniz ayarlara bağlı olarak, aşağıdaki listede yer alan değerlerden bazıları yapılandırılabilir değildir.

**Bağlantı adı** - Bu bağlantı için bir ad girin. Cihazlarındaki kullanılabilir VPN bağlantılarına göz atan son kullanıcılar bu adı görür.
- **IP adresi veya FQDN** - Cihazların bağlanacağı VPN sunucusunun IP adresini veya tam etki alanı adını sağlayın. Örnekler: **192.168.1.1**, **vpn.contoso.com**.
- **Kimlik doğrulama yöntemi** - Cihazların VPN sunucusuna kimliklerini nasıl doğrulayacaklarını seçin:
    - **Sertifikalar** - Bağlantının kimliğini doğrulamak için daha önce oluşturduğunuz SCEP veya PKCS sertifika profilini seçin. Sertifika profilleri hakkındaki diğer ayrıntılar için bkz. [Sertifikaları yapılandırma](how-to-configure-certificates.md).
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



<!--HONumber=Feb17_HO2-->

