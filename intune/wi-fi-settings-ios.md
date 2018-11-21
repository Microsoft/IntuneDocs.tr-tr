---
title: Microsoft Intune - Azure’da iOS cihazlar için Wi-Fi ayarlarını yapılandırma - Azure | Microsoft Docs
titleSuffix: ''
description: iOS cihazlar için bir Wi-Fi cihaz yapılandırma profili oluşturun veya ekleyin. Microsoft Intune’da sertifika ekleme, EAP türü seçme ve bir kimlik doğrulama yöntemi seçme gibi farklı ayarları görün.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 6d84c64e93f986a86e90cd9b7b5341fd8ea97d12
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52180213"
---
# <a name="add-wi-fi-settings-for-ios-devices-in-microsoft-intune"></a>Microsoft Intune’da iOS cihazlar için Wi-Fi ayarları ekleme

Belirli Wi-Fi ayarları ile bir profil oluşturabilir ve ardından bu profili iOS cihazlarınıza dağıtabilirsiniz. Microsoft Intune; ağınızda kimlik doğrulama, bir PKS veya SCEP sertifikası ekleme ve daha fazlası gibi pek çok özellik sunar.

Bu Wi-Fi ayarları iki kategoriye ayrılır: Temel ayarlar ve Kurumsal düzeydeki ayarlar.

Bu makalede bu ayarlar açıklanır.

## <a name="before-you-begin"></a>Başlamadan önce

[Cihaz profili oluşturma](device-profile-create.md).

## <a name="basic-profiles"></a>Temel profiller

- **Wi-Fi türü**: **Temel**’i seçin.
- **Ağ adı**: Bu Wi-Fi bağlantısı için bir ad girin. Bu değer, kullanıcıların cihazlarında kullanılabilir bağlantılar listesine göz attıklarında görecekleri addır.
- **SSID**: **Hizmet kümesi tanımlayıcısının** kısaltması. Bu özellik, cihazların bağlandığı kablosuz ağın gerçek adıdır. Bununla birlikte, bağlantıyı seçen kullanıcılar yalnızca yapılandırdığınız ağ adını görür.
- **Otomatik olarak bağlan**: Cihaz alana girdiğinde bu ağa otomatik olarak bağlanmak için **Etkinleştir**’i seçin. Cihazların otomatik olarak bağlanmasını önlemek için **Devre dışı bırak**’ı seçin.
- **Gizli ağ**: Cihazdaki kullanılabilir ağlar listesinde bu ağı gizlemek için **Etkinleştir**’i seçin. SSID yayınlanmaz. Cihazdaki kullanılabilir ağlar listesinde bu ağı göstermek için **Devre dışı bırak**’ı seçin.
- **Güvenlik türü**: Wi-Fi ağında kimlik doğrulamak için kullanılacak güvenlik protokolünü seçin. Seçenekleriniz şunlardır:

  - **Açık (kimlik doğrulamasız)**: Bu seçeneği yalnızca ağ güvenlik altına alınmamış olduğunda kullanın.
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

    - **Sunucu Güveni** - **Sertifika sunucu adları**: Güvenilen sertifika yetkiliniz (CA) tarafından verilen sertifikalarda yaygın olarak kullanılan bir veya birden çok ad **ekleyin**. Bu bilgiyi girdikten sonra bu Wi-Fi ağına bağlanırken kullanıcının cihazında görüntülenen dinamik güven penceresini atlayabilirsiniz.
    - **Sunucu doğrulaması için kök sertifika**: Mevcut bir güvenilen kök sertifika profilini seçin. Bu sertifika, istemci ağa bağlandığında sunucuya sunulur ve bağlantının kimliğini doğrulamak için kullanılır.

      Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

    - **İstemci Kimlik Doğrulaması** - **İstemci kimlik doğrulaması için istemci sertifikası (Kimlik sertifikası)**: Cihaza da dağıtılmış olan SCEP veya PKCS istemci sertifikası profilini seçin. Bu sertifika, bağlantının kimliğini doğrulamak için cihaz tarafından sunucuya sunulan kimliktir.

      Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

  - **EAP-TTLS**: Ayrıca şunları girin:

    - **Sunucu Güveni** - **Sertifika sunucu adları**: Güvenilen sertifika yetkiliniz (CA) tarafından verilen sertifikalarda yaygın olarak kullanılan bir veya birden çok ad **ekleyin**. Bu bilgiyi girdikten sonra bu Wi-Fi ağına bağlanırken kullanıcının cihazında görüntülenen dinamik güven penceresini atlayabilirsiniz.
    - **Sunucu doğrulaması için kök sertifika**: Mevcut bir güvenilen kök sertifika profilini seçin. Bu sertifika, istemci ağa bağlandığında sunucuya sunulur ve bağlantının kimliğini doğrulamak için kullanılır.

      Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

    - **İstemci Kimlik Doğrulaması** - Bir **Kimlik doğrulama yöntemi** seçin. Seçenekleriniz şunlardır:

      - **Kullanıcı adı ve Parola**: Bağlantının kimliğini doğrulamak için kullanıcıdan bir kullanıcı adı ve parola girmesini isteyin. Şunları da girin:
        - **EAP dışı yöntem (iç kimlik)**: Bağlantının kimliğini nasıl doğrulayacağınızı seçin. Wi-Fi ağınızda yapılandırılmış olan protokolü seçtiğinizden emin olun.

          Seçenekleriniz şunlardır: **Şifrelenmemiş parola (PAP)**, **Karşılıklı Kimlik Doğrulama Protokolü (CHAP)**, **Microsoft CHAP (MS-CHAP)** veya **Microsoft CHAP Sürüm 2 (MS-CHAP v2)**

      - **Sertifikalar**: Cihaza da dağıtılmış olan SCEP veya PKCS istemci sertifikası profilini seçin. Bu sertifika, bağlantının kimliğini doğrulamak için cihaz tarafından sunucuya sunulan kimliktir.

        Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

      - **Kimlik gizliliği (dış kimlik)**: EAP kimlik isteğine yanıt olarak gönderilen metni girin. Bu metin herhangi bir değer olabilir, örneğin `anonymous`. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.

  - **LEAP**

  - **PEAP**: Ayrıca şunları girin:

    - **Sunucu Güveni** - **Sertifika sunucu adları**: Güvenilen sertifika yetkiliniz (CA) tarafından verilen sertifikalarda yaygın olarak kullanılan bir veya birden çok ad **ekleyin**. Bu bilgiyi girdikten sonra bu Wi-Fi ağına bağlanırken kullanıcının cihazında görüntülenen dinamik güven penceresini atlayabilirsiniz.
    - **Sunucu doğrulaması için kök sertifika**: Mevcut bir güvenilen kök sertifika profilini seçin. Bu sertifika, istemci ağa bağlandığında sunucuya sunulur ve bağlantının kimliğini doğrulamak için kullanılır.

      Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

    - **İstemci Kimlik Doğrulaması** - Bir **Kimlik doğrulama yöntemi** seçin. Seçenekleriniz şunlardır:

      - **Kullanıcı adı ve Parola**: Bağlantının kimliğini doğrulamak için kullanıcıdan bir kullanıcı adı ve parola girmesini isteyin. 

      - **Sertifikalar**: Cihaza da dağıtılmış olan SCEP veya PKCS istemci sertifikası profilini seçin. Bu sertifika, bağlantının kimliğini doğrulamak için cihaz tarafından sunucuya sunulan kimliktir.

        Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

      - **Kimlik gizliliği (dış kimlik)**: EAP kimlik isteğine yanıt olarak gönderilen metni girin. Bu metin herhangi bir değer olabilir, örneğin `anonymous`. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.

- **Proxy ayarları**: Seçenekleriniz şunlardır:
  - **Hiçbiri**: Hiçbir ara sunucu ayarı yapılandırılmaz.
  - **El ile**: IP adresi olarak **Proxy sunucu adresini** girin ve sunucunun **Bağlantı noktası numarasını** girin.
  - **Otomatik**: Proxy sunucusunu yapılandırmak için bir dosya kullanın. Yapılandırma dosyasını içeren **Proxy sunucu URL’si** (örneğin `http://proxy.contoso.com`) değerini girin.

Değişikliklerinizi kaydetmek için **Tamam** > **Oluştur**’u seçin. Profil oluşturuldu ve profiller listesinde gösteriliyor.

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturuldu ancak hiçbir şey yapmıyor. Daha sonra [bu profili atayın](device-profile-assign.md).

## <a name="more-resources"></a>Daha fazla kaynak

Diğer kullanılabilir platformlar dahil olmak üzere [Wi-Fi ayarlarına genel bakış](wi-fi-settings-configure.md).