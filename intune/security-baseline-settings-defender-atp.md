---
title: Microsoft Defender Gelişmiş tehdit koruması için Intune güvenlik temelleri ayarları
titleSuffix: Microsoft Intune
description: Microsoft Defender Gelişmiş tehdit koruması yönetmek için Intune tarafından desteklenen güvenlik temel ayarları
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 05/29/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: karthib
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c6feae4d7caeeefbf9638e5018ba7b653a260f5c
ms.sourcegitcommit: 78ae22b1a7cb221648fc7346db751269d9c898b1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66373505"
---
# <a name="microsoft-defender-advanced-threat-protection-baseline-settings-for-intune"></a>Intune için Microsoft Defender Gelişmiş tehdit koruması temel ayarları

Microsoft Intune tarafından desteklenen Microsoft Defender Gelişmiş tehdit Koruması (eski adıyla Windows Defender Gelişmiş tehdit koruması) taban çizgisi ayarlarını görüntüleyin. Varsayılan değerleri bu makalede, Intune için varsayılan taban çizgisi yapılandırmasını temsil eder. Bu varsayılanlar, Intune önerilen yapılandırmasını temsil eder ve Windows Varsayılanları eşleşmeyebilir.

  Ortamınızı kullanmak için önkoşulları karşıladığı durumlarda Microsoft Defender Gelişmiş tehdit koruması temel kullanılabilir [Microsoft Defender Gelişmiş tehdit koruması](advanced-threat-protection.md#prerequisites)).




> [!NOTE]  
> WDATP temel ayarlar **Önizleme**. Önizleme ile kullanılabilir ayarlar ve bu ayarlar, bu içerik sunan Sipariş listesini portalda kullanılabilir eşleşmeyebilir. 
>
> Temel ayarlar önizlemeden sonra bu içeriği Intune'un desteklediği güvenlik taban çizgisi ayarlarını güncel bir listesi yansıtacak şekilde güncelleştirilir.

## <a name="application-guard"></a>Uygulama koruma  
Daha fazla bilgi için [WindowsDefenderApplicationGuard CSP](https://docs.microsoft.com/windows/client-management/mdm/windowsdefenderapplicationguard-csp) Windows belgelerinde.  

Microsoft Edge kullanırken, Microsoft Defender Application Guard, ortamınızı kuruluşunuz tarafından güvenilir olmayan sitelerden korur. İçinde yalıtılmış bir ağ sınırında listelenmemiş siteler kullanıcıların ziyaret ettiğinizde, siteleri bir Hyper-V sanal gözatma oturumunda açın. Güvenilen siteler, bir ağ sınırı tarafından tanımlanır.  

- **Application Guard** - *Settings/AllowWindowsDefenderApplicationGuard*  
  Seçin *Evet* güvenilmeyen siteleri bir Hyper-V sanallaştırılmış gözatma kapsayıcısında açar. Bu özelliği açmak için. Ayarlandığında *yapılandırılmadı*, cihazda ve sanallaştırılmış bir kapsayıcı içinde değil (güvenilen ve güvenilmeyen) herhangi bir sitenin açılır.  

  **Varsayılan**: Evet
 
  - **Kurumsal sitelerdeki dış içerik** - *ayarları/BlockNonEnterpriseContent*  
    Seçin *Evet* yükleme onaylanmamış Web sitelerinden içerik bloğu. Ayarlandığında *yapılandırılmadı*, kurumsal olmayan siteler, cihazda açabilirsiniz. 
 
    **Varsayılan**: Evet

  - **Pano davranışı** - *ayarları/ClipboardSettings*  
    Yerel bilgisayar ile Application Guard sanal tarayıcı arasında hangi kopyalama ve yapıştırma eylemlerine izin verileceğini seçin.  Şu seçenekler mevcuttur:
    - *Yapılandırılmadı*  
    - *Hem de block* -bilgisayar ile sanal tarayıcı arasında veri aktarımı olamaz.  
    - *Kapsayıcıya blok konak* -veri sanal tarayıcıya Bilgisayardan aktaramıyor.
    - *Blok kapsayıcıdan konağa* -veri ana makine PC'de sanal tarayıcı içeriklerini aktaramıyor.
    - *Hiçbiri block* - hiçbir içerik var. için engelleyin.  

    **Varsayılan**: Her ikisi de engelle  

- **Windows ağ yalıtımı İlkesi – kurumsal ağ etki alanı adları**  
  Daha fazla bilgi için [ilke CSP'si - NetworkIsolation](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-networkisolation) Windows belgelerinde.
  
  Etki alanları, IP adresi aralıkları ve Application Guard enterprise sitesi değerlendirir bulutta barındırılan ağ sınırlarını kurumsal kaynak listesini belirtin.  

  **Varsayılan**: securitycenter.windows.com

## <a name="application-reputation"></a>Uygulama Saygınlığı  

Daha fazla bilgi için [ilke CSP'si - SmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-smartscreen) Windows belgelerinde.

- **Doğrulanmamış dosyaları yürütülmesini engeller**  
    Kullanıcının doğrulanmamış dosyalarının çalıştırmasını engelleyin. Ayarlandığında *yapılandırılmadı*, çalışanların SmartScreen uyarılarını yoksayarak kötü amaçlı dosyalardan çalıştırın. Kümesine *Evet* böylece çalışanlar SmartScreen uyarılarını gözardı et ve kötü amaçlı dosyalardan çalıştırın.  
  
    **Varsayılan**: Evet

- **Uygulamalar ve dosyalar için SmartScreen gerektirir**  
  Kümesine *Evet* için SmartScreen Windows etkinleştirmek için.  

  **Varsayılan**: Evet

## <a name="attach-surface-reduction"></a>Yüzeyi azaltma ekleme  

- **Office uygulamalarının alt işlem türü başlatın**  
  [Saldırı yüzeyi Azaltma kuralı](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) – ayarlandığında *blok*, Office uygulamaları olmaz izin alt işlemlerin oluşturun. Office uygulamaları, Word, Excel, PowerPoint, OneNote ve erişim içerir. Bir alt işlem oluşturma özellikle başlatın veya kötü amaçlı bir yürütülebilir dosyaları indirmek için Office uygulamalarını kullanma girişimi makrosu tabanlı saldırılar için bir tipik bir kötü amaçlı yazılım davranıştır.  

  **Varsayılan**: Engelle

- **Betiği yük yürütme türü indirildi**  
  [Defender/PUAProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-puaprotection) – yükleyebilir veya yüklemeye çalışırsanız istenmeyebilecek uygulamalar için algılama düzeyini belirtin.  

  **Varsayılan**: Engelle 

- **Kimlik bilgisi türü çalmaya engelle**  
  Kümesine *etkinleştirme* için [türetilmiş etki alanı kimlik bilgilerini Credential Guard ile koruyun](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard). Windows Defender Credential Guard, parolaları yalnızca ayrıcalıklı sistem yazılımlarının erişebileceği böylece yalıtmak için sanallaştırma tabanlı güvenlik kullanır. Bu parolalara yetkisiz erişim, Pass-the-Hash veya Pass-The-Ticket gibi kimlik bilgisi hırsızlığı saldırılarına yol açabilir. Windows Defender Credential Guard, NTLM parola karmalarını, Kerberos anahtar verme anahtarı ve etki alanı kimlik bilgileri uygulamalar tarafından depolanan kimlik bilgilerini koruyarak bu saldırıları engeller.  

  **Varsayılan**: Etkinleştir

- **E-posta içeriği yürütme türü**  
  [Saldırı yüzeyi Azaltma kuralı](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) – ayarlandığında *blok*, aşağıdaki dosya türleri çalıştırın veya Microsoft Outlook veya Web postası (örneğin, Gmail.com veya Outlook.com) görünen bir e-postasındaki başlatılan bu kural bloklarını:  

  - Yürütülebilir dosyalar (örneğin, .exe, .dll veya .scr)  
  - Komut dosyaları (örneğin, bir PowerShell .ps, VisualBasic .vbs veya .js dosyası JavaScript)  
  - Betik arşiv dosyaları  

  **Varsayılan**: Engelle

- **Bir alt işlemde Adobe Reader başlatma**  
  [Saldırı yüzeyi Azaltma kuralı](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) – *etkinleştirme* Adobe Reader bir alt işlem oluşturmasını engellemek için bu kural. Sosyal mühendislik veya açıkları, kötü amaçlı yazılım indirebilir ve başlatma ek yüklerini ve Adobe Reader dışında bölün.  

  **Varsayılan**: Etkinleştir

- **Betik gizlenmiş makro kod türü**  
  [Saldırı yüzeyi Azaltma kuralı](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) – kötü amaçlı yazılım ve diğer tehditlerden karartmak veya bazı komut dosyalarında kötü amaçlı kodlarını Gizle başlatmayı deneyebilirsiniz. Bu kural çalışmasını görünen gizlenmiş olabilir önler.  
    
  **Varsayılan**: Engelle

- **Güvenilmeyen USB işlem türü**  
  [Saldırı yüzeyi Azaltma kuralı](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) – ayarlandığında *blok*, çıkarılabilir USB sürücülerden imzalanmamış veya güvenilmeyen yürütülebilir dosyaları ve SD kartları çalıştırılamaz.

  Yürütülebilir dosyalar şunları içerir:
  - Yürütülebilir dosyalar (örneğin, .exe, .dll veya .scr)
  - Komut dosyaları (örneğin, bir PowerShell .ps, VisualBasic .vbs veya .js dosyası JavaScript)  

  **Varsayılan**: Engelle

- **Ekleme türü Office uygulamalarının diğer işlem**  
  [Saldırı yüzeyi Azaltma kuralı](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) -ayarlandığında *blok*, Office uygulamaları, Word, Excel, PowerPoint ve OneNote dahil olmak üzere başka işlemlere kod ekleme yapamazsınız. Kod ekleme, kötü amaçlı yazılım tarafından virüsten koruma tarama motorları etkinliğini gizlemek girişimi kötü amaçlı kod çalıştırmak için genellikle kullanılır.  

  **Varsayılan**: Engelle

- **Office makro kodu Win32 içeri aktarmalar türü izin ver**  
  [Saldırı yüzeyi Azaltma kuralı](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) -ayarlandığında *blok*, bu kuralı, Win32 DLL'leri içeri aktarabilirsiniz makro kodu içeren bir Office dosyaları engellemeye çalışır. Word, Excel, PowerPoint ve OneNote, Office dosyaları içerir. Kötü amaçlı yazılım makro kodu'nde Office dosyaları içeri aktarma ve ardından daha fazla bulaşmasını sistem genelinde izin vermek için API çağrıları gerçekleştirmek için kullanılan Win32 DLL'leri yüklemek için kullanabilirsiniz.  

  **Varsayılan**: Engelle

- **Bir alt işlemde Office iletişimi uygulamalarını başlatma**  
  [Saldırı yüzeyi Azaltma kuralı](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) – ayarlandığında *etkinleştirme*, bu kural Outlook alt işlemlerin oluşturmasını engeller. Tarafından bir alt işlem oluşturulmasını engelleyen, bu kural, sosyal mühendislik saldırılarına karşı korur ve Outlook'ta bir güvenlik açığı ayrıcalıkların gelen yararlanma kod önler.  

  **Varsayılan**: Etkinleştir

- **Office uygulamaları yürütülebilir içerik oluşturma veya başlatma türü**  
  [Saldırı yüzeyi Azaltma kuralı](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) – ayarlandığında *blok*, Office uygulamaları, yürütülebilir içerik oluşturamıyor. Office uygulamaları, Word, Excel, PowerPoint, OneNote ve erişim içerir.  

  Bu kural, şüpheli ve kötü amaçlı eklentiler ve oluşturan veya yürütülebilir dosya başlatmak betikleri (Uzantılar) tarafından kullanılan tipik davranışları hedefler. Tipik bir kötü amaçlı yazılım yöntem budur. Office uygulamaları tarafından kullanılan uzantıları engellenir. Genellikle, bu uzantılar belirli görevleri otomatikleştirin veya kullanıcı tarafından oluşturulan eklenti özellikleri sağlayan komut dosyalarını çalıştırmak için Windows Scripting Host (.wsh dosyaları) kullanın.

  **Varsayılan**: Engelle

## <a name="bitlocker"></a>BitLocker  

Daha fazla bilgi için [BitLocker Grup İlkesi ayarlarını](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-group-policy-settings) Windows belgelerinde.  

- **Cihazları şifrele**  
  Seçin *Evet* BitLocker cihaz şifrelemesini etkinleştirmek için. Cihaz donanım ve Windows sürümüne bağlı olarak, cihaz kullanıcılarının cihazın üçüncü taraf şifreleme olduğundan emin olmak için istenebilir. Üçüncü taraf şifreleme etkinken Windows şifrelemesini açmak cihazı kararsız işlenir.  

   **Varsayılan**: Evet

- **Bit locker çıkarılabilir sürücü İlkesi**  
  Bu ilke için değerleri, BitLocker kullanan çıkarılabilir sürücülerde şifreleme için şifreleme gücünü belirler. Kuruluşlar şifreleme düzeyini (AES-256'yı AES-128'den daha güçlü) Artırılmış güvenlik denetimi. Seçerseniz *Evet* bu ayarı etkinleştirmek için bir şifreleme algoritması ve anahtar şifreleme düzeyi, sabit veri sürücüleri işletim sistemi sürücüleri ve çıkarılabilir veri sürücülerinin ayrı ayrı yapılandırabilirsiniz. Sabit ve işletim sistemi sürücüleri için XTS-AES algoritmasını kullanmanızı öneririz. Sürücü Windows 10 'un 1511 veya sonraki bir sürümü çalıştırmıyor diğer cihazlar'da kullanılıyorsa, çıkarılabilir sürücüler için AES-CBC 128-bit veya AES-CBC 256 bit kullanmalısınız. Şifreleme yöntemi değiştirme, sürücü zaten şifrelendiyse veya şifreleme sürüyorsa hiçbir etkisi olmaz. Bu gibi durumlarda, bu ilke ayarı göz ardı edilir. 

  Bit locker çıkarılabilir sürücü ilke için aşağıdaki ayarları yapılandırın:

    - **Yazma erişimi için şifreleme iste**  
      **Varsayılan**: Evet

    - **Şifreleme yöntemi**  
      **Varsayılan**: AES 128bit CBC

- **Bit locker sabit sürücü İlkesi**  
  Bu ilke için değerleri, Sabit sürücülerin şifreleme için BitLocker'ın kullandığı şifreleme gücünü belirler. Kuruluşların (AES-256'yı AES-128'den daha güçlü) Artırılmış güvenlik şifreleme düzeyini denetleyebilirsiniz. Bu ayarı etkinleştirirseniz, bir şifreleme algoritması ve anahtar şifreleme düzeyi sabit veri sürücüleri, işletim sistemi sürücüleri ve çıkarılabilir veri sürücüleri için ayrı ayrı yapılandırabilirsiniz. Sabit ve işletim sistemi sürücüleri için XTS-AES algoritmasını kullanmanızı öneririz. Sürücü Windows 10 'un 1511 veya sonraki bir sürümü çalıştırmıyor diğer cihazlar'da kullanılıyorsa, çıkarılabilir sürücüler için AES-CBC 128-bit veya AES-CBC 256 bit kullanmalısınız. Şifreleme yöntemi değiştirme, sürücü zaten şifrelendiyse veya şifreleme sürüyorsa hiçbir etkisi olmaz. Bu gibi durumlarda, bu ilke ayarı göz ardı edilir.

  Sabit sürücü ilke Bit locker için aşağıdaki ayarları yapılandırın:

    - **Yazma erişimi için şifreleme iste**  
      **Varsayılan**: Evet

    - **Şifreleme yöntemi**  
      **Varsayılan**: AES 128 bit XTS

- **Bit locker sistem sürücüsü İlkesi**  
  Bu ilke için değerleri, sistem sürücüsünün şifreleme için BitLocker'ı kullanan şifreleme gücünü belirler. Kuruluşlar, şifreleme düzeyini (AES-256'yı AES-128'den daha güçlü) Artırılmış güvenlik için denetlemek isteyebilirsiniz. Bu ayarı etkinleştirirseniz, bir şifreleme algoritması ve anahtar şifreleme düzeyi sabit veri sürücüleri, işletim sistemi sürücüleri ve çıkarılabilir veri sürücüleri için ayrı ayrı yapılandırabilirsiniz. Sabit ve işletim sistemi sürücüleri için XTS-AES algoritmasını kullanmanızı öneririz. Sürücü Windows 10 'un 1511 veya sonraki bir sürümü çalıştırmıyor diğer cihazlar'da kullanılıyorsa, çıkarılabilir sürücüler için AES-CBC 128-bit veya AES-CBC 256 bit kullanmalısınız. Şifreleme yöntemi değiştirme, sürücü zaten şifrelendiyse veya şifreleme sürüyorsa hiçbir etkisi olmaz. Bu gibi durumlarda, bu ilke ayarı göz ardı edilir.  

  Bit locker sistem sürücüsü ilkesi için aşağıdaki ayarları yapılandırın:  

  - **Şifreleme yöntemi**  
    **Varsayılan**: AES 128 bit XTS

## <a name="device-control"></a>Cihaz denetimi  

- **Tam tarama sırasında Çıkarılabilir sürücüleri tara**  
  [Defender/AllowFullScanRemovableDriveScanning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowfullscanremovabledrivescanning) -ayarlandığında *Evet*, Defender tam tarama sırasında kötü amaçlı ve istenmeyen yazılım flash sürücü gibi çıkarılabilir sürücüleri için tarar. USB cihaz dosyalarını çalıştırmadan önce defender virüsten koruma USB cihazlar üzerindeki tüm dosyaları tarar.

  Bu listede ayarlama ile ilgili: *Defender/AllowFullScanOnMappedNetworkDrives*  

  **Varsayılan**: Evet

- **Dış cihazları çekirdek DMA koruması ile uyumsuz numaralandırması**  
   Bkz: *DmaGuard/DeviceEnumerationPolicy* içinde [CSP - DmaGuard İlkesi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dmaguard#dmaguard-deviceenumerationpolicy)

  Bu ilke, dış DMA özellikli cihazlarda karşı ek güvenlik sağlar. DMA aygıt bellek ayırma ve korumalı alana alma ile uyumsuz olan dış DMA özellikli cihazlarda numaralandırma üzerinde daha fazla denetim sağlar.

  Çekirdek DMA koruması desteklenir ve sistem üretici yazılımı tarafından etkin olduğunda bu ilke yalnızca etkinleşir. Çekirdek DMA koruma İlkesi tarafından veya cihaz kullanıcısı tarafından kontrol edilemez bir platform özelliğidir. Üretim anda sistem tarafından desteklenmelidir. 

  Sistem çekirdek DMA koruması destekleyip desteklemediğini kontrol etmek için MSINFO32.exe sistem üzerinde çalışan ve gözden geçirme *çekirdek DMA koruması* Özet sayfasında alan.  

  Şu seçenekler mevcuttur: 
  - *Cihaz varsayılanı* - sonra oturum açın veya ekran kilidini, uyumlu sürücüleri izin verilen herhangi bir zamanda numaralandırmak için DMA'yı yeniden eşleme ile cihazları. DMA uyumsuz sürücülerini yeniden eşleme ile cihazları, kullanıcı ekranın kilidini açarak sonra yalnızca numaralandırılır
  - *Tümüne izin vermek* -herhangi bir zamanda tüm dış DMA özellikli PCIe cihazlarda numaralandırılır
  - *Tüm engelleme* -DMA uyumlu sürücülerini yeniden eşleme ile cihazları herhangi bir zamanda listeleme izin verilir. DMA uyumsuz sürücülerini yeniden eşleme ile cihazların başlatmak ve herhangi bir anda DMA gerçekleştirmek için hiçbir zaman izin verilir.

  **Varsayılan**: Cihaz varsayılanı

- **Cihaz tanımlayıcıları olarak donanım cihaz yükleme**  
  [DeviceInstallation/PreventInstallationOfMatchingDeviceIDs](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-preventinstallationofmatchingdeviceids) -Bu ilke Windows yüklenmesini engelleyen cihazlar için Tak ve Kullan donanım kimlikleri ve uyumlu bir listesini belirtin. Bu ilke ayarı, bir cihaza yüklemek Windows sağlayan diğer ilke ayarları üzerinden önceliklidir. Bu ilke ayarını etkinleştirirseniz (kümesine *Block donanım cihaz yükleme*), Windows, oluşturduğunuz listesinde bir cihaz olan donanım kimliği veya uyumlu kimliği görünür yüklenmesini engellenir. Uzak Masaüstü sunucuda bu ilke ayarını etkinleştirirseniz, uzak masaüstü istemcisini belirtilen cihazlarından Uzak Masaüstü sunucusuna yeniden yönlendirme ilkesi etkiler. Devre dışı bırakır veya bu ilke ayarı yapılandırmayın (kümesine *donanım cihazı yüklemeye izin ver*), cihazları, yükleme ve güncelleştirme izin verilen veya diğer ilke ayarları tarafından önlenmiş olarak.  

  **Varsayılan**: Blok donanım cihaz yükleme  

  Zaman *Block donanım cihaz yükleme* olduğu belirlenirse, aşağıdaki ayarlar kullanılabilir.
  - **Eşleşen donanım cihazları kaldırma**  
    Bu ayar yalnızca olan *donanım cihaz yükleme cihaz tanımlayıcısı tarafından* ayarlanır *Block donanım cihaz yükleme*.  

    **Varsayılan**: *Varsayılan yapılandırma*

  - **Engellenen donanım cihaz tanımlayıcıları**  
    Bu ayar yalnızca olan *donanım cihaz yükleme cihaz tanımlayıcısı tarafından* ayarlanır *Block donanım cihaz yükleme*. Bu ayarı yapılandırmak için seçeneğini genişletin, **+ Ekle**, engellemek istediğiniz donanım cihaz tanımlayıcısı belirtin.  

    **Varsayılan**: *Cihaz engellenmiş*  

- **Doğrudan bellek erişimi engelle**  
  [DataProtection/AllowDirectMemoryAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dataprotection#dataprotection-allowdirectmemoryaccess) -Bu ilke ayarı Windows bir kullanıcı oturumu kadar tüm sık erişimli takılabilir PCI aşağı akış bağlantı noktaları için bir cihazda doğrudan bellek erişimi (DMA) engellemek için kullanın. Bir kullanıcı oturum açtığında sonra Windows ana Tak PCI bağlantı noktalarına bağlı PCI cihazları numaralandırır. Her seferinde kullanıcı makine kilitler, DMA kullanıcı yeniden oturum kadar hiçbir alt cihazlarla sık erişimli Tak PCI noktalarına engellenir. Makine kilidi açıldı, zaten numaralandırılmıştır cihazlar takılı kadar çalışmaya devam eder. 

  Bu ilke ayarı, BitLocker veya cihaz şifrelemesi etkinken yalnızca zorlanır.  

  **Varsayılan**: Evet


- **Kurulum sınıflar tarafından donanım cihaz yükleme**  
  [DeviceInstallation/AllowInstallationOfMatchingDeviceSetupClasses](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-allowinstallationofmatchingdevicesetupclasses) - Bu ilke, cihaz listesini kurulum Windows yüklenmesini engelleyen bir aygıt sürücülerini yönetmek için sınıf genel olarak benzersiz tanımlayıcıları (GUID'ler) belirtebilirsiniz. Bu ilke ayarı, bir cihaza yüklemek Windows sağlayan diğer ilke ayarları üzerinden önceliklidir. Bu ilke ayarını etkinleştirirseniz (kümesine *Block donanım cihaz yükleme*), Windows yüklemenizi engellenir veya cihazını sınıf GUID Kurulum cihaz sürücüleri güncelleştirme oluşturduğunuz listede görünür. İlke ayarı, Uzak Masaüstü sunucuda bu ilke ayarını etkinleştirirseniz, uzak masaüstü istemcisini belirtilen cihazlarından Uzak Masaüstü sunucuya yönlendirilmesini etkiler. Devre dışı bırakır veya bu ilke ayarı yapılandırmayın (kümesine *donanım cihazı yüklemeye izin ver*), Windows yükleyebilir ve güncelleştirme cihazlar olarak izin verilen veya diğer ilke ayarları tarafından engellendi.  

  **Varsayılan**: Blok donanım cihaz yükleme

  Zaman *Block donanım cihaz yükleme* olduğu belirlenirse, aşağıdaki ayarlar kullanılabilir.  

  - **Eşleşen donanım cihazları kaldırma**  
    Bu ayar yalnızca olan *donanım cihaz yükleme kurulum sınıflar tarafından* ayarlanır *Block donanım cihaz yükleme*.  
 
    **Varsayılan**: *Varsayılan yapılandırma*  

  - **Engellenen donanım cihaz tanımlayıcıları**  
    Bu ayar, yalnızca donanım cihaz yükleme engellemek için donanım cihazı yükleme kurulum sınıflar tarafından ayarlandığında kullanılabilir. Bu ayarı yapılandırmak için seçeneğini genişletin, **+ Ekle**, engellemek istediğiniz donanım cihaz tanımlayıcısı belirtin.  
 
    **Varsayılan**: *Cihaz engellenmiş*

## <a name="endpoint-detection-and-response"></a>Uç nokta algılama ve yanıtlama  
Daha fazla bilgi için [WindowsAdvancedThreatProtection CSP](https://docs.microsoft.com/windows/client-management/mdm/windowsadvancedthreatprotection-csp) Windows belgelerinde.  

- **Telemetri raporlama sıklığını hızlandır** - *yapılandırma/TelemetryReportingFrequency*  

  Microsoft Defender Gelişmiş tehdit koruması telemetri raporlama sıklığını hızlandır.  

  **Varsayılan**: Evet

- **Tüm dosyalar için örnek paylaşımı** - *yapılandırma/SampleSharing*  

  Döndürür veya Microsoft Defender Gelişmiş tehdit koruması örnek paylaşımı yapılandırma parametresini ayarlar.  

  **Varsayılan**: Evet

## <a name="exploit-protection"></a>Exploit Protection  

- **Exploit Protection XML**  
  Daha fazla bilgi için [içeri aktarma, dışarı aktarma ve exploit protection yapılandırmaları dağıtma ](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/import-export-exploit-protection-emet-xml) Windows belgelerinde.  

  BT yöneticisi, istenen sistem ve kuruluşunuzdaki tüm cihazlar için uygulama risk azaltma seçenekleri temsil eden bir yapılandırma çıkış göndermek etkinleştirir. Yapılandırma, bir XML tarafından temsil edilir. 

  Yararlanma koruması uygulayan yardımcı aygıtları dağıtabilir ve bulaşma vektörlerine kullanan kötü amaçlı yazılımlardan korumak. Risk azaltma işlemleri (bir yapılandırma olarak bilinir) bir dizi oluşturmak için PowerShell ve Windows güvenlik uygulaması'nı kullanın. Ardından, bu yapılandırma, bir XML dosyası olarak dışarı aktarın ve risk azaltma ayarlarını kümesinin aynısına sahip oldukları tüm için ağınızda birden çok makineyle paylaşın.
 
  Ayrıca, dönüştürme ve exploit koruma yapılandırması XML içinde mevcut bir EMET yapılandırma XML dosyasını içeri aktarın.

- **Blok exploit protection geçersiz kılma**  
  [WindowsDefenderSecurityCenter/DisallowExploitProtectionOverride](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsdefendersecuritycenter#windowsdefendersecuritycenter-disallowexploitprotectionoverride) – kümesine *Evet* kullanıcıların Windows Defender Güvenlik Merkezi'ndeki exploit koruması ayarları alanında değişiklik yapmasını önlemek için. Devre dışı bırakın ya da bu ayarı yapılandırmayın, yerel kullanıcıların exploit koruması ayarları alanında değişiklik yapabilirsiniz.  
  **Varsayılan**: Evet  

- **Denetimli klasör erişimi**  
  Bkz: [Defender/ControlledFolderAccessAllowedApplications](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessallowedapplications) ve [Defender/ControlledFolderAccessProtectedFolders](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) 
  
   Dosya ve klasörleri kötü amaçlı uygulamaların yetkisiz değişikliklerinden korur.

  **Varsayılan**: Denetim modu

## <a name="web-network-protection"></a>Web ağ koruması  

- **Ağ koruması türü**  
  [Defender/EnableNetworkProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection) -Bu ilke Windows Defender Exploit Guard ağ koruması açıp kapatma olanak tanır. Ağ koruması, Windows Defender Exploit erişirken kimlik avı kuşku verici, siteleri yararlanma barındırma ve kötü amaçlı içerik herhangi bir uygulamadan Internet'te kullanan çalışanların koruyan koruma özelliğidir. Bu, üçüncü taraf tarayıcılar tehlikeli sitelere bağlanmasına engel içerir.  

  Olarak ayarlandığında *etkinleştirme* veya *Denetim modu*, kullanıcıları ağ korumayı açın ve bağlantı girişimleri hakkında bilgi görüntülemek için Windows Defender Güvenlik Merkezi'ni kullanabilirsiniz.  
 
  - *Etkinleştirme* kullanıcılar ve uygulamalar tehlikeli etki alanlarına bağlanmasını engeller.  
  - *Denetim modu* kullanıcılar ve uygulamalar tehlikeli etki alanlarına bağlanmasını engellemez.  

  Ayarlandığında *kullanıcı tanımlı*, kullanıcılar ve uygulamalar, olmayan engellenen tehlikeli etki alanlarına bağlanmasını ve bağlantılar hakkında bilgi Windows Defender Güvenlik Merkezi'nde kullanılamıyor.  

  **Varsayılan**: Denetim modu

- **Microsoft Edge için SmartScreen gerektirir**  
  [Tarayıcı/AllowSmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen) -Microsoft Edge, varsayılan olarak kullanıcılar olası kimlik avı kuşku verici ve kötü amaçlı yazılımlardan korumak için Windows Defender SmartScreen (açık) kullanır. Bu ilke varsayılan olarak etkindir (kümesine *Evet*) ve etkin kullanıcıların Windows Defender SmartScreen kapatmasını engeller.  Bir cihaz için etkin ilke yapılandırılmadı eşit olduğunda, kullanıcıların Windows Defender korumasız cihaz bırakan SmartScreen, kapatabilirsiniz.  

  **Varsayılan**: Evet
  
- **Kötü niyetli site erişimi engelle**  
  [Tarayıcı/PreventSmartScreenPromptOverride](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-preventsmartscreenpromptoverride) -varsayılan olarak, Microsoft Edge atlamak kullanıcılara (yoksay) kullanıcıların siteye devam etmelerine izin vererek kötü amaçlı siteleri hakkındaki Windows Defender SmartScreen uyarılarını. Bu ilke etkinleştirildiğinde ile (kümesine *Evet*), Microsoft Edge, kullanıcıların atlaması uyarıları engeller ve siteye devam etmesini engeller.  

  **Varsayılan**: Evet

- **Doğrulanmamış dosyayı indirme işlemini engelleyin**  
  [Tarayıcı/PreventSmartScreenPromptOverrideForFiles](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-preventsmartscreenpromptoverrideforfiles) -varsayılan olarak, Microsoft Edge atlamak kullanıcılara (yoksay) indirilmeye devam etmelerini sağlayan Windows Defender SmartScreen uyarılarını kötü amaçlı dosyaları hakkında doğrulanmamış dosyaları. Bu ilke etkinleştirildiğinde ile (kümesine *Evet*), kullanıcı uyarıları atlaması engellenir ve doğrulanmamış dosyaları karşıdan yükleyemiyor.  

  **Varsayılan**: Evet

## <a name="windows-defender-anti-virus----settings-review-pending-for-this-section"></a>Windows Defender virüsten koruma [ayarları gözden geçir bekleyen bu bölümün]

Daha fazla bilgi için [ilke CSP'si - Defender'ın](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender) Windows belgelerinde.

- **Microsoft web tarayıcılarında yüklenen betikleri tarama**  
  [Defender/AllowScriptScanning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowscriptscanning) – kümesine *Evet* Windows Defender betik taramayı işlevlerine izin vermek için.  

  **Varsayılan**: Evet

- **Gelen posta iletilerini tarama**  
  [Defender/AllowEmailScanning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowemailscanning) – kümesine *Evet* e-posta taramak üzere Windows Defender izin vermek için.  

  **Varsayılan**: Evet

- **Defender'ın örnek gönderimi onay türü**  
  [Defender/SubmitSamplesConsent](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent) -onay veri göndermek için Windows Defender'ı düzeyinde kullanıcı olup olmadığını denetler. Gerekli onay verilmiş, Windows Defender'ın bunları gönderir. Aksi takdirde (ve kullanıcı tarafından hiç sormak için belirtilen değilse), kullanıcı onay için sormak için kullanıcı Arabirimi başlatıldığında (zaman *bulut teslimli koruma* ayarlanır *Evet*) veri göndermeden önce.  

  **Varsayılan**: Güvenli örnekleri otomatik olarak gönder

- **Ağ denetleme Sistemi'ni (NIS)**  
  [Defender/EnableNetworkProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection) -ağ İnceleme sistemi (NIS) imzalar tarafından algılanan kötü amaçlı trafiği engelleyin.  
 
  **Varsayılan**: Evet

- **İmza güncelleştirme aralığı (saat)**  
  [Defender/SignatureUpdateInterval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-signatureupdateinterval) – saat olarak cihazın yeni Defender imzası güncelleştirmeleri ne sıklıkla denetleyeceğini belirtin.  
 
  **Varsayılan**: 4

- **Düşük CPU önceliği zamanlanmış taramaların için yapılandırma**  
  [Defender/EnableLowCPUPriority](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablelowcpupriority) – ayarlandığında *Evet*, CPU önceliği taramaları için ayarlanmış düşük. Zaman *yapılandırılmadı*, zamanlanmış taramaların CPU önceliği için hiçbir değişiklik yapılmaz.  

    **Varsayılan**: Evet

- **Defender blok erişimi koruma**  
  [Defender/AllowOnAccessProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowonaccessprotection) – ayarlandığında *Evet*, Windows Defender'ın üzerinde erişim koruması etkin.  

  **Varsayılan**: Evet

- **Gerçekleştirilecek sistem taraması türü**  
  [Defender/ScanParameter](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-scanparameter) -Defender'ın tarama türü.  

  **Varsayılan**: Hızlı tarama

- **Tüm indirmeleri tara**  
  [Defender/AllowIOAVProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowioavprotection) -ayarlandığında *Evet*, indirilen tüm dosyaları ve ekleri Defender tarar.  

  **Varsayılan**: Evet

- **Kötü amaçlı yazılım silinmeden önce gün karantinaya**  
  [Defender/DaysToRetainCleanedMalware](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-daystoretaincleanedmalware) -otomatik olarak silinmesini önce sistemde karantina öğeleri tutmak için kaç gün belirtin. Sıfır olarak ayarlandığında, Karantina öğeleri hiçbir zaman otomatik olarak silinir.  

  **Varsayılan**: 0

- **Zamanlanmış tarama başlangıç zamanı**  
  [Defender/ScheduleScanTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulescantime) – Defender'ın cihazları taramak için günün bir saati zamanlayın. 
  
  Bu listedeki ilgili seçeneği: *Defender/ScheduleScanDay*   

  **Varsayılan**: 2 ÖÖ

- **Bulut teslimli koruma**  
  [Defender/AllowCloudProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowcloudprotection) – ayarlandığında *Evet*, Windows Defender'ın bulduğu sorunları hakkında Microsoft'a bilgi gönderir. Microsoft bu bilgileri analiz edin, sizin ve diğer müşterilerin etkileyen sorunlar hakkında daha fazla bilgi edinmek ve geliştirilmiş çözümler sunar.

  Bu ilke ayarlandığında *Evet*, kullanabileceğiniz *Defender örnek gönderme onayı türü* kullanıcıların cihazlarından bilgi gönderme denetim sağlamak için.  

  **Varsayılan**: Evet

- **Defender'ın uygulama eylemi olası istenmeyen**  
  [Defender/PUAProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-puaprotection) – Windows Defender virüsten koruma tanımlayabilir ve engelleme *uygulamaları olası istenmeyen* (Koruyucu'daki) indirilmesini ve ağınızdaki Uç noktalara yükleniyor. 
 
  - Ayarlandığında *blok*, Windows Defender Koruyucu'daki engeller ve diğer tehditlere birlikte geçmişi listeler.
  - Ayarlandığında *denetim*, Windows defender Koruyucu'daki algılar ancak bunları engellemez. Windows Defender tarafından Olay Görüntüleyicisi'ni oluşturulan olayları arayarak Windows Defender karşı önlem alacağı uygulamalar hakkında daha fazla bilgi bulunabilir.  
  - Ayarlandığında *cihaz varsayılan*, PUA koruma kapalıdır.  
 
  **Varsayılan**: Engelle

- **Defender'ın bulut zaman aşımı ile genişletilmiş**  
  [Defender/CloudExtendedTimeout](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-cloudextendedtimeout) -buluttan sonuç beklerken bir dosyayı Windows Defender virüsten koruma Engellemesi gereken ek süre miktarını belirtin. Windows Defender'ın beklediği temel süre 10 saniyedir. Burada belirttiğiniz ek süre (50 saniyeye varan) bu 10 saniyenin üzerine eklenir. Çoğu zaman tarama maksimum daha kısa sürer. Bu süreyi artırmak, bulutun şüpheli klasörleri ayrıntılı olarak araştırmasına olanak verir.  

  Varsayılan olarak 0 (devre dışı) genişletilmiş zaman değerdir. Intune, bu ayarı etkinleştirin ve ek en az 20 saniye belirtirseniz önerir.  
 
  **Varsayılan**: 0

- **Arşiv dosyalarını tara**  
  [Defender/AllowArchiveScanning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowarchivescanning) – kümesine *Evet* Windows Defender'ın arşiv dosyalarını tara sağlamak için.  

  **Varsayılan**: Evet

- **Defender'ın sistem tarama zamanlaması**  
  [Defender/ScheduleScanDay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulescanday) -zamanlama hangi gününde Defender cihazları tarar. 
 
  Bu listedeki ilgili seçeneği: *Defender/ScheduleScanTime*

  **Varsayılan**: Kullanıcı tanımlı

- **Davranış izleme**  
  [Defender/AllowBehaviorMonitoring](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowbehaviormonitoring) – kümesine *Evet* Windows Defender davranış izleme işlevselliğini etkinleştirmek için. Windows 10'da katıştırılmış, Windows Defender davranış izlemeyi sensörlerden toplar ve işletim sisteminden davranış sinyalleri işlemek ve bu sensör verilerini özel, yalıtılmış, bulut Örneğiniz için Microsoft Defender ATP gönderir.  

  **Varsayılan**: Evet

- **Ağ klasörlerinden açılan dosyaları tara**  
  [Defender/AllowScanningNetworkFiles](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowscanningnetworkfiles) – kümesine *Evet* Windows Defender'ın ağ dosyalarını tara sağlamak için. Kullanıcı Algılanan kötü amaçlı yazılım salt okunur dosyaların kaldırmak mümkün olmayacaktır.  

  **Varsayılan**: Evet

- **Defender'ın bulut engelleme düzeyi**  
  [Defender/CloudBlockLevel](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-cloudblocklevel) – nasıl agresif Windows Defender virüsten koruma belirlemek için bu ilke, engelleme ve şüpheli dosyaları tarama kullanın. Şu seçenekler mevcuttur:

  - Yüksek - agresif bir şekilde (hatalı pozitif sonuçları büyük olasılığını) istemci performansını en iyi duruma getirme sırasında bilinmeyen yürütülebilir dosyaların çalışmasını engelle
  - Yüksek artı - titizlikle bilinmeyen blok dosyaları ve (istemci performansını etkileyebilecek) ek koruma önlemleri uygulayın
  - Sıfır tolerans - tüm bilinmeyen yürütülebilir dosyaları engeller

  **Varsayılan**: Yapılandırılmadı

- **Gerçek zamanlı izleme**  
  [Defender/AllowRealtimeMonitoring](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowrealtimemonitoring) – kümesine *Evet* Windows Defender'ın gerçek zamanlı izlemeye izin vermek için.  

  **Varsayılan**: Evet

- **Bir tarama sırasında CPU kullanım sınırı**  
  [Defender/AvgCPULoadFactor](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-avgcpuloadfactor) – Windows Defender, tarama sırasında kullanabileceğiniz belirtin en yüksek ortalama CPU kullanım yüzdesi.  

  **Varsayılan**: 50

- **Tam tarama sırasında eşlenmiş ağ sürücülerini tara**  
  [Defender/AllowFullScanOnMappedNetworkDrives](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowfullscanonmappednetworkdrives) -kümesine *Evet* Windows Defender'ın ağ dosyalarını tara sağlamak için. Kullanıcı, salt okunur dosyaları Algılanan kötü amaçlı yazılımı kaldıramaz,

  Bu listede ayarlama ile ilgili: *Defender/AllowScanningNetworkFiles*

  **Varsayılan**: Evet

- **Defender'a son kullanıcı erişimi engelle**  
  [Defender/AllowUserUIAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowuseruiaccess) – kümesine *Evet* için cihazlarında Windows Defender kullanıcı arabirimini son kullanıcılardan erişimi engelleyin.  

  **Varsayılan**: Evet

- **Hızlı tarama başlangıç zamanı**  
  [Defender/ScheduleQuickScanTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulequickscantime) -Defender hızlı tarama çalıştıracak biçimde için günün bir saati zamanlayın.  

  **Varsayılan**: 2 ÖÖ

## <a name="windows-defender-firewall"></a>Windows Defender Güvenlik Duvarı
Daha fazla bilgi için [güvenlik duvarı CSP](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp) Windows belgelerinde.

- **Silmeden önce güvenlik ilişkilendirme boşta kalma süresi** - *MdmStore/Global/SaIdleTime*   
  Ağ trafiği bu kadar saniye görülen değil sonra güvenlik ilişkilendirmeleri silinir.  
  **Varsayılan**: 300

- **Dosya Aktarım Protokolü** - *MdmStore/genel/DisableStatefulFtp*   
  Durum bilgisi olan Dosya Aktarım Protokolü (FTP) engeller.  
  **Varsayılan**: Evet

- **Paket sıraya alma** - *MdmStore/Global/EnablePacketQueue*    
  Metin iletme için IPSec tünel ağ geçidi senaryosunda temizleyin ve alma tarafında yazılım ölçeklendirmenin şifreli alma nasıl etkinleştirildiğini belirtin. Bu, paket sırasının korunmasını sağlar.  
  **Varsayılan**: Cihaz varsayılanı

- **Güvenlik duvarı profili etki alanı** - *FirewallRuleName/FirewallRules/profilleri*  
  Kurala ait olduğu profillerin belirtir: Domain, Private, Public. Bu değer, etki alanlarına bağlı ağlara profilini temsil eder.  

  Kullanılabilir ayarlar:  
  - **Gerekli çok noktaya yayına tek noktaya yayın yanıtları**  
    **Varsayılan**: Evet

  - **Birleştirilmiş Grup İlkesi'nden yetkili uygulama kuralları**  
    **Varsayılan**: Evet

  - **Engellenen gelen bildirimler**  
    **Varsayılan**: Evet

  - **Birleştirilmiş Grup İlkesi'nden genel bağlantı noktası kuralları**  
    **Varsayılan**: Evet

  - **Gizli mod engellendi**  
    **Varsayılan**: Evet

  - **Güvenlik Duvarı etkin**  
    **Varsayılan**: İzin Verildi

  - **Bağlantı güvenliği kuralları birleştirilmemiş Grup İlkesi**  
    **Varsayılan**: Evet

  - **Grup İlkesi birleştirilmemiş İlkesi kuralları**  
    **Varsayılan**: Evet

- **Güvenlik duvarı profili genel** - *FirewallRuleName/FirewallRules/profilleri*  
  Kurala ait olduğu profillerin belirtir: Domain, Private, Public. Bu değer, ortak ağlar için profil temsil eder. Bu ağlar genel sunucu ana yöneticiler tarafından sınıflandırılır. Sınıflandırma, ana bilgisayar ağa bağlanan ilk kez gerçekleşir. Genellikle bu havaalanları, kahve dükkanları ve burada ağ veya ağ yöneticisine eşlerden güvenilir olmayan diğer ortak bir yerde ağlardır.  

  Kullanılabilir ayarlar:

  - **Gelen bağlantılar engellenir**  
    **Varsayılan**: Evet 

  - **Gerekli çok noktaya yayına tek noktaya yayın yanıtları**  
    **Varsayılan**: Evet  

  - **Gereken gizli modu**  
    **Varsayılan**: Evet 
 
  - **Gerekli giden bağlantı**  
    **Varsayılan**: Evet  

  - **Birleştirilmiş Grup İlkesi'nden yetkili uygulama kuralları**  
    **Varsayılan**: Evet  

  - **Engellenen gelen bildirimler**  
    **Varsayılan**: Evet  

  - **Birleştirilmiş Grup İlkesi'nden genel bağlantı noktası kuralları**  
    **Varsayılan**: Evet

  - **Gizli mod engellendi**  
    **Varsayılan**: Evet

  - **Güvenlik Duvarı etkin**  
    **Varsayılan**: İzin Verildi  

  - **Bağlantı güvenliği kuralları birleştirilmemiş Grup İlkesi**  
    **Varsayılan**: Evet  

  - **Gerekli gelen trafik**  
    **Varsayılan**: Evet

  - **Grup İlkesi birleştirilmemiş İlkesi kuralları**  
    **Varsayılan**: Evet  

- **Güvenlik duvarı profili özel** - *FirewallRuleName/FirewallRules/profilleri*  
  Kurala ait olduğu profillerin belirtir: Domain, Private, Public. Bu değer özel ağlar için profil temsil eder.  

  Kullanılabilir ayarlar: 

  - **Gelen bağlantılar engellenir**  
    **Varsayılan**: Evet

  - **Gerekli çok noktaya yayına tek noktaya yayın yanıtları**  
    **Varsayılan**: Evet

  - **Gereken gizli modu**  
    **Varsayılan**: Evet

  - **Gerekli giden bağlantı**  
    **Varsayılan**: Evet

  - **Engellenen gelen bildirimler**  
    **Varsayılan**: Evet

  - **Birleştirilmiş Grup İlkesi'nden genel bağlantı noktası kuralları**  
    **Varsayılan**: Evet

  - **Gizli mod engellendi**  
    **Varsayılan**: Evet  

  - **Güvenlik Duvarı etkin**  
    **Varsayılan**: İzin Verildi

  - **Grup İlkesi birleştirilmemiş yetkili uygulama kuralları**  
    **Varsayılan**: Evet

  - **Bağlantı güvenliği kuralları birleştirilmemiş Grup İlkesi**  
    **Varsayılan**: Evet

  - **Gerekli gelen trafik**  
    **Varsayılan**: Evet

  - **Grup İlkesi birleştirilmemiş İlkesi kuralları**  
    **Varsayılan**: Evet  

- **Güvenlik Duvarı önceden paylaşılan anahtar kodlama yöntemi**  
  **Varsayılan**: UTF8

- **Sertifika iptal listesi doğrulaması**  
  **Varsayılan**: Cihaz varsayılanı

## <a name="windows-hello-for-business"></a>İş İçin Windows Hello  

Daha fazla bilgi için [PassportForWork CSP](https://docs.microsoft.com/windows/client-management/mdm/passportforwork-csp) Windows belgelerinde.

- **İş için Windows Hello yapılandırma** - *Tenantıd/ilkeler/UsePassportForWork*    
  Windows iş için Hello ile Windows parolaları, akıllı kartlar ve sanal akıllı kartları değiştirerek imzalamak için bir alternatifidir.  

  Etkinleştirin veya bu ilke ayarı yapılandırmayın, cihaz Windows iş için Hello sağlar. Bu ilke ayarını devre dışı bırakırsanız, cihazı Windows iş için Hello herhangi bir kullanıcı için sağlama değil.

  Intune, Windows Hello'yu devre dışı bırakma desteklemiyor. Bunun yerine, Windows iş için Hello (Evet) etkinleştirmek veya Windows Hello doğrudan yapılandırmak için bir ilke yapılandırabilirsiniz (yapılandırılmadı). Yapılandırılmadığında, bir cihaz yapılandırma etkinleştirin veya bu özelliği devre dışı diğer ilkesiyle alabilir.  

  **Varsayılan**: Evet  

- **PIN kodunda küçük harfler iste** - *Tenantıd/ilkeler/PINComplexity/LowercaseLetters*  
  **Varsayılan**: İzin Verildi  

- **PIN kodunda özel karakterler iste** - *Tenantıd/ilkeler/PINComplexity/SpecialCharacters*  
  **Varsayılan**: İzin Verildi  

- **PIN kodunda büyük harfler iste** - *Tenantıd/ilkeler/PINComplexity/UppercaseLetters*   
  **Varsayılan**: İzin Verildi  

