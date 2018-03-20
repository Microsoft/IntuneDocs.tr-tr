---
title: "Web uygulamalarını Microsoft Intune’a ekleme"
titleSuffix: 
description: "Microsoft Intune'a web uygulamaları ekleme hakkında bilgi edinin."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/08/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ecb44f8b98501f6c82f91994cd8a06b8177208d7
ms.sourcegitcommit: 8a235b7af6ec3932c29a76d0b1aa481d983054bc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-add-web-apps-to-microsoft-intune"></a>Web uygulamalarını Microsoft Intune’a ekleme

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune web uygulamaları da dahil olmak üzere çeşitli uygulama türlerini destekler. Web uygulaması, bir istemci-sunucu uygulamasıdır. Sunucu; kullanıcı arabirimi, içerik ve işlevleri içeren web uygulamasını sağlar. Ayrıca modern web barındırma platformları çoğu zaman güvenlik, yük dengeleme ve diğer yararlar da sunar. Web uygulaması Web’de ayrı olarak korunur. Bu uygulama türüne işaret etmek için Microsoft Intune kullanırsınız. Bu uygulamaya erişebilecek kullanıcı gruplarını da atarsınız. 

Kullanıcılarınız için uygulamaları yönetebilmek ve atayabilmek için önce uygulamayı Intune’a ekleyin. Intune, kullanıcının cihazındaki giriş ekranında web uygulaması için bir kısayol oluşturur.

> [!Note]
> Android for Work ve macOS cihazlarında web uygulamaları desteklenmez.

Bir uygulamayı web'de uygulamanın kısayolu olarak Intune'a eklemek için aşağıdaki adımları tamamlayın:

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Microsoft Intune** bölmesinde **Mobil uygulamalar**'ı seçin.
4. **Mobil uygulamalar** bölmesinde **Uygulamalar**'ı seçin.
5. Uygulama listesinin üst kısmında **Ekle**’yi seçin. **Uygulama ekle** bölmesi görüntülenir.
6. **Uygulama ekle** bölmesinde, **Uygulama türü** açılan listesinden **Web bağlantısı** türünü seçin.
7. **Yapılandır** seçeneğini belirterek **Uygulama bilgileri** bölmesini görüntüleyin.
8. **Uygulama bilgileri** bölmesinde aşağıdaki bilgileri ekleyin:
    - **Ad** - Şirket portalında görüntülendiği şekliyle uygulamanın adını girin.
    - **Açıklama** - Uygulama için bir açıklama girin. Bu, şirket portalında son kullanıcılara görüntülenir.
    - **Yayımcı** - Bu uygulamanın yayımcısının adını girin.
    - **Uygulama URL’si** - Atamak istediğiniz uygulamayı barındıran web sitesinin URL’sini girin.
    - **Kategori (isteğe bağlı)** - Yerleşik uygulama kategorilerinden birini veya kendi oluşturduğunuz bir kategoriyi seçin. Bu seçim kullanıcıların şirket portalına göz atarken uygulamaları daha kolay bulabilmesini sağlar.
    - **Bunu Şirket Portalı'nda öne çıkan uygulama olarak görüntüle** - Kullanıcılar uygulamalara göz atarken bu uygulamayı Şirket Portalı’nın ana sayfasında göze çarpacak şekilde görüntüleyin.
    - **Bu bağlantının açılabilmesi için yönetilen tarayıcı gerektir** - Kullanıcılara bir web sitesi veya web uygulamasının bağlantısını atadığınızda bunu Intune ile yönetilen tarayıcıda açabilirler. Bu tarayıcı cihazlarında yüklü olmalıdır.
    - **Logo** -- Uygulamayla ilişkilendirilen logoyu karşıya yükleyin. Bu logo, kullanıcılar şirket portalına göz atarken uygulamayla birlikte görüntülen logodur.
9. İşiniz bittiğinde, **Bilgi ekle** bölmesinde **Tamam**'ı seçin.
10. Ardından, **Uygulama ekle** bölmesinde **Ekle**'yi seçin.

> [!Note]
> Android cihazlarına atanmış web uygulamalarını görüntüleyebilmek için kullanıcıların giriş ekranlarına Intune pencere öğesini eklemeleri gerekir.

## <a name="next-steps"></a>Sonraki adımlar

- Oluşturduğunuz uygulama, uygulamalar listesinde görüntülenir ve burada uygulamayı seçtiğiniz gruplara atayabilirsiniz. Yardım için bkz. [Uygulamaları gruplara atama](apps-deploy.md).