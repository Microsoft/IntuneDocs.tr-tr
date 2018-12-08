---
title: İlke varlıkları için başvuru
titlesuffix: Microsoft Intune
description: Intune Veri Ambarı API’sindeki varlık koleksiyonlarının İlke kategorisi için başvuru konusu.
keywords: Intune Veri Ambarı
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: 9fb05991b3e289d4a24cc2f3a5b2c398c12b1a15
ms.sourcegitcommit: fff179f59bd542677cbd4bf3bacc24bb880e2cb6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/07/2018
ms.locfileid: "53032444"
---
# <a name="reference-for-policy-entities"></a>İlke varlıkları için başvuru

**İlke** kategorisi, mobil cihazlar için aşağıdaki gibi bilgileri izleyen varlıklar içerir:

  -  Cihaz yapılandırma profilleri, uygulama yapılandırma profilleri ve uyumluluk ilkelerinin dökümü  
  -  Başarılı, beklemede, başarısız veya hata durumundaki cihazların günlük sayısı  
  -  Başarılı, beklemede, başarısız veya hata durumundaki kullanıcıların günlük sayısı  
  -  Başarılı, beklemede, başarısız veya hata durumundaki cihazların toplam sayısı  

## <a name="policy"></a>İlke

**İlke** varlığı, cihaz yapılandırma profillerini, uygulama yapılandırma profillerini ve uyumluluk ilkelerini listeler. Kuruluşunuzda bir gruba Mobil Cihaz Yönetimi (MDM) ilkeleri atayabilirsiniz.

| Özellik  | Açıklama | Örnek |
|---------|------------|--------|
| PolicyKey |Veri ambarında ilkeyi temsil eden Benzersiz Anahtar. |123 |
| PolicyId |İlkenin veri ambarındaki benzersiz tanımlayıcısı. |b66bc706-ffff-7437-0340-032819502773 |
| PolicyName |İlkenin Adı. |"Windows 10 Temel" |
| PolicyVersion |Yapılandırmanın Sürümü. İlke düzenlendiğinde veya değiştirildiğinde, daha yeni bir sürüm oluşturulur. |1, 2, 3 |
| IsDeleted |Bu MAM uygulaması kaydının güncelleştirilip güncelleştirilmediğini gösterir.  <br>True- ilkenin güncelleştirilmiş alanları içeren yeni bir kaydı var. <br>False- ilke için en son kayıt. |Doğru/Yanlış |
| StartDateInclusiveUTC |Bu ilkenin veri ambarında oluşturulduğu tarih ve UTC diliminde saat. |23.11.2016 12:00:00 |
| DeletedDateUTC |IsDeleted değerinin True olarak değiştirildiği tarih ve UTC diliminde saat. |23.11.2016 12:00:00 |
| RowLastModifiedDateTimeUTC |Bu ilkenin veri ambarında son değiştirildiği tarih ve UTC diliminde saat. |23.11.2016 12:00:00 |

## <a name="policytype"></a>PolicyType

**PolicyType** varlığı, cihaz yapılandırma profillerini, uygulama yapılandırma profillerini ve Uyumluluk ilkeleri türlerini listeler. Kuruluşunuzda bir gruba Mobil Cihaz Yönetimi (MDM) ilkeleri atayabilirsiniz.

| Özellik  | Açıklama | Örnek |
|---------|------------|--------|
| PolicyTypeId |İlkenin kaynak sistemindeki benzersiz tanımlayıcısı. |123 |
| PolicyTypeKey |İlkenin veri ambarındaki benzersiz tanımlayıcısı. |1. |
| PolicyTypeName |İlke türünün adı. |Windows 10 Uyumluluk ilkesi. |

## <a name="deviceconfiguration"></a>DeviceConfiguration

**DeviceConfigurationProfileDeviceActivity** varlığı, başarılı, beklemede, başarısız veya hata durumundaki cihazların günlük sayısını listeler. Bu sayı, varlığa atanmış Cihaz Yapılandırma Profillerini gösterir. Örneğin, bir cihaz kendisine atanan tüm ilkeler için başarılı durumunda ise ilgili gün için başarılı sayacı bir artar. Cihaza biri başarılı diğeri hata durumunda olmak üzere iki profil atanmışsa varlık, başarılı sayacını artırır ve cihazı hata durumuna geçirir. Varlık, son 30 gün içindeki belirli bir gün için kaç cihazın hangi durumda olduğunu listeler.

| Özellik  | Açıklama | Örnek |
|---------|------------|--------|
| DateKey |Cihaz Yapılandırma Profilinin iade işleminin, veri ambarına kaydedildiği zamanı belirten Tarih Anahtarı. |20160703 |
| Bekleniyor |Bekleme durumundaki benzersiz cihazların sayısı. |123 |
| Başarılı |Başarı durumundaki benzersiz cihazların sayısı. |12 |
| Hata |Hata durumundaki benzersiz cihazların sayısı. |10 |
| Başarısız |Başarısız durumundaki benzersiz cihazların sayısı. |2 |



**DeviceConfigurationProfileUserActivity** varlığı; başarılı, beklemede, başarısız veya hata durumundaki kullanıcıların günlük sayısını listeler. Bu sayı, varlığa atanmış Cihaz Yapılandırma Profillerini gösterir. Örneğin, bir kullanıcı kendisine atanan tüm ilkeler için başarılı durumunda ise ilgili gün için başarılı sayacı bir artar. Bir kullanıcıya biri başarılı diğeri hata durumunda olmak üzere iki profil atanmışsa, kullanıcı hata durumunda olarak değerlendirilir.  **DeviceConfigurationProfileUserActivity** varlığı, son 30 gün içindeki belirli bir gün için kaç kullanıcının hangi durumda olduğunu listeler.

| Özellik  | Açıklama | Örnek |
|---------|------------|--------|
| DateKey |Cihaz Yapılandırma Profilinin iade işleminin, veri ambarına kaydedildiği zamanı belirten Tarih Anahtarı. |20160703 |
| Bekleniyor |Bekleme durumundaki benzersiz kullanıcıların sayısı. |123 |
| Başarılı |Başarı durumundaki benzersiz kullanıcıların sayısı. |12 |
| Hata |Hata durumundaki benzersiz kullanıcıların sayısı. |10 |
| Başarısız |Başarısız durumundaki benzersiz kullanıcıların sayısı. |2 |

## <a name="policytypeactivity"></a>PolicyTypeActivity

**PolicyTypeActivity** varlığı, başarılı, beklemede, başarısız veya hata durumundaki cihazların toplam sayısını listeler. Bu durumları cihazın yapılandırma profiline, uygulama yapılandırma profiline veya uyumluluk ilkesine göre günlük olarak listeler.

| Özellik  | Açıklama | Örnek |
|---------|------------|--------|
| DateKey |Cihaz Yapılandırma Profilinin iade işleminin, veri ambarına kaydedildiği zamanı belirten Tarih Anahtarı. |20160703 |
| PolicyKey |İlke Anahtarı, İlke ile birleştirilerek ilke adı elde edilebilir. |Windows 10 temel |
| PolicyTypeKey |İlke Anahtarı türü, İlke Türü ile birleştirilerek ilke türü adı elde edilebilir. |Windows 10 Uyumluluk İlkesi |
| Bekleniyor |Bekleme durumundaki benzersiz cihazların sayısı. |123 |
| Başarılı |Başarı durumundaki benzersiz cihazların sayısı. |12 |
| Hata |Hata durumundaki benzersiz cihazların sayısı. |10 |
| Başarısız |Başarısız durumundaki benzersiz cihazların sayısı. |2 |

## <a name="compliance-policy"></a>Uyumluluk İlkesi

Uyumluluk İlkesi API’si, cihazlara atanmış uyumluluk ilkeleriyle ilgili durum bilgisi içeren varlıklar barındırır.

### <a name="compliancepolicystatusdeviceactivities"></a>CompliancePolicyStatusDeviceActivities

Aşağıdaki tablo, uyumluluk ilkelerinin cihazlara atanma durumunu özetler. Ve her bir uyumluluk durumunda bulunan cihaz sayısını listeler.


|Özellik     |Açıklama  |Örnek  |
|---------|---------|---------|
|DateKey  |Uyumluluk ilkesi için özetin oluşturulduğu tarihin anahtarı.|20161204 |
|Bilinmeyen  |Çevrimdışı olan veya Intune ya da Azure AD ile başka bir nedenle iletişim kuramayan cihaz sayısı. |5|
|NotApplicable      |Yönetici tarafından hedeflenen cihaz uyumluluk ilkelerinin uygulanabilir olmadığı cihaz sayısı.|201 |
|Uyumlu      |Yönetici tarafından hedeflenen bir veya daha fazla cihaz uyumluluk ilkesini başarıyla uygulayan cihaz sayısı. |4083 |
|InGracePeriod      |Uyumlu olmayan ancak yönetici tarafından belirlenen mehil süresinde olan cihaz sayısı. |57|
|Uyumsuz      |Yönetici tarafından hedeflenen bir veya daha fazla cihaz uyumluluk ilkesi ayarını uygulayamayan veya kullanıcısı yönetici tarafından hedeflenen ilkeler ile uyum sağlayamayan cihaz sayısı.|43 |
|Hata      |Intune veya Azure AD ile iletişim kuramayan ve hata iletisi veren cihaz sayısı. |3|

### <a name="compliancepolicystatusdeviceperpolicyactivities"></a>CompliancePolicyStatusDevicePerPolicyActivities 

Aşağıdaki tablo, uyumluluk ilkelerinin cihazlara atanma durumunu ilke başına ve ilke türü başına olacak şekilde özetler. Ve her atanmış uyumluluk ilkesi için her bir uyumluluk durumunda bulunan cihaz sayısını listeler.



|Özellik  |Açıklama  |Örnek  |
|---------|---------|---------|
|DateKey  |Uyumluluk ilkesi için özetin oluşturulduğu tarihin anahtarı.|20161219|
|PolicyKey     |Özetin oluşturulduğu uyumluluk ilkesi için anahtar. |10178 |
|PolicyPlatformKey      |Özetin oluşturulduğu uyumluluk ilkesinin platform türü için anahtar.|5|
|Bilinmeyen     |Çevrimdışı olan veya Intune ya da Azure AD ile başka bir nedenle iletişim kuramayan cihaz sayısı.|13|
|NotApplicable     |Yönetici tarafından hedeflenen cihaz uyumluluk ilkelerinin uygulanabilir olmadığı cihaz sayısı.|3|
|Uyumlu      |Yönetici tarafından hedeflenen bir veya daha fazla cihaz uyumluluk ilkesini başarıyla uygulayan cihaz sayısı. |45|
|YetkisizKullanımSüresinde      |Uyumlu olmayan ancak yönetici tarafından belirlenen mehil süresinde olan cihaz sayısı. |3|
|Uyumsuz      |Yönetici tarafından hedeflenen bir veya daha fazla cihaz uyumluluk ilkesi ayarını uygulayamayan veya kullanıcısı yönetici tarafından hedeflenen ilkeler ile uyum sağlayamayan cihaz sayısı.|7|
|Hata      |Intune veya Azure AD ile iletişim kuramayan ve hata iletisi veren cihaz sayısı. |3|

### <a name="policyplatformtypes"></a>PolicyPlatformTypes

Aşağıdaki tablo, tüm atanmış ilkelerin platform türlerini içerir. Hiçbir cihaza atanmamış ilkelerin platform türleri bu tabloda yer almamaktadır.


|Özellik  |Açıklama  |Örnek  |
|---------|---------|---------|
|PolicyPlatformTypeKey      |İlke platform türü için benzersiz anahtar. |20170519 |
|PolicyPlatformTypeId      |İlke platform türü için benzersiz tanımlayıcı.|1.|
|PolicyPlatformTypeName      |İlke platform türünün adı.|AndroidForWork |

### <a name="policydeviceactivity"></a>PolicyDeviceActivity

Aşağıdaki tablo; başarılı, beklemede, başarısız veya hata durumundaki cihazların günlük sayısını listeler. Bu sayı, İlke Türü profillerindeki verileri yansıtır. Örneğin, bir cihaz kendisine atanan tüm ilkeler için başarılı durumunda ise ilgili gün için başarılı sayacı bir artar. Cihaza biri başarılı diğeri hata durumunda olmak üzere iki profil atanmışsa varlık, başarılı sayacını artırır ve cihazı hata durumuna geçirir. PolicyDeviceActivity varlığı, son 30 gün içindeki belirli bir gün için kaç cihazın hangi durumda olduğunu listeler.

|Özellik  |Açıklama  |Örnek  |
|---------|---------|---------|
|DateKey|Cihaz Yapılandırma Profilinin iade işleminin, veri ambarına kaydedildiği zamanı belirten Tarih Anahtarı.|20160703|
|Bekleniyor|Bekleme durumundaki benzersiz cihazların sayısı.|123|
|Başarılı|Başarı durumundaki benzersiz cihazların sayısı.|12|
PolicyKey|İlke Anahtarı, İlke ile birleştirilerek ilke adı elde edilebilir.|Windows 10 temel|
|Hata|Hata durumundaki benzersiz cihazların sayısı.|10|
|Başarısız|Başarısız durumundaki benzersiz cihazların sayısı.|2|

### <a name="policyuseractivity"></a>PolicyUserActivity 

Aşağıdaki tablo; başarılı, beklemede, başarısız veya hata durumundaki kullanıcıların günlük sayısını listeler. Bu sayı, İlke Türü profillerindeki verileri yansıtır. Örneğin, bir kullanıcı kendisine atanan tüm ilkeler için başarılı durumunda ise ilgili gün için başarılı sayacı bir artar. Bir kullanıcıya biri başarılı diğeri hata durumunda olmak üzere iki profil atanmışsa, kullanıcı hata durumunda olarak değerlendirilir. PolicyUserActivity varlığı, son 30 gün içindeki belirli bir gün için kaç kullanıcının hangi durumda olduğunu listeler.


| Özellik  |                                         Açıklama                                         |       Örnek       |
|-----------|---------------------------------------------------------------------------------------------|---------------------|
|  DateKey  | Cihaz Yapılandırma Profilinin iade işleminin, veri ambarına kaydedildiği zamanı belirten Tarih Anahtarı. |      20160703       |
|  Bekleniyor  |                         Bekleme durumundaki benzersiz cihazların sayısı.                          |         123         |
| Başarılı |                         Başarı durumundaki benzersiz cihazların sayısı.                          |         12          |
| PolicyKey |                İlke Anahtarı, İlke ile birleştirilerek ilke adı elde edilebilir.                 | Windows 10 temel |
|   Hata   |                          Hata durumundaki benzersiz cihazların sayısı.                           |         10          |

