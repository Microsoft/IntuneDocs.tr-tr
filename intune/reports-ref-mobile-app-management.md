---
title: Mobil Uygulama Yönetimi (MAM)
titleSuffix: Microsoft Intune
description: Intune Veri Ambarı API’sindeki varlık koleksiyonlarının Mobil Uygulama Yönetimi kategorisi için başvuru konusu.
keywords: Intune Veri Ambarı
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/09/2019
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
ms.openlocfilehash: c549a7063883f637ac7b5316e767b159d2328d0b
ms.sourcegitcommit: c3ac858bbadb63d248ed54069e48160d703bbaf2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/18/2019
ms.locfileid: "68313650"
---
# <a name="reference-for-mobile-app-management-mam-entities"></a>Mobil Uygulama Yönetimi (MAM) varlıkları için başvuru

**Mobil Uygulama Yönetimi** kategorisi, mobil uygulamalar için aşağıdaki gibi varlıklar içerir:

- Uygulamalar
- Örnek Sayısı
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
| IsDeleted |Bu MAM uygulaması kaydının güncelleştirilip güncelleştirilmediğini gösterir. <br>True- MAM uygulamasının bu tablodaki güncelleştirilmiş alanları içeren yeni bir kaydı var. <br>False- bu MAM uygulaması için en son kayıt. |True/False |
| startDateInclusiveUTC |Bu MAM uygulamasının veri ambarında oluşturulduğu tarih ve UTC diliminde saat. |23.11.2016 12:00:00 |
| DeletedDateUTC |IsDeleted değerinin True olarak değiştirildiği tarih ve UTC diliminde saat. |23.11.2016 12:00:00 |
| RowLastModifiedDateTimeUTC |Bu MAM uygulamasının veri ambarında son değiştirildiği tarih ve UTC diliminde saat. |23.11.2016 12:00:00 |


## <a name="mamapplicationinstances"></a>mamApplicationInstances

**Mamapplicationınstance** varlığı yönetilen mobil uygulama YÖNETIMI (MAM) uygulamalarını cihaz başına Kullanıcı başına tekil örnekler olarak listeler. Varlıkta listelenen tüm kullanıcılar ve cihazlar korunur. Örneğin, hepsine en az bir MAM İlkesi atanmıştır.


|          Özellik          |                                                                                                  Açıklama                                                                                                  |               Örnek                |
|----------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------|
|   Applicationınstancekey ile   |                                                               Veri ambarındaki MAM uygulaması örneğinin benzersiz tanımlayıcısı - vekil anahtar.                                                                |                 123                  |
|           UserID           |                                                                              Bu MAM uygulamasını yükleyen kullanıcının kullanıcı KIMLIĞI.                                                                              | b66bc706-ffff-7437-0340-032819502773 |
|   ApplicationInstanceId    |                                              MAM uygulaması örneğinin benzersiz tanımlayıcısı - ApplicationInstanceKey ile benzer ancak tanımlayıcı, bir doğal anahtardır.                                              | b66bc706-ffff-7437-0340-032819502773 |
| mamApplicationId | Bu mam uygulama örneğinin oluşturulduğu mam uygulamasının uygulama KIMLIĞI.   | 23.11.2016 12:00:00   |
|     ApplicationVersion     |                                                                                     Bu MAM uygulamasının uygulama sürümü.                                                                                      |                  2                   |
|        CreatedDate         |                                                                 Bu MAM uygulama örneği kaydının oluşturulduğu tarih. Değer null olabilir.                                                                 |        23.11.2016 12:00:00        |
|          Platform          |                                                                          MAM uygulamasının yüklü olduğu cihazın platformu.                                                                           |                  2                   |
|      PlatformVersion       |                                                                      Bu MAM uygulamasının yüklü olduğu cihazın platform sürümü.                                                                       |                 2.2                  |
|         SDK sürümü         |                                                                            Bu MAM uygulamasını sarmalayan MAM SDK sürümü.                                                                            |                 3,2                  |
| Mamdeviceıd | MAM uygulama örneğinin ilişkilendirildiği cihazın cihaz KIMLIĞI.   | 23.11.2016 12:00:00   |
| mamDeviceType | MAM uygulama örneğinin ilişkilendirildiği cihazın cihaz türü.   | 23.11.2016 12:00:00   |
| Mamaygıtadı | MAM uygulama örneğinin ilişkilendirildiği cihazın cihaz adı.   | 23.11.2016 12:00:00   |
|         IsDeleted          | Bu MAM uygulama örneği kaydının güncelleştirilip güncelleştirilmediğini gösterir. <br>True- bu MAM uygulaması örneğinin, bu tablodaki güncelleştirilmiş alanları içeren yeni bir kaydı var. <br>False- bu MAM uygulaması örneği için en son kayıt. |              True/False              |
|   StartDate, Iveutc    |                                                              Bu MAM uygulaması örneğinin, veri ambarında oluşturulduğu tarih ve UTC diliminde saat.                                                               |        23.11.2016 12:00:00        |
|       DeletedDateUtc       |                                                                             IsDeleted değerinin True olarak değiştirildiği tarih ve UTC diliminde saat.                                                                              |        23.11.2016 12:00:00        |
| RowLastModifiedDateTimeUtc |                                                           Bu MAM uygulaması örneğinin, veri ambarında son değiştirildiği tarih ve UTC diliminde saat.                                                            |        23.11.2016 12:00:00        |


## <a name="mamcheckins"></a>mamCheckins

**Mamcheckin** varlığı, bir mobil uygulama YÖNETIMI (MAM) uygulama örneği Intune hizmetiyle iade edildiğinde toplanan verileri temsil eder. 

> [!Note]  
> Bir uygulama örneği gün içinde birden çok kez iade etme işlemi yaparsa, veri ambarı bunu tek bir iade etme işlemi olarak depolar.

| Özellik | Açıklama | Örnek |
|---------|------------|--------|
| dateKey |MAM uygulamasının iade işleminin, veri ambarına kaydedildiği zamanı belirten tarih anahtarı. | 20160703 |
| Applicationınstancekey ile |Bu MAM uygulamasının iade işlemiyle ilişkili uygulama örneğinin anahtarı. | 123 |
| userKey |Bu MAM uygulamasının iade işlemiyle ilişkili kullanıcı anahtarı. | 4323 |
| mamApplicationKey |MAM uygulama denetimi ile ilişkili uygulamanın uygulama anahtarı. | 432 |
| Devicehealthkey ile |Bu MAM uygulamasının iade işlemiyle ilişkili DeviceHealth için anahtar. | 321 |
| ; PlatformKey ile |Bu MAM uygulamasının iade işlemiyle ilişkili cihaz platformunu temsil eder. |123 |
| EffectiveAppliedPolicyKey |İade etme işlemi yapan MAM uygulamasıyla ile ilişkili olarak uygulanan geçerli ilkeyi temsil eder. Uygulanan geçerli ilke, belirli bir uygulama ve kullanıcıyla ilişkili tüm ilkelerin birleştirilmesi sonucu elde edilir. | 322 |
| Pastcheckındate |Bu MAM uygulamasının en son iade etme işlemi yaptığı tarih ve saat. Değer null olabilir. |23.11.2016 12:00:00 |


## <a name="mamdevicehealth"></a>MamDeviceHealth

**Mamdevicehealth** varlığı, jailbreak uygulanmış olsalar dahi, mobil uygulama YÖNETIMI (MAM) ilkelerinin dağıtıldığı cihazları temsil eder.

| Özellik | Açıklama | Örnek |
|---------|------------|--------|
| Devicehealthkey ile |Cihazın ve cihazla ilişkili sistem durumunun, veri ambarındaki benzersiz tanımlayıcısı - vekil anahtar. |123 |
| deviceHealth |Cihazın ve cihazla ilişkili sistem durumunun benzersiz tanımlayıcısı - DeviceHealthKey ile benzer ancak tanımlayıcı, doğal bir anahtardır. |b66bc706-ffff-7777-0340-032819502773 |
| DeviceHealthName |Cihazın durumunu temsil eder. <br>Kullanılamıyor - bu cihaz hakkında bilgi yok. <br>İyi durumda - cihazın işletim sistemi kısıtlamaları kaldırılmamış. <br>İyi durumda değil - cihazın işletim sistemi kısıtlamaları kaldırılmış. |Kullanılamıyor, İyi durumda, İyi durumda değil |
| RowLastModifiedDateTimeUtc |Bu MAM Cihaz Durumunun, veri ambarında son değiştirildiği tarih ve UTC diliminde saat. |23.11.2016 12:00:00 |

## <a name="mameffectivepolicies"></a>mamEffectivePolicies

**MamEffectivePolicy** varlığı, kuruluşunuzda uygulanan tüm mobil uygulama YÖNETIMI (MAM) etkin ilkelerini listeler. Uygulanan geçerli ilke, belirli bir uygulama ve kullanıcıyla ilişkili tüm ilkelerin birleştirilmesi sonucu elde edilir.

| Özellik | Açıklama | Örnek |
|---------|------------|--------|
| Etkilenen Ilke anahtarı |MAM geçerli ilkesinin, veri ambarındaki benzersiz tanımlayıcısı. |2 |
| RealPolicyKey |MAM ilkesinin, BT uzmanı tarafından yazılan benzersiz tanıtıcısı. |1\. |
| RowCreatedDateTimeUtc |Bu geçerli ilkenin, veri ambarında oluşturulduğu tarih ve saat (UTC). |23.11.2016 12:00:00 |

## <a name="mamplatforms"></a>mamPlatforms

**Mamplatform** varlığı, mobil uygulama YÖNETIMI (MAM) uygulamasının yüklendiği platform adlarını ve türlerini listeler.


|          Özellik          |                                    Açıklama                                    |                         Örnek                         |
|----------------------------|-----------------------------------------------------------------------------------|---------------------------------------------------------|
|        ; PlatformKey ile         |     Veri ambarındaki platformun benzersiz tanımlayıcısı - vekil anahtar.      |                           123                           |
|          Platform          | Platformun benzersiz tanımlayıcısı; PlatformKey ile benzer ancak doğal bir anahtardır. |                           123                           |
|        PlatformName        |                                   Platform adı                                   | Kullanılamıyor <br>Yok. <br>Windows <br>IOS <br>Android. |
| RowLastModifiedDateTimeUtc | Bu platformun veri ambarında son değiştirildiği tarih ve UTC diliminde saat.  |                 23.11.2016 12:00:00                  |

