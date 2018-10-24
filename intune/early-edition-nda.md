---
title: Erken sürüm
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/03/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 72585982cd27962981f581a99f0ea361642df0ee
ms.sourcegitcommit: ba0699cc351954960b222223c60c4ecd50edc829
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49652147"
---
# <a name="the-early-edition-for-microsoft-intune---october-2018"></a>Microsoft Intune için erken sürüm - Ekim 2018

> [!Note]
> NDA bildirimi: Aşağıdaki değişiklikler, Intune için geliştirilme aşamasındadır. Bu bilgiler NDA kapsamında çok kısıtlı bir kapsamla paylaşılır. Bu bilgilerin hiçbirini sosyal medyada veya Twitter, UserVoice, Reddit vb. gibi kamuya açık web sitelerinde paylaşmayın. 

**Erken sürüm**, NDA altında paylaşılan Microsoft Intune'un gelecek sürümlerinde kullanıma sunulacak yeni özelliklerin bir listesini sunar. Bu bilgiler kısıtlı bir kapsamla verilmektedir ve değiştirilebilir. Bu bilgileri Twitter veya UserVoice’da ya da şirketiniz dışında paylaşmayın. Burada listelenen özelliklerden bazılarının son tarihe yetişememe riski vardır ve gelecek sürüme ertelenebilir. Diğer özellikler, müşterinin kullanımına hazır olduğundan emin olmak için pilot (sürüyor) aşamasında test edilmektedir. Herhangi bir sorunuz veya endişeniz varsa lütfen Microsoft ürün grubu ilgili kişisiyle bağlantı kurun.

Bu sayfa düzenli aralıklarla güncelleştirilir. Ek güncelleştirmeleri daha sonra denetleyin.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Azure portalında Intune

<!-- 1810 start -->

### <a name="use-microsoft-recommended-settings-with-security-baselines----2055484---"></a>Microsoft tarafından önerilen Güvenlik Taban Çizgili ayarları kullanma <!-- 2055484 -->
Intune, Windows Defender ATP ve Office 365 ATP dahil güvenliğe odaklı diğer hizmetlerle tümleşir. Müşteriler, Microsoft 365 hizmetleri çapında ortak bir strateji ve birbiriyle bütünleşen bir dizi uçtan uca güvenlik iş akışı istiyor. Amacımız, stratejileri birbiriyle uyumlu hale getirmek ve güvenlik işlemleri ve sık kullanılan yönetici görevleri arasında bir köprü oluşturan çözümler geliştirmek. Intune olarak bu amaca Microsoft tarafından önerilen bir dizi "Güvenlik taban çizgisini" (**Intune** > **Güvenlik taban çizgileri**) yayımlayarak ulaşmayı hedefliyoruz.  Yöneticiler, doğrudan bu taban çizgilerinden güvenlik ilkeleri oluşturabilecek ve sonra bunları kullanıcılarına dağıtabilecekler. Ayrıca en iyi yöntem olan önerileri kuruluşlarının ihtiyaçlarını karşılayacak şekilde özelleştirebilirler. Intune, cihazların bu taban çizgilerle uyumlu kalmasını sağlar ve yöneticilere uyumlu olmayan kullanıcıları ve cihazları bildirir.

### <a name="autopilot-support-for-hybrid-azure-active-directory-joined-devices----1048100---"></a>Karma Azure Active Directory alanına katılmış cihazlar için Autopilot desteği <!-- 1048100 -->
Karma Azure Active Directory alanına katılmış cihazları Autopilot'ı kullanarak ayarlamanız mümkün olacaktır. Hibrit Autopilot özelliğini kullanmak için cihazların kuruluşunuzun ağına katılmış olması gerekir.

### <a name="scope-tags-for-apps---1081941---"></a>Uygulamalar için kapsam etiketleri <!--1081941 -->
Intune kaynaklarına erişimi sınırlamak için kapsam etiketleri oluşturabileceksiniz. Bir rol atamasına kapsam etiketi ekleyin ve daha sonra kapsam etiketini bir yapılandırma profiline ekleyin. Rolün yalnızca eşleşen kapsam etiketlerine sahip yapılandırma profillerine erişimi olacaktır.
Bir kapsam etiketi oluşturmak için **Intune rolleri** > **Kapsam (Etiketler)** > **Oluştur**’u seçin.
Kapsam etiketini bir rol atamasına eklemek için **Intune rolleri** > **Tüm roller** > **İlke ve Profil Yöneticisi** > **Atamalar** > **Kapsam (Etiketler)**’i seçin.
Kapsam etiketini bir yapılandırma profiline eklemek için **Cihaz yapılandırması** > **Profiller** > bir profil seçin > **Özellikler** > **Kapsam (Etiketler)**’i seçin.

### <a name="tenant-health-dashboard----1124854---"></a>Kiracı Sistem Durumu panosu <!-- 1124854 -->
Intune Kiracı Durumu sayfası tek bir yerde kiracı durumu bilgileri sağlayacaktır. Sayfa 4 bölüme ayrılmıştır:  
- **Kiracı Ayrıntıları**: MDM Yetkiliniz, kiracınızdaki toplam kayıtlı cihaz sayısı ve lisans sayınız gibi bilgileri içerir. Bu bölüm, kiracınız için geçerli hizmet sürümünü de sağlanır.
- **Bağlayıcı Durumu**: Apple VPP, İş için Windows Store ve Sertifika bağlayıcıları gibi yapılandırılmış bağlayıcıların bilgilerini içerir. Bunların geçerli durumu temel alındığında bağlayıcılar *Sağlıklı*, *Uyarı* veya *Sağlıksız* olarak işaretlenir.
- **Intune Hizmet Durumu**: Kiracınız için etkin olayları ve kesintileri içerir. Bu bölümdeki bilgiler doğrudan Office İleti Merkezi'nden ([https://portal.office.com](https://portal.office.com)) alınır.
- **Intune Haberleri**: Kiracınızın en yeni Intune özelliklerini aldığı bildirimleri gibi şeyler dahil, kiracınız için etkin iletileri içerir. Bu bölümdeki bilgiler doğrudan Office İleti Merkezi'nden ([https://portal.office.com](https://portal.office.com)) alınır.

### <a name="enrollment-abandonment-report----1382924---"></a>Kayıttan vazgeçme raporu <!-- 1382924 -->
Vazgeçilmiş kayıtların ayrıntılarını sağlayan yeni bir rapor **Cihaz kaydı** > **İzle** altında bulunabilir.

### <a name="deployed-wip-policies-without-user-enrollment----1434452---"></a>Kullanıcı kaydı olmadan dağıtılan WIP ilkeleri <!-- 1434452 -->
Windows Bilgi Koruması (WIP) ilkeleri, MDM kullanıcılarının Windows 10 cihazlarını kaydetmesini gerektirmeden dağıtılabilecektir. Bu yapılandırma, kullanıcıların Windows cihazlarının yönetimini sürdürmesini sağlarken şirketlerin de kurumsal belgelerini WIP yapılandırmasına göre korumasını sağlar. Belgeler bir kez bir WIP ilkesiyle korunduktan sonra korumalı veriler bir Intune yöneticisi tarafından seçmeli olarak silinebilir. Kullanıcı ve cihaz seçilerek ve bir silme isteği gönderilerek WIP İlkesi aracılığıyla korunan tüm veriler kullanılamaz hale getirilir. Azure portalındaki Intune'dan **Mobil uygulama** > **Uygulama seçmeli silme**'yi seçin.


### <a name="add-custom-brand-image-for-company-portal-app----1916266---"></a>Şirket Portalı uygulaması için özel marka resmi ekleme <!-- 1916266 -->
Microsoft Intune yöneticisi olarak Şirket Portalı uygulamasındaki kullanıcı profil sayfasında bir arka plan görüntüsü olarak kullanılacak özel bir marka resmini karşıya yükleyebilirsiniz. Şirket Portalı uygulamasını yapılandırma hakkında daha fazla bilgi için bkz. [Microsoft Intune Şirket Portalı uygulamasını yapılandırma](company-portal-app.md).

### <a name="group-windows-autopilot-enrolled-devices-by-correlator-id----2075110---"></a>Windows Autopilot kayıtlı cihazları ilişkilendirici kimliğine göre gruplama <!-- 2075110 -->
Intune, Configuration Manager aracılığıyla [mevcut cihazlar için Autopilot](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/New-Windows-Autopilot-capabilities-and-expanded-partner-support/ba-p/260430) kullanılarak kaydedilmiş Windows cihazlarını ilişkilendirici kimliğine göre gruplamayı destekleyecektir. İlişkilendirici kimliği, Autopilot yapılandırma dosyasının bir parametresidir. Intune, [Azure AD cihaz özniteliği enrollmentProfileName](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#using-attributes-to-create-rules-for-device-objects) değerini "OfflineAutopilotprofile-\<correlator ID\>" değerine eşit olarak şekilde otomatik olarak ayarlayacaktır. Bu, çevrimdışı Autopilot kayıtları için enrollmentprofileName özniteliği aracılığıyla ilişkilendirici kimliğine göre rasgele Azure AD dinamik grupları oluşturulmasına izin verir. 


### <a name="support-for-ios-12-oauth-in-ios-email-profiles---2155106---"></a>iOS e-posta profillerinde iOS 12 OAuth için destek <!--2155106 -->
Intune'un iOS e-posta profilleri iOS 12 OAuth'u destekleyecektir. Bu özelliği görmek için **Intune** > **Cihaz Yapılandırması** > **Profiller** > **Profil oluştur** > **OAuth**'u seçin. Bu ayar açılırsa iki şey olur:
1. Zaten hedeflenen cihazlara yeni bir profil verilir.
2. Son kullanıcılardan kimlik bilgileri yeniden istenir.

### <a name="new-required-password-type-default-setting-for-android-android-enterprise---2649963---"></a>Android, Android kurumsal için yeni "Gerekli parola türü" varsayılan ayarı<!-- 2649963 -->
Yeni bir uyumluluk ilkesi oluşturduğunuzda (**Intune** > **Cihaz uyumluluğu** > **İlkeler** > **İlke oluştur** > **Android** veya Platform > Sistem Güvenliği için **Android kurumsal**), **Gerekli parola türü** varsayılan değeri değişir: Geçerli varsayılan: Cihaz varsayılanı Yeni varsayılan: En azından sayısal Hedefi: Android, Android Kurumsal

### <a name="assign-autopilot-profiles-to-the-all-devices-virtual-group---2715522---"></a>Tüm cihazlar sanal grubuna Autopilot profilleri atama <!--2715522 -->
Tüm cihazlar sanal grubuna Autopilot profilleri atayabileceksiniz. Bunu yapmak için **Cihaz kaydı** > **Windows kaydı** > **Dağıtım Profilleri**'i seçin > bir profil seçin > **Atamalar**'ı seçin > **Atama hedefi** altından **Tüm cihazlar**'ı seçin.

### <a name="new-azure-active-directory-terms-of-use-feature----2870393---"></a>Yeni Azure Active Directory kullanım koşulları özelliği <!-- 2870393 -->
Azure Active Directory'de mevcut Intune hüküm ve koşulları yerine kullanabileceğiniz bir kullanım koşulları özelliği olacaktır. Azure AD kullanım koşulları özelliği, hangi koşulların ne zaman gösterileceği konusunda daha fazla esneklik, daha iyi yerelleştirme desteği, koşulların ekrana çizilmesi üzerinde daha fazla denetim ve daha iyi raporlama sağlamaktadır. Azure AD kullanım koşulları özelliği, Enterprise Mobility + Security E3 paketinin de parçası olan Azure Active Directory Premium P1'i gerektirir.


### <a name="intune-will-maintain-the-office-localized-language-when-updating-office-on-end-users-machines----2971030---"></a>Intune, son kullanıcı makinelerinde Office'i güncelleştirirken yerelleştirilmiş Office dilini korur <!-- 2971030 -->
Intune son kullanıcı makinenize Office yüklediğinde, son kullanıcılar önceki .MSI Office yüklemeleri ile aldıkları aynı dil paketini otomatik olarak alır. 

<!-- 1809 start -->  

### <a name="intune-app-data-transfer-settings-on-ios-mdm-enrolled-devices----2244713---"></a>iOS MDM kayıtlı cihazlarda Intune APP veri aktarımı ayarları <!-- 2244713 -->
iOS MDM kayıtlı cihazlarda Intune APP veri aktarımı ayarlarının denetimini, kayıtlı kullanıcının kimliğini belirtmekten ayrı tutabileceksiniz. IntuneMAMUPN kullanmayan yöneticiler, davranış değişikliği gözlemlemeyecektir. Bu işlev kullanılabilir olduğunda, kayıtlı cihazlarda veri aktarımı davranışını denetlemek için IntuneMAMUPN kullanan yöneticiler yeni ayarları gözden geçirmeli ve APP ayarlarını gerektiği gibi güncelleştirmelidir.

### <a name="use-a-pre-shared-key-in-a-windows-10-wi-fi-profile----2662938---"></a>Bir Windows 10 Wi-Fi profilinde önceden paylaşılan anahtar kullanma <!-- 2662938 -->
Windows 10’da bir Wi-Fi yapılandırma profilinin kimliğini doğrulamak için WPA/WPA2 Kişisel güvenlik protokolü ile birlikte bir önceden paylaşılan anahtar (PSK) kullanabileceksiniz.
Şu anda önceden paylaşılan anahtarları kullanmak için bir Wi-Fi profilini içeri aktarmanız veya özel bir profil oluşturmanız gerekiyor. [Windows 10 için Wi-Fi ayarları](wi-fi-settings-windows.md) makalesi, geçerli ayarları listeler. 

### <a name="app-protection-policy-app-settings-for-web-data----2662995---"></a>Web verileri için Uygulama Koruma İlkesi (APP) ayarları <!-- 2662995 -->
Gerek Android gerekse iOS cihazlarında Web içeriği için uygulama ilke ayarları, gerek http gerekse https Web bağlantılarını, ayrıca iOS Evrensel Bağlantıları ve Android Uygulama Bağlantıları aracılığıyla veri aktarımını daha iyi işleyecek şekilde güncelleştirilecektir.  

### <a name="autopilot-device-sync-frequency-increasing-to-every-12-hours----2753673---"></a>Autopilot cihaz eşitleme sıklığı 12 saatte bir olarak artıyor <!-- 2753673 -->
Autopilot cihazlar, 24 saatte bir yerine 12 saatte bir eşitlenecek.

### <a name="intune-landing-page-updates-and-node-rename---2867309---"></a>Intune giriş sayfası güncelleştirmeleri ve düğümü yeniden adlandırma <!--2867309 -->
Intune giriş sayfasında daha iyi görselleştirme için yeni ve değiştirilmiş izleme kutucukları ve grafikleri olacak. **Mobil uygulamalar** düğümü, **İstemci uygulamalar** olarak değişecek.

### <a name="increased-end-user-access-using-the-company-portal-app----772203---"></a>Şirket Portalı uygulaması kullanılarak daha fazla son kullanıcı erişimi <!-- 772203 -->
Son kullanıcılar, Şirket Portalı uygulaması üzerinden parola ve AAD profillerini sıfırlama gibi anahtar hesap eylemlerine erişebilecekler.  

<!-- 1808 start -->

### <a name="apple-vpp-token-used-by-another-mdm----1488946---"></a>Başka bir MDM tarafından kullanılan Apple VPP belirteci <!-- 1488946 -->
Bir Apple toplu satın alınan program (VPP) belirteci hem Intune hem de başka bir MDM tarafından kullanıldığında Intune bunu algılayacak ve ayrıntıları gösterecek.

### <a name="ios-version-number-and-build-number-are-shown----1892471---"></a>iOS sürüm numarası ve derleme numarası gösteriliyor <!-- 1892471 -->
**Cihaz uyumluluğu** > **Cihaz uyumluluğu**’nda iOS işletim sistemi sürümü gösterilir. Gelecek bir güncelleştirme ile derleme numarası da gösterilecek.
Güvenlik güncelleştirmeleri kullanıma sunulduğunda Apple genellikle sürüm numarasını olduğu gibi bırakır ancak derleme numarasını güncelleştirir. Derleme numarasına bakarak bir güvenlik açığı güncelleştirmesinin yüklenip yüklenmediğini kolayca denetleyebilirsiniz.

### <a name="retired-devices-in-the-device-compliance-dashboard----1981119---"></a>Cihaz uyumluluk panosunda kullanımdan kaldırılan cihazlar <!-- 1981119 -->
Gelecek bir güncelleştirme ile kullanımdan kaldırılan cihazlar uyumluluk panosundan da kaldırılacak. Bu durum, uyumluluk numaralarınızı değiştirecek.


### <a name="change-in-the-update-process-for-on-premises-connectors----2277554---"></a>Şirket içi bağlayıcılar için güncelleştirme işleminde değişiklik <!-- 2277554 -->
Müşterilerden gelen geri bildirimlere dayalı olarak şirket içi bağlayıcılarda güncelleştirme işlemi değiştirilecek. Bir şirket içi bağlayıcıyı ilk yüklediğinizde güncelleştirmeler otomatik olarak gerçekleşecek. Bu değişiklik, yeni Microsoft Intune için PFX Sertifika Bağlayıcısı ile başlayacak ve ardından diğer şirket içi bağlayıcı türlerine de sağlanacak. 

<!-- 1807 start -->

### <a name="improved-company-portal-app-experience-for-device-enrollment-manager-users----675800---"></a>Cihaz kayıt yöneticisi kullanıcıları için geliştirilmiş Şirket Portalı uygulama deneyimi <!-- 675800 -->
Bir cihaz kayıt yöneticisi (DEM) Windows için Şirket Portalı uygulamasında oturum açtığında, uygulama yalnızca yöneticinin geçerli, çalışan cihazını listeleyecek. Bu yenilik, uygulama DEM tarafından kaydedilen tüm cihazlara yüklenmeye çalıştığında yaşanan zaman aşımı sorunlarını azaltacak.  

### <a name="check-for-configuration-manager-compliance----2192052---"></a>Configuration Manager uyumluluğunu denetleme <!-- 2192052 -->
Gelecekte yapılacak bir güncelleştirmede yeni bir System Center Configuration Manager uyumluluk ayarı olacak (**Cihaz uyumluluğu** > **İlkeler** > **İlke oluştur** > **Windows 10**). Configuration Manager, Intune uyumluluğuna sinyal gönderir. Intune ayarını kullanarak tüm Configuration Manager sinyallerinin “uyumlu” olarak döndürülmesini gerektirebilirsiniz.

Örneğin, tüm yazılım güncelleştirmelerinin cihazlarda yüklü olmasını gerektirirsiniz. Configuration Manager’da bu gereksinim, “Yüklü” durumundadır. Cihazdaki herhangi bir program bilinmeyen bir durumdaysa cihaz, Intune ile uyumlu olmayacaktır.

Windows 10 ve üzeri için geçerlidir

### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low----2237572---"></a>Süresi dolan VPP belirteci veya yetersiz Şirket portalı lisansı uyarıları <!-- 2237572 -->
DEP kaydı sırasında Şirket Portalı’nın ön sağlamasını yapmak için Volume Purchase Program (VPP) kullanıyorsanız Intune, VPP belirtecinin süresi dolmak üzereyken ve Şirket Portalı lisansları yetersiz sayıdayken sizi uyarır.

<!-- 1806 start -->

### <a name="3rd-party-keyboards-can-be-blocked-by-app-settings-on-ios----1248481---"></a>iOS'ta üçüncü taraf klavyeler APP ayarlarıyla engellenebilir <!-- 1248481 -->
iOS cihazlarında, Intune yöneticileri ilke korumalı uygulamalarda kuruluş verilerine erişilirken üçüncü taraf klavyelerin kullanımını engelleyebilecek. Uygulama Koruma İlkesi (APP) üçüncü taraf klavyelerini engelleyecek şekilde ayarlandığında, cihaz kullanıcısı üçüncü taraf klavyesini kullanarak şirket verileriyle ilk kez etkileşim kurarken bir ileti alacak. Yerel klavye dışındaki tüm seçenekler engellenecek ve cihaz kullanıcıları bunları görmeyecek. Cihaz kullanıcıları iletişim kutusu iletisini tek bir kez görür. 

<!-- 1805 start -->

### <a name="require-non-biometric-after-specified-timeout----1506985---"></a>Belirtilen zaman aşımından sonra biyometrik olmayan PIN gerektirme <!-- 1506985 --> 

Intune, yöneticinin belirttiği zaman aşımından sonra biyometrik olmayan bir PIN gerektirerek şirket verilerine erişim için biyometrik tanımlama kullanımını kısıtlama yoluyla Mobil Uygulama Yönetimi’nin (MAM) etkinleştirildiği uygulamalarda gelişmiş güvenlik sağlayacak. Bu ayar, APP/MAM etkin uygulamalarına erişmek için Touch ID (iOS), Face ID (iOS), Android Biometric, veya geleceğin diğer kimlik doğrulama yöntemlerine güvenen kullanıcıları etkileyecek. Bu ayarlar birden çok parmak izi veya başka biyometrik erişim yöntemi olan bir cihazın şirket verilerini yanlış kullanıcıya gösterebildiği durumları ortadan kaldırarak, Intune yöneticilerinin kullanıcı erişimi üzerinde daha ayrıntılı bir denetim sahibi olmasına olanak tanıyacak. Azure portalında **Microsoft Intune**'u açın. **Mobil uygulamalar** > **Uygulama koruma ilkeleri** > **İlke ekle** > **Ayarlar**'ı seçin. Belirli ayarlar için **Erişim** bölümünü bulun.

<!-- 1803 start -->

### <a name="updating-the-help-and-feedback-experience-on-company-portal-app-for-android---1631531---"></a>Android için Şirket Portalı uygulamasında Yardım ve Geri Bildirim deneyimini güncelleştirme <!--1631531 -->

Android uygulamalarına yönelik en iyi yöntemlerle uyumlu olacak şekilde, Android için Şirket Portalı uygulamasında Yardım ve Geri Bildirim deneyimi güncelleştirilecek. Önümüzdeki birkaç ay içinde Android için Şirket Portalı uygulaması güncelleştirilerek **Yardım ve Geri Bildirim** menü öğesi **Yardım** ve **Geri Bildirim Gönder** menü öğelerine ayrılacak. Son kullanıcıları günlükleri Microsoft'a yüklemeye ve şirket desteğine sorunu açıklayan bir e-posta göndermeye yönlendirmek için, **Yardım** sayfasında **Sık Sorulan Sorular** bölümü ve **E-posta Desteği** düğmesi bulunacak. **Geri Bildirim Gönder** kullanıcıyı standart Microsoft geri bildirim gönderimine yönlendirecek ve kullanıcıdan "Bir şeyi beğendim" "Bir şeyi beğenmedim" veya "Bir fikrim var" arasında seçim yapması istenecek.



<!-- the following are present prior to 1711 -->

## <a name="notices"></a>Bildirimler

Şu anda etkin bildirim yok.

### <a name="see-also"></a>Ayrıca bkz:
Son geliştirmelere ilişkin ayrıntılar için bkz. [Microsoft Intune’daki Yenilikler](whats-new.md).



