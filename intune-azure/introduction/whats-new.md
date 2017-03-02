---
title: "Microsoft Intune Önizlemesindeki yenilikler | Intune Azure önizlemesi | Microsoft Docs"
description: "Intune Azure önizlemesindeki yenilikleri keşfedin"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/15/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9852fdb9d1bfeede4931f0ead2fa0898dfcacb0b
ms.openlocfilehash: a05c7464b3f2fbca467d44218904671529320dda
ms.lasthandoff: 02/15/2017

---

# <a name="whats-new-in-the-microsoft-intune-preview"></a>Microsoft Intune önizlemesindeki yenilikler

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Genel önizleme süreci ilerler ve giderek daha fazla özellik eklenirken, bunlar konusunda size burada bilgi sağlayacağız.

## <a name="february-2017"></a>Şubat 2017

### <a name="ability-to-restrict-mobile-device-enrollment---747600-795782--"></a>Mobil cihaz kaydını kısıtlama özelliği <!--747600, 795782-->
Intune, katılmasına izin verilecek mobil cihaz platformlarını denetleyen yeni kayıt kısıtlamaları ekliyor. Intune, mobil cihaz platformlarını iOS, macOS, Android, Windows ve Windows Mobile şeklinde ayırıyor.

* Mobil cihaz kaydının kısıtlanması, bilgisayar istemcisi kaydını etkilemez.  
* Yalnızca iOS ve Android için kişisel cihazların kaydedilmesini engelleyen ek seçenek vardır.

Intune, BT yöneticileri [bu makalede](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices) anlatılan şekilde kuruluş cihazı olarak işaretlemediği sürece tüm yeni cihazları kişisel cihaz olarak işaretler.

### <a name="view-all-actions-on-managed-devices---677150--"></a>Yönetilen cihazlardaki tüm eylemleri görüntüleme <!--677150-->
Yeni __Cihaz Eylemleri__ raporu cihazları fabrika ayarlarına sıfırlama gibi uzaktan gerçekleştirilen eylemleri kimin yaptığını ve ilgili eylemin durumunu göstermektedir. Bkz. [Cihaz yönetimi nedir?](https://docs.microsoft.com/intune-azure/manage-devices/what-is)

### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Yönetilmeyen cihazlar atanmış uygulamalara erişebilir <!--664691-->
Şirket Portalı web sitesinde yapılan tasarım değişikliklerinin bir parçası olarak iOS ve Android kullanıcılar yönetilmeyen cihazlarında kendilerine "kayıtsız kullanılabilir" olarak atanmış uygulamaları yükleyebilecek. Kullanıcılar Intune kimlik bilgilerini kullanarak Şirket Portalı web sitesine girebilecek ve kendilerine atanan uygulamaların listesini görebilecek. "Kayıtsız kullanılabilir" uygulamaların uygulama paketleri Şirket Portalı web sitesinden indirilebilir. Yükleme için kayıt gerektiren uygulamalar bu değişikten etkilenmeyecek ve bu uygulamaları yüklemek isteyen kullanıcılardan cihazlarını kaydetmeleri istenecektir.

### <a name="custom-app-categories---748805--"></a>Özel uygulama kategorileri <!--748805-->
Artık Intune’a eklediğiniz uygulamalar için kategoriler oluşturabilir, düzenleyebilir ve atayabilirsiniz. Şu anda kategoriler yalnızca İngilizce olarak belirtilebilir.
Bkz. [Intune'a uygulama ekleme](/intune-azure/manage-apps/add-apps).

### <a name="display-device-categories---814654--"></a>Cihaz kategorilerini görüntüleme <!--814654-->
Artık cihaz kategorisini cihaz listesinde ayrı bir sütunda görüntüleyebilirsiniz. Kategoriyi ayrıca cihaz özellikleri dikey penceresinin özellikler bölümünden de düzenleyebilirsiniz. Bkz. [Intune'a uygulama ekleme](/intune-azure/manage-apps/add-apps). 

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

