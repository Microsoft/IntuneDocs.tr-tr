---
title: Microsoft Intune - Azure - Android Kurumsal ve bilgi noktası cihazları için Wi-Fi ayarlarını yapılandırma | Microsoft Docs
titleSuffix: ''
description: Android Kurumsal ve Android Bilgi Noktası için bir Wi-Fi cihaz yapılandırma profili oluşturun veya ekleyin. Microsoft Intune’da sertifika ekleme, EAP türü seçme ve bir kimlik doğrulama yöntemi seçme gibi farklı ayarları inceleyin. Bilgi noktası cihazlarında ağınızın Önceden paylaşılan anahtarını da girin.
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
ms.custom: intune-azure
ms.openlocfilehash: c2983f2f7b7079f73c857bf7caafe4236373c5dc
ms.sourcegitcommit: cff65435df070940da390609d6376af6ccdf0140
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2018
ms.locfileid: "49431968"
---
# <a name="add-wi-fi-settings-for-devices-running-android-enterprise-and-android-kiosk-in-microsoft-intune"></a>Microsoft Intune’da Android Kurumsal ve Android Bilgi Noktası çalıştıran cihazlar için Wi-Fi ayarları ekleme

Belirli Wi-Fi ayarları ile bir profil oluşturabilir ve ardından bu profili Android Kurumsal ve Android bilgi noktası cihazlarınıza dağıtabilirsiniz. Microsoft Intune; ağınızda kimlik doğrulama, bir önceden paylaşılan anahtar kullanma ve daha fazlası gibi pek çok özellik sunar.

Bu makalede bu ayarlar açıklanır.

## <a name="before-you-begin"></a>Başlamadan önce

[Cihaz profili oluşturma](device-profile-create.md).

## <a name="device-owner-only---kiosk"></a>Yalnızca cihaz sahibi - bilgi noktası

Bir Android Kurumsal cihazı bilgi noktası olarak kullanıyorsanız bu seçeneği belirleyin.

- **Ağ adı**: Bu Wi-Fi bağlantısı için bir ad girin. Bu değer, kullanıcıların cihazlarında kullanılabilir bağlantılar listesine göz attıklarında görecekleri addır.
- **SSID**: **Hizmet kümesi tanımlayıcısının** kısaltması. Bu ayar, cihazların bağlandığı kablosuz ağın gerçek adıdır. Ancak bağlantıyı seçen kullanıcılar yalnızca yapılandırdığınız **ağ adını** görür.
- **Otomatik olarak bağlan**: Cihaz alana girdiğinde bu ağa otomatik olarak bağlanmak için **Etkinleştir**’i seçin. Cihazların otomatik olarak bağlanmasını önlemek için **Devre dışı bırak**’ı seçin.
- **Gizli ağ**: Cihazdaki kullanılabilir ağlar listesinde bu ağı gizlemek için **Etkinleştir**’i seçin. SSID yayınlanmaz. Cihazdaki kullanılabilir ağlar listesinde bu ağı göstermek için **Devre dışı bırak**’ı seçin.
- **Wi-Fi türü**: Wi-Fi ağında kimlik doğrulamak için kullanılacak güvenlik protokolünü seçin. Seçenekleriniz şunlardır:

  - **Açık (kimlik doğrulamasız)**: Bu seçeneği yalnızca ağ güvenlik altına alınmamış olduğunda kullanın.
  - **WEP-Önceden paylaşılan anahtar**: **Önceden paylaşılan anahtar** olarak parolayı girin. Kuruluşunuzun ağı ayarlandığında veya yapılandırıldığında bir parola veya ağ anahtarı da yapılandırılır. PSK değeri için bu parolayı veya ağ anahtarını girin.
  - **WPA-Önceden paylaşılan anahtar**: **Önceden paylaşılan anahtar** olarak parolayı girin. Kuruluşunuzun ağı ayarlandığında veya yapılandırıldığında bir parola veya ağ anahtarı da yapılandırılır. PSK değeri için bu parolayı veya ağ anahtarını girin.

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="work-profile-only"></a>Yalnızca iş profili

### <a name="basic-settings"></a>Temel ayarlar

- **Wi-Fi türü**: **Temel**’i seçin.
- **SSID**: **Hizmet kümesi tanımlayıcısının** kısaltması. Bu ayar, cihazların bağlandığı kablosuz ağın gerçek adıdır.
- **Otomatik olarak bağlan**: Cihaz alana girdiğinde bu ağa otomatik olarak bağlanmak için **Etkinleştir**’i seçin. Cihazların otomatik olarak bağlanmasını önlemek için **Devre dışı bırak**’ı seçin.
- **Gizli ağ**: Cihazdaki kullanılabilir ağlar listesinde bu ağı gizlemek için **Etkinleştir**’i seçin. SSID yayınlanmaz. Cihazdaki kullanılabilir ağlar listesinde bu ağı göstermek için **Devre dışı bırak**’ı seçin.

## <a name="enterprise-profile"></a>Kurumsal profil

- **Wi-Fi türü**: **Kurumsal**’ı seçin.
- **SSID**: **Hizmet kümesi tanımlayıcısının** kısaltması. Bu ayar, cihazların bağlandığı kablosuz ağın gerçek adıdır.
- **Otomatik olarak bağlan**: Cihaz alana girdiğinde bu ağa otomatik olarak bağlanmak için **Etkinleştir**’i seçin. Cihazların otomatik olarak bağlanmasını önlemek için **Devre dışı bırak**’ı seçin.
- **Gizli ağ**: Cihazdaki kullanılabilir ağlar listesinde bu ağı gizlemek için **Etkinleştir**’i seçin. SSID yayınlanmaz. Cihazdaki kullanılabilir ağlar listesinde bu ağı göstermek için **Devre dışı bırak**’ı seçin.
- **EAP türü**: Güvenli kablosuz bağlantıların kimliğini doğrulamak için kullanılan Genişletilebilir Kimlik Doğrulama Protokolü (EAP) türünü seçin. Seçenekleriniz şunlardır: 

  - **EAP-TLS**: Ayrıca şunları girin:

    - **Sunucu Güveni** - **Sunucu doğrulaması için kök sertifika**: Mevcut bir güvenilen kök sertifika profilini seçin. Bu sertifika, istemci ağa bağlandığında sunucuya sunulur ve bağlantının kimliğini doğrulamak için kullanılır.

      Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

    - **İstemci Kimlik Doğrulaması** - **İstemci kimlik doğrulaması için istemci sertifikası (Kimlik sertifikası)**: Cihaza da dağıtılmış olan SCEP veya PKCS istemci sertifikası profilini seçin. Bu sertifika, bağlantının kimliğini doğrulamak için cihaz tarafından sunucuya sunulan kimliktir.

      Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

  - **EAP-TTLS**: Ayrıca şunları girin:

    - **Sunucu Güveni** - **Sunucu doğrulaması için kök sertifika**: Mevcut bir güvenilen kök sertifika profilini seçin. Bu sertifika, istemci ağa bağlandığında sunucuya sunulur ve bağlantının kimliğini doğrulamak için kullanılır.

      Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

    - **İstemci Kimlik Doğrulaması** - Bir **Kimlik doğrulama yöntemi** seçin. Seçenekleriniz şunlardır:

      - **Kullanıcı adı ve Parola**: Bağlantının kimliğini doğrulamak için kullanıcıdan bir kullanıcı adı ve parola girmesini isteyin. Şunları da girin:
        - **EAP dışı yöntem (iç kimlik)**: Bağlantının kimliğini nasıl doğrulayacağınızı seçin. Wi-Fi ağınızda yapılandırılmış olan protokolü seçtiğinizden emin olun.

          Seçenekleriniz şunlardır: **Şifrelenmemiş parola (PAP)**, **Karşılıklı Kimlik Doğrulama Protokolü (CHAP)**, **Microsoft CHAP (MS-CHAP)** veya **Microsoft CHAP Sürüm 2 (MS-CHAP v2)**

      - **Sertifikalar**: Cihaza da dağıtılmış olan SCEP veya PKCS istemci sertifikası profilini seçin. Bu sertifika, bağlantının kimliğini doğrulamak için cihaz tarafından sunucuya sunulan kimliktir.

        Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

      - **Kimlik gizliliği (dış kimlik)**: EAP kimlik isteğine yanıt olarak gönderilen metni girin. Bu metin herhangi bir değer olabilir, örneğin `anonymous`. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.

  - **PEAP**: Ayrıca şunları girin:

    - **Sunucu Güveni** - **Sunucu doğrulaması için kök sertifika**: Mevcut bir güvenilen kök sertifika profilini seçin. Bu sertifika, istemci ağa bağlandığında sunucuya sunulur ve bağlantının kimliğini doğrulamak için kullanılır.

      Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

    - **İstemci Kimlik Doğrulaması** - Bir **Kimlik doğrulama yöntemi** seçin. Seçenekleriniz şunlardır:

      - **Kullanıcı adı ve Parola**: Bağlantının kimliğini doğrulamak için kullanıcıdan bir kullanıcı adı ve parola girmesini isteyin. Şunları da girin:
        - **Kimlik doğrulaması için EAP dışı yöntem (iç kimlik)**: Bağlantının kimliğini nasıl doğrulayacağınızı seçin. Wi-Fi ağınızda yapılandırılmış olan protokolü seçtiğinizden emin olun.

          Seçenekleriniz şunlardır: **Hiçbiri** veya **Microsoft CHAP Sürüm 2 (MS-CHAP v2)**

      - **Sertifikalar**: Cihaza da dağıtılmış olan SCEP veya PKCS istemci sertifikası profilini seçin. Bu sertifika, bağlantının kimliğini doğrulamak için cihaz tarafından sunucuya sunulan kimliktir.

        Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

      - **Kimlik gizliliği (dış kimlik)**: EAP kimlik isteğine yanıt olarak gönderilen metni girin. Bu metin herhangi bir değer olabilir, örneğin `anonymous`. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.

Değişikliklerinizi kaydetmek için **Tamam** > **Oluştur**’u seçin. Profil oluşturuldu ve profiller listesinde gösteriliyor.

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturuldu ancak hiçbir şey yapmıyor. Daha sonra [bu profili atayın](device-profile-assign.md).

## <a name="more-resources"></a>Daha fazla kaynak

- Android cihazlarda kullanılabilir ayarlar için [Android çalıştıran cihazlar için Wi-Fi ayarları](wi-fi-settings-android.md) bölümüne bakın.
- Diğer platformlar dahil olmak üzere [Wi-Fi ayarlarına genel bakış](wi-fi-settings-configure.md).