---
title: Android mağazası uygulamalarını Microsoft Intune’a ekleme
titleSuffix: ''
description: Microsoft Intune'a Android mağazası uygulamaları ekleme hakkında bilgi edinin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4433000a-23e9-4cad-a818-48c28eedc1f5
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ece6edee891b147ad2124b987239da6af8e1bc8d
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-android-store-apps-to-microsoft-intune"></a>Android mağazası uygulamalarını Microsoft Intune’a ekleme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bir cihaza veya kullanıcı grubuna uygulama atamadan önce uygulamayı ilk olarak Microsoft Intune’a eklemeniz gerekir. Aşağıdaki adımlar, Azure portalından Intune’a bir Android mağaza uygulaması eklemeyi gösterir.

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** bölmesinde **Mobil uygulamalar**’ı seçin.
4. **Mobil uygulamalar** iş yükündeki **Yönet** grubu altında **Uygulamalar**’ı seçin.
5. Uygulama listesinin üst kısmında **Ekle**’yi seçin.
6. **Uygulama Ekle** bölmesinde kullanılabilir **Mağaza uygulaması** türlerinden **Android**’i seçin.
7. **Yapılandır**’ı seçerek aşağıdaki uygulama bilgilerini yapılandırın. Seçtiğiniz uygulamaya bağlı olarak bu bölmedeki bazı değerler otomatik olarak doldurulmuş olabilir:
    - **Ad** - Uygulamanın şirket portalında görüntülenecek olan adını girin. Kullandığınız tüm uygulama adlarının benzersiz olduğundan emin olun. Aynı uygulama adı iki kez kullanılmışsa, uygulamalardan yalnızca biri şirket portalında kullanıcılara görüntülenir.
    - **Açıklama** - Uygulama için bir açıklama girin. Bu açıklama, Şirket Portalı’nda kullanıcılara görüntülenir.
    - **Yayımcı** - Uygulamanın yayımcısının adını girin.
    - **Uygulama mağazası URL’si** - Oluşturmak istediğiniz uygulamanın uygulama mağazası URL’sini girin.
    - **En Düşük İşletim Sistemi** - Listeden uygulamanın yüklenebileceği en düşük işletim sistemi sürümünü seçin. Uygulamayı daha önceki bir işletim sistemini çalıştıran cihazlara atarsanız, uygulama yüklenmez.
    - **Kategori (isteğe bağlı)** - Yerleşik uygulama kategorilerinden birini veya kendi oluşturduğunuz bir kategoriyi seçin. Bu, kullanıcıların şirket portalına göz atarken uygulamaları daha kolay bulabilmesini sağlar.
    - **Bunu Şirket Portalı'nda öne çıkan uygulama olarak görüntüle** - Kullanıcılar uygulamalara göz atarken bu uygulamayı Şirket Portalı’nın ana sayfasında göze çarpacak şekilde görüntüleyin.
    - **Bilgi URL’si** (isteğe bağlı) - Bu uygulama hakkında bilgi içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Gizlilik URL’si** (isteğe bağlı) - Bu uygulamayla ilgili gizlilik bilgilerini içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Geliştirici** (isteğe bağlı) - Uygulama geliştiricisinin adını girin.
    - **Sahip** (isteğe bağlı) - Bu uygulamanın sahibi olarak **İK departmanı** gibi bir ad girin.
    - **Notlar** (isteğe bağlı) - Bu uygulamayla ilişkilendirmek isteyebileceğiniz notları girin.
    - **Logo** - (isteğe bağlı) Uygulamayla ilişkilendirilecek simgeyi karşıya yükleyin. Bu simge, kullanıcılar şirket portalına gözatarken uygulamayla birlikte görüntülenir.
8. Uygulama bilgilerini ayarlamayı bitirdiğinizde **Tamam**’a tıklayın.
9. Uygulamayı eklemek için **Ekle**’ye tıklayın.

Oluşturduğunuz uygulama, uygulamalar listesinde görüntülenir ve burada uygulamayı seçtiğiniz gruplara atayabilirsiniz. 

## <a name="next-steps"></a>Sonraki adımlar

- [Uygulamaları gruplara ekleme](apps-deploy.md)