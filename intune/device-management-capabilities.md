---
title: Microsoft Intune cihaz yönetimi özellikleri
description: Intune’un kaydettiğiniz cihazları yönetmenize nasıl yardımcı olabileceğini öğrenmek için bu konuyu okuyun.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/16/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 293fa40b59d0005f60aad45a3fc42d3dd790857d
ms.sourcegitcommit: acf4c36619fc7a068a751c88343978ce749b668c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/13/2019
ms.locfileid: "59551694"
---
# <a name="enrolled-device-management-capabilities-of-microsoft-intune"></a>Microsoft Intune’un kayıtlı cihaz yönetimi özellikleri

Microsoft Intune bir dizi cihazı hizmete *kaydederek* yönetmenize olanak tanır. Bazı cihaz türlerini kendiniz kaydedebilirsiniz veya kullanıcılar *şirket portalı* uygulamasını kullanarak kaydedebilir. Kaydetme göz atın ve uygulamaları yüklemek, cihazlarını şirket ilkeleriyle uyumlu olduğundan emin olun ve BT desteğine başvurun olanak tanır.

Bu makalede, cihazlar kaydedildikten sonra elde özelliklerinin tam listesini sağlar.

Yönetim, Envanter, uygulama dağıtımı, sağlama ve kullanımdan kaldırma gerçekleştirilir Intune aracılığıyla Azure portalında.

Kullanıcılar uygulamaları yüklemek, cihazlarını kaydetmek veya kaydı kaldırmak ve BT departmanına ya da yardım masasına başvurmak için şirket portalına erişim kazanır.



## <a name="device-security-and-configuration"></a>Cihaz güvenliği ve yapılandırma

|Özellik|Ayrıntılar|Daha fazla bilgi|
|--------------|-----------|--------------------|
|Yapılandırma ilkeleri<br><br>Özel ilkeler| Kuruluşunuzdaki mobil cihazlarda birçok ayar ve özelliği yönetmenizi sağlar. Örneğin, parola isteyebilir, başarısız oturum açma girişimlerinin sayısını sınırlandırabilir, ekranın kilitlenmesinden önceki süreyi sınırlandırabilir, parola sona erme süresini ayarlayabilir ve daha önce kullanılan parolaların kullanımını engelleyebilirsiniz. Ayrıca cihaz kamerası veya web tarayıcısı gibi donanım ve yazılım özelliklerinin kullanımını da denetleyebilirsiniz.<br><br>Yapılandırma ilkeleri ihtiyaç duyduğunuz ayarları içermiyorsa özel ilkeleri kullanın. iOS cihazları için Apple Yapılandırıcı aracından dışarı aktarılan ayarları alabilirsiniz. Diğer cihazlar için Open Mobile Alliance Uniform Resource Identifier (OMA-URI) ayarlarını kullanarak cihazdaki ayarları ve özellikleri yapılandırabilirsiniz.|[Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](device-compliance-get-started.md)|
|Uzaktan Temizleme, Uzak Kilit ve Parola Sıfırlama|Bir cihaz kaybolur veya çalınırsa hassas verileri siler. Örneğin, cihazı uzaktan kilitleyebilir, fabrika ayarlarına sıfırlayabilir veya yalnızca kurumsal verileri temizleyebilirsiniz.<br><br>Kullanıcılar cihazlarına erişimi kaybederse geçiş kodlarını sıfırlayabilir, kaybolan veya çalınan cihazları kilitleyebilir ve hatta kaybolan ya da çalınan cihazların verilerini temizleyebilirsiniz.|Özellikleriyle cihazlarınızın korunmasına yardımcı [uzaktan kilitleme](device-remote-lock.md) ve [geçiş kodunu sıfırlama](device-passcode-reset.md)|
|Bilgi noktası modu|Mobil cihazların ekran yakalama ve güç düğmesi gibi belirli özelliklerini kilitlemenizi sağlar. Ayrıca, cihazları belirttiğiniz tek bir uygulamayı çalıştıracak şekilde kısıtlamanıza olanak tanır. |[Microsoft Intune’da iOS yapılandırma ilkesi ayarları](device-restrictions-ios.md)|

## <a name="app-management"></a>Uygulama yönetimi

|Özellik|Ayrıntılar|Daha fazla bilgi|
|--------------|-----------|--------------------|
|Uygulama dağıtımı ve yönetimi|Mobil uygulamaları kurulum dosyalarından ve uygulama mağazalarından uygulama dağıtma, uygulama durumunun ayrıntılı bir şekilde izlenmesi ve uygulama kaldırma dahil yaşam döngüsü boyunca yönetmenize yardımcı olmak için çeşitli araçlar sağlar.|[Microsoft Intune'da uygulamaları dağıtma](apps-deploy.md)|
|Uyumlu ve uyumlu olmayan uygulamalar|Uyumlu uygulamaların (kullanıcıların yüklemesine izin verilen uygulamalar) ve uyumlu olmayan uygulamaların (kullanıcıların yüklemesine izin verilmeyen uygulamalar) listelerini belirtmenizi sağlar.|[Microsoft Intune’da iOS ilke ayarları](device-restrictions-ios.md)|
|Mobil uygulama yönetimi|Mobil uygulama yönetimini kullanarak, hem Intune tarafından yönetilen hem de yönetilmeyen tüm cihazlarda uygulamalar için kısıtlamaları yapılandırır. Kopyalama ve yapıştırma, verilerin dış yedeğini ve uygulamalar arasında veri aktarımı gibi işlemleri kısıtlayarak şirket verilerinizin güvenliğini artırabilirsiniz.|[Microsoft Intune konsolunda mobil uygulama yönetimi ilkelerini yapılandırma ve dağıtma](app-wrapper-prepare-android.md)|
|iOS mobil uygulama yapılandırması|Mobil uygulama yapılandırma ilkelerini kullanarak, kullanıcı uygulamayı çalıştırdığında iOS uygulamaları için gerekebilecek ayarları sağlar. Örneğin, uygulama kullanıcının bağlantı noktası numarasını veya oturum açma bilgilerini belirtmesini isteyebilir. Uygulama yapılandırmasını kolaylaştırmaya ve Destek aramalarının sayısını azaltın.|[iOS uygulamalarını Microsoft Intune’da mobil uygulama yapılandırma ilkeleriyle yapılandırma](app-configuration-policies-use-ios.md)|
|iOS mobil uygulaması sağlama profilleri|Süresi dolmak üzere olan iOS uygulamalarına sağlama profilleri dağıtmanıza yardımcı olur. |[Uygulamalarınızın süresinin dolmasını engellemek için iOS mobil sağlama profili ilkelerini kullanma](app-provisioning-profile-ios.md)|
|Yönetilen tarayıcı|Cihaz kullanıcılarının ziyaret edebileceği web sitelerini denetlemek için yönetilen tarayıcı profilleri yapılandırır. Ayrıca, yönetilen tarayıcıya mobil uygulama yönetimi ilkeleri de uygulayabilirsiniz.|[Microsoft Intune'la yönetilen tarayıcı ilkelerini kullanarak İnternet erişimini yönetme](app-configuration-managed-browser.md)|
|İş İçin Windows Hello|Parolaları, akıllı kartları ya da sanal akıllı kartları değiştirmek için Windows 10’da şirket içi Active Directory’nin veya Azure Active Directory’nin kullanıldığı alternatif bir oturum açma yöntemi olan İş İçin Windows Hello’yu tümleştirmenize olanak tanır.|[Microsoft Intune ile cihazlarda İş İçin Windows Hello ayarlarını denetleme](windows-hello.md)|
|Toplu satın alınan uygulamalar|Bir toplu satın alma programı aracılığıyla lisans bilgilerini uygulama mağazasından içeri aktararak, kaç lisans kullandığınızı izleyerek ve sahip olduğunuzdan fazla uygulama kopyası yüklemenizi önleyerek satın aldığınız uygulamaları yönetmenize yardımcı olur.|[Microsoft Intune kullanarak toplu satın alınan uygulamaları yönetme](vpp-apps.md)|

## <a name="company-resource-access"></a>Şirket kaynak erişimi

|Özellik|Ayrıntılar|Daha fazla bilgi|
|--------------|-----------|--------------------|
|Sertifika profilleri|Wi-Fi, VPN ve e-posta profillerini güvenli hale getirmek ve kimlik doğrulaması yapmak için kullanılabilen güvenli sertifika profilleri ve Basit Sertifika Kaydı Profilleri (SCEP) sertifikaları oluşturur ve dağıtır.|[Microsoft Intune’da sertifika profilleriyle güvenli kaynak erişimi](certificates-configure.md)|
|Wi-Fi profilleri|Kablosuz ağ ayarlarını kullanıcılarınıza dağıtır. Bu ayarları dağıtarak kurumsal ağa bağlanmak için gereken kullanıcı çabasını en aza indirirsiniz.|[Microsoft Intune’da Wi-Fi bağlantıları](wi-fi-settings-configure.md)|
|E-posta profilleri|Oluşturur ve kullanıcıların herhangi bir kurulum yapmalarına gerek kalmadan kişisel cihazlarından Kurumsal e-posta erişebilmesi için e-posta ayarlarını cihazlara dağıtır.|[Microsoft Intune ile e-posta profilleri kullanarak şirket e-postasına erişimi yapılandırma](email-settings-configure.md)|
|VPN profilleri|VPN ayarlarını kuruluşunuzdaki kullanıcı ve cihazlara dağıtır. Bu ayarları dağıtarak, şirket ağındaki kaynaklara bağlanmak için gereken kullanıcı çabasını en aza indirirsiniz.|[Microsoft Intune’da VPN bağlantıları](device-profiles.md#vpn)|
|Koşullu erişim ilkeleri|Intune tarafından yönetilmeyen cihazların Microsoft Exchange e-posta ve SharePoint Online hizmetlerine erişimini yönetir.|[Microsoft Intune ile e-posta ve SharePoint erişimini kısıtlama](app-based-conditional-access-intune.md)|

## <a name="next-steps"></a>Sonraki adımlar

[Yönettiğiniz cihazların listesini görmek](device-management.md).
