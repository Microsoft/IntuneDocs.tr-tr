---
# required metadata

title: Kuruluşa ait cihazları yönetme | Microsoft Intune
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

# Microsoft Intune'la kuruluşa ait cihazları kaydetme
Kuruluşa ait cihazlar (COD), cihaza, nasıl satın alındığına ve kuruluşun gereksinimlerine bağlı olarak Intune tarafından çeşitli yollarla yönetime getirilebilir.

## Kuruluşa ait iOS cihazları
Bu kayıt yöntemleri, kuruluşun kullanıcılar için cihaz satın aldığı ancak cihazın yönetimini elinde tutmak istediği "Kendi cihazını seç" (KCS) senaryolarına uygundur. Kuruluşunuz iOS cihazları satın aldıysa, cihazın kullanıcı tarafından ilk kez açılmasından başlayarak yönetilebilmesi için, kaydı önceden yapılandırabilirsiniz. Intune, [Apple'ın Cihaz Kayıt Programı (DEP)](ios-device-enrollment-program-in-microsoft-intune.md) aracılığıyla ya da [doğrudan](ios-direct-enrollment-in-microsoft-intune.md) veya [Kurulum Yardımcısı](ios-setup-assistant-enrollment-in-microsoft-intune.md) kaydı için Mac bilgisayarda çalışan Apple Configurator aracı kullanılarak kayıt yapılmasını destekler.

[Kuruluşa ait iOS cihazlarını kaydetme](enroll-corporate-owned-ios-devices-in-microsoft-intune.md)

## Cihaz kayıt yöneticisi
Kuruluşlar, cihaz kayıt yöneticisi hesabı olarak adlandırılan tek bir kullanıcı hesabıyla çok sayıda mobil cihazı yönetmek için Intune'u kullanabilir. Cihaz kayıt yöneticisi hesabı oluşturulduktan sonra, bu hesap bir yönetici tarafından, normal kullanıcılara varsayılan olarak izin verilen standart beş cihazdan fazlasını kaydetmek için kullanılabilir. Cihazları cihaz kayıt yöneticisi hesabıyla kaydetme işlemi yalnızca belirli bir kullanıcı tarafından kullanılmayan cihazlarda çalışır. Bu cihazlar örneğin satış noktası veya kamu hizmeti uygulamalarına uygundur ancak e-postaya veya şirket kaynaklarına erişmesi gereken kullanıcılar için uygun değildir.

[Kuruluşa ait cihazları cihaz kayıt yöneticisi ile kaydetme](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)

## Uluslararası mobil donanım kimliği (IMEI)
Benzersiz uluslararası mobil donanım kimliği (IMEI) numaraları, birçok mobil cihaz üreticisi için ortak cihaz özelliğidir. Intune yöneticileri şirketin sahip olduğu cihazlar için IMEI numaralarını içeri aktarabilir. Cihaz Intune tarafından yönetilir hale geldiğinde, kuruluşa ait cihaz olarak etiketlenebilir ve uygun ilkede hedeflenebilir.

[Uluslararası mobil donanım kimliği (IMEI) numaralarıyla kuruluşa ait cihazları belirtme](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

## Kuruluşa ait cihaz kayıt yöntemlerine genel bakış

Aşağıdaki tabloda kuruluşa ait cihaz kayıt yöntemleri ve bunların avantajları gösterilir.

**iOS Kayıt Yöntemleri**

| **Yöntem** |  **[Sıfırlama](#Reset)** |   **[Benzeşim](#Affinity)**   |   **[Kilitli](#Locked)** |
|:---:|:---:|:---:|:---:|
|**[KCG](#BYOD)** | Hayır|    Evet |   Hayır |
|**[DEM](#DEM)**|   Hayır |Hayır |Hayır  |
|**[DEP](#DEP)**|   Evet |   Seçenek |   Seçenek|
|**[USB-SA](#USB-SA)**| Evet |   Seçenek |   Hayır|
|**[USB-Direct](#USB-Direct)**| Hayır |    Hayır  | Hayır|

**Windows ve Android Kayıt Yöntemleri**

| **Yöntem** |  **[Silme](#Wipe)** | **[Kullanıcı](#User)**   |   **[Kilitli](#Locked)** |
|:---:|:---:|:---:|:---:|
|**[KCG](#BYOD)** | Hayır|    Evet |   Hayır |
|**[DEM](#DEM)**|   Hayır |Hayır |Hayır  |

**Kuruluşa ait cihazlar için kayıt yöntemleri**

### KCG
“Kendi Cihazını Getir.” Şirket Portalı uygulamasını kullanıcılar yükler ve cihazlarını kaydeder. Cihazı Şirket Portalı’na kaydetmek cihazın çalışma alanına katılmasını sağlar. iOS cihazlarını Şirket Portalı’na kaydetmek için Apple Kimliği gerekir. Kuruluşa ait cihazlarda KCG ek yapılandırma gerektirmez. [Cihaz yönetimini ayarlama](get-ready-to-enroll-devices-in-microsoft-intune#set-up-device-management.md) adımlarına bakın.

### DEM
Cihaz kayıt yöneticisi. DEM hesaplarını yönetici oluşturur. Bundan sonra, yöneticiler Şirket Portalı’nı yükleyebilir ve kullanıcısı olmayan birçok cihazı kaydedebilir. [DEM](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) hakkında daha fazla bilgi edinin. ([Tabloya dön](#overview-of corporate-owned-device-enrollment-methods))

### DEP
Apple Cihaz Kaydı Programı. DEP ile satın alınan iOS cihazları için ilkeyi yöneticiler oluşturur ve “uzaktan” dağıtır. Kullanıcı iOS Kurulum Yardımcısı’nı çalıştırdığında, cihaz kaydedilir. Bu yöntem **iOS Denetimli** modunu destekler ve bu mod şunlara olanak tanır:
  - Kilitli kayıt
  - Koşullu erişim
  - Kaçış algılama
  - Mobil uygulama yönetimi

[DEP](ios-device-enrollment-program-in-microsoft-intune.md) hakkında daha fazla bilgi edinin. ([Tabloya dön](#overview-of corporate-owned-device-enrollment-methods))

### USB-SA
USB bağlantılı, Kurulum Yardımcısı kaydı. Yönetici Intune ilkesini oluşturur ve bunu Apple Configurator’a aktarır. USB bağlantılı cihazlar Intune ilkesiyle hazırlanır. Yöneticinin her cihazı el ile kaydetmesi gerekir. Kullanıcılar cihazlarını alır ve Kurulum Yardımcısı7nı çalıştırarak cihazlarını kaydederler. Bu yöntem **iOS Denetimli** modunu destekler ve bu mod şunlara olanak tanır:
  - Kilitli kayıt
  - Koşullu erişim
  - Kaçış algılama
  - Mobil uygulama yönetimi

[Apple Configurator ile Kurulum Yardımcısı kaydı](ios-setup-assistant-enrollment-in-microsoft-intune.md) hakkında daha fazla bilgi edinin. ([Tabloya dön](#overview-of corporate-owned-device-enrollment-methods))

### USB-Direct
Doğrudan kayıt. Yönetici Intune ilkesini oluşturur ve bunu Apple Configurator’a aktarır. USB bağlantılı cihazlar fabrika sıfırlamasına gerek kalmadan doğrudan kaydedilir. Yöneticinin her cihazı el ile kaydetmesi gerekir. Cihazlar, kullanıcısız cihaz olarak yönetilir. Bunlar kilitli veya denetimli değildir ve koşullu erişimi, kaçış algılamasını, mobil uygulama yönetimini destekleyemez. [Apple Configurator ile doğrudan kayıt](ios-direct-enrollment-in-microsoft-intune.md) hakkında daha fazla bilgi edinin. ([Tabloya dön](#overview-of corporate-owned-device-enrollment-methods))

**Kuruluşa ait mobil cihazların davranışı**

### Sıfırlama
Cihazı kaydetmek için cihazın fabrika ayarlarına sıfırlanması, cihazdan tüm veriler kaldırılarak ilk durumuna döndürülmesi gerekip gerekmediğini belirtir.
([Tabloya dön](#overview-of corporate-owned-device-enrollment-methods))

### Benzeşim
Kayıt yönteminin, cihazı belirli bir kullanıcıya bağlayan “Kullanıcı Benzeşimi” özelliğini destekleyip desteklemediğini belirtir. “Seçenek” ile işaretli cihazlar kullanıcı benzeşimiyle veya benzeşim olmadan kaydedilebilir. Aşağıdakileri desteklemek için kullanıcı benzeşimi gereklidir:
  - Mobil uygulama yönetimi (MAM) uygulamaları
  - E-postaya ve şirket verilerine koşullu erişim
  - Şirket Portalı uygulaması

([Tabloya dön](#overview-of corporate-owned-device-enrollment-methods)) ([Tabloya dön](#overview-of corporate-owned-device-enrollment-methods))

### Kilitle
Kullanıcının Intune ilkesini kaldırıp cihazı etkili bir şekilde yönetimden kaldırmasını önlemek için cihazın kilitlenip kilitlenemeyeceğini belirtir. iOS cihazlarında, cihazın kilitlenmesi için cihaz Denetimli modda olmalıdır.
([Tabloya dön](#overview-of corporate-owned-device-enrollment-methods)) ([Tabloya dön](#overview-of corporate-owned-device-enrollment-methods))


<!--HONumber=Jun16_HO1-->


