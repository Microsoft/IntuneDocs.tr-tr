---
title: "iOS mağaza uygulamalarını Intune’a ekleme | Intune Azure önizlemesi | Microsoft Docs"
description: "Intune Azure önizlemesi: iOS mağaza uygulamalarını Intune’a eklemeyi öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c59514d7-1256-4576-9380-e7a0b85a0378
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: 6026c942aea906e7e730152e6e92797ec5775bc3
ms.lasthandoff: 02/16/2017

---

# <a name="how-to-add-ios-store-apps-to-microsoft-intune"></a>iOS mağazası uygulamalarını Microsoft Intune’a ekleme

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


## <a name="step-1---search-for-the-app-in-the-store"></a>1. Adım - Mağazada uygulama arama

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Uygulamaları yönet**’i seçin.
4. **Mobil uygulamalar** iş yükünde **Yönet** > Uygulamalar’ı seçin.
5. Uygulama listesinin üst kısmında **Ekle**’yi seçin.
6. **Uygulama Ekle** dikey penceresinde **App Store'da Ara**’yı seçin.
7. **Apple App Store** dikey penceresinde, arama kutusuna adı (veya adın bir bölümünü) girin. Intune, mağazada arama yapar ve ilgili sonuçların listesini döndürür.
8. Listeden istediğiniz uygulamayı seçin ve ardından **Tamam**’a tıklayın.

## <a name="step-2---configure-app-information"></a>2. Adım - Uygulama bilgilerini yapılandırma

1. **Uygulama Ekle** dikey penceresinde **Uygulama Bilgileri**’ni seçin.
2. **Uygulamayı Düzenle** dikey penceresinde aşağıdaki bilgileri yapılandırın. Bitirdiğinizde, **Ekle**’ye tıklayın. Seçtiğiniz uygulamaya bağlı olarak, dikey penceredeki değerlerden bazıları otomatik olarak doldurulmuş olabilir:
- **Uygulama Adı** - Uygulamanın şirket portalında görüntülenecek olan adını girin. Kullandığınız tüm uygulama adlarının benzersiz olduğundan emin olun. Aynı uygulama adı iki kez kullanılmışsa, uygulamalardan yalnızca biri şirket portalında kullanıcılara görüntülenir.
    - **Uygulama Açıklaması** - Uygulama için bir açıklama girin. Bu, şirket portalında kullanıcılara görüntülenir.
- **Yayımcı** - Uygulamanın yayımcısının adını girin.
- **Uygulama mağazası URL’si** - Oluşturmak istediğiniz uygulamanın uygulama mağazası URL’sini girin.
- **Minimum İşletim Sistemi** - Listeden uygulamanın yüklenebileceği minimum işletim sistemi sürümünü seçin. Uygulamayı daha önceki bir işletim sistemini çalıştıran cihazlara atarsanız, uygulama yüklenmez.
- **Kategori** (isteğe bağlı). Yerleşik uygulama kategorilerinden birini veya kendi oluşturduğunuz bir kategoriyi seçin. Bu, kullanıcıların şirket portalına göz atarken uygulamaları daha kolay bulabilmesini sağlar.
- **Bunu Şirket Portalı'nda öne çıkan uygulama olarak görüntüle** - Kullanıcılar uygulamalara göz atarken bu uygulamayı Şirket Portalı’nın ana sayfasında göze çarpacak şekilde görüntüleyin.
- **Bilgi URL’si** - İsteğe bağlı olarak, bu uygulama hakkında bilgi içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
- **Gizlilik URL’si**- İsteğe bağlı olarak, bu uygulamayla ilgili gizlilik bilgilerini içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
- **Geliştirici** - İsteğe bağlı olarak, uygulama geliştiricinin adını girin.
- **Sahip** - İsteğe bağlı olarak, bu uygulamanın sahibi olarak **İK bölümü** gibi bir ad girin.
- **Notlar** - Bu uygulamayla ilişkilendirmek isteyebileceğiniz notları girin.
- **Simgeyi Karşıya Yükle** - Uygulamayla ilişkilendirilecek bir simgeyi karşıya yükleyin. Bu, kullanıcılar şirket portalına göz atarken uygulamayla birlikte görüntülenecek olan simgedir.
3. İşiniz bittiğinde, **Uygulama Ekle** dikey penceresinde **Kaydet**’i seçin.

Oluşturduğunuz uygulama, uygulamalar listesinde görüntülenir ve burada uygulamayı seçtiğiniz gruplara atayabilirsiniz. Yardım için bkz. [Uygulamaları gruplara atama](/intune-azure/manage-apps/deploy-apps).
