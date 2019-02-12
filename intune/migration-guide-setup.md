---
title: Microsoft Intune temel kurulumu
description: Bu makalede, Microsoft Intune’u ayarlamak için gerekli adımlar sağlanmaktadır.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 60cfa440-0723-4ea0-bacf-3c5d26f9a1d3
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: b5e075bdf834f70cf0c138942338963886662ae3
ms.sourcegitcommit: c0b954c82cd732b5328f92b618947bf425bf0a91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56086021"
---
# <a name="basic-setup"></a>Temel kurulum

Ortamınızı değerlendirdikten sonra, Microsoft Intune’u kurma aşamasına gelmiş olursunuz.

## <a name="external-dependencies-for-an-intune-deployment"></a>Intune dağıtımı için dış bağımlılıklar

### <a name="identity"></a>Kimlik

Intune, kimlik ve kullanıcı gruplama sağlayıcısı olarak Azure Active Directory (AAD) gerektirir. Daha fazla bilgi:

-  [Kimlik gereksinimleri](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview)

-   [Dizin eşitleme gereksinimleri](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements)

-   [Çok faktörlü kimlik doğrulaması (MFA)](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)

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

### <a name="task-3-set-your-mdm-authority-to-intune"></a>3. Görev: MDM yetkiliniz olarak Intune'u ayarlama

Intune, Azure portalından veya Configuration Manager Güncel Dal konsolundan yönetilebilir. Intune’u Configuration Manager Güncel Dal dağıtımı ile tümleştirmeniz gerekmedikçe, Intune'u [Azure portalından](https://portal.azure.com) yönetmenizi öneririz.

MDM yetkilinizi **Intune** olarak ayarlayarak Intune Azure portalını etkinleştirin. Farklı bir MDM yetkilisi kullanmak, Intune’un MDM yönetimini diğer Microsoft yönetim konsollarına aktarmasını sağlar. Bu durum nadiren oluşur.

> [!IMPORTANT]
> Mobil cihaz yönetiminizi ilk defa Intune'a aktarıyorsanız MDM yetkilinizi Intune olarak ayarlamanız gerekir.

[Mobil yönetim yetkilisini ayarlamayı](mdm-authority-set.md) öğrenin.

## <a name="next-step"></a>Sonraki adım

[Mobil cihaz ve uygulama yönetimi ilkelerini](migration-guide-configure-policies.md) yapılandırın.
