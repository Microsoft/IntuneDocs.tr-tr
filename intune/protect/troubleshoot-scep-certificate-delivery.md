---
title: Microsoft Intune ile SCEP kullandığınızda cihazlara sertifikaların teslimini giderme | Microsoft Docs
description: Sertifikaları dağıtmak için Intune ile SCEP sertifika profillerini kullanırken CA 'dan bir cihaza sertifika tesliminde sorun giderin.
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
ms.openlocfilehash: 40075ad3c90f9ce5131d88780d15eec5c258e276
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77515263"
---
# <a name="troubleshoot-the-delivery-of-certificates-provisioned-by-scep-to-devices-in-microsoft-intune"></a>Microsoft Intune 'daki cihazlara SCEP tarafından sağlanan sertifikaların tesliminde sorun giderme

Intune 'da sertifika sağlamak üzere Basit Sertifika Kayıt Protokolü (SCEP) kullandığınızda cihazlara sertifikaların teslimini araştırmanıza yardımcı olması için bu makaledeki bilgileri kullanın. Ağ cihazı kayıt hizmeti (NDES) sunucusu, sertifika yetkilisinden (CA) bir cihaz için istenen sertifikayı aldıktan sonra, bu sertifikayı cihaza geri geçirir.

Bu makale, [SCEP iletişim iş akışının](troubleshoot-scep-certificate-profiles.md)5. adımı için geçerlidir; sertifikayı, sertifika isteğini gönderen cihaza teslim edin.

## <a name="review-the-certification-authority"></a>Sertifika yetkilisini gözden geçirin

CA sertifikayı verildiğinde, CA 'da aşağıdaki örneğe benzer bir giriş görürsünüz:

![Verilen sertifika örneği](../protect/media/troubleshoot-scep-certificate-delivery/certificate-authority.png)

## <a name="review-the-device"></a>Cihazı gözden geçirme

### <a name="android"></a>Android

Cihaz Yöneticisi kayıtlı cihazlar için aşağıdaki görüntüye benzer bir bildirim görürsünüz ve bu da sertifikayı yüklemenizi ister:

![Android bildirimi](../protect/media/troubleshoot-scep-certificate-delivery/android-notification.png)

Android Enterprise veya Samsung Knox için, sertifika yüklemesi otomatiktir ve sessiz olur.

Android 'de yüklü bir sertifikayı görüntülemek için 3. taraf sertifika görüntüleme uygulamasını kullanın.

[CIHAZLAR OMADM günlüğünü](troubleshoot-scep-certificate-profiles.md#logs-for-android-devices)de gözden geçirebilirsiniz. Sertifikaların yüklemesi sırasında günlüğe kaydedilen aşağıdakine benzer girdileri arayın:

**Kök sertifika**:

```
2018-02-27T04:50:52.1890000    INFO    Event     com.microsoft.omadm.platforms.android.certmgr.state.NativeRootCertInstallStateMachine     9595        9    Root cert '17…' state changed from CERT_INSTALL_REQUESTED to CERT_INSTALL_REQUESTED
2018-02-27T04:53:31.1300000    INFO    Event     com.microsoft.omadm.platforms.android.certmgr.state.NativeRootCertInstallStateMachine     9595        0    Root cert '17…' state changed from CERT_INSTALL_REQUESTED to CERT_INSTALLING
2018-02-27T04:53:32.0390000    INFO    Event     com.microsoft.omadm.platforms.android.certmgr.state.NativeRootCertInstallStateMachine     9595       14    Root cert '17…' state changed from CERT_INSTALLING to CERT_INSTALL_SUCCESS
```

**SCEP aracılığıyla sağlanan sertifika**

```
2018-02-27T05:16:08.2500000    VERB    Event     com.microsoft.omadm.platforms.android.certmgr.CertificateEnrollmentManager    18327       10    There are 1 requests
2018-02-27T05:16:08.2500000    VERB    Event     com.microsoft.omadm.platforms.android.certmgr.CertificateEnrollmentManager    18327       10    Trying to enroll certificate request: ModelName=AC_51…%2FLogicalName_39907…;Hash=1677525787
2018-02-27T05:16:20.6150000    VERB    Event     org.jscep.transport.UrlConnectionGetTransport    18327       10    Sending GetCACert(ca) to https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACert&message=ca
2018-02-27T05:16:20.6530000    VERB    Event     org.jscep.transport.UrlConnectionGetTransport    18327       10    Received '200 OK' when sending GetCACert(ca) to https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACert&message=ca
2018-02-27T05:16:21.7460000    VERB    Event     org.jscep.transport.UrlConnectionGetTransport    18327       10    Sending GetCACaps(ca) to https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACaps&message=ca
2018-02-27T05:16:21.7890000    VERB    Event     org.jscep.transport.UrlConnectionGetTransport    18327       10    Received '200 OK' when sending GetCACaps(ca) to https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACaps&message=ca
2018-02-27T05:16:28.0340000    VERB    Event     org.jscep.transaction.EnrollmentTransaction    18327       10    Response: org.jscep.message.CertRep@3150777b[failInfo=<null>,pkiStatus=SUCCESS,recipientNonce=Nonce [GUID],messageData=org.spongycastle.cms.CMSSignedData@27cc8998,messageType=CERT_REP,senderNonce=Nonce [GUID],transId=TRANSID]
2018-02-27T05:16:28.2440000    INFO    Event     com.microsoft.omadm.platforms.android.certmgr.state.NativeScepCertInstallStateMachine    18327       10    SCEP cert 'ModelName=AC_51…%2FLogicalName_39907…;Hash=1677525787' state changed from CERT_ENROLLED to CERT_INSTALL_REQUESTED
2018-02-27T05:18:44.9820000    INFO    Event     com.microsoft.omadm.platforms.android.certmgr.state.NativeScepCertInstallStateMachine    18327        0    SCEP cert 'ModelName=AC_51…%2FLogicalName_39907…;Hash=1677525787' state changed from CERT_INSTALL_REQUESTED to CERT_INSTALLING
2018-02-27T05:18:45.3460000    INFO    Event     com.microsoft.omadm.platforms.android.certmgr.state.NativeScepCertInstallStateMachine    18327       14    SCEP cert 'ModelName=AC_51…%2FLogicalName_39907…;Hash=1677525787' state changed from CERT_INSTALLING to CERT_ACCESS_REQUESTED
2018-02-27T05:20:15.3520000    INFO    Event     com.microsoft.omadm.platforms.android.certmgr.state.NativeScepCertInstallStateMachine    18327       21    SCEP cert 'ModelName=AC_51…%2FLogicalName_39907…;Hash=1677525787' state changed from CERT_ACCESS_REQUESTED to CERT_ACCESS_GRANTED
```

### <a name="iosipados"></a>iOS/ıpados

İOS/ıpados veya ıpados cihazında, sertifikayı cihaz yönetimi profili altında görebilirsiniz. Yüklü sertifikalara ilişkin ayrıntıları görmek için ayrıntıya gidin.

![iOS sertifikası](../protect/media/troubleshoot-scep-certificate-delivery/ios-certificate.png)

[İOS hata ayıklama günlüğünde](troubleshoot-scep-certificate-profiles.md#logs-for-ios-and-ipados-devices)aşağıdakine benzer girdileri de bulabilirsiniz:

```
Debug 18:30:53.691033 -0500 profiled Performing synchronous URL request: https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACert&message=SCEP%20Authority\  
Debug 18:30:54.640644 -0500 profiled Performing synchronous URL request: https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACaps&message=SCEP%20Authority\ 
Debug 18:30:55.487908 -0500 profiled Performing synchronous URL request: https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=PKIOperation&message=MIAGCSqGSIb3DQEHAqCAMIACAQExDzANBglghkgBZQMEAgMFADCABgkqhkiG9w0BBwGggCSABIIZfzCABgkqhkiG9w0BBwOggDCAAgEAMYIBgjCCAX4CAQAwZjBPMRUwEwYKCZImiZPyLGQBGRYFbG9jYWwxHDAaBgoJkiaJk/IsZAEZFgxmb3VydGhjb2ZmZWUxGDAWBgNVBAMTD0ZvdXJ0aENvZmZlZSBDQQITaAAAAAmaneVjEPlcTwAAAAAACTANBgkqhkiG9w0BAQEFAASCAQCqfsOYpuBToerQLkw/tl4tH9E+97TBTjGQN9NCjSgb78fF6edY0pNDU+PH4RB356wv3rfZi5IiNrVu5Od4k6uK4w0582ZM2n8NJFRY7KWSNHsmTIWlo/Vcr4laAtq5rw+CygaYcefptcaamkjdLj07e/Uk4KsetGo7ztPVjSEFwfRIfKv474dLDmPqp0ZwEWRQG 
Debug 18:30:57.285730 -0500 profiled Adding dependent Microsoft.Profiles.MDM to parent www.windowsintune.com.SCEP.ModelName=AC_51bad41f.../LogicalName_1892fe4c...;Hash=-912418295 in domain ManagedProfileToManagingProfile to system\ 
Default 18:30:57.320616 -0500 profiled Profile \'93www.windowsintune.com.SCEP.ModelName=AC_51bad41f.../LogicalName_1892fe4c...;Hash=-912418295\'94 installed.\ 
```

### <a name="windows"></a>Windows

Windows cihazında, sertifikanın teslim edildiğini doğrulayın:

- Olay Görüntüleyicisi açmak için **eventvwr. msc** ' i çalıştırın. **Microsoft** > **Windows** > **DeviceManagement-Enterprise-Diagnostic-Provider** > **admin** > **uygulamalar ve hizmetler günlüklerine** gidin ve **olay 39**' i arayın. Bu olay için genel bir açıklama olmalıdır: **SCEP: sertifika başarıyla yüklendi.**

   ![Windows uygulama günlüğünde olay 39](../protect/media/troubleshoot-scep-certificate-delivery/device-app-log.png)

Cihazdaki sertifikayı görüntülemek için, Sertifikalar MMC 'yi açmak üzere **certmgr. msc** ' yi çalıştırın ve kök ve SCEP sertifikalarının kişisel depodaki cihaza doğru şekilde yüklendiğini doğrulayın:

   1. Sertifikalar **(yerel bilgisayar)**  > **Güvenilen kök sertifika yetkilileri** > **SERTIFIKALARı**' na gidin ve CA 'nızdan kök sertifikanın mevcut olduğunu doğrulayın. *Verilen* ve *veren* değerleri aynı olacaktır.
   2. Sertifikalar MMC ' de, **sertifikalar – geçerli kullanıcı** > **Kişisel** > **sertifikaları**' na gidin ve Istenen sertifikanın, CA adına eşit *olarak verilmiş* olduğunu doğrulayın.

## <a name="troubleshoot-failures"></a>Sorun giderme hataları

### <a name="android"></a>Android

Bu adımı gidermek için, OMA DM günlüğünde günlüğe kaydedilen hataları gözden geçirin.

### <a name="iosipados"></a>iOS/ıpados

Bu adımı gidermek için, cihazlar hata ayıklama günlüğünde günlüğe kaydedilen hataları gözden geçirin.

### <a name="windows"></a>Windows

Cihazda yüklü olmayan sorunları gidermek için, sorun öneren hatalar için Windows olay günlüğü 'ne bakın:

- Cihazda, Olay Görüntüleyicisi açmak için **eventvwr. msc** ' yi çalıştırın ve ardından **Microsoft** > **Windows** > **DeviceManagement-Enterprise-Diagnostic-Provider** > **admin** > **uygulamalar ve hizmetler günlüklerine** gidin.

Sertifikayı cihaza teslim ve yükleme ile ilgili hatalar genellikle Intune 'a değil, Windows işlemleri ile ilgilidir.

## <a name="next-steps"></a>Sonraki adımlar

Sertifika başarıyla cihaza dağıttığında, ancak Intune başarılı olarak bildirilmezse, bkz. Raporlama sorunlarını gidermek için [Intune 'A NDES raporlaması](troubleshoot-scep-certificate-reporting.md) .
