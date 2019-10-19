---
title: Microsoft Intune-Azure 'da VPN ayarlarını iOS cihazlarına yapılandırma | Microsoft Docs
description: iOS çalıştıran cihazlarda Microsoft Intune’da bağlantı ayrıntıları, kimlik doğrulama yöntemleri ve temel ayarlarda bölünmüş tünel; tanımlayıcı ile özel VPN ayarları ve anahtar-değer çiftleri; Safari URL’lerini içeren uygulama başına VPN ayarları, SSID veya DNS arama etki alanları ile isteğe bağlı VPN’ler; bir yapılandırma betiği, IP veya FQDN adresini içeren proxy ayarları ile TCP bağlantı noktası dahil olmak üzere sanal özel ağ (VPN) yapılandırma ayarlarını kullanarak bir VPN yapılandırma profili ekleyin veya oluşturun.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/18/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f6d7b831899a740e722560c509c4b09c31d2a42b
ms.sourcegitcommit: 8c25aeefb7cbc6444a8596af22fccd1c5426877a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72593783"
---
# <a name="add-vpn-settings-on-ios-devices-in-microsoft-intune"></a>Microsoft Intune 'de iOS cihazlarına VPN ayarları ekleme

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Microsoft Intune, iOS cihazlarınıza dağıtılabilir pek çok VPN ayarı içerir. Bu ayarlar, kuruluşunuzun ağına yönelik VPN bağlantıları oluşturmak ve yapılandırmak için kullanılır. Bu makalede bu ayarlar açıklanır. Bazı ayarlar yalnızca Citrix ve Zscaler gibi bazı VPN istemcileri için kullanılabilir.

## <a name="before-you-begin"></a>Başlamadan önce

[Bir cihaz yapılandırma profili oluşturun](vpn-settings-configure.md).

> [!NOTE]
> Bu ayarlar tüm kayıt türleri için kullanılabilir. Kayıt türleri hakkında daha fazla bilgi için bkz. [iOS kaydı](../enrollment/ios-enroll.md).

## <a name="connection-type"></a>Bağlantı türü

Aşağıdaki satıcı listesinden VPN bağlantı türünü seçin:

- **Check Point Capsule VPN**
- **Cisco Eski AnyConnect**: [Cisco Eski AnyConnect](https://itunes.apple.com/app/cisco-legacy-anyconnect/id392790924) uygulama sürümü 4.0.5x ve öncesi için geçerlidir.
- **Cisco AnyConnect**: [Cisco AnyConnect](https://itunes.apple.com/app/cisco-anyconnect/id1135064690) uygulama sürümü 4.0.7x ve sonrası için geçerlidir.
- **SonicWall Mobile Connect**
- **F5 Access Eski**: F5 Access uygulama sürümü 2.1 ve öncesi için geçerlidir.
- **F5 Access**: F5 Access uygulama sürümü 3.0 ve sonrası için geçerlidir.
- **Palo Alto Networks GlobalProtect (Eski)** : Palo Alto Networks GlobalProtect uygulama sürümü 4.1 ve öncesi için geçerlidir.
- **Palo Alto Networks GlobalProtect**: Palo Alto Networks GlobalProtect uygulama sürümü 5.0 ve sonrası için geçerlidir.
- **Pulse Secure**
- **Cisco (IPSec)**
- **Citrix VPN**
- **Citrix SSO**
- **Zscaler**: koşullu erişimi kullanmak veya kullanıcıların Zscaler oturum açma ekranını atlamasına izin vermek Için, Zscaler özel erişimini (ZPA) Azure AD hesabınızla tümleştirmeniz gerekir. Ayrıntılı adımlar için bkz. [Zscaler belgeleri](https://help.zscaler.com/zpa/configuration-example-microsoft-azure-ad). 
- **Ikev2**: [Ikev2 ayarları](#ikev2-settings) (Bu makalede) özelliklerini açıklar.
- **Özel VPN**

> [!NOTE]
> Cisco, Citrix, F5 ve Palo Alto; eski istemcilerinin iOS 12 sürümünde çalışmadığını duyurdu. En kısa zamanda yeni uygulamalara geçmeniz gerekir. Daha fazla bilgi için bkz. [Microsoft Intune Destek Ekibi Blogu](https://go.microsoft.com/fwlink/?linkid=2013806&clcid=0x409).

## <a name="base-vpn-settings"></a>Temel VPN ayarları

Aşağıdaki listede gösterilen ayarlar, seçtiğiniz VPN bağlantı türüne göre belirlenir.  

- **Bağlantı adı**: Cihazlarındaki kullanılabilir VPN bağlantıları listesine göz atan son kullanıcılar bu adı görür.
- **Özel etki alanı adı** (yalnızca Zscaler): Zscaler uygulamasının oturum açma alanını kullanıcılarınızın ait olduğu etki alanı Ile önceden doldurun. Örneğin kullanıcı adı `Joe@contoso.net` ise uygulama açıldığında alanda `contoso.net` etki alanı statik olarak görünür. Bir etki alanı adı girmezseniz Azure Active Directory’deki (AD) UPN’nin etki alanı kısmı kullanılır.
- **IP adresi veya FQDN**: Cihazların bağlanırken kullandığı VPN sunucusunun IP adresi veya tam etki alanı adı (FQDN). Örneğin `192.168.1.1` veya `vpn.contoso.com` girin.
- **Kuruluşun bulut adı** (yalnızca Zscaler): Kuruluşunuzun sağlandığı bulutun adını girin. Bu ad, Zscaler’da oturum açarken kullandığınız URL’de mevcuttur.  
- **Kimlik doğrulama yöntemi**: Cihazların VPN sunucusunda kimliklerini nasıl doğrulayacaklarını seçin. 
  - **Sertifikalar**: **Kimlik doğrulama sertifikası** altında, bağlantının kimliğini doğrulamak için mevcut bir SCEP veya PKCS sertifika profilini seçin. [Sertifika yapılandırma](../protect/certificates-configure.md), sertifika profilleri hakkında rehberlik sağlar.
  - **Kullanıcı adı ve parola**: Son kullanıcıların VPN sunucusunda oturum açmak için kullanıcı adı ve parola girmesi gerekir.  

    > [!NOTE]
    > Cisco IPsec VPN için kimlik doğrulama yöntemi olarak kullanıcı adı ve parola kullanılacaksa bunlar, özel bir Apple Configurator profili ile SharedSecret’ı teslim etmelidir.

  - **Türetilmiş kimlik bilgileri**: türetilmiş bir kimlik bilgisi veren yapılandırılmamışsa, Intune bunu yapmanızı ister.

- **Dışlanan URL’ler** (yalnızca Zscaler): Zscaler VPN’e bağlıyken, listelenen URL’lere Zscaler bulutu dışında da erişilebilir. 

- **Bölünmüş tünel**: Trafiğe bağlı olarak hangi bağlantının kullanılacağına cihazların karar vermesini sağlamak için bu seçeneği **Etkinleştirin** veya **Devre Dışı Bırakın**. Örneğin, oteldeki bir kullanıcı çalışma dosyalarına erişmek için VPN bağlantısını, web’e göz atmak için ise otelin standart ağını kullanır.

- **VPN tanımlayıcısı** (özel VPN, Zscaler ve Citrix): kullanmakta olduğunuz VPN uygulaması için bir tanımlayıcı ve VPN sağlayıcınız tarafından sağlanır.
  - **Kuruluşunuzun özel VPN öznitelikleri için anahtar/değer çiftlerini girin**: VPN bağlantınızı özelleştiren **Anahtarlar** ve **Değerler**’i ekleyin veya içeri aktarın. Bu değerlerin genelde VPN sağlayıcınız tarafından verildiğini unutmayın.

- **Ağ erişim denetimini etkinleştir (NAC)** (Citrix SSO, F5 Access): **kabul ediyorum**' u SEÇTIĞINIZDE, cihaz kimliği VPN profiline dahildir. Bu KIMLIK, ağ erişimine izin vermek veya erişimi engellemek için VPN kimlik doğrulaması için kullanılabilir.

  **F5 erişimini kullanırken**şunları yaptığınızdan emin olun:

  - F5 BIG-IP 13.1.1.5 kullandığınızı onaylayın. BÜYÜK IP 14 desteklenmez.
  - NAC için büyük IP 'yi Intune ile tümleştirin. Bkz. [genel bakış: uç nokta yönetim sistemleri ile cihaz gönderme denetimleri IÇIN APM yapılandırma](https://support.f5.com/kb/en-us/products/big-ip_apm/manuals/product/apm-client-configuration-7-1-6/6.html#guid-0bd12e12-8107-40ec-979d-c44779a8cc89) F5 Kılavuzu.
  - VPN profilinde NAC 'yi etkinleştirin.

  **CITRIX SSO 'Yu ağ geçidiyle kullanırken**şunları yaptığınızdan emin olun:

  - Citrix Gateway 12.0.59 veya üstünü kullandığınızı onaylayın.
  - Kullanıcılarınızın cihazlarında Citrix SSO 1.1.6 veya üzeri yüklü olduğunu doğrulayın.
  - NAC için Citrix Gateway 'i Intune ile tümleştirin. Bkz. [Microsoft Intune/Enterprise Mobility Suite 'ı NetScaler (LDAP + OTP senaryosu)](https://www.citrix.com/content/dam/citrix/en_us/documents/guide/integrating-microsoft-intune-enterprise-mobility-suite-with-netscaler.pdf) Citrix dağıtım kılavuzu ile tümleştirme.
  - VPN profilinde NAC 'yi etkinleştirin.

  **Önemli ayrıntılar**:  

  - NAC etkinleştirildiğinde, VPN her 24 saatte bir kesilir. VPN hemen yeniden bağlanabilir.
  - Cihaz KIMLIĞI profilin bir parçasıdır, ancak Intune 'da gösterilmez. Bu kimlik Microsoft tarafından herhangi bir yerde depolanmaz ve paylaşılmaz.

  Cihaz KIMLIĞI VPN iş ortakları tarafından desteklenerek, Citrix SSO gibi VPN istemcisi KIMLIĞI alabilir. Daha sonra, cihazın kaydedildiğini ve VPN profilinin uyumlu veya uyumlu olmadığını doğrulamak için Intune 'U sorgulayabilir.

  - Bu ayarı kaldırmak için profili yeniden oluşturun ve **Kabul ediyorum**’u seçmeyin. Daha sonra profili yeniden atayın.

## <a name="ikev2-settings"></a>Ikev2 ayarları

Bu ayarlar  >  Ikev2 **bağlantı türünü**seçtiğinizde geçerlidir.

- **Uzak tanımlayıcı**: Ikev2 sunucusunun ağ IP ADRESINI, FQDN 'Sini, userfqdn 'SINI veya ASN1DN girin. Örneğin `10.0.0.3` veya `vpn.contoso.com` girin. Genellikle [**bağlantı adı**](#base-vpn-settings) ile aynı değeri girersiniz (Bu makalede). Ancak, Ikev2 Sunucu ayarlarınıza göre değişir.

- **Istemci kimlik doğrulaması türü**: VPN istemcisinin VPN 'de kimlik doğrulamasını seçin. Seçenekleriniz şunlardır:
  - **Kullanıcı kimlik doğrulaması** (varsayılan): Kullanıcı KIMLIK bilgileri VPN 'de kimlik doğrular.
  - **Makine kimlik doğrulaması**: cihaz KIMLIK bilgileri VPN ile kimlik doğrular.

- **Kimlik doğrulama yöntemi**: sunucuya göndermek için istemci kimlik bilgilerinin türünü seçin. Seçenekleriniz şunlardır:
  - **Sertifikalar**: VPN 'de kimlik doğrulamak için mevcut bir sertifika profilini kullanır. Bu sertifika profilinin zaten Kullanıcı veya cihaza atanmış olduğundan emin olun. Aksi halde VPN bağlantısı başarısız olur.
    - **Sertifika türü**: sertifika tarafından kullanılan şifreleme türünü seçin. VPN sunucusunun bu tür bir sertifikayı kabul edecek şekilde yapılandırıldığından emin olun. Seçenekleriniz şunlardır:
      - **RSA** (varsayılan)
      - **ECDSA256**
      - **ECDSA384**
      - **ECDSA521**

  - **Kullanıcı adı ve parola** (yalnızca Kullanıcı kimlik doğrulaması): kullanıcılar VPN 'e bağlandıklarında, Kullanıcı adı ve parola istenir.
  - **Paylaşılan gizli** dizi (yalnızca makine kimlik doğrulaması): VPN sunucusuna göndermek için paylaşılan bir gizlilik girmenize olanak sağlar.
    - **Paylaşılan gizlilik**: önceden paylaşılan anahtar (PSK) olarak da bilinen paylaşılan parolayı girin. Değerin VPN sunucusunda yapılandırılmış paylaşılan gizli anahtar ile eşleştiğinden emin olun.

- **Sunucu sertifikası verenin ortak adı**: VPN sunucusunun VPN istemcisinde kimlik doğrulamasına izin verir. Cihazdaki VPN istemcisine gönderilen VPN sunucu sertifikasının sertifika verenin ortak adını (CN) girin. CN değerinin VPN sunucusundaki yapılandırmayla eşleştiğinden emin olun. Aksi halde VPN bağlantısı başarısız olur.
- **Sunucu sertifikası ortak adı**: sertifikanın kendısı için CN 'yi girin. Boş bırakılırsa, uzak tanımlayıcı değeri kullanılır.

- **Kullanılmayan eş algılama oranı**: VPN istemcisinin etkin olup OLMADıĞıNı, VPN istemcisinin ne sıklıkta denetleyeceğini seçin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı**:, **Orta**' i seçmeyle aynı olabilen iOS sistemi varsayılanını kullanır.
  - **Hiçbiri**: kullanılmayan eşdüzey algılamayı devre dışı bırakır.
  - **Düşük**: her 30 dakikada bir canlı tutma iletisi gönderir.
  - **Orta** (varsayılan): 10 dakikada bir canlı tutma iletisi gönderir.
  - **Yüksek**: her 60 saniyede bir KeepAlive iletisi gönderir.

- **TLS sürüm aralığı en az**: kullanılacak en düşük TLS sürümünü girin. @No__t_0, `1.1` veya `1.2` girin. Boş bırakılırsa, `1.0` ' ın varsayılan değeri kullanılır.
- **En yüksek TLS sürüm aralığı**: kullanılacak en fazla TLS sürümünü girin. @No__t_0, `1.1` veya `1.2` girin. Boş bırakılırsa, `1.2` ' ın varsayılan değeri kullanılır.
- **Kusursuz iletme gizliliği**: kusursuz iletme gizliliği 'NI (PFS) açmak için **Etkinleştir** ' i seçin. PFS, bir oturum anahtarının güvenliğinin tehlikeye girdiği etkiyi azaltan bir IP güvenlik özelliğidir. **Devre dışı bırak** (varsayılan) PFS kullanmaz.
- **Sertifika iptal denetimi**: VPN bağlantısının başarılı olmasına izin vermeden önce sertifikaların iptal edilmediğinden emin olmak için **Etkinleştir** ' i seçin. Bu denetim en iyi çabadır. Sertifikanın iptal edilip edilmediğini belirlemekten önce VPN sunucusu zaman aşımına uğrarsa, erişim izni verilir. **Devre dışı bırak** (varsayılan) iptal edilen sertifikaları denetlemez.

- **Güvenlik ilişkisi parametrelerini yapılandırma**: **Yapılandırılmadı** (varsayılan) iOS sistemi varsayılanını kullanır. VPN sunucusuyla güvenlik ilişkilendirmeleri oluştururken kullanılan parametreleri girmek için **Etkinleştir** ' i seçin:
  - **Şifreleme algoritması**: istediğiniz algoritmayı seçin:
    - MADDESINI
    - 3DES
    - AES-128
    - AES-256 (varsayılan)
    - AES-128-GCM
    - AES-256-GCM
  - **Bütünlük algoritması**: istediğiniz algoritmayı seçin:
    - SHA1-96
    - SHA1-160
    - SHA2-256 (varsayılan)
    - SHA2-384
    - SHA2-512
  - **Diffie-Hellman grubu**: istediğiniz grubu seçin. Varsayılan Grup `2` ' dır.
  - **Yaşam süresi** (dakika): anahtarlar döndürülünceye kadar güvenlik ilişkisinin ne kadar süreyle etkin kalacağını seçin. @No__t_0 ve `1440` arasında bir tam değer girin (1440 dakika 24 saat). Varsayılan değer `1440` ' dır.

- **Alt güvenlik ilişkilendirmeleri için ayrı bir parametre kümesi yapılandırın**: IOS, Ike bağlantısı için ayrı parametreleri ve tüm alt bağlantıları yapılandırmanıza olanak tanır. 

  **Yapılandırılmadı** (varsayılan), önceki **güvenlik ilişkisi parametrelerini Yapılandır** ayarında girdiğiniz değerleri kullanır. VPN sunucusu ile *alt* güvenlik ilişkilendirmeleri oluştururken kullanılan parametreleri girmek için **Etkinleştir** ' i seçin:
  - **Şifreleme algoritması**: istediğiniz algoritmayı seçin:
    - MADDESINI
    - 3DES
    - AES-128
    - AES-256 (varsayılan)
    - AES-128-GCM
    - AES-256-GCM
  - **Bütünlük algoritması**: istediğiniz algoritmayı seçin:
    - SHA1-96
    - SHA1-160
    - SHA2-256 (varsayılan)
    - SHA2-384
    - SHA2-512
  - **Diffie-Hellman grubu**: istediğiniz grubu seçin. Varsayılan Grup `2` ' dır.
  - **Yaşam süresi** (dakika): anahtarlar döndürülünceye kadar güvenlik ilişkisinin ne kadar süreyle etkin kalacağını seçin. @No__t_0 ve `1440` arasında bir tam değer girin (1440 dakika 24 saat). Varsayılan değer `1440` ' dır.

## <a name="automatic-vpn-settings"></a>Otomatik VPN ayarları

- **Uygulama başına VPN**: Uygulama başına VPN’i etkinleştirir. Belirli uygulamalar açıldığında VPN bağlantısının otomatik olarak tetiklenmesine izin verir. Ayrıca uygulamaları bu VPN profiliyle ilişkilendirir. Daha fazla bilgi için bkz. [iOS için uygulama başına VPN ayarlama yönergeleri](vpn-setting-configure-per-app.md).
  - **Sağlayıcı Türü**: Yalnızca Pulse Secure ve Özel VPN için kullanılabilir.
  - Pulse Secure veya Özel VPN ile iOS **uygulama başına VPN** profillerini kullanırken uygulama katmanı tünelini (app-proxy) veya paket düzeyi tüneli (packet-tunnel) seçin. **ProviderType** değerini uygulama katmanı tüneli için **app-proxy** olarak veya paket katmanı tüneli için **packet-tunnel** ayarlayın. Hangi değeri kullanmanız gerektiğini bilmiyorsanız VPN sağlayıcınızın belgelerine bakın.
  - **Bu VPN’i tetikleyecek Safari URL’leri**: Bir veya daha fazla web sitesi URL’si ekleyin. Bu URL’ler cihazda Safari tarayıcıyla ziyaret edildiğinde, VPN bağlantısı otomatik olarak kurulur.

- **İsteğe bağlı VPN**: VPN bağlantısının ne zaman başlatılacağını denetleyen koşullu kurallar yapılandırın. Örneğin, yalnızca cihaz şirketin Wi-Fi ağına bağlı olmadığında VPN bağlantısının kullanılacağı bir koşul oluşturun. Ya da bir koşul oluşturun. Örneğin, bir cihaz girdiğiniz DNS arama etki alanına erişemezse VPN bağlantısı başlatılmaz.

  - **SSID’ler veya DNS arama etki alanları**: Bu koşulun kablosuz ağ **SSID’lerini** mi yoksa **DNS arama etki alanlarını** mı kullanacağını seçin. Bir veya birden çok SSID veya arama etki alanı yapılandırmak için **Ekle**’yi seçin.
  - **URL dizesi araştırması**: İsteğe bağlıdır. Kuralın test olarak kullanacağı bir URL girin. Bu profille cihaz bu URL 'ye yeniden yönlendirmesiz erişirse VPN bağlantısı başlatılır. Cihaz hedef URL’ye bağlanır. Kullanıcı, URL dize araştırma sitesini görmez. URL dize yoklaması, VPN’i bağlamadan önce cihaz uyumluluğunu denetleyen bir denetim Web sunucusunun adresidir. Başka bir seçenek de URL’nin, cihazı VPN aracılığıyla hedef URL’ye bağlamadan önce VPN’in bir siteye bağlanma yeteneğini sınamasıdır.
  - **Etki alanı eylemi**: Aşağıdaki öğelerden birini seçin:
    - Gerekirse bağlan
    - Hiçbir zaman bağlanma
  - **Eylem**: Aşağıdaki öğelerden birini seçin:
    - Bağlanma
    - Bağlantıyı değerlendir
    - Yoksay
    - Ayır

## <a name="proxy-settings"></a>Proxy ayarları

Proxy kullanıyorsanız aşağıdaki ayarları yapılandırın. Proxy ayarları, Zscaler VPN bağlantıları için kullanılamaz.  

- **Otomatik yapılandırma betiği**: Proxy sunucusunu yapılandırmak için bir dosya kullanın. Yapılandırma dosyasını içeren **Proxy sunucu URL’si** (örneğin `http://proxy.contoso.com`) değerini girin.
- **Adres**: Proxy sunucusunun tam konak adına ait IP adresini girin.
- **Bağlantı noktası numarası**: Proxy sunucusuyla ilişkilendirilmiş bağlantı noktası numarasını girin.

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturulur ancak henüz herhangi bir işlem gerçekleştirmez. Ardından [profili atayın](device-profile-assign.md) ve [durumunu izleyin](device-profile-monitor.md).

[Android](vpn-settings-android.md), [Android Enterprise](vpn-settings-android-enterprise.md), [MacOS](vpn-settings-macos.md)ve [Windows 10](vpn-settings-windows-10.md) cihazlarında VPN ayarlarını yapılandırın.
