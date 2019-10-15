---
title: Microsoft Intune sertifika Bağlayıcısı ve olay kimlikleri sorunlarını giderme | Microsoft Docs
titleSuffix: Microsoft Intune
description: Olay kimliklerini ve açıklamalarını inceleyerek Microsoft Intune sertifika Bağlayıcısı sorunlarını giderin ve Intune Bağlayıcısı hizmeti için tanılama kodlarını gözden geçirin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 05/01/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2d798f22ee4e0f11f46626eec01ad3b739d61467
ms.sourcegitcommit: dd6755383ba89824d1cc128698a65fde6bb2de55
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/14/2019
ms.locfileid: "72306717"
---
# <a name="intune-certificate-connector-events-and-diagnostic-codes"></a>Intune sertifika Bağlayıcısı olayları ve tanılama kodları

6\.1806. x. x sürümünden itibaren, Intune bağlayıcı hizmeti **Olay Görüntüleyicisi** (**uygulama ve hizmet günlükleri** > **Microsoft Intune Bağlayıcısı**) olayları günlüğe kaydeder. Intune bağlayıcısının yapılandırmasındaki olası sorunları gidermeye yardımcı olması için bu olayları kullanın. Bu olaylar, bir işlemin başarıları ve başarısızlıklarını günlüğe kaydeder ve BT yöneticisinin sorun gidermelerine yardımcı olmak için iletilerle birlikte tanılama kodları içerir.

> [!TIP]  
> Sorunları gidermek ve Intune Bağlayıcısı kurulumunu doğrulamak için bkz. [sertifika yetkilisi betik örnekleri](https://aka.ms/intuneconnectorverificationscript).

## <a name="event-ids-and-descriptions"></a>Olay kimlikleri ve açıklamaları

| Olay KIMLIĞI      | Olay adı    | Olay açıklaması | İlgili tanılama kodları |
| ------------- | ------------- | -------------     | -------------            |
| 10010 | StartedConnectorService  | Bağlayıcı hizmeti başlatıldı | 0x00000000, 0x0FFFFFFF |
| 10020 | StoppedConnectorService  | Bağlayıcı hizmeti durdu | 0x00000000, 0x0FFFFFFF |
| 10100 | CertificateRenewal_Success  | Bağlayıcı kayıt sertifikası başarıyla yenilendi | 0x00000000, 0x0FFFFFFF |
| 10102 | CertificateRenewal_Failure  | Bağlayıcı kayıt sertifikası yenilenemedi. Bağlayıcıyı yeniden yükleyin. | 0x00000000, 0x00000405, 0x0FFFFFFF |
| 10302 | RetrieveCertificate_Error  | Bağlayıcı kayıt sertifikası kayıt defterinden alınamadı. Bu olayla ilgili sertifika parmak izi için olay ayrıntılarını gözden geçirin. | 0x00000000, 0x00000404, 0x0FFFFFFF |
| 10301 | RetrieveCertificate_Warning  | Olay ayrıntılarında tanılama bilgilerini denetleyin. | 0x00000000, 0x00000403, 0x0FFFFFFF |
| 20100 | PkcsCertIssue_Success  | PKCS sertifikası başarıyla verildi. Cihaz KIMLIĞI, Kullanıcı KIMLIĞI, CA adı, sertifika şablonu adı ve bu olayla ilgili sertifika parmak izi için olay ayrıntılarını gözden geçirin. | 0x00000000, 0x0FFFFFFF |
| 20102 | PkcsCertIssue_Failure  | PKCS sertifikası verilemedi. Cihaz KIMLIĞI, Kullanıcı KIMLIĞI, CA adı, sertifika şablonu adı ve bu olayla ilgili sertifika parmak izi için olay ayrıntılarını gözden geçirin. | 0x00000000, 0x00000400, 0x00000401, 0x0FFFFFFF |
| 20200 | RevokeCert_Success  | Sertifika başarıyla iptal edildi. Bu olayla ilgili cihaz KIMLIĞI, Kullanıcı KIMLIĞI, CA adı ve sertifika seri numarası için olay ayrıntılarını gözden geçirin. | 0x00000000, 0x0FFFFFFF |
| 20202 | RevokeCert_Failure | Sertifika iptal edilemedi. Bu olayla ilgili cihaz KIMLIĞI, Kullanıcı KIMLIĞI, CA adı ve sertifika seri numarası için olay ayrıntılarını gözden geçirin. Daha fazla bilgi için NDES SVC günlüklerine bakın.   | 0x00000000, 0x00000402, 0x0FFFFFFF |
| 20300 | Upload_Success | Sertifikanın isteği veya iptal verileri başarıyla karşıya yüklendi. Karşıya yükleme ayrıntılarının olay ayrıntılarını gözden geçirin. | 0x00000000, 0x0FFFFFFF |
| 20302 | Upload_Failure | Sertifikanın isteği veya iptal verileri karşıya yüklenemedi. Hata noktasını anlamak için karşıya yükleme durumunu > Olay ayrıntılarını gözden geçirin.| 0x00000000, 0x0FFFFFFF |
| 20400 | Download_Success | Sertifikayı imzalama, istemci sertifikası indirme veya sertifikayı iptal etme isteği başarıyla indirildi. İndirme ayrıntılarının olay ayrıntılarını gözden geçirin.  | 0x00000000, 0x0FFFFFFF |
| 20402 | Download_Failure | Sertifikayı imzalama, istemci sertifikası indirme veya sertifikayı iptal etme isteği indirilemedi. İndirme ayrıntılarının olay ayrıntılarını gözden geçirin. | 0x00000000, 0x0FFFFFFF |
| 20500 | CRPVerifyMetric_Success  | Sertifika kayıt noktası istemci sınamasını başarıyla doğruladı | 0x00000000, 0x0FFFFFFF |
| 20501 | CRPVerifyMetric_Warning  | Sertifika kayıt noktası tamamlandı, ancak isteği reddetti. Daha fazla ayrıntı için bkz. tanılama kodu ve iletisi. | 0x00000000, 0x00000411, 0x0FFFFFFF |
| 20502 | CRPVerifyMetric_Failure  | Sertifika kayıt noktası istemci sınamasını doğrulayamadı. Daha fazla ayrıntı için bkz. tanılama kodu ve iletisi. Güçlük ilgili cihaz KIMLIĞI için olay iletisi ayrıntılarına bakın. | 0x00000000, 0x00000408, 0x00000409, 0x00000410, 0x0FFFFFFF |
| 20600 | CRPNotifyMetric_Success  | Sertifika kayıt noktası, bildirim işlemini başarıyla tamamladı ve sertifikayı istemci cihazına gönderdi. | 0x00000000, 0x0FFFFFFF |
| 20602 | CRPNotifyMetric_Failure  | Sertifika kayıt noktası, bildirim işlemini tamamlayamadı. İstek hakkında bilgi için olay iletisi ayrıntılarına bakın. NDES sunucusu ile CA arasındaki bağlantıyı doğrulayın. | 0x00000000, 0x0FFFFFFF |

## <a name="diagnostic-codes"></a>Tanılama kodları

| Tanılama kodu | Tanılama adı | Tanılama Iletisi |
| -------------   | -------------   | -------------      |
| 0xC0000 | Başarılı  | Başarılı |
| 0x00000400 | PKCS_Issue_CA_Unavailable  | Sertifika yetkilisi geçerli değil veya ulaşılamaz durumda. Sertifika yetkilisinin kullanılabilir olduğunu ve sunucunuzun onunla iletişim kurabildiğini doğrulayın. |
| 0x00000401 | Symantec_ClientAuthCertNotFound  | Symantec Istemci kimlik doğrulama sertifikası yerel sertifika deposunda bulunamadı. Daha fazla bilgi için [Symantec kayıt yetkilendirme sertifikasını yüklemeyin](certificates-digicert-configure.md#install-the-digicert-ra-certificate) makalesine bakın.  |
| 0x00000402 | RevokeCert_AccessDenied  | Belirtilen hesabın CA 'dan bir sertifikayı iptal etme izni yok. Sertifika veren CA 'yı öğrenmek için olay iletisi ayrıntılarında CA adı alanına bakın.  |
| 0x00000403 | CertThumbprint_NotFound  | Girişten eşleşen bir sertifika bulunamadı. Sertifika bağlayıcısını kaydedin ve yeniden deneyin. |
| 0x00000404 | Certificate_NotFound  | Sağlanan girişle eşleşen bir sertifika bulunamadı. Sertifika bağlayıcısını yeniden kaydedin ve yeniden deneyin. |
| 0x00000405 | Certificate_Expired  | Sertifika zaman aşımına uğradı. Sertifikayı yenilemek için sertifika bağlayıcısını yeniden kaydedin ve yeniden deneyin. |
| 0x00000408 | CRPSCEPCert_NotFound  | CRP şifreleme sertifikası bulunamadı. NDES ve Intune bağlayıcısının doğru şekilde ayarlandığından emin olun. |
| 0x00000409 | CRPSCEPSigningCert_NotFound  | İmza sertifikası alınamadı. Intune Bağlayıcısı hizmetinin doğru şekilde yapılandırıldığını ve Intune Bağlayıcısı hizmetinin çalıştığını doğrulayın. Ayrıca sertifika indirme olaylarının başarılı olduğunu doğrulayın. |
| 0x00000410 | CRPSCEPDeserialize_Failed  | SCEP sınama isteğinin serisi kaldırılamadı. NDES ve Intune bağlayıcısının doğru şekilde ayarlandığından emin olun. |
| 0x00000411 | CRPSCEPChallenge_Expired  | Süresi dolan sertifika sınaması nedeniyle istek reddedildi. İstemci cihaz, yönetim sunucusundan yeni bir sınama elde ettikten sonra yeniden deneyebilir. |
| 0x0FFFFFFFF | Unknown_Error  | Sunucu tarafı hatası oluştuğundan isteğinizi tamamlayamıyoruz. Lütfen yeniden deneyin. |


## <a name="next-steps"></a>Sonraki adımlar
Ek Yardım için [Microsoft Intune KıLAVUZUNDA SCEP sertifika profili dağıtımını sorun giderme](https://support.microsoft.com/help/4457481/troubleshooting-scep-certificate-profile-deployment-in-intune) ' yi kullanın.
