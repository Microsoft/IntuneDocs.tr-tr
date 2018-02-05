---
title: "Windows 10 cihazları için Intune VPN ayarları"
titlesuffix: Azure portal
description: "Windows 10 cihazlarında VPN bağlantılarını yapılandırmak için kullanabileceğiniz Intune ayarlarını öğrenin.\""
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 1/26/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e7bd1d15276f93b50a22c7b47de6bd1eb619264a
ms.sourcegitcommit: 4509039cbfd4d450324a3475fb5841906720baa1
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2018
---
# <a name="vpn-settings-for-windows-10-devices-in-microsoft-intune"></a>Microsoft Intune’daki Windows 10 cihazlar için VPN ayarları

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Seçtiğiniz ayarlara bağlı olarak, aşağıdaki listede yer alan değerlerden bazıları yapılandırılamayacaktır.


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
- **Otomatik**
- **Check Point Capsule VPN**
- **Citrix VPN**
- **Dell SonicWALL Mobile Connect**
- **F5 Edge Client**
- **IKEv2**
- **L2TP**
- **PPTP**
- **Pulse Secure**


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

Özel EAP XML oluşturma hakkında daha fazla bilgi için bkz. [EAP yapılandırması](https://docs.microsoft.com/en-us/windows/client-management/mdm/eap-configuration).

**Bölünmüş tünel** - Trafiğe bağlı olarak hangi bağlantının kullanılacağına cihazların karar vermesini sağlayan bu seçeneği **etkinleştirin** veya **devre dışı bırakın**. Örneğin, oteldeki bir kullanıcı çalışma dosyalarına erişmek için VPN bağlantısını, ama normal web’e göz atmak için otelin standart ağını kullanır.
- **Bu VPN bağlantısının tünel oluşturma rotalarını ayırma** - Üçüncü taraf VPN sağlayıcıları için isteğe bağlı rotalar ekleyin. Hedef önekini ve her birinin önek boyutunu belirtin.

## <a name="apps-and-traffic-rules"></a>Uygulamalar ve Trafik Kuralları

**VPN bağlantısını bu uygulamalarla kısıtlama** - Yalnızca belirttiğiniz uygulamaların VPN bağlantısını kullanmasını istiyorsanız bu seçeneği etkinleştirin.
**İlişkili Uygulamalar** - VPN bağlantısını otomatik olarak kullanacak uygulamaların listesini sağlayın. Uygulamanın türü uygulama tanımlayıcısını belirler. Bir evrensel uygulama için paket aile adını belirtin. Bir masaüstü uygulaması için söz konusu uygulamanın dosya yolunu belirtin.

>[!IMPORTANT]
>Uygulama başına VPN yapılandırmasında kullanılması için derlediğiniz tüm uygulama listelerini güvenlik altına almanızı öneririz. Yetkisiz bir kullanıcı listenizde değişiklik yaparsa ve bunu uygulama başına VPN uygulama listesine aktarırsanız, erişimi olmaması gereken uygulamalara VPN erişimi yetkisi verme olasılığınız vardır. Uygulama listelerini güvenlik altına almanın yollarından biri, erişim denetim listesi (ACL) kullanmaktır.

**Bu VPN bağlantısının ağ trafiği kuralları** - VPN bağlantısı için hangi protokollerin, yerel ve uzak bağlantı noktasının ve adres aralıklarının etkinleştirileceğini seçin. Bir ağ trafiği kuralı oluşturmazsanız, tüm protokoller, bağlantı noktaları ve adres aralıkları etkinleştirilir. Bir kural oluşturduktan sonra, VPN bağlantısı yalnızca bu kuralda veya ek kurallarda belirttiğiniz protokolleri, bağlantı noktalarını ve adres aralıklarını kullanır.


## <a name="conditional-access"></a>Koşullu Erişim

**VPN bağlantısı için koşullu erişim** - İstemciden cihaz uyumluluk akışını etkinleştirir. Bu etkinleştirildiğinde VPN istemcisi, kimlik doğrulama için kullanmak üzere bir sertifika almak üzere Azure Active Directory ile iletişime geçmeye çalışır. VPN’in sertifika kimlik doğrulamasını kullanacak şekilde ayarlanmış olması ve VPN sunucusunun Azure Active Directory tarafından gönderilen sunucuya güvenmesi gerekir.

**Alternatif sertifika ile çoklu oturum açma (SSO)** - Cihaz uyumluluğu amacıyla Kerberos kimlik doğrulaması için VPN kimlik doğrulama sertifikasından farklı bir sertifika kullanın. Aşağıdaki ayarlarla sertifikayı belirtin: 

- **Genişletilmiş anahtar kullanımı** - Genişletilmiş anahtar kullanımı (EKU) için ad.
- **Nesne Tanımlayıcısı** - EKU için nesne tanımlayıcısı.
- **Sertifikayı veren karması** - SSO sertifikası için parmak izi.

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
