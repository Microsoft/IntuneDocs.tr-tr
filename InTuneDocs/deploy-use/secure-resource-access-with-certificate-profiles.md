---
title: "Kaynak erişimi için sertifika profilleri |Microsoft Intune"
description: "Her kullanıcı cihazına yüklenen bir sertifikayla Güvenli VPN, Wi-Fi ve e-posta erişimi."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 11/23/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8cbb8499-611d-4217-a7b4-e9b864785dd0
ms.reviewer: kmyrup
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 35d08100b4332cc63667a401143c17972225a908
ms.openlocfilehash: b64260fd44e5c3fd0fb80e0dab4d75bd5c4eb305


---

# <a name="secure-resource-access-with-certificate-profiles-in-microsoft-intune"></a>Microsoft Intune’da sertifika profilleriyle güvenli kaynak erişimi
VPN, Wi-Fi veya e-posta profilleri aracılığıyla kullanıcılara şirket kaynaklarına erişim izni verdiğinizde, her kullanıcı cihazında yüklü bir sertifika kullanarak erişim güvenliğini sağlayabilirsiniz. Şu şekilde çalışır:

1. [Sertifika altyapısını SCEP için yapılandırma](configure-certificate-infrastructure-for-scep.md) ve [Sertifika altyapısını PFX için yapılandırma](configure-certificate-infrastructure-for-pfx.md) konuları altında açıklandığı gibi, doğru sertifika altyapısına sahip olduğunuzdan emin olun.

2. Her cihaza bir kök sertifika veya ara Sertifika Yetkilisi (CA) sertifikası yükleyerek cihazın Sertifika Yetkilinizin meşruluğunu tanımasını sağlayın. Bunu yapmak için **Güvenilen Sertifika Profili** oluşturun ve dağıtın. Bu profili dağıttığınızda Intune ile yönettiğiniz cihazlar kök sertifikayı ister ve alır. Her platform için ayrı bir profil oluşturmanız gerekir. Şu platformlar için **Güvenilen Sertifika Profili** sağlanır:
 -  iOS 8.0 ve üzeri
 -  Mac OS X 10.9 ve üzeri
 -  Android 4.0 ve üzeri
 -  Android for Work
 -  Windows 8.1 ve üzeri
 -  Windows Phone 8.1 ve üzeri

[!INCLUDE[wit_nextref](../includes/afw_rollout_disclaimer.md)]

3. [Intune sertifika profillerini yapılandırma](configure-intune-certificate-profiles.md) konusunda açıklandığı gibi, cihazların VPN, Wi-Fi ve e-posta erişimi kimlik doğrulaması için kullanılacak bir sertifika istemelerini sağlamak için sertifika profilleri oluşturun. Aşağıdaki platformları çalıştıran cihazlar için **PKCS #12 (.PFX) Sertifika Profili** *veya* **SCEP Sertifika Profili** oluşturabilir ve dağıtabilirsiniz:

  -  iOS 8.0 ve üzeri
  -  Android 4.0 ve üzeri
  -  Android for Work
  -  Windows 10 (masaüstü ve Mobile) ve üzeri

  Aşağıdaki platformları çalıştıran cihazlar için bir **SCEP Sertifika Profili** kullanın:
    -   Mac OS X 10.9 ve üzeri
    -   Windows Phone 8.1 

Her platform için ayrı profil oluşturmanız gerekir. Profili oluştururken daha önce oluşturduğunuz **Güvenilen Kök Sertifika Profili** ile ilişkilendirin.

> [!NOTE]           
> - Kuruluş Sertifika Yetkiliniz yoksa oluşturmanız gerekir.
>- Cihaz platformlarınıza bağlı olarak Basitleştirilmiş Sertifika Kayıt Protokolü (SCEP) profili kullanmaya karar verirseniz ayrıca bir Ağ Cihazı Kayıt Hizmeti (NDES) sunucusunu yapılandırmanız gerekir.
>-  SCEP veya .PFX profilleri kullanmayı planlıyorsanız Microsoft Intune Sertifika Bağlayıcısı'nı indirip yapılandırmanız gerekir.
>-  Tüm gerekli hizmetlerin nasıl yapılandırılacağını [SCEP için sertifika altyapısını yapılandırma](configure-certificate-infrastructure-for-scep.md) veya [PFX için sertifika altyapısını yapılandırma](configure-certificate-infrastructure-for-pfx.md) konularında öğrenebilirsiniz.

### <a name="next-steps"></a>Sonraki adımlar
- [SCEP için sertifika altyapısını yapılandırma](configure-certificate-infrastructure-for-scep.md)
- [PFX için sertifika altyapısını yapılandırma](configure-certificate-infrastructure-for-pfx.md)
- [Intune sertifika profillerini yapılandırma](configure-intune-certificate-profiles.md)



<!--HONumber=Nov16_HO4-->

