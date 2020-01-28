---
title: Microsoft Intune’da Android cihazları için Wi-Fi ayarlarını yapılandırma - Azure | Microsoft Docs
titleSuffix: ''
description: Android için bir Wi-Fi cihaz yapılandırma profili oluşturun veya ekleyin. Microsoft Intune’da sertifika ekleme, EAP türü seçme ve bir kimlik doğrulama yöntemi seçme gibi farklı ayarları görün.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/24/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: maholdaa
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2ea0a60537bb488d3280990747d3e337e73fddc0
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2020
ms.locfileid: "76754567"
---
# <a name="add-wi-fi-settings-for-devices-running-android-in-microsoft-intune"></a>Microsoft Intune’da Android çalıştıran cihazlar için Wi-Fi ayarları ekleme

Belirli Wi-Fi ayarları ile bir profil oluşturabilir ve ardından bu profili Android cihazlarınıza dağıtabilirsiniz. Microsoft Intune; ağınızda kimlik doğrulama, bir PKS veya SCEP sertifikası ekleme ve daha fazlası gibi pek çok özellik sunar.

Bu Wi-Fi ayarları iki kategoriye ayrılır: Temel ayarlar ve Kurumsal düzeydeki ayarlar.

Bu makalede bu ayarlar açıklanır.

## <a name="before-you-begin"></a>Başlamadan önce

[Cihaz profili oluşturma](device-profile-create.md).

## <a name="basic"></a>Temel

- **Wi-Fi türü**: **Temel**’i seçin.
- **SSID**: cihazların bağlandığı kablosuz ağın gerçek adı olan **hizmet kümesi tanımlayıcısını**girin. Ancak bağlantıyı seçen kullanıcılar yalnızca yapılandırdığınız **ağ adını** görür.
- **Gizli ağ**: Cihazdaki kullanılabilir ağlar listesinde bu ağı gizlemek için **Etkinleştir**’i seçin. SSID yayınlanmaz. Cihazdaki kullanılabilir ağlar listesinde bu ağı göstermek için **Devre dışı bırak**’ı seçin.

## <a name="enterprise"></a>Enterprise

- **Wi-Fi türü**: **Kurumsal**’ı seçin.
- **SSID**: cihazların bağlandığı kablosuz ağın gerçek adı olan **hizmet kümesi tanımlayıcısını**girin. Ancak bağlantıyı seçen kullanıcılar yalnızca yapılandırdığınız **ağ adını** görür.
- **Gizli ağ**: Cihazdaki kullanılabilir ağlar listesinde bu ağı gizlemek için **Etkinleştir**’i seçin. SSID yayınlanmaz. Cihazdaki kullanılabilir ağlar listesinde bu ağı göstermek için **Devre dışı bırak**’ı seçin.
- **EAP türü**: Güvenli kablosuz bağlantıların kimliğini doğrulamak için kullanılan Genişletilebilir Kimlik Doğrulama Protokolü (EAP) türünü seçin. Seçenekleriniz şunlardır:

  - **EAP-TLS**: Ayrıca şunları girin:

    - **Sunucu Güveni** - **Sunucu doğrulaması için kök sertifika**: Mevcut bir güvenilen kök sertifika profilini seçin. İstemci ağa bağlanırken bu sertifika sunucuya sunulur. Bağlantının kimliğini doğrular.

    - **İstemci Kimlik Doğrulaması** - **İstemci kimlik doğrulaması için istemci sertifikası (Kimlik sertifikası)** : Cihaza da dağıtılmış olan SCEP veya PKCS istemci sertifikası profilini seçin. Bu sertifika, bağlantının kimliğini doğrulamak için cihaz tarafından sunucuya sunulan kimliktir.

    - **Kimlik gizliliği (dış kimlik)** : EAP kimlik isteğine yanıt olarak gönderilen metni girin. Bu metin herhangi bir değer olabilir, örneğin `anonymous`. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.

    - **Proxy ayarları**: kuruluşunuz tarafından kullanılan ara sunucu yapılandırmasını belirtin. Seçenekleriniz şunlardır:

      - **Hiçbiri** -proxy sunucusu kullanmazsınız.
      - **Otomatik** – ara *sunucu URL 'si* ayarını kullanılabilir hale getirmek için bu seçeneği belirleyin. proxy sunucusu veya proxy sunucularınızın bir listesini Içeren bir proxy otomatik yapılandırma (PAC) dosyası belirtin.

    - **Proxy sunucusu URL 'si**: Bu ayar, *Ara sunucu ayarlarını* *Otomatik*olarak belirlediğinizde kullanılabilir. Cihazları proxy sunucunuza yönlendirmek için aşağıdaki seçeneklerden birini belirtin:

      - IP adresi. Örneğin, `10.0.0.11`
      - BIR URL. Örneğin, `http://proxyserver.contoso.com`.
      - Bir proxy otomatik yapılandırma (PAC) dosyasının URL 'SI. Örneğin: `http://proxy.contoso.com/proxy.pac`.

      PAC dosyaları hakkında daha fazla bilgi için bkz. [proxy otomatik yapılandırma (PAC) dosyası](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (Microsoft dışı bir site açar).

  - **EAP-TTLS**: Ayrıca şunları girin:

    - **Sunucu Güveni** - **Sunucu doğrulaması için kök sertifika**: Mevcut bir güvenilen kök sertifika profilini seçin. İstemci ağa bağlanırken bu sertifika sunucuya sunulur. Bağlantının kimliğini doğrular.

    - **Istemci kimlik doğrulaması**: bir **kimlik doğrulama yöntemi**seçin. Seçenekleriniz şunlardır:

      - **Kullanıcı adı ve Parola**: Bağlantının kimliğini doğrulamak için kullanıcıdan bir kullanıcı adı ve parola girmesini isteyin. Şunları da girin:
        - **EAP dışı yöntem (iç kimlik)** : Bağlantının kimliğini nasıl doğrulayacağınızı seçin. Wi-Fi ağınızda yapılandırılmış olan protokolü seçtiğinizden emin olun. Seçenekleriniz şunlardır:

          - **Şifrelenmemiş parola (PAP)**
          - **Karşılıklı Kimlik Doğrulama Protokolü (CHAP)**
          - **Microsoft CHAP (MS-CHAP)**
          - **Microsoft CHAP Sürüm 2 (MS-CHAP v2)**

      - **Sertifikalar**: Cihaza da dağıtılmış olan SCEP veya PKCS istemci sertifikası profilini seçin. Bu sertifika, bağlantının kimliğini doğrulamak için cihaz tarafından sunucuya sunulan kimliktir.

      - **Kimlik gizliliği (dış kimlik)** : EAP kimlik isteğine yanıt olarak gönderilen metni girin. Bu metin herhangi bir değer olabilir, örneğin `anonymous`. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.

    - **Proxy ayarları**: kuruluşunuz tarafından kullanılan ara sunucu yapılandırmasını belirtin. Seçenekleriniz şunlardır:

      - **Hiçbiri** -proxy sunucusu kullanmazsınız.
      - **Otomatik** – ara *sunucu URL 'si* ayarını kullanılabilir hale getirmek için bu seçeneği belirleyin. proxy sunucusu veya proxy sunucularınızın bir listesini Içeren bir proxy otomatik yapılandırma (PAC) dosyası belirtin.

    - **Proxy sunucusu URL 'si**: Bu ayar, *Ara sunucu ayarlarını* *Otomatik*olarak belirlediğinizde kullanılabilir. Cihazları proxy sunucunuza yönlendirmek için aşağıdaki seçeneklerden birini belirtin:

      - IP adresi. Örneğin, `10.0.0.11`
      - BIR URL. Örneğin, `http://proxyserver.contoso.com`.
      - Bir proxy otomatik yapılandırma (PAC) dosyasının URL 'SI. Örneğin: `http://proxy.contoso.com/proxy.pac`.

      PAC dosyaları hakkında daha fazla bilgi için bkz. [proxy otomatik yapılandırma (PAC) dosyası](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (Microsoft dışı bir site açar).

  - **PEAP**: Ayrıca şunları girin:

    - **Sunucu Güveni** - **Sunucu doğrulaması için kök sertifika**: Mevcut bir güvenilen kök sertifika profilini seçin. İstemci ağa bağlanırken bu sertifika sunucuya sunulur. Bağlantının kimliğini doğrular.

    - **Istemci kimlik doğrulaması**: bir **kimlik doğrulama yöntemi**seçin. Seçenekleriniz şunlardır:

      - **Kullanıcı adı ve Parola**: Bağlantının kimliğini doğrulamak için kullanıcıdan bir kullanıcı adı ve parola girmesini isteyin. Şunları da girin:
        - **Kimlik doğrulaması için EAP dışı yöntem (iç kimlik)** : Bağlantının kimliğini nasıl doğrulayacağınızı seçin. Wi-Fi ağınızda yapılandırılmış olan protokolü seçtiğinizden emin olun. Seçenekleriniz şunlardır:

          - **Yok.**
          - **Microsoft CHAP Sürüm 2 (MS-CHAP v2)**

      - **Sertifikalar**: Cihaza da dağıtılmış olan SCEP veya PKCS istemci sertifikası profilini seçin. Bu sertifika, bağlantının kimliğini doğrulamak için cihaz tarafından sunucuya sunulan kimliktir.

      - **Kimlik gizliliği (dış kimlik)** : EAP kimlik isteğine yanıt olarak gönderilen metni girin. Bu metin herhangi bir değer olabilir, örneğin `anonymous`. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.

      - **Proxy ayarları**: kuruluşunuz tarafından kullanılan ara sunucu yapılandırmasını belirtin. Seçenekleriniz şunlardır:

        - **Hiçbiri** -proxy sunucusu kullanmazsınız.
        - **Otomatik** – ara *sunucu URL 'si* ayarını kullanılabilir hale getirmek için bu seçeneği belirleyin. proxy sunucusu veya proxy sunucularınızın bir listesini Içeren bir proxy otomatik yapılandırma (PAC) dosyası belirtin.

      - **Proxy sunucusu URL 'si**: Bu ayar, *Ara sunucu ayarlarını* *Otomatik*olarak belirlediğinizde kullanılabilir. Cihazları proxy sunucunuza yönlendirmek için aşağıdaki seçeneklerden birini belirtin:

        - IP adresi. Örneğin, `10.0.0.11`
        - BIR URL. Örneğin, `http://proxyserver.contoso.com`.
        - Bir proxy otomatik yapılandırma (PAC) dosyasının URL 'SI. Örneğin: `http://proxy.contoso.com/proxy.pac`.

        PAC dosyaları hakkında daha fazla bilgi için bkz. [proxy otomatik yapılandırma (PAC) dosyası](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (Microsoft dışı bir site açar).

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturuldu ancak hiçbir şey yapmıyor. Daha sonra [bu profili atayın](device-profile-assign.md).

## <a name="more-resources"></a>Daha fazla kaynak

- Diğer platformlar dahil olmak üzere [Wi-Fi ayarlarına genel bakış](wi-fi-settings-configure.md).

- Android Kurumsal veya Android bilgi noktası cihazları mı kullanıyorsunuz? Yanıt Evet ise, [Android Enterprise ve adanmış cihazlar çalıştıran cihazlar Için Wi-Fi ayarlarına](wi-fi-settings-android-enterprise.md)bakın.
