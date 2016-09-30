---
title: "Android kullanıcılarınız uygulamalarını nasıl alır | Microsoft Intune"
description: "Android uygulamalarını son kullanıcılara sağlama yöntemleri"
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 7/7/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33d1684-b1b5-44f7-9aac-c6d5186a5d7c
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a3db9269bf4f93021d16d8ea23a2a13b87b43677
ms.openlocfilehash: d3d37b9bcf8cc5833b4e11185b49902e26a625dc


---


# Android kullanıcılarınız uygulamalarını nasıl alır
Microsoft Intune aracılığıyla dağıttığınız uygulamaları Android son kullanıcılarınızın nasıl ve nereden alacağını anlamak için bu bilgileri kullanın. Yerel Android cihazlarıyla Samsung Knox cihazlarına yönelik bilgiler farklı olabilir.

## Yerel (Samsung Knox olmayan) Android cihazları

| Uygulama türü | İş kolu (LOB) uygulamaları | Play Store uygulamaları  |
| ------------- |-------------| -----|
| Kullanılabilir uygulamalar      | Kullanıcılar Şirket Portalı’nda **yükle**’ye dokunur. Bir bildirim görüntülenir ve kullanıcılar buna dokunarak yüklemeyi başlatır. Yükleme başarılı olduktan sonra, bildirim görüntüden kaldırılır. | Kullanıcılar Şirket Portalı’nda uygulamaya dokunur ve Play Store’da uygulamanın sayfasına ulaşır; burada yüklemeyi başlatabilirler.|
| Gerekli uygulamalar      | Kullanıcılara bir bildirim gösterilir. Bu bildirimi kapatamazlar ve bu, uygulamayı yüklemeleri gerektiğini gösterir. Kullanıcılar yüklemeyi başlatmak için bildirime dokunur. Yükleme başarılı olduktan sonra, bildirim görüntüden kaldırılır.    | Kullanıcılara bir bildirim gösterilir. Bu bildirimi kapatamazlar ve bu, uygulamayı yüklemeleri gerektiğini gösterir. Kullanıcılar bildirime dokunur ve Play Store’da uygulamanın sayfasına ulaşır; burada yüklemeyi başlatabilirler. Yükleme başarılı olduktan sonra, bildirim görüntüden kaldırılır. |

## Samsung Knox Android cihazları

| Uygulama türü | İş kolu (LOB) uygulamaları | Play Store uygulamaları  |
| ------------- |-------------| -----|
| Kullanılabilir uygulamalar      | Kullanıcılar Şirket Portalı’nda **yükle**’ye dokunur. Uygulama, başka kullanıcı müdahalesi olmadan yüklenir. | Kullanıcılar Şirket Portalı’nda uygulamaya dokunur ve Play Store’da uygulamanın sayfasına ulaşır; burada yüklemeyi başlatabilirler.|
| Gerekli uygulamalar      | Uygulama, hiçbir kullanıcı müdahalesi olmadan yüklenir.    | Kullanıcılara bir bildirim gösterilir. Bu bildirimi kapatamazlar ve bu, uygulamayı yüklemeleri gerektiğini gösterir. Kullanıcılar bildirime dokunur ve Play Store’da uygulamanın sayfasına ulaşır; burada yüklemeyi başlatabilirler. Yükleme başarılı olduktan sonra, bildirim görüntüden kaldırılır. |

Uygulamalar, aşağıda açıklandığı gibi yönetilebilir veya yönetilmeyebilir. Uygulamaları yönetilen uygulama yapma işlemi, tüm Android cihaz türlerinde aynıdır.

**Yönetilen uygulamalar** - İlkeler aracılığıyla yönetilebilen ve Intune tarafından “sarmalanmış" veya Intune Mobil Uygulama Yönetimi (MAM) Yazılım Geliştirme Seti (SDK) ile oluşturulmuş uygulamalar. Bu uygulamalar Intune tarafından yönetilebilir ve uygulama ilkeleri uygulanabilir.

**Yönetilmeyen uygulamalar** - İlkeler aracılığıyla yönetilebilen ve Intune tarafından sarmalanmamış veya Intune MAM SDK’sini içermeyen uygulamalar. Uygulama ilkeleri bu uygulamalara uygulanamaz.

### Ayrıca bkz.
[Microsoft Intune’la uygulamaları ekleme](/intune/deploy-use/add-apps)

[iOS kullanıcılarınız uygulamalarını nasıl alır](how-your-ios-users-get-their-apps.md)

[Windows kullanıcılarınız uygulamalarını nasıl alır](how-your-windows-users-get-their-apps.md)



<!--HONumber=Sep16_HO5-->


