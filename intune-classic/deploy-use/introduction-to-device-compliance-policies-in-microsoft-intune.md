---
title: Cihaz uyumluluk ilkeleri | Microsoft Docs
description: "Bu konu başlığı altında, cihaz uyumluluk ilkelerinin anlamı ve nasıl çalıştıkları açıklanır."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0775107a-6662-41c8-9404-be14bbb599f3
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: a14c9d7f0fcf6a99007380bb01f5f7bc94f0b413
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---

# <a name="device-compliance-policies-in-microsoft-intune"></a>Microsoft Intune’da cihaz uyumluluk ilkeleri

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="what-is-a-compliance-policy"></a>Uyumluluk ilkesi nedir?
Şirket verilerini korumaya yardımcı olmak için şirket uygulamalarına ve verilerine erişmek için kullanılan cihazların belirli kurallarla uyumlu olduğundan emin olmanız gerekir. Bu kurallar, cihazlara ve cihazlarda depolanan şifreleme verilerine erişmek için bir PIN kullanmayı içerebilir. Bu tür bir kurallar kümesine uyumluluk ilkesi adı verilir.

## <a name="how-should-i-use-compliance-policies"></a>Uyumluluk ilkelerini nasıl kullanmalıyım?
E-postaya ve diğer hizmetlere yalnızca uyumluluk ilkesi kurallarıyla uyumlu olan cihazların erişmesine izin vermek için uyumluluk ilkelerini koşullu erişim ilkeleri ile kullanabilirsiniz. İki ilkenin nasıl birlikte kullanılabileceğini anlamak için [E-postaya ve O365 hizmetlerine erişimi kısıtlama](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) makalesini okuyun.

Uyumluluk ilkelerini, koşullu erişimden bağımsız olarak da kullanabilirsiniz. Uyumluluk ilkelerini bağımsız olarak kullandığınızda, hedeflenen cihazlar değerlendirilir ve uyumluluk durumları raporlanır. Örneğin, kaç cihazın şifrelenmediğini ya da hangi cihazların yazılım kilidinin kırıldığını veya kökünün belirtildiğini raporlamak isteyebilirsiniz. Ancak uyumluluk ilkelerini bağımsız olarak kullandığınızda, şirket kaynaklarına yönelik erişim kısıtlaması olmaz.

Uyumluluk ilkelerini kullanıcılara siz dağıtırsınız. Bir uyumluluk ilkesi kullanıcıya dağıtıldığında, kullanıcının cihazlarında uyumluluk denetimi yapılır.
İlke dağıtıldıktan sonra mobil cihazların ilke almasının ne kadar sürdüğü hakkında bilgi edinmek için bkz. [Cihazlarınızda ayarları ve özellikleri yönetme](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies#frequently-asked-questions-about-intune-policies).

Aşağıdaki tabloda, uyumluluk ilkeleri tarafından desteklenen cihaz türleri listelenmiştir. Tabloda ayrıca bir uyumluluk ilkesi koşullu erişim ilkesi ile kullanıldığında uyumlu olmayan ayarların nasıl yönetildiği açıklanır.

-----------------------------

|İlke ayarı| Windows 8.1 ve üzeri| Windows Phone 8.1 ve üzeri| iOS 8.0 ve üzeri|Android 4.0 ve üzeri<br/>Samsung KNOX Standard 4.0 ve üzeri|
|-----|----|----|----|----|
|**PIN veya Parola yapılandırması** |Çözümlendi|Çözümlendi|Çözümlendi|Karantinaya Alındı|
|**Cihaz şifrelemesi**|Uygulanamaz|Çözümlendi|Çözümlendi (PIN ayarlanarak)|Karantinaya Alındı|
|**Jailbreak uygulanmış veya kök erişim izni verilmiş cihaz**|Uygulanamaz|Uygulanamaz|Karantinaya Alındı (ayar değil)|Karantinaya Alındı (ayar değil)|
|**E-posta profili**|Uygulanamaz|Uygulanamaz|Karantinaya Alındı|Uygulanamaz|
|**En düşük işletim sistemi sürümü**|Karantinaya Alındı|Karantinaya Alındı|Karantinaya Alındı|Karantinaya Alındı|
|**En yüksek işletim sistemi sürümü**|Karantinaya Alındı|Karantinaya Alındı|Karantinaya Alındı|Karantinaya Alındı|
|**Windows durum kanıtlama**|Karantinaya alındı: Windows 10 ve Windows 10 Mobile<br /><br />Uygulanamaz: Windows 8.1|Uygulanamaz|Uygulanamaz|Uygulanamaz|

------------------------------

**Düzeltilen** = Cihazın işletim sistemi, uyumluluğu mecbur kılar. (Örneğin, kullanıcı bir PIN ayarlamaya zorlanır.)

**Karantinaya alındı** = Cihazın işletim sistemi uyumluluğu mecbur kılmaz. (Örneğin, Android cihazlar kullanıcıyı cihazı şifrelemeye zorlamaz.) Cihazlar uyumsuz olduğunda, aşağıdaki işlemler yapılır:

-   Kullanıcı için geçerli bir koşullu erişim ilkesi varsa cihaz engellenir.

-   Şirket portalı, tüm uyumluluk sorunları hakkında kullanıcıya bildirim gönderir.

## <a name="next-steps"></a>Sonraki adımlar
[Cihaz uyumluluğu ilkesi oluşturma](create-a-device-compliance-policy-in-microsoft-intune.md)

[Cihaz uyumluluğu ilkesini dağıtma ve izleme](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md)

### <a name="see-also"></a>Ayrıca bkz.
[E-posta ve O365 hizmetlerine erişimi kısıtlama](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)

