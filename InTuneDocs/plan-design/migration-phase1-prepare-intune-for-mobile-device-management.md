---
title: "Intune’u mobil cihaz yönetimi için hazırlama| Microsoft Docs"
description: "Bu makalenin amacı, Intune&quot;a geçiş yapmadan önce iş ve teknik gereksinimlerini değerlendirmeleri için okuyuculara yardımcı olmaktır."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 58591442-6606-4f39-a06b-f17a1f25af25
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab6d9b6b296fb4e1fb0aaa9496fede28976728dc
ms.openlocfilehash: 4bf9bd15f3f22e0609c4f56f5651454a62dbb7a8
ms.lasthandoff: 04/14/2017


---

# <a name="phase-1-prepare-intune-for-mobile-device-management-mdm"></a>1. Aşama: Intune’u mobil cihaz yönetimi (MDM) için hazırlama

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Intune'u ayarlama ayrıntılarına girmeden önce, kuruluşunuzun mobil cihaz yönetimi gereksinimlerini gözden geçirelim. Kritik kullanıcı gruplarını tanımlamak için geçerli MDM sağlayıcınızdaki etkin kullanıcıların raporlarını hazırlamak faydalı olabilir, [MDM gereksinimlerini değerlendirme bölümü](https://docs.microsoft.com/intune/plan-design/migration-phase1-prepare-intune-for-mobile-device-management#assess-mdm-requirements) altındaki soruları ele almaya başlayabilirsiniz.

## <a name="assess-mdm-requirements"></a>MDM gereksinimlerini değerlendirme

### <a name="what-kinds-of-devices-do-you-need-to-manage"></a>Ne tür cihazlar yönetmeniz gerekiyor?

-   Hangi [platformları](https://docs.microsoft.com/intune/get-started/supported-mobile-devices-and-computers) desteklemeniz gerekiyor?

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

[1. Aşama: Temel Kurulum](https://docs.microsoft.com/intune/plan-design/migration-phase1-basic-setup)

