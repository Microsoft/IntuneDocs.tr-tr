---
title: Apple’ın Intune’a gönderdiği veriler
titleSuffix: Microsoft Intune
description: Apple’ın Intune’a gönderdiği verilerin listesi.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/19/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: cf27fdb8-f408-425c-9a7c-146de1534425
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b316e305afa5aaae2c65c3aa062ff0343a845ffe
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71729721"
---
# <a name="data-apple-sends-to-intune"></a>Apple’ın Intune’a gönderdiği veriler

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Bir cihazda aşağıdaki Apple hizmetlerinden herhangi biri etkinleştirildiğinde Microsoft Intune, Apple ile kullanıcı ve cihaz bilgilerini paylaşmak için bağlantı kurar:

- [Apple Aygıt Kayıt Programı (DEP)](../enrollment/device-enrollment-program-enroll-ios.md)
- [Apple MDM anında Iletme sertifikası (APNs)](../enrollment/apple-mdm-push-certificate-get.md)
- [Apple School Manager (ASM)](https://docs.microsoft.com/schooldatasync/apple-school-manager-integration-with-intune-for-education-and-school-data-sync)
- [Apple Volume Purchase Program (VPP)](../apps/vpp-apps-ios.md)

Microsoft Intune’un bir bağlantı kurabilmesi için, önce Apple hizmetlerinin her biri için bir Apple hesabı oluşturmalısınız.

> [!NOTE]
> Microsoft ve Apple ilkesiyle tutarlı olan her nedenden dolayı hizmetimiz tarafından toplanan herhangi bir veriyi üçüncü taraflardan satmayacağız.

Aşağıdaki tablo, bir Apple cihazın Intune’a gönderdiği verileri listelemektedir. [Intune da Apple’a veri gönderir](data-intune-sends-to-apple.md). 

| Hizmet | İleti | Intune’a gönderilen veriler | Kullanıldığı yer |
|:---:|:---:|:---:| ---|
| [Indirin](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Kimlik doğrulaması | MessageType | İleti türü: kimlik doğrulaması. |
| [Indirin](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Kimlik doğrulaması | Konu | Cihazın dinleyeceği konu. |
| [Indirin](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Kimlik doğrulaması | MesUDID | Cihazın UDID’si. |
| [Indirin](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Kimlik doğrulaması | OSVersion | Cihazın işletim sistemi sürümü. |
| [Indirin](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Kimlik doğrulaması | BuildVersion | Cihazın derleme sürümü. |
| [Indirin](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Kimlik doğrulaması | ProductName | Cihazın ürün adı. |
| [Indirin](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Kimlik doğrulaması | SerialNumber | Cihazın seri numarası. |
| [Indirin](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Kimlik doğrulaması | IMEI | Cihazın Uluslararası Mobil İstasyon Ekipman Tanımlayıcısı. |
| [Indirin](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Kimlik doğrulaması | MEID | Cihazın Mobil Ekipman Tanımlayıcısı |
| [Indirin](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | TokenUpdate | Konu | Cihazın dinleyeceği konu. |
| [Indirin](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | TokenUpdate | UDID | Cihazın UDID’si. |
| [Indirin](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | TokenUpdate | Belirteç | Cihazın iletim belirteci. Sunucu, cihaza anında iletme bildirimleri gönderirken bu güncelleştirilmiş belirteci kullanmalıdır. |
| [Indirin](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | TokenUpdate | PushMagic | Anında iletme bildirimi iletisinde bulunması gereken sihirli dize.  |
| [Indirin](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | TokenUpdate | UnlockToken | Cihazın kilidini açmak için kullanılabilecek veri blobu. |
| [Indirin](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | TokenUpdate | AwaitingConfiguration | True olarak ayarlanırsa cihaz, Kurulum Yardımcısı’na devam etmeden önce bir DeviceConfigured MDM komutu bekler.  |
| [Indirin](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Kullanıma alma | MessageType | İleti türü: kullanıma alma. |
| [Indirin](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Kullanıma alma | Konu | Cihazın dinleyeceği konu. |
| [Indirin](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Kullanıma alma | UDID | Cihazın UDID’si |
| [Indirin](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | MDM Protokolü | Durum | Durum.  |
| [APNS](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | MDM Protokolü | UDID |Cihazın UDID’si.  |
| [Indirin](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | MDM Protokolü | CommandUUID | Bu yanıtın ait olduğu komutun UUID’si. |
| [Indirin](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | MDM Protokolü | ErrorChain | Ortaya çıkan hatalar zincirini temsil eden sözlükler dizisi.  |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Kayıt Programı belirteci | Seri numarası | Cihazın seri numarası. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Kayıt Programı belirteci | model | Cihazın model adı. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Kayıt Programı belirteci | Description | Cihazın açıklaması. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Kayıt Programı belirteci | Renk | Cihazın rengi. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Kayıt Programı belirteci | Varlık etiketi | Cihazın varlık etiketi. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Kayıt Programı belirteci | Profil durumu | Profil yükleme durumu. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Kayıt Programı belirteci | Profil UUID’si | Atanan profilin UUID’si. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Kayıt Programı belirteci | Profil atama zamanı | Bir profilin cihaza ne zaman atandığını gösteren ISO 8601 biçimli zaman damgası. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Kayıt Programı belirteci | Profil iletme zamanı | Bir profilin cihaza ne zaman iletildiğini gösteren ISO 8601 biçimli zaman damgası.|
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Kayıt Programı belirteci | Cihaz atanma tarihi | Cihazın Aygıt Kayıt Programı’na ne zaman kaydedildiğini gösteren ISO 8601 biçimli zaman damgası. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Kayıt Programı belirteci | Cihazı atayan | Cihazı atayan kişinin e-postası. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Kayıt Programı belirteci | İşletim sistemi | Cihazın işletim sistemi. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Kayıt Programı belirteci | Cihaz ailesi | Cihazın Apple ürün ailesi. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Belirteci | Apple Kullanıcı Kimliği | Apple tarafından oluşturulan bir kullanıcı kimliği. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Belirteci | uygulama açıklaması | Bir VPP uygulamasının açıklaması. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Belirteci | uygulama simgesi | Bir VPP uygulamasının Apple tarafından barındırılan simgesinin URL’si. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Belirteci | Uygulama kimliği | Apple Uygulama kimliği, diğer adıyla adamsId. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Belirteci | uygulama adı | Bir VPP uygulamasının adı. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Belirteci | assignedCount | Bir uygulamaya atanmış lisans sayısı. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Belirteci | availableCount | Bir uygulamaya atanmamış lisans sayısı. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Belirteci | bundleId | Bir uygulamanın bundleId kimliği. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Belirteci | Yaptırımlar | Bir uygulamanın telif hakkı bilgileri. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Belirteci | CountryCode | Bir VPP programının ülke kodu. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Belirteci | deviceAssignable | Yönetici bir uygulama için cihaz lisansı atayabiliyorsa Apple bunu true olarak döndürür. Aksi takdirde false döndürülür. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Belirteci | facilitatorMemberId | Bir VPP hesabı yöneticisinin üye kimliği.  |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Belirteci | türler | Bir uygulamanın türleri. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Belirteci | Intune UserId guid | Intune tarafından oluşturulan GUID. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Belirteci | isIrrevocable | Lisans iptal edilemiyorsa Apple bunu true olarak döndürür. İptal edilebiliyorsa false döndürülür. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Belirteci | Lisans kimliği | Apple tarafından belirli bir lisansı tanımlamak için oluşturulan kimlik. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Belirteci | Konum | Apple VPP yapılandırma verilerinde depolanan konum. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Belirteci | Managed AppleId UPN | Kullanıcı, yönetici ve yönetim üyesi için AppleID e-postası. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Belirteci | OrganizationId | Apple tarafından atanan kuruluş kimliği. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Belirteci | pricingParam | Bir uygulamanın Apple fiyatlandırma türü. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Belirteci | productType | Bir VPP uygulamasının ürün türü. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Belirteci | retiredCount | Bir uygulamanın devre dışı bırakılan lisans sayısı. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Belirteci | totalCount | Bir uygulama için satın alınmış toplam lisans sayısı. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Belirteci | url | Bir uygulamanın iTunes mağaza URL’si.|
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Belirteci | Kullanıcı Durumu | Apple VPP programlarındaki kullanıcı durumu. |


Microsoft Intune ile Apple hizmetlerini kullanmayı bırakmak ve verileri silmek için hem Microsoft Intune Apple belirtecini devre dışı bırakmanız hem de Apple hesabınızı silmeniz gerekir. Hesap yönetimini nasıl gerçekleştireceğinizi görmek için Apple hesabına bakın.


