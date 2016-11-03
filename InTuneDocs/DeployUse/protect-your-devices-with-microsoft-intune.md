---
title: "Cihazları koruma | Microsoft Intune"
description: "Intune’un cihazlarınızı yetkisiz erişime veya diğer tehditlere karşı korumanıza yardımcı olabileceği yollardan bazılarını öğrenin."
keywords: 
author: Robstackmsft
manager: angrobe
ms.date: 09/01/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 71e0cbf3-2bfb-412e-8a12-8503df08b4cf
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 3e761ed60fe3df81061023aa31e0545aeeadd316
ms.openlocfilehash: be5051c46e1ef04ea140c9d440720f570edcbd1e


---

# Cihazları Microsoft Intune ile koruma

Microsoft Intune, yönettiğiniz cihazları ve bu cihazlarda depolanan verileri korumaya yardımcı olmak için tam özellik kümesi sunar. Bu özelliklerin temellerini ve daha fazla nasıl bilgi bulacağınızı öğrenmek için bu konuyu okuyun.

## Tüm cihazları korumanın genel yolları

### Cihaz yapılandırması
Intune [yapılandırma ilkeleri](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md), çeşitli ayar ve özellikleri denetleyerek cihazları korumanıza ve yapılandırmanıza yardımcı olur. Örneğin:
- Cihazdaki kamera veya Bluetooth gibi donanım özelliklerinin kullanımını kısıtlayabilirsiniz.
- Uyumlu ve uyumsuz uygulamaları yapılandırabilirsiniz. Uyumsuz bir uygulama yüklenirse size uyarı verilir (ve bazı platformlar yüklemeyi engelleyebilir).

### Kullanıcılar kilitlenen cihazlarına erişemediğinde geçiş kodlarını sıfırlama
Mobil cihazlarda şirket verilerini korumanın ilk adımı cihazı kullanmak için bir geçiş kodu istenmesi olduğundan, bazen bir [geçiş kodunu sıfırlamanız](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) ya da geçiş kodunu kaldırarak veya uzaktan geçici geçiş kodu ayarlayarak bir çalışana kodu sıfırlaması için yardımcı olmanız gerekir. Ayrıca, kaybedilirse veya çalınırsa [bir cihazı uzaktan kilitleyebilirsiniz.](use-remote-lock-and-passcode-reset-in-microsoft-intune.md)

### Cihazları devre dışı bırakma ve verileri kaldırma
Bir cihazın [Intune yönetiminden kaldırılması](retire-devices-from-microsoft-intune-management) gerektiğinde (örneğin, bir kullanıcı ayrıldığında veya cihaz kaybedildiğinde veya çalındığında), bu cihazdaki verileri kaldırmak isteyeceksinizdir. Intune, şirketinizin verilerinin güvenli kalmasını sağlamak için bir dizi yöntem sunar.

### Cihazların uyumlu olmasını zorunlu kılma
Intune’da, belirttiğiniz kurallarla uyumlu olmayan cihazları değerlendirmenize (ve bazı durumlarda düzeltmenize) izin veren [cihaz uyumluluk ilkeleri](introduction-to-device-compliance-policies-in-microsoft-intune) bulunur. Örneğin, kısıtlamalardan kurtulmuş iOS cihazlarını, cihazların şifreli olup olmadığını veya Windows 10 cihazların durumunun Sistem Durumu Kanıtı Hizmeti tarafından uygun olarak bildirilip bildirilmediğini rapor edebilirsiniz.

### Uygulamaları ve kullandıkları verileri koruma
Intune, uygulamaları ve bunların verilerini korumanıza yardımcı olmak için size bir dizi özellik sunar. Örneğin, mobil uygulama yönetimi (MAM) ilkeleri verilerin korumalı bir uygulamadan yedeklenmesini engelleyebilir, kopyalama ve başka uygulamalara yapıştırmayı kısıtlayabilir, bir uygulamaya erişim için bir PIN isteyebilir vb. Uygulamaları koruma hakkında daha fazla ayrıntı için bkz. [Microsoft Intune ile uygulamalar ve verileri koruma](protect-apps-and-data-with-microsoft-intune)

## Windows cihazları için diğer özellikler

### Windows cihazlar için ek bir koruma katmanı ekleme
[Multi-factor authentication (MFA)](protect-windows-devices-with-multi-factor-authentication.md), ağdaki Windows ve Windows Phone cihazı kullanıcılarının kimliklerini doğrulamak için daha güvenli bir yoludur.  MFA ile, kullanıcıların, kimliklerini kullanıcı adı ve parolanın ötesinde, bir telefon konuşması veya kısa mesaj üzerinden doğrulaması gerekir.

### Windows cihazlarda İş İçin Windows Hello ayarlarını denetleme
Intune bir parolayı, akıllı kartı ya da sanal akıllı kartı değiştirmek üzere Windows 10 ve üzeri için Active Directory veya bir Azure Active Directory hesabı ile alternatif bir oturum açma yöntemi olan [İş İçin Windows Hello](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md)’yu (eskiden Microsoft Passport) tümleştirmenize olanak sağlar.

## iOS cihazlar için diğer özellikler

### iOS’de Etkinleştirme Kilidini Atlama
Etkinleştirme Kilidi, kullanıcılardan cihazlarını silmeden veya yeniden etkinleştirmeden önce Apple Kimliklerini ve parolalarını girmelerini isteyerek bu cihazları korumaya yardımcı olan bir özelliktir. Ancak, bu, örneğin kullanıcının kilidi kaldırmadan şirketten ayrılması durumunda sorunlara yol açabilir. [iOS Etkinleştirme Kilidi atlama](help-protect-ios-devices-with-activation-lock-bypass-for-microsoft-intune.md), denetimli iOS cihazlarından kilidi kaldırarak bu cihazları yeniden kullanıma almanıza veya silmenize yardımcı olabilir.



## Intune istemcisiyle yönetilen Windows bilgisayarları koruma
Intune, kaydolmadığınız ancak Intune bilgisayar istemci yazılımıyla yönettiğiniz Windows bilgisayarlar için güvenlik ilkelerini desteklemeye devam etmektedir. Bu ilkelerin, Windows bilgisayarlarınızı güvenli hale getirmenize nasıl yardımcı olabileceğini öğrenmek için, bkz. [Intune istemci yazılımını çalıştıran Windows bilgisayarları korumanıza yardımcı olması için ilkeler kullanma](policies-to-protect-windows-pcs-in-microsoft-intune.md).



<!--HONumber=Sep16_HO1-->


