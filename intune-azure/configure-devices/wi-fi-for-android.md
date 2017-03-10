---
title: "Android cihazları için Intune Wi-Fi ayarları"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Android cihazlarda Wi-Fi bağlantılarını yapılandırmak için kullanabileceğiniz Intune ayarlarını öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 103e17a4-2993-4359-b340-73e2acf4cf7d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: b274dd2b6e7e6c2c0bd8b6315b5924b72611ab40
ms.lasthandoff: 02/18/2017


---

# <a name="wi-fi-settings-for-android-devices-in-microsoft-intune"></a>Microsoft Intune’da Android cihazları için Wi-Fi ayarları

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="wi-fi-settings-for-basic-and-enterprise-profiles"></a>Temel ve kurumsal profiller için Wi-Fi ayarları

- **Ağ adı** - Bu Wi-Fi bağlantısı için bir ad girin. Bu, kullanıcıların cihazlarında kullanılabilir bağlantılar listesine göz attıklarında görecekleri addır.
- **SSID** - Hizmet kümesi tanımlayıcısının kısaltması. Bu, cihazların bağlanacağı kablosuz ağın gerçek adıdır. Bununla birlikte, bağlantıyı seçen kullanıcılar yalnızca yukarıda oluşturduğunuz ağ adını görür.
- **Otomatik olarak bağlan** - Cihazın ağ kapsamında olduğu her yerde bağlanmasını sağlar.
- **Gizli ağ** - Bu ağın, cihazdaki kullanılabilir ağlar listesinde gösterilmesini önler.


## <a name="wi-fi-settings-for-enterprise-profiles-only"></a>Yalnızca kurumsal profiller için Wi-Fi ayarları

- **EAP türü** - Güvenli kablosuz bağlantıların kimliğini doğrulamak için kullanılan Genişletilebilir Kimlik Doğrulama Protokolü (EAP) türünü seçin:
    - **EAP-TLS**
    - **EAP-TTLS**
    - **PEAP**

### <a name="further-options-when-you-choose-an-eap-type"></a>EAP türü seçtiğinizde diğer seçenekler

#### <a name="server-trust"></a>Sunucu Güveni



|Ayar adı|Daha fazla bilgi|Şu durumlarda kullanın|
|-------------|---------------|-----------|
|**Sertifika sunucu adları**|Güvenilen sertifika yetkiliniz (CA) tarafından verilen sertifikalarda yaygın olarak kullanılan bir veya birden çok ad belirtin. Bu bilgiyi sağlarsanız, bu Wi-Fi ağına bağlanırken son kullanıcıların cihazlarında görüntülenen dinamik güven iletişim kutusunu atlayabilirsiniz.|EAP türü **EAP-TLS** veya **EAP-TTLS**’dir.|
|**Sunucu doğrulaması için kök sertifika**|Bağlantı kimliğini doğrulamak için kullanılan, güvenilen kök sertifika profilini seçin. |EAP türü **EAP-TLS**, **EAP-TTLS** veya **PEAP**’dir.|
|**Kimlik gizliliği (dış kimlik)**|Bir EAP kimlik isteğine yanıt olarak gönderilen metni belirtin. Bu metin herhangi bir değer olabilir. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.|EAP türü **PEAP**’dir.|


#### <a name="client-authentication"></a>İstemci Kimlik Doğrulaması


|Ayar adı|Daha fazla bilgi|Şu durumlarda kullanın|
|----------|--------------|----------|
|**İstemci kimlik doğrulaması için istemci sertifikası (Kimlik sertifikası)**|Bağlantı kimliğini doğrulamak için kullanılan SCEP veya PKCS sertifika profilini seçin.|EAP türü **EAP-TLS**’dir.|
|**Kimlik doğrulama yöntemi**|Bağlantı için kimlik doğrulama yöntemini seçin:<br>Sunucuya gösterilen kimlik sertifikası olan SCEP veya PKCS istemci sertifikasını seçmek için - **Sertifikalar**.<br><br>Farklı bir kimlik doğrulama yöntemi belirtmek için - **Kullanıcı Adı ve Parola**. <br><br>**Kullanıcı Adı ve Parola**’yı seçerseniz, şunları yapılandırın:<br><br>-  **EAP dışı yöntem (iç kimlik)**. Sonra da bağlantının kimliğini nasıl doğrulayacağınızı belirtmek için aşağıdakilerden birini seçin:<br>- **Yok**<br>- **Şifrelenmemiş parola (PAP)**<br>- **Karşılıklı Kimlik Doğrulama Protokolü (CHAP)**<br>- **Microsoft CHAP (MS-CHAP)**<br>- **Microsoft CHAP Sürüm 2 (MS-CHAP v2)**<br>Mevcut seçenekler, seçtiğiniz EAP türüne bağlıdır.<br><br>**ve**<br><br>- **Kimlik gizliliği (dış kimlik)** - EAP kimlik isteğine yanıt olarak gönderilen metni belirtin. Bu metin herhangi bir değer olabilir. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.|EAP türü **EAP-TTLS** veya **PEAP**’dir.|

