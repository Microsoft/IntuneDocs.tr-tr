---
title: "Mobil cihaz yönetimi özellikleri | Microsoft Intune"
description: 
keywords: 
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f23b3ee7-78da-4e53-9fc2-78e58401bcf9
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f33a86c51320c75ce74d20e0cac2b9581990ecec
ms.openlocfilehash: 0f460165f251acf95f4af36afa39409d3eb21162


---
# Microsoft Intune'da mobil cihaz yönetimi özellikleri

Microsoft Intune bir dizi cihazı hizmete *kaydederek* yönetmenize olanak tanır. Bundan sonra kullanıcılar, *şirket portalını* kullanarak cihazlarını kaydetme, uygulamalara göz atma, uygulamaları yükleme, cihazlarının şirket ilkeleriyle uyumlu olduğundan emin olma ve BT desteğine başvurma gibi çeşitli işlemler yapabilirler.
Bu konu başlığı altında, kayıtlı cihazların size sağladığı özelliklerin tam listesi verilmiştir.

Yönetim, envanter, uygulama dağıtımı, sağlama ve kullanımdan kaldırma, Intune yönetim konsolu aracılığıyla gerçekleştirilir. Kullanıcılar uygulamaları yüklemek, cihazlarını kaydetmek veya kaydı kaldırmak ve BT departmanına ya da yardım masasına başvurmak için şirket portalına erişir.



## Cihaz güvenliği ve yapılandırma

|Özellik|Ayrıntılar|Daha fazla bilgi|
|--------------|-----------|--------------------|
|Yapılandırma ilkeleri<br><br>Özel ilkeler|Mobil cihaz yapılandırma ilkeleri, kuruluşunuzdaki mobil cihazlarda birçok ayar ve özelliği yönetmenizi sağlar. Örneğin, parola isteyebilir, başarısız oturum açma girişimlerinin sayısını sınırlandırabilir, ekranın kilitlenmesinden önceki süreyi dakika cinsinden sınırlandırabilir, parola sona erme süresini ayarlayabilir ve daha önce kullanılan parolaların kullanımını engelleyebilirsiniz. Ayrıca cihaz kamerası veya web tarayıcısı gibi donanım ve yazılım özelliklerinin kullanımını da denetleyebilirsiniz.<br><br>Yapılandırma ilkeleri ihtiyaç duyduğunuz ayarı içermiyorsa özel ilkeleri kullanın. iOS cihazları için Apple Yapılandırıcı Aracı'ndan dışarı aktarılan ayarları alabilirsiniz. Diğer cihazlar için OMA URI ayarlarını kullanarak cihazdaki ayarları ve özellikleri yapılandırabilirsiniz.|[Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies)<br />|
|Uzaktan Temizleme, Uzak Kilit ve Parola Sıfırlama|Bir cihaz kaybolur veya çalınırsa hassas verileri silin. Örneğin, cihazı uzaktan kilitleyebilir, fabrika ayarlarına sıfırlayabilir veya yalnızca kurumsal verileri temizleyebilirsiniz.<br>Kullanıcılar cihazlarına erişimi kaybederse geçiş kodlarını sıfırlayabilir, kaybolan veya çalınan cihazları kilitleyebilir ve hatta kaybolan ya da çalınan cihazların verilerini temizleyebilirsiniz.|[Uzak kilitleme ve parola sıfırlama ile cihazlarınızı korumaya yardımcı olma](/intune/deploy-use/use-remote-lock-and-passcode-reset-in-microsoft-intune) ve [Cihazları Intune yönetiminden kaldırma](/intune/deploy-use/retire-devices-from-microsoft-intune-management).|
|Bilgi noktası modu|Mobil cihazların ekran yakalama ve güç düğmesi gibi belirli özelliklerini kilitlemenizi sağlar. Ayrıca, cihazları belirttiğiniz tek bir uygulamayı çalıştıracak şekilde kısıtlamanıza olanak tanır.|[Microsoft Intune’da iOS yapılandırma ilkesi ayarları](/intune/deploy-use/ios-policy-settings-in-microsoft-intune)|

## Uygulama yönetimi

|Özellik|Ayrıntılar|Daha fazla bilgi|
|--------------|-----------|--------------------|
|Uygulama dağıtımı ve yönetimi|Mobil uygulamaları kurulum dosyalarından ve uygulama mağazalarından uygulama dağıtma, uygulama durumunun ayrıntılı bir şekilde izlenmesi ve uygulama kaldırma dahil yaşam döngüsü boyunca yönetmenize yardımcı olmak için çeşitli araçlar sağlar.|[Microsoft Intune'da uygulamaları dağıtma](/intune/deploy-use/deploy-apps)|
|Uyumlu ve uyumlu olmayan uygulamalar|Uyumlu uygulamaların (kullanıcıların yüklemesine izin verilir) ve uyumlu olmayan uygulamaların (kullanıcılar tarafından yüklenmemelidir) listelerini belirtmenizi sağlar.|[Microsoft Intune’da iOS ilke ayarları](/intune/deploy-use/ios-policy-settings-in-microsoft-intune)|
|Mobil uygulama yönetimi|Mobil uygulama yönetimini kullanarak, hem Intune’la yönettiğiniz hem de Intune’la yönetilmeyen cihazlarda uygulamalar için kısıtlamaları yapılandırın. Bu kopyalama ve yapıştırma, verilerin dış yedeğini oluşturma ve uygulamalar arasında veri aktarma gibi işlemleri kısıtlayarak şirket verilerinizin güvenliğini artırmaya yardımcı olur.|[Configure and deploy mobile application management policies in the Microsoft Intune console](/intune/deploy-use/configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console)<br><br>[Microsoft Intune ile mobil uygulama yönetimi ilkeleri oluşturma ve dağıtma](/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune)<br /><br />[Microsoft Intune Uygulama Sarmalama Aracı ile iOS uygulamalarını mobil uygulama yönetimi için hazırlama](/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)<br /><br />[Microsoft Intune Uygulaması Sarmalama Aracı ile Android uygulamaları mobil uygulama yönetimi için hazırlama](/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)|
|Mobil uygulama yapılandırması|Kullanıcı uygulamayı çalıştırdığında, iOS uygulamaları için gerekebilecek ayarları sağlamak için mobil uygulama yapılandırma ilkelerini kullanın. Örneğin, uygulama kullanıcının oturum açma bilgilerinin bağlantı noktası numarasını belirtmesini isteyebilir. Bu, uygulama yapılandırmasını kolaylaştırmaya ve yardım masasına yapılan aramaların sayısını azaltmaya yardımcı olabilir.|[iOS uygulamalarını Microsoft Intune’da mobil uygulama yapılandırma ilkeleriyle yapılandırma](/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)|
|Yönetilen tarayıcı|Yönetilen tarayıcıyı kullanıcılarınıza dağıttıktan sonra, ziyaret edebilecekleri web sitelerini denetlemek için bir yönetilen tarayıcı ilkesi yapılandırabilirsiniz. Ayrıca, yönetilen tarayıcıya mobil uygulama yönetimi ilkeleri de uygulayabilirsiniz.|[Microsoft Intune'la yönetilen tarayıcı ilkelerini kullanarak İnternet erişimini yönetme](/intune/deploy-use/manage-internet-access-using-managed-browser-policies)|
|Microsoft Passport|Intune, parolayı, akıllı kartı ya da sanal akıllı kartı değiştirmek için Windows 10’da Active Directory veya bir Azure Active Directory hesabının kullanıldığı alternatif bir oturum açma yöntemi olan İş İçin Microsoft Passport’u tümleştirmenize olanak tanır.|[Microsoft Intune ile cihazlarda Microsoft Passport ayarlarını denetleme](/intune/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune)|

## Şirket kaynak erişimi

|Özellik|Ayrıntılar|Daha fazla bilgi|
|--------------|-----------|--------------------|
|Sertifika profilleri|Wi-Fi, VPN ve e-posta profillerini güvenli hale getirmek ve kimlik doğrulaması yapmak için kullanılabilen güvenli sertifika profilleri ve Basit Sertifika Kaydı Profilleri (SCEP) sertifikaları oluşturun ve dağıtın.|[Microsoft Intune’da sertifika profilleriyle güvenli kaynak erişimi](/intune/deploy-use/secure-resource-access-with-certificate-profiles)|
|Wi-Fi profilleri|Kablosuz ağ ayarlarını kullanıcılarınıza dağıtın. Bu ayarları dağıtarak kurumsal ağa bağlanmak için gereken son kullanıcı çabasını en aza indirin.|[Microsoft Intune’da Wi-Fi bağlantıları](/intune/deploy-use/wi-fi-connections-in-microsoft-intune)|
|E-posta profilleri|E-posta ayarlarını oluşturun ve cihazlara dağıtın. Bu, kullanıcıların herhangi bir ayar yapmasına gerek kalmadan kişisel cihazlarından kurumsal e-postalara erişmelerini sağlar.|[Microsoft Intune ile e-posta profilleri kullanarak şirket e-postasına erişimi yapılandırma](/intune/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune)|
|VPN profilleri|VPN ayarlarını kuruluşunuzdaki kullanıcı ve cihazlara dağıtın. Bu ayarları dağıtarak, şirket ağındaki kaynaklara bağlanmak için gereken son kullanıcı çabasını en aza indirirsiniz.|[Microsoft Intune’da VPN bağlantıları](/intune/deploy-use/vpn-connections-in-microsoft-intune)|
|Koşullu erişim ilkeleri|Intune tarafından yönetilmeyen cihazların Microsoft Exchange e-posta ve SharePoint Online hizmetlerine erişimini yönetin.|[Microsoft Intune ile e-posta ve SharePoint erişimini kısıtlama](/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)|

## Envanter ve raporlama

|Özellik|Ayrıntılar|Daha fazla bilgi|
|--------------|-----------|--------------------|
|Envanter ve raporlama|Yönettiğiniz cihazlar ve kullandıkları yazılım hakkında bilgiler bulun.|[Microsoft Intune’da envanterle cihazlarınızı anlama](/intune/deploy-use/understand-your-devices-with-inventory-in-microsoft-intune)|


### Ayrıca bkz.
[Microsoft Intune'da Windows bilgisayarı yönetim özellikleri](windows-pc-management-capabilities-in-microsoft-intune.md)



<!--HONumber=Jun16_HO4-->


