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
ms.assetid: 40262e47-1ab4-437d-8ca5-c89b5022f91f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
translationtype: Human Translation
ms.sourcegitcommit: a5f80058e004f119acc9a918123c897b72b71314
ms.openlocfilehash: ecc6834b18d7906633bf1a029f5d63a4432c4989


---
# Mobil cihazların nasıl kaydedileceğini belirleme

Bu soru dizisine vereceğiniz yanıtlar, yönettiğiniz cihazları kaydetmek için en iyi yöntemi belirlemenize yardımcı olacaktır.

## **Şirkete ait adanmış cihazları nasıl yöneteceksiniz?**

  > [!div class="button"]
[iOS DEP >](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune)<br>[iOS Kurulum Yardımcısı >](/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune)<br>[IMEI ile etiket >](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  Ayrılmış kullanıcıları bulunan, şirkete ait cihazları kaydetmek için aşağıdaki yöntemleri kullanabilirsiniz:

  - **Apple Cihaz Kaydetme Programı (DEP)** -DEP ile satın alınan veya yönetilen iOS cihazları bir kayıt profiliyle hedef olarak kullanılabilir. Kullanıcılar cihazlarını ilk kez açtığında cihaz, DEP profilini indirir ve Intune’a kaydolur.

  - **Mac’te Apple Configurator** - Apple Configurator, Mac PC’de çalışan bir Apple uygulamasıdır. Bir kayıt profilini cihaza yüklemek için, iOS cihazlarınızı USB kablosu ile Mac’e bağlayabilirsiniz. Kaydetmek için cihazlarınıza fabrika sıfırlaması yapabiliyorsanız, Kurulum Yardımcısı kayıt yöntemini kullanın.

  - **IMEI numarasıyla etiketleme** - Şirkete ait cihazların uluslararası mobil ekipman kimliği (IMEI) numaralarını içeri aktararak, cihazları Intune’da şirkete ait cihazlar olarak etiketleyebilirsiniz. Bu, adanmış ("tek kullanıcı") Windows ve Android cihazları şirkete ait olarak belirlemenin tek yoludur. Apple’ın cihaz kayıt programına veya Apple Configurator’a kaydedilemeyen iOS cihazları da bir IMEI numarası ile etiketlenebilir. Cihazı, "şirket" etiketiyle tanımlanacak şekilde önceden bildirdikten sonra cihazları kullanıcılara dağıtabilirsiniz. Kullanıcılar, e-posta, uygulamalar ve veriler gibi şirket kaynaklarına erişmek üzere Şirket Portalı’nı yükleyerek, cihazlarını adanmış cihaz olarak kaydedebilir.

  > [!div class="button"]
  [< Geri](choose-how-to-enroll-devices3.md)



<!--HONumber=Aug16_HO5-->


