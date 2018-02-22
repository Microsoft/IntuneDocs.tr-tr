---
title: "Erken sürüm"
description: 
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/24/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ed427382b94f591559a2264f40455ab5254daadb
ms.sourcegitcommit: a6fd6b3df8e96673bc2ea48a2b9bda0cf0a875ae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/03/2018
---
# <a name="the-early-edition-for-microsoft-intune---february-2018"></a>Microsoft Intune için erken sürüm - Şubat 2018

**Erken sürüm**, Microsoft Intune'un gelecek sürümlerinde kullanıma sunulacak yeni özelliklerin bir listesini sunar. Bu bilgiler kısıtlı bir kapsamla verilmektedir ve değiştirilebilir. Bu bilgileri şirket dışından kimselerle paylaşmayın. Burada listelenen özelliklerden bazılarının son tarihe yetişememe riski vardır ve gelecek sürüme ertelenebilir. Diğer özellikler, müşterinin kullanımına hazır olduğundan emin olmak için pilot (sürüyor) aşamasında test edilmektedir. Herhangi bir sorunuz veya endişeniz varsa lütfen Microsoft ürün grubu ilgili kişisiyle bağlantı kurun.

Bu sayfa düzenli aralıklarla güncelleştirilir. Ek güncelleştirmeleri daha sonra denetleyin.

> [!Note]
>Intune için aşağıdaki değişiklikler geliştirilme aşamasındadır. Yeni karma özellikler hakkında daha fazla bilgi için [Karma Yenilikler](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) sayfasını gözden geçirin.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->

## <a name="intune-in-the-azure-portal"></a>Azure portalında Intune


<!-- 1802 start -->

### <a name="prevent-end-users-from-adding-or-removing-accounts-in-the-work-profile----1728700---"></a>Son kullanıcıların iş profiline hesap eklemesini veya profilden hesap çıkarmasını önleme <!-- 1728700 -->    
Bir Android for Work profiline Gmail uygulamasını dağıttığınızda, Android for Work cihaz kısıtlama profilindeki **Hesap ekle veya kaldır** ayarını kullanarak son kullanıcıların iş profilinde hesap ekleme veya kaldırma işlemleri yapmasını önleyebilirsiniz.

### <a name="app-protection-policies-----679615---"></a>Uygulama koruma ilkeleri  <!-- 679615 -->
Intune Uygulama Koruma İlkeleri, tüm kiracıdaki tüm kullanıcılar için hızlı bir şekilde koruma sağlamaya yönelik genel ve varsayılan ilkeler oluşturma olanağı sunar.

### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685---"></a>Birden çok Apple DEP / Apple School Manager hesabı için Intune desteği <!-- 747685 -->

Intune, sayıları 100'e varan farklı Apple Aygıt Kayıt Programı (DEP) veya Apple School Manager hesabından cihazların kaydını destekleyecek. Karşıya yüklenen her belirteç kayıt profilleri ve cihazlar için ayrı olarak yönetilebilir. Karşıya yüklenen DEP/School Manager belirteçlerinin her biri için farklı bir kayıt profili otomatik olarak atanabilir. Birden çok School Manager belirteci karşıya yüklenirse, Microsoft School Data Sync ile bir kerede tek bir belirteç paylaşılabilir.

Geçişten sonra, Graph üzerinden Apple DEP veya ASM yönetimi için beta Graph API'leri ve yayımlanan betikler artık çalışmayacak. Yeni beta Graph API'leri geliştirme aşamasındadır ve geçiş sonrasında yayınlanacaktır.

### <a name="windows-defender-health-status-and-threat-status-reports---854704---"></a>Windows Defender sistem durumu ve tehdit durumu raporları <!--854704 -->

Windows Defender’ın sistem durumunu anlamak, Windows bilgisayarları yönetmenin anahtarıdır.  Intune, Windows Defender aracısının sistem durumuna yeni raporlar ve eylemler ekler. Cihaz Uyumluluğu iş yükünde bir durum toplama raporu kullanarak, aşağıdakilerden herhangi birine gereksinim duyan cihazları görebilirsiniz:

- imza güncelleştirmesi
- yeniden başlatma
- el ile müdahale
- tam tarama
- müdahale gerektiren diğer aracı durumları

Bazı durumlarda, bir imza güncelleştirmesi tetiklemek gibi uzaktan düzeltme eylemleri gerçekleştirilebilir.  Rapor ayrıca, **Temiz** olarak raporlanan kişisel bilgisayar sayısını da belirtir.

Her bir durum kategorisi için ayrıntılı bir rapor ile ilgilenilmesi gereken bireysel bilgisayarlar veya **Temiz** olarak raporlananlar listelenir.

### <a name="protocol-exceptions-for-applications---1035509-eeready--"></a>Uygulamalar için protokol özel durumları <!--1035509 eeready-->

Belirli yönetilmeyen uygulamaları açmak için Intune Mobil Uygulama Yönetimi (MAM) veri aktarımı ilkesinde özel durumlar oluşturabileceksiniz. Bu tür uygulamaların BT tarafından güvenilen uygulamalar olması gerekir. Oluşturduğunuz özel durumlar dışında, veri aktarımı ilkeniz **yalnızca yönetilen uygulamalar** olarak ayarlı olduğu sürece veri aktarımınız Intune tarafından yönetilen uygulamalarla kısıtlı kalacaktır. Protokoller (iOS) veya paketler (Android) kullanarak kısıtlamalar oluşturabilirsiniz.

Örneğin MAM veri aktarımı ilkesine Webex paketini özel durum olarak ekleyebilirsiniz. Böylece, yönetilen bir Outlook e-posta iletisindeki Webex bağlantıları, doğrudan Webex uygulamasında açılacaktır. Veri aktarımı, diğer yönetilmeyen uygulamalarda kısıtlı olmaya devam edecektir.

### <a name="customize-your-company-portal-themes-with-hex-codes---1049561-eeready--"></a>Şirket Portalı temalarınızı onaltılık kodlarla özelleştirme <!--1049561 eeready-->

Onaltılık kodlar kullanarak Şirket Portalı uygulamalarında tema rengini özelleştirebileceksiniz. Onaltılık kodunuzu girdiğinizde Intune, [WCAG 2.0 standartlarına](http://www.w3.org/TR/WCAG20) göre metin rengi ile arka plan rengi arasında en yüksek düzeyde kontrast sağlayan metin rengini belirler. **Mobil uygulamalar** > **Şirket Portalı**’nda metin renginin ve bu renk ile şirket logonuzun önizlemesini görüntüleyebilirsiniz. 

### <a name="select-device-categories-by-using-the-access-work-or-school-settings----1058963---"></a>İş Yeri veya Okula Erişme ayarlarını kullanarak cihaz kategorilerini seçme <!-- 1058963 --> 
[Cihaz grubu eşlemeyi](https://docs.microsoft.com/intune/device-group-mapping) etkinleştirdiyseniz, Windows 10'daki kullanıcılardan **Ayarlar** > **Hesaplar** > **İş yeri veya okula eriş** altındaki **Bağlan** düğmesi aracılığıyla veya ilk kez çalıştırma deneyimi sırasında kaydolduktan sona cihaz kategorisini seçmeleri istenecek.

### <a name="new-windows-defender-credential-guard-settings-added-to-endpoint-protection-settings---1102252---"></a>Endpoint Protection ayarlarına yeni Windows Defender Credential Guard ayarları eklendi <!--1102252 --> 

**Cihaz yapılandırması** > **Profiller** > **Endpoint protection**’a yeni [Windows Defender Credential Guard](https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard] ayarlar eklenecek. Eklenecek ayarlar aşağıdaki gibidir: 

- Platform Güvenlik Düzeyi: Bir sonraki yeniden başlatmada Platform Güvenlik Düzeyi’nin etkinleştirilip etkinleştirilmeyeceğini belirtin. Sanallaştırma tabanlı güvenlik, Güvenli Önyükleme gerektirir. Sanallaştırma tabanlı güvenlik, isteğe bağlı olarak doğrudan bellek erişimi (DMA) korumaları kullanımıyla etkinleştirilebilir. DMA korumaları, donanım desteği gerektirir ve yalnızca doğru yapılandırılmış cihazlarda etkinleştirilir.
- Sanallaştırma Tabanlı Güvenlik: Bir sonraki yeniden başlatmada sanallaştırma tabanlı güvenliğin etkinleştirilip etkinleştirilmeyeceğini belirtin. 
- Windows Defender Credential Guard: Sanallaştırma tabanlı güvenlik ile Credential Guard’ı etkinleştirerek, Güvenli Önyükleme ile Platform Güvenlik Düzeyi ve Sanallaştırma Tabanlı Güvenlik’in etkin olduğu bir sonraki yeniden başlatmada kimlik bilgilerinin korunmasına yardımcı olun. Kullanılabilir seçenekler **Devre dışı**, **UEFI kilidi ile etkin**, **Kilit olmadan etkin** ve **Yapılandırılmadı** şeklindedir. 
  - “Devre dışı” seçeneği, “Kilit olmadan etkin” seçeneğiyle açılmış olan Credential Guard’ı uzaktan kapatır.

  - “UEFI kilidi ile etkin” seçeneği, Credential Guard’ın kayıt defteri anahtarı ile veya Grup İlkesi kullanılarak devre dışı bırakılamamasını sağlar. Bu ayarı kullandıktan sonra Credential Guard’ı devre dışı bırakmak için, UEFI’de belirtilen yapılandırmayı kaldırmak üzere Grup İlkesini “Devre Dışı” olarak ayarlamanız ve kullanıcısı fiziksel olarak mevcut olan her bir bilgisayardan güvenlik işlevselliğini kaldırmanız gerekir. UEFI yapılandırması devam ettiği sürece, Credential Guard etkindir.

  - “Kilit olmadan etkin” seçeneği, Credential Guard’ın Grup İlkesi kullanılarak uzaktan devre dışı bırakılmasına imkan verir. Bu ayarı kullanan cihazların en az Windows 10 (Sürüm 1511) çalıştırıyor olması gerekir.

  - “Yapılandırılmadı” seçeneği, ilke ayarını tanımlanmamış halde bırakır. Grup İlkesi, ilke ayarını kayıt defterine yazmaz ve bu nedenle bilgisayarlar ve kullanıcılar üzerinde hiçbir etkisi yoktur. Kayıt defterinde geçerli bir ayar varsa bu ayar değiştirilmeyecektir.

### <a name="synchronize-and-deploy-sparsely-bundled-windows-store-for-business-apps---1222672---"></a>Seyrek paketlenmiş İş İçin Microsoft Store uygulamalarını eşitleme ve dağıtma <!--1222672 -->
İş İçin Microsoft Store’dan satın alınan çevrimdışı uygulamalar, Intune portalına eşitlenecek. Daha sonra bu uygulamaları cihaz gruplarına veya kullanıcı gruplarına dağıtabilirsiniz. Çevrimdışı uygulamalar, mağaza tarafından değil, Intune tarafından yüklenir.

### <a name="reset-passwords-for-android-o-devices----1238299---"></a>Android O cihazlar için parola sıfırlama <!-- 1238299 -->
Kayıtlı Android O cihazlar için parolaları sıfırlayabileceksiniz. Bir Android O cihaza “Parola sıfırla” isteği gönderdiğinizde cihaz, geçerli kullanıcıya yeni bir cihaz kilidi açma parolası veya yönetilen profil sınaması ayarlar. Parola veya sınama, kullanıcının cihazın profil sahibi veya cihaz sahibi olmasına bağlıdır ve hemen devreye girer.

### <a name="local-device-security-option-settings----1251887---"></a>Yerel cihaz güvenliği seçeneği ayarları <!-- 1251887 -->
Yeni Yerel Cihaz Güvenlik Seçeneği ayarlarını kullanarak Windows 10 cihazlarda güvenlik ayarlarını etkinleştirebileceksiniz. Bu ayarları, bir Windows 10 cihaz yapılandırma ilkesi oluşturduğunuzda Endpoint Protection kategorisinde bulabilirsiniz.

### <a name="new-printer-settings-for-education-profiles----1308900---"></a>Eğitim profilleri için yeni yazıcı ayarları <!-- 1308900 -->

Eğitim profilleri için yeni ayarlar, **Yazıcılar** kategori: **Yazıcılar**, **Varsayılan yazıcı**, **Yeni yazıcı ekle** altında kullanılabilir olacak. 

### <a name="new-privacy-settings-for-device-restrictions---1308926---"></a>Cihaz kısıtlamaları için yeni gizlilik ayarları <!--1308926 -->

Cihazlar için iki yeni gizlilik ayarı kullanılabilir olacak:

- **Kullanıcı etkinliklerini yayımla**: Bunu **Engelle** şeklinde ayarlayarak, görev değiştiricide paylaşılan deneyimleri ve yakın zamanda kullanılan kaynakların bulunmasını önleyin.

- **Yalnızca yerel etkinlikler**: Bunu **Engelle** şeklinde ayarlayarak, görev değiştiricide yalnızca yerel etkinliklere bağlı olan paylaşılan deneyimleri ve yakın zamanda kullanılan kaynakların bulunmasını önleyin.

### <a name="macos-company-portal-support-for-enrollments-that-use-the-device-enrollment-manager----1352411---"></a>macOS Aygıt Kayıt Yöneticisi’ni kullanan kayıtlar için Şirket Portalı desteği <!-- 1352411 -->

macOS Şirket Portalı’na kaydolurken kullanıcılar, Aygıt Kayıt Yöneticisi’ni kullanabilecekler.

#### <a name="new-settings-for-the-edge-browser---1469166---"></a>Edge tarayıcısı için yeni ayarlar <!--1469166 -->

Edge tarayıcısı kullanan cihazlar için iki yeni ayar kullanılabilir olacak: **Sık kullanılanlar dosyasının yolu** ve **Sık kullanılanlarda değişiklikler**. 

### <a name="windows-information-protection-wip-encrypted-data-in-windows-search-results----1469193---"></a>Windows arama sonuçlarında Windows Bilgi Koruması (WIP) ile şifrelenmiş veriler <!-- 1469193 -->

Windows Bilgi Koruması (WIP) ilkesindeki yeni bir ayar, Windows arama sonuçlarına WIP ile şifrelenmiş verilerin dahil edilip edilmeyeceğini denetlemenize olanak tanıyacak.

### <a name="line-of-business-lob-app-support-for-macos----1473977---"></a>macOS için iş kolu (LOB) uygulamaları desteği <!-- 1473977 -->
Intune, macOS LOB uygulamalarını yükleme olanağı sağlayacak. LOB uygulamaları, yükleme dosyasını sağladığınız ve uygulamayı cihaza yüklemek için Intune’u kullandığınız uygulamalardır. macOS LOB desteğinin bir parçası olarak, macOS iş kolu (LOB) uygulamalarını ön işlemden geçirmek üzere macOS için Microsoft Intune Uygulama Sarmalama Aracı’nı kullanmanız gerekir.

### <a name="configure-resource-account-settings-for-surface-hubs----1475674---"></a>Surface Hub’lar için kaynak hesap ayarlarını yapılandırma <!-- 1475674 -->

Surface Hub’lar için kaynak hesap ayarlarını uzaktan yapılandırabileceksiniz.

Kaynak hesabı, Skype/Exchange ile kimlik doğrulaması yapmak için bir Surface Hub tarafından kullanılır; böylece bir toplantıya katılabilir. Surface Hub’ın toplantıdaki konferans odası olarak görünmesi için eşsiz bir kaynak hesabı oluşturmak isteyebilirsiniz. Örneğin, **Konferans Salonu B41/6233** kaynak hesabı.

> [!NOTE]
> - Alanları boş bırakırsanız cihazın önceden yapılandırılmış özniteliklerini geçersiz kılarsınız.
>
> - Kaynak Hesap özellikleri, Surface Hub’da dinamik olarak değişebilir. Örneğin, parola dönüşü açıksa. Bu nedenle, Azure konsolundaki değerlerin cihazdaki gerçekliği yansıtması biraz zaman alabilir. 
>
>   Surface Hub’daki geçerli yapılandırmaları anlamak için Kaynak Hesap bilgileri donanım envanterine (7 günlük aralığı vardır) veya salt okunur özelliklere dahil edilebilir. Uzak eylem gerçekleştikten sonra doğruluğu artırmak için, Surface Hub hesabını/parametrelerini güncelleştirmek üzere eylemi çalıştırdıktan hemen sonra parametrelerin durumunu alabilirsiniz.

### <a name="ios-app-provisioning-configuration----1581650---"></a>iOS uygulama sağlama yapılandırması <!-- 1581650 -->
Güvenlik gruplarını dahil ederek veya dışlayarak, uygulamalarınızın süresinin dolmasını önlemek için iOS uygulama sağlama profilleri atayabileceksiniz.

### <a name="new-windows-defender-exploit-guard-settings----631893---"></a>Yeni Windows Defender Exploit Guard ayarları <!-- 631893 -->

Altı yeni **Saldırı Yüzeyi Azaltma** ayarı ve genişletilmiş **Denetimli klasör erişimi: Klasör koruması** yetenekleri kullanılabilir olacak. Bu ayarlar şurada bulunabilir: Cihaz yapılandırması\Profiller\
Profil oluştur\Endpoint protection\Windows Defender Exploit Guard.

#### <a name="attack-surface-reduction"></a>Saldırı Yüzeyini Azaltma

|Ayar adı  |Ayar seçenekleri  |Description  |
|---------|---------|---------|
|Gelişmiş fidye yazılımı koruması|Etkin, Denetle, Yapılandırılmadı|Agresif fidye yazılımı koruması kullanır.|
|Windows yerel güvenlik yetkilisi alt sisteminden kimlik bilgisi çalma eylemlerine bayrak ekleme|Etkin, Denetle, Yapılandırılmadı|Windows yerel güvenlik yetkilisi alt sisteminden kimlik bilgisi çalma eylemlerine bayrak ekler (lsass.exe).|
|PSExec ve WMI komutlarından işlem oluşturma|Engelle, Denetle, Yapılandırılmadı|PSExec ve WMI komutlarından kaynaklanan işlem oluşturmalarını engeller.|
|USB’den çalışan güvenilmeyen ve imzasız işlemler|Engelle, Denetle, Yapılandırılmadı|USB’den çalışan güvenilmeyen ve imzasız işlemleri engeller.|
|Bir yaygınlık, yaş veya güvenilenler listesi kriterine uymayan yürütülebilir dosyalar|Engelle, Denetle, Yapılandırılmadı|Bir yaygınlık, yaş veya güvenilenler listesi kriterine uymadıkları sürece yürütülebilir dosyaları engeller.|

#### <a name="controlled-folder-access"></a>Denetlenen klasör erişimi

|Ayar adı  |Ayar seçenekleri  |Description  |
|---------|---------|---------|
|Klasör koruması (zaten uygulanmış)|Yapılandırılmamış, Etkinleştir, Yalnızca denetle (zaten uygulanmış)<br><br> **Yeni**<br>Disk değişikliğini engelle, Disk değişikliğini denetle|
Dosya ve klasörleri kötü amaçlı uygulamaların yetkisiz değişikliklerinden korur.<br><br>**Etkinleştir**: Güvenilmeyen uygulamaların korumalı klasörlerdeki dosyaları değiştirmesini veya silmesini ve disk kesimlerine yazmasını engeller.<br><br>
**Yalnızca disk değişikliğini engelle**:<br>Güvenilmeyen uygulamaların, disk kesimlerine yazmasını engeller. Güvenilmeyen uygulamalar hala korumalı klasörlerdeki dosyaları değiştirebilir veya silebilir.|

### <a name="new-windows-defender-application-guard-settings----1631890---"></a>Yeni Windows Defender Application Guard ayarları <!-- 1631890 -->

- **Grafik hızlandırmayı etkinleştirme**

Yöneticiler, Windows Defender Application Guard için bir sanal grafik işlemcisi etkinleştirebilecek. Bu ayar, CPU’nun vGPU’ya işlenen grafikleri boşaltmasına olanak sağlar. Bu, yoğun grafikli sitelerde çalışırken veya kapsayıcı dahilinde video izlerken performansı iyileştirebilir.

- **SaveFilestoHost**

Yöneticiler, dosyaların kapsayıcıda çalışan Microsoft Edge’den konak dosya sistemine geçmesine izin verebilecek. Bunu açmak, kullanıcıların kapsayıcıda çalışan Microsoft Edge’den konak dosya sistemine dosya indirmesine imkan sağlayacaktır.

### <a name="see-enrollment-restrictions-per-user----1634444---"></a>Kullanıcı başına kayıt kısıtlamalarına bakın <!-- 1634444 -->
Sorun giderme dikey penceresinde, her bir kullanıcı için etkin durumdaki kayıt kısıtlamalarını görebileceksiniz.

### <a name="configuring-a-self-updating-mobile-msi-app----1740840---"></a>Kendi kendini güncelleştiren bir MSI uygulaması yapılandırma <!-- 1740840 -->
Sürüm denetim işlemini yok saymak için bilinen bir kendi kendini güncelleştiren MSI uygulaması yapılandırabileceksiniz. Bu yetenek, yarış durumuna girmeyi önlemek açısından kullanışlıdır. Bu durum örneğin uygulama, uygulama geliştirici tarafından otomatik olarak güncelleştirilirken diğer yandan Intune tarafından da güncelleştirildiği durumlarda ortaya çıkabilir. Her iki taraf da Windows istemcisinde uygulamanın bir sürümünü zorlamaya çalışabilir, böylece bir çakışma ortaya çıkabilir.

### <a name="additions-to-system-security-settings-for-windows-10-and-later-compliance-policies---1704133---"></a>Windows 10 ve üzeri uyumluluk ilkeleri için Sistem Güvenliği ayarlarına eklemeler <!--1704133 -->

Güvenlik Duvarı ve Windows Defender Virüsten Koruma gerektirme dahil olmak üzere Windows 10 uyumluluk ayarlarına bazı eklemeler gelecek.

### <a name="including-and-excluding-app-assignment-based-on-groups-for-android-enterprise----1813081---"></a>Android Enterprise için gruplar temelinde uygulama atamasını dahil etme ve hariç tutma <!-- 1813081 -->
Android Enterprise (eski adıyla Android for Work), uygulama ataması sırasında atama türünü seçtikten sonra dışlama işlevini destekleyecek.


### <a name="related-sets-of-app-licenses-supported-in-intune----1864117---"></a>Intune’da desteklenen ilgili uygulama lisans kümeleri <!-- 1864117 -->
Azure portalında Intune, ilgili uygulama lisans kümelerini kullanıcı arabiriminde tek bir uygulama öğesi olarak destekleyecek. Buna ek olarak, İş İçin Microsoft Store’dan eşitlenmiş Çevrimdışı Lisanslanan uygulamalar da tek bir uygulama girdisi olarak birleştirilecek ve ayrı ayrı paketlerdeki dağıtım ayrıntıları bu tek girdiye taşınacak. Azure portalında ilgili uygulama lisans kümelerini görüntülemek için **Mobil uygulamalar** dikey penceresinden **Uygulama lisansları**’nı seçin.

<!-- the following are present prior to 1802 -->

### <a name="new-option-for-user-authentication-for-apple-bulk-enrollment----747625---"></a>Apple toplu kaydında kullanıcı kimlik doğrulaması için yeni seçenek <!-- 747625 -->
Intune, aşağıdaki kayıt yöntemlerinde size Şirket Portalı uygulamasını kullanarak cihazların kimliğini doğrulama seçeneği sağlayacak:

- Apple Cihaz Kaydı Programı
- Apple School Manager
- Apple Configurator Kaydı

Şirket portalı seçeneği kullanılırken, bu kayıt yöntemlerini engellemeden Azure Active Directory çok faktörlü kimlik doğrulaması zorunlu tutulabilir.

Şirket portalı seçeneği kullanılırken, Intune kullanıcı benzeşimi kaydı için iOS Kurulum Yardımcısı'nda kullanıcı kimlik doğrulamasını atlar. Bu, cihazın başlangıçta kullanıcısız bir cihaz olarak kaydedildiği ve dolayısıyla kullanıcı gruplarının yapılandırmaları veya ilkelerini almayacağı anlamına gelir. Yalnızca cihaz gruplarının yapılandırmalarını ve ilkelerini alacak. Bununla birlikte, Intune Şirket Portalı uygulamasını Cihaz üzerine otomatik olarak yükleyecek. Şirket Portalı uygulamasını başlatan ve bu uygulamada oturum açan ilk kullanıcı, Intune'da cihazla ilişkilendirilecek. Bu noktada kullanıcı, kendi kullanıcı gruplarının yapılandırmalarını ve ilkelerini alacak. Yeniden kayıt yapılmadan kullanıcı ilişkisi değiştirilemez.

### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685---"></a>Birden çok Apple DEP / Apple School Manager hesabı için Intune desteği <!-- 747685 -->
Intune, sayıları 100'e varan farklı Apple Aygıt Kayıt Programı (DEP) veya Apple School Manager hesabından cihazların kaydını destekleyecek. Karşıya yüklenen her belirteç kayıt profilleri ve cihazlar için ayrı olarak yönetilebilir. Karşıya yüklenen DEP/School Manager belirteçlerinin her biri için farklı bir kayıt profili otomatik olarak atanabilir. Birden çok School Manager belirteci karşıya yüklenirse, Microsoft School Data Sync ile bir kerede tek bir belirteç paylaşılabilir.

Geçişten sonra, Graph üzerinden Apple DEP veya ASM yönetimi için beta Graph API'leri ve yayımlanan betikler artık çalışmayacak. Yeni beta Graph API'leri geliştirme aşamasındadır ve geçiş sonrasında yayınlanacaktır.

### <a name="select-device-categories-by-using-the-access-work-or-school-settings----1058963---"></a>İş Yeri veya Okula Erişme ayarlarını kullanarak cihaz kategorilerini seçme <!-- 1058963 -->
[Cihaz grubu eşlemeyi](https://docs.microsoft.com/intune/device-group-mapping) etkinleştirdiyseniz, Windows 10'daki kullanıcılardan **Ayarlar** > **Hesaplar** > **İş yeri veya okula eriş** altındaki **Bağlan** düğmesi aracılığıyla veya ilk kez çalıştırma deneyimi sırasında kaydolduktan sona cihaz kategorisini seçmeleri istenecek.

### <a name="targeting-compliance-policies-to-devices-in-device-groups---1307012---"></a>Uyumluluk ilkelerinde cihaz gruplarındaki cihazları hedefleme <!--1307012 -->

Uyumluluk ilkelerinde kullanıcı gruplarındaki kullanıcıları hedefleyebileceksiniz. Uyumluluk ilkelerinde cihaz gruplarındaki cihazları hedefleyebileceksiniz.

### <a name="windows-information-protection-wip-encrypted-data-in-windows-search-results----1469193---"></a>Windows arama sonuçlarında Windows Bilgi Koruması (WIP) ile şifrelenmiş veriler <!-- 1469193 -->

Windows Bilgi Koruması (WIP) ilkesindeki yeni bir ayar, Windows arama sonuçlarına WIP ile şifrelenmiş verilerin dahil edilip edilmeyeceğini denetlemenize olanak tanıyacak.

### <a name="remote-printing-over-a-secure-network----1709994----"></a>Güvenli bir ağ üzerinden uzaktan yazdırma <!-- 1709994  -->
PrinterOn’un kablosuz mobil yazdırma çözümleri kullanıcıların güvenli bir ağ üzerinden istedikleri yerde ve istedikleri zaman uzaktan yazdırma işlemi yapmalarını sağlayacak. PrinterOn, hem iOS hem de Android için Intune APP SDK'sıyla tümleştirilecek. Yönetim konsolundaki Intune **Uygulama koruma ilkeleri** dikey penceresi aracılığıyla uygulama koruma ilkelerinde bu uygulamayı hedefleyebileceksiniz. Son kullanıcılar 'PrinterOn for Microsoft' uygulamasını kendi Intune ekosistemlerinde kullanmak üzere Play Store veya iTunes üzerinden indirebilecek.



### <a name="microsoft-graph-api-for-intune---general-availability-----1833289---"></a>Intune için Microsoft Graph API'si - Genel Kullanılabilirlik  <!-- 1833289 -->
Microsoft Graph'te Intune API'leri, Intune hizmetinde yönetim eylemlerini otomatik hale getirmek için verilere ve yöntemlere programlı erişim sağlayacak.  Bu API’lerin **Genel Kullanılabilirlik** aşaması geldiğinde müşteriler, iş ortakları ve geliştiriciler API’lerden yararlanarak Intune’la ilgili olan veya Intune desteği gerektiren şirket içi veya ticari çözümleri ya da Microsoft Graph üzerinden sağlanan diğer Microsoft hizmetlerini tümleştirebilecekler.

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>Uygulama koruma ilkeleri  <!-- 679615 -->
Intune Uygulama Koruma İlkeleri, tüm kiracıdaki tüm kullanıcılar için hızlı bir şekilde koruma sağlamaya yönelik genel ve varsayılan ilkeler oluşturma olanağı sunar.

### <a name="new-ios-device-action------1244701---"></a>Yeni iOS cihaz eylemi  <!-- 1244701 -->
IOS 10.3 denetlenen cihazları kapatabilirsin. Bu eylem, son kullanıcıya herhangi bir uyarı yapılmadan cihazı hemen kapatır. **Cihaz** iş yükünde bir cihaz seçtiğinde, cihaz özelliklerinde **Kapat (yalnızca denetimli)** eylemi bulunabilir.

### <a name="intune-provides-the-account-move-operation-----1573558-1579830---"></a>Intune, Hesap Taşıma işlemi sağlar <!-- 1573558, 1579830 -->
**Hesap Taşıma** bir kiracıyı bir Azure Ölçeği Birimi'nden (ASU) diğerine taşır. **Hesap Taşı**, hem bunu isteyen Intune destek ekibini aradığınızda istemci tarafından başlatılan senaryolar için, hem de Microsoft'un arka uç hizmetinde ayarlamalar yapması gereken Microsoft tarafından yönetilen bir senaryo olarak kullanılabilir. **Hesap Taşıma** sırasında kiracı salt okunur moda (ROM) girer. ROM süresi boyunca kayıt yaptırma, cihazları yeniden adlandırma, uyumluluk durumunu güncelleme gibi servis işlemleri başarısız olur.

Değişiklik, bir uygulama farklı uygulama amaçlarına sahip birden çok gruba atandığında görülen karışıklığı giderir.

Uygulamanızın Kasım hizmet yayınından önce Bilgi Çalışanı Portalı ve Şirket Portalı’nda kullanılabilir olmasını istiyorsanız iki seçeneğiniz bulunur:

1. Grubunuz için **Geçerli değil** atamasını kaldırın.
2. **Gerekli ve Kullanılabilir** amacı atanmamış yeni bir grup oluşturun ve bu grubu **Geçerli değil** olarak atayın.

Daha fazla bilgi için bkz. [Microsoft Intune ile uygulamaları gruplara atama](apps-deploy.md).

> [!Note]
> Yayından sonra Intune klasik konsolunda Mobil Cihaz Yönetimi (MDM) uygulama atamalarını göremeyecek veya düzenleyemeyeceksiniz. Ancak uygulama atamalarınızı gerçekleştirmek için Azure konsolu veya Intune Graph API’yi kullanabilirsiniz.

### <a name="configure-an-ios-app-pin----1586774---"></a>iOS uygulama PIN’i yapılandırma <!-- 1586774 -->
Yakında, hedeflenen iOS uygulamaları için bir PIN’i zorunlu kılmanız mümkün olacaktır. PIN gereksinimini ve sona erme tarihi gün sayısını Azure portalında yapılandırabilirsiniz. Gerektiğinde, kullanıcının bir iOS uygulamasına erişmeden önce yeni bir PIN ayarlaması ve kullanması gerekli olacaktır. Yalnızca Intune Uygulama SDK’sı ile uygulama koruması etkinleştirilmiş iOS uygulamaları bu özelliği destekler.

### <a name="user-experience-update-for-the-company-portal-app-for-ios---1412866--"></a>iOS için Şirket Portalı uygulamasında kullanıcı deneyimi güncelleştirmesi <!--1412866-->

iOS için Şirket Portalı uygulamasına büyük bir kullanıcı deneyimi güncelleştirmesi yayımlayacağız. Bu güncelleştirmede, artırılmış kullanılabilirlik ve erişim ile modern bir görüntü ve his veren baştan aşağı yeni bir görsel tasarım yer alacak. Tüm mevcut iOS Şirket Portalı işlevselliği korunacaktır.

Güncelleştirilmiş iOS için Şirket Portalı uygulamasını kullanıp geri bildirimde bulunmanız için Apple TestFlight programı aracılığıyla uygulamanın yayın öncesi sürümünü sunuyoruz. TestFlight erişimi için https://aka.ms/intune_ios_cp_testflight adresine kaydolun. 

![yeni ios şirket portalı uygulamasının teaser görüntüleri](./media/ios-cp-app-redesign-1801-teaser.png)

<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Azure Active Directory web siteleri, Intune Managed Browser Uygulaması gerektirebilir ve Managed Browser’da (Genel Önizleme) Çoklu Oturum Açma’yı destekler <!-- 710595 -->   
Azure Active Directory (Azure AD) kullanarak, mobil cihazlarda web sitelerine erişimi Intune Managed Browser uygulaması ile kısıtlayabileceksiniz. Web sitesi verileri, Managed Browser’da güvende ve son kullanıcının kişisel verilerinden ayrı bir yerde olacaktır. Managed Browser ayrıca Azure AD ile korunan sitelerde Çoklu Oturum Açma işlevlerini de destekleyecektir. Managed Browser’da oturum açmak veya Intune tarafından yönetilen başka bir uygulamanın bulunduğu bir cihazda Managed Browser’ı kullanmak, kullanıcıların kimlik bilgilerini girmelerine gerek kalmaksızın Managed Browser’ın Azure AD ile korunan sitelere erişmesine olanak tanır. Bu özellik, Outlook Web Access (OWA) ve SharePoint Online’ın yanı sıra Azure Uygulama Proxy’si yoluyla erişilen intranet kaynakları gibi diğer kurumsal sitelerde de geçerlidir.

<!-- the following are present prior to 1709 -->
### <a name="intune-app-protection-and-citrix-mdx-development-tools----709185---"></a>Intune Uygulama Koruması ve Citrix MDX Geliştirme Araçları<!-- 709185 -->
Cihazları ve uygulamaları Citrix XenMobile MDX ve Microsoft Intune bileşimi ile yönetebilirsiniz. Bu, Citrix’in mVPN teknolojisini kullanırken uygulamaları Intune uygulama koruması ilkesiyle yönetmenize olanak sağlar.

iOS ve Android için Citrix MDX mVPN teknolojisiyle tümleştiren, Intune Uygulama Sarmalama Aracı ve Intune Uygulama SDK’sını içeren bir kod deposu bulabilirsiniz.

<!-- the following are present prior to 1711 -->

### <a name="redirecting-macos-users-to-the-new-company-portal-app---1380728--"></a>macOS kullanıcılarını yeni Şirket Portalı uygulamasına yönlendirme <!--1380728-->   
Bir son kullanıcı, macOS cihazını kaydetmek için Şirket Portalı web sitesinde oturum açtığında, işlemi tamamlamak için yeni macOS Şirket Portalı uygulamasını indirmek üzere yönlendirilecektir. Bu durum, OS X El Capitan 10.11 ve üzeri sürümleri kullanan macOS cihazlarda görülür. 

<!-- the following are present prior to 1709 -->

### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a>iOS ve Android için Intune Managed Browser desteği <!-- 1374196 -->
Ekim 2017 itibariyle Android uygulamasındaki Intune Managed Browser uygulaması yalnızca Android 4.4 ve sonraki sürümleri çalıştıran cihazları destekleyecektir. iOS’taki Intune Managed Browser uygulaması yalnızca iOS 9.0 ve sonraki sürümleri çalıştıran cihazları destekleyecektir. Android ve iOS’un daha eski sürümleri Managed Browser'ı kullanmaya devam edebilecek, ancak uygulamanın yeni sürümlerini yükleyemeyecek ve uygulamanın tüm özelliklerine erişemeyecektir. Bu cihazları desteklenen işletim sistemi sürümüne güncelleştirmenizi öneririz.

### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Kullanıcı, izin verilen en yüksek cihaz kaydı sayısına ulaştığında gösterilen hata iletisi iyileştirildi <!-- 1270370 -->
Genel bir hata iletisi yerine, Android cihazı olan son kullanıcılar kolay, işlem yapılabilir bir hata iletisi görür: “BT yöneticiniz tarafından izin verilen en yüksek cihaz kaydı sayısına ulaştınız. Lütfen kayıtlı bir cihazı kaldırın veya BT yöneticinizden yardım alın.”



## <a name="notices"></a>Bildirimler

Şu anda etkin bildirim yok.



### <a name="see-also"></a>Ayrıca bkz:
Son geliştirmelere ilişkin ayrıntılar için bkz. [Microsoft Intune’daki Yenilikler](whats-new.md).


