---
title: Microsoft Intune cihaz kaydı nedir?
titleSuffix: Microsoft Intune
description: İOS/ıpados, Android ve Windows cihazları için kayıt hakkında bilgi edinin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 4/24/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7955c91a33edef37b86f5bd8f29dfb681d28030e
ms.sourcegitcommit: 51591b862d97904291af7aa53a6eb341b11a761e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/17/2020
ms.locfileid: "77415337"
---
# <a name="what-is-device-enrollment"></a>Cihaz kaydı nedir?
[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Intune; iş gücünüzün cihazları, uygulamaları ve şirket verilerinize erişimini yönetmenizi sağlar. Bu mobil cihaz yönetimini kullanmak için cihazın önce Intune hizmetinde kaydedilmesi gerekir. Bir cihaz kaydolduğunda, bu bir MDM sertifikası verilir. Bu sertifika, Intune hizmeti ile iletişim kurmak için kullanılır.

Aşağıdaki tablolarda görebileceğiniz gibi, iş gücünüzün cihazlarını kaydetmek için çeşitli yöntemler vardır. Her bir yöntem cihazın sahipliği (kişisel veya şirket), cihaz türü (iOS, Windows, Android) ve yönetim gereksinimlerine (sıfırlama, benzeşim, kilitleme) bağlıdır.

Varsayılan olarak tüm platform cihazları Intune'a kaydedilebilir. Ancak [cihazları platforma göre kısıtlayabilirsiniz](enrollment-restrictions-set.md#create-a-device-type-restriction).

## <a name="iosipados-enrollment-methods"></a>iOS/ıpados kayıt yöntemleri

| **Yöntem** | **Sıfırlama Gerekli** | [**Kullanıcı Benzeşimi**](device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile) | **Kilitli** | **Ayrıntılar** |
|:---:|:---:|:---:|:---:|:---:|
| | Kayıt sırasında cihazlar silinir. | Her bir cihazı bir kullanıcıyla ilişkilendirir.| Yanıt Evet ise, kullanıcılar cihazların kaydını geri kaydedemez. | |
|**[KCG](#bring-your-own-device)** | Hayır| Evet | Hayır | [Daha fazla bilgi](apple-mdm-push-certificate-get.md)|
|**[DEM](#device-enrollment-manager)**| Hayır |Hayır |Hayır | [Daha fazla bilgi](device-enrollment-program-enroll-ios.md)|
|**[DEP](#apple-device-enrollment-program)**| Evet | İsteğe bağlı | İsteğe bağlı|[Daha fazla bilgi](device-enrollment-program-enroll-ios.md)|
|**[USB-SA](#usb-sa)**| Evet | İsteğe bağlı | Hayır| [Daha fazla bilgi](apple-configurator-enroll-ios.md)|
|**[USB-Direct](#usb-direct)**| Hayır | Hayır | Hayır|[Daha fazla bilgi](apple-configurator-enroll-ios.md)|

## <a name="macos-enrollment-methods"></a>macOS kayıt yöntemleri
| **Yöntem** |  **Sıfırlama Gerekli** |  **Kullanıcı Benzeşimi** | **Kilitli** | **Ayrıntılar**|
|:---:|:---:|:---:|:---:|:---:|
|**[KCG](#bring-your-own-device)** | Hayır| Evet | Hayır | [Daha fazla bilgi](macos-enroll.md)|
|**[DEM](#device-enrollment-manager)**| Hayır |Hayır |Hayır  | [Daha fazla bilgi](device-enrollment-manager-enroll.md)|
|**[DEP](#apple-device-enrollment-program)**| Evet | İsteğe bağlı | İsteğe bağlı|[Daha fazla bilgi](device-enrollment-program-enroll-macos.md)|

## <a name="windows-enrollment-methods"></a>Windows kayıt yöntemleri

| **Yöntem** | **Sıfırlama Gerekli** | **Kullanıcı Benzeşimi** | **Kilitli** | **Ayrıntılar**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[KCG](#bring-your-own-device)** | Hayır | Evet | Hayır | [Daha fazla bilgi](windows-enroll.md)|
|**[DEM](#device-enrollment-manager)**| Hayır |Hayır |Hayır |[Daha fazla bilgi](device-enrollment-manager-enroll.md)|
|**Otomatik kayıt** | Hayır |Evet |Hayır | [Daha fazla bilgi](windows-enroll.md#enable-windows-10-automatic-enrollment)|
|**Autopilot** |Evet |Evet |Hayır | [Daha fazla bilgi](enrollment-autopilot.md)
|**Toplu kayıt** |Hayır |Hayır |Hayır | [Daha fazla bilgi](windows-bulk-enroll.md) |
|**Ortak yönetim** |Hayır |Evet |Hayır | [Daha fazla bilgi](https://docs.microsoft.com/configmgr/core/clients/manage/co-management-overview)
|**GPO** |Hayır |Evet |Hayır | [Daha fazla bilgi](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)

## <a name="android-enrollment-methods"></a>Android kayıt yöntemleri

| **Kişisel** | **Kayıt yöntemleri** | **Sıfırlama Gerekli** | **Kullanıcı Benzeşimi** | **Kilitli** | **Ayrıntılar**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**Android Cihaz Yöneticisi**|**Şirket Portalı aracılığıyla başlatılan Kullanıcı** | Hayır | Evet | Hayır | [Daha fazla bilgi](https://docs.microsoft.com/intune-user-help/enroll-device-android-company-portal)|
|**Android kurumsal Iş profili**|**Şirket Portalı aracılığıyla başlatılan Kullanıcı**| Hayır | Evet | Hayır | [Daha fazla bilgi](android-work-profile-enroll.md)|


| **Kurumsal** | **Kayıt yöntemleri** | **Sıfırlama Gerekli** | **Kullanıcı Benzeşimi** | **Kilitli** | **Ayrıntılar**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**Android Cihaz Yöneticisi**|**[DEM](#device-enrollment-manager) Şirket Portalı aracılığıyla başlatıldı**| Hayır | Hayır | Hayır |[Daha fazla bilgi](device-enrollment-manager-enroll.md)|
|**Android Cihaz Yöneticisi**|**(Önceden tanımlanmış ıMEı veya SN) Şirket Portalı aracılığıyla başlatılan Kullanıcı**| Hayır | Evet | Hayır | [Daha fazla bilgi](./../corporate-identifiers-add.md)|
|**Zeköşeli Mobility uzantılarına sahip Android Cihaz Yöneticisi**|**Şirket Portalı aracılığıyla başlatılan Kullanıcı veya [dem](#device-enrollment-manager)**| Hayır | Kullanıcı başlatılmışsa Evet, [dem](#device-enrollment-manager) başlatılmışsa Hayır | Hayır | [Daha fazla bilgi](../configuration/android-zebra-mx-overview.md)|
|**Android kurumsal adanmış**|**NFC, Token, QR kodu, sıfır Touch**| Evet | Hayır | İlke aracılığıyla yapılandırılabilir | [Daha fazla bilgi](android-kiosk-enroll.md)|
|**Android kurumsal tam yönetilen**|**NFC, Token, QR kodu, sıfır Touch**| Evet | Evet | İlke aracılığıyla yapılandırılabilir | [Daha fazla bilgi](android-dedicated-devices-fully-managed-enroll.md)|


## <a name="bring-your-own-device"></a>Kendi cihazını getir
Kendi cihazlarınızı getir (KCG), kişisel telefonlar, tabletleri ve bilgisayarları içerir. Kullanıcılar, KCG’leri kaydetmek için Şirket Portalı uygulamasını yükleyip çalıştırır. Bu program, kullanıcıların e-posta gibi şirket kaynaklarına erişmesini sağlar.

## <a name="corporate-owned-device"></a>Şirkete ait cihaz
[Şirkete ait cihazlar (COD)](corporate-identifiers-add.md) arasında kuruluşa ait olan ve iş gücüne dağıtılmış telefonlar, tabletler ve bilgisayarlar bulunur. COD kaydı; otomatik kayıt, paylaşılan cihazlar veya önceden yetkilendirilmiş kaydetme gereksinimleri gibi yönetim senaryolarını destekler. COD’ları kaydetmenin yaygın bir yolu, bir yöneticinin cihaz kayıt yöneticisini (DEM) kullanarak kayıt yapmasıdır. iOS/ıpados cihazları, Apple tarafından sunulan Aygıt Kayıt Programı (DEP) araçları aracılığıyla doğrudan kaydedilebilir. IMEI numaralı cihazlar da şirkete ait olarak tanımlanabilir ve etiketlenebilir.

### <a name="device-enrollment-manager"></a>Cihaz kaydı yöneticisi
Cihaz kayıt yöneticisi (DEM), şirkete ait birden çok cihazı kaydetmek ve yönetmek için kullanılan özel bir kullanıcı hesabıdır. Yöneticiler Şirket Portalı’nı yükleyebilir ve kullanıcısı olmayan birçok cihazı kaydedebilir. Bu tür cihazlar örneğin satış noktası veya yardımcı uygulamalara uygundur ancak e-postaya veya şirket kaynaklarına erişmesi gereken kullanıcılar için uygun değildir. [DEM](device-enrollment-manager-enroll.md) hakkında daha fazla bilgi edinin.

### <a name="apple-device-enrollment-program"></a>Apple Cihaz Kaydı Programı
Apple Aygıt Kayıt Programı (DEP) yönetimi, DEP ile satın alınan ve yönetilen iOS/ıpados ve macOS cihazlarına "hava üzerinden" ilkesi oluşturmanıza ve dağıtmanıza olanak tanır. Cihaz, kullanıcı cihazı ilk açtığında ve Ayarlama Yardımcısı’nı çalıştırdığında kaydedilir. Bu yöntem, bir cihazın belirli işlevlerle yapılandırılmasını sağlayan iOS/ıpados denetimli modunu destekler.

İOS/ıpados DEP kaydı hakkında daha fazla bilgi edinin:

- [İOS/ıpados cihazlarının nasıl kaydedileceğini seçin](ios-enroll.md)
- [Aygıt Kayıt Programı kullanarak iOS/ıpados cihazlarını kaydetme](device-enrollment-program-enroll-ios.md)

### <a name="usb-sa"></a>USB-SA
BT yöneticileri, şirkete ait tüm cihazları Kurulum Yardımcısı kullanarak el ile kaydetme işlemine hazırlamak için USB aracılığıyla Apple Configurator kullanır. BT yöneticisi bir kayıt profili oluşturur ve bunu Apple Configurator’a aktarır. Kullanıcılar cihazlarını alırken, daha sonra cihazını kaydetmek için Kurulum Yardımcısı 'Nı çalıştırması istenir. Bu yöntem **iOS Denetimli** modunu destekler ve bu mod da aşağıdaki özellikleri etkinleştirir:
- Kilitli kayıt
- Bilgi noktası modu ile diğer gelişmiş yapılandırmalar ve kısıtlamalar

Kurulum Yardımcısı ile iOS/ıpados Apple Configurator kaydı hakkında daha fazla bilgi edinin:

- [İOS/ıpados cihazlarını kaydetme kararı verme](ios-enroll.md)
- [Configurator ve Kurulum Yardımcısı ile iOS/ıpados cihazlarını kaydetme](apple-configurator-enroll-ios.md)

### <a name="usb-direct"></a>USB-Direct
Doğrudan kayıt için yöneticinin bir kayıt ilkesi oluşturup bunu Apple Configurator’a aktararak her cihazı el ile kaydetmesi gerekir. USB bağlantılı, şirkete ait cihazlar silinmeye gerek kalmadan doğrudan kaydedilir. Cihazlar, kullanıcısız cihaz olarak yönetilir. Bunlar kilitli veya denetimli değildir ve koşullu erişimi, jailbreak algılamayı veya mobil uygulama yönetimini destekleyemez.

İOS/ıpados kaydı hakkında daha fazla bilgi edinmek için bkz.:

- [İOS/ıpados cihazlarını kaydetme kararı verme](ios-enroll.md)
- [Configurator ve doğrudan kayıt ile iOS/ıpados cihazlarını kaydetme](apple-configurator-enroll-ios.md)

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>MDM sertifikası süre sonunda mobil cihazı temizleme

Mobil cihazlar Intune hizmetiyle iletişim kurduğunda MDM sertifikası otomatik olarak yenilenir. Mobil cihazlar silinir veya belirli bir süre boyunca Intune hizmetiyle iletişim kuramazlar, MDM sertifikası yenilenmez. MDM sertifikasının süre sonundan 180 gün sonra, cihaz Azure Portal’dan kaldırılır.
