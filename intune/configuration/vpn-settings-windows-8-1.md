---
title: Microsoft Intune-Azure 'da Windows 8.1 cihazlarda VPN ayarlarını yapılandırma | Microsoft Docs
description: Bağlantı ayrıntıları ve IP veya FQDN adresi dahil edilecek proxy ayarları ve Windows 8.1 çalıştıran cihazlarda Microsoft Intune TCP bağlantı noktası dahil olmak üzere sanal özel ağ (VPN) yapılandırma ayarlarını kullanarak bir VPN yapılandırma profili ekleyin veya oluşturun.
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
ms.openlocfilehash: 9f9a1399d5474d79ac8fd48a8aa3a844f20eb640
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/19/2019
ms.locfileid: "75207052"
---
# <a name="add-vpn-settings-on-windows-81-devices-in-microsoft-intune"></a>Microsoft Intune Windows 8.1 cihazlara VPN ayarları ekleme



Bu makale, Windows 8.1 çalıştıran cihazlarda VPN bağlantılarını yapılandırmak için kullanabileceğiniz Intune ayarları hakkında bilgi sağlar.

Seçtiğiniz ayarlara bağlı olarak, aşağıdaki listede yer alan değerlerden bazıları yapılandırılamaz.

## <a name="base-vpn-settings"></a>Temel VPN ayarları

- **Tüm ayarları yalnızca Windows 8.1 Uygula**: klasik Intune portalında bu ayarı yapılandırın. Microsoft Endpoint Manager Yönetim Merkezi 'nde Bu ayar değiştirilemez. **Yapılandırılmış**olarak ayarlandığında, tüm ayarlar yalnızca Windows 8.1 cihazlara uygulanır. **Yapılandırılmadı**olarak ayarlandığında, bu ayarlar Windows 10 cihazlarına da uygulanır.
- **Bağlantı adı**: Bu bağlantı için bir ad girin. Cihazlarındaki kullanılabilir VPN bağlantılarına göz atan kullanıcılar bu adı görür.
- **Sunucular**: Cihazların bağlandığı bir veya birden çok VPN sunucusu ekleyin.
  - **Ekle**: aşağıdaki bilgileri belirtebileceğiniz **satır ekle** sayfasını açar:
    - **Açıklama**: sunucu IÇIN **contoso VPN sunucusu**gibi açıklayıcı bir ad belirtin.
    - **IP adresi veya FQDN**: CIHAZLARıN bağlanacağı VPN sunucusunun IP adresini veya tam etki alanı adını belirtin. Örnekler: **192.168.1.1**, **vpn.contoso.com**.
    - **Varsayılan sunucu**: Bu sunucuyu, cihazların bağlantı oluşturmak için kullandığı varsayılan sunucu olarak etkinleştirir. Varsayılan sunucu olarak tek bir sunucu ayarladığınızdan emin olun.
  - **Içeri aktar**: tanım, IP adresı veya FQDN, varsayılan sunucu biçiminde sunucu listesini içeren virgülle ayrılmış bir dosyaya gidin. **Tamam**'ı seçerek bu sunucuları **Sunucular** listesine içeri aktarın.
  - **Dışarı aktar**: sunucu listesini virgülle ayrılmış değerler (CSV) dosyasına aktarır.

- **Bağlantı türü**: Aşağıdaki satıcı listesinden VPN bağlantı türünü seçin:
  - **Check Point Capsule VPN**
  - **SonicWall Mobile Connect**
  - **F5 Edge Client**
  - **Pulse Secure**

<!--- **Fingerprint** (Check Point Capsule VPN only): Specify a string (for example, "Contoso Fingerprint Code") that will be used to verify that the VPN server can be trusted. A fingerprint can be sent to the client so it knows to trust any server that presents the same fingerprint when connecting. If the device doesn’t already have the fingerprint, it will prompt the user to trust the VPN server that they are connecting to while showing the fingerprint. (The user manually verifies the fingerprint and chooses **trust** to connect.) --->

- **Oturum açma grubu veya etki alanı** (yalnızca SonicWALL mobil bağlantı): bağlanmak istediğiniz oturum açma grubu veya etki alanı adını belirtin.

- **Rol** (yalnızca Pulse Secure): bu bağlantıya erişimi olan kullanıcı rolünün adını belirtin. Bir kullanıcı rolü, kişisel ayarları ve seçenekleri tanımlar, belirli erişim özelliklerini etkinleştirir veya devre dışı bırakır.

- **Bölge** (yalnızca Pulse Secure): kullanmak istediğiniz kimlik doğrulama bölgesi adını belirtin. Bir kimlik doğrulaması bölgesi, Pulse Secure bağlantı türü tarafından kullanılan kimlik doğrulaması kaynakları gruplandırmasıdır.

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

## <a name="proxy-settings"></a>Proxy ayarları

- **Proxy ayarlarını otomatik olarak algıla**: VPN sunucunuz bağlantı için proxy sunucusu gerektiriyorsa, cihazların bağlantı ayarlarını otomatik olarak algılamasını isteyip istemediğinizi belirtin.
- **Otomatik yapılandırma betiği**: Proxy sunucusunu yapılandırmak için bir dosya kullanın. Yapılandırma dosyasını içeren **Proxy sunucu URL'sini** girin. Örneğin, şunu girin: `http://proxy.contoso.com`.
- Proxy sunucusu **kullan**: proxy sunucu ayarlarını el ile girmek istiyorsanız bu seçeneği etkinleştirin.
  - **Adres**: proxy sunucu adresini (bir IP adresi olarak) girin.
  - **Bağlantı noktası numarası**: Proxy sunucusuyla ilişkilendirilmiş bağlantı noktası numarasını girin.
- **Yerel adresler için proxy 'Yi atla**: VPN sunucunuz bağlantı için bir ara sunucu gerektiriyorsa ve girdiğiniz yerel adresler için proxy sunucusunu kullanmak istemiyorsanız, bu seçeneği belirleyin.

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturulur ancak henüz herhangi bir işlem gerçekleştirmez. Ardından [profili atayın](device-profile-assign.md) ve [durumunu izleyin](device-profile-monitor.md).

[Android](vpn-settings-android.md), [Android Enterprise](vpn-settings-android-enterprise.md), [MacOS](vpn-settings-macos.md)ve [Windows 10](vpn-settings-windows-10.md) cihazlarında VPN ayarlarını yapılandırın.
