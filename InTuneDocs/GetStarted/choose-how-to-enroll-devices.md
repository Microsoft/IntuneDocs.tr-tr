---
title: "Mobil cihazların nasıl kaydedileceğini belirleme | Microsoft Intune"
description: "Mobil cihazları Intune’a nasıl kaydedeceğinizi birkaç basit soruyu yanıtlayarak kararlaştırın"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: cac62b64-3f8b-47ae-aa66-970c7ba15466
ms.reviewer: dagerrit
translationtype: Human Translation
ms.sourcegitcommit: 2c14071f5fb1a3604b897d6b2f81797d40bedc6d
ms.openlocfilehash: 1fd8495811e2cbcf4761707f2d1b705e49a240c6


---

# Mobil cihazların nasıl kaydedileceğini belirleme

Aşağıdaki sorulara vereceğiniz yanıtlar, yönettiğiniz cihazları kaydetmek için en iyi yöntemi belirlemenize yardımcı olur.

## **Çalışanların kendi cihazlarını mı getiriyor, yoksa cihazları kuruluşunuz mu veriyor?**

  - **Kullanıcıya ait cihazlar** - "Kendi cihazını getir" (KCG) kaydı
  - **Şirkete ait cihazlar** - COD kaydı

> [!div class="button"]
[KCG Kaydı >](#what-byod-devices-can-your-users-enroll)   
> [!div class="button"]
[COD Kaydı >](#are-your-company-owned-devices-shared-or-do-they-have-dedicated-users)

## **Kullanıcılar hangi KCG cihazlarını kaydedebilir?**

> [!div class="button"]
[Android](/intune/deploy-use/set-up-android-management-with-microsoft-intune) [iOS ve Mac](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) [Windows 10 Mobile ve Window Phone](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune) [Windows Bilgisayarları](/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune)

## **Şirketinize ait cihazlar paylaşılıyor mu, yoksa hepsinin ayrı kullanıcısı mı var?**

> [!div class="button"]
[Paylaşılan >](#what-operating-system-are-your-shared-devices-running)   [Adanmış >](#how-will-you-manage-dedicated-ios-devices)


## **Paylaşılan cihazlarınızda hangi işletim sistemi çalıştırılıyor?**

  > [!div class="button"]
  [Windows >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [Android >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [iOS >](#how-will-you-manage-shared-ios-devices)

## **Paylaşılan iOS cihazlarınızı nasıl yöneteceksiniz?**

  > [!div class="button"]
  [iOS DEP Kaydı >](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [iOS Doğrudan kayıt >](/intune/deploy-use/ios-direct-enrollment-in-microsoft-intune)  [DEM kaydı >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

  - **Apple Aygıt Kayıt Programı (DEP)** - DEP ile satın alınan veya yönetilen iOS cihazları bir kayıt profiliyle ilişkilendirilebilir. Kullanıcılar cihazlarını ilk kez açtığında cihaz, DEP profilini indirir ve DEP profiline kaydolur.

  - **Mac’te Apple Configurator** - Apple Configurator, Mac PC’de çalışan bir Apple uygulamasıdır. Bir kayıt profilini cihaza yüklemek için, iOS cihazlarınızı USB kablosu ile Mac’e bağlayabilirsiniz. Kaydetmek için cihazlarınıza fabrika sıfırlaması yapabiliyorsanız, Ayarlama Yardımcısı kayıt seçeneğini kullanın. Cihazlara fabrika sıfırlaması yapmak istemiyorsanız, Doğrudan kayıt seçeneğini kullanın.

  - **Cihaz kayıt yöneticisi (Intune)** - Intune cihaz kayıt yöneticisi (DEM), bir yöneticinin tek bir kullanıcı hesabı ile çok sayıda mobil cihaz kaydetmesine olanak tanır. Bu cihazlar ayrılmış kullanıcılara (kullanıcı benzeşimine) sahip olamaz ve Şirket Portalı uygulaması yüklenip uygulamada oturum açılarak kaydedilmelidir.

## **Adanmış iOS cihazlarınızı nasıl yöneteceksiniz?**

  > [!div class="button"]
   [iOS DEP](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [iOS Ayarlama Yardımcısı](/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [IMEI ile Etiket](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  Ayrılmış kullanıcıları bulunan, şirkete ait cihazları kaydetmek için aşağıdaki yöntemleri kullanabilirsiniz:

  - **Apple Aygıt Kayıt Programı (DEP)** - DEP ile satın alınan veya yönetilen iOS cihazları bir kayıt profiliyle ilişkilendirilebilir. Kullanıcılar cihazlarını ilk kez açtığında cihaz, DEP profilini indirir ve Intune’a kaydolur.

  - **Mac’te Apple Configurator** - Apple Configurator, Mac PC’de çalışan bir Apple uygulamasıdır. Bir kayıt profilini cihaza yüklemek için, iOS cihazlarınızı USB kablosu ile Mac’e bağlayabilirsiniz. Kaydetmek için cihazlarınıza fabrika sıfırlaması yapabiliyorsanız, Ayarlama Yardımcısı kayıt seçeneğini kullanın.

  - **IMEI numarasıyla etiketleme** - Şirkete ait cihazların uluslararası mobil ekipman kimliği (IMEI) numaralarını içeri aktararak, cihazları Intune’da şirkete ait cihazlar olarak etiketleyebilirsiniz. Kullanıcılar e-posta, uygulamalar ve veriler gibi şirket kaynaklarına erişmek üzere Şirket Portalı’nı yükleyerek, cihazlarını kişisel cihaz olarak kaydedebilirler.



<!--HONumber=Oct16_HO3-->


