---
title: Windows 10 MDM için Intune güvenlik temelleri ayarları
titleSuffix: Microsoft Intune
description: Microsoft Intune ile yönetebileceğiniz Windows MDM güvenlik temelinin farklı sürümleri için varsayılan değerleri ve kullanılabilir ayarları gözden geçirin.
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 09/06/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
zone_pivot_groups: windows-mdm-versions
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e0be7627403cc95316a99e841127a137e0279ff1
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72508975"
---
# <a name="windows-mdm-security-baseline-settings-for-intune"></a>Intune için Windows MDM güvenlik taban çizgisi ayarları
Windows 10 veya üstünü çalıştıran cihazlar için Microsoft Intune tarafından desteklenen MDM güvenlik temeli ayarlarını görüntüleyin. Bu temeldeki ayarların varsayılan değerleri, uygulanabilir cihazlar için önerilen yapılandırmayı temsil eder ve diğer güvenlik temellerinden ya da bu taban çizgisinin diğer sürümlerinden taban çizgisi varsayılanlarından eşleşmeyebilir.

- Intune ile güvenlik temellerini kullanma ve güvenlik taban çizgisi profillerinizden temel sürümü yükseltme hakkında bilgi edinmek için bkz. [güvenlik temellerini kullanma](../security-baselines.md).  
- 2019 Mayıs 'un en son temel sürümü **MDM güvenlik temeliyle**  
   
Görüntülemek istediğiniz taban çizgisinin sürümünü seçtiğinizden emin olun.   

<!-- Cookies might be required to enable some browsers to display the zone options --> 
 

::: zone pivot="mdm-may-2019"  
**2019 Mayıs için MDM güvenlik temeli** 
> [!NOTE]  
> Haziran 2019 ' de, *mayıs 2019 şablonunun MDM güvenlik temeli* genel kullanıma sunuldu (önizlemede değil) olarak yayımlanmıştır. Güvenlik temelinin bu sürümü, *2018 Ekim Için MDM güvenlik temeli*olan prvou taban çizgisinin yerini alır.  Mayıs 2019 temelinin kullanılabilirliği öncesinde oluşturulan profiller, Mayıs 2019 sürümündeki ayarları ve değerleri yansıtacak şekilde güncellemeyebilir.  Önizleme şablonunu temel alan yeni profiller oluşturmasanız da, önizleme şablonunu temel alan daha önce oluşturduğunuz profilleri düzenleyebilir ve kullanmaya devam edebilirsiniz. 

Taban çizgisinin bu sürümünde önceki sürümden nelerin değiştirildiğini öğrenmek için, bkz. [Yeni şablonda nelerin değiştiğini](#whats-changed-in-the-new-template).  
::: zone-end

::: zone pivot="mdm-preview"
**Preview-2018 Ekim için MDM güvenlik temeli**  
> [!NOTE]  
> Bu, Ekim 2018 ' de yayınlanan MDM güvenlik temelinin önizleme sürümüdür. Bu önizleme temeli, 2019 Haziran 'da, genel kullanıma açık olan (Önizleme aşamasında değil) *mayıs 2019 şablonu Için MDM güvenlik temeli* sürümü ile değiştirilmiştir. *Mayıs 2019 temeli Için MDM güvenlik temelinin* kullanılabilirliği öncesinde oluşturulan profiller, Mayıs 2019 sürümü Için MDM güvenlik temelindeki ayarları ve değerleri yansıtacak şekilde güncellemeyebilir. Önizleme şablonunu temel alan yeni profiller oluşturmasanız da, önizleme şablonunu temel alan daha önce oluşturduğunuz profilleri düzenleyebilir ve kullanmaya devam edebilirsiniz. 
::: zone-end

::: zone pivot="mdm-may-2019,mdm-preview"
## <a name="above-lock"></a>Kilidin üstünde  
Daha fazla bilgi için Windows belgelerindeki [POLICY CSP-AboveLock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-abovelock) bölümüne bakın.  

- **Bildirim bildirimlerinin görüntülenmesini engelle**  
  Bu ilke ayarı, uygulama bildirimlerinin kilit ekranında görüntülenmesini engellemenizi sağlar. Bu ilke ayarını etkinleştirirseniz, kilit ekranında hiçbir uygulama bildirimi gösterilmez. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, kullanıcılar hangi uygulamaların kilit ekranında bildirim görüntülemesini seçebilirler.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067101)  

  **Varsayılan**: Evet  
::: zone-end
::: zone pivot="mdm-may-2019" 
- **Uygulamaları kilitli ekrandan etkinleştir**  

  **Varsayılan**: devre dışı
::: zone-end

::: zone pivot="mdm-may-2019,mdm-preview"  
## <a name="app-runtime"></a>Uygulama çalışma zamanı    
Daha fazla bilgi için Windows belgelerindeki [Ilke CSP-AppRuntime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-appruntime
) bölümüne bakın.  

- **Microsoft hesapları Windows Mağazası uygulamaları için isteğe bağlı**  
  Bu ilke ayarı, Microsoft hesaplarının bir hesabının oturum açmasını gerektiren Windows Mağazası uygulamaları için isteğe bağlı olup olmadığını denetlemenize olanak tanır. Bu ilke yalnızca bunu destekleyen Windows Mağazası uygulamalarını etkiler. Bu ilke ayarını etkinleştirirseniz, genellikle oturum açmak için bir Microsoft hesabı gerektiren Windows Mağazası uygulamaları, kullanıcıların bunun yerine bir kurumsal hesapla oturum açmalarına olanak tanır. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, kullanıcıların bir Microsoft hesabı oturum açması gerekir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067104)  
  
  **Varsayılan**: etkin  

## <a name="application-management"></a>Uygulama yönetimi   
Daha fazla bilgi için Windows belgelerindeki [Ilke CSP-ApplicationManagement](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement) bölümüne bakın.  
::: zone-end

::: zone pivot="mdm-may-2019"
- **Yüklemeler üzerinde kullanıcı denetimini engelle**  
  Bu ilke ayarı, kullanıcıların genellikle sistem yöneticileri tarafından kullanılabilen yükleme seçeneklerini değiştirmesine izin verir. Bu ilke ayarını etkinleştirirseniz, Windows Installer güvenlik özelliklerinden bazıları atlanır. Bu, yüklemelerin tamamlanmasına izin verir, aksi takdirde bir güvenlik ihlali nedeniyle durdurulur. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, Windows Installer güvenlik özellikleri, kullanıcıların sistem yöneticileri için tipik olarak ayrılmış yükleme seçeneklerini değiştirmelerini engeller (örneğin, dosyaların yüklendiği dizini belirtme). Windows Installer bir yükleme paketinin kullanıcının korumalı bir seçeneği değiştirmesine izin verdiğini algılarsa, yüklemeyi sonlandırır ve bir ileti görüntüler. Bu güvenlik özellikleri yalnızca, yükleme programı Kullanıcı tarafından reddedilen dizinlere erişimi olan ayrıcalıklı bir güvenlik bağlamında çalışırken çalışır. Bu ilke ayarı, daha az kısıtlayıcı ortamlar için tasarlanmıştır. Bu, yazılımın yüklenmesini önleyen bir yükleme programındaki hataları aşmak için kullanılabilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067060)  

  **Varsayılan**: Evet

- **Yükseltilmiş ayrıcalıklarla MSI uygulama yüklemelerini engelleyin**  
  Bu ilke ayarı, sisteme herhangi bir program yüklediğinde Windows Installer yükseltilmiş izinleri kullanmak üzere yönlendirir.  
  - *Bu ilke ayarını etkinleştirirseniz*, ayrıcalıklar tüm programlara genişletilir. Bu ayrıcalıklar genellikle kullanıcıya atanan (masaüstünde sunulan), bilgisayara atanan (otomatik olarak yüklenir) f veya Denetim Masası 'ndaki Program Ekle/Kaldır bölümünde kullanılabilir olan programlar için ayrılmıştır. Bu profil ayarı, kullanıcıların, son derece kısıtlanmış bilgisayarlardaki dizinler dahil olmak üzere, Kullanıcı tarafından görüntüleme veya değiştirme iznine sahip olmadığı dizinlere erişim gerektiren programları yüklemesine olanak sağlar.
  - *Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız*, sistem yöneticisinin dağıtmayacağı veya sunmayacağı programları yüklediğinde, sistem geçerli kullanıcının izinlerini uygular. Note: Bu ilke ayarı, bilgisayar yapılandırması ve Kullanıcı Yapılandırması klasörlerinde görüntülenir. Bu ilke ayarının etkili olması için, her iki klasörde da etkinleştirmeniz gerekir. Dikkat: nitelikli kullanıcılar, bu ilke ayarının ayrıcalıklarını değiştirme ve kısıtlanmış dosya ve klasörlere kalıcı erişim elde etmesine izin verdiği izinlerden yararlanabilir. Bu ilke ayarının Kullanıcı Yapılandırması sürümünün güvenli olduğu garanti edilmez.  
  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067134)    

  **Varsayılan**: Evet
::: zone-end
::: zone pivot="mdm-preview,mdm-may-2019"
- **Oyun DVR 'ı engelle (yalnızca masaüstü)**  
  Oyunları kaydetmeye ve yayına izin verilip verilmeyeceğini yapılandırır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067056)  
  
  **Varsayılan**: Evet  

## <a name="auto-play"></a>Otomatik Yürüt   
Daha fazla bilgi için bkz. [Ilke CSP-Windows belgelerinde otomatik kullan](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-autoplay) .  

- **Varsayılan otomatik çalıştırma davranışını Otomatik Yürüt**  
  Bu ayar Autorun komutlarının varsayılan davranışını etkiler. Autorun komutları Autorun. inf dosyalarında depolanır ve yükleme programlarını veya diğer yordamları başlatabilir. *Etkinleştirildiğinde*Yöneticiler, Windows Vista veya üstünü çalıştıran bir cihazda varsayılan otomatik çalıştırma davranışını değiştirebilir. Davranış: a), otomatik çalıştırma komutunu otomatik olarak yürüten Windows Vista öncesi davranışına geri dönmek için şu şekilde ayarlanabilir: a). *Devre dışı* veya *yapılandırılmamış*olarak ayarlandığında, Windows Vista veya sonraki bir sürümü çalıştıran cihazlar kullanıcıdan bir otomatik çalıştırma komutunun çalıştırılıp çalıştırılmayacağı konusunda bilgi ister.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067133)       
  
  **Varsayılan**: yürütme  
  
- **Otomatik yürütme modu**  
  Bu ilke ayarı, Otomatik Kullan özelliğini kapatmanıza olanak sağlar. Otomatik yürütme, sürücüye medya eklediğiniz andan itibaren bir sürücüden okumaya başlar. Sonuç olarak, programların kurulum dosyası ve ses medyasındaki müzikler hemen başlar. Windows XP SP2 'den önce, otomatik kullan, disket sürücüsü (CD-ROM sürücüsü değil) ve ağ sürücülerinde varsayılan olarak çıkarılabilir sürücülerde devre dışıdır. Windows XP SP2 'den başlayarak, Zip sürücüleri ve bazı USB yığın depolama cihazları dahil olmak üzere, Otomatik Çalıştır, çıkarılabilir sürücüler için de etkinleştirilir. Bu ilke ayarını etkinleştirirseniz, otomatik kullan, CD-ROM ve çıkarılabilir medya sürücülerinde devre dışıdır veya tüm sürücülerde devre dışı bırakılır. Bu ilke ayarı, ek sürücü türlerinde Otomatik yürütmeyi devre dışı bırakır. Bu ayarı, varsayılan olarak devre dışı bırakılmış sürücülerde otomatik olarak etkinleştirmek için kullanamazsınız. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, Otomatik Kullan özelliği etkinleştirilir. Note: Bu ilke ayarı, hem bilgisayar yapılandırması hem de Kullanıcı yapılandırma klasörlerinde görüntülenir. İlke ayarları çakışıyorsa, bilgisayar yapılandırması 'ndaki ilke ayarı, Kullanıcı Yapılandırması 'ndaki ilke ayarından önce gelir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2066793)  
  
  **Varsayılan**: devre dışı

- **Birim olmayan cihazlar için otomatik yürütmeye engel**  
  Bu ilke ayarı, kamera veya telefon gibi MTP cihazları için otomatik olarak izin vermez. Bu ilke ayarını etkinleştirirseniz, kamera veya telefon gibi MTP cihazları için otomatik etkinleştirmeye izin verilmez. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, otomatik kullan, birim olmayan cihazlar için etkinleştirilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067106)    
  
  **Varsayılan**: etkin  

## <a name="bitlocker"></a>Kurulumu    
Daha fazla bilgi için Windows belgelerindeki [Ilke CSP-BitLocker](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bitlocker
) bölümüne bakın.  

- **Bit dolabı çıkarılabilir sürücü ilkesi**  
  Bu ilke ayarı, şifreleme yöntemini ve şifre gücünü denetlemek için kullanılır. Bu ilkenin değerleri BitLocker 'ın şifreleme için kullandığı şifre gücünü belirlemektir. Kuruluşlar, artırılmış güvenlik için şifreleme düzeyini denetlemek isteyebilir (AES-256, AES-128 ' den daha güçlüdür). Bu ayarı etkinleştirirseniz, sabit veri sürücüleri, işletim sistemi sürücüleri ve çıkarılabilir veri sürücüleri için şifreleme algoritması ve anahtar şifreleme gücünü ayrı ayrı yapılandırabileceksiniz. Sabit ve işletim sistemi sürücüleri için, XTS-AES algoritmasını kullanmanızı öneririz. Sürücü, Windows 10, sürüm 1511 veya üzerini çalıştırmayan diğer cihazlarda kullanılıyorsa, çıkarılabilir sürücüler için AES-CBC 128-bit veya AES-CBC 256-bit ' i kullanmanız gerekir. Sürücü zaten şifrelendiyse veya şifreleme devam ediyorsa şifreleme yönteminin değiştirilmesi etkisizdir. Bu durumlarda, bu ilke ayarı yok sayılır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067140) 

  Bit dolabı çıkarılabilir sürücü ilkesi için aşağıdaki ayarı yapılandırın:

  - **Yazma erişimi için şifreleme gerektir**  
    **Varsayılan**: Evet  

::: zone-end
::: zone pivot="mdm-preview"

- **Bit dolabı çıkarılabilir sürücü ilkesi**  
  Bu ilke ayarı, şifreleme yöntemini ve şifre gücünü denetlemek için kullanılır. Bu ilkenin değerleri BitLocker 'ın şifreleme için kullandığı şifre gücünü belirlemektir. Kuruluşlar, artırılmış güvenlik için şifreleme düzeyini denetlemek isteyebilir (AES-256, AES-128 ' den daha güçlüdür). Bu ayarı etkinleştirirseniz, sabit veri sürücüleri, işletim sistemi sürücüleri ve çıkarılabilir veri sürücüleri için şifreleme algoritması ve anahtar şifreleme gücünü ayrı ayrı yapılandırabileceksiniz. Sabit ve işletim sistemi sürücüleri için, XTS-AES algoritmasını kullanmanızı öneririz. Sürücü, Windows 10, sürüm 1511 veya üzerini çalıştırmayan diğer cihazlarda kullanılıyorsa, çıkarılabilir sürücüler için AES-CBC 128-bit veya AES-CBC 256-bit ' i kullanmanız gerekir. Sürücü zaten şifrelendiyse veya şifreleme devam ediyorsa şifreleme yönteminin değiştirilmesi etkisizdir. Bu durumlarda, bu ilke ayarı yok sayılır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067140) 

  Bit dolabı çıkarılabilir sürücü ilkesi için aşağıdaki ayarı yapılandırın:

  - **Yazma erişimi için şifreleme gerektir**  
    **Varsayılan**: Evet  

  - **Şifreleme yöntemi**  
    **Varsayılan**: AES 256BIT CBC  

- **Bit dolabı sabit sürücü ilkesi**  
  Bu ilke ayarı, şifreleme yöntemini ve şifre gücünü denetlemek için kullanılır. Bu ilkenin değerleri BitLocker 'ın şifreleme için kullandığı şifre gücünü belirlemektir. Kuruluşlar, artırılmış güvenlik için şifreleme düzeyini denetlemek isteyebilir (AES-256, AES-128 ' den daha güçlüdür). Bu ayarı etkinleştirirseniz, sabit veri sürücüleri, işletim sistemi sürücüleri ve çıkarılabilir veri sürücüleri için şifreleme algoritması ve anahtar şifreleme gücü ayrı ayrı yapılandırabilirsiniz. Sabit ve işletim sistemi sürücüleri için, XTS-AES algoritmasını kullanmanızı öneririz. Sürücü, Windows 10, sürüm 1511 veya üzerini çalıştırmayan diğer cihazlarda kullanılıyorsa, çıkarılabilir sürücüler için AES-CBC 128-bit veya AES-CBC 256-bit ' i kullanmanız gerekir. Sürücü zaten şifrelendiyse veya şifreleme devam ediyorsa şifreleme yönteminin değiştirilmesi etkisizdir. Bu durumlarda, bu ilke ayarı yok sayılır.  
 
  Bit dolabı sabit sürücü ilkesi için aşağıdaki ayarları yapılandırın: 
  - **Şifreleme yöntemi** **varsayılan**
    : AES 256bit XTS  

- **Bit dolabı sistem sürücüsü ilkesi**  
  Bu ilke ayarı, şifreleme yöntemini ve şifre gücünü denetlemek için kullanılır. Bu ilkenin değerleri BitLocker 'ın şifreleme için kullandığı şifre gücünü belirlemektir. Kuruluşlar, artırılmış güvenlik için şifreleme düzeyini denetlemek isteyebilir (AES-256, AES-128 ' den daha güçlüdür). Bu ayarı etkinleştirirseniz, sabit veri sürücüleri, işletim sistemi sürücüleri ve çıkarılabilir veri sürücüleri için şifreleme algoritması ve anahtar şifreleme gücü ayrı ayrı yapılandırabilirsiniz. Sabit ve işletim sistemi sürücüleri için, XTS-AES algoritmasını kullanmanızı öneririz. Sürücü, Windows 10, sürüm 1511 veya üzerini çalıştırmayan diğer cihazlarda kullanılıyorsa, çıkarılabilir sürücüler için AES-CBC 128-bit veya AES-CBC 256-bit ' i kullanmanız gerekir. Sürücü zaten şifrelendiyse veya şifreleme devam ediyorsa şifreleme yönteminin değiştirilmesi etkisizdir. Bu durumlarda, bu ilke ayarı yok sayılır.  

   Bit dolabı sistem sürücüsü ilkesi için aşağıdaki ayarları yapılandırın:
  - **Şifreleme yöntemi**  
    **Varsayılan**: AES 256BIT XTS  
::: zone-end
::: zone pivot="mdm-preview,mdm-may-2019"

## <a name="browser"></a>Browser  
Daha fazla bilgi için Windows belgelerindeki [Ilke CSP-Browser](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser) bölümüne bakın.  

- **Microsoft Edge için SmartScreen gerektir**  
  Microsoft Edge, kullanıcıların olası kimlik avı dolandırıcılarından ve kötü amaçlı yazılımlardan varsayılan olarak korunmasını sağlamak için Microsoft Defender SmartScreen (açık) kullanır. Ayrıca, kullanıcılar varsayılan olarak Microsoft Defender SmartScreen 'i devre dışı bırakamıyorum (kapatamaz). Bu ilkeyi etkinleştirmek, Microsoft Defender SmartScreen 'i kapatır ve kullanıcıların bunu açmasını önler. Kullanıcıların Microsoft Defender SmartScreen 'i açmayı veya kapatmayı seçmesini sağlamak için bu ilkeyi yapılandırmayın.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067029)   
  
  **Varsayılan**: Evet  
  
- **Kötü amaçlı Site erişimini engelleyin**  
  Varsayılan olarak, Microsoft Edge kullanıcıların, potansiyel olarak kötü amaçlı olabilecek siteler hakkında Microsoft Defender SmartScreen uyarılarını atlayıp siteye devam etmesine izin verir. Bu ilkeyle, Microsoft Edge 'i kullanıcıların uyarıları atlamasını önleyecek ve siteye devam etmesini engelleyecek şekilde yapılandırabilirsiniz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067040)   
  
  **Varsayılan**: Evet  
  
- **Doğrulanmamış dosya indirmeyi engelle**  
  Varsayılan olarak, Microsoft Edge, kullanıcıların, zararlı olabilecek dosyalarla ilgili Microsoft Defender SmartScreen uyarılarını atlamasına (yoksaymasına) izin verir ve bu da doğrulanmamış dosyaları indirmeye devam edebilir. Bu ilkeyi etkinleştirmek, kullanıcıların, doğrulanmamış dosya (ler) i indirmelerini engelleyerek uyarıları atlamasını engeller.  
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
  
  **Varsayılan**: etkin  

::: zone-end
::: zone pivot="mdm-may-2019"
- **UNC yollarına güvenli erişimi yapılandırma**  
  Bu ilke ayarı, UNC yollarına güvenli erişimi yapılandırır. Bu ilkeyi etkinleştirirseniz, Windows yalnızca ek güvenlik gereksinimlerini karşıladıktan sonra belirtilen UNC yollarına erişime izin verir.
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067243) 

  **Varsayılan**: Windows 'ı yalnızca ek güvenlik gereksinimlerini karşıladıktan sonra belirtilen UNC yollarına erişime izin verecek şekilde yapılandırın
  
  *Windows 'u yalnızca ek güvenlik gereksinimlerini karşıladıktan sonra BELIRTILEN UNC yollarına erişime izin verecek şekilde yapılandırdığınızda* , * güçlendirilmiş UNC yol listesini yapılandırabilirsiniz.
  - **Sağlamlaştırılmış UNC yol listesi**  
    Adton güvenlik bayraklarını ve sunucu yollarını belirtmek için **Ekle** ' yi seçin.  

::: zone-end
::: zone pivot="mdm-preview,mdm-may-2019"

- **HTTP üzerinden yazdırma sürücülerinin indirilmesini engelle**  
  Bu ilke ayarı, bu istemcinin HTTP üzerinden yazıcı sürücüsü paketleri indirmesine izin verilip verilmeyeceğini belirtir. HTTP yazdırmayı ayarlamak için, gelen kutusu olmayan sürücülerin HTTP üzerinden indirilmesi gerekir. Note: Bu ilke ayarı, istemcinin Intranet üzerindeki yazıcılara veya HTTP üzerinden Internet üzerinden yazdırmasını engellemez. Yalnızca yerel olarak yüklü olmayan sürücülerin indirilmesini yasaklar. Bu ilke ayarını etkinleştirirseniz, yazıcı sürücüleri HTTP üzerinden indirilemez. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız kullanıcılar, yazıcı sürücülerini HTTP üzerinden indirebilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067141)  
  
  **Varsayılan**: etkin  

<!-- here -->
## <a name="credentials-delegation"></a>Kimlik bilgileri temsili  
Daha fazla bilgi için Windows belgelerindeki [Ilke CSP-Credentialstemsilciliğini](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-credentialsdelegation
) inceleyin.  

- **Dışarı aktarılabilir olmayan kimlik bilgilerinin uzak ana bilgisayar temsili**  
  Uzak ana bilgisayar, dışarı aktarılabilir olmayan kimlik bilgilerinin temsilciliğini sağlar. Kimlik bilgileri temsilcisini kullanırken, cihazlar uzak ana bilgisayara kimlik bilgilerinin dışa aktarılabilir bir sürümünü sağlar ve bu da kullanıcıları uzak ana bilgisayardaki saldırganlar tarafından kimlik bilgilerinin hırsızlık riskini gösterir. Bu ilke ayarını etkinleştirirseniz, ana bilgisayar kısıtlı yönetici veya uzak Credential Guard modunu destekler. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, kısıtlı yönetim ve uzak Credential Guard modu desteklenmez. Kullanıcının kimlik bilgilerini her zaman konağa geçirmesi gerekir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067103)   
  
  **Varsayılan**: etkin  

## <a name="credentials-ui"></a>Kimlik bilgileri kullanıcı arabirimi  
Daha fazla bilgi için Windows belgelerindeki [Ilke CSP-CredentialsUI](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-credentialsui) bölümüne bakın.  

- **Yöneticileri listeleme** Bu ilke ayarı, bir Kullanıcı çalışan bir uygulamayı yükseltmeyi denediğinde yönetici hesaplarının görüntülenip görüntülenmeyeceğini denetler. Varsayılan olarak, Kullanıcı çalışan bir uygulamayı yükseltmeyi denediğinde yönetici hesapları görüntülenmez. Bu ilke ayarını etkinleştirirseniz, BILGISAYARDAKI tüm yerel yönetici hesapları kullanıcının hesabı seçmesini ve doğru parolayı girebilmesini sağlayacak biçimde görüntülenir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcıların yükseltmek için her zaman bir Kullanıcı adı ve parola yazmanız gerekir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067021)

  
  **Varsayılan**: devre dışı  

## <a name="data-protection"></a>Veri Koruma  
Daha fazla bilgi için Windows belgelerindeki [Ilke CSP-DataProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dataprotection
) bölümüne bakın.  

- **Doğrudan bellek erişimini engelle**  
  Bu ilke ayarı, bir Kullanıcı Windows 'a oturum açana kadar, tüm etkin takılabilir PCI akış bağlantı noktaları için doğrudan bellek erişimini (DMA) engellemenizi sağlar. Kullanıcı oturum açtıktan sonra Windows, ana bilgisayar eklentisi PCI bağlantı noktalarına bağlı PCI cihazlarını numaralandırır. Kullanıcı makineyi her kilitlediğinde, Kullanıcı yeniden oturum açana kadar alt cihazları olmayan hot plug PCI bağlantı noktalarında DMA engellenir. Makine kilidi açıldığında zaten numaralandırılan cihazlar, söküle kadar çalışmaya devam eder. Bu ilke ayarı yalnızca BitLocker veya cihaz şifrelemesi etkinleştirildiğinde zorlanır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067031)     
  
  **Varsayılan**: Evet  

## <a name="device-guard"></a>Device Guard  
Daha fazla bilgi için Windows belgelerindeki [Ilke CSP-DeviceGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceguard
) bölümüne bakın.  

- **Credential Guard**  
  Bu ayar, kullanıcıların bir sonraki yeniden başlatmada kimlik bilgilerini korumaya yardımcı olmak üzere sanallaştırma tabanlı güvenlik ile Credential Guard 'ı kapatmasına olanak sağlar.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067044)
   
  **Varsayılan**: UEFI kilidi ile etkinleştir 
::: zone-end
::: zone pivot="mdm-may-2019"

- **sanallaştırma tabanlı güvenlik** 
  **varsayılan**: VBS 'yi güvenli önyükleme ile etkinleştirin
::: zone-end
::: zone pivot="mdm-preview,mdm-may-2019"

- **Sanallaştırma tabanlı güvenliği etkinleştir**  
  Bir sonraki yeniden başlatmada sanallaştırma tabanlı güvenliği (VBS) açar. Sanallaştırma tabanlı güvenlik, güvenlik hizmetlerine destek sağlamak için Windows Hiper Yöneticisi'ni kullanır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067066)  
  
  **Varsayılan**: Evet  

- **System guard   Başlat**  
  **Varsayılan**: etkin  

## <a name="device-installation"></a>Cihaz yüklemesi  
Daha fazla bilgi için Windows belgelerindeki [Ilke CSP-Deviceınstallation](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceinstallation) bölümüne bakın.  

- **Cihaz tanımlayıcılarına göre donanım cihazı yüklemesi**  
  Bu ilke ayarı, Windows 'un yüklemesi engellenen cihazlar için Tak ve Kullan donanım kimliklerinin ve uyumlu kimliklerin bir listesini belirtmenizi sağlar. Bu ilke ayarı, Windows 'un bir cihaz yüklemesine izin veren diğer tüm ilke ayarlarından önceliklidir. Bu ilke ayarını etkinleştirirseniz, Windows 'un, oluşturduğunuz listede donanım KIMLIĞI veya uyumlu KIMLIĞI görünen bir cihaz yüklemesi engellenir. Uzak Masaüstü sunucusunda bu ilke ayarını etkinleştirirseniz, ilke ayarı, belirtilen cihazların uzak masaüstü istemcisinden uzak masaüstü sunucusuna yönlendirilmesini etkiler. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, cihazlar diğer ilke ayarları tarafından izin verilen veya engellenen şekilde yükleyebilir ve güncelleştirebilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2066794)  
  
  **Varsayılan**: donanım cihazını yüklemeyi engelle  

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
  
  **Varsayılan**: donanım cihazını yüklemeyi engelle  

  *Donanım aygıtı yüklemesi engellenme* seçildiğinde aşağıdaki ayarlar kullanılabilir.
  - **Eşleşen donanım cihazlarını kaldırma**    
    Bu ayar yalnızca, *kurulum sınıfları tarafından sağlanan donanım cihaz yüklemesi* , *donanım cihazı yüklemeyi engelleyecek*şekilde ayarlandığında kullanılabilir.  

    **Varsayılan**: *varsayılan yapılandırma yok*  

  - **Engellenen donanım cihaz tanımlayıcıları**  
    Bu ayar yalnızca, *kurulum sınıfları tarafından sağlanan donanım cihaz yüklemesi* , *donanım cihazı yüklemeyi engelleyecek*şekilde ayarlandığında kullanılabilir.
    
    **Varsayılan**: *varsayılan yapılandırma yok*  

## <a name="device-lock"></a>Cihaz kilidi  
Daha fazla bilgi için Windows belgelerindeki [POLICY CSP-DeviceLock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock) bölümüne bakın.  

- **Kameranın kullanımını engelle**  
  BILGISAYAR ayarlarındaki kilit ekranı Kamerası geçiş anahtarını devre dışı bırakır ve bir kameranın kilit ekranında çağrılmasını engeller. Varsayılan olarak, kullanıcılar, kilit ekranında kullanılabilir bir kameranın çağrılmasını sağlayabilir. Bu ayarı etkinleştirirseniz, kullanıcılar artık bılgısayar ayarlarında kilit ekranı kamera erişimini etkinleştiremez veya devre dışı bırakamayacaktır ve kamera kilit ekranında çağrılamaz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067052)
  
  **Varsayılan**: etkin  

- **Parola gerektir**  
  Cihaz kilidinin etkinleştirilip etkinleştirilmeyeceğini belirtir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067049)  
  
  **Varsayılan**: Evet  
  
  *Parola ıste* *Evet*olarak ayarlandığında aşağıdaki ayarlar kullanılabilir.

  - **Parola en az karakter kümesi sayısı**  
    Güçlü bir PIN veya parola için gereken karmaşık öğe türleri sayısı (büyük ve küçük harfler, rakamlar ve noktalama işaretleri). PIN masaüstü ve mobil cihazlar için aşağıdaki davranışı zorlar: 1-yalnızca basamak 2 rakamları ve küçük harflerin 3 basamaklı, küçük harflerin ve büyük harflerin olması gerekir. Masaüstü Microsoft hesaplarında ve etki alanı hesaplarında desteklenmez. 4 basamaklı, küçük harfler, büyük harfler ve özel karakterler gereklidir. Masaüstünde desteklenmez. Varsayılan değer 1’dir.  
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
    
    **Varsayılan**: alfasayısal  

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
  
  **Varsayılan**: etkin  
  *Etkin bir ayar, slayt gösterisinin çalışmasını önler.* 

- **Parola en az gün cinsinden süre**  
  Minimum parola yaşı ilke ayarı, kullanıcının değiştirebilmesi için bir parolanın kullanılması gereken süreyi (gün olarak) belirler. 1 ila 998 gün arasında bir değer ayarlayabilir veya gün sayısını 0 olarak ayarlayarak parola değişikliklerine hemen izin verebilirsiniz. Maksimum parola yaşı 0 olarak ayarlanmadığı ve parolaların süresinin dolmayacağını belirten en az parola yaşı en fazla parola geçerlilik süresinden daha az olmalıdır. Maksimum parola yaşı 0 olarak ayarlandıysa, minimum parola yaşı 0 ile 998 arasında bir değere ayarlanabilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067022) 
  
  **Varsayılan**: 1  
::: zone-end
::: zone pivot="mdm-may-2019"

## <a name="dma-guard"></a>DMA koruyucusu  
Daha fazla bilgi için Windows belgelerindeki [POLICY CSP-DmaGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dmaguard) bölümüne bakın.
- **Çekirdek DMA koruması ile uyumsuz dış cihazların numaralandırması**  
  Bu ilke, dış DMA özellikli cihazlara karşı ek güvenlik sağlamaya yöneliktir. DMA yeniden eşleme/cihaz belleği yalıtımı ve korumalı alana alma ile uyumsuz olan dış DMA özellikli cihazların numaralandırılması üzerinde daha fazla denetim sağlar. Bu ilke, yalnızca çekirdek DMA koruması desteklenirken ve Sistem bellenimi tarafından etkinleştirildiğinde devreye girer. Çekirdek DMA koruması, ilke veya son kullanıcı tarafından denetlenebilecek bir platform özelliğidir. Bu, üretim sırasında sistem tarafından desteklenmelidir. Sistemin çekirdek DMA korumasını destekleyip desteklemediğini denetlemek için lütfen MSINFO32. exe ' nin Özet sayfasındaki çekirdek DMA koruması alanını kontrol edin.  
  [Daha fazla bilgi edinin](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dmaguard#dmaguard-deviceenumerationpolicy)

  **Varsayılan**: tümünü engelle   
::: zone-end
::: zone pivot="mdm-preview,mdm-may-2019"

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
  
  **Varsayılan**: *örnek XML sağlanır* 
 
## <a name="file-explorer"></a>Dosya Gezgini  
Daha fazla bilgi için Windows belgelerindeki [POLICY CSP-FileExplorer](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-fileexplorer) bölümüne bakın.  

- **Veri yürütme engellemesini engelle**  
  Veri yürütme engellemesini devre dışı bırakmak, bazı eski eklenti uygulamalarının gezgin 'i sonlandırmadan çalışmasına izin verebilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067043)  
  
  **Varsayılan**: devre dışı  
   
- **Bozulma durumunda yığın sonlandırmasını engelle**  
  Bozulmaya karşı yığın sonlandırmasının devre dışı bırakılması, bazı eski eklenti uygulamalarının gezgin 'i hemen sonlandırmadan çalışmasına izin verebilir, ancak gezgin daha sonra beklenmedik bir şekilde sonlandırılabilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067107)  
  
  **Varsayılan**: devre dışı  
    

## <a name="internet-explorer"></a>Internet Explorer  
Daha fazla bilgi için bkz. Windows belgelerindeki [Ilke CSP-ınternebir](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-internetexplorer) .  

- **Internet Explorer kısıtlı bölge güncelleştirmelerini betik aracılığıyla durum çubuğuna güncelleştirme**  
  Bu ilke ayarı, betiğin bölge içindeki durum çubuğunu güncelleştirmesine izin verilip verilmeyeceğini yönetmenizi sağlar. 
  - *Bu ilke ayarını etkinleştirirseniz*betiğin durum çubuğunu güncelleştirmesine izin verilir.
  - *Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız*, betiğin durum çubuğunu güncelleştirmesine izin verilmez.  

  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067074)  

  **Varsayılan**: devre dışı
::: zone-end
::: zone pivot="mdm-may-2019"

- **Internet Explorer Internet bölgesi dosyaları sürükleme ve bırakma veya kopyalama ve yapıştırma**  
  Bu ilke ayarı, kullanıcıların bölge içindeki bir kaynaktan dosya sürükleyip sürükleyemeyeceğini veya dosya kopyalayıp yapıştıramayacağını yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, kullanıcılar dosyaları sürükleyebilir veya bu bölgeden otomatik olarak dosya kopyalayabilir ve yapıştırabilir. Açılır kutuda sor ' u seçerseniz, kullanıcıların bu bölgeden dosya sürükleyip sürükleyeceğinizi veya kopyalanıp kopyalanmayacağını seçmeleri istenir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcıların bu bölgeden dosya sürüklenmesi veya dosyaları kopyalaması ve yapıştırması engellenir. Bu ilke ayarını yapılandırmazsanız, kullanıcılar dosyaları sürükleyebilir veya bu bölgeden otomatik olarak dosya kopyalayabilir ve yapıştırabilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067076)  

  **Varsayılan**: devre dışı

- **Internet Explorer kısıtlı bölge .NET Framework bağımlı bileşenler**    
  Bu ilke ayarı, Authenticode ile imzalanmamış .NET Framework bileşenlerinin Internet Explorer 'dan yürütülüp yürütülmeyeceğini yönetmenizi sağlar. Bu bileşenler bir nesne etiketiyle başvurulan yönetilen denetimleri ve bir bağlantıdan başvurulan yönetilen yürütülebilir dosyaları içerir. Bu ilke ayarını etkinleştirirseniz, Internet Explorer imzasız yönetilen bileşenleri yürütür. Açılır kutuda sor ' u seçerseniz, Internet Explorer kullanıcıdan imzasız yönetilen bileşenleri çalıştırıp yürütmeyeceğini belirlemesini ister. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer imzasız yönetilen bileşenleri yürütmez. Bu ilke ayarını yapılandırmazsanız, Internet Explorer imzasız yönetilen bileşenleri yürütmez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067077)

  **Varsayılan**: devre dışı


- **Internet Explorer yerel makine bölgesi, kötü amaçlı yazılımdan koruma 'yi etkin X denetimlerine karşı çalıştırmaz**  
  Bu ilke ayarı, Internet Explorer 'ın, sayfalarda güvenli olup olmadığını denetlemek için kötü amaçlı yazılımdan koruma programlarını ActiveX denetimlerine karşı çalıştırmasını belirler. Bu ilke ayarını etkinleştirirseniz, Internet Explorer, ActiveX denetiminin bir örneğini oluşturmanın güvenli olup olmadığını görmek için kötü amaçlı yazılımdan koruma programınızı denetlemez. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer, ActiveX denetiminin bir örneğinin oluşturulması için güvenli olup olmadığını görmek üzere her zaman kötü amaçlı yazılımdan koruma programınızı denetler. Bu ilke ayarını yapılandırmazsanız, Internet Explorer, ActiveX denetiminin bir örneğinin oluşturulması için güvenli olup olmadığını görmek üzere kötü amaçlı yazılımdan koruma programınızı denetlemez. Kullanıcılar, Internet Explorer güvenlik ayarlarını kullanarak bu davranışı etkinleştirebilir veya devre dışı bırakabilirsiniz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067152)

  **Varsayılan**: devre dışı
::: zone-end
::: zone pivot="mdm-preview,mdm-may-2019"

- **Veri kaynaklarına Internet Explorer Internet bölgesi erişimi**  
  Bu ilke ayarı, Internet Explorer 'ın Microsoft XML ayrıştırıcısı (MSXML) veya ActiveX Data Objects (ADO) kullanarak başka bir güvenlik bölgesinden veriye erişip erişemeyeceğini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, kullanıcılar bölgedeki başka bir siteden veriye erişmek için MSXML veya ADO kullanan bölgeye bir sayfa yükleyebilir. Açılır kutuda sor ' u seçerseniz, kullanıcılar bölgedeki başka bir siteden veriye erişmek için MSXML veya ADO kullanan bölgede bir sayfanın yüklenmesine izin verip vermeyeceğinizi belirlemek üzere sorgulanır. Bu ilke ayarını devre dışı bırakırsanız, kullanıcılar bölgedeki başka bir siteden veriye erişmek için MSXML veya ADO kullanan bölgeye bir sayfa yükleyemez. Bu ilke ayarını yapılandırmazsanız kullanıcılar bölgedeki başka bir siteden veriye erişmek için MSXML veya ADO kullanan bölgeye bir sayfa yükleyemez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067078)  
  
  **Varsayılan**: devre dışı  
  
- **Internet Explorer kısıtlı bölge Windows içindeki farklı etki alanlarından içerik sürükle**  
  Bu ilke ayarı, kaynak ve hedef aynı pencerede olduğunda bir etki alanından farklı bir etki alanına içerik sürükleme seçeneklerini ayarlamanıza olanak sağlar. Bu ilke ayarını etkinleştirir ve Etkinleştir ' e tıklarsanız, kullanıcılar kaynak ve hedef aynı pencerede olduğunda bir etki alanından farklı bir etki alanına içerik sürükleyebilir. Kullanıcılar bu ayarı değiştiremezler. Bu ilke ayarını etkinleştirirseniz ve devre dışı bırak ' a tıkladığınızda, kaynak ve hedef aynı pencerede olduğunda kullanıcılar bir etki alanından farklı bir etki alanına içerik sürüklenemez. Kullanıcılar bu ayarı Internet Seçenekleri iletişim kutusunda değiştiremezler. Internet Explorer 10 ' da, bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, kaynak ve hedef aynı pencerede olduğunda kullanıcılar bir etki alanından farklı bir etki alanına içerik sürüklenemez. Kullanıcılar bu ayarı Internet Seçenekleri iletişim kutusunda değiştirebilir. Internet Explorer 9 ve önceki sürümlerde, bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız kullanıcılar, kaynak ve hedef aynı pencerede olduğunda, içeriği bir etki alanından farklı bir etki alanına sürükleyebilir. Kullanıcılar bu ayarı Internet Seçenekleri iletişim kutusunda değiştiremezler.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067079)  
  
  **Varsayılan**: devre dışı
  
- **Internet Explorer sertifika adresi uyumsuzluğu uyarısı**  
  Bu ilke ayarı, sertifika adresi uyuşmazlığı güvenlik uyarısını açmanıza olanak tanır. Bu ilke ayarı açıkken, Kullanıcı farklı bir Web sitesi adresi için verilen sertifikaları sunan güvenli HTTP (HTTPS) Web sitelerini ziyaret ederken uyarılır. Bu uyarı, sahtekarlığı saldırılarını önlemeye yardımcı olur. Bu ilke ayarını etkinleştirirseniz, sertifika adresi uyumsuzluğu uyarısı her zaman görünür. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız kullanıcı, sertifika adresi uyumsuzluğu Uyarısı ' nı (Internet Denetim Masası 'ndaki gelişmiş sayfasını kullanarak) seçebilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067153)  
  
  **Varsayılan**: etkin 
  
- **Internet Explorer kısıtlı bölge daha az ayrıcalıklı siteler**  
  Bu ilke ayarı, Internet siteleri gibi daha az ayrıcalıklı bölgelerdeki Web sitelerinin bu bölgede gezinip gidemeyeceğini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, daha az ayrıcalıklı bölgelerdeki Web siteleri içinde yeni pencereler açabilir veya bu bölge üzerinde gezinebilirsiniz. Güvenlik bölgesi, bölge yükselmesi güvenlik özelliğinden koruma tarafından belirtilen ek bir güvenlik katmanı olmadan çalışacaktır. Açılır kutuda sor ' u seçerseniz, kullanıcıya riskli gezintinin gerçekleşmek üzere olduğunu belirten bir uyarı verilir. Bu ilke ayarını devre dışı bırakırsanız, olası zararlı gezinme engellenir. Internet Explorer güvenlik özelliği, bölge yükselmesi özellik denetiminden koruma tarafından ayarlandığı şekilde bu bölgede bulunur. Bu ilke ayarını yapılandırmazsanız, olası zararlı gezintiler engellenir. Internet Explorer güvenlik özelliği, bölge yükselmesi özellik denetiminden koruma tarafından ayarlandığı şekilde bu bölgede bulunur.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067148)  
  
  **Varsayılan**: devre dışı  
  
- **Dosya indirmeleri için Internet Explorer kısıtlı bölge otomatik istemi**  
  Bu ilke ayarı, kullanıcılardan Kullanıcı tarafından başlatılmayan dosya indirmeleri isteyip istemeyeceğini belirler. Bu ayardan bağımsız olarak kullanıcılar, Kullanıcı tarafından başlatılan indirmeler için dosya indirme iletişim kutularını alırlar. Bu ayarı etkinleştirirseniz, kullanıcılar otomatik indirme girişimleri için bir dosya indirme iletişim kutusu alır. Bu ayarı devre dışı bırakır veya yapılandırmazsanız, Kullanıcı tarafından başlatılmayan dosya indirmeleri engellenir ve kullanıcılar dosya indirme iletişim kutusu yerine bildirim çubuğunu görür. Kullanıcılar daha sonra, dosya indirme istemine izin vermek için bildirim çubuğuna tıklayabilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067150)  
  
  **Varsayılan**: devre dışı
  
- **Internet Explorer Internet bölgesi .NET Framework bağımlı bileşenler**  
  Bu ilke ayarı, Authenticode ile imzalanmamış .NET Framework bileşenlerinin Internet Explorer 'dan yürütülüp yürütülmeyeceğini yönetmenizi sağlar. Bu bileşenler bir nesne etiketiyle başvurulan yönetilen denetimleri ve bir bağlantıdan başvurulan yönetilen yürütülebilir dosyaları içerir. Bu ilke ayarını etkinleştirirseniz, Internet Explorer imzasız yönetilen bileşenleri yürütür. Açılır kutuda sor ' u seçerseniz, Internet Explorer kullanıcıdan imzasız yönetilen bileşenleri çalıştırıp yürütmeyeceğini belirlemesini ister. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer imzasız yönetilen bileşenleri yürütmez. Bu ilke ayarını yapılandırmazsanız, Internet Explorer imzasız yönetilen bileşenleri yürütür.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067073)  
  
  **Varsayılan**: devre dışı 
  
- **Internet Explorer Internet bölgesi yalnızca onaylanan etki alanlarının TDC ActiveX denetimlerini kullanmasına izin verir**  
  Bu ilke ayarı, kullanıcının web sitelerinde TDC ActiveX denetimini çalıştırıp çalıştırameyeceğini denetler. Bu ilke ayarını etkinleştirirseniz, TDC ActiveX denetimi bu bölgedeki Web sitelerinden çalışmaz. Bu ilke ayarını devre dışı bırakırsanız, TDC etkin X denetimi bu bölgedeki tüm sitelerden çalıştırılır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067151)
  
  **Varsayılan**: etkin 
  
- **Internet Explorer kısıtlı bölge betiği başlatılan Windows**  
  Bu ilke ayarı, başlık ve durum çubuklarını içeren, betik ile başlatılan açılır pencereler ve pencereler üzerindeki kısıtlamaları yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, Windows kısıtlamaları güvenliği bu bölgede uygulanmaz. Güvenlik bölgesi, bu özellik tarafından sunulan ek bir güvenlik katmanı olmadan çalışır. Bu ilke ayarını devre dışı bırakırsanız, başlık ve durum çubuklarını içeren, komut dosyası tarafından başlatılan açılır pencereler ve Windows 'da bulunan olası zararlı eylemler çalıştırılamaz. Bu Internet Explorer güvenlik özelliği, bu bölgede, işlem için Betikleştirilmiş Windows güvenlik kısıtlamaları özelliği denetim ayarı tarafından dikte edildiği şekilde açık. Bu ilke ayarını yapılandırmazsanız, komut dosyası tarafından başlatılan açılır pencereler ve başlık ve durum çubuklarını içeren pencerelerin içerdiği olası zararlı eylemler çalıştırılamaz. Bu Internet Explorer güvenlik özelliği, bu bölgede, işlem için Betikleştirilmiş Windows güvenlik kısıtlamaları özelliği denetim ayarı tarafından dikte edildiği şekilde açık.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067075)  
  
  **Varsayılan**: devre dışı 
  
- **Internet Explorer Internet bölgesi, dosyaları sunucuya yüklerken yerel yolu içerir**  
  Bu ilke ayarı, Kullanıcı HTML formu aracılığıyla bir dosya yüklerken yerel yol bilgilerinin gönderilip gönderilmediğini denetler. Yerel yol bilgileri gönderildiyse, bazı bilgiler istenmeden sunucu tarafından görüntülenebilir. Örneğin, kullanıcının masaüstünden gönderilen dosyalar yolun bir parçası olarak Kullanıcı adını içerebilir. Bu ilke ayarını etkinleştirirseniz, Kullanıcı HTML formu aracılığıyla bir dosya yüklerken yol bilgileri gönderilir. Bu ilke ayarını devre dışı bırakırsanız, Kullanıcı HTML formu aracılığıyla bir dosya yüklerken yol bilgileri kaldırılır. Bu ilke ayarını yapılandırmazsanız kullanıcı HTML formu aracılığıyla bir dosya yüklerken yol bilgilerinin gönderilip gönderilmeyeceğini seçebilir. Varsayılan olarak, yol bilgileri gönderilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067072)  
  
  **Varsayılan**: devre dışı 
  
- **Internet Explorer, gelişmiş korumalı modda işlemi devre dışı bırak**  
  Bu ilke ayarı, Windows 'un 64-bit sürümlerinde gelişmiş korumalı modda çalışırken Internet Explorer 11 ' in 64 bitlik süreçler (daha fazla güvenlik için) veya 32 bit süreçler (daha fazla uyumluluk için) kullanıp kullanmadığını belirler. Önemli: 64 bit işlem kullanılırken bazı ActiveX denetimleri ve araç çubukları kullanılamayabilir. Bu ilke ayarını etkinleştirirseniz, Internet Explorer 11, Windows 'un 64 bit sürümlerinde gelişmiş korumalı modda çalışırken 64 bitlik sekme süreçlerini kullanacaktır. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer 11, Windows 'un 64 bit sürümlerinde gelişmiş korumalı modda çalışırken 32 bitlik sekme süreçlerini kullanacaktır. Bu ilke ayarını yapılandırmazsanız kullanıcılar Internet Explorer ayarlarını kullanarak bu özelliği etkinleştirebilir veya devre dışı bırakabilirsiniz. Bu özellik varsayılan olarak kapalıdır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067149)  
  
  **Varsayılan**: etkin 
  
- **Internet Explorer sertifika hatalarını yoksay**  
  Bu ilke ayarı, Internet Explorer 'da kullanıcının taramayı kesintiye uğratan Güvenli Yuva Katmanı/Aktarım Katmanı Güvenliği (SSL/TLS) sertifika hatalarını ("süre dolduğunda", "iptal edildi" veya "ad uyuşmazlığı" hataları) yok saymasını engeller. Bu ilke ayarını etkinleştirirseniz Kullanıcı göz atmaya devam edebilir. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, Kullanıcı sertifika hatalarını yoksaymayı ve gözatmaya devam etmeyi tercih edebilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067071)  
  
  **Varsayılan**: devre dışı 
  
- **XAML dosyalarının Internet Explorer Internet bölgesi yüklemesi**  
  Bu ilke ayarı, Extensible Application Markup Language (XAML) dosyalarının yüklenmesini yönetmenizi sağlar. XAML, Windows Presentation Foundation faydalanan zengin Kullanıcı arabirimleri ve grafikleri oluşturmak için yaygın olarak kullanılan XML tabanlı bildirime dayalı bir biçimlendirme dilidir. Bu ilke ayarını etkinleştirir ve açılır kutuyu etkinleştir olarak ayarlarsanız, XAML dosyaları Internet Explorer 'ın içine otomatik olarak yüklenir. Kullanıcı bu davranışı değiştiremez. Açılır kutuyu sor olarak ayarlarsanız, kullanıcıdan XAML dosyalarını yüklemesi istenir. Bu ilke ayarını devre dışı bırakırsanız, XAML dosyaları Internet Explorer 'ın içinde yüklenmez. Kullanıcı bu davranışı değiştiremez. Bu ilke ayarını yapılandırmazsanız, Kullanıcı XAML dosyalarını Internet Explorer içinde yükleyip yükleyemeyeceğine karar verebilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067147)  
  
  **Varsayılan**: devre dışı  

::: zone-end
::: zone pivot="mdm-may-2019"
- **Dosya indirmeleri için Internet Explorer Internet bölgesi otomatik istemi**  
  Bu ilke ayarı, kullanıcılardan Kullanıcı tarafından başlatılmayan dosya indirmeleri isteyip istemeyeceğini belirler. Bu ayardan bağımsız olarak kullanıcılar, Kullanıcı tarafından başlatılan indirmeler için dosya indirme iletişim kutularını alırlar. Bu ayarı etkinleştirirseniz, kullanıcılar otomatik indirme girişimleri için bir dosya indirme iletişim kutusu alır. Bu ayarı devre dışı bırakır veya yapılandırmazsanız, Kullanıcı tarafından başlatılmayan dosya indirmeleri engellenir ve kullanıcılar dosya indirme iletişim kutusu yerine bildirim çubuğunu görür. Kullanıcılar daha sonra, dosya indirme istemine izin vermek için bildirim çubuğuna tıklayabilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067117)  
  
  **Varsayılan**: devre dışı  
  
::: zone-end
::: zone pivot="mdm-preview"
- **Dosya indirmeleri için Internet Explorer Internet bölgesi otomatik istemi**  
  Bu ilke ayarı, kullanıcılardan Kullanıcı tarafından başlatılmayan dosya indirmeleri isteyip istemeyeceğini belirler. Bu ayardan bağımsız olarak kullanıcılar, Kullanıcı tarafından başlatılan indirmeler için dosya indirme iletişim kutularını alırlar. Bu ayarı etkinleştirirseniz, kullanıcılar otomatik indirme girişimleri için bir dosya indirme iletişim kutusu alır. Bu ayarı devre dışı bırakır veya yapılandırmazsanız, Kullanıcı tarafından başlatılmayan dosya indirmeleri engellenir ve kullanıcılar dosya indirme iletişim kutusu yerine bildirim çubuğunu görür. Kullanıcılar daha sonra, dosya indirme istemine izin vermek için bildirim çubuğuna tıklayabilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067117)  
  
  **Varsayılan**: etkin  
::: zone-end
::: zone pivot="mdm-preview,mdm-may-2019"

- **Güvenli olmayabilecek dosyalar için Internet Explorer kısıtlı bölge güvenliği uyarısı**  
  Bu ilke ayarı, Kullanıcı yürütülebilir dosyaları veya diğer olası güvenli olmayan dosyaları (örneğin, dosya Gezgini 'ni kullanarak bir intranet dosya paylaşımından) açmaya çalıştığında "dosya güvenlik uyarısı aç" iletisinin görünüp görüntülenmeyeceğini denetler. Bu ilke ayarını etkinleştirir ve açılır kutuyu etkinleştir olarak ayarlarsanız, bu dosyalar güvenlik uyarısı olmadan açılır. Açılır kutuyu sor olarak ayarlarsanız, dosyalar açılmadan önce bir güvenlik uyarısı görüntülenir. Bu ilke ayarını devre dışı bırakırsanız, bu dosyalar açılmaz. Bu ilke ayarını yapılandırmazsanız kullanıcı bilgisayarın bu dosyaları nasıl işleyeceğini yapılandırabilir. Varsayılan olarak, bu dosyalar, Intranet ve yerel bilgisayar bölgelerinde etkin olan kısıtlanmış bölgede engellenir ve Internet ve güvenilen bölgelerde sorulacak şekilde ayarlanır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2066797)  
  
  **Varsayılan**: devre dışı  
  
- **Internet Explorer Internet bölgesi siteler arası betik filtresi**  
  Bu ilke, siteler arası komut dosyası yazma (XSS) filtresinin bu bölgedeki Web sitelerine yönelik siteler arası betik oluşturmayı algılayıp engellemesine izin olup olmadığını denetler. Bu ilke ayarını etkinleştirirseniz, XSS filtresi bu bölgedeki siteler için açıktır ve XSS filtresi siteler arası betik oluşturma girişimlerini engellemeye çalışır. Bu ilke ayarını devre dışı bırakırsanız, bu bölgedeki siteler için XSS filtresi kapatılır ve Internet Explorer siteler arası betik oluşturma izni verir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067053) 
  
  **Varsayılan**: etkin 
  
- **Internet Explorer SSL3 'e geri dönüş**  
  Bu ilke ayarı, SSL 3,0 'e güvenli olmayan bir geri dönüş engellemenizi sağlar. Bu ilke etkinleştirildiğinde, Internet Explorer, TLS 1,0 veya daha fazla hata verdiğinde SSL 3,0 veya sonraki bir sürümü kullanarak sitelere bağlanmaya çalışır. Ortadaki adam saldırısı oluşmasını engellemek için güvenli olmayan geri dönüşe izin vermemenizi öneririz. Bu ilke hangi güvenlik protokollerinin etkinleştirildiğini etkilemez. Bu ilkeyi devre dışı bırakırsanız, sistem Varsayılanları kullanılır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067118)  
  
  **Varsayılan**: site yok  
::: zone-end
::: zone pivot="mdm-may-2019"

- **Internet Explorer şifreleme desteği**  
  Bu ilke ayarı, tarayıcıda Aktarım Katmanı Güvenliği (TLS) 1,0, TLS 1,1, TLS 1,2, Güvenli Yuva Katmanı (SSL) 2,0 veya SSL 3,0 desteğini kapatmanıza olanak sağlar. TLS ve SSL, tarayıcı ile hedef sunucu arasındaki iletişimi korumaya yardımcı olan protokollerdir. Tarayıcı hedef sunucuyla korunan bir iletişim kurmayı denediğinde, tarayıcı ve sunucu hangi protokol ve sürümü kullanacağınızı anlaşacaktır. Tarayıcı ve sunucu birbirlerinin desteklenen protokollerin ve sürümlerin listesini eşleştirmeye çalışır ve en tercih edilen eşleşmeyi seçer. Bu ilke ayarını etkinleştirirseniz tarayıcı, açılan listeden seçtiğiniz şifreleme yöntemlerini kullanarak bir şifreleme tüneli üzerinde anlaşır veya anlaşmaz. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, Kullanıcı tarayıcının desteklediği şifreleme yöntemini seçebilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067057)

  **Varsayılan**: 2 öğe: TLS v 1.1 ve TLS v 1.2  
  *Bu ayar için seçebileceğiniz seçenekleri göstermek için aşağı oku seçin.*
::: zone-end
::: zone pivot="mdm-preview,mdm-may-2019"

- **Internet Explorer kilitli Internet alanı akıllı ekranı**  
  Bu ilke ayarı, SmartScreen Filtresi 'nin bu bölgedeki sayfaları kötü amaçlı içerik için taramayacağını denetler. Bu ilke ayarını etkinleştirirseniz SmartScreen Filtresi bu bölgedeki sayfaları kötü amaçlı içeriğe karşı tarar. Bu ilke ayarını devre dışı bırakırsanız, SmartScreen Filtresi bu bölgedeki sayfaları kötü amaçlı içerik için taramaz. Bu ilke ayarını yapılandırmazsanız kullanıcı SmartScreen Filtresi 'nin bu bölgedeki sayfaları kötü amaçlı içerik için tarayıp taramayacağını seçebilir. Note: Internet Explorer 7 ' de bu ilke ayarı, kimlik avı filtresinin bu bölgedeki sayfaları kötü amaçlı içerik için taramayacağını denetler.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067059)  
  
  **Varsayılan**: etkin 
  
- **Internet Explorer kısıtlı bölge bir iFrame içindeki uygulamaları ve dosyaları başlatma**  
  Bu ilke ayarı, uygulamaların çalıştırılıp çalıştırılmadığını ve bu bölgedeki sayfaların HTML 'si içindeki bir IFRAME başvurusundan dosya indirilip indirilmeyeceğini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, kullanıcılar bu bölgedeki sayfalardaki IFRAME 'lerden Kullanıcı müdahalesi olmadan uygulama çalıştırabilir ve dosya indirebilir. Açılır kutuda sor ' u seçerseniz, kullanıcılar, bu bölgedeki sayfalardaki IFRAME 'lerden uygulama çalıştırıp indirme yapıp uygulamacağınızı seçmeleri istenir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcıların uygulama çalıştırması ve bu bölgedeki sayfalardaki IFRAME 'lerden dosya indirmeleri engellenir. Bu ilke ayarını yapılandırmazsanız, kullanıcıların uygulama çalıştırması ve bu bölgedeki sayfalardaki IFRAME 'lerden dosya indirmeleri engellenir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067061)  
  
  **Varsayılan**: devre dışı 
  
- **Internet Explorer, seyrek görülen dosyalarla ilgili akıllı ekran uyarılarını atla**  
  Bu ilke ayarı, kullanıcının SmartScreen filtresinden gelen uyarıları atlayıp atlayamayacağını belirler. SmartScreen Filtresi, Internet Explorer kullanıcılarının Internet 'ten yaygın olarak indirmediğini çalıştıran yürütülebilir dosyalar hakkında kullanıcıyı uyarır. Bu ilke ayarını etkinleştirirseniz SmartScreen Filtresi uyarıları kullanıcıyı engeller. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız kullanıcı SmartScreen Filtresi uyarılarını atlayabilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067068)  
  
  **Varsayılan**: devre dışı  
  
- **Internet Explorer Internet bölgesi açılır pencere engelleyicisi**  
  Bu ilke ayarı, istenmeyen açılır pencerelerin görünüp görünmeyeceğini yönetmenizi sağlar. Son Kullanıcı bir bağlantıya tıkladığında açılan açılır pencereler engellenmez. Bu ilke ayarını etkinleştirirseniz, istenmeyen açılır pencerelerin çoğunun görünmesi engellenir. Bu ilke ayarını devre dışı bırakırsanız, açılır pencerelerin görüntülenmesini önlenemez. Bu ilke ayarını yapılandırmazsanız, istenmeyen açılır pencerelerin çoğunun görünmesi engellenir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067069)  
  
  **Varsayılan**: etkinleştir  
  
- **Internet Explorer işleme tutarlı MIME işleme**  
  Internet Explorer dinamik ikili davranışları içerir: eklendiği HTML öğeleri için belirli işlevleri kapsülleyen bileşenler. Bu ilke ayarı, Ikili davranış güvenlik kısıtlaması ayarının engellenip engellenmeyeceğini veya izin verilmediğini denetler. Bu ilke ayarını etkinleştirirseniz, dosya Gezgini ve Internet Explorer işlemlerinde ikili davranışlar engellenir. Bu ilke ayarını devre dışı bırakırsanız, dosya Gezgini ve Internet Explorer işlemlerinde ikili davranışlara izin verilir. Bu ilke ayarını yapılandırmazsanız, dosya Gezgini ve Internet Explorer işlemlerinde ikili davranışlar engellenir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067144)  
  
  **Varsayılan**: etkin  
  
- **Internet Explorer kısıtlı bölge Java izinleri**  
  Bu ilke ayarı, Java uygulamaları için izinleri yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, açılan kutudan Seçenekler ' i seçebilirsiniz. Özel, izin ayarlarını tek tek denetlemek için. Düşük güvenlik, uygulamaların tüm işlemleri gerçekleştirmesini sağlar. Orta düzey güvenlik, uygulamaların korumalı alanları üzerinde (programın çağrı yapamasının dışında bir alan) ve boş alan (istemci bilgisayardaki güvenli ve güvenli bir depolama alanı) ve kullanıcı denetimli dosya g/ç gibi yetenekler üzerinde çalışmasına imkan sağlar. Yüksek güvenlik, uygulamaların kendi korumalı kuruluşlarının çalışmasına olanak sağlar. Tüm uygulamaların çalıştırılmasını engellemek için Java 'Yı devre dışı bırakın. Bu ilke ayarını devre dışı bırakırsanız, Java uygulamaları çalıştırılamaz. Bu ilke ayarını yapılandırmazsanız Java uygulamaları devre dışı bırakılır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067132)  
  
  **Varsayılan**: Java 'yı devre dışı bırak  
    
  
- **Korumalı modda Internet Explorer Active X denetimleri**  
  Bu ilke ayarı, Gelişmiş Korumalı mod etkinken ActiveX denetimlerinin korumalı modda çalışmasını engeller. Bir Kullanıcı, Gelişmiş Korumalı mod ile uyumlu olmayan bir ActiveX denetimine sahip olduğunda ve bir Web sitesi denetimi yüklemeye çalışırsa, Internet Explorer kullanıcıya bildirir ve Web sitesini normal korumalı modda çalıştırma seçeneği sunar. Bu ilke ayarı, bu bildirimi devre dışı bırakır ve tüm Web sitelerini gelişmiş korumalı modda çalışacak şekilde zorlar. Gelişmiş Korumalı mod, Windows 'un 64 bit sürümlerinde 64 bitlik süreçler kullanarak kötü amaçlı Web sitelerine karşı ek koruma sağlar. En az Windows 8 çalıştıran bilgisayarlarda, Gelişmiş Korumalı mod, Internet Explorer 'ın kayıt defterinden ve dosya sisteminde okuyamadığı konumları da sınırlar. Gelişmiş Korumalı mod etkinken ve bir Kullanıcı, Gelişmiş Korumalı modla uyumlu olmayan bir ActiveX denetimi yüklemeye çalışır bir Web sitesi içinde olduğunda, Internet Explorer kullanıcıya bildirir ve gelişmiş korumalı modu için devre dışı bırakma seçeneği sağlar. Bu belirli bir Web sitesi. Bu ilke ayarını etkinleştirirseniz, Internet Explorer kullanıcıya gelişmiş korumalı modu devre dışı bırakma seçeneğini vermez. Tüm korumalı mod Web siteleri, gelişmiş korumalı modda çalışır. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, Internet Explorer kullanıcılara bildirir ve normal korumalı modda uyumsuz ActiveX denetimleriyle Web sitelerini çalıştırma seçeneği sunar.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067145)  
  
  **Varsayılan**: devre dışı  
  
- **XAML dosyalarının Internet Explorer kısıtlı bölge yüklemesi**  
  Bu ilke ayarı, Extensible Application Markup Language (XAML) dosyalarının yüklenmesini yönetmenizi sağlar. XAML, Windows Presentation Foundation faydalanan zengin Kullanıcı arabirimleri ve grafikleri oluşturmak için yaygın olarak kullanılan XML tabanlı bildirime dayalı bir biçimlendirme dilidir. Bu ilke ayarını etkinleştirir ve açılır kutuyu etkinleştir olarak ayarlarsanız, XAML dosyaları Internet Explorer 'ın içine otomatik olarak yüklenir. Kullanıcı bu davranışı değiştiremez. Açılır kutuyu sor olarak ayarlarsanız, kullanıcıdan XAML dosyalarını yüklemesi istenir. Bu ilke ayarını devre dışı bırakırsanız, XAML dosyaları Internet Explorer 'ın içinde yüklenmez. Kullanıcı bu davranışı değiştiremez. Bu ilke ayarını yapılandırmazsanız, Kullanıcı XAML dosyalarını Internet Explorer içinde yükleyip yükleyemeyeceğine karar verebilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067070)  
  
  **Varsayılan**: devre dışı  
  
- **Internet Explorer komut dosyalı pencere güvenlik kısıtlamalarını işler**  
  Internet Explorer, komut dosyalarının çeşitli türlerin pencerelerini program aracılığıyla açmasına, yeniden boyutlandırmasına ve yeniden konumlandırmasına olanak tanır Pencere Kısıtlamaları güvenlik özelliği açılır pencereleri kısıtlar ve betiklerin, başlık ve durum çubuklarının Kullanıcı tarafından görülemeyen veya diğer pencerelerin başlık ve durum çubuklarının bir gizleme olmayan pencereler görüntülemesini engeller. Bu ilke ayarını etkinleştirirseniz, betikleştirilmiş pencereler tüm süreçler için kısıtlanır. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, betikleştirilmiş pencereler engellenmez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067146)  
  
  **Varsayılan**: etkin   
  
- **Internet Explorer kısıtlı bölgesi etkin X denetimleri ve eklentileri çalıştırma**  
  Bu ilke ayarı, ActiveX denetimlerinin ve eklentilerin belirtilen bölgedeki sayfalarda çalıştırılıp çalıştırılamayacağını yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, denetimler ve eklentiler Kullanıcı müdahalesi olmadan çalıştırılabilir. Açılır kutuda sor ' u seçtiyseniz, kullanıcılardan denetimlerin veya eklentinin çalışmasına izin verip vermeyeceklerini seçmesi istenir. Bu ilke ayarını devre dışı bırakırsanız, denetimlerin ve eklentilerin çalışması engellenir. Bu ilke ayarını yapılandırmazsanız, denetimlerin ve eklentilerin çalışması engellenir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067114) 
  
  **Varsayılan**: devre dışı  
  
- **Internet Explorer kısıtlı bölge betiği etkin X denetimleri betik için güvenli olarak işaretlendi**  
  Bu ilke ayarı, komut dosyası için güvenli olarak işaretlenmiş bir ActiveX denetiminin bir betikten etkileşime giremeyeceğini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, komut dosyası etkileşimi Kullanıcı müdahalesi olmadan otomatik olarak gerçekleşebilir. Açılır kutuda sor ' u seçerseniz, kullanıcılardan betik etkileşimine izin verip vermeyeceğinizi seçmeleri istenir. Bu ilke ayarını devre dışı bırakırsanız, betik etkileşiminin oluşmasını engellenir. Bu ilke ayarını yapılandırmazsanız, betik etkileşiminin oluşmasını engellenir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067062)  
  
  **Varsayılan**: devre dışı  
  
- **Internet Explorer kısıtlı bölge oturum açma seçenekleri**  
  Bu ilke ayarı, oturum açma seçeneklerinin ayarlarını yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, aşağıdaki oturum açma seçenekleri arasından seçim yapabilirsiniz. 
  - *Anonim* -http kimlik doğrulamasını devre dışı bırakmak ve yalnızca ortak Internet dosya SISTEMI (CIFS) protokolü için konuk hesabını kullanmak üzere anonim oturum açma özelliğini kullanın. 
  - *İstem* -Kullanıcı kimlikleri ve parolalar için kullanıcıları sorgulamak üzere Kullanıcı adı ve parola istemi kullanın. Kullanıcı sorgulandıktan sonra bu değerler sessizce oturum geri kalanı için kullanılabilir. 
  - *Yalnızca Intranet bölgesinde otomatik oturum açma* -bu seçeneği, kullanıcıları diğer bölgelerdeki Kullanıcı kimlikleri ve parolalar için sorgulamak üzere kullanın. Kullanıcı sorgulandıktan sonra bu değerler sessizce oturum geri kalanı için kullanılabilir. 
  - *Geçerli Kullanıcı adı ve parolasıyla otomatik oturum aç*-bu seçeneği, Windows NT Challenge yanıtı (NTLM kimlik doğrulaması olarak da bilinir) kullanarak oturum açmayı denemek için kullanın. Sunucu Windows NT Challenge yanıtını destekliyorsa, oturum açma oturum açmak için kullanıcının ağ kullanıcı adını ve parolasını kullanır. Sunucu Windows NT Challenge yanıtını desteklemiyorsa, Kullanıcı Kullanıcı adını ve parolayı sağlamak üzere sorgulanır. 

  Bu ilke ayarını devre dışı bırakırsanız, oturum açma *yalnızca Intranet bölgesinde otomatik oturum açma*olarak ayarlanır. Bu ilke ayarını yapılandırmazsanız, oturum açma, Kullanıcı adı ve parola *isteyecek* şekilde ayarlanır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067110)  
  
  **Varsayılan**: anonim  
  
- **Internet Explorer güvenilir bölge başlatma ve betik etkin X denetimleri güvenli olarak işaretlenmemiş**  
  Bu ilke ayarı, güvenli olarak işaretlenmemiş ActiveX denetimlerini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, ActiveX denetimleri çalışır, parametrelerle yüklenir ve güvenilir olmayan veriler veya betikler için nesne güvenliğini ayarlamadan komut dosyası. Bu ayar, güvenli ve yönetilen bölgeler dışında önerilmez. Bu ayar, komut dosyası oluşturma seçeneği için güvenli olarak işaretlenmiş betik ActiveX denetimlerini yoksayarak, hem güvensiz hem de güvenli denetimlerin başlatılmasına ve betiklere neden olur. Bu ilke ayarını etkinleştirir ve açılan kutuda sor ' u seçerseniz, kullanıcılara, denetimin parametrelerle veya betiklerle yüklenmesine izin verip vermeyecekleri sorulur. Bu ilke ayarını devre dışı bırakırsanız, güvenli hale getirilemeyen ActiveX denetimleri parametrelerle veya betiklerle yüklenmez. Bu ilke ayarını yapılandırmazsanız kullanıcılara, denetimin parametrelerle veya betiklerle yüklenmesine izin verip vermeyecekleri sorulur.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067137)  
  
  **Varsayılan**: devre dışı  
  
- **Internet Explorer sunucu sertifikasını iptal etme**  
  Bu ilke ayarı, Internet Explorer 'ın, sunucuların sertifikalarının iptal durumunu denetleyip denetmeyeceğini yönetmenizi sağlar. Sertifikalar tehlikeye atıldığında veya artık geçerli olmadığında iptal edilir ve bu seçenek, kullanıcıların sahte veya güvenli olmayan bir siteye gizli veriler göndermesini önler. Bu ilke ayarını etkinleştirirseniz, Internet Explorer sunucu sertifikalarının iptal edilip edilmediğini kontrol eder. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer, iptal edilip edilmediğini görmek için sunucu sertifikalarını denetlemez. Bu ilke ayarını yapılandırmazsanız Internet Explorer, iptal edilip edilmediğini görmek için sunucu sertifikalarını denetlemez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067046)  
  
  **Varsayılan**: etkin 
  
- **Internet Explorer Internet bölgesi daha az ayrıcalıklı siteler**  
  Bu ilke ayarı, kısıtlanmış siteler gibi daha az ayrıcalıklı bölgelerdeki Web sitelerinin bu bölgede gezinip gidemeyeceğini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, daha az ayrıcalıklı bölgelerdeki Web siteleri içinde yeni pencereler açabilir veya bu bölge üzerinde gezinebilirsiniz. Güvenlik bölgesi, bölge yükselmesi güvenlik özelliğinden koruma tarafından belirtilen ek bir güvenlik katmanı olmadan çalışacaktır. Açılır kutuda sor ' u seçerseniz, kullanıcıya riskli gezintinin gerçekleşmek üzere olduğunu belirten bir uyarı verilir. Bu ilke ayarını devre dışı bırakırsanız, olası zararlı gezintiler engellenir. Internet Explorer güvenlik özelliği, bölge yükselmesi özellik denetiminden koruma tarafından ayarlandığı şekilde bu bölgede bulunur. Bu ilke ayarını yapılandırmazsanız, daha az ayrıcalıklı bölgelerdeki Web siteleri içinde yeni pencereler açabilir veya bu bölge üzerinde gezinebilirsiniz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067109)  
  
  **Varsayılan**: devre dışı  
  
- **Internet Explorer kısıtlı bölge dosyası İndirmeleri**  
  Bu ilke ayarı, bölgeden dosya indirmelerine izin verilip verilmeyeceğini yönetmenizi sağlar. Bu seçenek, dosyanın teslim edildiği bölgeden değil, indirilmesine neden olan sayfanın bölgesi tarafından belirlenir. Bu ilke ayarını etkinleştirirseniz, dosyalar bölgeden indirilebilir. Bu ilke ayarını devre dışı bırakırsanız, dosyaların bölgeden indirilmesi engellenir. Bu ilke ayarını yapılandırmazsanız, dosyaların bölgeden indirilmesi engellenir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067038)  
  
  **Varsayılan**: devre dışı  
  
- **Internet Explorer Internet bölgesi çalıştırma .NET Framework Authenticode ile imzalanmış bağımlı bileşenler**  
  Bu ilke ayarı, Authenticode ile imzalanmış .NET Framework bileşenlerinin Internet Explorer 'dan yürütülüp yürütülmeyeceğini yönetmenizi sağlar. Bu bileşenler bir nesne etiketiyle başvurulan yönetilen denetimleri ve bir bağlantıdan başvurulan yönetilen yürütülebilir dosyaları içerir. Bu ilke ayarını etkinleştirirseniz, Internet Explorer imzalanmış yönetilen bileşenleri yürütür. Açılır kutuda sor ' u seçerseniz, Internet Explorer kullanıcıdan imzalanmış yönetilen bileşenleri çalıştırıp yürütmeyeceğini belirlemesini ister. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer imzalanmış yönetilen bileşenleri yürütmez. Bu ilke ayarını yapılandırmazsanız, Internet Explorer imzalanmış yönetilen bileşenleri yürütmez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067033)  
  
  **Varsayılan**: devre dışı  
  
- **Internet Explorer, etkin X denetimlerinin Kullanıcı başına yüklenmesini engelliyor**  
  Bu ilke ayarı, ActiveX denetimlerinin Kullanıcı bazında yüklenmesini engellemenizi sağlar. Bu ilke ayarını etkinleştirirseniz, ActiveX denetimleri Kullanıcı başına temelinde yüklenemez. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, ActiveX denetimleri Kullanıcı başına temelinde yüklenebilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067058)  
  
  **Varsayılan**: etkin  
  
- **Internet Explorer akıllı ekran filtresini yönetmeyi engelliyor**  
  Bu ilke ayarı, kullanıcının ziyaret ettikleri web sitesinin "kimlik avı" aracılığıyla kişisel bilgi toplamak için veya kötü amaçlı yazılım barındırmaya yönelik olarak tanındığı durumlarda kullanıcıyı uyaran SmartScreen Filtresi 'ni yönetmesini engeller. Bu ilke ayarını etkinleştirirseniz Kullanıcı SmartScreen Filtresi 'ni etkinleştirmek isteyip istemediğiniz sorulur. Filtreler izin verilenler listesinde olmayan tüm Web sitesi adresleri, kullanıcıya sormadan otomatik olarak Microsoft 'a gönderilir. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, kullanıcıdan ilk çalıştırma deneyimi sırasında SmartScreen Filtresi 'ni açıp açmayacağına karar vermesini istenir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067135)  
  
  **Varsayılan**: etkinleştir  
  
- **Internet Explorer işlem MIME algılaması güvenlik özelliği**  
  Bu ilke ayarı, Internet Explorer MIME algılaması 'nın bir türdeki dosyanın daha tehlikeli bir dosya türüne yükseltilmesini engelleyip engelmeyeceğini belirler. Bu ilke ayarını etkinleştirirseniz, MIME algılaması hiçbir şekilde bir türdeki dosyayı daha tehlikeli bir dosya türüne yükseltmez. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer işlemi bir MIME algılamasına bir tür dosyanın daha tehlikeli bir dosya türüne yükseltme yapmasına izin verir. Bu ilke ayarını yapılandırmazsanız, MIME algılaması hiçbir şekilde bir türdeki dosyayı daha tehlikeli bir dosya türüne yükseltmez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067124)  
  
  **Varsayılan**: etkin  
  
- **Internet Explorer kısıtlı bölge, imzalanmış etkin X denetimlerini indirin**  
  Bu ilke ayarı, kullanıcıların, bölgedeki bir sayfadan imzalı ActiveX denetimlerini indirip indirmeyeceğini yönetmenizi sağlar. Bu ilkeyi etkinleştirirseniz kullanıcılar, imzalanmış denetimleri kullanıcı müdahalesi olmadan indirebilir. Açılır kutuda sor ' u seçerseniz, kullanıcılara güvenilmeyen yayımcılar tarafından imzalanmış denetimlerin indirilip indirilmeyeceği sorgulanır. Güvenilen yayımcılar tarafından imzalanan kod sessizce indirilir. İlke ayarını devre dışı bırakırsanız, imzalanmış denetimler indirimez. Bu ilke ayarını yapılandırmazsanız kullanıcılara güvenilmeyen yayımcılar tarafından imzalanmış denetimlerin indirilip indirilmeyeceği istenir. Güvenilen yayımcılar tarafından imzalanan kod sessizce indirilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067120) 
  
  **Varsayılan**: devre dışı  
  
- **Internet Explorer otomatik olarak tamamlanır**  
  Bu otomatik tamamlanma özelliği, formlarda Kullanıcı adlarını ve parolalarını anımsayabilir ve önerebilir. Bu ayarı etkinleştirirseniz, Kullanıcı "formlardaki Kullanıcı adı ve parolaları" veya "parola kaydetmem iste" seçeneğini değiştiremez. Formlardaki kullanıcı adları ve parolalar için otomatik tamamlanma özelliği açıktır. "Parolaları kaydetmem için sor" seçeneğini belirleyip seçmemeye karar vermeniz gerekir. Bu ayarı devre dışı bırakırsanız, Kullanıcı "formlardaki Kullanıcı adı ve parolaları" veya "parola kaydetmem iste" öğesini değiştiremez. Formlardaki kullanıcı adları ve parolalar için otomatik tamamlanma özelliği kapalıdır. Kullanıcı da parola kaydetmeyeceğine izin sorulmayı kabul edebilir. Bu ayarı yapılandırmazsanız kullanıcı, formlarda Kullanıcı adı ve parolalar için otomatik tamamlamayı açma özgürlüğüne sahiptir ve parolaları kaydetmenizi isteme seçeneğini sunar. Bu seçeneği göstermek için kullanıcılar Internet Seçenekleri iletişim kutusunu açar, Içerikler sekmesine tıklayın ve Ayarlar düğmesine tıklayın.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067122)  
  
  **Varsayılan**: devre dışı  
  
- **Internet Explorer Internet bölgesi VBscript 'in çalışmasına izin verir**  
  Bu ilke ayarı, VBScript 'in belirli Internet Explorer bölgelerindeki sayfalarda çalıştırılıp etmeyeceğine karar vermenizi sağlar. Şu seçenekler mevcuttur: 
  - *Enable* -herhangi bir etkileşim olmadan belirli bölgelerdeki sayfalarda VBScript çalıştırmaları. 
  - *İstem* -çalışanlara VBScript 'in bölgede çalışmasına izin verip vermeyeceğine sorulur. 
  - *Disable* -VBScript 'in bölgede çalışması engellenir. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız VBScript, belirtilen bölgede herhangi bir etkileşim olmadan çalışır.    

  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067119)  
  
  **Varsayılan**: devre dışı  
  
- **Internet Explorer kısıtlı bölgesi yalnızca onaylanan etki alanlarının TDC etkin X denetimlerini kullanmasına izin verir**  
  Bu ilke ayarı, kullanıcının web sitelerinde TDC ActiveX denetimini çalıştırıp çalıştırameyeceğini denetler. Bu ilke ayarını etkinleştirirseniz, TDC ActiveX denetimi bu bölgedeki Web sitelerinden çalışmaz. Bu ilke ayarını devre dışı bırakırsanız, TDC etkin X denetimi bu bölgedeki tüm sitelerden çalıştırılır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067032)  
  
  **Varsayılan**: etkin  
  
- **Internet Explorer güvenilen bölgesi, etkin X denetimlerine karşı kötü amaçlı yazılımdan koruma çalıştırmayın**  
  Bu ilke ayarı, Internet Explorer 'ın, sayfalarda güvenli olup olmadığını denetlemek için kötü amaçlı yazılımdan koruma programlarını ActiveX denetimlerine karşı çalıştırmasını belirler. Bu ilke ayarını etkinleştirirseniz, Internet Explorer, ActiveX denetiminin bir örneğini oluşturmanın güvenli olup olmadığını görmek için kötü amaçlı yazılımdan koruma programınızı denetlemez. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer, ActiveX denetiminin bir örneğinin oluşturulması için güvenli olup olmadığını görmek üzere her zaman kötü amaçlı yazılımdan koruma programınızı denetler. Bu ilke ayarını yapılandırmazsanız, Internet Explorer, ActiveX denetiminin bir örneğinin oluşturulması için güvenli olup olmadığını görmek üzere her zaman kötü amaçlı yazılımdan koruma programınızı denetler. Kullanıcılar, Internet Explorer güvenlik ayarlarını kullanarak bu davranışı etkinleştirebilir veya devre dışı bırakabilirsiniz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067115)  
  
  **Varsayılan**: devre dışı 
  
- **Internet Explorer yerel makine bölgesi Java izinleri**  
  Bu ilke ayarı, Java uygulamaları için izinleri yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, açılan kutudan Seçenekler ' i seçebilirsiniz. Özel, izin ayarlarını tek tek denetlemek için. Düşük güvenlik, uygulamaların tüm işlemleri gerçekleştirmesini sağlar. Orta düzey güvenlik, uygulamaların korumalı alanları üzerinde (programın çağrı yapamasının dışında bir alan) ve boş alan (istemci bilgisayardaki güvenli ve güvenli bir depolama alanı) ve kullanıcı denetimli dosya g/ç gibi yetenekler üzerinde çalışmasına imkan sağlar. Yüksek güvenlik, uygulamaların kendi korumalı kuruluşlarının çalışmasına olanak sağlar. Tüm uygulamaların çalıştırılmasını engellemek için Java 'Yı devre dışı bırakın. Bu ilke ayarını devre dışı bırakırsanız, Java uygulamaları çalıştırılamaz. Bu ilke ayarını yapılandırmazsanız, izin orta düzey güvenlik olarak ayarlanır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067113)  
  
  **Varsayılan**: Java 'yı devre dışı bırak 
  
- **Internet Explorer intranet bölgesi, etkin X denetimlerine karşı kötü amaçlı yazılımdan koruma çalıştırmaz**  
  Bu ilke ayarı, Internet Explorer 'ın, sayfalarda güvenli olup olmadığını denetlemek için kötü amaçlı yazılımdan koruma programlarını ActiveX denetimlerine karşı çalıştırmasını belirler. Bu ilke ayarını etkinleştirirseniz, Internet Explorer, ActiveX denetiminin bir örneğini oluşturmanın güvenli olup olmadığını görmek için kötü amaçlı yazılımdan koruma programınızı denetlemez. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer, ActiveX denetiminin bir örneğinin oluşturulması için güvenli olup olmadığını görmek üzere her zaman kötü amaçlı yazılımdan koruma programınızı denetler. Bu ilke ayarını yapılandırmazsanız, Internet Explorer, ActiveX denetiminin bir örneğinin oluşturulması için güvenli olup olmadığını görmek üzere kötü amaçlı yazılımdan koruma programınızı denetlemez. Kullanıcılar, Internet Explorer güvenlik ayarlarını kullanarak bu davranışı etkinleştirebilir veya devre dışı bırakabilirsiniz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067138)  
  
  **Varsayılan**: devre dışı  

- **Internet Explorer kısıtlı bölge komut dosyası**  
  Bu ilke ayarı, kullanıcının kod parçacıklarına erişip çalıştıramayacağını yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz kullanıcı komut dosyası çalıştırılmasına izin verebilir. Bu ilke ayarını devre dışı bırakırsanız, Kullanıcı komut dosyası çalıştırılmasına izin vermez. Bu ilke ayarını yapılandırmazsanız kullanıcı kod parçacıklarını etkinleştirebilir veya devre dışı bırakabilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067112)  
  
  **Varsayılan**: devre dışı  
  
- **Internet Explorer işlem bildirim çubuğu**  
  Bu ilke ayarı, dosya veya kod yüklemeleri kısıtlandıktan sonra bildirim çubuğunun Internet Explorer işlemlerinde görüntülenip görüntülenmeyeceğini yönetmenizi sağlar. Varsayılan olarak, Internet Explorer işlemlerinde bildirim çubuğu görüntülenir. Bu ilke ayarını etkinleştirirseniz, Internet Explorer Işlemlerine yönelik bildirim çubuğu görüntülenir. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer işlemlerinde bildirim çubuğu gösterilmez. Bu ilke ayarını yapılandırmazsanız, Internet Explorer Işlemlerinde bildirim çubuğu görüntülenmez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067139)  
  
  **Varsayılan**: etkin  
  
- **Internet Explorer Internet bölgesi imzalı ActiveX denetimlerini indirme**  
  Bu ilke ayarı, kullanıcıların, bölgedeki bir sayfadan imzalı ActiveX denetimlerini indirip indirmeyeceğini yönetmenizi sağlar. Bu ilkeyi etkinleştirirseniz kullanıcılar, imzalanmış denetimleri kullanıcı müdahalesi olmadan indirebilir. Açılır kutuda sor ' u seçerseniz, kullanıcılara güvenilmeyen yayımcılar tarafından imzalanmış denetimlerin indirilip indirilmeyeceği sorgulanır. Güvenilen yayımcılar tarafından imzalanan kod sessizce indirilir. İlke ayarını devre dışı bırakırsanız, imzalanmış denetimler indirimez. Bu ilke ayarını yapılandırmazsanız kullanıcılara güvenilmeyen yayımcılar tarafından imzalanmış denetimlerin indirilip indirilmeyeceği istenir. Güvenilen yayımcılar tarafından imzalanan kod sessizce indirilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067064)  
  
  **Varsayılan**: devre dışı  
  
- **Internet Explorer kısıtlı bölge akıllı ekranı**  
  Bu ilke ayarı, SmartScreen Filtresi 'nin bu bölgedeki sayfaları kötü amaçlı içerik için taramayacağını denetler. Bu ilke ayarını etkinleştirirseniz SmartScreen Filtresi bu bölgedeki sayfaları kötü amaçlı içeriğe karşı tarar. Bu ilke ayarını devre dışı bırakırsanız, SmartScreen Filtresi bu bölgedeki sayfaları kötü amaçlı içerik için taramaz. Bu ilke ayarını yapılandırmazsanız kullanıcı SmartScreen Filtresi 'nin bu bölgedeki sayfaları kötü amaçlı içerik için tarayıp taramayacağını seçebilir. Note: Internet Explorer 7 ' de bu ilke ayarı, kimlik avı filtresinin bu bölgedeki sayfaları kötü amaçlı içerik için taramayacağını denetler.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067034)  
  
  **Varsayılan**: etkin  
  
- **Güncel olmayan etkin X denetimleri için Internet Explorer bu zamanı Çalıştır düğmesini kaldır**  
  Bu ilke ayarı, kullanıcıların "Bu saati Çalıştır" düğmesini görmesini ve Internet Explorer 'da tarihi geçmiş belirli ActiveX denetimlerini çalıştırmasını durdurmanızı sağlar. Bu ilke ayarını etkinleştirirseniz, kullanıcılar Internet Explorer tarihi geçmiş ActiveX denetimini engellediğinde görüntülenen uyarı iletisinde "Bu saati Çalıştır" düğmesini görmez. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, kullanıcılar Internet Explorer tarihi geçmiş ActiveX denetimini engellediğinde görüntülenen uyarı iletisinde "Bu saati Çalıştır" düğmesini görür. Bu düğmeye tıkladığınızda kullanıcının tarihi geçmiş ActiveX denetimini bir kez çalıştırmasına izin verir. Daha fazla bilgi için Internet Explorer TechNet Kitaplığı 'nda "güncel olmayan ActiveX denetimleri" bölümüne bakın.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067123)  
  
  **Varsayılan**: etkin 
  
- **Internet Explorer Internet bölgesi bir iframe içindeki uygulamaları ve dosyaları başlatma**  
  Bu ilke ayarı, uygulamaların çalıştırılıp çalıştırılmadığını ve bu bölgedeki sayfaların HTML 'si içindeki bir IFRAME başvurusundan dosya indirilip indirilmeyeceğini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, kullanıcılar bu bölgedeki sayfalardaki IFRAME 'lerden Kullanıcı müdahalesi olmadan uygulama çalıştırabilir ve dosya indirebilir. Açılır kutuda sor ' u seçerseniz, kullanıcılar, bu bölgedeki sayfalardaki IFRAME 'lerden uygulama çalıştırıp indirme yapıp uygulamacağınızı seçmeleri istenir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcıların uygulama çalıştırması ve bu bölgedeki sayfalardaki IFRAME 'lerden dosya indirmeleri engellenir. Bu ilke ayarını yapılandırmazsanız, kullanıcılar, bu bölgedeki sayfalardaki IFRAME 'lerden uygulama çalıştırıp indirme yapıp uygulamacağınızı seçmeleri istenir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067020)  
  
  **Varsayılan**: devre dışı 
  
- **Internet Explorer kısıtlı bölgesi farklı etki alanlarındaki pencereler ve çerçevelere gider**  
  Bu ilke ayarı, kaynak ve hedef farklı pencereler olduğunda bir etki alanından farklı bir etki alanına içerik sürükleme seçeneklerini ayarlamanıza olanak sağlar. Bu ilke ayarını etkinleştirir ve Etkinleştir ' e tıklarsanız, kullanıcılar, kaynak ve hedef farklı pencereler olduğunda bir etki alanından farklı bir etki alanına içerik sürükleyebilir. Kullanıcılar bu ayarı değiştiremezler. Bu ilke ayarını etkinleştirirseniz ve devre dışı bırak ' a tıkladığınızda, her ikisi de kaynak ve hedef farklı pencereler olduğunda, kullanıcılar bir etki alanından farklı bir etki alanına içerik sürüklenemez. Kullanıcılar bu ayarı değiştiremezler. Internet Explorer 10 ' da, bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız kullanıcılar, kaynak ve hedef farklı pencereler olduğunda bir etki alanından farklı bir etki alanına içerik sürüklenemez. Kullanıcılar bu ayarı Internet Seçenekleri iletişim kutusunda değiştirebilir. Internet Explorer 9 ve önceki sürümlerde, bu ilkeyi devre dışı bırakır veya yapılandırmazsanız, kullanıcılar, kaynak ve hedef farklı pencereler olduğunda bir etki alanından farklı bir etki alanına içerik sürükleyebilirsiniz. Kullanıcılar bu ayarı değiştiremezler.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067050)  
  
  **Varsayılan**: devre dışı  
  
- **Internet Explorer Internet bölgesi akıllı ekranı**  
  Bu ilke ayarı, SmartScreen Filtresi 'nin bu bölgedeki sayfaları kötü amaçlı içerik için taramayacağını denetler. Bu ilke ayarını etkinleştirirseniz SmartScreen Filtresi bu bölgedeki sayfaları kötü amaçlı içeriğe karşı tarar. Bu ilke ayarını devre dışı bırakırsanız, SmartScreen Filtresi bu bölgedeki sayfaları kötü amaçlı içerik için taramaz. Bu ilke ayarını yapılandırmazsanız kullanıcı SmartScreen Filtresi 'nin bu bölgedeki sayfaları kötü amaçlı içerik için tarayıp taramayacağını seçebilir. Note: Internet Explorer 7 ' de bu ilke ayarı, kimlik avı filtresinin bu bölgedeki sayfaları kötü amaçlı içerik için taramayacağını denetler.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067047)  
  
  **Varsayılan**: etkin  
  
- **Internet Explorer kilitli Güvenilen bölge Java izinleri**  
  Bu ilke ayarı, Java uygulamaları için izinleri yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, açılan kutudan Seçenekler ' i seçebilirsiniz. Özel, izin ayarlarını tek tek denetlemek için. Düşük güvenlik, uygulamaların tüm işlemleri gerçekleştirmesini sağlar. Orta düzey güvenlik, uygulamaların korumalı alanları üzerinde (programın çağrı yapamasının dışında bir alan) ve boş alan (istemci bilgisayardaki güvenli ve güvenli bir depolama alanı) ve kullanıcı denetimli dosya g/ç gibi yetenekler üzerinde çalışmasına imkan sağlar. Yüksek güvenlik, uygulamaların kendi korumalı kuruluşlarının çalışmasına olanak sağlar. Tüm uygulamaların çalıştırılmasını engellemek için Java 'Yı devre dışı bırakın. Bu ilke ayarını devre dışı bırakırsanız, Java uygulamaları çalıştırılamaz. Bu ilke ayarını yapılandırmazsanız Java uygulamaları devre dışı bırakılır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067142)  
  
  
  **Varsayılan**: Java 'yı devre dışı bırak 
  
- **Internet Explorer indirilen programlardaki imzaları denetle**  
  Bu ilke ayarı, Internet Explorer 'ın, yürütülebilir programları indirmeden önce kullanıcı bilgisayarlarında dijital imzaları (imzalı yazılımın yayımcısını tanımlar ve değiştirilmediğini veya kurcalanmadığını doğrular) denetleyip denetlemeyeceğini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, Internet Explorer çalıştırılabilir programların dijital imzalarını denetler ve kimliklerini kullanıcı bilgisayarlarına indirmeden önce görüntüler. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer yürütülebilir programların dijital imzalarını denetlemez veya kullanıcı bilgisayarlarına indirmeden önce kimliklerini görüntüler. Bu ilkeyi yapılandırmazsanız, Internet Explorer yürütülebilir programların dijital imzalarını denetlemez veya kullanıcı bilgisayarlarına indirmeden önce kimliklerini görüntüler.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067051)  
  
  **Varsayılan**: etkin  
  
- **Web tarayıcısı denetimlerinin Internet Explorer kısıtlı bölge betiği**  
  Bu ilke ayarı, bir sayfanın katıştırılmış WebBrowser denetimlerini betik aracılığıyla denetleyebilir olup olmayacağını belirler. Bu ilke ayarını etkinleştirirseniz, WebBrowser denetimine betik erişimine izin verilir. Bu ilke ayarını devre dışı bırakırsanız, WebBrowser denetimine betik erişimine izin verilmez. Bu ilke ayarını yapılandırmazsanız kullanıcı WebBrowser denetimine betik erişimini etkinleştirebilir veya devre dışı bırakabilir. Varsayılan olarak, WebBrowser denetimine betik erişimine yalnızca yerel makine ve Intranet bölgelerinde izin verilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067098)  
  
  **Varsayılan**: devre dışı  
  
- **Internet Explorer kısıtlı bölge siteler arası betik filtresi**  
  Bu ilke, siteler arası komut dosyası yazma (XSS) filtresinin bu bölgedeki Web sitelerine yönelik siteler arası betik oluşturmayı algılayıp engellemesine izin olup olmadığını denetler. Bu ilke ayarını etkinleştirirseniz, XSS filtresi bu bölgedeki siteler için açıktır ve XSS filtresi siteler arası betik oluşturma girişimlerini engellemeye çalışır. Bu ilke ayarını devre dışı bırakırsanız, bu bölgedeki siteler için XSS filtresi kapatılır ve Internet Explorer siteler arası betik oluşturma izni verir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067178)  
  
  **Varsayılan**: etkin  
  
- **Internet Explorer kısıtlı bölge ikili ve betik davranışları**  
  Bu ilke ayarı, dinamik ikili ve betik davranışlarını yönetmenizi sağlar: eklendiği HTML öğelerine yönelik belirli işlevleri kapsülleyen bileşenler. Bu ilke ayarını etkinleştirirseniz, ikili ve betik davranışları kullanılabilir. Açılan kutuda yönetici onaylı ' i seçerseniz, yalnızca Ikili davranışlar güvenlik kısıtlama ilkesi altındaki yönetici onaylı davranışlar bölümünde listelenen davranışlar vardır. Bu ilke ayarını devre dışı bırakırsanız, uygulamalar özel bir güvenlik yöneticisi uygulamadıkça ikili ve betik davranışları kullanılamaz. Bu ilke ayarını yapılandırmazsanız, uygulamalar özel bir güvenlik yöneticisi uygulamadıkça ikili ve betik davranışları kullanılamaz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067224)  
  
  **Varsayılan**: devre dışı  
  
- **Internet Explorer güvenlik ayarları denetimi**  
  Bu ilke ayarı, Internet Explorer güvenlik ayarlarını, ayarların ne zaman Internet Explorer 'ı riske sokması gerektiğini belirleyecek şekilde denetleyen güvenlik ayarları denetim özelliğini kapatır. Bu ilke ayarını etkinleştirirseniz, özellik kapalıdır. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, özellik açıktır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067182)  
  
  **Varsayılan**: etkin  
  
- **Güvenli olmayabilecek dosyalar için Internet Explorer Internet bölgesi güvenlik uyarısı**  
  Bu ilke ayarı, Kullanıcı yürütülebilir dosyaları veya diğer olası güvenli olmayan dosyaları (örneğin, dosya Gezgini 'ni kullanarak bir intranet dosya paylaşımından) açmaya çalıştığında "dosya güvenlik uyarısı aç" iletisinin görünüp görüntülenmeyeceğini denetler. Bu ilke ayarını etkinleştirir ve açılır kutuyu etkinleştir olarak ayarlarsanız, bu dosyalar güvenlik uyarısı olmadan açılır. Açılır kutuyu sor olarak ayarlarsanız, dosyalar açılmadan önce bir güvenlik uyarısı görüntülenir. Bu ilke ayarını devre dışı bırakırsanız, bu dosyalar açılmaz. Bu ilke ayarını yapılandırmazsanız kullanıcı bilgisayarın bu dosyaları nasıl işleyeceğini yapılandırabilir. Varsayılan olarak, bu dosyalar, Intranet ve yerel bilgisayar bölgelerinde etkin olan kısıtlanmış bölgede engellenir ve Internet ve güvenilen bölgelerde sorulacak şekilde ayarlanır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067204)  
  
  **Varsayılan**: istem  
  
- **Internet Explorer intranet bölgesi Java izinleri**  
  Bu ilke ayarı, Java uygulamaları için izinleri yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, açılan kutudan Seçenekler ' i seçebilirsiniz. Özel, izin ayarlarını tek tek denetlemek için. Düşük güvenlik, uygulamaların tüm işlemleri gerçekleştirmesini sağlar. Orta düzey güvenlik, uygulamaların korumalı alanları üzerinde (programın çağrı yapamasının dışında bir alan) ve boş alan (istemci bilgisayardaki güvenli ve güvenli bir depolama alanı) ve kullanıcı denetimli dosya g/ç gibi yetenekler üzerinde çalışmasına imkan sağlar. Yüksek güvenlik, uygulamaların kendi korumalı kuruluşlarının çalışmasına olanak sağlar. Tüm uygulamaların çalıştırılmasını engellemek için Java 'Yı devre dışı bırakın. Bu ilke ayarını devre dışı bırakırsanız, Java uygulamaları çalıştırılamaz. Bu ilke ayarını yapılandırmazsanız, izin orta düzey güvenlik olarak ayarlanır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067206)  
  
  **Varsayılan**: yüksek güvenilirlik 
  
- **Internet Explorer blok süresi geçmiş etkin X denetimlerini**   
  Bu ilke ayarı, Internet Explorer 'ın güncelliğini yitirmiş belirli ActiveX denetimlerini engellediğini belirler. Güncel olmayan ActiveX denetimleri, Intranet bölgesinde hiçbir şekilde engellenmez. Bu ilke ayarını etkinleştirirseniz, Internet Explorer tarihi geçmiş ActiveX denetimlerini engellemeyi durduruyor. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, Internet Explorer tarihi geçmiş belirli ActiveX denetimlerini engellemeye devam eder. Daha fazla bilgi için Internet Explorer TechNet Kitaplığı 'nda "güncel olmayan ActiveX denetimleri" bölümüne bakın.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067203)  
  
  **Varsayılan**: etkin  
  
- **Internet Explorer kısıtlı bölge açılan pencere engelleyicisi**  
  Bu ilke ayarı, istenmeyen açılır pencerelerin görünüp görünmeyeceğini yönetmenizi sağlar. Son Kullanıcı bir bağlantıya tıkladığında açılan açılır pencereler engellenmez. Bu ilke ayarını etkinleştirirseniz, istenmeyen açılır pencerelerin çoğunun görünmesi engellenir. Bu ilke ayarını devre dışı bırakırsanız, açılır pencerelerin görüntülenmesini önlenemez. Bu ilke ayarını yapılandırmazsanız, istenmeyen açılır pencerelerin çoğunun görünmesi engellenir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067180)  
  
  **Varsayılan**: etkinleştir  
  
- **Internet Explorer işlem MK protokol güvenlik kısıtlaması**  
  MK Protokol güvenliği kısıtlama ilkesi ayarı, MK protokolünü engellemek için saldırı yüzeyi alanını azaltır. MK protokolünde barındırılan kaynaklar başarısız olur. Bu ilke ayarını etkinleştirirseniz, MK protokolü dosya Gezgini ve Internet Explorer için engellenir ve MK protokolünde barındırılan kaynaklar başarısız olur. Bu ilke ayarını devre dışı bırakırsanız, uygulamalar MK protokol API 'sini kullanabilir. MK protokolünde barındırılan kaynaklar dosya Gezgini ve Internet Explorer işlemlerinde çalışır. Bu ilke ayarını yapılandırmazsanız, MK protokolü dosya Gezgini ve Internet Explorer için engellenir ve MK protokolünde barındırılan kaynaklar başarısız olur.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067179)  
  
  **Varsayılan**: etkin  
  
- **Internet Explorer güvenilen bölge Java izinleri**   
  Bu ilke ayarı, Java uygulamaları için izinleri yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, açılan kutudan Seçenekler ' i seçebilirsiniz. Özel, izin ayarlarını tek tek denetlemek için. Düşük güvenlik, uygulamaların tüm işlemleri gerçekleştirmesini sağlar. Orta düzey güvenlik, uygulamaların korumalı alanları üzerinde (programın çağrı yapamasının dışında bir alan) ve boş alan (istemci bilgisayardaki güvenli ve güvenli bir depolama alanı) ve kullanıcı denetimli dosya g/ç gibi yetenekler üzerinde çalışmasına imkan sağlar. Yüksek güvenlik, uygulamaların kendi korumalı kuruluşlarının çalışmasına olanak sağlar. Tüm uygulamaların çalıştırılmasını engellemek için Java 'Yı devre dışı bırakın. Bu ilke ayarını devre dışı bırakırsanız, Java uygulamaları çalıştırılamaz. Bu ilke ayarını yapılandırmazsanız, izin düşük güvenilirlik olarak ayarlanır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067200)  
  
  **Varsayılan**: yüksek güvenilirlik  
  
- **Java uygulamalarının Internet Explorer kısıtlı bölge betiği**  
  Bu ilke ayarı, uygulamaların bölge içindeki betiklerin gösterilip gösterilmediğini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz betikler, Kullanıcı müdahalesi olmadan uygulamalara otomatik olarak erişebilir. Açılır kutuda sor ' u seçerseniz, kullanıcıların betiklerin uygulamalara erişmesine izin verip vermeyeceğinizi seçmeleri istenir. Bu ilke ayarını devre dışı bırakırsanız, betiklerin uygulamalara erişmesi engellenir. Bu ilke ayarını yapılandırmazsanız betiklerin uygulamalara erişmesi engellenir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067202)  
  
  **Varsayılan**: devre dışı  
  
- **Internet Explorer kısıtlı bölge Java izinlerini kilitli**   
  Bu ilke ayarı, Java uygulamaları için izinleri yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, açılan kutudan Seçenekler ' i seçebilirsiniz. Özel, izin ayarlarını tek tek denetlemek için. Düşük güvenlik, uygulamaların tüm işlemleri gerçekleştirmesini sağlar. Orta düzey güvenlik, uygulamaların korumalı alanları üzerinde (programın çağrı yapamasının dışında bir alan) ve boş alan (istemci bilgisayardaki güvenli ve güvenli bir depolama alanı) ve kullanıcı denetimli dosya g/ç gibi yetenekler üzerinde çalışmasına imkan sağlar. Yüksek güvenlik, uygulamaların kendi korumalı kuruluşlarının çalışmasına olanak sağlar. Tüm uygulamaların çalıştırılmasını engellemek için Java 'Yı devre dışı bırakın. Bu ilke ayarını devre dışı bırakırsanız, Java uygulamaları çalıştırılamaz. Bu ilke ayarını yapılandırmazsanız Java uygulamaları devre dışı bırakılır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067181)  
  
  **Varsayılan**: Java 'yı devre dışı bırak 
  
- **Internet Explorer Internet bölgesi yalnızca onaylanan etki alanlarının ActiveX denetimlerini kullanmasına izin verir**   
  Bu ilke ayarı, kullanıcıdan ActiveX denetimini yükleyen web sitesi dışındaki web sitelerinde ActiveX denetimlerinin çalışmasına izin istenip istenmeyeceğini denetler. Bu ilke ayarını etkinleştirirseniz, bu bölgedeki Web sitelerinden ActiveX denetimleri çalıştırılmadan önce kullanıcıya sorulur. Kullanıcı, denetimin geçerli siteden veya tüm sitelerden çalışmasına izin vermeyi seçebilir. Bu ilke ayarını devre dışı bırakırsanız, Kullanıcı site başına ActiveX istemi 'ni görmez ve ActiveX denetimleri bu bölgedeki tüm sitelerden çalıştırılabilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067091)  
  
  **Varsayılan**: etkin  
  
- **Internet Explorer tüm ağ yollarını içerir**  
  Internet Explorer tüm ağ yollarını içerir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067090)  
  
  **Varsayılan**: devre dışı 
  
- **Internet Explorer Internet bölgesi korumalı modu**  
  Bu ilke ayarı, korumalı modu açmanıza olanak tanır. Korumalı mod, Internet Explorer 'ın kayıt defterine ve dosya sistemine yazabilecek konumları azaltarak Internet Explorer 'ın açıktan yararlanan güvenlik açıklarına karşı korunmasına yardımcı olur. Bu ilke ayarını etkinleştirirseniz, korumalı mod açıktır. Kullanıcı korumalı modu kapatamaz. Bu ilke ayarını devre dışı bırakırsanız, korumalı mod kapalıdır. Kullanıcı korumalı modu açamaz. Bu ilke ayarını yapılandırmazsanız kullanıcı korumalı modu etkinleştirebilir veya devre dışı bırakabilirsiniz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067171)  
  
  **Varsayılan**: etkinleştir 
  
- **Internet Explorer Internet bölgesi başlatma ve betik etkin X denetimleri güvenli olarak işaretlenmemiş**  
  Bu ilke ayarı, güvenli olarak işaretlenmemiş ActiveX denetimlerini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, ActiveX denetimleri çalışır, parametrelerle yüklenir ve güvenilir olmayan veriler veya betikler için nesne güvenliğini ayarlamadan komut dosyası. Bu ayar, güvenli ve yönetilen bölgeler dışında önerilmez. Bu ayar, komut dosyası oluşturma seçeneği için güvenli olarak işaretlenmiş betik ActiveX denetimlerini yoksayarak, hem güvensiz hem de güvenli denetimlerin başlatılmasına ve betiklere neden olur. Bu ilke ayarını etkinleştirir ve açılan kutuda sor ' u seçerseniz, kullanıcılara, denetimin parametrelerle veya betiklerle yüklenmesine izin verip vermeyecekleri sorulur. Bu ilke ayarını devre dışı bırakırsanız, güvenli hale getirilemeyen ActiveX denetimleri parametrelerle veya betiklerle yüklenmez. Bu ilke ayarını yapılandırmazsanız, güvenli hale getirilemeyen ActiveX denetimleri parametrelerle veya betiklerle yüklenmez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067170)  
  
  **Varsayılan**: devre dışı 
  
- **Internet Explorer kilitli, kısıtlı bölge akıllı ekranını**   
  Bu ilke ayarı, SmartScreen Filtresi 'nin bu bölgedeki sayfaları kötü amaçlı içerik için taramayacağını denetler. Bu ilke ayarını etkinleştirirseniz SmartScreen Filtresi bu bölgedeki sayfaları kötü amaçlı içeriğe karşı tarar. Bu ilke ayarını devre dışı bırakırsanız, SmartScreen Filtresi bu bölgedeki sayfaları kötü amaçlı içerik için taramaz. Bu ilke ayarını yapılandırmazsanız kullanıcı SmartScreen Filtresi 'nin bu bölgedeki sayfaları kötü amaçlı içerik için tarayıp taramayacağını seçebilir. Note: Internet Explorer 7 ' de bu ilke ayarı, kimlik avı filtresinin bu bölgedeki sayfaları kötü amaçlı içerik için taramayacağını denetler.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067092)  
  
  **Varsayılan**: etkin  
  
- **Internet Explorer kilitlenme algılaması**  
  Bu ilke ayarı, eklenti yönetiminin kilitlenme algılama özelliğini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz Internet Explorer 'da bir kilitlenme, Windows XP Professional Service Pack 1 ve önceki sürümlerde bulunan ve Windows Hata Bildirimi çağırmak için bir davranış sergiler. Windows Hata Bildirimi için tüm ilke ayarları uygulanmaya devam eder. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, eklenti yönetimi için kilitlenme algılama özelliği çalışır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067094)  
  
  **Varsayılan**: devre dışı  
  
- **Internet Explorer Internet bölgesi Java izinleri**  
  Bu ilke ayarı, Java uygulamaları için izinleri yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, açılan kutudan Seçenekler ' i seçebilirsiniz. Özel, izin ayarlarını tek tek denetlemek için. Düşük güvenlik, uygulamaların tüm işlemleri gerçekleştirmesini sağlar. Orta düzey güvenlik, uygulamaların korumalı alanları üzerinde (programın çağrı yapamasının dışında bir alan) ve boş alan (istemci bilgisayardaki güvenli ve güvenli bir depolama alanı) ve kullanıcı denetimli dosya g/ç gibi yetenekler üzerinde çalışmasına imkan sağlar. Yüksek güvenlik, uygulamaların kendi korumalı kuruluşlarının çalışmasına olanak sağlar. Tüm uygulamaların çalıştırılmasını engellemek için Java 'Yı devre dışı bırakın. Bu ilke ayarını devre dışı bırakırsanız, Java uygulamaları çalıştırılamaz. Bu ilke ayarını yapılandırmazsanız, izin yüksek güvenlik olarak ayarlanır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067174)  
  
  **Varsayılan**: Java 'yı devre dışı bırak  
  
- **Internet Explorer kısıtlı bölge etkin komut dosyası**  
  Bu ilke ayarı, bölgedeki sayfalarda betik kodunun çalıştırılıp çalıştırılmadığını yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, bölgedeki sayfalardaki betik kodu otomatik olarak çalışabilir. Açılır kutuda sor ' u seçerseniz, kullanıcılar bölgedeki sayfalarda komut dosyası kodunun çalışmasına izin verilip verilmeyeceğini belirlemek için sorgulanır. Bu ilke ayarını devre dışı bırakırsanız, bölgedeki sayfalardaki betik kodunun çalışması engellenir. Bu ilke ayarını yapılandırmazsanız bölgedeki sayfalardaki betik kodunun çalışması engellenir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067172)  
  
  **Varsayılan**: devre dışı  
  
- **Internet Explorer Internet bölgesi oturum açma seçenekleri**  
  Bu ilke ayarı, oturum açma seçeneklerinin ayarlarını yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, aşağıdaki oturum açma seçenekleri arasından seçim yapabilirsiniz. HTTP kimlik doğrulamasını devre dışı bırakmak için anonim oturum açın ve yalnızca ortak Internet dosya sistemi (CIFS) protokolü için konuk hesabını kullanın. Kullanıcı kimlikleri ve parolaları için kullanıcıları sorgulamak üzere Kullanıcı adı ve parola iste. Kullanıcı sorgulandıktan sonra bu değerler, oturumun geri kalanı için sessizce kullanılabilir. Kullanıcıları diğer bölgelerdeki Kullanıcı kimlikleri ve parolalar için sorgulamak üzere yalnızca Intranet bölgesinde otomatik oturum açma. Kullanıcı sorgulandıktan sonra bu değerler sessizce oturum geri kalanı için kullanılabilir. Windows NT Challenge yanıtı (NTLM kimlik doğrulaması olarak da bilinir) kullanarak oturum açmayı denemek için geçerli Kullanıcı adı ve parolasıyla otomatik olarak oturum açın. Sunucu Windows NT Challenge yanıtını destekliyorsa, oturum açma oturum açmak için kullanıcının ağ kullanıcı adını ve parolasını kullanır. Sunucu Windows NT Challenge yanıtını desteklemiyorsa, Kullanıcı Kullanıcı adını ve parolayı sağlamak üzere sorgulanır. Bu ilke ayarını devre dışı bırakırsanız, oturum açma yalnızca Intranet bölgesinde otomatik oturum açma olarak ayarlanır. Bu ilke ayarını yapılandırmazsanız, oturum açma yalnızca Intranet bölgesinde otomatik oturum açma olarak ayarlanır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067194)  
  
  **Varsayılan**: istem  
  
- **Internet Explorer kısıtlı bölgesi VBScript 'in çalışmasına izin**   
  Bu ilke ayarı, VBScript 'in Internet Explorer 'da belirtilen bölgedeki sayfalarda çalıştırılıp çalıştırılamayacağını yönetmenizi sağlar. Açılır kutuda etkinleştir ' i seçtiyseniz, VBScript Kullanıcı müdahalesi olmadan çalıştırılabilir. Açılır kutuda sor ' u seçtiyseniz, kullanıcılardan VBScript 'in çalışmasına izin verip vermeyeceklerini seçmesi istenir. Açılan kutuda devre dışı bırak ' ı seçtiyseniz, VBScript 'in çalışması engellenir. Bu ilke ayarını yapılandırmazsanız veya devre dışı bırakırsanız, VBScript 'in çalışması engellenir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067173)  
  
  **Varsayılan**: devre dışı  
  
- **Internet Explorer Internet bölgesi Windows genelindeki farklı etki alanlarından içerik sürükle**  
  Bu ilke ayarı, kaynak ve hedef farklı pencereler olduğunda bir etki alanından farklı bir etki alanına içerik sürükleme seçeneklerini ayarlamanıza olanak sağlar. Bu ilke ayarını etkinleştirir ve Etkinleştir ' e tıklarsanız, kullanıcılar, kaynak ve hedef farklı pencereler olduğunda bir etki alanından farklı bir etki alanına içerik sürükleyebilir. Kullanıcılar bu ayarı değiştiremezler. Bu ilke ayarını etkinleştirirseniz ve devre dışı bırak ' a tıkladığınızda, her ikisi de kaynak ve hedef farklı pencereler olduğunda, kullanıcılar bir etki alanından farklı bir etki alanına içerik sürüklenemez. Kullanıcılar bu ayarı değiştiremezler. Internet Explorer 10 ' da, bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız kullanıcılar, kaynak ve hedef farklı pencereler olduğunda bir etki alanından farklı bir etki alanına içerik sürüklenemez. Kullanıcılar bu ayarı Internet Seçenekleri iletişim kutusunda değiştirebilir. Internet Explorer 9 ve önceki sürümlerde, bu ilkeyi devre dışı bırakır veya yapılandırmazsanız, kullanıcılar, kaynak ve hedef farklı pencereler olduğunda bir etki alanından farklı bir etki alanına içerik sürükleyebilirsiniz. Kullanıcılar bu ayarı değiştiremezler.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067093)  
  
  **Varsayılan**: devre dışı 
  
- **Internet Explorer intranet bölgesi başlatma ve betik etkin X denetimleri güvenli olarak işaretlenmemiş**  
  Bu ilke ayarı, güvenli olarak işaretlenmemiş ActiveX denetimlerini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, ActiveX denetimleri çalışır, parametrelerle yüklenir ve güvenilir olmayan veriler veya betikler için nesne güvenliğini ayarlamadan komut dosyası. Bu ayar, güvenli ve yönetilen bölgeler dışında önerilmez. Bu ayar, komut dosyası oluşturma seçeneği için güvenli olarak işaretlenmiş betik ActiveX denetimlerini yoksayarak, hem güvensiz hem de güvenli denetimlerin başlatılmasına ve betiklere neden olur. Bu ilke ayarını etkinleştirir ve açılan kutuda sor ' u seçerseniz, kullanıcılara, denetimin parametrelerle veya betiklerle yüklenmesine izin verip vermeyecekleri sorulur. Bu ilke ayarını devre dışı bırakırsanız, güvenli hale getirilemeyen ActiveX denetimleri parametrelerle veya betiklerle yüklenmez. Bu ilke ayarını yapılandırmazsanız, güvenli hale getirilemeyen ActiveX denetimleri parametrelerle veya betiklerle yüklenmez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067175)  
  
  **Varsayılan**: devre dışı 
  
- **Internet Explorer indirme kasaları**  
  Bu ilke ayarı, kullanıcının bir akıştan kullanıcı bilgisayarına indirilen kasaları (dosya ekleri) olmasını engeller. Bu ilke ayarını etkinleştirirseniz Kullanıcı, akış özelliği sayfası aracılığıyla bir kutu indirmek için akış eşitleme altyapısını ayarlayamıyorum. Geliştirici, akış API 'Leri aracılığıyla indirme ayarını değiştiremez. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, Kullanıcı akış eşitleme altyapısını, akış özelliği sayfasından bir kutu indirmek üzere ayarlayabilir. Geliştirici, akış API 'Leri aracılığıyla indirme ayarını değiştirebilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067245)  
  
  **Varsayılan**: devre dışı  
  
- **Internet Explorer kısıtlı bölge imzasız etkin X denetimlerini indirme**  
  Bu ilke ayarı, kullanıcıların imzasız ActiveX denetimlerini bölgeden yükleyip yükleyemeyeceğini yönetmenizi sağlar. Bu kod, özellikle güvenilmeyen bir bölgeden geldiği zaman zararlı olabilir. Bu ilke ayarını etkinleştirirseniz, kullanıcılar imzasız denetimleri kullanıcı müdahalesi olmadan çalıştırabilir. Açılır kutuda sor ' u seçerseniz, kullanıcılardan imzasız denetimin çalışmasına izin verip vermeyeceğinizi seçmeleri istenir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcılar imzasız denetimleri çalıştıramıyorum. Bu ilke ayarını yapılandırmazsanız kullanıcılar imzasız denetimleri çalıştırmaz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067177)  
  
  **Varsayılan**: devre dışı  
  
- **Internet Explorer Internet bölgesi Windows içindeki farklı etki alanlarından içerik sürükle**  
  Bu ilke ayarı, kullanıcıların imzasız ActiveX denetimlerini bölgeden yükleyip yükleyemeyeceğini yönetmenizi sağlar. Bu kod, özellikle güvenilmeyen bir bölgeden geldiği zaman zararlı olabilir. Bu ilke ayarını etkinleştirirseniz, kullanıcılar imzasız denetimleri kullanıcı müdahalesi olmadan çalıştırabilir. Açılır kutuda sor ' u seçerseniz, kullanıcılardan imzasız denetimin çalışmasına izin verip vermeyeceğinizi seçmeleri istenir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcılar imzasız denetimleri çalıştıramıyorum. Bu ilke ayarını yapılandırmazsanız kullanıcılar imzasız denetimleri çalıştırmaz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067095)  
  
  **Varsayılan**: devre dışı  
  
- **Internet Explorer işlemi, etkin X yüklemesini kısıtlar**   
  Bu ilke ayarı, Web tarayıcısı denetimini barındıran uygulamaların, ActiveX denetimi yüklemesinin otomatik olarak sorulmasını engellemesini sağlar. Bu ilke ayarını etkinleştirirseniz, Web tarayıcısı denetimi tüm işlemlerde ActiveX denetimi yüklemesinin otomatik olarak sorulmasını engeller. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, Web tarayıcısı denetimi tüm işlemlerde ActiveX denetimi yüklemesinin otomatik olarak sorulmasını engellemez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067250)  
  
  **Varsayılan**: etkin  
  
- **Internet Explorer Internet bölgesi komut dosyası**  
  Bu ilke ayarı, kullanıcının kod parçacıklarına erişip çalıştıramayacağını yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz kullanıcı komut dosyası çalıştırılmasına izin verebilir. Bu ilke ayarını devre dışı bırakırsanız, Kullanıcı komut dosyası çalıştırılmasına izin vermez. Bu ilke ayarını yapılandırmazsanız kullanıcı kod parçacıklarını etkinleştirebilir veya devre dışı bırakabilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067176)  
  
  **Varsayılan**: devre dışı  
  
- **Internet Explorer kısıtlı bölge sürükle ve bırak veya dosyaları kopyala ve Yapıştır**  
  Bu ilke ayarı, kullanıcıların bölge içindeki bir kaynaktan dosya sürükleyip sürükleyemeyeceğini veya dosya kopyalayıp yapıştıramayacağını yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, kullanıcılar dosyaları sürükleyebilir veya bu bölgeden otomatik olarak dosya kopyalayabilir ve yapıştırabilir. Açılır kutuda sor ' u seçerseniz, kullanıcıların bu bölgeden dosya sürükleyip sürükleyeceğinizi veya kopyalanıp kopyalanmayacağını seçmeleri istenir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcıların bu bölgeden dosya sürüklenmesi veya dosyaları kopyalaması ve yapıştırması engellenir. Bu ilke ayarını yapılandırmazsanız, kullanıcıların bu bölgeden dosya sürükleyip sürükleyeceğinizi veya kopyalanıp kopyalanmayacağını seçmesi istenir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067096)  
  
  **Varsayılan**: devre dışı  
  
- **İmza geçersiz olduğunda Internet Explorer yazılımı**  
  Bu ilke ayarı, imza geçersiz olsa bile, ActiveX denetimleri ve dosya indirmeleri gibi yazılımların Kullanıcı tarafından yüklenip yüklenmeyeceğini veya çalıştırılıp çalıştırılamayacağını yönetmenizi sağlar. Geçersiz bir imza, birisinin dosya üzerinde değişiklik yaptığını gösterebilir. Bu ilke ayarını etkinleştirirseniz, kullanıcılardan geçersiz imzalı dosyaları yüklemesi veya çalıştırmaları istenir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcılar geçersiz imzalı dosyaları çalıştıramıyorum veya yükleyemez. Bu ilkeyi yapılandırmazsanız, kullanıcılar geçersiz imzalı dosyaları çalıştırmayı veya yüklemeyi seçebilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067201)
  
  **Varsayılan**: devre dışı  
  
- **Internet Explorer kısıtlı bölge kopyalama ve betik aracılığıyla yapıştırma**  
  Bu ilke ayarı, betiklerin belirtilen bölgede bir Pano işlemi gerçekleştirip gerçekleştiremeyeceğini (örneğin, kesme, kopyalama ve yapıştırma) yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz bir betik bir Pano işlemi gerçekleştirebilir. Açılır kutuda sor ' u seçerseniz, kullanıcılar Pano işlemleri yapıp gerçekleştirmeyeceği gibi sorgulanır. Bu ilke ayarını devre dışı bırakırsanız, bir betik bir Pano işlemi gerçekleştiremez. Bu ilke ayarını yapılandırmazsanız bir betik bir Pano işlemi gerçekleştiremez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067165)  
  
  **Varsayılan**: devre dışı  
  
- **Internet Explorer kısıtlı bölgesi Windows üzerinde farklı etki alanlarından içerik sürükle**  
  Bu ilke ayarı, kaynak ve hedef farklı pencereler olduğunda bir etki alanından farklı bir etki alanına içerik sürükleme seçeneklerini ayarlamanıza olanak sağlar. Bu ilke ayarını etkinleştirir ve Etkinleştir ' e tıklarsanız, kullanıcılar, kaynak ve hedef farklı pencereler olduğunda bir etki alanından farklı bir etki alanına içerik sürükleyebilir. Kullanıcılar bu ayarı değiştiremezler. Bu ilke ayarını etkinleştirirseniz ve devre dışı bırak ' a tıkladığınızda, her ikisi de kaynak ve hedef farklı pencereler olduğunda, kullanıcılar bir etki alanından farklı bir etki alanına içerik sürüklenemez. Kullanıcılar bu ayarı değiştiremezler. Internet Explorer 10 ' da, bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız kullanıcılar, kaynak ve hedef farklı pencereler olduğunda bir etki alanından farklı bir etki alanına içerik sürüklenemez. Kullanıcılar bu ayarı Internet Seçenekleri iletişim kutusunda değiştirebilir. Internet Explorer 9 ve önceki sürümlerde, bu ilkeyi devre dışı bırakır veya yapılandırmazsanız, kullanıcılar, kaynak ve hedef farklı pencereler olduğunda bir etki alanından farklı bir etki alanına içerik sürükleyebilirsiniz. Kullanıcılar bu ayarı değiştiremezler.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067166)   

  **Varsayılan**: devre dışı  
  
- **Siteleri ekleyen Internet Explorer kullanıcıları**  
  Kullanıcıların güvenlik bölgelerinden site eklemesini veya kaldırmasını engeller. Güvenlik bölgesi, aynı güvenlik düzeyine sahip bir Web siteleri grubudur. Bu ilkeyi etkinleştirirseniz güvenlik bölgelerinin site yönetim ayarları devre dışı bırakılır. (Güvenlik bölgelerinin site yönetim ayarlarını görmek için, Internet Seçenekleri iletişim kutusunda Güvenlik sekmesine tıklayın ve ardından siteler düğmesine tıklayın.) Bu ilkeyi devre dışı bırakır veya yapılandırmazsanız, kullanıcılar güvenilen siteler ve Yasak Siteler bölgelerine Web siteleri ekleyebilir veya kaldırabilir ve yerel Intranet bölgesi için ayarları değiştirebilirsiniz. Bu ilke, kullanıcıların yönetici tarafından belirlenen güvenlik bölgelerinin site yönetim ayarlarını değiştirmesini engeller. Note: arabirimden Güvenlik sekmesini kaldıran "Güvenlik sayfasını devre dışı bırak" ilkesi (Kullanıcı Yapılandırması \ Yönetim Şablonları \ Windows bileşenleri \ Denetim Masası ' nda bulunur) Bu ilkeden önceliklidir. Etkinleştirilirse, bu ilke yok sayılır. Ayrıca bkz. "güvenlik bölgeleri: yalnızca makine ayarlarını kullanma" ilkesi.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067167)  
  
  **Varsayılan**: devre dışı  
  
- **Internet Explorer Internet bölgesi betiği başlatılan Windows**  
  Bu ilke ayarı, başlık ve durum çubuklarını içeren, betik ile başlatılan açılır pencereler ve pencereler üzerindeki kısıtlamaları yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, Windows kısıtlamaları güvenliği bu bölgede uygulanmaz. Güvenlik bölgesi, bu özellik tarafından sunulan ek bir güvenlik katmanı olmadan çalışır. Bu ilke ayarını devre dışı bırakırsanız, başlık ve durum çubuklarını içeren, komut dosyası tarafından başlatılan açılır pencereler ve Windows 'da bulunan olası zararlı eylemler çalıştırılamaz. Bu Internet Explorer güvenlik özelliği, bu bölgede, işlem için Betikleştirilmiş Windows güvenlik kısıtlamaları özelliği denetim ayarı tarafından dikte edildiği şekilde açık. Bu ilke ayarını yapılandırmazsanız, komut dosyası tarafından başlatılan açılır pencereler ve başlık ve durum çubuklarını içeren pencerelerin içerdiği olası zararlı eylemler çalıştırılamaz. Bu Internet Explorer güvenlik özelliği, bu bölgede, işlem için Betikleştirilmiş Windows güvenlik kısıtlamaları özelliği denetim ayarı tarafından dikte edildiği şekilde açık.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067088)  
  
  **Varsayılan**: devre dışı  
  
- **Internet Explorer güvenlik bölgeleri yalnızca makine ayarlarını kullanır**  
  Aynı bilgisayarın tüm kullanıcılarına güvenlik bölgesi bilgilerini uygular. Güvenlik bölgesi, aynı güvenlik düzeyine sahip bir Web siteleri grubudur. Bu ilkeyi etkinleştirirseniz, kullanıcının bir güvenlik bölgesinde yaptığı değişiklikler bu bilgisayarın tüm kullanıcıları için geçerlidir. Bu ilkeyi devre dışı bırakır veya yapılandırmazsanız, aynı bilgisayarın kullanıcıları kendi güvenlik bölgesi ayarlarını kurabilir. Güvenlik bölgesi ayarlarının aynı bilgisayara tek bir şekilde uygulandığından ve kullanıcıdan kullanıcıya değişmemesini sağlamak için bu ilkeyi kullanın. Ayrıca, "güvenlik bölgeleri: kullanıcıların ilke değiştirmesine izin verme" ilkesini inceleyin.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067086)  
  
  **Varsayılan**: etkin  
  
- **Internet Explorer kilitli yerel makine bölgesi Java izinleri**  
  Bu ilke ayarı, Java uygulamaları için izinleri yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, açılan kutudan Seçenekler ' i seçebilirsiniz. Özel, izin ayarlarını tek tek denetlemek için. Düşük güvenlik, uygulamaların tüm işlemleri gerçekleştirmesini sağlar. Orta düzey güvenlik, uygulamaların korumalı alanları üzerinde (programın çağrı yapamasının dışında bir alan) ve boş alan (istemci bilgisayardaki güvenli ve güvenli bir depolama alanı) ve kullanıcı denetimli dosya g/ç gibi yetenekler üzerinde çalışmasına imkan sağlar. Yüksek güvenlik, uygulamaların kendi korumalı kuruluşlarının çalışmasına olanak sağlar. Tüm uygulamaların çalıştırılmasını engellemek için Java 'Yı devre dışı bırakın. Bu ilke ayarını devre dışı bırakırsanız, Java uygulamaları çalıştırılamaz. Bu ilke ayarını yapılandırmazsanız Java uygulamaları devre dışı bırakılır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067253) 
  
  **Varsayılan**: Java 'yı devre dışı bırak 
  
- **Internet Explorer kısıtlı bölgesi, kötü amaçlı yazılımdan koruma 'Yi etkin X denetimlerine karşı çalıştırmaz**   
  Bu ilke ayarı, Internet Explorer 'ın, sayfalarda güvenli olup olmadığını denetlemek için kötü amaçlı yazılımdan koruma programlarını ActiveX denetimlerine karşı çalıştırmasını belirler. Bu ilke ayarını etkinleştirirseniz, Internet Explorer, ActiveX denetiminin bir örneğini oluşturmanın güvenli olup olmadığını görmek için kötü amaçlı yazılımdan koruma programınızı denetlemez. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer, ActiveX denetiminin bir örneğinin oluşturulması için güvenli olup olmadığını görmek üzere her zaman kötü amaçlı yazılımdan koruma programınızı denetler. Bu ilke ayarını yapılandırmazsanız, Internet Explorer, ActiveX denetiminin bir örneğinin oluşturulması için güvenli olup olmadığını görmek üzere her zaman kötü amaçlı yazılımdan koruma programınızı denetler. Kullanıcılar, Internet Explorer güvenlik ayarlarını kullanarak bu davranışı etkinleştirebilir veya devre dışı bırakabilirsiniz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067089)
  
  **Varsayılan**: devre dışı  
  
- **Internet Explorer kısıtlı bölge çalıştırma .NET Framework Authenticode ile imzalanmış bağımlı bileşenler**  
  Bu ilke ayarı, Authenticode ile imzalanmış .NET Framework bileşenlerinin Internet Explorer 'dan yürütülüp yürütülmeyeceğini yönetmenizi sağlar. Bu bileşenler bir nesne etiketiyle başvurulan yönetilen denetimleri ve bir bağlantıdan başvurulan yönetilen yürütülebilir dosyaları içerir. Bu ilke ayarını etkinleştirirseniz, Internet Explorer imzalanmış yönetilen bileşenleri yürütür. Açılır kutuda sor ' u seçerseniz, Internet Explorer kullanıcıdan imzalanmış yönetilen bileşenleri çalıştırıp yürütmeyeceğini belirlemesini ister. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer imzalanmış yönetilen bileşenleri yürütmez. Bu ilke ayarını yapılandırmazsanız, Internet Explorer imzalanmış yönetilen bileşenleri yürütmez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067169)  
  
  **Varsayılan**: devre dışı  
  
- **Internet Explorer kısıtlı bölge erişimini veri kaynaklarına erişim**  
  Bu ilke ayarı, Internet Explorer 'ın Microsoft XML ayrıştırıcısı (MSXML) veya ActiveX Data Objects (ADO) kullanarak başka bir güvenlik bölgesinden veriye erişip erişemeyeceğini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, kullanıcılar bölgedeki başka bir siteden veriye erişmek için MSXML veya ADO kullanan bölgeye bir sayfa yükleyebilir. Açılır kutuda sor ' u seçerseniz, kullanıcılar bölgedeki başka bir siteden veriye erişmek için MSXML veya ADO kullanan bölgede bir sayfanın yüklenmesine izin verip vermeyeceğinizi belirlemek üzere sorgulanır. Bu ilke ayarını devre dışı bırakırsanız, kullanıcılar bölgedeki başka bir siteden veriye erişmek için MSXML veya ADO kullanan bölgeye bir sayfa yükleyemez. Bu ilke ayarını yapılandırmazsanız kullanıcılar bölgedeki başka bir siteden veriye erişmek için MSXML veya ADO kullanan bölgeye bir sayfa yükleyemez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067161)  
  
  **Varsayılan**: devre dışı 
  
- **Internet Explorer Internet bölgesi ActiveX denetimlerinde kötü amaçlı yazılımdan koruma çalıştırmayın**  
  Bu ilke ayarı, Internet Explorer 'ın, sayfalarda güvenli olup olmadığını denetlemek için kötü amaçlı yazılımdan koruma programlarını ActiveX denetimlerine karşı çalıştırmasını belirler. Bu ilke ayarını etkinleştirirseniz, Internet Explorer, ActiveX denetiminin bir örneğini oluşturmanın güvenli olup olmadığını görmek için kötü amaçlı yazılımdan koruma programınızı denetlemez. Bu ilke ayarını devre dışı bırakırsanız, Internet Explorer, ActiveX denetiminin bir örneğinin oluşturulması için güvenli olup olmadığını görmek üzere her zaman kötü amaçlı yazılımdan koruma programınızı denetler. Bu ilke ayarını yapılandırmazsanız, Internet Explorer, ActiveX denetiminin bir örneğinin oluşturulması için güvenli olup olmadığını görmek üzere her zaman kötü amaçlı yazılımdan koruma programınızı denetler. Kullanıcılar, Internet Explorer güvenlik ayarlarını kullanarak bu davranışı etkinleştirebilir veya devre dışı bırakabilirsiniz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067162)  
  
  **Varsayılan**: devre dışı  
  
- **Internet Explorer Internet bölgesi kopyalama ve betik aracılığıyla yapıştırma**  
  Bu ilke ayarı, betiklerin belirtilen bölgede bir Pano işlemi gerçekleştirip gerçekleştiremeyeceğini (örneğin, kesme, kopyalama ve yapıştırma) yönetmenize olanak sağlar. Bu ilke ayarını etkinleştirirseniz bir betik bir Pano işlemi gerçekleştirebilir. Açılır kutuda sor ' u seçerseniz, kullanıcılar Pano işlemleri yapıp gerçekleştirmeyeceği gibi sorgulanır. Bu ilke ayarını devre dışı bırakırsanız, bir betik bir Pano işlemi gerçekleştiremez. Bu ilke ayarını yapılandırmazsanız bir betik bir Pano işlemi gerçekleştirebilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067084)  
  
  **Varsayılan**: devre dışı  
  
- **Internet Explorer etkin X Yükleyici hizmetini kullan**  
  Bu ilke ayarı, ActiveX denetimlerinin nasıl yüklendiğini belirtmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, ActiveX denetimleri yalnızca ActiveX Yükleyici hizmeti varsa ve ActiveX denetimlerinin yüklenmesine izin verecek şekilde yapılandırıldıysa yüklenir. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, Kullanıcı başına denetimler dahil olmak üzere ActiveX denetimleri standart yükleme işlemi aracılığıyla yüklenir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067163)
  
  **Varsayılan**: etkin  
  
- **Internet Explorer, bölge yükselmesinin korumasını işler**  
  Internet Explorer, açtığı her bir Web sayfasına yönelik kısıtlamalar koyar. Kısıtlamalar, Web sayfasının konumuna (Internet, Intranet, yerel makine bölgesi vb.) bağlıdır. Örneğin, yerel bilgisayardaki Web sayfaları en az güvenlik kısıtlamalarına sahiptir ve yerel makine bölgesinde olduğundan, yerel makine güvenlik bölgesine kötü amaçlı kullanıcılar için bir ana hedef atanır. Bu ilke ayarını etkinleştirirseniz, tüm işlemlerin bölge yükselmesine karşı herhangi bir bölge korunabilir. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, Internet Explorer dışındaki işlemler veya Işlem listesinde listelenenler böyle bir koruma almaz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067160)  
  
  **Varsayılan**: etkin  
  
- **Internet Explorer Internet bölgesi Imzasız ActiveX denetimlerini indir**   
  Bu ilke ayarı, kullanıcıların imzasız ActiveX denetimlerini bölgeden yükleyip yükleyemeyeceğini yönetmenizi sağlar. Bu kod, özellikle güvenilmeyen bir bölgeden geldiği zaman zararlı olabilir. Bu ilke ayarını etkinleştirirseniz, kullanıcılar imzasız denetimleri kullanıcı müdahalesi olmadan çalıştırabilir. Açılır kutuda sor ' u seçerseniz, kullanıcılardan imzasız denetimin çalışmasına izin verip vermeyeceğinizi seçmeleri istenir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcılar imzasız denetimleri çalıştıramıyorum. Bu ilke ayarını yapılandırmazsanız kullanıcılar imzasız denetimleri çalıştırmaz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067325)
  
  **Varsayılan**: devre dışı  
  
- **Internet Explorer Internet bölgesi farklı etki alanlarındaki pencereler ve çerçevelere gider**   
  Bu ilke ayarı, farklı etki alanlarındaki pencerelerin ve çerçevelerin açılmasını ve uygulama erişimini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, kullanıcılar diğer etki alanlarından Windows ve çerçeveler açabilir ve diğer etki alanlarından uygulamalara erişebilir. Açılır kutuda sor ' u seçerseniz, kullanıcılar Windows ve çerçevelerin diğer etki alanlarından uygulamalara erişmesine izin verilip verilmeyeceğini belirtir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcılar farklı etki alanlarından uygulamalara erişmek için Windows ve çerçeveler açamaz. Bu ilke ayarını yapılandırmazsanız, kullanıcılar diğer etki alanlarından Windows ve çerçeveler açabilir ve diğer etki alanlarından uygulamalara erişebilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067083)  
  
  **Varsayılan**: devre dışı  

- **Komut dosyası aracılığıyla durum çubuğuna Internet Explorer Internet bölgesi güncelleştirmeleri**  
  Bu ilke ayarı, bir betiğin bölge içindeki durum çubuğunu güncelleştirip güncelleştiremeyeceğini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz betikler durum çubuğunu güncelleştirebilir. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, betiğin durum çubuğunu güncelleştirmesine izin verilmez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067087)  
  
  **Varsayılan**: devre dışı  
 
- **Internet Explorer kısıtlı bölgesi, dosyaları sunucuya yüklerken yerel yolu içerir**  
  Bu ilke ayarı, Kullanıcı HTML formu aracılığıyla bir dosya yüklerken yerel yol bilgilerinin gönderilip gönderilmediğini denetler. Yerel yol bilgileri gönderildiyse, bazı bilgiler istenmeden sunucu tarafından görüntülenebilir. Örneğin, kullanıcının masaüstünden gönderilen dosyalar yolun bir parçası olarak Kullanıcı adını içerebilir. Bu ilke ayarını etkinleştirirseniz, Kullanıcı HTML formu aracılığıyla bir dosya yüklerken yol bilgileri gönderilir. Bu ilke ayarını devre dışı bırakırsanız, Kullanıcı HTML formu aracılığıyla bir dosya yüklerken yol bilgileri kaldırılır. Bu ilke ayarını yapılandırmazsanız kullanıcı HTML formu aracılığıyla bir dosya yüklerken yol bilgilerinin gönderilip gönderilmeyeceğini seçebilir. Varsayılan olarak, yol bilgileri gönderilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067085)  
  
  **Varsayılan**: devre dışı  
  
- **Internet Explorer işlemi dosya indirmeyi kısıtlar**   
  Bu ilke ayarı, Web tarayıcısı denetimini barındıran uygulamaların, Kullanıcı tarafından başlatılmayan dosya indirmelerinin otomatik olarak sorulmasını engellemesini sağlar. Bu ilke ayarını etkinleştirirseniz, Web tarayıcısı denetimi, tüm işlemlerde Kullanıcı tarafından başlatılmayan dosya indirmelerinin otomatik olarak sorulmasını engeller. Bu ilke ayarını devre dışı bırakırsanız, Web tarayıcısı denetimi, tüm işlemlerde Kullanıcı tarafından başlatılmayan dosya indirmelerinin otomatik olarak sorulmasını engellemez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067164)  
  
  **Varsayılan**: etkin  
  
- **Internet Explorer kısıtlı bölgesi yalnızca onaylanan etki alanlarının Active X denetimlerini kullanmasına izin verir**   
  Bu ilke ayarı, kullanıcıdan ActiveX denetimini yükleyen web sitesi dışındaki web sitelerinde ActiveX denetimlerinin çalışmasına izin istenip istenmeyeceğini denetler. Bu ilke ayarını etkinleştirirseniz, bu bölgedeki Web sitelerinden ActiveX denetimleri çalıştırılmadan önce kullanıcıya sorulur. Kullanıcı, denetimin geçerli siteden veya tüm sitelerden çalışmasına izin vermeyi seçebilir. Bu ilke ayarını devre dışı bırakırsanız, Kullanıcı site başına ActiveX istemi 'ni görmez ve ActiveX denetimleri bu bölgedeki tüm sitelerden çalıştırılabilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067233)  
  
  **Varsayılan**: etkin  
  
- **Internet Explorer kısıtlı bölge başlatma ve betik etkin X denetimleri güvenli olarak işaretlenmemiş**  
  Bu ilke ayarı, güvenli olarak işaretlenmemiş ActiveX denetimlerini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, ActiveX denetimleri çalışır, parametrelerle yüklenir ve güvenilir olmayan veriler veya betikler için nesne güvenliğini ayarlamadan komut dosyası. Bu ayar, güvenli ve yönetilen bölgeler dışında önerilmez. Bu ayar, komut dosyası oluşturma seçeneği için güvenli olarak işaretlenmiş betik ActiveX denetimlerini yoksayarak, hem güvensiz hem de güvenli denetimlerin başlatılmasına ve betiklere neden olur. Bu ilke ayarını etkinleştirir ve açılan kutuda sor ' u seçerseniz, kullanıcılara, denetimin parametrelerle veya betiklerle yüklenmesine izin verip vermeyecekleri sorulur. Bu ilke ayarını devre dışı bırakırsanız, güvenli hale getirilemeyen ActiveX denetimleri parametrelerle veya betiklerle yüklenmez. Bu ilke ayarını yapılandırmazsanız, güvenli hale getirilemeyen ActiveX denetimleri parametrelerle veya betiklerle yüklenmez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067097)  
  
  **Varsayılan**: devre dışı  
  
- **Internet Explorer kullanıcıları ilkeleri değiştirme**  
  Kullanıcıların güvenlik bölgesi ayarlarını değiştirmesini engeller. Güvenlik bölgesi, aynı güvenlik düzeyine sahip bir Web siteleri grubudur. Bu ilkeyi etkinleştirirseniz Internet Seçenekleri iletişim kutusundaki Güvenlik sekmesinde Özel düzey düğmesi ve güvenlik düzeyi kaydırıcısı devre dışı bırakılır. Bu ilkeyi devre dışı bırakır veya yapılandırmazsanız, kullanıcılar güvenlik bölgelerinin ayarlarını değiştirebilir. Bu ilke, kullanıcıların yönetici tarafından belirlenen güvenlik bölgesi ayarlarını değiştirmesini engeller. Note: Denetim Masası 'nda Internet Explorer 'dan Güvenlik sekmesini kaldıran "Güvenlik sayfasını devre dışı bırak" ilkesi (Kullanıcı Yapılandırması \ Yönetim Şablonları \ Windows bileşenleri \ Denetim Masası) Bu ilkenin üzerinde. Etkinleştirilirse, bu ilke yok sayılır. Ayrıca bkz. "güvenlik bölgeleri: yalnızca makine ayarlarını kullanma" ilkesi.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067155)  
    
  **Varsayılan**: devre dışı  
  
- **Internet Explorer kısıtlı bölge korumalı modu**  
  Bu ilke ayarı, korumalı modu açmanıza olanak tanır. Korumalı mod, Internet Explorer 'ın kayıt defterine ve dosya sistemine yazabilecek konumları azaltarak Internet Explorer 'ın açıktan yararlanan güvenlik açıklarına karşı korunmasına yardımcı olur. Bu ilke ayarını etkinleştirirseniz, korumalı mod açıktır. Kullanıcı korumalı modu kapatamaz. Bu ilke ayarını devre dışı bırakırsanız, korumalı mod kapalıdır. Kullanıcı korumalı modu açamaz. Bu ilke ayarını yapılandırmazsanız kullanıcı korumalı modu etkinleştirebilir veya devre dışı bırakabilirsiniz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067080)  
  
  **Varsayılan**: etkinleştir  
  
- **Internet Explorer Internet bölgesi Kullanıcı verileri kalıcılığı**  
  Bu ilke ayarı, bilgilerin tarayıcının geçmişinde, Sık Kullanılanlar 'da, bir XML deposunda veya doğrudan diske kaydedilen bir Web sayfasından korunmasını yönetmenizi sağlar. Bir Kullanıcı kalıcı bir sayfaya döndüğünde, bu ilke ayarı uygun şekilde yapılandırıldıysa sayfanın durumu geri yüklenebilir. Bu ilke ayarını etkinleştirirseniz, kullanıcılar tarayıcı geçmişinde, Sık Kullanılanlar 'da, bir XML deposunda veya doğrudan diske kaydedilmiş bir Web sayfasında bilgileri koruyabilir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcılar tarayıcı geçmişinde, Sık Kullanılanlar 'da, bir XML deposunda veya doğrudan diske kaydedilmiş bir Web sayfasında bilgileri koruyamaz. Bu ilke ayarını yapılandırmazsanız, kullanıcılar tarayıcı geçmişinde, Sık Kullanılanlar 'da, bir XML deposunda veya doğrudan diske kaydedilmiş bir Web sayfası içinde bilgileri koruyabilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067156)  
  
  **Varsayılan**: devre dışı  
  
- **Web tarayıcısı denetimlerinin Internet Explorer Internet bölgesi komut dosyası oluşturma**  
 
  Bu ilke ayarı, bir sayfanın katıştırılmış WebBrowser denetimlerini betik aracılığıyla denetleyebilir olup olmayacağını belirler. Bu ilke ayarını etkinleştirirseniz, WebBrowser denetimine betik erişimine izin verilir. Bu ilke ayarını devre dışı bırakırsanız, WebBrowser denetimine betik erişimine izin verilmez. Bu ilke ayarını yapılandırmazsanız kullanıcı WebBrowser denetimine betik erişimini etkinleştirebilir veya devre dışı bırakabilir. Varsayılan olarak, WebBrowser denetimine betik erişimine yalnızca yerel makine ve Intranet bölgelerinde izin verilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067157)  
  
  **Varsayılan**: devre dışı  
  
- **Internet Explorer kısıtlı bölge Kullanıcı verileri kalıcılığı**  
  Bu ilke ayarı, bilgilerin tarayıcının geçmişinde, Sık Kullanılanlar 'da, bir XML deposunda veya doğrudan diske kaydedilen bir Web sayfasından korunmasını yönetmenizi sağlar. Bir Kullanıcı kalıcı bir sayfaya döndüğünde, bu ilke ayarı uygun şekilde yapılandırıldıysa sayfanın durumu geri yüklenebilir. Bu ilke ayarını etkinleştirirseniz, kullanıcılar tarayıcı geçmişinde, Sık Kullanılanlar 'da, bir XML deposunda veya doğrudan diske kaydedilmiş bir Web sayfasında bilgileri koruyabilir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcılar tarayıcı geçmişinde, Sık Kullanılanlar 'da, bir XML deposunda veya doğrudan diske kaydedilmiş bir Web sayfasında bilgileri koruyamaz. Bu ilke ayarını yapılandırmazsanız kullanıcılar tarayıcı geçmişinde, Sık Kullanılanlar 'da, bir XML deposunda veya doğrudan diske kaydedilmiş bir Web sayfasında bilgileri koruyamaz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067081)  
  
  **Varsayılan**: devre dışı  
  
- **Internet Explorer kilitli intranet bölgesi Java izinleri**  
  Bu ilke ayarı, Java uygulamaları için izinleri yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, açılan kutudan Seçenekler ' i seçebilirsiniz. Özel, izin ayarlarını tek tek denetlemek için. Düşük güvenlik, uygulamaların tüm işlemleri gerçekleştirmesini sağlar. Orta düzey güvenlik, uygulamaların korumalı alanları üzerinde (programın çağrı yapamasının dışında bir alan) ve boş alan (istemci bilgisayardaki güvenli ve güvenli bir depolama alanı) ve kullanıcı denetimli dosya g/ç gibi yetenekler üzerinde çalışmasına imkan sağlar. Yüksek güvenlik, uygulamaların kendi korumalı kuruluşlarının çalışmasına olanak sağlar. Tüm uygulamaların çalıştırılmasını engellemek için Java 'Yı devre dışı bırakın. Bu ilke ayarını devre dışı bırakırsanız, Java uygulamaları çalıştırılamaz. Bu ilke ayarını yapılandırmazsanız Java uygulamaları devre dışı bırakılır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067082)  
  
  **Varsayılan**: Java 'yı devre dışı bırak  
  
- **Internet Explorer Gelişmiş Korumalı mod**  
  Gelişmiş Korumalı mod, Windows 'un 64 bit sürümlerinde 64 bitlik süreçler kullanarak kötü amaçlı Web sitelerine karşı ek koruma sağlar. En az Windows 8 çalıştıran bilgisayarlarda, Gelişmiş Korumalı mod, Internet Explorer 'ın kayıt defterinden ve dosya sisteminde okuyamadığı konumları da sınırlar. Bu ilke ayarını etkinleştirirseniz, Gelişmiş Korumalı mod açıktır. Korumalı mod etkin olan herhangi bir bölge, Gelişmiş Korumalı mod kullanır. Kullanıcılar Gelişmiş korumalı modu devre dışı bırakamayacak. Bu ilke ayarını devre dışı bırakırsanız, Gelişmiş Korumalı mod kapalıdır. Korumalı mod özellikli herhangi bir bölge, Windows Vista için Internet Explorer 7 ' de sunulan korumalı mod sürümünü kullanır. Bu ilkeyi yapılandırmazsanız kullanıcılar, Internet Seçenekleri iletişim kutusunun Gelişmiş sekmesinde Gelişmiş korumalı modu açabilir veya kapatabilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067158)  
  
  **Varsayılan**: etkin  
  
- **Internet Explorer akıllı ekran uyarılarını atla**  
  Bu ilke ayarı, kullanıcının SmartScreen filtresinden gelen uyarıları atlayıp atlayamayacağını belirler. SmartScreen Filtresi, Internet Explorer kullanıcılarının Internet 'ten yaygın olarak indirmediğini çalıştıran yürütülebilir dosyalar hakkında kullanıcıyı uyarır. Bu ilke ayarını etkinleştirirseniz SmartScreen Filtresi uyarıları kullanıcıyı engeller. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız kullanıcı SmartScreen Filtresi uyarılarını atlayabilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067159)  
  
  **Varsayılan**: devre dışı  
  
- **Internet Explorer kısıtlı bölge meta yenilemesi**  
  Bu ilke ayarı, Web sayfasının yazarı tarayıcıları başka bir Web sayfasına yönlendirmek için meta yenileme ayarı (etiket) kullanıyorsa, kullanıcının tarayıcısının başka bir Web sayfasına yönlendirilip yönlendirilmeyeceğini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, etkin Meta Yenileme ayarı içeren bir sayfayı yükleyen bir kullanıcının tarayıcısı başka bir Web sayfasına yönlendirilebilir. Bu ilke ayarını devre dışı bırakırsanız, etkin bir meta yenileme ayarı içeren bir sayfayı yükleyen kullanıcının tarayıcısı başka bir Web sayfasına yönlendirilemez. Bu ilke ayarını yapılandırmazsanız, etkin Meta Yenileme ayarı içeren bir sayfayı yükleyen bir kullanıcının tarayıcısı başka bir Web sayfasına yönlendirilemez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067154)  
  
  **Varsayılan**: devre dışı  
  
## <a name="local-policies-security-options"></a>Yerel Ilkeler güvenlik seçenekleri
Daha fazla bilgi için Windows belgelerindeki [Ilke CSP-LocalPoliciesSecurityOptions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions) bölümüne bakın. 

- **Adlandırılmış kanallara ve Paylaşımlara anonim erişimi kısıtla**  
  Bu güvenlik ayarı etkinleştirildiğinde paylaşımlar ve kanallar için anonim erişimi, anonim olarak erişilebilen, anonim (2) paylaşımlara erişilebilen adlandırılmış kanallarla kısıtlar.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067212)  
  
  **Varsayılan**: Evet  
  
- **NTLM SSP tabanlı sunucular için en düşük oturum güvenliği**  
  Bu güvenlik ayarı, bir sunucunun 128 bitlik şifreleme ve/veya NTLMv2 oturum güvenliği için anlaşma sağlamasına izin verir. Bu değerler, LAN Manager kimlik doğrulama düzeyi güvenlik ayarı değerine bağımlıdır. Seçenekler şunlardır: NTLMv2 oturum güvenliği gerektir: ileti bütünlüğü anlaşılırsa bağlantı başarısız olur. 128 bit şifrelemeyi gerektir. Güçlü şifreleme (128 bit) anlaşılmazsa bağlantı başarısız olur.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067246) 
  
  **Varsayılan**: NTLM V2 ve 128 bit şifrelemeyi gerektir  
  
- **Ekran koruyucusu etkinleşene kadar kilit ekranının işlem yapılmayan dakika sayısı**  
  Windows, bir oturumun etkin olmamasını fark eder ve etkin olmama süresi etkin olmama sınırını aşarsa, ekran koruyucusu çalışarak oturumu kilitler.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067210)  
  
  **Varsayılan**: 15
  
- **İstemcinin iletişimleri her zaman dijital olarak Imzalamasını gerektir** Bu güvenlik ayarı, etki alanı üyesi tarafından başlatılan tüm güvenli kanal trafiğinin imzalanıp imzalanmayacağını veya şifrelenmeyeceğini belirler. Bilgisayar bir etki alanına katıldığında bir bilgisayar hesabı oluşturulur. Bundan sonra, sistem başlatıldığında, etki alanı denetleyicisi için etki alanı denetleyicisiyle güvenli bir kanal oluşturmak üzere bilgisayar hesabı parolasını kullanır. Bu güvenli kanal, kimlik doğrulaması, LSA SID/Ad arama ve daha fazlası gibi işlemleri gerçekleştirmek için kullanılır. Bu ayar, etki alanı üyesi tarafından başlatılan tüm güvenli kanal trafiğinin en düşük güvenlik gereksinimlerini karşılayıp karşılamadığını belirler. Özellikle, etki alanı üyesi tarafından başlatılan tüm güvenli kanal trafiğinin imzalı veya şifrelenmiş olması gerekip gerekmediğini belirler. Bu ilke etkinleştirilirse, tüm güvenli kanal trafiği imzalanmadan veya şifrelenmediği takdirde güvenli kanal kurulmaz. Bu ilke devre dışı bırakılırsa, tüm güvenli kanal trafiğinin şifrelenmesi ve imzalanması, etki alanı denetleyicisi ile görüşülür ve bu durumda, imzalama ve şifreleme düzeyi, etki alanı denetleyicisinin sürümüne ve aşağıdaki iki ayarlara bağlıdır ilkeler: etki alanı üyesi: güvenli kanal verilerini (mümkünse) dijital olarak şifrele etki alanı üyesi: güvenli kanal verilerini dijital olarak imzala (mümkün olduğunda).  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067187) 
  
  **Varsayılan**: Evet
  
- **Kimlik doğrulama düzeyi**  
  Bu güvenlik ayarı, ağ oturum açmaları için hangi sınama/yanıt kimlik doğrulama protokolünün kullanıldığını belirler. Bu seçim, istemciler tarafından kullanılan kimlik doğrulama protokolünün düzeyini, üzerinde anlaşılan oturum güvenliği düzeyini ve sunucular tarafından kabul edilen kimlik doğrulama düzeyini şu şekilde etkiler:  
  - *LM ve NTLM yanıtları gönderme* -İstemciler LM ve NTLM kimlik doğrulaması kullanır ve hiçbir şekilde NTLMv2 oturum güvenliği kullanmaz; etki alanı denetleyicileri LM, NTLM ve NTLMv2 kimlik doğrulamasını kabul eder. 
  - *Anlaşılırsa LM ve NTLM-NTLMv2 gönder* -İstemciler LM ve NTLM kimlik doğrulaması kullanır ve sunucu destekliyorsa NTLMv2 oturum güvenliği kullanır; etki alanı denetleyicileri LM, NTLM ve NTLMv2 kimlik doğrulamasını kabul eder. 
  - *Yalnızca NTLM yanıtı gönder* -ISTEMCILER yalnızca NTLM kimlik doğrulaması kullanır ve sunucu destekliyorsa NTLMv2 oturum güvenliği kullanır; etki alanı denetleyicileri LM, NTLM ve NTLMv2 kimlik doğrulamasını kabul eder. 
  - *Yalnızca NTLMv2 yanıtı gönder* -Istemciler yalnızca NTLMv2 kimlik doğrulaması kullanır ve sunucu destekliyorsa NTLMv2 oturum güvenliği kullanır; etki alanı denetleyicileri LM, NTLM ve NTLMv2 kimlik doğrulamasını kabul eder. 
  - *Yalnızca NTLMv2 yanıtı gönder. LM 'yi reddetme* -istemciler yalnızca NTLMv2 kimlik doğrulaması kullanır ve sunucu destekliyorsa NTLMv2 oturum güvenliği kullanır; etki alanı denetleyicileri LM 'yi reddeder (yalnızca NTLM ve NTLMv2 kimlik doğrulamasını kabul et). 
  - *Yalnızca NTLMv2 yanıtı gönder. LM ve NTLM reddetme* -istemciler yalnızca NTLMv2 kimlik doğrulaması kullanır ve sunucu destekliyorsa NTLMv2 oturum güvenliği kullanır; etki alanı denetleyicileri LM ve NTLM 'yi reddeder (yalnızca NTLMv2 kimlik doğrulamasını kabul eder).  

  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067189)   
    
  **Varsayılan**: yalnızca NTLMv2 yanıtı gönder. LM ve NTLM 'yi reddetme
  
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
  - *Sormadan Yükselt* -ayrıcalıklı hesapların, izin veya kimlik bilgileri gerekmeden yükseltme gerektiren bir işlem gerçekleştirmesine izin verir. Note: Bu seçeneği yalnızca en kısıtlanmış ortamlarda kullanın. 
  - *Güvenli masaüstünde kimlik bilgileri iste* -bir işlem ayrıcalık yükseltmesi gerektirdiğinde, kullanıcının güvenli masaüstünde ayrıcalıklı bir Kullanıcı adı ve parola girmesi istenir. Kullanıcı geçerli kimlik bilgileri girerse, işlem kullanıcının kullanılabilir en yüksek ayrıcalığıyla devam eder. 
  - *Güvenli masaüstünde onay iste* -bir işlem ayrıcalık yükseltmesi gerektirdiğinde, kullanıcının güvenli masaüstünde izin ver veya Reddet ' i seçmesi istenir. Kullanıcı Izin ver ' i seçerse, işlem kullanıcının kullanılabilir en yüksek ayrıcalığıyla devam eder. 
  - *Kimlik bilgileri iste* -bir işlem ayrıcalık yükseltmesi gerektirdiğinde kullanıcıdan bir Yönetici Kullanıcı adı ve parola girmesi istenir. Kullanıcı geçerli kimlik bilgileri girerse, işlem ilgili ayrıcalıkla devam eder. 
  - *Onay iste* -bir işlem ayrıcalık yükseltmesi gerektirdiğinde, kullanıcıdan izin ver veya Reddet ' i seçmesi istenir. Kullanıcı Izin ver ' i seçerse, işlem kullanıcının kullanılabilir en yüksek ayrıcalığıyla devam eder.  
  - *Windows dışı ikili dosyalar için Izin iste* -Microsoft dışı bir uygulama için bir işlem ayrıcalık yükseltmesi gerektirdiğinde, kullanıcıdan güvenli masaüstünde izin ver veya Reddet ' i seçmesi istenir. Kullanıcı Izin ver ' i seçerse, işlem kullanıcının kullanılabilir en yüksek ayrıcalığıyla devam eder. 
  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067215)   
  
  **Varsayılan**: güvenli masaüstünde onay iste
  
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
    
  **Varsayılan**: kilit iş istasyonu
  
- **SAM hesaplarının ve paylaşımlarının anonim numaralandırılmasına engel**  
  Bu güvenlik ayarı, SAM hesaplarının ve paylaşımlarının anonim numaralandırılmasına izin verilip verilmeyeceğini belirler. Windows, anonim kullanıcıların etki alanı hesaplarının ve ağ paylaşımlarının adlarını numaralandırma gibi belirli etkinlikleri gerçekleştirmesine olanak sağlar. Bu, örneğin, bir yönetici, güvenilen bir etki alanındaki kullanıcılara, karşılıklı güven ilişkisi olmayan kullanıcılar için erişim vermek istediğinde kullanışlıdır. SAM hesaplarının ve paylaşımlarının anonim numaralandırmasına izin vermek istemiyorsanız, bu ilkeyi *Evet*olarak ayarlayın.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067191)  
  
  **Varsayılan**: Evet
  
- **Boş parolayla uzaktan oturum açmayı engelle**  
  Bu güvenlik ayarı, parola korumalı olmayan yerel hesapların fiziksel bilgisayar konsolu dışındaki konumlardan oturum açmak için kullanılıp kullanılamayacağını belirler. Etkinleştirilirse, parola korumalı olan yerel hesapların oturum açması için bilgisayarın klavyesini kullanması gerekir. 

  *Uyarı*: fiziksel olarak güvenli konumlarda olmayan bilgisayarlar her zaman tüm yerel kullanıcı hesapları için güçlü parola ilkeleri uygulamalıdır. Aksi takdirde, bilgisayara fiziksel erişimi olan herkes, parolası olmayan bir kullanıcı hesabı kullanarak oturum açabilir. Bu özellikle taşınabilir bilgisayarlar için önemlidir. 

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
  - *Yapılandırılmadı* -yönetici onay modu ve ılgılı tüm UAC ilkesi ayarları devre dışı bırakıldı. Note: Bu ilke ayarı devre dışıysa, Güvenlik Merkezi, işletim sisteminin genel güvenliğinin azaldığını size bildirir. 
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
  
  **Varsayılan**: *O:bag: Hatalı: (A;; RC;;; BA)*

- **Yönetici onay modunu kullan**  
  Bu ilke ayarı, yerleşik yönetici hesabı için yönetici onay modunun davranışını denetler. Seçenekler şunlardır: 
  - *Evet* -yerleşik yönetici hesabı yönetici onay modunu kullanır. Varsayılan olarak, ayrıcalık yükseltme gerektiren tüm işlemler kullanıcıdan işlemi onaylamasını ister. 
  - *Yapılandırılmadı* -yerleşik yönetici hesabı tüm uygulamaları tam yönetici ayrıcalığıyla çalıştırır. 

  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067186)  

  **Varsayılan**: Evet
  
- **Güvenli konumlar için UI erişim uygulamalarına izin ver**  
  Bu ilke ayarı, Kullanıcı arabirimi erişilebilirliği (UIAccess veya UıA) programlarının standart bir kullanıcı tarafından kullanılan yükseltme istemleri için güvenli masaüstünü otomatik olarak devre dışı bırakıp bırakamayacağını denetler. 
  - Windows Uzaktan Yardım dahil olmak üzere *Evet* -UIA programları, yükseltme istemleri için güvenli masaüstünü otomatik olarak devre dışı bırakır. "Kullanıcı hesabı denetimi: Yükseltme isterken güvenli masaüstüne geç" ilke ayarını devre dışı bırakmazsanız, istemler güvenli masaüstü yerine etkileşimli kullanıcının masaüstünde görünür. 
  - *Yapılandırılmadı*:-güvenli masaüstü yalnızca etkileşimli masaüstü kullanıcısı tarafından veya "Kullanıcı hesabı denetimi: Yükseltme isterken güvenli masaüstüne geç" ilke ayarı devre dışı bırakılarak devre dışı bırakılabilir.  

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

  **Varsayılan**: etkin
  
- **SMB v1 istemci sürücüsü yapılandırma Başlat**  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067214) 
 
  **Varsayılan**: devre dışı sürücü
  
- **SMB v1 sunucusu**  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067190)  

  **Varsayılan**: devre dışı
  
- **Özet kimlik doğrulaması**  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067193) 
 
  **Varsayılan**: devre dışı
  
- **Yapılandırılmış özel durum işleme üzerine yazma koruması**  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067217)  

  **Varsayılan**: etkin
  
## <a name="mss-legacy"></a>Bulunan eski  
Daha fazla bilgi için Windows belgelerindeki [Ilke CSP-MSSLegacy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-msslegacy) bölümüne bakın.  

- **Ağ IP kaynağı yönlendirme koruma düzeyi**  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067220)  
  
  **Varsayılan**: en yüksek koruma  
  
- **Ağ, WINS sunucuları hariç NetBIOS ad yayın isteklerini yoksay**  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067218)  
 
  **Varsayılan**: etkin
  
- **Ağ IPv6 kaynak yönlendirme koruma düzeyi**  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067216)  

  **Varsayılan**: en yüksek koruma

- **Ağ ıCMP yeniden yönlendirmeleri geçersiz kılma OSPF oluşturulan**  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067326)  

  **Varsayılan**: devre dışı
  
## <a name="power"></a>Açılma  
Daha fazla bilgi için Windows belgelerindeki [Ilke CSP-güç](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power) bölümüne bakın.  

- **Prize takılıyken uyanma durumunda parola iste**  
  Bu ilke ayarı, sistem uykudan devam ettiğinde kullanıcıdan bir parola istenip istenmeyeceğine belirtir. Bu ilke ayarını etkinleştirir veya yapılandırmazsanız, sistem uykudan devam ettiğinde kullanıcıdan bir parola istenir. Bu ilke ayarını devre dışı bırakırsanız, sistem uykudan devam ettiğinde kullanıcıdan parola istenmez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067221)  
  
  **Varsayılan**: etkin
  
- **Pille çalışırken bekleme durumları**  
  Bu ilke ayarı, Windows 'un bilgisayarı uyku durumuna geçirirken bekleme durumlarını kullanıp kullanmeyeceğini yönetir. Bu ilke ayarını etkinleştirir veya yapılandırmazsanız, Windows bilgisayarı uyku durumuna geçirmek için bekleme durumlarını kullanır. Bu ilke ayarını devre dışı bırakırsanız, bekleme durumlarına (S1-S3) izin verilmez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067195)  
  
  **Varsayılan**: devre dışı
  
- **Prize takılıyken uyurken bekleme durumları**  
  Bu ilke ayarı, Windows 'un bilgisayarı uyku durumuna geçirirken bekleme durumlarını kullanıp kullanmeyeceğini yönetir. Bu ilke ayarını etkinleştirir veya yapılandırmazsanız, Windows bilgisayarı uyku durumuna geçirmek için bekleme durumlarını kullanır. Bu ilke ayarını devre dışı bırakırsanız, bekleme durumlarına (S1-S3) izin verilmez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067196)  
  
  **Varsayılan**: devre dışı
  
- **Pille çalışırken Uyandırma için parola gerektir**  
  Bu ilke ayarı, sistem uykudan devam ettiğinde kullanıcıdan bir parola istenip istenmeyeceğine belirtir. Bu ilke ayarını etkinleştirir veya yapılandırmazsanız, sistem uykudan devam ettiğinde kullanıcıdan bir parola istenir. Bu ilke ayarını devre dışı bırakırsanız, sistem uykudan devam ettiğinde kullanıcıdan parola istenmez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067322)  
  
  **Varsayılan**: etkin
::: zone-end
::: zone pivot="mdm-may-2019"

## <a name="remote-assistance"></a>Uzaktan Yardım   
Daha fazla bilgi için Windows belgelerindeki [Ilke CSP-RemoteAssistance](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remoteassistance#remoteassistance-solicitedremoteassistance) bölümüne bakın.  

- **Uzaktan Yardım istenen**  
  Bu ilke ayarı, bu bilgisayarda uzaktan yardım ISTEME veya devre dışı bırakmanıza olanak tanır. 
  - *Bu ilke ayarını etkinleştirirseniz*, bu bilgisayardaki kullanıcılar e-posta veya dosya aktarımını kullanarak birinden yardım isteyebilir. Ayrıca, kullanıcılar bu bilgisayara bağlantılara izin vermek için anlık mesajlaşma programlarını kullanabilir ve ek Uzaktan Yardım ayarlarını yapılandırabilirsiniz. 
  - *Bu ilke ayarını devre dışı*bırakırsanız, bu bilgisayardaki kullanıcılar, birinden yardım istemek için e-posta veya dosya aktarımını kullanamaz. Ayrıca, kullanıcılar bu bilgisayara bağlantılara izin vermek için anlık mesajlaşma programlarını kullanamaz. 
  - *Bu ilke ayarını yapılandırmazsanız*, kullanıcılar Denetim Masası 'Ndaki Sistem Özellikleri ' nde, Istenen Uzaktan Yardım ' ı etkinleştirebilir veya devre dışı bırakabilirsiniz. Kullanıcılar, Uzaktan Yardım ayarlarını da yapılandırabilir. 

  Bu ilke ayarını etkinleştirirseniz yardımcıların uzaktan yardım sağlamasına izin vermenin iki yolu vardır: "yardımcılar yalnızca bilgisayarı görüntülemesine izin ver" veya "yardımcılar bilgisayarı uzaktan denetlemesine izin ver". "En fazla bilet süresi" ilke ayarı, e-posta veya dosya aktarımı kullanılarak oluşturulan bir Uzaktan Yardım davetinin açık kalabileceği zaman miktarı için bir sınır ayarlar. "E-posta davetleri göndermek için yöntemi seçin" ayarı, uzaktan yardım davetleri göndermek için kullanılacak e-posta standardını belirtir. E-posta programınıza bağlı olarak, mailto standardını (davet alıcısı bir Internet bağlantısı üzerinden bağlanır) ya da SMAPI (basit MAPI) standardını (davet e-posta iletinize iliştirilir) kullanabilirsiniz. Bu ilke ayarı, desteklenen tek yöntem olduğundan, Windows Vista 'da kullanılamaz. Bu ilke ayarını etkinleştirirseniz, uzaktan yardım iletişimine izin vermek için uygun güvenlik duvarı özel durumlarını da etkinleştirmeniz gerekir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067198)

  **Varsayılan**: Uzaktan Yardım 'ı devre dışı bırak

  *Uzaktan Yardımı etkinleştirmek*için ayarlandığında, aşağıdaki ek ayarları yapılandırın:  
  - **Uzaktan Yardım istenen izin**  
    **Varsayılan**: görünüm  

  - **En uzun bilet süresi değeri**  
    **Varsayılan**: *Yapılandırılmadı*  

  - **Maksimum bilet süresi dönemi**  
    **Varsayılan**: dakika    

  - **E-posta davet yöntemi**  
    **Varsayılan**: basit MAPI
::: zone-end
::: zone pivot="mdm-preview,mdm-may-2019"
  
## <a name="remote-desktop-services"></a>Uzak Masaüstü Hizmetleri  
Daha fazla bilgi için Windows belgelerindeki [Ilke CSP-RemoteDesktopServices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remotedesktopservices) bölümüne bakın.  

- **Parola kaydetmeyi engelle**  
  Uzak Masaüstü Bağlantısı 'tan bu bilgisayara parolaların kaydedilip kaydedilmediğini denetler. Bu ayarı etkinleştirirseniz Uzak Masaüstü Bağlantısı ' de parola kaydetme onay kutusu devre dışıdır ve kullanıcılar parolaları kaydedemezler. Kullanıcı Uzak Masaüstü Bağlantısı kullanarak bir RDP dosyası açtığında ve ayarlarını kaydettiğinde, RDP dosyasında daha önce varolan tüm parolalar silinir. Bu ayarı devre dışı bırakırsanız veya yapılandırılmamışsa, Kullanıcı Uzak Masaüstü Bağlantısı kullanarak parolaları kaydedebilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067301)  
  
   **Varsayılan**: etkin
  
- **Güvenli RPC iletişimi**  
  Bir Uzak Masaüstü Oturumu Ana Bilgisayarı sunucusunun tüm istemcilerle güvenli RPC iletişimi gerektirip gerektirmediğini veya güvenli olmayan iletişime izin verip etmeyeceğini belirtir. Yalnızca kimliği doğrulanmış ve şifreli isteklere izin vererek istemcilerle RPC iletişiminin güvenliğini güçlendirmek için bu ayarı kullanabilirsiniz. Durum etkin olarak ayarlandıysa Uzak Masaüstü Hizmetleri, güvenli istekleri destekleyen RPC istemcilerinden gelen istekleri kabul eder ve güvenilmeyen istemcilerle güvenli olmayan iletişime izin vermez. Durum devre dışı olarak ayarlandıysa Uzak Masaüstü Hizmetleri tüm RPC trafiği için her zaman güvenlik ister. Ancak, isteğe yanıt vermeyen RPC istemcilerinde güvenli olmayan iletişime izin verilir. Durum Yapılandırılmadı olarak ayarlandıysa, güvenli olmayan iletişime izin verilir. Note: RPC arabirimi Uzak Masaüstü Hizmetleri yönetmek ve yapılandırmak için kullanılır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067248)  
  
  **Varsayılan**: etkin
  
- **Sürücü yeniden yönlendirmeyi engelle**  
  Bu ilke ayarı, Uzak Masaüstü Hizmetleri oturumunda istemci sürücülerinin eşlenmesinin engellenip engellenmeyeceğini belirtir (sürücü yeniden yönlendirme). Varsayılan olarak, bir RD Oturumu Ana Bilgisayarı sunucusu bağlantı kurulduğunda istemci sürücüleri otomatik olarak eşler. Eşlenen sürücüler, *\<computername >* üzerinde *\<SürücüHarfi >* Dosya Gezgini veya bilgisayardaki oturum klasörü ağacında görüntülenir. Bu davranışı geçersiz kılmak için bu ilke ayarını kullanabilirsiniz. Bu ilke ayarını etkinleştirirseniz, Uzak Masaüstü Hizmetleri oturumlarında istemci sürücü yönlendirmesine izin verilmez ve Windows Server 2003, Windows 8 ve Windows XP çalıştıran bilgisayarlarda Pano dosya kopyası yeniden yönlendirmesine izin verilmez. Bu ilke ayarını devre dışı bırakırsanız, istemci sürücü yeniden yönlendirmesine her zaman izin verilir. Ayrıca, pano yeniden yönlendirmesine izin veriliyorsa Pano dosya kopyalama yönlendirmesine her zaman izin verilir. Bu ilke ayarını yapılandırmazsanız, istemci sürücü yeniden yönlendirmesi ve Pano dosya kopyalama yönlendirmesi grup ilkesi düzeyinde belirtilmez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067197)  
  
  **Varsayılan**: etkin
  
- **Bağlantı kurulduğunda parola iste**  
  Bu ilke ayarı, Uzak Masaüstü Hizmetleri bağlantı kurulduğunda istemciden her zaman bir parola isteyip istemediğinizi belirtir. Bu ayarı, Uzak Masaüstü Bağlantısı istemcisinde zaten parola sağladıklarında bile Uzak Masaüstü Hizmetleri oturum açan kullanıcılar için bir parola istemi zorlamak üzere kullanabilirsiniz. Varsayılan olarak, Uzak Masaüstü Hizmetleri Uzak Masaüstü Bağlantısı istemcisine bir parola girerek kullanıcıların otomatik olarak oturum açmasına olanak tanır. Bu ilke ayarını etkinleştirirseniz, kullanıcılar Uzak Masaüstü Bağlantısı istemcisinde parolalarını sağlayarak Uzak Masaüstü Hizmetleri otomatik olarak oturum açamaz. oturum açmak için parola istenir. Bu ilke ayarını devre dışı bırakırsanız, kullanıcılar Uzak Masaüstü Bağlantısı istemcisinde parolalarını sağlayarak Uzak Masaüstü Hizmetleri her zaman otomatik olarak oturum açabilirler. Bu ilke ayarını yapılandırmazsanız, grup ilkesi düzeyinde otomatik oturum açma belirtilmez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067328)  
  
  **Varsayılan**: etkin
  
- **Uzak Masaüstü Hizmetleri istemci bağlantısı şifreleme düzeyi**  
  Uzak Masaüstü Protokolü (RDP) bağlantıları sırasında istemci bilgisayarlar ile RD Oturumu Ana Bilgisayarı sunucuları arasındaki iletişimin güvenliğini sağlamak için belirli bir şifreleme düzeyinin kullanılıp kullanılmayacağını belirtir. Bu ilke yalnızca yerel RDP şifrelemesini kullanırken geçerlidir. Ancak, yerel RDP şifrelemesi (SSL şifrelemesinin aksine) önerilmez. Bu ilke, SSL şifrelemesi için uygulanmaz. Bu ilke ayarını etkinleştirirseniz, uzak bağlantılar sırasında istemciler ve RD Oturumu Ana Bilgisayarı sunucular arasındaki tüm iletişimler bu ayarda belirtilen şifreleme yöntemini kullanmalıdır. Varsayılan olarak, şifreleme düzeyi yüksek olarak ayarlanır. Aşağıdaki şifreleme yöntemleri kullanılabilir:  
  - *Yüksek* ayarı, güçlü 128 bit şifrelemeyi kullanarak istemciden sunucuya ve sunucudan istemciye gönderilen verileri şifreler. Bu şifreleme düzeyini yalnızca 128 bitlik istemciler (örneğin, Uzak Masaüstü Bağlantısı çalıştıran istemciler) içeren ortamlarda kullanın. Bu şifreleme düzeyini desteklemeyen istemciler RD Oturumu Ana Bilgisayarı sunucularına bağlanamaz.  
  - *Istemci uyumluluğu* -Istemci ile uyumlu ayarı, istemci ile sunucu arasında gönderilen verileri, istemci tarafından desteklenen en büyük anahtar gücüyle şifreler. 128 bit şifrelemeyi desteklemeyen istemcileri içeren ortamlarda bu şifreleme düzeyini kullanın.  
  - *Düşük* -düşük ayar, 56 bit şifrelemeyi kullanarak yalnızca istemciden sunucuya gönderilen verileri şifreler.  
  
  Bu ayarı devre dışı bırakır veya yapılandırmazsanız, RD Oturumu Ana Bilgisayarı sunucularına uzak bağlantılar için kullanılacak şifreleme düzeyi grup ilkesi aracılığıyla zorlanmaz. Önemli FIPS uyumluluğu Sistem şifrelemesi aracılığıyla yapılandırılabilir. Grup ilkesi (Bilgisayar Yapılandırması \ güvenlik ayarları \ yerel ilkeler \ güvenlik seçenekleri altında) şifreleme, karma ve imzalama ayarları için FIPS uyumlu algoritmalar kullanın. FIPS uyumlu ayar, Microsoft şifreleme modüllerini kullanarak istemciden sunucuya ve sunucudan istemciye gönderilen verilerin şifrelemesini, Federal bilgi Işleme standardı (FIPS) 140 şifreleme algoritmalarıyla şifreler ve şifresini çözer. İstemcilerle RD Oturumu Ana Bilgisayarı sunucuları arasındaki iletişimler en yüksek düzeyde şifrelemeyi gerektirdiğinde bu şifreleme düzeyini kullanın.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067222)  
  
  **Varsayılan**: yüksek
  
## <a name="remote-management"></a>Uzaktan Yönetim  
Daha fazla bilgi için Windows belgelerindeki [Ilke CSP-RemoteManagement](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remotemanagement) bölümüne bakın.  

- **Farklı çalıştır kimlik bilgilerini depolamayı engelle**  
  İstemci temel kimlik doğrulaması.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067300)  
  
  **Varsayılan**: etkin
  
- **Temel kimlik doğrulaması**  
  Bu ilke ayarı, Windows Uzaktan Yönetimi (WinRM) hizmetinin uzak bir istemciden Temel kimlik doğrulaması kabul edip etmediğini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz WinRM hizmeti, uzak bir istemciden Temel kimlik doğrulamasını kabul eder. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, WinRM hizmeti uzak bir istemciden Temel kimlik doğrulamasını kabul etmez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067223)  
  
  **Varsayılan**: devre dışı
  
- **İstemci Özeti kimlik doğrulamasını engelle**  
  Bu ilke ayarı, Windows Uzaktan Yönetimi (WinRM) istemcisinin Özet kimlik doğrulaması kullanıp kullanmadığını yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, WinRM istemcisi Özet kimlik doğrulaması kullanmaz. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, WinRM istemcisi Özet kimlik doğrulaması kullanır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067302)  
  
  **Varsayılan**: etkin
  
- **Şifrelenmemiş trafik**  
  Bu ilke ayarı, Windows Uzaktan Yönetimi (WinRM) hizmetinin ağ üzerinden şifrelenmemiş iletiler gönderip alıp almayacağını yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, WinRM istemcisi ağ üzerinden şifrelenmemiş iletiler gönderir ve alır. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, WinRM istemcisi ağ üzerinden yalnızca şifrelenmiş iletiler gönderir veya alır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067226)  
  
  **Varsayılan**: devre dışı
  
- **İstemci şifrelenmemiş trafiği**  
  Bu ilke ayarı, Windows Uzaktan Yönetimi (WinRM) istemcisinin ağ üzerinden şifrelenmemiş iletiler gönderip göndermediğini yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, WinRM istemcisi ağ üzerinden şifrelenmemiş iletiler gönderir ve alır. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, WinRM istemcisi ağ üzerinden yalnızca şifrelenmiş iletiler gönderir veya alır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067304)  
  
  **Varsayılan**: devre dışı
  
- **İstemci temel kimlik doğrulaması**  
  Bu ilke ayarı, Windows Uzaktan Yönetimi (WinRM) istemcisinin temel kimlik doğrulaması kullanıp kullanmadığını yönetmenizi sağlar. Bu ilke ayarını etkinleştirirseniz, WinRM istemcisi temel kimlik doğrulamasını kullanır. WinRM, HTTP taşıması kullanacak şekilde yapılandırıldıysa, Kullanıcı adı ve parola ağ üzerinden şifresiz metin olarak gönderilir. Bu ilke ayarını devre dışı bırakır veya yapılandırmazsanız, WinRM istemcisi temel kimlik doğrulaması kullanmaz.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067252)  
  
  **Varsayılan**: devre dışı
  
## <a name="remote-procedure-call"></a>Uzak yordam çağrısı  
Daha fazla bilgi için Windows belgelerindeki [POLICY CSP-RemoteProcedureCall](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remoteprocedurecall) bölümüne bakın.  

- **RPC kimliği doğrulanmamış istemci seçenekleri**  
  Bu ilke ayarı, RPC sunucusu çalışma zamanının RPC sunucularına bağlanan kimliği doğrulanmamış RPC istemcilerini nasıl işlediğini denetler. Bu ilke ayarı tüm RPC uygulamalarını etkiler. Bir etki alanı ortamında, Grup İlkesi işleme dahil olmak üzere çok çeşitli işlevleri etkileyebileceğinden Bu ilke ayarını dikkatli kullanın. Bu ilke ayarında bir değişikliği geri almak, etkilenen her makinede el ile müdahale gerektirebilir. Bu ilke ayarı, bir etki alanı denetleyicisine hiçbir şekilde uygulanmamalıdır. Bu ilke ayarını devre dışı bırakırsanız, RPC sunucusu çalışma zamanı Windows Istemcisinde "kimliği doğrulanmış" değerini ve bu ilke ayarını destekleyen Windows Server sürümlerinde "none" değerini kullanır. Bu ilke ayarını yapılandırmazsanız, devre dışı kalır. RPC sunucusu çalışma zamanı, Windows Istemcisi için kullanılan "kimliği doğrulanmış" değeri ve bu ilke ayarını destekleyen sunucu SKU 'Ları için kullanılan "none" değeri ile etkinleştirilmiş gibi davranır. Bu ilke ayarını etkinleştirirseniz, bir makinede çalışan RPC sunucularına bağlanan kimliği doğrulanmamış RPC istemcilerini kısıtlamak için RPC sunucusu çalışma zamanını yönlendirir. İstemci, sunucuyla iletişim kurmak için adlandırılmış bir kanal kullanıyorsa veya RPC güvenliği kullanıyorsa, kimliği doğrulanmış bir istemci olarak kabul edilir. Kimliği doğrulanmamış istemciler tarafından erişilebilmesi istenen RPC arabirimleri, bu ilke ayarı için seçilen değere bağlı olarak bu kısıtlamadan muaf kalabilir.  
  - *Hiçbiri* tüm RPC istemcilerinin, ilke ayarının uygulandığı MAKINEDE çalışan RPC sunucularına bağlanmasına izin verir. 
  - *Kimliği DOĞRULANMıŞ* RPC istemcilerinin, ilke ayarının uygulandığı MAKINEDE çalışan RPC sunucularına bağlanmasını sağlar. Bu arabirimleri isteyen arabirimlere muafiyet verilir. 
  - *Özel durumlar olmadan kimlik doğrulaması* yalnızca KIMLIĞI doğrulanmış RPC istemcilerinin (Yukarıdaki Tanım başına) ilke ayarının uygulandığı MAKINEDE çalışan RPC sunucularına bağlanmasını sağlar. Hiçbir özel duruma izin verilmez. Note: Bu ilke ayarı, sistem yeniden başlatılana kadar uygulanmaz.  

  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067225)  

  **Varsayılan**: kimliği doğrulandı

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
  
  **Varsayılan**: iyi bilinmeyen ve hatalı kritik


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

  **Varsayılan**: etkin
  
## <a name="microsoft-defender"></a>Microsoft Defender  
Daha fazla bilgi için Windows belgelerindeki [Ilke CSP-Defender](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender) bölümüne bakın.  

- **Gelen posta iletilerini Tara**  
  E-postanın taranarak veya taramaya izin vermez.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067116)  
  
  **Varsayılan**: Evet  

- **Office uygulamaları alt işlem türünü Başlat**  
  Office uygulamalarının alt işlem oluşturmasına izin verilmez. Buna Word, Excel, PowerPoint, OneNote ve Access dahildir. Bu, özellikle de kötü amaçlı yürütülebilir dosyaları başlatmak veya indirmek üzere Office uygulamalarını kullanmaya çalışacak makro tabanlı saldırılar için tipik bir kötü amaçlı yazılım davranışıdır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067121)  
  
  **Varsayılan**: engelle
  
- **Defender örnek gönderimi onay türü**  
  Veri göndermek için Microsoft Defender 'daki Kullanıcı izin düzeyini denetler. Gerekli onay zaten verildiyse, Microsoft Defender bunları gönderir. Aksi takdirde (ve Kullanıcı hiçbir zaman sorma), veri göndermeden önce Kullanıcı izni (Defender/AllowCloudProtection 'a izin verildiğinde) istemek için kullanıcı ARABIRIMI başlatılır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067131)  
  
  **Varsayılan**: güvenli örnekleri otomatik olarak gönder 
  
- **İmza güncelleştirme aralığı (saat)**  
  Defender imza güncelleştirme aralığı saat cinsinden
  
  **Varsayılan**: 4
  
- **Betiği indirilen yük yürütme türü**  
  Defender betiği indirilen yük yürütme türü
  
  **Varsayılan**: engelle
  
- **Kimlik bilgisi hırsızlığı türünü engelle**  
  Microsoft Defender Credential Guard, yalnızca ayrıcalıklı sistem yazılımlarının erişebilmesi için gizli dizileri yalıtmak üzere sanallaştırma tabanlı güvenlik kullanır. Bu parolalara yetkisiz erişim, Pass-the-Hash veya Pass-The-Ticket gibi kimlik bilgisi hırsızlığı saldırılarına yol açabilir. Microsoft Defender Credential Guard, NTLM parola karmalarını, Kerberos bileti verme biletlerini ve uygulamalar tarafından etki alanı kimlik bilgileri olarak depolanan kimlik bilgilerini koruyarak bu saldırıları engeller.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067065)  
  
  **Varsayılan**: etkinleştir

- **E-posta içeriği yürütme türü**  
  Bu kural, aşağıdaki dosya türlerinin Microsoft Outlook veya Web postasından (örn. exe,. dll veya. SCR) komut dosyaları (örneğin, PowerShell. PS, VisualBasic. vbs gibi) görülen bir e-postadan çalıştırılmasını veya başlatılmasını engeller. ya da JavaScript. js dosyası) betik Arşivi dosyaları.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067063)  
  
  **Varsayılan**: engelle
::: zone-end
::: zone pivot="mdm-may-2019"

- **Bir alt işlemde Adobe Reader başlatma**  

  **Varsayılan**: etkinleştir
::: zone-end
::: zone pivot="mdm-preview,mdm-may-2019"

- **Ağ koruması**  
  Bu ilke, Microsoft Defender Exploit Guard 'da ağ korumasını (engelleme/denetim) açmanıza veya kapatmanıza olanak sağlar. Ağ koruması, Microsoft Defender Exploit Guard 'ın herhangi bir uygulamayı kullanan çalışanları, kimlik avı dolandırıcılığı, yararlanma siteleri ve Internet 'teki kötü amaçlı içeriklere erişmesini koruyan bir özelliktir. Bu, üçüncü taraf tarayıcıların tehlikeli sitelere bağlanmasını engellemeyi de kapsar. Değer türü tamsayı. Bu ayarı etkinleştirirseniz, ağ koruması açıktır ve çalışanlar bu özelliği kapatamaz. Davranışı şu seçenekler tarafından denetlenebilir: Block ve audit. Bu ilkeyi "engelle" seçeneği ile etkinleştirirseniz, kullanıcıların ve uygulamaların tehlikeli etki alanlarına bağlanması engellenir. Bu etkinliği Microsoft Defender Güvenlik Merkezi 'nde görebilirsiniz. Bu ilkeyi "Denetim" seçeneği ile etkinleştirirseniz, kullanıcıların/uygulamaların tehlikeli etki alanlarına bağlanması engellenmez. Bununla birlikte, yine de bu etkinliği Microsoft Defender Güvenlik Merkezi ' nde görürsünüz. Bu ilkeyi devre dışı bırakırsanız, kullanıcıların/uygulamaların tehlikeli etki alanlarına bağlanması engellenmez. Microsoft Defender Güvenlik Merkezi 'nde herhangi bir ağ etkinliği görmezsiniz. Bu ilkeyi yapılandırmazsanız, ağ engelleme varsayılan olarak devre dışıdır.  
  [Daha fazla bilgi edinin](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-network-protection)  
  
  **Varsayılan**: etkinleştir
  
- **Defender Tarama günü zamanlaması**  
  Defender tarama gününü zamanlayamıyor.
  
  **Varsayılan**: günlük
  
- **Buluta teslim edilen koruma**  
  Bilgisayarınızı en iyi şekilde korumak için Microsoft Defender, bulduğu sorunlar hakkında Microsoft 'a bilgi gönderir. Microsoft bu bilgileri analiz eder, sizi ve diğer müşterileri etkileyen sorunlar hakkında daha fazla bilgi edinin ve geliştirilmiş çözümler sunar.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067039)
  
  **Varsayılan**: Evet  

- **Defender istenmeyebilecek uygulama eylemi**  
  Microsoft Defender virüsten koruma 'daki istenmeyebilecek uygulama (PUA) koruması özelliği, PUAs 'yi ağınızdaki uç noktalara indirme ve yükleme işlemi için tanımlayabilir ve engelleyebilir. Bu uygulamalar virüsler, kötü amaçlı yazılım veya diğer tehdit türleri olarak kabul edilmez, ancak performansını veya kullanımını olumsuz etkileyecek uç noktalar üzerinde eylemler gerçekleştirebilir. PUA, zayıf bir saygınlığa sahip olarak kabul edilen uygulamalara da başvurabilir. Tipik PUA davranışı şunları içerir: Web tarayıcıları sürücüsüne ad ekleme ve sorunları tespit eden en iyi duruma getirme, hataları gidermek için ödeme isteği, ancak uç noktada kalan, ancak bir değişiklik veya iyileştirmeler ("olarak da bilinir" Standart dışı virüsten koruma "programları). Bu uygulamalar, ağınıza kötü amaçlı yazılımdan etkilenme riskini artırabilir, kötü amaçlı yazılımdan bulaşmaları daha zor hale gelir ve uygulamaları temizlemede BT kaynaklarını boşa çıkarabilir.  
  [Daha fazla bilgi edinin](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-puaprotection)    
  
  **Varsayılan**: engelle  

- **Betik gizleme makro kod türü**  
  Kötü amaçlı yazılım ve diğer tehditler bazı betik dosyalarında kötü amaçlı kodlarını gizlemeyi veya gizlemeyi deneyebilir. Bu kural, görünmeyen görünen betiklerin çalışmasını engeller.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067026)  
  
  **Varsayılan**: engelle
  
- **Tam tarama sırasında çıkarılabilir sürücüleri tarama**  
  Microsoft Defender 'ın, tam tarama sırasında çıkarılabilir sürücülerde (örneğin, Flash sürücüler) kötü amaçlı ve istenmeyen yazılımları taramasına izin verir. Microsoft Defender virüsten koruma, yürütmeden önce USB cihazlarındaki tüm dosyaları tarar.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067036)  
  
  **Varsayılan**: Evet  
  
- **Arşiv dosyalarını tara**  
  Defender arşiv dosyalarını tarar.
  
  **Varsayılan**: Evet
  
- **Davranış izleme**  
  Microsoft Defender davranış Izleme işlevselliğine izin verir veya vermez. Windows 10 ' da gömülü olan bu sensörler, işletim sisteminden davranış sinyallerini toplayıp işler ve bu algılayıcı verilerini Microsoft Defender ATP 'nin özel, yalıtılmış, bulut örneğine gönderir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067111)  
  
  **Varsayılan**: Evet

- **Ağ klasörlerinden açılan dosyaları tara**  
  Dosyalar salt okunurdur, Kullanıcı algılanan herhangi bir kötü amaçlı yazılımı kaldıramayacaktır.
  
  **Varsayılan**: Evet

- **Güvenilmeyen USB işlem türü**  
  Bu kuralla, Yöneticiler, imzasız veya güvenilmeyen yürütülebilir dosyaların SD kartları dahil USB çıkarılabilir sürücülerden çalışmasını engelleyebilir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067100)  
  
  **Varsayılan**: engelle
  
- **Office uygulamaları diğer işlem ekleme türü**  
  Word, Excel, PowerPoint ve OneNote dahil Office uygulamaları diğer işlemlere kod ekleyemeyecektir. Bu genellikle kötü amaçlı yazılım tarafından virüsten koruma tarama altyapılarından etkinliği gizleme girişiminde kötü amaçlı kod çalıştırmak için kullanılır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067019)  
  
  **Varsayılan**: engelle
  
- **Office makro kodu Win32 içeri aktarmalar türüne izin ver**  
  Kötü amaçlı yazılım, sistem genelinde daha fazla bulaşma sağlamak üzere API çağrıları yapmak için kullanılabilecek Win32 DLL 'Lerini içeri aktarmak ve yüklemek üzere Office dosyalarındaki makro kodunu kullanabilir. Bu kural, Win32 DLL 'Leri içeri aktarabilecek makro kodu içeren Office dosyalarını engellemeye çalışır. Buna Word, Excel, PowerPoint ve OneNote dahildir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067130)  
  
  **Varsayılan**: engelle  
  
- **Defender bulut blok düzeyi**  
  Defender bulut blok düzeyi.
  
  **Varsayılan**: yapılandırılmadı

- **Gerçek zamanlı izleme**  
  Defender gerçek zamanlı izleme gerektirir.
  
  **Varsayılan**: Evet
 
::: zone-end
::: zone pivot="mdm-may-2019"
- **Office iletişim uygulamaları bir alt işlemde başlatılır**  

  **Varsayılan**: etkinleştir
::: zone-end
::: zone pivot="mdm-preview,mdm-may-2019"

- **Office uygulamaları yürütülebilir içerik oluşturma veya başlatma türü**  
  Bu kural, şüpheli ve kötü amaçlı eklentiler ve yürütülebilir dosyalar oluşturan ya da Başlatan olağan dışı eklentiler ve betikler (Uzantılar) tarafından kullanılan tipik davranışları hedefler. Bu tipik bir kötü amaçlı yazılım tekniğidir. Uzantıların Office uygulamaları tarafından kullanılması engellenir. Genellikle bu uzantılar, belirli görevleri otomatikleştiren betikleri çalıştırmak veya Kullanıcı tarafından oluşturulan eklenti özellikleri sağlamak için Windows komut dosyası konağını (. WSH dosyaları) kullanır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067108)  
  
  **Varsayılan**: engelle

::: zone-end
::: zone pivot="mdm-may-2019"
## <a name="microsoft-defender-firewall"></a>Microsoft Defender güvenlik duvarı  
Daha fazla bilgi için Windows protokolleri belgelerindeki [2.2.2 FW_PROFILE_TYPE]( https://docs.microsoft.com/openspecs/windows_protocols/ms-fasp/7704e238-174d-4a5e-b809-5f3787dd8acc) bölümüne bakın.  

- **Güvenlik duvarı profili etki alanı**  
  Kuralın ait olduğu profilleri belirtir: etki alanı, özel, genel. Bu değer, etki alanlarına bağlı ağların profilini temsil eder.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2066796)  

  - **Engellenen gelen bağlantılar**  
    **Varsayılan**: Evet

  - **Gerekli giden bağlantılar**  
    **Varsayılan**: Evet 

  - **Engellenen gelen bildirimler**  
    **Varsayılan**: Evet

  - **Güvenlik Duvarı etkin**  
    **Varsayılan**: izin verildi

- **Güvenlik duvarı profili genel**  
  Kuralın ait olduğu profilleri belirtir: etki alanı, özel, genel. Bu değer, ortak ağların profilini temsil eder. Bu ağlar, sunucu konağındaki yöneticiler tarafından genel olarak sınıflandırılır. Sınıflandırma, ana bilgisayarın ağa ilk bağlanışında meydana gelir. Genellikle bu ağlar havaalanları, kafeterler ve ağdaki eşlere veya ağ yöneticisine güvenilmediği diğer genel yerlerdeki olanlardır.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067143)  

  - **Engellenen gelen bağlantılar**  
    **Varsayılan**: Evet

  - **Gerekli giden bağlantılar**  
    **Varsayılan**: Evet 

  - **Engellenen gelen bildirimler**  
    **Varsayılan**: Evet

  - **Güvenlik Duvarı etkin**  
    **Varsayılan**: izin verildi

  - **Grup İlkesi 'nden bağlantı güvenlik kuralları birleştirilmedi**  
    **Varsayılan**: Evet

  - **Grup ilkesinden ilke kuralları birleştirilmedi**  
    **Varsayılan**: Evet

- **Güvenlik duvarı profili özel**  
  Kuralın ait olduğu profilleri belirtir: etki alanı, özel, genel. Bu değer, özel ağların profilini temsil eder.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067041)  

  - **Engellenen gelen bağlantılar**  
    **Varsayılan**: Evet

  - **Gerekli giden bağlantılar**  
    **Varsayılan**: Evet 

  - **Engellenen gelen bildirimler**  
    **Varsayılan**: Evet

  - **Güvenlik Duvarı etkin**  
    **Varsayılan**: izin verildi

## <a name="windows-hello-for-business"></a>İş İçin Windows Hello  
- **Kullanılabilir olduğunda gelişmiş yanıltma koruması gerektir**  
  Yanıt Evet ise, cihazlar, kullanılabilir olduğunda gelişmiş yanıltma koruması kullanacaktır. Hayır ise, sahtekarlığı önleme engellenir. Yapılandırılmadı, istemci üzerinde gerçekleştirilen yapılandırmalara uyar.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067192)

  **Varsayılan**: Evet

- **İş Için Windows Hello 'Yu yapılandırma**   
    Iş için Windows Hello, parolaları, akıllı kartları ve sanal akıllı kartları değiştirerek Windows 'da oturum açmak için alternatif bir yöntemdir.  

  - *Evet*olarak ayarlandığında, bu ilkeyi etkinleştirir ve cihaz Iş Için Windows Hello 'yu hazırlar.  
  - *Yapılandırılmadı*olarak ayarlandığında, taban çizgisi cihazın ilke ayarını etkilemez. Bu, Iş için Windows Hello 'nun bir cihazda devre dışı bırakıldığı durumlarda devre dışı kaldığı anlamına gelir. Etkinse, etkin kalır. 

  Bu taban çizgisi aracılığıyla Iş için Windows Hello 'Yu devre dışı bırakayükleyemezsiniz. [Windows kaydını](windows-hello.md)yapılandırırken veya [kimlik koruması](identity-protection-configure.md)için bir cihaz yapılandırma profilinin parçası olarak Iş için Windows Hello 'yu devre dışı bırakabilirsiniz.  

  **Varsayılan**: Evet

- **PIN kodunda küçük harfler iste**  
  Gerekirse, Kullanıcı PIN 'ı en az bir küçük harf içermelidir.

  **Varsayılan**: izin verildi

- **PIN 'de özel karakterler iste**  
  Gerekirse, Kullanıcı PIN 'ı en az bir özel karakter içermelidir.

  **Varsayılan**: izin verildi

- **Minimum PIN uzunluğu**  
  Minimum PIN uzunluğu 4 ile 127 arasında olmalıdır.

  **Varsayılan**: 6

- **PIN kodunda büyük harfler iste**  
  Gerekirse, Kullanıcı PIN 'ı en az bir büyük harf içermelidir.

  **Varsayılan**: izin verildi
::: zone-end
::: zone pivot="mdm-preview,mdm-may-2019"

## <a name="windows-ink-workspace"></a>Windows Ink çalışma alanı  
Daha fazla bilgi için Windows belgelerindeki [Ilke CSP-WindowsInkWorkspace](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsinkworkspace) bölümüne bakın.  

- **Mürekkep çalışma alanı**  
  Kullanıcının Ink çalışma alanına erişmesine izin verilip verilmeyeceğini belirtir. 
  - *Devre dışı* -mürekkep çalışma alanına erişim devre dışı bırakıldı. Özellik kapalı.
  - *Etkin* -mürekkep çalışma alanı özelliği açıktır, ancak kullanıcı kilit ekranının üzerine erişemez.
  - *Yapılandırılmadı* -mürekkep çalışma alanı özelliği açıktır ve Kullanıcı onu kilit ekranının üzerinde kullanabilir.  

  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067241)  

  **Varsayılan**: etkin
 
## <a name="windows-powershell"></a>Windows PowerShell  
Daha fazla bilgi için Windows belgelerindeki [Ilke CSP-WindowsPowerShell](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowspowershell) bölümüne bakın.  

- **Power Shell kabuğu betik bloğu günlüğü**  
  Bu ilke ayarı, tüm PowerShell betiği girişinin Microsoft-Windows-PowerShell/Işletimsel olay günlüğüne kaydedilmesini sağlar. Bu ilke ayarını etkinleştirirseniz, Windows PowerShell komutların, betik bloklarının, işlevlerin ve betiklerin işlenmesini ister etkileşimli olarak, ister Otomasyon aracılığıyla günlüğe kaydeder. Bu ilke ayarını devre dışı bırakırsanız, PowerShell betik girişinin günlüğe kaydı devre dışı bırakılır. Betik bloğu çağırma günlüğünü etkinleştirirseniz, PowerShell Ayrıca bir komut, betik bloğu, işlev veya komut dosyası başlatıldığında veya durdurulduğunda olayları günlüğe kaydeder. Çağırma günlüğünü etkinleştirmek, yüksek miktarda olay günlüğü oluşturur. Note: Bu ilke ayarı, grup ilkesi düzenleyicisinde hem bilgisayar yapılandırması hem de Kullanıcı Yapılandırması altında bulunur. Bilgisayar yapılandırma ilkesi ayarı, Kullanıcı yapılandırma ilkesi ayarından önceliklidir.  
  [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2067330)  

  **Varsayılan**: etkin

::: zone-end
::: zone pivot="mdm-may-2019"  
## <a name="whats-changed-in-the-new-template"></a>Yeni şablonda değiştirilen özellikler
*2019 Mayıs şablonuna yönelik MDM güvenlik temeli* , *Önizleme* şablonundan aşağıdaki değişikliklere sahiptir.

### <a name="changes-to-the-baseline-settings"></a>Taban çizgisi ayarlarındaki değişiklikler
Aşağıdaki ayarlar şunlardır:
- Taban çizgisinin bu en son sürümünde *yenidir* .
- Bu en son temel sürümden *kaldırıldı* , ancak önceki sürümde vardı.
- Önceki sürümde ayarların nasıl görünmeyeceği bir şekilde *yeniden düzenlendi* . 

*[Yeni]* [**kilidin üzerinde**](#above-lock):
- **Uygulamaları kilitli ekrandan etkinleştir**    

*[Yeni]* [**uygulama yönetimi**](#application-management): 
- **Yüklemeler üzerinde kullanıcı denetimini engelle**  
- **Yükseltilmiş ayrıcalıklarla MSI uygulama yüklemelerini engelleyin**  

*[Kaldırıldı]* [**BitLocker**](#bitlocker):  
- Bit dolabı çıkarılabilir sürücü ilkesi > **şifreleme yöntemi**
- **Bit dolabı sabit sürücü ilkesi** *(tüm ayarlar)*
- **Bit dolabı sistem sürücüsü ilkesi** *(tüm ayarlar)*

*[Yeni]* [**bağlantı**](#connectivity):
- **UNC yollarına güvenli erişimi yapılandırma**

*[Yeni]* [**Device Guard**](#device-guard):
- **Sanallaştırma tabanlı güvenlik**


*[Yeni]* [**DMA koruyucusu**](#dma-guard):
- **Çekirdek DMA koruması ile uyumsuz dış cihazların numaralandırması**  

*[Yeni]* [**Internet Explorer**](#internet-explorer):
- **Komut dosyası aracılığıyla durum çubuğuna Internet Explorer Internet bölgesi güncelleştirmeleri**
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


*[Yeni]* [**Microsoft Defender**](#microsoft-defender):
- **Bir alt işlemde Adobe Reader başlatma**  
- **Office iletişim uygulamaları bir alt işlemde başlatılır** 

*[Yeni]* [ **Microsoft Defender güvenlik duvarı**](#microsoft-defender-firewall)
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

*[Yeni]* [**Iş için Windows Hello**](#windows-hello-for-business):  
- **Kullanılabilir olduğunda gelişmiş yanıltma koruması gerektir**  
- **Iş için Windows Hello 'Yu yapılandırma**  
- **PIN kodunda küçük harfler iste** 
- **PIN 'de özel karakterler iste** 
- **Minimum PIN uzunluğu**  
- **PIN kodunda büyük harfler iste** 
::: zone-end




 