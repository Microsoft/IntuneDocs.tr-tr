---
title: Cihaz uyumluluk ilkeleri | Microsoft Intune
description: "Bu konu başlığı altında, cihaz uyumluluk ilkelerinin ne olduğunu ve nasıl çalıştığını anlamanız için gereken kavramlar açıklanır."
keywords: 
author: karthikaraman
manager: jeffgilb
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0775107a-6662-41c8-9404-be14bbb599f3
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c72c8e1a764af73ba4d421ca6637ee91ab7bca0a
ms.openlocfilehash: f34ff402ae1012a471219647e94bc1f5225a6f07


---

# Microsoft Intune’da cihaz uyumluluk ilkeleri
## Uyumluluk ilkesi nedir?
Şirket verilerini korumak için, şirket uygulamalarına ve verilerine erişmek için kullanılan cihazların bazı kurallara (cihaza erişim için PIN kullanma ve cihazda depolanan verileri şifreleme gibi) uyduğundan emin olmanız gerekir. Bu tür bir kurallar kümesine uyumluluk ilkesi adı verilir.

## Uyumluluk ilkelerini nasıl kullanmalıyım?
E-postaya ve diğer hizmetlere yalnızca uyumluluk ilkesi kurallarıyla uyumlu olan cihazların erişmesine izin vermek için uyumluluk ilkelerini koşullu erişim ilkeleri ile kullanabilirsiniz. İki ilkenin nasıl birlikte kullanılabileceğini anlamak için [E-postaya ve O365 hizmetlerine erişimi kısıtlama](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) makalesini okuyun.

Uyumluluk ilkelerini, koşullu erişimden bağımsız olarak da kullanabilirsiniz. Bağımsız olarak kullanıldığında, hedeflenen cihazlar değerlendirilir ve uyumluluk durumları raporlanır. Örneğin, kaç cihazın şifrelenmediğini ya da hangi cihazların yazılım kilidinin kırıldığını veya kökünün belirtildiğini raporlamak isteyebilirsiniz. Öte yandan, bunlar bağımsız kullanıldığında, şirket kaynaklarına yönelik erişim kısıtlaması olmaz.

Uyumluluk ilkelerini kullanıcılara siz dağıtırsınız. Bir uyumluluk ilkesi kullanıcıya dağıtıldığında, kullanıcının cihazlarında uyumluluk denetimi yapılır.

Aşağıdaki tabloda, ilke koşullu erişim ilkesi ile kullanıldığında, uyumluluk ilkeleri tarafından desteklenen cihaz türleri ve uyumsuz ayarların nasıl yönetildiği listelenmektedir.

--------------

|İlke Ayarı| Windows 8.1 ve üzeri| Windows Phone 8.1 ve üzeri| iOS 6.0 ve üzeri|Android 4.0 ve üzeri<br/>Samsung KNOX Standard 4.0 ve üzeri|
|-----|----|----|----|
|**PIN veya Parola Yapılandırması** |Çözümlendi|Çözümlendi|Çözümlendi|Karantinaya Alındı|
|**Cihaz şifrelemesi**|Yok|Çözümlendi|Çözümlendi (PIN ayarlanarak)|Karantinaya Alındı|
|**Güvenliği kırılmış veya kökü belirtilen cihaz**|Yok|Yok|Karantinaya Alındı (ayar değil)|Karantinaya Alındı (ayar değil)|
|**E-posta profili**|Yok|Yok|Karantinaya Alındı|Yok|
|**En düşük işletim sistemi sürümü**|Karantinaya Alındı|Karantinaya Alındı|Karantinaya Alındı|Karantinaya Alındı|
|**En yüksek işletim sistemi sürümü**|Karantinaya Alındı| Karantinaya Alındı| Karantinaya Alındı| Karantinaya Alındı|
|**Windows durum kanıtlama**|Windows 10 ve Windows 10 Mobile Karantinaya Alındı durumundadır.<br /><br />Ayar Windows 8. 1 için geçerli değildir|Yok|Yok|Yok|
--------------
**Çözümlendi** = Uyumluluk cihazın işletim sistemi tarafından zorlanır (örneğin, kullanıcı bir PIN ayarlamaya zorlanır).  Ayarın uyumsuz olması durumu hiçbir zaman söz konusu değildir.

**Karantinaya Alındı** = Cihazın işletim sistemi uyumluluğu zorlamaz (örneğin, Android cihazlar kullanıcıyı cihazı şifrelemeye zorlamaz). Cihazlar uyumsuz olduğunda, aşağıdaki işlemler yapılır:

-   Kullanıcı bir koşullu erişim ilkesi tarafından hedefleniyorsa cihaz engellenir.

-   Şirket portalı, tüm uyumluluk sorunları hakkında kullanıcıya bildirim gönderir.

## Sonraki adımlar
[Cihaz uyumluluğu ilkesi oluşturma](create-a-device-compliance-policy-in-microsoft-intune.md)

[Cihaz uyumluluğu ilkesini dağıtma ve izleme](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md)

### Ayrıca bkz.
[E-posta ve O365 hizmetlerine erişimi kısıtlama](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)



<!--HONumber=Jul16_HO3-->


