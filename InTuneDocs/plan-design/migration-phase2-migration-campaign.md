---
title: "Intune geçiş kampanyası başlatma | Microsoft Docs"
description: "Bu makalenin amacı, bir geçiş kampanyası başlatma hakkında rehberlik sağlamaktır."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f781b029-50f2-46ee-8ff7-03b4a6719e80
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab5aa4e12d951d818c5afb4e1ac5e866b05733fb
ms.openlocfilehash: 506b0360fb7b1f28c4c9ad3265e24c0ffa0b065d
ms.lasthandoff: 03/27/2017


---

# <a name="phase-2-migration-campaign"></a>2. Aşama: Geçiş Kampanyası

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Kuruluşların, kendi gereksinimlerine en uygun geçiş yaklaşımını benimsemeleri ve uygulama taktiklerini özel gereksinimlerine göre ayarlamaları gerekir. Bu rehberin geri kalanında kullanıcınızın cihazlarını Intune'a kaydetme amacına ulaşmanız için gereken araçlar sağlanacaktır.

## <a name="keys-to-a-successful-migration"></a>Başarılı bir geçişin önemli noktaları

Bir üçüncü taraf MDM sağlayıcısından Intune’a geçiş sırasında öğrenilen önemli dersler şunlardır:

-   İletişim, son kullanıcının devre dışı kalma süresini en aza indirmek ve memnuniyet için büyük önem taşır.

-   Belirli ve somut geçiş yönergeleriniz olduğundan emin olun.

-   Intune’a kayıt öncesinde tüm yönetilen cihazların mevcut MDM sağlayıcısındaki kayıtları silinmelidir.

-   Son kullanıcılara cihazlarının kaydını nasıl kaldıracakları konusunda mevcut MDM sağlayıcısından yönergeler sağlayın.

-   Aşamalı bir yaklaşım kullanın. Küçük bir pilot kullanıcı grubu kullanın ve tam ölçekli dağıtıma ulaşana kadar aşamalı olarak daha fazla kullanıcı grubu ekleyin.

-   Her döngünün Yardım masası yükünü ve kayıt başarısını izleyin. Her grup için başarı ölçütlerinin bir sonrakine geçmeden önce değerlendirilmesini sağlamak için zaman çizelgesinde süre bırakın. Pilot dağıtımınız aşağıdakileri doğrulamalıdır:

    -   Kayıt başarı ve başarısızlık hızları beklentiler dahilindedir.

    -   Kullanıcı üretkenliği:

        -   VPN, Wi-Fi, e-posta ve sertifikalar gibi şirket kaynakları çalışır durumdadır.

        -   Sağlanan Uygulamalara erişilebilir.

    -   Veri güvenliği:

        -   Uyumluluk raporlaması

        -   Mobil uygulama korumaları zorlanır

-   Geçişin ilk aşamasından memnun kaldığınızda, Geçiş Döngüsünü (Aşağıda Tipik Geçiş Döngüsü altında açıklanır) sonraki aşama için yineleyin.

-   Tüm kullanıcılar Intune’a geçirilene kadar aşamalı döngüleri yineleyin.

-   Yardım Masası ekibinin geçiş kampanyası boyunca son kullanıcıları desteklemesini sağlayın. Destek çağrısı iş yükünü tahmin edebilene kadar gönüllü bir geçiş çalıştırın.

-   Yardım Masası kalan kullanıcı sayısıyla başa çıkabilir duruma gelene kadar son tarih belirlemeyin

> [!IMPORTANT] 
> Exchange veya SharePoint Online gibi kaynaklara erişim denetimleri uygulamak için hem Intune hem de mevcut üçüncü taraf MDM çözümünüzü yapılandırmayın. Ayrıca, cihazların aynı anda yalnızca bir çözüme kayıtlı olması gerekir.

## <a name="next-steps"></a>Sonraki adımlar

[2. Aşama: İletişim planı](https://docs.microsoft.com/intune/plan-design/migration-phase2-communication-plan)

