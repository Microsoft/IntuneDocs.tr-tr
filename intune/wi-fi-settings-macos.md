---
title: Microsoft Intune - Azure’da macOS cihazlar için Wi-Fi ayarlarını içeri aktarma - Azure | Microsoft Docs
titleSuffix: ''
description: macOS cihazlar için bir Wi-Fi cihaz yapılandırma profili oluşturun veya ekleyin. Microsoft Intune’da sertifika ekleme, EAP türü seçme ve bir kimlik doğrulama yöntemi seçme gibi farklı ayarları görün.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/18/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 551d77b21e69eca76c4d9804130f253a69ca736b
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61514693"
---
# <a name="add-wi-fi-settings-for-macos-devices-in-microsoft-intune"></a>Microsoft Intune’da macOS cihazlar için Wi-Fi ayarları ekleme

Belirli Wi-Fi ayarları ile bir profil oluşturabilir ve ardından bu profili macOS cihazlarınıza dağıtabilirsiniz. Microsoft Intune; ağınızda kimlik doğrulama, bir PKS veya SCEP sertifikası ekleme ve daha fazlası gibi pek çok özellik sunar.

Bu Wi-Fi ayarları olarak iki kategoriye ayrılır: Temel ayarları ve kurumsal düzeyde ayarlar.

Bu makalede bu ayarlar açıklanır.

## <a name="before-you-begin"></a>Başlamadan önce

[Cihaz profili oluşturma](device-profile-create.md).

## <a name="basic-profiles"></a>Temel profiller

- **Wi-Fi türü**: **Temel**’i seçin.
- **Ağ adı**: Bu Wi-Fi bağlantısı için bir ad girin. Bu değer, kullanıcıların cihazlarında kullanılabilir bağlantılar listesine göz attıklarında görecekleri addır.
- **SSID**: Kısaltması **hizmet kümesi tanımlayıcısı**. Bu özellik, cihazların bağlandığı kablosuz ağın gerçek adıdır. Bununla birlikte, bağlantıyı seçen kullanıcılar yalnızca yapılandırdığınız ağ adını görür.
- **Otomatik olarak bağlan**: Seçin **etkinleştirme** cihaz menzil içindeyken otomatik olarak bu ağa bağlanmak için. Cihazların otomatik olarak bağlanmasını önlemek için **Devre dışı bırak**’ı seçin.
- **Gizli ağ**: Seçin **etkinleştirme** bu ağın, cihazdaki kullanılabilir ağlar listesinde gizlemek için. SSID yayınlanmaz. Cihazdaki kullanılabilir ağlar listesinde bu ağı göstermek için **Devre dışı bırak**’ı seçin.
- **Güvenlik türü**: Wi-Fi ağına kimlik doğrulaması için güvenlik protokolü seçin. Seçenekleriniz şunlardır:

  - **Açık (kimlik doğrulamasız)**: Ağ güvenli değilse, yalnızca bu seçeneği kullanın.
  - **WPA/WPA2 - Kişisel**: Parolayı girin **önceden paylaşılan anahtar**. Kuruluşunuzun ağı ayarlandığında veya yapılandırıldığında bir parola veya ağ anahtarı da yapılandırılır. PSK değeri için bu parolayı veya ağ anahtarını girin.
  - **4**

- **Proxy ayarlarını**: Seçenekleriniz şunlardır:
  - **Hiçbiri**: Hiçbir proxy ayarı yapılandırılır.
  - **El ile**: Girin **Proxy sunucu adresi** bir IP adresi olarak ve kendi **bağlantı noktası numarası**.
  - **Otomatik**: Proxy sunucusunu yapılandırmak için bir dosya kullanın. Yapılandırma dosyasını içeren **Proxy sunucu URL’si** (örneğin `http://proxy.contoso.com`) değerini girin.

## <a name="enterprise-profiles"></a>Kurumsal profiller

- **Wi-Fi türü**: Seçin **Kurumsal**.
- **SSID**: Kısaltması **hizmet kümesi tanımlayıcısı**. Bu özellik, cihazların bağlandığı kablosuz ağın gerçek adıdır. Bununla birlikte, bağlantıyı seçen kullanıcılar yalnızca yapılandırdığınız ağ adını görür.
- **Otomatik olarak bağlan**: Seçin **etkinleştirme** cihaz menzil içindeyken otomatik olarak bu ağa bağlanmak için. Cihazların otomatik olarak bağlanmasını önlemek için **Devre dışı bırak**’ı seçin.
- **Gizli ağ**: Seçin **etkinleştirme** bu ağın, cihazdaki kullanılabilir ağlar listesinde gizlemek için. SSID yayınlanmaz. Cihazdaki kullanılabilir ağlar listesinde bu ağı göstermek için **Devre dışı bırak**’ı seçin.

- **EAP türü**: Güvenli kablosuz bağlantıların kimliğini doğrulamak için kullanılan Genişletilebilir Kimlik Doğrulama Protokolü (EAP) türünü seçin. Seçenekleriniz şunlardır:

  - **EAP-FAST**: Girin **korumalı erişim kimlik bilgisi (PAC) ayarları**. Bu seçenek, istemci ile kimlik doğrulama sunucusu arasında kimliği doğrulanmış bir tünel oluşturmak için korumalı erişim kimlik bilgilerini kullanır. Seçenekleriniz şunlardır:
    - **(PAC) kullanma**
    - **PAC kullan**: Mevcut bir PAC dosyası varsa, bunu kullanın.
    - **PAC'yi kullan ve sağla**: Oluşturun ve cihazlarınıza PAC dosyasını ekleyin.
    - **Kullanabilir ve anonim olarak PAC sağla**: Oluşturun ve için sunucu kimliği doğrulanmadan PAC dosyasını cihazlarınıza ekleyin.

  - **EAP-SIM**

  - **EAP-TLS**: Şunları da girin:

    - **Sunucu güveni** - **sertifika sunucu adları**: **Ekleme** , güvenilen sertifika yetkiliniz (CA) tarafından verilen sertifikalarda kullanılan bir veya daha fazla yaygın olarak kullanılan adları. Bu bilgiyi girdikten sonra bu Wi-Fi ağına bağlanırken kullanıcının cihazında görüntülenen dinamik güven penceresini atlayabilirsiniz.
    - **Sunucu doğrulaması için kök sertifika**: Var olan bir güvenilen kök sertifika profilini seçin. Bu sertifika, istemci ağa bağlandığında sunucuya sunulur ve bağlantının kimliğini doğrulamak için kullanılır.

      Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

    - **İstemci kimlik doğrulaması** - **istemci kimlik doğrulaması (kimlik sertifikası) için istemci sertifikası**: SCEP veya PKCS istemci cihaza da dağıtılmış olan sertifika profilini seçin. Bu sertifika, bağlantının kimliğini doğrulamak için cihaz tarafından sunucuya sunulan kimliktir.

      Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

  - **EAP-TTLS**: Şunları da girin:

    - **Sunucu güveni** - **sertifika sunucu adları**: **Ekleme** , güvenilen sertifika yetkiliniz (CA) tarafından verilen sertifikalarda kullanılan bir veya daha fazla yaygın olarak kullanılan adları. Bu bilgiyi girdikten sonra bu Wi-Fi ağına bağlanırken kullanıcının cihazında görüntülenen dinamik güven penceresini atlayabilirsiniz.
    - **Sunucu doğrulaması için kök sertifika**: Var olan bir güvenilen kök sertifika profilini seçin. Bu sertifika, istemci ağa bağlandığında sunucuya sunulur ve bağlantının kimliğini doğrulamak için kullanılır.

      Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

    - **İstemci Kimlik Doğrulaması** - Bir **Kimlik doğrulama yöntemi** seçin. Seçenekleriniz şunlardır:

      - **Kullanıcı adı ve parola**: Bağlantı kimliğini doğrulamak için bir kullanıcı adı ve parola girmesini. Şunları da girin:
        - **EAP dışı yöntem (iç kimlik)**: Bağlantı kimliğini nasıl seçin. Wi-Fi ağınızda yapılandırılmış olan protokolü seçtiğinizden emin olun.

          Seçenekleriniz şunlardır: **Şifrelenmemiş parola (PAP)**, **karşılıklı kimlik doğrulama protokolü (CHAP)**, **Microsoft CHAP (MS-CHAP)**, veya **Microsoft CHAP Version 2 (MS-CHAP v2)**

      - **Sertifikaları**: SCEP veya PKCS istemci cihaza da dağıtılmış olan sertifika profilini seçin. Bu sertifika, bağlantının kimliğini doğrulamak için cihaz tarafından sunucuya sunulan kimliktir.

        Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

      - **Kimlik gizliliği (Dış kimlik)**: Bir EAP kimlik isteğine yanıt olarak gönderilen metni girin. Bu metin herhangi bir değer olabilir, örneğin `anonymous`. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.

  - **LEAP**

  - **PEAP**: Şunları da girin:

    - **Sunucu güveni** - **sertifika sunucu adları**: **Ekleme** , güvenilen sertifika yetkiliniz (CA) tarafından verilen sertifikalarda kullanılan bir veya daha fazla yaygın olarak kullanılan adları. Bu bilgiyi girdikten sonra bu Wi-Fi ağına bağlanırken kullanıcının cihazında görüntülenen dinamik güven penceresini atlayabilirsiniz.
    - **Sunucu doğrulaması için kök sertifika**: Var olan bir güvenilen kök sertifika profilini seçin. Bu sertifika, istemci ağa bağlandığında sunucuya sunulur ve bağlantının kimliğini doğrulamak için kullanılır.

      Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

    - **İstemci Kimlik Doğrulaması** - Bir **Kimlik doğrulama yöntemi** seçin. Seçenekleriniz şunlardır:

      - **Kullanıcı adı ve parola**: Bağlantı kimliğini doğrulamak için bir kullanıcı adı ve parola girmesini. 

      - **Sertifikaları**: SCEP veya PKCS istemci cihaza da dağıtılmış olan sertifika profilini seçin. Bu sertifika, bağlantının kimliğini doğrulamak için cihaz tarafından sunucuya sunulan kimliktir.

        Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

      - **Kimlik gizliliği (Dış kimlik)**: Bir EAP kimlik isteğine yanıt olarak gönderilen metni girin. Bu metin herhangi bir değer olabilir, örneğin `anonymous`. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.

- **Proxy ayarlarını**: Seçenekleriniz şunlardır:
  - **Hiçbiri**: Hiçbir proxy ayarı yapılandırılır.
  - **El ile**: Girin **Proxy sunucu adresi** bir IP adresi olarak ve kendi **bağlantı noktası numarası**.
  - **Otomatik**: Proxy sunucusunu yapılandırmak için bir dosya kullanın. Yapılandırma dosyasını içeren **Proxy sunucu URL’si** (örneğin `http://proxy.contoso.com`) değerini girin.

Değişikliklerinizi kaydetmek için **Tamam** > **Oluştur**’u seçin. Profil oluşturuldu ve profiller listesinde gösteriliyor.

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturuldu ancak hiçbir şey yapmıyor. Daha sonra [bu profili atayın](device-profile-assign.md).

## <a name="more-resources"></a>Daha fazla kaynak

Diğer kullanılabilir platformlar dahil olmak üzere [Wi-Fi ayarlarına genel bakış](wi-fi-settings-configure.md).
