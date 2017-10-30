---
title: "Erken sürüm"
description: 
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 10/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: a2e6fd2381286aa652a04b5ed34ab21c57ed85f6
ms.sourcegitcommit: bb2c181fd6de929cf1e5d3856e048d617eb72063
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2017
---
# <a name="the-early-edition-for-microsoft-intune---october-2017"></a>Microsoft Intune için erken sürüm - Ekim 2017

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

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Azure Active Directory web siteleri, Intune Managed Browser Uygulaması gerektirebilir ve Managed Browser’da (Genel Önizleme) Çoklu Oturum Açma’yı destekler <!-- 710595 -->   
Azure Active Directory (Azure AD) kullanarak, mobil cihazlarda web sitelerine erişimi Intune Managed Browser uygulaması ile kısıtlayabileceksiniz. Web sitesi verileri, Managed Browser’da güvende ve son kullanıcının kişisel verilerinden ayrı bir yerde olacaktır. Managed Browser ayrıca Azure AD ile korunan sitelerde Çoklu Oturum Açma işlevlerini de destekleyecektir. Managed Browser’da oturum açmak veya Intune tarafından yönetilen başka bir uygulamanın bulunduğu bir cihazda Managed Browser’ı kullanmak, kullanıcıların kimlik bilgilerini girmelerine gerek kalmaksızın Managed Browser’ın Azure AD ile korunan sitelere erişmesine olanak tanır. Bu özellik, Outlook Web Access (OWA) ve SharePoint Online’ın yanı sıra Azure Uygulama Proxy’si yoluyla erişilen intranet kaynakları gibi diğer kurumsal sitelerde de geçerlidir.

### <a name="troubleshoot-enrollment-issues------746324----"></a>Kayıt sorunlarını giderme  <!--- 746324 --->  
Sorun giderme çalışma alanı, kullanıcı kayıt sorunlarını gösterecektir. Sorunun ayrıntıları ve önerilen düzeltme adımları, yönetici ve yardım masası çalışanlarının sorunları çözmesine yardımcı olabilir. Bazı kayıt sorunları burada yer almaz ve bazı hatalar için düzeltme önerileri bulunmayabilir.

### <a name="admins-can-now-configure-the-firewall-settings-on-a-device-using-a-device-configuration-profile----951708---"></a>Yöneticiler artık bir cihazda cihaz yapılandırma profili kullanarak Güvenlik Duvarı ayarlarını yapılandırabilir <!-- 951708 -->   
Yöneticiler, cihazlar için güvenlik duvarını etkinleştirebilir ve etki alanı, özel ve ortak ağlar için çeşitli protokoller yapılandırabilir.  Bu güvenlik duvarı ayarlarını “Uç nokta koruma” profilinde bulabilirsiniz.

### <a name="windows-defender-application-guard-helps-protect-devices-from-untrusted-websites-as-defined-by-your-organization----958257---"></a>Windows Defender Application Guard, cihazları kuruluşunuz tarafından belirlenen güvenilmeyen web sitelerinden korumaya yardımcı olur <!-- 958257 -->   
Yöneticiler, bir Windows Bilgi Koruması iş akışını veya cihaz yapılandırmaları altındaki yeni “Ağ sınırı” profilini kullanarak siteleri “güvenilir” veya “kurumsal” olarak tanımlayabilir. Bir 64 bit Windows 10 cihazın güvenilir ağ sınırında listelenmemiş tüm siteler, Microsoft Edge ile görüntülenmeleri durumunda bir Hyper-V sanal bilgisayarındaki tarayıcıda açılır.

Application Guard’ı, “Uç nokta koruma” profilindeki cihaz yapılandırma profillerinde bulabilirsiniz. Yöneticiler buradan, sanallaştırılmış tarayıcı ile konak makine, güvenilmeyen siteler ile güvenilir siteler ve sanallaştırılmış tarayıcıda oluşturulan verileri depolama arasındaki etkileşimi yapılandırabilir. Bir cihazda Application Guard’ı kullanmak için önce bir ağ sınırı yapılandırılmalıdır. Bir cihaz için yalnızca bir ağ sınırı tanımlamak önemlidir.  

### <a name="windows-defender-application-guard-on-windows-10-enterprise-provides-mode-to-trust-only-authorized-apps----1031096---"></a>Windows 10 Enterprise’da Windows Defender Application Guard, yalnızca yetkilendirilmiş uygulamalara güvenme modu sağlar <!-- 1031096 -->    
Her gün oluşturulan binlerce yeni kötü amaçlı dosya karşısında virüsten koruma imza tabanlı algılama kullanmak artık yeni saldırılara karşı yeterli korumayı sağlayamıyor. Windows 10 Enterprise’da Windows Defender Application Guard’ı kullanarak cihaz yapılandırmasını, uygulamaların bir virüsten koruma veya başka bir güvenlik çözümü tarafından engellenmediği durumda güvenilir olduğu bir moddan, işletim sisteminin yalnızca kuruluşunuzun yetkilendirdiği güvenilir uygulamalara güvendiği bir moda değiştirebilirsiniz. Uygulamalara güveni Windows Defender Application Guard’da atarsınız.

Intune kullanarak uygulama denetleme ilkelerini “yalnızca denetim” modunda veya zorlama modunda yapılandırabilirsiniz. Uygulamalar, “yalnızca denetim” modunda çalıştırıldığında engellenmeyecektir. “Yalnızca denetim” modu, tüm olayları yerel istemci günlüklerine kaydeder. Ayrıca, yalnızca Windows bileşenleri ve Windows Mağazası uygulamalarının mı yoksa Intelligent Security Graph tarafından tanımlanan diğer itibarlı uygulamaların da mı çalışmaya izni olacağını yapılandırabilirsiniz.

### <a name="new-enrollment-status-page-for-windows-10-enrollments---1063201--"></a>Windows 10 kayıtları için yeni kayıt durumu sayfası <!--1063201-->    
Artık kullanıcılarınızın Windows 10 cihazlar kaydettiğinde görecekleri bir karşılama iletisi yapılandırabilirsiniz. **Kayıt Durumu Ekranı**’nı kullanarak, Windows 10 cihazlarını kaydettikleri zaman son kullanıcılarınıza görüntülenecek özel bir ileti ve köprü oluşturun.  **Kayıt Durumu Ekranı** ayrıca son kullanıcılara, cihazlarına uygulanmakta olan ilke ayarlarının ilerleme durumunu görme imkanı verir.  

### <a name="window-defender-exploit-guard-is-a-new-set-of-intrusion-prevention-capabilities-for-windows-10----1063615---"></a>Windows Defender Exploit Guard, Windows 10 için yeni bir yetkisiz erişim önleme işlevleri dizisi <!-- 1063615 -->   
Windows Defender Exploit Guard; uygulamaların kötüye kullanımını azaltacak özel kurallar içerir, makro ve betik tehditlerini önler, düşük itibarlı IP adreslerine yapılan ağ bağlantılarını otomatik olarak önler ve fidye yazılımı ile bilinmeyen tehditlere karşı verileri korur. Windows Defender Exploit Guard aşağıdaki bileşenlerden oluşur:

- **Saldırı Yüzeyi Azaltma (ASR)** makro, betik ve e-posta tehditlerini önlemenize yardımcı kurallar sağlar.
- **Denetimli Klasör erişimi** korumalı klasörlerin içeriklerine erişimi otomatik olarak engeller.
- **Ağ Filtresi** herhangi bir uygulamanın düşük itibarlı bir IP/etki alanına bağlantı yapmasını engeller
- **Exploit Protection** bir uygulamanın kötüye kullanılmasını önlemek üzere kullanılabilecek bellek, denetim akışı ve ilke kısıtlamaları sağlar.

### <a name="app-conditional-launch-support----1193313---"></a>Uygulama koşullu başlatma desteği <!-- 1193313 -->
Artık BT yöneticileri, uygulama başlatıldığında mobil uygulama yönetiminde (MAM) sayısal PIN yerine bir geçiş kodu kullanılmasını zorlamak için Azure yönetici portalında bir gereksinim ayarlayabilir. Bu gereksinim ayarlanırsa kullanıcının, MAM etkin uygulamalara erişim almadan önce bir geçiş kodu ayarlaması ve istendiğinde bunu kullanması gerekir. Geçiş kodu, en az bir özel karakter veya büyük/küçük harf içeren sayısal PIN’dir. Intune’un bu sürümünde bu özellik, **yalnızca iOS’ta** geçerli olacaktır. Intune, sayısal PIN’e benzer bir geçiş kodunu destekler, uzunluk alt sınırı belirler ve karakter ile dizi tekrarlarına izin verir. Bu özellik, geçiş kodu ayarlarının hedeflenen uygulamalarda zorlanabilmesi için uygulamaların katılımının (WXP, Outlook, Managed Browser, Yammer) Intune Uygulama SDK’sıyla bu özellik için gereken kodu birleştirmesini gerektirir.

### <a name="app-version-number-for-line-of-business-in-device-install-status-report----1233999---"></a>Cihaz yükleme durum raporunda iş kolu için uygulama sürüm numarası <!-- 1233999 -->  
Cihaz yükleme durum raporu, iOS ve Android için iş kolu uygulamalarında uygulama sürüm numarasını görüntüleyecek. Bu bilgiyi kullanarak uygulamalarınızda sorun giderebilir veya eski uygulama sürümleri çalıştıran cihazları bulabilirsiniz.

### <a name="co-management-for-windows-10-devices-----124445---"></a>Windows 10 cihazlar için ortak yönetim <!-- 124445 -->
Ortak yönetim, geleneksel yönetimden modern yönetime bir köprü sağlar ve aşamalı bir yaklaşım ile bu geçişi yapmanızı sağlayan bir yol sunar. Ortak yönetim temelde Windows 10 cihazların, Configuration Manager ve Microsoft Intune tarafından eş zamanlı olarak yönetildiği ve Active Directory (AD) ile Azure Active Directory’ye (Azure AD) katıldığı bir çözümdür.  Bu yapılandırma size, her şeyi aynı anda taşıyamadığınız durumlarda kuruluşunuza uygun bir tempoda zaman içinde modernleştireceğiniz bir yol sunar.  

### <a name="set-access-for-apps-by-minimum-android-security-patch-on-the-device---1278463---"></a>Uygulamalara erişimi cihazdaki en düşük Android güvenlik düzeltme ekine göre ayarlama<!-- 1278463 -->   
Yönetici, yönetilen bir hesap altındaki yönetilen bir uygulamaya erişim kazanmak için cihazda yüklü olması gereken en düşük Android güvenlik düzeltme ekini belirleyebilecek.

> [!Note]  
> Bu özellik, yalnızca Android 6.0+ cihazlarda Google tarafından yayınlanan düzeltme eklerini kısıtlar.

### <a name="new-device-restriction-settings-for-windows-10---------1308850---"></a>Windows 10 için yeni cihaz kısıtlama ayarları      <!-- 1308850 -->
-    Mesajlaşma (yalnızca mobil) - sınamayı ve MMS iletilerini devre dışı bırakır
-    Parola - FIPS’yi ve kimlik doğrulaması için ikincil Windows Hello cihazların kullanımını etkinleştirme ayarları 
-    Görüntü - eski uygulamalar için GDI Ölçeklendirmeyi açma ve kapama ayarları


### <a name="windows-10-kiosk-mode-device-restrictions----1308872---"></a>Windows 10 bilgi noktası modu cihaz kısıtlamaları <!-- 1308872 -->   
Windows 10 cihaz kullanıcılarını bilgi noktası moduna kısıtlayabileceksiniz, böylece kullanıcılar önceden tanımlı bir uygulamalar dizisiyle sınırlanacaktır.  Bunun için bir Windows 10 cihaz kısıtlama profili oluşturun ve Bilgi Noktası ayarlarını ayarlayın.

Bilgi noktası modu şu iki modu destekler: **tek uygulama** (kullanıcının yalnızca bir uygulama çalıştırmasına izin verir) veya **çok uygulama** (bir dizi uygulamaya erişme izni verir).  Kullanıcı hesabı ve cihaz adını siz belirlersiniz, böylece desteklenen uygulamalar belirlenir.  Kullanıcı oturum açtığında belirlenen uygulamalarla sınırlı olur.  Daha fazla bilgi için bkz. [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp). 

Bilgi noktası modu şunları gerektirir:

- MDM yetkilisi Intune olmalıdır.
- Uygulamalar hedef cihazda yüklü olmalıdır.
- Cihaz [doğru bir şekilde sağlanmalıdır](https://docs.microsoft.com/windows/configuration/set-up-a-kiosk-for-windows-10-for-desktop-editions).

### <a name="new-device-configuration-profile-for-creating-network-boundaries----1311967---"></a>Ağ sınırları oluşturmak için yeni cihaz yapılandırma profili <!-- 1311967 -->   
**Ağ sınırı** adı verilen yeni bir cihaz yapılandırma profili oluşturduk. Bu profil, diğer cihaz yapılandırma profillerinizin yanında bulunur. Bu profili kullanarak kurumsal ve güvenilir olarak değerlendirilmesini istediğiniz çevrimiçi kaynakları tanımlayabilirsiniz. Windows Defender Application Guard ve Windows Bilgi Koruması gibi özelliklerin cihazda kullanılabilmesi için *önce* bir ağ sınırı tanımlamanız gerekir. Her cihaz için yalnızca bir ağ sınırı tanımlamanız önemlidir.

Güvenilir olarak değerlendirilmesini istediğiniz kuruluş bulut kaynakları, IP adresi aralıkları ve dahili proxy sunucularını tanımlayabilirsiniz. Tanımlandıktan sonra bu ağ sınırı, Windows Defender Application Guard ve Windows Bilgi Koruması gibi diğer özellikler tarafından kullanılır.

###  <a name="two-additional-settings-for-windows-defender-antivirus----1338409---"></a>Windows Defender Virüsten Koruma için iki ek ayar <!-- 1338409 -->  
**Dosya engelleme düzeyi**

| | |
|---|---|
| Yapılandırılmadı | **Yapılandırılmadı**, varsayılan Windows Defender Virüsten Koruma engelleme düzeyini kullanır ve güvenli klasörleri algılama riskini artırmadan güçlü bir algılama sağlar. |
| Yüksek | **Yüksek** güçlü bir algılama düzeyi sağlar.
| Yüksek +  | **Yüksek +** Yüksek düzeyine istemci performansını etkileyebilecek ek koruma önlemleri getirir.
| Sıfır tolerans  | **Sıfır tolerans** tüm bilinmeyen yürütülebilir dosyaları engeller. |

**Yüksek** düzeyini ayarlamak, düşük ihtimalle de olsa bazı güvenli dosyaların algılanmasına yol açabilir.
Dosya engelleme düzeyini varsayılan **Yapılandırmadı** düzeyine ayarlamanızı öneririz.

**Bulut tarafından dosya tarama için zaman aşımı uzantısı**  

| | |
|--|--|
| Saniye sayısı (0-50) | Windows Defender Virüsten Koruma’nın buluttan sonuç beklerken bir klasörü engellemesi için geçmesi gereken en uzun süreyi belirtin. Varsayılan süre 10 saniyedir: burada belirtilen ek süre (en fazla 50 saniyeye kadar) bu 10 saniyenin üzerine eklenir. Çoğu zaman tarama, belirtilen en uzun süreden daha kısa zamanda biter. Bu süreyi artırmak, bulutun şüpheli klasörleri ayrıntılı olarak araştırmasına olanak verir. Bu ayarı etkinleştirip fazladan en az 20 saniye belirtmenizi öneririz. |


### <a name="support-for-symantec-cloud-certification-authority-ca-----1333638---"></a>Symantec Cloud Sertifika Yetkilisi (CA) desteği <!-- 1333638 -->    
Intune artık Symantec Cloud CA’yı desteklemektedir. Böylece Intune Sertifika Bağlayıcısı, Symantec Cloud’dan Intune ile yönetilen cihazlara PKCS sertifikaları verebilir. Intune Sertifika Bağlayıcısı’nı Microsoft Sertifika Yetkilisi (CA) ile kullanıyorsanız, Symantec CA desteğini eklemesi için mevcut Intune Sertifika Bağlayıcısı kurulumundan yararlanabilirsiniz.



### <a name="citrix-vpn-added-for-windows-10-devices----1512457---"></a>Windows 10 cihazlar için Citrix VPN eklendi <!-- 1512457 -->  
Müşteriler, Windows 10 cihazları için Citrix VPN’i yapılandırabilecekler. Windows 10 ve üzeri sürümler için bir VPN yapılandırırken, **Temel VPN** dikey penceresinde bulunan *Bağlantı türü seçin* listesinden Citrix VPN’i seçebilirsiniz.

> [!Note]
> Citrix yapılandırması iOS ve Android için zaten mevcuttu.





<!-- the following are present prior to 1710 -->

### <a name="google-play-protect-support-on-android----908720----"></a>Android’de Google Play Protect desteği <!-- 908720  -->  
Android Oreo sürümüyle Google, kuruluşların güvenli uygulamalar çalıştırmasına ve Android görüntülerinin güvenliğini sağlamasına imkan veren Google Play Protect adlı bir güvenlik özellikleri paketi piyasaya sunuyor. Intune, SafetyNet uzak kanıtlama dahil olmak üzere Google Play Protect özelliklerini destekleyecektir.  Yöneticiler, Google Play Protect’ın yapılandırılması ve iyi durumda olmasını gerektiren uyumluluk ilke gereksinimleri ayarlayabilir. **SafetyNet cihaz kanıtlama** ayarı, cihazın iyi durumda olduğu ve güvenliğinin aşılmadığını doğrulamak için cihazın bir Google hizmetiyle bağlanmasını gerektirir. Yöneticiler ayrıca, yüklenen uygulamaların Google Play hizmetleri tarafından doğrulanmasını gerektiren bir Android for Work yapılandırma profili ayarı da ayarlayabilir.  Koşullu erişim, bir cihaz Google Play Protect gereksinimleriyle uyumlu olmadığında kullanıcıların şirket kaynaklarına erişimini engelleyebilir. 


### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a>Windows 10 sürüm yükseltme ilkesi desteği <!-- 903672(archived), 1119689 -->  
Windows 10 cihazları; Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education ve Windows 10 Professional Education N’e yükselten bir Windows 10 sürüm yükseltme ilkesi oluşturabileceksiniz. Windows 10 sürüm yükseltmeleri hakkında daha fazla bilgi için bkz. [Windows 10 sürüm yükseltmelerini yapılandırma](edition-upgrade-configure-windows-10.md).


### <a name="intune-mam-and-outlook-for-android-add-ins-----1450688---"></a>Android eklentileri için Intune MAM ve Outlook  <!-- 1450688 -->
Birkaç hafta içerisinde Office ekibi, Android için Outlook eklentilerini duyuracak. Bu eklenti özellikleri kümesi Windows, iOS, web ve Mac için Outlook uygulamalarında zaten mevcuttur. Eklentiler Exchange yoluyla yönetildiğinden, eklentilere erişim Exchange yöneticiniz tarafından kapatılmadığı sürece, kullanıcılar Outlook’ta ve yönetilmeyen eklenti uygulamalarda veri ve iletileri kopyalayabilir ve paylaşabilir. 

Eklentilere kullanıcı izinlerini yönetmek için MAM veri koruma ilkelerinizin eklentilerde de geçerli olduğundan emin olmak adına Exchange yöneticinizle görüşün.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
Exchange ilkeleriniz zaten eklentileri dışarıdan yüklemeyi veya yüklemeyi önleyecek şekilde ayarlıysa burayı okumanıza gerek yoktur. MAM ilkeleriniz beklendiği gibi uygulanacaktır. Ancak Android’de Outlook dahilinde kesme, kopyalama ve yapıştırma işlemlerini kısıtlayacak şekilde MAM’da ilkeler ayarladıysanız ve Exchange’de eklenti ilkenizi ayarlamadıysanız varsayılan olarak kullanıcıların Outlook’a eklenti yükleyebileceğini bilmeniz gerekir. Bu eklentiler ileti gövdesine, konusuna ve diğer ileti özelliklerine erişebilir. Exchange Yöneticinize “Market Uygulamalarım” ve “Özel Uygulamalarım” rollerini kaldırarak kullanıcıların eklenti yüklemesini engelleyebilirsiniz.

Exchange’deki ayar değişikliği Outlook’un Windows, iOS, web, Mac ve mobil sürümlerinde geçerli olacaktır. 

#### <a name="what-do-i-need-to-do"></a>Neler yapmam gerekir?
Hemen Exchange ilkelerinizi gözden geçirin. BT ve yardım masası çalışanlarınızı bilgilendirin. Sorularınız veya aklınıza takılanlar konusunda destek ekibimizle iletişime geçin. 




<!-- the following are present prior to 1709 -->

### <a name="actions-for-non-compliance----730266--846515---"></a>Uyumsuzluk için eylemler <!--730266  846515 -->     
*Uyumsuzluk için eylemler*, uyumsuz cihazlar üzerinde eylem gerçekleştirmenize olanak tanıyan yeni bir uyumluluk ilkeleri özelliğidir. Tek veya birden çok eylem belirtebilir ve bu eylemlerin gerçekleştirilmesi gereken zaman aralığını belirtebilirsiniz. Örneğin, uyumsuz cihaz kullanıcılarını cihazlar uyumsuz hale geldiği anda e-posta yoluyla haberdar edebilir veya Koşullu Erişim aracılığıyla 3 günlük yetkisiz kullanım süresi ardından uyumsuz cihazların kurumsal kaynaklara erişimini engelleyebilirsiniz.

### <a name="android-for-work-support-for-lookout----1087312---"></a>Lookout için Android for Work desteği <!-- 1087312 -->   
Lookout kullanan Intune bağlayıcısı, Lookout for Work uygulamasını kullanan Android for Work cihazlarını destekleyecektir. Lookout uygulamasını kapsayıcının içinde veya dışında dağıtabilirsiniz.

### <a name="intune-app-protection-and-citrix-mdx-development-tools----709185---"></a>Intune Uygulama Koruması ve Citrix MDX Geliştirme Araçları<!-- 709185 -->
Cihazları ve uygulamaları Citrix XenMobile MDX ve Microsoft Intune bileşimi ile yönetebilirsiniz. Bu, Citrix’in mVPN teknolojisini kullanırken uygulamaları Intune uygulama koruması ilkesiyle yönetmenize olanak sağlar.

iOS ve Android için Citrix MDX mVPN teknolojisiyle tümleştiren, Intune Uygulama Sarmalama Aracı ve Intune Uygulama SDK’sını içeren bir kod deposu bulabilirsiniz.

#### <a name="how-integration-with-intune-works"></a>Intune ile tümleştirme nasıl çalışır?
Risk, Zimperium çalıştıran cihazlardan toplanan telemetriye göre değerlendirilir. Intune cihaz uyumluluk ilkeleri aracılığıyla etkinleştirilen Zimperium risk değerlendirmesine dayalı EMS koşullu erişim ilkelerini yapılandırabilirsiniz. Algılanan tehditler temelinde, uyumlu olmayan cihazların şirket kaynaklarına erişmesine izin vermek veya erişimini engellemek için bu ilkeleri kullanabilirsiniz.

### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Yüksek kullanılabilirlik desteği ile şirket içi Exchange bağlayıcısı <!-- 676614 -->   
Şirket içi Exchange bağlayıcısı için birden çok İstemci Erişimi Sunucusu (CAS) rolü kullanabilirsiniz. Örneğin ana CAS hata verirse Exchange bağlayıcısı diğer CAS’lere geçmek için bir sorgu alır. Bu özellik sayesinde hizmet asla kesilmez.

### <a name="system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Exchange bağlayıcısı için System Center Operations Manager yönetim paketi <!-- 885457 -->   
Exchange bağlayıcısı günlüklerini ayrıştırmanıza yardımcı olmak amacıyla Exchange bağlayıcısı için System Center Operations Manager yönetim paketi kullanıma sunulacak. Bu yönetim paketi, sorun gidermeniz gerektiğinde Intune'u izlemek için size farklı yollar sunar.


## <a name="intune-apps"></a>Intune uygulamaları


### <a name="redirecting-macos-users-to-our-new-company-portal-app---1380728--"></a>macOS kullanıcılarını yeni Şirket Portalı uygulamamıza yönlendirme <!--1380728-->   
Bir son kullanıcı, macOS cihazını kaydetmek için Şirket Portalı web sitesinde oturum açtığında, işlemi tamamlamak için yeni macOS Şirket Portalı uygulamasını indirmek üzere yönlendirilecektir. Bu durum, OS X El Capitan 10.11 ve üzeri sürümleri kullanan macOS cihazlarda görülür. 

### <a name="certificate-based-authentication-support-on-the-company-portal-for-ios---1029830--"></a>iOS için Şirket Portalı’nda sertifika tabanlı kimlik doğrulaması desteği <!--1029830-->
iOS için Şirket Portalı’na sertifika tabanlı kimlik doğrulaması (CBA) desteği ekledik. CBA kullanan kullanıcılar kullanıcı adını girer ve “Bir sertifika ile oturum aç” bağlantısına dokunur. CBA, Android ve Windows için Şirket Portalı’nda zaten destekleniyordu. [Şirket Portalı uygulamasında oturum açma](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal) sayfasından daha fazla bilgi edinebilirsiniz.

<!-- the following are present prior to 1710 -->



### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment----1334712---"></a>Kayıt durumuna bakılmaksızın kullanılabilir olan uygulamalar artık kayıt istemi yapılmadan yüklenebilir. <!-- 1334712 -->
Android Şirket Portalı uygulamasındaki kayıt durumuna bakılmaksızın kullanılabilir olan şirket uygulamaları, kayıt için istem yapılmadan yüklenebilir.


<!-- the following are present prior to 1709 -->

### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a>iOS ve Android için Intune Managed Browser desteği <!-- 1374196 -->
Ekim 2017 itibariyle Android uygulamasındaki Intune Managed Browser uygulaması yalnızca Android 4.4 ve sonraki sürümleri çalıştıran cihazları destekleyecektir. iOS’taki Intune Managed Browser uygulaması yalnızca iOS 9.0 ve sonraki sürümleri çalıştıran cihazları destekleyecektir. Android ve iOS’un daha eski sürümleri Managed Browser'ı kullanmaya devam edebilecek, ancak uygulamanın yeni sürümlerini yükleyemeyecek ve uygulamanın tüm özelliklerine erişemeyecektir. Bu cihazları desteklenen işletim sistemi sürümüne güncelleştirmenizi öneririz.


### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Kullanıcı, izin verilen en yüksek cihaz kaydı sayısına ulaştığında gösterilen hata iletisi iyileştirildi <!-- 1270370 -->
Genel bir hata iletisi yerine, son kullanıcılar kolay, işlem yapılabilir bir hata iletisi görür: “BT yöneticiniz tarafından izin verilen en yüksek cihaz kaydı sayısına ulaştınız. Lütfen kayıtlı bir cihazı kaldırın veya BT yöneticinizden yardım alın.”




## <a name="notices"></a>Bildirimler

### <a name="device-and-app-management-integration----677972---"></a>Cihaz ve uygulama yönetim tümleştirmesi <!-- 677972 -->   
Artık Intune’un mobil cihaz yönetimi (MDM) ve mobil uygulama yönetimi (MAM) işlevleri Azure portalından erişilebilir olduğu için Intune, uygulama ve cihaz yönetiminde BT yönetici deneyimini tümleştirmeye başladı. Bu değişikliklerin amacı, cihaz ve uygulama yönetimi deneyiminizi kolaylaştırmaktır.

[Intune destek ekibi blogundan](https://blogs.technet.microsoft.com/intunesupport/2017/09/19/support-tip-setting-up-communication-between-mam-managed-and-mdm-managed-apps/) MDM ve MAM değişiklikleri hakkında daha fazla bilgi edinebilirsiniz.




### <a name="see-also"></a>Ayrıca bkz.
Son geliştirmelere ilişkin ayrıntılar için bkz. [Microsoft Intune’daki Yenilikler](whats-new.md).
