---
title: "Mobil cihazların nasıl kaydedileceğini belirleme | Microsoft Intune"
description: 
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 06/06/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: cac62b64-3f8b-47ae-aa66-970c7ba15466
translationtype: Human Translation
ms.sourcegitcommit: f1dc713099c982d6e32c87b814dd3f55b1656eda
ms.openlocfilehash: 5668a4d8a6cce15446201926b03d71ede174a299


---

# Mobil cihazların nasıl kaydedileceğini belirleme

Mobil cihaz kaydetme, akıllı telefonları, tablet ve PC’leri Microsoft Intune yönetimine alma işlemidir. Yönetici olarak, aşağıdakilere göre cihazların en iyi ne şekilde kaydedileceğine karar vermeniz gerekir:

 -  Sahiplik (kişisel veya şirkete ait)
 -  Kullanım (paylaşılan veya kişisel)
 -  Platform (iOS, Android, Windows Phone, Windows PC, Mac PC) - Kayıt yöntemiyle seçilir

Aşağıdaki sorulara vereceğiniz yanıtlar, yönettiğiniz cihazları kaydetmek için en iyi yöntemi belirlemenize yardımcı olur.

## **Çalışanların kendi cihazlarını mı getiriyor, yoksa cihazları kuruluşunuz mu veriyor?**

  “Kendi cihazını getir” (BYOD) kaydı olarak da bilinen **kullanıcılara ait cihazlar**, kullanıcıların e-posta, şirket uygulamaları, şirket verileri ve destek gibi şirket kaynaklarına erişim elde etmek için kendi cihazlarını kaydetmesine izin verir. **Şirkete ait cihazlar** (COD), bir iş gereksiniminin karşılanması amacıyla kurum tarafından çalışanlara sağlanan cihazlardır.
  > [!div class="button"]
  [BYOD Kaydı >](#byod-device-enrollment)   [COD Kaydı >](#cod-device-enrollment)

### BYOD cihaz kaydı

BYOD kaydı, kullanıcıların cihazlarına Intune Şirket Portalı uygulaması yüklemesini gerektirir. Daha sonra uygulamayı açıp iş veya okul kimlik bilgilerini sağlayarak kaydolabilirler. Intune tarafından cihaz için bir lisans bulunursa, cihaz Intune yönetici konsoluna eklenir ve Intune’dan cihazın şirket kaynaklarına erişmesini sağlayan ilkeyi alabilir.

**Cihaz türünü seçin:**
> [!div class="button"]
[Android](..deploy-use/set-up-android-management-with-microsoft-intune) [iOS ve Mac](..deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) [Windows 10 Mobile ve Windows Phone](..deploy-use/set-up-windows-phone-management-with-microsoft-intune) [Windows bilgisayarları](..deploy-use/set-up-windows-device-management-with-microsoft-intune)


### COD cihaz kaydı

Şirkete ait cihazlar (COD), bağımsız bir kullanıcıyı desteklemek ya da çok sayıda kullanıcı arasında paylaşılmak üzere kaydedilebilir.  **Paylaşılan cihazların** tek bir kullanıcısı yoktur ve genellikle e-postalara erişecek şekilde yapılandırılmamışlardır. Bilgi noktası cihazları veya kullanıcıların gerektiğinde bir havuzdan ödünç alarak kullandıkları görev odaklı cihazlar bunlara örnektir. Önerilen kayıt yöntemleri cihazların platformuna göre değişir. **Adanmış cihazlar**: bireysel kullanıcılara verilen bu cihazların bir yandan şirket varlığı olarak takip edilmeleri gerekirken, diğer yandan kişiselleştirilmiş cihazlar olarak kullanıcılarının e-posta ve verilere erişmesini sağlamalıdır. Önerilen kayıt yöntemleri cihazların platformuna göre değişir. [Sonraki soru...](Are your company-owned devices shared or do they have dedicated users?)

## **Şirketinize ait cihazlar paylaşılıyor mu, yoksa hepsinin ayrı kullanıcısı mı var?**

> [!div class="button"]
[Paylaşılan >](#Shared-company-owned-devices)   [Adanmış >](..deploy-use/get-ready-to-enroll-devices-in-microsoft-intune)


### Şirkete ait paylaşılan cihazlar

Bu cihazların tek bir kullanıcısı yoktur ve genellikle e-postalara erişecek şekilde yapılandırılmamışlardır. Bilgi noktası cihazları veya kullanıcıların gerektiğinde bir havuzdan ödünç alarak kullandıkları görev odaklı cihazlar bunlara örnektir. Önerilen kayıt yöntemleri cihazların platformuna göre değişir.

  - **Windows ve Android cihazları** - *Cihaz kayıt yöneticisi* çok sayıda paylaşılan cihazı Şirket Portalı uygulamasını kullanarak kaydetmek için kullanılabilen bir Intune hesabıdır.
  > [!div class="button"]
  [Windows >](../deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [Android >](../deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [iOS >](#shared-ios-device-enrollment)

### Paylaşılan iOS cihaz kaydı

Şirkete ait paylaşılan iOS cihazların kaydı için tercih edilen yöntem, bu cihazları nasıl satın aldığınıza ve yönettiğinize bağlıdır:

  - **Apple Cihaz Kaydetme Programı (DEP)** -DEP ile satın alınan veya yönetilen iOS cihazları bir kayıt profiliyle hedef olarak kullanılabilir. Kullanıcılar cihazlarını ilk kez açtığında, cihaz DEP profilini indirir ve DEP profiliyle kaydolur
  - **Mac’te Apple Configurator (Mac)** - Apple Configurator, Mac PC’de çalışan bir Apple uygulamasıdır. Bir kayıt profilini cihaza yüklemek için, iOS cihazlarınızı USB kablosu ile Mac’e bağlayabilirsiniz. Kaydetmek için cihazlarınıza fabrika sıfırlaması yapabiliyorsanız, Kurulum Yardımcısı kayıt yöntemini kullanın. Cihazlara fabrika sıfırlaması yapmak istemiyorsanız, Doğrudan kayıt yöntemini kullanın.
  - **Yukarıdakilerin hiçbiri** - Apple DEP veya Apple Configurator kayıt yöntemlerini kullanamıyorsanız veya kullanmak istemiyorsanız, Intune'un cihaz kayıt yöneticisini kullanın.

  **Şunu seçin:**
    > [!div class="button"]
     [DEP Kaydı >](../deploy-use/ios-device-enrollment-program-in-microsoft-intune) [Mac >](../deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [Doğrudan kayıt >](../deploy-use/ios-direct-enrollment-in-microsoft-intune)  

  > [!div class="button"]
    [DEM kaydı >](../deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).

**Bireysel Kullanıcılar** - Bireysel kullanıcılara verilen şirkete ait cihazların bir yandan şirket varlığı olarak takip edilmeleri gerekirken, diğer yandan kişisel cihazlar olarak kullanıcılarına e-posta ve verilere erişim verilmelidir. Önerilen kayıt yöntemleri cihazların platformuna göre değişir.

  - **Windows ve Android cihazları** - Şirkete ait cihazların uluslar arası mobil ekipman kimliği (IMEI) numaralarını içeri aktararak, cihazları Intune’da şirkete ait cihazlar olarak etiketleyebilirsiniz. Kullanıcılar e-posta, uygulamalar ve veriler gibi şirket kaynaklarına erişmek üzere Şirket Portalı’nı yükleyerek, cihazlarını kişisel cihaz olarak kaydedebilirler.
  > [!div class="button"]
  [IMEI ile etiket >](../deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  - **iOS cihazları** - Paylaşılan iOS cihazları üç şekilde yönetilebilir.  **Paylaşılan iOS cihazlarınızı nasıl kaydedeceksiniz?**

    - **Apple Cihaz Kaydetme Programı (DEP)** -DEP ile satın alınan veya yönetilen iOS cihazları bir kayıt profiliyle hedef olarak kullanılabilir. Kullanıcılar cihazlarını ilk kez açtığında, cihaz DEP profilini indirir ve profile göre kaydedilir.
    > [!div class="button"]
    [DEP Kaydı](../deploy-use/ios-device-enrollment-program-in-microsoft-intune).

    - **Mac’te Apple Configurator** - Apple Configurator, Mac PC’de çalışan bir Apple uygulamasıdır. Bir kayıt profilini cihaza yüklemek için, iOS cihazlarınızı USB kablosu ile Mac’e bağlayabilirsiniz. Kaydetmek için cihazlarınıza fabrika sıfırlaması yapabiliyorsanız, Kurulum Yardımcısı kayıt yöntemini kullanın.

    Cihazlara fabrika sıfırlaması yapmak istemiyorsanız, Doğrudan kayıt yöntemini kullanın.
    Kaydetmek için cihazlarınıza fabrika sıfırlaması yapabiliyorsanız, Kurulum Yardımcısı kayıt yöntemini kullanın.
    > [!div class="button"][iOS Setup Assistant enrollment](../deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [!div class="button"][iOS direct enrollment](../deploy-use/ios-direct-enrollment-in-microsoft-intune).

    - **Yukarıdakilerin hiçbiri** - Apple'ın DEP veya Apple Configurator kayıt yöntemlerini kullanamıyor veya kullanmak istemiyorsanız, şirkete ait cihazların uluslar arası mobil ekipman kimliği (IMEI) numaralarını içeri aktararak, Intune’da bu cihazları şirkete ait cihazlar olarak etiketleyebilirsiniz. Kullanıcılar e-posta, uygulamalar ve veriler gibi şirket kaynaklarına erişmek üzere Şirket Portalı’nı yükleyerek, cihazlarını kişisel cihaz olarak kaydedebilirler.
    > [!div class="button"][Tag devices with IMEI numbers](../deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)



<!--HONumber=Jun16_HO5-->


