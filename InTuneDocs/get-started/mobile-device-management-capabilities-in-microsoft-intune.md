---
title: "Kayıtlı cihaz yönetimi özellikleri |Microsoft Docs"
description: "Intune’un kaydettiğiniz cihazları yönetmenize nasıl yardımcı olabileceğini öğrenmek için bu konuyu okuyun."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/12/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f23b3ee7-78da-4e53-9fc2-78e58401bcf9
ms.reviewer: angrobe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f268cf29461447306d0f5c3ca06d541d9a03a49d
ms.openlocfilehash: 898975338edcd3267fd47d62d23b35e295f0d99b


---
# <a name="enrolled-device-management-capabilities-of-microsoft-intune"></a>Microsoft Intune’un kayıtlı cihaz yönetimi özellikleri

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune bir dizi cihazı hizmete *kaydederek* yönetmenize olanak tanır. Bazı cihaz türlerini kendiniz kaydedebilirsiniz veya kullanıcılar *şirket portalı* uygulamasını kullanarak kaydedebilir. Bu ayrıca, uygulamalara göz atma, uygulamaları yükleme, cihazlarının şirket ilkeleriyle uyumlu olduğundan emin olma ve BT desteğine başvurma gibi işlemler yapmalarını da sağlar.

Bu konu başlığı altında, cihazınızı kaydettikten sonra elde edeceğiniz özelliklerin tam listesi verilmiştir.

Yönetim, envanter, uygulama dağıtımı, sağlama ve kullanımdan kaldırma, Intune yönetim konsolu aracılığıyla gerçekleştirilir. Kullanıcılar uygulamaları yüklemek, cihazlarını kaydetmek veya kaydı kaldırmak ve BT departmanına ya da yardım masasına başvurmak için şirket portalına erişim kazanır.



## <a name="device-security-and-configuration"></a>Cihaz güvenliği ve yapılandırma

|Özellik|Ayrıntılar|Daha fazla bilgi|
|--------------|-----------|--------------------|
|Yapılandırma ilkeleri<br><br>Özel ilkeler| Kuruluşunuzdaki mobil cihazlarda birçok ayar ve özelliği yönetmenizi sağlar. Örneğin, parola isteyebilir, başarısız oturum açma girişimlerinin sayısını sınırlandırabilir, ekranın kilitlenmesinden önceki süreyi sınırlandırabilir, parola sona erme süresini ayarlayabilir ve daha önce kullanılan parolaların kullanımını engelleyebilirsiniz. Ayrıca cihaz kamerası veya web tarayıcısı gibi donanım ve yazılım özelliklerinin kullanımını da denetleyebilirsiniz.<br><br>Yapılandırma ilkeleri ihtiyaç duyduğunuz ayarı içermiyorsa, özel ilkeleri kullanın. iOS cihazları için Apple Yapılandırıcı aracından dışarı aktarılan ayarları alabilirsiniz. Diğer cihazlar için Open Mobile Alliance Uniform Resource Identifier (OMA-URI) ayarlarını kullanarak cihazdaki ayarları ve özellikleri yapılandırabilirsiniz.|[Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies)<br />|
|Uzaktan Temizleme, Uzak Kilit ve Parola Sıfırlama|Bir cihaz kaybolur veya çalınırsa hassas verileri siler. Örneğin, cihazı uzaktan kilitleyebilir, fabrika ayarlarına sıfırlayabilir veya yalnızca kurumsal verileri temizleyebilirsiniz.<br><br>Kullanıcılar cihazlarına erişimi kaybederse geçiş kodlarını sıfırlayabilir, kaybolan veya çalınan cihazları kilitleyebilir ve hatta kaybolan ya da çalınan cihazların verilerini temizleyebilirsiniz.|[Uzak kilitleme ve parola sıfırlama ile cihazlarınızı korumaya yardımcı olma](/intune/deploy-use/use-remote-lock-and-passcode-reset-in-microsoft-intune) ve [Cihazları Intune yönetiminden kaldırma](/intune/deploy-use/retire-devices-from-microsoft-intune-management).|
|Bilgi noktası modu|Mobil cihazların ekran yakalama ve güç düğmesi gibi belirli özelliklerini kilitlemenizi sağlar. Ayrıca, cihazları belirttiğiniz tek bir uygulamayı çalıştıracak şekilde kısıtlamanıza olanak tanır.|[Microsoft Intune’da iOS yapılandırma ilkesi ayarları](/intune/deploy-use/ios-policy-settings-in-microsoft-intune)|

## <a name="app-management"></a>Uygulama yönetimi

|Özellik|Ayrıntılar|Daha fazla bilgi|
|--------------|-----------|--------------------|
|Uygulama dağıtımı ve yönetimi|Mobil uygulamaları kurulum dosyalarından ve uygulama mağazalarından uygulama dağıtma, uygulama durumunun ayrıntılı bir şekilde izlenmesi ve uygulama kaldırma dahil yaşam döngüsü boyunca yönetmenize yardımcı olmak için çeşitli araçlar sağlar.|[Microsoft Intune'da uygulamaları dağıtma](/intune/deploy-use/deploy-apps)|
|Uyumlu ve uyumlu olmayan uygulamalar|Uyumlu uygulamaların (kullanıcıların yüklemesine izin verilen uygulamalar) ve uyumlu olmayan uygulamaların (kullanıcıların yüklemesine izin verilmeyen uygulamalar) listelerini belirtmenizi sağlar.|[Microsoft Intune’da iOS ilke ayarları](/intune/deploy-use/ios-policy-settings-in-microsoft-intune)|
|Mobil uygulama yönetimi|Mobil uygulama yönetimini kullanarak, hem Intune tarafından yönetilen hem de yönetilmeyen tüm cihazlarda uygulamalar için kısıtlamaları yapılandırır. Bu, kopyalama ve yapıştırma, verilerin dış yedeğini oluşturma ve uygulamalar arasında veri aktarma gibi işlemleri kısıtlayarak şirket verilerinizin güvenliğini artırmaya yardımcı olur.|[Microsoft Intune konsolunda mobil uygulama yönetimi ilkelerini yapılandırma ve dağıtma](/intune/deploy-use/configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console)<br><br>[Microsoft Intune ile mobil uygulama yönetimi ilkeleri oluşturma ve dağıtma](/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune)<br /><br />[Microsoft Intune Uygulama Sarmalama Aracı ile iOS uygulamalarını mobil uygulama yönetimi için hazırlama](/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)<br /><br />[Microsoft Intune Uygulaması Sarmalama Aracı ile Android uygulamaları mobil uygulama yönetimi için hazırlama](/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)|
|iOS mobil uygulama yapılandırması|Mobil uygulama yapılandırma ilkelerini kullanarak, kullanıcı uygulamayı çalıştırdığında iOS uygulamaları için gerekebilecek ayarları sağlar. Örneğin, uygulama kullanıcının bağlantı noktası numarasını veya oturum açma bilgilerini belirtmesini isteyebilir. Bu, uygulama yapılandırmasını kolaylaştırmaya ve destek aramalarının sayısını azaltmaya yardımcı olabilir.|[iOS uygulamalarını Microsoft Intune’da mobil uygulama yapılandırma ilkeleriyle yapılandırma](/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)|
|iOS mobil uygulaması sağlama profilleri|Süresi dolmak üzere olan iOS uygulamalarına sağlama profilleri dağıtmanıza yardımcı olur. |[Uygulamalarınızın süresinin dolmasını engellemek için iOS mobil sağlama profili ilkelerini kullanma](/intune/deploy-use/ios-mobile-app-provisioning-profiles)|
|Yönetilen tarayıcı|Cihaz kullanıcılarının ziyaret edebileceği web sitelerini denetlemek için yönetilen tarayıcı profilleri yapılandırır. Ayrıca, yönetilen tarayıcıya mobil uygulama yönetimi ilkeleri de uygulayabilirsiniz.|[Microsoft Intune'la yönetilen tarayıcı ilkelerini kullanarak İnternet erişimini yönetme](/intune/deploy-use/manage-internet-access-using-managed-browser-policies)|
|İş İçin Windows Hello|Parolaları, akıllı kartları ya da sanal akıllı kartları değiştirmek için Windows 10’da şirket içi Active Directory’nin veya Azure Active Directory’nin kullanıldığı alternatif bir oturum açma yöntemi olan İş İçin Windows Hello’yu tümleştirmenize olanak tanır.|[Microsoft Intune ile cihazlarda İş İçin Windows Hello ayarlarını denetleme](/intune/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune)|
|Toplu satın alınan uygulamalar|Bir toplu satın alma programı aracılığıyla lisans bilgilerini uygulama mağazasından içeri aktararak, kaç lisans kullandığınızı izleyerek ve sahip olduğunuzdan fazla uygulama kopyası yüklemenizi önleyerek satın aldığınız uygulamaları yönetmenize yardımcı olur.|[Microsoft Intune kullanarak toplu satın alınan uygulamaları yönetme](/intune/deploy-use/manage-volume-purchased-apps-in-microsoft-intune)|

## <a name="company-resource-access"></a>Şirket kaynak erişimi

|Özellik|Ayrıntılar|Daha fazla bilgi|
|--------------|-----------|--------------------|
|Sertifika profilleri|Wi-Fi, VPN ve e-posta profillerini güvenli hale getirmek ve kimlik doğrulaması yapmak için kullanılabilen güvenli sertifika profilleri ve Basit Sertifika Kaydı Profilleri (SCEP) sertifikaları oluşturur ve dağıtır.|[Microsoft Intune’da sertifika profilleriyle güvenli kaynak erişimi](/intune/deploy-use/secure-resource-access-with-certificate-profiles)|
|Wi-Fi profilleri|Kablosuz ağ ayarlarını kullanıcılarınıza dağıtır. Bu ayarları dağıtarak kurumsal ağa bağlanmak için gereken kullanıcı çabasını en aza indirirsiniz.|[Microsoft Intune’da Wi-Fi bağlantıları](/intune/deploy-use/wi-fi-connections-in-microsoft-intune)|
|E-posta profilleri|E-posta ayarlarını oluşturur ve cihazlara dağıtır. Bu, kullanıcıların herhangi bir ayar yapmasına gerek kalmadan kişisel cihazlarından kurumsal e-postalara erişebilecekleri anlamına gelir.|[Microsoft Intune ile e-posta profilleri kullanarak şirket e-postasına erişimi yapılandırma](/intune/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune)|
|VPN profilleri|VPN ayarlarını kuruluşunuzdaki kullanıcı ve cihazlara dağıtır. Bu ayarları dağıtarak, şirket ağındaki kaynaklara bağlanmak için gereken kullanıcı çabasını en aza indirirsiniz.|[Microsoft Intune’da VPN bağlantıları](/intune/deploy-use/vpn-connections-in-microsoft-intune)|
|Koşullu erişim ilkeleri|Intune tarafından yönetilmeyen cihazların Microsoft Exchange e-posta ve SharePoint Online hizmetlerine erişimini yönetir.|[Microsoft Intune ile e-posta ve SharePoint erişimini kısıtlama](/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)|

## <a name="inventory-and-reporting"></a>Envanter ve raporlama

|Özellik|Ayrıntılar|Daha fazla bilgi|
|--------------|-----------|--------------------|
|Envanter ve raporlama|Yönettiğiniz cihazlar ve cihazlarda kullanılan yazılımlar hakkında bilgiler bulur.|[Microsoft Intune’da envanterle cihazlarınızı anlama](/intune/deploy-use/understand-your-devices-with-inventory-in-microsoft-intune)|


### <a name="see-also"></a>Ayrıca bkz.
[Microsoft Intune'da Windows bilgisayarı yönetim özellikleri](windows-pc-management-capabilities-in-microsoft-intune.md)



<!--HONumber=Dec16_HO3-->


