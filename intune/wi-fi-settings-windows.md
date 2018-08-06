---
title: Microsoft Intune - Azure’da Windows 10 cihazlar için Wi-Fi ayarları | Microsoft Docs
description: Microsoft Intune'da Windows 10 ve üzeri cihazlar için Wi-Fi ayarlarını kullanarak Wi-Fi yapılandırma profilini ekleme veya oluşturma. Temel ayarları veya kurumsal düzey ayarları yapılandırabilirsiniz.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 07/25/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8f6532c63612b806f9824f5b9ca98f1ebbbc943f
ms.sourcegitcommit: e8e8164586508f94704a09c2e27950fe6ff184c3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2018
ms.locfileid: "39321847"
---
## <a name="wi-fi-settings-for-windows-10-and-later-devices-in-intune"></a>Intune’da Windows 10 ve üzeri cihazlar için Wi-Fi ayarları

Wi-Fi ayarları, Windows 10 ve üzerini çalıştıran cihazlara uygulanan yapılandırma profilinde kullanılır. Seçenekleriniz şunlardır:

- Temel
- Kurumsal

## <a name="before-you-begin"></a>Başlamadan önce

[Cihaz profili oluşturma](device-profile-create.md).

## <a name="settings-for-basic-and-enterprise-profiles"></a>Temel ve kurumsal profiller için ayarlar

- **Wi-Fi adı (SSID)**: Hizmet kümesi tanımlayıcısının kısaltması. Bu değer, cihazların bağlandığı kablosuz ağın gerçek adıdır. Bununla birlikte, bağlantıyı seçen kullanıcılar yalnızca yapılandırdığınız **Bağlantı adını** görür.
- **Bağlantı adı**: Bu Wi-Fi bağlantısı için bir kolay ad girin. Girdiğiniz metin, kullanıcıların cihazlarında kullanılabilir bağlantılara göz attıklarında görecekleri addır.
- **Aralığa girdiğinde otomatik bağlan**: **Evet** olduğunda, bu ağın aralığına giren cihazlar otomatik olarak bağlanır. **Hayır** olduğunda, cihazlar otomatik olarak bağlanmaz.
  - **Mevcutsa daha fazla tercih edilen ağa bağlan**: Cihazlar tercih edilen birden çok ağın aralığında yer alıyorsa, tercih edilen ağı kullanmak için **Evet**'i seçin. Bu yapılandırma profilindeki Wi-Fi ağını kullanmak için **Hayır**'ı seçin.

    Örneğin, **ContosoCorp** Wi-Fi ağını oluşturduğunuzu ve bu yapılandırma profili içinde **ContosoCorp**'u kullandığınızı varsayalım. Ayrıca, aralık içinde bir de **ContosoGuest** Wi-Fi ağınız olsun. Şirket cihazlarınız aralık içinde olduğunda, bunların otomatik olarak **ContosoCorp**'a bağlanmasını istiyorsunuz. Bu senaryoda, **Mevcutsa daha fazla tercih edilen ağa bağlan** özelliğini **Hayır** olarak ayarlayın.

  - **SSID'sini yayınlamıyor olsa bile bu ağa bağlanın**: Ağınız gizli (SSID'si herkese açık şekilde yayınlanmıyor) olduğunda bile, ağınıza otomatik olarak bağlanmak üzere yapılandırma profili için **Evet**'i seçin. Bu yapılandırma profilinin gizli ağınıza bağlanmasını istemiyorsanız **Hayır**'ı seçin.

- **Şirket ara sunucu ayarları**: Kuruluşunuz içinde ara sunucu ayarlarını kullanmak için seçin. Seçenekleriniz şunlardır:
  - **Hiçbiri**: Hiçbir ara sunucu ayarı yapılandırılmaz.
  - **El ile yapılandır**: **Ara sunucu IP adresini** ve onun **Bağlantı noktası numarasını** girin.
  - **Otomatik olarak yapılandır**: Ara sunucu otomatik yapılandırma (PAC) betiğine işaret eden URL'yi girin. Örneğin, şunu girin: `http://proxy.contoso.com/proxy.pac`.

## <a name="settings-for-basic-profiles-only"></a>Yalnızca temel profiller için ayarlar

- **Kablosuz Güvenlik Türü**: Ağınızda cihazların kimliğini doğrulamak için kullanılan güvenlik protokolünü girin. Seçenekleriniz şunlardır:
  - **Açık (kimlik doğrulamasız)**: Bu seçeneği yalnızca ağ güvenlik altına alınmamış olduğunda kullanın.
  - **WPA/WPA2-Kişisel**

## <a name="settings-for-enterprise-profiles-only"></a>Yalnızca kurumsal profiller için ayarlar

- **Çoklu oturum açma (SSO)**: Kimlik bilgilerinin bilgisayar ve Wi-Fi ağı oturum açma işleminde paylaşıldığı çoklu oturum açmayı (SSO) yapılandırmanıza olanak tanır. Seçenekleriniz şunlardır:
  - **Devre dışı bırak**: SSO davranışını devre dışı bırakır. Kullanıcının ağda ayrıca kimlik doğrulaması yapması gerekir.
  - **Kullanıcı cihazda oturum açmadan önce etkinleştir**: Kullanıcı oturum açma işleminden hemen önce ağda kimlik doğrulaması yapmak için SSO kullanın.
  - **Kullanıcı cihazda oturum açmadan sonra etkinleştir**: Kullanıcı oturum açma işlemini tamamlandıktan hemen sonra ağda kimlik doğrulaması yapmak için SSO kullanın.
  - **Zaman aşımından önce kimlik doğrulanması gereken en uzun süre**: Ağda kimlik doğrulaması yapmadan önce beklenecek saniye sayısı üst sınırını (1-120 saniye arası) girin.
  - **Windows'un kullanıcıdan ek kimlik doğrulama kimlik bilgileri istemesine izin ver**: **Evet** seçildiğinde, kimlik doğrulama yöntemi gerektiriyorsa Windows sisteminin kullanıcıdan ek kimlik bilgileri istemesine izin verilir. Bu istemleri gizlemek için **Hayır**'ı seçin.

- **İkili ana anahtar önbelleğe almayı etkinleştir**: Kimlik doğrulamasında kullanılan PMK'yi önbelleğe almak için **Evet**'i seçin. Bu önbellek normalde ağda kimlik doğrulamasının daha hızlı tamamlanmasını sağlar. Wi-Fi ağına her bağlantıda karşılıklı kimlik doğrulamayı zorlamak için **Hayır**'ı seçin.

  - **Bir PMK'nin önbellekte depolanacağı en uzun süre**: İkili ana anahtarın (PMK) önbellekte depolanacağı dakika sayısını (5-1440 dakika arası) girin.
  - **Önbellekte depolanacak en fazla PMK sayısı**: Önbellekte depolanacak anahtar sayısını (1-255 arası) girin.

- **Ön kimlik doğrulamasını etkinleştir**: Ön kimlik doğrulaması profilin bağlantı öncesinde profildeki ağ için tüm erişim noktalarında kimlik doğrulaması yapmasını sağlar. Erişim noktaları arasında hareket ederken, ön kimlik doğrulaması kullanıcının veya cihazların daha hızlı yeniden bağlanmasını sağlar. Profilin aralık içinde yer alan bu ağın tüm erişim noktalarında kimlik doğrulaması yapması için **Evet**'i seçin. Kullanıcı veya cihazın her erişim noktasında ayrıca kimlik doğrulaması yapmasını gerektirmek için **Hayır**'ı seçin.

  - **En yüksek ön kimlik doğrulaması denemesi**: Ön kimlik doğrulaması için yapılacak deneme sayısını (1-16 arası) girin.

- **EAP türü**: Güvenli kablosuz bağlantıların kimliğini doğrulamak için kullanılacak Genişletilebilir Kimlik Doğrulama Protokolü (EAP) türünü seçin. Seçenekleriniz şunlardır:

  - **EAP-SIM**
  - **EAP-TLS**
  - **EAP-TTLS**
  - **Korumalı PEAP** (PEAP)

### <a name="more-options-when-you-choose-the-eap-type"></a>EAP türünü seçtiğinizde diğer seçenekler

> [!NOTE]
> Şu anda, EAP türünü kullanırken yalnızca SCEP sertifika profilleri destekleniyor. PKCS sertifika profilleri desteklenmiyor. Kullanıcıdan her sertifika girişi istendiğinde, bir SCEP sertifikası seçtiğinizden emin olun.

#### <a name="server-trust"></a>Sunucu Güveni

|Ayar adı|Daha fazla bilgi|Şu durumlarda kullanın|
|--------------|-------------|----------|
|**Sertifika sunucu adları**|Güvenilen sertifika yetkiliniz (CA) tarafından verilen sertifikalarda yaygın olarak kullanılan bir veya birden çok ad girin. Bu bilgiyi girerseniz, bu Wi-Fi ağına bağlanırken kullanıcının cihazında görüntülenen dinamik güven iletişim kutusunu atlayabilirsiniz.|EAP türü **EAP-TLS**, **EAP-TTLS** veya **PEAP**’dir.|
|**Sunucu doğrulaması için kök sertifika**|Bağlantı kimliğini doğrulamak için kullanılan, güvenilen kök sertifika profilini seçin. |EAP türü **EAP-TLS**, **EAP-TTLS** veya **PEAP**’dir.|
|**Kimlik gizliliği (dış kimlik)**|Bir EAP kimlik isteğine yanıt olarak gönderilen metni girin. Bu metin herhangi bir değer olabilir. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.|EAP türü **PEAP**’dir.|

#### <a name="client-authentication"></a>İstemci Kimlik Doğrulaması

| Ayar adı | Daha fazla bilgi | Şu durumlarda kullanın |
|---|---|---|
| **İstemci kimlik doğrulaması için istemci sertifikası (Kimlik sertifikası)** |  Bağlantı kimliğini doğrulamak için kullanılan SCEP sertifika profilini seçin. | EAP türü **EAP-TLS**’dir. |
| **Kimlik doğrulama yöntemi** | Bağlantı için kimlik doğrulama yöntemini seçin:<br><br>- **Sertifikalar**: Sunucuya gösterilen kimlik sertifikası olan SCEP istemci sertifikasını seçin.<br><br>- **Kullanıcı Adı ve Parola**: Kimlik doğrulama için bir **EAP dışı yöntem (iç kimlik)** girin. Seçenekleriniz şunlardır:<br><br>- **Şifrelenmemiş parola (PAP)**<br>- **Karşılıklı Kimlik Doğrulama Protokolü (CHAP)**<br>- **Microsoft CHAP (MS-CHAP)**<br>- **Microsoft CHAP Sürüm 2 (MS-CHAP v2)**<br><br>- **Kimlik gizliliği (dış kimlik)**: EAP kimlik isteğine yanıt olarak gönderilen metni girin. Bu metin herhangi bir değer olabilir. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir. | EAP türü **EAP-TTLS** olur |

## <a name="use-an-imported-settings-file"></a>İçeri aktarılan ayarlar dosyasını kullanma

Intune'da sağlanmayan tüm ayarlar için, başka bir Windows cihazından Wi-Fi ayarlarını dışarı aktarabilirsiniz. Bu dışarı aktarma, tüm ayarlarıyla birlikte bir XML dosyası oluşturur. Ardından, bu dosyayı Intune'da içeri aktarın ve bunu Wi-Fi profili olarak kullanın. Bkz. [Windows cihazları için Wi-Fi ayarlarını dışarı ve içeri aktarma](wi-fi-settings-import-windows-8-1.md).

## <a name="next-steps"></a>Sonraki adımlar
[Intune'da Wi-Fi ayarlarını yapılandırma](wi-fi-settings-configure.md)
