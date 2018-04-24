---
title: iOS mağazası uygulamalarını Microsoft Intune’a ekleme
titlesuffix: ''
description: Microsoft Intune'a iOS mağazası uygulamaları ekleme hakkında bilgi edinin.
keywords: Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: c59514d7-1256-4576-9380-e7a0b85a0378
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4eaa4b279ab98c6fe41482628937e0f2b0dc70a5
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-ios-store-apps-to-microsoft-intune"></a>iOS mağazası uygulamalarını Microsoft Intune’a ekleme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bu makaledeki bilgileri kullanarak iOS mağaza uygulamalarını Microsoft Intune’a eklemeyi öğrenin. iOS mağaza uygulamaları, Intune'un bir kullanıcı cihazına yüklediği uygulamalardır. Kullanıcı, şirketinizin iş gücünün bir parçasıdır. iOS mağaza uygulamaları otomatik olarak güncelleştirilir.

>[!NOTE]
>iOS kullanıcıları bazı yerleşik iOS uygulamalarını kaldırabilir (Stocks ve Harita gibi) ancak siz bu uygulamaları yeniden dağıtmak için Intune’u kullanamazsınız. Son kullanıcılar bu uygulamaları silerse uygulama mağazasına gidip el ile yeniden indirmeleri gerekir.

## <a name="before-you-start"></a>Başlamadan önce

Bu yöntemi kullanarak yalnızca uygulama mağazasında ücretsiz olan uygulamaları atayabilirsiniz. Intune kullanarak ücretli uygulamaları atamak isterseniz [iOS toplu satın alma programı](vpp-apps-ios.md) kullanmayı düşünün.

>[!NOTE]
>Microsoft Intune ile çalışırken önerilen tarayıcılar Chrome ve Edge’dir.

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** dikey penceresinde **Mobil uygulamalar**’ı seçin.
4. **Mobil uygulamalar** iş yükündeki **Yönet** grubu altında **Uygulamalar**’ı seçin.
5. **Uygulamalar** bölmesinin sağ tarafındaki **Ekle**’yi seçin.
6. **Uygulama türü** listesinde kullanılabilir **Mağaza uygulaması** türleri altından **iOS**’u seçin.
7. **App Store’da Ara**’yı seçin.
8. **App Store’da Ara** dikey penceresinde App Store ülke yerel ayarını seçin.
9. Adı (veya adın bir kısmını) arama kutusuna yazın. Intune, mağazada arama yapar ve ilgili sonuçların listesini getirir.
10. Listeden istediğiniz uygulamayı seçin ve ardından **Seçin**’e tıklayın.
11. Uygulamayı yapılandırmak için **Uygulama ekle** dikey penceresinde **Uygulama bilgileri**’ni seçin.
12. **Uygulama bilgileri** dikey penceresinde uygulama bilgilerini ekleyin. Seçtiğiniz uygulamaya bağlı olarak, dikey penceredeki değerlerden bazıları otomatik olarak doldurulmuş olabilir:
    - **Ad** -- Şirket portalında görüntülenmek üzere bir uygulama adı yazın. Kullandığınız tüm uygulama adlarının benzersiz olduğundan emin olun. Aynı uygulama adı iki kez kullanılmışsa Şirket Portalı uygulamalardan yalnızca birini kullanıcılara görüntüler.
    - **Açıklama** -- Şirket Portalı’nda kullanıcılara görüntülenmek üzere bir uygulama açıklaması yazın.
    - **Yayımcı** -- Uygulamanın yayımcısının adını yazın.
    - **Uygulama mağazası URL’si** -- Oluşturmak istediğiniz uygulamanın uygulama mağazası URL’sini yazın.
    - **En Düşük İşletim Sistemi** -- Listeden uygulamanın yüklenebileceği en düşük işletim sistemi sürümünü seçin. Uygulama, daha önceki bir işletim sistemini çalıştıran cihazlara yüklenmeyecektir.
    - **Geçerli cihaz türü** -- Uygulama tarafından kullanılan cihazları listeden seçin.
    - **Kategori** (isteğe bağlı). Yerleşik uygulama kategorilerinden birini veya kendi oluşturduğunuz bir kategoriyi seçin. Kategoriler, kullanıcıların şirket portalına göz atarken uygulamayı daha kolay bulabilmesini sağlar.
    - **Bunu Şirket Portalı'nda öne çıkan uygulama olarak görüntüle** -- Kullanıcılar uygulamalara göz atarken bu uygulamayı Şirket Portalı’nın ana sayfasında göze çarpacak şekilde görüntüleyin.
    - **Bilgi URL’si** -- İsteğe bağlı olarak, bu uygulama hakkında bilgi içeren bir web sitesinin URL’sini yazın. URL, şirket portalında kullanıcılara görüntülenir.
    - **Gizlilik URL’si** -- İsteğe bağlı olarak, bu uygulamayla ilgili gizlilik bilgilerini içeren bir web sitesinin URL’sini yazın. URL, şirket portalında kullanıcılara görüntülenir.
    - **Geliştirici** -- İsteğe bağlı olarak, uygulama geliştiricinin adını yazın. Bu alan yalnızca bir yönetici tarafından görülebilir, son kullanıcılar tarafından görülemez.
    - **Sahip** -- İsteğe bağlı olarak, bu uygulamanın sahibi olarak örneğin **İK bölümü** yazın.  Bu alan yalnızca bir yönetici tarafından görülebilir, son kullanıcılar tarafından görülemez.
    - **Notlar** -- Bu uygulamayla ilişkilendirmek isteyebileceğiniz notları yazın. Bu alan yalnızca bir yönetici tarafından görülebilir, son kullanıcılar tarafından görülemez.
    - **Logo** -- Uygulamayla ilişkilendirilen bir simgeyi karşıya yükleyin. Bu simge, kullanıcılar şirket portalına göz atarken uygulamayla birlikte görüntülenir.
13. İşiniz bittiğinde **Bilgi ekle** dikey penceresinde **Tamam**’a tıklayın.
14. **Uygulama ekle** dikey penceresinde **Ekle**’ye tıklayın.

Oluşturduğunuz uygulama, uygulamalar listesinde görüntülenir ve burada uygulamayı seçtiğiniz gruplara atayabilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

- [Uygulamaları gruplara ekleme](apps-deploy.md)
