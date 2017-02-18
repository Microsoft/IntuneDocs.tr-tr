---
title: "Uygulama dağıtımı sorunlarını giderme | Microsoft Docs"
description: "Bu konu, Microsoft Intune’la uygulama dağıtımı sorunlarını çözmenize yardımcı olur."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 09/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 28ac298e-fb73-4c1c-b3fd-8336639e05e6
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 239371198cbbc01b1345c72b3f887055acd44462


---

# <a name="troubleshoot-app-deployment-problems-in-microsoft-intune"></a>Microsoft Intune’da uygulama dağıtımı sorunlarını giderme

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune ile uygulamalarınızı dağıtma ve yönetme konusunda sorun yaşıyorsanız buradan başlayın. Bu konuda, karşılaşabileceğiniz bazı yaygın sorunlar çözümleriyle birlikte sunulmuştur.

## <a name="common-app-deployment-error-codes"></a>Yaygın uygulama dağıtımı hata kodları

|Hata kodu|Olası sorun|Önerilen çözüm|
|--------------|--------------------|------------------------|
|0x80073CFF<br /><br />0x80CF201C (istemci hatası)|Bu uygulamayı yüklemek için dışarıdan yükleme özellikli bir sisteme sahip olmanız gerekir.|Uygulama paketinin güvenilir bir imza ile imzalandığından ve AllowAllTrustedApps ilkesi etkinleştirilerek etki alanına katılmış bir cihaza ya da AllowAllTrustedApps etkin bir Windows Dışarıdan Yükleme lisansına sahip cihaza yüklendiğinden emin olun.|
|0x80073CF0|Paket açılamadı.|Olası nedenler:<br /><br />-   Paket imzasız.<br />-   Yayımcı adı, imzalama sertifikası konusuyla eşleşmiyor.<br /><br />Daha fazla bilgi için AppxPackagingOM olay günlüğünü denetleyin.|
|0x80073CF3|Pakette güncelleştirme, bağımlılık veya çakışma doğrulaması başarısız oldu|Olası nedenler:<br /><br />-   Gelen paket yüklü bir paketle çakışıyor.<br />-   Belirtilen paket bağımlılığı bulunamadı.<br />-   Paket doğru işlemci mimarisini desteklemiyor.<br /><br />Daha fazla bilgi için sunucu AppXDeployment-Server olay günlüğünü denetleyin.|
|0x80073CFB|Belirtilen paket zaten yüklü ve paketin yeniden yüklenmesi engellendi|Zaten yüklü olan paketten farklı bir paket yüklüyorsanız bu hatayı alabilirsiniz. Dijital imzanın paketin bir parçası olduğunu da onaylayın. Bir paket yeniden oluşturulduğunda veya yeniden imzalandığında, bu paket artık önceden yüklenmiş paket ile aynı bit düzeyinde değildir. Bu hatayı düzeltmek için kullanılabilecek iki seçenek aşağıda belirtilmiştir:<br /><br />-   Uygulamanın sürüm sayısını artırın ve ardından paketi yeniden oluşturup yeniden imzalayın.<br />-   Yeni paketi yüklemeden önce sistem üzerindeki her kullanıcı için eski paketi kaldırın.|
|0x87D1041C|Uygulama yükleme başarılı oldu ancak uygulama algılanmadı.|- Uygulama Intune tarafından başarıyla dağıtıldı, daha sonra (olasılıkla son kullanıcı tarafından) kaldırıldı. Kullanıcıya uygulamayı şirket portalından yeniden yüklemesini söyleyin. Gerekli uygulamalar, cihazın bir sonraki oturum açısında otomatik olarak yüklenir.|

## <a name="troubleshooting-apps-from-the-windows-store"></a>Windows Mağazası'ndan uygulama sorunlarını giderme

[Windows Mağazası uygulamalarının paketleme, dağıtım ve sorgu sorunlarını giderme](https://msdn.microsoft.com/library/windows/desktop/hh973484.aspx) konusunda yer alan bilgiler, Intune’u veya diğer araçları kullanarak Windows Mağazası’nden uygulama yüklerken karşılaşabileceğiniz genel sorunları gidermenize yardımcı olur.

## <a name="troubleshooting-app-deployment-to-pcs-managed-by-the-intune-software-client"></a>Intune yazılım istemcisi tarafından yönetilen bilgisayarlara uygulama dağıtımı sorunlarını giderme
Intune yazılım istemcisi tarafından yönetilen bilgisayarlara uygulama dağıtımı sorunlarını gidermenize yardımcı olması için aşağıdaki iki günlük dosyasına göz atabilirsiniz:
- %ProgramFiles%\Microsoft\OnlineManagement\Logs klasörü
- %ProgramFiles%\Microsoft\OnlineManagement\Updates\ReportingEvents.log

Ayrıca, Intune için destek talebinde bulunmanız gerekiyorsa, bu günlükleri Microsoft'a göndermek de faydalı olacaktır.


### <a name="next-steps"></a>Sonraki adımlar
Bu sorun giderme bilgileri işe yaramazsa, [Microsoft Intune için destek alma](how-to-get-support-for-microsoft-intune.md) konusunda açıklandığı gibi Microsoft Desteği ile iletişim kurun.



<!--HONumber=Dec16_HO2-->


