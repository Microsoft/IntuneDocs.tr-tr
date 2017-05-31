---
title: "Microsoft Intune cihaz kaydı nedir?"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: iOS, Android ve Windows cihazlarının kaydını öğrenin."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 57bad4be991b61fe5212d340ab8d89cb6af3b0f7
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---

# <a name="what-is-device-enrollment"></a>Cihaz kaydı nedir?
[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Bu konu başlığı altında, Intune yönetiminde kayıt konusu açıklanır ve mobil cihazları kaydetmenin farklı yollar listelenir.

Cihazları yönetebilmek için Intune’a kaydedersiniz. Intune belgelerinde bu özellik mobil cihaz yönetimi (MDM) olarak adlandırılır. Cihazlar Intune’a kaydedildiğinde, bunlara bir MDM sertifikası verilir ve cihazlar bu sertifikayı Intune hizmetiyle iletişim kurmak için kullanır.

Cihazları kaydetme biçiminiz, cihaz türüne, sahipliğine ve size gereken yönetim düzeyine bağlıdır. "Kendi cihazını getir" (KCG) kaydı, kullanıcıların kendi kişisel telefonlarını, tabletlerini veya bilgisayarlarını kaydetmesine izin verir. Şirkete ait cihaz (COD) kaydetme; otomatik kaydetme, paylaşılan cihazlar veya önceden yetkilendirilmiş kaydetme gereksinimleri gibi yönetim senaryolarına olanak tanır.

Şirket içinde veya bulutta barındırılan Exchange ActiveSync kullanırsanız, kayda gerek kalmadan basit Intune yönetimini etkinleştirebilirsiniz (çok yakında daha fazla bilgi sağlanacaktır). Windows bilgisayarlarını mobil cihazlar olarak yönetebilirsiniz. Aşağıda açıklandığı gibi önerilen yöntem budur.


## <a name="overview-of-device-enrollment-methods"></a>Cihaz kayıt yöntemlerine genel bakış

Aşağıdaki tabloda Intune'a kayıt yöntemleri ve her yöntem için desteklenen özellikler ile gereksinimler gösterilmektedir. Özellik ve gereksinimleri açıklamaları aşağıda verilmiştir. Tabloda aşağıdaki terimler kullanılır:

- **Temizle** - Kullanıcıların cihazı kaydedebilmesi için temizleme yapılıp yapılmaması gerektiğini belirtir. "Temizleme" terimi, cihazın fabrika verilerine döndürülerek tüm verilerin silinmesini ifade eder. Daha fazla bilgi için bkz. [Cihazlarda tam veya seçmeli temizleme kullanma](devices-wipe.md).
- **Benzeşim** - Cihazlarla kullanıcıları ilişkilendirir. Mobil uygulama yönetimi (MAM) ve şirket verilerine koşullu erişim için gereklidir. Daha fazla bilgi için bkz. [Kullanıcı benzeşimi](device-enrollment-program-enroll-ios.md).
- **Kilitle** - Kullanıcıların cihaz kayıtlarını yönetimden kaldırmasının engellenip engellenmediğini gösterir. Kullanıcılar, Şirket Portalı uygulamalarını kullanarak tüm platformlarda cihaz kaydını kaldırabilir. Cihaz kaydını kaldırma işlemi için yerel işletim sistemi menüleri kullanılamaz.


**iOS kayıt yöntemleri**

| **Yöntem** |    **Temizleme gerekli mi?** |    **Benzeşim**    |    **Kilitle** | **Ayrıntılar** |
|:---:|:---:|:---:|:---:|:---:|
|**[KCG](#byod)** | Hayır|    Evet |    Hayır | Çok yakında daha fazla bilgi sağlanacaktır|
|**[DEM](#dem)**|    Hayır |Hayır |Hayır    | [Daha fazla bilgi](device-enrollment-program-enroll-ios.md)|
|**[DEP](#dep)**|    Evet |    İsteğe bağlı |    İsteğe bağlı|[Daha fazla bilgi](device-enrollment-program-enroll-ios.md)|
|**[USB-SA](#usb-sa)**|    Evet |    İsteğe bağlı |    Hayır| [Daha fazla bilgi](apple-configurator-setup-assistant-enroll-ios.md)|
|**[USB-Direct](#usb-direct)**|    Hayır |    Hayır    | Hayır|[Daha fazla bilgi](apple-configurator-direct-enroll-ios.md)|

**Windows kayıt yöntemleri**

| **Yöntem** |    **Temizleme gerekli mi?** |    **Benzeşim**    |    **Kilitle** | **Ayrıntılar**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[KCG](#byod)** | Hayır |    Evet |    Hayır | [Daha fazla bilgi](windows-enroll.md)|
|**[DEM](#dem)**|    Hayır |Hayır |Hayır    |[Daha fazla bilgi](device-enrollment-manager-enroll.md)|

**Android kayıt yöntemleri**

| **Yöntem** |    **Temizleme gerekli mi?** |    **Benzeşim**    |    **Kilitle** | **Ayrıntılar**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[KCG](#byod)** | Hayır|    Evet |    Hayır | [Daha fazla bilgi](android-enroll.md)|
|**[DEM](#dem)**|    Hayır |Hayır |Hayır    |[Daha fazla bilgi](device-enrollment-program-enroll-ios.md)|
|**Android for Work**| Hayır | Evet | Hayır| [Daha fazla bilgi](android-enroll.md) |


## <a name="byod"></a>KCG
“Kendi cihazını getir” kullanıcıları Şirket Portalı uygulamasını yükler ve cihazlarını kaydeder. Bu, kullanıcıların şirket ağına bağlanarak etki alanına veya Azure Active Directory’ye katılmasına olanak tanır. Çoğu platformda, birçok COD senaryosu için KCG’yi etkinleştirmeniz gerekir. Kişisel iOS ve Android cihazlarının kaydedilmesini engelleyebilirsiniz. Yönergeler için bkz. [Cihaz türü kısıtlamaları ayarlama](enrollment-restrictions-set.md#set-device-type-restrictions).

## <a name="corporate-owned-devices"></a>Şirkete ait cihazlar
Şirkete ait cihazlar (COD) Azure Portal kullanılarak yönetilebilir. iOS cihazları, Apple tarafından sağlanan araçlar üzerinden doğrudan kaydedilebilir. Tüm cihaz türleri, cihaz kayıt yöneticisini kullanan bir yönetici ya da müdür tarafından kaydedilebilir. IMEI numaralı cihazlar da, COD senaryolarını etkinleştirmek için şirkete ait olarak tanımlanabilir ve etiketlenebilir.

### <a name="dem"></a>DEM
Cihaz kayıt yöneticisi (DEM), şirkete ait birden çok cihazı kaydetmek ve yönetmek için kullanılan özel bir kullanıcı hesabıdır. Yöneticiler Şirket Portalı’nı yükleyebilir ve kullanıcısı olmayan birçok cihazı kaydedebilir. [DEM](device-enrollment-manager-enroll.md) hakkında daha fazla bilgi edinin. ([Tabloya dön](#overview-of-device-enrollment-methods))

### <a name="dep"></a>DEP
Apple Aygıt Kayıt Programı (DEP) yönetimi, “havadan” ilke oluşturmanıza ve DEP ile satın alınan ve yönetilen iOS cihazlara dağıtmanıza olanak sağlar. Cihaz, kullanıcı cihazı ilk açtığında ve iOS Ayarlama Yardımcısı’nı çalıştırdığında kaydedilir. Bu yöntem **iOS Denetimli** modunu destekler ve bu mod şunlara olanak tanır:

  -    Kilitli kayıt
  -    Bilgi noktası modu ile diğer gelişmiş yapılandırmalar ve kısıtlamalar

iOS kaydı hakkında daha fazla bilgi için bkz:

- [iOS cihazlarının nasıl kaydedileceğini belirleme](enrollment-method-choose-ios.md)
- [Cihaz Kayıt Programı’nı kullanarak iOS cihazlarını kaydetme](device-enrollment-program-enroll-ios.md)
- [Yukarıdaki tabloya dön](#overview-of-device-enrollment-methods)

### <a name="usb-sa"></a>USB-SA
BT yöneticileri, şirkete ait tüm cihazları Kurulum Yardımcısı kullanarak el ile kaydetme işlemine hazırlamak için USB aracılığıyla Apple Configurator kullanır. BT yöneticisi bir kayıt profili oluşturur ve bunu Apple Configurator’a aktarır. Kullanıcılar cihazlarını aldığında, bu cihazları kaydetmek için Kurulum Yardımcısını çalıştırmaları istenir. Bu yöntem **iOS Denetimli** modunu destekler ve bu mod şunlara olanak tanır:
  -    Kilitli kayıt
  -    Bilgi noktası modu ile diğer gelişmiş yapılandırmalar ve kısıtlamalar

iOS kaydı hakkında daha fazla bilgi için bkz:

- [iOS cihazlarının nasıl kaydedileceğine karar verme](enrollment-method-choose-ios.md)
- [Configurator ve Kurulum Yardımcısı ile iOS cihazlarını kaydetme](apple-configurator-setup-assistant-enroll-ios.md)

### <a name="usb-direct"></a>USB-Direct
Doğrudan kayıt için yöneticinin bir kayıt ilkesi oluşturup bunu Apple Configurator’a aktararak her cihazı el ile kaydetmesi gerekir. USB bağlantılı, şirkete ait cihazlar fabrika sıfırlamasına gerek kalmadan doğrudan kaydedilir. Cihazlar, kullanıcısız cihaz olarak yönetilir. Bunlar kilitli veya denetimli değildir ve koşullu erişimi, jailbreak algılamasını ya da mobil uygulama yönetimini destekleyemez.

iOS kaydı hakkında daha fazla bilgi için bkz:

- [iOS cihazlarının nasıl kaydedileceğine karar verme](enrollment-method-choose-ios.md)
- [Configurator ve doğrudan kayıt ile iOS cihazlarını kaydetme](apple-configurator-direct-enroll-ios.md)

## <a name="mobile-device-management-with-exchange-activesync-and-intune"></a>Exchange ActiveSync ve Intune ile mobil cihaz yönetimi
Kaydedilmemiş ancak Exchange ActiveSync’e (EAS) bağlanan mobil cihazlar, EAS MDM ilkesi kullanılarak Intune tarafından yönetilebilir. Intune, şirket içinde veya bulutta barındırılan EAS ile iletişim kurmak için bir Exchange Connector kullanır. Çok yakında daha fazla bilgi sağlanacaktır.

## <a name="supported-device-platforms-and-browsers"></a>Desteklenen cihaz platformları ve tarayıcılar

Bkz. [Intune için desteklenen cihazlar ve tarayıcılar](https://docs.microsoft.com/intune-classic/get-started/supported-mobile-devices-and-computers)

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>MDM sertifikası süre sonunda mobil cihazı temizleme

Mobil cihazlar Intune hizmetiyle iletişim kurduğunda MDM sertifikası otomatik olarak yenilenir. Mobil cihazlar temizlendiğinde veya belirli bir süre boyunca Intune hizmetiyle iletişim kuramadığında, MDM sertifikası yenilenmez. MDM sertifikasının süre sonundan 180 gün sonra, cihaz Azure Portal’dan kaldırılır.
