---
title: Microsoft Intune ile SCEP kullandığınızda cihazlara başarılı sertifika dağıtımının bildirilmesinde sorun giderme | Microsoft Docs
description: NDES ile ilgili olarak raporlama ile Intune 'a bağlayıcı ve SCEP sertifika profilleri ile sağlanan başarılı bir sertifika dağıtımı hakkında sorun giderin.
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
ms.openlocfilehash: 2ccc738626efc140efca46d1b997164ed36dd37f
ms.sourcegitcommit: c46b0c2d4507be6a2786a4ea06009b2d5aafef85
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/01/2020
ms.locfileid: "76913242"
---
# <a name="troubleshoot-ndes-reporting-of-certificate-deployments-in-microsoft-intune"></a>Microsoft Intune 'de sertifika dağıtımlarının NDES raporlaması sorunlarını giderme

NDES 'nin bir cihaza gönderildiği ve Microsoft Intune Sertifika Bağlayıcısı Intune 'a başarıyla rapor edildiğini onaylamak için aşağıdaki bilgileri kullanın. Intune 'a raporlama, bir sertifika ile Windows cihazları sağlamak için SCEP Sertifika profillerinin kullanılmasına yönelik son aşamadır.

Bu makale, [SCEP iletişim iş akışının](troubleshoot-scep-certificate-profiles.md)6. adımı için geçerlidir.

## <a name="review-for-signs-of-successful-reporting"></a>Başarılı raporlama belirtileri için gözden geçirme

Raporlama başarılı olduysa, NDES sunucusunda aşağıdaki örneklere benzer girişler bulacaksınız:

- **IIS günlüğü**:

  `fe80::f53d:89b8:c3e8:5fec%13 POST /CertificateRegistrationSvc/Certificate/Notify - 443 - fe80::f53d:89b8:c3e8:5fec%13 NDES_Plugin - 204 0 0 277 62`

- **NDESPlugin. log**:

  ```
  Calling Notifyrequest ...
  Sending request to certificate registration point.
  Exiting Notify with 0x0
  ```

- **Certificateregistrationpoint. svclog**:

  ![Intune sertifika Bağlayıcısı günlüğü](../protect/media/troubleshoot-scep-certificate-reporting/certificate-registration-point-log.png)

- **Ndesconnector. svclog**:

  ![Intune sertifika Bağlayıcısı günlüğü](../protect/media/troubleshoot-scep-certificate-reporting/ndesconnector-log.png)

- **Certificaterequeststatus**:

  Sertifika isteği durum dosyalarını içeren **başarısız**, **işleme**ve **başarılı** klasörleri görebileceğiniz *%ProgramFiles%\Microsoft ıntune\certificaterequeststatus* klasörüne gidin.

  Sertifika isteği başarıyla işleniyorsa, **başarılı** klasörde yeni dosyalar görürsünüz. *Notepad. exe* ' yi kullanarak dosyaları açabilir ve Intune sertifika Bağlayıcısı tarafından Intune hizmetine yüklenen verileri görüntüleyebilirsiniz. Karşıya yüklenen veriler **Certificateserialnumber**, **UserID**, **DeviceID**ve **parmak izi**gibi ayrıntıları içerir.

### <a name="troubleshoot-stuck-files"></a>Takılı dosya sorunlarını giderme

*Başarılı* klasöründe oluşturulan yeni dosyaları görmüyorsanız, *işleme* klasöründe takılı herhangi bir dosya olup olmadığını kontrol edin.

NDES sunucusunda Intune Bağlayıcısı hizmetinin başlatıldığını ve Ndesconnector. svclog dosyasında hata olmadığını doğrulayın.

## <a name="next-steps"></a>Sonraki adımlar

[Microsoft Intune için destek alma](../fundamentals/get-support.md)
