---
title: "Cihaz günlüklerini toplama| Microsoft Intune"
description: 
keywords: 
author: Nbigman
manager: jeffgilb
ms.date: 06/01/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d97fb610-9d88-40e5-bb06-447eec533630
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ac5c66f57194a84580aa495a58e5281683aa1cca
ms.openlocfilehash: 4fc08fcea6cea897b9ddc3d0c00f2d83069f639d


---

# Cihaz günlükleri

Sorun giderme çalışmalarınız kapsamında, kullanıcı cihazlarından günlükleri toplamak isteyebilirsiniz. Günlükleri toplama yönergeleri burada açıklanmaktadır. Normalde, cihaza erişmeniz veya kullanıcıdan günlükleri toplayıp size göndermesini istemeniz gerekebilir. 

### Android günlüğü konumu
Android günlükleri *<Android Device>\Phone\Android\data\com.microsoft.windowsintune.companyportal\files* yolunda yer alır. [Android tanılama veri günlüklerini e-posta kullanarak BT yöneticinize gönderme](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-email-android) konu başlığı altında açıklandığı gibi, kullanıcı günlük dosyalarını size e-postayla da gönderebilir.

### iOS günlükleri

[BT yöneticinize iOS kayıt hatalarını gönderme](/intune/enduser/send-errors-to-your-it-admin-ios) konu başlığı altında açıklandığı gibi, kullanıcı kayıt hatalarını size gönderebilir.

### Mac OS X cihazları

1. **Console** uygulamasını açın.
2. **FILES** altında **system.log** dosyasını seçin.
3. En üstteki menü çubuğunda **File** > **Save a Copy As…** öğesini seçin ve dosyayı kaydedin.

### Windows Phone

**Windows Phone Şirket Portalı**’nda, kullanıcının **…** düğmesini seçerek menüye erişmesi ve sonra da **Günlükleri Gönder**’i seçmesi gerekir. Bu seçenek hem portalda oturum açmadan önce hem de oturum açtıktan sonra kullanılabilir.

### Windows

Windows Şirket Portalı’nda günlükler *%localappdata%\Packages\Microsoft.CompanyPortal_8wekyb3d8bbwe\LocalState* yolunda yer alır.



<!--HONumber=Jul16_HO3-->


