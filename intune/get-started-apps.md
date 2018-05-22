---
title: Microsoft Intune’daki uygulamaları kullanmaya başlarken
titlesuffix: ''
description: İş gücünüzün işlerini yapabilmeleri için uygulamalar bulun ve bunları cihazlara ekleyin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a1542fc3-672e-47c1-a21f-82826a2f8ac4
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5d99812c57596e10d0cdfa2c0f4504f8a6ac583c
ms.sourcegitcommit: 34e96e57af6b861ecdfea085acf3c44cff1f3d43
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="get-started-with-adding-apps-in-microsoft-intune"></a>Microsoft Intune'da uygulama eklemeye başlama

Uygulamaları atama, izleme, yapılandırma veya korumadan önce bunları Intune’a eklemelisiniz. Intune, birçok farklı uygulama türünü destekler. Ayrıca, her bir uygulama türü için kullanılabilir seçenekler farklılık gösterir.

Intune kurumsal cihazlarınıza aşağıdaki uygulama türlerini eklemenize ve atamanıza izin verir:
- **Mağazadan uygulamalar** - App Store’da mevcut olan uygulamalarda ek mobil uygulama yönetimine gerek duyduğunuz cihazlar için.
- **Şirket içinde yazılan uygulamalar (iş kolu)** - Kullanıcılarınızın cihazlarına indirilen bir dosyayı karşıya yüklersiniz.
- **Yerleşik uygulamalar** - iOS ve Android cihazlara Office 365 uygulamaları gibi seçkin yönetilen uygulamaları atarsınız.
- **Web’deki uygulamalar** - Intune, cihaz giriş ekranında web uygulaması için bir kısayol oluşturur.

## <a name="how-do-i-assign-a-public-store-app"></a>Bir ortak mağaza uygulamasını nasıl atarım?

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Mobil Uygulamalar**'ı, sonra **Uygulamalar**'ı seçin.
4. **Ekle**’yi ve ardından **Uygulama türü** olarak **iOS**’u seçin.
5. **Uygulama seçin**’i belirleyerek **App Store’da Ara** bölmesini görüntüleyin.
6. Metin kutusunda cihaza atayacak bir uygulama arayın. Uygulamayı seçin ve **Seç**'e tıklayın.
7. **Uygulama ekle** bölmesinde **Uygulama bilgileri**'ni seçin, sonra tüm uygulama bilgilerinin doldurulduğundan emin olun. Bu uygulamayı düzenlemenize yardımcı olacak **Sahibi**, **Notlar**, **Geliştirici** gibi isteğe bağlı başka ayrıntılar ve şirketinizin gizlilik ilkesi için bir **Gizlilik URL'si** ekleyebilirsiniz.
8. **Bunu Şirket Portalı'nda öne çıkan bir uygulama olarak görüntüle** için **Evet**'i seçtiğinizden emin olun, sonra **Tamam**'ı seçin.
9. **Uygulama ekle** bölmesinde **Ekle**'yi seçerek uygulamayı ekleyin. Bu eylem, sizi uygulamanın **Genel Bakış**'ına yönlendirir. **Atamalar**'ı seçin, sonra sınama grubunuza atamak için **Grup ekle**'ye tıklayın. Uygulamayı indirebilmek için **Kullanılabilir** yapın. Uygulama artık sınama cihazınızda **Öne Çıkan Uygulama** olarak görünür.


- [Uygulamaları gruplara ekleme](apps-deploy.md)

## <a name="learn-more"></a>Daha fazlasını öğrenin

* [Intune ile uygulama yönetimi nedir?](app-management.md)
* [Uygulama yaşam döngüsüne genel bakış](app-lifecycle.md)
* [Uygulama koruma ilkeleri nedir?](app-protection-policy.md)
