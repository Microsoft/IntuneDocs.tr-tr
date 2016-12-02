---
title: "Erken Sürüm | Microsoft Intune"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f287a0ad082fa20a2e84abbf8f5585117aae6f57
ms.openlocfilehash: e604b8809bd444d9069d449a6c691a8444296623


---

# <a name="the-early-edition-for-microsoft-intune---december"></a>Microsoft Intune için Erken Sürüm - Aralık

**Erken Sürüm** Microsoft Intune'un gelecek sürümlerinde kullanıma sunulacak yeni özelliklerin bir listesini sağlar. Bu bilgiler NDA kapsamında çok sınırlı bir temelde sağlanır ve değiştirilebilir. Burada listelenen özelliklerden bazılarının son tarihe yetişememe riski vardır ve gelecek sürüme ertelenebilir. Diğer özellikler, müşterinin kullanımına hazır olduğundan emin olmak için pilot (sürüyor) aşamasında test edilmektedir. Sorularınız veya kaygılarınız varsa lütfen Intune/PM arkadaşınıza ulaşın.

Bu sayfa düzenli aralıklarla güncelleştirilir. Ek güncelleştirmeleri daha sonra denetleyin.

Intune için aşağıdaki değişiklikler geliştirilme aşamasındadır. Bu özelliklerin tümü, sonunda karma müşteri dağıtımlarında (Intune ile Configuration Manager) desteklenecektir. Yeni karma özellikler hakkında daha fazla bilgi için, [Karma Yenilikler sayfamızı](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx) gözden geçirin.

<!--736542-->
## <a name="public-preview-of-the-new-intune-admin-experience-on-azure"></a>Azure’daki yeni Intune yönetici deneyiminin genel önizlemesi

2017 takvim yılının başlarında tam yönetici deneyimimizi Azure’a geçireceğiz. Bu sayede Grafik API’leri kullanılarak genişletilebilen modern bir hizmet platformunda çekirdek EMS iş akışlarının güçlü ve tümleşik yönetimi mümkün olacaktır.

Yeni deneme kiracıları, yeni yönetici deneyiminin genel önizlemesini bu ay Azure portalında görmeye başlayacaklar. Önizleme durumundayken, mevcut Intune konsolu ile gelen yetenekler ve eşlik, yinelemeli olarak sağlanır.

Azure portalındaki yönetici deneyimi, duyurulan yeni gruplandırma ve hedefleme işlevselliğini kullanır; mevcut kiracınız yeni gruplandırma deneyimine geçirildiğinde, siz de kiracınıza yönelik yeni yönetici deneyimini önizlemek üzere geçirilirsiniz. Bu sırada, kiracınız geçirilene kadar yeni işlevleri sınamak veya bunlara göz atmak isterseniz, yeni bir Intune deneme hesabına kaydolun veya yeni belgelere bakın.

Kiracınızın geçişinin zaman çizelgesi hakkında sorunuz varsa, geçiş ekibimize şuradan ulaşabilirsiniz: [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>Azure portalının genel önizlemesinde telekom gider yönetimi tümleştirmesi<!--747605-->
Artık Azure portalında üçüncü taraf telekom gider yönetimi (TEM) hizmetleri ile tümleştirme önizlemesine başlıyoruz. Yurt içi verilerin ve dolaşım verilerinin kullanımına yönelik sınırlamalarını zorunlu olarak uygulamak için Intune'u kullanabilirsiniz. Bu tümleştirmelere [Saaswedo](http://www.saaswedo.com) ile başlıyoruz.

## <a name="new-capabilities"></a>Yeni Özellikler

### <a name="multi-factor-authentication-across-all-platforms---747590--"></a>Tüm platformlar arasında çok faktörlü kimlik doğrulaması <!--747590-->
Belirli bir kullanıcı grubu Azure Active Directory’de Microsoft Intune Kaydı uygulamasında MFA’yı yapılandırarak Azure Yönetim Portalı’ndan bir iOS, Android, Windows 8.1+ veya Windows Phone 8.1+ cihazını kaydettiklerinde, bu kullanıcılara çok faktörlü kimlik doğrulaması (MFA) kullanma zorunluluğu getirebilirsiniz.

### <a name="conditional-access-for-mam-with-sharepoint-online---vso-679339--"></a>SharePoint Online ile MAM için koşullu erişim <!--VSO 679339-->
Intune mobil uygulama yönetimi (MAM) ilkeleri tarafından desteklenmeyen uygulamaların SharePoint Online’a erişmesini engelleyebilirsiniz.  Azure portalında Intune mobil uygulama yönetimini kullanarak başlayabilirsiniz. __Ayarlar__ dikey penceresinde SharePoint Online ile ilgili seçeneği içeren __Koşullu Erişim__ kısmını arayın. Bu özellik, hizmet sürümünün geri kalanından ayrı olarak sevk edilir.

## <a name="notices"></a>Bildirimler

### <a name="multi-factor-authentication-on-enrollment-moving-to-the-azure-portal---vso-750545--"></a>Kayıt sırasında Multi-Factor Authentication, Azure portalına taşınıyor <!--VSO 750545-->
Daha önce yöneticiler Intune kaydı sırasında MFA ayarlamak için Intune konsoluna veya Configuration Manager (1610'dan önceki sürümler) konsoluna gitmek durumundaydı. Bu güncelleştirilmiş özellik sayesinde, artık [Microsoft Azure portalında](https://manage.windowsazure.com) Intune kimlik bilgilerinizi kullanarak oturum açar ve MFA ayarlarını Azure AD ile yapılandırırsınız. Bunun hakkında daha fazla bilgi için [burayı](https://aka.ms/mfa_ad) okuyun.

### <a name="company-portal-app-for-android-now-available-in-china---vso-658093--"></a>Android için Şirket Portalı uygulaması artık Çin'de kullanılabilir <!--VSO 658093-->
Android için Şirket Portalı uygulamasını karşıdan yüklenebilir olarak Çin’de yayımlıyoruz. Çin’de Google Play Mağazası olmaması nedeniyle, Android cihazlarının uygulamaları Çin’deki uygulama mağazalarından edinmeleri gerekir. Android için Şirket Portalı uygulaması 360, Tencent, Xiaomi, Wandoujia ve Huawei üzerinden yüklenebilir. 

Android için Şirket Portalı uygulaması Microsoft Intune hizmetiyle iletişim kurmak için Google Play Hizmetleri’ni kullanır. Google Play Hizmetleri henüz Çin'de kullanılamadığından, aşağıdaki görevlerin tamamlanması 8 saate kadar sürebilir. 

|Intune Yönetici Konsolu| Android için Intune Şirket Portalı uygulaması |Intune Şirket Portalı Web Sitesi|   
|---|---|---|
|Tam temizleme| Uzak bir cihazı kaldırma| Cihaz kaldırma (yerel ve uzak)|
|Seçmeli temizleme| Cihaz sıfırlama| Cihaz sıfırlama|
|Yeni veya güncelleştirilmiş uygulamaların dağıtımı| Kullanılabilir iş kolu uygulamalarını yükleme| Cihaz geçiş kodu sıfırlama|
|Uzaktan kilitleme|||
|Geçiş kodu sıfırlama|||

## <a name="deprecations"></a>Kullanım dışı bırakılanlar

### <a name="removal-of-exchange-online-mobile-inbox-policies---770687--"></a>Exchange Online mobil gelen kutusu ilkelerini kaldırma <!--770687-->
Aralık’tan itibaren yöneticilerin artık Intune konsolu içinde Exchange Online (EAS) mobil gelen kutusu ilkelerini görüntülemesi veya yapılandırması mümkün olmayacaktır. Bu değişiklik, Aralık ve Ocak boyunca tüm Intune kiracılarına gönderilecektir. Tüm mevcut ilkeler yapılandırıldığı gibi kalır; yeni ilkeler yapılandırmak için Exchange Yönetim Kabuğu'nu kullanın. Daha fazla bilgi için [buraya](https://technet.microsoft.com/en-us/library/bb123783%28v=exchg.150%29.aspx) göz atın.

### <a name="intune-av-player-image-viewer-and-pdf-viewer-apps-are-no-longer-supported-on-android---747553--"></a>Intune AV Oynatıcı, Resim Görüntüleyici ve PDF Görüntüleyici uygulamaları artık Android’de desteklenmiyor <!--747553-->
2016 Aralık ortasından itibaren, kullanıcılar Intune AV Oynatıcı, Resim Görüntüleyici ve PDF Görüntüleyici uygulamalarını kullanamayacaktır. Bu uygulamaların yerini Azure Information Protection uygulaması almıştır. Azure Information Protection hakkında daha fazla bilgiyi [burada](https://docs.microsoft.com/information-protection/rms-client/mobile-app-faq) bulabilirsiniz.

### <a name="see-also"></a>Ayrıca bkz.
Son geliştirmelere ilişkin ayrıntılar için bkz. [Microsoft Intune’daki Yenilikler](whats-new-in-microsoft-intune.md).



<!--HONumber=Nov16_HO4-->


