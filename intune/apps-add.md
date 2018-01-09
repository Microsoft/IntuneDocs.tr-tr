---
title: "Microsoft Intune’a uygulama ekleme"
titlesuffix: Azure portal
description: "Bu yordamlar, uygulamalarınızı Intune’a kullanıcılara ve cihazlara atanmaya hazır durumda almanıza yardımcı olur. \""
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 07/17/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1ded457-0ecf-4f9c-a2d2-857d57f8d30a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b33e15e8bd6597464bfe54a5152a872889d08e15
ms.sourcegitcommit: 9fabf1a8db53842f7b00762374de5b137158ee25
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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

Orijinal satın alma metodunuzu kullanarak Intune için ek depolama alanı satın alabilirsiniz.  Fatura veya kredi kartıyla ödeme yaptıysanız [Abonelik Yönetim portalını](https://portal.office.com/adminportal/home?switchtomodern=true#/subscriptions) ziyaret edin.  Başka bir satın alma yöntemi kullandıysanız iş ortağınız veya satış yardımcınızla iletişime geçin.

Bulut depolama alanı gereksinimleri aşağıda belirtilmiştir:

-   Tüm uygulama yükleme dosyaları aynı klasörde olmalıdır.
-   Karşıya yüklediğiniz her dosya için dosya boyutu üst sınırı 2 GB'dir.

## <a name="how-to-create-and-edit-categories-for-apps"></a>Uygulamalar için kategorileri oluşturma ve düzenleme

Uygulama kategorileri, kullanıcıların uygulamaları şirket portalında daha kolay bulabilmeleri için sıralamanıza yardımcı olabilir. Uygulamaya, **Geliştirici uygulamaları** veya **İletişim uygulamaları** gibi bir veya birden çok kategori atayabilirsiniz.
Uygulamayı Intune’a eklediğinizde, size istediğiniz kategoriyi belirtme seçeneği sağlanır. Uygulama eklemek ve kategorileri atamak için, platforma özgü konu başlıklarını kullanın. Kendi kategorilerinizi oluşturmak ve düzenlemek için aşağıdaki yordamı kullanın:

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Mobil uygulamalar**’ı seçin.
4. **Mobil uygulamalar** iş yükünde **Kurulum** > **Uygulama kategorileri**’ni seçin.
5. **Uygulama kategorileri** dikey penceresinde geçerli kategorilerin listesi gösterilir. Aşağıdaki eylemlerden birini seçin:
    - **Kategori oluştur** - **Kategori oluştur** dikey penceresinde yeni kategori için bir ad girin. Adlar tek bir dilde girilebilir ve Intune tarafından bunların çevirisi yapılmaz. İşiniz bittiğinde **Oluştur**’a tıklayın.
    - **Kategori düzenle** - Listedeki herhangi bir kategori için, '**...**' düğmesini seçin. **Özellikler** dikey penceresinde, kategori için yeni bir ad girebilir veya kategoriyi silebilirsiniz.


## <a name="apps-added-automatically-by-intune"></a>Intune tarafından otomatik olarak eklenen uygulamalar

Eskiden Intune’da hızlıca atayabileceğiniz birkaç yerleşik uygulama vardı. Geri bildirimlerinize dayanarak bu listeyi kaldırdık, artık yerleşik uygulamaları görmeyeceksiniz.
Ancak herhangi bir yerleşik uygulamayı önceden atadıysanız bu uygulamalar, uygulama listesinde görünmeye devam edecektir. Bu cihazları gerektiği gibi atamaya devam edebilirsiniz.
Sonraki bir sürümde, Azure portalında yerleşik uygulama seçme ve atama için daha kolay bir yöntem eklemeyi planlıyoruz.

## <a name="next-steps"></a>Sonraki adımlar

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
- [ Windows 10 için Office 365 uygulamaları](apps-add-office365.md)

