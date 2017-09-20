---
title: "Erken sürüm"
description: 
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 09/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0ac0d1fd2f618339f847201f333d3f32561ca6b1
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/15/2017
---
# <a name="the-early-edition-for-microsoft-intune---september-2017"></a>Microsoft Intune için erken sürüm - Eylül 2017

**Erken sürüm**, Microsoft Intune'un gelecek sürümlerinde kullanıma sunulacak yeni özelliklerin bir listesini sunar. Bu bilgiler kısıtlı bir kapsamla verilmektedir ve değiştirilebilir. Bu bilgileri şirket dışından kimselerle paylaşmayın. Burada listelenen özelliklerden bazılarının son tarihe yetişememe riski vardır ve gelecek sürüme ertelenebilir. Diğer özellikler, müşterinin kullanımına hazır olduğundan emin olmak için pilot (sürüyor) aşamasında test edilmektedir. Herhangi bir sorunuz veya endişeniz varsa lütfen Microsoft ürün grubu ilgili kişisiyle bağlantı kurun.

Bu sayfa düzenli aralıklarla güncelleştirilir. Ek güncelleştirmeleri daha sonra denetleyin.

> [!Note]
>Intune için aşağıdaki değişiklikler geliştirilme aşamasındadır. Yeni karma özellikler hakkında daha fazla bilgi için, [Karma Yenilikler sayfamızı](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) gözden geçirin.

<!--

## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
   
-->

  

## <a name="intune-in-the-azure-portal"></a>Azure portalında Intune


### <a name="google-play-protect-support-on-android----908720----"></a>Android’de Google Play Protect desteği <!-- 908720  -->  
Android Oreo sürümüyle Google, kuruluşların güvenli uygulamalar çalıştırmasına ve Android görüntülerinin güvenliğini sağlamasına imkan veren Google Play Protect adlı bir güvenlik özellikleri paketi piyasaya sunuyor. Intune, SafetyNet uzak kanıtlama dahil olmak üzere Google Play Protect özelliklerini destekleyecektir.  Yöneticiler, Google Play Protect’ın yapılandırılması ve iyi durumda olmasını gerektiren uyumluluk ilke gereksinimleri ayarlayabilir. **SafetyNet cihaz kanıtlama** ayarı, cihazın iyi durumda olduğu ve güvenliğinin aşılmadığını doğrulamak için cihazın bir Google hizmetiyle bağlanmasını gerektirir. Yöneticiler ayrıca, yüklenen uygulamaların Google Play hizmetleri tarafından doğrulanmasını gerektiren bir Android for Work yapılandırma profili ayarı da ayarlayabilir.  Koşullu erişim, bir cihaz Google Play Protect gereksinimleriyle uyumlu olmadığında kullanıcıların şirket kaynaklarına erişimini engelleyebilir. 

### <a name="prevent-users-of-android-devices-from-changing-their-device-date-and-time-----1333292---"></a>Android cihaz kullanıcılarının cihaz tarih ve saatini değiştirmelerini önleme <!-- 1333292 -->
Android cihaz kullanıcılarının cihaz tarih ve saatini değiştirmelerini önlemek için bir [Android özel cihaz ilkesi](custom-settings-android.md) kullanabilirsiniz.
Bunun için bir Android özel ilkesini ./Vendor/MSFT/PolicyManager/My/System/AllowDateTimeChange ayar URI’si ile yapılandırın, bunu **TRUE** olarak ayarlayın ve gerekli gruplara atayın.

### <a name="view-app-protection-policy-assignments-for-troubleshooting-----1475003---"></a>Sorun giderme için uygulama koruma ilke atamalarını görüntüleme <!--  1475003 -->
Gelecek sürümde, sorun giderme dikey penceresinde bulunan **Atamalar** açılan listesine **Uygulama koruma ilkesi** seçeneği eklenecek. Artık, uygulama koruma ilkelerini seçerek seçili kullanıcılara atanan uygulama koruma ilkelerini görebileceksiniz.

### <a name="create-ios-apps-limited-to-specific-regional-apple-app-stores----1281692---"></a>Belirli bölgesel Apple App Store’lar ile sınırlı iOS uygulamaları oluşturma <!-- 1281692 -->
Bir Apple App Store yönetilen uygulaması oluştururken ülke yerel ayarını belirtebileceksiniz.

> [!NOTE]  
> Şu anda yalnızca ABD mağazasında kullanılabilen Apple App Store yönetilen uygulamaları oluşturabilirsiniz.

### <a name="select-apple-country-store-to-sync-vpp-apps-----1332311---"></a>VPP uygulamalarını eşitlemek için Apple ülke mağazası seçme <!-- 1332311 -->  
VPP belirtecinizi karşıya yüklerken Volume Purchase Program (VPP) ülke mağazasını yapılandırabilirsiniz. Intune, belirtilen VPP ülke mağazasındaki tüm yerel ayarlarla VPP uygulamaları eşitler.

> [!NOTE]  
> Şu anda Intune, yalnızca Intune kiracısının oluşturulduğu Intune yerel ayarına uyan VPP ülke mağazasındaki VPP uygulamaları eşitliyor.

###  <a name="update-ios-vpp-user-and-device-licensed-apps-----1305564---"></a>iOS VPP kullanıcı ve cihaz lisanslı uygulamaları güncelleştirme <!-- 1305564 -->  
Intune hizmeti yoluyla belirteç için satın alınmış tüm uygulamaları güncelleştirmek için bu iOS VPP belirtecini yapılandırabileceksiniz. Intune, uygulama mağazasındaki VPP uygulama güncelleştirmelerini algılayacak ve cihaz iade edildiğinde bunları cihaza otomatik olarak gönderecektir.

### <a name="ios-11-support----1428975---"></a>iOS 11 desteği <!-- 1428975 -->
iOS 11, Apple tarafından yayınlandığında Intune’u destekleyecektir.

### <a name="new-settings-for-windows-10-team-device-restriction-profile------1308838----"></a>Windows 10 Team cihaz kısıtlama profili için yeni ayarlar <!--- 1308838  -->
Bu sürümde, Surface Hub cihazları denetlemenizi kolaylaştırmak için Windows 10 Team cihaz kısıtlama profiline pek çok yeni ayar ekliyoruz.
Bu profil hakkında daha fazla bilgi için bkz. [Windows 10 Team cihaz kısıtlama ayarları](device-restrictions-windows-10-teams.md).

### <a name="support-for-windows-10-edition-upgrade-policy------903672-1119689---"></a>Windows 10 sürüm yükseltme ilkesi desteği <!-- 903672, 1119689 -->  
Windows 10 cihazları Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education ve Windows 10 Professional Education N’e yükselten bir Windows 10 sürüm yükseltme ilkesi oluşturabileceksiniz. Windows 10 sürüm yükseltmeleri hakkında daha fazla bilgi için bkz. [Windows 10 sürüm yükseltmelerini yapılandırma](edition-upgrade-configure-windows-10.md).

### <a name="review-policy-compliance-for-windows-10-update-rings----1352223---"></a>Windows 10 güncelleştirme halkaları için ilke uyumluluğunu gözden geçirme <!-- 1352223 -->  
**Yazılım güncelleştirmeleri** > **Her bir güncelleştirme halkası dağıtımı durumu**’ndan, Windows 10 güncelleştirme halkalarınız için bir ilke raporu görüntüleyebileceksiniz. İlke raporu, yapılandırdığınız güncelleştirme halkaları için dağıtım durumunu da içerir. 

### <a name="windows-10-company-portal-app-added-to-windows-information-protection-allow-policy----677129---"></a>Windows 10 Şirket Portalı uygulaması, Windows Bilgi Koruması izin ilkesine eklendi <!-- 677129 -->  
Windows 10 Şirket Portalı uygulaması, Windows Bilgi Koruması’nı (WIP) destekleyecek şekilde güncelleştirilecek. Uygulama, WIP izin ilkesine eklenebilecek. Bu değişiklik ile uygulamanın **Muaf** listesine eklenme gerekliliği ortadan kalkacak. 

### <a name="remote-support-for-windows-and-windows-mobile-devices-----1070473---"></a>Windows ve Windows Mobile cihazlar için uzak destek <!-- 1070473 -->    
Intune, Windows ve Windows Mobile cihazlar çalıştıran kullanıcılarınıza uzaktan yardım etmenizi sağlamak için ayrıca satın alınan [TeamViewer](https://www.teamviewer.com) yazılımını kullanabilecek.

### <a name="scan-devices-with-windows-defender----1280988--1280990-----"></a>Windows Defender ile cihazları tarama <!-- 1280988  1280990   -->
Yönetilen Windows 10 cihazlarda Windows Defender Virüsten Koruma ile **Hızlı Tarama**, **Tam Tarama** ve **İmza güncelleştirme** işlemleri yapabileceksiniz. Cihazın genel bakış dikey penceresinden cihazda çalıştırılacak eylemi seçin. Komut cihaza gönderilmeden önce eylemi onaylamanız istenir. 

**Hızlı tarama**: Hızlı tarama, kayıt defteri anahtarı ve bilinen Windows başlangıç klasörleri gibi kötü amaçlı yazılımların başladığı konumları tarar. Bir hızlı tarama ortalama beş dakika sürer. Bir dosya açıldığında, kapandığında ve bir kullanıcı bir klasöre gittiğinde dosyaları tarayan **Her zaman açık gerçek zamanlı koruma** ayarıyla birlikte kullanıldığında hızlı tarama, sistemde veya çekirdekte olması mümkün kötü amaçlı yazılımlara karşı koruma sağlamaya yardımcı olur. Tarama bittiğinde kullanıcılar, sonuçları cihazlarında görebilir. 

**Tam tarama**: Tam tarama, etkin olmayan bileşenleri bulunan ve daha kapsamlı bir temizlik gerektiren kötü amaçlı yazılım tehditleriyle karşı karşıya kalan cihazlarda gereklidir ve isteğe bağlı taramalar yapmaya yarar. Tam taramanın tamamlanması bir saati bulabilir. Tarama bittiğinde kullanıcılar, sonuçları cihazlarında görebilir. 

**İmza güncelleştirme**: İmza güncelleştirme komutu, Windows Defender Virüsten Koruma kötü amaçlı yazılım tanımlarını ve imzalarını güncelleştirir. Böylece Windows Defender Virüsten Koruma’nın kötü amaçlı yazılımı algılamada her zaman etkili olması sağlanır. Bu özellik yalnızca Windows 10 cihazlar içindir ve cihaz İnternet bağlantısı gerektirir. 

### <a name="bitlocker-device-configuration----1397398---"></a>BitLocker cihaz yapılandırması <!-- 1397398 -->  
**Windows Şifreleme > Temel Ayarlar** yeni bir **Başka bir disk şifreleme için uyarı** ayarı barındıracak. Bu ayar, kullanıcının cihazında kullanımda olabilecek bir diğer disk şifreleme için [uyarı istemini](https://docs.microsoft.com/en-us/windows/client-management/mdm/bitlocker-csp#allowarningforotherdiskencryption) devre dışı bırakmanızı sağlayacak.  Uyarı istemi, cihazda BitLocker ayarlamadan önce son kullanıcı onayı gerektirir ve son kullanıcı tarafından onaylanana kadar BitLocker kurulumunu engeller.  Bu yeni ayar, son kullanıcı uyarısını devre dışı bırakır.

### <a name="company-portal-for-windows-81-and-windows-phone-81-moving-to-sustaining-mode---1428681--"></a>Windows 8.1 ve Windows Phone 8.1 için Şirket Portalı, dayanıklılık moduna geçiyor <!--1428681-->
Ekim 2017’den itibaren Windows 8.1 ve Windows Phone 8.1 için Şirket Portalı uygulamaları, dayanıklılık moduna geçecek. Yani kayıt ve uyumluluk gibi mevcut senaryolar bu platformlarda desteklenmeye devam edecek. Bu uygulamalar Microsoft Mağazası gibi mevcut yayın kanallarından hala indirilebilir. 

Dayanıklılık moduna geçtikten sonra bu uygulamalar, yalnızca kritik güvenlik güncelleştirmelerini alacak. Bu uygulamalar için ek güncelleştirmeler veya özellikler yayımlanmayacak. Yeni özellikler için cihazları Windows 10 veya Windows 10 Mobile’a güncelleştirmenizi öneririz. 

###  <a name="block-copy-and-paste-between-work-and-personal-profiles-in-android-for-work----1098994---"></a>Android for Work’te iş hesapları ve kişisel hesaplar arasında kopyalama ve yapıştırmayı engelleme <!-- 1098994 -->   
Bu sürümle birlikte, Android for Work iş profilini kopyalama ve yapıştırmayı engelleyecek şekilde yapılandırabilirsiniz. Bu yeni ayarı **İş profili ayarları** altında bulunan **Android for Work** Platformunun **Cihaz kısıtlamaları** profilinde bulabilirsiniz.

### <a name="new-behaviors-for-the-company-portal-app-for-android-with-work-profiles----1485783---"></a>İş profilleri bulunan Android için Şirket Portalı uygulamasında yeni davranışlar <!---1485783--->
Bir Android for Work cihazını iş profiliyle kaydettiğinizde cihazda yönetim görevlerini gerçekleştiren uygulama, iş profilindeki Şirket Portalı’dır. Kişisel profilde MAM özellikli uygulama kullanmıyorsanız Android için Şirket Portalı uygulamasının artık hiçbir kullanımı yoktur. İş profili deneyimini iyileştirmek için Intune, başarılı bir iş profili kaydından sonra kişisel Şirket Portalı uygulamasını otomatik olarak saklar.

İstediğiniz zaman [Play Store’da Şirket Portalı](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) araması yapıp **Etkinleştir**’e dokunarak kişisel profilinizde Android için Şirket Portalı uygulamasını etkinleştirebilirsiniz.

### <a name="intune-mam--outlook-for-android-add-ins-----1450688---"></a>Intune MAM ve Android için Outlook eklentileri <!-- 1450688 -->
Birkaç hafta içerisinde Office ekibi, Android için Outlook eklentilerini duyuracak. Bu eklenti özellikleri kümesi Windows, iOS, web ve Mac için Outlook uygulamalarında zaten mevcuttur. Eklentiler Exchange yoluyla yönetildiğinden, eklentilere erişim Exchange yöneticiniz tarafından kapatılmadığı sürece, kullanıcılar Outlook’ta ve yönetilmeyen eklenti uygulamalarda veri ve iletileri kopyalayabilir ve paylaşabilir. 

Eklentilere kullanıcı izinlerini yönetmek için MAM veri koruma ilkelerinizin eklentilerde de geçerli olduğundan emin olmak adına Exchange yöneticinizle görüşün.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
Exchange ilkeleriniz zaten eklentileri dışarıdan yüklemeyi veya yüklemeyi önleyecek şekilde ayarlıysa burayı okumanıza gerek yoktur. MAM ilkeleriniz beklendiği gibi uygulanacaktır. Ancak Android’de Outlook dahilinde kesme, kopyalama ve yapıştırma işlemlerini kısıtlayacak şekilde MAM’da ilkeler ayarladıysanız ve Exchange’de eklenti ilkenizi ayarlamadıysanız varsayılan olarak kullanıcıların Outlook’a eklenti yükleyebileceğini bilmeniz gerekir. Bu eklentiler ileti gövdesine, konusuna ve diğer ileti özelliklerine erişebilir. Exchange Yöneticinize “Market Uygulamalarım” ve “Özel Uygulamalarım” rollerini kaldırtarak son kullanıcıların eklenti yüklemesini engelleyebilirsiniz. Daha fazla ayrıntı için aşağıda verilen ek bilgi bağlantısına bakın.

Bu ayar değişikliğinin Windows, iOS, web, Mac ve mobilde Outlook’ta geçerli olacağına dikkat edin. 

#### <a name="what-do-i-need-to-do"></a>Neler yapmam gerekir?
Hemen Exchange ilkelerinizi gözden geçirin. BT ve yardım masası çalışanlarınızı bilgilendirin. Sorularınız veya aklınıza takılanlar konusunda destek ekibimizle iletişime geçin. 

### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Intune Veri Ambarı veri modeline kullanıcı cihaz ilişkisi varlığı eklendi <!-- 1187917 -->
Kullanıcı ve cihaz varlık koleksiyonlarını ilişkilendiren kullanıcı cihaz ilişki bilgilerini kullanarak rapor ve veri görselleştirmeleri oluşturabileceksiniz. OData uç noktası veya özel bir istemci geliştirme yoluyla Veri Ambarı Intune sayfasından alınan Power BI dosyasından (PBIX) veri modeline erişebilirsiniz.


<!-- the following are present prior to 1709 -->

### <a name="actions-for-non-compliance----730266--"></a>Uyumsuzluk için eylemler <!--730266-->     
*Uyumsuzluk için eylemler*, uyumsuz cihazlar üzerinde eylem gerçekleştirmenize olanak tanıyan yeni uyumluluk ilkeleri özelliğidir. Tek veya birden çok eylem belirtebilir ve bu eylemlerin gerçekleştirilmesi gereken zaman aralığını belirtebilirsiniz. Örneğin, uyumsuz cihaz kullanıcılarını cihazlar uyumsuz hale geldiği anda e-posta yoluyla haberdar edebilir veya Koşullu Erişim aracılığıyla 3 günlük yetkisiz kullanım süresi ardından uyumsuz cihazların kurumsal kaynaklara erişimini engelleyebilirsiniz.

### <a name="new-report-that-lists-ios-devices-with-older-ios-versions------1352223---"></a>Eski iOS sürümleri ile iOS cihazlarını listeleyen yeni rapor   <!-- 1352223 -->
**Güncel olmayan iOS Cihazları** raporu, **Yazılım güncelleştirmeleri** çalışma alanında kullanılabilecektir. Raporda, bir iOS güncelleştirme ilkesi tarafından hedeflenen ve kullanılabilir güncelleştirmelere sahip denetimli iOS cihazların listesini görüntüleyebilirsiniz. Her cihaz için cihazın neden otomatik olarak güncelleştirilmediğiyle ilgili bir durum görüntüleyebilirsiniz. 

### <a name="new-settings-for-windows-10-device-restriction-profile"></a>Windows 10 cihaz kısıtlama profili için yeni ayarlar
<!--- 978575, 1308849, -->
Windows Defender SmartScreen kategorisinde Windows 10 cihaz kısıtlama profiline yeni ayarlar ekliyoruz.

Windows 10 cihaz kısıtlama profili hakkında ayrıntılar için bkz. [Windows 10 ve üzeri cihaz kısıtlama ayarları]( device-restrictions-windows-10.md).

### <a name="android-for-work-support-for-lookout----1087312---"></a>Lookout için Android for Work desteği <!-- 1087312 -->   
Lookout kullanan Intune bağlayıcısı, Lookout for Work uygulamasını kullanan Android for Work cihazlarını destekleyecektir. Lookout uygulamasını kapsayıcının içinde veya dışında dağıtabilirsiniz.

### <a name="intune-app-protection-and-citrix-mdx-development-tools----709185---"></a>Intune Uygulama Koruması ve Citrix MDX Geliştirme Araçları<!-- 709185 -->
Cihazları ve uygulamaları Citrix XenMobile MDX ve Microsoft Intune bileşimi ile yönetebilirsiniz. Bu, Citrix’in mVPN teknolojisini kullanırken uygulamaları Intune uygulama koruması ilkesiyle yönetmenize olanak sağlar.

iOS ve Android için Citrix MDX mVPN teknolojisiyle tümleştiren, Intune Uygulama Sarmalama Aracı ve Intune Uygulama SDK’sını içeren bir kod deposu bulabilirsiniz.

### <a name="zimperium---new-mobile-threat-defense-partner------954681---"></a>Zimperium - Yeni Mobile Threat Defense iş ortağı  <!-- 954681 -->
Microsoft Intune ile tümleştirilen Mobile Threat Defense çözümü Zimperium tarafından gerçekleştirilen risk değerlendirmesine dayalı koşullu erişimi kullanarak mobil cihazlardan şirket kaynaklarına erişimi denetleyebilirsiniz.

#### <a name="how-integration-with-intune-works"></a>Intune ile tümleştirme nasıl çalışır?
Risk, Zimperium çalıştıran cihazlardan toplanan telemetriye göre değerlendirilir. Intune cihaz uyumluluk ilkeleri aracılığıyla etkinleştirilen Zimperium risk değerlendirmesine dayalı EMS koşullu erişim ilkelerini yapılandırabilirsiniz. Algılanan tehditler temelinde, uyumlu olmayan cihazların şirket kaynaklarına erişmesine izin vermek veya erişimini engellemek için bu ilkeleri kullanabilirsiniz.

### <a name="new-azure-ad-conditional-access-policy-ui-link-from-intune-----1016201---"></a>Intune’dan yeni Azure AD koşullu erişim ilkesi kullanıcı arabirimi bağlantısı <!-- 1016201 -->
BT yöneticileri, Azure AD iş yükünde yeni koşullu erişim ilkesi kullanıcı arabirimi aracılığıyla uygulama tabanlı ilkeleri ayarlayabilir. Azure’da Intune Uygulama Koruması bölümünde bulunan uygulama tabanlı koşullu erişim ilkeleri şimdilik orada kalır ve yan yana yürütülmeye zorlanır. Ayrıca, Intune iş yükünden Azure AD’de yeni koşullu erişim ilkesi kullanıcı arabirimine kolay bir bağlantı eklenecektir.

### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Yüksek kullanılabilirlik desteği ile şirket içi Exchange bağlayıcısı <!-- 676614 -->   
Şirket içi Exchange bağlayıcısı için birden çok İstemci Erişimi Sunucusu (CAS) rolü kullanabilirsiniz. Örneğin ana CAS hata verirse Exchange bağlayıcısı diğer CAS’lere geçmek için bir sorgu alır. Bu özellik sayesinde hizmet asla kesilmez.

### <a name="system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Exchange bağlayıcısı için System Center Operations Manager yönetim paketi <!-- 885457 -->   
Exchange bağlayıcısı günlüklerini ayrıştırmanıza yardımcı olmak amacıyla Exchange bağlayıcısı için System Center Operations Manager yönetim paketi kullanıma sunulacak. Bu yönetim paketi, sorun gidermeniz gerektiğinde Intune'u izlemek için size farklı yollar sunar.

### <a name="end-of-support-for-ios-80----1164477---"></a>iOS 8.0 desteğinin son bulması <!---1164477--->
Yönetilen uygulamalar ve iOS için Şirket Portalı uygulaması, şirket kaynaklarına erişim için iOS 9.0 ve üzeri sürümleri gerektirecek. Eylül ayından önce güncelleştirmeyen cihazlar, Şirket Portalı veya diğer uygulamalara erişemeyecek.  

### <a name="end-of-support-for-android-43-and-lower----1171127-1326920----"></a>Android 4.3 ve altı sürümler için desteğin son bulması<!---1171127, 1326920 --->
Yönetilen uygulamalar ve Android için Şirket Portalı uygulaması, şirket kaynaklarına erişim için Android 4.4 ve üzeri sürümleri gerektirecek. Ekim ayının başından önce güncelleştirmeyen cihazlar, Şirket Portalı veya diğer uygulamalara erişemeyecek. Aralık ayında ise tüm kayıtlı cihazlar zorla devre dışı bırakılıp şirket kaynaklarına erişimleri kaldırılacak. MDM’siz uygulama koruma ilkeleri kullanıyorsanız uygulamalar güncelleştirme almayacak ve deneyimlerinin kalitesi zamanla düşecek.

### <a name="platform-support-reminder-windows-phone-81-mainstream-support-will-end-july-11-2017----1327781---"></a>Platform Desteği Anımsatıcı: Windows Phone 8.1 temel desteği, 11 Temmuz 2017 tarihinde sona erecek <!-- 1327781 -->  
11 Temmuz 2017 tarihinde Windows Phone 8.1 platformu temel desteği son bulacaktır. Windows 8.1 PC desteği bundan etkilenmeyecektir.

Bu durum, Intune hizmeti ile yönetilen Windows Phone 8.1 cihazlar üzerinde doğrudan bir etki göstermeyecektir. Kayıtlı cihazlar çalışmaya devam edecek ve tüm ilkeler, yapılandırmalar ve uygulamalar olması gerektiği gibi çalışmayı sürdürecektir. Ancak Windows Phone 8.1 platformu ve Windows Phone 8.1 Şirket Portalı uygulaması için Intune hizmeti dahilinde hiçbir iyileştirme planı olmadığını unutmayın.

İlk fırsatta uygun Windows Phone 8.1 cihazları Windows 10 Mobile sürümüne yükseltmenizi öneririz. 





## <a name="intune-apps"></a>Intune uygulamaları
### <a name="refresh-action-added-to-the-company-portal-app-for-windows-10---1132468--"></a>Windows 10 için Şirket Portalı uygulamasına yenileme eylemi eklendi <!--1132468-->
Windows 10 için Şirket Portalı uygulaması, mobil cihazlarda aşağı çekerek veya masaüstü cihazlarda F5’e basarak kullanıcılara uygulamadaki verileri yenileme imkanı sunacak.


### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment----1334712---"></a>Kayıt durumuna bakılmaksızın kullanılabilir olan uygulamalar artık kayıt istemi yapılmadan yüklenebilir. <!-- 1334712 -->
Android Şirket Portalı uygulamasındaki kayıt durumuna bakılmaksızın kullanılabilir olan şirket uygulamaları, kayıt için istem yapılmadan yüklenebilir.

### <a name="ios-company-portal-display-large-icons----1454593---"></a>iOS Şirket Portalı’nda büyük simgeler görüntüleme <!-- 1454593 -->
iOS Şirket Portalı’nın uygulama kutucuğunda simgeleri görüntülemesiyle ilgili bilinen bir sorunu çözüyoruz. 120x120 veya daha büyük boyutlu uygulama simgeleri yüklerseniz bunlar artık [Şirket portalı web sitesinde] (https://portal.manage.microsoft.com) ve iOS Şirket Portalı uygulama sayfalarında bütün uygulama kutucuğunu kaplayacak şekilde görüntülenecek.

### <a name="easier-to-understand-phrasing-for-the-company-portal-app-for-android------1396349---"></a>Android için Şirket Portalı uygulamasında daha kolay anlaşılır bir dil   <!---1396349--->    
Android için Şirket Portalı uygulamasında kayıt işlemi, son kullanıcıların kaydını kolaylaştırmak adına yeni metinlerle düzenlendi. 


<!-- the following are present prior to 1709 -->


### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a>iOS ve Android için Intune Managed Browser desteği <!---1374196--->
Ekim 2017 itibariyle Android uygulamasındaki Intune Managed Browser uygulaması yalnızca Android 4.4 ve sonraki sürümleri çalıştıran cihazları destekleyecektir. iOS’taki Intune Managed Browser uygulaması yalnızca iOS 9.0 ve sonraki sürümleri çalıştıran cihazları destekleyecektir. Android ve iOS’un daha eski sürümleri Managed Browser'ı kullanmaya devam edebilecek, ancak uygulamanın yeni sürümlerini yükleyemeyecek ve uygulamanın tüm özelliklerine erişemeyecektir. Bu cihazları desteklenen işletim sistemi sürümüne güncelleştirmenizi öneririz.

### <a name="allow-end-users-to-access-the-company-portal-app-for-android-without-enrollment----1169910---"></a>Son kullanıcıların kayıt yapmadan Android için Şirket Portalı uygulamasına erişmelerine izin verme <!---1169910--->  
Son kullanıcılar yakın zamanda cihazlarını kaydetmeden Android için Şirket Portalı uygulamasına erişebilecek. Uygulama Koruma İlkeleri kullanan kuruluşlardaki son kullanıcılar artık Şirket Portalı uygulamasını açtıklarında cihazlarını kaydetmelerine yönelik komut istemleri almayacaklar. Son kullanıcılar ayrıca cihaz kaydı yapmaksızın Şirket Portalı’dan uygulama yükleyebilecek. 

### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Kullanıcı, izin verilen en yüksek cihaz kaydı sayısına ulaştığında gösterilen hata iletisi iyileştirildi <!-- 1270370 -->
Genel bir hata iletisi yerine, son kullanıcılar kolay, işlem yapılabilir bir hata iletisi görür: “BT yöneticiniz tarafından izin verilen en yüksek cihaz kaydı sayısına ulaştınız. Lütfen kayıtlı bir cihazı kaldırın veya BT yöneticinizden yardım alın.”

### <a name="inform-end-users-what-device-information-can-be-seen-for-ios---739894--"></a>iOS için hangi cihaz bilgilerinin görülebileceği hakkında son kullanıcıları bilgilendirme <!--739894-->
iOS için Şirket Portalı’nda Cihaz Ayrıntıları ekranına **Sahiplik Türü** ekliyoruz. Bu, kullanıcıların doğrudan bu sayfadaki Intune son kullanıcı belgelerinden gizlilik hakkında daha fazla bilgi edinmesini sağlar. Kullanıcılar bu bilgileri Hakkında ekranında da bulabilir.

### <a name="apps-details-pages-display-new-information-for-android-devices---1287476--"></a>Uygulama ayrıntıları sayfaları, Android cihazlar için yeni bilgiler görüntüler <!--1287476-->
Android için Şirket Portalı uygulamasının uygulama ayrıntıları sayfası, BT yöneticisinin bu uygulama için tanımlamış olduğu uygulama kategorilerini görüntüler.

### <a name="intune-mobile-application-management-mam-dialog-boxes-now-have-a-modern-interface----1199015---"></a>Intune Mobil Uygulama Yönetimi (MAM) iletişim kutuları artık modern bir arabirime sahip <!-- 1199015 -->
Intune Mobil Uygulama Yönetimi (MAM) iletişim kutuları modern bir görünüm ve hisse sahip olacak şekilde güncelleştirildi. İletişim kutuları, önceki stil ile aynı şekilde çalışır.

Modern Android cihazlarda, Intune tarafından görüntülenen hata veya bildirim iletişim kutuları güncelleştirilmiş görünüm ve hisse sahiptir.



## <a name="notices"></a>Bildirimler
### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple, Uygulama Taşıma Güvenliği için güncelleştirmeler gerektirecek <!--748318-->   
Apple, 2017 baharından itibaren, Uygulama Taşıma Güvenliği (ATS) için belirli gereksinimler uygulayacağını açıkladı. ATS, HTTPS üzerinden yapılan tüm uygulama iletişimlerinde daha sıkı güvenlik uygulamak için kullanılır. Bu değişiklik, iOS Şirket Portalı uygulamaları kullanan Intune müşterilerini etkiler. Daha fazla ayrıntı için bkz. [Intune destek blogu](https://aka.ms/compportalats).

### <a name="plan-for-change-intune-is-changing-the-intune-partner-portal-experience----1050016---"></a>Değişiklik planı: Intune, Intune İş Ortağı Portalı deneyimini değiştiriyor <!-- 1050016 -->
2017 Mayıs ayı ortalarındaki hizmet güncelleştirmesinden başlayarak, manage.microsoft.com’dan Intune İş Ortağı sayfasını kaldırıyoruz.  

İş ortağı yöneticisiyseniz, artık Intune İş Ortağı sayfasında müşterileriniz adına görüntüleyemeyecek ve işlem yapamayacaksınız; bunun yerine Microsoft’taki diğer iki iş ortağı portalından birinde oturum açmanız gerekecektir.

Hem [Microsoft İş Ortağı Merkezi](https://partnercenter.microsoft.com/) hem de [Microsoft Office 365 İş Ortağı Yönetim Merkezi](https://portal.office.com/), yönettiğiniz müşteri hesaplarında oturum açmanıza olanak tanıyacaktır. İş ortağı olarak ilerlemek için, lütfen müşterilerinizi bu sitelerimizden birini kullanarak yönetin.



### <a name="see-also"></a>Ayrıca bkz.
Son geliştirmelere ilişkin ayrıntılar için bkz. [Microsoft Intune’daki Yenilikler](whats-new.md).
