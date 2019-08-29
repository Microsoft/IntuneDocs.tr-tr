---
title: Microsoft Intune sertifika Bağlayıcısı ve olay kimlikleri sorunlarını giderme | Microsoft Docs
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
ms.openlocfilehash: 8a282662032fe77cbf39da279c587bff31ad9e24
ms.sourcegitcommit: cf40f641af4746a1e34edd980dc6ec96fd040126
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/28/2019
ms.locfileid: "70129556"
---
# <a name="intune-certificate-connector-events-and-diagnostic-codes"></a>Intune sertifika Bağlayıcısı olayları ve tanılama kodları

Sürüm 6.1806.x.x’ten itibaren Intune Bağlayıcısı Hizmeti, olayları **Olay Görüntüleyicisi**’nde günlüğe kaydeder (**Uygulama ve Hizmet Günlükleri** > **Microsoft Intune Bağlayıcısı**). Bu olayları, Intune Bağlayıcısı'nın yapılandırmasındaki olası sorunları gidermenize yardımcı olması için kullanın. Bu olaylar bir işlemin başarılarını ve başarısızlıklarını günlüğe kaydeder ve ayrıca BT yöneticisinin sorun gidermesine yardımcı olmak için tanılama kodlarıyla iletilerini içerir.

> [!TIP]  
> Sorunları gidermek ve Intune Bağlayıcısı kurulumunu doğrulamak için bkz. [sertifika yetkilisi betik örnekleri](https://aka.ms/intuneconnectorverificationscript).

## <a name="event-ids-and-descriptions"></a>Olay kimlikleri ve açıklamaları

| Olay Kimliği      | Olay Adı    | Olay Açıklaması | İlgili Tanılama Kodları |
| ------------- | ------------- | -------------     | -------------            |
| 10010 | StartedConnectorService  | Bağlayıcı hizmeti başlatıldı | 0x00000000, 0x0FFFFFFF |
| 10020 | StoppedConnectorService  | Bağlayıcı hizmeti durduruldu | 0x00000000, 0x0FFFFFFF |
| 10100 | CertificateRenewal_Success  | Bağlayıcı kayıt sertifikası başarıyla yenilendi | 0x00000000, 0x0FFFFFFF |
| 10102 | CertificateRenewal_Failure  | Bağlayıcı kayıt sertifikası yenilenemedi. Bağlayıcıyı yeniden yükleyin. | 0x00000000, 0x00000405, 0x0FFFFFFF |
| 10302 | RetrieveCertificate_Error  | Bağlayıcı kayıt sertifikası kayıt defterinden alınamadı. Bu olayla ilgili sertifika parmak izinin olay ayrıntılarını gözden geçirin. | 0x00000000, 0x00000404, 0x0FFFFFFF |
| 10301 | RetrieveCertificate_Warning  | Olay ayrıntılarındaki tanılama bilgilerini denetleyin. | 0x00000000, 0x00000403, 0x0FFFFFFF |
| 20100 | PkcsCertIssue_Success  | PKCS sertifikası başarıyla verildi. Bu olayla ilgili cihaz kimliği, kullanıcı kimliği, CA adı, sertifika şablonu adı ve sertifika parmak izi gibi olay ayrıntılarını gözden geçirin. | 0x00000000, 0x0FFFFFFF |
| 20102 | PkcsCertIssue_Failure  | PKCS sertifikası verilemedi. Bu olayla ilgili cihaz kimliği, kullanıcı kimliği, CA adı, sertifika şablonu adı ve sertifika parmak izi gibi olay ayrıntılarını gözden geçirin. | 0x00000000, 0x00000400, 0x00000401, 0x0FFFFFFF |
| 20200 | RevokeCert_Success  | Sertifika başarıyla iptal edildi. Bu olayla ilgili cihaz kimliği, kullanıcı kimliği, CA adı ve sertifika seri numarası gibi olay ayrıntılarını gözden geçirin. | 0x00000000, 0x0FFFFFFF |
| 20202 | RevokeCert_Failure | Sertifika iptal edilemedi. Bu olayla ilgili cihaz kimliği, kullanıcı kimliği, CA adı ve sertifika seri numarası gibi olay ayrıntılarını gözden geçirin. Ek bilgi için NDES SVC Günlükleri'ne bakın.   | 0x00000000, 0x00000402, 0x0FFFFFFF |
| 20300 | Upload_Success | Sertifikanın istek veya iptal verileri başarıyla karşıya yüklendi. Karşıya yükleme ayrıntıları için olay ayrıntılarını gözden geçirin. | 0x00000000, 0x0FFFFFFF |
| 20302 | Upload_Failure | Sertifikanın istek veya iptal verileri karşıya yüklenemedi. Hatanın hangi noktada oluştuğunu saptamak için olay ayrıntıları > Karşıya Yükleme Durumu'nu gözden geçirin.| 0x00000000, 0x0FFFFFFF |
| 20400 | Download_Success | Sertifika imzalama, istemci sertifikası indirme veya sertifika iptal etme isteği başarıyla indirildi. İndirme ayrıntıları için olay ayrıntılarını gözden geçirin.  | 0x00000000, 0x0FFFFFFF |
| 20402 | Download_Failure | Sertifika imzalama, istemci sertifikası indirme veya sertifika iptal etme isteği indirilemedi. İndirme ayrıntıları için olay ayrıntılarını gözden geçirin. | 0x00000000, 0x0FFFFFFF |
| 20500 | CRPVerifyMetric_Success  | Sertifika Kayıt Noktası istemci sınamasını başarıyla doğruladı | 0x00000000, 0x0FFFFFFF |
| 20501 | CRPVerifyMetric_Warning  | Sertifika Kayıt Noktası isteği tamamladı ama reddetti. Diğer ayrıntılar için tanılama koduna ve iletisine bakın. | 0x00000000, 0x00000411, 0x0FFFFFFF |
| 20502 | CRPVerifyMetric_Failure  | Sertifika Kayıt Noktası istemci sınamasını doğrulayamadı. Diğer ayrıntılar için tanılama koduna ve iletisine bakın. Sınamaya karşılık gelen Cihaz Kimliği için olay iletisi ayrıntılarına bakın. | 0x00000000, 0x00000408, 0x00000409, 0x00000410, 0x0FFFFFFF |
| 20600 | CRPNotifyMetric_Success  | Sertifika Kayıt Noktası bildirme işlemini başarıyla bitirdi ve sertifikayı istemci cihazına gönderdi. | 0x00000000, 0x0FFFFFFF |
| 20602 | CRPNotifyMetric_Failure  | Sertifika Kayıt Noktası bildirme işlemini bitiremedi. İstekle ilgili bilgiler için olay iletisi ayrıntılarına bakın. NDES sunucusuyla CA arasındaki bağlantıyı doğrulayın. | 0x00000000, 0x0FFFFFFF |

## <a name="diagnostic-codes"></a>Tanılama kodları

| Tanılama Kodu | Tanı Adı | Tanılama İletisi |
| -------------   | -------------   | -------------      |
| 0x00000000 | Başarılı  | Başarılı |
| 0x00000400 | PKCS_Issue_CA_Unavailable  | Sertifika yetkilisi geçerli değil veya yetkiliye ulaşılamıyor. Sertifika yetkilisinin kullanılabilir olduğunu ve sunucunuzun onunla iletişim kurabildiğini doğrulayın. |
| 0x00000401 | Symantec_ClientAuthCertNotFound  | Yerel sertifika deposunda Symantec Client Auth sertifikası bulunamadı. Daha fazla bilgi için [Symantec kayıt yetkilendirme sertifikası yükleme](https://docs.microsoft.com/intune/certificates-symantec-configure#install-the-symantec-registration-authorization-certificate) makalesine bakın.  |
| 0x00000402 | RevokeCert_AccessDenied  | Belirtilen hesabın CA'dan sertifika iptal etme izinleri yok. Veren CA'yı saptamak için olay iletisi ayrıntılarında CA Adı alanına bakın.  |
| 0x00000403 | CertThumbprint_NotFound  | Girişinizle eşleşen bir sertifika bulunamadı. Sertifika bağlayıcısının kaydını yapın ve yeniden deneyin. |
| 0x00000404 | Certificate_NotFound  | Sağlanan girişle eşleşen bir sertifika bulunamadı. Sertifika bağlayıcısının kaydını yeniden yapın ve bir kez daha deneyin. |
| 0x00000405 | Certificate_Expired  | Sertifikanın süresi doldu. Sertifikayı yenilemek için sertifika bağlayıcısının kaydını yeniden yapın ve bir kez daha deneyin. |
| 0x00000408 | CRPSCEPCert_NotFound  | CRP Şifreleme sertifikası bulunamadı. NDES ve Intune Connector'ın düzgün kurulduğunu doğrulayın. |
| 0x00000409 | CRPSCEPSigningCert_NotFound  | İmzalama sertifikası alınamadı. Intune Bağlayıcı Hizmeti'nin düzgün yapılandırıldığını ve Intune Bağlayıcı Hizmeti'nin çalıştığını doğrulayın. Ayrıca sertifika indirme olaylarının başarılı olduğunu da doğrulayın. |
| 0x00000410 | CRPSCEPDeserialize_Failed  | SCEP sınama isteği seri durumdan çıkarılamadı. NDES ile Intune Connector'ın düzgün kurulduğunu doğrulayın. |
| 0x00000411 | CRPSCEPChallenge_Expired  | Sertifika sınamasının süresi dolduğundan istek reddedildi. İstemci cihazı yönetim sunucusundan yeni bir sınama aldıktan sonra bir kez daha deneyebilir. |
| 0x0FFFFFFFF | Unknown_Error  | Bir sunucu tarafı hatası oluştuğundan isteğinizi tamamlayamadık. Lütfen yeniden deneyin. |


## <a name="next-steps"></a>Sonraki adımlar
Ek Yardım için [Microsoft Intune KıLAVUZUNDA SCEP sertifika profili dağıtımını sorun giderme](https://support.microsoft.com/help/4457481/troubleshooting-scep-certificate-profile-deployment-in-intune) ' yi kullanın.
