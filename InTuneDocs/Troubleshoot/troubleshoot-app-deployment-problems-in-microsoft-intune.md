---
title: "Uygulama dağıtımı sorunlarını giderme | Microsoft Intune"
description: "Bu konu, Microsoft Intune’la uygulama dağıtımı sorunlarını çözmenize yardımcı olur."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 08/02/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 28ac298e-fb73-4c1c-b3fd-8336639e05e6
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: aa96cf3a1909e3ea2187a3beb0aede3228894504
ms.openlocfilehash: 9f4b91bd523c82665bcac54902b2e8cc9c72ef75


---

# Microsoft Intune’da uygulama dağıtımı sorunlarını giderme
Intune ile uygulamalarınızı dağıtma ve yönetme konusunda sorun yaşıyorsanız buradan başlayın. Bu konuda, karşılaşabileceğiniz bazı yaygın sorunlar çözümleriyle birlikte sunulmuştur.

## Yaygın uygulama dağıtım sorunları

### Şirket Portalı’nda BT iletişim bilgileri yok

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


### Uygulamanız karşıya yüklenirken "sürüyor" durumunda takılıyorsa

1.  Bir uygulama karşıya yüklenirken öncelikle meta veriler, ardından uygulama paketi eklenir. Meta veriler karşıya yüklendikten sonra uygulama sürüyor durumunda görünür. Uygulamanızın aşırı uzun bir süre işlem sürüyor durumunda olduğunu görürseniz uygulamayı silin ve yeniden yükleyin.

2.  Uygulama "sürüyor" durumundayken uygulamanın dağıtımını yönetmediğinizden emin olun.

### Bir iOS uygulaması yüklenirken hatayla karşılaşırsanız

1.  Kuruluşunuzun güvenlik duvarının Apple sağlama ve sertifika web sitelerine erişim izni verdiğinden emin olun.

2.  Daha fazla bilgi için Apple geliştirici belgelerini görüntüleyin.

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
|0x87D1041C|Uygulama yükleme başarılı oldu ancak uygulama algılanmadı.|- Uygulama Intune tarafından başarıyla dağıtıldı, daha sonra (olasılıkla son kullanıcı tarafından) kaldırıldı. Kullanıcıya uygulamayı şirket portalından yeniden yüklemesini söyleyin. Gerekli uygulamalar, cihazın bir sonraki oturum açısında otomatik olarak yüklenir.|

### Sonraki adımlar
Bu sorun giderme bilgileri işe yaramazsa, [Microsoft Intune için destek alma](how-to-get-support-for-microsoft-intune.md) konusunda açıklandığı gibi Microsoft Desteği ile iletişim kurun.



<!--HONumber=Aug16_HO5-->


