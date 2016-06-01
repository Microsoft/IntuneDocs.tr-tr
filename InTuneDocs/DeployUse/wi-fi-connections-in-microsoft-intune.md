---
# required metadata

title: Wi-Fi bağlantıları | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 0b1b86ed-2e80-474d-8437-17dd4bc07b55

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune’da Wi-Fi bağlantıları
Microsoft Intune Wi-Fi profillerini, kuruluşunuzdaki cihazlara ve kullanıcılara kablosuz ağ ayarlarını dağıtmak için kullanın. Bu ayarlar, kablosuz ağlara kullanıcı bağlantılarını basitleştirir.

Örneğin, **Contoso Wi-Fi** adlı yeni bir Wi-Fi ağı kurdunuz ve tüm iOS cihazlarının bu ağa bağlanması ayarı yapmak istiyorsunuz. İşlem şöyledir:

1.   **Contoso Wi-Fi** kablosuz ağına bağlanmak için gerekli ayarları içeren bir Wi-Fi profili oluşturun.

2. Profil, iOS cihazları olan kullanıcı grubuna dağıtın.

3.   Kullanıcılar yeni **Contoso Wi-Fi** ağını kablosuz ağ listesinde bulur ve bu ağa kolayca bağlanabilir.

Wi-Fi profillerini aşağıdaki platformlara dağıtabilirsiniz:

-   Android 4.0 ve üzeri

-   iOS 7.1 ve üzeri

-   Mac OS X 10.9 ve üzeri

Windows 8.1 ve üzeri bir sürümü çalıştıran cihazlar için daha önce bir dosyaya aktarılmış Wi-Fi yapılandırma profilini içeri aktarabilirsiniz. Ayrıntılar için, bu konunun ilerleyen bölümlerinde bkz. Wi-Fi profilini içeri aktarma.

## Wi-Fi profili oluşturma

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **İlke** &gt; **İlke Ekle**’ye tıklayın

2.  İlke türlerinden birini seçin ve ardından **İlke Oluştur**'a tıklayın:

    -   **Wi-Fi Profili (Android 4 ve üzeri)**

    -   **Wi-Fi Profili (iOS 7.1 ve üzeri)**

    -   **Wi-Fi Profili (Mac OS X 10.9 ve üzeri)**

    Bu ilke türü için önerilen ayar yok. Özel bir ilke oluşturmanız gerekir.

3.  Profil için adı ve açıklamayı belirtin.

4.  **Ağ Bağlantıları** değerlerini belirtin:

  | Ayar| Daha fazla bilgi| **Ağ adı**|Kablosuz ağ için açıklayıcı bir ad belirtin. Bu ad, kullanıcının cihazında bir kablosuz ağ seçildiğinde görüntülenen addır.|

5. **SSID (Hizmet Kümesi Tanımlayıcısı)**|Cihazların bağlanmasını istediğiniz kablosuz ağın (SSID) bilgisini belirtin. SSID'yi büyük/küçük harfe duyarlıdır ve kullanıcılara gösterilmez.|

  #### **Bu ağ aralık içinde olduğunda otomatik olarak bağlan**|Aralıkta olduğunda kablosuz ağa cihazları otomatik olarak bağlamak için bu seçeneği belirleyin.|

  **Ağ adını yayınlamadığında bağlan (SSID)**|Cihazların, ağ listesinde görünmediğinde (gizli olduğu veya adını yayınlamadığı için) ağa bağlanmasına izin vermek istiyorsanız bu seçeneği belirleyin.<br /><br />-   **Seçilen platform için **Güvenlik Ayarları** 'nı yapılandırın.**<br />-   Kullanılabilir ayarlar seçtiğiniz güvenlik türlerine bağlıdır.<br /><br />-   **Android cihazlar için**<br />-   **| Ayar adı| Daha fazla bilgi | Şu durumlarda kullanın:|**<br />-   **Güvenlik türü**|Kablosuz ağ için güvenlik protokolü seçin: WPA-Kuruluş/WPA2-Kuruluş<br /><br />-   **Kimlik doğrulama yok (Açık)**, ağ güvenli değilse.|Her zaman|<br />-   **EAP Tipi**|Güvenli kablosuz bağlantıların kimliğini doğrulamak için kullanılan Genişletilebilir Kimlik Doğrulama Protokolü (EAP) türünü seçin:<br /><br />-   **EAP-TLS**<br />-   **PEAP**<br />-   ****EAP-TTLS**|**WPA-Kuruluşu/WPA2-Kuruluşu** güvenlik türünü seçtiğinizde.|**<br />-   ****Sunucu doğrulaması için kök sertifikaları seçin**|**Seç**’e tıklayın, ardından bağlantı kimliğini doğrulamak için kullanılan güvenilir kök sertifika profilini seçin.**<br />-   ****Önemli:** Güvenilen kök sertifika profilini oluşturmak için, bkz. [Kaynak erişimini sertifika profilleriyle güvenli hale getirme](secure-resource-access-with-certificate-profiles.md).|Herhangi bir **EAP Türü** seçildiğinde.|**<br /><br />**Kimlik doğrulama yöntemi**|Bağlantı için kimlik doğrulama yöntemini seçin: İstemci sertifikasını belirtmek için**Sertifikalar**  **Kullanıcı adı ve Parola**, kimlik doğrulama için farklı bir yöntem belirtmek amacıyla |**EAP türü**, **PEAP** veya **EAP-TTLS** olduğunda **Kimlik doğrulaması (İç kimlik) için EAP olmayan bir yöntem seçin**| Bağlantı kimliğini nasıl doğrulayacağınızı seçin:

  #### Yok.

  Şifrelenmemiş parola (PAP)<br /><br />-   **Karşılıklı Kimlik Doğrulama Protokolü (CHAP)**<br />-   **Microsoft CHAP (MS-CHAP)**<br />-   **Microsoft CHAP Sürüm 2 (MS-CHAP v2)**<br />-   Kullanılabilir seçenekler, seçtiğiniz EAP türüne bağlıdır.|**Kimlik doğrulama yöntemi**, **kullanıcı adı ve Parola** olduğunda<br /><br />-   ****Kimlik gizliliğini etkinleştirin (Dış Kimlik)**|Bir EAP kimlik isteğine yanıt olarak gönderilen metni belirtin.**<br />-   **Bu metin herhangi bir değer olabilir.**<br />-   **Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.|**EAP türü,** **PEAP** veya **EAP-TTLS** olduğunda**<br />-   ****İstemci kimlik doğrulaması için bir istemci sertifikası seçin (Kimlik Sertifikası)**|**Seç**’e tıklayın, ardından bağlantı kimliğini doğrulamak için kullanılan SCEP sertifika profilini seçin.**<br />-   ****Önemli:** Bir SCEP sertifika profili oluşturmak için, bkz. [Sertifika profilleriyle kaynak erişimini güvenli hale getirin](secure-resource-access-with-certificate-profiles.md). | Güvenlik türü **WPA-Kuruluş/WPA2-Kuruluş** olduğunda ve herhangi bir **EAP türü** seçildiğinde.|**<br />-   iOS ve Mac OS X cihazlar için | Ayar adı| Daha fazla bilgi | Şu durumlarda kullanın:| **Güvenlik türü**|Kablosuz ağ güvenlik protokolünü seçin:<br /><br />WPA-Kişisel/WPA2-Kişisel<br /><br /><ul><li>WPA-Kuruluş/WPA2-Kuruluş</li><li>WEP<br /><br /><ul><li>****Kimlik doğrulama yok (Açık)**, ağ güvenli değilse.|Her zaman|**</li><li>****EAP Tipi**|Güvenli kablosuz bağlantıların kimliğini doğrulamak için kullanılan Genişletilebilir Kimlik Doğrulama Protokolü (EAP) türünü seçin:**</li><li>**EAP-TLS**</li><li>**PEAP**</li><li>**EAP-TLS**</li><li>**EAP-AST**</li></ul></li></ul>LEAP **EAP-SIM**|**WPA-Kuruluş/WPA2-Kuruluş** güvenlik türünü seçtiğinizde **Güvenilir sunucu sertifika adları**|Bağlantı kimliğini doğrulamak için kullanılan güvenilir kök sertifika profilini seçin.<br /><br />**Önemli:** Güvenilen kök sertifika profilini oluşturmak için, bkz. [Kaynak erişimini sertifika profilleriyle güvenli hale getirme](secure-resource-access-with-certificate-profiles.md).|EAP türü olarak **EAP-TLS**, **PEAP**, **EAP-TTLS** veya **EAP-FAST** seçtiğinde

6. **Korumalı Erişim Kimlik Bilgisi (PAC) kullanın**|İstemci ile kimlik doğrulama sunucusu arasında kimliği doğrulanmış bir tünel oluşturmak için korumalı erişim kimlik bilgilerini kullanmayı seçin.

    |Varsa mevcut bir PAC dosyası kullanılır.|**EAP-türü** **EAP-FAST** olduğunda|**PAC gönder**|PAC dosyasını cihazlarınıza gönderir.|Kullanıldığında, PAC dosyasının sunucu kimliği doğrulanmadan sağlanması için **PAC Dosyasını Anonim Olarak Sağla** öğesini de seçebilirsiniz.|**Korumalı Erişim Kimlik Bilgisi (PAC) kullanın** seçildiğinde.||
    |----------------|-------------------|-------------|
    |****Kimlik doğrulama yöntemi**|Bağlantı için kullanılan kimlik doğrulama yöntemini seçin:**|İstemci sertifikasını belirtmek için**Sertifikalar** <br /><br />-   Kimlik doğrulaması (İç kimlik olarak da bilinir) için aşağıdaki EAP olmayan yöntemlerden birini belirtmek üzere **Kullanıcı Adı ve Parola**:<br />-   Yok.<br />-   Şifrelenmemiş parola (PAP)|Karşılıklı Kimlik Doğrulama Protokolü (CHAP)|
    |Microsoft CHAP (MS-CHAP)|Microsoft CHAP Sürüm 2 (MS-CHAP v2)|EAP-TLS|
    |**|**EAP türü**, **PEAP** veya **EAP-TTLS** olduğunda**|**İstemci kimlik doğrulaması için bir istemci sertifikası seçin (Kimlik Sertifikası)**|Bağlantı kimliğini doğrulamak için kullanılan SCEP sertifika profilini seçin.|**Önemli:** Bir SCEP sertifika profili oluşturmak için, bkz. [Sertifika profilleriyle kaynak erişimini güvenli hale getirin](secure-resource-access-with-certificate-profiles.md). | Güvenlik türü **WPA-Kuruluş/WPA2-Kuruluş** olduğunda ve **EAP türü**, **EAP-TLS**, **PEAP** veya **EAP-TTLS** olduğunda|

7.  **Kimlik gizliliğini etkinleştirin (Dış Kimlik)**|Bir EAP kimlik isteğine yanıt olarak gönderilen metni belirtin.

Bu metin herhangi bir değer olabilir. Kimlik doğrulaması sırasında, başlangıçta bu anonim kimlik gönderilir, ardından güvenli bir tünelde gerçek kimlik gönderilir.|**EAP türü,** **PEAP**, **EAP-TTLS** veya **EAP-FAST** olarak ayarlandığında

## (yalnızca iOS ve MAC OS X) **Proxy Ayarlarını** Yapılandırma

### Ayar adı
Daha fazla bilgi Şu durumlarda kullanın:

1.  Bu Wi-Fi bağlantısı için proxy ayarları

2.  Proxy ayarları türünü seçin:

3.  **Hiçbiri** (varsayılan)  **El ile** - Proxy sunucusunun URL ve bağlantı noktası numarasını el ile belirtin.

4.  **Otomatik** – Proxy sunucusunu yapılandırmak için bir yapılandırma dosyası kullanın.

## Her zaman
**Proxy sunucu adresi** ve **Bağlantı noktası numarası** Proxy sunucusunun URL ve bağlantı noktası numarasını belirtin.

1.  **Bu Wi-Fi bağlantısı için proxy ayarları** değeri **El ile** olarak ayarlanır

2.  Proxy Sunucusu URL'si

    Proxy sunucusu ayarlarını içeren dosyanın URL'sini belirtin. **Bu Wi-Fi bağlantısı için proxy ayarları** değeri **Otomatik** olarak ayarlanır

3.  Wi-Fi profilini kaydetme

    |Yeni ilke, **İlke** çalışma alanının **Yapılandırma İlkeleri** düğümünde görüntülenir.|Profili dağıtma hakkında bilgi için, bkz. **Sonraki adımlar**|
    |----------------|--------------------|
    |**Wi-Fi yapılandırma profilini dışarı aktarma veya içeri aktarma (yalnızca Windows 8.1 ve üzeri)**|Bir Wi-Fi profilini dışarı aktarma|
    |**Windows'ta **netsh wlan** yardımcı programını kullanarak var olan bir Wi-Fi profilini Intune tarafından okunabilen bir XML dosyasına aktarabilirsiniz.**|Gerekli WiFi profilinin zaten yüklü olduğu bir Windows bilgisayarda bu aşağıdaki yordamı izleyin.|

4.  Dışarı aktarılan W-Fi-profilleri için c:\WiFi gibi bir yerel klasör oluşturun

    |Yönetici olarak bir Komut İstemi açın.|`netsh wlan show profiles` komutunu çalıştırın ve dışarı aktarmak istediğiniz profilin adını not edin.|
    |----------------|--------------------|
    |**Bu örnekte profil adı *WiFiName* şeklindedir.**|Şu komutu çalıştırın: `netsh wlan export profile name="ProfileName" folder=c:\Wifi`. Bunun yapılması hedef klasörünüzde "Wi-Fi-WiFiName.xml" adlı bir Wi-Fi profili dosyası oluşturur.|
    |**Bir Wi-Fi profilini içeri aktarma**|Daha sonra gerekli kullanıcı veya cihaz grubuna dağıtabileceğiniz bir dizi Wi-Fi ayarını içeri aktarmak için **Windows Wi-Fi İçeri Aktarma İlkesi**'ni kullanın.|
    |**Bir Wi-Fi profilini dışarı aktarma yordamı için bkz.**|[Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **İlke** &gt; **İlke Ekle**’ye tıklayın|

5.  **Windows** &gt; **Windows Wi-Fi İçeri Aktarma İlkesi** türünde bir ilke yapılandırın

6.  Yalnızca özel bir Windows Wi-Fi içeri aktarma ilkesi oluşturup dağıtabilirsiniz.

## Önerilen ayarlar kullanılamaz.

1.  Windows Wi-Fi İçeri Aktarma İlkesi için aşağıdaki genel değerleri belirtin:

2.  Ayar adı

    -   Daha fazla bilgi

    -   Ad


Wi-Fi profilini Intune konsolunda tanımlamak üzere benzersiz bir ad girin. Açıklama


<!--HONumber=May16_HO2-->


