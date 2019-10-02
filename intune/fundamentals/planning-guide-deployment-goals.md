---
title: Intune dağıtım hedeflerini, amaçlarını ve zorluklarını belirleme
titleSuffix: Microsoft Intune
description: Bu makale, bir Microsoft Intune yalnızca bulut uygulaması için dağıtım hedeflerini, amaçlarını ve zorluklarını belirlemeye yardımcı olur.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 24cf9d97-db39-4b95-a664-4aa2e33edb87
ms.reviewer: jeffbu, cgerth
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8cc4a109aac22617f2785a74de701e4d1d7bdf09
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71732225"
---
# <a name="determine-deployment-goals-objectives-and-challenges"></a>Intune dağıtım hedeflerini, amaçlarını ve zorluklarını belirleme

İyi bir dağıtım planı, kuruluşunuzun dağıtım hedeflerini, amaçlarını ve olası zorlukları belirlemekle başlar. Her alanı daha ayrıntılı bir şekilde açıklayacağız.

## <a name="deployment-goals"></a>Dağıtım hedefleri

Dağıtım hedefleri, kuruluşunuza Intune dağıtarak uzun vadede ulaşmak istediğiniz hedeflerdir. Aşağıda, bu tür hedeflerden bazıları, açıklaması ve iş açısından taşıdığı değer ile birlikte listelenmiştir.

- **Office 365 ile tümleştirme ve Office mobil uygulamaların kullanımını destekleme**

  - **Açıklama:** Office 365 ile sıkı bir tümleştirme ve Office mobil uygulamalarının uygulama koruması ile kullanılmasını sağlar.

  - **İş değeri:** Kullanıcıların aşina olduğu ve tercih ettiği uygulamaları kullanmasına olanak tanıyarak güvenli ve iyileştirilmiş kullanıcı deneyimi.

- **Mobil cihazlarda iç kurumsal hizmetlere erişimi etkinleştirme**

  - **Açıklama:** Çalışanların çalışmak istedikleri yerde, kendilerine en uygun gelen cihazı kullanarak daha üretken olmalarını sağlama. Bu proje, mobil üretkenliğe olanak tanımayı ve kurumsal verilere güvenli bir şekilde erişilmesini sağlamayı hedeflemelidir.

  - **İş değeri:** Çalışanların çevik olmalarını ve çalışmaları gereken yerde çalışabilmelerini sağlamak, işletmenin daha rekabetçi hale gelmesini ve daha doyurucu bir çalışma ortamı sağlamasını olanaklı kılar.

- **Mobil cihazlarda veri koruması sağlama**

  - **Açıklama:** Veriler mobil bir cihazda depolandığında, kötü amaçlı ve yanlışlıkla gerçekleşen kayıp veya paylaşımdan korunmalıdır.

  - **İş değeri:** Veri koruması rekabetçi kalmamızı sağlamak için hayati öneme sahiptir ve müşterilerimize ve onların verilerine son derece büyük bir titizlikle yaklaşırız.

- **Maliyetleri azaltma**

  - **Açıklama:** Mümkün olduğunda, proje, dağıtım ve işletim maliyetlerini azaltır.

  - **İş değeri:** Kaynakların verimli kullanımı, işletmenin diğer alanlara yatırım yapmasını, daha etkili bir şekilde rekabet etmesini ve müşterilere daha iyi hizmet vermesini sağlar.

## <a name="deployment-objectives"></a>Dağıtım amaçları

Dağıtım amaçları, kuruluşunuzun Intune dağıtım hedeflerine ulaşması için gerçekleştirebileceği eylemlerdir. Aşağıda dağıtım amaçlarına bazı örnekler ve bunların nasıl gerçekleştirilebileceği listelenmiştir.

- **Cihaz yönetim çözümlerinin sayısını azaltma**

  - **Uygulama:** Tek bir mobil cihaz yönetimi çözümünde birleşin: uygulama ve cihazlara yönelik kurumsal veri koruması için Microsoft Intune kullanın.

- **Exchange'e ve SharePoint Online’a güvenli erişim sağlama**

  - **Uygulama:** Exchange ve SharePoint Online için koşullu erişim uygulayın.

- **Kurumsal verilerin mobil cihazda depolanmasını veya kurum dışı hizmetlere iletilmesini engelleme**

  - **Uygulama:** Microsoft Office ve iş kolu uygulamaları için Intune uygulama koruma ilkeleri uygulayın.

- **Cihazdan kurumsal veri silme yeteneği sağlama**

  - **Uygulama:** Cihazları Intune'a kaydedin. Bu, uygun olduğunda şirket verilerini ve kaynaklarını uzaktan silebilmenizi sağlar.

## <a name="deployment-challenges"></a>Dağıtım zorlukları

Dağıtım zorlukları, bir kuruluşun önde gelen ve dağıtım üzerinde olumsuz bir etkiye sahip olabilen sorunlarıdır. Bunlar, bazen geçmiş projelerle ilişkili ve yeniden oluşmasını istemediğiniz eski sorunlar, bazen de güncel dağıtım çabasıyla ilişkili yeni sorunlardır. Aşağıda Intune dağıtım güçlüklerinin bazı örnekleri, bunları hafifletebilecek olası çözümlerle birlikte listelenmiştir.

- Destek hazırlığı ve son kullanıcı deneyimi, bir projenin başlangıçtaki kapsamına dahil edilmez. Bu, son kullanıcıların çözümü yeterince benimsememesine ve destek grubunuzda zorluklara neden olur.

  - **Hafifletme:** Destek eğitimini proje bünyesine alın. Son kullanıcı deneyimini, dağıtım planınızdaki başarı ölçümleriyle doğrulayın.

- Açıkça tanımlanmış hedeflerin ve başarı ölçümlerinin olmaması, somut olmayan sonuçlar elde edilmesine neden olur. Ayrıca, sorunlar ortaya çıktığında kuruluşunuzu geriye dönük bir tutuma kaydırır.

  - **Hafifletme:** Hedeflerinizi ve başarı ölçümlerinizi proje kapsamınızda erken aşamada tanımlayın ve bu veri noktalarınızı, diğer sunum aşamalarınızı ayrıntılı hale getirmek için kullanın. Amaçların Net, Ölçülebilir, Ulaşılabilir, Gerçekçi ve Zamanlı olduğundan emin olun. Her aşamada amaçlarınıza kıyasla ölçüm yapmaya göre plan yapın ve dağıtım projenizin yolundan çıkmadığından emin olun.

- Kuruluşunuz tarafından benimsenen net bir değer önermesi oluşturmayı, bunu doğrulamayı ve herkesle paylaştığınızdan emin olmayı ihmal ediyorsunuz. Bu, çoğu kez çözümün sınırlı düzeyde benimsenmesine ve bir yatırım getirisi (ROI) oluşmamasına neden olur.

  - **Hafifletme:** Projenize hemen başlama fikri heyecan verici de olsa, açıkça tanımlanmış hedefleriniz ve amaçlarınız olduğundan emin olun. Bunları kullanıcıların kuruluşunuzun neden Intune’u seçtiğini anlamasına yardımcı olması için tüm farkındalık ve eğitim faaliyetlerine ekleyin.

## <a name="next-steps"></a>Sonraki adımlar

Artık dağıtım hedeflerinizi, amaçlarınızı ve olası zorlukları tanımladığınıza göre bir sonraki bölüme geçebiliriz: [Kullanım örneği senaryolarını tanımlama](planning-guide-scenarios.md).
