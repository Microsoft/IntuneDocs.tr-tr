---
title: Uygulama yükleme sorunlarını giderme
titlesuffix: Microsoft Intune
description: Uygulama yükleme sorunlarını gidermenize yardımcı olması için Microsoft Intune sorun giderme bölmesini kullanın.
keywords: ''
author: ErikRe
ms.author: erikre
manager: dougeby
ms.date: 08/29/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: b613f364-0150-401f-b9b8-2b09470b34f4
ms.reviewer: mghadial
ms.custom: intune-azure
ms.openlocfilehash: 80b6828f4768ff79f86532ef0d39ff2100b0ef25
ms.sourcegitcommit: 11cad61c565c474a8d653181675cc1109d562626
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43241720"
---
# <a name="troubleshoot-app-installation-issues"></a>Uygulama yükleme sorunlarını giderme

Microsoft Intune MDM ile yönetilen cihazlarda bazen uygulama yüklemeleri başarısız olabilir. Bu uygulamaların yüklemesi başarısız olduğunda, başarısızlık sebebini anlamak ve sorunu gidermek zor olabilir. Microsoft Intune, kullanıcı yardım isteklerini ele almak yardım masası operatörleri ve Intune yöneticilerinin uygulama bilgilerini görüntülemek için uygulama yükleme hatası ayrıntıları sağlar. Intune içindeki sorun giderme bölmesi, kullanıcının cihazında yönetilen uygulamalar dahil hata ayrıntılarını sağlar. Bir uygulamanın uçtan uca yaşam döngüsü hakkındaki ayrıntıları, **Yönetilen Uygulamalar** bölmesinde her bir cihaz altında sağlanır. Uygulamanın ne zaman yüklendiği, değiştirildiği, hedeflendiği ve bir cihaza teslim edildiği gibi yükleme sorunlarını görüntüleyebilirsiniz. 

## <a name="to-review-app-troubleshooting-details"></a>Uygulama sorun giderme ayrıntılarını gözden geçirmek için

Intune, belirli bir kullanıcının cihazında yüklü uygulamalar temelinde sorun giderme ayrıntıları sağlar.

1. [Azure portalında](https://portal.azure.com) oturum açın.
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

## <a name="app-installation-errors"></a>Uygulama yükleme hataları

Aşağıdaki hata iletileri ve açıklamaları, Android ve iOS yükleme hataları hakkında ayrıntılar sağlar. 

### <a name="android-errors"></a>Android hataları

|    Hata iletisi/kodu    |    Description    |
|----------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Uygulama yüklenemedi. (0xC7D14FB5)    |    Bu hata iletisi Intune Android uygulama yükleme hatasının kök nedenini saptayamadığında görüntülenir. Hata sırasında Android tarafından hiç bilgi sağlanmadı.       APK indirme başarılı olduğunda ama uygulama yüklemesi yapılamadığında bu hata döndürülür. Bu hata yaygın olarak cihaza yüklenemeyen bozuk bir APK dosyasından kaynaklanıyor olabilir. Olası nedenlerinden biri, Google Play Koruması'nın güvenlik nedenleriyle uygulamanın yüklenmesini engellemesidir. Bu hatanın diğer bir olası nedeni cihazın uygulamayı desteklememesidir. Örneğin, uygulamaya API'nin 21+ sürümü gerekirken cihazda şu anda API'nin 19 sürümü yüklü olabilir.         Intune bu hatayı hem DA hem de KNOX cihazları için döndürür ve kullanıcının yeniden denemek için tıklayabileceği bir bildirim olabilir ama sorun APK'den kaynaklanıyorsa bir daha hata vermeyecektir. Uygulama kullanılabilir bir uygulamaysa, bu bildirim kapatılabilir. Öte yandan uygulama gerekliyse, kapatılamaz.        |
|    Yükleme (APK) dosyası, indirme işleminden sonra ancak yüklemeden önce silindiği için uygulamayı yükleme iptal edildi. (0xC7D14FBA)    |    APK'nin indirilmesi başarılı oldu ama kullanıcı uygulamayı yüklemeden önce dosya cihazdan silindi. İndirme ile yükleme arasında çok uzun bir süre geçtiğinde bu durum ortaya çıkabilir. Örneğin, kullanıcı özgün yüklemeyi iptal etmiş, beklemiş ve ardından yeniden denemek için bildirime tıklamıştır.         Bu hata iletisi yalnızca DA senaryolarında bunu döndürür. KNOX senaryoları sessiz gerçekleştirilebilir. Yeniden denemek için bir bildirim gösteririz, dolayısıyla kullanıcı iptal etmek yerine kabul edebilir. Uygulama kullanılabilir bir uygulamaysa, bu bildirim kapatılabilir. Öte yandan uygulama gerekliyse, kapatılamaz.    |
|    Uygulamayı yükleme işlemi, yükleme sırasında süreç yeniden başlatıldığı için iptal edildi. (0xC7D14FBB)    |    APK yükleme işleminde cihaz yeniden başlatıldı ve sonuçta bu yüklemenin iptal edilmesine neden oldu.        Bu hata iletisi hem DA hem de KNOX cihazları için döndürülür. Intune kullanıcıların yeniden denemek için tıklayabileceği bir bildirim gösterir. Uygulama kullanılabilir bir uygulamaysa, bu bildirim kapatılabilir. Öte yandan uygulama gerekliyse, kapatılamaz.    |
|    Bu uygulama, yükleme başarıyla tamamlandıktan sonra algılanmadı. (0x87D1041C)    |    Kullanıcı uygulamayı açıkça kaldırdı. Bu hata istemciden döndürülmedi. Bu, bir noktada uygulama yüklendiğinde ama ardından kullanıcı bu uygulamayı kaldırdığında oluşan bir hatadır. Bu hata, yalnızca gerekli uygulamalar için oluşturulur. Gerekli olmayan uygulamaları kullanıcı kaldırabilir. Bu hata yalnızca DA'da oluşabilir. KNOX, yönetilen uygulamaların kaldırılmasını engeller.       Sonraki eşitlemede kullanıcının yüklemesi için bildirim cihaza yeniden gönderilir.   Kullanıcı bildirimi yoksayabilir. Kullanıcı uygulamayı yükleyene kadar bu hata bildirilmeye devam edecektir.    |
|    Bilinmeyen bir hata nedeniyle indirme başarısız oldu. (0xC7D14FB2)    |    Bu hata indirme başarısız olduğunda oluşur. Bu hata yaygın olarak Wi-Fi sorunlarından veya yavaş bağlantılardan kaynaklanabilir.       Bu hata yalnızca DA senaryolarında döndürülür. KNOX senaryolarında kullanıcılardan yüklemeleri istenmez; bu işlem sessiz olarak yapılabilir. Intune kullanıcıların yeniden denemek için tıklayabileceği bir bildirim gösterir. Uygulama kullanılabilir bir uygulamaysa, bu bildirim kapatılabilir. Öte yandan uygulama gerekliyse, kapatılamaz.    |
|    Bilinmeyen bir hata nedeniyle indirme başarısız oldu. Cihazın bir sonraki eşitlenmesinde ilke yeniden denenecektir. (0xC7D15078)    |    Bu hata indirme başarısız olduğunda oluşur. Bu hata yaygın olarak Wi-Fi sorunlarından veya yavaş bağlantılardan kaynaklanabilir.       Bu hata yalnızca DA senaryolarında döndürülür. KNOX senaryolarında kullanıcılardan yüklemeleri istenmez; bu işlem sessiz olarak yapılabilir.    |
|    Son kullanıcı, uygulama yüklemesini iptal etti. (0xC7D14FB1)    |    Kullanıcı uygulamayı açıkça kaldırdı. Bu hata, Android işletim sistemi yükleme etkinliği kullanıcı tarafından iptal edildiğinde döndürülür. İşletim sistemi yükleme istemi gösterildiğinde kullanıcı iptal düğmesine bastı veya istemin dışına tıkladı.        Bu hata yalnızca DA senaryolarında döndürülür. KNOX senaryolarında kullanıcılardan yüklemeleri istenmez; bu işlem sessiz olarak yapılabilir. Intune kullanıcıların yeniden denemek için tıklayabileceği bir bildirim gösterir. Uygulama kullanılabilir bir uygulamaysa, bu bildirim kapatılabilir. Öte yandan uygulama gerekliyse, kapatılamaz.    |
|    Dosya indirme süreci beklenmedik bir şekilde durduruldu. (0xC7D15015)    |    İşletim sistemi, indirme işlemini tamamlanmadan önce durdurdu. Bu hata cihazın pil düzeyi düşük olduğunda veya indirme işlemi fazla uzun sürdüğünde oluşur.       Bu hata yalnızca DA senaryolarında döndürülür. KNOX senaryolarında kullanıcılardan yüklemeleri istenmez; bu işlem sessiz olarak yapılabilir. Intune kullanıcıların yeniden denemek için tıklayabileceği bir bildirim gösterir. Uygulama kullanılabilir bir uygulamaysa, bu bildirim kapatılabilir. Öte yandan uygulama gerekliyse, kapatılamaz.    |
|    Dosya indirme hizmeti beklenmedik bir şekilde durduruldu. Cihazın bir sonraki eşitlenmesinde ilke yeniden denenecektir. (0xC7D1507C)    |    İşletim sistemi, indirme işlemini tamamlanmadan önce durdurdu. Bu hata cihazın pil düzeyi düşük olduğunda veya indirme işlemi fazla uzun sürdüğünde oluşur.       Bu hata yalnızca DA senaryolarında döndürülür. KNOX senaryolarında kullanıcılardan yüklemeleri istenmez; bu işlem sessiz olarak yapılabilir.    |

### <a name="ios-errors"></a>iOS hataları

|    Hata iletisi/kodu    |    Description    |
|:----------------------------------------------------------------------------------------------------------------------:|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
|    (0x87D12906)    |    Apple MDM Aracısı yükleme komutunun başarısız olduğu bilgisini döndürdü.        |
|    (0x87D1313C)    |    Güncelleştirilmiş indirme hizmeti URL'si cihaza gönderilirken ağ bağlantısı koptu. Özel olarak, belirtilen konak adına sahip sunucu bulunamadı.    |
|    iOS cihazı şu anda meşgul. (0x87D11388)    |    İOS cihazının meşgul olması nedeniyle bir hata oluştu.    |
|    Uygulama yüklemesi başarısız oldu. (0x87D13B64)    |    Uygulama yükleme hatası oluştu. Bu hatayı gidermek için XCODE günlükleri gerekiyor.    |
|    Uygulama yönetiliyor, ama süresi doldu veya kullanıcı tarafından kaldırıldı. (0x87D13B66)    |    Kullanıcı uygulamayı açıkça kaldırdı. Öte yandan, uygulamanın süresi dolmuş ama indirilememiş veya uygulama algılaması cihazdan gelen yanıtla eşleşmiyor da olabilir.   Buna ek olarak, bu hata iOS 9.2.2 platform hatası nedeniyle oluşabilir.    |
|    Uygulama yüklenmek üzere zamanlandı, ancak işlemi tamamlamak için bir kullanım kodu gerekiyor.   (0x87D13B60)    |    Bu hata normalde ücretli uygulamalar olan iOS Store uygulamalarıyla oluşur.     |
|    Bu uygulama, yükleme başarıyla tamamlandıktan sonra algılanmadı. (0x87D1041C)    |    Uygulama algılama işlemi cihazdan gelen yanıtla eşleşmedi.    |
|    Kullanıcı, uygulamayı yükleme teklifini reddetti. (0x87D13B62)    |    İlk uygulama yükleme sırasında kullanıcı iptal düğmesine tıkladı.    |
|    Kullanıcı, uygulamayı güncelleştirme teklifini reddetti. (0x87D13B63)    |    Güncelleştirme işlemi sırasında son kullanıcı iptal düğmesine tıkladı.     |
|    Bilinmeyen hata (0x87D103E8)    |    Bilinmeyen uygulama yükleme hatası oluştu. Bu, diğer hatanın oluşması sonucu ortaya çıkan hatadır.    |


## <a name="next-steps"></a>Sonraki adımlar

- Ek Intune sorun giderme bilgileri için bkz. [Şirketinizdeki kullanıcılara yardımcı olmak için sorun giderme portalını kullanma](help-desk-operators.md). 
- Microsoft Intune’daki tüm bilinen sorunlar hakkında bilgi edinin. Daha fazla bilgi için bkz. [Microsoft Intune’da bilinen sorunlar](known-issues.md).
- Ek yardım mı gerekiyor? Bkz. [Microsoft Intune için destek alma](get-support.md).
