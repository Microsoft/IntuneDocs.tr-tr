---
title: Windows Phone 8.1 mağazası uygulamalarını Microsoft Intune’a ekleme
titleSuffix: ''
description: Bu konu, Microsoft Intune Windows Phone 8,1 Mağaza uygulamalarının nasıl ekleneceğini açıklar.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/23/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 4a95e575-2c63-4bfc-b9c4-f0a132eef618
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6f749371a6fe2410386ba0cc10e043699e841d2f
ms.sourcegitcommit: c8cb314256c4896e838918f015ffaefb8f00ace5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/23/2019
ms.locfileid: "71302930"
---
# <a name="add-windows-phone-81-store-apps-to-microsoft-intune"></a>Windows Phone 8.1 mağazası uygulamalarını Microsoft Intune’a ekleme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bir cihaza veya kullanıcı grubuna uygulama atamadan önce uygulamayı ilk olarak Microsoft Intune’a eklemeniz gerekir. 

## <a name="add-an-app-to-intune"></a>Intune’a uygulama ekleme
Aşağıdakileri yaparak, Azure portalından Intune’a bir Windows Phone 8.1 mağaza uygulaması ekleyebilirsiniz:

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
3. **Intune** bölmesinde **İstemci uygulamaları**’nı seçin.
4. **İstemci uygulamaları** iş yükü bölmesindeki **Yönet**’in altında **Uygulamalar**’ı seçin.
5. **Uygulamalar** bölmesinde **Ekle**’yi seçin.
6. **Uygulama ekle** bölmesinde, **Uygulama türü** olarak **Windows Phone 8.1**’i ve **Uygulama bilgileri**’ni seçin.
7. **Uygulama bilgileri** bölmesinde uygulama bilgilerini ekleyin. Seçtiğiniz uygulamaya bağlı olarak, bölmedeki değerlerden bazıları otomatik olarak doldurulmuş olabilir:
    - **Ad**: Şirket portalında görüntülendiği şekliyle uygulamanın adını girin. Kullandığınız uygulama adlarının benzersiz olduğundan emin olun. Bir uygulama adı iki kez kullanılırsa, Şirket Portalı’nda kullanıcılara yalnızca bir ad gösterilir.
    - **Açıklama**: Uygulama için bir açıklama girin. Bu açıklama Şirket Portalı’nda kullanıcılara görüntülenir.Açıklama şirket portalında kullanıcılara görüntülenir.
    - **Yayımcı**: Uygulama yayımcısının adını girin.
    - **Appstore URL'si**: Oluşturmak istediğiniz uygulamanın App Store URL’sini yazın.
    - **Kategori**: İsteğe bağlı olarak, yerleşik uygulama kategorilerinden veya kendi oluşturduğunuz kategorilerden birini ya da birkaçını seçin. Böylelikle, Şirket Portalı’na göz atarken kullanıcıların uygulamayı bulmaları kolaylaşır.
    - **Şirket Portalı’nda bu uygulamayı öne çıkan uygulama olarak görüntüle**: Kullanıcılar uygulamalara göz attığında, uygulama paketini şirket portalının ana sayfasında önce çıkacak şekilde görüntülemek için bu seçeneği belirleyin.
    - **Bilgi URL'si**: İsteğe bağlı olarak, bu uygulama hakkında bilgi içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Gizlilik URL’si**: İsteğe bağlı olarak, bu uygulamayla ilgili gizlilik bilgilerini içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Geliştirici**: İsteğe bağlı olarak, uygulama geliştiricisinin adını girin.
    - **Sahip**: İsteğe bağlı olarak, bu uygulamanın sahibi için bir ad girin, örneğin *İK departmanı*.
    - **Notlar**: İsteğe bağlı olarak bu uygulamayla ilişkilendirmek istediğiniz notları girin.
    - **Logo**: İsteğe bağlı olarak, uygulamayla ilişkilendirilecek bir simgeyi karşıya yükleyin. Bu simge, kullanıcılar şirket portalına gözatarken uygulamayla birlikte görüntülenir.
8. **Tamam**’ı seçin.
9. **Add (Ekle)** seçeneğini belirleyin.

Oluşturduğunuz uygulama, uygulamalar listesinde görüntülenir ve burada uygulamayı seçtiğiniz gruplara atayabilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

- [Gruplara uygulama ekleme](apps-deploy.md)
