---
title: Intune Şirket Portalı cihazlar için parola gereksinimleri | Microsoft Docs
description: Bu makalede, kuruluşunuzun zorlayacağı ortak parola gereksinimleri açıklanmaktadır.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 09/05/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: efb3c261-1f6c-4d39-bfa4-18661f8c59c7
searchScope:
- User help
ROBOTS: ''
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: bce3ae1fd5386c749285313f29fc88cf7b464750
ms.sourcegitcommit: d0d320fbac69b063b4264491d8a918cfe12bd485
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70751778"
---
# <a name="device-password-requirements-for-enrolled-devices"></a>Kayıtlı cihazlar için cihaz parolası gereksinimleri

Kuruluşunuz, iş veya okul kaynaklarına erişmenize izin vermeden önce daha güvenli bir parola oluşturmanızı gerektirebilir. Bu makalede, Windows 10, iOS, macOS ve Android cihazları için ortak parola gereksinimleri açıklanmaktadır. Kuruluşunuz bu gereksinimlerin tümünü zorlayamayabilir.  


Bir parola veya geçiş kodu artık bir gereksinimi karşılamıyorsa, Şirket Portalı bir ileti alırsınız. Bu, yapmanız gereken değişiklikleri anlatmaktadır. İletide ayrıntı sağlanmamışsa, bu makaleyi geçerli parolanızla karşılaştırmak için bir başvuru olarak kullanın.  

> [!IMPORTANT]
> Parolanızı gereksinimlerini karşılayacak şekilde değiştirdiyseniz ancak hala bildirimler alıyorsanız, cihazınızı yeniden başlatın.  

Ek Yardım veya kuruluşunuzun özel gereksinimlerini öğrenmek için BT destek sorumlunuza başvurun. İletişim bilgileri için [Şirket portalı Web sitesini](https://go.microsoft.com/fwlink/?linkid=2010980) denetleyin.  

## <a name="windows-10-password-requirements"></a>Windows 10 parola gereksinimleri

| `Message` | Nasıl düzeltileceğini |
|-----------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Parola gereklidir. | Bir parola ayarlayın. Kuruluşunuz cihazınızın kilidini açmak için bir parola girmenizi gerektiriyor. |
| Parola çok basit. |  Parolanızın 1234 veya 1111 gibi sıralı veya yinelenen numaralar içermediğinden emin olun. |
| Parola çok kısa.| Daha fazla karakter içeren bir parola güncelleştirin veya ayarlayın. Kuruluşunuz parolanızın belirli bir uzunlukta olmasını gerektirir. Gerçekte seçtikleri Özellikler farklılık gösterir, ancak ihtiyaç duydukları en düşük uzunluk 4 karakterdir ve üst sınır 16 ' dır. |
| Parola yalnızca sayı içermelidir. | Yalnızca sayı içeren bir parola ayarlayın.|
| Parola yalnızca alfasayısal karakterlerden oluşmalıdır. | Sayıların ve harflerin karışımını içeren bir parola ayarlayın.|
| Parola karmaşık karakterler içermelidir. | Sayılar, büyük harfler ve, `$` `%`ve `#`gibi semboller gibi karmaşık karakterler ekleyin. Kuruluşunuz, diğerlerinin parolayı tahmin etmelerini zorlaştırmak için harf, sayı ve alfasayısal olmayan karakterlerin bir karışımını gerektirir.|  
| Parolanın süresi doldu. | Yeni bir parola ayarlayın. Kuruluşunuz, parolanızın belirli bir süre geçtikten sonra değiştirilmesini gerektirir. |
| Parolanız çok kısa süre önce kullanıldı. | Daha önce kullanılmayan bir parola seçin. Bir parolayı yeniden kullanmadan önce kuruluşunuz belirli bir süre geçiş yapılmasını gerektirir. |

## <a name="ios-passcode-requirements"></a>iOS geçiş kodu gereksinimleri

| `Message` | Nasıl düzeltileceğini |
|-----------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Geçiş kodu gerekiyor.| Bir geçiş kodu ayarlayın. Kuruluşunuz, cihazınızın kilidini açmak için bir geçiş kodu girmenizi gerektiriyor. |
| Geçiş kodu çok basit. |  Geçiş kodu, 1234 veya 1111 gibi sıralı veya yinelenen sayılar içermediğinden emin olun. |
| Geçiş kodu çok kısa. | Bir geçiş kodunu daha fazla karakterle güncelleştirin veya ayarlayın. Kuruluşunuz, geçiş kodunun belirli bir uzunlukta olmasını gerektiriyor. Gerçekte seçtikleri Özellikler farklılık gösterir, ancak ihtiyaç duydukları en düşük uzunluk 4 karakterdir ve üst sınır 14 ' tür. Geçiş kodunuzu değiştirdiğinizde, Apple 'dan 6 veya daha fazla karakter girebileceğini söyleyen bir istem görürsünüz. Bu ileti, bir Apple sistem önerisine sahiptir. Kuruluşunuz yalnızca 4 veya 5 karakterden oluşan bir geçiş kodu gerektiriyorsa, 6 basamaklı bir geçiş kodu girmeniz gerekmez.|  
| Geçiş kodu yalnızca sayı içermelidir. | Yalnızca sayı içeren bir geçiş kodu ayarlayın.|
| Geçiş kodu yalnızca alfasayısal karakterlerden oluşmalıdır.| Sayı ve harf karışımı içeren bir geçiş kodu ayarlayın.|
| Geçiş kodu, alfasayısal olmayan karakterler içermelidir. | ,,, Ve `&` `$` `!` gibiözel`%`karakterlerekleyin. `#` Kuruluşunuz, başkalarının geçiş kodunu tahmin etmelerini zorlaştırmak için harf, sayı ve alfasayısal olmayan karakterlerin bir karışımını gerektirir.|
| Geçiş kodunun süresi doldu. | Yeni bir parola ayarlayın. Kuruluşunuz, parolanızın belirli bir süre geçtikten sonra değiştirilmesini gerektirir. |
| Geçiş kodu çok kısa süre önce kullanıldı.| Daha önce kullanmadığınız bir geçiş kodu seçin. Bir geçiş kodunu yeniden kullanmadan önce kuruluşunuz belirli bir süre için geçiş yapılmasını gerektirir. |
|Dokunma KIMLIĞI veya yüz KIMLIĞI kimlik doğrulaması gerekiyor. | Touch ID veya yüz KIMLIĞI ayarlayın. Kuruluşunuz, parolalar veya kredi kartı bilgileri için otomatik doldurma kullanmadan önce bu yöntemlerden biriyle kimlik doğrulaması yapmanızı gerektirir. | 

## <a name="macos-password-requirements"></a>macOS parola gereksinimleri
| `Message` | Nasıl düzeltileceğini |
|-----------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Parola gereklidir. | Bir parola ayarlayın. Kuruluşunuz cihazınızın kilidini açmak için bir parola girmenizi gerektiriyor. |
| Parola çok basit.|  Parolanızın 1234 veya 1111 gibi sıralı veya yinelenen numaralar içermediğinden emin olun. |
| Parola çok kısa. | Daha fazla karakter içeren bir parola güncelleştirin veya ayarlayın. Kuruluşunuz parolanızın belirli bir uzunlukta olmasını gerektirir.|
| Parola yalnızca sayı içermelidir. | Yalnızca sayı içeren bir parola ayarlayın.|
| Parola yalnızca alfasayısal karakterlerden oluşmalıdır. | Sayıların ve harflerin karışımını içeren bir parola ayarlayın.|
| Parola, alfasayısal olmayan karakterler içermelidir. | ,,, Ve `&` `$` `!` gibiözel`%`karakterlerekleyin. `#` Kuruluşunuz, diğerlerinin parolayı tahmin etmelerini zorlaştırmak için harf, sayı ve alfasayısal olmayan karakterlerin bir karışımını gerektirir.|
| Parolanın süresi doldu. | Yeni bir parola ayarlayın. Kuruluşunuz, parolanızın belirli bir süre geçtikten sonra değiştirilmesini gerektirir. |
| Parolanız çok kısa süre önce kullanıldı. | Daha önce kullanılmayan bir parola seçin. Bir parolayı yeniden kullanmadan önce kuruluşunuz belirli bir süre geçiş yapılmasını gerektirir. |

## <a name="android-password-requirements"></a>Android parola gereksinimleri
| `Message` | Nasıl düzeltileceğini |
|-----------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Parola gereklidir. | Bir parola veya PIN ayarlayın. Kuruluşunuz cihazınızın kilidini açmak için bir parola girmenizi gerektiriyor. |
| Parola çok basit. |  Parolanızın veya PIN 'inizin 1234 veya 1111 gibi sıralı veya yinelenen numaralar içermediğinden emin olun. |
| Parola çok kısa. | Daha fazla karakter içeren bir parola güncelleştirin veya ayarlayın. Kuruluşunuz parolanızın belirli bir uzunlukta olmasını gerektirir.|
| Parola sayı içermelidir. | Sayı içeren bir parola veya PIN kodu ayarlayın.|
| Parola harf içermelidir. | Alfabeden harfler içeren bir parola ayarlayın.|
| Parola alfasayısal karakterlerden oluşmalıdır. | Sayıların ve harflerin karışımını içeren bir parola ayarlayın.|
| Parola alfasayısal karakterler ve semboller içermelidir. | ,,, Ve `&` `$` `!` gibiharflerin`%`, sayıların ve özel karakterlerin bir karışımını içeren bir parola ayarlayın. `#` |
| Parola, biyometrik teknolojiyi kullanmalıdır.| Cihazınızı parmak izi veya yüz tanıma gibi biyometrik kimlik doğrulaması kullanacak şekilde ayarlayın.
| Parolanın süresi doldu. | Yeni bir parola ayarlayın. Kuruluşunuz, parolanızın belirli bir süre geçtikten sonra değiştirilmesini gerektirir. |
| Parolanız çok kısa süre önce kullanıldı. | Daha önce kullanılmayan bir parola seçin. Bir parolayı yeniden kullanmadan önce kuruluşunuz belirli bir süre geçiş yapılmasını gerektirir. |

## <a name="next-steps"></a>Sonraki adımlar

Cihaz parolanızı, geçiş kodunu veya PIN 'inizi oluşturmak veya değiştirmek için aşağıdaki makalelere bakın.  

- [Windows 10 cihaz parolasını ayarla](set-or-change-your-password-windows.md)  
- [İOS cihaz geçiş kodunu ayarla](set-or-change-your-passcode-ios.md)  
- [Android cihaz PIN 'ini veya parolasını ayarlama](set-your-pin-or-password-android.md)  

Bu bilgiler yardımcı olmadı mı? Destek sorumlunuza başvurun. Kişi bilgileri için [Şirket Portalı Web sitesine](https://go.microsoft.com/fwlink/?linkid=2010980) bakın.  


