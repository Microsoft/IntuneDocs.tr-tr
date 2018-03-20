---
title: "Microsoft Intune - Azure’da VPN ayarlarını görüntüleme | Microsoft Docs"
description: "Trafik kuralları, koşullu erişim ve Windows 10 cihazları ile Windows Holographic for Business cihazları için DNS ile ara sunucu ayarları da dahil olmak üzere Microsoft Intune'da sağlanan VPN ayarları, bunların ne için kullanıldığı ve ne yaptıkları hakkındaki bilgileri okuyun ve öğrenin."
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/8/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.reviewer: tycast
ms.custom: intune-azure
ms.openlocfilehash: 1c1ed2946782f92313aacec05a65a80b2704ddaa
ms.sourcegitcommit: 8a235b7af6ec3932c29a76d0b1aa481d983054bc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
---
# <a name="read-about-the-vpn-settings-in-intune"></a>Intune'daki VPN ayarları hakkındaki bilgileri okuyun

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune kullanarak VPN bağlantılarını yapılandırabilirsiniz. Bu makalede bu ayarlar, trafik kuralları, koşullu erişim ve DNS ile ara sunucu ayarları açıklanır.

Bu ayarlar şu cihazlarda geçerlidir:

- Windows 10 çalıştıran cihazlar
- Windows Holographic for Business çalıştıran cihazlar

Seçtiğiniz ayarlara bağlı olarak, değerlerden bazıları yapılandırılamayabilir.

## <a name="base-vpn-settings"></a>Temel VPN ayarları

- **Bağlantı adı**: Bu bağlantı için bir ad girin. Cihazlarındaki kullanılabilir VPN bağlantılarına göz atan son kullanıcılar bu adı görür.
- **Sunucular**: Cihazların bağlandığı bir veya birden çok VPN sunucusu ekleyin.
  - **Ekle**: Aşağıdaki bilgileri girebileceğiniz **Satır Ekle** öğesini açar:
    - **Açıklama**: Sunucu için **Contoso VPN sunucusu** gibi açıklayıcı bir ad girin.
    - **IP adresi veya FQDN**: Cihazların bağlanacağı VPN sunucusunun **192.168.1.1** veya **vpn.contoso.com** gibi IP adresini veya tam etki alanı adını girin.
    - **Varsayılan sunucu**: Bu sunucuyu, cihazların bağlantı oluşturmak için kullandığı varsayılan sunucu olarak etkinleştirir. Varsayılan sunucu olarak tek bir sunucu ayarlayın.
  - **İçeri Aktar**: Açıklama, IP adresi veya FQDN, Varsayılan sunucu biçiminde sunucu listesini içeren virgülle ayrılmış bir dosyaya göz atın. **Tamam**'ı seçerek bu sunucuları **Sunucular** listesine içeri aktarın.
  - **Dışarı aktar**: Sunucu listesini virgülle ayrılmış değerler (csv) dosyasına dışarı aktarır

**Bağlantı türü**: Aşağıdaki satıcı listesinden VPN bağlantı türünü seçin:

- **Otomatik**
- **Check Point Capsule VPN**
- **Citrix VPN**
- **SonicWALL Mobile Connect**
- **F5 Edge Client**
- **IKEv2**
- **L2TP**
- **PPTP**
- **Pulse Secure**

**Oturum açma grubu veya etki alanı** (yalnızca SonicWALL Mobile Connect): VPN profilinde bu özellik ayarlanamaz. Bunun yerine, `username@domain` veya `DOMAIN\username` biçimlerinde kullanıcı adıyla etki alanı girildiğinde Mobile Connect bu değeri ayrıştırır.

**Özel XML**/**EAP XML**: VPN bağlantısını yapılandıran özel XML komutlarını girin.

**Pulse Secure örneği:**

```
<pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>
```

**CheckPoint Mobile VPN örneği:**

```
<CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />
```

**SonicWALL Mobile Connect örneği:**

```
<MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>
```

**F5 Edge Client örneği:**

```
<f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>
```

Özel XML komutları yazma hakkında daha fazla bilgi için her bir üreticinin VPN belgelerine başvurun.

Özel EAP XML oluşturma hakkında daha fazla bilgi için bkz. [EAP yapılandırması](https://docs.microsoft.com/windows/client-management/mdm/eap-configuration).

**Bölünmüş tünel**: Trafiğe bağlı olarak hangi bağlantının kullanılacağına cihazların karar vermesini sağlamak için bu seçeneği **Etkinleştirin** veya **Devre Dışı Bırakın**. Örneğin, oteldeki bir kullanıcı çalışma dosyalarına erişmek için VPN bağlantısını, web’e göz atmak için ise otelin standart ağını kullanır.
- **Bu VPN bağlantısının tünel oluşturma rotalarını ayırma**: Üçüncü taraf VPN sağlayıcıları için isteğe bağlı rotalar ekleyin. Hedef önekini ve her birinin önek boyutunu girin.

## <a name="apps-and-traffic-rules"></a>Uygulamalar ve Trafik Kuralları

**VPN bağlantısını bu uygulamalarla kısıtlama**: Yalnızca belirli uygulamaların VPN bağlantısını kullanmasını istiyorsanız bu ayarı etkinleştirin.
**İlişkili Uygulamalar**: VPN bağlantısını otomatik olarak kullanan uygulamaların listesini girin. Uygulamanın türü uygulama tanımlayıcısını belirler. Bir evrensel uygulama için paket aile adını girin. Bir masaüstü uygulaması için söz konusu uygulamanın dosya yolunu girin.

>[!IMPORTANT]
>Uygulama başına VPN'ler için oluşturulan tüm uygulama listelerini güvenlik altına almanızı öneririz. Yetkisiz bir kullanıcı bu listede değişiklik yaparsa ve bunu uygulama başına VPN uygulama listesine aktarırsanız, erişimi olmaması gereken uygulamalara VPN erişimi yetkisi verme olasılığınız vardır. Uygulama listelerini güvenlik altına almanın yollarından biri, erişim denetim listesi (ACL) kullanmaktır.

**Bu VPN bağlantısının ağ trafiği kuralları**: VPN bağlantısı için hangi protokollerin, yerel ve uzak bağlantı noktasının ve adres aralıklarının etkinleştirileceğini seçin. Bir ağ trafiği kuralı oluşturmazsanız, bu durumda tüm protokoller, bağlantı noktaları ve adres aralıkları etkinleştirilir. Bir kural oluşturduktan sonra, VPN bağlantısı yalnızca bu kuralda veya ek kurallarda girdiğiniz protokolleri, bağlantı noktalarını ve adres aralıklarını kullanır.

## <a name="conditional-access"></a>Koşullu Erişim

**VPN bağlantısı için koşullu erişim**: İstemciden cihaz uyumluluk akışını etkinleştirir. Bu etkinleştirildiğinde VPN istemcisi, kimlik doğrulama için kullanmak üzere bir sertifika almak üzere Azure Active Directory ile iletişime geçmeye çalışır. VPN’in sertifika kimlik doğrulamasını kullanacak şekilde ayarlanmış olması ve VPN sunucusunun Azure Active Directory tarafından gönderilen sunucuya güvenmesi gerekir.

**Alternatif sertifika ile çoklu oturum açma (SSO)**: Cihaz uyumluluğu amacıyla Kerberos kimlik doğrulaması için VPN kimlik doğrulama sertifikasından farklı bir sertifika kullanın. Aşağıdaki ayarlarla sertifikayı girin:

- **Genişletilmiş anahtar kullanımı**: Genişletilmiş anahtar kullanımı (EKU) için ad
- **Nesne Tanımlayıcısı**: EKU için nesne tanımlayıcısı
- **Sertifikayı veren karması**: SSO sertifikası için parmak izi

## <a name="dns-settings"></a>DNS Ayarları

**Bu VPN bağlantısının DNS adları ve sunucuları**: Bağlantı kurulduktan sonra VPN bağlantısının hangi DNS sunucularını kullanacağını seçin.
Her sunucu için şunları girin:
- **DNS Adı**
- **DNS Sunucusu**
- **Proxy**

## <a name="proxy-settings"></a>Proxy ayarları

- **Proxy ayarlarını otomatik olarak algıla**: VPN sunucunuz bağlantı için proxy sunucusu gerektiriyorsa, cihazların bağlantı ayarlarını otomatik olarak algılamasını isteyip istemediğinizi seçin.
- **Otomatik yapılandırma betiği**: Proxy sunucusunu yapılandırmak için bir dosya kullanın. Yapılandırma dosyasını içeren **Proxy sunucu URL'sini** (örneğin, `http://proxy.contoso.com`) girin.
- **Proxy sunucusu kullan**: Proxy sunucusu ayarlarını el ile girmek için bu seçeneği etkinleştirin.
  - **Adres**: Proxy sunucusu adresini (IP adresi olarak) girin
  - **Bağlantı noktası numarası**: Proxy sunucusuyla ilişkilendirilmiş bağlantı noktası numarasını girin
- **Yerel adresler için proxy atlama**: VPN sunucunuz bağlantı için proxy sunucusu gerektiriyorsa ve girdiğiniz yerel adreslerde proxy sunucusunu kullanmak istemiyorsanız, bu ayarı seçin.
