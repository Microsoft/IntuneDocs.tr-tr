---
title: Cihaz yönetimi olmadan Exchange
titleSuffix: Microsoft Intune
description: Microsoft Intune'u kullanarak, bir cihaz yönetim sistemi ayarlamadan çalışanlara Office 365 Exchange Online e-postalarına erişim verin.
keywords: Office 365 Exchange e-posta erişimi
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/31/2017
ms.prod: ''
ms.service: microsoft-intune
ms.topic: article
ms.technology: ''
ms.assetid: 88a0d3b9-2622-403b-8374-1396afd8066e
ms.reviewer: pchacon
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 695eef8bb130200fd4f0913099aeeb51b752cabe
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55844148"
---
# <a name="protect-office-365-exchange-online-without-requiring-device-management"></a>Cihaz yönetimi gerektirmeden Office 365 Exchange Online’ı koruma

Bir cihaz yönetim sistemi ayarlama zahmetine katlanmaksızın çalışanların e-posta adreslerine erişimini sağlamak istiyorsanız, bu mümkündür. Intune aracılığıyla Office 365 Exchange Online’a erişim verebilirsiniz. Gerekli adımları tamamlamak için Microsoft 365 veya Azure Active Directory (premium) ve Intune lisanslarınızın olduğunu onaylayın. Çalışanların [desteklenen bir iOS veya Android cihazı](supported-devices-browsers.md) olmalıdır. 

Bir cihaz yönetim sistemi ayarlamak istiyorsanız, bu da mümkündür. Bu tür bir uygulama koruması, cihaz yönetiminden bağımsız olarak çalışır. 

## <a name="action-plan"></a>Eylem planı

1. [Koşullu erişim hakkında bilgi edinin](conditional-access.md). 
2. [Uygulama tabanlı koşullu erişim hakkında bilgi edinin](app-based-conditional-access-intune.md).
3. [Exchange Online için uygulama tabanlı koşullu erişim ilkeleri ayarlayın](app-based-conditional-access-intune-create.md).
4. [Yönetilemeyen uygulamaları engelleyin](app-modern-authentication-block.md), özellikle Azure Active Directory Authentication Library (ADAL) kullanmayanları.
5. (İsteğe bağlı) [SharePoint Online için uygulama tabanlı koşullu erişim ilkeleri ayarlayın](app-based-conditional-access-intune-create.md). Bu ilkeler, yönetilemeyen ve güvende olmayan uygulamalardan şirket verilerinize erişimi engeller. Ayrıca SharePoint Mobile’dan erişimi de sınırlar. 

## <a name="what-to-tell-employees-and-students"></a>Çalışanlara ve öğrencilere söylenecekler

* Çalışanlarınızdan ve öğrencilerinizden, iOS için Apple App Store veya Android için Google Play Store’dan Microsoft Outlook veya Microsoft SharePoint’i yüklemelerini isteyin. 
* Modern kimlik doğrulaması kullanmayan uygulamalara erişimi engellerseniz, çalışanlarınızı ve öğrencilerinizi bu kısıtlamadan haberdar edin. 

## <a name="next-steps"></a>Sonraki adımlar

Şirket verilerinin güvenliğini arttırmak için uygulama tabanlı koşullu erişim kullandınız. Sonraki adımların parçası olarak, şirket verilerinizin güvenliğini arttırmak için aşağıdaki gibi diğer yollar hakkında bilgi edinebilirsiniz: 

* [Active Directory ve Azure Active Directory’de cihaz uyumluluğu, cihaz riski, konum ve kullanıcı özniteliklerine bağlı olarak koşullu erişim](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) ayarlamak.  
* Kasıtlı veya kasıtsız veri sızıntılarına karşı şirketinizi korumaya yardımcı olmak adına uygulama koruma ilkeleri ayarlamak. 
* Şirket verilerini ağınız dışında da korumak adına Azure Information Protection’dan yararlanmak. 

Bunu veya diğer EMS ya da Office 365 senaryolarını etkinleştirmek için yardıma mı ihtiyacınız var? Microsoft 365, Enterprise Mobility + Security veya Azure Active Directory Premium için en az 150 lisansınız varsa, [FastTrack avantajlarınızdan](https://docs.microsoft.com/enterprise-mobility-security/solutions/enterprise-mobility-fasttrack-program) yararlanın. 
