---
title: Android mağazası uygulamalarını Microsoft Intune’a ekleme
titleSuffix: ''
description: Google Play deposundan Android mağaza uygulamalarını Microsoft Intune 'a eklemeyi öğrenin.
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
ms.assetid: 4433000a-23e9-4cad-a818-48c28eedc1f5
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ec800064d109cca42878c79ade6777de9b782015
ms.sourcegitcommit: 73b362173929f59e9df57e54e76d19834f155433
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/27/2019
ms.locfileid: "74563496"
---
# <a name="add-android-store-apps-to-microsoft-intune"></a>Android mağazası uygulamalarını Microsoft Intune’a ekleme

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Bir cihaza veya kullanıcı grubuna uygulama atamadan önce uygulamayı ilk olarak Microsoft Intune’a eklemeniz gerekir. 

## <a name="add-an-app"></a>Uygulama ekleme

Aşağıdakileri yaparak, Azure portalından Intune’a bir Android mağaza uygulaması ekleyebilirsiniz:

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. **Tüm uygulamalar** ** >  > ** **Ekle**' yi seçin.
3. **Uygulama Ekle** bölmesindeki kullanılabilir **Mağaza uygulaması** türlerinden **Android**’i seçin.
4. Uygulama bilgilerini yapılandırmak için **Yapılandırma**’yı seçin ve ardından aşağıdaki bilgileri sağlayın. Android uygulamaları için [Google Play mağazası](https://play.google.com/store)’na gidin ve dağıtmak istediğiniz uygulamayı arayın. Uygulamayı seçin ve uygulama ayrıntılarını not edin. Seçtiğiniz uygulamaya bağlı olarak, bazı değerler otomatik olarak doldurulmuş olabilir:
    - **Ad**: Şirket Portalı’nda görüntülendiği şekliyle uygulamanın adını girin. Kullandığınız uygulama adlarının benzersiz olduğundan emin olun. Bir uygulama adı iki kez kullanılırsa, Şirket Portalı’nda kullanıcılara yalnızca bir ad gösterilir.
    - **Açıklama**: Uygulama için bir açıklama girin. Bu açıklama Şirket Portalı’nda kullanıcılara görüntülenir.Açıklama şirket portalında kullanıcılara görüntülenir.
    - **Yayımcı**: Uygulama yayımcısının adını girin.
    - **Uygulama mağazası URL’si**: Oluşturmak istediğiniz uygulamanın uygulama mağazası URL’sini girin.
    - **En düşük işletim sistemi**: Listeden uygulamanın yüklenebileceği en eski işletim sistemi sürümünü seçin. Uygulamayı daha önceki bir işletim sistemini çalıştıran cihazlara atarsanız, uygulama yüklenmez.
    - **Kategori**: İsteğe bağlı olarak, yerleşik uygulama kategorilerinden veya kendi oluşturduğunuz kategorilerden birini ya da birkaçını seçin. Böylelikle, Şirket Portalı’na göz atarken kullanıcıların uygulamayı bulmaları kolaylaşır.
    - **Bunu Şirket Portalı’nda öne çıkan uygulama olarak görüntüle**: Bu seçenek uygulama paketini, kullanıcılar uygulamalara göz atarken Şirket Portalı’nın ana sayfasında göze çarpacak şekilde görüntüler. Kullanılabilir amaç ile dağıtılan uygulamalar için geçerlidir.
    - **Bilgi URL’si**: İsteğe bağlı olarak, bu uygulama hakkında bilgi içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Gizlilik URL’si**: İsteğe bağlı olarak, bu uygulamayla ilgili gizlilik bilgilerini içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Geliştirici**: İsteğe bağlı olarak, uygulama geliştiricisinin adını girin.
    - **Sahip**: İsteğe bağlı olarak, bu uygulamanın sahibi için bir ad girin, örneğin *İK departmanı*.
    - **Notlar**: İsteğe bağlı olarak bu uygulamayla ilişkilendirmek istediğiniz notları girin.
    - **Logo**: İsteğe bağlı olarak, uygulamayla ilişkilendirilecek bir simgeyi karşıya yükleyin. Bu simge, kullanıcılar şirket portalına gözatarken uygulamayla birlikte görüntülenir.
5. **Tamam**’ı seçin.
6. **Ekle**’yi seçin.

Oluşturduğunuz uygulama, uygulamalar listesinde görüntülenir ve burada uygulamayı seçtiğiniz gruplara atayabilirsiniz. 

## <a name="next-steps"></a>Sonraki adımlar

- [Gruplara uygulama ekleme](apps-deploy.md)
