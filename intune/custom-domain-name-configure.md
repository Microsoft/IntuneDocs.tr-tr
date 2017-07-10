---
title: "Özel bir etki alanı adı yapılandırma"
description: "Intune aboneliğiniz için özel etki alanı adı ekleme"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/07/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2382f36f-13d8-4a32-81ad-6cfa604889c3
ms.reviewer: angerobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d75292ce60eb1db232aed12fc80a7cbccc063fb4
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="configure-a-custom-domain-name"></a>Özel bir etki alanı adı yapılandırma

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Bu konuda, yöneticilerin oturum açma deneyimlerini kolaylaştırmak ve özelleştirmek için DNS CNAME’i nasıl oluşturacakları açıklanır.

Kuruluşunuz, Microsoft'un Intune gibi bulut tabanlı bir hizmetine kaydolduğunda size Azure Active Directory'de (AD) barındırılan, şuna benzeyen bir ilk etki alanı adı verilir: **etkialanınız.onmicrosoft.com**. Bu örnekte **etkialanınız**, kaydolurken seçtiğiniz etki alanı adıdır ve **onmicrosoft.com**, aboneliğinize eklediğiniz hesaplara atanan son ektir. Kuruluşunuz özel bir etki alanına sahip olduğunda, Intune örneğinizi aboneliğinizle sağlanan etki alanı adını değil bu etki alanı adını kullanmak için yapılandırabilirsiniz.

Kullanıcı hesapları oluşturmadan veya şirket içi Active Directory'nizden eşitlemeden önce, yalnızca .onmicrosoft.com etki alanı adını kullanmaya veya bir veya daha fazla özel etki alanı eklemeye karar vermenizi önemle öneririz. Kullanıcıları eklemeden önce özel bir etki alanı yapılandırmak, kullanıcılarınızın diğer etki alanı kaynaklarına erişmek için kullandığı kimlik bilgileriyle oturum açmasını sağlayarak aboneliğiniz için kullanıcı kimliklerinin yönetilmesini kolaylaştırmaya yardımcı olabilir.

Microsoft'un sunduğu bulut tabanlı bir hizmete abone olduğunuzda, sizin hizmet örneğiniz bulut tabanlı hizmetiniz için kimlik ve dizin hizmetleri sağlayan bir Microsoft [Azure AD kiracısı](http://technet.microsoft.com/library/jj573650.aspx#BKMK_WhatIsAnAzureADTenant) olur. Ayrıca, kuruluşunuzun özel etki alanını kullanmak için Intune’u yapılandırma görevleri diğer Azure AD kiracılarıyla aynı olduğunda, [Etki alanınızı ekleme](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/) konu başlığı altında bulunan bilgi ve yordamları kullanabilirsiniz.

> [!TIP]
> Özel etki alanınızı Microsoft'un sunduğu bulut tabanlı bir hizmetle kullanma hakkında daha fazla bilgi için, bkz [Azure Active Directory’de özel etki alanı adlarına kavramsal genel bakış](https://azure.microsoft.com/documentation/articles/active-directory-add-domain-concepts/).

Bu ilk etki alanı adını yeniden adlandırılamaz veya kaldıramazsınız. Ancak, Intune ile kullanmak üzere özel etki alanı adlarınızı ekleyebilir, doğrulayabilir veya kaldırabilirsiniz; bu, iş kimliğinizi korumak istiyorsanız kullanışlıdır.

## <a name="to-add-and-verify-your-custom-domain"></a>Özel etki alanınızı ekleme ve doğrulama

1. [Office 365 yönetim portalına](https://portal.office.com/Admin/Default.aspx) gidin ve yönetici hesabınızda oturum açın.

2. Gezinme bölmesinde, **Ayarlar** &gt; **Etki alanları** öğelerini seçin.

3. **Etki alanı ekle**’yi seçin ve özel etki alanı adınızı yazın.

4. **Etki alanını doğrula** iletişim kutusu açılarak, DNS barındırma sağlayıcınızdaki TXT kaydını oluşturmak için değerleri verir.
    - **GoDaddy kullanıcıları**: Office 365 Yönetim portalı, sizi GoDaddy'nin oturum açma sayfasına yönlendirir. Kimlik bilgilerinizi girdikten ve etki alanı değiştirme izni sözleşmesini kabul ettikten sonra, TXT kaydı otomatik olarak oluşturulur. Alternatif olarak, kendiniz [TXT kaydını oluşturabilirsiniz](https://support.office.com/article/Create-DNS-records-at-GoDaddy-for-Office-365-f40a9185-b6d5-4a80-bb31-aa3bb0cab48a).
    - **Register.com kullanıcıları**: TXT kaydını oluşturmak için [adım adım yönergeleri](https://support.office.com/article/Create-DNS-records-at-Register-com-for-Office-365-55bd8c38-3316-48ae-a368-4959b2c1684e#BKMK_verify) izleyin.

Özel bir etki alanı ekleme ve doğrulama adımları ayrıca [Azure Active Directory'de gerçekleştirilebilir](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/).

[Office 365'te, ilk onmicrosoft.com etki alanınız hakkında](https://support.office.com/article/About-your-initial-onmicrosoft-com-domain-in-Office-365-B9FC3018-8844-43F3-8DB1-1B3A8E9CFD5A) daha fazla bilgi edinebilirsiniz
