---
title: "Windows 8.1 cihazları için Intune VPN ayarları"
titleSuffix: Intune on Azure
description: "Windows 8.1 cihazlarında VPN bağlantılarını yapılandırmak için kullanabileceğiniz Intune ayarlarını öğrenin.\""
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d851a8900ae1e164cb22f1878b352c3e90096f73
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="vpn-settings-for-windows-81-devices-in-microsoft-intune"></a>Microsoft Intune’da Windows 8.1 cihazları için VPN ayarları

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Seçtiğiniz ayarlara bağlı olarak, aşağıdaki listede yer alan değerlerden bazıları yapılandırılabilir değildir.

## <a name="base-vpn-settings"></a>Temel VPN ayarları


- **Tüm ayarları yalnızca Windows 8.1’e uygula** - Bu, klasik Intune portalında yapılandırabileceğiniz bir ayardır. Azure Portal’da bu ayar değiştirilemez. **Yapılandırıldı** olarak ayarlanırsa, tüm ayarlar yalnızca Windows 8.1 cihazlarına uygulanır. **Yapılandırılmadı** olarak ayarlanırsa, bu ayarlar Windows 10 cihazlarına da uygulanır.
- **Bağlantı adı** - Bu bağlantı için bir ad girin. Cihazlarındaki kullanılabilir VPN bağlantılarına göz atan son kullanıcılar bu adı görür.
- **Sunucular** - Cihazların bağlanacağı bir veya birden çok VPN sunucusu ekleyin.
    - **Ekle** - Aşağıdaki bilgileri belirtebileceğiniz **Satır Ekle** dikey penceresini açar:
        - **Açıklama** - Sunucu için **Contoso VPN sunucusu** gibi açıklayıcı bir ad belirtin.
        - **IP adresi veya FQDN** - Cihazların bağlanacağı VPN sunucusunun IP adresini veya tam etki alanı adını sağlayın. Örnekler: **192.168.1.1**, **vpn.contoso.com**.
        - **Varsayılan sunucu** - Bu sunucuyu cihazların bağlantı oluşturmak için kullanacağı varsayılan sunucu olarak etkinleştirir. Varsayılan sunucu olarak tek bir sunucu ayarladığınızdan emin olun.
    - **İçeri aktar** - Açıklama, IP adresi veya FQDN, Varsayılan sunucu biçiminde virgülle ayrılmış bir sunucu listesi içeren bir dosyaya göz atın. Bunları **Sunucular** listesine içeri aktarmak için **Tamam**’ı seçin.
    - **Dışarı aktar** - Sunucu listesini virgülle ayrılmış değerler (csv) dosyasına aktarır.

- **Bağlantı türü** - Aşağıdaki satıcı listesinden VPN bağlantı türünü seçin:
- **Check Point Capsule VPN**
- **Dell SonicWALL Mobile Connect**
- **F5 Edge Client**
- **Pulse Secure**

<!--- **Fingerprint** (Check Point Capsule VPN only) - Specify a string (for example, "Contoso Fingerprint Code") that will be used to verify that the VPN server can be trusted. A fingerprint can be sent to the client so it knows to trust any server that presents the same fingerprint when connecting. If the device doesn’t already have the fingerprint, it will prompt the user to trust the VPN server that they are connecting to while showing the fingerprint. (The user manually verifies the fingerprint and chooses **trust** to connect.) --->

- **Oturum açma grubu veya etki alanı** (yalnızca Dell SonicWALL Mobile Connect) - Bağlanmak istediğiniz oturum açma grubu veya etki alanı adını belirtin.

- **Rol** (yalnızca Pulse Secure) - Bu bağlantıya erişimi olan kullanıcı rolünün adını belirtin. Bir kullanıcı rolü, kişisel ayarları ve seçenekleri tanımlar, belirli erişim özelliklerini etkinleştirir veya devre dışı bırakır.

- **Bölge** (yalnızca Pulse Secure) - Kullanmak istediğiniz kimlik doğrulaması bölgesinin adını belirtin. Bir kimlik doğrulaması bölgesi, Pulse Secure bağlantı türü tarafından kullanılan kimlik doğrulaması kaynakları gruplandırmasıdır.


- **Özel XML** - VPN bağlantısını yapılandıran özel XML komutlarını belirtin.

**Pulse Secure örneği:**

```
    <pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>

```

**CheckPoint Mobile VPN örneği:**
```
    <CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />

```

**Dell SonicWALL Mobile Connect örneği:**
```
    <MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>

```

**F5 Edge Client örneği:**

```
    <f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>

```

Özel XML komutları yazma hakkında daha fazla bilgi için her bir üreticinin VPN belgelerine başvurun.


## <a name="proxy-settings"></a>Proxy ayarları

- **Proxy ayarlarını otomatik olarak algıla** - VPN sunucunuz bağlantı için proxy sunucusu gerektiriyorsa, cihazların bağlantı ayarlarını otomatik olarak algılamasını isteyip istemediğinizi belirtin. Daha fazla bilgi için Windows Server belgelerinize bakın.
- **Otomatik yapılandırma betiği** - Proxy sunucusunu yapılandırmak için bir dosya kullanın. Yapılandırma dosyasını içeren **Proxy sunucu URL’si** (örneğin **http://proxy.contoso.com**) değerini girin.
- **Proxy sunucusu kullan** - Proxy sunucusu ayarlarını el ile girmek istiyorsanız bu seçeneği etkinleştirin.
    - **Adres** - Proxy sunucusu adresini (IP adresi olarak) girin.
    - **Bağlantı noktası numarası** - Proxy sunucusuyla ilişkilendirilmiş bağlantı noktası numarasını girin.
- **Yerel adresler için proxy atlama** - VPN sunucunuz bağlantı için proxy sunucusu gerektiriyorsa ve belirttiğiniz yerel adresler için proxy sunucusunu kullanmak istemiyorsanız, bu seçeneği belirtin. Daha fazla bilgi için Windows Server belgelerinize bakın.
