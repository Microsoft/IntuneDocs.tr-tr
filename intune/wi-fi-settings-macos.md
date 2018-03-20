---
title: "macOS çalıştıran cihazlar için Microsoft Intune Wi-Fi ayarları"
titleSuffix: 
description: "macOS çalıştıran cihazlarda Wi-Fi bağlantılarını yapılandırmak için kullanabileceğiniz Intune ayarlarını öğrenin."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 25cc8cd550567d6edc63f1cab416bdb7d978eb52
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2018
---
# <a name="wi-fi-settings-for-macos-devices-in-microsoft-intune"></a>Microsoft Intune’da macOS cihazları için Wi-Fi ayarları

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Bu makalede, macOS çalıştıran cihazlar için Microsoft Intune’da yapılandırabileceğiniz Wi-Fi ayarları gösterilir.

## <a name="wi-fi-settings-for-basic-and-enterprise-profiles"></a>Temel ve kurumsal profiller için Wi-Fi ayarları

- **Ağ adı** - Bu Wi-Fi bağlantısı için bir ad girin. Bu, kullanıcıların cihazlarında kullanılabilir bağlantılar listesine göz attıklarında gördükleri addır.
- **SSID** - Hizmet kümesi tanımlayıcısının kısaltması. Bu, cihazların bağlandığı kablosuz ağın gerçek adıdır. Bununla birlikte, bağlantıyı seçen kullanıcılar yalnızca yapılandırdığınız ağ adını görür.
- **Otomatik olarak bağlan** - Cihazın ağ kapsamında olduğu her yerde bağlanmasını sağlar.
- **Gizli ağ** - Bu ağın, cihazdaki kullanılabilir ağlar listesinde gösterilmesini önler.
- **Proxy ayarları** - Aşağıdakilerden birini seçin:
    - **Hiçbiri** - Hiçbir proxy ayarı yapılandırılmaz.
    - **El ile** - **Proxy sunucu adresini** (bir IP adresi olarak) ve onunla ilişkilendirilmiş **Bağlantı noktası numarasını** girin.
    - **Otomatik** - Proxy sunucusunu yapılandırmak için bir dosya kullanın. Yapılandırma dosyasını içeren **Proxy sunucu URL’si** (örneğin **http://proxy.contoso.com) değerini girin.

## <a name="wi-fi-settings-for-basic-profiles-only"></a>Yalnızca temel profiller için Wi-Fi ayarları

- **Güvenlik türü** - Wi-Fi ağında kimliği doğrulamak için kullanılacak güvenlik protokolü olarak aşağıdakilerden birini seçin:
    - **Açık (kimlik doğrulamasız)** - Bu seçeneği yalnızca ağ güvenlik altına alınmamış olduğunda kullanın.
    - **WPA/WPA2 - Kişisel**
    - **4**

## <a name="wi-fi-settings-for-enterprise-profiles-only"></a>Yalnızca kurumsal profiller için Wi-Fi ayarları

- **EAP türü** - Güvenli kablosuz bağlantıların kimliğini doğrulamak için kullanılan Genişletilebilir Kimlik Doğrulama Protokolü (EAP) türünü seçin:
    - **EAP-FAST**
    - **EAP-SIM**
    - **EAP-TLS**
    - **EAP-TTLS**
    - **LEAP**
    - **PEAP**

### <a name="further-options-when-you-choose-an-eap-type"></a>EAP türü seçtiğinizde diğer seçenekler


|Ayar adı|Daha fazla bilgi|Şu durumlarda kullanın|
|--------------|-------------|----------|
|**Korumalı Erişim Kimlik Bilgisi (PAC) Ayarları**|İstemci ile kimlik doğrulama sunucusu arasında kimliği doğrulanmış bir tünel oluşturmak için korumalı erişim kimlik bilgilerini kullanmayı seçin. Aşağıdakilerden birini seçin:<br>- **PAC kullan** - Varsa, mevcut PAC dosyasını kullanın.<br>- **PAC’yi Kullan ve Sağla** - Cihazlarınıza PAC dosyası sağlayın.<br>- **Anonim Olarak PAC Sağla** - Cihazlarınıza PAC dosyasını sağlayın ve PAC dosyasının, sunucunun kimliği doğrulanmadan sağlandığından emin olun.|EAP türü **EAP-FAST**’dir.|

#### <a name="server-trust"></a>Sunucu Güveni


|Ayar adı|Daha fazla bilgi|Şu durumlarda kullanın|
|--------------|-------------|----------|
|**Sertifika sunucu adları**|Güvenilen sertifika yetkiliniz (CA) tarafından verilen sertifikalarda yaygın olarak kullanılan bir veya birden çok ad belirtin. Bu bilgiyi sağlarsanız, bu Wi-Fi ağına bağlanırken kullanıcıların cihazlarında görüntülenen dinamik güven iletişim kutusunu atlayabilirsiniz.|EAP türü **EAP-TLS**, **EAP-TTLS** veya **PEAP**’dir.|
|**Sunucu doğrulaması için kök sertifikası**|Bağlantı kimliğini doğrulamak için kullanılan, güvenilen kök sertifika profilini seçin. |EAP türü **EAP-TLS**, **EAP-TTLS** veya **PEAP**’dir.|
|**Kimlik gizliliği (dış kimlik)**|Bir EAP kimlik isteğine yanıt olarak gönderilen metni belirtin. Bu metin herhangi bir değer olabilir. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.|EAP türü **PEAP**’dir.|


#### <a name="client-authentication"></a>İstemci Kimlik Doğrulaması


|Ayar adı|Daha fazla bilgi|Şu durumlarda kullanın|
|--------------|-------------|----------|
|**İstemci kimlik doğrulaması için istemci sertifikası (Kimlik sertifikası)**|Bağlantı kimliğini doğrulamak için kullanılan SCEP veya PKCS sertifika profilini seçin.|EAP türü **EAP-TLS**’dir.|
|**Kimlik doğrulama yöntemi**|Bağlantı için kimlik doğrulama yöntemini seçin:<br>Sunucuya gösterilen kimlik sertifikası olan SCEP veya PKCS istemci sertifikasını seçmek için - **Sertifikalar**.<br><br>Farklı bir kimlik doğrulama yöntemi belirtmek için - **Kullanıcı Adı ve Parola**. <br><br>**Kullanıcı Adı ve Parola**’yı seçerseniz, şunları yapılandırın:<br><br>-  **EAP dışı yöntem (iç kimlik)**. Sonra da bağlantının kimliğini nasıl doğrulayacağınızı belirtmek için aşağıdakilerden birini seçin:<br>- **Yok**<br>- **Şifrelenmemiş parola (PAP)**<br>- **Karşılıklı Kimlik Doğrulama Protokolü (CHAP)**<br>- **Microsoft CHAP (MS-CHAP)**<br>- **Microsoft CHAP Sürüm 2 (MS-CHAP v2)**<br>Mevcut seçenekler, seçtiğiniz EAP türüne bağlıdır.<br><br>**ve**<br><br>- **Kimlik gizliliği (dış kimlik)** - EAP kimlik isteğine yanıt olarak gönderilen metni belirtin. Bu metin herhangi bir değer olabilir. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.|EAP türü **EAP-TTLS** veya **PEAP**’dir.|
