---
# required metadata

title: Cihaz uyumluluk ilkeleri | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 0775107a-6662-41c8-9404-be14bbb599f3

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune’da cihaz uyumluluk ilkeleri
## Uyumluluk ilkesi nedir?
Şirket verilerini korumak için, şirket uygulamalarına ve verilerine erişmek için kullanılan cihazların bazı kurallara (cihaza erişim için PIN kullanma ve cihazda depolanan verileri şifreleme gibi) uyduğundan emin olmanız gerekir. Bu tür bir kurallar kümesine uyumluluk ilkesi adı verilir.

## Uyumluluk ilkelerini nasıl kullanmalıyım?
Uyumluluk ilkelerini koşullu erişim ilkeleriyle birlikte kullanarak, uyumluluk ilkesi kurallarına uyan cihazlara erişimi kısıtlayabilirsiniz. İki ilkenin nasıl birlikte kullanılabileceğini anlamak için [E-postaya ve O365 hizmetlerine erişimi kısıtlama](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) makalesini okuyun.

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


<!--HONumber=May16_HO2-->


