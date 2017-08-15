---
title: Microsoft Intune'daki yenilikler
titleSuffix: Intune on Azure
description: "Intune Azure portalındaki yenilikleri keşfedin"
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 08/10/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f915c805b20e88c661ad52e280a31054bbebce02
ms.sourcegitcommit: 2ed8d1c39d4b3e3282111f1d758afb3a50f19f8f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2017
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
  ### Intune apps
-->   

## <a name="week-of-july-31-2017"></a>31 Temmuz 2017 Haftası

### <a name="device-enrollment"></a>Cihaz kaydı  

#### <a name="restrict-android-and-ios-device-enrollment-restriction-by-os-version------1333256--1245463----"></a>Android ve iOS cihaz kaydı kısıtlamasını işletim sistemi sürümüyle kısıtlama <!--- 1333256,  1245463 --->
Intune artık iOS ve Android kaydını işletim sistemi sürüm numarasına göre kısıtlamayı desteklemektedir. BT yöneticisi bundan sonra, **Cihaz Türü Kısıtlaması**'nın altından kaydı en düşük ve en yüksek işletim sistemi değerleri arasında bir platform yapılandırmasını sınırlamak üzere ayarlayabilir. Android işletim sistemi sürümleri Büyük.Küçük.Derleme.Düzeltme olarak belirtilmelidir. Burada Küçük, Derleme ve Düzeltme isteğe bağlıdır. iOS sürümleri ise Büyük.Küçük.Derleme olarak belirtilmelidir; burada Küçük ve Derleme isteğe bağlıdır. [Cihaz kaydı kısıtlamaları](enrollment-restrictions-set.md) hakkında daha fazla bilgi edinin.

>[!NOTE]
>Kayıt işlemini Apple kayıt programları veya Apple Configurator ile kısıtlamayın.

#### <a name="restrict-android-ios-and-macos-device-personally-owned-device-enrollment------1333272--1333275-1245709----"></a>Android, iOS ve macOS cihazların kişisel cihaz kaydını kısıtlama  <!--- 1333272,  1333275, 1245709 --->
Intune, şirket cihazı IMEI numaralarını güvenilir listeye ekleyerek kişisel cihaz kaydını kısıtlayabilir. Intune artık bu işlevi cihaz seri numarası kullanan iOS, Android ve macOS için genişletmiştir. Intune’a seri numaralarını yükleyerek cihazların şirkete ait olduğunu önceden bildirmiş olursunuz. Kayıt kısıtlamalarını kullanarak kişişel (KCG) cihazları engelleyebilir ve yalnızca şirkete ait cihazların kaydına izin verebilirsiniz. [Cihaz kaydı kısıtlamaları](enrollment-restrictions-set.md) hakkında daha fazla bilgi edinin.

Seri numaralarını içeri aktarmak için **Cihaz kaydı** > **Kurumsal cihaz tanımlayıcıları**’na gidin, **Ekle**’ye tıklayın ve bir .CSV dosyası yükleyin (üst bilgi, seri numarası ve IMEI numaraları gibi ayrıntılar için iki sütun).  Kişisel cihazları kısıtlamak için **Cihaz kaydı** > **Kayıt kısıtlamaları**’na gidin. **Cihaz Türü Kısıtlamaları** altında **Varsayılan**’ı ve daha sonra **Platform Yapılandırmaları**’nı seçin. iOS, Android ve macOS kişisel cihazlar için **İzin Ver** veya **Engelle** seçeneklerinden birini belirtebilirsiniz. 


### <a name="device-management"></a>Cihaz yönetimi   

#### <a name="new-device-action-to-force-devices-to-sync-with-intune----711369---"></a>Cihazları Intune ile eşitlemeye zorlayan yeni bir cihaz eylemi <!-- 711369 -->
Bu sürümde, seçili cihazı Intune ile hemen iade etmeye zorlayan yeni bir cihaz eylemi ekledik. Bir cihaz eşitlendiğinde, kendisine atanan beklemedeki eylem veya ilkeleri hemen alır.  Bu eylem, atadığınız ilkeleri bir sonraki zamanlanmış iadeyi beklemenize gerek kalmadan hızla doğrulamanız ve ilkelerin sorunlarını gidermenize yardımcı olur.
Ayrıntılar için bkz. [Cihaz eşitleme](device-sync.md)

#### <a name="force-supervised-ios-devices-to-automatically-install-the-latest-available-software-update----777100---"></a>Denetimli iOS cihazları, son yazılım güncelleştirmesini yüklemeye zorlama <!-- 777100 -->
Denetimli iOS cihazları mevcut son yazılım güncelleştirmesini otomatik olarak yüklemeye zorlayabileceğiniz Yazılım güncelleştirmeleri çalışma alanında yeni bir ilke kullanılabilir durumdadır. Ayrıntılar için bkz. [iOS güncelleştirme ilkelerini yapılandırma](/intune/software-updates-ios)


#### <a name="check-point-sandblast-mobile---new-mobile-threat-defense-partner-----954651-1172027---"></a>Check Point SandBlast Mobile - Yeni Mobile Threat Defense iş ortağı  <!-- 954651, 1172027 -->
Microsoft Intune ile tümleşik çalışan mobil tehdit savunması çözümü Checkpoint SandBlast Mobile tarafından gerçekleştirilen risk değerlendirmesine dayalı koşullu erişimi kullanarak mobil cihazlardan şirket kaynaklarına erişimi denetleyebilirsiniz.

##### <a name="how-integration-with-intune-works"></a>Intune ile tümleştirme nasıl çalışır?
Risk, Checkpoint SandBlast Mobile çalıştıran cihazlardan toplanan telemetriye göre değerlendirilir. Intune cihaz uyumluluk ilkeleri aracılığıyla etkinleştirilen Checkpoint SandBlast Mobile risk değerlendirmesine dayalı olarak EMS koşullu erişim ilkeleri yapılandırabilirsiniz. Algılanan tehditlere dayalı olarak uyumlu olmayan cihazların şirket kaynaklarına erişmesine izin verebilir ya da erişimi engelleyebilirsiniz.


### <a name="app-management"></a>Uygulama yönetimi

#### <a name="deploy-an-app-as-available-in-the-microsoft-store-for-business----748101---"></a>Bir uygulamayı İş için Microsoft Mağazası’nda kullanılabilir olarak dağıtma <!-- 748101 -->
Bu sürümle birlikte, yöneticiler artık İş için Microsoft Mağazası’nı kullanılabilir olarak atayabilir. Kullanılabilir olarak ayarlandığında, son kullanıcılar Microsoft Mağazası’na yönlendirilmeden uygulamayı Şirket Portalı uygulamasından veya web sitesinden yükleyebilir.


### <a name="intune-apps"></a>Intune uygulamaları  

#### <a name="ui-updates-to-the-company-portal-website---1313244-part-1--"></a>Şirket Portalı web sitesine kullanıcı arabirimi güncelleştirmeleri <!--1313244 part 1-->
Son kullanıcı deneyimini geliştirmek için [Şirket Portalı Web sitesinin](https://portal.manage.microsoft.com) kullanıcı arabiriminde bazı güncelleştirmeler yaptık.

- __Uygulama kutucuklarında yapılan geliştirmeler__: Uygulama simgeleri artık simgedeki baskın renge göre (algılanabilirse) otomatik olarak oluşturulmuş bir arka plan ile görüntülenecektir. Uygun olduğunda, bu arka plan daha önce uygulama kutucuklarında görünen gri kenarlıkların yerine geçer.

    Şirket Portalı web sitesi, gelecek bir sürümde mümkün olduğunda büyük simgeler gösterecektir. BT yöneticilerinin en az 120x120 piksel boyutuna sahip yüksek çözünürlüklü simgeler kullanarak uygulama yayımlamalarını öneririz. 

- __Gezinti değişiklikleri__ Gezinti çubuğu öğeleri, sol üstteki hamburger menüsüne taşındı. Kategoriler sayfası kaldırıldı. Kullanıcılar artık gözatma sırasında içeriği kategorilere göre filtreleyebilir.

- __Öne Çıkan Uygulama Güncelleştirmeleri__: Kullanıcıların öne çıkarmak istediğiniz uygulamalara göz atabileceği siteye ayrı bir sayfa ekledik ve giriş sayfasındaki Öne Çıkan sekmesinde bazı kullanıcı arabirimi değişiklikleri yaptık.

#### <a name="ibooks-support-for-the-company-portal-website---1231841--"></a>Şirket Portalı web sitesine yönelik iBooks desteği <!--1231841-->
Şirket Portalı web sitesine, kullanıcıların iBooks’a göz atıp kitap indirmesine olanak tanıyan özel bir sayfa ekledik. 

### <a name="reporting"></a>Raporlama

#### <a name="intune-data-warehouse-public-preview"></a>Intune Veri Ambarı (Genel Önizleme)

Intune Veri Ambarı, kiracınızın geçmiş bilgilerini görüntülemenizi sağlamak için her gün veri örnekleri sağlar. Verilere bir Power BI dosyası (PBIX), birçok analiz aracıyla uyumlu bir OData bağlantısı kullanarak veya REST API’si ile etkileşimde bulunarak erişebilirsiniz. Daha fazla bilgi için bkz. [Intune Veri Ambarı’nı Kullanma](reports-nav-create-intune-reports.md).


## <a name="week-of-july-23rd-2017"></a>23 Temmuz 2017 haftası

### <a name="light-and-dark-modes-available-for-the-company-portal-app-for-windows-10----676547---"></a>Windows 10 için Şirket Portalı uygulamasında açık ve koyu modlar kullanılabilir <!---676547--->
Windows 10 için Şirket Portalı uygulamasında son kullanıcılar, renk modunu özelleştirebilecek. Kullanıcılar bu değişikliği Şirket Portalı uygulamasının Ayarlar kısmından yapabilir. Değişiklik, kullanıcı uygulamayı yeniden başlattığında görünecektir. Windows 10 sürüm 1607 ve üzeri için uygulama modu varsayılan olarak sistem ayarında olacaktır. Windows 10 sürüm 1511 ve öncesi için uygulama modu varsayılan olarak açık modda olacaktır.

### <a name="enable-end-users-to-tag-their-device-group-in-the-company-portal-app-for-windows-10----807046--"></a>Windows 10 için Şirket Portalı uygulamasında son kullanıcıların cihaz gruplarını etiketlemelerine izin verme <!---807046-->
Son kullanıcılar, artık doğrudan Windows 10 için Şirket Portalı uygulamasında cihazlarının hangi gruba ait olduğunu etiketleyerek cihaz gruplarını belirleyebilir.




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

### <a name="end-of-support-for-ios-80----1164477---"></a>iOS 8.0 desteğinin son bulması <!---1164477--->
Yönetilen uygulamalar ve iOS için Şirket Portalı uygulaması, şirket kaynaklarına erişim için iOS 9.0 ve üzeri sürümleri gerektirecek. Eylül ayından önce güncelleştirmeyen cihazlar, Şirket Portalı veya diğer uygulamalara erişemeyecek. 

### <a name="ui-updates-to-the-company-portal-website---1313244-part-2--"></a>Şirket Portalı web sitesine kullanıcı arabirimi güncelleştirmeleri <!--1313244 part 2-->
__Öne Çıkan Uygulama Güncelleştirmeleri__  
Kullanıcıların öne çıkarmak istediğiniz uygulamalara göz atabileceği siteye ayrı bir sayfa ekledik ve giriş sayfasındaki Öne Çıkan sekmesinde bazı kullanıcı arabirimi değişiklikleri yaptık. Bu değişikliklerin neler olduğunu [uygulama kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md) sayfasında görebilirsiniz.


### <a name="end-of-support-for-android-43-and-lower----1171127-1326920----"></a>Android 4.3 ve altı sürümler için desteğin son bulması<!---1171127, 1326920 --->
Yönetilen uygulamalar ve Android için Şirket Portalı uygulaması, şirket kaynaklarına erişim için Android 4.4 ve üzeri sürümleri gerektirecek. Ekim ayının başından önce güncelleştirmeyen cihazlar, Şirket Portalı veya diğer uygulamalara erişemeyecek. Aralık ayında ise tüm kayıtlı cihazlar zorla devre dışı bırakılıp şirket kaynaklarına erişimleri kaldırılacak. MDM’siz uygulama koruma ilkeleri kullanıyorsanız uygulamalar güncelleştirme almayacak ve deneyimlerinin kalitesi zamanla düşecek.


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
