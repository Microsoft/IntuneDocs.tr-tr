---
title: "Microsoft Intune’daki uygulamaları kullanmaya başlarken"
titlesuffix: 
description: "İş gücünüzün işlerini yapabilmeleri için uygulamalar bulun ve bunları cihazlara ekleyin."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 3/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1542fc3-672e-47c1-a21f-82826a2f8ac4
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0185eebbe436da73e1920d7cd834f0897a143894
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2018
---
# <a name="get-started-with-adding-apps-in-microsoft-intune"></a>Microsoft Intune'da uygulama eklemeye başlama

Uygulamaları atama, izleme, yapılandırma veya korumadan önce bunları Intune’a eklemelisiniz. Intune, birçok farklı uygulama türünü destekler. Ayrıca, her bir uygulama türü için kullanılabilir seçenekler farklılık gösterir.

Intune kurumsal cihazlarınıza aşağıdaki uygulama türlerini eklemenize ve atamanıza izin verir:
- **Mağazadan uygulamalar** - App Store’da mevcut olan uygulamalarda ek mobil uygulama yönetimine gerek duyduğunuz cihazlar için.
- **Şirket içinde yazılan uygulamalar (iş kolu)** - Kullanıcılarınızın cihazlarına indirilen bir dosyayı karşıya yüklersiniz.
- **Yerleşik uygulamalar** - iOS ve Android cihazlara Office 365 uygulamaları gibi seçkin yönetilen uygulamaları atarsınız. 
- **Web’deki uygulamalar** - Intune, cihaz giriş ekranında web uygulaması için bir kısayol oluşturur.

## <a name="how-do-i-assign-a-public-store-app"></a>Bir ortak mağaza uygulamasını nasıl atarım?

Aşağıdaki örnek, Microsoft Intune'da bir iOS uygulamasının nasıl ekleneceğini adım adım açıklar.

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** dikey penceresinde **Mobil uygulamalar**’ı seçin.
4. **Mobil uygulamalar** iş yükündeki **Yönet** grubu altında **Uygulamalar**’ı seçin.
5. **Uygulamalar** bölmesinin sağ tarafındaki **Ekle**’yi seçin.
6. **Uygulama türü** listesinde kullanılabilir **Mağaza uygulaması** türleri altından **iOS**’u seçin.
6. **App Store’da Ara**’yı seçin.
7. **App Store’da Ara** dikey penceresinde önce App Store ülke yerel ayarını seçin.
8. Adı (veya adın bir kısmını) arama kutusuna yazın. Intune, mağazada arama yapar ve ilgili sonuçların listesini getirir.
9. Listeden istediğiniz uygulamayı seçin ve ardından **Seçin**’e tıklayın.
10. **Uygulama bilgileri**’ni seçerek uygulama bilgilerini yapılandırın.
11. (İsteğe bağlı) Bu uygulamayı düzenlemenize yardımcı olacak **Sahibi**, **Notlar**, **Geliştirici** gibi başka ayrıntılar ve bir **Gizlilik URL'si** (şirketinizin gizlilik ilkesi için) ekleyin.
12. **Bunu Şirket Portalı'nda öne çıkan bir uygulama olarak görüntüle** için **Evet**'i seçin. 
13. Tüm gerekli uygulama bilgilerini ekledikten sonra **Tamam**’a tıklayın.
14. **Uygulama ekle** yatay penceresinde **Ekle**’ye tıklayın. Bu, sizi uygulamanın **Genel Bakış** kısmına götürür. 

## <a name="next-steps"></a>Sonraki adımlar

Artık bir uygulamayı Intune’a eklediğinize göre, hangi çalışan gruplarının uygulamayı cihazlarına ekleyebileceklerini belirleyebilirsiniz.

- [Uygulamaları gruplara ekleme](apps-deploy.md)
- 
## <a name="learn-more"></a>Daha fazlasını öğrenin

* [Intune ile uygulama yönetimi nedir?](app-management.md)
* [Uygulama yaşam döngüsüne genel bakış](app-lifecycle.md)
* [Uygulama koruma ilkeleri nedir?](app-protection-policy.md)
