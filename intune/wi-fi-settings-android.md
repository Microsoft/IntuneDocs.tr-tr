---
title: Microsoft Intune’da Android cihazları için Wi-Fi ayarlarını yapılandırma - Azure | Microsoft Docs
titleSuffix: ''
description: Android için bir Wi-Fi cihaz yapılandırma profili oluşturun veya ekleyin. Microsoft Intune’da sertifika ekleme, EAP türü seçme ve bir kimlik doğrulama yöntemi seçme gibi farklı ayarları görün.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/18/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 772a7f0e02691350a9c1feb16210a9390add3580
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57397894"
---
# <a name="add-wi-fi-settings-for-devices-running-android-in-microsoft-intune"></a>Microsoft Intune’da Android çalıştıran cihazlar için Wi-Fi ayarları ekleme

Belirli Wi-Fi ayarları ile bir profil oluşturabilir ve ardından bu profili Android cihazlarınıza dağıtabilirsiniz. Microsoft Intune; ağınızda kimlik doğrulama, bir PKS veya SCEP sertifikası ekleme ve daha fazlası gibi pek çok özellik sunar.

Bu Wi-Fi ayarları olarak iki kategoriye ayrılır: Temel ayarları ve kurumsal düzeyde ayarlar.

Bu makalede bu ayarlar açıklanır.

## <a name="before-you-begin"></a>Başlamadan önce

[Cihaz profili oluşturma](device-profile-create.md).

## <a name="basic-profile"></a>Temel profil

- **Wi-Fi türü**: **Temel**’i seçin.
- **SSID**: Kısaltması **hizmet kümesi tanımlayıcısı**. Bu ayar, cihazların bağlandığı kablosuz ağın gerçek adıdır.
- **Otomatik olarak bağlan**: Seçin **etkinleştirme** cihaz menzil içindeyken otomatik olarak bu ağa bağlanmak için. Cihazların otomatik olarak bağlanmasını önlemek için **Devre dışı bırak**’ı seçin.
- **Gizli ağ**: Seçin **etkinleştirme** bu ağın, cihazdaki kullanılabilir ağlar listesinde gizlemek için. SSID yayınlanmaz. Cihazdaki kullanılabilir ağlar listesinde bu ağı göstermek için **Devre dışı bırak**’ı seçin.

## <a name="enterprise-profile"></a>Kurumsal profil

- **Wi-Fi türü**: Seçin **Kurumsal**.
- **SSID**: Kısaltması **hizmet kümesi tanımlayıcısı**. Bu ayar, cihazların bağlandığı kablosuz ağın gerçek adıdır.
- **Otomatik olarak bağlan**: Seçin **etkinleştirme** cihaz menzil içindeyken otomatik olarak bu ağa bağlanmak için. Cihazların otomatik olarak bağlanmasını önlemek için **Devre dışı bırak**’ı seçin.
- **Gizli ağ**: Seçin **etkinleştirme** bu ağın, cihazdaki kullanılabilir ağlar listesinde gizlemek için. SSID yayınlanmaz. Cihazdaki kullanılabilir ağlar listesinde bu ağı göstermek için **Devre dışı bırak**’ı seçin.
- **EAP türü**: Güvenli kablosuz bağlantıların kimliğini doğrulamak için kullanılan Genişletilebilir Kimlik Doğrulama Protokolü (EAP) türünü seçin. Seçenekleriniz şunlardır: 

  - **EAP-TLS**: Şunları da girin:

    - **Sunucu güveni** - **sunucu doğrulaması için kök sertifika**: Var olan bir güvenilen kök sertifika profilini seçin. Bu sertifika, istemci ağa bağlandığında sunucuya sunulur ve bağlantının kimliğini doğrulamak için kullanılır.

      Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

    - **İstemci kimlik doğrulaması** - **istemci kimlik doğrulaması (kimlik sertifikası) için istemci sertifikası**: SCEP veya PKCS istemci cihaza da dağıtılmış olan sertifika profilini seçin. Bu sertifika, bağlantının kimliğini doğrulamak için cihaz tarafından sunucuya sunulan kimliktir.

      Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

  - **EAP-TTLS**: Şunları da girin:

    - **Sunucu güveni** - **sunucu doğrulaması için kök sertifika**: Var olan bir güvenilen kök sertifika profilini seçin. Bu sertifika, istemci ağa bağlandığında sunucuya sunulur ve bağlantının kimliğini doğrulamak için kullanılır.

      Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

    - **İstemci Kimlik Doğrulaması** - Bir **Kimlik doğrulama yöntemi** seçin. Seçenekleriniz şunlardır:

      - **Kullanıcı adı ve parola**: Bağlantı kimliğini doğrulamak için bir kullanıcı adı ve parola girmesini. Şunları da girin:
        - **EAP dışı yöntem (iç kimlik)**: Bağlantı kimliğini nasıl seçin. Wi-Fi ağınızda yapılandırılmış olan protokolü seçtiğinizden emin olun.

          Seçenekleriniz şunlardır: **Şifrelenmemiş parola (PAP)**, **karşılıklı kimlik doğrulama protokolü (CHAP)**, **Microsoft CHAP (MS-CHAP)**, veya **Microsoft CHAP Version 2 (MS-CHAP v2)**

      - **Sertifikaları**: SCEP veya PKCS istemci cihaza da dağıtılmış olan sertifika profilini seçin. Bu sertifika, bağlantının kimliğini doğrulamak için cihaz tarafından sunucuya sunulan kimliktir.

        Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

      - **Kimlik gizliliği (Dış kimlik)**: Bir EAP kimlik isteğine yanıt olarak gönderilen metni girin. Bu metin herhangi bir değer olabilir, örneğin `anonymous`. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.

  - **PEAP**: Şunları da girin:

    - **Sunucu güveni** - **sunucu doğrulaması için kök sertifika**: Var olan bir güvenilen kök sertifika profilini seçin. Bu sertifika, istemci ağa bağlandığında sunucuya sunulur ve bağlantının kimliğini doğrulamak için kullanılır.

      Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

    - **İstemci Kimlik Doğrulaması** - Bir **Kimlik doğrulama yöntemi** seçin. Seçenekleriniz şunlardır:

      - **Kullanıcı adı ve parola**: Bağlantı kimliğini doğrulamak için bir kullanıcı adı ve parola girmesini. Şunları da girin:
        - **Kimlik doğrulaması (iç kimlik) için EAP dışı yöntem**: Bağlantı kimliğini nasıl seçin. Wi-Fi ağınızda yapılandırılmış olan protokolü seçtiğinizden emin olun.

          Seçenekleriniz şunlardır: **Hiçbiri** veya **Microsoft CHAP sürüm 2 (MS-CHAP v2)**

      - **Sertifikaları**: SCEP veya PKCS istemci cihaza da dağıtılmış olan sertifika profilini seçin. Bu sertifika, bağlantının kimliğini doğrulamak için cihaz tarafından sunucuya sunulan kimliktir.

        Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

      - **Kimlik gizliliği (Dış kimlik)**: Bir EAP kimlik isteğine yanıt olarak gönderilen metni girin. Bu metin herhangi bir değer olabilir, örneğin `anonymous`. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.

Değişikliklerinizi kaydetmek için **Tamam** > **Oluştur**’u seçin. Profil oluşturuldu ve profiller listesinde gösteriliyor.

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturuldu ancak hiçbir şey yapmıyor. Daha sonra [bu profili atayın](device-profile-assign.md).

## <a name="more-resources"></a>Daha fazla kaynak

- Diğer platformlar dahil olmak üzere [Wi-Fi ayarlarına genel bakış](wi-fi-settings-configure.md).

- Android Kurumsal veya Android bilgi noktası cihazları mı kullanıyorsunuz? Cevabınız evetse [Android Kurumsal ve Android Bilgi Noktası çalıştıran cihazlar için Wi-Fi ayarları ekleme](wi-fi-settings-android-enterprise.md) bölümüne bakın.
