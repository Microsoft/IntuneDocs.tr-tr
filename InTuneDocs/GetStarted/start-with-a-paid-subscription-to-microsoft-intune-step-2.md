---
title: "Özel bir etki alanı adı yapılandırma | Microsoft Intune"
description: "Intune aboneliğiniz için özel etki alanı adı ekleme"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2382f36f-13d8-4a32-81ad-6cfa604889c3
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 29b6e5a3d319c741482fcc2b600842e2e42b96e2
ms.openlocfilehash: 9fe78bca15ffee1e5e0e7e3758ff70b6bc92b619


---


# <a name="configure-a-custom-domain-name"></a>Özel bir etki alanı adı yapılandırma

Kuruluşunuz, Microsoft'un Intune gibi bulut tabanlı bir hizmetine kaydolduğunda size Azure Active Directory'de (AD) barındırılan, şuna benzeyen bir ilk etki alanı adı verilir: **etkialanınız.onmicrosoft.com**. Bu örnekte **etkialanınız**, kaydolurken seçtiğiniz etki alanı adıdır ve **onmicrosoft.com**, aboneliğinize eklediğiniz hesaplara atanan son ektir. Kuruluşunuz özel bir etki alanına sahip olduğunda, Intune örneğinizi aboneliğinizle sağlanan etki alanı adını değil bu etki alanı adını kullanmak için yapılandırabilirsiniz.

Kullanıcı hesapları oluşturmadan veya şirket içi Active Directory'nizden eşitlemeden önce, yalnızca .onmicrosoft.com etki alanı adını kullanmaya veya bir veya daha fazla özel etki alanı eklemeye karar vermenizi önemle öneririz. Kullanıcıları eklemeden önce özel bir etki alanı yapılandırmak, kullanıcılarınızın diğer etki alanı kaynaklarına erişmek için kullandığı kimlik bilgileriyle oturum açmasını sağlayarak aboneliğiniz için kullanıcı kimliklerinin yönetilmesini kolaylaştırmaya yardımcı olabilir.

Microsoft'un sunduğu bulut tabanlı bir hizmete abone olduğunuzda, sizin hizmet örneğiniz bulut tabanlı hizmetiniz için kimlik ve dizin hizmetleri sağlayan bir Microsoft [Azure AD kiracısı](http://technet.microsoft.com/library/jj573650.aspx#BKMK_WhatIsAnAzureADTenant) olur. Ayrıca, kuruluşunuzun özel etki alanını kullanmak için Intune’u yapılandırma görevleri diğer Azure AD kiracılarıyla aynı olduğunda, [Etki alanınızı ekleme](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/) konu başlığı altında bulunan bilgi ve yordamları kullanabilirsiniz.

> [!TIP]
> Özel etki alanınızı Microsoft'un sunduğu bulut tabanlı bir hizmetle kullanma hakkında daha fazla bilgi için, bkz [Azure Active Directory’de özel etki alanı adlarına kavramsal genel bakış](https://azure.microsoft.com/documentation/articles/active-directory-add-domain-concepts/).

Bu ilk etki alanı adını yeniden adlandırılamaz veya kaldıramazsınız. Ancak, Intune ile kullanmak üzere özel etki alanı adlarınızı ekleyebilir, doğrulayabilir veya kaldırabilirsiniz; bu, iş kimliğinizi korumak istiyorsanız kullanışlıdır.

## <a name="to-add-and-verify-your-custom-domain"></a>Özel etki alanınızı ekleme ve doğrulama

1. [Office 365 yönetim portalına](https://portal.office.com/Admin/Default.aspx) gidin ve yönetici hesabınızda oturum açın.

2. Gezinme bölmesinde, **Ayarlar** &gt; **Etki alanları** öğelerini seçin.

3. **Etki alanı ekle**’yi seçin ve özel etki alanı adınızı yazın.

4. **Etki alanını doğrula** iletişim kutusu açılarak, DNS barındırma sağlayıcınızdaki TXT kaydını oluşturmak için değerleri verir.
    - **GoDaddy kullanıcıları**: Office 365 Yönetim portalı, sizi GoDaddy'nin oturum açma sayfasına yönlendirir. Kimlik bilgilerinizi girdikten ve etki alanı değiştirme izni sözleşmesini kabul ettikten sonra, TXT kaydı otomatik olarak oluşturulur. Alternatif olarak, kendiniz [TXT kaydını oluşturabilirsiniz](https://support.office.com/en-us/article/Create-DNS-records-at-GoDaddy-for-Office-365-f40a9185-b6d5-4a80-bb31-aa3bb0cab48a?ui=en-US&rs=en-US&ad=US).
    - **Register.com kullanıcıları**: TXT kaydını oluşturmak için [adım adım yönergeleri](https://support.office.com/en-us/article/Create-DNS-records-at-Register-com-for-Office-365-55bd8c38-3316-48ae-a368-4959b2c1684e?ui=en-US&rs=en-US&ad=US#BKMK_verify) izleyin.

    > [!TIP]
    > DNS barındırma sağlayıcınızda değişiklikler yaparken, [Windows cihazları kaydı](/Intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune) için bir DNS diğer adı (CNAME) oluşturduğunuzdan emin olun.

Özel bir etki alanı ekleme ve doğrulama adımları alternatif olarak [Azure Active Directory'de gerçekleştirilebilir](https://azure.microsoft.com/en-us/documentation/articles/active-directory-add-domain/).

Bir karma bulut senaryosunda, özel etki alanı adınızı ekledikten sonra ve kuruluşunuzun onun sahibi olduğu doğrulandıktan sonra, şirket içi Active Directory'de kullanıcı hesaplarınızı yönetmeye devam edebilirsiniz, ardından onu Azure AD ile eşitleyebilirsiniz.

## <a name="to-synchronize-on-premises-users-with-azure-ad"></a>Şirket içi kullanıcıları Azure AD ile eşitleme##

1. Şirket içi Active Directory’de özel etki alanınız için [UPN sonekini ekleyin](https://technet.microsoft.com/en-us/library/cc772007.aspx).
2. İçe aktarmayı planladınız şirket için kullanıcılar için, yeni UPN sonekini ayarlayın.
3. Şirket için kullanıcılarınızı Azure AD ile tümleştirmek için, [Azure AD Connect eşitleme](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect/) çalıştırın.
4. Kullanıcı hesabı bilgileri başarıyla eşitlendiğinde, [Office 365 Yönetim Portalı](https://portal.office.com/Admin/Default.aspx)’nı kullanarak Microsoft Intune lisansları atayabilirsiniz.

### <a name="see-also"></a>Ayrıca bkz.

[Office 365'te, ilk onmicrosoft.com etki alanınız hakkında](https://support.office.com/en-us/article/About-your-initial-onmicrosoft-com-domain-in-Office-365-B9FC3018-8844-43F3-8DB1-1B3A8E9CFD5A?ui=en-US&rs=en-US&ad=US)

[Microsoft Intune'u başlatmadan önce bilinmesi gerekenler](what-to-know-before-you-start-microsoft-intune.md)
### <a name="next-steps"></a>Sonraki adımlar
Tebrikler! *Intune hızlı başlangıç kılavuzunun* 2. adımını tamamlamış oldunuz.

>[!div class="step-by-step"]

>[&larr; **Intune’da oturum açma**](.\start-with-a-paid-subscription-to-microsoft-intune-step-1.md)     [**Intune’a kullanıcı ekleme** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-3.md)  



<!--HONumber=Nov16_HO4-->


