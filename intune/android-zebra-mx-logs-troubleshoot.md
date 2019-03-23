---
title: Kullanım StageNow günlükleri Microsoft Intune - Azure'da Android Zebra cihazlarda | Microsoft Docs
description: Genel sorunlar ve çözümleri StageNow Intune Android cihazlarda kullanırken bakın. Ayrıca günlükleri alın ve başarı veya Hata günlüklerini okumak örnekleri Bkz öğrenin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/20/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: ''
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5edc528abf5c3cb58200e2d0511fac3220cfad11
ms.sourcegitcommit: 1069b3b1ed593c94af725300aafd52610c7d8f04
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2019
ms.locfileid: "58395255"
---
# <a name="use-stagenow-logs-to-troubleshoot-and-see-potential-issues-on-android-zebra-devices-in-microsoft-intune"></a>Sorun gidermek için StageNow günlüklerini kullanma ve Microsoft Intune Android Zebra cihazları üzerinde olası sorunlara bakın

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Microsoft Intune kullanabileceğiniz [ **Zebra Mobility Uzantıları (MX)** Zebra Android cihazları yönetmek için](android-zebra-mx-overview.md). Zebra cihazlarını kullanırken ayarlarını yönetmek için StageNow profilleri oluşturmak ve bunları Intune'a yükleyin. Intune, cihazlarda ayarları uygulamak için StageNow uygulama kullanır. StageNow uygulama sorunlarını gidermek için kullanılan cihaz ayrıntılı bir günlük dosyası da oluşturur.

Bu özellik şu platformlarda geçerlidir:

- Android

Örneğin, bir cihaz yapılandırma StageNow bir profil oluşturun. StageNow profili oluştururken, son adım profil testi için bir dosya oluşturur. Cihazdaki StageNow uygulaması ile bu dosyayı tükettiğiniz.

Başka bir örnekte StageNow bir profil oluşturmak ve test. Intune, StageNow profili ekleyin ve ardından, Zebra cihazlara atayabilirsiniz. Atanan profil durumu denetlenirken profili üst düzey bir durumu gösterir. Daha fazla ayrıntı kullanmanız gerekir.

Her iki bu durumda, cihazda kaydedilen StageNow profili uygulanır her seferinde hangi StageNow günlük dosyasından daha fazla ayrıntıya ulaşabilirsiniz.

Bu makalede StageNow günlüklerini okumak nasıl gösterir ve Zebra cihazlarla bazı olası sorunları listeler.

[Zebra Mobility uzantıları Zebra cihazları yönetme ve kullanma](android-zebra-mx-overview.md) bu özellik hakkında daha fazla bilgi bulunur.

## <a name="read-the-logs"></a>Günlüklerini okuyun

Günlüklere aranırken bir hata var. gördüğünüz her `<characteristic-error>` etiketi. Hata ayrıntılarını yazılır `<parm-error>` etiket > `desc` özelliği.

## <a name="error-types"></a>Hata türleri

Zebra cihazlar farklı hata raporlama seviyelerini şunlardır:

- CSP, cihaz üzerinde desteklenmiyor. Örneğin, cihaz hücresel cihaz değil ve bir hücresel Yöneticisi yok.
- MX veya OSX sürüm eşleşmiyor. Her CSP sürümlü ' dir. Görmek için tam destek matrisi, [Zebra'nın belgeleri](http://techdocs.zebra.com/mx/) (Zebra'nın web sitesini açar).
- Cihaz başka bir sorun veya hata bildirir.

## <a name="examples"></a>Örnekler

Örneğin, aşağıdaki giriş profil vardır:

```xml
<wap-provisioningdoc>
    <characteristic type="Clock">
        <parm name="AutoTime" value="false"/>
        <parm name="TimeZone" value="GMT-5"/>
        <parm name="Date" value="2014-12-03"/>
        <parm name="Time" value="11:11:11"/>
    </characteristic>
</wap-provisioningdoc>
```

Oturum, XML giriş aynıdır. Eşleşen bu çıkış, herhangi bir hata cihaza başarıyla uygulandı profili anlamına gelir:

```xml
<wap-provisioningdoc>
    <characteristic type="Clock" version="6.0">
        <parm name="AutoTime" value="false"/>
        <parm name="TimeZone" value="GMT-5"/>
        <parm name="Date" value="2014-12-03"/>
        <parm name="Time" value="11:11:11"/>
    </characteristic>
</wap-provisioningdoc>
```

Başka bir örnekte, aşağıdaki giriş vardır:

```xml
<wap-provisioningdoc>
    <characteristic type="XmlMgr" version="4.2" >
        <parm name="ProcessingMode" value="1"/>
    </characteristic>
    <characteristic type="AppMgr" version="4.2" >
        <parm name="Action" value="Install"/>
        <parm name="APK" value="/sdcard/test.apk"/>
    </characteristic>
</wap-provisioningdoc>
```

İçerdiğinden günlük bir hata gösterir. bir `<characteristic-error>` etiketi. Bu senaryoda, profil belirtilen yolda mevcut olmayan bir Android paketin (APK) yüklemeye çalıştı:

```xml
<wap-provisioningdoc>
    <characteristic type="XmlMgr" version="4.2">
        <parm name="ProcessingMode" value="1"/>
    </characteristic>
    <characteristic-error type="AppMgr" version="5.1" desc="missing">
        <parm-error name="Action" value="Install" desc="apk doesnot exist in the path"/>
        <parm name="APK" value="/sdcard/test.apk"/>
    </characteristic-error>
</wap-provisioningdoc>
```

## <a name="potential-issues-with-zebra-devices"></a>Zebra cihazlarla ilgili olası sorunları

Bu bölümde Zebra cihazların cihaz Yöneticisi ile kullanırken çalışabilir olası sorunlar listelenir.

### <a name="android-system-webview-is-out-of-date"></a>Android System WebView'u güncel değil

Eski cihazları Şirket portalı uygulamasını kullanarak oturum açtığınızda, kullanıcılar yükseltilmiş System WebView bileşenin güncel değil ve gerekli bir ileti görebilirsiniz. Cihazda Google Play yüklü, internet ve güncelleştirmeleri denetlemenizi bağlanın. Cihazda yoksa Google Play yüklü, bileşen güncelleştirilmiş sürümü edinmek ve cihazlar için geçerlidir. Veya en son işletim sistemi tarafından Zebra verilen cihazı güncelleştirin.

### <a name="management-actions-take-a-long-time"></a>Zaman yönetimi eylemleri

Google Play Hizmetleri kullanılamaz ise bazı görevlerin tamamlanması 8 saat yararlanın. [Android için Intune sınırlamaları Şirket portalı uygulaması](https://support.microsoft.com/help/3211588/limitations-of-intune-company-portal-app-for-android-in-china) (başka bir Microsoft web sitesi açılır) iyi bir kaynak olabilir.

### <a name="device-spoofing-suspected-shows-in-intune"></a>"Cihaz kimlik sahtekarlığı tespit edildiğinde alınan önlemlerin" Intune'da gösterir

Bu hata Intune Zebra Android cihaz olarak Zebra cihaz üreticisi ve modeli raporlama şüphelendiği anlamına gelir.

### <a name="company-portal-app-is-older-than-minimum-required-version"></a>Şirket portalı uygulaması gereken en düşük sürümden daha eski

Intune Şirket portalı uygulaması, gerekli en düşük sürümü güncelleştirebilir. Google Play cihazda yüklü değilse, Şirket portalı uygulamasını otomatik olarak güncelleştirilmesini değil. Gereken en düşük sürümü yüklü olan sürümden daha yeniyse, Şirket portalı uygulamasını çalışmayı durdurur. En son Şirket portalı uygulamasını kullanarak güncelleştirme [Zebra cihazlara dışarıdan yükleme](android-zebra-mx-overview.md#sideload-the-company-portal-app).

## <a name="next-steps"></a>Sonraki adımlar

[Zebra tartışma panoları](https://developer.zebra.com/community/home/discussions) (Zebra'nın web sitesi açılır)

[Intune'da Zebra Mobility uzantılarıyla Zebra cihazları yönetmek ve kullanın](android-zebra-mx-overview.md)
