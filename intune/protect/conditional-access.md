---
title: Microsoft Intune koşullu erişim
titleSuffix: Microsoft Intune
description: Microsoft Intune'da kullanıcıların, cihazların ve uygulamaların şirket kaynaklarına erişmek için uymaları gereken koşulları tanımlamayı öğrenin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/06/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a1973f38-ea55-43eb-a151-505fb34a8afb
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: fb9dd31c87d27ec7885d25269988cfd968e81e08
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72504551"
---
# <a name="learn-about-conditional-access-and-intune"></a>Koşullu erişim ve Intune hakkında bilgi edinin

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Koşullu erişim, e-postanıza ve şirket kaynaklarınıza bağlanmasına izin verilen cihazları ve uygulamaları denetleyebilmeniz için yollar anlamına gelir. Bu konu başlığında, cihaz tabanlı ve uygulama tabanlı koşullu erişim hakkında bilgi edinin ve Intune ile koşullu erişim kullanmaya yönelik yaygın senaryolar bulun.

Enterprise Mobility + Security (EMS) Koşullu Erişim, tek başına bir ürün değildir; EMS'nin parçası olan tüm ürün ve hizmetlerde yer alan bir çözümdür. Kurumsal verilerinizi güvenli tutmak için ayrıntılı erişim denetimi sağlarken, kullanıcılara herhangi bir cihazdan ve herhangi bir yerden en iyi şekilde çalışmalarına izin veren bir deneyim sunar.

Kurumsal verilerinize erişim için konum, cihaz, kullanıcı durumu ve uygulama hassaslığı temelinde bir geçit oluşturan koşullar tanımlayabilirsiniz.

> [!NOTE] 
> Koşullu Erişim, sahip olduğu özellikleri [Office 365 hizmetlerine](https://docs.microsoft.com/office365/enterprise/office-365-client-support-conditional-access) de yayar.

![Koşullu erişim mimari diyagramı](./media/conditional-access/ca-diagram-1.png)

## <a name="use-conditional-access-with-intune"></a>Intune ile koşullu erişim kullanma

Koşullu erişim, bir Azure Active Directory Premium lisansıyla birlikte sunulan bir Azure Active Directory özelliğidir. Intune, çözüme mobil cihaz uyumluluğu ve mobil uygulama yönetimi ekleyerek bu özelliği geliştirir. 

![EMS kullanırken Intune ve koşullu erişim](./media/conditional-access/intune-with-ca-1.png)

Intune ile koşullu erişim kullanmanın yolları:

- **Cihaz tabanlı koşullu erişim**

  - Şirket içi Exchange için koşullu erişim

  - Ağ erişim denetimi tabanlı koşullu erişim

  - Cihaz riskine dayalı koşullu erişim

  - Windows bilgisayarları için koşullu erişim

    - Şirkete ait olanlar

    - Kendi cihazını getir (KCG)

- **Uygulama tabanlı koşullu erişim**

## <a name="next-steps"></a>Sonraki adımlar

[Intune ile koşullu erişim kullanmanın yaygın yolları](conditional-access-intune-common-ways-use.md)
