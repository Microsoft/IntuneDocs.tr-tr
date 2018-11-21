---
title: Bir destek planı geliştirme
titlesuffix: Microsoft Intune
description: Bu makale, Microsoft Intune dağıtımı için bir Intune destek planı geliştirmenize yardımcı olur.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: b9428769-4333-4778-b677-f23dea1f74da
ms.reviewer: jeffbu, cgerth
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.openlocfilehash: 3bb1bb97dd113ac4f7fe41e516ad93dc7b6d7f01
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52188237"
---
# <a name="develop-a-support-plan"></a>Bir destek planı geliştirme

Bir Intune destek planınızın olması, Intune ile ilgili sorunları daha etkili bir şekilde tanımlayıp çözmenize yardımcı olabilir. Bunun karşılığında kullanıcılarınızın genel Intune deneyimi iyileşir. Intune destek planınızı geliştirirken dikkate almanız gereken bazı sorular şunlardır:

-   Intune desteğini sağlamaktan hangi ekipler sorumlu olacak?

-   Intune desteği sağlamak için hangi süreç kullanılacak?

-   Intune destek eğitimini nasıl sağlamayı planlıyorsunuz?

-   Intune dağıtım aşamasının başlarında destek ekibini dahil etme konusunda ne gibi fırsatlar var?

Her alanı daha ayrıntılı bir şekilde inceleyeceğiz.

## <a name="which-teams-are-responsible-for-providing-support"></a>Destek sağlamaktan hangi ekipler sorumlu?

Kuruluşların farklı destek katmanları veya düzeyleri (1-3) olabilir. Örneğin, katman 1 ve 2 destek ekibinin parçası olabilir ve katman 3 Intune dağıtımından sorumlu MDM ekip üyelerini içerir.

Katman 1 normalde ilk destek düzeyidir ve genellikle destek istekleri için kullanıcı tarafından iletişim kurulacak ilk katmandır. Katman 1, son kullanıcının sorununu çözemiyorsa bunu katman 2’ye iletir. Katman 2 ise gerekirse katman 3’e iletir. Ek olarak, Microsoft desteği katman 4 olarak düşünülebilir.

[Intune desteği](/intune/get-support) hakkında daha fazla bilgi edinin.

## <a name="what-is-the-support-process"></a>Destek süreci nedir?

İlk ürün piyasaya çıkarma aşamalarında, üç katman birlikte köprü veya Skype çağrısına katılabilir. Bir kuruluşun kendi BT destek veya yardım masası iş akışlarını nasıl uygulayabileceğine ilişkin bir örnek aşağıda verilmiştir:

1.  Son kullanıcı yaşadığı kayıt sorunu nedeniyle BT destek veya yardım masası katman 1 ile irtibat kurar.

2.  BT destek veya yardım masası katman 1, sorunun temel nedenini belirleyemez ve konuyu katman 2’ye iletir.

3.  BT destek veya yardım masası katman 2, sorunu araştırmasına rağmen çözemez ve araştırmaya yardımcı olması için ek bilgi sağlayarak konuyu katman 3’e iletir.

4.  BT desteği veya yardım masası katman 3; konuyu daha derinlemesine araştırır, sorunun temel nedenini belirler ve çözümü katman 2 ve 1'e bildirir.

5.  Ardından BT destek/yardım masası katman 1 müşteriyle irtibata geçerek sorunu giderir.

Bu tür bir yaklaşım, özellikle Intune’un piyasaya çıkışının erken aşamalarında pek çok yarar sağlar, örneğin:

-   Teknolojiyi öğrenme ve geliştirme konusunda yardım.

-   Sorunları ve çözümleri hızlı bir şekilde tanımlama.

-   Genel kullanıcı deneyimini geliştirir.

## <a name="how-you-plan-to-provide-intune-support-training"></a>Intune destek eğitimini nasıl sağlamayı planlıyorsunuz?

Eğitimin uygun bir düzeyde ve her destek katmanının kendi sorumluluklarını karşılayacak nitelikte olması için BT desteği veya yardım masası personelinize Intune teknik eğitimi sağlamanız önemlidir. Destek liderlerine bu eğitimi Intune MDM ekibinin vermesini (eğitmeni eğitme) ve ardından liderlerin de destek ekibi üyelerini eğitmesini sağlayabilirsiniz. Genellikle 2-3 saat içinde sağlanabilen bu eğitim sınıf ve laboratuvar çalışmaları içerir.

Intune destek eğitim gündemine bir örnek aşağıda verilmiştir.

-   Intune destek planı incelemesi

-   Intune genel bakışı

-   Yaygın sorunları giderme

-   Araçlar ve kaynaklar

-   Soru ve Cevap

[Intune belgeleri](https://docs.microsoft.com/intune/); Intune’a genel bakış, ayrıntılı özellik açıklamaları ve bazı sorun giderme bilgileri sağlar. [Intune forumu](https://social.technet.microsoft.com/Forums/home), Intune belgelerinde bahsedilmeyen konu ve sorulara yönelik topluluk tabanlı bir kaynaktır.

## <a name="what-opportunities-are-there-to-involve-the-support-team-earlier"></a>Destek ekibinin daha erken katılımını sağlamak için ne gibi fırsatlar var?

Intune dağıtım planlama ve pilot çalışmalarının erken aşamalarında BT destek/yardım masası personelinizin katılımını sağlamak, Intune dağıtımını ve son kullanıcı deneyimini iyileştirmeye yardımcı olabilir. Erken katılım, personelinizin Intune ile baştan tanışmasına ve bu süreçte önemli deneyimler edinmesine imkan tanır. Ayrıca BT destek/yardım masası personelinizin, kuruluşun tam üretim dağıtımını desteklemek üzere hazırlanmasına yardımcı olur.

## <a name="next-step"></a>Sonraki adım

Sonraki bölümde [Intune’u tasarlama](planning-guide-design.md) konusunda yönergeler sağlanır.
