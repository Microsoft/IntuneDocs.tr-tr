---
title: Microsoft Intune yönetilen cihazın NDES iletişim sorunlarını giderme | Microsoft Docs
description: Intune ile sertifika dağıtmak için SCEP sertifika profillerini kullanırken yönetilen cihazın NDES sunucusuna iletişimini sorun giderme.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/30/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7945f1df3ddf1a6ff2c42a537e1071d1b5acff24
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77514277"
---
# <a name="troubleshoot-device-to-ndes-server-communication-for-scep-certificate-profiles-in-microsoft-intune"></a>Microsoft Intune 'daki SCEP sertifika profilleri için cihazdan NDES sunucu iletişimi sorunlarını giderme

Bir Intune Basit Sertifika Kayıt Protokolü (SCEP) sertifika profilini alan ve işleyen bir cihazın bir sınama sunmak üzere ağ cihazı kayıt hizmeti 'ne (NDES) başarıyla başvurmadığını öğrenmek için aşağıdaki bilgileri kullanın. Cihazda, özel bir anahtar oluşturulur ve sertifika Imzalama Isteği (CSR) ve zorluk cihazdan NDES sunucusuna geçirilir. NDES sunucusuyla iletişim kurmak için cihaz, SCEP sertifika profilinden URI 'yi kullanır.

Bu makale, [SCEP iletişim akışına genel bakış](troubleshoot-scep-certificate-profiles.md)' ın 2. adımına başvurur.

## <a name="review-iis-logs-for-a-connection-from-the-device"></a>Cihazdan bir bağlantı için IIS günlüklerini gözden geçirme

IIS günlükleri tüm platformlar için aynı tür girdileri içerir.


1. NDES sunucusunda, şu klasörde bulunan en son IIS günlük dosyasını açın: *%systemdrive%\ınetpub\logs\logfiles\w3svc1*

2. Günlükte aşağıdaki örneklere benzer girdileri arayın. Her iki örnek de, sonunda görünen durum **200**' i içerir:

   `fe80::f53d:89b8:c3e8:5fec%13 GET /certsrv/mscep/mscep.dll/pkiclient.exe operation=GetCACaps&message=default 80 - fe80::f53d:89b8:c3e8:5fec%13 Mozilla/4.0+(compatible;+Win32;+NDES+client) - 200 0 0 186 0.`

   Ve

   `fe80::f53d:89b8:c3e8:5fec%13 GET /certsrv/mscep/mscep.dll/pkiclient.exe operation=GetCACert&message=default 80 - fe80::f53d:89b8:c3e8:5fec%13 Mozilla/4.0+(compatible;+Win32;+NDES+client) - 200 0 0 3567 0`

3. Cihaz IIS ile iletişim kurduğunda, mscep. dll için bir HTTP GET isteği günlüğe kaydedilir.

   Bu isteğin sonundaki durum kodunu gözden geçirin:
   - **Durum kodu 200**: Bu durum NDES sunucusuyla kurulan bağlantının başarılı olduğunu gösterir.
   - **500 durum kodu**: IIS_IURS grubunun doğru izinleri bulunmayabilir. Bu makalenin devamındaki [500 durum koduna](#status-code-500)bakın.
   - Durum kodu 200 veya 500 değilse:

     - Yapılandırmayı doğrulamaya yardımcı olması için bu makaledeki daha sonra [SCEP sunucu URL 'Sini test](#test-the-scep-server-url) edin bölümüne bakın.

     - Daha az yaygın hata kodları hakkında bilgi için [IIS 7 ve sonraki sürümlerde http durum koduna](https://support.microsoft.com/help/943891) bakın.

   Bağlantı isteği hiç günlüğe kaydedilmez, cihazdaki kişi cihaz ile NDES sunucusu arasındaki ağ üzerinde engelleniyor olabilir.

## <a name="review-device-logs-for-connections-to-ndes"></a>NDES bağlantıları için cihaz günlüklerini gözden geçirme

### <a name="android-devices"></a>Android cihazlar

[CIHAZLAR OMADM günlüğünü](troubleshoot-scep-certificate-profiles.md#logs-for-android-devices)gözden geçirin. Cihaz NDES 'ye bağlanırken günlüğe kaydedilecek aşağıdakine benzer girdileri arayın:

```
2018-02-27T05:16:08.2500000  VERB  Event  com.microsoft.omadm.platforms.android.certmgr.CertificateEnrollmentManager  18327    10  There are 1 requests
2018-02-27T05:16:08.2500000  VERB  Event  com.microsoft.omadm.platforms.android.certmgr.CertificateEnrollmentManager  18327    10  Trying to enroll certificate request: ModelName=AC_51bad41f-3854-4eb5-a2f2-0f7a94034ee8%2FLogicalName_39907e78_e61b_4730_b9fa_d44a53e4111c;Hash=1677525787
2018-02-27T05:16:09.5530000  VERB  Event  org.jscep.transport.UrlConnectionGetTransport  18327    10  Sending GetCACaps(ca) to https://<server>.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACaps&message=ca
2018-02-27T05:16:14.6440000  VERB  Event  org.jscep.transport.UrlConnectionGetTransport  18327    10  Received '200 OK' when sending GetCACaps(ca) to https://<server>.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACaps&message=ca
2018-02-27T05:16:21.8220000  VERB  Event  org.jscep.message.PkiMessageEncoder  18327     10 Encoding message: org.jscep.message.PkcsReq@2b06f45f[messageData=org.<server>.pkcs.PKCS10CertificationRequest@699b3cd,messageType=PKCS_REQ,senderNonce=Nonce [D447AE9955E624A56A09D64E2B3AE76E],transId=251E592A777C82996C7CF96F3AAADCF996FC31FF]
2018-02-27T05:16:21.8790000  VERB  Event  org.jscep.message.PkiMessageEncoder  18327     10  Signing pkiMessage using key belonging to [dn=CN=<uesrname>; serial=1]
2018-02-27T05:16:21.9580000  VERB  Event  org.jscep.transaction.EnrollmentTransaction  18327     10  Sending org.<server>.cms.CMSSignedData@ad57775
```

Anahtar girişleri aşağıdaki örnek metin dizelerini içerir:

- 1 istek var
- Https://\<Server > 'ye GetCACaps (CA) gönderilirken ' 200 OK ' alındı. msappproxy. net/certsrv/mscep/mscep. dll? Operation = GetCACaps & Message = CA
- [DN = CN =\<Kullanıcı adı >; seri = 1] öğesine ait anahtar kullanılarak pkiMessage imzalanıyor


Bağlantı, NDES sunucusunun%systemdrive%\ınetpub\logs\logfiles\w3svc1\ klasöründe IIS tarafından da günlüğe kaydedilir. Aşağıda bir örnek verilmiştir:

```
fe80::f53d:89b8:c3e8:5fec%13 GET /certsrv/mscep/mscep.dll operation=GetCACert&message=ca 443 - 
fe80::f53d:89b8:c3e8:5fec%13 Dalvik/2.1.0+(Linux;+U;+Android+5.0;+P01M+Build/LRX21V) - 200 0 0 3909 0
fe80::f53d:89b8:c3e8:5fec%13 GET /certsrv/mscep/mscep.dll operation=GetCACaps&message=ca 443 - 
fe80::f53d:89b8:c3e8:5fec%13 Dalvik/2.1.0+(Linux;+U;+Android+5.0;+P01M+Build/LRX21V) - 200 0 0 421 
```

### <a name="iosipados-devices"></a>iOS/ıpados cihazları

[Cihazlar hata ayıklama günlüğünü](troubleshoot-scep-certificate-profiles.md#logs-for-ios-and-ipados-devices)gözden geçirin. Cihaz NDES 'ye bağlanırken günlüğe kaydedilecek aşağıdakine benzer girdileri arayın:

```
debug    18:30:53.691033 -0500    profiled    Performing synchronous URL request: https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACert&message=SCEP%20Authority\ 
debug    18:30:54.640644 -0500    profiled    Performing synchronous URL request: https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACaps&message=SCEP%20Authority\ 
default    18:30:55.483977 -0500    profiled    Attempting to retrieve issued certificate...\ 
debug    18:30:55.487798 -0500    profiled    Sending CSR via GET.\  
debug    18:30:55.487908 -0500    profiled    Performing synchronous URL request: https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=PKIOperation&message=MIAGCSqGSIb3DQEHAqCAMIACAQExDzANBglghkgBZQMEAgMFADCABgkqhkiG9w0BBwGggCSABIIZfzCABgkqhkiG9w0BBwOggDCAAgEAMYIBgjCCAX4CAQAwZjBPMRUwEwYKCZImiZPyLGQBGRYFbG9jYWwxHDAaBgoJkiaJk/IsZAEZFgxmb3VydGhjb2ZmZWUxGDAWBgNVBAMTD0ZvdXJ0aENvZmZlZSBDQQITaAAAAAmaneVjEPlcTwAAAAAACTANBgkqhkiG9w0BAQEFAASCAQCqfsOYpuBToerQLkw/tl4tH9E+97TBTjGQN9NCjSgb78fF6edY0pNDU+PH4RB356wv3rfZi5IiNrVu5Od4k6uK4w0582ZM2n8NJFRY7KWSNHsmTIWlo/Vcr4laAtq5rw+CygaYcefptcaamkjdLj07e/Uk4KsetGo7ztPVjSEFwfRIfKv474dLDmPqp0ZwEWRQGZwmPoqFMbX3g85CJT8khPaqFW05yGDTPSX9YpuEE0Bmtht9EwOpOZe6O7sd77IhfFZVmHmwy5mIYN7K6mpx/4Cb5zcNmY3wmTBlKEkDQpZDRf5PpVQ3bmQ3we9XxeK1S4UsAXHVdYGD+bg/bCafMIAGCSqGSIb3DQEHATAUBggqhkiG9w0DBwQI5D5J2lwZS5OggASCF6jSG9iZA/EJ93fEvZYLV0v7GVo3JAsR11O7DlmkIqvkAg5iC6DQvXO1j88T/MS3wV+rqUbEhktr8Xyf4sAAPI4M6HMfVENCJTStJw1PzaGwUJHEasq39793nw4k268UV5XHXvzZoF3Os2OxUHSfHECOj
```

Anahtar girişleri aşağıdaki örnek metin dizelerini içerir:

- işlem = GetCACert
- Verilen sertifika alınmaya çalışılıyor
- GET aracılığıyla CSR gönderme
- işlem = Pkıoperation

### <a name="windows-devices"></a>Windows cihazları

NDES bağlantısı kuran bir Windows cihazında, Windows Olay Görüntüleyicisi cihazları görüntüleyebilir ve başarılı bir bağlantının göstergelerine bakabilirsiniz. Cihazlarda bir olay KIMLIĞI **36** olarak kaydedilir *DeviceManagement-Enterprise-Diagnostics-*  > **yönetici** günlüğü sağlayın.

Günlüğü açmak için:

1. Cihazda, Windows Olay Görüntüleyicisi açmak için **eventvwr. msc** ' yi çalıştırın.

2. **Microsoft** > **Windows** > **DeviceManagement-Enterprise-Diagnostic-Provider** > **admin** > **uygulamalar ve hizmet günlükleri '** ni genişletin.

3. Anahtar **SCEP: sertifika isteği başarıyla oluşturuldu**ile aşağıdaki örneğe benzeyen olay **36**' i arayın:

   ```
   Event ID:      36
   Task Category: None
   Level:         Information
   Keywords:
   User:          <UserSid>
   Computer:      <Computer Name>
   Description:
   SCEP: Certificate request generated successfully. Enhanced Key Usage: (1.3.6.1.5.5.7.3.2), NDES URL: (https://<server>/certsrv/mscep/mscep.dll/pkiclient.exe), Container Name: (), KSP Setting: (0x2), Store Location: (0x1).
   ```

## <a name="troubleshoot-common-errors"></a>Sık karşılaşılan hataları giderme

Aşağıdaki bölümler, tüm cihaz platformlarından NDES 'ye genel bağlantı sorunlarının sağlanmasına yardımcı olabilir.

### <a name="status-code-500"></a>Durum kodu 500

Aşağıdaki örneğe benzeyen bağlantılar, 500 durum koduyla, *bir Istemcinin kimliğine bürünerek* NDES sunucusundaki IIS_IURS grubuna kimlik doğrulama kullanıcı hakkı atanmamıştır. **500** öğesinin durum değeri sonda görünür:

```
2017-08-08 20:22:16 IP_address GET /certsrv/mscep/mscep.dll operation=GetCACert&message=SCEP%20Authority 443 - 10.5.14.22 profiled/1.0+CFNetwork/811.5.4+Darwin/16.6.0 - 500 0 1346 31
```

**Bu sorunu onarmak için**:

1. NDES sunucusunda, yerel güvenlik Ilkesini açmak için **secpol. msc** ' yi çalıştırın.

2. **Yerel ilkeler**' i genişletin ve **Kullanıcı hakları ataması**' na tıklayın.

3. Sağ bölmedeki **kimlik doğrulamasından sonra Istemcinin özelliklerini Al ' a** çift tıklayın.

4. **Kullanıcı veya Grup Ekle..** . ' ye tıklayın, **Seçilecek nesne adlarını girin kutusuna** **IIS_IURS** girin ve ardından **Tamam**' a tıklayın.

5. **Tamam**'ı tıklatın.

6. Bilgisayarı yeniden başlatın ve ardından cihazdan bağlantıyı yeniden deneyin.

### <a name="test-the-scep-server-url"></a>SCEP sunucusu URL 'sini test etme

SCEP sertifika profilinde belirtilen URL 'YI sınamak için aşağıdaki adımları kullanın.

1. Intune 'da, SCEP sertifika profilinizi düzenleyin ve sunucu URL 'sini kopyalayın. URL *https://contoso.com/certsrv/mscep/msecp.dll* benzemelidir.

2. Bir Web tarayıcısı açın ve ardından bu SCEP sunucu URL 'sine gidin. Sonuç şu şekilde olmalıdır: **http hatası 403,0 – yasak**. Bu sonuç URL 'nin doğru şekilde çalıştığını gösterir.

   Bu hatayı almazsanız, soruna özgü Kılavuzu görüntülemek için gördüğünüz hataya benzeyen bağlantıyı seçin:
   - [Genel bir ağ cihazı kayıt hizmeti iletisi alıyorum](#general-ndes-message)
   - ["HTTP hatası 503" alıyorum. Hizmet kullanılamıyor "](#http-error-503)
   - ["GatewayTimeout" hatası alıyorum](#gatewaytimeout)
   - ["HTTP 414 Isteği-URI çok uzun" alıyorum](#http-414-request-uri-too-long)
   - ["Bu sayfa görüntülenemiyor" olarak alıyorum](#this-page-cant-be-displayed)
   - ["500-Iç sunucu hatası" alıyorum](#internal-server-error)

#### <a name="general-ndes-message"></a>Genel NDES iletisi

SCEP sunucu URL 'sine gözattığınızda aşağıdaki ağ aygıtı kayıt hizmeti iletisini alırsınız:

![SCEP sunucu URL'si](../protect/media/troubleshoot-scep-certificate-device-to-ndes/ndes-server-url-message.png)

- **Neden**: Bu sorun genellikle Microsoft Intune Bağlayıcısı yüklemesiyle ilgili bir sorundur.

  Mscep. dll, gelen isteği izleyen ve doğru şekilde yüklenmişse HTTP 403 hatasını görüntüleyen bir ISAPI uzantısıdır.
  
  **Çözüm**: Microsoft Intune bağlayıcısının başarıyla yüklenip yüklenmediğini öğrenmek Için *setupmsi. log* dosyasını inceleyin. Aşağıdaki örnekte, *yükleme başarıyla tamamlandı* ve *yükleme başarısı veya hata durumu: 0* başarılı bir yükleme olduğunu gösteriyor:

  ```
  MSI (c) (28:54) [16:13:11:905]: Product: Microsoft Intune Connector -- Installation completed successfully.
  MSI (c) (28:54) [16:13:11:999]: Windows Installer installed the product. Product Name: Microsoft Intune Connector. Product Version: 6.1711.4.0. Product Language: 1033. Manufacturer: Microsoft Corporation. Installation success or error status: 0.
  ```

  Yükleme başarısız olursa, Microsoft Intune bağlayıcısını kaldırın ve yeniden yükleyin.

#### <a name="http-error-503"></a>HTTP hatası 503

SCEP sunucu URL 'sine gözattığınızda, şu hatayı alırsınız:

![HTTP hatası 503. Hizmet kullanılamıyor](../protect/media/troubleshoot-scep-certificate-device-to-ndes/service-unavailable.png)

Bu sorun genellikle IIS 'deki **SCEP** uygulama havuzu başlamadığı için oluşur. NDES sunucusunda, **IIS Yöneticisi** ' ni açın ve **uygulama havuzları**' na gidin. **SCEP** uygulama havuzunu bulun ve başlatıldığını onaylayın.

SCEP uygulama havuzu başlatılmazsa, sunucusundaki uygulama olay günlüğünü kontrol edin:

1. Cihazda, **Olay Görüntüleyicisi** açmak ve **Windows günlükleri** > **uygulamasına**gitmek için **eventvwr. msc** ' yi çalıştırın.

2. Aşağıdaki örneğe benzer bir olay arayın. Bu, bir istek alındığında uygulama havuzunun çöktüğü anlamına gelir:

   ```
   Log Name:      Application
   Source:        Application Error
   Event ID:      1000
   Task Category: Application Crashing Events
   Level:         Error
   Keywords:      Classic
   Description: Faulting application name: w3wp.exe, version: 8.5.9600.16384, time stamp: 0x5215df96
   Faulting module name: ntdll.dll, version: 6.3.9600.18821, time stamp: 0x59ba86db
   Exception code: 0xc0000005
   ```

**Uygulama havuzu kilitlenmesinin yaygın nedenleri**:

- **Neden 1**: NDES sunucusunun Güvenilen kök sertifika yetkilileri sertifika deposunda ara CA sertifikaları (otomatik imzalı değil) vardır.

  **Çözüm**: ara sertifikaları Güvenilen kök sertifika yetkilileri sertifika deposundan kaldırın ve ardından NDES sunucusunu yeniden başlatın.
  
  Güvenilen kök sertifika yetkilileri sertifika deposundaki tüm ara sertifikaları belirlemek için aşağıdaki PowerShell cmdlet 'ini çalıştırın: `Get-Childitem -Path cert:\LocalMachine\root -Recurse | Where-Object {$_.Issuer -ne $_.Subject}`

  Değerleri tarafından **verilen ve** **çıkarılan** bir sertifika, kök bir sertifikadır. Aksi takdirde, bu bir ara sertifikadır.

  Sertifikaları kaldırdıktan ve sunucuyu yeniden başlattıktan sonra, ara sertifika olmadığını doğrulamak için PowerShell cmdlet 'ini yeniden çalıştırın. Varsa, bir grup ilkesi ara sertifikaları NDES sunucusuna iletip iletmediğini denetleyin. Bu durumda, NDES sunucusunu grup ilkesi hariç tutun ve ara sertifikaları yeniden kaldırın.

- **Neden 2**: Intune sertifika Bağlayıcısı tarafından kullanılan sertifikalar Için sertifika iptal LISTESI (CRL) Içindeki URL 'ler engellenir veya ulaşılamaz olur.

  **Çözüm**: daha fazla bilgi toplamak için ek günlüğe yazmayı etkinleştirin:
  1. Olay Görüntüleyicisi açın, **görüntüle**' ye tıklayın, **analitik ve hata ayıklama günlüklerini göster** seçeneğinin işaretli olduğundan emin olun.
  2. **Uygulamalar ve hizmetler günlüklerine** giderek **Microsoft** > **Windows** > **CAPI2** > **Işletimsel** > , **İşlemsel**' a sağ tıklayın ve **günlüğü etkinleştir**' e tıklayın.
  3. CAPı2 günlüğü etkinleştirildikten sonra sorunu yeniden oluşturun ve sorunu gidermek için olay günlüğünü inceleyin.

- **Neden 3**: **Certificateregistrationsvc** 'de IIS izninin **Windows kimlik doğrulaması** etkinleştirilmiş olması.

  **Çözüm**: **anonim kimlik doğrulamasını** etkinleştirin ve **Windows kimlik doğrulamasını**devre dışı bırakın ve ardından NDES sunucusunu yeniden başlatın.

  ![IIS izinleri](../protect/media/troubleshoot-scep-certificate-device-to-ndes/iis-permissions.png)

#### <a name="gatewaytimeout"></a>GatewayTimeout

SCEP sunucu URL 'sine gözattığınızda, şu hatayı alırsınız:

![Gatewaytimeout hatası](../protect/media/troubleshoot-scep-certificate-device-to-ndes/gateway-timeout.png)

- **Neden**: **Microsoft AAD uygulama proxy Bağlayıcısı** hizmeti başlatılmadı.

  **Çözüm**: **Services. msc**' yi ÇALıŞTıRıN ve ardından **Microsoft AAD uygulama proxy Bağlayıcısı** hizmetinin çalıştığından ve **Başlangıç türünün** **Otomatik**olarak ayarlandığından emin olun.

#### <a name="http-414-request-uri-too-long"></a>HTTP 414 Isteği-URI çok uzun

SCEP sunucu URL 'sine gözattığınızda şu hatayı alırsınız: `HTTP 414 Request-URI Too Long`

- **Neden**: IIS istek FILTRELEME, NDES hizmetinin aldığı uzun URL 'leri (sorgular) destekleyecek şekilde yapılandırılmamış. Bu destek, [NDES HIZMETINI](certificates-scep-configure.md#configure-the-ndes-service) SCEP için altyapınızla birlikte kullanmak üzere yapılandırdığınızda yapılandırılır.

- **Çözüm**: uzun URL 'ler için desteği yapılandırın.

  1. NDES sunucusunda, IIS Yöneticisi ' ni açın, **varsayılan Web sitesi** ' ni seçin > istek **filtreleme** > **özellik ayarlarını** Düzenle ' yi seçerek **istek filtreleme ayarlarını Düzenle** sayfasını açın.

  2. Aşağıdaki ayarları yapılandırın:
     - **URL uzunluğu üst sınırı (bayt)** = 65534
     - **En fazla sorgu dizesi (bayt)** = 65534

  3. Bu yapılandırmayı kaydetmek ve IIS Yöneticisi 'ni kapatmak için **Tamam** ' ı seçin.

  4. Belirtilen değerlere sahip olduğunu doğrulamak için aşağıdaki kayıt defteri anahtarını bularak bu yapılandırmayı doğrulayın:

     HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\HTTP\Parameters

     Aşağıdaki değerler DWORD girdileri olarak ayarlanır:
     - Ad: **MaxFieldLength**, **65534**'ün ondalık bir değeri ile
     - Ad: **MaxRequestBytes**, **65534**'ün ondalık bir değeri ile

  5. NDES sunucusunu yeniden başlatın.

#### <a name="this-page-cant-be-displayed"></a>Bu sayfa görüntülenemiyor

Azure AD Uygulama Ara Sunucusu yapılandırıldı. SCEP sunucu URL 'sine gözattığınızda, şu hatayı alırsınız:

`This page can't be displayed`

- **Neden**: Bu sorun, SCEP dış URL 'Si Uygulama Proxy yapılandırmasında yanlış olduğunda oluşur. Bu URL 'ye bir örnek https://contoso.com/certsrv/mscep/mscep.dll.

  **Çözüm**: uygulama ara sunucusu yapılandırmasındaki SCEP dış URL 'si için varsayılan *Yourtenant.msappproxy.net* etki alanını kullanın.

#### <a name="internal-server-error"></a>500-iç sunucu hatası

SCEP sunucu URL 'sine gözattığınızda, şu hatayı alırsınız:

![500-iç sunucu hatası](../protect/media/troubleshoot-scep-certificate-device-to-ndes/500-internal-server-error.png)

- **Neden 1**: NDES hizmet hesabı kilitli veya parolasının geçerliliği zaman aşımına uğradı.

  **Çözüm**: hesabın kilidini açın veya parolayı sıfırlayın.

- **Neden 2**: mscep-ra sertifikalarının geçerliliği dolmuştur.

  **Çözüm**: mscep-ra sertifikalarının GEÇERLILIĞI dolmuşsa NDES rolünü yeniden yükleyin veya yenı bir cep şifreleme ve Exchange kayıt aracısı (çevrimdışı istek) sertifikaları isteyin.

  Yeni sertifika istemek için aşağıdaki adımları izleyin:

  1. Sertifika yetkilisi (CA) veya veren CA 'da, Sertifika Şablonları MMC ' yi açın. Oturum açmış kullanıcının ve NDES sunucusunun CEP şifreleme ve Exchange kayıt aracısı (çevrimdışı istek) sertifika şablonlarında **okuma** ve **kaydetme** izinlerine sahip olduğundan emin olun.

  2. NDES sunucusunda, son kullanma tarihi olan sertifikaları denetleyin, **ilgili** bilgileri sertifikadan kopyalayın.

  3. **Bilgisayar hesabı**için Sertifikalar MMC 'yi açın.

  4. **Kişisel**' i genişletin, **Sertifikalar**' a sağ tıklayın ve ardından **Yeni sertifika iste** > **Tüm görevler** ' i seçin

  5. **Sertifika iste** sayfasında, **Cep şifreleme**' yi seçin, ardından **Bu sertifikaya kaydolmak için daha fazla bilgi gerekiyor. Ayarları yapılandırmak için buraya tıklayın**.

     ![CEP şifrelemeyi seçin](../protect/media/troubleshoot-scep-certificate-device-to-ndes/select-scep-encryption.png)

  6. **Sertifika özellikleri**' nde **Konu** sekmesine tıklayın, **konu adını** adım 2 sırasında topladığınız bilgilerle girin, **Ekle**' ye tıklayın ve ardından **Tamam**' a tıklayın.

  7. Sertifika kaydını doldurun.

  8. **Kullanıcı hesabım**için Sertifikalar MMC 'yi açın.

     Exchange kayıt aracısı (çevrimdışı istek) sertifikasına kaydoldığınızda, kullanıcı bağlamında yapılmalıdır. Bu sertifika şablonunun **konu türü** **Kullanıcı**olarak ayarlandığından.

  9. **Kişisel**' i genişletin, **Sertifikalar**' a sağ tıklayın ve ardından **Yeni sertifika iste** > **Tüm görevler** ' i seçin

  10. **Sertifika iste** sayfasında **Exchange kayıt aracısı (çevrimdışı istek)** öğesini seçin ve ardından **Bu sertifikaya kaydolmak için daha fazla bilgi gerekiyor. Ayarları yapılandırmak için buraya tıklayın**.

      ![Exchange kayıt aracısı seçin](../protect/media/troubleshoot-scep-certificate-device-to-ndes/select-exchange-enrollment-agent.png)

  11. **Sertifika özellikleri**' nde **Konu** sekmesine tıklayın, **konu adını** adım 2 sırasında topladığınız bilgilerle girin, **Ekle**' ye tıklayın.

      ![Sertifika özellikleri](../protect/media/troubleshoot-scep-certificate-device-to-ndes/certificate-properties.png)

      **Özel anahtar** sekmesini seçin, **özel anahtarı dışarı aktarılabilir yap**' ı seçin ve ardından **Tamam**' a tıklayın.

      ![Özel anahtar](../protect/media/troubleshoot-scep-certificate-device-to-ndes/private-key.png)

  12. Sertifika kaydını doldurun.

  13. Exchange kayıt aracısı (çevrimdışı istek) sertifikasını geçerli kullanıcı sertifika deposundan dışarı aktarın. Sertifika dışarı aktarma sihirbazında **Evet, özel anahtarı dışarı aktar**' ı seçin.

  14. Sertifikayı yerel makine sertifika deposuna aktarın.

  15. Sertifikalar MMC ' de, yeni sertifikaların her biri için aşağıdaki işlemi yapın:

      Sertifikaya sağ tıklayın, **Tüm görevler** > **özel anahtarları Yönet**' e tıklayın, NDES hizmet hesabına **Oku** izni ekleyin.

  16. IIS 'i yeniden başlatmak için **iisreset** komutunu çalıştırın.

## <a name="next-steps"></a>Sonraki adımlar

Cihaz, sertifika isteğini sunmak için NDES sunucusuna başarıyla ulaşırsa, sonraki adım [Intune sertifika bağlayıcıları ilke modülünü](troubleshoot-scep-certificate-ndes-policy-module.md)gözden geçirmeye yönelik olur.
