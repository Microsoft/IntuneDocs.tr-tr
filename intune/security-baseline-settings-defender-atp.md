---
title: Microsoft Defender Gelişmiş tehdit koruması için Intune güvenlik temelleri ayarları
titleSuffix: Microsoft Intune
description: Microsoft Defender Gelişmiş tehdit koruması 'nı yönetmek için Intune tarafından desteklenen güvenlik taban çizgisi ayarları
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/25/2019
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
ms.openlocfilehash: eee3d4187dd513cd3945e86aff478fe96b341660
ms.sourcegitcommit: 1d4aec7b79c70d35ec3fc29df6ff9c6a1403412e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/25/2019
ms.locfileid: "68491923"
---
# <a name="microsoft-defender-advanced-threat-protection-baseline-settings-for-intune"></a>Intune için Microsoft Defender Gelişmiş tehdit koruması temel ayarları

Microsoft Intune tarafından desteklenen Microsoft Defender Gelişmiş tehdit koruması (eski adıyla Windows Defender Gelişmiş tehdit koruması) taban çizgisi ayarlarını görüntüleyin. Gelişmiş tehdit koruması (ATP) taban çizgisi Varsayılanları, ATP için önerilen yapılandırmayı temsil eder ve diğer güvenlik temelleri için temel varsayılanlarla eşleşmeyebilir.  

Microsoft Defender Gelişmiş tehdit koruması temeli, ortamınız [Microsoft Defender Gelişmiş tehdit koruması](advanced-threat-protection.md#prerequisites)kullanımı için önkoşulları karşılıyorsa kullanılabilir. 

Bu taban çizgisi fiziksel cihazlar için iyileştirilmiştir ve şu anda sanal makinelerde (VM) veya VDı uç noktalarında kullanılması önerilmez. Belirli taban çizgisi ayarları, sanallaştırılmış ortamlarda uzak etkileşimli oturumları etkileyebilir. Daha fazla bilgi için bkz. Windows belgelerindeki [Microsoft Defender ATP güvenlik temeliyle uyumluluğu artırma](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline) .


> [!NOTE]  
> ATP taban çizgisi ayarları önizlemededir . Önizleme aşamasında, kullanılabilir ayarların listesi ve bu içeriğin bu ayarları sunduğu sıra, portalda kullanılabilir olanlarla eşleşmeyebilir.  
>
> Taban çizgisi ayarları önizlemeden sonra bu içerik, Intune 'un desteklediği güvenlik temeli ayarlarının geçerli bir listesini yansıtacak şekilde güncelleştirilir.

## <a name="application-guard"></a>Application Guard  
Daha fazla bilgi için Windows belgelerindeki [Windowssavunma Derapplicationguard CSP](https://docs.microsoft.com/windows/client-management/mdm/windowsdefenderapplicationguard-csp) bölümüne bakın.  

Microsoft Edge kullanırken, Microsoft Defender Application Guard, ortamınızı kuruluşunuz tarafından güvenilmeyen sitelerden korur. Kullanıcılar yalıtılmış ağ sınırlarında listelenmeyen siteleri ziyaret ettiğinde, siteler bir Hyper-V sanal gözatma oturumunda açılır. Güvenilen siteler bir ağ sınırı tarafından tanımlanır.  

- **Application Guard** - *ayarları/allowwindowssavunma derapplicationguard*  
  Güvenilmeyen siteleri bir Hyper-V sanallaştırılmış gözatma kapsayıcısında açan bu özelliği açmak için *Evet* ' i seçin. *Yapılandırılmadı*olarak ayarlandığında, cihazda herhangi bir site (güvenilen ve güvenilmeyen) açılır ve sanallaştırılmış bir kapsayıcıda değildir.  

  **Varsayılan**: Evet
 
  - **Enterprise Sites** - *Settings/blocknonenterprisecontent* üzerindeki dış içerik  
    Onaylanmamış Web sitelerindeki içeriğin yüklenmesini engellemek için *Evet* ' i seçin. *Yapılandırılmadı*olarak ayarlandığında, kurumsal olmayan siteler cihazda açılabilir. 
 
    **Varsayılan**: Evet

  - **Pano davranışı** - *ayarları/clipboardsettings*  
    Yerel BILGISAYAR ile Application Guard sanal tarayıcısı arasında kopyalama ve yapıştırma eylemlerine izin verileceğini seçin.  Şu seçenekler mevcuttur:
    - *Yapılandırılmadı*  
    - *Her Iki blok de* bilgisayar ile sanal tarayıcı arasında aktarım yapamıyor.  
    - *Ana bilgisayarı kapsayıcıya engelle* -veriler bilgisayardan sanal tarayıcıya aktarılamaz.
    - *Kapsayıcıyı konağa engelle* -veriler sanal tarayıcıdan ana bilgisayar bilgisayarına aktarılamaz.
    - *Blok yok* -içerik için blok yok.  

    **Varsayılan**: Her ikisini engelle  

- **Windows ağ yalıtımı ilkesi – kurumsal ağ etki alanı adları**  
  Daha fazla bilgi için Windows belgelerindeki [Ilke CSP-NetworkIsolation](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-networkisolation) bölümüne bakın.
  
  Uygulama koruması 'nın kurumsal siteler olarak davrandığı bulutta barındırılan etki alanları, IP adresi aralıkları ve ağ sınırları olarak kurumsal kaynak listesini belirtin.  

  **Varsayılan**: SecurityCenter.Windows.com

## <a name="application-reputation"></a>Uygulama saygınlığı  

Daha fazla bilgi için Windows belgelerindeki [Ilke CSP-SmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-smartscreen) bölümüne bakın.

- **Doğrulanmamış dosyaların yürütülmesini engelle**  
    Kullanıcının doğrulanmamış dosyaları çalıştırmasını engelleyin. *Yapılandırılmadı*olarak ayarlandığında, çalışanlar SmartScreen uyarılarını yoksayabilir ve kötü amaçlı dosyalar çalıştırabilir. Çalışanların SmartScreen uyarılarını yok sayabilmesi ve kötü amaçlı dosyalar çalıştırmasına izin vermek için *Evet* olarak ayarlayın.  
  
    **Varsayılan**: Evet

- **Uygulamalar ve dosyalar için SmartScreen gerektir**  
  Windows için SmartScreen 'ı etkinleştirmek üzere *Evet* olarak ayarlayın.  

  **Varsayılan**: Evet

## <a name="attack-surface-reduction"></a>Saldırı Yüzeyini Azaltma  

- **Office uygulamaları alt işlem türünü Başlat**  
  [Saldırı yüzeyi Azaltma kuralı](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) – *blok*olarak ayarlandığında Office uygulamalarının alt işlem oluşturmasına izin verilmez. Office uygulamaları, Word, Excel, PowerPoint, OneNote ve Access ' i içerir. Özel bir işlemin oluşturulması, özellikle de kötü amaçlı dosyaları başlatmak veya indirmek üzere Office uygulamalarını kullanmaya çalışacak makro tabanlı saldırılar için tipik bir kötü amaçlı yazılım davranışıdır.  

  **Varsayılan**: Engelle

- **Betiği indirilen yük yürütme türü**  
  [Defender/PUAProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-puaprotection) – karşıdan yükleyen veya yüklemeyi deneyen istenmeyebilecek uygulamalar için bir algılama düzeyi belirtir.  

  **Varsayılan**: Engelle 

- **Kimlik bilgisi hırsızlığı türünü engelle**  
  [Türetilmiş etki alanı kimlik bilgilerini Credential Guard Ile korumak](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard)için *etkin* olarak ayarlayın. Windows Defender Credential Guard, gizli dizileri yalnızca ayrıcalıklı sistem yazılımlarının erişebileceği şekilde yalıtmak için sanallaştırma tabanlı güvenlik kullanır. Bu parolalara yetkisiz erişim, Pass-the-Hash veya Pass-The-Ticket gibi kimlik bilgisi hırsızlığı saldırılarına yol açabilir. Windows Defender Credential Guard, NTLM parola karmalarını, Kerberos bileti verme biletlerini ve uygulamalar tarafından etki alanı kimlik bilgileri olarak depolanan kimlik bilgilerini koruyarak bu saldırıları engeller.  

  **Varsayılan**: Etkinleştir

- **E-posta içeriği yürütme türü**  
  [Saldırı yüzeyi Azaltma kuralı](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) – *blok*olarak ayarlandığında, bu kural aşağıdaki dosya türlerinin Microsoft Outlook veya Web postasından 'de (gmail.com veya Outlook.com gibi) görülen bir e-postadan çalıştırılmasını ya da başlatılmasını engeller:  

  - Yürütülebilir dosyalar (. exe,. dll veya. scr gibi)  
  - Betik dosyaları (PowerShell. PS, VisualBasic. vbs veya JavaScript. js dosyası gibi)  
  - Betik Arşivi dosyaları  

  **Varsayılan**: Engelle

- **Bir alt işlemde Adobe Reader başlatma**  
  [Saldırı yüzeyi Azaltma kuralı](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) – Adobe Reader 'ın bir alt işlem oluşturmasını engellemek için bu kuralı *etkinleştirin* . Kötü amaçlı yazılım, sosyal mühendisler veya güvenlik açıkları aracılığıyla ek yükleri indirebilir ve başlatabilir ve Adobe Reader 'dan daha fazla kesebilir.  

  **Varsayılan**: Etkinleştir

- **Betik gizleme makro kod türü**  
  [Saldırı yüzeyi Azaltma kuralı](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) – kötü amaçlı yazılım ve diğer tehditler bazı betik dosyalarında kötü amaçlı kodlarını gizlemeyi veya gizlemeyi deneyebilir. Bu kural, görünmeyen görünen betiklerin çalışmasını engeller.  
    
  **Varsayılan**: Engelle

- **Güvenilmeyen USB işlem türü**  
  [Saldırı yüzeyi Azaltma kuralı](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) – USB çıkarılabilir sürücülerden *blok*, imzasız veya güvenilmeyen yürütülebilir dosyalar olarak ayarlandığında ve SD kartları çalıştırılamaz.

  Yürütülebilir dosyalar şunları içerir:
  - Yürütülebilir dosyalar (. exe,. dll veya. scr gibi)
  - Betik dosyaları (PowerShell. PS, VisualBasic. vbs veya JavaScript. js dosyası gibi)  

  **Varsayılan**: Engelle

- **Office uygulamaları diğer işlem ekleme türü**  
  [Saldırı yüzeyi Azaltma kuralı](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) - *blok*olarak ayarlandığında Word, Excel, PowerPoint ve OneNote dahil Office uygulamaları diğer işlemlere kod ekleyemez. Kod ekleme, genellikle kötü amaçlı yazılım tarafından virüsten koruma tarama altyapılarından etkinliği gizleme girişimi için kullanılır.  

  **Varsayılan**: Engelle

- **Office makro kodu Win32 içeri aktarmalar türüne izin ver**  
  [Saldırı yüzeyi Azaltma kuralı](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) - *blok*olarak ayarlandığında, bu kural Win32 DLL 'leri içeri aktarabilen makro kodunu içeren Office dosyalarını engellemeye çalışır. Office dosyaları Word, Excel, PowerPoint ve OneNote içerir. Kötü amaçlı yazılım, sistem genelinde daha fazla bulaşma sağlamak üzere API çağrıları yapmak için kullanılan Win32 DLL 'Lerini içeri aktarmak ve yüklemek üzere Office dosyalarındaki makro kodunu kullanabilir.  

  **Varsayılan**: Engelle

- **Office iletişim uygulamaları bir alt işlemde başlatılır**  
  [Saldırı yüzeyi Azaltma kuralı](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) – *Etkinleştir*olarak ayarlandığında, bu kural Outlook 'un alt işlem oluşturmasını engeller. Bir alt işlemin oluşturulması engellenerek, bu kural sosyal mühendislik saldırılarına karşı koruma sağlar ve Outlook 'taki bir güvenlik açığını kullanarak açıktan yararlanma kodunu engeller.  

  **Varsayılan**: Etkinleştir

- **Office uygulamaları yürütülebilir içerik oluşturma veya başlatma türü**  
  [Saldırı yüzeyi Azaltma kuralı](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) – *blok*olarak ayarlandığında Office uygulamaları yürütülebilir içerik oluşturamaz. Office uygulamaları, Word, Excel, PowerPoint, OneNote ve Access ' i içerir.  

  Bu kural, şüpheli ve kötü amaçlı eklentiler ve yürütülebilir dosyalar oluşturan ya da Başlatan olağan dışı eklentiler ve betikler (Uzantılar) tarafından kullanılan tipik davranışları hedefler. Bu tipik bir kötü amaçlı yazılım tekniğidir. Uzantıların Office uygulamaları tarafından kullanılması engellenir. Genellikle, bu uzantılar belirli görevleri otomatikleştiren betikleri çalıştırmak veya Kullanıcı tarafından oluşturulan eklenti özellikleri sağlamak için Windows komut dosyası konağını (. WSH dosyaları) kullanır.

  **Varsayılan**: Engelle

## <a name="bitlocker"></a>BitLocker  

Daha fazla bilgi için, Windows belgelerindeki [BitLocker Grup İlkesi ayarları](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-group-policy-settings) .  

- **Cihazları şifreleme**  
  BitLocker cihaz şifrelemesini etkinleştirmek için *Evet* ' i seçin. Cihaz donanımına ve Windows sürümüne bağlı olarak, cihaz kullanıcılarının cihazda üçüncü taraf şifreleme olmadığını onaylamasını istenebilir. Üçüncü taraf şifreleme etkinken Windows şifrelemeyi açmak, cihazı kararsız olarak işleyecek.  

   **Varsayılan**: Evet

- **Bit dolabı çıkarılabilir sürücü ilkesi**  
  Bu ilkenin değerleri BitLocker 'ın çıkarılabilir sürücüleri şifrelemek için kullandığı şifre gücünü belirlemektir. Kuruluşlar, artırılmış güvenlik için şifreleme düzeyini denetler (AES-256, AES-128 ' den daha güçlüdür). Bu ayarı etkinleştirmek için *Evet* ' i seçerseniz, sabit veri sürücüleri, işletim sistemi sürücüleri ve çıkarılabilir veri sürücüleri için bir şifreleme algoritması ve anahtar şifreleme gücü yapılandırabilirsiniz. Sabit ve işletim sistemi sürücüleri için, XTS-AES algoritmasını kullanmanızı öneririz. Sürücü, Windows 10, sürüm 1511 veya üzerini çalıştırmayan diğer cihazlarda kullanılıyorsa, çıkarılabilir sürücüler için AES-CBC 128-bit veya AES-CBC 256-bit ' i kullanmanız gerekir. Sürücü zaten şifrelendiyse veya şifreleme devam ediyorsa şifreleme yönteminin değiştirilmesi etkisizdir. Bu durumlarda, bu ilke ayarı yok sayılır. 

  Bit dolabı çıkarılabilir sürücü ilkesi için aşağıdaki ayarları yapılandırın:

  - **Yazma erişimi için şifreleme gerektir**  
    **Varsayılan**: Evet

  - **Şifreleme yöntemi**  
    **Varsayılan**: AES 128bit CBC

- **Bit dolabı sabit sürücü ilkesi**  
  Bu ilkenin değerleri BitLocker 'ın sabit sürücüleri şifrelemek için kullandığı şifre gücünü belirlemektir. Kuruluşlar, artırılmış güvenlik için şifreleme düzeyini denetleyebilir (AES-256, AES-128 ' den daha güçlüdür). Bu ayarı etkinleştirirseniz, sabit veri sürücüleri, işletim sistemi sürücüleri ve çıkarılabilir veri sürücüleri için şifreleme algoritması ve anahtar şifreleme gücü ayrı ayrı yapılandırabilirsiniz. Sabit ve işletim sistemi sürücüleri için, XTS-AES algoritmasını kullanmanızı öneririz. Sürücü, Windows 10, sürüm 1511 veya üzerini çalıştırmayan diğer cihazlarda kullanılıyorsa, çıkarılabilir sürücüler için AES-CBC 128-bit veya AES-CBC 256-bit ' i kullanmanız gerekir. Sürücü zaten şifrelendiyse veya şifreleme devam ediyorsa şifreleme yönteminin değiştirilmesi etkisizdir. Bu durumlarda, bu ilke ayarı yok sayılır.

  Bit dolabı sabit sürücü ilkesi için aşağıdaki ayarları yapılandırın:

  - **Yazma erişimi için şifreleme gerektir**  
    **Varsayılan**: Evet

  - **Şifreleme yöntemi**  
    **Varsayılan**: AES 128bit XTS

- **Bit dolabı sistem sürücüsü ilkesi**  
  Bu ilkenin değerleri BitLocker 'ın sistem sürücüsünü şifrelemek için kullandığı şifre gücünü belirlemektir. Kuruluşlar, artırılmış güvenlik için şifreleme düzeyini denetlemek isteyebilir (AES-256, AES-128 ' den daha güçlüdür). Bu ayarı etkinleştirirseniz, sabit veri sürücüleri, işletim sistemi sürücüleri ve çıkarılabilir veri sürücüleri için şifreleme algoritması ve anahtar şifreleme gücü ayrı ayrı yapılandırabilirsiniz. Sabit ve işletim sistemi sürücüleri için, XTS-AES algoritmasını kullanmanızı öneririz. Sürücü, Windows 10, sürüm 1511 veya üzerini çalıştırmayan diğer cihazlarda kullanılıyorsa, çıkarılabilir sürücüler için AES-CBC 128-bit veya AES-CBC 256-bit ' i kullanmanız gerekir. Sürücü zaten şifrelendiyse veya şifreleme devam ediyorsa şifreleme yönteminin değiştirilmesi etkisizdir. Bu durumlarda, bu ilke ayarı yok sayılır.  

  Bit dolabı sistem sürücüsü ilkesi için aşağıdaki ayarları yapılandırın:  

  - **Şifreleme yöntemi**  
    **Varsayılan**: AES 128bit XTS

## <a name="device-control"></a>Cihaz denetimi  

- **Tam tarama sırasında çıkarılabilir sürücüleri tarama**  
  [Defender/AllowFullScanRemovableDriveScanning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowfullscanremovabledrivescanning) - *Evet*olarak ayarlandığında, Defender, tam tarama sırasında Flash sürücüleri gibi çıkarılabilir sürücülerde kötü amaçlı ve istenmeyen yazılımları tarar. Defender virüsten koruma, USB cihazdaki dosyaların çalıştırılabilmesi için önce USB cihazlarındaki tüm dosyaları tarar.

  Bu listedeki ilgili ayar: *Defender/AllowFullScanOnMappedNetworkDrives*  

  **Varsayılan**: Evet

- **Çekirdek DMA koruması ile uyumsuz dış cihazların numaralandırması**  
   Bkz. [Ilke CSP-dmaguard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dmaguard#dmaguard-deviceenumerationpolicy) 'Da *dmaguard/DeviceEnumerationPolicy*

  Bu ilke, dış DMA özellikli cihazlara karşı ek güvenlik sağlar. DMA cihaz belleği yalıtımı ve korumalı alana alma uyumlu olmayan harici DMA özellikli cihazların numaralandırılması üzerinde daha fazla denetim sağlar.

  Bu ilke, yalnızca çekirdek DMA koruması desteklenirken ve Sistem bellenimi tarafından etkinleştirildiğinde devreye girer. Çekirdek DMA koruması, ilke tarafından veya bir cihazın kullanıcısı tarafından denetlenebilecek bir platform özelliğidir. Üretim sırasında sistem tarafından desteklenmelidir. 

  Sistemin çekirdek DMA korumasını destekleyip desteklemediğini denetlemek için, sistemde MSINFO32. exe ' yi çalıştırın ve Özet sayfasında *çekırdek DMA koruması* alanını gözden geçirin.  

  Şu seçenekler mevcuttur: 
  - *Cihaz varsayılanı* -oturum açma veya ekran kilidini açma SONRASıNDA, DMA yeniden eşleme uyumlu sürücülere sahip cihazların herhangi bir zamanda numaralandırılmaya izin verilir. DMA yeniden eşleme uyumsuz sürücüleri olan cihazlar yalnızca Kullanıcı ekranın kilidini açana kadar numaralandırılır
  - Tüm dış DMA özellikli PCIe cihazlarının *tümüne Izin ver* , her zaman numaralandırılır
  - *Blok tümünü engelle* : DMA yeniden eşleme uyumlu sürücüleri olan cihazların herhangi bir zamanda numaralandırılmaya izin verilir. DMA yeniden eşleme uyumlu olmayan sürücülere sahip cihazların hiçbir zaman DMA olarak başlayamaz ve gerçekleştirmesine izin verilmez.

  **Varsayılan**: Cihaz varsayılanı

- **Cihaz tanımlayıcılarına göre donanım cihazı yüklemesi**  
  [Deviceınstallation/Preventınstaldmatchingdevicıdds](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-preventinstallationofmatchingdeviceids) -bu Ilkeyle, Windows 'un yüklemesi engellenen cihazlar için Tak ve Kullan donanım kimliklerinin ve uyumlu kimliklerin bir listesini belirtirsiniz. Bu ilke ayarı, Windows 'un bir cihaz yüklemesine izin veren diğer tüm ilke ayarlarından önceliklidir. Bu ilke ayarını etkinleştirirseniz ( *donanım cihazı yüklemeyi engelleyecek*şekilde ayarlanır), Windows 'un, oluşturduğunuz LISTEDE donanım kimliği veya uyumlu kimliği görünen bir cihaz yüklemesi engellenir. Bu ilke ayarını Uzak Masaüstü sunucusunda etkinleştirirseniz, ilke belirtilen cihazların uzak masaüstü istemcisinden uzak masaüstü sunucusuna yönlendirilmesini etkiler. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız ( *donanım cihazı yüklemeye Izin ver*olarak ayarlanır), cihazlar diğer ilke ayarları tarafından izin verilen veya engellenen şekilde yükleyebilir ve güncelleştirebilir.  

  **Varsayılan**: Donanım cihazını yüklemeyi engelle  

  *Donanım aygıtı yüklemesi engellenme* seçildiğinde aşağıdaki ayarlar kullanılabilir.
  - **Eşleşen donanım cihazlarını kaldırma**  
    Bu ayar yalnızca *cihaz tanımlayıcılarına göre donanım cihaz yüklemesi* , *donanım cihazı yüklemeyi engelleyecek*şekilde ayarlandığında kullanılabilir.  

    **Varsayılan**: *Varsayılan yapılandırma yok*

  - **Engellenen donanım cihaz tanımlayıcıları**  
    Bu ayar yalnızca *cihaz tanımlayıcılarına göre donanım cihaz yüklemesi* , *donanım cihazı yüklemeyi engelleyecek*şekilde ayarlandığında kullanılabilir. Bu ayarı yapılandırmak için, seçeneğini genişletin, **+ Ekle**' yi seçin ve ardından engellemek istediğiniz donanım cihaz tanımlayıcısını belirtin.  

    **Varsayılan**: *Hiçbir cihaz engellenmiyor*  

- **Doğrudan bellek erişimini engelle**  
  [DataProtection/AllowDirectMemoryAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dataprotection#dataprotection-allowdirectmemoryaccess) -bir Kullanıcı Windows 'a oturum açana kadar, bir cihazdaki tüm ETKIN takılabilir PCI aşağı akış bağlantı noktalarında doğrudan bellek ERIŞIMINI (DMA) engellemek için bu ilke ayarını kullanın. Kullanıcı oturum açtıktan sonra Windows, ana bilgisayar eklentisi PCI bağlantı noktalarına bağlı PCI cihazlarını numaralandırır. Kullanıcı makineyi her kilitlediğinde, Kullanıcı yeniden oturum açana kadar alt cihazları olmayan hot plug PCI bağlantı noktalarında DMA engellenir. Makine kilidi açıldığında zaten numaralandırılan cihazlar, söküle kadar çalışmaya devam eder. 

  Bu ilke ayarı yalnızca BitLocker veya cihaz şifrelemesi etkinleştirildiğinde zorlanır.  

  **Varsayılan**: Evet


- **Kurulum sınıflarına göre donanım cihaz yüklemesi**  
  [Deviceınstall/Allowwinstallationofmatchingdevicesetupclasses](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-allowinstallationofmatchingdevicesetupclasses) -bu Ilkeyle, Windows 'un yüklemesi engellenmesinin önyüklendiği cihaz sürücüleri için cihaz kurulum sınıfının genel benzersiz tanımlayıcıları (GUID 'ler) listesini belirtebilirsiniz. Bu ilke ayarı, Windows 'un bir cihaz yüklemesine izin veren diğer tüm ilke ayarlarından önceliklidir. Bu ilke ayarını etkinleştirirseniz ( *donanım cihazı yüklemeyi engelleyecek*şekilde ayarlanır), Windows 'un, cihaz kurulum sınıfı GUID 'leri oluşturduğunuz listede göründüğü cihaz sürücülerini yüklemesi veya güncelleştirmesi engellenir. Uzak Masaüstü sunucusunda bu ilke ayarını etkinleştirirseniz, ilke ayarı, belirtilen cihazların uzak masaüstü istemcisinden uzak masaüstü sunucusuna yönlendirilmesini etkiler. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız ( *donanım cihazı yüklemeye Izin ver*olarak ayarlanır), Windows, diğer ilke ayarları tarafından izin verilen veya engellenen cihazları yükleyebilir ve güncelleştirebilir.  

  **Varsayılan**: Donanım cihazını yüklemeyi engelle

  *Donanım aygıtı yüklemesi engellenme* seçildiğinde aşağıdaki ayarlar kullanılabilir.  

  - **Eşleşen donanım cihazlarını kaldırma**  
    Bu ayar yalnızca, *kurulum sınıfları tarafından sağlanan donanım cihaz yüklemesi* , *donanım cihazı yüklemeyi engelleyecek*şekilde ayarlandığında kullanılabilir.  
 
    **Varsayılan**: *Varsayılan yapılandırma yok*  

  - **Engellenen donanım cihaz tanımlayıcıları**  
    Bu ayar yalnızca, kurulum sınıfları tarafından sağlanan donanım cihaz yüklemesi, donanım cihazı yüklemeyi engelleyecek şekilde ayarlandığında kullanılabilir. Bu ayarı yapılandırmak için, seçeneğini genişletin, **+ Ekle**' yi seçin ve ardından engellemek istediğiniz donanım cihaz tanımlayıcısını belirtin.  
 
    **Varsayılan**: *Hiçbir cihaz engellenmiyor*

## <a name="endpoint-detection-and-response"></a>Uç nokta algılama ve yanıt  
Daha fazla bilgi için Windows belgelerindeki [Windowsadvancedthreatprotection CSP](https://docs.microsoft.com/windows/client-management/mdm/windowsadvancedthreatprotection-csp) bölümüne bakın.  

- **Telemetriyi raporlama sıklığı** - *yapılandırma/TelemetryReportingFrequency*  

  Microsoft Defender Gelişmiş tehdit koruması telemetri raporlama sıklığını hızlandırın.  

  **Varsayılan**: Evet

- **Tüm dosyalar** - için örnek paylaşımı*yapılandırma/samplesharing*  

  Microsoft Defender Gelişmiş tehdit koruması örnek paylaşımı yapılandırma parametresini döndürür veya ayarlar.  

  **Varsayılan**: Evet

## <a name="exploit-protection"></a>Exploit koruması  

- **Exploit Protection XML**  
  Daha fazla bilgi için Windows belgelerindeki [Exploit Protection yapılandırmalarının içeri ve dışarı](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/import-export-exploit-protection-emet-xml) aktarılması bölümüne bakın.  

  BT yöneticisinin, kuruluştaki tüm cihazlara istenen sistem ve uygulama azaltma seçeneklerini temsil eden bir yapılandırma gönderebilmesini sağlar. Yapılandırma bir XML ile temsil edilir. 

  Exploit Protection geçerlidir, cihazları yaymak ve bulaşma için kötüye kullanılan kötü amaçlı yazılımlardan korumaya yardımcı olur. Windows güvenlik uygulamasını veya PowerShell 'i kullanarak bir azaltma kümesi (yapılandırma olarak bilinir) oluşturabilirsiniz. Daha sonra bu yapılandırmayı bir XML dosyası olarak dışarı aktarabilir ve ağınızdaki birden fazla makineyle paylaşarak, hepsi aynı azaltma ayarları kümesine sahip olurlar.
 
  Ayrıca, var olan bir EMET yapılandırma XML dosyasını bir Exploit Protection yapılandırması XML dosyasına dönüştürebilir ve içeri aktarabilirsiniz.

- **Açıktan yararlanma korumasını geçersiz kılmayı engelle**  
  [Windowssavunma Dersecuritycenter/Disallowpatıprotectionoverride](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsdefendersecuritycenter#windowsdefendersecuritycenter-disallowexploitprotectionoverride) – kullanıcıların Windows Defender Güvenlik Merkezi 'ndeki Exploit Protection ayarları alanında değişiklik yapmasını engellemek için *Evet* olarak ayarlayın. Bu ayarı devre dışı bırakır veya yapılandırmazsanız, yerel kullanıcılar, açıktan yararlanma koruması ayarları alanında değişiklik yapabilirler.  
  **Varsayılan**: Evet  

- **Denetlenen klasör erişimi**  
  Bkz. [Defender/ControlledFolderAccessAllowedApplications](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessallowedapplications) ve [Defender/ControlledFolderAccessProtectedFolders](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) 
  
   Dosya ve klasörleri kötü amaçlı uygulamaların yetkisiz değişikliklerinden korur.

  **Varsayılan**: Denetim modu

## <a name="web--network-protection"></a>Web & ağ koruması  

- **Ağ koruma türü**  
  [Defender/EnableNetworkProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection) -bu Ilke, Windows Defender Exploit Guard 'da ağ korumasını açıp kapaetmenize olanak tanır. Ağ koruması, herhangi bir uygulamanın kimlik avı dolandırıcılığı, yararlanma ve barındırma siteleri ve Internet 'teki kötü amaçlı içeriklere erişmesini koruyan bir Windows Defender Exploit Guard özelliğidir. Bu, üçüncü taraf tarayıcıların tehlikeli sitelere bağlanmasını engellemeyi de kapsar.  

  *Etkin* veya *Denetim moduna*ayarlandığında, kullanıcılar ağ korumasını kapatamaz ve bağlantı denemeleri hakkındaki bilgileri görüntülemek Için Windows Defender Güvenlik Merkezi 'ni kullanabilirsiniz.  
 
  - *Etkinleştir* ayarı, kullanıcıların ve uygulamaların tehlikeli etki alanlarına bağlanmasını engeller.  
  - *Denetim modu* , kullanıcıların ve uygulamaların tehlikeli etki alanlarına bağlanmasını engellemez.  

  *Kullanıcı tanımlı*olarak ayarlandığında, kullanıcıların ve uygulamaların tehlikeli etki alanlarına bağlanması engellenmez ve bağlantılar hakkındaki bilgiler Windows Defender Güvenlik Merkezi 'nde kullanılamaz.  

  **Varsayılan**: Denetim modu

- **Microsoft Edge için SmartScreen gerektir**  
  [Tarayıcı/AllowSmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen) -Microsoft Edge, kullanıcıların olası kimlik avı dolandırıcılarından ve kötü amaçlı yazılımlardan varsayılan olarak korunmasını sağlamak Için Windows Defender SmartScreen (açık) kullanır. Varsayılan olarak, bu ilke etkinleştirilmiştir ( *Evet*olarak ayarlanır) ve etkinleştirildiğinde kullanıcıların Windows Defender SmartScreen 'i kapatmasını engeller.  Bir cihaz için geçerli ilke Yapılandırılmadı olarak eşitse, kullanıcılar Windows Defender SmartScreen 'i kapatabilir ve bu da cihazı korumasız olarak bırakır.  

  **Varsayılan**: Evet
  
- **Kötü amaçlı Site erişimini engelleyin**  
  [Tarayıcı/PreventSmartScreenPromptOverride](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-preventsmartscreenpromptoverride) -varsayılan olarak Microsoft Edge, kullanıcıların siteye devam etmesine izin veren kötü amaçlı olabilecek siteler hakkındaki Windows Defender SmartScreen uyarılarını atlamasına (yoksaymasına) izin verir. Bu ilke etkinken ( *Evet*olarak ayarlanırsa), Microsoft Edge kullanıcıların uyarıları atlamasını ve siteye devam etmesini engeller.  

  **Varsayılan**: Evet

- **Doğrulanmamış dosya indirmeyi engelle**  
  [Tarayıcı/PreventSmartScreenPromptOverrideForFiles](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-preventsmartscreenpromptoverrideforfiles) -varsayılan olarak, Microsoft Edge, kullanıcıların, zararlı olabilecek dosyalarla Ilgili Windows Defender SmartScreen uyarılarını atlamasına (yoksaymasına) izin verir ve bu da doğrulanmamış dosyaları indirmeye devam edebilir. Bu ilke etkinken ( *Evet*olarak ayarlanır), kullanıcıların uyarıları atlaması ve doğrulanmamış dosyaları indiremez.  

  **Varsayılan**: Evet

## <a name="windows-defender-anti-virus----settings-review-pending-for-this-section"></a>Windows Defender Anti-Virus [Bu bölüm için ayarları gözden geçirme bekleniyor]

Daha fazla bilgi için Windows belgelerindeki [Ilke CSP-Defender](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender) bölümüne bakın.

- **Microsoft Web tarayıcılarında yüklenen betikleri tarama**  
  [Defender/AllowScriptScanning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowscriptscanning) : Windows Defender betik tarama işlevselliğine izin vermek için *Evet* olarak ayarlayın.  

  **Varsayılan**: Evet

- **Gelen posta iletilerini Tara**  
  [Defender/AllowEmailScanning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowemailscanning) – Windows Defender 'ın e-postayı taramasına izin vermek için *Evet* olarak ayarlayın.  

  **Varsayılan**: Evet

- **Defender örnek gönderimi onay türü**  
  [Defender/Submitsamplesonayını](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent) -veri göndermek Için Windows Defender 'daki Kullanıcı izin düzeyini denetler. Gerekli onay zaten verildiyse, Windows Defender bunları gönderir. Değilse (ve Kullanıcı hiçbir zaman sorma olarak belirtilmişse), veri göndermeden önce Kullanıcı onayını ( *buluta teslim edilen koruma* *Evet*olarak ayarlandığında) istemek için Kullanıcı arabirimi başlatılır.  

  **Varsayılan**: Güvenli örnekleri otomatik olarak gönder

- **Ağ İnceleme Sistemi (NIS)**  
  [Defender/EnableNetworkProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection) -ağ İnceleme SISTEMI (NIS) imzaları tarafından algılanan kötü amaçlı trafiği engelleyin.  
 
  **Varsayılan**: Evet

- **İmza güncelleştirme aralığı (saat)**  
  [Defender/Signatureupdateınterval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-signatureupdateinterval) – cihazın yeni Defender imza güncelleştirmelerini ne sıklıkta denetleyeceğini saat cinsinden belirtin.  
 
  **Varsayılan**: 4

- **Zamanlanan Taramalar için düşük CPU önceliğini yapılandırma**  
  [Defender/Enablelowcpupriınlık](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablelowcpupriority) – *Evet*olarak ayarlandığında, taramalar için CPU önceliği düşük olarak ayarlanır. *Yapılandırılmadığında*, zamanlanan taramalar için CPU önceliğine hiçbir değişiklik yapılmaz.  

    **Varsayılan**: Evet

- **Erişim Koruması 'nda Defender bloğu**  
  [Defender/AllowOnAccessProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowonaccessprotection) – *Evet*olarak ayarlandığında, erişim koruması 'nda Windows Defender etkin olur.  

  **Varsayılan**: Evet

- **Gerçekleştirilecek sistem taraması türü**  
  [Defender/ScanParameter](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-scanparameter) -Defender tarama türü.  

  **Varsayılan**: Hızlı tarama

- **Tüm indirmeleri tara**  
  [Defender/Allowwioavprotection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowioavprotection) - *Evet*olarak ayarlandığında, Defender indirilen tüm dosya ve ekleri tarar.  

  **Varsayılan**: Evet

- **Karantinaya alınan kötü amaçlı yazılımı silmeden önce geçen gün**  
  [Defender/DaysToRetainCleanedMalware](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-daystoretaincleanedmalware) -karantina öğelerinin otomatik olarak silinmeden önce sistemde kaç gün tutulacağını belirtin. Sıfır olarak ayarlandığında, Karantinadaki öğeler hiçbir zaman otomatik olarak silinmez.  

  **Varsayılan**: 0

- **Zamanlanmış tarama başlangıç zamanı**  
  [Defender/ScheduleScanTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulescantime) – Defender 'ın cihazları taraması için bir gün saati zamanlayın. 
  
  Bu listedeki ilgili seçenek: *Defender/ScheduleScanDay*   

  **Varsayılan**: 2 HAR

- **Buluta teslim edilen koruma**  
  [Defender/AllowCloudProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowcloudprotection) – *Evet*olarak ayarlandığında, Windows Defender bulduğu sorunlar hakkında Microsoft 'a bilgi gönderir. Microsoft bu bilgileri analiz eder, sizi ve diğer müşterileri etkileyen sorunlar hakkında daha fazla bilgi edinin ve geliştirilmiş çözümler sunar.

  Bu ilke *Evet*olarak ayarlandığında, kullanıcıların cihazlarından bilgi göndermesi için denetim sağlamak üzere *Defender örnek gönderimi izin türü* ' nu kullanabilirsiniz.  

  **Varsayılan**: Evet

- **Defender istenmeyebilecek uygulama eylemi**  
  [Defender/PUAProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-puaprotection) – Windows Defender virüsten koruma, istenmeyebilecek *uygulamaları* (PUAs) ağınızdaki uç noktalara indirip yüklemeye yönelik olarak tanımlayabilir ve engelleyebilir. 
 
  - *Block*olarak ayarlandığında, Windows Defender PUAs 'yi engeller ve bunları diğer tehditlere karşı geçmiş olarak listeler.
  - *Denetim*olarak ayarlandığında, Windows Defender PUAs algılar, ancak bunları engellemez. Windows Defender tarafından gerçekleştirilecek uygulamalar hakkında bilgi, Olay Görüntüleyicisi Windows Defender tarafından oluşturulan olayları arayarak bulunabilir.  
  - *Cihaz varsayılanı*olarak ayarlandığında Pua koruması kapalıdır.  
 
  **Varsayılan**: Engelle

- **Defender bulutu genişletilmiş zaman aşımı**  
  [Defender/CloudExtendedTimeout](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-cloudextendedtimeout) -Windows Defender virüsten koruma 'nın buluttan bir sonuç beklerken dosyayı engellemesi gereken en fazla ek süreyi belirtin. Windows Defender 'ın beklediği sürenin taban süresi 10 saniyedir. Burada belirttiğiniz ek zaman (50 saniyeye kadar) bu 10 saniyeye eklenir. Çoğu durumda, tarama en büyük boyuttan daha az zaman alır. Bu süreyi artırmak, bulutun şüpheli klasörleri ayrıntılı olarak araştırmasına olanak verir.  

  Varsayılan olarak, genişletilmiş saat değeri 0 ' dır (devre dışı). Intune, bu ayarı etkinleştirmenizi ve en az 20 ek saniye belirtmenizi önerir.  
 
  **Varsayılan**: 0

- **Arşiv dosyalarını tara**  
  [Defender/AllowArchiveScanning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowarchivescanning) – Windows Defender 'ın arşiv dosyalarını taraması için *Evet* olarak ayarlayın.  

  **Varsayılan**: Evet

- **Defender sistem tarama zamanlaması**  
  [Defender/ScheduleScanDay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulescanday) -Defender 'ın cihazları taradığı günü zamanlayın. 
 
  Bu listedeki ilgili seçenek: *Defender/ScheduleScanTime*

  **Varsayılan**: Kullanıcı tanımlı

- **Davranış izleme**  
  [Defender/AllowBehaviorMonitoring](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowbehaviormonitoring) – Windows Defender davranış izleme işlevini açmak için *Evet* olarak ayarlayın. Windows 10 ' da Embedded Windows Defender davranış Izleme algılayıcısı, işletim sisteminden davranış sinyallerini toplayıp işler ve bu algılayıcı verilerini Microsoft Defender ATP 'nin özel, yalıtılmış, bulut örneğine gönderir.  

  **Varsayılan**: Evet

- **Ağ klasörlerinden açılan dosyaları tara**  
  [Defender/AllowScanningNetworkFiles](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowscanningnetworkfiles) : Windows Defender 'ın ağ üzerinde dosya taraması için *Evet* olarak ayarlayın. Kullanıcı algılanan kötü amaçlı yazılımları salt okuma dosyalarından kaldıramayacak.  

  **Varsayılan**: Evet

- **Defender bulut blok düzeyi**  
  [Defender/CloudBlockLevel](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-cloudblocklevel) – agresif Windows Defender virüsten koruma 'nın şüpheli dosyaları engelleyip taramakta olduğunu öğrenmek için bu ilkeyi kullanın. Şu seçenekler mevcuttur:

  - İstemci performansını iyileştirirken (hatalı pozitif sonuçlar için büyük olasılıkla) yüksek performanslı, bilinmeyen dosyaları engelle
  - Yüksek artı-bilinmeyen dosyaları engelle ve ek koruma önlemleri Uygula (istemci performansını etkileyebilir)
  - Sıfır toleransı-tüm bilinmeyen yürütülebilir dosyaları engelle

  **Varsayılan**: Yapılandırılmadı

- **Gerçek zamanlı izleme**  
  [Defender/AllowRealtimeMonitoring](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowrealtimemonitoring) – Windows Defender gerçek zamanlı izlemeye izin vermek için *Evet* olarak ayarlayın.  

  **Varsayılan**: Evet

- **Tarama sırasında CPU kullanım sınırı**  
  [Defender/AvgCPULoadFactor](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-avgcpuloadfactor) – Windows Defender 'ın tarama sırasında kullanabileceği en yüksek ortalama CPU kullanımını belirtin.  

  **Varsayılan**: 50

- **Tam tarama sırasında eşlenmiş ağ sürücülerine tarama**  
  [Defender/AllowFullScanOnMappedNetworkDrives](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowfullscanonmappednetworkdrives) -Windows Defender 'ın ağ üzerinde dosyaları taramasını sağlamak için *Evet* olarak ayarlayın. Kullanıcı algılanan kötü amaçlı yazılımları salt okuma dosyalarından kaldıramaz,

  Bu listedeki ilgili ayar: *Defender/AllowScanningNetworkFiles*

  **Varsayılan**: Evet

- **Defender 'a Son Kullanıcı erişimini engelleyin**  
  [Defender/AllowUserUIAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowuseruiaccess) : son kullanıcıların cihazındaki Windows Defender Kullanıcı arabirimine erişimini engellemek için *Evet* olarak ayarlayın.  

  **Varsayılan**: Evet

- **Hızlı tarama başlangıç zamanı**  
  [Defender/ScheduleQuickScanTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulequickscantime) -Defender 'ın bir hızlı tarama çalıştırması için günün saatini zamanlayın.  

  **Varsayılan**: 2 HAR

## <a name="windows-defender-firewall"></a>Windows Defender Güvenlik Duvarı
Daha fazla bilgi için Windows belgelerindeki [güvenlik DUVARı CSP](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp) bölümüne bakın.

- **Silinmeden önce güvenlik ilişkilendirmesi boşta kalma süresi***mdmstore/Global/saıdsaati*  -    
  Güvenlik ilişkilendirmeleri, bu sayıda saniye boyunca ağ trafiği görülmediğinde silinir.  
  **Varsayılan**: 300

- DosyaAktarımProtokolü - *mdmstore/Global/disablestatefulftp*   
  Durum bilgisi olan Dosya Aktarım Protokolü (FTP) blokları.  
  **Varsayılan**: Evet

- **Paket kuyruğu** - *mdmstore/Global/enablepacketqueue*    
  IPSec tüneli ağ geçidi senaryosunda, şifreli alma ve şifresiz metin iletme için alma tarafında yazılım ölçeklendirmesinin nasıl etkinleştirildiğini belirtin. Bu, paket sırasının korunmasını sağlar.  
  **Varsayılan**: Cihaz varsayılanı

- **Güvenlik duvarı profili etki alanı** - *FirewallRules/firewallrulename/Profiles*  
  Kuralın ait olduğu profilleri belirtir: Etki alanı, özel, genel. Bu değer, etki alanlarına bağlı ağların profilini temsil eder.  

  Kullanılabilir ayarlar:  
  - **Çok noktaya yayın yayınlarına tek noktaya yayın yanıtları gerekiyor**  
    **Varsayılan**: Evet

  - **Grup İlkesi birleştirilmiş uygulama kuralları birleştirildi**  
    **Varsayılan**: Evet

  - **Engellenen gelen bildirimler**  
    **Varsayılan**: Evet

  - **Grup İlkesi ile birleştirilen genel bağlantı noktası kuralları**  
    **Varsayılan**: Evet

  - **Gizli mod engellendi**  
    **Varsayılan**: Evet

  - **Güvenlik Duvarı etkin**  
    **Varsayılan**: İzin Verildi

  - **Grup İlkesi 'nden bağlantı güvenlik kuralları birleştirilmedi**  
    **Varsayılan**: Evet

  - **Grup ilkesinden ilke kuralları birleştirilmedi**  
    **Varsayılan**: Evet

- **Güvenlik duvarı profili genel** - *FirewallRules/firewallrulename/Profiles*  
  Kuralın ait olduğu profilleri belirtir: Etki alanı, özel, genel. Bu değer, ortak ağların profilini temsil eder. Bu ağlar, sunucu konağındaki yöneticiler tarafından genel olarak sınıflandırılır. Sınıflandırma, ana bilgisayarın ağa ilk bağlanışında meydana gelir. Genellikle bu ağlar havaalanları, kafeterler ve ağdaki veya ağ yöneticisinin güvendiği diğer genel yerlerden oluşur.  

  Kullanılabilir ayarlar:

  - **Engellenen gelen bağlantılar**  
    **Varsayılan**: Evet 

  - **Çok noktaya yayın yayınlarına tek noktaya yayın yanıtları gerekiyor**  
    **Varsayılan**: Evet  

  - **Gizli mod gerekli**  
    **Varsayılan**: Evet 
 
  - **Gerekli giden bağlantılar**  
    **Varsayılan**: Evet  

  - **Grup İlkesi birleştirilmiş uygulama kuralları birleştirildi**  
    **Varsayılan**: Evet  

  - **Engellenen gelen bildirimler**  
    **Varsayılan**: Evet  

  - **Grup İlkesi ile birleştirilen genel bağlantı noktası kuralları**  
    **Varsayılan**: Evet

  - **Gizli mod engellendi**  
    **Varsayılan**: Evet

  - **Güvenlik Duvarı etkin**  
    **Varsayılan**: İzin Verildi  

  - **Grup İlkesi 'nden bağlantı güvenlik kuralları birleştirilmedi**  
    **Varsayılan**: Evet  

  - **Gelen trafik gerekli**  
    **Varsayılan**: Evet

  - **Grup ilkesinden ilke kuralları birleştirilmedi**  
    **Varsayılan**: Evet  

- **Güvenlik duvarı profili özel** - *FirewallRules/firewallrulename/Profiles*  
  Kuralın ait olduğu profilleri belirtir: Etki alanı, özel, genel. Bu değer, özel ağların profilini temsil eder.  

  Kullanılabilir ayarlar: 

  - **Engellenen gelen bağlantılar**  
    **Varsayılan**: Evet

  - **Çok noktaya yayın yayınlarına tek noktaya yayın yanıtları gerekiyor**  
    **Varsayılan**: Evet

  - **Gizli mod gerekli**  
    **Varsayılan**: Evet

  - **Gerekli giden bağlantılar**  
    **Varsayılan**: Evet

  - **Engellenen gelen bildirimler**  
    **Varsayılan**: Evet

  - **Grup İlkesi ile birleştirilen genel bağlantı noktası kuralları**  
    **Varsayılan**: Evet

  - **Gizli mod engellendi**  
    **Varsayılan**: Evet  

  - **Güvenlik Duvarı etkin**  
    **Varsayılan**: İzin Verildi

  - **Grup ilkesinden yetkili uygulama kuralları birleştirilmedi**  
    **Varsayılan**: Evet

  - **Grup İlkesi 'nden bağlantı güvenlik kuralları birleştirilmedi**  
    **Varsayılan**: Evet

  - **Gelen trafik gerekli**  
    **Varsayılan**: Evet

  - **Grup ilkesinden ilke kuralları birleştirilmedi**  
    **Varsayılan**: Evet  

- **Güvenlik Duvarı paylaşılan anahtar kodlama yöntemi**  
  **Varsayılan**: UTF8

- **Sertifika iptal listesi doğrulaması**  
  **Varsayılan**: Cihaz varsayılanı

## <a name="windows-hello-for-business"></a>İş İçin Windows Hello  

Daha fazla bilgi için Windows belgelerindeki [Passportforwork CSP](https://docs.microsoft.com/windows/client-management/mdm/passportforwork-csp) bölümüne bakın.

- **İş için Windows Hello***tenantıd/policies/usepassportforwork yapılandırma*  -     
  Iş için Windows Hello, parolaları, akıllı kartları ve sanal akıllı kartları değiştirerek Windows 'da oturum açmak için alternatif bir yöntemdir.  

  - *Evet*olarak ayarlandığında, bu ilkeyi etkinleştirir ve cihaz Iş Için Windows Hello 'yu hazırlar.  
  - *Yapılandırılmadı*olarak ayarlandığında, taban çizgisi cihazın ilke ayarını etkilemez. Bu, Iş için Windows Hello 'nun bir cihazda devre dışı bırakıldığı durumlarda devre dışı kaldığı anlamına gelir. Etkinse, etkin kalır. 

  Bu taban çizgisi aracılığıyla Iş için Windows Hello 'Yu devre dışı bırakayükleyemezsiniz. [Windows kaydını](windows-hello.md)yapılandırırken veya [kimlik koruması](identity-protection-configure.md)için bir cihaz yapılandırma profilinin parçası olarak Iş için Windows Hello 'yu devre dışı bırakabilirsiniz.  

Iş için Windows Hello, parolaları, akıllı kartları ve sanal akıllı kartları değiştirerek Windows 'da oturum açmak için alternatif bir yöntemdir.  

  Bu ilke ayarını etkinleştirir veya yapılandırmazsanız, cihaz Iş için Windows Hello 'Yu sağlar. Bu ilke ayarını devre dışı bırakırsanız, cihaz herhangi bir kullanıcı için Iş için Windows Hello 'Yu sağlayamaz.

  Intune, Windows Hello 'Yu devre dışı bırakmayı desteklemez. Bunun yerine, ilkeyi Iş için Windows Hello 'yu etkinleştirmek üzere yapılandırabilirsiniz (Evet) veya doğrudan Windows Hello 'Yu yapılandırmayın (yapılandırılmadı). Yapılandırılmadığında, bir cihaz başka bir ilke aracılığıyla yapılandırma alabilir, bu da bu özelliği etkinleştirebilir veya devre dışı bırakabilir.  

  **Varsayılan**: Evet  

- PIN - *tenantıd/policies/ınsekarmaşıklık/* küçük harf ayrımına göre küçük harfler iste  
  **Varsayılan**: İzin Verildi  

- PIN - *tenantıd/policies/pinkarmaşıklık/specialcharacters* içinde özel karakterler iste  
  **Varsayılan**: İzin Verildi  

- PIN - *tenantıd/ilkelerindeki* veya en üst üstelerde büyük harfler iste   
  **Varsayılan**: İzin Verildi  

