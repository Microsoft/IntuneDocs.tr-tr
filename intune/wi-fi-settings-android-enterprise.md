---
title: Android Enterprise ve bilgi noktası cihazları için Wi-Fi ayarları-Microsoft Intune | Microsoft Docs
description: Android Kurumsal ve Android Bilgi Noktası için bir Wi-Fi cihaz yapılandırma profili oluşturun veya ekleyin. Microsoft Intune’da sertifika ekleme, EAP türü seçme ve bir kimlik doğrulama yöntemi seçme gibi farklı ayarları inceleyin. Bilgi noktası cihazlarında ağınızın Önceden paylaşılan anahtarını da girin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/06/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 51096b4ff42902b5feb8cecdebf9d839821e1bb2
ms.sourcegitcommit: b78793ccbef2a644a759ca3110ea73e7ed6ceb8f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69545943"
---
# <a name="add-wi-fi-settings-for-devices-running-android-enterprise-and-android-kiosk-in-microsoft-intune"></a>Microsoft Intune’da Android Kurumsal ve Android Bilgi Noktası çalıştıran cihazlar için Wi-Fi ayarları ekleme

Belirli bir WiFi ayarlarına sahip bir profil oluşturabilir ve ardından bu profili Android Enterprise ve Android adanmış cihazlarınıza dağıtabilirsiniz. Microsoft Intune; ağınızda kimlik doğrulama, bir önceden paylaşılan anahtar kullanma ve daha fazlası gibi pek çok özellik sunar.

Bu makalede bu ayarlar açıklanır. [Cihazlarınızda Wi-Fi kullanın](wi-fi-settings-configure.md) , Microsoft Intune Wi-Fi özelliği hakkında daha fazla bilgi içerir.

## <a name="before-you-begin"></a>Başlamadan önce

[Cihaz profili oluşturma](wi-fi-settings-configure.md#create-a-device-profile).

## <a name="device-owner-only"></a>Yalnızca cihaz sahibi

Bir Android kurumsal adanmış cihazı bilgi noktası olarak kullanıyorsanız bu seçeneği belirleyin.

### <a name="basic"></a>Temel

- **Wi-Fi türü**: **Temel**’i seçin.
- **Ağ adı**: Bu Wi-Fi bağlantısı için bir ad girin. Son kullanıcılar, kullanılabilir Wi-FI bağlantıları için cihazına gözatarken bu adı görür. Örneğin, **contoso WiFi**girin.
- **SSID**: Cihazların bağlandığı kablosuz ağın gerçek adı olan **hizmet kümesi tanımlayıcısını**girin. Ancak bağlantıyı seçen kullanıcılar yalnızca yapılandırdığınız **ağ adını** görür.
- **Otomatik olarak bağlan**: Cihaz Aralık içinde olduğunda bu ağa otomatik olarak bağlanmak için **Etkinleştir** ' i seçin. Cihazların otomatik olarak bağlanmasını önlemek için **Devre dışı bırak**’ı seçin.
- **Gizli ağ**: Bu ağı cihazdaki kullanılabilir ağlar listesinden gizlemek için **Etkinleştir** ' i seçin. SSID yayınlanmaz. Cihazdaki kullanılabilir ağlar listesinde bu ağı göstermek için **Devre dışı bırak**’ı seçin.
- **Wi-Fi türü**: Wi-Fi ağına kimlik doğrulaması yapmak için güvenlik protokolünü seçin. Seçenekleriniz şunlardır:

  - **Açık (kimlik doğrulaması yok)** : Yalnızca ağ güvenli değilse bu seçeneği kullanın.
  - **WEP-önceden paylaşılan anahtar**: Parolayı **önceden paylaşılan anahtarda**girin. Kuruluşunuzun ağı ayarlandığında veya yapılandırıldığında bir parola veya ağ anahtarı da yapılandırılır. PSK değeri için bu parolayı veya ağ anahtarını girin.
  - **WPA-önceden paylaşılan anahtar**: Parolayı **önceden paylaşılan anahtarda**girin. Kuruluşunuzun ağı ayarlandığında veya yapılandırıldığında bir parola veya ağ anahtarı da yapılandırılır. PSK değeri için bu parolayı veya ağ anahtarını girin.

### <a name="enterprise"></a>Enterprise

- **Wi-Fi türü**: **Kuruluş**' ı seçin.
- **SSID**: Cihazların bağlandığı kablosuz ağın gerçek adı olan **hizmet kümesi tanımlayıcısını**girin. Ancak bağlantıyı seçen kullanıcılar yalnızca yapılandırdığınız **ağ adını** görür.
- **Otomatik olarak bağlan**: Cihaz Aralık içinde olduğunda bu ağa otomatik olarak bağlanmak için **Etkinleştir** ' i seçin. Cihazların otomatik olarak bağlanmasını önlemek için **Devre dışı bırak**’ı seçin.
- **Gizli ağ**: Bu ağı cihazdaki kullanılabilir ağlar listesinden gizlemek için **Etkinleştir** ' i seçin. SSID yayınlanmaz. Cihazdaki kullanılabilir ağlar listesinde bu ağı göstermek için **Devre dışı bırak**’ı seçin.
- **EAP türü**: Güvenli kablosuz bağlantıların kimliğini doğrulamak için kullanılan Genişletilebilir Kimlik Doğrulama Protokolü (EAP) türünü seçin. Seçenekleriniz şunlardır:

  - **EAP-TLS**: Şunları da girin:

    -  - Sunucu**doğrulaması için sunucu güveni kök sertifikası**: Var olan bir güvenilen kök sertifika profili seçin. İstemci ağa bağlandığı zaman, bu sertifika sunucuya sunulur ve bağlantının kimliğini doğrular.

    -  - İstemci**kimlik doğrulaması (kimlik sertifikası) için**istemci kimlik doğrulama istemci sertifikası: Cihaza de dağıtılan SCEP veya PKCS istemci sertifikası profilini seçin. Bu sertifika, bağlantının kimliğini doğrulamak için cihaz tarafından sunucuya sunulan kimliktir.

    - **Kimlik gizliliği (dış kimlik)** : Bir EAP kimlik isteğine yanıt olarak gönderilen metni girin. Bu metin herhangi bir değer olabilir, örneğin `anonymous`. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.

  - **EAP-TTLS**: Şunları da girin:

    -  - Sunucu**doğrulaması için sunucu güveni kök sertifikası**: Var olan bir güvenilen kök sertifika profili seçin. İstemci ağa bağlandığı zaman, bu sertifika sunucuya sunulur ve bağlantının kimliğini doğrular.

    - **Istemci kimlik doğrulaması**: Bir **kimlik doğrulama yöntemi**seçin. Seçenekleriniz şunlardır:

      - **Kullanıcı adı ve parola**: Bağlantının kimliğini doğrulamak için kullanıcıdan bir Kullanıcı adı ve parola iste. Şunları da girin:
        - **EAP olmayan Yöntem (iç kimlik)** : Bağlantının kimliğini nasıl doğrulayacağınızı seçin. Wi-Fi ağınızda yapılandırılmış olan protokolü seçtiğinizden emin olun. Seçenekleriniz şunlardır:

          - **Şifrelenmemiş parola (PAP)**
          - **Microsoft CHAP (MS-CHAP)**
          - **Microsoft CHAP Sürüm 2 (MS-CHAP v2)**

      - **Sertifikalar**: Cihaza de dağıtılan SCEP veya PKCS istemci sertifikası profilini seçin. Bu sertifika, bağlantının kimliğini doğrulamak için cihaz tarafından sunucuya sunulan kimliktir.

      - **Kimlik gizliliği (dış kimlik)** : Bir EAP kimlik isteğine yanıt olarak gönderilen metni girin. Bu metin herhangi bir değer olabilir, örneğin `anonymous`. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.

  - **PEAP**: Şunları da girin:

    -  - Sunucu**doğrulaması için sunucu güveni kök sertifikası**: Var olan bir güvenilen kök sertifika profili seçin. İstemci ağa bağlandığı zaman, bu sertifika sunucuya sunulur ve bağlantının kimliğini doğrular.

    - **Istemci kimlik doğrulaması**: Bir **kimlik doğrulama yöntemi**seçin. Seçenekleriniz şunlardır:

      - **Kullanıcı adı ve parola**: Bağlantının kimliğini doğrulamak için kullanıcıdan bir Kullanıcı adı ve parola iste. Şunları da girin:
        - **Kimlik doğrulaması IÇIN EAP olmayan Yöntem (iç kimlik)** : Bağlantının kimliğini nasıl doğrulayacağınızı seçin. Wi-Fi ağınızda yapılandırılmış olan protokolü seçtiğinizden emin olun. Seçenekleriniz şunlardır:

          - **Yok.**
          - **Microsoft CHAP Sürüm 2 (MS-CHAP v2)**

      - **Sertifikalar**: Cihaza de dağıtılan SCEP veya PKCS istemci sertifikası profilini seçin. Bu sertifika, bağlantının kimliğini doğrulamak için cihaz tarafından sunucuya sunulan kimliktir.

      - **Kimlik gizliliği (dış kimlik)** : Bir EAP kimlik isteğine yanıt olarak gönderilen metni girin. Bu metin herhangi bir değer olabilir, örneğin `anonymous`. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.

## <a name="work-profile-only"></a>Yalnızca iş profili

### <a name="basic"></a>Temel

- **Wi-Fi türü**: **Temel**’i seçin.
- **SSID**: Cihazların bağlandığı kablosuz ağın gerçek adı olan **hizmet kümesi tanımlayıcısını**girin. Ancak bağlantıyı seçen kullanıcılar yalnızca yapılandırdığınız **ağ adını** görür.
- **Otomatik olarak bağlan**: Cihaz Aralık içinde olduğunda bu ağa otomatik olarak bağlanmak için **Etkinleştir** ' i seçin. Cihazların otomatik olarak bağlanmasını önlemek için **Devre dışı bırak**’ı seçin.
- **Gizli ağ**: Bu ağı cihazdaki kullanılabilir ağlar listesinden gizlemek için **Etkinleştir** ' i seçin. SSID yayınlanmaz. Cihazdaki kullanılabilir ağlar listesinde bu ağı göstermek için **Devre dışı bırak**’ı seçin.

### <a name="enterprise"></a>Enterprise

- **Wi-Fi türü**: **Kuruluş**' ı seçin.
- **SSID**: Cihazların bağlandığı kablosuz ağın gerçek adı olan **hizmet kümesi tanımlayıcısını**girin. Ancak bağlantıyı seçen kullanıcılar yalnızca yapılandırdığınız **ağ adını** görür.
- **Otomatik olarak bağlan**: Cihaz Aralık içinde olduğunda bu ağa otomatik olarak bağlanmak için **Etkinleştir** ' i seçin. Cihazların otomatik olarak bağlanmasını önlemek için **Devre dışı bırak**’ı seçin.
- **Gizli ağ**: Bu ağı cihazdaki kullanılabilir ağlar listesinden gizlemek için **Etkinleştir** ' i seçin. SSID yayınlanmaz. Cihazdaki kullanılabilir ağlar listesinde bu ağı göstermek için **Devre dışı bırak**’ı seçin.
- **EAP türü**: Güvenli kablosuz bağlantıların kimliğini doğrulamak için kullanılan Genişletilebilir Kimlik Doğrulama Protokolü (EAP) türünü seçin. Seçenekleriniz şunlardır:

  - **EAP-TLS**: Şunları da girin:

    -  - Sunucu**doğrulaması için sunucu güveni kök sertifikası**: Var olan bir güvenilen kök sertifika profili seçin. İstemci ağa bağlandığı zaman, bu sertifika sunucuya sunulur ve bağlantının kimliğini doğrular.

    -  - İstemci**kimlik doğrulaması (kimlik sertifikası) için**istemci kimlik doğrulama istemci sertifikası: Cihaza de dağıtılan SCEP veya PKCS istemci sertifikası profilini seçin. Bu sertifika, bağlantının kimliğini doğrulamak için cihaz tarafından sunucuya sunulan kimliktir.

    - **Kimlik gizliliği (dış kimlik)** : Bir EAP kimlik isteğine yanıt olarak gönderilen metni girin. Bu metin herhangi bir değer olabilir, örneğin `anonymous`. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.

  - **EAP-TTLS**: Şunları da girin:

    -  - Sunucu**doğrulaması için sunucu güveni kök sertifikası**: Var olan bir güvenilen kök sertifika profili seçin. İstemci ağa bağlandığı zaman, bu sertifika sunucuya sunulur ve bağlantının kimliğini doğrular.

    - **Istemci kimlik doğrulaması**: Bir **kimlik doğrulama yöntemi**seçin. Seçenekleriniz şunlardır:

      - **Kullanıcı adı ve parola**: Bağlantının kimliğini doğrulamak için kullanıcıdan bir Kullanıcı adı ve parola iste. Şunları da girin:
        - **EAP olmayan Yöntem (iç kimlik)** : Bağlantının kimliğini nasıl doğrulayacağınızı seçin. Wi-Fi ağınızda yapılandırılmış olan protokolü seçtiğinizden emin olun. Seçenekleriniz şunlardır:

          - **Şifrelenmemiş parola (PAP)**
          - **Microsoft CHAP (MS-CHAP)**
          - **Microsoft CHAP Sürüm 2 (MS-CHAP v2)**

      - **Sertifikalar**: Cihaza de dağıtılan SCEP veya PKCS istemci sertifikası profilini seçin. Bu sertifika, bağlantının kimliğini doğrulamak için cihaz tarafından sunucuya sunulan kimliktir.

      - **Kimlik gizliliği (dış kimlik)** : Bir EAP kimlik isteğine yanıt olarak gönderilen metni girin. Bu metin herhangi bir değer olabilir, örneğin `anonymous`. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.

  - **PEAP**: Şunları da girin:

    -  - Sunucu**doğrulaması için sunucu güveni kök sertifikası**: Var olan bir güvenilen kök sertifika profili seçin. İstemci ağa bağlandığı zaman, bu sertifika sunucuya sunulur ve bağlantının kimliğini doğrular.

    - **Istemci kimlik doğrulaması**: Bir **kimlik doğrulama yöntemi**seçin. Seçenekleriniz şunlardır:

      - **Kullanıcı adı ve parola**: Bağlantının kimliğini doğrulamak için kullanıcıdan bir Kullanıcı adı ve parola iste. Şunları da girin:
        - **Kimlik doğrulaması IÇIN EAP olmayan Yöntem (iç kimlik)** : Bağlantının kimliğini nasıl doğrulayacağınızı seçin. Wi-Fi ağınızda yapılandırılmış olan protokolü seçtiğinizden emin olun. Seçenekleriniz şunlardır:

          - **Yok.**
          - **Microsoft CHAP Sürüm 2 (MS-CHAP v2)**

      - **Sertifikalar**: Cihaza de dağıtılan SCEP veya PKCS istemci sertifikası profilini seçin. Bu sertifika, bağlantının kimliğini doğrulamak için cihaz tarafından sunucuya sunulan kimliktir.

      - **Kimlik gizliliği (dış kimlik)** : Bir EAP kimlik isteğine yanıt olarak gönderilen metni girin. Bu metin herhangi bir değer olabilir, örneğin `anonymous`. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturuldu ancak hiçbir şey yapmıyor. Sonra, [Bu profili atayın](device-profile-assign.md) ve [durumunu izleyin.](device-profile-monitor.md)

[Android](wi-fi-settings-android.md), [iOS](wi-fi-settings-ios.md), [macos](wi-fi-settings-macos.md), [Windows 10](wi-fi-settings-windows.md)ve [Windows 8.1](wi-fi-settings-import-windows-8-1.md) cihazları için Wi-Fi profilleri de oluşturabilirsiniz.
