---
# required metadata

title: Özel bir etki alanı adı yapılandırma | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 2382f36f-13d8-4a32-81ad-6cfa604889c3

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Özel bir etki alanı adı yapılandırma

Varsayılan olarak Intune, hizmete ilk abone olduğunuzda oluşturulan **<domain>.onmicrosoft.com** etki alanı adını kullanır. Kuruluşunuz özel bir etki alanına sahip olduğunda, Intune örneğinizi aboneliğinizle sağlanan etki alanı adını değil bu etki alanı adını kullanmak için yapılandırabilirsiniz.

Yeni kullanıcı hesapları oluşturmadan veya şirket içi Active Directory'nizden hesapları eşitlemeden önce, yalnızca .onmicrosoft.com etki alanı adını kullanmaya veya bir veya daha fazla özel etki alanı eklemeye karar vermenizi önemle öneririz. Kullanıcıları eklemeden önce özel bir etki alanı yapılandırmak, kullanıcılarınızın diğer etki alanı kaynaklarına erişmek için kullandığı kimlik bilgileriyle oturum açmasını sağlayarak aboneliğiniz için kullanıcı kimliklerinin yönetilmesini kolaylaştırmaya yardımcı olabilir.

Microsoft'un sunduğu bulut tabanlı bir hizmete abone olduğunuzda, sizin hizmet örneğiniz bulut tabanlı hizmetiniz için kimlik ve dizin hizmetleri sağlayan bir Microsoft [Azure AD kiracısı](http://technet.microsoft.com/library/jj573650.aspx#BKMK_WhatIsAnAzureADTenant) olur. Ayrıca, kuruluşunuzun özel etki alanını kullanmak için Intune’u yapılandırma görevleri diğer Azure AD kiracılarıyla aynı olduğunda, [Etki alanınızı ekleme](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/) konu başlığı altında bulunan bilgi ve yordamları kullanabilirsiniz.

> Özel etki alanınızı Microsoft'un sunduğu bulut tabanlı bir hizmetle kullanma hakkında daha fazla bilgi için, bkz [Azure Active Directory’de özel etki alanı adlarına kavramsal genel bakış](https://azure.microsoft.com/documentation/articles/active-directory-add-domain-concepts/).

### Sonraki adımlar
Tebrikler! *Intune hızlı başlangıç kılavuzunun* 2. adımını tamamlamış oldunuz.

>[!div class="step-by-step"]

>[&larr; **Intune’da oturum açma**](.\start-with-a-paid-subscription-to-microsoft-intune-step-1.md)     [**Intune’a kullanıcı ekleme** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-3.md)  


<!--HONumber=May16_HO2-->


