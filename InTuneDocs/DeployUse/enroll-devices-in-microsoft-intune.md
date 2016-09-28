---
title: "Cihazları kaydetme | Microsoft Intune"
description: "Mobil cihaz yönetimi (MDM), kaydı, cihazları yönetime getirmek ve kaynaklara erişim izni vermek için kullanır."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 09/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8fc415f7-0053-4aa5-8d2b-03202eca4b87
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e6b182ebab1691c62e69cabaf4689ac7395ab31a
ms.openlocfilehash: 0995d3ced978f5213fdb0e9905f508b64a1e5c09


---

# Cihazları yönetim için Intune’a kaydetme
Microsoft Intune ile mobil cihaz yönetimini (MDM) etkinleştirmek için Windows bilgisayarları da dahil olmak üzere cihazları kaydedebilirsiniz. Bu konuda, Intune yönetiminde mobil cihazları kaydetmek için farklı yollar açıklanmaktadır. Cihazların kaydedilme biçimi, cihaz türüne, sahipliğine ve gereken yönetim seviyesine bağlıdır. "Kendi cihazını getir" (KCG) kaydı, kullanıcıların kendi kişisel telefonlarını, tabletlerini veya bilgisayarlarını kaydetmesine izin verir. Şirkete ait cihaz (COD) kaydı uzaktan silme, paylaşılan cihazlar veya bir cihaz için kullanıcı benzeşimi gibi yönetim senaryolarına olanak sağlar.

Şirket içinde veya bulutta barındırılan [Exchange ActiveSync](#mobile-device-management-with-exchange-activesync-and-intune) kullanırsanız, kayda gerek kalmadan basit Intune yönetimini etkinleştirebilirsiniz. Windows bilgisayarları, [Intune istemci yazılımı](#manage-windows-pcs-with-intune) kullanılarak da yönetilebilir.

## Cihaz kayıt yöntemlerine genel bakış

Aşağıdaki tablo, desteklenen özellikleriyle birlikte Intune'un kayıt yöntemlerini gösterir. Bu özellikler şunları içerir:
- **Sil** - Cihazı fabrika ayarlarına sıfırlayarak tüm verileri kaldırma. [Cihazları devre dışı bırakma](retire-devices-from-microsoft-intune-management.md)
- **Benzeşim** - Cihazlarla kullanıcıları ilişkilendirir. Mobil uygulama yönetimi (MAM) ve şirket verilerine koşullu erişim için gereklidir. [Kullanıcı Benzeşimi](enroll-corporate-owned-ios-devices-in-microsoft-intune.md#using-company-portal-on-dep-or-apple-configurator-enrolled-devices)
- **Kilitle** Kullanıcıların cihazı yönetimden çıkarmasını engeller. iOS cihazlarında Kilitle eylemi için Denetimli mod gerekir. [Uzaktan kilitleme](retire-devices-from-microsoft-intune-management.md#block-access-a-device)

**iOS kayıt yöntemleri**

| **Yöntem** |  **Silme** |  **Benzeşim**    |   **Kilitle** | **Ayrıntılar** |
|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Hayır|    Evet |   Hayır | [daha fazla](get-ready-to-enroll-devices-in-microsoft-intune.md#set-up-device-management)|
|**[DEM](#dem)**|   Hayır |Hayır |Hayır  | [daha fazla](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|
|**[DEP](#dep)**|   Evet |   İsteğe bağlı |  İsteğe bağlı|[daha fazla](ios-device-enrollment-program-in-microsoft-intune.md)|
|**[USB-SA](#usb-sa)**| Evet |   İsteğe bağlı |  Hayır| [daha fazla](ios-setup-assistant-enrollment-in-microsoft-intune.md)|
|**[USB-Direct](#usb-direct)**| Hayır |    Hayır  | Hayır|[daha fazla](ios-direct-enrollment-in-microsoft-intune.md)|

**Windows ve Android kayıt yöntemleri**

| **Yöntem** |  **Silme** |  **Benzeşim**    |   **Kilitle** | **Ayrıntılar**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Hayır|    Evet |   Hayır | [daha fazla](get-ready-to-enroll-devices-in-microsoft-intune.md#set-up-device-management)|
|**[DEM](#dem)**|   Hayır |Hayır |Hayır  |[daha fazla](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|

Doğru yöntemi bulmanıza yardımcı olmak üzere bir dizi soru için bkz. [Cihazların nasıl kaydedileceği seçin](/intune/get-started/choose-how-to-enroll-devices1).

## BYOD
“Kendi cihazını getir” kullanıcıları Şirket Portalı uygulamasını yükler ve cihazlarını kaydeder. Bu, kullanıcıların etki alanına veya Azure Active Directory’ye katılarak şirket ağına bağlanmasına olanak tanır. KCG kaydını etkinleştirmek çoğu platformda birçok COD senaryosunun önkoşuludur. Bkz: [Cihaz kaydı için önkoşullar](prerequisites-for-enrollment.md). ([Tabloya dön](#overview-of-device-enrollment-methods))

## Şirkete ait cihazlar
Şirkete ait cihazlar (COD) Intune konsolu ile yönetilebilir. iOS cihazları, Apple tarafından sağlanan araçlar üzerinden doğrudan kaydedilebilir. Tüm cihaz türleri, cihaz kayıt yöneticisini kullanan bir yönetici ya da müdür tarafından kaydedilebilir. IMEI numaralı cihazlar da, COD senaryolarını etkinleştirmek için şirkete ait olarak tanımlanabilir ve etiketlenebilir.

[Şirkete ait cihazları kaydedin](manage-corporate-owned-devices.md)

### DEM
Cihaz kayıt yöneticisi şirkete ait birden çok cihazı kaydetmek ve yönetmek için kullanılan özel bir Intune hesabıdır. Yöneticiler Şirket Portalı’nı yükleyebilir ve kullanıcısı olmayan birçok cihazı kaydedebilir. [DEM](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) hakkında daha fazla bilgi edinin. ([Tabloya dön](#overview-of-device-enrollment-methods))

### DEP
Apple Aygıt Kayıt Programı (DEP) yönetimi, “havadan” ilke oluşturmanıza ve DEP ile satın alınan ve yönetilen iOS cihazlara dağıtmanıza olanak sağlar. Cihaz, kullanıcı cihazı ilk açtığında ve iOS Kurulum Yardımcısı’nı çalıştırdığında kaydedilir. Bu yöntem **iOS Denetimli** modunu destekler ve bu mod şunlara olanak tanır:
  - Kilitli kayıt
  - Koşullu erişim
  - Kaçış algılama
  - Mobil uygulama yönetimi

[DEP](ios-device-enrollment-program-in-microsoft-intune.md) hakkında daha fazla bilgi edinin. ([Tabloya dön](#overview-of-device-enrollment-methods))

### USB-SA
USB bağlantılı, Kurulum Yardımcısı kaydı. Yönetici Intune ilkesini oluşturur ve bunu Apple Configurator’a aktarır. USB bağlantılı, şirkete ait cihazlar Intune ilkesiyle hazırlanır. Yöneticinin her cihazı el ile kaydetmesi gerekir. Kullanıcılar cihazlarını alır ve Kurulum Yardımcısını çalıştırarak cihazlarını kaydederler. Bu yöntem **iOS Denetimli** modunu destekler ve bu mod şunlara olanak tanır:
  - Koşullu erişim
  - Kaçış algılama
  - Mobil uygulama yönetimi

[Apple Configurator ile Kurulum Yardımcısı kaydı](ios-setup-assistant-enrollment-in-microsoft-intune.md) hakkında daha fazla bilgi edinin. ([Tabloya dön](#overview-of-device-enrollment-methods))

### USB-Direct
Doğrudan kayıt. Yönetici Intune ilkesini oluşturur ve bunu Apple Configurator’a aktarır. USB bağlantılı, şirkete ait cihazlar fabrika sıfırlamasına gerek kalmadan doğrudan kaydedilir. Yöneticinin her cihazı el ile kaydetmesi gerekir. Cihazlar, kullanıcısız cihaz olarak yönetilir. Bunlar kilitli veya denetimli değildir ve koşullu erişimi, kaçış algılamasını, mobil uygulama yönetimini destekleyemez. [Apple Configurator ile doğrudan kayıt](ios-direct-enrollment-in-microsoft-intune.md) hakkında daha fazla bilgi edinin. ([Tabloya dön](#overview-of-device-enrollment-methods))

## Exchange ActiveSync ve Intune ile mobil cihaz yönetimi
Kaydedilmemiş ancak Exchange ActiveSync’e (EAS) bağlanan mobil cihazlar, EAS MDM ilkesi kullanılarak Intune tarafından yönetilebilir. Intune, şirket içinde veya bulutta barındırılan EAS ile iletişim kurmak için bir Exchange Connector kullanır.

[Exchange ActiveSync ve Intune ile mobil cihaz yönetimi](mobile-device-management-with-exchange-activesync-and-microsoft-intune.md)


## Intune ile Windows bilgisayarlarını yönetme  
Windows bilgisayarları, Intune istemci yazılımını kullanarak yönetmek için Microsoft Intune da kullanabilirsiniz. Intune istemcisiyle yönetilen bilgisayarlar aşağıdakileri yapabilir:

 - Yazılım ve donanım envanterlerini raporlama
 - Masaüstü uygulamaları yükleme (örneğin, .exe ve .msi dosyaları)
 - Güvenlik duvarı ayarları

Intune istemci yazılımıyla yönetilen bilgisayarlar, silinemez ve koşullu erişim, VPN ve Wi-Fi ayarları ya da sertifika ve e-posta yapılandırmalarının dağıtımı gibi birçok Intune yönetimi özelliğinden yararlanamaz.

[Intune ile Windows bilgisayarlarını yönetme](manage-windows-pcs-with-microsoft-intune.md)

##  Desteklenen cihaz platformları

Intune aşağıdaki cihaz platformlarını yönetebilir:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

## Sonraki adımlar
- [Cihaz kaydı için önkoşullar](prerequisites-for-enrollment.md)
- [Şirketin sahip olduğu cihazları yönetme](manage-corporate-owned-devices.md)
- [Desteklenen mobil cihazlar ve bilgisayarlar](../get-started/supported-mobile-devices-and-computers.md)



<!--HONumber=Sep16_HO3-->


