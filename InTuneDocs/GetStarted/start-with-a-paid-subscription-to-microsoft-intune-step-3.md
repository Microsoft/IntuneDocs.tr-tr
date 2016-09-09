---
title: "Active Directory’yi eşitleme ve Intune’a kullanıcı ekleme | Microsoft Intune"
description: "Şirket içindeki kullanıcıları Azure AD ile eşitleme ve Intune aboneliğiniz için yönetici izinleri verme işlemleri açıklanır"
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 08/29/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6e9ec662-465b-4ed4-94c1-cff0fe18f126
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0c1e08cc49d75303f6793894e3c8a040f6e7a8b1
ms.openlocfilehash: a2ed4b1e025437cca6de4a15b3800daa2c9a212b


---


# Active Directory’yi eşitleme ve Intune’a kullanıcı ekleme
Şirket içi Active Directory'nizden Microsoft Azure Active Directory’ye (Azure AD) kullanıcı hesaplarını aktarmak için dizin eşitlemeyi yapılandırabilirsiniz. Şirket içi Active Directory hizmetinizi tüm Azure Active Directory tabanlı hizmetlere bağlamak kullanıcı kimliği yönetimini daha kolay hale getirir. Kullanıcılarınız için kimlik doğrulaması deneyimini tanıdık ve kolay hale getirmek isterseniz, çoklu oturum açma özelliklerini de yapılandırabilirsiniz.

İşleri daha da kolaylaştırmak için, aynı [Azure AD kiracısıyla](http://technet.microsoft.com/library/jj573650.aspx#BKMK_WhatIsAnAzureADTenant) birden çok hizmet kullandığınızda, daha önce eşitlemiş olduğunuz kullanıcı hesapları aynı Azure AD kiracı aboneliğini paylaşan tüm bulut tabanlı hizmetlerin kullanımına sunulur.

## Şirket içi kullanıcılarını Azure AD ile eşitleme
Kullanıcı hesaplarınızı Azure AD ile eşitlemek için ihtiyacınız olan tek araç [Azure AD Connect sihirbazıdır](https://www.microsoft.com/download/details.aspx?id=47594). Azure AD Connect sihirbazı, şirket içi kimlik altyapınızı buluta bağlamak için basitleştirilmiş ve kılavuzlu bir deneyim sağlar.  Topolojinizi ve ihtiyaçlarınızı (tek veya birden çok dizin, parola eşitleme ya da federasyon) seçtiğinizde, sihirbaz bağlantınızı çalışır hale getirmek için gereken tüm bileşenleri dağıtır ve yapılandırır. Bunlara eşitleme hizmetleri, Active Directory Federasyon Hizmetleri (AD FS) ve Azure AD PowerShell modülü de dahildir.

> [!TIP]
> Azure AD Connect, önceden Dirsync ve Azure AD Eşitleme olarak yayımlanan işlevselliği kapsar. [Dizin tümleştirmesi](http://technet.microsoft.com/library/jj573653.aspx) hakkında daha fazla bilgi edinebilirsiniz. Kullanıcı hesaplarını yerel dizininizden Azure AD'ye eşitlemenin avantajlarını öğrenmek için, bkz. [Active Directory ve Azure AD arasındaki benzerlikler](http://technet.microsoft.com/library/dn518177.aspx).

## Yönetici izinleri verme
Intune aboneliğinize kullanıcılar ekledikten sonra, birkaç kullanıcı hesabına [yönetici kimlik bilgileri](administrative-accounts-websites-perms.md) vermenizi öneririz. Yönetici kimlik bilgilerini atamak için kullandığınız konsol atamak istediğiniz yönetici türüne bağlıdır:

-   **Kiracı yöneticisi**: Faturalandırma, bulut depolama ve [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] kullanabilecek kullanıcıları yönetme gibi, aboneliğinizin özelliklerini yönetmesi için bu tür yöneticiyi atamak amacıyla **[!INCLUDE[wit_icp_1](../includes/wit_icp_1_md.md)]** kullanın.

-   **Hizmet yöneticisi**: Mobil cihaz veya bilgisayar yönetimi, ilke veya yazılım dağıtma ve raporları çalıştırma gibi günlük görevler için bir yönetici atamak için **[!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)]** kullanın.


### Sonraki adımlar
Tebrikler! *Intune hızlı başlangıç kılavuzunun* 3. adımını tamamlamış oldunuz.

>[!div class="step-by-step"]

>[&larr; **Etki alanı ayarları**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Intune lisanslarını yönetme** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-4.md)  



<!--HONumber=Aug16_HO5-->


