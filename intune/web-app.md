---
title: Microsoft Intune’a web uygulamaları ekleme
titleSuffix: ''
description: Web apps (istemci-sunucu uygulamaları) Microsoft Intune ekleme hakkında bilgi edinin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/19/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: dddf5d76177a31d67190a5c259845c199a0fce2f
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57235506"
---
# <a name="add-web-apps-to-microsoft-intune"></a>Microsoft Intune’a web uygulamaları ekleme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune, web uygulamaları da dahil olmak üzere çeşitli uygulama türlerini destekler. Web uygulaması, bir istemci-sunucu uygulamasıdır. Sunucu; kullanıcı arabirimi, içerik ve işlevleri içeren web uygulamasını sağlar. Ayrıca modern web barındırma platformları çoğu zaman güvenlik, yük dengeleme ve diğer yararlar da sunar. Web uygulaması web’de ayrı olarak korunur. Bu uygulama türüne işaret etmek için Microsoft Intune kullanırsınız. Bu uygulamaya erişebilecek kullanıcı gruplarını da atarsınız. 

Kullanıcılarınız için uygulamaları yönetebilmek ve atayabilmek için önce uygulamayı Intune’a ekleyin. Intune, kullanıcının cihazındaki giriş ekranında web uygulaması için bir kısayol oluşturur.

> [!Note]
> Android iş profili ve macOS cihazlarda web uygulamaları desteklenmez.

## <a name="add-a-web-app-to-intune"></a>Intune’a bir web uygulaması ekleme
Bir uygulamayı web’de uygulamanın kısayolu olarak Intune’a eklemek için:

1. [Azure Portal](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin.  
    Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** bölmesinde **İstemci uygulamaları**’nı seçin.
4. **İstemci uygulamaları** iş yükü bölmesindeki **Yönet**’in altında **Uygulamalar**’ı seçin.
5. **Uygulamalar** bölmesinde **Ekle**’yi seçin.
6. **Uygulama ekle** bölmesinde, **Uygulama türü** açılan listesinden **Web bağlantısı** türünü seçin.
7. **Yapılandır**’ı seçin.
8. **Uygulama bilgileri** bölmesinde aşağıdaki bilgileri ekleyin:
    - **Ad**:  Şirket portalı'nda görüntülenecek olduğu gibi bir uygulama adı girin. 
    
        > [!NOTE]
        > Uygulamayı dağıttıktan ve yükledikten sonra Intune Azure portalı aracılığıyla uygulamanın adını değiştirirseniz, uygulama artık komutlar kullanılarak hedeflenemez.
    
    - **Açıklama**: Uygulama için bir açıklama girin. Bu açıklama Şirket Portalı’nda kullanıcılara görüntülenir.Açıklama şirket portalında kullanıcılara görüntülenir.
    - **Yayımcı**: Bu uygulamanın yayımcısının adını girin.
    - **Uygulama URL'sini**: Atamak istediğiniz uygulamayı barındıran Web sitesinin URL'sini girin.
    - **Kategori**: İsteğe bağlı olarak, bir veya daha fazla yerleşik uygulama kategorilerinden veya kendi oluşturduğunuz bir kategoriyi seçin. Böylelikle, Şirket Portalı’na göz atarken kullanıcıların uygulamayı bulmaları kolaylaşır.
    - **Bunu şirket Portalı'nda öne çıkan uygulama olarak görüntüle**: Kullanıcılar uygulamalara göz atarken uygulama paketinin şirket Portalı'nın ana sayfasında göze çarpacak şekilde görüntüleyin için. Bu seçeneği belirleyin.
    - **Bu bağlantının açılabilmesi için yönetilen tarayıcı gerektir**: Intune ile yönetilen tarayıcıda açmak bir Web sitesi veya web uygulaması için bir bağlantı, kullanıcılara atamak için bu seçeneği belirleyin. Bu tarayıcı cihazlarında yüklü olmalıdır.
    - **Logo**: Uygulamayla ilişkilendirilecek bir simgeyi karşıya yükleyin. Bu simge, kullanıcılar şirket portalına gözatarken uygulamayla birlikte görüntülenir.
9. **Tamam**’ı seçin.
10. **Uygulama ekle** bölmesinde **Ekle**’yi seçin.

> [!Note]
> Android cihazlarına atanmış web uygulamalarını görüntüleyebilmek için kullanıcıların giriş ekranlarına Intune pencere öğesini eklemeleri gerekir.
>
> Şu anda Intune web uygulamalarının iOS cihazlara dağıtımı, yönetim profiliyle ilişkili ve el ile kaldırılamaz. Intune portalında dağıtım türünü **Kaldır** seçeneğine değiştirerek web uygulamasının otomatik olarak kaldırılmasını sağlayabilirsiniz. Ancak uygulama ataması amacını **Kaldır** seçeneğine değiştirmeden dağıtımı kaldırırsanız, cihazın kaydı Intune’dan kaldırılana kadar web uygulaması cihazda kalır.

## <a name="next-steps"></a>Sonraki adımlar

Oluşturduğunuz uygulama, uygulamalar listesinde görüntülenir ve burada uygulamayı seçtiğiniz gruplara atayabilirsiniz. Yardım için bkz. [Uygulamaları gruplara atama](apps-deploy.md). 
