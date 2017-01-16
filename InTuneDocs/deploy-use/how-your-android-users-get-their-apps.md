---
title: "Android kullanıcılarınız uygulamalarını nasıl alır | Microsoft Docs"
description: "Android uygulamalarını son kullanıcılara sağlama yöntemleri"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33d1684-b1b5-44f7-9aac-c6d5186a5d7c
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 370dd5d4a96253f0b7d208ef85659beeace18739


---


# <a name="how-your-android-users-get-their-apps"></a>Android kullanıcılarınız uygulamalarını nasıl alır

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune aracılığıyla dağıttığınız uygulamaları Android son kullanıcılarınızın nasıl ve nereden alacağını anlamak için bu bilgileri kullanın. Bilgiler cihaz türüne göre değişebilir (yerel Android cihazlar veya Samsung Knox Standard cihazlar).

## <a name="native-non-samsung-knox-standard-android-devices"></a>Yerel (Samsung Knox Standard harici) Android cihazlar

| Uygulama türü | İş kolu (LOB) uygulamaları | Play Store uygulamaları  |
| ------------- |-------------| -----|
| Kullanılabilir uygulamalar      | Kullanıcılar Şirket Portalı’nda **yükle**’ye dokunur. Bir bildirim görüntülenir ve kullanıcılar buna dokunarak yüklemeyi başlatır. Yükleme başarılı olduktan sonra, bildirim görüntüden kaldırılır. | Kullanıcılar Şirket Portalı’nda uygulamaya dokunur ve Play Store’da uygulamanın sayfasına ulaşır; burada yüklemeyi başlatabilirler.|
| Gerekli uygulamalar      | Kullanıcılara bir bildirim gösterilir. Bu bildirimi kapatamazlar ve bu, uygulamayı yüklemeleri gerektiğini gösterir. Kullanıcılar yüklemeyi başlatmak için bildirime dokunur. Yükleme başarılı olduktan sonra, bildirim görüntüden kaldırılır.    | Kullanıcılara bir bildirim gösterilir. Bu bildirimi kapatamazlar ve bu, uygulamayı yüklemeleri gerektiğini gösterir. Kullanıcılar bildirime dokunur ve Play Store’da uygulamanın sayfasına ulaşır; burada yüklemeyi başlatabilirler. Yükleme başarılı olduktan sonra, bildirim görüntüden kaldırılır. |

## <a name="samsung-knox-standard-android-devices"></a>Samsung Knox Standard Android cihazlar

| Uygulama türü | İş kolu (LOB) uygulamaları | Play Store uygulamaları  |
| ------------- |-------------| -----|
| Kullanılabilir uygulamalar      | Kullanıcılar Şirket Portalı’nda **yükle**’ye dokunur. Uygulama, başka kullanıcı müdahalesi olmadan yüklenir. | Kullanıcılar Şirket Portalı’nda uygulamaya dokunur ve Play Store’da uygulamanın sayfasına ulaşır; burada yüklemeyi başlatabilirler.|
| Gerekli uygulamalar      | Uygulama, hiçbir kullanıcı müdahalesi olmadan yüklenir.    | Kullanıcılara bir bildirim gösterilir. Bu bildirimi kapatamazlar ve bu, uygulamayı yüklemeleri gerektiğini gösterir. Kullanıcılar bildirime dokunur ve Play Store’da uygulamanın sayfasına ulaşır; burada yüklemeyi başlatabilirler. Yükleme başarılı olduktan sonra, bildirim görüntüden kaldırılır. |

Uygulamalar, aşağıda açıklandığı gibi yönetilebilir veya yönetilmeyebilir. Uygulamaları yönetilen uygulama yapma işlemi, tüm Android cihaz türlerinde aynıdır.

**Yönetilen uygulamalar** - İlkeler aracılığıyla yönetilebilen uygulamalardır. Intune tarafından “sarmalanmış" veya Intune Mobil Uygulama Yönetimi (MAM) Yazılım Geliştirme Seti (SDK) ile oluşturulmuş uygulamalardır. Bu uygulamalar Intune tarafından yönetilebilir ve uygulama ilkeleri uygulanabilir.

**Yönetilmeyen uygulamalar** - İlkeler aracılığıyla yönetilemeyen uygulamalardır. Intune tarafından sarmalanmamış veya Intune MAM SDK’sini içermeyen uygulamalardır. Uygulama ilkeleri bu uygulamalara uygulanamaz.

### <a name="see-also"></a>Ayrıca bkz.
[Microsoft Intune’la uygulama ekleme](/intune/deploy-use/add-apps)

[iOS kullanıcılarınız uygulamalarını nasıl alır](how-your-ios-users-get-their-apps.md)

[Windows kullanıcılarınız uygulamalarını nasıl alır](how-your-windows-users-get-their-apps.md)



<!--HONumber=Dec16_HO2-->


