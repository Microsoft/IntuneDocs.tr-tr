---
title: Microsoft Intune - Azure’da iOS cihazlar için VPN ayarları | Microsoft Docs
description: iOS çalıştıran cihazlarda Microsoft Intune’da bağlantı ayrıntıları, kimlik doğrulama yöntemleri ve temel ayarlarda bölünmüş tünel; tanımlayıcı ile özel VPN ayarları ve anahtar ve değer çiftleri; Safari URL’lerini içeren uygulama başına VPN ayarları, SSID veya DNS arama etki alanları ile isteğe bağlı VPN’ler; bir yapılandırma betiği, IP veya FQDN adresini içermek için proxy ayarları ve TCP bağlantı noktası dahil olmak üzere kullanılabilir sanal özel ağ (VPN) yapılandırma ayarlarını görüntüleyin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 8/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: deb6a230573ff20237e6eee386052baba472832a
ms.sourcegitcommit: 4d314df59747800169090b3a870ffbacfab1f5ed
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/30/2018
ms.locfileid: "43313879"
---
# <a name="configure-vpn-settings-in-microsoft-intune-for-devices-running-ios"></a>iOS çalıştıran cihazlar için Microsoft Intune'da VPN ayarlarını yapılandırın

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bu makale, iOS çalıştıran cihazlarda VPN bağlantılarını yapılandırmak için kullanabileceğiniz Intune ayarları hakkında bilgi sağlar.

Seçtiğiniz ayarlara bağlı olarak, aşağıdaki listede yer alan değerlerden bazıları yapılandırılamaz.

## <a name="base-vpn-settings"></a>Temel VPN ayarları
Aşağıdaki listede bulunan ayarlardan hangilerini göreceğiniz, seçtiğiniz VPN bağlantı türüne göre belirlenir.  
- **Bağlantı adı**: Cihazlarındaki kullanılabilir VPN bağlantıları listesine göz atan son kullanıcılar bu adı görür.
- **Özel etki alanı adı** (yalnızca Zscaler): Zscaler uygulamasının oturum açma alanını kullanıcılarınızın ait olduğu etki alanı ile önceden doldurun. Örneğin bir kullanıcı **Joe@contoso.net** ise, uygulama açıldığında etki alanı olan **contoso.net** statik olarak görünür. Bir etki alanı adı girmezseniz Azure Active Directory’deki UPN’nin etki alanı kısmı kullanılır.
- **IP adresi veya FQDN**: Cihazların bağlanırken kullandığı VPN sunucusunun IP adresi veya tam etki alanı adı (FQDN). Örneğin, **192.168.1.1** veya **vpn.contoso.com** yazın. 
- **Kuruluşun bulut adı** (yalnızca Zscaler): Kuruluşunuzun sağlandığı bulutun adını yazın. Bu adı bulmak için Zscaler’da oturum açarken kullandığınız URL’ye bakın.  
- **Kimlik doğrulama yöntemi**: Cihazların VPN sunucusunda kimliklerini nasıl doğrulayacaklarını seçin. 
  - **Sertifikalar**: **Kimlik doğrulama sertifikası** altında, bağlantının kimliğini doğrulamak için mevcut bir SCEP veya PKCS sertifika profilini seçin. [Sertifika yapılandırma](certificates-configure.md), sertifika profilleri hakkında rehberlik sağlar.
  - **Kullanıcı adı ve parola**: Son kullanıcıların VPN sunucusunda oturum açmak için kullanıcı adı ve parola girmesi gerekir.  

    > [!NOTE]
    > Cisco IPsec VPN için kimlik doğrulama yöntemi olarak kullanıcı adı ve parola kullanılacaksa bunlar, özel bir Apple Configurator profili ile SharedSecret’ı teslim etmelidir.
  
- **Bağlantı türü**: Aşağıdaki satıcı listesinden VPN bağlantı türünü seçin:
  - **Check Point Capsule VPN**
  - **Cisco Eski AnyConnect**: [Cisco Eski AnyConnect](https://itunes.apple.com/app/cisco-legacy-anyconnect/id392790924) uygulama sürümü 4.0.5x ve öncesi için geçerlidir.
  - **Cisco AnyConnect**: [Cisco AnyConnect](https://itunes.apple.com/app/cisco-anyconnect/id1135064690) uygulama sürümü 4.0.7x ve sonrası için geçerlidir.
  - **SonicWall Mobile Connect**
  - **F5 Access Eski**: F5 Access uygulama sürümü 2.1 ve öncesi için geçerlidir.
  - **F5 Access**: F5 Access uygulama sürümü 3.0 ve sonrası için geçerlidir.
  - **Palo Alto Networks GlobalProtect (Eski)**: Palo Alto Networks GlobalProtect uygulama sürümü 4.1 ve öncesi için geçerlidir.
  - **Palo Alto Networks GlobalProtect**: Palo Alto Networks GlobalProtect uygulama sürümü 5.0 ve sonrası için geçerlidir.
  - **Pulse Secure**
  - **Cisco (IPSec)**
  - **Citrix VPN**
  - **Citrix SSO**
  - **Zscaler**: Zscaler Özel Erişim’i (ZPA) Azure Active Directory hesabınızla tümleştirmenizi gerektirir. Ayrıntılı adımlar için bkz. [Zscaler belgeleri](https://help.zscaler.com/zpa/configuration-example-microsoft-azure-ad#Azure_UserSSO). 
  - **Özel VPN**    

    > [!NOTE]
    > Cisco, Citrix, F5 ve Palo Alto; eski istemcilerinin gelecek iOS sürümü olan iOS 12’de çalışmayacağını duyurdu. En kısa zamanda yeni uygulamalara geçmeniz gerekir. Daha fazla bilgi için bkz. [Microsoft Intune Destek Ekibi Blogu](https://go.microsoft.com/fwlink/?linkid=2013806&clcid=0x409).

* **Dışlanan URL’ler** (yalnızca Zscaler): Zscaler VPN’e bağlıyken, listelenen URL’lere Zscaler bulutu dışında da erişilebilir. 

- **Bölünmüş tünel**: Trafiğe bağlı olarak hangi bağlantının kullanılacağına cihazların karar vermesini sağlamak için bu seçeneği **Etkinleştirin** veya **Devre Dışı Bırakın**. Örneğin, oteldeki bir kullanıcı çalışma dosyalarına erişmek için VPN bağlantısını, web’e göz atmak için ise otelin standart ağını kullanır.   

## <a name="custom-vpn-settings"></a>Özel VPN ayarları

Bağlantı türü olarak **Özel VPN**’i seçtiyseniz şu ayarları yapılandırın. Bu ayarlar, Zscaler ve Citrix bağlantıları için de görünürdür.

- **VPN tanımlayıcısı**: Kullandığınız VPN uygulamasının tanımlayıcısıdır ve VPN sağlayıcınız tarafından verilir.
- **Kuruluşunuzun özel VPN öznitelikleri için anahtar/değer çiftlerini girin**: VPN bağlantınızı özelleştiren **Anahtarlar** ve **Değerler**’i ekleyin veya içeri aktarın. Yinelemek gerekirse, bu değerler normalde VPN sağlayıcınız tarafından verilir.

## <a name="automatic-vpn-settings"></a>Otomatik VPN ayarları

- **Uygulama başına VPN**: Bu seçeneği belirtmek uygulama başına VPN’i etkinleştirir, böylece bazı uygulamalar açıldığında VPN bağlantısı otomatik olarak tetiklenir. Bu seçeneği belirtmeye ek olarak uygulamaları bu VPN profiliyle ilişkilendirmeniz gerekecektir. Daha fazla ayrıntı için [iOS için uygulama başına VPN ayarlama yönergelerine](vpn-setting-configure-per-app.md) bakın. 
  - **Sağlayıcı Türü** ayarı, yalnızca Pulse Secure ve Özel VPN için kullanılabilirdir.
  - Pulse Secure veya Özel VPN ile iOS **uygulama başına VPN** profillerini kullanırken uygulama katman tüneli (uygulama-proxy) veya paket düzeyi tünel (paket-tünel) kullanabilirsiniz. **ProviderType** değerini uygulama katmanı tüneli için **app-proxy** olarak veya paket katmanı tüneli için **packet-tunnel** olarak ayarlayın. Hangi değeri kullanacağınızdan emin değilseniz VPN sağlayıcınızın belgelerine bakın. 
  - **Bu VPN’i tetikleyecek Safari URL’leri**: Eklenecek bir veya daha fazla web sitesi URL’si seçin. Bu URL’ler cihazda Safari tarayıcıyla ziyaret edildiğinde, VPN bağlantısı otomatik olarak kurulur.

- **İsteğe bağlı VPN**: VPN bağlantısının ne zaman başlatılacağını denetleyen koşullu kurallar yapılandırın. Örneğin, yalnızca cihaz şirketin Wi-Fi ağına bağlı olmadığında VPN bağlantısının kullanılacağına ilişkin bir koşul oluşturun. Veya cihazın belirttiğiniz DNS’in arama etki alanına erişememesi durumunda VPN bağlantısının başlatılmayacağına ilişkin bir koşul oluşturun.

  - **SSID’ler veya DNS arama etki alanları**: Bu koşulun kablosuz ağ **SSID’lerini** mi yoksa **DNS arama etki alanlarını** mı kullanacağını seçin. Bir veya birden çok SSID veya arama etki alanı yapılandırmak için **Ekle**’yi seçin.
  - **URL dizesi araştırması**: İsteğe bağlıdır. Kuralın test olarak kullanacağı bir URL girin. Bu profilin yüklü olduğu cihaz, bu URL’ye yeniden yönlendirmesiz erişebiliyorsa VPN bağlantısı başlatılır ve cihaz, hedef URL’ye bağlanır. Kullanıcı, URL araştırma dizesi sitesini görmez. URL dize yoklaması, VPN’i bağlamadan önce cihaz uyumluluğunu denetleyen bir denetim Web sunucusunun adresidir. Başka bir seçenek de URL’nin, cihazı VPN aracılığıyla hedef URL’ye bağlamadan önce VPN’in bir siteye bağlanma yeteneğini sınamasıdır.
  - **Etki alanı eylemi**: Aşağıdaki öğelerden birini seçin:
    - Gerekirse bağlan
    - Hiçbir zaman bağlanma
  - **Eylem**: Aşağıdaki öğelerden birini seçin:
    - Bağlanma
    - Bağlantıyı değerlendir
    - Yoksay
    - Bağlantıyı kes

## <a name="proxy-settings"></a>Proxy ayarları
Proxy kullanıyorsanız aşağıdaki ayarları yapılandırın. Proxy ayarları, Zscaler VPN bağlantıları için kullanılamaz.  

- **Otomatik yapılandırma betiği**: Proxy sunucusunu yapılandırmak için bir dosya kullanın. Yapılandırma dosyasını içeren **Proxy sunucu URL’si** (örneğin **http://proxy.contoso.com**) değerini girin.
- **Adres**: Proxy sunucusunun tam konak adına ait IP adresini girin.
- **Bağlantı noktası numarası**: Proxy sunucusuyla ilişkilendirilmiş bağlantı noktası numarasını girin.

## <a name="next-step"></a>Sonraki adım
[Intune’da VPN profilleri oluşturma](vpn-settings-configure.md)  
