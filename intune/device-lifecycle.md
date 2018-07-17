---
title: Microsoft Intune MDM yaşam döngüsüne genel bakış
description: Kayıt, yapılandırma ve son olarak kullanımdan kaldırma süreçleri boyunca Intune’un cihazları yönetmenize nasıl yardımcı olduğu konusunda bilgi edinin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 3/2/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: c2e4cf0e77a63f0a8a3049e66ec16e563e410873
ms.sourcegitcommit: 2198a39ae48beca5fc74316976bc3fc9db363659
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38225214"
---
# <a name="overview-of-the-microsoft-intune-mobile-device-management-mdm-lifecycle"></a>Microsoft Intune mobil cihaz yönetimi (MDM) yaşam döngüsüne genel bakış

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

Yönettiğiniz tüm cihazlarda *yaşam döngüsü* adı verilen bir unsur vardır. Intune, kayıt işleminden başlanarak, yapılandırma ve korumadan tutun artık gerekli olmadığında cihazın kullanımdan kaldırılmasına kadarki süreçte bu yaşam döngüsünü yönetmenize yardımcı olabilir.

![Cihaz yaşam döngüsü](./media/device-lifecycle.png "Intune cihaz yaşam döngüsü")

## <a name="enroll"></a>Kaydetme
Günümüzün mobil cihaz yönetimi (MDM) stratejileri, çeşitli telefonlar ve tabletler ve bilgisayarlarla (iOS, Android, Windows ve Mac OS X) ilgilenir. Şirkete ait cihazlarda çoğu kez söz konusu olduğu gibi cihazı yönetebilmeniz gerekiyorsa, ilk adım [cihaz kaydını ayarlamaktır](device-enrollment.md) ([Klasik portal](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)). Windows bilgisayarları da Intune’a (MDM) kaydederek veya [Intune istemci yazılımını yükleyerek](/intune-classic/deploy-use/manage-windows-pcs-with-microsoft-intune) yönetebilirsiniz.

## <a name="configure"></a>Yapılandırma
Cihazlarınızın kaydını yaptırmak yalnızca ilk adımdır. Tüm bu Intune tekliflerinden yararlanmak, ayrıca cihazlarınızın güvenli ve şirket standartlarıyla uyumlu olduğundan emin olmak için birçok farklı ilke arasından seçim yapabilirsiniz. Bu ilkeler, yönetilen cihazların nasıl çalışacağını neredeyse her açıdan yapılandırmanıza imkan tanır. Örneğin, kullanıcılar şirket verilerini içeren cihazlarda parola kullanmalı mı? Bir parola gerektirebilirsiniz. Kurumsal Wi-Fi bağlantınız var mı? Otomatik olarak yapılandırabilirsiniz. Aşağıdaki türlerde yapılandırma seçenekleri sağlanır:

- [**Cihaz yapılandırması**](device-profiles.md) ([Klasik portal](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies)). Bu ilkeler, yönettiğiniz cihazların özelliklerini ve yeteneklerini yapılandırmanıza imkan sağlar. Örneğin, Windows telefonlarında parola kullanımını zorunlu tutabilir veya iPhone’larda kamera kullanımını devre dışı bırakabilirsiniz.
- [**Şirket kaynak erişimi**](device-profiles.md) ([Klasik portal](/intune-classic/deploy-use/enable-access-to-company-resources-with-microsoft-intune)). Kullanıcılarınıza kişisel cihazlarını kullanarak işlerine erişme izni verirseniz karşınıza bazı zorluklar çıkarabilir. Örneğin, şirket e-postasına erişmesi gereken tüm cihazların doğru yapılandırıldığından nasıl emin olursunuz? Kullanıcıların karmaşık ayarları bilmek zorunda kalmadan, VPN bağlantısıyla şirket ağına erişebilmelerini nasıl sağlayabilirsiniz? Intune, yönettiğiniz cihazları ortak şirket kaynaklarına erişecek şekilde otomatik olarak yapılandırarak bu yükü azaltmaya yardımcı olabilir.
- [**Windows bilgisayarı yönetim ilkeleri (Intune istemci yazılımıyla)**](/intune-classic/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client). Windows bilgisayarlarını Intune’a kaydetmek size en kapsamlı cihaz yönetim özelliklerini getirirken, Intune Windows bilgisayarlarının yönetimini desteklemeye Intune istemci yazılımıyla devam eder. Bilgisayarlarla gerçekleştirebileceğiniz görevlerden bazıları hakkında bilgi almanız gerekiyorsa buradan başlayın.

## <a name="protect"></a>Koruma
Modern BT dünyasında cihazları yetkisiz erişime karşı korumak, en önemli görevlerinizden biridir. Cihaz yaşam döngüsünün **Yapılandırma** adımındaki öğelere ek olarak, Intune yönettiğiniz cihazları yetkisiz erişime veya kötü amaçlı saldırılara karşı korumaya yardımcı olmak için şu özellikleri sağlar:
- [**Çok faktörlü kimlik doğrulaması**](/intune-classic/deploy-use/protect-your-devices-with-microsoft-intune). Kullanıcı oturum açma işlemlerine fazladan bir kimlik doğrulama katmanı daha eklemek cihazların daha da güvenli olmasına yardım edebilir. Birçok cihaz çok faktörlü kimlik doğrulamasını destekler. Bu, kullanıcılar erişim kazanmadan önce telefonla arama veya kısa mesaj gibi ikinci bir kimlik doğrulama düzeyini gerektirir.
- [**İş İçin Windows Hello ayarları**](windows-hello.md) ([Klasik portal](/intune-classic/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune)). İş İçin Microsoft Hello, kullanıcıların parolaya gerek kalmadan parmak izi gibi bir *hareket* veya Windows Hello kullanarak oturum açmalarına olanak tanıyan alternatif bir oturum açma yöntemidir.
- [**Windows bilgisayarlarını korumaya yönelik ilkeler (Intune istemci yazılımıyla)**](/intune-classic/deploy-use/policies-to-protect-windows-pcs-in-microsoft-intune). Windows bilgisayarlarını Intune istemci yazılımını kullanarak yönetirken, yönettiğiniz bilgisayarlarda Endpoint Protection’ın, yazılım güncelleştirmelerinin ve Windows Güvenlik Duvarı’nın ayarlarını denetlemenize olanak tanıyan ilkeler sağlanır.

## <a name="retire"></a>Devre dışı bırakma
Cihaz kaybolduğunda veya çalındığında, değiştirilmesi gerektiğinde veya kullanıcılar başka bir pozisyona geçtiğinde, çoğunlukla cihazı [devre dışı bırakmanın veya temizlemenin](device-management.md) ([Klasik portal](/intune-classic/deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune)) zamanı gelmiştir. Cihazı sıfırlamak, yönetimden kaldırmak veya üzerindeki şirket verilerini temizlemek dahil olmak üzere birçok farklı yolla bunu yapabilirsiniz.
