---
title: Intune temel kurulumu
description: "Bu makalenin amacı, Microsoft Intune’u kurmak için gerekli adımları sağlamaktır."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 60cfa440-0723-4ea0-bacf-3c5d26f9a1d3
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: c3129b2a8d93e91493455da5f3e5fd1a59dd77bb
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="basic-setup"></a>Temel kurulum

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

Ortamınızı değerlendirdikten sonra, Intune'u kurma aşamasına gelmiş olursunuz.

## <a name="external-dependencies-for-an-intune-deployment"></a>Intune dağıtımı için dış bağımlılıklar

### <a name="identity"></a>Kimlik

Intune, kimlik ve kullanıcı gruplama sağlayıcısı olarak Azure Active Directory (AAD) gerektirir.

-   [Kimlik gereksinimleri](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview) hakkında daha fazla bilgi edinin.

-   [Dizin eşitleme gereksinimleri](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements) hakkında daha fazla bilgi edinin.

-   [Çok faktörlü kimlik doğrulaması gereksinimleri](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements) hakkında daha fazla bilgi edinin.

-   [Kullanıcı ve cihaz gruplarınızı planlama](/intune/users-permissions-add) hakkında daha fazla bilgi edinin.

-   [Kullanıcı ve cihaz gruplarının nasıl oluşturulacağını](/intune/groups-get-started) öğrenin.

Kuruluşunuzda zaten Office 365 kullanılıyorsa Intune’un aynı Azure Active Directory ortamını kullanması önemlidir.

### <a name="pki-optional"></a>PKI (isteğe bağlı)

Intune ile VPN, Wi-Fi veya e-posta profilleri için sertifika tabanlı kimlik doğrulaması kullanmayı planlıyorsanız sertifika ilkeleri oluşturmaya ve dağıtmaya hazır, desteklenen bir [PKI altyapısına sahip olduğunuzdan](/intune/certificates-configure) emin olmanız gerekir.

Intune’da sertifikaları yapılandırma hakkında daha fazla bilgi aşağıda verilmiştir.

-   [SCEP için sertifika altyapısını yapılandırma](/intune/certificates-scep-configure).

-   [PFX için sertifika altyapısını yapılandırma](/intune/certficates-pfx-configure).


## <a name="task-list-for-an-intune-setup"></a>Intune kurulumu için görev listesi

### <a name="task-1-intune-subscription"></a>1. Görev: Intune aboneliği

Intune'a geçebilmek için Intune aboneliği gerekir.

-   Aşağıdakileri nasıl yapacağınızı öğrenmek için [bu sayfayı](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0) ziyaret edebilirsiniz:

    -   Yeni bir AAD kiracısına bağlantılı yeni bir Intune aboneliği oluşturun.

    -   Mevcut bir AAD kiracısında oturum açarak Intune aboneliğini bağlayın.

### <a name="task-2-assign-intune-user-licenses"></a>2. Görev: Intune kullanıcı lisanslarını atayın

-   [Intune kullanıcı lisanslarının nasıl atanacağını](licenses-assign.md) öğrenin.

-   Yeni bir Azure Active Directory kiracısı oluşturduysanız [yeni kullanıcılar oluşturma veya şirket içi Active Directory’den (AD) kullanıcı eşitleme.](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)

### <a name="task-3-set-your-mdm-authority-to-intune"></a>3. Görev: MDM yetkilinizi Intune olarak ayarlayın

Intune, Azure portalından veya Configuration Manager Güncel Dal konsolundan yönetilebilir. Intune’u Configuration Manager Güncel Dal dağıtımı ile tümleştirmeniz gerekmedikçe, Intune'u [Azure Portalından](https://portal.azure.com) yönetmeniz önerilir.

MDM yetkilinizi **Intune** olarak ayarlayarak Intune Azure Portalı'nı etkinleştirin. Farklı bir MDM yetkilisi kullanmak, Intune’un MDM yönetimini diğer Microsoft yönetim konsollarına aktarmasını sağlar. Bu durum nadiren oluşur.

> [!IMPORTANT]
> Mobil cihaz yönetiminizi ilk defa Intune'a aktarıyorsanız MDM yetkilinizi Intune olarak ayarlamanız gerekir.

-   [Mobil yönetim yetkilisini ayarlamayı](/intune/mdm-authority-set) öğrenin.

## <a name="next-step"></a>Sonraki adım

[Mobil cihaz ve uygulama yönetimi ilkelerini yapılandırma](migration-guide-configure-policies.md)
