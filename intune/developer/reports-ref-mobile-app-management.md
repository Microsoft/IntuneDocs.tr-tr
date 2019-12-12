---
title: Mobil Uygulama Yönetimi (MAM)
titleSuffix: Microsoft Intune
description: Intune Veri Ambarı API’sindeki varlık koleksiyonlarının Mobil Uygulama Yönetimi kategorisi için başvuru konusu.
keywords: Intune Veri Ambarı
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/02/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 084F11AD-F7BA-45A4-8424-45E6E4564930
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: eb1833a6a54fe0a7f78958e653468921df952b4d
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72505705"
---
# <a name="reference-for-mobile-app-management-mam-entities"></a>Mobil Uygulama Yönetimi (MAM) varlıkları için başvuru

**Mobil Uygulama Yönetimi** kategorisi, mobil uygulamalar için aşağıdaki gibi varlıklar içerir:

- Apps
- Örnek Sayısı
- İade etme durumu
- Sistem durumu
- İlke durumu
- Kayıt durumu
- Platform türleri

## <a name="mamapplications"></a>MamApplications

**Mamappi** varlığı, kuruluşunuzda kayıt olmadan mobil uygulama YÖNETIMI (MAM) aracılığıyla yönetilen iş kolu (LOB) uygulamalarını listeler.

| Özellik | Description | Örnek |
|---------|------------|--------|
| mamApplicationKey |MAM uygulamasının benzersiz tanıtıcısı. | 432 |
| mamApplicationName |MAM uygulamasının adı. |MAM uygulaması örnek adı |
| mamApplicationId |MAM uygulamasının uygulama KIMLIĞI. | 123 |
| isDeleted |Bu MAM uygulaması kaydının güncelleştirilip güncelleştirilmediğini gösterir. <br>True- MAM uygulamasının bu tablodaki güncelleştirilmiş alanları içeren yeni bir kaydı var. <br>False- bu MAM uygulaması için en son kayıt. |Doğru/Yanlış |
| startDateInclusiveUTC |Bu MAM uygulamasının veri ambarında oluşturulduğu tarih ve UTC diliminde saat. |23.11.2016 12:00:00 |
| deletedDateUTC |IsDeleted değerinin True olarak değiştirildiği tarih ve UTC diliminde saat. |23.11.2016 12:00:00 |
| rowLastModifiedDateTimeUTC |Bu MAM uygulamasının veri ambarında son değiştirildiği tarih ve UTC diliminde saat. |23.11.2016 12:00:00 |


## <a name="mamapplicationinstances"></a>MamApplicationInstances

**Mamapplicationınstance** varlığı yönetilen mobil uygulama YÖNETIMI (MAM) uygulamalarını cihaz başına Kullanıcı başına tekil örnekler olarak listeler. Varlıkta listelenen tüm kullanıcılar ve cihazlar korunur. Örneğin, hepsine en az bir MAM İlkesi atanmıştır.


|          Özellik          |                                                                                                  Description                                                                                                  |               Örnek                |
|----------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------|
|   Applicationınstancekey ile   |                                                               Veri ambarındaki MAM uygulaması örneğinin benzersiz tanımlayıcısı - vekil anahtar.                                                                |                 123                  |
|           userId           |                                                                              Bu MAM uygulamasını yükleyen kullanıcının kullanıcı KIMLIĞI.                                                                              | b66bc706-ffff-7437-0340-032819502773 |
|   ApplicationInstanceId    |                                              MAM uygulaması örneğinin benzersiz tanımlayıcısı - ApplicationInstanceKey ile benzer ancak tanımlayıcı, bir doğal anahtardır.                                              | b66bc706-ffff-7437-0340-032819502773 |
| mamApplicationId | Bu mam uygulama örneğinin oluşturulduğu mam uygulamasının uygulama KIMLIĞI.   | 23.11.2016 12:00:00   |
|     applicationVersion     |                                                                                     Bu MAM uygulamasının uygulama sürümü.                                                                                      |                  2                   |
|        createdDate         |                                                                 Bu MAM uygulama örneği kaydının oluşturulduğu tarih. Değer null olabilir.                                                                 |        23.11.2016 12:00:00        |
|          Platform          |                                                                          MAM uygulamasının yüklü olduğu cihazın platformu.                                                                           |                  2                   |
|      platformVersion       |                                                                      Bu MAM uygulamasının yüklü olduğu cihazın platform sürümü.                                                                       |                 2.2                  |
|         SDK sürümü         |                                                                            Bu MAM uygulamasını sarmalayan MAM SDK sürümü.                                                                            |                 3.2                  |
| Mamdeviceıd | MAM uygulama örneğinin ilişkilendirildiği cihazın cihaz KIMLIĞI.   | 23.11.2016 12:00:00   |
| mamDeviceType | MAM uygulama örneğinin ilişkilendirildiği cihazın cihaz türü.   | 23.11.2016 12:00:00   |
| Mamaygıtadı | MAM uygulama örneğinin ilişkilendirildiği cihazın cihaz adı.   | 23.11.2016 12:00:00   |
|         isDeleted          | Bu MAM uygulama örneği kaydının güncelleştirilip güncelleştirilmediğini gösterir. <br>True- bu MAM uygulaması örneğinin, bu tablodaki güncelleştirilmiş alanları içeren yeni bir kaydı var. <br>False- bu MAM uygulaması örneği için en son kayıt. |              Doğru/Yanlış              |
|   StartDate, Iveutc    |                                                              Bu MAM uygulaması örneğinin, veri ambarında oluşturulduğu tarih ve UTC diliminde saat.                                                               |        23.11.2016 12:00:00        |
|       deletedDateUtc       |                                                                             IsDeleted değerinin True olarak değiştirildiği tarih ve UTC diliminde saat.                                                                              |        23.11.2016 12:00:00        |
| rowLastModifiedDateTimeUtc |                                                           Bu MAM uygulaması örneğinin, veri ambarında son değiştirildiği tarih ve UTC diliminde saat.                                                            |        23.11.2016 12:00:00        |


## <a name="mamcheckins"></a>MamCheckins

**Mamcheckin** varlığı, bir mobil uygulama YÖNETIMI (MAM) uygulama örneği Intune hizmetiyle iade edildiğinde toplanan verileri temsil eder. 

> [!Note]  
> Bir uygulama örneği gün içinde birden çok kez iade etme işlemi yaparsa, veri ambarı bunu tek bir iade etme işlemi olarak depolar.

| Özellik | Description | Örnek |
|---------|------------|--------|
| dateKey |MAM uygulamasının iade işleminin, veri ambarına kaydedildiği zamanı belirten tarih anahtarı. | 20160703 |
| Applicationınstancekey ile |Bu MAM uygulamasının iade işlemiyle ilişkili uygulama örneğinin anahtarı. | 123 |
| userKey |Bu MAM uygulamasının iade işlemiyle ilişkili kullanıcı anahtarı. | 4323 |
| mamApplicationKey |MAM uygulama denetimi ile ilişkili uygulamanın uygulama anahtarı. | 432 |
| Devicehealthkey ile |Bu MAM uygulamasının iade işlemiyle ilişkili DeviceHealth için anahtar. | 321 |
| ; platformKey ile |Bu MAM uygulamasının iade işlemiyle ilişkili cihaz platformunu temsil eder. |123 |
| effectiveAppliedPolicyKey |İade etme işlemi yapan MAM uygulamasıyla ile ilişkili olarak uygulanan geçerli ilkeyi temsil eder. Uygulanan geçerli ilke, belirli bir uygulama ve kullanıcıyla ilişkili tüm ilkelerin birleştirilmesi sonucu elde edilir. | 322 |
| Pastcheckındate |Bu MAM uygulamasının en son iade etme işlemi yaptığı tarih ve saat. Değer null olabilir. |23.11.2016 12:00:00 |


## <a name="mamdevicehealth"></a>mamDeviceHealth

**Mamdevicehealth** varlığı, jailbreak uygulanmış olsalar dahi, mobil uygulama YÖNETIMI (MAM) ilkelerinin dağıtıldığı cihazları temsil eder.

| Özellik | Description | Örnek |
|---------|------------|--------|
| Devicehealthkey ile |Cihazın ve cihazla ilişkili sistem durumunun, veri ambarındaki benzersiz tanımlayıcısı - vekil anahtar. |123 |
| deviceHealth |Cihazın ve cihazla ilişkili sistem durumunun benzersiz tanımlayıcısı - DeviceHealthKey ile benzer ancak tanımlayıcı, doğal bir anahtardır. |b66bc706-ffff-7777-0340-032819502773 |
| deviceHealthName |Cihazın durumunu temsil eder. <br>Kullanılamıyor - bu cihaz hakkında bilgi yok. <br>İyi durumda - cihazın işletim sistemi kısıtlamaları kaldırılmamış. <br>İyi durumda değil - cihazın işletim sistemi kısıtlamaları kaldırılmış. |Kullanılamıyor, İyi durumda, İyi durumda değil |
| rowLastModifiedDateTimeUtc |Bu MAM Cihaz Durumunun, veri ambarında son değiştirildiği tarih ve UTC diliminde saat. |23.11.2016 12:00:00 |

## <a name="mameffectivepolicies"></a>mamEffectivePolicies

**MamEffectivePolicy** varlığı, kuruluşunuzda uygulanan tüm mobil uygulama YÖNETIMI (MAM) etkin ilkelerini listeler. Uygulanan geçerli ilke, belirli bir uygulama ve kullanıcıyla ilişkili tüm ilkelerin birleştirilmesi sonucu elde edilir.

| Özellik | Description | Örnek |
|---------|------------|--------|
| Etkilenen Ilke anahtarı |MAM geçerli ilkesinin, veri ambarındaki benzersiz tanımlayıcısı. |2 |
| realPolicyKey |MAM ilkesinin, BT uzmanı tarafından yazılan benzersiz tanıtıcısı. |1 |
| rowCreatedDateTimeUtc |Bu geçerli ilkenin, veri ambarında oluşturulduğu tarih ve saat (UTC). |23.11.2016 12:00:00 |

## <a name="mamplatforms"></a>MamPlatforms

**Mamplatform** varlığı, mobil uygulama YÖNETIMI (MAM) uygulamasının yüklendiği platform adlarını ve türlerini listeler.


|          Özellik          |                                    Description                                    |                         Örnek                         |
|----------------------------|-----------------------------------------------------------------------------------|---------------------------------------------------------|
|        ; platformKey ile         |     Veri ambarındaki platformun benzersiz tanımlayıcısı - vekil anahtar.      |                           123                           |
|          Platform          | Platformun benzersiz tanımlayıcısı; PlatformKey ile benzer ancak doğal bir anahtardır. |                           123                           |
|        platformName        |                                   Platform adı                                   | Kullanılamıyor <br>Yok. <br>Windows <br>IOS <br>Android. |
| rowLastModifiedDateTimeUtc | Bu platformun veri ambarında son değiştirildiği tarih ve UTC diliminde saat.  |                 23.11.2016 12:00:00                  |

