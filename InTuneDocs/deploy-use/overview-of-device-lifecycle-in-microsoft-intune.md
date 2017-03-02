---
title: "MDM yaşam döngüsüne genel bakış | Microsoft Docs"
description: "Kayıt, yapılandırma ve son olarak kullanımdan kaldırma süreçleri boyunca Intune’un cihazları yönetmenize nasıl yardımcı olduğu konusunda bilgi edinin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f6051fa7-133f-4712-86a5-e5f5bc5ab3c7
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b7a066c1387a97d6100be0e6ab22d78222bf2a30
ms.openlocfilehash: 3311ba5081c4b04d72fdeb1f9a558ffc2e1b02fc
ms.lasthandoff: 02/21/2017


---

# <a name="overview-of-the-mobile-device-management-mdm-lifecycle"></a>Mobil cihaz yönetimi (MDM) yaşam döngüsüne genel bakış

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Yönettiğiniz tüm cihazlarda *yaşam döngüsü* adı verilen bir unsur vardır. Intune, kayıt işleminden başlanarak, yapılandırma ve korumadan tutun artık gerekli olmadığında cihazın kullanımdan kaldırılmasına kadarki süreçte bu yaşam döngüsünü yönetmenize yardımcı olabilir:

![Cihaz yaşam döngüsü](./media/device-lifecycle.png "Intune cihaz yaşam döngüsü")

## <a name="enroll"></a>Kaydetme
Günümüzün mobil cihaz yönetimi (MDM) stratejileri, çeşitli telefonlar ve tabletler ve bilgisayarlarla (iOS, Android, Windows ve Mac OS X) ilgilenir. Şirkete ait cihazlarda çoğunlukla söz konusu olduğu gibi cihazı yönetebilmeniz gerekiyorsa, ilk adım [cihaz kaydını ayarlamaktır](enroll-devices-in-microsoft-intune.md). Windows bilgisayarları da Intune’a (MDM) kaydederek veya [Intune istemci yazılımını yükleyerek](manage-windows-pcs-with-microsoft-intune.md) yönetebilirsiniz.

## <a name="configure"></a>Yapılandırma
Cihazlarınızın kaydını yaptırmak yalnızca ilk adımdır. Tüm bu Intune tekliflerinden yararlanmak, ayrıca cihazlarınızın güvenli ve şirket standartlarıyla uyumlu olduğundan emin olmak için birçok farklı ilke arasından seçim yapabilirsiniz. Bu ilkeler, yönetilen cihazların nasıl çalışacağını neredeyse her açıdan yapılandırmanıza imkan tanır. Örneğin, kullanıcılar şirket verilerini içeren cihazlarda parola kullanmalı mı? Bir parola gerektirebilirsiniz. Kurumsal Wi-Fi bağlantınız var mı? Otomatik olarak yapılandırabilirsiniz. Aşağıdaki türlerde yapılandırma seçenekleri sağlanır:

- [**Yapılandırma İlkeleri**](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md). Bu ilkeler, yönettiğiniz cihazların özelliklerini ve yeteneklerini yapılandırmanıza imkan sağlar. Örneğin, Windows telefonlarında parola kullanımını zorunlu tutabilir veya iPhone’larda kamera kullanımını devre dışı bırakabilirsiniz.
- [**Şirket kaynağına erişim ilkeleri**](enable-access-to-company-resources-with-microsoft-intune.md). Kullanıcılarınıza kişisel cihazlarını kullanarak işlerine erişme izni verirseniz karşınıza bazı zorluklar çıkarabilir. Örneğin, şirket e-postasına erişmesi gereken tüm cihazların doğru yapılandırıldığından nasıl emin olursunuz? Kullanıcıların karmaşık ayarları bilmek zorunda kalmadan, VPN bağlantısıyla şirket ağına erişebilmelerini nasıl sağlayabilirsiniz? Intune, yönettiğiniz cihazları ortak şirket kaynaklarına erişecek şekilde otomatik olarak yapılandırarak bu yükü azaltmaya yardımcı olabilir.
- [**Windows bilgisayarı yönetim ilkeleri (Intune istemci yazılımıyla)**](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md). Windows bilgisayarlarını Intune’a kaydetmek size en kapsamlı cihaz yönetim özelliklerini getirirken, Intune Windows bilgisayarlarının yönetimini desteklemeye Intune istemci yazılımıyla devam eder. Bilgisayarlarla gerçekleştirebileceğiniz görevlerden bazıları hakkında bilgi almanız gerekiyorsa buradan başlayın.

## <a name="protect"></a>Koruma
Modern BT dünyasında cihazları yetkisiz erişime karşı korumak, yerine getireceğiniz en önemli görevlerden biridir. Cihaz yaşam döngüsünün **Yapılandırma** adımındaki öğelere ek olarak, Intune yönettiğiniz cihazları yetkisiz erişime veya kötü amaçlı saldırılara karşı korumaya yardımcı olmak için şu özellikleri sağlar:
- [**Çok faktörlü kimlik doğrulaması**](protect-your-devices-with-microsoft-intune.md). Kullanıcı oturum açma işlemlerine fazladan bir kimlik doğrulama katmanı daha eklemek cihazların daha da güvenli olmasına yardım edebilir. Birçok cihaz çok faktörlü kimlik doğrulamasını destekler. Bu, kullanıcılar erişim kazanmadan önce telefonla arama veya kısa mesaj gibi ikinci bir kimlik doğrulama düzeyini gerektirir.
- [**Microsoft Passport ayarları**](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md). Microsoft Passport, kullanıcıların parolaya gerek kalmadan parmak izi gibi bir *hareket* veya Windows Hello kullanarak oturum açmalarına olanak tanıyan alternatif bir oturum açma yöntemidir.
- [**Windows bilgisayarlarını korumaya yönelik ilkeler (Intune istemci yazılımıyla)**](policies-to-protect-windows-pcs-in-microsoft-intune.md). Windows bilgisayarlarını Intune istemci yazılımını kullanarak yönetirken, yönettiğiniz bilgisayarlarda Endpoint Protection’ın, yazılım güncelleştirmelerinin ve Windows Güvenlik Duvarı’nın ayarlarını denetlemenize olanak tanıyan ilkeler sağlanır.

## <a name="retire"></a>Devre dışı bırakma
Cihaz kaybolduğunda veya çalındığında, değiştirilmesi gerektiğinde veya kullanıcılar başka bir pozisyona geçtiğinde, çoğunlukla cihazı [devre dışı bırakmanın veya temizlemenin](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md) zamanı gelmiştir. Cihazı sıfırlamak, yönetimden kaldırmak veya üzerindeki şirket verilerini temizlemek dahil olmak üzere birçok farklı yolla bunu yapabilirsiniz.

