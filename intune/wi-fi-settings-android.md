---
title: Microsoft Intune’da Android cihazları için Wi-Fi ayarlarını yapılandırma - Azure | Microsoft Docs
titleSuffix: ''
description: Android için bir Wi-Fi cihaz yapılandırma profili oluşturun veya ekleyin. Microsoft Intune’da sertifika ekleme, EAP türü seçme ve bir kimlik doğrulama yöntemi seçme gibi farklı ayarları görün.
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
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1d341aeace950f62ae699aa7760a65c0fd2f74fa
ms.sourcegitcommit: b78793ccbef2a644a759ca3110ea73e7ed6ceb8f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69550051"
---
# <a name="add-wi-fi-settings-for-devices-running-android-in-microsoft-intune"></a>Microsoft Intune’da Android çalıştıran cihazlar için Wi-Fi ayarları ekleme

Belirli Wi-Fi ayarları ile bir profil oluşturabilir ve ardından bu profili Android cihazlarınıza dağıtabilirsiniz. Microsoft Intune; ağınızda kimlik doğrulama, bir PKS veya SCEP sertifikası ekleme ve daha fazlası gibi pek çok özellik sunar.

Bu Wi-Fi ayarları iki kategoride ayrılır: Temel ayarlar ve kurumsal düzeyde ayarlar.

Bu makalede bu ayarlar açıklanır.

## <a name="before-you-begin"></a>Başlamadan önce

[Cihaz profili oluşturma](device-profile-create.md).

## <a name="basic"></a>Temel

- **Wi-Fi türü**: **Temel**’i seçin.
- **SSID**: Cihazların bağlandığı kablosuz ağın gerçek adı olan **hizmet kümesi tanımlayıcısını**girin. Ancak bağlantıyı seçen kullanıcılar yalnızca yapılandırdığınız **ağ adını** görür.
- **Otomatik olarak bağlan**: Cihaz Aralık içinde olduğunda bu ağa otomatik olarak bağlanmak için **Etkinleştir** ' i seçin. Cihazların otomatik olarak bağlanmasını önlemek için **Devre dışı bırak**’ı seçin.
- **Gizli ağ**: Bu ağı cihazdaki kullanılabilir ağlar listesinden gizlemek için **Etkinleştir** ' i seçin. SSID yayınlanmaz. Cihazdaki kullanılabilir ağlar listesinde bu ağı göstermek için **Devre dışı bırak**’ı seçin.

## <a name="enterprise"></a>Enterprise

- **Wi-Fi türü**: **Kuruluş**' ı seçin.
- **SSID**: Cihazların bağlandığı kablosuz ağın gerçek adı olan **hizmet kümesi tanımlayıcısını**girin. Ancak bağlantıyı seçen kullanıcılar yalnızca yapılandırdığınız **ağ adını** görür.
- **Otomatik olarak bağlan**: Cihaz Aralık içinde olduğunda bu ağa otomatik olarak bağlanmak için **Etkinleştir** ' i seçin. Cihazların otomatik olarak bağlanmasını önlemek için **Devre dışı bırak**’ı seçin.
- **Gizli ağ**: Bu ağı cihazdaki kullanılabilir ağlar listesinden gizlemek için **Etkinleştir** ' i seçin. SSID yayınlanmaz. Cihazdaki kullanılabilir ağlar listesinde bu ağı göstermek için **Devre dışı bırak**’ı seçin.
- **EAP türü**: Güvenli kablosuz bağlantıların kimliğini doğrulamak için kullanılan Genişletilebilir Kimlik Doğrulama Protokolü (EAP) türünü seçin. Seçenekleriniz şunlardır: 

  - **EAP-TLS**: Şunları da girin:

    -  - Sunucu**doğrulaması için sunucu güveni kök sertifikası**: Var olan bir güvenilen kök sertifika profili seçin. İstemci ağa bağlanırken bu sertifika sunucuya sunulur. Bağlantının kimliğini doğrular.

    -  - İstemci**kimlik doğrulaması (kimlik sertifikası) için**istemci kimlik doğrulama istemci sertifikası: Cihaza de dağıtılan SCEP veya PKCS istemci sertifikası profilini seçin. Bu sertifika, bağlantının kimliğini doğrulamak için cihaz tarafından sunucuya sunulan kimliktir.

    - **Kimlik gizliliği (dış kimlik)** : Bir EAP kimlik isteğine yanıt olarak gönderilen metni girin. Bu metin herhangi bir değer olabilir, örneğin `anonymous`. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.

  - **EAP-TTLS**: Şunları da girin:

    -  - Sunucu**doğrulaması için sunucu güveni kök sertifikası**: Var olan bir güvenilen kök sertifika profili seçin. İstemci ağa bağlanırken bu sertifika sunucuya sunulur. Bağlantının kimliğini doğrular.

    - **Istemci kimlik doğrulaması**: Bir **kimlik doğrulama yöntemi**seçin. Seçenekleriniz şunlardır:

      - **Kullanıcı adı ve parola**: Bağlantının kimliğini doğrulamak için kullanıcıdan bir Kullanıcı adı ve parola iste. Şunları da girin:
        - **EAP olmayan Yöntem (iç kimlik)** : Bağlantının kimliğini nasıl doğrulayacağınızı seçin. Wi-Fi ağınızda yapılandırılmış olan protokolü seçtiğinizden emin olun. Seçenekleriniz şunlardır:

          - **Şifrelenmemiş parola (PAP)**
          - **Karşılıklı Kimlik Doğrulama Protokolü (CHAP)**
          - **Microsoft CHAP (MS-CHAP)**
          - **Microsoft CHAP Sürüm 2 (MS-CHAP v2)**

      - **Sertifikalar**: Cihaza de dağıtılan SCEP veya PKCS istemci sertifikası profilini seçin. Bu sertifika, bağlantının kimliğini doğrulamak için cihaz tarafından sunucuya sunulan kimliktir.

      - **Kimlik gizliliği (dış kimlik)** : Bir EAP kimlik isteğine yanıt olarak gönderilen metni girin. Bu metin herhangi bir değer olabilir, örneğin `anonymous`. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.

  - **PEAP**: Şunları da girin:

    -  - Sunucu**doğrulaması için sunucu güveni kök sertifikası**: Var olan bir güvenilen kök sertifika profili seçin. İstemci ağa bağlanırken bu sertifika sunucuya sunulur. Bağlantının kimliğini doğrular.

    - **Istemci kimlik doğrulaması**: Bir **kimlik doğrulama yöntemi**seçin. Seçenekleriniz şunlardır:

      - **Kullanıcı adı ve parola**: Bağlantının kimliğini doğrulamak için kullanıcıdan bir Kullanıcı adı ve parola iste. Şunları da girin:
        - **Kimlik doğrulaması IÇIN EAP olmayan Yöntem (iç kimlik)** : Bağlantının kimliğini nasıl doğrulayacağınızı seçin. Wi-Fi ağınızda yapılandırılmış olan protokolü seçtiğinizden emin olun. Seçenekleriniz şunlardır:

          - **Yok.**
          - **Microsoft CHAP Sürüm 2 (MS-CHAP v2)**

      - **Sertifikalar**: Cihaza de dağıtılan SCEP veya PKCS istemci sertifikası profilini seçin. Bu sertifika, bağlantının kimliğini doğrulamak için cihaz tarafından sunucuya sunulan kimliktir.

      - **Kimlik gizliliği (dış kimlik)** : Bir EAP kimlik isteğine yanıt olarak gönderilen metni girin. Bu metin herhangi bir değer olabilir, örneğin `anonymous`. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturuldu ancak hiçbir şey yapmıyor. Daha sonra [bu profili atayın](device-profile-assign.md).

## <a name="more-resources"></a>Daha fazla kaynak

- Diğer platformlar dahil olmak üzere [Wi-Fi ayarlarına genel bakış](wi-fi-settings-configure.md).

- Android Kurumsal veya Android bilgi noktası cihazları mı kullanıyorsunuz? Yanıt Evet ise, [Android Enterprise ve adanmış cihazlar çalıştıran cihazlar Için Wi-Fi ayarlarına](wi-fi-settings-android-enterprise.md)bakın.
