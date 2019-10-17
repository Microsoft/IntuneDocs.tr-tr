---
title: Microsoft Intune-Azure 'da Android Zeköşeli cihazlarda StageNow günlüklerini kullanma | Microsoft Docs
description: Microsoft Intune ile Android cihazlarda StageNow kullanırken karşılaşılan yaygın sorunlar ve çözümleri bölümüne bakın. Ayrıca günlükleri nasıl alabileceğinizi öğrenin ve başarılı veya hatalara yönelik günlüklerin nasıl okunduğunu gösteren örneklere bakın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/26/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: ''
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e7ed93c86d3fbe7ed7a6ac5d4b1a3494fb55f2bc
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72506996"
---
# <a name="troubleshoot-and-see-potential-issues-on-android-zebra-devices-in-microsoft-intune"></a>Microsoft Intune Android Zeköşeli cihazlarda sorun giderme ve olası sorunları görme

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Microsoft Intune, [Zeköşeli Mobility uzantıları 'nı (MX) kullanarak Android zezemi cihazlarını yönetebilirsiniz](android-zebra-mx-overview.md). Zeköşeli cihazları kullanırken, ayarları yönetmek ve Intune 'a yüklemek için StageNow 'da Profiller oluşturun. Intune, ayarları cihazlara uygulamak için StageNow uygulamasını kullanır. StageNow uygulaması, sorun gidermek için kullanılan cihazda ayrıntılı bir günlük dosyası da oluşturur.

Bu özellik şu platformlarda geçerlidir:

- Android

Örneğin, bir cihazı yapılandırmak için StageNow 'da bir profil oluşturursunuz. StageNow profilini oluşturduğunuzda, son adım profili test etmeniz için bir dosya oluşturur. Bu dosyayı cihazdaki StageNow uygulamasıyla kullanırsınız.

Başka bir örnekte, StageNow 'da bir profil oluşturur ve test edin. Intune 'da StageNow profilini ekleyin ve ardından Zeköşeli cihazlarınıza atayın. Atanan profilin durumu denetlenirken profil, üst düzey bir durumu gösterir.

Her iki durumda da, bir StageNow profili her seferinde cihaza kaydedilen StageNow günlük dosyasından daha ayrıntılı bilgi edinebilirsiniz.

Bazı sorunlar StageNow profilinin içeriğiyle ilgili değildir ve günlüklere yansıtılmaz.

Bu makale, StageNow günlüklerinin nasıl okunacağını gösterir ve günlüklerde yansıtılmamış olan Zeköşeli cihazlarla ilgili diğer olası sorunları listeler.

Zeköşeli [Mobility uzantıları Ile zeköşeli cihazlarını kullanın ve yönetin](android-zebra-mx-overview.md) bu özellik hakkında daha fazla bilgi içerir.

## <a name="get-the-logs"></a>Günlükleri al

### <a name="use-the-stagenow-app-on-the-device"></a>Cihazda StageNow uygulamasını kullanma
' De bilgisayarınızda StageNow kullanarak doğrudan bir profil test ettiğinizde, [profili dağıtmak Için Intune](android-zebra-mx-overview.md#step-4-create-a-device-management-profile-in-stagenow)kullanmak yerine cihazdaki stagenow uygulaması, günlükleri testten kaydeder. Günlük dosyasını almak için, cihazdaki StageNow uygulamasında **daha fazla (...)** seçeneğini kullanın.

### <a name="get-logs-using-android-debug-bridge"></a>Android Debug Bridge kullanarak günlükleri al
Profil zaten Intune ile dağıtıldıktan sonra günlükleri almak için cihazı [Android Debug Bridge (ADB)](https://developer.android.com/studio/command-line/adb) olan bir bilgisayara bağlayın (Android 'in Web sitesini açar).

Cihazda Günlükler @no__t kaydedilir-0

### <a name="get-logs-from-email"></a>E-postadaki günlükleri al
Profil Intune ile zaten dağıtıldıktan sonra günlükleri almak için, son kullanıcılar cihazdaki bir e-posta uygulaması kullanarak günlüklere e-posta gönderebilir. Zeköşeli cihazda Şirket Portalı uygulamasını açın ve [günlükleri gönderin](https://docs.microsoft.com/intune-user-help/send-logs-to-your-it-admin-by-email-android). Günlükleri Gönder özelliğinin kullanılması, Microsoft desteği 'ne başvurduğunuzda başvurduğunuzda kullanabileceğiniz bir Powerasansör olay KIMLIĞI de oluşturur.

## <a name="read-the-logs"></a>Günlükleri okuyun

Günlüklere baktığınızda, `<characteristic-error>` etiketini her gördüğünüzde bir hata vardır. Hata ayrıntıları `desc` özelliğine > `<parm-error>` etiketine yazılır.

## <a name="error-types"></a>Hata türleri

Zeköşeli cihazlar farklı hata raporlama düzeyleri içerir:

- CSP cihazda desteklenmiyor. Örneğin, cihaz bir hücresel cihaz değildir ve hücresel Yöneticisi yoktur.
- MX veya OSX sürümü eşleşmiyor. Her CSP sürümü oluşturulur. Tam destek matrisi için bkz. [Zela 'nın belgeleri](http://techdocs.zebra.com/mx/) (Zela 'nın Web sitesini açar).
- Cihaz başka bir sorun veya hata bildiriyor.

## <a name="examples"></a>Örnekler

Örneğin, aşağıdaki giriş profiline sahipsiniz:

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

Günlükte XML, girişle aynıdır. Bu eşleşen çıkış, profilin cihaza başarıyla uygulandığı anlamına gelir ve hata yok:

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

Başka bir örnekte, aşağıdaki girişe sahipsiniz:

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

Günlük, `<characteristic-error>` etiketi içerdiğinden bir hata gösterir. Bu senaryoda profil, belirtilen yolda mevcut olmayan bir Android paketini (APK) yüklemeye çalıştı:

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

## <a name="other-potential-issues-with-zebra-devices"></a>Zeköşeli cihazlarıyla ilgili diğer olası sorunlar

Bu bölümde, Zeköşeli cihazları cihaz yöneticisiyle kullanırken görebileceğiniz diğer olası sorunlar listelenmektedir. Bu sorunlar StageNow günlüklerinde bildirilmemektedir.

### <a name="android-system-webview-is-out-of-date"></a>Android System WebView güncel değil

Eski cihazlar Şirket Portalı uygulamasını kullanarak oturum açtığında, kullanıcılar sistem Web görünümü bileşeninin güncel olmadığını ve yükseltilmesi gerektiğini belirten bir ileti görebilirler. Cihazda Google Play yüklüyse, internet 'e bağlayın ve güncelleştirmeleri denetleyin. Cihazda yüklü Google Play yoksa, bileşenin güncelleştirilmiş sürümünü alın ve cihazlara uygulayın. Veya, Zeköşeli tarafından verilen en son cihaz işletim sistemine güncelleştirin.

### <a name="management-actions-take-a-long-time"></a>Yönetim eylemleri uzun zaman alabilir

Google Play hizmetleri yoksa, bazı görevlerin tamamlanması 8 saate kadar sürer. [Android için Intune şirket portalı uygulamasının sınırlamaları](https://support.microsoft.com/help/3211588/limitations-of-intune-company-portal-app-for-android-in-china) (başka bir Microsoft Web sitesini açar) iyi bir kaynak olabilir.

### <a name="device-spoofing-suspected-shows-in-intune"></a>Intune 'da "cihaz yanıltma şüpheli" gösteriliyor

Bu hata, Intune 'un bir zekesiz Android cihazı, modelini ve üreticisini bir Zeköşeli cihaz olarak raporlamadığını gösterir.

### <a name="company-portal-app-is-older-than-minimum-required-version"></a>Şirket Portalı uygulama en düşük gerekli sürümden daha eski

Intune, Şirket Portalı uygulamasının gerekli en düşük sürümünü güncelleştirebilir. Cihazda Google Play yüklü değilse, Şirket Portalı uygulama otomatik olarak güncellenmez. Gerekli en düşük sürüm yüklü sürümden daha yeniyse Şirket Portalı uygulama çalışmayı durduruyor. [Zeköşeli cihazlarda dışarıdan yükleme](android-zebra-mx-overview.md#sideload-the-company-portal-app)kullanarak en son Şirket Portalı uygulamasına güncelleştirin.

## <a name="next-steps"></a>Sonraki adımlar

[Zeköşeli tartışma panoları](https://developer.zebra.com/community/home/discussions) (zeköşeli 'ın Web sitesini açar)

[Intune 'da Zeköşeli Mobility uzantıları ile Zeköşeli cihazları kullanma ve yönetme](android-zebra-mx-overview.md)
