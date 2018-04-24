---
title: Windows Phone iş kolu uygulamalarını Microsoft Intune’a ekleme
titlesuffix: ''
description: Windows Phone iş kolu (LOB) uygulamalarını Intune’a ekleme hakkında bilgi edinin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a097b7b2-d01d-454b-954c-da4f3cd0ae86
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6f1a07960f4c00fa5562529a97453a61202a3913
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-windows-phone-line-of-business-lob-apps-to-microsoft-intune"></a>Windows Phone iş kolu (LOB) uygulamalarını Microsoft Intune’a ekleme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bu makaledeki bilgiler Windows Phone iş kolu uygulamalarını Microsoft Intune’a eklemenize yardımcı olabilir. İş kolu (LOB) uygulaması, bir uygulama yükleme dosyasından Intune'a eklediğiniz uygulamadır. Bu tür uygulamalar genellikle şirket içinde yazılanlardır. Intune LOB uygulamasını kullanıcıların cihazlarına yükler. 

## <a name="step-1---specify-the-software-setup-file"></a>1. Adım - Yazılım kurulum dosyasını belirtme

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** bölmesinde **Mobil uygulamalar**’ı seçin.
4. **Mobil uygulamalar** iş yükünde **Yönet** > **Uygulamalar**’ı seçin.
5. Uygulama listesinin üst kısmında **Ekle**’yi seçin.
6. **Uygulama ekle** bölmesinde **İş kolu uygulaması**’nı seçin.

## <a name="step-2---configure-the-app-package-file"></a>Adım 2 - Uygulama paketi dosyasını yapılandırma

1. **Uygulama ekle** bölmesinde **Uygulama paketi**’ni seçin.
2. **Uygulama paketi dosyası** bölmesinde gözat düğmesini seçin ve sonra da **.xap** uzantısına sahip Windows Phone yükleme dosyasını seçin.
3. İşiniz bittiğinde **Tamam**’ı seçin.


## <a name="step-3---configure-app-information"></a>Adım 3 - Uygulama bilgilerini yapılandırma

1. **Uygulama ekle** bölmesinde **Uygulama paketi**’ni seçin.
2. **Uygulama bilgileri** bölmesinde uygulama bilgilerini yapılandırın. Seçtiğiniz uygulamaya bağlı olarak, bölmedeki değerlerden bazıları otomatik olarak doldurulmuş olabilir:
    - **Ad** - Uygulamanın şirket portalında görüntülenen adını girin. Kullandığınız tüm uygulama adlarının benzersiz olduğundan emin olun. Aynı uygulama adı iki kez kullanılmışsa uygulamalardan yalnızca biri şirket portalında kullanıcılara görüntülenir.
    - **Açıklama** - Uygulama için bir açıklama girin. Açıklama şirket portalında kullanıcılara görüntülenir.
    - **Yayımcı** - Uygulamanın yayımcısının adını girin.
    - **Uygulama sürümünü yoksay** - Uygulama, uygulama geliştiricisi tarafından otomatik olarak güncelleştiriliyorsa **Evet** olarak ayarlayın.
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

1. **Uygulama ekle** bölmesinde, bilgileri doğru yapılandırdığınızı onaylayın.
2. Uygulamayı Intune'a yüklemek için **Ekle**’yi seçin.

## <a name="next-steps"></a>Sonraki adımlar

- Oluşturduğunuz uygulama, uygulamalar listesinde gösterilir. Artık seçtiğiniz gruplara bu uygulamayı atayabilirsiniz. Yardım için bkz. [Uygulamaları gruplara atama](apps-deploy.md).

- Uygulamanızın özelliklerini ve atamasını izleme yolları hakkında daha fazla bilgi edinin. Daha fazla bilgi için bkz. [Uygulama bilgilerini ve atamalarını izleme](apps-monitor.md).

- Intune’da uygulamanızın bağlamı hakkında daha fazla bilgi edinin. Daha fazla bilgi için bkz. [Cihaz ve uygulama yaşam döngülerine genel bakış](introduction-device-app-lifecycles.md)
