---
title: "Windows Phone iş kolu uygulamalarını Intune’a ekleme"
titleSuffix: Intune on Azure
description: "Windows Phone iş kolu uygulamalarını Intune’a ekleme hakkında bilgi edinin.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a097b7b2-d01d-454b-954c-da4f3cd0ae86
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f27ad720556a866b5f2a9326df0a574cc37f2a5d
ms.sourcegitcommit: f100c943a635f5a08254ba7cf30f1aaebb7e810e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/13/2017
---
# <a name="how-to-add-windows-phone-line-of-business-lob-apps-to-microsoft-intune"></a>Windows Phone iş kolu (LOB) uygulamalarını Microsoft Intune’a ekleme

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


## <a name="step-1---specify-the-software-setup-file"></a>1. Adım - Yazılım kurulum dosyasını belirtme

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Uygulamaları yönet**’i seçin.
4. **Mobil uygulamalar** iş yükünde **Yönet** > **Uygulamalar**’ı seçin.
5. Uygulama listesinin üst kısmında **Ekle**’yi seçin.
6. **Uygulama Ekle** dikey penceresinde, **İş kolu uygulaması**’nı seçin.

## <a name="step-2---configure-the-app-package-file"></a>Adım 2 - Uygulama paketi dosyasını yapılandırma

1. **Uygulama ekle** dikey penceresinde **Uygulama paketi**’ni seçin.
2. **Uygulama paketi** dosyası dikey penceresinde, gözat düğmesini seçin ve **.xap** uzantısına sahip Windows Phone yükleme dosyasını seçin.
3. İşiniz bittiğinde **Tamam**’ı seçin.


## <a name="step-3---configure-app-information"></a>Adım 3 - Uygulama bilgilerini yapılandırma

1. **Uygulama ekle** dikey penceresinde **Uygulama paketi**’ni seçin.
2. **Uygulama bilgileri** dikey penceresinde uygulama bilgilerini yapılandırın. Seçtiğiniz uygulamaya bağlı olarak, dikey penceredeki değerlerden bazıları otomatik olarak doldurulmuş olabilir:
    - **Ad** - Uygulamanın şirket portalında görüntülenen adını girin. Kullandığınız tüm uygulama adlarının benzersiz olduğundan emin olun. Aynı uygulama adı iki kez kullanılmışsa uygulamalardan yalnızca biri şirket portalında kullanıcılara görüntülenir.
    - **Açıklama** - Uygulama için bir açıklama girin. Açıklama şirket portalında kullanıcılara görüntülenir.
    - **Yayımcı** - Uygulamanın yayımcısının adını girin.
    - **Kategori** - Yerleşik uygulama kategorilerinden birini veya kendi oluşturduğunuz bir kategoriyi seçin. Kategorileri kullanmak, kullanıcıların şirket portalına gözatarken uygulamaları daha kolay bulabilmesini sağlar.
    - **Bunu Şirket Portalı'nda öne çıkan uygulama olarak görüntüle** - Kullanıcılar uygulamalara göz atarken bu uygulamayı Şirket Portalı’nın ana sayfasında göze çarpacak şekilde görüntüleyin.
    - **Bilgi URL’si** - İsteğe bağlı olarak, bu uygulama hakkında bilgi içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Gizlilik URL’si**- İsteğe bağlı olarak, bu uygulamayla ilgili gizlilik bilgilerini içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Geliştirici** - İsteğe bağlı olarak, uygulama geliştiricinin adını girin.
    - **Sahip** - İsteğe bağlı olarak, bu uygulamanın sahibi olarak **İK bölümü** gibi bir ad girin.
    - **Notlar** - Bu uygulamayla ilişkilendirmek isteyebileceğiniz notları girin.
    - **Logo** - Uygulamayla ilişkilendirilen bir simgeyi karşıya yükleyin. Bu simge, kullanıcılar şirket portalına gözatarken uygulamayla birlikte görüntülenir.
3. İşiniz bittiğinde **Tamam**’ı seçin.

## <a name="step-4---finish-up"></a>Adım 4 - Bitirme

1. **Uygulama ekle** dikey penceresinde, bilgileri doğru yapılandırdığınızı doğrulayın.
2. Uygulamayı Intune'a yüklemek için **Ekle**’yi seçin.

## <a name="next-steps"></a>Sonraki adımlar

Oluşturduğunuz uygulama, uygulamalar listesinde görüntülenir ve burada uygulamayı seçtiğiniz gruplara atayabilirsiniz. Yardım için bkz. [Uygulamaları gruplara atama](apps-deploy.md).
