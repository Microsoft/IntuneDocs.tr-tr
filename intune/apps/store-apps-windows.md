---
title: Microsoft Store uygulamalarını Microsoft Intune’a ekleme
titleSuffix: ''
description: Microsoft Intune’a Microsoft Store (Windows Store) uygulamalarını ekleme hakkında bilgi edinin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 07241b6d-86d8-4abb-83a2-3fc5feae5788
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3c13d7960c0bb5c73908a0a574ab7d6c169d6460
ms.sourcegitcommit: 73b362173929f59e9df57e54e76d19834f155433
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/27/2019
ms.locfileid: "74563431"
---
# <a name="add-microsoft-store-apps-to-microsoft-intune"></a>Microsoft Store uygulamalarını Microsoft Intune’a ekleme

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Uygulamaları atama, izleme, yapılandırma veya korumadan önce bunları Intune’a eklemelisiniz. 

## <a name="add-an-app-to-intune"></a>Intune’a uygulama ekleme
Aşağıdakileri yaparak Intune’a bir Microsoft Store uygulaması ekleyebilirsiniz:

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. **Tüm uygulamalar** ** >  > ** **Ekle**' yi seçin.
3. **Uygulama ekle** bölmesinde, **Uygulama türü** olarak **Windows**’u ve **Uygulama bilgileri**’ni seçin.
4. **Uygulama bilgileri** bölmesinde uygulama bilgilerini ekleyin. Seçtiğiniz uygulamaya bağlı olarak, bölmedeki değerlerden bazıları otomatik olarak doldurulmuş olabilir:
    - **Ad**: Şirket Portalı’nda görüntülendiği şekliyle uygulamanın adını girin. Kullandığınız uygulama adlarının benzersiz olduğundan emin olun. Bir uygulama adı iki kez kullanılırsa, Şirket Portalı’nda kullanıcılara yalnızca bir ad gösterilir.
    - **Açıklama**: Uygulama için bir açıklama girin. Bu açıklama Şirket Portalı’nda kullanıcılara görüntülenir.Açıklama şirket portalında kullanıcılara görüntülenir.
    - **Yayımcı**: Uygulama yayımcısının adını girin.
    - **Uygulama mağazası URL’si**: Oluşturmak istediğiniz uygulamanın App Store URL’sini yazın. URL, istenen uygulama için [Microsoft Store](https://store.microsoft.com) arayarak bulunabilir. Tarayıcı adres çubuğundan URL 'YI kullanın.
    - **Kategori**: İsteğe bağlı olarak, yerleşik uygulama kategorilerinden veya kendi oluşturduğunuz kategorilerden birini ya da birkaçını seçin. Böylelikle, Şirket Portalı’na göz atarken kullanıcıların uygulamayı bulmaları kolaylaşır.
    - **Bunu Şirket Portalı’nda öne çıkan uygulama olarak görüntüle**: Bu seçenek uygulama paketini, kullanıcılar uygulamalara göz atarken Şirket Portalı’nın ana sayfasında göze çarpacak şekilde görüntüler.
    - **Bilgi URL’si**: İsteğe bağlı olarak, bu uygulama hakkında bilgi içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Gizlilik URL’si**: İsteğe bağlı olarak, bu uygulamayla ilgili gizlilik bilgilerini içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Geliştirici**: İsteğe bağlı olarak, uygulama geliştiricisinin adını girin.
    - **Sahip**: İsteğe bağlı olarak, bu uygulamanın sahibi için bir ad girin, örneğin *İK departmanı*.
    - **Notlar**: İsteğe bağlı olarak bu uygulamayla ilişkilendirmek istediğiniz notları girin.
    - **Logo**: İsteğe bağlı olarak, uygulamayla ilişkilendirilecek bir simgeyi karşıya yükleyin. Bu simge, kullanıcılar şirket portalına gözatarken uygulamayla birlikte görüntülenir.
5. **Tamam**’ı seçin.
6. **Ekle**’yi seçin.

Oluşturduğunuz uygulama, uygulamalar listesinde görüntülenir ve burada uygulamayı seçtiğiniz gruplara atayabilirsiniz. Microsoft Store uygulamaları, yalnızca **Kayıtlı cihazlar için kullanılabilir** atama türüne sahip gruplara atanabilir (kullanıcılar uygulamayı Şirket Portalı uygulamasından veya web sitesinden yükler).

## <a name="next-steps"></a>Sonraki adımlar
- [Gruplara uygulama ekleme](apps-deploy.md)
