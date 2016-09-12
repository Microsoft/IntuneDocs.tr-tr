---
title: "Kuruluşa ait cihazları yönetme | Microsoft Intune"
description: "Şirkete ait cihazları (COD), cihaza, nasıl satın alındığına ve kuruluşun gereksinimlerine bağlı olarak, çeşitli yollarla yönetime getirin."
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
ms.sourcegitcommit: ecfeb73efed4a47256275120c52de232c556adfe
ms.openlocfilehash: 58efadf2f9fc34a31070aff93e86083583630caa


---

# Microsoft Intune'la şirketin sahip olduğu cihazları kaydetme
Kuruluşa ait cihazlar (COD), cihaza, nasıl satın alındığına ve kuruluşun gereksinimlerine bağlı olarak Intune tarafından çeşitli yollarla yönetime getirilebilir. Şirkete ait cihazlar, ayrıca, “kendi cihazını getir” (BYOD) senaryolarında olduğu gibi Şirket Portalı uygulamaları yüklenerek de kaydedilebilir ve yönetilebilir.

## Şirketin sahip olduğu iOS cihazları
Bu kayıt yöntemleri, kuruluşun kullanıcılar için cihaz satın aldığı ancak cihazın yönetimini elinde tutmak istediği "Kendi cihazını seç" (KCS) senaryolarına uygundur. Kuruluşunuz iOS cihazları satın aldıysa, cihazın kullanıcı tarafından ilk kez açılmasından başlayarak yönetilebilmesi için, kaydı önceden yapılandırabilirsiniz. Intune, [Apple'ın Cihaz Kayıt Programı (DEP)](ios-device-enrollment-program-in-microsoft-intune.md) aracılığıyla ya da [doğrudan](ios-direct-enrollment-in-microsoft-intune.md) veya [Kurulum Yardımcısı](ios-setup-assistant-enrollment-in-microsoft-intune.md) kaydı için Mac bilgisayarda çalışan Apple Configurator aracı kullanılarak kayıt yapılmasını destekler.

[Şirketin sahip olduğu iOS cihazlarını kaydetme](enroll-corporate-owned-ios-devices-in-microsoft-intune.md)

## Cihaz kayıt yöneticisi
Kuruluşlar, cihaz kayıt yöneticisi hesabı olarak adlandırılan tek bir kullanıcı hesabıyla çok sayıda mobil cihazı yönetmek için Intune'u kullanabilir. Cihaz kayıt yöneticisi hesabı oluşturulduktan sonra, bu hesap bir yönetici tarafından, normal kullanıcılara varsayılan olarak izin verilen standart beş cihazdan fazlasını kaydetmek için kullanılabilir. Cihazları cihaz kayıt yöneticisi hesabıyla kaydetme işlemi yalnızca belirli bir kullanıcı tarafından kullanılmayan cihazlarda çalışır. Bu cihazlar örneğin satış noktası veya kamu hizmeti uygulamalarına uygundur ancak e-postaya veya şirket kaynaklarına erişmesi gereken kullanıcılar için uygun değildir.

[Şirket ait cihazları cihaz kayıt yöneticisi ile kaydetme](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)

## Şirkete ait Windows 10 masaüstü bilgisayarlarını kaydetme

Kuruluşunuzda Azure Active Directory Premium (AADP) veya Enterprise Management Suite (EMS) varsa, [kuruluş için Windows 10’u kaydedebilirsiniz](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview) ve kullanıcılar iş veya okul hesaplarını eklediklerinde bu cihazlar otomatik olarak “şirkete ait” etiketini taşır.

## Cihazları şirkete ait olarak tanımlama

Şirkete ait cihazlar, cihaz listelerinde **Sahiplik** alanında **Şirket** belirtimiyle gösterilir. Cihazlar, aşağıdaki yollarla şirkete ait olarak tanımlanabilir:

 - [Cihaz kayıt yöneticisiyle (DEM) kaydetme](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)
 - Apple'ın [cihaz kayıt programı (DEP)](ios-device-enrollment-program-in-microsoft-intune.md) veya [Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md) ile kaydetme
 - [Cihazları IMEI numaralarıyla önceden bildirme](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md)
 - [Windows 10 cihazlarının Azure Active Directory/Enterprise Management Suite kaydı](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview)

### Uluslararası mobil donanım kimliği (IMEI)

Benzersiz uluslararası mobil donanım kimliği (IMEI) numaraları, birçok mobil cihaz üreticisi için ortak cihaz özelliğidir. Intune yöneticileri şirketin sahip olduğu cihazlar için IMEI numaralarını içeri aktarabilir. Cihaz Intune’la yönetilen bir cihaza dönüştüğünde, şirkete ait cihaz olarak etiketlenir.

[Uluslararası mobil donanım kimliği (IMEI) numaralarıyla şirkete ait cihazları belirtme](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md)



<!--HONumber=Jul16_HO4-->


