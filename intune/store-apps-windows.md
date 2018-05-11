---
title: Microsoft Store uygulamalarını Microsoft Intune’a ekleme
titleSuffix: ''
description: Microsoft Intune’a Microsoft Store (Windows Store) uygulamalarını ekleme hakkında bilgi edinin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 07241b6d-86d8-4abb-83a2-3fc5feae5788
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: baa9b20ee8820915f3cdee6ee26ec2429c93d63b
ms.sourcegitcommit: 2b5d88c434bda7f1cdc32d1ccacc6b341a9a399b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="add-microsoft-store-apps-to-microsoft-intune"></a>Microsoft Store uygulamalarını Microsoft Intune’a ekleme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Uygulamaları atama, izleme, yapılandırma veya korumadan önce bunları Intune’a eklemelisiniz. 

## <a name="add-an-app-to-intune"></a>Intune’a uygulama ekleme
Aşağıdakileri yaparak Intune’a bir Microsoft Store uygulaması ekleyebilirsiniz:

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin.  
    Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** bölmesinde **Mobil uygulamalar**’ı seçin.
4. **Mobil uygulamalar** iş yükü bölmesinde **Yönet** altında **Uygulamalar**’ı seçin.
5. **Uygulamalar** bölmesinde **Ekle**’yi seçin.
6. **Uygulama ekle** bölmesinde, **Uygulama türü** olarak **Windows**’u ve **Uygulama bilgileri**’ni seçin.
7. **Uygulama bilgileri** bölmesinde uygulama bilgilerini ekleyin. Seçtiğiniz uygulamaya bağlı olarak, bölmedeki değerlerden bazıları otomatik olarak doldurulmuş olabilir:
    - **Ad**: Şirket Portalı’nda görüntülendiği şekliyle uygulamanın adını girin. Kullandığınız uygulama adlarının benzersiz olduğundan emin olun. Bir uygulama adı iki kez kullanılırsa, Şirket Portalı’nda kullanıcılara yalnızca bir ad gösterilir.
    - **Açıklama**: Uygulama için bir açıklama girin. Bu açıklama Şirket Portalı’nda kullanıcılara görüntülenir.Açıklama şirket portalında kullanıcılara görüntülenir.
    - **Yayımcı**: Uygulama yayıncısının adını girin.
    - **Uygulama mağazası URL’si**: Oluşturmak istediğiniz uygulamanın App Store URL’sini yazın.
    - **Kategori**: İsteğe bağlı olarak, yerleşik uygulama kategorilerinden veya kendi oluşturduğunuz kategorilerden birini ya da birkaçını seçin. Böylelikle, Şirket Portalı’na göz atarken kullanıcıların uygulamayı bulmaları kolaylaşır.
    - **Bunu Şirket Portalı’nda öne çıkan uygulama olarak görüntüle**: Bu seçenek uygulama paketini, kullanıcılar uygulamalara göz atarken Şirket Portalı’nın ana sayfasında göze çarpacak şekilde görüntüler.
    - **Bilgi URL’si**: İsteğe bağlı olarak, bu uygulama hakkında bilgi içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Gizlilik URL’si**: İsteğe bağlı olarak, bu uygulamayla ilgili gizlilik bilgilerini içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Geliştirici**: İsteğe bağlı olarak, uygulama geliştiricisinin adını girin.
    - **Sahip**: İsteğe bağlı olarak, bu uygulamanın sahibi için bir ad girin, örneğin *İK departmanı*.
    - **Notlar**: İsteğe bağlı olarak bu uygulamayla ilişkilendirmek istediğiniz notları girin.
    - **Logo**: İsteğe bağlı olarak, uygulamayla ilişkilendirilecek bir simgeyi karşıya yükleyin. Bu simge, kullanıcılar şirket portalına gözatarken uygulamayla birlikte görüntülenir.
8. **Tamam**’ı seçin.
9. **Ekle**’yi seçin.

Oluşturduğunuz uygulama, uygulamalar listesinde görüntülenir ve burada uygulamayı seçtiğiniz gruplara atayabilirsiniz. 

## <a name="next-steps"></a>Sonraki adımlar
- [Gruplara uygulama ekleme](apps-deploy.md)
