---
title: Şirketin sahip olduğu cihazları yönetme
description: Şirkete ait cihazları cihaz türüne, nasıl satın alındığına ve kuruluşun gereksinimlerine bağlı olarak çeşitli yollarla kaydedin.
keywords: ''
author: nathbarn
ms.author: nathbarn
manager: dougeby
ms.date: 01/29/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 2b60bbff-25e6-489b-9621-c71b4275fa06
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4d224ceb819b6b0b4be0596c46d7bb20a98ddd97
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="enroll-corporate-owned-devices-by-using-intune"></a>Şirkete ait cihazları Intune kullanarak kaydetme

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Kuruluşa ait veya şirkete ait cihazları cihaz türüne, cihazın nasıl satın alındığına ve kuruluşun gereksinimlerine bağlı olarak çeşitli yollarla Intune ile yönetilmek üzere kaydedebilirsiniz. Bir “kendi cihazını getir” (KCG) senaryosunda olduğu gibi, şirkete ait cihazları kaydetmek ve yönetmek için Şirket Portalı uygulamasını da yükleyebilirsiniz.

Varsayılan olarak tüm platform cihazları Intune'a kaydedilebilir. Cihazların kaydedilmesini engellemek için yönetici kimlik bilgilerinizle [Microsoft Intune yönetim portalında](https://manage.microsoft.com) oturum açın. **Yönetim** > **Mobil Cihaz Yönetimi** > **Kayıt Kuralları**'nı seçip engellemek istediğiniz platformlara ait onay kutularının işaretini kaldırın.

## <a name="enroll-corporate-owned-ios-devices"></a>Şirketin sahip olduğu iOS cihazlarını kaydetme

Şirkete ait cihazları kaydetme yöntemleri "kendi cihazını seç" (CYOD) senaryoları için iyi bir seçimdir. Bir CYOD ortamında, kuruluş kullanıcının seçtiği bir cihaz için ödeme yapar ve cihazı yönetir.

Kullanıcılara iOS cihazlar arasından seçim yapma olanağı sunarsanız, kaydı önceden yapılandırarak kullanıcı ilk açtığı anda cihazın Intune ile yönetilmesini sağlayabilirsiniz. Intune, [Apple Cihaz Kayıt Programı (DEP)](ios-device-enrollment-program-in-microsoft-intune.md) aracılığıyla ya da [doğrudan](ios-direct-enrollment-in-microsoft-intune.md) veya [Kurulum Yardımcısı](ios-setup-assistant-enrollment-in-microsoft-intune.md) kaydı için Mac bilgisayarda Apple Configurator aracı kullanılarak kayıt yapılmasını destekler.

[Şirkete ait iOS cihazlarını kaydetmeyi](enroll-corporate-owned-ios-devices-in-microsoft-intune.md) öğrenin.

## <a name="create-a-device-enrollment-manager-account"></a>Cihaz kayıt yöneticisi hesabı oluşturma

Kuruluşunuzdaki çok sayıda mobil cihazı Intune ile yönetmek için tek kullanıcılı cihaz kayıt yöneticisi (DEM) hesabı oluşturabilirsiniz. Bir DEM hesabı oluşturduktan sonra, belirlenen bir hesap yöneticisi standart bir kullanıcıdan 15 cihaz daha fazla kaydedebilir.

DEM hesabını yalnızca tek, belirli bir kullanıcı tarafından kullanılanlar dışındaki cihazları kaydetmek için kullanabilirsiniz. Bu tür cihazlar örneğin satış noktası veya kamu hizmeti uygulamalarına uygundur ancak e-postaya veya şirket kaynaklarına erişmesi gereken kullanıcılar için uygun değildir.

[DEM hesabı kullanarak şirkete ait cihazları kaydetme](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) hakkında bilgi edinin.

## <a name="enroll-corporate-owned-windows-10-enterprise-devices"></a>Şirkete ait Windows 10 Enterprise cihazlarını kaydetme

Kuruluşunuzda Azure Active Directory Premium veya Microsoft Enterprise Mobility Suite kullanıyorsanız, [Windows 10 Enterprise cihazlarını kaydedebilirsiniz](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview). Bir kullanıcı bir cihaza iş veya okul hesabı eklerse, cihaz otomatik olarak "şirkete ait" olarak etiketlenir.

## <a name="import-imei-numbers"></a>IMEI numaralarını içeri aktarma

Çoğu mobil cihaz üreticisi, cihazlarında Uluslararası Mobil Donanım Kimliği (IMEI) adı verilen benzersiz bir numara kullanır. Kuruluşunuza ait cihazlar için IMEI numaralarını içeri aktarabilirsiniz. Cihaz Intune’la yönetilen bir cihaza dönüştüğünde, şirkete ait cihaz olarak etiketlenir.

[IMEI numaraları kullanarak şirkete ait cihazları etiketleme](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md) hakkında bilgi edinin.

## <a name="identify-a-device-as-corporate-owned"></a>Bir cihazı şirkete ait olarak tanımlama

Aşağıdaki koşullardan herhangi biri doğru olduğunda, Intune bir cihazı “şirket” cihazı olarak tanır:

 - Cihaz, [bir DEM hesabı kullanılarak kaydedilmiştir](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) (tüm platformlarda).
 - Cihaz [Apple DEP](ios-device-enrollment-program-in-microsoft-intune.md) veya [Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md) kullanılarak kaydedilmiştir (yalnızca iOS için).
 - Cihaz üreticisi, [cihazı IMEI numaraları kullanarak önceden bildirmiştir](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md) (IMEI numaraları olan tüm platformlar).
 - Cihaz [Azure Active Directory veya Enterprise Mobility Suite’e bir Windows 10 Enterprise cihazı olarak kaydedilmiştir](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview) (yalnızca Windows 10 için).

Bir cihaz şirket cihazı olarak etiketlendiğinde, yönetici konsolunda bulunan cihaz kaydındaki **Sahiplik** sütununda **Şirket** seçeneğini görürsünüz. 
