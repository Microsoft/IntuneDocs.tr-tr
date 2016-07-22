---
title: "Uygulama dağıtımı sorunlarını giderme | Microsoft Intune"
description: 
keywords: 
author: Nbigman
manager: jeffgilb
ms.date: 05/26/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 28ac298e-fb73-4c1c-b3fd-8336639e05e6
ms.reviewer: mghadial
ms.suite: ems
ms.sourcegitcommit: 327c3aaf42aaf7f97e2b78d5ae38584bc13773e1
ms.openlocfilehash: dc782a54983e4db39a029a15183834a925d0e00c


---

# Microsoft Intune’da uygulama dağıtımı sorunlarını giderme
Bu konu, Microsoft Intune’la uygulama dağıtımı sorunlarını çözmenize yardımcı olur.

Bu bilgiler sorununuzu çözmezse, yardım almanın daha fazla yolunu öğrenmek için bkz. [Microsoft Intune için destek alma](how-to-get-support-for-microsoft-intune.md).


## Normal uygulama dağıtımı sorunları

### Microsoft Intune şirket portalında oturum açamıyorsanız

1.  Hesabınızın [Office 365 portalında](http://go.microsoft.com/fwlink/p/?LinkId=698854) olup olmadığını ve devre dışı bırakılıp bırakılmadığını kontrol edin.

2.  [Office 365 portalında](http://go.microsoft.com/fwlink/p/?LinkId=698854) bu hesabın sizin için sağlandığından emin olun.

3.  [Office 365 portalında](http://go.microsoft.com/fwlink/p/?LinkId=698854), Intune’da oturumu açmak için şu biçimdeki doğru kullanıcı adını ve parolayı kullandığınızdan emin olun: **ali@etkialanı.com**.

### BT İletişim bilgileri şirket portalında yoksa

1.  Intune yönetim konsolunda **Yönetici**&gt;**Şirket Portalı**’nı seçin.

2.   **BT İletişimi** ayrıntılarını ayarlayın.

### Listede belirli uygulamaları göremiyorsanız

1.  Uygulamanın dağıtıldığı bir kullanıcı veya cihazın uygulamalar listesini denetlediğinizden emin olun.

2.  Cihazların uygulama için gereksinimleri karşıladığından emin olun.

### Uygulamayı indirirken hata iletisi alırsanız

1.  Kullanıcı başına aynı anda birden çok indirme işlemi yapılmadığından emin olun. Her kullanıcı aynı anda bir uygulama yükleyebilir.

2.  Hesap başına çok sayıda eş zamanlı indirme olmadığından emin olun. Birkaç dakika bekleyin ve sonra yeniden deneyin.

3.  Yükleme yapamayacağınızı, yüklemenin iptal edildiğini veya yeniden denemeniz gerektiğini bildiren bir iOS yerel iletisi alırsanız bunun nedeni yoğun trafik olabilir. Birkaç dakika bekleyin ve sonra yeniden deneyin.

4.  iOS uygulaması indirme ilerleme çubuğu tamamlanır ancak uygulama yükleme başarısız olursa, sağladığınız uygulama dosyalarıyla ilgili bir sorun olabilir.

### iOS uygulamasının bağlantısı sizi iTunes App Store'daki önceki konumlardan birine geri döndürüyorsa

1.  Geçerli iTunes App Store oturumu önceki uygulama sayfasına açılıyor.

2.  Cihazda iTunes App Store'u kapatın ve bağlantıyı açmayı yeniden deneyin.

### Bir iOS uygulaması başlatılırken hata iletisi alıyorsanız

1.  Uygulamanın sona erme tarihi geçerli olmayabilir.

### Uygulamanız karşıya yüklenirken "sürüyor" durumunda takılıyorsa

1.  Bir uygulama karşıya yüklenirken öncelikle meta veriler, ardından uygulama paketi eklenir. Meta veriler karşıya yüklendikten sonra uygulama sürüyor durumunda görünür. Uygulamanızın aşırı uzun bir süre işlem sürüyor durumunda olduğunu görürseniz uygulamayı silin ve yeniden yükleyin.

2.  Uygulama "sürüyor" durumundayken uygulamanın dağıtımını yönetmediğinizden emin olun.

### Bir iOS uygulaması yüklenirken hatayla karşılaşırsanız

1.  Kuruluşunuzun güvenlik duvarının Apple sağlama ve sertifika web sitelerine erişim izni verdiğinden emin olun.

2.  Daha fazla bilgi için Apple geliştirici belgelerini görüntüleyin.

### Hata: Yayımcı yok
Üçüncü taraf lisans sözleşmesini eklemek için **Başka Yazılım Anlaşması Ekle**’yi kullanıyorsunuz. Yayıncıyı **Diğer yazılım lisanslama anlaşmaları** sayfasından eklemeyi deniyorsunuz. Sayfa, mevcut yayımcıların alfabetik olarak sıralanmış listesini sağlar.
Eksik yayımcıyı giriyorsunuz ancak **Yayımcı yok** hatasını alıyorsunuz. 

Bu, bilinçli olarak böyle tasarlanmıştır. Intune, yalnızca popüler yazılım markaları için lisans izleme sağlar. Intune’da, yazılımın lisanslama iş yükünde bir seçenek olarak sağlanabilmesi için en az 4 ayrı hesap tarafından raporlanması gerekir.

### Yönetilen uygulamalar yükleme durumunu bildirmiyorsa

Kasım 2014'teki Microsoft Intune hizmet güncelleştirmesinden önceki yönetilen uygulama yüklemeleri için yükleme durumu toplanmamıştır. Bu hizmet güncelleştirmesinden önce yönetilen uygulamalar yükleyen cihazlar için, ilişkili uygulama dağıtımlarının her birini uygun dağıtım eylemiyle (örneğin, **Kullanılabilir yükleme**) güncelleştirin. Her cihaz, kullanılabilir uygulamaların otomatik olarak denetlenmesi sırasında uygulamayı güncelleştirir. Daha fazla bilgi için bkz. [Microsoft Intune kullanarak uygulamaları güncelleştirme](/intune/deploy-use/update-apps-using-microsoft-intune).

## <a name="BKMK_SoftDistErrorCodes"></a>Uygulama dağıtımı hata kodları
Aşağıdaki tabloda Intune uygulama dağıtımı sırasında oluşabilecek yaygın hatalar, hataların olası nedenleri ve hataları gidermenizi sağlayabilecek çözümler listelenmektedir.

|Hata kodu|Olası sorun|Önerilen çözüm|
|--------------|--------------------|------------------------|
|0x80073CFF<br /><br />0x80CF201C (istemci hatası)|Bu uygulamayı yüklemek için dışarıdan yükleme özellikli bir sisteme sahip olmanız gerekir.|Uygulama paketinin güvenilir bir imza ile imzalandığından ve AllowAllTrustedApps ilkesi etkinleştirilerek etki alanına katılmış bir cihaza ya da AllowAllTrustedApps (Windows RT cihazı kaydedildiğinde uygulanır) etkin bir Windows Dışarıdan Yükleme lisansına sahip cihaza yüklendiğinden emin olun.|
|0x80073CF0|Paket açılamadı.|Olası nedenler:<br /><br />-   Paket imzasız.<br />-   Yayımcı adı, imzalama sertifikası konusuyla eşleşmiyor.<br /><br />Daha fazla bilgi için AppxPackagingOM olay günlüğünü denetleyin.|
|0x80073CF3|Pakette güncelleştirme, bağımlılık veya çakışma doğrulaması başarısız oldu|Olası nedenler:<br /><br />-   Gelen paket yüklü bir paketle çakışıyor.<br />-   Belirtilen paket bağımlılığı bulunamadı.<br />-   Paket doğru işlemci mimarisini desteklemiyor.<br /><br />Daha fazla bilgi için sunucu AppXDeployment-Server olay günlüğünü denetleyin.|
|0x80073CFB|Belirtilen paket zaten yüklü ve paketin yeniden yüklenmesi engellendi|Zaten yüklü olan paketten farklı bir paket yüklüyorsanız bu hatayı alabilirsiniz. Dijital imzanın paketin bir parçası olduğunu da onaylayın. Bir paket yeniden oluşturulduğunda veya yeniden imzalandığında, bu paket artık önceden yüklenmiş paket ile aynı bit düzeyinde değildir. Bu hatayı düzeltmek için kullanılabilecek iki seçenek aşağıda belirtilmiştir:<br /><br />-   Uygulamanın sürüm sayısını artırın ve ardından paketi yeniden oluşturup yeniden imzalayın.<br />-   Yeni paketi yüklemeden önce sistem üzerindeki her kullanıcı için eski paketi kaldırın.|
|0x87D1041C|Uygulama yükleme başarılı oldu ancak uygulama algılanmadı.|- Kullanıcı, uygulamayı şirket portalından yükledi, ardından doğrudan cihazdan kaldırdı. Uygulamayı şirket portalından yeniden yükleyin.<br /><br />- Intune tarafından algılandığı şekilde bir iş kolu uygulaması sürüm numarası ve cihazda yüklü sürüm arasında bir uyuşmazlık olabilir. Intune'da doğru sürüm olduğundan emin olun ve uygulamayı yeniden yükleyin.|

### Sonraki adımlar
Bu sorun giderme bilgileri işe yaramazsa, [Microsoft Intune için destek alma](how-to-get-support-for-microsoft-intune.md) konusunda açıklandığı gibi Microsoft Desteği ile iletişim kurun.



<!--HONumber=Jul16_HO2-->


