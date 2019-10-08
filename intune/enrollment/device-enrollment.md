---
title: Microsoft Intune cihaz kaydı nedir?
titleSuffix: Microsoft Intune
description: İOS, Android ve Windows cihazları için kayıt hakkında bilgi edinin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 4/24/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: e3fb9af260b8fddc78b644b8ede056c90bac24d0
ms.sourcegitcommit: 29b1113dc04534c4c87c33c773c5a0e24266e042
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/07/2019
ms.locfileid: "71999360"
---
# <a name="what-is-device-enrollment"></a>Cihaz kaydı nedir?
[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Intune, iş gücünüzün cihazlarını ve uygulamalarını ve şirket verilerinize erişimini yönetmenizi sağlar. Bu mobil cihaz yönetimini (MDM) kullanmak için önce cihazların Intune hizmetine kaydolması gerekir. Bir cihaz kaydolduğunda, bu bir MDM sertifikası verilir. Bu sertifika, Intune hizmeti ile iletişim kurmak için kullanılır.

Aşağıdaki tablolarda görebileceğiniz gibi, iş gücünüzün cihazlarını kaydetmek için çeşitli yöntemler vardır. Her yöntem cihazın sahipliğini (kişisel veya kurumsal), cihaz türü (iOS, Windows, Android) ve yönetim gereksinimlerine (sıfırlamaları, benzeşim, kilitleme) bağlıdır.

Varsayılan olarak, Tüm platformlardaki cihazların Intune 'a kaydetmesine izin verilir. Ancak, [cihazları platforma göre kısıtlayabilirsiniz](enrollment-restrictions-set.md#create-a-device-type-restriction).

## <a name="ios-enrollment-methods"></a>iOS kayıt yöntemleri

| **Yöntemidir** | **Sıfırlama gerekli** | [**Kullanıcı benzeşimi**](device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile) | **Kilitlenecek** | **Bilgileri** |
|:---:|:---:|:---:|:---:|:---:|
| | Cihazlar kayıt sırasında temizlenir. | Her cihazı bir kullanıcıyla ilişkilendirir.| Yanıt Evet ise, kullanıcılar cihazların kaydını geri kaydedemez. | |
|**[KCG](#bring-your-own-device)** | Hayır| Evet | Hayır | [Daha fazla bilgi](apple-mdm-push-certificate-get.md)|
|**[DEM](#device-enrollment-manager)**| Hayır |Hayır |Hayır | [Daha fazla bilgi](device-enrollment-program-enroll-ios.md)|
|**[DEP](#apple-device-enrollment-program)**| Evet | İsteğe Bağlı | İsteğe Bağlı|[Daha fazla bilgi](device-enrollment-program-enroll-ios.md)|
|**[USB-SA](#usb-sa)**| Evet | İsteğe Bağlı | Hayır| [Daha fazla bilgi](apple-configurator-enroll-ios.md)|
|**[USB-doğrudan](#usb-direct)**| Hayır | Hayır | Hayır|[Daha fazla bilgi](apple-configurator-enroll-ios.md)|

## <a name="macos-enrollment-methods"></a>macOS kayıt yöntemleri
| **Yöntemidir** |  **Sıfırlama gerekli** |  **Kullanıcı benzeşimi** | **Kilitlenecek** | **Bilgileri**|
|:---:|:---:|:---:|:---:|:---:|
|**[KCG](#bring-your-own-device)** | Hayır| Evet | Hayır | [Daha fazla bilgi](macos-enroll.md)|
|**[DEM](#device-enrollment-manager)**| Hayır |Hayır |Hayır  | [Daha fazla bilgi](device-enrollment-manager-enroll.md)|
|**[DEP](#apple-device-enrollment-program)**| Evet | İsteğe Bağlı | İsteğe Bağlı|[Daha fazla bilgi](device-enrollment-program-enroll-macos.md)|

## <a name="windows-enrollment-methods"></a>Windows kayıt yöntemleri

| **Yöntemidir** | **Sıfırlama gerekli** | **Kullanıcı benzeşimi** | **Kilitlenecek** | **Bilgileri**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[KCG](#bring-your-own-device)** | Hayır | Evet | Hayır | [Daha fazla bilgi](windows-enroll.md)|
|**[DEM](#device-enrollment-manager)**| Hayır |Hayır |Hayır |[Daha fazla bilgi](device-enrollment-manager-enroll.md)|
|**Otomatik Kaydet** | Hayır |Evet |Hayır | [Daha fazla bilgi](windows-enroll.md#enable-windows-10-automatic-enrollment)|
|**Autopilot** |Evet |Evet |Hayır | [Daha fazla bilgi](enrollment-autopilot.md)
|**Toplu kayıt** |Hayır |Hayır |Hayır | [Daha fazla bilgi](windows-bulk-enroll.md) |
|**Ortak yönetim** |Hayır |Evet |Hayır | [Daha fazla bilgi](https://docs.microsoft.com/sccm/core/clients/manage/co-management-overview)
|**GPO** |Hayır |Evet |Hayır | [Daha fazla bilgi](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)

## <a name="android-enrollment-methods"></a>Android kayıt yöntemleri

| **C** | **Kayıt yöntemleri** | **Sıfırlama gerekli** | **Kullanıcı benzeşimi** | **Kilitlenecek** | **Bilgileri**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**Android Cihaz Yöneticisi**|**Şirket Portalı aracılığıyla başlatılan Kullanıcı** | Hayır | Evet | Hayır | [Daha fazla bilgi](https://docs.microsoft.com/intune-user-help/enroll-device-android-company-portal)|
|**Android kurumsal Iş profili**|**Şirket Portalı aracılığıyla başlatılan Kullanıcı**| Hayır | Evet | Hayır | [Daha fazla bilgi](android-work-profile-enroll.md)|


| **Ağı** | **Kayıt yöntemleri** | **Sıfırlama gerekli** | **Kullanıcı benzeşimi** | **Kilitlenecek** | **Bilgileri**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**Android Cihaz Yöneticisi**|**[DEM](#device-enrollment-manager) Şirket Portalı aracılığıyla başlatıldı**| Hayır | Hayır | Hayır |[Daha fazla bilgi](device-enrollment-manager-enroll.md)|
|**Android Cihaz Yöneticisi**|**(Önceden tanımlanmış ıMEı veya SN) Şirket Portalı aracılığıyla başlatılan Kullanıcı**| Hayır | Evet | Hayır | [Daha fazla bilgi](./../corporate-identifiers-add.md)|
|**Zeköşeli Mobility uzantılarına sahip Android Cihaz Yöneticisi**|**Şirket Portalı aracılığıyla başlatılan Kullanıcı veya [dem](#device-enrollment-manager)**| Hayır | Kullanıcı başlatılmışsa Evet, [dem](#device-enrollment-manager) başlatılmışsa Hayır | Hayır | [Daha fazla bilgi](../configuration/android-zebra-mx-overview.md)|
|**Android kurumsal adanmış**|**NFC, Token, QR kodu, sıfır Touch**| Evet | Hayır | İlke aracılığıyla yapılandırılabilir | [Daha fazla bilgi](android-kiosk-enroll.md)|
|**Android kurumsal tam yönetilen**|**NFC, Token, QR kodu, sıfır Touch**| Evet | Evet | İlke aracılığıyla yapılandırılabilir | [Daha fazla bilgi](android-dedicated-devices-fully-managed-enroll.md)|


## <a name="bring-your-own-device"></a>Kendi cihazını getir
Kendi cihazlarını getir (KCG) kişisel telefonlar, tabletleri ve bilgisayarları içerir. Kullanıcılar, KCG 'leri kaydetmek için Şirket Portalı uygulamasını yükler ve çalıştırır. Bu program, kullanıcıların e-posta gibi şirket kaynaklarına erişmesine izin verir.

## <a name="corporate-owned-device"></a>Şirkete ait cihaz
[Şirkete ait cihazlar (COD)](corporate-identifiers-add.md) , kuruluşa ait olan ve iş gücüne dağıtılan telefon, tablet ve bilgisayarları içerir. COD kaydı, otomatik kayıt, paylaşılan cihazlar veya önceden yetkilendirilmiş kayıt gereksinimleri gibi senaryoları destekler. Birlikte, bir yönetici veya yöneticinin cihaz kayıt yöneticisi 'ni (DEM) kullanması için yaygın olarak kullanılan bir yöntem. iOS cihazları, Apple tarafından sunulan Aygıt Kayıt Programı (DEP) araçları aracılığıyla doğrudan kaydedilebilir. IMEı numarasına sahip cihazlar aynı zamanda şirkete ait olarak tanımlanabilir ve etiketlenebilir.

### <a name="device-enrollment-manager"></a>Cihaz Kayıt Yöneticisi
Cihaz Kayıt Yöneticisi (DEM), şirkete ait birden çok cihazı kaydetmek ve yönetmek için kullanılan özel bir kullanıcı hesabıdır. Yöneticiler Şirket Portalı yükleyebilir ve Kullanıcı benzeri birçok cihazı kaydedebilir. Bu cihaz türleri, örneğin, e-postaya veya şirket kaynaklarına erişmesi gereken kullanıcılar için değil, satış noktası veya yardımcı uygulamalar için uygundur. [Dem](device-enrollment-manager-enroll.md)hakkında daha fazla bilgi edinin.

### <a name="apple-device-enrollment-program"></a>Apple Aygıt Kayıt Programı
Apple Aygıt Kayıt Programı (DEP) yönetimi, DEP ile satın alınan ve yönetilen iOS ve macOS cihazlarına "hava üzerinden" ilkesi oluşturmanıza ve dağıtmanıza olanak tanır. Kullanıcılar cihazı ilk kez açıp Kurulum Yardımcısını çalıştırdığınızda cihaz kaydedilir. Bu yöntem, bir cihazın belirli işlevlerle yapılandırılmasını sağlayan iOS denetimli modunu destekler.

İOS DEP kaydı hakkında daha fazla bilgi edinin:

- [İOS cihazlarının nasıl kaydedileceğini seçin](ios-enroll.md)
- [Aygıt Kayıt Programı kullanarak iOS cihazlarını kaydetme](device-enrollment-program-enroll-ios.md)

### <a name="usb-sa"></a>USB-SA
BT yöneticileri, şirkete ait her cihazı Kurulum Yardımcısı 'Nı kullanarak kayıt için el ile hazırlamak üzere, USB üzerinden Apple Configurator 'ı kullanır. BT Yöneticisi bir kayıt profili oluşturur ve bunu Apple Configurator 'a aktarır. Kullanıcılar cihazlarını alırken, daha sonra cihazını kaydetmek için Kurulum Yardımcısı 'Nı çalıştırması istenir. Bu yöntem, **iOS** denetimli modunu destekler ve bu, sırasıyla aşağıdaki özellikleri sunar:
- Kilitli kayıt
- Bilgi noktası modu ve diğer gelişmiş yapılandırma ve kısıtlamalar

Kurulum Yardımcısı ile iOS Apple Configurator kaydı hakkında daha fazla bilgi edinin:

- [İOS cihazlarının nasıl kaydedileceğini belirleyin](ios-enroll.md)
- [Configurator ve Kurulum Yardımcısı ile iOS cihazlarını kaydetme](apple-configurator-enroll-ios.md)

### <a name="usb-direct"></a>USB-doğrudan
Doğrudan kayıt için, yöneticinin bir kayıt ilkesi oluşturup Apple Configurator 'a aktararak her cihazı el ile kaydetmesi gerekir. USB bağlantılı, şirkete ait cihazlar doğrudan kaydedilir ve Temizleme gerektirmez. Cihazlar Kullanıcı-daha az cihazlar olarak yönetilir. Bunlar kilitli veya denetimli değildir ve koşullu erişimi, jailbreak algılamayı veya mobil uygulama yönetimini destekleyemez.

İOS kaydı hakkında daha fazla bilgi edinmek için bkz.:

- [İOS cihazlarının nasıl kaydedileceğini belirleyin](ios-enroll.md)
- [Configurator ve doğrudan kayıt ile iOS cihazlarını kaydetme](apple-configurator-enroll-ios.md)

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>MDM sertifikasının süresi dolduktan sonra mobil cihaz Temizleme

Mobil cihazlar Intune hizmetiyle iletişim kurduğunda MDM sertifikası otomatik olarak yenilenir. Mobil cihazlar silinir veya belirli bir süre boyunca Intune hizmetiyle iletişim kuramazlar, MDM sertifikası yenilenmez. MDM sertifikasının süresi dolduktan sonra cihaz Azure portal 180 gün sonra kaldırılır.
