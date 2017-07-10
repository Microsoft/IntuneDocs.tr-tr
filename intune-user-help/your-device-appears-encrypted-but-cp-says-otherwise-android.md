---
title: "Android cihazınız şifrelenmiş görünüyor"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 05/25/2017
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
ms.openlocfilehash: 269ad7968242f8f5ce7095c9c73347987675e846
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="your-android-device-seems-to-be-encrypted-but-company-portal-says-otherwise"></a>Android cihazınızı şifreli gibi görünüyor, ancak Şirket Portalı aksini söylüyor

Bir cihazı şifrelediğinizde, yalnızca sizin bildiğiniz gizli bir anahtar kullanarak cihazdaki bilgileri kodlamış ve dolayısıyla yetkisiz kişilerin cihaza erişimini engellemiş olursunuz. Bilgilerinizin güvende olduğundan emin olmak için kuruluşunuz; şirket dosyalarına, e-postalara veya verilere erişebilmeniz için Android cihazınızı şifrelemenizi istiyor.

## <a name="common-issues"></a>Yaygın sorunlar

Özellikle sürüm 7.0 sonrası daha yeni Android sürümleri cihazınızın tam olarak şifrelendiğinden emin olmak için başlangıç geçiş kodu gerektirir. Farklı cihaz üreticilerinin başlangıç geçiş kodu için farklı açıklamaları ve konumları vardır. Çoğu zaman, bu "Güvenli Başlatma" olarak adlandırılır. 

## <a name="solutions"></a>Çözümler

### <a name="add-a-startup-pin"></a>Başlangıç PIN’i ekleme

Belirli Android cihazları cihazınızın güvenli olduğundan emin olmak için bir başlangıç PIN’i oluşturmanızı gerektirir. Birçok farklı üreticinin çok çeşitli Android sürümleri vardır. Bu seçeneği etkinleştirmek için ayarlar uygulamanızda bir konum bularak bu sorunu gidermeyi deneyebilirsiniz. Örneğin, Samsung Galaxy S7’de, Güvenli Başlatma’yı **Ayarlar** > **Kilit Ekranı ve Güvenlik** > **Güvenli Başlatma** ekranına giderek etkinleştirirsiniz.  

### <a name="downgrade-your-version-of-android"></a>Android sürümünüzü düşürme
Cihazınız Android 6.0+ sürümüne düşürme seçeneği sunuyorsa, bunu yapın. Cihazınızın sürümünü düşürmeyi denediğinizde veri kaybı riski vardır. Aksi takdirde, bu sorunu çözmek için BT yöneticinize başvurmanızı öneririz. BT yöneticinizin iletişim bilgilerini [Şirket Portalı web sitesinden](http://portal.manage.microsoft.com) alabilirsiniz.

## <a name="specific-manufacturer-issues"></a>Belirli üretici sorunları

7.0+ sürümü kullanılan bazı Android cihazlar, belirli Android platformu standartları ile uymayan yollarla veri şifreler. Bu cihazlar kutudan çıktığı haliyle şifreli gibi görünebilir, ancak Intune cihaza fiziksel erişimi olan kötü amaçlı kullanıcıların cihazdaki bilgileri tehlikeye atması gibi kullanılan yöntemleri tanır.

> [!Note]
> Microsoft, sınama aşamasında ya da kullanıcıların bize bildirdiği tüm sorunları ele almak için üreticiler ile birlikte çalışır. Yeni bilgiler kullanılabilir olduğunda bu makaleyi güncelleştireceğiz. 

## <a name="known-devices"></a>Bilinen cihazlar

### <a name="known-devices-that-can-be-updated-to-fix-this-issue"></a>Bu sorunu gidermek için güncelleştirilebilir bilinen cihazlar

Aşağıdaki cihazlardan birine sahipseniz cihazınızı Android’in en son sürümüne güncelleştirmediğiniz durumda bu sorunla karşılaşabilirsiniz. Bu cihaz güncelleştirmelerini yüklemek için **Ayarlar** > **Güncelleştirme** bölümüne gidin. 

- [Huawei Honor 8](http://consumer.huawei.com/en/support/mobile-phones/honor8_en-sup.htm)
- [Huawei P9](http://consumer.huawei.com/mobile-phones/p9/index.html)

### <a name="known-devices-that-currently-cannot-be-updated-to-fix-this-issue"></a>Bu sorunu gidermek için şu anda güncelleştirilebilir olmayan bilinen cihazlar

- [Huawei Mate 8](http://consumer.huawei.com/en/mobile-phones/mate8/index.htm)
- [Xiaomi Mi akıllı telefonlar](https://xiaomi-mi.com/mi-smartphones/)
