---
title: "Microsoft Intune’a uygulamaları ekleme | Intune Azure önizlemesi | Microsoft Docs"
description: "Intune Azure önizlemesi: Bu yordamlar, uygulamalarınızı kullanıcılara ve cihazlara atanmaya hazır durumda Intune’a almanıza yardımcı olur. "
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1ded457-0ecf-4f9c-a2d2-857d57f8d30a
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 969ce8deae9142944f3481172277dc252baa5779
ms.openlocfilehash: a7838f57b2eb8bd36a875f7b5b001b12eafcbf8d

---

# <a name="how-to-add-an-app"></a>Uygulama ekleme 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Kullanıcılarınız için uygulamaları yönetmeden ve atamadan önce, bunları Intune’a eklemeniz gerekir. Intune, birbirinden farklı çok çeşitli uygulama türlerini destekler ve türlerin her biri için seçenekler farklı olabilir.

Intune şu uygulama türlerinin eklenmesini ve atanmasını destekler:

![Intune tarafından desteklenen uygulama türleri](./media/app-types.png)

Şu platformlar desteklenir. Her uygulama türünün nasıl eklendiği hakkında daha fazla bilgi için başlıklardan birine tıklayın.

- [Android iş kolu uygulamaları](/intune-azure/manage-apps/android-lob-app)
- [Android mağaza uygulamaları](/intune-azure/manage-apps/android-store-app)
- [iOS iş kolu uygulamaları](/intune-azure/manage-apps/ios-lob-app)
- [iOS Store uygulamaları](/intune-azure/manage-apps/ios-store-app)
- [Web uygulamaları (tüm platformlar için)](/intune-azure/manage-apps/web-app)
- [Windows Phone 8.1 mağaza uygulamaları](/intune-azure/manage-apps/windows-phone-8-1-store-app)
- [Windows Mağazası uygulamaları](/intune-azure/manage-apps/windows-store-app)

> [!NOTE]
> Bir mağazadan uygulama eklediğinizde ve dağıttığınızda, son kullanıcıların uygulamayı yükleyebilmesi için o mağazada bir hesapları olması gerekir.

## <a name="how-to-create-and-edit-categories-for-apps"></a>Uygulamalar için kategorileri oluşturma ve düzenleme 

Uygulama kategorileri, son kullanıcıların şirket portalında daha kolay bulabilmeleri için uygulamaları sıralamanıza yardımcı olabilir. Uygulamaya, **Geliştirici uygulamaları** veya **İletişim uygulamaları** gibi bir veya birden çok kategori atayabilirsiniz. Uygulamayı Intune’a eklediğinizde, size istediğiniz kategoriyi belirtme seçeneği sağlanır. Uygulama eklemek ve kategorileri atamak için, platforma özgü konu başlıklarını kullanın. Kendi kategorilerinizi oluşturmak ve düzenlemek için aşağıdaki yordamı kullanın: 

1. Azure Portal’da oturum açın. 
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin. 
3. **Intune** dikey penceresinde **Uygulamaları yönet**’i seçin. 
4. **Mobil uygulamalar** iş yükünde **Kurulum** > **Uygulama kategorileri**’ni seçin. 
5. **Uygulama kategorileri** dikey penceresinde geçerli kategorilerin listesi gösterilir. Aşağıdaki eylemlerden birini seçin: 
    - **Kategori oluştur** - **Kategori oluştur** dikey penceresinde yeni kategori için bir ad girin. Adlar tek bir dilde girilebilir ve Intune tarafından bunların çevirisi yapılmaz. İşiniz bittiğinde **Oluştur**’a tıklayın.
    - **Kategori düzenle** - Listedeki herhangi bir kategori için, '**...**' düğmesini seçin. **Özellikler** dikey penceresinde, kategori için yeni bir ad girebilir veya kategoriyi silebilirsiniz. --->






<!--HONumber=Feb17_HO1-->


