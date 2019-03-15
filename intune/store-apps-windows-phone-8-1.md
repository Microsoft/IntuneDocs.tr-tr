---
title: Windows Phone 8.1 mağazası uygulamalarını Microsoft Intune’a ekleme
titleSuffix: ''
description: Bu konu, Windows Phone 8.1 mağazası uygulamalarını Microsoft Intune eklemeyi açıklar.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/19/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 4a95e575-2c63-4bfc-b9c4-f0a132eef618
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a448d0da0e2e155d0b9aedb8e012c42115b4cf83
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57392998"
---
# <a name="add-windows-phone-81-store-apps-to-microsoft-intune"></a>Windows Phone 8.1 mağazası uygulamalarını Microsoft Intune’a ekleme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bir cihaza veya kullanıcı grubuna uygulama atamadan önce uygulamayı ilk olarak Microsoft Intune’a eklemeniz gerekir. 

## <a name="add-an-app-to-intune"></a>Intune’a uygulama ekleme
Aşağıdakileri yaparak, Azure portalından Intune’a bir Windows Phone 8.1 mağaza uygulaması ekleyebilirsiniz:

1. [Azure Portal](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin.  
    Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** bölmesinde **İstemci uygulamaları**’nı seçin.
4. **İstemci uygulamaları** iş yükü bölmesindeki **Yönet**’in altında **Uygulamalar**’ı seçin.
5. **Uygulamalar** bölmesinde **Ekle**’yi seçin.
6. **Uygulama ekle** bölmesinde, **Uygulama türü** olarak **Windows Phone 8.1**’i ve **Uygulama bilgileri**’ni seçin.
7. **Uygulama bilgileri** bölmesinde uygulama bilgilerini ekleyin. Seçtiğiniz uygulamaya bağlı olarak, bölmedeki değerlerden bazıları otomatik olarak doldurulmuş olabilir:
    - **Ad**: Şirket portalı'nda görüntülenecek olduğu gibi bir uygulama adı girin. Kullandığınız uygulama adlarının benzersiz olduğundan emin olun. Bir uygulama adı iki kez kullanılırsa, Şirket Portalı’nda kullanıcılara yalnızca bir ad gösterilir.
    - **Açıklama**: Uygulama için bir açıklama girin. Bu açıklama Şirket Portalı’nda kullanıcılara görüntülenir.Açıklama şirket portalında kullanıcılara görüntülenir.
    - **Yayımcı**: Uygulama yayımcısının adını girin.
    - **Appstore URL**: Oluşturmak istediğiniz uygulamayı App Store URL'sini yazın.
    - **Kategori**: İsteğe bağlı olarak, bir veya daha fazla yerleşik uygulama kategorilerinden veya kendi oluşturduğunuz bir kategoriyi seçin. Böylelikle, Şirket Portalı’na göz atarken kullanıcıların uygulamayı bulmaları kolaylaşır.
    - **Bunu şirket Portalı'nda öne çıkan uygulama olarak görüntüle**: Kullanıcılar uygulamalara göz atarken uygulama paketinin şirket Portalı'nın ana sayfasında göze çarpacak şekilde görüntüleyin için. Bu seçeneği belirleyin.
    - **Bilgi URL'si**: İsteğe bağlı olarak, bu uygulama hakkında bilgi içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Gizlilik URL'si**: İsteğe bağlı olarak, bu uygulamayla ilgili gizlilik bilgilerini içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Geliştirici**: İsteğe bağlı olarak, uygulama geliştiricisinin adını girin.
    - **Sahibi**: İsteğe bağlı olarak, örneğin, bu uygulamanın sahibi için bir ad girin *ik departmanı*.
    - **Notları**: İsteğe bağlı olarak, bu uygulamayla ilişkilendirmek istediğiniz notları girin.
    - **Logo**: İsteğe bağlı olarak, uygulamayla ilişkilendirilecek bir simgeyi karşıya yükleyin. Bu simge, kullanıcılar şirket portalına gözatarken uygulamayla birlikte görüntülenir.
8. **Tamam**’ı seçin.
9. **Add (Ekle)** seçeneğini belirleyin.

Oluşturduğunuz uygulama, uygulamalar listesinde görüntülenir ve burada uygulamayı seçtiğiniz gruplara atayabilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

- [Gruplara uygulama ekleme](apps-deploy.md)
