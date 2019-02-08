---
title: Windows 8.1 cihazları için Microsoft Intune VPN ayarları
titleSuffix: ''
description: Windows 8.1 çalıştıran cihazlarda VPN bağlantılarını yapılandırmak için kullanabileceğiniz Intune ayarları hakkında bilgi edinin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1ef2fd878a46e7a934dbb6e868356375883bc584
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55836889"
---
# <a name="configure-vpn-settings-in-microsoft-intune-for-devices-running-windows-81"></a>Windows 8.1 çalıştıran cihazlar için Microsoft Intune'da VPN ayarlarını yapılandırın

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bu makale, Windows 8.1 çalıştıran cihazlarda VPN bağlantılarını yapılandırmak için kullanabileceğiniz Intune ayarları hakkında bilgi sağlar.

Seçtiğiniz ayarlara bağlı olarak, aşağıdaki listede yer alan değerlerden bazıları yapılandırılamaz.

## <a name="base-vpn-settings"></a>Temel VPN ayarları


- **Tüm ayarları yalnızca Windows 8.1’e uygula** - Bu, klasik Intune portalında yapılandırabileceğiniz bir ayardır. Azure Portal’da bu ayar değiştirilemez. **Yapılandırıldı** olarak ayarlanırsa, tüm ayarlar yalnızca Windows 8.1 cihazlarına uygulanır. **Yapılandırılmadı** olarak ayarlanırsa, bu ayarlar Windows 10 cihazlarına da uygulanır.
- **Bağlantı adı** - Bu bağlantı için bir ad girin. Cihazlarındaki kullanılabilir VPN bağlantılarına göz atan kullanıcılar bu adı görür.
- **Sunucular** - Cihazların bağlandığı bir veya birden çok VPN sunucusu ekleyin.
    - **Ekle** - Aşağıdaki bilgileri belirtebileceğiniz **Satır Ekle** sayfasını açar:
        - **Açıklama** - Sunucu için **Contoso VPN sunucusu** gibi açıklayıcı bir ad belirtin.
        - **IP adresi veya FQDN** - Cihazların bağlanacağı VPN sunucusunun IP adresini veya tam etki alanı adını sağlayın. Örnekler: **192.168.1.1**, **vpn.contoso.com**.
        - **Varsayılan sunucu** - Bu sunucuyu, cihazların bağlantı oluşturmak için kullandığı varsayılan sunucu olarak etkinleştirir. Varsayılan sunucu olarak tek bir sunucu ayarladığınızdan emin olun.
    - **İçeri aktar** - Açıklama, IP adresi veya FQDN, Varsayılan sunucu biçiminde virgülle ayrılmış bir sunucu listesi içeren bir dosyaya göz atın. Bunları **Sunucular** listesine içeri aktarmak için **Tamam**’ı seçin.
    - **Dışarı aktar** - Sunucu listesini virgülle ayrılmış değerler (csv) dosyasına aktarır.

- **Bağlantı türü** - Aşağıdaki satıcı listesinden VPN bağlantı türünü seçin:
- **Check Point Capsule VPN**
- **SonicWall Mobile Connect**
- **F5 Edge Client**
- **Pulse Secure**

<!--- **Fingerprint** (Check Point Capsule VPN only) - Specify a string (for example, "Contoso Fingerprint Code") that will be used to verify that the VPN server can be trusted. A fingerprint can be sent to the client so it knows to trust any server that presents the same fingerprint when connecting. If the device doesn’t already have the fingerprint, it will prompt the user to trust the VPN server that they are connecting to while showing the fingerprint. (The user manually verifies the fingerprint and chooses **trust** to connect.) --->

- **Oturum açma grubu veya etki alanı** (yalnızca SonicWall Mobile Connect) - Bağlanmak istediğiniz oturum açma grubu veya etki alanı adını belirtin.

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

**SonicWall Mobile Connect örneği:**
```
    <MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>
```

**F5 Edge Client örneği:**

```
    <f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>
```

Daha fazla bilgi için her üreticinin özel XML komutları yazma hakkındaki VPN belgelerine başvurun.


## <a name="proxy-settings"></a>Proxy ayarları

- **Proxy ayarlarını otomatik olarak algıla** - VPN sunucunuz bağlantı için proxy sunucusu gerektiriyorsa, cihazların bağlantı ayarlarını otomatik olarak algılamasını isteyip istemediğinizi belirtin. Daha fazla bilgi için Windows Server belgelerinize bakın.
- **Otomatik yapılandırma betiği** - Proxy sunucusunu yapılandırmak için bir dosya kullanın. Girin **Proxy sunucu URL'si** yapılandırma dosyasını içeren. Örneğin, şunu girin: `http://proxy.contoso.com`.
- **Proxy sunucusu kullan** - Proxy sunucusu ayarlarını el ile girmek istiyorsanız bu seçeneği etkinleştirin.
    - **Adres** - Proxy sunucusu adresini (IP adresi olarak) girin.
    - **Bağlantı noktası numarası** - Proxy sunucusuyla ilişkilendirilmiş bağlantı noktası numarasını girin.
- **Yerel adresler için proxy atlama** - VPN sunucunuz bağlantı için proxy sunucusu gerektiriyorsa ve belirttiğiniz yerel adresler için proxy sunucusunu kullanmak istemiyorsanız, bu seçeneği belirtin. Daha fazla bilgi için Windows Server belgelerinize bakın.
