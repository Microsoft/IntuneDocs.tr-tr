---
title: Microsoft Intune'daki yenilikler
titlesuffix: ''
description: Intune Azure portalındaki yenilikleri keşfedin
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/16/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: dougeby
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f171779a2606790dd1e59caf5e261e6d22faaf7f
ms.sourcegitcommit: 54fc806036f84a8667cf8f74086358bccd30aa7d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/20/2018
---
# <a name="whats-new-in-microsoft-intune"></a>Microsoft Intune'daki yenilikler

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Microsoft Intune’daki haftalık yenilikleri öğrenin. [Yaklaşan değişiklikler](#whats-coming), hizmet hakkında [önemli bildirimler](#notices) ve [geçmiş sunumlar](whats-new-archive.md) hakkında bilgiler de alabilirsiniz.

> [!Note]
> Karma mobil cihaz yönetimindeki (MDM) yeni işlevler hakkında bilgi için, [karma Yenilikler sayfamızı](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) gözden geçirin.


<!-- Common categories:  
  ### Device enrollment
  ### Device management
  ### App management
  ### Device configuration
  ### Role-based access control
  ### Intune apps
  ### Monitor and troubleshoot

-->   





## <a name="week-of-march-12-2018"></a>12 Mart 2018 Haftası

### <a name="new-windows-defender-exploit-guard-settings----1631893---"></a>Yeni Windows Defender Exploit Guard ayarları <!-- 1631893 -->

Altı yeni **Saldırı Yüzeyi Azaltma** ayarı ve genişletilmiş **Denetimli klasör erişimi: Klasör koruması** işlevleri artık kullanılabilir. Bu ayarlar şurada bulunabilir: Cihaz yapılandırması\Profiller\
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

## <a name="week-of-february-19-2018"></a>19 Şubat 2018 haftası

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685---"></a>Birden çok Apple DEP / Apple School Manager hesabı için Intune desteği <!-- 747685 -->

Intune, artık sayıları 100’e varan farklı [Apple Aygıt Kayıt Programı (DEP)](device-enrollment-program-enroll-ios.md) veya [Apple School Manager](apple-school-manager-set-up-ios.md) hesabından cihazların kaydını destekliyor. Karşıya yüklenen her belirteç kayıt profilleri ve cihazlar için ayrı olarak yönetilebilir. Karşıya yüklenen DEP/School Manager belirteçlerinin her biri için farklı bir kayıt profili otomatik olarak atanabilir. Birden çok School Manager belirteci karşıya yüklenirse, Microsoft School Data Sync ile bir kerede tek bir belirteç paylaşılabilir.

Geçişten sonra, Graph üzerinden Apple DEP veya ASM yönetimi için beta Graph API'leri ve yayımlanan betikler artık çalışmayacak. Yeni beta Graph API'leri geliştirme aşamasındadır ve geçiş sonrasında yayınlanacaktır.

#### <a name="see-enrollment-restrictions-per-user----1634444-eeready-wnready---"></a>Kullanıcı başına kayıt kısıtlamalarına bakın <!-- 1634444 eeready wnready -->
Artık **Sorun Giderme** dikey penceresinde **Atamalar** listesinden **Kayıt kısıtlamaları**’nı seçerek her kullanıcı için geçerli olan [kayıt kısıtlamalarını](enrollment-restrictions-set.md) görebilirsiniz.

### <a name="device-management"></a>Cihaz yönetimi
#### <a name="windows-defender-health-status-and-threat-status-reports---854704---"></a>Windows Defender sistem durumu ve tehdit durumu raporları <!--854704 -->

Windows Defender’ın sistem durumunu anlamak, Windows bilgisayarları yönetmenin anahtarıdır.  Bu güncelleştirmeyle Intune, Windows Defender aracısının sistem durumuna yeni raporlar ve eylemler ekler. [Cihaz Uyumluluğu iş yükünde](compliance-policy-monitor.md) bir durum toplama raporu kullanarak, aşağıdakilerden herhangi birine gereksinim duyan cihazları görebilirsiniz:
- imza güncelleştirmesi
- yeniden başlatıp
- el ile müdahale
- tam tarama
- müdahale gerektiren diğer aracı durumları

Her bir durum kategorisi için ayrıntılı bir rapor ile ilgilenilmesi gereken bireysel bilgisayarlar veya **Temiz** olarak raporlananlar listelenir.

#### <a name="new-privacy-settings-for-device-restrictions---1308926---"></a>Cihaz kısıtlamaları için yeni gizlilik ayarları <!--1308926 -->
Cihazlar için [iki yeni gizlilik ayarı](device-restrictions-windows-10.md#privacy) artık kullanılabilir:
- **Kullanıcı etkinliklerini yayımla**: Bunu **Engelle** şeklinde ayarlayarak, görev değiştiricide paylaşılan deneyimleri ve yakın zamanda kullanılan kaynakların bulunmasını önleyin.
- **Yalnızca yerel etkinlikler**: Bunu **Engelle** şeklinde ayarlayarak, görev değiştiricide yalnızca yerel etkinliklere bağlı olan paylaşılan deneyimleri ve yakın zamanda kullanılan kaynakların bulunmasını önleyin.

#### <a name="new-settings-for-the-edge-browser---1469166---"></a>Edge tarayıcısı için yeni ayarlar <!--1469166 -->
Edge tarayıcısı kullanan cihazlar için [iki yeni ayar artık](device-restrictions-windows-10.md#edge-browser) kullanılabilir: **Sık kullanılanlar dosyasının yolu** ve **Sık kullanılanlarda değişiklikler**.

### <a name="app-management"></a>Uygulama yönetimi
#### <a name="protocol-exceptions-for-applications---1035509---"></a>Uygulamalar için protokol özel durumları <!--1035509 -->

Belirli yönetilmeyen uygulamaları açmak için Intune Mobil Uygulama Yönetimi (MAM) veri aktarımı ilkesinde artık özel durumlar oluşturabilirsiniz. Bu tür uygulamaların BT tarafından güvenilen uygulamalar olması gerekir. Oluşturduğunuz özel durumlar dışında, veri aktarımı ilkeniz **yalnızca yönetilen uygulamalar** olarak ayarlı olduğu sürece veri aktarımınız Intune tarafından yönetilen uygulamalarla kısıtlıdır. Protokoller (iOS) veya paketler (Android) kullanarak kısıtlamalar oluşturabilirsiniz.

Örneğin MAM veri aktarımı ilkesine Webex paketini özel durum olarak ekleyebilirsiniz. Böylece, yönetilen bir Outlook e-posta iletisindeki Webex bağlantıları, doğrudan Webex uygulamasında açılacaktır. Veri aktarımı, diğer yönetilmeyen uygulamalarda kısıtlı olmaya devam edecektir. Daha fazla bilgi için bkz. [Uygulamalar için veri aktarım ilkesi özel durumları](app-protection-policies-exception.md).

#### <a name="windows-information-protection-wip-encrypted-data-in-windows-search-results----1469193---"></a>Windows arama sonuçlarında Windows Bilgi Koruması (WIP) ile şifrelenmiş veriler <!-- 1469193 -->
Windows Bilgi Koruması (WIP) ilkesindeki bir ayar, artık Windows arama sonuçlarına WIP ile şifrelenmiş verilerin dahil edilip edilmeyeceğini denetlemenize olanak tanıyor. Windows Bilgi Koruması ilkesinin **Gelişmiş ayarlar** kısmında **Windows Search Dizin Oluşturucu’nun şifrelenmiş öğeleri aramasına izin ver**’i seçerek bu uygulama koruma ilkesi seçeneğini belirleyin. Uygulama koruma ilkesi, *Windows 10* platformuna ayarlanmalı ve uygulama ilkesi **Kayıt durumu**, **Kayıt ile** olarak ayarlanmalıdır. Daha fazla bilgi için bkz. [Windows Search Dizin Oluşturucu’nun şifrelenmiş öğeleri aramasına izin ver](windows-information-protection-policy-create.md#allow-windows-search-indexer-to-search-encrypted-items).

#### <a name="configuring-a-self-updating-mobile-msi-app----1740840---"></a>Kendi kendini güncelleştiren bir MSI uygulaması yapılandırma <!-- 1740840 -->
Sürüm denetim işlemini yoksaymak için bilinen bir kendi kendini güncelleştiren MSI uygulaması yapılandırabilirsiniz. Bu yetenek, bir yarış durumuna girmeyi önlemek açısından kullanışlıdır. Bu tür bir yarış durumu örneğin uygulama, uygulama geliştiricisi tarafından otomatik olarak güncelleştirilirken diğer yandan Intune tarafından da güncelleştirildiği durumlarda ortaya çıkabilir. Her iki taraf da bir Windows istemcisinde uygulamanın bir sürümünü zorlamaya çalışabilir, böylece bir çakışma ortaya çıkabilir. Otomatik olarak güncelleştirilen bu MSI uygulamaları için **Uygulama bilgileri** dikey penceresindeki **Uygulama sürümünü yoksay**  ayarını yapılandırabilirsiniz. Bu ayar **Evet** olarak değiştirildiğinde, Microsoft Intune, Windows istemcisinde yüklü olan uygulama sürümünü yoksayar.

#### <a name="related-sets-of-app-licenses-supported-in-intune----1864117---"></a>Intune’da desteklenen ilgili uygulama lisans kümeleri <!-- 1864117 -->
Azure portalında Intune, ilgili uygulama lisans kümelerini artık kullanıcı arabiriminde tek bir uygulama öğesi olarak destekliyor. Buna ek olarak, İş İçin Microsoft Store’dan eşitlenmiş Çevrimdışı Lisanslanan uygulamalar da tek bir uygulama girdisi olarak birleştirilecek ve ayrı ayrı paketlerdeki dağıtım ayrıntıları bu tek girdiye taşınacak. Azure portalında ilgili uygulama lisans kümelerini görüntülemek için **Mobil uygulamalar** dikey penceresinden **Uygulama lisansları**’nı seçin.

### <a name="device-configuration"></a>Cihaz yapılandırması
#### <a name="windows-information-protection-wip-file-extensions-for-automatic-encryption----1463582---"></a>Otomatik şifreleme için Windows Bilgi Koruması (WIP) dosya uzantıları <!-- 1463582 -->
Windows Bilgi Koruması (WIP) ilkesindeki bir ayar, WIP politikasında tanımlanan şekilde şirket sınırında bir Sunucu İleti Bloğu (SMB) paylaşımından kopyalarken hangi dosya uzantılarının otomatik olarak şifreleneceğini belirtmenize artık izin veriyor.

#### <a name="configure-resource-account-settings-for-surface-hubs"></a>Surface Hub’lar için kaynak hesap ayarlarını yapılandırma

Surface Hub’lar için kaynak hesap ayarlarını artık uzaktan yapılandırabilirsiniz.

Kaynak hesabı, Skype/Exchange ile kimlik doğrulaması yapmak için bir Surface Hub tarafından kullanılır; böylece bir toplantıya katılabilir.
Surface Hub’ın toplantıdaki konferans odası olarak görünmesi için eşsiz bir kaynak hesabı oluşturmak isteyebilirsiniz.
Örneğin, **Konferans Salonu B41/6233** kaynak hesabı.

> [!NOTE]
> - Alanları boş bırakırsanız cihazın önceden yapılandırılmış özniteliklerini geçersiz kılarsınız.
>
> - Kaynak Hesap özellikleri, Surface Hub’da dinamik olarak değişebilir. Örneğin, parola dönüşü açıksa. Bu nedenle, Azure konsolundaki değerlerin cihazdaki gerçekliği yansıtması biraz zaman alabilir.
>
>   Surface Hub’daki geçerli yapılandırmaları anlamak için Kaynak Hesap bilgileri donanım envanterine (7 günlük aralığı vardır) veya salt okunur özelliklere dahil edilebilir. Uzak eylem gerçekleştikten sonra doğruluğu artırmak için, Surface Hub hesabını/parametrelerini güncelleştirmek üzere eylemi çalıştırdıktan hemen sonra parametrelerin durumunu alabilirsiniz.


##### <a name="attack-surface-reduction"></a>Saldırı Yüzeyini Azaltma


|Ayar adı  |Ayar seçenekleri  |Description  |
|---------|---------|---------|
|Parola korumalı yürütülebilir içeriğin e-postadan yürütülmesi|Engelle, Denetle, Yapılandırılmadı|E-posta üzerinden indirilen parola korumalı yürütülebilir dosyaların çalıştırılmasını engelleyin.|
|Gelişmiş fidye yazılımı koruması|Etkin, Denetle, Yapılandırılmadı|Agresif fidye yazılımı koruması kullanır.|
|Windows yerel güvenlik yetkilisi alt sisteminden kimlik bilgisi çalma eylemlerine bayrak ekleme|Etkin, Denetle, Yapılandırılmadı|Windows yerel güvenlik yetkilisi alt sisteminden kimlik bilgisi çalma eylemlerine bayrak ekler (lsass.exe).|
|PSExec ve WMI komutlarından işlem oluşturma|Engelle, Denetle, Yapılandırılmadı|PSExec ve WMI komutlarından kaynaklanan işlem oluşturmalarını engeller.|
|USB’den çalışan güvenilmeyen ve imzasız işlemler|Engelle, Denetle, Yapılandırılmadı|USB’den çalışan güvenilmeyen ve imzasız işlemleri engeller.|
|Bir yaygınlık, yaş veya güvenilenler listesi kriterine uymayan yürütülebilir dosyalar|Engelle, Denetle, Yapılandırılmadı|Bir yaygınlık, yaş veya güvenilenler listesi kriterine uymadıkları sürece yürütülebilir dosyaları engeller.|

##### <a name="controlled-folder-access"></a>Denetlenen klasör erişimi

|Ayar adı  |Ayar seçenekleri  |Description  |
|---------|---------|---------|
|Klasör koruması (zaten uygulanmış)|Yapılandırılmamış, Etkinleştir, Yalnızca denetle (zaten uygulanmış)<br><br> **Yeni**<br>Disk değişikliğini engelle, Disk değişikliğini denetle|
Dosya ve klasörleri kötü amaçlı uygulamaların yetkisiz değişikliklerinden korur.<br><br>**Etkinleştir**: Güvenilmeyen uygulamaların korumalı klasörlerdeki dosyaları değiştirmesini veya silmesini ve disk kesimlerine yazmasını engeller.<br><br>
**Yalnızca disk değişikliğini engelle**:<br>Güvenilmeyen uygulamaların, disk kesimlerine yazmasını engeller. Güvenilmeyen uygulamalar hala korumalı klasörlerdeki dosyaları değiştirebilir veya silebilir.|

#### <a name="additions-to-system-security-settings-for-windows-10-and-later-compliance-policies---1704133--"></a>Windows 10 ve üzeri uyumluluk ilkeleri için Sistem Güvenliği ayarlarına eklemeler <!--1704133-->

Güvenlik Duvarı ve Windows Defender Virüsten Koruma dahil olmak üzere Windows 10 uyumluluk ayarlarına bazı eklemeler geldi.


### <a name="role-based-access-control"></a>Rol tabanlı erişim denetimi
### <a name="intune-apps"></a>Intune uygulamaları
#### <a name="support-for-offline-apps-from-the-microsoft-store-for-business---1222672--"></a>İş İçin Microsoft Mağazası uygulamaları için çevrimdışı desteği <!--1222672-->
İş için Microsoft Store’dan satın aldığınız çevrimdışı uygulamalar, artık Azure portalına eşitlenir. Bu uygulamaları cihaz gruplarına veya kullanıcı gruplarına dağıtabilirsiniz. Çevrimdışı uygulamalar, mağaza tarafından değil Intune tarafından yüklenir.

#### <a name="prevent-end-users-from-manually-adding-or-removing-accounts-in-the-work-profile----1728700---"></a>Son kullanıcıların iş profiline el ile hesap eklemesini veya profilden hesap kaldırmasını önleme <!-- 1728700 -->

Bir Android for Work profiline Gmail uygulamasını dağıttığınızda, artık Android for Work cihaz kısıtlama profilindeki **Hesap ekle veya kaldır** ayarını kullanarak son kullanıcıların iş profilinde hesap ekleme veya kaldırma işlemleri yapmasını önleyebilirsiniz.

## <a name="week-of-february-5-2018"></a>5 Şubat 2018 haftası

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="new-option-for-user-authentication-for-apple-bulk-enrollment----747625-eeready---"></a>Apple toplu kaydında kullanıcı kimlik doğrulaması için yeni seçenek <!-- 747625 eeready -->

> [!NOTE]
> Yeni kiracılar bu seçeneği hemen görecektir. Mevcut kiracılar için ise bu özellik, Nisan ayı içerisinde sunulacaktır. Bu dağıtım tamamlanana kadar, bu yeni özelliklere erişemeyebilirsiniz.

Intune, artık aşağıdaki kayıt yöntemlerinde size Şirket Portalı uygulamasını kullanarak cihazların kimliğini doğrulama seçeneği sağlıyor:

- Apple Cihaz Kaydı Programı
- Apple School Manager
- Apple Configurator Kaydı

Şirket portalı seçeneği kullanılırken, bu kayıt yöntemlerini engellemeden Azure Active Directory çok faktörlü kimlik doğrulaması zorunlu tutulabilir.

Şirket portalı seçeneği kullanılırken, Intune kullanıcı benzeşimi kaydı için iOS Kurulum Yardımcısı'nda kullanıcı kimlik doğrulamasını atlar. Bu, cihazın başlangıçta kullanıcısız bir cihaz olarak kaydedildiği ve dolayısıyla kullanıcı gruplarının yapılandırmaları veya ilkelerini almadığı anlamına gelir. Cihaz, yalnızca cihaz gruplarının yapılandırmalarını ve ilkelerini alır. Bununla birlikte, Intune Şirket Portalı uygulamasını Cihaz üzerine otomatik olarak yükleyecek. Şirket Portalı uygulamasını başlatan ve bu uygulamada oturum açan ilk kullanıcı, Intune'da cihazla ilişkilendirilecek. Bu noktada kullanıcı, kendi kullanıcı gruplarının yapılandırmalarını ve ilkelerini alacak. Yeniden kayıt yapılmadan kullanıcı ilişkisi değiştirilemez.

#### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685-eeready---"></a>Birden çok Apple DEP / Apple School Manager hesabı için Intune desteği <!-- 747685 eeready -->

Intune, artık sayıları 100'e varan farklı Apple Aygıt Kayıt Programı (DEP) veya Apple School Manager hesabından cihazların kaydını destekliyor. Karşıya yüklenen her belirteç kayıt profilleri ve cihazlar için ayrı olarak yönetilebilir. Karşıya yüklenen DEP/School Manager belirteçlerinin her biri için farklı bir kayıt profili otomatik olarak atanabilir. Birden çok School Manager belirteci karşıya yüklenirse, Microsoft School Data Sync ile bir kerede tek bir belirteç paylaşılabilir.

Geçişten sonra, Graph üzerinden Apple DEP veya ASM yönetimi için beta Graph API'leri ve yayımlanan betikler artık çalışmayacak. Yeni beta Graph API'leri geliştirme aşamasındadır ve geçiş sonrasında yayınlanacaktır.

### <a name="remote-printing-over-a-secure-network----1709994----"></a>Güvenli bir ağ üzerinden uzaktan yazdırma <!-- 1709994  -->
PrinterOn’un kablosuz mobil yazdırma çözümleri kullanıcıların güvenli bir ağ üzerinden istedikleri yerde ve istedikleri zaman uzaktan yazdırma işlemi yapmalarını sağlayacak. PrinterOn, hem iOS hem de Android için Intune APP SDK'sıyla tümleştirilecek. Yönetim konsolundaki Intune **Uygulama koruma ilkeleri** dikey penceresi aracılığıyla uygulama koruma ilkelerinde bu uygulamayı hedefleyebileceksiniz. Son kullanıcılar 'PrinterOn for Microsoft' uygulamasını kendi Intune ekosistemlerinde kullanmak üzere Play Store veya iTunes üzerinden indirebilecek.

### <a name="macos-company-portal-support-for-enrollments-that-use-the-device-enrollment-manager----1352411---"></a>macOS Aygıt Kayıt Yöneticisi’ni kullanan kayıtlar için Şirket Portalı desteği <!-- 1352411 -->

macOS Şirket Portalı’na kaydolurken kullanıcılar, artık Cihaz Kayıt Yöneticisi’ni kullanabilirler.

## <a name="week-of-january-29-2018"></a>29 Ocak 2018 Haftası

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="alerts-for-expired-tokens-and-tokens-that-will-soon-expire----1639263---"></a>Süresi dolan ve dolmak üzere olan belirteçler için uyarılar <!-- 1639263 -->
Genel bakış sayfasında süresi dolan ve dolmak üzere olan belirteçler için artık uyarılar gösteriliyor. Tek bir belirtecin uyarısına tıkladığınızda, belirtecin ayrıntılar sayfasına gideceksiniz.  Birden çok belirteç içeren bir uyarıya tıklarsanız, durumlarıyla birlikte tüm belirteçlerin listesine gideceksiniz. Yöneticilerin, süreleri dolmadan önce belirteçleri yenilemesi gerekir.

### <a name="device-management"></a>Cihaz yönetimi

#### <a name="remote-erase-command-support-for-macos-devices----1438084---"></a>macOS cihazlar için uzaktan “Sil” komutu desteği <!-- 1438084 -->

macOS cihazlar için yöneticiler uzaktan Sil komutu gönderebilir.

> [!IMPORTANT]
> Sil komutu geri alınamaz ve dikkatli kullanılmalıdır.

Sil komutu işletim sistemi de içinde olmak üzere cihazdan tüm verileri kaldırır. Cihaz ayrıca Intune yönetiminden de kaldırılır. Kullanıcıya hiçbir uyarı gönderilmez ve komut gönderildiğinde silme işlemi hemen gerçekleştirilir.

6 basamaklı bir kurtarma PIN’i yapılandırmanız gerekir. Bu PIN silinmiş olan cihazın kilidini açmak için kullanılabilir ve bu noktada işletim sisteminin yeniden yüklemesi başlar. Silme işlemi başlatıldıktan sonra, Intune'da cihazın genel bakış dikey penceresindeki durum çubuğunda PIN gösterilir. Silme işlemi devam ettiği sürece PIN görüntüde kalacak. Silme işlemi tamamlandıktan sonra, cihaz Intune yönetiminden tamamen kaybolur. Herhangi birinin cihazı geri yükleyen kullanabilmesi için kurtarma PIN'ini bir yere kaydettiğinizden emin olun.

#### <a name="revoke-licenses-for-an-ios-volume-purchasing-program-token----820870---"></a>Bir iOS Toplu Satın Alma Programı belirteci için lisansları iptal et <!-- 820870 -->
Belirli bir VPP Belirteci için tüm iOS Volume Purchasing Program (VPP) uygulamalarının lisansını iptal edebilirsiniz.

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="revoking-ios-volume-purchase-program-apps-----820863---"></a>iOS - Toplu Satın Alma Programı uygulamalarını iptal etme <!-- 820863 -->
Bir veya daha fazla iOS Volume Purchase Program (VPP) uygulaması olan belirli bir cihaz için, cihazla ilişkili cihaza dayalı uygulama lisansını iptal edebilirsiniz. Bir uygulama lisansını iptal etmek ilgili VPP uygulamasını cihazdan kaldırmaz. Bir VPP uygulamasını kaldırmak için, atama işlemini **Kaldır** olarak değiştirmelisiniz. Daha fazla bilgi için bkz. [Microsoft Intune ile toplu satın alma programından satın alınan iOS uygulamalarını yönetme](vpp-apps-ios.md).

#### <a name="assign-office-365-mobile-apps-to-ios-and-android-devices-using-built-in-app-type----1332318---"></a>Yerleşik uygulama türü kullanarak Office 365 mobil uygulamaları iOS ve Android cihazlara atama <!-- 1332318 -->
**Yerleşik** uygulama türü yönettiğiniz iOS ve Android cihazlar için Office 365 uygulamaları oluşturmayı ve atamayı kolaylaştırır. Bu uygulamalar Word, Excel, PowerPoint ve OneDrive gibi 0365 uygulamalarını içerir. Uygulama türüne belirli uygulamalar atayabilir ve uygulama bilgileri yapılandırmasını düzenleyebilirsiniz.

#### <a name="including-and-excluding-app-assignment-based-on-groups----1406920---"></a>Gruplar temelinde uygulama atamasını dahil etme ve hariç tutma <!-- 1406920 -->

Uygulama ataması sırasında ve bir atama türü seçtikten sonra, hem dahil edilecek hem de hariç tutulacak grupları seçebilirsiniz.

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="you-can-assign-an-application-configuration-policy-to-groups-by-including-and-excluding-assignments-----1480316---"></a>Atamaları dahil ederek veya dışlayarak gruplara bir uygulama yapılandırma ilkesi atayabilirsiniz  <!-- 1480316 -->

Dahil etme ve dışlama atamaları bileşimini kullanarak kullanıcı ve cihaz gruplarına bir uygulama yapılandırma ilkesi atayabilirsiniz. Atamalar, özel seçili gruplar olarak veya sanal bir grup şeklinde seçilebilir. Bir sanal grup **Tüm Kullanıcılar**, **Tüm Cihazlar** ve **Tüm Kullanıcılar + Tüm Cihazlar** şeklinde olabilir.

#### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a>Windows 10 sürüm yükseltme ilkesi desteği <!-- 903672(archived), 1119689 -->  
Windows 10 cihazları; Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education ve Windows 10 Professional Education N’e yükselten bir Windows 10 sürüm yükseltme ilkesi oluşturabilirsiniz. Windows 10 sürüm yükseltmeleri hakkında daha fazla bilgi için bkz. [Windows 10 sürüm yükseltmelerini yapılandırma](edition-upgrade-configure-windows-10.md).

#### <a name="conditional-access-policies-for-intune-is-only-available-from-the-azure-portal-----1737088-1634311---"></a>Intune için Koşullu Erişim ilkeleri yalnızca Azure Portal'dan sağlanır  <!-- 1737088 1634311 -->

Bu yayından başlayarak, Koşullu Erişim ilkelerinizi yalnızca [Azure Portalı](https://portal.azure.com)’ndaki **Azure Active Directory** > **Koşullu Erişim**’de yapılandırabilir ve yönetebilirsiniz. Size kolaylık olması için, Azure Portal'daki Intune'da **Intune** > **Koşullu Erişim** konumundan da erişebilirsiniz.

#### <a name="updates-to-compliance-emails---1637547---"></a>Uyumluluk e-postalarında güncelleştirmeler <!--1637547 -->

Uyumsuz bir cihazı raporlamak amacıyla e-posta gönderildiğinde, bu e-postaya uyumsuz cihaz hakkındaki ayrıntılar da eklenir.


## <a name="week-of-january-22-2018"></a>22 Ocak 2018 haftası

### <a name="intune-apps"></a>Intune uygulamaları

#### <a name="new-functionality-for-the-resolve-action-for-android-devices---1583480--"></a>Android cihazlarda “Çözümle” eylemi için yeni işlev <!--1583480-->

Android için Şirket Portalı uygulaması, **Cihaz ayarlarını güncelleştir** için “Çözümle” eylemini [cihaz şifreleme sorunlarını](/intune-user-help/encrypt-your-device-android) çözümlemek üzere genişletiyor.

#### <a name="remote-lock-available-in-company-portal-app-for-windows-10---676506--"></a>Windows 10 için Şirket Portalı uygulamasında uzaktan kilitleme kullanılabilir <!--676506-->
Son kullanıcılar artık, Windows 10 için Şirket Portalı uygulamasını kullanarak cihazlarını uzaktan kilitleyebilirler. Bu, etkin olarak kullanmakta oldukları yerel cihazda görüntülenmez.

#### <a name="easier-resolution-of-compliance-issues-for-the-company-portal-app-for-windows-10---676546--"></a>Windows 10 için Şirket Portalı'ndaki uyumluluk sorunlarının daha kolay çözümü<!--676546-->
Windows cihazı olan son kullanıcılar, Şirket Portalı uygulamasında uyumsuzluk nedenine dokunabilecek. Buna dokunmaları mümkün olduğunda, ayarlar uygulamasında sorunu çözebilecekleri konuma gidecekler.

## <a name="week-of-december-11-2017"></a>11 Aralık 2017 haftası

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="new-automatic-redeployment-setting----1469168---"></a>Yeni otomatik yeniden dağıtım ayarı<!-- 1469168 -->
**Otomatik yeniden dağıtım** ayarı, yönetici haklarına sahip olan kullanıcıların cihaz kilidi ekranında **CTRL + Win + R** tuşunu kullanarak tüm kullanıcı verilerini ve ayarlarını silmelerini sağlar. Cihaz otomatik olarak yeniden yapılandırılacak ve yönetime yeniden kaydedilir. Bu ayar, Windows 10 > Aygıt kısıtlamaları > Genel > Otomatik yeniden dağıtma altında bulunabilir. Ayrıntılar için bkz. [Windows 10 için Intune cihaz kısıtlama ayarları](device-restrictions-windows-10.md#general).

#### <a name="support-for-additional-source-editions-in-the-windows-10-edition-upgrade-policy-----903672--1119689---"></a>Windows 10 sürüm yükseltme ilkesinde ek kaynak sürümleri desteği  <!-- 903672,  1119689 -->
Artık başka Windows 10 sürümlerinden (Windows 10 Pro, Windows 10 Pro Education, Windows 10 Cloud, vb.) yükseltme yapmak için Windows 10 sürüm yükseltme ilkesini kullanabilirsiniz. Bu sürümden önce, desteklenen sürüm yükseltme yolları daha sınırlıydı. Ayrıntılar için bkz. [Windows 10 sürüm yükseltmelerini yapılandırma](edition-upgrade-configure-windows-10.md).

#### <a name="new-windows-defender-security-center-wdsc-device-configuration-profile-settings----1335507---"></a>Yeni Windows Defender Güvenlik Merkezi (WDSC) cihaz yapılandırma profili ayarları <!-- 1335507 -->

Intune, cihaz yapılandırma profili ayarlarının Uç nokta koruma altında **Windows Defender Güvenlik Merkezi** adında yeni bir bölüm ekler. BT yöneticileri, son kullanıcıların Windows Defender Güvenlik Merkezi uygulamasının hangi sütunlarına erişebileceklerini yapılandırabilir. Bir BT yöneticisi Windows Defender Güvenlik Merkezi uygulamasında bir sütun gizlerse, gizli sütunlarla ilgili hiçbir bildirim kullanıcının cihazında görüntülenmez.

Yöneticilerin Windows Defender Güvenlik Merkezi aygıt yapılandırma profili ayarlarından gizleyebilecekleri sütunlar şunlardır:
- Virüs ve tehdit koruması
- Cihaz performans ve sistem durumu
- Güvenlik duvarı ve ağ korumaları
- Uygulama ve tarayıcı denetimi
- Aile seçenekleri

BT yöneticileri, kullanıcıların hangi bildirimleri aldığını da özelleştirebilir. Örneğin, kullanıcıların WDSC'deki görünür sütunlar tarafından oluşturulan tüm bildirimleri alıp almayacaklarını veya yalnızca kritik bildirimleri alıp almayacaklarını yapılandırabilirsiniz. Kritik olmayan bildirimlere, Windows Defender Antivirus etkinliğinin periyodik özetleri ve taramalar tamamlandığında verilen bildirimler dahildir. Diğer tüm bildirimler kritik olarak kabul edilir. Ayrıca, bildirim içeriğini kendiniz de özelleştirebilirsiniz, örneğin, kullanıcıların cihazlarında görünen bildirimlere eklemek için BT iletişim bilgilerini sağlayabilirsiniz.

#### <a name="multiple-connector-support-for-scep-and-pfx-certificate-handling----1361755---"></a>SCEP ve PFX sertifika işleme için birden çok bağlayıcı desteği <!-- 1361755 -->

Şirket içi NDES bağlayıcısı kullanan müşteriler, artık tek bir kiracıda birden fazla bağlayıcıyı yapılandırarak sertifikaları cihazlara teslim edebilir.

Bu yeni yetenek aşağıdaki senaryoyu destekler:

- **Yüksek kullanılabilirlik**

Her bir NDES bağlayıcısı, Intune'dan sertifika istekleri çeker.  Bir NDES Bağlayıcısı çevrimdışı olursa, diğer bağlayıcı istekleri işlemeye devam edebilir.

#### <a name="customer-subject-name-can-use-aaddeviceid-variable-----1468599---"></a>Özel konu adı AAD_DEVICE_ID değişkenini kullanabilir  <!-- 1468599 -->

Intune'da SCEP sertifika profili oluşturduğunuzda, artık özel konu adını oluştururken AAD_DEVICE_ID değişkenini kullanabilirsiniz.   Bu SCEP profili kullanılarak sertifika istendiğinde, değişkenin yerini sertifika isteğinde bulunan cihazın AAD cihaz kimliği alır.


### <a name="device-management"></a>Cihaz yönetimi

#### <a name="manage-jamf-enrolled-macos-devices-with-intunes-device-compliance-engine----1592747---"></a>Jamf'e kayıtlı makro cihazları Intune cihaz uyumluluk motoruyla yönetme <!-- 1592747 -->
Artık, Intune konsolunda tanımlanan ilkelere uyumu değerlendirecek olan MacOS cihaz durumu bilgilerini Intune'a göndermek için Jamf kullanabilirsiniz. Cihaz uyumluluk durumuna ve diğer koşullara (konum, kullanıcı riski vb.) bağlı olarak koşullu erişim, buluta erişen ve Office 365 de dahil olmak üzere Azure AD ile bağlantılı kurum içi uygulamalara erişen macOS cihazlarına uyumluluğu zorlar. [Jamf tümleştirmesini ayarlama](conditional-access-integrate-jamf.md) ve [Jamf tarafından yönetilen cihazlarda uyumluluğu zorlama](conditional-access-assign-jamf.md) hakkında daha fazla bilgi edinin.

#### <a name="new-ios-device-action------1424701---"></a>Yeni iOS cihaz eylemi  <!-- 1424701 -->

Şimdi IOS 10.3 denetlenen cihazlarını kapatabilirsiniz. Bu eylem, son kullanıcıya herhangi bir uyarı yapılmadan cihazı hemen kapatır. **Cihaz** iş yükünde bir cihaz seçtiğinde, cihaz özelliklerinde **Kapat (yalnızca denetimli)** eylemi bulunabilir.

#### <a name="disallow-datetime-changes-to-samsung-knox-devices----1468103---"></a>Samsung Knox cihazlarında tarih/saat değişikliklerine izin vermeme <!-- 1468103 -->

Samsung Knox cihazlarında tarih ve saat değişikliklerini engellemenize olanak tanıyan yeni bir özellik ekledik. Bunu, **Cihaz yapılandırma profilleri** > **Cihaz kısıtlamaları (Android)** > **Genel** altında bulabilirsiniz.

#### <a name="surface-hub-resource-account-supported----1566442----"></a>Surface Hub kaynak hesabını destekler <!-- 1566442  -->

Yeni bir cihaz eylemi eklendi; böylece yöneticiler bir Surface Hub ile ilişkili kaynak hesabını tanımlayıp güncelleyebilir.

Kaynak hesabı, Skype/Exchange ile kimlik doğrulaması yapmak için bir Surface Hub tarafından kullanılır; böylece bir toplantıya katılabilir. Eşsiz bir kaynak hesabı oluşturabilir; böylece Surface Hub toplantıdaki konferans odası olarak görünür. Örneğin, kaynak hesabı *Konferans Salonu B41/6233* olarak görünebilir. Surface Hub için kaynak hesabı (cihaz hesabı olarak bilinir), genellikle Konferans odası konumu için ve diğer kaynak hesabı parametreleri değiştirilmesi gerektiğinde yapılandırılması gerekir.

Yöneticiler bir cihazdaki kaynak hesabını güncelleştirmek istediği zaman, cihazla ilişkili geçerli Active Directory/Azure Active Directory kimlik bilgilerini sağlamaları gerekir. Cihaz için parola rotasyonu açıksa, yöneticiler parolayı bulmak için Azure Active Directory'ye gitmelidir.

> [!NOTE]
> Tüm alanlar bir paket halinde gönderilir ve daha önce yapılandırılmış olan tüm alanların üzerine yazılır. Boş alanlar var olan alanların üzerine yazılır.

Yöneticilerin yapılandırabileceği ayarlar şunlardır:

- **Kaynak hesabı**
   - **Active Directory kullanıcısı**

      EtkiAlanıAdı\KullanıcıAdı veya Kullanıcı Asıl Adı (UPN):user@domainname.com

   - **Parola**

- **İsteğe bağlı kaynak hesabı parametreleri** (belirtilen kaynak hesabını kullanarak ayarlanması gerekir)

   - **Parola rotasyon süresi**

     Güvenlik nedeniyle, hesap şifresinin her hafta Surface Hub tarafından güncellenmesini sağlar. Bu etkinleştirildikten sonra parametreleri yapılandırmak için, Azure Active Directory'deki hesapta önce parolanın sıfırlanması gerekir.

   - **SIP (Oturum Başlatma Protokolü) adresi**

     Yalnızca otomatik bulma başarısız olduğunda kullanılır.

   - **E-posta**

     Cihaz/kaynak hesabının e-posta adresi.

   - **Exchange sunucusu**

     Yalnızca otomatik bulma başarısız olduğunda gereklidir.

   - **Takvim eşitleme**

     Takvim eşitleme ve diğer Exchange server hizmetlerini etkinleştirilip etkinleştirilmeyeceğini belirtir. Örneğin: Toplantı eşitleme.

#### <a name="install-office-apps-on-macos-devices----1494311---"></a>MacOS cihazlarda Office uygulamalarını yükleyin <!-- 1494311 -->
Artık Office uygulamalarını macOS cihazlara yükleyebilirsiniz. Bu yeni uygulama türü, Word, Excel, PowerPoint, Outlook ve OneNote yüklemeye izin verir. Bu uygulamalar, uygulamalarınızı güvenli ve güncel tutmaya yardımcı olmak için ayrıca Microsoft AutoUpdate (MAU) ile gelir.

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="delete-an-ios--volume-purchasing-program-token----820879---"></a>Bir iOS Toplu Satın Alma Programı belirtecini silin <!-- 820879 -->
Konsolu kullanarak iOS Toplu Satın Alma Programı (VPP) belirtecini silebilirsiniz. VPP belirteci kopya örnekleriniz olduğunda bu gerekli olabilir.

### <a name="intune-apps"></a>Intune uygulamaları


### <a name="role-based-access-control"></a>Rol tabanlı erişim denetimi

#### <a name="a-new-entity-collection-named-current-user-is-limited-to-currently-active-user-data----1667026---"></a>Geçerli Kullanıcı adlı yeni bir varlık koleksiyonu şu anda etkin olan kullanıcı verisi ile sınırlıdır <!-- 1667026 -->

**Kullanıcılar** varlık koleksiyonu, kuruluşunuzda kendisine lisans atanmış olan tüm Azure Active Directory (Azure AD) kullanıcılarını içerir. Örneğin, bir kullanıcı Intune'a eklenebilir ve son bir ay içerisinde kaldırılabilir. Bu kullanıcı raporun olduğu saatte bulunmamakla birlikte, verilerde kullanıcı ve durumu bulunur. Kullanıcının verilerinizdeki varlığının süresini gösterecek bir rapor oluşturabilirsiniz.

Buna karşılık, yeni **Geçerli Kullanıcı** varlık koleksiyonu yalnızca kaldırılmamış olan kullanıcıları içerir. **Geçerli kullanıcı** varlık koleksiyonu yalnızca etkin kullanıcıları içerir. **Geçerli Kullanıcı** öğesi hakkında daha fazla bilgi edinmek için bkz. [Geçerli kullanıcı varlığı için başvuru](reports-ref-current-user.md).


### <a name="updated-graph-apis----1736360---"></a>Güncelleştirilmiş Graph API'leri <!-- 1736360 -->

Bu sürümde, beta aşamasında olan Intune için Graph API'lerinden birkaçını güncelleştirdik. Daha fazla bilgi için lütfen aylık [Graph API değişiklik günlüğünü](https://developer.microsoft.com/graph/docs/concepts/changelog) gözden geçirin.

## <a name="week-of-december-4-2017"></a>4 Aralık 2017 haftası

### <a name="monitor-and-troubleshoot"></a>İzleme ve sorun giderme

#### <a name="intune-supports-windows-information-protection-wip-denied-apps----1479103---"></a>Intune, Windows Information Protection (WIP) tarafından reddedilen uygulamaları destekler <!-- 1479103 -->
Intune'da reddedilen uygulamaları belirtebilirsiniz. Uygulama reddedilirse, şirket bilgilerine erişimi engellenir; aslında izin verilen uygulamalar listesinin tam tersidir. Daha fazla bilgi için bkz. [Windows Information Protection için önerilen reddedilenler listesi](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp?f=255&MSPPError=-2147217396#recommended-deny-list-for-windows-information-protection).


## <a name="week-of-november-27-2017"></a>27 Kasım 2017 Haftası

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="troubleshoot-enrollment-issues-----746324---"></a>Kayıt sorunlarını giderme  <!-- 746324 -->

**Sorun Giderme** çalışma alanı, şimdi kullanıcı kayıt sorunlarını gösterir. Sorunun ayrıntıları ve önerilen düzeltme adımları, yönetici ve yardım masası çalışanlarının sorunları çözmesine yardımcı olabilir. Bazı kayıt sorunları burada yer almaz ve bazı hatalar için düzeltme önerileri bulunmayabilir.

#### <a name="group-assigned-enrollment-restrictions----747598---"></a>Gruba atanan kayıt kısıtlamaları <!-- 747598 -->

Bir Intune yöneticisi olarak, artık [kullanıcı grupları için özel Cihaz Türü ve Cihaz Sınırı kayıt sınırlamaları oluşturabilirsiniz](enrollment-restrictions-set.md).

Intune Azure portalı, her kısıtlama türü için en fazla 25 örnek oluşturmanıza olanak sağlar. Bunlar daha sonra kullanıcı gruplarına atanabilir. Grup tarafından atanan kısıtlamalar varsayılan kısıtlamaları geçersiz kılar.

Bir kısıtlama türünün tüm örnekleri kesin bir şekilde sıralanmış bir listede tutulur. Bu sıra, çakışmaları çözümlemek için bir öncelik değerini tanımlar. Birden fazla kısıtlama örneğinden etkilenen bir kullanıcı, yalnızca en yüksek öncelik değerine sahip örnek tarafından kısıtlanır. Belirli bir örneği listede farklı bir konuma sürükleyerek örneğin önceliğini değiştirebilirsiniz.

Bu işlevsellik, Android for Work ayarlarının Android For Work kayıt menüsünden Kayıt Kısıtlamaları menüsüne geçişi ile birlikte yayımlanacak. Bu geçiş birkaç gün sürebileceğinden, grup atamasının Kayıt Kısıtlamaları için etkinleştirildiğini görmeden önce hesabınız Kasım yayınının diğer bölümleri için güncelleştirilebilir.

#### <a name="support-for-multiple-network-device-enrollment-service-ndes-connectors----1528104---"></a>Çoklu Ağ Cihazı Kayıt Hizmeti (NDES) bağlayıcısı desteği <!-- 1528104 -->

NDES, etki alanı kimlik bilgileri olmadan çalışan mobil cihazların Basit Sertifika Kayıt Protokolü’nü (SCEP) temel alarak sertifikaları edinmesini sağlar.
Bu güncelleştirme ile birden çok NDES bağlayıcısı desteklenir.

#### <a name="manage-android-for-work-devices-independently-from-android-devices----1490731-eeready--"></a>Android for Work cihazlarını Android cihazlardan ayrı olarak yönetme <!-- 1490731 EEready-->

**Not**: Aşağıdaki değişiklikler, Kasım güncelleştirmesi ile dağıtılmaya başlanacaktır ancak hesabınızda yürürlüğe girmesi zaman alabilir. Bu değişiklikler hesabınızda geçerli olduğunda Office 365 portalında bir onay bildirimi alacaksınız. Dağıtım sonrasında, ek yönetilebilirlik seçeneklerine sahip olacaksınız. Dağıtım sırasında son kullanıcı deneyiminde hiçbir değişiklik olmayacak.

Intune, Android for Work cihazlarının Android platformundan bağımsız olarak kaydını yönetmeyi destekler. Bu ayarlar **Cihaz Kaydı** > **Kayıt kısıtlamaları** > **Cihaz Türü Kısıtlamaları** altında yönetilir. (Eskiden **Cihaz Kaydı** > **Android for Work Kaydı** > **Android for Work Kayıt Ayarları** altında bulunuyordu.)

Varsayılan olarak, Android for Work cihaz ayarlarınız Android cihazlarınız için ayarlarınızla aynı olur. Ancak Android for Work ayarlarınızı değiştirdikten sonra artık bu durum oluşmaz.

Kişisel Android for Work kaydını engellerseniz, yalnızca kurumsal Android cihazlar Android for Work olarak kaydolabilir.

Yeni ayarlarla çalışırken şu noktaları göz önünde bulundurun:

##### <a name="if-you-have-never-previously-onboarded-android-for-work-enrollment"></a>Daha önce hiç Android for Work kaydı eklemediyseniz

Yeni Android for Work platformu varsayılan Cihaz Türü Kısıtlamalarında engellidir. Özelliği ekledikten sonra, cihazların Android for Work ile kaydolmasına izin verebilirsiniz. Bunu yapmak için varsayılan ayarı değiştirin veya varsayılan Cihaz Türü Kısıtlamasının yerine geçen yeni bir Cihaz Türü Kısıtlaması oluşturun.

##### <a name="if-you-have-onboarded-android-for-work-enrollment"></a>Android for Work kaydı eklediyseniz

Daha önceden eklediyseniz durumunuz seçtiğiniz ayara bağlıdır:

| Ayar | Varsayılan Cihaz Türü Kısıtlamasında Android for Work durumu | Notlar |
| --- | --- | --- |
| **Tüm cihazları Android olarak yönetme** | Engellendi | Tüm Android cihazların Android for Work ile kaydolması gerekir. |
| **Desteklenen cihazları Android for Work olarak yönetme** | İzin Verildi | Android for Work’ü destekleyen tüm Android cihazların Android for Work ile kaydolması gerekir. |
| **Yalnızca bu gruplardaki kullanıcılar için desteklenen cihazları Android for Work olarak yönetme** | Engellendi | Varsayılan ayarı geçersiz kılmak için ayrı bir Cihaz Türü Kısıtlama ilkesi oluşturuldu. Bu ilke önceden Android for Work kaydına izin vermek için seçtiğiniz grupları tanımlar. Seçili gruplardaki kullanıcıların Android for Work cihazlarını kaydetmesine izin verilir. Diğer tüm kullanıcıların Android for Work ile kaydolması kısıtlanır. |

Tüm durumlarda, hedeflenen düzenlemeniz korunur. Ortamınızda Android for Work’e genel olarak veya grup başına verilen izinleri tutmak için herhangi bir eylem gerçekleştirmeniz gerekmez.

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="app-install-report-updated-to-include-install-pending-status----1249446---"></a>Uygulama yükleme raporu Yükleme Bekletiliyor durumunu içerecek şekilde güncelleştirildi <!-- 1249446 -->  

Her uygulama için **Mobil uygulamalar** iş yükünde **Uygulama** listesi üzerinden erişilebilen **Uygulama yükleme durumu** raporu, şimdi Kullanıcılar ve Cihazlar için **Yükleme Bekletiliyor** sayısını içeriyor.

#### <a name="ios-11-app-inventory-api-for-mobile-threat-detection----1391759---"></a>Mobil Tehdit Algılama için iOS 11 uygulama envanteri API’si<!-- 1391759 -->

Intune, kişisel ve kuruluşa ait cihazlardan uygulama envanter bilgilerini toplayarak Lookout for Work gibi Mobil Tehdit Algılama (MTD) sağlayıcıları için kullanılabilir hale getirir. iOS 11+ cihazlarının kullanıcılarından uygulama envanteri toplayabilirsiniz.

**Uygulama envanteri**  
Şirkete ait iOS 11+ ve kişisel cihazlar için envanterler MTD hizmet sağlayıcınıza gönderilir. Uygulama envanterindeki veriler şunları içerir:

 - Uygulama Kimliği
 - Uygulama Sürümü
 - Uygulama Kısa Sürümü
 - Uygulama Adı
 - Uygulama Paketi Boyutu
 - Uygulama Dinamik Boyutu
 - Uygulamanın doğrulanıp doğrulanmadığı
 - Uygulamanın yönetilip yönetilmediği


### <a name="device-management"></a>Cihaz yönetimi

#### <a name="migrate-hybrid-mdm-users-and-devices-to-intune-standalone----1463747-wnready---"></a>Karma MDM kullanıcıları ve cihazlarını tek başına Intune'a geçirme <!-- 1463747 wnready -->
Kullanıcıları ve onların cihazlarını karma MDM’den Azure Portal’daki Intune’a geçirmek için yeni süreçler ve araçlar artık kullanılabilir. Bunlar sayesinde aşağıdaki görevleri yapabilirsiniz:
- İlkeleri ve profilleri Configuration Manager konsolundan Azure Portal'daki Intune'a kopyalama
- Kullanıcıların bir alt kümesini Azure Portal'da Intune'a taşırken kalanlarını karma MDM'de bırakma
- Cihazları yeniden kaydetmeye gerek kalmadan Azure Portal'daki Intune'a geçirme

Ayrıntılar için bkz. [Karma MDM kullanıcıları ve cihazlarını tek başına Intune'a geçirme](https://docs.microsoft.com/sccm/mdm/deploy-use/migrate-hybridmdm-to-intunesa).

#### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Yüksek kullanılabilirlik desteği ile şirket içi Exchange bağlayıcısı <!-- 676614 -->
Exchange bağlayıcısı belirtilen CAS'yi kullanarak Exchange bağlantısı oluşturduktan sonra, bağlayıcı artık diğer CAS'leri bulabilir. Birincil CAS kullanılamaz duruma gelirse, birincil CAS kullanılabilir duruma gelene kadar varsa bağlayıcı başka bir CAS’ye yük devreder. Ayrıntılar için bkz. [Yüksek kullanılabilirlik desteği ile şirket içi Exchange bağlayıcısı](exchange-connector-install.md#on-premises-exchange-connector-high-availability-support).

#### <a name="remotely-restart-ios-device-supervised-only----1424595---"></a>iOS cihazı uzaktan yeniden başlatma (yalnızca denetimli) <!-- 1424595 -->

Artık bir cihaz eylemi kullanarak, denetimli bir iOS 10.3+ cihazı yeniden başlatma için tetikleyebilirsiniz. Cihazı yeniden başlatma eylemini kullanma hakkında daha fazla bilgi için bkz. [Intune ile cihazları uzaktan yeniden başlatma](device-restart.md).

> [!Note]
> Bu komut, denetlenen cihazlar ve **Cihaz Kilidi** erişim hakkı gerektirir. Cihaz hemen yeniden başlatılır. Geçiş koduyla kilitli iOS cihazlar yeniden başlatmadan sonra bir Wi-Fi ağına yeniden katılmaz; yeniden başlatıldıktan sonra sunucu ile iletişim kuramayabilir.

#### <a name="single-sign-on-support-for-ios----1333645---"></a>iOS için Çoklu Oturum Açma desteği <!-- 1333645 -->  

iOS kullanıcıları için Çoklu Oturum Açma kullanabilirsiniz. Çoklu Oturum Açma yükünde kullanıcı kimlik bilgilerini aramak için kodlanan iOS uygulamaları bu yük yapılandırması güncelleştirmesi ile işlevseldir. Asıl Ad ve Bölgeyi yapılandırmak için UPN ve Intune Cihaz Kimliğini de kullanabilirsiniz. Ayrıntılar için bkz. [Intune'u iOS cihazında çoklu oturum açma için yapılandırma](sso-ios.md).

#### <a name="add-find-my-iphone-for-personal-devices---1427287--"></a>Kişisel cihazlar için "iPhone’umu Bul" özelliği ekleme <!--1427287-->
Artık iOS cihazlarda Etkinleştirme Kilidi’nin açık olup olmadığını görüntüleyebilirsiniz. Bu özellik önceden Intune’da klasik portalda bulunuyordu.


#### <a name="remotely-lock-managed-macos-device-with-intune----1437691---"></a>Intune ile yönetilen macOS cihazları uzaktan kilitleme <!-- 1437691 -->

Kayıp bir macOS cihazı kilitleyebilir ve 6 basamaklı bir kurtarma PIN’i ayarlayabilirsiniz. Kilitliyken, **Cihaza genel bakış** dikey penceresi başka bir cihaz eylemi gönderilene kadar PIN’i görüntüler.

Daha fazla bilgi için bkz. [Intune ile yönetilen cihazları uzaktan kilitleme](device-remote-lock.md).

#### <a name="new-scep-profile-details-supported----1559808---"></a>Desteklenen yeni SCEP profili ayrıntıları <!-- 1559808 -->

Yöneticiler artık Windows, iOS, macOS ve Android platformlarında SCEP profili oluştururken ek ayarlar yapabilir.  Yöneticiler IMEI, seri numarası veya konu adı biçiminde e-posta dahil ortak ad ayarlayabilir.

<!-- #### Update to what device details your company may see -1616825
The Company Portal app for Android can now use geofencing to protect access to company resources. It uses network details such as IP address, default gateway address, and Domain Name System (DNS) to determine whether to allow access to protected company resources. -->

#### <a name="retain-data-during-a-factory-reset----1588489---"></a>Fabrika sıfırlaması sırasında verileri tutma <!--1588489 -->
Windows 10 sürüm 1709 ve üstünü fabrika ayarlarına sıfırlarken, yeni bir özellik sağlanır. Yöneticiler fabrika sıfırlaması sırasında cihaz kaydı ve diğer sağlanan verilerin cihazda tutulup tutulmayacağını belirtebilir.

Fabrika sıfırlamasında aşağıdaki veriler tutulur:
- Cihazla ilişkilendirilen kullanıcı hesapları
- Makine durumu (etki alanına katılım, Azure Active Directory’ye katılım)
- MDM kaydı
- OEM tarafından yüklenen uygulamalar (mağaza ve Win32 uygulamaları)
- Kullanıcı profili
- Kullanıcı profili dışındaki kullanıcı verileri
- Kullanıcı otomatik oturum açma

Şu veriler korunmaz:
- Kullanıcı dosyaları
- Kullanıcı tarafından yüklenen uygulamalar (mağaza ve Win32 uygulamaları)
- Varsayılan olmayan cihaz ayarları

### <a name="monitor-and-troubleshoot"></a>İzleme ve sorun giderme
#### <a name="window-10-update-ring-assignments-are-displayed----1621837---"></a>Windows 10 güncelleştirme halkası atamaları görüntülenir <!-- 1621837 -->
**Sorun giderirken**, görüntülediğiniz kullanıcı için Windows 10 güncelleştirme halkası atamalarını görebilirsiniz.  

#### <a name="windows-defender-advanced-threat-protection-reporting-frequency-settings-----1455974----"></a>Windows Defender Gelişmiş Tehdit Koruması raporlama sıklığı ayarları <!-- 1455974  -->
Windows Defender Gelişmiş Tehdit Koruması (WDATP) hizmeti yöneticilerin yönetilen cihazlar için raporlama sıklığını yönetmesine olanak sağlar. Yeni **Telemetri raporlama sıklığını hızlandır** seçeneğiyle, WDATP daha sık veri toplar ve riskleri değerlendirir. Raporlama için varsayılan ayar, hızı ve performansı en iyi duruma getirir. Raporlama sıklığını artırmak yüksek riskli cihazlar için yararlı olabilir. Bu ayar, **Cihaz yapılandırmaları** içinde **Windows Defender ATP** profilinde bulunabilir.

#### <a name="audit-updates----1412961---"></a>Güncelleştirmeleri denetleme <!-- 1412961 -->  
Intune denetimi, Intune’la ilgili değişiklik işlemlerinin bir kaydını sağlar.  Tüm oluşturma, güncelleştirme, silme ve uzak görev işlemleri yakalanır ve bir yıl süreyle tutulur.  Azure portalı her iş yükü içinde son 30 günlük denetim verilerinin bir görünümünü sağlar ve bunlar filtrelenebilir.  Karşılık gelen bir Graph API, geçen yıl için depolanan denetim verilerinin alınmasına olanak sağlar.

Denetim **İZLEYİCİ** grubu altında bulunur. Her bir iş yükü için bir **Denetim Günlükleri** menü öğesi bulunur.




## <a name="week-of-november-20-2017"></a>20 Kasım 2017 Haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="google-play-protect-support-on-android----908720---"></a>Android’de Google Play Protect desteği <!-- 908720 -->

Android Oreo sürümüyle Google, kuruluşların güvenli uygulamalar çalıştırmasına ve Android görüntülerinin güvenliğini sağlamasına imkan veren Google Play Protect adlı bir güvenlik özellikleri paketi piyasaya sunuyor. Intune, artol SafetyNet uzak kanıtlama dahil olmak üzere Google Play Protect özelliklerini destekliyor. Yöneticiler, Google Play Protect’ın yapılandırılması ve iyi durumda olmasını gerektiren uyumluluk ilke gereksinimleri ayarlayabilir.
**SafetyNet cihaz kanıtlama** ayarı, cihazın iyi durumda olduğu ve güvenliğinin aşılmadığını doğrulamak için cihazın bir Google hizmetiyle bağlanmasını gerektirir. Yöneticiler ayrıca, yüklenen uygulamaların Google Play hizmetleri tarafından doğrulanmasını gerektiren bir Android for Work yapılandırma profili ayarı da ayarlayabilir. Koşullu erişim, bir cihaz Google Play Protect gereksinimleriyle uyumlu olmadığında kullanıcıların şirket kaynaklarına erişimini engelleyebilir.

- [Google Play Koruması'nı etkinleştirmek için cihaz uyumluluk ilkesi oluşturmayı](https://docs.microsoft.com/intune/compliance-policy-create-google-play-protect) öğrenin.

#### <a name="text-protocol-allowed-from-managed-apps----1414050----"></a>Yönetilen Uygulamalar izin verilen metin protokolü <!-- 1414050  -->

Intune Uygulama SDK’sı tarafından yönetilen uygulamalar SMS mesajları gönderebilir.

## <a name="week-of-november-13-2017"></a>13 Kasım 2017 Haftası

### <a name="intune-apps"></a>Intune Uygulamaları
#### <a name="company-portal-app-for-macos-is-available---1541700--"></a>Şirket Portalı uygulaması macOS için kullanılabilir <!--1541700-->
MacOS'daki Intune Şirketi Portalı, kayıtlı oldukları tüm cihazlar için kullanıcılarınıza gereken tüm bilgileri ve uyum bildirimlerini temiz bir şekilde görüntülemek için iyileştirilmiş güncel bir tecrübeye sahiptir. Ve Intune Şirketi Portalı bir cihaza dağıtıldığında, macOS için Microsoft AutoUpdate kendisine güncelleme sağlayacaktır. Yeni macOS için Intune Şirket Portalı’nı, bir macOS cihazından Intune Şirketi Portalı web sitesine girerek indirebilirsiniz.

#### <a name="microsoft-planner-is-now-part-of-the-mobile-app-management-mam-list-of-approved-apps-----1248473---"></a>Microsoft Planner, artık mobil uygulama yönetimi (MAM) onaylı uygulamalar listesinin bir parçasıdır <!-- 1248473 -->
IOS ve Android için Microsoft Planner uygulaması artık mobil uygulama yönetimi (MAM) için onaylanan uygulamaların bir parçasıdır. Uygulama, tüm kiracılara Azure portalındaki Intune App Protection dikey penceresi aracılığıyla yapılandırılabilir.
- [Onaylı uygulamaların MAM listesi](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) hakkında daha fazla bilgi edin.

#### <a name="per-app-vpn-requirement-update-frequency-on-ios-devices------1547061---"></a>IOS cihazlarında Uygulama Başına VPN gereksinimi güncelleştirme sıklığı <!-- 1547061 -->  
Yöneticiler, artık iOS cihazlarındaki uygulamalar için Uygulama Başına VPN gereksinimlerini kaldırabilir; etkilenen cihazlar genellikle bir sonraki Intune iade etme işleminden sonra olacak ve bu da genellikle 15 dakika içinde gerçekleşecektir.  

### <a name="monitor-and-troubleshoot"></a>İzleme ve sorun giderme
#### <a name="support-for-system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Exchange Bağlayıcı için System Center Operations Manager yönetim paketi desteği <!-- 885457 -->
Exchange bağlayıcı için Sistem Merkezi İşlemleri Yöneticisi (SCOM) yönetim paketi, Exchange bağlayıcı günlüklerini ayrıştırmanıza yardımcı olmak için kullanılabilir. Bu özellik, sorun gidermeniz gerektiğinde Exchange bağlayıcıyı izlemek için size farklı yollar sunar.

## <a name="week-of-november-6-2017"></a>6 Kasım 2017 Haftası

### <a name="device-enrollment"></a>Cihaz kaydı
#### <a name="co-management-for-windows-10-devices-----1243445---"></a>Windows 10 cihazlar için ortak yönetim <!-- 1243445 -->
Ortak yönetim, geleneksel yönetimden modern yönetime bir köprü sağlar ve aşamalı bir yaklaşım ile bu geçişi yapmanızı sağlayan bir yol sunar. Ortak yönetim temelde Windows 10 cihazların, Configuration Manager ve Microsoft Intune tarafından eş zamanlı olarak yönetildiği ve Active Directory (AD) ile Azure Active Directory’ye (Azure AD) katıldığı bir çözümdür.  Bu yapılandırma size, her şeyi aynı anda taşıyamadığınız durumlarda kuruluşunuza uygun bir tempoda zaman içinde modernleştireceğiniz bir yol sunar.  

#### <a name="restrict-windows-enrollment-by-os-version----245498---"></a>Windows Kaydını işletim sistemi sürümüyle kısıtlama <!-- 245498 -->
Bir Intune yöneticisi olarak cihaz kayıtları için Windows 10 en düşük ve en yüksek sürümleri belirtebilirsiniz. Bu kısıtlamaları, **Platform Yapılandırmaları** dikey penceresinde ayarlayabilirsiniz.

Intune, Windows 8.1 bilgisayarlar ve telefonların kaydını desteklemeye devam edecektir. Ancak yalnızca Windows 10 sürümleri için en düşük ve en yüksek sınırlar ayarlanabilir. 8.1 cihazların kaydına izin vermek için en düşük sınırı boş bırakın.

#### <a name="alerts-for-windows-autopilot-unassigned-devices-----1631236---"></a>Windows AutoPilot’ta atanmamış cihazlar için uyarılar  <!-- 1631236 -->
**Microsoft Intune** > **Cihaz kaydı** > **Genel bakış** sayfasında Windows AutoPilot atanmamış cihazlar için yeni bir uyarı mevcut. Bu uyarı, AutoPilot programından kaç tane cihaza AutoPilot dağıtım profili atanmamış olduğunu gösterir. Uyarıdaki bilgileri kullanarak profiller oluşturun ve bunları profil atanmamış cihazlara atayın. Uyarıya tıkladığınızda, Windows AutoPilot cihazların tam listesini ve cihazlar hakkında ayrıntılı bilgileri görürsünüz. Daha fazla bilgi için bkz. [Windows AutoPilot dağıtım programını kullanarak Windows cihazları kaydetme](https://docs.microsoft.com/intune/enrollment-autopilot).

### <a name="device-management"></a>Cihaz yönetimi

#### <a name="refresh-button-for-devices-list-------1333581---"></a>Cihazlar listesi için Yenile düğmesi    <!-- 1333581 -->
Cihazlar listesi otomatik olarak yenilenmediği için, yeni Yenile düğmesini kullanarak listede görüntülenen cihazları güncelleyebilirsiniz.

#### <a name="support-for-symantec-cloud-certification-authority-ca-----1333638---"></a>Symantec Cloud Sertifika Yetkilisi (CA) desteği <!-- 1333638 -->    
Intune artık Symantec Cloud CA’yı desteklemektedir. Böylece Intune Sertifika Bağlayıcısı, Symantec Cloud’dan Intune ile yönetilen cihazlara PKCS sertifikaları verebilir. Intune Sertifika Bağlayıcısı’nı Microsoft Sertifika Yetkilisi (CA) ile kullanıyorsanız, Symantec CA desteğini eklemesi için mevcut Intune Sertifika Bağlayıcısı kurulumunu kullanabilirsiniz.

#### <a name="new-items-added-to-device-inventory-----1404455---"></a>Cihaz envanterine yeni öğeler eklendi   <!--1404455 -->
[Kayıtlı cihazların aldığı envanterde](device-inventory.md) artık aşağıdaki yeni öğeler kullanılabilir:

- WIFI Mac adresi
- Toplam depolama alanı
- Toplam boş alanı
- MEID
- Abone operatör


### <a name="app-management"></a>Uygulama yönetimi
#### <a name="set-access-for-apps-by-minimum-android-security-patch-on-the-device---1278463---"></a>Uygulamalara erişimi cihazdaki en düşük Android güvenlik düzeltme ekine göre ayarlama<!-- 1278463 -->   
Yönetici, yönetilen bir hesap altındaki yönetilen bir uygulamaya erişim kazanmak için cihazda yüklü olması gereken en düşük Android güvenlik düzeltme ekini belirleyebilir.

> [!Note]  
> Bu özellik, yalnızca Android 6.0+ cihazlarda Google tarafından yayınlanan düzeltme eklerini kısıtlar.

#### <a name="app-conditional-launch-support----1193313---"></a>Uygulama koşullu başlatma desteği <!-- 1193313 -->
Artık BT yöneticileri, uygulama başlatıldığında mobil uygulama yönetiminde (MAM) sayısal PIN yerine bir geçiş kodu kullanılmasını zorlamak için Azure yönetici portalında bir gereksinim ayarlayabilir. Bu gereksinim ayarlanırsa kullanıcının, MAM etkin uygulamalara erişim almadan önce bir geçiş kodu ayarlaması ve istendiğinde bunu kullanması gerekir. Geçiş kodu, en az bir özel karakter veya büyük/küçük harf içeren sayısal PIN’dir. Intune’un bu sürümünde bu özellik, **yalnızca iOS’ta** geçerli olacaktır. Intune, sayısal PIN’e benzer bir geçiş kodunu destekler, uzunluk alt sınırı belirler ve karakter ile dizi tekrarlarına izin verir. Bu özellik, Intune App SDK'yi hedef kod uygulamalarında uygulanacak parola ayarlarının yapılması için bu özelliğe ait kodla tümleştirmek için uygulamaların (WXP, Outlook, Managed Browser, Yammer) katılımını gerektirir.

#### <a name="app-version-number-for-line-of-business-in-device-install-status-report----1233999---"></a>Cihaz yükleme durum raporunda iş kolu için Uygulama Sürüm numarası <!-- 1233999 -->
Bu sürümle birlikte cihaz yükleme durum raporu, iOS ve Android için iş kolu uygulamalarında uygulama sürüm numarasını görüntüler. Bu bilgiyi kullanarak uygulamalarınızda sorun giderebilir veya eski uygulama sürümleri çalıştıran cihazları bulabilirsiniz.


### <a name="device-configuration"></a>Cihaz yapılandırması
#### <a name="admins-can-now-configure-the-firewall-settings-on-a-device-using-a-device-configuration-profile----951708---"></a>Yöneticiler artık bir cihazda cihaz yapılandırma profili kullanarak Güvenlik Duvarı ayarlarını yapılandırabilir <!-- 951708 -->   
Yöneticiler, cihazlar için güvenlik duvarını etkinleştirebilir ve etki alanı, özel ve ortak ağlar için çeşitli protokoller yapılandırabilir.  Bu güvenlik duvarı ayarlarını “Uç nokta koruma” profilinde bulabilirsiniz.

#### <a name="windows-defender-application-guard-helps-protect-devices-from-untrusted-websites-as-defined-by-your-organization----958257---"></a>Windows Defender Application Guard, cihazları kuruluşunuz tarafından belirlenen güvenilmeyen web sitelerinden korumaya yardımcı olur <!-- 958257 -->   
Yöneticiler, bir Windows Bilgi Koruması iş akışını veya cihaz yapılandırmaları altındaki yeni “Ağ sınırı” profilini kullanarak siteleri “güvenilir” veya “kurumsal” olarak tanımlayabilir. Bir 64 bit Windows 10 cihazın güvenilir ağ sınırında listelenmemiş tüm siteler, Microsoft Edge ile görüntülenmeleri durumunda bir Hyper-V sanal bilgisayarındaki tarayıcıda açılır.

Application Guard’ı, “Uç nokta koruma” profilindeki cihaz yapılandırma profillerinde bulabilirsiniz. Yöneticiler buradan, sanallaştırılmış tarayıcı ile konak makine, güvenilmeyen siteler ile güvenilir siteler ve sanallaştırılmış tarayıcıda oluşturulan verileri depolama arasındaki etkileşimi yapılandırabilir. Bir cihazda Application Guard’ı kullanmak için önce bir ağ sınırı yapılandırılmalıdır. Bir cihaz için yalnızca bir ağ sınırı tanımlamak önemlidir.  

#### <a name="windows-defender-application-control-on-windows-10-enterprise-provides-mode-to-trust-only-authorized-apps----1031096---"></a>Windows 10 Enterprise’da Windows Defender Uygulama Denetimi, yalnızca yetkilendirilmiş uygulamalara güvenme modu sağlar <!-- 1031096 -->    
Her gün oluşturulan binlerce yeni kötü amaçlı dosya karşısında virüsten koruma imza tabanlı algılama kullanmak artık yeni saldırılara karşı yeterli korumayı sağlayamıyor. Windows 10 Enterprise’da Windows Defender Uygulama Denetimi'ni kullanarak cihaz yapılandırmasını, uygulamaların bir virüsten koruma veya başka bir güvenlik çözümü tarafından engellenmediği durumda güvenilir olduğu bir moddan, işletim sisteminin yalnızca kuruluşunuzun yetkilendirdiği güvenilir uygulamalara güvendiği bir moda değiştirebilirsiniz. Uygulamalara güveni Windows Defender Uygulama Denetimi'nde atarsınız.

Intune kullanarak uygulama denetleme ilkelerini “yalnızca denetim” modunda veya zorlama modunda yapılandırabilirsiniz. Uygulamalar, “yalnızca denetim” modunda çalıştırıldığında engellenmez. “Yalnızca denetim” modu, tüm olayları yerel istemci günlüklerine kaydeder. Ayrıca, yalnızca Windows bileşenleri ve Microsoft Mağazası uygulamalarının mı yoksa Intelligent Security Graph tarafından tanımlanan diğer itibarlı uygulamaların da mı çalışmaya izni olacağını yapılandırabilirsiniz.

#### <a name="window-defender-exploit-guard-is-a-new-set-of-intrusion-prevention-capabilities-for-windows-10----1063615---"></a>Windows Defender Exploit Guard, Windows 10 için yeni bir yetkisiz erişim önleme işlevleri dizisi <!-- 1063615 -->   
Windows Defender Exploit Guard; uygulamaların kötüye kullanımını azaltacak özel kurallar içerir, makro ve betik tehditlerini önler, düşük itibarlı IP adreslerine yapılan ağ bağlantılarını otomatik olarak önler ve fidye yazılımı ile bilinmeyen tehditlere karşı verileri korur. Windows Defender Exploit Guard aşağıdaki bileşenlerden oluşur:

- **Saldırı Yüzeyi Azaltma (ASR)** makro, betik ve e-posta tehditlerini önlemenize yardımcı kurallar sağlar.
- **Denetimli Klasör erişimi** korumalı klasörlerin içeriklerine erişimi otomatik olarak engeller.
- **Ağ Filtresi** herhangi bir uygulamanın düşük itibarlı bir IP/etki alanına bağlantı yapmasını engeller
- **Exploit Protection** bir uygulamanın kötüye kullanılmasını önlemek üzere kullanılabilecek bellek, denetim akışı ve ilke kısıtlamaları sağlar.


#### <a name="manage-powershell-scripts-in-intune-for-windows-10-devices----790537---"></a>Windows 10 cihazlar için Intune’da PowerShell betiklerini yönetme <!-- 790537 -->

Intune yönetim uzantısı, Intune’da PowerShell betiklerini Windows 10 cihazlarda çalıştırmak için karşıya yüklemenize olanak sağlar. Uzantı, Windows 10 mobil cihaz yönetimi (MDM) özelliklerini tamamlar ve modern yönetime geçiş yapmanızı kolaylaştırır. Ayrıntılar için bkz. [Windows 10 cihazlar için Intune’da PowerShell betiklerini yönetme](intune-management-extension.md).

#### <a name="new-device-restriction-settings-for-windows-10---------1308850---"></a>Windows 10 için yeni cihaz kısıtlama ayarları      <!-- 1308850 -->
-    Mesajlaşma (yalnızca mobil) - sınamayı ve MMS iletilerini devre dışı bırakır
-    Parola - FIPS’yi ve kimlik doğrulaması için ikincil Windows Hello cihazların kullanımını etkinleştirme ayarları 
-    Görüntü - eski uygulamalar için GDI Ölçeklendirmeyi açma ve kapama ayarları

#### <a name="windows-10-kiosk-mode-device-restrictions----1308872---"></a>Windows 10 bilgi noktası modu cihaz kısıtlamaları <!-- 1308872 -->   
Windows 10 cihaz kullanıcılarını bilgi noktası moduna kısıtlayabilirsiniz, böylece kullanıcılar önceden tanımlı bir uygulamalar dizisiyle sınırlanır.  Bunun için bir Windows 10 cihaz kısıtlama profili oluşturun ve Bilgi Noktası ayarlarını ayarlayın.

Bilgi noktası modu şu iki modu destekler: **tek uygulama** (kullanıcının yalnızca bir uygulama çalıştırmasına izin verir) veya **çok uygulama** (bir dizi uygulamaya erişme izni verir).  Kullanıcı hesabı ve cihaz adını siz belirlersiniz, böylece desteklenen uygulamalar belirlenir.  Kullanıcı oturum açtığında belirlenen uygulamalarla sınırlı olur.  Daha fazla bilgi için bkz. [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp). 

Bilgi noktası modu şunları gerektirir:

- MDM yetkilisi Intune olmalıdır.
- Uygulamalar hedef cihazda yüklü olmalıdır.
- Cihaz [doğru bir şekilde sağlanmalıdır](https://docs.microsoft.com/windows/configuration/set-up-a-kiosk-for-windows-10-for-desktop-editions).

#### <a name="new-device-configuration-profile-for-creating-network-boundaries----1311967---"></a>Ağ sınırları oluşturmak için yeni cihaz yapılandırma profili <!-- 1311967 -->   
**Ağ sınırı** adı verilen yeni cihaz yapılandırma profilini diğer cihaz yapılandırma profillerinizin yanında bulabilirsiniz. Bu profili kullanarak kurumsal ve güvenilir olarak değerlendirilmesini istediğiniz çevrimiçi kaynakları tanımlayabilirsiniz. Windows Defender Application Guard ve Windows Bilgi Koruması gibi özelliklerin cihazda kullanılabilmesi için *önce* bir ağ sınırı tanımlamanız gerekir. Her cihaz için yalnızca bir ağ sınırı tanımlamanız önemlidir.

Güvenilir olarak değerlendirilmesini istediğiniz kuruluş bulut kaynakları, IP adresi aralıkları ve dahili proxy sunucularını tanımlayabilirsiniz. Tanımlandıktan sonra bu ağ sınırı, Windows Defender Application Guard ve Windows Bilgi Koruması gibi diğer özellikler tarafından kullanılır.

####  <a name="two-additional-settings-for-windows-defender-antivirus----1338409---"></a>Windows Defender Virüsten Koruma için iki ek ayar <!-- 1338409 -->  
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

#### <a name="citrix-vpn-added-for-windows-10-devices----1512457---"></a>Windows 10 cihazlar için Citrix VPN eklendi <!-- 1512457 -->  
Windows 10 cihazlar için Citrix VPN’i yapılandırabilirsiniz. Windows 10 ve üzeri sürümler için bir VPN yapılandırırken, **Temel VPN** dikey penceresinde bulunan *Bağlantı türü seçin* listesinden Citrix VPN’i seçebilirsiniz.

> [!Note]
> Citrix yapılandırması iOS ve Android için zaten mevcuttu.

#### <a name="wi-fi-connections-support-pre-shared-keys-on-ios----1550823---"></a>Wi-Fi bağlantıları iOS’ta önceden paylaşılan anahtarları destekliyor <!-- 1550823 -->
Müşteriler, Wi-Fi profillerini, iOS cihazlarda WPA/WPA2 Kişisel bağlantıları için önceden paylaşılan anahtarları (PSK) kullanacak şekilde yapılandırabilirler. Bu profiller, kullanıcının cihazı Intune’a kaydedildiğinde cihaza gönderilir.

Profil cihaza gönderildikten sonraki adım, profil yapılandırmasına bağlıdır.  Otomatik olarak bağlanmaya ayarlıysa, ağa ihtiyaç olduğunda otomatik olarak bağlanır.  Profil el ile bağlanıyorsa, kullanıcı bağlantıyı el ile etkinleştirmelidir.  

### <a name="intune-apps"></a>Intune uygulamaları

#### <a name="access-to-managed-app-logs-for-ios----1469920---"></a>iOS için yönetilen uygulama günlüklerine erişim <!-- 1469920 -->
Managed Browser yüklü olan son kullanıcılar artık tüm Microsoft uygulamalarının yönetim durumunu görüntüleyebilir ve yönetilen iOS uygulamalarında sorun giderme için günlük gönderebilirler.

Bir iOS cihaz üzerinde Managed Browser’da sorun giderme modunu nasıl etkinleştireceğini öğrenmek için bkz. [iOS’a Managed Browser kullanarak yönetilen uygulama günlüklerine erişme](app-configuration-managed-browser.md#how-to-access-to-managed-app-logs-using-the-managed-browser-on-ios).

#### <a name="improvements-to-device-setup-workflow-in-the-company-portal-for-ios-in-version-290----1417174---"></a>Sürüm 2.9.0'da iOS için Şirket Portalı'nda cihaz kurulum iş akışındaki iyileştirmeler <!-- 1417174 -->

iOS için Şirket Portalı uygulamasında cihaz kurulum iş akışı geliştirildi. Dil artık daha kullanıcı dostu ve mümkün olan yerlerde ekranları birleştirdik. Kurulum metninde şirket adınızın kullanılmasıyla diliniz, firmanıza özel hale geldi. Bu güncelleştirilmiş iş akışını  [Uygulama UI sayfasındaki yenilikler](whats-new-app-ui.md) sayfasında görebilirsiniz.

### <a name="monitor-and-troubleshoot"></a>İzleme ve sorun giderme

#### <a name="user-entity-contains-latest-user-data-in-data-warehouse-data-model----1544273---"></a>Kullanıcı varlığı Veri Ambarı veri modelinde en son kullanıcı verilerini içeriyor <!-- 1544273 -->
Intune Veri Ambarı eri modelinin ilk sürümü yalnızca son geçmiş Intune verilerini içeriyordu. Rapor oluşturucular bir kullanıcının geçerli durumunu yakalayamadı. Bu güncelleştirmede, **Kullanıcı varlığı** en son kullanıcı verileriyle doldurulur.


## <a name="notices"></a>Bildirimler


### <a name="coming-soon-workflow-updates-to-intune-administration-ui"></a>Yakında: Intune Yönetim Kullanıcı Arabirimine İş Akışı Güncelleştirmeleri

Intune, Mart hizmet sürümünde yönetici deneyimini güncelleştiriyor. Herhangi bir işlem yapmanız gerekmez, ancak Microsoft’un şeffaflık hakkındaki taahhüdünün bir parçası olan bu konu hakkında sizi bilgilendirmek istedik. Android veya Apple cihaz yönetimi etkinleştirildiğinde, Intune ilgili cihazları yönetmek üzere bu üçüncü taraf hizmetleriyle tümleştirme için cihaz ve kullanıcı bilgilerini gönderir. Mart hizmet sürümünde sunduğumuz gelişmiş kullanıcı arabirimi deneyimi, paylaşılan verilere daha fazla şeffaflık sağlayacaktır. Bu kullanıcı arabirimi değişikliklerinin son kullanıcı üzerinde etkisi yoktur.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?

Veri pencerelerini paylaşma onayı ekleyen senaryolar şunları içerir:
- Android for Work’u etkinleştirdiğinizde
- Apple MDM anında iletme sertifikalarını etkinleştirdiğinizde ve karşıya yüklediğinizde
- Aygıt Kayıt Programı, School Manager ve Volume Purchasing Program gibi Apple hizmetlerinden herhangi biri etkinleştirildiğinde

Her durumda onay, bir BT Yöneticisi'nin Google veya Apple cihazlarına kaydolma yetkisi verdiğini doğrulaması gibi, bir mobil cihaz yönetimi hizmetinin çalıştırılmasıyla ilgilidir. Yeni iş akışları yayınlandığında hangi bilgilerin paylaşıldığına ilişkin belgeler şu adreste bulunabilir:
- [Intune’un Google’a gönderdiği veriler](data-intune-sends-to-google.md)
- [Intune’un Apple’a gönderdiği veriler](data-intune-sends-to-apple.md)

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapmam gerek?

Bunlar küçük iş akışı kullanıcı arabirimi güncelleştirmeleri olduğundan, bu değişikliğe hazırlanmak için bir şey yapmanız gerekmez.
Microsoft’un GDPR uyumluluğu hakkında daha fazla bilgi için lütfen Ek Bilgiler bağlantısından erişilebilen Güven Merkezi'ne bakın.



### <a name="plan-for-change-update-where-you-configure-your-app-protection-policies"></a>Değişiklik Planı: Uygulama Koruma İlkelerinizi nerede yapılandırdığınızı güncelleştirme

Mart 2018’den itibaren sizi geçici olarak Azure portalında Intune Uygulama Koruma hizmeti dikey penceresinden Azure portalında Intune içerisindeki Mobil uygulama dikey penceresine yeniden yönlendireceğiz. Tüm Uygulama koruma ilkelerinizin zaten Intune’da uygulama yapılandırması altındaki Mobil uygulama dikey penceresinde olduğuna dikkat edin. Intune Uygulama Koruması yerine yalnızca Intune’a gideceksiniz. Nisan ayında bu yeniden yönlendirmeyi durduracak ve Intune Uygulama Koruma hizmeti dikey penceresini tamamen kaldıracağız çünkü bu, zaten artık Intune’da bulunan şeyin aynısı.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
Bu değişiklik, hem tek başına Intune müşterilerini hem de karma (Configuration Manager ile Intune) müşterileri etkileyecek. Bu tümleştirme, bulut yönetim idaresini basitleştirmenize yardımcı olacak. Böylece Azure’da grupları, ilkeleri, uygulamaları ve tüm mobil cihazları yönetmek için gitmeniz gereken yalnızca bir dikey pencere olacak (Intune dikey penceresi).

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapmam gerek?
Lütfen Intune Uygulama Koruması yerine Intune’u sık kullanılan olarak etiketleyin ve Intune içerisindeki Mobil uygulama dikey penceresinde bulunan Uygulama koruma ilkesi iş akışını inceleyin. Kısa bir süreliğine yenilen yönlendirme yapacağız ancak daha sonra Uygulama Koruma dikey penceresini kaldıracağız. Intune’da tüm Uygulama Koruma ilkelerine zaten son verildiğini ve tüm koşullu erişim ilkelerinizi şu belgeleri izleyerek değiştirebileceğinizi unutmayın: [https://aka.ms/azuread_ca](https://aka.ms/azuread_ca).

**Ek bilgiler**: [https://aka.ms/intuneapppolicy](https://aka.ms/intuneapppolicy)

### <a name="updated-new-security-enhancements-in-the-intune-service-----1637539---"></a>Güncelleştirildi: Intune hizmetinde yeni güvenlik geliştirmeleri <!-- 1637539 -->   

Intune hizmetinde güvenlik geliştirmelerini dağıtıyoruz. Bu değişikliğin bir parçası olarak Intune hizmetine yapılacak Mart güncelleştirmesi ile bu güvenlik özelliğini açıp kapatmak için Azure’da Intune konsolunda bir düğme bulunacak. Bu özellik açık olduğunda, kendisine hiçbir uyumluluk ilkesi atanmamış cihazlar “uyumlu değil” olarak işaretlenecek.

**Karma müşteriler**: Bu değişikliği henüz karma müşterilere sunmuyoruz. Herhangi bir eylemde bulunmanız gerekmiyor. Ancak cihazlarınıza en az bir uyumluluk ilkesi atanmış olduğundan emin olmanızı kesinlikle öneririz.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?

Bu değişikliği Mart güncelleştirmesinde dağıtmaya başladığımızda, uyumluluk ilkelerini atamış olup olmamanıza bağlı olarak bu değişiklik sizi farklı şekilde etkileyecek.

- Cihazlarına hiçbir uyumluluk ilkesi atanmamış yeni veya mevcut bir kiracıysanız, durum otomatik olarak **uyumlu** şeklinde ayarlanacaktır. Konsolda bu özellik, varsayılan olarak kapalı olacaktır. Son kullanıcılar bundan etkilenmeyecektir.
- Cihazlarına uyumluluk ilkesi atanmış mevcut bir kiracıysanız, durum otomatik olarak “uyumlu değil” şeklinde ayarlanacaktır. Özellik, Mart güncelleştirmesi dağıtıldığında varsayılan olarak açık olacaktır.

Uyumluluk ilkelerini Koşullu Erişim (CA) ile birlikte kullanıyorsanız ve bu özelliği açtıysanız, artık kendisine en az bir uyumluluk ilkesi atanmamış cihazlarınız CA tarafından engellenecektir. Bu cihazlarla ilişkili olup bu zamana kadar e-postaya erişme izni olan kullanıcılar, tüm cihazlara en az bir uyumluluk ilkesi atamadığınız sürece erişimlerini kaybedeceklerdir.   

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapmam gerek?  

Koşullu Erişim kullanıyorsanız, bu özelliği açmanızı ve durumu **Uyumlu değil** olarak ayarlamanızı öneririz. Son kullanıcılarınızın e-posta erişimini kaybetmemeleri için cihazlarınıza en az bir uyumluluk ilkesi atanmış olduğundan emin olun. Bunu yapmanıza yardımcı olmak için yaptığımız birkaç değişiklik var:   

- Intune portalında **Uyumluluk ilkesi olmayan cihazlar** adlı bir raporu kullanımınıza sunduk. Bu raporu kullanarak ortamınızda kendisine hiçbir uyumluluk ilkesi atanmamış cihazları belirleyebilirsiniz.
- Uyumluluk ilkesini tüm kullanıcılara atamanızı kolaylaştıran bir **Tüm Kullanıcılar** seçeneği mevcut.

Özelliği kapalı bırakmayı tercih ederseniz, başka hiçbir eylemde bulunmanıza gerek yoktur.

**Ek bilgiler**: [https://aka.ms/compliance_policies](https://aka.ms/compliance_policies)

### <a name="plan-for-change-change-in-support-for-the-microsoft-intune-app-sdk-for-cordova-plugin"></a>Değişiklik Planı: Cordova eklentisi için Microsoft Intune Uygulama SDK’sı desteğinde değişiklik
Intune, [Microsoft Intune Uygulama SDK’sı Cordova Eklentisi](app-sdk-cordova.md) için desteği 1 Mayıs 2018 tarihinde kesiyor. Cordova temelli uygulamalarınızı yönetilebilirlik ve kullanılabilirliğe hazırlamak için Intune Uygulama Sarmalama Aracı’nı kullanmanızı öneririz. Bu değişiklik gerçekleştiğinde, Cordova eklentisi için Microsoft Intune Uygulama SDK’sı artık bakıma alınmayacak veya güncelleştirme almayacak. Uygulama geliştiriciler bu eklentiyi kullanamayacaklar. Intune, Cordova ile oluşturulmuş uygulamaları desteklemeye devam etmeyi planlamaktadır. Ancak Cordova eklentisi için Microsoft Intune Uygulama SDK’sı ile oluşturulmuş uygulamalar Intune’da düşük işlevsellikle karşı karşıya kalabilir. Intune Uygulama Sarmalama Aracı ile sarmaladıktan sonra uygulamalar, normalde olduğu gibi son kullanıcılara dağıtılabilir. Google Play Store’a yayımlanmış Cordova temelli Android uygulamalar için:
- İlk başlatmada Intune ilkesi almak için kullanıcılardan kimlik bilgileri istenecek.
- Uygulamalar, uygulama mağazasına Intune kullanıcılarını hedefleyecek şekilde yayımlanmalıdır, örneğin “Intune için Contoso Uygulaması”.

Uygulama Sarmalama Aracı hakkında daha fazla bilgi için bkz. [iOS için Uygulama Sarmalama Aracı](app-wrapper-prepare-ios.md) ve [Android için Uygulama Sarmalama Aracı](app-wrapper-prepare-android.md). Herhangi bir soru veya sorununuz için [msintuneappsdk@microsoft.com](mailto:msintuneappsdk@microsoft.com) ile iletişime geçin.

### <a name="plan-for-change-use-intune-on-azure-now-for-your-mdm-management----1227338---"></a>Değişiklik Planı: Artık MDM yönetiminiz için Azure’da Intune kullanabilirsiniz <!-- 1227338 -->
Bir yılı aşkın bir süre önce [Azure’da Intune’un genel önizlemesini](https://cloudblogs.microsoft.com/enterprisemobility/2016/12/07/public-preview-of-intune-on-azure/) duyurup altı ay önce Intune için [yeni yönetici deneyiminin genel kullanılabilirliğini](https://cloudblogs.microsoft.com/enterprisemobility/2017/06/08/the-new-intune-and-conditional-access-admin-consoles-are-ga/) yayımlamıştık. 31 Ağustos 2018 itibarıyla, tek başına Intune kullanan müşteriler için klasik Silverlight konsolunda mobil cihaz yönetimini (MDM) kaldıracağız. Bunun yerine MDM ihtiyaçlarınız için [Azure’da Intune](https://aka.ms/Intune_on_Azure) kullanabilirsiniz. MDM için hala klasik konsolu kullanıyorsanız, lütfen bundan vazgeçin ve Azure üzerinden Intune kullanmaya alışın. Bu değişiklik ile hiçbir son kullanıcı etkisi beklemiyoruz. Klasik bilgisayar yönetimi Silverlight’ta kalacaktır. [Buraya](https://aka.ms/Intune_on_Azure_mdm) tıklayarak bu değişikliğin sizi nasıl etkileyeceği hakkında daha fazla bilgi alabilirsiniz.


### <a name="manage-android-for-work-devices-independently-from-android-devices----1490731-eeready--"></a>Android for Work cihazlarını Android cihazlardan ayrı olarak yönetme <!-- 1490731 EEready-->    
**Not**: Aşağıdaki değişiklikler, Kasım güncelleştirmesi ile dağıtılmaya başlanacaktır ancak hesabınızda yürürlüğe girmesi zaman alabilir. Bu değişiklikler hesabınızda geçerli olduğunda Office 365 portalında bir onay bildirimi alacaksınız. Dağıtım sonrasında, ek yönetilebilirlik seçeneklerine sahip olacaksınız. Dağıtım sırasında son kullanıcı deneyiminde hiçbir değişiklik olmayacak.

Intune, Android for Work cihazlarının Android platformundan bağımsız olarak kaydını yönetmeyi destekler. Bu ayarlar **Cihaz Kaydı** > **Kayıt kısıtlamaları** > **Cihaz Türü Kısıtlamaları** altında yönetilir. (Eskiden **Cihaz Kaydı** > **Android for Work Kaydı** > **Android for Work Kayıt Ayarları** altında bulunuyordu.)

Varsayılan olarak, Android for Work cihaz ayarlarınız Android cihazlarınız için ayarlarınızla aynı olacaktır. Ancak Android for Work ayarlarınızı değiştirdikten sonra artık bu durum oluşmaz.

Kişisel Android for Work kaydını engellerseniz, yalnızca kurumsal Android cihazlar Android for Work olarak kaydolabilir.

Yeni ayarlarla çalışırken şu noktaları göz önünde bulundurun:

#### <a name="if-you-have-never-previously-onboarded-android-for-work-enrollment"></a>Daha önce hiç Android for Work kaydı eklemediyseniz

Yeni Android for Work platformu varsayılan Cihaz Türü Kısıtlamalarında engellidir. Özelliği ekledikten sonra, cihazların Android for Work ile kaydolmasına izin verebilirsiniz. Bunu yapmak için varsayılan ayarı değiştirin veya varsayılan Cihaz Türü Kısıtlamasının yerine geçen yeni bir Cihaz Türü Kısıtlaması oluşturun.

#### <a name="if-you-have-onboarded-android-for-work-enrollment"></a>Android for Work kaydı eklediyseniz

Daha önceden eklediyseniz durumunuz seçtiğiniz ayara bağlıdır:

| Ayar | Varsayılan Cihaz Türü Kısıtlamasında Android for Work durumu | Notlar |
| --- | --- | --- |
| **Tüm cihazları Android olarak yönetme** | Engellendi | Tüm Android cihazların Android for Work ile kaydolması gerekir. |
| **Desteklenen cihazları Android for Work olarak yönetme** | İzin Verildi | Android for Work’ü destekleyen tüm Android cihazların Android for Work ile kaydolması gerekir. |
| **Yalnızca bu gruplardaki kullanıcılar için desteklenen cihazları Android for Work olarak yönetme** | Engellendi | Varsayılan ayarı geçersiz kılmak için ayrı bir Cihaz Türü Kısıtlama ilkesi oluşturuldu. Bu ilke önceden Android for Work kaydına izin vermek için seçtiğiniz grupları tanımlar. Seçili gruplardaki kullanıcıların Android for Work cihazlarını kaydetmesine izin verilir. Diğer tüm kullanıcıların Android for Work ile kaydolması kısıtlanır. |

Tüm durumlarda, hedeflenen düzenlemeniz korunur. Ortamınızda Android for Work’e genel olarak veya grup başına verilen izinleri tutmak için herhangi bir eylem gerçekleştirmeniz gerekmez.

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Apple kayıt senaryolarına doğrudan erişim <!--951869-->
Intune, Azure portalındaki Cihaz Kaydetme iş yükünü kullanarak Apple kayıt senaryolarına doğrudan erişimi Ocak 2017 sonrasında oluşturulan Intune hesapları için etkinleştirdi. Daha önce, Apple kayıt önizleme sürümüne yalnızca klasik Intune portalı bağlantıları ile erişilebiliyordu. Bu özelliklerin Azure’da kullanılabilmesi için Ocak 2017 öncesi oluşturulan Intune hesaplarında tek seferlik bir geçiş yapılması gerekir. Geçiş için zaman çizelgesi henüz açıklanmamıştır, ancak konuya ilişkin ayrıntılar olabildiğince çabuk duyurulacaktır. Mevcut hesabınız Azure portalına erişemiyorsa yeni deneyimi sınamak için bir deneme hesabı oluşturmanızı kesinlikle öneririz.

## <a name="whats-coming"></a>Yakında

### <a name="new-user-experience-update-for-the-company-portal-website---2000968--"></a>Şirket Portalı web sitesi için yeni kullanıcı deneyimi güncelleştirmesi <!--2000968-->

Kullanıcı arabirimi güncelleştirmeleri, kolaylaştırılmış iş akışları ve erişilebilirlik iyileştirmeleri içeren bir Şirket Portalı web sitesi deneyimini Nisan ayında tanıtacağız. Bunun içerisinde, size daha kullanıcı dostu bir deneyim sunmak için uygulama paylaşımı ve iyileştirilmiş genel performans gibi müşteri odaklı iyileştirmeler olacak.
Sizin gibi müşterilerden aldığımız geri bildirimlere dayanarak bazı yeni özellikler ekledik. Bu özellikler, geçerli işlevsellik ve kullanılabilirliği büyük oranda artıracak:

-   Web sitesi üzerinde kullanıcı arabirimi iyileştirmeleri
-   Doğrudan uygulama bağlantıları paylaşabilme seçeneği
- Büyük uygulama katalogları için iyileştirilmiş performans

Bu değişikliğe hazırlanmak için herhangi bir şey yapmanız gerekmez. Güncelleştirilmiş Şirket Portalı web sitesi kullanılabilir duruma geldiğinde size haber vereceğiz. Ancak daha sonra son kullanıcı belgelerini güncel ekran görüntüleriyle güncelleştirmeniz gerekebilir. iOS uygulamasının **Uygulamalar** bölümü web sitesi tarafından sağlandığı için iOS’ta Şirket Portalı belgelerini de güncelleştirmeniz gerekebileceğine dikkat edin. [Uygulama kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md) sayfasında bunun için bir örnek görüntü görebilirsiniz.

### <a name="user-experience-update-for-the-company-portal-app-for-ios---1412866--"></a>iOS için Şirket Portalı uygulamasında kullanıcı deneyimi güncelleştirmesi <!--1412866-->

iOS için Şirket Portalı uygulamasına büyük bir kullanıcı deneyimi güncelleştirmesi yayımlayacağız. Bu güncelleştirmede, artırılmış kullanılabilirlik ve erişim ile modern bir görüntü ve his veren baştan aşağı yeni bir görsel tasarım yer alacak. Tüm mevcut iOS Şirket Portalı işlevselliği korunacaktır.

Güncelleştirilmiş iOS için Şirket Portalı uygulamasını kullanıp geri bildirimde bulunmanız için Apple TestFlight programı aracılığıyla uygulamanın yayın öncesi sürümünü sunuyoruz. TestFlight erişimi için https://aka.ms/intune_ios_cp_testflight adresinde kaydolun. Bu güncelleştirme hakkında son bilgiler için bkz. https://aka.ms/iOS_companyportal_update.

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple, Uygulama Taşıma Güvenliği için güncelleştirmeler gerektirecek <!--748318-->
Apple, Uygulama Taşıma Güvenliği (ATS) için belirli gereksinimler uygulayacağını açıkladı. ATS, HTTPS üzerinden yapılan tüm uygulama iletişimlerinde daha sıkı güvenlik uygulamak için kullanılır. Bu değişiklik, iOS Şirket Portalı uygulamaları kullanan Intune müşterilerini etkiler.

Yeni ATS gereksinimlerinin kullanılmasını zorunlu kılan Apple TestFlight programı aracılığıyla iOS için Şirket Portalı uygulamasının yeni bir sürümünü kullanıma sunduk. ATS uyumluluğunuzu sınamak için bunu denemek isterseniz, adınızı, soyadınızı, e-posta adresinizi ve şirketinizin adını e-posta ile <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app">CompanyPortalBeta@microsoft.com</a> adresine gönderin. Daha fazla ayrıntı için bkz. [Intune destek blogu](https://aka.ms/compportalats).

## <a name="see-also"></a>Ayrıca bkz:
* [Microsoft Intune Blogu](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Cloud Platform yol haritası](https://www.microsoft.com/cloud-platform/roadmap)
* [Şirket Portalı kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md)
* [Önceki aylardaki yenilikler](whats-new-archive.md)
