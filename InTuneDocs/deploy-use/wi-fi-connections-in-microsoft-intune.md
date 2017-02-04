---
title: "Wi-Fi bağlantıları | Microsoft Docs"
description: "Kullanıcıların Wi-Fi ağlarınıza bağlanmasına yardımcı olmak için Wi-Fi profilleri kullanın."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0b1b86ed-2e80-474d-8437-17dd4bc07b55
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 985b3d14091f1adff15ae08dd95800640363d2f2


---

# <a name="configure-devices-to-connect-to-your-corporate-wi-fi-networks"></a>Cihazları kurumsal Wi-Fi ağlarınıza bağlanmak üzere yapılandırma

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune Wi-Fi profillerini, kuruluşunuzdaki cihazlara ve kullanıcılara kablosuz ağ ayarlarını dağıtmak için kullanın. Bir Wi-Fi profili dağıttığınızda, kullanıcılarınız kurumsal Wi-Fi ağınıza ağı kendileri yapılandırmak zorunda kalmadan erişir.

Örneğin, **Contoso Wi-Fi** adlı yeni bir Wi-Fi ağı kurdunuz ve tüm iOS cihazlarının bu ağa bağlanması ayarı yapmak istiyorsunuz. İşlem şöyledir:

![Wi-Fi profili işlem özeti](..\media\wi-fi-process-diagram.png)

1.   **Contoso Wi-Fi** kablosuz ağına bağlanmak için gerekli ayarları içeren bir Wi-Fi profili oluşturun.

2.   Profil, iOS cihazları olan kullanıcı grubuna dağıtın.

3.   Kullanıcılar yeni **Contoso Wi-Fi** ağını kablosuz ağ listesinde bulur ve bu ağa kolayca bağlanabilir.


## <a name="create-a-wi-fi-profile"></a>Wi-Fi profili oluşturma

Wi-Fi profillerini aşağıdaki platformlara dağıtabilirsiniz:

-   Android 4.0 ve üzeri

-   Android for Work   

-   iOS 8.0 ve üzeri

-   Mac OS X 10.9 ve üzeri

Windows 8.1 veya Windows 10 masaüstü veya mobil işletim sistemi çalıştıran cihazlar için daha önce bir dosyaya aktarılmış Wi-Fi yapılandırma profilini içeri aktarabilirsiniz. Ayrıntılar için bkz. [Windows cihazları için bir Wi-Fi yapılandırma profilini içeri veya dışarı aktarma](#export-or-import-a-wi-fi-configuration-profile-for-windows-devices).

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **İlke** &gt; **İlke Ekle**’yi seçin.

2.  İlke türlerinden birini seçin ve ardından **İlke Oluştur**'u seçin:

    -   Wi-Fi Profili (Android 4 ve üzeri)

    -   Wi-Fi Profili (Android for Work)

    -   Wi-Fi Profili (iOS 8.0 ve üzeri)

    -   Wi-Fi Profili (Mac OS X 10.9 ve üzeri)


Bu ilke türü için önerilen ayar yok. Özel bir ilke oluşturmanız gerekir.

3.  Profil için adı ve açıklamayı belirtin.

4. **Ağ Bağlantıları** değerlerini belirtin.
 - **SSID (Hizmet Kümesi Tanımlayıcısı)**: Kullanıcıların SSID bilgisi yerine ağ adını görmelerini istiyorsanız bu seçeneği belirleyin.
 - **Ağ adını (SSID) yayınlamadığında bağlan**: Cihazların, ağ listesinde görünmediğinde (gizli olduğu veya adını yayınlamadığı için) ağa bağlanmasına izin vermek istiyorsanız bu seçeneği belirleyin.

5. Seçilen platform için **Güvenlik Ayarları** 'nı yapılandırın. Kullanılabilir ayarlar seçtiğiniz güvenlik türlerine bağlıdır. Tümü [Güvenlik ayarları](#security-settings) bölümünde açıklanmıştır.

6. **Proxy Ayarlarını** yapılandırın (yalnızca iOS ve MAC OS X).

    |Ayar adı|Daha fazla bilgi|Ne zaman kullanmalı|
    |----------------|-------------------|-------------|
    |**Bu Wi-Fi bağlantısı için proxy ayarları**|Proxy ayarları türünü seçin:<br /><br />-   **Hiçbiri** (varsayılan)<br />-   **El ile** - Proxy sunucusunun URL ve bağlantı noktası numarasını el ile belirtin.<br />-   **Otomatik** - Proxy sunucusunu yapılandırmak için bir yapılandırma dosyası kullanın.|Her zaman|
    |**Proxy sunucu adresi** ve **Bağlantı noktası numarası**|Proxy sunucusunun URL ve bağlantı noktası numarasını belirtin.|**Bu Wi-Fi bağlantısı için proxy ayarları** değeri **El ile** olarak ayarlandıysa|
    |**Proxy Sunucusu URL'si**|Proxy sunucusu ayarlarını içeren dosyanın URL'sini belirtin.|**Bu Wi-Fi bağlantısı için proxy ayarları** değeri **Otomatik** olarak ayarlandıysa|

7.  Wi-Fi profilini kaydetme

Yeni ilke, **İlke** çalışma alanının **Yapılandırma İlkeleri** düğümünde görüntülenir. Profili dağıtma hakkında bilgi için, bkz. **Sonraki adımlar**

## <a name="export-or-import-a-wi-fi-configuration-profile-for-windows-devices"></a>Windows cihazları için bir Wi-Fi yapılandırma profilini içeri veya dışarı aktarma

Windows 8.1 veya Windows 10 masaüstü veya mobil işletim sistemi çalıştıran cihazlar için daha önce bir dosyaya aktarılmış Wi-Fi yapılandırma profilini içeri aktarabilirsiniz.

### <a name="export-a-wi-fi-profile"></a>Bir Wi-Fi profilini dışarı aktarma
Windows'ta **netsh wlan** yardımcı programını kullanarak var olan bir Wi-Fi profilini Intune tarafından okunabilen bir XML dosyasına aktarabilirsiniz. Gerekli Wi-Fi profilinin zaten yüklü olduğu bir Windows bilgisayarda aşağıdaki adımları uygulayın:

1.  Dışarı aktarılan W-Fi-profilleri için yerel klasör oluşturun. Örneğin, **c:\WiFi.**

2.  Yönetici olarak bir komut istemi açın.

3.  `netsh wlan show profiles` komutunu çalıştırın ve dışarı aktarmak istediğiniz profilin adını not edin.  Bu örnekte profil adı **WiFiName** şeklindedir.

4.  Şu komutu çalıştırın: `netsh wlan export profile name="ProfileName" folder=c:\Wifi`. Bunun yapılması hedef klasörünüzde **Wi-Fi-WiFiName.xml** adlı bir Wi-Fi profili dosyası oluşturur.

### <a name="import-a-wi-fi-profile"></a>Bir Wi-Fi profilini içeri aktarma
Daha sonra gerekli kullanıcı veya cihaz grubuna dağıtabileceğiniz bir dizi Wi-Fi ayarını içeri aktarmak için **Windows Wi-Fi İçeri Aktarma İlkesi**'ni kullanın.


1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **İlke** &gt; **İlke Ekle**'ye tıklayın.

2.  **Windows** &gt; **Wi-Fi İçeri Aktarma (Windows 8.1 ve üstü)** türünde bir ilke yapılandırın.

    Bu ilke Windows 8.1 ve Windows 10 masaüstü ve mobil işletim sistemlerini çalıştıran cihazlara uygulanabilir.

    Yalnızca *özel* bir Windows Wi-Fi içeri aktarma ilkesi oluşturup dağıtabilirsiniz. Önerilen ayarlar kullanılamaz.

3.  Windows Wi-Fi İçeri Aktarma İlkesi için aşağıdaki genel değerleri belirtin:

    |Ayar adı|Daha fazla bilgi|
    |----------------|--------------------|
    |**Ad**|Wi-Fi profilini Intune konsolunda tanımlamak üzere benzersiz bir ad girin.|
    |**Açıklama**|Wi-Fi profiline ve onu bulmanıza yardımcı olan diğer ilgili bilgilere ilişkin bir açıklama belirtin.|

4.  **Özel Wi-Fi Profili** üst bilgisi altında aşağıdaki değerleri belirtin:

    |Ayar adı|Daha fazla bilgi|
    |----------------|--------------------|
    |**Yapılandırma profili dosyası**|Intune içine aktarmak istediğiniz Wi-Fi profili ayarlarını içeren XML dosyasını seçmek için **İçeri Aktar**'ı seçin.|
    |**Özel yapılandırma profili adı (kullanıcılara gösterilir)**|Wi-Fi yapılandırma profilinin cihazlarda kullanıcılara gösterilen adının nasıl görüntüleneceğini seçin.|
    |**Yapılandırma profili ayrıntıları**|Seçilen yapılandırma profili için XML kodunun nasıl görüntüleneceğini seçin.|

5.  İşiniz bittiğinde **İlkeyi Kaydet**'e tıklayın.

6.  Yeni ilke, **İlke** çalışma alanının **Yapılandırma İlkeleri** düğümünde görüntülenir.

## <a name="deploy-the-profile"></a>İlkeyi dağıtma

Profil bir ilke türü olduğundan dağıtılması için **İlke** çalışma alanı kullanmanız gerekir.

1.  **İlke** çalışma alanında, dağıtmak istediğiniz ilkeyi ve ardından **Dağıtımı Yönet**’i seçin.

2.  **Dağıtımı Yönet** iletişim kutusunda:

    -   **İlkeyi dağıtmak için**: İlkeyi dağıtmak istediğiniz bir veya daha fazla grubu seçin. Ardından **Ekle** &gt; **Tamam**'ı seçin.

    -   **Dağıtmadan iletişim kutusunu kapatmak için**: **İptal**'e tıklayın.


**İlke** çalışma alanının **Genel Bakış** sayfasında işlem yapmanız gereken ilkeyle ilgili sorunlar görüntülenir. Ayrıca, Pano çalışma alanında bir durum özeti görüntülenir.

## <a name="security-settings"></a>Güvenlik ayarları
Bu tablolar Android, iOS ve Mac OS X Wi-Fi profilleri için bulunan güvenlik ayarlarının ayrıntılarını içerir.

### <a name="security-settings-for-android-devices"></a>Android cihazlar için güvenlik ayarları

  |Ayar adı|Daha fazla bilgi|Ne zaman kullanmalı|
|----------------|--------------------|-------------|
|**Güvenlik türü**|Kablosuz ağ için güvenlik protokolü seçin:<br /><br />-   **WPA-Kuruluş/WPA2-Kuruluş**<br />Ağ güvenli değilse -   **Kimlik doğrulaması yapma (Açık)**.|Her zaman|
|**EAP Türü**|Güvenli kablosuz bağlantıların kimliğini doğrulamak için kullanılan Genişletilebilir Kimlik Doğrulama Protokolü (EAP) türünü seçin:<br /><br />-   **EAP-TLS**<br />-   **PEAP**<br />-   **EAP-TTLS**|**WPA-Kuruluş/WPA2-Kuruluş** güvenlik türünü seçtiyseniz.|
|**Sunucu doğrulaması için kök sertifikalarını seçin**|**Seç**'i belirleyin, ardından bağlantı kimliğini doğrulamak için kullanılan güvenilir kök sertifika profilini seçin. Güvenilir kök sertifika profilini oluşturma hakkında daha fazla bilgi için bkz. [Sertifika profillerini kullanarak kaynak erişiminin güvenliğini sağlama](secure-resource-access-with-certificate-profiles.md).|Herhangi bir **EAP Türü** seçimi yaptıysanız.|
|**Kimlik doğrulama yöntemi**|Bağlantı için kullanılan kimlik doğrulama yöntemini seçin:<br /><br />İstemci sertifikasını belirtmek için -   **Sertifikalar**<br />Farklı bir kimlik doğrulama yöntemi belirtmek için -   **Kullanıcı Adı ve Parola**|**EAP türü**, **PEAP** veya **EAP-TTLS**'dir.|
|**Kimlik doğrulaması (İç kimlik) için bir EAP yöntemi seçin**|Bağlantı kimliğini nasıl doğrulayacağınızı seçin:<br /><br />-   **Yok**<br />-   **Şifrelenmemiş parola (PAP)**<br />-   **Karşılıklı Kimlik Doğrulama Protokolü (CHAP)**<br />-   **Microsoft CHAP (MS-CHAP)**<br />-   **Microsoft CHAP Sürüm 2 (MS-CHAP v2)**<br /><br />Mevcut seçenekler, seçtiğiniz EAP türüne bağlıdır.|**Kimlik doğrulama yöntemi**, **Kullanıcı Adı ve Parola**'dır.|
|**Kimlik gizliliğini (Dış kimlik) etkinleştir**|Bir EAP kimlik isteğine yanıt olarak gönderilen metni belirtin. Bu metin herhangi bir değer olabilir. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir. Ardından gerçek kimlik güvenli bir tünelde gönderilir.|**EAP türü** **PEAP** veya **EAP-TTLS** ise.|
|**İstemci kimlik doğrulaması (Kimlik Sertifikası) için bir istemci sertifikası seçin**|**Seç**'i belirleyin, ardından bağlantı kimliğini doğrulamak için kullanılan SCEP sertifika profilini seçin. SCEP sertifika profilini oluşturma hakkında daha fazla bilgi için bkz. [Sertifika profillerini kullanarak kaynak erişiminin güvenliğini sağlama](secure-resource-access-with-certificate-profiles.md).|Güvenlik türü **WPA-Kuruluş/WPA2-Kuruluş** şeklindeyse ve herhangi bir **EAP türü** seçildiyse.|

### <a name="security-settings-for-ios-and-mac-os-x-devices"></a>iOS ve Mac OS X cihazlar için güvenlik ayarları

  |Ayar adı|Daha fazla bilgi|Ne zaman kullanmalı|
|----------------|--------------------|-------------|
|**Güvenlik türü**|Kablosuz ağ güvenlik protokolünü seçin:<br /><br />-   **WPA-Kişisel/WPA2-Kişisel**<br />-   **WPA-Kuruluş/WPA2-Kuruluş**<br />-   **WEP**<br />Ağ güvenli değilse -   **Kimlik doğrulaması yapma (Açık)**.|Her zaman|
|**EAP Türü**|Güvenli kablosuz bağlantıların kimliğini doğrulamak için kullanılan Genişletilebilir Kimlik Doğrulama Protokolü (EAP) türünü seçin:<br /><br />-   **EAP-TLS**<br />-   **PEAP**<br />-   **EAP-TLS**<br />-   **EAP-AST**<br />-   **LEAP**<br />-   **EAP-SIM**|**WPA-Kuruluş/WPA2-Kuruluş** güvenlik türünü seçtiyseniz.|
|**Güvenilir sunucu sertifikası adları**|Bağlantı kimliğini doğrulamak için kullanılan güvenilir kök sertifika profilini seçin. Güvenilir kök sertifika profilini oluşturma hakkında daha fazla bilgi için bkz. [Sertifika profillerini kullanarak kaynak erişiminin güvenliğini sağlama](secure-resource-access-with-certificate-profiles.md).|**EAP-TLS**, **PEAP**, **EAP-TTLS** veya **EAP-FAST** EAP türünü seçtiyseniz.|
|**Korumalı Erişim Kimlik Bilgisi (PAC) Kullan**|İstemci ile kimlik doğrulama sunucusu arasında kimliği doğrulanmış bir tünel oluşturmak için korumalı erişim kimlik bilgilerini kullanmayı seçin. Varsa mevcut bir PAC dosyası kullanılır.|**EAP türü**, **EAP-FAST** ise.|
|**PAC Sağla**|Cihazlarınızdaki PAC dosyasını ayarlar.<br /><br />Kullanıldığında, PAC dosyasının sunucu kimliği doğrulanmadan ayarlanması için **PAC Dosyasını Anonim Olarak Sağla** öğesini de seçebilirsiniz.|**Korumalı Erişim Kimlik Bilgisi (PAC) Kullan** seçildiyse.|
|**Kimlik doğrulama yöntemi**|Bağlantı için kullanılan kimlik doğrulama yöntemini seçin:<br /><br /><ul><li>İstemci sertifikasını belirtmek için**Sertifikalar** </li><li>Kimlik doğrulaması (İç kimlik olarak da bilinir) için aşağıdaki EAP olmayan yöntemlerden birini belirtmek üzere **Kullanıcı Adı ve Parola**:<br /><br /><ul><li>**Yok.**</li><li>**Şifrelenmemiş parola (PAP)**</li><li>**Karşılıklı Kimlik Doğrulama Protokolü (CHAP)**</li><li>**Microsoft CHAP (MS-CHAP)**</li><li>**Microsoft CHAP Sürüm 2 (MS-CHAP v2)**</li><li>**EAP-TLS**</li></ul></li></ul>|**EAP türü** **PEAP** veya **EAP-TTLS** ise.|
|**İstemci kimlik doğrulaması (Kimlik Sertifikası) için bir istemci sertifikası seçin**|Bağlantı kimliğini doğrulamak için kullanılan SCEP sertifikası profilini seçin. SCEP sertifika profilini oluşturma hakkında daha fazla bilgi için bkz. [Sertifika profillerini kullanarak kaynak erişiminin güvenliğini sağlama](secure-resource-access-with-certificate-profiles.md).|Güvenlik türü **WPA-Kuruluş/WPA2-Kuruluş** ve **EAP türü** **EAP-TLS**, **PEAP** veya **EAP-TTLS** ise.|
|**Kimlik gizliliğini (Dış kimlik) etkinleştir**|Bir EAP kimlik isteğine yanıt olarak gönderilen metni belirtin. Bu metin herhangi bir değer olabilir.<br /><br />Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir. Ardından gerçek kimlik güvenli bir tünelde gönderilir.|**EAP türü** **PEAP**, **EAP-TTLS** veya **EAP-FAST** ise.|


### <a name="see-also"></a>Ayrıca bkz.
Önceden paylaşılan anahtarla bir Wi-Fi profilinin nasıl oluşturulduğunu, [Önceden paylaşılan anahtar Wi-Fi profili](pre-shared-key-wi-fi-profile.md) başlığı altında öğrenebilirsiniz.



<!--HONumber=Dec16_HO2-->


