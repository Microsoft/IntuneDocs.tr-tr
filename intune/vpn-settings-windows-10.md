---
title: Microsoft Intune - Azure’da Windows 10 VPN ayarları | Microsoft Docs
description: Trafik kuralları, koşullu erişim ve Windows 10 cihazları ile Windows Holographic for Business cihazları için DNS ile ara sunucu ayarları da dahil olmak üzere Microsoft Intune'da sağlanan VPN ayarları, bunların ne için kullanıldığı ve ne yaptıkları hakkındaki bilgileri okuyun ve öğrenin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 8/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.reviewer: tycast
ms.custom: intune-azure
ms.openlocfilehash: 0b064c6f0eaa67157c5c50ddad3a8fd863295b8b
ms.sourcegitcommit: 4d314df59747800169090b3a870ffbacfab1f5ed
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/30/2018
ms.locfileid: "43312859"
---
# <a name="windows-10-vpn-settings-in-intune"></a>Intune'da Windows 10 VPN ayarları

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune kullanarak VPN bağlantılarını yapılandırabilirsiniz. Bu makalede bu ayarlar, trafik kuralları, koşullu erişim ve DNS ile ara sunucu ayarları açıklanır.

Bu ayarlar şu cihazlarda geçerlidir:

- Windows 10 çalıştıran cihazlar
- Windows Holographic for Business çalıştıran cihazlar

Seçtiğiniz ayarlara bağlı olarak, değerlerden bazıları yapılandırılamayabilir.

## <a name="base-vpn-settings"></a>Temel VPN ayarları

- **Bağlantı adı**: Bu bağlantı için bir ad girin. Cihazlarındaki kullanılabilir VPN bağlantılarına göz atan son kullanıcılar bu adı görür.
- **Sunucular**: Cihazların bağlandığı bir veya birden çok VPN sunucusu ekleyin. Sunucu eklerken aşağıdaki bilgileri girersiniz:
  - **Açıklama**: Sunucu için **Contoso VPN sunucusu** gibi açıklayıcı bir ad girin.
  - **IP adresi veya FQDN**: Cihazların bağlanacağı VPN sunucusunun **192.168.1.1** veya **vpn.contoso.com** gibi IP adresini veya tam etki alanı adını girin.
  - **Varsayılan sunucu**: Bu sunucuyu, cihazların bağlantı oluşturmak için kullandığı varsayılan sunucu olarak etkinleştirir. Varsayılan sunucu olarak tek bir sunucu ayarlayın.
  - **İçeri Aktar**: Açıklama, IP adresi veya FQDN, Varsayılan sunucu biçiminde sunucu listesini içeren virgülle ayrılmış bir dosyaya göz atın. **Tamam**'ı seçerek bu sunucuları **Sunucular** listesine içeri aktarın.
  - **Dışarı aktar**: Sunucu listesini virgülle ayrılmış değerler (csv) dosyasına dışarı aktarır

- **Dahili DNS ile IP adresi kaydetme** Windows 10 VPN profilinin dahili DNS ile VPN arabirimine atanmış IP adresini dinamik olarak kaydetmek için **Etkinleştir** olarak ayarlayın veya IP adreslerini dinamik olarak kaydetmek istemiyorsanız **Devre Dışı Bırak** olarak ayarlayın.

- **Bağlantı türü**: Aşağıdaki satıcı listesinden VPN bağlantı türünü seçin:

  - **Pulse Secure**
  - **F5 Edge Client**
  - **SonicWALL Mobile Connect**
  - **Check Point Capsule VPN**
  - **Citrix**
  - **Palo Alto Networks GlobalProtect**
  - **Otomatik**
  - **IKEv2**
  - **L2TP**
  - **PPTP**

  VPN bağlantı türünü seçtiğinizde, aşağıdaki ayarları belirtmeniz de istenebilir:  
    - **Her Zaman Açık**: Aşağıdaki durumlar oluştuğunda VPN bağlantısına otomatik olarak bağlanmak için etkinleştirin: 
      - Kullanıcılar cihazlarında oturum açtığında
      - Cihazdaki ağ değiştiğinde
      - Cihaz ekranı kapandıktan sonra yeniden açıldığında 

    - **Kimlik doğrulama yöntemi**: Kullanıcıların VPN sunucusunda nasıl kimlik doğrulaması yapmasını istediğinizi seçin. **Sertifikaların** kullanılması sıfır temaslı deneyim, isteğe bağlı VPN ve uygulama başına VPN gibi iyileştirilmiş özellikler sağlar.
    - **Her oturum açışta kimlik bilgilerini hatırla**: Kimlik doğrulama bilgilerini önbelleğe almak için bunu seçin.
    - **Özel XML**: VPN bağlantısını yapılandıran tüm özel XML komutlarını girin.
    - **EAP Xml**: VPN bağlantısını yapılandıran tüm EAP XML komutlarını girin

#### <a name="pulse-secure-example"></a>Pulse Secure örneği

```
<pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>
```

#### <a name="f5-edge-client-example"></a>F5 Edge Client örneği

```
<f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>
```

#### <a name="sonicwall-mobile-connect-example"></a>SonicWALL Mobile Connect örneği
**Oturum açma grubu veya etki alanı**: VPN profilinde bu özellik ayarlanamaz. Bunun yerine, `username@domain` veya `DOMAIN\username` biçimlerinde kullanıcı adıyla etki alanı girildiğinde Mobile Connect bu değeri ayrıştırır.

Örnek:

```
<MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>
```

#### <a name="checkpoint-mobile-vpn-example"></a>CheckPoint Mobile VPN örneği

```
<CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />
```

#### <a name="writing-custom-xml"></a>Özel XML yazma
Özel XML komutları yazma hakkında daha fazla bilgi için her bir üreticinin VPN belgelerine başvurun.

Özel EAP XML oluşturma hakkında daha fazla bilgi için bkz. [EAP yapılandırması](https://docs.microsoft.com/windows/client-management/mdm/eap-configuration).

## <a name="apps-and-traffic-rules"></a>Uygulamalar ve Trafik Kuralları

- **WIP veya uygulamaları bu VPN ile ilişkilendir**: Yalnızca bazı uygulamaların VPN bağlantısını kullanmasını istiyorsanız bu ayarı etkinleştirin. Seçenekleriniz şunlardır:

  - **Bu bağlantıyla bir WIP'i ilişkilendir**: **Bu bağlantı için WIP etki alanını** girin
  - **Uygulamaları bu bağlantıyla ilişkilendir**: **VPN bağlantısını bu uygulamalarla kısıtlayabilir** ve ardından **İlişkili Uygulamalar** ekleyebilirsiniz. Girdiğiniz uygulamalar VPN bağlantısını otomatik olarak kullanır. Uygulamanın türü uygulama tanımlayıcısını belirler. Bir evrensel uygulama için paket aile adını girin. Bir masaüstü uygulaması için söz konusu uygulamanın dosya yolunu girin.
  >[!IMPORTANT]
  >Uygulama başına VPN'ler için oluşturulan tüm uygulama listelerini güvenlik altına almanızı öneririz. Yetkisiz bir kullanıcı bu listede değişiklik yaparsa ve bunu uygulama başına VPN uygulama listesine aktarırsanız, erişimi olmaması gereken uygulamalara VPN erişimi yetkisi verme olasılığınız vardır. Uygulama listelerini güvenlik altına almanın yollarından biri, erişim denetim listesi (ACL) kullanmaktır.

- **Bu VPN bağlantısının ağ trafiği kuralları**: VPN bağlantısı için hangi protokollerin, yerel ve uzak bağlantı noktasının ve adres aralıklarının etkinleştirileceğini seçin. Bir ağ trafiği kuralı oluşturmazsanız, bu durumda tüm protokoller, bağlantı noktaları ve adres aralıkları etkinleştirilir. Bir kural oluşturduktan sonra, VPN bağlantısı yalnızca bu kuralda veya ek kurallarda girdiğiniz protokolleri, bağlantı noktalarını ve adres aralıklarını kullanır.

## <a name="conditional-access"></a>Koşullu Erişim

- **VPN bağlantısı için koşullu erişim**: İstemciden cihaz uyumluluk akışını etkinleştirir. Etkinleştirildiğinde, VPN istemcisi kimlik doğrulama için kullanmak üzere bir sertifika almak üzere Azure Active Directory (AD) ile iletişime geçmeye çalışır. VPN’nin sertifika kimlik doğrulamasını kullanacak şekilde ayarlanmış olması ve VPN sunucusunun Azure AD tarafından döndürülen sunucuya güvenmesi gerekir.

- **Alternatif sertifika ile çoklu oturum açma (SSO)**: Cihaz uyumluluğu amacıyla Kerberos kimlik doğrulaması için VPN kimlik doğrulama sertifikasından farklı bir sertifika kullanın. Aşağıdaki ayarlarla sertifikayı girin:

  - **Ad**: Genişletilmiş anahtar kullanımı (EKU) adı
  - **Nesne Tanımlayıcısı**: EKU için nesne tanımlayıcısı
  - **Sertifikayı veren karması**: SSO sertifikası için parmak izi

## <a name="dns-settings"></a>DNS Ayarları

**Bu VPN bağlantısı için etki alanı ve sunucular**: VPN'nin kullanması için etki alanını ve DNS sunucusunu ekleyin. Bağlantı kurulduktan sonra VPN bağlantısının hangi DNS sunucularını kullanacağını seçebilirsiniz. Her sunucu için şunları girin:
- **Etki alanı**
- **DNS Sunucusu**
- **Proxy**

## <a name="proxy-settings"></a>Proxy ayarları

- **Otomatik yapılandırma betiği**: Proxy sunucusunu yapılandırmak için bir dosya kullanın. Yapılandırma dosyasını içeren **Proxy sunucu URL'sini** (örneğin, `http://proxy.contoso.com`) girin.
- **Adres**: Proxy sunucusu adresini girin (IP adresi veya `vpn.contoso.com` gibi)
- **Bağlantı noktası numarası**: Proxy sunucunuz tarafından kullanılan TCP bağlantı noktası numarasını girin
- **Yerel adresler için proxy atlama**: Yerel adresleriniz için proxy sunucusu kullanmak istemiyorsanız Etkinleştir'i seçin. VPN sunucunuz bağlantı için bir proxy sunucusu gerektiriyorsa, bu ayar uygulanır.

## <a name="split-tunneling"></a>Bölünmüş Tünel

- **Bölünmüş tünel**: Trafiğe bağlı olarak hangi bağlantının kullanılacağına cihazların karar vermesini sağlamak için bu seçeneği **Etkinleştirin** veya **Devre Dışı Bırakın**. Örneğin, oteldeki bir kullanıcı çalışma dosyalarına erişmek için VPN bağlantısını, web’e göz atmak için ise otelin standart ağını kullanır.
- **Bu VPN bağlantısının tünel oluşturma rotalarını ayırma**: Üçüncü taraf VPN sağlayıcıları için isteğe bağlı rotalar ekleyin. Her bağlantı için bir hedef ön eki ve ön ek boyutu girin.
