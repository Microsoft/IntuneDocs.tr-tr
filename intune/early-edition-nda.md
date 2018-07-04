---
title: Erken sürüm
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0500194f5afaba11f37b84bbdf606e6167632a71
ms.sourcegitcommit: afa2e84d5cadf5542ecabc26e61dc71919992a22
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37340199"
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

### <a name="reset-device-passcodes-from-company-portal-app-for-windows-10----2101282---"></a>Windows 10 için Şirket Portalı uygulamasından cihaz geçiş kodlarını sıfırlama <!-- 2101282 --> 
Çalışanlarınız yakın zamanda cihazlarının PIN’i veya geçiş kodunu doğrudan Windows 10 için Şirket Portalı uygulamasından sıfırlayabilecek. Bu işlevsellik, geçiş kodu sıfırlamalarını destekleyen hem uzak hem de yerel Intune tarafından yönetilen cihazlarda kullanılabilecek. Cihaz türüne bağlı olarak, bir uzak cihaza yapılan istek ya cihazın geçerli geçiş kodunu kaldırır ya da geçici bir geçiş kodu oluşturur. Yerel bir cihaz için sıfırlama isteğinde bulunan kullanıcılar, cihazın Ayarlar uygulamasına yeniden yönlendirilir.

### <a name="use-smime-to-encrypt-and-sign-a-users-multiple-devices-----1333642---"></a>Bir kullanıcının birden fazla cihazını şifrelemek ve imzalamak için S/MIME kullanın <!-- 1333642 -->
Gelecekteki bir güncelleştirme, içeri aktarılmış yeni bir sertifika profili kullanan S/MIME e-posta şifrelemesi içerecek (**Cihaz yapılandırması** > **Profiller** > **Profil oluşturun** > platform seçin > **PKCS içeri aktarılan sertifika** profil türü). Intune’da sertifikaları PFX biçiminde içeri aktarabilirsiniz. Intune, aynı sertifikaları tek bir kullanıcı tarafından kaydedilen birden fazla cihaza teslim edebilir. Ayrıca şunları da içerir:

- Yerel iOS e-posta profili, PFX biçiminde içeri aktarılan sertifikaları kullanan S/MIME şifrelemesini etkinleştirmeyi destekler.
- Windows Phone 10 cihazlarındaki yerel posta uygulaması, S/MIME sertifikalarını otomatik olarak kullanır.
- Özel sertifikalar, birden fazla platforma teslim edilebilir. Ancak tüm e-posta uygulamaları, S/MIME’yi desteklemez.
- Diğer platformlarda S/MIME’yi etkinleştirmek için posta uygulamasını el ile yapılandırmanız gerekebilir.  
- S/MIME şifrelemesini destekleyen e-posta uygulamaları, S/MIME e-posta şifrelemesi için sertifika alma işlemini MDM’nin destekleyemeyeceği bir şekilde halleder, ör. yayımcılarının sertifika deposundan okuma.

Desteklenir: Windows, Windows Phone 10, macOS, iOS, Android

### <a name="use-vpp-device-licenses-to-pre-provision-the-company-portal-during-dep-enrollment----1608345---"></a>DEP kaydı sırasında Şirket Portalı’nın ön sağlamasını yapmak için VPP cihaz lisanslarını kullanın <!-- 1608345 -->
Aygıt Kayıt Programı (DEP) kayıtları sırasında Şirket Portalı’nın ön sağlamasını yapmak için Volume Purchase Program (VPP) cihaz lisanslarını kullanabileceksiniz. Bunu yapmak için bir kayıt profili oluşturduğunuzda veya düzenlediğinizde, Şirket Portalı’nı yüklemek için kullanmak istediğiniz VPP belirtecini belirtin. Belirtecinizin süresinin dolmadığından ve Şirket Portalı uygulaması için yeterli lisansınız olduğundan emin olun. Belirtecin süresi dolduğu veya yeterli lisans olmadığı durumlarda, Intune bunun yerine Uygulama Mağazası Şirket Portalı’na istek gönderir (bu, Apple kimliği ister).

### <a name="bulk-delete-devices-on-devices-blade----1793693---"></a>Cihazlar dikey penceresinde cihazları toplu silme <!-- 1793693 -->
Cihazlar dikey penceresinde tek seferde birden fazla cihazı silmek mümkün olacaktır. **Cihazlar** > **Tüm cihazlar** > silmek istediğiniz cihazları seçin > **Sil**'i seçin. Silinemeyen cihazlar için bir uyarı görüntülenir.

### <a name="new-wi-fi-device-configuration-profile-for-windows-10-and-later----1879077---"></a>Windows 10 ve üzeri için yeni Wi-Fi cihaz yapılandırma profili <!-- 1879077 -->
Şu anda XML dosyalarını kullanarak Wi-Fi profillerini içeri ve dışarı aktarabilirsiniz. Tıpkı bazı diğer platformlarda olduğu gibi Intune’da doğrudan Wi-Fi cihaz yapılandırma profili oluşturabileceksiniz.

Profili oluşturmak için **Cihaz Yapılandırması** > **Profiller** > **Profil Oluştur** > **Windows 10 ve üzeri** > **Wi-Fi** seçeneklerini açın. 

Windows 10 ve üzeri için geçerlidir.

###  <a name="windows-line-of-business-lob-apps-file-extension-rename----1884873---"></a>Windows iş kolu (LOB) uygulamaları dosya uzantısını yeniden adlandırma <!-- 1884873 -->
Windows LOB uygulamaları için dosya uzantıları, *.appx* ve *.appxbundle*’dan *.msix* ve *.msixbundle*’a yeniden adlandırılacak. Microsoft Intune’da, **Mobil uygulamalar** > **Uygulamalar** > **Ekle**’yi seçerek bir uygulama ekleyebilirsiniz. **Bölme ekle** bölmesi görüntülenir ve **Uygulama türünü** seçmenize olanak tanır. Windows LOB uygulamaları için uygulama türü olarak **İş kolu uygulamasını** seçin, **Uygulama paketi dosyasını** seçin ve uygun uzantıya sahip bir yükleme dosyası girin.

### <a name="windows-defender-atp-configuration-package-automatically-added-to-configuration-profile----2144658---"></a>Windows Defender ATP yapılandırma paketi, otomatik olarak yapılandırma profiline eklenir <!-- 2144658 -->
Şu anda Intune’da [Gelişmiş Tehdit Koruması ve ekleme](advanced-threat-protection.md#onboard-devices-using-a-configuration-profile) cihazları kullanırken bir yapılandırma paketini indirip bunu yapılandırma profilinize ekliyorsunuz. Gelecekteki bir güncelleştirmede Intune, paketi otomatik olarak Windows Defender Güvenlik Merkezi'nden alır ve profilinize ekler.

Windows 10 ve üzeri için geçerlidir.

### <a name="kiosk---obsolete-is-grayed-out-and-cant-be-changed----2149998---"></a>Bilgi noktası - eski seçenek gri renkte ve değiştirilemez <!-- 2149998 -->
[Bilgi noktası özelliği](device-restrictions-windows-10.md#kiosk-preview---obsolete) (**Cihaz Yapılandırması** > **Profiller** > **Profil oluştur** > **Windows 10 ve üzeri** > **Cihaz kısıtlamaları**) artık kullanılmıyor ve [Windows 10 ve üzeri için bilgi noktası ayarları](kiosk-settings.md) ile değiştirildi. **Bilgi Noktası - Eski** özelliği gri renkte olacak ve kullanıcı arabirimi değiştirilemeyecek veya güncelleştirilemeyecek. 

Bilgi noktası modunu etkinleştirmek için bkz. [Windows 10 ve üzeri için bilgi noktası ayarları](kiosk-settings.md).

Windows 10 ve üzeri, Windows Holographic for Business için geçerlidir

### <a name="apis-to-use-3rd-party-certification-authorities----2184013---"></a>3. taraf sertifika yetkilileri kullanacak API’ler <!-- 2184013 -->
Üçüncü taraf sertifika yetkililerinin Intune ve SCEP ile tümleştirilmesini etkinleştirecek bir Java API’si olacaktır. Ardından kullanıcılar, SCEP sertifikasını bir profil ekleyebilir ve MDM kullanarak cihazlara uygulayabilir.

Intune şu anda [Active Directory Sertifika Hizmetleri kullanarak SCEP isteklerini](certificates-scep-configure.md) destekler.

### <a name="check-for-sccm-compliance----2192052---"></a>SCCM uyumluluğunu denetleme <!-- 2192052 -->
Gelecekte yapılacak bir güncelleştirmede yeni bir System Center Configuration Manager (SCCM) uyumluluk ayarı olacaktır (**Cihaz uyumluluğu** > **İlkeler** > **İlke oluşturma**  > **Windows 10**). SCCM, Intune uyumluluğuna sinyal gönderir. Intune ayarını kullanarak, tüm SCCM sinyallerinin “uyumlu” döndürmesini gerektirebilirsiniz.

Örneğin, tüm yazılım güncelleştirmelerinin cihazlarda yüklü olmasını gerektirirsiniz. SCCM’de bu gereksinim, "Yüklü" durumuna sahiptir. Cihazdaki herhangi bir program bilinmeyen bir durumdaysa cihaz, Intune ile uyumlu olmayacaktır.

Windows 10 ve üzeri için geçerlidir

### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low----2237572---"></a>Süresi dolan VPP belirteci veya yetersiz Şirket portalı lisansı uyarıları <!-- 2237572 -->
DEP kaydı sırasında Şirket Portalı’nın ön sağlamasını yapmak için Volume Purchase Program (VPP) kullanıyorsanız Intune, VPP belirtecinin süresi dolmak üzereyken ve Şirket Portalı lisansları yetersiz sayıdayken sizi uyarır.

### <a name="confirmation-required-to-delete-vpp-token-that-is-being-used-for-company-portal-pre-provisioning----2237634---"></a>Şirket Portalı ön sağlaması için kullanılan bir VPP belirtecini silmek için onay gerekir <!-- 2237634 -->
DEP kaydı sırasında Şirket Portalı’nın ön sağlaması için kullanılıyorsa bir Volume Purchase Program (VPP) belirtecini silmek için onay gerekir.

### <a name="automatically-mark-android-devices-enrolled-by-using-samsung-knox-mobile-enrollment-as-corporate----2404851---"></a>Samsung Knox Mobil Kayıt kullanarak “şirket” olarak kaydedilen Android cihazları otomatik olarak işaretleme <!-- 2404851 -->
Varsayılan olarak Samsung Knox Mobil Kayıt kullanarak kaydedilen Android cihazlar, **Cihaz Sahipliği** altında **şirket** olarak işaretlenir. Şirket cihazlarını Knox Mobil Kayıt kullanarak kaydetmeden önce IMEI veya seri numaraları kullanarak el ile belirlemeniz gerekmez.

### <a name="toggle-to-show-or-not-show-the-end-session-button-on-a-kiosk-browser----2455253---"></a>Bir Bilgi Noktası tarayıcısında Oturumu Sonlandır düğmesini gösterme veya gizleme geçişi <!-- 2455253 -->
Bilgi Noktası tarayıcılarını Oturumu Sonlandır düğmesini gösterecek veya gizleyecek şekilde yapılandırabileceksiniz. Denetim seçeneğini **Cihaz yapılandırması** > **Bilgi noktası (önizleme)** > **Bilgi Noktası Web Tarayıcısı**’ndan görebilirsiniz. Açılırsa kullanıcı bir düğmeye tıkladığında uygulama, oturumu sonlandırma için onay ister. Onaylandığında tarayıcı, tüm göz atma verilerini temizler ve varsayılan URL’ye geri gider.

### <a name="create-an-esim-cellular-configuration-profile----2564077---"></a>eSIM hücresel yapılandırma profili oluşturma <!-- 2564077 -->
**Cihaz yapılandırmasında** bir eSIM hücresel profili oluşturabileceksiniz. Cep telefonu operatörünüz tarafından sağlanan hücresel etkinleştirme kodlarını içeren bir dosyayı içeri aktarabilirsiniz. Ardından bu profilleri, Surface Pro LTE ve diğer eSIM özellikli cihazlar gibi eSIM LTE etkinleştirilmiş Windows 10 cihazlara dağıtabilirsiniz.

[Cihazınızın eSIM profillerini destekleyip desteklemediğini](https://support.microsoft.com/help/4020763/windows-10-use-esim-for-cellular-data) görmek için kontrol edin.

Windows 10 ve üzeri için geçerlidir. 




<!-- 1806 start -->

### <a name="see-device-configuration-profiles-in-conflict----1556983---"></a>Çakışması olan cihaz yapılandırma profillerini görme <!-- 1556983 -->
**Cihaz Yapılandırmasında** mevcut profillerin bir listesi gösterilir. Bu güncelleştirme ile çakışması olan profiller hakkında ayrıntılar sağlayan yeni bir sütun eklenir. Çakışması olan ayarı ve profili görmek için çakışan bir satır seçebilirsiniz. 

[Cihaz yapılandırma profillerinden](device-profiles.md) daha fazla bilgi edinebilirsiniz.

### <a name="corporate-owned-single-use-cosu-support-for-android-devices----1630973---"></a>Android cihazları için şirkete ait, tek kullanım (COSU) desteği <!-- 1630973 -->

Intune üst düzeyde yönetilen, kilitlenen, bilgi noktası stilindeki Android cihazlarını destekler. Bu sayede yöneticiler cihazın kullanımını tek uygulamayla veya küçük bir uygulama kümesiyle kilitleyebilir ve kullanıcıların cihazda başka uygulamaları etkinleştirmesini veya başka eylemler gerçekleştirmesini engelleyebilir.

### <a name="macos-support-for-apple-device-enrollment-program----747651---"></a>Apple Aygıt Kayıt Programı için macOS desteği <!-- 747651 -->

Intune, macOS cihazlarının Apple Aygıt Kayıt Programı'na (DEP) kaydedilmesini destekleyecek. Bunu yapmak için:

1. Deploy.apple.com sitesinde, macOS seri numaralarını bir MDM sunucusuna atayın.
2. Seri numaralarını Intune'da içeri aktarın.
3. macOS cihazlarına özgü bir kayıt programı profili oluşturun.

### <a name="google-name-changes-for-android-for-work-and-play-for-work---842873---"></a>Android for Work ve Play for Work için Google ad değişiklikleri <!--842873 -->
Intune, "Android for Work" terminolojisini Google marka değişikliklerini yansıtacak şekilde güncelleştirecek.  "Android for Work" ve "Play for Work" terimleri artık kullanılmayacak. Bağlama göre farklı bir terminoloji kullanılacak:

- "Android kurumsal", genel olarak modern Android yönetim yığınına karşılık gelir.
- "İş Profili" veya "Profil Sahibi", iş profilleriyle yönetilen KCG cihazlarına karşılık gelir.
- "Yönetilen Google Play", Google uygulama mağazasına karşılık gelir.

### <a name="monitor-ios--app-configuration-status-per-device----880037-eeready-eestaged---"></a>Cihaz başına iOS uygulama yapılandırması durumunu izleme <!-- 880037 eeready eestaged -->

Microsoft Intune yöneticisi olarak, yönetilen her cihaz için iOS uygulama yapılandırması durumunu izleyebileceksiniz. Azure portalında **Microsoft Intune**'dan **Cihazlar** > **Tüm cihazlar**'ı seçin. Yönetilen cihaz listesinden belirli bir cihazı seçerek o cihazın dikey penceresini görüntüleyin. Cihaz dikey penceresinde **Uygulama yapılandırması**'nı seçin.  

### <a name="3rd-party-keyboards-can-be-blocked-by-app-settings-on-ios----1248481---"></a>iOS'ta üçüncü taraf klavyeler APP ayarlarıyla engellenebilir <!-- 1248481 -->
iOS cihazlarında, Intune yöneticileri ilke korumalı uygulamalarda kuruluş verilerine erişilirken üçüncü taraf klavyelerin kullanımını engelleyebilecek. Uygulama Koruma İlkesi (APP) üçüncü taraf klavyelerini engelleyecek şekilde ayarlandığında, cihaz kullanıcısı üçüncü taraf klavyesini kullanarak şirket verileriyle ilk kez etkileşim kurarken bir ileti alacak. Yerel klavye dışındaki tüm seçenekler engellenecek ve cihaz kullanıcıları bunları görmeyecek. Cihaz kullanıcıları iletişim kutusu iletisini tek bir kez görür. 

### <a name="create-device-compliance-policy-using-firewall-settings-on-macos-devices----1497640---"></a>macOS cihazlarında Güvenlik Duvarı ayarlarını kullanarak cihaz uyumluluk ilkesi oluşturma <!-- 1497640 -->
Yeni bir macOS uyumluluk ilkesi oluşturduğunuzda (**Cihaz uyumluluğu** > **İlkeler** > **İlke oluştur** > **Platform: macOS** > **Sistem güvenliği**), bazı yeni **Güvenlik Duvarı** ayarları sağlanır: 
- **Güvenlik Duvarı**: Gelen bağlantıların ortamınızda nasıl işleneceğini yapılandırın.
- **Gelen bağlantılar**: DHCP, Bonjour ve IPSec gibi temel İnternet hizmetleri için gerekenler dışında tüm gelen bağlantıları **engelleyin**. Bu ayar tüm paylaşım hizmetlerini de engeller.
- **Gizli Mod**: Cihazın yoklama isteklerine yanıt vermesini önlemek için gizli modu **etkinleştirin**. Cihaz, yetkilendirilmiş uygulamalardan gelen istekleri yanıtlamaya devam eder.

Şunlar için geçerlidir: macOS 10.12 ve üstü

### <a name="use-samaccountname-as-the-account-username-for-email-profiles----1500307---"></a>E-posta profilleri için hesap kullanıcı adı olarak sAMAccountName kullanın <!-- 1500307 -->

Android, iOS ve Windows 10'da e-posta profillerinin hesap kullanıcı adı olarak şirket içi **sAMAccountName** adını kullanabilirsiniz. Ayrıca Azure Active Directory'de (Azure AD) `domain`.veya `ntdomain` özniteliğinden etki alanını da alacaksınız. Bunun yerine özel bir statik etki alanı girebilirsiniz.

Bu özelliği kullanmak için, şirket içi Active Directory ortamınızdan Azure AD'ye `sAMAccountName` özniteliğini eşitlemeniz gerekir.

Şunlar için geçerlidir: Android, iOS, Windows 10 ve üstü

### <a name="require-non-biometric-passcode-on-app-launch-and-timeout----1506985---"></a>Uygulama başlatma işleminde ve zaman aşımı durumunda biyometrik olmayan bir geçiş kodu gerektirin <!-- 1506985 -->

Uygulama başlatma işleminde ve yöneticinin belirttiği zaman aşımı durumunda biyometrik olmayan bir geçiş kodu gerektirerek, Intune şirket verilerine erişim için biyometrik tanımlama kullanımını kısıtlama yoluyla Mobil Uygulama Yönetimi'nin (MAM) etkinleştirildiği uygulamalarda gelişmiş güvenlik sağlayacak. Bu ayar, APP/MAM etkin uygulamalarına erişmek için Touch ID (iOS), Face ID (iOS), Android Biometric, veya geleceğin diğer kimlik doğrulama yöntemlerine güvenen kullanıcıları etkileyecek. Bu ayarlar birden çok parmak izi veya başka biyometrik erişim yöntemi olan bir cihazın şirket verilerini yanlış kullanıcıya gösterebildiği durumları ortadan kaldırarak, Intune yöneticilerinin kullanıcı erişimi üzerinde daha ayrıntılı bir denetim sahibi olmasına olanak tanıyacak. Azure portalında **Microsoft Intune**'u açın. **Mobil uygulamalar** > **Uygulama koruma ilkeleri** > **İlke ekle** > **Ayarlar**'ı seçin. Belirli ayarlar için **Erişim** bölümünü bulun.

### <a name="selective-wipe-of-organizations-app-data----1507030---"></a>Kuruluşun uygulama verilerini seçmeli silme <!-- 1507030 -->
Uygulama Koruma İlkeleri (APP) Erişim ayarlarının koşullarına uyulmadığında, yöneticiler yeni bir eylem olarak kuruluş verilerinin seçmeli silinmesini yapılandırabilecek.  Bu özellik yöneticilerin önceden yapılandırılmış ölçütler temelinde hassas kuruluş verilerini otomatik olarak korumasına ve uygulamalardan kaldırmasına yardımcı olur.

### <a name="revoking-an-ios-app-purchased-through-vpp----1777384---"></a>VPP üzerinden satın alınan iOS uygulamasını iptal etme <!-- 1777384 -->
Microsoft Intune yöneticisi olarak, Volume Purchase Program (VPP) üzerinden satın alınan seçili iOS uygulamasının lisansını iptal edebileceksiniz. Uygulamanın artık kendisine atanmış durumda olmadığını kullanıcıya bildirebilirsiniz. Bir uygulama lisansını iptal etmek ilgili VPP uygulamasını cihazdan kaldırmaz. Bir VPP uygulamasını kaldırmak için, atama işlemini **Kaldır** olarak değiştirmelisiniz. Geri kazanılan lisans sayısı, Intune'un **Uygulama** iş yükündeki **Lisanslı Uygulamalar** düğümünde yansıtılacak. iOS VPP uygulamalarıyla ilgili daha fazla bilgi için bkz. [Microsoft Intune ile Volume Purchase Program üzerinden satın alınan iOS uygulamalarını yönetme](vpp-apps-ios.md).

### <a name="office-365-pro-plus-language-packs----1833450---"></a>Office 365 Pro Plus dil paketleri <!-- 1833450 -->
Intune yöneticisi olarak, Intune aracılığıyla yönetilen Office 365 Pro Plus uygulamaları için ek dillerin dağıtımını yapabileceksiniz. Kullanılabilir diller listesi, dil paketinin **Tür** bilgisini içerir (çekirdek, kısmı ve yazım denetleme). Azure portalında **Microsoft Intune** > **Mobil uygulamalar** > **Uygulamalar** > **Ekle**'yi seçin. **Uygulama ekle** dikey penceresindeki **Uygulama türü** listesinde **Office 365 Paketi** altından **Windows 10**'u seçin. **Uygulama Paketi Ayarları** dikey penceresinde **Diller**'i seçin.

### <a name="revoke-ios-vpp-app-license----1863797---"></a>iOS VPP uygulama lisansını iptal etme <!-- 1863797 -->
Yönetici olarak, bir kullanıcı veya cihaza atanmış olan iOS VPP uygulama lisansını geri kazanabileceksiniz. iOS VPP uygulamasını kaldırmak uygulama lisansını geri kazanmanıza da olanak tanıyacak. Ardından, uygulama lisansını başka bir kullanıcı veya cihaza atamayı seçebilirsiniz. iOS VPP uygulama lisansları hakkında daha fazla bilgi için bkz. [Microsoft Intune'da toplu satın alınan iOS uygulamalarını yönetme](vpp-apps-ios.md).

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

### <a name="updates-to-out-of-compliance-messages-in-company-portal-app----1832222---"></a>Şirket Portalı uygulamasında uyumsuzluk iletilerine güncelleştirmeler <!-- 1832222 -->
Bir cihaz uyumlu olmadığında cihaz kullanıcılarının gördüğü iletileri yeniden düzenliyoruz. İletiler özgün anlamlarını koruyacak ancak daha kolay bir dil ve daha az teknik terminoloji ile güncelleştirilecek. Ayrıca belge bağlantılarını ve bunları güncel tutmak için düzeltme adımlarını da yeniliyoruz.  

Aşağıda öncesi ve sonrası gösterilen metin, göreceğiniz ileti iyileştirmelerinin bir örneğidir:  

Öncesi: *Bu cihaz, BT yöneticiniz tarafından belirlenen süre içinde Intune ile iletişime geçmedi. Bu sorunu çözmek için lütfen cihazınızda şirket portalı uygulamasını açın ve Uyumluluğu Denetle düğmesine tıklayın.*  

Sonrası: *Cihazınız bir süredir kuruluşunuza iade edilmedi. Bağlantıyı yeniden kurmak üzere cihazınızda Şirket Portalı uygulamasını açın ve cihazınız için Ayarları Denetle’ye dokunun*.  

### <a name="edit-your-office-365-pro-plus-app-deployments----2150145---"></a>Office 365 Pro Plus uygulama dağıtımlarınızı düzenleme <!-- 2150145 -->
Microsoft Intune yöneticisi olarak, Office 365 Pro Plus uygulama dağıtımlarınızı düzenleme olanağınız artacaktır. Azure portalında **Microsoft Intune** > **Mobil uygulamalar** > **Uygulamalar**'ı seçin. Uygulama listesinden Office 365 Pro Plus Suite ürününüz seçin.  

### <a name="per-row-review-of-duplicate-corporate-device-identifiers-uploaded----2203794---"></a>Karşıya yüklenmiş yinelen şirket cihazı tanımlayıcılarını satır temelinde gözden geçirme <!-- 2203794 -->
Şirket kimliklerini karşıya yüklerken, Intune tüm yinelemelerin listesini sağlayacak ve size mevcut bilgileri değiştirme veya koruma seçeneği verecek. **Cihaz kaydı** > **Şirket Cihazı Tanımlayıcıları** > **Tanımlayıcıları Ekle**'yi seçtikten sonra yinelemeler varsa rapor görüntülenecek. 

### <a name="manually-add-corporate-device-identifiers----2203803---"></a>Şirket cihazı tanımlayıcılarını el ile ekleme <!-- 2203803 -->
Şirket cihazı kimliklerini el ile ekleyebileceksiniz. **Cihaz kaydı** > **Şirket Cihazı Tanımlayıcıları** > **Ekle**'yi seçin.

### <a name="new-status-for-devices-in-device-compliance----2308882---"></a>Cihaz uyumluluğunda cihazlar için yeni durum <!-- 2308882 -->
**Cihaz uyumluluğu** > **İlkeler** > bir ilke seçin > **Genel Bakış**’a aşağıdaki yeni durumlar eklenecektir:
- başarılı
- hata
- çakışma
- bekleniyor
- uygun değil

Farklı bir platformdaki cihaz sayısını gösteren bir resim de görüntülenir. Örneğin bir iOS profiline bakıyorsanız, yeni kutucuk yine bu profile atanmış olan iOS dışı cihazların sayısını gösterir. 

### <a name="device-compliance-supports-3rd-party-anti-virus-solutions----2325484---"></a>Cihaz uyumluluğu üçüncü taraf virüsten koruma çözümlerini destekler <!-- 2325484 -->
Yeni bir cihaz uyumluluğu ilkesi oluşturduğunuzda (**Cihaz uyumluluğu** > **İlkeler** > **İlke oluştur** > **Platform: Windows 10 ve üzeri** > **Ayarlar** > **Sistem Güvenliği**) yeni **Cihaz Güvenliği** seçenekleri olacak: 
- **Virüsten koruma**: **Gerekli** olarak ayarlandığında, Windows Güvenlik Merkezi'ne kaydedilmiş Symantec gibi virüsten koruma çözümlerini kullanarak uyumluluğu denetleyebilirsiniz. 
- **Casus yazılım önleme**: **Gerekli** olarak ayarlandığında, Windows Güvenlik Merkezi'ne kaydedilmiş Symantec gibi casus yazılım önleme çözümlerini kullanarak uyumluluğu denetleyebilirsiniz. 

Şunlar için geçerlidir: Windows 10 ve üzeri 

<!-- 1805 start -->

### <a name="improved-troubleshooting-for-app-installation----928990---"></a>Uygulama yüklemesi için geliştirilmiş sorun giderme <!-- 928990 -->
Microsoft Intune MDM ile yönetilen cihazlarda bazen uygulama yüklemeleri başarısız olabilir. Bu uygulamaların yüklemesi başarısız olduğunda, başarısızlık sebebini anlamak ve sorunu gidermek zor olabilir. Uygulama Sorun Giderme özelliklerimizin bir Genel Önizlemesini yayınlıyoruz. Tüm cihazlarda **Yönetilen Uygulamalar** adlı yeni bir düğüm göreceksiniz. Bu düğümde Intune MDM yoluyla teslim edilen uygulamalar listelenir. Burada uygulama yükleme durumlarının bir listesini bulacaksınız. Bir uygulamayı seçtiğinizde, o uygulamaya özel sorun giderme görünümünü açmış olacaksınız. Sorun giderme görünümünde uygulamanın oluşturulma, değiştirilme, hedeflenme ve cihaza teslim edilme tarihleri gibi uçtan uca yaşam döngüsünü bulabileceksiniz. Buna ek olarak, uygulama yüklemesinin başarısız olması durumunda size bir hata kodu ve hatanın sebebiyle ilgili yardım olacak bir ileti sunulacak.

### <a name="require-non-biometric-passcode-on-cold-app-launch-and-timeout----1506985---"></a>Sıfırdan uygulama başlatma işleminde ve zaman aşımı durumunda biyometrik olmayan bir geçiş kodu gerektirin <!-- 1506985 --> 

Sıfırdan uygulama başlatma işleminde ve yöneticinin belirttiği zaman aşımı durumunda biyometrik olmayan bir geçiş kodu gerektirerek, Intune şirket verilerine erişim için biyometrik tanımlama kullanımını kısıtlama yoluyla Mobil Uygulama Yönetimi'nin (MAM) etkinleştirildiği uygulamalarda gelişmiş güvenlik sağlayacak. Bu ayar, APP/MAM etkin uygulamalarına erişmek için Touch ID (iOS), Face ID (iOS), Android Biometric, veya geleceğin diğer kimlik doğrulama yöntemlerine güvenen kullanıcıları etkileyecek. Bu ayarlar birden çok parmak izi veya başka biyometrik erişim yöntemi olan bir cihazın şirket verilerini yanlış kullanıcıya gösterebildiği durumları ortadan kaldırarak, Intune yöneticilerinin kullanıcı erişimi üzerinde daha ayrıntılı bir denetim sahibi olmasına olanak tanıyacak. Azure portalında **Microsoft Intune**'u açın. **Mobil uygulamalar** > **Uygulama koruma ilkeleri** > **İlke ekle** > **Ayarlar**'ı seçin. Belirli ayarlar için **Erişim** bölümünü bulun.

### <a name="block-app-access-based-on-unapproved-device-vendors-and-models-----1425689----"></a>Onaylanmamış cihaz satıcıları ve modellerine göre uygulama erişimini engelleme <!-- 1425689 ! -->
Intune BT yöneticisi, belirlenen Android üreticileri ve/veya iOS modelleri listesini Intune Uygulama Koruması İlkeleri yoluyla zorlayabilecek. BT yöneticisi, Android ilkeleri için noktalı virgülle ayrılmış bir üretici listesi ve aynı şekilde iOS ilkeleri için bir cihaz modelleri listesi sağlayabilecek. Intune Uygulama Koruması İlkeleri, yalnızca Android ve iOS için geçerlidir. Bu belirtilen listede gerçekleştirilebilecek iki ayrı eylem vardır:
- Belirtilmemiş cihazlarda uygulama erişimini engelleme.
- Veya belirtilmemiş cihazlarda şirket verilerini seçmeli olarak silme. 

İlke gereksinimleri karşılanmazsa kullanıcı, hedeflenen uygulamaya erişemeyecek. Ayarlara bağlı olarak kullanıcı engellenebilir veya uygulama dahilinde kullanıcının şirket verileri seçmeli olarak silinir. iOS cihazlarda bu özellik, en düşük sürüm ayarlarının hedeflenen uygulamalarda zorlanabilmesi için uygulamaların katılımının (WXP, Outlook, Managed Browser, Yammer) Intune APP SDK’sıyla tümleştirilmesini gerektirir. Bu tümleştirme, sıralı bir şekilde gerçekleşir ve belirli uygulama ekiplerine bağımlıdır. Android’de bu özellik, Şirket Portalı’nın en son sürümünü gerektirir. 

Son kullanıcı cihazlarında Intune istemcisi, Intune’un Uygulama Koruma İlkeleri dikey penceresinde belirtilen dizelerin basit eşleştirmesine dayalı olarak eylem gerçekleştirir. Bu, tamamen cihazın rapor ettiği değere bağlıdır. Bu nedenle BT yöneticisinin amaçlanan davranışın doğru olduğundan emin olması önerilir. Bu ayar, küçük bir kullanıcı grubuna hedeflenen çeşitli cihaz üreticileri ve modellerinde sınanarak doğruluğundan emin olunabilir. Microsoft Intune’da uygulama koruma ilkelerini görüntülemek ve ilke eklemek için **Mobil uygulamalar** > **Uygulama koruma ilkeleri**’ni seçin. Uygulama koruma ilkeleri hakkında daha fazla bilgi için bkz. [Uygulama koruma ilkeleri nelerdir](app-protection-policy.md).

### <a name="access-actions-for-app-protection-policies----1483510-eeready---"></a>Uygulama koruma ilkeleri için eylemlere erişme <!-- 1483510 EEready -->
Yakında uyumsuz cihazları açık olarak silmek, engellemek veya uyarmak üzere uygulama koruma ilkeleri yapılandırabileceksiniz. En yeni *silme* eylemi, bir cihazdan şirketinizin verilerini kaldırır. Bir silme işlemi gerçekleştirildiğinde, kullanıcıya silme sebebi ve düzeltme adımları bildirilir. En düşük işletim sistemi sürümü gibi bazı ayarlarda, engelleme ve silme gibi birden fazla eylem gerçekleştirebileceksiniz. Bu eylemler uygulama başlatıldığında tetiklenir.

<!-- 1804 start -->

### <a name="rules-for-removing-devices----1609459---"></a>Cihaz kaldırma kuralları <!-- 1609459 -->
Ayarladığınız süre boyunca (gün) iade edilmeyen cihazları otomatik olarak kaldırmanıza imkan veren yeni kurallar kullanılabilir olacak. Yeni kuralı görmek için **Intune** bölmesine gidin, **Cihazlar**’ı ve **Cihaz kaldırma kuralları**’nı seçin.

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