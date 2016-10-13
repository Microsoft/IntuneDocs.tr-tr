---
title: "Erken sürüm | Microsoft Intune"
description: 
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 10/05/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a5c4b0f15456a9f24c95954d669a17c63f96a459
ms.openlocfilehash: 273016d4fe114bbe60e9cebc06e89584c8f91f0b


---

# Microsoft Intune'da kullanıma sunulacak yeni özellikler - Ekim
**Erken Sürüm** Microsoft Intune'un gelecek sürümlerinde kullanıma sunulacak yeni özelliklerin bir listesini sağlar. Bu bilgiler NDA kapsamında çok sınırlı bir temelde sağlanır ve değiştirilebilir. Burada listelenen özelliklerden bazılarının son tarihe yetişememe riski vardır ve gelecek sürüme ertelenebilir. Diğer özellikler, müşterinin kullanımına hazır olduğundan emin olmak için pilot (sürüyor) aşamasında test edilmektedir. Sorularınız veya kaygılarınız varsa lütfen Intune/PM arkadaşınıza ulaşın.

Bu sayfa düzenli aralıklarla güncelleştirilir. Beklenen yeni güncelleştirmeler için yeniden gelip gözden geçirin.

Intune için aşağıdaki değişiklikler geliştirilme aşamasındadır. Bu özelliklerin tümü, sonunda karma müşteri dağıtımlarında (Intune ile Configuration Manager) desteklenecektir. Yeni karma özellikler hakkında daha fazla bilgi için, [Karma Yenilikler sayfamızı](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx) gözden geçirin.

### MAM ilkeleriyle yönetilen uygulamalardan yazdırmayı yönetme
Artık MAM ilkeleri olan uygulamalardan şirket verilerinin yazdırılmasını engelleyebilirsiniz. Bu ayar, [Azure portalından](..deployuse/create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) kullanılabilir ve gerek [iOS](..deployuse/ios-mam-policy-settings), gerekse [Android](..deployuse/android-mam-policy-settings) cihazlarında desteklenmektedir.
<!--TFS 1014328-->

### Windows 10 cihazları için Yeni Microsoft Intune Şirket Portalı
Microsoft, Windows 10 cihazları için yeni bir Microsoft Intune Şirket Portalı'nı piyasaya sürüyor. Yeni Windows 10 Evrensel biçiminden yararlanan bu uygulama, kullanıcıya uygulama içinden güncelleştirilmiş bir kullanıcı deneyimi ve kullanıcının bugün kullanmakta olduğu işlevselliğin tümünü olanaklı kılmaya devam ederken, ister bilgisayar ister Mobil tüm Windows 10 cihazlarında aynı deneyimi sunacak.

Yeni uygulama, kullanıcının Windows 10 cihazlarında çoklu oturum açma (SSO) ve sertifika tabanlı kimlik doğrulama gibi ek platform özelliklerinden yararlanmasını da sağlar. Uygulama, mevcut Windows 8.1 Şirket Portalı ve Windows Phone 8.1 Şirket Portalı için güncelleştirme olarak Windows Mağazası'ndan yüklenir.
<!--TFS 1016502-->

### Android for Work desteği

Intune artık [Android for Work programının](https://enterprise.google.com/android/partners/) bir parçası. Intune'a Android for Work özellikleri için desteği bu ay çıkarmaya başlayacağız.

[Android for Work için Intune desteği hakkında Microsoft'un duyurusunu okuyun](https://blogs.technet.microsoft.com/enterprisemobility/2016/09/12/microsoft-intune-support-for-android-for-work/).

<!---This month, some newly provisioned Intune tenants will start seeing the Android for Work features. We will announce later when existing tenants will begin to see this feature.--->
<!--TFS 1043303-->

### Android Samsung KNOX ile Intune uyumluluğu

Samsung Galaxy Ace telefonunun bazı modelleri, Intune tarafından Samsung KNOX cihazları olarak yönetilemiyor. Bu cihazları Intune’a kaydettiğinizde, artık standart Android cihazları olarak yönetilecek.
Etkilenen model numaraları:

* SM-G313HU
* SM-G313HY
* SM-G313M
* SM-G313MY
* SM-G313U

Sizin ve son kullanıcılarınızın başka bir işlem yapması gerekmez.
Daha fazla bilgi için [Samsung KNOX](https://www.samsungknox.com) web sitesini ziyaret edin.

<!--TFS 1173566 iX blurb provided by Barry; requires PM signoff

### Multi-factor authentication for Android and iOS enrollment

In addition to Windows 8.1 and later, administrators can now enable multi-factor authentication for Android and iOS devices in the Microsoft Intune Enrollment application. -->    

### Windows 8 için Şirket Portalı uygulaması kaldırılmıştır; Windows Phone 8 ve Windows RT platformları için destek kaldırılmaktadır
Microsoft Intune, Ekim 2016'dan başlayarak Windows 8 Şirket Portalı için desteği kaldıracaktır. Microsoft Intune, ayrıca Windows Phone 8 ve Windows RT platformları için desteği de kaldıracaktır. Bu nedenle bundan sonra herhangi bir Windows Phone 8 veya Windows RT cihazını kaydetmeniz veya güncelleştirmeniz mümkün olmayacaktır.

Daha önce kaydedilen Windows Phone 8, Windows RT ve Windows 8 cihazlarını yönetmeye devam edebilirsiniz. Windows 8 ve Windows Phone 8 cihazlarını Windows 8.1’e ve Windows Phone 8.1’e güncelleştirin ve bu cihazlara bir kesinti olmadan uygulama dağıtmaya devam etmek için ilgili Windows 8.1 ve Windows Phone 8.1 Şirket Portalı uygulamalarını kullanın.

Kasım 2016'dan itibaren Windows Phone 8 Şirket Portalı için desteği kaldıracağız.
<!--TFS 1255391-->

### Mobil uygulama yönetimi için koşullu destek
Yönetilmeyen mobil uygulamaların [Exchange Online](..deployuse/restrict-access-to-exchange-online-with-microsoft-intune.md)'a ve [SharePoint Online](..deployuse/restrict-access-to-sharepoint-online-with-microsoft-intune.md)'a erişimini engellemek için artık bir koşullu erişim ilkesi oluşturabilirsiniz. Üzerinde MAM etkin olmayan yerleşik posta istemcilerini ve uygulamalarını Intune Uygulama SDK'sı ile engelleyebilirsiniz.  Bu, bir koşullu erişim ilkesi oluşturularak ve Exchange Online'a ve SharePoint Online'a Azure portalı üzerinden erişmesini istediğiniz uygulamalar belirtilerek yapılabilir.
<!--TFS 1317673-->

<!--TFS 1318014; awaiting approval in notes as to whether to proceed

### "Default" policy is deprecated

To minimize unintentionally assigned profiles, Intune is removing support for the "default" Corporate Device Enrollment profile for Apple Device Enrollment Program (DEP) device serial numbers in the new Azure console. Serial numbers synchronized from an Apple DEP account will initially have no Corporate Device Enrollment profile assigned.  A profile must be assigned manually after synchronization. This change will apply to the new console only. Until the existing Admin console is retired, no change will take place.
-->

<!--TFS 1318023; awaiting approval in notes as to whether to proceed

### Deprecation of row-by-row iOS Details review for iOS device CSV uploads

In order to streamline uploading IMEI numbers for Corporate devices and Apple serial numbers for Configurator enrollment, Intune is removing the row by row review of hardware identifiers already found in the system. This review allows the IT Pro to accept associated Details from the CSV to overwrite the existing details for a hardware identifier already in the system. The review will be replaced by a single option to automatically overwrite Details for all hardware identifiers or ignore new details for existing identifiers. This change will apply to the new console only. Until the existing Admin console is retired, no change will take place.
-->

### iOS cihazlarını korumak için Lookout tümleştirmesi
Ekim'de, Microsoft, iOS mobil cihazlardaki kötü amaçlı yazılımları, riskli uygulamaları ve diğer tehditleri algılayarak cihazları korumak için Lookout'un mobil tehdit koruma çözümüyle tümleşiyor. Lookout’ın çözümü tehdit düzeyini saptamanıza yardımcı olur ve bu ayar yapılandırılabilir. Lookout’un risk değerlendirmesi temelinde cihaz uyumluluğunu saptamak için Intune’da bir uyumluluk ilkesi kuralı oluşturabilirsiniz. Koşullu erişim ilkelerini kullanarak, cihaz uyumluluk durumuna göre şirket kaynaklarına erişime izin verebilir veya erişimi reddedebilirsiniz.

Uyumlu olmayan iOS cihazlarının son kullanıcılarının kaydolmaları istenecek ve şirket verilerine erişim kazanmak için cihazlarına Lookout for Work uygulamasını yüklemeleri, uygulamayı etkinleştirmeleri ve Lookout for Work uygulamasında bildirilen tehditleri gidermeleri gerekecek.
<!--TFS 1319493-->

### Intune Uygulama SDK'sı ve Android için Uygulama Sarmalama Aracı
Intune Uygulaması Sarmalama Aracı'nı veya Intune Uygulama SDK'sını kullanarak uygulamalarınızın Intune mobil uygulama yönetim (MAM) ilkelerini kullanmasını sağlayabilirsiniz. Uygulama Sarmalama Aracı ve SDK için yeni güncelleştirmeler şunları içerecek:

* Android N desteği
* Cihaz kaydı gerektirmeden Intune MAM ilkeleri desteği
* Xamarin tabanlı Android uygulamaları için destek

Cihaz kaydı gerektirmeyen MAM'yi ve Xamarin desteğini şu adresteki Android Uygulama Sarmalama Aracı genel önizlemesinden deneyebilirsiniz: [https://github.com/msintuneappsdk/intune-app-wrapper-android-preview](https://github.com/msintuneappsdk/intune-app-wrapper-android-preview)
<!--TFS 1319511; please create new TFS entry for WN text associated with this TFS item-->

<!--TFS 1319613; no iX review on PM text blurb

### Private preview customers using MAM Conditional Access will have their policies reset

Due to changes in the policy structure for Conditional Access for Mobile App Management, any existing policies that were set by customers through the private preview will be removed. Customers will need to set new policies once the change is made. The timing will coincide with the October service update.
-->

### Ayrıca bkz.
Son geliştirmelere ilişkin ayrıntılar için bkz. [Microsoft Intune’daki Yenilikler](whats-new-in-microsoft-intune.md).



<!--HONumber=Oct16_HO1-->


