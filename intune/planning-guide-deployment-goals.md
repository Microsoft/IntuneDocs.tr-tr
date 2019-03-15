---
title: Intune dağıtım hedeflerini, amaçlarını ve zorluklarını belirleme
titlesuffix: Microsoft Intune
description: Bu makale, bir Microsoft Intune yalnızca bulut uygulaması için dağıtım hedeflerini, amaçlarını ve zorluklarını belirlemeye yardımcı olur.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 24cf9d97-db39-4b95-a664-4aa2e33edb87
ms.reviewer: jeffbu, cgerth
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: f9d7f04c9d625e6c263f4feb0eca7c8b6cadaf47
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57393288"
---
# <a name="determine-deployment-goals-objectives-and-challenges"></a>Intune dağıtım hedeflerini, amaçlarını ve zorluklarını belirleme

İyi bir dağıtım planı, kuruluşunuzun dağıtım hedeflerini, amaçlarını ve olası zorlukları belirlemekle başlar. Her alanı daha ayrıntılı bir şekilde açıklayacağız.

## <a name="deployment-goals"></a>Dağıtım hedefleri

Dağıtım hedefleri, kuruluşunuza Intune dağıtarak uzun vadede ulaşmak istediğiniz hedeflerdir. Aşağıda, bu tür hedeflerden bazıları, açıklaması ve iş açısından taşıdığı değer ile birlikte listelenmiştir.

-   **Office 365 ile tümleştirme ve Office mobil uygulamaların kullanımını destekleme**

    -   **Açıklama:** Office 365 ve Office mobil uygulamalarının uygulama koruması ile kullanımı, sıkı bir tümleştirme sağlar.

    -   **İş değeri:** İle ilgili bilgi sahibi olduğunuz ve tercih ettiğiniz uygulamaları kullanmasına olanak tanıyarak güvenli ve geliştirilmiş kullanıcı deneyimi.

-   **Mobil cihazlarda iç kurumsal hizmetlere erişimi etkinleştirme**

    -   **Açıklama:** Çalışanlar, gelen ve kendilerine en uygun cihazı ile çalışmak ihtiyaç duydukları her yerde üretken olmasını sağlar. Bu proje, mobil üretkenliğe olanak tanımayı ve kurumsal verilere güvenli bir şekilde erişilmesini sağlamayı hedeflemelidir.

    -   **İş değeri:** Çalışanların Çevik ve yerde iş etkinleştirilmesi, işletmenin daha rekabetçi hale gelmesini ve daha doyurucu bir çalışma ortamı sağlamasını olanaklı sağlar.

-   **Mobil cihazlarda veri koruması sağlama**

    -   **Açıklama:** Veriler Mobil bir cihazda depolandığında, kötü amaçlı ve yanlışlıkla gerçekleşen kayıp veya paylaşımdan korunmalıdır.

    -   **İş değeri:** Veri koruması rekabetçi ve biz müşterilerimize ve onların verilerine hayati dikkatli olmanızı ile kalmamızı sağlamak önemlidir.

-   **Maliyetleri azaltma**

    -   **Açıklama:** Mümkün olduğunda, proje, dağıtım ve işletim maliyetlerini azaltır.

    -    **İş değeri:** Kaynakların verimli kullanımı, işletmenin diğer alanlara yatırım yapmasını, daha etkili olmanıza ve daha iyi hizmet vermesini sağlamak etkinleştirir.

## <a name="deployment-objectives"></a>Dağıtım amaçları

Dağıtım amaçları, kuruluşunuzun Intune dağıtım hedeflerine ulaşması için gerçekleştirebileceği eylemlerdir. Aşağıda dağıtım amaçlarına bazı örnekler ve bunların nasıl gerçekleştirilebileceği listelenmiştir.

-   **Cihaz yönetim çözümlerinin sayısını azaltma**

    -   **Uygulama:** İçin bir tek bir mobil cihaz yönetimi çözümü birleştirin: Uygulama ve cihazların kurumsal veri koruma için Microsoft Intune.

-   **Exchange'e ve SharePoint Online’a güvenli erişim sağlama**

    -   **Uygulama:** Exchange ve SharePoint Online için koşullu erişim uygulayın.

-   **Kurumsal verilerin mobil cihazda depolanmasını veya kurum dışı hizmetlere iletilmesini engelleme**

    -   **Uygulama:** Intune uygulama koruma ilkeleri, Microsoft Office ve satır iş kolu uygulamaları için geçerlidir.

-   **Cihazdan kurumsal veri silme yeteneği sağlama**

    -   **Uygulama:** Cihazlarını Intune'a kaydetmeleri. Bu, uygun olduğunda şirket verilerini ve kaynaklarını uzaktan silebilmenizi sağlar.

## <a name="deployment-challenges"></a>Dağıtım zorlukları

Dağıtım zorlukları, bir kuruluşun önde gelen ve dağıtım üzerinde olumsuz bir etkiye sahip olabilen sorunlarıdır. Bunlar, bazen geçmiş projelerle ilişkili ve yeniden oluşmasını istemediğiniz eski sorunlar, bazen de güncel dağıtım çabasıyla ilişkili yeni sorunlardır. Aşağıda Intune dağıtım güçlüklerinin bazı örnekleri, bunları hafifletebilecek olası çözümlerle birlikte listelenmiştir.

-   Destek hazırlığı ve son kullanıcı deneyimi, bir projenin başlangıçtaki kapsamına dahil edilmez. Bu, son kullanıcıların çözümü yeterince benimsememesine ve destek grubunuzda zorluklara neden olur.

    -   **Azaltma:** Destek eğitimi ekleyin. Son kullanıcı deneyimini, dağıtım planınızdaki başarı ölçümleriyle doğrulayın.

-   Açıkça tanımlanmış hedeflerin ve başarı ölçümlerinin olmaması, somut olmayan sonuçlar elde edilmesine neden olur. Ayrıca, sorunlar ortaya çıktığında kuruluşunuzu geriye dönük bir tutuma kaydırır.

    -   **Azaltma:** Hedeflerinizi ve başarı ölçümlerinizi proje kapsamınızda erken tanımlayın ve bu veri noktalarınızı, diğer sunum aşamalarınızı için kullanın. Amaçların Net, Ölçülebilir, Ulaşılabilir, Gerçekçi ve Zamanlı olduğundan emin olun. Her aşamada amaçlarınıza kıyasla ölçüm yapmaya göre plan yapın ve dağıtım projenizin yolundan çıkmadığından emin olun.

-   Kuruluşunuz tarafından benimsenen net bir değer önermesi oluşturmayı, bunu doğrulamayı ve herkesle paylaştığınızdan emin olmayı ihmal ediyorsunuz. Bu, çoğu kez çözümün sınırlı düzeyde benimsenmesine ve bir yatırım getirisi (ROI) oluşmamasına neden olur.

    -   **Azaltma:** Projenize geçmek heyecanlı olsanız, açıkça hedefleriniz ve amaçlarınız tanımlanmış olun. Bunları kullanıcıların kuruluşunuzun neden Intune’u seçtiğini anlamasına yardımcı olması için tüm farkındalık ve eğitim faaliyetlerine ekleyin.

## <a name="next-steps"></a>Sonraki adımlar

Size, dağıtım hedeflerini, amaçlarını ve olası zorlukları tanımladığınıza göre sonraki bölüme geçelim: [Kullanım örneği senaryolarını tanımlama](planning-guide-scenarios.md).
