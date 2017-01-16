---
title: "iOS cihazınızı Intune’a kaydetmeye çalışırken hata alıyorsunuz | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 12/02/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 92a8d06d-0ecb-4912-898b-993e8eaf4e58
searchScope:
- Company Portal
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: esmich
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 9da632e906a1486ac705a0af99179ce9669c8a24


---

# <a name="you-see-errors-while-trying-to-enroll-your-ios-device-in-intune"></a>iOS cihazınızı Intune’a kaydetmeye çalışırken hata görüyorsunuz

Aşağıdaki tabloda iOS cihazlarınızı Intune’a kaydederken görebileceğiniz hatalar listelenmektedir. Bu bağlantıyı BT yöneticinizle paylaşın. Kişi bilgileri için [Şirket Portalı Web sitesine](http://portal.manage.microsoft.com) bakın.

|Hata iletisi|Sorun|BT yöneticinize söylemeniz gerekenler|
|-----------------|---------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
|NoEnrollmentPolicy|Kayıt ilkesi yok|Apple Anında İletilen Bildirim Servisi (APNs) sertifikası gibi tüm kayıt önkoşullarının ayarlandığını ve “Platform olarak iOS”un etkinleştirildiğini denetleyin. Yönergeler için, bkz. [iOS ve Mac cihaz yönetimini ayarlama](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune).|
|DeviceCapReached|Daha önce çok fazla sayıda mobil cihaz kaydettiniz.|Kullanıcı başka bir cihaz kaydetmeden önce o anda Şirket Portalı’na kayıtlı mobil cihazlarından birini kaldırmalıdır. Kullanmakta olduğunuz cihaz türüne yönelik yönergelere bakın: [Android](unenroll-your-device-from-intune-android.md), [iOS](unenroll-your-device-from-intune-ios.md), [Windows](unenroll-your-device-from-intune-windows.md).|
|APNSCertificateNotValid|Mobil cihazınızın şirket ağınızla iletişim kurmasına imkan tanıyan sertifika ile ilgili bir sorun var.<br /><br />BT yöneticilerinize başvurun, mobil cihazınızı kaydetmeyi denediğinizde **APNSCertificateNotValid** iletisini aldığınızı ve bu tablodaki çözüme bakmalarını söyleyin.|Apple Anında İletilen Bildirim Servisi (APNs) kayıtlı iOS cihazlara ulaşmak için bir kanal sağlar. APNs sertifikasını alma adımları uygulanmadıysa veya APNs sertifikasının süresi dolduysa kayıt denemeleri başarısız olur ve bu ileti görüntülenir.<br /><br />[Active Directory’yi eşitleme ve Intune’a kullanıcıları ekleme](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-3) ve [Kullanıcıları ve cihazları düzenleme](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-5) konu başlıkları altında kullanıcıları ayarlamayla ilgili bilgileri gözden geçirin.|
|AccountNotOnboarded|Mobil cihazınızın şirket ağınızla iletişim kurmasına imkan tanıyan sertifika ile ilgili bir sorun var.<br /><br />BT yöneticilerinize başvurun, mobil cihazınızı kaydetmeyi denediğinizde **APNSNotOnboarded** iletisini aldığınızı ve bu tablodaki çözüme bakmalarını söyleyin.|Apple Anında İletilen Bildirim Servisi (APNs) kayıtlı iOS cihazlara ulaşmak için bir kanal sağlar. APNs sertifikasını alma adımları uygulanmadıysa veya APNs sertifikasının süresi dolduysa kayıt denemeleri başarısız olur ve bu ileti görüntülenir.<br /><br />Daha fazla bilgi için, [Microsoft Intune ile iOS ve Mac yönetimini ayarlama](/Intune/Deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) konusunu gözden geçirin.|
|DeviceTypeNotSupported|iOS olmayan bir cihaz kullanarak kaydolmayı denemiş olabilirsiniz. Kaydetmeye çalıştığınız mobil cihaz türü desteklenmemektedir.<br /><br />Cihazınızın iOS sürüm 8.0 veya üzerini çalıştırdığından emin olun.<br /><br />BT yöneticilerinize başvurun, mobil cihazınızı kaydetmeyi denediğinizde **DeviceTypeNotSupported** iletisini aldığınızı ve bu tablodaki çözüme bakmalarını söyleyin.|Kullanıcı cihazının iOS sürüm 8.0 veya üzerini çalıştırdığından emin olun.|
|UserLicenseTypeInvalid|Kullanıcı hesabınız henüz gerekli bir kullanıcı grubuna üye olmadığı için mobil cihazınızı kaydedemiyorsunuz.<br /><br />BT yöneticilerinize başvurun, mobil cihazınızı kaydetmeyi denediğinizde **UserLicenseTypeInvalid** iletisini aldığınızı ve bu tablodaki çözüme bakmalarını söyleyin.|Kullanıcıların cihazlarını kaydedebilmesi için doğru kullanıcı grubunun üyesi olmaları gerekir. Bu ileti kullanıcının belirlenen mobil cihaz yönetimi yetkilisi için yanlış lisans türüne sahip olduğu anlamına gelir. Örneğin, mobil cihaz yönetimi yetkilisi olarak Intune belirlendiyse ve kullanıcı bir System Center 2012 R2 Configuration Manager lisansı kullanıyorsa bu hatayı alır.<br /><br />Daha fazla bilgi için aşağıdakileri gözden geçirin:<br /><br />[Microsoft Intune ile iOS ve Mac yönetimi ayarlama](/Intune/Deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) konusunu ve [Active Directory’yi eşitleme ve Intune’a kullanıcı ekleme](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-3) ve [kullanıcıları ve cihazları düzenleme](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-5) konularındaki kullanıcı ayarlamayla ilgili bilgileri gözden geçirin.|
|MdmAuthorityNotDefined|BT yöneticinizin şirketinizdeki mobil cihazların yönetilme şeklini ayarlaması gerekir.<br /><br />BT yöneticilerinize başvurun, mobil cihazınızı kaydetmeyi denediğinizde **MdmAuthorityNotDefined** iletisini aldığınızı ve bu tablodaki çözüme bakmalarını söyleyin.|Intune’da mobil cihaz yönetimi yetkilisi belirlenmemiştir.<br /><br />[30 günlük Microsoft Intune denemesini başlatın](/Intune/Understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune) bölümündeki “6. Adım: Mobil cihazları kaydetme ve uygulama yükleme” kısmında madde 1’i gözden geçirin.|



<!--HONumber=Dec16_HO2-->


