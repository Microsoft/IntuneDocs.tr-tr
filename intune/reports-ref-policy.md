---
title: "İlke | Microsoft Docs"
description: "Intune Veri Ambarı API’sindeki varlık koleksiyonlarının İlke kategorisi için başvuru konusu."
keywords: "Intune Veri Ambarı"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: D5ADB9D8-D46A-43BD-AB0F-D6927508E3F4
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 079cfe097d6cf462f9ccd0a32d2e327b3b605e40
ms.sourcegitcommit: bb2c181fd6de929cf1e5d3856e048d617eb72063
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2017
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
| PolicyTypeKey |İlkenin veri ambarındaki benzersiz tanımlayıcısı. |1 |
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

## <a name="userconfiguration"></a>UserConfiguration

**UserConfigurationProfileDeviceActivity** varlığı, başarılı, beklemede, başarısız veya hata durumundaki kullanıcıların günlük sayısını listeler. Bu sayı, varlığa atanmış Cihaz Yapılandırma Profillerini gösterir. Örneğin, bir kullanıcı kendisine atanan tüm ilkeler için başarılı durumunda ise ilgili gün için başarılı sayacı bir artar. Bir kullanıcıya biri başarılı diğeri hata durumunda olmak üzere iki profil atanmışsa, kullanıcıyı hata durumunda olarak değerlendiririz.  **UserConfigurationProfileDeviceActivity** varlığı, son 30 gün içindeki belirli bir gün için kaç kullanıcının hangi durumda olduğunu listeler.

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
| Başarısız- |Başarısız durumundaki benzersiz cihazların sayısı. |2 |