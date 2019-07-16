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
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2019
ms.locfileid: "67885012"
---
# <a name="determine-deployment-goals-objectives-and-challenges"></a>Intune dağıtım hedeflerini, amaçlarını ve zorluklarını belirleme

İyi bir dağıtım planı, kuruluşunuzun dağıtım hedeflerini, amaçlarını ve olası zorlukları belirlemekle başlar. Her alanı daha ayrıntılı bir şekilde açıklayacağız.

## <a name="deployment-goals"></a>Dağıtım hedefleri

Dağıtım hedefleri, kuruluşunuza Intune dağıtarak uzun vadede ulaşmak istediğiniz hedeflerdir. Aşağıda, bu tür hedeflerden bazıları, açıklaması ve iş açısından taşıdığı değer ile birlikte listelenmiştir.

- **Office 365 ile tümleştirme ve Office mobil uygulamaların kullanımını destekleme**

  - **Açıklama:** Office 365 ile sıkı tümleştirme ve Office mobil uygulamalarının uygulama koruması ile kullanımı.

  - **İş değeri:** Kullanıcıların tanıdık ve tercih ettiği uygulamaları kullanmasına izin vererek güvenli ve geliştirilmiş Kullanıcı deneyimi.

- **Mobil cihazlarda iç kurumsal hizmetlere erişimi etkinleştirme**

  - **Açıklama:** Çalışanların, üzerinde çalışması gereken her yerde ve kendileri için en uygun cihaz ile üretken olmalarını sağlama. Bu proje, mobil üretkenliğe olanak tanımayı ve kurumsal verilere güvenli bir şekilde erişilmesini sağlamayı hedeflemelidir.

  - **İş değeri:** Çalışanların çevik olmasını ve ihtiyaç duydukları yerden çalışmasını sağlamak, işletmenin daha rekabet etmesine ve daha fazla çalışma ortamı sağlamasına imkan tanır.

- **Mobil cihazlarda veri koruması sağlama**

  - **Açıklama:** Veriler bir mobil cihazda depolandığında, kötü amaçlı ve yanlışlıkla kayıp ya da paylaşım arasında korunması gerekir.

  - **İş değeri:** Veri koruma, rekabetçi olmaya devam etmemiz ve istemcilerimizi ve verilerini en çok dille değerlendirmemiz açısından önemlidir.

- **Maliyetleri azaltma**

  - **Açıklama:** Mümkün olduğunda, proje dağıtım ve işletim maliyetlerini azaltır.

  - **İş değeri:** Kaynakların verimli kullanımı, işletmenin diğer alanlara yatırım yapmasına, daha etkili bir şekilde rekabet etmenize ve istemcilere daha iyi hizmet sağlamasına olanak sağlar.

## <a name="deployment-objectives"></a>Dağıtım amaçları

Dağıtım amaçları, kuruluşunuzun Intune dağıtım hedeflerine ulaşması için gerçekleştirebileceği eylemlerdir. Aşağıda dağıtım amaçlarına bazı örnekler ve bunların nasıl gerçekleştirilebileceği listelenmiştir.

- **Cihaz yönetim çözümlerinin sayısını azaltma**

  - **Paylaşır** Tek bir mobil cihaz yönetimi çözümüne birleştirin: Uygulama ve cihazların kurumsal veri koruması için Microsoft Intune.

- **Exchange'e ve SharePoint Online’a güvenli erişim sağlama**

  - **Paylaşır** Exchange ve SharePoint Online için koşullu erişim uygulayın.

- **Kurumsal verilerin mobil cihazda depolanmasını veya kurum dışı hizmetlere iletilmesini engelleme**

  - **Paylaşır** Microsoft Office ve iş kolu uygulamaları için Intune uygulama koruma ilkeleri uygulayın.

- **Cihazdan kurumsal veri silme yeteneği sağlama**

  - **Paylaşır** Cihazları Intune 'a kaydetme. Bu, uygun olduğunda şirket verilerini ve kaynaklarını uzaktan silebilmenizi sağlar.

## <a name="deployment-challenges"></a>Dağıtım zorlukları

Dağıtım zorlukları, bir kuruluşun önde gelen ve dağıtım üzerinde olumsuz bir etkiye sahip olabilen sorunlarıdır. Bunlar, bazen geçmiş projelerle ilişkili ve yeniden oluşmasını istemediğiniz eski sorunlar, bazen de güncel dağıtım çabasıyla ilişkili yeni sorunlardır. Aşağıda Intune dağıtım güçlüklerinin bazı örnekleri, bunları hafifletebilecek olası çözümlerle birlikte listelenmiştir.

- Destek hazırlığı ve son kullanıcı deneyimi, bir projenin başlangıçtaki kapsamına dahil edilmez. Bu, son kullanıcıların çözümü yeterince benimsememesine ve destek grubunuzda zorluklara neden olur.

  - **Mayı** Destek eğitimi ekleyin. Son kullanıcı deneyimini, dağıtım planınızdaki başarı ölçümleriyle doğrulayın.

- Açıkça tanımlanmış hedeflerin ve başarı ölçümlerinin olmaması, somut olmayan sonuçlar elde edilmesine neden olur. Ayrıca, sorunlar ortaya çıktığında kuruluşunuzu geriye dönük bir tutuma kaydırır.

  - **Mayı** Hedefleri ve başarı ölçümlerinizi proje kapsamınızda erken bir şekilde tanımlayın ve bu veri noktalarını kullanarak diğer dağıtım aşamalarınızı dışarı geçirin. Amaçların Net, Ölçülebilir, Ulaşılabilir, Gerçekçi ve Zamanlı olduğundan emin olun. Her aşamada amaçlarınıza kıyasla ölçüm yapmaya göre plan yapın ve dağıtım projenizin yolundan çıkmadığından emin olun.

- Kuruluşunuz tarafından benimsenen net bir değer önermesi oluşturmayı, bunu doğrulamayı ve herkesle paylaştığınızdan emin olmayı ihmal ediyorsunuz. Bu, çoğu kez çözümün sınırlı düzeyde benimsenmesine ve bir yatırım getirisi (ROI) oluşmamasına neden olur.

  - **Mayı** Projenize geçmek için heyecanlı olsa da, hedeflerinizi ve hedeflerinizi açıkça tanımlamış olduğunuzdan emin olun. Bunları kullanıcıların kuruluşunuzun neden Intune’u seçtiğini anlamasına yardımcı olması için tüm farkındalık ve eğitim faaliyetlerine ekleyin.

## <a name="next-steps"></a>Sonraki adımlar

Dağıtım Hedeflerinizi, amaçları ve olası güçlüklerinizi tanımladığınıza göre, bir sonraki bölüme geçelim: [Kullanım örneği senaryolarını belirler](planning-guide-scenarios.md).
