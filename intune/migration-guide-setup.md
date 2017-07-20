---
title: Intune temel kurulumu
description: "Bu makalede, Microsoft Intune’u ayarlamak için gerekli adımlar sağlanmaktadır."
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
ms.openlocfilehash: 9ea12f3707b830f0e3426526a7ae91d176d6e809
ms.sourcegitcommit: fb17b59f4aa2b994b149fcc6d32520f74b0de6a5
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2017
---
# <a name="basic-setup"></a>Temel kurulum

Ortamınızı değerlendirdikten sonra, Intune'u kurma aşamasına gelmiş olursunuz.

## <a name="external-dependencies-for-an-intune-deployment"></a>Intune dağıtımı için dış bağımlılıklar

### <a name="identity"></a>Kimlik

Intune, kimlik ve kullanıcı gruplama sağlayıcısı olarak Azure Active Directory (AAD) gerektirir. Daha fazla bilgi:

-  [Kimlik gereksinimleri](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview)

-   [Dizin eşitleme gereksinimleri](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements)

-   [Çok Faktörlü Kimlik Doğrulaması (MFA) gerekli mi?](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements)

-   [Kullanıcı ve cihaz gruplarınızı planlama](users-add.md)

-   [Kullanıcı ve cihaz grupları oluşturma](groups-get-started.md)

Kuruluşunuzda zaten Office 365 kullanılıyorsa Intune’un aynı Azure Active Directory ortamını kullanması gerekir.

### <a name="pki-optional"></a>PKI (isteğe bağlı)

Intune ile VPN, Wi-Fi veya e-posta profilleri için sertifika tabanlı kimlik doğrulaması kullanmayı planlıyorsanız sertifika ilkeleri oluşturmaya ve dağıtmaya hazır, desteklenen bir [PKI altyapısına sahip olduğunuzdan](certificates-configure.md) emin olmanız gerekir. Intune’da sertifikaları yapılandırma hakkında daha fazla bilgi edinin:

-   [SCEP için sertifika altyapısını yapılandırma](/intune/certificates-scep-configure)

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

Intune, Azure portalından veya Configuration Manager Güncel Dal konsolundan yönetilebilir. Intune’u Configuration Manager Güncel Dal dağıtımı ile tümleştirmeniz gerekmedikçe, Intune'u [Azure portalından](https://portal.azure.com) yönetmenizi öneririz.

MDM yetkilinizi **Intune** olarak ayarlayarak Intune Azure portalını etkinleştirin. Farklı bir MDM yetkilisi kullanmak, Intune’un MDM yönetimini diğer Microsoft yönetim konsollarına aktarmasını sağlar. Bu durum nadiren oluşur.

> [!IMPORTANT]
> Mobil cihaz yönetiminizi ilk defa Intune'a aktarıyorsanız MDM yetkilinizi Intune olarak ayarlamanız gerekir.

[Mobil yönetim yetkilisini ayarlamayı](mdm-authority-set.md) öğrenin.

## <a name="next-step"></a>Sonraki adım

[Mobil cihaz ve uygulama yönetimi ilkelerini](migration-guide-configure-policies.md) yapılandırın.
