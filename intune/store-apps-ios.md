---
title: iOS mağaza uygulamalarını Microsoft Intune’a ekleme
titleSuffix: ''
description: Microsoft Intune'a iOS mağazası uygulamaları ekleme hakkında bilgi edinin. Bu yöntemi kullanarak App Store'da ücretsiz olan uygulamaları atayabilirsiniz.
keywords: Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/27/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: c59514d7-1256-4576-9380-e7a0b85a0378
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 40bb5e1b14fa0c8c9b1af4e5a07e6a855808324a
ms.sourcegitcommit: 6c74ff568267d85fd1d44fda75e3e24ead87cb2b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/28/2019
ms.locfileid: "71303128"
---
# <a name="add-ios-store-apps-to-microsoft-intune"></a>iOS mağaza uygulamalarını Microsoft Intune’a ekleme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bu makaledeki bilgileri kullanarak iOS mağaza uygulamalarını Microsoft Intune’a eklemeyi öğrenin. iOS mağaza uygulamaları, Intune’un kullanıcılarınızın cihazlarına yüklediği uygulamalardır. Bir kullanıcı, şirketinizin iş gücünün bir parçasıdır. iOS mağaza uygulamaları otomatik olarak güncelleştirilir.

>[!NOTE]
>iOS kullanıcıları bazı yerleşik iOS uygulamalarını (Stocks ve Harita gibi) kaldırabilir ve siz, bu uygulamaları yeniden dağıtmak için Intune’u kullanamazsınız. Kullanıcılarınız bu uygulamaları silerse App Store’a gidip el ile yeniden yüklemeleri gerekir.

## <a name="before-you-start"></a>Başlamadan önce

Bu yöntemi kullanarak yalnızca App Store’da ücretsiz olan uygulamaları atayabilirsiniz. Intune kullanarak ücretli uygulamaları atamak isterseniz [iOS toplu satın alma programı](vpp-apps-ios.md) kullanmayı düşünebilirsiniz.

>[!NOTE]
>Microsoft Intune ile çalışırken Microsoft Edge veya Google Chrome tarayıcılarını kullanmanızı öneririz.

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
3. **Intune** bölmesinde **İstemci uygulamaları**’nı seçin.
4. **İstemci uygulamaları** iş yükü bölmesindeki **Yönet**’in altında **Uygulamalar**’ı seçin.
5. **Uygulamalar** bölmesinde **Ekle**’yi seçin.
6. **Uygulama türü** listesindeki **Mağaza uygulaması** türleri altında **iOS**’u seçin.
7. **App Store’da Ara**’yı seçin.
8. **App Store 'Da ara** bölmesinde, App Store ülke/bölge yerel ayarını seçin.
9. **Ara** kutusuna uygulama adını (veya adın bir kısmını) yazın.  
    Intune, mağazada arama yapar ve ilgili sonuçların listesini getirir.
10. Sonuçlar listesinde istediğiniz uygulamayı seçin ve ardından **Seçin**’e tıklayın.
11. Uygulamayı yapılandırmak için **Uygulama ekle** bölmesinde **Uygulama bilgileri**’ni seçin.
12. **Uygulama bilgileri** bölmesinde uygulama bilgilerini ekleyin. Seçtiğiniz uygulamaya bağlı olarak, bölmedeki değerlerden bazıları otomatik olarak doldurulmuş olabilir:
    - **Ad**: Şirket portalında görüntülendiği şekliyle uygulamanın adını girin. Kullandığınız uygulama adlarının benzersiz olduğundan emin olun. Bir uygulama adı iki kez kullanılırsa, Şirket Portalı’nda kullanıcılara yalnızca bir ad gösterilir.
    - **Açıklama**: Uygulama için bir açıklama girin. Bu açıklama Şirket Portalı’nda kullanıcılara görüntülenir.Açıklama şirket portalında kullanıcılara görüntülenir.
    - **Yayımcı**: Uygulama yayımcısının adını girin.
    - **Appstore URL'si**: Oluşturmak istediğiniz uygulamanın App Store URL’sini yazın.
    - **Minimum işletim sistemi**: Listeden uygulamanın yüklenebileceği en eski işletim sistemi sürümünü seçin. Uygulamayı daha önceki bir işletim sistemini çalıştıran cihazlara atarsanız, uygulama yüklenmez.
    - **İlgili cihaz türü**: Uygulama tarafından kullanılan cihazları listeden seçin.
    - **Kategori**: İsteğe bağlı olarak, yerleşik uygulama kategorilerinden veya kendi oluşturduğunuz kategorilerden birini ya da birkaçını seçin. Böylelikle, Şirket Portalı’na göz atarken kullanıcıların uygulamayı bulmaları kolaylaşır.
    - **Şirket Portalı’nda bu uygulamayı öne çıkan uygulama olarak görüntüle**: Kullanıcılar uygulamalara göz attığında, uygulama paketini şirket portalının ana sayfasında önce çıkacak şekilde görüntülemek için bu seçeneği belirleyin.
    - **Bilgi URL'si**: İsteğe bağlı olarak, bu uygulama hakkında bilgi içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Gizlilik URL’si**: İsteğe bağlı olarak, bu uygulamayla ilgili gizlilik bilgilerini içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Geliştirici**: İsteğe bağlı olarak, uygulama geliştiricisinin adını girin. Bu alan yalnızca yöneticilerinize görünür, kullanıcılarınız tarafından görülemez.
    - **Sahip**: İsteğe bağlı olarak, bu uygulamanın sahibi için bir ad girin, örneğin *İK departmanı*. Bu alan yalnızca yöneticilerinize görünür, kullanıcılarınız tarafından görülemez.
    - **Notlar**: İsteğe bağlı olarak bu uygulamayla ilişkilendirmek istediğiniz notları girin. Bu alan yalnızca bir yönetici tarafından görülebilir, son kullanıcılar tarafından görülemez.
    - **Logo**: İsteğe bağlı olarak, uygulamayla ilişkilendirilecek bir simgeyi karşıya yükleyin. Bu simge, kullanıcılar şirket portalına gözatarken uygulamayla birlikte görüntülenir.
13. **Tamam**’ı seçin.
14. **Add (Ekle)** seçeneğini belirleyin.

Oluşturduğunuz uygulama, uygulamalar listesinde görüntülenir ve burada uygulamayı seçtiğiniz gruplara atayabilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

- [Gruplara uygulama ekleme](apps-deploy.md)
