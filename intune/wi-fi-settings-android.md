---
title: Android çalıştıran cihazlar için Microsoft Intune Wi-Fi ayarlarını yapılandırma
titleSuffix: ''
description: Android çalıştıran cihazlarda Intune Wi-Fi yapılandırma ayarlarını öğrenin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 7/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0157815322488525a4ce7a3d6d2c90cbb8d3ff2a
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/07/2018
ms.locfileid: "37905675"
---
# <a name="configure-wi-fi-settings-in-microsoft-intune-for-devices-running-android-android-work-profiles-and-android-kiosk-devices"></a>Android, Android iş profili ve Android bilgi noktası çalıştıran cihazlar için Microsoft Intune’da Wi-Fi ayarlarını yapılandırma

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bu makale, Android ve Android iş profili çalıştıran cihazlar için Microsoft Intune’da yapılandırabileceğiniz Wi-Fi ayarlarını gösterir.

## <a name="wi-fi-settings-for-basic-and-enterprise-profiles"></a>Temel ve kurumsal profiller için Wi-Fi ayarları

Aşağıdaki Wi-Fi ayarları hem Android hem de Android iş profili cihazları için kullanılabilir:

- **Ağ adı** - Bu Wi-Fi bağlantısı için bir ad girin. Bu, kullanıcıların cihazlarında kullanılabilir bağlantılar listesine göz attıklarında görecekleri addır.
- **SSID** - Hizmet kümesi tanımlayıcısının kısaltması. Bu, cihazların bağlandığı kablosuz ağın gerçek adıdır. Bununla birlikte, bağlantıyı seçen kullanıcılar yalnızca yapılandırdığınız ağ adını görür.
- **Otomatik olarak bağlan** - Cihazın ağ kapsamında olduğu her yerde bağlanmasını sağlar.
- **Gizli ağ** - Bu ağın, cihazdaki kullanılabilir ağlar listesinde gösterilmesini önler.

## <a name="wi-fi-settings-available-for-enterprise-kiosk-profiles"></a>Kurumsal bilgi noktası profilleri için kullanılabilen Wi-Fi ayarları
- **Wi-Fi türü**: Bu Wi-Fi türü ayarları yalnızca **Profil türü** > **Yalnızca Cihaz Sahibi** > **Wi-Fi**’ı seçerseniz kullanılabilir.
    - **Açık (kimlik doğrulaması yok)**
    - **WEP-Önceden paylaşılan anahtar**: Parolayı **Önceden paylaşılan anahtar** kutusunda sağlamanız gerekir.
    - **WPA-Önceden paylaşılan anahtar**: Parolayı **Önceden paylaşılan anahtar** kutusunda sağlamanız gerekir

## <a name="wi-fi-settings-for-android-legacy-and-android-work-profiles-only"></a>Yalnızca eski Android cihazlar ve Android iş profilleri için Wi-Fi ayarları

- **EAP türü** - Güvenli kablosuz bağlantıların kimliğini doğrulamak için kullanılan Genişletilebilir Kimlik Doğrulama Protokolü (EAP) türünü seçin:
    - **EAP-TLS**
    - **EAP-TTLS**
    - **PEAP**

### <a name="further-options-when-you-choose-an-eap-type"></a>EAP türü seçtiğinizde diğer seçenekler

#### <a name="server-trust"></a>Sunucu Güveni



|Ayar adı|Daha fazla bilgi|Şu durumlarda kullanın|
|-------------|---------------|-----------|
|**Sertifika sunucu adları**|Güvenilen sertifika yetkiliniz (CA) tarafından verilen sertifikalarda yaygın olarak kullanılan bir veya birden çok ad belirtin. Bu bilgiyi sağlarsanız, bu Wi-Fi ağına bağlanırken kullanıcının cihazında görüntülenen dinamik güven iletişim kutusunu atlayabilirsiniz.|EAP türü **EAP-TLS** veya **EAP-TTLS**’dir.|
|**Sunucu doğrulaması için kök sertifika**|Bağlantı kimliğini doğrulamak için kullanılan, güvenilen kök sertifika profilini seçin. |EAP türü **EAP-TLS**, **EAP-TTLS** veya **PEAP**’dir.|
|**Kimlik gizliliği (dış kimlik)**|Bir EAP kimlik isteğine yanıt olarak gönderilen metni belirtin. Bu metin herhangi bir değer olabilir. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.|EAP türü **PEAP**’dir.|


#### <a name="client-authentication"></a>İstemci Kimlik Doğrulaması


|                                     Ayar adı                                     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       Daha fazla bilgi                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |                            Şu durumlarda kullanın                            |
|--------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------|
| <strong>İstemci kimlik doğrulaması için istemci sertifikası (Kimlik sertifikası)</strong> |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       Bağlantı kimliğini doğrulamak için kullanılan SCEP veya PKCS sertifika profilini seçin.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |              EAP türü <strong>EAP-TLS</strong>’dir.              |
|                        <strong>Kimlik doğrulama yöntemi</strong>                        | Bağlantı için kimlik doğrulama yöntemini seçin:<br>Sunucuya gösterilen kimlik sertifikası olan SCEP veya PKCS istemci sertifikasını seçmek için - <strong>Sertifikalar</strong>.<br><br>Farklı bir kimlik doğrulama yöntemi belirtmek için - <strong>Kullanıcı Adı ve Parola</strong>. <br><br><strong>Kullanıcı Adı ve Parola</strong>’yı seçerseniz, şunları yapılandırın:<br><br>-  <strong>EAP dışı yöntem (iç kimlik)</strong>, sonra da bağlantının kimliğini nasıl doğrulayacağınızı belirtmek için aşağıdakilerden birini seçin:<br>- <strong>Yok</strong><br>- <strong>Şifrelenmemiş parola (PAP)</strong><br>- <strong>Karşılıklı Kimlik Doğrulama Protokolü (CHAP)</strong><br>- <strong>Microsoft CHAP (MS-CHAP)</strong><br>- <strong>Microsoft CHAP Sürüm 2 (MS-CHAP v2)</strong><br>Mevcut seçenekler, seçtiğiniz EAP türüne bağlıdır.<br><br><strong>ve</strong><br><br>- <strong>Kimlik gizliliği (dış kimlik)</strong> - EAP kimlik isteğine yanıt olarak gönderilen metni belirtin. Bu metin herhangi bir değer olabilir. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir. | EAP türü <strong>EAP-TTLS</strong> veya <strong>PEAP</strong>’dir. |

