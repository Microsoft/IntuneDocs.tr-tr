---
title: "Web uygulamalarını Intune’a ekleme"
titleSuffix: Intune on Azure
description: "Intune'a Web uygulamaları ekleme hakkında bilgi edinin.\""
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f64d60b659d0316cab542cb6005026a353ab0589
ms.sourcegitcommit: 4034ac474bfed358270a32459a2cf2fe02f44e45
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2017
---
# <a name="how-to-add-web-apps-to-microsoft-intune"></a>Web uygulamalarını Microsoft Intune’a ekleme

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Uygulamaları yönet**’i seçin.
4. **Mobil uygulamalar** iş yükünde **Yönet** > **Uygulamalar**’ı seçin.
5. Uygulama listesinin üst kısmında **Ekle**’yi seçin.
6. **Uygulama Ekle** dikey penceresinde **Uygulama Bilgileri**’ni seçin.
7. **Uygulamayı Düzenle** dikey penceresinde aşağıdaki bilgileri yapılandırın. Bitirdiğinizde, **Ekle**’ye tıklayın:
    - **Uygulama URL’si** - Atamak istediğiniz uygulamayı barındıran web sitesinin URL’sini girin.
    - **Uygulama Adı** - Uygulamanın şirket portalında görüntülenecek olan adını girin.
    - **Uygulama Açıklaması** - Uygulama için bir açıklama girin. Bu, şirket portalında son kullanıcılara görüntülenir.
    - **Yayımcı** - Bu uygulamanın yayımcısının adını girin.
    - **Kategori (isteğe bağlı)** - Yerleşik uygulama kategorilerinden birini veya kendi oluşturduğunuz bir kategoriyi seçin. Bu, kullanıcıların şirket portalına göz atarken uygulamaları daha kolay bulabilmesini sağlar.
    - **Bunu Şirket Portalı'nda öne çıkan uygulama olarak görüntüle** - Kullanıcılar uygulamalara göz atarken bu uygulamayı Şirket Portalı’nın ana sayfasında göze çarpacak şekilde görüntüleyin.
    - **Bu bağlantının açılabilmesi için yönetilen tarayıcı gerektir** - Kullanıcılara bir web sitesi veya web uygulamasının bağlantısını atadığınızda bunu yalnızca Intune ile yönetilen tarayıcıda açabilirler. Bu tarayıcı cihazlarında yüklü olmalıdır.
    - **Simgeyi Karşıya Yükle** - Uygulamayla ilişkilendirilecek bir simgeyi karşıya yükleyin. Bu, kullanıcılar şirket portalına göz atarken uygulamayla birlikte görüntülenecek olan simgedir.
8. İşiniz bittiğinde, **Uygulama Ekle** dikey penceresinde **Kaydet**’i seçin.

Oluşturduğunuz uygulama, uygulamalar listesinde görüntülenir ve burada uygulamayı seçtiğiniz gruplara atayabilirsiniz. Yardım için bkz. [Uygulamaları gruplara atama](apps-deploy.md).