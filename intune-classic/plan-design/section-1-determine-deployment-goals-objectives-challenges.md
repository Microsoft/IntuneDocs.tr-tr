---
title: "Intune dağıtım hedeflerini, amaçlarını ve zorluklarını belirleme | Microsoft Docs"
description: "Bu makale, bir Microsoft Intune yalnızca bulut uygulaması için dağıtım hedeflerini, amaçlarını ve zorluklarını belirlemeye yardımcı olur."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 24cf9d97-db39-4b95-a664-4aa2e33edb87
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 6014527422ea3dae4d1333965ccd9e48e8216afb
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---

# <a name="determine-intune-deployment-goals-objectives-and-challenges"></a>Intune dağıtım hedeflerini, amaçlarını ve zorluklarını belirleme

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

İyi bir dağıtım planı, kuruluşunuzun dağıtım hedeflerini, amaçlarını ve olası zorlukları belirlemekle başlar. Her kuruluş ayrıdır ve hepsinin kendine özgü dağıtım hedefleri, amaçları ve zorlukları vardır. Her alanı daha ayrıntılı bir şekilde açıklayacağız.

## <a name="deployment-goals"></a>Dağıtım hedefleri

Dağıtım hedefleri, bir kuruluşta Microsoft Intune uygulanarak amaçlanan uzun vadeli başarılardır. Aşağıda, her birinin açıklaması ve iş değeriyle birlikte bir kuruluşun Intune dağıtım amaçlarına örnekler verilmiştir.

-   **Office 365 ile tümleştirme ve Office mobil uygulamaların kullanımını destekleme**

    -   **Açıklama:** Office 365 ile sıkı bir tümleştirme ve Office mobil uygulamalarının uygulama koruması ile kullanımını sağlar.

    -   **İş değeri:** Kullanıcıların aşina olduğu ve tercih ettiği uygulamaları kullanmasına olanak tanıyarak güvenli ve iyileştirilmiş kullanıcı deneyimi.

-   **Mobil cihazlarda iç kurumsal hizmetlere erişimi etkinleştirme**

    -   **Açıklama:** Bu, nerede olurlarsa olsun çalışanların daha üretken olmasına ve kendilerine en uygun cihazı kullanmalarına olanak tanımak için kuruluşun stratejik yönelimidir. Bu proje, mobil üretkenliğe olanak tanımayı ve kurumsal verilere güvenli bir şekilde erişilmesini sağlamayı hedeflemelidir.

    -   **İş değeri:** Çalışanların çevik olmalarına ve nerede gerekiyorsa orada çalışabilmelerine olanak tanımak, daha rekabetçi bir iş ve daha doyurucu bir çalışma ortamı sağlamayı mümkün kılar.

-   **Mobil cihazlarda veri koruması sağlama**

    -   **Açıklama:** Verilerin mobil cihazda depolandığı yer kötü amaçlı ve yanlışlıkla gerçekleşen kayıplardan ve paylaşımlardan korunmalıdır.

    -   **İş değeri:** Veri koruması rekabetçi kalmamızı sağlamak için hayati öneme sahiptir ve müşterilerimize ve onların verilerine son derece büyük bir titizlikle yaklaşırız.

-   **Maliyetleri azaltma**

    -   **Açıklama:** Mümkün olduğunda, proje, dağıtım ve işletim maliyetlerini azaltır.

    -    **İş değeri:** Kaynakların verimli kullanımı, işletmenin diğer alanlara yatırım yapmasını, daha etkili bir şekilde rekabet etmesini ve müşterilere daha iyi hizmet vermesini sağlar.

## <a name="deployment-objectives"></a>Dağıtım amaçları

Dağıtım amaçları, bir kuruluşun Microsoft Intune dağıtım hedeflerine ulaşmak için gerçekleştirebileceği eylemlerdir. Aşağıda bir kuruluşun dağıtım amaçları ve her birine nasıl ulaşılacağına ilişkin bazı örnekler verilmiştir.

-   **Cihaz yönetim çözümlerinin sayısını düşürme**
<br>
    -   **Yürütme:** Tek bir mobil cihaz yönetimi çözümü; yani uygulamalar ve cihazlara yönelik kurumsal veri koruması için Microsoft Intune kullanın.
<br></br>
-   **Exchange ve SharePoint Online’a güvenli erişim sağlama**
<br>
    -   **Yürütme:** Exchange ve SharePoint Online için Microsoft Intune Koşullu Erişim uygulayın.
<br></br>
-   **Kurumsal verilerin mobil cihaza kaydedilmesini veya kurum dışı hizmetlere iletilmesini engelleme**
<br>
    -   **Yürütme:** Microsoft Office ve İş Kolu uygulamaları için Microsoft Intune Uygulama Koruma İlkeleri uygulayın.
<br></br>
-   **Cihazdan kurumsal verileri silme yeteneği sağlama**
<br>
    -   **Yürütme:** Uygun olduğunda kurumsal verileri ve kaynakları uzaktan silme yeteneği sağlaması için cihazları Microsoft Intune’a kaydedin ve Microsoft Intune ile yönetin.

## <a name="deployment-challenges"></a>Dağıtım zorlukları

Dağıtım zorlukları bir kuruluş için önde gelen sorunlardır ve dağıtım üzerinde olumsuz bir etkiye sahip olabilir. Bunlar bazen önceki projelerinde yaşadıkları ve kaçınmak istedikleri sorunlarla ilgili olabilir veya mevcut dağıtım çalışmasıyla ilgili yeni sorunları ifade edebilir. Aşağıda, bir kuruluşun Microsoft Intune dağıtım zorluklarına bazı örnekler, yapılması mümkün olan hafifletmelerle birlikte verilmiştir.

-   Destek hazırlığı ve son kullanıcı deneyimi ilk proje kapsamına dahil edilmemiştir.  Bu, son kullanıcının benimseme konusunda zayıflık yaşamasına neden olur ve çözümü desteklemeyi zorlaştırır.
<br>
    -   **Hafifletme:** Destek eğitimi ekleyin ve son kullanıcı deneyimini dağıtım planınızda başarı ölçümleri ile doğrulayın.
<br></br>
-   Açıkça tanımlanmış hedefler ve başarı ölçümleri olmaması, somut olmayan sonuçlara ve sorunlar ortaya çıktığında reaktif moda yol açar.
<br>
    -   **Hafifletme:** Hedeflerinizi ve başarı ölçümlerinizi proje kapsamınızda erken aşamada tanımlayın ve bu veri noktalarınızı, diğer sunum aşamalarınızı ayrıntılı hale getirmek için kullanın. Hedeflerin akıllı olduğundan emin olun (Spesifik, Ölçülebilir, Ulaşılabilir, Gerçekçi ve Zamanlı) ve her aşamada hedeflerinize göre ölçüm yapmak ve sunum projenizin yolunda gitmesini sağlamak için planlama yapın.
<br></br>
-   Kuruluşunuza uygun net bir değer önermesinin olmaması, denenmemesi ve hızlıca paylaşılmaması çoğunlukla benimsenme oranının düşük olması ve düşük yatırım getirisiyle (ROI) sonuçlanır.
<br>
    -   **Hafifletme:** Projenize geçmek için heyecanlı olsanız da, açıkça tanımlanmış hedefleriniz ve amaçlarınız olduğundan emin olun. Bunları kullanıcıların kuruluşunuzun neden Intune’u seçtiğini anlamasına yardımcı olması için tüm farkındalık ve eğitim faaliyetlerine ekleyin.

## <a name="next-steps"></a>Sonraki adımlar

Artık dağıtım hedeflerinizi, amaçlarınızı ve olası zorlukları tanımladığınıza göre bir sonraki bölüme geçebiliriz: [Kullanım örneği senaryolarını tanımlama](section-2-identify-use-case-scenarios.md).

