---
title: "Intune ile koşullu erişim"
titleSuffix: Intune on Azure
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
ms.openlocfilehash: d3e6b720eeed65c81e5f3a4dbf06890ea8fd09ce
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
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

Intune, EMS Koşullu Erişim çözümünü desteklemek için mobil cihaz uyumluluğu ve mobil uygulama yönetimi özellikleri ekler.

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