---
title: Microsoft Intune - Azure’da iOS cihazlar için Wi-Fi ayarlarını yapılandırma - Azure | Microsoft Docs
titleSuffix: ''
description: iOS cihazlar için bir Wi-Fi cihaz yapılandırma profili oluşturun veya ekleyin. Microsoft Intune’da sertifika ekleme, EAP türü seçme ve bir kimlik doğrulama yöntemi seçme gibi farklı ayarları inceleyin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/13/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: dd37813e5ea0b6a64d7fae22cada06cccb01a942
ms.sourcegitcommit: 78cebd3571fed72a3a99e9d33770ef3d932ae8ca
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74059212"
---
# <a name="add-wi-fi-settings-for-ios-devices-in-microsoft-intune"></a>Microsoft Intune’da iOS cihazlar için Wi-Fi ayarları ekleme

Belirli Wi-Fi ayarları ile bir profil oluşturabilir ve ardından bu profili iOS cihazlarınıza dağıtabilirsiniz. Microsoft Intune, ağınızda kimlik doğrulaması, PKCS veya SCEP sertifikası ekleme ve daha fazlası dahil olmak üzere birçok özellik sunar.

Bu Wi-Fi ayarları iki kategoriye ayrılır: Temel ayarlar ve Kurumsal düzeydeki ayarlar.

Bu makalede bu ayarlar açıklanır.

## <a name="before-you-begin"></a>Başlamadan önce

[Cihaz profili oluşturma](../device-profile-create.md).

> [!NOTE]
> Bu ayarlar tüm kayıt türleri için kullanılabilir. Kayıt türleri hakkında daha fazla bilgi için bkz. [iOS kaydı](../enrollment/ios-enroll.md).

## <a name="basic-profiles"></a>Temel profiller

- **Wi-Fi türü**: **Temel**’i seçin.
- **Ağ adı**: Bu Wi-Fi bağlantısı için bir ad girin. Bu değer, kullanıcıların cihazlarında kullanılabilir bağlantılar listesine göz attıklarında görecekleri addır.
- **SSID**: **Hizmet kümesi tanımlayıcısının** kısaltması. Bu özellik, cihazların bağlandığı kablosuz ağın gerçek adıdır. Bununla birlikte, bağlantıyı seçen kullanıcılar yalnızca yapılandırdığınız ağ adını görür.
- **Otomatik olarak bağlan**: Cihaz alana girdiğinde bu ağa otomatik olarak bağlanmak için **Etkinleştir**’i seçin. Cihazların otomatik olarak bağlanmasını önlemek için **Devre dışı bırak**’ı seçin.
- **Gizli ağ**: ağ SSID 'si yayınlanmadıysa **Etkinleştir** ' i seçin. Ağın SSID 'si yayınlandıysanız ve görülemiyorsa **devre dışı bırak** ' ı seçin.
- **Güvenlik türü**: Wi-Fi ağında kimlik doğrulamak için kullanılacak güvenlik protokolünü seçin. Seçenekleriniz şunlardır:

  - **Açık (kimlik doğrulamasız)** : Bu seçeneği yalnızca ağ güvenlik altına alınmamış olduğunda kullanın.
  - **WPA/WPA2 - Kişisel**: **Önceden paylaşılan anahtar** olarak parolayı girin. Kuruluşunuzun ağı ayarlandığında veya yapılandırıldığında bir parola veya ağ anahtarı da yapılandırılır. PSK değeri için bu parolayı veya ağ anahtarını girin.
  - **4**

- **Proxy ayarları**: Seçenekleriniz şunlardır:
  - **Hiçbiri**: Hiçbir ara sunucu ayarı yapılandırılmaz.
  - **El ile**: IP adresi olarak **Proxy sunucu adresini** girin ve sunucunun **Bağlantı noktası numarasını** girin.
  - **Otomatik**: Proxy sunucusunu yapılandırmak için bir dosya kullanın. Yapılandırma dosyasını içeren **Proxy sunucu URL’si** (örneğin `http://proxy.contoso.com`) değerini girin.

## <a name="enterprise-profiles"></a>Kurumsal profiller

- **Wi-Fi türü**: **Kurumsal**’ı seçin.
- **SSID**: **Hizmet kümesi tanımlayıcısının** kısaltması. Bu özellik, cihazların bağlandığı kablosuz ağın gerçek adıdır. Bununla birlikte, bağlantıyı seçen kullanıcılar yalnızca yapılandırdığınız ağ adını görür.
- **Otomatik olarak bağlan**: Cihaz alana girdiğinde bu ağa otomatik olarak bağlanmak için **Etkinleştir**’i seçin. Cihazların otomatik olarak bağlanmasını önlemek için **Devre dışı bırak**’ı seçin.
- **Gizli ağ**: Cihazdaki kullanılabilir ağlar listesinde bu ağı gizlemek için **Etkinleştir**’i seçin. SSID yayınlanmaz. Cihazdaki kullanılabilir ağlar listesinde bu ağı göstermek için **Devre dışı bırak**’ı seçin.

- **EAP türü**: Güvenli kablosuz bağlantıların kimliğini doğrulamak için kullanılan Genişletilebilir Kimlik Doğrulama Protokolü (EAP) türünü seçin. Seçenekleriniz şunlardır:

  - **EAP-FAST**: **Korumalı Erişim Kimlik Bilgisi (PAC) Ayarları**’nı girin. Bu seçenek, istemci ile kimlik doğrulama sunucusu arasında kimliği doğrulanmış bir tünel oluşturmak için korumalı erişim kimlik bilgilerini kullanır. Seçenekleriniz şunlardır:
    - **(PAC) kullanma**
    - **(PAC) kullan**: Mevcut bir PAC dosyası varsa bunu kullanın.
    - **PAC’yi kullan ve sağla**: PAC dosyasını oluşturun ve cihazlarınıza sağlayın.
    - **PAC’yi anonim olarak kullan ve sağla**: PAC dosyasını sunucuda kimlik doğrulamadan oluşturun ve cihazlarınıza ekleyin.

  - **EAP-SIM**

  - **EAP-TLS**: Ayrıca şunları girin:

    - **Sunucu güveni** - **sertifika sunucu adları**: güvenilir SERTIFIKA yetkiliniz (CA) tarafından verilen sertifikalarda kablosuz ağ erişim sunucularınıza kullanılan bir veya daha fazla ortak ad **ekleyin** . Örneğin `mywirelessserver.contoso.com` veya `mywirelessserver` ' i ekleyin. Bu bilgiyi girdikten sonra bu Wi-Fi ağına bağlanırken kullanıcının cihazında görüntülenen dinamik güven penceresini atlayabilirsiniz.
    - **Sunucu doğrulaması için kök sertifika**: Mevcut bir güvenilen kök sertifika profilini seçin. Bu sertifika, istemcinin kablosuz ağ erişim sunucusunun sertifikasına güvenmesini sağlar.

    - **Istemci kimlik doğrulaması** Bir **kimlik doğrulama yöntemi**seçin. Seçenekleriniz şunlardır:

      - **Türetilmiş kimlik bilgileri**: kullanıcının akıllı kartından türetilmiş bir sertifika kullanın. Türetilmiş bir kimlik bilgisi veren yapılandırılmamışsa, Intune sizden bir tane eklemeniz istenir. Daha fazla bilgi için bkz. [Microsoft Intune türetilmiş kimlik bilgilerini kullanma](../protect/derived-credentials.md).

      - **Sertifikalar**: Cihaza da dağıtılmış olan SCEP veya PKCS istemci sertifikası profilini seçin. Bu sertifika, bağlantının kimliğini doğrulamak için cihaz tarafından sunucuya sunulan kimliktir.

    - **Kimlik gizliliği (dış kimlik)** : EAP kimlik isteğine yanıt olarak gönderilen metni girin. Bu metin herhangi bir değer olabilir, örneğin `anonymous`. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.

  - **EAP-TTLS**: Ayrıca şunları girin:

    - **Sunucu güveni** - **sertifika sunucu adları**: güvenilir SERTIFIKA yetkiliniz (CA) tarafından verilen sertifikalarda kablosuz ağ erişim sunucularınıza kullanılan bir veya daha fazla ortak ad **ekleyin** . Örneğin `mywirelessserver.contoso.com` veya `mywirelessserver` ' i ekleyin. Bu bilgiyi girdikten sonra bu Wi-Fi ağına bağlanırken kullanıcının cihazında görüntülenen dinamik güven penceresini atlayabilirsiniz.
    - **Sunucu doğrulaması için kök sertifika**: Mevcut bir güvenilen kök sertifika profilini seçin. Bu sertifika, istemcinin kablosuz ağ erişim sunucusunun sertifikasına güvenmesini sağlar.

    - **İstemci Kimlik Doğrulaması** - Bir **Kimlik doğrulama yöntemi** seçin. Seçenekleriniz şunlardır:

      - **Türetilmiş kimlik bilgileri**: kullanıcının akıllı kartından türetilmiş bir sertifika kullanın. Türetilmiş bir kimlik bilgisi veren yapılandırılmamışsa, Intune sizden bir tane eklemeniz istenir. Daha fazla bilgi için bkz. [Microsoft Intune türetilmiş kimlik bilgilerini kullanma](../protect/derived-credentials.md).

      - **Kullanıcı adı ve Parola**: Bağlantının kimliğini doğrulamak için kullanıcıdan bir kullanıcı adı ve parola girmesini isteyin. Şunları da girin:
        - **EAP dışı yöntem (iç kimlik)** : Bağlantının kimliğini nasıl doğrulayacağınızı seçin. Wi-Fi ağınızda yapılandırılmış olan protokolü seçtiğinizden emin olun.

          Seçenekleriniz şunlardır: **Şifrelenmemiş parola (PAP)** , **Karşılıklı Kimlik Doğrulama Protokolü (CHAP)** , **Microsoft CHAP (MS-CHAP)** veya **Microsoft CHAP Sürüm 2 (MS-CHAP v2)**

      - **Sertifikalar**: Cihaza da dağıtılmış olan SCEP veya PKCS istemci sertifikası profilini seçin. Bu sertifika, bağlantının kimliğini doğrulamak için cihaz tarafından sunucuya sunulan kimliktir.

      - **Kimlik gizliliği (dış kimlik)** : EAP kimlik isteğine yanıt olarak gönderilen metni girin. Bu metin herhangi bir değer olabilir, örneğin `anonymous`. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.

  - **LEAP**

  - **PEAP**: Ayrıca şunları girin:

    - **Sunucu güveni** - **sertifika sunucu adları**: güvenilir SERTIFIKA yetkiliniz (CA) tarafından verilen sertifikalarda kablosuz ağ erişim sunucularınıza kullanılan bir veya daha fazla ortak ad **ekleyin** . Örneğin `mywirelessserver.contoso.com` veya `mywirelessserver` ' i ekleyin. Bu bilgiyi girdikten sonra bu Wi-Fi ağına bağlanırken kullanıcının cihazında görüntülenen dinamik güven penceresini atlayabilirsiniz.
    - **Sunucu doğrulaması için kök sertifika**: Mevcut bir güvenilen kök sertifika profilini seçin. Bu sertifika, istemcinin kablosuz ağ erişim sunucusunun sertifikasına güvenmesini sağlar.

    - **İstemci Kimlik Doğrulaması** - Bir **Kimlik doğrulama yöntemi** seçin. Seçenekleriniz şunlardır:

      - **Türetilmiş kimlik bilgileri**: kullanıcının akıllı kartından türetilmiş bir sertifika kullanın. Türetilmiş bir kimlik bilgisi veren yapılandırılmamışsa, Intune sizden bir tane eklemeniz istenir. Daha fazla bilgi için bkz. [Microsoft Intune türetilmiş kimlik bilgilerini kullanma](../protect/derived-credentials.md).

      - **Kullanıcı adı ve Parola**: Bağlantının kimliğini doğrulamak için kullanıcıdan bir kullanıcı adı ve parola girmesini isteyin. 

      - **Sertifikalar**: Cihaza da dağıtılmış olan SCEP veya PKCS istemci sertifikası profilini seçin. Bu sertifika, bağlantının kimliğini doğrulamak için cihaz tarafından sunucuya sunulan kimliktir.

      - **Kimlik gizliliği (dış kimlik)** : EAP kimlik isteğine yanıt olarak gönderilen metni girin. Bu metin herhangi bir değer olabilir, örneğin `anonymous`. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.

- **Proxy ayarları**: Seçenekleriniz şunlardır:
  - **Hiçbiri**: Hiçbir ara sunucu ayarı yapılandırılmaz.
  - **El ile**: IP adresi olarak **Proxy sunucu adresini** girin ve sunucunun **Bağlantı noktası numarasını** girin.
  - **Otomatik**: Proxy sunucusunu yapılandırmak için bir dosya kullanın. Yapılandırma dosyasını içeren **Proxy sunucu URL’si** (örneğin `http://proxy.contoso.com`) değerini girin.

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturuldu ancak hiçbir şey yapmıyor. Sonra, [Bu profili atayın](device-profile-assign.md)ve [durumunu izleyin](device-profile-monitor.md).

[Android](wi-fi-settings-android.md), [Android Enterprise](wi-fi-settings-android-enterprise.md), [MacOS](wi-fi-settings-macos.md)ve [Windows 10](wi-fi-settings-windows.md) cihazlarında Wi-Fi ayarlarını yapılandırın.
