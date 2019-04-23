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
ms.openlocfilehash: b49595493b5db3e5735e0a4717c27e91f058b8d8
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61511373"
---
# <a name="quickstart-create-a-user-in-intune-and-assign-them-a-license"></a>Hızlı Başlangıç: Intune'a bir kullanıcı oluşturun ve onlara lisans atayın

Bu hızlı başlangıçta, bir kullanıcı oluşturun ve bunları Intune atayabilirsiniz. Şirket verilerine erişimi olmasını istediğiniz her kişi, Intune kullanırken, kendi kullanıcı hesabı olması gerekir. Intune yöneticileri, kullanıcıların daha sonra erişim denetimini yönetme yapılandırabilirsiniz.

Bir Intune aboneliğiniz yoksa [ücretsiz bir deneme hesabı için kaydolun](free-trial-sign-up.md).

## <a name="sign-in-to-intune"></a>Intune'da oturum açma

Oturum [Intune](https://aka.ms/intuneportal) olarak bir [genel yönetici veya Intune Hizmet Yöneticisi](users-add.md#types-of-administrators). Intune Deneme aboneliği oluşturduysanız aboneliği oluşturduğunuz hesap Genel yönetici rolüne sahip olur.

## <a name="create-a-user"></a>Kullanıcı oluşturma

Kullanıcıların, Intune cihaz Yönetimi'nde kaydetmek için bir kullanıcı hesabı olmalıdır. Yeni bir kullanıcı oluşturmak için:

1. Intune'da, **Kullanıcılar** > **Tm kullanıcılar** > **Yeni kullanıcı**'yı seçin.
![Tarayıcı](media/quickstart-create-user/create-user.png)
2. **Ad** kutusuna *Dewey Kellum* gibi bir ad girin.
3. **Kullanıcı adı** kutusuna Dewey@contoso.onmicrosoft.com gibi bir kullanıcı tanımlayıcısı girin.

    > [!NOTE]
    > Müşteri etki alanı adınızı yapılandırmadıysanız, Intune aboneliğini oluşturmak için kullanılan doğrulanmış etki alanı adını kullanın (veya [ücretsiz deneme sürümü](free-trial-sign-up.md#sign-up-for-a-microsoft-intune-free-trial)). 

4. **Parolayı göster**'i seçin ve bir test cihazında oturum açabilmek için otomatik olarak oluşturulan parolayı not edin.
5. **Oluştur**’u seçin.

## <a name="assign-a-license-to-the-user"></a>Kullanıcıya lisans atama

Bir kullanıcı oluşturduktan sonra kullanmalısınız [Microsoft 365 Yönetim merkezini](http://go.microsoft.com/fwlink/p/?LinkId=698854) bir Intune lisansı atamak. Kullanıcı bir lisans atamazsanız, cihazlarını Intune'a kaydetmeleri mümkün olmayacaktır. 

Bir kullanıcıya bir Intune lisansı atamak için:

1. Oturum [Microsoft 365 Yönetim merkezini](http://go.microsoft.com/fwlink/p/?LinkId=698854) ile aynı kimlik bilgilerini Intune'da oturum açma için kullanılır.
2. Seçin **kullanıcılar** > **etkin kullanıcılar** > ve yeni oluşturduğunuz kullanıcıyı seçin.
3. **Ürün lisansları**’nın yanında bulunan **Düzenle**’yi seçin.
4. **Konum** altında kullanıcı için bir konum seçin.
5. Intune lisansının (veya elinizdeki Intune’u içeren başka bir lisansın) yanındaki **Açık** seçeneğine tıklayın. Görüntülenen [ürün adı](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)** Azure yönetiminde hizmet planı olarak kullanılır 

   > [!NOTE]
   > Bu ayar, bu kullanıcı için lisanslarınızdan birini kullanır. Deneme ortamındaysanız bu lisansı daha sonra canlı ortamda gerçek bir kullanıcıya yeniden atayın.
6. **Kaydet** > **Kapat**’ı seçin.

Yeni etkin Intune kullanıcısı artık bir **Intune** lisansı kullandığını gösterir.

## <a name="clean-up-resources"></a>Kaynakları temizleme

Bu kullanıcı artık gerekmiyorsa, giderek kullanıcı silebilir [Microsoft 365 Yönetim merkezini](http://go.microsoft.com/fwlink/p/?LinkId=698854) ve **kullanıcılar** > **etkin kullanıcılar**  >  *listeden kullanıcı seçin* > **kullanıcıyı silme** > **kullanıcıyı silme** > **Onayla değişiklikleri** > **Kapat**.

## <a name="next-steps"></a>Sonraki adımlar

Bu hızlı başlangıçta, bir kullanıcının oluşturduğu ve bir Intune lisansı atanmış. Intune’a kullanıcı ekleme hakkında daha fazla bilgi için bkz. [Intune’da kullanıcı ekleme ve kullanıcılara yönetici izni verme](users-add.md).

Bu Intune hızlı başlangıç serisini takip etmek için bir sonraki hızlı başlangıca ilerleyin.

> [!div class="nextstepaction"]
> [Hızlı Başlangıç: Kullanıcıları yönetmek için bir grup oluşturun](quickstart-create-group.md)
