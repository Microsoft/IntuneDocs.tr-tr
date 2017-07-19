---
title: "Microsoft Intune’a uygulama ekleme"
titleSuffix: Intune on Azure
description: "Bu yordamlar, uygulamalarınızı Intune’a kullanıcılara ve cihazlara atanmaya hazır durumda almanıza yardımcı olur. \""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1ded457-0ecf-4f9c-a2d2-857d57f8d30a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6a4dfa9e0066a2ac6f410aa9f8e4d77a40484ea5
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="how-to-add-an-app-to-microsoft-intune"></a>Microsoft Intune’a uygulama ekleme

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Kullanıcılarınız için uygulamaları yönetmeden ve atamadan önce, bunları Intune’a eklemeniz gerekir. Intune, birbirinden farklı çok çeşitli uygulama türlerini destekler ve türlerin her biri için seçenekler farklı olabilir.

Intune aşağıdaki uygulama türlerini eklemenize ve atamanıza izin verir:

![Intune tarafından desteklenen uygulama türleri](./media/app-types.png)

Şu platformlar desteklenir.

- Android mağaza uygulamaları
- Android iş kolu (LOB) uygulamaları
- iOS mağaza uygulamaları
- iOS iş kolu (LOB) uygulamaları
- Web uygulamaları
- Windows Phone 8.1 mağaza uygulamaları
- Windows Phone iş kolu uygulamaları (.xap dosyaları)
- Windows mağazası uygulamaları
- Windows iş kolu uygulamaları (sadece .msi dosyaları)

>[!TIP]
> İş kolu (veya LOB) uygulaması, bir uygulama mağazasından değil uygulama yükleme dosyasından yüklediğiniz bir uygulamadır. Örneğin, bir iOS LOB uygulamasını yüklemek için uygulama arşiv dosyasını (.ipa uzantılı dosya) eklersiniz. Bunlar normal olarak şirket içinde yazdığınız uygulamalardır.

## <a name="before-you-start"></a>Başlamadan önce

Uygulamaları eklemeye ve atamaya başlamadan önce aşağıdaki noktaları göz önünde bulundurun.

- Bir mağazadan uygulama eklediğinizde ve atadığınızda, son kullanıcıların uygulamayı yükleyebilmesi için o mağazada bir hesapları olması gerekir.
- Atadığınız uygulama veya öğelerden bazıları yerleşik iOS uygulamalarına bağlı olabilir. Örneğin, iOS mağazasından bir kitap atarsanız cihazda iBooks uygulaması olmalıdır. Yerleşik iBooks uygulamasını kaldırdıysanız, yeniden devreye sokmak için Intune'u kullanamazsınız.

## <a name="cloud-storage-space"></a>Bulut depolama alanı
Yazılım yükleyicisi yükleme türünü kullanarak oluşturduğunuz tüm uygulamalar (örneğin, bir iş kolu uygulaması) paketlenir ve Intune bulut depolama alanına yüklenir. Intune deneme aboneliği, yönetilen uygulamaları ve güncelleştirmeleri depolamak için kullanılan 2 gigabayt (GB) bulut tabanlı depolama alanı içerir. Tam abonelik 20 GB depolama alanı içerir.

İlk satın alma yönteminizi kullanarak Intune için ek depolama alanı satın alabilirsiniz.  Fatura veya kredi kartıyla ödeme yaptıysanız [Abonelik Yönetim portalını](https://portal.office.com/adminportal/home?switchtomodern=true#/subscriptions) ziyaret edin.  Başka bir satın alma yöntemi kullandıysanız iş ortağınız veya satış yardımcınızla iletişime geçin.

Bulut depolama alanı gereksinimleri aşağıda belirtilmiştir:

-   Tüm uygulama yükleme dosyaları aynı klasörde olmalıdır.
-   Karşıya yüklediğiniz her dosya için dosya boyutu üst sınırı 2 GB'dir.

## <a name="how-to-create-and-edit-categories-for-apps"></a>Uygulamalar için kategorileri oluşturma ve düzenleme

Uygulama kategorileri, kullanıcıların uygulamaları şirket portalında daha kolay bulabilmeleri için sıralamanıza yardımcı olabilir. Uygulamaya, **Geliştirici uygulamaları** veya **İletişim uygulamaları** gibi bir veya birden çok kategori atayabilirsiniz.
Uygulamayı Intune’a eklediğinizde, size istediğiniz kategoriyi belirtme seçeneği sağlanır. Uygulama eklemek ve kategorileri atamak için, platforma özgü konu başlıklarını kullanın. Kendi kategorilerinizi oluşturmak ve düzenlemek için aşağıdaki yordamı kullanın:

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde, **Mobil uygulamalar**’ı seçin.
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

## <a name="next-steps"></a>Sonraki Adımlar

Her platform için Intune’a uygulamaların nasıl eklendiğini öğrenmek için aşağıdaki konulardan birini seçin:

- [Android mağaza uygulamaları](store-apps-android.md)
- [Android LOB uygulamaları](lob-apps-android.md)
- [iOS Store uygulamaları](store-apps-ios.md)
- [iOS LOB uygulamaları](lob-apps-ios.md)
- [Web uygulamaları (tüm platformlar için)](web-app.md)
- [Windows Phone 8.1 mağaza uygulamaları](store-apps-windows-phone-8-1.md)
- [Windows Phone LOB uygulamaları](lob-apps-windows-phone.md)
- [Windows Mağazası uygulamaları](store-apps-windows.md)
- [Windows LOB uygulaması](lob-apps-windows.md)

