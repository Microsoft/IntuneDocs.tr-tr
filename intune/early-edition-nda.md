---
title: Erken sürüm
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0f6447f4a5cfb2638278a59414e83f744adb8c81
ms.sourcegitcommit: ed97b68f08c1a8469f0b45bc1c839a0b5f5c71e0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "45978272"
---
# <a name="the-early-edition-for-microsoft-intune---september-2018"></a>Microsoft Intune için erken sürüm - Eylül 2018

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

<!-- 1809 start -->

### <a name="user-account-access-of-intune-apps-on-managed-android-and-ios-devices-----1248496----"></a>Yönetilen Android ve iOS cihazlarda Intune uygulamalarına kullanıcı hesabı erişimi <!-- ! 1248496  -->

Microsoft Intune yöneticisi olarak yönetilen cihazlarda hangi kullanıcı hesaplarının Microsoft Office uygulamalarına eklendiğini denetleyebileceksiniz. Erişimi yalnızca izin verilen kullanıcı hesaplarıyla sınırlayabilecek ve kayıtlı cihazlarda kişisel hesapları engelleyebileceksiniz. 

### <a name="create-dns-suffixes-in-vpn-configuration-profiles-on-devices-running-windows-10----1333668---"></a>Windows 10 çalıştıran cihazlardaki VPN yapılandırma profillerinde DNS son ekleri oluşturma <!-- 1333668 -->
Bir VPN cihaz yapılandırma profili oluşturduğunuzda (**Cihaz yapılandırması** > **Profiller** > **Profil oluştur** > **Windows 10 ve üzeri** platform > **VPN** profil türü) bazı DNS ayarları girersiniz. Artık Intune’da da birden fazla **DNS son eki** girebileceksiniz. DNS son ekleri kullanırken bir ağ kaynağını tam etki alanı adı (FQDN) yerine kısa adını kullanarak arayabilirsiniz. Bu güncelleştirme ayrıca Intune’da DNS son eklerinin sırasını değiştirmenize de imkan verir.
[Windows 10 VPN ayarları](vpn-settings-windows-10.md#dns-settings) makalesi, geçerli DNS ayarlarını listeler.
Şunlar için geçerlidir: Windows 10 cihazlar

### <a name="support-for-always-on-vpn-for-android-enterprise-work-profiles----1333705---"></a>Android kurumsal iş profillerinde her zaman açık VPN desteği <!-- 1333705 -->
Yönetilen iş profillerine sahip Android kurumsal cihazlarda Her Zaman Açık VPN bağlantıları kullanabileceksiniz. Her zaman açık VPN bağlantıları; kullanıcı cihazının kilidini açtığında, cihaz yeniden başlatıldığında veya kablosuz ağ değiştiğinde bağlı kalır veya hemen tekrar bağlanır. Bağlantıyı “kilitli”moduna da alabilirsiniz, böylece VPN bağlantısı etkin olana kadar tüm ağ trafiği engellenir.
Her Zaman Açık VPN ayarı şurada olacaktır: **Cihaz yapılandırması** > **Profiller** > **Profil oluştur** > **Android kurumsal** platform için > **Yalnızca İş Profilleri** altında **Cihaz kısıtlamaları** Profil türü için > **Bağlantı** ayarları. 

### <a name="outlook-for-ios-and-android-app-configuration-policy---1828527---"></a>iOS ve Android için Outlook uygulama yapılandırma ilkesi <!--1828527 -->
iOS’ta bir iOS için Outlook ve Android uygulama yapılandırma ilkesi oluşturabileceksiniz. Ek yapılandırma ayarları, iOS ve Android için Outlook’ta etkinleştirildikçe eklenecektir.

###  <a name="windows-line-of-business-lob-app-file-extensions----1884873---"></a>Windows iş kolu (LOB) uygulaması dosya uzantıları <!-- 1884873 -->
Windows LOB uygulamalarının dosya uzantıları arasında *.msi*, *.appx*, *.appxbundle*, *.msix* ve *.msixbundle* bulunur. Microsoft Intune'da **İstemci uygulamaları** > **Uygulamalar** > **Ekle**’yi seçerek bir uygulama ekleyebilirsiniz. **Uygulama türü**'nü seçmenize izin veren **Uygulama ekle** bölmesi görüntülenir. Windows LOB uygulamalarında, uygulama türü olarak **İş kolu uygulamasını**, **Uygulama paket dosyasını** seçin ve ardından uygun uzantılı bir yükleme dosyası girin.

### <a name="remotely-lock-noncompliant-devices----2064495---"></a>Uyumsuz cihazları uzaktan kilitleme <!-- 2064495 -->
Bir cihazın uyumlu olmadığı durumlarda, uyumluluk ilkesinde cihazı uzaktan kilitleyen bir eylem oluşturabileceksiniz. Intune > **Cihaz uyumluluğu**’nda yeni bir ilke oluşturun veya mevcut bir ilkeyi seçin. **Uyumsuzluğa yönelik eylemler** > **Ekle**’yi ve cihazı uzaktan kilitlemeyi seçin.
Şu platformlarda desteklenir: 
- Android
- iOS
- Mac OS
- Windows 10 Mobile 
- Windows Phone 8.1 ve üzeri 

### <a name="intune-app-data-transfer-settings-on-ios-mdm-enrolled-devices----2244713---"></a>iOS MDM kayıtlı cihazlarda Intune APP veri aktarımı ayarları <!-- 2244713 -->
iOS MDM kayıtlı cihazlarda Intune APP veri aktarımı ayarlarının denetimini, kayıtlı kullanıcının kimliğini belirtmekten ayrı tutabileceksiniz. IntuneMAMUPN kullanmayan yöneticiler, davranış değişikliği gözlemlemeyecektir. Bu işlev kullanılabilir olduğunda, kayıtlı cihazlarda veri aktarımı davranışını denetlemek için IntuneMAMUPN kullanan yöneticiler yeni ayarları gözden geçirmeli ve APP ayarlarını gerektiği gibi güncelleştirmelidir.

### <a name="use-a-pre-shared-key-in-a-windows-10-wi-fi-profile----2662938---"></a>Bir Windows 10 Wi-Fi profilinde önceden paylaşılan anahtar kullanma <!-- 2662938 -->
Windows 10’da bir Wi-Fi yapılandırma profilinin kimliğini doğrulamak için WPA/WPA2 Kişisel güvenlik protokolü ile birlikte bir önceden paylaşılan anahtar (PSK) kullanabileceksiniz.
Şu anda önceden paylaşılan anahtarları kullanmak için bir Wi-Fi profilini içeri aktarmanız veya özel bir profil oluşturmanız gerekiyor. [Windows 10 için Wi-Fi ayarları](wi-fi-settings-windows.md) makalesi, geçerli ayarları listeler. 

### <a name="app-protection-policy-app-settings-for-web-data----2662995-eeready---"></a>Web verileri için Uygulama Koruma İlkesi (APP) ayarları <!-- 2662995 eeready -->
Gerek Android gerekse iOS cihazlarında Web içeriği için uygulama ilke ayarları, gerek http gerekse https Web bağlantılarını, ayrıca iOS Evrensel Bağlantıları ve Android Uygulama Bağlantıları aracılığıyla veri aktarımını daha iyi işleyecek şekilde güncelleştirilecektir.  

### <a name="autopilot-device-sync-frequency-increasing-to-every-12-hours----2753673---"></a>Autopilot cihaz eşitleme sıklığı 12 saatte bir olarak artıyor <!-- 2753673 -->
Autopilot cihazlar, 24 saatte bir yerine 12 saatte bir eşitlenecek.

### <a name="apply-autopilot-profile-to-enrolled-win-10-devices-not-already-registered-for-autopilot----1558983---"></a>Autopilot’a kayıtlı olmayan kayıtlı Win 10 cihazlara Autopilot profili uygulama <!-- 1558983 -->
Kayıtlı olduğu halde Autopilot’a kayıtlı olmayan Win 10 cihazlara Autopilot profili uygulayabilirsiniz. Autopilot profilinde **Hedeflenen tüm cihazları Autopilot’a dönüştür** seçeneğini belirterek Autopilot olmayan cihazları Autopilot dağıtım hizmetine otomatik olarak kaydedin. Kaydın işlenmesi için 48 saat kadar bekleyin. Cihazın kaydı kaldırıldığında ve cihaz sıfırlandığında Autopilot, cihazı sağlar. 

### <a name="create-and-assign-multiple-enrollment-status--page-profiles-to-azure-ad-groups----2526564--"></a>Azure AD gruplarına birden fazla Kayıt Durumu Sayfası profili oluşturma ve atama <!-- 2526564-->
Azure AAD kullanıcı gruplarına birden fazla Kayıt Durumu Sayfası profili oluşturup atayabileceksiniz.

### <a name="intune-landing-page-updates-and-node-rename---2867309---"></a>Intune giriş sayfası güncelleştirmeleri ve düğümü yeniden adlandırma <!--2867309 -->
Intune giriş sayfasında daha iyi görselleştirme için yeni ve değiştirilmiş izleme kutucukları ve grafikleri olacak. **Mobil uygulamalar** düğümü, **İstemci uygulamalar** olarak değişecek.

### <a name="increased-end-user-access-using-the-company-portal-app----772203---"></a>Şirket Portalı uygulaması kullanılarak artan son kullanıcı erişimi <!-- 772203 -->
Son kullanıcılar, Şirket Portalı uygulaması üzerinden parola ve AAD profillerini sıfırlama gibi anahtar hesap eylemlerine erişebilecekler.

### <a name="issue-scep-certificates-to-user-less-devices----1744554---"></a>Kullanıcısız cihazlara SCEP sertifikaları verme <!-- 1744554 -->
Şu anda sertifikalar kullanıcılara atanmaktadır. Ancak bilgi noktası cihazları gibi kullanıcısız olanlar da dahil olmak üzere cihazlara SCEP sertifikaları atayabileceksiniz (**Cihaz yapılandırması** > **Profiller** > **Profil oluştur** > **Windows 10 ve üzeri** platform için > **SCEP sertifikası** profil için). Diğer güncelleştirmeler şu şekildedir:
- SCEP profilindeki **Konu** özelliği, artık özel bir metin kutusundadır ve yeni değişkenler içerebilir. 
- SCEP profilindeki **Konu diğer adı (SAN)** özelliği artık tablo biçimindedir ve yeni değişkenler içerebilir. Yöneticiler tabloda bir öznitelik ekleyebilir ve değeri özel bir metin kutusunda doldurabilir. SAN, aşağıdaki öznitelikleri destekleyecek: 
  - DNS
  - E-posta adresi
  - UPN Bu yeni değişkenler, özel bir değer metin kutusunda statik metin ile eklenebilir. Örneğin DNS özniteliği `DNS = {{AzureADDeviceId}}.domain.com` olarak eklenebilir.
  > [!NOTE]
  > Küme ayraçları, noktalı virgül ve düz çizgi işareti “ { } ; | ” SAN statik metninde kullanılmaz. Küme ayraçları, `Subject` veya `Subject alternative name` olarak kabul edilmek için yalnızca yeni cihaz sertifika değişkenlerinden birini kapatmalıdır. Yeni cihaz sertifika değişkenleri:  
```
"{{AAD_Device_ID}}",
"{{Device_Serial}}",
"{{Device_IMEI}}",
"{{SerialNumber}}",
"{{IMEINumber}}",
"{{AzureADDeviceId}}",
"{{WiFiMacAddress}}",
"{{IMEI}}",
"{{DeviceName}}",
"{{FullyQualifiedDomainName}}",
"{{MEID}}",
```

> [!NOTE]
>  - `{{FullyQualifiedDomainName}}` yalnızca Windows ve etki alanına katılmış cihazlarda kullanılır. 
>  -  Bir cihaz sertifikası için konu veya SAN’da IMEI, Seri Numarası ve Tam Etki Alanı Adı gibi cihaz özellikleri belirtirken cihaza erişimi olan biri tarafından kandırma amaçlı olarak farklı özellikler verilebileceğine dikkat edin. 

[Bir SCEP sertifika profili oluşturma](certificates-scep-configure.md#create-a-scep-certificate-profile) makalesi, bir SCEP yapılandırma profili oluştururken geçerli değişkenleri listeler. 

Şunlar için geçerlidir: Windows 10 ve üzeri ve iOS, Wi-Fi desteklenir



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

### <a name="windows-10-and-later-kiosk-profile-improvements-in-the-azure-portal----2748224-eeready---"></a>Azure portalında Windows 10 ve üzeri Bilgi Noktası geliştirmeleri <!-- 2748224 eeready -->
Windows 10 Bilgi Noktası cihaz yapılandırma profili (**Cihaz yapılandırması** > **Profiller** > **Profil oluştur** > **Windows 10 ve üzeri** platform için > **Bilgi noktası önizlemesi** profil türü için) geliştirilecek: 
- Şu anda aynı cihazda birden fazla bilgi noktası profili oluşturabiliyorsunuz. Bu güncelleştirme ile Intune, cihaz başına yalnızca bir bilgi noktası profilini destekleyecek. Tek bir cihazda birden fazla bilgi noktası profiline ihtiyacınız varsa bir Özel URI kullanabilirsiniz.
-**Çoklu uygulama bilgi noktası** profilinde, uygulama kılavuzundaki **Başlangıç menüsü düzeni** için uygulama kutucuğu boyutunu ve sırasını seçebilirsiniz. Daha fazla özelleştirme isterseniz bir XML dosyasını karşıya yükleyebilirsiniz.
- Bilgi Noktası Tarayıcısı ayarları, **Bilgi Noktası** ayarlarına taşınıyor. Şu anda **Bilgi Noktası web tarayıcısı** ayarlarının Azure portalında kendi kategorisi var.
Şunlar için geçerlidir: Windows 10 ve üzeri

<!-- 1807 start -->

### <a name="improved-company-portal-app-experience-for-device-enrollment-manager-users----675800---"></a>Cihaz kayıt yöneticisi kullanıcıları için geliştirilmiş Şirket Portalı uygulama deneyimi <!-- 675800 -->
Bir cihaz kayıt yöneticisi (DEM) Windows için Şirket Portalı uygulamasında oturum açtığında, uygulama yalnızca yöneticinin geçerli, çalışan cihazını listeleyecek. Bu yenilik, uygulama DEM tarafından kaydedilen tüm cihazlara yüklenmeye çalıştığında yaşanan zaman aşımı sorunlarını azaltacak.  

### <a name="check-for-configuration-manager-compliance----2192052---"></a>Configuration Manager uyumluluğunu denetleme <!-- 2192052 -->
Gelecekte yapılacak bir güncelleştirmede yeni bir System Center Configuration Manager uyumluluk ayarı olacak (**Cihaz uyumluluğu** > **İlkeler** > **İlke oluştur** > **Windows 10**). Configuration Manager, Intune uyumluluğuna sinyal gönderir. Intune ayarını kullanarak tüm Configuration Manager sinyallerinin “uyumlu” olarak döndürülmesini gerektirebilirsiniz.

Örneğin, tüm yazılım güncelleştirmelerinin cihazlarda yüklü olmasını gerektirirsiniz. Configuration Manager’da bu gereksinim, “Yüklü” durumundadır. Cihazdaki herhangi bir program bilinmeyen bir durumdaysa cihaz, Intune ile uyumlu olmayacaktır.

Windows 10 ve üzeri için geçerlidir

### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low----2237572---"></a>Süresi dolan VPP belirteci veya yetersiz Şirket portalı lisansı uyarıları <!-- 2237572 -->
DEP kaydı sırasında Şirket Portalı’nın ön sağlamasını yapmak için Volume Purchase Program (VPP) kullanıyorsanız Intune, VPP belirtecinin süresi dolmak üzereyken ve Şirket Portalı lisansları yetersiz sayıdayken sizi uyarır.

### <a name="additional-security-settings-for-windows-installer----2282430---"></a>Windows Installer için ek güvenlik ayarları <!-- 2282430 -->
Kullanıcıların uygulama yüklemelerini denetlemesine olanak sağlayabileceksiniz. Etkinleştirilirse, aksi takdirde güvenlik ihlali nedeniyle durdurulabilecek olan yüklemelerin devam etmesine izin verilebilir. Windows Installer’ı sistemde herhangi bir program yüklerken yükseltilmiş izinler kullanmaya yönlendirebileceksiniz. Buna ek olarak, Windows Bilgi Koruması (WIP) öğelerinin dizine alınmasını ve bunlar hakkındaki meta verilerin şifrelenmemiş bir konumda depolanmasını etkinleştirebileceksiniz. İlke devre dışı bırakıldığında, WIP korumalı öğelerin dizini oluşturulmayacak ve Cortana veya dosya gezgini sonuçlarında görünmeyecek. Bu seçeneklerin işlevselliği varsayılan olarak devre dışı bırakılacak. 

<!-- 1806 start -->

### <a name="3rd-party-keyboards-can-be-blocked-by-app-settings-on-ios----1248481---"></a>iOS'ta üçüncü taraf klavyeler APP ayarlarıyla engellenebilir <!-- 1248481 -->
iOS cihazlarında, Intune yöneticileri ilke korumalı uygulamalarda kuruluş verilerine erişilirken üçüncü taraf klavyelerin kullanımını engelleyebilecek. Uygulama Koruma İlkesi (APP) üçüncü taraf klavyelerini engelleyecek şekilde ayarlandığında, cihaz kullanıcısı üçüncü taraf klavyesini kullanarak şirket verileriyle ilk kez etkileşim kurarken bir ileti alacak. Yerel klavye dışındaki tüm seçenekler engellenecek ve cihaz kullanıcıları bunları görmeyecek. Cihaz kullanıcıları iletişim kutusu iletisini tek bir kez görür. 

### <a name="office-365-pro-plus-language-packs----1833450---"></a>Office 365 Pro Plus dil paketleri <!-- 1833450 -->
Intune yöneticisi olarak, Intune aracılığıyla yönetilen Office 365 Pro Plus uygulamaları için ek dillerin dağıtımını yapabileceksiniz. Kullanılabilir diller listesi, dil paketinin **Tür** bilgisini içerir (çekirdek, kısmı ve yazım denetleme). Azure portalında **Microsoft Intune** > **Mobil uygulamalar** > **Uygulamalar** > **Ekle**'yi seçin. **Uygulama ekle** dikey penceresindeki **Uygulama türü** listesinde **Office 365 Paketi** altından **Windows 10**'u seçin. **Uygulama Paketi Ayarları** dikey penceresinde **Diller**'i seçin.

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



