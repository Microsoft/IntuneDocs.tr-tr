---
title: Veri JAMF Pro, Intune 'a gönderir
titleSuffix: Microsoft Intune
description: JAMF Pro 'Yu Intune ile Mac yönetmek üzere tümleştirdiğinizde Microsoft Intune, JAMF Pro tarafından gönderilen veri listesini gözden geçirin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: elocholi
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e4bf6df44335f3375d58d3c2c11da7cb3f982b3e
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72502409"
---
# <a name="data-jamf-pro-sends-to-intune"></a>Jamf Pro’nun Intune’a gönderdiği veriler

Intune ile son kullanıcılarınızın Mac 'nizi yönetmek için [JAMF Pro](https://www.jamf.com) kullandığınızda, JAMF Pro yönetilen MacOS cihazlarıyla ilgili envanter bilgilerini yakalar. 

## <a name="data"></a>Veri  
JAMF Pro paylaşımlarının Intune ile paylaştığı verilerin listesi için, JAMF Pro Technical belgelerindeki [ek: Microsoft Intune Ile paylaşılan envanter bilgileri](https://docs.jamf.com/technical-papers/jamf-pro/microsoft-intune/10.9.0/Appendix__Inventory_Information_Shared_with_Microsoft_Intune.html) bölümüne bakın. 

<!--  
Jamf Pro reports the following information to Intune:  

* Device Azure AD ID
* JAMF Inventory State (inventory state of a computer checked in with Jamf Pro within the last 24 hours)
* OS Version
* User Azure AD ID
* Encrypted (FileVault 2)
* Gatekeeper Status
* Password: minimum number of character sets
* Password expiration (days)
* Password Type - simple, alphanumeric, or unknown
* Prevent Auto Login
* Required Passcode Length
* Password: number of previous passwords to prevent reuse
* System Integrity Protection
* Last Check-In Time
* Architecture Type
* Available RAM Slots
* Battery Capacity
* Boot ROM
* Bus Speed
* Cache Size
* Device Name
* Domain Join
* Jamf ID
* MAC address
* Make
* Model
* Model Identifier
* NIC Speed
* Number of Cores
* Number of Processors
* OS
* Platform
* Processor Speed
* Processor Type
* Secondary MAC Address
* Serial Number
* SMC Version
* Total RAM
* UDID
* User Email
--> 

<!-- 
You can remove a Jamf-managed device from the Intune console by selecting **Delete** in the **All devices** view. Bulk device deletion can be enabled by selecting multiple devices and clicking **Delete**.
-->

## <a name="next-steps"></a>Sonraki adımlar
JAMF [Pro belgelerinden JAMF ile yönetilen bir cihazı kaldırma](https://www.jamf.com/jamf-nation/articles/80/unmanaging-computers-while-preserving-their-inventory-information)hakkında bilgi alın. Ek Yardım için [JAMF desteğiyle](https://www.jamf.com/support/) bir destek bileti de oluşturabilirsiniz. 

