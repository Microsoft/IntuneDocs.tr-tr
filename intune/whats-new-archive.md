---
title: "Microsoft Intune önceki aylardaki yenilikler"
titlesuffix: Azure portal
description: "Intune’daki yenilikler sayfasından eski duyuruları gözden geçirme"
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 10/19/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9ba01d60-4a03-4e3e-9aba-8be905c0054c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3462c6c418ed48991f58e0ccf2e09f2df8b48410
ms.sourcegitcommit: bb2c181fd6de929cf1e5d3856e048d617eb72063
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2017
---
# <a name="whats-new-in-the-microsoft-intune---previous-months"></a>Microsoft Intune’daki yenilikler - önceki aylar

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="september-2017"></a>Eylül 2017

### <a name="inform-end-users-what-device-information-can-be-seen-for-ios---739894--"></a>iOS için hangi cihaz bilgilerinin görülebileceği hakkında son kullanıcıları bilgilendirme <!--739894-->

iOS için Şirket Portalı’nda Cihaz Ayrıntıları ekranına **Sahiplik Türü** ekledik. Bu, kullanıcıların doğrudan bu sayfadaki Intune son kullanıcı belgelerinden gizlilik hakkında daha fazla bilgi edinmesini sağlar. Kullanıcılar bu bilgileri Hakkında ekranında da bulabilir.

### <a name="allow-end-users-to-access-the-company-portal-app-for-android-without-enrollment----1169910---"></a>Son kullanıcıların kayıt yapmadan Android için Şirket Portalı uygulamasına erişmelerine izin verme <!---1169910--->

Son kullanıcılar yakın zamanda cihazlarını kaydetmeden Android için Şirket Portalı uygulamasına erişebilecek. Uygulama Koruma İlkeleri kullanan kuruluşlardaki son kullanıcılar artık Şirket Portalı uygulamasını açtıklarında cihazlarını kaydetmelerine yönelik komut istemleri almayacaklar. Son kullanıcılar ayrıca cihaz kaydı yapmaksızın Şirket Portalı’dan uygulama yükleyebilecek. 


### <a name="easier-to-understand-phrasing-for-the-company-portal-app-for-android----1396349---"></a>Android için Şirket Portalı uygulamasında daha kolay anlaşılır bir dil <!---1396349--->  

Android için Şirket Portalı uygulamasında kayıt işlemi, son kullanıcıların kaydını kolaylaştırmak adına yeni metinlerle düzenlendi. Özel kayıt belgeleriniz varsa bunları, değişiklikleri yansıtması için güncelleştirmelisiniz. [Intune son kullanıcı uygulamaları için kullanıcı arabirimi güncelleştirmeleri](whats-new-app-ui.md#week-of-september-11-2017) sayfamızda örnek görüntüleri bulabilirsiniz.

### <a name="windows-10-company-portal-app-added-to-windows-information-protection-allow-policy----677129---"></a>Windows 10 Şirket Portalı uygulaması, Windows Bilgi Koruması izin ilkesine eklendi <!-- 677129 -->

Windows 10 Şirket Portalı uygulaması, Windows Bilgi Koruması’nı (WIP) destekleyecek şekilde güncelleştirildi. Uygulama, WIP izin ilkesine eklenebilecek. Bu değişiklik ile uygulamanın **Muaf** listesine eklenme gerekliliği ortadan kalkacak.


## <a name="august-2017"></a>Ağustos 2017

### <a name="improvements-to-device-overview----1404453---"></a>Cihaz önizlemesi iyileştirmeleri <!-- 1404453 -->  
Cihaz önizlemesi iyileştirmeleri artık kayıtlı cihazları gösterirken Exchange ActiveSync tarafından yönetilen cihazları göstermiyor. Exchange ActiveSync cihazları, kayıtlı cihazlarla aynı yönetim seçeneklerine sahip değil. Azure portalında Intune’da kayıtlı cihaz sayısını ve platforma göre kayıtlı cihaz sayısını görüntülemek için, **Cihazlar** > **Genel Bakış**‘a gidin.

### <a name="improvements-to-device-inventory-collected-by-intune"></a>Intune tarafından toplanan cihaz envanteri geliştirmeleri
<!-- 961134, 1104426, 1281327, 1333543 -->
Bu sürümde, yönettiğiniz cihazlar tarafından toplanan envanter bilgilerinde aşağıdaki iyileştirmeleri yaptık:
 
-   Android cihazlarda artık her cihaz için cihaz envanterine son düzeltme eki düzeyini gösteren bir sütun ekleyebilirsiniz. Bunu görmek için cihaz listenize **Güvenlik düzeltme eki düzeyi** sütununu ekleyin.
-   Cihaz görünümünü filtrelerken artık cihazları kayıt tarihlerine göre filtreleyebilirsiniz. Örneğin, yalnızca belirttiğiniz bir tarihten sonra kaydedilen cihazları görüntüleyebilirsiniz.
-   **Son Yer Bildirim Tarihi** öğesi tarafından kullanılan filtrede iyileştirmeler yaptık.
-   Cihaz listesinde artık şirkete ait cihazların telefon numaralarını görüntüleyebilirsiniz.
Ayrıca, filtre bölmesini kullanarak cihazları telefon numarasına göre arayabilirsiniz.
 
Cihaz envanteri hakkında daha fazla ayrıntı için bkz. [Intune cihaz envanterini görüntüleme](device-inventory.md).

### <a name="conditional-access-support-for-macos-devices"></a>macOS cihazlar için koşullu erişim desteği 
<!-- 720172 -->
Artık Mac cihazların Intune’a kaydedilmesi ve Intune cihaz uyumluluk ilkeleriyle uyumlu olmasını gerektiren bir koşullu erişim ilkesi ayarlayabilirsiniz. Örneğin kullanıcılar, macOS için Intune Şirket Portalı uygulamasını indirebilir ve Mac cihazlarını Intune’a kaydedebilir. Intune ise PIN, şifreleme, işletim sistemi sürümü ve Sistem Bütünlüğü gibi gereksinimleri kullanarak Mac cihazın uyumlu olup olmadığını değerlendirir.

- [macOS cihazlar için koşullu erişim desteği](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) hakkında daha fazla bilgi edinin.

### <a name="company-portal-app-for-macos-is-in-public-preview----1484796---"></a>macOS için Intune Şirket Portalı uygulaması genel önizlemede <!---1484796--->
macOS için Şirket Portalı uygulaması artık Enterprise Mobility + Security’de koşullu erişim için genel önizlemenin bir parçası olarak kullanılabilir. Bu sürüm, macOS 10.11 ve üzerini destekler. Uygulamayı [https://aka.ms/macOScompanyportal](https://aka.ms/macOScompanyportal) adresinden edinin. 


### <a name="new-device-restriction-settings-for-windows-10"></a>Windows 10 için yeni cihaz kısıtlama ayarları    
<!--1063965, 1308850  -->
Bu sürümde, [Windows 10 cihaz kısıtlama profili](/intune/device-restrictions-windows-10) için aşağıdaki kategorilere yeni ayarlar ekledik:

-   Windows Defender SmartScreen
-   Uygulama mağazası

### <a name="updates-to-the-windows-10-endpoint-protection-device-profile-for-bitlocker-settings"></a>BitLocker ayarları için Windows 10 uç nokta koruma cihaz profili güncelleştirmeleri
<!--1459533 -->    
Bu sürümde, BitLocker’ın Windows 10 uç nokta koruma cihaz profilinde çalışması konusunda aşağıdaki iyileştirmeleri yaptık:
 
**BitLocker işletim sistemi sürücü ayarları** altında **Uyumlu olmayan TPM yongası ile BitLocker** için **Engelle**’yi seçtiğinizde, Bu durum eskiden BitLocker’a izin verilmesine yol açıyordu. Artık bunu, seçildiğinde BitLocker’ı engelleyecek şekilde düzelttik.
**BitLocker işletim sistemi sürücü ayarları** altında **Sertifika tabanlı veri kurtarma aracısı** ayarında artık sertifika tabanlı veri kurtarma aracısını engelleyebilirsiniz. Ancak varsayılan olarak bu aracıya izin verilir.
**BitLocker sabit veri sürücü ayarları** altında **Veri kurtarma aracısı** ayarında artık kurtarma aracısını engelleyebilirsiniz.
Daha fazla bilgi için bkz. [Windows 10 ve üzeri sürümler için Endpoint Protection ayarları](endpoint-protection-windows-10.md).


### <a name="new-signed-in-experience-for-android-company-portal-users-and-app-protection-policy-users----621669---"></a>Android Şirket Portalı ve Uygulama Koruma İlkesi kullanıcıları için yeni oturum açma deneyimi <!-- 621669 -->
Son kullanıcılar artık Android Şirket Portalı’nı kullanarak cihazlarını kaydetmeden uygulamalara göz atabilir, cihazları yönetebilir ve BT iletişim bilgilerini görüntüleyebilir. Ayrıca, son kullanıcı zaten Intune Uygulama Koruma İlkeleri ile korunan bir uygulama kullanıyorsa ve Android Şirket Portalı'nı başlatırsa artık cihazı kaydetmek için bir istem almaz.

### <a name="new-setting-in-the-android-company-portal-app-to-toggle-battery-optimization---1405990--"></a>Android Şirket Portalı uygulamasında pil iyileştirmesini değiştirmek için yeni bir ayar <!--1405990-->
Android için Şirket Portalı uygulamasında **Ayarlar** sayfası, kullanıcıların Şirket Portalı ve Microsoft Authenticator uygulamaları için pil iyileştirmesini kolaylıkla kapatmalarına izin veren yeni bir ayara sahip. Ayarda gösterilen uygulama adı, hangi uygulamanın iş hesabını yönettiğine bağlı olarak değişecektir. E-posta ve veri eşitleyen iş uygulamalarının daha iyi çalışması için kullanıcıların pil iyileştirmesini kapatmalarını öneririz. 

### <a name="multi-identity-support-for-onenote-for-ios---------1234281---"></a>iOS için OneNote’da çoklu kimlik desteği      <!-- 1234281 -->
Son kullanıcılar artık, iOS için Microsoft OneNote ile farklı hesaplar (iş ve kişisel) kullanabilir. Kullanıcıların kişisel not defterlerini etkilemeksizin iş not defterlerinde şirket verilerine uygulama koruma ilkeleri uygulanabilir. Örneğin bir ilke, bir kullanıcının iş not defterlerinde istediği bilgileri bulmasına izin verirken iş not defterlerinden kişisel not defterine şirket verilerini kopyalayıp yapıştırmasını engelleyebilir.
 
- Intune ile [uygulama koruması ve çoklu kimlik](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) destekleyen uygulamalar hakkında daha fazla bilgi edinin.

### <a name="new-settings-to-allow-and-block-apps-on-samsung-knox-standard-devices"></a>Samsung KNOX Standard cihazlarda uygulamalara izin vermek veya bunları engellemek için yeni ayarlar
<!-- 1305423 822899-->  
Bu sürümde, aşağıdaki uygulama listelerini belirtmenizi sağlayan yeni [cihaz kısıtlama ayarları](device-restrictions-android.md) ekliyoruz:
 
- Kullanıcıların yüklemesine izin verilen uygulamalar
- Kullanıcıların çalıştırması engellenen uygulamalar
- Cihazda kullanıcıdan gizlenen uygulamalar
 
Uygulamayı URL, paket adı ile veya yönettiğiniz uygulamalar listesinden belirtebilirsiniz.

### <a name="new-azure-ad-app-based-conditional-access-policy-ui-link-from-intune"></a>Intune’dan yeni Azure AD uygulama tabanlı koşullu erişim ilkesi kullanıcı arabirimi bağlantısı
<!-- 1016201 -->
BT yöneticileri artık, Azure AD iş yükünde yeni koşullu erişim ilkesi kullanıcı arabirimi aracılığıyla uygulama tabanlı ilkeler ayarlayabilir. Azure portalındaki Intune Uygulama Koruması bölümünde bulunan uygulama tabanlı koşullu erişim şimdilik orada kalacak ve yan yana uygulanacaktır. Ayrıca Intune iş yükünde, yeni koşullu erişim ilkesi kullanıcı arabirimine kolay bir bağlantı da bulunur.

- [Azure AD’de uygulama tabanlı koşullu erişim](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-technical-reference) hakkında daha fazla bilgi edinin.



## <a name="july-2017"></a>Temmuz 2017

### <a name="restrict-android-and-ios-device-enrollment-restriction-by-os-version------1333256--1245463----"></a>Android ve iOS cihaz kaydı kısıtlamasını işletim sistemi sürümüyle kısıtlama <!--- 1333256,  1245463 --->
Intune artık iOS ve Android kaydını işletim sistemi sürüm numarasına göre kısıtlamayı desteklemektedir. BT yöneticisi bundan sonra, **Cihaz Türü Kısıtlaması**'nın altından kaydı en düşük ve en yüksek işletim sistemi değerleri arasında bir platform yapılandırmasını sınırlamak üzere ayarlayabilir. Android işletim sistemi sürümleri Büyük.Küçük.Derleme.Düzeltme olarak belirtilmelidir. Burada Küçük, Derleme ve Düzeltme isteğe bağlıdır. iOS sürümleri ise Büyük.Küçük.Derleme olarak belirtilmelidir; burada Küçük ve Derleme isteğe bağlıdır. [Cihaz kaydı kısıtlamaları](enrollment-restrictions-set.md) hakkında daha fazla bilgi edinin.

>[!NOTE]
>Kayıt işlemini Apple kayıt programları veya Apple Configurator ile kısıtlamayın.

### <a name="restrict-android-ios-and-macos-device-personally-owned-device-enrollment------1333272--1333275-1245709----"></a>Android, iOS ve macOS cihazların kişisel cihaz kaydını kısıtlama  <!--- 1333272,  1333275, 1245709 --->
Intune, şirket cihazı IMEI numaralarını güvenilir listeye ekleyerek kişisel cihaz kaydını kısıtlayabilir. Intune artık bu işlevi cihaz seri numarası kullanan iOS, Android ve macOS için genişletmiştir. Intune’a seri numaralarını yükleyerek cihazların şirkete ait olduğunu önceden bildirmiş olursunuz. Kayıt kısıtlamalarını kullanarak kişişel (KCG) cihazları engelleyebilir ve yalnızca şirkete ait cihazların kaydına izin verebilirsiniz. [Cihaz kaydı kısıtlamaları](enrollment-restrictions-set.md) hakkında daha fazla bilgi edinin.

Seri numaralarını içeri aktarmak için **Cihaz kaydı** > **Kurumsal cihaz tanımlayıcıları**’na gidin, **Ekle**’ye tıklayın ve bir .CSV dosyası yükleyin (üst bilgi, seri numarası ve IMEI numaraları gibi ayrıntılar için iki sütun).  Kişisel cihazları kısıtlamak için **Cihaz kaydı** > **Kayıt kısıtlamaları**’na gidin. **Cihaz Türü Kısıtlamaları** altında **Varsayılan**’ı ve daha sonra **Platform Yapılandırmaları**’nı seçin. iOS, Android ve macOS kişisel cihazlar için **İzin Ver** veya **Engelle** seçeneklerinden birini belirtebilirsiniz. 


### <a name="new-device-action-to-force-devices-to-sync-with-intune----711369---"></a>Cihazları Intune ile eşitlemeye zorlayan yeni bir cihaz eylemi <!-- 711369 -->
Bu sürümde, seçili cihazı Intune ile hemen iade etmeye zorlayan yeni bir cihaz eylemi ekledik. Bir cihaz giriş yaptığında, kendisine atanan beklemedeki eylem veya ilkeleri hemen alır.  Bu eylem, atadığınız ilkeleri bir sonraki zamanlanmış iadeyi beklemenize gerek kalmadan hızla doğrulamanız ve ilkelerin sorunlarını gidermenize yardımcı olur.
Ayrıntılar için bkz. [Cihaz eşitleme](device-sync.md)

### <a name="force-supervised-ios-devices-to-automatically-install-the-latest-available-software-update----777100---"></a>Denetimli iOS cihazları, son yazılım güncelleştirmesini yüklemeye zorlama <!-- 777100 -->
Denetimli iOS cihazları mevcut son yazılım güncelleştirmesini otomatik olarak yüklemeye zorlayabileceğiniz Yazılım güncelleştirmeleri çalışma alanında yeni bir ilke kullanılabilir durumdadır. Ayrıntılar için bkz. [iOS güncelleştirme ilkelerini yapılandırma](/intune/software-updates-ios)

### <a name="check-point-sandblast-mobile---new-mobile-threat-defense-partner-----954651-1172027---"></a>Check Point SandBlast Mobile - Yeni Mobile Threat Defense iş ortağı  <!-- 954651, 1172027 -->
Microsoft Intune ile tümleşik çalışan mobil tehdit savunması çözümü Checkpoint SandBlast Mobile tarafından gerçekleştirilen risk değerlendirmesine dayalı koşullu erişimi kullanarak mobil cihazlardan şirket kaynaklarına erişimi denetleyebilirsiniz.

#### <a name="how-integration-with-intune-works"></a>Intune ile tümleştirme nasıl çalışır?
Risk, Checkpoint SandBlast Mobile çalıştıran cihazlardan toplanan telemetriye göre değerlendirilir. Intune cihaz uyumluluk ilkeleri aracılığıyla etkinleştirilen Checkpoint SandBlast Mobile risk değerlendirmesine dayalı olarak EMS koşullu erişim ilkeleri yapılandırabilirsiniz. Algılanan tehditlere dayalı olarak uyumlu olmayan cihazların şirket kaynaklarına erişmesine izin verebilir ya da erişimi engelleyebilirsiniz.


### <a name="deploy-an-app-as-available-in-the-microsoft-store-for-business----748101---"></a>Bir uygulamayı İş için Microsoft Mağazası’nda kullanılabilir olarak dağıtma <!-- 748101 -->
Bu sürümle birlikte, yöneticiler artık İş için Microsoft Mağazası’nı kullanılabilir olarak atayabilir. Kullanılabilir olarak ayarlandığında, son kullanıcılar Microsoft Mağazası’na yönlendirilmeden uygulamayı Şirket Portalı uygulamasından veya web sitesinden yükleyebilir.

### <a name="ui-updates-to-the-company-portal-website---1313244-part-1--"></a>Şirket Portalı web sitesine kullanıcı arabirimi güncelleştirmeleri <!--1313244 part 1-->
Son kullanıcı deneyimini geliştirmek için [Şirket Portalı Web sitesinin](https://portal.manage.microsoft.com) kullanıcı arabiriminde bazı güncelleştirmeler yaptık.

- __Uygulama kutucuklarında yapılan geliştirmeler__: Uygulama simgeleri artık simgedeki baskın renge göre (algılanabilirse) otomatik olarak oluşturulmuş bir arka plan ile görüntülenecektir. Uygun olduğunda, bu arka plan daha önce uygulama kutucuklarında görünen gri kenarlıkların yerine geçer.

    Şirket Portalı web sitesi, gelecek bir sürümde mümkün olduğunda büyük simgeler gösterecektir. BT yöneticilerinin en az 120x120 piksel boyutuna sahip yüksek çözünürlüklü simgeler kullanarak uygulama yayımlamalarını öneririz. 

- __Gezinti değişiklikleri__ Gezinti çubuğu öğeleri, sol üstteki hamburger menüsüne taşındı. Kategoriler sayfası kaldırıldı. Kullanıcılar artık gözatma sırasında içeriği kategorilere göre filtreleyebilir.

- __Öne Çıkan Uygulama Güncelleştirmeleri__: Kullanıcıların öne çıkarmak istediğiniz uygulamalara göz atabileceği siteye ayrı bir sayfa ekledik ve giriş sayfasındaki Öne Çıkan sekmesinde bazı kullanıcı arabirimi değişiklikleri yaptık.

### <a name="ibooks-support-for-the-company-portal-website---1231841--"></a>Şirket Portalı web sitesine yönelik iBooks desteği <!--1231841-->
Şirket Portalı web sitesine, kullanıcıların iBooks’a göz atıp kitap indirmesine olanak tanıyan özel bir sayfa ekledik. 


### <a name="additional-help-desk-troubleshooting-details------applies-to-1263399-1326964-1341642----"></a>İlave yardım masası sorun giderme ayrıntıları <!---  Applies to 1263399, 1326964, 1341642 --->
Intune, sorun giderme ekranını güncelleştirdi ve yöneticilerle yardım masası çalışanları için sağladığı bilgileri artırdı. Artık, kullanıcı tabanlı grup üyeliği için tüm atamaları özetleyen bir **Atamalar** tablosu görebilirsiniz. Liste şunları içerir:
- Mobil uygulamalar
- Uyumluluk ilkeleri
- Yapılandırma profilleri
 
Ayrıca **Cihazlar** tablosu artık **Azure AD katılım türü** ve**Azure AD uyumlu** sütunlarını içeriyor. Daha fazla bilgi için bkz. [kullanıcıların sorunlarını gidermeye yardım etme](help-desk-operators.md).



### <a name="intune-data-warehouse-public-preview"></a>Intune Veri Ambarı (Genel Önizleme)
Intune Veri Ambarı, kiracınızın geçmiş bilgilerini görüntülemenizi sağlamak için her gün veri örnekleri sağlar. Verilere bir Power BI dosyası (PBIX), birçok analiz aracıyla uyumlu bir OData bağlantısı kullanarak veya REST API’si ile etkileşimde bulunarak erişebilirsiniz. Daha fazla bilgi için bkz. [Intune Veri Ambarı’nı Kullanma](reports-nav-create-intune-reports.md).


### <a name="light-and-dark-modes-available-for-the-company-portal-app-for-windows-10----676547---"></a>Windows 10 için Şirket Portalı uygulamasında açık ve koyu modlar kullanılabilir <!---676547--->
Windows 10 için Şirket Portalı uygulamasında son kullanıcılar, renk modunu özelleştirebilecek. Kullanıcılar bu değişikliği Şirket Portalı uygulamasının Ayarlar kısmından yapabilir. Değişiklik, kullanıcı uygulamayı yeniden başlattığında görünecektir. Windows 10 sürüm 1607 ve üzeri için uygulama modu varsayılan olarak sistem ayarında olacaktır. Windows 10 sürüm 1511 ve öncesi için uygulama modu varsayılan olarak açık modda olacaktır.

### <a name="enable-end-users-to-tag-their-device-group-in-the-company-portal-app-for-windows-10----807046--"></a>Windows 10 için Şirket Portalı uygulamasında son kullanıcıların cihaz gruplarını etiketlemelerine izin verme <!---807046-->
Son kullanıcılar, artık doğrudan Windows 10 için Şirket Portalı uygulamasında cihazlarının hangi gruba ait olduğunu etiketleyerek cihaz gruplarını belirleyebilir.



## <a name="june-2017"></a>Haziran 2017

### <a name="new-role-based-administration-access-for-intune-admins------1099990---"></a>Intune yöneticileri için yeni rol tabanlı yönetim erişimi   <!-- 1099990 -->  
Azure AD Koşullu Erişim ilkelerini görüntülemek, oluşturmak, değiştirmek ve silmek için yeni bir koşullu erişim yönetim rolü ekleniyor. Daha önce yalnızca genel yöneticiler ve güvenlik yöneticileri bu izne sahipti. Koşullu erişim ilkelerine erişebilmeleri için Intune yöneticilerine bu rolün izinleri verilebilir.


### <a name="tag-corporate-owned-devices-with-serial-number----1215070---"></a>Şirkete ait cihazları seri numarasıyla etiketleme <!-- 1215070 -->  
Intune artık iOS, macOS ve Android seri numaralarını Kurumsal Cihaz Tanımlayıcıları olarak karşıya yüklemeyi destekliyor. Seri numaralar kayıt sırasında doğrulanmadığı için bu numaraları henüz kişisel cihazların kaydedilmesini engellemek için kullanamazsınız. Kişisel cihazları seri numarasına göre engelleme, yakın bir gelecekte çıkacak.


### <a name="new-remote-actions-for-ios-devices----854689---"></a>iOS cihazları için yeni uzak eylemler <!-- 854689 -->
Bu sürümde, Apple Classroom uygulamasını yöneten paylaşılan iPad cihazlar için iki yeni uzak cihaz eylemi ekledik:

-   [Geçerli kullanıcının oturumunu kapat](device-logout-user.md) - Seçtiğiniz bir iOS cihazının geçerli kullanıcısının oturumunu kapatır.
-   [Kullanıcı kaldır](device-remove-user.md) - Bir iOS cihazdaki yerel önbellekten seçtiğiniz bir kullanıcıyı siler.


### <a name="support-for-shared-ipads-with-the-ios-classroom-app----1044681---"></a>iOS Classroom uygulaması ile paylaşılan iPad'ler için destek <!-- 1044681 -->
Bu sürümde, iOS Classroom uygulamasının kapsamını, paylaşılan iPad’lerde yönetilen Apple kimliklerini kullanarak oturum açan öğrencileri de içerecek şekilde genişlettik.


### <a name="changes-to-intune-built-in-apps----1332306---"></a>Intune yerleşik uygulamalarındaki yenilikler <!-- 1332306 -->
Eskiden Intune’da hızlıca atayabileceğiniz birkaç yerleşik uygulama vardı. Geri bildirimlerinize dayanarak bu listeyi kaldırdık, artık yerleşik uygulamaları görmeyeceksiniz.
Ancak herhangi bir yerleşik uygulamayı önceden atadıysanız bu uygulamalar, uygulama listesinde görünmeye devam edecektir. Bu cihazları gerektiği gibi atamaya devam edebilirsiniz.
Sonraki bir sürümde, Azure portalında yerleşik uygulama seçme ve atama için daha kolay bir yöntem eklemeyi planlıyoruz.

### <a name="easier-installation-of-office-365-apps-----1121362----"></a>Office 365 uygulamalarında yükleme kolaylığı <!--- 1121362 --->
Yeni **Office 365 ProPlus** uygulama türü, Office 365 ProPlus 2016 uygulamalarını Windows 10’un en son sürümünü çalıştıran yönettiğiniz cihazlara atamayı kolaylaştırır. Bunun yanı sıra, Microsoft Project ve Microsoft Visio lisanslarınız varsa bu uygulamaları yükleyebilirsiniz. İstediğiniz uygulamalar birlikte paketlenir ve Intune konsolundaki uygulamalar listesinde tek uygulama olarak gösterilir.
Daha fazla bilgi için bkz. [Windows 10 için Office 365 uygulamaları ekleme](apps-add-office365.md).


### <a name="support-for-offline-apps-from-the-microsoft-store-for-business-----777044----"></a>İş İçin Microsoft Mağazası uygulamaları için çevrimdışı desteği <!--- 777044 --->
İş için Microsoft Mağazası’ndan satın aldığınız çevrimdışı uygulamalar, artık Azure portalına eşitlenecektir. Daha sonra bu uygulamaları cihaz gruplarına veya kullanıcı gruplarına dağıtabilirsiniz. Çevrimdışı uygulamalar, mağaza tarafından değil Intune tarafından yüklenir.

### <a name="microsoft-teams-is-now-part-of-the-app-based-ca-list-of-approved-apps------1257019---"></a>Microsoft Teams artık onaylı uygulamaların Uygulama temelli CA listesinin bir parçasıdır   <!-- 1257019 -->
iOS ve Android için Microsoft Teams uygulaması artık Exchange ve SharePoint Online için uygulama tabanlı koşullu erişim ilkeleri onaylı uygulamalarının bir parçasıdır. Uygulamayı, uygulama tabanlı koşullu erişim kullanmakta olan tüm kiracıların Azure portalındaki Intune Uygulama Koruması dikey penceresinde yapılandırabilirsiniz.

### <a name="managed-browser-and-app-proxy-integration----1287310---"></a>Managed Browser ve uygulama proxy’si tümleştirmesi <!-- 1287310 -->
Intune Managed Browser artık Azure AD Uygulama Proxy’si hizmeti ile tümleştirilebilir ve bu sayede kullanıcılar uzaktan çalışsalar bile dahili web sitelerine erişebilirler. Tarayıcıyı kullanırken her zaman yaptığınız gibi site URL’sini girmeniz yeterlidir, Managed Browser bu isteği uygulama proxy’si web ağ geçidine yönlendirecektir. Daha fazla bilgi için bkz. [Managed Browser ilkeleri kullanarak İnternet erişimini yönetme](app-configuration-managed-browser.md).

### <a name="new-app-configuration-settings-for-the-intune-managed-browser----682951---"></a>Intune'la Managed Browser için yeni uygulama ayarları <!-- 682951 -->
Bu sürümde, iOS ve Android için Intune Managed Browser uygulamasına ilave yapılandırmalar ekledik. Artık tarayıcının varsayılan giriş sayfasını ve yer işaretlerini yapılandırmak için bir uygulama yapılandırma ilkesi kullanabilirsiniz.
Daha fazla bilgi için bkz. [Managed Browser ilkeleri kullanarak İnternet erişimini yönetme](app-configuration-managed-browser.md)

### <a name="bitlocker-settings-for-windows-10-----951707---"></a>Windows 10 için BitLocker ayarları <!-- 951707 -->
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


### <a name="company-portal-app-for-android-now-has-a-new-end-user-experience-for-app-protection-policies---1305217--"></a>Android için Şirket Portalı uygulamasının artık Uygulama Koruma İlkeleri için yeni bir son kullanıcı deneyimi vardır <!--1305217-->
Müşteri geri bildirimi doğrultusunda, Android için Şirket Portalı uygulamasını bir **Şirket İçeriğine Eriş** düğmesi gösterecek şekilde değiştirdik. Amaç, son kullanıcıların yalnızca, Intune mobil uygulama yönetiminin bir özelliği olan Uygulama Koruma İlkelerini destekleyen uygulamalara erişmek için gereksiz yere kayıt işlemi yapmalarını engellemektir. Bu değişiklikleri, [uygulama kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md) sayfasında görebilirsiniz.

### <a name="new-menu-action-to-easily-remove-company-portal---1164569--"></a>Şirket Portalını kolayca kaldırmak için yeni menü eylemi <!--1164569-->
Kullanıcı geri bildirimi doğrultusunda, Android için Şirket Portalı uygulaması, Şirket Portalını cihazınızdan kaldırmak için yeni bir menü eylemi ekledi. Bu eylem cihazı Intune yönetiminden kaldırır, böylece uygulama cihazdan kullanıcı tarafından kaldırılabilir. Bu değişiklikleri [Uygulamanın kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md) sayfasında ve [Android son kullanıcı belgelerinde](/intune-user-help/unenroll-your-device-from-intune-android) görebilirsiniz.

### <a name="improvements-to-app-syncing-with-windows-10-creators-update---676505--"></a>Windows 10 Creators Güncelleştirmesi ile uygulama eşitleme geliştirmeleri <!--676505-->
Windows 10 için Şirket Portalı uygulaması, Windows 10 Creators Update (sürüm 1703) içeren cihazlarda uygulama yükleme istekleri için eşitlemeyi artık otomatik olarak başlatacak. Bu, “Eşitleme Bekleniyor” durumu sırasında bekletilen uygulama yüklemeleri sorununu azaltacak. Buna ek olarak, kullanıcılar uygulamanın içinden el ile eşitleme başlatabilecek. Bu değişiklikleri, [uygulama kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md) sayfasında görebilirsiniz.

### <a name="new-guided-experience-for-windows-10-company-portal----1058938---"></a>Windows 10 Şirket Portalı için kullanıcının yönlendirildiği yeni deneyim <!---1058938--->
Windows 10 için Şirket Portalı uygulaması, tanımlanmamış veya kaydedilmemiş cihazlar için kullanıcının adım adım yönlendirildiği bir Intune deneyimi içerecek. Yeni deneyim, kullanıcıya Azure Active Directory kaydı sürecinde (Koşullu Erişim özelliklerinde gereklidir) ve MDM kaydı sürecinde (cihaz yönetim özellikleri için gereklidir) kılavuzluk eden adım adım yönergeler sağlıyor. Kılavuzluk destekli deneyime Şirket Portalı giriş sayfasından erişilebilecek. Kullanıcılar, cihaz kaydettirme ve kaydolma işlemlerini tamamlamasa da uygulamayı kullanmaya devam edebilecek, ancak sınırlı bir işlevsellikleri olacak.

Bu güncelleştirme yalnızca Windows 10 Yıldönümü Güncelleştirmesi (derleme 1607) veya üzerini çalıştıran cihazlarda görünür. Bu değişiklikleri, [uygulama kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md) sayfasında görebilirsiniz.


### <a name="microsoft-intune-and-conditional-access-admin-consoles-are-generally-available"></a>Microsoft Intune ve Koşullu Erişim yönetici konsolları genel olarak kullanılabilir
Azure portalında Intune yönetici konsolu ve Koşullu Erişim yönetici konsolunun genel olarak kullanılabilir olduğunu duyuruyoruz. Azure portalında Intune aracılığıyla, artık tüm Intune MAM ve MDM özelliklerini birleştirilmiş tek bir yönetim deneyiminde yönetebilir ve Azure AD gruplandırma ve hedefleme özelliğinden yararlanabilirsiniz. Azure’da koşullu erişim, Azure AD ve Intune’daki zengin özellikleri birleştirilmiş bir konsol ile bir araya getirir. Yönetim deneyimi açısından ise Azure platformuna geçmek modern tarayıcıları kullanmanıza olanak tanır.

Intune artık portal.azure.com adresindeki Azure portalında **önizleme** etiketi olmadan da görünür durumdadır.

İleti merkezinde gruplarınızın geçişini yapmamız için eylemde bulunmanızı isteyen ileti serilerinden birini almadıysanız şu anda mevcut müşterilerin yapması gereken bir eylem yoktur. Tarafımızdaki hatalardan dolayı geçişinizin daha uzun sürdüğünü belirten bir ileti merkezi bildirimi de almış olabilirsiniz. Etkilenen tüm müşterilerin geçişini tamamlamak üzere titizlikle çalışmaya devam ediyoruz.

### <a name="improvements-to-the-app-tiles-in-the-company-portal-app-for-ios"></a>iOS için Şirket Portalı uygulamasındaki uygulama kutucukları geliştirmeleri
Şirket Portalı için ayarladığınız marka rengini yansıtmak için giriş sayfasındaki uygulama kutucuklarının tasarımı güncelleştirildi. Daha fazla bilgi için bkz. [Uygulamanın kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md).

### <a name="account-picker-now-available-for-the-company-portal-app-for-ios"></a>iOS Şirket Portalı uygulaması için artık hesap seçici kullanılabilir
iOS cihazı kullanıcıları diğer Microsoft uygulamalarında oturum açmak için iş veya okul hesaplarını kullanıyorsa Şirket Portalı uygulamasında oturum açtıklarında yeni hesap seçiciyi görebilirler. Daha fazla bilgi için bkz. [Uygulamanın kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md).

## <a name="may-2017"></a>Mayıs 2017

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
Mağazadaki bazı Android uygulamaları, bir BT yöneticisinin bir uygulamanın iş profilinde nasıl çalışacağını denetlemesine izin veren yönetilen yapılandırma seçeneklerini destekler. Intune ile artık bir uygulama tarafından desteklenen yapılandırmaları görüntüleyebilir ve bunları bir yapılandırma tasarımcısı veya JSON düzenleyicisi ile Azure portalından yapılandırabilirsiniz. Daha fazla bilgi için bkz. [Android for Work için uygulama yapılandırmaları kullanma](app-configuration-policies-use-android.md).

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
- Yalnızca bir iş profili geçiş kodu ilkesi tanımlama - İş profilindeki bir uygulama her açıldığında kullanıcılardan geçiş kodunu girmesi istenir.
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



## <a name="april-2017"></a>Nisan 2017

### <a name="support-for-managing-the-apple-classroom-app"></a>Apple Classroom uygulamasını yönetme desteği
Artık iOS Classroom uygulamasını iPad cihazlarında yönetebilirsiniz. Doğru sınıf ve öğrenci verileriyle Classroom uygulamasını öğretmenin iPad cihazına kurun ve sınıfa kayıtlı öğrencilerin iPad cihazlarını uygulamayı kullanarak denetlemek için yapılandırın.
Ayrıntılar için bkz. [iOS eğitim ayarlarını yapılandırma](education-settings-configure-ios.md).

### <a name="support-for-managed-configuration-options-for-android-apps----621621---"></a>Android uygulamaları için yönetilen yapılandırma seçenekleri desteği <!-- 621621 -->
Playstore'da yer alan ve yönetilen yapılandırma seçeneklerini destekleyen Android uygulamaları, artık Intune tarafından yapılandırılabilir.  Bu özellik, BT ekibinin bir uygulama tarafından desteklenen yapılandırma değerlerinin listesini görüntülemesini sağlar ve bu değerlerin yapılandırılması için kılavuzlu bir birinci sınıf kullanıcı arabirimi sunar.

### <a name="new-android-policy-for-complex-pins----722069---"></a>Karmaşık PIN'ler için yeni Android ilkesi <!-- 722069 -->
Artık Android 5.0 ve üzeri çalıştıran cihazların Android cihaz profilinde Sayısal karmaşık türünde [parola](device-restrictions-android.md#password) gereksinimi belirleyebilirsiniz.  Bu ayarı kullanarak cihaz kullanıcılarının 1111 veya 1234 gibi tekrar eden ya da ardışık rakamlardan oluşan PIN'ler oluşturmasını engelleyebilirsiniz.

### <a name="additional-support-for-android-for-work-devices"></a>Android for Work cihazları için ek destek
- **Parola ve iş profili ayarlarını yönetin** <!-- 612808 -->

  Bu yeni Android for Work cihaz kısıtlama ilkesi artık yönettiğiniz Android for Work cihazlarında parola ve iş profili ayarlarını yönetmenizi sağlar.

- **İş ve kişisel profiller arasında veri paylaşımına izin verin** <!-- 1045102 -->

Bu Android for Work cihaz kısıtlama profili artık iş ve kişisel profiller arasında veri paylaşımını yapılandırmanıza yardımcı olan yeni seçenekler sunar.

- **İş ve kişisel profiller arasında kopyalama ve yapıştırma işlemlerini kısıtlama** <!-- 1046094 -->

  Android for Work cihazları için yeni bir özel cihaz profili, artık iş ve kişisel uygulamalar arasında kopyala ve yapıştır eylemlerini kısıtlayabilmenizi sağlar.

Daha fazla bilgi için bkz. [Android for Work için cihaz kısıtlamaları](device-restrictions-android-for-work.md).

### <a name="assign-lob-apps-to-ios-and-android-devices----1057568---"></a>iOS ve Android cihazlara LOB uygulamaları atama <!-- 1057568 -->
Artık [iOS](lob-apps-ios.md) (.ipa dosyaları) ve [Android](lob-apps-android.md) (.apk dosyaları) için iş kolu (LOB) uygulamalarını kullanıcılara veya cihazlara atayabilirsiniz.


###  <a name="new-device-policies-for-ios----723774-723815-723826-723830---"></a>iOS için yeni cihaz ilkeleri <!-- 723774, 723815, 723826, 723830 -->
- **Giriş ekranındaki uygulamalar** - Kullanıcıların [iOS cihazlarının giriş ekranında](home-screen-settings-ios.md) göreceği uygulamaları denetler. Bu ilke, Giriş ekranının düzenini değiştirir ancak herhangi bir uygulama dağıtmaz.

- **AirPrint cihazlarıyla bağlantı** - Bir iOS cihazı son kullanıcılarının bağlanabileceği [AirPrint cihazlarını](air-print-settings-ios-macos.md) (ağ yazıcılarını) denetler.

- **AirPlay cihazlarıyla bağlantı** - Bir iOS cihazı son kullanıcılarının bağlanabileceği [AirPlay cihazlarını](airplay-settings-ios.md) (Apple TV gibi) denetler.

- **Özel kilit ekranı iletisi** - Kullanıcıların iOS cihazlarının kilit ekranında varsayılan kilit ekranı iletisi yerine göreceği özel bir ileti yapılandırır. Daha fazla bilgi için bkz. [iOS cihazlarında kayıp modunu etkinleştirme](device-lost-mode.md)

### <a name="restrict-push-notifications-for-ios-apps----723767---"></a>iOS uygulamaları için anında iletme bildirimlerini kısıtlama <!-- 723767 -->
Bir Intune cihaz kısıtlama profilinde iOS cihazlar için artık aşağıdaki [bildirim ayarlarını](app-notification-settings-ios.md) yapılandırabilirsiniz:

- Belirli bir uygulama için bildirimleri tamamen açma veya kapatma.
- Belirli bir uygulama için bildirim merkezindeki bildirimleri açma veya kapatma.
- Uyarı için **Yok**, **Başlık** veya **Uyarı** türünü belirleme.
- Bu uygulama için rozetlere izin verilip verilmeyeceğini belirleme.
- Bildirim seslerine izin verilip verilmeyeceğini belirleme.

### <a name="configure-ios-apps-to-run-in-single-app-mode-autonomously----737837---"></a>iOS uygulamalarını otonom tek uygulama modunda çalışacak şekilde yapılandırma <!-- 737837 -->
Bir Intune cihaz profili kullanarak belirtilen uygulamaları artık [otonom tek uygulama modunda](device-restrictions-ios.md#autonomous-single-app-mode-supervised-only) çalışacak şekilde iOS cihazlarını yapılandırabilirsiniz. Bu mod yapılandırılıp uygulama çalıştırıldığında cihaz yalnızca belirtilen uygulamayı çalıştıracak şekilde kilitlenir. Buna örnek olarak kullanıcıların cihazda test çözmesini sağlayan bir uygulama verilebilir. Uygulamanın eylemleri tamamlandığında veya bu ilkeyi kaldırdığınızda cihaz normal durumuna geri döner.

### <a name="configure-trusted-domains-for-email-and-web-browsing-on-ios-devices----723765---"></a>iOS cihazlarda e-posta ve web üzerinde gezinme için güvenilen etki alanlarını yapılandırma <!-- 723765 -->
Artık bir iOS cihaz kısıtlama profilinden aşağıdaki [etki alanı ayarlarını](device-restrictions-ios.md#domains) yapılandırabilirsiniz:

- **İşaretlenmemiş e-posta etki alanları** - Son kullanıcı tarafından gönderilen veya alınan ve burada belirttiğiniz etki alanlarıyla eşleşmeyen e-postalar, güvenilmeyen olarak işaretlenir.

- **Yönetilen web etki alanları** - Burada belirttiğiniz URL'lerden indirilen belgeler, yönetilen belgeler olarak değerlendirilir (yalnızca Safari).  

- **Safari otomatik parola doldurma etki alanları (yalnızca denetimli)** - Kullanıcılar yalnızca burada belirttiğiniz desenlerle eşleşen URL'lerdeki parolaları Safari'ye kaydedebilir. Bu ayarı kullanabilmeniz için cihazın denetimli modda olması ve birden fazla kullanıcı için yapılandırılmış olmaması gerekir. (iOS 9.3 ve üzeri)


### <a name="vpp-apps-available-in-ios-company-portal----748782---"></a>iOS Şirket Portalında VPP uygulamaları kullanılabilir <!-- 748782 -->
iOS toplu satın alınan (VPP) uygulamalarını son kullanıcılara artık **Kullanılabilir** yüklemeler olarak atayabilirsiniz. Son kullanıcıların uygulamayı yükleyebilmek için bir Apple Store hesabına sahip olmaları gerekir.

### <a name="synchronize-ebooks-from-apple-vpp-store----800878---"></a>Apple VPP Store'dan alınan eKitapları eşitleme <!-- 800878 -->
Apple Volume Purchase Program mağazasından satın aldığınız kitapları artık Intune ile [eşitleyebilir](vpp-apps-ios.md) ve kullanıcılara atayabilirsiniz.

### <a name="multi-user-management-for-samsung-knox-standard-devices----971988---"></a>Samsung KNOX Standard cihazları için birden çok kullanıcı yönetimi <!-- 971988 -->
Samsung KNOX Standard çalıştıran cihazlarda artık Intune ile [birden çok kullanıcı yönetimi](android-enroll.md) gerçekleştirilebilir. Başka bir deyişle kullanıcılar Azure Active Directory kimlik bilgilerini kullanarak cihazda oturum açıp kapatabilir ve cihaz kullanım durumundan bağımsız olarak merkezden yönetilir.  Son kullanıcılar oturum açtığında uygulamalara erişir ve kendilerine uygulanan ilkeleri alır. Kullanıcılar oturumu kapattığında tüm veriler silinir.

### <a name="additional-windows-device-restriction-settings----818566---"></a>Ek Windows cihaz kısıtlama ayarları <!-- 818566 -->
Ek Edge tarayıcısı desteği, cihaz kilit ekranı özelleştirmesi, başlat menüsü özelleştirmeleri, Windows Spot araması duvar kağıdı ve proxy ayarı gibi ek [Windows cihaz kısıtlama ayarları](device-restrictions-windows-10.md) için destek ekledik.

### <a name="multi-user-support-for-windows-10-creators-update----822547---"></a>Windows 10 Creators Update için birden çok kullanıcı desteği <!-- 822547 -->
Windows 10 Creators Update çalıştıran ve Azure Active Directory etki alanına katılmış olan cihazlar için [birden çok kullanıcı yönetimi](windows-enroll.md) desteği ekledik. Bu, değişik standart kullanıcılar cihazlarında Azure AD kimlik bilgileriyle oturum açtıklarında, kullanıcı adlarına atanan tüm uygulama ve ilkeleri alacakları anlamına gelir. Kullanıcılar, uygulama yükleme gibi self servis senaryoları için Şirket Portalını şu anda kullanamaz.

### <a name="fresh-start-for-windows-10-pcs---1004830---"></a>Windows 10 PC'ler Fresh Start<!-- 1004830 -->
Windows 10 PC'ler için yeni bir [Fresh Start cihaz eylemi](device-fresh-start.md) artık kullanılabilir.  Bu eylemi düzenlediğinizde PC'ye önceden yüklenmiş olan uygulamalar kaldırılır ve PC otomatik olarak en son Windows sürümüne güncelleştirilir. Bu eylem genellikle yeni bir PC ile gelen önceden yüklü OEM uygulamalarının kaldırılmasına yardımcı olması için kullanılabilir. Bu cihaz eylemi düzenlendiğinde kullanıcı verilerinin tutulup tutulmayacağını yapılandırabilirsiniz.

### <a name="additional-windows-10-upgrade-paths----903672---"></a>Ek Windows 10 yükseltme yolları <!-- 903672 -->
Artık, cihazları aşağıdaki ek Windows 10 sürümlerine yükseltmek için bir [sürüm yükseltme ilkesi](edition-upgrade-configure-windows-10.md) oluşturabilirsiniz:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N

### <a name="bulk-enroll-windows-10-devices----747607---"></a>Windows 10 cihazlarını toplu kaydetme <!-- 747607 -->
Artık, Windows Yapılandırma Tasarımcısı (WCD) kullanarak Windows 10 Creators Update çalıştıran çok sayıda cihazın Azure Active Directory ve Intune’a katılmasını sağlayabilirsiniz. Azure AD kiracınız için [Toplu MDM kaydını](windows-bulk-enroll.md) etkinleştirmek için Windows Yapılandırma Tasarımcısı kullanarak cihazların Azure AD kiracınıza katılmasını sağlayan bir sağlama paketi oluşturun ve paketi toplu kaydetmek ve yönetmek istediğiniz şirkete ait cihazlara uygulayın. Paket cihazlarınıza uygulandıktan sonra cihazlar Azure AD'ye katılır, Intune'a kaydolur ve Azure AD kullanıcılarınızın oturum açmasına hazır hale gelir.  Azure AD kullanıcıları, bu cihazlarda standart kullanıcılardır ve atanan ilkeleri ve gerekli uygulamaları alırlar. Self servis ve Şirket Portalı senaryoları şu anda desteklenmemektedir.

### <a name="new-mam-settings-for-pin-and-managed-storage-locations----581122-736644---"></a>PIN ve yönetilen depolama konumları için yeni MAM ayarları <!-- 581122, 736644 -->
Mobil uygulama yönetimi (MAM) senaryolarında size yardımcı olacak iki yeni uygulama ayarı artık mevcuttur:

- **Cihaz PIN'i yönetildiğinde uygulama PIN'ini devre dışı bırak** - Kaydedilen cihazda bir cihaz PIN'i olup olmadığını algılar ve varsa uygulama koruma ilkeleri tarafından tetiklenen uygulama PIN'ini atlar. Bu ayar, kayıtlı cihazda MAM özellikli bir uygulamayı açan kullanıcılara gösterilen PIN istemi sayısının azaltılmasını sağlar. Bu özellik hem Android hem de iOS için kullanılabilir.

- **Şirket verilerinin kaydedilebileceği depolama hizmetlerini seçin** - Şirket verilerinin kaydedileceği depolama konumlarını belirtmenizi sağlar. Kullanıcılar seçilen depolama konumu hizmetlerine veri kaydedebilir ve listede olmayan diğer tüm depolama konumu hizmetleri engellenir.

  Desteklenen depolama konumu hizmetlerin listesi:

  - OneDrive
  - İş SharePoint Online
  - Yerel depolama

### <a name="help-desk-troubleshooting-portal----907448---"></a>Yardım masası sorun giderme portalı <!-- 907448 -->
Yeni [sorun giderme portalı](help-desk-operators.md), yardım masası operatörlerinin ve Intune yöneticilerinin, kullanıcıları ve cihazlarını görüntülemesine ve Intune teknik sorunlarını çözmek için görevler gerçekleştirmelerine izin verir.

## <a name="march-2017"></a>Mart 2017

### <a name="support-for-ios-lost-mode---431695--"></a>İOS Kayıp Modu desteği <!--431695-->
Intune, iOS 9.3 ve üzeri cihazlar için **Kayıp Modu** desteği ekledi. Artık bir cihazı kilitleyerek tüm kullanımını önleyebilir, cihaz kilit ekranında bir ileti ve iletişim telefon numarası görüntüleyebilirsiniz.

Bir yönetici Kayıp Modu’nu devre dışı bırakmadıkça son kullanıcılar cihazın kilidini açamaz. Kayıp modu etkin olduğunda, **Cihazı bul** eylemini kullanarak cihazın coğrafi konumunu Intune konsolundaki bir haritada görüntüleyebilirsiniz.

Cihazın DEP aracılığıyla kaydedilen ve denetimli modda olan, şirkete ait bir iOS cihazı olması gerekir.

Daha fazla bilgi için bkz. [Microsoft Intune cihaz yönetimi nedir](device-management.md)?

### <a name="improvements-to-device-actions-report---677150--"></a>Cihaz Eylemler raporu geliştirmeleri <!--677150-->
Performansı artırmak için Cihaz Eylemler raporunda geliştirmeler yaptık. Bundan sonra ek olarak rapor durumuna göre filtre uygulayabilirsiniz. Örneğin, yalnızca tamamlanan cihaz eylemlerini gösterecek şekilde rapora filtre uygulayabilirsiniz."

### <a name="custom-app-categories---748805--"></a>Özel uygulama kategorileri <!--748805-->
Artık Intune’a eklediğiniz uygulamalar için kategoriler oluşturabilir, düzenleyebilir ve atayabilirsiniz. Şu anda kategoriler yalnızca İngilizce olarak belirtilebilir.
Bkz. [Intune'a uygulama ekleme](apps-add.md).

### <a name="assign-lob-apps-to-users-with-unenrolled-devices---748823--"></a>Kaydedilmemiş cihaz kullanıcılarına LOB uygulamaları atama <!--748823-->
Cihazları Intune'a kayıtlı olsun ya da olmasın, artık kullanıcılara mağazadan iş kolu uygulamaları atayabilirsiniz. Kullanıcıların cihazları Intune’a kayıtlı değilse yüklemek için Şirket Portalı uygulaması yerine Şirket Portalı web sitesine gitmeleri gerekir.

### <a name="new-compliance-reports---846671--"></a>Yeni uyumluluk raporları <!--846671-->
Artık şirketinizdeki cihazların uyumluluk durumunu size sağlayan ve kullanıcılarınızın karşılaştığı uyumluluk sorunlarını hızlı bir şekilde gidermenize olanak tanıyan uyumluluk raporlarına sahipsiniz. Aşağıdaki konular hakkındaki bilgileri görüntüleyebilirsiniz:

- Cihazların genel uyumluluk durumu
- Ayrı bir ayarın uyumluluk durumu
- Ayrı bir ilkenin uyumluluk durumu

Bu raporları ayrıca bir cihazı incelemek ve cihazı etkileyen belirli ayar ve ilkeleri görüntülemek için de kullanabilirsiniz.

<!--- You can now create an edition upgrade policy to upgrade devices to the following additional Windows 10 editions:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N --->

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Apple kayıt senaryolarına doğrudan erişim <!--951869-->
Intune, Azure portalındaki Cihaz Kaydetme iş yükünü kullanarak Apple kayıt senaryolarına doğrudan erişimi Ocak 2017 sonrasında oluşturulan Intune hesapları için etkinleştirdi. Daha önce, Apple kayıt önizleme sürümüne yalnızca Azure portalı bağlantıları ile erişilebiliyordu. Bu özelliklerin Azure’da kullanılabilmesi için, Ocak 2017 öncesi oluşturulan Intune hesaplarında tek seferlik bir geçiş yapılması gerekir. Geçiş için zaman çizelgesi henüz açıklanmamıştır, ancak konuya ilişkin ayrıntılar olabildiğince çabuk duyurulacaktır. Mevcut hesabınız önizleme sürümüne erişemiyorsa, yeni deneyimi test etmek için bir deneme hesabı oluşturmanızı kesinlikle öneririz.


## <a name="february-2017"></a>Şubat 2017

### <a name="ability-to-restrict-mobile-device-enrollment---747600-795782--"></a>Mobil cihaz kaydını kısıtlama özelliği <!--747600, 795782-->
Intune, katılmasına izin verilecek mobil cihaz platformlarını denetleyen yeni kayıt kısıtlamaları ekliyor. Intune, mobil cihaz platformlarını iOS, macOS, Android, Windows ve Windows Mobile şeklinde ayırıyor.

* Mobil cihaz kaydının kısıtlanması, bilgisayar istemcisi kaydını etkilemez.  
* Yalnızca iOS ve Android için kişisel cihazların kaydedilmesini engelleyen ek seçenek vardır.

Intune, BT yöneticileri [bu makalede](https://docs.microsoft.com/intune-classic/deploy-use/manage-corporate-owned-devices) anlatılan şekilde kuruluş cihazı olarak işaretlemediği sürece tüm yeni cihazları kişisel cihaz olarak işaretler.

### <a name="view-all-actions-on-managed-devices---677150--"></a>Yönetilen cihazlardaki tüm eylemleri görüntüleme <!--677150-->
Yeni __Cihaz Eylemleri__ raporu cihazları fabrika ayarlarına sıfırlama gibi uzaktan gerçekleştirilen eylemleri kimin yaptığını ve ilgili eylemin durumunu göstermektedir. Bkz. [Cihaz yönetimi nedir?](device-management.md)

### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Yönetilmeyen cihazlar atanmış uygulamalara erişebilir <!--664691-->
Şirket Portalı web sitesinde yapılan tasarım değişikliklerinin bir parçası olarak iOS ve Android kullanıcılar yönetilmeyen cihazlarında kendilerine "kayıtsız kullanılabilir" olarak atanmış uygulamaları yükleyebilecek. Kullanıcılar Intune kimlik bilgilerini kullanarak Şirket Portalı web sitesine girebilecek ve kendilerine atanan uygulamaların listesini görebilecek. "Kayıtsız kullanılabilir" uygulamaların uygulama paketleri Şirket Portalı web sitesinden indirilebilir. Yükleme için kayıt gerektiren uygulamalar bu değişikten etkilenmeyecek ve bu uygulamaları yüklemek isteyen kullanıcılardan cihazlarını kaydetmeleri istenecektir.

### <a name="custom-app-categories---748805--"></a>Özel uygulama kategorileri <!--748805-->
Artık Intune’a eklediğiniz uygulamalar için kategoriler oluşturabilir, düzenleyebilir ve atayabilirsiniz. Şu anda kategoriler yalnızca İngilizce olarak belirtilebilir.
Bkz. [Intune'a uygulama ekleme](apps-add.md).

### <a name="display-device-categories---814654--"></a>Cihaz kategorilerini görüntüleme <!--814654-->
Artık cihaz kategorisini cihaz listesinde ayrı bir sütunda görüntüleyebilirsiniz. Kategoriyi ayrıca cihaz özellikleri dikey penceresinin özellikler bölümünden de düzenleyebilirsiniz. Bkz. [Intune'a uygulama ekleme](apps-add.md).

### <a name="configure-windows-update-for-business-settings---776716--"></a>İşletmeler için Windows Update ayarlarını yapılandırma <!--776716-->

Hizmet olarak Windows, Windows 10 güncelleştirmeleri sağlamanın yeni yoludur. Windows 10’dan itibaren tüm yeni Özellik Güncelleştirmeleri ve Kalite Güncelleştirmeleri, önceki güncelleştirmelerin hepsinde yer alan içerikleri de kapsayacaktır. Böylece, en son güncelleştirmeyi yüklediğiniz sürece Windows 10 cihazlarınızın tamamen güncel olduğundan emin olabilirsiniz. Önceki Windows sürümlerinin aksine, artık güncelleştirmelerin tamamını yüklemeniz gerekir. Güncelleştirmenin yalnızca bir parçası yüklenemez.

İşletmeler için Windows Update’i kullanarak güncelleştirme yönetimi deneyimini, cihaz grupları için tek tek güncelleştirmelerin onaylanması gerekmeyecek şekilde basitleştirebilirsiniz. Ortamlarınızdaki riski yönetmek amacıyla hala bir güncelleştirme dağıtım stratejisi yapılandırabilirsiniz. Böyle yaptığınızda Windows Update güncelleştirmelerin doğru zamanda yüklenmesini sağlayacaktır. Microsoft Intune, cihazlarda güncelleştirme ayarlarının yapılandırılabilmesini sağlar ve güncelleştirme yüklemelerini erteleme olanağı tanır. Intune, güncelleştirmeleri değil yalnızca güncelleştirme ilkesi atamalarını depolar. Cihazlar, güncelleştirmeler için doğrudan Windows Update’e erişir. **Windows 10 güncelleştirme kademelerini** yapılandırmak ve yönetmek için Intune’u kullanın. Güncelleştirme kademesi, Windows 10 güncelleştirmelerinin ne zaman ve nasıl yükleneceğini yapılandıran bir dizi ayar içerir. Daha ayrıntılı bilgiler için bkz. [İşletmeler için Windows Update ayarlarını yapılandırma](windows-update-for-business-configure.md).
