---
title: Uygulama yükleme sorunlarını giderme
titleSuffix: Microsoft Intune
description: Uygulama yükleme sorunlarını gidermenize yardımcı olması için Microsoft Intune sorun giderme bölmesini kullanın.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/25/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: b613f364-0150-401f-b9b8-2b09470b34f4
ms.reviewer: mghadial
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b93fc8bc1bddbae8b1b0bde4f8b8815e8052fb51
ms.sourcegitcommit: 2fa20338bd0236884e1f3fde624cf70da89fd254
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/26/2019
ms.locfileid: "68507685"
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
- İOS DEP cihazları için, kullanıcının Intune cihazına genel bakış dikey penceresinde **kayıtlı** olarak listelendiğinden emin olun. Varsa, Intune Şirket Portalı için bir yapılandırma ilkesi dağıtın. Daha fazla bilgi için bkz. [Şirket Portalı uygulamasını yapılandırma](https://docs.microsoft.com/intune/app-configuration-policies-use-ios#configure-the-company-portal-app-to-support-ios-dep-devices).

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
- Saklanan Günlükler günlüklerde bulunan PII bilgilerini korumak için şifrelenir.
- Win32 uygulama hataları için destek biletlerini açarken, yukarıda belirtilen adımları kullanarak ilgili hata günlüklerini iliştirin.

## <a name="app-installation-errors"></a>Uygulama yükleme hataları

Aşağıdaki hata iletileri ve açıklamaları, Android ve iOS yükleme hataları hakkında ayrıntılar sağlar. 

### <a name="android-errors"></a>Android hataları

|    Hata iletisi/kodu    |    Açıklama    |
|----------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Uygulama yüklenemedi. (0xC7D14FB5)    |    Bu hata iletisi Intune Android uygulama yükleme hatasının kök nedenini saptayamadığında görüntülenir. Hata sırasında Android tarafından hiç bilgi sağlanmadı.       APK indirme başarılı olduğunda ama uygulama yüklemesi yapılamadığında bu hata döndürülür. Bu hata yaygın olarak cihaza yüklenemeyen bozuk bir APK dosyasından kaynaklanıyor olabilir. Olası nedenlerinden biri, Google Play Koruması'nın güvenlik nedenleriyle uygulamanın yüklenmesini engellemesidir. Bu hatanın diğer bir olası nedeni cihazın uygulamayı desteklememesidir. Örneğin, uygulamaya API'nin 21+ sürümü gerekirken cihazda şu anda API'nin 19 sürümü yüklü olabilir.         Intune bu hatayı hem DA hem de KNOX cihazları için döndürür ve kullanıcının yeniden denemek için tıklayabileceği bir bildirim olabilir ama sorun APK'den kaynaklanıyorsa bir daha hata vermeyecektir. Uygulama kullanılabilir bir uygulamaysa, bu bildirim kapatılabilir. Öte yandan uygulama gerekliyse, kapatılamaz.        |
|    Yükleme (APK) dosyası indirildikten sonra, ancak yüklemeden önce silindiği için uygulama yüklemesi iptal edildi. (0xC7D14FBA)    |    APK'nin indirilmesi başarılı oldu ama kullanıcı uygulamayı yüklemeden önce dosya cihazdan silindi. İndirme ile yükleme arasında çok uzun bir süre geçtiğinde bu durum ortaya çıkabilir. Örneğin, Kullanıcı özgün yüklemeyi iptal etti, bekledi ve sonra yeniden denemek için bildirime tıkladı.         Bu hata iletisi yalnızca DA senaryolarında bunu döndürür. KNOX senaryoları sessiz gerçekleştirilebilir. Yeniden denemek için bir bildirim gösteririz, dolayısıyla kullanıcı iptal etmek yerine kabul edebilir. Uygulama kullanılabilir bir uygulamaysa, bu bildirim kapatılabilir. Öte yandan uygulama gerekliyse, kapatılamaz.    |
|    İşlem yükleme sırasında yeniden başlatıldığından uygulama yüklemesi iptal edildi. (0xC7D14FBB)    |    Cihaz, APK yükleme işlemi sırasında yeniden başlatıldığı için iptal edilmiş bir yüklemeye neden oldu.        Bu hata iletisi hem DA hem de KNOX cihazları için döndürülür. Intune kullanıcıların yeniden denemek için tıklayabileceği bir bildirim gösterir. Uygulama kullanılabilir bir uygulamaysa, bu bildirim kapatılabilir. Öte yandan uygulama gerekliyse, kapatılamaz.    |
|    Bu uygulama, yükleme başarıyla tamamlandıktan sonra algılanmadı. (0x87D1041C)    |    Kullanıcı uygulamayı açıkça kaldırdı. Bu hata istemciden döndürülmedi. Bu, bir noktada uygulama yüklendiğinde ama ardından kullanıcı bu uygulamayı kaldırdığında oluşan bir hatadır. Bu hata, yalnızca gerekli uygulamalar için oluşturulur. Gerekli olmayan uygulamaları kullanıcı kaldırabilir. Bu hata yalnızca DA'da oluşabilir. KNOX, yönetilen uygulamaların kaldırılmasını engeller.       Sonraki eşitlemede kullanıcının yüklemesi için bildirim cihaza yeniden gönderilir.   Kullanıcı bildirimi yoksayabilir. Kullanıcı uygulamayı yükleyene kadar bu hata bildirilmeye devam edecektir.    |
|    Bilinmeyen bir hata nedeniyle indirme başarısız oldu. (0xC7D14FB2)    |    Bu hata indirme başarısız olduğunda oluşur. Bu hata yaygın olarak Wi-Fi sorunlarından veya yavaş bağlantılardan kaynaklanabilir.       Bu hata yalnızca DA senaryolarında döndürülür. KNOX senaryolarında kullanıcılardan yüklemeleri istenmez; bu işlem sessiz olarak yapılabilir. Intune kullanıcıların yeniden denemek için tıklayabileceği bir bildirim gösterir. Uygulama kullanılabilir bir uygulamaysa, bu bildirim kapatılabilir. Öte yandan uygulama gerekliyse, kapatılamaz.    |
|    Bilinmeyen bir hata nedeniyle indirme başarısız oldu. Cihazın bir sonraki eşitlenmesinde ilke yeniden denenecektir. (0xC7D15078)    |    Bu hata indirme başarısız olduğunda oluşur. Bu hata yaygın olarak Wi-Fi sorunlarından veya yavaş bağlantılardan kaynaklanabilir.       Bu hata yalnızca DA senaryolarında döndürülür. KNOX senaryolarında kullanıcılardan yüklemeleri istenmez; bu işlem sessiz olarak yapılabilir.    |
|    Son Kullanıcı, uygulama yüklemesini iptal etti. (0xC7D14FB1)    |    Kullanıcı uygulamayı açıkça kaldırdı. Bu hata, Android işletim sistemi yüklemesi etkinliği Kullanıcı tarafından iptal edildiğinde döndürülür. İşletim sistemi yükleme istemi gösterildiğinde kullanıcı iptal düğmesine bastı veya istemin dışına tıkladı.        Bu hata yalnızca DA senaryolarında döndürülür. KNOX senaryolarında kullanıcılardan yüklemeleri istenmez; bu işlem sessiz olarak yapılabilir. Intune kullanıcıların yeniden denemek için tıklayabileceği bir bildirim gösterir. Uygulama kullanılabilir bir uygulamaysa, bu bildirim kapatılabilir. Öte yandan uygulama gerekliyse, kapatılamaz.    |
|    Dosya indirme süreci beklenmedik bir şekilde durduruldu. (0xC7D15015)    |    İşletim sistemi, indirme işlemini tamamlanmadan önce durdurdu. Bu hata cihazın pil düzeyi düşük olduğunda veya indirme işlemi fazla uzun sürdüğünde oluşur.       Bu hata yalnızca DA senaryolarında döndürülür. KNOX senaryolarında kullanıcılardan yüklemeleri istenmez; bu işlem sessiz olarak yapılabilir. Intune kullanıcıların yeniden denemek için tıklayabileceği bir bildirim gösterir. Uygulama kullanılabilir bir uygulamaysa, bu bildirim kapatılabilir. Öte yandan uygulama gerekliyse, kapatılamaz.    |
|    Dosya indirme hizmeti beklenmedik bir şekilde durduruldu. Cihazın bir sonraki eşitlenmesinde ilke yeniden denenecektir. (0xC7D1507C)    |    İşletim sistemi, indirme işlemini tamamlanmadan önce durdurdu. Bu hata cihazın pil düzeyi düşük olduğunda veya indirme işlemi fazla uzun sürdüğünde oluşur.       Bu hata yalnızca DA senaryolarında döndürülür. KNOX senaryolarında kullanıcılardan yüklemeleri istenmez; bu işlem sessiz olarak yapılabilir.    |

### <a name="ios-errors"></a>iOS hataları

| Hata iletisi/kodu | Açıklama/sorun giderme ipuçları |
|------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| (0x87D12906) | Apple MDM Aracısı yükleme komutunun başarısız olduğunu döndürdü. |
| (0x87D1313C) | Güncelleştirilmiş indirme hizmeti URL 'SI cihaza gönderilirken ağ bağlantısı kayboldu. Özellikle, belirtilen ana bilgisayar adına sahip bir sunucu bulunamadı. |
| iOS cihazı şu anda meşgul. (0x87D11388) | İOS cihazı meşgul, bu da hata ile sonuçlandı. |
| Uygulama yüklemesi başarısız oldu. (0x87D13B64) | Uygulama yükleme hatası oluştu. Bu hatayı gidermek için XCODE günlükleri gerekiyor. |
| Uygulama yönetiliyor, ancak süresi doldu veya Kullanıcı tarafından kaldırıldı. (0x87D13B66) | Kullanıcı uygulamayı açıkça kaldırdı. Öte yandan, uygulamanın süresi dolmuş ama indirilememiş veya uygulama algılaması cihazdan gelen yanıtla eşleşmiyor da olabilir.   Buna ek olarak, bu hata iOS 9.2.2 platform hatası nedeniyle oluşabilir. |
| Uygulama yüklenmek üzere zamanlandı, ancak işlemi tamamlaması için bir kullanım kodu gerekiyor. (0x87D13B60) | Bu hata genellikle ücretli uygulamalar olan iOS Mağazası uygulamalarıyla birlikte oluşur. |
| Yükleme başarıyla tamamlandıktan sonra uygulama algılanmadı.   (0x87D1041C) | Uygulama algılama işlemi cihazdaki Yanıtla eşleşmedi. |
| Kullanıcı uygulamayı yüklemeye yönelik teklifi reddetti. (0x87D13B62) | İlk uygulama yüklemesi sırasında Kullanıcı iptal ' i tıklamıştır. |
| Kullanıcı, uygulamayı güncelleştirme teklifini reddetti. (0x87D13B63) | Son Kullanıcı güncelleştirme işlemi sırasında iptal ' i tıkladı. |
| Bilinmeyen hata (0x87D103E8) | Bilinmeyen bir uygulama yükleme hatası oluştu. Bu, diğer hatalar gerçekleşmediğinden ortaya çıkan hatadır. |
| Yalnızca paylaşılan iPad (-2016330861) üzerinde VPP uygulamaları yüklenebilir. | Uygulamalar, paylaşılan bir iPad 'e yüklemek için Apple Volume Purchase Program kullanılarak alınmalıdır. |
| App Store devre dışı bırakıldığında uygulamalar yüklenemez (-2016330860).  | Kullanıcının uygulamayı yüklemesi için uygulama mağazası 'nın etkinleştirilmesi gerekir. |
| Uygulama için VPP lisansı bulunamıyor (-2016330859).  | Uygulama lisansını iptal edip yeniden atanmasını deneyin. |
| MDM sağlayıcınızda sistem uygulamaları yüklenemez (-2016330858). | İOS işletim sistemi tarafından önceden yüklenmiş uygulamaların yüklenmesi desteklenen bir senaryo değildir. |
| Cihaz kayıp modundayken (-2016330857) uygulamalar yüklenemez. | Cihazın tüm kullanımı kayıp modunda engellenmiştir.   Uygulamaları yüklemek için kayıp modunu devre dışı bırakın. |
| Cihaz bilgi noktası modundayken (-2016330856) uygulamalar yüklenemez. | Uygulamaları yüklemek için bu cihazı bilgi noktası modu yapılandırma ilkesi için dışlama grubuna eklemeyi deneyin. |
| Bu cihaza 32 bitlik uygulamalar yüklenemiyor (-2016330852). | Cihaz, 32 bitlik uygulamaları yüklemeyi desteklemez. Uygulamanın 64 bitlik sürümünü dağıtmaya çalışın. |
| Kullanıcının uygulama mağazası 'nda oturum açması gerekir (-2016330855). | Uygulamanın yüklenebilmesi için önce kullanıcının App Store 'da oturum açması gerekir. |
| Bilinmeyen sorun. Lütfen yeniden deneyin (-2016330854). | Uygulama yüklemesi bilinmeyen bir nedenden dolayı başarısız oldu.   Daha sonra tekrar deneyin. |
| Uygulama yüklemesi başarısız oldu. Intune, cihazın bir sonraki eşitlediği bir dahaki sefer yeniden dener (-2016330853). | Uygulama yüklemesi bir cihaz hatasıyla karşılaştı. Uygulamayı yeniden yüklemeyi denemek için cihazı eşitleyin. |

### <a name="other-installation-errors"></a>Diğer yükleme hataları

|    Hata iletisi/kodu    |    Açıklama    |
|-----------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    0x80073CFF, 0x80CF201C (istemci hatası)    |    Bu uygulamayı yüklemek için dışarıdan yükleme özellikli bir sisteme sahip olmanız gerekir. Uygulama paketinin güvenilir bir imza ile imzalandığından ve **AllowAllTrustedApps** ilkesinin etkinleştirildiği bir etki alanına katılmış cihaza veya **AllowAllTrustedApps** ilkesiyle Windows dışarıdan yükleme lisansına sahip bir cihaza yüklenmiş olduğundan emin olun etkinletir. Daha fazla bilgi için bkz. [Windows Mağazası uygulamalarının paketlenmesi, dağıtılması ve sorgu sorunlarını giderme](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting).     |
|    0x80073CF0    |    Paket açılamadı. Olası nedenler:<ul><li> Paket imzasız.</li><li> Yayımcı adı imza sertifikası konusuyla eşleşmiyor.</li></ul> Bilgi için **Appxpackagingom** olay günlüğünü denetleyin. Daha fazla bilgi için bkz. [Windows Mağazası uygulamalarının paketlenmesi, dağıtılması ve sorgu sorunlarını giderme](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting).    |
|    0x80073CF3    |    Paket güncelleştirme, bağımlılık veya çakışma doğrulaması başarısız oldu. Olası nedenler:<ul><li> Gelen paket yüklü bir paketle çakışıyor.</li><li> Belirtilen bir paket bağımlılığı bulunamadı.</li><li> Paket doğru işlemci mimarisini desteklemiyor.</li></ul> Bilgi için **Appxdeployment-Server** olay günlüğünü denetleyin. Daha fazla bilgi için bkz. [Windows Mağazası uygulamalarının paketlenmesi, dağıtılması ve sorgu sorunlarını giderme](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting).    |
|    0x80073CFB    |    Belirtilen paket zaten yüklü ve paketin yeniden yüklenmesi engellendi. Zaten yüklü olan paketle aynı olmayan bir paket yüklüyorsanız bu hatayı alabilirsiniz. Dijital imzanın paketin bir parçası olduğunu da onaylayın. Bir paket yeniden oluşturulduğunda veya yeniden imzalandığında, bu paket artık önceden yüklenmiş paket ile aynı bit düzeyinde değildir. Bu hatayı düzeltmek için kullanılabilecek iki seçenek aşağıda belirtilmiştir:<ul><li> Uygulamanın sürüm numarasını artırın, ardından paketi yeniden oluşturup yeniden imzalayın.</li><li> Yeni paketi yüklemeden önce sistem üzerindeki her kullanıcı için eski paketi kaldırın.</li></ul> Daha fazla bilgi için bkz. [Windows Mağazası uygulamalarının paketlenmesi, dağıtılması ve sorgu sorunlarını giderme](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting).    |
|    0x87D1041C    |    Uygulama yükleme başarılı oldu ancak uygulama algılanmadı. Uygulama Intune tarafından başarıyla dağıtıldı ve sonra kaldırıldı. Kaldırılmakta olan uygulamanın nedenleri şunlardır:<ul><li> Son Kullanıcı uygulamayı kaldırdı.</li><li> Paketteki kimlik bilgileri, bozuk uygulamalar için hangi cihaz raporlarının raporlamalarına uymuyor.</li><li>Kendi kendine güncelleştirilmesi için, ürün sürümü, Intune dışında güncelleştirildikten sonra uygulamanın bilgileriyle eşleşmez.</li></ul> Kullanıcıya uygulamayı şirket portalından yeniden yüklemesini söyleyin. Cihaz bir sonraki iade edildiğinde gerekli uygulamaların otomatik olarak yeniden yüklenmesini unutmayın.    |
|    0x8000FFFF    |    Yükleme sırasında beklenmeyen bir hata oluştu. Ek bilgi için yükleme günlüklerine bakın.    |

## <a name="troubleshooting-apps-from-the-microsoft-store"></a>Microsoft Mağazası'ndan uygulama sorunlarını giderme

[Microsoft Mağazası uygulamalarının paketleme, dağıtım ve sorgu sorunlarını giderme](https://msdn.microsoft.com/library/windows/desktop/hh973484.aspx) konusunda yer alan bilgiler, Intune’u veya diğer araçları kullanarak Microsoft Mağazası’nden uygulama yüklerken karşılaşabileceğiniz genel sorunları gidermenize yardımcı olur.

## <a name="app-troubleshoooting-resources"></a>Uygulama, kaynakların sorunlarını giderir
- [Office Pro Plus dağıtımınızın bir parçası olarak Visio ve proje dağıtma](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Deploying-Visio-and-Project-as-part-of-your-Office/ba-p/701795)
- [Windows 10 1903 ' de Intune yüklemesi aracılığıyla dağıtılan MSfB uygulamalarının sağlandığından emin olmak için Işlem yapın](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Take-Action-to-Ensure-MSfB-Apps-deployed-through/ba-p/658864)
- [Microsoft Intune 'de MSI uygulama dağıtımları sorunlarını giderme](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Troubleshooting-MSI-App-deployments-in-Microsoft/ba-p/359125)
- [Klasik Intune Windows bılgısayar aracısına yazılım dağıtımı için en iyi uygulamalar](https://support.microsoft.com/en-us/help/2583929/best-practices-for-intune-software-distribution-to-windows-pc)

## <a name="next-steps"></a>Sonraki adımlar

- Ek Intune sorun giderme bilgileri için bkz. [Şirketinizdeki kullanıcılara yardımcı olmak için sorun giderme portalını kullanma](help-desk-operators.md). 
- Microsoft Intune’daki tüm bilinen sorunlar hakkında bilgi edinin. Daha fazla bilgi için bkz. [Intune müşteri başarısı](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/bg-p/IntuneCustomerSuccess).
- Ek yardım mı gerekiyor? Bkz. [Microsoft Intune için destek alma](get-support.md).
