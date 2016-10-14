---
title: "Microsoft Intune için etki alanı adları | Microsoft Intune"
description: "Intune için etki alanı adı ekleme"
keywords: 
author: andredm7
manager: swadhwa
ms.date: 10/11/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c3c136f0-330d-432a-a91f-16f7dd097e55
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 38159f6dbcae2eeb4dca47141e60eed12cd7f6ee
ms.openlocfilehash: abcf37e7ec3150b5a2fe4cda910631f83d4c510a


---



# Microsoft Intune ile özel etki alanı adları

Kuruluşunuz, Microsoft'un Intune gibi bulut tabanlı bir hizmetine kaydolduğunda size Azure Active Directory’de barındırılan, şuna benzeyen bir ilk etki alanı adı verilir: **etkialanınız.onmicrosoft.com**. Bu örnekte **etkialanınız**, kaydolurken seçtiğiniz etki alanı adıdır ve **onmicrosoft.com**, aboneliğinize eklediğiniz hesaplara atanan son ektir.

Bu ilk etki alanı adını yeniden adlandırılamaz veya kaldıramazsınız. Ancak, Intune ile kullanmak üzere özel etki alanı adlarınızı ekleyebilir, doğrulayabilir veya kaldırabilirsiniz; bu, iş kimliğinizi korumak istiyorsanız kullanışlıdır.

## Özel etki alanınızı ekleme ve doğrulama 

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

## Şirket içi kullanıcıları Azure AD ile eşitleme##

1. Şirket içi Active Directory’de özel etki alanınız için [UPN sonekini ekleyin](https://technet.microsoft.com/en-us/library/cc772007.aspx).
2. İçe aktarmayı planladınız şirket için kullanıcılar için, yeni UPN sonekini ayarlayın.
3. Şirket için kullanıcılarınızı Azure AD ile tümleştirmek için, [Azure AD Connect eşitleme](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect/) çalıştırın.
4. Kullanıcı hesabı bilgileri başarıyla eşitlendiğinde, [Office 365 Yönetim Portalı](https://portal.office.com/Admin/Default.aspx)’nı kullanarak Microsoft Intune lisansları atayabilirsiniz.

### Ayrıca bkz.

[Office 365'te, ilk onmicrosoft.com etki alanınız hakkında](https://support.office.com/en-us/article/About-your-initial-onmicrosoft-com-domain-in-Office-365-B9FC3018-8844-43F3-8DB1-1B3A8E9CFD5A?ui=en-US&rs=en-US&ad=US)

[Microsoft Intune'u başlatmadan önce bilinmesi gerekenler](what-to-know-before-you-start-microsoft-intune.md)



<!--HONumber=Oct16_HO2-->


