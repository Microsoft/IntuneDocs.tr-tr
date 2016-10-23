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
ms.sourcegitcommit: 627914b2ac877c1b5ff5bc95f7f2098ab8988250
ms.openlocfilehash: 98e712fb852c89c1d092b87482f30ada33010a33


---


# Android kullanıcılarınız uygulamalarını nasıl alır
Microsoft Intune aracılığıyla dağıttığınız uygulamaları Android son kullanıcılarınızın nasıl ve nereden alacağını anlamak için bu bilgileri kullanın. Bilgiler cihaz türüne göre değişebilir (yerel Android cihazları veya Samsung Knox cihazları).

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

**Yönetilen uygulamalar** - İlkeler aracılığıyla yönetilebilen uygulamalardır. Intune tarafından “sarmalanmış" veya Intune Mobil Uygulama Yönetimi (MAM) Yazılım Geliştirme Seti (SDK) ile oluşturulmuş uygulamalardır. Bu uygulamalar Intune tarafından yönetilebilir ve uygulama ilkeleri uygulanabilir.

**Yönetilmeyen uygulamalar** - İlkeler aracılığıyla yönetilemeyen uygulamalardır. Intune tarafından sarmalanmamış veya Intune MAM SDK’sini içermeyen uygulamalardır. Uygulama ilkeleri bu uygulamalara uygulanamaz.

### Ayrıca bkz.
[Microsoft Intune’la uygulamaları ekleme](/intune/deploy-use/add-apps)

[iOS kullanıcılarınız uygulamalarını nasıl alır](how-your-ios-users-get-their-apps.md)

[Windows kullanıcılarınız uygulamalarını nasıl alır](how-your-windows-users-get-their-apps.md)



<!--HONumber=Oct16_HO2-->


