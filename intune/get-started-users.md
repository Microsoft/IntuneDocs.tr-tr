---
title: "Kullanıcılar ile çalışmaya başlama"
titlesuffix: Azure portal
description: "Mobil cihazlarda şirket kaynaklarına erişmesini sağlamak için Intune’a bir kullanıcı ekleyin."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 22a232de-ab93-44ab-b0b5-d2b3ccb007fe
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a33eb2d5dc96a2647cf2582bbc6cd4ba2d9c0961
ms.sourcegitcommit: fa6aaf12611c3e03e38e467806fc30b1d0255e88
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2017
---
# <a name="get-started-with-managing-users"></a>Kullanıcıları yönetmeye başlama

Kuruluşunuzdaki tüm farklı kişileri düşünün. Şirket kaynaklarını kullanan herkesin, Intune’da bu kaynaklara erişimi yönetmesi için bir kullanıcıya ihtiyacı vardır.

## <a name="how-do-i-create-a-user"></a>Bir kullanıcı nasıl oluşturulur?

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Kaynak ara**'yı kullanarak **Intune**'u arayın.
3. **Microsoft Intune** dikey penceresini açtıktan sonra **Kullanıcılar**’ı seçin. **Tüm Kullanıcılar** sayfasında **+ Yeni kullanıcı**’yı seçin.
4. Kullanıcının **Ad** ve **Kullanıcı adı** gibi ayrıntılarını girin. Kullanıcı adının etki alanı adı kısmı, "contoso.onmicrosoft.com" gibi ilk varsayılan etki alanı adı veya "contoso.com" gibi doğrulanmış, federasyon olmayan bir etki alanı adı olmalıdır.
5. **Gruplar**'ın altından kullanıcının ekleneceği sınama grubunu seçin.
6. Bir sınama cihazında oturum açmak üzere kullanabilmek için otomatik olarak oluşturulan kullanıcı parolasını kaydedin. Bu parolayı, hatırlayabilecekleri normal bir parola ile değiştirebilmeleri için kullanıcılara vermelisiniz.
7. **Kullanıcı** dikey penceresinde **Oluştur**'u seçin.

## <a name="assigning-licenses-to-users"></a>Kullanıcılara lisans atama

Bir kullanıcı oluşturduktan sonra, bu kullanıcıya bir Intune lisansı atamak için [Office 365 portalı](http://go.microsoft.com/fwlink/p/?LinkId=698854)'nı kullanmanız gerekir. Kendisine bir lisans atanmazsa kullanıcı cihazını yönetime kaydedemez.

1. Intune'da oturum açmak için kullandığınız kimlik bilgileriyle [Office 365 portalı](http://go.microsoft.com/fwlink/p/?LinkId=698854)'nda oturum açın.
2. **Kullanıcılar** > **Etkin Kullanıcılar**'ı, sonra daha önce oluşturduğunuz kullanıcıyı seçin.
3. Kullanıcı bilgilerinin yüklenmesi için bir süre beklemeniz gerekebilir. Yüklendikten sonra kullanıcının **Ürün lisansları** için **Düzenle**'yi seçin.
4. Kullanıcıyı bir **Konum**'a atayın, sonra Intune'u **açık** hale getirin.

 > [!NOTE]
 > Bu işlem, kullanıcı için lisanslarınızdan birini kullanır. Yayındaki ortamınızı kullanıyorsanız bu lisansın kullanımını, daha sonra gerçek bir kullanıcıya yeniden atayabilmek için kapatabilirsiniz.

5. **Kaydet**’i seçin.

## <a name="next-steps"></a>Sonraki adımlar

[Grupları kullanmaya başlama](get-started-groups.md) - Erişebilecekleri ilke ve uygulamaların yönetimini kolaylaştırmak için kullanıcıları gruplara ayırın.
