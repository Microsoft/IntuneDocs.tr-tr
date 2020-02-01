---
title: Microsoft Intune Sertifika Bağlayıcısı ilke modülünün sorunlarını giderme | Microsoft Docs
description: Intune ile sertifika dağıtmak için SCEP sertifika profillerini kullandığınızda modül bir sertifika isteğini işlediğinde, NDES ilke modülünün işleminde sorun giderin.
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
ms.openlocfilehash: be53f6102226b004cab2bd953357e8c360a00f67
ms.sourcegitcommit: c46b0c2d4507be6a2786a4ea06009b2d5aafef85
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/01/2020
ms.locfileid: "76913186"
---
# <a name="troubleshoot-the-ndes-policy-module-in-microsoft-intune"></a>Microsoft Intune 'de NDES ilke modülünün sorunlarını giderme

Bu makaledeki bilgiler, Microsoft Intune Sertifika Bağlayıcısı yüklenen ağ cihazı kayıt hizmeti (NDES) ilke modülünün işlemini doğrulamanıza yardımcı olabilir. NDES bir sertifika için bir istek aldığında, isteği cihaz için geçerli olarak doğrulayan ilke modülüne iletir. Doğrulamadan sonra NDES, sertifikayı cihaz adına istemek için sertifika yetkilisi (CA) ile iletişim kurar.

Bu makale, hem 3. adım hem de [SCEP iletişim iş akışının](troubleshoot-scep-certificate-profiles.md)4. adımı için geçerlidir.

## <a name="ndes-communication-to-the-policy-module"></a>İlke modülüyle NDES iletişimi

Bir cihazdan sertifika isteği aldıktan sonra, NDES bu isteği Microsoft Intune Sertifika Bağlayıcısı ile yüklenen ilke modülü aracılığıyla Intune ile doğrular. Bu girişler, *sertifika kayıt noktasına*başvurur.

**Başarıyı belirten günlük girişleri**:

Doğrulama isteğinin modüle gönderildiğini onaylamak için NDES sunucusu 'ndaki günlüklerde aşağıdaki örneklere benzer bir giriş arayın:

- **IIS günlükleri**:

  ```
  fe80::f53d:89b8:c3e8:5fec%13 POST /CertificateRegistrationSvc/Certificate/VerifyRequest - 443 - 
  fe80::f53d:89b8:c3e8:5fec%13 NDES_Plugin - 201 0 0 341 875
  ```

- **NDESPlugin günlüğü**:

  ```
  Calling VerifyRequest ...  
  Sending request to certificate registration point.
  ```

  Aşağıdaki örnek, cihazların sınama isteğinin başarılı bir şekilde doğrulanmasını ve NDES 'in artık CA ile bağlantı kurabildiğini gösterir:

  ```
  Verify challenge returns true
  Exiting VerifyRequest with 0x0
  ```

- **Certificateregistrationpoint. svclog**:

  `Validation Phase 1 finished with status True.`  
  `Validation Phase 3 finished with status True.`  
  `VerifyRequest Finished with status True`


**Başarı göstergeleri mevcut olmadığında**:

Bu girdileri bulamazsanız, [CIHAZDAN NDES sunucu iletişimine](troubleshoot-scep-certificate-device-to-ndes.md#troubleshoot-common-errors)yönelik sorun giderme kılavuzunu inceleyerek başlayın.

Bu makaledeki bilgiler sorunu çözmenize yardımcı değilse, aşağıdaki ek girişler sorunları belirtebilirler.

### <a name="ndespluginlog-contains-an-error-12175"></a>NDESPlugin. log bir hata 12175 içerir

Günlük, aşağıdakine benzer bir 12175 hatası içerdiğinde, SSL sertifikasıyla ilgili bir sorun olabilir:

```
WINHTTP_CALLBACK_STATUS_FLAG_CERT_CN_INVALID
Failed to send http request /CertificateRegistrationSvc/Certificate/VerifyRequest. Error 12175
```

Mobil cihazlardaki modern tarayıcılar ve tarayıcılar, *konu alternatif adları* varsa bir SSL sertifikasındaki *ortak adı* yoksayar.

**Çözüm**: Web sunucusu SSL sertifikasını *ortak ad* ve *konu alternatif adı*IÇIN aşağıdaki özniteliklerle verin ve ardından IIS 'de 443 numaralı bağlantı noktasına bağlayın:

  - **Konu adı**  
    CN = dış sunucu adı
  - **Konu diğer adı**  
     Ad = dış sunucu adı  
     DNS adı = iç sunucu adı

### <a name="ndespluginlog-contains-an-error-403--forbidden-access-is-denied"></a>NDESPlugin. log bir hata içeriyor 403 – Yasak: erişim reddedildi "

Aşağıdaki Günlükler aşağıdakine benzer bir 403 hatası içerdiğinde, istemci sertifikası güvenilir değil veya geçersiz olabilir:

**NDESPlugin. log**:

```
Sending request to certificate registration point.
Verify challenge returns <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd"> <html xmlns="http://www.w3.org/1999/xhtml"> <head><meta http-equiv="Content-Type" content="text/html; charset=iso-8859-1"/>
<title>403 - Forbidden: Access is denied.</title>
```

**IIS günlüğü**:

```
POST /CertificateRegistrationSvc/Certificate/VerifyRequest - 443 -<IP_address>
NDES_Plugin - 403 16 2148204809 453  
```

Bu sorun, NDES sunucusunun Güvenilen kök sertifika yetkilileri sertifika deposunda ara CA sertifikaları varsa oluşur.

Bir sertifika, değerleri tarafından *verilen* ve *verilen* değerlere sahipse, kök bir sertifikadır. Aksi takdirde, bu bir ara sertifikadır.

**Çözüm**: sorunu çözmek Için, güvenilen kök sertifika yetkilileri sertifika DEPOSUNDAN ara CA sertifikalarını tanımlayıp kaldırın.

### <a name="ndespluginlog-indicates-the-challenge-returns-false"></a>NDESPlugin. log, Challenge 'ın false döndürdüğünü gösterir

Sınama sonucu **yanlış**döndürdüğünde, hatalar Için *Certificateregistrationpoint. svclog dosyasına* bakın. Örneğin, aşağıdaki girdiye benzer bir "Imza sertifikası alınamadı" hatası görebilirsiniz:

```
Signing certificate could not be retrieved. System.Security.Cryptography.CryptographicException: m_safeCertContext is an invalid handle. at System.Security.Cryptography.X509Certificates.X509Certificate.ThrowIfContextInvalid() at System.Security.Cryptography.X509Certificates.X509Certificate.GetCertHashString() at Microsoft.ConfigurationManager.CertRegPoint.CRPCertificate.RetrieveSigningCert(String certThumbprint
```

**Çözüm**: bağlayıcının yüklü olduğu sunucuda, kayıt defteri düzenleyicisini açın, `HKLM\SOFTWARE\Microsoft\MicrosoftIntune\NDESConnector` kayıt defteri anahtarını bulun ve ardından SigningCertificate değerinin var olup olmadığını denetleyin.

Bu değer yoksa, Services. msc ' de Intune Bağlayıcısı hizmetini yeniden başlatın ve değerin kayıt defterinde görünüp görüntülenmediğini denetleyin. Değer hala eksikse, genellikle NDES ve Intune hizmeti arasındaki ağ bağlantısı sorunlarından kaynaklanır.

## <a name="ndes-passes-the-request-to-issue-the-certificate"></a>NDES sertifikayı verme isteğini geçirir

Sertifika kayıt noktası (ilke modülü) tarafından başarılı bir doğrulamasından sonra NDES, sertifika isteğini cihaz adına CA 'ya geçirir.

**Başarıyı belirten günlük girişleri**:

- **NDESPlugin günlüğü**:

  ```
  Verify challenge returns true
  Exiting VerifyRequest with 0x0
  ```

- **IIS günlükleri**:

  ```
  fe80::f53d:89b8:c3e8:5fec%13 GET /certsrv/mscep/mscep.dll/pkiclient.exe ... 80 - 
  fe80::f53d:89b8:c3e8:5fec%13 Mozilla/4.0+(compatible;+Win32;+NDES+client) - 200 0 0 2713 1296
  ```

- **Certificateregistrationpoint. svclog**:

  `Validation Phase 1 finished with status True.`  
  `Validation Phase 3 finished with status True.`  
  `VerifyRequest Finished with status True`

**Başarı göstergeleri mevcut olmadığında**:

Başarıyı belirten girişleri görmüyorsanız, şu adımları izleyin:

1. Sertifika kayıt noktası sınamayı doğruladığında, *Certificateregistrationpoint. svclog* dosyasında günlüğe kaydedilen sorunları arayın. Aşağıdaki satırlar arasındaki girdileri arayın:

   - VerifyRequest başladı.
   - VerifyRequest, false durumuyla tamamlandı

2. Sertifika yetkilisi MMC 'yi CA 'da açın ve bir sorunu belirlemesine yardımcı olan hataları aramak için **başarısız istekleri** seçin. Aşağıdaki resim bir örnektir:

   ![Başarısız istek örneği](../protect/media/troubleshoot-scep-certificate-ndes-policy-module/failed-requests.png)

3. Hatalar için CA 'da uygulama olay günlüğünü gözden geçirin. Genellikle, önceki adımda **başarısız isteklerde** gördükleriniz ile eşleşen hataları görebilirsiniz. Aşağıdaki resim bir örnektir:

   ![Uygulama günlüğünü gözden geçirin](../protect/media/troubleshoot-scep-certificate-ndes-policy-module/application-log-errors.png)

## <a name="next-steps"></a>Sonraki adımlar

NDES ilke modülü isteği doğrulayıp istek sertifika yetkilisine iletilirse, sonraki adım [cihaza sertifika teslimini](troubleshoot-scep-certificate-delivery.md)gözden geçirmekte olur.
