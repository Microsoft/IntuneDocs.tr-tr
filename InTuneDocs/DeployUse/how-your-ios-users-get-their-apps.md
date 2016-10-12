---
title: "iOS kullanıcılarınız uygulamalarını nasıl alır | Microsoft Intune"
description: "iOS uygulamalarını son kullanıcılara sağlama yöntemleri"
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 08/24/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e3135c1-df26-48c9-aa4c-cdab6168897a
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a3db9269bf4f93021d16d8ea23a2a13b87b43677
ms.openlocfilehash: 61c4cb00fba3352f6898ec41b6d07834da4ec63d


---


# iOS kullanıcılarınız uygulamalarını nasıl alır

Microsoft Intune aracılığıyla dağıttığınız uygulamaları son kullanıcılarınızın nasıl ve nereden alacağını anlamak için bu bilgileri kullanın.

**Gerekli uygulamalar** - Platforma bağlı olarak yönetici tarafından gerekli kılınan ve minimum kullanıcı katılımıyla cihaza yüklenen uygulamalar.

**Kullanılabilir uygulamalar** - Şirket Portalı uygulama listesinde sağlanan ve kullanıcıların isteğe bağlı olarak yüklemeyi seçebileceği uygulamalar.

**Yönetilen uygulamalar** - İlkeler aracılığıyla yönetilebilen ve Intune tarafından “sarmalanmış" veya Intune Mobil Uygulama Yönetimi (MAM) Yazılım Geliştirme Seti (SDK) ile oluşturulmuş uygulamalar. Bu uygulamalar Intune tarafından yönetilebilir ve uygulama ilkeleri uygulanabilir.

**Yönetilmeyen uygulamalar** - İlkeler aracılığıyla yönetilebilen ve Intune tarafından sarmalanmamış veya Intune MAM SDK’sini içermeyen uygulamalar. Uygulama ilkeleri bu uygulamalara uygulanamaz.

Apple kısıtlamaları, iş kolu ve yönetilen uygulama mağazası uygulamalarının Şirket Portalı uygulamasında listelenmesini yasaklar. Bu sorunu aşmak için, iOS için Şirket Portalı uygulamasındaki uygulama kutucukları, aşağıda açıklandığı gibi kullanıcıları tüm uygulamalarda farklı görünümle tek konuma, yani Şirket Portalı web sitesine yönlendirir:

- **Şirket Uygulamaları** kutucuğu daha önce [Şirket Portalı Web sitesinin](http://portal.manage.microsoft.com) TÜMÜ sekmesindeki tüm uygulamaların listesine yönlendirmekteydi ve bu şekilde çalışmaya devam edecektir. Kutucuk adı **Tüm Uygulamalar** olarak değişmiştir.

- **Diğer Uygulamalar** kutucuğu daha önce, Şirket Portalı uygulamasında bulunan ve Apple’ın Şirket Portalı uygulamasının göstermesine izin verdiği tüm uygulamaları listeleyen görünüme yönlendiriyordu. Kutucuk adı **Öne Çıkan Uygulamalar** olarak değişmiştir ve kutucuğa dokunan kullanıcıları Şirket Portalı web sitesinin ÖNE ÇIKANLAR sekmesine götürür.

-  **Kategoriler** kutucuğu daha önce Şirket Portalı uygulaması içinde bulunan ve uygulama kategorilerini listeleyen görünüme yönlendirmekteydi. Kutucuk adı değişmemiştir, ancak artık Şirket Portalı web sitesinin KATEGORİLER sekmesine yönlendirir.
Güncelleştirilmiş ekran görüntülerini [burada](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186) bulabilirsiniz.



###Ayrıca bkz.
[Android kullanıcılarınız uygulamalarını nasıl alır](how-your-android-users-get-their-apps.md)

[Windows kullanıcılarınız uygulamalarını nasıl alır](how-your-windows-users-get-their-apps.md)



<!--HONumber=Sep16_HO5-->


