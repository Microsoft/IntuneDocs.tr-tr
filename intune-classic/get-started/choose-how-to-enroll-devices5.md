---
title: Mobil cihazların nasıl kaydedileceğini belirleme
description: Mobil cihazları Intune’a nasıl kaydedeceğinizi birkaç basit soruyu yanıtlayarak kararlaştırın
keywords: ''
author: NathBarn
ms.author: nathbarn
manager: dougeby
ms.date: 03/27/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ed9250aa-e894-4eac-92b8-5f1a3748e255
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.custom: intune-classic EXPIERIMENT
ms.openlocfilehash: c7e750d308c4167dd6e99f503ed52d3a96ea630b
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="choose-how-to-enroll-mobile-devices"></a>Mobil cihazların nasıl kaydedileceğini belirleme

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Bu soru dizisine vereceğiniz yanıtlar, yönettiğiniz cihazları kaydetmek için en iyi yöntemi belirlemenize yardımcı olacaktır.

## <a name="how-will-you-manage-shared-ios-devices"></a>**Paylaşılan iOS cihazlarınızı nasıl yöneteceksiniz?**

> [!div class="button"]
> [iOS DEP Kaydı >](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune)
> [!div class="button"]
> [iOS Doğrudan kaydı >](/intune-classic/deploy-use/ios-direct-enrollment-in-microsoft-intune)
> [!div class="button"]
> [DEM kaydı >](/intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

  - **Apple Cihaz Kaydetme Programı (DEP)** -DEP ile satın alınan veya yönetilen iOS cihazları bir kayıt profiliyle hedef olarak kullanılabilir. Kullanıcılar cihazlarını ilk kez açtığında cihaz, DEP profilini indirir ve DEP profiline kaydolur.

  - **Mac’te Apple Configurator** - Apple Configurator, Mac PC’de çalışan bir Apple uygulamasıdır. Bir kayıt profilini cihaza yüklemek için, iOS cihazlarınızı USB kablosu ile Mac’e bağlayabilirsiniz. Kaydetmek için cihazlarınıza fabrika sıfırlaması yapabiliyorsanız, Kurulum Yardımcısı kayıt yöntemini kullanın. Cihazlara fabrika sıfırlaması yapmak istemiyorsanız, Doğrudan kayıt yöntemini kullanın.

  - **Cihaz Kayıt Yöneticisi** - Intune cihaz kayıt yöneticisi (DEM), bir yöneticinin tek bir kullanıcı hesabı ile çok sayıda mobil cihaz kaydetmesine olanak tanır. Bu cihazlar kullanıcı benzeşimine (yani ayrılmış kullanıcılara) sahip olamaz ve Şirket Portalı uygulaması yüklenip uygulamada oturum açılarak kaydedilmelidir.

> [!div class="button"]
> [< Geri](choose-how-to-enroll-devices3.md)
