---
title: "Kavram kanıtı | Microsoft Intune"
description: "Intune dağıtımının kavram kanıtı aşamasıyla ilgili öneriler."
keywords: 
author: Nbigman
manager: angrobe
ms.date: 07/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f3c97380-23ca-40da-acbc-78108507cad7
ms.reviewer: tscott
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2a192c71b1b82f59b34ea614d09d895174f8112b
ms.openlocfilehash: bffd46199873f01e2c03fe8b30cdfb3c425a07ee


---

# Kavram kanıtı (PoC)
Kavram kanıtı aşaması, dağıtımınızın, şirketinizin gereksinimlerini karşılama becerisini belirlemeye odaklanmalıdır. Bu aşama, belirli teknik senaryoları doğrulamak üzere tasarlanmış basit bir topolojiyi içerir.  Dağıtım, bir test ortamında olmalıdır ve herhangi bir üretim kullanıcısını barındırmamalıdır.

## Bu neden önemli?
Kavram kanıtı, dağıtımınızın pilot kullanıcılara geçmeden önceki uygulanabilirliğini anlamak açısından önemlidir. Microsoft Intune’un ortamınızda nasıl çalışacağını öğreneceğiniz küçük ölçekli bir deney olarak düşünülmelidir. Ayrıca, bir pilot için gereken kaynaklara yatırım yapmadan önce belirli senaryoları doğrulamalıdır. Kavram kanıtında alınan dersler, pilot ve üretim tasarımınızı etkilemelidir.
Kapsamınızı oluşturmanıza ve kavram kanıtınızı tanımlamanıza yardımcı olması için, keşif sorularını inceleyerek başlayın.

## Keşif soruları
Proje ayrıntılarınızın kapsamını belirlemeye, olası riskleri ortaya çıkarmaya ve eyleme geçirilebilir görevleri tanımlamanıza yardımcı olması için bu soruları proje ekibinizle tartışın.

-   Kuruluşunuzun cihaz yönetimi gereksinimlerini ele almak üzere Intune’un karşılaması gereken temel senaryolar nelerdir?

-   İncelemek ve doğrulamak istediğiniz özellikler nelerdir?

-   Bu senaryoların doğrulamasını tamamlamak için test ortamında hangi kaynaklara sahip olmanız gerekir?

## Odak alanı hedefleri
Bu bölümü, sunumunuzun bu belirtilen aşaması için odak alanı etkinlikleri hakkında yönergeler almak amacıyla gözden geçirin.

### Planlama
Doğrulamanız gereken senaryoları PoC altyapınızı dağıtmadan önce bu doğrulamayı tamamlamak için ihtiyacınız olanları bilmeniz gerekir.

### Yardım masası
Herhangi bir üretim kullanıcısı veya cihazı dahil olmayacağından, projenin bu aşaması için yardım masasının hazırlanması gerekmez. Ancak bu, yardım masasının Intune dağıtım ve işleyişini öğrenmesi için bir fırsattır.

### Farkındalık
Teknik ekip ve yönetim sponsorluğunun, senaryo testinin ilerlemesini görebiliyor olması gerekir. Tasarım ekibinin, tasarımına dahil etmek amacıyla, öğrenilmiş dersleri biliyor olması gerekir.

### Eğitim
Kullanıcıları, cihazları, ilkeleri ve uygulamaları yönetecek yöneticiler, Intune konsolunu ve özelliklerini öğrenmek için bir fırsat olarak PoC kullanmalıdır.

### İşlemler
Kavram kanıtı, devam eden işlemler gerektirmez. Ancak operasyon personelinin PoC’de anlamak veya doğrulamak isteyeceği senaryolar olabilir.

## Başlarken denetim listesi
**Kavram kanıtı** aşamasına başlamanız için adımlar listesi aşağıda verilmiştir.

-   PoC başarı ölçütlerinizi tanımlayın. Bunlar, işletme gereksinimleri ve teknik gereksinimlerin doğrulanmasını temel almalıdır.

-   Test senaryolarını doğrulamak için gerekli kaynakları belirleyin.

-   Üretim ortamının benzetimini yapacak uygun test ortamlarını belirleyin, örneğin çeşitli işletim sistemleri için gereken cihaz sayısı.

## Sık karşılaşılan zorluklar
**Kavram kanıtı** aşamasında karşılaşabileceğiniz bazı zorluklar aşağıda verilmiştir.

-   **Zorluk:** Teknik birim ve insan kaynaklarının, üretime benzer senaryoları doğrulamasını sağlama.

    **Hafifletme:** PoC ortamında öğrenilen derslerin açıkla belirtilmesi, teknik tasarıma yardımcı olur ve sonraki aşamaların kalitesini iyileştirir. PoC için kaynakların olmaması, bu derslerin teknik tasarım tamamlandıktan sonra öğrenilmesini gerektirir - olasılıkla, bazı öğelerin yeniden tasarlanmasını gerektirir.

-   **Zorluk:** Üretimde gerekli olacak test senaryolarını tanımlama.

    **Hafifletme:** Yönetim sponsoru, ağ ve kullanıcı ekipleriyle birlikte çalışarak, bir istemci yönetimi çözümünün gereksinimlerini anlayın.

### Sonraki adımlar
[Pilot](pilot.md)



<!--HONumber=Jul16_HO4-->


