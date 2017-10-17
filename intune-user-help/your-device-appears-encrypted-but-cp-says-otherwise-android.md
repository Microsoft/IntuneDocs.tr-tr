---
title: "Android cihazınız şifrelenmiş görünüyor"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 09/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ba593c08-1a78-4013-8525-b45a948772ec
searchScope: User help
ROBOTS: 
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 208cf6eb2d29ec5458d97d0a4481cec420acc281
ms.sourcegitcommit: 59811bf1183b3ef9c9e81eded634bd0d3124d0bb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/09/2017
---
# <a name="your-android-device-seems-to-be-encrypted-but-company-portal-says-otherwise"></a>Android cihazınızı şifreli gibi görünüyor, ancak Şirket Portalı aksini söylüyor

Bir cihazı şifrelemek, cihazdaki bilgileri yalnızca sizin bildiğiniz bir gizli anahtar ile kodlamaktır. Böylece yetkisi olmayanların cihaza erişimi engellenmiş olur. Pek çok kuruluş; kullanıcılarının şirket dosyaları, e-postası veya verilerine erişmeleri için Android cihazlarını şifrelemelerini gerektirir.

## <a name="common-issues"></a>Yaygın sorunlar

Özellikle sürüm 7.0 sonrası daha yeni Android sürümleri cihazınızın tam olarak şifrelendiğinden emin olmak için başlangıç geçiş kodu gerektirir. Farklı cihaz üreticilerinin başlangıç geçiş kodu için farklı açıklamaları ve konumları vardır. Bu ayar çoğu zaman “Güvenli Başlatma” olarak adlandırılır. 

## <a name="solutions"></a>Çözümler

### <a name="add-a-startup-pin"></a>Başlangıç PIN’i ekleme

Belirli Android cihazları, cihazınızın güvenli olduğundan emin olmak için bir başlangıç PIN’i oluşturmayı gerektirir. Birçok farklı üreticinin çok çeşitli Android sürümleri vardır. Bu seçeneği etkinleştirmek için ayarlar uygulamanızda bir konum bularak bu sorunu gidermeyi deneyebilirsiniz. Örneğin, Samsung Galaxy S7’de, Güvenli Başlatma’yı **Ayarlar** > **Kilit Ekranı ve Güvenlik** > **Güvenli Başlatma** ekranına giderek etkinleştirirsiniz.  

### <a name="downgrade-your-version-of-android"></a>Android sürümünüzü düşürme

Cihazınız Android 6.0+ sürümüne düşürme seçeneği sunuyorsa, bunu yapın. Cihazınızın sürümünü düşürmeyi denediğinizde veri kaybı riski vardır. Aksi takdirde, bu sorunu çözmek için şirketinizin destek birimine başvurmanızı öneririz. Şirketinizin destek biriminin iletişim bilgilerini [Şirket Portalı web sitesinden](https://portal.manage.microsoft.com) alabilirsiniz.

## <a name="specific-manufacturer-issues"></a>Belirli üretici sorunları

7.0+ sürümü kullanan bazı Android cihazlar, belirli Android platformu standartlarına uymayan yollarla veri şifreler. Bu cihazlar, yeni olsalar dahi şifreli görünebilir. Intune, bu cihazların şifreleme yönteminin cihaz bilgilerini riske attığını algılar. Bu risk temel olarak cihaza fiziksel erişimi olan kötü amaçlı kullanıcılardan kaynaklanır.

> [!Note]
> Microsoft, sınama aşamasında ya da kullanıcıların bize bildirdiği tüm sorunları ele almak için üreticiler ile birlikte çalışır. Yeni bilgiler mevcut oldukça bu makaleyi güncelleştireceğiz. 

## <a name="known-devices"></a>Bilinen cihazlar

### <a name="known-devices-that-can-be-updated-to-fix-this-issue"></a>Bu sorunu gidermek için güncelleştirilebilir bilinen cihazlar

Aşağıdaki cihazlardan birine sahipseniz cihazınızı Android’in en son sürümüne güncelleştirmediğiniz durumda bu sorunla karşılaşabilirsiniz. Bu cihaz güncelleştirmelerini yüklemek için **Ayarlar** > **Güncelleştirme** bölümüne gidin. 

- [Huawei Honor 8](http://consumer.huawei.com/en/support/mobile-phones/honor8_en-sup.htm)
- [Huawei P9](http://consumer.huawei.com/en/phones/p9/)

### <a name="known-devices-that-currently-cannot-be-updated-to-fix-this-issue"></a>Bu sorunu gidermek için şu anda güncelleştirilebilir olmayan bilinen cihazlar

Aşağıdaki cihazlarda bu sorun çözülememektedir. Şirket kaynaklarına erişmek için başka bir cihaz kullanmanız gerekebilir. 

- [Huawei Mate 8](http://consumer.huawei.com/en/mobile-phones/mate8/index.htm)
- [Xiaomi Mi akıllı telefonlar](https://xiaomi-mi.com/mi-smartphones/)
