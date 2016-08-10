---
title: "Mobil cihazların nasıl kaydedileceğini belirleme | Microsoft Intune"
description: "Mobil cihazları Intune’a nasıl kaydedeceğinizi birkaç basit soruyu yanıtlayarak kararlaştırın"
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: cac62b64-3f8b-47ae-aa66-970c7ba15466
ms.reviewer: dagerrit
translationtype: Human Translation
ms.sourcegitcommit: c671610b9c56d8b92d126d9902cce9c8c689ed63
ms.openlocfilehash: 9f1612ffd9ab85e38058edb09870297a44b37c16


---

# Mobil cihazların nasıl kaydedileceğini belirleme

Mobil cihaz kaydetme, akıllı telefonları, tablet ve PC’leri Microsoft Intune yönetimine alma işlemidir. Yönetici olarak, aşağıdakilere göre cihazların en iyi ne şekilde kaydedileceğine karar vermeniz gerekir:

 -  Sahiplik (kişisel veya şirkete ait)
 -  Kullanım (paylaşılan veya kişisel)
 -  Platform (iOS, Android, Windows Phone, Windows PC, Mac PC)

Aşağıdaki sorulara vereceğiniz yanıtlar, yönettiğiniz cihazları kaydetmek için en iyi yöntemi belirlemenize yardımcı olur.

## **Çalışanların kendi cihazlarını mı getiriyor, yoksa cihazları kuruluşunuz mu veriyor?**

  - **Kullanıcılara ait cihazları** - "KCG” (kendi cihazını getir) kayıt yöntemi – Kullanıcılar kendi cihazlarına Intune Şirket Portalı uygulamasını yükleyip cihazı kaydederek, e-posta, şirket uygulamaları, şirket verileri ve destek gibi şirket kaynaklarına erişim elde edebilirler.  

  - **Şirkete ait cihazlar** - Şirkete ait cihazlar (ŞAC) kuruluşun ihtiyaçlarına ve yönetilen cihaz türlerine bağlı olarak çeşitli şekillerde kaydedilebilir.

> [!div class="button"]
[KCG Kaydı >](#what-byod-devices-can-your-users-enroll)   [COD Kaydı >](#are-your-company-owned-devices-shared-or-do-they-have-dedicated-users)

## **Kullanıcılar hangi KCG cihazlarını kaydedebilir?**

> [!div class="button"]
[Android](/intune/deploy-use/set-up-android-management-with-microsoft-intune) [iOS ve Mac](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) [Windows 10 Mobile ve Window Phone](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune) [Windows Bilgisayarları](/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune)

## **Şirketinize ait cihazlar paylaşılıyor mu, yoksa hepsinin ayrı kullanıcısı mı var?**

- **Şirkete ait paylaşılan cihazlar** -Bu cihazların tek bir kullanıcısı yoktur ve genellikle e-postalara erişecek şekilde yapılandırılmamışlardır. Bilgi noktası cihazları veya kullanıcıların gerektiğinde bir havuzdan alıp kullandıkları görev odaklı cihazlar bunlara örnektir. Önerilen kayıt yöntemleri cihazların platformuna göre değişir.

- **Ayrılmış Kullanıcılar** - Bireysel kullanıcılara verilen şirkete ait cihazların bir yandan şirket varlığı olarak takip edilmeleri gerekirken, diğer yandan kişisel cihazlar olarak kullanıcılarına e-posta ve verilere erişim verilmelidir. Önerilen kayıt yöntemleri cihazların platformuna göre değişir.

> [!div class="button"]
[Paylaşılan >](#what-operating-system-are-your-shared-devices-running)   [Adanmış >](#how-will-you-manage-dedicated-ios-devices)


## **Paylaşılan cihazlarınızda hangi işletim sistemi çalıştırılıyor?**

  > [!div class="button"]
  [Windows >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [Android >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [iOS >](#how-will-you-manage-shared-ios-devices)

## **Paylaşılan iOS cihazlarınızı nasıl yöneteceksiniz?**

- **Apple Cihaz Kaydetme Programı (DEP)** -DEP ile satın alınan veya yönetilen iOS cihazları bir kayıt profiliyle hedef olarak kullanılabilir. Kullanıcılar cihazlarını ilk kez açtığında, cihaz DEP profilini indirir ve DEP profiliyle kaydolur

- **Mac’te Apple Configurator** - Apple Configurator, Mac PC’de çalışan bir Apple uygulamasıdır. Bir kayıt profilini cihaza yüklemek için, iOS cihazlarınızı USB kablosu ile Mac’e bağlayabilirsiniz. Kaydetmek için cihazlarınıza fabrika sıfırlaması yapabiliyorsanız, Kurulum Yardımcısı kayıt yöntemini kullanın. Cihazlara fabrika sıfırlaması yapmak istemiyorsanız, Doğrudan kayıt yöntemini kullanın.

- **Cihaz Kayıt Yöneticisi** - Intune cihaz kayıt yöneticisi (DEM), bir yöneticinin tek bir kullanıcı hesabı ile çok sayıda mobil cihazı kaydetmesine imkan tanır. Bu cihazlar kullanıcı benzeşimine (yani ayrılmış kullanıcılar) sahip olamaz ve Şirket Portalı uygulamasını yükleyip uygulamada oturum açarak kaydedilmelidir.

  > [!div class="button"]
  [iOS DEP Kaydı >](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [iOS Doğdudan kayıt >](/intune/deploy-use/ios-direct-enrollment-in-microsoft-intune)  [DEM kaydı >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).

## **Adanmış iOS cihazlarınızı nasıl yöneteceksiniz?**

Kuruma ait cihazları ayrılmış kullanıcılarla kaydetmek için aşağıdaki yöntemleri kullanabilirsiniz:

- **Apple Cihaz Kaydetme Programı (DEP)** -DEP ile satın alınan veya yönetilen iOS cihazları bir kayıt profiliyle hedef olarak kullanılabilir. Kullanıcılar cihazlarını ilk kez açtığında, cihaz DEP profilini indirir ve Intune’a kaydolur.

- **Mac’te Apple Configurator** - Apple Configurator, Mac PC’de çalışan bir Apple uygulamasıdır. Bir kayıt profilini cihaza yüklemek için, iOS cihazlarınızı USB kablosu ile Mac’e bağlayabilirsiniz. Kaydetmek için cihazlarınıza fabrika sıfırlaması yapabiliyorsanız, Kurulum Yardımcısı kayıt yöntemini kullanın.

- **IMEI numaralı etiket** - Şirkete ait cihazların uluslar arası mobil ekipman kimliği (IMEI) numaralarını içeri aktararak, cihazları Intune’da şirkete ait cihazlar olarak etiketleyebilirsiniz. Kullanıcılar e-posta, uygulamalar ve veriler gibi şirket kaynaklarına erişmek üzere Şirket Portalı’nı yükleyerek, cihazlarını kişisel cihaz olarak kaydedebilirler.

  > [!div class="button"]
  [IMEI ile Etiket >](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers) [iOS DEP](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [iOS Kurulum Yardımcısı](/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [IMEI ile Etiket](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)



<!--HONumber=Aug16_HO1-->


