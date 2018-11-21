---
title: Hızlı Başlangıç - Intune'da kullanıcı oluşturma
description: Hızlı Başlangıç - Intune'da kullanıcı oluşturma.
services: microsoft-intune
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: quickstart
ms.date: 10/30/2018
ms.author: erikje
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.openlocfilehash: b5653c67766a3312cf7ce2872e8b0cd4301b0e8b
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52189505"
---
# <a name="quickstart-create-a-user-and-assign-a-license-to-it"></a>Hızlı Başlangıç: Kullanıcı oluşturun ve ona bir lisans atayın

Bu hızlı başlangıçta bir kullanıcı oluşturacak ve ona bir lisans atayacaksınız. Intune'u kullanırken, şirket verilerine erişimi olmasını istediğiniz her kişinin bir kullanıcı hesabı olması gerekir. Daha sonra Intune yöneticileri, erişim denetimini yönetmek için bu kullanıcıları yapılandırabilir.

Bir Intune aboneliğiniz yoksa [ücretsiz bir deneme hesabı için kaydolun](free-trial-sign-up.md).

## <a name="sign-in-to-intune"></a>Intune'da oturum açma

[Intune](https://aka.ms/intuneportal)’da [Genel Yönetici veya Intune Hizmet yöneticisi](users-add.md#types-of-administrators) olarak oturum açın. Intune Deneme aboneliği oluşturduysanız aboneliği oluşturduğunuz hesap Genel yönetici rolüne sahip olur.

## <a name="create-a-user"></a>Bir kullanıcı oluşturun

Intune cihaz Yönetimi'ne kaydolmak için bir kullanıcı hesabı gerekir.

1. Intune'da, **Kullanıcılar** > **Tm kullanıcılar** > **Yeni kullanıcı**'yı seçin.
![Tarayıcı](media/quickstart-create-user/create-user.png)
2. **Ad** kutusuna *Dewey Kellum* gibi bir ad girin.
3. **Kullanıcı adı** kutusuna Dewey@contoso.onmicrosoft.com gibi bir kullanıcı tanımlayıcısı girin.

    > [!NOTE]
    > Müşteri etki alanı adınızı yapılandırmadıysanız Intune aboneliğini (veya [ücretsiz denemeyi](free-trial-sign-up.md#sign-up-for-a-microsoft-intune-free-trial)) oluşturmak için kullandığınız doğrulanmış etki alanı adını kullanın. 

4. **Parolayı göster**'i seçin ve bir test cihazında oturum açabilmek için otomatik olarak oluşturulan parolayı not edin.
5. **Oluştur**’u seçin.

## <a name="assign-a-license-to-the-user"></a>Kullanıcıya lisans atama

Bir kullanıcı oluşturduktan sonra, bu kullanıcıya bir Intune lisansı atamak için [Office 365 portalı](http://go.microsoft.com/fwlink/p/?LinkId=698854)'nı kullanmanız gerekir. Kendisine bir lisans atanmazsa kullanıcı cihazını Intune'a kaydedemez. 

1. Intune'da oturum açmak için kullandığınız kimlik bilgileriyle [Office 365 portalı](http://go.microsoft.com/fwlink/p/?LinkId=698854)'nda oturum açın.
2. **Kullanıcılar** > **Etkin Kullanıcılar**'ı > oluşturduğunuz kullanıcıyı seçin.
3. **Ürün lisansları**’nın yanında bulunan **Düzenle**’yi seçin.
4. **Konum** altında kullanıcı için bir konum seçin.
5. Intune lisansının (veya elinizdeki Intune’u içeren başka bir lisansın) yanındaki **Açık** seçeneğine tıklayın. Görüntülenen [ürün adı](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)** Azure yönetiminde hizmet planı olarak kullanılır 

   > [!NOTE]
   > Bu ayar, bu kullanıcı için lisanslarınızdan birini kullanır. Deneme ortamındaysanız bu lisansı daha sonra canlı ortamda gerçek bir kullanıcıya yeniden atayın.
6. **Kaydet** > **Kapat**’ı seçin.

Yeni etkin Intune kullanıcısı artık bir **Intune** lisansı kullandığını gösterir.

## <a name="clean-up-resources"></a>Kaynakları temizleme

Artık bu kullanıcıya ihtiyacınız kalmadıysa [Office 365 portalına](http://go.microsoft.com/fwlink/p/?LinkId=698854) gidip sırasıyla şunları seçerek kullanıcıyı silebilirsiniz: **Kullanıcılar** > **Etkin kullanıcılar** > *listeden kullanıcıyı seçin* > **Kullanıcıyı sil** > **Kullanıcıyı sil** > **Değişiklikleri onayla** > **Kapat**.

## <a name="next-steps"></a>Sonraki adımlar

Bu hızlı başlangıçta bir kullanıcı oluşturdunuz ve ona bir lisans atadınız. Intune’a kullanıcı ekleme hakkında daha fazla bilgi için bkz. [Intune’da kullanıcı ekleme ve kullanıcılara yönetici izni verme](users-add.md).

Bu Intune hızlı başlangıç serisini takip etmek için bir sonraki hızlı başlangıca ilerleyin.

> [!div class="nextstepaction"]
> [Hızlı Başlangıç: Kullanıcıları yönetmek için grup oluşturma](quickstart-create-group.md)
