---
title: Kullanıcıları yönetmeye başlama
titlesuffix: Microsoft Intune
description: Intune'a bir kullanıcı ekleyin ve şirket kaynaklarına mobil cihazlardan erişebilmesi için bu kullanıcıya bir lisans atayın.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 22a232de-ab93-44ab-b0b5-d2b3ccb007fe
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 292df171b613ada7a5f8e2cf666ba358ef26df9b
ms.sourcegitcommit: e01945bff19157fa7acaa4f7975b0f2a8b3a73f0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37949484"
---
# <a name="get-started-managing-users"></a>Kullanıcıları yönetmeye başlama

Kuruluşunuzdaki tüm farklı kişileri düşünün. Şirket kaynaklarını kullanan herkesin, Intune’da bu kaynaklara erişimi yönetmesi için bir kullanıcıya ihtiyacı vardır.

## <a name="how-do-i-create-a-user"></a>Bir kullanıcı nasıl oluşturulur?

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Microsoft Intune** bölmesini açtıktan sonra **Kullanıcılar**’ı seçin. **Tüm Kullanıcılar** sayfasında **+ Yeni kullanıcı**’yı seçin.
4. Kullanıcının **Ad** ve **Kullanıcı adı** gibi ayrıntılarını girin. Kullanıcı adının etki alanı adı kısmı şu etki alanlarından biri olmalıdır:
    - ilk varsayılan etki alanı adı olan “contoso.onmicrosoft.com” etki alanı adı veya
    - doğrulanmış, federasyon olmayan “contoso.com” gibi bir etki alanı adı.
5. **Gruplar**'ın altından kullanıcının ekleneceği bir [grup](get-started-groups.md) seçin.
6. Bir test cihazında oturum açmak üzere kullanabilmek için otomatik olarak oluşturulan kullanıcı parolasını kaydedin. Bu parolayı, hatırlayabilecekleri normal bir parola ile değiştirebilmeleri için kullanıcılara vermelisiniz.
7. **Kullanıcı** bölmesinde **Oluştur**’u seçin.

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
