---
title: "iOS cihazları için Intune Wi-Fi ayarları"
titleSuffix: Azure portal
description: "iOS cihazlarında Wi-Fi bağlantılarını yapılandırmak için kullanabileceğiniz Intune ayarlarını öğrenin.\""
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 12/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 89229a5e-3421-4221-a62f-fa800620cc0d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6a4a5b9b76995be6a82cc3dcaa9f782c158ba174
ms.sourcegitcommit: b982f9d50da4f958fb0c48c56ba46c8ef71500c4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2018
---
# <a name="wi-fi-settings-for-ios-devices-in-microsoft-intune"></a>Microsoft Intune’da iOS cihazları için Wi-Fi ayarları

[!INCLUDE[azure_portal](./includes/azure_portal.md)]



## <a name="wi-fi-settings-for-basic-and-enterprise-profiles"></a>Temel ve kurumsal profiller için Wi-Fi ayarları

- **Ağ adı** - Bu Wi-Fi bağlantısı için bir ad girin. Bu, kullanıcıların cihazlarında kullanılabilir bağlantılar listesine göz attıklarında görecekleri addır.
- **SSID** - Hizmet kümesi tanımlayıcısının kısaltması. Bu, cihazların bağlanacağı kablosuz ağın gerçek adıdır. Bununla birlikte, bağlantıyı seçen kullanıcılar yalnızca yukarıda oluşturduğunuz ağ adını görür.
- **Otomatik olarak bağlan** - Cihazın ağ kapsamında olduğu her yerde bağlanmasını sağlar.
- **Gizli ağ** - Bu ağın, cihazdaki kullanılabilir ağlar listesinde gösterilmesini önler.
- **Önceden paylaşılan anahtar** - 
- **Proxy ayarları** - Aşağıdakilerden birini seçin:
    - **Hiçbiri** - Hiçbir proxy ayarı yapılandırılmaz.
    - **El ile** - **Proxy sunucu adresini** (bir IP adresi olarak) ve onunla ilişkilendirilmiş **Bağlantı noktası numarasını** girin.
    - **Otomatik** - Proxy sunucusunu yapılandırmak için bir dosya kullanın. Yapılandırma dosyasını içeren **Proxy sunucu URL’si** (örneğin **http://proxy.contoso.com**) değerini girin.

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
|**Sertifika sunucu adları**|Güvenilen sertifika yetkiliniz (CA) tarafından verilen sertifikalarda yaygın olarak kullanılan bir veya birden çok ad belirtin. Bu bilgiyi sağlarsanız, bu Wi-Fi ağına bağlanırken son kullanıcıların cihazlarında görüntülenen dinamik güven iletişim kutusunu atlayabilirsiniz.|EAP türü **EAP-TLS**, **EAP-TTLS** veya **PEAP**’dir.|
|**Sunucu doğrulaması için kök sertifikası**|Bağlantı kimliğini doğrulamak için kullanılan, güvenilen kök sertifika profilini seçin. |EAP türü **EAP-TLS**, **EAP-TTLS** veya **PEAP**’dir.|
|**Kimlik gizliliği (dış kimlik)**|Bir EAP kimlik isteğine yanıt olarak gönderilen metni belirtin. Bu metin herhangi bir değer olabilir. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.|EAP türü **PEAP**’dir.|


#### <a name="client-authentication"></a>İstemci Kimlik Doğrulaması


|Ayar adı|Daha fazla bilgi|Şu durumlarda kullanın|
|--------------|-------------|----------|
|**İstemci kimlik doğrulaması için istemci sertifikası (Kimlik sertifikası)**|Bağlantı kimliğini doğrulamak için kullanılan SCEP veya PKCS sertifika profilini seçin.|EAP türü **EAP-TLS**’dir.|
|**Kimlik doğrulama yöntemi**|Bağlantı için kimlik doğrulama yöntemini seçin:<br>Sunucuya gösterilen kimlik sertifikası olan SCEP veya PKCS istemci sertifikasını seçmek için - **Sertifikalar**.<br><br>Farklı bir kimlik doğrulama yöntemi belirtmek için - **Kullanıcı Adı ve Parola**. <br><br>**Kullanıcı Adı ve Parola**’yı seçerseniz, şunları yapılandırın:<br><br>-  **EAP dışı yöntem (iç kimlik)**. Sonra da bağlantının kimliğini nasıl doğrulayacağınızı belirtmek için aşağıdakilerden birini seçin:<br>- **Yok**<br>- **Şifrelenmemiş parola (PAP)**<br>- **Karşılıklı Kimlik Doğrulama Protokolü (CHAP)**<br>- **Microsoft CHAP (MS-CHAP)**<br>- **Microsoft CHAP Sürüm 2 (MS-CHAP v2)**<br>Mevcut seçenekler, seçtiğiniz EAP türüne bağlıdır.<br><br>**ve**<br><br>- **Kimlik gizliliği (dış kimlik)** - EAP kimlik isteğine yanıt olarak gönderilen metni belirtin. Bu metin herhangi bir değer olabilir. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.|EAP türü **EAP-TTLS** veya * olur.
