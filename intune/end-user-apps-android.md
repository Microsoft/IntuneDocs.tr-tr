---
title: "Android kullanıcılarınız uygulamalarını nasıl alır"
description: "Android uygulamalarını son kullanıcılara sağlama yöntemleri"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 08/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33d1684-b1b5-44f7-9aac-c6d5186a5d7c
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0e1906de7e735174d660bb8508cab49196ff0aef
ms.sourcegitcommit: 0b164f806165d312acfc88815a60e325e3d02672
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/21/2017
---
# <a name="how-your-android-users-get-their-apps"></a>Android kullanıcılarınız uygulamalarını nasıl alır

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Microsoft Intune aracılığıyla dağıttığınız uygulamaları Android son kullanıcılarınızın nasıl ve nereden alacağını anlamak için bu bilgileri kullanın. Bilgiler cihaz türüne göre değişebilir (yerel Android cihazlar veya Samsung Knox Standard cihazlar).

## <a name="native-non-samsung-knox-standard-android-devices"></a>Yerel (Samsung Knox Standard harici) Android cihazlar

| Uygulama türü | İş kolu (LOB) uygulamaları | Play Store uygulamaları  |
| ------------- |-------------| -----|
| Kullanılabilir uygulamalar      | Kullanıcılar Şirket Portalı’nda **yükle**’ye dokunur. Bir bildirim görüntülenir ve kullanıcılar buna dokunarak yüklemeyi başlatır. Yükleme başarılı olduktan sonra, bildirim görüntüden kaldırılır. | Kullanıcılar Şirket Portalı’nda uygulamaya dokunur ve Play Store’da uygulamanın sayfasına ulaşır; burada yüklemeyi başlatabilirler.|
| Gerekli uygulamalar      | Kullanıcılara bir bildirim gösterilir. Bu bildirimi kapatamazlar ve bu, uygulamayı yüklemeleri gerektiğini gösterir. Kullanıcılar yüklemeyi başlatmak için bildirime dokunur. Yükleme başarılı olduktan sonra, bildirim görüntüden kaldırılır.    | Kullanıcılara bir bildirim gösterilir. Bu bildirimi kapatamazlar ve bu, uygulamayı yüklemeleri gerektiğini gösterir. Kullanıcılar bildirime dokunur ve Play Store’da uygulamanın sayfasına ulaşır; burada yüklemeyi başlatabilirler. Yükleme başarılı olduktan sonra, bildirim görüntüden kaldırılır. |

[LOB uygulamalarını](lob-apps-android.md) yüklemek için son kullanıcılarınızın, bilinmeyen kaynaklardan yüklemeye izin vermesi gerekir. Bunlar genellikle iki farklı yerde bulunur:

* **Android 7.1.2 ve altı sürümler**: **Ayarlar** > **Güvenlik** > **Bilinmeyen kaynaklar**
* **Android 8.0 ve üzeri sürümler**: **Ayarlar** > **Uygulamalar ve bildirimler** > **Özel uygulama erişimi** > **Bilinmeyen uygulama yükleme** > **Şirket Portalı** > **Bu kaynağa izin ver**

Bu durumda Şirket Portalı uygulaması, son kullanıcıya bilgi verip onu doğrudan uygun ayara yönlendirecektir. 


## <a name="samsung-knox-standard-android-devices"></a>Samsung Knox Standard Android cihazlar

| Uygulama türü | İş kolu (LOB) uygulamaları | Play Store uygulamaları  |
| ------------- |-------------| -----|
| Kullanılabilir uygulamalar      | Kullanıcılar Şirket Portalı’nda **yükle**’ye dokunur. Uygulama, başka kullanıcı müdahalesi olmadan yüklenir. | Kullanıcılar Şirket Portalı’nda uygulamaya dokunur ve Play Store’da uygulamanın sayfasına ulaşır; burada yüklemeyi başlatabilirler.|
| Gerekli uygulamalar      | Uygulama, hiçbir kullanıcı müdahalesi olmadan yüklenir.    | Kullanıcılara bir bildirim gösterilir. Bu bildirimi kapatamazlar ve bu, uygulamayı yüklemeleri gerektiğini gösterir. Kullanıcılar bildirime dokunur ve Play Store’da uygulamanın sayfasına ulaşır; burada yüklemeyi başlatabilirler. Yükleme başarılı olduktan sonra, bildirim görüntüden kaldırılır. |

Uygulamalar, aşağıda açıklandığı gibi yönetilebilir veya yönetilmeyebilir. Uygulamaları yönetilen uygulama yapma işlemi, tüm Android cihaz türlerinde aynıdır.

**Yönetilen uygulamalar** - İlkeler aracılığıyla yönetilebilen uygulamalardır. Intune tarafından “sarmalanmış" veya Intune Mobil Uygulama Yönetimi (MAM) Yazılım Geliştirme Seti (SDK) ile oluşturulmuş uygulamalardır. Bu uygulamalar Intune tarafından yönetilebilir ve uygulama ilkeleri uygulanabilir.

**Yönetilmeyen uygulamalar** - İlkeler aracılığıyla yönetilemeyen uygulamalardır. Intune tarafından sarmalanmamış veya Intune MAM SDK’sini içermeyen uygulamalardır. Uygulama ilkeleri bu uygulamalara uygulanamaz.

### <a name="see-also"></a>Ayrıca bkz.
[Microsoft Intune’la uygulama ekleme](apps-add.md)

[iOS kullanıcılarınız uygulamalarını nasıl alır](end-user-apps-ios.md)

[Windows kullanıcılarınız uygulamalarını nasıl alır](end-user-apps-windows.md)
