---
title: Arşiv - Windows 10 için Intune MDM güvenlik temelleri ayarları
titleSuffix: Microsoft Intune
description: Windows 10 Intune yönetmek için MDM güvenlik taban çizgisi ayarlarını son yayın sürümleri Arşivi
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/27/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: shpate
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b8e83aa6b13f192da87a78690b0040e545d8943e
ms.sourcegitcommit: 690e680e854b7d707421c5e06f134e493f4f4194
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2019
ms.locfileid: "67417876"
---
<!-- This article contains the exact baseline details for baseline versions that were previously published in security-baseline-settings-mdm.md.  -->

# <a name="archive-of-mdm-security-baseline-settings"></a>MDM güvenlik taban çizgisi ayarlarını Arşivi  

Intune MDM güvenlik temeli arşivlenen sürümleri için ayrıntıları görüntüleyin.  

Yeni bir MDM güvenlik temeli bıraktığında önceki ayarların listesi için arşiv güvenlik taban çizgisi ayarlarını makalesinden taşıyın. Bu Arşiv eski temel sürümler için varsayılan ayarları anlaşılmasına yardımcı olması için sağlanmıştır ve bu sürümleri yine de kullanım için desteklenir.

Kullanım için bir temel sürüm artık desteklenmeyen, daha sonra bu makaleden kaldırılacak.

- Kullanılabilir ayarları görüntüleyin [geçerli MDM güvenlik temeli](security-baseline-settings-mdm.md) 
- Hakkında bilgi edinin [güvenlik temellerini](security-baselines.md)ve, güvenlik temeli profillerinde temel sürümünden yükseltme.

## <a name="preview-mdm-security-baseline-for-october-2018"></a>Önizleme: Ekim 2018 için MDM güvenlik temeli  

*Bu temel yerine geçen [Spring 2019 (19 saat 1) için MDM güvenlik temeli](security-baseline-settings-mdm.md)*

### <a name="above-lock"></a>Kilit üzerinde  

Daha fazla bilgi için [ilke CSP'si - AboveLock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-abovelock) Windows belgelerinde.  

- **Blok görüntülenmesini kutlama bildirimleri**  
  Bu ilke ayarı, uygulama bildirimleri kilit ekranında görünmesini önlemek sağlar. Bu ilke ayarını etkinleştirirseniz, hiçbir uygulama bildirimleri kilit ekranında görüntülenir. Devre dışı bırakmak veya bu ilke ayarı yapılandırmazsanız, kullanıcıların hangi uygulamaları seçebilirsiniz kilit ekranında bildirimleri görüntüleme.
  
  **Varsayılan**: Evet  

### <a name="app-runtime"></a>Uygulama çalışma zamanı  

Daha fazla bilgi için [ilke CSP'si - AppRuntime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-appruntime
) Windows belgelerinde.  

- **Windows Store uygulamaları için isteğe bağlı Microsoft hesapları**  
  Bu ilke ayarı Microsoft hesaplarının oturum açmak için bir hesap gerektiren Windows Store uygulamaları için isteğe bağlı olup olmadığını denetlemenizi sağlar. Bu ilke yalnızca destekleyen Windows Store uygulamaları etkiler. Bu ilke ayarını etkinleştirirseniz, genellikle oturum açmak için bir Microsoft hesabı gerektiren Windows Store uygulamaları, bunun yerine bir kuruluş hesabıyla oturum açmasına izin verir. Devre dışı bırakmak veya bu ilke ayarı yapılandırmazsanız, kullanıcıların bir Microsoft hesabıyla oturum açmanız gerekir.  
  
  **Varsayılan**: Enabled  

### <a name="application-management"></a>Uygulama Yönetimi  

Daha fazla bilgi için [ilke CSP'si - ApplicationManagement](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement) Windows belgelerinde.  

- **Oyun DVR (yalnızca Masaüstü) engelle**  
  Kaydetme ve oyun yayın izin verilip verilmediğini yapılandırır.
  
  **Varsayılan**: Evet  

### <a name="auto-play"></a>Otomatik Yürüt  

Daha fazla bilgi için [ilke CSP'si - Autoplay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-autoplay) Windows belgelerinde.  

- **Otomatik yürütme varsayılan otomatik çalıştırılan davranış**  
  Bu ayar otomatik çalıştırma komutları için varsayılan davranışını etkiler. Otomatik Çalıştırma komutları autorun.inf dosyalarında depolanır ve yükleme programları veya diğer yordamlar başlatabilirsiniz. Zaman *etkin*, Yöneticiler, Windows Vista çalıştıran bir cihazda varsayılan otomatik çalıştırma davranışını değiştirebilir veya üzeri. Davranışı ayarlanabilir: a) tamamen otomatik çalıştırma komutları devre dışı bırakın veya (b) davranış otomatik olarak otomatik çalıştırma komutunun yürütülmesi yeniden öncesi Windows Vista için geri döndür. Ayarlandığında *devre dışı bırakılmış* veya *yapılandırılmadı*, cihazları Windows Vista çalıştıran veya eklenebilir olup kullanıcı daha sonra sor otomatik çalıştırma komutunu çalıştırmanız gerekir.
  
  **Varsayılan**: Yürütülmeyen  
  
- **Otomatik yürütme modu**  
  Bu ilke ayarı, otomatik özelliği devre dışı bırakmak sağlar. Autoplay medyayı sürücüye takın sürücüyü okumaya başlar. Sonuç olarak, programları ve müzik kurulum dosyası ses ortamdaki hemen başlayın. Windows XP SP2 öncesinde otomatik bir disket sürücüsü gibi çıkarılabilir sürücüleri (ancak CD-ROM sürücüsü) ve ağ sürücülerini varsayılan olarak devre dışı bırakıldı. Windows XP SP2'den başlayarak, Autoplay Zip sürücüleri ve bazı USB yığın depolama cihazı gibi çıkarılabilir sürücülerde de, etkinleştirilir. Bu ilke ayarını etkinleştirirseniz, otomatik CD-ROM ve çıkarılabilir medya sürücüsü devre dışı veya tüm sürücüleri devre dışı olur. Bu ilke ayarı ek sürücüler tür Autoplay devre dışı bırakır. Varsayılan olarak devre dışı bırakılmış sürücülerde Autoplay etkinleştirmek için bu ayarı kullanamazsınız. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, otomatik etkinleştirilir. Not: Bu ilke ayarı bilgisayar yapılandırması ve kullanıcı yapılandırması klasörlerde görünür. İlke ayarları çakışırsa, Bilgisayar Yapılandırması ilke ayarında Kullanıcı Yapılandırması ilke ayarı önceliklidir.
  
  **Varsayılan**: Devre dışı

- **Toplu olmayan cihazlar için Otomatik Oynat engelle**  
  Bu ilke ayarı, kamera veya telefon gibi MTP cihazları için otomatik izin vermiyor. Bu ilke ayarını etkinleştirirseniz, otomatik kamera veya telefon gibi MTP cihazları için izin verilmiyor. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, otomatik birim olmayan cihazlar için etkinleştirilmiş.
  
  **Varsayılan**: Enabled  

### <a name="bitlocker"></a>BitLocker'ı  

Daha fazla bilgi için [ilke CSP'si - Bitlocker](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bitlocker
) Windows belgelerinde.  

- **Bit locker çıkarılabilir sürücü İlkesi**  
  Bu ilke ayarı, şifreleme yöntemini denetlemek ve güçlü şifre için kullanılır. Bu ilke değerlerini BitLocker şifreleme için kullandığı şifreleme gücünü belirler. Kuruluşlar, şifreleme düzeyini (AES-256'yı AES-128'den daha güçlü) Artırılmış güvenlik için denetlemek isteyebilirsiniz. Bu ayarı etkinleştirirseniz, bir şifreleme algoritması ve anahtar şifreleme düzeyi sabit veri sürücüleri, işletim sistemi sürücüleri ve çıkarılabilir veri sürücüleri için tek tek yapılandırmanız mümkün olacaktır. Sabit ve işletim sistemi sürücüleri için XTS-AES algoritmasını kullanmanızı öneririz. Sürücü Windows 10 'un 1511 veya sonraki bir sürümü çalıştırmıyor diğer cihazlar'da kullanılıyorsa, çıkarılabilir sürücüler için AES-CBC 128-bit veya AES-CBC 256 bit kullanmalısınız. Şifreleme yöntemi değiştirme, sürücü zaten şifrelendiyse veya şifreleme sürüyorsa hiçbir etkisi olmaz. Bu gibi durumlarda, bu ilke ayarı göz ardı edilir.

  Bit locker çıkarılabilir sürücü ilke için aşağıdaki ayarları yapılandırın:

    - **Yazma erişimi için şifreleme iste**  
      **Varsayılan**: Evet  
  
    - **Şifreleme yöntemi**  
      **Varsayılan**: AES 256bit CBC  

- **Bit locker sabit sürücü İlkesi**  
  Bu ilke ayarı, şifreleme yöntemini denetlemek ve güçlü şifre için kullanılır. Bu ilke değerlerini BitLocker şifreleme için kullandığı şifreleme gücünü belirler. Kuruluşlar, şifreleme düzeyini (AES-256'yı AES-128'den daha güçlü) Artırılmış güvenlik için denetlemek isteyebilirsiniz. Bu ayarı etkinleştirirseniz, bir şifreleme algoritması ve anahtar şifreleme düzeyi sabit veri sürücüleri, işletim sistemi sürücüleri ve çıkarılabilir veri sürücüleri için ayrı ayrı yapılandırabilirsiniz. Sabit ve işletim sistemi sürücüleri için XTS-AES algoritmasını kullanmanızı öneririz. Sürücü Windows 10 'un 1511 veya sonraki bir sürümü çalıştırmıyor diğer cihazlar'da kullanılıyorsa, çıkarılabilir sürücüler için AES-CBC 128-bit veya AES-CBC 256 bit kullanmalısınız. Şifreleme yöntemi değiştirme, sürücü zaten şifrelendiyse veya şifreleme sürüyorsa hiçbir etkisi olmaz. Bu gibi durumlarda, bu ilke ayarı göz ardı edilir.  
 
   Sabit sürücü ilke Bit locker için aşağıdaki ayarları yapılandırın: 
   - **Şifreleme yöntemi**
     **varsayılan**: AES 256 bit XTS  

- **Bit locker sistem sürücüsü İlkesi**  
  Bu ilke ayarı, şifreleme yöntemini denetlemek ve güçlü şifre için kullanılır. Bu ilke değerlerini BitLocker şifreleme için kullandığı şifreleme gücünü belirler. Kuruluşlar, şifreleme düzeyini (AES-256'yı AES-128'den daha güçlü) Artırılmış güvenlik için denetlemek isteyebilirsiniz. Bu ayarı etkinleştirirseniz, bir şifreleme algoritması ve anahtar şifreleme düzeyi sabit veri sürücüleri, işletim sistemi sürücüleri ve çıkarılabilir veri sürücüleri için ayrı ayrı yapılandırabilirsiniz. Sabit ve işletim sistemi sürücüleri için XTS-AES algoritmasını kullanmanızı öneririz. Sürücü Windows 10 'un 1511 veya sonraki bir sürümü çalıştırmıyor diğer cihazlar'da kullanılıyorsa, çıkarılabilir sürücüler için AES-CBC 128-bit veya AES-CBC 256 bit kullanmalısınız. Şifreleme yöntemi değiştirme, sürücü zaten şifrelendiyse veya şifreleme sürüyorsa hiçbir etkisi olmaz. Bu gibi durumlarda, bu ilke ayarı göz ardı edilir.  

   Bit locker sistem sürücüsü ilkesi için aşağıdaki ayarları yapılandırın:
  - **Şifreleme yöntemi**  
    **Varsayılan**: AES 256 bit XTS  

### <a name="browser"></a>Tarayıcı  

Daha fazla bilgi için [ilke CSP'si - tarayıcı](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser) Windows belgelerinde.  

- **Microsoft Edge için SmartScreen gerektirir**  

  Microsoft Edge, kullanıcılar varsayılan olarak olası kimlik avı kuşku verici ve kötü amaçlı yazılımlardan korumak için Windows Defender SmartScreen (açık) kullanır. Ayrıca, varsayılan olarak, kullanıcılar (kapatma) devre dışı bırakamaz Windows Defender SmartScreen. Bu ilkeyi etkinleştirmek, Windows Defender SmartScreen devre dışı bırakır ve kullanıcıların açma engellemek. Bu ilke, kullanıcıların Windows defender SmartScreen açmak veya kapatmak seçmesine izin vermek için yapılandırmayın.  
  
  **Varsayılan**: Evet  
  
- **Kötü niyetli site erişimi engelle**  

  Varsayılan olarak, Microsoft Edge atlamak kullanıcılara (yoksay) Windows Defender SmartScreen uyarılarını siteye devam etmek için bunları izin vererek kötü amaçlı olabilecek sitelerle ilgili. Bu ilkeyle yine de kullanıcıların atlaması uyarıları önlemek için Microsoft Edge siteye devam etmesini engelleyen yapılandırabilirsiniz.
  
  **Varsayılan**: Evet  
  
- **Doğrulanmamış dosyayı indirme blok** varsayılan olarak, Microsoft Edge atlamak kullanıcılara (yoksay) Windows Defender SmartScreen uyarılarını doğrulanmamış dosyaları indirme devam etmek için bunları izin vererek kötü amaçlı dosyaları hakkında. Bu ilkeyi etkinleştirmek, kullanıcıların doğrulanmamış dosyaları indirmesini engelleme uyarıları atlaması engeller.
  
  **Varsayılan**: Evet  
  
- **Parola yöneticisini engelle**  
  Varsayılan olarak, Microsoft Edge parola Yöneticisi otomatik olarak kullanıcıların yerel yönetici parolaları kullanır. Bu ilkeyi devre dışı bırakmak, Microsoft Edge parola Yöneticisi kullanmasını önler. Bu ilke, kullanıcı Kaydet ve yerel parola Yöneticisi'ni kullanarak parolaları yönetmek seçin izin vermek istiyorsanız yapılandırmayın.
  
  **Varsayılan**: Evet  
  
- **Sertifika hatası geçersiz kılmaları engelle**  
  Bu ilke ayarı, kullanıcı ("süresi gibi", "İptal" veya "Ad uyuşmazlığı" hatalar) Internet Explorer'da gözatma kesme Güvenli Yuva Katmanı/Aktarım Katmanı Güvenliği (SSL/TLS) sertifikası hataları yoksayma öğesinden engeller. Bu ilke ayarını etkinleştirirseniz, kullanıcı gözatma devam edemiyor. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, sertifika hataları yoksay ve Tarama devam etmek kullanıcı seçebilir.
  
  **Varsayılan**: Evet  

### <a name="connectivity"></a>Bağlantı  

Daha fazla bilgi için [ilke CSP'si - bağlantı](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity) Windows belgelerinde.  

- **Web yayımı ve çevrimiçi sipariş sihirbazları için Internet blok indirme**  
  Bu ilke ayarı, Windows web yayımı ve çevrimiçi sipariş sihirbazları için sağlayıcıların listesini indirip indirmeyeceğini belirtir. Bu sihirbazlar, kullanıcıların çevrimiçi depolama alanını ve fotoğraf yazdırma gibi hizmetleri sağlayan şirketlerin listesinden seçmesine izin ver. Varsayılan olarak, Windows kayıt defterinde belirtilen sağlayıcılara ek olarak bir Windows Web sitesinden indirilen sağlayıcıları görüntüler. Bu ilke ayarını etkinleştirirseniz, Windows, sağlayıcıları ve yalnızca yerel kayıt defteri görüntüsünü önbelleğe alınan hizmet sağlayıcıları indirilmedi. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, kullanıcı Web'de yayımlama veya çevrimiçi sipariş sihirbazları kullandığında sağlayıcılarının bir listesini indirir. Kayıt defterinde hizmet sağlayıcıları belirtme hakkında bilgi içerir. daha fazla bilgi için web yayımı ve çevrimiçi sipariş sihirbazları için belgelere bakın.  
  
  **Varsayılan**: Enabled  

- **Yazıcı sürücülerini HTTP üzerinden indirmeyi engelleyin**  
  Bu ilke ayarı, bu istemci yazdırma sürücüsü paketleri HTTP üzerinden indirilmesine izin verilip verilmeyeceğini belirtir. HTTP yazdırmayı kurmak için HTTP üzerinden indirilecek gelen olmayan sürücüler gerekir. Not: Bu ilke ayarı istemci yazdırma Intranet veya Internet üzerinde yazıcılara HTTP üzerinden engellemez. Yalnızca zaten yerel olarak yüklü değildir sürücülerini indirmeyi yasaklar. Bu ilke ayarını etkinleştirirseniz, yazıcı sürücülerini HTTP üzerinden yüklenemiyor. Devre dışı bırakmak veya bu ilke ayarı yapılandırmazsanız, kullanıcıların yazıcı sürücülerini HTTP üzerinden indirebilirsiniz.
  
  **Varsayılan**: Enabled  

### <a name="credentials-delegation"></a>Kimlik temsilcisi  

Daha fazla bilgi için [ilke CSP'si - CredentialsDelegation](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-credentialsdelegation
) Windows belgelerinde.  

- **Uzak ana aktarılamaz kimlik temsili**  
  Uzak ana aktarılamaz kimlik temsili sağlar. Cihazları kimlik bilgilerini dışarı aktarılabilir bir sürümünü kimlik bilgileri temsilcisi kullanılırken, kullanıcıların kimlik bilgileri hırsızlığı riski saldırganlar uzaktaki ana makinede gelen gösterir. uzak konağa sağlar. Bu ilke ayarını etkinleştirirseniz, konak uzak Credential Guard ya da kısıtlı yönetici modunu destekler. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, sınırlı yönetim ve uzak Credential Guard modu desteklenmiyor. Kullanıcı kimlik bilgilerini ana bilgisayara geçirmek her zaman gerekecektir.  

  
  **Varsayılan**: Enabled  

### <a name="credentials-ui"></a>Kimlik bilgileri kullanıcı Arabirimi  

Daha fazla bilgi için [ilke CSP'si - CredentialsUI](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-credentialsui) Windows belgelerinde.  

- **Yöneticiler listeleme** Bu ilke ayarı bir kullanıcı, çalışan bir uygulamayı yükseltme girişiminde bulunduğunda yönetici hesaplarını görüntülemek eşleştirilmeyeceğini denetler. Kullanıcı, çalışan bir uygulamayı yükseltme girişiminde bulunduğunda, varsayılan olarak, yönetici hesapları görüntülenmez. Bu ilke ayarını etkinleştirirseniz, kullanıcı seçin ve doğru parolayı girmek için bilgisayarda tüm yerel yönetici hesapları görüntüleyin. Bu ilke ayarını devre dışı bırakırsanız, kullanıcıların her zaman bir kullanıcı adı ve parola yükseltmesine yazmanız gerekir.  

  
  **Varsayılan**: Devre dışı  

### <a name="data-protection"></a>Veri Koruma  

Daha fazla bilgi için [ilke CSP'si - DataProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dataprotection
) Windows belgelerinde.  

- **Doğrudan bellek erişimi engelle**  
  Bir kullanıcı Windows oturum kadar bu ilke ayarı, doğrudan bellek erişimi (DMA) engellemek sık erişimli takılabilir PCI aşağı akış için tüm bağlantı sağlar. Bir kullanıcı oturum açtığında sonra Windows ana Tak PCI bağlantı noktalarına bağlı PCI cihazları numaralandırır. Her seferinde kullanıcı makine kilitler, DMA kullanıcı yeniden oturum kadar hiçbir alt cihazlarla sık erişimli Tak PCI noktalarına engellenir. Makine kilidi açıldı, zaten numaralandırılmıştır cihazlar takılı kadar çalışmaya devam eder. Bu ilke ayarı, BitLocker veya cihaz şifrelemesi etkinken yalnızca zorlanır.
  
  
  **Varsayılan**: Evet  

### <a name="device-guard"></a>Cihaz koruma  

Daha fazla bilgi için [ilke CSP'si - DeviceGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceguard
) Windows belgelerinde.  

- **Credential Guard**  
  Bu ayar, sonraki yeniden başlatma sırasında kimlik bilgilerinin korunmasına yardımcı olmak için sanallaştırma tabanlı güvenlik ile Credential Guard hakkında kullanıcıların sağlar.
   
  **Varsayılan**: UEFI kilidiyle etkinleştir 

- **Sanallaştırma tabanlı güvenliği etkinleştir**  </br>
  Sanallaştırma tabanlı güvenlik (VBS) sonraki önyüklemede açar. Sanallaştırma tabanlı güvenlik, güvenlik hizmetlerine destek sağlamak için Windows Hiper Yöneticisi'ni kullanır.
  
  **Varsayılan**: Evet  

- **Sistem koruma başlatın**    
  **Varsayılan**: Enabled  

### <a name="device-installation"></a>Cihaz yükleme  

Daha fazla bilgi için [ilke CSP'si - DeviceInstallation](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceinstallation) Windows belgelerinde.  

- **Cihaz tanımlayıcıları olarak donanım cihaz yükleme**  
  Bu ilke ayarı Windows yüklenmesini engelleyen cihazlar için Tak ve Kullan donanım kimlikleri ve uyumlu bir listesini belirtmenize olanak sağlar. Bu ilke ayarı, bir cihaza yüklemek Windows sağlayan diğer ilke ayarları üzerinden önceliklidir. Bu ilke ayarını etkinleştirirseniz, Windows, donanım kimliği veya uyumlu kimliği görünür bir cihaz listesinde oluşturduğunuz yüklenmesini engelledi. İlke ayarı, Uzak Masaüstü sunucuda bu ilke ayarını etkinleştirirseniz, uzak masaüstü istemcisini belirtilen cihazlarından Uzak Masaüstü sunucuya yönlendirilmesini etkiler. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, cihazları yükleyebilir ve izin verilen veya diğer ilke ayarları tarafından önlenmiş olarak güncelleştirin.
  
  **Varsayılan**: Blok donanım cihaz yükleme  

    Zaman *Block donanım cihaz yükleme* olduğu belirlenirse, aşağıdaki ayarlar kullanılabilir.
  
    - **Eşleşen donanım cihazları kaldırma**   
    Bu ayar yalnızca olan *donanım cihaz yükleme cihaz tanımlayıcısı tarafından* ayarlanır *Block donanım cihaz yükleme*.
      
      **Varsayılan**: Evet
  
    - **Engellenen donanım cihaz tanımlayıcıları**  
       Bu ayar yalnızca olan *donanım cihaz yükleme cihaz tanımlayıcısı tarafından* ayarlanır *Block donanım cihaz yükleme*.
      
      **Varsayılan**: Evet  
  
- **Kurulum sınıflar tarafından donanım cihaz yükleme**  
  Bu ilke ayarı, cihaz Kurulumu sınıf genel olarak benzersiz tanımlayıcıları (GUID'ler) cihaz sürücülerini Windows yüklenmesini engelleyen bir listesini belirtmenize olanak sağlar. Bu ilke ayarı, bir cihaza yüklemek Windows sağlayan diğer ilke ayarları üzerinden önceliklidir. Bu ilke ayarını etkinleştirirseniz, Windows yükleme veya GUID'leri listede, cihaz Kurulumu sınıfı oluşturduğunuz cihaz sürücüleri güncelleştirme engellenir. İlke ayarı, Uzak Masaüstü sunucuda bu ilke ayarını etkinleştirirseniz, uzak masaüstü istemcisini belirtilen cihazlarından Uzak Masaüstü sunucuya yönlendirilmesini etkiler. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, Windows yükleyebilir ve güncelleştirme cihazlar olarak izin verilen veya diğer ilke ayarları tarafından engellendi.
  
  **Varsayılan**: Blok donanım cihaz yükleme  

    Zaman *Block donanım cihaz yükleme* olduğu belirlenirse, aşağıdaki ayarlar kullanılabilir.
    - **Eşleşen donanım cihazları kaldırma**    
    Bu ayar yalnızca olan *donanım cihaz yükleme kurulum sınıflar tarafından* ayarlanır *Block donanım cihaz yükleme*.  

      **Varsayılan**: *Varsayılan yapılandırma*  
  
    - **Engellenen donanım cihaz tanımlayıcıları**  
      Bu ayar yalnızca olan *donanım cihaz yükleme kurulum sınıflar tarafından* ayarlanır *Block donanım cihaz yükleme*.
      
      **Varsayılan**: *Varsayılan yapılandırma*  

### <a name="device-lock"></a>Cihaz kilidi  

Daha fazla bilgi için [ilke CSP'si - DeviceLock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock) Windows belgelerinde.  

- **Kamera kullanımını engelle**  
  PC Ayarları'nda kilit ekranı kamera iki durumlu düğme devre dışı bırakır ve kilit ekranında çağrılan bir kamera önler. Varsayılan olarak, kullanıcıların kullanılabilir bir kamera kilit ekranında çağrılmasını etkinleştirebilirsiniz. Bu ayarı etkinleştirirseniz, kullanıcılar artık etkinleştirme veya devre dışı PC Ayarları'nda kilit ekranı kamera erişimi mümkün olacaktır ve kilit ekranında kamera çağrılamaz. 
  
  **Varsayılan**: Enabled  

- **Parola iste**  
  Cihaz kilidi etkinleştirilip etkinleştirilmeyeceğini belirtir.
  
  **Varsayılan**: Evet  
  
    Zaman *parola iste* ayarlanır *Evet*, aşağıdaki ayarlar kullanılabilir.

    - **Parola en az karakter kümesi sayısı**  
      Güçlü PIN veya parola için gereken karmaşık öğe türleri (büyük ve küçük harfler, sayılar ve noktalama işaretleri) sayısı. PIN, masaüstü ve mobile cihazları için aşağıdaki davranışı uygular: 1 - gereken 3 - sayılar ve küçük harf, basamak yalnızca 2 - sayılar ve küçük harf olduğunu ve büyük harfler gereklidir. Masaüstü Microsoft hesapları ve etki alanı hesapları desteklenmez. 4 - rakamlar, küçük harfler, büyük harfler ve özel karakterler gereklidir. Desktop'ta desteklenmiyor. Varsayılan değer 1’dir. 
      
      **Varsayılan**: 3  
  
    - **Cihaz silinmeden önceki oturum açma hatası sayısı**  
      Cihaz temizlenmeden önce izin verilen kimlik doğrulama hataları sayısı. 0 değeri cihaz silme işlevselliği devre dışı bırakır.
        
      **Varsayılan**: 10  
  
    - **Parola kullanım süresi (gün)**  
      En fazla parola yaşı ilkesi ayarını nasıl uzun süre (gün) belirler. Sistem kullanıcıdan değiştirmesini olmasını gerektirir. önce bir parola kullanılabilir. Gün sayısı 0 olarak ayarlayarak parolaları asla sona belirtebilirsiniz veya parolaları gün 1 ile 999 arasında bir süre sonra süresi dolacak şekilde ayarlayabilirsiniz. En fazla parola geçerlilik süresi 1 ile 999 gün arasında ise, en az parola geçerlilik süresi en fazla parola geçerlilik süresinden daha az olmalıdır. En fazla parola geçerlilik süresi 0 olarak ayarlarsanız, parola geçerlilik süresi alt sınırı 0 ile 998 gün arasında herhangi bir değer olabilir.
      
      **Varsayılan**: 60  
  
    - **Gerekli parola türü**  
      PIN veya parola gerekli türünü belirler.
      
      **Varsayılan**: Alfasayısal  
  
    - **En düşük parola uzunluğu**  
      Minimum parola uzunluğu ilkesi ayarını belirler en az bir kullanıcı hesabı için bir parola ayarlama yapabilirsiniz karakter sayısı. 1 ile 14 karakter arasında bir değer ayarlayabilirsiniz veya karakter sayısı 0 olarak ayarlayarak, parola gerektiğini kurabilirsiniz.
      
      **Varsayılan**: 8  
  
    - **Basit parolaları engelle**  
      "1111" veya "1234" gibi PIN veya parolalara izin verilip verilmeyeceğini belirtir. Masaüstü için resimli parola kullanımını da denetler.
      
      **Varsayılan**: Evet  
        *Evet, bir ayar basit parolaların kullanımına engeller.* 

  - **Önceki parolaların yeniden kullanılmasını engelleme**  
    Kaç adet parola kullanılamaz geçmişinde depolanacak belirtir. Değer, kullanıcının geçerli parolası içerir. Örneğin, ayarı ile *1* kullanıcı, yeni bir parola seçerken, geçerli parolaları yeniden kullanılamaz. Ayarı *5* kullanıcının yeni parolasını, geçerli parolaları veya herhangi bir önceki dört parolalarını ayarlayamayacağı anlamına gelir.
    
    **Varsayılan**: 24  

- **Slayt gösterisi engelle**  
  PC Ayarları'nda kilit ekranı slayt gösterisi ayarlarını devre dışı bırakır ve bir slayt gösterisi kilit ekranında çalışmasını önler. Varsayılan olarak, bunlar makine kilitleme sonra çalıştırılacak bir slayt gösterisi açabileceğinizi bilirsiniz. Bu ayarı etkinleştirirseniz, kullanıcılar, PC Ayarları'nda slayt gösterisi ayarlarını değiştiremez ve hiçbir slayt gösterisi başlayabilir.
  
    **Varsayılan**: Enabled  
    *Etkin ayarı, slayt gösterilerini çalışmasını engeller.* 

- **Gün olarak parola en düşük yaş**  
  En az parola geçerlilik süresi ilke ayarı bir parola olmalıdır süre (gün cinsinden) belirler. kullanıcı değiştirmeden önce kullanıldı. 1 ile 998 gün arasında bir değer ayarlayabilirsiniz veya gün sayısı 0 olarak ayarlayarak, hemen bir parola değişikliklerini verebilirsiniz. En fazla parola geçerlilik süresi, parolaların süresiz belirten, 0 olarak ayarlanmadığı sürece, en az parola geçerlilik süresi en fazla parola geçerlilik süresi değerinden küçük olması gerekir. En fazla parola geçerlilik süresi 0 olarak ayarlarsanız, en az parola geçerlilik süresi 0 ile 998 arasında herhangi bir değere ayarlanabilir.
  
    **Varsayılan**: 1.  

### <a name="event-log-service"></a>Olay Günlüğü hizmeti  

Daha fazla bilgi için [ilke CSP'si - EventLogService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-eventlogservice) Windows belgelerinde.  

- **Güvenlik günlüğü maksimum dosya boyutunu KB**  
  Bu ilke ayarı, günlük dosyasının en büyük boyutu kilobayt cinsinden belirtir. Bu ilke ayarını etkinleştirirseniz, en fazla günlük dosyası boyutunu 1 megabayt (1024 kilobayt) ve 2 terabaytlık (2147483647 kilobayt) kilobayt artışlarla arasında olacak şekilde yapılandırabilirsiniz. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, günlük dosyasının en büyük boyutu yerel olarak yapılandırılmış değerine ayarlanır. Bu değer günlüğü Özellikleri iletişim kutusunu kullanarak yerel bir yönetici tarafından değiştirilebilir ve 20 megabayt olarak varsayılan.
  
   **Varsayılan**: 196608  

- **Sistem günlük en fazla dosya boyutunu KB**  
  Bu ilke ayarı, günlük dosyasının en büyük boyutu kilobayt cinsinden belirtir. Bu ilke ayarını etkinleştirirseniz, en fazla günlük dosyası boyutunu 1 megabayt (1024 kilobayt) ve 2 terabaytlık (2147483647 kilobayt) kilobayt artışlarla arasında olacak şekilde yapılandırabilirsiniz. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, günlük dosyasının en büyük boyutu yerel olarak yapılandırılmış değerine ayarlanır. Bu değer günlüğü Özellikleri iletişim kutusunu kullanarak yerel bir yönetici tarafından değiştirilebilir ve 20 megabayt olarak varsayılan.
  
  **Varsayılan**: 32768  

- **Uygulama günlük en fazla dosya boyutunu KB**  
  Bu ilke ayarı, günlük dosyasının en büyük boyutu kilobayt cinsinden belirtir. Bu ilke ayarını etkinleştirirseniz, en fazla günlük dosyası boyutunu 1 megabayt (1024 kilobayt) ve 2 terabaytlık (2147483647 kilobayt) kilobayt artışlarla arasında olacak şekilde yapılandırabilirsiniz. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, günlük dosyasının en büyük boyutu yerel olarak yapılandırılmış değerine ayarlanır. Bu değer günlüğü Özellikleri iletişim kutusunu kullanarak yerel bir yönetici tarafından değiştirilebilir ve 20 megabayt olarak varsayılan.
  
  **Varsayılan**: 32768  

### <a name="experience"></a>Deneyim  

Daha fazla bilgi için [ilke CSP'si - deneyimi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience) Windows belgelerinde.  

- **Blok Windows spot**  
  BT yöneticilerinin tüm Windows spot özelliklerini kapatmasını - Windows spot kilit ekranı, Windows ipuçları, Microsoft tüketici özellikleri ve diğer ilgili özellikler sağlar.
  
  **Varsayılan**: Evet  

  Zaman *blok Windows spot* ayarlanır *Evet*, aşağıdaki ayarlar kullanılabilir.
  
  - **Windows spot'ta üçüncü taraf önerilerini engelle**  
    Üçüncü taraf yazılım uygulama ve içerik önerilerini izin vermek için yayımcıları ile Windows kilit ekranı spot, önerilen uygulamaların başlangıç menüsünde ve Windows ipuçları gibi özellikleri spotlight olup olmadığını belirtir. Kullanıcılar, Microsoft özellikler, uygulamalar ve hizmetler için öneriler yine de görebilirsiniz.
      
    **Varsayılan**: Evet  
   - **Tüketici belirli özellikleri engelle**  
      BT yöneticilerinin, genellikle yalnızca tüketicilere yönelik olan gibi başlatma önerileri, üyelik bildirimleri, Post-OOBE uygulaması yükleme ve yeniden yönlendirme kutucukları deneyimleri açmalarını sağlar.
      
     **Varsayılan**: Evet  


### <a name="exploit-guard"></a>Exploit Guard  

Daha fazla bilgi için [ilke CSP'si - ExploitGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-exploitguard) Windows belgelerinde.  

- **Exploit Protection XML**  
  BT yöneticisi, istenen sistem ve kuruluşunuzdaki tüm cihazlar için uygulama risk azaltma seçenekleri temsil eden bir yapılandırma çıkış göndermek etkinleştirir. Yapılandırma, bir XML tarafından temsil edilir. Exploit Protection dağıtabilir ve bulaşma vektörlerine kullanan kötü amaçlı yazılımlardan korunmasına cihazları yardımcı olur. Risk azaltma işlemleri (bir yapılandırma olarak bilinir) bir dizi oluşturmak için PowerShell ve Windows güvenlik uygulaması'nı kullanın. Ardından, bu yapılandırma, bir XML dosyası olarak dışarı aktarın ve risk azaltma ayarlarını kümesinin aynısına sahip oldukları tüm için ağınızda birden çok makineyle paylaşın. Ayrıca, dönüştürme ve exploit koruma yapılandırması XML içinde mevcut bir EMET yapılandırma XML dosyasını içeri aktarın.
  
  **Varsayılan**: *Örnek xml sağlanır* 
 
### <a name="file-explorer"></a>Dosya Gezgini  

Daha fazla bilgi için [ilke CSP'si - ta dosya Gezgini](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-fileexplorer) Windows belgelerinde.  

- **Blok Veri Yürütme Engellemesi**  
  Veri Yürütme Engellemesi devre dışı bırakma, bazı eski eklenti uygulamalarının Sonlandırıcı Gezgini işlev izin verebilirsiniz.
  
  **Varsayılan**: Devre dışı  
   
- **Blok yığın bozulması sonlandırıldığında**  
  Yığın bozulması sonlandırıldığında devre dışı bırakma, Gezgini hala beklenmedik bir şekilde daha sonra sonlandırabilir rağmen bazı eski eklenti uygulamalarının Sonlandırıcı Gezgini hemen çalışmaya izin verebilirsiniz.
  
  **Varsayılan**: Devre dışı  
    

### <a name="internet-explorer"></a>Internet Explorer  

Daha fazla bilgi için [ilke CSP'si - Internet Explorer](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-internetexplorer) Windows belgelerinde.  

- **Internet Explorer internet bölgesi veri kaynaklarına erişim**  
  Bu ilke ayarı, Internet Explorer Microsoft XML Parser (MSXML) ya da ActiveX Data Objects (ADO) kullanan başka bir güvenlik bölgesi'nden veri erişip erişemeyeceğini yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz, kullanıcılar bir bölge içinde başka bir siteden verilere erişmek için MSXML veya ADO kullanan bölge sayfasında yükleyebilir. Açılan kutusunda seçtiğiniz istemi, kullanıcıların sayfayı MSXML veya ADO bölgede başka bir siteden verilere erişmek için kullandığı bölgesinde yüklemek için izin verip vermeyeceklerini sorgulanır. Bu ilke ayarını devre dışı bırakırsanız, kullanıcıların bir bölge içinde başka bir siteden verilere erişmek için MSXML veya ADO kullanan bölge sayfasında yüklenemiyor. Bu ilke ayarı yapılandırmazsanız, kullanıcıların bir bölge içinde başka bir siteden verilere erişmek için MSXML veya ADO kullanan bölge sayfasında yüklenemiyor.
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer kısıtlı bölge windows içinde farklı etki alanlarından içerik sürükleyin**  
  Bu ilke ayarı kaynak ve hedef aynı pencerede olduğunda içerik bir etki alanından farklı bir etki alanına sürükleyerek seçenekleri ayarlamanıza olanak sağlar. Bu ilke ayarını etkinleştirin ve Etkinleştir'i tıklatın, kaynak ve hedef aynı pencerede olduğunda kullanıcıların içeriği bir etki alanından farklı bir etki alanına sürükleyebilirsiniz. Kullanıcılar, bu ayarı değiştiremezsiniz. Bu ilke ayarını etkinleştirin ve devre dışı bırak'a tıklayın, kaynak ve hedef aynı pencerede olduğunda kullanıcıların içeriği bir etki alanından farklı bir etki alanına sürükleyemezsiniz. Kullanıcıların Internet Seçenekleri iletişim kutusunda Bu ayarı değiştiremezsiniz. Bu ilke ayarını devre dışı bırakır veya, yapılandırmayın kaynak ve hedef aynı pencerede olduğunda Internet Explorer 10'da, kullanıcıların içeriği bir etki alanından farklı bir etki alanına sürükleyemezsiniz. Kullanıcıların Internet Seçenekleri iletişim kutusunda Bu ayarı değiştirebilirsiniz. Bu ilke ayarını devre dışı bırakır veya, yapılandırmayın kaynak ve hedef aynı pencerede olduğunda Internet Explorer 9 ve önceki sürümlerinde, kullanıcıların içeriği bir etki alanından farklı bir etki alanına sürükleyebilirsiniz. Kullanıcıların Internet Seçenekleri iletişim kutusunda Bu ayarı değiştiremezsiniz.
  
  **Varsayılan**: Devre dışı
  
- **Internet Explorer sertifika adresi uyuşmazlığı Uyarısı**  
  Bu ilke ayarı, sertifika adresi uyumsuzluğu güvenlik uyarısını kapatmanızı sağlar. Bu ilke ayarı etkinleştirildiğinde, kullanıcı için farklı bir Web sitesi adresi, mevcut sertifikalara Güvenli HTTP (HTTPS) Web siteleri ziyaret uyarılır. Bu uyarı, sahtekarlık saldırılarını önlemeye yardımcı olur. Bu ilke ayarını etkinleştirirseniz, sertifika adresi uyuşmazlığı her zaman uyarı görünür. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, kullanıcı (Internet Denetim Masası'nda Gelişmiş sayfasını kullanarak) sertifika adresi uyuşmazlığı uyarısı görüntülenip görüntülenmeyeceğini seçebilirsiniz.
  
  **Varsayılan**: Enabled 
  
- **Internet Explorer kısıtlı bölge ayrıcalıklı siteleri daha az**  
  Bu ilke ayarı, bu bölgeye Web siteleri Internet siteleri gibi daha az ayrıcalıklı bölgelerdeki gidebilirsiniz yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, Web siteleri daha az ayrıcalıklı bölgelerdeki yeni pencerelerde açın veya bu bölgeye gidin. Güvenlik bölgesi ek koruma Bölge Yüksekliği güvenlik özelliği tarafından sağlanan bir güvenlik katmanı olmadan çalışır. Açılan kutusunda seçtiğiniz istemi, riskli olabilecek Gezinti gerçekleşmek üzere olan bir kullanıcı için bir uyarı verilir. Bu ilke ayarını devre dışı bırakırsanız, zararlı olabilecek Gezinti engellenir. Internet Explorer güvenlik özelliği bu bölgede bölge yükseltme özelliği denetiminden koruma tarafından belirlenen açıktır. Bu ilke ayarı yapılandırmazsanız, zararlı olabilecek gezintiler engellenir. Internet Explorer güvenlik özelliği bu bölgede bölge yükseltme özelliği denetiminden koruma tarafından belirlenen açıktır.
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Dosya için Internet Explorer kısıtlı bölge otomatik istemi indirir**  
  Bu ilke ayarı, kullanıcıların olmayan kullanıcı tarafından başlatılan dosya indirmeleri için sorulup sorulmayacağını belirler. Bu ayar ne olursa olsun, kullanıcılar, dosya indirme iletişim kutuları için kullanıcı tarafından başlatılan indirmeler alır. Bu ayarı etkinleştirirseniz, kullanıcılar bir dosya indirme iletişim kutusu için otomatik indirme denemelerinin alır. Devre dışı bırakın ya da bu ayarı yapılandırmayın, kullanıcı tarafından başlatılan olmayan dosya yüklemeleri engellenir ve kullanıcıların dosya indirme iletişim kutusu yerine bildirim çubuğu göreceksiniz. Kullanıcılar daha sonra dosya indirme istemi izin vermek için bildirim çubuğu tıklatabilirsiniz.
  
  **Varsayılan**: Devre dışı
  
- **Internet Explorer internet bölgesi .NET Framework bağımlı bileşenler**  
  Bu ilke ayarı, Authenticode imzalanmadığını .NET Framework bileşenlerini Internet Explorer'dan çalışıp çalışmayacağını yönetmenizi sağlar. Bu bileşenler, bir nesne etiketi ve bir bağlantıdan başvurulan Yönetilen yürütülebilir dosyaları başvurulan yönetilen denetimleri içerir. Bu ilke ayarını etkinleştirirseniz, Internet Explorer işaretsiz yönetilen bileşenleri çalıştırır. Açılan kutusunda seçtiğiniz istemi, Internet Explorer işaretsiz yönetilen bileşenleri çalıştırılıp çalıştırılmayacağını için girmesini ister. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer işaretsiz yönetilen bileşenleri yürütme olmaz. Bu ilke ayarı yapılandırmazsanız, Internet Explorer işaretsiz yönetilen bileşenleri çalıştırır.
  
  **Varsayılan**: Devre Dışı Bırak 
  
- **Internet Explorer internet bölgesi izin tdc ActiveX denetimlerini kullanmak için etki alanları yalnızca onaylanmış**  
  Bu ilke ayarı, kullanıcı Web siteleri TDC ActiveX denetimini çalışıp çalışamayacağını denetler. Bu ilke ayarını etkinleştirirseniz, bu bölgedeki sitelerinden TDC ActiveX denetimini çalışmaz. Bu ilke ayarını devre dışı bırakırsanız, bu bölgedeki tüm sitelerden TDC ActiveX denetimi çalıştırılır.
  
  **Varsayılan**: Enabled 
  
- **Windows Internet Explorer'ın kısıtlı bölge betik başlatıldı**  
  Bu ilke ayarı, betik tarafından başlatılan açılır pencereleri ve başlık ve durum çubuğu içeren windows üzerindeki kısıtlamaları yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz, bu bölgede Windows kısıtlamaları güvenlik uygulanmayacak. Bu özellik tarafından sağlanan bir güvenlik katmanı eklendi olmadan güvenlik bölgesi çalıştırır. Bu ilke ayarını devre dışı bırakırsanız, betik tarafından başlatılan açılır pencereleri ve başlık ve durum çubuğu içeren windows içerdiği zararlı olabilecek eylemler çalıştıramazsınız. Internet Explorer güvenlik özelliği bu bölgede işlem için Windows güvenlik kısıtlamaları komut dosyası özellik denetim ayarı tarafından belirlenen açıktır. Bu ilke ayarı yapılandırmazsanız, betik tarafından başlatılan açılır pencereleri ve başlık ve durum çubuğu içeren windows içerdiği zararlı olabilecek eylemler çalıştıramazsınız. Internet Explorer güvenlik özelliği bu bölgede işlem için Windows güvenlik kısıtlamaları komut dosyası özellik denetim ayarı tarafından belirlenen açıktır.
  
  **Varsayılan**: Devre dışı 
  
- **Internet Explorer internet bölgesi dahil yerel yolu sunucu için dosyalar karşıya yüklenirken**  
  Bu ilke ayarı, kullanıcı, bir HTML formu aracılığıyla bir dosya karşıya yüklenirken yerel yol bilgisi gönderilir, denetler. Yerel yol bilgisi gönderilir, bazı bilgiler sunucuya yanlışlıkla açığa. Örneğin, kullanıcının Masaüstü'nden gönderilen dosya yolun bir parçası olarak kullanıcı adını içerebilir. Bu ilke ayarını etkinleştirirseniz, kullanıcı, bir HTML formu aracılığıyla bir dosya karşıya yüklenirken yol bilgisi gönderilir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcı, bir HTML formu aracılığıyla bir dosya karşıya yüklenirken yol bilgisi kaldırıldı. Bu ilke ayarı yapılandırmazsanız, kullanıcı, bir HTML formu aracılığıyla bir dosyayı karşıya yüklediğinizde, yol bilgisi gidiyor olup olmadığını seçebilir. Varsayılan olarak, yol bilgisi gönderilir.
  
  **Varsayılan**: Devre dışı 
  
- **Internet Explorer, geliştirilmiş korumalı mod işlemi devre dışı bırak**  
  Bu ilke ayarı Internet Explorer 11 64-bit işlemler (için daha fazla güvenlik için) veya (daha fazla uyumluluk için) 32-bit işlemler zaman kullanıp kullanmadığını belirler geliştirilmiş korumalı modu 64-bit Windows sürümlerinde çalışan. Önemli: 64 bit işlemleri kullanıldığında bazı ActiveX denetimleri ve araç çubuklarını kullanılamayabilir. Bu ilke ayarını etkinleştirirseniz, Internet Explorer 11 geliştirilmiş korumalı modu 64-bit Windows sürümlerinde çalışan 64-bit sekmesi işlemleri kullanır. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer 11 zaman geliştirilmiş korumalı modu 64-bit Windows sürümlerinde çalışan 32-bit sekmesi işlemleri kullanır. Bu ilke ayarı yapılandırmazsanız, kullanıcıların üzerinde veya Internet Explorer ayarlarını kullanarak bu özelliği kapatabilirsiniz. Bu özellik varsayılan olarak kapalıdır.
  
  **Varsayılan**: Enabled 
  
- **Internet Explorer, sertifika hataları yoksay**  
  Bu ilke ayarı, kullanıcı ("süresi gibi", "İptal" veya "Ad uyuşmazlığı" hatalar) Internet Explorer'da gözatma kesme Güvenli Yuva Katmanı/Aktarım Katmanı Güvenliği (SSL/TLS) sertifikası hataları yoksayma öğesinden engeller. Bu ilke ayarını etkinleştirirseniz, kullanıcı gözatma devam edemiyor. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, sertifika hataları yoksay ve Tarama devam etmek kullanıcı seçebilir.
  
  **Varsayılan**: Devre dışı 
  
- **XAML dosyalarının Internet Explorer internet bölgesi yükleniyor**  
  Bu ilke ayarı, Extensible Application Markup Language (XAML) dosyaların yüklenmesini yönetmenize olanak sağlar. XAML, zengin kullanıcı arabirimleri ve Windows Presentation Foundation yararlanan bir grafik oluşturmak için yaygın olarak kullanılan bir XML tabanlı bildirim temelli bir biçimlendirme dilidir. Bu ilke ayarını etkinleştirin ve etkinleştirmek için açılan kutudan ayarlayın, XAML dosyaları Internet Explorer içinde otomatik olarak yüklenir. Kullanıcı bu davranışı değiştiremezsiniz. Açılan kutunun istemine ayarlarsanız, XAML dosyalarının yüklenmesi için kullanıcıdan istenir. Bu ilke ayarını devre dışı bırakırsanız, XAML dosyaları Internet Explorer yüklü değilken. Kullanıcı bu davranışı değiştiremezsiniz. Bu ilke ayarı yapılandırmazsanız, kullanıcının Internet Explorer içinde XAML dosyalarını yüklemeye karar verebilirsiniz.
  
  **Varsayılan**: Devre Dışı Bırak 
  
- **Dosya için Internet Explorer internet bölgesi istemi otomatik indirmeleri**  
  Bu ilke ayarı, kullanıcıların olmayan kullanıcı tarafından başlatılan dosya indirmeleri için sorulup sorulmayacağını belirler. Bu ayar ne olursa olsun, kullanıcılar, dosya indirme iletişim kutuları için kullanıcı tarafından başlatılan indirmeler alır. Bu ayarı etkinleştirirseniz, kullanıcılar bir dosya indirme iletişim kutusu için otomatik indirme denemelerinin alır. Devre dışı bırakın ya da bu ayarı yapılandırmayın, kullanıcı tarafından başlatılan olmayan dosya yüklemeleri engellenir ve kullanıcıların dosya indirme iletişim kutusu yerine bildirim çubuğu göreceksiniz. Kullanıcılar daha sonra dosya indirme istemi izin vermek için bildirim çubuğu tıklatabilirsiniz.
  
  **Varsayılan**: Enabled  
  
- **Güvenli olmayan dosyalar için Internet Explorer'ın kısıtlı bölge güvenlik uyarısı**  
  "Dosya – Güvenlik Uyarısı açın" iletisi görüntülenirse, kullanıcı yürütülebilir dosyaları veya diğer olmayabilecek dosyaları (örneğin dosya Gezgini'ni kullanarak bir intranet dosya paylaşımından) açmayı denediğinde bu ilke ayarı denetler. Bu ilke ayarını etkinleştirin ve etkinleştirmek için açılan kutudan ayarlayın, bu dosyalar olmadan bir güvenlik uyarısı açın. Açılan kutunun istemine ayarlarsanız, dosyaları açmadan önce bir güvenlik uyarısı görüntülenir. Bu ilke ayarını devre dışı bırakırsanız, bu dosyalar açmayın. Bu ilke ayarı yapılandırmazsanız, kullanıcı, bilgisayar bu dosyaları nasıl işlediğini yapılandırabilirsiniz. Varsayılan olarak, bu dosyalar Intranet ve yerel bilgisayar bölgeleri, etkin Yasak bölgesinde engellenen ve Internet ve güvenilen bölgelerde isteyecek şekilde ayarlayın.
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer internet bölgesi çoklu site komut dosyası filtresi**  
  Bu ilke, siteler arası betik (XSS) filtre algılayın ve bu bölgedeki Web siteleri içine siteler arası betik eklemelerini engelle denetler. Bu ilke ayarını etkinleştirirseniz, bu bölgedeki sitelerden XSS filtre açıktır ve XSS filtre siteler arası betik eklemelerini engellemeye çalışır. Bu ilke ayarını devre dışı bırakırsanız, bu bölgedeki sitelerden XSS filtre kapalıdır ve Internet Explorer, siteler arası betik eklemelerini izin verir.
  
  **Varsayılan**: Enabled 
  
- **Internet Explorer SSL3 geri dön**  
  Bu ilke ayarı, güvenli olmayan bir geri dönüş SSL 3.0 engellemenize olanak sağlar. Bu ilke etkinleştirildiğinde, Internet Explorer sitelere kullanarak SSL 3.0 veya TLS 1.0 veya üstü başarısız olduğunda aşağıda bağlanmayı dener. Bir adam-de-ortadaki adam saldırısı önlemek için güvenli olmayan bir geri dönüş izin verme öneririz. Bu ilke, hangi güvenlik protokollerine etkin etkilemez. Bu ilke devre dışı bırakırsanız, sistem varsayılan değerler kullanılır.
  
  **Varsayılan**: Site yok 
  
- **Internet Explorer'ın internet bölgesi akıllı ekran aşağıya kilitli**  
  Bu ilke kötü amaçlı içerik için bu bölgedeki sayfalar SmartScreen Filtresi tarar olmadığını ayarı denetler. Bu ilke ayarını etkinleştirirseniz, SmartScreen Filtresi, kötü amaçlı içerik için bu bölgedeki sayfalar tarar. Bu ilke ayarını devre dışı bırakırsanız, kötü amaçlı içerik için bu bölgedeki sayfalar SmartScreen Filtresi taramaz. Bu ilke ayarı yapılandırmazsanız, kullanıcıya SmartScreen Filtresi'ni kötü amaçlı içerik için bu bölgedeki sayfalar tarayıp taramayacağını seçebilirsiniz. Not: Internet Explorer 7'de, bu ilke ayarı, kimlik avı filtre kötü amaçlı içerik için bu bölgedeki sayfalar tarayıp taramayacağını denetler.
  
  **Varsayılan**: Enabled 
  
- **Internet Explorer bölge başlatma uygulamalar ve dosyalar bir iFrame içinde kısıtlı**  
  Bu ilke ayarı, uygulamaları çalıştırabilir ve dosyaları, HTML sayfaları bu bölgedeki bir IFRAME başvurusuna şuradan indirilebilir yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, kullanıcılar uygulamalarını çalıştırmak ve kullanıcı müdahalesi olmadan bu bölgedeki sayfalarında IFRAMES dosyaları indirin. Açılan kutusunda seçtiğiniz istemi, kullanıcılara uygulamalarını çalıştırmak ve bu bölgedeki sayfalarında IFRAMES dosyaları karşıdan seçmeleri istenir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcıların uygulamaları çalıştırmaya ve bu bölgedeki sayfalarında IFRAMES dosyaları indirme engellenir. Bu ilke ayarı yapılandırmazsanız, kullanıcıların uygulamaları çalıştırmaya ve bu bölgedeki sayfalarında IFRAMES dosyaları indirme engellenir.
  
  **Varsayılan**: Devre Dışı Bırak 
  
- **Internet Explorer atlama smart screen'i uyarıları seyrek dosyaları hakkında**  
  Bu ilke ayarı, kullanıcı Kimden SmartScreen Filtresi uyarılarını devre dışı bırakabilir olup olmadığını belirler. SmartScreen Filtresi, Internet Explorer kullanıcıların yaygın olarak Internet'ten yüklemeyin yürütülebilir dosyaları hakkında kullanıcıyı uyarır. Bu ilke ayarını etkinleştirirseniz, kullanıcıya SmartScreen Filtresi uyarılarını engelleyin. Kullanıcı devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, SmartScreen Filtresi uyarılarını devre dışı bırakabilir.
  
  **Varsayılan**: Devre dışı  
  
- **İnternet bölgesi için Internet Explorer Açılır Pencere Engelleyicisi**  
  Bu ilke ayarı, istenmeyen açılır pencerelerin görüntülenip görüntülenmeyeceğini yönetmenize olanak sağlar. Son kullanıcı bağlantıyı tıklattığında açılan açılan pencereler engellenmez. Bu ilke ayarını etkinleştirirseniz, en istenmeyen açılır pencereleri görüntülenmesi engellenir. Bu ilke ayarını devre dışı bırakırsanız, açılır pencereleri görünmesini engelleyen değildir. Bu ilke ayarı yapılandırmazsanız en istenmeyen açılır pencereleri görüntülenmesi engellenir.
  
  **Varsayılan**: Etkinleştir  
  
- **Internet Explorer tutarlı MIME işleme işlemleri**  
  Internet Explorer dinamik ikili davranışlar içerir: takılı HTML öğeleri için belirli işlevi kapsülleyen bileşenler. Bu ilke, ikili davranışı güvenlik kısıtlama ayarını engellendi veya izin ayarı denetler. Bu ilke ayarını etkinleştirirseniz, ikili davranışları için dosya Gezgini ve Internet Explorer işlemleri engellenir. Bu ilke ayarını devre dışı bırakırsanız, ikili davranışları dosya Gezgini ve Internet Explorer işlemleri için izin verilir. Bu ilke ayarı yapılandırmazsanız, ikili davranışları için dosya Gezgini ve Internet Explorer işlemleri engellenir.
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer'ın kısıtlı bölge java izinleri**  
  Bu ilke ayarı, Java uygulamaları için izinleri yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz, Seçenekler açılır kutusundan seçebilirsiniz. Özel denetim izinlerini ayarlar için ayrı ayrı. Düşük güvenilirlik, uygulamaların tüm işlemleri sağlar. Orta düzey güvenilirlik (bir alanda bellek görüşmesi yapamaz program dışında), kendi sanal uygulamaların artı boş alan (istemci bilgisayarda bir güvenli depolama alanı) ve kullanıcı tarafından denetlenen dosya g/ç gibi özellikler sağlar. Yüksek güvenilirlik, korumalı alanında çalışmasını sağlar. Java uygulamaları çalışmasını önlemek için devre dışı bırakın. Bu ilke ayarını devre dışı bırakırsanız, Java uygulamalarını çalıştıramazsınız. Bu ilke ayarı yapılandırmazsanız, Java uygulamalarını devre dışı bırakıldı.
  
  **Varsayılan**: Java devre dışı bırak  
    
  
- **Korumalı modda Internet Explorer ActiveX denetimleri**  
  Bu ilke ayarı, ActiveX denetimleri geliştirilmiş korumalı mod etkinleştirildiğinde korumalı modda çalışmasını engeller. Geliştirilmiş korumalı mod ile uyumlu olmayan bir ActiveX denetimi bir kullanıcının bir Web sitesi denetim yükleme girişiminde, Internet Explorer kullanıcıya bildirir ve Web sitesi normal korumalı modda çalıştırma seçeneği sunar. Bu ilke ayarı, bu bildirim devre dışı bırakır ve geliştirilmiş korumalı modu çalıştırmak için tüm Web sitelerinin zorlar. Geliştirilmiş korumalı mod, Windows 64 bit sürümlerinde 64 bit işlemleri kullanarak kötü amaçlı Web sitelerinin karşı ek koruma sağlar. En az çalıştıran bilgisayarlar için Windows 8, geliştirilmiş korumalı mod da sınırlar Internet Explorer okuyabileceği konumlar kayıt defteri ve dosya sistemi. Geliştirilmiş korumalı mod etkin ve geliştirilmiş korumalı mod ile uyumlu olmayan bir ActiveX denetimini yükleme girişiminde bir Web sitesi üzerinden kullanıcı gelir, Internet Explorer kullanıcıya bildirir ve geliştirilmiş korumalı mod için devre dışı bırakma seçeneği sunar Bu özel Web sitesi. Bu ilke ayarını etkinleştirirseniz, Internet Explorer geliştirilmiş korumalı mod devre dışı bırakma seçeneği kullanıcıya vermek olmaz. Tüm korumalı mod Web siteleri, geliştirilmiş korumalı modu çalıştırılır. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, Internet Explorer kullanıcıları uyarır ve normal korumalı modda uyumsuz ActiveX denetimleri ile Web sitelerini çalıştırmak için bir seçenek sunar.  
  
  **Varsayılan**: Devre dışı  
  
- **XAML dosyalarının Internet Explorer kısıtlı bölge yükleniyor**  
  Bu ilke ayarı, Extensible Application Markup Language (XAML) dosyaların yüklenmesini yönetmenize olanak sağlar. XAML, zengin kullanıcı arabirimleri ve Windows Presentation Foundation yararlanan bir grafik oluşturmak için yaygın olarak kullanılan bir XML tabanlı bildirim temelli bir biçimlendirme dilidir. Bu ilke ayarını etkinleştirin ve etkinleştirmek için açılan kutudan ayarlayın, XAML dosyaları Internet Explorer içinde otomatik olarak yüklenir. Kullanıcı bu davranışı değiştiremezsiniz. Açılan kutunun istemine ayarlarsanız, XAML dosyalarının yüklenmesi için kullanıcıdan istenir. Bu ilke ayarını devre dışı bırakırsanız, XAML dosyaları Internet Explorer yüklü değilken. Kullanıcı bu davranışı değiştiremezsiniz. Bu ilke ayarı yapılandırmazsanız, kullanıcının Internet Explorer içinde XAML dosyalarını yüklemeye karar verebilirsiniz.
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer pencerelerine güvenlik kısıtlamaları işlemleri**  
  Internet Explorer, program aracılığıyla açın, yeniden boyutlandırma ve çeşitli türlerdeki windows yeniden konumlandırmak için komut dosyaları sağlar. Pencere Kısıtlamaları güvenlik özelliği açılır pencereleri kısıtlar ve betikleri başlık ve Durum Çubuğu'nın kullanıcıya görünür olmayan veya diğer Windows başlık ve durum çubukları karartmak windows görüntülenmesini engeller. Bu ilke ayarını etkinleştirirseniz, tüm işlemler için pencerelerine kısıtlanır. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın pencerelerine sınırlı değildir.
  
  **Varsayılan**: Enabled   
  
- **Internet Explorer kısıtlı bölge ActiveX denetimleri ve eklentileri çalıştırma**  
  Bu ilke ayarı ActiveX denetimleri ve eklentiler sayfalarda belirtilen bölgeden çalıştırabilirsiniz yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, denetimleri ve eklentiler kullanıcı müdahalesi olmadan çalıştırabilirsiniz. Aşağı açılan kutusunda seçtiğiniz istemi kullanıcıların denetimleri izin verip vermeyeceklerini sorulan veya çalıştırmak için eklenti vardır. Bu ilke ayarını devre dışı bırakırsanız, denetimleri ve eklentiler çalışması engellenir. Bu ilke ayarı yapılandırmazsanız, denetimleri ve eklentiler çalışması engellenir.
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer'ın kısıtlı bölge betik ActiveX denetimleri için güvenli olarak işaretlenmiş**  
  Bu ilke ayarı, bir ActiveX denetimi için güvenli olarak işaretlenmiş bir betik ile etkileşimde bulunup bulunamayacağı yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, komut dosyası etkileşimi kullanıcı müdahalesi olmadan otomatik olarak ortaya çıkabilir. Aşağı açılan kutusunda istemi seçerseniz, kullanıcıların betik katılımına izin verip vermeyeceklerini sorgulanır. Bu ilke ayarını devre dışı bırakırsanız, betik etkileşim oluşmasını engellenir. Bu ilke ayarı yapılandırmazsanız, betik etkileşim oluşmasını engellenir.
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer'ın kısıtlı bölge oturum açma seçenekleri**  
  Bu ilke ayarı, oturum açma seçenekleri ayarlarını yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz, aşağıdaki oturum açma seçenekleri arasından seçim yapabilirsiniz. 
  - *Anonim* - anonim oturum açma devre dışı bırakma HTTP kimlik doğrulaması kullanın ve yalnızca ortak Internet dosya sistemi (CIFS) protokolü için Konuk hesabı kullanın. 
  - *İstemi* -kullanıcı kimliklerini ve parolaları için kullanıcı adı ve parola sorgusu kullanıcıları için kullanım istemi. Bir Kullanıcı sorgulandıktan sonra bu değerleri sessizce oturumunun geri kalanı için kullanılabilir. 
  - *Yalnızca Intranet bölgesinde otomatik oturum açma* -kullanıcı kimliklerini ve parolaları diğer bölgelerdeki sorgusu kullanıcıları için bu seçeneği kullanın. Bir Kullanıcı sorgulandıktan sonra bu değerleri sessizce oturumunun geri kalanı için kullanılabilir. 
  - *Geçerli kullanıcı adı ve parola otomatik oturum*-Windows NT Sınama yanıtı (NTLM kimlik doğrulaması olarak da bilinir) kullanarak oturum açma denemesi için bu seçeneği kullanın. Sunucu, Windows NT Sınama yanıtı, kullanıcının ağ kullanıcı adı ve parola için oturum açın oturum açma kullanan destekliyorsa. Sunucu, Windows NT Sınama yanıtı desteklemiyorsa, kullanıcının kullanıcı adı ve parola sağlamak için sorgulanır. 

  Bu ilke ayarını devre dışı bırakırsanız, oturum açma ayarlanır *otomatik oturum yalnızca Intranet bölgesinde*. Bu ilke ayarı yapılandırmazsanız, oturum açma ayarlanır *istemi* kullanıcı adı ve parola.
  
  **Varsayılan**: Anonim  
  
- **Internet Explorer Güvenilen Bölge başlatmak ve ActiveX denetimlerini betik güvenli olarak işaretlenmemiş**  
  Bu ilke ayarı, güvenli olarak işaretlenmemiş ActiveX denetimlerini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, ActiveX denetimleri, güvenilir olmayan verileri veya betikler için nesne güvenliği ayarlamadan parametreler ile yüklenir ve komut dosyalı çalıştırın. Bu ayar, güvenli ve yönetilen bölgeler dışında önerilmez. Bu ayar, başlatılır ve komut dosyası için hem güvenli hem de güvenli denetimler neden olur, betik ActiveX denetimlerini yoksayma seçeneği için güvenli olarak işaretlenmiş. Bu ilke ayarını etkinleştirin ve istemi açılır kutusunda, kullanıcıların denetimi parametrelerle yüklemeye izin verilip verilmeyeceği veya komut dosyası. Bu ilke ayarını devre dışı bırakırsanız, güvenli hale getirilemez ActiveX denetimlerini parametrelerle yüklü değil veya komut dosyası. Bu ilke ayarı yapılandırmazsanız, kullanıcıların denetimi parametrelerle yüklemeye izin verilip verilmeyeceği veya komut dosyası.
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer onay sunucu sertifika iptal etme**  
  Bu ilke ayarı, Internet Explorer ın sunucu sertifikalarının iptal durumunu denetleyip denetlemeyeceğini yönetmenize olanak sağlar. Sertifikalar, gizliliği ihlal edilmiş veya artık geçerli ve bu seçenek, gizli veriler sahte veya güvenli olmayan bir siteye göndermesinin kullanıcıları korur iptal edilir. Bu ilke ayarını etkinleştirirseniz, Internet Explorer sunucu sertifikası iptal edilmiş görmek için denetler. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer sunucu sertifikası iptal edilmiş görmek için kontrol olmaz. Bu ilke ayarı yapılandırmazsanız, Internet Explorer sunucu sertifikası iptal edilmiş görmek için kontrol olmaz.
  
  **Varsayılan**: Enabled 
  
- **Internet Explorer internet bölgesi ayrıcalıklı siteleri daha az**  
  Bu ilke ayarı, bu bölgeye Web siteleri Yasak siteler gibi daha az ayrıcalıklı bölgelerdeki gidebilirsiniz yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, Web siteleri daha az ayrıcalıklı bölgelerdeki yeni pencerelerde açın veya bu bölgeye gidin. Güvenlik bölgesi ek koruma Bölge Yüksekliği güvenlik özelliği tarafından sağlanan bir güvenlik katmanı olmadan çalışır. Açılan kutusunda seçtiğiniz istemi, riskli olabilecek Gezinti gerçekleşmek üzere olan bir kullanıcı için bir uyarı verilir. Bu ilke ayarını devre dışı bırakırsanız, zararlı olabilecek gezintiler engellenir. Internet Explorer güvenlik özelliği bu bölgede bölge yükseltme özelliği denetiminden koruma tarafından belirlenen açıktır. Bu ilke ayarı yapılandırmazsanız, Web siteleri daha az ayrıcalıklı bölgelerdeki yeni pencerelerde açın veya bu bölgeye gidin.
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer kısıtlı bölge dosyasını indirir.**  
  Bu ilke ayarı, Dosya indirmeleri bölgeden yüklenmesine izin verilip verilmeyeceğini yönetmenizi sağlar. Bu seçeneği neden değil dosyanın teslim edildiği bölge indirme bağlantısıyla sayfanın bölgesine göre belirlenen. Bu ilke ayarını etkinleştirirseniz, dosyaları bölgeden indirilebilir. Bu ilke ayarını devre dışı bırakırsanız, bölgeden indirilen dosyaları engellenir. Bu ilke ayarı yapılandırmazsanız bölgeden indirilen dosyaları engellenir.
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer internet bölgesi Authenticode ile imzalanmış .NET Framework bağımlı bileşenleri çalıştırın**  
  Bu ilke ayarı, Authenticode ile imzalanmış .NET Framework bileşenlerini Internet Explorer'dan çalışıp çalışmayacağını yönetmenizi sağlar. Bu bileşenler, bir nesne etiketi ve bir bağlantıdan başvurulan Yönetilen yürütülebilir dosyaları başvurulan yönetilen denetimleri içerir. Bu ilke ayarını etkinleştirirseniz, Internet Explorer imzalı yönetilen bileşenleri çalıştırır. Açılan kutusunda seçtiğiniz istemi, Internet Explorer imzalı yönetilen bileşenleri çalıştırılıp çalıştırılmayacağını için girmesini ister. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer imzalı yönetilen bileşenleri yürütme olmaz. Bu ilke ayarı yapılandırmazsanız, Internet Explorer imzalı yönetilen bileşenleri yürütme olmaz.
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer kullanıcı ActiveX denetimleri yüklenmesini engelle**  
  Bu ilke ayarı, kullanıcı başına temelinde ActiveX denetimlerini yüklenmesini önlemek sağlar. Bu ilke ayarını etkinleştirirseniz, kullanıcı başına esasına göre ActiveX denetimlerini yüklenemez. ActiveX denetimleri, devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, kullanıcı başına esasına göre yüklenebilir.
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer smart screen'i Filtresi'nin yönetimini engelle**  
  Bu ilke ayarı, ziyaret ettikleri Web sitesi aracılığıyla "kimlik avı" kişisel bilgileri toplamak sahte girişimleri için bilinen veya ana bilgisayar kötü amaçlı yazılımı bildirmeye bilinen kullanıcıyı uyarır SmartScreen Filtresi'ni yönetmesini kullanıcı engeller. Bu ilke ayarını etkinleştirirseniz, kullanıcıya SmartScreen Filtresi'ni istenir değil. Filtrelere olmayan tüm Web sitesi adresleri listesi gönderilen otomatik olarak Microsoft'a kullanıcıya sormadan izin verin. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, kullanıcı ilk kez çalıştırma deneyimi sırasında SmartScreen Filtresi'ni açmak isteyip karar vermeniz istenir.
  
  **Varsayılan**: Etkinleştir  
  
- **Internet Explorer MIME algılaması güvenlik özelliği işlemleri**  
  Bu ilke ayarı, Internet Explorer MIME algılaması tek bir dosyanın daha tehlikeli bir dosya türü için engelleyecek olup olmadığını belirler. Bu ilke ayarını etkinleştirirseniz, MIME algılaması daha tehlikeli bir dosya türü için bir türde bir dosya hiçbir zaman yükseltmez. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer işlemleri daha tehlikeli bir dosya türü için bir türde bir dosya MIME algılamasının izin verir. Bu ilke ayarı yapılandırmazsanız MIME algılaması daha tehlikeli bir dosya türü için bir türde bir dosya hiçbir zaman yükseltmez.
  
  **Varsayılan**: Enabled  
  
- **İmzalı ActiveX denetimlerini Internet Explorer kısıtlı bölge yükle**  
  Bu ilke ayarı, kullanıcıların imzalanmış ActiveX denetimlerini bölgesinde sayfasından yükleyip yükleyemeyeceklerini yönetmenize olanak sağlar. Bu ilkeyi etkinleştirmek, kullanıcıların kullanıcı müdahalesi olmadan imzalı denetimleri indirebilirsiniz. Aşağı açılan kutusunda istemi seçerseniz, kullanıcıların güvenilen yayımcılar tarafından imzalanmış denetimleri indirin etkinleştirilip etkinleştirilmeyeceğini sorgulanır. Güvenilen Yayımcılar tarafından imzalanmış kod sessizce indirilir. İlke ayarını devre dışı bırakırsanız, imzalı denetimleri karşıdan yükleyemiyor. Bu ilke ayarı yapılandırmazsanız, kullanıcıların güvenilen yayımcılar tarafından imzalanmış denetimleri indirin etkinleştirilip etkinleştirilmeyeceğini sorgulanır. Güvenilen Yayımcılar tarafından imzalanmış kod sessizce indirilir.
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer otomatik tamamlama**  
  Bu otomatik tamamlama özelliği, unutmayın ve kullanıcı adları ve parolalar formlarında önerin. Bu ayarı etkinleştirirseniz, kullanıcı "kullanıcı adı ve parolaların" değiştiremez ya da "parolaları kaydetmek için sor". Kullanıcı adları ve parolaların için Otomatik Tamamlama özelliği etkinleştirilir. "Parola kaydetmemi iste" seçip seçmemeye karar verin gerekir. Bu ayar devre dışı bırakırsanız kullanıcı "kullanıcı adı ve parolaların" değiştiremez ya da "parolaları kaydetmek için sor". Kullanıcı adları ve parolaların için Otomatik Tamamlama özelliği kapalıdır. Kullanıcı parolaları kaydedilmeyeceğinin sorulması için de kapatılamaz. Bu ayarı yapılandırmazsanız, kullanıcının tam kullanıcı adı ve parola form ve parolaları kaydetme istemi seçeneği otomatik kapatma özgürlüğü sahip. Bu seçeneği görüntülemek için kullanıcıların Internet Seçenekleri iletişim kutusunu açın, İçindekiler sekmesini tıklatın ve ayarlar düğmesine tıklayın.
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer internet bölgesi çalıştırmak VBscript izin ver**  
  Bu ilke ayarı, VBScript belirli Internet Explorer bölgeleri sayfalarında çalıştırılıp çalıştırılmayacağını karar vermenize olanak tanır. Şu seçenekler mevcuttur: 
  - *Etkinleştirme* -herhangi bir etkileşim olmadan, belirli bölgelerde sayfalarında VBScript çalıştırır. 
  - *Komut İstemi* -çalışanlar istenir bölgede çalıştırılacak VBScript izin verilip verilmeyeceğini. 
  - *Devre dışı* -VBScript bölgede çalışmasını engellenir. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, belirtilen bölgede herhangi bir etkileşim olmadan bir VBScript çalıştırır. 
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer'ın kısıtlı bölgede tdc ActiveX denetimlerini kullanmak için etki alanları yalnızca onaylanmış**  
  Bu ilke ayarı, kullanıcı Web siteleri TDC ActiveX denetimini çalışıp çalışamayacağını denetler. Bu ilke ayarını etkinleştirirseniz, bu bölgedeki sitelerinden TDC ActiveX denetimini çalışmaz. Bu ilke ayarını devre dışı bırakırsanız, bu bölgedeki tüm sitelerden TDC ActiveX denetimi çalıştırılır.
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer Güvenilen Bölge ActiveX denetimleri karşı kötü amaçlı yazılımdan koruma çalışmaz**  
  Bu ilke ayarı, Internet Explorer karşı sayfalarında güvenli iseler denetlemek için ActiveX denetimleri, kötü amaçlı yazılımdan koruma programları çalışıp çalışmayacağını belirler. Bu ilke ayarını etkinleştirirseniz, Internet Explorer ActiveX denetiminin bir örneğini oluşturmak güvenli olup olmadığını görmek için kötü amaçlı yazılımdan koruma programınızı denetleyin olmaz. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer ActiveX denetiminin bir örneğini oluşturmak güvenli olup olmadığını görmek için kötü amaçlı yazılımdan koruma programı her zaman denetler. Bu ilke ayarı yapılandırmazsanız, Internet Explorer ActiveX denetiminin bir örneğini oluşturmak güvenli olup olmadığını görmek için kötü amaçlı yazılımdan koruma programı her zaman denetler. Kullanıcılar bu davranışı açıp kapatabilir, Internet Explorer güvenlik ayarlarını kullanarak kapatabilirsiniz.
  
  **Varsayılan**: Devre dışı 
  
- **Internet Explorer yerel makine bölge java izinleri**  
  Bu ilke ayarı, Java uygulamaları için izinleri yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz, Seçenekler açılır kutusundan seçebilirsiniz. Özel denetim izinlerini ayarlar için ayrı ayrı. Düşük güvenilirlik, uygulamaların tüm işlemleri sağlar. Orta düzey güvenilirlik (bir alanda bellek görüşmesi yapamaz program dışında), kendi sanal uygulamaların artı boş alan (istemci bilgisayarda bir güvenli depolama alanı) ve kullanıcı tarafından denetlenen dosya g/ç gibi özellikler sağlar. Yüksek güvenilirlik, korumalı alanında çalışmasını sağlar. Java uygulamaları çalışmasını önlemek için devre dışı bırakın. Bu ilke ayarını devre dışı bırakırsanız, Java uygulamalarını çalıştıramazsınız. Bu ilke ayarı yapılandırmazsanız, Java Orta çalışamaz.
  
  **Varsayılan**: Java devre dışı bırak 
  
- **Internet Explorer intranet bölgesi çalıştırma kötü amaçlı yazılımdan koruma ActiveX denetimleri karşı** Bu ilke ayarı, Internet Explorer karşı sayfalarında yüklemek güvenli olup olmadıklarını kontrol etmek için ActiveX denetimleri, kötü amaçlı yazılımdan koruma programları çalışıp çalışmayacağını belirler. Bu ilke ayarını etkinleştirirseniz, Internet Explorer ActiveX denetiminin bir örneğini oluşturmak güvenli olup olmadığını görmek için kötü amaçlı yazılımdan koruma programınızı denetleyin olmaz. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer ActiveX denetiminin bir örneğini oluşturmak güvenli olup olmadığını görmek için kötü amaçlı yazılımdan koruma programı her zaman denetler. Bu ilke ayarı yapılandırmazsanız, Internet Explorer ActiveX denetiminin bir örneğini oluşturmak güvenli olup olmadığını görmek için kötü amaçlı yazılımdan koruma programınızı denetleyin olmaz. Kullanıcılar bu davranışı açıp kapatabilir, Internet Explorer güvenlik ayarlarını kullanarak kapatabilirsiniz.
  
  **Varsayılan**: Devre dışı  

- **Internet Explorer'ın kısıtlı bölge kod parçacıkları**  
  Bu ilke ayarı, kullanıcı kod parçacıklarını çalıştırıp çalıştıramayacağını yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz, kullanıcı kod parçacıklarını çalıştırabilirsiniz. Bu ilke ayarını devre dışı bırakırsanız, kullanıcı kod parçacıklarını çalıştıramazsınız. Bu ilke ayarı yapılandırmazsanız, kullanıcı etkinleştirebilir veya kod parçacıklarını devre dışı bırakın.
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer işlemleri bildirim çubuğu**  
  Bu ilke ayarı dosyası veya kod yüklemeleri kısıtlandığında Internet Explorer işlemleri için bildirim çubuğu görüntülenmez yönetmenizi sağlar. Varsayılan olarak, Internet Explorer işlemleri için bildirim çubuğu görüntülenir. Bu ilke ayarını etkinleştirirseniz, Internet Explorer işlemleri için bildirim çubuğu görüntüler. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer işlemleri için bildirim çubuğu görüntülenmez. Bu ilke ayarı yapılandırmazsanız, bildirim çubuğu için Internet Explorer işlemleri görüntülemez.
  
  **Varsayılan**: Enabled  
  
- **İmzalı ActiveX denetimlerini Internet Explorer internet bölgesi yükle**  
  Bu ilke ayarı, kullanıcıların imzalanmış ActiveX denetimlerini bölgesinde sayfasından yükleyip yükleyemeyeceklerini yönetmenize olanak sağlar. Bu ilkeyi etkinleştirmek, kullanıcıların kullanıcı müdahalesi olmadan imzalı denetimleri indirebilirsiniz. Aşağı açılan kutusunda istemi seçerseniz, kullanıcıların güvenilen yayımcılar tarafından imzalanmış denetimleri indirin etkinleştirilip etkinleştirilmeyeceğini sorgulanır. Güvenilen Yayımcılar tarafından imzalanmış kod sessizce indirilir. İlke ayarını devre dışı bırakırsanız, imzalı denetimleri karşıdan yükleyemiyor. Bu ilke ayarı yapılandırmazsanız, kullanıcıların güvenilen yayımcılar tarafından imzalanmış denetimleri indirin etkinleştirilip etkinleştirilmeyeceğini sorgulanır. Güvenilen Yayımcılar tarafından imzalanmış kod sessizce indirilir.
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer kısıtlı bölge Akıllı Ekran**  
  Bu ilke kötü amaçlı içerik için bu bölgedeki sayfalar SmartScreen Filtresi tarar olmadığını ayarı denetler. Bu ilke ayarını etkinleştirirseniz, SmartScreen Filtresi, kötü amaçlı içerik için bu bölgedeki sayfalar tarar. Bu ilke ayarını devre dışı bırakırsanız, kötü amaçlı içerik için bu bölgedeki sayfalar SmartScreen Filtresi taramaz. Bu ilke ayarı yapılandırmazsanız, kullanıcıya SmartScreen Filtresi'ni kötü amaçlı içerik için bu bölgedeki sayfalar tarayıp taramayacağını seçebilirsiniz. Not: Internet Explorer 7'de, bu ilke ayarı, kimlik avı filtre kötü amaçlı içerik için bu bölgedeki sayfalar tarayıp taramayacağını denetler.
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer kaldırmayı Çalıştır eski ActiveX denetimleri için bu saat düğmesi**  
  Bu ilke ayarı, kullanıcıların görmesini "Bu kez çalıştır" düğmesi ve Internet Explorer'ın belirli eski ActiveX denetimlerini çalışmasını durdurmak sağlar. Bu ilke ayarını etkinleştirirseniz, kullanıcılar Internet Explorer güncel olmayan bir ActiveX denetimi engellediğinde görüntülenen uyarı iletisi "Bu kez çalıştır" düğmesi görmez. Devre dışı bırakmak veya bu ilke ayarı yapılandırmazsanız, kullanıcıların Internet Explorer güncel olmayan bir ActiveX denetimi engellediğinde görüntülenen uyarı iletisi "Bu kez çalıştır" düğmesi görürsünüz. Bu düğmeye tıklandığında, güncel olmayan bir ActiveX denetimi bir kez çalıştır kullanıcı sağlar. Daha fazla bilgi için "Eski ActiveX denetimlerini" Internet Explorer TechNet kitaplığında bkz.
  
  **Varsayılan**: Enabled 
  
- **Internet Explorer Internet bölgesi başlatma uygulamalarına ve bir iframe içinde dosyaları**  
  Bu ilke ayarı, uygulamaları çalıştırabilir ve dosyaları, HTML sayfaları bu bölgedeki bir IFRAME başvurusuna şuradan indirilebilir yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, kullanıcılar uygulamalarını çalıştırmak ve kullanıcı müdahalesi olmadan bu bölgedeki sayfalarında IFRAMES dosyaları indirin. Açılan kutusunda seçtiğiniz istemi, kullanıcılara uygulamalarını çalıştırmak ve bu bölgedeki sayfalarında IFRAMES dosyaları karşıdan seçmeleri istenir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcıların uygulamaları çalıştırmaya ve bu bölgedeki sayfalarında IFRAMES dosyaları indirme engellenir. Bu ilke ayarı yapılandırmazsanız, kullanıcıların isteyip istemediğinizi belirleyin uygulamalarını çalıştırmak ve bu bölgedeki sayfalarında IFRAMES dosyaları indirmek için sorgulanır
  
  **Varsayılan**: Devre Dışı Bırak 
  
- **Internet Explorer kısıtlı bölge, farklı etki alanlarında windows ve çerçeveleri gidin**  
  Bu ilke ayarı kaynak ve hedef farklı windows olduğunda içerik bir etki alanından farklı bir etki alanına sürükleyerek seçenekleri ayarlamanıza olanak sağlar. Bu ilke ayarını etkinleştirin ve Etkinleştir'i tıklatın, kaynak ve hedef farklı windows olduğunda kullanıcıların içeriği bir etki alanından farklı bir etki alanına sürükleyebilirsiniz. Kullanıcılar, bu ayarı değiştiremezsiniz. Bu ilke ayarını etkinleştirin ve devre dışı bırak'a tıklayın, hem kaynak hem de hedef farklı windows olduğunda kullanıcıların içeriği bir etki alanından farklı bir etki alanına sürükleyemezsiniz. Kullanıcılar, bu ayarı değiştiremezsiniz. Bu ilke ayarını devre dışı bırakır veya, yapılandırmayın olduğunda kaynak ve hedef farklı windows Internet Explorer 10'da, kullanıcıların içeriği bir etki alanından farklı bir etki alanına sürükleyemezsiniz. Kullanıcıların Internet Seçenekleri iletişim kutusunda Bu ayarı değiştirebilirsiniz. Bu ilke devre dışı bırakır veya, yapılandırmayın olduğunda kaynak ve hedef farklı windows Internet Explorer 9 ve önceki sürümlerinde, kullanıcıların içeriği bir etki alanından farklı bir etki alanına sürükleyebilirsiniz. Kullanıcılar, bu ayarı değiştiremezsiniz.
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer internet bölgesi Akıllı Ekran**  
  Bu ilke kötü amaçlı içerik için bu bölgedeki sayfalar SmartScreen Filtresi tarar olmadığını ayarı denetler. Bu ilke ayarını etkinleştirirseniz, SmartScreen Filtresi, kötü amaçlı içerik için bu bölgedeki sayfalar tarar. Bu ilke ayarını devre dışı bırakırsanız, kötü amaçlı içerik için bu bölgedeki sayfalar SmartScreen Filtresi taramaz. Bu ilke ayarı yapılandırmazsanız, kullanıcıya SmartScreen Filtresi'ni kötü amaçlı içerik için bu bölgedeki sayfalar tarayıp taramayacağını seçebilirsiniz. Not: Internet Explorer 7'de, bu ilke ayarı, kimlik avı filtre kötü amaçlı içerik için bu bölgedeki sayfalar tarayıp taramayacağını denetler.
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer Güvenilen Bölge java izinleri kilitli**  
  Bu ilke ayarı, Java uygulamaları için izinleri yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz, Seçenekler açılır kutusundan seçebilirsiniz. Özel denetim izinlerini ayarlar için ayrı ayrı. Düşük güvenilirlik, uygulamaların tüm işlemleri sağlar. Orta düzey güvenilirlik (bir alanda bellek görüşmesi yapamaz program dışında), kendi sanal uygulamaların artı boş alan (istemci bilgisayarda bir güvenli depolama alanı) ve kullanıcı tarafından denetlenen dosya g/ç gibi özellikler sağlar. Yüksek güvenilirlik, korumalı alanında çalışmasını sağlar. Java uygulamaları çalışmasını önlemek için devre dışı bırakın. Bu ilke ayarını devre dışı bırakırsanız, Java uygulamalarını çalıştıramazsınız. Bu ilke ayarı yapılandırmazsanız, Java uygulamalarını devre dışı bırakıldı.
  
  **Varsayılan**: Java devre dışı bırak 
  
- **Internet Explorer indirilen programları imzaları denetle**  
  Bu ilke ayarı, Internet Explorer (imzalı yazılım yayımcısını tanımlar ve bu değiştirilmediğini veya üzerinde oynama doğrular) dijital imzalar için denetleyip denetlemeyeceğini yürütülebilir programlar indirmeden önce kullanıcı bilgisayarları üzerinde yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz, Internet Explorer yürütülebilir programlar dijital imzalarını denetler ve kullanıcının bilgisayarına indirmeden önce kimliklerini görüntülemez. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer yürütülebilir programlar dijital imzaları denetleme olmaz veya kullanıcının bilgisayarına indirmeden önce kimliklerini görüntülemez. Bu ilke yapılandırmazsanız, Internet Explorer yürütülebilir programlar dijital imzaları denetleme olmaz veya kullanıcının bilgisayarına indirmeden önce kimliklerini görüntülemez.
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer web tarayıcı denetimi bölge kodlamasını kısıtlı**  
  Bu ilke ayarı, bir sayfa komut dosyası aracılığıyla gömülü WebBrowser denetimi denetimi olup olmadığını belirler. Bu ilke ayarını etkinleştirirseniz, WebBrowser denetimi betik erişime izin. Bu ilke ayarını devre dışı bırakırsanız, WebBrowser denetimi betik erişmesine izin verilmiyor. Bu ilke ayarı yapılandırmazsanız, kullanıcı etkinleştirebilir veya betik erişimi WebBrowser denetimi devre dışı bırakın. Varsayılan olarak, yalnızca yerel makine ve Intranet bölgeleri WebBrowser denetimi betik erişime izin.
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer kısıtlı bölge arası site komut dosyası filtresi**  
  Bu ilke, siteler arası betik (XSS) filtre algılayın ve bu bölgedeki Web siteleri içine siteler arası betik eklemelerini engelle denetler. Bu ilke ayarını etkinleştirirseniz, bu bölgedeki sitelerden XSS filtre açıktır ve XSS filtre siteler arası betik eklemelerini engellemeye çalışır. Bu ilke ayarını devre dışı bırakırsanız, bu bölgedeki sitelerden XSS filtre kapalıdır ve Internet Explorer, siteler arası betik eklemelerini izin verir.
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer kısıtlı bölge ikili ve komut dosyası davranışları**  
  Bu ilke ayarı, dinamik ikili ve betik davranışları yönetmenize olanak sağlar: HTML öğeleri bağlı oldukları için belirli işlevi kapsülleyen bileşenler. Bu ilke ayarını etkinleştirirseniz, ikili ve betik davranışları kullanılabilir. Yönetici aşağı açılan kutusunda onaylı seçerseniz, yalnızca yönetici tarafından onaylanan davranışları ikili davranışları güvenlik kısıtlama ilkesi altında listelenen kullanılabilir. Bu ilke ayarını devre dışı bırakırsanız, uygulamaları özel bir güvenlik yöneticisi uyguladıysanız sürece, ikili ve betik davranışları mevcut değildir. Bu ilke ayarı yapılandırmazsanız, uygulamaları özel bir güvenlik yöneticisi uyguladıysanız sürece, ikili ve betik davranışları mevcut değildir.
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer güvenlik ayarları denetimi**  
  Bu ilke ayarı, riske Internet Explorer ayarlarını belirlemek için Internet Explorer güvenlik ayarlarını denetleyen güvenlik ayarlarını denetleme özelliği kapatır. Bu ilke ayarını etkinleştirirseniz, bu özellik devre dışıdır. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, özelliği etkinleştirilir.
  
  **Varsayılan**: Enabled  
  
- **Güvenli olmayan dosyalar için Internet Explorer internet bölgesi güvenlik uyarısı**  
  "Dosya – Güvenlik Uyarısı açın" iletisi görüntülenirse, kullanıcı yürütülebilir dosyaları veya diğer olmayabilecek dosyaları (örneğin dosya Gezgini'ni kullanarak bir intranet dosya paylaşımından) açmayı denediğinde bu ilke ayarı denetler. Bu ilke ayarını etkinleştirin ve etkinleştirmek için açılan kutudan ayarlayın, bu dosyalar olmadan bir güvenlik uyarısı açın. Açılan kutunun istemine ayarlarsanız, dosyaları açmadan önce bir güvenlik uyarısı görüntülenir. Bu ilke ayarını devre dışı bırakırsanız, bu dosyalar açmayın. Bu ilke ayarı yapılandırmazsanız, kullanıcı, bilgisayar bu dosyaları nasıl işlediğini yapılandırabilirsiniz. Varsayılan olarak, bu dosyalar Intranet ve yerel bilgisayar bölgeleri, etkin Yasak bölgesinde engellenen ve Internet ve güvenilen bölgelerde isteyecek şekilde ayarlayın.
  
  **Varsayılan**: İstem  
  
- **Internet Explorer intranet bölgesi java izinleri**  
  Bu ilke ayarı, Java uygulamaları için izinleri yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz, Seçenekler açılır kutusundan seçebilirsiniz. Özel denetim izinlerini ayarlar için ayrı ayrı. Düşük güvenilirlik, uygulamaların tüm işlemleri sağlar. Orta düzey güvenilirlik (bir alanda bellek görüşmesi yapamaz program dışında), kendi sanal uygulamaların artı boş alan (istemci bilgisayarda bir güvenli depolama alanı) ve kullanıcı tarafından denetlenen dosya g/ç gibi özellikler sağlar. Yüksek güvenilirlik, korumalı alanında çalışmasını sağlar. Java uygulamaları çalışmasını önlemek için devre dışı bırakın. Bu ilke ayarını devre dışı bırakırsanız, Java uygulamalarını çalıştıramazsınız. Bu ilke ayarı yapılandırmazsanız, Java Orta çalışamaz.
  
  **Varsayılan**: Yüksek güvenilirlik 
  
- **Internet Explorer eski blok ActiveX denetimleri**  </br>
  Bu ilke ayarı, Internet Explorer blokları belirli ActiveX denetimlerini eski olup olmadığını belirler. Güncel olmayan bir ActiveX denetimleri, Intranet bölgesinde hiçbir zaman engellenir. Bu ilke ayarını etkinleştirirseniz, Internet Explorer eski ActiveX denetimlerini engelleme durdurur. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, Internet Explorer belirli eski ActiveX denetimlerini engelleyecek şekilde devam eder. Daha fazla bilgi için "Eski ActiveX denetimlerini" Internet Explorer TechNet kitaplığında bkz.
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer'ın kısıtlı bölge açılır pencere engelleyicisi**  
  Bu ilke ayarı, istenmeyen açılır pencerelerin görüntülenip görüntülenmeyeceğini yönetmenize olanak sağlar. Son kullanıcı bağlantıyı tıklattığında açılan açılan pencereler engellenmez. Bu ilke ayarını etkinleştirirseniz, en istenmeyen açılır pencereleri görüntülenmesi engellenir. Bu ilke ayarını devre dışı bırakırsanız, açılır pencereleri görünmesini engelleyen değildir. Bu ilke ayarı yapılandırmazsanız en istenmeyen açılır pencereleri görüntülenmesi engellenir.
  
  **Varsayılan**: Etkinleştir  
  
- **Internet Explorer MK protokolü güvenlik kısıtlaması işlemleri**  
  MK protokolü güvenlik kısıtlaması ilke ayarı, MK protokolü engelleyerek saldırı yüzey alanını azaltır. MK protokolü üzerinde bulunan kaynaklara başarısız olur. Bu ilke ayarını etkinleştirirseniz, MK protokolü, dosya Gezgini ve Internet Explorer'da engellenir ve MK protokolü üzerinde bulunan kaynaklara başarısız olur. Bu ilke ayarını devre dışı bırakırsanız, MK protokolü API uygulamaları kullanabilir. MK protokolü üzerinde bulunan kaynaklara dosya Gezgini ve Internet Explorer işlemleri için çalışır. Bu ilke ayarı yapılandırmazsanız, MK protokolü, dosya Gezgini ve Internet Explorer'da engellenir ve MK protokolü üzerinde bulunan kaynaklara başarısız olur.
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer Güvenilen Bölge java izinleri**  </br>
  Bu ilke ayarı, Java uygulamaları için izinleri yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz, Seçenekler açılır kutusundan seçebilirsiniz. Özel denetim izinlerini ayarlar için ayrı ayrı. Düşük güvenilirlik, uygulamaların tüm işlemleri sağlar. Orta düzey güvenilirlik (bir alanda bellek görüşmesi yapamaz program dışında), kendi sanal uygulamaların artı boş alan (istemci bilgisayarda bir güvenli depolama alanı) ve kullanıcı tarafından denetlenen dosya g/ç gibi özellikler sağlar. Yüksek güvenilirlik, korumalı alanında çalışmasını sağlar. Java uygulamaları çalışmasını önlemek için devre dışı bırakın. Bu ilke ayarını devre dışı bırakırsanız, Java uygulamalarını çalıştıramazsınız. Bu ilke ayarı yapılandırmazsanız, düşük güvenilirlik izni ayarlanır.
  
  **Varsayılan**: Yüksek güvenilirlik  
  
- **Internet Explorer bölge java uygulamaları için komut dosyası kısıtlı**  
  Bu ilke ayarı, uygulamaları bölge içindeki komut dosyaları için sunulan yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, komut dosyaları otomatik olarak kullanıcı müdahalesi olmadan uygulamalara erişebilir. Açılan kutusunda seçtiğiniz istemi, kullanıcılar uygulamalara erişmek betiklere izin vermek isteyip istemediğinizi seçin için sorgulanır. Bu ilke ayarını devre dışı bırakırsanız, betikleri, uygulamalara erişimi engellenir. Bu ilke ayarı yapılandırmazsanız, betikleri, uygulamalara erişimi engellenir.
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer kısıtlı bölge java izinleri kilitli**  </br>
  Bu ilke ayarı, Java uygulamaları için izinleri yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz, Seçenekler açılır kutusundan seçebilirsiniz. Özel denetim izinlerini ayarlar için ayrı ayrı. Düşük güvenilirlik, uygulamaların tüm işlemleri sağlar. Orta düzey güvenilirlik (bir alanda bellek görüşmesi yapamaz program dışında), kendi sanal uygulamaların artı boş alan (istemci bilgisayarda bir güvenli depolama alanı) ve kullanıcı tarafından denetlenen dosya g/ç gibi özellikler sağlar. Yüksek güvenilirlik, korumalı alanında çalışmasını sağlar. Java uygulamaları çalışmasını önlemek için devre dışı bırakın. Bu ilke ayarını devre dışı bırakırsanız, Java uygulamalarını çalıştıramazsınız. Bu ilke ayarı yapılandırmazsanız, Java uygulamalarını devre dışı bırakıldı.
  
  **Varsayılan**: Java devre dışı bırak 
  
- **Internet Explorer internet bölgesi izin ActiveX denetimlerini kullanmak için etki alanları yalnızca onaylanmış**  </br>
  Bu ilke ayarı, Web siteleri dışında ActiveX denetimini yüklü Web sitesini çalıştırmak ActiveX denetimlerini izin vermek için kullanıcı istenirse denetler. Bu ilke ayarını etkinleştirirseniz, ActiveX denetimleri, bu bölgedeki sitelerinden çalıştırmadan önce kullanıcıya sorulur. Kullanıcı, denetimlerin geçerli siteden veya tüm sitelerden çalışmasına izin vermeyi seçebilirsiniz. Bu ilke ayarını devre dışı bırakırsanız, kullanıcı başına site ActiveX istemini görmez ve bu bölgedeki tüm sitelerden ActiveX denetimlerini çalıştırabilirsiniz.
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer dahil tüm ağ yolları**  
  Internet Explorer dahil tüm ağ yolları
  
  **Varsayılan**: Devre dışı 
  
- **Internet Explorer internet bölgesi korumalı mod**  
  Bu ilke ayarı, korumalı modunu açmak sağlar. Korumalı modu, Internet Explorer, Internet Explorer için kayıt defteri ve dosya sistemine yazabilirsiniz konumları azaltarak kötü amaçla kullanılan güvenlik açıklarına karşı korumaya yardımcı olur. Bu ilke ayarını etkinleştirirseniz, korumalı mod etkinleştirilir. Kullanıcı, korumalı modunu devre dışı bırakmak olamaz. Bu ilke ayarını etkinleştirirseniz, korumalı mod kapalıdır. Kullanıcı, korumalı modu kapatamazsınız. Bu ilke ayarı yapılandırmazsanız, açın veya korumalı modunu kapatın.
  
  **Varsayılan**: Etkinleştir 
  
- **İnternet bölgesi Internet Explorer'ı başlatın ve ActiveX denetimlerini betik güvenli olarak işaretlenmemiş**  
  Bu ilke ayarı, güvenli olarak işaretlenmemiş ActiveX denetimlerini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, ActiveX denetimleri, güvenilir olmayan verileri veya betikler için nesne güvenliği ayarlamadan parametreler ile yüklenir ve komut dosyalı çalıştırın. Bu ayar, güvenli ve yönetilen bölgeler dışında önerilmez. Bu ayar, başlatılır ve komut dosyası için hem güvenli hem de güvenli denetimler neden olur, betik ActiveX denetimlerini yoksayma seçeneği için güvenli olarak işaretlenmiş. Bu ilke ayarını etkinleştirin ve istemi açılır kutusunda, kullanıcıların denetimi parametrelerle yüklemeye izin verilip verilmeyeceği veya komut dosyası. Bu ilke ayarını devre dışı bırakırsanız, güvenli hale getirilemez ActiveX denetimlerini parametrelerle yüklü değil veya komut dosyası. Bu ilke ayarı yapılandırmazsanız, güvenli hale getirilemez ActiveX denetimlerini parametrelerle yüklü değil veya komut dosyası.
  
  **Varsayılan**: Devre Dışı Bırak 
  
- **Internet Explorer kısıtlı bölge akıllı ekran aşağıya kilitli**  </br>
  Bu ilke kötü amaçlı içerik için bu bölgedeki sayfalar SmartScreen Filtresi tarar olmadığını ayarı denetler. Bu ilke ayarını etkinleştirirseniz, SmartScreen Filtresi, kötü amaçlı içerik için bu bölgedeki sayfalar tarar. Bu ilke ayarını devre dışı bırakırsanız, kötü amaçlı içerik için bu bölgedeki sayfalar SmartScreen Filtresi taramaz. Bu ilke ayarı yapılandırmazsanız, kullanıcıya SmartScreen Filtresi'ni kötü amaçlı içerik için bu bölgedeki sayfalar tarayıp taramayacağını seçebilirsiniz. Not: Internet Explorer 7'de, bu ilke ayarı, kimlik avı filtre kötü amaçlı içerik için bu bölgedeki sayfalar tarayıp taramayacağını denetler.
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer kilitlenmesi algılama**  
  Bu ilke ayarı, eklenti Yönetimi kilitlenme algılaması özelliği yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, Internet Explorer'da bir kilitlenme Windows XP Professional Service Pack 1 ve önceki sürümlerinde, yani bulunan davranışı sergiler Windows hata bildirimi çağırmak için. Windows hata bildirimi için tüm ilke ayarları uygulanmaya devam eder. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, eklenti yönetimi için kilitlenme algılaması özelliği çalışır durumdadır.
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer internet bölgesi java izinleri**  
  Bu ilke ayarı, Java uygulamaları için izinleri yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz, Seçenekler açılır kutusundan seçebilirsiniz. Özel denetim izinlerini ayarlar için ayrı ayrı. Düşük güvenilirlik, uygulamaların tüm işlemleri sağlar. Orta düzey güvenilirlik (bir alanda bellek görüşmesi yapamaz program dışında), kendi sanal uygulamaların artı boş alan (istemci bilgisayarda bir güvenli depolama alanı) ve kullanıcı tarafından denetlenen dosya g/ç gibi özellikler sağlar. Yüksek güvenilirlik, korumalı alanında çalışmasını sağlar. Java uygulamaları çalışmasını önlemek için devre dışı bırakın. Bu ilke ayarını devre dışı bırakırsanız, Java uygulamalarını çalıştıramazsınız. Bu ilke ayarı yapılandırmazsanız izni yüksek güvenilirlik olarak ayarlanır.
  
  **Varsayılan**: Java devre dışı bırak  
  
- **Internet Explorer'ın kısıtlı bölge etkin komut dosyası**  
  Bu ilke ayarı, kod sayfalarında bölgesinde çalıştırılıp çalıştırılmayacağını yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, kod sayfalarında bölgede otomatik olarak çalıştırabilirsiniz. Açılan kutusunda seçtiğiniz istemi, kullanıcı kodu çalıştırmak için bölge sayfalarında izin verip vermeyeceklerini sorgulanır. Şirket bu ilke ayarı, kod devre dışı bırakırsanız bölgedeki sayfalar çalışması engellenir. Bu ilke ayarı yapılandırmazsanız, kod sayfalarında bölgesinde çalışması engellenir.
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer internet bölgesi oturum açma seçenekleri**  
  Bu ilke ayarı, oturum açma seçenekleri ayarlarını yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz, aşağıdaki oturum açma seçenekleri arasından seçim yapabilirsiniz. Anonim oturum açma devre dışı bırakma HTTP kimlik doğrulama ve kullanım Konuk hesap için yalnızca ortak Internet dosya sistemi (CIFS) protokolü. Kullanıcı adı ve parola sorgusu kullanıcıları için kullanıcı kimliklerini ve parolaları sor. Bir Kullanıcı sorgulandıktan sonra bu değerleri sessizce oturumunun kalanı için kullanılabilir. Yalnızca sorgu kullanıcılar için kullanıcı kimliklerini ve parolaları diğer bölgelerdeki Intranet bölgesinde otomatik oturum açma. Bir Kullanıcı sorgulandıktan sonra bu değerleri sessizce oturumunun geri kalanı için kullanılabilir. Windows NT Sınama yanıtı (NTLM kimlik doğrulaması olarak da bilinir) kullanarak oturum aç'ı denemek için otomatik oturum geçerli kullanıcı adı ve parolayla. Sunucu, Windows NT Sınama yanıtı, oturum açma kullanan ağ kullanıcı adını ve parolasını oturum destekliyorsa. Sunucu, Windows NT Sınama yanıtı desteklemiyorsa, kullanıcının kullanıcı adı ve parola sağlamak için sorgulanır. Bu ilke ayarını devre dışı bırakırsanız, oturum açma için otomatik günlük yalnızca Intranet bölgesinde ayarlanır. Bu ilke ayarı yapılandırmazsanız, oturum açma için otomatik oturum ayarlamak da Intranet bölgesinde.
  
  **Varsayılan**: İstem  
  
- **Internet Explorer kısıtlı bölge vbscript çalışmasına izin ver**  </br>  
  Bu ilke ayarı, Internet Explorer'da belirtilen bölgeden sayfalarında VBScript çalıştırılıp çalıştırılmayacağını yönetmenizi sağlar. VBScript, açılan kutuya Etkinleştir'i seçtiyseniz, kullanıcı müdahalesi olmadan çalıştırabilirsiniz. Aşağı açılan kutusunda seçtiğiniz istemi, kullanıcıların VBScript çalışmasına izin verilip verilmeyeceğini seçmeniz istenir. Aşağı açılan kutuya devre dışı bırak'ı seçtiyseniz, VBScript çalışması engellenir. Yapılandırma görmüyorsanız veya bu ilke ayarını devre dışı VBScript çalışması engellenir.
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer internet bölgesi arasında windows farklı etki alanlarından içerik sürükleyin**  
  Bu ilke ayarı kaynak ve hedef farklı windows olduğunda içerik bir etki alanından farklı bir etki alanına sürükleyerek seçenekleri ayarlamanıza olanak sağlar. Bu ilke ayarını etkinleştirin ve Etkinleştir'i tıklatın, kaynak ve hedef farklı windows olduğunda kullanıcıların içeriği bir etki alanından farklı bir etki alanına sürükleyebilirsiniz. Kullanıcılar, bu ayarı değiştiremezsiniz. Bu ilke ayarını etkinleştirin ve devre dışı bırak'a tıklayın, hem kaynak hem de hedef farklı windows olduğunda kullanıcıların içeriği bir etki alanından farklı bir etki alanına sürükleyemezsiniz. Kullanıcılar, bu ayarı değiştiremezsiniz. Bu ilke ayarını devre dışı bırakır veya, yapılandırmayın olduğunda kaynak ve hedef farklı windows Internet Explorer 10'da, kullanıcıların içeriği bir etki alanından farklı bir etki alanına sürükleyemezsiniz. Kullanıcıların Internet Seçenekleri iletişim kutusunda Bu ayarı değiştirebilirsiniz. Bu ilke devre dışı bırakır veya, yapılandırmayın olduğunda kaynak ve hedef farklı windows Internet Explorer 9 ve önceki sürümlerinde, kullanıcıların içeriği bir etki alanından farklı bir etki alanına sürükleyebilirsiniz. Kullanıcılar, bu ayarı değiştiremezsiniz.
  
  **Varsayılan**: Devre dışı 
  
- **Intranet Bölgesi Internet Explorer'ı başlatın ve ActiveX denetimlerini betik güvenli olarak işaretlenmemiş**  
  Bu ilke ayarı, güvenli olarak işaretlenmemiş ActiveX denetimlerini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, ActiveX denetimleri, güvenilir olmayan verileri veya betikler için nesne güvenliği ayarlamadan parametreler ile yüklenir ve komut dosyalı çalıştırın. Bu ayar, güvenli ve yönetilen bölgeler dışında önerilmez. Bu ayar, başlatılır ve komut dosyası için hem güvenli hem de güvenli denetimler neden olur, betik ActiveX denetimlerini yoksayma seçeneği için güvenli olarak işaretlenmiş. Bu ilke ayarını etkinleştirin ve istemi açılır kutusunda, kullanıcıların denetimi parametrelerle yüklemeye izin verilip verilmeyeceği veya komut dosyası. Bu ilke ayarını devre dışı bırakırsanız, güvenli hale getirilemez ActiveX denetimlerini parametrelerle yüklü değil veya komut dosyası. Bu ilke ayarı yapılandırmazsanız, güvenli hale getirilemez ActiveX denetimlerini parametrelerle yüklü değil veya komut dosyası.
  
  **Varsayılan**: Devre Dışı Bırak 
  
- **Internet Explorer indirme kasaları**  
  Bu ilke ayarı, kullanıcının bilgisayarına bir akışı'ndan indirilen kasaları (dosya ekleri) sahip kullanıcı engeller. Bu ilke ayarını etkinleştirirseniz, kullanıcı bir akışa özellik sayfası Motoru'nu indirmek için akış eşitleme altyapısı ayarlanamaz. Bir geliştirici, akış API'leri aracılığıyla indirme ayarı değiştiremezsiniz. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, kullanıcı bir akışa özellik sayfası Motoru'nu indirmek için akış eşitleme altyapısı ayarlayabilirsiniz. Bir geliştirici akış API'leri aracılığıyla indirme ayarını değiştirebilirsiniz.
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer kısıtlı bölge İmzalanmamış ActiveX denetimlerini indirin**  </br>
  Bu ilke ayarı, kullanıcıların İmzasız ActiveX denetimlerini bölgesinden yükleyip yükleyemeyeceklerini yönetmenize olanak sağlar. Bu tür kod, özellikle güvenilmeyen bir bölgeden Bekletmeden çıkarken zararlı olabilir. Bu ilke ayarını etkinleştirirseniz, kullanıcıların kullanıcı müdahalesi olmadan imzasız denetimlerini çalıştırabilirsiniz. Açılan kutuda istemi seçerseniz, kullanıcıların imzasız denetiminin çalışmasına izin verip vermeyeceklerini sorgulanır. Bu ilke ayarını devre dışı bırakırsanız, kullanıcıların imzasız denetimleri çalıştıramaz. Bu ilke ayarı yapılandırmazsanız, kullanıcıların imzasız denetimleri çalıştıramaz.
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer internet bölgesi, Windows'da farklı etki alanlarından içerik sürükleyin**  
  Bu ilke ayarı, kullanıcıların İmzasız ActiveX denetimlerini bölgesinden yükleyip yükleyemeyeceklerini yönetmenize olanak sağlar. Bu tür kod, özellikle güvenilmeyen bir bölgeden Bekletmeden çıkarken zararlı olabilir. Bu ilke ayarını etkinleştirirseniz, kullanıcıların kullanıcı müdahalesi olmadan imzasız denetimlerini çalıştırabilirsiniz. Açılan kutuda istemi seçerseniz, kullanıcıların imzasız denetiminin çalışmasına izin verip vermeyeceklerini sorgulanır. Bu ilke ayarını devre dışı bırakırsanız, kullanıcıların imzasız denetimleri çalıştıramaz. Bu ilke ayarı yapılandırmazsanız, kullanıcıların imzasız denetimleri çalıştıramaz.
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer işlemleri Active X yüklemesini kısıtla**  </br>
  Bu ilke ayarı, Web tarayıcı denetimi barındırma uygulamaları otomatik ActiveX denetimi yüklenmesini sorması için etkinleştirir. Bu ilke ayarını etkinleştirirseniz, tüm işlemler için ActiveX denetimi yüklemesinin otomatik isteyen Web tarayıcı denetimi engeller. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, Web tarayıcı denetimi ActiveX denetimi yüklemesinin tüm işlemler için otomatik olarak sorulmasını engellemez.
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer internet bölgesi kod parçacıklarını** Bu ilke ayarı, kullanıcı kod parçacıklarını çalıştırıp çalıştıramayacağını yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz, kullanıcı kod parçacıklarını çalıştırabilirsiniz. Bu ilke ayarını devre dışı bırakırsanız, kullanıcı kod parçacıklarını çalıştıramazsınız. Bu ilke ayarı yapılandırmazsanız, kullanıcı etkinleştirebilir veya kod parçacıklarını devre dışı bırakın.
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer kısıtlı bölge sürükleyin ve bırakın veya kopyalama ve yapıştırmanın**  
  Bu ilke ayarı, kullanıcıların dosyaları ya da kopyalama sürükleyin ve bölgede bir kaynak dosyalarından yapıştırma yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, kullanıcılar dosyaları veya kopyalama sürükleyin ve bu bölge dosyalarından otomatik olarak yapıştırın. Aşağı açılan kutusunda istemi seçerseniz, kullanıcıların sürükleyin veya kopya dosyalar bu bölgeden verilmeyeceğini seçmek için sorgulanır. Bu ilke ayarını devre dışı bırakırsanız, kullanıcıların dosyaları sürükleyerek veya kopyalama ve dosyaları bu bölgeden yapıştırma engellenir. Bu ilke ayarı yapılandırmazsanız, kullanıcıların sürükleyin veya kopya dosyalar bu bölgeden verilmeyeceğini seçmek için sorgulanır.
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **İmza geçersiz olduğunda Internet Explorer yazılım** </br>
  Bu ilke ayarı ActiveX denetimlerini ve dosya indirme gibi yazılımlar yüklenebilir ya da imzası geçersiz olsa bile kullanıcı tarafından çalıştırılan yönetmenizi sağlar. Geçersiz bir imza, birisi dosyasıyla yapmadığından gösterebilir. Bu ilke ayarını etkinleştirirseniz, kullanıcılar dosyaları, geçersiz imzalı kurulmayı veya istenir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcılar çalıştırın veya geçersiz bir imza ile dosyalarını yükleyin. Bu ilke yapılandırmazsanız, kullanıcıların çalıştırmak veya geçersiz bir imza ile dosyaları yüklemek seçebilirsiniz.
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer'ın kısıtlı bölge Kopyala ve Yapıştır komut dosyası aracılığıyla** </br> Bu ilke ayarı, belirli bir bölgede (örneğin, kesme, kopyalama ve yapıştırma) Pano işlemi betikleri gerçekleştirip gerçekleştiremeyeceğini yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz, komut dosyası bir pano işlemini gerçekleştirebilirsiniz. Açılan kutusunda seçtiğiniz istemi, kullanıcılar mı kullanılacağına yönelik pano işlemlerini gerçekleştirmek sorgulanır. Bu ilke ayarını devre dışı bırakırsanız, bir komut dosyası bir Pano işlemi gerçekleştirilemiyor. Bu ilke ayarı yapılandırmazsanız, bir komut dosyası bir Pano işlemi gerçekleştirilemiyor.
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer kısıtlı bölge farklı etki alanlarından içerik arasında windows sürükleyin**  
  Bu ilke ayarı kaynak ve hedef farklı windows olduğunda içerik bir etki alanından farklı bir etki alanına sürükleyerek seçenekleri ayarlamanıza olanak sağlar. Bu ilke ayarını etkinleştirin ve Etkinleştir'i tıklatın, kaynak ve hedef farklı windows olduğunda kullanıcıların içeriği bir etki alanından farklı bir etki alanına sürükleyebilirsiniz. Kullanıcılar, bu ayarı değiştiremezsiniz. Bu ilke ayarını etkinleştirin ve devre dışı bırak'a tıklayın, hem kaynak hem de hedef farklı windows olduğunda kullanıcıların içeriği bir etki alanından farklı bir etki alanına sürükleyemezsiniz. Kullanıcılar, bu ayarı değiştiremezsiniz. Bu ilke ayarını devre dışı bırakır veya, yapılandırmayın olduğunda kaynak ve hedef farklı windows Internet Explorer 10'da, kullanıcıların içeriği bir etki alanından farklı bir etki alanına sürükleyemezsiniz. Kullanıcıların Internet Seçenekleri iletişim kutusunda Bu ayarı değiştirebilirsiniz. Bu ilke devre dışı bırakır veya, yapılandırmayın olduğunda kaynak ve hedef farklı windows Internet Explorer 9 ve önceki sürümlerinde, kullanıcıların içeriği bir etki alanından farklı bir etki alanına sürükleyebilirsiniz. Kullanıcılar, bu ayarı değiştiremezsiniz.  <br><br>
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer kullanıcıları siteleri ekleme**  
  Ekleme veya siteler, güvenlik bölgelerinden kaldırma engeller. Web siteleri aynı güvenlik düzeyine sahip bir güvenlik bölgesi grubudur. Güvenlik bölgeleri için site yönetimi ayarlarını bu ilkeyi etkinleştirmek, devre dışı bırakılır. (Site yönetim görmek için ayarları, Internet Seçenekleri iletişim kutusundaki güvenlik bölgesi için Güvenlik sekmesine tıklayın ve sonra siteler düğmesine tıklayın.) Bu ilkeyi devre dışı bırakır veya yapılandırmazsanız, kullanıcıların Web sitelerinin, siteleri güvenilen siteler ve Yasak siteler bölgelerinden kaldırın ve yerel Intranet bölgesi için ayarları ekleyebilirsiniz. Bu ilke, kullanıcılar yönetici tarafından kurulan güvenlik bölgeleri için site yönetimi ayarlarını değiştirmesini engeller. Not: Güvenlik sekmesine arabirimden kaldıran (\User Configuration\Administrative Templates\Windows components\ınternet Explorer\Internet Denetim Masası ' bulunur) "güvenlik sayfası devre dışı bırak" ilkesi, bu ilkesine göre önceliklidir. Bu ilke etkinleştirilirse, göz ardı edilir. Ayrıca bkz: "güvenlik bölgeleri: Yalnızca makine ayarlarını kullan"ilkesi.
  
  **Varsayılan**: Devre dışı  
  
- **Windows Internet Explorer internet bölgesi başlatılan betik**  
  Bu ilke ayarı, betik tarafından başlatılan açılır pencereleri ve başlık ve durum çubuğu içeren windows üzerindeki kısıtlamaları yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz, bu bölgede Windows kısıtlamaları güvenlik uygulanmayacak. Bu özellik tarafından sağlanan bir güvenlik katmanı eklendi olmadan güvenlik bölgesi çalıştırır. Bu ilke ayarını devre dışı bırakırsanız, betik tarafından başlatılan açılır pencereleri ve başlık ve durum çubuğu içeren windows içerdiği zararlı olabilecek eylemler çalıştıramazsınız. Internet Explorer güvenlik özelliği bu bölgede işlem için Windows güvenlik kısıtlamaları komut dosyası özellik denetim ayarı tarafından belirlenen açıktır. Bu ilke ayarı yapılandırmazsanız, betik tarafından başlatılan açılır pencereleri ve başlık ve durum çubuğu içeren windows içerdiği zararlı olabilecek eylemler çalıştıramazsınız. Internet Explorer güvenlik özelliği bu bölgede işlem için Windows güvenlik kısıtlamaları komut dosyası özellik denetim ayarı tarafından belirlenen açıktır.
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer güvenlik bölgeleri yalnızca makine ayarlarını kullan**  
  Güvenlik bölgesi bilgilerini aynı bilgisayarın tüm kullanıcıları için geçerlidir. Web siteleri aynı güvenlik düzeyine sahip bir güvenlik bölgesi grubudur. Bu ilkeyi etkinleştirmek, bir güvenlik bölgesi için kullanıcının yaptığı değişiklikleri o bilgisayardaki tüm kullanıcılara uygulanır. Bu ilkeyi devre dışı bırakır veya yapılandırmazsanız, aynı bilgisayardaki kullanıcılar kendi güvenlik bölgesi ayarlarından kurabilirsiniz. Güvenlik bölgesi ayarlarından aynı bilgisayara aynı şekilde geçerlidir ve kullanıcı başka bir kullanıcı değişiklik yoksa emin olmak için bu ilkeyi kullanın. Ayrıca bkz: "güvenlik bölgeleri: ilkeleri değiştirmek kullanıcılara izin verme" ilkesi.
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer'ın yerel makine bölge java izinleri kilitli**  
  Bu ilke ayarı, Java uygulamaları için izinleri yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz, Seçenekler açılır kutusundan seçebilirsiniz. Özel denetim izinlerini ayarlar için ayrı ayrı. Düşük güvenilirlik, uygulamaların tüm işlemleri sağlar. Orta düzey güvenilirlik (bir alanda bellek görüşmesi yapamaz program dışında), kendi sanal uygulamaların artı boş alan (istemci bilgisayarda bir güvenli depolama alanı) ve kullanıcı tarafından denetlenen dosya g/ç gibi özellikler sağlar. Yüksek güvenilirlik, korumalı alanında çalışmasını sağlar. Java uygulamaları çalışmasını önlemek için devre dışı bırakın. Bu ilke ayarını devre dışı bırakırsanız, Java uygulamalarını çalıştıramazsınız. Bu ilke ayarı yapılandırmazsanız, Java uygulamalarını devre dışı bırakıldı
  
  **Varsayılan**: Java devre dışı bırak 
  
- **Internet Explorer kısıtlı bölge kötü amaçlı yazılımdan koruma karşı ActiveX denetimlerini çalıştırmaz**  </br>
  Bu ilke ayarı, Internet Explorer karşı sayfalarında güvenli iseler denetlemek için ActiveX denetimleri, kötü amaçlı yazılımdan koruma programları çalışıp çalışmayacağını belirler. Bu ilke ayarını etkinleştirirseniz, Internet Explorer ActiveX denetiminin bir örneğini oluşturmak güvenli olup olmadığını görmek için kötü amaçlı yazılımdan koruma programınızı denetleyin olmaz. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer ActiveX denetiminin bir örneğini oluşturmak güvenli olup olmadığını görmek için kötü amaçlı yazılımdan koruma programı her zaman denetler. Bu ilke ayarı yapılandırmazsanız, Internet Explorer ActiveX denetiminin bir örneğini oluşturmak güvenli olup olmadığını görmek için kötü amaçlı yazılımdan koruma programı her zaman denetler. Kullanıcılar bu davranışı açıp kapatabilir, Internet Explorer güvenlik ayarlarını kullanarak kapatabilirsiniz.
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer kısıtlı bölge Authenticode ile imzalanmış .NET Framework bağımlı bileşenleri Çalıştır**  
  Bu ilke ayarı, Authenticode ile imzalanmış .NET Framework bileşenlerini Internet Explorer'dan çalışıp çalışmayacağını yönetmenizi sağlar. Bu bileşenler, bir nesne etiketi ve bir bağlantıdan başvurulan Yönetilen yürütülebilir dosyaları başvurulan yönetilen denetimleri içerir. Bu ilke ayarını etkinleştirirseniz, Internet Explorer imzalı yönetilen bileşenleri çalıştırır. Açılan kutusunda seçtiğiniz istemi, Internet Explorer imzalı yönetilen bileşenleri çalıştırılıp çalıştırılmayacağını için girmesini ister. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer imzalı yönetilen bileşenleri yürütme olmaz. Bu ilke ayarı yapılandırmazsanız, Internet Explorer imzalı yönetilen bileşenleri yürütme olmaz.
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer veri kaynaklarına kısıtlı bölge erişim**  
  Bu ilke ayarı, Internet Explorer Microsoft XML Parser (MSXML) ya da ActiveX Data Objects (ADO) kullanan başka bir güvenlik bölgesi'nden veri erişip erişemeyeceğini yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz, kullanıcılar bir bölge içinde başka bir siteden verilere erişmek için MSXML veya ADO kullanan bölge sayfasında yükleyebilir. Açılan kutusunda seçtiğiniz istemi, kullanıcıların sayfayı MSXML veya ADO bölgede başka bir siteden verilere erişmek için kullandığı bölgesinde yüklemek için izin verip vermeyeceklerini sorgulanır. Bu ilke ayarını devre dışı bırakırsanız, kullanıcıların bir bölge içinde başka bir siteden verilere erişmek için MSXML veya ADO kullanan bölge sayfasında yüklenemiyor. Bu ilke ayarı yapılandırmazsanız, kullanıcıların bir bölge içinde başka bir siteden verilere erişmek için MSXML veya ADO kullanan bölge sayfasında yüklenemiyor.
  
  **Varsayılan**: Devre Dışı Bırak 
  
- **Internet Explorer internet bölgesi, kötü amaçlı yazılımdan koruma ActiveX denetimlerini karşı çalışmaz**  </br>
  Bu ilke ayarı, Internet Explorer karşı sayfalarında güvenli iseler denetlemek için ActiveX denetimleri, kötü amaçlı yazılımdan koruma programları çalışıp çalışmayacağını belirler. Bu ilke ayarını etkinleştirirseniz, Internet Explorer ActiveX denetiminin bir örneğini oluşturmak güvenli olup olmadığını görmek için kötü amaçlı yazılımdan koruma programınızı denetleyin olmaz. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer ActiveX denetiminin bir örneğini oluşturmak güvenli olup olmadığını görmek için kötü amaçlı yazılımdan koruma programı her zaman denetler. Bu ilke ayarı yapılandırmazsanız, Internet Explorer ActiveX denetiminin bir örneğini oluşturmak güvenli olup olmadığını görmek için kötü amaçlı yazılımdan koruma programı her zaman denetler. Kullanıcılar bu davranışı açıp kapatabilir, Internet Explorer güvenlik ayarlarını kullanarak kapatabilirsiniz.
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer internet bölgesi Kopyala ve Yapıştır komut dosyası aracılığıyla** </br> Bu ilke ayarı, belirli bir bölgede (örneğin, kesme, kopyalama ve yapıştırma) Pano işlemi betikleri gerçekleştirip gerçekleştiremeyeceğini yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz, komut dosyası bir pano işlemini gerçekleştirebilirsiniz. Açılan kutusunda seçtiğiniz istemi, kullanıcılar mı kullanılacağına yönelik pano işlemlerini gerçekleştirmek sorgulanır. Bu ilke ayarını devre dışı bırakırsanız, bir komut dosyası bir Pano işlemi gerçekleştirilemiyor. Bu ilke ayarı yapılandırmazsanız, bir komut dosyası bir pano işlemini gerçekleştirebilirsiniz.
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **ActiveX Yükleyici Hizmeti Internet Explorer kullan**  </br>
  Bu ilke ayarı ActiveX denetimleri nasıl yüklendiğini belirtmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz, ActiveX Yükleyici Hizmeti varsa ve ActiveX denetimleri yüklenmesine izin verecek şekilde yapılandırılmış ActiveX denetimleri yüklendi. Devre dışı bırakın veya bu ilke ayarı yapılandırmayın, ActiveX denetimleri, kullanıcı başına denetimlerini dahil olmak üzere standart yükleme süreci boyunca yüklenir.
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer bölge yüksekliğinden koruma işlemleri**  
  Internet Explorer her Web sayfası üzerinde kısıtlamalar getirir. Kısıtlamalar (Internet, Intranet, yerel makine bölgesi ve benzeri) Web sayfasının konumuna bağlıdır. Örneğin, Web sayfalarını yerel bilgisayarda en az bir güvenlik kısıtlamalarına sahiptir ve Yerel Makine bölgesini birinci hedef kötü niyetli kullanıcılar için yerel makine güvenliğin bölgesindedir. Bu ilke ayarını etkinleştirirseniz, tüm işlemler için bölge yüksekliğinden herhangi bir bölge korunabilir. Internet Explorer veya işlem listesinde listelenenler dışındaki işlemleri devre dışı bırakın veya bu ilke ayarı yapılandırmayın, bu tür bir koruma alırsınız.
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer internet bölgesi İmzalanmamış ActiveX denetimlerini indirin**  </br>
  Bu ilke ayarı, kullanıcıların İmzasız ActiveX denetimlerini bölgesinden yükleyip yükleyemeyeceklerini yönetmenize olanak sağlar. Bu tür kod, özellikle güvenilmeyen bir bölgeden Bekletmeden çıkarken zararlı olabilir. Bu ilke ayarını etkinleştirirseniz, kullanıcıların kullanıcı müdahalesi olmadan imzasız denetimlerini çalıştırabilirsiniz. Açılan kutuda istemi seçerseniz, kullanıcıların imzasız denetiminin çalışmasına izin verip vermeyeceklerini sorgulanır. Bu ilke ayarını devre dışı bırakırsanız, kullanıcıların imzasız denetimleri çalıştıramaz. Bu ilke ayarı yapılandırmazsanız, kullanıcıların imzasız denetimleri çalıştıramaz.
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer internet bölgesi, farklı etki alanlarında windows ve çerçeveleri gidin**  </br>
  Bu ilke ayarı, windows ve çerçeveler açma ve erişim uygulamaların farklı etki alanlarında yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, kullanıcılar windows ve çerçeveleri diğer etki alanları ve diğer etki alanlarından erişim uygulamalara açabilirsiniz. Kullanıcılar açılan kutusunda seçtiğiniz istemi, windows ve çerçeveleri başka etki alanlarından uygulamalara erişmesine izin verilip verilmeyeceğini sorgulanır. Bu ilke ayarını devre dışı bırakırsanız, kullanıcılar, windows ve çerçeveleri, farklı etki alanlarından uygulamalara erişmek için açılamıyor. Bu ilke ayarı yapılandırmazsanız, kullanıcıların windows ve çerçeveleri diğer etki alanları ve diğer etki alanlarından erişim uygulamalara açabilirsiniz.
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer internet bölgesi durum çubuğu komut dosyası aracılığıyla güncelleştirmeleri**  
  Bu ilke ayarı, bir komut dosyası bölge içindeki durum çubuğu güncelleştirebilirsiniz yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, durum çubuğu komut dosyalarını güncelleştirebilirsiniz. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, betik durum çubuğu güncelleştirmeye izin verilmiyor.
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer kısıtlı bölge dahil yerel yolu sunucu için dosyalar karşıya yüklenirken**  </br> Bu ilke ayarı, kullanıcı, bir HTML formu aracılığıyla bir dosya karşıya yüklenirken yerel yol bilgileri gönderildiğinde denetler. Yerel yol bilgisi gönderilir, bazı bilgiler sunucuya yanlışlıkla açığa. Örneğin, kullanıcının Masaüstü'nden gönderilen dosya yolun bir parçası olarak kullanıcı adını içerebilir. Bu ilke ayarını etkinleştirirseniz, kullanıcı, bir HTML formu aracılığıyla bir dosya karşıya yüklenirken yol bilgisi gönderilir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcı, bir HTML formu aracılığıyla bir dosya karşıya yüklenirken yol bilgisi kaldırıldı. Bu ilke ayarı yapılandırmazsanız, kullanıcıya bir HTML formu aracılığıyla bir dosya yüklenirken yol bilgisi gönderilip gönderilmeyeceğini seçebilirsiniz. Varsayılan olarak, yol bilgisi gönderilir.
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer işlemleri kısıtlamak dosya indirme**  </br> Bu ilke ayarı, Web tarayıcı denetimi barındırma uygulamaları otomatik kullanıcı tarafından başlatılan olmayan dosya indirmeleri sorması için etkinleştirir. Bu ilke ayarını etkinleştirirseniz, Web tarayıcı denetimi otomatik olarak kullanıcı tarafından başlatılan tüm işlemler için olmayan dosya indirmeleri sorulmasını engeller. Bu ilke ayarını devre dışı bırakırsanız, Web tarayıcı denetimi otomatik olarak kullanıcı tarafından başlatılan tüm işlemler için olmayan dosya indirmeleri sorulmasını engellemez.
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer'ın kısıtlı bölge izin ActiveX denetimlerini kullanmak için etki alanları yalnızca onaylanmış**  </br>
  Bu ilke ayarı, Web siteleri dışında ActiveX denetimini yüklü Web sitesini çalıştırmak ActiveX denetimlerini izin vermek için kullanıcı istenirse denetler. Bu ilke ayarını etkinleştirirseniz, ActiveX denetimleri, bu bölgedeki sitelerinden çalıştırmadan önce kullanıcıya sorulur. Kullanıcı, denetimlerin geçerli siteden veya tüm sitelerden çalışmasına izin vermeyi seçebilirsiniz. Bu ilke ayarını devre dışı bırakırsanız, kullanıcı başına site ActiveX istemini görmez ve bu bölgedeki tüm sitelerden ActiveX denetimlerini çalıştırabilirsiniz.
  
  **Varsayılan**: Enabled  
  
- **Kısıtlı bölge Internet Explorer'ı başlatın ve ActiveX denetimlerini betik güvenli olarak işaretlenmemiş**  
  Bu ilke ayarı, güvenli olarak işaretlenmemiş ActiveX denetimlerini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, ActiveX denetimleri, güvenilir olmayan verileri veya betikler için nesne güvenliği ayarlamadan parametreler ile yüklenir ve komut dosyalı çalıştırın. Bu ayar, güvenli ve yönetilen bölgeler dışında önerilmez. Bu ayar, başlatılır ve komut dosyası için hem güvenli hem de güvenli denetimler neden olur, betik ActiveX denetimlerini yoksayma seçeneği için güvenli olarak işaretlenmiş. Bu ilke ayarını etkinleştirin ve istemi açılır kutusunda, kullanıcıların denetimi parametrelerle yüklemeye izin verilip verilmeyeceği veya komut dosyası. Bu ilke ayarını devre dışı bırakırsanız, güvenli hale getirilemez ActiveX denetimlerini parametrelerle yüklü değil veya komut dosyası. Bu ilke ayarı yapılandırmazsanız, güvenli hale getirilemez ActiveX denetimlerini parametrelerle yüklü değil veya komut dosyası.
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer kullanıcıları ilkelerini değiştirme**  
    Kullanıcılar güvenlik bölge ayarlarını değiştirmesini engeller. Web siteleri aynı güvenlik düzeyine sahip bir güvenlik bölgesi grubudur. Bu ilkeyi etkinleştirmek, güvenlik düzeyi kaydırıcısını Internet Seçenekleri iletişim kutusundaki Güvenlik sekmesinde ve Özel Düzey düğmesini devre dışı bırakılır. Bu ilkeyi devre dışı bırakır veya yapılandırmazsanız, kullanıcıların güvenlik bölgeleri için ayarları değiştirebilirsiniz. Bu ilke, kullanıcılar yönetici tarafından kurulan güvenlik bölge ayarlarını değiştirmesini engeller. Not: Denetim Masası'ndaki Internet Explorer'dan Güvenlik sekmesine kaldıran (\User Configuration\Administrative Templates\Windows components\ınternet Explorer\Internet Denetim Masası ' bulunur) "güvenlik sayfası devre dışı bırak" ilkesi önceliklidir Bu ilke. Bu ilke etkinleştirilirse, göz ardı edilir. Ayrıca bkz: "güvenlik bölgeleri: Yalnızca makine ayarlarını kullan"ilkesi.
    
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer kısıtlı bölge korumalı modu**  
  Bu ilke ayarı, korumalı modunu açmak sağlar. Korumalı modu, Internet Explorer, Internet Explorer için kayıt defteri ve dosya sistemine yazabilirsiniz konumları azaltarak kötü amaçla kullanılan güvenlik açıklarına karşı korumaya yardımcı olur. Bu ilke ayarını etkinleştirirseniz, korumalı mod etkinleştirilir. Kullanıcı, korumalı modunu devre dışı bırakmak olamaz. Bu ilke ayarını etkinleştirirseniz, korumalı mod kapalıdır. Kullanıcı, korumalı modu kapatamazsınız. Bu ilke ayarı yapılandırmazsanız, açın veya korumalı modunu kapatın.
  
  **Varsayılan**: Etkinleştir  
  
- **Internet Explorer internet bölgesi kullanıcı veri kalıcılığı**  
  Bu ilke ayarı, tarayıcının geçmişinde, Sık Kullanılanlar'da, bir XML deposu veya doğrudan bir Web sayfasında diske kaydedilmiş bilgilerin korunması yönetmenizi sağlar. Bir kullanıcı için kalıcı bir sayfa geri döndüğünde, bu ilke ayarını uygun şekilde yapılandırıldıysa sayfa durumu geri yüklenebilir. Bu ilke ayarını etkinleştirirseniz, kullanıcı tarayıcının geçmişinde, Sık Kullanılanlar'da, bir XML deposu veya doğrudan bir Web sayfasında diske kaydedilmiş bilgi saklayabilir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcı bilgileri tarayıcının geçmişinde, Sık Kullanılanlar'da, bir XML deposu veya doğrudan bir Web sayfasında diske kaydedilmiş korumak olamaz. Bu ilke ayarı yapılandırmazsanız, kullanıcıların tarayıcının geçmişinde, Sık Kullanılanlar'da, bir XML deposu veya doğrudan bir Web sayfasında diske kaydedilmiş bilgi saklayabilir.
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer internet bölgesi web tarayıcı denetimleri betik oluşturma**  
 
  Bu ilke ayarı, bir sayfa komut dosyası aracılığıyla gömülü WebBrowser denetimi denetimi olup olmadığını belirler. Bu ilke ayarını etkinleştirirseniz, WebBrowser denetimi betik erişime izin. Bu ilke ayarını devre dışı bırakırsanız, WebBrowser denetimi betik erişmesine izin verilmiyor. Bu ilke ayarı yapılandırmazsanız, kullanıcı etkinleştirebilir veya betik erişimi WebBrowser denetimi devre dışı bırakın. Varsayılan olarak, yalnızca yerel makine ve Intranet bölgeleri WebBrowser denetimi betik erişime izin.
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer'ın kısıtlı bölge kullanıcı veri kalıcılığı**  
    Bu ilke ayarı, tarayıcının geçmişinde, Sık Kullanılanlar'da, bir XML deposu veya doğrudan bir Web sayfasında diske kaydedilmiş bilgilerin korunması yönetmenizi sağlar. Bir kullanıcı için kalıcı bir sayfa geri döndüğünde, bu ilke ayarını uygun şekilde yapılandırıldıysa sayfa durumu geri yüklenebilir. Bu ilke ayarını etkinleştirirseniz, kullanıcı tarayıcının geçmişinde, Sık Kullanılanlar'da, bir XML deposu veya doğrudan bir Web sayfasında diske kaydedilmiş bilgi saklayabilir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcı bilgileri tarayıcının geçmişinde, Sık Kullanılanlar'da, bir XML deposu veya doğrudan bir Web sayfasında diske kaydedilmiş korumak olamaz. Bu ilke ayarı yapılandırmazsanız, kullanıcıların tarayıcının geçmişinde, Sık Kullanılanlar'da, bir XML deposu veya doğrudan bir Web sayfasında diske kaydedilmiş bilgi koruma olamaz.  
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer'ın intranet bölgesi java izinleri kilitli**  
  Bu ilke ayarı, Java uygulamaları için izinleri yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz, Seçenekler açılır kutusundan seçebilirsiniz. Özel denetim izinlerini ayarlar için ayrı ayrı. Düşük güvenilirlik, uygulamaların tüm işlemleri sağlar. Orta düzey güvenilirlik (bir alanda bellek görüşmesi yapamaz program dışında), kendi sanal uygulamaların artı boş alan (istemci bilgisayarda bir güvenli depolama alanı) ve kullanıcı tarafından denetlenen dosya g/ç gibi özellikler sağlar. Yüksek güvenilirlik, korumalı alanında çalışmasını sağlar. Java uygulamaları çalışmasını önlemek için devre dışı bırakın. Bu ilke ayarını devre dışı bırakırsanız, Java uygulamalarını çalıştıramazsınız. Bu ilke ayarı yapılandırmazsanız, Java uygulamalarını devre dışı bırakıldı.
  
  **Varsayılan**: Java devre dışı bırak  
  
- **Internet Explorer'ın gelişmiş korumalı mod**  
  Geliştirilmiş korumalı mod, Windows 64 bit sürümlerinde 64 bit işlemleri kullanarak kötü amaçlı Web sitelerinin karşı ek koruma sağlar. En az çalıştıran bilgisayarlar için Windows 8, geliştirilmiş korumalı mod da sınırlar Internet Explorer okuyabileceği konumlar kayıt defteri ve dosya sistemi. Bu ilke ayarını etkinleştirirseniz, geliştirilmiş korumalı mod etkinleştirilir. Korumalı modu etkin olan herhangi bir bölgeye geliştirilmiş korumalı mod kullanır. Kullanıcılar, geliştirilmiş korumalı mod devre dışı bırakmak mümkün olmayacaktır. Bu ilke ayarını devre dışı bırakırsanız, geliştirilmiş korumalı mod kapalıdır. Korumalı modu etkin olan herhangi bir bölgeye, Windows Vista için Internet Explorer 7'de sunulan korumalı modu sürümünü kullanır. Bu ilke yapılandırmazsanız, kullanıcıların açın veya Internet Seçenekleri iletişim kutusunun Gelişmiş sekmesinde geliştirilmiş korumalı mod devre dışı açın.
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer smart screen'i uyarıları atla**  
  Bu ilke ayarı, kullanıcı Kimden SmartScreen Filtresi uyarılarını devre dışı bırakabilir olup olmadığını belirler. SmartScreen Filtresi, Internet Explorer kullanıcıların yaygın olarak Internet'ten yüklemeyin yürütülebilir dosyaları hakkında kullanıcıyı uyarır. Bu ilke ayarını etkinleştirirseniz, kullanıcıya SmartScreen Filtresi uyarılarını engelleyin. Kullanıcı devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, SmartScreen Filtresi uyarılarını devre dışı bırakabilir.
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer'ın kısıtlı bölge meta yenileme**  
  Bu ilke ayarı, Web sayfasının yazarı tarayıcılar başka bir Web sayfasına yönlendirmek için Meta Yenile ayarı (Etiket) kullanıyorsa, başka bir Web sayfasına bir kullanıcının tarayıcı yönlendirilebilir yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, başka bir Web sayfasına etkin Meta Yenileme ayarı içeren bir sayfa yükleyen kullanıcının tarayıcısı yönlendirilebilir. Bu ilke ayarını devre dışı bırakırsanız, etkin yenileme Meta ayarı içeren bir sayfa yükleyen kullanıcının tarayıcısı başka bir Web sayfasına yönlendirilemiyor. Bu ilke ayarı yapılandırmazsanız, etkin yenileme Meta ayarı içeren bir sayfa yükleyen kullanıcının tarayıcısı başka bir Web sayfasına yönlendirilemiyor.
  
  **Varsayılan**: Devre dışı  
  
### <a name="local-policies-security-options"></a>Yerel İlkeler Güvenlik Seçenekleri
Daha fazla bilgi için [ilke CSP'si - LocalPoliciesSecurityOptions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions) Windows belgelerinde. 

- **Adlandırılmış kanallara ve paylaşımlarına için anonim erişimi kısıtlama**  
  Etkin olduğunda, bu güvenlik ayarı paylaşımlarını ve ayarlarını kanallara anonim erişimi kısıtlar: (1) olabilir adlandırılmış kanallar (2) anonim olarak erişilebilecek paylaşımlar anonim olarak erişilebilir.
  
  **Varsayılan**: Evet  
  
- **En düşük oturum güvenliği için NTLM SSP tabanlı sunucuları**  
  Bu güvenlik ayarı, bir server istemesine, 128 bit şifreleme ve/veya NTLMv2 oturum güvenliği sağlar. Bu değerler, LAN Manager kimlik doğrulama düzeyi güvenlik ayarı değerine bağlıdır. Seçenekler şunlardır: NTLMv2 oturum güvenliği gerektirir: İleti bütünlüğü anlaşma değilse bağlantı başarısız olur. 128 bit şifreleme gerektir. Güçlü şifreleme (128-bit) değilse anlaşıldığında bağlantı başarısız olur.
  
  **Varsayılan**: NTLM V2 ve 128 bit şifreleme gerektir  
  
- **Ekran koruyucu etkinleşmeden kilit ekranında işlem yapılmadan geçen süre**  
  Windows, bir oturumun etkin olmamasını fark eder ve etkin olmama süresi etkin olmama sınırını aşarsa, ekran koruyucusu çalışarak oturumu kilitler.
  
  **Varsayılan**: 15
  
- **Her zaman imzala istemciye gerektiren** etki alanı üyesi tarafından başlatılan tüm güvenli kanal trafiği imzalanmış veya şifrelenmiş gerekir, bu güvenlik ayarı belirler. Bir bilgisayar bir etki alanına katıldığında, bir bilgisayar hesabı oluşturulur. Sistem yeniden başlatıldığında, bundan sonra bilgisayar hesabı parolasını kendi etki alanı için etki alanı denetleyicisi ile güvenli bir kanal oluşturmak için kullanır. Bu güvenli kanal geçirmek NTLM kimlik doğrulaması, LSA SID/name arama ve daha fazlası gibi işlemleri gerçekleştirmek için kullanılır. Bu ayar etki alanı üyesi tarafından başlatılan tüm güvenli kanal trafiği en düşük güvenlik gereksinimlerini karşılayıp karşılamadığını belirler. Özel etki alanı üyesi tarafından başlatılan tüm güvenli kanal trafiği imzalanmış veya şifrelenmiş gerekir belirler. Bu ilke etkinleştirilirse, imzalama veya şifreleme tüm güvenli kanal trafik anlaşılmadıkça sonra güvenli kanal oluşturulmuş olmaz. Bu ilkeyi devre dışı bırakıldı ve ardından şifreleme ve tüm güvenli kanal trafiğinin etki alanı denetleyicisi ile imzalama işlemi yapılır ve bu durumda imzalama ve şifreleme düzeyini etki alanı denetleyicisinin sürümü ve aşağıdaki iki ayarlarını bağlıdır İlkeler: Etki alanı üyesi: (Uygun olduğunda) güvenli kanal verisini dijital olarak şifrele etki alanı üyesi: Dijital olarak imzala güvenli kanal verisini (uygun olduğunda)
  
  **Varsayılan**: Evet
  
- **Kimlik doğrulama düzeyi**  
  Bu güvenlik ayarı, ağ açmalarında hangi sınama/yanıt kimlik doğrulama protokolü belirler. Bu seçim, istemcileri, oturum güvenliği anlaşması düzeyini ve şu şekilde sunucuları tarafından kabul edilen kimlik doğrulama düzeyi tarafından kullanılan kimlik doğrulama protokolü düzeyini etkiler:  
  - *LM ve NTLM yanıtlar göndermek*: İstemciler, LM ve NTLM kimlik doğrulaması kullanmak ve hiçbir zaman NTLMv2 oturum güvenliği kullanır; etki alanı denetleyicileri, LM, NTLM ve NTLMv2 kimlik doğrulamasını kabul eder. 
  - *LM ve NTLM - NTLMv2 anlaşıldığında Gönder*: İstemciler, LM ve NTLM kimlik doğrulaması kullanmak ve sunucu destekliyorsa NTLMv2 oturum güvenliği kullanır; etki alanı denetleyicileri, LM, NTLM ve NTLMv2 kimlik doğrulamasını kabul eder. 
  - *Yalnızca NTLM yanıtı gönder*: İstemciler, yalnızca NTLM kimlik doğrulaması kullanmak ve sunucu destekliyorsa NTLMv2 oturum güvenliği kullanır; etki alanı denetleyicileri, LM, NTLM ve NTLMv2 kimlik doğrulamasını kabul eder. 
  - *Gönder NTLMv2 yanıtı*: İstemciler, yalnızca NTLMv2 kimlik doğrulamasını ve sunucu destekliyorsa NTLMv2 oturum güvenliği kullanır; etki alanı denetleyicileri, LM, NTLM ve NTLMv2 kimlik doğrulamasını kabul eder. 
  - *Yalnızca NTLMv2 yanıtı gönderin. LM Reddet*: İstemciler, yalnızca NTLMv2 kimlik doğrulamasını ve sunucu destekliyorsa NTLMv2 oturum güvenliği kullanır; etki alanı denetleyicileri, LM reddeder (yalnızca NTLM ve NTLMv2 kimlik doğrulamasını kabul eder). 
  - *Yalnızca NTLMv2 yanıtı gönderin. LM ve NTLM reddeder*: İstemciler, yalnızca NTLMv2 kimlik doğrulamasını ve sunucu destekliyorsa NTLMv2 oturum güvenliği kullanır; etki alanı denetleyicileri, LM ve NTLM (yalnızca NTLMv2 kimlik doğrulamasını kabul) reddeder. 
    
  **Varsayılan**: Yalnızca NTLMv2 yanıtı gönderin. LM ve NTLM Reddet
  
- **İstemcilerin üçüncü taraf SMB sunucularına şifrelenmemiş parolaları göndermesini engelleme**  
  Bu güvenlik ayarı etkinleştirilmişse, sunucu ileti bloğu (SMB) yeniden yönlendiricisinin doğrulama sırasında parola şifrelemesini desteklemeyen Microsoft olmayan SMB sunucularına düz metin parolalar gönderebilirsiniz. Şifrelenmemiş parolalar göndermek için bir güvenlik riski oluşturur.
  
  **Varsayılan**: Evet
  
- **Sunucu İletişimleri dijital olarak her zaman imzalama devre dışı bırak**  
  Bu güvenlik ayarı, SMB istemcisinin SMB paket imzalamasını deneyip denemeyeceğini belirler. Sunucu İleti Bloğu (SMB) protokolünü temel Microsoft dosya ve yazıcı paylaşımı ve birçok ağ gibi diğer işlemler, Windows Uzaktan yönetim sağlar. SMB paket aktarım değiştirme adam-de-adam saldırıları önlemek için SMB paketlerin dijital imza SMB protokolünü destekler. Bu ilke ayarı, SMB istemci bileşeni bir SMB sunucusuna bağlandığında imzalaması deneyip denemeyeceğini belirler. Bu ayar etkinleştirilirse Microsoft ağ istemcisi oturum kurulduğunda imzalaması gerçekleştirmek için sunucu sorar. Sunucuda paket imzalama etkinleştirildiyse, paket imzalama anlaşması yapılır. Bu ilke devre dışı bırakılırsa, SMB istemcisi hiçbir zaman SMB paket imzalamasını.
  
  **Varsayılan**: Evet
  
- **Yönetici yükseltme istemi davranışı**  
  Bu ilke ayarı, Yöneticiler için yükseltme isteminin davranışını denetler. Seçenekler şunlardır: 
    - *İstem olmadan Yükselt*: Yükseltme gerektirmeden onayı veya kimlik bilgileri gerektiren bir işlem gerçekleştirmek ayrıcalıklı hesaplara izin verir. Not: Bu seçenek yalnızca en kısıtlı ortamlarında kullanın. 
    - *Güvenli masaüstünde kimlik bilgileri istemi*: Ayrıcalık yükseltme bir işlem gerektirir, kullanıcının güvenli masaüstünde bir ayrıcalıklı kullanıcı adı ve parola girmeniz istenir. Geçerli kimlik bilgileri kullanıcının girdiği işlemi kullanıcının yüksek kullanılabilir ayrıcalık ile devam eder. 
    - *Güvenli masaüstünde onay istemi*: Bir işlem ayrıcalıkların gerektirdiğinde, kullanıcının güvenli masaüstünde izin ver veya Reddet seçmek için istenir. Kullanıcı izin seçerse, işlemi kullanıcının yüksek kullanılabilir ayrıcalık ile devam eder. 
    - *Kimlik bilgileri istemi*: Bir işlem ayrıcalıkların gerektirdiğinde, kullanıcı bir yönetici kullanıcı adı ve parola girmesi istenir. Geçerli kimlik bilgileri kullanıcının girdiği işlemi ayrıcalık ile devam eder. 
    - *Onay istemi*: Bir işlem ayrıcalıkların gerektirdiğinde, kullanıcıya izin ver veya Reddet seçin istenir. Kullanıcı izin seçerse, işlemi kullanıcının yüksek kullanılabilir ayrıcalık ile devam eder.  
    - *Windows dışı ikililer için onay istemi*: Microsoft'a ait olmayan bir uygulama için bir işlem ayrıcalıkların gerektirdiğinde, kullanıcının güvenli masaüstünde izin ver veya Reddet seçmek için istenir. Kullanıcı izin seçerse, işlemi kullanıcının yüksek kullanılabilir ayrıcalık ile devam eder.   
  
  **Varsayılan**: Güvenli masaüstünde onay iste
  
- **En düşük oturum güvenliği için NTLM SSP tabanlı istemciler**  
  Bu güvenlik ayarı, istemci istemesine, 128 bit şifreleme ve/veya NTLMv2 oturum güvenliği sağlar. Bu değerler, LAN Manager kimlik doğrulama düzeyi güvenlik ayarı değerine bağlıdır. Seçenekler şunlardır:
  - NTLMv2 oturum güvenliği gerektirir: NTLMv2 protokol anlaşma değilse bağlantı başarısız olur. 
  - *128 bit şifreleme gerektir*: Güçlü şifreleme (128-bit) değilse anlaşıldığında bağlantı başarısız olur.
  - *NTLMv2 ve 128 bit şifreleme gerektiren*. 

  **Varsayılan**: NTLM V2 128 şifrelemesi
  
- **Akıllı kart kaldırma davranışı**  
    Bu güvenlik ayarı, akıllı kart oturum açan kullanıcı için akıllı kart okuyucusundan kaldırıldığında ne olacağını belirler. Seçenekler şunlardır:
     - *Herhangi bir eylemi*. 
     - *İş istasyonu kilitleme* -akıllı kart kaldırıldığında alan bırakın, bunları akıllı kartlarını almak ve hala korumalı bir oturum korumasına izin vererek iş istasyonu kilitlenmiş.
     - *Oturum kapatmaya zorla* -akıllı kart kaldırıldığında kullanıcı otomatik olarak kapatılır.
     - *Uzak masaüstü oturumunun bağlantısının kesilip kesilmeyeceğini* -akıllı kart kaldırma işlemi, kullanıcı oturumu kapatmadan oturum keser. Bu, kullanıcının akıllı kart ekleyin ve tekrar oturum açmaya gerek olmadan daha sonra veya başka bir akıllı kart bilgisayara, okuyuculu oturumu Sürdür sağlar. Yerel bir oturum söz konusuysa, bu ilke İş İstasyonunu Kilitle ilkesiyle tam olarak aynı işlevi görür.  <br><br>
    
  **Varsayılan**: İş İstasyonunu Kilitle
  
- **Blok SAM hesaplarının ve paylaşımların anonim listelenmesi**  
  Bu güvenlik ayarı hesaplarının ve paylaşımların anonim listelenmesi SAM izin verilip verilmeyeceğini belirler. Windows, anonim kullanıcıların etki alanı hesapları ve ağ paylaşımlara adları listelendirmek gibi etkinlikleri gerçekleştirmesine olanak tanır. Örneğin, yönetici kullanıcılara karşılıklı güven saklamaz güvenilen bir etki alanında erişim istediğinde bu kullanışlı hale. Anonim numaralandırmasına SAM hesaplarının ve paylaşımların izin vermek istemiyorsanız, ardından bu ilkeyi kümesine *Evet*.
  
  **Varsayılan**: Evet
  
- **Blok boş parolalı uzaktan oturum açma**  
  Bu güvenlik ayarı, parola korumalı olmayan yerel hesapların fiziksel bilgisayar konsolu dışındaki konumlardan oturum açmak için kullanılıp kullanılamayacağını belirler. Etkinleştirilirse, oturum açmak için parola korumalı olmayan yerel hesaplar bilgisayarın Klavyesi kullanmanız gerekir. 

  *Uyarı*: Bilgisayarların fiziksel olarak güvenli bir yerde değil, tüm yerel kullanıcı hesapları için güçlü parola ilkeleri her zaman uygulamalıdır. Aksi takdirde, bilgisayara fiziksel erişimi olan herkes bir parola sahip olmayan bir kullanıcı hesabı kullanarak oturum açabilir. Bu taşınabilir bilgisayarlar için özellikle önemlidir. 

  Bu güvenlik ilkesi Herkes grubuna uygularsanız, hiç kimsenin Uzak Masaüstü Hizmetleri üzerinden oturum açabilir. Bu ayar, etki alanı hesapları kullanıyorsanız oturumları etkilemez. Bu ayar atlamak için uzak etkileşimli oturum açma kullanan uygulamalar için mümkündür.
  
  **Varsayılan**: Evet
  
- **Standart kullanıcı yükseltme istemi davranışı**  
  Bu ilke ayarı, standart kullanıcılar için yükseltme isteminin davranışını denetler. 
  - *Yükseltme isteklerini otomatik olarak Reddet*: Bir işlem ayrıcalıkların gerektirdiğinde, hata iletisi görüntülenir yapılandırılabilir bir erişim reddedildi. Standart kullanıcı Yardım Masası aramalarını azaltır için bu ayarı seçebilir gibi Masaüstü çalıştıran bir kurumsal. 
  - *Güvenli masaüstünde kimlik bilgileri istemi*: Bir işlem ayrıcalıkların gerektirdiğinde, kullanıcının güvenli masaüstünde farklı bir kullanıcı adı ve parola girmeniz istenir. Geçerli kimlik bilgileri kullanıcının girdiği işlemi ayrıcalık ile devam eder. 
  - *Kimlik bilgileri istemi*: Bir işlem ayrıcalıkların gerektirdiğinde, kullanıcı bir yönetici kullanıcı adı ve parola girmesi istenir. Geçerli kimlik bilgileri kullanıcının girdiği işlemi ayrıcalık ile devam eder.  
  
  **Varsayılan**: Yükseltme isteklerini otomatik olarak reddet
  
- **Yönetici Onay Modu'ndaki yöneticiler için gerektirir**  
  Bu ilke ayarı, bilgisayarın tüm kullanıcı hesabı denetimi (UAC) ilke ayarlarını davranışını denetler. Bu ilke ayarı değiştirirseniz, bilgisayarınızı yeniden başlatmanız gerekir. Seçenekler şunlardır:   
  - *Yapılandırılmadı*: Yönetici Onay Modu ve ilgili tüm UAC ilke ayarlarını devre dışı bırakıldı. Not: Bu ilke ayarı devre dışıysa, Güvenlik Merkezi, işletim sistemi güvenliğinin bir bütün düşürüldü bildirir. 
  - *Evet*: Yönetici onay modu etkin. Bu ilke etkinleştirilmiş olması ve ilgili UAC ilke ayarları, yerleşik yönetici hesabı ve Yönetici Onay Modu'nda Çalıştır için Administrators grubunun üyesi olan diğer tüm kullanıcılara izin vermek için uygun şekilde ayarlanmalıdır.  
  
  **Varsayılan**: Evet
  
- **SAM hesaplarının anonim numaralandırmasına engelle**  
  Bu güvenlik ayarı, anonim bağlantılara bilgisayara verilen ek hangi izinleri belirler. Windows, anonim kullanıcıların etki alanı hesapları ve ağ paylaşımlara adları listelendirmek gibi etkinlikleri gerçekleştirmesine olanak tanır. Örneğin, yönetici kullanıcılara karşılıklı güven saklamaz güvenilen bir etki alanında erişim istediğinde bu kullanışlı hale. Bu güvenlik seçeneği ek sınırlamalar anonim bağlantılara gibi yerleştirilmesine olanak sağlar: 
  - *Evet*: Numaralandırma SAM hesaplarının izin vermez. Bu seçenek, herkes kaynaklar için güvenlik izinleri kimliği doğrulanmış kullanıcılar ile değiştirir.
  - *Yapılandırılmadı*: Ek kısıtlama yoktur. Varsayılan izinlerini kullanır.  
  
  **Varsayılan**: Evet
  
- **Güvenlik Hesapları Yöneticisi uzak çağrısına izin ver**  
  Bu ilke ayarı, SAM uzak rpc bağlantılarını kısıtla olanak sağlar. Seçilmezse, varsayılan güvenlik tanımlayıcısı kullanılır.
  
  **Varsayılan**: *O:BAG:BAD:(A;; RC;; BA)*

- **Yönetici onay modu kullanın**  
  Bu ilke ayarı, yerleşik yönetici hesabı için yönetici onay modu davranışını denetler. Seçenekler şunlardır: 
  - *Evet*: Yerleşik yönetici hesabı yönetici onay modu kullanır. Varsayılan olarak kullanıcıdan işlemi ayrıcalık gerektiren herhangi bir işlem ister. 
  - *Yapılandırılmamış*: Yerleşik yönetici hesabı tüm uygulamaları tam yönetici ayrıcalıklarıyla çalıştırır.  

  **Varsayılan**: Evet
  
- **Güvenli konumları için kullanıcı Arabirimi uygulamalara izin ver**  
  Bu ilke, kullanıcı arabirimi erişilebilirliği (UIAccess veya UIA) programları standart bir kullanıcı tarafından kullanılan yükseltme istemleri için güvenli masaüstünü otomatik olarak devre dışı olup olmadığını ayarı denetler. 
  - *Evet*: Windows Uzaktan Yardım dahil olmak üzere, UIA programları yükseltme istemleri için güvenli masaüstünü otomatik olarak devre dışı bırakın. Devre dışı bırakmayın, "kullanıcı hesabı denetimi: Yükseltme isterken güvenli masaüstüne geç"ilke ayarı, istemler güvenli masaüstü yerine etkileşimli kullanıcının masaüstünde görünür. 
  - *Yapılandırılmamış*: Güvenli Masaüstü yalnızca etkileşimli masaüstü kullanıcısı tarafından veya devre dışı bırakılarak devre dışı bırakılabilir "kullanıcı hesabı denetimi: Yükseltme isterken güvenli masaüstüne geç"ilke ayarı.  

  **Varsayılan**: Evet

- **Uygulama yüklemelerini Algıla ve yükseltme isteminde bulun**  
  Bu ilke ayarı, bilgisayarın uygulama yükleme algılama davranışını denetler. Seçenekler şunlardır: 
  - *Etkin*: Ayrıcalık gerektiren bir uygulama yükleme paketi tespit edildiğinde, kullanıcı bir yönetici kullanıcı adı ve parola girmesi istenir. Geçerli kimlik bilgileri kullanıcının girdiği işlemi ayrıcalık ile devam eder. 
  - *Devre dışı*: Uygulama yükleme paketleri değil ve yükseltme istenir. Standart kullanıcı Masaüstü çalıştıran ve kullanmak kuruluşların Grup İlkesi Yazılım Yükleme gibi yükleme teknolojileri temsilci veya Systems Management Server (SMS) Bu ilke ayarını devre dışı bırakmanız gerekir. Bu durumda, yükleyici algılama gerekli değildir.  
  
  **Varsayılan**: Evet
  
- **Sonraki parola değişiminde LAN manager karma değerini depolama engelle**  
  Sonraki parola değişiminde yeni parolanın LAN Manager (LM) karma değeri depolanır, bu güvenlik ayarı belirler. LM karması nispeten zayıf ve saldırıya değiştirmeyen şifreleme açısından güçlü Windows NT karması. LM karması güvenlik veritabanında yerel bilgisayarda depolandığından parolalar, güvenlik veritabanı gerçekleşirse zarar görebilir.
  
  **Varsayılan**: Evet

- **Dosya ve kayıt defteri yazma hatalarını kullanıcı konumlarında başına konumlarında sanal olarak oluştur**  
  Bu ilke, uygulama yazma hatalarının tanımlanan kayıt defteri ve dosya sistemi konumlarına yeniden yönlendirilen olup olmadığını ayarı denetler. Bu ilke ayarı, yönetici olarak çalıştırın ve çalışma zamanı uygulama verileri için yazma uygulamaları azaltır *% ProgramFiles %* , *% Windir %* , *%Windir%\system32*, veya *HKLM\Software*.
  
  **Varsayılan**: Evet

### <a name="ms-security-guide"></a>MS Güvenlik Kılavuzu  

Daha fazla bilgi için [ilke CSP'si - MSSecurityGuide](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mssecurityguide) Windows belgelerinde.  

- **Ağ oturumu açma üzerindeki yerel hesaplar için UAC kısıtlamalarını Uygula**  
  **Varsayılan**: Enabled
  
- **SMB v1 istemci sürücü başlangıç yapılandırması**  
  **Varsayılan**: Devre dışı sürücü
  
- **SMB v1 sunucusu**  
  **Varsayılan**: Devre dışı
  
- **Özet kimlik doğrulaması**  
  **Varsayılan**: Devre dışı
  
- **Yapılandırılmış özel durum işleme üzerine koruma**  
  **Varsayılan**: Enabled
  
### <a name="mss-legacy"></a>MSS eski  

Daha fazla bilgi için [ilke CSP'si - MSSLegacy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-msslegacy) Windows belgelerinde.  

- **Koruma düzeyi yönlendirme ağ IP kaynağı**  
  **Varsayılan**: En yüksek koruma  
  
- **Itanium tabanlı sistemler için NetBIOS adı sürüm istekleri dışında WINS sunucusundan ağ yoksay**  
  **Varsayılan**: Enabled
  
- **IPv6 yönlendirme koruma düzeyi kaynak ağ**  
  **Varsayılan**: En yüksek koruma

- **Ağ ICMP yeniden yönlendirmeleri oluşturulan OSPF geçersiz kıl**  
  **Varsayılan**: Devre dışı
  
### <a name="power"></a>Güç  

Daha fazla bilgi için [ilke CSP'si - Power](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power) Windows belgelerinde.  

- **Takılıyken Uyandırma parola iste**  
  Bu ilke ayarı, sistem uyku durumundan çıktığında kullanıcıyı parola girmeniz istenir, belirtir. Etkinleştirin veya bu ilke ayarı yapılandırmayın, kullanıcı sistem uyku durumundan çıktığında parola istenir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcı sistem uyku durumundan çıktığında parola sorulmadan değil.
  
  **Varsayılan**: Enabled
  
- **Pil sırada Uyuma, bekleme durumlarını**  
  Bu ilke ayarı, Windows bilgisayar uyku durumunda koyma, bekleme durumlarını kullanabiliyorsa yönetir. Etkinleştirin veya bu ilke ayarı yapılandırmayın varsa, Windows bilgisayar uyku durumuna için bekleme durumlarını kullanır. Bu ilke ayarını devre dışı bırakırsanız, bekleme durumlarını (S1 S3) izin verilmez.
  
  **Varsayılan**: Devre dışı
  
- **Takılıyken Uyuma, bekleme durumlarını**  
  Bu ilke ayarı, Windows bilgisayar uyku durumunda koyma, bekleme durumlarını kullanabiliyorsa yönetir. Etkinleştirin veya bu ilke ayarı yapılandırmayın varsa, Windows bilgisayar uyku durumuna için bekleme durumlarını kullanır. Bu ilke ayarını devre dışı bırakırsanız, bekleme durumlarını (S1 S3) izin verilmez.
  
  **Varsayılan**: Devre dışı
  
- **LAN'da Uyandırma pil sırasında parola iste**  
  Bu ilke ayarı, sistem uyku durumundan çıktığında kullanıcıyı parola girmeniz istenir, belirtir. Etkinleştirin veya bu ilke ayarı yapılandırmayın, kullanıcı sistem uyku durumundan çıktığında parola istenir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcı sistem uyku durumundan çıktığında parola sorulmadan değil.
  
  **Varsayılan**: Enabled
  
### <a name="remote-desktop-services"></a>Uzak Masaüstü Hizmetleri  

Daha fazla bilgi için [ilke CSP'si - RemoteDesktopServices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remotedesktopservices) Windows belgelerinde.  

- **Parola kaydetme engelle**  
  Parolaları bu bilgisayarda Uzak Masaüstü Bağlantısı'ndan kaydedilebilir olup olmadığını denetler. Bu ayarı etkinleştirirseniz, parola Uzak Masaüstü Bağlantısı'nda onay kutusu kaydetme devre dışıdır ve kullanıcıların parolaları Kaydet mümkün olmayacaktır. Bir kullanıcı, Uzak Masaüstü bağlantısı kullanarak bir RDP dosyası açılır ve ayarlarına kaydederse, daha önce RDP dosyasındaki var olan herhangi bir parola silinir. Bu ayarı devre dışı veya yapılandırılmamış bırakın, kullanıcı parolaları Uzak Masaüstü bağlantısı kullanarak kaydedebilirsiniz.
  
   **Varsayılan**: Enabled
  
- **RPC iletişimi güvenli hale getirme**  
  Bir Uzak Masaüstü oturumu konağı sunucusu ile tüm istemcilerin güvenli RPC iletişimi gerektirir veya iletişime izin verir belirtir. İstemciler ile RPC iletişimi güvenliğini sağlayarak yalnızca kimliği doğrulanmış ve şifrelenmiş isteklere güçlendirmek için bu ayarı kullanabilirsiniz. Durum Etkin olarak ayarlanırsa, Uzak Masaüstü Hizmetleri güvenli isteklerini desteklemek RPC istemcilerden gelen istekleri kabul eder ve güvenilmeyen istemciler ile iletişime izin vermez. Durumu devre dışı olarak ayarlanmışsa, Uzak Masaüstü Hizmetleri, her zaman tüm RPC trafiği için güvenlik ister. Ancak, iletişime isteğine yanıt yok RPC istemciler için izin verilir. Yapılandırılmamış durumu olarak iletişime izin verilir. Not: RPC arabirimi, yönetme ve Uzak Masaüstü Hizmetleri yapılandırmak için kullanılır.
  
  **Varsayılan**: Enabled
  
- **Blok sürücü yeniden yönlendirme**  
  Bu ilke ayarı, Uzak Masaüstü Hizmetleri oturumu (sürücü yeniden yönlendirme) istemci sürücü eşleme engellenip engellenmeyeceğini belirtir. Varsayılan olarak, RD Oturumu Ana bilgisayarı sunucu bağlantıyla birlikte otomatik olarak istemci sürücüleri eşler. Eşlenen sürücüler görünür biçimde dosya Gezgini veya bilgisayar oturum klasör ağacında  *\<SürücüHarfi >* üzerinde  *\<computername >* . Bu ilke ayarı, bu davranışı geçersiz kılmak için kullanabilirsiniz. Bu ilke ayarını etkinleştirirseniz, istemci sürücüsü yeniden yönlendirmesi, Uzak Masaüstü Hizmetleri oturumlarına izin verilmiyor ve Windows Server 2003, Windows 8 ve Windows XP çalıştıran bilgisayarlarda Pano dosya kopyalama yeniden yönlendirmesine izin verilmiyor. Bu ilke ayarını devre dışı bırakırsanız istemci sürücüsü yeniden yönlendirmesi her zaman izin verilir. Ayrıca, Pano yeniden yönlendirmesine izin verilip verilmediğini Pano dosya kopyalama yönlendirmesini her zaman izin verilir. Bu ilke ayarı yapılandırmazsanız istemci sürücüsü yeniden yönlendirmesi ve Pano dosya kopyalama yeniden yönlendirme Grup İlkesi düzeyinde belirtilmeyen.
  
  **Varsayılan**: Enabled
  
- **Bağlantı kurulduğunda parola istemi**  
  Bu ilke ayarı, Uzak Masaüstü Hizmetleri istemci bağlantı kurulduğunda parola her zaman uyarıp uyarmayacağını belirtir. Uzak Masaüstü Bağlantısı istemci Parolada zaten sağlanan bile Uzak Masaüstü Hizmetleri oturum açan kullanıcılar için bir parola istemi zorlamak için bu ayarı kullanabilirsiniz. Varsayılan olarak, Uzak Masaüstü Hizmetleri Uzak Masaüstü Bağlantısı istemcisinde bir parola girerek otomatik olarak oturum açmasını sağlar. Bu ilke ayarını etkinleştirirseniz, kullanıcılar otomatik olarak Uzak Masaüstü Hizmetleri için Uzak Masaüstü Bağlantısı istemcisinde parolalarını sağlayarak oturum açamaz. oturum açmak parola istenir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcıların her zaman için Uzak Masaüstü Hizmetleri otomatik olarak Uzak Masaüstü Bağlantısı istemcisinde parolalarını sağlayarak oturum açabilir. Bu ilke ayarı yapılandırmazsanız, otomatik oturum açma Grup İlkesi düzeyinde belirtilmemiş. 
  
  **Varsayılan**: Enabled
  
- **Uzak Masaüstü Hizmetleri istemci bağlantı şifreleme düzeyi**  
  Uzak Masaüstü Protokolü (RDP) bağlantıları sırasında RD Oturumu Ana bilgisayarı sunucuları ile istemci bilgisayar arasındaki iletişimin güvenliğini sağlamak için özel bir şifreleme düzeyi kullanımını gerekip gerekmediğini belirtir. Bu ilke, yalnızca yerel RDP şifreleme kullanılırken geçerlidir. Ancak, yerel RDP şifreleme (aksine, SSL şifrelemesi) önerilmez. Bu ilke, SSL şifrelemesi için geçerli değildir. Bu ilke ayarını etkinleştirirseniz, istemcilerin ve RD Oturumu Ana bilgisayarı sunucuları arasındaki tüm iletişimler sırasında uzak bağlantıları bu ayarında belirtilen şifreleme yöntemini kullanmanız gerekir. Varsayılan olarak, şifreleme düzeyini Yüksek olarak ayarlanır. Aşağıdaki şifreleme yöntemleri kullanılabilir:  
  - *Yüksek*: Yüksek ayarı, güçlü 128 bit şifreleme kullanarak istemciden sunucuya ve sunucudan istemciye gönderilen verileri şifreler. Bu şifreleme düzeyi yalnızca 128-bit istemcileri (örneğin, Uzak Masaüstü Bağlantısı'nı çalıştıran istemciler) içeren ortamlarda kullanın. Bu şifreleme düzeyi desteklemeyen istemciler, RD Oturumu Ana Bilgisayarı sunucularına bağlanamazlar.  
  - *İstemci uyumlu*: Uyumlu istemci ayarı istemci tarafından desteklenen en yüksek anahtar gücünde sunucusu ile istemci arasında gönderilen verileri şifreler. Bu şifreleme düzeyi 128 bit şifreleme desteklemeyen istemciler içeren ortamlarda kullanın.  
  - *Düşük*: Düşük ayarı yalnızca 56 bit şifreleme kullanarak istemciden sunucuya gönderilen verileri şifreler.  
  
  Devre dışı bırakın ya da bu ayarı yapılandırmayın, RD Oturumu Ana bilgisayarı sunucularını uzaktan bağlantılar için kullanılacak şifreleme düzeyini Grup İlkesi aracılığıyla zorlanmaz. FIPS uyumluluğunu önemli sistem şifreleme yapılandırılabilir. Şifreleme, karma ve (Bilgisayar Yapılandırması\Windows Ayarları\Güvenlik Ayarları\Yerel İlkeler\Güvenlik Seçenekleri altında.) Grup İlkesi ayarlarına imzalama için FIPS uyumlu algoritmalar kullanın FIPS uyumlu ayarı şifreler ve Microsoft şifreleme modüllerini kullanarak istemciden sunucuya ve Federal Bilgi İşleme Standardı (FIPS) 140 şifreleme algoritmaları, istemciden sunucuya gönderilen verilerin şifresini çözer. RD Oturumu Ana bilgisayarı sunucuları ile istemci arasındaki iletişimin şifreleme en yüksek düzeyde gerektirdiğinde bu şifreleme düzeyi kullanın.
  
  **Varsayılan**: Yüksek
  
### <a name="remote-management"></a>Uzaktan Yönetim  

Daha fazla bilgi için [ilke CSP'si - RemoteManagement](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remotemanagement) Windows belgelerinde.  

- **Blok depolama kimlik bilgileri olarak çalıştırma**  
  İstemci temel kimlik doğrulaması
  
  **Varsayılan**: Enabled
  
- **Temel kimlik doğrulaması**  
  Bu ilke ayarı, Windows Uzaktan Yönetim (WinRM) hizmeti uzak bir istemciden Temel kimlik doğrulaması kabul edip etmeyeceğini yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz, WinRM hizmeti uzak bir istemciden Temel kimlik doğrulaması kabul eder. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, WinRM hizmeti uzak bir istemciden Temel kimlik doğrulaması kabul etmez.
  
  **Varsayılan**: Devre dışı
  
- **Blok istemci Özet kimlik doğrulaması**  
  Bu ilke ayarı Windows Uzaktan Yönetim (WinRM) istemcisi Özet kimlik doğrulaması kullanır yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, WinRM istemci Özet kimlik doğrulaması kullanmaz. WinRM istemcisini devre dışı bırakın veya bu ilke ayarı yapılandırmayın, Özet kimlik doğrulaması kullanır.
  
  **Varsayılan**: Enabled
  
- **Şifrelenmemiş trafiği**  
  Bu ilke ayarı, Windows Uzaktan Yönetim (WinRM) hizmeti ağ üzerinden şifrelenmemiş iletileri alan ve gönderen yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, WinRM istemci gönderir ve ağ üzerinden şifrelenmemiş iletileri alır. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, WinRM istemci gönderir veya ağ üzerinden yalnızca şifrelenmiş iletileri alır.  
  
  **Varsayılan**: Devre dışı
  
- **Şifrelenmemiş istemci trafiğini**  
  Bu ilke ayarı Windows Remote Management (WinRM) istemcisi ağ üzerinden şifrelenmemiş iletileri alan ve gönderen yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, WinRM istemci gönderir ve ağ üzerinden şifrelenmemiş iletileri alır. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, WinRM istemci gönderir veya ağ üzerinden yalnızca şifrelenmiş iletileri alır.
  
  **Varsayılan**: Devre dışı
  
- **İstemci temel kimlik doğrulaması**  
  Bu ilke ayarı Windows Uzaktan Yönetim (WinRM) istemcisi temel kimlik doğrulaması kullanır yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, WinRM istemci temel kimlik doğrulaması kullanır. WinRM HTTP aktarımı kullanmak için yapılandırılmışsa, kullanıcı adı ve parola ağda düz metin gönderilir. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, WinRM istemci temel kimlik doğrulaması kullanmaz.
  
  **Varsayılan**: Devre dışı
  

### <a name="remote-procedure-call"></a>Uzak yordam çağrısı  

Daha fazla bilgi için [ilke CSP'si - RemoteProcedureCall](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remoteprocedurecall) Windows belgelerinde.  

- **Kimliği doğrulanmamış RPC istemci seçenekleri**  
  Bu ilke ayarı, RPC sunucusu çalıştırma zamanı RPC sunuculara bağlanma kimliği doğrulanmamış RPC istemcilerinin nasıl işlediğini denetler. Bu ilke ayarı, tüm RPC uygulamaları etkiler. Grup İlkesi kendisini işleme dahil işlevleri çeşitli etkileyebileceğinden bir etki alanı ortamında, bu ilke ayarı dikkatli kullanın. Bu ilke ayarı için bir değişikliği geri alma, her bir sorundan etkilenen makinede el ile müdahale gerektirebilir. Bu ilke ayarı, hiçbir zaman bir etki alanı denetleyicisine uygulanmalıdır. Bu ilke ayarını devre dışı bırakırsanız, RPC sunucusu çalıştırma zamanı Windows istemcisi ve Windows Server sürümlerinde bu ilke ayarı destek "None" değerini "Kimliği doğrulanmış" değerini kullanır. Bu ilke ayarı yapılandırmazsanız, devre dışı kalır. RPC sunucusu çalışma zamanı, "Windows istemci ve"None"Bu ilke ayarı destek Server SKU için kullanılan değeri için kullanılan kimlik doğrulaması yapılmış" değeriyle etkinleştirildi ancak gibi davranır. Bu ilke ayarını etkinleştirirseniz, bir makine üzerinde çalışan sunucularına bağlanan kimliği doğrulanmamış RPC istemcilere kısıtlamak için RPC sunucusu çalıştırma zamanı yönlendirir. Bir istemci kimliği doğrulanmış bir istemci sunucusuyla iletişim kurmak için bir adlandırılmış kanal kullanıyorsa veya RPC güvenlik kullanıyorsa olarak kabul edilir. Özellikle kimliği doğrulanmamış istemcileri tarafından erişilebilir olmasını istediğiniz RPC arabirimlerinin Bu ilke ayarı için seçili değerine bağlı olarak bu kısıtlama, muaf olabilir.  
  - *Hiçbiri* tüm RPC istemcilerinin ilke ayarının uygulandığı makine üzerinde çalışan sunucularına bağlanmasını sağlar. 
  - *Kimliği doğrulanmış* ilke ayarının uygulandığı makine üzerinde çalışan RPC sunucularına bağlanmak için yalnızca kimliği doğrulanmış RPC istemcilerinin (yukarıdaki tanımı) sağlar. Muafiyetleri bunları istenen arabirimleri verilir. 
  - *Özel durumlar kimliği doğrulanmış* ilke ayarının uygulandığı makine üzerinde çalışan RPC sunucularına bağlanmak için yalnızca kimliği doğrulanmış RPC istemcilerinin (yukarıdaki tanımı) sağlar. Hiçbir özel durumlara izin verilmez. Not: Bu ilke ayarı, sistem yeniden başlatılana kadar uygulanmaz.  

  **Varsayılan**: Kimlik doğrulaması

### <a name="search"></a>Ara  

Daha fazla bilgi için [ilke CSP'si - arama](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-search) Windows belgelerinde.  

- **Şifrelenmiş öğeler için dizin oluşturmayı devre dışı**  
  Öğeler için dizin oluşturulmasına izin verir veya engeller. Bu anahtar, bu, Windows bilgi Koruması (WIP) korumalı dosyalar gibi şifreli öğelerin dizininin oluşturulmasını denetleyen Windows Search dizin'Oluşturucu içindir. İlke etkinleştirildiğinde, WIP korumalı öğelerin dizini oluşturulur ve bunlar hakkındaki meta veriler şifrelenmemiş bir konumda depolanır. Meta veriler, dosya yolu ve değiştirilme tarihi gibi veriler içerir. İlkeyi devre dışı bırakıldığında, WIP korumalı öğelerin dizini olmayan ve Cortana veya dosya Gezgini sonuçlarında içinde gösterme. Cihazda çok sayıda WIP korumalı medya dosyası varsa fotoğraflar ve Groove uygulamaları performansını da etkileyebilir.
  
**Varsayılan**: Evet
  
### <a name="smart-screen"></a>Akıllı Ekran  

Daha fazla bilgi için [ilke CSP'si - SmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-smartscreen) Windows belgelerinde.  

- **Doğrulanmamış dosyaları yürütülmesini engeller**  
  Kullanıcının doğrulanmamış dosyalarının çalıştırmasını engelleyin. 
  - *Yapılandırılmamış* -çalışanlar SmartScreen uyarılarını yoksayarak kötü amaçlı dosyalardan çalıştırın. 
  - *Evet* – çalışanlar SmartScreen uyarılarını gözardı et ve kötü amaçlı dosyalardan çalıştırın.

  **Varsayılan**: Evet

<!-- Not currently available? - **Block unverified file download**  
  By default, Microsoft Edge allows users to bypass (ignore) the Windows Defender SmartScreen warnings about potentially malicious files, allowing them to continue downloading the unverified file(s). Enabling this policy prevents users from bypassing the warnings, blocking them from downloading of the unverified file(s).
  
  **Default**: Yes
 --> 
- **Uygulamalar ve dosyalar için SmartScreen gerektirir**  
  BT yöneticilerinin için SmartScreen Windows yapılandırmasına olanak tanır.

  **Varsayılan**: Evet
  
### <a name="system"></a>Sistem  

Daha fazla bilgi için [ilke CSP'si - sistem](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system) Windows belgelerinde.  

- **Sistem önyükleme başlangıç sürücü başlatma**  
  Bu ilke ayarı erken başlatma kötü amaçlı yazılımdan koruma önyükleme başlatma sürücü tarafından belirlenen bir sınıflandırma göre hangi önyükleme başlatma sürücüler başlatılmadan belirtmenize olanak sağlar. Erken Başlatma kötü amaçlı yazılımdan koruma önyükleme başlatma sürücü, aşağıdaki sınıflandırmaları için her önyükleme başlatma sürücü döndürebilirsiniz: 
  - *İyi*: İmzalanmış ve kurcalanmadığı.  
  - *Hatalı* -sürücü kötü amaçlı yazılım olarak belirlenmiştir. Başlatılacak bilinen hatalı sürücüler izin verme öneririz. 
  - *Hatalı, ancak önyükleme için gerekli*: Sürücü kötü amaçlı yazılım olarak belirlenmiştir, ancak bilgisayar bu sürücü yüklemeden başarıyla önyükleme yapamazsınız. 
  - *Bilinmeyen* -Bu sürücü için kötü amaçlı yazılım algılama uygulamanız tarafından tarafından kanıtlanan taşınmadığından ve önyükleme başlatma erken başlatma kötü amaçlı yazılımdan koruma sürücüsü tarafından sınıflandırılan edilmemiş.  

  Bu ilke ayarını etkinleştirirseniz, bilgisayarın bir sonraki başlatılışında başlatmak için hangi önyükleme başlatma sürücüleri seçebilirsiniz. Devre dışı bırakır veya bu ilkeyi yapılandırmayın ayarlamak, belirlenen önyükleme başlatma sürücülerini iyi, bilinmeyen veya hatalı önyükleme kritik ancak başlatılır ve başlatılması hatalı belirlenen sürücü atlandı. Kötü amaçlı yazılım algılama uygulamanızı bir erken başlatma kötü amaçlı yazılımdan koruma önyükleme başlatma sürücü içermiyorsa veya erken başlatma kötü amaçlı yazılımdan koruma önyükleme başlatma sürücünüzü devre dışı bırakılırsa, bu ayarın hiçbir etkisi ve tüm önyükleme başlatma sürücüleri başlatılır.  
  
  **Varsayılan**: İyi bilinmeyen ve kritik bozuk


### <a name="wi-fi"></a>Wi-Fi  

Daha fazla bilgi için [ilke CSP'si - Wi-Fi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi) Windows belgelerinde.  

- **Internet paylaşmayı engelle**  
  İnternet paylaşımı cihazda mümkün olup olmadığını belirtir.  

  **Varsayılan**: Evet  

- **Blok Wi-Fi etkin noktalarına bağlanmasını otomatik olarak**  
  İzin vermek veya cihaz için Wi-Fi etkin noktalarına otomatik olarak bağlanmasına izin vermeyin.  

  **Varsayılan**: Evet  
  
### <a name="windows-connection-manager"></a>Windows Bağlantı Yöneticisi  

Daha fazla bilgi için [ilke CSP'si - WindowsConnectionManager](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsconnectionmanager) Windows belgelerinde.  

- **Etki alanı olmayan ağlara bağlantıyı engelle**  
  Bu ilke ayarı için bir etki alanı tabanlı ağ ve bir temel etki alanı olmayan bağlanmasını bilgisayarlar engeller. aynı zamanda ağ. Bu ilke ayarı etkinse, bilgisayar üzerinde aşağıdaki koşullara göre otomatik ve el ile ağ bağlantısı denemeleri yanıt verir: 
  - Bilgisayarın etki alanı olmayan ağlara tüm otomatik bağlantı girişimlerinde bir etki alanı tabanlı ağ zaten bağlı olduğunda otomatik bağlantı girişimleri engellenir. Bilgisayar bir etki alanı dışı tabanlı ağa bağlandığında, etki alanı tabanlı ağlara otomatik bağlantı girişimleri engellenir. 
  - Ortamı dışındaki Ethernet üzerinden veya etki alanı tabanlı bir ağdaki bilgisayar ya da bir etki alanı olmayan için zaten bağlı olduğunda el ile yapılan bağlantı girişimleri tabanlı ve kullanıcının bu ilkeyi ihlal el ile ek bir ağa bağlantı oluşturmaya çalışır ayarlama, var olan ağ bağlantısını keser ve el ile bağlantıya izin verilir. Bilgisayar zaten bağlı olduğunda ya da Ethernet üzerinden veya etki alanı tabanlı bir ağdaki bir etki alanı dışı tabanlı ve bir kullanıcı bu ilke ayarı ihlal el ile ek bir ağa bağlantı oluşturmaya çalışır, mevcut Ethernet bağlantısı tutulur ve el ile bağlantı denemesi engellendi.  

  Bu ilke ayarı yapılandırılmadı veya devre dışı bırakıldı, bilgisayarları aynı anda hem etki alanı ve etki alanı olmayan ağlara bağlanmasına izin verilir.  

  **Varsayılan**: Enabled
  
### <a name="windows-defender"></a>Windows Defender  

Daha fazla bilgi için [ilke CSP'si - Defender'ın](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender) Windows belgelerinde.  

- **Gelen posta iletilerini tarama**  
  Erişim izni verdiği veya e-posta taramasına izin vermiyor.
  
  **Varsayılan**: Evet  

- **Office uygulamalarının alt işlem türü başlatın**  
  Office uygulamalarının alt işlemler oluşturmak izin verilmez. Bu, Word, Excel, PowerPoint, OneNote ve erişim içerir. Özellikle başlatın veya kötü amaçlı bir yürütülebilir dosyaları indirmek için Office uygulamalarını kullanma girişimi makrosu tabanlı saldırılar için tipik bir kötü amaçlı yazılım yer alan bir davranış budur.
  
  **Varsayılan**: Engelle
  
- **Defender'ın örnek gönderimi onay türü**  
  Kullanıcı denetimleri, veri göndermek için Windows Defender'ı düzeyinde vermiş olursunuz. Gerekli onay verilmiş, Windows Defender'ın bunları gönderir. Aksi halde (ve kullanıcı tarafından hiç sormak için belirtilen değilse), verileri göndermeden önce (Defender/AllowCloudProtection izin verildiğinde) kullanıcı onay için sormak için kullanıcı Arabirimi başlatılır.
  
  **Varsayılan**: Güvenli örnekleri otomatik olarak gönder 
  
- **İmza güncelleştirme aralığı (saat)**  
  Defender imza güncelleştirme aralığı saat
  
  **Varsayılan**: 4
  
- **Betiği yük yürütme türü indirildi**  
  Defender betiği yük yürütme türü indirildi
  
  **Varsayılan**: Engelle
  
- **Kimlik bilgisi türü çalmaya engelle**  
  Windows Defender Credential Guard, parolaları yalnızca ayrıcalıklı sistem yazılımlarının erişebileceği böylece yalıtmak için sanallaştırma tabanlı güvenlik kullanır. Bu parolalara yetkisiz erişim, Pass-the-Hash veya Pass-The-Ticket gibi kimlik bilgisi hırsızlığı saldırılarına yol açabilir. Windows Defender Credential Guard, NTLM parola karmalarını, Kerberos anahtar verme anahtarı ve etki alanı kimlik bilgileri uygulamalar tarafından depolanan kimlik bilgilerini koruyarak bu saldırıları engeller.
  
  **Varsayılan**: Etkinleştir

- **E-posta içeriği yürütme türü**  
  Bu kural, çalıştırmak veya Microsoft Outlook veya Web postası (örneğin, Gmail.com veya Outlook.com) görünen bir e-postasındaki başlatılan engeller aşağıdaki dosya türlerinde engeller: Yürütülebilir (.exe, .dll veya .scr) komut dosyaları (örneğin, bir PowerShell .ps, VisualBasic .vbs veya .js dosyası JavaScript) dosyaları komut arşiv dosyaları.
  
  **Varsayılan**: Engelle
  
- **Ağ koruması türü**  
  Bu ilke, ağ Koruması (Denetim/engelleme) açma veya kapatma sağlar, Windows Defender Exploit Guard. Ağ koruması, Windows Defender Exploit erişirken kimlik avı kuşku verici, siteleri yararlanma barındırma ve kötü amaçlı içerik herhangi bir uygulamadan Internet'te kullanan çalışanların koruyan koruma özelliğidir. Bu, üçüncü taraf tarayıcılar tehlikeli sitelere bağlanmasına engel içerir. Değer, bir tamsayı türüdür. Bu ayarı etkinleştirirseniz, ağ koruması açıktır ve çalışanlar, devre dışı bırakamazlar. Davranışını aşağıdaki seçeneklere göre denetlenebilir: Blok ve denetim. Bu ilke "Engelle" seçeneğiyle etkinleştirirseniz, kullanıcılar ve uygulamalar tehlikeli etki alanlarına bağlanmasını engellenir. Windows Defender Güvenlik Merkezi'nde bu etkinliği görebilirsiniz. Bu ilke "Denetleme" seçeneğiyle etkinleştirirseniz, kullanıcı/uygulama tehlikeli etki alanlarına bağlanmasını engellenmeyecektir. Ancak, bu etkinlik Windows Defender Güvenlik Merkezi, yine de görürsünüz. Bu ilke devre dışı bırakırsanız, kullanıcı/uygulama tehlikeli etki alanlarına bağlanmasını engellenmeyecektir. Windows Defender Güvenlik Merkezi'nde tüm ağ etkinliği görmemeniz. Bu ilke yapılandırmazsanız, ağ engelleme, varsayılan olarak devre dışıdır.
  
  **Varsayılan**: Etkinleştir
  
- **Defender'ın tarama gününü zamanla**  
  Tarama gününü zamanla Defender.
  
  **Varsayılan**: her gün
  
- **Bulut teslimli koruma**  
  En iyi bilgisayarınızı korumak için Windows Defender bilgileri Microsoft'a bulduğu sorunları hakkında gönderir. Microsoft bu bilgileri analiz edin, sizin ve diğer müşterilerin etkileyen sorunlar hakkında daha fazla bilgi edinmek ve geliştirilmiş çözümler sunar.
  
  **Varsayılan**:  Evet  

- **Defender'ın uygulama eylemi olası istenmeyen**  
  Windows Defender virüsten koruma olası istenmeyen uygulama (PUA) Koruması özelliği, tanımlamak ve indiriliyor ve yükleniyor. ağınızdaki Uç noktalara Koruyucu'daki engelleyin. Bu uygulamalar, virüsler, kötü amaçlı yazılım veya diğer tür tehditlerden değerlendirilmeyen, ancak olumsuz etkileyen performanslarını veya kullanan uç noktalarda eylemler gerçekleştirebilir. PUA düşük itibarlı sahip olduğu kabul edilir ve uygulamalar için de başvurabilir. Tipik PUA davranışını içerir: Sürücü web tarayıcıları ve kayıt defteri iyileştiricileri Ad ekleme paketleme yazılımların çeşitli türleri, hataları düzeltin, ancak uç noktada kalır ve değişiklik ya da en iyi duruma getirme ("standart dışı virüsten koruma" programları olarak da bilinir) sağlamak için istek ödeme sorunları algılayın. Bu uygulamalar riskini artırabilir ağınızı kötü amaçlı yazılım bulaşması tanımlamak için daha sıkı olmasını kötü amaçlı yazılımdan Etkilenme neden ve uygulamaları temizleme, BT kaynaklarının boşa harcanmasına neden.  
  
  **Varsayılan**: Engelle  

- **Betik gizlenmiş makro kod türü**  
  Kötü amaçlı yazılım ve diğer tehditlerden karartmak veya kötü amaçlı kodlarını bazı komut dosyalarında gizleme girişiminde bulunabilir. Bu kural çalışmasını görünen gizlenmiş olabilir önler.
  
  **Varsayılan**: Engelle
  
- **Tam tarama sırasında Çıkarılabilir sürücüleri tara**  
  Windows Defender'ı tam tarama sırasında Çıkarılabilir sürücüleri (örneğin flash sürücü) kötü amaçlı ve istenmeyen yazılım taraması sağlar. Windows Defender virüsten koruma USB cihazları yürütmeden önce tüm dosyaları tarar.
  
  **Varsayılan**: Evet  
  
- **Arşiv dosyalarını tara**  
  Defender'ın tarama arşiv dosyaları.
  
  **Varsayılan**: Evet
  
- **Davranış izleme**  
  Erişim izni verdiği veya işlevselliği Windows Defender davranış izlemeye izin vermiyor. Windows 10'da katıştırılmış, algılayıcınız toplamak ve işletim sisteminden davranış sinyalleri işleyebilir ve yalıtılmış, özel bulut Örneğiniz için Microsoft Defender ATP bu sensör verilerini gönderir.
  
  **Varsayılan**: Evet

- **Ağ klasörlerinden açılan dosyaları tara**  
  Dosya salt okunur ise kullanıcı Algılanan kötü amaçlı yazılımı kaldırmak mümkün olmayacaktır.
  
  **Varsayılan**: Evet

- **Güvenilmeyen USB işlem türü**  
  Bu kural, yöneticilerin imzalanmamış veya güvenilmeyen yürütülebilir dosyalar SD kartları gibi USB çıkarılabilir sürücü çalışmasını engelleyebilir.
  
  **Varsayılan**: Engelle
  
- **Ekleme türü Office uygulamalarının diğer işlem**  
  Word, Excel, PowerPoint ve OneNote dahil olmak üzere, office uygulamalarının başka işlemlere kod eklemesini mümkün olmayacaktır. Bu genellikle, kötü amaçlı yazılım tarafından virüsten koruma tarama motorları etkinliğini gizlemek girişimi kötü amaçlı kod çalıştırmak için kullanılır.
  
  **Varsayılan**:  Engelle
  
- **Office makro kodu Win32 içeri aktarmalar türü izin ver**  
  Kötü amaçlı yazılım makro kodu'nde Office dosyaları almak ve daha fazla bulaşmasını sistem genelinde izin vermek için API çağrıları gerçekleştirmek için kullanılabilen Win32 DLL'leri yüklemek için kullanabilirsiniz. Bu kural, Win32 DLL'leri içe aktarabilir makro kodu içeren bir Office dosyaları engellemek çalışır. Bu, Word, Excel, PowerPoint ve OneNote içerir.
  
  **Varsayılan**: Engelle  
  
- **Defender'ın bulut engelleme düzeyi**  
  Defender'ın bulut blok düzeyi.
  
  **Varsayılan**: Yapılandırılmadı

- **Gerçek zamanlı izleme**  
  Defender'ın gerçek zamanlı izlemeyi gerektirir.
  
  **Varsayılan**: Evet
  
- **Office uygulamaları yürütülebilir içerik oluşturma veya başlatma türü**  
  Bu kural, şüpheli ve kötü amaçlı eklentiler ve oluşturan veya yürütülebilir dosya başlatmak betikleri (Uzantılar) tarafından kullanılan tipik davranışları hedefler. Tipik bir kötü amaçlı yazılım yöntem budur. Office uygulamaları tarafından kullanılan uzantıları engellenir. Genellikle bu uzantılar belirli görevleri otomatikleştirin veya kullanıcı tarafından oluşturulan eklenti özellikleri sağlayan komut dosyaları çalıştırmak için Windows Scripting Host (.wsh dosyaları) kullanın
  
  **Varsayılan**: Engelle

### <a name="windows-ink-workspace"></a>Windows Ink çalışma  

Daha fazla bilgi için [ilke CSP'si - WindowsInkWorkspace](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsinkworkspace) Windows belgelerinde.  

- **Mürekkep çalışma alanı**  
  Kullanıcının Ink çalışma alanına erişmesine izin verilip verilmeyeceğini belirtir. 
  - *Devre dışı* -mürekkep çalışma alanı erişimi devre dışı bırakıldı. Bu özellik devre dışıdır.
  - *Etkin* - mürekkep çalışma alanı özelliğin açık, ancak kullanıcının bunu kilit ekranının üstünde erişemez.
  - *Yapılandırılmamış* - mürekkep çalışma alanı özelliği açıktır ve kullanıcının bunu kilit ekranının üstünde kullanabilirsiniz.  

  **Varsayılan**: Enabled
 
### <a name="windows-powershell"></a>Windows PowerShell  

Daha fazla bilgi için [ilke CSP'si - WindowsPowerShell](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowspowershell) Windows belgelerinde.  

- **Power shell Kabuk betiği block günlüğe kaydetme**  
  Bu ilke ayarı, Microsoft-Windows-PowerShell/Operational Olay günlüğüne tüm PowerShell Betiği giriş günlüğü etkinleştirir. Bu ilke ayarını etkinleştirirseniz, Windows PowerShell komutları, komut dosyası blokları, İşlevler ve betikleri - işlenmesini etkileşimli olarak veya Otomasyon aracılığıyla çağrılan olmadığını günlüğe kaydeder. Bu ilke ayarını devre dışı bırakırsanız, PowerShell Betiği giriş günlüğünü devre dışı bırakıldı. Betik bloğu çağırma günlüğü etkinleştirirseniz, PowerShell, ayrıca komutu, betik bloğu, işlev veya betiği başlatıldığında veya durdurulduğunda olayları kaydeder. Çağrı günlüğü etkinleştirme, yüksek hacimli olay günlükleri oluşturur. Not: Bu ilke ayarı, Bilgisayar Yapılandırması hem Kullanıcı Yapılandırması Grup İlkesi Düzenleyicisi'nde altında bulunmaktadır. Bilgisayar Yapılandırma İlkesi ayarı üzerinden Kullanıcı Yapılandırması ilke ayarı öncelik kazanır.
  
  **Varsayılan**: Enabled
 
## <a name="next-steps"></a>Sonraki adımlar  

[Geçerli bir temel sürümünü görüntüleme](security-baseline-settings-mdm.md)  
[Yeni bir temel sürüm kullanmak üzere yükseltme profili](security-baselines.md#change-the-baseline-instance-for-a-profile)