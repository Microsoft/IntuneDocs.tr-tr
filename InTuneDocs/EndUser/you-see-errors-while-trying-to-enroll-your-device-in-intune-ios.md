---
# required metadata

title: iOS cihazınızı Intune’a kaydetmeye çalışırken hata görüyorsunuz | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 92a8d06d-0ecb-4912-898b-993e8eaf4e58

# optional metadata

ROBOTS: noindex
#audience:
#ms.devlang:
ms.reviewer: esmich
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# iOS cihazınızı Intune’a kaydetmeye çalışırken hata görüyorsunuz

Aşağıdaki tabloda iOS cihazlarınızı Intune’a kaydederken görebileceğiniz hatalar listelenmektedir. Bu bağlantıyı BT yöneticinizle paylaşın. Kişi bilgileri için [Şirket Portalı Web sitesine](http://portal.manage.microsoft.com) bakın.

|Hata iletisi|Sorun|BT yöneticinize söylemeniz gerekenler|
|-----------------|---------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
|DeviceCapReached|Daha önce çok fazla sayıda mobil cihaz kaydettiniz.|Kullanıcı başka bir cihaz kaydetmeden önce o anda Şirket Portalı’na kayıtlı mobil cihazlarından birini kaldırmalıdır. Kullanmakta olduğunuz cihaz türüne yönelik yönergelere bakın: [Android](unenroll-your-device-from-intune-android.md), [iOS](unenroll-your-device-from-intune-ios), [Windows](unenroll-your-device-from-intune-windows).|
|APNSCertificateNotValid|Mobil cihazınızın şirket ağınızla iletişim kurmasına imkan tanıyan sertifika ile ilgili bir sorun var.<br /><br />IT yöneticilerinize başvurun ve mobil cihazınızı kaydederken **APNSCertificateNotValid** iletisini aldığınızı ve bu tablodaki çözüme bakmalarını söyleyin.|Apple Anında İletilen Bildirim Servisi (APNS) kayıtlı iOS cihazlara ulaşmak için bir kanal sağlar. APNS sertifikasını alma adımları uygulanmadıysa veya APNS sertifikasının süresi dolduysa kayıt denemeleri başarısız olur ve bu ileti görüntülenir.<br /><br />[Active Directory’yi eşitleme ve Intune’a kullanıcıları ekleme](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-3) ve [Kullanıcıları ve cihazları düzenleme](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-5) konu başlıkları altında kullanıcıları ayarlamayla ilgili bilgileri gözden geçirin.|
|AccountNotOnboarded|Mobil cihazınızın şirket ağınızla iletişim kurmasına imkan tanıyan sertifika ile ilgili bir sorun var.<br /><br />IT yöneticilerinize başvurun ve mobil cihazınızı kaydederken **APNSNotOnboarded** iletisini aldığınızı ve bu tablodaki çözüme bakmalarını söyleyin.|Apple Anında İletilen Bildirim Servisi (APNS) kayıtlı iOS cihazlara ulaşmak için bir kanal sağlar. APNS sertifikasını alma adımları uygulanmadıysa veya APNS sertifikasının süresi dolduysa kayıt denemeleri başarısız olur ve bu ileti görüntülenir.<br /><br />Daha fazla bilgi için, [Microsoft Intune ile iOS ve Mac yönetimini ayarlama](/Intune/Deployuse/set-up-ios-and-mac-management-with-microsoft-intune) konusunu gözden geçirin.|
|DeviceTypeNotSupported|iOS olmayan bir cihaz kullanarak kaydolmayı denediniz. Kaydetmeye çalıştığınız mobil cihaz türü desteklenmemektedir.<br /><br />Cihazınızın iOS sürüm 7.1 veya üzerini çalıştırdığından emin olun.<br /><br />IT yöneticilerinize başvurun ve mobil cihazınızı kaydederken **DeviceTypeNotSupported** iletisini aldığınızı ve bu tablodaki çözüme bakmalarını söyleyin.|Kullanıcı cihazının iOS sürüm 7.1 veya üzerini çalıştırdığından emin olun.|
|UserLicenseTypeInvalid|Kullanıcı hesabınız henüz gerekli bir kullanıcı grubuna üye olmadığı için mobil cihazınızı kaydedemiyorsunuz.<br /><br />IT yöneticilerinize başvurun ve mobil cihazınızı kaydederken **UserLicenseTypeInvalid** iletisini aldığınızı ve bu tablodaki çözüme bakmalarını söyleyin.|Kullanıcıların cihazlarını kaydedebilmesi için doğru kullanıcı grubunun üyesi olmaları gerekir. Bu ileti kullanıcının belirlenen mobil cihaz yönetimi yetkilisi için yanlış lisans türüne sahip olduğu anlamına gelir. Örneğin, mobil cihaz yönetimi yetkilisi olarak Intune belirlendiyse ve kullanıcı bir System Center 2012 R2 Configuration Manager lisansı kullanıyorsa bu hatayı alır.<br /><br />Daha fazla bilgi için aşağıdakileri gözden geçirin:<br /><br />[Microsoft Intune’la iOS ve Mac yönetimini ayarlama](/Intune/Deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) konusunu, [Sync Active Directory’de kullanıcıları ayarlama ve Intune’a kullanıcı kaydetme](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-3 ayrıca [kullanıcıları ve cihazları düzenleme](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-5) bilgilerini gözden geçirin.|
|MdmAuthorityNotDefined|Bu mesaj BT yöneticinizin şirketinizdeki mobil cihazların yönetilme şeklini yapılandırması gerektiğini belirtir.<br /><br />IT yöneticilerinize başvurun ve mobil cihazınızı kaydederken **MdmAuthorityNotDefined** iletisini aldığınızı ve bu tablodaki çözüme bakmalarını söyleyin.|Intune’da mobil cihaz yönetimi yetkilisi belirlenmemiştir.<br /><br />[30 günlük Microsoft Intune denemesini başlatın](/Intune/Understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune) bölümündeki “6. Adım: Mobil cihazları kaydetme ve uygulama yükleme” kısmında madde 1’i gözden geçirin.|

### Ayrıca bkz.
[Using your iOS or Mac OS X device with Intune](using-your-ios-or-mac-os-x-device-with-intune.md)

<!--HONumber=Jun16_HO2-->


