---
title: "Kullanıcılar ile çalışmaya başlama"
titleSuffix: Intune on Azure
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 06/27/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 22a232de-ab93-44ab-b0b5-d2b3ccb007fe
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e711f32ebd77a83b17e6db468f8cb23a409c8d31
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/03/2017
---
# <a name="get-started-with-users"></a>Kullanıcılar ile çalışmaya başlama

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Azure Active Directory, kuruluşunuzun cihaz ve uygulama gibi nesne gruplarını ve ayrıca kullanıcı gruplarını yönetir. Her cihazı ayrı yönetmek zorunda kalmak yerine kullanıcıları veya cihazları gruplayabilirsiniz. Bu, büyük sayıda kullanıcı ve cihaza kolayca uygulama ve ayar atamanıza izin verir.

## <a name="how-do-i-create-a-user"></a>Bir kullanıcı nasıl oluşturulur?

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Kaynak ara**'yı kullanarak **Kullanıcılar ve gruplar**’ı arayın.
3. **Kullanıcılar ve gruplar** dikey penceresini açtıktan sonra **Tüm kullanıcılar**'ı, sonra **+Yeni kullanıcı**'yı seçin.
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
