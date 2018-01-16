---
title: "Web uygulamalarını Intune’a ekleme"
titleSuffix: Azure portal
description: "Intune'a Web uygulamaları ekleme hakkında bilgi edinin.\""
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 12/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6da1441b16a43b5e22bedd9e87970f3388b11b9e
ms.sourcegitcommit: a3a744ea55f38a360ca9f788c77a5b3018d1add5
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/30/2017
---
# <a name="how-to-add-web-apps-to-microsoft-intune"></a>Web uygulamalarını Microsoft Intune’a ekleme

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Kullanıcılarınız için uygulamaları yönetebilmek ve atayabilmek için önce uygulamayı Intune’a ekleyin. Intune web uygulamaları da dahil olmak üzere çeşitli uygulama türlerini destekler.

> [!Note]
> Android for Work cihazlarında web uygulamaları desteklenmez.

Bir uygulamayı web'de uygulamanın kısayolu olarak Intune'a eklemek için aşağıdaki adımları tamamlayın:

1. Azure Portal’da oturum açın.
2. **Diğer kaynaklar**'ı kullanarak **Intune** için arama yapın ve Intune'u seçin.
3. **Microsoft Intune** dikey penceresinde **Mobil uygulamalar**'ı seçin.
4. **Mobil uygulamalar** dikey penceresinde **Uygulamalar**'ı seçin.
5. Uygulama listesinin üst kısmında **Ekle**’yi seçin. **Uygulama ekle** dikey penceresi görüntülenir.
6. **Uygulama ekle** dikey penceresinde, **Uygulama türü** açılan listesinden **Web uygulaması** türünü seçin.
7. **Yapılandır** seçeneğini belirterek **Uygulama bilgileri** dikey penceresini görüntüleyin.
8. **Uygulama bilgileri** dikey penceresinde aşağıdaki bilgileri ekleyin:
    - **Ad** - Şirket portalında görüntülendiği şekliyle uygulamanın adını girin.
    - **Açıklama** - Uygulama için bir açıklama girin. Bu, şirket portalında son kullanıcılara görüntülenir.
    - **Yayımcı** - Bu uygulamanın yayımcısının adını girin.
    - **Uygulama URL’si** - Atamak istediğiniz uygulamayı barındıran web sitesinin URL’sini girin.
    - **Kategori (isteğe bağlı)** - Yerleşik uygulama kategorilerinden birini veya kendi oluşturduğunuz bir kategoriyi seçin. Bu seçim kullanıcıların şirket portalına göz atarken uygulamaları daha kolay bulabilmesini sağlar.
    - **Bunu Şirket Portalı'nda öne çıkan uygulama olarak görüntüle** - Kullanıcılar uygulamalara göz atarken bu uygulamayı Şirket Portalı’nın ana sayfasında göze çarpacak şekilde görüntüleyin.
    - **Bu bağlantının açılabilmesi için yönetilen tarayıcı gerektir** - Kullanıcılara bir web sitesi veya web uygulamasının bağlantısını atadığınızda bunu Intune ile yönetilen tarayıcıda açabilirler. Bu tarayıcı cihazlarında yüklü olmalıdır.
    - **Logo** -- Uygulamayla ilişkilendirilen logoyu karşıya yükleyin. Bu logo, kullanıcılar şirket portalına göz atarken uygulamayla birlikte görüntülen logodur.
9. İşiniz bittiğinde, **Bilgi ekle** dikey penceresinde **Tamam**'ı seçin.
10. Ardından, **Uygulama ekle** dikey penceresinde **Ekle**'yi seçin.

Oluşturduğunuz uygulama, uygulamalar listesinde görüntülenir ve burada uygulamayı seçtiğiniz gruplara atayabilirsiniz. Yardım için bkz. [Uygulamaları gruplara atama](apps-deploy.md).