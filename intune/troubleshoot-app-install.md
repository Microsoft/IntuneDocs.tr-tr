---
title: Uygulama yükleme sorunlarını giderme
titleSuffix: Microsoft Intune
description: Uygulama yükleme sorunlarını gidermenize yardımcı olması için Microsoft Intune sorun giderme bölmesini kullanın.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/19/2019
ms.topic: troubleshooting
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: b613f364-0150-401f-b9b8-2b09470b34f4
ms.reviewer: mghadial
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 574f509383891ff3e8e0f4c1b04a19832a378829
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58799510"
---
# <a name="troubleshoot-app-installation-issues"></a>Uygulama yükleme sorunlarını giderme

Microsoft Intune MDM ile yönetilen cihazlarda bazen uygulama yüklemeleri başarısız olabilir. Bu uygulamaların yüklemesi başarısız olduğunda, başarısızlık sebebini anlamak ve sorunu gidermek zor olabilir. Microsoft Intune, kullanıcı yardım isteklerini ele almak yardım masası operatörleri ve Intune yöneticilerinin uygulama bilgilerini görüntülemek için uygulama yükleme hatası ayrıntıları sağlar. Intune içindeki sorun giderme bölmesi, kullanıcının cihazında yönetilen uygulamalar dahil hata ayrıntılarını sağlar. Bir uygulamanın uçtan uca yaşam döngüsü hakkındaki ayrıntıları, **Yönetilen Uygulamalar** bölmesinde her bir cihaz altında sağlanır. Uygulamanın ne zaman yüklendiği, değiştirildiği, hedeflendiği ve bir cihaza teslim edildiği gibi yükleme sorunlarını görüntüleyebilirsiniz. 

## <a name="app-troubleshooting-details"></a>Uygulama sorun giderme ayrıntıları

Intune, belirli bir kullanıcının cihazında yüklü uygulamalar temelinde sorun giderme ayrıntıları sağlar.

1. [Azure portal](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
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

Uygulama yükleme hatası ayrıntıları, sorunu gösterecektir. Sorunu çözmek için yapılacak en iyi eylemi belirlemek üzere bu ayrıntıları kullanabilirsiniz. Uygulama yükleme sorunlarını giderme hakkında daha fazla bilgi için bkz. [Uygulama Yükleme Sorunlarını Gidermek İçin Hata Kodları](https://blogs.technet.microsoft.com/intunesupport/2018/05/15/error-codes-for-troubleshooting-app-installation-issues).

> [!Note]  
> **Sorun giderme** bölmesine tarayıcınızı [https://aka.ms/intunetroubleshooting](https://aka.ms/intunetroubleshooting) adresine yönlendirerek de erişebilirsiniz.

## <a name="win32-app-installation-troubleshooting"></a>Win32 uygulama yükleme sorunlarını giderme

Intune Yönetim Uzantısı kullanılarak dağıtılmıştır Win32 uygulaması seçin. Seçebileceğiniz **günlükleri toplayın** seçeneği, Win32 uygulama yüklemesi başarısız olduğunda. 

> [!IMPORTANT]
> **Günlükleri toplayın** seçeneği etkin olmayabilir, Win32 uygulama cihaza başarıyla yüklendi.<p>Win32 Uygulama günlük bilgileri aktarmadan önce Intune Yönetim Uzantısı Windows istemcisinde yüklü olmalıdır. Bir PowerShell Betiği, Intune yönetim uzantısı yüklü değil veya bir Win32 uygulaması için bir kullanıcı veya cihaz güvenlik grubu olarak dağıtılır. Daha fazla bilgi için [Intune yönetim uzantısı - Önkoşullar](intune-management-extension.md#prerequisites).

### <a name="collect-log-file"></a>Günlük dosyası

Win32 uygulama yükleme günlüklerinizi toplamak için ilk bölümünde verilen adımları izleyin [sorun giderme ayrıntıları uygulama](troubleshoot-app-install.md#app-troubleshooting-details). Ardından, aşağıdaki adımları uygulayın:

1. Tıklayın **günlükleri toplayın** seçeneğini **Yükleme ayrıntıları** dikey penceresi.

    <image alt="Win32 app installation details - Collect log option" src="media/troubleshoot-app-install-04.png" width="500" />

2. Dosya yolları, günlük dosya toplama işlemi başlar ve dosya adları ile günlük sağlamak **Tamam**.
    
    > [!NOTE]
    > Günlük toplama iki saatten daha kısa sürer. Desteklenen dosya türleri: *.log, .txt, .dmp, .cab, .zip, .xml, .evtx ve .evtl*. En fazla 25 dosya yolları izin verilir.

3. Günlük dosyaları toplandıktan sonra seçebileceğiniz **günlükleri** günlük dosyalarını indirmek için bağlantı.

    <image alt="Win32 app log details - Download logs" src="media/troubleshoot-app-install-05.png" width="500" />

    > [!NOTE]
    > Uygulama günlük toplama başarıyı gösteren bir bildirim görüntülenir.

#### <a name="win32-log-collection-requirements"></a>Win32 günlük toplama gereksinimleri

Günlük dosyaları toplamak için izlenmesi gereken belirli gereksinimleri vardır:

- Tam günlük dosyası yolu belirtmeniz gerekir. 
- Aşağıdaki gibi günlük toplama için ortam değişkenlerini belirtebilirsiniz:<br>
  *% PROGRAMFILES %, % PROGRAMDATA % GENEL %, % WINDIR %, % TEMP %, % TMP %*
- Yalnızca tam dosya uzantıları gibi verilir:<br>
  *.log, .txt, .dmp, .cab, .zip, .xml*
- 60 MB veya 25 dosyayı karşıya yüklemek için en fazla günlük dosyası olduğu hangisi önce gerçekleşirse. 
- Win32 uygulama yükleme günlük toplama etkin gerekli, uyan uygulamalar için kullanılabilir ve uygulama atama hedefi kaldırın.
- Depolanan günlükler günlüklerde yer alan tüm PII bilgilerini korumak için şifrelenir.
- Win32 uygulama hataları için açılış destek biletleri karşın, yukarıda sağlanan adımları kullanarak ilişkili hata günlükleri ekleyin.

## <a name="app-installation-errors"></a>Uygulama yükleme hataları

Aşağıdaki hata iletileri ve açıklamaları, Android ve iOS yükleme hataları hakkında ayrıntılar sağlar. 

### <a name="android-errors"></a>Android hataları

|    Hata iletisi/kodu    |    Açıklama    |
|----------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Uygulama yüklenemedi. (0xC7D14FB5)    |    Bu hata iletisi Intune Android uygulama yükleme hatasının kök nedenini saptayamadığında görüntülenir. Hata sırasında Android tarafından hiç bilgi sağlanmadı.       APK indirme başarılı olduğunda ama uygulama yüklemesi yapılamadığında bu hata döndürülür. Bu hata yaygın olarak cihaza yüklenemeyen bozuk bir APK dosyasından kaynaklanıyor olabilir. Olası nedenlerinden biri, Google Play Koruması'nın güvenlik nedenleriyle uygulamanın yüklenmesini engellemesidir. Bu hatanın diğer bir olası nedeni cihazın uygulamayı desteklememesidir. Örneğin, uygulamaya API'nin 21+ sürümü gerekirken cihazda şu anda API'nin 19 sürümü yüklü olabilir.         Intune bu hatayı hem DA hem de KNOX cihazları için döndürür ve kullanıcının yeniden denemek için tıklayabileceği bir bildirim olabilir ama sorun APK'den kaynaklanıyorsa bir daha hata vermeyecektir. Uygulama kullanılabilir bir uygulamaysa, bu bildirim kapatılabilir. Öte yandan uygulama gerekliyse, kapatılamaz.        |
|    Uygulama yüklemesi, yükleme (APK) dosyası, indirme işleminden sonra ancak yüklemeden önce silindiği için iptal edildi. (0xC7D14FBA)    |    APK'nin indirilmesi başarılı oldu ama kullanıcı uygulamayı yüklemeden önce dosya cihazdan silindi. İndirme ile yükleme arasında çok uzun bir süre geçtiğinde bu durum ortaya çıkabilir. Örneğin, kullanıcının özgün yükleme iptal edildi, beklenen ve daha sonra yeniden denemek için bildirim tıkladı.         Bu hata iletisi yalnızca DA senaryolarında bunu döndürür. KNOX senaryoları sessiz gerçekleştirilebilir. Yeniden denemek için bir bildirim gösteririz, dolayısıyla kullanıcı iptal etmek yerine kabul edebilir. Uygulama kullanılabilir bir uygulamaysa, bu bildirim kapatılabilir. Öte yandan uygulama gerekliyse, kapatılamaz.    |
|    Uygulama yüklemesi, yükleme sırasında işlemin yeniden başlatıldığı için iptal edildi. (0xC7D14FBB)    |    İptal edilen bir yüklemede kaynaklanan APK yükleme işlemi sırasında cihaz yeniden başlatıldı.        Bu hata iletisi hem DA hem de KNOX cihazları için döndürülür. Intune kullanıcıların yeniden denemek için tıklayabileceği bir bildirim gösterir. Uygulama kullanılabilir bir uygulamaysa, bu bildirim kapatılabilir. Öte yandan uygulama gerekliyse, kapatılamaz.    |
|    Bu uygulama, yükleme başarıyla tamamlandıktan sonra algılanmadı. (0x87D1041C)    |    Kullanıcı uygulamayı açıkça kaldırdı. Bu hata istemciden döndürülmedi. Bu, bir noktada uygulama yüklendiğinde ama ardından kullanıcı bu uygulamayı kaldırdığında oluşan bir hatadır. Bu hata, yalnızca gerekli uygulamalar için oluşturulur. Gerekli olmayan uygulamaları kullanıcı kaldırabilir. Bu hata yalnızca DA'da oluşabilir. KNOX, yönetilen uygulamaların kaldırılmasını engeller.       Sonraki eşitlemede kullanıcının yüklemesi için bildirim cihaza yeniden gönderilir.   Kullanıcı bildirimi yoksayabilir. Kullanıcı uygulamayı yükleyene kadar bu hata bildirilmeye devam edecektir.    |
|    Bilinmeyen bir hata nedeniyle indirme başarısız oldu. (0xC7D14FB2)    |    Bu hata indirme başarısız olduğunda oluşur. Bu hata yaygın olarak Wi-Fi sorunlarından veya yavaş bağlantılardan kaynaklanabilir.       Bu hata yalnızca DA senaryolarında döndürülür. KNOX senaryolarında kullanıcılardan yüklemeleri istenmez; bu işlem sessiz olarak yapılabilir. Intune kullanıcıların yeniden denemek için tıklayabileceği bir bildirim gösterir. Uygulama kullanılabilir bir uygulamaysa, bu bildirim kapatılabilir. Öte yandan uygulama gerekliyse, kapatılamaz.    |
|    Bilinmeyen bir hata nedeniyle indirme başarısız oldu. Cihazın bir sonraki eşitlenmesinde ilke yeniden denenecektir. (0xC7D15078)    |    Bu hata indirme başarısız olduğunda oluşur. Bu hata yaygın olarak Wi-Fi sorunlarından veya yavaş bağlantılardan kaynaklanabilir.       Bu hata yalnızca DA senaryolarında döndürülür. KNOX senaryolarında kullanıcılardan yüklemeleri istenmez; bu işlem sessiz olarak yapılabilir.    |
|    Son kullanıcı uygulama yüklemesi iptal edildi. (0xC7D14FB1)    |    Kullanıcı uygulamayı açıkça kaldırdı. Android işletim sistemi yüklediğinizde etkinliği kullanıcı tarafından iptal edildi Bu hata oluşur. İşletim sistemi yükleme istemi gösterildiğinde kullanıcı iptal düğmesine bastı veya istemin dışına tıkladı.        Bu hata yalnızca DA senaryolarında döndürülür. KNOX senaryolarında kullanıcılardan yüklemeleri istenmez; bu işlem sessiz olarak yapılabilir. Intune kullanıcıların yeniden denemek için tıklayabileceği bir bildirim gösterir. Uygulama kullanılabilir bir uygulamaysa, bu bildirim kapatılabilir. Öte yandan uygulama gerekliyse, kapatılamaz.    |
|    Dosya indirme süreci beklenmedik bir şekilde durduruldu. (0xC7D15015)    |    İşletim sistemi, indirme işlemini tamamlanmadan önce durdurdu. Bu hata cihazın pil düzeyi düşük olduğunda veya indirme işlemi fazla uzun sürdüğünde oluşur.       Bu hata yalnızca DA senaryolarında döndürülür. KNOX senaryolarında kullanıcılardan yüklemeleri istenmez; bu işlem sessiz olarak yapılabilir. Intune kullanıcıların yeniden denemek için tıklayabileceği bir bildirim gösterir. Uygulama kullanılabilir bir uygulamaysa, bu bildirim kapatılabilir. Öte yandan uygulama gerekliyse, kapatılamaz.    |
|    Dosya indirme hizmeti beklenmedik bir şekilde durduruldu. Cihazın bir sonraki eşitlenmesinde ilke yeniden denenecektir. (0xC7D1507C)    |    İşletim sistemi, indirme işlemini tamamlanmadan önce durdurdu. Bu hata cihazın pil düzeyi düşük olduğunda veya indirme işlemi fazla uzun sürdüğünde oluşur.       Bu hata yalnızca DA senaryolarında döndürülür. KNOX senaryolarında kullanıcılardan yüklemeleri istenmez; bu işlem sessiz olarak yapılabilir.    |

### <a name="ios-errors"></a>iOS hataları

| Hata iletisi/kodu | Açıklama/sorun giderme ipuçları |
|------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| (0x87D12906) | Apple MDM Aracısı yükleme komutu başarısız olduğunu döndürdü. |
| (0x87D1313C) | Güncelleştirilmiş indirme hizmeti URL'si cihaza gönderilmiştir ancak ağ bağlantısı kaybedildi. Özellikle, belirtilen ana bilgisayar adına sahip bir sunucu bulunamadı. |
| iOS cihazı şu anda meşgul. (0x87D11388) | İOS cihazı, bir hata ile sonuçlandır meşgul. |
| Uygulama yüklemesi başarısız oldu. (0x87D13B64) | Bir uygulama yükleme hatası oluştu. Bu hatayı gidermek için XCODE günlükleri gerekiyor. |
| Uygulama yönetiliyor ancak süresi doldu veya kullanıcı tarafından kaldırıldı. (0x87D13B66) | Kullanıcı, uygulamayı açıkça kaldırılır. Öte yandan, uygulamanın süresi dolmuş ama indirilememiş veya uygulama algılaması cihazdan gelen yanıtla eşleşmiyor da olabilir.   Buna ek olarak, bu hata iOS 9.2.2 platform hatası nedeniyle oluşabilir. |
| Uygulama yüklenmek üzere zamanlandı ancak işlemi tamamlamak için bir kullanım kodu gerekiyor. (0x87D13B60) | Bu hata genellikle hangi uygulamaları Ücretli iOS Store uygulamaları ile oluşur. |
| Yükleme başarıyla tamamlandıktan sonra uygulama algılanmadı.   (0x87D1041C) | Uygulama Algılama işlemi aygıttan yanıt ile eşleşmedi. |
| Kullanıcı, uygulamayı yükleme teklifini reddetti. (0x87D13B62) | İlk uygulama yükleme sırasında tıklanan kullanıcı iptal edin. |
| Kullanıcı, uygulamayı güncelleştirme teklifini reddetti. (0x87D13B63) | Tıklanan son kullanıcı güncelleştirme işlemi sırasında iptal edin. |
| Bilinmeyen hata (0x87D103E8) | Bilinmeyen uygulama yükleme hatası. Diğer hatalar değil oluştuğunda sonuç hatadır. |
| Yalnızca VPP uygulamaları, paylaşılan iPad (-2016330861) üzerinde yükleyebilirsiniz. | Uygulamaları, paylaşılan iPad üzerinde yüklemek için Apple Volume Purchase Program'ı kullanarak elde edilebilir. |
| App Store devre dışı bırakıldığında, uygulama yükleyemeyeceğiniz (-2016330860).  | App Store, kullanıcı uygulamayı yüklemek etkinleştirilmesi gerekir. |
| VPP lisans için (-2016330859) uygulaması bulunamıyor.  | Try iptal etme ve uygulama lisans yeniden atama. |
| Sistemi uygulamaları MDM sağlayıcınız ile (-2016330858) yükleyemezsiniz. | İOS işletim sistemi tarafından yüklenmiş uygulamaları yükleme, desteklenen bir senaryo değildir. |
| Cihaz kayıp modu (-2016330857) olduğunda uygulama yükleyemezsiniz. | Kayıp modu, cihazın tüm kullanımı engellenir.   Uygulamaları yüklemek için kayıp modu devre dışı bırakın. |
| Cihaz bilgi noktası modu (-2016330856) olduğunda uygulama yükleyemezsiniz. | Bu cihaz, uygulama yüklemek için bir dışlama grup için bilgi noktası modu yapılandırma ilkesi için eklemeyi deneyin. |
| 32 bit uygulamaların bu cihaza (-2016330852) yükleyemezsiniz. | Cihaz 32-bit uygulamaları desteklemez. Uygulamasının 64 bit sürümü dağıtmayı deneyin. |
| Kullanıcı App Store (-2016330855) oturum açmanız gerekir. | Kullanıcı, uygulamanın cihaza yüklenmesinden önce App Store için oturum açması gerekiyor. |
| Bilinmeyen bir sorun oluştu. Lütfen yeniden deneyin (-2016330854). | Uygulama yüklemesi, bilinmeyen bir nedenden dolayı başarısız oldu.   Daha sonra tekrar deneyin. |
| Uygulama yüklemesi başarısız oldu. Intune cihaz eşitlemeler (-2016330853) yeniden deneyecek. | Uygulama yüklemesi, bir cihaz hatasıyla karşılaştı. Uygulamayı yeniden yüklemeyi denemek için cihazı eşitleyebilir. |

### <a name="other-installation-errors"></a>Diğer yükleme hataları

|    Hata iletisi/kodu    |    Açıklama    |
|-----------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    0x80073CFF, 0x80CF201C (istemci hatası)    |    Bu uygulamayı yüklemek için dışarıdan yükleme özellikli bir sisteme sahip olmanız gerekir. Uygulama paketinin güvenilir bir imza ile imzalandığından ve sahip etki alanına katılmış bir cihazda yüklü olduğundan emin olun **AllowAllTrustedApps** etkin ilke veya bir Windows dışarıdan yükleme lisansına sahip olan bir cihazda  **AllowAllTrustedApps** etkin ilke. Daha fazla bilgi için [paketleme, dağıtım ve sorgu Windows Store uygulamalarının sorunlarını giderme](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting).     |
|    0x80073CF0    |    Paket açılamadı. Olası nedenler:<ul><li> Paket imzasız.</li><li> Yayımcı adı, imzalama sertifikası konusuyla eşleşmiyor.</li></ul> Denetleme **AppxPackagingOM** bilgi için olay günlüğünü. Daha fazla bilgi için [paketleme, dağıtım ve sorgu Windows Store uygulamalarının sorunlarını giderme](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting).    |
|    0x80073CF3    |    Paket güncelleştirme, bağımlılık veya çakışma doğrulaması başarısız oldu. Olası nedenler:<ul><li> Yüklü bir paketle gelen paket çakışıyor.</li><li> Belirtilen paket bağımlılığı bulunamadı.</li><li> Paket doğru işlemci mimarisini desteklemiyor.</li></ul> Denetleme **AppXDeployment-Server** bilgi için olay günlüğünü. Daha fazla bilgi için [paketleme, dağıtım ve sorgu Windows Store uygulamalarının sorunlarını giderme](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting).    |
|    0x80073CFB    |    Sağlanan paket zaten yüklü ve paketin yeniden yüklenmesi engellendi. Zaten yüklü olan paketten değil bir paket yüklüyorsanız bu hatayı alabilir. Dijital imzanın paketin bir parçası olduğunu da onaylayın. Bir paket yeniden oluşturulduğunda veya yeniden imzalandığında, bu paket artık önceden yüklenmiş paket ile aynı bit düzeyinde değildir. Bu hatayı düzeltmek için kullanılabilecek iki seçenek aşağıda belirtilmiştir:<ul><li> Uygulama sürüm numarasını Artır daha sonra yeniden oluşturun ve paketi yeniden imzalayın.</li><li> Yeni paketi yüklemeden önce sistem üzerindeki her kullanıcı için eski paketi kaldırın.</li></ul> Daha fazla bilgi için [paketleme, dağıtım ve sorgu Windows Store uygulamalarının sorunlarını giderme](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting).    |
|    0x87D1041C    |    Uygulama yükleme başarılı oldu ancak uygulama algılanmadı. Uygulaması Intune tarafından başarıyla dağıtıldı, daha sonra kaldırıldı. Kaldırılmakta uygulama nedenleri şunlardır:<ul><li> Son kullanıcı uygulamayı kaldırıldı.</li><li> Hatalı uygulamalar için hangi cihaz raporları paketinde kimlik bilgileri eşleşmiyor.</li><li>Intune dışında güncelleştirildikten sonra kendi kendini güncelleştirme Msı'ler için uygulama bilgilerini ürün sürümü eşleşmiyor.</li></ul> Kullanıcıya uygulamayı şirket portalından yeniden yüklemesini söyleyin. Sonraki cihaz giriş yaptığında, gerekli uygulamaları'nin otomatik olarak yeniden yüklenecektir unutmayın.    |

## <a name="troubleshooting-apps-from-the-microsoft-store"></a>Microsoft Mağazası'ndan uygulama sorunlarını giderme

[Microsoft Mağazası uygulamalarının paketleme, dağıtım ve sorgu sorunlarını giderme](https://msdn.microsoft.com/library/windows/desktop/hh973484.aspx) konusunda yer alan bilgiler, Intune’u veya diğer araçları kullanarak Microsoft Mağazası’nden uygulama yüklerken karşılaşabileceğiniz genel sorunları gidermenize yardımcı olur.

## <a name="next-steps"></a>Sonraki adımlar

- Ek Intune sorun giderme bilgileri için bkz. [Şirketinizdeki kullanıcılara yardımcı olmak için sorun giderme portalını kullanma](help-desk-operators.md). 
- Microsoft Intune’daki tüm bilinen sorunlar hakkında bilgi edinin. Daha fazla bilgi için bkz. [Microsoft Intune’da bilinen sorunlar](known-issues.md).
- Ek yardım mı gerekiyor? Bkz. [Microsoft Intune için destek alma](get-support.md).
