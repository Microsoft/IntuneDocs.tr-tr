---
title: "Kuruluşa ait cihazları yönetme | Microsoft Intune"
description: "Şirkete ait cihazları cihaz türüne, nasıl satın alındığına ve kuruluşun gereksinimlerine bağlı olarak çeşitli yollarla kaydedin."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2b60bbff-25e6-489b-9621-c71b4275fa06
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 88409332d203dc4ee82fdf98f89a94e5a89a7eed
ms.openlocfilehash: c29cd2c0c4c5671a84f7c0b0ba473e6fb32604d9


---

# <a name="enroll-corporateowned-devices-by-using-intune"></a>Şirkete ait cihazları Intune kullanarak kaydetme

Kuruluşa ait veya şirkete ait cihazları cihaz türüne, cihazın nasıl satın alındığına ve kuruluşun gereksinimlerine bağlı olarak çeşitli yollarla Intune ile yönetilmek üzere kaydedebilirsiniz. Bir “kendi cihazını getir” (KCG) senaryosunda olduğu gibi, şirkete ait cihazları kaydetmek ve yönetmek için Şirket Portalı uygulamasını da yükleyebilirsiniz.

## <a name="enroll-corporateowned-ios-devices"></a>Şirketin sahip olduğu iOS cihazlarını kaydetme

Şirkete ait cihazları kaydetme yöntemleri "kendi cihazını seç" (CYOD) senaryoları için iyi bir seçimdir. Bir CYOD ortamında, kuruluş kullanıcının seçtiği bir cihaz için ödeme yapar ve cihazı yönetir.

Kullanıcılara iOS cihazlar arasından seçim yapma olanağı sunarsanız, kaydı önceden yapılandırarak kullanıcı ilk açtığı anda cihazın Intune ile yönetilmesini sağlayabilirsiniz. Intune, [Apple Cihaz Kayıt Programı (DEP)](ios-device-enrollment-program-in-microsoft-intune.md) aracılığıyla ya da [doğrudan](ios-direct-enrollment-in-microsoft-intune.md) veya [Kurulum Yardımcısı](ios-setup-assistant-enrollment-in-microsoft-intune.md) kaydı için Mac bilgisayarda Apple Configurator aracı kullanılarak kayıt yapılmasını destekler.

[Şirkete ait iOS cihazlarını kaydetmeyi](enroll-corporate-owned-ios-devices-in-microsoft-intune.md) öğrenin.

## <a name="create-a-device-enrollment-manager-account"></a>Cihaz kayıt yöneticisi hesabı oluşturma

Kuruluşunuzdaki çok sayıda mobil cihazı Intune ile yönetmek için tek kullanıcılı cihaz kayıt yöneticisi (DEM) hesabı oluşturabilirsiniz. Bir DEM hesabı oluşturduktan sonra, belirlenen bir hesap yöneticisi standart bir kullanıcıdan beş cihaz daha fazla kaydedebilir.

DEM hesabını yalnızca tek, belirli bir kullanıcı tarafından kullanılanlar dışındaki cihazları kaydetmek için kullanabilirsiniz. Bu tür cihazlar örneğin satış noktası veya kamu hizmeti uygulamalarına uygundur ancak e-postaya veya şirket kaynaklarına erişmesi gereken kullanıcılar için uygun değildir.

[DEM hesabı kullanarak şirkete ait cihazları kaydetme](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) hakkında bilgi edinin.

## <a name="enroll-corporateowned-windows-10-enterprise-devices"></a>Şirkete ait Windows 10 Enterprise cihazlarını kaydetme

Kuruluşunuzda Azure Active Directory Premium veya Microsoft Enterprise Mobility Suite kullanıyorsanız, [Windows 10 Enterprise cihazlarını kaydedebilirsiniz](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview). Bir kullanıcı bir cihaza iş veya okul hesabı eklerse, cihaz otomatik olarak "şirkete ait" olarak etiketlenir.

## <a name="import-imei-numbers"></a>IMEI numaralarını içeri aktarma

Çoğu mobil cihaz üreticisi, cihazlarında Uluslararası Mobil Donanım Kimliği (IMEI) adı verilen benzersiz bir numara kullanır. Kuruluşunuza ait cihazlar için IMEI numaralarını içeri aktarabilirsiniz. Cihaz Intune’la yönetilen bir cihaza dönüştüğünde, şirkete ait cihaz olarak etiketlenir.

[IMEI numaraları kullanarak şirkete ait cihazları etiketleme](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md) hakkında bilgi edinin.

## <a name="identify-a-device-as-corporateowned"></a>Bir cihazı şirkete ait olarak tanımlama

Bir cihazlar listesinde, **Sahiplik** değerinin karşılığı **Şirket**’tir. Şirkete ait bir cihaz şu özelliklerden birine sahiptir:

 - Cihaz [bir DEM hesabı kullanılarak kaydedilmiştir](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md).
 - Cihaz [Apple DEP](ios-device-enrollment-program-in-microsoft-intune.md) veya [Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md) kullanılarak kaydedilmiştir.
 - Cihaz üreticisi [IMEI numaraları kullanarak cihazı önceden beyan etmiştir](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md).
 - Cihaz [bir Windows 10 Enterprise cihazı olarak Azure Active Directory veya Enterprise Mobility Suite](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview)’e kaydedilmiştir.



<!--HONumber=Nov16_HO1-->


