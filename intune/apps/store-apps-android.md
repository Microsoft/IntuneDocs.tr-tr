---
title: Android mağazası uygulamalarını Microsoft Intune’a ekleme
titleSuffix: ''
description: Google Play deposundan Android mağaza uygulamalarını Microsoft Intune 'a eklemeyi öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/22/2020
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
ms.openlocfilehash: e6b9f6a9303e53652959639193633cdcc00dfb99
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2020
ms.locfileid: "76755094"
---
# <a name="add-android-store-apps-to-microsoft-intune"></a>Android mağazası uygulamalarını Microsoft Intune’a ekleme

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Bir cihaza veya kullanıcı grubuna uygulama atamadan önce uygulamayı ilk olarak Microsoft Intune’a eklemeniz gerekir. 

## <a name="add-an-app"></a>Uygulama ekleme

Aşağıdakileri yaparak, Azure portalından Intune’a bir Android mağaza uygulaması ekleyebilirsiniz:

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. **Tüm uygulamalar** ** >  > ** **Ekle**' yi seçin.
3. **Uygulama türünü seçin** bölmesinde, kullanılabilir **Mağaza uygulama** türleri altında, **Android Mağazası uygulaması**' nı seçin.
4. **Seçin**’e tıklayın.<br>
   **Uygulama ekleme** adımları görüntülenir.
5. Android uygulaması için **uygulama bilgilerini** yapılandırmak üzere [Google Play deposuna](https://play.google.com/store) gidin ve dağıtmak istediğiniz uygulamayı arayın. Uygulama sayfasını görüntüleyin ve uygulama ayrıntılarını bir yere göz önünde yapın. 
6. **Uygulama bilgileri** sayfasında, uygulama ayrıntılarını ekleyin:
    - **Ad**: Şirket Portalı’nda görüntülendiği şekliyle uygulamanın adını girin. Kullandığınız uygulama adlarının benzersiz olduğundan emin olun. Bir uygulama adı iki kez kullanılırsa, Şirket Portalı’nda kullanıcılara yalnızca bir ad gösterilir.
    - **Açıklama**: Uygulama için bir açıklama girin. Bu açıklama Şirket Portalı’nda kullanıcılara görüntülenir.Açıklama şirket portalında kullanıcılara görüntülenir.
    - **Yayımcı**: Uygulama yayımcısının adını girin.
    - **Uygulama mağazası URL’si**: Oluşturmak istediğiniz uygulamanın uygulama mağazası URL’sini girin. Uygulamanın ayrıntıları mağazada görüntülenirken uygulama sayfasının URL 'sini kullanın. 
    - **En düşük işletim sistemi**: Listeden uygulamanın yüklenebileceği en eski işletim sistemi sürümünü seçin. Uygulamayı daha önceki bir işletim sistemini çalıştıran cihazlara atarsanız, uygulama yüklenmez.
    - **Kategori**: İsteğe bağlı olarak, yerleşik uygulama kategorilerinden veya kendi oluşturduğunuz kategorilerden birini ya da birkaçını seçin. Böylelikle, Şirket Portalı’na göz atarken kullanıcıların uygulamayı bulmaları kolaylaşır.
    - **Bunu şirket portalı öne çıkan uygulama olarak göster**: kullanıcılar uygulamalara gözatarken, uygulama paketini Şirket portalının ana sayfasında göze çarpacak şekilde görüntülemek için bu seçeneği belirleyin. Kullanılabilir amaç ile dağıtılan uygulamalar için geçerlidir.
    - **Bilgi URL’si**: İsteğe bağlı olarak, bu uygulama hakkında bilgi içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Gizlilik URL’si**: İsteğe bağlı olarak, bu uygulamayla ilgili gizlilik bilgilerini içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Geliştirici**: İsteğe bağlı olarak, uygulama geliştiricisinin adını girin.
    - **Sahip**: İsteğe bağlı olarak, bu uygulamanın sahibi için bir ad girin, örneğin *İK departmanı*.
    - **Notlar**: İsteğe bağlı olarak bu uygulamayla ilişkilendirmek istediğiniz notları girin.
    - **Logo**: İsteğe bağlı olarak, uygulamayla ilişkilendirilecek bir simgeyi karşıya yükleyin. Bu simge, kullanıcılar şirket portalına gözatarken uygulamayla birlikte görüntülenir.
7. **İleri** ' ye tıklayarak **kapsam etiketleri** sayfasını görüntüleyin.
8. İsteğe bağlı olarak uygulamanın kapsam etiketlerini eklemek için **kapsam etiketlerini Seç** ' e tıklayın. Daha fazla bilgi için bkz. [Dağıtılmış BT için rol tabanlı erişim denetimi (RBAC) ve kapsam etiketleri kullanma](~/fundamentals/scope-tags.md).
9. **Atamalar** sayfasını göstermek için **İleri** ' ye tıklayın.
10. Uygulama için Grup atamalarını seçin. Daha fazla bilgi için bkz. [kullanıcıları ve cihazları düzenlemek için grup ekleme](~/fundamentals/groups-add.md). 
11. **İleri** ' ye tıklayarak **gözden geçir + oluştur** sayfasını görüntüleyin. Uygulama için girdiğiniz değerleri ve ayarları gözden geçirin.
12. İşiniz bittiğinde, uygulamayı Intune 'a eklemek için **Oluştur** ' a tıklayın.

Oluşturduğunuz uygulamanın **genel bakış** dikey penceresi görüntülenir.

## <a name="next-steps"></a>Sonraki adımlar

- [Gruplara uygulama ekleme](apps-deploy.md)
