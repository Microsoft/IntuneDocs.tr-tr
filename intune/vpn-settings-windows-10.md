---
title: Microsoft Intune - Azure'da Windows 10 VPN ayarları | Microsoft Docs
description: Öğrenin ve tüm kullanılabilir VPN Intune ayarlarında, ne için kullanıldıkları ve, trafik kuralları, koşullu erişim ve DNS ile Ara sunucu ayarlarını Windows 10 ve Windows Holographic for Business cihazlar dahil olmak üzere yapabileceklerini okuyun.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/12/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.reviewer: tycast
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8b71bc2ea893199b83de5fd1480dae5630c3edfd
ms.sourcegitcommit: 9a4c5b6c2ce511edaeace25426a23f180cb71e15
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/07/2019
ms.locfileid: "57565679"
---
# <a name="windows-10-and-windows-holographic-device-settings-to-add-vpn-connections-using-intune"></a>Intune kullanarak VPN bağlantılarını eklemek için Windows 10 ve Windows Holographic cihaz ayarları

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ekleme ve Intune kullanan cihazlar için VPN bağlantıları yapılandırın. Bu makalede, listeler ve sanal özel ağlar (VPN'ler) oluştururken kullanılan ayarları ve özellikleri açıklar. Bu VPN ayarları ve özellikleri gönderildi veya cihazlara dağıttığınız ıntune'da cihaz yapılandırma profili kullanılır. 

Mobil cihaz Yönetimi (MDM) çözümünüzün bir parçası olarak, izin vermek veya bir VPN satıcısı kullanarak, her zaman etkinleştirme, DNS kullanarak, bir ara sunucu ve daha fazlasını ekleme dahil olmak üzere, özellikleri devre dışı bırakmak için bu ayarları kullanın.

Bu ayarlar çalıştıran cihazlar için geçerlidir:

- Windows 10
- Windows 10 Holographic for Business

Seçtiğiniz ayarlara bağlı olarak, değerlerden bazıları yapılandırılamayabilir.

## <a name="before-you-begin"></a>Başlamadan önce

[VPN cihaz yapılandırma profili oluşturma](vpn-settings-configure.md).

## <a name="base-vpn-settings"></a>Temel VPN ayarları

- **Bağlantı adı**: Bu bağlantı için bir ad girin. Cihazlarındaki kullanılabilir VPN bağlantılarına göz atan son kullanıcılar bu adı görür.
- **Sunucuları**: Cihazların bağlandığı bir veya daha fazla VPN sunucusu ekleyin. Sunucu eklerken aşağıdaki bilgileri girersiniz:
  - **Açıklama**: Sunucu için açıklayıcı bir ad girmeniz **Contoso VPN sunucusu**
  - **IP adresi veya FQDN**: IP adresi veya gibi cihaz için bağlanan VPN sunucusunun tam etki alanı adı (FQDN) girin **192.168.1.1** veya **vpn.contoso.com**
  - **Varsayılan sunucu**: Bu sunucuyu, cihazların bağlantı kurmak için kullandığı varsayılan sunucu olarak etkinleştirir. Varsayılan sunucu olarak tek bir sunucu ayarlayın.
  - **İçeri aktarma**: Biçiminde sunucu listesini içeren virgülle ayrılmış bir dosyaya göz atın: açıklama, IP adresi veya FQDN, varsayılan sunucu. **Tamam**'ı seçerek bu sunucuları **Sunucular** listesine içeri aktarın.
  - **Dışarı aktarma**: Sunucu listesini virgülle ayrılmış değerler (csv) dosyasına dışarı aktarır.

- **IP adreslerini iç DNS ile Kaydet**: Seçin **etkinleştirme** iç DNS ile VPN arabirimi için atanan IP adresleri dinamik olarak kaydetmek için Windows 10 VPN profili yapılandırılır. IP adreslerini dinamik olarak kaydetmek istemiyorsanız **Devre Dışı Bırak**’ı seçin.

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
    - **Her zaman açık**: Seçin **etkinleştirme** aşağıdaki olaylar gerçekleştiğinde VPN bağlantısı otomatik olarak bağlanmak için: 
      - Kullanıcılar cihazlarında oturum açtığında
      - Cihazdaki ağ değiştiğinde
      - Cihaz ekranı kapandıktan sonra yeniden açıldığında 

    - **Kimlik doğrulama yöntemi**: Kullanıcıların VPN sunucusunda kimlik doğrulaması yapmasına nasıl istediğinizi seçin. **Sertifikaların** kullanılması sıfır temaslı deneyim, isteğe bağlı VPN ve uygulama başına VPN gibi iyileştirilmiş özellikler sağlar.
    - **Her oturum açmada kimlik bilgilerini Hatırla**: Kimlik doğrulama kimlik bilgilerini önbelleğe almak bu seçeneği seçin.
    - **Özel XML**: VPN bağlantısını yapılandıran özel XML komutlarını girin.
    - **EAP Xml**: VPN bağlantısını yapılandıran EAP XML komutlarını girin

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

- **WIP veya uygulamaları bu VPN ile ilişkilendir**: Yalnızca belirli uygulamaların VPN bağlantısını kullanmasını istiyorsanız bu ayarı etkinleştirin. Seçenekleriniz şunlardır:

  - **Bu bağlantıyla bir WIP'i ilişkilendir**: Girin bir **Bu bağlantı için WIP etki alanı**
  - **Uygulamaları bu bağlantıyla ilişkilendir**: Yapabilecekleriniz **kısıtlama VPN bağlantısını bu uygulamalarla**ve ardından eklemek **ilişkili uygulamalar**. Girdiğiniz uygulamalar VPN bağlantısını otomatik olarak kullanır. Uygulamanın türü uygulama tanımlayıcısını belirler. Bir evrensel uygulama için paket aile adını girin. Bir masaüstü uygulaması için söz konusu uygulamanın dosya yolunu girin.
  >[!IMPORTANT]
  >Uygulama başına VPN'ler için oluşturulan tüm uygulama listelerini güvenlik altına almanızı öneririz. Yetkisiz bir kullanıcı bu listede değişiklik yaparsa ve bunu uygulama başına VPN uygulama listesine aktarırsanız, erişimi olmaması gereken uygulamalara VPN erişimi yetkisi verme olasılığınız vardır. Uygulama listelerini güvenlik altına almanın yollarından biri, erişim denetim listesi (ACL) kullanmaktır.

- **Ağ trafiği kuralları bu VPN bağlantısının**: Hangi, VPN bağlantısı için protokolleri ve hangi yerel ve uzak bağlantı noktasının ve adres aralıklarının etkinleştirileceğini seçin. Bir ağ trafiği kuralı oluşturmazsanız, bu durumda tüm protokoller, bağlantı noktaları ve adres aralıkları etkinleştirilir. Bir kural oluşturduktan sonra, VPN bağlantısı yalnızca bu kuralda veya ek kurallarda girdiğiniz protokolleri, bağlantı noktalarını ve adres aralıklarını kullanır.

## <a name="conditional-access"></a>Koşullu Erişim

- **Bu VPN bağlantısı için koşullu erişim**: İstemciden cihaz uyumluluk akışını etkinleştirir. Etkinleştirildiğinde, VPN istemcisi kimlik doğrulama için kullanmak üzere bir sertifika almak için Azure Active Directory (AD) ile iletişim kurar. VPN’nin sertifika kimlik doğrulamasını kullanacak şekilde ayarlanmış olması ve VPN sunucusunun Azure AD tarafından döndürülen sunucuya güvenmesi gerekir.

- **Çoklu oturum açma (SSO) alternatif sertifikayla**: Cihaz uyumluluğu amacıyla Kerberos kimlik doğrulaması için VPN kimlik doğrulama sertifikasından farklı bir sertifika kullanın. Aşağıdaki ayarlarla sertifikayı girin:

  - **Ad**: Genişletilmiş Anahtar Kullanımı (EKU) için ad
  - **Nesne tanımlayıcısı**: EKU için nesne tanımlayıcısı
  - **Veren karması**: SSO sertifikası için parmak izi

## <a name="dns-settings"></a>DNS Ayarları

- **DNS soneki arama listesi**: İçinde **DNS son eklerini**, bir DNS son eki girin ve **Ekle**. Birçok sonekleri ekleyebilirsiniz.

  DNS son ekleri kullanırken bir ağ kaynağını tam etki alanı adı (FQDN) yerine kısa adını kullanarak arayabilirsiniz. Kısa ad kullanılarak yapılan aramalarda, son ek otomatik olarak DNS sunucusu tarafından belirlenir. Örneğin, `utah.contoso.com` DNS son eki listesinde yer alır. `DEV-comp` ping yaparsınız. Bu senaryoda `DEV-comp.utah.contoso.com` olarak çözümlenir.

  DNS son ekleri listelenen sırayla çözümlenir ve bu sıra değiştirilebilir. Örneğin `colorado.contoso.com` ve `utah.contoso.com` DNS son eki listesindedir ve ikisinin de `DEV-comp` adlı bir kaynağı vardır. `colorado.contoso.com` listedeki ilk öğe olduğundan, `DEV-comp.colorado.contoso.com` olarak çözümlenir.
  
  Sırayı değiştirmek için DNS son ekinin solundaki noktalara tıklayın ve son eki en üste sürükleyin:

  ![Dns son ekini taşımak için üç noktaya tıklayın ve sürükleyin](./media/vpn-settings-windows10-move-dns-suffix.png)

- **Ad çözümleme İlkesi tablosu (NRPT) kuralları**: DNS adları VPN'ye bağlı olduğunda nasıl çözümler ad çözümleme İlkesi tablosu (NRPT) kuralları tanımlayın. VPN bağlantısı kurulduktan sonra VPN bağlantısı tarafından kullanılan hangi DNS sunucularını seçin.

  Etki alanı, DNS sunucusu, Ara sunucu ve diğer ayrıntıları, girdiğiniz etki alanını çözümlemek için tablonun kuralları ekleyebilirsiniz. Kullanıcılar, girdiğiniz etki alanlarına bağlanırken VPN bağlantısını bu kurallar kullanır.

  Seçin **Ekle** yeni bir kural eklemek üzere. Her sunucu için şunları girin:

  - **Etki alanı**: Tam etki alanı adı (FQDN) veya kuralı uygulamak için bir DNS son eki girin. Bir DNS soneki için başında nokta (.) da girebilirsiniz. Örneğin `contoso.com` veya `.allcontososubdomains.com` girin.
  - **DNS sunucuları**: IP adresi veya etki alanı çözümler DNS sunucusu girin. Örneğin `10.0.0.3` veya `vpn.contoso.com` girin.
  - **Proxy**: Etki alanı çözümler web proxy sunucusu girin. Örneğin, şunu girin: `http://proxy.com`.
  - **Otomatik olarak bağlan**: Zaman **etkin**, bir cihaz gibi girdiğiniz etki alanına bağlandığında VPN cihaz otomatik olarak bağlanır. `contoso.com`. Zaman **yapılandırılmadı** (varsayılan), cihaz değil otomatik olarak bağlanmak için VPN
  - **Kalıcı**: Ayarlandığında **etkin**kural el ile CİHAZDAN kaldırılana kadar kural ad çözümleme İlkesi tablosu (NRPT) kalır, hatta sonra VPN bağlantısını keser. Ayarlandığında **yapılandırılmadı** (varsayılan), VPN kesildiğinde NRPT kurallarının VPN profili CİHAZDAN kaldırılır.

## <a name="proxy-settings"></a>Proxy ayarları

- **Otomatik yapılandırma betiği**: Proxy sunucusunu yapılandırmak için bir dosya kullanın. Yapılandırma dosyasını içeren **Proxy sunucu URL'sini** (örneğin, `http://proxy.contoso.com`) girin.
- **Adresi**: Proxy sunucu adresi, örneğin bir IP adresi girin veya `vpn.contoso.com`
- **Bağlantı noktası numarası**: Proxy sunucunuz tarafından kullanılan TCP bağlantı noktası numarasını girin
- **Yerel adresler için proxy atlama**: Yerel adresler için Ara sunucu kullanmak istemiyorsanız, Etkinleştir'ni seçin. VPN sunucunuz bağlantı için bir proxy sunucusu gerektiriyorsa, bu ayar uygulanır.

## <a name="split-tunneling"></a>Bölünmüş Tünel

- **Bölünmüş tünel**: **Etkinleştirme** veya **devre dışı** cihazların trafiğe bağlı olarak kullanmak için hangi bağlantı karar vermesini sağlamak için. Örneğin, oteldeki bir kullanıcı çalışma dosyalarına erişmek için VPN bağlantısını, web’e göz atmak için ise otelin standart ağını kullanır.
- **Bu VPN bağlantısının tünel oluşturma rotalarını ayırma**: Üçüncü taraf VPN sağlayıcıları için isteğe bağlı rotalar ekleyin. Her bağlantı için bir hedef ön eki ve ön ek boyutu girin.

## <a name="trusted-network-detection"></a>Güvenilen ağ algılama

**Ağ DNS soneklerini güvenilir**: Kullanıcılar zaten güvenilen bir ağa bağlıyken diğer VPN bağlantıları için otomatik olarak bağlanmasını cihazları engelleyebilirsiniz.

İçinde **DNS son eklerini**, seçin ve güvendiğiniz, contoso.com gibi istediğiniz bir DNS son eki girin **Ekle**. İstediğiniz sayıda sonekleri ekleyebilirsiniz.

Ardından kullanıcı otomatik olarak bir kullanıcı listesinde bir DNS soneki bağlıysa, başka bir VPN bağlantısı bağlantı olmayacaktır. Kullanıcı, girdiğiniz DNS soneklerini güvenilir listesinde kullanmaya devam eder. Tüm autotriggers ayarlanmış olsa bile, güvenilen bir ağa yine de kullanılır.

Kullanıcı için güvenilir bir DNS soneki zaten bağlıysa, örneğin, ardından aşağıdaki autotriggers göz ardı edilir. Özellikle, listedeki DNS son eklerini dahil olmak üzere tüm diğer bağlantı autotriggers, iptal et:

- Her zaman açık
- Uygulama tabanlı tetikleyicisi
- DNS otomatik tetikleyici

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturulur ancak henüz herhangi bir işlem gerçekleştirmez. Ardından, [profili atama](device-profile-assign.md), ve [atamanın durumunu izlemenize](device-profile-monitor.md).

VPN ayarlarını yapılandırın [Android](vpn-settings-android.md), [iOS](vpn-settings-ios.md), ve [macOS](vpn-settings-macos.md) cihazlar.
