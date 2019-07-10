---
title: Microsoft Intune - Azure’da iOS cihazlara VPN ayarları ekleme | Microsoft Docs
description: iOS çalıştıran cihazlarda Microsoft Intune’da bağlantı ayrıntıları, kimlik doğrulama yöntemleri ve temel ayarlarda bölünmüş tünel; tanımlayıcı ile özel VPN ayarları ve anahtar-değer çiftleri; Safari URL’lerini içeren uygulama başına VPN ayarları, SSID veya DNS arama etki alanları ile isteğe bağlı VPN’ler; bir yapılandırma betiği, IP veya FQDN adresini içeren proxy ayarları ile TCP bağlantı noktası dahil olmak üzere sanal özel ağ (VPN) yapılandırma ayarlarını kullanarak bir VPN yapılandırma profili ekleyin veya oluşturun.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/25/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1eee827ace5dae92b485a250e6e4e0b9b426fbe6
ms.sourcegitcommit: 63b55e81122e5c15893302b109ae137c30855b55
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67713197"
---
# <a name="configure-vpn-settings-on-ios-devices-in-microsoft-intune"></a>Microsoft Intune’da iOS cihazlardaki VPN ayarlarını yapılandırma

Microsoft Intune, iOS cihazlarınıza dağıtılabilir pek çok VPN ayarı içerir. Bu ayarlar, kuruluşunuzun ağına yönelik VPN bağlantıları oluşturmak ve yapılandırmak için kullanılır. Bu makalede bu ayarlar açıklanır. Bazı ayarlar yalnızca Citrix ve Zscaler gibi bazı VPN istemcileri için kullanılabilir.

## <a name="connection-type"></a>Bağlantı türü

Aşağıdaki satıcı listesinden VPN bağlantı türünü seçin:

- **Check Point Capsule VPN**
- **Cisco eski AnyConnect**: Uygulanabilir [Cisco eski AnyConnect](https://itunes.apple.com/app/cisco-legacy-anyconnect/id392790924) uygulama sürümü 4.0.5x ve daha önce.
- **Cisco AnyConnect**: Uygulanabilir [Cisco AnyConnect](https://itunes.apple.com/app/cisco-anyconnect/id1135064690) uygulama sürümü 4.0.7x ve daha sonra.
- **SonicWall Mobile Connect**
- **F5'e Erişim eski**: F5'e erişimi uygulama sürüm 2.1 için geçerli ve önceki sürümler.
- **F5'e Erişim**: F5'e erişim uygulama sürüm 3.0 için geçerlidir ve üzeri.
- **Palo Alto Networks GlobalProtect (eski)** : Palo Alto ağları GlobalProtect uygulama sürümü 4.1 ve önceki sürümleri için geçerlidir.
- **Palo Alto Networks GlobalProtect**: Palo Alto ağları GlobalProtect uygulama sürüm 5.0 ve üzeri için geçerlidir.
- **Pulse Secure**
- **Cisco (IPSec)**
- **Citrix VPN**
- **Citrix SSO**
- **Zscaler**: Koşullu erişim kullanın veya kullanıcıların Zscaler oturum açma ekranı atlamasına izin ver ardından Zscaler özel erişim (ZPA) Azure AD hesabınız ile tümleştirmeniz gerekir. Ayrıntılı adımlar için bkz. [Zscaler belgeleri](https://help.zscaler.com/zpa/configuration-example-microsoft-azure-ad). 
- **Özel VPN**

> [!NOTE]
> Cisco, Citrix, F5 ve Palo Alto; eski istemcilerinin iOS 12 sürümünde çalışmadığını duyurdu. En kısa zamanda yeni uygulamalara geçmeniz gerekir. Daha fazla bilgi için bkz. [Microsoft Intune Destek Ekibi Blogu](https://go.microsoft.com/fwlink/?linkid=2013806&clcid=0x409).

## <a name="base-vpn-settings"></a>Temel VPN ayarları

Aşağıdaki listede gösterilen ayarlar, seçtiğiniz VPN bağlantı türüne göre belirlenir.  

- **Bağlantı adı**: Cihazlarındaki kullanılabilir VPN bağlantıları listesine göz atan son kullanıcılar bu adı görür.
- **Özel etki alanı adı** (yalnızca Zscaler): Zscaler uygulamanın oturum açma, kullanıcılarınızın ait etki alanına önceden doldurur. Örneğin kullanıcı adı `Joe@contoso.net` ise uygulama açıldığında alanda `contoso.net` etki alanı statik olarak görünür. Bir etki alanı adı girmezseniz Azure Active Directory’deki (AD) UPN’nin etki alanı kısmı kullanılır.
- **IP adresi veya FQDN**: IP adresini veya tam etki alanı adı (FQDN) ile cihazları bağlantı VPN sunucusu. Örneğin `192.168.1.1` veya `vpn.contoso.com` girin.
- **Kuruluşunuzun bulut adı** (yalnızca Zscaler): Kuruluşunuz burada sağlanan bulut adı girin. Bu ad, Zscaler’da oturum açarken kullandığınız URL’de mevcuttur.  
- **Kimlik doğrulama yöntemi**: Cihazların VPN sunucusuna kimliklerini nasıl doğrulayacaklarını seçin. 
  - **Sertifikaları**: Altında **kimlik doğrulama sertifikası**seçin profili bağlantı kimliğini doğrulamak için mevcut bir SCEP veya PKCS sertifika. [Sertifika yapılandırma](certificates-configure.md), sertifika profilleri hakkında rehberlik sağlar.
  - **Kullanıcı adı ve parola**: Son kullanıcılar, bir kullanıcı adı ve VPN sunucusunda oturum açmak için parola girmeniz gerekir.  

    > [!NOTE]
    > Cisco IPsec VPN için kimlik doğrulama yöntemi olarak kullanıcı adı ve parola kullanılacaksa bunlar, özel bir Apple Configurator profili ile SharedSecret’ı teslim etmelidir.

- **Dışlanan URL'leri** (yalnızca Zscaler): Zscaler VPN'ye bağlı, listedeki URL'leri Zscaler bulut dışında erişilebilir. 

- **Bölünmüş tünel**: **Etkinleştirme** veya **devre dışı** cihazların, trafiğe bağlı olarak kullanmak için hangi bağlantı karar vermesini sağlamak için. Örneğin, oteldeki bir kullanıcı çalışma dosyalarına erişmek için VPN bağlantısını, web’e göz atmak için ise otelin standart ağını kullanır.

- **VPN tanımlayıcısı** (özel VPN, Zscaler ve Citrix): VPN uygulamasının tanımlayıcısıdır kullanıyorsanız ve VPN sağlayıcınız tarafından verilir.
  - **Kuruluşunuzun özel VPN öznitelikleri için anahtar/değer çiftleri girin**: Ekleyin veya içeri aktarın **anahtarları** ve **değerleri** VPN bağlantınızı özelleştiren. Bu değerlerin genelde VPN sağlayıcınız tarafından verildiğini unutmayın.

- **Ağ erişim denetimi (NAC) etkinleştirme** (Citrix SSO, F5'e erişim): Seçeneğini belirlediğinizde **kabul ediyorum**, cihaz kimliği VPN profilinde yer almaktadır. Bu kimliği kimlik doğrulaması için VPN izin vermek veya ağ erişimi engellemek için kullanılabilir.

  **F5'e erişimini kullanırken**, yaptığınızdan emin olun:

  - F5 BIG-IP 13.1.1.5 kullanmakta olduğunuz onaylayın. BIG-IP 14 desteklenmez.
  - BIG-IP NAC için Intune ile tümleştirme. Bkz: [genel bakış: APM yapılandırma cihaz duruşu için uç nokta yönetim sistemleri ile denetler](https://support.f5.com/kb/en-us/products/big-ip_apm/manuals/product/apm-client-configuration-7-1-6/6.html#guid-0bd12e12-8107-40ec-979d-c44779a8cc89) F5 Kılavuzu.
  - NAC, VPN profilinde etkinleştirin.

  **Citrix SSO ile ağ geçidi kullanırken**, yaptığınızdan emin olun:

  - Citrix ağ geçidi 12.0.59 kullandığınızı onaylayın veya üzeri.
  - Kullanıcılarınızın Citrix SSO 1.1.6 veya daha sonra kullanıcıların cihazlarında yüklü onaylayın.
  - Citrix ağ geçidi için NAC ile Intune tümleştirmesi. Bkz: [NetScaler (LDAP + OTP senaryosu) ile Microsoft Intune/Enterprise Mobility Suite tümleştirme](https://www.citrix.com/content/dam/citrix/en_us/documents/guide/integrating-microsoft-intune-enterprise-mobility-suite-with-netscaler.pdf) Citrix dağıtım kılavuzu.
  - NAC, VPN profilinde etkinleştirin.

  **Önemli ayrıntıları**:  

  - NAC etkinleştirildiğinde, VPN 24 saatte kesilir. VPN hemen yeniden.
  - Cihaz kimliği profilinin bir parçasıdır, ancak Intune'da gösterilmiyor. Bu kimlik Microsoft tarafından herhangi bir yerde depolanmaz ve paylaşılmaz.

  Cihaz kimliği VPN iş ortakları tarafından desteklendiğinde, Citrix SSO gibi VPN istemci kimliğini alabilirsiniz Cihazın kaydolduğunu onaylamak için Intune sorgulayabilirsiniz ardından ve VPN profili uyumlu veya uyumsuz olduğunda.

  - Bu ayarı kaldırmak için profili yeniden oluşturun ve **Kabul ediyorum**’u seçmeyin. Daha sonra profili yeniden atayın.

## <a name="automatic-vpn-settings"></a>Otomatik VPN ayarları

- **Uygulama başına VPN**: Uygulama başına VPN sağlar. Belirli uygulamalar açıldığında VPN bağlantısının otomatik olarak tetiklenmesine izin verir. Ayrıca uygulamaları bu VPN profiliyle ilişkilendirir. Daha fazla bilgi için bkz. [iOS için uygulama başına VPN ayarlama yönergeleri](vpn-setting-configure-per-app.md).
  - **Sağlayıcı türü**: Yalnızca, Pulse Secure ve özel VPN için de kullanılabilir.
  - Pulse Secure veya Özel VPN ile iOS **uygulama başına VPN** profillerini kullanırken uygulama katmanı tünelini (app-proxy) veya paket düzeyi tüneli (packet-tunnel) seçin. **ProviderType** değerini uygulama katmanı tüneli için **app-proxy** olarak veya paket katmanı tüneli için **packet-tunnel** ayarlayın. Hangi değeri kullanmanız gerektiğini bilmiyorsanız VPN sağlayıcınızın belgelerine bakın.
  - **Bu VPN'i tetikleyecek safari URL'leri**: Bir veya daha fazla web sitesi URL'si ekleyin. Bu URL’ler cihazda Safari tarayıcıyla ziyaret edildiğinde, VPN bağlantısı otomatik olarak kurulur.

- **İsteğe bağlı VPN**: VPN bağlantısı başlatıldığında denetleyen koşullu kurallar yapılandırın. Örneğin, yalnızca cihaz şirketin Wi-Fi ağına bağlı olmadığında VPN bağlantısının kullanılacağı bir koşul oluşturun. Veya, bir koşul oluşturun. Örneğin, bir cihaz DNS arama etki alanına erişememesi durumunda, girin ve ardından VPN bağlantısını kullanmaya değil.

  - **Ssıd'ler veya DNS arama etki alanları**: Bu koşulun kablosuz ağ kullanıp kullanmayacağını seçin **Ssıd'ler**, veya **DNS arama etki alanları**. Bir veya birden çok SSID veya arama etki alanı yapılandırmak için **Ekle**’yi seçin.
  - **URL dizesi araştırması**: İsteğe bağlı. Kuralın test olarak kullanacağı bir URL girin. Bu profille cihaz bu URL'ye yeniden yönlendirmesiz erişiyorsa, VPN bağlantısı başlatılır. Cihaz hedef URL’ye bağlanır. Kullanıcı, URL dize araştırma sitesini görmez. URL dize yoklaması, VPN’i bağlamadan önce cihaz uyumluluğunu denetleyen bir denetim Web sunucusunun adresidir. Başka bir seçenek de URL’nin, cihazı VPN aracılığıyla hedef URL’ye bağlamadan önce VPN’in bir siteye bağlanma yeteneğini sınamasıdır.
  - **Etki alanı eylemi**: Aşağıdaki öğelerden birini seçin:
    - Gerekirse bağlan
    - Hiçbir zaman bağlanma
  - **Eylem**: Aşağıdaki öğelerden birini seçin:
    - Bağlanma
    - Bağlantıyı değerlendir
    - Yoksayma
    - Bağlantıyı Kes

## <a name="proxy-settings"></a>Proxy ayarları

Proxy kullanıyorsanız aşağıdaki ayarları yapılandırın. Proxy ayarları, Zscaler VPN bağlantıları için kullanılamaz.  

- **Otomatik yapılandırma betiği**: Proxy sunucusunu yapılandırmak için bir dosya kullanın. Yapılandırma dosyasını içeren **Proxy sunucu URL’si** (örneğin `http://proxy.contoso.com`) değerini girin.
- **Adresi**: Proxy sunucusunun tam ana bilgisayar adını IP adresini girin.
- **Bağlantı noktası numarası**: Proxy sunucusuyla ilişkilendirilmiş bağlantı noktası numarasını girin.

## <a name="next-step"></a>Sonraki adım
[Intune’da VPN profilleri oluşturma](vpn-settings-configure.md)  
