---
title: Microsoft Intune için Windows for Business güncelleştirme ayarları-Azure | Microsoft Docs
description: Intune kullanarak dağıtabileceğiniz Windows 10 cihazları için WUfB ayarları.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 08/15/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: aiwang
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: f9882328efa2ddc5a6c5d6924fe15176e50b7837
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72508711"
---
# <a name="windows-update-settings-for-intune"></a>Intune için Windows Update ayarları  

Microsoft Intune ile [yapılandırabileceğiniz ve yönetebileceğiniz](windows-update-for-business-configure.md) Windows 10 güncelleştirme ayarlarını görüntüleyin.  

Intune 'da Windows 10 güncelleştirme halkaları için ayarları yapılandırdığınızda Windows Update ayarlarını yapılandırıyorsunuz. Bir Windows Update ayarında Windows 10 sürüm bağımlılığı varsa, ayarlar ayrıntıları ' nda sürüm bağımlılığı belirtilir.  

## <a name="update-settings"></a>Güncelleştirme ayarları  

Güncelleştirme ayarları, bir cihazın indirileceği bitleri ve ne zaman yapılacağını denetler. Her ayarın davranışı hakkında daha fazla bilgi için, Windows başvuru belgelerine bakın.  

- **Hizmet kanalı**  
  **Varsayılan**: yarı yıllık Kanal  
  Windows Update CSP: [Update/BranchReadinessLevel](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-branchreadinesslevel)  

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
  > Windows sürüm 1903 ' den başlayarak, *yarı yıllık kanal (hedefli)* (sac-T) kullanımı kullanımdan kaldırıldı. Bu değişiklik ile SAC-T *yarı yıllık kanalla*birleştirir. Bu değişiklik hakkında daha fazla bilgi edinmek ve BT 'nin Iş Windows Update nasıl etkilediği hakkında daha fazla bilgi edinmek için, Iş için Windows IT Pro blog gönderisine [Windows Update ve sac-T ' i emeklikten](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/Windows-Update-for-Business-and-the-retirement-of-SAC-T/ba-p/339523)  
 
- **Microsoft ürün güncelleştirmeleri**  
  **Varsayılan**: izin ver  
  Windows Update CSP: [Update/AllowMUUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowmuupdateservice)

  - **Izin ver** -Microsoft Update uygulama güncelleştirmelerini taramaya *izin ver* ' i seçin.  
  - **Engelle** -uygulama güncelleştirmelerinin taranmasını engellemek için blok ' ı seçin.  

- **Windows sürücüleri**  
  **Varsayılan**: izin ver  
  Windows Update CSP: [Update/ExcludeWUDriversInQualityUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-excludewudriversinqualityupdate)  

  - **Izin ver** -seçme *izin ver* seçeneği, güncelleştirmeler sırasında Windows Update sürücüleri içerir.  
  - **Engelle** -sürücülerin taranmasını engellemek için blok ' ı seçin.  

- **Kalite güncelleştirmesi erteleme süresi (gün)**  
  **Varsayılan**: 0  
  Windows Update CSP: [Update/DeferQualityUpdatesPeriodInDays](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-deferqualityupdatesperiodindays)  

  Kalite güncelleştirmelerinin ertelenmesi için 0 ile 30 arasında gün sayısını belirtin. Bu süre, seçtiğiniz hizmet kanalının bir parçası olan herhangi bir erteleme dönemine ek olarak yapılır. Erteleme süresi, ilke cihaz tarafından alındığında başlar.  

  Kalite güncelleştirmeleri, genellikle mevcut Windows işlevselliğine yönelik düzeltmeler ve geliştirmelerdir.  

- **Özellik Güncelleştirmesi erteleme süresi (gün)**  
  **Varsayılan**: 0  
  Windows Update CSP: [Update/PauseFeatureUpdatesPeriodInDays](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-deferfeatureupdatesperiodindays)  

  Özellik güncelleştirmelerinin ertelenmesi gereken gün sayısını belirtin. Bu süre, seçtiğiniz hizmet kanalının bir parçası olan herhangi bir erteleme dönemine ek olarak yapılır. Erteleme süresi, ilke cihaz tarafından alındığında başlar.  

  Desteklenen erteleme dönemi:  

  - *Windows sürüm 1709 ve üzeri* -0-365 gün  
  - *Windows sürüm 1703* -0-180 gün  

  Özellik Güncelleştirmeleri genellikle Windows’un yeni özellikleridir.  

- **Özellik güncelleştirmesini kaldırma süresini ayarla (2 – 60 gün)**  
  **Varsayılan**: 10  
  Windows Update CSP: [Update/ConfigureFeatureUpdateUninstallPeriod](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-configurefeatureupdateuninstallperiod)  

  Özellik güncelleştirmelerinin kaldırılması için bir saat yapılandırın.  

  Bu sürenin süresi dolduktan sonra, önceki güncelleştirme bitleri cihazdan kaldırılır ve daha önceki bir güncelleştirme sürümüne kaldıramazlar.  

  Örneğin, özellik güncelleştirme kaldırma süresi 20 gün olan bir güncelleştirme halkasını düşünün. 25 gün sonra en son özellik güncelleştirmesini geri alma ve kaldırma seçeneğini kullanma kararı verirsiniz.  Özellik güncelleştirmesini 20 gün önce yükleyen cihazlar, bakımın bir parçası olarak gerekli bitleri kaldırdıklarından bu sürümü kaldıramıyor. Ancak, yalnızca 19 güne kadar olan özellik güncelleştirmesini yükleyen cihazlar, 20 günlük kaldırma dönemini aşmadan önce Uninstall komutunu almak üzere iade ederseniz güncelleştirmeyi kaldırabilir.  

## <a name="user-experience-settings"></a>Kullanıcı deneyimi ayarları  

Kullanıcı deneyimi ayarları, cihaz yeniden başlatma ve anımsatıcıları için son kullanıcı deneyimini denetler. Her ayarın davranışı hakkında daha fazla bilgi için Windows Update CSP belgelerine bakın.  

- **Otomatik güncelleştirme davranışı**  
  **Varsayılan**: bakım zamanında otomatik olarak yüklenir  
  Windows Update CSP: [güncelleştirme/Allowotomatik güncelleştirme](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)  

  Otomatik güncelleştirmelerin nasıl yükleneceğini ve gerekirse cihazın ne zaman yeniden başlatılması gerektiğini seçin.  

  Desteklenen seçenekler:  

  - **Indirmeyi bildir** -güncelleştirmeyi indirmeden önce kullanıcıya bildirin. Kullanıcılar güncelleştirmeleri indirip yüklemeyi seçer.  

  - **Bakım zamanında otomatik olarak yükle** -güncelleştirmeler otomatik olarak indirilir ve cihaz kullanımda olmadığında veya pil gücüyle çalışırken otomatik bakım sırasında yüklenir. Yeniden başlatma gerekli olduğunda, kullanıcılardan yedi güne kadar yeniden başlatılması istenir ve sonra yeniden başlatma zorlanır.  

    Bu seçenek, güncelleştirme yüklendikten sonra bir aygıtı otomatik olarak yeniden başlatabilir. Otomatik yeniden başlatmalarının engellendiği bir dönem tanımlamak için **etkin saatler** ayarlarını kullanın:  

    - **Etkin saatler başlangıcı** -güncelleştirme yüklemeleri nedeniyle yeniden başlatma işlemlerini gizleme için bir başlangıç saati belirtin.  
      **Varsayılan**: 8 ÖÖ  
      Windows Update CSP: [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)  
  
    - **Etkin saatler bitiş** -güncelleştirme yüklemeleri nedeniyle yeniden başlatmaları gizleme için bitiş saati belirtin.  
      **Varsayılan**: 5 pm  
      Windows Update CSP: [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)  

  - **Bakım zamanında otomatik olarak yükle ve yeniden Başlat** -güncelleştirmeler otomatik olarak indirilir ve cihaz kullanımda olmadığında veya pil gücüyle çalışırken otomatik bakım sırasında yüklenir. Yeniden başlatma gerektiğinde cihaz, kullanılmayacağı zaman yeniden başlatılır. (Bu, yönetilmeyen cihazlar için varsayılandır.)  

    Bu seçenek, güncelleştirme yüklendikten sonra bir aygıtı otomatik olarak yeniden başlatabilir. **Etkin saatler** ayarlarının kullanılması Windows Update ayarlarda açıklanmamıştır, ancak Intune tarafından otomatik yeniden başlatmalarının engellendiği bir dönem tanımlamak için kullanılır:  

    - **Etkin saatler başlangıcı** -güncelleştirme yüklemeleri nedeniyle yeniden başlatma işlemlerini gizleme için bir başlangıç saati belirtin.  
      **Varsayılan**: 8 ÖÖ  
      Windows Update CSP: [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)  
  
    - **Etkin saatler bitiş** -güncelleştirme yüklemeleri nedeniyle yeniden başlatmaları gizleme için bitiş saati belirtin.  
      **Varsayılan**: 5 pm  
      Windows Update CSP: [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)  

  - **Zamanlanan saatte otomatik olarak yükleme ve yeniden başlatma** -yükleme gününü ve saatini belirtin. Belirtilmemişse, yükleme 3 ' te günlük olarak çalışır ve ardından yeniden başlatmaya 15 dakikalık bir geri sayım gelir. Oturum açan kullanımlar geri sayıma erteleyebilir ve yeniden başlatılabilir.   
  Windows Update CSP: [güncelleştirme/Allowotomatik güncelleştirme](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)  

    Bu seçenek ek ayarları destekler.  

    - **Otomatik davranış sıklığı** -bu ayarı, güncelleştirmelerin ne zaman yükleneceğini, hafta, gün ve saat dahil olduğunu zamanlamak için kullanın.  
      **Varsayılan**: her hafta

    - **Zamanlanan yüklemesi günü** -güncelleştirmelerin hangi güne yüklenmesini istediğinizi belirtin.  
      **Varsayılan**: herhangi bir gün  

    - **Zamanlanan yüklemesi süresi** -güncelleştirmelerin yüklenmesini istediğiniz saati belirtin.  
      **Varsayılan**: 3 ÖÖ  

  - **Son Kullanıcı denetimi olmadan otomatik olarak yükle ve yeniden Başlat** -güncelleştirmeler otomatik olarak indirilir ve cihaz kullanımda olmadığında veya pil gücüyle çalışırken otomatik bakım sırasında yüklenir. Yeniden başlatma gerektiğinde cihaz, kullanılmayacağı zaman yeniden başlatılır. Bu seçenek, son kullanıcılar denetim bölmesini salt okunurdur olarak ayarlar.  

  - **Varsayılana sıfırla** -Ekim 2018 güncelleştirme veya sonrasını çalıştıran Windows 10 makinelerinde özgün otomatik güncelleştirme ayarlarını geri yükleyin.  


- **Yeniden başlatma denetimleri**  
  **Varsayılan**: izin ver  
  Windows Update CSP: [Update/SetEDURestart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setedurestart)  

  Cihazı yeniden başlattığınızda bu denetimleri atlamak için **Atla**’yı seçin. 
  
  Bu ayarın, Windows 'un cihazlar sürümüne bağlı olarak farklı sonuçları vardır:  
 
  - *Windows sürüm 1703 ve önceki sürümler* -bir cihazı yeniden başlattığınızda, etkin kullanıcılar, pil düzeyleri, oyunları çalıştırmak ve daha fazlasını denetlemek dahil bazı denetimler vardır.  
  
  - *Windows sürüm 1709 ve üzeri* -etkin saatler sırasında aşağıdaki süreçler güncelleştirmeler için çalıştırılmaz: tarama, indirme, yükleme ve yeniden başlatma. Etkin saatten sonra, güncelleştirme işlemi çalıştırılır ve cihaz, pil denetimleri ve güç denetimleri başarılı olduğu sürece cihazı uykudan uyandırabilirler, indirebilir, yükleyebilir, yükleyebilir ve yeniden başlatabilirsiniz. 

- **Kullanıcının Windows güncelleştirmelerini duraklatmasını engelle**  
  **Varsayılan**: izin ver  
  Windows Update CSP: [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)  

  - **Izin ver** -cihaz kullanıcılarının bir güncelleştirmenin yüklenmesini duraklatmasını sağlar.  
  - **Engelle** -cihaz kullanıcılarının bir güncelleştirmenin yüklenmesini duraklatmasını engeller.  

- **Kullanıcının Windows güncelleştirmelerini taramasını engelle**  
  **Varsayılan**: izin ver  
  Windows Update CSP: [Update/SetDisableUXWUAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisableuxwuaccess) 

  - **Izin ver** -cihaz kullanıcılarının güncelleştirmeleri bulmak ve indirmek için Windows Update taraması kullanmasına izin verin ve özellikleri yükleyin.
  - **Engelle** -cihaz kullanıcılarının Windows Update taramaya erişmesini, güncelleştirmeleri karşıdan yüklemesini ve özellikleri yüklemeyi engeller.  

- **İş saatleri dışında yeniden başlatma için kullanıcının onayını iste**  
  **Varsayılan**: yapılandırılmadı  
  Windows Update CSP: [Update/AutoRestartRequiredNotificationDismissal](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-autorestartrequirednotificationdismissal)
  
  - **Yapılandırılmadı**  
  - **Gerekli** -bir kullanıcının, çalışma saatleri dışında bir cihaz yeniden başlatmasını onayladığından emin olmanız gerekir.  
   
- **Kullanıcıyı, kabul edilebilir anımsatıcı (saatler) ile gerekli otomatik yeniden başlatmadan önce hatırlat**  
  **Varsayılan**: 4  
  Windows Update CSP: [Update/ScheduleRestartWarning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-schedulerestartwarning)  

  Bir otomatik yeniden başlatmanın ne kadar ilerlemek üzere bir cihaz kullanıcısına bu yeniden başlatma ile ilgili bir bildirimi görüntüleme süresini belirtin. **2**, **4**, **8**, **12**veya **24** saatlik değerler desteklenir.  
  
  Varsayılan değeri temizlediğinizde, bu ayar *yapılandırılmaz*.  

- **Kalıcı anımsatıcı ile kullanıcıyı gerekli otomatik yeniden başlatmadan önce hatırlat (dakika)**  
  **Varsayılan**: 15  
  Windows Update CSP: [Update/ScheduleImminentRestartWarning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduleimminentrestartwarning)  

  Bir otomatik yeniden başlatmanın ne kadar ilerlecereceğine ilişkin bir cihaz kullanıcısına, bu yeniden başlatma ile ilgili olmayan bir uyarının nasıl görüntüleneceğini belirtin. **15**, **30** veya **60** dakikalık değerler desteklenir.  

  Varsayılan değeri temizlediğinizde, bu ayar *yapılandırılmaz*.  

- **Güncelleştirme bildirim düzeyini Değiştir**  
  **Varsayılan**: varsayılan Windows Update bildirimleri kullanın  
  Windows Update CSP: [Update/UpdateNotificationLevel](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updatenotificationlevel)
  
  Kullanıcıların göreceği Windows Update bildirimi düzeyini belirtin. Bu ayar güncelleştirmelerin nasıl ve ne zaman indirildiğini ve yüklendiğini denetlemez.  

  Desteklenen seçenekler:
  - **Yapılandırılmadı**
  - **Varsayılan Windows Update bildirimlerini kullan**
  - **Yeniden başlatma uyarılarını hariç tüm bildirimleri kapat**
  - **Yeniden başlatma uyarıları dahil tüm bildirimleri kapat**  

- **Kullanıcının yeniden başlatılmasına izin ver (bağlı yeniden başlatma)**  
  **Varsayılan**: yapılandırılmadı  
  > [!IMPORTANT]  
  > Kullanım için *yeniden başlatma* ayarları artık önerilmez. Bunun yerine, *denetimli yeniden başlatma* ayarlarının yerini aldığı yeni *son tarih* ayarlarını kullanın. Intune, gelecekteki bir güncelleştirmede, [ *denetimli yeniden başlatma* ayarları desteğini kullanımdan](../fundamentals/whats-new.md#plan-for-change-new-windows-updates-settings-in-intune-) kaldırır.

  Windows 10 sürüm 1803 ve üzeri için, Kullanıcı için yeniden başlatma desteklenir. 

  > [!NOTE]  
  > Windows 10 sürüm 1809, özellik ve kalite güncelleştirmelerine ayrı ayarların uygulanmasını sağlayan, ek olarak kullanılabilir yeniden başlatma ayarları sunar. Ancak, Intune tarafından yönetilen ayarlar farklı güncelleştirme türlerine ayrı olarak uygulanmaz. Bunun yerine, Intune aynı değerleri özellik ve kalite güncelleştirmelerine uygular.  
  
  - **Yapılandırılmadı**  
  - **Gerekli** -Windows 10 güncelleştirmeleri için etkin yeniden başlatma seçeneklerinin kullanımını etkinleştirmek için *gerekli* olarak ayarlayın. Bu seçenekler, bir cihazın yeniden başlatılmasını gerektiren bir güncelleştirme yükledikten sonra cihazın ne zaman yeniden başlatılmasının yönetilmesine yardımcı olmak için bir cihazın kullanıcısını devreye sok.  

  Bu seçenek hakkında daha fazla bilgi için bkz. güncelleştirmeleri dağıtmak için Windows 10 belgelerinde [bağlı yeniden başlatma](https://docs.microsoft.com/windows/deployment/update/waas-restart#engaged-restart) .  

  Aşağıdaki ayarlar, ne zaman yeniden başlatma eylemlerinin gerçekleşeceğini denetlemek için kullanılır.  

  - **Otomatik yeniden başlatmadan sonra kullanıcılara Kullanıcı tarafından yeniden başlatma için geçiş yapın (gün)**  
    **Varsayılan**: YAPıLANDıRıLMADı Windows Update CSP: [Update/EngagedRestartTransitionSchedule](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-engagedrestarttransitionschedule)  
    
    Cihaz, boşta yeniden başlatma davranışına girene kadar güncelleştirme yüklendikten sonra **2** ila **30** gün arasında bir değer belirtin. Yapılandırılan gün sayısından sonra, kullanıcılar cihazı yeniden başlatmak için bir istem alır.  

  - **Yeniden başlatma için yeniden başlatma anımsatıcısı (gün)**  
    **Varsayılan**: yapılandırılmadı    
    Windows Update CSP: [Update/EngagedRestartSnoozeSchedule](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-engagedrestartsnoozeschedule)  
    
    Yeniden başlatma isteminin ne kadar süreyle ertelendi olabilir **1** ile **3** arasında bir değer belirtin.  Erteleme süresinden sonra yeniden başlatma istemi tekrar sunulur. Kullanıcı, yükleme son tarihine ulaşıncaya kadar anımsatıcıyı geri almaya devam edebilir.  

  - **Bekleyen yeniden başlatmalar için son tarihi ayarla (gün)**  
    **Varsayılan**: yapılandırılmadı  
    Windows Update CSP: [Update/EngagedRestartDeadline](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-engagedrestartdeadline)  
  
    Bir cihaz gerekli yeniden başlatmayı zorunlu yapmadan önce, boşta yeniden başlatma davranışı başladıktan sonra beklenecek en fazla gün sayısı olarak **2** ile **30 arasında** bir değer belirtin. Bu yeniden başlatma, kullanıcılardan işlerini kaydetmesini ister.

- **Son tarih ayarlarını kullan**  
  **Varsayılan**: yapılandırılmadı  
  > [!IMPORTANT]  
  > Intune için Ağustos güncelleştirmesiyle başlayarak, ara yeniden başlatma ayarlarının yerini alan aşağıdaki son tarih ayarlarını kullanmanızı öneririz. Intune, gelecekteki bir Intune güncelleştirmesinde, BT için [ *yeniden başlatma* ayarlarının desteğini kullanımdan](../fundamentals/whats-new.md#plan-for-change-new-windows-updates-settings-in-intune-) kaldırır.  

  Kullanıcının son tarih ayarlarını kullanmasına izin verir.  

  - **Yapılandırılmadı**
  - **İzin ver**

  *Izin ver*olarak ayarlandığında, son tarihleri için aşağıdaki ayarları yapılandırabilirsiniz:

  - **Özellik güncelleştirmeleri için son tarih**  
    **Varsayılan**: 7  
    Windows Update CSP: [Update/ConfigureDeadlineForFeatureUpdates](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforfeatureupdates)  

    Bir kullanıcının, cihazlarına otomatik olarak yüklenmesi için gereken gün sayısını belirtir (2-30).

  - **Kalite güncelleştirmeleri için son tarih**  
    **Varsayılan**: 7  
    Windows Update CSP: [Update/ConfigureDeadlineForQualityUpdates](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforqualityupdates)

    Bir kullanıcının, kalite güncelleştirmelerinin cihazlarına otomatik olarak yüklenmesi için gereken gün sayısını belirtir (2-30).

  - **Yetkisiz kullanım süresi**  
    **Varsayılan**: 2 Windows Update CSP: [Update/ConfigureDeadlineGracePeriod]( https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-configuredeadlinegraceperiod)

    Yeniden başlatmalar otomatik olarak gerçekleşene kadar geçen en az gün sayısını belirtir (0-7).

  - **Son tarihten önce otomatik yeniden başlatma**  
    **Varsayılan**: Evet Windows Update CSP: [Update/Configuredeadlinenooto reboot](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-configuredeadlinenoautoreboot)

    Cihazın son tarihten önce otomatik olarak yeniden başlatılması gerekip gerekmediğini belirtir.
    - **Yes**
    - **Hayır**




### <a name="delivery-optimization-download-mode"></a>Teslim iyileştirme indirme modu  

Teslim iyileştirme artık yazılım güncelleştirmeleri kapsamında bir Windows 10 güncelleştirme halkası 'nin parçası olarak yapılandırılmamıştır. Teslim iyileştirme artık cihaz yapılandırması ile ayarlanır. Ancak, önceki yapılandırma konsolunda kullanılabilir kalır. Bu önceki konfigürasyonları, *Yapılandırılmadı*olarak düzenleyerek kaldırabilirsiniz, ancak başka bir şekilde değiştirilemez. 

Yeni ve eski ilke arasındaki çakışmaları önlemek için bkz. [var olan güncelleştirme halkalarından teslim Iyileştirmeye geçme](../configuration/delivery-optimization-windows.md#move-existing-update-rings-to-delivery-optimization) ve sonra ayarlarınızı bir teslim iyileştirme profiline taşıma.
