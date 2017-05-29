---
title: "Skycure Mobile Threat Defense uyumluluk ilkesi oluşturma | Microsoft Docs"
description: "Intune klasik konsolunda Skycure Mobile Threat Defense uyumluluk ilkesi oluşturun."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 56ff1728-1119-4e8a-aae6-ed5c7fafa052
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 54c36ffaee24ed7643bf8d64c52084d66550b240
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---

# <a name="create-skycure-mobile-threat-defense-compliance-policy"></a>Skycure Mobile Threat Defense uyumluluk ilkesi oluşturma

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Skycure Mobile Threat Defense ile Intune mobil cihazlardaki tehditleri algılamanıza ve bu cihazlardaki riski değerlendirmenize olanak tanır. Bir cihazın uyumlu olup olmadığını belirlemek üzere risk değerlendirmesi yapan bir Intune uyumluluk ilkesi oluşturabilirsiniz. Ardından cihaz uyumluluğuna dayalı olarak hizmetlere erişimi engellemek için koşullu erişim ilkesini kullanabilirsiniz.

## <a name="before-you-begin"></a>Başlamadan önce

Skycure cihaz tehdit koruması ile uyumluluk ilkesinin önkoşulları:

-   [Intune ile Skycure tümleştirmesi kurma](/intune-classic/deploy-use/setup-the-skycure-integration-with-Intune)

-   [Intune'da Skycure bağlantısını etkinleştirme](/intune-classic/deploy-use/enable-skycure-mobile-threat-defense-in-intune)

Skycure Mobile Threat Defense kurulumunun bir parçası olarak, Skycure konsolunda çeşitli tehditleri yüksek, orta ve düşük olarak sınıflandıran bir ilke oluşturulur. Şimdi, Intune uyumluluk ilkesinde izin verilen en yüksek tehdit düzeyini ayarlamalısınız.

## <a name="to-create-skycure-compliance-policy"></a>Skycure uyumluluk ilkesi oluşturmak için

1.  [Intune klasik konsoluna](https://manage.microsoft.com/) gidin ve kimlik bilgilerinizi girin.

2.  **İlke** &gt; **Uyumluluk İlkeleri**’ni seçin. Mevcut bir uyumluluk ilkesi kullanabilir veya yeni bir tane oluşturabilirsiniz.

3.  **Ekle** &gt; **Cihaz Durumu**’nu seçin ve **Cihaz Tehdit Koruması**’nı etkinleştirin.

4.  **İzin verilen en yüksek tehdit düzeyini** seçin:

    a.  **Hiçbiri (Güvenli)**: Bu, en güvenli ayardır. Cihazda herhangi bir tehdit mevcut olamaz ve yine de şirket kaynaklarına erişebilir. Herhangi bir tehdit bulunduğunda, cihaz uyumsuz olarak değerlendirilir.

    b.  **Düşük**: Cihaz, yalnızca düşük düzeydeki tehditler varsa uyumludur. Daha yüksek bir tehdit düzeyi, cihazı uyumlu değil durumuna getirir.

    c.  **Orta**: Cihazda bulunan tehditler düşük veya orta düzeydeyse cihaz uyumludur. Yüksek düzeyde tehditler algılanırsa cihaz uyumlu değil olarak değerlendirilir.

    d.  **Yüksek**: Bu en az güvenli seçenektir. Bu tüm tehdit düzeylerine izin verir ve Skycure mobil tehdit korumasını yalnızca raporlama amacıyla kullanır.

> [!IMPORTANT]
> Office 365 veya diğer hizmetler için koşullu erişim ilkeleri oluşturursanız bu uyumluluk değerlendirmesi dikkate alınır ve uyumlu olmayan cihazların bu hizmetlere erişimi tehdit giderilene kadar engellenir.

## <a name="span-idmonitor-device-threats-classanchorspan-idnext-steps-classanchorspan-idtoc477360344-classanchorspanspanspannext-steps"></a><span id="monitor-device-threats" class="anchor"><span id="next-steps" class="anchor"><span id="_Toc477360344" class="anchor"></span></span></span>Sonraki adımlar

-   Şu uygulamalar için koşullu erişim ilkesi oluşturma:

    -   [Exchange Online](/intune-classic/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)
    -   [Exchange Şirket İçi](/intune-classic/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)
    -   [SharePoint Online](/intune-classic/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune)
    -   [Skype Kurumsal Çevrimiçi](/intune-classic/deploy-use/restrict-access-to-skype-for-business-online-with-microsoft-intune)
    -   [Dynamics CRM](/intune-classic/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune)

