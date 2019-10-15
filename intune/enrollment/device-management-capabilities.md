---
title: Microsoft Intune cihaz yönetimi özellikleri
description: Intune 'un kaydolduğunuzdan cihazları yönetmenize nasıl yardımcı olduğunu öğrenmek için bu konuyu okuyun.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/16/2019
ms.topic: conceptual
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
ms.openlocfilehash: bf862e59e135a875f5f18af731c581f3e5ea89d5
ms.sourcegitcommit: dd6755383ba89824d1cc128698a65fde6bb2de55
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/14/2019
ms.locfileid: "72306608"
---
# <a name="enrolled-device-management-capabilities-of-microsoft-intune"></a>Microsoft Intune kayıtlı cihaz yönetimi özellikleri

Microsoft Intune, bir dizi cihazı *hizmete kaydederek yönetmenize* olanak sağlar. Bazı cihaz türlerini kendiniz kaydedebilir veya kullanıcılar *Şirket portalı* uygulamasını kullanarak kaydedebilir. Kaydetme, uygulamalara gözatıp yüklemeye izin verir, cihazlarının şirket ilkeleriyle uyumlu olduğundan emin olun ve BT desteğiyle iletişim kurun.

Bu makale, cihazların kaydolduktan sonra elde ettiğiniz yeteneklerin tam bir listesini sağlar.

Yönetim, envanter, uygulama dağıtımı, sağlama ve kullanımdan kaldırma işlemleri Azure portal Intune aracılığıyla gerçekleştirilir.

Kullanıcılar şirket portalına erişebilir, bu sayede uygulamaları yüklemeleri, cihazları kaydetmek ve kaldırmak ve BT departmanlarına veya yardım masasına başvurmalarını sağlayabilirsiniz.



## <a name="device-security-and-configuration"></a>Cihaz güvenliği ve yapılandırması

|Özellik|Ayrıntılar|Daha fazla bilgi|
|--------------|-----------|--------------------|
|Yapılandırma ilkeleri<br><br>Özel ilkeler| Kuruluşunuzdaki mobil cihazlarda birçok ayarı ve özelliği yönetmenizi sağlar. Örneğin, parola isteyebilir, başarısız girişim sayısını sınırlayabilir, ekran kilitlenmeden önce geçen süreyi sınırlandırabilir, parola kullanım süresini ayarlayabilir ve daha önce kullanılmayan parolalara engel olabilirsiniz. Ayrıca cihaz Kamerası veya Web tarayıcısı gibi donanım ve yazılım özelliklerinin kullanımını da denetleyebilirsiniz.<br><br>Yapılandırma ilkeleri ihtiyaç duyduğunuz ayarları içermiyorsa özel ilkeleri kullanın. İOS cihazları için Apple Configurator aracından dışarı aktardığınız ayarları içeri aktarabilirsiniz. Diğer cihazlar için Open Mobile Alliance Tekdüzen Kaynak tanımlayıcısı (OMA-URI) ayarlarını kullanarak cihazdaki ayarları ve özellikleri yapılandırabilirsiniz.|[Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](../protect/device-compliance-get-started.md)|
|Uzaktan Temizleme, uzaktan kilitleme ve geçiş kodu sıfırlama|Bir cihaz kaybolduğunda veya çalındığında hassas verileri siler. Örneğin, cihazı uzaktan kilitleyebilir, fabrika ayarlarına geri yükleyebilir veya yalnızca kurumsal verileri temizleyebilirsiniz.<br><br>Kullanıcılar cihazlarına erişimi kaybederse, kayıp veya çalınmış cihazları kilitleyip hatta kaybolan veya çalınan cihazlardan verileri silerek geçiş kodlarını 'i sıfırlayabilirsiniz.|[Uzaktan kilitleme](../remote-actions/device-remote-lock.md) ve [geçiş kodu sıfırlama](../remote-actions/device-passcode-reset.md) ile cihazlarınızı korumaya yardımcı olma|
|Bilgi noktası modu|Mobil cihazların ekran yakalama ve güç anahtarları gibi bazı özelliklerini kilitlemenizi sağlar. Ayrıca, cihazları belirttiğiniz tek bir uygulamayı çalıştıracak şekilde kısıtlamanıza olanak tanır. |[Microsoft Intune 'de iOS yapılandırma ilkesi ayarları](../configuration/device-restrictions-ios.md)|
|Autopilot sıfırlaması|Sıfırlama işlemini uzaktan başlatmak için cihaza bir görev gönderir ve bu işlemi başlatmak için BT personelinin veya diğer yöneticilerin her bir makineyi ziyaret etmesini önler. Bir cihazda Autopilot Reset kullanıldığında, cihazın birincil kullanıcısı kaldırılır. Sıfırlamadan sonra oturum açan bir sonraki Kullanıcı, birincil kullanıcı olarak ayarlanır.|[Uzak Windows Autopilot sıfırlaması](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-reset#reset-devices-with-remote-windows-autopilot-reset)|

## <a name="app-management"></a>Uygulama yönetimi

|Özellik|Ayrıntılar|Daha fazla bilgi|
|--------------|-----------|--------------------|
|Uygulama dağıtımı ve yönetimi|, Yükleme dosyalarından ve uygulama mağazalarından uygulama dağıtımı, uygulama durumunu ayrıntılı olarak izleme ve uygulama kaldırma gibi yaşam döngülerinde mobil uygulamaları yönetmenize yardımcı olacak bir dizi araç sağlar.|[Uygulamaları Microsoft Intune dağıtma](../apps/apps-deploy.md)|
|Uyumlu ve uyumsuz uygulamalar|Uyumlu uygulamaların (Kullanıcıların yüklemesine izin verilen) ve uyumlu olmayan uygulamaların (Kullanıcıların yüklemesine izin verilmeyen) listelerini belirtmenizi sağlar.|[Microsoft Intune iOS ilke ayarları](../configuration/device-restrictions-ios.md)|
|Mobil uygulama yönetimi|Hem Intune ile yönetilen hem de Intune ile yönetilmeyen tüm cihazlarda mobil uygulama yönetimi 'ni kullanarak uygulamalar için kısıtlamalar yapılandırır. Kopyalama ve yapıştırma, verilerin dış yedeklemesi ve uygulamalar arasında veri aktarımı gibi işlemleri kısıtlayarak şirket verilerinizin güvenliğini artırabilirsiniz.|[Microsoft Intune konsolunda mobil uygulama yönetimi ilkelerini yapılandırma ve dağıtma](../developer/app-wrapper-prepare-android.md)|
|iOS mobil uygulama yapılandırması|, Kullanıcı uygulamayı çalıştırdığında gerekli olabilecek iOS uygulamalarına yönelik ayarları sağlamak için mobil uygulama yapılandırma ilkelerini kullanır. Örneğin, bir uygulama kullanıcının bir bağlantı noktası numarası veya oturum açma bilgisi belirtmesini gerektirebilir. Uygulama yapılandırmasını daha kolay hale getirebilirsiniz ve destek çağrılarının sayısını azaltabilirsiniz.|[İOS uygulamalarını Microsoft Intune 'de mobil uygulama yapılandırma ilkeleriyle yapılandırma](../apps/app-configuration-policies-use-ios.md)|
|iOS mobil uygulama sağlama profilleri|, Süresi dolmak üzere olan iOS uygulamalarına sağlama profilleri dağıtmanıza yardımcı olur. |[Uygulamalarınızın süresinin dolmasını engellemek için iOS mobil sağlama profili ilkelerini kullanın](../apps/app-provisioning-profile-ios.md)|
|Managed Browser|Cihaz kullanıcılarının ziyaret edebileceği web sitelerini denetlemek için yönetilen tarayıcı ilkelerini yapılandırır. Ayrıca, yönetilen tarayıcıya mobil uygulama yönetimi ilkeleri de uygulayabilirsiniz.|[Microsoft Intune ile yönetilen tarayıcı ilkelerini kullanarak Internet erişimini yönetme](../apps/app-configuration-managed-browser.md)|
|İş İçin Windows Hello|Windows 10 ' da, parola, akıllı kartlar veya sanal akıllı kartları değiştirmek için şirket içi Active Directory veya Azure Active Directory kullanan alternatif bir oturum açma yöntemi olan Iş için Windows Hello ile tümleştirmenize olanak sağlar.|[Microsoft Intune ile cihazlarda Iş için Windows Hello ayarlarını denetleme](../protect/windows-hello.md)|
|Toplu satın alınan uygulamalar|, Lisans bilgilerini uygulama mağazasından içeri aktararak, kaç lisans kullandığını izleyerek ve sahip olduğunuz uygulamanın daha fazla kopyasını yüklemenizi önleyerek, toplu satın alma programı aracılığıyla satın aldığınız uygulamaları yönetmenize yardımcı olur.|[Microsoft Intune kullanarak toplu satın alınan uygulamaları yönetme](../apps/vpp-apps.md)|

## <a name="company-resource-access"></a>Şirket kaynağına erişim

|Özellik|Ayrıntılar|Daha fazla bilgi|
|--------------|-----------|--------------------|
|Sertifika profilleri|Wi-Fi, VPN ve e-posta profillerinin güvenliğini sağlamak ve kimliğini doğrulamak için kullanılabilen, güvenilen sertifika profilleri ve Basit Sertifika Kayıt Protokolü (SCEP) sertifikaları oluşturur ve dağıtır.|[Microsoft Intune’da sertifika profilleriyle güvenli kaynak erişimi](../protect/certificates-configure.md)|
|Wi-Fi profilleri|Kullanıcılarınıza kablosuz ağ ayarlarını dağıtır. Bu ayarları dağıtarak, kurumsal ağa bağlanmak için gereken Kullanıcı çabalarını en aza indirmiş olursunuz.|[Microsoft Intune’da Wi-Fi bağlantıları](../configuration/wi-fi-settings-configure.md)|
|E-posta profilleri|Kullanıcıların kendi bölümünde herhangi bir kurulum yapması gerekmeden kişisel cihazlarında Şirket e-postasına erişebilmeleri için cihazlara e-posta ayarları oluşturur ve dağıtır.|[Microsoft Intune ile e-posta profillerini kullanarak kurumsal e-postaya erişim yapılandırma](../configuration/email-settings-configure.md)|
|VPN profilleri|VPN ayarlarını kuruluşunuzdaki kullanıcılara ve cihazlara dağıtır. Bu ayarları dağıtarak, şirket ağındaki kaynaklara bağlanmak için gereken Kullanıcı çabalarını en aza indirmiş olursunuz.|[Microsoft Intune’da VPN bağlantıları](../configuration/device-profiles.md#vpn)|
|Koşullu erişim ilkeleri|Intune tarafından yönetilmeyen cihazlardan Microsoft Exchange e-posta ve SharePoint Online erişimini yönetir.|[Microsoft Intune ile e-posta ve SharePoint erişimini kısıtlama](../protect/app-based-conditional-access-intune.md)|

## <a name="next-steps"></a>Sonraki adımlar

[Yönetebileceğiniz cihazların listesini görüntüleyin](../remote-actions/device-management.md).
