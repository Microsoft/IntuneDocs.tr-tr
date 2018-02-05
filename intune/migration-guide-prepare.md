---
title: "Intune'u mobil cihaz yönetimi için hazırlama"
description: "Intune’a geçmeden önce iş ve teknik gereksinimlerinizi değerlendirin."
keywords: 
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 58591442-6606-4f39-a06b-f17a1f25af25
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: 93c17ff0343c4475bbc665ff2418e1e7860894d5
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
---
# <a name="phase-1-prepare-intune-for-mobile-device-management-mdm"></a>1. Aşama: Intune’u mobil cihaz yönetimi (MDM) için hazırlama

Intune'u ayarlama ayrıntılarına girmeden önce, kuruluşunuzun mobil cihaz yönetimi gereksinimlerini gözden geçirelim. Kritik kullanıcı gruplarını tanımlamak için geçerli MDM sağlayıcınızdaki etkin kullanıcıların raporlarını çalıştırmak faydalı olabilir. Daha sonra [MDM gereksinimlerini değerlendirme ](migration-guide-prepare.md#assess-mdm-requirements) bölümündeki soruları cevaplamaya başlayabilirsiniz.

## <a name="assess-mdm-requirements"></a>MDM gereksinimlerini değerlendirme

### <a name="what-kinds-of-devices-do-you-need-to-manage"></a>Ne tür cihazlar yönetmeniz gerekiyor?

-   Hangi [platformları](supported-devices-browsers.md) desteklemeniz gerekiyor?

-   Desteklemeniz gereken cihazlar şirkete mi ait yoksa kişisel mi?

-   Ne tür bir bağlantı kullanıyorsunuz? Wi-Fi, hücresel, VPN?

### <a name="what-do-your-users-need-to-do-on-managed-devices"></a>Kullanıcılarınızın yönetilen cihazlarda ne yapması gerekiyor?

-   Son kullanıcılarınıza uygulama sağlamanız gerekiyor mu?

-   Özel iş kolu uygulamaları kullanıyor musunuz? Yoksa yalnızca ortak mağaza uygulamalarına mı ihtiyacınız var?

-   E-posta hesapları sağlamanız gerekiyor mu?

### <a name="what-kinds-of-users"></a>Ne tür kullanıcılar var?

-   Tek bir cihazın kaç kullanıcısı olacak?

-   Hangi kullanım koşullarına ihtiyacınız var?

    -   Hukuk departmanınızın bu konuya erkenden dahil olmasını sağlayın.
    -   Ne tür bir yerelleştirme gerekli?

-   Kullanıcılar genel olarak teknoloji ve BT konusunda bilgi sahibi mi?

### <a name="what-is-your-device-security-policy"></a>Cihaz güvenlik ilkeniz nedir?

-   Cihaz düzeyinde şifreleme gerekiyor mu?

-   Mevcut cihaz geçiş kodu/pin kodu uzunluklarınız nedir?

-   Cihaz özelliklerini devre dışı bırakmanız veya belirli cihaz davranışlarını kısıtlamanız gerekiyor mu? Cihaz yapılandırma profilleri ile çeşitli platforma özgü ayarları kontrol edebilirsiniz, örneğin:
      - Kamerayı devre dışı bırakma
      - Tek uygulama moduna kilitleme<br/>

-   Hangi kimlik doğrulaması türlerini desteklemeniz gerekli? Sertifika tabanlı kimlik doğrulaması gerekiyorsa hangi tür sertifikaların sağlanması gerekir?
  - Intune, kaydedilen cihazlar için kaynak erişim profilleri ile sertifikalar sağlayabilir.
    -   Ne tür bir Ortak Anahtar Altyapısı (PKI) desteklemeniz gerekli?
<br></br>
-   Cihaz veya uygulama düzeyinde Sanal Özel Ağ (VPN) desteklemeniz gerekiyor mu?

    -   Intune, üçüncü taraf VPN sağlayıcıları için VPN yapılandırmaları sağlayabilir.
<br/><br/>
-   Kapalı kalma süresini önlemek üzere belirli gereksinimler için geçici özel durumlar yapılabilir mi? Yoksa erişimi olan cihazların her zaman tüm güvenlik gereksinimlerine uygun olması mı gerekir?

## <a name="next-steps"></a>Sonraki adımlar
Kuruluşların mobil cihaz yönetimi gereksinimlerini nasıl değerlendirdiğini görmek üzere farklı sektörlerden bu [örnek olay incelemelerini](https://customers.microsoft.com/story/mwh-global-now-part-of-stantec-secures-mobile-devices-with-intune) gözden geçirin.

[Temel Intune kurulumuna](migration-guide-setup.md) göz atın.
