---
title: Hızlı Başlangıç - Intune'da kullanıcı oluşturma
description: Hızlı Başlangıç - Intune'da kullanıcı oluşturma.
services: microsoft-intune
author: ErikjeMS
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.topic: quickstart
ms.date: 01/17/2020
ms.author: erikje
ms.manager: dougeby
ms.assetid: 820fcb18-0927-4ebd-be79-dce92b51c261
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.collection: M365-identity-device-management
ms.openlocfilehash: f6aa57b71e052e3fc8566fcdff8bdd9ef5d1c39e
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2020
ms.locfileid: "76754499"
---
# <a name="quickstart-create-a-user-in-intune-and-assign-the-user-a-license"></a>Hızlı başlangıç: Intune 'da Kullanıcı oluşturma ve kullanıcıya lisans atama

Bu hızlı başlangıçta bir Kullanıcı oluşturacak ve sonra kullanıcıya bir Intune lisansı atayacaksınız. Intune kullandığınızda şirket verilerine erişim sağlamak istediğiniz her kişinin kendi Kullanıcı hesabı olması gerekir. Intune yöneticileri, daha sonra erişim denetimini yönetmek için kullanıcıları yapılandırabilir.

## <a name="prerequisites"></a>Prerequisites

- Microsoft Intune aboneliği. [Ücretsiz deneme hesabı Için kaydolun](../fundamentals/free-trial-sign-up.md).

## <a name="sign-in-to-intune-in-microsoft-endpoint-manager"></a>Microsoft Endpoint Manager 'da Intune 'da oturum açma

[Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431) [genel yönetici veya Intune Hizmet Yöneticisi](users-add.md#types-of-administrators)olarak oturum açın. Bir Intune deneme aboneliği oluşturduysanız, aboneliği oluşturduğunuz hesap genel yöneticime sahip olur.

## <a name="create-a-user"></a>Kullanıcı oluşturma

Kullanıcının Intune cihaz yönetimine kaydolması için bir kullanıcı hesabı olması gerekir. Yeni bir kullanıcı oluşturmak için:

1. Microsoft Endpoint Manager 'da **kullanıcılar** > **tüm kullanıcılar** > **Yeni Kullanıcı**: ![Microsoft Uç Nokta Yöneticisi 'nde Yeni Kullanıcı ' yı seçin](./media/quickstart-create-user/create-user.png)
2. **Ad** kutusuna, *Kellum*: ![Kullanıcı](./media/quickstart-create-user/create-user-02.png) ayrıntıları Ekle gibi bir ad girin.
3. **Kullanıcı adı** kutusuna, Dewey@contoso.onmicrosoft.comgibi bir kullanıcı tanımlayıcısı girin.

    > [!NOTE]
    > Müşteri etki alanı adınızı yapılandırmadıysanız, Intune aboneliğini (veya [ücretsiz denemeyi](free-trial-sign-up.md#sign-up-for-a-microsoft-intune-free-trial)) oluşturmak için kullandığınız doğrulanmış etki alanı adını kullanın. 

4. **Parolayı göster** ' i seçin ve bir test cihazında oturum açabilmeniz için otomatik olarak oluşturulan parolayı anımsadığınızdan emin olun.
5. **Oluştur**’u seçin.

## <a name="assign-a-license-to-the-user"></a>Kullanıcıya lisans atama

Bir kullanıcı oluşturduktan sonra, kullanıcıya bir Intune lisansı atamak için [Microsoft 365 Yönetim merkezini](https://go.microsoft.com/fwlink/p/?LinkId=698854) kullanmanız gerekir. Kullanıcıya bir lisans atamadıysanız, cihazlarını Intune 'a kaydedemeyecek.

Bir kullanıcıya bir Intune lisansı atamak için:

1. [Microsoft 365 Yönetim merkezinde](https://go.microsoft.com/fwlink/p/?LinkId=698854) Intune 'da oturum açmak için kullandığınız kimlik bilgileriyle oturum açın.
2. **Etkin kullanıcılar** > **Kullanıcılar** ' ı seçin ve ardından yeni oluşturduğunuz kullanıcıyı seçin.
3. **Lisanslar ve uygulamalar** sekmesini seçin.
4. **Konum Seç**' in altında, henüz ayarlanmamışsa Kullanıcı için bir konum seçin.
2. **Lisanslar** bölümünde **Intune** onay kutusunu seçin. Başka bir lisans Intune içeriyorsa, bu lisansı seçebilirsiniz. Görüntülenmiş [ürün adı](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference) , Azure yönetiminde hizmet planı olarak kullanılır.

    ![Konumu ve Intune lisansını seçin](./media/quickstart-create-user/create-user-03.png)

   > [!NOTE]
   > Bu ayar, Kullanıcı için lisanslarınızdan birini kullanır. Deneme ortamı kullanıyorsanız, bu lisansı daha sonra canlı bir ortamda gerçek bir kullanıcıya yeniden atayacaksınız.

6. Seçin **değişiklikleri kaydetmek**.

Yeni etkin Intune kullanıcısı artık bir **Intune** lisansı kullandığını gösterecektir.

## <a name="clean-up-resources"></a>Kaynakları temizleme

Bu kullanıcıya artık ihtiyacınız yoksa, [Microsoft 365 yönetim merkezine](https://go.microsoft.com/fwlink/p/?LinkId=698854) gidip Kullanıcı > **kullanıcıları** * > Kullanıcı sil* *simgesini* ** > kullanıcıyı sil > ** **Kapat**' ı seçerek kullanıcıyı silebilirsiniz.

   ![Sil simgesini seçin](./media/quickstart-create-user/create-user-04.png)

## <a name="next-steps"></a>Sonraki adımlar

Bu hızlı başlangıçta bir Kullanıcı oluşturdunuz ve bu kullanıcıya bir Intune lisansı atadınız. Intune’a kullanıcı ekleme hakkında daha fazla bilgi için bkz. [Intune’da kullanıcı ekleme ve kullanıcılara yönetici izni verme](users-add.md).

Bu Intune hızlı başlangıç dizisine devam etmek için sonraki hızlı başlangıca gidin:

> [!div class="nextstepaction"]
> [Hızlı Başlangıç: Kullanıcıları yönetmek için grup oluşturma](../quickstart-create-group.md)
