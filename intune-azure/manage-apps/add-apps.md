---
title: "Microsoft Intune’a uygulama ekleme"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Bu yordamlar, uygulamalarınızı kullanıcılara ve cihazlara atanmaya hazır durumda Intune’a almanıza yardımcı olur. "
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1ded457-0ecf-4f9c-a2d2-857d57f8d30a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: d85544bdfaa3a369e1d2d03e5454ff7aa2d75467
ms.lasthandoff: 04/19/2017

---

# <a name="how-to-add-an-app-to-microsoft-intune"></a>Microsoft Intune’a uygulama ekleme

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Kullanıcılarınız için uygulamaları yönetmeden ve atamadan önce, bunları Intune’a eklemeniz gerekir. Intune, birbirinden farklı çok çeşitli uygulama türlerini destekler ve türlerin her biri için seçenekler farklı olabilir.

Intune aşağıdaki uygulama türlerini eklemenize ve atamanıza izin verir:

![Intune tarafından desteklenen uygulama türleri](./media/app-types.png)

Şu platformlar desteklenir. Her uygulama türünün nasıl eklendiği hakkında daha fazla bilgi için başlıklardan birine tıklayın.

- [Android mağaza uygulamaları](/intune-azure/manage-apps/android-store-app)
- [Android LOB uygulamaları](/intune-azure/manage-apps/android-lob-app)
- [iOS Store uygulamaları](/intune-azure/manage-apps/ios-store-app)
- [iOS LOB uygulamaları](/intune-azure/manage-apps/ios-lob-app)
- [Web uygulamaları (tüm platformlar için)](/intune-azure/manage-apps/web-app)
- [Windows Phone 8.1 mağaza uygulamaları](/intune-azure/manage-apps/windows-phone-8-1-store-app)
- [Windows Mağazası uygulamaları](/intune-azure/manage-apps/windows-store-app)

Ayrıca, bazı Microsoft uygulamaları kiracınızı ayarladığınızda Intune tarafından otomatik olarak eklenir. Bu konunun ilerleyen bölümlerinde bunların bir listesi bulacaksınız.

## <a name="before-you-start"></a>Başlamadan önce

Uygulamaları eklemeye ve atamaya başlamadan önce aşağıdaki noktaları göz önünde bulundurun.

- Bir mağazadan uygulama eklediğinizde ve dağıttığınızda, son kullanıcıların uygulamayı yükleyebilmesi için o mağazada bir hesapları olması gerekir.
- Dağıttınız uygulama veya öğelerden bazıları yerleşik iOS uygulamalarına bağlı olabilir. Örneğin, iOS mağazasından bir kitap dağıtırsanız cihazda iBooks uygulaması olmalıdır. Yerleşik iBooks uygulamasını kaldırdıysanız, yeniden devreye sokmak için Intune'u kullanamazsınız.

## <a name="cloud-storage-space"></a>Bulut depolama alanı
Yazılım yükleyicisi yükleme türünü kullanarak oluşturduğunuz tüm uygulamalar (örneğin, bir iş kolu uygulaması) paketlenir ve Microsoft Intune bulut depolama alanına yüklenir. Intune deneme aboneliği, yönetilen uygulamaları ve güncelleştirmeleri depolamak için kullanılan 2 gigabayt (GB) bulut tabanlı depolama alanı içerir. Tam aboneliğiniz 20 GB depolama alanı içerir.

İlk satın alma yönteminizi kullanarak Intune için ek depolama alanı satın alabilirsiniz.  Fatura veya kredi kartıyla ödeme yaptıysanız [Abonelik Yönetim portalını](https://portal.office.com/adminportal/home?switchtomodern=true#/subscriptions) ziyaret edin.  Başka bir satın alma yöntemi kullandıysanız iş ortağınız veya satış yardımcınızla iletişime geçin.

Bulut depolama alanı gereksinimleri aşağıda belirtilmiştir:

-   Tüm uygulama yükleme dosyaları aynı klasörde olmalıdır.
-   Karşıya yüklediğiniz her dosya için dosya boyutu üst sınırı 2 GB'dir.

## <a name="how-to-create-and-edit-categories-for-apps"></a>Uygulamalar için kategorileri oluşturma ve düzenleme

Uygulama kategorileri, son kullanıcıların şirket portalında daha kolay bulabilmeleri için uygulamaları sıralamanıza yardımcı olabilir. Uygulamaya, **Geliştirici uygulamaları** veya **İletişim uygulamaları** gibi bir veya birden çok kategori atayabilirsiniz.
Uygulamayı Intune’a eklediğinizde, size istediğiniz kategoriyi belirtme seçeneği sağlanır. Uygulama eklemek ve kategorileri atamak için, platforma özgü konu başlıklarını kullanın. Kendi kategorilerinizi oluşturmak ve düzenlemek için aşağıdaki yordamı kullanın:

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Uygulamaları yönet**’i seçin.
4. **Mobil uygulamalar** iş yükünde **Kurulum** > **Uygulama kategorileri**’ni seçin.
5. **Uygulama kategorileri** dikey penceresinde geçerli kategorilerin listesi gösterilir. Aşağıdaki eylemlerden birini seçin:
    - **Kategori oluştur** - **Kategori oluştur** dikey penceresinde yeni kategori için bir ad girin. Adlar tek bir dilde girilebilir ve Intune tarafından bunların çevirisi yapılmaz. İşiniz bittiğinde **Oluştur**’a tıklayın.
    - **Kategori düzenle** - Listedeki herhangi bir kategori için, '**...**' düğmesini seçin. **Özellikler** dikey penceresinde, kategori için yeni bir ad girebilir veya kategoriyi silebilirsiniz.


## <a name="apps-added-automatically-by-intune"></a>Intune tarafından otomatik olarak eklenen uygulamalar

Microsoft tarafından yayımlanan aşağıdaki uygulamalar, Intune’da yerleşiktir ve atama yapmanız için hazırdır:

|||
|-|-|
|Ad|Platform|Uygulama türü|
|Azure Information Protection|Android|Yönetilen Android mağazası uygulaması|
|Telefonlar için Dynamics CRM|Android|Yönetilen Android mağazası uygulaması|
|Tabletler için Dynamics CRM|Android|Yönetilen Android mağazası uygulaması|
|Excel|iOS|Yönetilen iOS mağazası uygulaması|
|Excel|Android|Yönetilen Android mağazası uygulaması|
|Managed Browser|Android|Yönetilen Android mağazası uygulaması|
|Managed Browser|iOS|Yönetilen iOS mağazası uygulaması|
|Telefonlarda Microsoft Dynamics CRM|iOS|Yönetilen iOS mağazası uygulaması|
|Tabletlerde Microsoft Dynamics CRM|iOS|Yönetilen iOS mağazası uygulaması|
|Microsoft Power BI|iOS|Yönetilen iOS mağazası uygulaması|
|Microsoft Power BI|Android|Yönetilen Android mağazası uygulaması|
|Microsoft SharePoint|iOS|Yönetilen iOS mağazası uygulaması|
|Microsoft SharePoint|Android|Yönetilen Android mağazası uygulaması|
|Microsoft Teams|Android|Yönetilen Android mağazası uygulaması|
|Microsoft Teams|iOS|Yönetilen iOS mağazası uygulaması|
|OneDrive|iOS|Yönetilen iOS mağazası uygulaması|
|OneDrive|Android|Yönetilen Android mağazası uygulaması|
|OneNote|iOS|Yönetilen iOS mağazası uygulaması|
|Outlook|Android|Yönetilen Android mağazası uygulaması|
|Outlook|iOS|Yönetilen iOS mağazası uygulaması|
|Outlook Groups|Android|Yönetilen Android mağazası uygulaması|
|Outlook Groups|iOS|Yönetilen iOS mağazası uygulaması|
|PowerPoint|iOS|Yönetilen iOS mağazası uygulaması|

