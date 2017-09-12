---
title: "iOS cihazları için Intune VPN ayarları"
titlesuffix: Azure portal
description: "iOS cihazlarda VPN bağlantılarını yapılandırmak için kullanabileceğiniz Intune ayarlarını öğrenin.\""
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1447c123-ea33-4ea0-aab4-69577cdb8d00
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d623f44b8765a29a998a9ddd3911d2d7da690caa
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/09/2017
---
# <a name="vpn-settings-for-ios-devices-in-microsoft-intune"></a>Microsoft Intune’da iOS cihazları için VPN ayarları

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Seçtiğiniz ayarlara bağlı olarak, aşağıdaki listede yer alan değerlerden bazıları yapılandırılamaz.

## <a name="base-vpn-settings"></a>Temel VPN ayarları


**Bağlantı adı** - Bu bağlantı için bir ad girin. Cihazlarındaki kullanılabilir VPN bağlantılarına göz atan son kullanıcılar bu adı görür.
- **IP adresi veya FQDN** - Cihazların bağlanacağı VPN sunucusunun IP adresini veya tam etki alanı adını sağlayın. Örnekler: **192.168.1.1**, **vpn.contoso.com**.
- **Kimlik doğrulama yöntemi** - Cihazların VPN sunucusuna kimliklerini nasıl doğrulayacaklarını seçin:
    - **Sertifikalar** - **Kimlik doğrulama sertifikası**’nın altında, bağlantının kimliğini doğrulamak için daha önce oluşturduğunuz SCEP veya PKCS sertifika profilini seçin. Sertifika profilleri hakkındaki daha fazla bilgi için bkz. [Sertifikaları yapılandırma](certificates-configure.md).
    - **Kullanıcı adı ve parola** - Son kullanıcıların VPN sunucusunda oturum açmak için kullanıcı adı ve parola sağlaması gerekir.
- **Bağlantı türü** - Aşağıdaki satıcı listesinden VPN bağlantı türünü seçin:
    - **Check Point Capsule VPN**
    - **Cisco AnyConnect**
    - **Dell SonicWALL Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**
    - **Cisco (IPSec)**
    - **Citrix**
    - **Özel VPN**
- **Bölünmüş tünel** - Trafiğe bağlı olarak hangi bağlantının kullanılacağına cihazların karar vermesini sağlayan bu seçeneği **Etkinleştirin** veya **Devre Dışı Bırakın**. Örneğin, oteldeki bir kullanıcı çalışma dosyalarına erişmek için VPN bağlantısını, web’e göz atmak için ise otelin standart ağını kullanır.


## <a name="custom-vpn-settings"></a>Özel VPN ayarları

Bağlantı türü olarak **Özel VPN**’yi seçtiyseniz şu ek ayarları yapılandırın:

- **VPN tanımlayıcısı** Bu, kullandığınız VPN uygulamasının tanımlayıcısıdır ve VPN sağlayıcınız tarafından verilir.
- **Özel VPN öznitelikleri için anahtar ve değer çiftlerini girin** VPN bağlantınızı özelleştiren **Anahtarlar** ve **Değerler**’i ekleyin veya içeri aktarın. Yinelemek gerekirse, bu değerler normalde VPN sağlayıcınız tarafından verilir.

## <a name="apps-per-app-vpn-settings"></a>Uygulama (uygulama başına VPN) ayarları

- **Uygulama başına VPN** - Safari tarayıcısından ziyaret edildiğinde VPN bağlantısını etkinleştirecek URL’ler isterseniz bu seçeneği etkinleştirin. Bunu yapılandırmak için, temel VPN ayarlarında kimlik doğrulama yöntemi olarak **Sertifikalar**’ı seçmiş olmalısınız.
- **Safari tarayıcısını kullanırken VPN bağlantısını etkinleştirecek URL'leri belirtin** - Bir veya birden çok web sitesi URL’si eklemek için Ekle’ye tıklayın. Bu URL’ler ziyaret edildiğinde, VPN bağlantısı etkinleştirilir.

- **İsteğe bağlı kurallar** - VPN bağlantısının ne zaman başlatılacağını denetleyen koşullu kuralları yapılandırmanıza olanak tanır. Örneğin, yalnızca cihaz şirketinizin Wi-Fi ağlarından birine bağlı olmadığında VPN bağlantısının kullanılacağına ilişkin bir koşul oluşturabilirsiniz. Alternatif olarak, cihazın belirttiğiniz DNS arama etki alanına erişememesi durumunda VPN bağlantısının başlatılmayacağına ilişkin bir koşul da oluşturmanız mümkündür.

    - **SSID’ler veya DNS arama etki alanları** - Bu koşulun kablosuz ağ **SSID’lerini** mi yoksa **DNS arama etki alanlarını** mı kullanacağını seçin. Bir veya birden çok SSID veya arama etki alanı yapılandırmak için Ekle’yi seçin.
    - **URL dizesi araştırması** - İsteğe bağlı olarak, kuralın test için kullanacağı bir URL sağlayın. Bu profilin yüklü olduğu cihaz bu URL’ye yeniden yönlendirmesiz erişebiliyorsa VPN bağlantısı başlatılır ve cihaz hedef URL’ye bağlanır. Kullanıcı, URL araştırma dizesi sitesini görmez. URL araştırma dizesine örnek, VPN’i bağlamadan önce cihaz uyumluluğunu denetleyen bir denetim Web sunucusunun adresidir. Başka bir seçenek de URL’nin, cihazı VPN aracılığıyla hedef URL’ye bağlamadan önce VPN’in bir siteye bağlanma yeteneğini sınamasıdır.
    - **Etki alanı eylemi** - Aşağıdaki öğelerden birini seçin:
        - Gerekirse bağlan - 
        - Hiçbir zaman bağlanma - 
    - **Eylem** - Aşağıdaki öğelerden birini seçin:
        - Bağlan - 
        - Bağlantıyı değerlendir - 
        - Yoksay - 
        - Bağlantıyı kes - 


## <a name="proxy-settings"></a>Proxy ayarları

- **Otomatik yapılandırma betiği** - Proxy sunucusunu yapılandırmak için bir dosya kullanın. Yapılandırma dosyasını içeren **Proxy sunucu URL’si** (örneğin **http://proxy.contoso.com**) değerini girin.
- **Adres** - Proxy sunucusu adresini (IP adresi olarak) girin.
- **Bağlantı noktası numarası** - Proxy sunucusuyla ilişkilendirilmiş bağlantı noktası numarasını girin.