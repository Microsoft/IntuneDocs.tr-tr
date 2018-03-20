---
title: "Erken sürüm"
description: 
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9a2c104200518af31fd05e6b8abe853377767aa9
ms.sourcegitcommit: 9cf05d3cb8099e4a238dae9b561920801ad5cdc6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/09/2018
---
# <a name="the-early-edition-for-microsoft-intune---march-2018"></a>Microsoft Intune için erken sürüm - Mart 2018

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

<!-- 1803 start -->

#### <a name="multiple-exchange-connector-support----2070451---"></a>Birden çok Exchange Connector desteği <!-- 2070451 -->

Artık kiracı başına tek bir Microsoft Intune Exchange Connector’la sınırlı değilsiniz. Intune, birden çok Exchange Connector’u destekleyeceği için Intune koşullu erişimini birden çok şirket içi Exchange kuruluşunda ayarlayabilirsiniz.

Intune şirket içi Exchange bağlayıcısıyla, cihazın Intune'a kayıtlı olup olmadığına ve Intune cihaz uyumluluk ilkelerine uyup uymadığına bağlı olarak şirket içi Exchange posta kutularınıza cihaz erişimini ayarlayabilirsiniz. Bağlayıcıyı ayarlamak için, Intune şirket içi Exchange bağlayıcısını Azure portalından indirir ve Exchange kuruluşunuzdaki bir sunucuya yüklersiniz. Microsoft Intune panosunda **Şirket içi erişim**'i seçin ve ardından **Kurulum**'un altında **Exchange ActiveSync bağlayıcısı**'nı seçin. Exchange şirket içi bağlayıcısını indirin ve Exchange kuruluşunuzdaki bir sunucuya yükleyin. Artık kiracı başına tek Exchange bağlayıcısıyla sınırlı olmadığınıza göre, başka Exchange kuruluşlarınız varsa her ek Exchange kuruluşu için aynı süreci izleyip bağlayıcı indirebilir ve yükleyebilirsiniz.

### <a name="support-coming-for-new-cisco-anyconnect-client-for-ios----1333708---"></a>iOS için yeni Cisco AnyConnect istemcisi desteği geliyor <!-- 1333708 -->

iOS için Cisco AnyConnect'e yönelik oluşturulan yeni VPN profilleri Cisco AnyConnect 4.0.7x ve üstüyle çalışacaktır. Mevcut iOS Cisco AnyConnect VPN profilleri **Cisco Eski AnyConnect** olarak etiketlenecek ve bugün olduğu gibi Cisco AnyConnect 4.0.5x ile çalışmaya devam edecektir.

> [!NOTE]
> Bu değişiklik yalnızca iOS'ye yöneliktir; Android, Android for Work ve macOS için yine tek Cisco AnyConnect seçeneği olacaktır. 

#### <a name="more-information"></a>Daha fazla bilgi

Yeni uygulamayı desteklemek için yeni bir iOS Cisco AnyConnect VPN profili oluşturmalısınız çünkü yeni Cisco AnyConnect uygulaması ve Cisco Eski AnyConnect uygulaması ayrı uygulamalardır. Ortamınızda AnyConnect istemcisini yönetiyorsanız, yeni Cisco AnyConnect uygulamasını da dağıtmanız gerekir. Ayrıca yükseltmeyi tamamlamak için, Cisco Eski AnyConnect VPN profilini silmeli ve Cisco Eski AnyConnect uygulamasını kaldırmalısınız. 

İlk sürümde yeni AnyConnect istemcisi için ağ erişim denetimi (NAC) tümleştirmesi çalışmaz. Gelecek Intune sürümlerinden birinde NAC tümleştirmesi sağlamak için Cisco'yla çalışmaları sürdürüyoruz.

### <a name="enhanced-jailbreak-detection----846515---"></a>Gelişmiş jailbreak algılama <!-- 846515 -->

Gelişmiş jailbreak algılama, Intune'un jailbreak uygulanmış cihazları değerlendirme yöntemini geliştirecek yeni bir uyumluluk ayarıdır. Ayar cihazın Intune'a daha sık iade edilmesine neden olur; bu da cihazın konum hizmetlerini kullanır ve pil kullanımını etkiler.

### <a name="ability-to-deploy-required-line-of-business-lob-apps-to-all-users-on-windows-10-desktop-devices----1627835-rs4---"></a>Gerekli iş kolu (LOB) uygulamalarını Windows 10 Masaüstü cihazlarında Tüm Kullanıcılara dağıtabilme <!-- 1627835 RS4 -->
Müşteriler gerekli iş kolu Windows 10 uygulamalarını cihaz bağlamlarına yüklemek üzere dağıtabilecek. Böylelikle bu uygulamalar cihazdaki tüm kullanıcılara sağlanabilir. Bu yalnızca Windows 10 Masaüstü cihazları için geçerlidir. 

### <a name="expiring-line-of-business-lob-apps-for-microsoft-intune----748789---"></a>Microsoft Intune için süresi dolan iş kolu (LOB) uygulamaları <!-- 748789 -->
Azure portalında, Intune süresi dolmak üzere olan iş kolu uygulamaları konusunda sizi uyaracaktır. İş kolu uygulamasının yeni sürümü karşıya yüklenince, Intune süre sonu bildirimini uygulama listesinden kaldırır.

### <a name="company-portal-enrollment-improved----1874230--"></a>Şirket Portalı kaydı geliştirildi <!-- 1874230-->
Windows 10 derleme 1703'te ve üstünde Şirket Portalı'nı kullanarak cihaz kaydı yapan kullanıcılar, uygulamadan çıkmadan kaydın ilk adımını tamamlayabilecekler.

### <a name="new-management-name-column----1333586---"></a>Yeni Yönetim adı sütunu <!-- 1333586 -->
Cihazlar dikey penceresine **Yönetim adı** adlı yeni bir sütun eklenecektir. Bu, aşağıdaki formül temelinde her cihaza atanan, otomatik olarak oluşturulmuş ve düzenlenemez bir addır: 
- Tüm cihazlar için varsayılan ad: <username>_<devicetype>_<enrollmenttimestamp>
- Toplu eklenen cihazlar: <PaketKimliği/ProfilKimliği>_<DeviceType>_<EnrollmentTime> 
 
Bu, cihazlar dikey penceresinde isteğe bağlı bir sütundur. Varsayılan olarak sağlanmaz ve bu sütuna yalnızca sütun seçici üzerinden erişebilirsiniz. Cihaz adı bu yeni sütundan etkilenmez.

### <a name="new-settings-for-windows-defender-security-center-notifications-device-configuration-profile----1631906---"></a>Windows Defender Güvenlik Merkezi bildirimleri cihaz yapılandırma profilinin yeni ayarları <!-- 1631906 -->

Windows Defender Güvenlik Merkezi (WDSC) bildirimleri cihaz yapılandırma profiline üç yeni ayar eklenecektir.

Yöneticiler şunları yapabilecek:

- Kimlik sütununu gizleme
- Donanım sütununu ve onun alt ayarlarını gizleme
- Fidye Yazılımı sütununu gizleme (Onedrive İş dosya geri yüklemesi)

WDSC uygulamasında bu sütunları gizlediğinizde, son kullanıcılar bu ayarları yapılandıramaz ve gizlenen bileşenlerle ilişkilendirilmiş bildirimlerden hiçbiri oluşturulmaz.

### <a name="mam-policies-targeted-based-on-management-state----1665993---"></a>Yönetim durumu temelinde hedeflenen MAM ilkeleri <!-- 1665993 -->

MAM ilkelerinin hedefini, cihazın yönetim durumu temelinde belirleyebileceksiniz:

- **iOS cihazları** - Yönetilmeyen cihazları (yalnızca MAM) veya Intune'da yönetilen cihazları hedefleyebileceksiniz.
- **Android cihazları** - Yönetilmeyen cihazları, Intune'da yönetilen cihazları ve Intune'da yönetilen Android Enterprise Profillerini (eski adı Android for Work) hedefleyebileceksiniz.

### <a name="configure-gatekeeper-to-control-macos-app-download-source----1690459--"></a>macOS uygulama indirme kaynağını denetlemek için Ağ Geçidi Denetleyicisi'ni yapılandırma <!-- 1690459-->

Uygulamaların nereden indirilebileceğini denetleyerek cihazları uygulamalardan korumak için Ağ Geçidi Denetleyicisi'ni yapılandırabileceksiniz. Yapılandırabileceğiniz indirme kaynakları şunlardır: **Mac App Store**, **Mac App Store ve tanımlanan geliştiriciler** veya **Her Yer**. Ayrıca kullanıcıların bu Ağ Geçidi Denetleyicisi denetimlerini geçersiz kılmak için Control+tıklama kullanarak uygulama yükleyip yükleyemeyeceklerini de yapılandırabileceksiniz.

Bu ayarlar **Cihaz yapılandırması** -> **Profil oluştur** -> **macOS** -> **Uç nokta koruma** altında bulunabilir.

### <a name="configure-the-mac-application-firewall----1690461---"></a>Mac uygulaması güvenlik duvarını yapılandırma <!-- 1690461 -->

Mac uygulaması güvenlik duvarını yapılandırabileceksiniz. Bunu kullanarak bağlantıları her bağlantı noktası temelinde değil her uygulama temelinde denetleyebilirsiniz. Güvenlik duvarı korumasının avantajlarından yararlanmanızı kolaylaştırır ve geçerli uygulamalar için açılmış ağ bağlantı noktalarında istenmeyen uygulamaların denetimi ele geçirmesini önlemeye yardımcı olur.
 
Bu özellik **Cihaz yapılandırması** -> **Profil oluştur** -> **macOS** -> **Uç nokta koruma** altında bulunabilir.

Güvenlik Duvarı ayarını etkinleştirdikten sonra, güvenlik duvarını yapılandırmak için şu iki stratejiyi kullanabilirsiniz:

- Tüm gelen bağlantıları engelleme

   Hedeflenen cihazlar için tüm gelen bağlantıları engelleyebilirsiniz. Bunu yapmayı seçerseniz, tüm uygulamalar için gelen bağlantılar engellenir. 

- Belirli uygulamalara izin verme veya engelleme

   Belirli uygulamaların gelen bağlantıları almasına izin verebilir veya bunu engelleyebilirsiniz. Ayrıca yoklama isteklerine yönelik yanıtları engellemek için gizli modu da etkinleştirebilirsiniz.
 
#### <a name="more-information"></a>Daha fazla bilgi

- Tüm gelen bağlantıları engelleme

   Bu, tüm paylaşım hizmetlerinin (Dosya Paylaşımı ve Ekran Paylaşımı gibi) genel bağlantıları almasını engeller. Gelen bağlantıları almasına izin verilen sistem hizmetleri şunlardır:
   - configd - DHCP ve diğer ağ yapılandırma hizmetlerini gerçekleştirir
   - mDNSResponder - Bonjour'u gerçekleştirir
   - racoon -  IPSec'i gerçekleştirir

   Paylaşım hizmetlerini kullanmak için, **Gelen bağlantılar**'ın **Yapılandırılmadı** olarak ayarlandığından emin olun (**Engelle** olarak ayarlanmamalıdır).

- Gizli mod

   Bilgisayarın yoklama isteklerine yanıt vermesini önlemek için bunu etkinleştirin. Bilgisayar, yetkili uygulamalardan gelen istekleri yanıtlamaya devam eder. ICMP (ping) gibi beklenmedik istekler yoksayılır.
 

### <a name="updating-the-help-and-feedback-experience-on-company-portal-app-for-android---1631531---"></a>Android için Şirket Portalı uygulamasında Yardım ve Geri Bildirim deneyimini güncelleştirme <!--1631531 -->

Android uygulamalarına yönelik en iyi yöntemlerle uyumlu olacak şekilde, Android için Şirket Portalı uygulamasında Yardım ve Geri Bildirim deneyimini güncelleştiriyoruz. Önümüzdeki birkaç ay içinde Android için Şirket Portalı uygulamasını güncelleştirerek **Yardım ve Geri Bildirim** menü öğesini **Yardım** ve **Geri Bildirim Gönder** menü öğelerine ayıracağız. Son kullanıcıları günlükleri Microsoft'a yüklemeye ve şirket desteğine sorunu açıklayan bir e-posta göndermeye yönlendirmek için, **Yardım** sayfasında **Sık Sorulan Sorular** bölümü ve **E-posta Desteği** düğmesi bulunacak. **Geri Bildirim Gönder** kullanıcıyı standart Microsoft geri bildirim gönderimine yönlendirecek ve kullanıcıdan "Bir şeyi beğendim" "Bir şeyi beğenmedim" veya "Bir fikrim var" arasında seçim yapması istenecek.

### <a name="custom-book-categories-for-volume-purchase-program-vpp-ebooks----1488911---"></a>Toplu satın alma programı (VPP) eKitapları için Özel Kitap kategorileri <!-- 1488911 -->
Özel eKitap kategorileri oluşturabilecek ve VPP eKitaplarını bu özel eKitap kategorilerine ekleyebileceksiniz. Bundan sonra son kullanıcılar yeni oluşturulan eKitap kategorilerini ve bu kategorilere atanmış olan kitapları görebilecek.

#### <a name="company-portal-for-android-visual-updates---976944---"></a>Android için Şirket Portalı görsel güncelleştirmeleri <!--976944 -->

Android için Şirket Portalı uygulamasını, Android'in [Materyal Tasarım](https://material.io/) yönergelerine uyacak şekilde güncelleştireceğiz. Uygulama kullanıma sunulduğunda, yeni simgelerin resimlerini [Uygulama kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md) makalesinde yayımlayacağız. 


<!-- 1802 start -->

### <a name="new-enrollment-failure-trend-chart-and-failure-reasons-table----1471783---"></a>Yeni kayıt hatası eğilim grafiği ve hatanın nedenleri tablosu <!-- 1471783 -->

Kayıt Genel Bakış sayfasında kayıt hatalarının eğilimini ve hataların ilk beş sebebini görüntüleyebileceksiniz. Grafiğe veya tabloya tıklayarak sorun giderme tavsiyeleri ve düzeltme önerileri almak üzere ayrıntıları inceleyebileceksiniz.

### <a name="customize-your-company-portal-themes-with-hex-codes---1049561---"></a>Şirket Portalı temalarınızı onaltılık kodlarla özelleştirme <!--1049561 -->

Onaltılık kodlar kullanarak Şirket Portalı uygulamalarında tema rengini özelleştirebileceksiniz. Onaltılık kodunuzu girdiğinizde Intune, [WCAG 2.0 standartlarına](http://www.w3.org/TR/WCAG20) göre metin rengi ile arka plan rengi arasında en yüksek düzeyde kontrast sağlayan metin rengini belirler. **Mobil uygulamalar** > **Şirket Portalı**’nda metin renginin ve bu renk ile şirket logonuzun önizlemesini görüntüleyebilirsiniz. 

### <a name="new-windows-defender-credential-guard-settings-added-to-endpoint-protection-settings---1102252---"></a>Endpoint Protection ayarlarına yeni Windows Defender Credential Guard ayarları eklendi <!--1102252 --> 

**Cihaz yapılandırması** > **Profiller** > **Endpoint protection**’a yeni [Windows Defender Credential Guard](https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard] ayarlar eklenecek. Eklenecek ayarlar aşağıdaki gibidir: 

- Platform Güvenlik Düzeyi: Bir sonraki yeniden başlatmada Platform Güvenlik Düzeyi’nin etkinleştirilip etkinleştirilmeyeceğini belirtin. Sanallaştırma tabanlı güvenlik, Güvenli Önyükleme gerektirir. Sanallaştırma tabanlı güvenlik, isteğe bağlı olarak doğrudan bellek erişimi (DMA) korumaları kullanımıyla etkinleştirilebilir. DMA korumaları, donanım desteği gerektirir ve yalnızca doğru yapılandırılmış cihazlarda etkinleştirilir.
- Sanallaştırma Tabanlı Güvenlik: Bir sonraki yeniden başlatmada sanallaştırma tabanlı güvenliğin etkinleştirilip etkinleştirilmeyeceğini belirtin. 
- Windows Defender Credential Guard: Sanallaştırma tabanlı güvenlik ile Credential Guard’ı etkinleştirerek, Güvenli Önyükleme ile Platform Güvenlik Düzeyi ve Sanallaştırma Tabanlı Güvenlik’in etkin olduğu bir sonraki yeniden başlatmada kimlik bilgilerinin korunmasına yardımcı olun. Kullanılabilir seçenekler **Devre dışı**, **UEFI kilidi ile etkin**, **Kilit olmadan etkin** ve **Yapılandırılmadı** şeklindedir. 
  - “Devre dışı” seçeneği, “Kilit olmadan etkin” seçeneğiyle açılmış olan Credential Guard’ı uzaktan kapatır.

  - “UEFI kilidi ile etkin” seçeneği, Credential Guard’ın kayıt defteri anahtarı ile veya Grup İlkesi kullanılarak devre dışı bırakılamamasını sağlar. Bu ayarı kullandıktan sonra Credential Guard’ı devre dışı bırakmak için, UEFI’de belirtilen yapılandırmayı kaldırmak üzere Grup İlkesini “Devre Dışı” olarak ayarlamanız ve kullanıcısı fiziksel olarak mevcut olan her bir bilgisayardan güvenlik işlevselliğini kaldırmanız gerekir. UEFI yapılandırması devam ettiği sürece, Credential Guard etkindir.

  - “Kilit olmadan etkin” seçeneği, Credential Guard’ın Grup İlkesi kullanılarak uzaktan devre dışı bırakılmasına imkan verir. Bu ayarı kullanan cihazların en az Windows 10 (Sürüm 1511) çalıştırıyor olması gerekir.

  - “Yapılandırılmadı” seçeneği, ilke ayarını tanımlanmamış halde bırakır. Grup İlkesi, ilke ayarını kayıt defterine yazmaz ve bu nedenle bilgisayarlar ve kullanıcılar üzerinde hiçbir etkisi yoktur. Kayıt defterinde geçerli bir ayar varsa bu ayar değiştirilmeyecektir.

### <a name="reset-passwords-for-android-o-devices----1238299---"></a>Android O cihazlar için parola sıfırlama <!-- 1238299 -->
Kayıtlı Android O cihazlar için parolaları sıfırlayabileceksiniz. Bir Android O cihaza “Parola sıfırla” isteği gönderdiğinizde cihaz, geçerli kullanıcıya yeni bir cihaz kilidi açma parolası veya yönetilen profil sınaması ayarlar. Parola veya sınama, kullanıcının cihazın profil sahibi veya cihaz sahibi olmasına bağlıdır ve hemen devreye girer.

### <a name="local-device-security-option-settings----1251887---"></a>Yerel cihaz güvenliği seçeneği ayarları <!-- 1251887 -->
Yeni Yerel Cihaz Güvenlik Seçeneği ayarlarını kullanarak Windows 10 cihazlarda güvenlik ayarlarını etkinleştirebileceksiniz. Bu ayarları, bir Windows 10 cihaz yapılandırma ilkesi oluşturduğunuzda Endpoint Protection kategorisinde bulabilirsiniz.

### <a name="new-printer-settings-for-education-profiles----1308900---"></a>Eğitim profilleri için yeni yazıcı ayarları <!-- 1308900 -->

Eğitim profilleri için yeni ayarlar, **Yazıcılar** kategori: **Yazıcılar**, **Varsayılan yazıcı**, **Yeni yazıcı ekle** altında kullanılabilir olacak. 

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

### <a name="including-and-excluding-app-assignment-based-on-groups-for-android-enterprise----1813081---"></a>Android Enterprise için gruplar temelinde uygulama atamasını dahil etme ve hariç tutma <!-- 1813081 -->
Android Enterprise (eski adıyla Android for Work), uygulama ataması sırasında atama türünü seçtikten sonra dışlama işlevini destekleyecek.

<!-- the following are present prior to 1802 -->

### <a name="targeting-compliance-policies-to-devices-in-device-groups---1307012---"></a>Uyumluluk ilkelerinde cihaz gruplarındaki cihazları hedefleme <!--1307012 -->

Uyumluluk ilkelerinde kullanıcı gruplarındaki kullanıcıları hedefleyebileceksiniz. Uyumluluk ilkelerinde cihaz gruplarındaki cihazları hedefleyebileceksiniz.

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>Uygulama koruma ilkeleri  <!-- 679615 -->
Intune Uygulama Koruma İlkeleri, tüm kiracıdaki tüm kullanıcılar için hızlı bir şekilde koruma sağlamaya yönelik genel ve varsayılan ilkeler oluşturma olanağı sunar.

### <a name="configure-an-ios-app-pin----1586774---"></a>iOS uygulama PIN’i yapılandırma <!-- 1586774 -->
Yakında, hedeflenen iOS uygulamaları için bir PIN’i zorunlu kılmanız mümkün olacaktır. PIN gereksinimini ve sona erme tarihi gün sayısını Azure portalında yapılandırabilirsiniz. Gerektiğinde, kullanıcının bir iOS uygulamasına erişmeden önce yeni bir PIN ayarlaması ve kullanması gerekli olacaktır. Yalnızca Intune Uygulama SDK’sı ile uygulama koruması etkinleştirilmiş iOS uygulamaları bu özelliği destekler.

<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Azure Active Directory web siteleri, Intune Managed Browser Uygulaması gerektirebilir ve Managed Browser’da (Genel Önizleme) Çoklu Oturum Açma’yı destekler <!-- 710595 -->   
Azure Active Directory (Azure AD) kullanarak, mobil cihazlarda web sitelerine erişimi Intune Managed Browser uygulaması ile kısıtlayabileceksiniz. Web sitesi verileri, Managed Browser’da güvende ve son kullanıcının kişisel verilerinden ayrı bir yerde olacaktır. Managed Browser ayrıca Azure AD ile korunan sitelerde Çoklu Oturum Açma işlevlerini de destekleyecektir. Managed Browser’da oturum açmak veya Intune tarafından yönetilen başka bir uygulamanın bulunduğu bir cihazda Managed Browser’ı kullanmak, kullanıcıların kimlik bilgilerini girmelerine gerek kalmaksızın Managed Browser’ın Azure AD ile korunan sitelere erişmesine olanak tanır. Bu özellik, Outlook Web Access (OWA) ve SharePoint Online’ın yanı sıra Azure Uygulama Proxy’si yoluyla erişilen intranet kaynakları gibi diğer kurumsal sitelerde de geçerlidir.

<!-- the following are present prior to 1711 -->

### <a name="redirecting-macos-users-to-the-new-company-portal-app---1380728--"></a>macOS kullanıcılarını yeni Şirket Portalı uygulamasına yönlendirme <!--1380728-->   
Bir son kullanıcı, macOS cihazını kaydetmek için Şirket Portalı web sitesinde oturum açtığında, işlemi tamamlamak için yeni macOS Şirket Portalı uygulamasını indirmek üzere yönlendirilecektir. Bu durum, OS X El Capitan 10.11 ve üzeri sürümleri kullanan macOS cihazlarda görülür. 

<!-- the following are present prior to 1709 -->

### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Kullanıcı, izin verilen en yüksek cihaz kaydı sayısına ulaştığında gösterilen hata iletisi iyileştirildi <!-- 1270370 -->
Genel bir hata iletisi yerine, Android cihazı olan son kullanıcılar kolay, işlem yapılabilir bir hata iletisi görür: “BT yöneticiniz tarafından izin verilen en yüksek cihaz kaydı sayısına ulaştınız. Lütfen kayıtlı bir cihazı kaldırın veya BT yöneticinizden yardım alın.”



## <a name="notices"></a>Bildirimler

Şu anda etkin bildirim yok.



### <a name="see-also"></a>Ayrıca bkz:
Son geliştirmelere ilişkin ayrıntılar için bkz. [Microsoft Intune’daki Yenilikler](whats-new.md).


