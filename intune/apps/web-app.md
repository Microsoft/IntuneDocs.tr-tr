---
title: Microsoft Intune’a web uygulamaları ekleme
titleSuffix: ''
description: Microsoft Intune için Web uygulamaları (istemci-sunucu uygulamaları) ekleme hakkında bilgi edinin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/02/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6600c75ce3e6120143b17fb863670b2eb423a09f
ms.sourcegitcommit: ae6f2e7812e7fd36f2393b8f4b6cd8de63777b2c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73592052"
---
# <a name="add-web-apps-to-microsoft-intune"></a>Microsoft Intune’a web uygulamaları ekleme

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Intune, web uygulamaları da dahil olmak üzere çeşitli uygulama türlerini destekler. Web uygulaması, bir istemci-sunucu uygulamasıdır. Sunucu; kullanıcı arabirimi, içerik ve işlevleri içeren web uygulamasını sağlar. Ayrıca modern web barındırma platformları çoğu zaman güvenlik, yük dengeleme ve diğer yararlar da sunar. Web uygulaması web’de ayrı olarak korunur. Bu uygulama türüne işaret etmek için Microsoft Intune kullanırsınız. Bu uygulamaya erişebilecek kullanıcı gruplarını da atarsınız. 

Kullanıcılarınız için uygulamaları yönetebilmek ve atayabilmek için önce uygulamayı Intune’a ekleyin. 

Intune, kullanıcının cihazında Web uygulaması için bir kısayol oluşturur. İOS cihazlarında, giriş ekranına Web uygulaması için bir kısayol eklenir. Android cihazlarda, Intune şirket portalı pencere öğesine Web uygulaması için bir kısayol eklenir ve pencere öğesinin Kullanıcı tarafından el ile sabitlenilmesi gerekir. Windows cihazlarında, Web uygulamasının bir kısayolu Başlat menüsüne yerleştirilir.

> [!Note]
> Web uygulamalarını başlatmak için kullanıcının cihazında bir tarayıcı yüklü olmalıdır.

## <a name="add-a-web-app-to-intune"></a>Intune’a bir web uygulaması ekleme
Bir uygulamayı web’de uygulamanın kısayolu olarak Intune’a eklemek için:

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
3. **Intune** bölmesinde **İstemci uygulamaları**’nı seçin.
4. **İstemci uygulamaları** iş yükü bölmesindeki **Yönet**’in altında **Uygulamalar**’ı seçin.
5. **Uygulamalar** bölmesinde **Ekle**’yi seçin.
6. **Uygulama ekle** bölmesinde, **Uygulama türü** açılan listesinden **Web bağlantısı** türünü seçin.
7. **Yapılandır**’ı seçin.
8. **Uygulama bilgileri** bölmesinde aşağıdaki bilgileri ekleyin:
    - **Ad**: Şirket portalında görüntülendiği şekliyle uygulamanın adını girin. 

        > [!NOTE]
        > Uygulamayı dağıttıktan ve yükledikten sonra Intune Azure portalı aracılığıyla uygulamanın adını değiştirirseniz, uygulama artık komutlar kullanılarak hedeflenemez.

    - **Açıklama**: Uygulama için bir açıklama girin. Bu açıklama Şirket Portalı’nda kullanıcılara görüntülenir.Açıklama şirket portalında kullanıcılara görüntülenir.
    - **Yayımcı**: Bu uygulamanın yayımcısının adını girin.
    - **Uygulama URL’si**: Atamak istediğiniz uygulamayı barındıran web sitesinin URL’sini girin.
    - **Kategori**: İsteğe bağlı olarak, yerleşik uygulama kategorilerinden veya kendi oluşturduğunuz kategorilerden birini ya da birkaçını seçin. Böylelikle, Şirket Portalı’na göz atarken kullanıcıların uygulamayı bulmaları kolaylaşır.
    - **Bunu Şirket Portalı’nda öne çıkan uygulama olarak görüntüle**: Bu seçenek uygulama paketini, kullanıcılar uygulamalara göz atarken Şirket Portalı’nın ana sayfasında göze çarpacak şekilde görüntüler.
    - **Bu bağlantının açılabilmesi için bir yönetilen tarayıcı gerektir**: Kullanıcılara, Intune ile yönetilen tarayıcıda açabilecekleri bir web sitesi veya web uygulaması bağlantısı atayın. Bu tarayıcı cihazlarında yüklü olmalıdır.
    - **Logo**: Uygulamayla ilişkilendirilecek bir simgeyi karşıya yükleyin. Bu simge, kullanıcılar şirket portalına gözatarken uygulamayla birlikte görüntülenir.
9. **Tamam**’ı seçin.
10. **Uygulama ekle** bölmesinde **Ekle**’yi seçin.

> [!Note]
> Android cihazlarına atanmış web uygulamalarını görüntüleyebilmek için kullanıcıların giriş ekranlarına Intune pencere öğesini eklemeleri gerekir.
>
> Şu anda Intune web uygulamalarının iOS cihazlara dağıtımı, yönetim profiliyle ilişkili ve el ile kaldırılamaz. Intune portalında dağıtım türünü **Kaldır** seçeneğine değiştirerek web uygulamasının otomatik olarak kaldırılmasını sağlayabilirsiniz. Ancak uygulama ataması amacını **Kaldır** seçeneğine değiştirmeden dağıtımı kaldırırsanız, cihazın kaydı Intune’dan kaldırılana kadar web uygulaması cihazda kalır.

## <a name="next-steps"></a>Sonraki adımlar

Oluşturduğunuz uygulama, uygulamalar listesinde görüntülenir ve burada uygulamayı seçtiğiniz gruplara atayabilirsiniz. Yardım için bkz. [Uygulamaları gruplara atama](apps-deploy.md). 
