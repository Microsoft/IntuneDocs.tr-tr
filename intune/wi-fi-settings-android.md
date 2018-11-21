---
title: Microsoft Intune’da Android cihazları için Wi-Fi ayarlarını yapılandırma - Azure | Microsoft Docs
titleSuffix: ''
description: Android için bir Wi-Fi cihaz yapılandırma profili oluşturun veya ekleyin. Microsoft Intune’da sertifika ekleme, EAP türü seçme ve bir kimlik doğrulama yöntemi seçme gibi farklı ayarları görün.
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
ms.openlocfilehash: 834d9c0012e12620f4ac61de916eabfb598d02f5
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52179668"
---
# <a name="add-wi-fi-settings-for-devices-running-android-in-microsoft-intune"></a>Microsoft Intune’da Android çalıştıran cihazlar için Wi-Fi ayarları ekleme

Belirli Wi-Fi ayarları ile bir profil oluşturabilir ve ardından bu profili Android cihazlarınıza dağıtabilirsiniz. Microsoft Intune; ağınızda kimlik doğrulama, bir PKS veya SCEP sertifikası ekleme ve daha fazlası gibi pek çok özellik sunar.

Bu Wi-Fi ayarları iki kategoriye ayrılır: Temel ayarlar ve Kurumsal düzeydeki ayarlar.

Bu makalede bu ayarlar açıklanır.

## <a name="before-you-begin"></a>Başlamadan önce

[Cihaz profili oluşturma](device-profile-create.md).

## <a name="basic-profile"></a>Temel profil

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

- Diğer platformlar dahil olmak üzere [Wi-Fi ayarlarına genel bakış](wi-fi-settings-configure.md).

- Android Kurumsal veya Android bilgi noktası cihazları mı kullanıyorsunuz? Cevabınız evetse [Android Kurumsal ve Android Bilgi Noktası çalıştıran cihazlar için Wi-Fi ayarları ekleme](wi-fi-settings-android-enterprise.md) bölümüne bakın.
