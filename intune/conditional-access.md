---
title: Microsoft Intune ile koşullu erişim
titleSuffix: Microsoft Intune
description: Microsoft Intune'da kullanıcıların, cihazların ve uygulamaların şirket kaynaklarına erişmek için uymaları gereken koşulları tanımlamayı öğrenin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/06/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a1973f38-ea55-43eb-a151-505fb34a8afb
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 34ce3f34dbf3c060438a6b30abc9345687cdaf47
ms.sourcegitcommit: 364a7dbc7eaa414c7a9c39cf53eb4250e1ad3151
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59292199"
---
# <a name="whats-conditional-access"></a>Koşullu erişim nedir?

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Koşullu erişim, e-postanıza ve şirket kaynaklarınıza bağlanmasına izin verilen cihazları ve uygulamaları denetlemek için kullanabileceğiniz yolları gösterir. Bu konu başlığı altında, cihaz tabanlı ve uygulama tabanlı koşullu erişim hakkında bilgi edinebilir ve koşullu erişimi Intune'la kullanmaya yönelik yaygın senaryolar bulabilirsiniz.

Enterprise Mobility + Security (EMS) Koşullu Erişim, tek başına bir ürün değildir; EMS'nin parçası olan tüm ürün ve hizmetlerde yer alan bir çözümdür. Kurumsal verilerinizi güvenli tutmak için ayrıntılı erişim denetimi sağlarken, kullanıcılara herhangi bir cihazdan ve herhangi bir yerden en iyi şekilde çalışmalarına izin veren bir deneyim sunar.

Kurumsal verilerinize erişim için konum, cihaz, kullanıcı durumu ve uygulama hassaslığı temelinde bir geçit oluşturan koşullar tanımlayabilirsiniz.

> [!NOTE] 
> Koşullu Erişim, sahip olduğu özellikleri [Office 365 hizmetlerine](https://blogs.technet.microsoft.com/wbaer/2017/02/17/conditional-access-policies-with-sharepoint-online-and-onedrive-for-business/) de yayar.

![Koşullu erişim mimari şeması](./media/ca-diagram-1.png)

## <a name="conditional-access-with-intune"></a>Intune ile koşullu erişim

Koşullu erişim, Azure Active Directory Premium lisansına eklenmiş olan bir Azure Active Directory özelliğidir. Intune, çözüme mobil cihaz uyumluluğu ve mobil uygulama yönetimi ekleyerek bu özelliği geliştirir. 

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
