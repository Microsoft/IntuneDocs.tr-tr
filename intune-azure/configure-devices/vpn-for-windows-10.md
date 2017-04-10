---
title: "Windows 10 cihazları için Intune VPN ayarları"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Windows 10 cihazlarında VPN bağlantılarını yapılandırmak için kullanabileceğiniz Intune ayarlarını öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 495e4ed6-b2ef-47cc-a110-13fa9b5f85a6
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 87004408ddcb07571507f68d5b9925b7e475282a
ms.lasthandoff: 02/18/2017


---

# <a name="vpn-settings-for-windows-10-devices-in-microsoft-intune"></a>Microsoft Intune’daki Windows 10 cihazlar için VPN ayarları

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Seçtiğiniz ayarlara bağlı olarak, aşağıdaki listede yer alan değerlerden bazıları yapılandırılabilir değildir.


## <a name="base-vpn-settings"></a>Temel VPN ayarları


- **Bağlantı adı** - Bu bağlantı için bir ad girin. Cihazlarındaki kullanılabilir VPN bağlantılarına göz atan son kullanıcılar bu adı görür.
- **Sunucular** - Cihazların bağlanacağı bir veya birden çok VPN sunucusu ekleyin.
    - **Ekle** - Aşağıdaki bilgileri belirtebileceğiniz **Satır Ekle** dikey penceresini açar:
        - **Açıklama** - Sunucu için **Contoso VPN sunucusu** gibi açıklayıcı bir ad belirtin.
        - **IP adresi veya FQDN** - Cihazların bağlanacağı VPN sunucusunun IP adresini veya tam etki alanı adını sağlayın. Örnekler: **192.168.1.1**, **vpn.contoso.com**.
        - **Varsayılan sunucu** - Bu sunucuyu cihazların bağlantı oluşturmak için kullanacağı varsayılan sunucu olarak etkinleştirir. Varsayılan sunucu olarak tek bir sunucu ayarladığınızdan emin olun.
    - **İçeri aktar** - Açıklama, IP adresi veya FQDN, Varsayılan sunucu biçiminde virgülle ayrılmış bir sunucu listesi içeren bir dosyaya göz atın. Bunları **Sunucular** listesine içeri aktarmak için **Tamam**’ı seçin.
    - **Dışarı aktar** - Sunucu listesini virgülle ayrılmış değerler (csv) dosyasına aktarır.

**Bağlantı türü** - Aşağıdaki satıcı listesinden VPN bağlantı türünü seçin:
- **Pulse Secure**
- **F5 Edge Client**
- **Dell SonicWALL Mobile Connect**
- **Check Point Capsule VPN**
- **Otomatik**
- **IKEv2**
- **L2TP**
- **PPTP**

**Oturum açma grubu veya etki alanı** (yalnızca Dell SonicWALL Mobile Connect) - Bağlanmak istediğiniz oturum açma grubu veya etki alanı adını belirtin.

**Özel XML**/**EAP XML** - VPN bağlantısını yapılandıran özel XML komutlarını belirtin.

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

**Bölünmüş tünel** - Trafiğe bağlı olarak hangi bağlantının kullanılacağına cihazların karar vermesini sağlayan bu seçeneği **etkinleştirin** veya **devre dışı bırakın**. Örneğin, oteldeki bir kullanıcı çalışma dosyalarına erişmek için VPN bağlantısını, ama normal web’e göz atmak için otelin standart ağını kullanır.
- **Bu VPN bağlantısının tünel oluşturma rotalarını ayırma** - Üçüncü taraf VPN sağlayıcıları için isteğe bağlı rotalar ekleyin. Hedef önekini ve her birinin önek boyutunu belirtin.

## <a name="apps-and-traffic-rules"></a>Uygulamalar ve Trafik Kuralları

**VPN bağlantısını bu uygulamalarla kısıtlama** - Yalnızca belirttiğiniz uygulamaların VPN bağlantısını kullanmasını istiyorsanız bu seçeneği etkinleştirin.
**İlişkili Uygulamalar** - VPN bağlantısını otomatik olarak kullanacak uygulamaların listesini sağlayın. Uygulamanın türü uygulama tanımlayıcısını belirler. Bir evrensel uygulama için paket aile adını belirtin. Bir masaüstü uygulaması için söz konusu uygulamanın dosya yolunu belirtin.

>[!IMPORTANT]
>Uygulama başına VPN yapılandırmasında kullanılması için derlediğiniz tüm uygulama listelerini güvenlik altına almanızı öneririz. Yetkisiz bir kullanıcı listenizde değişiklik yaparsa ve bunu uygulama başına VPN uygulama listesine aktarırsanız, erişimi olmaması gereken uygulamalara VPN erişimi yetkisi verme olasılığınız vardır. Uygulama listelerini güvenlik altına almanın yollarından biri, erişim denetim listesi (ACL) kullanmaktır.

**Bu VPN bağlantısının ağ trafiği kuralları** - VPN bağlantısı için hangi protokollerin, yerel ve uzak bağlantı noktasının ve adres aralıklarının etkinleştirileceğini seçin. Bir ağ trafiği kuralı oluşturmazsanız, tüm protokoller, bağlantı noktaları ve adres aralıkları etkinleştirilir. Bir kural oluşturduktan sonra, VPN bağlantısı yalnızca bu kuralda veya ek kurallarda belirttiğiniz protokolleri, bağlantı noktalarını ve adres aralıklarını kullanır.


## <a name="conditional-access"></a>Koşullu Erişim

**Bu VPN bağlantısı için koşullu erişim** -
**Alternatif sertifikayla çoklu oturum açma (SSO)** -
**Genişletilmiş anahtar kullanımı** -
**Veren karması** -

## <a name="dns-settings"></a>DNS Ayarları

**Bu VPN bağlantısının DNS adları ve sunucuları** - Bağlantı kurulduktan sonra VPN bağlantısının hangi DNS sunucularını kullanacağını seçin.
Her sunucu için. şunları belirtin:
- **DNS Adı**
- **DNS Sunucusu**
- **Proxy**

## <a name="proxy-settings"></a>Proxy ayarları

- **Proxy ayarlarını otomatik olarak algıla** - VPN sunucunuz bağlantı için proxy sunucusu gerektiriyorsa, cihazların bağlantı ayarlarını otomatik olarak algılamasını isteyip istemediğinizi belirtin. Daha fazla bilgi için Windows Server belgelerinize bakın.
- **Otomatik yapılandırma betiği** - Proxy sunucusunu yapılandırmak için bir dosya kullanın. Yapılandırma dosyasını içeren **Proxy sunucu URL’si** (örneğin **http://proxy.contoso.com**) değerini girin.
- **Proxy sunucusu kullan** - Proxy sunucusu ayarlarını el ile girmek istiyorsanız bu seçeneği etkinleştirin.
    - **Adres** - Proxy sunucusu adresini (IP adresi olarak) girin.
    - **Bağlantı noktası numarası** - Proxy sunucusuyla ilişkilendirilmiş bağlantı noktası numarasını girin.
- **Yerel adresler için proxy atlama** - VPN sunucunuz bağlantı için proxy sunucusu gerektiriyorsa ve belirttiğiniz yerel adresler için proxy sunucusunu kullanmak istemiyorsanız, bu seçeneği belirtin. Daha fazla bilgi için Windows Server belgelerinize bakın.

