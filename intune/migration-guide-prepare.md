---
title: "Intune'u mobil cihaz yönetimi için hazırlama"
description: "Bu makalenin amacı, Intune'a geçiş yapmadan önce iş ve teknik gereksinimlerini değerlendirmeleri için okuyuculara yardımcı olmaktır."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 58591442-6606-4f39-a06b-f17a1f25af25
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 65e3bb4b6a4e6e8dcfa1dd16738ae47758f4fb9b
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="phase-1-prepare-intune-for-mobile-device-management-mdm"></a>1. Aşama: Intune’u mobil cihaz yönetimi (MDM) için hazırlama

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

Intune'u ayarlama ayrıntılarına girmeden önce, kuruluşunuzun mobil cihaz yönetimi gereksinimlerini gözden geçirelim. Kritik kullanıcı gruplarını tanımlamak için geçerli MDM sağlayıcınızdaki etkin kullanıcıların raporlarını hazırlamak faydalı olabilir, [MDM gereksinimlerini değerlendirme bölümü](migration-guide-prepare.md#assess-mdm-requirements) altındaki soruları ele almaya başlayabilirsiniz.

## <a name="assess-mdm-requirements"></a>MDM gereksinimlerini değerlendirme

### <a name="what-kinds-of-devices-do-you-need-to-manage"></a>Ne tür cihazlar yönetmeniz gerekiyor?

-   Hangi [platformları](/intune-classic/get-started/supported-mobile-devices-and-computers) desteklemeniz gerekiyor?

-   Desteklemeniz gereken cihazlar şirkete mi ait yoksa KCG cihazları mı?

-   Ne tür bir bağlantı kullanılır? Wi-Fi, hücresel, VPN?

### <a name="what-do-your-users-need-to-do-on-managed-devices"></a>Kullanıcılarınızın yönetilen cihazlarda ne yapması gerekiyor?

-   Son kullanıcılarınıza uygulama sağlamanız gerekiyor mu?

-   Özel iş kolu uygulamaları kullanıyor musunuz? Yoksa yalnızca ortak mağaza uygulamalarına mı ihtiyacınız var?

-   E-posta hesapları sağlamanız gerekiyor mu?

### <a name="what-kinds-of-users"></a>Ne tür kullanıcılar var?

-   Tek bir cihazın kaç kullanıcısı olacak?

-   Size hangi Kullanım Koşulları gerekli?

    -   Hukuk departmanınızın bu konuya erkenden dahil olmasını sağlayın.

    -   Ne tür bir yerelleştirme gerekli?

-   Kullanıcılar genel olarak teknoloji ve BT konusunda bilgi sahibi mi?

### <a name="what-is-your-device-security-policy"></a>Cihaz güvenlik ilkeniz nedir?

-   Cihaz düzeyinde şifreleme gerekiyor mu?

-   Cihaz parolası/PIN kodu uzunlukları?

-   Cihaz özelliklerini devre dışı bırakmanız veya belirli cihaz davranışlarını kısıtlamanız gerekiyor mu?

    -   Cihaz yapılandırma profilleri ile çeşitli platforma özgü ayarları kontrol edebilirsiniz, örneğin: Kamerayı devre dışı bırakma, tek uygulama moduna kilitleme.
<br></br>
-   Hangi kimlik doğrulaması türlerini desteklemeniz gerekli?

    -   Sertifika tabanlı kimlik doğrulaması gerekiyorsa, hangi tür sertifikaların sağlanması gerekir?

        -   Intune, kaydedilen cihazlar için kaynak erişim profilleri ile sertifikalar sağlayabilir.
<br></br>
    -   Ne tür bir Ortak Anahtar Altyapısı (PKI) desteklemeniz gerekli?
<br></br>
-   Cihaz veya uygulama düzeyinde Sanal Özel Ağ (VPN) desteklemeniz gerekiyor mu?

    -   Intune, üçüncü taraf VPN sağlayıcıları için VPN yapılandırmaları sağlayabilir.
<br></br>
-   Kapalı kalma süresini önlemek üzere belirli gereksinimler için geçici özel durumlar yapılabilir mi? Yoksa erişimi olan cihazların her zaman tüm güvenlik gereksinimlerine uygun olması mı gerekir?

## <a name="additional-information"></a>Ek bilgiler

-   Daha ayrıntılı örnekler için kuruluşların mobil cihaz yönetimi gereksinimlerini nasıl değerlendirdiğini görmek üzere farklı sektörlerden bu [örnek olay incelemelerini](https://customers.microsoft.com/story/mwh-global-now-part-of-stantec-secures-mobile-devices-with-intune) gözden geçirin.

## <a name="next-steps"></a>Sonraki adımlar

[Temel Kurulum](migration-guide-setup.md)
