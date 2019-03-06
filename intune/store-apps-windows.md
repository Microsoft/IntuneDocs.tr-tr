---
title: Microsoft Store uygulamalarını Microsoft Intune’a ekleme
titleSuffix: ''
description: Microsoft Intune’a Microsoft Store (Windows Store) uygulamalarını ekleme hakkında bilgi edinin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/20/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 07241b6d-86d8-4abb-83a2-3fc5feae5788
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2fc059339ffdb1111d3fe7cf1bbe9c39f5523944
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57398996"
---
# <a name="add-microsoft-store-apps-to-microsoft-intune"></a>Microsoft Store uygulamalarını Microsoft Intune’a ekleme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Uygulamaları atama, izleme, yapılandırma veya korumadan önce bunları Intune’a eklemelisiniz. 

## <a name="add-an-app-to-intune"></a>Intune’a uygulama ekleme
Aşağıdakileri yaparak Intune’a bir Microsoft Store uygulaması ekleyebilirsiniz:

1. [Azure Portal](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin.  
    Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** bölmesinde **İstemci uygulamaları**’nı seçin.
4. **İstemci uygulamaları** iş yükü bölmesindeki **Yönet**’in altında **Uygulamalar**’ı seçin.
5. **Uygulamalar** bölmesinde **Ekle**’yi seçin.
6. **Uygulama ekle** bölmesinde, **Uygulama türü** olarak **Windows**’u ve **Uygulama bilgileri**’ni seçin.
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

Oluşturduğunuz uygulama, uygulamalar listesinde görüntülenir ve burada uygulamayı seçtiğiniz gruplara atayabilirsiniz. Microsoft Store uygulamaları, yalnızca **Kayıtlı cihazlar için kullanılabilir** atama türüne sahip gruplara atanabilir (kullanıcılar uygulamayı Şirket Portalı uygulamasından veya web sitesinden yükler).

## <a name="next-steps"></a>Sonraki adımlar
- [Gruplara uygulama ekleme](apps-deploy.md)
