---
title: Uygulama yükleme sorunlarını giderme
titleSuffix: Microsoft Intune
description: Uygulama yükleme sorunlarını gidermenize yardımcı olması için Microsoft Intune sorun giderme bölmesini kullanın.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/04/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: b613f364-0150-401f-b9b8-2b09470b34f4
ms.reviewer: mghadial
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 850c7a28c4df1638e9f635713695dcf2e914ffce
ms.sourcegitcommit: 1494ff4b33c13a87f20e0f3315da79a3567db96e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/20/2019
ms.locfileid: "71166943"
---
# <a name="troubleshoot-app-installation-issues"></a>Uygulama yükleme sorunlarını giderme

Microsoft Intune MDM ile yönetilen cihazlarda bazen uygulama yüklemeleri başarısız olabilir. Bu uygulamaların yüklemesi başarısız olduğunda, başarısızlık sebebini anlamak ve sorunu gidermek zor olabilir. Microsoft Intune, kullanıcı yardım isteklerini ele almak yardım masası operatörleri ve Intune yöneticilerinin uygulama bilgilerini görüntülemek için uygulama yükleme hatası ayrıntıları sağlar. Intune içindeki sorun giderme bölmesi, kullanıcının cihazında yönetilen uygulamalar dahil hata ayrıntılarını sağlar. Bir uygulamanın uçtan uca yaşam döngüsü hakkındaki ayrıntıları, **Yönetilen Uygulamalar** bölmesinde her bir cihaz altında sağlanır. Uygulamanın ne zaman yüklendiği, değiştirildiği, hedeflendiği ve bir cihaza teslim edildiği gibi yükleme sorunlarını görüntüleyebilirsiniz. 

## <a name="app-troubleshooting-details"></a>Uygulama sorunlarını giderme ayrıntıları

Intune, belirli bir kullanıcının cihazında yüklü uygulamalar temelinde sorun giderme ayrıntıları sağlar.

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
3. **Intune** bölmesinde **Sorun gider**’i seçin.
4. Sorun gidermek üzere bir kullanıcı belirlemek için **Seçin**’e tıklayın. **Seçili kullanıcılar** bölmesi görüntülenir.
5. Adını veya e-posta adresini yazarak bir kullanıcı seçin. Bölmenin altındaki **Seçin**’e tıklayın. Kullanıcı için sorun giderme bilgileri, **Sorun Giderme** bölmesinde görüntülenir. 
6. **Cihazlar** listesinden sorun gidermek istediğiniz cihazı seçin.
    ![Intune Sorun Giderme bölmesi.](media/troubleshoot-app-install-01.png)
7. Seçili cihaz bölmesinden **Yönetilen Uygulamalar**’ı seçin. Yönetilen uygulamaların bir listesi görüntülenir.
    ![Intune tarafından yönetilen belirli bir cihazın ayrıntıları.](media/troubleshoot-app-install-02.png)
8. Listeden **Yükleme Durumu**’nun hata gösterdiği bir uygulamayı seçin.
    ![Yükleme hatası ayrıntıları gösteren seçili bir uygulama.](media/troubleshoot-app-install-03.png)

    > [!Note]  
    > Aynı uygulama, birden çok gruba atanabilir ancak uygulama için amaçlanan farklı eylemleri (amaçları) olmalıdır. Örneğin uygulama ataması sırasında bir kullanıcı için uygulama dışlandıysa uygulama için çözümlenen amaç **dışlandı** olarak görüntülenecektir. Daha fazla bilgi için bkz. [Uygulama amaçları arasındaki çakışmalar nasıl çözümlenir](apps-deploy.md#how-conflicts-between-app-intents-are-resolved).<br><br>
    > Gerekli bir uygulama için yükleme hatası oluşursa siz veya yardım masanız tarafından cihaz eşitlenebilir ve uygulama yüklemesi yeniden denenebilir.

Uygulama yükleme hatası ayrıntıları, sorunu gösterecektir. Sorunu çözmek için yapılacak en iyi eylemi belirlemek üzere bu ayrıntıları kullanabilirsiniz. Uygulama yükleme sorunlarını giderme hakkında daha fazla bilgi için bkz. [uygulama yükleme hataları](troubleshoot-app-install.md#app-installation-errors).

> [!Note]  
> **Sorun giderme** bölmesine tarayıcınızı [https://aka.ms/intunetroubleshooting](https://aka.ms/intunetroubleshooting) adresine yönlendirerek de erişebilirsiniz.

## <a name="user-group-targeted-app-installation-does-not-reach-device"></a>Kullanıcı grubu hedeflenen uygulama yüklemesi cihaza ulaşmıyor
Uygulamaları yüklerken sorun yaşadığınızda aşağıdaki eylemler göz önünde bulundurulmalıdır:
- Uygulama Şirket Portalı görünmüyorsa, uygulamanın **kullanılabilir** amaç ile dağıtıldığından ve kullanıcının, uygulama tarafından desteklenen cihaz türüyle Şirket portalı eriştiğinden emin olun.
- Windows BYOD cihazlarında, kullanıcının cihaza bir Iş hesabı eklemesi gerekir.
- Kullanıcının AAD cihaz sınırının üzerinde olup olmadığını denetleyin:
  1. [Azure Active Directory cihaz ayarları](https://portal.azure.com/#blade/Microsoft_AAD_IAM/DevicesMenuBlade/DeviceSettings/menuId)' na gidin.
  2. **Kullanıcı başına en fazla cihaz**için ayarlanan değeri unutmayın.
  3. [Azure Active Directory kullanıcılara](https://portal.azure.com/#blade/Microsoft_AAD_IAM/UsersManagementMenuBlade/AllUsers)gidin.
  4. Etkilenen kullanıcıyı seçin ve **cihazlar**' a tıklayın.
  5. Kullanıcı ayarlanan sınırın üzerinde ise artık gerekli olmayan eski kayıtları silin.
- İOS DEP cihazları için, kullanıcının Intune cihazına genel bakış dikey penceresinde **kayıtlı** olarak listelendiğinden emin olun. Varsa, Intune Şirket Portalı için bir yapılandırma ilkesi dağıtın. Daha fazla bilgi için bkz. [Şirket Portalı uygulamasını yapılandırma](app-configuration-policies-use-ios.md#configure-the-company-portal-app-to-support-ios-dep-devices).

## <a name="win32-app-installation-troubleshooting"></a>Win32 uygulaması yükleme sorunlarını giderme

Intune yönetim uzantısı kullanılarak dağıtılan Win32 uygulamasını seçin. Win32 uygulamanızın yüklemesi başarısız olduğunda **günlükleri topla** seçeneğini belirleyebilirsiniz. 

> [!IMPORTANT]
> Win32 uygulaması cihaza başarıyla yüklendiğinde **günlükleri topla** seçeneği etkinleştirilmeyecektir.<p>Win32 uygulama günlüğü bilgilerini toplayabilmeniz için önce Intune yönetim uzantısının Windows istemcisinde yüklü olması gerekir. Bir PowerShell betiği veya bir Win32 uygulaması bir kullanıcı veya cihaz güvenlik grubuna dağıtıldığında, Intune yönetim uzantısı yüklenir. Daha fazla bilgi için bkz. [Intune yönetim uzantısı-Önkoşullar](intune-management-extension.md#prerequisites).

### <a name="collect-log-file"></a>Günlük dosyası topla

Win32 uygulama yükleme günlüklerinizi toplamak için öncelikle [uygulama sorun giderme ayrıntıları](troubleshoot-app-install.md#app-troubleshooting-details)bölümünde belirtilen adımları izleyin. Ardından, aşağıdaki adımlarla devam edin:

1. **Yükleme ayrıntıları** dikey penceresinde **günlükleri topla** seçeneğine tıklayın.

    <image alt="Win32 app installation details - Collect log option" src="media/troubleshoot-app-install-04.png" width="500" />

2. Günlük dosyası toplama işlemini başlatmak için günlük dosyası adlarıyla dosya yolları sağlayın ve **Tamam**' a tıklayın.
    
    > [!NOTE]
    > Günlük toplama, iki saatten daha az sürer. Desteklenen dosya türleri: *. log,. txt,. dmp,. cab,. zip,. xml,. evtx ve. evtl*. En fazla 25 dosya yoluna izin verilir.

3. Günlük dosyaları toplandıktan sonra günlük dosyalarını indirmek için **Günlükler** bağlantısını seçebilirsiniz.

    <image alt="Win32 app log details - Download logs" src="media/troubleshoot-app-install-05.png" width="500" />

    > [!NOTE]
    > Uygulama günlüğü koleksiyonunun başarısını belirten bir bildirim görüntülenir.

#### <a name="win32-log-collection-requirements"></a>Win32 günlük toplama gereksinimleri

Günlük dosyalarını toplamak için izlenmesi gereken belirli gereksinimler vardır:

- Günlük dosyası yolunun tamamını belirtmeniz gerekir. 
- Günlük toplama için aşağıdaki gibi ortam değişkenlerini belirtebilirsiniz:<br>
  *% PROGRAMFILES%,% PROGRAMDATA%% PUBLIC%,% WINDIR%,% TEMP%,% TMP%*
- Yalnızca tam dosya uzantılarına izin verilir, örneğin:<br>
  *. log,. txt,. dmp,. cab,. zip,. xml*
- Karşıya yüklenecek en fazla günlük dosyası 60 MB veya 25 dosya, hangisi önce gerçekleşir. 
- Win32 uygulama yükleme günlüğü koleksiyonu, gerekli, kullanılabilir ve kaldırma uygulama atama hedefini karşılayan uygulamalar için etkinleştirilir.
- Saklanan Günlükler, günlüklerde yer alan kişisel bilgileri korumak için şifrelenir.
- Win32 uygulama hataları için destek biletlerini açarken, yukarıda belirtilen adımları kullanarak ilgili hata günlüklerini iliştirin.

## <a name="app-installation-errors"></a>Uygulama yükleme hataları

Aşağıdaki hata iletileri ve açıklamaları, Android ve iOS yükleme hataları hakkında ayrıntılar sağlar. 

### <a name="android-errors"></a>Android hataları

Bu bölüm hem Cihaz Yöneticisi (DA) hem de Samsung KNOX kaydı ile bahsetmektedir. Daha fazla bilgi için bkz. [Android Cihaz Yöneticisi kaydı](android-enroll-device-administrator.md) ve [Samsung 's Knox mobil kayıt kullanarak Android cihazları otomatik olarak kaydetme](android-samsung-knox-mobile-enroll.md). 

| Hata iletisi/kodu | Açıklama |
|---------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Uygulama yüklenemedi. (0xC7D14FB5) | Intune, Android uygulama yükleme hatasının kök nedenini belirleyemediğinde bu hata iletisi görüntülenir. Hata sırasında Android tarafından hiç bilgi sağlanmadı. Bu hata, APK indirmesi başarılı olduğunda döndürülür, ancak uygulama yüklemesi başarısız olur. Cihaza yüklenemeyen hatalı bir APK dosyası nedeniyle bu hata daha yaygın olarak oluşabilir. Olası bir neden Google Play koruma, güvenlik sorunları nedeniyle uygulamanın yüklenmesini engellediğinde olabilir. Bu hatanın olası nedenlerinden biri, cihaz uygulamayı desteklemediğinde oluşur. Örneğin, uygulama API sürümü 21 + gerektiriyorsa ve cihazda Şu anda API sürüm 19 varsa. Intune hem DA hem de KNOX cihazlarında bu hatayı döndürür ve kullanıcıların yeniden denemek için tıklayabileceği bir bildirim olabilir, ancak APK ile ilgili bir sorun varsa, bu durum hiçbir şekilde başarısız olmaya devam eder. Uygulama kullanılabilir bir uygulama ise, bildirim kapatılabilir. Öte yandan uygulama gerekliyse, kapatılamaz. |
| Yükleme (APK) dosyası indirildikten sonra, ancak yüklemeden önce silindiği için uygulama yüklemesi iptal edildi. (0xC7D14FBA) | APK yüklemesi başarılı oldu, ancak kullanıcı uygulamayı yüklemeden önce dosya cihazdan kaldırıldı. İndirme ve yükleme arasında büyük bir zaman farkı varsa bu durum oluşabilir. Örneğin, Kullanıcı özgün yüklemeyi iptal etti, bekledi ve sonra yeniden denemek için bildirime tıkladı. Bu hata iletisi yalnızca DA DA Bu senaryolar için döndürülür. KNOX senaryoları sessizce yapılabilir. Kullanıcının iptali yerine kabul edebilmesi için yeniden denemek üzere bir bildirim sunuyoruz. Uygulama kullanılabilir bir uygulama ise, bildirim kapatılabilir. Öte yandan uygulama gerekliyse, kapatılamaz. |
| İşlem yükleme sırasında yeniden başlatıldığından uygulama yüklemesi iptal edildi. (0xC7D14FBB) | Cihaz, APK yükleme işlemi sırasında yeniden başlatıldığı için iptal edilmiş bir yüklemeye neden oldu. Bu hata iletisi hem DA hem de KNOX cihazları için döndürülür. Intune, kullanıcıların yeniden denemek için tıklamakta olduğu bir bildirim sunar. Uygulama kullanılabilir bir uygulama ise, bildirim kapatılabilir. Öte yandan uygulama gerekliyse, kapatılamaz. |
| Yükleme başarıyla tamamlandıktan sonra uygulama algılanmadı. (0x87D1041C) | Kullanıcı uygulamayı açıkça kaldırdı. Bu hata istemciden döndürülmedi. Uygulama bir noktada yüklendiğinde üretilmekte olan bir hatadır, ancak kullanıcı onu kaldırmış olur. Bu hata yalnızca gerekli uygulamalar için gerçekleştirilmelidir. Gerekli olmayan uygulamaları kullanıcı kaldırabilir. Bu hata yalnızca DA içinde olabilir. KNOX, yönetilen uygulamaların kaldırılmasını engeller. Sonraki eşitleme, kullanıcının yüklemesi için cihaza bildirimi yeniden gönderecek. Kullanıcı bildirimi yoksayabilir. Kullanıcı uygulamayı yükleyinceye kadar bu hata bildirilmeye devam edecektir. |
| Bilinmeyen bir hata nedeniyle indirme başarısız oldu. (0xC7D14FB2) | İndirme başarısız olduğunda bu hata oluşur. Bu hata, genellikle Wi-Fi sorunları veya yavaş bağlantılar nedeniyle ortaya çıkabilir. Bu hata yalnızca DA Bu senaryolar için döndürülür. KNOX senaryolarında, kullanıcının yüklemesi istenmez, bu işlem sessizce yapılabilir. Intune, kullanıcıların yeniden denemek için tıklamakta olduğu bir bildirim sunar. Uygulama kullanılabilir bir uygulama ise, bildirim kapatılabilir. Öte yandan uygulama gerekliyse, kapatılamaz. |
| Bilinmeyen bir hata nedeniyle indirme başarısız oldu. İlke, cihazın bir sonraki eşitlediği yeniden denenir. (0xC7D15078) | İndirme başarısız olduğunda bu hata oluşur. Bu hata, genellikle Wi-Fi sorunları veya yavaş bağlantılar nedeniyle ortaya çıkabilir. Bu hata yalnızca DA Bu senaryolar için döndürülür. KNOX senaryolarında, kullanıcının yüklemesi istenmez, bu işlem sessizce yapılabilir. |
| Son Kullanıcı, uygulama yüklemesini iptal etti. (0xC7D14FB1) | Kullanıcı uygulamayı açıkça kaldırdı. Bu hata, Android işletim sistemi yüklemesi etkinliği Kullanıcı tarafından iptal edildiğinde döndürülür. Kullanıcı, istemden uzakta veya tıklandığı zaman iptal düğmesine bastın. Bu hata yalnızca DA Bu senaryolar için döndürülür. KNOX senaryolarında, kullanıcının yüklemesi istenmez, bu işlem sessizce yapılabilir. Intune, kullanıcıların yeniden denemek için tıklamakta olduğu bir bildirim sunar. Uygulama kullanılabilir bir uygulama ise, bildirim kapatılabilir. Öte yandan uygulama gerekliyse, kapatılamaz. Kullanıcıdan yüklemeyi iptal etmesini isteyin. |
| Dosya indirme işlemi beklenmedik bir şekilde durduruldu. (0xC7D15015) | İşletim sistemi, tamamlanmadan önce indirme işlemini durdurdu. Bu hata, cihazda düşük pil varsa veya indirme çok uzun sürerse meydana gelebilir. Bu hata yalnızca DA Bu senaryolar için döndürülür. KNOX senaryolarında, kullanıcının yüklemesi istenmez, bu işlem sessizce yapılabilir. Intune, kullanıcıların yeniden denemek için tıklamakta olduğu bir bildirim sunar. Uygulama kullanılabilir bir uygulama ise, bildirim kapatılabilir. Öte yandan uygulama gerekliyse, kapatılamaz. Cihazın güvenilir bir ağ bağlantısına sahip olduğundan emin olun.  |
| Dosya indirme hizmeti beklenmedik bir şekilde durduruldu. İlke, cihazın bir sonraki eşitlediği yeniden denenir. (0xC7D1507C) | İşletim sistemi tamamlanmadan önce indirme işlemini sonlandırdı. Bu hata, cihazda düşük pil varsa veya indirme çok uzun sürerse meydana gelebilir. Bu hata yalnızca DA Bu senaryolar için döndürülür. KNOX senaryolarında, kullanıcının yüklemesi istenmez, bu işlem sessizce yapılabilir. Cihazı el ile eşitleyin veya 24 saat bekleyin ve durumu denetleyin. |
| Uygulama kaldırılamadı. (0xc7d14fb8) | Bu hata, genel bir kaldırma hatasıdır. İşletim sistemi, uygulamanın neden kaldırılması başarısız olduğunu belirtmedi. Bazı yönetici uygulamaları yalnızca kaldırılamaz. Uygulamanın el ile kaldırılabileceği ve kaldırma başarısız olursa Şirket Portalı günlüklerini toplamadan emin olmak için denetleyin. |
| Yükseltme için kullanılan uygulama yükleme APK dosyası cihazdaki geçerli uygulamanın imzasıyla eşleşmiyor. (0xc7d14fb7) | Android işletim sistemi, yükseltme sürümü için imzalama sertifikasının, mevcut sürümü imzalamak için kullanılan sertifika ile tam olarak aynı olmasını gerektirmektir. Geliştirici yeni sürümü imzalamak için aynı sertifikayı kullanmıyorsanız var olan uygulamayı kaldırmanız ve mevcut uygulamayı yükseltmek yerine yeni uygulamayı yeniden dağıtmanız gerekir. |
| Son Kullanıcı, uygulama yüklemesini iptal etti. (0xc7d14fb9) | Intune tarafından dağıtılan uygulamayı kabul etmek ve istendiğinde uygulamayı yüklemek için kullanıcıyı eğitin. |
| İşlem yükleme sırasında yeniden başlatıldığından uygulama kaldırma işlemi iptal edildi. (0xc7d14fbc) | Uygulama yüklemesi işlemi işletim sistemi tarafından sonlandırıldı veya cihaz yeniden başlatıldı. Bu hata tekrar oluşursa, yüklemeyi ve toplamayı Şirket Portalı günlüklerini yeniden deneyin. |
| Uygulama yüklemesi APK dosyası, imzalanmadığı için yüklenemiyor. (0xc7d14fb6) | Android işletim sistemi, varsayılan olarak uygulamaların imzalanmasını gerektirir. Uygulamanın dağıtımdan önce imzalandığından emin olun. |

### <a name="ios-errors"></a>iOS hataları

| Hata iletisi/kodu | Açıklama/sorun giderme ipuçları |
|------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| (0x87D12906) | Apple MDM Aracısı yükleme komutunun başarısız olduğunu döndürdü. |
| (0x87D1313C) | Güncelleştirilmiş indirme hizmeti URL 'SI cihaza gönderilirken ağ bağlantısı kayboldu. Özellikle, belirtilen ana bilgisayar adına sahip bir sunucu bulunamadı. |
| iOS cihazı şu anda meşgul. (0x87D11388) | İOS cihazı meşgul, bu da hata ile sonuçlandı. Cihaz kilitlendi. Uygulamayı yüklemek için kullanıcının cihazın kilidini açması gerekir. |
| Uygulama yüklemesi başarısız oldu. (0x87D13B64) | Uygulama yükleme hatası oluştu. Bu hatayı gidermek için iOS konsol günlükleri gereklidir. |
| Uygulama yönetiliyor, ancak süresi doldu veya Kullanıcı tarafından kaldırıldı. (0x87D13B66) | Kullanıcı uygulamayı açıkça kaldırdı ya da uygulamanın geçerliliği, ancak indirilemedi ya da uygulama algılaması cihazdaki Yanıtla eşleşmiyor. Buna ek olarak, bu hata iOS 9.2.2 platform hatası nedeniyle oluşabilir. |
| Uygulama yüklenmek üzere zamanlandı, ancak işlemi tamamlaması için bir kullanım kodu gerekiyor. (0x87D13B60) | Bu hata genellikle ücretli uygulamalar olan iOS Mağazası uygulamalarıyla birlikte oluşur. |
| Yükleme başarıyla tamamlandıktan sonra uygulama algılanmadı. (0x87D1041C) | Uygulama algılama işlemi cihazdaki Yanıtla eşleşmedi. |
| Kullanıcı uygulamayı yüklemeye yönelik teklifi reddetti. (0x87D13B62) | İlk uygulama yüklemesi sırasında Kullanıcı iptal ' i tıklamıştır. Kullanıcıdan bir sonraki sefer Install isteğini kabul etmesini isteyin. |
| Kullanıcı, uygulamayı güncelleştirme teklifini reddetti. (0x87D13B63) | Son Kullanıcı güncelleştirme işlemi sırasında iptal ' i tıkladı. Gerekli olarak dağıtın veya yükseltme isteğini kabul etmek için kullanıcıyı eğitin. |
| Bilinmeyen hata (0x87D103E8) | Bilinmeyen bir uygulama yükleme hatası oluştu. Bu, diğer hatalar gerçekleşmediğinden ortaya çıkan hatadır. |
| Yalnızca paylaşılan iPad (-2016330861) üzerinde VPP uygulamaları yüklenebilir. | Uygulamalar, paylaşılan bir iPad 'e yüklemek için Apple Volume Purchase Program kullanılarak alınmalıdır. |
| App Store devre dışı bırakıldığında uygulamalar yüklenemez (-2016330860). | Kullanıcının uygulamayı yüklemesi için uygulama mağazası 'nın etkinleştirilmesi gerekir. |
| Uygulama için VPP lisansı bulunamıyor (-2016330859). | Uygulama lisansını iptal edip yeniden atanmasını deneyin. |
| MDM sağlayıcınızda sistem uygulamaları yüklenemez (-2016330858). | İOS işletim sistemi tarafından önceden yüklenmiş uygulamaların yüklenmesi desteklenen bir senaryo değildir. |
| Cihaz kayıp modundayken (-2016330857) uygulamalar yüklenemez. | Cihazın tüm kullanımı kayıp modunda engellenmiştir. Uygulamaları yüklemek için kayıp modunu devre dışı bırakın. |
| Cihaz bilgi noktası modundayken (-2016330856) uygulamalar yüklenemez. | Uygulamaları yüklemek için bu cihazı bilgi noktası modu yapılandırma ilkesi için dışlama grubuna eklemeyi deneyin. |
| Bu cihaza 32 bitlik uygulamalar yüklenemiyor (-2016330852). | Cihaz, 32 bitlik uygulamaları yüklemeyi desteklemez. Uygulamanın 64 bitlik sürümünü dağıtmaya çalışın. |
| Kullanıcının uygulama mağazası 'nda oturum açması gerekir (-2016330855). | Uygulamanın yüklenebilmesi için önce kullanıcının App Store 'da oturum açması gerekir. |
| Bilinmeyen sorun. Lütfen yeniden deneyin (-2016330854). | Uygulama yüklemesi bilinmeyen bir nedenden dolayı başarısız oldu. Daha sonra tekrar deneyin. |
| Uygulama yüklemesi başarısız oldu. Intune, cihazın bir sonraki eşitlediği bir dahaki sefer yeniden dener (-2016330853). | Uygulama yüklemesi bir cihaz hatasıyla karşılaştı. Uygulamayı yeniden yüklemeyi denemek için cihazı eşitleyin. |
| Lisans ataması, ' ' VPP lisansı kalmadı ' adlı Apple hatasıyla başarısız oldu (0x87d13b7e) | Bu davranış tasarım gereğidir. Bu sorunu çözmek için, ek VPP lisansları satın alın veya kullanıcılardan artık hedeflenmediğini bir lisans geri kazanın. |
| Uygulama yüklemesi hatası 12024: Bilinmeyen neden. (0x87d13b6e) | Apple 'ın yüklemenin başarısız olduğunu belirlemede yeterli bilgi vermedi. Raporlanacak bir şey yok. |
| Gerekli uygulama yapılandırma ilkesi yok, ilkenin aynı grupları hedeflediğinden emin olun. (0x87d13b7f) | Uygulama uygulama yapılandırması gerektiriyor, ancak hiçbir uygulama yapılandırması hedeflenmedi. Yönetici, uygulamanın hedeflediği grupların, gruplara hedeflenmiş gerekli uygulama yapılandırmasını da içerdiğinden emin olmalıdır. |
| Cihaz VPP lisansı yalnızca iOS 9.0 + cihazları için geçerlidir. (0x87d13b69) | Etkilenen iOS cihazlarını iOS 9.0 + sürümüne yükseltin. |
| Uygulama cihaza yüklenir, ancak yönetilmez. (0x87d13b8f) | Bu hata yalnızca LOB uygulamalarında meydana gelir. Uygulama, Intune dışında yüklendi. Bu hatayı gidermek için, uygulamayı cihazdan kaldırın. Cihazın eşitlenmesi bir sonraki sefer olduğunda, cihazın uygulamayı Intune 'dan yüklemesi gerekir. |
| Kullanıcı, uygulama yönetimini reddetti (0x87d13b68) | Kullanıcıdan uygulama yönetimini kabul etmesini isteyin. |
| Bilinmeyen hata. (0x87d1279d) | Bu hata iOS Mağazası uygulamaları için gerçekleşir, ancak hata senaryosu bilinmez. |
| Uygulamanın en son sürümü önceki bir sürümden güncelleştirilemedi. (0x87D13B9D) | Bu hata iletisi, uygulama yüklenip yönetiliyorsa, ancak cihazda yanlış sürüm ile birlikte görüntülenir. Bu durum, bir cihazın uygulamayı güncelleştirmek için bir komut aldığında, ancak yeni sürümün henüz yüklenmemiş ve geri raporlanmadığında oluşur. Bu hata, yükseltme dağıtıldıktan sonra bir cihazın ilk iadede raporlanır ve cihaz yeni sürümün yüklü olduğunu bildirene veya farklı bir hata nedeniyle başarısız olana kadar gerçekleşmeyecektir.  |


### <a name="other-installation-errors"></a>Diğer yükleme hataları

|  Hata iletisi/kodu  |  Açıklama  |
|-----------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  0x80073CFF, 0x80CF201C (istemci hatası)  |  Bu uygulamayı yüklemek için dışarıdan yükleme özellikli bir sisteme sahip olmanız gerekir. Uygulama paketinin güvenilir bir imza ile imzalandığından ve **AllowAllTrustedApps** ilkesinin etkinleştirildiği bir etki alanına katılmış cihaza veya **AllowAllTrustedApps** ilkesiyle Windows dışarıdan yükleme lisansına sahip bir cihaza yüklenmiş olduğundan emin olun etkinletir. Daha fazla bilgi için bkz. [Windows Mağazası uygulamalarının paketlenmesi, dağıtılması ve sorgu sorunlarını giderme](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting).   |
|  0x80073CF0  |  Paket açılamadı. Olası nedenler:<ul><li> Paket imzasız.</li><li> Yayımcı adı imza sertifikası konusuyla eşleşmiyor.</li></ul> Bilgi için **Appxpackagingom** olay günlüğünü denetleyin. Daha fazla bilgi için bkz. [Windows Mağazası uygulamalarının paketlenmesi, dağıtılması ve sorgu sorunlarını giderme](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting).  |
|  0x80073CF3  |  Paket güncelleştirme, bağımlılık veya çakışma doğrulaması başarısız oldu. Olası nedenler:<ul><li> Gelen paket yüklü bir paketle çakışıyor.</li><li> Belirtilen bir paket bağımlılığı bulunamadı.</li><li> Paket doğru işlemci mimarisini desteklemiyor.</li></ul> Bilgi için **Appxdeployment-Server** olay günlüğünü denetleyin. Daha fazla bilgi için bkz. [Windows Mağazası uygulamalarının paketlenmesi, dağıtılması ve sorgu sorunlarını giderme](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting).  |
|  0x80073CFB  |  Belirtilen paket zaten yüklü ve paketin yeniden yüklenmesi engellendi. Zaten yüklü olan paketle aynı olmayan bir paket yüklüyorsanız bu hatayı alabilirsiniz. Dijital imzanın paketin bir parçası olduğunu da onaylayın. Bir paket yeniden oluşturulduğunda veya yeniden imzalandığında, bu paket artık önceden yüklenmiş paket ile aynı bit düzeyinde değildir. Bu hatayı düzeltmek için kullanılabilecek iki seçenek aşağıda belirtilmiştir:<ul><li> Uygulamanın sürüm numarasını artırın, ardından paketi yeniden oluşturup yeniden imzalayın.</li><li> Yeni paketi yüklemeden önce sistem üzerindeki her kullanıcı için eski paketi kaldırın.</li></ul> Daha fazla bilgi için bkz. [Windows Mağazası uygulamalarının paketlenmesi, dağıtılması ve sorgu sorunlarını giderme](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting).  |
|  0x87D1041C  |  Uygulama yükleme başarılı oldu ancak uygulama algılanmadı. Uygulama Intune tarafından başarıyla dağıtıldı ve sonra kaldırıldı. Kaldırılmakta olan uygulamanın nedenleri şunlardır:<ul><li> Son Kullanıcı uygulamayı kaldırdı.</li><li> Paketteki kimlik bilgileri, bozuk uygulamalar için hangi cihaz raporlarının raporlamalarına uymuyor.</li><li>Kendi kendine güncelleştirilmesi için, ürün sürümü, Intune dışında güncelleştirildikten sonra uygulamanın bilgileriyle eşleşmez.</li></ul> Kullanıcıya uygulamayı şirket portalından yeniden yüklemesini söyleyin. Cihaz bir sonraki iade edildiğinde gerekli uygulamaların otomatik olarak yeniden yüklenmesini unutmayın.  |
|  0x8000FFFF  |  Yükleme sırasında beklenmeyen bir hata oluştu. Ek bilgi için yükleme günlüklerine bakın.  |

## <a name="troubleshooting-apps-from-the-microsoft-store"></a>Microsoft Mağazası'ndan uygulama sorunlarını giderme

[Microsoft Mağazası uygulamalarının paketleme, dağıtım ve sorgu sorunlarını giderme](https://msdn.microsoft.com/library/windows/desktop/hh973484.aspx) konusunda yer alan bilgiler, Intune’u veya diğer araçları kullanarak Microsoft Mağazası’nden uygulama yüklerken karşılaşabileceğiniz genel sorunları gidermenize yardımcı olur.

## <a name="app-troubleshooting-resources"></a>Uygulama sorun giderme kaynakları
- [Office Pro Plus dağıtımınızın bir parçası olarak Visio ve proje dağıtma](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Deploying-Visio-and-Project-as-part-of-your-Office/ba-p/701795)
- [Windows 10 1903 ' de Intune yüklemesi aracılığıyla dağıtılan MSfB uygulamalarının sağlandığından emin olmak için Işlem yapın](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Take-Action-to-Ensure-MSfB-Apps-deployed-through/ba-p/658864)
- [Microsoft Intune 'de MSI uygulama dağıtımları sorunlarını giderme](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Troubleshooting-MSI-App-deployments-in-Microsoft/ba-p/359125)
- [Klasik Intune Windows bılgısayar aracısına yazılım dağıtımı için en iyi uygulamalar](https://support.microsoft.com/en-us/help/2583929/best-practices-for-intune-software-distribution-to-windows-pc)

## <a name="next-steps"></a>Sonraki adımlar

- Ek Intune sorun giderme bilgileri için bkz. [Şirketinizdeki kullanıcılara yardımcı olmak için sorun giderme portalını kullanma](help-desk-operators.md). 
- Microsoft Intune’daki tüm bilinen sorunlar hakkında bilgi edinin. Daha fazla bilgi için bkz. [Intune müşteri başarısı](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/bg-p/IntuneCustomerSuccess).
- Ek yardım mı gerekiyor? Bkz. [Microsoft Intune için destek alma](get-support.md).
