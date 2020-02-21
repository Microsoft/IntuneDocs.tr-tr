---
title: iOS mağaza uygulamalarını Microsoft Intune’a ekleme
titleSuffix: ''
description: Microsoft Intune'a iOS mağazası uygulamaları ekleme hakkında bilgi edinin. Bu yöntemi kullanarak App Store'da ücretsiz olan uygulamaları atayabilirsiniz.
keywords: Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/22/2020
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
ms.openlocfilehash: f2baf60fed2c6010e5ae0784cda166ac4fabfd57
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77511744"
---
# <a name="add-ios-store-apps-to-microsoft-intune"></a>iOS mağaza uygulamalarını Microsoft Intune’a ekleme

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Bu makaledeki bilgileri kullanarak iOS mağaza uygulamalarını Microsoft Intune’a eklemeyi öğrenin. iOS mağaza uygulamaları, Intune’un kullanıcılarınızın cihazlarına yüklediği uygulamalardır. Bir kullanıcı, şirketinizin iş gücünün bir parçasıdır. iOS mağaza uygulamaları otomatik olarak güncelleştirilir.

>[!NOTE]
>İOS/ıpados cihazlarının kullanıcıları, hisse senetleri ve haritalar gibi bazı yerleşik iOS/ıpados uygulamalarını kaldırabilse de, bu uygulamaları yeniden dağıtmak için Intune 'U kullanamazsınız. Kullanıcılarınız bu uygulamaları silerse App Store’a gidip el ile yeniden yüklemeleri gerekir.

## <a name="before-you-start"></a>Başlamadan önce

Bu yöntemi kullanarak yalnızca App Store’da ücretsiz olan uygulamaları atayabilirsiniz. Intune kullanarak ücretli uygulamalar atamak istiyorsanız [iOS/ıpados toplu satın alma programını](vpp-apps-ios.md)kullanmayı deneyin.

>[!NOTE]
>Microsoft Intune ile çalışırken Microsoft Edge veya Google Chrome tarayıcılarını kullanmanızı öneririz.

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. **Tüm uygulamalar** ** >  > ** **Ekle**' yi seçin.
3. **Uygulama türünü seçin** bölmesinde, kullanılabilir **Mağaza uygulama** türleri altında **iOS Mağazası uygulaması**' nı seçin.
4. **Seçin**’e tıklayın.<br>
   **Uygulama ekleme** adımları görüntülenir.
5. **App Store’da Ara**’yı seçin.
6. **App Store 'Da ara** bölmesinde, App Store ülke/bölge yerel ayarını seçin.
7. **Ara** kutusuna uygulama adını (veya adın bir kısmını) yazın.  
    Intune, mağazada arama yapar ve ilgili sonuçların listesini getirir.
8. Sonuçlar listesinde istediğiniz uygulamayı seçin ve ardından **Seçin**’e tıklayın.<br>

   **Uygulama bilgileri** sayfası, **Uygulama Ekle** bölmesinde görüntülenir. Mümkün olduğunda, uygulama bilgileri mağazadan seçtiğiniz uygulamaya bağlı olarak eklenecektir.

9. **Uygulama bilgileri** sayfasında, uygulama ayrıntılarını ekleyin. Seçtiğiniz uygulamaya bağlı olarak, bölmedeki değerlerden bazıları otomatik olarak doldurulmuş olabilir:
    - **Ad**: Şirket Portalı’nda görüntülendiği şekliyle uygulamanın adını girin. Kullandığınız uygulama adlarının benzersiz olduğundan emin olun. Bir uygulama adı iki kez kullanılırsa, Şirket Portalı’nda kullanıcılara yalnızca bir ad gösterilir.
    - **Açıklama**: Uygulama için bir açıklama girin. Bu açıklama Şirket Portalı’nda kullanıcılara görüntülenir.Açıklama şirket portalında kullanıcılara görüntülenir.
    - **Yayımcı**: Uygulama yayıncısının adını girin.
    - **Uygulama mağazası URL’si**: Oluşturmak istediğiniz uygulamanın App Store URL’sini yazın.
    - **En düşük işletim sistemi**: Listeden uygulamanın yüklenebileceği en eski işletim sistemi sürümünü seçin. Uygulamayı daha önceki bir işletim sistemini çalıştıran cihazlara atarsanız, uygulama yüklenmez.
    - **Geçerli cihaz türü**: Uygulama tarafından kullanılan cihazları listeden seçin.
    - **Kategori**: İsteğe bağlı olarak, yerleşik uygulama kategorilerinden veya kendi oluşturduğunuz kategorilerden birini ya da birkaçını seçin. Böylelikle, Şirket Portalı’na göz atarken kullanıcıların uygulamayı bulmaları kolaylaşır.
    - **Bunu şirket portalı öne çıkan uygulama olarak göster**: kullanıcılar uygulamalara gözatarken, uygulama paketini Şirket portalının ana sayfasında göze çarpacak şekilde görüntülemek için bu seçeneği belirleyin.
    - **Bilgi URL’si**: İsteğe bağlı olarak, bu uygulama hakkında bilgi içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Gizlilik URL’si**: İsteğe bağlı olarak, bu uygulamayla ilgili gizlilik bilgilerini içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Geliştirici**: İsteğe bağlı olarak, uygulama geliştiricinin adını girin. Bu alan yalnızca yöneticilerinize görünür, kullanıcılarınız tarafından görülemez.
    - **Sahip**: İsteğe bağlı olarak, bu uygulamanın sahibi için bir ad girin, örneğin *İK departmanı*. Bu alan yalnızca yöneticilerinize görünür, kullanıcılarınız tarafından görülemez.
    - **Notlar**: İsteğe bağlı olarak bu uygulamayla ilişkilendirmek istediğiniz notları girin. Bu alan yalnızca bir yönetici tarafından görülebilir, son kullanıcılar tarafından görülemez.
    - **Logo**: İsteğe bağlı olarak, uygulamayla ilişkilendirilecek bir simgeyi karşıya yükleyin. Bu simge, kullanıcılar şirket portalına gözatarken uygulamayla birlikte görüntülenir.
10. **İleri** ' ye tıklayarak **kapsam etiketleri** sayfasını görüntüleyin.
11. İsteğe bağlı olarak uygulamanın kapsam etiketlerini eklemek için **kapsam etiketlerini Seç** ' e tıklayın. Daha fazla bilgi için bkz. [Dağıtılmış BT için rol tabanlı erişim denetimi (RBAC) ve kapsam etiketleri kullanma](~/fundamentals/scope-tags.md).
12. **Atamalar** sayfasını göstermek için **İleri** ' ye tıklayın.
13. Uygulama için Grup atamalarını seçin. Daha fazla bilgi için bkz. [kullanıcıları ve cihazları düzenlemek için grup ekleme](~/fundamentals/groups-add.md). 
14. **İleri** ' ye tıklayarak **gözden geçir + oluştur** sayfasını görüntüleyin. Uygulama için girdiğiniz değerleri ve ayarları gözden geçirin.
15. İşiniz bittiğinde, uygulamayı Intune 'a eklemek için **Oluştur** ' a tıklayın.

Oluşturduğunuz uygulamanın **genel bakış** dikey penceresi görüntülenir.

## <a name="next-steps"></a>Sonraki adımlar

- [Gruplara uygulama ekleme](apps-deploy.md)
