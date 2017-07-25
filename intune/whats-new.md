---
title: Microsoft Intune'daki yenilikler
titleSuffix: Intune on Azure
description: "Intune Azure portalındaki yenilikleri keşfedin"
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 07/13/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dec4fb1d373f49c1f6c15b1f2a9acb2f8d20138d
ms.sourcegitcommit: be12974a7eaa4ce9cffe45aabe456c858d582e20
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/14/2017
---
# <a name="whats-new-in-microsoft-intune"></a>Microsoft Intune'daki yenilikler

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Microsoft Intune’daki haftalık yenilikleri öğrenin. [Yaklaşan değişiklikler](#whats-coming), hizmet hakkında [önemli bildirimler](#notices) ve [geçmiş sunumlar](whats-new-archive.md) hakkında bilgiler de alabilirsiniz.

> [!Note]
> Bu özelliklerin birçoğu, sonunda Configuration Manager ile karma müşteri dağıtımlarında desteklenecektir. Yeni karma özellikler hakkında daha fazla bilgi için, [Karma Yenilikler sayfamızı](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) gözden geçirin.


<!-- Common categories:  
  ### Role-based access control
  ### Device enrollment
  ### Device management
  ### App management
  ### Device configuration
-->   



## <a name="week-of-june-26th-2017"></a>26 Haziran 2017 haftası

### <a name="role-based-access-control"></a>Rol tabanlı erişim denetimi
#### <a name="new-role-based-administration-access-for-intune-admins------1099990---"></a>Intune yöneticileri için yeni rol tabanlı yönetim erişimi   <!-- 1099990 -->  
Azure AD Koşullu Erişim ilkelerini görüntülemek, oluşturmak, değiştirmek ve silmek için yeni bir koşullu erişim yönetim rolü ekleniyor. Daha önce yalnızca genel yöneticiler ve güvenlik yöneticileri bu izne sahipti. Koşullu erişim ilkelerine erişebilmeleri için Intune yöneticilerine bu rolün izinleri verilebilir.


### <a name="device-enrollment"></a>Cihaz kaydı
#### <a name="tag-corporate-owned-devices-with-serial-number----1215070---"></a>Şirkete ait cihazları seri numarasıyla etiketleme <!-- 1215070 -->  
Intune artık iOS, macOS ve Android seri numaralarını Kurumsal Cihaz Tanımlayıcıları olarak karşıya yüklemeyi destekliyor. Seri numaralar kayıt sırasında doğrulanmadığı için bu numaraları henüz kişisel cihazların kaydedilmesini engellemek için kullanamazsınız. Kişisel cihazları seri numarasına göre engelleme, yakın bir gelecekte çıkacak.


### <a name="device-management"></a>Cihaz yönetimi
#### <a name="new-remote-actions-for-ios-devices----854689---"></a>iOS cihazları için yeni uzak eylemler <!-- 854689 -->
Bu sürümde, Apple Classroom uygulamasını yöneten paylaşılan iPad cihazlar için iki yeni uzak cihaz eylemi ekledik:

-   [Geçerli kullanıcının oturumunu kapat](device-logout-user.md) - Seçtiğiniz bir iOS cihazının geçerli kullanıcısının oturumunu kapatır.
-   [Kullanıcı kaldır](device-remove-user.md) - Bir iOS cihazdaki yerel önbellekten seçtiğiniz bir kullanıcıyı siler.


#### <a name="support-for-shared-ipads-with-the-ios-classroom-app----1044681---"></a>iOS Classroom uygulaması ile paylaşılan iPad'ler için destek <!-- 1044681 -->
Bu sürümde, iOS Classroom uygulamasının kapsamını, paylaşılan iPad’lerde yönetilen Apple kimliklerini kullanarak oturum açan öğrencileri de içerecek şekilde genişlettik.


### <a name="app-management"></a>Uygulama yönetimi  

#### <a name="changes-to-intune-built-in-apps----1332306---"></a>Intune yerleşik uygulamalarındaki yenilikler <!-- 1332306 -->

Eskiden Intune’da hızlıca atayabileceğiniz birkaç yerleşik uygulama vardı. Geri bildirimlerinize dayanarak bu listeyi kaldırdık, artık yerleşik uygulamaları görmeyeceksiniz.
Ancak herhangi bir yerleşik uygulamayı önceden atadıysanız bu uygulamalar, uygulama listesinde görünmeye devam edecektir. Bu cihazları gerektiği gibi atamaya devam edebilirsiniz.
Sonraki bir sürümde, Intune portalında uygulama seçme ve atama için daha kolay bir yöntem eklemeyi planlıyoruz.


#### <a name="support-for-offline-apps-from-the-windows-store-for-business-----777044----"></a>İş İçin Windows Mağazası uygulamaları için çevrimdışı desteği <!--- 777044 --->
İş İçin Windows Mağazası'ndan satın aldığınız çevrimdışı uygulamalar, artık Intune portalına eşitlenecektir. Daha sonra bu uygulamaları cihaz gruplarına veya kullanıcı gruplarına dağıtabilirsiniz. Çevrimdışı uygulamalar, mağaza tarafından değil Intune tarafından yüklenir.

#### <a name="microsoft-teams-is-now-part-of-the-app-based-ca-list-of-approved-apps------1257019---"></a>Microsoft Teams artık onaylı uygulamaların Uygulama temelli CA listesinin bir parçasıdır   <!-- 1257019 -->

iOS ve Android için Microsoft Teams uygulaması artık Exchange ve SharePoint Online için uygulama tabanlı koşullu erişim ilkeleri onaylı uygulamalarının bir parçasıdır. Uygulamayı, uygulama tabanlı koşullu erişim kullanmakta olan tüm kiracıların Azure portalındaki Intune Uygulama Koruması dikey penceresinde yapılandırabilirsiniz.

#### <a name="managed-browser-and-app-proxy-integration----1287310---"></a>Managed Browser ve uygulama proxy’si tümleştirmesi <!-- 1287310 -->
 Intune Managed Browser artık Azure AD Uygulama Proxy’si hizmeti ile tümleştirilebilir ve bu sayede kullanıcılar uzaktan çalışsalar bile dahili web sitelerine erişebilirler. Tarayıcıyı kullanırken her zaman yaptığınız gibi site URL’sini girmeniz yeterlidir, Managed Browser bu isteği uygulama proxy’si web ağ geçidine yönlendirecektir. Daha fazla bilgi için bkz. [Managed Browser ilkeleri kullanarak İnternet erişimini yönetme](app-configuration-managed-browser.md).


#### <a name="new-app-configuration-settings-for-the-intune-managed-browser----682951---"></a>Intune'la Managed Browser için yeni uygulama ayarları <!-- 682951 -->
Bu sürümde, iOS ve Android için Intune Managed Browser uygulamasına ilave yapılandırmalar ekledik. Artık tarayıcının varsayılan giriş sayfasını ve yer işaretlerini yapılandırmak için bir uygulama yapılandırma ilkesi kullanabilirsiniz.
Daha fazla bilgi için bkz. [Managed Browser ilkeleri kullanarak İnternet erişimini yönetme](app-configuration-managed-browser.md)




### <a name="device-configuration"></a>Cihaz yapılandırması  
#### <a name="bitlocker-settings-for-windows-10-----951707---"></a>Windows 10 için BitLocker ayarları <!-- 951707 -->
Artık yeni bir Intune cihaz profili kullanarak Windows 10 cihazlar için BitLocker ayarlarını yapılandırabilirsiniz. Örneğin cihazların şifreli olmasını gerekli kılabilir ve BitLocker açık olduğunda uygulanacak başka ayarlar da yapılandırabilirsiniz.
Daha fazla bilgi için bkz. [Windows 10 ve üzeri sürümler için Endpoint Protection ayarları](endpoint-protection-windows-10.md).

### <a name="new-settings-for-windows-10-device-restriction-profile-----978527--978550-978569-1050031-1058611-----"></a>Windows 10 cihaz kısıtlama profili için yeni ayarlar <!--- 978527,  978550, 978569, 1050031, 1058611,  --->

Bu sürümde, Windows 10 cihaz kısıtlama profili için aşağıdaki kategorilere yeni ayarlar ekledik:

 -  Windows Defender
-  Hücresel ve bağlantı
-  Kilit ekranı deneyimi
-  Gizlilik
-  Ara
-  Windows Spot
-  Edge tarayıcısı

Windows 10 ayarları hakkında daha fazla bilgi için bkz. [Windows 10 ve üzeri sürümler için cihaz kısıtlama ayarları](device-restrictions-windows-10.md).

## <a name="week-of-june-12-2017"></a>12 Haziran 2017 haftası

### <a name="company-portal-app-for-android-now-has-a-new-end-user-experience-for-app-protection-policies---1305217--"></a>Android için Şirket Portalı uygulamasının artık Uygulama Koruma İlkeleri için yeni bir son kullanıcı deneyimi vardır <!--1305217-->
Müşteri geri bildirimi doğrultusunda, Android için Şirket Portalı uygulamasını bir **Şirket İçeriğine Eriş** düğmesi gösterecek şekilde değiştirdik. Amaç, son kullanıcıların yalnızca, Intune mobil uygulama yönetiminin bir özelliği olan Uygulama Koruma İlkelerini destekleyen uygulamalara erişmek için gereksiz yere kayıt işlemi yapmalarını engellemektir. Bu değişiklikleri, [uygulama kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md) sayfasında görebilirsiniz.

### <a name="new-menu-action-to-easily-remove-company-portal---1164569--"></a>Şirket Portalını kolayca kaldırmak için yeni menü eylemi <!--1164569-->
Kullanıcı geri bildirimi doğrultusunda, Android için Şirket Portalı uygulaması, Şirket Portalını cihazınızdan kaldırmak için yeni bir menü eylemi ekledi. Bu eylem cihazı Intune yönetiminden kaldırır, böylece uygulama cihazdan kullanıcı tarafından kaldırılabilir. Bu değişiklikleri [Uygulamanın kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md) sayfasında ve [Android son kullanıcı belgelerinde](/intune-user-help/unenroll-your-device-from-intune-android) görebilirsiniz.

### <a name="improvements-to-app-syncing-with-windows-10-creators-update---676505--"></a>Windows 10 Creators Güncelleştirmesi ile uygulama eşitleme geliştirmeleri <!--676505-->

Windows 10 için Şirket Portalı uygulaması, Windows 10 Creators Update (sürüm 1703) içeren cihazlarda uygulama yükleme istekleri için eşitlemeyi artık otomatik olarak başlatacak. Bu, “Eşitleme Bekleniyor” durumu sırasında bekletilen uygulama yüklemeleri sorununu azaltacak. Buna ek olarak, kullanıcılar uygulamanın içinden el ile eşitleme başlatabilecek. Bu değişiklikleri, [uygulama kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md) sayfasında görebilirsiniz.

### <a name="new-guided-experience-for-windows-10-company-portal----1058938---"></a>Windows 10 Şirket Portalı için kullanıcının yönlendirildiği yeni deneyim <!---1058938--->

Windows 10 için Şirket Portalı uygulaması, tanımlanmamış veya kaydedilmemiş cihazlar için kullanıcının adım adım yönlendirildiği bir Intune deneyimi içerecek. Yeni deneyim, kullanıcıya Azure Active Directory kaydı sürecinde (Koşullu Erişim özelliklerinde gereklidir) ve MDM kaydı sürecinde (cihaz yönetim özellikleri için gereklidir) kılavuzluk eden adım adım yönergeler sağlıyor. Kılavuzluk destekli deneyime Şirket Portalı giriş sayfasından erişilebilecek. Kullanıcılar, cihaz kaydettirme ve kaydolma işlemlerini tamamlamasa da uygulamayı kullanmaya devam edebilecek, ancak sınırlı bir işlevsellikleri olacak.

Bu güncelleştirme yalnızca Windows 10 Yıldönümü Güncelleştirmesi (derleme 1607) veya üzerini çalıştıran cihazlarda görünür. Bu değişiklikleri, [uygulama kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md) sayfasında görebilirsiniz.

## <a name="week-of-june-5-2017"></a>5 Haziran 2017 haftası

### <a name="microsoft-intune-and-conditional-access-admin-consoles-are-generally-available"></a>Microsoft Intune ve Koşullu Erişim yönetici konsolları genel olarak kullanılabilir

Azure’da Intune yönetici konsolu ve Koşullu Erişim yönetici konsolunun genel olarak kullanılabilir olduğunu duyuruyoruz. Azure’da Intune aracılığıyla, artık tüm Intune MAM ve MDM özelliklerini birleştirilmiş tek bir yönetim deneyiminde yönetebilir ve Azure AD gruplandırma ve hedefleme özelliğinden yararlanabilirsiniz. Azure’da koşullu erişim, Azure AD ve Intune’daki zengin özellikleri birleştirilmiş bir konsol ile bir araya getirir. Yönetim deneyimi açısından ise Azure platformuna geçmek modern tarayıcıları kullanmanıza olanak tanır.

Intune artık portal.azure.com adresindeki Azure konsolunda **önizleme** etiketi olmadan da görünür durumdadır.

İleti merkezinde gruplarınızın geçişini yapmamız için eylemde bulunmanızı isteyen ileti serilerinden birini almadıysanız şu anda mevcut müşterilerin yapması gereken bir eylem yoktur. Tarafımızdaki hatalardan dolayı geçişinizin daha uzun sürdüğünü belirten bir ileti merkezi bildirimi de almış olabilirsiniz. Etkilenen tüm müşterilerin geçişini tamamlamak üzere titizlikle çalışmaya devam ediyoruz.

### <a name="improvements-to-the-app-tiles-in-the-company-portal-app-for-ios"></a>iOS için Şirket Portalı uygulamasındaki uygulama kutucukları geliştirmeleri
Şirket Portalı için ayarladığınız marka rengini yansıtmak için giriş sayfasındaki uygulama kutucuklarının tasarımı güncelleştirildi. Daha fazla bilgi için bkz. [Uygulamanın kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md).

### <a name="account-picker-now-available-for-the-company-portal-app-for-ios"></a>iOS Şirket Portalı uygulaması için artık hesap seçici kullanılabilir
iOS cihazı kullanıcıları diğer Microsoft uygulamalarında oturum açmak için iş veya okul hesaplarını kullanıyorsa Şirket Portalı uygulamasında oturum açtıklarında yeni hesap seçiciyi görebilirler. Daha fazla bilgi için bkz. [Uygulamanın kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md).

## <a name="week-of-may-29-2017"></a>29 Mayıs 2017 haftası

### <a name="change-your-mdm-authority-without-unenrolling-managed-devices---1103950--"></a>Yönetilen cihazların kaydını kaldırmadan MDM yetkilinizi değiştirme <!--1103950-->

Artık Microsoft Desteği’ne başvurmak ve mevcut yönetilen cihazlarınızın kaydını kaldırıp yeniden kaydetmek zorunda kalmadan MDM yetkilinizi değiştirebilirsiniz. Configuration Manager konsolunda, [MDM yetkilinizi değiştirerek](/sccm/mdm/deploy-use/change-mdm-authority) Configuration Manager’a Ayarla (karma) ile Microsoft Intune (tek başına) seçenekleri arasında geçiş yapabilirsiniz.


### <a name="improved-notification-for-samsung-knox-startup-pins---1087143--"></a>Samsung KNOX başlangıç PIN’leri için geliştirilmiş bildirim <!--1087143-->
Şifrelemeyle uyumlu olması için son kullanıcıların Samsung KNOX cihazlarında başlangıç PIN’i ayarlamaları gerektiğinde, son kullanıcılara gösterilen bildirime dokunulduğunda bildirimleri Ayarlar uygulamasında doğru yere yerleştirir.  Daha önce, bildirim son kullanıcıyı parola değiştirme ekranına getiriyordu.


### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="apple-school-manager-asm-support-with-shared-ipad----748864-770395--"></a>Paylaşılan iPad ile Apple School Manager (ASM) desteği <!-- 748864, 770395-->

Intune, iOS cihazlarında hazır kayıt sağlamak için Apple Aygıt Kayıt Programı yerine artık Apple School Manager’ı (ASM) destekler. Paylaşılan iPad’lerde Classroom uygulamasını kullanmak ve Microsoft School Data Sync (SDS) yoluyla ASM’den Azure Active Directory’ye veri eşitlemeyi etkinleştirmek için ASM’nin kullanıma alınması gereklidir. Daha fazla bilgi için bkz. [Apple School Manager ile iOS cihaz kaydını etkinleştirme](apple-school-manager-set-up-ios.md).

> [!NOTE]
> Paylaşılan iPad’leri Classroom uygulaması ile birlikte çalışmak üzere yapılandırmak Azure’da henüz kullanılamayan iOS Eğitim yapılandırmaları gerektirir.  Bu işlev yakında eklenecektir.

### <a name="device-management"></a>Cihaz yönetimi

#### <a name="provide-remote-assistance-to-android-devices-using-teamviewer----675418---"></a>TeamViewer kullanarak Android cihazları için uzaktan yardım sağlama <!-- 675418 -->

Intune, Android cihaz çalıştıran kullanıcılarınıza uzaktan yardım etmenizi sağlamak için artık ayrı satın alınan [TeamViewer](https://www.teamviewer.com) yazılımını kullanabilir. Daha fazla bilgi için bkz. [Intune ile yönetilen Android cihazlar için uzaktan yardım sağlama](device-profile-android-teamviewer.md).

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="new-app-protection-policies-conditions-for-mam----679864---"></a>MAM için yeni uygulama koruma ilkesi koşulları <!-- 679864 -->

Artık kayıt kullanıcıları olmadan MAM için aşağıdaki ilkeleri zorunlu tutan bir gereksinim ayarlayabilirsiniz:

- En düşük uygulama sürümü
- En düşük işletim sistemi sürümü
- Hedeflenen uygulamanın en düşük Intune APP SDK’sı sürümü (yalnızca iOS)

Bu özellik hem Android hem de iOS’ta kullanılabilir. Intune; işletim sistemi platformu sürümleri, uygulama sürümleri ve Intune APP SDK’sı için en düşük sürüm zorlamasını destekler. iOS’ta, SDK’nın tümleştirildiği uygulamalar da SDK düzeyinde en düşük sürüm zorlaması ayarlayabilir. Yukarıda açıklanan üç farklı düzeyde uygulama koruma ilkesi aracılığıyla belirlenen en düşük gereksinimler karşılanmazsa kullanıcı hedeflenen uygulamaya erişemez. Bu noktada, kullanıcı hesabını kaldırabilir (çok kimlikli uygulamalarda), uygulamayı kapatabilir veya işletim sistemi veya uygulama sürümünü güncelleştirebilir.

İşletim sistemi veya uygulama yükseltmesi öneren ve engelleyici olmayan bir bildirim sağlamak için ek ayarlar da yapılandırabilirsiniz. Bu bildirim kapatılabilir ve uygulama normal şekilde kullanılabilir.

Daha fazla bilgi için bkz. [iOS uygulama koruma ilkesi ayarları](app-protection-policy-settings-ios.md) ve [Android uygulama koruma ilkesi ayarları](app-protection-policy-settings-android.md).

#### <a name="configure-app-configurations-for-android-for-work----621621---"></a>Android for Work için uygulama yapılandırmaları ayarlayın <!-- 621621 -->
Mağazadaki bazı Android uygulamaları, bir BT yöneticisinin bir uygulamanın iş profilinde nasıl çalışacağını denetlemesine izin veren yönetilen yapılandırma seçeneklerini destekler. Intune ile artık bir uygulama tarafından desteklenen yapılandırmaları görüntüleyebilir ve bunları bir yapılandırma tasarımcısı veya JSON düzenleyicisi ile Intune portalından yapılandırabilirsiniz. Daha fazla bilgi için bkz. [Android for Work için uygulama yapılandırmaları kullanma](app-configuration-policies-use-android.md).

#### <a name="new-app-configuration-capability-for-mam-without-enrollment----677969---"></a>Kayıt olmadan MAM için yeni uygulama yapılandırma özelliği <!-- 677969 -->

Artık kayıt kanalı olmadan MAM ile uygulama yapılandırma ilkeleri oluşturabilirsiniz. Bu özellik, mobil cihaz yönetimi (MDM) uygulama yapılandırmasında kullanılabilir uygulama yapılandırma ilkelerine eşdeğerdir. Kayıt olmadan MAM kullanılan uygulama yapılandırması örneği için bkz. [Microsoft Intune'la Managed Browser ilkelerini kullanarak İnternet erişimini yönetme](app-configuration-managed-browser.md).

#### <a name="configure-allowed-and-blocked-url-lists-for-the-managed-browser----682960---"></a>Managed Browser için izin verilen ve engellenen URL listelerini yapılandırma <!-- 682960 -->

Artık Azure portalındaki uygulama yapılandırma ayarlarını kullanarak Intune Managed Browser için izin verilen ve engellenen etki alanları ve URL’ler listesi yapılandırabilirsiniz. Bu ayarlar yönetilen bir cihazda mı yoksa yönetilmeyen bir cihazda mı kullanıldığına bakılmaksızın yapılandırılabilir. Daha fazla bilgi için bkz. [Microsoft Intune'la Managed Browser ilkelerini kullanarak İnternet erişimini yönetme](app-configuration-managed-browser.md).

#### <a name="app-protection-policy-helpdesk-view----1069473---"></a>Uygulama koruma ilkesi yardım masası görünümü <!-- 1069473 -->

BT Yardım Masası kullanıcıları, artık kullanıcı lisans durumu ve Sorun Giderme dikey penceresinde kullanıcılara atanan uygulama koruma ilkesi uygulamalarının durumunu denetleyebilir. Ayrıntılar için bkz. [Sorun giderme](./help-desk-operators.md).

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="control-website-visits-on-ios-devices----723832---"></a>iOS cihazlarda web sitesi ziyaretlerini denetleme <!-- 723832 -->

iOS cihazı kullanıcılarının ziyaret edebileceği web sitelerini aşağıdaki iki yöntemden birini kullanarak denetleyebilirsiniz:

- Apple'ın yerleşik web içeriği filtresini kullanarak izin verilen ve engellenen URL'leri ekleyin.

- Safari tarayıcısı tarafından yalnızca belirli web sitelerine erişilmesine izin verin. Belirttiğiniz siteler için Safari'de yer işaretleri oluşturulur.

Daha fazla bilgi için bkz. [iOS cihazları için web içeriği filtresi ayarları](web-content-filter-settings-ios.md).

#### <a name="preconfigure-device-permissions-for-android-for-work-apps----621614---"></a>Android for Work uygulamaları için cihaz izinlerini önceden yapılandırma <!-- 621614 -->

Android for Work cihazı iş profillerine dağıtılan uygulamalarda, artık tek tek uygulamalar için izin durumunu yapılandırabilirsiniz.  Varsayılan olarak, konuma veya cihaz kamerasına erişim gibi cihaz izinlerine ihtiyacı olan Android uygulamaları kullanıcıdan izinleri kabul etmesini veya reddetmesini ister.  Örneğin, uygulama cihazın mikrofonunu kullanıyorsa, son kullanıcıdan mikrofonu kullanmak için uygulamaya izin vermesi istenir. Bu özellik, son kullanıcılar için izinleri tanımlamanıza olanak tanır.  İzinleri a) kullanıcıya bildirimde bulunmadan otomatik olarak reddedilecek şekilde b) kullanıcıya bildirimde bulunmadan otomatik olarak onaylanacak şekilde veya c) kullanıcıya kabul etmesi veya reddetmesi için sorulacak şekilde yapılandırabilirsiniz. Daha fazla bilgi için bkz. [Microsoft Intune’da Android for Work cihaz kısıtlama ayarları](device-restrictions-android-for-work.md).

#### <a name="define-app-specific-pin-for-android-for-work-devices----728976-1102534---"></a>Android for Work cihazlarında uygulamaya özgü PIN’i tanımlama <!-- 728976, 1102534 -->

Android for Work cihazı olarak yönetilen ve bir iş profili bulunan Android 7.0 ve üzeri cihazlarda, yöneticinin yalnızca iş profilindeki uygulamalar için geçerli olacak bir geçiş kodu ilkesi tanımlamasına izin verilir.  Şu seçenekler mevcuttur:

- Yalnızca cihaz genelinde bir geçiş kodu ilkesi tanımlama - Bu, kullanıcının tüm cihaz kilidini açmak için kullanması gereken geçiş kodudur.
 Yalnızca bir iş profili geçiş kodu ilkesi tanımlama - İş profilindeki bir uygulama her açıldığında kullanıcılardan geçiş kodunu girmesi istenir.
- Hem cihaz hem iş profili ilkesi tanımlama - BT yöneticisinin farklı güç düzeylerinde hem cihaz geçiş kodu ilkesi hem de iş profili geçiş kodu ilkesi tanımlama seçeneği vardır (örneğin, cihazın kilidini açmak için dört basamaklı bir PIN, ancak herhangi bir iş uygulamasını açmak için altı basamaklı bir PIN).

Daha fazla bilgi için bkz. [Microsoft Intune’da Android for Work cihaz kısıtlama ayarları](device-restrictions-android-for-work.md).

> [!NOTE]
> Bu özellik yalnızca Android 7.0 ve üzeri sürümlerde kullanılabilir.  Varsayılan olarak, son kullanıcı ayrı tanımlanmış iki PIN kullanabilir veya tanımlanmış olan iki PIN’den en güçlü olanı seçebilir.

#### <a name="new-settings-for-windows-10-devices----978585---"></a>Windows 10 cihazları için yeni ayarlar <!-- 978585 -->

Kablosuz ekranlar, cihaz bulma, görev geçişi ve SIM kartı hata iletileri gibi özellikleri denetleyen yeni [Windows cihaz kısıtlama ayarları](device-restrictions-windows-10.md) ekledik.

#### <a name="updates-to-certificate-configuration----918991-and-823198---"></a>Sertifika yapılandırması güncelleştirmeleri <!-- 918991 and 823198 -->

Bir SCEP sertifika profili oluştururken, **Konu adı biçimi** için **Özel** seçeneği iOS, Android ve Windows cihazları için kullanılabilir. Bu güncelleştirmeden önce, **Özel** alanı yalnızca iOS cihazları için kullanılabiliyordu. Daha fazla bilgi için bkz. [SCEP sertifika profili oluşturma] (certificates-scep-configure.md#how-to-create-a-scep-certificate-profile).

Bir PKCS sertifika profili oluştururken, **Konu diğer adı** için **Özel Azure AD özniteliği** kullanılabilir. **Departman** seçeneği, **Özel Azure AD özniteliği** seçtiğinizde kullanılabilir. Daha fazla bilgi için bkz. [PKCS sertifika profili oluşturma] (certficates-pfx-configure.md#how-to-create-a-pkcs-certificate-profile).

#### <a name="configure-multiple-apps-that-can-run-when-an-android-device-is-in-kiosk-mode----662059---"></a>Bir Android cihazı bilgi noktası modunda olduğunda çalışabilen birden çok uygulama yapılandırma <!-- 662059 -->

Bir Android cihazı bilgi noktası modundayken, önceden çalışmasına izin verilen yalnızca bir uygulama yapılandırmanıza izin veriliyordu. Artık uygulama kimliği, mağaza kimliği veya zaten yönettiğiniz Android uygulamasını seçerek birden fazla uygulamayı yapılandırabilirsiniz. Daha fazla bilgi için bkz. [Bilgi noktası modu ayarları](device-restrictions-android.md#kiosk).


## <a name="notices"></a>Bildirimler

### <a name="ip-addresses-for-intune-updated----1175274---"></a>Intune için IP adresleri güncelleştirildi <!-- 1175274 -->

Güvenlik duvarı proxy ayarları için [güncelleştirilmiş DNS adları ve IP adresleri listesi](/intune/network-bandwidth-use) kullanılabilir.

### <a name="use-azure-active-directory-for-conditional-access----967947---"></a>Koşullu erişim için Azure Active Directory kullanın <!-- 967947 -->

Koşullu erişim Azure konsolundaki Azure Active Directory bölümünde kullanılabilir ve Office 365 Exchange Online ve SharePoint Online gibi bulut uygulamalarında ilkeleri ayarlamak için daha güçlü ve esnek bir çerçeve sağlar.  İlkeleri yapılandırmak için klasik Intune konsolu yerine **Azure Active Directory'de koşullu erişim** dikey penceresini kullanın. Klasik Intune konsolundaki mevcut ilkelerin Azure konsolunda yeniden oluşturulması gerekir. Daha fazla bilgi için bkz. [Azure AD Koşullu erişim ilkeleri oluşturma](/intune/conditional-access-exchange-create.md#create-azure-ad-conditional-access-policies-in-intune-azure-preview)

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Apple kayıt senaryolarına doğrudan erişim <!--951869-->

Intune, Azure portalındaki Cihaz Kaydetme iş yükünü kullanarak Apple kayıt senaryolarına doğrudan erişimi Ocak 2017 sonrasında oluşturulan Intune hesapları için etkinleştirdi. Daha önce, Apple kayıt önizleme sürümüne yalnızca klasik Intune portalı bağlantıları ile erişilebiliyordu. Bu özelliklerin Azure’da kullanılabilmesi için Ocak 2017 öncesi oluşturulan Intune hesaplarında tek seferlik bir geçiş yapılması gerekir. Geçiş için zaman çizelgesi henüz açıklanmamıştır, ancak konuya ilişkin ayrıntılar olabildiğince çabuk duyurulacaktır. Mevcut hesabınız Azure portalına erişemiyorsa yeni deneyimi sınamak için bir deneme hesabı oluşturmanızı kesinlikle öneririz.

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Yönetim rolleri Azure portalında değiştiriliyor

Klasik Intune portalında (Silverlight) kullanılan mevcut mobil uygulama yönetimi (MAM) yönetim rolleri (Katkıda bulunan, Sahibi ve Salt okunur) yerine Intune Azure portalında yeni rol tabanlı yönetim denetimleri (RBAC) geliyor. Azure portalına geçiş yaptıktan sonra, yöneticilerinizi bu yeni yönetim rollerine yeniden atamanız gerekiyor. RBAC ve yeni roller hakkında daha fazla bilgi için bkz. [Microsoft Intune için rol tabanlı erişim denetimi](/intune/role-based-access-control).

## <a name="whats-coming"></a>Yakında

### <a name="end-of-support-for-android-43-and-lower----1171127-1326920----"></a>Android 4.3 ve altı sürümler için desteğin son bulması<!---1171127, 1326920 --->
Yönetilen uygulamalar ve Android için Şirket Portalı uygulaması, şirket kaynaklarına erişim için Android 4.4 ve üzeri sürümleri gerektirecek. Ekim ayının başından önce güncelleştirmeyen cihazlar, Şirket Portalı veya diğer uygulamalara erişemeyecek. Aralık ayında ise tüm kayıtlı cihazlar zorla devre dışı bırakılıp şirket kaynaklarına erişimleri kaldırılacak. MDM’siz uygulama koruma ilkeleri kullanıyorsanız uygulamalar güncelleştirme almayacak ve deneyimlerinin kalitesi zamanla düşecek.


### <a name="platform-support-reminder-windows-phone-81-mainstream-support-will-end-july-11-2017"></a>Platform Desteği Anımsatıcı: Windows Phone 8.1 temel desteği, 11 Temmuz 2017 tarihinde sona erecektir
<!-- 1327781 -->

11 Temmuz 2017 tarihinde Windows Phone 8.1 platformu temel desteği son bulacaktır. Windows 8.1 PC desteği bundan etkilenmeyecektir.

Bu durum, Intune hizmeti ile yönetilen Windows Phone 8.1 cihazlar üzerinde doğrudan bir etki göstermeyecektir. Kayıtlı cihazlar çalışmaya devam edecek ve tüm ilkeler, yapılandırmalar ve uygulamalar olması gerektiği gibi çalışmayı sürdürecektir. Ancak Windows Phone 8.1 platformu ve Windows Phone 8.1 Şirket Portalı uygulaması için Intune hizmeti dahilinde iyileştirme planı olmadığını unutmayın.

İlk fırsatta uygun Windows Phone 8.1 cihazları Windows 10 Mobile sürümüne yükseltmenizi öneririz. 

### <a name="changes-in-support-for-the-intune-ios-company-portal-app-----1164474----"></a>Intune iOS Şirket Portalı uygulaması desteğindeki değişiklikler <!-- 1164474  -->


Yakında gelecek olan bir güncelleştirme ile iOS için Microsoft Intune Şirket Portalı uygulamasının yalnızca iOS 9.0 veya üzerini çalıştıran cihazları destekleyen yeni bir sürümü sunulacak. iOS 8’i destekleyen Şirket Portalı sürümü ise çok kısa bir süre daha kullanılabilir olacak. Ancak MAM etkin iOS uygulamaları kullanıyorsanız iOS 9.0 ve üzeri sürümlerin desteklendiğini unutmayın ve son kullanıcılarınızın en son işletim sistemi sürümüne güncelleştirdiğinden emin olun. 

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
Kesin tarih belirlenmemiş olmasına rağmen plan yapmak için zamanınız olmasına adına size önceden haber veriyoruz. Kullanıcılarınızın iOS 9 ve üzerine güncelleştirdiklerinden emin olun ve Şirket Portalı uygulaması yayımlandığında son kullanıcılarınızdan Şirket Portalı uygulamalarını güncelleştirmelerini isteyin.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapmam gerek?

Yeni Intune özelliklerinden tam anlamıyla yararlanmaları için kullanıcılarınıza iOS 9.0 veya üzerine güncelleştirmelerini önerin.  Kullanıcılara, Şirket Portalı uygulamasının yeni sürümüne güncelleştirip bu sürümle gelen yeni özelliklerden yararlanmalarını önerin.

Azure portalında Intune’a gidin ve Cihazlar > Tüm Cihazlar listesini iOS sürümüne göre filtreleyerek iOS 9’dan eski işletim sistemi kullanan cihazları görüntüleyin.

### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a>Tüm platformlar için Şirket Portalı uygulamalarında gelişmiş oturum açma deneyimi <!--User Story 1132123-->

Android, iOS ve Windows için Intune Şirket Portalı uygulamalarında oturum açma deneyimini geliştirecek bir değişikliği önümüzdeki birkaç ay içinde piyasaya süreceğiz. Yeni kullanıcı deneyimi, Azure AD bu değişikliği gerçekleştirdiğinde Şirket Portalına yönelik tüm platformlarda görünecektir. Ayrıca, kullanıcılar artık tek kullanımlık bir kod ile başka bir cihazdan Şirket Portalında oturum açabilir. Bu, özellikle kullanıcıların kimlik bilgileri olmadan oturum açması gerektiğinde faydalıdır.

Önceki oturum açma deneyiminin, kimlik bilgileriyle yeni oturum açma deneyiminin ve başka bir cihazdan yeni oturum açma deneyiminin ekran görüntülerini görmek için bkz. [Uygulamanın kullanıcı arabirimindeki yenilikler](/intune/whats-new-app-ui).

### <a name="plan-for-change-intune-is-changing-the-intune-partner-portal-experience----1050016---"></a>Değişiklik planı: Intune, Intune İş Ortağı Portalı deneyimini değiştiriyor <!-- 1050016 -->

2017 Mayıs ayı ortalarındaki hizmet güncelleştirmesinden başlayarak, manage.microsoft.com’dan Intune İş Ortağı sayfasını kaldırıyoruz.  

İş ortağı yöneticisiyseniz, artık Intune İş Ortağı sayfasında müşterileriniz adına görüntüleyemeyecek ve işlem yapamayacaksınız; bunun yerine Microsoft’taki diğer iki iş ortağı portalından birinde oturum açmanız gerekecektir.

Hem [Microsoft İş Ortağı Merkezi](https://partnercenter.microsoft.com/) hem de [Microsoft Office 365 İş Ortağı Yönetim Merkezi](https://portal.office.com/), yönettiğiniz müşteri hesaplarında oturum açmanıza olanak tanıyacaktır. İş ortağı olarak ilerlemek için, lütfen müşterilerinizi bu sitelerimizden birini kullanarak yönetin.


### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple, Uygulama Taşıma Güvenliği için güncelleştirmeler gerektirecek <!--748318-->

Apple, Uygulama Taşıma Güvenliği (ATS) için belirli gereksinimler uygulayacağını açıkladı. ATS, HTTPS üzerinden yapılan tüm uygulama iletişimlerinde daha sıkı güvenlik uygulamak için kullanılır. Bu değişiklik, iOS Şirket Portalı uygulamaları kullanan Intune müşterilerini etkiler.

Yeni ATS gereksinimlerinin kullanılmasını zorunlu kılan Apple TestFlight programı aracılığıyla iOS için Şirket Portalı uygulamasının yeni bir sürümünü kullanıma sunduk. ATS uyumluluğunuzu sınamak için bunu denemek isterseniz, adınızı, soyadınızı, e-posta adresinizi ve şirketinizin adını e-posta ile <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app">CompanyPortalBeta@microsoft.com</a> adresine gönderin. Daha fazla ayrıntı için bkz. [Intune destek blogu](https://aka.ms/compportalats).

### <a name="see-also"></a>Ayrıca bkz.
* [Microsoft Intune Blogu](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Cloud Platform yol haritası](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Şirket Portalı kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md)
* [Önceki aylardaki yenilikler](whats-new-archive.md)
