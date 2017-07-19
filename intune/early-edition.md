---
title: "Erken sürüm"
description: 
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 07/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5eab3fb933b2999e23115091cf0ded3f140e114c
ms.sourcegitcommit: f5c6e8b218431dc9a8d85464d7f58adebd048866
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2017
---
# <a name="the-early-edition-for-microsoft-intune---july-2017"></a>Microsoft Intune için erken sürüm - Temmuz 2017

**Erken sürüm**, Microsoft Intune'un gelecek sürümlerinde kullanıma sunulacak yeni özelliklerin bir listesini sunar. Bu bilgiler çok kısıtlı bir kapsamla verilmektedir ve değiştirilebilir. Bu bilgileri şirket dışından kimselerle paylaşmayın. Burada listelenen özelliklerden bazılarının son tarihe yetişememe riski vardır ve gelecek sürüme ertelenebilir. Diğer özellikler, müşterinin kullanımına hazır olduğundan emin olmak için pilot (sürüyor) aşamasında test edilmektedir. Herhangi bir sorunuz veya endişeniz varsa lütfen Microsoft ürün grubu ilgili kişisiyle bağlantı kurun.

Bu sayfa düzenli aralıklarla güncelleştirilir. Ek güncelleştirmeleri daha sonra denetleyin.

> [!Note]
>Intune için aşağıdaki değişiklikler geliştirilme aşamasındadır. Yeni karma özellikler hakkında daha fazla bilgi için, [Karma Yenilikler sayfamızı](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) gözden geçirin.

<!--

## What's coming to Intune on the Azure portal  
## What's coming to Intune apps
## Notices

-->



## <a name="whats-coming-to-intune-on-the-azure-portal"></a>Azure portalında Intune'da yakında çıkacak özellikler

### <a name="easier-installation-of-office-365-apps-----1121362----"></a>Office 365 uygulamalarında yükleme kolaylığı <!--- 1121362 --->
Yeni bir tür **Office 365 ProPlus** uygulaması, yönettiğiniz ve Windows 10’un son sürümünü çalıştıran cihazlara Office 365 ProPlus uygulamalarını atamanızı kolaylaştıracak. Bunun yanı sıra, Microsoft Project ve Microsoft Visio lisanslarınız varsa bu uygulamaları da yükleyebilirsiniz. İstediğiniz uygulamalar birlikte paketlenir ve Intune konsolundaki uygulama listesinde tek uygulama olarak gösterilir.
 

### <a name="new-device-action-to-force-devices-to-sync-with-intune----711369---"></a>Cihazları Intune ile eşitlemeye zorlayan yeni bir cihaz eylemi <!-- 711369 -->    
Seçili cihazı hemen Intune ile eşitlemeye zorlayan yeni bir cihaz eylemi ekliyoruz. Bir cihaz eşitlendiğinde, kendisine atanan beklemedeki eylem veya ilkeleri hemen alır.  Bu eylem, atadığınız ilkeleri bir sonraki zamanlanmış iadeyi beklemenize gerek kalmadan hızla doğrulamanız ve ilkelerin sorunlarını gidermenize yardımcı olur.

### <a name="actions-for-non-compliance----730266--"></a>Uyumsuzluk için eylemler <!--730266-->     
*Uyumsuzluk için eylemler*, uyumsuz cihazlar üzerinde eylem gerçekleştirmenize olanak tanıyan yeni bir uyumluluk ilkeleri özelliğidir. Tek veya birden çok eylem belirtebilir ve bu eylemlerin gerçekleştirilmesi gereken zaman aralığını belirtebilirsiniz. Örneğin, uyumsuz cihaz kullanıcılarını cihazlar uyumsuz hale geldiği anda e-posta yoluyla haberdar edebilir veya Koşullu Erişim aracılığıyla 3 günlük yetkisiz kullanım süresi ardından uyumsuz cihazların kurumsal kaynaklara erişimini engelleyebilirsiniz.

### <a name="new-app-configuration-settings-for-the-intune-managed-browser-----682951----"></a>Intune'la Managed Browser için yeni uygulama ayarları <!--- 682951 --->
Intune'la Managed Browser uygulaması için başka yapılandırmalar da ekliyor olacağız. Tarayıcının varsayılan giriş sayfasını ve yer işaretlerini yapılandırma için bir uygulama yapılandırma ilkesi kullanabileceksiniz.

### <a name="restrict-android-and-ios-device-enrollment-restriction-by-os-version------1333256--1245463----"></a>Android ve iOS cihaz kaydı kısıtlamasını işletim sistemi sürümüyle kısıtlama <!--- 1333256,  1245463 --->  
Intune artık iOS ve Android kaydını işletim sistemi sürüm numarasına göre kısıtlamayı desteklemektedir. BT yöneticisi artık **Intune** > **Kayıt kısıtlamaları** > **Cihaz Türü Kısıtlaması** > **Varsayılan** > **Platform kısıtlamaları** altında, cihaz kaydını en düşük ve en yüksek işletim sistemi değerleri arasında kısıtlaması için bir platform yapılandırması ayarlayabilir. İşletim sistemi sürümleri Major.Minor.Build.Rev olarak belirtilmelidir. Burada Build ve Rev isteğe bağlıdır. iOS sürümleri ise Major.Minor.Build olarak belirtilmelidir, Build isteğe bağlıdır.

>[!NOTE]
>Bu ayar ile Apple Aygıt Kayıt Programı ve Apple School Manager, veya Apple Configurator’ı barındıran Apple kayıt programlarını kısıtlamış olmazsınız.

### <a name="restrict-android-ios-and-macos-device-personally-owned-device-enrollment------1333272--1333275-1245709----"></a>Android, iOS ve macOS cihazların kişisel cihaz kaydını kısıtlama  <!--- 1333272,  1333275, 1245709 --->
Intune artık cihaz seri numaralarını kullanarak Android, iOS ve macOS için kişisel cihaz kaydını kısıtlamayı desteklemektedir. Bazı cihazlar seri numaralarını bildirmez. Ayrıntılar için cihaz üreticisine danışın. Intune’a seri numaralarını yükleyerek cihazların şirkete ait olduğunu önceden bildirmiş olursunuz. Kayıt kısıtlamalarını kullanarak kişişel (KCG) cihazları engelleyebilir ve yalnızca şirkete ait cihazların kaydına izin verebilirsiniz.

Intune portalında seri numaralarını içeri aktarmak için **Cihaz kaydı** > **Kurumsal cihaz tanımlayıcıları**’na gidin, **Ekle**’ye tıklayın ve bir .CSV dosyası yükleyin (üst bilgi, seri numarası için iki sütunlu ve IMEI numarası gibi ayrıntılarla).  Kişisel cihazları kısıtlamak için **Cihaz kaydı** > **Kayıt kısıtlamaları**’na gidin. **Cihaz Türü Kısıtlamaları** altında **Varsayılan**’ı ve daha sonra **Platform Yapılandırmaları**’nı seçin. iOS, Android ve macOS kişisel cihazlar için **İzin Ver** veya **Engelle** seçeneklerinden birini belirtebilirsiniz. 

### <a name="force-supervised-ios-devices-to-automatically-install-the-latest-available-software-update----777100---"></a>Denetimli iOS cihazları, son yazılım güncelleştirmesini yüklemeye zorlama <!-- 777100 -->   
Denetimli iOS cihazları, son yazılım güncelleştirmesini otomatik olarak yüklemeye zorlayabileceğiniz Yazılım güncelleştirmeleri çalışma alanında yeni bir ilke kullanılabilir olacaktır. Ayrıca eski sürümleri kullanan iOS cihazların bir listesini içeren ve neden eski sürüm kullandıklarını özetleyen yeni bir rapor görüntüleyebileceksiniz.

### <a name="new-settings-to-allow-and-block-apps-on-samsung-knox-standard-devices-----822899--1305423--"></a>Samsung KNOX Standard cihazlarda uygulamalara izin vermek veya bunları engellemek için yeni ayarlar  <!-- 822899,  1305423-->   
Aşağıdaki uygulama listelerini belirtmenizi sağlayan yeni [cihaz kısıtlama ayarları](device-restrictions-android.md) ekliyoruz:
  - Kullanıcıların yüklemesine izin verilen uygulamalar
  - Kullanıcıların çalıştırması engellenen uygulamalar
  - Cihazda kullanıcıdan gizlenen uygulamalar  

Uygulamayı URL, paket adı ile veya yönettiğiniz uygulamalar listesinden belirtebilirsiniz.

### <a name="android-for-work-support-for-lookout----1087312---"></a>Lookout için Android for Work desteği <!-- 1087312 -->   
Lookout kullanan Intune bağlayıcısı, Lookout for Work uygulamasını kullanan Android for Work cihazlarını destekleyecektir. Lookout uygulamasını kapsayıcının içinde veya dışında dağıtabileceksiniz.


### <a name="check-point-sandblast-mobile---new-mobile-threat-defense-partner-----954651--and--1172027----"></a>Check Point SandBlast Mobile - Yeni Mobile Threat Defense iş ortağı  <!-- 954651  and  1172027 ? -->  
Microsoft Intune ile tümleşik çalışan mobil tehdit savunması çözümü Check Point SandBlast Mobile tarafından gerçekleştirilen risk değerlendirmesine dayalı koşullu erişimi kullanarak mobil cihazlardan şirket kaynaklarına erişimi denetleyebileceksiniz.

#### <a name="how-integration-with-intune-works"></a>Intune ile tümleştirme nasıl çalışır?
Risk, Check Point SandBlast Mobile çalıştıran cihazlardan toplanan telemetriye göre değerlendirilir. Intune cihaz uyumluluk ilkeleri aracılığıyla etkinleştirilen Check Point SandBlast Mobile risk değerlendirmesine dayalı olarak EMS koşullu erişim ilkeleri yapılandırabilirsiniz. Algılanan tehditlere dayalı olarak uyumlu olmayan cihazların şirket kaynaklarına erişmesine izin verebilir ya da erişimi engelleyebilirsiniz.

### <a name="zimperium---new-mobile-threat-defense-partner------954681---"></a>Zimperium - Yeni Mobile Threat Defense iş ortağı  <!-- 954681 -->
Microsoft Intune ile tümleşik çalışan Mobile Threat Defense çözümü Zimperium tarafından gerçekleştirilen risk değerlendirmesine dayalı koşullu erişimi kullanarak mobil cihazlardan şirket kaynaklarına erişimi denetleyebileceksiniz.

#### <a name="how-integration-with-intune-works"></a>Intune ile tümleştirme nasıl çalışır?
Risk, Zimperium çalıştıran cihazlardan toplanan telemetriye göre değerlendirilir. Intune cihaz uyumluluk ilkeleri aracılığıyla etkinleştirilen Zimperium risk değerlendirmesine dayalı EMS koşullu erişim ilkelerini yapılandırabilirsiniz. Algılanan tehditler temelinde, uyumlu olmayan cihazların şirket kaynaklarına erişmesine izin vermek veya erişimini engellemek için bu ilkeleri kullanabilirsiniz.

### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Yüksek kullanılabilirlik desteği ile şirket içi Exchange bağlayıcısı <!-- 676614 -->   
Şirket içi Exchange bağlayıcısı için birden çok İstemci Erişimi Sunucusu (CAS) rolü kullanabileceksiniz. Örneğin ana CAS hata verirse Exchange bağlayıcısı diğer CAS’lere geçmek için bir sorgu alır. Bu özellik sayesinde hizmet asla kesilmez.

### <a name="system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Exchange bağlayıcısı için System Center Operations Manager yönetim paketi <!-- 885457 -->   
Exchange bağlayıcısı günlüklerini ayrıştırmanıza yardımcı olmak amacıyla Exchange bağlayıcısı için System Center Operations Manager yönetim paketi kullanıma sunulacak. Bu özellik, sorun gidermeniz gerektiğinde Intune'u izlemek için size değişik yollar sunacak.

### <a name="conditional-access-support-for-mac-devices-----720172---"></a>Mac cihazlar için koşullu erişim desteği  <!-- 720172 -->   
Yakın zamanda, Mac cihazların Intune’a kaydedilmesi ve Intune cihaz uyumluluk ilkeleriyle uyumlu olmasını gerektiren bir koşullu erişim ilkesi ayarlamanız mümkün olabilecek. Örneğin kullanıcılar, macOS için Intune Şirket Portalı uygulamasını indirebilir ve Mac cihazlarını Intune’a kaydedebilir. Intune ise PIN, şifreleme, işletim sistemi sürümü ve Sistem Bütünlüğü gibi gereksinimleri kullanarak Mac cihazın uyumlu olup olmadığını değerlendirir.

### <a name="end-of-support-for-ios-80----1164477---"></a>iOS 8.0 desteğinin son bulması <!---1164477--->
Yönetilen uygulamalar ve iOS için Şirket Portalı uygulaması, şirket kaynaklarına erişim için iOS 9.0 ve üzeri sürümleri gerektirecek. Eylül ayından önce güncelleştirmeyen cihazlar, Şirket Portalı veya diğer uygulamalara erişemeyecek. Aralık ayına gelindiğinde ise e-posta dahil olmak üzere tüm şirket kaynaklarına erişim kaldırılacak. 

### <a name="end-of-support-for-android-43-and-lower----1171127---"></a>Android 4.3 ve altı sürümler için desteğin son bulması<!---1171127--->
Yönetilen uygulamalar ve Android için Şirket Portalı uygulaması, şirket kaynaklarına erişim için Android 4.4 ve üzeri sürümleri gerektirecek. Ekim ayının başından önce güncelleştirmeyen cihazlar, Şirket Portalı veya diğer uygulamalara erişemeyecek. Aralık ayında ise tüm kayıtlı cihazlar zorla devre dışı bırakılıp şirket kaynaklarına erişimleri kaldırılacak. MDM’siz uygulama koruma ilkeleri kullanıyorsanız uygulamalar güncelleştirme almayacak ve deneyimlerinin kalitesi zamanla düşecek.





### <a name="platform-support-reminder-windows-phone-81-mainstream-support-will-end-july-11-2017----1327781---"></a>Platform Desteği Anımsatıcı: Windows Phone 8.1 temel desteği, 11 Temmuz 2017 tarihinde sona erecek <!-- 1327781 -->  
11 Temmuz 2017 tarihinde Windows Phone 8.1 platformu temel desteği son bulacaktır. Windows 8.1 PC desteği bundan etkilenmeyecektir.

Bu durum, Intune hizmeti ile yönetilen Windows Phone 8.1 cihazlar üzerinde doğrudan bir etki göstermeyecektir. Kayıtlı cihazlar çalışmaya devam edecek ve tüm ilkeler, yapılandırmalar ve uygulamalar olması gerektiği gibi çalışmayı sürdürecektir. Ancak Windows Phone 8.1 platformu ve Windows Phone 8.1 Şirket Portalı uygulaması için Intune hizmeti dahilinde hiçbir iyileştirme planı olmadığını unutmayın.

İlk fırsatta uygun Windows Phone 8.1 cihazları Windows 10 Mobile sürümüne yükseltmenizi öneririz. 




## <a name="whats-coming-to-intune-apps"></a>Intune uygulamalarında yakında çıkacak özellikler

### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a>Tüm platformlar için Şirket Portalı uygulamalarında gelişmiş oturum açma deneyimi <!--User Story 1132123-->    
Android, iOS ve Windows için Intune Şirket Portalı uygulamalarında oturum açma deneyimini geliştirecek bir değişikliği önümüzdeki birkaç ay içinde piyasaya süreceğiz. Yeni kullanıcı deneyimi, Azure AD bu değişikliği gerçekleştirdiğinde Şirket Portalına yönelik tüm platformlarda görünecektir. Ayrıca, kullanıcılar artık tek kullanımlık bir kod ile başka bir cihazdan Şirket Portalında oturum açabilir. Bu, özellikle kullanıcıların kimlik bilgileri olmadan oturum açması gerektiğinde faydalıdır.

[Uygulamanın kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md) sayfasında, önceki oturum açma deneyiminin, kimlik bilgileriyle yeni oturum açma deneyiminin ve başka bir cihazdan yeni oturum açma deneyiminin ekran görüntülerini bulabilirsiniz.

### <a name="light-and-dark-modes-available-for-the-company-portal-app-for-windows-10----676547---"></a>Windows 10 için Şirket Portalı uygulamasında açık ve koyu modlar kullanılabilir <!---676547--->
Windows 10 için Şirket Portalı uygulamasında son kullanıcılar, renk modunu özelleştirebilecek. Kullanıcılar bu değişikliği Şirket Portalı uygulamasının Ayarlar kısmından yapabilir. Değişiklik, kullanıcı uygulamayı yeniden başlattığında görünecektir. Windows 10 sürüm 1607 ve üzeri için uygulama modu, varsayılan olarak sistem ayarında olacaktır. Windows 10 sürüm 1511 ve öncesini kullanan masaüstü cihazlarda uygulama modu, varsayılan olarak açık modda olacaktır.

### <a name="enable-end-users-to-tag-their-device-group-in-the-company-portal-app-for-windows-10----807046--"></a>Windows 10 için Şirket Portalı uygulamasında son kullanıcıların cihaz gruplarını etiketlemelerine izin verme <!---807046-->    
Son kullanıcılar, doğrudan Windows 10 için Şirket Portalı uygulamasında cihazlarının hangi gruba ait olduğunu etiketleyerek cihaz gruplarını belirleyebilecekler.

### <a name="allow-end-users-to-access-the-company-portal-app-for-android-without-enrollment----1169910---"></a>Son kullanıcıların kayıt yapmadan Android için Şirket Portalı uygulamasına erişmelerine izin verme <!---1169910--->  
Son kullanıcılar yakın zamanda cihazlarını kaydetmeden Android için Şirket Portalı uygulamasına erişebilecek. Uygulama Koruma İlkeleri kullanan kuruluşlardaki son kullanıcılar artık Şirket Portalı uygulamasını açtıklarında cihazlarını kaydetmelerine yönelik komut istemleri almayacaklar. Son kullanıcılar ayrıca cihaz kaydı yapmaksızın Şirket Portalı’dan uygulama yükleyebilecek. 

### <a name="users-who-are-signed-in-to-exchange-can-automatically-access-the-company-portal-website-on-windows-10-devices---1323204--"></a>Exchange’de oturum açan kullanıcıların Windows 10 cihazlarda Şirket Portalı web sitesine otomatik olarak erişmesi <!--1323204-->  
Exchange’de kimliği doğrulanmış Windows 10 kullanıcıları, alacakları koşullu erişim karantina e-postasındaki bağlantıya tıklayarak Şirket Erişimi Kurulumu’na başlamadan önce tarayıcıda otomatik olarak oturum açabilecekler.


## <a name="notices"></a>Bildirimler

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple, Uygulama Taşıma Güvenliği için güncelleştirmeler gerektirecek <!--748318-->   
Apple, 2017 baharından itibaren, Uygulama Taşıma Güvenliği (ATS) için belirli gereksinimler uygulayacağını açıkladı. ATS, HTTPS üzerinden yapılan tüm uygulama iletişimlerinde daha sıkı güvenlik uygulamak için kullanılır. Bu değişiklik, iOS Şirket Portalı uygulamaları kullanan Intune müşterilerini etkiler. Daha fazla ayrıntı için bkz. [Intune destek blogu](https://aka.ms/compportalats).

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Apple kayıt senaryolarına doğrudan erişim <!--951869-->   
Intune, Azure Önizleme Portalı'ndaki Cihaz Kaydetme iş yükünü kullanarak Apple kayıt senaryolarına doğrudan erişimi Ocak 2017 sonrasında oluşturulan Intune hesapları için etkinleştirdi. Daha önce, Apple kayıt önizleme sürümüne yalnızca klasik Intune portalı bağlantıları ile erişilebiliyordu. Bu özelliklerin Azure’da kullanılabilmesi için, Ocak 2017 öncesi oluşturulan Intune hesaplarında tek seferlik bir geçiş yapılması gerekir. Geçiş için zaman çizelgesi henüz açıklanmamıştır, ancak konuya ilişkin ayrıntılar olabildiğince çabuk duyurulacaktır. Mevcut hesabınız önizleme sürümüne erişemiyorsa, yeni deneyimi test etmek için bir deneme hesabı oluşturmanızı kesinlikle öneririz.

### <a name="plan-for-change-intune-is-changing-the-intune-partner-portal-experience----1050016---"></a>Değişiklik planı: Intune, Intune İş Ortağı Portalı deneyimini değiştiriyor <!-- 1050016 -->
2017 Mayıs ayı ortalarındaki hizmet güncelleştirmesinden başlayarak, manage.microsoft.com’dan Intune İş Ortağı sayfasını kaldırıyoruz.  

İş ortağı yöneticisiyseniz, artık Intune İş Ortağı sayfasında müşterileriniz adına görüntüleyemeyecek ve işlem yapamayacaksınız; bunun yerine Microsoft’taki diğer iki iş ortağı portalından birinde oturum açmanız gerekecektir.

Hem [Microsoft İş Ortağı Merkezi](https://partnercenter.microsoft.com/) hem de [Microsoft Office 365 İş Ortağı Yönetim Merkezi](https://portal.office.com/), yönettiğiniz müşteri hesaplarında oturum açmanıza olanak tanıyacaktır. İş ortağı olarak ilerlemek için, lütfen müşterilerinizi bu sitelerimizden birini kullanarak yönetin.



### <a name="see-also"></a>Ayrıca bkz.
Son geliştirmelere ilişkin ayrıntılar için bkz. [Microsoft Intune’daki Yenilikler](whats-new.md).
