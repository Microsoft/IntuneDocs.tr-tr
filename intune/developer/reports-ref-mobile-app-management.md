---
title: Mobil uygulama yönetimi (MAM)
titleSuffix: Microsoft Intune
description: Intune veri ambarı API 'sindeki varlık koleksiyonlarının mobil uygulama yönetimi kategorisi için başvuru konusu.
keywords: Intune veri ambarı
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/02/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 084F11AD-F7BA-45A4-8424-45E6E4564930
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: f06d2b4b61d522dced12e5d08cd1e854aefd9de8
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71939940"
---
# <a name="reference-for-mobile-app-management-mam-entities"></a>Mobil uygulama yönetimi (MAM) varlıkları için başvuru

**Mobil uygulama yönetimi** kategorisi, mobil uygulamalar için şu gibi varlıklar içerir:

- Gör
- Örnekler
- İade etme durumu
- Sistem durumu
- İlke durumu
- Kayıt durumu
- Platform türleri

## <a name="mamapplications"></a>mamApplications

**Mamappi** varlığı, kuruluşunuzda kayıt olmadan mobil uygulama YÖNETIMI (MAM) aracılığıyla yönetilen iş kolu (LOB) uygulamalarını listeler.

| Özellik | Açıklama | Örnek |
|---------|------------|--------|
| mamApplicationKey |MAM uygulamasının benzersiz tanıtıcısı. | 432 |
| mamApplicationName |MAM uygulamasının adı. |MAM uygulaması örnek adı |
| mamApplicationId |MAM uygulamasının uygulama KIMLIĞI. | 123 |
| IsDeleted |Bu MAM uygulaması kaydının güncelleştirilip güncelleştirilmediğini gösterir. <br>True-MAM uygulamasının bu tablodaki güncelleştirilmiş alanları içeren yeni bir kaydı vardır. <br>False-bu MAM uygulaması için en son kayıt. |Doğru/yanlış |
| StartDate, Iveutc |Bu MAM uygulamasının veri ambarında oluşturulduğu tarih ve saat (UTC). |11/23/2016 12:00:00 |
| DeletedDateUTC |IsDeleted değeri true olarak değiştiğinde UTC Tarih ve saati. |11/23/2016 12:00:00 |
| RowLastModifiedDateTimeUTC |Bu MAM uygulamasının veri ambarında son değiştirildiği tarih ve saat (UTC). |11/23/2016 12:00:00 |


## <a name="mamapplicationinstances"></a>mamApplicationInstances

**Mamapplicationınstance** varlığı yönetilen mobil uygulama YÖNETIMI (MAM) uygulamalarını cihaz başına Kullanıcı başına tekil örnekler olarak listeler. Varlıkta ile listelenen tüm kullanıcılar ve cihazlar, ' de olduğu gibi, en az bir MAM Ilkesi atanmış olarak korunur.


|          Özellik          |                                                                                                  Açıklama                                                                                                  |               Örnek                |
|----------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------|
|   Applicationınstancekey ile   |                                                               Veri ambarındaki MAM uygulaması örneğinin benzersiz tanıtıcısı-vekil anahtar.                                                                |                 123                  |
|           UserID           |                                                                              Bu MAM uygulamasını yükleyen kullanıcının kullanıcı KIMLIĞI.                                                                              | b66bc706-ffff-7437-0340-032819502773 |
|   ApplicationInstanceId    |                                              MAM uygulama örneğinin benzersiz tanıtıcısı-Applicationınstancekey ile ile benzerdir, ancak tanımlayıcı doğal bir anahtardır.                                              | b66bc706-ffff-7437-0340-032819502773 |
| mamApplicationId | Bu mam uygulama örneğinin oluşturulduğu mam uygulamasının uygulama KIMLIĞI.   | 11/23/2016 12:00:00   |
|     ApplicationVersion     |                                                                                     Bu MAM uygulamasının uygulama sürümü.                                                                                      |                  2                   |
|        CreatedDate         |                                                                 MAM uygulama örneğinin bu kaydının oluşturulduğu tarih. Değer null olabilir.                                                                 |        11/23/2016 12:00:00        |
|          platform          |                                                                          Bu MAM uygulamasının yüklü olduğu cihazın platformu.                                                                           |                  2                   |
|      PlatformVersion       |                                                                      Bu MAM uygulamasının yüklü olduğu cihazın platform sürümü.                                                                       |                 2,2                  |
|         SDK sürümü         |                                                                            Bu MAM uygulamasının sarmalanmış olduğu MAM SDK sürümü.                                                                            |                 3,2                  |
| Mamdeviceıd | MAM uygulama örneğinin ilişkilendirildiği cihazın cihaz KIMLIĞI.   | 11/23/2016 12:00:00   |
| mamDeviceType | MAM uygulama örneğinin ilişkilendirildiği cihazın cihaz türü.   | 11/23/2016 12:00:00   |
| Mamaygıtadı | MAM uygulama örneğinin ilişkilendirildiği cihazın cihaz adı.   | 11/23/2016 12:00:00   |
|         IsDeleted          | Bu MAM uygulama örneği kaydının güncelleştirilip güncelleştirilmediğini gösterir. <br>True-Bu MAM App örneğinin bu tablodaki güncelleştirilmiş alanları olan yeni bir kaydı vardır. <br>False-bu MAM uygulaması örneği için en son kayıt. |              Doğru/yanlış              |
|   StartDate, Iveutc    |                                                              Bu MAM uygulamasının veri ambarında oluşturulduğu tarih ve saat (UTC).                                                               |        11/23/2016 12:00:00        |
|       DeletedDateUtc       |                                                                             IsDeleted değeri true olarak değiştiğinde UTC Tarih ve saati.                                                                              |        11/23/2016 12:00:00        |
| RowLastModifiedDateTimeUtc |                                                           Bu MAM uygulamasının, veri ambarında son değiştirildiği tarih ve saat (UTC).                                                            |        11/23/2016 12:00:00        |


## <a name="mamcheckins"></a>mamCheckins

**Mamcheckin** varlığı, bir mobil uygulama YÖNETIMI (MAM) uygulama örneği Intune hizmetiyle iade edildiğinde toplanan verileri temsil eder. 

> [!Note]  
> Bir uygulama örneği günde birden çok kez denetlediğinde, veri ambarı kendisini tek iade olarak depolar.

| Özellik | Açıklama | Örnek |
|---------|------------|--------|
| DateKey |MAM uygulamasının iade etme işlemi veri ambarına kaydedildiğinde tarih anahtarı. | 20160703 |
| Applicationınstancekey ile |Bu MAM uygulamasının iade etme işlemiyle ilişkili uygulama örneğinin anahtarı. | 123 |
| UserKey |Bu MAM uygulamasının iade etme işlemiyle ilişkili Kullanıcı anahtarı. | 4323 |
| mamApplicationKey |MAM uygulama denetimi ile ilişkili uygulamanın uygulama anahtarı. | 432 |
| Devicehealthkey ile |Bu MAM uygulamasının iade etme işlemiyle ilişkili DeviceHealth anahtarı. | 321 |
| ; PlatformKey ile |Bu MAM uygulamasının iade etme işlemiyle ilişkili cihaz platformunu temsil eder. |123 |
| EffectiveAppliedPolicyKey |İade edilmiş MAM uygulamasıyla ilişkili geçerli uygulanan ilkeyi temsil eder. Geçerli bir uygulanan ilke, belirli bir uygulama ve kullanıcıyla ilgili tüm ilkelerin birleştirilmesiyle sonuçlanır. | 322 |
| Pastcheckındate |Bu MAM uygulamasının en son iade edilme tarihi ve saati. Değer null olabilir. |11/23/2016 12:00:00 |


## <a name="mamdevicehealth"></a>MamDeviceHealth

**Mamdevicehealth** varlığı, jailbreak uygulanmış olsalar dahi, mobil uygulama YÖNETIMI (MAM) ilkelerinin dağıtıldığı cihazları temsil eder.

| Özellik | Açıklama | Örnek |
|---------|------------|--------|
| Devicehealthkey ile |Cihazın benzersiz tanıtıcısı ve veri ambarındaki ilişkili sistem durumu-vekil anahtar. |123 |
| DeviceHealth |Cihazın ve onunla ilişkili sistem durumunun benzersiz tanımlayıcısı-DeviceHealthKey ile benzerdir, ancak tanımlayıcı doğal bir anahtardır. |b66bc706-ffff-7777-0340-032819502773 |
| DeviceHealthName |Cihazın durumunu temsil eder. <br>Kullanılamıyor-bu cihaz hakkında bilgi yok. <br>Sağlıklı-cihaz jailbreak uygulanmış değil. <br>Sağlıksız-cihaz jailbreak uygulanmış. |Sağlıklı sağlıksız sistem durumu yok |
| RowLastModifiedDateTimeUtc |Bu özel MAM Cihaz Durumu, veri ambarında son değiştirildiği tarih ve saat (UTC). |11/23/2016 12:00:00 |

## <a name="mameffectivepolicies"></a>mamEffectivePolicies

**MamEffectivePolicy** varlığı, kuruluşunuzda uygulanan tüm mobil uygulama YÖNETIMI (MAM) etkin ilkelerini listeler. Geçerli bir uygulanan ilke, belirli bir uygulama ve kullanıcıyla ilgili tüm ilkelerin birleştirilmesiyle sonuçlanır.

| Özellik | Açıklama | Örnek |
|---------|------------|--------|
| Etkilenen Ilke anahtarı |Veri ambarındaki MAM etkin ilkesinin benzersiz tanıtıcısı. |2 |
| RealPolicyKey |It Pro tarafından yazılan MAM ilkesinin benzersiz tanıtıcısı. |1\. |
| RowCreatedDateTimeUtc |Bu MAM etkin ilkenin veri ambarında oluşturulduğu tarih ve saat (UTC). |11/23/2016 12:00:00 |

## <a name="mamplatforms"></a>mamPlatforms

**Mamplatform** varlığı, mobil uygulama YÖNETIMI (MAM) uygulamasının yüklendiği platform adlarını ve türlerini listeler.


|          Özellik          |                                    Açıklama                                    |                         Örnek                         |
|----------------------------|-----------------------------------------------------------------------------------|---------------------------------------------------------|
|        ; PlatformKey ile         |     Veri ambarındaki platformun benzersiz tanıtıcısı-vekil anahtar.      |                           123                           |
|          platform          | Platformun benzersiz tanıtıcısı-PlatformKey ile benzerdir, ancak doğal bir anahtardır. |                           123                           |
|        PlatformName        |                                   Platform adı                                   | Kullanılamıyor <br>Yok. <br>Windows <br>Işlemine <br>Android. |
| RowLastModifiedDateTimeUtc | Bu platformun veri ambarında son değiştirildiği tarih ve saat (UTC).  |                 11/23/2016 12:00:00                  |

