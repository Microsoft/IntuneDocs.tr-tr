---
title: Microsoft Intune-Azure 'da Windows Phone 8,1 cihazlarında VPN ayarlarını yapılandırma | Microsoft Docs
description: Bağlantı ayrıntıları ve IP veya FQDN adresi dahil edilecek proxy ayarları ve Windows Phone 8,1 çalıştıran cihazlarda Microsoft Intune TCP bağlantı noktası dahil sanal özel ağ (VPN) yapılandırma ayarlarını kullanarak bir VPN yapılandırma profili ekleyin veya oluşturun.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/19/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 70f33fe132eb6c3dbf91c5dc313369d75f4f3e24
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/19/2019
ms.locfileid: "75207035"
---
# <a name="add-vpn-settings-on-windows-phone-81-devices-in-microsoft-intune"></a>Microsoft Intune Windows Phone 8,1 cihazlarına VPN ayarları ekleme



Bu makale, Windows Phone 8.1 çalıştıran cihazlarda VPN bağlantılarını yapılandırmak için kullanabileceğiniz Intune ayarları hakkında bilgi sağlar. 

Seçtiğiniz ayarlara bağlı olarak, aşağıdaki listede yer alan değerlerden bazıları yapılandırılamaz.

>[!IMPORTANT]
>Windows Phone 8,1 VPN profilleri Windows 10 cihazlarına da uygulanır.

## <a name="base-vpn-settings"></a>Temel VPN ayarları

- **Tüm ayarları yalnızca Windows Phone 8,1 Uygula**: klasik Intune portalında bu ayarı yapılandırın. Microsoft Endpoint Manager Yönetim Merkezi 'nde Bu ayar değiştirilemez. **Yapılandırılmış**olarak ayarlandığında, tüm ayarlar yalnızca Windows Phone 8,1 cihazlarına uygulanır. **Yapılandırılmadı**olarak ayarlandığında, bu ayarlar Windows 10 Mobile cihazları için de geçerlidir.
- **Bağlantı adı**: Bu bağlantı için bir ad girin. Cihazlarındaki kullanılabilir VPN bağlantılarına göz atan kullanıcılar bu adı görür.
- **Kimlik doğrulama yöntemi**: Cihazların VPN sunucusunda kimliklerini nasıl doğrulayacaklarını seçin:
  - **Sertifikalar**: **kimlik doğrulama sertifikası**altında, bağlantının kimliğini doğrulamak için daha önce oluşturduğunuz bir SCEP veya PKCS sertifika profilini seçin. Sertifika profilleri hakkındaki daha fazla bilgi için bkz. [Sertifikaları yapılandırma](../protect/certificates-configure.md).
  - **Kullanıcı adı ve parola**: son kullanıcılar VPN sunucusunda oturum açmak için bir Kullanıcı adı ve parola sağlamalıdır.
- **Sunucular**: Cihazların bağlandığı bir veya birden çok VPN sunucusu ekleyin.
  - **Ekle**: aşağıdaki bilgileri belirtebileceğiniz **satır ekle** dikey penceresini açar:
    - **Açıklama**: sunucu IÇIN **contoso VPN sunucusu**gibi açıklayıcı bir ad belirtin.
    - **IP adresi veya FQDN**: CIHAZLARıN bağlanacağı VPN sunucusunun IP adresini veya tam etki alanı adını belirtin. Örnekler: **192.168.1.1**, **vpn.contoso.com**.
    - **Varsayılan sunucu**: Bu sunucuyu, cihazların bağlantı oluşturmak için kullandığı varsayılan sunucu olarak etkinleştirir. Varsayılan sunucu olarak tek bir sunucu ayarladığınızdan emin olun.
  - **Içeri aktar**: Açıklama, IP adresı veya FQDN, varsayılan sunucu biçiminde bir sunucu listesini içeren virgülle ayrılmış bir dosyaya gidin. **Tamam**'ı seçerek bu sunucuları **Sunucular** listesine içeri aktarın.
  - **Dışarı aktar**: sunucu listesini virgülle ayrılmış değerler (CSV) dosyasına aktarır.

- **Şirket Wi-Fi AĞıNDA VPN 'ı atlama**: cihaz şirket Wi-Fi AĞıNA bağlıyken VPN bağlantılarının kullanılmayacağını belirtmek için bu seçeneği etkinleştirin.
- **Ana Wi-Fi AĞıNDA VPN 'ı atlama**: cihaz bir ev Wi-Fi AĞıNA bağlıyken VPN bağlantısının kullanılmayacağını belirtmek için bu seçeneği etkinleştirin.

- **Bağlantı türü**: Aşağıdaki satıcı listesinden VPN bağlantı türünü seçin:
  - **Check Point Capsule VPN**
  - **SonicWall Mobile Connect**
  - **F5 Edge Client**
  - **Pulse Secure**

- **Oturum açma grubu veya etki alanı** (yalnızca SonicWALL mobil bağlantı): bağlanmak istediğiniz oturum açma grubu veya etki alanı adını belirtin.
- **Rol** (yalnızca Pulse Secure): bu bağlantıya erişimi olan kullanıcı rolünün adını belirtin. Bir kullanıcı rolü, kişisel ayarları ve seçenekleri tanımlar, belirli erişim özelliklerini etkinleştirir veya devre dışı bırakır.
- **Bölge** (yalnızca Pulse Secure): kullanmak istediğiniz kimlik doğrulama bölgesi adını belirtin. Bir kimlik doğrulaması bölgesi, Pulse Secure bağlantı türü tarafından kullanılan kimlik doğrulaması kaynakları gruplandırmasıdır.

- **DNS son eki arama listesi**: bir veya daha fazla DNS **ekleyin** . Bir web sitesine kısa ad kullanarak bağlanılırken, belirttiğiniz her DNS soneki aranır. Örneğin **etkialanı1.contoso.com** ve **etkialanı2.contoso.com** DNS son eklerini belirtin ve `http://mywebsite` URL’yi ziyaret edin, böylece `http://mywebsite.domain1.contoso.com` ve `http://mywebsite.domain2.contoso.com` URL’leri aranır.

- **Özel XML**: VPN bağlantısını YAPıLANDıRAN özel xml komutlarını belirtin.

  **Pulse Secure örneği**:

  ```xml
  <pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>
  ```

  **Checkpoint MOBILE VPN örneği**:

  ```xml
  <CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />
  ```

  **SonicWALL Mobile Connect örneği**:

  ```xml
  <MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>
  ```

  **F5 Edge Client örnek**:

  ```xml
  <f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>
  ```

  Özel XML komutları yazma hakkında daha fazla bilgi için üreticinin VPN belgelerine bakın.

- **Bölünmüş tünel**: cihazların trafiğe bağlı olarak hangi bağlantının kullanılacağına karar vermesine olanak sağlayan bu seçeneği **etkinleştirin** veya **devre dışı bırakın** . Örneğin, oteldeki bir kullanıcı çalışma dosyalarına erişmek için VPN bağlantısını, web’e göz atmak için ise otelin standart ağını kullanır.

## <a name="proxy-settings"></a>Proxy ayarları

- **Proxy ayarlarını otomatik olarak algıla**: VPN sunucunuz bağlantı için proxy sunucusu gerektiriyorsa, cihazların bağlantı ayarlarını otomatik olarak algılamasını isteyip istemediğinizi belirtin.
- **Otomatik yapılandırma betiği**: Proxy sunucusunu yapılandırmak için bir dosya kullanın. Yapılandırma dosyasını içeren **Proxy sunucu URL’si** (örneğin `http://proxy.contoso.com`) değerini girin.
- Proxy sunucusu **kullan**: proxy sunucu ayarlarını el ile girmek istiyorsanız bu seçeneği etkinleştirin.
  - **Adres**: proxy sunucu adresini (bir IP adresi olarak) girin.
  - **Bağlantı noktası numarası**: Proxy sunucusuyla ilişkilendirilmiş bağlantı noktası numarasını girin.
- **Yerel adresler için proxy 'Yi atla**: VPN sunucunuz bağlantı için bir ara sunucu gerektiriyorsa ve girdiğiniz yerel adresler için proxy sunucusunu kullanmak istemiyorsanız, bu seçeneği belirleyin.

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturulur ancak henüz herhangi bir işlem gerçekleştirmez. Ardından [profili atayın](device-profile-assign.md) ve [durumunu izleyin](device-profile-monitor.md).

[Android](vpn-settings-android.md), [Android Enterprise](vpn-settings-android-enterprise.md), [MacOS](vpn-settings-macos.md)ve [Windows 10](vpn-settings-windows-10.md) cihazlarında VPN ayarlarını yapılandırın.
