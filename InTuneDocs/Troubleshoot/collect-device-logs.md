---
title: "Cihaz günlüklerini toplama| Microsoft Intune"
description: "Yönetilen cihazlarınızdan günlük toplamayı öğrenin."
keywords: 
author: staciebarker
ms.author: staciebarker
manager: angrobe
ms.date: 10/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d97fb610-9d88-40e5-bb06-447eec533630
ms.reviewer: esmich
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 3a081109cd499d3bdda75cb6c8a4dab9d9d28fab
ms.openlocfilehash: ec7d522e8dcff66d1b84fed3c4c0cc708e555e67


---

# <a name="device-logs"></a>Cihaz günlükleri

Sorun giderme çalışmalarınız kapsamında, kullanıcı cihazlarından günlükleri toplamak isteyebilirsiniz. Günlükleri toplama yönergeleri burada açıklanmaktadır. Normalde, cihaza erişmeniz veya kullanıcıdan günlükleri toplayıp size göndermesini istemeniz gerekebilir.

### <a name="android-log-location"></a>Android günlüğü konumu
Android günlükleri *<Android Device>\Phone\Android\data\com.microsoft.windowsintune.companyportal\files* yolunda yer alır. [Android tanılama veri günlüklerini e-posta kullanarak BT yöneticinize gönderme](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-email-android) konu başlığı altında açıklandığı gibi, kullanıcı günlük dosyalarını size e-postayla da gönderebilir.

### <a name="ios-logs"></a>iOS günlükleri

[BT yöneticinize iOS kayıt hatalarını gönderme](/intune/enduser/send-errors-to-your-it-admin-ios) konu başlığı altında açıklandığı gibi, kullanıcı kayıt hatalarını size gönderebilir.

### <a name="mac-os-x-devices"></a>Mac OS X cihazları

1. **Console** uygulamasını açın.
2. **FILES** altında **system.log** dosyasını seçin.
3. En üstteki menü çubuğunda **File** > **Save a Copy As…** öğesini seçin ve dosyayı kaydedin.

### <a name="windows-phone"></a>Windows Phone

**Windows Phone Şirket Portalı**’nda, kullanıcının **…** düğmesini seçerek menüye erişmesi ve sonra da **Günlükleri Gönder**’i seçmesi gerekir. Bu seçenek hem portalda oturum açmadan önce hem de oturum açtıktan sonra kullanılabilir.

### <a name="windows"></a>Windows

Windows Şirket Portalı’nda günlükler *%localappdata%\Packages\Microsoft.CompanyPortal_8wekyb3d8bbwe\LocalState* yolunda yer alır.



<!--HONumber=Oct16_HO3-->


