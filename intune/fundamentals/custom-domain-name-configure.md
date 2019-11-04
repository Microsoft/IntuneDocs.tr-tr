---
title: Özel bir etki alanı adı yapılandırma
titleSuffix: Microsoft Intune
description: Microsoft Intune aboneliğiniz için özel etki alanı adı ekleme
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 06/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.assetid: 2382f36f-13d8-4a32-81ad-6cfa604889c3
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 04708842373abf296b5350d9f77e02fa08ce48ed
ms.sourcegitcommit: 60f0ff6d2efbae0f2ce14b9a9f3f9267309e209b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73414611"
---
# <a name="configure-a-custom-domain-name"></a>Özel bir etki alanı adı yapılandırma

Bu konuda, yöneticilerin oturum açma deneyimlerini kolaylaştırmak ve özelleştirmek için DNS CNAME’in nasıl oluşturulacağı açıklanır.

Kuruluşunuz, Microsoft’un Intune gibi bulut tabanlı bir hizmete kaydolduğunda size Azure Active Directory’de (AD) barındırılan, **etki-alanınız.onmicrosoft.com** şeklinde bir ilk etki alanı adı verilir. Bu örnekte **etki-alanınız** kısmı, kaydolduğunuz zaman seçtiğiniz etki alanı adıdır. **onmicrosoft.com** kısmı ise aboneliğinize eklediğiniz hesaplara atanan sonektir. Intune’a erişmek için aboneliğinizle sağlanan etki alanı adı yerine kuruluşunuzun özel etki alanını kullanabilirsiniz.

Kullanıcı hesapları oluşturmadan veya şirket içi Active Directory'nizden eşitlemeden önce, yalnızca .onmicrosoft.com etki alanı adını kullanmaya veya bir veya daha fazla özel etki alanı eklemeye karar vermenizi önemle öneririz. Kullanıcı yönetimini kolaylaştırmak için kullanıcı eklemeden önce özel bir etki alanı ayarlayın. Bir müşteri etki alanı ayarlamak, kullanıcıların diğer etki alanı kaynaklarına erişmek için kullandıkları kimlik bilgileriyle oturum açmalarına olanak tanır.

Microsoft'un sunduğu bulut tabanlı bir hizmete abone olduğunuzda, sizin hizmet örneğiniz bulut tabanlı hizmetiniz için kimlik ve dizin hizmetleri sağlayan bir Microsoft [Azure AD kiracısı](https://technet.microsoft.com/library/jj573650.aspx#BKMK_WhatIsAnAzureADTenant) olur. Ayrıca, kuruluşunuzun özel etki alanını kullanmak için Intune’u yapılandırma görevleri diğer Azure AD kiracılarıyla aynı olduğunda, [Etki alanınızı ekleme](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/) konu başlığı altında bulunan bilgi ve yordamları kullanabilirsiniz.

> [!TIP]
> Özel etki alanları hakkında daha fazla bilgi için bkz. [Azure Active Directory’de özel etki alanlarına kavramsal bir genel bakış](https://azure.microsoft.com/documentation/articles/active-directory-add-domain-concepts/).

onmicrosoft.com ilk etki alanı adını yeniden adlandıramaz veya kaldıramazsınız. İş kimliğinizi açık tutmak için Intune ile kullanılan özel etki alanı adlarını ekleyebilir, doğrulayabilirsiniz veya kaldırabilirsiniz.

## <a name="to-add-and-verify-your-custom-domain"></a>Özel etki alanınızı ekleme ve doğrulama

1. [Microsoft 365 yönetim merkezine](https://admin.microsoft.com/) gidin ve yönetici hesabınızda oturum açın.

2. Gezinme bölmesinde, **Kurulum** &gt; **Etki alanları**'nı seçin.

3. **Etki alanı ekle**’yi seçin ve özel etki alanı adınızı yazın. **İleri**'yi seçin.
   ![Microsoft 365 yönetim merkezinde Ayarlar > Etki Alanları’nın seçili olduğu ve yeni bir etki alanının eklenmesini gösteren ekran görüntüsü](./media/custom-domain-name-configure/domain-custom-add.png)
4. **Etki alanını doğrula** iletişim kutusu açılarak, DNS barındırma sağlayıcınızdaki TXT kaydını oluşturmak için değerleri verir.
    - **GoDaddy kullanıcıları**: Microsoft 365 Yönetim Merkezi sizi GoDaddy 'ın oturum açma sayfasına yönlendirir. Kimlik bilgilerinizi girdikten ve etki alanı değiştirme izni sözleşmesini kabul ettikten sonra, TXT kaydı otomatik olarak oluşturulur. Alternatif olarak, kendiniz [TXT kaydını oluşturabilirsiniz](https://support.office.com/article/Create-DNS-records-at-GoDaddy-for-Office-365-f40a9185-b6d5-4a80-bb31-aa3bb0cab48a).
    - **Register.com kullanıcıları**: TXT kaydını oluşturmak için [adım adım yönergeleri](https://support.office.com/article/Create-DNS-records-at-Register-com-for-Office-365-55bd8c38-3316-48ae-a368-4959b2c1684e#BKMK_verify) izleyin.
5. [Intune kayıtları için ek DNS kayıtları oluşturmanız](../enrollment/windows-enroll.md#simplify-windows-enrollment-without-azure-ad-premium)gerekebilir.

Özel bir etki alanı ekleme ve doğrulama adımları ayrıca [Azure Active Directory'de gerçekleştirilebilir](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/).

[Office 365'te, ilk onmicrosoft.com etki alanınız hakkında](https://support.office.com/article/About-your-initial-onmicrosoft-com-domain-in-Office-365-B9FC3018-8844-43F3-8DB1-1B3A8E9CFD5A) daha fazla bilgi edinebilirsiniz

Kaydı Intune sunucularına yönlendiren bir DNS CNAME 'i oluşturarak, [Windows kaydını Azure AD Premium olmadan nasıl basitleştireceğinizi](../enrollment/windows-enroll.md#simplify-windows-enrollment-without-azure-ad-premium) öğrenin.
