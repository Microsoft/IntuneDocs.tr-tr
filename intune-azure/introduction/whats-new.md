---
title: "Microsoft Intune Önizlemesindeki yenilikler | Intune Azure önizlemesi | Microsoft Docs"
description: "Intune Azure önizlemesi: Intune Azure önizlemesindeki yenilikleri keşfedin"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/02/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e405363f9d0a89b1589b01d18ee8d2861b07ec60
ms.openlocfilehash: 70007f5501fba37964a0a54807c0e0f565510a74


---

# <a name="whats-new-in-the-microsoft-intune-preview"></a>Microsoft Intune önizlemesindeki yenilikler


[!INCLUDE[azure_preview](../includes/azure_preview.md)]


Genel önizleme süreci ilerler ve giderek daha fazla özellik eklenirken, bunlar konusunda size burada bilgi sağlayacağız.

<!--## February 2017-->

<!--### Custom app categories <!--748805
You can now create, edit, and assign categories for apps you add to Intune. Currently, categories can only be specified in English.
See [How to add an app to Intune](/intune-azure/manage-apps/add-apps).-->

<!--### Display device categories <!--814654
You can now view the device category as a column in the device list. You can also edit the category from the properties section of the device properties blade.-->

## <a name="january-2017"></a>Ocak 2017

### <a name="assign-line-of-business-apps-whether-or-not-devices-are-enrolled---748823--"></a>Cihazlar kayıtlı olsa da olmasa da iş kolu uygulamaları atayın <!--748823-->
Artık, cihazları Intune’a kayıtlı olsun ya da olmasın, kullanıcılara mağazadan iş kolu uygulamaları atayabilirsiniz. Kullanıcıların cihazları Intune’a kayıtlı değilse yüklemek için Şirket Portalı uygulaması yerine Şirket Portalı web sitesine gitmeleri gerekir. Bkz. [Uygulama yönetimi nedir](/intune-azure/manage-apps/what-is-app-management).

### <a name="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them"></a>iOS cihazlarının etkin olmaması veya yönetim konsolunun cihazlarla iletişim kuramaması sorununu çözme
Kullanıcıların cihazları Intune ile iletişimi kaybettiğinde, şirket kaynaklarına yeniden erişmeleri için kullanıcılara yeni sorun giderme adımları verebilirsiniz. Bkz. [Cihazlar etkin değil veya yönetim konsolu cihazlarla iletişim kuramıyor](/intune-azure/enroll-devices/troubleshoot-device-enrollment#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).

## <a name="december-2016-initial-release"></a>Aralık 2016 (ilk sürüm)

### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>Azure portalının genel önizlemesinde telekom gider yönetimi tümleştirmesi<!--747605-->
Artık Azure portalında üçüncü taraf telekom gider yönetimi (TEM) hizmetleri ile tümleştirme önizlemesine başlıyoruz. Yurt içi verilerin ve dolaşım verilerinin kullanımına yönelik sınırlamalarını zorunlu olarak uygulamak için Intune'u kullanabilirsiniz. Bu tümleştirmelere [Saaswedo](http://www.saaswedo.com) ile başlıyoruz. Deneme kiracınızda bu özelliği etkinleştirmek için lütfen [Microsoft desteğe başvurun](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

- Uygulamaları mağazadan iOS, Android ve Windows cihazlarına dağıtma ve yönetme
- İş kolu uygulamalarını iOS, Android ve Windows cihazlarına dağıtma ve yönetme
- Toplu satın alınan uygulamaları iOS ve Windows cihazlarına dağıtma ve yönetme
- Android, iOS ve Windows cihazları için web uygulamalarını dağıtma ve yönetme
- iOS yönetilen uygulama yapılandırma profilleri
- Uygulama koruma ilkelerini yapılandırma ve iş kolu uygulamalarını Intune’a kayıtlı olmayan cihazlara dağıtma
- VPN profilleri, her uygulama için VPN, Wi-Fi, e-posta ve sertifika profilleri
- Uyumluluk ilkeleri
- Azure AD için koşullu erişim
- Şirket İçi Exchange için koşullu erişim
- Cihaz kaydı
- Rol tabanlı erişim denetimi

## <a name="deprecated-features-in-the-azure-portal"></a>Azure Portal’da kullanım dışı bırakılan özellikler

### <a name="support-for-row-by-row-review-of-hardware-identifiers"></a>Donanım tanımlayıcılarının satır satır gözden geçirme desteği
Azure Portal, donanım tanımlayıcılarının IMEI numaraları ve Apple seri numaraları için satır satır gözden geçirilmesini desteklemez. Klasik Intune konsolunda, virgülle ayrılmış değerler (.csv) dosyasından ayrıntıları içeri aktarabilir ve tek tek donanım tanımlayıcıları için mevcut ayrıntıların üzerine yazabilirsiniz. Azure Portal’da tüm donanım tanımlayıcıları için otomatik olarak ayrıntıların üzerine yazan veya mevcut tanımlayıcılar için yeni ayrıntıları yoksayan tek ve kullanımı kolay bir seçenek vardır.

#### <a name="how-this-affects-you"></a>Bu sizi nasıl etkiler?
Azure Portal’da, Uluslararası Mobil Ekipman Kimliği (IMEI) cihazlarından hangilerinin güncelleştirileceğine, satır satır karar veremezsiniz. Klasik Intune konsolu bu işlevselliği desteklemeye devam edecektir.

#### <a name="how-to-get-ready-for-this-change"></a>Bu değişikliğe hazır olmak için ne yapmalı?
Bu bilgileri size önceden sağlıyoruz; böylece, bu sizi etkiliyorsa destek yöneticilerinize bu değişikliği haber verebilirsiniz. Bu değişiklik, 2017’nin ilk yarısında gerçekleştirilmesi beklenen Azure Portal’a geçişle aynı zamana denk gelecektir.


### <a name="support-for-default-corporate-device-enrollment-profiles-in-apple-dep"></a>Apple DEP’te varsayılan Kurumsal Cihaz Kaydı profilleri için destek
Azure Portal, Apple Cihaz Kaydı Programı (DEP) cihaz seri numaraları için “varsayılan” Kurumsal Cihaz Kaydı profilini desteklemez. Klasik Intune konsolunda sağlanan bu işlevsellik, profillerin yanlışlıkla atanmasını önlemek için kullanımdan kaldırılmıştır. Azure Portal’da, bir Apple DEP hesabından eşitlenen seri numaralarına başlangıçta hiçbir Kurumsal Cihaz Kaydı profili atanmaz.

#### <a name="how-this-affects-you"></a>Bu sizi nasıl etkiler?
Azure Portal’da, tüm Apple cihazlarına genel olarak bir varsayılan profil ilkesi ayarlayamazsınız. Klasik Intune konsolu bu işlevselliği desteklemeye devam edecektir.

#### <a name="how-to-get-ready-for-this-change"></a>Bu değişikliğe hazır olmak için ne yapmalı?
Bu bilgileri size önceden sağlıyoruz; böylece, bu sizi etkiliyorsa destek yöneticilerinize bu değişikliği haber verebilirsiniz. Bu, 2017’nin ilk yarısında gerçekleştirilmesi beklenen Azure Portal’a geçişle aynı zamana denk gelecektir.



<!--HONumber=Feb17_HO1-->


