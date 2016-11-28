---
title: "Mobil cihazların nasıl kaydedileceğini belirleme | Microsoft Intune"
description: "Mobil cihazları Intune’a nasıl kaydedeceğinizi birkaç basit soruyu yanıtlayarak kararlaştırın"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cac62b64-3f8b-47ae-aa66-970c7ba15466
ms.reviewer: dagerrit
translationtype: Human Translation
ms.sourcegitcommit: a563105aafb447c6e009cca09645e630709ff72d
ms.openlocfilehash: 143f77bde09648a233ff09e9740668191a50cb1e


---

# <a name="choose-how-to-enroll-mobile-devices"></a>Mobil cihazların nasıl kaydedileceğini belirleme

Aşağıdaki sorulara vereceğiniz yanıtlar, yönettiğiniz cihazları kaydetmek için en iyi yöntemi belirlemenize yardımcı olur.

## <a name="do-employees-bring-their-own-devices-or-are-devices-provided-by-your-organization"></a>**Çalışanların kendi cihazlarını mı getiriyor, yoksa cihazları kuruluşunuz mu veriyor?**

  - **Kullanıcıya ait cihazlar** - "Kendi cihazını getir" (KCG) kaydı
  - **Şirkete ait cihazlar** - COD kaydı

> [!div class="button"]
[KCG Kaydı >](#what-byod-devices-can-your-users-enroll)   
> [!div class="button"]
[COD Kaydı >](#are-your-company-owned-devices-shared-or-do-they-have-dedicated-users)

## <a name="what-byod-devices-can-your-users-enroll"></a>**Kullanıcılar hangi KCG cihazlarını kaydedebilir?**

> [!div class="button"]
[Android](/intune/deploy-use/set-up-android-management-with-microsoft-intune) [iOS ve Mac](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) [Windows 10 Mobile ve Window Phone](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune) [Windows Bilgisayarları](/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune)

## <a name="are-your-company-owned-devices-shared-or-do-they-have-dedicated-users"></a>**Şirketinize ait cihazlar paylaşılıyor mu, yoksa hepsinin ayrı kullanıcısı mı var?**

> [!div class="button"]
[Paylaşılan >](#what-operating-system-are-your-shared-devices-running)   [Adanmış >](#how-will-you-manage-dedicated-ios-devices)


## <a name="what-operating-system-are-your-shared-devices-running"></a>**Paylaşılan cihazlarınızda hangi işletim sistemi çalıştırılıyor?**

> [!div class="button"]
[Windows >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [Android >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [iOS >](#how-will-you-manage-shared-ios-devices)

## <a name="how-will-you-manage-shared-ios-devices"></a>**Paylaşılan iOS cihazlarınızı nasıl yöneteceksiniz?**

> [!div class="button"]
[iOS DEP Kaydı >](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [iOS Doğrudan kayıt >](/intune/deploy-use/ios-direct-enrollment-in-microsoft-intune)  [DEM kaydı >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

  - **Apple Aygıt Kayıt Programı (DEP)** - DEP ile satın alınan veya yönetilen iOS cihazları bir kayıt profiliyle ilişkilendirilebilir. Kullanıcılar cihazlarını ilk kez açtığında cihaz, DEP profilini indirir ve DEP profiline kaydolur.

  - **Mac’te Apple Configurator** - Apple Configurator, Mac PC’de çalışan bir Apple uygulamasıdır. Bir kayıt profilini cihaza yüklemek için, iOS cihazlarınızı USB kablosu ile Mac’e bağlayabilirsiniz. Kaydetmek için cihazlarınıza fabrika sıfırlaması yapabiliyorsanız, Ayarlama Yardımcısı kayıt seçeneğini kullanın. Cihazlara fabrika sıfırlaması yapmak istemiyorsanız, Doğrudan kayıt seçeneğini kullanın.

  - **Cihaz kayıt yöneticisi (Intune)** - Intune cihaz kayıt yöneticisi (DEM), bir yöneticinin tek bir kullanıcı hesabı ile çok sayıda mobil cihaz kaydetmesine olanak tanır. Bu cihazlar ayrılmış kullanıcılara (kullanıcı benzeşimine) sahip olamaz ve Şirket Portalı uygulaması yüklenip uygulamada oturum açılarak kaydedilmelidir.

## <a name="how-will-you-manage-dedicated-ios-devices"></a>**Adanmış iOS cihazlarınızı nasıl yöneteceksiniz?**

> [!div class="button"]
[iOS DEP](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [iOS Ayarlama Yardımcısı](/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [IMEI ile Etiket](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  Ayrılmış kullanıcıları bulunan, şirkete ait cihazları kaydetmek için aşağıdaki yöntemleri kullanabilirsiniz:

  - **Apple Aygıt Kayıt Programı (DEP)** - DEP ile satın alınan veya yönetilen iOS cihazları bir kayıt profiliyle ilişkilendirilebilir. Kullanıcılar cihazlarını ilk kez açtığında cihaz, DEP profilini indirir ve Intune’a kaydolur.

  - **Mac’te Apple Configurator** - Apple Configurator, Mac PC’de çalışan bir Apple uygulamasıdır. Bir kayıt profilini cihaza yüklemek için, iOS cihazlarınızı USB kablosu ile Mac’e bağlayabilirsiniz. Kaydetmek için cihazlarınıza fabrika sıfırlaması yapabiliyorsanız, Ayarlama Yardımcısı kayıt seçeneğini kullanın.

  - **IMEI numarasıyla etiketleme** - Şirkete ait cihazların uluslararası mobil ekipman kimliği (IMEI) numaralarını içeri aktararak, cihazları Intune’da şirkete ait cihazlar olarak etiketleyebilirsiniz. Kullanıcılar e-posta, uygulamalar ve veriler gibi şirket kaynaklarına erişmek üzere Şirket Portalı’nı yükleyerek, cihazlarını kişisel cihaz olarak kaydedebilirler.



<!--HONumber=Nov16_HO4-->


