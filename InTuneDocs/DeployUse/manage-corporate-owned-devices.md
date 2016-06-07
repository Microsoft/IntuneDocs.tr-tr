---
# required metadata

title: Microsoft Intune’la şirketin sahip olduğu cihazları yönetme | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 2b60bbff-25e6-489b-9621-c71b4275fa06

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune'la şirketin sahip olduğu cihazları kaydetme
Kuruluşun veya şirketin sahip olduğu cihazlar (COD), cihaza ve nasıl satın alındığına bağlı olarak çeşitli yollarla yönetime getirilebilir.

## Şirketin sahip olduğu iOS cihazları
Bu kayıt yöntemleri, kuruluşun kullanıcılar için cihaz satın aldığı ancak cihazın yönetimini elinde tutmak istediği "Kendi cihazını seç" (KCS) senaryolarına uygundur. Kuruluşunuz iOS cihazları satın aldıysa, cihazın kullanıcı tarafından ilk kez açılmasından başlayarak yönetilebilmesi için, kaydı önceden yapılandırabilirsiniz. Intune, [Apple'ın Cihaz Kayıt Programı (DEP)](ios-device-enrollment-program-in-microsoft-intune.md) aracılığıyla ya da [doğrudan](ios-direct-enrollment-in-microsoft-intune.md) veya [Kurulum Yardımcısı](ios-setup-assistant-enrollment-in-microsoft-intune.md) kaydı için Mac bilgisayarda çalışan Apple Configurator aracı kullanılarak kayıt yapılmasını destekler.

[Şirketin sahip olduğu iOS cihazlarını kaydetme](enroll-corporate-owned-ios-devices-in-microsoft-intune.md)

## Cihaz kayıt yöneticisi
Kuruluşlar, cihaz kayıt yöneticisi hesabı olarak adlandırılan tek bir kullanıcı hesabıyla çok sayıda mobil cihazı yönetmek için Intune'u kullanabilir. Cihaz kayıt yöneticisi hesabı oluşturulduktan sonra, bu hesap bir yönetici tarafından, normal kullanıcılara varsayılan olarak izin verilen standart beş cihazdan fazlasını kaydetmek için kullanılabilir. Cihazları cihaz kayıt yöneticisi hesabıyla kaydetme işlemi yalnızca belirli bir kullanıcı tarafından kullanılmayan cihazlarda çalışır. Bu cihazlar örneğin satış noktası veya kamu hizmeti uygulamalarına uygundur ancak e-postaya veya şirket kaynaklarına erişmesi gereken kullanıcılar için uygun değildir.

[Şirket ait cihazları cihaz kayıt yöneticisi ile kaydetme](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)

## Şirkete ait cihazları uluslararası mobil donanım kimliğiyle (IMEI) belirtme
Benzersiz uluslararası mobil donanım kimliği (IMEI) numaraları, birçok mobil cihaz üreticisi için ortak cihaz özelliğidir. Intune yöneticileri şirketin sahip olduğu cihazlar için IMEI numaralarını içeri aktarabilir. Cihaz Intune tarafından yönetilir hale geldiğinde, şirkete ait cihaz olarak etiketlenebilir ve uygun ilkede hedeflenebilir.

[Uluslararası mobil donanım kimliği (IMEI) numaralarıyla şirkete ait cihazları belirtme](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md)


<!--HONumber=May16_HO2-->

