---
title: iOS mağaza uygulamalarını Microsoft Intune’a ekleme
titleSuffix: ''
description: Microsoft Intune'a iOS mağazası uygulamaları ekleme hakkında bilgi edinin. Bu yöntemi kullanarak App Store'da ücretsiz olan uygulamaları atayabilirsiniz.
keywords: Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: c59514d7-1256-4576-9380-e7a0b85a0378
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c5616b27b97d5623958ec872390e2a6de79db3c5
ms.sourcegitcommit: 73b362173929f59e9df57e54e76d19834f155433
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/27/2019
ms.locfileid: "74563445"
---
# <a name="add-ios-store-apps-to-microsoft-intune"></a>iOS mağaza uygulamalarını Microsoft Intune’a ekleme

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Bu makaledeki bilgileri kullanarak iOS mağaza uygulamalarını Microsoft Intune’a eklemeyi öğrenin. iOS mağaza uygulamaları, Intune’un kullanıcılarınızın cihazlarına yüklediği uygulamalardır. Bir kullanıcı, şirketinizin iş gücünün bir parçasıdır. iOS mağaza uygulamaları otomatik olarak güncelleştirilir.

>[!NOTE]
>iOS kullanıcıları bazı yerleşik iOS uygulamalarını (Stocks ve Harita gibi) kaldırabilir ve siz, bu uygulamaları yeniden dağıtmak için Intune’u kullanamazsınız. Kullanıcılarınız bu uygulamaları silerse App Store’a gidip el ile yeniden yüklemeleri gerekir.

## <a name="before-you-start"></a>Başlamadan önce

Bu yöntemi kullanarak yalnızca App Store’da ücretsiz olan uygulamaları atayabilirsiniz. Intune kullanarak ücretli uygulamaları atamak isterseniz [iOS toplu satın alma programı](vpp-apps-ios.md) kullanmayı düşünebilirsiniz.

>[!NOTE]
>Microsoft Intune ile çalışırken Microsoft Edge veya Google Chrome tarayıcılarını kullanmanızı öneririz.

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. **Tüm uygulamalar** ** >  > ** **Ekle**' yi seçin.
3. **Uygulama türü** listesindeki **Mağaza uygulaması** türleri altında **iOS**’u seçin.
4. **App Store’da Ara**’yı seçin.
5. **App Store 'Da ara** bölmesinde, App Store ülke/bölge yerel ayarını seçin.
6. **Ara** kutusuna uygulama adını (veya adın bir kısmını) yazın.  
    Intune, mağazada arama yapar ve ilgili sonuçların listesini getirir.
7. Sonuçlar listesinde istediğiniz uygulamayı seçin ve ardından **Seçin**’e tıklayın.
8. Uygulamayı yapılandırmak için **Uygulama ekle** bölmesinde **Uygulama bilgileri**’ni seçin.
9. **Uygulama bilgileri** bölmesinde uygulama bilgilerini ekleyin. Seçtiğiniz uygulamaya bağlı olarak, bölmedeki değerlerden bazıları otomatik olarak doldurulmuş olabilir:
    - **Ad**: Şirket Portalı’nda görüntülendiği şekliyle uygulamanın adını girin. Kullandığınız uygulama adlarının benzersiz olduğundan emin olun. Bir uygulama adı iki kez kullanılırsa, Şirket Portalı’nda kullanıcılara yalnızca bir ad gösterilir.
    - **Açıklama**: Uygulama için bir açıklama girin. Bu açıklama Şirket Portalı’nda kullanıcılara görüntülenir.Açıklama şirket portalında kullanıcılara görüntülenir.
    - **Yayımcı**: Uygulama yayımcısının adını girin.
    - **Uygulama mağazası URL’si**: Oluşturmak istediğiniz uygulamanın App Store URL’sini yazın.
    - **En düşük işletim sistemi**: Listeden uygulamanın yüklenebileceği en eski işletim sistemi sürümünü seçin. Uygulamayı daha önceki bir işletim sistemini çalıştıran cihazlara atarsanız, uygulama yüklenmez.
    - **Geçerli cihaz türü**: Uygulama tarafından kullanılan cihazları listeden seçin.
    - **Kategori**: İsteğe bağlı olarak, yerleşik uygulama kategorilerinden veya kendi oluşturduğunuz kategorilerden birini ya da birkaçını seçin. Böylelikle, Şirket Portalı’na göz atarken kullanıcıların uygulamayı bulmaları kolaylaşır.
    - **Bunu Şirket Portalı’nda öne çıkan uygulama olarak görüntüle**: Bu seçenek uygulama paketini, kullanıcılar uygulamalara göz atarken Şirket Portalı’nın ana sayfasında göze çarpacak şekilde görüntüler.
    - **Bilgi URL’si**: İsteğe bağlı olarak, bu uygulama hakkında bilgi içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Gizlilik URL’si**: İsteğe bağlı olarak, bu uygulamayla ilgili gizlilik bilgilerini içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Geliştirici**: İsteğe bağlı olarak, uygulama geliştiricisinin adını girin. Bu alan yalnızca yöneticilerinize görünür, kullanıcılarınız tarafından görülemez.
    - **Sahip**: İsteğe bağlı olarak, bu uygulamanın sahibi için bir ad girin, örneğin *İK departmanı*. Bu alan yalnızca yöneticilerinize görünür, kullanıcılarınız tarafından görülemez.
    - **Notlar**: İsteğe bağlı olarak bu uygulamayla ilişkilendirmek istediğiniz notları girin. Bu alan yalnızca bir yönetici tarafından görülebilir, son kullanıcılar tarafından görülemez.
    - **Logo**: İsteğe bağlı olarak, uygulamayla ilişkilendirilecek bir simgeyi karşıya yükleyin. Bu simge, kullanıcılar şirket portalına gözatarken uygulamayla birlikte görüntülenir.
10. **Tamam**’ı seçin.
11. **Ekle**’yi seçin.

Oluşturduğunuz uygulama, uygulamalar listesinde görüntülenir ve burada uygulamayı seçtiğiniz gruplara atayabilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

- [Gruplara uygulama ekleme](apps-deploy.md)
