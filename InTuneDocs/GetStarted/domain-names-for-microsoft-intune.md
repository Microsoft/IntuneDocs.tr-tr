---
# required metadata

title: Microsoft Intune için etki alanı adları | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: c3c136f0-330d-432a-a91f-16f7dd097e55

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---



# Microsoft Intune için etki alanı adları

Microsoft Intune’u ayarlamadan önce bu konuyu ve [Microsoft Intune’u başlatmadan önce bilinmesi gerekenler](what-to-know-before-you-start-microsoft-intune.md) başlığı altında listelenen diğer gereksinimleri gözden geçirin.

Kuruluşunuz, Microsoft'un Intune gibi bulut tabanlı bir hizmetine kaydolduğunda size şuna benzeyen bir ilk etki alanı adı verilir: **contoso.onmicrosoft.com**. Bu örnekte **contoso**, kaydolurken seçtiğiniz etki alanı adıdır ve **onmicrosoft.com**, aboneliğinize eklediğiniz hesaplara atanan son ektir. Kayıt işlemini tamamladıktan sonra bu etki alanı adını değiştiremezsiniz. Ancak, genel yönetici olarak kuruluşunuz için hizmetle birlikte kullanılacak özel etki alanı adları ekleyebilir veya daha önce eklediğiniz etki alanlarını kaldırabilirsiniz.

Varsayılan olarak, onmicrosoft etki alanını kullandığınızda içeri aktardığınız her kullanıcının kullanıcı asıl adına (UPN) **onmicrosoft.com** son eki getirilir.

Kayıt sırasında verilenin yerine sahip olduğunuz bir etki alanı adını kullanmak için, etki alanı adını Azure Active Directory’ye ekleyebilirsiniz. Etki alanını ekledikten ve size ait olduğu onaylandıktan sonra, DNS barındırma sağlayıcınızdaki DNS kaynak kayıtlarını değiştirerek etki alanı adını içeren hesaplar ve gruplar oluşturabilirsiniz. Özel bir etki alanı kullanmayı planladığınızda kullanıcı hesaplarının yönetimini kolaylaştırmak için, yerel Active Directory'den kullanıcıları eşitlemeye başlamadan önce aboneliğinize özel bir etki alanı adı yapılandırın.

Intune için etki alanı adlarını ve DNS kaynak kayıtlarını yapılandırma işlemi, diğer Azure Active Directory kiracıları için yapılan işlemle aynıdır. Yönergeler için bz. [Azure Active Directory’yi kullanarak oturum açmayı basitleştirmek için özel etki alanı adınızı ekleme](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/).

### Ayrıca bkz.
[Microsoft Intune'u başlatmadan önce bilinmesi gerekenler](what-to-know-before-you-start-microsoft-intune.md)


<!--HONumber=May16_HO2-->


