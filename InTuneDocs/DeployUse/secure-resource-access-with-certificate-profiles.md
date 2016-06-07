---
# required metadata

title: Microsoft Intune ile sertifika profillerini kullanarak şirket kaynaklarına erişimi etkinleştirme | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8cbb8499-611d-4217-a7b4-e9b864785dd0

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune’da sertifika profilleriyle güvenli kaynak erişimi
VPN, Wi-Fi veya e-posta profilleri aracılığıyla şirket kaynaklarına erişimi etkinleştirdiğinizde her kullanıcı cihazına yüklü bir sertifika ile bu erişimin güvenliğini sağlama seçeneğine sahip olursunuz. Şu şekilde çalışır:

1. [Sertifika altyapısını yapılandırma](configure-certificate-infrastructure.md) konu başlığı altında açıklandığı gibi, doğru sertifika altyapısına sahip olduğunuzdan emin olun.

2. Cihazın Sertifika Yetkilinizin meşruluğunu tanıması için her cihaza bir kök sertifika (veya ara CA sertifikası) yükleyin. Bunu yapmak için bir **Güvenilen Kök Sertifikası** oluşturun ve dağıtın. Bu profili dağıttığınızda Intune ile yönettiğiniz cihazlar kök sertifikayı ister ve alır. Her platform için ayrı bir profil oluşturmanız gerekir. Şu platformlar için **Güvenilen Sertifika Profili** sağlanır:
 -  iOS 7.1 ve üzeri
 -  Mac OS X 10.9 ve üzeri
 -  Android 4.0 ve üzeri
 -  Windows 8.1 ve üzeri
 -  Windows Phone 8.1 ve üzeri

3. [Intune sertifika profillerini yapılandırma](configure-intune-certificate-profiles.md) konu başlığı altında açıklandığı gibi, her cihazın e-posta, VPN ve Wi-Fi erişimi kimlik doğrulaması için kullanılacak bir sertifika istemesini sağlayın. Bu platformlardaki cihazlar için **PKCS #12 (.PFX) Sertifika Profili** veya **SCEP Sertifika Profili** oluşturabilir ve dağıtabilirsiniz:
 
-  Android 4.0 ve üzeri
-  iOS 7.1 ve üzeri
-  Windows 10 (masaüstü ve Mobile) ve üzeri 

Aşağıdakiler için **SCEP Sertifika Profili** kullanın:
-   Mac OS X 10.9 ve üzeri
-   Windows Phone 8.1 ve üzeri

Her platform için ayrı bir profil oluşturmanız gerekir. Profili oluştururken daha önce oluşturduğunuz **Güvenilen Kök Sertifika profili** ile ilişkilendirin.

> [!NOTE]           
> -    Kuruluş sertifika yetkiliniz yoksa bir tane oluşturmanız gerekir. 
>- Cihaz platformlarınıza bağlı olarak Basitleştirilmiş Sertifika Kayıt Protokolü (SCEP) profili kullanmaya karar verirseniz ayrıca bir Ağ Cihazı Kayıt Hizmeti (NDES) sunucusunu yapılandırmanız gerekir.
>-  SCEP veya .PFX profilleri kullanmayı planlıyorsanız Microsoft Intune Sertifika Bağlayıcısı'nı indirip yapılandırmanız gerekir.
> Tüm bunların yapılandırılması [Sertifika altyapısını yapılandırma](configure-certificate-infrastructure.md) konusunda açıklanmaktadır.

### Sonraki adımlar
- [Sertifika altyapısını yapılandırma](configure-certificate-infrastructure.md)
- [Intune sertifika profillerini yapılandırma](configure-intune-certificate-profiles.md)



<!--HONumber=May16_HO2-->

