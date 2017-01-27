---
title: "Intune destek planı geliştirme | Microsoft Docs"
description: "Bu makale, Microsoft Intune yalnızca bulut tasarımı ve uygulaması için bir Intune destek planı oluşturmaya yardımcı olur."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b9428769-4333-4778-b677-f23dea1f74da
ms.reviewer: jeffbu, cgerth
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 874146573898e8a28de83ed599dbd4829ea8f335
ms.openlocfilehash: fb72b74d922cef8659c34ef9d3d36e14b1a22ac1


---

# <a name="develop-an-intune-support-plan"></a>Intune destek planı geliştirme

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Bir Intune destek planına sahip olmak Intune ile ilgili sorunları daha etkili bir şekilde tanımlamaya, çözmeye ve son kullanıcının genel Intune deneyimini iyileştirmeye yardımcı olabilir. Intune destek planınızı geliştirirken dikkate almanız gereken bazı sorular şunlardır:

-   Intune desteğini sağlamaktan hangi ekip veya ekipler sorumlu olacak?

-   Destek kuruluşunuz birden çok katman (örneğin katman 1-3) içeriyorsa her bir katman için Intune desteği sorumlulukları nelerdir?

-   Intune desteği sağlamak için hangi süreç kullanılacak?

-   Intune destek eğitimini nasıl sağlamayı planlıyorsunuz?

-   Intune dağıtım aşamasının başlarında destek ekibini dahil etme konusunda ne gibi fırsatlar var?

Her alanı daha ayrıntılı bir şekilde inceleyeceğiz.

## <a name="which-teams-are-responsible-for-providing-support"></a>Destek sağlamaktan hangi ekipler sorumlu?

Kuruluşların farklı destek katmanları/düzeyleri (1-3) olabilir. Örneğin, katman 1 ve 2 destek ekibinin parçası olabilir ve katman 3 Intune dağıtımından sorumlu MDM ekip üyelerini içerir.

## <a name="what-is-the-support-process"></a>Destek süreci nedir?

Katman 1 normalde ilk destek düzeyidir ve genellikle destek istekleri için kullanıcı tarafından iletişim kurulacak ilk katmandır. Katman 1, son kullanıcının sorununu çözemiyorsa sorun katman 2’ye taşınır ve gerekirse oradan da katman 3’e taşınır. Ek olarak, Microsoft desteği katman 4 olarak düşünülebilir.

-   [Intune desteği](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune) hakkında daha fazla bilgi edinin.

İlk üretim dağıtımı aşamalarında, kuruluşlardaki üç katman da köprü veya Skype çağrısına katılabilir. Bir kuruluşun kendi BT destek/yardım masası iş akışlarını nasıl uygulayabileceğine ilişkin bir örnek aşağıda verilmiştir:

1.  Son kullanıcı yaşadığı kayıt sorunu nedeniyle BT destek/yardım masası katman 1 ile irtibat kurar.

2.  BT destek/yardım masası katman 1, sorunun temel nedenini belirleyemez ve konuyu katman 2’ye iletir.

3.  BT destek/yardım masası katman 2, sorunu araştırmasına rağmen çözemez ve araştırmaya yardımcı olması için ek bilgi sağlayarak konuyu katman 3’e iletir.

4.  BT destek/yardım masası katman 3, konuyu daha derinlemesine araştırır, sorunun temel nedenini belirler ve çözümü katman 2 ve 1’e bildirir.

5.  Ardından BT destek/yardım masası katman 1 müşteriyle irtibata geçerek sorunu giderir.

Özellikle Intune dağıtımının erken aşamalarında bu tür bir yaklaşım kullanmak aşağıdakiler gibi pek çok yarar sağlar:

-   Teknolojiyi öğrenme ve geliştirme konusunda yardım.

-   Sorunları ve çözümleri hızlı bir şekilde tanımlama.

-   Genel kullanıcı deneyimini geliştirir.

## <a name="how-you-plan-to-provide-intune-support-training"></a>Intune destek eğitimini nasıl sağlamayı planlıyorsunuz?

Eğitimin uygun bir düzeyde olması ve belirli destek katmanı ve sorumluluklarını karşılayacak nitelikte olması için BT destek/yardım masası personelinize Intune teknik eğitimi sağlamak önemlidir. Kuruluşlar destek liderlerine bu eğitimi Intune MDM ekibinin vermesini (eğitmeni eğitme) ve ardından liderlerin bu eğitimi destek ekibi üyelerine vermesini sağlayabilir. Genellikle 2-3 saat içinde sağlanabilen bu eğitim sınıf ve laboratuvar çalışmaları içerir.

Intune destek eğitim gündemine bir örnek aşağıda verilmiştir.

-   Intune Destek Planı İncelemesi

-   Intune’a Genel Bakış

-   Yaygın Sorunları Giderme

-   Araçlar ve Kaynaklar

-   Soru ve Cevaplar

>[!TIP]
> [Ek kaynaklar](additional-resources.md), Microsoft Intune eğitimi sırasında destek ekibinizin incelemesi ve faydalanması açısından değerli olabilecek teknik kaynaklar sağlar.

## <a name="what-opportunities-are-there-to-involve-the-support-team-earlier"></a>Destek ekibinin daha erken katılımını sağlamak için ne gibi fırsatlar var?

Intune dağıtım planlama ve pilot çalışmalarının erken aşamalarında BT destek/yardım masası personelinin katılımını sağlamak kuruluşlar için çok yararlı olabilir. Bu, destek personelinin çözümü anlamasına ve değerli deneyimler elde etmesine olanak tanır. Ayrıca, BT destek/yardım masası personelini kuruluşların tam üretim dağıtımına hazırlamaya da yardımcı olur.

## <a name="next-section"></a>Sonraki Bölüm

Sonraki bölümde [Intune’u tasarlama](section-7-create-an-intune-design.md) konusunda yönergeler sağlanır.



<!--HONumber=Jan17_HO4-->


