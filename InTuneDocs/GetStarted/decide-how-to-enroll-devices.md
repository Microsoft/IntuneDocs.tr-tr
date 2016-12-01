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
ms.assetid: 178df739-d3b9-43cb-8440-c5c110b1276b
ms.reviewer: dagerrit
translationtype: Human Translation
ms.sourcegitcommit: 149f3a3310907d131affeaad4bd372aa60be9206
ms.openlocfilehash: b5cc645ea50e6c4bb521e04371037c3978c9426a


---

# <a name="choose-how-to-enroll-mobile-devices"></a>Mobil cihazların nasıl kaydedileceğini belirleme

Mobil cihaz kaydetme, akıllı telefonları, tablet ve PC’leri Microsoft Intune yönetimine alma işlemidir. Yönetici olarak, aşağıdakilere göre cihazların en iyi ne şekilde kaydedileceğine karar vermeniz gerekir:

 -  Sahiplik (kişisel veya şirkete ait)
 -  Kullanım (paylaşılan veya kişisel)
 -  Platform (iOS, Android, Windows Phone, Windows PC, Mac PC)

Aşağıdaki sorulara vereceğiniz yanıtlar, yönettiğiniz cihazları kaydetmek için en iyi yöntemi belirlemenize yardımcı olur.

## <a name="do-employees-bring-their-own-devices-or-are-devices-provided-by-your-organization"></a>**Çalışanların kendi cihazlarını mı getiriyor, yoksa cihazları kuruluşunuz mu veriyor?**

  - **Kullanıcılara ait cihazları** - "KCG” (kendi cihazını getir) kayıt yöntemi – Kullanıcılar kendi cihazlarına Intune Şirket Portalı uygulamasını yükleyip cihazı kaydederek, e-posta, şirket uygulamaları, şirket verileri ve destek gibi şirket kaynaklarına erişim elde edebilirler.  

  - **Şirkete ait cihazlar** - Şirkete ait cihazlar (ŞAC) kuruluşun ihtiyaçlarına ve yönetilen cihaz türlerine bağlı olarak çeşitli şekillerde kaydedilebilir.

> [!div class="button"]
[KCG Kaydı >](#what-byod-devices-can-your-users-enroll)   [COD Kaydı >](#are-your-company-owned-devices-shared-or-do-they-have-dedicated-users)

## <a name="what-byod-devices-can-your-users-enroll"></a>**Kullanıcılar hangi KCG cihazlarını kaydedebilir?**

> [!div class="button"]
[Android](/intune/deploy-use/set-up-android-management-with-microsoft-intune) [iOS ve Mac](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) [Windows 10 Mobile ve Window Phone](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune) [Windows Bilgisayarları](/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune)

## <a name="are-your-company-owned-devices-shared-or-do-they-have-dedicated-users"></a>**Şirketinize ait cihazlar paylaşılıyor mu, yoksa hepsinin ayrı kullanıcısı mı var?**

- **Şirkete ait paylaşılan cihazlar** -Bu cihazların tek bir kullanıcısı yoktur ve genellikle e-postalara erişecek şekilde yapılandırılmamışlardır. Bilgi noktası cihazları veya kullanıcıların gerektiğinde bir havuzdan alıp kullandıkları görev odaklı cihazlar bunlara örnektir. Önerilen kayıt yöntemleri cihazların platformuna göre değişir.

- **Ayrılmış Kullanıcılar** - Bireysel kullanıcılara verilen şirkete ait cihazların bir yandan şirket varlığı olarak takip edilmeleri gerekirken, diğer yandan kişisel cihazlar olarak kullanıcılarına e-posta ve verilere erişim verilmelidir. Önerilen kayıt yöntemleri cihazların platformuna göre değişir.

> [!div class="button"]
[Paylaşılan >](#what-operating-system-are-your-shared-devices-running)   [Adanmış >](#how-will-you-manage-dedicated-ios-devices)


## <a name="what-operating-system-are-your-shared-devices-running"></a>**Paylaşılan cihazlarınızda hangi işletim sistemi çalıştırılıyor?**

> [!div class="button"]
[Windows >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [Android >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [iOS >](#how-will-you-manage-shared-ios-devices)

## <a name="how-will-you-manage-shared-ios-devices"></a>**Paylaşılan iOS cihazlarınızı nasıl yöneteceksiniz?**

- **Apple Cihaz Kaydetme Programı (DEP)** -DEP ile satın alınan veya yönetilen iOS cihazları bir kayıt profiliyle hedef olarak kullanılabilir. Kullanıcılar cihazlarını ilk kez açtığında, cihaz DEP profilini indirir ve DEP profiliyle kaydolur

- **Mac’te Apple Configurator** - Apple Configurator, Mac PC’de çalışan bir Apple uygulamasıdır. Bir kayıt profilini cihaza yüklemek için, iOS cihazlarınızı USB kablosu ile Mac’e bağlayabilirsiniz. Kaydetmek için cihazlarınıza fabrika sıfırlaması yapabiliyorsanız, Kurulum Yardımcısı kayıt yöntemini kullanın. Cihazlara fabrika sıfırlaması yapmak istemiyorsanız, Doğrudan kayıt yöntemini kullanın.

- **Cihaz Kayıt Yöneticisi** - Intune cihaz kayıt yöneticisi (DEM), bir yöneticinin tek bir kullanıcı hesabı ile çok sayıda mobil cihaz kaydetmesine olanak tanır. Bu cihazlar kullanıcı benzeşimine (yani ayrılmış kullanıcılar) sahip olamaz ve Şirket Portalı uygulamasını yükleyip uygulamada oturum açarak kaydedilmelidir.

  > [!div class="button"]
  [iOS DEP Kaydı >](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [iOS Doğdudan kayıt >](/intune/deploy-use/ios-direct-enrollment-in-microsoft-intune)  [DEM kaydı >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).

## <a name="how-will-you-manage-dedicated-ios-devices"></a>**Adanmış iOS cihazlarınızı nasıl yöneteceksiniz?**

Ayrılmış kullanıcıları bulunan, şirkete ait cihazları kaydetmek için aşağıdaki yöntemleri kullanabilirsiniz:

- **Apple Cihaz Kaydetme Programı (DEP)** -DEP ile satın alınan veya yönetilen iOS cihazları bir kayıt profiliyle hedef olarak kullanılabilir. Kullanıcılar cihazlarını ilk kez açtığında cihaz, DEP profilini indirir ve Intune’a kaydolur.

- **Mac’te Apple Configurator** - Apple Configurator, Mac PC’de çalışan bir Apple uygulamasıdır. Bir kayıt profilini cihaza yüklemek için, iOS cihazlarınızı USB kablosu ile Mac’e bağlayabilirsiniz. Kaydetmek için cihazlarınıza fabrika sıfırlaması yapabiliyorsanız, Kurulum Yardımcısı kayıt yöntemini kullanın.

- **IMEI numarasıyla etiketleme** - Şirkete ait cihazların uluslararası mobil ekipman kimliği (IMEI) numaralarını içeri aktararak, cihazları Intune’da şirkete ait cihazlar olarak etiketleyebilirsiniz. Kullanıcılar e-posta, uygulamalar ve veriler gibi şirket kaynaklarına erişmek üzere Şirket Portalı’nı yükleyerek, cihazlarını kişisel cihaz olarak kaydedebilirler.

  > [!div class="button"]
  [IMEI ile Etiket >](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers) [iOS DEP](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [iOS Kurulum Yardımcısı](/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [IMEI ile Etiket](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)



<!--HONumber=Nov16_HO4-->


