---
title: Erken sürüm
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/25/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ad49b983bd5dc72a3355cba5645192456a555e38
ms.sourcegitcommit: e8e8164586508f94704a09c2e27950fe6ff184c3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2018
ms.locfileid: "39321263"
---
# <a name="the-early-edition-for-microsoft-intune---july-2018"></a>Microsoft Intune için erken sürüm - Temmuz 2018

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

<!-- 1807 start -->

### <a name="more-sync-opportunities-in-the-company-portal-app-for-windows----2683177---"></a>Windows için Şirket Portalı uygulamasında daha fazla eşitleme fırsatı <!-- 2683177 -->
Windows için Şirket Portalı uygulaması, Windows görev çubuğuna ve Başlat menüsü atlama listesine bir cihaz eşitleme eylemi ekliyor. İki konumdan birine tıklayarak cihazlarınızı hızla eşitleyin ve şirket kaynaklarına erişim sağlayın.  

### <a name="reset-device-passcodes-from-company-portal-app-for-windows-10----2101282---"></a>Windows 10 için Şirket Portalı uygulamasından cihaz geçiş kodlarını sıfırlama <!-- 2101282 --> 
Çalışanlarınız yakın zamanda cihazlarının PIN’i veya geçiş kodunu doğrudan Windows 10 için Şirket Portalı uygulamasından sıfırlayabilecek. Bu işlevsellik, geçiş kodu sıfırlamalarını destekleyen hem uzak hem de yerel Intune tarafından yönetilen cihazlarda kullanılabilecek. Cihaz türüne bağlı olarak, bir uzak cihaza yapılan istek ya cihazın geçerli geçiş kodunu kaldırır ya da geçici bir geçiş kodu oluşturur. Yerel bir cihaz için sıfırlama isteğinde bulunan kullanıcılar, cihazın Ayarlar uygulamasına yeniden yönlendirilir.  

### <a name="new-browsing-experiences-in-the-company-portal-app-for-windows----2317227---"></a>Windows için Şirket Portalı uygulamasında yeni gözatma deneyimleri <!-- 2317227 -->  
Windows için Şirket Portalı uygulamasında uygulamalara gözatarken veya uygulama ararken mevcut **Kutucuklar** görünümü ile yeni eklenen **Ayrıntılar** görünümü arasında geçiş yapabileceksiniz. Yeni görünüm; ad, yayımcı, yayım tarihi ve yükleme durumu gibi uygulama ayrıntılarını listeler.  

**Uygulamalar** sayfası, tamamlanmış ve devam eden uygulama yüklemeleri hakkında ayrıntıları görmenize olanak verecek bir **Yüklemeler** görünümü sunacak. Yeni değişiklikler hakkında geri bildirim veya görüş paylaşmak ister misiniz? Geri bildiriminizi bize Şirket Portalı uygulaması üzerinden gönderin.

### <a name="improved-company-portal-app-experience-for-device-enrollment-manager-users----675800---"></a>Cihaz kayıt yöneticisi kullanıcıları için geliştirilmiş Şirket Portalı uygulama deneyimi <!-- 675800 -->
Bir cihaz kayıt yöneticisi (DEM) Windows için Şirket Portalı uygulamasında oturum açtığında, uygulama yalnızca yöneticinin geçerli, çalışan cihazını listeleyecek. Bu yenilik, uygulama DEM tarafından kaydedilen tüm cihazlara yüklenmeye çalıştığında yaşanan zaman aşımı sorunlarını azaltacak.  

### <a name="use-vpp-device-licenses-to-pre-provision-the-company-portal-during-dep-enrollment----1608345---"></a>DEP kaydı sırasında Şirket Portalı’nın ön sağlamasını yapmak için VPP cihaz lisanslarını kullanın <!-- 1608345 -->
Aygıt Kayıt Programı (DEP) kayıtları sırasında Şirket Portalı’nın ön sağlamasını yapmak için Volume Purchase Program (VPP) cihaz lisanslarını kullanabileceksiniz. Bunu yapmak için bir kayıt profili oluşturduğunuzda veya düzenlediğinizde, Şirket Portalı’nı yüklemek için kullanmak istediğiniz VPP belirtecini belirtin. Belirtecinizin süresinin dolmadığından ve Şirket Portalı uygulaması için yeterli lisansınız olduğundan emin olun. Belirtecin süresi dolduğu veya yeterli lisans olmadığı durumlarda, Intune bunun yerine Uygulama Mağazası Şirket Portalı’na istek gönderir (bu, Apple kimliği ister).


### <a name="bulk-delete-devices-on-devices-blade----1793693---"></a>Cihazlar dikey penceresinde cihazları toplu silme <!-- 1793693 -->
Cihazlar dikey penceresinde tek seferde birden fazla cihazı silmek mümkün olacaktır. **Cihazlar** > **Tüm cihazlar** > silmek istediğiniz cihazları seçin > **Sil**'i seçin. Silinemeyen cihazlar için bir uyarı görüntülenir.

### <a name="new-wi-fi-device-configuration-profile-for-windows-10-and-later----1879077---"></a>Windows 10 ve üzeri için yeni Wi-Fi cihaz yapılandırma profili <!-- 1879077 -->
Şu anda XML dosyalarını kullanarak Wi-Fi profillerini içeri ve dışarı aktarabilirsiniz. Tıpkı bazı diğer platformlarda olduğu gibi Intune’da doğrudan Wi-Fi cihaz yapılandırma profili oluşturabileceksiniz.

Profili oluşturmak için **Cihaz Yapılandırması** > **Profiller** > **Profil Oluştur** > **Windows 10 ve üzeri** > **Wi-Fi** seçeneklerini açın. 

Windows 10 ve üzeri için geçerlidir.

###  <a name="windows-line-of-business-lob-apps-file-extensions----1884873---"></a>Windows iş kolu (LOB) uygulamaları dosya uzantıları <!-- 1884873 -->
Windows LOB uygulamaları için dosya uzantıları artık *.msi*, *.appx*, *.appxbundle*, *.msix* ve *.msixbundle*’ı içerecek. Microsoft Intune’da, **Mobil uygulamalar** > **Uygulamalar** > **Ekle**’yi seçerek bir uygulama ekleyebilirsiniz. **Bölme ekle** bölmesi görüntülenir ve **Uygulama türünü** seçmenize olanak tanır. Windows LOB uygulamaları için uygulama türü olarak **İş kolu uygulamasını** seçin, **Uygulama paketi dosyasını** seçin ve uygun uzantıya sahip bir yükleme dosyası girin.

### <a name="windows-defender-atp-configuration-package-automatically-added-to-configuration-profile----2144658---"></a>Windows Defender ATP yapılandırma paketi, otomatik olarak yapılandırma profiline eklenir <!-- 2144658 -->
Şu anda Intune’da [Gelişmiş Tehdit Koruması ve ekleme](advanced-threat-protection.md#onboard-devices-using-a-configuration-profile) cihazları kullanırken bir yapılandırma paketini indirip bunu yapılandırma profilinize ekliyorsunuz. Gelecekteki bir güncelleştirmede Intune, paketi otomatik olarak Windows Defender Güvenlik Merkezi'nden alır ve profilinize ekler.

Windows 10 ve üzeri için geçerlidir.


### <a name="check-for-sccm-compliance----2192052---"></a>SCCM uyumluluğunu denetleme <!-- 2192052 -->
Gelecekte yapılacak bir güncelleştirmede yeni bir System Center Configuration Manager (SCCM) uyumluluk ayarı olacaktır (**Cihaz uyumluluğu** > **İlkeler** > **İlke oluşturma**  > **Windows 10**). SCCM, Intune uyumluluğuna sinyal gönderir. Intune ayarını kullanarak, tüm SCCM sinyallerinin “uyumlu” döndürmesini gerektirebilirsiniz.

Örneğin, tüm yazılım güncelleştirmelerinin cihazlarda yüklü olmasını gerektirirsiniz. SCCM’de bu gereksinim, "Yüklü" durumuna sahiptir. Cihazdaki herhangi bir program bilinmeyen bir durumdaysa cihaz, Intune ile uyumlu olmayacaktır.

Windows 10 ve üzeri için geçerlidir

### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low----2237572---"></a>Süresi dolan VPP belirteci veya yetersiz Şirket portalı lisansı uyarıları <!-- 2237572 -->
DEP kaydı sırasında Şirket Portalı’nın ön sağlamasını yapmak için Volume Purchase Program (VPP) kullanıyorsanız Intune, VPP belirtecinin süresi dolmak üzereyken ve Şirket Portalı lisansları yetersiz sayıdayken sizi uyarır.

### <a name="confirmation-required-to-delete-vpp-token-that-is-being-used-for-company-portal-pre-provisioning----2237634---"></a>Şirket Portalı ön sağlaması için kullanılan bir VPP belirtecini silmek için onay gerekir <!-- 2237634 -->
DEP kaydı sırasında Şirket Portalı’nın ön sağlaması için kullanılıyorsa bir Volume Purchase Program (VPP) belirtecini silmek için onay gerekir.


#### <a name="additional-security-settings-for-windows-installer----2282430---"></a>Windows Installer için ek güvenlik ayarları <!-- 2282430 -->
Kullanıcıların uygulama yüklemelerini denetlemesine olanak sağlayabileceksiniz. Etkinleştirilirse, aksi takdirde güvenlik ihlali nedeniyle durdurulabilecek olan yüklemelerin devam etmesine izin verilebilir. Windows Installer'ı sistemde herhangi bir program yüklerken yükseltilmiş izinler kullanmaya yönlendirebileceksiniz. Buna ek olarak, Windows Bilgi Koruması (WIP) öğelerinin dizine alınmasını ve bunlar hakkındaki meta verilerin şifrelenmemiş bir konumda depolanmasını etkinleştirebileceksiniz. İlke devre dışı bırakıldığında, WIP korumalı öğelerin dizini oluşturulmayacak ve Cortana veya dosya gezgini sonuçlarında görünmeyecek. Bu seçeneklerin işlevselliği varsayılan olarak devre dışı bırakılacak. 


<!-- 1806 start -->


### <a name="3rd-party-keyboards-can-be-blocked-by-app-settings-on-ios----1248481---"></a>iOS'ta üçüncü taraf klavyeler APP ayarlarıyla engellenebilir <!-- 1248481 -->
iOS cihazlarında, Intune yöneticileri ilke korumalı uygulamalarda kuruluş verilerine erişilirken üçüncü taraf klavyelerin kullanımını engelleyebilecek. Uygulama Koruma İlkesi (APP) üçüncü taraf klavyelerini engelleyecek şekilde ayarlandığında, cihaz kullanıcısı üçüncü taraf klavyesini kullanarak şirket verileriyle ilk kez etkileşim kurarken bir ileti alacak. Yerel klavye dışındaki tüm seçenekler engellenecek ve cihaz kullanıcıları bunları görmeyecek. Cihaz kullanıcıları iletişim kutusu iletisini tek bir kez görür. 

### <a name="require-non-biometric-passcode-on-app-launch-and-timeout----1506985---"></a>Uygulama başlatma işleminde ve zaman aşımı durumunda biyometrik olmayan bir geçiş kodu gerektirin <!-- 1506985 -->

Uygulama başlatma işleminde ve yöneticinin belirttiği zaman aşımı durumunda biyometrik olmayan bir geçiş kodu gerektirerek, Intune şirket verilerine erişim için biyometrik tanımlama kullanımını kısıtlama yoluyla Mobil Uygulama Yönetimi'nin (MAM) etkinleştirildiği uygulamalarda gelişmiş güvenlik sağlayacak. Bu ayar, APP/MAM etkin uygulamalarına erişmek için Touch ID (iOS), Face ID (iOS), Android Biometric, veya geleceğin diğer kimlik doğrulama yöntemlerine güvenen kullanıcıları etkileyecek. Bu ayarlar birden çok parmak izi veya başka biyometrik erişim yöntemi olan bir cihazın şirket verilerini yanlış kullanıcıya gösterebildiği durumları ortadan kaldırarak, Intune yöneticilerinin kullanıcı erişimi üzerinde daha ayrıntılı bir denetim sahibi olmasına olanak tanıyacak. Azure portalında **Microsoft Intune**'u açın. **Mobil uygulamalar** > **Uygulama koruma ilkeleri** > **İlke ekle** > **Ayarlar**'ı seçin. Belirli ayarlar için **Erişim** bölümünü bulun.

### <a name="office-365-pro-plus-language-packs----1833450---"></a>Office 365 Pro Plus dil paketleri <!-- 1833450 -->
Intune yöneticisi olarak, Intune aracılığıyla yönetilen Office 365 Pro Plus uygulamaları için ek dillerin dağıtımını yapabileceksiniz. Kullanılabilir diller listesi, dil paketinin **Tür** bilgisini içerir (çekirdek, kısmı ve yazım denetleme). Azure portalında **Microsoft Intune** > **Mobil uygulamalar** > **Uygulamalar** > **Ekle**'yi seçin. **Uygulama ekle** dikey penceresindeki **Uygulama türü** listesinde **Office 365 Paketi** altından **Windows 10**'u seçin. **Uygulama Paketi Ayarları** dikey penceresinde **Diller**'i seçin.

### <a name="preview-a-new-user-experience-update-for-the-company-portal-website---2000968---"></a>Şirket Portalı web sitesi için yeni kullanıcı deneyimi güncelleştirmesinin önizlemesi <!--2000968 -->
Müşterilerden gelen geri bildirim temelinde Şirket Portalı web sitesine/iOS uygulama kataloğuna yeni özellikler ekliyoruz. Android, iOS ve Windows cihazlarının mevcut işlevselliğinde ve kullanılabilirliğinde önemli geliştirmeler göreceksiniz. Sitenin cihaz ayrıntıları, geri bildirim ve destek, cihaza genel bakış gibi alanlarında yeni, modern, hızlı yanıt veren bir tasarım elde edeceksiniz. Şunları da göreceksiniz:

- Tüm cihaz platformları arasında rahat iş akışları
- Geliştirilmiş cihaz kimlik ve kayıt akışları
- Daha yararlı hata iletileri
- Daha rahat bir dil, daha az teknik jargon
- Doğrudan uygulama bağlantıları paylaşabilme seçeneği
- Büyük uygulama katalogları için iyileştirilmiş performans
- Tüm kullanıcılar için artırılmış erişilebilirlik

Bu güncelleştirme şu anda önizleme aşamasındadır. Önizlemeye katılmak için http://aka.ms/webcpflighting adresinden kaydolabilirsiniz


<!-- 1805 start -->

### <a name="require-non-biometric-passcode-on-cold-app-launch-and-timeout----1506985---"></a>Sıfırdan uygulama başlatma işleminde ve zaman aşımı durumunda biyometrik olmayan bir geçiş kodu gerektirin <!-- 1506985 --> 

Sıfırdan uygulama başlatma işleminde ve yöneticinin belirttiği zaman aşımı durumunda biyometrik olmayan bir geçiş kodu gerektirerek, Intune şirket verilerine erişim için biyometrik tanımlama kullanımını kısıtlama yoluyla Mobil Uygulama Yönetimi'nin (MAM) etkinleştirildiği uygulamalarda gelişmiş güvenlik sağlayacak. Bu ayar, APP/MAM etkin uygulamalarına erişmek için Touch ID (iOS), Face ID (iOS), Android Biometric, veya geleceğin diğer kimlik doğrulama yöntemlerine güvenen kullanıcıları etkileyecek. Bu ayarlar birden çok parmak izi veya başka biyometrik erişim yöntemi olan bir cihazın şirket verilerini yanlış kullanıcıya gösterebildiği durumları ortadan kaldırarak, Intune yöneticilerinin kullanıcı erişimi üzerinde daha ayrıntılı bir denetim sahibi olmasına olanak tanıyacak. Azure portalında **Microsoft Intune**'u açın. **Mobil uygulamalar** > **Uygulama koruma ilkeleri** > **İlke ekle** > **Ayarlar**'ı seçin. Belirli ayarlar için **Erişim** bölümünü bulun.


<!-- 1803 start -->

### <a name="ability-to-deploy-required-line-of-business-lob-apps-to-all-users-on-windows-10-desktop-devices----1627835-rs4---"></a>Gerekli iş kolu (LOB) uygulamalarını Windows 10 Masaüstü cihazlarında Tüm Kullanıcılara dağıtabilme <!-- 1627835 RS4 -->
Müşteriler gerekli iş kolu Windows 10 uygulamalarını cihaz bağlamlarına yüklemek üzere dağıtabilecek. Böylelikle bu uygulamalar cihazdaki tüm kullanıcılara sağlanabilir. Bu yalnızca Windows 10 Masaüstü cihazları için geçerlidir.

### <a name="updating-the-help-and-feedback-experience-on-company-portal-app-for-android---1631531---"></a>Android için Şirket Portalı uygulamasında Yardım ve Geri Bildirim deneyimini güncelleştirme <!--1631531 -->

Android uygulamalarına yönelik en iyi yöntemlerle uyumlu olacak şekilde, Android için Şirket Portalı uygulamasında Yardım ve Geri Bildirim deneyimi güncelleştirilecek. Önümüzdeki birkaç ay içinde Android için Şirket Portalı uygulaması güncelleştirilerek **Yardım ve Geri Bildirim** menü öğesi **Yardım** ve **Geri Bildirim Gönder** menü öğelerine ayrılacak. Son kullanıcıları günlükleri Microsoft'a yüklemeye ve şirket desteğine sorunu açıklayan bir e-posta göndermeye yönlendirmek için, **Yardım** sayfasında **Sık Sorulan Sorular** bölümü ve **E-posta Desteği** düğmesi bulunacak. **Geri Bildirim Gönder** kullanıcıyı standart Microsoft geri bildirim gönderimine yönlendirecek ve kullanıcıdan "Bir şeyi beğendim" "Bir şeyi beğenmedim" veya "Bir fikrim var" arasında seçim yapması istenecek.

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>Uygulama koruma ilkeleri  <!-- 679615 -->
Intune Uygulama Koruma İlkeleri, tüm kiracıdaki tüm kullanıcılar için hızlı bir şekilde koruma sağlamaya yönelik genel ve varsayılan ilkeler oluşturma olanağı sunar.

<!-- the following are present prior to 1711 -->

## <a name="notices"></a>Bildirimler

Şu anda etkin bildirim yok.

### <a name="see-also"></a>Ayrıca bkz:
Son geliştirmelere ilişkin ayrıntılar için bkz. [Microsoft Intune’daki Yenilikler](whats-new.md).
