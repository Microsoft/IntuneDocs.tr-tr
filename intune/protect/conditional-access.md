---
title: Conditional Access with Microsoft Intune
titleSuffix: Microsoft Intune
description: Learn how to define the conditions that users, devices, and apps must meet to access company resources in Microsoft Intune.
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
ms.openlocfilehash: 179d135ee8e216495cd7435bf38d8087e5c990e8
ms.sourcegitcommit: 13fa1a4a478cb0e03c7f751958bc17d9dc70010d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/19/2019
ms.locfileid: "74188287"
---
# <a name="learn-about-conditional-access-and-intune"></a>Learn about Conditional Access and Intune

With Conditional Access, you can control the devices and apps that can connect to your email and company resources. 

Enterprise Mobility + Security (EMS)  is not a standalone product. It's a solution that takes part on all services and products that are part of EMS. Conditional Access provides granular access control to keep your corporate data secure, while giving users an experience that allows them to do their best work from any device, and from any location.

Kurumsal verilerinize erişim için konum, cihaz, kullanıcı durumu ve uygulama hassaslığı temelinde bir geçit oluşturan koşullar tanımlayabilirsiniz.

> [!NOTE]
> Koşullu Erişim, sahip olduğu özellikleri [Office 365 hizmetlerine](https://docs.microsoft.com/office365/enterprise/office-365-client-support-conditional-access) de yayar.

![Conditional Access diagram](./media/conditional-access/ca-diagram-1.png)

## <a name="use-conditional-access-with-intune"></a>Use Conditional Access with Intune

Conditional Access is an Azure Active Directory capability that is included with an Azure Active Directory Premium license. Intune, çözüme mobil cihaz uyumluluğu ve mobil uygulama yönetimi ekleyerek bu özelliği geliştirir. 

![Intune and Conditional Access when using EMS](./media/conditional-access/intune-with-ca-1.png)

Ways to use Conditional Access with Intune:

- **Device-based Conditional Access**

  - Conditional Access for Exchange on-premises

  - Conditional Access based on network access control

  - Conditional Access based on device risk

  - Conditional Access for Windows PCs

    - Şirkete ait olanlar

    - Kendi cihazını getir (KCG)

- **App-based Conditional Access**

## <a name="next-steps"></a>Sonraki adımlar

[Common ways to use Conditional Access with Intune](conditional-access-intune-common-ways-use.md)
