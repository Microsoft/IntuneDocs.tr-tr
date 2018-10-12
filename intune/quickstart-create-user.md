---
title: Hızlı Başlangıç - Intune'da kullanıcı oluşturma
description: Hızlı Başlangıç - Intune'da kullanıcı oluşturma.
services: microsoft-intune
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: quickstart
ms.date: 09/21/2018
ms.author: erikje
ms.openlocfilehash: 6a1d591e635dccd99551d9b8d40e099724a85d77
ms.sourcegitcommit: 27eed5aba5c8bfafb079171081b68f75a6cbffaf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/22/2018
ms.locfileid: "46581811"
---
# <a name="quickstart-create-a-user-and-assign-a-license-to-it"></a>Hızlı Başlangıç: Kullanıcı oluşturun ve ona bir lisans atayın

Bu hızlı başlangıçta bir kullanıcı oluşturacak ve ona bir lisans atayacaksınız. Intune'u kullanırken, şirket verilerine erişimi olmasını istediğiniz her kişinin bir kullanıcı hesabı olması gerekir. Intune yöneticileri daha sonra, erişim denetimini yönetmek için bu kullanıcıları yapılandırabilir.

Bir Intune aboneliğiniz yoksa [ücretsiz bir deneme hesabı için kaydolun](free-trial-sign-up.md).

## <a name="sign-in-to-intune"></a>Intune'da oturum açma

[Intune](https://aka.ms/intuneportal)'da Genel Yönetici veya Intune Hizmet Yöneticisi olarak oturum açın.

## <a name="create-a-user"></a>Bir kullanıcı oluşturun

Intune cihaz Yönetimi'ne kaydolmak için bir kullanıcı hesabı gerekir.

1. Intune'da, **Kullanıcılar** > **Tm kullanıcılar** > **Yeni kullanıcı**'yı seçin.
![Tarayıcı](media/quickstart-create-user/create-user.png)
2. **Ad** kutusuna *Dewey Kellum* adını girin.
3. **Kullanıcı adı** kutusuna *Dewey@contoso.onmicrosoft.com* girin.
4. **Gruplar** > **Herkes** > **Seç**'i seçin.
5. **Parolayı göster**'i seçin ve bir test cihazında oturum açabilmek için otomatik olarak oluşturulan parolayı not edin.
6. **Oluştur**’u seçin.

## <a name="assign-a-license-to-the-user"></a>Kullanıcıya lisans atama

Bir kullanıcı oluşturduktan sonra, bu kullanıcıya bir Intune lisansı atamak için [Office 365 portalı](http://go.microsoft.com/fwlink/p/?LinkId=698854)'nı kullanmanız gerekir. Kendisine bir lisans atanmazsa kullanıcı cihazını Intune'a kaydedemez. 

1. Intune'da oturum açmak için kullandığınız kimlik bilgileriyle [Office 365 portalı](http://go.microsoft.com/fwlink/p/?LinkId=698854)'nda oturum açın.
2. **Kullanıcılar** > **Etkin Kullanıcılar**'ı > oluşturduğunuz kullanıcıyı seçin.
3. **Konum** altında kullanıcı için bir konum seçin.
3. **Ürün lisansları**'nı seçip **Enterprise Mobility + Security E3**'ü (veya elinizdeki Intune'u içeren başka bir lisansı) **Açık** olarak ayarlayın.
   > [!NOTE]
   > Bu işlem, kullanıcı için lisanslarınızdan birini kullanır. Yayındaki ortamınızı kullanıyorsanız bu lisansın kullanımını, daha sonra gerçek bir kullanıcıya yeniden atayabilmek için kapatabilirsiniz.
5. **Kaydet**’i seçin.

## <a name="clean-up-resources"></a>Kaynakları temizleme

Bu kullanıcı artık gerekmiyorsa, **Kullanıcılar** > **Tüm kullanıcılar** > kullanıcıyı listeden seçin > **Kullanıcı sil** > **Evet**'i seçerek silebilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

Bu hızlı başlangıçta bir kullanıcı oluşturdunuz ve ona bir lisans atadınız. Artık bu kullanıcıyı bir gruba atayabilirsiniz.

> [!div class="nextstepaction"]
> [Grup oluşturma](quickstart-create-group.md)
