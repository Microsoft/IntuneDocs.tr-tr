---
title: "Değerlendirme mobil cihazlarını kaydetme | Microsoft Intune"
description: "Intune’un ücretsiz, 30 günlük değerlendirmesine kaydolduğunuzda, mobil cihazlar nasıl kaydedilir ve uygulama nasıl yüklenir"
keywords: 
author: lindavr
manager: angrobe
ms.date: 08/09/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47806f69-303d-41d9-9b0e-9b9445ea24ac
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 51fba2b01d8978bc062c50c4388714609be0fdf0
ms.openlocfilehash: 66dc46eb9dc1010b8c176ccfdea68b9a6e4b0618


---

# Değerlendirme mobil cihazlarını kaydetme ve uygulama yükleme
Intune ile mobil cihaz yönetimi ayarlamak için, önce mobil cihaz yönetimi yetkilisini ayarlamanız, cihaz platformları için yönetimi etkinleştirmeniz ve cihazlarınızı Şirket Portalı uygulamasına kaydetmeniz gerekir. Ardından, yayımladığınız Microsoft Skype uygulamasını dağıtabilirsiniz.

## Hizmet cihaz yönetimi için hazırlama

1.  **Intune’ı, mobil cihaz yönetimi yetkiliniz yapın**

    [Intune yönetim konsolunda](https://manage.microsoft.com/), **Yönetici** &gt; **Mobil Cihaz Yönetimi**’ni seçin. **Görevler** > **MDM Yetkilisini Ayarla**’yı seçin ve ardından **MDM Yetkilisi** iletişim kutusunda **Evet**’i seçin.

2.  **Cihaz platformunuz için MDM’yi etkinleştirme**

    Yönetmek istediğiniz cihaz platformu için mobil cihaz yönetimini etkinleştirin. Platforma bağlı olarak farklı gereksinimler bulunur:

    -   **iOS ve Mac OS X**: bkz. [Microsoft Intune ile iOS ve Mac yönetimini ayarlama](/Intune/Deploy-Use/set-up-ios-and-mac-management-with-microsoft-intune).

    -   **Android**: Android mobil cihazlar kullanıcıların Google Play’den erişilebilen Şirket Portalı uygulamasını kullanarak kendi kendilerine kaydolmalarına olanak tanır. Intune’da ek yapılandırma gerekmez.

    -   **Windows Phone**: bkz. [Microsoft Intune ile Windows Phone yönetimini ayarlama](/Intune/Deploy-Use/set-up-windows-phone-management-with-microsoft-intune).

## Test cihazlarını kaydetme

### iOS ve Mac OS X
App Store’dan erişilebilen, Microsoft Corporation’a ait **Microsoft Intune Şirket Portalı** uygulamasını yükleyin ve yukarıya eklenen Intune kullanıcı kimlik bilgileriyle oturum açın. Cihazınızı eklemek için **Kayıtlı cihazlar** ’ı görüntüleyin.

### Android
[Google Play](http://go.microsoft.com/fwlink/p/?LinkId=386612)’den erişilebilen Microsoft Corporation’ın **Intune Şirket Portalı** uygulamasını yükleyin ve yukarıya eklenen Intune kullanıcı kimlik bilgileriyle oturum açın.

### Windows Phone 8.1
Kullanıcılar, Windows Phone mağazasından erişilebilen Microsoft Corporation’ın **Şirket Portalı** uygulamasını yükler ve yukarıya eklenen Intune kullanıcı kimlik bilgileriyle oturum açar.  Cihazınızı eklemek için **Kayıtlı cihazlar** ’ı görüntüleyin.

 ### Windows Phone 8.0
 Kullanıcılar **sistem ayarları** &gt; **şirket uygulamaları**’na tıklar ve Intune kullanıcı kimlik bilgileriyle oturum açar. Şirket Portalı uygulaması, telefonunuza dağıtılır.

**Sunucu adresi**istenirse “manage.microsoft.com” yazın.


## Daha önce dağıtılan uygulamayı yükleme
Mobil cihazda Şirket Portalı’nı açın, **Uygulamalar**'ı seçin ve ardından **Microsoft Skype**'ı yükleyin.

Intune kullanarak mobil cihaz yönetimi hakkında daha fazla bilgi için, bkz. [Microsoft Intune’da cihazları kaydetmeye hazırlanma](/Intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune).

### Sonraki adımlar
Tebrikler! *Microsoft Intune değerlendirme* gözden geçirmesinin 5. adımını tamamladınız.

>[!div class="step-by-step"]

>[&larr; **İlke Oluşturma**](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-4.md)     [**Seçenekler ve ek özellikler** &rarr;](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-6.md)  



<!--HONumber=Aug16_HO2-->


