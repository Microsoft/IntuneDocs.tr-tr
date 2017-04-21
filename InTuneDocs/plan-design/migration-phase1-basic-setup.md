---
title: Intune temel kurulum | Microsoft Docs
description: "Bu makalenin amacı, Microsoft Intune’u kurmak için gerekli adımları sağlamaktır."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 60cfa440-0723-4ea0-bacf-3c5d26f9a1d3
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab6d9b6b296fb4e1fb0aaa9496fede28976728dc
ms.openlocfilehash: 0fce3edb43a147491465d8a58d1a9a4f009fba55
ms.lasthandoff: 04/14/2017


---

# <a name="phase-1-basic-setup"></a>1. Aşama: Temel kurulum

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Ortamınızı değerlendirdikten sonra, Intune’u kurma zamanı gelmiştir.

## <a name="external-dependencies-for-an-intune-deployment"></a>Intune dağıtımı için dış bağımlılıklar

### <a name="identity"></a>Kimlik

Intune, kimlik ve kullanıcı gruplama sağlayıcısı olarak Azure Active Directory (AAD) gerektirir.

-   [Kimlik gereksinimleri](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview) hakkında daha fazla bilgi edinin.

-   [Dizin eşitleme gereksinimleri](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements) hakkında daha fazla bilgi edinin.

-   [Çok faktörlü kimlik doğrulaması gereksinimleri](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements) hakkında daha fazla bilgi edinin.

-   [Kullanıcı ve cihaz gruplarınızı planlama](https://docs.microsoft.com/intune/deploy-use/plan-your-user-and-device-groups) hakkında daha fazla bilgi edinin.

-   [Kullanıcı ve cihaz gruplarının nasıl oluşturulacağını](https://docs.microsoft.com/intune/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune) öğrenin.

Kuruluşunuzda zaten Office 365 kullanılıyorsa Intune’un aynı Azure Active Directory ortamını kullanması önemlidir.

### <a name="pki-optional"></a>PKI (isteğe bağlı)

Intune ile VPN, Wi-Fi veya e-posta profilleri için sertifika tabanlı kimlik doğrulaması kullanmayı planlıyorsanız sertifika ilkeleri oluşturmaya ve dağıtmaya hazır, desteklenen bir [PKI altyapısına sahip olduğunuzdan](https://docs.microsoft.com/intune/deploy-use/secure-resource-access-with-certificate-profiles) emin olmanız gerekir.

Intune’da sertifikaları yapılandırma hakkında daha fazla bilgi aşağıda verilmiştir.

-   [SCEP için sertifika altyapısını yapılandırma](https://docs.microsoft.com/intune/deploy-use/configure-certificate-infrastructure-for-scep).

-   [PFX için sertifika altyapısını yapılandırma](https://docs.microsoft.com/intune/deploy-use/configure-certificate-infrastructure-for-pfx).

-   [Intune sertifika ilkelerini yapılandırma](file:///C:/intune/deploy-use/https://docs.microsoft.com/intune/deploy-use/configure-intune-certificate-profiles).

-   [Kaynak erişim ilkelerini yapılandırma](https://docs.microsoft.com/intune/deploy-use/enable-access-to-company-resources-with-microsoft-intune).

## <a name="task-list-for-an-intune-setup"></a>Intune kurulumu için görev listesi

### <a name="task-1-intune-subscription"></a>1. Görev: Intune aboneliği

Intune'a geçebilmek için Intune aboneliği gerekir.

-   Aşağıdakileri nasıl yapacağınızı öğrenmek için [bu sayfayı](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0) ziyaret edebilirsiniz:

    -   Yeni bir AAD kiracısına bağlantılı yeni bir Intune aboneliği oluşturun.

    -   Mevcut bir AAD kiracısında oturum açarak Intune aboneliğini bağlayın.

### <a name="task-2-assign-intune-user-licenses"></a>2. Görev: Intune kullanıcı lisanslarını atayın

-   [Intune kullanıcı lisanslarının nasıl atanacağını](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-4) öğrenin.

-   Yeni bir Azure Active Directory kiracısı oluşturduysanız [yeni kullanıcılar oluşturma veya şirket içi Active Directory’den (AD) kullanıcı eşitleme.](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)

### <a name="task-3-set-your-mdm-authority-to-intune"></a>3. Görev: MDM yetkilinizi Intune olarak ayarlayın

Intune, Azure Portalından veya Configuration Manager Güncel Dal konsolundan yönetilebilir. Intune’u Configuration Manager Güncel Dal dağıtımı ile tümleştirmeniz gerekmedikçe, Intune'u [Azure Portalından](https://portal.azure.com) yönetmeniz önerilir.

MDM yetkilinizi **Intune** olarak ayarlayarak Intune Azure Portalı'nı etkinleştirin. Farklı bir MDM yetkilisi kullanmak, Intune’un MDM yönetimini diğer Microsoft yönetim konsollarına aktarmasını sağlar. Bu durum nadiren oluşur.

> [!IMPORTANT]
> Mobil cihaz yönetiminizi ilk defa Intune'a aktarıyorsanız MDM yetkilinizi Intune olarak ayarlamanız gerekir.

-   [Mobil yönetim yetkilisini ayarlamayı](https://docs.microsoft.com/intune/deploy-use/prerequisites-for-enrollment#step-2-set-mdm-authority) öğrenin.

## <a name="next-step"></a>Sonraki adım

[1. Aşama: Mobil cihaz ve uygulama yönetimi ilkelerini yapılandırma](https://docs.microsoft.com/intune/plan-design/migration-phase1-configure-device-and-app-management-policies)

