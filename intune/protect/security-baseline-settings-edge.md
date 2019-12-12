---
title: Microsoft Edge için Intune güvenlik temelleri ayarları
titleSuffix: Microsoft Intune
description: Intune tarafından Microsoft Edge tarayıcısını yönetmek için desteklenen güvenlik temeli ayarları
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/30/2019
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
ms.openlocfilehash: c75029c60609b0383e2f647e5b94144d4186248c
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "73754867"
---
# <a name="microsoft-edge-baseline-settings-for-intune"></a>Intune için Microsoft Edge taban çizgisi ayarları

Microsoft Intune tarafından desteklenen Microsoft Edge Web tarayıcısı taban çizgisi ayarlarını görüntüleyin. Microsoft Edge taban çizgisi Varsayılanları, Microsoft Edge tarayıcıları için önerilen yapılandırmayı temsil eder ve diğer güvenlik temelleri için temel varsayılanlarla eşleşmeyebilir.

> [!NOTE]
> Microsoft Edge taban çizgisi genel önizlemede. 

## <a name="microsoft-edge"></a>Microsoft Edge

- **Siteler için Microsoft Defender SmartScreen istemlerinin atlanmasını engelle**  
  **Varsayılan**: etkin  
  Microsoft Edge CSP: [Browser/PreventSmartScreenPromptOverride](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-preventsmartscreenpromptoverride)

  Bu ilke ayarı, kullanıcıların olası kötü amaçlı Web siteleri hakkında Microsoft Defender SmartScreen uyarılarını geçersiz kılıp kılamayacağını belirlemenize olanak sağlar. 
  - Bu ayarı etkinleştirirseniz, kullanıcılar Microsoft Defender SmartScreen uyarılarını yok sayamazlar ve siteye devam etmeleri engellenir. 
  - Bu ayarı devre dışı bırakır veya yapılandırmazsanız, kullanıcılar Microsoft Defender SmartScreen uyarılarını yoksayabilir ve siteye devam edebilir.

- **En düşük SSL sürümü etkin**  
  **Varsayılan**: etkin  

  SSL 'nin desteklenen en düşük sürümünü ayarlayın. Bu ilkeyi *Yapılandırılmadı*olarak ayarlarsanız, Microsoft Edge varsayılan en düşük *TLS 1,0*sürümünü kullanır. *Etkin*olarak ayarlandığında, aşağıdaki değerlerden en düşük sürümü seçebilirsiniz:

  - TLS 1.0
  - TLS 1.1
  - TLS 1.2

  - **En düşük SSL sürümü etkin**  
    **Varsayılan**: TLS 1,2

- **İndirmeler hakkında Microsoft Defender SmartScreen uyarılarını atlamayı engelle**  
  **Varsayılan**: etkin  
  Microsoft Edge CSP: [Browser/PreventSmartScreenPromptOverrideForFiles](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-preventsmartscreenpromptoverrideforfiles)  

  Bu ilke, kullanıcıların doğrulanmamış indirmeler hakkında Microsoft Defender SmartScreen uyarılarını geçersiz kılıp kılamayacağını belirlemenizi sağlar.
  - Bu ilkeyi etkinleştirirseniz kuruluşunuzdaki kullanıcılar Microsoft Defender SmartScreen uyarılarını yok sayamazlar ve doğrulanmamış İndirmeleri tamamlamada engellenirler.
  - Bu ilkeyi devre dışı bırakır veya yapılandırmazsanız, kullanıcılar Microsoft Defender SmartScreen uyarılarını yoksayabilir ve doğrulanmamış İndirmeleri tamamlayabilir.

- **Kullanıcıların SSL uyarı sayfasından devam edebilsin**  
  **Varsayılan**: devre dışı  
  Microsoft Edge CSP: [Browser/Preventcerterrorkılmalar](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-preventcerterroroverrides)  

  Microsoft Edge, kullanıcılar SSL hatalarına sahip siteleri ziyaret ettiğinde bir uyarı sayfası gösterir. Bu ilkeyi *etkin* veya *yapılandırılmamış*olarak ayarlarsanız, kullanıcılar bu uyarı sayfalarında tıklabilirler. Bu ilke *devre dışı*bırakıldığında, kullanıcıların herhangi bir uyarı sayfasında tıklamakla engellenir. 

- **Varsayılan Adobe Flash ayarı**  
  **Varsayılan**: etkin  
  Microsoft Edge CSP: [Browser/AllowFlash](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-allowflash)ve [Browser/Allowflashtıklatorun](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-allowflashclicktorun)  

  ' Pluginsallodilimforurls ' veya ' PluginsBlockedForUrls ' tarafından kapsanmayan Web sitelerinin Adobe Flash eklentisini otomatik olarak çalıştırıp çalıştıramayacağını belirler. 

  - Tüm sitelerde Adobe Flash 'ı engellemek için ' Blockeklentiler ' seçeneğini belirleyin
  - Adobe Flash 'ın çalışmasına izin vermek, ancak kullanıcının uygulamayı başlatmak için yer tutucuya tıklamasına izin vermek için ' ClickToPlay ' seçeneğini belirleyin.
  
   Herhangi bir durumda, ' Pluginsallodilimforurls ' ve ' PluginsBlockedForUrls ' ilkeleri ' DefaultPluginsSetting ' üzerinden önceliklidir. Otomatik kayıttan yürütmeye yalnızca ' Pluginsallodilimforurls ' ilkesinde açık olarak listelenen etki alanları için izin verilir. 
   Tüm siteler için otomatik kayıttan yürütmeyi etkinleştirmek istiyorsanız, bu listeye http://* ve https://* eklemeyi göz önünde bulundurun. 
   
   - Bu ilkeyi *Yapılandırılmadı*olarak ayarlarsanız, Kullanıcı bu ayarı el ile değiştirebilir. * 2 = Adobe Flash eklentisini engelle * 3 = önceki ' 1 ' seçenek kümesini izin ver-All ' ı oynatmak için tıklayın, ancak bu işlev artık yalnızca ' Pluginsallodilimforurls ' ilkesi tarafından işlenir. ' 1 ' kullanan mevcut ilkeler tıklama-yürütme modunda çalışır.  
 
  - **Varsayılan Adobe Flash ayarı**  
    **Varsayılan**: Adobe Flash eklentisini engelle

- **Her site için site yalıtımını etkinleştir**  
  **Varsayılan**: etkin  

  ' SitePerProcess ' ilkesi, kullanıcıların tüm siteleri yalıtma için varsayılan davranışı yerine almasını engellemek için kullanılabilir. Ayrıca, ek ve daha hassas kaynakları yalıtmak için ısotekaynakları ilkesini de kullanabilirsiniz.

  - Bu ilke *etkin*olarak ayarlandığında, kullanıcılar her sitenin kendi sürecinde çalıştığı varsayılan davranışı geri çevirebilir. 
  - *Devre dışı* veya *yapılandırılmamış*olarak kullanırsanız, Kullanıcı site yalıtımını devre dışı bırakabilirsiniz. (Örneğin, edge://flags içinde "site yalıtımını devre dışı bırak" girişini kullanarak) İlkeyi devre dışı bırakmak veya ilkeyi yapılandırmak, site yalıtımını kapatamaz.

- **Desteklenen kimlik doğrulama şemaları**  
  **Varsayılan**: etkin  

  Hangi HTTP kimlik doğrulama düzenlerinin desteklendiğini belirtir. İlkeyi şu değerleri kullanarak yapılandırabilirsiniz: ' Basic ', ' Digest ', ' NTLM ' ve ' anlaş '. Birden çok değeri virgülle ayırın. Bu ilkeyi yapılandırmazsanız dört düzen de kullanılır.
 
  - **Desteklenen kimlik doğrulama şemaları**  
    Aşağıdaki seçeneklerden seçim yapın: 
    - Temel
    - Bilgisi
    - NTLM *(varsayılan olarak seçilidir)*
    - Anlaş *(varsayılan olarak seçilidir)*

- **Parola yöneticisine parolaların kaydedilmesini etkinleştir**  
  **Varsayılan**: devre dışı  
  Microsoft Edge CSP: [Browser/AllowPasswordManager](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-allowpasswordmanager)  

  Kullanıcı parolalarını kaydetmek için Microsoft Edge 'i etkinleştirin. 
  - Bu ilkeyi etkinleştirirseniz kullanıcılar parolalarını Microsoft Edge 'e kaydedebilir. Siteyi daha sonra ziyaret ettiklerinde, Microsoft Edge parolayı otomatik olarak girer. 
  - Bu ilkeyi devre dışı bırakırsanız, kullanıcılar yeni parolaları kaydedemez, ancak daha önce kaydedilen parolaları kullanmaya devam edebilirler. 
  
  Bu ilkeyi *etkin* veya *devre dışı*olarak ayarlarsanız, kullanıcılar Microsoft Edge 'de bu ilkeyi değiştiremez veya geçersiz kılamazsınız. 
  
  Bunu *Yapılandırılmadı*olarak ayarlarsanız, kullanıcılar parolaları kaydedebilir ve bu özelliği kapatabilir.

- **Hangi uzantıların yükleneyüklenmediğini denetleme**  
  **Varsayılan**: etkin  

  Kullanıcıların Microsoft Edge 'e yükleyene özel uzantıları listeleyin. Bu ilkeyi dağıttığınızda, bu listede daha önce yüklenmiş olan uzantılar devre dışıdır ve Kullanıcı bunları etkinleştiremeyecektir. Engellenen uzantılar listesinden bir öğeyi kaldırırsanız, bu uzantı önceden yüklenmiş olduğu her yerde otomatik olarak yeniden etkinleştirilir.
  
  İzin verilenler listesinde açıkça listelenmeyen tüm uzantıları engellemek için **\*** kullanın. Bu ilke *Yapılandırılmadı*olarak ayarlandıysa, kullanıcılar Microsoft Edge 'de herhangi bir uzantıyı yükleyebilir. 
  
  Örnek değer: extension_id1 extension_id2.  
  <br>
  - **Uzantı kimlikleri kullanıcının yüklemesi engellenmelidir (veya * tümü için)**  
    **Ekle** ' yi seçin ve ek uzantıları belirtin. **\*** varsayılan olarak seçilidir.

- **Microsoft Defender SmartScreen 'i yapılandırma**  
  **Varsayılan**: etkin  
  Microsoft Edge CSP: [tarayıcı/AllowSmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen)  
  
  Bu ilke ayarı, Microsoft Defender SmartScreen 'i açıp kullanmayacağınızı yapılandırmanızı sağlar. Microsoft Defender SmartScreen, kullanıcılarınızın olası kimlik avı dolandırıcılarından ve kötü amaçlı yazılımlardan korunmasına yardımcı olmak için uyarı iletileri sağlar. 
  
  - Varsayılan olarak, Microsoft Defender SmartScreen açıktır. Bu ayarı etkinleştirirseniz, Microsoft Defender SmartScreen açık olur ve kullanıcılar bu özelliği kapatamaz.
  - Bu ayarı devre dışı bırakırsanız, Microsoft Defender SmartScreen kapalıdır ve kullanıcılar açamaz. 
  - *Yapılandırılmadı*olarak ayarlandığında, kullanıcılar Microsoft Defender SmartScreen 'i kullanıp kullanmayacağınızı seçebilirler. 
  
  Bu ilke yalnızca Microsoft etkin bir etki alanına katılmış Windows örneklerinde veya cihaz yönetimi için kaydedilen Windows 10 Pro veya Enterprise örneklerinde kullanılabilir.

- **Kullanıcı düzeyindeki yerel mesajlaşma konaklarına izin ver (yönetici izinleri olmadan yüklenir)**  
  **Varsayılan**: devre dışı  

  Yerel mesajlaşma konakları için Kullanıcı düzeyinde yüklemeyi mümkün. 
  - Bu ilkeyi devre dışı bırakırsanız, Microsoft Edge yalnızca sistem düzeyinde yüklü yerel mesajlaşma Konakları kullanır. Varsayılan olarak, bu ilkeyi yapılandırmazsanız, Microsoft Edge kullanıcı düzeyindeki yerel mesajlaşma ana bilgisayarlarının kullanılmasına izin verir.

## <a name="next-steps"></a>Sonraki adımlar

[Intune 'da güvenlik temellerini kullanma](security-baselines.md)
