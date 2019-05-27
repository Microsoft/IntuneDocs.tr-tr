---
title: Windows için Microsoft Intune - Azure için iş güncelleştirme ayarları | Microsoft Docs
description: Intune kullanarak dağıtabileceğiniz Windows 10 cihazları için WUfB ayarları.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 04/18/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: aiwang
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: c5a0ee88a24804294346888facef523f89fee816
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66046642"
---
# <a name="windows-update-settings-for-intune"></a>Windows Intune için ayarları güncelleştir  

Yapabilecekleriniz Windows 10 güncelleştirme ayarları görüntülemek [yapılandırmak ve yönetmek](windows-update-for-business-configure.md) Intune.  

Intune'da Windows 10 güncelleştirme halkaları için ayarlarını yapılandırdığınızda, Windows Update ayarlarını yapılandırma. Bir Windows update ayarını bir Windows 10 sürüm bağımlılığı vardır, sürüm bağımlılık ayarları ayrıntılarında belirtilir.  

## <a name="update-settings"></a>Güncelleştirme ayarları  

Bir cihaz indirir, hangi BITS ayarları denetimini güncelle ve ne zaman. Her ayarın davranış hakkında daha fazla bilgi için Windows başvuru belgelerine bakın.  

### <a name="servicing-channel"></a>Hizmet kanalı  

- **Varsayılan**: Yarı Yıllık kanal (hedeflenen)  
- **Windows başvuru belgeleri**: [Güncelleştirme/BranchReadinessLevel](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-branchreadinesslevel)  
Cihazın Windows güncelleştirmelerini aldığı kanalı (dal) ayarlayın. Farklı kanallar güncelleştirmeleri teslim önce farklı erteleme nokta kullanabilirsiniz.  

Örneğin, *yarı yıllık kanal* altı aylık erteleme sahiptir. Bu kanal, hiçbir ek gönderilemeyenler ayarlarının bu gövdesinden ile kullanırsanız, cihaz güncelleştirme altı ay sonra sürüm yükler.  

Desteklenen güncelleştirme kanalları:  

- Yarı Yıllık kanal  
- Yarı Yıllık kanal (hedeflenen)  
- Windows Insider-hızlı  
- Windows Insider-yavaş  
- Windows Insider Yayımlama  

Insider kanal'ı seçerseniz, Intune ayarı Windows update otomatik olarak yapılandırır. [güncelleştirme/ManagePreviewBuilds](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-managepreviewbuilds) böylece Insider derlemesi çalışır.  


> [!IMPORTANT]  
> Windows ile sürüm 1903, kullanımını başlayarak *yarı yıllık kanal (hedefli)* (SAC-T) devre dışı bırakılan. Bu değişiklik, SAC-T ile birleştirir. *yarı yıllık kanal*. Bu değişiklik ve iş için Windows Update nasıl etkilediği hakkında daha fazla bilgi için Windows BT Pro Blog gönderisine bakın [SAC-T devre dışı bırakılması ve iş için Windows Update](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/Windows-Update-for-Business-and-the-retirement-of-SAC-T/ba-p/339523).
 


### <a name="microsoft-product-updates"></a>Microsoft ürün güncelleştirmeleri  

- **Varsayılan**:  İzin Ver
- **Windows başvuru belgeleri**: [Update/AllowMUUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowmuupdateservice)

Seçin *izin* Microsoft Update'ten uygulama güncelleştirmeleri için tarama.    

### <a name="windows-drivers"></a>Windows sürücüleri  

- **Varsayılan**:  İzin Ver
- **Windows başvuru belgeleri**: [Güncelleştirme/ExcludeWUDriversInQualityUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-excludewudriversinqualityupdate)

Seçin *izin* güncelleştirmeler sırasında Windows Update sürücülerini eklemek için

### <a name="quality-update-deferral-period-days"></a>Kalite güncelleştirmesi erteleme süresi (gün)  

- **Varsayılan**: 0  
- **Windows başvuru belgeleri**: [Update/DeferQualityUpdatesPeriodInDays](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-deferqualityupdatesperiodindays)  

Kalite güncelleştirmelerini ertelenmiş 30 0 gün sayısını belirtin. Ek olarak, seçtiğiniz hizmet kanalı parçasıdır erteleme süresi dönemdir. İlke cihaz tarafından alındığında erteleme süresi başlar.  

Kalite güncelleştirmeleri, genellikle mevcut Windows işlevselliğine yönelik düzeltme ve cihazlardır.  

### <a name="feature-update-deferral-period-days"></a>Özellik güncelleştirmesi erteleme süresi (gün)  

- **Varsayılan**: 0  
- **Windows başvuru belgeleri**: [Update/PauseFeatureUpdatesPeriodInDays](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-deferfeatureupdatesperiodindays)  

Özellik güncelleştirmeleri ertelenmiş gün sayısını belirtin. Ek olarak, seçtiğiniz hizmet kanalı parçasıdır erteleme süresi dönemdir. İlke cihaz tarafından alındığında erteleme süresi başlar.  
Desteklenen erteleme süresi:  

- *Windows sürüm 1709 veya üzeri*: 0 ila 365 gün  
- *Windows sürüm 1703*:  0-180 gün  

Özellik Güncelleştirmeleri genellikle Windows’un yeni özellikleridir.  

### <a name="set-feature-update-uninstall-period-2--60-days"></a>Özellik güncelleştirmesini kaldırma süresini Ayarla (2-60 gün)  

- **Varsayılan**: 10  
- **Windows başvuru belgeleri**:  [Güncelleştirme/ConfigureFeatureUpdateUninstallPeriod](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-configurefeatureupdateuninstallperiod)  

Bir süre sonra hangi özellik güncelleştirmelerinin kaldırılamaz yapılandırın.  

Bu süre sona erdikten sonra önceki güncelleştirme BITS CİHAZDAN kaldırılır ve artık önceki bir güncelleştirme sürümüne kaldırabilirsiniz.  

Örneğin, bir özellik ile güncelleştirme halkası düşünün güncelleştirmesini kaldırma süresini 20 güne. 25 gün sonra en son özellik güncelleştirmesine geri alma ve Kaldır seçeneğini kullanmak karar verin.  Özellik güncelleştirmesini üzerinde 20 gün önce yüklü olduğu cihazlara bakım işleminin bir parçası olarak gerekli bitleri kaldırmış gibi kaldıramazsınız. Ancak, bunlar başarıyla 20 gün kaldırma süresi aşan önce kaldırma komutu almak üzere giriş yalnızca özellik güncelleştirmesini yukarı 19 gün önce yüklü olduğu cihazlara güncelleştirme kaldırabilirsiniz.  


## <a name="user-experience-settings"></a>Kullanıcı deneyimi ayarlarını  

Cihaz yeniden başlatıldıktan ve anımsatıcıları son kullanıcı deneyimi kullanıcı deneyimi ayarlarını denetler. Her ayarın davranış hakkında daha fazla bilgi için Windows başvuru belgelerine bakın.  

### <a name="automatic-update-behavior"></a>Otomatik Güncelleştirme davranışı  

- **Varsayılan**: Otomatik olarak yükle ve planlanan bir zamanda yeniden başlatın  
- **Windows başvuru belgeleri**: [Güncelleştir/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)  

Otomatik güncelleştirmelerin nasıl yüklendiğini ve ve gerekirse cihaz yeniden başlatma zamanı.  

Windows başvuru aşağıdaki desteklenen seçenekler için tam açığa belgelerine bakın:  

- **İndirme bilgilendir** – güncelleştirmeyi yüklemeden önce kullanıcıya bildir. Güncelleştirmeleri indirmek ve yüklemek için kullanıcılar'ı seçin.  

- **Bakım zamanında otomatik yükle** -güncelleştirmeleri indirme otomatik olarak ve cihaz kullanın veya pille kullanılmadığında otomatik bakım sırasında yükleyin. Yeniden başlatma gerekli olduğunda, kullanıcılar için yedi güne kadar yeniden başlatmanız istenir ve daha sonra yeniden başlatma zorlanır.  

  Güncelleştirme yüklendikten sonra bu seçeneği bir cihaz otomatik olarak yeniden başlatabilirsiniz. Kullanım **etkin saatlerin** ayarları bir süre boyunca otomatik yeniden Başlatmalara engellenir tanımlamak için:  

  - **Etkin saatlerin başlangıcı**: Güncelleştirme yüklemelerine bağlı yeniden göstermemek için bir başlangıç saati belirtin.  
    **Windows başvuru belgeleri**:  [Güncelleştirme/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)  
    **Varsayılan**: 8 SABAH  
  
  - **Etkin saatlerin sonu**: Güncelleştirme yüklemelerine bağlı yeniden göstermemek için bir bitiş saati belirtin.  
    **Windows başvuru belgeleri**:  [Güncelleştirme/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)  
    **Varsayılan**: 17: 00  

- **Otomatik olarak yükle ve bakım sırasında yeniden** - güncelleştirmeleri indirme otomatik olarak ve cihaz kullanın veya pille kullanılmadığında otomatik bakım sırasında yükleyin. Yeniden başlatma gerektiğinde, cihaz kullanılmadığı zaman yeniden başlatılır. (Bu, yönetilmeyen cihazlar için varsayılan değerdir.)  

  Güncelleştirme yüklendikten sonra bu seçeneği bir cihaz otomatik olarak yeniden başlatabilirsiniz. Kullanım **etkin saatlerin** ayarları Windows Update ayarlarında açıklanan değildir, ancak Intune tarafından bir süre boyunca otomatik yeniden Başlatmalara engellenir tanımlamak için kullanılır:  

  - **Etkin saatlerin başlangıcı**: Güncelleştirme yüklemelerine bağlı yeniden göstermemek için bir başlangıç saati belirtin.  
    **Windows başvuru belgeleri**:  [Güncelleştirme/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)  
    **Varsayılan**: 8 SABAH  

  - **Etkin saatlerin sonu**: Güncelleştirme yüklemelerine bağlı yeniden göstermemek için bir bitiş saati belirtin.  
    **Windows başvuru belgeleri**:  [Güncelleştirme/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)  
    **Varsayılan**: 17: 00  

- **Otomatik olarak yükle ve yeniden zamanlanan saatte** – bir yüklemesi gün ve saati belirtin. Belirtilmemişse, yükleme günlük, 3'de yeniden başlatma için 15 dakikalık geri sayım tarafından izlenen çalıştırır. Oturum açmış kullandığı gecikme geri sayım ve yeniden başlatın.  
  
  Bu seçenek, ek ayarları destekler.  
  **Windows başvuru belgeleri**:  [Güncelleştir/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)  

  - **Otomatik davranış sıklığı**: Bu ayarı kullanarak güncelleştirmelerin yüklenmesini hafta, gün ve saat olarak zamanlayın.  
    **Varsayılan**: Her hafta

  - **Zamanlanan yükleme günü**:  Haftanın hangi gününde güncelleştirmeleri yüklemek istediğinizi belirtin.  
    **Varsayılan**: Herhangi bir gün  

  - **Zamanlanan yükleme saati**:  Güncelleştirmeleri yüklemek için istediğiniz zaman günün saatini belirtin.  
    **Varsayılan**: 3'TE  

- **Otomatik yükle ve yeniden başlatma son kullanıcı denetimi olmadan** -güncelleştirmeleri indirme otomatik olarak ve cihaz kullanın veya pille kullanılmadığında otomatik bakım sırasında yükleyin. Yeniden başlatma gerektiğinde, cihaz kullanılmadığı zaman yeniden başlatılır. Bu seçenek son kullanıcılar Denetim Masası ' salt okunur olarak ayarlar.  

- **Varsayılana Sıfırla** -özgün otomatik güncelleştirme ayarlarını Windows 10 çalıştıran makineleri geri yükleme Ekim 2018 güncelleştirmesi veya üstü.  


### <a name="restart-checks"></a>Yeniden başlatma denetimleri  

- **Varsayılan**: İzin Ver  
- **Windows başvuru belgeleri**: [Güncelleştirme/SetEDURestart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setedurestart)  

Bu ayar, Windows cihazları sürümüne bağlı olarak farklı sonuçlar sahiptir:  

- Windows sürüm 1703 ve öncesinde: Bir cihazı yeniden başlattığınızda ortaya çıkan bazı denetimler vardır; örneğin etkin kullanıcı, pil düzeyi, çalışan oyunlar vb. Cihazı yeniden başlattığınızda bu denetimleri atlamak için **Atla**’yı seçin.  
- Windows sürüm 1709'ile başlayan: Etkin saatlerin sırasında güncelleştirmeleri aşağıdaki işlemleri çalıştırma: tarama, indirme, yükleme ve yeniden başlatın. Etkin saatlerin, güncelleştirme işlemlerini çalıştırmak ve cihaz, uykudan Uyanma özelliğine taradıktan sonra indirin, yükleyin ve pass pil denetimleri ve güç denetler sürece cihazı yeniden başlatın. Daha fazla bilgi için [güncelleştirme/SetEDURestart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setedurestart).  

### <a name="block-user-from-pausing-windows-updates"></a>Duraklatma Windows Update'ten kullanıcıyı engelle  

- **Varsayılan**: İzin Ver  
- **Windows başvuru belgeleri**: [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)  

İzin vermek veya bir güncelleştirme yüklemesini duraklatma bir cihaz kullanıcının engelleyin. 

### <a name="block-user-from-scanning-for-windows-updates"></a>Kullanıcının Windows güncelleştirmeleri için tarama engelleyin  
 - **Varsayılan**: İzin Ver
 - **Windows başvuru belgeleri**: [Update/SetDisableUXWUAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisableuxwuaccess) 

Windows Update taramak için bir kullanıcının erişimine izin verilip verilmeyeceğini belirtir. Örneğin yapılandırırsanız, bir *blok*, kullanıcılar, Windows Update erişemiyor taramak, indirmek ve özellikleri yükleyin.  

### <a name="require-users-approval-to-restart-outside-of-work-hours"></a>İş saatleri dışında yeniden başlatmak için kullanıcı onayı iste  

- **Varsayılan**: Yapılandırılmamış  
- **Windows başvuru belgeleri**: [Güncelleştirme/AutoRestartRequiredNotificationDismissal](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-autorestartrequirednotificationdismissal)
  
Seçin *gerekli* gerektiren bir kullanıcı cihaz yeniden başlatma iş saatleri dışında onaylar.  
   
### <a name="remind-user-prior-to-required-auto-restart-with-dismissible-reminder-hours"></a>Gerekli otomatik yeniden başlatma kapatılabilen anımsatıcı önce kullanıcıyı şu aralıklarla uyar (saat)  

- **Varsayılan**: *Bu ayar varsayılan olarak yapılandırılmamış ve anımsatıcı kullanıcılara sunulan*.  
- **Windows başvuru belgeleri**: [Güncelleştirme/ScheduleRestartWarning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-schedulerestartwarning)  

Bu yeniden başlatma hakkında cihaz kullanıcısına kapatılabilen bir bildirim görüntülenecek belirtin'de otomatik yeniden başlatma öncesinde bu seçeneği belirtin. Değerleri **2**, **4**, **8**, **12**, veya **24** saat desteklenir.  

### <a name="remind-user-prior-to-required-auto-restart-with-permanent-reminder-minutes"></a>Gerekli otomatik yeniden başlatma kalıcı anımsatıcı (dakika) önce kullanıcıyı şu aralıklarla uyar  

- **Varsayılan**: *Bu ayar varsayılan olarak yapılandırılmamış ve anımsatıcı kullanıcılara sunulan*.  
- **Windows başvuru belgeleri**: [Güncelleştirme/ScheduleImminentRestartWarning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduleimminentrestartwarning) 

Yeniden hakkında cihaz kullanıcısına kapatılabilen olmayan bir uyarı görüntülenecek belirtin'de otomatik yeniden başlatma öncesinde bu seçeneği belirtin. Değerleri **15**, **30** veya **60** dakika desteklenir.  

### <a name="windows-update-notification-level"></a>Windows güncelleştirme bildirim düzeyi  
- **Varsayılan**: Varsayılan Windows güncelleştirme bildirimleri kullanma 
- **Windows başvuru belgeleri**: [Güncelleştirme/UpdateNotificationLevel](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updatenotificationlevel)

Windows güncelleştirme bildirimleri bkz düzeyini belirtin. Bu ayar, nasıl ve ne zaman güncelleştirmeleri indirilip yüklendiği denetlemez.

### <a name="allow-user-to-restart-engaged-restart"></a>(Meşgul yeniden) izin ver  

- **Varsayılan**: Yapılandırılmamış  
- **Windows başvuru belgeleri**: *Uygulanamaz*  
- **Windows sürümü**: Windows 10 sürüm 1803 ve üzeri için desteklenir  

  > [!NOTE]  
  > Windows 10 sürüm 1809 ayrı ayarların özellik ve kalite güncelleştirmeleri uygulanmasını sağlayan ek katılımcı yeniden başlatma ayarı tanıtıyor. Ancak, Intune tarafından yönetilen ayarları için farklı güncelleştirme türlerinin ayrı olarak uygulanmaz. Bunun yerine, Intune aynı değerleri hem özellik ve kalite güncelleştirmeleri uygular.  

Ayarlandığında **gerekli**, Windows 10 güncelleştirmeleri için katılımcı yeniden başlatma seçeneklerini kullanımını etkinleştirin. Bu seçenekler, ne zaman bir cihazı yeniden başlatma gerektiren bir güncelleştirmeyi yükledikten sonra yeniden yönetmenize yardımcı olmak için bir cihazın kullanıcısı etkileşim kurun.  

Bu seçenek hakkında daha fazla bilgi için bkz. [yeniden gerçekleştiriliyor](https://docs.microsoft.com/windows/deployment/update/waas-restart#engaged-restart) güncelleştirmeleri dağıtmak için Windows 10 belgelerinde.  

Aşağıdaki ayarlar, katılımcı yeniden başlatma eylemleri olduğunda denetlemek için kullanılır.  

- **Sonra otomatik yeniden başlatma bir geçiş katılımcı yeniden kullanıcılara (gün)**  
  - **Varsayılan**:  Varsayılan olarak, bu yapılandırılmamış ancak bir değerden destekler **2** için **30**.  
  - **Windows başvuru belgeleri**: [Güncelleştirme/EngagedRestartTransitionSchedule](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-engagedrestarttransitionschedule)  
  Cihaz girene kadar güncelleştirme yüklendikten sonra ne kadar meşgul davranışı yeniden belirtin. Yapılandırılan gün sayısının sonra kullanıcılar, cihazı yeniden başlatmak için bir istem alır.  

- **Erteleme katılımcı yeniden anımsatıcı (gün)**  
  - **Varsayılan**:  Bu ayar varsayılan olarak yapılandırılmamış ancak bir değerden destekler **1** için **3**.  
  - **Windows başvuru belgeleri**: [Güncelleştirme/EngagedRestartSnoozeSchedule](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-engagedrestartsnoozeschedule)  
  İçin ne kadar yeniden istemi ertelenemedi belirtin.  Bir erteleme döneminden sonra yeniden başlatma isteğini yeniden sunulur. Kullanıcı, yükleme son tarihine ulaşıldıktan kadar anımsatıcı uykuda devam edebilirsiniz.  

- **Bekleyen için son tarih Ayarla (gün) yeniden başlatır**  
  - **Varsayılan**:  Bu ayar varsayılan olarak yapılandırılmamış ancak bir değerden destekler **2** için **30**.  
  - **Windows başvuru belgeleri**: [Güncelleştirme/EngagedRestartDeadline](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-engagedrestartdeadline)  
  Bir cihazı yeniden başlatma gerektiğinde uygulamadan önce en fazla bir katılımcı davranışı yeniden başlattıktan sonra beklenecek gün sayısı başlar belirtin. Bu yeniden başlatma çalışmalarını kaydetmeleri için kullanıcılara ister.

### <a name="delivery-optimization-download-mode"></a>Teslim iyileştirme indirme modu  

Teslim iyileştirme, artık bir Windows 10 güncelleştirme halkası yazılım güncelleştirmelerini altında bir parçası olarak yapılandırılır. Teslim iyileştirme artık cihaz yapılandırması ayarlanır. Ancak, önceki yapılandırmaların konsolda kullanılabilir kalır. Olmalarını düzenleyerek bu önceki yapılandırmaları kaldırabilirsiniz *yapılandırılmadı*, ancak Aksi halde değiştirilemez. 

Yeni ve eski İlkesi arasındaki çakışmaları önlemek için bkz: [mevcut güncelleştirme halkaları için teslim iyileştirme taşıma](delivery-optimization-windows.md#move-existing-update-rings-to-delivery-optimization) ve ardından ayarlarınızı bir teslim iyileştirme profiline taşıyın.
