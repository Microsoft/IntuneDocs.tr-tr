---
title: Microsoft Intune’a bir Windows Phone iş kolu uygulaması ekleme
titlesuffix: ''
description: Microsoft Intune kullanarak bir Windows Phone iş kolu (LOB) uygulaması eklemeyi öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/11/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a097b7b2-d01d-454b-954c-da4f3cd0ae86
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 828ad7b42338e789c11c1f68b2b8b7daf0c72547
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57397260"
---
# <a name="add-a-windows-phone-line-of-business-app-to-microsoft-intune"></a>Microsoft Intune’a bir Windows Phone iş kolu uygulaması ekleme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Windows Phone iş kolu (LOB) uygulamalarını Microsoft Intune’a eklemek için bu makaledeki bilgileri kullanın. LOB uygulamaları, bir uygulama yükleme dosyasından Intune’a eklediğiniz uygulamalardır. Bu tür bir uygulama genellikle şirket içinde yazılmıştır. Intune, LOB uygulamasını kullanıcının cihazına yükler. 

## <a name="step-1-specify-the-software-setup-file"></a>1. adım: Yazılım Kurulum dosyasını belirtme

1. [Azure Portal](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümündedir.
3. **Intune** bölmesinde **İstemci uygulamaları**’nı seçin.
4. **İstemci uygulamaları** iş yükünde **Yönet** > **Uygulamalar**’ı seçin.
5. Uygulama listesinin üst kısmında **Ekle**’yi seçin.
6. **Uygulama ekle** bölmesinde **İş kolu uygulaması**’nı seçin.

## <a name="step-2-configure-the-app-package-file"></a>2. adım: Uygulama paketi dosyasını yapılandırma

1. **Uygulama ekle** bölmesinde **Uygulama paketi**’ni seçin.
2. **Uygulama paket dosyası** bölmesinde gözat düğmesini seçin. Daha sonra **.xap** uzantısına sahip bir Windows Phone yükleme dosyası seçin.
3. İşiniz bittiğinde **Tamam**’a tıklayın.


## <a name="step-3-configure-app-information"></a>3. adım: Uygulama bilgilerini yapılandırma

1. **Uygulama ekle** bölmesinde **Uygulama bilgileri**’ni seçin.
2. **Uygulama bilgileri** bölmesinde uygulama bilgilerini yapılandırın. Seçtiğiniz uygulamaya bağlı olarak bu bölmedeki değerlerden bazıları otomatik olarak doldurulabilir.
    - **Ad**: Şirket portalı'nda göründüğü gibi bir uygulama adı girin. Kullandığınız tüm uygulama adlarının benzersiz olduğundan emin olun. Aynı uygulama adı iki kez kullanılmışsa uygulamalardan yalnızca biri Şirket Portalı’nda kullanıcılara görüntülenir.
    - **Açıklama**: Uygulama için bir açıklama girin. Açıklama, Şirket Portalı’nda görünür.
    - **Yayımcı**: Uygulama yayımcısının adını girin.
    - **Kategori**: Bir veya daha fazla yerleşik uygulama kategorilerinden birini seçin veya oluşturduğunuz bir kategoriyi seçin. Kategoriler, kullanıcıların Şirket Portalı’na göz atarken uygulamayı daha kolay bulabilmesini sağlar.
    - **Bunu şirket Portalı'nda öne çıkan uygulama olarak görüntüle**: Kullanıcılar uygulamalara göz attığında, uygulamayı şirket portalının ana sayfasında önce çıkacak şekilde görüntüleyin.
    - **Bilgi URL'si**: İsteğe bağlı olarak, bu uygulama hakkında bilgi içeren bir web sitesinin URL’sini girin. URL, Şirket Portalı’nda görünür.
    - **Gizlilik URL'si**: İsteğe bağlı olarak, bu uygulamayla ilgili gizlilik bilgilerini içeren bir web sitesinin URL’sini girin. URL, Şirket Portalı’nda görünür.
    - **Geliştirici**: İsteğe bağlı olarak, uygulama geliştiricisinin adını girin.
    - **Sahibi**: İsteğe bağlı olarak, bu uygulamanın sahibi için bir ad girin. Örneğin **İK departmanı**.
    - **Notları**: Bu uygulamayla ilişkilendirmek istediğiniz notları girin.
    - **Logo**: Uygulamayla ilişkilendirilen bir simgeyi karşıya yükleyin. Bu simge, kullanıcılar Şirket Portalı’na göz atarken uygulamayla birlikte görüntülenir.
3. İşiniz bittiğinde **Tamam**’a tıklayın.

## <a name="step-4-finish-up"></a>4. adım: Bitirme

1. **Uygulama ekle** bölmesinde, bilgileri doğru yapılandırdığınızı onaylayın.
2. Uygulamayı Intune'a yüklemek için **Ekle**’yi seçin.

## <a name="next-steps"></a>Sonraki adımlar

- Oluşturduğunuz uygulama, uygulamalar listesinde görünür. Artık seçtiğiniz gruplara bu uygulamayı atayabilirsiniz. Yardım için bkz. [Uygulamaları gruplara atama](apps-deploy.md).

- Uygulamanızın özelliklerini ve atamasını izleme yolları hakkında daha fazla bilgi edinin. [Uygulama bilgilerini ve atamaları izleme](apps-monitor.md) makalesine bakın.

- Intune’da uygulamanızın bağlamı hakkında daha fazla bilgi edinin. [Cihaz ve uygulama yaşam döngülerine genel bakış](introduction-device-app-lifecycles.md) makalesine bakın.
