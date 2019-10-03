---
title: Microsoft Intune Web uygulamaları ekleme
titleSuffix: ''
description: Microsoft Intune için Web uygulamaları (istemci-sunucu uygulamaları) ekleme hakkında bilgi edinin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/02/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a8beb8291ede1bf2fde32014fadf9f8cd52da5b6
ms.sourcegitcommit: fc356fd69beaeb3d69982b47e2bdffb6f7127f8c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/03/2019
ms.locfileid: "71830572"
---
# <a name="add-web-apps-to-microsoft-intune"></a>Microsoft Intune Web uygulamaları ekleme

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Intune, Web uygulamaları dahil olmak üzere çeşitli uygulama türlerini destekler. Bir Web uygulaması, bir istemci-sunucu uygulamasıdır. Sunucu, Kullanıcı arabirimi, içerik ve işlevleri içeren Web uygulamasını sağlar. Ayrıca, modern web barındırma platformları genellikle güvenlik, yük dengeleme ve diğer avantajlar sunar. Web uygulaması, Web 'de ayrı olarak korunur. Bu uygulama türünü işaret etmek için Microsoft Intune kullanırsınız. Ayrıca, bu uygulamaya erişebilen kullanıcı gruplarını da atarsınız. 

Kullanıcılarınız için bir uygulamayı yönetebilmeniz ve atayabilmeniz için önce uygulamayı Intune 'a ekleyin. Intune, kullanıcının cihaz giriş ekranında Web uygulaması için bir kısayol oluşturur.

> [!Note]
> Android iş profili cihazlarında Web uygulamaları desteklenmez. Web uygulamalarını başlatmak için kullanıcının cihazında bir tarayıcı yüklü olmalıdır.

## <a name="add-a-web-app-to-intune"></a>Intune 'a bir Web uygulaması ekleme
Web 'deki bir uygulamanın kısayolu olarak Intune 'a bir uygulama eklemek için aşağıdakileri yapın:

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
3. **Intune** bölmesinde, **istemci uygulamaları**' nı seçin.
4. **İstemci uygulamaları** iş yükü bölmesinde, **Yönet**altında **uygulamalar**' ı seçin.
5. **Uygulamalar** bölmesinde **Ekle**' yi seçin.
6. **Uygulama Ekle** bölmesinde, **uygulama türü** aşağı açılan listesinde, **Web bağlantı** türünü seçin.
7. **Yapılandır**' ı seçin.
8. **Uygulama bilgileri** bölmesinde aşağıdaki bilgileri ekleyin:
    - **Ad**: uygulamanın şirket portalında görüntülenecek olan adını girin. 

        > [!NOTE]
        > Uygulamayı dağıttıktan ve yükledikten sonra Intune Azure portalı aracılığıyla uygulamanın adını değiştirirseniz, uygulama artık komutları kullanarak hedeflenmeyecektir.

    - **Açıklama**: uygulama için bir açıklama girin. Bu açıklama şirket portalında kullanıcılara görüntülenir.
    - **Yayımcı**: Bu uygulamanın yayımcısının adını girin.
    - **Uygulama URL 'si**: atamak istediğiniz uygulamayı barındıran Web sitesinin URL 'sini girin.
    - **Kategori**: isteğe bağlı olarak, yerleşik uygulama kategorilerinden birini veya daha fazlasını veya oluşturduğunuz bir kategoriyi seçin. Bunun yapılması, kullanıcıların şirket portalına gözatarken uygulamayı bulmasını kolaylaştırır.
    - **Bunu şirket portalı öne çıkan uygulama olarak görüntüle**: kullanıcılar uygulamalara gözatarken Şirket portalının ana sayfasında uygulama paketini göze çarpacak şekilde göstermek için bu seçeneği belirleyin.
    - **Bu bağlantıyı açmak için yönetilen bir tarayıcı gerektir**: kullanıcılarınıza, Intune Managed Browser 'da açabildikleri bir Web sitesi veya Web uygulamasına bir bağlantı atamak için bu seçeneği belirleyin. Bu tarayıcının cihazında yüklü olması gerekir.
    - **Logo**: uygulamayla ilişkilendirilecek bir simgeyi karşıya yükleyin. Bu simge, kullanıcılar şirket portalına gözatarken uygulamayla birlikte görüntülenir.
9. **Tamam**’ı seçin.
10. **Uygulama Ekle** bölmesinde **Ekle**' yi seçin.

> [!Note]
> Kullanıcıların, Android cihazlara atanmış Web uygulamalarını görüntülemesi için Intune pencere öğesini giriş ekranına eklemesi gerekir.
>
> Şu anda, Intune Web uygulamalarının iOS cihazlarına dağıtılması yönetim profiliyle ilişkili olduğundan el ile kaldırılamaz. Dağıtım türünü, Intune portalında **kaldırmak** için değiştirebilirsiniz, bu noktada Web uygulamasının otomatik olarak kaldırılabileceği anlamına gelir. Ancak **, uygulamayı kaldırmak için uygulama**atama hedefini değiştirmeden önce dağıtımı kaldırırsanız, cihaz Intune 'a kaydedilmediği sürece web uygulaması cihazda kalıcı olarak yerinde kalır.

## <a name="next-steps"></a>Sonraki adımlar

Oluşturduğunuz uygulama, uygulamalar listesinde görüntülenir ve burada seçtiğiniz gruplara atayabilirsiniz. Yardım için bkz. [uygulamaları gruplara atama](apps-deploy.md). 
