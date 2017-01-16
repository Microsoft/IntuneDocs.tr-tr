---
title: Yenilikler | Microsoft Docs
description: "Bu ayki ve geçmişteki Microsoft Intune sunumlarındaki yenilikleri öğrenin"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 12/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1d9ebc7fd727b80091625ed5256ae634323a9257
ms.openlocfilehash: f7e71d20923e113b533668a7b5aef688de196182


---
# <a name="whats-new-in-microsoft-intune---december-2016"></a>Microsoft Intune'daki yenilikler - Aralık 2016
Microsoft Intune’un bu sürümündeki yenilikleri öğrenin. Planlama yapmanız gereken yaklaşan değişiklikler hakkında ve geçmiş sunumlar hakkında bilgiler de alabilirsiniz.

> [!Note]
> Bu özelliklerin tümü, sonunda karma müşteri dağıtımlarında (Intune ile Configuration Manager) desteklenecektir. Yeni karma özellikler hakkında daha fazla bilgi için, [Karma Yenilikler sayfamızı](https://docs.microsoft.com/en-us/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) gözden geçirin.

## <a name="public-preview-of-the-new-intune-admin-experience-on-azure--736542--"></a>Azure’daki yeni Intune yönetici deneyiminin genel önizlemesi<!--736542-->
2017 takvim yılının başlarında tam yönetici deneyimimizi Azure’a geçireceğiz. Bu sayede Grafik API’leri kullanılarak genişletilebilen modern bir hizmet platformunda çekirdek EMS iş akışlarının güçlü ve tümleşik yönetimi mümkün olacaktır. Tüm Intune kiracıları için bu portalın genel kullanılabilirliğinin yanı sıra, kiracı seçmek için bu yeni yönetici deneyiminin önizlemesini bu ay içinde kullanıma sunmaya başlayacağımızı duyurmak isteriz.

Azure portalındaki yönetici deneyimi, duyurulan yeni gruplandırma ve hedefleme işlevselliğini kullanır; mevcut kiracınız yeni gruplandırma deneyimine geçirildiğinde, siz de kiracınıza yönelik yeni yönetici deneyimini önizlemek üzere geçirilirsiniz. Bu sırada, Azure portalında Microsoft Intune hakkında bilgilere [yeni belgelerimizden](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune) ulaşabilirsiniz.

Kiracınızın geçişinin zaman çizelgesi hakkında sorunuz varsa, geçiş ekibimize şuradan ulaşabilirsiniz: [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>Azure portalının genel önizlemesinde telekom gider yönetimi tümleştirmesi<!--747605-->
Artık Azure portalında üçüncü taraf telekom gider yönetimi (TEM) hizmetleri ile tümleştirme önizlemesine başlıyoruz. Yurt içi verilerin ve dolaşım verilerinin kullanımına yönelik sınırlamalarını zorunlu olarak uygulamak için Intune'u kullanabilirsiniz. Bu tümleştirmelere [Saaswedo](http://www.saaswedo.com) ile başlıyoruz. Deneme kiracınızda bu özelliği etkinleştirmek için lütfen [Microsoft desteğe başvurun](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

## <a name="new-capabilities"></a>Yeni Özellikler

### <a name="multi-factor-authentication-across-all-platforms---747590--"></a>Tüm platformlar arasında çok faktörlü kimlik doğrulaması <!--747590-->
Belirli bir kullanıcı grubu Azure Active Directory’de Microsoft Intune Kaydı uygulamasında MFA’yı yapılandırarak Azure Yönetim Portalı’ndan bir iOS, Android, Windows 8.1+ veya Windows Phone 8.1+ cihazını kaydettiklerinde, bu kullanıcılara çok faktörlü kimlik doğrulaması (MFA) kullanma zorunluluğu getirebilirsiniz.

### <a name="ability-to-restrict-mobile-device-enrollment--747596--"></a>Mobil cihaz kaydını kısıtlama özelliği<!--747596-->
Intune, katılmasına izin verilecek mobil cihaz platformlarını denetleyen yeni kayıt kısıtlamaları ekliyor. Intune, mobil cihaz platformlarını iOS, macOS, Android, Windows ve Windows Mobile şeklinde ayırıyor.
* Mobil cihaz kaydının kısıtlanması, bilgisayar istemcisi kaydını etkilemez.
* Yalnızca iOS için kişisel cihazların kaydedilmesini engelleyen ek seçenek vardır.

Intune, BT yöneticileri [bu makalede](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices) anlatılan şekilde kuruluş cihazı olarak işaretlemediği sürece tüm yeni cihazları kişisel cihaz olarak işaretler.


## <a name="notices"></a>Bildirimler

### <a name="multi-factor-authentication-on-enrollment-moving-to-the-azure-portal---vso-750545--"></a>Kayıt sırasında Multi-Factor Authentication, Azure portalına taşınıyor <!--VSO 750545-->
Daha önce yöneticiler Intune kaydı sırasında MFA ayarlamak için Intune konsoluna veya Configuration Manager (Ekim 2016'dan önceki sürümler) konsoluna gitmek durumundaydı. Bu güncelleştirilmiş özellik sayesinde, artık [Microsoft Azure portalında](https://manage.windowsazure.com) Intune kimlik bilgilerinizi kullanarak oturum açar ve MFA ayarlarını Azure AD ile yapılandırırsınız. Bunun hakkında daha fazla bilgi için [burayı](https://aka.ms/mfa_ad) okuyun.

### <a name="company-portal-app-for-android-now-available-in-china--vso-658093--"></a>Android için Şirket Portalı uygulaması artık Çin'de kullanılabilir <!--VSO 658093-->
Android için Şirket Portalı uygulamasını karşıdan yüklenebilir olarak Çin’de yayımlıyoruz. Çin’de Google Play Mağazası olmaması nedeniyle, Android cihazlarının uygulamaları Çin’deki uygulama mağazalarından edinmeleri gerekir. Android için Şirket Portalı uygulaması aşağıdaki mağazalardan yüklenebilir:
* [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
* [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
* [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
* [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)
* [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)

Android için Şirket Portalı uygulaması Microsoft Intune hizmetiyle iletişim kurmak için Google Play Hizmetleri’ni kullanır. Google Play Hizmetleri henüz Çin'de kullanılamadığından, aşağıdaki görevlerin tamamlanması 8 saate kadar sürebilir. 

|Intune Yönetici Konsolu| Android için Intune Şirket Portalı uygulaması |Intune Şirket Portalı Web Sitesi|   
|---|---|---|
|Tam temizleme| Uzak bir cihazı kaldırma| Cihaz kaldırma (yerel ve uzak)|
|Seçmeli temizleme| Cihaz sıfırlama| Cihaz sıfırlama|
|Yeni veya güncelleştirilmiş uygulamaların dağıtımı| Kullanılabilir iş kolu uygulamalarını yükleme| Cihaz geçiş kodu sıfırlama|
|Uzaktan kilitleme|||
|Geçiş kodu sıfırlama|||

## <a name="deprecations"></a>Kullanım dışı bırakılanlar

### <a name="firefox-to-no-longer-support-silverlight--vso-tba--"></a>Firefox artık Silverlight desteklemiyor<!--VSO TBA-->
Mozilla Mart 2017’den itibaren [Firefox tarayıcısı](https://www.mozilla.org/firefox) sürüm 52’de Silverlight desteğini kaldırıyor. Sonuç olarak, 51 üzeri Firefox sürümleri kullanarak mevcut Intune konsolunda oturum açmanız artık mümkün olmayacaktır. Yönetici konsoluna erişmek için Internet Explorer 10 veya 11 ya da [Sürüm 52'den önceki bir Firefox sürümü](https://ftp.mozilla.org/pub/firefox/releases/) kullanmanızı öneririz. Intune'un Azure portalına geçişi, Silverlight bağımlılığı olmadan bir dizi [modern tarayıcı](https://docs.microsoft.com/en-us/azure/azure-preview-portal-supported-browsers-devices) desteğine olanak sağlayacaktır.

### <a name="removal-of-exchange-online-mobile-inbox-policies---770687--"></a>Exchange Online mobil gelen kutusu ilkelerini kaldırma <!--770687-->
Aralık’tan itibaren yöneticilerin artık Intune konsolu içinde Exchange Online (EAS) mobil gelen kutusu ilkelerini görüntülemesi veya yapılandırması mümkün olmayacaktır. Bu değişiklik, Aralık ve Ocak boyunca tüm Intune kiracılarına gönderilecektir. Tüm mevcut ilkeler yapılandırıldığı gibi kalır; yeni ilkeler yapılandırmak için Exchange Yönetim Kabuğu'nu kullanın. Daha fazla bilgi için [buraya](https://technet.microsoft.com/en-us/library/bb123783%28v=exchg.150%29.aspx) göz atın.

### <a name="intune-av-player-image-viewer-and-pdf-viewer-apps-are-no-longer-supported-on-android---747553--"></a>Intune AV Oynatıcı, Resim Görüntüleyici ve PDF Görüntüleyici uygulamaları artık Android’de desteklenmiyor <!--747553-->
2016 Aralık ortasından itibaren, kullanıcılar Intune AV Oynatıcı, Resim Görüntüleyici ve PDF Görüntüleyici uygulamalarını kullanamayacaktır. Bu uygulamaların yerini Azure Information Protection uygulaması almıştır. Azure Information Protection hakkında daha fazla bilgiyi [burada](https://docs.microsoft.com/information-protection/rms-client/mobile-app-faq) bulabilirsiniz.

### <a name="see-also"></a>Ayrıca bkz.
* [Microsoft Intune Blogu](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Cloud Platform yol haritası](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Yenilikler arşivi](whats-new-archive.md)



<!--HONumber=Dec16_HO4-->


