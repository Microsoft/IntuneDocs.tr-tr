---
title: Yenilikler | Microsoft Intune
description: "Bu ayki ve geçmişteki Microsoft Intune sunumlarındaki yenilikleri öğrenin"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 503719953031bf5079b2bf5bc84a0497d708f79a
ms.openlocfilehash: 730809e0841a248b90f5fe157f2c6338bfd32b2d


---
# Microsoft Intune'daki yenilikler -- Ekim 2016
Microsoft Intune’un bu sürümündeki yenilikleri öğrenin. Planlama yapmanız gereken yaklaşan değişiklikler hakkında ve geçmiş sunumlar hakkında bilgiler de alabilirsiniz.

Bu özelliklerin tümü, sonunda karma müşteri dağıtımlarında (Intune ile Configuration Manager) desteklenecektir. Yeni karma özellikler hakkında daha fazla bilgi için, [Karma Yenilikler sayfamızı](https://technet.microsoft.com/library/mt718155.aspx) gözden geçirin.
<!---@Barry, the above blurb stays in each version, but make sure Tyler signs off each time. Also, remember to set the ms.date in the metadata to the sprint release. --->

## Yenilikler

### Mobil uygulama yönetimi için koşullu destek
Yalnızca Outlook gibi Intune mobil uygulama yönetimi ilkelerini destekleyen uygulamalardan erişime izin vermek için Exchange Online’a erişimi kısıtlayabilirsiniz. [Bu yeni özellik](/intune/deploy-use/allow-policy-managed-apps-access-to-o365), Intune mobil uygulama yönetimi (MAM) ilkeleriyle mükemmel bir uyum sağlar ve yerleşik posta istemcilerine veya Intune MAM ilkeleriyle yapılandırılmamış olan diğer uygulamalara erişimi engelleyebilirsiniz. Böylelikle, kullanıcılarınızın kuruluşunuzun verilerine Intune MAM kullanılarak korunan uygulamalarla erişmesi güvence altına alır. Intune mobil uygulama yönetimini Azure portalından başlatabilirsiniz. “Ayarlar” dikey penceresinde yeni Koşullu Erişim bölümünü bulun.

### Windows Bilgisayarlar için koşullu erişim
Artık Windows bilgisayarlarının [Exchange Online](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune) ve [SharePoint Online](/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune)’a erişmesini engellemek için Intune Yönetici Konsolu aracılığıyla koşullu erişim ilkeleri oluşturabilirsiniz. Office masaüstü ve evrensel uygulamalara erişimi engellemek için de koşullu erişim ilkeleri oluşturabilirsiniz.

### Android for Work desteği
Intune artık Android for Work programının bir parçası haline gelmiştir. Intune'a Android for Work özellikleri için desteği bu ay çıkarmaya başlayacağız.
[Android for Work için Intune desteği hakkında Microsoft'un duyurusunu okuyun](https://blogs.technet.microsoft.com/enterprisemobility/2016/09/12/microsoft-intune-support-for-android-for-work/).

Aşağıdaki Intune konuları yenidir veya Android for Work bilgileriyle güncelleştirilmiştir:

BT uzmanları için:
- [Android for Work’ü ayarlama](/intune/deploy-use/set-up-android-for-work)
<!--- [Nathan Bigman's resource access topics]()-->
- [Intune ile Exchange Online’a ve yeni Ayrılmış Exchange Online ortamına e-posta erişimini kısıtlama](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)
- [Intune’la Şirket İçi Exchange’e ve eski Ayrılmış Exchange Online ortamına e-posta erişimini kısıtlama](/intune/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)
- [Android for Work uyumluluk ilkesi ayarları](/intune/deploy-use/afw-compliance-policy-settings-in-microsoft-intune)
- [Android for Work uygulamalarını dağıtma](/intune/deploy-use/android-for-work-apps)
- [Android for Work uygulamalarını mobil uygulama yapılandırma ilkeleri ile yapılandırma](/intune/deploy-use/afw-app-configuration-policy)
- [Android for Work ilke ayarları](/intune/deploy-use/android-for-work-policy-settings-in-microsoft-intune)

Son kullanıcılar için:
- [İş profili oluşturduğunuzda ne olur?](/intune/enduser/what-happens-when-you-create-a-work-profile-android)
- [Bir iş profili oluşturma ve cihazınızı Intune’a kaydetme](/intune/enduser/create-a-work-profile-and-enroll-your-device-in-intune-android)

### iOS cihazlarını korumak için Lookout tümleştirmesi
Ekim'de, Microsoft, iOS mobil cihazlardaki kötü amaçlı yazılımları, riskli uygulamaları ve diğer tehditleri algılayarak cihazları korumak için Lookout'un mobil tehdit koruma çözümüyle tümleşiyor. Lookout’ın çözümü tehdit düzeyini saptamanıza yardımcı olur ve bu ayar yapılandırılabilir. Lookout’un risk değerlendirmesi temelinde cihaz uyumluluğunu saptamak için Intune’da bir uyumluluk ilkesi kuralı oluşturabilirsiniz. Koşullu erişim ilkelerini kullanarak, cihaz uyumluluk durumuna göre şirket kaynaklarına erişime izin verebilir veya erişimi reddedebilirsiniz.

Uyumlu olmayan iOS cihazlarının son kullanıcılarının kaydolmaları istenecek ve şirket verilerine erişim kazanmak için cihazlarına Lookout for Work uygulamasını yüklemeleri, uygulamayı etkinleştirmeleri ve Lookout for Work uygulamasında bildirilen tehditleri gidermeleri gerekecek. [Lookout for Work uygulamalarını yapılandırmayı ve dağıtmayı](/intune/deploy-use/configure-and-deploy-lookout-for-work-apps) öğrenin.
<!--TFS 1319493-->

<!--### New Microsoft Intune Company Portal available for Windows 10 devices
Microsoft is releasing a new [Microsoft Intune Company Portal for Windows 10 devices](https://go.microsoft.com/fwlink/?linkid=830663). This app, which leverages the new Windows 10 Universal format, will provide the user with an updated user experience within the app and identical experiences across all Windows 10 devices, PC and Mobile alike, while still enabling all the same functionality that they are using today.

The new app will also allow users to leverage additional platform features like single sign-on (SSO) and certificate-based authentication on Windows 10 devices. The app will be made available as an upgrade to the existing Windows 8.1 Company Portal and Windows Phone 8.1 Company Portal installs from the Windows Store.-->

### Android için Intune Uygulama Sarmalama Aracı
Intune Uygulaması Sarmalama Aracı'nı kullanarak uygulamalarınızın Intune mobil uygulama yönetim (MAM) ilkelerini kullanmasını sağlayabilirsiniz. Cihaz kaydı gerektirmeden Intune MAM ilkeleri desteği artık kullanılabilir.

### MAM ilkeleriyle yönetilen uygulamalardan yazdırmayı yönetme
Artık MAM ilkeleri olan uygulamalardan şirket verilerinin yazdırılmasını engelleyebilirsiniz. Bu ayar, [Azure portalından](/Intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) kullanılabilir ve gerek [iOS](/Intune/deploy-use/ios-mam-policy-settings), gerekse [Android](/Intune/deploy-use/android-mam-policy-settings) cihazlarında desteklenmektedir.
<!--TFS 1014328-->

## Bildirimler

### Android Samsung KNOX ile Intune uyumluluğu
Samsung Galaxy Ace telefonunun bazı modelleri, Intune tarafından Samsung KNOX cihazları olarak yönetilemiyor. Bu cihazları Intune’a kaydettiğinizde, artık standart Android cihazları olarak yönetilecek.

Etkilenen model numaraları:

* SM-G313HU
* SM-G313HY
* SM-G313M
* SM-G313MY
* SM-G313U

Sizin ve son kullanıcılarınızın başka bir işlem yapması gerekmez. Daha fazla bilgi için [Samsung KNOX](https://www.samsungknox.com) web sitesini ziyaret edin.

### Windows 8 için Şirket Portalı uygulaması kaldırılmıştır; Windows Phone 8 ve Windows RT platformları için destek kaldırılmaktadır
Microsoft Intune, Ekim 2016'dan başlayarak Windows 8 Şirket Portalı için desteği kaldıracaktır. Microsoft Intune, ayrıca Windows Phone 8 ve Windows RT platformları için desteği de kaldıracaktır. Bu nedenle bundan sonra herhangi bir Windows Phone 8 veya Windows RT cihazını kaydetmeniz veya güncelleştirmeniz mümkün olmayacaktır.

Daha önce kaydedilen Windows Phone 8, Windows RT ve Windows 8 cihazlarını yönetmeye devam edebilirsiniz. Windows 8 ve Windows Phone 8 cihazlarını Windows 8.1’e ve Windows Phone 8.1’e güncelleştirin ve bu cihazlara bir kesinti olmadan uygulama dağıtmaya devam etmek için ilgili Windows 8.1 ve Windows Phone 8.1 Şirket Portalı uygulamalarını kullanın.

Kasım 2016'dan itibaren Windows Phone 8 Şirket Portalı için desteği kaldıracağız.
<!--TFS 1255391-->

## Yakında

### Windows 10 cihazları için Yeni Microsoft Intune Şirket Portalı
Microsoft, Windows 10 cihazları için yeni bir Microsoft Intune Şirket Portalı'nı piyasaya sürüyor. Yeni Windows 10 Evrensel biçiminden yararlanan bu uygulama, kullanıcıya uygulama içinden güncelleştirilmiş bir kullanıcı deneyimi ve kullanıcının bugün kullanmakta olduğu işlevselliğin tümünü olanaklı kılmaya devam ederken, ister bilgisayar ister Mobil tüm Windows 10 cihazlarında aynı deneyimi sunacak.

Yeni uygulama, kullanıcının Windows 10 cihazlarında çoklu oturum açma (SSO) ve sertifika tabanlı kimlik doğrulama gibi ek platform özelliklerinden yararlanmasını da sağlar. Uygulama, mevcut Windows 8.1 Şirket Portalı ve Windows Phone 8.1 Şirket Portalı için güncelleştirme olarak Windows Mağazası'ndan yüklenir. Daha fazla ayrıntı için bkz. [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp).
<!--TFS 1016502-->

### Ayrıca bkz.
* [Microsoft Intune Blogu](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Bulut Platformu yol haritası](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Önceki Intune sürümleri](previous-intune-releases.md)



<!--HONumber=Oct16_HO3-->


