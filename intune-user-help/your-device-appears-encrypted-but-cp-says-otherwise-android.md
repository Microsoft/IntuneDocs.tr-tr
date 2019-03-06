---
title: Android cihazınız şifrelenmiş görünüyor | Microsoft Docs
description: ''
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 11/14/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ba593c08-1a78-4013-8525-b45a948772ec
searchScope:
- User help
ROBOTS: ''
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 55935b2f69f9573d8df5ea5ca32fb4587c652b26
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57389475"
---
# <a name="your-android-device-seems-to-be-encrypted-but-company-portal-says-otherwise"></a>Android cihazınızı şifreli gibi görünüyor, ancak Şirket Portalı aksini söylüyor

Bir cihazı şifrelemek, cihazdaki bilgileri yalnızca sizin bildiğiniz bir gizli anahtar ile kodlamaktır. Böylece yetkisi olmayanların cihaza erişimi engellenmiş olur. Pek çok kuruluş; kullanıcılarının şirket dosyaları, e-postası veya verilerine erişmeleri için Android cihazlarını şifrelemelerini gerektirir.

## <a name="common-issues"></a>Yaygın sorunlar

Özellikle sürüm 7.0 sonrası daha yeni Android sürümleri cihazınızın tam olarak şifrelendiğinden emin olmak için başlangıç geçiş kodu gerektirir. Farklı cihaz üreticilerinin başlangıç geçiş kodu için farklı açıklamaları ve konumları vardır. Bu ayar çoğu zaman “Güvenli Başlatma” olarak adlandırılır. 

## <a name="solutions"></a>Çözümler

### <a name="add-a-startup-pin"></a>Başlangıç PIN’i ekleme

Belirli Android cihazları, cihazınızın güvenli olduğundan emin olmak için bir başlangıç PIN’i oluşturmayı gerektirir. Birçok farklı üreticinin çok çeşitli Android sürümleri vardır. Bu seçeneği etkinleştirmek için ayarlar uygulamanızda bir konum bularak bu sorunu gidermeyi deneyebilirsiniz. Örneğin, Samsung Galaxy S7’de, Güvenli Başlatma’yı **Ayarlar** > **Kilit Ekranı ve Güvenlik** > **Güvenli Başlatma** ekranına giderek etkinleştirirsiniz.  

### <a name="encrypt-the-entire-device"></a>Tüm cihazı şifreleyin

Bazı cihazlar size, tüm cihazı veya yalnızca kullanılan alanı şifreleme seçeneği sunar. “Yalnızca kullanılan alan” yerine tüm cihazı şifreleme seçeneğini belirleyin. Yalnızca kullanılan alanı şifrelediyseniz:

1. [Bu cihazı Şirket Portalı’ndan kaldırın](unenroll-your-device-from-intune-android.md)
2. Kullanılan alanın şifresini çözün
3. Tüm cihazı şifreleyin
4. Cihazı yeniden kaydedin

### <a name="downgrade-your-version-of-android"></a>Android sürümünüzü düşürme

Cihazınız Android 6.0+ sürümüne düşürme seçeneği sunuyorsa, bunu yapın. Cihazınızın sürümünü düşürmeyi denediğinizde veri kaybı riski vardır. Aksi takdirde, bu sorunu çözmek için şirketinizin destek birimine başvurmanızı öneririz. Şirketinizin destek biriminin iletişim bilgilerini [Şirket Portalı web sitesinden](https://go.microsoft.com/fwlink/?linkid=2010980) alabilirsiniz.

## <a name="specific-manufacturer-issues"></a>Belirli üretici sorunları

7.0+ sürümü kullanan bazı Android cihazlar, belirli Android platformu standartlarına uymayan yollarla veri şifreler. Bu cihazlar, yeni olsalar dahi şifreli görünebilir. Intune, bu cihazların şifreleme yönteminin cihaz bilgilerini riske attığını algılar. Bu risk temel olarak cihaza fiziksel erişimi olan kötü amaçlı kullanıcılardan kaynaklanır.

> [!Note]
> Microsoft, sınama aşamasında ya da kullanıcıların bize bildirdiği tüm sorunları ele almak için üreticiler ile birlikte çalışır. Yeni bilgiler mevcut oldukça bu makaleyi güncelleştireceğiz. 

## <a name="known-devices"></a>Bilinen cihazlar

### <a name="known-devices-that-can-be-updated-to-fix-this-issue"></a>Bu sorunu gidermek için güncelleştirilebilir bilinen cihazlar

Cihazınızı en son Android sürümüne güncelleştirmediyseniz, cihazınızın Git **ayarları** seçin **güncelleştirme**. Güncelleştirilene kadar bu cihazların uyumlu olmayan olarak görünebilir:  

- Huawei Honor 8
- Huawei P9

### <a name="known-devices-that-currently-cannot-be-updated-to-fix-this-issue"></a>Bu sorunu gidermek için şu anda güncelleştirilebilir olmayan bilinen cihazlar
Aşağıdaki cihazlar, her zaman şifreli görünür ve şirket kaynaklarına erişmek için kullanılamaz. Şirket kaynaklarına erişmek için farklı bir cihaz kullanmanız gerekir.  

- Huawei Mate 8
- OPPO cihazları
- Vivo cihazları
- Xiaomi Mi smartphones
