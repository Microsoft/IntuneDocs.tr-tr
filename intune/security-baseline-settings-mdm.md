---
title: Windows 10 için Intune güvenlik temelleri ayarları
titleSuffix: Microsoft Intune
description: Intune ile yönettiğiniz Windows 10 cihazları için Windows MDM güvenlik taban çizgisinde bulunan Varsayılanları ve kullanılabilir ayarları gözden geçirin.
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/25/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5565ce7a355136a749d79b52e4830af91684440a
ms.sourcegitcommit: 864fdf995c2b41f104a98a7e2665088c2864774f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/31/2019
ms.locfileid: "68680033"
---
# <a name="mdm-security-baseline-settings-for-intune"></a>Intune için MDM güvenlik taban çizgisi ayarları  

Windows 10 veya üstünü çalıştıran cihazlar için Microsoft Intune tarafından desteklenen MDM güvenlik temeli ayarlarını görüntüleyin. Bu temeldeki ayarların varsayılan değerleri, uygulanabilir cihazlar için önerilen yapılandırmayı temsil eder ve diğer güvenlik temellerinden temel varsayılan varsayılanlar ile eşleşmeyebilir.  

2019 Mayıs 'un en son temel sürümü **MDM güvenlik temeliyle**  

Önceki sürümden bu taban çizgisinin en son sürümünde nelerin değiştirildiğini öğrenmek için, bkz. [yeni şablondaki değiştirilme öğeleri](#whats-changed-in-the-new-template).  

> [!NOTE]  
> Haziran 2019 ' de, MDM güvenlik taban çizgisi, genel kullanıma sunulan (önizlemede değil) *mayıs 2019 şablonu Için MDM güvenlik temeli* sürümü ile değiştirilmiştir. *Mayıs 2019 temeli Için MDM güvenlik temelinin* kullanılabilirliği öncesinde oluşturulan profiller, Mayıs 2019 sürümü Için MDM güvenlik temelindeki ayarları ve değerleri yansıtacak şekilde güncellemeyebilir.  Önizleme şablonunu temel alan yeni profiller oluşturmasanız da, önizleme şablonunu temel alan daha önce oluşturduğunuz profilleri düzenleyebilir ve kullanmaya devam edebilirsiniz.   
  
Intune ile güvenlik temellerini kullanma hakkında bilgi edinmek için bkz. [güvenlik temellerini kullanma](security-baselines.md).  


   
## <a name="above-lock"></a>Kilidin üstünde  
Daha fazla bilgi için Windows belgelerindeki [POLICY CSP-AboveLock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-abovelock) bölümüne bakın.  

- **Bildirim bildirimlerinin görüntülenmesini engelle**  
  Bu ilke ayarı, uygulama bildirimlerinin kilit ekranında görüntülenmesini engellemenizi sağlar. Bu ilke ayarını etkinleştirirseniz, kilit ekranında hiçbir uygulama bildirimi gösterilmez. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, kullanıcılar hangi uygulamaların kilit ekranında bildirim görüntülemesini seçebilirler.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067101)  

  **Varsayılan**: Evet  

- **Uygulamaları kilitli ekrandan etkinleştir**  

  **Varsayılan**: Devre dışı

## <a name="app-runtime"></a>Uygulama çalışma zamanı    
Daha fazla bilgi için Windows [belgelerindeki ilke CSP-appruntime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-appruntime
) bölümüne bakın.  

- **Microsoft hesapları Windows Mağazası uygulamaları için isteğe bağlı**  
  Bu ilke ayarı, Microsoft hesaplarının bir hesabının oturum açmasını gerektiren Windows Mağazası uygulamaları için isteğe bağlı olup olmadığını denetlemenize olanak tanır. Bu ilke yalnızca bunu destekleyen Windows Mağazası uygulamalarını etkiler. Bu ilke ayarını etkinleştirirseniz, genellikle oturum açmak için bir Microsoft hesabı gerektiren Windows Mağazası uygulamaları, kullanıcıların bunun yerine bir kurumsal hesapla oturum açmalarına olanak tanır. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, kullanıcıların bir Microsoft hesabı oturum açması gerekir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067104)  
  
  **Varsayılan**: Enabled  

## <a name="application-management"></a>Uygulama yönetimi   
Daha fazla bilgi için Windows belgelerindeki [Ilke CSP-ApplicationManagement](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement) bölümüne bakın.  

- **Yüklemeler üzerinde kullanıcı denetimini engelle**  
  Bu ilke ayarı, kullanıcıların genellikle sistem yöneticileri tarafından kullanılabilen yükleme seçeneklerini değiştirmesine izin verir. Bu ilke ayarını etkinleştirirseniz, Windows Installer güvenlik özelliklerinden bazıları atlanır. Bu, yüklemelerin tamamlanmasına izin verir, aksi takdirde bir güvenlik ihlali nedeniyle durdurulur. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, Windows Installer güvenlik özellikleri, kullanıcıların sistem yöneticileri için tipik olarak ayrılmış yükleme seçeneklerini değiştirmelerini engeller (örneğin, dosyaların yüklendiği dizini belirtme). Windows Installer bir yükleme paketinin kullanıcının korumalı bir seçeneği değiştirmesine izin verdiğini algılarsa, yüklemeyi sonlandırır ve bir ileti görüntüler. Bu güvenlik özellikleri yalnızca, yükleme programı Kullanıcı tarafından reddedilen dizinlere erişimi olan ayrıcalıklı bir güvenlik bağlamında çalışırken çalışır. Bu ilke ayarı, daha az kısıtlayıcı ortamlar için tasarlanmıştır. Bu, yazılımın yüklenmesini önleyen bir yükleme programındaki hataları aşmak için kullanılabilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067060)  

  **Varsayılan**: Evet

- **Yükseltilmiş ayrıcalıklarla MSI uygulama yüklemelerini engelleyin**  
  Bu ilke ayarı, sisteme herhangi bir program yüklediğinde Windows Installer yükseltilmiş izinleri kullanmak üzere yönlendirir.  
  - *Bu ilke ayarını etkinleştirirseniz*, ayrıcalıklar tüm programlara genişletilir. Bu ayrıcalıklar genellikle kullanıcıya atanan (masaüstünde sunulan), bilgisayara atanan (otomatik olarak yüklenir) f veya Denetim Masası 'ndaki Program Ekle/Kaldır bölümünde kullanılabilir olan programlar için ayrılmıştır. Bu profil ayarı, kullanıcıların, son derece kısıtlanmış bilgisayarlardaki dizinler dahil olmak üzere, Kullanıcı tarafından görüntüleme veya değiştirme iznine sahip olmadığı dizinlere erişim gerektiren programları yüklemesine olanak sağlar.
  - *Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız*, sistem yöneticisinin dağıtmayacağı veya sunmayacağı programları yüklediğinde, sistem geçerli kullanıcının izinlerini uygular. Not: Bu ilke ayarı, bilgisayar yapılandırması ve Kullanıcı Yapılandırması klasörlerinde görüntülenir. Bu ilke ayarının etkili olması için, her iki klasörde da etkinleştirmeniz gerekir. Dikkatli Nitelikli kullanıcılar, bu ilke ayarının ayrıcalıklarını değiştirme ve kısıtlanmış dosya ve klasörlere kalıcı erişim elde etmesine izin verdiği izinlerden yararlanabilir. Bu ilke ayarının Kullanıcı Yapılandırması sürümünün güvenli olduğu garanti edilmez.  
  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067134)    

  **Varsayılan**: Evet

- **Oyun DVR 'ı engelle (yalnızca masaüstü)**  
  Oyunları kaydetmeye ve yayına izin verilip verilmeyeceğini yapılandırır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067056)  
  
  **Varsayılan**: Evet  

## <a name="auto-play"></a>Otomatik Yürüt   
Daha fazla bilgi için bkz. [Ilke CSP-Windows belgelerinde otomatik kullan](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-autoplay) .  

- **Varsayılan otomatik çalıştırma davranışını Otomatik Yürüt**  
  Bu ayar Autorun komutlarının varsayılan davranışını etkiler. Autorun komutları Autorun. inf dosyalarında depolanır ve yükleme programlarını veya diğer yordamları başlatabilir. *Etkinleştirildiğinde*Yöneticiler, Windows Vista veya üstünü çalıştıran bir cihazda varsayılan otomatik çalıştırma davranışını değiştirebilir. Davranış: a), otomatik çalıştırma komutunu otomatik olarak yürüten Windows Vista öncesi davranışına geri dönmek için şu şekilde ayarlanabilir: a). *Devre dışı* veya *yapılandırılmamış*olarak ayarlandığında, Windows Vista veya sonraki bir sürümü çalıştıran cihazlar kullanıcıdan bir otomatik çalıştırma komutunun çalıştırılıp çalıştırılmayacağı konusunda bilgi ister.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067133)       
  
  **Varsayılan**: Yürütme  
  
- **Otomatik yürütme modu**  
  Bu ilke ayarı, Otomatik Kullan özelliğini kapatmanıza olanak sağlar. Otomatik yürütme, sürücüye medya eklediğiniz andan itibaren bir sürücüden okumaya başlar. Sonuç olarak, programların kurulum dosyası ve ses medyasındaki müzikler hemen başlar. Windows XP SP2 'den önce, otomatik kullan, disket sürücüsü (CD-ROM sürücüsü değil) ve ağ sürücülerinde varsayılan olarak çıkarılabilir sürücülerde devre dışıdır. Windows XP SP2 'den başlayarak, Zip sürücüleri ve bazı USB yığın depolama cihazları dahil olmak üzere, Otomatik Çalıştır, çıkarılabilir sürücüler için de etkinleştirilir. Bu ilke ayarını etkinleştirirseniz, otomatik kullan, CD-ROM ve çıkarılabilir medya sürücülerinde devre dışıdır veya tüm sürücülerde devre dışı bırakılır. Bu ilke ayarı, ek sürücü türlerinde Otomatik yürütmeyi devre dışı bırakır. Bu ayarı, varsayılan olarak devre dışı bırakılmış sürücülerde otomatik olarak etkinleştirmek için kullanamazsınız. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, Otomatik Kullan özelliği etkinleştirilir. Not: Bu ilke ayarı, bilgisayar yapılandırması ve Kullanıcı Yapılandırması klasörlerinde görüntülenir. İlke ayarları çakışıyorsa, bilgisayar yapılandırması 'ndaki ilke ayarı, Kullanıcı Yapılandırması 'ndaki ilke ayarından önce gelir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2066793)  
  
  **Varsayılan**: Devre dışı

- **Birim olmayan cihazlar için otomatik yürütmeye engel**  
  Bu ilke ayarı, kamera veya telefon gibi MTP cihazları için otomatik olarak izin vermez. Bu ilke ayarını etkinleştirirseniz, kamera veya telefon gibi MTP cihazları için otomatik etkinleştirmeye izin verilmez. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, otomatik kullan, birim olmayan cihazlar için etkinleştirilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067106)    
  
  **Varsayılan**: Enabled  

## <a name="bitlocker"></a>Kurulumu    
Daha fazla bilgi için Windows [belgelerindeki ilke CSP-](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bitlocker
) BitLocker bölümüne bakın.  

- **Bit dolabı çıkarılabilir sürücü ilkesi**  
  Bu ilke ayarı, şifreleme yöntemini ve şifre gücünü denetlemek için kullanılır. Bu ilkenin değerleri BitLocker 'ın şifreleme için kullandığı şifre gücünü belirlemektir. Kuruluşlar, artırılmış güvenlik için şifreleme düzeyini denetlemek isteyebilir (AES-256, AES-128 ' den daha güçlüdür). Bu ayarı etkinleştirirseniz, sabit veri sürücüleri, işletim sistemi sürücüleri ve çıkarılabilir veri sürücüleri için şifreleme algoritması ve anahtar şifreleme gücünü ayrı ayrı yapılandırabileceksiniz. Sabit ve işletim sistemi sürücüleri için, XTS-AES algoritmasını kullanmanızı öneririz. Sürücü, Windows 10, sürüm 1511 veya üzerini çalıştırmayan diğer cihazlarda kullanılıyorsa, çıkarılabilir sürücüler için AES-CBC 128-bit veya AES-CBC 256-bit ' i kullanmanız gerekir. Sürücü zaten şifrelendiyse veya şifreleme devam ediyorsa şifreleme yönteminin değiştirilmesi etkisizdir. Bu durumlarda, bu ilke ayarı yok sayılır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067140) 

  Bit dolabı çıkarılabilir sürücü ilkesi için aşağıdaki ayarı yapılandırın:

  - **Yazma erişimi için şifreleme gerektir**  
    **Varsayılan**: Evet  
  

## <a name="browser"></a>Browser  
Daha fazla bilgi için Windows belgelerindeki [Ilke CSP-Browser](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser) bölümüne bakın.  

- **Microsoft Edge için SmartScreen gerektir**  
  Microsoft Edge, kullanıcıların olası kimlik avı dolandırıcılarından ve kötü amaçlı yazılımlardan varsayılan olarak korunmasını sağlamak için Windows Defender SmartScreen (açık) kullanır. Ayrıca, kullanıcılar varsayılan olarak Windows Defender SmartScreen 'i devre dışı bırakamıyorum (kapatamaz). Bu ilkeyi etkinleştirmek, Windows Defender SmartScreen 'i kapatır ve kullanıcıların bunu açmasını önler. Kullanıcıların Windows Defender SmartScreen 'i açmayı veya kapatmayı seçmesini sağlamak için bu ilkeyi yapılandırmayın.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067029)   
  
  **Varsayılan**: Evet  
  
- **Kötü amaçlı Site erişimini engelleyin**  
  Varsayılan olarak, Microsoft Edge, kullanıcıların olası kötü amaçlı siteler hakkındaki Windows Defender SmartScreen uyarılarını atlamasına (yoksaymasına) izin verir ve siteye devam etmesine olanak tanır. Bu ilkeyle, Microsoft Edge 'i kullanıcıların uyarıları atlamasını önleyecek ve siteye devam etmesini engelleyecek şekilde yapılandırabilirsiniz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067040)   
  
  **Varsayılan**: Evet  
  
- **Doğrulanmamış dosya indirmeyi engelle**  
  Varsayılan olarak, Microsoft Edge, kullanıcıların, zararlı olabilecek dosyalarla ilgili Windows Defender SmartScreen uyarılarını atlamasına (yoksaymasına) izin verir ve bu da doğrulanmamış dosyaları indirmeye devam edebilir. Bu ilkeyi etkinleştirmek, kullanıcıların, doğrulanmamış dosya (ler) i indirmelerini engelleyerek uyarıları atlamasını engeller.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067023)  
  
  **Varsayılan**: Evet  
  
- **Parola yöneticisini engelle**  
  Varsayılan olarak, Microsoft Edge parola Yöneticisi 'ni otomatik olarak kullanarak kullanıcıların parolalarını yerel olarak yönetici yapmasına izin verir. Bu ilkeyi devre dışı bırakmak Microsoft Edge 'in parola Yöneticisi 'Ni kullanmasını kısıtlar. Kullanıcıların parola Yöneticisi 'Ni kullanarak parolaları yerel olarak kaydedip yönetmesine izin vermek istiyorsanız bu ilkeyi yapılandırmayın.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067128)  
  
  **Varsayılan**: Evet  
  
- **Sertifika hatası geçersiz kılmalarını engelle**  
  Bu ilke ayarı, Internet Explorer 'da kullanıcının taramayı kesintiye uğratan Güvenli Yuva Katmanı/Aktarım Katmanı Güvenliği (SSL/TLS) sertifika hatalarını ("süre dolduğunda", "iptal edildi" veya "ad uyuşmazlığı" hataları) yok saymasını engeller. Bu ilke ayarını etkinleştirirseniz Kullanıcı göz atmaya devam edebilir. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, Kullanıcı sertifika hatalarını yoksaymayı ve gözatmaya devam etmeyi tercih edebilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067126)  
  
  **Varsayılan**: Evet  

## <a name="connectivity"></a>Bağlantı  
Daha fazla bilgi için Windows belgelerindeki [Ilke CSP-bağlantı](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity) bölümüne bakın.  

- **Web yayımı ve çevrimiçi sipariş sihirbazları için Internet 'ten indirmeyi engelleyin**  
  Bu ilke ayarı, Windows 'un Web yayımı ve çevrimiçi sipariş sihirbazları için sağlayıcı listesini indirip indirmeyeceğini belirtir. Bu sihirbazlar, kullanıcıların çevrimiçi depolama ve fotoğraf baskısı gibi hizmetler sağlayan şirketler listesinden seçmesine olanak sağlar. Varsayılan olarak, Windows, kayıt defterinde belirtilen sağlayıcılara ek olarak Windows Web sitesinden indirilen sağlayıcıları görüntüler. Bu ilke ayarını etkinleştirirseniz, Windows sağlayıcıları indirmez ve yalnızca yerel kayıt defterinde önbelleğe alınan hizmet sağlayıcılarını görüntüler. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, Kullanıcı Web yayımlaması veya çevrimiçi sıralama sihirbazları kullandığında bir sağlayıcı listesi indirilir. Kayıt defterindeki hizmet sağlayıcılarının belirtilmesine ilişkin ayrıntıları içeren daha fazla bilgi için, Web yayımı ve çevrimiçi sipariş sihirbazları belgelerine bakın.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067136)  
  
  **Varsayılan**: Enabled  

- **HTTP üzerinden yazdırma sürücülerinin indirilmesini engelle**  
  Bu ilke ayarı, bu istemcinin HTTP üzerinden yazıcı sürücüsü paketleri indirmesine izin verilip verilmeyeceğini belirtir. HTTP yazdırmayı ayarlamak için, gelen kutusu olmayan sürücülerin HTTP üzerinden indirilmesi gerekir. Not: Bu ilke ayarı, istemcinin Intranetteki yazıcılara veya HTTP üzerinden Internet üzerinden yazdırmasını engellemez. Yalnızca yerel olarak yüklü olmayan sürücülerin indirilmesini yasaklar. Bu ilke ayarını etkinleştirirseniz, yazıcı sürücüleri HTTP üzerinden indirilemez. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız kullanıcılar, yazıcı sürücülerini HTTP üzerinden indirebilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067141)  
  
  **Varsayılan**: Enabled  

## <a name="credentials-delegation"></a>Kimlik bilgileri temsili  
Daha fazla bilgi için Windows [belgelerindeki ilke CSP-credentialstemsilciliğini](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-credentialsdelegation
) inceleyin.  

- **Dışarı aktarılabilir olmayan kimlik bilgilerinin uzak ana bilgisayar temsili**  
  Uzak ana bilgisayar, dışarı aktarılabilir olmayan kimlik bilgilerinin temsilciliğini sağlar. Kimlik bilgileri temsilcisini kullanırken, cihazlar uzak ana bilgisayara kimlik bilgilerinin dışa aktarılabilir bir sürümünü sağlar ve bu da kullanıcıları uzak ana bilgisayardaki saldırganlar tarafından kimlik bilgilerinin hırsızlık riskini gösterir. Bu ilke ayarını etkinleştirirseniz, ana bilgisayar kısıtlı yönetici veya uzak Credential Guard modunu destekler. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, kısıtlı yönetim ve uzak Credential Guard modu desteklenmez. Kullanıcının kimlik bilgilerini her zaman konağa geçirmesi gerekir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067103)   
  
  **Varsayılan**: Enabled  

## <a name="credentials-ui"></a>Kimlik bilgileri kullanıcı arabirimi  
Daha fazla bilgi için Windows belgelerindeki [Ilke CSP-CredentialsUI](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-credentialsui) bölümüne bakın.  

- **Yöneticileri listeleme** Bu ilke ayarı, bir Kullanıcı çalışan bir uygulamayı yükseltmeyi denediğinde yönetici hesaplarının görüntülenip görüntülenmeyeceğini denetler. Varsayılan olarak, Kullanıcı çalışan bir uygulamayı yükseltmeyi denediğinde yönetici hesapları görüntülenmez. Bu ilke ayarını etkinleştirirseniz, BILGISAYARDAKI tüm yerel yönetici hesapları kullanıcının hesabı seçmesini ve doğru parolayı girebilmesini sağlayacak biçimde görüntülenir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcıların yükseltmek için her zaman bir Kullanıcı adı ve parola yazmanız gerekir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067021)

  
  **Varsayılan**: Devre dışı  

## <a name="data-protection"></a>Veri Koruma  
Daha fazla bilgi için Windows [belgelerindeki ilke CSP-DataProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dataprotection
) bölümüne bakın.  

- **Doğrudan bellek erişimini engelle**  
  Bu ilke ayarı, bir Kullanıcı Windows 'a oturum açana kadar, tüm etkin takılabilir PCI akış bağlantı noktaları için doğrudan bellek erişimini (DMA) engellemenizi sağlar. Kullanıcı oturum açtıktan sonra Windows, ana bilgisayar eklentisi PCI bağlantı noktalarına bağlı PCI cihazlarını numaralandırır. Kullanıcı makineyi her kilitlediğinde, Kullanıcı yeniden oturum açana kadar alt cihazları olmayan hot plug PCI bağlantı noktalarında DMA engellenir. Makine kilidi açıldığında zaten numaralandırılan cihazlar, söküle kadar çalışmaya devam eder. Bu ilke ayarı yalnızca BitLocker veya cihaz şifrelemesi etkinleştirildiğinde zorlanır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067031)     
  
  **Varsayılan**: Evet  

## <a name="device-guard"></a>Device Guard  
Daha fazla bilgi için Windows [belgelerindeki ilke CSP-deviceguard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceguard
) bölümüne bakın.  

- **Credential Guard**  
  Bu ayar, kullanıcıların bir sonraki yeniden başlatmada kimlik bilgilerini korumaya yardımcı olmak üzere sanallaştırma tabanlı güvenlik ile Credential Guard 'ı kapatmasına olanak sağlar.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067044)
   
  **Varsayılan**: UEFı kilidi ile etkinleştir 

- **Sanallaştırma tabanlı güvenliği etkinleştir**   
  Bir sonraki yeniden başlatmada sanallaştırma tabanlı güvenliği (VBS) açar. Sanallaştırma tabanlı güvenlik, güvenlik hizmetlerine destek sağlamak için Windows Hiper Yöneticisi'ni kullanır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067066)  
  
  **Varsayılan**: Evet  


- **System Guard 'ı Başlat**    
  **Varsayılan**: Enabled  

## <a name="device-installation"></a>Cihaz yüklemesi  
Daha fazla bilgi için Windows belgelerindeki [Ilke CSP-Deviceınstallation](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceinstallation) bölümüne bakın.  

- **Cihaz tanımlayıcılarına göre donanım cihazı yüklemesi**  
  Bu ilke ayarı, Windows 'un yüklemesi engellenen cihazlar için Tak ve Kullan donanım kimliklerinin ve uyumlu kimliklerin bir listesini belirtmenizi sağlar. Bu ilke ayarı, Windows 'un bir cihaz yüklemesine izin veren diğer tüm ilke ayarlarından önceliklidir. Bu ilke ayarını etkinleştirirseniz, Windows 'un, oluşturduğunuz listede donanım KIMLIĞI veya uyumlu KIMLIĞI görünen bir cihaz yüklemesi engellenir. Uzak Masaüstü sunucusunda bu ilke ayarını etkinleştirirseniz, ilke ayarı, belirtilen cihazların uzak masaüstü istemcisinden uzak masaüstü sunucusuna yönlendirilmesini etkiler. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, cihazlar diğer ilke ayarları tarafından izin verilen veya engellenen şekilde yükleyebilir ve güncelleştirebilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2066794)  
  
  **Varsayılan**: Donanım cihazını yüklemeyi engelle  

  *Donanım aygıtı yüklemesi engellenme* seçildiğinde aşağıdaki ayarlar kullanılabilir.

  - **Eşleşen donanım cihazlarını kaldırma**   
    Bu ayar yalnızca *cihaz tanımlayıcılarına göre donanım cihaz yüklemesi* , *donanım cihazı yüklemeyi engelleyecek*şekilde ayarlandığında kullanılabilir.
    
    **Varsayılan**: Evet

  - **Engellenen donanım cihaz tanımlayıcıları**  
    Bu ayar yalnızca *cihaz tanımlayıcılarına göre donanım cihaz yüklemesi* , *donanım cihazı yüklemeyi engelleyecek*şekilde ayarlandığında kullanılabilir.
    
    **Varsayılan**: Evet  
  
- **Kurulum sınıflarına göre donanım cihaz yüklemesi**  
  Bu ilke ayarı, Windows 'un yüklemesi engellenen cihaz sürücüleri için cihaz kurulum sınıfının genel benzersiz tanımlayıcıları (GUID 'Ler) listesini belirtmenizi sağlar. Bu ilke ayarı, Windows 'un bir cihaz yüklemesine izin veren diğer tüm ilke ayarlarından önceliklidir. Bu ilke ayarını etkinleştirirseniz, Windows 'un, cihaz kurulum sınıfı GUID 'Leri oluşturduğunuz listede göründüğü cihaz sürücülerini yüklemesi veya güncelleştirmesi engellenir. Uzak Masaüstü sunucusunda bu ilke ayarını etkinleştirirseniz, ilke ayarı, belirtilen cihazların uzak masaüstü istemcisinden uzak masaüstü sunucusuna yönlendirilmesini etkiler. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, Windows, diğer ilke ayarları tarafından izin verilen veya engellenen cihazları yükleyebilir ve güncelleştirebilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067048)  
  
  **Varsayılan**: Donanım cihazını yüklemeyi engelle  

  *Donanım aygıtı yüklemesi engellenme* seçildiğinde aşağıdaki ayarlar kullanılabilir.
  - **Eşleşen donanım cihazlarını kaldırma**    
    Bu ayar yalnızca, *kurulum sınıfları tarafından sağlanan donanım cihaz yüklemesi* , *donanım cihazı yüklemeyi engelleyecek*şekilde ayarlandığında kullanılabilir.  

    **Varsayılan**: *Varsayılan yapılandırma yok*  

  - **Engellenen donanım cihaz tanımlayıcıları**  
    Bu ayar yalnızca, *kurulum sınıfları tarafından sağlanan donanım cihaz yüklemesi* , *donanım cihazı yüklemeyi engelleyecek*şekilde ayarlandığında kullanılabilir.
    
    **Varsayılan**: *Varsayılan yapılandırma yok*  

## <a name="device-lock"></a>Cihaz kilidi  
Daha fazla bilgi için Windows belgelerindeki [POLICY CSP-DeviceLock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock) bölümüne bakın.  

- **Kameranın kullanımını engelle**  
  BILGISAYAR ayarlarındaki kilit ekranı Kamerası geçiş anahtarını devre dışı bırakır ve bir kameranın kilit ekranında çağrılmasını engeller. Varsayılan olarak, kullanıcılar, kilit ekranında kullanılabilir bir kameranın çağrılmasını sağlayabilir. Bu ayarı etkinleştirirseniz, kullanıcılar artık bılgısayar ayarlarında kilit ekranı kamera erişimini etkinleştiremez veya devre dışı bırakamayacaktır ve kamera kilit ekranında çağrılamaz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067052)
  
  **Varsayılan**: Enabled  

- **Parola gerektir**  
  Cihaz kilidinin etkinleştirilip etkinleştirilmeyeceğini belirtir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067049)  
  
  **Varsayılan**: Evet  
  
  *Parola ıste* *Evet*olarak ayarlandığında aşağıdaki ayarlar kullanılabilir.

  - **Parola en az karakter kümesi sayısı**  
    Güçlü bir PIN veya parola için gereken karmaşık öğe türleri sayısı (büyük ve küçük harfler, rakamlar ve noktalama işaretleri). PIN masaüstü ve mobil cihazlar için aşağıdaki davranışı uygular: 1-yalnızca 2 basamaklı rakamlar ve küçük harflerden oluşan 3 basamaklı, küçük harflerin ve büyük harflerin olması gerekir. Masaüstü Microsoft hesaplarında ve etki alanı hesaplarında desteklenmez. 4 basamaklı, küçük harfler, büyük harfler ve özel karakterler gereklidir. Masaüstünde desteklenmez. Varsayılan değer 1’dir.  
    [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067055)  
    
    **Varsayılan**: 3  

  - **Cihaz silinmeden önceki oturum açma hatası sayısı**  
    Cihaz temizlenmeden önce izin verilen kimlik doğrulama hatalarının sayısı. 0 değeri cihaz temizleme işlevini devre dışı bırakır.  
    [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067030)  
      
    **Varsayılan**: 10  

  - **Parola kullanım süresi (gün)**  
    En fazla parola yaşı ilke ayarı, sistem kullanıcının değiştirmesini gerektirdiğinden bir parolanın ne kadar süreyle kullanılabileceğini (gün cinsinden) belirler. Parolaların süresini 1 ile 999 arasında bir gün sonra dolacak şekilde ayarlayabilir veya gün sayısını 0 olarak ayarlayarak parolaların süre dolmamasını belirtebilirsiniz. Maksimum parola yaşı 1 ila 999 gün arasındaysa, en düşük parola yaşı en fazla parola geçerlilik süresinden az olmalıdır. Maksimum parola yaşı 0 olarak ayarlandıysa, minimum parola yaşı 0 ile 998 gün arasında herhangi bir değer olabilir.  
    [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067028)  
    
    **Varsayılan**: 60  

  - **Gerekli parola türü**  
    Gerekli PIN veya parola türünü belirler.  
    [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067027)  
    
    **Varsayılan**: Sayısal  

  - **En düşük parola uzunluğu**  
    Minimum parola uzunluğu ilke ayarı, bir kullanıcı hesabı için parola oluşturmak üzere en az karakter sayısını belirler. 1 ila 14 karakter arasında bir değer ayarlayabilir veya karakter sayısını 0 olarak ayarlayarak parola gerekmesiz bir değer belirleyebilirsiniz.  
    [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067024)  
    
    **Varsayılan**: 8  

  - **Basit parolaları engelle**  
    "1111" veya "1234" gibi PIN veya parolalara izin verilip verilmeyeceğini belirtir. Masaüstü için, resim parolalarının kullanımını da denetler.  
    [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067127) 
    
    **Varsayılan**: Evet  
      *Evet ayarı basit parolaların kullanımını engeller.* 

  - **Önceki parolaların yeniden kullanılmasını engelleme**  
    Bu, kullanılamayan bir geçmişe kaç parola depolanabileceğini belirtir. Değer, kullanıcının geçerli parolasını içerir. Örneğin, *1* ayarı ile Kullanıcı yeni bir parola seçerken geçerli parolasını yeniden kullantıramıyorum. *5* ayarı, kullanıcının yeni parolasını geçerli parolasına veya önceki dört parolalarından birine ayarlayamayacağı anlamına gelir.  
    [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2066795)  
    
    **Varsayılan**: 24  

- **Slayt gösterisini engelle**  
  BILGISAYAR ayarlarındaki kilit ekranı slayt gösterisi ayarlarını devre dışı bırakır ve kilit ekranında bir slayt gösterisinin yürütülmesini önler. Varsayılan olarak, kullanıcılar makineyi kilitledikten sonra çalışacak bir slayt gösterisine izin verebilir. Bu ayarı etkinleştirirseniz, kullanıcılar bılgısayar ayarlarındaki slayt gösterisi ayarlarını değiştiremezler ve hiçbir slayt gösterisi başlayamaz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067105) 
  
  **Varsayılan**: Enabled  
  *Etkin bir ayar, slayt gösterisinin çalışmasını önler.* 

- **Parola en az gün cinsinden süre**  
  Minimum parola yaşı ilke ayarı, kullanıcının değiştirebilmesi için bir parolanın kullanılması gereken süreyi (gün olarak) belirler. 1 ila 998 gün arasında bir değer ayarlayabilir veya gün sayısını 0 olarak ayarlayarak parola değişikliklerine hemen izin verebilirsiniz. Maksimum parola yaşı 0 olarak ayarlanmadığı ve parolaların süresinin dolmayacağını belirten en az parola yaşı en fazla parola geçerlilik süresinden daha az olmalıdır. Maksimum parola yaşı 0 olarak ayarlandıysa, minimum parola yaşı 0 ile 998 arasında bir değere ayarlanabilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067022) 
  
  **Varsayılan**: 1.  

## <a name="dma-guard"></a>DMA koruyucusu  
Daha fazla bilgi için Windows belgelerindeki [POLICY CSP-DmaGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dmaguard) bölümüne bakın.
- **Çekirdek DMA koruması ile uyumsuz dış cihazların numaralandırması**  
  Bu ilke, dış DMA özellikli cihazlara karşı ek güvenlik sağlamaya yöneliktir. DMA yeniden eşleme/cihaz belleği yalıtımı ve korumalı alana alma ile uyumsuz olan dış DMA özellikli cihazların numaralandırılması üzerinde daha fazla denetim sağlar. Bu ilke, yalnızca çekirdek DMA koruması desteklenirken ve Sistem bellenimi tarafından etkinleştirildiğinde devreye girer. Çekirdek DMA koruması, ilke veya son kullanıcı tarafından denetlenebilecek bir platform özelliğidir. Bu, üretim sırasında sistem tarafından desteklenmelidir. Sistemin çekirdek DMA korumasını destekleyip desteklemediğini denetlemek için lütfen MSINFO32. exe ' nin Özet sayfasındaki çekirdek DMA koruması alanını kontrol edin.  
  [Daha fazla bilgi edinin](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dmaguard#dmaguard-deviceenumerationpolicy)

  **Varsayılan**: Tümünü engelle   

## <a name="event-log-service"></a>Olay günlüğü hizmeti  
Daha fazla bilgi için Windows belgelerindeki [Ilke CSP-EventLogService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-eventlogservice) bölümüne bakın.  

- **KB cinsinden güvenlik günlüğü en büyük dosya boyutu**  
  Bu ilke ayarı, günlük dosyasının en büyük boyutunu kilobayt cinsinden belirtir. Bu ilke ayarını etkinleştirirseniz, en büyük günlük dosyası boyutunu uzunluğu 1 megabayt (1024 kilobayt) ve 2 terabayta (2147483647 kilobayt) kadar kilobayt artışlarla yapılandırabilirsiniz. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, günlük dosyasının en büyük boyutu yerel olarak yapılandırılmış değere ayarlanır. Bu değer, günlük özellikleri iletişim kutusu kullanılarak yerel yönetici tarafından değiştirilebilir ve varsayılan olarak 20 megabaylardır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067042)  
  
   **Varsayılan**: 196608  

- **KB cinsinden sistem günlüğü en büyük dosya boyutu**  
  Bu ilke ayarı, günlük dosyasının en büyük boyutunu kilobayt cinsinden belirtir. Bu ilke ayarını etkinleştirirseniz, en büyük günlük dosyası boyutunu uzunluğu 1 megabayt (1024 kilobayt) ve 2 terabayta (2147483647 kilobayt) kadar kilobayt artışlarla yapılandırabilirsiniz. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, günlük dosyasının en büyük boyutu yerel olarak yapılandırılmış değere ayarlanır. Bu değer, günlük özellikleri iletişim kutusu kullanılarak yerel yönetici tarafından değiştirilebilir ve varsayılan olarak 20 megabaylardır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2066798)  
  
  **Varsayılan**: 32768  

- **KB cinsinden uygulama günlüğü en büyük dosya boyutu**  
  Bu ilke ayarı, günlük dosyasının en büyük boyutunu kilobayt cinsinden belirtir. Bu ilke ayarını etkinleştirirseniz, en büyük günlük dosyası boyutunu uzunluğu 1 megabayt (1024 kilobayt) ve 2 terabayta (2147483647 kilobayt) kadar kilobayt artışlarla yapılandırabilirsiniz. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, günlük dosyasının en büyük boyutu yerel olarak yapılandırılmış değere ayarlanır. Bu değer, günlük özellikleri iletişim kutusu kullanılarak yerel yönetici tarafından değiştirilebilir ve varsayılan olarak 20 megabaylardır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067125)  
  
  **Varsayılan**: 32768  

## <a name="experience"></a>Deneyim  
Daha fazla bilgi için Windows belgelerindeki [Ilke CSP-deneyim](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience) bölümüne bakın.  

- **Windows spot 'u engelle**  
  BT yöneticilerinin tüm Windows spot özelliklerini kapatmasına izin verir-kilit ekranında pencere projektörü, Windows Ipuçları, Microsoft tüketici özellikleri ve diğer ilgili özellikler.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067037)  
  
  **Varsayılan**: Evet  

  *Windows spot 'U engelle* seçeneği *Evet*olarak ayarlandığında aşağıdaki ayarlar kullanılabilir.
  
  - **Windows spot 'da üçüncü taraf önerilerini engelleyin**  
    Kilit ekranı servisleri, başlangıç menüsünde önerilen uygulamalar ve Windows ipuçları gibi Windows spot özelliklerinin üçüncü taraf yazılım yayımcılarından uygulama ve içerik önerilerine izin verilip verilmeyeceğini belirtir. Kullanıcılar Microsoft özellikleri, uygulamaları ve hizmetleri için öneriler görmeye devam edebilir.  
    [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067045)  
      
    **Varsayılan**: Evet  
  - **Tüketiciye özgü özellikleri engelle**  
    BT yöneticilerinin, başlangıç önerileri, üyelik bildirimleri, OOBE sonrası uygulama yüklemesi ve yeniden yönlendirme kutucukları gibi genellikle yalnızca tüketicilere yönelik deneyimler açmasına olanak sağlar.  
    [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067054)  
     
    **Varsayılan**: Evet  

## <a name="exploit-guard"></a>Exploit Guard  
Daha fazla bilgi için Windows belgelerindeki [Ilke CSP-Patıguard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-exploitguard) bölümüne bakın.  

- **Exploit Protection XML**  
  BT yöneticisinin, kuruluştaki tüm cihazlara istenen sistem ve uygulama azaltma seçeneklerini temsil eden bir yapılandırma gönderebilmesini sağlar. Yapılandırma bir XML ile temsil edilir. Yararlanma koruması, cihazları yaymak ve bulaşma için kötüye kullanılan kötü amaçlı yazılımlara karşı korumanıza yardımcı olur. Windows güvenlik uygulamasını veya PowerShell 'i kullanarak bir azaltma kümesi (yapılandırma olarak bilinir) oluşturabilirsiniz. Daha sonra bu yapılandırmayı bir XML dosyası olarak dışarı aktarabilir ve ağınızdaki birden fazla makineyle paylaşarak, hepsi aynı azaltma ayarları kümesine sahip olurlar. Ayrıca, var olan bir EMET yapılandırma XML dosyasını bir Exploit Protection yapılandırması XML dosyasına dönüştürebilir ve içeri aktarabilirsiniz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067035)  
  
  **Varsayılan**: *Örnek XML sağlanır* 
 
## <a name="file-explorer"></a>Dosya Gezgini  
Daha fazla bilgi için Windows belgelerindeki [POLICY CSP-FileExplorer](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-fileexplorer) bölümüne bakın.  

- **Veri yürütme engellemesini engelle**  
  Veri yürütme engellemesini devre dışı bırakmak, bazı eski eklenti uygulamalarının gezgin 'i sonlandırmadan çalışmasına izin verebilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067043)  
  
  **Varsayılan**: Devre dışı  
   
- **Bozulma durumunda yığın sonlandırmasını engelle**  
  Bozulmaya karşı yığın sonlandırmasının devre dışı bırakılması, bazı eski eklenti uygulamalarının gezgin 'i hemen sonlandırmadan çalışmasına izin verebilir, ancak gezgin daha sonra beklenmedik bir şekilde sonlandırılabilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067107)  
  
  **Varsayılan**: Devre dışı  
    

## <a name="internet-explorer"></a>Internet Explorer  
Daha fazla bilgi için bkz. Windows belgelerindeki [Ilke CSP-ınternebir](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-internetexplorer) .  

- **Internet Explorer kısıtlı bölge güncelleştirmelerini betik aracılığıyla durum çubuğuna güncelleştirme**  
  Bu ilke ayarı, betiğin bölge içindeki durum çubuğunu güncelleştirmesine izin verilip verilmeyeceğini yönetmenizi sağlar. 
  - *Bu ilke ayarını etkinleştirirseniz*betiğin durum çubuğunu güncelleştirmesine izin verilir.
  - *Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız*, betiğin durum çubuğunu güncelleştirmesine izin verilmez.  

  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067074)  

  **Varsayılan**: Devre dışı

- **Internet Explorer Internet bölgesi dosyaları sürükleme ve bırakma veya kopyalama ve yapıştırma**  
  Bu ilke ayarı, kullanıcıların bölge içindeki bir kaynaktan dosya sürükleyip sürükleyemeyeceğini veya dosya kopyalayıp yapıştıramayacağını yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, kullanıcılar dosyaları sürükleyebilir veya bu bölgeden otomatik olarak dosya kopyalayabilir ve yapıştırabilir. Açılır kutuda sor ' u seçerseniz, kullanıcıların bu bölgeden dosya sürükleyip sürükleyeceğinizi veya kopyalanıp kopyalanmayacağını seçmeleri istenir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcıların bu bölgeden dosya sürüklenmesi veya dosyaları kopyalaması ve yapıştırması engellenir. Bu ilke ayarını yapılandırmazsanız, kullanıcılar dosyaları sürükleyebilir veya bu bölgeden otomatik olarak dosya kopyalayabilir ve yapıştırabilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067076)  

  **Varsayılan**: Devre Dışı Bırak

- **Internet Explorer kısıtlı bölge .NET Framework bağımlı bileşenler**    
  Bu ilke ayarı, Authenticode ile imzalanmamış .NET Framework bileşenlerinin Internet Explorer 'dan yürütülüp yürütülmeyeceğini yönetmenizi sağlar. Bu bileşenler bir nesne etiketiyle başvurulan yönetilen denetimleri ve bir bağlantıdan başvurulan yönetilen yürütülebilir dosyaları içerir. Bu ilke ayarını etkinleştirirseniz, Internet Explorer imzasız yönetilen bileşenleri yürütür. Açılır kutuda sor ' u seçerseniz, Internet Explorer kullanıcıdan imzasız yönetilen bileşenleri çalıştırıp yürütmeyeceğini belirlemesini ister. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer imzasız yönetilen bileşenleri yürütmez. Bu ilke ayarını yapılandırmazsanız, Internet Explorer imzasız yönetilen bileşenleri yürütmez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067077)

  **Varsayılan**: Devre Dışı Bırak


- **Internet Explorer yerel makine bölgesi, kötü amaçlı yazılımdan koruma 'yi etkin X denetimlerine karşı çalıştırmaz**  
  Bu ilke ayarı, Internet Explorer 'ın, sayfalarda güvenli olup olmadığını denetlemek için kötü amaçlı yazılımdan koruma programlarını ActiveX denetimlerine karşı çalıştırmasını belirler. Bu ilke ayarını etkinleştirirseniz, Internet Explorer, ActiveX denetiminin bir örneğini oluşturmanın güvenli olup olmadığını görmek için kötü amaçlı yazılımdan koruma programınızı denetlemez. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer, ActiveX denetiminin bir örneğinin oluşturulması için güvenli olup olmadığını görmek üzere her zaman kötü amaçlı yazılımdan koruma programınızı denetler. Bu ilke ayarını yapılandırmazsanız, Internet Explorer, ActiveX denetiminin bir örneğinin oluşturulması için güvenli olup olmadığını görmek üzere kötü amaçlı yazılımdan koruma programınızı denetlemez. Kullanıcılar, Internet Explorer güvenlik ayarlarını kullanarak bu davranışı etkinleştirebilir veya devre dışı bırakabilirsiniz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067152)

  **Varsayılan**: Devre dışı

- **Veri kaynaklarına Internet Explorer Internet bölgesi erişimi**  
  Bu ilke ayarı, Internet Explorer 'ın Microsoft XML ayrıştırıcısı (MSXML) veya ActiveX Data Objects (ADO) kullanarak başka bir güvenlik bölgesinden veriye erişip erişemeyeceğini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, kullanıcılar bölgedeki başka bir siteden veriye erişmek için MSXML veya ADO kullanan bölgeye bir sayfa yükleyebilir. Açılır kutuda sor ' u seçerseniz, kullanıcılar bölgedeki başka bir siteden veriye erişmek için MSXML veya ADO kullanan bölgede bir sayfanın yüklenmesine izin verip vermeyeceğinizi belirlemek üzere sorgulanır. Bu ilke ayarını devre dışı bırakırsanız, kullanıcılar bölgedeki başka bir siteden veriye erişmek için MSXML veya ADO kullanan bölgeye bir sayfa yükleyemez. Bu ilke ayarını yapılandırmazsanız kullanıcılar bölgedeki başka bir siteden veriye erişmek için MSXML veya ADO kullanan bölgeye bir sayfa yükleyemez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067078)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer kısıtlı bölge Windows içindeki farklı etki alanlarından içerik sürükle**  
  Bu ilke ayarı, kaynak ve hedef aynı pencerede olduğunda bir etki alanından farklı bir etki alanına içerik sürükleme seçeneklerini ayarlamanıza olanak sağlar. Bu ilke ayarını etkinleştirir ve Etkinleştir ' e tıklarsanız, kullanıcılar kaynak ve hedef aynı pencerede olduğunda bir etki alanından farklı bir etki alanına içerik sürükleyebilir. Kullanıcılar bu ayarı değiştiremezler. Bu ilke ayarını etkinleştirirseniz ve devre dışı bırak ' a tıkladığınızda, kaynak ve hedef aynı pencerede olduğunda kullanıcılar bir etki alanından farklı bir etki alanına içerik sürüklenemez. Kullanıcılar bu ayarı Internet Seçenekleri iletişim kutusunda değiştiremezler. Internet Explorer 10 ' da, bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, kaynak ve hedef aynı pencerede olduğunda kullanıcılar bir etki alanından farklı bir etki alanına içerik sürüklenemez. Kullanıcılar bu ayarı Internet Seçenekleri iletişim kutusunda değiştirebilir. Internet Explorer 9 ve önceki sürümlerde, bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız kullanıcılar, kaynak ve hedef aynı pencerede olduğunda, içeriği bir etki alanından farklı bir etki alanına sürükleyebilir. Kullanıcılar bu ayarı Internet Seçenekleri iletişim kutusunda değiştiremezler.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067079)  
  
  **Varsayılan**: Devre dışı
  
- **Internet Explorer sertifika adresi uyumsuzluğu uyarısı**  
  Bu ilke ayarı, sertifika adresi uyuşmazlığı güvenlik uyarısını açmanıza olanak tanır. Bu ilke ayarı açıkken, Kullanıcı farklı bir Web sitesi adresi için verilen sertifikaları sunan güvenli HTTP (HTTPS) Web sitelerini ziyaret ederken uyarılır. Bu uyarı, sahtekarlığı saldırılarını önlemeye yardımcı olur. Bu ilke ayarını etkinleştirirseniz, sertifika adresi uyumsuzluğu uyarısı her zaman görünür. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız kullanıcı, sertifika adresi uyumsuzluğu Uyarısı ' nı (Internet Denetim Masası 'ndaki gelişmiş sayfasını kullanarak) seçebilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067153)  
  
  **Varsayılan**: Enabled 
  
- **Internet Explorer kısıtlı bölge daha az ayrıcalıklı siteler**  
  Bu ilke ayarı, Internet siteleri gibi daha az ayrıcalıklı bölgelerdeki Web sitelerinin bu bölgede gezinip gidemeyeceğini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, daha az ayrıcalıklı bölgelerdeki Web siteleri içinde yeni pencereler açabilir veya bu bölge üzerinde gezinebilirsiniz. Güvenlik bölgesi, bölge yükselmesi güvenlik özelliğinden koruma tarafından belirtilen ek bir güvenlik katmanı olmadan çalışacaktır. Açılır kutuda sor ' u seçerseniz, kullanıcıya riskli gezintinin gerçekleşmek üzere olduğunu belirten bir uyarı verilir. Bu ilke ayarını devre dışı bırakırsanız, olası zararlı gezinme engellenir. Internet Explorer güvenlik özelliği, bölge yükselmesi özellik denetiminden koruma tarafından ayarlandığı şekilde bu bölgede bulunur. Bu ilke ayarını yapılandırmazsanız, olası zararlı gezintiler engellenir. Internet Explorer güvenlik özelliği, bölge yükselmesi özellik denetiminden koruma tarafından ayarlandığı şekilde bu bölgede bulunur.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067148)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Dosya indirmeleri için Internet Explorer kısıtlı bölge otomatik istemi**  
  Bu ilke ayarı, kullanıcılardan Kullanıcı tarafından başlatılmayan dosya indirmeleri isteyip istemeyeceğini belirler. Bu ayardan bağımsız olarak kullanıcılar, Kullanıcı tarafından başlatılan indirmeler için dosya indirme iletişim kutularını alırlar. Bu ayarı etkinleştirirseniz, kullanıcılar otomatik indirme girişimleri için bir dosya indirme iletişim kutusu alır. Bu ayarı devre dışı bırakır veya yapılandırmazsanız, Kullanıcı tarafından başlatılmayan dosya indirmeleri engellenir ve kullanıcılar dosya indirme iletişim kutusu yerine bildirim çubuğunu görür. Kullanıcılar daha sonra, dosya indirme istemine izin vermek için bildirim çubuğuna tıklayabilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067150)  
  
  **Varsayılan**: Devre dışı
  
- **Internet Explorer Internet bölgesi .NET Framework bağımlı bileşenler**  
  Bu ilke ayarı, Authenticode ile imzalanmamış .NET Framework bileşenlerinin Internet Explorer 'dan yürütülüp yürütülmeyeceğini yönetmenizi sağlar. Bu bileşenler bir nesne etiketiyle başvurulan yönetilen denetimleri ve bir bağlantıdan başvurulan yönetilen yürütülebilir dosyaları içerir. Bu ilke ayarını etkinleştirirseniz, Internet Explorer imzasız yönetilen bileşenleri yürütür. Açılır kutuda sor ' u seçerseniz, Internet Explorer kullanıcıdan imzasız yönetilen bileşenleri çalıştırıp yürütmeyeceğini belirlemesini ister. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer imzasız yönetilen bileşenleri yürütmez. Bu ilke ayarını yapılandırmazsanız, Internet Explorer imzasız yönetilen bileşenleri yürütür.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067073)  
  
  **Varsayılan**: Devre Dışı Bırak 
  
- **Internet Explorer Internet bölgesi yalnızca onaylanan etki alanlarının TDC ActiveX denetimlerini kullanmasına izin verir**  
  Bu ilke ayarı, kullanıcının web sitelerinde TDC ActiveX denetimini çalıştırıp çalıştırameyeceğini denetler. Bu ilke ayarını etkinleştirirseniz, TDC ActiveX denetimi bu bölgedeki Web sitelerinden çalışmaz. Bu ilke ayarını devre dışı bırakırsanız, TDC etkin X denetimi bu bölgedeki tüm sitelerden çalıştırılır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067151)
  
  **Varsayılan**: Enabled 
  
- **Internet Explorer kısıtlı bölge betiği başlatılan Windows**  
  Bu ilke ayarı, başlık ve durum çubuklarını içeren, betik ile başlatılan açılır pencereler ve pencereler üzerindeki kısıtlamaları yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, Windows kısıtlamaları güvenliği bu bölgede uygulanmaz. Güvenlik bölgesi, bu özellik tarafından sunulan ek bir güvenlik katmanı olmadan çalışır. Bu ilke ayarını devre dışı bırakırsanız, başlık ve durum çubuklarını içeren, komut dosyası tarafından başlatılan açılır pencereler ve Windows 'da bulunan olası zararlı eylemler çalıştırılamaz. Bu Internet Explorer güvenlik özelliği, bu bölgede, işlem için Betikleştirilmiş Windows güvenlik kısıtlamaları özelliği denetim ayarı tarafından dikte edildiği şekilde açık. Bu ilke ayarını yapılandırmazsanız, komut dosyası tarafından başlatılan açılır pencereler ve başlık ve durum çubuklarını içeren pencerelerin içerdiği olası zararlı eylemler çalıştırılamaz. Bu Internet Explorer güvenlik özelliği, bu bölgede, işlem için Betikleştirilmiş Windows güvenlik kısıtlamaları özelliği denetim ayarı tarafından dikte edildiği şekilde açık.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067075)  
  
  **Varsayılan**: Devre dışı 
  
- **Internet Explorer Internet bölgesi, dosyaları sunucuya yüklerken yerel yolu içerir**  
  Bu ilke ayarı, Kullanıcı HTML formu aracılığıyla bir dosya yüklerken yerel yol bilgilerinin gönderilip gönderilmediğini denetler. Yerel yol bilgileri gönderildiyse, bazı bilgiler istenmeden sunucu tarafından görüntülenebilir. Örneğin, kullanıcının masaüstünden gönderilen dosyalar yolun bir parçası olarak Kullanıcı adını içerebilir. Bu ilke ayarını etkinleştirirseniz, Kullanıcı HTML formu aracılığıyla bir dosya yüklerken yol bilgileri gönderilir. Bu ilke ayarını devre dışı bırakırsanız, Kullanıcı HTML formu aracılığıyla bir dosya yüklerken yol bilgileri kaldırılır. Bu ilke ayarını yapılandırmazsanız kullanıcı HTML formu aracılığıyla bir dosya yüklerken yol bilgilerinin gönderilip gönderilmeyeceğini seçebilir. Varsayılan olarak, yol bilgileri gönderilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067072)  
  
  **Varsayılan**: Devre dışı 
  
- **Internet Explorer, gelişmiş korumalı modda işlemi devre dışı bırak**  
  Bu ilke ayarı, Windows 'un 64-bit sürümlerinde gelişmiş korumalı modda çalışırken Internet Explorer 11 ' in 64 bitlik süreçler (daha fazla güvenlik için) veya 32 bit süreçler (daha fazla uyumluluk için) kullanıp kullanmadığını belirler. Önemli: 64 bit işlem kullanılırken bazı ActiveX denetimleri ve araç çubukları kullanılamayabilir. Bu ilke ayarını etkinleştirirseniz, Internet Explorer 11, Windows 'un 64 bit sürümlerinde gelişmiş korumalı modda çalışırken 64 bitlik sekme süreçlerini kullanacaktır. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer 11, Windows 'un 64 bit sürümlerinde gelişmiş korumalı modda çalışırken 32 bitlik sekme süreçlerini kullanacaktır. Bu ilke ayarını yapılandırmazsanız kullanıcılar Internet Explorer ayarlarını kullanarak bu özelliği etkinleştirebilir veya devre dışı bırakabilirsiniz. Bu özellik varsayılan olarak kapalıdır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067149)  
  
  **Varsayılan**: Enabled 
  
- **Internet Explorer sertifika hatalarını yoksay**  
  Bu ilke ayarı, Internet Explorer 'da kullanıcının taramayı kesintiye uğratan Güvenli Yuva Katmanı/Aktarım Katmanı Güvenliği (SSL/TLS) sertifika hatalarını ("süre dolduğunda", "iptal edildi" veya "ad uyuşmazlığı" hataları) yok saymasını engeller. Bu ilke ayarını etkinleştirirseniz Kullanıcı göz atmaya devam edebilir. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, Kullanıcı sertifika hatalarını yoksaymayı ve gözatmaya devam etmeyi tercih edebilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067071)  
  
  **Varsayılan**: Devre dışı 
  
- **XAML dosyalarının Internet Explorer Internet bölgesi yüklemesi**  
  Bu ilke ayarı, Extensible Application Markup Language (XAML) dosyalarının yüklenmesini yönetmenizi sağlar. XAML, Windows Presentation Foundation faydalanan zengin Kullanıcı arabirimleri ve grafikleri oluşturmak için yaygın olarak kullanılan XML tabanlı bildirime dayalı bir biçimlendirme dilidir. Bu ilke ayarını etkinleştirir ve açılır kutuyu etkinleştir olarak ayarlarsanız, XAML dosyaları Internet Explorer 'ın içine otomatik olarak yüklenir. Kullanıcı bu davranışı değiştiremez. Açılır kutuyu sor olarak ayarlarsanız, kullanıcıdan XAML dosyalarını yüklemesi istenir. Bu ilke ayarını devre dışı bırakırsanız, XAML dosyaları Internet Explorer 'ın içinde yüklenmez. Kullanıcı bu davranışı değiştiremez. Bu ilke ayarını yapılandırmazsanız, Kullanıcı XAML dosyalarını Internet Explorer içinde yükleyip yükleyemeyeceğine karar verebilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067147)  
  
  **Varsayılan**: Devre Dışı Bırak 
  
- **Dosya indirmeleri için Internet Explorer Internet bölgesi otomatik istemi**  
  Bu ilke ayarı, kullanıcılardan Kullanıcı tarafından başlatılmayan dosya indirmeleri isteyip istemeyeceğini belirler. Bu ayardan bağımsız olarak kullanıcılar, Kullanıcı tarafından başlatılan indirmeler için dosya indirme iletişim kutularını alırlar. Bu ayarı etkinleştirirseniz, kullanıcılar otomatik indirme girişimleri için bir dosya indirme iletişim kutusu alır. Bu ayarı devre dışı bırakır veya yapılandırmazsanız, Kullanıcı tarafından başlatılmayan dosya indirmeleri engellenir ve kullanıcılar dosya indirme iletişim kutusu yerine bildirim çubuğunu görür. Kullanıcılar daha sonra, dosya indirme istemine izin vermek için bildirim çubuğuna tıklayabilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067117)  
  
  **Varsayılan**: Devre dışı  
  
- **Güvenli olmayabilecek dosyalar için Internet Explorer kısıtlı bölge güvenliği uyarısı**  
  Bu ilke ayarı, Kullanıcı yürütülebilir dosyaları veya diğer olası güvenli olmayan dosyaları (örneğin, dosya Gezgini 'ni kullanarak bir intranet dosya paylaşımından) açmaya çalıştığında "dosya güvenlik uyarısı aç" iletisinin görünüp görüntülenmeyeceğini denetler. Bu ilke ayarını etkinleştirir ve açılır kutuyu etkinleştir olarak ayarlarsanız, bu dosyalar güvenlik uyarısı olmadan açılır. Açılır kutuyu sor olarak ayarlarsanız, dosyalar açılmadan önce bir güvenlik uyarısı görüntülenir. Bu ilke ayarını devre dışı bırakırsanız, bu dosyalar açılmaz. Bu ilke ayarını yapılandırmazsanız kullanıcı bilgisayarın bu dosyaları nasıl işleyeceğini yapılandırabilir. Varsayılan olarak, bu dosyalar, Intranet ve yerel bilgisayar bölgelerinde etkin olan kısıtlanmış bölgede engellenir ve Internet ve güvenilen bölgelerde sorulacak şekilde ayarlanır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2066797)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer Internet bölgesi siteler arası betik filtresi**  
  Bu ilke, siteler arası komut dosyası yazma (XSS) filtresinin bu bölgedeki Web sitelerine yönelik siteler arası betik oluşturmayı algılayıp engellemesine izin olup olmadığını denetler. Bu ilke ayarını etkinleştirirseniz, XSS filtresi bu bölgedeki siteler için açıktır ve XSS filtresi siteler arası betik oluşturma girişimlerini engellemeye çalışır. Bu ilke ayarını devre dışı bırakırsanız, bu bölgedeki siteler için XSS filtresi kapatılır ve Internet Explorer siteler arası betik oluşturma izni verir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067053) 
  
  **Varsayılan**: Enabled 
  
- **Internet Explorer SSL3 'e geri dönüş**  
  Bu ilke ayarı, SSL 3,0 'e güvenli olmayan bir geri dönüş engellemenizi sağlar. Bu ilke etkinleştirildiğinde, Internet Explorer, TLS 1,0 veya daha fazla hata verdiğinde SSL 3,0 veya sonraki bir sürümü kullanarak sitelere bağlanmaya çalışır. Ortadaki adam saldırısı oluşmasını engellemek için güvenli olmayan geri dönüşe izin vermemenizi öneririz. Bu ilke hangi güvenlik protokollerinin etkinleştirildiğini etkilemez. Bu ilkeyi devre dışı bırakırsanız, sistem Varsayılanları kullanılır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067118)  
  
  **Varsayılan**: Site yok  

- **Internet Explorer şifreleme desteği**  
  Bu ilke ayarı, tarayıcıda Aktarım Katmanı Güvenliği (TLS) 1,0, TLS 1,1, TLS 1,2, Güvenli Yuva Katmanı (SSL) 2,0 veya SSL 3,0 desteğini kapatmanıza olanak sağlar. TLS ve SSL, tarayıcı ile hedef sunucu arasındaki iletişimi korumaya yardımcı olan protokollerdir. Tarayıcı hedef sunucuyla korunan bir iletişim kurmayı denediğinde, tarayıcı ve sunucu hangi protokol ve sürümü kullanacağınızı anlaşacaktır. Tarayıcı ve sunucu birbirlerinin desteklenen protokollerin ve sürümlerin listesini eşleştirmeye çalışır ve en tercih edilen eşleşmeyi seçer. Bu ilke ayarını etkinleştirirseniz tarayıcı, açılan listeden seçtiğiniz şifreleme yöntemlerini kullanarak bir şifreleme tüneli üzerinde anlaşır veya anlaşmaz. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, Kullanıcı tarayıcının desteklediği şifreleme yöntemini seçebilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067057)

  **Varsayılan**: 2 öğe:  TLS v 1.1 ve TLS v 1.2  
  *Bu ayar için seçebileceğiniz seçenekleri göstermek için aşağı oku seçin.*
  
- **Internet Explorer kilitli Internet alanı akıllı ekranı**  
  Bu ilke ayarı, SmartScreen Filtresi 'nin bu bölgedeki sayfaları kötü amaçlı içerik için taramayacağını denetler. Bu ilke ayarını etkinleştirirseniz SmartScreen Filtresi bu bölgedeki sayfaları kötü amaçlı içeriğe karşı tarar. Bu ilke ayarını devre dışı bırakırsanız, SmartScreen Filtresi bu bölgedeki sayfaları kötü amaçlı içerik için taramaz. Bu ilke ayarını yapılandırmazsanız kullanıcı SmartScreen Filtresi 'nin bu bölgedeki sayfaları kötü amaçlı içerik için tarayıp taramayacağını seçebilir. Not: Internet Explorer 7 ' de bu ilke ayarı, kimlik avı filtresinin bu bölgedeki sayfaları kötü amaçlı içerik için taramayacağını denetler.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067059)  
  
  **Varsayılan**: Enabled 
  
- **Internet Explorer kısıtlı bölge bir iFrame içindeki uygulamaları ve dosyaları başlatma**  
  Bu ilke ayarı, uygulamaların çalıştırılıp çalıştırılmadığını ve bu bölgedeki sayfaların HTML 'si içindeki bir IFRAME başvurusundan dosya indirilip indirilmeyeceğini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, kullanıcılar bu bölgedeki sayfalardaki IFRAME 'lerden Kullanıcı müdahalesi olmadan uygulama çalıştırabilir ve dosya indirebilir. Açılır kutuda sor ' u seçerseniz, kullanıcılar, bu bölgedeki sayfalardaki IFRAME 'lerden uygulama çalıştırıp indirme yapıp uygulamacağınızı seçmeleri istenir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcıların uygulama çalıştırması ve bu bölgedeki sayfalardaki IFRAME 'lerden dosya indirmeleri engellenir. Bu ilke ayarını yapılandırmazsanız, kullanıcıların uygulama çalıştırması ve bu bölgedeki sayfalardaki IFRAME 'lerden dosya indirmeleri engellenir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067061)  
  
  **Varsayılan**: Devre Dışı Bırak 
  
- **Internet Explorer, seyrek görülen dosyalarla ilgili akıllı ekran uyarılarını atla**  
  Bu ilke ayarı, kullanıcının SmartScreen filtresinden gelen uyarıları atlayıp atlayamayacağını belirler. SmartScreen Filtresi, Internet Explorer kullanıcılarının Internet 'ten yaygın olarak indirmediğini çalıştıran yürütülebilir dosyalar hakkında kullanıcıyı uyarır. Bu ilke ayarını etkinleştirirseniz SmartScreen Filtresi uyarıları kullanıcıyı engeller. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız kullanıcı SmartScreen Filtresi uyarılarını atlayabilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067068)  
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer Internet bölgesi açılır pencere engelleyicisi**  
  Bu ilke ayarı, istenmeyen açılır pencerelerin görünüp görünmeyeceğini yönetmenizi sağlar. Son Kullanıcı bir bağlantıya tıkladığında açılan açılır pencereler engellenmez. Bu ilke ayarını etkinleştirirseniz, istenmeyen açılır pencerelerin çoğunun görünmesi engellenir. Bu ilke ayarını devre dışı bırakırsanız, açılır pencerelerin görüntülenmesini önlenemez. Bu ilke ayarını yapılandırmazsanız, istenmeyen açılır pencerelerin çoğunun görünmesi engellenir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067069)  
  
  **Varsayılan**: Etkinleştir  
  
- **Internet Explorer işleme tutarlı MIME işleme**  
  Internet Explorer dinamik ikili davranışları içerir: eklendiği HTML öğeleri için belirli işlevleri kapsülleyen bileşenler. Bu ilke ayarı, Ikili davranış güvenlik kısıtlaması ayarının engellenip engellenmeyeceğini veya izin verilmediğini denetler. Bu ilke ayarını etkinleştirirseniz, dosya Gezgini ve Internet Explorer işlemlerinde ikili davranışlar engellenir. Bu ilke ayarını devre dışı bırakırsanız, dosya Gezgini ve Internet Explorer işlemlerinde ikili davranışlara izin verilir. Bu ilke ayarını yapılandırmazsanız, dosya Gezgini ve Internet Explorer işlemlerinde ikili davranışlar engellenir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067144)  
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer kısıtlı bölge Java izinleri**  
  Bu ilke ayarı, Java uygulamaları için izinleri yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, açılan kutudan Seçenekler ' i seçebilirsiniz. Özel, izin ayarlarını tek tek denetlemek için. Düşük güvenlik, uygulamaların tüm işlemleri gerçekleştirmesini sağlar. Orta düzey güvenlik, uygulamaların korumalı alanları üzerinde (programın çağrı yapamasının dışında bir alan) ve boş alan (istemci bilgisayardaki güvenli ve güvenli bir depolama alanı) ve kullanıcı denetimli dosya g/ç gibi yetenekler üzerinde çalışmasına imkan sağlar. Yüksek güvenlik, uygulamaların kendi korumalı kuruluşlarının çalışmasına olanak sağlar. Tüm uygulamaların çalıştırılmasını engellemek için Java 'Yı devre dışı bırakın. Bu ilke ayarını devre dışı bırakırsanız, Java uygulamaları çalıştırılamaz. Bu ilke ayarını yapılandırmazsanız Java uygulamaları devre dışı bırakılır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067132)  
  
  **Varsayılan**: Java 'yı devre dışı bırak  
    
  
- **Korumalı modda Internet Explorer Active X denetimleri**  
  Bu ilke ayarı, Gelişmiş Korumalı mod etkinken ActiveX denetimlerinin korumalı modda çalışmasını engeller. Bir Kullanıcı, Gelişmiş Korumalı mod ile uyumlu olmayan bir ActiveX denetimine sahip olduğunda ve bir Web sitesi denetimi yüklemeye çalışırsa, Internet Explorer kullanıcıya bildirir ve Web sitesini normal korumalı modda çalıştırma seçeneği sunar. Bu ilke ayarı, bu bildirimi devre dışı bırakır ve tüm Web sitelerini gelişmiş korumalı modda çalışacak şekilde zorlar. Gelişmiş Korumalı mod, Windows 'un 64 bit sürümlerinde 64 bitlik süreçler kullanarak kötü amaçlı Web sitelerine karşı ek koruma sağlar. En az Windows 8 çalıştıran bilgisayarlarda, Gelişmiş Korumalı mod, Internet Explorer 'ın kayıt defterinden ve dosya sisteminde okuyamadığı konumları da sınırlar. Gelişmiş Korumalı mod etkinken ve bir Kullanıcı, Gelişmiş Korumalı modla uyumlu olmayan bir ActiveX denetimi yüklemeye çalışır bir Web sitesi içinde olduğunda, Internet Explorer kullanıcıya bildirir ve gelişmiş korumalı modu için devre dışı bırakma seçeneği sağlar. Bu belirli bir Web sitesi. Bu ilke ayarını etkinleştirirseniz, Internet Explorer kullanıcıya gelişmiş korumalı modu devre dışı bırakma seçeneğini vermez. Tüm korumalı mod Web siteleri, gelişmiş korumalı modda çalışır. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, Internet Explorer kullanıcılara bildirir ve normal korumalı modda uyumsuz ActiveX denetimleriyle Web sitelerini çalıştırma seçeneği sunar.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067145)  
  
  **Varsayılan**: Devre dışı  
  
- **XAML dosyalarının Internet Explorer kısıtlı bölge yüklemesi**  
  Bu ilke ayarı, Extensible Application Markup Language (XAML) dosyalarının yüklenmesini yönetmenizi sağlar. XAML, Windows Presentation Foundation faydalanan zengin Kullanıcı arabirimleri ve grafikleri oluşturmak için yaygın olarak kullanılan XML tabanlı bildirime dayalı bir biçimlendirme dilidir. Bu ilke ayarını etkinleştirir ve açılır kutuyu etkinleştir olarak ayarlarsanız, XAML dosyaları Internet Explorer 'ın içine otomatik olarak yüklenir. Kullanıcı bu davranışı değiştiremez. Açılır kutuyu sor olarak ayarlarsanız, kullanıcıdan XAML dosyalarını yüklemesi istenir. Bu ilke ayarını devre dışı bırakırsanız, XAML dosyaları Internet Explorer 'ın içinde yüklenmez. Kullanıcı bu davranışı değiştiremez. Bu ilke ayarını yapılandırmazsanız, Kullanıcı XAML dosyalarını Internet Explorer içinde yükleyip yükleyemeyeceğine karar verebilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067070)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer komut dosyalı pencere güvenlik kısıtlamalarını işler**  
  Internet Explorer, komut dosyalarının çeşitli türlerin pencerelerini program aracılığıyla açmasına, yeniden boyutlandırmasına ve yeniden konumlandırmasına olanak tanır Pencere Kısıtlamaları güvenlik özelliği açılır pencereleri kısıtlar ve betiklerin, başlık ve durum çubuklarının Kullanıcı tarafından görülemeyen veya diğer pencerelerin başlık ve durum çubuklarının bir gizleme olmayan pencereler görüntülemesini engeller. Bu ilke ayarını etkinleştirirseniz, betikleştirilmiş pencereler tüm süreçler için kısıtlanır. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, betikleştirilmiş pencereler engellenmez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067146)  
  
  **Varsayılan**: Enabled   
  
- **Internet Explorer kısıtlı bölgesi etkin X denetimleri ve eklentileri çalıştırma**  
  Bu ilke ayarı, ActiveX denetimlerinin ve eklentilerin belirtilen bölgedeki sayfalarda çalıştırılıp çalıştırılamayacağını yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, denetimler ve eklentiler Kullanıcı müdahalesi olmadan çalıştırılabilir. Açılır kutuda sor ' u seçtiyseniz, kullanıcılardan denetimlerin veya eklentinin çalışmasına izin verip vermeyeceklerini seçmesi istenir. Bu ilke ayarını devre dışı bırakırsanız, denetimlerin ve eklentilerin çalışması engellenir. Bu ilke ayarını yapılandırmazsanız, denetimlerin ve eklentilerin çalışması engellenir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067114) 
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer kısıtlı bölge betiği etkin X denetimleri betik için güvenli olarak işaretlendi**  
  Bu ilke ayarı, komut dosyası için güvenli olarak işaretlenmiş bir ActiveX denetiminin bir betikten etkileşime giremeyeceğini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, komut dosyası etkileşimi Kullanıcı müdahalesi olmadan otomatik olarak gerçekleşebilir. Açılır kutuda sor ' u seçerseniz, kullanıcılardan betik etkileşimine izin verip vermeyeceğinizi seçmeleri istenir. Bu ilke ayarını devre dışı bırakırsanız, betik etkileşiminin oluşmasını engellenir. Bu ilke ayarını yapılandırmazsanız, betik etkileşiminin oluşmasını engellenir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067062)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer kısıtlı bölge oturum açma seçenekleri**  
  Bu ilke ayarı, oturum açma seçeneklerinin ayarlarını yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, aşağıdaki oturum açma seçenekleri arasından seçim yapabilirsiniz. 
  - *Anonim* -http kimlik doğrulamasını devre dışı bırakmak ve yalnızca ortak Internet dosya SISTEMI (CIFS) protokolü için konuk hesabını kullanmak üzere anonim oturum açma özelliğini kullanın. 
  - *İstem* -Kullanıcı kimlikleri ve parolalar için kullanıcıları sorgulamak üzere Kullanıcı adı ve parola istemi kullanın. Kullanıcı sorgulandıktan sonra bu değerler sessizce oturum geri kalanı için kullanılabilir. 
  - *Yalnızca Intranet bölgesinde otomatik oturum açma* -bu seçeneği, kullanıcıları diğer bölgelerdeki Kullanıcı kimlikleri ve parolalar için sorgulamak üzere kullanın. Kullanıcı sorgulandıktan sonra bu değerler sessizce oturum geri kalanı için kullanılabilir. 
  - *Geçerli Kullanıcı adı ve parolasıyla otomatik oturum aç*-bu seçeneği, Windows NT Challenge yanıtı (NTLM kimlik doğrulaması olarak da bilinir) kullanarak oturum açmayı denemek için kullanın. Sunucu Windows NT Challenge yanıtını destekliyorsa, oturum açma oturum açmak için kullanıcının ağ kullanıcı adını ve parolasını kullanır. Sunucu Windows NT Challenge yanıtını desteklemiyorsa, Kullanıcı Kullanıcı adını ve parolayı sağlamak üzere sorgulanır. 

  Bu ilke ayarını devre dışı bırakırsanız, oturum açma *yalnızca Intranet bölgesinde otomatik oturum açma*olarak ayarlanır. Bu ilke ayarını yapılandırmazsanız, oturum açma, Kullanıcı adı ve parola *isteyecek* şekilde ayarlanır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067110)  
  
  **Varsayılan**: Anonim  
  
- **Internet Explorer güvenilir bölge başlatma ve betik etkin X denetimleri güvenli olarak işaretlenmemiş**  
  Bu ilke ayarı, güvenli olarak işaretlenmemiş ActiveX denetimlerini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, ActiveX denetimleri çalışır, parametrelerle yüklenir ve güvenilir olmayan veriler veya betikler için nesne güvenliğini ayarlamadan komut dosyası. Bu ayar, güvenli ve yönetilen bölgeler dışında önerilmez. Bu ayar, komut dosyası oluşturma seçeneği için güvenli olarak işaretlenmiş betik ActiveX denetimlerini yoksayarak, hem güvensiz hem de güvenli denetimlerin başlatılmasına ve betiklere neden olur. Bu ilke ayarını etkinleştirir ve açılan kutuda sor ' u seçerseniz, kullanıcılara, denetimin parametrelerle veya betiklerle yüklenmesine izin verip vermeyecekleri sorulur. Bu ilke ayarını devre dışı bırakırsanız, güvenli hale getirilemeyen ActiveX denetimleri parametrelerle veya betiklerle yüklenmez. Bu ilke ayarını yapılandırmazsanız kullanıcılara, denetimin parametrelerle veya betiklerle yüklenmesine izin verip vermeyecekleri sorulur.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067137)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer sunucu sertifikasını iptal etme**  
  Bu ilke ayarı, Internet Explorer 'ın, sunucuların sertifikalarının iptal durumunu denetleyip denetmeyeceğini yönetmenizi sağlar. Sertifikalar tehlikeye atıldığında veya artık geçerli olmadığında iptal edilir ve bu seçenek, kullanıcıların sahte veya güvenli olmayan bir siteye gizli veriler göndermesini önler. Bu ilke ayarını etkinleştirirseniz, Internet Explorer sunucu sertifikalarının iptal edilip edilmediğini kontrol eder. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer, iptal edilip edilmediğini görmek için sunucu sertifikalarını denetlemez. Bu ilke ayarını yapılandırmazsanız Internet Explorer, iptal edilip edilmediğini görmek için sunucu sertifikalarını denetlemez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067046)  
  
  **Varsayılan**: Enabled 
  
- **Internet Explorer Internet bölgesi daha az ayrıcalıklı siteler**  
  Bu ilke ayarı, kısıtlanmış siteler gibi daha az ayrıcalıklı bölgelerdeki Web sitelerinin bu bölgede gezinip gidemeyeceğini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, daha az ayrıcalıklı bölgelerdeki Web siteleri içinde yeni pencereler açabilir veya bu bölge üzerinde gezinebilirsiniz. Güvenlik bölgesi, bölge yükselmesi güvenlik özelliğinden koruma tarafından belirtilen ek bir güvenlik katmanı olmadan çalışacaktır. Açılır kutuda sor ' u seçerseniz, kullanıcıya riskli gezintinin gerçekleşmek üzere olduğunu belirten bir uyarı verilir. Bu ilke ayarını devre dışı bırakırsanız, olası zararlı gezintiler engellenir. Internet Explorer güvenlik özelliği, bölge yükselmesi özellik denetiminden koruma tarafından ayarlandığı şekilde bu bölgede bulunur. Bu ilke ayarını yapılandırmazsanız, daha az ayrıcalıklı bölgelerdeki Web siteleri içinde yeni pencereler açabilir veya bu bölge üzerinde gezinebilirsiniz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067109)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer kısıtlı bölge dosyası İndirmeleri**  
  Bu ilke ayarı, bölgeden dosya indirmelerine izin verilip verilmeyeceğini yönetmenizi sağlar. Bu seçenek, dosyanın teslim edildiği bölgeden değil, indirilmesine neden olan sayfanın bölgesi tarafından belirlenir. Bu ilke ayarını etkinleştirirseniz, dosyalar bölgeden indirilebilir. Bu ilke ayarını devre dışı bırakırsanız, dosyaların bölgeden indirilmesi engellenir. Bu ilke ayarını yapılandırmazsanız, dosyaların bölgeden indirilmesi engellenir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067038)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer Internet bölgesi çalıştırma .NET Framework Authenticode ile imzalanmış bağımlı bileşenler**  
  Bu ilke ayarı, Authenticode ile imzalanmış .NET Framework bileşenlerinin Internet Explorer 'dan yürütülüp yürütülmeyeceğini yönetmenizi sağlar. Bu bileşenler bir nesne etiketiyle başvurulan yönetilen denetimleri ve bir bağlantıdan başvurulan yönetilen yürütülebilir dosyaları içerir. Bu ilke ayarını etkinleştirirseniz, Internet Explorer imzalanmış yönetilen bileşenleri yürütür. Açılır kutuda sor ' u seçerseniz, Internet Explorer kullanıcıdan imzalanmış yönetilen bileşenleri çalıştırıp yürütmeyeceğini belirlemesini ister. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer imzalanmış yönetilen bileşenleri yürütmez. Bu ilke ayarını yapılandırmazsanız, Internet Explorer imzalanmış yönetilen bileşenleri yürütmez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067033)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer, etkin X denetimlerinin Kullanıcı başına yüklenmesini engelliyor**  
  Bu ilke ayarı, ActiveX denetimlerinin Kullanıcı bazında yüklenmesini engellemenizi sağlar. Bu ilke ayarını etkinleştirirseniz, ActiveX denetimleri Kullanıcı başına temelinde yüklenemez. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, ActiveX denetimleri Kullanıcı başına temelinde yüklenebilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067058)  
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer akıllı ekran filtresini yönetmeyi engelliyor**  
  Bu ilke ayarı, kullanıcının ziyaret ettikleri web sitesinin "kimlik avı" aracılığıyla kişisel bilgi toplamak için veya kötü amaçlı yazılım barındırmaya yönelik olarak tanındığı durumlarda kullanıcıyı uyaran SmartScreen Filtresi 'ni yönetmesini engeller. Bu ilke ayarını etkinleştirirseniz Kullanıcı SmartScreen Filtresi 'ni etkinleştirmek isteyip istemediğiniz sorulur. Filtreler izin verilenler listesinde olmayan tüm Web sitesi adresleri, kullanıcıya sormadan otomatik olarak Microsoft 'a gönderilir. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, kullanıcıdan ilk çalıştırma deneyimi sırasında SmartScreen Filtresi 'ni açıp açmayacağına karar vermesini istenir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067135)  
  
  **Varsayılan**: Etkinleştir  
  
- **Internet Explorer işlem MIME algılaması güvenlik özelliği**  
  Bu ilke ayarı, Internet Explorer MIME algılaması 'nın bir türdeki dosyanın daha tehlikeli bir dosya türüne yükseltilmesini engelleyip engelmeyeceğini belirler. Bu ilke ayarını etkinleştirirseniz, MIME algılaması hiçbir şekilde bir türdeki dosyayı daha tehlikeli bir dosya türüne yükseltmez. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer işlemi bir MIME algılamasına bir tür dosyanın daha tehlikeli bir dosya türüne yükseltme yapmasına izin verir. Bu ilke ayarını yapılandırmazsanız, MIME algılaması hiçbir şekilde bir türdeki dosyayı daha tehlikeli bir dosya türüne yükseltmez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067124)  
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer kısıtlı bölge, imzalanmış etkin X denetimlerini indirin**  
  Bu ilke ayarı, kullanıcıların, bölgedeki bir sayfadan imzalı ActiveX denetimlerini indirip indirmeyeceğini yönetmenizi sağlar. Bu ilkeyi etkinleştirirseniz kullanıcılar, imzalanmış denetimleri kullanıcı müdahalesi olmadan indirebilir. Açılır kutuda sor ' u seçerseniz, kullanıcılara güvenilmeyen yayımcılar tarafından imzalanmış denetimlerin indirilip indirilmeyeceği sorgulanır. Güvenilen yayımcılar tarafından imzalanan kod sessizce indirilir. İlke ayarını devre dışı bırakırsanız, imzalanmış denetimler indirimez. Bu ilke ayarını yapılandırmazsanız kullanıcılara güvenilmeyen yayımcılar tarafından imzalanmış denetimlerin indirilip indirilmeyeceği istenir. Güvenilen yayımcılar tarafından imzalanan kod sessizce indirilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067120) 
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer otomatik olarak tamamlanır**  
  Bu otomatik tamamlanma özelliği, formlarda Kullanıcı adlarını ve parolalarını anımsayabilir ve önerebilir. Bu ayarı etkinleştirirseniz, Kullanıcı "formlardaki Kullanıcı adı ve parolaları" veya "parola kaydetmem iste" seçeneğini değiştiremez. Formlardaki kullanıcı adları ve parolalar için otomatik tamamlanma özelliği açıktır. "Parolaları kaydetmem için sor" seçeneğini belirleyip seçmemeye karar vermeniz gerekir. Bu ayarı devre dışı bırakırsanız, Kullanıcı "formlardaki Kullanıcı adı ve parolaları" veya "parola kaydetmem iste" öğesini değiştiremez. Formlardaki kullanıcı adları ve parolalar için otomatik tamamlanma özelliği kapalıdır. Kullanıcı da parola kaydetmeyeceğine izin sorulmayı kabul edebilir. Bu ayarı yapılandırmazsanız kullanıcı, formlarda Kullanıcı adı ve parolalar için otomatik tamamlamayı açma özgürlüğüne sahiptir ve parolaları kaydetmenizi isteme seçeneğini sunar. Bu seçeneği göstermek için kullanıcılar Internet Seçenekleri iletişim kutusunu açar, Içerikler sekmesine tıklayın ve Ayarlar düğmesine tıklayın.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067122)  
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer Internet bölgesi VBscript 'in çalışmasına izin verir**  
  Bu ilke ayarı, VBScript 'in belirli Internet Explorer bölgelerindeki sayfalarda çalıştırılıp etmeyeceğine karar vermenizi sağlar. Şu seçenekler mevcuttur: 
  - *Enable* -herhangi bir etkileşim olmadan belirli bölgelerdeki sayfalarda VBScript çalıştırmaları. 
  - *İstem* -çalışanlara VBScript 'in bölgede çalışmasına izin verip vermeyeceğine sorulur. 
  - *Disable* -VBScript 'in bölgede çalışması engellenir. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız VBScript, belirtilen bölgede herhangi bir etkileşim olmadan çalışır.    

  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067119)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer kısıtlı bölgesi yalnızca onaylanan etki alanlarının TDC etkin X denetimlerini kullanmasına izin verir**  
  Bu ilke ayarı, kullanıcının web sitelerinde TDC ActiveX denetimini çalıştırıp çalıştırameyeceğini denetler. Bu ilke ayarını etkinleştirirseniz, TDC ActiveX denetimi bu bölgedeki Web sitelerinden çalışmaz. Bu ilke ayarını devre dışı bırakırsanız, TDC etkin X denetimi bu bölgedeki tüm sitelerden çalıştırılır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067032)  
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer güvenilen bölgesi, etkin X denetimlerine karşı kötü amaçlı yazılımdan koruma çalıştırmayın**  
  Bu ilke ayarı, Internet Explorer 'ın, sayfalarda güvenli olup olmadığını denetlemek için kötü amaçlı yazılımdan koruma programlarını ActiveX denetimlerine karşı çalıştırmasını belirler. Bu ilke ayarını etkinleştirirseniz, Internet Explorer, ActiveX denetiminin bir örneğini oluşturmanın güvenli olup olmadığını görmek için kötü amaçlı yazılımdan koruma programınızı denetlemez. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer, ActiveX denetiminin bir örneğinin oluşturulması için güvenli olup olmadığını görmek üzere her zaman kötü amaçlı yazılımdan koruma programınızı denetler. Bu ilke ayarını yapılandırmazsanız, Internet Explorer, ActiveX denetiminin bir örneğinin oluşturulması için güvenli olup olmadığını görmek üzere her zaman kötü amaçlı yazılımdan koruma programınızı denetler. Kullanıcılar, Internet Explorer güvenlik ayarlarını kullanarak bu davranışı etkinleştirebilir veya devre dışı bırakabilirsiniz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067115)  
  
  **Varsayılan**: Devre dışı 
  
- **Internet Explorer yerel makine bölgesi Java izinleri**  
  Bu ilke ayarı, Java uygulamaları için izinleri yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, açılan kutudan Seçenekler ' i seçebilirsiniz. Özel, izin ayarlarını tek tek denetlemek için. Düşük güvenlik, uygulamaların tüm işlemleri gerçekleştirmesini sağlar. Orta düzey güvenlik, uygulamaların korumalı alanları üzerinde (programın çağrı yapamasının dışında bir alan) ve boş alan (istemci bilgisayardaki güvenli ve güvenli bir depolama alanı) ve kullanıcı denetimli dosya g/ç gibi yetenekler üzerinde çalışmasına imkan sağlar. Yüksek güvenlik, uygulamaların kendi korumalı kuruluşlarının çalışmasına olanak sağlar. Tüm uygulamaların çalıştırılmasını engellemek için Java 'Yı devre dışı bırakın. Bu ilke ayarını devre dışı bırakırsanız, Java uygulamaları çalıştırılamaz. Bu ilke ayarını yapılandırmazsanız, izin orta düzey güvenlik olarak ayarlanır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067113)  
  
  **Varsayılan**: Java 'yı devre dışı bırak 
  
- **Internet Explorer intranet bölgesi, etkin X denetimlerine karşı kötü amaçlı yazılımdan koruma çalıştırmaz**  
  Bu ilke ayarı, Internet Explorer 'ın, sayfalarda güvenli olup olmadığını denetlemek için kötü amaçlı yazılımdan koruma programlarını ActiveX denetimlerine karşı çalıştırmasını belirler. Bu ilke ayarını etkinleştirirseniz, Internet Explorer, ActiveX denetiminin bir örneğini oluşturmanın güvenli olup olmadığını görmek için kötü amaçlı yazılımdan koruma programınızı denetlemez. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer, ActiveX denetiminin bir örneğinin oluşturulması için güvenli olup olmadığını görmek üzere her zaman kötü amaçlı yazılımdan koruma programınızı denetler. Bu ilke ayarını yapılandırmazsanız, Internet Explorer, ActiveX denetiminin bir örneğinin oluşturulması için güvenli olup olmadığını görmek üzere kötü amaçlı yazılımdan koruma programınızı denetlemez. Kullanıcılar, Internet Explorer güvenlik ayarlarını kullanarak bu davranışı etkinleştirebilir veya devre dışı bırakabilirsiniz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067138)  
  
  **Varsayılan**: Devre dışı  

- **Internet Explorer kısıtlı bölge komut dosyası**  
  Bu ilke ayarı, kullanıcının kod parçacıklarına erişip çalıştıramayacağını yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz kullanıcı komut dosyası çalıştırılmasına izin verebilir. Bu ilke ayarını devre dışı bırakırsanız, Kullanıcı komut dosyası çalıştırılmasına izin vermez. Bu ilke ayarını yapılandırmazsanız kullanıcı kod parçacıklarını etkinleştirebilir veya devre dışı bırakabilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067112)  
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer işlem bildirim çubuğu**  
  Bu ilke ayarı, dosya veya kod yüklemeleri kısıtlandıktan sonra bildirim çubuğunun Internet Explorer işlemlerinde görüntülenip görüntülenmeyeceğini yönetmenizi sağlar. Varsayılan olarak, Internet Explorer işlemlerinde bildirim çubuğu görüntülenir. Bu ilke ayarını etkinleştirirseniz, Internet Explorer Işlemlerine yönelik bildirim çubuğu görüntülenir. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer işlemlerinde bildirim çubuğu gösterilmez. Bu ilke ayarını yapılandırmazsanız, Internet Explorer Işlemlerinde bildirim çubuğu görüntülenmez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067139)  
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer Internet bölgesi imzalı ActiveX denetimlerini indirme**  
  Bu ilke ayarı, kullanıcıların, bölgedeki bir sayfadan imzalı ActiveX denetimlerini indirip indirmeyeceğini yönetmenizi sağlar. Bu ilkeyi etkinleştirirseniz kullanıcılar, imzalanmış denetimleri kullanıcı müdahalesi olmadan indirebilir. Açılır kutuda sor ' u seçerseniz, kullanıcılara güvenilmeyen yayımcılar tarafından imzalanmış denetimlerin indirilip indirilmeyeceği sorgulanır. Güvenilen yayımcılar tarafından imzalanan kod sessizce indirilir. İlke ayarını devre dışı bırakırsanız, imzalanmış denetimler indirimez. Bu ilke ayarını yapılandırmazsanız kullanıcılara güvenilmeyen yayımcılar tarafından imzalanmış denetimlerin indirilip indirilmeyeceği istenir. Güvenilen yayımcılar tarafından imzalanan kod sessizce indirilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067064)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer kısıtlı bölge akıllı ekranı**  
  Bu ilke ayarı, SmartScreen Filtresi 'nin bu bölgedeki sayfaları kötü amaçlı içerik için taramayacağını denetler. Bu ilke ayarını etkinleştirirseniz SmartScreen Filtresi bu bölgedeki sayfaları kötü amaçlı içeriğe karşı tarar. Bu ilke ayarını devre dışı bırakırsanız, SmartScreen Filtresi bu bölgedeki sayfaları kötü amaçlı içerik için taramaz. Bu ilke ayarını yapılandırmazsanız kullanıcı SmartScreen Filtresi 'nin bu bölgedeki sayfaları kötü amaçlı içerik için tarayıp taramayacağını seçebilir. Not: Internet Explorer 7 ' de bu ilke ayarı, kimlik avı filtresinin bu bölgedeki sayfaları kötü amaçlı içerik için taramayacağını denetler.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067034)  
  
  **Varsayılan**: Enabled  
  
- **Güncel olmayan etkin X denetimleri için Internet Explorer bu zamanı Çalıştır düğmesini kaldır**  
  Bu ilke ayarı, kullanıcıların "Bu saati Çalıştır" düğmesini görmesini ve Internet Explorer 'da tarihi geçmiş belirli ActiveX denetimlerini çalıştırmasını durdurmanızı sağlar. Bu ilke ayarını etkinleştirirseniz, kullanıcılar Internet Explorer tarihi geçmiş ActiveX denetimini engellediğinde görüntülenen uyarı iletisinde "Bu saati Çalıştır" düğmesini görmez. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, kullanıcılar Internet Explorer tarihi geçmiş ActiveX denetimini engellediğinde görüntülenen uyarı iletisinde "Bu saati Çalıştır" düğmesini görür. Bu düğmeye tıkladığınızda kullanıcının tarihi geçmiş ActiveX denetimini bir kez çalıştırmasına izin verir. Daha fazla bilgi için Internet Explorer TechNet Kitaplığı 'nda "güncel olmayan ActiveX denetimleri" bölümüne bakın.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067123)  
  
  **Varsayılan**: Enabled 
  
- **Internet Explorer Internet bölgesi bir iframe içindeki uygulamaları ve dosyaları başlatma**  
  Bu ilke ayarı, uygulamaların çalıştırılıp çalıştırılmadığını ve bu bölgedeki sayfaların HTML 'si içindeki bir IFRAME başvurusundan dosya indirilip indirilmeyeceğini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, kullanıcılar bu bölgedeki sayfalardaki IFRAME 'lerden Kullanıcı müdahalesi olmadan uygulama çalıştırabilir ve dosya indirebilir. Açılır kutuda sor ' u seçerseniz, kullanıcılar, bu bölgedeki sayfalardaki IFRAME 'lerden uygulama çalıştırıp indirme yapıp uygulamacağınızı seçmeleri istenir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcıların uygulama çalıştırması ve bu bölgedeki sayfalardaki IFRAME 'lerden dosya indirmeleri engellenir. Bu ilke ayarını yapılandırmazsanız, kullanıcılar, bu bölgedeki sayfalardaki IFRAME 'lerden uygulama çalıştırıp indirme yapıp uygulamacağınızı seçmeleri istenir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067020)  
  
  **Varsayılan**: Devre Dışı Bırak 
  
- **Internet Explorer kısıtlı bölgesi farklı etki alanlarındaki pencereler ve çerçevelere gider**  
  Bu ilke ayarı, kaynak ve hedef farklı pencereler olduğunda bir etki alanından farklı bir etki alanına içerik sürükleme seçeneklerini ayarlamanıza olanak sağlar. Bu ilke ayarını etkinleştirir ve Etkinleştir ' e tıklarsanız, kullanıcılar, kaynak ve hedef farklı pencereler olduğunda bir etki alanından farklı bir etki alanına içerik sürükleyebilir. Kullanıcılar bu ayarı değiştiremezler. Bu ilke ayarını etkinleştirirseniz ve devre dışı bırak ' a tıkladığınızda, her ikisi de kaynak ve hedef farklı pencereler olduğunda, kullanıcılar bir etki alanından farklı bir etki alanına içerik sürüklenemez. Kullanıcılar bu ayarı değiştiremezler. Internet Explorer 10 ' da, bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız kullanıcılar, kaynak ve hedef farklı pencereler olduğunda bir etki alanından farklı bir etki alanına içerik sürüklenemez. Kullanıcılar bu ayarı Internet Seçenekleri iletişim kutusunda değiştirebilir. Internet Explorer 9 ve önceki sürümlerde, bu ilkeyi devre dışı bırakır veya yapılandırmazsanız, kullanıcılar, kaynak ve hedef farklı pencereler olduğunda bir etki alanından farklı bir etki alanına içerik sürükleyebilirsiniz. Kullanıcılar bu ayarı değiştiremezler.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067050)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer Internet bölgesi akıllı ekranı**  
  Bu ilke ayarı, SmartScreen Filtresi 'nin bu bölgedeki sayfaları kötü amaçlı içerik için taramayacağını denetler. Bu ilke ayarını etkinleştirirseniz SmartScreen Filtresi bu bölgedeki sayfaları kötü amaçlı içeriğe karşı tarar. Bu ilke ayarını devre dışı bırakırsanız, SmartScreen Filtresi bu bölgedeki sayfaları kötü amaçlı içerik için taramaz. Bu ilke ayarını yapılandırmazsanız kullanıcı SmartScreen Filtresi 'nin bu bölgedeki sayfaları kötü amaçlı içerik için tarayıp taramayacağını seçebilir. Not: Internet Explorer 7 ' de bu ilke ayarı, kimlik avı filtresinin bu bölgedeki sayfaları kötü amaçlı içerik için taramayacağını denetler.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067047)  
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer kilitli Güvenilen bölge Java izinleri**  
  Bu ilke ayarı, Java uygulamaları için izinleri yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, açılan kutudan Seçenekler ' i seçebilirsiniz. Özel, izin ayarlarını tek tek denetlemek için. Düşük güvenlik, uygulamaların tüm işlemleri gerçekleştirmesini sağlar. Orta düzey güvenlik, uygulamaların korumalı alanları üzerinde (programın çağrı yapamasının dışında bir alan) ve boş alan (istemci bilgisayardaki güvenli ve güvenli bir depolama alanı) ve kullanıcı denetimli dosya g/ç gibi yetenekler üzerinde çalışmasına imkan sağlar. Yüksek güvenlik, uygulamaların kendi korumalı kuruluşlarının çalışmasına olanak sağlar. Tüm uygulamaların çalıştırılmasını engellemek için Java 'Yı devre dışı bırakın. Bu ilke ayarını devre dışı bırakırsanız, Java uygulamaları çalıştırılamaz. Bu ilke ayarını yapılandırmazsanız Java uygulamaları devre dışı bırakılır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067142)  
  
  
  **Varsayılan**: Java 'yı devre dışı bırak 
  
- **Internet Explorer indirilen programlardaki imzaları denetle**  
  Bu ilke ayarı, Internet Explorer 'ın, yürütülebilir programları indirmeden önce kullanıcı bilgisayarlarında dijital imzaları (imzalı yazılımın yayımcısını tanımlar ve değiştirilmediğini veya kurcalanmadığını doğrular) denetleyip denetlemeyeceğini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, Internet Explorer çalıştırılabilir programların dijital imzalarını denetler ve kimliklerini kullanıcı bilgisayarlarına indirmeden önce görüntüler. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer yürütülebilir programların dijital imzalarını denetlemez veya kullanıcı bilgisayarlarına indirmeden önce kimliklerini görüntüler. Bu ilkeyi yapılandırmazsanız, Internet Explorer yürütülebilir programların dijital imzalarını denetlemez veya kullanıcı bilgisayarlarına indirmeden önce kimliklerini görüntüler.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067051)  
  
  **Varsayılan**: Enabled  
  
- **Web tarayıcısı denetimlerinin Internet Explorer kısıtlı bölge betiği**  
  Bu ilke ayarı, bir sayfanın katıştırılmış WebBrowser denetimlerini betik aracılığıyla denetleyebilir olup olmayacağını belirler. Bu ilke ayarını etkinleştirirseniz, WebBrowser denetimine betik erişimine izin verilir. Bu ilke ayarını devre dışı bırakırsanız, WebBrowser denetimine betik erişimine izin verilmez. Bu ilke ayarını yapılandırmazsanız kullanıcı WebBrowser denetimine betik erişimini etkinleştirebilir veya devre dışı bırakabilir. Varsayılan olarak, WebBrowser denetimine betik erişimine yalnızca yerel makine ve Intranet bölgelerinde izin verilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067098)  
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer kısıtlı bölge siteler arası betik filtresi**  
  Bu ilke, siteler arası komut dosyası yazma (XSS) filtresinin bu bölgedeki Web sitelerine yönelik siteler arası betik oluşturmayı algılayıp engellemesine izin olup olmadığını denetler. Bu ilke ayarını etkinleştirirseniz, XSS filtresi bu bölgedeki siteler için açıktır ve XSS filtresi siteler arası betik oluşturma girişimlerini engellemeye çalışır. Bu ilke ayarını devre dışı bırakırsanız, bu bölgedeki siteler için XSS filtresi kapatılır ve Internet Explorer siteler arası betik oluşturma izni verir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067178)  
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer kısıtlı bölge ikili ve betik davranışları**  
  Bu ilke ayarı, dinamik ikili ve betik davranışlarını yönetmenizi sağlar: eklendiği HTML öğelerine yönelik belirli işlevleri kapsülleyen bileşenler. Bu ilke ayarını etkinleştirirseniz, ikili ve betik davranışları kullanılabilir. Açılan kutuda yönetici onaylı ' i seçerseniz, yalnızca Ikili davranışlar güvenlik kısıtlama ilkesi altındaki yönetici onaylı davranışlar bölümünde listelenen davranışlar vardır. Bu ilke ayarını devre dışı bırakırsanız, uygulamalar özel bir güvenlik yöneticisi uygulamadıkça ikili ve betik davranışları kullanılamaz. Bu ilke ayarını yapılandırmazsanız, uygulamalar özel bir güvenlik yöneticisi uygulamadıkça ikili ve betik davranışları kullanılamaz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067224)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer güvenlik ayarları denetimi**  
  Bu ilke ayarı, Internet Explorer güvenlik ayarlarını, ayarların ne zaman Internet Explorer 'ı riske sokması gerektiğini belirleyecek şekilde denetleyen güvenlik ayarları denetim özelliğini kapatır. Bu ilke ayarını etkinleştirirseniz, özellik kapalıdır. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, özellik açıktır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067182)  
  
  **Varsayılan**: Enabled  
  
- **Güvenli olmayabilecek dosyalar için Internet Explorer Internet bölgesi güvenlik uyarısı**  
  Bu ilke ayarı, Kullanıcı yürütülebilir dosyaları veya diğer olası güvenli olmayan dosyaları (örneğin, dosya Gezgini 'ni kullanarak bir intranet dosya paylaşımından) açmaya çalıştığında "dosya güvenlik uyarısı aç" iletisinin görünüp görüntülenmeyeceğini denetler. Bu ilke ayarını etkinleştirir ve açılır kutuyu etkinleştir olarak ayarlarsanız, bu dosyalar güvenlik uyarısı olmadan açılır. Açılır kutuyu sor olarak ayarlarsanız, dosyalar açılmadan önce bir güvenlik uyarısı görüntülenir. Bu ilke ayarını devre dışı bırakırsanız, bu dosyalar açılmaz. Bu ilke ayarını yapılandırmazsanız kullanıcı bilgisayarın bu dosyaları nasıl işleyeceğini yapılandırabilir. Varsayılan olarak, bu dosyalar, Intranet ve yerel bilgisayar bölgelerinde etkin olan kısıtlanmış bölgede engellenir ve Internet ve güvenilen bölgelerde sorulacak şekilde ayarlanır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067204)  
  
  **Varsayılan**: İstem  
  
- **Internet Explorer intranet bölgesi Java izinleri**  
  Bu ilke ayarı, Java uygulamaları için izinleri yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, açılan kutudan Seçenekler ' i seçebilirsiniz. Özel, izin ayarlarını tek tek denetlemek için. Düşük güvenlik, uygulamaların tüm işlemleri gerçekleştirmesini sağlar. Orta düzey güvenlik, uygulamaların korumalı alanları üzerinde (programın çağrı yapamasının dışında bir alan) ve boş alan (istemci bilgisayardaki güvenli ve güvenli bir depolama alanı) ve kullanıcı denetimli dosya g/ç gibi yetenekler üzerinde çalışmasına imkan sağlar. Yüksek güvenlik, uygulamaların kendi korumalı kuruluşlarının çalışmasına olanak sağlar. Tüm uygulamaların çalıştırılmasını engellemek için Java 'Yı devre dışı bırakın. Bu ilke ayarını devre dışı bırakırsanız, Java uygulamaları çalıştırılamaz. Bu ilke ayarını yapılandırmazsanız, izin orta düzey güvenlik olarak ayarlanır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067206)  
  
  **Varsayılan**: Yüksek güvenilirlik 
  
- **Internet Explorer blok süresi geçmiş etkin X denetimleri**   
  Bu ilke ayarı, Internet Explorer 'ın güncelliğini yitirmiş belirli ActiveX denetimlerini engellediğini belirler. Güncel olmayan ActiveX denetimleri, Intranet bölgesinde hiçbir şekilde engellenmez. Bu ilke ayarını etkinleştirirseniz, Internet Explorer tarihi geçmiş ActiveX denetimlerini engellemeyi durduruyor. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, Internet Explorer tarihi geçmiş belirli ActiveX denetimlerini engellemeye devam eder. Daha fazla bilgi için Internet Explorer TechNet Kitaplığı 'nda "güncel olmayan ActiveX denetimleri" bölümüne bakın.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067203)  
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer kısıtlı bölge açılan pencere engelleyicisi**  
  Bu ilke ayarı, istenmeyen açılır pencerelerin görünüp görünmeyeceğini yönetmenizi sağlar. Son Kullanıcı bir bağlantıya tıkladığında açılan açılır pencereler engellenmez. Bu ilke ayarını etkinleştirirseniz, istenmeyen açılır pencerelerin çoğunun görünmesi engellenir. Bu ilke ayarını devre dışı bırakırsanız, açılır pencerelerin görüntülenmesini önlenemez. Bu ilke ayarını yapılandırmazsanız, istenmeyen açılır pencerelerin çoğunun görünmesi engellenir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067180)  
  
  **Varsayılan**: Etkinleştir  
  
- **Internet Explorer işlem MK protokol güvenlik kısıtlaması**  
  MK Protokol güvenliği kısıtlama ilkesi ayarı, MK protokolünü engellemek için saldırı yüzeyi alanını azaltır. MK protokolünde barındırılan kaynaklar başarısız olur. Bu ilke ayarını etkinleştirirseniz, MK protokolü dosya Gezgini ve Internet Explorer için engellenir ve MK protokolünde barındırılan kaynaklar başarısız olur. Bu ilke ayarını devre dışı bırakırsanız, uygulamalar MK protokol API 'sini kullanabilir. MK protokolünde barındırılan kaynaklar dosya Gezgini ve Internet Explorer işlemlerinde çalışır. Bu ilke ayarını yapılandırmazsanız, MK protokolü dosya Gezgini ve Internet Explorer için engellenir ve MK protokolünde barındırılan kaynaklar başarısız olur.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067179)  
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer güvenilen bölge Java izinleri**   
  Bu ilke ayarı, Java uygulamaları için izinleri yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, açılan kutudan Seçenekler ' i seçebilirsiniz. Özel, izin ayarlarını tek tek denetlemek için. Düşük güvenlik, uygulamaların tüm işlemleri gerçekleştirmesini sağlar. Orta düzey güvenlik, uygulamaların korumalı alanları üzerinde (programın çağrı yapamasının dışında bir alan) ve boş alan (istemci bilgisayardaki güvenli ve güvenli bir depolama alanı) ve kullanıcı denetimli dosya g/ç gibi yetenekler üzerinde çalışmasına imkan sağlar. Yüksek güvenlik, uygulamaların kendi korumalı kuruluşlarının çalışmasına olanak sağlar. Tüm uygulamaların çalıştırılmasını engellemek için Java 'Yı devre dışı bırakın. Bu ilke ayarını devre dışı bırakırsanız, Java uygulamaları çalıştırılamaz. Bu ilke ayarını yapılandırmazsanız, izin düşük güvenilirlik olarak ayarlanır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067200)  
  
  **Varsayılan**: Yüksek güvenilirlik  
  
- **Java uygulamalarının Internet Explorer kısıtlı bölge betiği**  
  Bu ilke ayarı, uygulamaların bölge içindeki betiklerin gösterilip gösterilmediğini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz betikler, Kullanıcı müdahalesi olmadan uygulamalara otomatik olarak erişebilir. Açılır kutuda sor ' u seçerseniz, kullanıcıların betiklerin uygulamalara erişmesine izin verip vermeyeceğinizi seçmeleri istenir. Bu ilke ayarını devre dışı bırakırsanız, betiklerin uygulamalara erişmesi engellenir. Bu ilke ayarını yapılandırmazsanız betiklerin uygulamalara erişmesi engellenir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067202)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer kilitli yasak bölge Java izinleri**   
  Bu ilke ayarı, Java uygulamaları için izinleri yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, açılan kutudan Seçenekler ' i seçebilirsiniz. Özel, izin ayarlarını tek tek denetlemek için. Düşük güvenlik, uygulamaların tüm işlemleri gerçekleştirmesini sağlar. Orta düzey güvenlik, uygulamaların korumalı alanları üzerinde (programın çağrı yapamasının dışında bir alan) ve boş alan (istemci bilgisayardaki güvenli ve güvenli bir depolama alanı) ve kullanıcı denetimli dosya g/ç gibi yetenekler üzerinde çalışmasına imkan sağlar. Yüksek güvenlik, uygulamaların kendi korumalı kuruluşlarının çalışmasına olanak sağlar. Tüm uygulamaların çalıştırılmasını engellemek için Java 'Yı devre dışı bırakın. Bu ilke ayarını devre dışı bırakırsanız, Java uygulamaları çalıştırılamaz. Bu ilke ayarını yapılandırmazsanız Java uygulamaları devre dışı bırakılır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067181)  
  
  **Varsayılan**: Java 'yı devre dışı bırak 
  
- **Internet Explorer Internet bölgesi yalnızca onaylanan etki alanlarının ActiveX denetimlerini kullanmasına izin verir**   
  Bu ilke ayarı, kullanıcıdan ActiveX denetimini yükleyen web sitesi dışındaki web sitelerinde ActiveX denetimlerinin çalışmasına izin istenip istenmeyeceğini denetler. Bu ilke ayarını etkinleştirirseniz, bu bölgedeki Web sitelerinden ActiveX denetimleri çalıştırılmadan önce kullanıcıya sorulur. Kullanıcı, denetimin geçerli siteden veya tüm sitelerden çalışmasına izin vermeyi seçebilir. Bu ilke ayarını devre dışı bırakırsanız, Kullanıcı site başına ActiveX istemi 'ni görmez ve ActiveX denetimleri bu bölgedeki tüm sitelerden çalıştırılabilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067091)  
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer tüm ağ yollarını içerir**  
  Internet Explorer tüm ağ yollarını içerir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067090)  
  
  **Varsayılan**: Devre dışı 
  
- **Internet Explorer Internet bölgesi korumalı modu**  
  Bu ilke ayarı, korumalı modu açmanıza olanak tanır. Korumalı mod, Internet Explorer 'ın kayıt defterine ve dosya sistemine yazabilecek konumları azaltarak Internet Explorer 'ın açıktan yararlanan güvenlik açıklarına karşı korunmasına yardımcı olur. Bu ilke ayarını etkinleştirirseniz, korumalı mod açıktır. Kullanıcı korumalı modu kapatamaz. Bu ilke ayarını devre dışı bırakırsanız, korumalı mod kapalıdır. Kullanıcı korumalı modu açamaz. Bu ilke ayarını yapılandırmazsanız kullanıcı korumalı modu etkinleştirebilir veya devre dışı bırakabilirsiniz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067171)  
  
  **Varsayılan**: Etkinleştir 
  
- **Internet Explorer Internet bölgesi başlatma ve betik etkin X denetimleri güvenli olarak işaretlenmemiş**  
  Bu ilke ayarı, güvenli olarak işaretlenmemiş ActiveX denetimlerini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, ActiveX denetimleri çalışır, parametrelerle yüklenir ve güvenilir olmayan veriler veya betikler için nesne güvenliğini ayarlamadan komut dosyası. Bu ayar, güvenli ve yönetilen bölgeler dışında önerilmez. Bu ayar, komut dosyası oluşturma seçeneği için güvenli olarak işaretlenmiş betik ActiveX denetimlerini yoksayarak, hem güvensiz hem de güvenli denetimlerin başlatılmasına ve betiklere neden olur. Bu ilke ayarını etkinleştirir ve açılan kutuda sor ' u seçerseniz, kullanıcılara, denetimin parametrelerle veya betiklerle yüklenmesine izin verip vermeyecekleri sorulur. Bu ilke ayarını devre dışı bırakırsanız, güvenli hale getirilemeyen ActiveX denetimleri parametrelerle veya betiklerle yüklenmez. Bu ilke ayarını yapılandırmazsanız, güvenli hale getirilemeyen ActiveX denetimleri parametrelerle veya betiklerle yüklenmez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067170)  
  
  **Varsayılan**: Devre Dışı Bırak 
  
- **Internet Explorer kilitli yasak bölge akıllı ekranı**   
  Bu ilke ayarı, SmartScreen Filtresi 'nin bu bölgedeki sayfaları kötü amaçlı içerik için taramayacağını denetler. Bu ilke ayarını etkinleştirirseniz SmartScreen Filtresi bu bölgedeki sayfaları kötü amaçlı içeriğe karşı tarar. Bu ilke ayarını devre dışı bırakırsanız, SmartScreen Filtresi bu bölgedeki sayfaları kötü amaçlı içerik için taramaz. Bu ilke ayarını yapılandırmazsanız kullanıcı SmartScreen Filtresi 'nin bu bölgedeki sayfaları kötü amaçlı içerik için tarayıp taramayacağını seçebilir. Not: Internet Explorer 7 ' de bu ilke ayarı, kimlik avı filtresinin bu bölgedeki sayfaları kötü amaçlı içerik için taramayacağını denetler.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067092)  
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer kilitlenme algılaması**  
  Bu ilke ayarı, eklenti yönetiminin kilitlenme algılama özelliğini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz Internet Explorer 'da bir kilitlenme, Windows XP Professional Service Pack 1 ve önceki sürümlerde bulunan ve Windows Hata Bildirimi çağırmak için bir davranış sergiler. Windows Hata Bildirimi için tüm ilke ayarları uygulanmaya devam eder. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, eklenti yönetimi için kilitlenme algılama özelliği çalışır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067094)  
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer Internet bölgesi Java izinleri**  
  Bu ilke ayarı, Java uygulamaları için izinleri yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, açılan kutudan Seçenekler ' i seçebilirsiniz. Özel, izin ayarlarını tek tek denetlemek için. Düşük güvenlik, uygulamaların tüm işlemleri gerçekleştirmesini sağlar. Orta düzey güvenlik, uygulamaların korumalı alanları üzerinde (programın çağrı yapamasının dışında bir alan) ve boş alan (istemci bilgisayardaki güvenli ve güvenli bir depolama alanı) ve kullanıcı denetimli dosya g/ç gibi yetenekler üzerinde çalışmasına imkan sağlar. Yüksek güvenlik, uygulamaların kendi korumalı kuruluşlarının çalışmasına olanak sağlar. Tüm uygulamaların çalıştırılmasını engellemek için Java 'Yı devre dışı bırakın. Bu ilke ayarını devre dışı bırakırsanız, Java uygulamaları çalıştırılamaz. Bu ilke ayarını yapılandırmazsanız, izin yüksek güvenlik olarak ayarlanır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067174)  
  
  **Varsayılan**: Java 'yı devre dışı bırak  
  
- **Internet Explorer kısıtlı bölge etkin komut dosyası**  
  Bu ilke ayarı, bölgedeki sayfalarda betik kodunun çalıştırılıp çalıştırılmadığını yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, bölgedeki sayfalardaki betik kodu otomatik olarak çalışabilir. Açılır kutuda sor ' u seçerseniz, kullanıcılar bölgedeki sayfalarda komut dosyası kodunun çalışmasına izin verilip verilmeyeceğini belirlemek için sorgulanır. Bu ilke ayarını devre dışı bırakırsanız, bölgedeki sayfalardaki betik kodunun çalışması engellenir. Bu ilke ayarını yapılandırmazsanız bölgedeki sayfalardaki betik kodunun çalışması engellenir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067172)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer Internet bölgesi oturum açma seçenekleri**  
  Bu ilke ayarı, oturum açma seçeneklerinin ayarlarını yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, aşağıdaki oturum açma seçenekleri arasından seçim yapabilirsiniz. HTTP kimlik doğrulamasını devre dışı bırakmak için anonim oturum açın ve yalnızca ortak Internet dosya sistemi (CIFS) protokolü için konuk hesabını kullanın. Kullanıcı kimlikleri ve parolaları için kullanıcıları sorgulamak üzere Kullanıcı adı ve parola iste. Kullanıcı sorgulandıktan sonra bu değerler, oturumun geri kalanı için sessizce kullanılabilir. Kullanıcıları diğer bölgelerdeki Kullanıcı kimlikleri ve parolalar için sorgulamak üzere yalnızca Intranet bölgesinde otomatik oturum açma. Kullanıcı sorgulandıktan sonra bu değerler sessizce oturum geri kalanı için kullanılabilir. Windows NT Challenge yanıtı (NTLM kimlik doğrulaması olarak da bilinir) kullanarak oturum açmayı denemek için geçerli Kullanıcı adı ve parolasıyla otomatik olarak oturum açın. Sunucu Windows NT Challenge yanıtını destekliyorsa, oturum açma oturum açmak için kullanıcının ağ kullanıcı adını ve parolasını kullanır. Sunucu Windows NT Challenge yanıtını desteklemiyorsa, Kullanıcı Kullanıcı adını ve parolayı sağlamak üzere sorgulanır. Bu ilke ayarını devre dışı bırakırsanız, oturum açma yalnızca Intranet bölgesinde otomatik oturum açma olarak ayarlanır. Bu ilke ayarını yapılandırmazsanız, oturum açma yalnızca Intranet bölgesinde otomatik oturum açma olarak ayarlanır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067194)  
  
  **Varsayılan**: İstem  
  
- **Internet Explorer kısıtlı bölgesi VBScript 'in çalışmasına izin verir**   
  Bu ilke ayarı, VBScript 'in Internet Explorer 'da belirtilen bölgedeki sayfalarda çalıştırılıp çalıştırılamayacağını yönetmenizi sağlar. Açılır kutuda etkinleştir ' i seçtiyseniz, VBScript Kullanıcı müdahalesi olmadan çalıştırılabilir. Açılır kutuda sor ' u seçtiyseniz, kullanıcılardan VBScript 'in çalışmasına izin verip vermeyeceklerini seçmesi istenir. Açılan kutuda devre dışı bırak ' ı seçtiyseniz, VBScript 'in çalışması engellenir. Bu ilke ayarını yapılandırmazsanız veya devre dışı bırakırsanız, VBScript 'in çalışması engellenir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067173)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer Internet bölgesi Windows genelindeki farklı etki alanlarından içerik sürükle**  
  Bu ilke ayarı, kaynak ve hedef farklı pencereler olduğunda bir etki alanından farklı bir etki alanına içerik sürükleme seçeneklerini ayarlamanıza olanak sağlar. Bu ilke ayarını etkinleştirir ve Etkinleştir ' e tıklarsanız, kullanıcılar, kaynak ve hedef farklı pencereler olduğunda bir etki alanından farklı bir etki alanına içerik sürükleyebilir. Kullanıcılar bu ayarı değiştiremezler. Bu ilke ayarını etkinleştirirseniz ve devre dışı bırak ' a tıkladığınızda, her ikisi de kaynak ve hedef farklı pencereler olduğunda, kullanıcılar bir etki alanından farklı bir etki alanına içerik sürüklenemez. Kullanıcılar bu ayarı değiştiremezler. Internet Explorer 10 ' da, bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız kullanıcılar, kaynak ve hedef farklı pencereler olduğunda bir etki alanından farklı bir etki alanına içerik sürüklenemez. Kullanıcılar bu ayarı Internet Seçenekleri iletişim kutusunda değiştirebilir. Internet Explorer 9 ve önceki sürümlerde, bu ilkeyi devre dışı bırakır veya yapılandırmazsanız, kullanıcılar, kaynak ve hedef farklı pencereler olduğunda bir etki alanından farklı bir etki alanına içerik sürükleyebilirsiniz. Kullanıcılar bu ayarı değiştiremezler.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067093)  
  
  **Varsayılan**: Devre dışı 
  
- **Internet Explorer intranet bölgesi başlatma ve betik etkin X denetimleri güvenli olarak işaretlenmemiş**  
  Bu ilke ayarı, güvenli olarak işaretlenmemiş ActiveX denetimlerini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, ActiveX denetimleri çalışır, parametrelerle yüklenir ve güvenilir olmayan veriler veya betikler için nesne güvenliğini ayarlamadan komut dosyası. Bu ayar, güvenli ve yönetilen bölgeler dışında önerilmez. Bu ayar, komut dosyası oluşturma seçeneği için güvenli olarak işaretlenmiş betik ActiveX denetimlerini yoksayarak, hem güvensiz hem de güvenli denetimlerin başlatılmasına ve betiklere neden olur. Bu ilke ayarını etkinleştirir ve açılan kutuda sor ' u seçerseniz, kullanıcılara, denetimin parametrelerle veya betiklerle yüklenmesine izin verip vermeyecekleri sorulur. Bu ilke ayarını devre dışı bırakırsanız, güvenli hale getirilemeyen ActiveX denetimleri parametrelerle veya betiklerle yüklenmez. Bu ilke ayarını yapılandırmazsanız, güvenli hale getirilemeyen ActiveX denetimleri parametrelerle veya betiklerle yüklenmez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067175)  
  
  **Varsayılan**: Devre Dışı Bırak 
  
- **Internet Explorer indirme kasaları**  
  Bu ilke ayarı, kullanıcının bir akıştan kullanıcı bilgisayarına indirilen kasaları (dosya ekleri) olmasını engeller. Bu ilke ayarını etkinleştirirseniz Kullanıcı, akış özelliği sayfası aracılığıyla bir kutu indirmek için akış eşitleme altyapısını ayarlayamıyorum. Geliştirici, akış API 'Leri aracılığıyla indirme ayarını değiştiremez. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, Kullanıcı akış eşitleme altyapısını, akış özelliği sayfasından bir kutu indirmek üzere ayarlayabilir. Geliştirici, akış API 'Leri aracılığıyla indirme ayarını değiştirebilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067245)  
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer kısıtlı bölge imzasız etkin X denetimlerini indirme**  
  Bu ilke ayarı, kullanıcıların imzasız ActiveX denetimlerini bölgeden yükleyip yükleyemeyeceğini yönetmenizi sağlar. Bu kod, özellikle güvenilmeyen bir bölgeden geldiği zaman zararlı olabilir. Bu ilke ayarını etkinleştirirseniz, kullanıcılar imzasız denetimleri kullanıcı müdahalesi olmadan çalıştırabilir. Açılır kutuda sor ' u seçerseniz, kullanıcılardan imzasız denetimin çalışmasına izin verip vermeyeceğinizi seçmeleri istenir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcılar imzasız denetimleri çalıştıramıyorum. Bu ilke ayarını yapılandırmazsanız kullanıcılar imzasız denetimleri çalıştırmaz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067177)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer Internet bölgesi Windows içindeki farklı etki alanlarından içerik sürükle**  
  Bu ilke ayarı, kullanıcıların imzasız ActiveX denetimlerini bölgeden yükleyip yükleyemeyeceğini yönetmenizi sağlar. Bu kod, özellikle güvenilmeyen bir bölgeden geldiği zaman zararlı olabilir. Bu ilke ayarını etkinleştirirseniz, kullanıcılar imzasız denetimleri kullanıcı müdahalesi olmadan çalıştırabilir. Açılır kutuda sor ' u seçerseniz, kullanıcılardan imzasız denetimin çalışmasına izin verip vermeyeceğinizi seçmeleri istenir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcılar imzasız denetimleri çalıştıramıyorum. Bu ilke ayarını yapılandırmazsanız kullanıcılar imzasız denetimleri çalıştırmaz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067095)  
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer işlem etkin X yüklemesini kısıtlar**   
  Bu ilke ayarı, Web tarayıcısı denetimini barındıran uygulamaların, ActiveX denetimi yüklemesinin otomatik olarak sorulmasını engellemesini sağlar. Bu ilke ayarını etkinleştirirseniz, Web tarayıcısı denetimi tüm işlemlerde ActiveX denetimi yüklemesinin otomatik olarak sorulmasını engeller. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, Web tarayıcısı denetimi tüm işlemlerde ActiveX denetimi yüklemesinin otomatik olarak sorulmasını engellemez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067250)  
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer Internet bölgesi komut dosyası**  
  Bu ilke ayarı, kullanıcının kod parçacıklarına erişip çalıştıramayacağını yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz kullanıcı komut dosyası çalıştırılmasına izin verebilir. Bu ilke ayarını devre dışı bırakırsanız, Kullanıcı komut dosyası çalıştırılmasına izin vermez. Bu ilke ayarını yapılandırmazsanız kullanıcı kod parçacıklarını etkinleştirebilir veya devre dışı bırakabilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067176)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer kısıtlı bölge sürükle ve bırak veya dosyaları kopyala ve Yapıştır**  
  Bu ilke ayarı, kullanıcıların bölge içindeki bir kaynaktan dosya sürükleyip sürükleyemeyeceğini veya dosya kopyalayıp yapıştıramayacağını yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, kullanıcılar dosyaları sürükleyebilir veya bu bölgeden otomatik olarak dosya kopyalayabilir ve yapıştırabilir. Açılır kutuda sor ' u seçerseniz, kullanıcıların bu bölgeden dosya sürükleyip sürükleyeceğinizi veya kopyalanıp kopyalanmayacağını seçmeleri istenir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcıların bu bölgeden dosya sürüklenmesi veya dosyaları kopyalaması ve yapıştırması engellenir. Bu ilke ayarını yapılandırmazsanız, kullanıcıların bu bölgeden dosya sürükleyip sürükleyeceğinizi veya kopyalanıp kopyalanmayacağını seçmesi istenir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067096)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **İmza geçersiz olduğunda Internet Explorer yazılımı**  
  Bu ilke ayarı, imza geçersiz olsa bile, ActiveX denetimleri ve dosya indirmeleri gibi yazılımların Kullanıcı tarafından yüklenip yüklenmeyeceğini veya çalıştırılıp çalıştırılamayacağını yönetmenizi sağlar. Geçersiz bir imza, birisinin dosya üzerinde değişiklik yaptığını gösterebilir. Bu ilke ayarını etkinleştirirseniz, kullanıcılardan geçersiz imzalı dosyaları yüklemesi veya çalıştırmaları istenir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcılar geçersiz imzalı dosyaları çalıştıramıyorum veya yükleyemez. Bu ilkeyi yapılandırmazsanız, kullanıcılar geçersiz imzalı dosyaları çalıştırmayı veya yüklemeyi seçebilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067201)
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer kısıtlı bölge kopyalama ve betik aracılığıyla yapıştırma**  
  Bu ilke ayarı, betiklerin belirtilen bölgede bir Pano işlemi gerçekleştirip gerçekleştiremeyeceğini (örneğin, kesme, kopyalama ve yapıştırma) yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz bir betik bir Pano işlemi gerçekleştirebilir. Açılır kutuda sor ' u seçerseniz, kullanıcılar Pano işlemleri yapıp gerçekleştirmeyeceği gibi sorgulanır. Bu ilke ayarını devre dışı bırakırsanız, bir betik bir Pano işlemi gerçekleştiremez. Bu ilke ayarını yapılandırmazsanız bir betik bir Pano işlemi gerçekleştiremez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067165)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer kısıtlı bölgesi Windows üzerinde farklı etki alanlarından içerik sürükle**  
  Bu ilke ayarı, kaynak ve hedef farklı pencereler olduğunda bir etki alanından farklı bir etki alanına içerik sürükleme seçeneklerini ayarlamanıza olanak sağlar. Bu ilke ayarını etkinleştirir ve Etkinleştir ' e tıklarsanız, kullanıcılar, kaynak ve hedef farklı pencereler olduğunda bir etki alanından farklı bir etki alanına içerik sürükleyebilir. Kullanıcılar bu ayarı değiştiremezler. Bu ilke ayarını etkinleştirirseniz ve devre dışı bırak ' a tıkladığınızda, her ikisi de kaynak ve hedef farklı pencereler olduğunda, kullanıcılar bir etki alanından farklı bir etki alanına içerik sürüklenemez. Kullanıcılar bu ayarı değiştiremezler. Internet Explorer 10 ' da, bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız kullanıcılar, kaynak ve hedef farklı pencereler olduğunda bir etki alanından farklı bir etki alanına içerik sürüklenemez. Kullanıcılar bu ayarı Internet Seçenekleri iletişim kutusunda değiştirebilir. Internet Explorer 9 ve önceki sürümlerde, bu ilkeyi devre dışı bırakır veya yapılandırmazsanız, kullanıcılar, kaynak ve hedef farklı pencereler olduğunda bir etki alanından farklı bir etki alanına içerik sürükleyebilirsiniz. Kullanıcılar bu ayarı değiştiremezler.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067166)   

  **Varsayılan**: Devre dışı  
  
- **Siteleri ekleyen Internet Explorer kullanıcıları**  
  Kullanıcıların güvenlik bölgelerinden site eklemesini veya kaldırmasını engeller. Güvenlik bölgesi, aynı güvenlik düzeyine sahip bir Web siteleri grubudur. Bu ilkeyi etkinleştirirseniz güvenlik bölgelerinin site yönetim ayarları devre dışı bırakılır. (Güvenlik bölgelerinin site yönetim ayarlarını görmek için, Internet Seçenekleri iletişim kutusunda Güvenlik sekmesine tıklayın ve ardından siteler düğmesine tıklayın.) Bu ilkeyi devre dışı bırakır veya yapılandırmazsanız, kullanıcılar güvenilen siteler ve Yasak Siteler bölgelerine Web siteleri ekleyebilir veya kaldırabilir ve yerel Intranet bölgesi için ayarları değiştirebilirsiniz. Bu ilke, kullanıcıların yönetici tarafından belirlenen güvenlik bölgelerinin site yönetim ayarlarını değiştirmesini engeller. Not: Arabirimden Güvenlik sekmesini kaldıran "Güvenlik sayfasını devre dışı bırak" ilkesi (Kullanıcı Yapılandırması \ Yönetim Şablonları \ Windows bileşenleri \ Windows Denetim Masası ' nda bulunur), bu ilkeden önceliklidir. Etkinleştirilirse, bu ilke yok sayılır. Ayrıca bkz. "güvenlik bölgeleri: Yalnızca makine ayarlarını kullan "ilkesi.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067167)  
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer Internet bölgesi betiği başlatılan Windows**  
  Bu ilke ayarı, başlık ve durum çubuklarını içeren, betik ile başlatılan açılır pencereler ve pencereler üzerindeki kısıtlamaları yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, Windows kısıtlamaları güvenliği bu bölgede uygulanmaz. Güvenlik bölgesi, bu özellik tarafından sunulan ek bir güvenlik katmanı olmadan çalışır. Bu ilke ayarını devre dışı bırakırsanız, başlık ve durum çubuklarını içeren, komut dosyası tarafından başlatılan açılır pencereler ve Windows 'da bulunan olası zararlı eylemler çalıştırılamaz. Bu Internet Explorer güvenlik özelliği, bu bölgede, işlem için Betikleştirilmiş Windows güvenlik kısıtlamaları özelliği denetim ayarı tarafından dikte edildiği şekilde açık. Bu ilke ayarını yapılandırmazsanız, komut dosyası tarafından başlatılan açılır pencereler ve başlık ve durum çubuklarını içeren pencerelerin içerdiği olası zararlı eylemler çalıştırılamaz. Bu Internet Explorer güvenlik özelliği, bu bölgede, işlem için Betikleştirilmiş Windows güvenlik kısıtlamaları özelliği denetim ayarı tarafından dikte edildiği şekilde açık.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067088)  
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer güvenlik bölgeleri yalnızca makine ayarlarını kullanır**  
  Aynı bilgisayarın tüm kullanıcılarına güvenlik bölgesi bilgilerini uygular. Güvenlik bölgesi, aynı güvenlik düzeyine sahip bir Web siteleri grubudur. Bu ilkeyi etkinleştirirseniz, kullanıcının bir güvenlik bölgesinde yaptığı değişiklikler bu bilgisayarın tüm kullanıcıları için geçerlidir. Bu ilkeyi devre dışı bırakır veya yapılandırmazsanız, aynı bilgisayarın kullanıcıları kendi güvenlik bölgesi ayarlarını kurabilir. Güvenlik bölgesi ayarlarının aynı bilgisayara tek bir şekilde uygulandığından ve kullanıcıdan kullanıcıya değişmemesini sağlamak için bu ilkeyi kullanın. Ayrıca, "güvenlik bölgeleri: kullanıcıların ilke değiştirmesine izin verme" ilkesini inceleyin.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067086)  
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer kilitli yerel makine bölgesi Java izinleri**  
  Bu ilke ayarı, Java uygulamaları için izinleri yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, açılan kutudan Seçenekler ' i seçebilirsiniz. Özel, izin ayarlarını tek tek denetlemek için. Düşük güvenlik, uygulamaların tüm işlemleri gerçekleştirmesini sağlar. Orta düzey güvenlik, uygulamaların korumalı alanları üzerinde (programın çağrı yapamasının dışında bir alan) ve boş alan (istemci bilgisayardaki güvenli ve güvenli bir depolama alanı) ve kullanıcı denetimli dosya g/ç gibi yetenekler üzerinde çalışmasına imkan sağlar. Yüksek güvenlik, uygulamaların kendi korumalı kuruluşlarının çalışmasına olanak sağlar. Tüm uygulamaların çalıştırılmasını engellemek için Java 'Yı devre dışı bırakın. Bu ilke ayarını devre dışı bırakırsanız, Java uygulamaları çalıştırılamaz. Bu ilke ayarını yapılandırmazsanız Java uygulamaları devre dışı bırakılır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067253) 
  
  **Varsayılan**: Java 'yı devre dışı bırak 
  
- **Internet Explorer kısıtlı bölgesi, kötü amaçlı yazılımdan koruma 'yi etkin X denetimlerine karşı çalıştırmaz**   
  Bu ilke ayarı, Internet Explorer 'ın, sayfalarda güvenli olup olmadığını denetlemek için kötü amaçlı yazılımdan koruma programlarını ActiveX denetimlerine karşı çalıştırmasını belirler. Bu ilke ayarını etkinleştirirseniz, Internet Explorer, ActiveX denetiminin bir örneğini oluşturmanın güvenli olup olmadığını görmek için kötü amaçlı yazılımdan koruma programınızı denetlemez. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer, ActiveX denetiminin bir örneğinin oluşturulması için güvenli olup olmadığını görmek üzere her zaman kötü amaçlı yazılımdan koruma programınızı denetler. Bu ilke ayarını yapılandırmazsanız, Internet Explorer, ActiveX denetiminin bir örneğinin oluşturulması için güvenli olup olmadığını görmek üzere her zaman kötü amaçlı yazılımdan koruma programınızı denetler. Kullanıcılar, Internet Explorer güvenlik ayarlarını kullanarak bu davranışı etkinleştirebilir veya devre dışı bırakabilirsiniz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067089)
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer kısıtlı bölge çalıştırma .NET Framework Authenticode ile imzalanmış bağımlı bileşenler**  
  Bu ilke ayarı, Authenticode ile imzalanmış .NET Framework bileşenlerinin Internet Explorer 'dan yürütülüp yürütülmeyeceğini yönetmenizi sağlar. Bu bileşenler bir nesne etiketiyle başvurulan yönetilen denetimleri ve bir bağlantıdan başvurulan yönetilen yürütülebilir dosyaları içerir. Bu ilke ayarını etkinleştirirseniz, Internet Explorer imzalanmış yönetilen bileşenleri yürütür. Açılır kutuda sor ' u seçerseniz, Internet Explorer kullanıcıdan imzalanmış yönetilen bileşenleri çalıştırıp yürütmeyeceğini belirlemesini ister. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer imzalanmış yönetilen bileşenleri yürütmez. Bu ilke ayarını yapılandırmazsanız, Internet Explorer imzalanmış yönetilen bileşenleri yürütmez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067169)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer kısıtlı bölge erişimini veri kaynaklarına erişim**  
  Bu ilke ayarı, Internet Explorer 'ın Microsoft XML ayrıştırıcısı (MSXML) veya ActiveX Data Objects (ADO) kullanarak başka bir güvenlik bölgesinden veriye erişip erişemeyeceğini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, kullanıcılar bölgedeki başka bir siteden veriye erişmek için MSXML veya ADO kullanan bölgeye bir sayfa yükleyebilir. Açılır kutuda sor ' u seçerseniz, kullanıcılar bölgedeki başka bir siteden veriye erişmek için MSXML veya ADO kullanan bölgede bir sayfanın yüklenmesine izin verip vermeyeceğinizi belirlemek üzere sorgulanır. Bu ilke ayarını devre dışı bırakırsanız, kullanıcılar bölgedeki başka bir siteden veriye erişmek için MSXML veya ADO kullanan bölgeye bir sayfa yükleyemez. Bu ilke ayarını yapılandırmazsanız kullanıcılar bölgedeki başka bir siteden veriye erişmek için MSXML veya ADO kullanan bölgeye bir sayfa yükleyemez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067161)  
  
  **Varsayılan**: Devre Dışı Bırak 
  
- **Internet Explorer Internet bölgesi ActiveX denetimlerinde kötü amaçlı yazılımdan koruma çalıştırmayın**  
  Bu ilke ayarı, Internet Explorer 'ın, sayfalarda güvenli olup olmadığını denetlemek için kötü amaçlı yazılımdan koruma programlarını ActiveX denetimlerine karşı çalıştırmasını belirler. Bu ilke ayarını etkinleştirirseniz, Internet Explorer, ActiveX denetiminin bir örneğini oluşturmanın güvenli olup olmadığını görmek için kötü amaçlı yazılımdan koruma programınızı denetlemez. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer, ActiveX denetiminin bir örneğinin oluşturulması için güvenli olup olmadığını görmek üzere her zaman kötü amaçlı yazılımdan koruma programınızı denetler. Bu ilke ayarını yapılandırmazsanız, Internet Explorer, ActiveX denetiminin bir örneğinin oluşturulması için güvenli olup olmadığını görmek üzere her zaman kötü amaçlı yazılımdan koruma programınızı denetler. Kullanıcılar, Internet Explorer güvenlik ayarlarını kullanarak bu davranışı etkinleştirebilir veya devre dışı bırakabilirsiniz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067162)  
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer Internet bölgesi kopyalama ve betik aracılığıyla yapıştırma**  
  Bu ilke ayarı, betiklerin belirtilen bölgede bir Pano işlemi gerçekleştirip gerçekleştiremeyeceğini (örneğin, kesme, kopyalama ve yapıştırma) yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz bir betik bir Pano işlemi gerçekleştirebilir. Açılır kutuda sor ' u seçerseniz, kullanıcılar Pano işlemleri yapıp gerçekleştirmeyeceği gibi sorgulanır. Bu ilke ayarını devre dışı bırakırsanız, bir betik bir Pano işlemi gerçekleştiremez. Bu ilke ayarını yapılandırmazsanız bir betik bir Pano işlemi gerçekleştirebilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067084)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer etkin X Yükleyici hizmetini kullan**  
  Bu ilke ayarı, ActiveX denetimlerinin nasıl yüklendiğini belirtmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, ActiveX denetimleri yalnızca ActiveX Yükleyici hizmeti varsa ve ActiveX denetimlerinin yüklenmesine izin verecek şekilde yapılandırıldıysa yüklenir. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, Kullanıcı başına denetimler dahil olmak üzere ActiveX denetimleri standart yükleme işlemi aracılığıyla yüklenir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067163)
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer, bölge yükselmesinin korumasını işler**  
  Internet Explorer, açtığı her bir Web sayfasına yönelik kısıtlamalar koyar. Kısıtlamalar, Web sayfasının konumuna (Internet, Intranet, yerel makine bölgesi vb.) bağlıdır. Örneğin, yerel bilgisayardaki Web sayfaları en az güvenlik kısıtlamalarına sahiptir ve yerel makine bölgesinde olduğundan, yerel makine güvenlik bölgesine kötü amaçlı kullanıcılar için bir ana hedef atanır. Bu ilke ayarını etkinleştirirseniz, tüm işlemlerin bölge yükselmesine karşı herhangi bir bölge korunabilir. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, Internet Explorer dışındaki işlemler veya Işlem listesinde listelenenler böyle bir koruma almaz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067160)  
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer Internet bölgesi imzasız ActiveX denetimlerini indirme**   
  Bu ilke ayarı, kullanıcıların imzasız ActiveX denetimlerini bölgeden yükleyip yükleyemeyeceğini yönetmenizi sağlar. Bu kod, özellikle güvenilmeyen bir bölgeden geldiği zaman zararlı olabilir. Bu ilke ayarını etkinleştirirseniz, kullanıcılar imzasız denetimleri kullanıcı müdahalesi olmadan çalıştırabilir. Açılır kutuda sor ' u seçerseniz, kullanıcılardan imzasız denetimin çalışmasına izin verip vermeyeceğinizi seçmeleri istenir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcılar imzasız denetimleri çalıştıramıyorum. Bu ilke ayarını yapılandırmazsanız kullanıcılar imzasız denetimleri çalıştırmaz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067325)
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer Internet bölgesi farklı etki alanlarındaki pencereler ve çerçevelere gider**   
  Bu ilke ayarı, farklı etki alanlarındaki pencerelerin ve çerçevelerin açılmasını ve uygulama erişimini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, kullanıcılar diğer etki alanlarından Windows ve çerçeveler açabilir ve diğer etki alanlarından uygulamalara erişebilir. Açılır kutuda sor ' u seçerseniz, kullanıcılar Windows ve çerçevelerin diğer etki alanlarından uygulamalara erişmesine izin verilip verilmeyeceğini belirtir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcılar farklı etki alanlarından uygulamalara erişmek için Windows ve çerçeveler açamaz. Bu ilke ayarını yapılandırmazsanız, kullanıcılar diğer etki alanlarından Windows ve çerçeveler açabilir ve diğer etki alanlarından uygulamalara erişebilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067083)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Komut dosyası aracılığıyla durum çubuğuna Internet Explorer Internet bölgesi güncelleştirmeleri**  
  Bu ilke ayarı, bir betiğin bölge içindeki durum çubuğunu güncelleştirip güncelleştiremeyeceğini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz betikler durum çubuğunu güncelleştirebilir. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, betiğin durum çubuğunu güncelleştirmesine izin verilmez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067087)  
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer kısıtlı bölgesi, dosyaları sunucuya yüklerken yerel yolu içerir**  
  Bu ilke ayarı, Kullanıcı HTML formu aracılığıyla bir dosya yüklerken yerel yol bilgilerinin gönderilip gönderilmediğini denetler. Yerel yol bilgileri gönderildiyse, bazı bilgiler istenmeden sunucu tarafından görüntülenebilir. Örneğin, kullanıcının masaüstünden gönderilen dosyalar yolun bir parçası olarak Kullanıcı adını içerebilir. Bu ilke ayarını etkinleştirirseniz, Kullanıcı HTML formu aracılığıyla bir dosya yüklerken yol bilgileri gönderilir. Bu ilke ayarını devre dışı bırakırsanız, Kullanıcı HTML formu aracılığıyla bir dosya yüklerken yol bilgileri kaldırılır. Bu ilke ayarını yapılandırmazsanız kullanıcı HTML formu aracılığıyla bir dosya yüklerken yol bilgilerinin gönderilip gönderilmeyeceğini seçebilir. Varsayılan olarak, yol bilgileri gönderilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067085)  
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer işlemi dosya indirmeyi kısıtla**   
  Bu ilke ayarı, Web tarayıcısı denetimini barındıran uygulamaların, Kullanıcı tarafından başlatılmayan dosya indirmelerinin otomatik olarak sorulmasını engellemesini sağlar. Bu ilke ayarını etkinleştirirseniz, Web tarayıcısı denetimi, tüm işlemlerde Kullanıcı tarafından başlatılmayan dosya indirmelerinin otomatik olarak sorulmasını engeller. Bu ilke ayarını devre dışı bırakırsanız, Web tarayıcısı denetimi, tüm işlemlerde Kullanıcı tarafından başlatılmayan dosya indirmelerinin otomatik olarak sorulmasını engellemez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067164)  
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer kısıtlı bölgesi yalnızca onaylanan etki alanlarının etkin X denetimlerini kullanmasına izin verir**   
  Bu ilke ayarı, kullanıcıdan ActiveX denetimini yükleyen web sitesi dışındaki web sitelerinde ActiveX denetimlerinin çalışmasına izin istenip istenmeyeceğini denetler. Bu ilke ayarını etkinleştirirseniz, bu bölgedeki Web sitelerinden ActiveX denetimleri çalıştırılmadan önce kullanıcıya sorulur. Kullanıcı, denetimin geçerli siteden veya tüm sitelerden çalışmasına izin vermeyi seçebilir. Bu ilke ayarını devre dışı bırakırsanız, Kullanıcı site başına ActiveX istemi 'ni görmez ve ActiveX denetimleri bu bölgedeki tüm sitelerden çalıştırılabilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067233)  
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer kısıtlı bölge başlatma ve betik etkin X denetimleri güvenli olarak işaretlenmemiş**  
  Bu ilke ayarı, güvenli olarak işaretlenmemiş ActiveX denetimlerini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, ActiveX denetimleri çalışır, parametrelerle yüklenir ve güvenilir olmayan veriler veya betikler için nesne güvenliğini ayarlamadan komut dosyası. Bu ayar, güvenli ve yönetilen bölgeler dışında önerilmez. Bu ayar, komut dosyası oluşturma seçeneği için güvenli olarak işaretlenmiş betik ActiveX denetimlerini yoksayarak, hem güvensiz hem de güvenli denetimlerin başlatılmasına ve betiklere neden olur. Bu ilke ayarını etkinleştirir ve açılan kutuda sor ' u seçerseniz, kullanıcılara, denetimin parametrelerle veya betiklerle yüklenmesine izin verip vermeyecekleri sorulur. Bu ilke ayarını devre dışı bırakırsanız, güvenli hale getirilemeyen ActiveX denetimleri parametrelerle veya betiklerle yüklenmez. Bu ilke ayarını yapılandırmazsanız, güvenli hale getirilemeyen ActiveX denetimleri parametrelerle veya betiklerle yüklenmez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067097)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer kullanıcıları ilkeleri değiştirme**  
  Kullanıcıların güvenlik bölgesi ayarlarını değiştirmesini engeller. Güvenlik bölgesi, aynı güvenlik düzeyine sahip bir Web siteleri grubudur. Bu ilkeyi etkinleştirirseniz Internet Seçenekleri iletişim kutusundaki Güvenlik sekmesinde Özel düzey düğmesi ve güvenlik düzeyi kaydırıcısı devre dışı bırakılır. Bu ilkeyi devre dışı bırakır veya yapılandırmazsanız, kullanıcılar güvenlik bölgelerinin ayarlarını değiştirebilir. Bu ilke, kullanıcıların yönetici tarafından belirlenen güvenlik bölgesi ayarlarını değiştirmesini engeller. Not: Denetim Masası 'nda Internet Explorer 'dan Güvenlik sekmesini kaldıran "Güvenlik sayfasını devre dışı bırak" ilkesi (Kullanıcı Yapılandırması \ Yönetim Şablonları \ Windows bileşenleri \ Denetim Masası) Bu ilke. Etkinleştirilirse, bu ilke yok sayılır. Ayrıca bkz. "güvenlik bölgeleri: Yalnızca makine ayarlarını kullan "ilkesi.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067155)  
    
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer kısıtlı bölge korumalı modu**  
  Bu ilke ayarı, korumalı modu açmanıza olanak tanır. Korumalı mod, Internet Explorer 'ın kayıt defterine ve dosya sistemine yazabilecek konumları azaltarak Internet Explorer 'ın açıktan yararlanan güvenlik açıklarına karşı korunmasına yardımcı olur. Bu ilke ayarını etkinleştirirseniz, korumalı mod açıktır. Kullanıcı korumalı modu kapatamaz. Bu ilke ayarını devre dışı bırakırsanız, korumalı mod kapalıdır. Kullanıcı korumalı modu açamaz. Bu ilke ayarını yapılandırmazsanız kullanıcı korumalı modu etkinleştirebilir veya devre dışı bırakabilirsiniz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067080)  
  
  **Varsayılan**: Etkinleştir  
  
- **Internet Explorer Internet bölgesi Kullanıcı verileri kalıcılığı**  
  Bu ilke ayarı, bilgilerin tarayıcının geçmişinde, Sık Kullanılanlar 'da, bir XML deposunda veya doğrudan diske kaydedilen bir Web sayfasından korunmasını yönetmenizi sağlar. Bir Kullanıcı kalıcı bir sayfaya döndüğünde, bu ilke ayarı uygun şekilde yapılandırıldıysa sayfanın durumu geri yüklenebilir. Bu ilke ayarını etkinleştirirseniz, kullanıcılar tarayıcı geçmişinde, Sık Kullanılanlar 'da, bir XML deposunda veya doğrudan diske kaydedilmiş bir Web sayfasında bilgileri koruyabilir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcılar tarayıcı geçmişinde, Sık Kullanılanlar 'da, bir XML deposunda veya doğrudan diske kaydedilmiş bir Web sayfasında bilgileri koruyamaz. Bu ilke ayarını yapılandırmazsanız, kullanıcılar tarayıcı geçmişinde, Sık Kullanılanlar 'da, bir XML deposunda veya doğrudan diske kaydedilmiş bir Web sayfası içinde bilgileri koruyabilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067156)  
  
  **Varsayılan**: Devre dışı  
  
- **Web tarayıcısı denetimlerinin Internet Explorer Internet bölgesi komut dosyası oluşturma**  
 
  Bu ilke ayarı, bir sayfanın katıştırılmış WebBrowser denetimlerini betik aracılığıyla denetleyebilir olup olmayacağını belirler. Bu ilke ayarını etkinleştirirseniz, WebBrowser denetimine betik erişimine izin verilir. Bu ilke ayarını devre dışı bırakırsanız, WebBrowser denetimine betik erişimine izin verilmez. Bu ilke ayarını yapılandırmazsanız kullanıcı WebBrowser denetimine betik erişimini etkinleştirebilir veya devre dışı bırakabilir. Varsayılan olarak, WebBrowser denetimine betik erişimine yalnızca yerel makine ve Intranet bölgelerinde izin verilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067157)  
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer kısıtlı bölge Kullanıcı verileri kalıcılığı**  
  Bu ilke ayarı, bilgilerin tarayıcının geçmişinde, Sık Kullanılanlar 'da, bir XML deposunda veya doğrudan diske kaydedilen bir Web sayfasından korunmasını yönetmenizi sağlar. Bir Kullanıcı kalıcı bir sayfaya döndüğünde, bu ilke ayarı uygun şekilde yapılandırıldıysa sayfanın durumu geri yüklenebilir. Bu ilke ayarını etkinleştirirseniz, kullanıcılar tarayıcı geçmişinde, Sık Kullanılanlar 'da, bir XML deposunda veya doğrudan diske kaydedilmiş bir Web sayfasında bilgileri koruyabilir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcılar tarayıcı geçmişinde, Sık Kullanılanlar 'da, bir XML deposunda veya doğrudan diske kaydedilmiş bir Web sayfasında bilgileri koruyamaz. Bu ilke ayarını yapılandırmazsanız kullanıcılar tarayıcı geçmişinde, Sık Kullanılanlar 'da, bir XML deposunda veya doğrudan diske kaydedilmiş bir Web sayfasında bilgileri koruyamaz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067081)  
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer kilitli intranet bölgesi Java izinleri**  
  Bu ilke ayarı, Java uygulamaları için izinleri yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, açılan kutudan Seçenekler ' i seçebilirsiniz. Özel, izin ayarlarını tek tek denetlemek için. Düşük güvenlik, uygulamaların tüm işlemleri gerçekleştirmesini sağlar. Orta düzey güvenlik, uygulamaların korumalı alanları üzerinde (programın çağrı yapamasının dışında bir alan) ve boş alan (istemci bilgisayardaki güvenli ve güvenli bir depolama alanı) ve kullanıcı denetimli dosya g/ç gibi yetenekler üzerinde çalışmasına imkan sağlar. Yüksek güvenlik, uygulamaların kendi korumalı kuruluşlarının çalışmasına olanak sağlar. Tüm uygulamaların çalıştırılmasını engellemek için Java 'Yı devre dışı bırakın. Bu ilke ayarını devre dışı bırakırsanız, Java uygulamaları çalıştırılamaz. Bu ilke ayarını yapılandırmazsanız Java uygulamaları devre dışı bırakılır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067082)  
  
  **Varsayılan**: Java 'yı devre dışı bırak  
  
- **Internet Explorer Gelişmiş Korumalı mod**  
  Gelişmiş Korumalı mod, Windows 'un 64 bit sürümlerinde 64 bitlik süreçler kullanarak kötü amaçlı Web sitelerine karşı ek koruma sağlar. En az Windows 8 çalıştıran bilgisayarlarda, Gelişmiş Korumalı mod, Internet Explorer 'ın kayıt defterinden ve dosya sisteminde okuyamadığı konumları da sınırlar. Bu ilke ayarını etkinleştirirseniz, Gelişmiş Korumalı mod açıktır. Korumalı mod etkin olan herhangi bir bölge, Gelişmiş Korumalı mod kullanır. Kullanıcılar Gelişmiş korumalı modu devre dışı bırakamayacak. Bu ilke ayarını devre dışı bırakırsanız, Gelişmiş Korumalı mod kapalıdır. Korumalı mod özellikli herhangi bir bölge, Windows Vista için Internet Explorer 7 ' de sunulan korumalı mod sürümünü kullanır. Bu ilkeyi yapılandırmazsanız kullanıcılar, Internet Seçenekleri iletişim kutusunun Gelişmiş sekmesinde Gelişmiş korumalı modu açabilir veya kapatabilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067158)  
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer akıllı ekran uyarılarını atla**  
  Bu ilke ayarı, kullanıcının SmartScreen filtresinden gelen uyarıları atlayıp atlayamayacağını belirler. SmartScreen Filtresi, Internet Explorer kullanıcılarının Internet 'ten yaygın olarak indirmediğini çalıştıran yürütülebilir dosyalar hakkında kullanıcıyı uyarır. Bu ilke ayarını etkinleştirirseniz SmartScreen Filtresi uyarıları kullanıcıyı engeller. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız kullanıcı SmartScreen Filtresi uyarılarını atlayabilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067159)  
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer kısıtlı bölge meta yenilemesi**  
  Bu ilke ayarı, Web sayfasının yazarı tarayıcıları başka bir Web sayfasına yönlendirmek için meta yenileme ayarı (etiket) kullanıyorsa, kullanıcının tarayıcısının başka bir Web sayfasına yönlendirilip yönlendirilmeyeceğini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, etkin Meta Yenileme ayarı içeren bir sayfayı yükleyen bir kullanıcının tarayıcısı başka bir Web sayfasına yönlendirilebilir. Bu ilke ayarını devre dışı bırakırsanız, etkin bir meta yenileme ayarı içeren bir sayfayı yükleyen kullanıcının tarayıcısı başka bir Web sayfasına yönlendirilemez. Bu ilke ayarını yapılandırmazsanız, etkin Meta Yenileme ayarı içeren bir sayfayı yükleyen bir kullanıcının tarayıcısı başka bir Web sayfasına yönlendirilemez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067154)  
  
  **Varsayılan**: Devre dışı  
  
## <a name="local-policies-security-options"></a>Yerel Ilkeler güvenlik seçenekleri
Daha fazla bilgi için Windows belgelerindeki [Ilke CSP-LocalPoliciesSecurityOptions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions) bölümüne bakın. 

- **Adlandırılmış kanallara ve Paylaşımlara anonim erişimi kısıtla**  
  Bu güvenlik ayarı etkinleştirildiğinde, paylaşımlara ve kanallara anonim erişimi şu ayarlarla kısıtlar: (1) anonim olarak erişilebilen, anonim (2) paylaşımlara erişilebilen adlandırılmış kanallar.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067212)  
  
  **Varsayılan**: Evet  
  
- **NTLM SSP tabanlı sunucular için en düşük oturum güvenliği**  
  Bu güvenlik ayarı, bir sunucunun 128 bitlik şifreleme ve/veya NTLMv2 oturum güvenliği için anlaşma sağlamasına izin verir. Bu değerler, LAN Manager kimlik doğrulama düzeyi güvenlik ayarı değerine bağımlıdır. Seçenekler şunlardır: NTLMv2 oturum güvenliği gerektir: İleti bütünlüğü anlaşılırsa bağlantı başarısız olur. 128 bit şifrelemeyi gerektir. Güçlü şifreleme (128 bit) anlaşılmazsa bağlantı başarısız olur.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067246) 
  
  **Varsayılan**: NTLM v2 ve 128 bit şifrelemeyi gerektir  
  
- **Ekran koruyucusu etkinleşene kadar kilit ekranının işlem yapılmayan dakika sayısı**  
  Windows, bir oturumun etkin olmamasını fark eder ve etkin olmama süresi etkin olmama sınırını aşarsa, ekran koruyucusu çalışarak oturumu kilitler.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067210)  
  
  **Varsayılan**: 15
  
- **İstemcinin iletişimleri her zaman dijital olarak Imzalamasını gerektir** Bu güvenlik ayarı, etki alanı üyesi tarafından başlatılan tüm güvenli kanal trafiğinin imzalanıp imzalanmayacağını veya şifrelenmeyeceğini belirler. Bilgisayar bir etki alanına katıldığında bir bilgisayar hesabı oluşturulur. Bundan sonra, sistem başlatıldığında, etki alanı denetleyicisi için etki alanı denetleyicisiyle güvenli bir kanal oluşturmak üzere bilgisayar hesabı parolasını kullanır. Bu güvenli kanal, kimlik doğrulaması, LSA SID/Ad arama ve daha fazlası gibi işlemleri gerçekleştirmek için kullanılır. Bu ayar, etki alanı üyesi tarafından başlatılan tüm güvenli kanal trafiğinin en düşük güvenlik gereksinimlerini karşılayıp karşılamadığını belirler. Özellikle, etki alanı üyesi tarafından başlatılan tüm güvenli kanal trafiğinin imzalı veya şifrelenmiş olması gerekip gerekmediğini belirler. Bu ilke etkinleştirilirse, tüm güvenli kanal trafiği imzalanmadan veya şifrelenmediği takdirde güvenli kanal kurulmaz. Bu ilke devre dışı bırakılırsa, tüm güvenli kanal trafiğinin şifrelenmesi ve imzalanması, etki alanı denetleyicisi ile görüşülür ve bu durumda, imzalama ve şifreleme düzeyi, etki alanı denetleyicisinin sürümüne ve aşağıdaki iki ayarlara bağlıdır Elerindeki Etki alanı üyesi: Güvenli kanal verilerini (mümkün olduğunda) dijital olarak şifrele etki alanı üyesi: Güvenli kanal verilerini dijital olarak imzala (mümkün olduğunda).  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067187) 
  
  **Varsayılan**: Evet
  
- **Kimlik doğrulama düzeyi**  
  Bu güvenlik ayarı, ağ oturum açmaları için hangi sınama/yanıt kimlik doğrulama protokolünün kullanıldığını belirler. Bu seçim, istemciler tarafından kullanılan kimlik doğrulama protokolünün düzeyini, üzerinde anlaşılan oturum güvenliği düzeyini ve sunucular tarafından kabul edilen kimlik doğrulama düzeyini şu şekilde etkiler:  
  - *LM ve NTLM yanıtları gönderme* -İstemciler LM ve NTLM kimlik doğrulaması kullanır ve hiçbir şekilde NTLMv2 oturum güvenliği kullanmaz; etki alanı denetleyicileri LM, NTLM ve NTLMv2 kimlik doğrulamasını kabul eder. 
  - *Anlaşılırsa LM ve NTLM-NTLMv2 gönder* -İstemciler LM ve NTLM kimlik doğrulaması kullanır ve sunucu destekliyorsa NTLMv2 oturum güvenliği kullanır; etki alanı denetleyicileri LM, NTLM ve NTLMv2 kimlik doğrulamasını kabul eder. 
  - *Yalnızca NTLM yanıtı gönder* -ISTEMCILER yalnızca NTLM kimlik doğrulaması kullanır ve sunucu destekliyorsa NTLMv2 oturum güvenliği kullanır; etki alanı denetleyicileri LM, NTLM ve NTLMv2 kimlik doğrulamasını kabul eder. 
  - *Yalnızca NTLMv2 yanıtı gönder* -Istemciler yalnızca NTLMv2 kimlik doğrulaması kullanır ve sunucu destekliyorsa NTLMv2 oturum güvenliği kullanır; etki alanı denetleyicileri LM, NTLM ve NTLMv2 kimlik doğrulamasını kabul eder. 
  - *Yalnızca NTLMv2 yanıtı gönder. LM* 'yi reddetme-istemciler yalnızca NTLMv2 kimlik doğrulaması kullanır ve sunucu destekliyorsa NTLMv2 oturum güvenliği kullanır; etki alanı denetleyicileri LM 'yi reddeder (yalnızca NTLM ve NTLMv2 kimlik doğrulamasını kabul eder). 
  - *Yalnızca NTLMv2 yanıtı gönder. LM ve NTLM* reddetme-istemciler yalnızca NTLMv2 kimlik doğrulaması kullanır ve sunucu destekliyorsa NTLMv2 oturum güvenliği kullanır; etki alanı denetleyicileri LM ve NTLM 'yi reddeder (yalnızca NTLMv2 kimlik doğrulamasını kabul eder).  

  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067189)   
    
  **Varsayılan**: Yalnızca NTLMv2 yanıtı gönder. LM ve NTLM 'yi reddetme
  
- **İstemcilerin üçüncü taraf SMB sunucularına Şifrelenmemiş parolalar göndermesini engelle**  
  Bu güvenlik ayarı etkinleştirilirse, sunucu Ileti bloğu (SMB) yeniden yönlendiricisi, kimlik doğrulaması sırasında parola şifrelemesini desteklemeyen, Microsoft olmayan SMB sunucularına düz metin parolaları gönderebilir. Şifrelenmemiş parolaların gönderilmesi bir güvenlik riskidir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067235)  
  
  **Varsayılan**: Evet
  
- **Sunucu iletişimlerini her zaman dijital olarak imzalamasını gerektir**  
  Bu güvenlik ayarı, SMB istemcisinin SMB paket imzalama anlaşması yapıp denemeyeceğini belirler. Sunucu ileti bloğu (SMB) protokolü, Microsoft dosya ve yazıcı paylaşımı ve uzak Windows yönetimi gibi birçok farklı ağ işlemi için temel sağlar. Geçiş sırasında SMB paketlerini değiştiren bağlantıyı izinsiz izleme saldırıları engellemek için SMB protokolü, SMB paketlerinin dijital imzalanmasını destekler. Bu ilke ayarı, SMB istemci bileşeninin bir SMB sunucusuna bağlanırken SMB paket imzalama anlaşması yapıp denemeyeceğini belirler. Bu ayar etkinleştirilirse, Microsoft ağ istemcisi, oturum kurulumundan sonra sunucudan SMB paket imzalamayı gerçekleştirmesini ister. Sunucuda paket imzalama etkinleştirildiyse, paket imzalama anlaşması yapılır. Bu ilke devre dışıysa, SMB istemcisi hiçbir şekilde SMB paket imzalamayı hiçbir şekilde anlaşacaktır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067319)  
  
  **Varsayılan**: Evet
  
- **Yönetici yükseltme istemi davranışı**  
  Bu ilke ayarı, Yöneticiler için yükseltme isteminin davranışını denetler. Seçenekler şunlardır: 
  - *Sormadan Yükselt* -ayrıcalıklı hesapların, izin veya kimlik bilgileri gerekmeden yükseltme gerektiren bir işlem gerçekleştirmesine izin verir. Not: Bu seçeneği yalnızca en kısıtlanmış ortamlarda kullanın. 
  - *Güvenli masaüstünde kimlik bilgileri iste* -bir işlem ayrıcalık yükseltmesi gerektirdiğinde, kullanıcının güvenli masaüstünde ayrıcalıklı bir Kullanıcı adı ve parola girmesi istenir. Kullanıcı geçerli kimlik bilgileri girerse, işlem kullanıcının kullanılabilir en yüksek ayrıcalığıyla devam eder. 
  - *Güvenli masaüstünde onay iste* -bir işlem ayrıcalık yükseltmesi gerektirdiğinde, kullanıcının güvenli masaüstünde izin ver veya Reddet ' i seçmesi istenir. Kullanıcı Izin ver ' i seçerse, işlem kullanıcının kullanılabilir en yüksek ayrıcalığıyla devam eder. 
  - *Kimlik bilgileri iste* -bir işlem ayrıcalık yükseltmesi gerektirdiğinde kullanıcıdan bir Yönetici Kullanıcı adı ve parola girmesi istenir. Kullanıcı geçerli kimlik bilgileri girerse, işlem ilgili ayrıcalıkla devam eder. 
  - *Onay iste* -bir işlem ayrıcalık yükseltmesi gerektirdiğinde, kullanıcıdan izin ver veya Reddet ' i seçmesi istenir. Kullanıcı Izin ver ' i seçerse, işlem kullanıcının kullanılabilir en yüksek ayrıcalığıyla devam eder.  
  - *Windows dışı ikili dosyalar için Izin iste* -Microsoft dışı bir uygulama için bir işlem ayrıcalık yükseltmesi gerektirdiğinde, kullanıcıdan güvenli masaüstünde izin ver veya Reddet ' i seçmesi istenir. Kullanıcı Izin ver ' i seçerse, işlem kullanıcının kullanılabilir en yüksek ayrıcalığıyla devam eder. 
  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067215)   
  
  **Varsayılan**: Güvenli masaüstünde onay iste
  
- **NTLM SSP tabanlı istemciler için en düşük oturum güvenliği**  
  Bu güvenlik ayarı, bir istemcinin 128 bitlik şifreleme ve/veya NTLMv2 oturum güvenliği anlaşmasını gerektirmesini sağlar. Bu değerler, LAN Manager kimlik doğrulama düzeyi güvenlik ayarı değerine bağımlıdır. Seçenekler şunlardır:
  - *NTLMv2 oturum güvenliği gerektir* -NTLMv2 Protokolü anlaşılırsa bağlantı başarısız olur. 
  - *128 bit şifreleme gerektir* -güçlü şifreleme (128 bit) anlaşılmazsa bağlantı başarısız olur.
  - *NTLMv2 ve 128 bit şifrelemeyi gerektir*.  

  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067324)  

  **Varsayılan**: NTLM v2 128 şifrelemesi gerektir
  
- **Akıllı kart kaldırma davranışı**  
  Bu güvenlik ayarı, oturum açmış bir kullanıcının akıllı kartı, akıllı kart okuyucusundan kaldırıldığında ne olacağını belirler. Seçenekler şunlardır:
  - *Eylem yok*. 
  - *Iş Istasyonunu kilitle* -akıllı kart kaldırıldığında iş istasyonu kilitlenir, kullanıcıların alanı terk etmeleri, akıllı kartlarını bunlara sahip olması ve hala korumalı bir oturum sürdürmesine izin verir.
  - *Kapanmaya zorla* -akıllı kart kaldırıldığında Kullanıcı oturumu otomatik olarak kapatılır.
  - *Uzak Masaüstü oturumunun bağlantısını kesme* -akıllı kartın kaldırılması, kullanıcının oturumunu kapatmadan oturumun bağlantısını keser. Bu, kullanıcının akıllı kartı eklemesini ve oturumu daha sonra ya da başka bir akıllı kart okuyucusu ile donatılmış bir bilgisayara yeniden oturum açmak zorunda kalmadan sürdürmesini sağlar. Yerel bir oturum söz konusuysa, bu ilke İş İstasyonunu Kilitle ilkesiyle tam olarak aynı işlevi görür.
  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067331) 
    
  **Varsayılan**: İş istasyonunu kilitle
  
- **SAM hesaplarının ve paylaşımlarının anonim numaralandırılmasına engel**  
  Bu güvenlik ayarı, SAM hesaplarının ve paylaşımlarının anonim numaralandırılmasına izin verilip verilmeyeceğini belirler. Windows, anonim kullanıcıların etki alanı hesaplarının ve ağ paylaşımlarının adlarını numaralandırma gibi belirli etkinlikleri gerçekleştirmesine olanak sağlar. Bu, örneğin, bir yönetici, güvenilen bir etki alanındaki kullanıcılara, karşılıklı güven ilişkisi olmayan kullanıcılar için erişim vermek istediğinde kullanışlıdır. SAM hesaplarının ve paylaşımlarının anonim numaralandırmasına izin vermek istemiyorsanız, bu ilkeyi *Evet*olarak ayarlayın.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067191)  
  
  **Varsayılan**: Evet
  
- **Boş parolayla uzaktan oturum açmayı engelle**  
  Bu güvenlik ayarı, parola korumalı olmayan yerel hesapların fiziksel bilgisayar konsolu dışındaki konumlardan oturum açmak için kullanılıp kullanılamayacağını belirler. Etkinleştirilirse, parola korumalı olan yerel hesapların oturum açması için bilgisayarın klavyesini kullanması gerekir. 

  *Uyarı*: Fiziksel olarak güvenli konumlarda olmayan bilgisayarların her zaman tüm yerel kullanıcı hesapları için güçlü parola ilkelerini zorlaması gerekir. Aksi takdirde, bilgisayara fiziksel erişimi olan herkes, parolası olmayan bir kullanıcı hesabı kullanarak oturum açabilir. Bu özellikle taşınabilir bilgisayarlar için önemlidir. 

  Bu güvenlik ilkesini Herkes grubuna uygularsanız, hiç kimse Uzak Masaüstü Hizmetleri aracılığıyla oturum açabilir. Bu ayar, etki alanı hesapları kullanan oturum açmaları etkilemez. Bu ayarı atlamak için uzak etkileşimli oturum açmaları kullanan uygulamalar mümkündür.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067219)  
  
  **Varsayılan**: Evet
  
- **Standart Kullanıcı yükseltme istemi davranışı**  
  Bu ilke ayarı, standart kullanıcılar için yükseltme isteminin davranışını denetler. 
  - *Yükseltme Isteklerini otomatik olarak Reddet* -bir işlem ayrıcalık yükseltmesi gerektirdiğinde, yapılandırılabilir bir erişim reddedildi hata iletisi görüntülenir. Masaüstlerini standart Kullanıcı olarak çalıştıran bir kuruluş, Yardım Masası çağrılarını azaltmak için bu ayarı seçebilirler. 
  - *Güvenli masaüstünde kimlik bilgileri iste* -bir işlem ayrıcalık yükseltmesi gerektirdiğinde, kullanıcının güvenli masaüstünde farklı bir Kullanıcı adı ve parola girmesi istenir. Kullanıcı geçerli kimlik bilgileri girerse, işlem ilgili ayrıcalıkla devam eder. 
  - *Kimlik bilgileri iste* -bir işlem ayrıcalık yükseltmesi gerektirdiğinde kullanıcıdan bir Yönetici Kullanıcı adı ve parola girmesi istenir. Kullanıcı geçerli kimlik bilgileri girerse, işlem ilgili ayrıcalıkla devam eder.  

  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067183)  
  
  **Varsayılan**: Yükseltme isteklerini otomatik olarak Reddet
  
- **Yöneticiler için yönetici onay modu gerektir**  
  Bu ilke ayarı, bilgisayar için tüm Kullanıcı hesabı denetimi (UAC) ilke ayarlarının davranışını denetler. Bu ilke ayarını değiştirirseniz, bilgisayarınızı yeniden başlatmanız gerekir. Seçenekler şunlardır:   
  - *Yapılandırılmadı* -yönetici onay modu ve ılgılı tüm UAC ilkesi ayarları devre dışı bırakıldı. Not: Bu ilke ayarı devre dışı bırakılırsa, Güvenlik Merkezi, işletim sisteminin genel güvenliğinin azaldığını size bildirir. 
  - *Evet* -yönetici onay modu etkin. Bu ilkenin etkinleştirilmesi ve ilgili UAC ilkesi ayarlarının, yerleşik yönetici hesabının ve Yöneticiler grubunun üyesi olan diğer tüm kullanıcıların yönetici onay modunda çalışmasına izin verecek şekilde ayarlanmış olması gerekir.  

  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067184)  
  
  **Varsayılan**: Evet
  
- **SAM hesaplarının anonim numaralandırılmasına engel**  
  Bu güvenlik ayarı, bilgisayara anonim bağlantılar için hangi ek izinlerin verildiğini belirler. Windows, anonim kullanıcıların etki alanı hesaplarının ve ağ paylaşımlarının adlarını numaralandırma gibi belirli etkinlikleri gerçekleştirmesine olanak sağlar. Bu, örneğin, bir yönetici, güvenilen bir etki alanındaki kullanıcılara, karşılıklı güven ilişkisi olmayan kullanıcılar için erişim vermek istediğinde kullanışlıdır. Bu güvenlik seçeneği, anonim bağlantılara aşağıdaki gibi ek kısıtlamaların yerleştirilmesine izin verir: 
  - *Evet* -Sam hesaplarının numaralandırılmasına izin verme. Bu seçenek, kaynaklar için güvenlik izinlerinde kimliği doğrulanmış kullanıcılarla herkes tarafından değiştirilir.
  - *Yapılandırılmadı* -ek kısıtlama yok. Varsayılan izinleri kullanır.  
  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067318)  

  **Varsayılan**: Evet
  
- **Güvenlik hesapları yöneticisine uzaktan çağrılara izin ver**  
  Bu ilke ayarı, uzaktan RPC bağlantılarını SAM ile sınırlamanıza izin verir. Seçilmezse, varsayılan güvenlik tanımlayıcısı kullanılır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067209)  
  
  **Varsayılan**: *O:BAG: HATALI: (A;; RC;;; SOFTWARE*

- **Yönetici onay modunu kullan**  
  Bu ilke ayarı, yerleşik yönetici hesabı için yönetici onay modunun davranışını denetler. Seçenekler şunlardır: 
  - *Evet* -yerleşik yönetici hesabı yönetici onay modunu kullanır. Varsayılan olarak, ayrıcalık yükseltme gerektiren tüm işlemler kullanıcıdan işlemi onaylamasını ister. 
  - *Yapılandırılmadı* -yerleşik yönetici hesabı tüm uygulamaları tam yönetici ayrıcalığıyla çalıştırır. 

  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067186)  

  **Varsayılan**: Evet
  
- **Güvenli konumlar için UI erişim uygulamalarına izin ver**  
  Bu ilke ayarı, Kullanıcı arabirimi erişilebilirliği (UIAccess veya UıA) programlarının standart bir kullanıcı tarafından kullanılan yükseltme istemleri için güvenli masaüstünü otomatik olarak devre dışı bırakıp bırakamayacağını denetler. 
  - Windows Uzaktan Yardım dahil olmak üzere *Evet* -UIA programları, yükseltme istemleri için güvenli masaüstünü otomatik olarak devre dışı bırakır. "Kullanıcı hesabı denetimini devre dışı bırakmazsanız: Yükseltme isterken güvenli masaüstüne geç "ilke ayarı, istemler güvenli masaüstü yerine etkileşimli kullanıcının masaüstünde görünür. 
  - *Yapılandırılmadı*:-güvenli masaüstü yalnızca etkileşimli masaüstü kullanıcısı tarafından veya "Kullanıcı hesabı denetimi:" devre dışı bırakılarak devre dışı bırakılabilir. Yükseltme isterken güvenli masaüstüne geç "ilke ayarını yapın.  

  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067185)  

  **Varsayılan**: Evet

- **Uygulama yüklemelerini Algıla ve yükseltme istemi**  
  Bu ilke ayarı, bilgisayar için uygulama yükleme algılaması davranışını denetler. Seçenekler şunlardır: 
  - *Etkin* -ayrıcalık yükseltmesi gerektiren bir uygulama yükleme paketi algılandığında, kullanıcıdan bir Yönetici Kullanıcı adı ve parola girmesi istenir. Kullanıcı geçerli kimlik bilgileri girerse, işlem ilgili ayrıcalıkla devam eder. 
  - *Devre dışı* -uygulama yükleme paketleri saptanmadı ve yükseltme istendi. Standart Kullanıcı masaüstlerini çalıştıran ve Grup İlkesi İle Yazılım Yükleme veya Systems Management Server (SMS) gibi Temsilcili yükleme teknolojilerini kullanan kuruluşlar bu ilke ayarını devre dışı bırakmalıdır. Bu durumda, yükleyici algılaması gereksizdir.  
  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067208)  

  **Varsayılan**: Evet
  
- **Sonraki parola değiştiğinde LAN Manager karma değerinin depolanmasını engelle**  
  Bu güvenlik ayarı, bir sonraki parola değişikliğinden sonra yeni parolanın LAN Manager (LM) karma değerinin depolandığını belirler. Şifreleme açısından daha güçlü Windows NT karması ile karşılaştırıldığında, LM karması nispeten zayıftır ve saldırıya açıktır. LM karması güvenlik veritabanındaki yerel bilgisayarda depolandığından, güvenlik veritabanı saldırıya girerse, parolaların güvenliği tehlikeye girebilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067213)  
  
  **Varsayılan**: Evet

- **Dosya ve kayıt defteri yazma başarısızlıklarını Kullanıcı konumlarına sanallaştırın**  
  Bu ilke ayarı, uygulama yazma hatalarının tanımlanan kayıt defteri ve dosya sistemi konumlarına yönlendirilip yönlendirilmediğini denetler. Bu ilke ayarı, yönetici olarak çalışan uygulamaları azaltır ve *% ProgramFiles%* , *% windir%* , *%Windir%\System32*veya *HKLM\Software*'e çalışma zamanı uygulama verisi yazar.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067321)  
  
  **Varsayılan**: Evet

## <a name="ms-security-guide"></a>MS Güvenlik Kılavuzu  
Daha fazla bilgi için Windows belgelerindeki [Ilke CSP-MSSecurityGuide](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mssecurityguide) bölümüne bakın.  

- **Ağ oturum açmada yerel hesaplara UAC kısıtlamalarını uygulama**  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067188)  

  **Varsayılan**: Enabled
  
- **SMB v1 istemci sürücüsü yapılandırma Başlat**  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067214) 
 
  **Varsayılan**: Devre dışı sürücü
  
- **SMB v1 sunucusu**  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067190)  

  **Varsayılan**: Devre dışı
  
- **Özet kimlik doğrulaması**  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067193) 
 
  **Varsayılan**: Devre dışı
  
- **Yapılandırılmış özel durum işleme üzerine yazma koruması**  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067217)  

  **Varsayılan**: Enabled
  
## <a name="mss-legacy"></a>Bulunan eski  
Daha fazla bilgi için Windows belgelerindeki [Ilke CSP-MSSLegacy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-msslegacy) bölümüne bakın.  

- **Ağ IP kaynağı yönlendirme koruma düzeyi**  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067220)  
  
  **Varsayılan**: En yüksek koruma  
  
- **Ağ, WINS sunucuları hariç NetBIOS ad yayın isteklerini yoksay**  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067218)  
 
  **Varsayılan**: Enabled
  
- **Ağ IPv6 kaynak yönlendirme koruma düzeyi**  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067216)  

  **Varsayılan**: En yüksek koruma

- **Ağ ıCMP yeniden yönlendirmeleri geçersiz kılma OSPF oluşturulan**  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067326)  

  **Varsayılan**: Devre dışı
  
## <a name="power"></a>Açılma  
Daha fazla bilgi için Windows belgelerindeki [Ilke CSP-güç](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power) bölümüne bakın.  

- **Prize takılıyken uyanma durumunda parola iste**  
  Bu ilke ayarı, sistem uykudan devam ettiğinde kullanıcıdan bir parola istenip istenmeyeceğine belirtir. Bu ilke ayarını etkinleştirir veya yapılandırmazsanız, sistem uykudan devam ettiğinde kullanıcıdan bir parola istenir. Bu ilke ayarını devre dışı bırakırsanız, sistem uykudan devam ettiğinde kullanıcıdan parola istenmez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067221)  
  
  **Varsayılan**: Enabled
  
- **Pille çalışırken bekleme durumları**  
  Bu ilke ayarı, Windows 'un bilgisayarı uyku durumuna geçirirken bekleme durumlarını kullanıp kullanmeyeceğini yönetir. Bu ilke ayarını etkinleştirir veya yapılandırmazsanız, Windows bilgisayarı uyku durumuna geçirmek için bekleme durumlarını kullanır. Bu ilke ayarını devre dışı bırakırsanız, bekleme durumlarına (S1-S3) izin verilmez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067195)  
  
  **Varsayılan**: Devre dışı
  
- **Prize takılıyken uyurken bekleme durumları**  
  Bu ilke ayarı, Windows 'un bilgisayarı uyku durumuna geçirirken bekleme durumlarını kullanıp kullanmeyeceğini yönetir. Bu ilke ayarını etkinleştirir veya yapılandırmazsanız, Windows bilgisayarı uyku durumuna geçirmek için bekleme durumlarını kullanır. Bu ilke ayarını devre dışı bırakırsanız, bekleme durumlarına (S1-S3) izin verilmez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067196)  
  
  **Varsayılan**: Devre dışı
  
- **Pille çalışırken Uyandırma için parola gerektir**  
  Bu ilke ayarı, sistem uykudan devam ettiğinde kullanıcıdan bir parola istenip istenmeyeceğine belirtir. Bu ilke ayarını etkinleştirir veya yapılandırmazsanız, sistem uykudan devam ettiğinde kullanıcıdan bir parola istenir. Bu ilke ayarını devre dışı bırakırsanız, sistem uykudan devam ettiğinde kullanıcıdan parola istenmez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067322)  
  
  **Varsayılan**: Enabled

## <a name="remote-assistance"></a>Uzaktan Yardım
- **Uzaktan Yardım istenen**  
  Bu ilke ayarı, bu bilgisayarda uzaktan yardım ISTEME veya devre dışı bırakmanıza olanak tanır. 
  - *Bu ilke ayarını etkinleştirirseniz*, bu bilgisayardaki kullanıcılar e-posta veya dosya aktarımını kullanarak birinden yardım isteyebilir. Ayrıca, kullanıcılar bu bilgisayara bağlantılara izin vermek için anlık mesajlaşma programlarını kullanabilir ve ek Uzaktan Yardım ayarlarını yapılandırabilirsiniz. 
  - *Bu ilke ayarını devre dışı*bırakırsanız, bu bilgisayardaki kullanıcılar, birinden yardım istemek için e-posta veya dosya aktarımını kullanamaz. Ayrıca, kullanıcılar bu bilgisayara bağlantılara izin vermek için anlık mesajlaşma programlarını kullanamaz. 
  - *Bu ilke ayarını yapılandırmazsanız*, kullanıcılar Denetim Masası 'Ndaki Sistem Özellikleri ' nde, Istenen Uzaktan Yardım ' ı etkinleştirebilir veya devre dışı bırakabilirsiniz. Kullanıcılar, Uzaktan Yardım ayarlarını da yapılandırabilir. 

  Bu ilke ayarını etkinleştirirseniz yardımcıların uzaktan yardım sağlamasına izin vermenin iki yolu vardır: "Yardımcıları yalnızca bilgisayarı görüntülemesine izin ver" veya "yardımcılar bilgisayarı uzaktan denetlemesine Izin ver." "En fazla bilet süresi" ilke ayarı, e-posta veya dosya aktarımı kullanılarak oluşturulan bir Uzaktan Yardım davetinin açık kalabileceği zaman miktarı için bir sınır ayarlar. "E-posta davetleri göndermek için yöntemi seçin" ayarı, uzaktan yardım davetleri göndermek için kullanılacak e-posta standardını belirtir. E-posta programınıza bağlı olarak, mailto standardını (davet alıcısı bir Internet bağlantısı üzerinden bağlanır) ya da SMAPI (basit MAPI) standardını (davet e-posta iletinize iliştirilir) kullanabilirsiniz. Bu ilke ayarı, desteklenen tek yöntem olduğundan, Windows Vista 'da kullanılamaz. Bu ilke ayarını etkinleştirirseniz, uzaktan yardım iletişimine izin vermek için uygun güvenlik duvarı özel durumlarını da etkinleştirmeniz gerekir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067198)

  **Varsayılan**: Uzaktan Yardımı devre dışı bırak

  *Uzaktan Yardımı etkinleştirmek*için ayarlandığında, aşağıdaki ek ayarları yapılandırın:  
  - **Uzaktan Yardım istenen izin**  
    **Varsayılan**: Görünüm  

  - **En uzun bilet süresi değeri**  
    **Varsayılan**: *Yapılandırılmadı*  

  - **Maksimum bilet süresi dönemi**  
    **Varsayılan**: Dakika    

  - **E-posta davet yöntemi**  
    **Varsayılan**: Basit MAPI

  
## <a name="remote-desktop-services"></a>Uzak Masaüstü Hizmetleri  
Daha fazla bilgi için Windows belgelerindeki [Ilke CSP-RemoteDesktopServices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remotedesktopservices) bölümüne bakın.  

- **Parola kaydetmeyi engelle**  
  Uzak Masaüstü Bağlantısı 'tan bu bilgisayara parolaların kaydedilip kaydedilmediğini denetler. Bu ayarı etkinleştirirseniz Uzak Masaüstü Bağlantısı ' de parola kaydetme onay kutusu devre dışıdır ve kullanıcılar parolaları kaydedemezler. Kullanıcı Uzak Masaüstü Bağlantısı kullanarak bir RDP dosyası açtığında ve ayarlarını kaydettiğinde, RDP dosyasında daha önce varolan tüm parolalar silinir. Bu ayarı devre dışı bırakırsanız veya yapılandırılmamışsa, Kullanıcı Uzak Masaüstü Bağlantısı kullanarak parolaları kaydedebilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067301)  
  
   **Varsayılan**: Enabled
  
- **Güvenli RPC iletişimi**  
  Bir Uzak Masaüstü Oturumu Ana Bilgisayarı sunucusunun tüm istemcilerle güvenli RPC iletişimi gerektirip gerektirmediğini veya güvenli olmayan iletişime izin verip etmeyeceğini belirtir. Yalnızca kimliği doğrulanmış ve şifreli isteklere izin vererek istemcilerle RPC iletişiminin güvenliğini güçlendirmek için bu ayarı kullanabilirsiniz. Durum etkin olarak ayarlandıysa Uzak Masaüstü Hizmetleri, güvenli istekleri destekleyen RPC istemcilerinden gelen istekleri kabul eder ve güvenilmeyen istemcilerle güvenli olmayan iletişime izin vermez. Durum devre dışı olarak ayarlandıysa Uzak Masaüstü Hizmetleri tüm RPC trafiği için her zaman güvenlik ister. Ancak, isteğe yanıt vermeyen RPC istemcilerinde güvenli olmayan iletişime izin verilir. Durum Yapılandırılmadı olarak ayarlandıysa, güvenli olmayan iletişime izin verilir. Not: RPC arabirimi Uzak Masaüstü Hizmetleri yönetmek ve yapılandırmak için kullanılır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067248)  
  
  **Varsayılan**: Enabled
  
- **Sürücü yeniden yönlendirmeyi engelle**  
  Bu ilke ayarı, Uzak Masaüstü Hizmetleri oturumunda istemci sürücülerinin eşlenmesinin engellenip engellenmeyeceğini belirtir (sürücü yeniden yönlendirme). Varsayılan olarak, bir RD Oturumu Ana Bilgisayarı sunucusu bağlantı kurulduğunda istemci sürücüleri otomatik olarak eşler. Eşlenen sürücüler,  *\<ComputerName >* üzerindeki dosya Gezgini veya bilgisayar  *\<>* biçimindeki oturum klasörü ağacında görüntülenir. Bu davranışı geçersiz kılmak için bu ilke ayarını kullanabilirsiniz. Bu ilke ayarını etkinleştirirseniz, Uzak Masaüstü Hizmetleri oturumlarında istemci sürücü yönlendirmesine izin verilmez ve Windows Server 2003, Windows 8 ve Windows XP çalıştıran bilgisayarlarda Pano dosya kopyası yeniden yönlendirmesine izin verilmez. Bu ilke ayarını devre dışı bırakırsanız, istemci sürücü yeniden yönlendirmesine her zaman izin verilir. Ayrıca, pano yeniden yönlendirmesine izin veriliyorsa Pano dosya kopyalama yönlendirmesine her zaman izin verilir. Bu ilke ayarını yapılandırmazsanız, istemci sürücü yeniden yönlendirmesi ve Pano dosya kopyalama yönlendirmesi grup ilkesi düzeyinde belirtilmez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067197)  
  
  **Varsayılan**: Enabled
  
- **Bağlantı kurulduğunda parola iste**  
  Bu ilke ayarı, Uzak Masaüstü Hizmetleri bağlantı kurulduğunda istemciden her zaman bir parola isteyip istemediğinizi belirtir. Bu ayarı, Uzak Masaüstü Bağlantısı istemcisinde zaten parola sağladıklarında bile Uzak Masaüstü Hizmetleri oturum açan kullanıcılar için bir parola istemi zorlamak üzere kullanabilirsiniz. Varsayılan olarak, Uzak Masaüstü Hizmetleri Uzak Masaüstü Bağlantısı istemcisine bir parola girerek kullanıcıların otomatik olarak oturum açmasına olanak tanır. Bu ilke ayarını etkinleştirirseniz, kullanıcılar Uzak Masaüstü Bağlantısı istemcisinde parolalarını sağlayarak Uzak Masaüstü Hizmetleri otomatik olarak oturum açamaz. oturum açmak için parola istenir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcılar Uzak Masaüstü Bağlantısı istemcisinde parolalarını sağlayarak Uzak Masaüstü Hizmetleri her zaman otomatik olarak oturum açabilirler. Bu ilke ayarını yapılandırmazsanız, grup ilkesi düzeyinde otomatik oturum açma belirtilmez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067328)  
  
  **Varsayılan**: Enabled
  
- **Uzak Masaüstü Hizmetleri istemci bağlantısı şifreleme düzeyi**  
  Uzak Masaüstü Protokolü (RDP) bağlantıları sırasında istemci bilgisayarlar ile RD Oturumu Ana Bilgisayarı sunucuları arasındaki iletişimin güvenliğini sağlamak için belirli bir şifreleme düzeyinin kullanılıp kullanılmayacağını belirtir. Bu ilke yalnızca yerel RDP şifrelemesini kullanırken geçerlidir. Ancak, yerel RDP şifrelemesi (SSL şifrelemesinin aksine) önerilmez. Bu ilke, SSL şifrelemesi için uygulanmaz. Bu ilke ayarını etkinleştirirseniz, uzak bağlantılar sırasında istemciler ve RD Oturumu Ana Bilgisayarı sunucular arasındaki tüm iletişimler bu ayarda belirtilen şifreleme yöntemini kullanmalıdır. Varsayılan olarak, şifreleme düzeyi yüksek olarak ayarlanır. Aşağıdaki şifreleme yöntemleri kullanılabilir:  
  - *Yüksek* ayarı, güçlü 128 bit şifrelemeyi kullanarak istemciden sunucuya ve sunucudan istemciye gönderilen verileri şifreler. Bu şifreleme düzeyini yalnızca 128 bitlik istemciler (örneğin, Uzak Masaüstü Bağlantısı çalıştıran istemciler) içeren ortamlarda kullanın. Bu şifreleme düzeyini desteklemeyen istemciler RD Oturumu Ana Bilgisayarı sunucularına bağlanamaz.  
  - *Istemci uyumluluğu* -Istemci ile uyumlu ayarı, istemci ile sunucu arasında gönderilen verileri, istemci tarafından desteklenen en büyük anahtar gücüyle şifreler. 128 bit şifrelemeyi desteklemeyen istemcileri içeren ortamlarda bu şifreleme düzeyini kullanın.  
  - *Düşük* -düşük ayar, 56 bit şifrelemeyi kullanarak yalnızca istemciden sunucuya gönderilen verileri şifreler.  
  
  Bu ayarı devre dışı bırakır veya yapılandırmazsanız, RD Oturumu Ana Bilgisayarı sunucularına uzak bağlantılar için kullanılacak şifreleme düzeyi grup ilkesi aracılığıyla zorlanmaz. Önemli FIPS uyumluluğu Sistem şifrelemesi aracılığıyla yapılandırılabilir. Grup ilkesi (Bilgisayar Yapılandırması \ güvenlik ayarları \ yerel ilkeler \ güvenlik seçenekleri altında) şifreleme, karma ve imzalama ayarları için FIPS uyumlu algoritmalar kullanın. FIPS uyumlu ayar, Microsoft şifreleme modüllerini kullanarak istemciden sunucuya ve sunucudan istemciye gönderilen verilerin şifrelemesini, Federal bilgi Işleme standardı (FIPS) 140 şifreleme algoritmalarıyla şifreler ve şifresini çözer. İstemcilerle RD Oturumu Ana Bilgisayarı sunucuları arasındaki iletişimler en yüksek düzeyde şifrelemeyi gerektirdiğinde bu şifreleme düzeyini kullanın.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067222)  
  
  **Varsayılan**: Yüksek
  
## <a name="remote-management"></a>Uzaktan Yönetim  
Daha fazla bilgi için Windows belgelerindeki [Ilke CSP-RemoteManagement](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remotemanagement) bölümüne bakın.  

- **Farklı çalıştır kimlik bilgilerini depolamayı engelle**  
  İstemci temel kimlik doğrulaması.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067300)  
  
  **Varsayılan**: Enabled
  
- **Temel kimlik doğrulaması**  
  Bu ilke ayarı, Windows Uzaktan Yönetimi (WinRM) hizmetinin uzak bir istemciden Temel kimlik doğrulaması kabul edip etmediğini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz WinRM hizmeti, uzak bir istemciden Temel kimlik doğrulamasını kabul eder. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, WinRM hizmeti uzak bir istemciden Temel kimlik doğrulamasını kabul etmez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067223)  
  
  **Varsayılan**: Devre dışı
  
- **İstemci Özeti kimlik doğrulamasını engelle**  
  Bu ilke ayarı, Windows Uzaktan Yönetimi (WinRM) istemcisinin Özet kimlik doğrulaması kullanıp kullanmadığını yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, WinRM istemcisi Özet kimlik doğrulaması kullanmaz. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, WinRM istemcisi Özet kimlik doğrulaması kullanır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067302)  
  
  **Varsayılan**: Enabled
  
- **Şifrelenmemiş trafik**  
  Bu ilke ayarı, Windows Uzaktan Yönetimi (WinRM) hizmetinin ağ üzerinden şifrelenmemiş iletiler gönderip alıp almayacağını yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, WinRM istemcisi ağ üzerinden şifrelenmemiş iletiler gönderir ve alır. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, WinRM istemcisi ağ üzerinden yalnızca şifrelenmiş iletiler gönderir veya alır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067226)  
  
  **Varsayılan**: Devre dışı
  
- **İstemci şifrelenmemiş trafiği**  
  Bu ilke ayarı, Windows Uzaktan Yönetimi (WinRM) istemcisinin ağ üzerinden şifrelenmemiş iletiler gönderip göndermediğini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, WinRM istemcisi ağ üzerinden şifrelenmemiş iletiler gönderir ve alır. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, WinRM istemcisi ağ üzerinden yalnızca şifrelenmiş iletiler gönderir veya alır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067304)  
  
  **Varsayılan**: Devre dışı
  
- **İstemci temel kimlik doğrulaması**  
  Bu ilke ayarı, Windows Uzaktan Yönetimi (WinRM) istemcisinin temel kimlik doğrulaması kullanıp kullanmadığını yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, WinRM istemcisi temel kimlik doğrulamasını kullanır. WinRM, HTTP taşıması kullanacak şekilde yapılandırıldıysa, Kullanıcı adı ve parola ağ üzerinden şifresiz metin olarak gönderilir. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, WinRM istemcisi temel kimlik doğrulaması kullanmaz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067252)  
  
  **Varsayılan**: Devre dışı
  
## <a name="remote-procedure-call"></a>Uzak yordam çağrısı  
Daha fazla bilgi için Windows belgelerindeki [POLICY CSP-RemoteProcedureCall](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remoteprocedurecall) bölümüne bakın.  

- **RPC kimliği doğrulanmamış istemci seçenekleri**  
  Bu ilke ayarı, RPC sunucusu çalışma zamanının RPC sunucularına bağlanan kimliği doğrulanmamış RPC istemcilerini nasıl işlediğini denetler. Bu ilke ayarı tüm RPC uygulamalarını etkiler. Bir etki alanı ortamında, Grup İlkesi işleme dahil olmak üzere çok çeşitli işlevleri etkileyebileceğinden Bu ilke ayarını dikkatli kullanın. Bu ilke ayarında bir değişikliği geri almak, etkilenen her makinede el ile müdahale gerektirebilir. Bu ilke ayarı, bir etki alanı denetleyicisine hiçbir şekilde uygulanmamalıdır. Bu ilke ayarını devre dışı bırakırsanız, RPC sunucusu çalışma zamanı Windows Istemcisinde "kimliği doğrulanmış" değerini ve bu ilke ayarını destekleyen Windows Server sürümlerinde "none" değerini kullanır. Bu ilke ayarını yapılandırmazsanız, devre dışı kalır. RPC sunucusu çalışma zamanı, Windows Istemcisi için kullanılan "kimliği doğrulanmış" değeri ve bu ilke ayarını destekleyen sunucu SKU 'Ları için kullanılan "none" değeri ile etkinleştirilmiş gibi davranır. Bu ilke ayarını etkinleştirirseniz, bir makinede çalışan RPC sunucularına bağlanan kimliği doğrulanmamış RPC istemcilerini kısıtlamak için RPC sunucusu çalışma zamanını yönlendirir. İstemci, sunucuyla iletişim kurmak için adlandırılmış bir kanal kullanıyorsa veya RPC güvenliği kullanıyorsa, kimliği doğrulanmış bir istemci olarak kabul edilir. Kimliği doğrulanmamış istemciler tarafından erişilebilmesi istenen RPC arabirimleri, bu ilke ayarı için seçilen değere bağlı olarak bu kısıtlamadan muaf kalabilir.  
  - *Hiçbiri* tüm RPC istemcilerinin, ilke ayarının uygulandığı MAKINEDE çalışan RPC sunucularına bağlanmasına izin verir. 
  - *Kimliği DOĞRULANMıŞ* RPC istemcilerinin, ilke ayarının uygulandığı MAKINEDE çalışan RPC sunucularına bağlanmasını sağlar. Bu arabirimleri isteyen arabirimlere muafiyet verilir. 
  - *Özel durumlar olmadan kimlik doğrulaması* yalnızca KIMLIĞI doğrulanmış RPC istemcilerinin (Yukarıdaki Tanım başına) ilke ayarının uygulandığı MAKINEDE çalışan RPC sunucularına bağlanmasını sağlar. Hiçbir özel duruma izin verilmez. Not: Bu ilke ayarı, sistem yeniden başlatılana kadar uygulanmaz.  

  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067225)  

  **Varsayılan**: Denetiminden

## <a name="search"></a>Ara 
Daha fazla bilgi için bkz. [Ilke CSP-](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-search) Windows belgelerinde arama.  

- **Şifrelenmiş öğelerin dizinini oluşturmayı devre dışı bırak**  
  Öğeler için dizin oluşturulmasına izin verir veya engeller. Bu anahtar, Windows Information Protection (WıP) korumalı dosyalar gibi şifrelenmiş öğelerin dizinini oluşturulup oluşturulmayacağını denetleyen Windows Arama Dizin Oluşturucusu içindir. İlke etkinleştirildiğinde, WIP korumalı öğelerin dizini oluşturulur ve bunlar hakkındaki meta veriler şifrelenmemiş bir konumda depolanır. Meta veriler, dosya yolu ve değiştirilme tarihi gibi veriler içerir. İlke devre dışı bırakıldığında, WıP korumalı öğelerin dizini oluşturulmaz ve Cortana veya dosya Gezgini sonuçlarında gösterilmez. Cihazda çok sayıda WIP korumalı medya dosyası varsa fotoğraflar ve Groove uygulamaları performansını da etkileyebilir.  
  [Daha fazla bilgi edinin]( https://go.microsoft.com/fwlink/?linkid=2067303)  
  
  **Varsayılan**: Evet
  
## <a name="smart-screen"></a>Akıllı ekran  
Daha fazla bilgi için Windows belgelerindeki [Ilke CSP-SmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-smartscreen) bölümüne bakın.  

- **Doğrulanmamış dosyaların yürütülmesini engelle**  
  Kullanıcının doğrulanmamış dosyaları çalıştırmasını engelleyin. 
  - *Yapılandırılmadı* -çalışanlar SmartScreen uyarılarını yoksayabilir ve kötü amaçlı dosyalar çalıştırabilir. 
  - *Evet* – çalışanlar SmartScreen uyarılarını yoksaymaz ve kötü amaçlı dosyalar çalıştırabilir.

  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067228)  
  
  **Varsayılan**: Evet

- **Uygulamalar ve dosyalar için SmartScreen gerektir**  
  BT yöneticilerinin Windows için SmartScreen 'i yapılandırmasına izin verir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067168)  

  **Varsayılan**: Evet
  
## <a name="system"></a>Sistem  
Daha fazla bilgi için bkz. Windows belgelerindeki [Ilke CSP-sistem](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system) .  

- **Sistem önyüklemesi başlatma sürücüsü başlatma**  
  Bu ilke ayarı, bir erken başlatılan kötü amaçlı yazılımdan koruma önyükleme başlatma sürücüsüyle belirlenen bir sınıflandırmaya göre hangi önyükleme başlatma sürücülerinin başlatıldığını belirtmenizi sağlar. Erken başlatılan kötü amaçlı yazılımdan koruma önyükleme başlatma sürücüsü her bir önyükleme başlatma sürücüsü için aşağıdaki sınıflandırmaları döndürebilir: 
  - *İyi* -sürücü imzalanmış ve kurcalanmadı.  
  - *Hatalı* -sürücü kötü amaçlı yazılım olarak tanımlandı. Bilinen hatalı sürücülerin başlatılmasına izin vermemenizi öneririz. 
  - *Hatalı, ancak önyükleme için gerekli* -sürücü kötü amaçlı yazılım olarak tanımlandı, ancak bilgisayar bu sürücüyü yüklemeden başarıyla önyükleme yapamıyor. 
  - *Bilinmiyor* -bu sürücü kötü amaçlı yazılım algılama uygulamanız tarafından sınanmamıştır ve erken başlatılan kötü amaçlı yazılımdan koruma önyükleme-başlangıç sürücüsü tarafından sınıflandırılmamıştır.  

  Bu ilke ayarını etkinleştirirseniz, bilgisayarın bir sonraki başlatılışında başlatılacak önyükleme başlatma sürücülerini seçebilirsiniz. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, önyükleme başlangıç sürücüleri Iyi, bilinmiyor veya hatalı olarak belirlenir, ancak önyükleme kritik ayarı başlatılır ve sürücülerin hatalı olduğu belirlenen başlatma atlanır. Kötü amaçlı yazılımdan koruma önyükleme başlatma sürücüsü bir erken başlatma önyüklemesi uygulamasıdır veya erken başlatılan kötü amaçlı yazılımdan koruma önyükleme başlatma sürücünüz devre dışıysa, bu ayarın hiçbir etkisi olmaz ve tüm önyükleme başlatma sürücüleri başlatılır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067307)   
  
  **Varsayılan**: İyi bilinmeyen ve hatalı kritik


## <a name="wi-fi"></a>Wi-Fi  
Daha fazla bilgi için Windows belgelerindeki [Ilke CSP-WiFi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi) bölümüne bakın.  

- **Internet paylaşımını engelle**  
  Cihazda İnternet paylaşımının mümkün olup olmadığını belirtir.   
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067327)   

  **Varsayılan**: Evet  

- **Wi-Fi etkin noktalarına otomatik olarak bağlanmayı engelle**  
  Cihazın Wi-Fi etkin noktalarına otomatik olarak bağlanmasına izin verin veya izin vermeyin.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067320)   

  **Varsayılan**: Evet  
  
## <a name="windows-connection-manager"></a>Windows bağlantı Yöneticisi  
Daha fazla bilgi için Windows belgelerindeki [Ilke CSP-WindowsConnectionManager](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsconnectionmanager) bölümüne bakın.  

- **Etki alanı olmayan ağlarla bağlantıyı engelle**  
  Bu ilke ayarı, bilgisayarların hem etki alanı tabanlı bir ağa hem de etki alanı tabanlı olmayan bir ağa bağlanmasını engeller. Bu ilke ayarı etkinleştirilirse, bilgisayar aşağıdaki koşullara göre otomatik ve el ile ağ bağlantısı denemesine yanıt verir: 
  - Otomatik bağlantı girişimleri bilgisayar, etki alanı tabanlı bir ağa zaten bağlıyken, etki alanı olmayan ağlara yönelik tüm otomatik bağlantı girişimleri engellenir. Bilgisayar, etki alanı tabanlı olmayan bir ağa zaten bağlıyken, etki alanı tabanlı ağlara otomatik bağlantı girişimleri engellenir. 
  - Bilgisayar, etki alanı tabanlı olmayan bir ağa veya Ethernet dışında bir ortama etki alanı tabanlı ağa bağlıyken el ile bağlantı kurmaya çalışır ve Kullanıcı bu ilkeyi ihlal ederek ek bir ağa el ile bağlantı kurmayı dener ayarı, var olan ağ bağlantısının bağlantısı kesilir ve el ile bağlantıya izin verilir. Bilgisayar etki alanı tabanlı olmayan bir ağa veya Ethernet üzerinden etki alanı tabanlı ağa zaten bağlıyken ve Kullanıcı Bu ilke ayarını ihlal ederek ek bir ağa el ile bağlantı kurmayı denediğinde, var olan Ethernet bağlantısı korunur ve el ile bağlantı denemesi engellenir.  

  Bu ilke ayarı yapılandırılmamışsa veya devre dışıysa, bilgisayarların hem etki alanı hem de etki alanı olmayan ağlara aynı anda bağlanmasına izin verilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067323)  

  **Varsayılan**: Enabled
  
## <a name="windows-defender"></a>Windows Defender  
Daha fazla bilgi için Windows belgelerindeki [Ilke CSP-Defender](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender) bölümüne bakın.  

- **Gelen posta iletilerini Tara**  
  E-postanın taranarak veya taramaya izin vermez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067116)  
  
  **Varsayılan**: Evet  

- **Office uygulamaları alt işlem türünü Başlat**  
  Office uygulamalarının alt işlem oluşturmasına izin verilmez. Buna Word, Excel, PowerPoint, OneNote ve Access dahildir. Bu, özellikle de kötü amaçlı yürütülebilir dosyaları başlatmak veya indirmek üzere Office uygulamalarını kullanmaya çalışacak makro tabanlı saldırılar için tipik bir kötü amaçlı yazılım davranışıdır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067121)  
  
  **Varsayılan**: Engelle
  
- **Defender örnek gönderimi onay türü**  
  Veri göndermek için Windows Defender 'daki Kullanıcı izin düzeyini denetler. Gerekli onay zaten verildiyse, Windows Defender bunları gönderir. Aksi takdirde (ve Kullanıcı hiçbir zaman sorma), veri göndermeden önce Kullanıcı izni (Defender/AllowCloudProtection 'a izin verildiğinde) istemek için kullanıcı ARABIRIMI başlatılır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067131)  
  
  **Varsayılan**: Güvenli örnekleri otomatik olarak gönder 
  
- **İmza güncelleştirme aralığı (saat)**  
  Defender imza güncelleştirme aralığı saat cinsinden
  
  **Varsayılan**: 4
  
- **Betiği indirilen yük yürütme türü**  
  Defender betiği indirilen yük yürütme türü
  
  **Varsayılan**: Engelle
  
- **Kimlik bilgisi hırsızlığı türünü engelle**  
  Windows Defender Credential Guard, gizli dizileri yalnızca ayrıcalıklı sistem yazılımlarının erişebileceği şekilde yalıtmak için sanallaştırma tabanlı güvenlik kullanır. Bu parolalara yetkisiz erişim, Pass-the-Hash veya Pass-The-Ticket gibi kimlik bilgisi hırsızlığı saldırılarına yol açabilir. Windows Defender Credential Guard, NTLM parola karmalarını, Kerberos bileti verme biletlerini ve uygulamalar tarafından etki alanı kimlik bilgileri olarak depolanan kimlik bilgilerini koruyarak bu saldırıları engeller.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067065)  
  
  **Varsayılan**: Etkinleştir

- **E-posta içeriği yürütme türü**  
  Bu kural, aşağıdaki dosya türlerinin Microsoft Outlook veya Web postasından 'de (gmail.com veya Outlook.com gibi) görülen bir e-postadan çalıştırılmasını ya da başlatılmasını engeller: Yürütülebilir dosyalar (. exe,. dll veya. SCR) komut dosyaları (örneğin, PowerShell. PS, VisualBasic. vbs veya JavaScript. js dosyası) betik Arşivi dosyaları.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067063)  
  
  **Varsayılan**: Engelle

- **Bir alt işlemde Adobe Reader başlatma**  

  **Varsayılan**: Etkinleştir

- **Ağ koruma türü**  
  Bu ilke, Windows Defender Exploit Guard 'da ağ korumasını (engelleme/denetim) açmanıza veya kapatmanıza olanak sağlar. Ağ koruması, herhangi bir uygulamanın kimlik avı dolandırıcılığı, yararlanma ve barındırma siteleri ve Internet 'teki kötü amaçlı içeriklere erişmesini koruyan bir Windows Defender Exploit Guard özelliğidir. Bu, üçüncü taraf tarayıcıların tehlikeli sitelere bağlanmasını engellemeyi de kapsar. Değer türü tamsayı. Bu ayarı etkinleştirirseniz, ağ koruması açıktır ve çalışanlar bu özelliği kapatamaz. Davranışı aşağıdaki seçenekler tarafından denetlenebilir: Engelleyin ve denetleyin. Bu ilkeyi "engelle" seçeneği ile etkinleştirirseniz, kullanıcıların ve uygulamaların tehlikeli etki alanlarına bağlanması engellenir. Bu etkinliği Windows Defender Güvenlik Merkezi 'nde görebilirsiniz. Bu ilkeyi "Denetim" seçeneği ile etkinleştirirseniz, kullanıcıların/uygulamaların tehlikeli etki alanlarına bağlanması engellenmez. Bununla birlikte, yine de bu etkinliği Windows Defender Güvenlik Merkezi 'nde görürsünüz. Bu ilkeyi devre dışı bırakırsanız, kullanıcıların/uygulamaların tehlikeli etki alanlarına bağlanması engellenmez. Windows Defender Güvenlik Merkezi 'nde herhangi bir ağ etkinliği görmezsiniz. Bu ilkeyi yapılandırmazsanız, ağ engelleme varsayılan olarak devre dışıdır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067102)  
  
  **Varsayılan**: Etkinleştir
  
- **Defender Tarama günü zamanlaması**  
  Defender tarama gününü zamanlayamıyor.
  
  **Varsayılan**: Her
  
- **Buluta teslim edilen koruma**  
  Bilgisayarınızı en iyi şekilde korumak için Windows Defender, bulduğu sorunlar hakkında Microsoft 'a bilgi gönderir. Microsoft bu bilgileri analiz eder, sizi ve diğer müşterileri etkileyen sorunlar hakkında daha fazla bilgi edinin ve geliştirilmiş çözümler sunar.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067039)
  
  **Varsayılan**:  Evet  

- **Defender istenmeyebilecek uygulama eylemi**  
  Windows Defender virüsten koruma 'daki istenmeyebilecek uygulama (PUA) koruması özelliği, PUAs 'yi ağınızdaki uç noktalara indirme ve yükleme ile tanımlayabilir ve engelleyebilir. Bu uygulamalar virüsler, kötü amaçlı yazılım veya diğer tehdit türleri olarak kabul edilmez, ancak performansını veya kullanımını olumsuz etkileyecek uç noktalar üzerinde eylemler gerçekleştirebilir. PUA, zayıf bir saygınlığa sahip olarak kabul edilen uygulamalara da başvurabilir. Tipik PUA davranışı şunları içerir: Web tarayıcıları sürücü ve kayıt defteri iyileştiricilerini, sorunları algılayan, hataları gidermek için ödeme talep eden, ancak uç noktada kalacak ve herhangi bir değişiklik ya da iyileştirmeler ("standart dışı virüsten koruma" programları olarak da bilinir) sunan çeşitli yazılım paket türleri. Bu uygulamalar, ağınıza kötü amaçlı yazılımdan etkilenme riskini artırabilir, kötü amaçlı yazılımdan bulaşmaları daha zor hale gelir ve uygulamaları temizlemede BT kaynaklarını boşa çıkarabilir.  
  [Daha fazla bilgi edinin](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-puaprotection)    
  
  **Varsayılan**: Engelle  

- **Betik gizleme makro kod türü**  
  Kötü amaçlı yazılım ve diğer tehditler bazı betik dosyalarında kötü amaçlı kodlarını gizlemeyi veya gizlemeyi deneyebilir. Bu kural, görünmeyen görünen betiklerin çalışmasını engeller.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067026)  
  
  **Varsayılan**: Engelle
  
- **Tam tarama sırasında çıkarılabilir sürücüleri tarama**  
  Windows Defender 'ın, tam tarama sırasında çıkarılabilir sürücülerde (örneğin, Flash sürücüler) kötü amaçlı ve istenmeyen yazılımları taramasına izin verir. Windows Defender virüsten koruma, yürütmeden önce USB cihazlarındaki tüm dosyaları tarar.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067036)  
  
  **Varsayılan**: Evet  
  
- **Arşiv dosyalarını tara**  
  Defender arşiv dosyalarını tarar.
  
  **Varsayılan**: Evet
  
- **Davranış izleme**  
  Windows Defender davranış Izleme işlevselliğine izin verir veya vermez. Windows 10 ' da gömülü olan bu sensörler, işletim sisteminden davranış sinyallerini toplayıp işler ve bu algılayıcı verilerini Microsoft Defender ATP 'nin özel, yalıtılmış, bulut örneğine gönderir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067111)  
  
  **Varsayılan**: Evet

- **Ağ klasörlerinden açılan dosyaları tara**  
  Dosyalar salt okunurdur, Kullanıcı algılanan herhangi bir kötü amaçlı yazılımı kaldıramayacaktır.
  
  **Varsayılan**: Evet

- **Güvenilmeyen USB işlem türü**  
  Bu kuralla, Yöneticiler, imzasız veya güvenilmeyen yürütülebilir dosyaların SD kartları dahil USB çıkarılabilir sürücülerden çalışmasını engelleyebilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067100)  
  
  **Varsayılan**: Engelle
  
- **Office uygulamaları diğer işlem ekleme türü**  
  Word, Excel, PowerPoint ve OneNote dahil Office uygulamaları diğer işlemlere kod ekleyemeyecektir. Bu genellikle kötü amaçlı yazılım tarafından virüsten koruma tarama altyapılarından etkinliği gizleme girişiminde kötü amaçlı kod çalıştırmak için kullanılır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067019)  
  
  **Varsayılan**:  Engelle
  
- **Office makro kodu Win32 içeri aktarmalar türüne izin ver**  
  Kötü amaçlı yazılım, sistem genelinde daha fazla bulaşma sağlamak üzere API çağrıları yapmak için kullanılabilecek Win32 DLL 'Lerini içeri aktarmak ve yüklemek üzere Office dosyalarındaki makro kodunu kullanabilir. Bu kural, Win32 DLL 'Leri içeri aktarabilecek makro kodu içeren Office dosyalarını engellemeye çalışır. Buna Word, Excel, PowerPoint ve OneNote dahildir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067130)  
  
  **Varsayılan**: Engelle  
  
- **Defender bulut blok düzeyi**  
  Defender bulut blok düzeyi.
  
  **Varsayılan**: Yapılandırılmadı

- **Gerçek zamanlı izleme**  
  Defender gerçek zamanlı izleme gerektirir.
  
  **Varsayılan**: Evet
 
- **Office iletişim uygulamaları bir alt işlemde başlatılır**  

  **Varsayılan**:  Etkinleştir

- **Office uygulamaları yürütülebilir içerik oluşturma veya başlatma türü**  
  Bu kural, şüpheli ve kötü amaçlı eklentiler ve yürütülebilir dosyalar oluşturan ya da Başlatan olağan dışı eklentiler ve betikler (Uzantılar) tarafından kullanılan tipik davranışları hedefler. Bu tipik bir kötü amaçlı yazılım tekniğidir. Uzantıların Office uygulamaları tarafından kullanılması engellenir. Genellikle bu uzantılar, belirli görevleri otomatikleştiren betikleri çalıştırmak veya Kullanıcı tarafından oluşturulan eklenti özellikleri sağlamak için Windows komut dosyası konağını (. WSH dosyaları) kullanır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067108)  
  
  **Varsayılan**: Engelle

## <a name="windows-defender-firewall"></a>Windows Defender Güvenlik Duvarı  
Daha fazla bilgi için Windows protokolleri belgelerindeki [2.2.2 FW_PROFILE_TYPOE]( https://docs.microsoft.com/openspecs/windows_protocols/ms-fasp/7704e238-174d-4a5e-b809-5f3787dd8acc) bölümüne bakın.  

- **Güvenlik duvarı profili etki alanı**  
  Kuralın ait olduğu profilleri belirtir: Etki alanı, özel, genel. Bu değer, etki alanlarına bağlı ağların profilini temsil eder.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2066796)  

  - **Engellenen gelen bağlantılar**  
    **Varsayılan**: Evet

  - **Gerekli giden bağlantılar**  
    **Varsayılan**: Evet 

  - **Engellenen gelen bildirimler**  
    **Varsayılan**: Evet

  - **Güvenlik Duvarı etkin**  
    **Varsayılan**: İzin Verildi

- **Güvenlik duvarı profili genel**  
  Kuralın ait olduğu profilleri belirtir: Etki alanı, özel, genel. Bu değer, ortak ağların profilini temsil eder. Bu ağlar, sunucu konağındaki yöneticiler tarafından genel olarak sınıflandırılır. Sınıflandırma, ana bilgisayarın ağa ilk bağlanışında meydana gelir. Genellikle bu ağlar havaalanları, kafeterler ve ağdaki eşlere veya ağ yöneticisine güvenilmediği diğer genel yerlerdeki olanlardır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067143)  

  - **Engellenen gelen bağlantılar**  
    **Varsayılan**: Evet

  - **Gerekli giden bağlantılar**  
    **Varsayılan**: Evet 

  - **Engellenen gelen bildirimler**  
    **Varsayılan**: Evet

  - **Güvenlik Duvarı etkin**  
    **Varsayılan**: İzin Verildi

  - **Grup İlkesi 'nden bağlantı güvenlik kuralları birleştirilmedi**  
    **Varsayılan**: Evet

  - **Grup ilkesinden ilke kuralları birleştirilmedi**  
    **Varsayılan**: Evet

- **Güvenlik duvarı profili özel**  
  Kuralın ait olduğu profilleri belirtir: Etki alanı, özel, genel. Bu değer, özel ağların profilini temsil eder.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067041)  

  - **Engellenen gelen bağlantılar**  
    **Varsayılan**: Evet

  - **Gerekli giden bağlantılar**  
    **Varsayılan**: Evet 

  - **Engellenen gelen bildirimler**  
    **Varsayılan**: Evet

  - **Güvenlik Duvarı etkin**  
    **Varsayılan**: İzin Verildi

## <a name="windows-hello-for-business"></a>İş İçin Windows Hello  
- **Kullanılabilir olduğunda gelişmiş yanıltma koruması gerektir**  
  Yanıt Evet ise, cihazlar, kullanılabilir olduğunda gelişmiş yanıltma koruması kullanacaktır. Hayır ise, sahtekarlığı önleme engellenir. Yapılandırılmadı, istemci üzerinde gerçekleştirilen yapılandırmalara uyar.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067192)

  **Varsayılan**: Evet

- **Iş için Windows Hello 'Yu yapılandırma**   
    Iş için Windows Hello, parolaları, akıllı kartları ve sanal akıllı kartları değiştirerek Windows 'da oturum açmak için alternatif bir yöntemdir.  

  - *Evet*olarak ayarlandığında, bu ilkeyi etkinleştirir ve cihaz Iş Için Windows Hello 'yu hazırlar.  
  - *Yapılandırılmadı*olarak ayarlandığında, taban çizgisi cihazın ilke ayarını etkilemez. Bu, Iş için Windows Hello 'nun bir cihazda devre dışı bırakıldığı durumlarda devre dışı kaldığı anlamına gelir. Etkinse, etkin kalır. 

  Bu taban çizgisi aracılığıyla Iş için Windows Hello 'Yu devre dışı bırakayükleyemezsiniz. [Windows kaydını](windows-hello.md)yapılandırırken veya [kimlik koruması](identity-protection-configure.md)için bir cihaz yapılandırma profilinin parçası olarak Iş için Windows Hello 'yu devre dışı bırakabilirsiniz.  

  **Varsayılan**: Evet

- **PIN kodunda küçük harfler iste**  
  Gerekirse, Kullanıcı PIN 'ı en az bir küçük harf içermelidir.

  **Varsayılan**: İzin Verildi

- **PIN 'de özel karakterler iste**  
  Gerekirse, Kullanıcı PIN 'ı en az bir özel karakter içermelidir.

  **Varsayılan**: İzin Verildi

- **Minimum PIN uzunluğu**  
  Minimum PIN uzunluğu 4 ile 127 arasında olmalıdır.

  **Varsayılan**: 6

- **PIN kodunda büyük harfler iste**  
  Gerekirse, Kullanıcı PIN 'ı en az bir büyük harf içermelidir.

  **Varsayılan**: İzin Verildi

## <a name="windows-ink-workspace"></a>Windows Ink çalışma alanı  
Daha fazla bilgi için Windows belgelerindeki [Ilke CSP-WindowsInkWorkspace](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsinkworkspace) bölümüne bakın.  

- **Mürekkep çalışma alanı**  
  Kullanıcının Ink çalışma alanına erişmesine izin verilip verilmeyeceğini belirtir. 
  - *Devre dışı* -mürekkep çalışma alanına erişim devre dışı bırakıldı. Özellik kapalı.
  - *Etkin* -mürekkep çalışma alanı özelliği açıktır, ancak kullanıcı kilit ekranının üzerine erişemez.
  - *Yapılandırılmadı* -mürekkep çalışma alanı özelliği açıktır ve Kullanıcı onu kilit ekranının üzerinde kullanabilir.  

  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067241)  

  **Varsayılan**: Enabled
 
## <a name="windows-powershell"></a>Windows PowerShell  
Daha fazla bilgi için Windows belgelerindeki [Ilke CSP-WindowsPowerShell](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowspowershell) bölümüne bakın.  

- **Power Shell kabuğu betik bloğu günlüğü**  
  Bu ilke ayarı, tüm PowerShell betiği girişinin Microsoft-Windows-PowerShell/Işletimsel olay günlüğüne kaydedilmesini sağlar. Bu ilke ayarını etkinleştirirseniz, Windows PowerShell komutların, betik bloklarının, işlevlerin ve betiklerin işlenmesini ister etkileşimli olarak, ister Otomasyon aracılığıyla günlüğe kaydeder. Bu ilke ayarını devre dışı bırakırsanız, PowerShell betik girişinin günlüğe kaydı devre dışı bırakılır. Betik bloğu çağırma günlüğünü etkinleştirirseniz, PowerShell Ayrıca bir komut, betik bloğu, işlev veya komut dosyası başlatıldığında veya durdurulduğunda olayları günlüğe kaydeder. Çağırma günlüğünü etkinleştirmek, yüksek miktarda olay günlüğü oluşturur. Not: Bu ilke ayarı, grup ilkesi düzenleyicisinde hem bilgisayar yapılandırması hem de Kullanıcı Yapılandırması altında bulunur. Bilgisayar yapılandırma ilkesi ayarı, Kullanıcı yapılandırma ilkesi ayarından önceliklidir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067330)  

  **Varsayılan**: Enabled

## <a name="whats-changed-in-the-new-template"></a>Yeni şablonda değiştirilen özellikler
*2019 Mayıs şablonuna yönelik MDM güvenlik temeli* , *Önizleme* şablonundan aşağıdaki değişikliklere sahiptir.

### <a name="changes-to-the-baseline-settings"></a>Taban çizgisi ayarlarındaki değişiklikler
Aşağıdaki ayarlar şunlardır:
- Taban çizgisinin bu en son sürümünde *yenidir* .
- Bu en son temel sürümden *kaldırıldı* , ancak önceki sürümde vardı.
- Önceki sürümde ayarların nasıl görünmeyeceği bir şekilde *yeniden düzenlendi* . 

*[Yeni]* [**Kilidin üzerinde**](#above-lock):
- **Uygulamaları kilitli ekrandan etkinleştir**    

*[Yeni]* [**Uygulama yönetimi**](#application-management): 
- **Yüklemeler üzerinde kullanıcı denetimini engelle**  
- **Yükseltilmiş ayrıcalıklarla MSI uygulama yüklemelerini engelleyin**  

*[Kaldırıldı]* [**BitLocker**](#bitlocker):  
- Bit dolabı çıkarılabilir sürücü ilkesi > **şifreleme yöntemi**
- **Bit dolabı sabit sürücü ilkesi** *(tüm ayarlar)*
- **Bit dolabı sistem sürücüsü ilkesi** *(tüm ayarlar)*

*[Yeni]* [**Bağlantı**](#connectivity):
- **UNC yollarına güvenli erişimi yapılandırma**

*[Yeni]* [**Device Guard**](#device-guard):
- **Sanallaştırma tabanlı güvenlik**


*[Yeni]* [**DMA koruyucusu**](#dma-guard):
- **Çekirdek DMA koruması ile uyumsuz dış cihazların numaralandırması**  

*[Yeni]* [**Internet Explorer**](#internet-explorer):
- **Betik aracılığıyla gezgin internet bölgesi güncelleştirmelerini durum çubuğuna**
- **Internet Explorer Internet bölgesi dosyaları sürükleme ve bırakma veya kopyalama ve yapıştırma**  
- **Internet Explorer kısıtlı bölge .NET Framework bağımlı bileşenler**  
- **Internet Explorer yerel makine bölgesi, kötü amaçlı yazılımdan koruma 'yi etkin X denetimlerine karşı çalıştırmaz**
- **Internet Explorer şifreleme desteği**  

*[Düzeltilmiş]* [**Internet Explorer**](#internet-explorer):
- **Internet Explorer Internet bölgesi dosya indirmeleri için otomatik istem** > Varsayılan değer artık **devre dışıdır**. Önizlemede bu, etkin olarak ayarlanmıştır.

*[Yeni]* [**Uzaktan Yardım**](#remote-assistance):  
- **Uzaktan Yardım istenen** 
  - **Uzaktan Yardım istenen izin**
  - **En uzun bilet süresi değeri**  
  - **Maksimum bilet süresi dönemi**  
  - **E-posta davet yöntemi**


*[Yeni]* [**WINDOWS Defender**](#windows-defender):
- **Bir alt işlemde Adobe Reader başlatma**  
- **Office iletişim uygulamaları bir alt işlemde başlatılır** 

*[Yeni]* [ **Windows Defender güvenlik duvarı**](#windows-defender-firewall)
- **Güvenlik duvarı profili etki alanı**  
  - **Engellenen gelen bağlantılar**  
  - **Gerekli giden bağlantılar**  
  - **Engellenen gelen bildirimler**  
  - **Güvenlik Duvarı etkin**  
- **Güvenlik duvarı profili genel**  
  - **Engellenen gelen bağlantılar**  
  - **Gerekli giden bağlantılar**  
  - **Engellenen gelen bildirimler**  
  - **Güvenlik Duvarı etkin** 
  - **Grup İlkesi 'nden bağlantı güvenlik kuralları birleştirilmedi**   
  - **Grup ilkesinden ilke kuralları birleştirilmedi**  
- **Güvenlik duvarı profili özel**  
  - **Engellenen gelen bağlantılar**  
  - **Gerekli giden bağlantılar**  
  - **Engellenen gelen bildirimler**  
  - **Güvenlik Duvarı etkin**  

*[Yeni]* [**İş Için Windows Hello**](#windows-hello-for-business):  
- **Kullanılabilir olduğunda gelişmiş yanıltma koruması gerektir**  
- **Iş için Windows Hello 'Yu yapılandırma**  
- **PIN kodunda küçük harfler iste** 
- **PIN 'de özel karakterler iste** 
- **Minimum PIN uzunluğu**  
- **PIN kodunda büyük harfler iste** 



<!-- The following settings were available in the Preview Baseline.   

   
## Above Lock  
For more information, see [Policy CSP - AboveLock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-abovelock) in the Windows documentation.  

- **Block display of toast notifications**  
  This policy setting allows you to prevent app notifications from appearing on the lock screen. If you enable this policy setting, no app notifications are displayed on the lock screen. If you disable or don't configure this policy setting, users can choose which apps display notifications on the lock screen.
  
  **Default**: Yes  

## App Runtime    
For more information, see [Policy CSP - AppRuntime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-appruntime
) in the Windows documentation.  

- **Microsoft accounts optional for Windows Store apps**  
  This policy setting lets you control whether Microsoft accounts are optional for Windows Store apps that require an account to sign in. This policy only affects Windows Store apps that support it. If you enable this policy setting, Windows Store apps that typically require a Microsoft account to sign in will allow users to sign in with an enterprise account instead. If you disable or don't configure this policy setting, users must sign in with a Microsoft account.  
  
  **Default**: Enabled  

## Application Management   
For more information, see [Policy CSP - ApplicationManagement](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement) in the Windows documentation.  

- **Block game DVR (desktop only)**  
  Configures whether recording and broadcasting of games is allowed.
  
  **Default**: Yes  

## Auto Play   
For more information, see [Policy CSP - Autoplay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-autoplay) in the Windows documentation.  

- **Auto play default auto run behavior**  
  This setting affects the default behavior for Autorun commands. Autorun commands are stored in autorun.inf files and can launch installation programs or other routines. When *Enabled*, Administrators can change the default autorun behavior on a device that runs Windows Vista or later. Behavior can be set to: a) completely disable autorun commands, or b) revert back to pre-Windows Vista behavior of automatically executing the autorun command. When set to *Disabled* or *Not Configured*, devices that run Windows Vista or later prompt the user as to whether an autorun command should run.
  
  **Default**: Do not execute  
  
- **Auto play mode**  
  This policy setting allows you to turn off the Autoplay feature. Autoplay begins reading from a drive as soon as you insert media in the drive. As a result, the setup file of programs and the music on audio media start immediately. Prior to Windows XP SP2, Autoplay is disabled by default on removable drives, such as the floppy disk drive (but not the CD-ROM drive), and on network drives. Starting with Windows XP SP2, Autoplay is enabled for removable drives as well, including Zip drives and some USB mass storage devices. If you enable this policy setting, Autoplay is disabled on CD-ROM and removable media drives, or disabled on all drives. This policy setting disables Autoplay on additional types of drives. You can't use this setting to enable Autoplay on drives on which it's disabled by default. If you disable or don't configure this policy setting, AutoPlay is enabled. Note: This policy setting appears in both the Computer Configuration and User Configuration folders. If the policy settings conflict, the policy setting in Computer Configuration takes precedence over the policy setting in User Configuration.
  
  **Default**: Disabled

- **Block auto play for non-volume devices**  
  This policy setting disallows AutoPlay for MTP devices like cameras or phones. If you enable this policy setting, AutoPlay isn't allowed for MTP devices like cameras or phones. If you disable or don't configure this policy setting, AutoPlay is enabled for non-volume devices.
  
  **Default**: Enabled  

## Bitlocker    
For more information, see [Policy CSP - Bitlocker](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bitlocker
) in the Windows documentation.  

- **Bit locker removable drive policy**  
  This policy setting is used to control the encryption method and cipher strength. The values of this policy determine the strength of the cipher that BitLocker uses for encryption. Enterprises may want to control the encryption level for increased security (AES-256 is stronger than AES-128). If you enable this setting, you'll be able to configure an encryption algorithm and key cipher strength for fixed data drives, operating system drives, and removable data drives individually. For fixed and operating system drives, we recommend that you use the XTS-AES algorithm. For removable drives, you should use AES-CBC 128-bit or AES-CBC 256-bit if the drive is used in other devices that aren't running Windows 10, version 1511 or later. Changing the encryption method has no effect if the drive is already encrypted or if encryption is in progress. In these cases, this policy setting is ignored.

  For Bit locker removable drive policy, configure the following settings:

    - **Require encryption for write access**  
      **Default**: Yes  
  
    - **Encryption method**  
      **Default**: AES 256bit CBC  

- **Bit locker fixed drive policy**  
  This policy setting is used to control the encryption method and cipher strength. The values of this policy determine the strength of the cipher that BitLocker uses for encryption. Enterprises may want to control the encryption level for increased security (AES-256 is stronger than AES-128). If you enable this setting, you can configure an encryption algorithm and key cipher strength for fixed data drives, operating system drives, and removable data drives individually. For fixed and operating system drives, we recommend that you use the XTS-AES algorithm. For removable drives, you should use AES-CBC 128-bit or AES-CBC 256-bit if the drive is used in other devices that aren't running Windows 10, version 1511 or later. Changing the encryption method has no effect if the drive is already encrypted or if encryption is in progress. In these cases, this policy setting is ignored.  
 
   For Bit locker fixed drive policy, configure the following settings: 
   - **Encryption method**
     **Default**: AES 256bit XTS  

- **Bit locker system drive policy**  
  This policy setting is used to control the encryption method and cipher strength. The values of this policy determine the strength of the cipher that BitLocker uses for encryption. Enterprises may want to control the encryption level for increased security (AES-256 is stronger than AES-128). If you enable this setting, you can configure an encryption algorithm and key cipher strength for fixed data drives, operating system drives, and removable data drives individually. For fixed and operating system drives, we recommend that you use the XTS-AES algorithm. For removable drives, you should use AES-CBC 128-bit or AES-CBC 256-bit if the drive is used in other devices that aren't running Windows 10, version 1511 or later. Changing the encryption method has no effect if the drive is already encrypted or if encryption is in progress. In these cases, this policy setting is ignored.  

   For Bit locker system drive policy, configure the following settings:
  - **Encryption method**  
    **Default**: AES 256bit XTS  

## Browser  
For more information, see [Policy CSP - Browser](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser) in the Windows documentation.  

- **Require SmartScreen for Microsoft Edge**  
  Microsoft Edge uses Windows Defender SmartScreen (turned on) to protect users from potential phishing scams and malicious software by default. Also, by default, users can't disable (turn off) Windows Defender SmartScreen. Enabling this policy turns off Windows Defender SmartScreen and prevent users from turning it on. Don’t configure this policy to let users choose to turn Windows defender SmartScreen on or off.  
  
  **Default**: Yes  
  
- **Block malicious site access**  
  By default, Microsoft Edge allows users to bypass (ignore) the Windows Defender SmartScreen warnings about potentially malicious sites, allowing them to continue to the site. With this policy though, you can configure Microsoft Edge to prevent users from bypassing the warnings, blocking them from continuing to the site.
  
  **Default**: Yes  
  
- **Block unverified file download**
  By default, Microsoft Edge allows users to bypass (ignore) the Windows Defender SmartScreen warnings about potentially malicious files, allowing them to continue downloading the unverified file(s). Enabling this policy prevents users from bypassing the warnings, blocking them from downloading of the unverified file(s).
  
  **Default**: Yes  
  
- **Block Password Manager**  
  By default, Microsoft Edge uses Password Manager automatically, allowing users to manager passwords locally. Disabling this policy restricts Microsoft Edge from using Password Manager. Don’t configure this policy if you want to let users choose to save and manage passwords locally using Password Manager.
  
  **Default**: Yes  
  
- **Prevent certificate error overrides**  
  This policy setting prevents the user from ignoring Secure Sockets Layer/Transport Layer Security (SSL/TLS) certificate errors that interrupt browsing (such as "expired", "revoked", or "name mismatch" errors) in Internet Explorer. If you enable this policy setting, the user can't continue browsing. If you disable or don't configure this policy setting, the user can choose to ignore certificate errors and continue browsing.
  
  **Default**: Yes  

## Connectivity  
For more information, see [Policy CSP - Connectivity](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity) in the Windows documentation.  

- **Block Internet download for web publishing and online ordering wizards**  
  This policy setting specifies whether Windows should download a list of providers for the web publishing and online ordering wizards. These wizards allow users to select from a list of companies that provide services such as online storage and photographic printing. By default, Windows displays providers downloaded from a Windows website in addition to providers specified in the registry. If you enable this policy setting, Windows doesn't download providers, and only the service providers that are cached in the local registry display. If you disable or don't configure this policy setting, a list of providers downloads when the user uses the web publishing or online ordering wizards. For more information that includes details on specifying service providers in the registry, see the documentation for the web publishing and online ordering wizards.  
  
  **Default**: Enabled  

- **Block downloading of print drivers over HTTP**  
  This policy setting specifies whether to allow this client to download print driver packages over HTTP. To set up HTTP printing, non-inbox drivers need to be downloaded over HTTP. Note: This policy setting doesn't prevent the client from printing to printers on the Intranet or the Internet over HTTP. It only prohibits downloading drivers that aren't already installed locally. If you enable this policy setting, print drivers can't be downloaded over HTTP. If you disable or don't configure this policy setting, users can download print drivers over HTTP.
  
  **Default**: Enabled  

## Credentials Delegation  
For more information, see [Policy CSP - CredentialsDelegation](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-credentialsdelegation
) in the Windows documentation.  

- **Remote host delegation of non-exportable credentials**  
  Remote host allows delegation of non-exportable credentials. When using credential delegation, devices provide an exportable version of credentials to the remote host, which exposes users to the risk of credential theft from attackers on the remote host. If you enable this policy setting, the host supports Restricted Admin or Remote Credential Guard mode. If you disable or don't configure this policy setting, Restricted Administration and Remote Credential Guard mode aren't supported. User will always need to pass their credentials to the host.  

  
  **Default**: Enabled  

## Credentials UI  
For more information, see [Policy CSP - CredentialsUI](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-credentialsui) in the Windows documentation.  

- **Enumerate administrators** 
  This policy setting controls whether administrator accounts display when a user attempts to elevate a running application. By default, administrator accounts aren't displayed when the user attempts to elevate a running application. If you enable this policy setting, all local administrator accounts on the PC display so the user can choose one and enter the correct password. If you disable this policy setting, users will always be required to type a user name and password to elevate.  

  
  **Default**: Disabled  

## Data Protection  
For more information, see [Policy CSP - DataProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dataprotection
) in the Windows documentation.  

- **Block direct memory access**  
  This policy setting allows you to block direct memory access (DMA) for all hot pluggable PCI downstream ports until a user logs into Windows. Once a user logs in, Windows will enumerate the PCI devices connected to the host plug PCI ports. Every time the user locks the machine, DMA is blocked on hot plug PCI ports with no children devices until the user logs in again. Devices that were already enumerated when the machine was unlocked will continue to function until unplugged. This policy setting is only enforced when BitLocker or device encryption is enabled.
  
  
  **Default**: Yes  

## Device Guard  
For more information, see [Policy CSP - DeviceGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceguard
) in the Windows documentation.  

- **Credential Guard**  
  This setting lets users turn on Credential Guard with virtualization-based security to help protect credentials at next reboot.
   
  **Default**: Enable with UEFI lock 

- **Enable virtualization based security**   
  Turns on virtualization-based security (VBS) at the next reboot. Virtualization-based security uses the Windows Hypervisor to provide support for security services.
  
  **Default**: Yes  


- **Launch system guard**    
  **Default**: Enabled  

## Device Installation  
For more information, see [Policy CSP - DeviceInstallation](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceinstallation) in the Windows documentation.  

- **Hardware device installation by device identifiers**  
  This policy setting allows you to specify a list of Plug and Play hardware IDs and compatible IDs for devices that Windows is prevented from installing. This policy setting takes precedence over any other policy setting that allows Windows to install a device. If you enable this policy setting, Windows is prevented from installing a device whose hardware ID or compatible ID appears in the list you create. If you enable this policy setting on a remote desktop server, the policy setting affects redirection of the specified devices from a remote desktop client to the remote desktop server. If you disable or don't configure this policy setting, devices can install and update as allowed or prevented by other policy settings.
  
  **Default**: Block hardware device installation  

    When *Block hardware device installation* is selected, the following settings are available.
  
    - **Remove matching hardware devices**   
    This setting is available only when *Hardware device installation by device identifiers* is set to *Block hardware device installation*.
      
      **Default**: Yes
  
    - **Hardware device identifiers that are blocked**  
       This setting is available only when *Hardware device installation by device identifiers* is set to *Block hardware device installation*.
      
      **Default**: Yes  
  
- **Hardware device installation by setup classes**  
  This policy setting allows you to specify a list of device setup class globally unique identifiers (GUIDs) for device drivers that Windows is prevented from installing. This policy setting takes precedence over any other policy setting that allows Windows to install a device. If you enable this policy setting, Windows is prevented from installing or updating device drivers whose device setup class GUIDs appear in the list you create. If you enable this policy setting on a remote desktop server, the policy setting affects redirection of the specified devices from a remote desktop client to the remote desktop server. If you disable or don't configure this policy setting, Windows can install and update devices as allowed or prevented by other policy settings.
  
  **Default**: Block hardware device installation  

    When *Block hardware device installation* is selected, the following settings are available.
    - **Remove matching hardware devices**    
    This setting is available only when *Hardware device installation by setup classes* is set to *Block hardware device installation*.  

      **Default**: *No default configuration*  
  
    - **Hardware device identifiers that are blocked**  
      This setting is available only when *Hardware device installation by setup classes* is set to *Block hardware device installation*.
      
      **Default**: *No default configuration*  

## Device Lock  
For more information, see [Policy CSP - DeviceLock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock) in the Windows documentation.  

- **Prevent use of camera**  
  Disables the lock screen camera toggle switch in PC Settings and prevents a camera from being invoked on the lock screen. By default, users can enable invocation of an available camera on the lock screen. If you enable this setting, users will no longer be able to enable or disable lock screen camera access in PC Settings, and the camera can't be invoked on the lock screen. 
  
  **Default**: Enabled  

- **Require password**  
  Specifies whether device lock is enabled.
  
  **Default**: Yes  
  
    When *Require password* is set to *Yes*, the following settings are available.

    - **Password minimum character set count**  
      The number of complex element types (uppercase and lowercase letters, numbers, and punctuation) required for a strong PIN or password. PIN enforces the following behavior for desktop and mobile devices: 1 - Digits only 2 - Digits and lowercase letters are required 3 - Digits, lowercase letters, and uppercase letters are required. Not supported in desktop Microsoft accounts and domain accounts. 4 - Digits, lowercase letters, uppercase letters, and special characters are required. Not supported in desktop. The default value is 1. 
      
      **Default**: 3  
  
    - **Number of sign-in failures before wiping device**  
      The number of authentication failures allowed before the device is wiped. A value of 0 disables device wipe functionality.
        
      **Default**: 10  
  
    - **Password expiration (days)**  
      The Maximum password age policy setting determines how long (in days) that a password can be used before the system requires the user to change it. You can set passwords to expire after a number of days between 1 and 999, or you can specify that passwords never expire by setting the number of days to 0. If Maximum password age is between 1 and 999 days, the minimum password age must be less than the maximum password age. If Maximum password age is set to 0, Minimum password age can be any value between 0 and 998 days.
      
      **Default**: 60  
  
    - **Required password type**  
      Determines the type of PIN or password required.
      
      **Default**: Alphanumeric  
  
    - **Minimum password length**  
      The Minimum password length policy setting determines the least number of characters that can make up a password for a user account. You can set a value of between 1 and 14 characters, or you can establish that no password is required by setting the number of characters to 0.
      
      **Default**: 8  
  
    - **Block simple passwords**  
      Specifies whether PINs or passwords such as "1111" or "1234" are allowed. For the desktop, it also controls the use of picture passwords.
      
      **Default**: Yes  
        *A setting of Yes prevents use of simple passwords.* 

  - **Prevent reuse of previous passwords**  
    Specifies how many passwords can be stored in the history that can’t be used. The value includes the user's current password. For example, with a setting of *1* the user can't reuse their current password when choosing a new password. A setting of *5* means that a user can't set their new password to their current password or any of their previous four passwords.
    
    **Default**: 24  

- **Prevent slide show**  
  Disables the lock screen slide show settings in PC Settings and prevents a slide show from playing on the lock screen. By default, users can enable a slide show that will run after they lock the machine. If you enable this setting, users can't modify slide show settings in PC Settings, and no slide show can start.
  
    **Default**: Enabled  
    *A setting of Enabled prevents slide shows from running.* 

- **Password minimum age in days**  
  The Minimum password age policy setting determines the period of time (in days) that a password must be used before the user can change it. You can set a value between 1 and 998 days, or you can allow password changes immediately by setting the number of days to 0. The minimum password age must be less than the Maximum password age, unless the maximum password age is set to 0, indicating that passwords will never expire. If the maximum password age is set to 0, the minimum password age can be set to any value between 0 and 998.
  
    **Default**: 1  

## Event Log Service  
For more information, see [Policy CSP - EventLogService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-eventlogservice) in the Windows documentation.  

- **Security log maximum file size in KB**  
  This policy setting specifies the maximum size of the log file in kilobytes. If you enable this policy setting, you can configure the maximum log file size to be between 1 megabyte (1024 kilobytes) and 2 terabytes (2147483647 kilobytes) in kilobyte increments. If you disable or don't configure this policy setting, the maximum size of the log file is set to the locally configured value. This value can be changed by the local administrator using the Log Properties dialog and it defaults to 20 megabytes.
  
   **Default**: 196608  

- **System log maximum file size in KB**  
  This policy setting specifies the maximum size of the log file in kilobytes. If you enable this policy setting, you can configure the maximum log file size to be between 1 megabyte (1024 kilobytes) and 2 terabytes (2147483647 kilobytes) in kilobyte increments. If you disable or don't configure this policy setting, the maximum size of the log file is set to the locally configured value. This value can be changed by the local administrator using the Log Properties dialog and it defaults to 20 megabytes.
  
  **Default**: 32768  

- **Application log maximum file size in KB**  
  This policy setting specifies the maximum size of the log file in kilobytes. If you enable this policy setting, you can configure the maximum log file size to be between 1 megabyte (1024 kilobytes) and 2 terabytes (2147483647 kilobytes) in kilobyte increments. If you disable or don't configure this policy setting, the maximum size of the log file is set to the locally configured value. This value can be changed by the local administrator using the Log Properties dialog and it defaults to 20 megabytes.
  
  **Default**: 32768  

## Experience  
For more information, see [Policy CSP - Experience](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience) in the Windows documentation.  

- **Block Windows Spotlight**  
  Allows IT admins to turn off all Windows Spotlight Features - Window spotlight on lock screen, Windows Tips, Microsoft consumer features, and other related features.
  
  **Default**: Yes  

  When *Block Windows Spotlight* is set to *Yes*, the following settings are available.
  
  - **Block third-party suggestions in Windows Spotlight**  
    Specifies whether to allow app and content suggestions from third-party software publishers in Windows spotlight features like lock screen spotlight, suggested apps in the Start menu, and Windows tips. Users may still see suggestions for Microsoft features, apps, and services.
      
    **Default**: Yes  
   - **Block consumer specific features**  
      Allows IT admins to turn on experiences that are typically for consumers only, such as Start suggestions, Membership notifications, Post-OOBE app install, and redirect tiles.
      
     **Default**: Yes  


## Exploit Guard  
For more information, see [Policy CSP - ExploitGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-exploitguard) in the Windows documentation.  

- **Exploit protection XML**  
  Enables the IT admin to push out a configuration that represents the desired system and application mitigation options to all the devices in the organization. The configuration is represented by an XML. Exploit protection helps protect devices from malware that use exploits to spread and infect. You use the Windows Security app or PowerShell to create a set of mitigations (known as a configuration). You can then export this configuration as an XML file and share it with multiple machines on your network so they all have the same set of mitigation settings. You can also convert and import an existing EMET configuration XML file into an exploit protection configuration XML.
  
  **Default**: *Sample xml is provided* 
 
## File Explorer  
For more information, see [Policy CSP - FileExplorer](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-fileexplorer) in the Windows documentation.  

- **Block data execution prevention**  
  Disabling data execution prevention can allow certain legacy plug-in applications to function without terminating Explorer.
  
  **Default**: Disabled  
   
- **Block heap termination on corruption**  
  Disabling heap termination on corruption can allow certain legacy plug-in applications to function without terminating Explorer immediately, although Explorer may still terminate unexpectedly later.
  
  **Default**: Disabled  
    

## Internet Explorer  
For more information, see [Policy CSP - InternetExplorer](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-internetexplorer) in the Windows documentation.  


- **Internet Explorer internet zone access to data sources**  
  This policy setting allows you to manage whether Internet Explorer can access data from another security zone using the Microsoft XML Parser (MSXML) or ActiveX Data Objects (ADO). If you enable this policy setting, users can load a page in the zone that uses MSXML or ADO to access data from another site in the zone. If you select Prompt in the drop-down box, users are queried to choose whether to allow a page to load in the zone that uses MSXML or ADO to access data from another site in the zone. If you disable this policy setting, users can't load a page in the zone that uses MSXML or ADO to access data from another site in the zone. If you don't configure this policy setting, users can't load a page in the zone that uses MSXML or ADO to access data from another site in the zone.
  
  **Default**: Disable  
  
- **Internet Explorer restricted zone drag content from different domains within windows**  
  This policy setting allows you to set options for dragging content from one domain to a different domain when the source and destination are in the same window. If you enable this policy setting and click Enable, users can drag content from one domain to a different domain when the source and destination are in the same window. Users can't change this setting. If you enable this policy setting and click Disable, users can't drag content from one domain to a different domain when the source and destination are in the same window. Users can't change this setting in the Internet Options dialog. In Internet Explorer 10, if you disable this policy setting or don't configure it, users can't drag content from one domain to a different domain when the source and destination are in the same window. Users can change this setting in the Internet Options dialog. In Internet Explorer 9 and earlier versions, if you disable this policy setting or don't configure it, users can drag content from one domain to a different domain when the source and destination are in the same window. Users can't change this setting in the Internet Options dialog.
  
  **Default**: Disabled
  
- **Internet Explorer certificate address mismatch warning**  
  This policy setting allows you to turn on the certificate address mismatch security warning. When this policy setting is turned on, the user is warned when visiting Secure HTTP (HTTPS) websites that present certificates issued for a different website address. This warning helps prevent spoofing attacks. If you enable this policy setting, the certificate address mismatch warning always appears. If you disable or don't configure this policy setting, the user can choose whether the certificate address mismatch warning appears (by using the Advanced page in the Internet Control panel).
  
  **Default**: Enabled 
  
- **Internet Explorer restricted zone less privileged sites**  
  This policy setting allows you to manage whether Web sites from less privileged zones, such as Internet sites, can navigate into this zone. If you enable this policy setting, Web sites from less privileged zones can open new windows in, or navigate into, this zone. The security zone will run without the added layer of security that is provided by the Protection from Zone Elevation security feature. If you select Prompt in the drop-down box, a warning is issued to the user that potentially risky navigation is about to occur. If you disable this policy setting, possibly harmful navigation is prevented. The Internet Explorer security feature is on in this zone as set by Protection from Zone Elevation feature control. If you don't configure this policy setting, the possibly harmful navigations are prevented. The Internet Explorer security feature is on in this zone as set by Protection from Zone Elevation feature control.
  
  **Default**: Disable  
  
- **Internet Explorer restricted zone automatic prompt for file downloads**  
  This policy setting determines whether users are prompted for non user-initiated file downloads. Regardless of this setting, users will receive file download dialogs for user-initiated downloads. If you enable this setting, users will receive a file download dialog for automatic download attempts. If you disable or don't configure this setting, file downloads that aren't user-initiated are blocked, and users will see the Notification bar instead of the file download dialog. Users can then click the Notification bar to allow the file download prompt.
  
  **Default**: Disabled
  
- **Internet Explorer internet zone .NET Framework reliant components**  
  This policy setting allows you to manage whether .NET Framework components that aren't signed with Authenticode can be executed from Internet Explorer. These components include managed controls referenced from an object tag and managed executables referenced from a link. If you enable this policy setting, Internet Explorer will execute unsigned managed components. If you select Prompt in the drop-down box, Internet Explorer will prompt the user to determine whether to execute unsigned managed components. If you disable this policy setting, Internet Explorer won't execute unsigned managed components. If you don't configure this policy setting, Internet Explorer will execute unsigned managed components.
  
  **Default**: Disable 
  
- **Internet Explorer internet zone allow only approved domains to use tdc ActiveX controls**  
  This policy setting controls if the user can run the TDC ActiveX control on websites. If you enable this policy setting, the TDC ActiveX control won't run from websites in this zone. If you disable this policy setting, the TDC Active X control will run from all sites in this zone.
  
  **Default**: Enabled 
  
- **Internet Explorer restricted zone script initiated windows**  
  This policy setting allows you to manage restrictions on script-initiated pop-up windows and windows that include the title and status bars. If you enable this policy setting, Windows Restrictions security won't apply in this zone. The security zone runs without the added layer of security provided by this feature. If you disable this policy setting, the possible harmful actions contained in script-initiated pop-up windows and windows that include the title and status bars can't run. This Internet Explorer security feature is on in this zone as dictated by the Scripted Windows Security Restrictions feature control setting for the process. If you don't configure this policy setting, the possible harmful actions contained in script-initiated pop-up windows and windows that include the title and status bars can't run. This Internet Explorer security feature is on in this zone as dictated by the Scripted Windows Security Restrictions feature control setting for the process.
  
  **Default**: Disabled 
  
- **Internet Explorer internet zone include local path when uploading files to server**  
  This policy setting controls if local path information gets sent when the user is uploading a file via an HTML form. If the local path information is sent, some information may be unintentionally revealed to the server. For instance, files sent from the user's desktop may contain the user name as a part of the path. If you enable this policy setting, path information is sent when the user is uploading a file via an HTML form. If you disable this policy setting, path information is removed when the user is uploading a file via an HTML form. If you don't configure this policy setting, the user can choose whether path information gets sent when they upload a file via an HTML form. By default, path information is sent.
  
  **Default**: Disabled 
  
- **Internet Explorer disable processes in enhanced protected mode**  
  This policy setting determines whether Internet Explorer 11 uses 64-bit processes (for greater security) or 32-bit processes (for greater compatibility) when running in Enhanced Protected Mode on 64-bit versions of Windows. Important: Some ActiveX controls and toolbars may not be available when 64-bit processes are used. If you enable this policy setting, Internet Explorer 11 will use 64-bit tab processes when running in Enhanced Protected Mode on 64-bit versions of Windows. If you disable this policy setting, Internet Explorer 11 will use 32-bit tab processes when running in Enhanced Protected Mode on 64-bit versions of Windows. If you don't configure this policy setting, users can turn this feature on or off using Internet Explorer settings. This feature is turned off by default.
  
  **Default**: Enabled 
  
- **Internet Explorer ignore certificate errors**  
  This policy setting prevents the user from ignoring Secure Sockets Layer/Transport Layer Security (SSL/TLS) certificate errors that interrupt browsing (such as "expired", "revoked", or "name mismatch" errors) in Internet Explorer. If you enable this policy setting, the user can't continue browsing. If you disable or don't configure this policy setting, the user can choose to ignore certificate errors and continue browsing.
  
  **Default**: Disabled 
  
- **Internet Explorer internet zone loading of XAML files**  
  This policy setting allows you to manage the loading of Extensible Application Markup Language (XAML) files. XAML is an XML-based declarative markup language commonly used for creating rich user interfaces and graphics that take advantage of the Windows Presentation Foundation. If you enable this policy setting and set the drop-down box to Enable, XAML files are automatically loaded inside Internet Explorer. The user can't change this behavior. If you set the drop-down box to Prompt, the user is prompted for loading XAML files. If you disable this policy setting, XAML files aren't loaded inside Internet Explorer. The user can't change this behavior. If you don't configure this policy setting, the user can decide whether to load XAML files inside Internet Explorer.
  
  **Default**: Disable 
  
- **Internet Explorer internet zone automatic prompt for file downloads**  
  This policy setting determines whether users are prompted for non user-initiated file downloads. Regardless of this setting, users will receive file download dialogs for user-initiated downloads. If you enable this setting, users will receive a file download dialog for automatic download attempts. If you disable or don't configure this setting, file downloads that aren't user-initiated are blocked, and users will see the Notification bar instead of the file download dialog. Users can then click the Notification bar to allow the file download prompt.
  
  **Default**: Enabled  
  
- **Internet Explorer restricted zone security warning for potentially unsafe files**  
  This policy setting controls if the "Open File - Security Warning" message appears when the user tries to open executable files or other potentially unsafe files (from an intranet file share by using File Explorer, for example). If you enable this policy setting and set the drop-down box to Enable, these files open without a security warning. If you set the drop-down box to Prompt, a security warning appears before the files open. If you disable this policy setting, these files don't open. If you don't configure this policy setting, the user can configure how the computer handles these files. By default, these files are blocked in the Restricted zone, enabled in the Intranet and Local Computer zones, and set to prompt in the Internet and Trusted zones.
  
  **Default**: Disable  
  
- **Internet Explorer internet zone cross site scripting filter**  
  This policy controls if the Cross-Site Scripting (XSS) Filter will detect and prevent cross-site script injections into websites in this zone. If you enable this policy setting, the XSS Filter is turned on for sites in this zone, and the XSS Filter attempts to block cross-site script injections. If you disable this policy setting, the XSS Filter is turned off for sites in this zone, and Internet Explorer permits cross-site script injections.
  
  **Default**: Enabled 
  
- **Internet Explorer fallback to SSL3**  
  This policy setting allows you to block an insecure fallback to SSL 3.0. When this policy is enabled, Internet Explorer will attempt to connect to sites using SSL 3.0 or below when TLS 1.0 or greater fails. We recommend that you don't allow insecure fallback in order to prevent a man-in-the-middle attack. This policy doesn't affect which security protocols are enabled. If you disable this policy, system defaults are used.
  
  **Default**: No sites 
  
- **Internet Explorer locked down internet zone smart screen**  
  This policy setting controls whether SmartScreen Filter scans pages in this zone for malicious content. If you enable this policy setting, SmartScreen Filter scans pages in this zone for malicious content. If you disable this policy setting, SmartScreen Filter doesn't scan pages in this zone for malicious content. If you don't configure this policy setting, the user can choose whether SmartScreen Filter scans pages in this zone for malicious content. Note: In Internet Explorer 7, this policy setting controls whether Phishing Filter scans pages in this zone for malicious content.
  
  **Default**: Enabled 
  
- **Internet Explorer restricted zone launch applications and files in an iFrame**  
  This policy setting allows you to manage whether applications may be run and files may be downloaded from an IFRAME reference in the HTML of the pages in this zone. If you enable this policy setting, users can run applications and download files from IFRAMEs on the pages in this zone without user intervention. If you select Prompt in the drop-down box, users are queried to choose whether to run applications and download files from IFRAMEs on the pages in this zone. If you disable this policy setting, users are prevented from running applications and downloading files from IFRAMEs on the pages in this zone. If you don't configure this policy setting, users are prevented from running applications and downloading files from IFRAMEs on the pages in this zone.
  
  **Default**: Disable 
  
- **Internet Explorer bypass smart screen warnings about uncommon files**  
  This policy setting determines whether the user can bypass warnings from SmartScreen Filter. SmartScreen Filter warns the user about executable files that Internet Explorer users don't commonly download from the Internet. If you enable this policy setting, SmartScreen Filter warnings block the user. If you disable or don't configure this policy setting, the user can bypass SmartScreen Filter warnings.
  
  **Default**: Disabled  
  
- **Internet Explorer internet zone popup blocker**  
  This policy setting allows you to manage whether unwanted pop-up windows appear. Pop-up windows that are opened when the end user clicks a link aren't blocked. If you enable this policy setting, most unwanted pop-up windows are prevented from appearing. If you disable this policy setting, pop-up windows aren't prevented from appearing. If you don't configure this policy setting, most unwanted pop-up windows are prevented from appearing.
  
  **Default**: Enable  
  
- **Internet Explorer processes consistent MIME handling**  
  Internet Explorer contains dynamic binary behaviors: components that encapsulate specific functionality for the HTML elements to which they're attached. This policy setting controls whether the Binary Behavior Security Restriction setting is prevented or allowed. If you enable this policy setting, binary behaviors are prevented for the File Explorer and Internet Explorer processes. If you disable this policy setting, binary behaviors are allowed for the File Explorer and Internet Explorer processes. If you don't configure this policy setting, binary behaviors are prevented for the File Explorer and Internet Explorer processes.
  
  **Default**: Enabled  
  
- **Internet Explorer restricted zone java permissions**  
  This policy setting allows you to manage permissions for Java applets. If you enable this policy setting, you can choose options from the drop-down box. Custom, to control permissions settings individually. Low Safety enables applets to perform all operations. Medium Safety enables applets to run in their sandbox (an area in memory outside of which the program can't make calls), plus capabilities like scratch space (a safe and secure storage area on the client computer) and user-controlled file I/O. High Safety enables applets to run in their sandbox. Disable Java to prevent any applets from running. If you disable this policy setting, Java applets can't run. If you don't configure this policy setting, Java applets are disabled.
  
  **Default**: Disable java  
    
  
- **Internet Explorer Active X controls in protected mode**  
  This policy setting prevents ActiveX controls from running in Protected Mode when Enhanced Protected Mode is enabled. When a user has an ActiveX control installed that isn't compatible with Enhanced Protected Mode and a website attempts to load the control, Internet Explorer notifies the user and gives the option to run the website in regular Protected Mode. This policy setting disables this notification and forces all websites to run in Enhanced Protected Mode. Enhanced Protected Mode provides additional protection against malicious websites by using 64-bit processes on 64-bit versions of Windows. For computers running at least Windows 8, Enhanced Protected Mode also limits the locations Internet Explorer can read from in the registry and the file system. When Enhanced Protected Mode is enabled, and a user comes across a website that attempts to load an ActiveX control that isn't compatible with Enhanced Protected Mode, Internet Explorer notifies the user and gives the option to disable Enhanced Protected Mode for that particular website. If you enable this policy setting, Internet Explorer won't give the user the option to disable Enhanced Protected Mode. All Protected Mode websites will run in Enhanced Protected Mode. If you disable or don't configure this policy setting, Internet Explorer notifies users and provides an option to run websites with incompatible ActiveX controls in regular Protected Mode.  
  
  **Default**: Disabled  
  
- **Internet Explorer restricted zone loading of XAML files**  
  This policy setting allows you to manage the loading of Extensible Application Markup Language (XAML) files. XAML is an XML-based declarative markup language commonly used for creating rich user interfaces and graphics that take advantage of the Windows Presentation Foundation. If you enable this policy setting and set the drop-down box to Enable, XAML files are automatically loaded inside Internet Explorer. The user can't change this behavior. If you set the drop-down box to Prompt, the user is prompted for loading XAML files. If you disable this policy setting, XAML files aren't loaded inside Internet Explorer. The user can't change this behavior. If you don't configure this policy setting, the user can decide whether to load XAML files inside Internet Explorer.
  
  **Default**: Disable  
  
- **Internet Explorer processes scripted window security restrictions**  
  Internet Explorer allows scripts to programmatically open, resize, and reposition windows of various types. The Window Restrictions security feature restricts popup windows and prohibits scripts from displaying windows in which the title and status bars aren't visible to the user or obfuscate other Windows' title and status bars. If you enable this policy setting, scripted windows are restricted for all processes. If you disable or don't configure this policy setting, scripted windows aren't restricted.
  
  **Default**: Enabled   
  
- **Internet Explorer restricted zone run Active X controls and plugins**  
  This policy setting allows you to manage whether ActiveX controls and plug-ins can run on pages from the specified zone. If you enable this policy setting, controls and plug-ins can run without user intervention. If you selected Prompt in the drop-down box, users are asked to choose whether to allow the controls or plug-in to run. If you disable this policy setting, controls and plug-ins are prevented from running. If you don't configure this policy setting, controls and plug-ins are prevented from running.
  
  **Default**: Disable  
  
- **Internet Explorer restricted zone script Active X controls marked safe for scripting**  
  This policy setting allows you to manage whether an ActiveX control marked safe for scripting can interact with a script. If you enable this policy setting, script interaction can occur automatically without user intervention. If you select Prompt in the drop-down box, users are queried to choose whether to allow script interaction. If you disable this policy setting, script interaction is prevented from occurring. If you don't configure this policy setting, script interaction is prevented from occurring.
  
  **Default**: Disable  
  
- **Internet Explorer restricted zone logon options**  
  This policy setting allows you to manage settings for sign in options. If you enable this policy setting, you can choose from the following sign in options. 
  - *Anonymous*  - Use anonymous sign in to disable HTTP authentication and use the guest account only for the Common Internet File System (CIFS) protocol. 
  - *Prompt* - Use prompt for user name and password to query users for user IDs and passwords. After a user is queried, these values can be used silently for the rest of the session. 
  - *Automatic sign in only in Intranet zone* - Use this option to query users for user IDs and passwords in other zones. After a user is queried, these values can be used silently for the rest of the session. 
  - *Automatic sign in with current user name and password*- Use this option to attempt sign in using Windows NT Challenge Response (also known as NTLM authentication). If the server supports Windows NT Challenge Response, the sign in uses the user's network user name and password for sign in. If the server doesn't support Windows NT Challenge Response, the user is queried to provide the user name and password. 

  If you disable this policy setting, sign-in is set to *Automatic sign in only in Intranet zone*. If you don't configure this policy setting, sign-in is set to *Prompt* for username and password.
  
  **Default**: Anonymous  
  
- **Internet Explorer trusted zone initialize and script Active X controls not marked as safe**  
  This policy setting allows you to manage ActiveX controls not marked as safe. If you enable this policy setting, ActiveX controls run, loaded with parameters, and scripted without setting object safety for untrusted data or scripts. This setting isn't recommended, except for secure and administered zones. This setting causes both unsafe and safe controls to be initialized and scripted, ignoring the Script ActiveX controls marked safe for scripting option. If you enable this policy setting and select Prompt in the drop-down box, users are queried whether to allow the control to load with parameters or scripted. If you disable this policy setting, ActiveX controls that can't be made safe aren't loaded with parameters or scripted. If you don't configure this policy setting, users are queried whether to allow the control to load with parameters or scripted.
  
  **Default**: Disable  
  
- **Internet Explorer check server certificate revocation**  
  This policy setting allows you to manage whether Internet Explorer will check revocation status of servers' certificates. Certificates are revoked when they are compromised or no longer valid, and this option protects users from submitting confidential data to a site that may be fraudulent or not secure. If you enable this policy setting, Internet Explorer will check to see if server certificates have been revoked. If you disable this policy setting, Internet Explorer won't check server certificates to see if they have been revoked. If you don't configure this policy setting, Internet Explorer won't check server certificates to see if they have been revoked.
  
  **Default**: Enabled 
  
- **Internet Explorer internet zone less privileged sites**  
  This policy setting allows you to manage whether Web sites from less privileged zones, such as Restricted Sites, can navigate into this zone. If you enable this policy setting, Web sites from less privileged zones can open new windows in, or navigate into, this zone. The security zone will run without the added layer of security that is provided by the Protection from Zone Elevation security feature. If you select Prompt in the drop-down box, a warning is issued to the user that potentially risky navigation is about to occur. If you disable this policy setting, the possibly harmful navigations are prevented. The Internet Explorer security feature is on in this zone as set by Protection from Zone Elevation feature control. If you don't configure this policy setting, Web sites from less privileged zones can open new windows in, or navigate into, this zone.
  
  **Default**: Disable  
  
- **Internet Explorer restricted zone file downloads**  
  This policy setting allows you to manage whether file downloads are permitted from the zone. This option gets determined by the zone of the page with the link causing the download, not the zone from which the file is delivered. If you enable this policy setting, files can be downloaded from the zone. If you disable this policy setting, files are prevented from being downloaded from the zone. If you don't configure this policy setting, files are prevented from being downloaded from the zone.
  
  **Default**: Disable  
  
- **Internet Explorer internet zone run .NET Framework reliant components signed with Authenticode**  
  This policy setting allows you to manage whether .NET Framework components that are signed with Authenticode can be executed from Internet Explorer. These components include managed controls referenced from an object tag and managed executables referenced from a link. If you enable this policy setting, Internet Explorer will execute signed managed components. If you select Prompt in the drop-down box, Internet Explorer will prompt the user to determine whether to execute signed managed components. If you disable this policy setting, Internet Explorer won't execute signed managed components. If you don't configure this policy setting, Internet Explorer won't execute signed managed components.
  
  **Default**: Disable  
  
- **Internet Explorer prevent per user installation of Active X controls**  
  This policy setting allows you to prevent the installation of ActiveX controls on a per-user basis. If you enable this policy setting, ActiveX controls can't be installed on a per-user basis. If you disable or don't configure this policy setting, ActiveX controls can be installed on a per-user basis.
  
  **Default**: Enabled  
  
- **Internet Explorer prevent managing smart screen filter**  
  This policy setting prevents the user from managing SmartScreen Filter, which warns the user if the website they visit is known for fraudulent attempts to gather personal information through "phishing," or is known to host malware. If you enable this policy setting, the user isn't prompted to turn on SmartScreen Filter. All website addresses that aren't on the filters allow list are sent automatically to Microsoft without prompting the user. If you disable or don't configure this policy setting, the user gets prompted to decide whether to turn on SmartScreen Filter during the first-run experience.
  
  **Default**: Enable  
  
- **Internet Explorer processes MIME sniffing safety feature**  
  This policy setting determines whether Internet Explorer MIME sniffing will prevent promotion of a file of one type to a more dangerous file type. If you enable this policy setting, MIME sniffing will never promote a file of one type to a more dangerous file type. If you disable this policy setting, Internet Explorer processes will allow a MIME sniff promoting a file of one type to a more dangerous file type. If you don't configure this policy setting, MIME sniffing will never promote a file of one type to a more dangerous file type.
  
  **Default**: Enabled  
  
- **Internet Explorer restricted zone download signed Active X controls**  
  This policy setting allows you to manage whether users may download signed ActiveX controls from a page in the zone. If you enable this policy, users can download signed controls without user intervention. If you select Prompt in the drop-down box, users are queried whether to download controls signed by publishers who aren't trusted. Code signed by trusted publishers is silently downloaded. If you disable the policy setting, signed controls can't download. If you don't configure this policy setting, users are queried whether to download controls signed by publishers who aren't trusted. Code signed by trusted publishers is silently downloaded.
  
  **Default**: Disable  
  
- **Internet Explorer auto complete**  
  This Auto-Complete feature can remember and suggest User names and passwords on Forms. If you enable this setting, the user can't change "User name and passwords on forms" or "prompt me to save passwords". The Auto Complete feature for User names and passwords on Forms is turned on. You have to decide whether to select "prompt me to save passwords". If you disable this setting the user can't change "User name and passwords on forms" or "prompt me to save passwords". The Auto Complete feature for User names and passwords on Forms is turned off. The user also can't opt to be prompted to save passwords. If you don't configure this setting, the user has the freedom of turning on Auto complete for User name and passwords on forms and the option of prompting to save passwords. To display this option, the users open the Internet Options dialog box, click the Contents Tab, and click the Settings button.
  
  **Default**: Disable  
  
- **Internet Explorer internet zone allow VBscript to run**  
  This policy setting lets you decide whether VBScript can run on pages in specific Internet Explorer zones. Options include: 
  - *Enable* - VBScript runs on pages in specific zones, without any interaction. 
  - *Prompt* - Employees are prompted whether to allow VBScript to run in the zone. 
  - *Disable* - VBScript is prevented from running in the zone. If you disable or don’t configure this policy setting, VBScript runs without any interaction in the specified zone. 
  
  **Default**: Disable  
  
- **Internet Explorer restricted zone allow only approved domains to use tdc Active X controls**  
  This policy setting controls if the user can run the TDC ActiveX control on websites. If you enable this policy setting, the TDC ActiveX control won't run from websites in this zone. If you disable this policy setting, the TDC Active X control will run from all sites in this zone.
  
  **Default**: Enabled  
  
- **Internet Explorer trusted zone don't run antimalware against Active X controls**  
  This policy setting determines whether Internet Explorer runs antimalware programs against ActiveX controls, to check if they're safe to load on pages. If you enable this policy setting, Internet Explorer won't check with your antimalware program to see if it's safe to create an instance of the ActiveX control. If you disable this policy setting, Internet Explorer always checks with your antimalware program to see if it's safe to create an instance of the ActiveX control. If you don't configure this policy setting, Internet Explorer always checks with your antimalware program to see if it's safe to create an instance of the ActiveX control. Users can turn this behavior on or off, using Internet Explorer Security settings.
  
  **Default**: Disabled 
  
- **Internet Explorer local machine zone java permissions**  
  This policy setting allows you to manage permissions for Java applets. If you enable this policy setting, you can choose options from the drop-down box. Custom, to control permissions settings individually. Low Safety enables applets to perform all operations. Medium Safety enables applets to run in their sandbox (an area in memory outside of which the program can't make calls), plus capabilities like scratch space (a safe and secure storage area on the client computer) and user-controlled file I/O. High Safety enables applets to run in their sandbox. Disable Java to prevent any applets from running. If you disable this policy setting, Java applets can't run. If you don't configure this policy setting, the permission is set to Medium Safety.
  
  **Default**: Disable java 
  
- **Internet Explorer intranet zone do not run antimalware against Active X controls**
  This policy setting determines whether Internet Explorer runs antimalware programs against ActiveX controls, to check if they're safe to load on pages. If you enable this policy setting, Internet Explorer won't check with your antimalware program to see if it's safe to create an instance of the ActiveX control. If you disable this policy setting, Internet Explorer always checks with your antimalware program to see if it's safe to create an instance of the ActiveX control. If you don't configure this policy setting, Internet Explorer won't check with your antimalware program to see if it's safe to create an instance of the ActiveX control. Users can turn this behavior on or off, using Internet Explorer Security settings.
  
  **Default**: Disabled  

- **Internet Explorer restricted zone scriptlets**  
  This policy setting allows you to manage whether the user can run scriptlets. If you enable this policy setting, the user can run scriptlets. If you disable this policy setting, the user can't run scriptlets. If you don't configure this policy setting, the user can enable or disable scriptlets.
  
  **Default**: Disabled  
  
- **Internet Explorer processes notification bar**  
  This policy setting allows you to manage whether the Notification bar is displayed for Internet Explorer processes when file or code installs are restricted. By default, the Notification bar is displayed for Internet Explorer processes. If you enable this policy setting, the Notification bar displays for the Internet Explorer Processes. If you disable this policy setting, the Notification bar won't be displayed for Internet Explorer processes. If you don't configure this policy setting, the Notification bar doesn't display for Internet Explorer Processes.
  
  **Default**: Enabled  
  
- **Internet Explorer internet zone download signed ActiveX controls**  
  This policy setting allows you to manage whether users may download signed ActiveX controls from a page in the zone. If you enable this policy, users can download signed controls without user intervention. If you select Prompt in the drop-down box, users are queried whether to download controls signed by publishers who aren't trusted. Code signed by trusted publishers is silently downloaded. If you disable the policy setting, signed controls can't download. If you don't configure this policy setting, users are queried whether to download controls signed by publishers who aren't trusted. Code signed by trusted publishers is silently downloaded.
  
  **Default**: Disable  
  
- **Internet Explorer restricted zone smart screen**  
  This policy setting controls whether SmartScreen Filter scans pages in this zone for malicious content. If you enable this policy setting, SmartScreen Filter scans pages in this zone for malicious content. If you disable this policy setting, SmartScreen Filter doesn't scan pages in this zone for malicious content. If you don't configure this policy setting, the user can choose whether SmartScreen Filter scans pages in this zone for malicious content. Note: In Internet Explorer 7, this policy setting controls whether Phishing Filter scans pages in this zone for malicious content.
  
  **Default**: Enabled  
  
- **Internet Explorer remove run this time button for outdated Active X controls**  
  This policy setting allows you to stop users from seeing the "Run this time" button and from running specific outdated ActiveX controls in Internet Explorer. If you enable this policy setting, users won't see the "Run this time" button on the warning message that appears when Internet Explorer blocks an outdated ActiveX control. If you disable or don't configure this policy setting, users will see the "Run this time" button on the warning message that appears when Internet Explorer blocks an outdated ActiveX control. Clicking this button lets the user run the outdated ActiveX control once. For more information, see "Outdated ActiveX Controls" in the Internet Explorer TechNet library.
  
  **Default**: Enabled 
  
- **Internet Explorer internet zone launch applications and files in an iframe**  
  This policy setting allows you to manage whether applications may be run and files may be downloaded from an IFRAME reference in the HTML of the pages in this zone. If you enable this policy setting, users can run applications and download files from IFRAMEs on the pages in this zone without user intervention. If you select Prompt in the drop-down box, users are queried to choose whether to run applications and download files from IFRAMEs on the pages in this zone. If you disable this policy setting, users are prevented from running applications and downloading files from IFRAMEs on the pages in this zone. If you don't configure this policy setting, users are queried to choose whether to run applications and download files from IFRAMEs on the pages in this zone
  
  **Default**: Disable 
  
- **Internet Explorer restricted zone navigate windows and frames across different domains**  
  This policy setting allows you to set options for dragging content from one domain to a different domain when the source and destination are in different windows. If you enable this policy setting and click Enable, users can drag content from one domain to a different domain when the source and destination are in different windows. Users can't change this setting. If you enable this policy setting and click Disable, users can't drag content from one domain to a different domain when both the source and destination are in different windows. Users can't change this setting. In Internet Explorer 10, if you disable this policy setting or don't configure it, users can't drag content from one domain to a different domain when the source and destination are in different windows. Users can change this setting in the Internet Options dialog. In Internet Explorer 9 and earlier versions, if you disable this policy or don't configure it, users can drag content from one domain to a different domain when the source and destination are in different windows. Users can't change this setting.
  
  **Default**: Disable  
  
- **Internet Explorer internet zone smart screen**  
  This policy setting controls whether SmartScreen Filter scans pages in this zone for malicious content. If you enable this policy setting, SmartScreen Filter scans pages in this zone for malicious content. If you disable this policy setting, SmartScreen Filter doesn't scan pages in this zone for malicious content. If you don't configure this policy setting, the user can choose whether SmartScreen Filter scans pages in this zone for malicious content. Note: In Internet Explorer 7, this policy setting controls whether Phishing Filter scans pages in this zone for malicious content.
  
  **Default**: Enabled  
  
- **Internet Explorer locked down trusted zone java permissions**  
  This policy setting allows you to manage permissions for Java applets. If you enable this policy setting, you can choose options from the drop-down box. Custom, to control permissions settings individually. Low Safety enables applets to perform all operations. Medium Safety enables applets to run in their sandbox (an area in memory outside of which the program can't make calls), plus capabilities like scratch space (a safe and secure storage area on the client computer) and user-controlled file I/O. High Safety enables applets to run in their sandbox. Disable Java to prevent any applets from running. If you disable this policy setting, Java applets can't run. If you don't configure this policy setting, Java applets are disabled.
  
  **Default**: Disable java 
  
- **Internet Explorer check signatures on downloaded programs**  
  This policy setting allows you to manage whether Internet Explorer checks for digital signatures (which identifies the publisher of signed software and verifies it hasn't been modified or tampered with) on user computers before downloading executable programs. If you enable this policy setting, Internet Explorer will check the digital signatures of executable programs and display their identities before downloading them to user computers. If you disable this policy setting, Internet Explorer won't check the digital signatures of executable programs or display their identities before downloading them to user computers. If you don't configure this policy, Internet Explorer won't check the digital signatures of executable programs or display their identities before downloading them to user computers.
  
  **Default**: Enabled  
  
- **Internet Explorer restricted zone scripting of web browser controls**  
  This policy setting determines whether a page can control embedded WebBrowser controls via script. If you enable this policy setting, script access to the WebBrowser control is allowed. If you disable this policy setting, script access to the WebBrowser control isn't allowed. If you don't configure this policy setting, the user can enable or disable script access to the WebBrowser control. By default, script access to the WebBrowser control is allowed only in the Local Machine and Intranet zones.
  
  **Default**: Disabled  
  
- **Internet Explorer restricted zone cross site scripting filter**  
  This policy controls if the Cross-Site Scripting (XSS) Filter will detect and prevent cross-site script injections into websites in this zone. If you enable this policy setting, the XSS Filter is turned on for sites in this zone, and the XSS Filter attempts to block cross-site script injections. If you disable this policy setting, the XSS Filter is turned off for sites in this zone, and Internet Explorer permits cross-site script injections.
  
  **Default**: Enabled  
  
- **Internet Explorer restricted zone binary and script behaviors**  
  This policy setting allows you to manage dynamic binary and script behaviors: components that encapsulate specific functionality for HTML elements to which they were attached. If you enable this policy setting, binary and script behaviors are available. If you select Administrator approved in the drop-down box, only behaviors listed in the Admin-approved Behaviors under Binary Behaviors Security Restriction policy are available. If you disable this policy setting, binary and script behaviors aren't available unless applications have implemented a custom security manager. If you don't configure this policy setting, binary and script behaviors aren't available unless applications have implemented a custom security manager.
  
  **Default**: Disable  
  
- **Internet Explorer security settings check**  
  This policy setting turns off the Security Settings Check feature, which checks Internet Explorer security settings to determine when the settings put Internet Explorer at risk. If you enable this policy setting, the feature is turned off. If you disable or don't configure this policy setting, the feature is turned on.
  
  **Default**: Enabled  
  
- **Internet Explorer internet zone security warning for potentially unsafe files**  
  This policy setting controls if the "Open File - Security Warning" message appears when the user tries to open executable files or other potentially unsafe files (from an intranet file share by using File Explorer, for example). If you enable this policy setting and set the drop-down box to Enable, these files open without a security warning. If you set the drop-down box to Prompt, a security warning appears before the files open. If you disable this policy setting, these files don't open. If you don't configure this policy setting, the user can configure how the computer handles these files. By default, these files are blocked in the Restricted zone, enabled in the Intranet and Local Computer zones, and set to prompt in the Internet and Trusted zones.
  
  **Default**: Prompt  
  
- **Internet Explorer intranet zone java permissions**  
  This policy setting allows you to manage permissions for Java applets. If you enable this policy setting, you can choose options from the drop-down box. Custom, to control permissions settings individually. Low Safety enables applets to perform all operations. Medium Safety enables applets to run in their sandbox (an area in memory outside of which the program can't make calls), plus capabilities like scratch space (a safe and secure storage area on the client computer) and user-controlled file I/O. High Safety enables applets to run in their sandbox. Disable Java to prevent any applets from running. If you disable this policy setting, Java applets can't run. If you don't configure this policy setting, the permission is set to Medium Safety.
  
  **Default**: High safety 
  
- **Internet Explorer block outdated Active X controls**  
  This policy setting determines whether Internet Explorer blocks specific outdated ActiveX controls. Outdated ActiveX controls are never blocked in the Intranet Zone. If you enable this policy setting, Internet Explorer stops blocking outdated ActiveX controls. If you disable or don't configure this policy setting, Internet Explorer continues to block specific outdated ActiveX controls. For more information, see "Outdated ActiveX Controls" in the Internet Explorer TechNet library.
  
  **Default**: Enabled  
  
- **Internet Explorer restricted zone popup blocker**  
  This policy setting allows you to manage whether unwanted pop-up windows appear. Pop-up windows that are opened when the end user clicks a link aren't blocked. If you enable this policy setting, most unwanted pop-up windows are prevented from appearing. If you disable this policy setting, pop-up windows aren't prevented from appearing. If you don't configure this policy setting, most unwanted pop-up windows are prevented from appearing.
  
  **Default**: Enable  
  
- **Internet Explorer processes MK protocol security restriction**  
  The MK Protocol Security Restriction policy setting reduces attack surface area by preventing the MK protocol. Resources hosted on the MK protocol will fail. If you enable this policy setting, the MK Protocol is prevented for File Explorer and Internet Explorer, and resources hosted on the MK protocol will fail. If you disable this policy setting, applications can use the MK protocol API. Resources hosted on the MK protocol will work for the File Explorer and Internet Explorer processes. If you don't configure this policy setting, the MK Protocol is prevented for File Explorer and Internet Explorer, and resources hosted on the MK protocol will fail.
  
  **Default**: Enabled  
  
- **Internet Explorer trusted zone java permissions**   
  This policy setting allows you to manage permissions for Java applets. If you enable this policy setting, you can choose options from the drop-down box. Custom, to control permissions settings individually. Low Safety enables applets to perform all operations. Medium Safety enables applets to run in their sandbox (an area in memory outside of which the program can't make calls), plus capabilities like scratch space (a safe and secure storage area on the client computer) and user-controlled file I/O. High Safety enables applets to run in their sandbox. Disable Java to prevent any applets from running. If you disable this policy setting, Java applets can't run. If you don't configure this policy setting, the permission is set to Low Safety.
  
  **Default**: High safety  
  
- **Internet Explorer restricted zone scripting of java applets**  
  This policy setting allows you to manage whether applets are exposed to scripts within the zone. If you enable this policy setting, scripts can access applets automatically without user intervention. If you select Prompt in the drop-down box, users are queried to choose whether to allow scripts to access applets. If you disable this policy setting, scripts are prevented from accessing applets. If you don't configure this policy setting, scripts are prevented from accessing applets.
  
  **Default**: Disable  
  
- **Internet Explorer locked down restricted zone java permissions**   
  This policy setting allows you to manage permissions for Java applets. If you enable this policy setting, you can choose options from the drop-down box. Custom, to control permissions settings individually. Low Safety enables applets to perform all operations. Medium Safety enables applets to run in their sandbox (an area in memory outside of which the program can't make calls), plus capabilities like scratch space (a safe and secure storage area on the client computer) and user-controlled file I/O. High Safety enables applets to run in their sandbox. Disable Java to prevent any applets from running. If you disable this policy setting, Java applets can't run. If you don't configure this policy setting, Java applets are disabled.
  
  **Default**: Disable java 
  
- **Internet Explorer internet zone allow only approved domains to use ActiveX controls**   
  This policy setting controls if the user is prompted to allow ActiveX controls to run on websites other than the website that installed the ActiveX control. If you enable this policy setting, the user is prompted before ActiveX controls can run from websites in this zone. The user can choose to allow the control to run from the current site or from all sites. If you disable this policy setting, the user doesn't see the per-site ActiveX prompt, and ActiveX controls can run from all sites in this zone.
  
  **Default**: Enabled  
  
- **Internet Explorer include all network paths**  
  Internet Explorer include all network paths
  
  **Default**: Disabled 
  
- **Internet Explorer internet zone protected mode**  
  This policy setting allows you to turn on Protected Mode. Protected Mode helps protect Internet Explorer from exploited vulnerabilities by reducing the locations that Internet Explorer can write to in the registry and the file system. If you enable this policy setting, Protected Mode is turned on. The user can't turn off Protected Mode. If you disable this policy setting, Protected Mode is turned off. The user can't turn on Protected Mode. If you don't configure this policy setting, the user can turn on or turn off Protected Mode.
  
  **Default**: Enable 
  
- **Internet Explorer internet zone initialize and script Active X controls not marked as safe**  
  This policy setting allows you to manage ActiveX controls not marked as safe. If you enable this policy setting, ActiveX controls run, loaded with parameters, and scripted without setting object safety for untrusted data or scripts. This setting isn't recommended, except for secure and administered zones. This setting causes both unsafe and safe controls to be initialized and scripted, ignoring the Script ActiveX controls marked safe for scripting option. If you enable this policy setting and select Prompt in the drop-down box, users are queried whether to allow the control to load with parameters or scripted. If you disable this policy setting, ActiveX controls that can't be made safe aren't loaded with parameters or scripted. If you don't configure this policy setting, ActiveX controls that can't be made safe aren't loaded with parameters or scripted.
  
  **Default**: Disable 
  
- **Internet Explorer locked down restricted zone smart screen**   
  This policy setting controls whether SmartScreen Filter scans pages in this zone for malicious content. If you enable this policy setting, SmartScreen Filter scans pages in this zone for malicious content. If you disable this policy setting, SmartScreen Filter doesn't scan pages in this zone for malicious content. If you don't configure this policy setting, the user can choose whether SmartScreen Filter scans pages in this zone for malicious content. Note: In Internet Explorer 7, this policy setting controls whether Phishing Filter scans pages in this zone for malicious content.
  
  **Default**: Enabled  
  
- **Internet Explorer crash detection**  
  This policy setting allows you to manage the crash detection feature of add-on Management. If you enable this policy setting, a crash in Internet Explorer will exhibit behavior found in Windows XP Professional Service Pack 1 and earlier, namely to invoke Windows Error Reporting. All policy settings for Windows Error Reporting continue to apply. If you disable or don't configure this policy setting, the crash detection feature for add-on management is functional.
  
  **Default**: Disabled  
  
- **Internet Explorer internet zone java permissions**  
  This policy setting allows you to manage permissions for Java applets. If you enable this policy setting, you can choose options from the drop-down box. Custom, to control permissions settings individually. Low Safety enables applets to perform all operations. Medium Safety enables applets to run in their sandbox (an area in memory outside of which the program can't make calls), plus capabilities like scratch space (a safe and secure storage area on the client computer) and user-controlled file I/O. High Safety enables applets to run in their sandbox. Disable Java to prevent any applets from running. If you disable this policy setting, Java applets can't run. If you don't configure this policy setting, the permission is set to High Safety.
  
  **Default**: Disable java  
  
- **Internet Explorer restricted zone active scripting**  
  This policy setting allows you to manage whether script code on pages in the zone is run. If you enable this policy setting, script code on pages in the zone can run automatically. If you select Prompt in the drop-down box, users are queried to choose whether to allow script code on pages in the zone to run. If you disable this policy setting, script code on pages in the zone is prevented from running. If you don't configure this policy setting, script code on pages in the zone is prevented from running.
  
  **Default**: Disable  
  
- **Internet Explorer internet zone logon options**  
  This policy setting allows you to manage settings for sign in options. If you enable this policy setting, you can choose from the following sign in options. Anonymous log on to disable HTTP authentication and use the guest account only for the Common Internet File System (CIFS) protocol. Prompt for user name and password to query users for user IDs and passwords. After a user is queried, these values can be used silently for the remainder of the session. Automatic log on only in Intranet zone to query users for user IDs and passwords in other zones. After a user is queried, these values can be used silently for the rest of the session. Automatic sign in with current user name and password to attempt log on using Windows NT Challenge Response (also known as NTLM authentication). If the server supports Windows NT Challenge Response, the sign in uses the user's network user name and password for log on. If the server doesn't support Windows NT Challenge Response, the user is queried to provide the user name and password. If you disable this policy setting, sign in is set to Automatic log on only in Intranet zone. If you don't configure this policy setting, sign in is set to Automatic sign in only in Intranet zone.
  
  **Default**: Prompt  
  
- **Internet Explorer restricted zone allow vbscript to run**  
  This policy setting allows you to manage whether VBScript can be run on pages from the specified zone in Internet Explorer. If you selected Enable in the drop-down box, VBScript can run without user intervention. If you selected Prompt in the drop-down box, users are asked to choose whether to allow VBScript to run. If you selected Disable in the drop-down box, VBScript is prevented from running. If you don't configure or disable this policy setting, VBScript is prevented from running.
  
  **Default**: Disable  
  
- **Internet Explorer internet zone drag content from different domains across windows**  
  This policy setting allows you to set options for dragging content from one domain to a different domain when the source and destination are in different windows. If you enable this policy setting and click Enable, users can drag content from one domain to a different domain when the source and destination are in different windows. Users can't change this setting. If you enable this policy setting and click Disable, users can't drag content from one domain to a different domain when both the source and destination are in different windows. Users can't change this setting. In Internet Explorer 10, if you disable this policy setting or don't configure it, users can't drag content from one domain to a different domain when the source and destination are in different windows. Users can change this setting in the Internet Options dialog. In Internet Explorer 9 and earlier versions, if you disable this policy or don't configure it, users can drag content from one domain to a different domain when the source and destination are in different windows. Users can't change this setting.
  
  **Default**: Disabled 
  
- **Internet Explorer intranet zone initialize and script Active X controls not marked as safe**  
  This policy setting allows you to manage ActiveX controls not marked as safe. If you enable this policy setting, ActiveX controls run, loaded with parameters, and scripted without setting object safety for untrusted data or scripts. This setting isn't recommended, except for secure and administered zones. This setting causes both unsafe and safe controls to be initialized and scripted, ignoring the Script ActiveX controls marked safe for scripting option. If you enable this policy setting and select Prompt in the drop-down box, users are queried whether to allow the control to load with parameters or scripted. If you disable this policy setting, ActiveX controls that can't be made safe aren't loaded with parameters or scripted. If you don't configure this policy setting, ActiveX controls that can't be made safe aren't loaded with parameters or scripted.
  
  **Default**: Disable 
  
- **Internet Explorer download enclosures**  
  This policy setting prevents the user from having enclosures (file attachments) downloaded from a feed to the user's computer. If you enable this policy setting, the user can't set the Feed Sync Engine to download an enclosure through the Feed property page. A developer can't change the download setting through the Feed APIs. If you disable or don't configure this policy setting, the user can set the Feed Sync Engine to download an enclosure through the Feed property page. A developer can change the download setting through the Feed APIs.
  
  **Default**: Disabled  
  
- **Internet Explorer restricted zone download unsigned Active X controls**   
  This policy setting allows you to manage whether users may download unsigned ActiveX controls from the zone. Such code is potentially harmful, especially when coming from an untrusted zone. If you enable this policy setting, users can run unsigned controls without user intervention. If you select Prompt in the drop-down box, users are queried to choose whether to allow the unsigned control to run. If you disable this policy setting, users can't run unsigned controls. If you don't configure this policy setting, users can't run unsigned controls.
  
  **Default**: Disable  
  
- **Internet Explorer internet zone drag content from different domains within windows**  
  This policy setting allows you to manage whether users may download unsigned ActiveX controls from the zone. Such code is potentially harmful, especially when coming from an untrusted zone. If you enable this policy setting, users can run unsigned controls without user intervention. If you select Prompt in the drop-down box, users are queried to choose whether to allow the unsigned control to run. If you disable this policy setting, users can't run unsigned controls. If you don't configure this policy setting, users can't run unsigned controls.
  
  **Default**: Disabled  
  
- **Internet Explorer processes restrict Active X install**   
  This policy setting enables applications hosting the Web Browser Control to block automatic prompting of ActiveX control installation. If you enable this policy setting, the Web Browser Control will block automatic prompting of ActiveX control installation for all processes. If you disable or don't configure this policy setting, the Web Browser Control won't block automatic prompting of ActiveX control installation for all processes.
  
  **Default**: Enabled  
  
- **Internet Explorer internet zone scriptlets**
  This policy setting allows you to manage whether the user can run scriptlets. If you enable this policy setting, the user can run scriptlets. If you disable this policy setting, the user can't run scriptlets. If you don't configure this policy setting, the user can enable or disable scriptlets.
  
  **Default**: Disable  
  
- **Internet Explorer restricted zone drag and drop or copy and paste files**  
  This policy setting allows you to manage whether users can drag files or copy and paste files from a source within the zone. If you enable this policy setting, users can drag files or copy and paste files from this zone automatically. If you select Prompt in the drop-down box, users are queried to choose whether to drag or copy files from this zone. If you disable this policy setting, users are prevented from dragging files or copying and pasting files from this zone. If you don't configure this policy setting, users are queried to choose whether to drag or copy files from this zone.
  
  **Default**: Disable  
  
- **Internet Explorer software when signature is invalid**   
  This policy setting allows you to manage whether software, such as ActiveX controls and file downloads, can be installed or run by the user even though the signature is invalid. An invalid signature might indicate that someone has tampered with the file. If you enable this policy setting, users are prompted to install or run files with an invalid signature. If you disable this policy setting, users can't run or install files with an invalid signature. If you don't configure this policy, users can choose to run or install files with an invalid signature.
  
  **Default**: Disabled  
  
- **Internet Explorer restricted zone copy and paste via script**   
  This policy setting allows you to manage whether scripts can perform a clipboard operation (for example, cut, copy, and paste) in a specified region. If you enable this policy setting, a script can perform a clipboard operation. If you select Prompt in the drop-down box, users are queried as to whether to perform clipboard operations. If you disable this policy setting, a script can't perform a clipboard operation. If you don't configure this policy setting, a script can't perform a clipboard operation.
  
  **Default**: Disable  
  
- **Internet Explorer restricted zone drag content from different domains across windows**  
  This policy setting allows you to set options for dragging content from one domain to a different domain when the source and destination are in different windows. If you enable this policy setting and click Enable, users can drag content from one domain to a different domain when the source and destination are in different windows. Users can't change this setting. If you enable this policy setting and click Disable, users can't drag content from one domain to a different domain when both the source and destination are in different windows. Users can't change this setting. In Internet Explorer 10, if you disable this policy setting or don't configure it, users can't drag content from one domain to a different domain when the source and destination are in different windows. Users can change this setting in the Internet Options dialog. In Internet Explorer 9 and earlier versions, if you disable this policy or don't configure it, users can drag content from one domain to a different domain when the source and destination are in different windows. Users can't change this setting.   
  **Default**: Disabled  
  
- **Internet Explorer users adding sites**  
  Prevents users from adding or removing sites from security zones. A security zone is a group of Web sites with the same security level. If you enable this policy, the site management settings for security zones are disabled. (To see the site management settings for security zones, in the Internet Options dialog box, click the Security tab, and then click the Sites button.) If you disable this policy or don't configure it, users can add Web sites to or remove sites from the Trusted Sites and Restricted Sites zones, and alter settings for the Local Intranet zone. This policy prevents users from changing site management settings for security zones established by the administrator. Note: The "Disable the Security page" policy (located in \User Configuration\Administrative Templates\Windows Components\Internet Explorer\Internet Control Panel), which removes the Security tab from the interface, takes precedence over this policy. If it's enabled, this policy is ignored. Also, see the "Security zones: Use only machine settings" policy.
  
  **Default**: Disabled  
  
- **Internet Explorer internet zone script initiated windows**  
  This policy setting allows you to manage restrictions on script-initiated pop-up windows and windows that include the title and status bars. If you enable this policy setting, Windows Restrictions security won't apply in this zone. The security zone runs without the added layer of security provided by this feature. If you disable this policy setting, the possible harmful actions contained in script-initiated pop-up windows and windows that include the title and status bars can't run. This Internet Explorer security feature is on in this zone as dictated by the Scripted Windows Security Restrictions feature control setting for the process. If you don't configure this policy setting, the possible harmful actions contained in script-initiated pop-up windows and windows that include the title and status bars can't run. This Internet Explorer security feature is on in this zone as dictated by the Scripted Windows Security Restrictions feature control setting for the process.
  
  **Default**: Disabled  
  
- **Internet Explorer security zones use only machine settings**  
  Applies security zone information to all users of the same computer. A security zone is a group of Web sites with the same security level. If you enable this policy, changes that the user makes to a security zone will apply to all users of that computer. If you disable this policy or don't configure it, users of the same computer can establish their own security zone settings. Use this policy to ensure that security zone settings apply uniformly to the same computer and don't vary from user to user. Also, see the "Security zones: don't allow users to change policies" policy.
  
  **Default**: Enabled  
  
- **Internet Explorer locked down local machine zone java permissions**  
  This policy setting allows you to manage permissions for Java applets. If you enable this policy setting, you can choose options from the drop-down box. Custom, to control permissions settings individually. Low Safety enables applets to perform all operations. Medium Safety enables applets to run in their sandbox (an area in memory outside of which the program can't make calls), plus capabilities like scratch space (a safe and secure storage area on the client computer) and user-controlled file I/O. High Safety enables applets to run in their sandbox. Disable Java to prevent any applets from running. If you disable this policy setting, Java applets can't run. If you don't configure this policy setting, Java applets are disabled
  
  **Default**: Disable java 
  
- **Internet Explorer restricted zone do not run antimalware against Active X controls**   
  This policy setting determines whether Internet Explorer runs antimalware programs against ActiveX controls, to check if they're safe to load on pages. If you enable this policy setting, Internet Explorer won't check with your antimalware program to see if it's safe to create an instance of the ActiveX control. If you disable this policy setting, Internet Explorer always checks with your antimalware program to see if it's safe to create an instance of the ActiveX control. If you don't configure this policy setting, Internet Explorer always checks with your antimalware program to see if it's safe to create an instance of the ActiveX control. Users can turn this behavior on or off, using Internet Explorer Security settings.
  
  **Default**: Disabled  
  
- **Internet Explorer restricted zone run .NET Framework reliant components signed with authenticode**  
  This policy setting allows you to manage whether .NET Framework components that are signed with Authenticode can be executed from Internet Explorer. These components include managed controls referenced from an object tag and managed executables referenced from a link. If you enable this policy setting, Internet Explorer will execute signed managed components. If you select Prompt in the drop-down box, Internet Explorer will prompt the user to determine whether to execute signed managed components. If you disable this policy setting, Internet Explorer won't execute signed managed components. If you don't configure this policy setting, Internet Explorer won't execute signed managed components.
  
  **Default**: Disable  
  
- **Internet Explorer restricted zone access to data sources**  
  This policy setting allows you to manage whether Internet Explorer can access data from another security zone using the Microsoft XML Parser (MSXML) or ActiveX Data Objects (ADO). If you enable this policy setting, users can load a page in the zone that uses MSXML or ADO to access data from another site in the zone. If you select Prompt in the drop-down box, users are queried to choose whether to allow a page to load in the zone that uses MSXML or ADO to access data from another site in the zone. If you disable this policy setting, users can't load a page in the zone that uses MSXML or ADO to access data from another site in the zone. If you don't configure this policy setting, users can't load a page in the zone that uses MSXML or ADO to access data from another site in the zone.
  
  **Default**: Disable 
  
- **Internet Explorer internet zone don't run antimalware against ActiveX controls**   
  This policy setting determines whether Internet Explorer runs antimalware programs against ActiveX controls, to check if they're safe to load on pages. If you enable this policy setting, Internet Explorer won't check with your antimalware program to see if it's safe to create an instance of the ActiveX control. If you disable this policy setting, Internet Explorer always checks with your antimalware program to see if it's safe to create an instance of the ActiveX control. If you don't configure this policy setting, Internet Explorer always checks with your antimalware program to see if it's safe to create an instance of the ActiveX control. Users can turn this behavior on or off, using Internet Explorer Security settings.
  
  **Default**: Disabled  
  
- **Internet Explorer internet zone copy and paste via script**  
  This policy setting allows you to manage whether scripts can perform a clipboard operation (for example, cut, copy, and paste) in a specified region. If you enable this policy setting, a script can perform a clipboard operation. If you select Prompt in the drop-down box, users are queried as to whether to perform clipboard operations. If you disable this policy setting, a script can't perform a clipboard operation. If you don't configure this policy setting, a script can perform a clipboard operation.
  
  **Default**: Disable  
  
- **Internet Explorer use Active X installer service**   
  This policy setting allows you to specify how ActiveX controls are installed. If you enable this policy setting, ActiveX controls are installed only if the ActiveX Installer Service is present and has been configured to allow the installation of ActiveX controls. If you disable or don't configure this policy setting, ActiveX controls, including per-user controls, are installed through the standard installation process.
  
  **Default**: Enabled  
  
- **Internet Explorer processes protection from zone elevation**  
  Internet Explorer places restrictions on each Web page it opens. The restrictions are dependent upon the location of the Web page (Internet, Intranet, Local Machine zone, and so on). For example, Web pages on the local computer have the fewest security restrictions and are in the Local Machine zone, making the Local Machine security zone a prime target for malicious users. If you enable this policy setting, any zone can be protected from zone elevation for all processes. If you disable or don't configure this policy setting, processes other than Internet Explorer or those listed in the Process List receive no such protection.
  
  **Default**: Enabled  
  
- **Internet Explorer internet zone download unsigned ActiveX controls**   
  This policy setting allows you to manage whether users may download unsigned ActiveX controls from the zone. Such code is potentially harmful, especially when coming from an untrusted zone. If you enable this policy setting, users can run unsigned controls without user intervention. If you select Prompt in the drop-down box, users are queried to choose whether to allow the unsigned control to run. If you disable this policy setting, users can't run unsigned controls. If you don't configure this policy setting, users can't run unsigned controls.
  
  **Default**: Disable  
  
- **Internet Explorer internet zone navigate windows and frames across different domains**   
  This policy setting allows you to manage the opening of windows and frames and access of applications across different domains. If you enable this policy setting, users can open windows and frames from other domains and access applications from other domains. If you select Prompt in the drop-down box, users are queried whether to allow windows and frames to access applications from other domains. If you disable this policy setting, users can't open windows and frames to access applications from different domains. If you don't configure this policy setting, users can open windows and frames from other domains and access applications from other domains.
  
  **Default**: Disable  
  
- **Internet Explorer internet zone updates to status bar via script**  
  This policy setting allows you to manage whether a script can update the status bar within the zone. If you enable this policy setting, scripts can update the status bar. If you disable or don't configure this policy setting, script isn't allowed to update the status bar.
  
  **Default**: Disabled  
  
- **Internet Explorer restricted zone include local path when uploading files to server**  
  This policy setting controls if local path information is sent when the user is uploading a file via an HTML form. If the local path information is sent, some information may be unintentionally revealed to the server. For instance, files sent from the user's desktop may contain the user name as a part of the path. If you enable this policy setting, path information is sent when the user is uploading a file via an HTML form. If you disable this policy setting, path information is removed when the user is uploading a file via an HTML form. If you don't configure this policy setting, the user can choose whether path information is sent when they are uploading a file via an HTML form. By default, path information is sent.
  
  **Default**: Disabled  
  
- **Internet Explorer processes restrict file download**   
  This policy setting enables applications hosting the Web Browser Control to block automatic prompting of file downloads that aren't user initiated. If you enable this policy setting, the Web Browser Control will block automatic prompting of file downloads that aren't user initiated for all processes. If you disable this policy setting, the Web Browser Control won't block automatic prompting of file downloads that aren't user initiated for all processes.
  
  **Default**: Enabled  
  
- **Internet Explorer restricted zone allow only approved domains to use Active X controls**   
  This policy setting controls if the user is prompted to allow ActiveX controls to run on websites other than the website that installed the ActiveX control. If you enable this policy setting, the user is prompted before ActiveX controls can run from websites in this zone. The user can choose to allow the control to run from the current site or from all sites. If you disable this policy setting, the user doesn't see the per-site ActiveX prompt, and ActiveX controls can run from all sites in this zone.
  
  **Default**: Enabled  
  
- **Internet Explorer restricted zone initialize and script Active X controls not marked as safe**  
  This policy setting allows you to manage ActiveX controls not marked as safe. If you enable this policy setting, ActiveX controls run, loaded with parameters, and scripted without setting object safety for untrusted data or scripts. This setting isn't recommended, except for secure and administered zones. This setting causes both unsafe and safe controls to be initialized and scripted, ignoring the Script ActiveX controls marked safe for scripting option. If you enable this policy setting and select Prompt in the drop-down box, users are queried whether to allow the control to load with parameters or scripted. If you disable this policy setting, ActiveX controls that can't be made safe aren't loaded with parameters or scripted. If you don't configure this policy setting, ActiveX controls that can't be made safe aren't loaded with parameters or scripted.
  
  **Default**: Disable  
  
- **Internet Explorer users changing policies**  
    Prevents users from changing security zone settings. A security zone is a group of Web sites with the same security level. If you enable this policy, the Custom Level button and security-level slider on the Security tab in the Internet Options dialog box are disabled. If you disable this policy or don't configure it, users can change the settings for security zones. This policy prevents users from changing security zone settings established by the administrator. Note: The "Disable the Security page" policy (located in \User Configuration\Administrative Templates\Windows Components\Internet Explorer\Internet Control Panel), which removes the Security tab from Internet Explorer in Control Panel, takes precedence over this policy. If it's enabled, this policy is ignored. Also, see the "Security zones: Use only machine settings" policy.
    
  **Default**: Disabled  
  
- **Internet Explorer restricted zone protected mode**  
  This policy setting allows you to turn on Protected Mode. Protected Mode helps protect Internet Explorer from exploited vulnerabilities by reducing the locations that Internet Explorer can write to in the registry and the file system. If you enable this policy setting, Protected Mode is turned on. The user can't turn off Protected Mode. If you disable this policy setting, Protected Mode is turned off. The user can't turn on Protected Mode. If you don't configure this policy setting, the user can turn on or turn off Protected Mode.
  
  **Default**: Enable  
  
- **Internet Explorer internet zone user data persistence**  
  This policy setting allows you to manage the preservation of information in the browser's history, in favorites, in an XML store, or directly within a Web page saved to disk. When a user returns to a persisted page, the state of the page can be restored if this policy setting is appropriately configured. If you enable this policy setting, users can preserve information in the browser's history, in favorites, in an XML store, or directly within a Web page saved to disk. If you disable this policy setting, users can't preserve information in the browser's history, in favorites, in an XML store, or directly within a Web page saved to disk. If you don't configure this policy setting, users can preserve information in the browser's history, in favorites, in an XML store, or directly within a Web page saved to disk.
  
  **Default**: Disabled  
  
- **Internet Explorer internet zone scripting of web browser controls**  
 
  This policy setting determines whether a page can control embedded WebBrowser controls via script. If you enable this policy setting, script access to the WebBrowser control is allowed. If you disable this policy setting, script access to the WebBrowser control isn't allowed. If you don't configure this policy setting, the user can enable or disable script access to the WebBrowser control. By default, script access to the WebBrowser control is allowed only in the Local Machine and Intranet zones.
  
  **Default**: Disabled  
  
- **Internet Explorer restricted zone user data persistence**  
    This policy setting allows you to manage the preservation of information in the browser's history, in favorites, in an XML store, or directly within a Web page saved to disk. When a user returns to a persisted page, the state of the page can be restored if this policy setting is appropriately configured. If you enable this policy setting, users can preserve information in the browser's history, in favorites, in an XML store, or directly within a Web page saved to disk. If you disable this policy setting, users can't preserve information in the browser's history, in favorites, in an XML store, or directly within a Web page saved to disk. If you don't configure this policy setting, users can't preserve information in the browser's history, in favorites, in an XML store, or directly within a Web page saved to disk.  
  
  **Default**: Disabled  
  
- **Internet Explorer locked down intranet zone java permissions**  
  This policy setting allows you to manage permissions for Java applets. If you enable this policy setting, you can choose options from the drop-down box. Custom, to control permissions settings individually. Low Safety enables applets to perform all operations. Medium Safety enables applets to run in their sandbox (an area in memory outside of which the program can't make calls), plus capabilities like scratch space (a safe and secure storage area on the client computer) and user-controlled file I/O. High Safety enables applets to run in their sandbox. Disable Java to prevent any applets from running. If you disable this policy setting, Java applets can't run. If you don't configure this policy setting, Java applets are disabled.
  
  **Default**: Disable java  
  
- **Internet Explorer enhanced protected mode**  
  Enhanced Protected Mode provides additional protection against malicious websites by using 64-bit processes on 64-bit versions of Windows. For computers running at least Windows 8, Enhanced Protected Mode also limits the locations Internet Explorer can read from in the registry and the file system. If you enable this policy setting, Enhanced Protected Mode is turned on. Any zone that has Protected Mode enabled will use Enhanced Protected Mode. Users won't be able to disable Enhanced Protected Mode. If you disable this policy setting, Enhanced Protected Mode is turned off. Any zone that has Protected Mode enabled will use the version of Protected Mode introduced in Internet Explorer 7 for Windows Vista. If you don't configure this policy, users can turn on or turn off Enhanced Protected Mode on the Advanced tab of the Internet Options dialog.
  
  **Default**: Enabled  
  
- **Internet Explorer bypass smart screen warnings**  
  This policy setting determines whether the user can bypass warnings from SmartScreen Filter. SmartScreen Filter warns the user about executable files that Internet Explorer users don't commonly download from the Internet. If you enable this policy setting, SmartScreen Filter warnings block the user. If you disable or don't configure this policy setting, the user can bypass SmartScreen Filter warnings.
  
  **Default**: Disabled  
  
- **Internet Explorer restricted zone meta refresh**  
  This policy setting allows you to manage whether a user's browser can be redirected to another Web page if the author of the Web page uses the Meta Refresh setting (tag) to redirect browsers to another Web page. If you enable this policy setting, a user's browser that loads a page containing an active Meta Refresh setting can be redirected to another Web page. If you disable this policy setting, a user's browser that loads a page containing an active Meta Refresh setting can't be redirected to another Web page. If you don't configure this policy setting, a user's browser that loads a page containing an active Meta Refresh setting can't be redirected to another Web page.
  
  **Default**: Disabled  
  
## Local Policies Security Options
For more information, see [Policy CSP - LocalPoliciesSecurityOptions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions) in the Windows documentation. 

- **Restrict anonymous access to named pipes and shares**  
  When enabled, this security setting restricts anonymous access to shares and pipes to the settings for: (1) Named pipes that can be accessed anonymously (2) Shares that can be accessed anonymously
  
  **Default**: Yes  
  
- **Minimum session security for NTLM SSP based servers**  
  This security setting allows a server to require the negotiation of 128-bit encryption and/or NTLMv2 session security. These values are dependent on the LAN Manager Authentication Level security setting value. The options are: Require NTLMv2 session security: The connection will fail if message integrity isn't negotiated. Require 128-bit encryption. The connection will fail if strong encryption (128-bit) isn't negotiated.
  
  **Default**: Require NTLM V2 and 128 bit encryption  
  
- **Minutes of lock screen inactivity until screen saver activates**  
  Windows notices inactivity of a logon session, and if the amount of inactive time exceeds the inactivity limit, then the screen saver will run, locking the session.
  
  **Default**: 15
  
- **Require client to always digitally sign communications** 
  This security setting determines whether all secure channel traffic initiated by the domain member must be signed or encrypted. When a computer joins a domain, a computer account is created. After that, when the system starts, it uses the computer account password to create a secure channel with a domain controller for its domain. This secure channel is used to perform operations such as NTLM pass through authentication, LSA SID/name Lookup and more. This setting determines if all secure channel traffic initiated by the domain member meets minimum security requirements. Specifically it determines whether all secure channel traffic started by the domain member must be signed or encrypted. If this policy is enabled, then the secure channel won't be established unless either signing or encryption of all secure channel traffic is negotiated. If this policy is disabled, then encryption and signing of all secure channel traffic is negotiated with the Domain Controller in which case the level of signing and encryption depends on the version of the Domain Controller and the settings of the following two policies: Domain member: Digitally encrypt secure channel data (when possible) Domain member: Digitally sign secure channel data (when possible)
  
  **Default**: Yes
  
- **Authentication level**  
  This security setting determines which challenge/response authentication protocol is used for network logons. This choice affects the level of authentication protocol used by clients, the level of session security negotiated, and the level of authentication accepted by servers as follows:  
  - *Send LM and NTLM responses*: Clients use LM and NTLM authentication and never use NTLMv2 session security; domain controllers accept LM, NTLM, and NTLMv2 authentication. 
  - *Send LM and NTLM - NTLMv2 if negotiated*: Clients use LM and NTLM authentication and use NTLMv2 session security if the server supports it; domain controllers accept LM, NTLM, and NTLMv2 authentication. 
  - *Send NTLM response only*: Clients use NTLM authentication only and use NTLMv2 session security if the server supports it; domain controllers accept LM, NTLM, and NTLMv2 authentication. 
  - *Send NTLMv2 response only*: Clients use NTLMv2 authentication only and use NTLMv2 session security if the server supports it; domain controllers accept LM, NTLM, and NTLMv2 authentication. 
  - *Send NTLMv2 response only. Refuse LM*: Clients use NTLMv2 authentication only and use NTLMv2 session security if the server supports it; domain controllers refuse LM (accept only NTLM and NTLMv2 authentication). 
  - *Send NTLMv2 response only. Refuse LM and NTLM*: Clients use NTLMv2 authentication only and use NTLMv2 session security if the server supports it; domain controllers refuse LM and NTLM (accept only NTLMv2 authentication). 
    
  **Default**: Send NTLMv2 response only. Refuse LM and NTLM
  
- **Prevent clients from sending unencrypted passwords to third party SMB servers**  
  If this security setting is enabled, the Server Message Block (SMB) redirector can send plaintext passwords to non-Microsoft SMB servers that don't support password encryption during authentication. Sending unencrypted passwords is a security risk.
  
  **Default**: Yes
  
- **Disable server digitally signing communications always**  
  This security setting determines whether the SMB client attempts to negotiate SMB packet signing. The server message block (SMB) protocol provides the basis for Microsoft file and print sharing and many other networking operations, such as remote Windows administration. To prevent man-in-the-middle attacks that modify SMB packets in transit, the SMB protocol supports the digital signing of SMB packets. This policy setting determines whether the SMB client component attempts to negotiate SMB packet signing when it connects to an SMB server. If this setting is enabled, the Microsoft network client will ask the server to perform SMB packet signing upon session setup. If packet signing has been enabled on the server, packet signing is negotiated. If this policy is disabled, the SMB client will never negotiate SMB packet signing.
  
  **Default**: Yes
  
- **Administrator elevation prompt behavior**  
  This policy setting controls the behavior of the elevation prompt for administrators. The options are: 
    - *Elevate without prompting*: Allows privileged accounts to perform an operation that requires elevation without requiring consent or credentials. Note: Use this option only in the most constrained environments. 
    - *Prompt for credentials on the secure desktop*: When an operation requires elevation of privilege, the user is prompted on the secure desktop to enter a privileged user name and password. If the user enters valid credentials, the operation continues with the user's highest available privilege. 
    - *Prompt for consent on the secure desktop*: When an operation requires elevation of privilege, the user is prompted on the secure desktop to select either Permit or Deny. If the user selects Permit, the operation continues with the user's highest available privilege. 
    - *Prompt for credentials*: When an operation requires elevation of privilege, the user is prompted to enter an administrative user name and password. If the user enters valid credentials, the operation continues with the applicable privilege. 
    - *Prompt for consent*: When an operation requires elevation of privilege, the user is prompted to select either Permit or Deny. If the user selects Permit, the operation continues with the user's highest available privilege.  
    - *Prompt for consent for non-Windows binaries*: When an operation for a non-Microsoft application requires elevation of privilege, the user is prompted on the secure desktop to select either Permit or Deny. If the user selects Permit, the operation continues with the user's highest available privilege.   
  
  **Default**: Prompt for consent on the secure desktop
  
- **Minimum session security for NTLM SSP based clients**  
  This security setting allows a client to require the negotiation of 128-bit encryption and/or NTLMv2 session security. These values are dependent on the LAN Manager Authentication Level security setting value. The options are:
  - Require NTLMv2 session security: The connection will fail if NTLMv2 protocol isn't negotiated. 
  - *Require 128-bit encryption*: The connection will fail if strong encryption (128-bit) isn't negotiated.
  - *Require NTLMv2 and 128-bit encryption*. 

  **Default**: Require NTLM V2 128 encryption
  
- **Smart card removal behavior**  
    This security setting determines what happens when the smart card for a logged-on user is removed from the smart card reader. The options are:
     - *No action*. 
     - *Lock Workstation* - The workstation is locked when the smart card is removed, allowing users to leave the area, take their smart card with them, and still maintain a protected session.
     - *Force Logoff* - the user is automatically logged off when the smart card is removed.
     - *Disconnect Remote Desktop session* - Removal of the smart card disconnects the session without logging the user off. This allows the user to insert the smart card and resume the session later, or at another smart card reader-equipped computer, without having to log on again. If the session is local, this policy functions identically to Lock Workstation.   
    
  **Default**: Lock workstation
  
- **Block anonymous enumeration of SAM accounts and shares**  
  This security setting determines whether to allow anonymous enumeration of SAM accounts and shares. Windows allows anonymous users to perform certain activities, such as enumerating the names of domain accounts and network shares. This is convenient, for example, when an administrator wants to grant access to users in a trusted domain that doesn't maintain a reciprocal trust. If you don't want to allow anonymous enumeration of SAM accounts and shares, then set this policy to *Yes*.
  
  **Default**: Yes
  
- **Block remote logon with blank password**  
  This security setting determines whether local accounts that aren't password protected can be used to log on from locations other than the physical computer console. If enabled, local accounts that aren't password protected must use the computer's keyboard to log on. 

  *Warning*: Computers that aren't in physically secure locations should always enforce strong password policies for all local user accounts. Otherwise, anyone with physical access to the computer can log on by using a user account that doesn't have a password. This is especially important for portable computers. 

  If you apply this security policy to the Everyone group, no one can log on through Remote Desktop Services. This setting doesn't affect logons that use domain accounts. It's possible for applications that use remote interactive logons to bypass this setting.
  
  **Default**: Yes
  
- **Standard user elevation prompt behavior**  
  This policy setting controls the behavior of the elevation prompt for standard users. 
  - *Automatically deny elevation requests*: When an operation requires elevation of privilege, a configurable access denied error message is displayed. An enterprise that is running desktops as standard user may choose this setting to reduce help desk calls. 
  - *Prompt for credentials on the secure desktop*: When an operation requires elevation of privilege, the user is prompted on the secure desktop to enter a different user name and password. If the user enters valid credentials, the operation continues with the applicable privilege. 
  - *Prompt for credentials*: When an operation requires elevation of privilege, the user is prompted to enter an administrative user name and password. If the user enters valid credentials, the operation continues with the applicable privilege.  
  
  **Default**: Automatically deny elevation requests
  
- **Require admin approval mode for administrators**  
  This policy setting controls the behavior of all User Account Control (UAC) policy settings for the computer. If you change this policy setting, you must restart your computer. The options are:   
  - *Not configured*: Admin Approval Mode and all related UAC policy settings are disabled. Note: If this policy setting is disabled, the Security Center notifies you that the overall security of the operating system has been reduced. 
  - *Yes*: Admin Approval Mode is enabled. This policy must be enabled and related UAC policy settings must be set appropriately to allow the built-in Administrator account and all other users who are members of the Administrators group to run in Admin Approval Mode.  
  
  **Default**: Yes
  
- **Prevent anonymous enumeration of SAM accounts**  
  This security setting determines what additional permissions are granted for anonymous connections to the computer. Windows allows anonymous users to perform certain activities, such as enumerating the names of domain accounts and network shares. This is convenient, for example, when an administrator wants to grant access to users in a trusted domain that doesn't maintain a reciprocal trust. This security option allows additional restrictions to be placed on anonymous connections as follows: 
  - *Yes*: Don't allow enumeration of SAM accounts. This option replaces Everyone with Authenticated Users in the security permissions for resources.
  - *Not configured*: No additional restrictions. Rely on default permissions.  
  
  **Default**: Yes
  
- **Allow remote calls to security accounts manager**  
  This policy setting allows you to restrict remote rpc connections to SAM. If not selected, the default security descriptor is used.
  
  **Default**: *O:BAG:BAD:(A;;RC;;;BA)*

- **Use admin approval mode**  
  This policy setting controls the behavior of Admin Approval Mode for the built-in Administrator account. The options are: 
  - *Yes*: The built-in Administrator account uses Admin Approval Mode. By default, any operation that requires elevation of privilege will prompt the user to approve the operation. 
  - *Not Configured*: The built-in Administrator account runs all applications with full administrative privilege.  

  **Default**: Yes
  
- **Allow UI access applications for secure locations**  
  This policy setting controls whether User Interface Accessibility (UIAccess or UIA) programs can automatically disable the secure desktop for elevation prompts used by a standard user. 
  - *Yes*: UIA programs, including Windows Remote Assistance, automatically disable the secure desktop for elevation prompts. If you don't disable the "User Account Control: Switch to the secure desktop when prompting for elevation" policy setting, the prompts appear on the interactive user's desktop instead of the secure desktop. 
  - *Not Configured*: The secure desktop can be disabled only by the user of the interactive desktop or by disabling the "User Account Control: Switch to the secure desktop when prompting for elevation" policy setting.  

  **Default**: Yes

- **Detect application installations and prompt for elevation**  
  This policy setting controls the behavior of application installation detection for the computer. The options are: 
  - *Enabled*: When an application installation package is detected that requires elevation of privilege, the user is prompted to enter an administrative user name and password. If the user enters valid credentials, the operation continues with the applicable privilege. 
  - *Disabled*: Application installation packages aren't detected and prompted for elevation. Enterprises that are running standard user desktops and use delegated installation technologies such as Group Policy Software Installation or Systems Management Server (SMS) should disable this policy setting. In this case, installer detection is unnecessary.  
  
  **Default**: Yes
  
- **Prevent storing LAN manager hash value on next password change**  
  This security setting determines if, at the next password change, the LAN Manager (LM) hash value for the new password is stored. The LM hash is relatively weak and prone to attack, as compared with the cryptographically stronger Windows NT hash. Since the LM hash is stored on the local computer in the security database the passwords can be compromised if the security database is attacked.
  
  **Default**: Yes

- **Virtualize file and registry write failures to per user locations**  
  This policy setting controls whether application write failures are redirected to defined registry and file system locations. This policy setting mitigates applications that run as administrator and write run-time application data to *%ProgramFiles%*, *%Windir%*, *%Windir%\system32*, or *HKLM\Software*.
  
  **Default**: Yes

## MS Security Guide  
For more information, see [Policy CSP - MSSecurityGuide](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mssecurityguide) in the Windows documentation.  

- **Apply UAC restrictions to local accounts on network logon**  
  **Default**: Enabled
  
- **SMB v1 client driver start configuration**  
  **Default**: Disabled driver
  
- **SMB v1 server**  
  **Default**: Disabled
  
- **Digest authentication**  
  **Default**: Disabled
  
- **Structured exception handling overwrite protection**  
  **Default**: Enabled
  
## MSS Legacy  
For more information, see [Policy CSP - MSSLegacy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-msslegacy) in the Windows documentation.  

- **Network IP source routing protection level**  
  **Default**: Highest protection  
  
- **Network ignore NetBIOS name release requests except from WINS servers**  
  **Default**: Enabled
  
- **Network IPv6 source routing protection level**  
  **Default**: Highest protection

- **Network ICMP redirects override OSPF generated**  
  **Default**: Disabled
  
## Power  
For more information, see [Policy CSP - Power](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power) in the Windows documentation.  

- **Require password on wake while plugged in**  
  This policy setting specifies if the user is prompted for a password when the system resumes from sleep. If you enable or don't configure this policy setting, the user is prompted for a password when the system resumes from sleep. If you disable this policy setting, the user isn't prompted for a password when the system resumes from sleep.
  
  **Default**: Enabled
  
- **Standby states when sleeping while on battery**  
  This policy setting manages if Windows can use standby states when putting the computer in a sleep state. If you enable or don't configure this policy setting, Windows uses standby states to put the computer in a sleep state. If you disable this policy setting, standby states (S1-S3) aren't allowed.
  
  **Default**: Disabled
  
- **Standby states when sleeping while plugged in**  
  This policy setting manages if Windows can use standby states when putting the computer in a sleep state. If you enable or don't configure this policy setting, Windows uses standby states to put the computer in a sleep state. If you disable this policy setting, standby states (S1-S3) aren't allowed.
  
  **Default**: Disabled
  
- **Require password on wake while on battery**  
  This policy setting specifies if the user is prompted for a password when the system resumes from sleep. If you enable or don't configure this policy setting, the user is prompted for a password when the system resumes from sleep. If you disable this policy setting, the user isn't prompted for a password when the system resumes from sleep.
  
  **Default**: Enabled
  
## Remote Desktop Services  
For more information, see [Policy CSP - RemoteDesktopServices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remotedesktopservices) in the Windows documentation.  

- **Block password saving**  
  Controls whether passwords can be saved on this computer from Remote Desktop Connection. If you enable this setting the password saving checkbox in Remote Desktop Connection is disabled and users won't be able to save passwords. When a user opens an RDP file using Remote Desktop Connection and saves their settings, any password that previously existed in the RDP file are deleted. If you disable this setting or leave it not configured, the user can save passwords using Remote Desktop Connection.
  
   **Default**: Enabled
  
- **Secure RPC communication**  
  Specifies whether a Remote Desktop Session Host server requires secure RPC communication with all clients or allows unsecured communication. You can use this setting to strengthen the security of RPC communication with clients by allowing only authenticated and encrypted requests. If the status is set to Enabled, Remote Desktop Services accepts requests from RPC clients that support secure requests, and doesn't allow unsecured communication with untrusted clients. If the status is set to Disabled, Remote Desktop Services always requests security for all RPC traffic. However, unsecured communication is allowed for RPC clients that don't respond to the request. If the status is set to Not Configured, unsecured communication is allowed. Note: The RPC interface is used for administering and configuring Remote Desktop Services.
  
  **Default**: Enabled
  
- **Block drive redirection**  
  This policy setting specifies whether to prevent the mapping of client drives in a Remote Desktop Services session (drive redirection). By default, an RD Session Host server maps client drives automatically upon connection. Mapped drives appear in the session folder tree in File Explorer or Computer in the format *\<driveletter>* on *\<computername>*. You can use this policy setting to override this behavior. If you enable this policy setting, client drive redirection isn't allowed in Remote Desktop Services sessions, and Clipboard file copy redirection isn't allowed on computers running Windows Server 2003, Windows 8, and Windows XP. If you disable this policy setting, client drive redirection is always allowed. Also, Clipboard file copy redirection is always allowed if Clipboard redirection is allowed. If you don't configure this policy setting, client drive redirection and Clipboard file copy redirection aren't specified at the Group Policy level.
  
  **Default**: Enabled
  
- **Prompt for password upon connection**  
  This policy setting specifies whether Remote Desktop Services always prompts the client for a password upon connection. You can use this setting to enforce a password prompt for users logging on to Remote Desktop Services, even if they already provided the password in the Remote Desktop Connection client. By default, Remote Desktop Services allows users to automatically log on by entering a password in the Remote Desktop Connection client. If you enable this policy setting, users can't automatically log on to Remote Desktop Services by supplying their passwords in the Remote Desktop Connection client. they're prompted for a password to log on. If you disable this policy setting, users can always log on to Remote Desktop Services automatically by supplying their passwords in the Remote Desktop Connection client. If you don't configure this policy setting, automatic logon isn't specified at the Group Policy level. 
  
  **Default**: Enabled
  
- **Remote desktop services client connection encryption level**  
  Specifies whether to require the use of a specific encryption level to secure communications between client computers and RD Session Host servers during Remote Desktop Protocol (RDP) connections. This policy only applies when you're using native RDP encryption. However, native RDP encryption (as opposed to SSL encryption) isn't recommended. This policy doesn't apply to SSL encryption. If you enable this policy setting, all communications between clients and RD Session Host servers during remote connections must use the encryption method specified in this setting. By default, the encryption level is set to High. The following encryption methods are available:  
  - *High*: The High setting encrypts data sent from the client to the server and from the server to the client by using strong 128-bit encryption. Use this encryption level in environments that contain only 128-bit clients (for example, clients that run Remote Desktop Connection). Clients that don't support this encryption level can't connect to RD Session Host servers.  
  - *Client Compatible*: The Client Compatible setting encrypts data sent between the client and the server at the maximum key strength supported by the client. Use this encryption level in environments that include clients that don't support 128-bit encryption.  
  - *Low*: The Low setting encrypts only data sent from the client to the server by using 56-bit encryption.  
  
  If you disable or don't configure this setting, the encryption level to be used for remote connections to RD Session Host servers isn't enforced through Group Policy. Important FIPS compliance can be configured through the System cryptography. Use FIPS-compliant algorithms for encryption, hashing, and signing settings in Group Policy (under Computer Configuration\Windows Settings\Security Settings\Local Policies\Security Options.) The FIPS-compliant setting encrypts and decrypts data sent from the client to the server and from the server to the client, with the Federal Information Processing Standard (FIPS) 140 encryption algorithms, by using Microsoft cryptographic modules. Use this encryption level when communications between clients and RD Session Host servers requires the highest level of encryption.
  
  **Default**: High
  
## Remote Management  
For more information, see [Policy CSP - RemoteManagement](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remotemanagement) in the Windows documentation.  

- **Block storing run as credentials**  
  Client basic authentication
  
  **Default**: Enabled
  
- **Basic authentication**  
  This policy setting allows you to manage whether the Windows Remote Management (WinRM) service accepts Basic authentication from a remote client. If you enable this policy setting, the WinRM service accepts Basic authentication from a remote client. If you disable or don't configure this policy setting, the WinRM service doesn't accept Basic authentication from a remote client.
  
  **Default**: Disabled
  
- **Block client digest authentication**  
  This policy setting allows you to manage whether the Windows Remote Management (WinRM) client uses Digest authentication. If you enable this policy setting, the WinRM client doesn't use Digest authentication. If you disable or don't configure this policy setting, the WinRM client uses Digest authentication.
  
  **Default**: Enabled
  
- **Unencrypted traffic**  
  This policy setting allows you to manage whether the Windows Remote Management (WinRM) service sends and receives unencrypted messages over the network. If you enable this policy setting, the WinRM client sends and receives unencrypted messages over the network. If you disable or don't configure this policy setting, the WinRM client sends or receives only encrypted messages over the network.  
  
  **Default**: Disabled
  
- **Client unencrypted traffic**  
  This policy setting allows you to manage whether the Windows Remote Management (WinRM) client sends and receives unencrypted messages over the network. If you enable this policy setting, the WinRM client sends and receives unencrypted messages over the network. If you disable or don't configure this policy setting, the WinRM client sends or receives only encrypted messages over the network.
  
  **Default**: Disabled
  
- **Client basic authentication**  
  This policy setting allows you to manage whether the Windows Remote Management (WinRM) client uses Basic authentication. If you enable this policy setting, the WinRM client uses Basic authentication. If WinRM is configured to use HTTP transport, the user name and password are sent over the network as clear text. If you disable or don't configure this policy setting, the WinRM client doesn't use Basic authentication.
  
  **Default**: Disabled
  

## Remote Procedure Call  
For more information, see [Policy CSP - RemoteProcedureCall](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remoteprocedurecall) in the Windows documentation.  

- **RPC unauthenticated client options**  
  This policy setting controls how the RPC server runtime handles unauthenticated RPC clients connecting to RPC servers. This policy setting impacts all RPC applications. In a domain environment, use this policy setting with caution as it can impact a wide range of functionality including group policy processing itself. Reverting a change to this policy setting can require manual intervention on each affected machine. This policy setting should never be applied to a domain controller. If you disable this policy setting, the RPC server runtime uses the value of "Authenticated" on Windows Client, and the value of "None" on Windows Server versions that support this policy setting. If you don't configure this policy setting, it remains disabled. The RPC server runtime behaves as though it was enabled with the value of "Authenticated" used for Windows Client and the value of "None" used for Server SKUs that support this policy setting. If you enable this policy setting, it directs the RPC server runtime to restrict unauthenticated RPC clients connecting to RPC servers running on a machine. A client is considered an authenticated client if it uses a named pipe to communicate with the server or if it uses RPC Security. RPC Interfaces that have specifically requested to be accessible by unauthenticated clients may be exempt from this restriction, depending on the selected value for this policy setting.  
  - *None* allows all RPC clients to connect to RPC Servers running on the machine on which the policy setting is applied. 
  - *Authenticated* allows only authenticated RPC Clients (per the definition above) to connect to RPC Servers running on the machine on which the policy setting is applied. Exemptions are granted to interfaces that have requested them. 
  - *Authenticated without exceptions* allows only authenticated RPC Clients (per the definition above) to connect to RPC Servers running on the machine on which the policy setting is applied. No exceptions are allowed. Note: This policy setting won't be applied until the system is rebooted.  

  **Default**: Authenticated

## Search 
For more information, see [Policy CSP - Search](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-search) in the Windows documentation.  

- **Disable indexing encrypted items**  
  Allows or disallows the indexing of items. This switch is for the Windows Search Indexer, which controls whether it will index items that are encrypted, such as the Windows Information Protection (WIP) protected files. When the policy is enabled, WIP protected items are indexed and the metadata about them are stored in an unencrypted location. The metadata includes things like file path and date modified. When the policy is disabled, the WIP protected items aren't indexed and don't show up in the results in Cortana or file explorer. There may also be a performance impact on photos and Groove apps if there are many WIP protected media files on the device.
  
**Default**: Yes
  
## Smart Screen  
For more information, see [Policy CSP - SmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-smartscreen) in the Windows documentation.  

- **Block execution of unverified files**  
  Block user from running unverified files. 
  - *Not Configured* - Employees can ignore SmartScreen warnings and run malicious files. 
  - *Yes* – Employees can't ignore SmartScreen warnings and run malicious files.

  **Default**: Yes

- **Require SmartScreen for apps and files**  
  Allows IT Admins to configure SmartScreen for Windows.

  **Default**: Yes
  
## System  
For more information, see [Policy CSP - System](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system) in the Windows documentation.  

- **System boot start driver initialization**  
  This policy setting allows you to specify which boot-start drivers are initialized based on a classification determined by an Early Launch Antimalware boot-start driver. The Early Launch Antimalware boot-start driver can return the following classifications for each boot-start driver: 
  - *Good*: The driver has been signed and hasn't been tampered with.  
  - *Bad* - The driver has been identified as malware. We recommend that you don't allow known bad drivers to be initialized. 
  - *Bad, but required for boot*: The driver has been identified as malware, but the computer can't successfully boot without loading this driver. 
  - *Unknown* - This driver hasn't been attested to by your malware detection application and hasn't been classified by the Early Launch Antimalware boot-start driver.  

  If you enable this policy setting, you can choose which boot-start drivers to initialize the next time the computer is started. If you disable or don't configure this policy setting, the boot start drivers determined to be Good, Unknown, or Bad but Boot Critical are initialized and the initialization of drivers determined to be Bad is skipped. If your malware detection application doesn't include an Early Launch Antimalware boot-start driver or if your Early Launch Antimalware boot-start driver has been disabled, this setting has no effect and all boot-start drivers are initialized.  
  
  **Default**: Good unknown and bad critical


## Wi-Fi  
For more information, see [Policy CSP - Wifi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi) in the Windows documentation.  

- **Block Internet sharing**  
  Specifies whether internet sharing is possible on the device.  

  **Default**: Yes  

- **Block Automatically connecting to Wi-Fi hotspots**  
  Allow or disallow the device to automatically connect to Wi-Fi hotspots.  

  **Default**: Yes  
  
## Windows Connection Manager  
For more information, see [Policy CSP - WindowsConnectionManager](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsconnectionmanager) in the Windows documentation.  

- **Block connection to non-domain networks**  
  This policy setting prevents computers from connecting to both a domain-based network and a non-domain based network at the same time. If this policy setting is enabled, the computer responds to automatic and manual network connection attempts based on the following circumstances: 
  - Automatic connection attempts When the computer is already connected to a domain-based network, all automatic connection attempts to non-domain networks are blocked. When the computer is already connected to a non-domain based network, automatic connection attempts to domain-based networks are blocked. 
  - Manual connection attempts When the computer is already connected to either a non-domain based network or a domain-based network over media other than Ethernet, and a user attempts to create a manual connection to an additional network in violation of this policy setting, the existing network connection disconnects and the manual connection is allowed. When the computer is already connected to either a non-domain based network or a domain-based network over Ethernet, and a user attempts to create a manual connection to an additional network in violation of this policy setting, the existing Ethernet connection is maintained and the manual connection attempt is blocked.  

  If this policy setting isn't configured or is disabled, computers are allowed to connect simultaneously to both domain and non-domain networks.  

  **Default**: Enabled
  
## Windows Defender  
For more information, see [Policy CSP - Defender](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender) in the Windows documentation.  

- **Scan incoming mail messages**  
  Allows or disallows scanning of email.
  
  **Default**: Yes  

- **Office apps launch child process type**  
  Office apps won't be allowed to create child processes. This includes Word, Excel, PowerPoint, OneNote, and Access. This is a typical malware behavior, especially for macro-based attacks that attempt to use Office apps to launch or download malicious executables.
  
  **Default**: Block
  
- **Defender sample submission consent type**  
  Checks for the user consent level in Windows Defender to send data. If the required consent has already been granted, Windows Defender submits them. If not, (and if the user has specified never to ask), the UI is launched to ask for user consent (when Defender/AllowCloudProtection is allowed) before sending data.
  
  **Default**: Send safe samples automatically 
  
- **Signature update interval (in hours)**  
  Defender signature update interval in hours
  
  **Default**: 4
  
- **Script downloaded payload execution type**  
  Defender script downloaded payload execution type
  
  **Default**: Block
  
- **Prevent credential stealing type**  
  Windows Defender Credential Guard uses virtualization-based security to isolate secrets so that only privileged system software can access them. Unauthorized access to these secrets can lead to credential theft attacks, such as Pass-the-Hash or Pass-The-Ticket. Windows Defender Credential Guard prevents these attacks by protecting NTLM password hashes, Kerberos Ticket Granting Tickets, and credentials stored by applications as domain credentials.
  
  **Default**: Enable

- **Email content execution type**  
  This rule blocks the following file types from being run or launched from an email seen in either Microsoft Outlook or webmail (such as Gmail.com or Outlook.com): Executable files (such as .exe, .dll, or .scr) Script files (such as a PowerShell .ps, VisualBasic .vbs, or JavaScript .js file) Script archive files.
  
  **Default**: Block
  
- **Network protection type**  
  This policy allows you to turn on network protection (block/audit) or off in Windows Defender Exploit Guard. Network protection is a feature of Windows Defender Exploit Guard that protects employees using any app from accessing phishing scams, exploit-hosting sites, and malicious content on the Internet. This includes preventing third-party browsers from connecting to dangerous sites. Value type is integer. If you enable this setting, network protection is turned on and employees can't turn it off. Its behavior can be controlled by the following options: Block and Audit. If you enable this policy with the "Block" option, users and apps are blocked from connecting to dangerous domains. You can see this activity in Windows Defender Security Center. If you enable this policy with the "Audit" option, users/apps won't be blocked from connecting to dangerous domains. However, you'll still see this activity in Windows Defender Security Center. If you disable this policy, users/apps won't be blocked from connecting to dangerous domains. You'll not see any network activity in Windows Defender Security Center. If you don't configure this policy, network blocking is disabled by default.
  
  **Default**: Enable
  
- **Defender schedule scan day**  
  Defender schedule scan day.
  
  **Default**: Everyday
  
- **Cloud-delivered protection**  
  To best protect your PC, Windows Defender will send information to Microsoft about any problems it finds. Microsoft will analyze that information, learn more about problems affecting you and other customers, and offer improved solutions.
  
  **Default**:  Yes  

- **Defender potentially unwanted app action**  
  The potentially unwanted application (PUA) protection feature in Windows Defender Antivirus can identify and block PUAs from downloading and installing on endpoints in your network. These applications aren't considered viruses, malware, or other types of threats, but might perform actions on endpoints that adversely affect their performance or use. PUA can also refer to applications that are considered to have a poor reputation. Typical PUA behavior includes: Various types of software bundling Ad injection into web browsers Driver and registry optimizers that detect issues, request payment to fix the errors, but remain on the endpoint and make no changes or optimizations (also known as "rogue antivirus" programs). These applications can increase the risk of your network being infected with malware, cause malware infections to be harder to identify, and can waste IT resources in cleaning up the applications.  
  
  **Default**: Block  

- **Script obfuscated macro code type**  
  Malware and other threats can attempt to obfuscate or hide their malicious code in some script files. This rule prevents scripts that appear to be obfuscated from running.
  
  **Default**: Block
  
- **Scan removable drives during a full scan**  
  Allows Windows Defender to scan for malicious and unwanted software in removable drives (for example, flash drives) during a full scan. Windows Defender Antivirus scans all files on USB devices before execution.
  
  **Default**: Yes  
  
- **Scan archive files**  
  Defender scan archive files.
  
  **Default**: Yes
  
- **Behavior monitoring**  
  Allows or disallows Windows Defender Behavior Monitoring functionality.Embedded in Windows 10, these sensors collect and process behavioral signals from the operating system and sends this sensor data to your private, isolated, cloud instance of Microsoft Defender ATP.
  
  **Default**: Yes

- **Scan files opened from network folders**  
  If files are read-only, user won't be able to remove any detected malware.
  
  **Default**: Yes

- **Untrusted USB process type**  
  With this rule, admins can prevent unsigned or untrusted executable files from running from USB removable drives, including SD cards.
  
  **Default**: Block
  
- **Office apps other process injection type**  
  Office apps, including Word, Excel, PowerPoint, and OneNote, won't be able to inject code into other processes. This is typically used by malware to run malicious code in an attempt to hide the activity from antivirus scanning engines.
  
  **Default**:  Block
  
- **Office macro code allow Win32 imports type**  
  Malware can use macro code in Office files to import and load Win32 DLLs, which can then be used to make API calls to allow further infection throughout the system. This rule attempts to block Office files that contain macro code that is capable of importing Win32 DLLs. This includes Word, Excel, PowerPoint, and OneNote.
  
  **Default**: Block  
  
- **Defender cloud block level**  
  Defender cloud block level.
  
  **Default**: Not Configured

- **Real-time monitoring**  
  Defender requires real-time monitoring.
  
  **Default**: Yes
  
- **Office apps executable content creation or launch type**  
  This rule targets typical behaviors used by suspicious and malicious add-ons and scripts (extensions) that create or launch executable files. This is a typical malware technique. Extensions are blocked from being used by Office apps. Typically these extensions use the Windows Scripting Host (.wsh files) to run scripts that automate certain tasks or provide user-created add-on features
  
  **Default**: Block

## Windows Ink Workspace  
For more information, see [Policy CSP - WindowsInkWorkspace](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsinkworkspace) in the Windows documentation.  

- **Ink Workspace**  
  Specifies whether to allow the user to access the ink workspace. 
  - *Disabled* - access to ink workspace is disabled. The feature is turned off.
  - *Enabled* - The Ink Workspace feature is turned on, but the user can't access it above the lock screen.
  - *Not Configured* - The Ink Workspace feature is turned on, and the user can use it above the lock screen.  

  **Default**: Enabled
 
## Windows PowerShell  
For more information, see [Policy CSP - WindowsPowerShell](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowspowershell) in the Windows documentation.  

- **Power shell shell script block logging**  
  This policy setting enables logging of all PowerShell script input to the Microsoft-Windows-PowerShell/Operational event log. If you enable this policy setting, Windows PowerShell will log the processing of commands, script blocks, functions, and scripts - whether invoked interactively, or through automation. If you disable this policy setting, logging of PowerShell script input is disabled. If you enable the Script Block Invocation Logging, PowerShell additionally logs events when invocation of a command, script block, function, or script starts or stops. Enabling Invocation Logging generates a high volume of event logs. Note: This policy setting exists under both Computer Configuration and User Configuration in the Group Policy Editor. The Computer Configuration policy setting takes precedence over the User Configuration policy setting.
  
  **Default**: Enabled
 

End of PReview baseilne list  -->
