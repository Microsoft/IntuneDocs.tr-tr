---
title: "Intune ile koşullu erişim"
titlesuffix: Azure portal
description: "Microsoft Intune'da kullanıcıların ve cihazların şirket kaynaklarına erişmek için uymaları gereken koşulları tanımlamayı öğrenin.\""
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 05/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1973f38-ea55-43eb-a151-505fb34a8afb
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1cd12a105142d5e537da487e3bd9297ef83ddcb3
ms.sourcegitcommit: 82088d297eef629e3da6011681ead442ae7e25f7
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="whats-conditional-access"></a>Koşullu erişim nedir?

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Bu konu, Enterprise Mobility + Security (EMS) için geçerli olduğu haliyle Koşullu erişimi açıklamakta, ardından Intune kullanırken karşılaşılan yaygın Koşullu erişim senaryolarına geçmektedir.

Enterprise Mobility + Security (EMS) Koşullu Erişim, tek başına bir ürün değildir; EMS'nin parçası olan tüm ürün ve hizmetlerde yer alan bir çözümdür. Kurumsal verilerinizi güvenli tutmak için ayrıntılı erişim denetimi sağlarken, kullanıcılara herhangi bir cihazdan ve herhangi bir yerden en iyi şekilde çalışmalarına izin veren bir deneyim sunar.

Kurumsal verilerinize erişim için konum, cihaz, kullanıcı durumu ve uygulama hassaslığı temelinde bir geçit oluşturan koşullar tanımlayabilirsiniz.

> [!NOTE] 
> Koşullu Erişim, sahip olduğu özellikleri [Office 365 hizmetlerine](https://blogs.technet.microsoft.com/wbaer/2017/02/17/conditional-access-policies-with-sharepoint-online-and-onedrive-for-business/) de yayar.

![Koşullu erişim mimari şeması](./media/ca-diagram-1.png)

## <a name="conditional-access-with-intune"></a>Intune ile koşullu erişim

Intune, EMS Koşullu Erişim çözümünü desteklemek için mobil cihaz uyumluluğu ve uygulama yönetim ilkeleri ekler.

![Intune ve EMS kullanırken koşullu erişim](./media/intune-with-ca-1.png)

Intune ile koşullu erişim kullanmanın yolları:

-   **Cihaz tabanlı koşullu erişim**

    -   Şirket içi Exchange için koşullu erişim

    -   Ağ erişim denetimine bağlı koşullu erişim

    -   Cihaz riskine bağlı olarak koşullu erişim

    -   Windows Bilgisayarlar için koşullu erişim

        -   Şirkete ait olanlar

        -   Kendi cihazını getir (KCG)

-   **Uygulamaya bağlı koşullu erişim**

## <a name="next-steps"></a>Sonraki adımlar

[Intune ile koşullu erişim kullanmanın yaygın yolları](conditional-access-intune-common-ways-use.md)
