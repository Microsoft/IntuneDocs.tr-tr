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
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 364c7e1fe2bf17b0c804960c3ebaadb1cf4652a8
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---
# <a name="enrolled-device-management-capabilities-of-microsoft-intune"></a>Microsoft Intune’un kayıtlı cihaz yönetimi özellikleri

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune bir dizi cihazı hizmete *kaydederek* yönetmenize olanak tanır. Bazı cihaz türlerini kendiniz kaydedebilirsiniz veya kullanıcılar *şirket portalı* uygulamasını kullanarak kaydedebilir. Bu ayrıca, uygulamalara göz atma, uygulamaları yükleme, cihazlarının şirket ilkeleriyle uyumlu olduğundan emin olma ve BT desteğine başvurma gibi işlemler yapmalarını da sağlar.

Bu konu başlığı altında, cihazınızı kaydettikten sonra elde edeceğiniz özelliklerin tam listesi verilmiştir.

Yönetim, envanter, uygulama dağıtımı, sağlama ve kullanımdan kaldırma, Intune yönetim konsolu aracılığıyla gerçekleştirilir. Kullanıcılar uygulamaları yüklemek, cihazlarını kaydetmek veya kaydı kaldırmak ve BT departmanına ya da yardım masasına başvurmak için şirket portalına erişim kazanır.



## <a name="device-security-and-configuration"></a>Cihaz güvenliği ve yapılandırma

|Özellik|Ayrıntılar|Daha fazla bilgi|
|--------------|-----------|--------------------|
|Yapılandırma ilkeleri<br><br>Özel ilkeler| Kuruluşunuzdaki mobil cihazlarda birçok ayar ve özelliği yönetmenizi sağlar. Örneğin, parola isteyebilir, başarısız oturum açma girişimlerinin sayısını sınırlandırabilir, ekranın kilitlenmesinden önceki süreyi sınırlandırabilir, parola sona erme süresini ayarlayabilir ve daha önce kullanılan parolaların kullanımını engelleyebilirsiniz. Ayrıca cihaz kamerası veya web tarayıcısı gibi donanım ve yazılım özelliklerinin kullanımını da denetleyebilirsiniz.<br><br>Yapılandırma ilkeleri ihtiyaç duyduğunuz ayarı içermiyorsa, özel ilkeleri kullanın. iOS cihazları için Apple Yapılandırıcı aracından dışarı aktarılan ayarları alabilirsiniz. Diğer cihazlar için Open Mobile Alliance Tekdüzen Kaynak Tanımlayıcısı /intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) kullanabilirsiniz<br />|
|Uzaktan Temizleme, Uzak Kilit ve Parola Sıfırlama|Bir cihaz kaybolur veya çalınırsa hassas verileri siler. Örneğin, cihazı uzaktan kilitleyebilir, fabrika ayarlarına sıfırlayabilir veya yalnızca kurumsal verileri temizleyebilirsiniz.<br><br>Kullanıcılar cihazlarına erişimi kaybederse geçiş kodlarını sıfırlayabilir, kaybolan veya çalınan cihazları kilitleyebilir ve hatta kaybolan ya da çalınan cihazların verilerini temizleyebilirsiniz.|[Uzaktan kilitleme ve geçiş kodu sıfırlama özellikleriyle cihazlarınızın korunmasına yardımcı olma](/intune-classic/deploy-use/retire-devices-from-microsoft-intune-management)|
|Bilgi noktası modu|Mobil cihazların ekran yakalama ve güç düğmesi gibi belirli özelliklerini kilitlemenizi sağlar. Ayrıca, cihazları belirttiğiniz tek bir uygulamayı çalıştıracak şekilde kısıtlamanıza olanak tanır.|[Microsoft Intune’da iOS yapılandırma ilkesi ayarları](/intune-classic/deploy-use/ios-policy-settings-in-microsoft-intune)|

## <a name="app-management"></a>Uygulama yönetimi

|Özellik|Ayrıntılar|Daha fazla bilgi|
|--------------|-----------|--------------------|
|Uygulama dağıtımı ve yönetimi|Mobil uygulamaları kurulum dosyalarından ve uygulama mağazalarından uygulama dağıtma, uygulama durumunun ayrıntılı bir şekilde izlenmesi ve uygulama kaldırma dahil yaşam döngüsü boyunca yönetmenize yardımcı olmak için çeşitli araçlar sağlar.|[Microsoft Intune'da uygulamaları dağıtma](/intune-classic/deploy-use/deploy-apps)|
|Uyumlu ve uyumlu olmayan uygulamalar|Uyumlu uygulamaların /intune-classic/deploy-use/ios-policy-settings-in-microsoft-intune) bir listesini belirtmenizi sağlar|
|Mobil uygulama yönetimi|Mobil uygulama yönetimini kullanarak, hem Intune tarafından yönetilen hem de yönetilmeyen tüm cihazlarda uygulamalar için kısıtlamaları yapılandırır. Bu, kopyalama ve yapıştırma, verilerin dış yedeğini oluşturma ve uygulamalar arasında veri aktarma gibi işlemleri kısıtlayarak şirket verilerinizin güvenliğini artırmaya yardımcı olur.|[Microsoft Intune konsolunda mobil uygulama yönetimi ilkelerini yapılandırma ve dağıtma](/intune-classic/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)|
|iOS mobil uygulama yapılandırması|Mobil uygulama yapılandırma ilkelerini kullanarak, kullanıcı uygulamayı çalıştırdığında iOS uygulamaları için gerekebilecek ayarları sağlar. Örneğin, uygulama kullanıcının bağlantı noktası numarasını veya oturum açma bilgilerini belirtmesini isteyebilir. Bu, uygulama yapılandırmasını kolaylaştırmaya ve destek aramalarının sayısını azaltmaya yardımcı olabilir.|[iOS uygulamalarını Microsoft Intune’da mobil uygulama yapılandırma ilkeleriyle yapılandırma](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)|
|iOS mobil uygulaması sağlama profilleri|Süresi dolmak üzere olan iOS uygulamalarına sağlama profilleri dağıtmanıza yardımcı olur. |[Uygulamalarınızın süresinin dolmasını engellemek için iOS mobil sağlama profili ilkelerini kullanma](/intune-classic/deploy-use/ios-mobile-app-provisioning-profiles)|
|Yönetilen tarayıcı|Cihaz kullanıcılarının ziyaret edebileceği web sitelerini denetlemek için yönetilen tarayıcı profilleri yapılandırır. Ayrıca, yönetilen tarayıcıya mobil uygulama yönetimi ilkeleri de uygulayabilirsiniz.|[Microsoft Intune'la yönetilen tarayıcı ilkelerini kullanarak İnternet erişimini yönetme](/intune-classic/deploy-use/manage-internet-access-using-managed-browser-policies)|
|İş İçin Windows Hello|Parolaları, akıllı kartları ya da sanal akıllı kartları değiştirmek için Windows 10’da şirket içi Active Directory’nin veya Azure Active Directory’nin kullanıldığı alternatif bir oturum açma yöntemi olan İş İçin Windows Hello’yu tümleştirmenize olanak tanır.|[Microsoft Intune ile cihazlarda İş İçin Windows Hello ayarlarını denetleme](/intune-classic/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune)|
|Toplu satın alınan uygulamalar|Bir toplu satın alma programı aracılığıyla lisans bilgilerini uygulama mağazasından içeri aktararak, kaç lisans kullandığınızı izleyerek ve sahip olduğunuzdan fazla uygulama kopyası yüklemenizi önleyerek satın aldığınız uygulamaları yönetmenize yardımcı olur.|[Microsoft Intune kullanarak toplu satın alınan uygulamaları yönetme](/intune-classic/deploy-use/manage-volume-purchased-apps-in-microsoft-intune)|

## <a name="company-resource-access"></a>Şirket kaynak erişimi

|Özellik|Ayrıntılar|Daha fazla bilgi|
|--------------|-----------|--------------------|
|Sertifika profilleri|Güvenilen sertifika profilleri ve Basit Sertifika Kayıt Protokolü /intune-classic/deploy-use/secure-resource-access-with-certificate-profiles) oluşturur ve dağıtır|
|Wi-Fi profilleri|Kablosuz ağ ayarlarını kullanıcılarınıza dağıtır. Bu ayarları dağıtarak kurumsal ağa bağlanmak için gereken kullanıcı çabasını en aza indirirsiniz.|[Microsoft Intune’da Wi-Fi bağlantıları](/intune-classic/deploy-use/wi-fi-connections-in-microsoft-intune)|
|E-posta profilleri|E-posta ayarlarını oluşturur ve cihazlara dağıtır. Bu, kullanıcıların herhangi bir ayar yapmasına gerek kalmadan kişisel cihazlarından kurumsal e-postalara erişebilecekleri anlamına gelir.|[Microsoft Intune ile e-posta profilleri kullanarak şirket e-postasına erişimi yapılandırma](/intune-classic/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune)|
|VPN profilleri|VPN ayarlarını kuruluşunuzdaki kullanıcı ve cihazlara dağıtır. Bu ayarları dağıtarak, şirket ağındaki kaynaklara bağlanmak için gereken kullanıcı çabasını en aza indirirsiniz.|[Microsoft Intune’da VPN bağlantıları](/intune-classic/deploy-use/vpn-connections-in-microsoft-intune)|
|Koşullu erişim ilkeleri|Intune tarafından yönetilmeyen cihazların Microsoft Exchange e-posta ve SharePoint Online hizmetlerine erişimini yönetir.|[Microsoft Intune ile e-posta ve SharePoint erişimini kısıtlama](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)|

## <a name="inventory-and-reporting"></a>Envanter ve raporlama

|Özellik|Ayrıntılar|Daha fazla bilgi|
|--------------|-----------|--------------------|
|Envanter ve raporlama|Yönettiğiniz cihazlar ve cihazlarda kullanılan yazılımlar hakkında bilgiler bulur.|[Microsoft Intune’da envanterle cihazlarınızı anlama](/intune-classic/deploy-use/understand-your-devices-with-inventory-in-microsoft-intune)|

