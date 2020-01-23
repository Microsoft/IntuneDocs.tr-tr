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
ms.openlocfilehash: 161a18f56256f4a056f32d677759bdb6efe4cd8b
ms.sourcegitcommit: 70b40aa4743c8396f8d6a0163893c4a337d67c48
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2020
ms.locfileid: "76540882"
---
# <a name="quickstart-create-a-user-in-intune-and-assign-them-a-license"></a>Hızlı başlangıç: Intune 'da Kullanıcı oluşturma ve onlara lisans atama

Bu hızlı başlangıçta bir Kullanıcı oluşturacak ve sonra bu kullanıcılara bir Intune lisansı atayacaksınız. Intune kullanırken, şirket verilerine erişim sağlamak istediğiniz her kişinin kendi Kullanıcı hesabı olması gerekir. Intune yöneticileri, daha sonra erişim denetimini yönetmek için kullanıcıları yapılandırabilir.

Bir Intune aboneliğiniz yoksa [ücretsiz bir deneme hesabı için kaydolun](free-trial-sign-up.md).

## <a name="prerequisites"></a>Prerequisites

- Microsoft Intune aboneliği - [ücretsiz deneme hesabına kaydolun](../fundamentals/free-trial-sign-up.md).

## <a name="sign-in-to-intune-in-the-microsoft-endpoint-manager"></a>Microsoft uç nokta yöneticisinde Intune 'da oturum açma

[Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431) [genel yönetici veya Intune Hizmet Yöneticisi](users-add.md#types-of-administrators)olarak oturum açın. Bir Intune deneme aboneliği oluşturduysanız, aboneliği oluşturduğunuz hesap genel yöneticime sahip olur.

## <a name="create-a-user"></a>Kullanıcı oluşturma

Kullanıcıların Intune cihaz yönetimine kaydolmak için bir kullanıcı hesabı olması gerekir. Yeni bir kullanıcı oluşturmak için:

1. Microsoft Uç Nokta Yöneticisi 'nde **kullanıcılar** > **tüm kullanıcılar** > **Yeni Kullanıcı**' ı seçin.
    Microsoft uç nokta yöneticisinde ![Yeni Kullanıcı Ekle ' yi seçin](./media/quickstart-create-user/create-user.png)
2. **Ad** kutusuna *Dewey Kellum* gibi bir ad girin.
    Kullanıcı ayrıntıları eklemek ![](./media/quickstart-create-user/create-user-02.png)
3. **Kullanıcı adı** kutusuna Dewey@contoso.onmicrosoft.com gibi bir kullanıcı tanımlayıcısı girin.

    > [!NOTE]
    > Müşteri etki alanı adınızı yapılandırmadıysanız, Intune aboneliğini (veya [ücretsiz denemeyi](free-trial-sign-up.md#sign-up-for-a-microsoft-intune-free-trial)) oluşturmak için kullandığınız doğrulanmış etki alanı adını kullanın. 

4. Bir test cihazında oturum açabilmeniz için **parolayı göster** ' e tıklayın ve otomatik olarak oluşturulan parolayı bir yere iade edin.
5. **Oluştur**'u tıklatın.

## <a name="assign-a-license-to-the-user"></a>Kullanıcıya lisans atama

Bir kullanıcı oluşturduktan sonra, bu kullanıcılara bir Intune lisansı atamak için [Microsoft 365 Yönetim merkezini](https://go.microsoft.com/fwlink/p/?LinkId=698854) kullanmanız gerekir. Kullanıcıya bir lisans atamadıysanız, cihazlarını Intune 'a kaydedemeyecek. 

Bir kullanıcıya bir Intune lisansı atamak için:

1. [Microsoft 365 Yönetim merkezinde](https://go.microsoft.com/fwlink/p/?LinkId=698854) Intune 'da oturum açmak için kullandığınız kimlik bilgileriyle oturum açın.
2. **Kullanıcıları** > **etkin kullanıcılar** > seçin ve yeni oluşturduğunuz kullanıcıyı seçin.
3. **Lisanslar ve uygulamalar** sekmesine tıklayın.
4. **Konum Seç**bölümünde, zaten ayarlanmamışsa Kullanıcı için bir konum seçin.
2. Lisanslar bölümünde **Intune** onay kutusunu seçin. Başka bir lisans Intune içeriyorsa, bu lisansı seçebilirsiniz. Görüntülenmiş [ürün adı](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)* *, Azure yönetiminde hizmet planı olarak kullanılır.

    ![Konumu ve Intune lisansını seçin](./media/quickstart-create-user/create-user-03.png)

   > [!NOTE]
   > Bu ayar, bu kullanıcı için lisanslarınızdan birini kullanır. Deneme ortamındaysanız bu lisansı daha sonra canlı ortamda gerçek bir kullanıcıya yeniden atayın.

6. **Değişiklikleri Kaydet**' i seçin.

Yeni etkin Intune kullanıcısı artık bir **Intune** lisansı kullandığını gösterecektir.

## <a name="clean-up-resources"></a>Kaynakları temizleme

Bu kullanıcıya artık ihtiyacınız yoksa, [Microsoft 365 yönetim merkezine](https://go.microsoft.com/fwlink/p/?LinkId=698854) giderek **kullanıcıları** silebilir > *Listeden Kullanıcı seçin* > kullanıcı *Sil simgesini* ** > Kullanıcı Sil > ** **Kapat**' ı seçin.

   ![Sil simgesini seçin](./media/quickstart-create-user/create-user-04.png)

## <a name="next-steps"></a>Sonraki adımlar

Bu hızlı başlangıçta bir Kullanıcı oluşturdunuz ve bunlara bir Intune lisansı atadınız. Intune’a kullanıcı ekleme hakkında daha fazla bilgi için bkz. [Intune’da kullanıcı ekleme ve kullanıcılara yönetici izni verme](users-add.md).

Bu Intune hızlı başlangıç serisini takip etmek için bir sonraki hızlı başlangıca ilerleyin.

> [!div class="nextstepaction"]
> [Hızlı Başlangıç: Kullanıcıları yönetmek için grup oluşturma](../quickstart-create-group.md)
