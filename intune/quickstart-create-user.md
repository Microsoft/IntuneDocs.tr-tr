---
title: Hızlı Başlangıç - Intune'da kullanıcı oluşturma
description: Hızlı Başlangıç - Intune'da kullanıcı oluşturma.
services: microsoft-intune
author: ErikjeMS
ms.service: microsoft-intune
ms.localizationpriority: high
ms.topic: quickstart
ms.date: 03/25/2019
ms.author: erikje
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.collection: M365-identity-device-management
ms.openlocfilehash: 398b8c748fddfa032194cfa60547d76322e28c9a
ms.sourcegitcommit: 2a7d621587471822b1428440b24f08c8722612dd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70234814"
---
# <a name="quickstart-create-a-user-in-intune-and-assign-them-a-license"></a>Hızlı başlangıç Intune 'da bir kullanıcı oluşturun ve bu kullanıcılara bir lisans atayın

Bu hızlı başlangıçta bir Kullanıcı oluşturacak ve sonra bu kullanıcılara bir Intune lisansı atayacaksınız. Intune kullanırken, şirket verilerine erişim sağlamak istediğiniz her kişinin kendi Kullanıcı hesabı olması gerekir. Intune yöneticileri, daha sonra erişim denetimini yönetmek için kullanıcıları yapılandırabilir.

Bir Intune aboneliğiniz yoksa [ücretsiz bir deneme hesabı için kaydolun](free-trial-sign-up.md).

## <a name="sign-in-to-intune"></a>Intune'da oturum açma

[Intune](https://aka.ms/intuneportal) 'da [genel yönetici veya Intune Hizmet Yöneticisi](users-add.md#types-of-administrators)olarak oturum açın. Bir Intune deneme aboneliği oluşturduysanız, aboneliği oluşturduğunuz hesap genel yöneticime sahip olur.

## <a name="create-a-user"></a>Kullanıcı oluşturma

Kullanıcıların Intune cihaz yönetimine kaydolmak için bir kullanıcı hesabı olması gerekir. Yeni bir kullanıcı oluşturmak için:

1. Intune'da, **Kullanıcılar** > **Tm kullanıcılar** > **Yeni kullanıcı**'yı seçin.
![Tarayıcı](media/quickstart-create-user/create-user.png)
2. **Ad** kutusuna *Dewey Kellum* gibi bir ad girin.
3. **Kullanıcı adı** kutusuna Dewey@contoso.onmicrosoft.com gibi bir kullanıcı tanımlayıcısı girin.

    > [!NOTE]
    > Müşteri etki alanı adınızı yapılandırmadıysanız, Intune aboneliğini (veya [ücretsiz denemeyi](free-trial-sign-up.md#sign-up-for-a-microsoft-intune-free-trial)) oluşturmak için kullandığınız doğrulanmış etki alanı adını kullanın. 

4. **Parolayı göster**'i seçin ve bir test cihazında oturum açabilmek için otomatik olarak oluşturulan parolayı not edin.
5. **Oluştur**’u seçin.

## <a name="assign-a-license-to-the-user"></a>Kullanıcıya lisans atama

Bir kullanıcı oluşturduktan sonra, bu kullanıcılara bir Intune lisansı atamak için [Microsoft 365 Yönetim merkezini](http://go.microsoft.com/fwlink/p/?LinkId=698854) kullanmanız gerekir. Kullanıcıya bir lisans atamadıysanız, cihazlarını Intune 'a kaydedemeyecek. 

Bir kullanıcıya bir Intune lisansı atamak için:

1. [Microsoft 365 Yönetim merkezinde](http://go.microsoft.com/fwlink/p/?LinkId=698854) Intune 'da oturum açmak için kullandığınız kimlik bilgileriyle oturum açın.
2. **Kullanıcılar** > **etkin kullanıcılar** > seçin ve yeni oluşturduğunuz kullanıcıyı seçin.
3. **Ürün lisansları**’nın yanında bulunan **Düzenle**’yi seçin.
4. **Konum** altında kullanıcı için bir konum seçin.
5. Intune lisansının (veya Intune içeren başka bir lisansın) **yanındaki ileri '** ye tıklayın. Görüntülenen [ürün adı](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)** Azure yönetiminde hizmet planı olarak kullanılır 

   > [!NOTE]
   > Bu ayar, bu kullanıcı için lisanslarınızdan birini kullanır. Deneme ortamındaysanız bu lisansı daha sonra canlı ortamda gerçek bir kullanıcıya yeniden atayın.
6. **Kaydet** > **Kapat**’ı seçin.

Yeni etkin Intune kullanıcısı artık bir **Intune** lisansı kullandığını gösterecektir.

## <a name="clean-up-resources"></a>Kaynakları temizleme

Bu kullanıcıya artık ihtiyacınız yoksa, [Microsoft 365 yönetim merkezine](http://go.microsoft.com/fwlink/p/?LinkId=698854) giderek kullanıcıları silebilir ve **Kullanıcılar** > **etkin kullanıcılar** > liste > silme*bölümünde kullanıcıyı seçer*' ı seçin.**Kullanıcı silme**Kullanıcısilmeyi > değişikliklerikapatma > . > 

## <a name="next-steps"></a>Sonraki adımlar

Bu hızlı başlangıçta bir Kullanıcı oluşturdunuz ve bunlara bir Intune lisansı atadınız. Intune’a kullanıcı ekleme hakkında daha fazla bilgi için bkz. [Intune’da kullanıcı ekleme ve kullanıcılara yönetici izni verme](users-add.md).

Bu Intune hızlı başlangıç serisini takip etmek için bir sonraki hızlı başlangıca ilerleyin.

> [!div class="nextstepaction"]
> [Hızlı başlangıç Kullanıcıları yönetmek için bir grup oluşturma](quickstart-create-group.md)
