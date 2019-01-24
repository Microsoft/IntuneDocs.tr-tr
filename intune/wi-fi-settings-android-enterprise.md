---
title: Android Enterprise ve bilgi noktası cihazları - Intune için Wi-Fi ayarları | Microsoft Docs
description: Android Kurumsal ve Android Bilgi Noktası için bir Wi-Fi cihaz yapılandırma profili oluşturun veya ekleyin. Microsoft Intune’da sertifika ekleme, EAP türü seçme ve bir kimlik doğrulama yöntemi seçme gibi farklı ayarları inceleyin. Bilgi noktası cihazlarında ağınızın Önceden paylaşılan anahtarını da girin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/16/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: ea72cda4cb72af9028c52078e2215619bb2bef3c
ms.sourcegitcommit: e08a26558174be3ea8f3d20646e577f1493ea21a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54831488"
---
# <a name="add-wi-fi-settings-for-devices-running-android-enterprise-and-android-kiosk-in-microsoft-intune"></a>Microsoft Intune’da Android Kurumsal ve Android Bilgi Noktası çalıştıran cihazlar için Wi-Fi ayarları ekleme

Belirli Wi-Fi ayarları ile bir profil oluşturabilir ve ardından bu profili Android Kurumsal ve Android bilgi noktası cihazlarınıza dağıtabilirsiniz. Microsoft Intune; ağınızda kimlik doğrulama, bir önceden paylaşılan anahtar kullanma ve daha fazlası gibi pek çok özellik sunar.

Bu makalede bu ayarlar açıklanır. [Wi-Fi cihazlarınızda kullanın](wi-fi-settings-configure.md) Intune Wi-Fi özelliği hakkında daha fazla bilgi içerir.

## <a name="before-you-begin"></a>Başlamadan önce

[Cihaz profili oluşturma](wi-fi-settings-configure.md#create-a-device-profile).

## <a name="device-owner-only---kiosk"></a>Yalnızca cihaz sahibi - bilgi noktası

Bir Android Kurumsal cihazı bilgi noktası olarak kullanıyorsanız bu seçeneği belirleyin.

- **Ağ adı**: Bu Wi-Fi bağlantısı için bir ad girin. Bu değer, kullanıcıların cihazlarında kullanılabilir bağlantılar listesine göz attıklarında görecekleri addır.
- **SSID**: Kısaltması **hizmet kümesi tanımlayıcısı**. Bu ayar, cihazların bağlandığı kablosuz ağın gerçek adıdır. Ancak bağlantıyı seçen kullanıcılar yalnızca yapılandırdığınız **ağ adını** görür.
- **Otomatik olarak bağlan**: Seçin **etkinleştirme** cihaz menzil içindeyken otomatik olarak bu ağa bağlanmak için. Cihazların otomatik olarak bağlanmasını önlemek için **Devre dışı bırak**’ı seçin.
- **Gizli ağ**: Seçin **etkinleştirme** bu ağın, cihazdaki kullanılabilir ağlar listesinde gizlemek için. SSID yayınlanmaz. Cihazdaki kullanılabilir ağlar listesinde bu ağı göstermek için **Devre dışı bırak**’ı seçin.
- **Wi-Fi türü**: Wi-Fi ağına kimlik doğrulaması için güvenlik protokolü seçin. Seçenekleriniz şunlardır:

  - **Açık (kimlik doğrulamasız)**: Ağ güvenli değilse, yalnızca bu seçeneği kullanın.
  - **WEP önceden paylaşılan anahtar**: Parolayı girin **önceden paylaşılan anahtar**. Kuruluşunuzun ağı ayarlandığında veya yapılandırıldığında bir parola veya ağ anahtarı da yapılandırılır. PSK değeri için bu parolayı veya ağ anahtarını girin.
  - **WPA önceden paylaşılan anahtar**: Parolayı girin **önceden paylaşılan anahtar**. Kuruluşunuzun ağı ayarlandığında veya yapılandırıldığında bir parola veya ağ anahtarı da yapılandırılır. PSK değeri için bu parolayı veya ağ anahtarını girin.

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="work-profile-only"></a>Yalnızca iş profili

### <a name="basic-settings"></a>Temel ayarlar

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

    - **Sunucu güveni** - **sunucu doğrulaması için kök sertifika**: Var olan bir güvenilen kök sertifika profilini seçin. İstemci ağa bağlandığında, bu sertifika sunucuya sunulur ve bağlantının kimliğini doğrular.

      Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

    - **İstemci kimlik doğrulaması** - **istemci kimlik doğrulaması (kimlik sertifikası) için istemci sertifikası**: SCEP veya PKCS istemci cihaza da dağıtılmış olan sertifika profilini seçin. Bu sertifika, bağlantının kimliğini doğrulamak için cihaz tarafından sunucuya sunulan kimliktir.

      Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

  - **EAP-TTLS**: Şunları da girin:

    - **Sunucu güveni** - **sunucu doğrulaması için kök sertifika**: Var olan bir güvenilen kök sertifika profilini seçin. İstemci ağa bağlandığında, bu sertifika sunucuya sunulur ve bağlantının kimliğini doğrular.

      Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

    - **İstemci Kimlik Doğrulaması** - Bir **Kimlik doğrulama yöntemi** seçin. Seçenekleriniz şunlardır:

      - **Kullanıcı adı ve parola**: Bağlantı kimliğini doğrulamak için bir kullanıcı adı ve parola girmesini. Şunları da girin:
        - **EAP dışı yöntem (iç kimlik)**: Bağlantı kimliğini nasıl seçin. Wi-Fi ağınızda yapılandırılmış olan protokolü seçtiğinizden emin olun.

          Seçenekleriniz şunlardır: **Şifrelenmemiş parola (PAP)**, **karşılıklı kimlik doğrulama protokolü (CHAP)**, **Microsoft CHAP (MS-CHAP)**, veya **Microsoft CHAP Version 2 (MS-CHAP v2)**

      - **Sertifikaları**: SCEP veya PKCS istemci cihaza da dağıtılmış olan sertifika profilini seçin. Bu sertifika, bağlantının kimliğini doğrulamak için cihaz tarafından sunucuya sunulan kimliktir.

        Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

      - **Kimlik gizliliği (Dış kimlik)**: Bir EAP kimlik isteğine yanıt olarak gönderilen metni girin. Bu metin herhangi bir değer olabilir, örneğin `anonymous`. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.

  - **PEAP**: Şunları da girin:

    - **Sunucu güveni** - **sunucu doğrulaması için kök sertifika**: Var olan bir güvenilen kök sertifika profilini seçin. İstemci ağa bağlandığında, bu sertifika sunucuya sunulur ve bağlantının kimliğini doğrular.

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

Profil oluşturuldu ancak hiçbir şey yapmıyor. Ardından, [bu profili atarsınız](device-profile-assign.md) ve [atamanın durumunu izlemenize.](device-profile-monitor.md).

Wi-Fi profilleri için de oluşturabilirsiniz [Android](wi-fi-settings-android.md), [iOS](wi-fi-settings-ios.md), [macOS](wi-fi-settings-macos.md), [Windows 10](wi-fi-settings-windows.md), ve [Windows 8.1](wi-fi-settings-import-windows-8-1.md)cihazlar.