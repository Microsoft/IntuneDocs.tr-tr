---
title: "Microsoft Intune cihaz kaydı nedir?"
titlesuffix: Azure portal
description: "iOS, Android ve Windows cihazları için kayıt hakkında bilgi edinin.\""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 10/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: caf399650e0a6382d3e03a133cad3aee1eda2d39
ms.sourcegitcommit: fc24d7eb4838b9102088dd4dcf5d1aa6b2c2e590
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/03/2017
---
# <a name="what-is-device-enrollment"></a>Cihaz kaydı nedir?
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Bu konu başlığı altında, Intune yönetiminde kayıt konusu açıklanır ve mobil cihazları kaydetmenin farklı yollar listelenir.

Cihazları yönetebilmek için Intune’a kaydedersiniz. Intune belgelerinde bu özellik mobil cihaz yönetimi (MDM) olarak adlandırılır. Cihazlar Intune’a kaydedildiğinde, bunlara bir MDM sertifikası verilir ve cihazlar bu sertifikayı Intune hizmetiyle iletişim kurmak için kullanır.

Cihazları kaydetme biçiminiz, cihaz türüne, sahipliğine ve size gereken yönetim düzeyine bağlıdır. "Kendi cihazını getir" (KCG) kaydı, kullanıcıların kendi kişisel telefonlarını, tabletlerini veya bilgisayarlarını kaydetmesine izin verir. Şirkete ait cihaz (COD) kaydetme; otomatik kaydetme, paylaşılan cihazlar veya önceden yetkilendirilmiş kaydetme gereksinimleri gibi yönetim senaryolarına olanak tanır.

Şirket içinde veya bulutta barındırılan Exchange ActiveSync kullanırsanız, kayda gerek kalmadan basit Intune yönetimini etkinleştirebilirsiniz (çok yakında daha fazla bilgi sağlanacaktır). Windows bilgisayarlarını mobil cihazlar olarak yönetebilirsiniz. Aşağıda açıklandığı gibi önerilen yöntem budur.


## <a name="overview-of-device-enrollment-methods"></a>Cihaz kayıt yöntemlerine genel bakış

Aşağıdaki tabloda Intune kayıt yöntemlerine, özelliklerine ve aşağıda açıklanan gereksinimlerine genel bir bakış sunulur.

**Gösterge**

- **Sıfırlama gerekli** - Cihaz kayıt sırasında fabrika ayarlarına sıfırlanır.
- **Kullanıcı Benzeşimi** - Cihazlarla kullanıcıları ilişkilendirir. Daha fazla bilgi için bkz. [Kullanıcı benzeşimi](device-enrollment-program-enroll-ios.md).
- **Kilitli** - Kullanıcıların cihazların kaydını silmesini engeller.

**iOS kayıt yöntemleri**

| **Yöntem** |  **Sıfırlama Gerekli** |    **Kullanıcı Benzeşimi**   |   **Kilitli** | **Ayrıntılar** |
|:---:|:---:|:---:|:---:|:---:|
|**[KCG](#byod)** | Hayır|    Evet |   Hayır | [Daha fazla bilgi](./apple-mdm-push-certificate-get.md)|
|**[DEM](#dem)**|   Hayır |Hayır |Hayır  | [Daha fazla bilgi](./device-enrollment-program-enroll-ios.md)|
|**[DEP](#dep)**|   Evet |   İsteğe bağlı |  İsteğe bağlı|[Daha fazla bilgi](./device-enrollment-program-enroll-ios.md)|
|**[USB-SA](#usb-sa)**| Evet |   İsteğe bağlı |  Hayır| [Daha fazla bilgi](./apple-configurator-setup-assistant-enroll-ios.md)|
|**[USB-Direct](#usb-direct)**| Hayır |    Hayır  | Hayır|[Daha fazla bilgi](./apple-configurator-direct-enroll-ios.md)|

**Windows kayıt yöntemleri**

| **Yöntem** |  **Sıfırlama Gerekli** |    **Kullanıcı Benzeşimi**   |   **Kilitli** | **Ayrıntılar**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[KCG](#byod)** | Hayır |   Evet |   Hayır | [Daha fazla bilgi](windows-enroll.md)|
|**[DEM](#dem)**|   Hayır |Hayır |Hayır  |[Daha fazla bilgi](device-enrollment-manager-enroll.md)|
|**Otomatik kayıt** | Hayır |Evet |Hayır | [Daha fazla bilgi](./windows-enroll.md#enable-windows-10-automatic-enrollment)|
|**Toplu kayıt** |Hayır |Hayır |Hayır | [Daha fazla bilgi](./windows-bulk-enroll.md) |

**Android kayıt yöntemleri**

| **Yöntem** |  **Sıfırlama Gerekli** |    **Kullanıcı Benzeşimi**   |   **Kilitli** | **Ayrıntılar**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[KCG](#byod)** | Hayır|    Evet |   Hayır | [Daha fazla bilgi](./android-enroll.md)|
|**[DEM](#dem)**|   Hayır |Hayır |Hayır  |[Daha fazla bilgi](./device-enrollment-program-enroll-ios.md)|
|**Android for Work**| Hayır | Evet | Hayır| [Daha fazla bilgi](./android-enroll.md#enable-enrollment-of-android-for-work-devices) |


## <a name="byod"></a>KCG
“Kendi cihazını getir” kullanıcıları Şirket Portalı uygulamasını yükleyip çalıştırarak cihazlarını kaydeder. Bu program, kullanıcıların e-posta gibi şirket kaynaklarına erişmesini sağlar.

## <a name="corporate-owned-devices"></a>Şirkete ait cihazlar
Şirkete ait cihazların (COD) kayıt senaryoları aşağıda verilmiştir. iOS cihazları, Apple tarafından sağlanan araçlar üzerinden doğrudan kaydedilebilir. Tüm cihaz türleri, cihaz kayıt yöneticisini kullanan bir yönetici ya da müdür tarafından kaydedilebilir. IMEI numaralı cihazlar da, COD senaryolarını etkinleştirmek için şirkete ait olarak tanımlanabilir ve etiketlenebilir.

### <a name="dem"></a>DEM
Cihaz kayıt yöneticisi (DEM), şirkete ait birden çok cihazı kaydetmek ve yönetmek için kullanılan özel bir kullanıcı hesabıdır. Yöneticiler Şirket Portalı’nı yükleyebilir ve kullanıcısı olmayan birçok cihazı kaydedebilir. [DEM](./device-enrollment-manager-enroll.md) hakkında daha fazla bilgi edinin.

### <a name="dep"></a>DEP
Apple Aygıt Kayıt Programı (DEP) yönetimi, “havadan” ilke oluşturmanıza ve DEP ile satın alınan ve yönetilen iOS cihazlara dağıtmanıza olanak sağlar. Cihaz, kullanıcı cihazı ilk açtığında ve iOS Ayarlama Yardımcısı’nı çalıştırdığında kaydedilir. Bu yöntem, iOS denetimli modunu destekler ve bu mod, bir cihazın belirli işlevlerle yapılandırılmasına olanak tanır.

iOS DEP kaydı hakkında daha fazla bilgi edinin:

- [iOS cihazlarının nasıl kaydedileceğini belirleme](ios-enroll.md)
- [Cihaz Kayıt Programı’nı kullanarak iOS cihazlarını kaydetme](https://docs.microsoft.com/intune/device-restrictions-ios#device-enrollment-program)

### <a name="usb-sa"></a>USB-SA
BT yöneticileri, şirkete ait tüm cihazları Kurulum Yardımcısı kullanarak el ile kaydetme işlemine hazırlamak için USB aracılığıyla Apple Configurator kullanır. BT yöneticisi bir kayıt profili oluşturur ve bunu Apple Configurator’a aktarır. Kullanıcılar cihazlarını aldığında, bu cihazları kaydetmek için Kurulum Yardımcısını çalıştırmaları istenir. Bu yöntem **iOS Denetimli** modunu destekler ve bu mod da aşağıdaki özellikleri etkinleştirir:
  - Kilitli kayıt
  - Bilgi noktası modu ile diğer gelişmiş yapılandırmalar ve kısıtlamalar

Kurulum Yardımcısı ile iOS Apple Configurator kaydı hakkında daha fazla bilgi edinin:

- [iOS cihazlarının nasıl kaydedileceğine karar verme](enrollment-method-choose-ios.md)
- [Configurator ve Kurulum Yardımcısı ile iOS cihazlarını kaydetme](apple-configurator-setup-assistant-enroll-ios.md)

### <a name="usb-direct"></a>USB-Direct
Doğrudan kayıt için yöneticinin bir kayıt ilkesi oluşturup bunu Apple Configurator’a aktararak her cihazı el ile kaydetmesi gerekir. USB bağlantılı, şirkete ait cihazlar fabrika sıfırlamasına gerek kalmadan doğrudan kaydedilir. Cihazlar, kullanıcısız cihaz olarak yönetilir. Bunlar kilitli veya denetimli değildir ve koşullu erişimi, jailbreak algılamasını ya da mobil uygulama yönetimini destekleyemez.

iOS kaydı hakkında daha fazla bilgi için bkz:

- [iOS cihazlarının nasıl kaydedileceğine karar verme](enrollment-method-choose-ios.md)
- [Configurator ve doğrudan kayıt ile iOS cihazlarını kaydetme](apple-configurator-direct-enroll-ios.md)

## <a name="mobile-device-management-with-exchange-activesync-and-intune"></a>Exchange ActiveSync ve Intune ile mobil cihaz yönetimi
Kaydedilmemiş ancak Exchange ActiveSync’e (EAS) bağlanan mobil cihazlar, EAS MDM ilkesi kullanılarak Intune tarafından yönetilebilir. Intune, şirket içinde veya bulutta barındırılan EAS ile iletişim kurmak için bir Exchange Connector kullanır. Çok yakında daha fazla bilgi sağlanacaktır.

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>MDM sertifikası süre sonunda mobil cihazı temizleme

Mobil cihazlar Intune hizmetiyle iletişim kurduğunda MDM sertifikası otomatik olarak yenilenir. Mobil cihazlar temizlendiğinde veya belirli bir süre boyunca Intune hizmetiyle iletişim kuramadığında, MDM sertifikası yenilenmez. MDM sertifikasının süre sonundan 180 gün sonra, cihaz Azure Portal’dan kaldırılır.
