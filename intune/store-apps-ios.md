---
title: "iOS mağazası uygulamalarını Intune’a ekleme | Microsoft Docs"
titlesuffix: Azure portal
description: "Intune'a iOS mağazası uygulamaları ekleme hakkında bilgi edinin.\""
keywords: Intune
author: Erikre
ms.author: erikre
manager: angrobe
ms.date: 09/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c59514d7-1256-4576-9380-e7a0b85a0378
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7dcb857127b3c36d2b90208aac9b8ad901e31d89
ms.sourcegitcommit: 833b1921ced35be140f0107d0b4205ecacd2753b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/04/2018
---
# <a name="how-to-add-ios-store-apps-to-microsoft-intune"></a>iOS mağazası uygulamalarını Microsoft Intune’a ekleme

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


Bu konudaki bilgileri kullanarak iOS mağaza uygulamalarını Intune’a eklemeyi öğrenin.

>[!NOTE]
>iOS kullanıcıları bazı yerleşik iOS uygulamalarını kaldırabilir (Stocks ve Harita gibi) ancak siz bu uygulamaları yeniden dağıtmak için Intune’u kullanamazsınız. Son kullanıcılar bu uygulamaları silerse uygulama mağazasına gidip el ile yeniden indirmeleri gerekir.

## <a name="before-you-start"></a>Başlamadan önce

Bu yöntemi kullanarak yalnızca uygulama mağazasında ücretsiz olan uygulamaları atayabilirsiniz. Intune kullanarak ücretli uygulamaları atamak isterseniz [iOS toplu satın alma programı](vpp-apps-ios.md) kullanmayı düşünün.


## <a name="step-1---search-for-the-app-in-the-store"></a>1. Adım - Mağazada uygulama arama

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Uygulamaları yönet**’i seçin.
4. **Mobil uygulamalar** iş yükünde **Yönet** > Uygulamalar’ı seçin.
5. Uygulama listesinin üst kısmında **Ekle**’yi seçin.
6. **Uygulama Ekle** dikey penceresinde **App Store'da Ara**’yı seçin.
7. **Apple App Store** dikey penceresinde App Store ülke yerel ayarını seçin.
8. Adı (veya adın bir kısmını) arama kutusuna yazın. Intune, mağazada arama yapar ve ilgili sonuçların listesini getirir.
9. Listeden istediğiniz uygulamayı seçin ve ardından **Tamam**’a tıklayın.

## <a name="step-2---configure-app-information"></a>2. Adım - Uygulama bilgilerini yapılandırma

1. **Uygulama Ekle** dikey penceresinde **Uygulama Bilgileri**’ni seçin.
2. **Uygulamayı Düzenle** dikey penceresinde uygulama bilgilerini yapılandırın. Bitirdiğinizde, **Ekle**’ye tıklayın. Seçtiğiniz uygulamaya bağlı olarak, dikey penceredeki değerlerden bazıları otomatik olarak doldurulmuş olabilir:
- **Ad** -- Şirket portalında görüntülenmek üzere bir uygulama adı yazın. Kullandığınız tüm uygulama adlarının benzersiz olduğundan emin olun. Aynı uygulama adı iki kez kullanılmışsa Şirket Portalı uygulamalardan yalnızca birini kullanıcılara görüntüler.
- **Açıklama** -- Şirket Portalı’nda kullanıcılara görüntülenmek üzere bir uygulama açıklaması yazın.
- **Yayımcı** -- Uygulamanın yayımcısının adını yazın.
- **Uygulama mağazası URL’si** -- Oluşturmak istediğiniz uygulamanın uygulama mağazası URL’sini yazın.
- **Mağaza ülkesi/bölgesi** -- Uygulama mağazası ülke yerel ayarını seçin.
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
3. İşiniz bittiğinde, **Uygulama Ekle** dikey penceresinde **Tamam**’ı seçin.

Oluşturduğunuz uygulama, uygulamalar listesinde görüntülenir ve burada uygulamayı seçtiğiniz gruplara atayabilirsiniz. Yardım için bkz. [Uygulamaları gruplara atama](apps-deploy.md).
