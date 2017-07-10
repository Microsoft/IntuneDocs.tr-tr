---
title: "Mobil cihazların nasıl kaydedileceğini belirleme"
description: "Mobil cihazları Intune’a nasıl kaydedeceğinizi birkaç basit soruyu yanıtlayarak kararlaştırın"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 40262e47-1ab4-437d-8ca5-c89b5022f91f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.custom: intune-classic EXPIERIMENT
ms.openlocfilehash: 8fe7b2bb58655374d3e92391cd0a37aeda3062d4
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="choose-how-to-enroll-mobile-devices"></a>Mobil cihazların nasıl kaydedileceğini belirleme

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Bu soru dizisine vereceğiniz yanıtlar, yönettiğiniz cihazları kaydetmek için en iyi yöntemi belirlemenize yardımcı olacaktır.

## <a name="how-will-you-manage-dedicated-corporate-owned-devices"></a>**Şirkete ait adanmış cihazları nasıl yöneteceksiniz?**

  > [!div class="button"]
[iOS DEP >](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune)  
> [!div class="button"]
[iOS Kurulum Yardımcısı >](/intune-classic/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune)
> [!div class="button"]
[IMEI ile etiket >](/intune-classic/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  Ayrılmış kullanıcıları bulunan, şirkete ait cihazları kaydetmek için aşağıdaki yöntemleri kullanabilirsiniz:

  - **Apple Cihaz Kaydetme Programı (DEP)** -DEP ile satın alınan veya yönetilen iOS cihazları bir kayıt profiliyle hedef olarak kullanılabilir. Kullanıcılar cihazlarını ilk kez açtığında cihaz, DEP profilini indirir ve Intune’a kaydolur.

  - **Mac’te Apple Configurator** - Apple Configurator, Mac PC’de çalışan bir Apple uygulamasıdır. Bir kayıt profilini cihaza yüklemek için, iOS cihazlarınızı USB kablosu ile Mac’e bağlayabilirsiniz. Kaydetmek için cihazlarınıza fabrika sıfırlaması yapabiliyorsanız, Kurulum Yardımcısı kayıt yöntemini kullanın.

  - **IMEI numarasıyla etiketleme** - Şirkete ait cihazların uluslararası mobil ekipman kimliği (IMEI) numaralarını içeri aktararak, cihazları Intune’da şirkete ait cihazlar olarak etiketleyebilirsiniz. Bu, adanmış ("tek kullanıcı") Windows ve Android cihazları şirkete ait olarak belirlemenin tek yoludur. Apple’ın cihaz kayıt programına veya Apple Configurator’a kaydedilemeyen iOS cihazları da bir IMEI numarası ile etiketlenebilir. Cihazı, "şirket" etiketiyle tanımlanacak şekilde önceden bildirdikten sonra cihazları kullanıcılara dağıtabilirsiniz. Kullanıcılar, e-posta, uygulamalar ve veriler gibi şirket kaynaklarına erişmek üzere Şirket Portalı’nı yükleyerek, cihazlarını adanmış cihaz olarak kaydedebilir.

> [!div class="button"]
[< Geri](choose-how-to-enroll-devices3.md)
