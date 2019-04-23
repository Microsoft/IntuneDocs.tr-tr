---
title: Mobil Uygulama Yönetimi (MAM)
titleSuffix: Microsoft Intune
description: Intune Veri Ambarı API’sindeki varlık koleksiyonlarının Mobil Uygulama Yönetimi kategorisi için başvuru konusu.
keywords: Intune Veri Ambarı
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/09/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 084F11AD-F7BA-45A4-8424-45E6E4564930
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 456abbf849120675b6a7c108ca65c6f9967ae64a
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61511201"
---
# <a name="reference-for-mobile-app-management-mam-entities"></a>Mobil Uygulama Yönetimi (MAM) varlıkları için başvuru

**Mobil Uygulama Yönetimi** kategorisi, mobil uygulamalar için aşağıdaki gibi varlıklar içerir:

  -  Uygulamalar
  -  Örnek Sayısı
  -  İade etme durumu
  -  Sistem durumu
  -  İlke durumu
  -  Kayıt durumu
  -  Platform türleri

## <a name="mamapplication"></a>MamApplication

**MamApplication** varlığı, Mobil Uygulama Yönetimi (MAM) aracılığıyla yönetilen ancak kuruluşunuza kayıtlı olmayan iş kolu (LOB) uygulamalarını listeler.

| Özellik | Açıklama | Örnek |
|---------|------------|--------|
| mamApplicationKey |MAM uygulamasının benzersiz tanımlayıcısı. | 432 |
| mamApplicationName |MAM uygulamasının adı. |MAM uygulama örneği adı |
| mamApplicationId |MAM uygulamasının uygulama kimliği. | 123 |
| IsDeleted |Bu MAM uygulaması kaydının güncelleştirilip güncelleştirilmediğini gösterir. <br>True- MAM uygulamasının bu tablodaki güncelleştirilmiş alanları içeren yeni bir kaydı var. <br>False- bu MAM uygulaması için en son kayıt. |True/False |
| StartDateInclusiveUTC |Bu MAM uygulamasının veri ambarında oluşturulduğu tarih ve UTC diliminde saat. |23.11.2016 12:00:00 |
| DeletedDateUTC |IsDeleted değerinin True olarak değiştirildiği tarih ve UTC diliminde saat. |23.11.2016 12:00:00 |
| RowLastModifiedDateTimeUTC |Bu MAM uygulamasının veri ambarında son değiştirildiği tarih ve UTC diliminde saat. |23.11.2016 12:00:00 |


## <a name="mamapplicationinstance"></a>MamApplicationInstance

**MamApplicationInstance** varlığı, Mobil Uygulama Yönetimi (MAM) uygulamalarını kullanıcı ve cihaz başına tekil örnekler olarak listeler. Varlıkta listelenen tüm kullanıcılar ve cihazlar korunur. Örneğin, hepsine en az bir MAM İlkesi atanmıştır.


|          Özellik          |                                                                                                  Açıklama                                                                                                  |               Örnek                |
|----------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------|
|   ApplicationInstanceKey   |                                                               Veri ambarındaki MAM uygulaması örneğinin benzersiz tanımlayıcısı - vekil anahtar.                                                                |                 123                  |
|           UserId           |                                                                              Bu MAM uygulamasını yükleyen kullanıcının kullanıcı kimliği.                                                                              | b66bc706-ffff-7437-0340-032819502773 |
|   ApplicationInstanceId    |                                              MAM uygulaması örneğinin benzersiz tanımlayıcısı - ApplicationInstanceKey ile benzer ancak tanımlayıcı, bir doğal anahtardır.                                              | b66bc706-ffff-7437-0340-032819502773 |
| mamApplicationId | Bu Mam uygulaması örneğinin oluşturulduğu Mam uygulamasının uygulama kimliği.   | 23.11.2016 12:00:00   |
|     ApplicationVersion     |                                                                                     Bu MAM uygulamasının uygulama sürümü.                                                                                      |                  2                   |
|        CreatedDate         |                                                                 Bu MAM uygulama örneği kaydının oluşturulduğu tarih. Değer null olabilir.                                                                 |        23/11/2016 00:00:00        |
|          Platform          |                                                                          MAM uygulamasının yüklü olduğu cihazın platformu.                                                                           |                  2                   |
|      PlatformVersion       |                                                                      Bu MAM uygulamasının yüklü olduğu cihazın platform sürümü.                                                                       |                 2.2                  |
|         SdkVersion         |                                                                            Bu MAM uygulamasını sarmalayan MAM SDK sürümü.                                                                            |                 3,2                  |
| mamDeviceId | Cihazın kimliği ile MAM uygulama örneği ile ilişkili.   | 23.11.2016 12:00:00   |
| mamDeviceType | Cihaz türü ile MAM uygulama örneği ile ilişkili cihaz.   | 23.11.2016 12:00:00   |
| mamDeviceName | Cihazın adı MAM uygulama örneği ile ilişkilidir.   | 23.11.2016 12:00:00   |
|         IsDeleted          | Bu MAM uygulama örneği kaydının güncelleştirilip güncelleştirilmediğini gösterir. <br>True- bu MAM uygulaması örneğinin, bu tablodaki güncelleştirilmiş alanları içeren yeni bir kaydı var. <br>False- bu MAM uygulaması örneği için en son kayıt. |              True/False              |
|   StartDateInclusiveUtc    |                                                              Bu MAM uygulaması örneğinin, veri ambarında oluşturulduğu tarih ve UTC diliminde saat.                                                               |        23.11.2016 12:00:00        |
|       DeletedDateUtc       |                                                                             IsDeleted değerinin True olarak değiştirildiği tarih ve UTC diliminde saat.                                                                              |        23.11.2016 12:00:00        |
| RowLastModifiedDateTimeUtc |                                                           Bu MAM uygulaması örneğinin, veri ambarında son değiştirildiği tarih ve UTC diliminde saat.                                                            |        23.11.2016 12:00:00        |


## <a name="mamcheckin"></a>MamCheckin

**MamCheckin** varlığı, bir Mobil Uygulama Yönetimi (MAM) uygulama örneği Intune Hizmetine iade etme işlemi yaparken toplanan verileri temsil eder. 

> [!Note]  
> Bir uygulama örneği gün içinde birden çok kez iade etme işlemi yaparsa, veri ambarı bunu tek bir iade etme işlemi olarak depolar.

| Özellik | Açıklama | Örnek |
|---------|------------|--------|
| DateKey |MAM uygulamasının iade işleminin, veri ambarına kaydedildiği zamanı belirten tarih anahtarı. | 20160703 |
| ApplicationInstanceKey |Bu MAM uygulamasının iade işlemiyle ilişkili uygulama örneğinin anahtarı. | 123 |
| UserKey |Bu MAM uygulamasının iade işlemiyle ilişkili kullanıcı anahtarı. | 4323 |
| mamApplicationKey |Uygulama anahtarı, MAM uygulama iade ile ilişkili uygulama. | 432 |
| DeviceHealthKey |Bu MAM uygulamasının iade işlemiyle ilişkili DeviceHealth için anahtar. | 321 |
| PlatformKey |Bu MAM uygulamasının iade işlemiyle ilişkili cihaz platformunu temsil eder. |123 |
| EffectiveAppliedPolicyKey |İade etme işlemi yapan MAM uygulamasıyla ile ilişkili olarak uygulanan geçerli ilkeyi temsil eder. Uygulanan geçerli ilke, belirli bir uygulama ve kullanıcıyla ilişkili tüm ilkelerin birleştirilmesi sonucu elde edilir. | 322 |
| LastCheckInDate |Bu MAM uygulamasının en son iade etme işlemi yaptığı tarih ve saat. Değer null olabilir. |23.11.2016 12:00:00 |


## <a name="mamdevicehealth"></a>MamDeviceHealth

**MamDeviceHealth** varlığı, işletim sistemi kısıtlamaları kaldırılmış olsa bile Mobil Uygulama Yönetimi (MAM) ilkelerinin dağıtıldığı cihazları temsil eder.

| Özellik | Açıklama | Örnek |
|---------|------------|--------|
| DeviceHealthKey |Cihazın ve cihazla ilişkili sistem durumunun, veri ambarındaki benzersiz tanımlayıcısı - vekil anahtar. |123 |
| DeviceHealth |Cihazın ve cihazla ilişkili sistem durumunun benzersiz tanımlayıcısı - DeviceHealthKey ile benzer ancak tanımlayıcı, doğal bir anahtardır. |b66bc706-FFFF-7777-0340-032819502773 |
| DeviceHealthName |Cihazın durumunu temsil eder. <br>Kullanılamıyor - bu cihaz hakkında bilgi yok. <br>İyi durumda - cihazın işletim sistemi kısıtlamaları kaldırılmamış. <br>İyi durumda değil - cihazın işletim sistemi kısıtlamaları kaldırılmış. |Kullanılamıyor, İyi durumda, İyi durumda değil |
| RowLastModifiedDateTimeUtc |Bu MAM Cihaz Durumunun, veri ambarında son değiştirildiği tarih ve UTC diliminde saat. |23.11.2016 12:00:00 |

## <a name="mameffectivepolicy"></a>MamEffectivePolicy

**MamEffectivePolicy** varlığı, kuruluşunuzda Mobil Uygulama Yönetimi (MAM) uygulanan tüm geçerli ilkeleri listeler. Uygulanan geçerli ilke, belirli bir uygulama ve kullanıcıyla ilişkili tüm ilkelerin birleştirilmesi sonucu elde edilir.

| Özellik | Açıklama | Örnek |
|---------|------------|--------|
| EffectivePolicyKey |MAM geçerli ilkesinin, veri ambarındaki benzersiz tanımlayıcısı. |2 |
| RealPolicyKey |MAM ilkesinin, BT uzmanı tarafından yazılan benzersiz tanıtıcısı. |1. |
| RowCreatedDateTimeUtc |Bu geçerli ilkenin, veri ambarında oluşturulduğu tarih ve saat (UTC). |23.11.2016 12:00:00 |

## <a name="mamglobalapplication"></a>MamGlobalApplication

**MamGlobalApplication** varlığı, Mobil Uygulama Yönetimi (MAM) aracılığıyla yönetilen ancak kuruluşunuza kayıtlı olmayan mağaza uygulamaları listeler.


|          Özellik          |                                               Açıklama                                               |           Örnek            |
|----------------------------|---------------------------------------------------------------------------------------------------------|------------------------------|
|       ApplicationKey       |          Veri ambarındaki mağaza uygulamasının benzersiz tanıtıcısı - vekil anahtar olarak bilinir.          |             123              |
|       ApplicationId        | Mağaza uygulamasının benzersiz tanıtıcısı. Tanıtıcı, ApplicationKey ile benzer ancak doğal bir anahtardır.  | com.microsoft.skydrive.<ios> |
|      ApplicationName       |                                      MAM Genel Uygulama Adı.                                       |           Skydrive           |
| RowLastModifiedDateTimeUtc | Bu MAM Genel Uygulamasının, veri ambarında son değiştirildiği tarih ve saat (UTC). |    23.11.2016 12:00:00    |

## <a name="mamplatform"></a>MamPlatform

**MamPlatform** varlığı, Mobil Uygulama Yönetimi (MAM) uygulamasının yüklendiği platform adlarını ve türlerini listeler.


|          Özellik          |                                    Açıklama                                    |                         Örnek                         |
|----------------------------|-----------------------------------------------------------------------------------|---------------------------------------------------------|
|        PlatformKey         |     Veri ambarındaki platformun benzersiz tanımlayıcısı - vekil anahtar.      |                           123                           |
|          Platform          | Platformun benzersiz tanımlayıcısı; PlatformKey ile benzer ancak doğal bir anahtardır. |                           123                           |
|        PlatformName        |                                   Platform adı                                   | Kullanılamıyor <br>Yok. <br>Windows <br>IOS <br>Android. |
| RowLastModifiedDateTimeUtc | Bu platformun veri ambarında son değiştirildiği tarih ve UTC diliminde saat.  |                 23.11.2016 12:00:00                  |

