---
# required metadata

title: Cihazları koruma | Microsoft Intune
description:
keywords:
author: Robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 71e0cbf3-2bfb-412e-8a12-8503df08b4cf

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Cihazları Microsoft Intune ile koruma
Cihazlarınızı Intune ile yönettikten sonra, yetkisiz erişim ve diğer tehditlere karşı korunmalarını sağlamak isteyeceksiniz. Aşağıda, Intune’un bunları gerçekleştirmenize yardımcı olacak bazı özellikleri verilmiştir.

> [!TIP]
> Bu konuda, Intune’un cihazlarınızı güvenli hale getirmeye yardımcı olacak tüm yöntemleri yer almamaktadır. Örneğin, cihazlarınız için, parolalar, şifreleme ayarları ve Bluetooth ve cihaz kamerası gibi donanım özellikleri yapılandırmak üzere Intune ilkelerini kullanabilirsiniz. Bu ayarlar hakkında daha fazla bilgi almak için, bkz. [Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

## Kullanıcılar kilitlenen cihazlarına erişemediğinde geçiş kodlarını sıfırlama
Mobil cihazlarda şirket verilerini korumanın ilk adımı cihazı kullanmak için bir geçiş kodu istenmesi olduğundan, bazen bir [geçiş kodunu sıfırlamanız](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) ya da geçiş kodunu kaldırarak veya uzaktan geçici geçiş kodu ayarlayarak bir çalışana kodu sıfırlaması için yardımcı olmanız gerekir. Ayrıca, kaybedilirse veya çalınırsa [bir cihazı uzaktan kilitleyebilirsiniz.](use-remote-lock-and-passcode-reset-in-microsoft-intune.md)

## Windows cihazlar için ek bir koruma katmanı ekleme
[Multi-factor authentication (MFA)](protect-windows-devices-with-multi-factor-authentication.md), ağdaki Windows ve Windows Phone cihazı kullanıcılarının kimliklerini doğrulamak için daha güvenli bir yoludur.  MFA ile kullanıcıların kimliklerini kullanıcı adı ve parolanın ötesinde, bir telefon konuşması veya kısa mesaj üzerinden doğrulaması gerekir.

## Windows cihazlarda Microsoft Passport ayarlarını denetleme
Intune, bir parola, akıllı kart ya da sanal akıllı kartı değiştirmek için Windows 10 ve üzerinde Active Directory veya bir Azure Active Directory hesabı kullanan alternatif bir oturum açma yöntemi olan [İş İçin Microsoft Passport](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md)’u tümleştirmenize olanak sağlar.

## Intune istemcisiyle yönetilen Windows bilgisayarları koruma
Intune, kaydolmadığınız ancak Intune bilgisayar istemci yazılımıyla yönettiğiniz Windows bilgisayarlar için güvenlik ilkelerini desteklemeye devam etmektedir. Bu ilkelerin, Windows bilgisayarlarınızı güvenli hale getirmenize nasıl yardımcı olabileceğini öğrenmek için, bkz. [Intune istemci yazılımını çalıştıran Windows bilgisayarları korumanıza yardımcı olması için ilkeler kullanma](policies-to-protect-windows-pcs-in-microsoft-intune.md).


<!--HONumber=May16_HO2-->


