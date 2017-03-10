---
title: "Windows Phone 8.1 cihazları için Intune VPN ayarları"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Windows Phone 8.1 cihazlarında VPN bağlantılarını yapılandırmak için kullanabileceğiniz Intune ayarlarını öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c1a9053f-02a7-4735-bc0d-fe4573b31ed4
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 2fe54f4d97c28825f06d40ec47a8a9dc40da2554
ms.lasthandoff: 02/18/2017


---

# <a name="vpn-settings-for-windows-phone-81-devices-in-microsoft-intune"></a>Microsoft Intune’da Windows Phone 8.1 cihazları için VPN ayarları

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Seçtiğiniz ayarlara bağlı olarak, aşağıdaki listede yer alan değerlerden bazıları yapılandırılabilir değildir.

## <a name="base-vpn-settings"></a>Temel VPN ayarları

- **Tüm ayarları yalnızca Windows Phone 8.1’e uygula** - Bu, klasik Intune portalında yapılandırabileceğiniz bir ayardır. Azure Portal’da bu ayar değiştirilemez. **Yapılandırıldı** olarak ayarlanırsa, tüm ayarlar yalnızca Windows Phone 8.1 cihazlarına uygulanır. **Yapılandırılmadı** olarak ayarlanırsa, bu ayarlar Windows 10 Mobile cihazlarına da uygulanır.
- **Bağlantı adı** - Bu bağlantı için bir ad girin. Cihazında kullanılabilir VPN bağlantılarına göz atan son kullanıcılar bu adı görür.
- **Kimlik doğrulama yöntemi** - Cihazların VPN sunucusuna kimliklerini nasıl doğrulayacaklarını seçin:
    - **Sertifikalar** - **Kimlik doğrulama sertifikası**’nın altında, bağlantının kimliğini doğrulamak için daha önce oluşturduğunuz SCEP veya PKCS sertifika profilini seçin. Sertifika profilleri hakkındaki diğer ayrıntılar için bkz. [Sertifikaları yapılandırma](how-to-configure-certificates.md).
    - **Kullanıcı adı ve parola** - Son kullanıcıların VPN sunucusunda oturum açmak için kullanıcı adı ve parola sağlaması gerekir.
- **Sunucular** - Cihazların bağlanacağı bir veya birden çok VPN sunucusu ekleyin.
    - **Ekle** - Aşağıdaki bilgileri belirtebileceğiniz **Satır Ekle** dikey penceresini açar:
        - **Açıklama** - Sunucu için **Contoso VPN sunucusu** gibi açıklayıcı bir ad belirtin.
        - **IP adresi veya FQDN** - Cihazların bağlanacağı VPN sunucusunun IP adresini veya tam etki alanı adını sağlayın. Örnekler: **192.168.1.1**, **vpn.contoso.com**.
        - **Varsayılan sunucu** - Bu sunucuyu cihazların bağlantı oluşturmak için kullanacağı varsayılan sunucu olarak etkinleştirir. Varsayılan sunucu olarak tek bir sunucu ayarladığınızdan emin olun.
    - **İçeri aktar** - Açıklama, IP adresi veya FQDN, Varsayılan sunucu biçiminde virgülle ayrılmış bir sunucu listesi içeren bir dosyaya göz atın. Bunları **Sunucular** listesine içeri aktarmak için **Tamam**’ı seçin.
    - **Dışarı aktar** - Sunucu listesini virgülle ayrılmış değerler (csv) dosyasına aktarır.

- **Şirket Wi-Fi ağında VPN'i atlama** - Bu seçeneği, cihaz şirket Wi-Fi ağına bağlıyken VPN bağlantısının kullanılmayacağını belirtmek için etkinleştirin.
- **Ev Wi-Fi ağında VPN'i atlama** - Bu seçeneği, cihaz bir ev Wi-Fi ağına bağlıyken VPN bağlantısının kullanılmayacağını belirtmek için etkinleştirin.

- **Bağlantı türü** - Aşağıdaki satıcı listesinden VPN bağlantı türünü seçin:
    - **Check Point Capsule VPN**
    - **Dell SonicWALL Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**

- **Oturum açma grubu veya etki alanı** (yalnızca Dell SonicWALL Mobile Connect) - Bağlanmak istediğiniz oturum açma grubu veya etki alanı adını belirtin.
- **Rol** (yalnızca Pulse Secure) - Bu bağlantıya erişimi olan kullanıcı rolünün adını belirtin. Bir kullanıcı rolü, kişisel ayarları ve seçenekleri tanımlar, belirli erişim özelliklerini etkinleştirir veya devre dışı bırakır.
- **Bölge** (yalnızca Pulse Secure) - Kullanmak istediğiniz kimlik doğrulaması bölgesinin adını belirtin. Bir kimlik doğrulaması bölgesi, Pulse Secure bağlantı türü tarafından kullanılan kimlik doğrulaması kaynakları gruplandırmasıdır.

- **DNS soneki arama listesi** - Bir veya birden çok DNS soneki **ekleyin**. Bir web sitesine kısa ad kullanarak bağlanılırken, belirttiğiniz her DNS soneki aranır. Örneğin, **domain1.contoso.com** ve **domain2.contoso.com** DNS son eklerini belirtip **http://mywebsite** URL’sini ziyaret ettiğinizde **http://mywebsite.domain1.contoso.com** ve **http://mywebsite.domain2.contoso.com** URL’leri aranır.

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

- **Bölünmüş tünel** - Trafiğe bağlı olarak hangi bağlantının kullanılacağına cihazların karar vermesini sağlayan bu seçeneği **etkinleştirin** veya **devre dışı bırakın**. Örneğin, oteldeki bir kullanıcı çalışma dosyalarına erişmek için VPN bağlantısını, ama normal web’e göz atmak için otelin standart ağını kullanır.




## <a name="proxy-settings"></a>Proxy ayarları

- **Proxy ayarlarını otomatik olarak algıla** - VPN sunucunuz bağlantı için proxy sunucusu gerektiriyorsa, cihazların bağlantı ayarlarını otomatik olarak algılamasını isteyip istemediğinizi belirtin. Daha fazla bilgi için Windows Server belgelerinize bakın.
- **Otomatik yapılandırma betiği** - Proxy sunucusunu yapılandırmak için bir dosya kullanın. Yapılandırma dosyasını içeren **Proxy sunucu URL’si** (örneğin **http://proxy.contoso.com**) değerini girin.
- **Proxy sunucusu kullan** - Proxy sunucusu ayarlarını el ile girmek istiyorsanız bu seçeneği etkinleştirin.
    - **Adres** - Proxy sunucusu adresini (IP adresi olarak) girin.
    - **Bağlantı noktası numarası** - Proxy sunucusuyla ilişkilendirilmiş bağlantı noktası numarasını girin.
- **Yerel adresler için proxy atlama** - VPN sunucunuz bağlantı için proxy sunucusu gerektiriyorsa ve belirttiğiniz yerel adresler için proxy sunucusunu kullanmak istemiyorsanız, bu seçeneği belirtin. Daha fazla bilgi için Windows Server belgelerinize bakın.

