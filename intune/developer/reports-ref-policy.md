---
title: Ilke varlıkları için başvuru
titleSuffix: Microsoft Intune
description: Intune veri ambarı API 'sindeki varlık koleksiyonlarının Ilke kategorisi için başvuru konusu.
keywords: Intune veri ambarı
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/02/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: a812234588081443c2ee8ea8d42b161c22ad4232
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71940335"
---
# <a name="reference-for-policy-entities"></a>Ilke varlıkları için başvuru

**İlkeler** kategorisi, mobil cihazlar için şu gibi bilgileri izleyen varlıklar içerir:

- Cihaz yapılandırma profillerinin, uygulama yapılandırma profillerinin ve uyumluluk ilkelerinin envanteri  
- Başarılı, beklemede, başarısız veya hata durumundaki cihaz sayısı/gün  
- Başarılı, beklemede, başarısız veya hata durumundaki Kullanıcı sayısı/gün  
- Başarılı, beklemede, başarısız veya hata durumundaki cihazların toplam sayısı  

## <a name="policies"></a>ilkeler

**İlke** varlığı cihaz yapılandırma profillerini, uygulama yapılandırma profillerini ve uyumluluk ilkelerini listeler. Mobil cihaz yönetimi (MDM) ile ilkeleri kuruluşunuzdaki bir gruba atayabilirsiniz.

| Özellik  | Açıklama | Örnek |
|---------|------------|--------|
| PolicyKey |Veri ambarındaki ilkeyi temsil eden benzersiz anahtar. |123 |
| PolicyId |Ilkenin veri ambarındaki benzersiz tanımlayıcısı. |b66bc706-ffff-7437-0340-032819502773 |
| PolicyName |Ilkenin adı. |"Windows 10 temeli" |
| PolicyVersion |Ilke sürümü. İlke düzenlendiğinde veya değiştirildiğinde, daha yeni bir sürüm oluşturulur. |1, 2, 3 |
| IsDeleted |Ilke kaydının güncelleştirilip güncelleştirilmediğini gösterir.  <br>True-ilkenin güncelleştirilmiş alanları olan yeni bir kaydı vardır. <br>False-ilke için en son kayıt. |Doğru/yanlış |
| StartDate, Iveutc |İlkenin veri ambarında oluşturulduğu tarih ve saat (UTC). |11/23/2016 12:00:00 |
| DeletedDateUTC |IsDeleted değeri true olarak değiştiğinde UTC Tarih ve saati. |11/23/2016 12:00:00 |
| RowLastModifiedDateTimeUTC |İlkenin veri ambarında son değiştirildiği tarih ve saat (UTC). |11/23/2016 12:00:00 |

## <a name="policytypes"></a>policyTypes

**PolicyType** varlığı cihaz yapılandırma profillerinin, uygulama yapılandırma profillerinin ve uyumluluk ilkelerinin türlerini listeler. Mobil cihaz yönetimi (MDM) ile ilkeleri kuruluşunuzdaki bir gruba atayabilirsiniz.

| Özellik  | Açıklama | Örnek |
|---------|------------|--------|
| Policytypeıd |Kaynak sistemdeki ilkenin benzersiz tanıtıcısı. |123 |
| PolicyTypeKey |İlkenin veri ambarındaki benzersiz tanımlayıcısı. |1\. |
| PolicyTypeName |İlke türünün adı. |Windows 10 uyumluluk ilkesi. |

## <a name="device-configuration"></a>Cihaz yapılandırması

**Deviceconfigurationprofiledeviceactivity** varlığı, başarılı, beklemede, başarısız veya hata durumundaki **cihazların** günlük sayısını listeler. Numara, varlığa atanan cihaz yapılandırma profillerini yansıtır. Örneğin, bir **cihaz** atanan tüm ilkeleri için başarılı durumdaysa, bu gün için başarılı olan sayacı artırır. Bir cihaza atanmış iki profil varsa, biri başarılı durumunda ve diğeri bir hata durumunda ise, varlık başarılı sayacı artırır ve cihazı hata durumuna yerleştirir. Varlık, son 30 gün içindeki belirli bir gün için kaç cihazın hangi durumda olduğunu listeler.

| Özellik  | Açıklama | Örnek |
|---------|------------|--------|
| DateKey |Cihaz yapılandırma profilinin iade etme işlemi veri ambarına kaydedildiğinde tarih anahtarı. |20160703 |
| bekleniyor |Bekleme durumundaki benzersiz cihazların sayısı. |123 |
| Baarı |Başarı durumundaki benzersiz cihazların sayısı. |12 |
| error |Hata durumundaki benzersiz cihazların sayısı. |10 |
| başarısız |Başarısız durumundaki benzersiz cihazların sayısı. |2 |

**Deviceconfigurationprofileuseractivity** varlığı, başarılı, beklemede, başarısız veya hata durumundaki **kullanıcıların** günlük sayısını listeler. Numara, varlığa atanan cihaz yapılandırma profillerini yansıtır. Örneğin, bir **Kullanıcı** atanmış tüm ilkeleri için başarılı durumdaysa, başarılı olan sayacı o gün için bir tane yukarı gider. Bir kullanıcının kendisine atanmış iki profili varsa, biri başarılı durumunda ve diğeri bir hata durumunda ise, hata durumundaki Kullanıcı sayılır.  **Deviceconfigurationprofileuseractivity** varlığı, son 30 gün içindeki belirli bir gün için kaç kullanıcının hangi durumda olduğunu listeler.

| Özellik  | Açıklama | Örnek |
|---------|------------|--------|
| DateKey |Cihaz yapılandırma profilinin iade etme işlemi veri ambarına kaydedildiğinde tarih anahtarı. |20160703 |
| bekleniyor |Bekleme durumundaki benzersiz kullanıcıların sayısı. |123 |
| Baarı |Başarılı durumundaki benzersiz kullanıcı sayısı. |12 |
| error |Hata durumundaki benzersiz kullanıcı sayısı. |10 |
| başarısız |Başarısız durumundaki benzersiz kullanıcıların sayısı. |2 |

## <a name="policytypeactivities"></a>policyTypeActivities

**Policytypeactivity** varlığı, başarılı, beklemede, başarısız veya hata durumundaki toplam cihaz sayısını listeler. Bu durumları bir cihaz yapılandırma profili, uygulama yapılandırma profili veya günlük uyumluluk ilkesi açısından listeler.

| Özellik  | Açıklama | Örnek |
|---------|------------|--------|
| DateKey |Tarih anahtarı, cihaz yapılandırma profili iade etme işlemi veri ambarına kaydedildiğinde. |20160703 |
| PolicyKey |policyKey, policyName 'i almak için ilkeyle eklenebilir. |Windows 10 temeli |
| PolicyTypeKey |İlke anahtarı türü, ilke türü adını almak için Ilke türü ile birlikte katılabilir. |Windows10 uyumluluk Ilkesi |
| bekleniyor |Bekleme durumundaki benzersiz cihazların sayısı. |123 |
| Baarı |Başarı durumundaki benzersiz cihazların sayısı. |12 |
| error |Hata durumundaki benzersiz cihazların sayısı. |10 |
| başarısız |Başarısız durumundaki benzersiz cihazların sayısı. |2 |

## <a name="compliance-policy"></a>Uyumluluk Ilkesi

Uyumluluk Ilkesi API 'SI başvurusu cihazlara atanan uyumluluk ilkeleriyle ilgili durum bilgilerini sağlayan varlıkları içerir.

### <a name="compliancepolicystatusdeviceactivities"></a>Karmaşıancepolicystatusdeviceactivities

Aşağıdaki tabloda, uyumluluk ilkelerinin cihazlara atama durumu özetlenmektedir. Her uyumluluk durumunda bulunan cihaz sayısını listeler.


|Özellik     |Açıklama  |Örnek  |
|---------|---------|---------|
|DateKey  |Uyumluluk ilkesi için özetin oluşturulduğu tarih anahtarı.|20161204 |
|Bilinmeyen  |Çevrimdışı olan veya Intune ya da Azure AD ile ilgili diğer nedenlerden dolayı iletişim kuramayan cihazların sayısı. |5|
|Notapplıcable      |Yönetici tarafından hedeflenen cihaz uyumluluk ilkelerinin geçerli olmadığı cihaz sayısı.|201 |
|Uyumluluk      |Yönetici tarafından hedeflenen bir veya daha fazla cihaz Uyumluluk ilkesini başarıyla uygulayan cihaz sayısı. |4083 |
|Yetkisizkullanımsüresinde      |Uyumlu olmayan ancak yönetici tarafından tanımlanan yetkisiz kullanım döneminde olan cihazların sayısı. |57|
|Izde      |Yönetici tarafından hedeflenen bir veya daha fazla cihaz Uyumluluk ilkesini veya kullanıcının yönetici tarafından hedeflenen ilkelerle uyumlu olmadığı bir veya daha fazla cihaz uyumluluk ilkesi uygulayamayan cihaz sayısı.|43 |
|error      |Intune veya Azure AD ile iletişim kuramayan cihazların sayısı ve bir hata iletisi döndürdü. |3|

### <a name="compliancepolicystatusdeviceperpolicyactivities"></a>Karmaşık Policystatusdeviceperpolicyacmize 

Aşağıdaki tablo, uyumluluk ilkelerinin atama durumunu ilke başına ve ilke başına tür temelinde cihazlara özetler. Her bir uyumluluk ilkesinin her bir uyumluluk durumunda bulunan cihaz sayısını listeler.



|Özellik  |Açıklama  |Örnek  |
|---------|---------|---------|
|DateKey  |Uyumluluk ilkesi için özetin oluşturulduğu tarih anahtarı.|20161219|
|PolicyKey     |Özetin oluşturulduğu uyumluluk ilkesi için anahtar. |10178 |
|PolicyPlatformKey      |Özetin oluşturulduğu uyumluluk ilkesinin platform türü için anahtar.|5|
|Bilinmeyen     |Çevrimdışı olan veya Intune ya da Azure AD ile ilgili diğer nedenlerden dolayı iletişim kuramayan cihazların sayısı.|13|
|Notapplıcable     |Yönetici tarafından hedeflenen cihaz uyumluluk ilkelerinin geçerli olmadığı cihaz sayısı.|3|
|Uyumluluk      |Yönetici tarafından hedeflenen bir veya daha fazla cihaz Uyumluluk ilkesini başarıyla uygulayan cihaz sayısı. |45|
|Yetkisizkullanımsüresinde      |Uyumlu olmayan ancak yönetici tarafından tanımlanan yetkisiz kullanım döneminde olan cihazların sayısı. |3|
|Izde      |Yönetici tarafından hedeflenen bir veya daha fazla cihaz Uyumluluk ilkesini veya kullanıcının yönetici tarafından hedeflenen ilkelerle uyumlu olmadığı bir veya daha fazla cihaz uyumluluk ilkesi uygulayamayan cihaz sayısı.|7|
|error      |Intune veya Azure AD ile iletişim kuramayan cihazların sayısı ve bir hata iletisi döndürdü. |3|

### <a name="policyplatformtypes"></a>PolicyPlatformTypes

Aşağıdaki tablo, atanan tüm ilkelerin platform türlerini içerir. Hiçbir cihaza hiç atanmamış ilke platformu türleri bu tabloda yok.


|Özellik  |Açıklama  |Örnek  |
|---------|---------|---------|
|PolicyPlatformTypeKey      |İlke platform türü için benzersiz anahtar. |20170519 |
|Policyplatformtypeıd      |İlke platform türü için benzersiz tanımlayıcı.|1\.|
|PolicyPlatformTypeName      |İlke platformu türünün adı.|AndroidForWork |

### <a name="policydeviceactivities"></a>policyDeviceActivities

Aşağıdaki tabloda, başarılı, beklemede, başarısız veya hata durumundaki cihaz sayısı günlük olarak listelenmektedir. Bu sayı, Ilke türü profilleri başına verileri yansıtır. Örneğin, bir cihaz atanan tüm ilkeleri için başarılı durumdaysa, bu gün için başarılı olan sayacı artırır. Bir cihaza atanmış iki profil varsa, biri başarılı durumunda ve diğeri bir hata durumunda ise, varlık başarılı sayacı artırır ve cihazı hata durumuna yerleştirir. PolicyDeviceActivity varlığı, son 30 gün içindeki belirli bir gün için kaç cihazın hangi durumda olduğunu listeler.

|Özellik  |Açıklama  |Örnek  |
|---------|---------|---------|
|DateKey|Cihaz yapılandırma profilinin iade etme işlemi veri ambarına kaydedildiğinde tarih anahtarı.|20160703|
|bekleniyor|Bekleme durumundaki benzersiz cihazların sayısı.|123|
|Baarı|Başarı durumundaki benzersiz cihazların sayısı.|12|
|PolicyKey|policyKey, policyName 'i almak için ilkeyle eklenebilir.|Windows 10 temeli|
|error|Hata durumundaki benzersiz cihazların sayısı.|10|
|başarısız|Başarısız durumundaki benzersiz cihazların sayısı.|2|

### <a name="policyuseractivities"></a>policyUserActivities

Aşağıdaki tabloda, başarılı, beklemede, başarısız veya hata durumundaki Kullanıcı sayısı günlük olarak listelenmektedir. Bu sayı, Ilke türü profilleri başına verileri yansıtır. Örneğin, bir kullanıcı atanmış tüm ilkeleri için başarılı durumdaysa, başarılı olan sayacı o gün için bir tane yukarı gider. Bir kullanıcının kendisine atanmış iki profili varsa, biri başarılı durumunda ve diğeri bir hata durumunda ise, hata durumundaki Kullanıcı sayılır. PolicyUserActivity varlığı, son 30 gün içindeki belirli bir gün için kaç kullanıcının hangi durumda olduğunu listeler.


| Özellik  |                                         Açıklama                                         |       Örnek       |
|-----------|---------------------------------------------------------------------------------------------|---------------------|
|  DateKey  | Cihaz yapılandırma profilinin iade etme işlemi veri ambarına kaydedildiğinde tarih anahtarı. |      20160703       |
|  bekleniyor  |                         Bekleme durumundaki benzersiz cihazların sayısı.                          |         123         |
| Baarı |                         Başarı durumundaki benzersiz cihazların sayısı.                          |         12          |
| PolicyKey |                 policyKey, policyName 'i almak için ilkeyle eklenebilir.                 | Windows 10 temeli |
|   error   |                          Hata durumundaki benzersiz cihazların sayısı.                           |         10          |

