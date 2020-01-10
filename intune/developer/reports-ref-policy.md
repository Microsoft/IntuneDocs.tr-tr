---
title: İlke varlıkları için başvuru
titleSuffix: Microsoft Intune
description: Intune Veri Ambarı API’sindeki varlık koleksiyonlarının İlke kategorisi için başvuru konusu.
keywords: Intune Veri Ambarı
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/03/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1fe4fabc86e7be647fa161d68fe8a4fe35e9eb6b
ms.sourcegitcommit: 8d7406b75ef0d75cc2ed03b1a5e5f74ff10b98c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/03/2020
ms.locfileid: "75654133"
---
# <a name="reference-for-policy-entities"></a>İlke varlıkları için başvuru

**İlkeler** kategorisi, mobil cihazlar için şu gibi bilgileri izleyen varlıklar içerir:

- Cihaz yapılandırma profilleri, uygulama yapılandırma profilleri ve uyumluluk ilkelerinin dökümü  
- Başarılı, beklemede, başarısız veya hata durumundaki cihazların günlük sayısı  
- Başarılı, beklemede, başarısız veya hata durumundaki kullanıcıların günlük sayısı  
- Başarılı, beklemede, başarısız veya hata durumundaki cihazların toplam sayısı  

## <a name="policies"></a>ilkeler

**İlke** varlığı cihaz yapılandırma profillerini, uygulama yapılandırma profillerini ve uyumluluk ilkelerini listeler. Kuruluşunuzda bir gruba Mobil Cihaz Yönetimi (MDM) ilkeleri atayabilirsiniz.

| Özellik  | Description | Örnek |
|---------|------------|--------|
| policyKey |Veri ambarında ilkeyi temsil eden Benzersiz Anahtar. |123 |
| PolicyId |İlkenin veri ambarındaki benzersiz tanımlayıcısı. |b66bc706-ffff-7437-0340-032819502773 |
| policyName |İlkenin Adı. |"Windows 10 Temel" |
| policyVersion |Yapılandırmanın Sürümü. İlke düzenlendiğinde veya değiştirildiğinde, daha yeni bir sürüm oluşturulur. |1, 2, 3 |
| isDeleted |Bu MAM uygulaması kaydının güncelleştirilip güncelleştirilmediğini gösterir.  <br>True- ilkenin güncelleştirilmiş alanları içeren yeni bir kaydı var. <br>False- ilke için en son kayıt. |Doğru/Yanlış |
| startDateInclusiveUTC |Bu ilkenin veri ambarında oluşturulduğu tarih ve UTC diliminde saat. |23.11.2016 12:00:00 |
| deletedDateUTC |IsDeleted değerinin True olarak değiştirildiği tarih ve UTC diliminde saat. |23.11.2016 12:00:00 |
| rowLastModifiedDateTimeUTC |Bu ilkenin veri ambarında son değiştirildiği tarih ve UTC diliminde saat. |23.11.2016 12:00:00 |

## <a name="policytypes"></a>policyTypes

**PolicyType** varlığı cihaz yapılandırma profillerinin, uygulama yapılandırma profillerinin ve uyumluluk ilkelerinin türlerini listeler. Kuruluşunuzda bir gruba Mobil Cihaz Yönetimi (MDM) ilkeleri atayabilirsiniz.

| Özellik  | Description | Örnek |
|---------|------------|--------|
| Policytypeıd |İlkenin kaynak sistemindeki benzersiz tanımlayıcısı. |123 |
| policyTypeKey |İlkenin veri ambarındaki benzersiz tanımlayıcısı. |1\. |
| policyTypeName |İlke türünün adı. |Windows 10 Uyumluluk ilkesi. |

## <a name="device-configuration"></a>Cihaz Yapılandırması

**Deviceconfigurationprofiledeviceactivity** varlığı, başarılı, beklemede, başarısız veya hata durumundaki **cihazların** günlük sayısını listeler. Bu sayı, varlığa atanmış Cihaz Yapılandırma Profillerini gösterir. Örneğin, bir **cihaz** atanan tüm ilkeleri için başarılı durumdaysa, bu gün için başarılı olan sayacı artırır. Cihaza biri başarılı diğeri hata durumunda olmak üzere iki profil atanmışsa varlık, başarılı sayacını artırır ve cihazı hata durumuna geçirir. Varlık, son 30 gün içindeki belirli bir gün için kaç cihazın hangi durumda olduğunu listeler.

| Özellik  | Description | Örnek |
|---------|------------|--------|
| dateKey |Cihaz Yapılandırma Profilinin iade işleminin, veri ambarına kaydedildiği zamanı belirten Tarih Anahtarı. |20160703 |
| bekleniyor |Bekleme durumundaki benzersiz cihazların sayısı. |123 |
| başarılı |Başarı durumundaki benzersiz cihazların sayısı. |12 |
| hata |Hata durumundaki benzersiz cihazların sayısı. |10 |
| başarısız |Başarısız durumundaki benzersiz cihazların sayısı. |2 |

**Deviceconfigurationprofileuseractivity** varlığı, başarılı, beklemede, başarısız veya hata durumundaki **kullanıcıların** günlük sayısını listeler. Bu sayı, varlığa atanmış Cihaz Yapılandırma Profillerini gösterir. Örneğin, bir **Kullanıcı** atanmış tüm ilkeleri için başarılı durumdaysa, başarılı olan sayacı o gün için bir tane yukarı gider. Bir kullanıcıya biri başarılı diğeri hata durumunda olmak üzere iki profil atanmışsa, kullanıcı hata durumunda olarak değerlendirilir.  **Deviceconfigurationprofileuseractivity** varlığı, son 30 gün içindeki belirli bir gün için kaç kullanıcının hangi durumda olduğunu listeler.

| Özellik  | Description | Örnek |
|---------|------------|--------|
| dateKey |Cihaz Yapılandırma Profilinin iade işleminin, veri ambarına kaydedildiği zamanı belirten Tarih Anahtarı. |20160703 |
| bekleniyor |Bekleme durumundaki benzersiz kullanıcıların sayısı. |123 |
| başarılı |Başarı durumundaki benzersiz kullanıcıların sayısı. |12 |
| hata |Hata durumundaki benzersiz kullanıcıların sayısı. |10 |
| başarısız |Başarısız durumundaki benzersiz kullanıcıların sayısı. |2 |

## <a name="policytypeactivities"></a>policyTypeActivities

**Policytypeactivity** varlığı, başarılı, beklemede, başarısız veya hata durumundaki toplam cihaz sayısını listeler. Bu durumları cihazın yapılandırma profiline, uygulama yapılandırma profiline veya uyumluluk ilkesine göre günlük olarak listeler.

| Özellik  | Description | Örnek |
|---------|------------|--------|
| dateKey |Tarih anahtarı, cihaz yapılandırma profili iade etme işlemi veri ambarına kaydedildiğinde. |20160703 |
| policyKey |policyKey, policyName 'i almak için ilkeyle eklenebilir. |Windows 10 temel |
| policyTypeKey |İlke Anahtarı türü, İlke Türü ile birleştirilerek ilke türü adı elde edilebilir. |Windows 10 Uyumluluk İlkesi |
| bekleniyor |Bekleme durumundaki benzersiz cihazların sayısı. |123 |
| başarılı |Başarı durumundaki benzersiz cihazların sayısı. |12 |
| hata |Hata durumundaki benzersiz cihazların sayısı. |10 |
| başarısız |Başarısız durumundaki benzersiz cihazların sayısı. |2 |

## <a name="compliance-policy"></a>Uyumluluk İlkesi

Uyumluluk İlkesi API’si, cihazlara atanmış uyumluluk ilkeleriyle ilgili durum bilgisi içeren varlıklar barındırır.

### <a name="compliancepolicystatusdeviceactivities"></a>compliancePolicyStatusDeviceActivities

Aşağıdaki tablo, uyumluluk ilkelerinin cihazlara atanma durumunu özetler. Ve her bir uyumluluk durumunda bulunan cihaz sayısını listeler.


|Özellik     |Description  |Örnek  |
|---------|---------|---------|
|dateKey  |Uyumluluk ilkesi için özetin oluşturulduğu tarihin anahtarı.|20161204 |
|bilinmiyor  |Çevrimdışı olan veya Intune ya da Azure AD ile başka bir nedenle iletişim kuramayan cihaz sayısı. |5|
|Notapplıcable      |Yönetici tarafından hedeflenen cihaz uyumluluk ilkelerinin uygulanabilir olmadığı cihaz sayısı.|201 |
|Uyumluluk      |Yönetici tarafından hedeflenen bir veya daha fazla cihaz uyumluluk ilkesini başarıyla uygulayan cihaz sayısı. |4083 |
|Yetkisizkullanımsüresinde      |Uyumlu olmayan ancak yönetici tarafından belirlenen mehil süresinde olan cihaz sayısı. |57|
|ızde      |Yönetici tarafından hedeflenen bir veya daha fazla cihaz uyumluluk ilkesi ayarını uygulayamayan veya kullanıcısı yönetici tarafından hedeflenen ilkeler ile uyum sağlayamayan cihaz sayısı.|43 |
|hata      |Intune veya Azure AD ile iletişim kuramayan ve hata iletisi veren cihaz sayısı. |3|

### <a name="compliancepolicystatusdeviceperpolicyactivities"></a>compliancePolicyStatusDevicePerPolicyActivities 

Aşağıdaki tablo, uyumluluk ilkelerinin cihazlara atanma durumunu ilke başına ve ilke türü başına olacak şekilde özetler. Ve her atanmış uyumluluk ilkesi için her bir uyumluluk durumunda bulunan cihaz sayısını listeler.



|Özellik  |Description  |Örnek  |
|---------|---------|---------|
|dateKey  |Uyumluluk ilkesi için özetin oluşturulduğu tarihin anahtarı.|20161219|
|policyKey     |Özetin oluşturulduğu uyumluluk ilkesi için anahtar. |10178 |
|policyPlatformKey      |Özetin oluşturulduğu uyumluluk ilkesinin platform türü için anahtar.|5|
|bilinmiyor     |Çevrimdışı olan veya Intune ya da Azure AD ile başka bir nedenle iletişim kuramayan cihaz sayısı.|13|
|Notapplıcable     |Yönetici tarafından hedeflenen cihaz uyumluluk ilkelerinin uygulanabilir olmadığı cihaz sayısı.|3|
|Uyumluluk      |Yönetici tarafından hedeflenen bir veya daha fazla cihaz uyumluluk ilkesini başarıyla uygulayan cihaz sayısı. |45|
|Yetkisizkullanımsüresinde      |Uyumlu olmayan ancak yönetici tarafından belirlenen mehil süresinde olan cihaz sayısı. |3|
|ızde      |Yönetici tarafından hedeflenen bir veya daha fazla cihaz uyumluluk ilkesi ayarını uygulayamayan veya kullanıcısı yönetici tarafından hedeflenen ilkeler ile uyum sağlayamayan cihaz sayısı.|7|
|hata      |Intune veya Azure AD ile iletişim kuramayan ve hata iletisi veren cihaz sayısı. |3|

### <a name="policyplatformtypes"></a>policyPlatformTypes

Aşağıdaki tablo, tüm atanmış ilkelerin platform türlerini içerir. Hiçbir cihaza atanmamış ilkelerin platform türleri bu tabloda yer almamaktadır.


|Özellik  |Description  |Örnek  |
|---------|---------|---------|
|policyPlatformTypeKey      |İlke platform türü için benzersiz anahtar. |20170519 |
|Policyplatformtypeıd      |İlke platform türü için benzersiz tanımlayıcı.|1\.|
|policyPlatformTypeName      |İlke platform türünün adı.|AndroidForWork |

### <a name="policydeviceactivities"></a>policyDeviceActivities

Aşağıdaki tablo; başarılı, beklemede, başarısız veya hata durumundaki cihazların günlük sayısını listeler. Bu sayı, İlke Türü profillerindeki verileri yansıtır. Örneğin, bir cihaz kendisine atanan tüm ilkeler için başarılı durumunda ise ilgili gün için başarılı sayacı bir artar. Cihaza biri başarılı diğeri hata durumunda olmak üzere iki profil atanmışsa varlık, başarılı sayacını artırır ve cihazı hata durumuna geçirir. PolicyDeviceActivity varlığı, son 30 gün içindeki belirli bir gün için kaç cihazın hangi durumda olduğunu listeler.

|Özellik  |Description  |Örnek  |
|---------|---------|---------|
|dateKey|Cihaz Yapılandırma Profilinin iade işleminin, veri ambarına kaydedildiği zamanı belirten Tarih Anahtarı.|20160703|
|bekleniyor|Bekleme durumundaki benzersiz cihazların sayısı.|123|
|Başarılı|Başarı durumundaki benzersiz cihazların sayısı.|12|
|policyKey|policyKey, policyName 'i almak için ilkeyle eklenebilir.|Windows 10 temel|
|hata|Hata durumundaki benzersiz cihazların sayısı.|10|
|başarısız|Başarısız durumundaki benzersiz cihazların sayısı.|2|

### <a name="policyuseractivities"></a>policyUserActivities

Aşağıdaki tablo; başarılı, beklemede, başarısız veya hata durumundaki kullanıcıların günlük sayısını listeler. Bu sayı, İlke Türü profillerindeki verileri yansıtır. Örneğin, bir kullanıcı kendisine atanan tüm ilkeler için başarılı durumunda ise ilgili gün için başarılı sayacı bir artar. Bir kullanıcıya biri başarılı diğeri hata durumunda olmak üzere iki profil atanmışsa, kullanıcı hata durumunda olarak değerlendirilir. PolicyUserActivity varlığı, son 30 gün içindeki belirli bir gün için kaç kullanıcının hangi durumda olduğunu listeler.


| Özellik  |                                         Description                                         |       Örnek       |
|-----------|---------------------------------------------------------------------------------------------|---------------------|
|  dateKey  | Cihaz Yapılandırma Profilinin iade işleminin, veri ambarına kaydedildiği zamanı belirten Tarih Anahtarı. |      20160703       |
|  bekleniyor  |                         Bekleme durumundaki benzersiz cihazların sayısı.                          |         123         |
| başarılı |                         Başarı durumundaki benzersiz cihazların sayısı.                          |         12          |
| policyKey |                 policyKey, policyName 'i almak için ilkeyle eklenebilir.                 | Windows 10 temel |
|   hata   |                          Hata durumundaki benzersiz cihazların sayısı.                           |         10          |

