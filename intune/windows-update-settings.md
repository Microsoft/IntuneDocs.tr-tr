---
title: Microsoft Intune için Windows for Business güncelleştirme ayarları-Azure | Microsoft Docs
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
ms.openlocfilehash: 9e9baf3593883cf2fa2402a0b4daec638a336366
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2019
ms.locfileid: "67884205"
---
# <a name="windows-update-settings-for-intune"></a>Intune için Windows Update ayarları  

Microsoft Intune ile [yapılandırabileceğiniz ve yönetebileceğiniz](windows-update-for-business-configure.md) Windows 10 güncelleştirme ayarlarını görüntüleyin.  

Intune 'da Windows 10 güncelleştirme halkaları için ayarları yapılandırdığınızda Windows Update ayarlarını yapılandırıyorsunuz. Bir Windows Update ayarında Windows 10 sürüm bağımlılığı varsa, ayarlar ayrıntıları ' nda sürüm bağımlılığı belirtilir.  

## <a name="update-settings"></a>Güncelleştirme ayarları  

Güncelleştirme ayarları, bir cihazın indirileceği bitleri ve ne zaman yapılacağını denetler. Her ayarın davranışı hakkında daha fazla bilgi için, Windows başvuru belgelerine bakın.  

### <a name="servicing-channel"></a>Bakım kanalı  

- **Varsayılan**: Yarı yıllık kanal (hedefli)  
- **Windows başvuru belgeleri**: [Güncelleştirme/Şubereadinesslevel](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-branchreadinesslevel)  
Cihazın Windows güncelleştirmelerini alacağı kanalı (dalı) ayarlayın. Farklı kanallar, güncelleştirmeler teslim edilmeden önce farklı erteleme dönemleri kullanabilir.  

Örneğin, *yarı yıllık kanal* altı aylık bir erteleme içerir. Bu kanalı bu ayarların bu gövdesinden ek bir erteleme olmadan kullanırsanız, cihaz, sürümünden sonra altı ay güncelleştirme yapar.  

Desteklenen güncelleştirme kanalları:  

- Yarı yıllık Kanal  
- Yarı yıllık kanal (hedefli)  
- Windows Insider – hızlı  
- Windows Insider – yavaş  
- Windows Insider Yayımlama  

Bir Insider kanalı seçerseniz, Intune, Insider Build 'ın çalışması için [Update/Managepreview derlemelerini](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-managepreviewbuilds) Windows güncelleştirme ayarını otomatik olarak yapılandırır.  


> [!IMPORTANT]  
> Windows sürüm 1903 ' den başlayarak, *yarı yıllık kanal (hedefli)* (sac-T) kullanımı kullanımdan kaldırıldı. Bu değişiklik ile SAC-T *yarı yıllık kanalla*birleştirir. Bu değişiklik hakkında daha fazla bilgi edinmek ve BT 'nin Iş Windows Update nasıl etkilediği hakkında daha fazla bilgi edinmek için, Iş için Windows IT Pro blog gönderisine [Windows Update ve sac-T](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/Windows-Update-for-Business-and-the-retirement-of-SAC-T/ba-p/339523)' i emeklikten
 


### <a name="microsoft-product-updates"></a>Microsoft ürün güncelleştirmeleri  

- **Varsayılan**:  Allow
- **Windows başvuru belgeleri**: [Güncelleştirme/AllowMUUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowmuupdateservice)

Microsoft Update uygulama güncelleştirmeleri için taramaya *Izin ver* ' i seçin.    

### <a name="windows-drivers"></a>Windows sürücüleri  

- **Varsayılan**:  Allow
- **Windows başvuru belgeleri**: [Güncelleştirme/ExcludeWUDriversInQualityUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-excludewudriversinqualityupdate)

Güncelleştirmeler sırasında Windows Update sürücülerini dahil etmek için *Izin ver* ' i seçin

### <a name="quality-update-deferral-period-days"></a>Kalite güncelleştirmesi erteleme süresi (gün)  

- **Varsayılan**: 0  
- **Windows başvuru belgeleri**: [Güncelleştirme/DeferQualityUpdatesPeriodInDays](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-deferqualityupdatesperiodindays)  

Kalite güncelleştirmelerinin ertelenmesi için 0 ile 30 arasında gün sayısını belirtin. Bu süre, seçtiğiniz hizmet kanalının bir parçası olan herhangi bir erteleme dönemine ek olarak yapılır. Erteleme süresi, ilke cihaz tarafından alındığında başlar.  

Kalite güncelleştirmeleri, genellikle mevcut Windows işlevselliğine yönelik düzeltmeler ve geliştirmelerdir.  

### <a name="feature-update-deferral-period-days"></a>Özellik Güncelleştirmesi erteleme süresi (gün)  

- **Varsayılan**: 0  
- **Windows başvuru belgeleri**: [Güncelleştirme/PauseFeatureUpdatesPeriodInDays](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-deferfeatureupdatesperiodindays)  

Özellik güncelleştirmelerinin ertelenmesi gereken gün sayısını belirtin. Bu süre, seçtiğiniz hizmet kanalının bir parçası olan herhangi bir erteleme dönemine ek olarak yapılır. Erteleme süresi, ilke cihaz tarafından alındığında başlar.  
Desteklenen erteleme dönemi:  

- *Windows sürüm 1709 veya üzeri*: 0-365 gün  
- *Windows sürüm 1703*:  0-180 gün  

Özellik Güncelleştirmeleri genellikle Windows’un yeni özellikleridir.  

### <a name="set-feature-update-uninstall-period-2--60-days"></a>Özellik güncelleştirmesini kaldırma süresini ayarla (2 – 60 gün)  

- **Varsayılan**: 10  
- **Windows başvuru belgeleri**:  [Update/ConfigureFeatureUpdateUninstallPeriod](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-configurefeatureupdateuninstallperiod)  

Özellik güncelleştirmelerinin kaldırılması için bir saat yapılandırın.  

Bu sürenin süresi dolduktan sonra, önceki güncelleştirme bitleri cihazdan kaldırılır ve daha önceki bir güncelleştirme sürümüne kaldıramazlar.  

Örneğin, özellik güncelleştirme kaldırma süresi 20 gün olan bir güncelleştirme halkasını düşünün. 25 gün sonra en son özellik güncelleştirmesini geri alma ve kaldırma seçeneğini kullanma kararı verirsiniz.  Özellik güncelleştirmesini 20 gün önce yükleyen cihazlar, bakımın bir parçası olarak gerekli bitleri kaldırdıklarından bu sürümü kaldıramıyor. Ancak, yalnızca 19 güne kadar olan özellik güncelleştirmesini yükleyen cihazlar, 20 günlük kaldırma dönemini aşmadan önce Uninstall komutunu almak üzere iade ederseniz güncelleştirmeyi kaldırabilir.  


## <a name="user-experience-settings"></a>Kullanıcı deneyimi ayarları  

Kullanıcı deneyimi ayarları, cihaz yeniden başlatma ve anımsatıcıları için son kullanıcı deneyimini denetler. Her ayarın davranışı hakkında daha fazla bilgi için, Windows başvuru belgelerine bakın.  

### <a name="automatic-update-behavior"></a>Otomatik Güncelleştirme davranışı  

- **Varsayılan**: Zamanlanan saatte otomatik olarak yükleyip yeniden başlatın  
- **Windows başvuru belgeleri**: [Güncelleştirme/Allowotomatik güncelleştirme](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)  

Otomatik güncelleştirmelerin nasıl yükleneceğini ve gerekirse cihazın ne zaman yeniden başlatılması gerektiğini seçin.  

Aşağıdaki desteklenen seçeneklerin tam olarak açıklanması için Windows başvuru belgelerine başvurun:  

- **Indirmeyi bildir** – güncelleştirmeyi indirmeden önce kullanıcıya bildirin. Kullanıcılar güncelleştirmeleri indirip yüklemeyi seçer.  

- **Bakım zamanında otomatik olarak yükle** – güncelleştirmeler otomatik olarak indirilir ve cihaz kullanımda olmadığında veya pil gücüyle çalışırken otomatik bakım sırasında yüklenir. Yeniden başlatma gerekli olduğunda, kullanıcılardan yedi güne kadar yeniden başlatılması istenir ve sonra yeniden başlatma zorlanır.  

  Bu seçenek, güncelleştirme yüklendikten sonra bir aygıtı otomatik olarak yeniden başlatabilir. Otomatik yeniden başlatmalarının engellendiği bir dönem tanımlamak için **etkin saatler** ayarlarını kullanın:  

  - **Etkin saatler başlangıç**: Güncelleştirme yüklemeleri nedeniyle yeniden başlatmaları gizleme için bir başlangıç saati belirtin.  
    **Windows başvuru belgeleri**:  [Güncelleştirme/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)  
    **Varsayılan**: 8 ÖÖ  
  
  - **Etkin saatler sonu**: Güncelleştirme yüklemeleri nedeniyle yeniden başlatmaları gizleme için bir bitiş saati belirtin.  
    **Windows başvuru belgeleri**:  [Güncelleştirme/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)  
    **Varsayılan**: 5 PM  

- **Bakım zamanında otomatik olarak yükle ve yeniden Başlat** -güncelleştirmeler otomatik olarak indirilir ve cihaz kullanımda olmadığında veya pil gücüyle çalışırken otomatik bakım sırasında yüklenir. Yeniden başlatma gerektiğinde cihaz, kullanılmayacağı zaman yeniden başlatılır. (Bu, yönetilmeyen cihazlar için varsayılandır.)  

  Bu seçenek, güncelleştirme yüklendikten sonra bir aygıtı otomatik olarak yeniden başlatabilir. **Etkin saatler** ayarlarının kullanılması Windows Update ayarlarda açıklanmamıştır, ancak Intune tarafından otomatik yeniden başlatmalarının engellendiği bir dönem tanımlamak için kullanılır:  

  - **Etkin saatler başlangıç**: Güncelleştirme yüklemeleri nedeniyle yeniden başlatmaları gizleme için bir başlangıç saati belirtin.  
    **Windows başvuru belgeleri**:  [Güncelleştirme/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)  
    **Varsayılan**: 8 ÖÖ  

  - **Etkin saatler sonu**: Güncelleştirme yüklemeleri nedeniyle yeniden başlatmaları gizleme için bir bitiş saati belirtin.  
    **Windows başvuru belgeleri**:  [Güncelleştirme/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)  
    **Varsayılan**: 5 PM  

- **Zamanlanan saatte otomatik olarak yükleme ve yeniden başlatma** – bir yükleme günü ve saati belirtin. Belirtilmemişse, yükleme 3 ' te günlük olarak çalışır ve ardından yeniden başlatmaya 15 dakikalık bir geri sayım gelir. Oturum açan kullanımlar geri sayıma erteleyebilir ve yeniden başlatılabilir.  
  
  Bu seçenek ek ayarları destekler.  
  **Windows başvuru belgeleri**:  [Güncelleştirme/Allowotomatik güncelleştirme](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)  

  - **Otomatik davranış sıklığı**: Bu ayarı kullanarak güncelleştirmelerin yüklenmesini hafta, gün ve saat olarak zamanlayın.  
    **Varsayılan**: Her hafta

  - **Zamanlanan yüklemenin günü**:  Güncelleştirmelerin hangi güne yüklenmesini istediğinizi belirtin.  
    **Varsayılan**: Herhangi bir gün  

  - **Zamanlanan yüklemesi saati**:  Güncelleştirmelerin yüklenmesini istediğiniz günün saatini belirtin.  
    **Varsayılan**: 3 HAR  

- **Son Kullanıcı denetimi olmadan otomatik olarak yükle ve yeniden Başlat** – güncelleştirmeler otomatik olarak indirilir ve cihaz kullanımda olmadığında veya pil gücüyle çalışırken otomatik bakım sırasında yüklenir. Yeniden başlatma gerektiğinde cihaz, kullanılmayacağı zaman yeniden başlatılır. Bu seçenek, son kullanıcılar denetim bölmesini salt okunurdur olarak ayarlar.  

- **Varsayılana sıfırla** -Ekim 2018 güncelleştirme veya sonrasını çalıştıran Windows 10 makinelerinde özgün otomatik güncelleştirme ayarlarını geri yükleyin.  


### <a name="restart-checks"></a>Yeniden başlatma denetimleri  

- **Varsayılan**: Allow  
- **Windows başvuru belgeleri**: [Güncelleştirme/SetEDURestart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setedurestart)  

Bu ayarın, Windows 'un cihazlar sürümüne bağlı olarak farklı sonuçları vardır:  

- Windows sürüm 1703 ve öncesi: Bir cihazı yeniden başlattığınızda ortaya çıkan bazı denetimler vardır; örneğin etkin kullanıcı, pil düzeyi, çalışan oyunlar vb. Cihazı yeniden başlattığınızda bu denetimleri atlamak için **Atla**’yı seçin.  
- Windows sürüm 1709 ' den başlayarak: Etkin saatler sırasında şu süreçler güncelleştirmeler için çalıştırılmaz: tarama, indirme, yükleme ve yeniden başlatma. Etkin saatten sonra, güncelleştirme işlemi çalıştırılır ve cihaz, pil denetimleri ve güç denetimleri başarılı olduğu sürece cihazı uykudan uyandırabilirler, indirebilir, yükleyebilir, yükleyebilir ve yeniden başlatabilirsiniz. Daha fazla bilgi için bkz. [Update/SetEDURestart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setedurestart).  

### <a name="block-user-from-pausing-windows-updates"></a>Kullanıcının Windows güncelleştirmelerini duraklatmasını engelle  

- **Varsayılan**: Allow  
- **Windows başvuru belgeleri**: [Güncelleştirme/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)  

Bir cihaz kullanıcısının bir güncelleştirmenin yüklenmesini duraklatmasına izin verin veya engelleyin. 

### <a name="block-user-from-scanning-for-windows-updates"></a>Kullanıcının Windows güncelleştirmelerini taramasını engelle  
- **Varsayılan**: Allow
- **Windows başvuru belgeleri**: [Güncelleştirme/SetDisableUXWUAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisableuxwuaccess) 

Kullanıcının Windows Update tarama erişimine izin verilip verilmeyeceğini belirtir. Örneğin, bir *blok*yapılandırırsanız, kullanıcılar Windows Update tarama, indirme ve yükleme özelliklerine erişemez.  

### <a name="require-users-approval-to-restart-outside-of-work-hours"></a>İş saatleri dışında yeniden başlatma için kullanıcının onayını iste  

- **Varsayılan**: Yapılandırılmamış  
- **Windows başvuru belgeleri**: [Güncelleştirme/AutoRestartRequiredNotificationDismissal](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-autorestartrequirednotificationdismissal)
  
Bir kullanıcının, çalışma saatleri dışında bir cihaz yeniden başlatmasını onayladığından emin olmak için *gerekli* ' yi seçin.  
   
### <a name="remind-user-prior-to-required-auto-restart-with-dismissible-reminder-hours"></a>Kullanıcıyı, kabul edilebilir anımsatıcı (saatler) ile gerekli otomatik yeniden başlatmadan önce hatırlat  

- **Varsayılan**: *Bu ayar varsayılan olarak yapılandırılmaz ve kullanıcılara hiçbir anımsatıcı sunulmaz*.  
- **Windows başvuru belgeleri**: [Güncelleştirme/ScheduleRestartWarning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-schedulerestartwarning)  

Bir otomatik yeniden başlatmanın ne kadar ilerlemek üzere bir cihaz kullanıcısına bu yeniden başlatma ile ilgili bir bildirimi görüntüleme süresini belirtin. **2**, **4**, **8**, **12**veya **24** saatlik değerler desteklenir.  

### <a name="remind-user-prior-to-required-auto-restart-with-permanent-reminder-minutes"></a>Kalıcı anımsatıcı ile kullanıcıyı gerekli otomatik yeniden başlatmadan önce hatırlat (dakika)  

- **Varsayılan**: *Bu ayar varsayılan olarak yapılandırılmaz ve kullanıcılara hiçbir anımsatıcı sunulmaz*.  
- **Windows başvuru belgeleri**: [Güncelleştirme/ScheduleImminentRestartWarning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduleimminentrestartwarning) 

Bir otomatik yeniden başlatmanın ne kadar ilerlecereceğine ilişkin bir cihaz kullanıcısına, bu yeniden başlatma ile ilgili olmayan bir uyarının nasıl görüntüleneceğini belirtin. **15**, **30** veya **60** dakikalık değerler desteklenir.  

### <a name="windows-update-notification-level"></a>Windows Update bildirim düzeyi  
- **Varsayılan**: Varsayılan Windows Update bildirimlerini kullan 
- **Windows başvuru belgeleri**: [Güncelleştirme/UpdateNotificationLevel](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updatenotificationlevel)

Kullanıcıların göreceği Windows Update bildirimi düzeyini belirtin. Bu ayar güncelleştirmelerin nasıl ve ne zaman indirildiğini ve yüklendiğini denetlemez.

### <a name="allow-user-to-restart-engaged-restart"></a>Kullanıcının yeniden başlatılmasına izin ver (bağlı yeniden başlatma)  

- **Varsayılan**: Yapılandırılmamış  
- **Windows başvuru belgeleri**: *Uygulanamaz*  
- **Windows sürümü**: Windows 10 sürüm 1803 ve üzeri için desteklenir  

  > [!NOTE]  
  > Windows 10 sürüm 1809, özellik ve kalite güncelleştirmelerine ayrı ayarların uygulanmasını sağlayan, ek olarak kullanılabilir yeniden başlatma ayarları sunar. Ancak, Intune tarafından yönetilen ayarlar farklı güncelleştirme türlerine ayrı olarak uygulanmaz. Bunun yerine, Intune aynı değerleri özellik ve kalite güncelleştirmelerine uygular.  

**Gerekli**olarak ayarlandığında, Windows 10 güncelleştirmeleri için etkin yeniden başlatma seçeneklerinin kullanımını etkinleştirirsiniz. Bu seçenekler, bir cihazın yeniden başlatılmasını gerektiren bir güncelleştirme yükledikten sonra cihazın ne zaman yeniden başlatılmasının yönetilmesine yardımcı olmak için bir cihazın kullanıcısını devreye sok.  

Bu seçenek hakkında daha fazla bilgi için bkz. güncelleştirmeleri dağıtmak için Windows 10 belgelerinde [bağlı yeniden başlatma](https://docs.microsoft.com/windows/deployment/update/waas-restart#engaged-restart) .  

Aşağıdaki ayarlar, ne zaman yeniden başlatma eylemlerinin gerçekleşeceğini denetlemek için kullanılır.  

- **Otomatik yeniden başlatmadan sonra kullanıcılara Kullanıcı tarafından yeniden başlatma için geçiş yapın (gün)**  
  - **Varsayılan**:  Varsayılan olarak, bu yapılandırılmaz ancak **2** ile **30**arasında bir değer destekler.  
  - **Windows başvuru belgeleri**: [Güncelleştirme/EngagedRestartTransitionSchedule](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-engagedrestarttransitionschedule)  
  Cihaz, boşta yeniden başlatma davranışına girene kadar güncelleştirmenin ne kadar süre sonra yükleneceğini belirtin. Yapılandırılan gün sayısından sonra, kullanıcılar cihazı yeniden başlatmak için bir istem alır.  

- **Yeniden başlatma için yeniden başlatma anımsatıcısı (gün)**  
  - **Varsayılan**:  Varsayılan olarak, bu ayar yapılandırılmaz ancak **1** ile **3**arasında bir değeri destekler.  
  - **Windows başvuru belgeleri**: [Güncelleştirme/EngagedRestartSnoozeSchedule](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-engagedrestartsnoozeschedule)  
  Yeniden başlatma isteminin ne kadar süreyle ertelendi olabilir.  Erteleme süresinden sonra yeniden başlatma istemi tekrar sunulur. Kullanıcı, yükleme son tarihine ulaşıncaya kadar anımsatıcıyı geri almaya devam edebilir.  

- **Bekleyen yeniden başlatmalar için son tarihi ayarla (gün)**  
  - **Varsayılan**:  Varsayılan olarak, bu ayar yapılandırılmaz ancak **2** ile **30**arasında bir değer destekler.  
  - **Windows başvuru belgeleri**: [Güncelleştirme/EngagedRestartDeadline](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-engagedrestartdeadline)  
  Bir cihaz gerekli yeniden başlatmayı zorunlu yapmadan önce, boşta yeniden başlatma davranışı başladıktan sonra beklenecek en fazla gün sayısını belirtin. Bu yeniden başlatma, kullanıcılardan işlerini kaydetmesini ister.

### <a name="delivery-optimization-download-mode"></a>Teslim iyileştirme indirme modu  

Teslim iyileştirme artık yazılım güncelleştirmeleri kapsamında bir Windows 10 güncelleştirme halkası 'nin parçası olarak yapılandırılmamıştır. Teslim iyileştirme artık cihaz yapılandırması ile ayarlanır. Ancak, önceki yapılandırma konsolunda kullanılabilir kalır. Bu önceki konfigürasyonları, *Yapılandırılmadı*olarak düzenleyerek kaldırabilirsiniz, ancak başka bir şekilde değiştirilemez. 

Yeni ve eski ilke arasındaki çakışmaları önlemek için bkz. [var olan güncelleştirme halkalarından teslim Iyileştirmeye geçme](delivery-optimization-windows.md#move-existing-update-rings-to-delivery-optimization) ve sonra ayarlarınızı bir teslim iyileştirme profiline taşıma.
