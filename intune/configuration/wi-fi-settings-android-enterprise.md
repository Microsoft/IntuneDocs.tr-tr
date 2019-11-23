---
title: Wi-Fi settings for Android Enterprise and kiosk devices - Microsoft Intune | Microsoft Docs
description: Android Kurumsal ve Android Bilgi Noktası için bir Wi-Fi cihaz yapılandırma profili oluşturun veya ekleyin. Microsoft Intune’da sertifika ekleme, EAP türü seçme ve bir kimlik doğrulama yöntemi seçme gibi farklı ayarları inceleyin. Bilgi noktası cihazlarında ağınızın Önceden paylaşılan anahtarını da girin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/08/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: maholdaa
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 04d35f49f9e07cb72a1fea92210b05e0a95ec256
ms.sourcegitcommit: 2fddb293d37453736ffa54692d03eca642f3ab58
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74390801"
---
# <a name="add-wi-fi-settings-for-android-enterprise-dedicated-and-fully-managed-devices-in-microsoft-intune"></a>Add Wi-Fi settings for Android Enterprise dedicated and fully managed devices in Microsoft Intune

You can create a profile with specific Wi-Fi settings, and then deploy this profile to your Android Enterprise fully managed and dedicated devices. Microsoft Intune; ağınızda kimlik doğrulama, bir önceden paylaşılan anahtar kullanma ve daha fazlası gibi pek çok özellik sunar.

Bu makalede bu ayarlar açıklanır. [Use Wi-Fi on your devices](wi-fi-settings-configure.md) includes more information about the Wi-Fi feature in Microsoft Intune.

## <a name="before-you-begin"></a>Başlamadan önce

[Cihaz profili oluşturma](wi-fi-settings-configure.md#create-a-device-profile).

## <a name="device-owner-only"></a>Device owner only

Select this option if you are deploying to an Android Enterprise dedicated or fully managed device.  Android Enterprise dedicated and fully managed devices currently support SCEP certificate deployment, but not PKCS.

### <a name="basic"></a>Basic

- **Wi-Fi türü**: **Temel**’i seçin.
- **Ağ adı**: Bu Wi-Fi bağlantısı için bir ad girin. End users see this name when they browse their device for available Wi-FI connections. For example, enter **Contoso WiFi**.
- **SSID**: Enter the **service set identifier**, which is the real name of the wireless network that devices connect to. Ancak bağlantıyı seçen kullanıcılar yalnızca yapılandırdığınız **ağ adını** görür.
- **Gizli ağ**: Cihazdaki kullanılabilir ağlar listesinde bu ağı gizlemek için **Etkinleştir**’i seçin. SSID yayınlanmaz. Cihazdaki kullanılabilir ağlar listesinde bu ağı göstermek için **Devre dışı bırak**’ı seçin.
- **Wi-Fi türü**: Wi-Fi ağında kimlik doğrulamak için kullanılacak güvenlik protokolünü seçin. Seçenekleriniz şunlardır:

  - **Açık (kimlik doğrulamasız)** : Bu seçeneği yalnızca ağ güvenlik altına alınmamış olduğunda kullanın.
  - **WEP-Önceden paylaşılan anahtar**: **Önceden paylaşılan anahtar** olarak parolayı girin. Kuruluşunuzun ağı ayarlandığında veya yapılandırıldığında bir parola veya ağ anahtarı da yapılandırılır. PSK değeri için bu parolayı veya ağ anahtarını girin.
  - **WPA-Önceden paylaşılan anahtar**: **Önceden paylaşılan anahtar** olarak parolayı girin. Kuruluşunuzun ağı ayarlandığında veya yapılandırıldığında bir parola veya ağ anahtarı da yapılandırılır. PSK değeri için bu parolayı veya ağ anahtarını girin.

### <a name="enterprise"></a>Enterprise

- **Wi-Fi türü**: **Kurumsal**’ı seçin.
- **SSID**: Enter the **service set identifier**, which is the real name of the wireless network that devices connect to. Ancak bağlantıyı seçen kullanıcılar yalnızca yapılandırdığınız **ağ adını** görür.
- **Gizli ağ**: Cihazdaki kullanılabilir ağlar listesinde bu ağı gizlemek için **Etkinleştir**’i seçin. SSID yayınlanmaz. Cihazdaki kullanılabilir ağlar listesinde bu ağı göstermek için **Devre dışı bırak**’ı seçin.
- **EAP türü**: Güvenli kablosuz bağlantıların kimliğini doğrulamak için kullanılan Genişletilebilir Kimlik Doğrulama Protokolü (EAP) türünü seçin. Seçenekleriniz şunlardır:

  - **EAP-TLS**: Ayrıca şunları girin:

    - **Sunucu Güveni** - **Sunucu doğrulaması için kök sertifika**: Mevcut bir güvenilen kök sertifika profilini seçin. When the client connects to the network, this certificate is presented to the server, and authenticates the connection.

    - **Client Authentication** - **Client certificate for client authentication (Identity certificate)** : Choose the SCEP client certificate profile that is also deployed to the device. Bu sertifika, bağlantının kimliğini doğrulamak için cihaz tarafından sunucuya sunulan kimliktir.

    - **Kimlik gizliliği (dış kimlik)** : EAP kimlik isteğine yanıt olarak gönderilen metni girin. Bu metin herhangi bir değer olabilir, örneğin `anonymous`. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.

  - **EAP-TTLS**: Ayrıca şunları girin:

    - **Sunucu Güveni** - **Sunucu doğrulaması için kök sertifika**: Mevcut bir güvenilen kök sertifika profilini seçin. When the client connects to the network, this certificate is presented to the server, and authenticates the connection.

    - **Client Authentication**: Choose an **Authentication method**. Seçenekleriniz şunlardır:

      - **Kullanıcı adı ve Parola**: Bağlantının kimliğini doğrulamak için kullanıcıdan bir kullanıcı adı ve parola girmesini isteyin. Şunları da girin:
        - **EAP dışı yöntem (iç kimlik)** : Bağlantının kimliğini nasıl doğrulayacağınızı seçin. Wi-Fi ağınızda yapılandırılmış olan protokolü seçtiğinizden emin olun. Seçenekleriniz şunlardır:

          - **Şifrelenmemiş parola (PAP)**
          - **Microsoft CHAP (MS-CHAP)**
          - **Microsoft CHAP Sürüm 2 (MS-CHAP v2)**

      - **Certificates**: Choose the SCEP client certificate profile that is also deployed to the device. Bu sertifika, bağlantının kimliğini doğrulamak için cihaz tarafından sunucuya sunulan kimliktir.

      - **Kimlik gizliliği (dış kimlik)** : EAP kimlik isteğine yanıt olarak gönderilen metni girin. Bu metin herhangi bir değer olabilir, örneğin `anonymous`. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.

  - **PEAP**: Ayrıca şunları girin:

    - **Sunucu Güveni** - **Sunucu doğrulaması için kök sertifika**: Mevcut bir güvenilen kök sertifika profilini seçin. When the client connects to the network, this certificate is presented to the server, and authenticates the connection.

    - **Client Authentication**: Choose an **Authentication method**. Seçenekleriniz şunlardır:

      - **Kullanıcı adı ve Parola**: Bağlantının kimliğini doğrulamak için kullanıcıdan bir kullanıcı adı ve parola girmesini isteyin. Şunları da girin:
        - **Kimlik doğrulaması için EAP dışı yöntem (iç kimlik)** : Bağlantının kimliğini nasıl doğrulayacağınızı seçin. Wi-Fi ağınızda yapılandırılmış olan protokolü seçtiğinizden emin olun. Seçenekleriniz şunlardır:

          - **Yok.**
          - **Microsoft CHAP Sürüm 2 (MS-CHAP v2)**

      - **Certificates**: Choose the SCEP client certificate profile that is also deployed to the device. Bu sertifika, bağlantının kimliğini doğrulamak için cihaz tarafından sunucuya sunulan kimliktir.

      - **Kimlik gizliliği (dış kimlik)** : EAP kimlik isteğine yanıt olarak gönderilen metni girin. Bu metin herhangi bir değer olabilir, örneğin `anonymous`. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.

## <a name="work-profile-only"></a>Yalnızca iş profili

### <a name="basic"></a>Basic

- **Wi-Fi türü**: **Temel**’i seçin.
- **SSID**: Enter the **service set identifier**, which is the real name of the wireless network that devices connect to. Ancak bağlantıyı seçen kullanıcılar yalnızca yapılandırdığınız **ağ adını** görür.
- **Gizli ağ**: Cihazdaki kullanılabilir ağlar listesinde bu ağı gizlemek için **Etkinleştir**’i seçin. SSID yayınlanmaz. Cihazdaki kullanılabilir ağlar listesinde bu ağı göstermek için **Devre dışı bırak**’ı seçin.

### <a name="enterprise"></a>Enterprise

- **Wi-Fi türü**: **Kurumsal**’ı seçin.
- **SSID**: Enter the **service set identifier**, which is the real name of the wireless network that devices connect to. Ancak bağlantıyı seçen kullanıcılar yalnızca yapılandırdığınız **ağ adını** görür.
- **Gizli ağ**: Cihazdaki kullanılabilir ağlar listesinde bu ağı gizlemek için **Etkinleştir**’i seçin. SSID yayınlanmaz. Cihazdaki kullanılabilir ağlar listesinde bu ağı göstermek için **Devre dışı bırak**’ı seçin.
- **EAP türü**: Güvenli kablosuz bağlantıların kimliğini doğrulamak için kullanılan Genişletilebilir Kimlik Doğrulama Protokolü (EAP) türünü seçin. Seçenekleriniz şunlardır:

  - **EAP-TLS**: Ayrıca şunları girin:

    - **Sunucu Güveni** - **Sunucu doğrulaması için kök sertifika**: Mevcut bir güvenilen kök sertifika profilini seçin. When the client connects to the network, this certificate is presented to the server, and authenticates the connection.

    - **İstemci Kimlik Doğrulaması** - **İstemci kimlik doğrulaması için istemci sertifikası (Kimlik sertifikası)** : Cihaza da dağıtılmış olan SCEP veya PKCS istemci sertifikası profilini seçin. Bu sertifika, bağlantının kimliğini doğrulamak için cihaz tarafından sunucuya sunulan kimliktir.

    - **Kimlik gizliliği (dış kimlik)** : EAP kimlik isteğine yanıt olarak gönderilen metni girin. Bu metin herhangi bir değer olabilir, örneğin `anonymous`. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.

  - **EAP-TTLS**: Ayrıca şunları girin:

    - **Sunucu Güveni** - **Sunucu doğrulaması için kök sertifika**: Mevcut bir güvenilen kök sertifika profilini seçin. When the client connects to the network, this certificate is presented to the server, and authenticates the connection.

    - **Client Authentication**: Choose an **Authentication method**. Seçenekleriniz şunlardır:

      - **Kullanıcı adı ve Parola**: Bağlantının kimliğini doğrulamak için kullanıcıdan bir kullanıcı adı ve parola girmesini isteyin. Şunları da girin:
        - **EAP dışı yöntem (iç kimlik)** : Bağlantının kimliğini nasıl doğrulayacağınızı seçin. Wi-Fi ağınızda yapılandırılmış olan protokolü seçtiğinizden emin olun. Seçenekleriniz şunlardır:

          - **Şifrelenmemiş parola (PAP)**
          - **Microsoft CHAP (MS-CHAP)**
          - **Microsoft CHAP Sürüm 2 (MS-CHAP v2)**

      - **Sertifikalar**: Cihaza da dağıtılmış olan SCEP veya PKCS istemci sertifikası profilini seçin. Bu sertifika, bağlantının kimliğini doğrulamak için cihaz tarafından sunucuya sunulan kimliktir.

      - **Kimlik gizliliği (dış kimlik)** : EAP kimlik isteğine yanıt olarak gönderilen metni girin. Bu metin herhangi bir değer olabilir, örneğin `anonymous`. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.

  - **PEAP**: Ayrıca şunları girin:

    - **Sunucu Güveni** - **Sunucu doğrulaması için kök sertifika**: Mevcut bir güvenilen kök sertifika profilini seçin. When the client connects to the network, this certificate is presented to the server, and authenticates the connection.

    - **Client Authentication**: Choose an **Authentication method**. Seçenekleriniz şunlardır:

      - **Kullanıcı adı ve Parola**: Bağlantının kimliğini doğrulamak için kullanıcıdan bir kullanıcı adı ve parola girmesini isteyin. Şunları da girin:
        - **Kimlik doğrulaması için EAP dışı yöntem (iç kimlik)** : Bağlantının kimliğini nasıl doğrulayacağınızı seçin. Wi-Fi ağınızda yapılandırılmış olan protokolü seçtiğinizden emin olun. Seçenekleriniz şunlardır:

          - **Yok.**
          - **Microsoft CHAP Sürüm 2 (MS-CHAP v2)**

      - **Sertifikalar**: Cihaza da dağıtılmış olan SCEP veya PKCS istemci sertifikası profilini seçin. Bu sertifika, bağlantının kimliğini doğrulamak için cihaz tarafından sunucuya sunulan kimliktir.

      - **Kimlik gizliliği (dış kimlik)** : EAP kimlik isteğine yanıt olarak gönderilen metni girin. Bu metin herhangi bir değer olabilir, örneğin `anonymous`. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturuldu ancak hiçbir şey yapmıyor. Next, [assign this profile](device-profile-assign.md) and [monitor its status.](device-profile-monitor.md).

You can also create Wi-Fi profiles for [Android](wi-fi-settings-android.md), [iOS](wi-fi-settings-ios.md), [macOS](wi-fi-settings-macos.md), [Windows 10](wi-fi-settings-windows.md), and [Windows 8.1](wi-fi-settings-import-windows-8-1.md) devices.
