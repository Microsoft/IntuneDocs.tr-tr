---
title: Windows 10 için Intune güvenlik temelleri ayarları
titleSuffix: Microsoft Intune
description: Windows 10 yönetmek için Intune güvenlik temel ayarları
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/20/2019
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
ms.openlocfilehash: d3b9f69e745baffd21b55274e173bb75e8581525
ms.sourcegitcommit: 256952cac44bc6289156489b6622fdc1a3c9c889
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2019
ms.locfileid: "67403743"
---
# <a name="mdm-security-baseline-settings-for-intune"></a>Intune MDM güvenlik temel ayarları  

Windows 10 çalıştıran cihazlar için desteklenen Microsoft Intune veya üzeri olan MDM güvenlik taban çizgisi ayarlarını görüntüleyin. Bu temelde ayarlar için varsayılan değerleri geçerli cihaz önerilen yapılandırmasını temsil eder ve diğer güvenlik temellerini temel varsayılanlarından eşleşmeyebilir.  

En son temel sürümdür **Spring 2019 güncelleştirme (19 saat 1) için MDM güvenlik temeli**  

Bu temel en son sürümünde önceki bir sürümünden değişiklikler hakkında bilgi edinmek için [yeni şablon Değiştirilenler](#whats-changed-in-the-new-template).  

> [!NOTE]  
> 2019 Haziran Önizleme MDM güvenlik temel sürümü tarafından değiştirildi *Spring 2019 güncelleştirme (19 saat 1) için MDM güvenlik temeli* generaly olan şablonu (önizlemede değil) kullanılabilir. Kullanılabilirliğini önce oluşturulan profiller *Spring 2019 güncelleştirme (19 saat 1) için MDM güvenlik temeli* olmaz temelini güncelleştirmek yansıtacak şekilde Spring 2019 güncelleştirme (MDM güvenlik temeli olan değerleri ve ayarları 19 saat 1) sürümü.  Önizleme şablonu temel alan yeni profilleri oluşturamazsınız ancak düzenleme ve önizleme şablona dayalı olarak daha önce oluşturduğunuz profillerini kullanmak devam edebilirsiniz.   
  
Güvenlik temellerini Intune ile kullanma hakkında bilgi edinmek için [güvenlik temellerini kullanın](security-baselines.md).  


   
## <a name="above-lock"></a>Kilit üzerinde  
Daha fazla bilgi için [ilke CSP'si - AboveLock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-abovelock) Windows belgelerinde.  

- **Blok görüntülenmesini kutlama bildirimleri**  
  Bu ilke ayarı, uygulama bildirimleri kilit ekranında görünmesini önlemek sağlar. Bu ilke ayarını etkinleştirirseniz, hiçbir uygulama bildirimleri kilit ekranında görüntülenir. Devre dışı bırakmak veya bu ilke ayarı yapılandırmazsanız, kullanıcıların hangi uygulamaları seçebilirsiniz kilit ekranında bildirimleri görüntüleme.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067101)  

  **Varsayılan**: Evet  

- **Ses, kilit ekranı uygulamalardan etkinleştir**  

  **Varsayılan**: Devre dışı

## <a name="app-runtime"></a>Uygulama çalışma zamanı    
Daha fazla bilgi için [ilke CSP'si - AppRuntime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-appruntime
) Windows belgelerinde.  

- **Windows Store uygulamaları için isteğe bağlı Microsoft hesapları**  
  Bu ilke ayarı Microsoft hesaplarının oturum açmak için bir hesap gerektiren Windows Store uygulamaları için isteğe bağlı olup olmadığını denetlemenizi sağlar. Bu ilke yalnızca destekleyen Windows Store uygulamaları etkiler. Bu ilke ayarını etkinleştirirseniz, genellikle oturum açmak için bir Microsoft hesabı gerektiren Windows Store uygulamaları, bunun yerine bir kuruluş hesabıyla oturum açmasına izin verir. Devre dışı bırakmak veya bu ilke ayarı yapılandırmazsanız, kullanıcıların bir Microsoft hesabıyla oturum açmanız gerekir.  
    [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067104)  
  
  **Varsayılan**: Enabled  

## <a name="application-management"></a>Uygulama Yönetimi   
Daha fazla bilgi için [ilke CSP'si - ApplicationManagement](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement) Windows belgelerinde.  

- **Blok kullanıcı denetime yüklemeleri**  
  Bu ilke ayarı, kullanıcıların genellikle yalnızca sistem yöneticileri tarafından kullanılabilir yükleme seçeneklerini değiştirmek izin verir. Bu ilke ayarını etkinleştirirseniz, Windows Installer'ın güvenlik özelliklerine bazıları atlanacağı. Bu bir güvenlik ihlali nedeniyle durdurulacak olan yüklemelerin tamamlanmasına izin verir. Windows Installer'ın güvenlik özelliklerine devre dışı bırakmak veya bu ilke ayarı yapılandırmazsanız, kullanıcıların dosyalarının yüklendiği dizinin belirtilmesi gibi sistem yöneticileri için genellikle ayrılmış yükleme seçeneklerini değiştirmesini engelleyin. Korumalı bir seçeneği değiştirmesine izin veren bir yükleme paketi Windows Installer algılarsa, yüklemeyi durdurur ve bir ileti görüntüler. Bu güvenlik özellikleri, yalnızca yükleme programı kullanıcıya izin verilmeyen dizinlere erişimi olan ayrıcalıklı güvenlik bağlamı çalışırken çalışır. Bu ilke ayarı, daha az kısıtlayıcı ortamlar için tasarlanmıştır. Yazılım yüklenmesini engelleyen bir yükleme programı hataları aşmak için kullanılabilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067060)  

    **Varsayılan**: Evet

- **Yükseltilmiş ayrıcalıklara sahip blok MSI uygulama yüklemeleri**  
  Bu ilke ayarı, Windows Installer'ın bir program yüklerken yükseltilmiş izinler kullanmanız yönlendirir.  
  - *Bu ilke ayarını etkinleştirirseniz*, ayrıcalıkları tüm programlar'ın genişletilmiş. Bu ayrıcalıkların genellikle bilgisayar (otomatik olarak yüklenir) f atanan (masaüstünde sunulur) kullanıcıya atanan olan veya Denetim Masası'ndaki Program Ekle veya Kaldır içinde kullanılabilir programlar için ayrılmıştır. Bu profil ayarlarını, kullanıcı görüntüleme veya değiştirme ileri derecede kısıtlı bilgisayarlarda dizinleri dahil olmak üzere, izni olmayabilir dizinlere program yüklemesini sağlar.
  - *Devre dışı bırakmak veya bu ilke ayarı yapılandırmazsanız*, bir Sistem Yöneticisi dağıtmak ya da programları yüklendiğinde sistem geçerli kullanıcının izinlerini uygular. Not: Bu ilke ayarı, bilgisayar yapılandırması ile Kullanıcı Yapılandırması klasörlerinde görünür. Bu ilke ayarı etkin hale getirmek için iki klasörü etkinleştirmeniz gerekir. Dikkat: Deneyimli kullanıcılar izinleri bu ilke ayarı ayrıcalıklarını değiştirmek ve kısıtlı dosya ve klasörlere yönelik kalıcı erişim kazanmak için izinler yararlanabilirsiniz. Bu ilke ayarı kullanıcı yapılandırması sürümü güvenli olmasını garanti edilmez unutmayın.  
  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067134)    

  **Varsayılan**: Evet

- **Oyun DVR (yalnızca Masaüstü) engelle**  
  Kaydetme ve oyun yayın izin verilip verilmediğini yapılandırır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067056)  
  
  **Varsayılan**: Evet  

## <a name="auto-play"></a>Otomatik Yürüt   
Daha fazla bilgi için [ilke CSP'si - Autoplay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-autoplay) Windows belgelerinde.  

- **Otomatik yürütme varsayılan otomatik çalıştırılan davranış**  
  Bu ayar otomatik çalıştırma komutları için varsayılan davranışını etkiler. Otomatik Çalıştırma komutları autorun.inf dosyalarında depolanır ve yükleme programları veya diğer yordamlar başlatabilirsiniz. Zaman *etkin*, Yöneticiler, Windows Vista çalıştıran bir cihazda varsayılan otomatik çalıştırma davranışını değiştirebilir veya üzeri. Davranışı ayarlanabilir: a) tamamen otomatik çalıştırma komutları devre dışı bırakın veya (b) davranış otomatik olarak otomatik çalıştırma komutunun yürütülmesi yeniden öncesi Windows Vista için geri döndür. Ayarlandığında *devre dışı bırakılmış* veya *yapılandırılmadı*, cihazları Windows Vista çalıştıran veya eklenebilir olup kullanıcı daha sonra sor otomatik çalıştırma komutunu çalıştırmanız gerekir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067133)       
  
  **Varsayılan**: Yürütülmeyen  
  
- **Otomatik yürütme modu**  
  Bu ilke ayarı, otomatik özelliği devre dışı bırakmak sağlar. Autoplay medyayı sürücüye takın sürücüyü okumaya başlar. Sonuç olarak, programları ve müzik kurulum dosyası ses ortamdaki hemen başlayın. Windows XP SP2 öncesinde otomatik bir disket sürücüsü gibi çıkarılabilir sürücüleri (ancak CD-ROM sürücüsü) ve ağ sürücülerini varsayılan olarak devre dışı bırakıldı. Windows XP SP2'den başlayarak, Autoplay Zip sürücüleri ve bazı USB yığın depolama cihazı gibi çıkarılabilir sürücülerde de, etkinleştirilir. Bu ilke ayarını etkinleştirirseniz, otomatik CD-ROM ve çıkarılabilir medya sürücüsü devre dışı veya tüm sürücüleri devre dışı olur. Bu ilke ayarı ek sürücüler tür Autoplay devre dışı bırakır. Varsayılan olarak devre dışı bırakılmış sürücülerde Autoplay etkinleştirmek için bu ayarı kullanamazsınız. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, otomatik etkinleştirilir. Not: Bu ilke ayarı bilgisayar yapılandırması ve kullanıcı yapılandırması klasörlerde görünür. İlke ayarları çakışırsa, Bilgisayar Yapılandırması ilke ayarında Kullanıcı Yapılandırması ilke ayarı önceliklidir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2066793)  
  
  **Varsayılan**: Devre dışı

- **Toplu olmayan cihazlar için Otomatik Oynat engelle**  
  Bu ilke ayarı, kamera veya telefon gibi MTP cihazları için otomatik izin vermiyor. Bu ilke ayarını etkinleştirirseniz, otomatik kamera veya telefon gibi MTP cihazları için izin verilmiyor. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, otomatik birim olmayan cihazlar için etkinleştirilmiş.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067106)    
  
  **Varsayılan**: Enabled  

## <a name="bitlocker"></a>BitLocker'ı    
Daha fazla bilgi için [ilke CSP'si - Bitlocker](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bitlocker
) Windows belgelerinde.  

- **Bit locker çıkarılabilir sürücü İlkesi**  
  Bu ilke ayarı, şifreleme yöntemini denetlemek ve güçlü şifre için kullanılır. Bu ilke değerlerini BitLocker şifreleme için kullandığı şifreleme gücünü belirler. Kuruluşlar, şifreleme düzeyini (AES-256'yı AES-128'den daha güçlü) Artırılmış güvenlik için denetlemek isteyebilirsiniz. Bu ayarı etkinleştirirseniz, bir şifreleme algoritması ve anahtar şifreleme düzeyi sabit veri sürücüleri, işletim sistemi sürücüleri ve çıkarılabilir veri sürücüleri için tek tek yapılandırmanız mümkün olacaktır. Sabit ve işletim sistemi sürücüleri için XTS-AES algoritmasını kullanmanızı öneririz. Sürücü Windows 10 'un 1511 veya sonraki bir sürümü çalıştırmıyor diğer cihazlar'da kullanılıyorsa, çıkarılabilir sürücüler için AES-CBC 128-bit veya AES-CBC 256 bit kullanmalısınız. Şifreleme yöntemi değiştirme, sürücü zaten şifrelendiyse veya şifreleme sürüyorsa hiçbir etkisi olmaz. Bu gibi durumlarda, bu ilke ayarı göz ardı edilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067140) 

  Bit locker çıkarılabilir sürücü ilke için aşağıdaki ayarları yapılandırın:

    - **Yazma erişimi için şifreleme iste**  
      **Varsayılan**: Evet  
  

## <a name="browser"></a>Tarayıcı  
Daha fazla bilgi için [ilke CSP'si - tarayıcı](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser) Windows belgelerinde.  

- **Microsoft Edge için SmartScreen gerektirir**  
  Microsoft Edge, kullanıcılar varsayılan olarak olası kimlik avı kuşku verici ve kötü amaçlı yazılımlardan korumak için Windows Defender SmartScreen (açık) kullanır. Ayrıca, varsayılan olarak, kullanıcılar (kapatma) devre dışı bırakamaz Windows Defender SmartScreen. Bu ilkeyi etkinleştirmek, Windows Defender SmartScreen devre dışı bırakır ve kullanıcıların açma engellemek. Bu ilke, kullanıcıların Windows defender SmartScreen açmak veya kapatmak seçmesine izin vermek için yapılandırmayın.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067029)   
  
  **Varsayılan**: Evet  
  
- **Kötü niyetli site erişimi engelle**  
  Varsayılan olarak, Microsoft Edge atlamak kullanıcılara (yoksay) Windows Defender SmartScreen uyarılarını siteye devam etmek için bunları izin vererek kötü amaçlı olabilecek sitelerle ilgili. Bu ilkeyle yine de kullanıcıların atlaması uyarıları önlemek için Microsoft Edge siteye devam etmesini engelleyen yapılandırabilirsiniz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067040)   
  
  **Varsayılan**: Evet  
  
- **Doğrulanmamış dosyayı indirme işlemini engelleyin**  
  Varsayılan olarak, Microsoft Edge atlamak kullanıcılara (yoksay) Windows Defender SmartScreen uyarılarını doğrulanmamış dosyaları indirme devam etmek için bunları izin vererek kötü amaçlı dosyaları hakkında. Bu ilkeyi etkinleştirmek, kullanıcıların doğrulanmamış dosyaları indirmesini engelleme uyarıları atlaması engeller.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067023)  
  
  **Varsayılan**: Evet  
  
- **Parola yöneticisini engelle**  
  Varsayılan olarak, Microsoft Edge parola Yöneticisi otomatik olarak kullanıcıların yerel yönetici parolaları kullanır. Bu ilkeyi devre dışı bırakmak, Microsoft Edge parola Yöneticisi kullanmasını önler. Bu ilke, kullanıcı Kaydet ve yerel parola Yöneticisi'ni kullanarak parolaları yönetmek seçin izin vermek istiyorsanız yapılandırmayın.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067128)  
  
  **Varsayılan**: Evet  
  
- **Sertifika hatası geçersiz kılmaları engelle**  
  Bu ilke ayarı, kullanıcı ("süresi gibi", "İptal" veya "Ad uyuşmazlığı" hatalar) Internet Explorer'da gözatma kesme Güvenli Yuva Katmanı/Aktarım Katmanı Güvenliği (SSL/TLS) sertifikası hataları yoksayma öğesinden engeller. Bu ilke ayarını etkinleştirirseniz, kullanıcı gözatma devam edemiyor. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, sertifika hataları yoksay ve Tarama devam etmek kullanıcı seçebilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067126)  
  
  **Varsayılan**: Evet  

## <a name="connectivity"></a>Bağlantı  
Daha fazla bilgi için [ilke CSP'si - bağlantı](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity) Windows belgelerinde.  

- **Web yayımı ve çevrimiçi sipariş sihirbazları için Internet blok indirme**  
  Bu ilke ayarı, Windows web yayımı ve çevrimiçi sipariş sihirbazları için sağlayıcıların listesini indirip indirmeyeceğini belirtir. Bu sihirbazlar, kullanıcıların çevrimiçi depolama alanını ve fotoğraf yazdırma gibi hizmetleri sağlayan şirketlerin listesinden seçmesine izin ver. Varsayılan olarak, Windows kayıt defterinde belirtilen sağlayıcılara ek olarak bir Windows Web sitesinden indirilen sağlayıcıları görüntüler. Bu ilke ayarını etkinleştirirseniz, Windows, sağlayıcıları ve yalnızca yerel kayıt defteri görüntüsünü önbelleğe alınan hizmet sağlayıcıları indirilmedi. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, kullanıcı Web'de yayımlama veya çevrimiçi sipariş sihirbazları kullandığında sağlayıcılarının bir listesini indirir. Kayıt defterinde hizmet sağlayıcıları belirtme hakkında bilgi içerir. daha fazla bilgi için web yayımı ve çevrimiçi sipariş sihirbazları için belgelere bakın.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067136)  
  
  **Varsayılan**: Enabled  

- **Yazıcı sürücülerini HTTP üzerinden indirmeyi engelleyin**  
  Bu ilke ayarı, bu istemci yazdırma sürücüsü paketleri HTTP üzerinden indirilmesine izin verilip verilmeyeceğini belirtir. HTTP yazdırmayı kurmak için HTTP üzerinden indirilecek gelen olmayan sürücüler gerekir. Not: Bu ilke ayarı istemci yazdırma Intranet veya Internet üzerinde yazıcılara HTTP üzerinden engellemez. Yalnızca zaten yerel olarak yüklü değildir sürücülerini indirmeyi yasaklar. Bu ilke ayarını etkinleştirirseniz, yazıcı sürücülerini HTTP üzerinden yüklenemiyor. Devre dışı bırakmak veya bu ilke ayarı yapılandırmazsanız, kullanıcıların yazıcı sürücülerini HTTP üzerinden indirebilirsiniz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067141)  
  
  **Varsayılan**: Enabled  

## <a name="credentials-delegation"></a>Kimlik temsilcisi  
Daha fazla bilgi için [ilke CSP'si - CredentialsDelegation](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-credentialsdelegation
) Windows belgelerinde.  

- **Uzak ana aktarılamaz kimlik temsili**  
  Uzak ana aktarılamaz kimlik temsili sağlar. Cihazları kimlik bilgilerini dışarı aktarılabilir bir sürümünü kimlik bilgileri temsilcisi kullanılırken, kullanıcıların kimlik bilgileri hırsızlığı riski saldırganlar uzaktaki ana makinede gelen gösterir. uzak konağa sağlar. Bu ilke ayarını etkinleştirirseniz, konak uzak Credential Guard ya da kısıtlı yönetici modunu destekler. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, sınırlı yönetim ve uzak Credential Guard modu desteklenmiyor. Kullanıcı kimlik bilgilerini ana bilgisayara geçirmek her zaman gerekecektir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067103)   
  
  **Varsayılan**: Enabled  

## <a name="credentials-ui"></a>Kimlik bilgileri kullanıcı Arabirimi  
Daha fazla bilgi için [ilke CSP'si - CredentialsUI](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-credentialsui) Windows belgelerinde.  

- **Yöneticiler listeleme** Bu ilke ayarı bir kullanıcı, çalışan bir uygulamayı yükseltme girişiminde bulunduğunda yönetici hesaplarını görüntülemek eşleştirilmeyeceğini denetler. Kullanıcı, çalışan bir uygulamayı yükseltme girişiminde bulunduğunda, varsayılan olarak, yönetici hesapları görüntülenmez. Bu ilke ayarını etkinleştirirseniz, kullanıcı seçin ve doğru parolayı girmek için bilgisayarda tüm yerel yönetici hesapları görüntüleyin. Bu ilke ayarını devre dışı bırakırsanız, kullanıcıların her zaman bir kullanıcı adı ve parola yükseltmesine yazmanız gerekir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067021)

  
  **Varsayılan**: Devre dışı  

## <a name="data-protection"></a>Veri Koruma  
Daha fazla bilgi için [ilke CSP'si - DataProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dataprotection
) Windows belgelerinde.  

- **Doğrudan bellek erişimi engelle**  
  Bir kullanıcı Windows oturum kadar bu ilke ayarı, doğrudan bellek erişimi (DMA) engellemek sık erişimli takılabilir PCI aşağı akış için tüm bağlantı sağlar. Bir kullanıcı oturum açtığında sonra Windows ana Tak PCI bağlantı noktalarına bağlı PCI cihazları numaralandırır. Her seferinde kullanıcı makine kilitler, DMA kullanıcı yeniden oturum kadar hiçbir alt cihazlarla sık erişimli Tak PCI noktalarına engellenir. Makine kilidi açıldı, zaten numaralandırılmıştır cihazlar takılı kadar çalışmaya devam eder. Bu ilke ayarı, BitLocker veya cihaz şifrelemesi etkinken yalnızca zorlanır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067031)     
  
  **Varsayılan**: Evet  

## <a name="device-guard"></a>Cihaz koruma  
Daha fazla bilgi için [ilke CSP'si - DeviceGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceguard
) Windows belgelerinde.  

- **Credential Guard**  
  Bu ayar, sonraki yeniden başlatma sırasında kimlik bilgilerinin korunmasına yardımcı olmak için sanallaştırma tabanlı güvenlik ile Credential Guard hakkında kullanıcıların sağlar.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067044)
   
  **Varsayılan**: UEFI kilidiyle etkinleştir 

- **Sanallaştırma tabanlı güvenliği etkinleştir**   
  Sanallaştırma tabanlı güvenlik (VBS) sonraki önyüklemede açar. Sanallaştırma tabanlı güvenlik, güvenlik hizmetlerine destek sağlamak için Windows Hiper Yöneticisi'ni kullanır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067066)  
  
  **Varsayılan**: Evet  


- **Sistem koruma başlatın**    
  **Varsayılan**: Enabled  

## <a name="device-installation"></a>Cihaz yükleme  
Daha fazla bilgi için [ilke CSP'si - DeviceInstallation](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceinstallation) Windows belgelerinde.  

- **Cihaz tanımlayıcıları olarak donanım cihaz yükleme**  
  Bu ilke ayarı Windows yüklenmesini engelleyen cihazlar için Tak ve Kullan donanım kimlikleri ve uyumlu bir listesini belirtmenize olanak sağlar. Bu ilke ayarı, bir cihaza yüklemek Windows sağlayan diğer ilke ayarları üzerinden önceliklidir. Bu ilke ayarını etkinleştirirseniz, Windows, donanım kimliği veya uyumlu kimliği görünür bir cihaz listesinde oluşturduğunuz yüklenmesini engelledi. İlke ayarı, Uzak Masaüstü sunucuda bu ilke ayarını etkinleştirirseniz, uzak masaüstü istemcisini belirtilen cihazlarından Uzak Masaüstü sunucuya yönlendirilmesini etkiler. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, cihazları yükleyebilir ve izin verilen veya diğer ilke ayarları tarafından önlenmiş olarak güncelleştirin.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2066794)  
  
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
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067048)  
  
  **Varsayılan**: Blok donanım cihaz yükleme  

    Zaman *Block donanım cihaz yükleme* olduğu belirlenirse, aşağıdaki ayarlar kullanılabilir.
    - **Eşleşen donanım cihazları kaldırma**    
    Bu ayar yalnızca olan *donanım cihaz yükleme kurulum sınıflar tarafından* ayarlanır *Block donanım cihaz yükleme*.  

      **Varsayılan**: *Varsayılan yapılandırma*  
  
    - **Engellenen donanım cihaz tanımlayıcıları**  
      Bu ayar yalnızca olan *donanım cihaz yükleme kurulum sınıflar tarafından* ayarlanır *Block donanım cihaz yükleme*.
      
      **Varsayılan**: *Varsayılan yapılandırma*  

## <a name="device-lock"></a>Cihaz kilidi  
Daha fazla bilgi için [ilke CSP'si - DeviceLock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock) Windows belgelerinde.  

- **Kamera kullanımını engelle**  
  PC Ayarları'nda kilit ekranı kamera iki durumlu düğme devre dışı bırakır ve kilit ekranında çağrılan bir kamera önler. Varsayılan olarak, kullanıcıların kullanılabilir bir kamera kilit ekranında çağrılmasını etkinleştirebilirsiniz. Bu ayarı etkinleştirirseniz, kullanıcılar artık etkinleştirme veya devre dışı PC Ayarları'nda kilit ekranı kamera erişimi mümkün olacaktır ve kilit ekranında kamera çağrılamaz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067052)
  
  **Varsayılan**: Enabled  

- **Parola iste**  
  Cihaz kilidi etkinleştirilip etkinleştirilmeyeceğini belirtir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067049)  
  
  **Varsayılan**: Evet  
  
    Zaman *parola iste* ayarlanır *Evet*, aşağıdaki ayarlar kullanılabilir.

    - **Parola en az karakter kümesi sayısı**  
      Güçlü PIN veya parola için gereken karmaşık öğe türleri (büyük ve küçük harfler, sayılar ve noktalama işaretleri) sayısı. PIN, masaüstü ve mobile cihazları için aşağıdaki davranışı uygular: 1 - gereken 3 - sayılar ve küçük harf, basamak yalnızca 2 - sayılar ve küçük harf olduğunu ve büyük harfler gereklidir. Masaüstü Microsoft hesapları ve etki alanı hesapları desteklenmez. 4 - rakamlar, küçük harfler, büyük harfler ve özel karakterler gereklidir. Desktop'ta desteklenmiyor. Varsayılan değer 1’dir.  
      [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067055)  
      
      **Varsayılan**: 3  
  
    - **Cihaz silinmeden önceki oturum açma hatası sayısı**  
      Cihaz temizlenmeden önce izin verilen kimlik doğrulama hataları sayısı. 0 değeri cihaz silme işlevselliği devre dışı bırakır.  
      [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067030)  
        
      **Varsayılan**: 10  
  
    - **Parola kullanım süresi (gün)**  
      En fazla parola yaşı ilkesi ayarını nasıl uzun süre (gün) belirler. Sistem kullanıcıdan değiştirmesini olmasını gerektirir. önce bir parola kullanılabilir. Gün sayısı 0 olarak ayarlayarak parolaları asla sona belirtebilirsiniz veya parolaları gün 1 ile 999 arasında bir süre sonra süresi dolacak şekilde ayarlayabilirsiniz. En fazla parola geçerlilik süresi 1 ile 999 gün arasında ise, en az parola geçerlilik süresi en fazla parola geçerlilik süresinden daha az olmalıdır. En fazla parola geçerlilik süresi 0 olarak ayarlarsanız, parola geçerlilik süresi alt sınırı 0 ile 998 gün arasında herhangi bir değer olabilir.  
      [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067028)  
      
      **Varsayılan**: 60  
  
    - **Gerekli parola türü**  
      PIN veya parola gerekli türünü belirler.  
      [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067027)  
      
      **Varsayılan**: Alfasayısal  
  
    - **En düşük parola uzunluğu**  
      Minimum parola uzunluğu ilkesi ayarını belirler en az bir kullanıcı hesabı için bir parola ayarlama yapabilirsiniz karakter sayısı. 1 ile 14 karakter arasında bir değer ayarlayabilirsiniz veya karakter sayısı 0 olarak ayarlayarak, parola gerektiğini kurabilirsiniz.  
      [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067024)  
      
      **Varsayılan**: 8  
  
    - **Basit parolaları engelle**  
      "1111" veya "1234" gibi PIN veya parolalara izin verilip verilmeyeceğini belirtir. Masaüstü için resimli parola kullanımını da denetler.  
      [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067127) 
      
      **Varsayılan**: Evet  
        *Evet, bir ayar basit parolaların kullanımına engeller.* 

  - **Önceki parolaların yeniden kullanılmasını engelleme**  
    Kaç adet parola kullanılamaz geçmişinde depolanacak belirtir. Değer, kullanıcının geçerli parolası içerir. Örneğin, ayarı ile *1* kullanıcı, yeni bir parola seçerken, geçerli parolaları yeniden kullanılamaz. Ayarı *5* kullanıcının yeni parolasını, geçerli parolaları veya herhangi bir önceki dört parolalarını ayarlayamayacağı anlamına gelir.  
    [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2066795)  
    
    **Varsayılan**: 24  

- **Slayt gösterisi engelle**  
  PC Ayarları'nda kilit ekranı slayt gösterisi ayarlarını devre dışı bırakır ve bir slayt gösterisi kilit ekranında çalışmasını önler. Varsayılan olarak, bunlar makine kilitleme sonra çalıştırılacak bir slayt gösterisi açabileceğinizi bilirsiniz. Bu ayarı etkinleştirirseniz, kullanıcılar, PC Ayarları'nda slayt gösterisi ayarlarını değiştiremez ve hiçbir slayt gösterisi başlayabilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067105) 
  
  **Varsayılan**: Enabled  
  *Etkin ayarı, slayt gösterilerini çalışmasını engeller.* 

- **Gün olarak parola en düşük yaş**  
  En az parola geçerlilik süresi ilke ayarı bir parola olmalıdır süre (gün cinsinden) belirler. kullanıcı değiştirmeden önce kullanıldı. 1 ile 998 gün arasında bir değer ayarlayabilirsiniz veya gün sayısı 0 olarak ayarlayarak, hemen bir parola değişikliklerini verebilirsiniz. En fazla parola geçerlilik süresi, parolaların süresiz belirten, 0 olarak ayarlanmadığı sürece, en az parola geçerlilik süresi en fazla parola geçerlilik süresi değerinden küçük olması gerekir. En fazla parola geçerlilik süresi 0 olarak ayarlarsanız, en az parola geçerlilik süresi 0 ile 998 arasında herhangi bir değere ayarlanabilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067022) 
  
  **Varsayılan**: 1.  

## <a name="dma-guard"></a>DMA koruma  
Daha fazla bilgi için [ilke CSP'si - DmaGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dmaguard) Windows belgelerinde.
- **Dış cihazları çekirdek DMA koruması ile uyumsuz numaralandırması**  
  Bu ilke, dış DMA özellikli cihazlarda karşı ek güvenlik sağlamak içindir. Dış DMA özellikli cihazlarda numaralandırma üzerinde daha fazla denetim için DMA'yı yeniden eşleme/cihaz bellek ayırma ve korumalı alana alma ile uyumsuz sağlar. Çekirdek DMA koruması desteklenir ve sistem üretici yazılımı tarafından etkin olduğunda bu ilke yalnızca etkinleşir. Çekirdek DMA koruma İlkesi aracılığıyla veya son kullanıcı tarafından kontrol edilemez bir platform özelliğidir. Üretim zamanında sistemi tarafından desteklenmesi gerekir. Sistem çekirdek DMA koruması destekleyip desteklemediğini kontrol etmek için lütfen MSINFO32.exe Özet sayfasında Çekirdek DMA koruması alanını denetleyin.  
  [Daha fazla bilgi edinin](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dmaguard#dmaguard-deviceenumerationpolicy)

  **Varsayılan**: Tüm engelleme   

## <a name="event-log-service"></a>Olay Günlüğü hizmeti  
Daha fazla bilgi için [ilke CSP'si - EventLogService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-eventlogservice) Windows belgelerinde.  

- **Güvenlik günlüğü maksimum dosya boyutunu KB**  
  Bu ilke ayarı, günlük dosyasının en büyük boyutu kilobayt cinsinden belirtir. Bu ilke ayarını etkinleştirirseniz, en fazla günlük dosyası boyutunu 1 megabayt (1024 kilobayt) ve 2 terabaytlık (2147483647 kilobayt) kilobayt artışlarla arasında olacak şekilde yapılandırabilirsiniz. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, günlük dosyasının en büyük boyutu yerel olarak yapılandırılmış değerine ayarlanır. Bu değer günlüğü Özellikleri iletişim kutusunu kullanarak yerel bir yönetici tarafından değiştirilebilir ve 20 megabayt olarak varsayılan.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067042)  
  
   **Varsayılan**: 196608  

- **Sistem günlük en fazla dosya boyutunu KB**  
  Bu ilke ayarı, günlük dosyasının en büyük boyutu kilobayt cinsinden belirtir. Bu ilke ayarını etkinleştirirseniz, en fazla günlük dosyası boyutunu 1 megabayt (1024 kilobayt) ve 2 terabaytlık (2147483647 kilobayt) kilobayt artışlarla arasında olacak şekilde yapılandırabilirsiniz. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, günlük dosyasının en büyük boyutu yerel olarak yapılandırılmış değerine ayarlanır. Bu değer günlüğü Özellikleri iletişim kutusunu kullanarak yerel bir yönetici tarafından değiştirilebilir ve 20 megabayt olarak varsayılan.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2066798)  
  
  **Varsayılan**: 32768  

- **Uygulama günlük en fazla dosya boyutunu KB**  
  Bu ilke ayarı, günlük dosyasının en büyük boyutu kilobayt cinsinden belirtir. Bu ilke ayarını etkinleştirirseniz, en fazla günlük dosyası boyutunu 1 megabayt (1024 kilobayt) ve 2 terabaytlık (2147483647 kilobayt) kilobayt artışlarla arasında olacak şekilde yapılandırabilirsiniz. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, günlük dosyasının en büyük boyutu yerel olarak yapılandırılmış değerine ayarlanır. Bu değer günlüğü Özellikleri iletişim kutusunu kullanarak yerel bir yönetici tarafından değiştirilebilir ve 20 megabayt olarak varsayılan.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067125)  
  
  **Varsayılan**: 32768  

## <a name="experience"></a>Deneyim  
Daha fazla bilgi için [ilke CSP'si - deneyimi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience) Windows belgelerinde.  

- **Blok Windows spot**  
  BT yöneticilerinin tüm Windows spot özelliklerini kapatmasını - Windows spot kilit ekranı, Windows ipuçları, Microsoft tüketici özellikleri ve diğer ilgili özellikler sağlar.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067037)  
  
  **Varsayılan**: Evet  

  Zaman *blok Windows spot* ayarlanır *Evet*, aşağıdaki ayarlar kullanılabilir.
  
  - **Windows spot'ta üçüncü taraf önerilerini engelle**  
    Üçüncü taraf yazılım uygulama ve içerik önerilerini izin vermek için yayımcıları ile Windows kilit ekranı spot, önerilen uygulamaların başlangıç menüsünde ve Windows ipuçları gibi özellikleri spotlight olup olmadığını belirtir. Kullanıcılar, Microsoft özellikler, uygulamalar ve hizmetler için öneriler yine de görebilirsiniz.  
    [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067045)  
      
    **Varsayılan**: Evet  
  - **Tüketici belirli özellikleri engelle**  
    BT yöneticilerinin, genellikle yalnızca tüketicilere yönelik olan gibi başlatma önerileri, üyelik bildirimleri, Post-OOBE uygulaması yükleme ve yeniden yönlendirme kutucukları deneyimleri açmalarını sağlar.  
    [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067054)  
     
    **Varsayılan**: Evet  

## <a name="exploit-guard"></a>Exploit Guard  
Daha fazla bilgi için [ilke CSP'si - ExploitGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-exploitguard) Windows belgelerinde.  

- **Exploit Protection XML**  
  BT yöneticisi, istenen sistem ve kuruluşunuzdaki tüm cihazlar için uygulama risk azaltma seçenekleri temsil eden bir yapılandırma çıkış göndermek etkinleştirir. Yapılandırma, bir XML tarafından temsil edilir. Exploit Protection dağıtabilir ve bulaşma vektörlerine kullanan kötü amaçlı yazılımlardan korunmasına cihazları yardımcı olur. Risk azaltma işlemleri (bir yapılandırma olarak bilinir) bir dizi oluşturmak için PowerShell ve Windows güvenlik uygulaması'nı kullanın. Ardından, bu yapılandırma, bir XML dosyası olarak dışarı aktarın ve risk azaltma ayarlarını kümesinin aynısına sahip oldukları tüm için ağınızda birden çok makineyle paylaşın. Ayrıca, dönüştürme ve exploit koruma yapılandırması XML içinde mevcut bir EMET yapılandırma XML dosyasını içeri aktarın.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067035)  
  
  **Varsayılan**: *Örnek xml sağlanır* 
 
## <a name="file-explorer"></a>Dosya Gezgini  
Daha fazla bilgi için [ilke CSP'si - ta dosya Gezgini](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-fileexplorer) Windows belgelerinde.  

- **Blok Veri Yürütme Engellemesi**  
  Veri Yürütme Engellemesi devre dışı bırakma, bazı eski eklenti uygulamalarının Sonlandırıcı Gezgini işlev izin verebilirsiniz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067043)  
  
  **Varsayılan**: Devre dışı  
   
- **Blok yığın bozulması sonlandırıldığında**  
  Yığın bozulması sonlandırıldığında devre dışı bırakma, Gezgini hala beklenmedik bir şekilde daha sonra sonlandırabilir rağmen bazı eski eklenti uygulamalarının Sonlandırıcı Gezgini hemen çalışmaya izin verebilirsiniz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067107)  
  
  **Varsayılan**: Devre dışı  
    

## <a name="internet-explorer"></a>Internet Explorer  
Daha fazla bilgi için [ilke CSP'si - Internet Explorer](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-internetexplorer) Windows belgelerinde.  

- **Durum çubuğu komut dosyası aracılığıyla Internet Explorer'ın kısıtlı bölge güncelleştirmeleri**  
  Bu ilke ayarı, betik bölge içindeki durum çubuğu güncelleştirmeye izin verilip verilmediğini yönetmenizi sağlar. 
  - *Bu ilke ayarını etkinleştirirseniz*, betik durum çubuğunu güncellemek için izin verilir.
  - *Devre dışı bırakmak veya bu ilke ayarı yapılandırmazsanız*, betik, durum çubuğunu güncelleştirmesine izin verilmiyor.  

  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067074)  

  **Varsayılan**: Devre dışı

- **Internet Explorer internet bölgesi sürükleyin ve bırakın veya kopyalama ve yapıştırmanın**  
  Bu ilke ayarı, kullanıcıların dosyaları ya da kopyalama sürükleyin ve bölgede bir kaynak dosyalarından yapıştırma yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, kullanıcılar dosyaları veya kopyalama sürükleyin ve bu bölge dosyalarından otomatik olarak yapıştırın. Aşağı açılan kutusunda istemi seçerseniz, kullanıcıların sürükleyin veya kopya dosyalar bu bölgeden verilmeyeceğini seçmek için sorgulanır. Bu ilke ayarını devre dışı bırakırsanız, kullanıcıların dosyaları sürükleyerek veya kopyalama ve dosyaları bu bölgeden yapıştırma engellenir. Bu ilke ayarı yapılandırmazsanız, kullanıcıların dosyaları ya da kopyalama sürükleyin ve bu bölge dosyalarından otomatik olarak yapıştırın.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067076)  

  **Varsayılan**: Devre Dışı Bırak

- **Internet Explorer'ın kısıtlı bölge .NET Framework bağımlı bileşenler**    
  Bu ilke ayarı, Authenticode imzalanmamış .NET Framework bileşenlerini Internet Explorer'dan çalışıp çalışmayacağını yönetmenizi sağlar. Bu bileşenler, bir nesne etiketi ve bir bağlantıdan başvurulan Yönetilen yürütülebilir dosyaları başvurulan yönetilen denetimleri içerir. Bu ilke ayarını etkinleştirirseniz, Internet Explorer işaretsiz yönetilen bileşenleri çalıştırır. Açılan kutusunda seçtiğiniz istemi, Internet Explorer işaretsiz yönetilen bileşenleri çalıştırılıp çalıştırılmayacağını için girmesini ister. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer işaretsiz yönetilen bileşenleri yürütülmez. Bu ilke ayarı yapılandırmazsanız, Internet Explorer işaretsiz yönetilen bileşenleri yürütülmez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067077)

  **Varsayılan**: Devre Dışı Bırak


- **Internet Explorer yerel makine bölgesi kötü amaçlı yazılımdan koruma karşı ActiveX denetimlerini çalıştırmaz**  
  Bu ilke ayarı, Internet Explorer karşı sayfalarında güvenli iseler denetlemek için ActiveX denetimleri, kötü amaçlı yazılımdan koruma programları çalışıp çalışmayacağını belirler. Bu ilke ayarını etkinleştirirseniz, Internet Explorer ActiveX denetiminin bir örneğini oluşturmak güvenli olup olmadığını görmek için kötü amaçlı yazılımdan koruma programınızı denetleyin olmaz. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer ActiveX denetiminin bir örneğini oluşturmak güvenli olup olmadığını görmek için kötü amaçlı yazılımdan koruma programı her zaman denetler. Bu ilke ayarı yapılandırmazsanız, Internet Explorer ActiveX denetiminin bir örneğini oluşturmak güvenli olup olmadığını görmek için kötü amaçlı yazılımdan koruma programınızı denetleyin olmaz. Kullanıcılar bu davranışı açıp kapatabilir, Internet Explorer güvenlik ayarlarını kullanarak kapatabilirsiniz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067152)

  **Varsayılan**: Devre dışı

- **Internet Explorer internet bölgesi veri kaynaklarına erişim**  
  Bu ilke ayarı, Internet Explorer Microsoft XML Parser (MSXML) ya da ActiveX Data Objects (ADO) kullanan başka bir güvenlik bölgesi'nden veri erişip erişemeyeceğini yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz, kullanıcılar bir bölge içinde başka bir siteden verilere erişmek için MSXML veya ADO kullanan bölge sayfasında yükleyebilir. Açılan kutusunda seçtiğiniz istemi, kullanıcıların sayfayı MSXML veya ADO bölgede başka bir siteden verilere erişmek için kullandığı bölgesinde yüklemek için izin verip vermeyeceklerini sorgulanır. Bu ilke ayarını devre dışı bırakırsanız, kullanıcıların bir bölge içinde başka bir siteden verilere erişmek için MSXML veya ADO kullanan bölge sayfasında yüklenemiyor. Bu ilke ayarı yapılandırmazsanız, kullanıcıların bir bölge içinde başka bir siteden verilere erişmek için MSXML veya ADO kullanan bölge sayfasında yüklenemiyor.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067078)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer kısıtlı bölge windows içinde farklı etki alanlarından içerik sürükleyin**  
  Bu ilke ayarı kaynak ve hedef aynı pencerede olduğunda içerik bir etki alanından farklı bir etki alanına sürükleyerek seçenekleri ayarlamanıza olanak sağlar. Bu ilke ayarını etkinleştirin ve Etkinleştir'i tıklatın, kaynak ve hedef aynı pencerede olduğunda kullanıcıların içeriği bir etki alanından farklı bir etki alanına sürükleyebilirsiniz. Kullanıcılar, bu ayarı değiştiremezsiniz. Bu ilke ayarını etkinleştirin ve devre dışı bırak'a tıklayın, kaynak ve hedef aynı pencerede olduğunda kullanıcıların içeriği bir etki alanından farklı bir etki alanına sürükleyemezsiniz. Kullanıcıların Internet Seçenekleri iletişim kutusunda Bu ayarı değiştiremezsiniz. Bu ilke ayarını devre dışı bırakır veya, yapılandırmayın kaynak ve hedef aynı pencerede olduğunda Internet Explorer 10'da, kullanıcıların içeriği bir etki alanından farklı bir etki alanına sürükleyemezsiniz. Kullanıcıların Internet Seçenekleri iletişim kutusunda Bu ayarı değiştirebilirsiniz. Bu ilke ayarını devre dışı bırakır veya, yapılandırmayın kaynak ve hedef aynı pencerede olduğunda Internet Explorer 9 ve önceki sürümlerinde, kullanıcıların içeriği bir etki alanından farklı bir etki alanına sürükleyebilirsiniz. Kullanıcıların Internet Seçenekleri iletişim kutusunda Bu ayarı değiştiremezsiniz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067079)  
  
  **Varsayılan**: Devre dışı
  
- **Internet Explorer sertifika adresi uyuşmazlığı Uyarısı**  
  Bu ilke ayarı, sertifika adresi uyumsuzluğu güvenlik uyarısını kapatmanızı sağlar. Bu ilke ayarı etkinleştirildiğinde, kullanıcı için farklı bir Web sitesi adresi, mevcut sertifikalara Güvenli HTTP (HTTPS) Web siteleri ziyaret uyarılır. Bu uyarı, sahtekarlık saldırılarını önlemeye yardımcı olur. Bu ilke ayarını etkinleştirirseniz, sertifika adresi uyuşmazlığı her zaman uyarı görünür. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, kullanıcı (Internet Denetim Masası'nda Gelişmiş sayfasını kullanarak) sertifika adresi uyuşmazlığı uyarısı görüntülenip görüntülenmeyeceğini seçebilirsiniz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067153)  
  
  **Varsayılan**: Enabled 
  
- **Internet Explorer kısıtlı bölge ayrıcalıklı siteleri daha az**  
  Bu ilke ayarı, bu bölgeye Web siteleri Internet siteleri gibi daha az ayrıcalıklı bölgelerdeki gidebilirsiniz yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, Web siteleri daha az ayrıcalıklı bölgelerdeki yeni pencerelerde açın veya bu bölgeye gidin. Güvenlik bölgesi ek koruma Bölge Yüksekliği güvenlik özelliği tarafından sağlanan bir güvenlik katmanı olmadan çalışır. Açılan kutusunda seçtiğiniz istemi, riskli olabilecek Gezinti gerçekleşmek üzere olan bir kullanıcı için bir uyarı verilir. Bu ilke ayarını devre dışı bırakırsanız, zararlı olabilecek Gezinti engellenir. Internet Explorer güvenlik özelliği bu bölgede bölge yükseltme özelliği denetiminden koruma tarafından belirlenen açıktır. Bu ilke ayarı yapılandırmazsanız, zararlı olabilecek gezintiler engellenir. Internet Explorer güvenlik özelliği bu bölgede bölge yükseltme özelliği denetiminden koruma tarafından belirlenen açıktır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067148)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Dosya için Internet Explorer kısıtlı bölge otomatik istemi indirir**  
  Bu ilke ayarı, kullanıcıların olmayan kullanıcı tarafından başlatılan dosya indirmeleri için sorulup sorulmayacağını belirler. Bu ayar ne olursa olsun, kullanıcılar, dosya indirme iletişim kutuları için kullanıcı tarafından başlatılan indirmeler alır. Bu ayarı etkinleştirirseniz, kullanıcılar bir dosya indirme iletişim kutusu için otomatik indirme denemelerinin alır. Devre dışı bırakın ya da bu ayarı yapılandırmayın, kullanıcı tarafından başlatılan olmayan dosya yüklemeleri engellenir ve kullanıcıların dosya indirme iletişim kutusu yerine bildirim çubuğu göreceksiniz. Kullanıcılar daha sonra dosya indirme istemi izin vermek için bildirim çubuğu tıklatabilirsiniz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067150)  
  
  **Varsayılan**: Devre dışı
  
- **Internet Explorer internet bölgesi .NET Framework bağımlı bileşenler**  
  Bu ilke ayarı, Authenticode imzalanmadığını .NET Framework bileşenlerini Internet Explorer'dan çalışıp çalışmayacağını yönetmenizi sağlar. Bu bileşenler, bir nesne etiketi ve bir bağlantıdan başvurulan Yönetilen yürütülebilir dosyaları başvurulan yönetilen denetimleri içerir. Bu ilke ayarını etkinleştirirseniz, Internet Explorer işaretsiz yönetilen bileşenleri çalıştırır. Açılan kutusunda seçtiğiniz istemi, Internet Explorer işaretsiz yönetilen bileşenleri çalıştırılıp çalıştırılmayacağını için girmesini ister. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer işaretsiz yönetilen bileşenleri yürütme olmaz. Bu ilke ayarı yapılandırmazsanız, Internet Explorer işaretsiz yönetilen bileşenleri çalıştırır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067073)  
  
  **Varsayılan**: Devre Dışı Bırak 
  
- **Internet Explorer internet bölgesi izin tdc ActiveX denetimlerini kullanmak için etki alanları yalnızca onaylanmış**  
  Bu ilke ayarı, kullanıcı Web siteleri TDC ActiveX denetimini çalışıp çalışamayacağını denetler. Bu ilke ayarını etkinleştirirseniz, bu bölgedeki sitelerinden TDC ActiveX denetimini çalışmaz. Bu ilke ayarını devre dışı bırakırsanız, bu bölgedeki tüm sitelerden TDC ActiveX denetimi çalıştırılır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067151)
  
  **Varsayılan**: Enabled 
  
- **Windows Internet Explorer'ın kısıtlı bölge betik başlatıldı**  
  Bu ilke ayarı, betik tarafından başlatılan açılır pencereleri ve başlık ve durum çubuğu içeren windows üzerindeki kısıtlamaları yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz, bu bölgede Windows kısıtlamaları güvenlik uygulanmayacak. Bu özellik tarafından sağlanan bir güvenlik katmanı eklendi olmadan güvenlik bölgesi çalıştırır. Bu ilke ayarını devre dışı bırakırsanız, betik tarafından başlatılan açılır pencereleri ve başlık ve durum çubuğu içeren windows içerdiği zararlı olabilecek eylemler çalıştıramazsınız. Internet Explorer güvenlik özelliği bu bölgede işlem için Windows güvenlik kısıtlamaları komut dosyası özellik denetim ayarı tarafından belirlenen açıktır. Bu ilke ayarı yapılandırmazsanız, betik tarafından başlatılan açılır pencereleri ve başlık ve durum çubuğu içeren windows içerdiği zararlı olabilecek eylemler çalıştıramazsınız. Internet Explorer güvenlik özelliği bu bölgede işlem için Windows güvenlik kısıtlamaları komut dosyası özellik denetim ayarı tarafından belirlenen açıktır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067075)  
  
  **Varsayılan**: Devre dışı 
  
- **Internet Explorer internet bölgesi dahil yerel yolu sunucu için dosyalar karşıya yüklenirken**  
  Bu ilke ayarı, kullanıcı, bir HTML formu aracılığıyla bir dosya karşıya yüklenirken yerel yol bilgisi gönderilir, denetler. Yerel yol bilgisi gönderilir, bazı bilgiler sunucuya yanlışlıkla açığa. Örneğin, kullanıcının Masaüstü'nden gönderilen dosya yolun bir parçası olarak kullanıcı adını içerebilir. Bu ilke ayarını etkinleştirirseniz, kullanıcı, bir HTML formu aracılığıyla bir dosya karşıya yüklenirken yol bilgisi gönderilir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcı, bir HTML formu aracılığıyla bir dosya karşıya yüklenirken yol bilgisi kaldırıldı. Bu ilke ayarı yapılandırmazsanız, kullanıcı, bir HTML formu aracılığıyla bir dosyayı karşıya yüklediğinizde, yol bilgisi gidiyor olup olmadığını seçebilir. Varsayılan olarak, yol bilgisi gönderilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067072)  
  
  **Varsayılan**: Devre dışı 
  
- **Internet Explorer, geliştirilmiş korumalı mod işlemi devre dışı bırak**  
  Bu ilke ayarı Internet Explorer 11 64-bit işlemler (için daha fazla güvenlik için) veya (daha fazla uyumluluk için) 32-bit işlemler zaman kullanıp kullanmadığını belirler geliştirilmiş korumalı modu 64-bit Windows sürümlerinde çalışan. Önemli: 64 bit işlemleri kullanıldığında bazı ActiveX denetimleri ve araç çubuklarını kullanılamayabilir. Bu ilke ayarını etkinleştirirseniz, Internet Explorer 11 geliştirilmiş korumalı modu 64-bit Windows sürümlerinde çalışan 64-bit sekmesi işlemleri kullanır. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer 11 zaman geliştirilmiş korumalı modu 64-bit Windows sürümlerinde çalışan 32-bit sekmesi işlemleri kullanır. Bu ilke ayarı yapılandırmazsanız, kullanıcıların üzerinde veya Internet Explorer ayarlarını kullanarak bu özelliği kapatabilirsiniz. Bu özellik varsayılan olarak kapalıdır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067149)  
  
  **Varsayılan**: Enabled 
  
- **Internet Explorer, sertifika hataları yoksay**  
  Bu ilke ayarı, kullanıcı ("süresi gibi", "İptal" veya "Ad uyuşmazlığı" hatalar) Internet Explorer'da gözatma kesme Güvenli Yuva Katmanı/Aktarım Katmanı Güvenliği (SSL/TLS) sertifikası hataları yoksayma öğesinden engeller. Bu ilke ayarını etkinleştirirseniz, kullanıcı gözatma devam edemiyor. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, sertifika hataları yoksay ve Tarama devam etmek kullanıcı seçebilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067071)  
  
  **Varsayılan**: Devre dışı 
  
- **XAML dosyalarının Internet Explorer internet bölgesi yükleniyor**  
  Bu ilke ayarı, Extensible Application Markup Language (XAML) dosyaların yüklenmesini yönetmenize olanak sağlar. XAML, zengin kullanıcı arabirimleri ve Windows Presentation Foundation yararlanan bir grafik oluşturmak için yaygın olarak kullanılan bir XML tabanlı bildirim temelli bir biçimlendirme dilidir. Bu ilke ayarını etkinleştirin ve etkinleştirmek için açılan kutudan ayarlayın, XAML dosyaları Internet Explorer içinde otomatik olarak yüklenir. Kullanıcı bu davranışı değiştiremezsiniz. Açılan kutunun istemine ayarlarsanız, XAML dosyalarının yüklenmesi için kullanıcıdan istenir. Bu ilke ayarını devre dışı bırakırsanız, XAML dosyaları Internet Explorer yüklü değilken. Kullanıcı bu davranışı değiştiremezsiniz. Bu ilke ayarı yapılandırmazsanız, kullanıcının Internet Explorer içinde XAML dosyalarını yüklemeye karar verebilirsiniz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067147)  
  
  **Varsayılan**: Devre Dışı Bırak 
  
- **Dosya için Internet Explorer internet bölgesi istemi otomatik indirmeleri**  
  Bu ilke ayarı, kullanıcıların olmayan kullanıcı tarafından başlatılan dosya indirmeleri için sorulup sorulmayacağını belirler. Bu ayar ne olursa olsun, kullanıcılar, dosya indirme iletişim kutuları için kullanıcı tarafından başlatılan indirmeler alır. Bu ayarı etkinleştirirseniz, kullanıcılar bir dosya indirme iletişim kutusu için otomatik indirme denemelerinin alır. Devre dışı bırakın ya da bu ayarı yapılandırmayın, kullanıcı tarafından başlatılan olmayan dosya yüklemeleri engellenir ve kullanıcıların dosya indirme iletişim kutusu yerine bildirim çubuğu göreceksiniz. Kullanıcılar daha sonra dosya indirme istemi izin vermek için bildirim çubuğu tıklatabilirsiniz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067117)  
  
  **Varsayılan**: Devre dışı  
  
- **Güvenli olmayan dosyalar için Internet Explorer'ın kısıtlı bölge güvenlik uyarısı**  
  "Dosya – Güvenlik Uyarısı açın" iletisi görüntülenirse, kullanıcı yürütülebilir dosyaları veya diğer olmayabilecek dosyaları (örneğin dosya Gezgini'ni kullanarak bir intranet dosya paylaşımından) açmayı denediğinde bu ilke ayarı denetler. Bu ilke ayarını etkinleştirin ve etkinleştirmek için açılan kutudan ayarlayın, bu dosyalar olmadan bir güvenlik uyarısı açın. Açılan kutunun istemine ayarlarsanız, dosyaları açmadan önce bir güvenlik uyarısı görüntülenir. Bu ilke ayarını devre dışı bırakırsanız, bu dosyalar açmayın. Bu ilke ayarı yapılandırmazsanız, kullanıcı, bilgisayar bu dosyaları nasıl işlediğini yapılandırabilirsiniz. Varsayılan olarak, bu dosyalar Intranet ve yerel bilgisayar bölgeleri, etkin Yasak bölgesinde engellenen ve Internet ve güvenilen bölgelerde isteyecek şekilde ayarlayın.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2066797)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer internet bölgesi çoklu site komut dosyası filtresi**  
  Bu ilke, siteler arası betik (XSS) filtre algılayın ve bu bölgedeki Web siteleri içine siteler arası betik eklemelerini engelle denetler. Bu ilke ayarını etkinleştirirseniz, bu bölgedeki sitelerden XSS filtre açıktır ve XSS filtre siteler arası betik eklemelerini engellemeye çalışır. Bu ilke ayarını devre dışı bırakırsanız, bu bölgedeki sitelerden XSS filtre kapalıdır ve Internet Explorer, siteler arası betik eklemelerini izin verir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067053) 
  
  **Varsayılan**: Enabled 
  
- **Internet Explorer SSL3 geri dön**  
  Bu ilke ayarı, güvenli olmayan bir geri dönüş SSL 3.0 engellemenize olanak sağlar. Bu ilke etkinleştirildiğinde, Internet Explorer sitelere kullanarak SSL 3.0 veya TLS 1.0 veya üstü başarısız olduğunda aşağıda bağlanmayı dener. Bir adam-de-ortadaki adam saldırısı önlemek için güvenli olmayan bir geri dönüş izin verme öneririz. Bu ilke, hangi güvenlik protokollerine etkin etkilemez. Bu ilke devre dışı bırakırsanız, sistem varsayılan değerler kullanılır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067118)  
  
  **Varsayılan**: Site yok  

- **Internet Explorer şifreleme desteği**  
  Bu ilke ayarı, tarayıcıda Aktarım Katmanı Güvenliği (TLS) 1.0, TLS 1.1, TLS 1.2, Güvenli Yuva Katmanı (SSL) 2.0 veya SSL 3.0 desteğini devre dışı bırakmak sağlar. TLS ve SSL, tarayıcı ve hedef sunucu arasındaki iletişimi korumak kurallarıdır. Hedef sunucu ile korunan bir iletişim kurmak tarayıcı girişiminde bulunduğunda, tarayıcı ve sunucu hangi protokol ve sürüm kullanmak için anlaşır. Desteklenen protokoller ve sürümler birbirlerinin listesi ile eşleşecek şekilde tarayıcı ve sunucu denemek ve bunlar en çok tercih edilen eşleşmeyi seçin. Bu ilke ayarını etkinleştirirseniz, tarayıcı belirleyici veya şifreleme tüneli aşağı açılan listeden seçtiğiniz şifreleme yöntemlerini kullanarak gerçekleştirmez. Devre dışı bırakmak veya bu ilke ayarı yapılandırmazsanız, kullanıcının hangi şifreleme seçebileceği yöntemi tarayıcıya destekler.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067057)

  **Varsayılan**: 2 öğe:  TLS v1.1 ve TLS 1.2 sürümü  
  *Bu ayar için seçebileceğiniz seçenekleri görüntülemek için aşağı oku seçin.*
  
- **Internet Explorer'ın internet bölgesi akıllı ekran aşağıya kilitli**  
  Bu ilke kötü amaçlı içerik için bu bölgedeki sayfalar SmartScreen Filtresi tarar olmadığını ayarı denetler. Bu ilke ayarını etkinleştirirseniz, SmartScreen Filtresi, kötü amaçlı içerik için bu bölgedeki sayfalar tarar. Bu ilke ayarını devre dışı bırakırsanız, kötü amaçlı içerik için bu bölgedeki sayfalar SmartScreen Filtresi taramaz. Bu ilke ayarı yapılandırmazsanız, kullanıcıya SmartScreen Filtresi'ni kötü amaçlı içerik için bu bölgedeki sayfalar tarayıp taramayacağını seçebilirsiniz. Not: Internet Explorer 7'de, bu ilke ayarı, kimlik avı filtre kötü amaçlı içerik için bu bölgedeki sayfalar tarayıp taramayacağını denetler.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067059)  
  
  **Varsayılan**: Enabled 
  
- **Internet Explorer bölge başlatma uygulamalar ve dosyalar bir iFrame içinde kısıtlı**  
  Bu ilke ayarı, uygulamaları çalıştırabilir ve dosyaları, HTML sayfaları bu bölgedeki bir IFRAME başvurusuna şuradan indirilebilir yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, kullanıcılar uygulamalarını çalıştırmak ve kullanıcı müdahalesi olmadan bu bölgedeki sayfalarında IFRAMES dosyaları indirin. Açılan kutusunda seçtiğiniz istemi, kullanıcılara uygulamalarını çalıştırmak ve bu bölgedeki sayfalarında IFRAMES dosyaları karşıdan seçmeleri istenir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcıların uygulamaları çalıştırmaya ve bu bölgedeki sayfalarında IFRAMES dosyaları indirme engellenir. Bu ilke ayarı yapılandırmazsanız, kullanıcıların uygulamaları çalıştırmaya ve bu bölgedeki sayfalarında IFRAMES dosyaları indirme engellenir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067061)  
  
  **Varsayılan**: Devre Dışı Bırak 
  
- **Internet Explorer atlama smart screen'i uyarıları seyrek dosyaları hakkında**  
  Bu ilke ayarı, kullanıcı Kimden SmartScreen Filtresi uyarılarını devre dışı bırakabilir olup olmadığını belirler. SmartScreen Filtresi, Internet Explorer kullanıcıların yaygın olarak Internet'ten yüklemeyin yürütülebilir dosyaları hakkında kullanıcıyı uyarır. Bu ilke ayarını etkinleştirirseniz, kullanıcıya SmartScreen Filtresi uyarılarını engelleyin. Kullanıcı devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, SmartScreen Filtresi uyarılarını devre dışı bırakabilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067068)  
  
  **Varsayılan**: Devre dışı  
  
- **İnternet bölgesi için Internet Explorer Açılır Pencere Engelleyicisi**  
  Bu ilke ayarı, istenmeyen açılır pencerelerin görüntülenip görüntülenmeyeceğini yönetmenize olanak sağlar. Son kullanıcı bağlantıyı tıklattığında açılan açılan pencereler engellenmez. Bu ilke ayarını etkinleştirirseniz, en istenmeyen açılır pencereleri görüntülenmesi engellenir. Bu ilke ayarını devre dışı bırakırsanız, açılır pencereleri görünmesini engelleyen değildir. Bu ilke ayarı yapılandırmazsanız en istenmeyen açılır pencereleri görüntülenmesi engellenir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067069)  
  
  **Varsayılan**: Etkinleştir  
  
- **Internet Explorer tutarlı MIME işleme işlemleri**  
  Internet Explorer dinamik ikili davranışlar içerir: takılı HTML öğeleri için belirli işlevi kapsülleyen bileşenler. Bu ilke, ikili davranışı güvenlik kısıtlama ayarını engellendi veya izin ayarı denetler. Bu ilke ayarını etkinleştirirseniz, ikili davranışları için dosya Gezgini ve Internet Explorer işlemleri engellenir. Bu ilke ayarını devre dışı bırakırsanız, ikili davranışları dosya Gezgini ve Internet Explorer işlemleri için izin verilir. Bu ilke ayarı yapılandırmazsanız, ikili davranışları için dosya Gezgini ve Internet Explorer işlemleri engellenir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067144)  
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer'ın kısıtlı bölge java izinleri**  
  Bu ilke ayarı, Java uygulamaları için izinleri yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz, Seçenekler açılır kutusundan seçebilirsiniz. Özel denetim izinlerini ayarlar için ayrı ayrı. Düşük güvenilirlik, uygulamaların tüm işlemleri sağlar. Orta düzey güvenilirlik (bir alanda bellek görüşmesi yapamaz program dışında), kendi sanal uygulamaların artı boş alan (istemci bilgisayarda bir güvenli depolama alanı) ve kullanıcı tarafından denetlenen dosya g/ç gibi özellikler sağlar. Yüksek güvenilirlik, korumalı alanında çalışmasını sağlar. Java uygulamaları çalışmasını önlemek için devre dışı bırakın. Bu ilke ayarını devre dışı bırakırsanız, Java uygulamalarını çalıştıramazsınız. Bu ilke ayarı yapılandırmazsanız, Java uygulamalarını devre dışı bırakıldı.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067132)  
  
  **Varsayılan**: Java devre dışı bırak  
    
  
- **Korumalı modda Internet Explorer ActiveX denetimleri**  
  Bu ilke ayarı, ActiveX denetimleri geliştirilmiş korumalı mod etkinleştirildiğinde korumalı modda çalışmasını engeller. Geliştirilmiş korumalı mod ile uyumlu olmayan bir ActiveX denetimi bir kullanıcının bir Web sitesi denetim yükleme girişiminde, Internet Explorer kullanıcıya bildirir ve Web sitesi normal korumalı modda çalıştırma seçeneği sunar. Bu ilke ayarı, bu bildirim devre dışı bırakır ve geliştirilmiş korumalı modu çalıştırmak için tüm Web sitelerinin zorlar. Geliştirilmiş korumalı mod, Windows 64 bit sürümlerinde 64 bit işlemleri kullanarak kötü amaçlı Web sitelerinin karşı ek koruma sağlar. En az çalıştıran bilgisayarlar için Windows 8, geliştirilmiş korumalı mod da sınırlar Internet Explorer okuyabileceği konumlar kayıt defteri ve dosya sistemi. Geliştirilmiş korumalı mod etkin ve geliştirilmiş korumalı mod ile uyumlu olmayan bir ActiveX denetimini yükleme girişiminde bir Web sitesi üzerinden kullanıcı gelir, Internet Explorer kullanıcıya bildirir ve geliştirilmiş korumalı mod için devre dışı bırakma seçeneği sunar Bu özel Web sitesi. Bu ilke ayarını etkinleştirirseniz, Internet Explorer geliştirilmiş korumalı mod devre dışı bırakma seçeneği kullanıcıya vermek olmaz. Tüm korumalı mod Web siteleri, geliştirilmiş korumalı modu çalıştırılır. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, Internet Explorer kullanıcıları uyarır ve normal korumalı modda uyumsuz ActiveX denetimleri ile Web sitelerini çalıştırmak için bir seçenek sunar.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067145)  
  
  **Varsayılan**: Devre dışı  
  
- **XAML dosyalarının Internet Explorer kısıtlı bölge yükleniyor**  
  Bu ilke ayarı, Extensible Application Markup Language (XAML) dosyaların yüklenmesini yönetmenize olanak sağlar. XAML, zengin kullanıcı arabirimleri ve Windows Presentation Foundation yararlanan bir grafik oluşturmak için yaygın olarak kullanılan bir XML tabanlı bildirim temelli bir biçimlendirme dilidir. Bu ilke ayarını etkinleştirin ve etkinleştirmek için açılan kutudan ayarlayın, XAML dosyaları Internet Explorer içinde otomatik olarak yüklenir. Kullanıcı bu davranışı değiştiremezsiniz. Açılan kutunun istemine ayarlarsanız, XAML dosyalarının yüklenmesi için kullanıcıdan istenir. Bu ilke ayarını devre dışı bırakırsanız, XAML dosyaları Internet Explorer yüklü değilken. Kullanıcı bu davranışı değiştiremezsiniz. Bu ilke ayarı yapılandırmazsanız, kullanıcının Internet Explorer içinde XAML dosyalarını yüklemeye karar verebilirsiniz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067070)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer pencerelerine güvenlik kısıtlamaları işlemleri**  
  Internet Explorer, program aracılığıyla açın, yeniden boyutlandırma ve çeşitli türlerdeki windows yeniden konumlandırmak için komut dosyaları sağlar. Pencere Kısıtlamaları güvenlik özelliği açılır pencereleri kısıtlar ve betikleri başlık ve Durum Çubuğu'nın kullanıcıya görünür olmayan veya diğer Windows başlık ve durum çubukları karartmak windows görüntülenmesini engeller. Bu ilke ayarını etkinleştirirseniz, tüm işlemler için pencerelerine kısıtlanır. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın pencerelerine sınırlı değildir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067146)  
  
  **Varsayılan**: Enabled   
  
- **Internet Explorer kısıtlı bölge ActiveX denetimleri ve eklentileri çalıştırma**  
  Bu ilke ayarı ActiveX denetimleri ve eklentiler sayfalarda belirtilen bölgeden çalıştırabilirsiniz yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, denetimleri ve eklentiler kullanıcı müdahalesi olmadan çalıştırabilirsiniz. Aşağı açılan kutusunda seçtiğiniz istemi kullanıcıların denetimleri izin verip vermeyeceklerini sorulan veya çalıştırmak için eklenti vardır. Bu ilke ayarını devre dışı bırakırsanız, denetimleri ve eklentiler çalışması engellenir. Bu ilke ayarı yapılandırmazsanız, denetimleri ve eklentiler çalışması engellenir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067114) 
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer'ın kısıtlı bölge betik ActiveX denetimleri için güvenli olarak işaretlenmiş**  
  Bu ilke ayarı, bir ActiveX denetimi için güvenli olarak işaretlenmiş bir betik ile etkileşimde bulunup bulunamayacağı yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, komut dosyası etkileşimi kullanıcı müdahalesi olmadan otomatik olarak ortaya çıkabilir. Aşağı açılan kutusunda istemi seçerseniz, kullanıcıların betik katılımına izin verip vermeyeceklerini sorgulanır. Bu ilke ayarını devre dışı bırakırsanız, betik etkileşim oluşmasını engellenir. Bu ilke ayarı yapılandırmazsanız, betik etkileşim oluşmasını engellenir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067062)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer'ın kısıtlı bölge oturum açma seçenekleri**  
  Bu ilke ayarı, oturum açma seçenekleri ayarlarını yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz, aşağıdaki oturum açma seçenekleri arasından seçim yapabilirsiniz. 
  - *Anonim* - anonim oturum açma devre dışı bırakma HTTP kimlik doğrulaması kullanın ve yalnızca ortak Internet dosya sistemi (CIFS) protokolü için Konuk hesabı kullanın. 
  - *İstemi* -kullanıcı kimliklerini ve parolaları için kullanıcı adı ve parola sorgusu kullanıcıları için kullanım istemi. Bir Kullanıcı sorgulandıktan sonra bu değerleri sessizce oturumunun geri kalanı için kullanılabilir. 
  - *Yalnızca Intranet bölgesinde otomatik oturum açma* -kullanıcı kimliklerini ve parolaları diğer bölgelerdeki sorgusu kullanıcıları için bu seçeneği kullanın. Bir Kullanıcı sorgulandıktan sonra bu değerleri sessizce oturumunun geri kalanı için kullanılabilir. 
  - *Geçerli kullanıcı adı ve parola otomatik oturum*-Windows NT Sınama yanıtı (NTLM kimlik doğrulaması olarak da bilinir) kullanarak oturum açma denemesi için bu seçeneği kullanın. Sunucu, Windows NT Sınama yanıtı, kullanıcının ağ kullanıcı adı ve parola için oturum açın oturum açma kullanan destekliyorsa. Sunucu, Windows NT Sınama yanıtı desteklemiyorsa, kullanıcının kullanıcı adı ve parola sağlamak için sorgulanır. 

  Bu ilke ayarını devre dışı bırakırsanız, oturum açma ayarlanır *otomatik oturum yalnızca Intranet bölgesinde*. Bu ilke ayarı yapılandırmazsanız, oturum açma ayarlanır *istemi* kullanıcı adı ve parola.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067110)  
  
  **Varsayılan**: Anonim  
  
- **Internet Explorer Güvenilen Bölge başlatmak ve ActiveX denetimlerini betik güvenli olarak işaretlenmemiş**  
  Bu ilke ayarı, güvenli olarak işaretlenmemiş ActiveX denetimlerini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, ActiveX denetimleri, güvenilir olmayan verileri veya betikler için nesne güvenliği ayarlamadan parametreler ile yüklenir ve komut dosyalı çalıştırın. Bu ayar, güvenli ve yönetilen bölgeler dışında önerilmez. Bu ayar, başlatılır ve komut dosyası için hem güvenli hem de güvenli denetimler neden olur, betik ActiveX denetimlerini yoksayma seçeneği için güvenli olarak işaretlenmiş. Bu ilke ayarını etkinleştirin ve istemi açılır kutusunda, kullanıcıların denetimi parametrelerle yüklemeye izin verilip verilmeyeceği veya komut dosyası. Bu ilke ayarını devre dışı bırakırsanız, güvenli hale getirilemez ActiveX denetimlerini parametrelerle yüklü değil veya komut dosyası. Bu ilke ayarı yapılandırmazsanız, kullanıcıların denetimi parametrelerle yüklemeye izin verilip verilmeyeceği veya komut dosyası.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067137)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer onay sunucu sertifika iptal etme**  
  Bu ilke ayarı, Internet Explorer ın sunucu sertifikalarının iptal durumunu denetleyip denetlemeyeceğini yönetmenize olanak sağlar. Sertifikalar, gizliliği ihlal edilmiş veya artık geçerli ve bu seçenek, gizli veriler sahte veya güvenli olmayan bir siteye göndermesinin kullanıcıları korur iptal edilir. Bu ilke ayarını etkinleştirirseniz, Internet Explorer sunucu sertifikası iptal edilmiş görmek için denetler. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer sunucu sertifikası iptal edilmiş görmek için kontrol olmaz. Bu ilke ayarı yapılandırmazsanız, Internet Explorer sunucu sertifikası iptal edilmiş görmek için kontrol olmaz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067046)  
  
  **Varsayılan**: Enabled 
  
- **Internet Explorer internet bölgesi ayrıcalıklı siteleri daha az**  
  Bu ilke ayarı, bu bölgeye Web siteleri Yasak siteler gibi daha az ayrıcalıklı bölgelerdeki gidebilirsiniz yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, Web siteleri daha az ayrıcalıklı bölgelerdeki yeni pencerelerde açın veya bu bölgeye gidin. Güvenlik bölgesi ek koruma Bölge Yüksekliği güvenlik özelliği tarafından sağlanan bir güvenlik katmanı olmadan çalışır. Açılan kutusunda seçtiğiniz istemi, riskli olabilecek Gezinti gerçekleşmek üzere olan bir kullanıcı için bir uyarı verilir. Bu ilke ayarını devre dışı bırakırsanız, zararlı olabilecek gezintiler engellenir. Internet Explorer güvenlik özelliği bu bölgede bölge yükseltme özelliği denetiminden koruma tarafından belirlenen açıktır. Bu ilke ayarı yapılandırmazsanız, Web siteleri daha az ayrıcalıklı bölgelerdeki yeni pencerelerde açın veya bu bölgeye gidin.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067109)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer kısıtlı bölge dosyasını indirir.**  
  Bu ilke ayarı, Dosya indirmeleri bölgeden yüklenmesine izin verilip verilmeyeceğini yönetmenizi sağlar. Bu seçeneği neden değil dosyanın teslim edildiği bölge indirme bağlantısıyla sayfanın bölgesine göre belirlenen. Bu ilke ayarını etkinleştirirseniz, dosyaları bölgeden indirilebilir. Bu ilke ayarını devre dışı bırakırsanız, bölgeden indirilen dosyaları engellenir. Bu ilke ayarı yapılandırmazsanız bölgeden indirilen dosyaları engellenir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067038)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer internet bölgesi Authenticode ile imzalanmış .NET Framework bağımlı bileşenleri çalıştırın**  
  Bu ilke ayarı, Authenticode ile imzalanmış .NET Framework bileşenlerini Internet Explorer'dan çalışıp çalışmayacağını yönetmenizi sağlar. Bu bileşenler, bir nesne etiketi ve bir bağlantıdan başvurulan Yönetilen yürütülebilir dosyaları başvurulan yönetilen denetimleri içerir. Bu ilke ayarını etkinleştirirseniz, Internet Explorer imzalı yönetilen bileşenleri çalıştırır. Açılan kutusunda seçtiğiniz istemi, Internet Explorer imzalı yönetilen bileşenleri çalıştırılıp çalıştırılmayacağını için girmesini ister. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer imzalı yönetilen bileşenleri yürütme olmaz. Bu ilke ayarı yapılandırmazsanız, Internet Explorer imzalı yönetilen bileşenleri yürütme olmaz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067033)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer kullanıcı ActiveX denetimleri yüklenmesini engelle**  
  Bu ilke ayarı, kullanıcı başına temelinde ActiveX denetimlerini yüklenmesini önlemek sağlar. Bu ilke ayarını etkinleştirirseniz, kullanıcı başına esasına göre ActiveX denetimlerini yüklenemez. ActiveX denetimleri, devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, kullanıcı başına esasına göre yüklenebilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067058)  
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer smart screen'i Filtresi'nin yönetimini engelle**  
  Bu ilke ayarı, ziyaret ettikleri Web sitesi aracılığıyla "kimlik avı" kişisel bilgileri toplamak sahte girişimleri için bilinen veya ana bilgisayar kötü amaçlı yazılımı bildirmeye bilinen kullanıcıyı uyarır SmartScreen Filtresi'ni yönetmesini kullanıcı engeller. Bu ilke ayarını etkinleştirirseniz, kullanıcıya SmartScreen Filtresi'ni istenir değil. Filtrelere olmayan tüm Web sitesi adresleri listesi gönderilen otomatik olarak Microsoft'a kullanıcıya sormadan izin verin. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, kullanıcı ilk kez çalıştırma deneyimi sırasında SmartScreen Filtresi'ni açmak isteyip karar vermeniz istenir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067135)  
  
  **Varsayılan**: Etkinleştir  
  
- **Internet Explorer MIME algılaması güvenlik özelliği işlemleri**  
  Bu ilke ayarı, Internet Explorer MIME algılaması tek bir dosyanın daha tehlikeli bir dosya türü için engelleyecek olup olmadığını belirler. Bu ilke ayarını etkinleştirirseniz, MIME algılaması daha tehlikeli bir dosya türü için bir türde bir dosya hiçbir zaman yükseltmez. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer işlemleri daha tehlikeli bir dosya türü için bir türde bir dosya MIME algılamasının izin verir. Bu ilke ayarı yapılandırmazsanız MIME algılaması daha tehlikeli bir dosya türü için bir türde bir dosya hiçbir zaman yükseltmez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067124)  
  
  **Varsayılan**: Enabled  
  
- **İmzalı ActiveX denetimlerini Internet Explorer kısıtlı bölge yükle**  
  Bu ilke ayarı, kullanıcıların imzalanmış ActiveX denetimlerini bölgesinde sayfasından yükleyip yükleyemeyeceklerini yönetmenize olanak sağlar. Bu ilkeyi etkinleştirmek, kullanıcıların kullanıcı müdahalesi olmadan imzalı denetimleri indirebilirsiniz. Aşağı açılan kutusunda istemi seçerseniz, kullanıcıların güvenilen yayımcılar tarafından imzalanmış denetimleri indirin etkinleştirilip etkinleştirilmeyeceğini sorgulanır. Güvenilen Yayımcılar tarafından imzalanmış kod sessizce indirilir. İlke ayarını devre dışı bırakırsanız, imzalı denetimleri karşıdan yükleyemiyor. Bu ilke ayarı yapılandırmazsanız, kullanıcıların güvenilen yayımcılar tarafından imzalanmış denetimleri indirin etkinleştirilip etkinleştirilmeyeceğini sorgulanır. Güvenilen Yayımcılar tarafından imzalanmış kod sessizce indirilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067120) 
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer otomatik tamamlama**  
  Bu otomatik tamamlama özelliği, unutmayın ve kullanıcı adları ve parolalar formlarında önerin. Bu ayarı etkinleştirirseniz, kullanıcı "kullanıcı adı ve parolaların" değiştiremez ya da "parolaları kaydetmek için sor". Kullanıcı adları ve parolaların için Otomatik Tamamlama özelliği etkinleştirilir. "Parola kaydetmemi iste" seçip seçmemeye karar verin gerekir. Bu ayar devre dışı bırakırsanız kullanıcı "kullanıcı adı ve parolaların" değiştiremez ya da "parolaları kaydetmek için sor". Kullanıcı adları ve parolaların için Otomatik Tamamlama özelliği kapalıdır. Kullanıcı parolaları kaydedilmeyeceğinin sorulması için de kapatılamaz. Bu ayarı yapılandırmazsanız, kullanıcının tam kullanıcı adı ve parola form ve parolaları kaydetme istemi seçeneği otomatik kapatma özgürlüğü sahip. Bu seçeneği görüntülemek için kullanıcıların Internet Seçenekleri iletişim kutusunu açın, İçindekiler sekmesini tıklatın ve ayarlar düğmesine tıklayın.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067122)  
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer internet bölgesi çalıştırmak VBscript izin ver**  
  Bu ilke ayarı, VBScript belirli Internet Explorer bölgeleri sayfalarında çalıştırılıp çalıştırılmayacağını karar vermenize olanak tanır. Şu seçenekler mevcuttur: 
  - *Etkinleştirme* -herhangi bir etkileşim olmadan, belirli bölgelerde sayfalarında VBScript çalıştırır. 
  - *Komut İstemi* -çalışanlar istenir bölgede çalıştırılacak VBScript izin verilip verilmeyeceğini. 
  - *Devre dışı* -VBScript bölgede çalışmasını engellenir. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, belirtilen bölgede herhangi bir etkileşim olmadan bir VBScript çalıştırır.    

  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067119)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer'ın kısıtlı bölgede tdc ActiveX denetimlerini kullanmak için etki alanları yalnızca onaylanmış**  
  Bu ilke ayarı, kullanıcı Web siteleri TDC ActiveX denetimini çalışıp çalışamayacağını denetler. Bu ilke ayarını etkinleştirirseniz, bu bölgedeki sitelerinden TDC ActiveX denetimini çalışmaz. Bu ilke ayarını devre dışı bırakırsanız, bu bölgedeki tüm sitelerden TDC ActiveX denetimi çalıştırılır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067032)  
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer Güvenilen Bölge ActiveX denetimleri karşı kötü amaçlı yazılımdan koruma çalışmaz**  
  Bu ilke ayarı, Internet Explorer karşı sayfalarında güvenli iseler denetlemek için ActiveX denetimleri, kötü amaçlı yazılımdan koruma programları çalışıp çalışmayacağını belirler. Bu ilke ayarını etkinleştirirseniz, Internet Explorer ActiveX denetiminin bir örneğini oluşturmak güvenli olup olmadığını görmek için kötü amaçlı yazılımdan koruma programınızı denetleyin olmaz. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer ActiveX denetiminin bir örneğini oluşturmak güvenli olup olmadığını görmek için kötü amaçlı yazılımdan koruma programı her zaman denetler. Bu ilke ayarı yapılandırmazsanız, Internet Explorer ActiveX denetiminin bir örneğini oluşturmak güvenli olup olmadığını görmek için kötü amaçlı yazılımdan koruma programı her zaman denetler. Kullanıcılar bu davranışı açıp kapatabilir, Internet Explorer güvenlik ayarlarını kullanarak kapatabilirsiniz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067115)  
  
  **Varsayılan**: Devre dışı 
  
- **Internet Explorer yerel makine bölge java izinleri**  
  Bu ilke ayarı, Java uygulamaları için izinleri yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz, Seçenekler açılır kutusundan seçebilirsiniz. Özel denetim izinlerini ayarlar için ayrı ayrı. Düşük güvenilirlik, uygulamaların tüm işlemleri sağlar. Orta düzey güvenilirlik (bir alanda bellek görüşmesi yapamaz program dışında), kendi sanal uygulamaların artı boş alan (istemci bilgisayarda bir güvenli depolama alanı) ve kullanıcı tarafından denetlenen dosya g/ç gibi özellikler sağlar. Yüksek güvenilirlik, korumalı alanında çalışmasını sağlar. Java uygulamaları çalışmasını önlemek için devre dışı bırakın. Bu ilke ayarını devre dışı bırakırsanız, Java uygulamalarını çalıştıramazsınız. Bu ilke ayarı yapılandırmazsanız, Java Orta çalışamaz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067113)  
  
  **Varsayılan**: Java devre dışı bırak 
  
- **Intranet Bölgesi Internet Explorer kötü amaçlı yazılımdan koruma karşı ActiveX denetimlerini çalıştırmaz**  
  Bu ilke ayarı, Internet Explorer karşı sayfalarında güvenli iseler denetlemek için ActiveX denetimleri, kötü amaçlı yazılımdan koruma programları çalışıp çalışmayacağını belirler. Bu ilke ayarını etkinleştirirseniz, Internet Explorer ActiveX denetiminin bir örneğini oluşturmak güvenli olup olmadığını görmek için kötü amaçlı yazılımdan koruma programınızı denetleyin olmaz. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer ActiveX denetiminin bir örneğini oluşturmak güvenli olup olmadığını görmek için kötü amaçlı yazılımdan koruma programı her zaman denetler. Bu ilke ayarı yapılandırmazsanız, Internet Explorer ActiveX denetiminin bir örneğini oluşturmak güvenli olup olmadığını görmek için kötü amaçlı yazılımdan koruma programınızı denetleyin olmaz. Kullanıcılar bu davranışı açıp kapatabilir, Internet Explorer güvenlik ayarlarını kullanarak kapatabilirsiniz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067138)  
  
  **Varsayılan**: Devre dışı  

- **Internet Explorer'ın kısıtlı bölge kod parçacıkları**  
  Bu ilke ayarı, kullanıcı kod parçacıklarını çalıştırıp çalıştıramayacağını yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz, kullanıcı kod parçacıklarını çalıştırabilirsiniz. Bu ilke ayarını devre dışı bırakırsanız, kullanıcı kod parçacıklarını çalıştıramazsınız. Bu ilke ayarı yapılandırmazsanız, kullanıcı etkinleştirebilir veya kod parçacıklarını devre dışı bırakın.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067112)  
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer işlemleri bildirim çubuğu**  
  Bu ilke ayarı dosyası veya kod yüklemeleri kısıtlandığında Internet Explorer işlemleri için bildirim çubuğu görüntülenmez yönetmenizi sağlar. Varsayılan olarak, Internet Explorer işlemleri için bildirim çubuğu görüntülenir. Bu ilke ayarını etkinleştirirseniz, Internet Explorer işlemleri için bildirim çubuğu görüntüler. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer işlemleri için bildirim çubuğu görüntülenmez. Bu ilke ayarı yapılandırmazsanız, bildirim çubuğu için Internet Explorer işlemleri görüntülemez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067139)  
  
  **Varsayılan**: Enabled  
  
- **İmzalı ActiveX denetimlerini Internet Explorer internet bölgesi yükle**  
  Bu ilke ayarı, kullanıcıların imzalanmış ActiveX denetimlerini bölgesinde sayfasından yükleyip yükleyemeyeceklerini yönetmenize olanak sağlar. Bu ilkeyi etkinleştirmek, kullanıcıların kullanıcı müdahalesi olmadan imzalı denetimleri indirebilirsiniz. Aşağı açılan kutusunda istemi seçerseniz, kullanıcıların güvenilen yayımcılar tarafından imzalanmış denetimleri indirin etkinleştirilip etkinleştirilmeyeceğini sorgulanır. Güvenilen Yayımcılar tarafından imzalanmış kod sessizce indirilir. İlke ayarını devre dışı bırakırsanız, imzalı denetimleri karşıdan yükleyemiyor. Bu ilke ayarı yapılandırmazsanız, kullanıcıların güvenilen yayımcılar tarafından imzalanmış denetimleri indirin etkinleştirilip etkinleştirilmeyeceğini sorgulanır. Güvenilen Yayımcılar tarafından imzalanmış kod sessizce indirilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067064)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer kısıtlı bölge Akıllı Ekran**  
  Bu ilke kötü amaçlı içerik için bu bölgedeki sayfalar SmartScreen Filtresi tarar olmadığını ayarı denetler. Bu ilke ayarını etkinleştirirseniz, SmartScreen Filtresi, kötü amaçlı içerik için bu bölgedeki sayfalar tarar. Bu ilke ayarını devre dışı bırakırsanız, kötü amaçlı içerik için bu bölgedeki sayfalar SmartScreen Filtresi taramaz. Bu ilke ayarı yapılandırmazsanız, kullanıcıya SmartScreen Filtresi'ni kötü amaçlı içerik için bu bölgedeki sayfalar tarayıp taramayacağını seçebilirsiniz. Not: Internet Explorer 7'de, bu ilke ayarı, kimlik avı filtre kötü amaçlı içerik için bu bölgedeki sayfalar tarayıp taramayacağını denetler.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067034)  
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer kaldırmayı Çalıştır eski ActiveX denetimleri için bu saat düğmesi**  
  Bu ilke ayarı, kullanıcıların görmesini "Bu kez çalıştır" düğmesi ve Internet Explorer'ın belirli eski ActiveX denetimlerini çalışmasını durdurmak sağlar. Bu ilke ayarını etkinleştirirseniz, kullanıcılar Internet Explorer güncel olmayan bir ActiveX denetimi engellediğinde görüntülenen uyarı iletisi "Bu kez çalıştır" düğmesi görmez. Devre dışı bırakmak veya bu ilke ayarı yapılandırmazsanız, kullanıcıların Internet Explorer güncel olmayan bir ActiveX denetimi engellediğinde görüntülenen uyarı iletisi "Bu kez çalıştır" düğmesi görürsünüz. Bu düğmeye tıklandığında, güncel olmayan bir ActiveX denetimi bir kez çalıştır kullanıcı sağlar. Daha fazla bilgi için "Eski ActiveX denetimlerini" Internet Explorer TechNet kitaplığında bkz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067123)  
  
  **Varsayılan**: Enabled 
  
- **Internet Explorer Internet bölgesi başlatma uygulamalarına ve bir iframe içinde dosyaları**  
  Bu ilke ayarı, uygulamaları çalıştırabilir ve dosyaları, HTML sayfaları bu bölgedeki bir IFRAME başvurusuna şuradan indirilebilir yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, kullanıcılar uygulamalarını çalıştırmak ve kullanıcı müdahalesi olmadan bu bölgedeki sayfalarında IFRAMES dosyaları indirin. Açılan kutusunda seçtiğiniz istemi, kullanıcılara uygulamalarını çalıştırmak ve bu bölgedeki sayfalarında IFRAMES dosyaları karşıdan seçmeleri istenir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcıların uygulamaları çalıştırmaya ve bu bölgedeki sayfalarında IFRAMES dosyaları indirme engellenir. Bu ilke ayarı yapılandırmazsanız, kullanıcıların uygulamaları çalıştırabilir ve bu bölgedeki sayfalarında IFRAMES dosyaları indirmek seçmeleri istenir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067020)  
  
  **Varsayılan**: Devre Dışı Bırak 
  
- **Internet Explorer kısıtlı bölge, farklı etki alanlarında windows ve çerçeveleri gidin**  
  Bu ilke ayarı kaynak ve hedef farklı windows olduğunda içerik bir etki alanından farklı bir etki alanına sürükleyerek seçenekleri ayarlamanıza olanak sağlar. Bu ilke ayarını etkinleştirin ve Etkinleştir'i tıklatın, kaynak ve hedef farklı windows olduğunda kullanıcıların içeriği bir etki alanından farklı bir etki alanına sürükleyebilirsiniz. Kullanıcılar, bu ayarı değiştiremezsiniz. Bu ilke ayarını etkinleştirin ve devre dışı bırak'a tıklayın, hem kaynak hem de hedef farklı windows olduğunda kullanıcıların içeriği bir etki alanından farklı bir etki alanına sürükleyemezsiniz. Kullanıcılar, bu ayarı değiştiremezsiniz. Bu ilke ayarını devre dışı bırakır veya, yapılandırmayın olduğunda kaynak ve hedef farklı windows Internet Explorer 10'da, kullanıcıların içeriği bir etki alanından farklı bir etki alanına sürükleyemezsiniz. Kullanıcıların Internet Seçenekleri iletişim kutusunda Bu ayarı değiştirebilirsiniz. Bu ilke devre dışı bırakır veya, yapılandırmayın olduğunda kaynak ve hedef farklı windows Internet Explorer 9 ve önceki sürümlerinde, kullanıcıların içeriği bir etki alanından farklı bir etki alanına sürükleyebilirsiniz. Kullanıcılar, bu ayarı değiştiremezsiniz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067050)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer internet bölgesi Akıllı Ekran**  
  Bu ilke kötü amaçlı içerik için bu bölgedeki sayfalar SmartScreen Filtresi tarar olmadığını ayarı denetler. Bu ilke ayarını etkinleştirirseniz, SmartScreen Filtresi, kötü amaçlı içerik için bu bölgedeki sayfalar tarar. Bu ilke ayarını devre dışı bırakırsanız, kötü amaçlı içerik için bu bölgedeki sayfalar SmartScreen Filtresi taramaz. Bu ilke ayarı yapılandırmazsanız, kullanıcıya SmartScreen Filtresi'ni kötü amaçlı içerik için bu bölgedeki sayfalar tarayıp taramayacağını seçebilirsiniz. Not: Internet Explorer 7'de, bu ilke ayarı, kimlik avı filtre kötü amaçlı içerik için bu bölgedeki sayfalar tarayıp taramayacağını denetler.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067047)  
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer Güvenilen Bölge java izinleri kilitli**  
  Bu ilke ayarı, Java uygulamaları için izinleri yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz, Seçenekler açılır kutusundan seçebilirsiniz. Özel denetim izinlerini ayarlar için ayrı ayrı. Düşük güvenilirlik, uygulamaların tüm işlemleri sağlar. Orta düzey güvenilirlik (bir alanda bellek görüşmesi yapamaz program dışında), kendi sanal uygulamaların artı boş alan (istemci bilgisayarda bir güvenli depolama alanı) ve kullanıcı tarafından denetlenen dosya g/ç gibi özellikler sağlar. Yüksek güvenilirlik, korumalı alanında çalışmasını sağlar. Java uygulamaları çalışmasını önlemek için devre dışı bırakın. Bu ilke ayarını devre dışı bırakırsanız, Java uygulamalarını çalıştıramazsınız. Bu ilke ayarı yapılandırmazsanız, Java uygulamalarını devre dışı bırakıldı.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067142)  
  
  
  **Varsayılan**: Java devre dışı bırak 
  
- **Internet Explorer indirilen programları imzaları denetle**  
  Bu ilke ayarı, Internet Explorer (imzalı yazılım yayımcısını tanımlar ve bu değiştirilmediğini veya üzerinde oynama doğrular) dijital imzalar için denetleyip denetlemeyeceğini yürütülebilir programlar indirmeden önce kullanıcı bilgisayarları üzerinde yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz, Internet Explorer yürütülebilir programlar dijital imzalarını denetler ve kullanıcının bilgisayarına indirmeden önce kimliklerini görüntülemez. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer yürütülebilir programlar dijital imzaları denetleme olmaz veya kullanıcının bilgisayarına indirmeden önce kimliklerini görüntülemez. Bu ilke yapılandırmazsanız, Internet Explorer yürütülebilir programlar dijital imzaları denetleme olmaz veya kullanıcının bilgisayarına indirmeden önce kimliklerini görüntülemez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067051)  
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer web tarayıcı denetimi bölge kodlamasını kısıtlı**  
  Bu ilke ayarı, bir sayfa komut dosyası aracılığıyla gömülü WebBrowser denetimi denetimi olup olmadığını belirler. Bu ilke ayarını etkinleştirirseniz, WebBrowser denetimi betik erişime izin. Bu ilke ayarını devre dışı bırakırsanız, WebBrowser denetimi betik erişmesine izin verilmiyor. Bu ilke ayarı yapılandırmazsanız, kullanıcı etkinleştirebilir veya betik erişimi WebBrowser denetimi devre dışı bırakın. Varsayılan olarak, yalnızca yerel makine ve Intranet bölgeleri WebBrowser denetimi betik erişime izin.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067098)  
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer kısıtlı bölge arası site komut dosyası filtresi**  
  Bu ilke, siteler arası betik (XSS) filtre algılayın ve bu bölgedeki Web siteleri içine siteler arası betik eklemelerini engelle denetler. Bu ilke ayarını etkinleştirirseniz, bu bölgedeki sitelerden XSS filtre açıktır ve XSS filtre siteler arası betik eklemelerini engellemeye çalışır. Bu ilke ayarını devre dışı bırakırsanız, bu bölgedeki sitelerden XSS filtre kapalıdır ve Internet Explorer, siteler arası betik eklemelerini izin verir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067178)  
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer kısıtlı bölge ikili ve komut dosyası davranışları**  
  Bu ilke ayarı, dinamik ikili ve betik davranışları yönetmenize olanak sağlar: HTML öğeleri bağlı oldukları için belirli işlevi kapsülleyen bileşenler. Bu ilke ayarını etkinleştirirseniz, ikili ve betik davranışları kullanılabilir. Yönetici aşağı açılan kutusunda onaylı seçerseniz, yalnızca yönetici tarafından onaylanan davranışları ikili davranışları güvenlik kısıtlama ilkesi altında listelenen kullanılabilir. Bu ilke ayarını devre dışı bırakırsanız, uygulamaları özel bir güvenlik yöneticisi uyguladıysanız sürece, ikili ve betik davranışları mevcut değildir. Bu ilke ayarı yapılandırmazsanız, uygulamaları özel bir güvenlik yöneticisi uyguladıysanız sürece, ikili ve betik davranışları mevcut değildir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067224)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer güvenlik ayarları denetimi**  
  Bu ilke ayarı, riske Internet Explorer ayarlarını belirlemek için Internet Explorer güvenlik ayarlarını denetleyen güvenlik ayarlarını denetleme özelliği kapatır. Bu ilke ayarını etkinleştirirseniz, bu özellik devre dışıdır. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, özelliği etkinleştirilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067182)  
  
  **Varsayılan**: Enabled  
  
- **Güvenli olmayan dosyalar için Internet Explorer internet bölgesi güvenlik uyarısı**  
  "Dosya – Güvenlik Uyarısı açın" iletisi görüntülenirse, kullanıcı yürütülebilir dosyaları veya diğer olmayabilecek dosyaları (örneğin dosya Gezgini'ni kullanarak bir intranet dosya paylaşımından) açmayı denediğinde bu ilke ayarı denetler. Bu ilke ayarını etkinleştirin ve etkinleştirmek için açılan kutudan ayarlayın, bu dosyalar olmadan bir güvenlik uyarısı açın. Açılan kutunun istemine ayarlarsanız, dosyaları açmadan önce bir güvenlik uyarısı görüntülenir. Bu ilke ayarını devre dışı bırakırsanız, bu dosyalar açmayın. Bu ilke ayarı yapılandırmazsanız, kullanıcı, bilgisayar bu dosyaları nasıl işlediğini yapılandırabilirsiniz. Varsayılan olarak, bu dosyalar Intranet ve yerel bilgisayar bölgeleri, etkin Yasak bölgesinde engellenen ve Internet ve güvenilen bölgelerde isteyecek şekilde ayarlayın.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067204)  
  
  **Varsayılan**: İstem  
  
- **Internet Explorer intranet bölgesi java izinleri**  
  Bu ilke ayarı, Java uygulamaları için izinleri yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz, Seçenekler açılır kutusundan seçebilirsiniz. Özel denetim izinlerini ayarlar için ayrı ayrı. Düşük güvenilirlik, uygulamaların tüm işlemleri sağlar. Orta düzey güvenilirlik (bir alanda bellek görüşmesi yapamaz program dışında), kendi sanal uygulamaların artı boş alan (istemci bilgisayarda bir güvenli depolama alanı) ve kullanıcı tarafından denetlenen dosya g/ç gibi özellikler sağlar. Yüksek güvenilirlik, korumalı alanında çalışmasını sağlar. Java uygulamaları çalışmasını önlemek için devre dışı bırakın. Bu ilke ayarını devre dışı bırakırsanız, Java uygulamalarını çalıştıramazsınız. Bu ilke ayarı yapılandırmazsanız, Java Orta çalışamaz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067206)  
  
  **Varsayılan**: Yüksek güvenilirlik 
  
- **Internet Explorer eski blok ActiveX denetimleri**   
  Bu ilke ayarı, Internet Explorer blokları belirli ActiveX denetimlerini eski olup olmadığını belirler. Güncel olmayan bir ActiveX denetimleri, Intranet bölgesinde hiçbir zaman engellenir. Bu ilke ayarını etkinleştirirseniz, Internet Explorer eski ActiveX denetimlerini engelleme durdurur. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, Internet Explorer belirli eski ActiveX denetimlerini engelleyecek şekilde devam eder. Daha fazla bilgi için "Eski ActiveX denetimlerini" Internet Explorer TechNet kitaplığında bkz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067203)  
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer'ın kısıtlı bölge açılır pencere engelleyicisi**  
  Bu ilke ayarı, istenmeyen açılır pencerelerin görüntülenip görüntülenmeyeceğini yönetmenize olanak sağlar. Son kullanıcı bağlantıyı tıklattığında açılan açılan pencereler engellenmez. Bu ilke ayarını etkinleştirirseniz, en istenmeyen açılır pencereleri görüntülenmesi engellenir. Bu ilke ayarını devre dışı bırakırsanız, açılır pencereleri görünmesini engelleyen değildir. Bu ilke ayarı yapılandırmazsanız en istenmeyen açılır pencereleri görüntülenmesi engellenir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067180)  
  
  **Varsayılan**: Etkinleştir  
  
- **Internet Explorer MK protokolü güvenlik kısıtlaması işlemleri**  
  MK protokolü güvenlik kısıtlaması ilke ayarı, MK protokolü engelleyerek saldırı yüzey alanını azaltır. MK protokolü üzerinde bulunan kaynaklara başarısız olur. Bu ilke ayarını etkinleştirirseniz, MK protokolü, dosya Gezgini ve Internet Explorer'da engellenir ve MK protokolü üzerinde bulunan kaynaklara başarısız olur. Bu ilke ayarını devre dışı bırakırsanız, MK protokolü API uygulamaları kullanabilir. MK protokolü üzerinde bulunan kaynaklara dosya Gezgini ve Internet Explorer işlemleri için çalışır. Bu ilke ayarı yapılandırmazsanız, MK protokolü, dosya Gezgini ve Internet Explorer'da engellenir ve MK protokolü üzerinde bulunan kaynaklara başarısız olur.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067179)  
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer Güvenilen Bölge java izinleri**   
  Bu ilke ayarı, Java uygulamaları için izinleri yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz, Seçenekler açılır kutusundan seçebilirsiniz. Özel denetim izinlerini ayarlar için ayrı ayrı. Düşük güvenilirlik, uygulamaların tüm işlemleri sağlar. Orta düzey güvenilirlik (bir alanda bellek görüşmesi yapamaz program dışında), kendi sanal uygulamaların artı boş alan (istemci bilgisayarda bir güvenli depolama alanı) ve kullanıcı tarafından denetlenen dosya g/ç gibi özellikler sağlar. Yüksek güvenilirlik, korumalı alanında çalışmasını sağlar. Java uygulamaları çalışmasını önlemek için devre dışı bırakın. Bu ilke ayarını devre dışı bırakırsanız, Java uygulamalarını çalıştıramazsınız. Bu ilke ayarı yapılandırmazsanız, düşük güvenilirlik izni ayarlanır.  
    [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067200)  
  
  **Varsayılan**: Yüksek güvenilirlik  
  
- **Internet Explorer bölge java uygulamaları için komut dosyası kısıtlı**  
  Bu ilke ayarı, uygulamaları bölge içindeki komut dosyaları için sunulan yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, komut dosyaları otomatik olarak kullanıcı müdahalesi olmadan uygulamalara erişebilir. Açılan kutusunda seçtiğiniz istemi, kullanıcılar uygulamalara erişmek betiklere izin vermek isteyip istemediğinizi seçin için sorgulanır. Bu ilke ayarını devre dışı bırakırsanız, betikleri, uygulamalara erişimi engellenir. Bu ilke ayarı yapılandırmazsanız, betikleri, uygulamalara erişimi engellenir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067202)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer kısıtlı bölge java izinleri kilitli**   
  Bu ilke ayarı, Java uygulamaları için izinleri yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz, Seçenekler açılır kutusundan seçebilirsiniz. Özel denetim izinlerini ayarlar için ayrı ayrı. Düşük güvenilirlik, uygulamaların tüm işlemleri sağlar. Orta düzey güvenilirlik (bir alanda bellek görüşmesi yapamaz program dışında), kendi sanal uygulamaların artı boş alan (istemci bilgisayarda bir güvenli depolama alanı) ve kullanıcı tarafından denetlenen dosya g/ç gibi özellikler sağlar. Yüksek güvenilirlik, korumalı alanında çalışmasını sağlar. Java uygulamaları çalışmasını önlemek için devre dışı bırakın. Bu ilke ayarını devre dışı bırakırsanız, Java uygulamalarını çalıştıramazsınız. Bu ilke ayarı yapılandırmazsanız, Java uygulamalarını devre dışı bırakıldı.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067181)  
  
  **Varsayılan**: Java devre dışı bırak 
  
- **Internet Explorer internet bölgesi izin ActiveX denetimlerini kullanmak için etki alanları yalnızca onaylanmış**   
  Bu ilke ayarı, Web siteleri dışında ActiveX denetimini yüklü Web sitesini çalıştırmak ActiveX denetimlerini izin vermek için kullanıcı istenirse denetler. Bu ilke ayarını etkinleştirirseniz, ActiveX denetimleri, bu bölgedeki sitelerinden çalıştırmadan önce kullanıcıya sorulur. Kullanıcı, denetimlerin geçerli siteden veya tüm sitelerden çalışmasına izin vermeyi seçebilirsiniz. Bu ilke ayarını devre dışı bırakırsanız, kullanıcı başına site ActiveX istemini görmez ve bu bölgedeki tüm sitelerden ActiveX denetimlerini çalıştırabilirsiniz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067091)  
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer dahil tüm ağ yolları**  
  Internet Explorer tüm ağ yollarını içerir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067090)  
  
  **Varsayılan**: Devre dışı 
  
- **Internet Explorer internet bölgesi korumalı mod**  
  Bu ilke ayarı, korumalı modunu açmak sağlar. Korumalı modu, Internet Explorer, Internet Explorer için kayıt defteri ve dosya sistemine yazabilirsiniz konumları azaltarak kötü amaçla kullanılan güvenlik açıklarına karşı korumaya yardımcı olur. Bu ilke ayarını etkinleştirirseniz, korumalı mod etkinleştirilir. Kullanıcı, korumalı modunu devre dışı bırakmak olamaz. Bu ilke ayarını etkinleştirirseniz, korumalı mod kapalıdır. Kullanıcı, korumalı modu kapatamazsınız. Bu ilke ayarı yapılandırmazsanız, açın veya korumalı modunu kapatın.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067171)  
  
  **Varsayılan**: Etkinleştir 
  
- **İnternet bölgesi Internet Explorer'ı başlatın ve ActiveX denetimlerini betik güvenli olarak işaretlenmemiş**  
  Bu ilke ayarı, güvenli olarak işaretlenmemiş ActiveX denetimlerini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, ActiveX denetimleri, güvenilir olmayan verileri veya betikler için nesne güvenliği ayarlamadan parametreler ile yüklenir ve komut dosyalı çalıştırın. Bu ayar, güvenli ve yönetilen bölgeler dışında önerilmez. Bu ayar, başlatılır ve komut dosyası için hem güvenli hem de güvenli denetimler neden olur, betik ActiveX denetimlerini yoksayma seçeneği için güvenli olarak işaretlenmiş. Bu ilke ayarını etkinleştirin ve istemi açılır kutusunda, kullanıcıların denetimi parametrelerle yüklemeye izin verilip verilmeyeceği veya komut dosyası. Bu ilke ayarını devre dışı bırakırsanız, güvenli hale getirilemez ActiveX denetimlerini parametrelerle yüklü değil veya komut dosyası. Bu ilke ayarı yapılandırmazsanız, güvenli hale getirilemez ActiveX denetimlerini parametrelerle yüklü değil veya komut dosyası.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067170)  
  
  **Varsayılan**: Devre Dışı Bırak 
  
- **Internet Explorer kısıtlı bölge akıllı ekran aşağıya kilitli**   
  Bu ilke kötü amaçlı içerik için bu bölgedeki sayfalar SmartScreen Filtresi tarar olmadığını ayarı denetler. Bu ilke ayarını etkinleştirirseniz, SmartScreen Filtresi, kötü amaçlı içerik için bu bölgedeki sayfalar tarar. Bu ilke ayarını devre dışı bırakırsanız, kötü amaçlı içerik için bu bölgedeki sayfalar SmartScreen Filtresi taramaz. Bu ilke ayarı yapılandırmazsanız, kullanıcıya SmartScreen Filtresi'ni kötü amaçlı içerik için bu bölgedeki sayfalar tarayıp taramayacağını seçebilirsiniz. Not: Internet Explorer 7'de, bu ilke ayarı, kimlik avı filtre kötü amaçlı içerik için bu bölgedeki sayfalar tarayıp taramayacağını denetler.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067092)  
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer kilitlenmesi algılama**  
  Bu ilke ayarı, eklenti Yönetimi kilitlenme algılaması özelliği yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, Internet Explorer'da bir kilitlenme Windows XP Professional Service Pack 1 ve önceki sürümlerinde, yani bulunan davranışı sergiler Windows hata bildirimi çağırmak için. Windows hata bildirimi için tüm ilke ayarları uygulanmaya devam eder. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, eklenti yönetimi için kilitlenme algılaması özelliği çalışır durumdadır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067094)  
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer internet bölgesi java izinleri**  
  Bu ilke ayarı, Java uygulamaları için izinleri yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz, Seçenekler açılır kutusundan seçebilirsiniz. Özel denetim izinlerini ayarlar için ayrı ayrı. Düşük güvenilirlik, uygulamaların tüm işlemleri sağlar. Orta düzey güvenilirlik (bir alanda bellek görüşmesi yapamaz program dışında), kendi sanal uygulamaların artı boş alan (istemci bilgisayarda bir güvenli depolama alanı) ve kullanıcı tarafından denetlenen dosya g/ç gibi özellikler sağlar. Yüksek güvenilirlik, korumalı alanında çalışmasını sağlar. Java uygulamaları çalışmasını önlemek için devre dışı bırakın. Bu ilke ayarını devre dışı bırakırsanız, Java uygulamalarını çalıştıramazsınız. Bu ilke ayarı yapılandırmazsanız izni yüksek güvenilirlik olarak ayarlanır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067174)  
  
  **Varsayılan**: Java devre dışı bırak  
  
- **Internet Explorer'ın kısıtlı bölge etkin komut dosyası**  
  Bu ilke ayarı, kod sayfalarında bölgesinde çalıştırılıp çalıştırılmayacağını yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, kod sayfalarında bölgede otomatik olarak çalıştırabilirsiniz. Açılan kutusunda seçtiğiniz istemi, kullanıcı kodu çalıştırmak için bölge sayfalarında izin verip vermeyeceklerini sorgulanır. Şirket bu ilke ayarı, kod devre dışı bırakırsanız bölgedeki sayfalar çalışması engellenir. Bu ilke ayarı yapılandırmazsanız, kod sayfalarında bölgesinde çalışması engellenir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067172)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer internet bölgesi oturum açma seçenekleri**  
  Bu ilke ayarı, oturum açma seçenekleri ayarlarını yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz, aşağıdaki oturum açma seçenekleri arasından seçim yapabilirsiniz. Anonim oturum açma devre dışı bırakma HTTP kimlik doğrulama ve kullanım Konuk hesap için yalnızca ortak Internet dosya sistemi (CIFS) protokolü. Kullanıcı adı ve parola sorgusu kullanıcıları için kullanıcı kimliklerini ve parolaları sor. Bir Kullanıcı sorgulandıktan sonra bu değerleri sessizce oturumunun kalanı için kullanılabilir. Yalnızca sorgu kullanıcılar için kullanıcı kimliklerini ve parolaları diğer bölgelerdeki Intranet bölgesinde otomatik oturum açma. Bir Kullanıcı sorgulandıktan sonra bu değerleri sessizce oturumunun geri kalanı için kullanılabilir. Windows NT Sınama yanıtı (NTLM kimlik doğrulaması olarak da bilinir) kullanarak oturum aç'ı denemek için otomatik oturum geçerli kullanıcı adı ve parolayla. Sunucu, Windows NT Sınama yanıtı, oturum açma kullanan ağ kullanıcı adını ve parolasını oturum destekliyorsa. Windows NT Sınama yanıtı sunucunun desteklemiyorsa, kullanıcının kullanıcı adı ve parola sağlamak için sorgulanır. Bu ilke ayarını devre dışı bırakırsanız, oturum açma için otomatik günlük yalnızca Intranet bölgesinde ayarlanır. Bu ilke ayarı yapılandırmazsanız, oturum açma için otomatik oturum ayarlamak da Intranet bölgesinde.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067194)  
  
  **Varsayılan**: İstem  
  
- **Internet Explorer kısıtlı bölge vbscript çalışmasına izin ver**   
  Bu ilke ayarı, Internet Explorer'da belirtilen bölgeden sayfalarında VBScript çalıştırılıp çalıştırılmayacağını yönetmenizi sağlar. VBScript, açılan kutuya Etkinleştir'i seçtiyseniz, kullanıcı müdahalesi olmadan çalıştırabilirsiniz. Aşağı açılan kutusunda seçtiğiniz istemi, kullanıcıların VBScript çalışmasına izin verilip verilmeyeceğini seçmeniz istenir. Aşağı açılan kutuya devre dışı bırak'ı seçtiyseniz, VBScript çalışması engellenir. Yapılandırma görmüyorsanız veya bu ilke ayarını devre dışı VBScript çalışması engellenir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067173)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer internet bölgesi arasında windows farklı etki alanlarından içerik sürükleyin**  
  Bu ilke ayarı kaynak ve hedef farklı windows olduğunda içerik bir etki alanından farklı bir etki alanına sürükleyerek seçenekleri ayarlamanıza olanak sağlar. Bu ilke ayarını etkinleştirin ve Etkinleştir'i tıklatın, kaynak ve hedef farklı windows olduğunda kullanıcıların içeriği bir etki alanından farklı bir etki alanına sürükleyebilirsiniz. Kullanıcılar, bu ayarı değiştiremezsiniz. Bu ilke ayarını etkinleştirin ve devre dışı bırak'a tıklayın, hem kaynak hem de hedef farklı windows olduğunda kullanıcıların içeriği bir etki alanından farklı bir etki alanına sürükleyemezsiniz. Kullanıcılar, bu ayarı değiştiremezsiniz. Bu ilke ayarını devre dışı bırakır veya, yapılandırmayın olduğunda kaynak ve hedef farklı windows Internet Explorer 10'da, kullanıcıların içeriği bir etki alanından farklı bir etki alanına sürükleyemezsiniz. Kullanıcıların Internet Seçenekleri iletişim kutusunda Bu ayarı değiştirebilirsiniz. Bu ilke devre dışı bırakır veya, yapılandırmayın olduğunda kaynak ve hedef farklı windows Internet Explorer 9 ve önceki sürümlerinde, kullanıcıların içeriği bir etki alanından farklı bir etki alanına sürükleyebilirsiniz. Kullanıcılar, bu ayarı değiştiremezsiniz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067093)  
  
  **Varsayılan**: Devre dışı 
  
- **Intranet Bölgesi Internet Explorer'ı başlatın ve ActiveX denetimlerini betik güvenli olarak işaretlenmemiş**  
  Bu ilke ayarı, güvenli olarak işaretlenmemiş ActiveX denetimlerini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, ActiveX denetimleri, güvenilir olmayan verileri veya betikler için nesne güvenliği ayarlamadan parametreler ile yüklenir ve komut dosyalı çalıştırın. Bu ayar, güvenli ve yönetilen bölgeler dışında önerilmez. Bu ayar, başlatılır ve komut dosyası için hem güvenli hem de güvenli denetimler neden olur, betik ActiveX denetimlerini yoksayma seçeneği için güvenli olarak işaretlenmiş. Bu ilke ayarını etkinleştirin ve istemi açılır kutusunda, kullanıcıların denetimi parametrelerle yüklemeye izin verilip verilmeyeceği veya komut dosyası. Bu ilke ayarını devre dışı bırakırsanız, güvenli hale getirilemez ActiveX denetimlerini parametrelerle yüklü değil veya komut dosyası. Bu ilke ayarı yapılandırmazsanız, güvenli hale getirilemez ActiveX denetimlerini parametrelerle yüklü değil veya komut dosyası.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067175)  
  
  **Varsayılan**: Devre Dışı Bırak 
  
- **Internet Explorer indirme kasaları**  
  Bu ilke ayarı, kullanıcının bilgisayarına bir akışı'ndan indirilen kasaları (dosya ekleri) sahip kullanıcı engeller. Bu ilke ayarını etkinleştirirseniz, kullanıcı bir akışa özellik sayfası Motoru'nu indirmek için akış eşitleme altyapısı ayarlanamaz. Bir geliştirici, akış API'leri aracılığıyla indirme ayarı değiştiremezsiniz. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, kullanıcı bir akışa özellik sayfası Motoru'nu indirmek için akış eşitleme altyapısı ayarlayabilirsiniz. Bir geliştirici akış API'leri aracılığıyla indirme ayarını değiştirebilirsiniz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067245)  
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer kısıtlı bölge İmzalanmamış ActiveX denetimlerini indirin**  
  Bu ilke ayarı, kullanıcıların İmzasız ActiveX denetimlerini bölgesinden yükleyip yükleyemeyeceklerini yönetmenize olanak sağlar. Bu tür kod, özellikle güvenilmeyen bir bölgeden Bekletmeden çıkarken zararlı olabilir. Bu ilke ayarını etkinleştirirseniz, kullanıcıların kullanıcı müdahalesi olmadan imzasız denetimlerini çalıştırabilirsiniz. Açılan kutuda istemi seçerseniz, kullanıcıların imzasız denetiminin çalışmasına izin verip vermeyeceklerini sorgulanır. Bu ilke ayarını devre dışı bırakırsanız, kullanıcıların imzasız denetimleri çalıştıramaz. Bu ilke ayarı yapılandırmazsanız, kullanıcıların imzasız denetimleri çalıştıramaz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067177)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer internet bölgesi, Windows'da farklı etki alanlarından içerik sürükleyin**  
  Bu ilke ayarı, kullanıcıların İmzasız ActiveX denetimlerini bölgesinden yükleyip yükleyemeyeceklerini yönetmenize olanak sağlar. Bu tür kod, özellikle güvenilmeyen bir bölgeden Bekletmeden çıkarken zararlı olabilir. Bu ilke ayarını etkinleştirirseniz, kullanıcıların kullanıcı müdahalesi olmadan imzasız denetimlerini çalıştırabilirsiniz. Açılan kutuda istemi seçerseniz, kullanıcıların imzasız denetiminin çalışmasına izin verip vermeyeceklerini sorgulanır. Bu ilke ayarını devre dışı bırakırsanız, kullanıcıların imzasız denetimleri çalıştıramaz. Bu ilke ayarı yapılandırmazsanız, kullanıcıların imzasız denetimleri çalıştıramaz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067095)  
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer işlemleri Active X yüklemesini kısıtla**   
  Bu ilke ayarı, Web tarayıcı denetimi barındırma uygulamaları otomatik ActiveX denetimi yüklenmesini sorması için etkinleştirir. Bu ilke ayarını etkinleştirirseniz, tüm işlemler için ActiveX denetimi yüklemesinin otomatik isteyen Web tarayıcı denetimi engeller. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, Web tarayıcı denetimi ActiveX denetimi yüklemesinin tüm işlemler için otomatik olarak sorulmasını engellemez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067250)  
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer internet bölgesi kod parçacıkları**  
  Bu ilke ayarı, kullanıcı kod parçacıklarını çalıştırıp çalıştıramayacağını yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz, kullanıcı kod parçacıklarını çalıştırabilirsiniz. Bu ilke ayarını devre dışı bırakırsanız, kullanıcı kod parçacıklarını çalıştıramazsınız. Bu ilke ayarı yapılandırmazsanız, kullanıcı etkinleştirebilir veya kod parçacıklarını devre dışı bırakın.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067176)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer kısıtlı bölge sürükleyin ve bırakın veya kopyalama ve yapıştırmanın**  
  Bu ilke ayarı, kullanıcıların dosyaları ya da kopyalama sürükleyin ve bölgede bir kaynak dosyalarından yapıştırma yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, kullanıcılar dosyaları veya kopyalama sürükleyin ve bu bölge dosyalarından otomatik olarak yapıştırın. Aşağı açılan kutusunda istemi seçerseniz, kullanıcıların sürükleyin veya kopya dosyalar bu bölgeden verilmeyeceğini seçmek için sorgulanır. Bu ilke ayarını devre dışı bırakırsanız, kullanıcıların dosyaları sürükleyerek veya kopyalama ve dosyaları bu bölgeden yapıştırma engellenir. Bu ilke ayarı yapılandırmazsanız, kullanıcıların sürükleyin veya kopya dosyalar bu bölgeden verilmeyeceğini seçmek için sorgulanır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067096)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **İmza geçersiz olduğunda Internet Explorer yazılım**  
  Bu ilke ayarı ActiveX denetimlerini ve dosya indirme gibi yazılımlar yüklenebilir ya da imzası geçersiz olsa bile kullanıcı tarafından çalıştırılan yönetmenizi sağlar. Geçersiz bir imza, birisi dosyasıyla yapmadığından gösterebilir. Bu ilke ayarını etkinleştirirseniz, kullanıcılar dosyaları, geçersiz imzalı kurulmayı veya istenir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcılar çalıştırın veya geçersiz bir imza ile dosyalarını yükleyin. Bu ilke yapılandırmazsanız, kullanıcıların çalıştırmak veya geçersiz bir imza ile dosyaları yüklemek seçebilirsiniz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067201)
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer'ın kısıtlı bölge Kopyala ve Yapıştır komut dosyası aracılığıyla**  
  Bu ilke ayarı, belirli bir bölgede (örneğin, kesme, kopyalama ve yapıştırma) Pano işlemi betikleri gerçekleştirip gerçekleştiremeyeceğini yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz, komut dosyası bir pano işlemini gerçekleştirebilirsiniz. Açılan kutusunda seçtiğiniz istemi, kullanıcılar mı kullanılacağına yönelik pano işlemlerini gerçekleştirmek sorgulanır. Bu ilke ayarını devre dışı bırakırsanız, bir komut dosyası bir Pano işlemi gerçekleştirilemiyor. Bu ilke ayarı yapılandırmazsanız, bir komut dosyası bir Pano işlemi gerçekleştirilemiyor.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067165)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer kısıtlı bölge farklı etki alanlarından içerik arasında windows sürükleyin**  
  Bu ilke ayarı kaynak ve hedef farklı windows olduğunda içerik bir etki alanından farklı bir etki alanına sürükleyerek seçenekleri ayarlamanıza olanak sağlar. Bu ilke ayarını etkinleştirin ve Etkinleştir'i tıklatın, kaynak ve hedef farklı windows olduğunda kullanıcıların içeriği bir etki alanından farklı bir etki alanına sürükleyebilirsiniz. Kullanıcılar, bu ayarı değiştiremezsiniz. Bu ilke ayarını etkinleştirin ve devre dışı bırak'a tıklayın, hem kaynak hem de hedef farklı windows olduğunda kullanıcıların içeriği bir etki alanından farklı bir etki alanına sürükleyemezsiniz. Kullanıcılar, bu ayarı değiştiremezsiniz. Bu ilke ayarını devre dışı bırakır veya, yapılandırmayın olduğunda kaynak ve hedef farklı windows Internet Explorer 10'da, kullanıcıların içeriği bir etki alanından farklı bir etki alanına sürükleyemezsiniz. Kullanıcıların Internet Seçenekleri iletişim kutusunda Bu ayarı değiştirebilirsiniz. Bu ilke devre dışı bırakır veya, yapılandırmayın olduğunda kaynak ve hedef farklı windows Internet Explorer 9 ve önceki sürümlerinde, kullanıcıların içeriği bir etki alanından farklı bir etki alanına sürükleyebilirsiniz. Kullanıcılar, bu ayarı değiştiremezsiniz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067166)   

  **Varsayılan**: Devre dışı  
  
- **Internet Explorer kullanıcıları siteleri ekleme**  
  Ekleme veya siteler, güvenlik bölgelerinden kaldırma engeller. Web siteleri aynı güvenlik düzeyine sahip bir güvenlik bölgesi grubudur. Güvenlik bölgeleri için site yönetimi ayarlarını bu ilkeyi etkinleştirmek, devre dışı bırakılır. (Site yönetim görmek için ayarları, Internet Seçenekleri iletişim kutusundaki güvenlik bölgesi için Güvenlik sekmesine tıklayın ve sonra siteler düğmesine tıklayın.) Bu ilkeyi devre dışı bırakır veya yapılandırmazsanız, kullanıcıların Web sitelerinin, siteleri güvenilen siteler ve Yasak siteler bölgelerinden kaldırın ve yerel Intranet bölgesi için ayarları ekleyebilirsiniz. Bu ilke, kullanıcılar yönetici tarafından kurulan güvenlik bölgeleri için site yönetimi ayarlarını değiştirmesini engeller. Not: Güvenlik sekmesine arabirimden kaldıran (\User Configuration\Administrative Templates\Windows components\ınternet Explorer\Internet Denetim Masası ' bulunur) "güvenlik sayfası devre dışı bırak" ilkesi, bu ilkesine göre önceliklidir. Bu ilke etkinleştirilirse, göz ardı edilir. Ayrıca bkz: "güvenlik bölgeleri: Yalnızca makine ayarlarını kullan"ilkesi.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067167)  
  
  **Varsayılan**: Devre dışı  
  
- **Windows Internet Explorer internet bölgesi başlatılan betik**  
  Bu ilke ayarı, betik tarafından başlatılan açılır pencereleri ve başlık ve durum çubuğu içeren windows üzerindeki kısıtlamaları yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz, bu bölgede Windows kısıtlamaları güvenlik uygulanmayacak. Bu özellik tarafından sağlanan bir güvenlik katmanı eklendi olmadan güvenlik bölgesi çalıştırır. Bu ilke ayarını devre dışı bırakırsanız, betik tarafından başlatılan açılır pencereleri ve başlık ve durum çubuğu içeren windows içerdiği zararlı olabilecek eylemler çalıştıramazsınız. Internet Explorer güvenlik özelliği bu bölgede işlem için Windows güvenlik kısıtlamaları komut dosyası özellik denetim ayarı tarafından belirlenen açıktır. Bu ilke ayarı yapılandırmazsanız, betik tarafından başlatılan açılır pencereleri ve başlık ve durum çubuğu içeren windows içerdiği zararlı olabilecek eylemler çalıştıramazsınız. Internet Explorer güvenlik özelliği bu bölgede işlem için Windows güvenlik kısıtlamaları komut dosyası özellik denetim ayarı tarafından belirlenen açıktır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067088)  
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer güvenlik bölgeleri yalnızca makine ayarlarını kullan**  
  Güvenlik bölgesi bilgilerini aynı bilgisayarın tüm kullanıcıları için geçerlidir. Web siteleri aynı güvenlik düzeyine sahip bir güvenlik bölgesi grubudur. Bu ilkeyi etkinleştirmek, bir güvenlik bölgesi için kullanıcının yaptığı değişiklikleri o bilgisayardaki tüm kullanıcılara uygulanır. Bu ilkeyi devre dışı bırakır veya yapılandırmazsanız, aynı bilgisayardaki kullanıcılar kendi güvenlik bölgesi ayarlarından kurabilirsiniz. Güvenlik bölgesi ayarlarından aynı bilgisayara aynı şekilde geçerlidir ve kullanıcı başka bir kullanıcı değişiklik yoksa emin olmak için bu ilkeyi kullanın. Ayrıca bkz: "güvenlik bölgeleri: ilkeleri değiştirmek kullanıcılara izin verme" ilkesi.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067086)  
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer'ın yerel makine bölge java izinleri kilitli**  
  Bu ilke ayarı, Java uygulamaları için izinleri yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz, Seçenekler açılır kutusundan seçebilirsiniz. Özel denetim izinlerini ayarlar için ayrı ayrı. Düşük güvenilirlik, uygulamaların tüm işlemleri sağlar. Orta düzey güvenilirlik (bir alanda bellek görüşmesi yapamaz program dışında), kendi sanal uygulamaların artı boş alan (istemci bilgisayarda bir güvenli depolama alanı) ve kullanıcı tarafından denetlenen dosya g/ç gibi özellikler sağlar. Yüksek güvenilirlik, korumalı alanında çalışmasını sağlar. Java uygulamaları çalışmasını önlemek için devre dışı bırakın. Bu ilke ayarını devre dışı bırakırsanız, Java uygulamalarını çalıştıramazsınız. Bu ilke ayarı yapılandırmazsanız, Java uygulamalarını devre dışı bırakıldı.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067253) 
  
  **Varsayılan**: Java devre dışı bırak 
  
- **Internet Explorer kısıtlı bölge kötü amaçlı yazılımdan koruma karşı ActiveX denetimlerini çalıştırmaz**   
  Bu ilke ayarı, Internet Explorer karşı sayfalarında güvenli iseler denetlemek için ActiveX denetimleri, kötü amaçlı yazılımdan koruma programları çalışıp çalışmayacağını belirler. Bu ilke ayarını etkinleştirirseniz, Internet Explorer ActiveX denetiminin bir örneğini oluşturmak güvenli olup olmadığını görmek için kötü amaçlı yazılımdan koruma programınızı denetleyin olmaz. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer ActiveX denetiminin bir örneğini oluşturmak güvenli olup olmadığını görmek için kötü amaçlı yazılımdan koruma programı her zaman denetler. Bu ilke ayarı yapılandırmazsanız, Internet Explorer ActiveX denetiminin bir örneğini oluşturmak güvenli olup olmadığını görmek için kötü amaçlı yazılımdan koruma programı her zaman denetler. Kullanıcılar bu davranışı açıp kapatabilir, Internet Explorer güvenlik ayarlarını kullanarak kapatabilirsiniz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067089)
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer kısıtlı bölge Authenticode ile imzalanmış .NET Framework bağımlı bileşenleri Çalıştır**  
  Bu ilke ayarı, Authenticode ile imzalanmış .NET Framework bileşenlerini Internet Explorer'dan çalışıp çalışmayacağını yönetmenizi sağlar. Bu bileşenler, bir nesne etiketi ve bir bağlantıdan başvurulan Yönetilen yürütülebilir dosyaları başvurulan yönetilen denetimleri içerir. Bu ilke ayarını etkinleştirirseniz, Internet Explorer imzalı yönetilen bileşenleri çalıştırır. Açılan kutusunda seçtiğiniz istemi, Internet Explorer imzalı yönetilen bileşenleri çalıştırılıp çalıştırılmayacağını için girmesini ister. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer imzalı yönetilen bileşenleri yürütme olmaz. Bu ilke ayarı yapılandırmazsanız, Internet Explorer imzalı yönetilen bileşenleri yürütme olmaz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067169)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer veri kaynaklarına kısıtlı bölge erişim**  
  Bu ilke ayarı, Internet Explorer Microsoft XML Parser (MSXML) ya da ActiveX Data Objects (ADO) kullanan başka bir güvenlik bölgesi'nden veri erişip erişemeyeceğini yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz, kullanıcılar bir bölge içinde başka bir siteden verilere erişmek için MSXML veya ADO kullanan bölge sayfasında yükleyebilir. Açılan kutusunda seçtiğiniz istemi, kullanıcıların sayfayı MSXML veya ADO bölgede başka bir siteden verilere erişmek için kullandığı bölgesinde yüklemek için izin verip vermeyeceklerini sorgulanır. Bu ilke ayarını devre dışı bırakırsanız, kullanıcıların bir bölge içinde başka bir siteden verilere erişmek için MSXML veya ADO kullanan bölge sayfasında yüklenemiyor. Bu ilke ayarı yapılandırmazsanız, kullanıcıların bir bölge içinde başka bir siteden verilere erişmek için MSXML veya ADO kullanan bölge sayfasında yüklenemiyor.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067161)  
  
  **Varsayılan**: Devre Dışı Bırak 
  
- **Internet Explorer internet bölgesi, kötü amaçlı yazılımdan koruma ActiveX denetimlerini karşı çalışmaz**  
  Bu ilke ayarı, Internet Explorer karşı sayfalarında güvenli iseler denetlemek için ActiveX denetimleri, kötü amaçlı yazılımdan koruma programları çalışıp çalışmayacağını belirler. Bu ilke ayarını etkinleştirirseniz, Internet Explorer ActiveX denetiminin bir örneğini oluşturmak güvenli olup olmadığını görmek için kötü amaçlı yazılımdan koruma programınızı denetleyin olmaz. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer ActiveX denetiminin bir örneğini oluşturmak güvenli olup olmadığını görmek için kötü amaçlı yazılımdan koruma programı her zaman denetler. Bu ilke ayarı yapılandırmazsanız, Internet Explorer ActiveX denetiminin bir örneğini oluşturmak güvenli olup olmadığını görmek için kötü amaçlı yazılımdan koruma programı her zaman denetler. Kullanıcılar bu davranışı açıp kapatabilir, Internet Explorer güvenlik ayarlarını kullanarak kapatabilirsiniz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067162)  
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer internet bölgesi Kopyala ve Yapıştır komut dosyası aracılığıyla**  
  Bu ilke ayarı, belirli bir bölgede (örneğin, kesme, kopyalama ve yapıştırma) Pano işlemi betikleri gerçekleştirip gerçekleştiremeyeceğini yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz, komut dosyası bir pano işlemini gerçekleştirebilirsiniz. Açılan kutusunda seçtiğiniz istemi, kullanıcılar mı kullanılacağına yönelik pano işlemlerini gerçekleştirmek sorgulanır. Bu ilke ayarını devre dışı bırakırsanız, bir komut dosyası bir Pano işlemi gerçekleştirilemiyor. Bu ilke ayarı yapılandırmazsanız, bir komut dosyası bir pano işlemini gerçekleştirebilirsiniz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067084)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **ActiveX Yükleyici Hizmeti Internet Explorer kullan**  
  Bu ilke ayarı ActiveX denetimleri nasıl yüklendiğini belirtmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz, ActiveX Yükleyici Hizmeti varsa ve ActiveX denetimleri yüklenmesine izin verecek şekilde yapılandırılmış ActiveX denetimleri yüklendi. Devre dışı bırakın veya bu ilke ayarı yapılandırmayın, ActiveX denetimleri, kullanıcı başına denetimlerini dahil olmak üzere standart yükleme süreci boyunca yüklenir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067163)
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer bölge yüksekliğinden koruma işlemleri**  
  Internet Explorer her Web sayfası üzerinde kısıtlamalar getirir. Kısıtlamalar (Internet, Intranet, yerel makine bölgesi ve benzeri) Web sayfasının konumuna bağlıdır. Örneğin, Web sayfalarını yerel bilgisayarda en az bir güvenlik kısıtlamalarına sahiptir ve Yerel Makine bölgesini birinci hedef kötü niyetli kullanıcılar için yerel makine güvenliğin bölgesindedir. Bu ilke ayarını etkinleştirirseniz, tüm işlemler için bölge yüksekliğinden herhangi bir bölge korunabilir. Internet Explorer veya işlem listesinde listelenenler dışındaki işlemleri devre dışı bırakın veya bu ilke ayarı yapılandırmayın, bu tür bir koruma alırsınız.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067160)  
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer internet bölgesi İmzalanmamış ActiveX denetimlerini indirin**   
  Bu ilke ayarı, kullanıcıların İmzasız ActiveX denetimlerini bölgesinden yükleyip yükleyemeyeceklerini yönetmenize olanak sağlar. Bu tür kod, özellikle güvenilmeyen bir bölgeden Bekletmeden çıkarken zararlı olabilir. Bu ilke ayarını etkinleştirirseniz, kullanıcıların kullanıcı müdahalesi olmadan imzasız denetimlerini çalıştırabilirsiniz. Açılan kutuda istemi seçerseniz, kullanıcıların imzasız denetiminin çalışmasına izin verip vermeyeceklerini sorgulanır. Bu ilke ayarını devre dışı bırakırsanız, kullanıcıların imzasız denetimleri çalıştıramaz. Bu ilke ayarı yapılandırmazsanız, kullanıcıların imzasız denetimleri çalıştıramaz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067325)
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer internet bölgesi, farklı etki alanlarında windows ve çerçeveleri gidin**   
  Bu ilke ayarı, windows ve çerçeveler açma ve erişim uygulamaların farklı etki alanlarında yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, kullanıcılar windows ve çerçeveleri diğer etki alanları ve diğer etki alanlarından erişim uygulamalara açabilirsiniz. Kullanıcılar açılan kutusunda seçtiğiniz istemi, windows ve çerçeveleri başka etki alanlarından uygulamalara erişmesine izin verilip verilmeyeceğini sorgulanır. Bu ilke ayarını devre dışı bırakırsanız, kullanıcılar, windows ve çerçeveleri, farklı etki alanlarından uygulamalara erişmek için açılamıyor. Bu ilke ayarı yapılandırmazsanız, kullanıcıların windows ve çerçeveleri diğer etki alanları ve diğer etki alanlarından erişim uygulamalara açabilirsiniz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067083)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer internet bölgesi durum çubuğu komut dosyası aracılığıyla güncelleştirmeleri**  
  Bu ilke ayarı, bir komut dosyası bölge içindeki durum çubuğu güncelleştirebilirsiniz yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, durum çubuğu komut dosyalarını güncelleştirebilirsiniz. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, betik durum çubuğu güncelleştirmeye izin verilmiyor.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067087)  
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer kısıtlı bölge dahil yerel yolu sunucu için dosyalar karşıya yüklenirken**  
  Bu ilke ayarı, kullanıcı, bir HTML formu aracılığıyla bir dosya karşıya yüklenirken yerel yol bilgileri gönderildiğinde denetler. Yerel yol bilgisi gönderilir, bazı bilgiler sunucuya yanlışlıkla açığa. Örneğin, kullanıcının Masaüstü'nden gönderilen dosya yolun bir parçası olarak kullanıcı adını içerebilir. Bu ilke ayarını etkinleştirirseniz, kullanıcı, bir HTML formu aracılığıyla bir dosya karşıya yüklenirken yol bilgisi gönderilir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcı, bir HTML formu aracılığıyla bir dosya karşıya yüklenirken yol bilgisi kaldırıldı. Bu ilke ayarı yapılandırmazsanız, kullanıcıya bir HTML formu aracılığıyla bir dosya yüklenirken yol bilgisi gönderilip gönderilmeyeceğini seçebilirsiniz. Varsayılan olarak, yol bilgisi gönderilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067085)  
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer işlemleri kısıtlamak dosya indirme**   
  Bu ilke ayarı, Web tarayıcı denetimi barındırma uygulamaları otomatik kullanıcı tarafından başlatılan olmayan dosya indirmeleri sorması için etkinleştirir. Bu ilke ayarını etkinleştirirseniz, Web tarayıcı denetimi otomatik olarak kullanıcı tarafından başlatılan tüm işlemler için olmayan dosya indirmeleri sorulmasını engeller. Bu ilke ayarını devre dışı bırakırsanız, Web tarayıcı denetimi otomatik olarak kullanıcı tarafından başlatılan tüm işlemler için olmayan dosya indirmeleri sorulmasını engellemez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067164)  
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer'ın kısıtlı bölge izin ActiveX denetimlerini kullanmak için etki alanları yalnızca onaylanmış**   
  Bu ilke ayarı, Web siteleri dışında ActiveX denetimini yüklü Web sitesini çalıştırmak ActiveX denetimlerini izin vermek için kullanıcı istenirse denetler. Bu ilke ayarını etkinleştirirseniz, ActiveX denetimleri, bu bölgedeki sitelerinden çalıştırmadan önce kullanıcıya sorulur. Kullanıcı, denetimlerin geçerli siteden veya tüm sitelerden çalışmasına izin vermeyi seçebilirsiniz. Bu ilke ayarını devre dışı bırakırsanız, kullanıcı başına site ActiveX istemini görmez ve bu bölgedeki tüm sitelerden ActiveX denetimlerini çalıştırabilirsiniz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067233)  
  
  **Varsayılan**: Enabled  
  
- **Kısıtlı bölge Internet Explorer'ı başlatın ve ActiveX denetimlerini betik güvenli olarak işaretlenmemiş**  
  Bu ilke ayarı, güvenli olarak işaretlenmemiş ActiveX denetimlerini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, ActiveX denetimleri, güvenilir olmayan verileri veya betikler için nesne güvenliği ayarlamadan parametreler ile yüklenir ve komut dosyalı çalıştırın. Bu ayar, güvenli ve yönetilen bölgeler dışında önerilmez. Bu ayar, başlatılır ve komut dosyası için hem güvenli hem de güvenli denetimler neden olur, betik ActiveX denetimlerini yoksayma seçeneği için güvenli olarak işaretlenmiş. Bu ilke ayarını etkinleştirin ve istemi açılır kutusunda, kullanıcıların denetimi parametrelerle yüklemeye izin verilip verilmeyeceği veya komut dosyası. Bu ilke ayarını devre dışı bırakırsanız, güvenli hale getirilemez ActiveX denetimlerini parametrelerle yüklü değil veya komut dosyası. Bu ilke ayarı yapılandırmazsanız, güvenli hale getirilemez ActiveX denetimlerini parametrelerle yüklü değil veya komut dosyası.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067097)  
  
  **Varsayılan**: Devre Dışı Bırak  
  
- **Internet Explorer kullanıcıları ilkelerini değiştirme**  
  Kullanıcılar güvenlik bölge ayarlarını değiştirmesini engeller. Web siteleri aynı güvenlik düzeyine sahip bir güvenlik bölgesi grubudur. Bu ilkeyi etkinleştirmek, güvenlik düzeyi kaydırıcısını Internet Seçenekleri iletişim kutusundaki Güvenlik sekmesinde ve Özel Düzey düğmesini devre dışı bırakılır. Bu ilkeyi devre dışı bırakır veya yapılandırmazsanız, kullanıcıların güvenlik bölgeleri için ayarları değiştirebilirsiniz. Bu ilke, kullanıcılar yönetici tarafından kurulan güvenlik bölge ayarlarını değiştirmesini engeller. Not: Denetim Masası'ndaki Internet Explorer'dan Güvenlik sekmesine kaldıran (\User Configuration\Administrative Templates\Windows components\ınternet Explorer\Internet Denetim Masası ' bulunur) "güvenlik sayfası devre dışı bırak" ilkesi önceliklidir Bu ilke. Bu ilke etkinleştirilirse, göz ardı edilir. Ayrıca bkz: "güvenlik bölgeleri: Yalnızca makine ayarlarını kullan"ilkesi.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067155)  
    
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer kısıtlı bölge korumalı modu**  
  Bu ilke ayarı, korumalı modunu açmak sağlar. Korumalı modu, Internet Explorer, Internet Explorer için kayıt defteri ve dosya sistemine yazabilirsiniz konumları azaltarak kötü amaçla kullanılan güvenlik açıklarına karşı korumaya yardımcı olur. Bu ilke ayarını etkinleştirirseniz, korumalı mod etkinleştirilir. Kullanıcı, korumalı modunu devre dışı bırakmak olamaz. Bu ilke ayarını etkinleştirirseniz, korumalı mod kapalıdır. Kullanıcı, korumalı modu kapatamazsınız. Bu ilke ayarı yapılandırmazsanız, açın veya korumalı modunu kapatın.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067080)  
  
  **Varsayılan**: Etkinleştir  
  
- **Internet Explorer internet bölgesi kullanıcı veri kalıcılığı**  
  Bu ilke ayarı, tarayıcının geçmişinde, Sık Kullanılanlar'da, bir XML deposu veya doğrudan bir Web sayfasında diske kaydedilmiş bilgilerin korunması yönetmenizi sağlar. Bir kullanıcı için kalıcı bir sayfa geri döndüğünde, bu ilke ayarını uygun şekilde yapılandırıldıysa sayfa durumu geri yüklenebilir. Bu ilke ayarını etkinleştirirseniz, kullanıcı tarayıcının geçmişinde, Sık Kullanılanlar'da, bir XML deposu veya doğrudan bir Web sayfasında diske kaydedilmiş bilgi saklayabilir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcı bilgileri tarayıcının geçmişinde, Sık Kullanılanlar'da, bir XML deposu veya doğrudan bir Web sayfasında diske kaydedilmiş korumak olamaz. Bu ilke ayarı yapılandırmazsanız, kullanıcıların tarayıcının geçmişinde, Sık Kullanılanlar'da, bir XML deposu veya doğrudan bir Web sayfasında diske kaydedilmiş bilgi saklayabilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067156)  
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer internet bölgesi web tarayıcı denetimleri betik oluşturma**  
 
  Bu ilke ayarı, bir sayfa komut dosyası aracılığıyla gömülü WebBrowser denetimi denetimi olup olmadığını belirler. Bu ilke ayarını etkinleştirirseniz, WebBrowser denetimi betik erişime izin. Bu ilke ayarını devre dışı bırakırsanız, WebBrowser denetimi betik erişmesine izin verilmiyor. Bu ilke ayarı yapılandırmazsanız, kullanıcı etkinleştirebilir veya betik erişimi WebBrowser denetimi devre dışı bırakın. Varsayılan olarak, yalnızca yerel makine ve Intranet bölgeleri WebBrowser denetimi betik erişime izin.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067157)  
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer'ın kısıtlı bölge kullanıcı veri kalıcılığı**  
  Bu ilke ayarı, tarayıcının geçmişinde, Sık Kullanılanlar'da, bir XML deposu veya doğrudan bir Web sayfasında diske kaydedilmiş bilgilerin korunması yönetmenizi sağlar. Bir kullanıcı için kalıcı bir sayfa geri döndüğünde, bu ilke ayarını uygun şekilde yapılandırıldıysa sayfa durumu geri yüklenebilir. Bu ilke ayarını etkinleştirirseniz, kullanıcı tarayıcının geçmişinde, Sık Kullanılanlar'da, bir XML deposu veya doğrudan bir Web sayfasında diske kaydedilmiş bilgi saklayabilir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcı bilgileri tarayıcının geçmişinde, Sık Kullanılanlar'da, bir XML deposu veya doğrudan bir Web sayfasında diske kaydedilmiş korumak olamaz. Bu ilke ayarı yapılandırmazsanız, kullanıcıların tarayıcının geçmişinde, Sık Kullanılanlar'da, bir XML deposu veya doğrudan bir Web sayfasında diske kaydedilmiş bilgi koruma olamaz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067081)  
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer'ın intranet bölgesi java izinleri kilitli**  
  Bu ilke ayarı, Java uygulamaları için izinleri yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz, Seçenekler açılır kutusundan seçebilirsiniz. Özel denetim izinlerini ayarlar için ayrı ayrı. Düşük güvenilirlik, uygulamaların tüm işlemleri sağlar. Orta düzey güvenilirlik (bir alanda bellek görüşmesi yapamaz program dışında), kendi sanal uygulamaların artı boş alan (istemci bilgisayarda bir güvenli depolama alanı) ve kullanıcı tarafından denetlenen dosya g/ç gibi özellikler sağlar. Yüksek güvenilirlik, korumalı alanında çalışmasını sağlar. Java uygulamaları çalışmasını önlemek için devre dışı bırakın. Bu ilke ayarını devre dışı bırakırsanız, Java uygulamalarını çalıştıramazsınız. Bu ilke ayarı yapılandırmazsanız, Java uygulamalarını devre dışı bırakıldı.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067082)  
  
  **Varsayılan**: Java devre dışı bırak  
  
- **Internet Explorer'ın gelişmiş korumalı mod**  
  Geliştirilmiş korumalı mod, Windows 64 bit sürümlerinde 64 bit işlemleri kullanarak kötü amaçlı Web sitelerinin karşı ek koruma sağlar. En az çalıştıran bilgisayarlar için Windows 8, geliştirilmiş korumalı mod da sınırlar Internet Explorer okuyabileceği konumlar kayıt defteri ve dosya sistemi. Bu ilke ayarını etkinleştirirseniz, geliştirilmiş korumalı mod etkinleştirilir. Korumalı modu etkin olan herhangi bir bölgeye geliştirilmiş korumalı mod kullanır. Kullanıcılar, geliştirilmiş korumalı mod devre dışı bırakmak mümkün olmayacaktır. Bu ilke ayarını devre dışı bırakırsanız, geliştirilmiş korumalı mod kapalıdır. Korumalı modu etkin olan herhangi bir bölgeye, Windows Vista için Internet Explorer 7'de sunulan korumalı modu sürümünü kullanır. Bu ilke yapılandırmazsanız, kullanıcıların açın veya Internet Seçenekleri iletişim kutusunun Gelişmiş sekmesinde geliştirilmiş korumalı mod devre dışı açın.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067158)  
  
  **Varsayılan**: Enabled  
  
- **Internet Explorer smart screen'i uyarıları atla**  
  Bu ilke ayarı, kullanıcı Kimden SmartScreen Filtresi uyarılarını devre dışı bırakabilir olup olmadığını belirler. SmartScreen Filtresi, Internet Explorer kullanıcıların yaygın olarak Internet'ten yüklemeyin yürütülebilir dosyaları hakkında kullanıcıyı uyarır. Bu ilke ayarını etkinleştirirseniz, kullanıcıya SmartScreen Filtresi uyarılarını engelleyin. Kullanıcı devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, SmartScreen Filtresi uyarılarını devre dışı bırakabilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067159)  
  
  **Varsayılan**: Devre dışı  
  
- **Internet Explorer'ın kısıtlı bölge meta yenileme**  
  Bu ilke ayarı, Web sayfasının yazarı tarayıcılar başka bir Web sayfasına yönlendirmek için Meta Yenile ayarı (Etiket) kullanıyorsa, başka bir Web sayfasına bir kullanıcının tarayıcı yönlendirilebilir yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, başka bir Web sayfasına etkin Meta Yenileme ayarı içeren bir sayfa yükleyen kullanıcının tarayıcısı yönlendirilebilir. Bu ilke ayarını devre dışı bırakırsanız, etkin yenileme Meta ayarı içeren bir sayfa yükleyen kullanıcının tarayıcısı başka bir Web sayfasına yönlendirilemiyor. Bu ilke ayarı yapılandırmazsanız, etkin yenileme Meta ayarı içeren bir sayfa yükleyen kullanıcının tarayıcısı başka bir Web sayfasına yönlendirilemiyor.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067154)  
  
  **Varsayılan**: Devre dışı  
  
## <a name="local-policies-security-options"></a>Yerel İlkeler Güvenlik Seçenekleri
Daha fazla bilgi için [ilke CSP'si - LocalPoliciesSecurityOptions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions) Windows belgelerinde. 

- **Adlandırılmış kanallara ve paylaşımlarına için anonim erişimi kısıtlama**  
  Etkin olduğunda, bu güvenlik ayarı paylaşımlarını ve ayarlarını kanallara anonim erişimi kısıtlar: (1) olabilir Adlandırılmış Kanallar, (2) anonim olarak erişilebilecek paylaşımlar anonim olarak erişilebilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067212)  
  
  **Varsayılan**: Evet  
  
- **En düşük oturum güvenliği için NTLM SSP tabanlı sunucuları**  
  Bu güvenlik ayarı, bir server istemesine, 128 bit şifreleme ve/veya NTLMv2 oturum güvenliği sağlar. Bu değerler, LAN Manager kimlik doğrulama düzeyi güvenlik ayarı değerine bağlıdır. Seçenekler şunlardır: NTLMv2 oturum güvenliği gerektirir: İleti bütünlüğü anlaşma değilse bağlantı başarısız olur. 128 bit şifreleme gerektir. Güçlü şifreleme (128-bit) değilse anlaşıldığında bağlantı başarısız olur.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067246) 
  
  **Varsayılan**: NTLM V2 ve 128 bit şifreleme gerektir  
  
- **Ekran koruyucu etkinleşmeden kilit ekranında işlem yapılmadan geçen süre**  
  Windows, bir oturumun etkin olmamasını fark eder ve etkin olmama süresi etkin olmama sınırını aşarsa, ekran koruyucusu çalışarak oturumu kilitler.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067210)  
  
  **Varsayılan**: 15
  
- **Her zaman imzala istemciye gerektiren** etki alanı üyesi tarafından başlatılan tüm güvenli kanal trafiği imzalanmış veya şifrelenmiş gerekir, bu güvenlik ayarı belirler. Bir bilgisayar bir etki alanına katıldığında, bir bilgisayar hesabı oluşturulur. Sistem yeniden başlatıldığında, bundan sonra bilgisayar hesabı parolasını kendi etki alanı için etki alanı denetleyicisi ile güvenli bir kanal oluşturmak için kullanır. Bu güvenli kanal geçirmek NTLM kimlik doğrulaması, LSA SID/name arama ve daha fazlası gibi işlemleri gerçekleştirmek için kullanılır. Bu ayar etki alanı üyesi tarafından başlatılan tüm güvenli kanal trafiği en düşük güvenlik gereksinimlerini karşılayıp karşılamadığını belirler. Özel etki alanı üyesi tarafından başlatılan tüm güvenli kanal trafiği imzalanmış veya şifrelenmiş gerekir belirler. Bu ilke etkinleştirilirse, imzalama veya şifreleme tüm güvenli kanal trafik anlaşılmadıkça sonra güvenli kanal oluşturulmuş olmaz. Bu ilkeyi devre dışı bırakıldı ve ardından şifreleme ve tüm güvenli kanal trafiğinin etki alanı denetleyicisi ile imzalama işlemi yapılır ve bu durumda imzalama ve şifreleme düzeyini etki alanı denetleyicisinin sürümü ve aşağıdaki iki ayarlarını bağlıdır İlkeler: Etki alanı üyesi: (Uygun olduğunda) güvenli kanal verisini dijital olarak şifrele etki alanı üyesi: Dijital olarak imzala güvenli kanal verisini (uygun olduğunda).  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067187) 
  
  **Varsayılan**: Evet
  
- **Kimlik doğrulama düzeyi**  
  Bu güvenlik ayarı, ağ açmalarında hangi sınama/yanıt kimlik doğrulama protokolü belirler. Bu seçim, istemcileri, oturum güvenliği anlaşması düzeyini ve şu şekilde sunucuları tarafından kabul edilen kimlik doğrulama düzeyi tarafından kullanılan kimlik doğrulama protokolü düzeyini etkiler:  
  - *LM ve NTLM yanıtlar göndermek* -İstemciler LM ve NTLM kimlik doğrulaması kullanmak ve hiçbir zaman NTLMv2 oturum güvenliği; etki alanı denetleyicileri, LM, NTLM ve NTLMv2 kimlik doğrulamasını kabul etmiş olursunuz. 
  - *LM ve NTLM - NTLMv2 anlaşıldığında gönderme* -istemcileri LM ve NTLM kimlik doğrulaması kullanmak ve sunucunun destekliyorsa NTLMv2 oturum güvenliği kullanır; etki alanı denetleyicileri, LM, NTLM ve NTLMv2 kimlik doğrulamasını kabul etmiş olursunuz. 
  - *Yalnızca NTLM yanıtı gönder* -istemciler yalnızca NTLM kimlik doğrulaması kullanmak ve sunucunun destekliyorsa NTLMv2 oturum güvenliği kullanır; etki alanı denetleyicileri, LM, NTLM ve NTLMv2 kimlik doğrulamasını kabul etmiş olursunuz. 
  - *Gönder NTLMv2 yanıtı* -istemciler yalnızca NTLMv2 kimlik doğrulamasını ve sunucunun destekliyorsa NTLMv2 oturum güvenliği kullanır; etki alanı denetleyicileri, LM, NTLM ve NTLMv2 kimlik doğrulamasını kabul etmiş olursunuz. 
  - *Yalnızca NTLMv2 yanıtı gönderin. LM Reddet* -istemciler yalnızca NTLMv2 kimlik doğrulamasını ve sunucunun destekliyorsa NTLMv2 oturum güvenliği kullanır; etki alanı denetleyicileri, LM reddeder (yalnızca NTLM ve NTLMv2 kimlik doğrulamasını kabul eder). 
  - *Yalnızca NTLMv2 yanıtı gönderin. LM ve NTLM reddeder* -istemciler yalnızca NTLMv2 kimlik doğrulamasını ve sunucunun destekliyorsa NTLMv2 oturum güvenliği kullanır; etki alanı denetleyicileri, LM ve NTLM (yalnızca NTLMv2 kimlik doğrulamasını kabul) reddeder.  

  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067189)   
    
  **Varsayılan**: Yalnızca NTLMv2 yanıtı gönderin. LM ve NTLM Reddet
  
- **İstemcilerin üçüncü taraf SMB sunucularına şifrelenmemiş parolaları göndermesini engelleme**  
  Bu güvenlik ayarı etkinleştirilmişse, sunucu ileti bloğu (SMB) yeniden yönlendiricisinin doğrulama sırasında parola şifrelemesini desteklemeyen Microsoft olmayan SMB sunucularına düz metin parolalar gönderebilirsiniz. Şifrelenmemiş parolalar göndermek için bir güvenlik riski oluşturur.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067235)  
  
  **Varsayılan**: Evet
  
- **Sunucu İletişimleri dijital olarak her zaman imzalama iste**  
  Bu güvenlik ayarı, SMB istemcisinin SMB paket imzalamasını deneyip denemeyeceğini belirler. Sunucu İleti Bloğu (SMB) protokolünü temel Microsoft dosya ve yazıcı paylaşımı ve birçok ağ gibi diğer işlemler, Windows Uzaktan yönetim sağlar. SMB paket aktarım değiştirme adam-de-adam saldırıları önlemek için SMB paketlerin dijital imza SMB protokolünü destekler. Bu ilke ayarı, SMB istemci bileşeni bir SMB sunucusuna bağlandığında imzalaması deneyip denemeyeceğini belirler. Bu ayar etkinleştirilirse Microsoft ağ istemcisi oturum kurulduğunda imzalaması gerçekleştirmek için sunucu sorar. Sunucuda paket imzalama etkinleştirildiyse, paket imzalama anlaşması yapılır. Bu ilke devre dışı bırakılırsa, SMB istemcisi hiçbir zaman SMB paket imzalamasını.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067319)  
  
  **Varsayılan**: Evet
  
- **Yönetici yükseltme istemi davranışı**  
  Bu ilke ayarı, Yöneticiler için yükseltme isteminin davranışını denetler. Seçenekler şunlardır: 
    - *İstem olmadan Yükselt* -yükseltme gerektirmeden onayı veya kimlik bilgileri gerektiren bir işlem gerçekleştirmek ayrıcalıklı hesaplara izin verir. Not: Bu seçenek yalnızca en kısıtlı ortamlarında kullanın. 
    - *Güvenli masaüstünde kimlik bilgileri istemi* - bir işlem, ayrıcalık yükseltme gerektirdiğinde kullanıcının güvenli masaüstünde bir ayrıcalıklı kullanıcı adı ve parola girmesi istenir. Geçerli kimlik bilgileri kullanıcının girdiği işlemi kullanıcının yüksek kullanılabilir ayrıcalık ile devam eder. 
    - *Güvenli masaüstünde onay istemi* - bir işlem, ayrıcalık yükseltme gerektirdiğinde kullanıcının güvenli masaüstünde izin ver veya Reddet seçmek için istenir. Kullanıcı izin seçerse, işlemi kullanıcının yüksek kullanılabilir ayrıcalık ile devam eder. 
    - *Kimlik bilgileri istemi* -, ayrıcalık yükseltme işleminin gerektirdiğinde, kullanıcı bir yönetici kullanıcı adı ve parola girmesi istenir. Geçerli kimlik bilgileri kullanıcının girdiği işlemi ayrıcalık ile devam eder. 
    - *Onay istemi* - bir işlem, ayrıcalık yükseltme gerektirdiğinde kullanıcı izin ver veya Reddet seçmesi istenir. Kullanıcı izin seçerse, işlemi kullanıcının yüksek kullanılabilir ayrıcalık ile devam eder.  
    - *Windows dışı ikililer için onay istemi* - bir işlem Microsoft'a ait olmayan bir uygulama ayrıcalık gerektiren için kullanıcının güvenli masaüstünde izin ver veya Reddet seçmek için istenir. Kullanıcı izin seçerse, işlemi kullanıcının yüksek kullanılabilir ayrıcalık ile devam eder. 
  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067215)   
  
  **Varsayılan**: Güvenli masaüstünde onay iste
  
- **En düşük oturum güvenliği için NTLM SSP tabanlı istemciler**  
  Bu güvenlik ayarı, istemci istemesine, 128 bit şifreleme ve/veya NTLMv2 oturum güvenliği sağlar. Bu değerler, LAN Manager kimlik doğrulama düzeyi güvenlik ayarı değerine bağlıdır. Seçenekler şunlardır:
  - *NTLMv2 oturum güvenliği gerektiren* -NTLMv2 protokol anlaşma değilse bağlantı başarısız olur. 
  - *128 bit şifreleme gerektir* -güçlü şifreleme (128-bit) değilse anlaşıldığında bağlantı başarısız olur.
  - *NTLMv2 ve 128 bit şifreleme gerektiren*.  

  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067324)  

  **Varsayılan**: NTLM V2 128 şifrelemesi
  
- **Akıllı kart kaldırma davranışı**  
    Bu güvenlik ayarı, akıllı kart oturum açan kullanıcı için akıllı kart okuyucusundan kaldırıldığında ne olacağını belirler. Seçenekler şunlardır:
     - *Herhangi bir eylemi*. 
     - *İş istasyonu kilitleme* -akıllı kart kaldırıldığında alan bırakın, bunları akıllı kartlarını almak ve hala korumalı bir oturum korumasına izin vererek iş istasyonu kilitlenmiş.
     - *Oturum kapatmaya zorla* -akıllı kart kaldırıldığında kullanıcı otomatik olarak kapatılır.
     - *Uzak masaüstü oturumunun bağlantısının kesilip kesilmeyeceğini* -akıllı kart kaldırma işlemi, kullanıcı oturumu kapatmadan oturum keser. Bu, kullanıcının akıllı kart ekleyin ve tekrar oturum açmaya gerek olmadan daha sonra veya başka bir akıllı kart bilgisayara, okuyuculu oturumu Sürdür sağlar. Yerel bir oturum söz konusuysa, bu ilke İş İstasyonunu Kilitle ilkesiyle tam olarak aynı işlevi görür.
  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067331) 
    
  **Varsayılan**: İş İstasyonunu Kilitle
  
- **Blok SAM hesaplarının ve paylaşımların anonim listelenmesi**  
  Bu güvenlik ayarı hesaplarının ve paylaşımların anonim listelenmesi SAM izin verilip verilmeyeceğini belirler. Windows, anonim kullanıcıların etki alanı hesapları ve ağ paylaşımlara adları listelendirmek gibi etkinlikleri gerçekleştirmesine olanak tanır. Örneğin, yönetici kullanıcılara karşılıklı güven saklamaz güvenilen bir etki alanında erişim istediğinde bu kullanışlı hale. Anonim numaralandırmasına SAM hesaplarının ve paylaşımların izin vermek istemiyorsanız, ardından bu ilkeyi kümesine *Evet*.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067191)  
  
  **Varsayılan**: Evet
  
- **Blok boş parolalı uzaktan oturum açma**  
  Bu güvenlik ayarı, parola korumalı olmayan yerel hesapların fiziksel bilgisayar konsolu dışındaki konumlardan oturum açmak için kullanılıp kullanılamayacağını belirler. Etkinleştirilirse, oturum açmak için parola korumalı olmayan yerel hesaplar bilgisayarın Klavyesi kullanmanız gerekir. 

  *Uyarı*: Bilgisayarların fiziksel olarak güvenli bir yerde değil, tüm yerel kullanıcı hesapları için güçlü parola ilkeleri her zaman uygulamalıdır. Aksi takdirde, bilgisayara fiziksel erişimi olan herkes bir parola sahip olmayan bir kullanıcı hesabı kullanarak oturum açabilir. Bu taşınabilir bilgisayarlar için özellikle önemlidir. 

  Bu güvenlik ilkesi Herkes grubuna uygularsanız, hiç kimsenin Uzak Masaüstü Hizmetleri üzerinden oturum açabilir. Bu ayar, etki alanı hesapları kullanıyorsanız oturumları etkilemez. Bu ayar atlamak için uzak etkileşimli oturum açma kullanan uygulamalar için mümkündür.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067219)  
  
  **Varsayılan**: Evet
  
- **Standart kullanıcı yükseltme istemi davranışı**  
  Bu ilke ayarı, standart kullanıcılar için yükseltme isteminin davranışını denetler. 
  - *Yükseltme isteklerini otomatik olarak Reddet* - bir işlem, ayrıcalık yükseltme gerektirdiğinde hata iletisi görüntülenir, yapılandırılabilir bir erişim reddedildi. Standart kullanıcı Yardım Masası aramalarını azaltır için bu ayarı seçebilir gibi Masaüstü çalıştıran bir kurumsal. 
  - *Güvenli masaüstünde kimlik bilgileri istemi* - bir işlem, ayrıcalık yükseltme gerektirdiğinde kullanıcının güvenli masaüstünde farklı bir kullanıcı adı ve parola girmesi istenir. Geçerli kimlik bilgileri kullanıcının girdiği işlemi ayrıcalık ile devam eder. 
  - *Kimlik bilgileri istemi* -, ayrıcalık yükseltme işleminin gerektirdiğinde, kullanıcı bir yönetici kullanıcı adı ve parola girmesi istenir. Geçerli kimlik bilgileri kullanıcının girdiği işlemi ayrıcalık ile devam eder.  

  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067183)  
  
  **Varsayılan**: Yükseltme isteklerini otomatik olarak reddet
  
- **Yönetici Onay Modu'ndaki yöneticiler için gerektirir**  
  Bu ilke ayarı, bilgisayarın tüm kullanıcı hesabı denetimi (UAC) ilke ayarlarını davranışını denetler. Bu ilke ayarı değiştirirseniz, bilgisayarınızı yeniden başlatmanız gerekir. Seçenekler şunlardır:   
  - *Yapılandırılmamış* -ilgili yönetici onay modu ve tüm UAC ilke ayarlarını devre dışı bırakıldı. Not: Bu ilke ayarı devre dışıysa, Güvenlik Merkezi, işletim sistemi güvenliğinin bir bütün düşürüldü bildirir. 
  - *Evet* -yönetici onay modu etkin. Bu ilke etkinleştirilmiş olması ve ilgili UAC ilke ayarları, yerleşik yönetici hesabı ve Yönetici Onay Modu'nda Çalıştır için Administrators grubunun üyesi olan diğer tüm kullanıcılara izin vermek için uygun şekilde ayarlanmalıdır.  

  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067184)  
  
  **Varsayılan**: Evet
  
- **SAM hesaplarının anonim numaralandırmasına engelle**  
  Bu güvenlik ayarı, anonim bağlantılara bilgisayara verilen ek hangi izinleri belirler. Windows, anonim kullanıcıların etki alanı hesapları ve ağ paylaşımlara adları listelendirmek gibi etkinlikleri gerçekleştirmesine olanak tanır. Örneğin, yönetici kullanıcılara karşılıklı güven saklamaz güvenilen bir etki alanında erişim istediğinde bu kullanışlı hale. Bu güvenlik seçeneği ek sınırlamalar anonim bağlantılara gibi yerleştirilmesine olanak sağlar: 
  - *Evet* -numaralandırma SAM hesaplarının izin verme. Bu seçenek, herkes kaynaklar için güvenlik izinleri kimliği doğrulanmış kullanıcılar ile değiştirir.
  - *Yapılandırılmamış* -ek kısıtlama yok. Varsayılan izinlerini kullanır.  
  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067318)  

  **Varsayılan**: Evet
  
- **Güvenlik Hesapları Yöneticisi uzak çağrısına izin ver**  
  Bu ilke ayarı, SAM uzak rpc bağlantılarını kısıtla olanak sağlar. Seçilmezse, varsayılan güvenlik tanımlayıcısı kullanılır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067209)  
  
  **Varsayılan**: *O:BAG:BAD:(A;; RC;; BA)*

- **Yönetici onay modu kullanın**  
  Bu ilke ayarı, yerleşik yönetici hesabı için yönetici onay modu davranışını denetler. Seçenekler şunlardır: 
  - *Evet* -yönetici onay modu yerleşik yönetici hesabı kullanır. Varsayılan olarak kullanıcıdan işlemi ayrıcalık gerektiren herhangi bir işlem ister. 
  - *Yapılandırılmamış* -yerleşik yönetici hesabı tüm uygulamaların tam yönetici ayrıcalıklarıyla çalıştırır. 

  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067186)  

  **Varsayılan**: Evet
  
- **Güvenli konumları için kullanıcı Arabirimi uygulamalara izin ver**  
  Bu ilke, kullanıcı arabirimi erişilebilirliği (UIAccess veya UIA) programları standart bir kullanıcı tarafından kullanılan yükseltme istemleri için güvenli masaüstünü otomatik olarak devre dışı olup olmadığını ayarı denetler. 
  - *Evet* -Windows Uzaktan Yardım dahil olmak üzere, UIA programları yükseltme istemleri için güvenli masaüstünü otomatik olarak devre dışı. Devre dışı bırakmayın, "kullanıcı hesabı denetimi: Yükseltme isterken güvenli masaüstüne geç"ilke ayarı, istemler güvenli masaüstü yerine etkileşimli kullanıcının masaüstünde görünür. 
  - *Yapılandırılmamış*:-Güvenli Masaüstü yalnızca etkileşimli masaüstü kullanıcısı tarafından veya devre dışı bırakılarak devre dışı bırakılabilir "kullanıcı hesabı denetimi: Yükseltme isterken güvenli masaüstüne geç"ilke ayarı.  

  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067185)  

  **Varsayılan**: Evet

- **Uygulama yüklemelerini Algıla ve yükseltme isteminde bulun**  
  Bu ilke ayarı, bilgisayarın uygulama yükleme algılama davranışını denetler. Seçenekler şunlardır: 
  - *Etkin* - uygulama yükleme paketi, ayrıcalık yükseltme gerektiren algılandığında, kullanıcı bir yönetici kullanıcı adı ve parola girmesi istenir. Geçerli kimlik bilgileri kullanıcının girdiği işlemi ayrıcalık ile devam eder. 
  - *Devre dışı bırakılmış* -uygulama yükleme paketleri algılandı ve yükseltme istenir. Standart kullanıcı Masaüstü çalıştıran ve kullanmak kuruluşların Grup İlkesi Yazılım Yükleme gibi yükleme teknolojileri temsilci veya Systems Management Server (SMS) Bu ilke ayarını devre dışı bırakmanız gerekir. Bu durumda, yükleyici algılama gerekli değildir.  
  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067208)  

  **Varsayılan**: Evet
  
- **Sonraki parola değişiminde LAN manager karma değerini depolama engelle**  
  Sonraki parola değişiminde yeni parolanın LAN Manager (LM) karma değeri depolanır, bu güvenlik ayarı belirler. LM karması nispeten zayıf ve saldırıya değiştirmeyen şifreleme açısından güçlü Windows NT karması. LM karması güvenlik veritabanında yerel bilgisayarda depolandığından parolalar, güvenlik veritabanı gerçekleşirse zarar görebilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067213)  
  
  **Varsayılan**: Evet

- **Dosya ve kayıt defteri yazma hatalarını kullanıcı konumlarında başına konumlarında sanal olarak oluştur**  
  Bu ilke, uygulama yazma hatalarının tanımlanan kayıt defteri ve dosya sistemi konumlarına yeniden yönlendirilen olup olmadığını ayarı denetler. Bu ilke ayarı, yönetici olarak çalıştırın ve çalışma zamanı uygulama verileri için yazma uygulamaları azaltır *% ProgramFiles %* , *% Windir %* , *%Windir%\system32*, veya *HKLM\Software*.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067321)  
  
  **Varsayılan**: Evet

## <a name="ms-security-guide"></a>MS Güvenlik Kılavuzu  
Daha fazla bilgi için [ilke CSP'si - MSSecurityGuide](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mssecurityguide) Windows belgelerinde.  

- **Ağ oturumu açma üzerindeki yerel hesaplar için UAC kısıtlamalarını Uygula**  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067188)  

  **Varsayılan**: Enabled
  
- **SMB v1 istemci sürücü başlangıç yapılandırması**  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067214) 
 
  **Varsayılan**: Devre dışı sürücü
  
- **SMB v1 sunucusu**  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067190)  

  **Varsayılan**: Devre dışı
  
- **Özet kimlik doğrulaması**  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067193) 
 
  **Varsayılan**: Devre dışı
  
- **Yapılandırılmış özel durum işleme üzerine koruma**  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067217)  

  **Varsayılan**: Enabled
  
## <a name="mss-legacy"></a>MSS eski  
Daha fazla bilgi için [ilke CSP'si - MSSLegacy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-msslegacy) Windows belgelerinde.  

- **Koruma düzeyi yönlendirme ağ IP kaynağı**  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067220)  
  
  **Varsayılan**: En yüksek koruma  
  
- **Itanium tabanlı sistemler için NetBIOS adı sürüm istekleri dışında WINS sunucusundan ağ yoksay**  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067218)  
 
  **Varsayılan**: Enabled
  
- **IPv6 yönlendirme koruma düzeyi kaynak ağ**  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067216)  

  **Varsayılan**: En yüksek koruma

- **Ağ ICMP yeniden yönlendirmeleri oluşturulan OSPF geçersiz kıl**  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067326)  

  **Varsayılan**: Devre dışı
  
## <a name="power"></a>Güç  
Daha fazla bilgi için [ilke CSP'si - Power](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power) Windows belgelerinde.  

- **Takılıyken Uyandırma parola iste**  
  Bu ilke ayarı, sistem uyku durumundan çıktığında kullanıcıyı parola girmeniz istenir, belirtir. Etkinleştirin veya bu ilke ayarı yapılandırmayın, kullanıcı sistem uyku durumundan çıktığında parola istenir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcı sistem uyku durumundan çıktığında parola sorulmadan değil.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067221)  
  
  **Varsayılan**: Enabled
  
- **Pil sırada Uyuma, bekleme durumlarını**  
  Bu ilke ayarı, Windows bilgisayar uyku durumunda koyma, bekleme durumlarını kullanabiliyorsa yönetir. Etkinleştirin veya bu ilke ayarı yapılandırmayın varsa, Windows bilgisayar uyku durumuna için bekleme durumlarını kullanır. Bu ilke ayarını devre dışı bırakırsanız, bekleme durumlarını (S1 S3) izin verilmez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067195)  
  
  **Varsayılan**: Devre dışı
  
- **Takılıyken Uyuma, bekleme durumlarını**  
  Bu ilke ayarı, Windows bilgisayar uyku durumunda koyma, bekleme durumlarını kullanabiliyorsa yönetir. Etkinleştirin veya bu ilke ayarı yapılandırmayın varsa, Windows bilgisayar uyku durumuna için bekleme durumlarını kullanır. Bu ilke ayarını devre dışı bırakırsanız, bekleme durumlarını (S1 S3) izin verilmez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067196)  
  
  **Varsayılan**: Devre dışı
  
- **LAN'da Uyandırma pil sırasında parola iste**  
  Bu ilke ayarı, sistem uyku durumundan çıktığında kullanıcıyı parola girmeniz istenir, belirtir. Etkinleştirin veya bu ilke ayarı yapılandırmayın, kullanıcı sistem uyku durumundan çıktığında parola istenir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcı sistem uyku durumundan çıktığında parola sorulmadan değil.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067322)  
  
  **Varsayılan**: Enabled

## <a name="remote-assistance"></a>Uzaktan Yardım
- **İstenen Uzak Yardım**  
  Bu ilke ayarını etkinleştirmek veya devre dışı Solicited (sor) bu bilgisayarda Uzaktan Yardım sağlar. 
  - *Bu ilke ayarını etkinleştirirseniz*, kullanıcıların bu bilgisayarda, birisi yardım istemek için e-posta veya dosya aktarımı kullanabilir. Ayrıca, kullanıcılar bu bilgisayar bağlantılara izin vermek için anlık ileti programları kullanabilir ve ek Uzak Yardım ayarlarını yapılandırabilirsiniz. 
  - *Bu ilke ayarını devre dışı bırakırsanız*, bu bilgisayardaki kullanıcıları e-posta veya dosya aktarımı birisi yardım istemek için kullanamazsınız. Ayrıca, kullanıcılar, bu bilgisayar bağlantılara izin vermek için anlık ileti programları kullanamazsınız. 
  - *Bu ilke ayarı yapılandırmazsanız*, kullanıcılar açabilir veya devre dışı Solicited (sor) Uzaktan Yardım kendilerini Denetim Masası'ndaki Sistem özellikleri kapatabilirsiniz. Kullanıcılar, Uzaktan Yardım ayarları da yapılandırabilirsiniz. 

  Bu ilke ayarını etkinleştirirseniz, Uzaktan Yardım sağlamak Yardımcıları izin vermek için iki yolunuz vardır: "Yalnızca bilgisayar görünümü Yardımcıları izin ver" veya "bilgisayarı uzaktan denetleme girişiminde Yardımcıları izin ver." "İlke ayarı bir zaman miktarı, sınırlar maksimum anahtar süresi" e-posta veya dosya aktarımı kullanılarak oluşturulan bir Uzaktan Yardım davet açık kalır. "Select e-posta davetiyesi göndermek için yöntem" ayarı, Uzaktan Yardım davet göndermek için kullanmak için hangi e-posta standart belirtir. E-posta programınızı bağlı olarak (davet alıcı bir Internet bağlantısı üzerinden bağlanır) Mailto standart ya da (davet e-posta iletinizi ekli) SMAPI (Basit MAPI) standart kullanabilirsiniz. SMAPI desteklenen yalnızca bir yöntem olduğundan, bu ilke ayarı Windows Vista'da kullanılabilir değil. Bu ilke ayarını etkinleştirirseniz, Uzaktan Yardım iletişime izin vermek uygun güvenlik duvarı özel durumları da etkinleştirmeniz gerekir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067198)

  **Varsayılan**: Uzaktan Yardım'ı devre dışı bırak

  Ayarlandığında *etkinleştirme Uzaktan Yardım*, aşağıdaki ek ayarları yapılandırın:  
  - **İstenen Uzak Yardım izni**  
    **Varsayılan**: Görünüm  

  - **En fazla bilet saat değeri**  
    **Varsayılan**: *Yapılandırılmadı*  

  - **En fazla bilet süre**  
    **Varsayılan**: Dakika    

  - **E-posta davetiyesi yöntemi**  
    **Varsayılan**: Basit MAPI

  
## <a name="remote-desktop-services"></a>Uzak Masaüstü Hizmetleri  
Daha fazla bilgi için [ilke CSP'si - RemoteDesktopServices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remotedesktopservices) Windows belgelerinde.  

- **Parola kaydetme engelle**  
  Parolaları bu bilgisayarda Uzak Masaüstü Bağlantısı'ndan kaydedilebilir olup olmadığını denetler. Bu ayarı etkinleştirirseniz, parola Uzak Masaüstü Bağlantısı'nda onay kutusu kaydetme devre dışıdır ve kullanıcıların parolaları Kaydet mümkün olmayacaktır. Bir kullanıcı, Uzak Masaüstü bağlantısı kullanarak bir RDP dosyası açılır ve ayarlarına kaydederse, daha önce RDP dosyasındaki var olan herhangi bir parola silinir. Bu ayarı devre dışı veya yapılandırılmamış bırakın, kullanıcı parolaları Uzak Masaüstü bağlantısı kullanarak kaydedebilirsiniz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067301)  
  
   **Varsayılan**: Enabled
  
- **RPC iletişimi güvenli hale getirme**  
  Bir Uzak Masaüstü oturumu konağı sunucusu ile tüm istemcilerin güvenli RPC iletişimi gerektirir veya iletişime izin verir belirtir. İstemciler ile RPC iletişimi güvenliğini sağlayarak yalnızca kimliği doğrulanmış ve şifrelenmiş isteklere güçlendirmek için bu ayarı kullanabilirsiniz. Durum Etkin olarak ayarlanırsa, Uzak Masaüstü Hizmetleri güvenli isteklerini desteklemek RPC istemcilerden gelen istekleri kabul eder ve güvenilmeyen istemciler ile iletişime izin vermez. Durumu devre dışı olarak ayarlanmışsa, Uzak Masaüstü Hizmetleri, her zaman tüm RPC trafiği için güvenlik ister. Ancak, iletişime isteğine yanıt yok RPC istemciler için izin verilir. Yapılandırılmamış durumu olarak iletişime izin verilir. Not: RPC arabirimi, yönetme ve Uzak Masaüstü Hizmetleri yapılandırmak için kullanılır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067248)  
  
  **Varsayılan**: Enabled
  
- **Blok sürücü yeniden yönlendirme**  
  Bu ilke ayarı, Uzak Masaüstü Hizmetleri oturumu (sürücü yeniden yönlendirme) istemci sürücü eşleme engellenip engellenmeyeceğini belirtir. Varsayılan olarak, RD Oturumu Ana bilgisayarı sunucu bağlantıyla birlikte otomatik olarak istemci sürücüleri eşler. Eşlenen sürücüler görünür biçimde dosya Gezgini veya bilgisayar oturum klasör ağacında  *\<SürücüHarfi >* üzerinde  *\<computername >* . Bu ilke ayarı, bu davranışı geçersiz kılmak için kullanabilirsiniz. Bu ilke ayarını etkinleştirirseniz, istemci sürücüsü yeniden yönlendirmesi, Uzak Masaüstü Hizmetleri oturumlarına izin verilmiyor ve Windows Server 2003, Windows 8 ve Windows XP çalıştıran bilgisayarlarda Pano dosya kopyalama yeniden yönlendirmesine izin verilmiyor. Bu ilke ayarını devre dışı bırakırsanız istemci sürücüsü yeniden yönlendirmesi her zaman izin verilir. Ayrıca, Pano yeniden yönlendirmesine izin verilip verilmediğini Pano dosya kopyalama yönlendirmesini her zaman izin verilir. Bu ilke ayarı yapılandırmazsanız istemci sürücüsü yeniden yönlendirmesi ve Pano dosya kopyalama yeniden yönlendirme Grup İlkesi düzeyinde belirtilmeyen.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067197)  
  
  **Varsayılan**: Enabled
  
- **Bağlantı kurulduğunda parola istemi**  
  Bu ilke ayarı, Uzak Masaüstü Hizmetleri istemci bağlantı kurulduğunda parola her zaman uyarıp uyarmayacağını belirtir. Uzak Masaüstü Bağlantısı istemci Parolada zaten sağlanan bile Uzak Masaüstü Hizmetleri oturum açan kullanıcılar için bir parola istemi zorlamak için bu ayarı kullanabilirsiniz. Varsayılan olarak, Uzak Masaüstü Hizmetleri Uzak Masaüstü Bağlantısı istemcisinde bir parola girerek otomatik olarak oturum açmasını sağlar. Bu ilke ayarını etkinleştirirseniz, kullanıcılar otomatik olarak Uzak Masaüstü Hizmetleri için Uzak Masaüstü Bağlantısı istemcisinde parolalarını sağlayarak oturum açamaz. oturum açmak parola istenir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcıların her zaman için Uzak Masaüstü Hizmetleri otomatik olarak Uzak Masaüstü Bağlantısı istemcisinde parolalarını sağlayarak oturum açabilir. Bu ilke ayarı yapılandırmazsanız, otomatik oturum açma Grup İlkesi düzeyinde belirtilmemiş.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067328)  
  
  **Varsayılan**: Enabled
  
- **Uzak Masaüstü Hizmetleri istemci bağlantı şifreleme düzeyi**  
  Uzak Masaüstü Protokolü (RDP) bağlantıları sırasında RD Oturumu Ana bilgisayarı sunucuları ile istemci bilgisayar arasındaki iletişimin güvenliğini sağlamak için özel bir şifreleme düzeyi kullanımını gerekip gerekmediğini belirtir. Bu ilke, yalnızca yerel RDP şifreleme kullanılırken geçerlidir. Ancak, yerel RDP şifreleme (aksine, SSL şifrelemesi) önerilmez. Bu ilke, SSL şifrelemesi için geçerli değildir. Bu ilke ayarını etkinleştirirseniz, istemcilerin ve RD Oturumu Ana bilgisayarı sunucuları arasındaki tüm iletişimler sırasında uzak bağlantıları bu ayarında belirtilen şifreleme yöntemini kullanmanız gerekir. Varsayılan olarak, şifreleme düzeyini Yüksek olarak ayarlanır. Aşağıdaki şifreleme yöntemleri kullanılabilir:  
  - *Yüksek* -yüksek ayarı, güçlü 128 bit şifreleme kullanarak istemciden sunucuya ve sunucudan istemciye gönderilen verileri şifreler. Bu şifreleme düzeyi yalnızca 128-bit istemcileri (örneğin, Uzak Masaüstü Bağlantısı'nı çalıştıran istemciler) içeren ortamlarda kullanın. Bu şifreleme düzeyi desteklemeyen istemciler, RD Oturumu Ana Bilgisayarı sunucularına bağlanamazlar.  
  - *İstemci uyumlu* -istemci uyumlu ayarı istemci tarafından desteklenen en yüksek anahtar gücünde sunucusu ile istemci arasında gönderilen verileri şifreler. Bu şifreleme düzeyi 128 bit şifreleme desteklemeyen istemciler içeren ortamlarda kullanın.  
  - *Düşük* -düşük ayarı yalnızca 56 bit şifreleme kullanarak istemciden sunucuya gönderilen verileri şifreler.  
  
  Devre dışı bırakın ya da bu ayarı yapılandırmayın, RD Oturumu Ana bilgisayarı sunucularını uzaktan bağlantılar için kullanılacak şifreleme düzeyini Grup İlkesi aracılığıyla zorlanmaz. FIPS uyumluluğunu önemli sistem şifreleme yapılandırılabilir. Şifreleme, karma ve (Bilgisayar Yapılandırması\Windows Ayarları\Güvenlik Ayarları\Yerel İlkeler\Güvenlik Seçenekleri altında.) Grup İlkesi ayarlarına imzalama için FIPS uyumlu algoritmalar kullanın FIPS uyumlu ayarı şifreler ve Microsoft şifreleme modüllerini kullanarak istemciden sunucuya ve Federal Bilgi İşleme Standardı (FIPS) 140 şifreleme algoritmaları, istemciden sunucuya gönderilen verilerin şifresini çözer. RD Oturumu Ana bilgisayarı sunucuları ile istemci arasındaki iletişimin şifreleme en yüksek düzeyde gerektirdiğinde bu şifreleme düzeyi kullanın.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067222)  
  
  **Varsayılan**: Yüksek
  
## <a name="remote-management"></a>Uzaktan Yönetim  
Daha fazla bilgi için [ilke CSP'si - RemoteManagement](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remotemanagement) Windows belgelerinde.  

- **Blok depolama kimlik bilgileri olarak çalıştırma**  
  İstemci temel kimlik doğrulaması.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067300)  
  
  **Varsayılan**: Enabled
  
- **Temel kimlik doğrulaması**  
  Bu ilke ayarı, Windows Uzaktan Yönetim (WinRM) hizmeti uzak bir istemciden Temel kimlik doğrulaması kabul edip etmeyeceğini yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz, WinRM hizmeti uzak bir istemciden Temel kimlik doğrulaması kabul eder. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, WinRM hizmeti uzak bir istemciden Temel kimlik doğrulaması kabul etmez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067223)  
  
  **Varsayılan**: Devre dışı
  
- **Blok istemci Özet kimlik doğrulaması**  
  Bu ilke ayarı Windows Uzaktan Yönetim (WinRM) istemcisi Özet kimlik doğrulaması kullanır yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, WinRM istemci Özet kimlik doğrulaması kullanmaz. WinRM istemcisini devre dışı bırakın veya bu ilke ayarı yapılandırmayın, Özet kimlik doğrulaması kullanır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067302)  
  
  **Varsayılan**: Enabled
  
- **Şifrelenmemiş trafiği**  
  Bu ilke ayarı, Windows Uzaktan Yönetim (WinRM) hizmeti ağ üzerinden şifrelenmemiş iletileri alan ve gönderen yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, WinRM istemci gönderir ve ağ üzerinden şifrelenmemiş iletileri alır. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, WinRM istemci gönderir veya ağ üzerinden yalnızca şifrelenmiş iletileri alır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067226)  
  
  **Varsayılan**: Devre dışı
  
- **Şifrelenmemiş istemci trafiğini**  
  Bu ilke ayarı Windows Remote Management (WinRM) istemcisi ağ üzerinden şifrelenmemiş iletileri alan ve gönderen yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, WinRM istemci gönderir ve ağ üzerinden şifrelenmemiş iletileri alır. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, WinRM istemci gönderir veya ağ üzerinden yalnızca şifrelenmiş iletileri alır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067304)  
  
  **Varsayılan**: Devre dışı
  
- **İstemci temel kimlik doğrulaması**  
  Bu ilke ayarı Windows Uzaktan Yönetim (WinRM) istemcisi temel kimlik doğrulaması kullanır yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, WinRM istemci temel kimlik doğrulaması kullanır. WinRM HTTP aktarımı kullanmak için yapılandırılmışsa, kullanıcı adı ve parola ağda düz metin gönderilir. Devre dışı bırakmak veya bu ilke ayarı yapılandırmayın, WinRM istemci temel kimlik doğrulaması kullanmaz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067252)  
  
  **Varsayılan**: Devre dışı
  
## <a name="remote-procedure-call"></a>Uzak yordam çağrısı  
Daha fazla bilgi için [ilke CSP'si - RemoteProcedureCall](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remoteprocedurecall) Windows belgelerinde.  

- **Kimliği doğrulanmamış RPC istemci seçenekleri**  
  Bu ilke ayarı, RPC sunucusu çalıştırma zamanı RPC sunuculara bağlanma kimliği doğrulanmamış RPC istemcilerinin nasıl işlediğini denetler. Bu ilke ayarı, tüm RPC uygulamaları etkiler. Grup İlkesi kendisini işleme dahil işlevleri çeşitli etkileyebileceğinden bir etki alanı ortamında, bu ilke ayarı dikkatli kullanın. Bu ilke ayarı için bir değişikliği geri alma, her bir sorundan etkilenen makinede el ile müdahale gerektirebilir. Bu ilke ayarı, hiçbir zaman bir etki alanı denetleyicisine uygulanmalıdır. Bu ilke ayarını devre dışı bırakırsanız, RPC sunucusu çalıştırma zamanı Windows istemcisi ve Windows Server sürümlerinde bu ilke ayarı destek "None" değerini "Kimliği doğrulanmış" değerini kullanır. Bu ilke ayarı yapılandırmazsanız, devre dışı kalır. RPC sunucusu çalışma zamanı, "Windows istemci ve"None"Bu ilke ayarı destek Server SKU için kullanılan değeri için kullanılan kimlik doğrulaması yapılmış" değeriyle etkinleştirildi ancak gibi davranır. Bu ilke ayarını etkinleştirirseniz, bir makine üzerinde çalışan sunucularına bağlanan kimliği doğrulanmamış RPC istemcilere kısıtlamak için RPC sunucusu çalıştırma zamanı yönlendirir. Bir istemci kimliği doğrulanmış bir istemci sunucusuyla iletişim kurmak için bir adlandırılmış kanal kullanıyorsa veya RPC güvenlik kullanıyorsa olarak kabul edilir. Özellikle kimliği doğrulanmamış istemcileri tarafından erişilebilir olmasını istediğiniz RPC arabirimlerinin Bu ilke ayarı için seçili değerine bağlı olarak bu kısıtlama, muaf olabilir.  
  - *Hiçbiri* tüm RPC istemcilerinin ilke ayarının uygulandığı makine üzerinde çalışan sunucularına bağlanmasını sağlar. 
  - *Kimliği doğrulanmış* ilke ayarının uygulandığı makine üzerinde çalışan RPC sunucularına bağlanmak için yalnızca kimliği doğrulanmış RPC istemcilerinin (yukarıdaki tanımı) sağlar. Muafiyetleri bunları istenen arabirimleri verilir. 
  - *Özel durumlar kimliği doğrulanmış* ilke ayarının uygulandığı makine üzerinde çalışan RPC sunucularına bağlanmak için yalnızca kimliği doğrulanmış RPC istemcilerinin (yukarıdaki tanımı) sağlar. Hiçbir özel durumlara izin verilmez. Not: Bu ilke ayarı, sistem yeniden başlatılana kadar uygulanmaz.  

  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067225)  

  **Varsayılan**: Kimlik doğrulaması

## <a name="search"></a>Ara 
Daha fazla bilgi için [ilke CSP'si - arama](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-search) Windows belgelerinde.  

- **Şifrelenmiş öğeler için dizin oluşturmayı devre dışı**  
  Öğeler için dizin oluşturulmasına izin verir veya engeller. Bu anahtar, bu, Windows bilgi Koruması (WIP) korumalı dosyalar gibi şifreli öğelerin dizininin oluşturulmasını denetleyen Windows Search dizin'Oluşturucu içindir. İlke etkinleştirildiğinde, WIP korumalı öğelerin dizini oluşturulur ve bunlar hakkındaki meta veriler şifrelenmemiş bir konumda depolanır. Meta veriler, dosya yolu ve değiştirilme tarihi gibi veriler içerir. İlkeyi devre dışı bırakıldığında, WIP korumalı öğelerin dizini olmayan ve Cortana veya dosya Gezgini sonuçlarında içinde gösterme. Cihazda çok sayıda WIP korumalı medya dosyası varsa fotoğraflar ve Groove uygulamaları performansını da etkileyebilir.  
  [Daha fazla bilgi edinin]( https://go.microsoft.com/fwlink/?linkid=2067303)  
  
  **Varsayılan**: Evet
  
## <a name="smart-screen"></a>Akıllı Ekran  
Daha fazla bilgi için [ilke CSP'si - SmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-smartscreen) Windows belgelerinde.  

- **Doğrulanmamış dosyaları yürütülmesini engeller**  
  Kullanıcının doğrulanmamış dosyalarının çalıştırmasını engelleyin. 
  - *Yapılandırılmamış* -çalışanlar SmartScreen uyarılarını yoksayarak kötü amaçlı dosyalardan çalıştırın. 
  - *Evet* – çalışanlar SmartScreen uyarılarını gözardı et ve kötü amaçlı dosyalardan çalıştırın.

  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067228)  
  
  **Varsayılan**: Evet

- **Uygulamalar ve dosyalar için SmartScreen gerektirir**  
  BT yöneticilerinin için SmartScreen Windows yapılandırmasına olanak tanır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067168)  

  **Varsayılan**: Evet
  
## <a name="system"></a>Sistem  
Daha fazla bilgi için [ilke CSP'si - sistem](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system) Windows belgelerinde.  

- **Sistem önyükleme başlangıç sürücü başlatma**  
  Bu ilke ayarı erken başlatma kötü amaçlı yazılımdan koruma önyükleme başlatma sürücü tarafından belirlenen bir sınıflandırma göre hangi önyükleme başlatma sürücüler başlatılmadan belirtmenize olanak sağlar. Erken Başlatma kötü amaçlı yazılımdan koruma önyükleme başlatma sürücü, aşağıdaki sınıflandırmaları için her önyükleme başlatma sürücü döndürebilirsiniz: 
  - *İyi* -sürücü imzalanmış ve kurcalanmadığı.  
  - *Hatalı* -sürücü kötü amaçlı yazılım olarak belirlenmiştir. Başlatılacak bilinen hatalı sürücüler izin verme öneririz. 
  - *Hatalı, ancak önyükleme için gerekli* - sürücü kötü amaçlı yazılım olarak belirlenmiştir, ancak bilgisayar bu sürücü yüklemeden başarıyla önyükleme yapamazsınız. 
  - *Bilinmeyen* -Bu sürücü için kötü amaçlı yazılım algılama uygulamanız tarafından tarafından kanıtlanan taşınmadığından ve önyükleme başlatma erken başlatma kötü amaçlı yazılımdan koruma sürücüsü tarafından sınıflandırılan edilmemiş.  

  Bu ilke ayarını etkinleştirirseniz, bilgisayarın bir sonraki başlatılışında başlatmak için hangi önyükleme başlatma sürücüleri seçebilirsiniz. Devre dışı bırakır veya bu ilkeyi yapılandırmayın ayarlamak, belirlenen önyükleme başlatma sürücülerini iyi, bilinmeyen veya hatalı önyükleme kritik ancak başlatılır ve başlatılması hatalı belirlenen sürücü atlandı. Kötü amaçlı yazılım algılama uygulamanızı bir erken başlatma kötü amaçlı yazılımdan koruma önyükleme başlatma sürücü içermiyorsa veya erken başlatma kötü amaçlı yazılımdan koruma önyükleme başlatma sürücünüzü devre dışı bırakılırsa, bu ayarın hiçbir etkisi ve tüm önyükleme başlatma sürücüleri başlatılır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067307)   
  
  **Varsayılan**: İyi bilinmeyen ve kritik bozuk


## <a name="wi-fi"></a>Wi-Fi  
Daha fazla bilgi için [ilke CSP'si - Wi-Fi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi) Windows belgelerinde.  

- **Internet paylaşmayı engelle**  
  İnternet paylaşımı cihazda mümkün olup olmadığını belirtir.   
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067327)   

  **Varsayılan**: Evet  

- **Blok Wi-Fi etkin noktalarına bağlanmasını otomatik olarak**  
  İzin vermek veya cihaz için Wi-Fi etkin noktalarına otomatik olarak bağlanmasına izin vermeyin.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067320)   

  **Varsayılan**: Evet  
  
## <a name="windows-connection-manager"></a>Windows Bağlantı Yöneticisi  
Daha fazla bilgi için [ilke CSP'si - WindowsConnectionManager](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsconnectionmanager) Windows belgelerinde.  

- **Etki alanı olmayan ağlara bağlantıyı engelle**  
  Bu ilke ayarı için bir etki alanı tabanlı ağ ve bir temel etki alanı olmayan bağlanmasını bilgisayarlar engeller. aynı zamanda ağ. Bu ilke ayarı etkinse, bilgisayar üzerinde aşağıdaki koşullara göre otomatik ve el ile ağ bağlantısı denemeleri yanıt verir: 
  - Bilgisayarın etki alanı olmayan ağlara tüm otomatik bağlantı girişimlerinde bir etki alanı tabanlı ağ zaten bağlı olduğunda otomatik bağlantı girişimleri engellenir. Bilgisayar bir etki alanı dışı tabanlı ağa bağlandığında, etki alanı tabanlı ağlara otomatik bağlantı girişimleri engellenir. 
  - Ortamı dışındaki Ethernet üzerinden veya etki alanı tabanlı bir ağdaki bilgisayar ya da bir etki alanı olmayan için zaten bağlı olduğunda el ile yapılan bağlantı girişimleri tabanlı ve kullanıcının bu ilkeyi ihlal el ile ek bir ağa bağlantı oluşturmaya çalışır ayarlama, var olan ağ bağlantısını keser ve el ile bağlantıya izin verilir. Bilgisayar zaten bağlı olduğunda ya da Ethernet üzerinden veya etki alanı tabanlı bir ağdaki bir etki alanı dışı tabanlı ve bir kullanıcı bu ilke ayarı ihlal el ile ek bir ağa bağlantı oluşturmaya çalışır, mevcut Ethernet bağlantısı tutulur ve el ile bağlantı denemesi engellendi.  

  Bu ilke ayarı yapılandırılmadı veya devre dışı bırakıldı, bilgisayarları aynı anda hem etki alanı ve etki alanı olmayan ağlara bağlanmasına izin verilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067323)  

  **Varsayılan**: Enabled
  
## <a name="windows-defender"></a>Windows Defender  
Daha fazla bilgi için [ilke CSP'si - Defender'ın](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender) Windows belgelerinde.  

- **Gelen posta iletilerini tarama**  
  Erişim izni verdiği veya e-posta taramasına izin vermiyor.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067116)  
  
  **Varsayılan**: Evet  

- **Office uygulamalarının alt işlem türü başlatın**  
  Office uygulamalarının alt işlemler oluşturmak izin verilmez. Bu, Word, Excel, PowerPoint, OneNote ve erişim içerir. Özellikle başlatın veya kötü amaçlı bir yürütülebilir dosyaları indirmek için Office uygulamalarını kullanma girişimi makrosu tabanlı saldırılar için tipik bir kötü amaçlı yazılım yer alan bir davranış budur.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067121)  
  
  **Varsayılan**: Engelle
  
- **Defender'ın örnek gönderimi onay türü**  
  Kullanıcı denetimleri, veri göndermek için Windows Defender'ı düzeyinde vermiş olursunuz. Gerekli onay verilmiş, Windows Defender'ın bunları gönderir. Aksi halde (ve kullanıcı tarafından hiç sormak için belirtilen değilse), verileri göndermeden önce (Defender/AllowCloudProtection izin verildiğinde) kullanıcı onay için sormak için kullanıcı Arabirimi başlatılır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067131)  
  
  **Varsayılan**: Güvenli örnekleri otomatik olarak gönder 
  
- **İmza güncelleştirme aralığı (saat)**  
  Defender imza güncelleştirme aralığı saat
  
  **Varsayılan**: 4
  
- **Betiği yük yürütme türü indirildi**  
  Defender betiği yük yürütme türü indirildi
  
  **Varsayılan**: Engelle
  
- **Kimlik bilgisi türü çalmaya engelle**  
  Windows Defender Credential Guard, parolaları yalnızca ayrıcalıklı sistem yazılımlarının erişebileceği böylece yalıtmak için sanallaştırma tabanlı güvenlik kullanır. Bu parolalara yetkisiz erişim, Pass-the-Hash veya Pass-The-Ticket gibi kimlik bilgisi hırsızlığı saldırılarına yol açabilir. Windows Defender Credential Guard, NTLM parola karmalarını, Kerberos anahtar verme anahtarı ve etki alanı kimlik bilgileri uygulamalar tarafından depolanan kimlik bilgilerini koruyarak bu saldırıları engeller.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067065)  
  
  **Varsayılan**: Etkinleştir

- **E-posta içeriği yürütme türü**  
  Bu kural, çalıştırmak veya Microsoft Outlook veya Web postası (örneğin, Gmail.com veya Outlook.com) görünen bir e-postasındaki başlatılan engeller aşağıdaki dosya türlerinde engeller: Yürütülebilir (.exe, .dll veya .scr) komut dosyaları (örneğin, bir PowerShell .ps, VisualBasic .vbs veya .js dosyası JavaScript) dosyaları komut arşiv dosyaları.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067063)  
  
  **Varsayılan**: Engelle

- **Adobe Reader başlatma bir alt işlemde**  

  **Varsayılan**: Etkinleştir

- **Ağ koruması türü**  
  Bu ilke, ağ Koruması (Denetim/engelleme) açma veya kapatma sağlar, Windows Defender Exploit Guard. Ağ koruması, Windows Defender Exploit erişirken kimlik avı kuşku verici, siteleri yararlanma barındırma ve kötü amaçlı içerik herhangi bir uygulamadan Internet'te kullanan çalışanların koruyan koruma özelliğidir. Bu, üçüncü taraf tarayıcılar tehlikeli sitelere bağlanmasına engel içerir. Değer, bir tamsayı türüdür. Bu ayarı etkinleştirirseniz, ağ koruması açıktır ve çalışanlar, devre dışı bırakamazlar. Davranışını aşağıdaki seçeneklere göre denetlenebilir: Blok ve denetim. Bu ilke "Engelle" seçeneğiyle etkinleştirirseniz, kullanıcılar ve uygulamalar tehlikeli etki alanlarına bağlanmasını engellenir. Windows Defender Güvenlik Merkezi'nde bu etkinliği görebilirsiniz. Bu ilke "Denetleme" seçeneğiyle etkinleştirirseniz, kullanıcı/uygulama tehlikeli etki alanlarına bağlanmasını engellenmeyecektir. Ancak, bu etkinlik Windows Defender Güvenlik Merkezi, yine de görürsünüz. Bu ilke devre dışı bırakırsanız, kullanıcı/uygulama tehlikeli etki alanlarına bağlanmasını engellenmeyecektir. Windows Defender Güvenlik Merkezi'nde tüm ağ etkinliği görmemeniz. Bu ilke yapılandırmazsanız, ağ engelleme, varsayılan olarak devre dışıdır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067102)  
  
  **Varsayılan**: Etkinleştir
  
- **Defender'ın tarama gününü zamanla**  
  Tarama gününü zamanla Defender.
  
  **Varsayılan**: her gün
  
- **Bulut teslimli koruma**  
  En iyi bilgisayarınızı korumak için Windows Defender bilgileri Microsoft'a bulduğu sorunları hakkında gönderir. Microsoft bu bilgileri analiz edin, sizin ve diğer müşterilerin etkileyen sorunlar hakkında daha fazla bilgi edinmek ve geliştirilmiş çözümler sunar.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067039)
  
  **Varsayılan**:  Evet  

- **Defender'ın uygulama eylemi olası istenmeyen**  
  Windows Defender virüsten koruma olası istenmeyen uygulama (PUA) Koruması özelliği, tanımlamak ve indiriliyor ve yükleniyor. ağınızdaki Uç noktalara Koruyucu'daki engelleyin. Bu uygulamalar, virüsler, kötü amaçlı yazılım veya diğer tür tehditlerden değerlendirilmeyen, ancak olumsuz etkileyen performanslarını veya kullanan uç noktalarda eylemler gerçekleştirebilir. PUA düşük itibarlı sahip olduğu kabul edilir ve uygulamalar için de başvurabilir. Tipik PUA davranışını içerir: Sürücü web tarayıcıları ve kayıt defteri iyileştiricileri Ad ekleme paketleme yazılımların çeşitli türleri, hataları düzeltin, ancak uç noktada kalır ve değişiklik ya da en iyi duruma getirme ("standart dışı virüsten koruma" programları olarak da bilinir) sağlamak için istek ödeme sorunları algılayın. Bu uygulamalar riskini artırabilir ağınızı kötü amaçlı yazılım bulaşması tanımlamak için daha sıkı olmasını kötü amaçlı yazılımdan Etkilenme neden ve uygulamaları temizleme, BT kaynaklarının boşa harcanmasına neden.  
  [Daha fazla bilgi edinin](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-puaprotection)    
  
  **Varsayılan**: Engelle  

- **Betik gizlenmiş makro kod türü**  
  Kötü amaçlı yazılım ve diğer tehditlerden karartmak veya kötü amaçlı kodlarını bazı komut dosyalarında gizleme girişiminde bulunabilir. Bu kural çalışmasını görünen gizlenmiş olabilir önler.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067026)  
  
  **Varsayılan**: Engelle
  
- **Tam tarama sırasında Çıkarılabilir sürücüleri tara**  
  Windows Defender'ı tam tarama sırasında Çıkarılabilir sürücüleri (örneğin flash sürücü) kötü amaçlı ve istenmeyen yazılım taraması sağlar. Windows Defender virüsten koruma USB cihazları yürütmeden önce tüm dosyaları tarar.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067036)  
  
  **Varsayılan**: Evet  
  
- **Arşiv dosyalarını tara**  
  Defender'ın tarama arşiv dosyaları.
  
  **Varsayılan**: Evet
  
- **Davranış izleme**  
  Erişim izni verdiği veya işlevselliği Windows Defender davranış izlemeye izin vermiyor. Windows 10'da katıştırılmış, algılayıcınız toplamak ve işletim sisteminden davranış sinyalleri işleyebilir ve yalıtılmış, özel bulut Örneğiniz için Microsoft Defender ATP bu sensör verilerini gönderir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067111)  
  
  **Varsayılan**: Evet

- **Ağ klasörlerinden açılan dosyaları tara**  
  Dosya salt okunur ise kullanıcı Algılanan kötü amaçlı yazılımı kaldırmak mümkün olmayacaktır.
  
  **Varsayılan**: Evet

- **Güvenilmeyen USB işlem türü**  
  Bu kural, yöneticilerin imzalanmamış veya güvenilmeyen yürütülebilir dosyalar SD kartları gibi USB çıkarılabilir sürücü çalışmasını engelleyebilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067100)  
  
  **Varsayılan**: Engelle
  
- **Ekleme türü Office uygulamalarının diğer işlem**  
  Word, Excel, PowerPoint ve OneNote dahil olmak üzere, office uygulamalarının başka işlemlere kod eklemesini mümkün olmayacaktır. Bu genellikle, kötü amaçlı yazılım tarafından virüsten koruma tarama motorları etkinliğini gizlemek girişimi kötü amaçlı kod çalıştırmak için kullanılır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067019)  
  
  **Varsayılan**:  Engelle
  
- **Office makro kodu Win32 içeri aktarmalar türü izin ver**  
  Kötü amaçlı yazılım makro kodu'nde Office dosyaları almak ve daha fazla bulaşmasını sistem genelinde izin vermek için API çağrıları gerçekleştirmek için kullanılabilen Win32 DLL'leri yüklemek için kullanabilirsiniz. Bu kural, Win32 DLL'leri içe aktarabilir makro kodu içeren bir Office dosyaları engellemek çalışır. Bu, Word, Excel, PowerPoint ve OneNote içerir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067130)  
  
  **Varsayılan**: Engelle  
  
- **Defender'ın bulut engelleme düzeyi**  
  Defender'ın bulut blok düzeyi.
  
  **Varsayılan**: Yapılandırılmadı

- **Gerçek zamanlı izleme**  
  Defender'ın gerçek zamanlı izlemeyi gerektirir.
  
  **Varsayılan**: Evet
 
- **Bir alt işlemde Office iletişimi uygulamalarını başlatma**  

  **Varsayılan**:  Etkinleştir

- **Office uygulamaları yürütülebilir içerik oluşturma veya başlatma türü**  
  Bu kural, şüpheli ve kötü amaçlı eklentiler ve oluşturan veya yürütülebilir dosya başlatmak betikleri (Uzantılar) tarafından kullanılan tipik davranışları hedefler. Tipik bir kötü amaçlı yazılım yöntem budur. Office uygulamaları tarafından kullanılan uzantıları engellenir. Genellikle bu uzantılar belirli görevleri otomatikleştirin veya kullanıcı tarafından oluşturulan eklenti özellikleri sağlayan komut dosyalarını çalıştırmak için Windows Scripting Host (.wsh dosyaları) kullanın.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067108)  
  
  **Varsayılan**: Engelle

## <a name="windows-defender-firewall"></a>Windows Defender Güvenlik Duvarı  
Daha fazla bilgi için [2.2.2 FW_PROFILE_TYPOE]( https://docs.microsoft.com/openspecs/windows_protocols/ms-fasp/7704e238-174d-4a5e-b809-5f3787dd8acc) Windows protokolleri belgelerini de.  

- **Güvenlik duvarı profili etki alanı**  
  Kurala ait olduğu profillerin belirtir: Domain, Private, Public. Bu değer, etki alanlarına bağlı ağlara profilini temsil eder.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2066796)  

  - **Gelen bağlantılar engellenir**  
    **Varsayılan**: Evet

  - **Gerekli giden bağlantı**  
    **Varsayılan**: Evet 

  - **Engellenen gelen bildirimler**  
    **Varsayılan**: Evet

  - **Güvenlik Duvarı etkin**  
    **Varsayılan**: İzin Verildi

- **Genel güvenlik duvarı profili**  
  Kurala ait olduğu profillerin belirtir: Domain, Private, Public. Bu değer, ortak ağlar için profil temsil eder. Bu ağlar genel sunucu ana yöneticiler tarafından sınıflandırılır. Sınıflandırma, ana bilgisayar ağa bağlanan ilk kez gerçekleşir. Genellikle bu ağlar havaalanları, kahve dükkanları ve burada ağ veya ağ yöneticisine eşlerden güvenilir olmayan diğer ortak bir yerde olanlardır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067143)  

  - **Gelen bağlantılar engellenir**  
    **Varsayılan**: Evet

  - **Gerekli giden bağlantı**  
    **Varsayılan**: Evet 

  - **Engellenen gelen bildirimler**  
    **Varsayılan**: Evet

  - **Güvenlik Duvarı etkin**  
    **Varsayılan**: İzin Verildi

  - **Bağlantı güvenliği kuralları birleştirilmemiş Grup İlkesi**  
    **Varsayılan**: Evet

  - **Grup İlkesi birleştirilmemiş İlkesi kuralları**  
    **Varsayılan**: Evet

- **Özel güvenlik duvarı profili**  
  Kurala ait olduğu profillerin belirtir: Domain, Private, Public. Bu değer özel ağlar için profil temsil eder.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067041)  

   - **Gelen bağlantılar engellenir**  
    **Varsayılan**: Evet

  - **Gerekli giden bağlantı**  
    **Varsayılan**: Evet 

  - **Engellenen gelen bildirimler**  
    **Varsayılan**: Evet

  - **Güvenlik Duvarı etkin**  
    **Varsayılan**: İzin Verildi

## <a name="windows-hello-for-business"></a>İş İçin Windows Hello  
- **Gelişmiş yanıltma, kullanılabilir olduğunda gerektirir**  
  Yanıt Evet ise, cihazlar Gelişmiş yanıltma, kullanılabilir olduğunda kullanın. Hayır ise, sahtekarlığına karşı koruma engellenir. Yapılandırılmadıysa istemcideki yapılandırmalara uyulur.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067192)

  **Varsayılan**: Evet

- **İş için Windows Hello'yu Yapılandır**   
  Windows iş için Hello ile Windows parolaları, akıllı kartlar ve sanal akıllı kartları değiştirerek imzalamak için bir alternatifidir. Etkinleştirin veya bu ilke ayarı yapılandırmazsanız, cihaz Windows iş için Hello sağlar. Bu ilke ayarını devre dışı bırakırsanız, cihaz Windows iş için Hello herhangi bir kullanıcı için kaynak.

  **Varsayılan**: Evet

- **PIN kodunda küçük harfler iste**  
  Zorunlu kılınırsa, kullanıcı PIN'inin en az bir küçük harf içermesi gerekir.

  **Varsayılan**: İzin Verildi

- **PIN kodunda özel karakterler iste**  
  Zorunlu kılınırsa, kullanıcı PIN'inin en az bir özel karakter içermesi gerekir.

  **Varsayılan**: İzin Verildi

- **Minimum PIN uzunluğu**  
  Minimum PIN uzunluğu 4 ile 127 karakter arasında olmalıdır.

  **Varsayılan**: 6

- **PIN kodunda büyük harfler iste**  
  Zorunlu kılınırsa, kullanıcı PIN'inin en az bir büyük harf içermesi gerekir.

  **Varsayılan**: İzin Verildi

## <a name="windows-ink-workspace"></a>Windows Ink çalışma  
Daha fazla bilgi için [ilke CSP'si - WindowsInkWorkspace](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsinkworkspace) Windows belgelerinde.  

- **Mürekkep çalışma alanı**  
  Kullanıcının Ink çalışma alanına erişmesine izin verilip verilmeyeceğini belirtir. 
  - *Devre dışı* -mürekkep çalışma alanı erişimi devre dışı bırakıldı. Bu özellik devre dışıdır.
  - *Etkin* - mürekkep çalışma alanı özelliğin açık, ancak kullanıcının bunu kilit ekranının üstünde erişemez.
  - *Yapılandırılmamış* - mürekkep çalışma alanı özelliği açıktır ve kullanıcının bunu kilit ekranının üstünde kullanabilirsiniz.  

  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067241)  

  **Varsayılan**: Enabled
 
## <a name="windows-powershell"></a>Windows PowerShell  
Daha fazla bilgi için [ilke CSP'si - WindowsPowerShell](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowspowershell) Windows belgelerinde.  

- **Power shell Kabuk betiği block günlüğe kaydetme**  
  Bu ilke ayarı, Microsoft-Windows-PowerShell/Operational Olay günlüğüne tüm PowerShell Betiği giriş günlüğü etkinleştirir. Bu ilke ayarını etkinleştirirseniz, Windows PowerShell komutları, komut dosyası blokları, İşlevler ve betikleri - işlenmesini etkileşimli olarak veya Otomasyon aracılığıyla çağrılan olmadığını günlüğe kaydeder. Bu ilke ayarını devre dışı bırakırsanız, PowerShell Betiği giriş günlüğünü devre dışı bırakıldı. Betik bloğu çağırma günlüğü etkinleştirirseniz, PowerShell, ayrıca komutu, betik bloğu, işlev veya betiği başlatıldığında veya durdurulduğunda olayları kaydeder. Çağrı günlüğü etkinleştirme, yüksek hacimli olay günlükleri oluşturur. Not: Bu ilke ayarı, Bilgisayar Yapılandırması hem Kullanıcı Yapılandırması Grup İlkesi Düzenleyicisi'nde altında bulunmaktadır. Bilgisayar Yapılandırma İlkesi ayarı üzerinden Kullanıcı Yapılandırması ilke ayarı öncelik kazanır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067330)  

  **Varsayılan**: Enabled

## <a name="whats-changed-in-the-new-template"></a>Yeni şablon Değiştirilenler
*Spring 2019 güncelleştirme (19 saat 1) için MDM güvenlik temeli* şablonda aşağıdaki değişikliklerden *Önizleme* şablonu.

### <a name="changes-to-the-baseline-settings"></a>Taban çizgisi ayarlarında yapılan değişiklikler
Aşağıdaki ayarlar ya da şunlardır:
- *Yeni* bu taban çizgisini en son sürümünde.
- *Kaldırılan* bu en son temel sürümü, ancak önceki sürümde yoktu.
- *Düzeltilmiş* gelen ayarlar önceki sürümde nasıl göründüğü şekilde. 

*[Yeni]*  [ **Kilit üzerinde**](#above-lock):
-  **Ses, kilit ekranı uygulamalardan etkinleştir**    

*[Yeni]*  [ **Uygulama Yönetimi**](#application-management): 
- **Blok kullanıcı denetime yüklemeleri**  
- **Yükseltilmiş ayrıcalıklara sahip blok MSI uygulama yüklemeleri**  

*[Kaldırıldı]*  [ **Bitlocker**](#bitlocker):  
- Bit locker çıkarılabilir sürücü ilke > **şifreleme yöntemi**
- **Sabit sürücü ilke bit locker** *(tüm ayarları)*
- **Bit locker sistem sürücüsü İlkesi** *(tüm ayarları)*

*[Yeni]*  [ **Bağlantı**](#connectivity):
- **Güvenli erişim UNC yollarını Yapılandır**

*[Yeni]*  [ **Cihaz koruyucusu**](#device-guard):
- **Sanallaştırma tabanlı güvenlik**


*[Yeni]*  [ **DMA Guard**](#dma-guard):
- **Dış cihazları çekirdek DMA koruması ile uyumsuz numaralandırması**  

*[Yeni]*  [ **Internet Explorer**](#internet-explorer):
- **Durum çubuğu komut dosyası aracılığıyla Gezgini internet bölgesi güncelleştirmeleri**
- **Internet Explorer internet bölgesi sürükleyin ve bırakın veya kopyalama ve yapıştırmanın**  
- **Internet Explorer'ın kısıtlı bölge .NET Framework bağımlı bileşenler**  
- **Internet Explorer yerel makine bölgesi kötü amaçlı yazılımdan koruma karşı ActiveX denetimlerini çalıştırmaz**
- **Internet Explorer şifreleme desteği**  

*[Düzeltildi]*  [ **Internet Explorer**](#internet-explorer):
- **Dosya indirmeleri için Internet Explorer internet bölgesi otomatik istemi** > artık varsayılan değer: **devre dışı bırakılmış**. Önizleme'de bu etkin olarak ayarlandı.

*[Yeni]*  [ **Uzaktan Yardım**](#remote-assistance):  
- **İstenen Uzak Yardım** 
  - **İstenen Uzak Yardım izni**
  - **En fazla bilet saat değeri**  
  - **En fazla bilet süre**  
  - **E-posta davetiyesi yöntemi**


*[Yeni]*  [ **WIndows Defender**](#windows-defender):
- **Adobe Reader başlatma bir alt işlemde**  
- **Bir alt işlemde Office iletişimi uygulamalarını başlatma** 

*[Yeni]*  [ **Windows Defender güvenlik duvarı**](#windows-defender-firewall)
- **Güvenlik duvarı profili etki alanı**  
  - **Gelen bağlantılar engellenir**  
  - **Gerekli giden bağlantı**  
  - **Engellenen gelen bildirimler**  
  - **Güvenlik Duvarı etkin**  
- **Genel güvenlik duvarı profili**  
  - **Gelen bağlantılar engellenir**  
  - **Gerekli giden bağlantı**  
  - **Engellenen gelen bildirimler**  
  - **Güvenlik Duvarı etkin** 
  - **Bağlantı güvenliği kuralları birleştirilmemiş Grup İlkesi**   
  - **Grup İlkesi birleştirilmemiş İlkesi kuralları**  
- **Özel güvenlik duvarı profili**  
  - **Gelen bağlantılar engellenir**  
  - **Gerekli giden bağlantı**  
  - **Engellenen gelen bildirimler**  
  - **Güvenlik Duvarı etkin**  

*[Yeni]*  [ **İş için Windows Hello**](#windows-hello-for-business):  
- **Gelişmiş yanıltma, kullanılabilir olduğunda gerektirir**  
- **İş için Windows Hello'yu Yapılandır**  
- **PIN kodunda küçük harfler iste** 
- **PIN kodunda özel karakterler iste** 
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
  This policy setting allows you to manage settings for sign in options. If you enable this policy setting, you can choose from the following sign in options. Anonymous log on to disable HTTP authentication and use the guest account only for the Common Internet File System (CIFS) protocol. Prompt for user name and password to query users for user IDs and passwords. After a user is queried, these values can be used silently for the remainder of the session. Automatic log on only in Intranet zone to query users for user IDs and passwords in other zones. After a user is queried, these values can be used silently for the rest of the session. Automatic sign in with current user name and password to attempt log on using Windows NT Challenge Response (also known as NTLM authentication). If the server supports Windows NT Challenge Response, the sign in uses the user's network user name and password for log on. If If the server doesn't support Windows NT Challenge Response, the user is queried to provide the user name and password. If you disable this policy setting, sign in is set to Automatic log on only in Intranet zone. If you don't configure this policy setting, sign in is set to Automatic sign in only in Intranet zone.
  
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
