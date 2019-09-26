---
title: Microsoft Intune - Azure’da macOS cihazlar için Wi-Fi ayarlarını içeri aktarma - Azure | Microsoft Docs
titleSuffix: ''
description: macOS cihazlar için bir Wi-Fi cihaz yapılandırma profili oluşturun veya ekleyin. Microsoft Intune’da sertifika ekleme, EAP türü seçme ve bir kimlik doğrulama yöntemi seçme gibi farklı ayarları görün.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/09/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0692a8ac0bcd1fd415d0bceb7f5a269648dd5b30
ms.sourcegitcommit: c19584b36448bbd4c8638d7cab552fe9b3eb3408
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/20/2019
ms.locfileid: "71302558"
---
# <a name="add-wi-fi-settings-for-macos-devices-in-microsoft-intune"></a>Microsoft Intune’da macOS cihazlar için Wi-Fi ayarları ekleme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Belirli Wi-Fi ayarları ile bir profil oluşturabilir ve ardından bu profili macOS cihazlarınıza dağıtabilirsiniz. Microsoft Intune; ağınızda kimlik doğrulama, bir PKS veya SCEP sertifikası ekleme ve daha fazlası gibi pek çok özellik sunar.

Bu Wi-Fi ayarları iki kategoride ayrılır: Temel ayarlar ve kurumsal düzeyde ayarlar.

Bu makalede bu ayarlar açıklanır.

## <a name="before-you-begin"></a>Başlamadan önce

[Cihaz profili oluşturma](device-profile-create.md).

> [!NOTE]
> Bu ayarlar tüm kayıt türleri için kullanılabilir. Kayıt türleri hakkında daha fazla bilgi için bkz. [MacOS kaydı](macos-enroll.md).

## <a name="basic-profiles"></a>Temel profiller

- **Wi-Fi türü**: **Temel**’i seçin.
- **Ağ adı**: Bu Wi-Fi bağlantısı için bir ad girin. Bu değer, kullanıcıların cihazlarında kullanılabilir bağlantılar listesine göz attıklarında görecekleri addır.
- **SSID**: **Hizmet kümesi tanımlayıcısı**için kısa. Bu özellik, cihazların bağlandığı kablosuz ağın gerçek adıdır. Bununla birlikte, bağlantıyı seçen kullanıcılar yalnızca yapılandırdığınız ağ adını görür.
- **Otomatik olarak bağlan**: Cihaz Aralık içinde olduğunda bu ağa otomatik olarak bağlanmak için **Etkinleştir** ' i seçin. Cihazların otomatik olarak bağlanmasını önlemek için **Devre dışı bırak**’ı seçin.
- **Gizli ağ**: Bu ağı cihazdaki kullanılabilir ağlar listesinden gizlemek için **Etkinleştir** ' i seçin. SSID yayınlanmaz. Cihazdaki kullanılabilir ağlar listesinde bu ağı göstermek için **Devre dışı bırak**’ı seçin.
- **Güvenlik türü**: Wi-Fi ağına kimlik doğrulaması yapmak için güvenlik protokolünü seçin. Seçenekleriniz şunlardır:

  - **Açık (kimlik doğrulaması yok)** : Yalnızca ağ güvenli değilse bu seçeneği kullanın.
  - **WPA/WPA2-Kişisel**: **Önceden paylaşılan anahtar**parolayı girin. Kuruluşunuzun ağı ayarlandığında veya yapılandırıldığında bir parola veya ağ anahtarı da yapılandırılır. PSK değeri için bu parolayı veya ağ anahtarını girin.
  - **4**

- **Ara sunucu ayarları**: Seçenekleriniz şunlardır:
  - **Hiçbiri**: Yapılandırılmış bir proxy ayarı yok.
  - **El ile**: **Proxy sunucu adresini** bir IP adresi olarak ve **bağlantı noktası numarasını**girin.
  - **Otomatik**: Proxy sunucusunu yapılandırmak için bir dosya kullanın. Yapılandırma dosyasını içeren **Proxy sunucu URL’si** (örneğin `http://proxy.contoso.com`) değerini girin.

## <a name="enterprise-profiles"></a>Kurumsal profiller

- **Wi-Fi türü**: **Kuruluş**' ı seçin.
- **SSID**: **Hizmet kümesi tanımlayıcısı**için kısa. Bu özellik, cihazların bağlandığı kablosuz ağın gerçek adıdır. Bununla birlikte, bağlantıyı seçen kullanıcılar yalnızca yapılandırdığınız ağ adını görür.
- **Otomatik olarak bağlan**: Cihaz Aralık içinde olduğunda bu ağa otomatik olarak bağlanmak için **Etkinleştir** ' i seçin. Cihazların otomatik olarak bağlanmasını önlemek için **Devre dışı bırak**’ı seçin.
- **Gizli ağ**: Bu ağı cihazdaki kullanılabilir ağlar listesinden gizlemek için **Etkinleştir** ' i seçin. SSID yayınlanmaz. Cihazdaki kullanılabilir ağlar listesinde bu ağı göstermek için **Devre dışı bırak**’ı seçin.

- **EAP türü**: Güvenli kablosuz bağlantıların kimliğini doğrulamak için kullanılan Genişletilebilir Kimlik Doğrulama Protokolü (EAP) türünü seçin. Seçenekleriniz şunlardır:

  - **EAP-HIZLI**: **Korumalı erişim kimlik bilgisi (PAC) ayarlarını**girin. Bu seçenek, istemci ile kimlik doğrulama sunucusu arasında kimliği doğrulanmış bir tünel oluşturmak için korumalı erişim kimlik bilgilerini kullanır. Seçenekleriniz şunlardır:
    - **(PAC) kullanma**
    - **Kullan (PAC)** : Mevcut bir PAC dosyası varsa, bunu kullanın.
    - **Pac kullanma ve sağlama**: PAC dosyasını oluşturun ve cihazlarınıza ekleyin.
    - **Pac kullanma ve sağlamayı adsız olarak sağlama**: Sunucu kimlik doğrulaması yapmadan PAC dosyasını cihazlarınıza oluşturun ve ekleyin.

  - **EAP-SIM**

  - **EAP-TLS**: Şunları da girin:

    - **Sunucu güven** - **sertifikası sunucu adları**: Güvenilen sertifika yetkiliniz (CA) tarafından verilen sertifikalarda kullanılan bir veya daha fazla ortak ad **ekleyin** . Bu bilgiyi girdikten sonra bu Wi-Fi ağına bağlanırken kullanıcının cihazında görüntülenen dinamik güven penceresini atlayabilirsiniz.
    - **Sunucu doğrulaması Için kök sertifika**: Var olan bir güvenilen kök sertifika profili seçin. Bu sertifika, istemci ağa bağlandığında sunucuya sunulur ve bağlantının kimliğini doğrulamak için kullanılır.

    -  - İstemci**kimlik doğrulaması (kimlik sertifikası) için**istemci kimlik doğrulama istemci sertifikası: Cihaza de dağıtılan SCEP veya PKCS istemci sertifikası profilini seçin. Bu sertifika, bağlantının kimliğini doğrulamak için cihaz tarafından sunucuya sunulan kimliktir.

  - **EAP-TTLS**: Şunları da girin:

    - **Sunucu güven** - **sertifikası sunucu adları**: Güvenilen sertifika yetkiliniz (CA) tarafından verilen sertifikalarda kullanılan bir veya daha fazla ortak ad **ekleyin** . Bu bilgiyi girdikten sonra bu Wi-Fi ağına bağlanırken kullanıcının cihazında görüntülenen dinamik güven penceresini atlayabilirsiniz.
    - **Sunucu doğrulaması Için kök sertifika**: Var olan bir güvenilen kök sertifika profili seçin. Bu sertifika, istemci ağa bağlandığında sunucuya sunulur ve bağlantının kimliğini doğrulamak için kullanılır.

    - **İstemci Kimlik Doğrulaması** - Bir **Kimlik doğrulama yöntemi** seçin. Seçenekleriniz şunlardır:

      - **Kullanıcı adı ve parola**: Bağlantının kimliğini doğrulamak için kullanıcıdan bir Kullanıcı adı ve parola iste. Şunları da girin:
        - **EAP olmayan Yöntem (iç kimlik)** : Bağlantının kimliğini nasıl doğrulayacağınızı seçin. Wi-Fi ağınızda yapılandırılmış olan protokolü seçtiğinizden emin olun.

          Seçenekleriniz şunlardır: **Şifrelenmemiş parola (PAP)** , **karşılıklı kimlik doğrulama protokolü (CHAP)** , **Microsoft CHAP (ms-CHAP)** veya **Microsoft CHAP sürüm 2 (MS-CHAP v2)**

      - **Sertifikalar**: Cihaza de dağıtılan SCEP veya PKCS istemci sertifikası profilini seçin. Bu sertifika, bağlantının kimliğini doğrulamak için cihaz tarafından sunucuya sunulan kimliktir.

      - **Kimlik gizliliği (dış kimlik)** : Bir EAP kimlik isteğine yanıt olarak gönderilen metni girin. Bu metin herhangi bir değer olabilir, örneğin `anonymous`. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.

  - **LEAP**

  - **PEAP**: Şunları da girin:

    - **Sunucu güven** - **sertifikası sunucu adları**: Güvenilen sertifika yetkiliniz (CA) tarafından verilen sertifikalarda kullanılan bir veya daha fazla ortak ad **ekleyin** . Bu bilgiyi girdikten sonra bu Wi-Fi ağına bağlanırken kullanıcının cihazında görüntülenen dinamik güven penceresini atlayabilirsiniz.
    - **Sunucu doğrulaması Için kök sertifika**: Var olan bir güvenilen kök sertifika profili seçin. Bu sertifika, istemci ağa bağlandığında sunucuya sunulur ve bağlantının kimliğini doğrulamak için kullanılır.

    - **İstemci Kimlik Doğrulaması** - Bir **Kimlik doğrulama yöntemi** seçin. Seçenekleriniz şunlardır:

      - **Kullanıcı adı ve parola**: Bağlantının kimliğini doğrulamak için kullanıcıdan bir Kullanıcı adı ve parola iste. 

      - **Sertifikalar**: Cihaza de dağıtılan SCEP veya PKCS istemci sertifikası profilini seçin. Bu sertifika, bağlantının kimliğini doğrulamak için cihaz tarafından sunucuya sunulan kimliktir.

      - **Kimlik gizliliği (dış kimlik)** : Bir EAP kimlik isteğine yanıt olarak gönderilen metni girin. Bu metin herhangi bir değer olabilir, örneğin `anonymous`. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.

- **Ara sunucu ayarları**: Seçenekleriniz şunlardır:
  - **Hiçbiri**: Yapılandırılmış bir proxy ayarı yok.
  - **El ile**: **Proxy sunucu adresini** bir IP adresi olarak ve **bağlantı noktası numarasını**girin.
  - **Otomatik**: Proxy sunucusunu yapılandırmak için bir dosya kullanın. Yapılandırma dosyasını içeren **Proxy sunucu URL’si** (örneğin `http://proxy.contoso.com`) değerini girin.

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturuldu ancak hiçbir şey yapmıyor. Sonra, [Bu profili atayın](device-profile-assign.md) ve [durumunu izleyin](device-profile-monitor.md).

[Android](wi-fi-settings-android.md), [Android Enterprise](wi-fi-settings-android-enterprise.md), [IOS](wi-fi-settings-ios.md)ve [Windows 10](wi-fi-settings-windows.md) cihazlarında Wi-Fi ayarlarını yapılandırın.
