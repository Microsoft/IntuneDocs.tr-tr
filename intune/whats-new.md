---
title: Microsoft Intune'daki yenilikler
titlesuffix: Azure portal
description: "Intune Azure portalındaki yenilikleri keşfedin"
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 10/05/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b2817537cd9bc5ec6b8e9f5800f0c8f87cfde189
ms.sourcegitcommit: 53a1f5226d1e1172f013a1b192321dde610b2d6c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/06/2017
---
# <a name="whats-new-in-microsoft-intune"></a>Microsoft Intune'daki yenilikler

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Microsoft Intune’daki haftalık yenilikleri öğrenin. [Yaklaşan değişiklikler](#whats-coming), hizmet hakkında [önemli bildirimler](#notices) ve [geçmiş sunumlar](whats-new-archive.md) hakkında bilgiler de alabilirsiniz.

> [!Note]
> Bu özelliklerin birçoğu, sonunda Configuration Manager ile karma müşteri dağıtımlarında desteklenecektir. Yeni karma özellikler hakkında daha fazla bilgi için, [Karma Yenilikler sayfamızı](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) gözden geçirin.


<!-- Common categories:  
  ### Device enrollment
  ### Device management
  ### App management
  ### Device configuration
  ### Role-based access control
  ### Intune apps
  ### Monitor and troubleshoot

-->   

## <a name="week-of-october-2-2017"></a>2 Ekim 2017 haftası

### <a name="intune-apps"></a>Intune uygulamaları

#### <a name="improvements-to-device-setup-workflow-in-company-portal---1490692--"></a>Şirket Portalı’nda cihaz kurulum iş akışı iyileştirmeleri <!--1490692-->
Android için Şirket Portalı uygulamasında cihaz kurulum iş akışını iyileştirdik. Dil kolay anlaşılır ve şirketinize özgü bir durumdadır ve ekranlar mümkün olduğunca birleştirilmiştir. Bunları [uygulama kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md#week-of-october-2-2017) sayfasında görebilirsiniz.

#### <a name="improved-guidance-around-the-request-for-access-to-contacts-on-android-devices---1484985--"></a>Android cihazlarda kişilere erişim isteği için iyileştirilmiş rehber <!--1484985-->

Android için Şirket Portalı uygulaması genellikle son kullanıcının Kişiler izni vermesini gerektirir. Son kullanıcı bu erişimi reddederse, artık kendisini koşullu erişim için bu izni vermesi konusunda uyaran bir uygulama içi bildirim alacak. 

#### <a name="secure-startup-remediation-for-android---1490712--"></a>Android için güvenli başlangıç düzeltmesi <!--1490712-->

Android cihazı olan son kullanıcılar, Şirket Portalı uygulamasında uyumsuzluk sebebine dokunabilecek. Buna dokunmaları mümkün olduğunda, ayarlar uygulamasında sorunu çözebilecekleri konuma gidecekler. 

#### <a name="additional-push-notifications-for-end-users-on-the-company-portal-app-for-android-o---1475932---"></a>Android O için Şirket Portalı uygulamasında son kullanıcılar için ilave anında iletme bildirimleri<!---1475932--->

Android O için Şirket Portalı uygulaması Intune hizmetinden ilkeler alma gibi arka plan görevleri gerçekleştirdiğinde, son kullanıcılar bununla ilgili ilave bildirimler görecektir. Bu, Şirket Portalı’nın cihazlarda ne zaman yönetim görevleri gerçekleştirdiği hakkında son kullanıcılara daha fazla şeffaflık sağlar. Bu, Android O için Şirket Portalı uygulamasında genel [Şirket Portalı kullanıcı arabirimi iyileştirmesinin](https://blogs.technet.microsoft.com/intunesupport/2017/08/21/android-8-0-o-behaviour-changes-and-microsoft-intune) bir parçasıdır. 

Android O’da etkin olan yeni kullanıcı arabirimi öğeleri için gelişmiş iyileştirmeler var. Şirket Portalı, Intune hizmetinden ilke almak gibi bir arka plan görevi yürüttüğünde son kullanıcılar bu duruma dair ilave bildirimler görecek.  Bu, Şirket Portalı’nın cihazda ne zaman yönetim görevleri gerçekleştirdiği hakkında son kullanıcılara daha fazla şeffaflık sağlar.

#### <a name="new-behaviors-for-the-company-portal-app-for-android-with-work-profiles----1485783---"></a>İş profilleri bulunan Android için Şirket Portalı uygulamasında yeni davranışlar <!---1485783--->

Bir Android for Work cihazını iş profiliyle kaydettiğinizde cihazda yönetim görevlerini gerçekleştiren uygulama, iş profilindeki Şirket Portalı’dır. 

Kişisel profilde MAM özellikli uygulama kullanmıyorsanız Android için Şirket Portalı uygulamasının artık hiçbir kullanımı yoktur. İş profili deneyimini iyileştirmek için Intune, başarılı bir iş profili kaydından sonra kişisel Şirket Portalı uygulamasını otomatik olarak saklar.

İstediğiniz zaman [Play Store’da Şirket Portalı](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) araması yapıp **Etkinleştir**’e dokunarak kişisel profilinizde Android için Şirket Portalı uygulamasını etkinleştirebilirsiniz.

#### <a name="company-portal-for-windows-81-and-windows-phone-81-moving-to-sustaining-mode---1428681--"></a>Windows 8.1 ve Windows Phone 8.1 için Şirket Portalı, dayanıklılık moduna geçiyor <!--1428681-->

Ekim 2017’den itibaren Windows 8.1 ve Windows Phone 8.1 için Şirket Portalı uygulamaları, dayanıklılık moduna geçecek. Yani kayıt ve uyumluluk gibi mevcut senaryolar bu platformlarda desteklenmeye devam edecek. Bu uygulamalar Microsoft Mağazası gibi mevcut yayın kanallarından hala indirilebilir. 

Dayanıklılık moduna geçtikten sonra bu uygulamalar, yalnızca kritik güvenlik güncelleştirmelerini alacak. Bu uygulamalar için ek güncelleştirmeler veya özellikler yayımlanmayacak. Yeni özellikler için cihazları Windows 10 veya Windows 10 Mobile’a güncelleştirmenizi öneririz. 

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="block-unsupported-samsung-knox-device-enrollment------1490695----"></a>Desteklenmeyen Samsung Knox cihaz kaydını engelleme <!--- 1490695 --->

Şirket Portalı uygulaması, yalnızca desteklenen Samsung Knox cihazları kaydetmeye çalışır. MDM kaydını önleyen KNOX etkinleştirme hatalarının önüne geçmek adına, yalnızca cihazın [Samsung tarafından yayınlanan cihazlar listesinde](https://www.samsungknox.com/knox-supported-devices/knox-workspace) yer aldığı durumlarda cihaz kaydı denenir. Samsung cihazların KNOX destekleyen model numaraları olabilir ancak diğerlerinin olamaz. Satın alma dağıtma işlemlerinden önce, cihazınızın kurumsal bayisinden Knox uyumluluğunu doğrulayın. [Android ve Samsung KNOX Standard ilke ayarları](/intune-classic/android-policy-settings-in-microsoft-intune.md#supported-samsung-knox-standard-devices)’nda doğrulanan cihazların tam listesini bulabilirsiniz.

#### <a name="end-of-support-for-android-43-and-lower----1171126-1326920----"></a>Android 4.3 ve altı sürümler için desteğin son bulması<!---1171126, 1326920 --->
Yönetilen uygulamalar ve Android için Şirket Portalı uygulaması, şirket kaynaklarına erişim için Android 4.4 ve üzeri sürümleri gerektirecek. Aralık ayında ise tüm kayıtlı cihazlar zorla devre dışı bırakılıp şirket kaynaklarına erişimleri kaldırılacak. MDM’siz uygulama koruma ilkeleri kullanıyorsanız uygulamalar güncelleştirme almayacak ve deneyimlerinin kalitesi zamanla düşecek.

#### <a name="inform-end-users-what-device-information-can-be-seen-on-enrolled-devices---1165314--"></a>Kayıtlı cihazlarda hangi cihaz bilgilerinin görülebileceği hakkında son kullanıcıları bilgilendirme <!--1165314-->
Tüm Şirket Portalı uygulamalarında Cihaz Ayrıntıları ekranına **Sahiplik Türü** ekliyoruz. Böylece kullanıcılar, doğrudan [Şirketiniz hangi bilgileri görebilir?](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune) makalesinden gizlilik hakkında bilgi edinebilecekler. Bu değişiklik, yakın zamanda tüm Şirket Portalı uygulamalarında sunulacak. iOS için bu değişikliği [Eylül](https://docs.microsoft.com/intune/whats-new#week-of-september-11-2017) ayı içinde duyurduk. 


## <a name="week-of-september-25-2017"></a>25 Eylül 2017 haftası

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="intune-supports-ios-11---1428975--"></a>Intune, iOS 11’i destekliyor <!--1428975-->
Intune, iOS 11’i destekliyor. Bu, daha önce [Intune Destek bloğunda](https://blogs.technet.microsoft.com/intunesupport/2017/09/12/support-tip-intune-support-for-ios-11/) duyurulmuştu.

### <a name="end-of-support-for-ios-80----1164477---"></a>iOS 8.0 desteğinin son bulması <!---1164477--->
Yönetilen uygulamalar ve iOS için Şirket Portalı uygulaması, şirket kaynaklarına erişim için iOS 9.0 ve üzeri sürümleri gerektirecek. Eylül ayından önce güncelleştirmeyen cihazlar, Şirket Portalı veya diğer uygulamalara erişemeyecek. 

### <a name="intune-apps"></a>Intune uygulamaları

#### <a name="refresh-action-added-to-the-company-portal-app-for-windows-10---1132468--"></a>Windows 10 için Şirket Portalı uygulamasına yenileme eylemi eklendi <!--1132468-->

Windows 10 için Şirket Portalı uygulaması, mobil cihazlarda aşağı çekerek veya masaüstü cihazlarda F5’e basarak kullanıcılara uygulamadaki verileri yenileme imkanı sunar.

## <a name="week-of-september-11-2017"></a>11 Eylül 2017 haftası

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="inform-end-users-what-device-information-can-be-seen-for-ios---739894--"></a>iOS için hangi cihaz bilgilerinin görülebileceği hakkında son kullanıcıları bilgilendirme <!--739894-->

iOS için Şirket Portalı’nda Cihaz Ayrıntıları ekranına **Sahiplik Türü** ekledik. Bu, kullanıcıların doğrudan bu sayfadaki Intune son kullanıcı belgelerinden gizlilik hakkında daha fazla bilgi edinmesini sağlar. Kullanıcılar bu bilgileri Hakkında ekranında da bulabilir.

#### <a name="allow-end-users-to-access-the-company-portal-app-for-android-without-enrollment----1169910---"></a>Son kullanıcıların kayıt yapmadan Android için Şirket Portalı uygulamasına erişmelerine izin verme <!---1169910--->

Son kullanıcılar yakın zamanda cihazlarını kaydetmeden Android için Şirket Portalı uygulamasına erişebilecek. Uygulama Koruma İlkeleri kullanan kuruluşlardaki son kullanıcılar artık Şirket Portalı uygulamasını açtıklarında cihazlarını kaydetmelerine yönelik komut istemleri almayacaklar. Son kullanıcılar ayrıca cihaz kaydı yapmaksızın Şirket Portalı’dan uygulama yükleyebilecek. 


#### <a name="easier-to-understand-phrasing-for-the-company-portal-app-for-android----1396349---"></a>Android için Şirket Portalı uygulamasında daha kolay anlaşılır bir dil <!---1396349--->  

Android için Şirket Portalı uygulamasında kayıt işlemi, son kullanıcıların kaydını kolaylaştırmak adına yeni metinlerle düzenlendi. Özel kayıt belgeleriniz varsa bunları, değişiklikleri yansıtması için güncelleştirmelisiniz. [Intune son kullanıcı uygulamaları için kullanıcı arabirimi güncelleştirmeleri](whats-new-app-ui.md#week-of-september-11-2017) sayfamızda örnek görüntüleri bulabilirsiniz.

#### <a name="windows-10-company-portal-app-added-to-windows-information-protection-allow-policy----677129---"></a>Windows 10 Şirket Portalı uygulaması, Windows Bilgi Koruması izin ilkesine eklendi <!-- 677129 -->

Windows 10 Şirket Portalı uygulaması, Windows Bilgi Koruması’nı (WIP) destekleyecek şekilde güncelleştirildi. Uygulama, WIP izin ilkesine eklenebilecek. Bu değişiklik ile uygulamanın **Muaf** listesine eklenme gerekliliği ortadan kalkacak.


## <a name="week-of-august-21-2017"></a>21 Ağustos 2017 Haftası

### <a name="device-enrollment"></a>Cihaz kaydı
#### <a name="improvements-to-device-overview----1404453---"></a>Cihaz önizlemesi iyileştirmeleri <!-- 1404453 -->  
Cihaz önizlemesi iyileştirmeleri artık kayıtlı cihazları gösterirken Exchange ActiveSync tarafından yönetilen cihazları göstermiyor. Exchange ActiveSync cihazları, kayıtlı cihazlarla aynı yönetim seçeneklerine sahip değil. Azure portalında Intune’da kayıtlı cihaz sayısını ve platforma göre kayıtlı cihaz sayısını görüntülemek için, **Cihazlar** > **Genel Bakış**‘a gidin.

### <a name="device-management"></a>Cihaz yönetimi
#### <a name="improvements-to-device-inventory-collected-by-intune"></a>Intune tarafından toplanan cihaz envanteri geliştirmeleri
<!-- 961134, 1104426, 1281327, 1333543 -->
Bu sürümde, yönettiğiniz cihazlar tarafından toplanan envanter bilgilerinde aşağıdaki iyileştirmeleri yaptık:
 
-   Android cihazlarda artık her cihaz için cihaz envanterine son düzeltme eki düzeyini gösteren bir sütun ekleyebilirsiniz. Bunu görmek için cihaz listenize **Güvenlik düzeltme eki düzeyi** sütununu ekleyin.
-   Cihaz görünümünü filtrelerken artık cihazları kayıt tarihlerine göre filtreleyebilirsiniz. Örneğin, yalnızca belirttiğiniz bir tarihten sonra kaydedilen cihazları görüntüleyebilirsiniz.
-   **Son Yer Bildirim Tarihi** öğesi tarafından kullanılan filtrede iyileştirmeler yaptık.
-   Cihaz listesinde artık şirkete ait cihazların telefon numaralarını görüntüleyebilirsiniz.
Ayrıca, filtre bölmesini kullanarak cihazları telefon numarasına göre arayabilirsiniz.
 
Cihaz envanteri hakkında daha fazla ayrıntı için bkz. [Intune cihaz envanterini görüntüleme](device-inventory.md).

#### <a name="conditional-access-support-for-macos-devices"></a>macOS cihazlar için koşullu erişim desteği 
<!-- 720172 -->
Artık Mac cihazların Intune’a kaydedilmesi ve Intune cihaz uyumluluk ilkeleriyle uyumlu olmasını gerektiren bir koşullu erişim ilkesi ayarlayabilirsiniz. Örneğin kullanıcılar, macOS için Intune Şirket Portalı uygulamasını indirebilir ve Mac cihazlarını Intune’a kaydedebilir. Intune ise PIN, şifreleme, işletim sistemi sürümü ve Sistem Bütünlüğü gibi gereksinimleri kullanarak Mac cihazın uyumlu olup olmadığını değerlendirir.

- [macOS cihazlar için koşullu erişim desteği](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) hakkında daha fazla bilgi edinin.

#### <a name="company-portal-app-for-macos-is-in-public-preview----1484796---"></a>macOS için Intune Şirket Portalı uygulaması genel önizlemede <!---1484796--->
macOS için Şirket Portalı uygulaması artık Enterprise Mobility + Security’de koşullu erişim için genel önizlemenin bir parçası olarak kullanılabilir. Bu sürüm, macOS 10.11 ve üzerini destekler. Uygulamayı [https://aka.ms/macOScompanyportal](https://aka.ms/macOScompanyportal) adresinden edinin. 


#### <a name="new-device-restriction-settings-for-windows-10"></a>Windows 10 için yeni cihaz kısıtlama ayarları    
<!--1063965, 1308850  -->
Bu sürümde, [Windows 10 cihaz kısıtlama profili](/intune/device-restrictions-windows-10) için aşağıdaki kategorilere yeni ayarlar ekledik:

-   Windows Defender SmartScreen
-   Uygulama mağazası

#### <a name="updates-to-the-windows-10-endpoint-protection-device-profile-for-bitlocker-settings"></a>BitLocker ayarları için Windows 10 uç nokta koruma cihaz profili güncelleştirmeleri
<!--1459533 -->    
Bu sürümde, BitLocker’ın Windows 10 uç nokta koruma cihaz profilinde çalışması konusunda aşağıdaki iyileştirmeleri yaptık:
 
**BitLocker işletim sistemi sürücü ayarları** altında **Uyumlu olmayan TPM yongası ile BitLocker** için **Engelle**’yi seçtiğinizde, Bu durum eskiden BitLocker’a izin verilmesine yol açıyordu. Artık bunu, seçildiğinde BitLocker’ı engelleyecek şekilde düzelttik.
**BitLocker işletim sistemi sürücü ayarları** altında **Sertifika tabanlı veri kurtarma aracısı** ayarında artık sertifika tabanlı veri kurtarma aracısını engelleyebilirsiniz. Ancak varsayılan olarak bu aracıya izin verilir.
**BitLocker sabit veri sürücü ayarları** altında **Veri kurtarma aracısı** ayarında artık kurtarma aracısını engelleyebilirsiniz.
Daha fazla bilgi için bkz. [Windows 10 ve üzeri sürümler için Endpoint Protection ayarları](endpoint-protection-windows-10.md).


### <a name="app-management"></a>Uygulama yönetimi
#### <a name="new-signed-in-experience-for-android-company-portal-users-and-app-protection-policy-users----621669---"></a>Android Şirket Portalı ve Uygulama Koruma İlkesi kullanıcıları için yeni oturum açma deneyimi <!-- 621669 -->
Son kullanıcılar artık Android Şirket Portalı’nı kullanarak cihazlarını kaydetmeden uygulamalara göz atabilir, cihazları yönetebilir ve BT iletişim bilgilerini görüntüleyebilir. Ayrıca, son kullanıcı zaten Intune Uygulama Koruma İlkeleri ile korunan bir uygulama kullanıyorsa ve Android Şirket Portalı'nı başlatırsa artık cihazı kaydetmek için bir istem almaz.

### <a name="new-setting-in-the-android-company-portal-app-to-toggle-battery-optimization---1405990--"></a>Android Şirket Portalı uygulamasında pil iyileştirmesini değiştirmek için yeni bir ayar <!--1405990-->
Android için Şirket Portalı uygulamasında **Ayarlar** sayfası, kullanıcıların Şirket Portalı ve Microsoft Authenticator uygulamaları için pil iyileştirmesini kolaylıkla kapatmalarına izin veren yeni bir ayara sahip. Ayarda gösterilen uygulama adı, hangi uygulamanın iş hesabını yönettiğine bağlı olarak değişecektir. E-posta ve veri eşitleyen iş uygulamalarının daha iyi çalışması için kullanıcıların pil iyileştirmesini kapatmalarını öneririz. 

#### <a name="multi-identity-support-for-onenote-for-ios---------1234281---"></a>iOS için OneNote’da çoklu kimlik desteği      <!-- 1234281 -->
Son kullanıcılar artık, iOS için Microsoft OneNote ile farklı hesaplar (iş ve kişisel) kullanabilir. Kullanıcıların kişisel not defterlerini etkilemeksizin iş not defterlerinde şirket verilerine uygulama koruma ilkeleri uygulanabilir. Örneğin bir ilke, bir kullanıcının iş not defterlerinde istediği bilgileri bulmasına izin verirken iş not defterlerinden kişisel not defterine şirket verilerini kopyalayıp yapıştırmasını engelleyebilir.
 
- Intune ile [uygulama koruması ve çoklu kimlik](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) destekleyen uygulamalar hakkında daha fazla bilgi edinin.

#### <a name="new-settings-to-allow-and-block-apps-on-samsung-knox-standard-devices"></a>Samsung KNOX Standard cihazlarda uygulamalara izin vermek veya bunları engellemek için yeni ayarlar
<!-- 1305423 822899-->  
Bu sürümde, aşağıdaki uygulama listelerini belirtmenizi sağlayan yeni [cihaz kısıtlama ayarları](device-restrictions-android.md) ekliyoruz:
 
- Kullanıcıların yüklemesine izin verilen uygulamalar
- Kullanıcıların çalıştırması engellenen uygulamalar
- Cihazda kullanıcıdan gizlenen uygulamalar
 
Uygulamayı URL, paket adı ile veya yönettiğiniz uygulamalar listesinden belirtebilirsiniz.

#### <a name="new-azure-ad-app-based-conditional-access-policy-ui-link-from-intune"></a>Intune’dan yeni Azure AD uygulama tabanlı koşullu erişim ilkesi kullanıcı arabirimi bağlantısı
<!-- 1016201 -->
BT yöneticileri artık, Azure AD iş yükünde yeni koşullu erişim ilkesi kullanıcı arabirimi aracılığıyla uygulama tabanlı ilkeler ayarlayabilir. Azure portalındaki Intune Uygulama Koruması bölümünde bulunan uygulama tabanlı koşullu erişim şimdilik orada kalacak ve yan yana uygulanacaktır. Ayrıca Intune iş yükünde, yeni koşullu erişim ilkesi kullanıcı arabirimine kolay bir bağlantı da bulunur.

- [Azure AD’de uygulama tabanlı koşullu erişim](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-technical-reference) hakkında daha fazla bilgi edinin.


## <a name="notices"></a>Bildirimler

### <a name="ip-addresses-for-intune-updated----1175274---"></a>Intune için IP adresleri güncelleştirildi <!-- 1175274 -->
Güvenlik duvarı proxy ayarları için [güncelleştirilmiş DNS adları ve IP adresleri listesi](/intune/network-bandwidth-use) kullanılabilir.

### <a name="use-azure-active-directory-for-conditional-access----967947---"></a>Koşullu erişim için Azure Active Directory kullanın <!-- 967947 -->
Koşullu erişim, Azure portalındaki Azure Active Directory bölümünde kullanılabilir ve Office 365 Exchange Online ve SharePoint Online gibi bulut uygulamalarında ilkeleri ayarlamak için daha güçlü ve esnek bir çerçeve sağlar.  İlkeleri yapılandırmak için Intune konsolu yerine **Azure Active Directory’de koşullu erişim** dikey penceresini kullanın. Intune konsolundaki mevcut ilkelerin Azure portalında yeniden oluşturulması gerekir. Daha fazla bilgi için bkz. [Azure AD koşullu erişim ilkeleri oluşturma](/intune/conditional-access-exchange-create.md#create-azure-ad-conditional-access-policies-in-intune-azure-preview).

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Apple kayıt senaryolarına doğrudan erişim <!--951869-->
Intune, Azure portalındaki Cihaz Kaydetme iş yükünü kullanarak Apple kayıt senaryolarına doğrudan erişimi Ocak 2017 sonrasında oluşturulan Intune hesapları için etkinleştirdi. Daha önce, Apple kayıt önizleme sürümüne yalnızca klasik Intune portalı bağlantıları ile erişilebiliyordu. Bu özelliklerin Azure’da kullanılabilmesi için Ocak 2017 öncesi oluşturulan Intune hesaplarında tek seferlik bir geçiş yapılması gerekir. Geçiş için zaman çizelgesi henüz açıklanmamıştır, ancak konuya ilişkin ayrıntılar olabildiğince çabuk duyurulacaktır. Mevcut hesabınız Azure portalına erişemiyorsa yeni deneyimi sınamak için bir deneme hesabı oluşturmanızı kesinlikle öneririz.

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Yönetim rolleri Azure portalında değiştiriliyor
Klasik Intune portalında (Silverlight) kullanılan mevcut mobil uygulama yönetimi (MAM) yönetim rolleri (Katkıda bulunan, Sahibi ve Salt okunur) yerine Intune Azure portalında yeni rol tabanlı yönetim denetimleri (RBAC) geliyor. Azure portalına geçiş yaptıktan sonra, yöneticilerinizi bu yeni yönetim rollerine yeniden atamanız gerekiyor. RBAC ve yeni roller hakkında daha fazla bilgi için bkz. [Microsoft Intune için rol tabanlı erişim denetimi](/intune/role-based-access-control).



## <a name="whats-coming"></a>Yakında

#### <a name="ios-11-mail-app-will-support-oauth----1196951---"></a>iOS 11 Mail uygulaması OAuth destekleyecek <!---1196951--->
Intune ile koşullu erişim, OAuth bulunan iOS cihazlarda daha güvenli kimlik doğrulamasını destekler. Bunu desteklemek üzere daha güvenli kimlik doğrulamasına imkan vermek için artık iOS için Şirket Portalı uygulamasında farklı bir akış bulunacak. Son kullanıcılar, Mail uygulamasında yeni bir Exchange hesabıyla oturum açmaya çalıştığında web görünümlü bir istem alacaklar. Intune’a kaydolduktan sonra kullanıcılar, yerel Mail uygulamasının sertifikaya erişmesine izin vermek için bir komut istemi görecekler. Pek çok son kullanıcı artık, karantinaya alınmış e-posta görmeyecek. Mevcut posta hesapları, temel kimlik doğrulama protokolünü kullanmaya devam edecek, bu yüzden bu kullanıcılar karantinaya alınmış e-postalar almaya devam edecektir. Son kullanıcılar için bu oturum açma deneyimi, Office mobil uygulamalarına benzerdir.

### <a name="ui-updates-to-the-company-portal-website---1313244-part-2--"></a>Şirket Portalı web sitesine kullanıcı arabirimi güncelleştirmeleri <!--1313244 part 2-->
__Öne Çıkan Uygulama Güncelleştirmeleri__  
Kullanıcıların öne çıkarmak istediğiniz uygulamalara göz atabileceği siteye ayrı bir sayfa ekledik ve giriş sayfasındaki Öne Çıkan sekmesinde bazı kullanıcı arabirimi değişiklikleri yaptık. Bu değişikliklerin neler olduğunu [uygulama kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md) sayfasında görebilirsiniz.

### <a name="platform-support-reminder-windows-phone-81-mainstream-support-ended-july-11-2017"></a>Platform Desteği Anımsatıcısı: Windows Phone 8.1 temel desteği, 11 Temmuz 2017 tarihinde sona ermiştir
<!-- 1327781 -->
11 Temmuz 2017 tarihinde Windows Phone 8.1 platformu temel desteği son bulmuştur. Windows 8.1 PC desteği bundan etkilenmeyecektir.

Bu durum, Intune hizmeti ile yönetilen Windows Phone 8.1 cihazlar üzerinde doğrudan bir etki göstermeyecektir. Kayıtlı cihazlar çalışmaya devam edecek ve tüm ilkeler, yapılandırmalar ve uygulamalar olması gerektiği gibi çalışmayı sürdürecektir. Ancak Windows Phone 8.1 platformu ve Windows Phone 8.1 Şirket Portalı uygulaması için Intune hizmeti dahilinde iyileştirme planı olmadığını unutmayın.

İlk fırsatta uygun Windows Phone 8.1 cihazları Windows 10 Mobile sürümüne yükseltmenizi öneririz. 

### <a name="changes-in-support-for-the-intune-ios-company-portal-app-----1164474----"></a>Intune iOS Şirket Portalı uygulaması desteğindeki değişiklikler <!-- 1164474  -->
Yakında gelecek olan bir güncelleştirme ile iOS için Microsoft Intune Şirket Portalı uygulamasının yalnızca iOS 9.0 veya üzerini çalıştıran cihazları destekleyen yeni bir sürümü sunulacak. iOS 8’i destekleyen Şirket Portalı sürümü ise çok kısa bir süre daha kullanılabilir olacak. Ancak MAM etkin iOS uygulamaları kullanıyorsanız iOS 9.0 ve üzeri sürümlerin desteklendiğini unutmayın ve son kullanıcılarınızın en son işletim sistemi sürümüne güncelleştirdiğinden emin olun. 

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
Kesin tarih belirlenmemiş olmasına rağmen plan yapmak için zamanınız olmasına adına size önceden haber veriyoruz. Kullanıcılarınızın iOS 9 ve üzerine güncelleştirdiklerinden emin olun ve Şirket Portalı uygulaması yayımlandığında son kullanıcılarınızdan Şirket Portalı uygulamalarını güncelleştirmelerini isteyin.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapmam gerek?
Yeni Intune özelliklerinden tam anlamıyla yararlanmaları için kullanıcılarınıza iOS 9.0 veya üzerine güncelleştirmelerini önerin.  Kullanıcılara, Şirket Portalı uygulamasının yeni sürümüne güncelleştirip bu sürümle gelen yeni özelliklerden yararlanmalarını önerin.

Azure portalında Intune’a gidin ve Cihazlar > Tüm Cihazlar listesini iOS sürümüne göre filtreleyerek iOS 9’dan eski işletim sistemi kullanan cihazları görüntüleyin.


### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple, Uygulama Taşıma Güvenliği için güncelleştirmeler gerektirecek <!--748318-->
Apple, Uygulama Taşıma Güvenliği (ATS) için belirli gereksinimler uygulayacağını açıkladı. ATS, HTTPS üzerinden yapılan tüm uygulama iletişimlerinde daha sıkı güvenlik uygulamak için kullanılır. Bu değişiklik, iOS Şirket Portalı uygulamaları kullanan Intune müşterilerini etkiler.

Yeni ATS gereksinimlerinin kullanılmasını zorunlu kılan Apple TestFlight programı aracılığıyla iOS için Şirket Portalı uygulamasının yeni bir sürümünü kullanıma sunduk. ATS uyumluluğunuzu sınamak için bunu denemek isterseniz, adınızı, soyadınızı, e-posta adresinizi ve şirketinizin adını e-posta ile <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app">CompanyPortalBeta@microsoft.com</a> adresine gönderin. Daha fazla ayrıntı için bkz. [Intune destek blogu](https://aka.ms/compportalats).

### <a name="see-also"></a>Ayrıca bkz.
* [Microsoft Intune Blogu](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Cloud Platform yol haritası](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Şirket Portalı kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md)
* [Önceki aylardaki yenilikler](whats-new-archive.md)
