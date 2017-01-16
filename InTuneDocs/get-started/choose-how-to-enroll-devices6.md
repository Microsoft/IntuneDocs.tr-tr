---
title: "Mobil cihazların nasıl kaydedileceğini belirleme | Microsoft Docs"
description: "Mobil cihazları Intune’a nasıl kaydedeceğinizi birkaç basit soruyu yanıtlayarak kararlaştırın"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/14/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 40262e47-1ab4-437d-8ca5-c89b5022f91f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
translationtype: Human Translation
ms.sourcegitcommit: f268cf29461447306d0f5c3ca06d541d9a03a49d
ms.openlocfilehash: bad5e7c342e481401db1d19388a8c87972fe69b8


---
# <a name="choose-how-to-enroll-mobile-devices"></a>Mobil cihazların nasıl kaydedileceğini belirleme

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Bu soru dizisine vereceğiniz yanıtlar, yönettiğiniz cihazları kaydetmek için en iyi yöntemi belirlemenize yardımcı olacaktır.

## <a name="how-will-you-manage-dedicated-corporate-owned-devices"></a>**Şirkete ait adanmış cihazları nasıl yöneteceksiniz?**

  > [!div class="button"]
[iOS DEP >](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune)  
> [!div class="button"]
[iOS Kurulum Yardımcısı >](/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune)
> [!div class="button"]
[IMEI ile etiket >](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  Ayrılmış kullanıcıları bulunan, şirkete ait cihazları kaydetmek için aşağıdaki yöntemleri kullanabilirsiniz:

  - **Apple Cihaz Kaydetme Programı (DEP)** -DEP ile satın alınan veya yönetilen iOS cihazları bir kayıt profiliyle hedef olarak kullanılabilir. Kullanıcılar cihazlarını ilk kez açtığında cihaz, DEP profilini indirir ve Intune’a kaydolur.

  - **Mac’te Apple Configurator** - Apple Configurator, Mac PC’de çalışan bir Apple uygulamasıdır. Bir kayıt profilini cihaza yüklemek için, iOS cihazlarınızı USB kablosu ile Mac’e bağlayabilirsiniz. Kaydetmek için cihazlarınıza fabrika sıfırlaması yapabiliyorsanız, Kurulum Yardımcısı kayıt yöntemini kullanın.

  - **IMEI numarasıyla etiketleme** - Şirkete ait cihazların uluslararası mobil ekipman kimliği (IMEI) numaralarını içeri aktararak, cihazları Intune’da şirkete ait cihazlar olarak etiketleyebilirsiniz. Bu, adanmış ("tek kullanıcı") Windows ve Android cihazları şirkete ait olarak belirlemenin tek yoludur. Apple’ın cihaz kayıt programına veya Apple Configurator’a kaydedilemeyen iOS cihazları da bir IMEI numarası ile etiketlenebilir. Cihazı, "şirket" etiketiyle tanımlanacak şekilde önceden bildirdikten sonra cihazları kullanıcılara dağıtabilirsiniz. Kullanıcılar, e-posta, uygulamalar ve veriler gibi şirket kaynaklarına erişmek üzere Şirket Portalı’nı yükleyerek, cihazlarını adanmış cihaz olarak kaydedebilir.

  > [!div class="button"]
  [< Geri](choose-how-to-enroll-devices3.md)



<!--HONumber=Dec16_HO3-->


