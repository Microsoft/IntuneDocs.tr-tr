---
title: "Cihaz yönetimi gerektirmeden Office 365 Exchange Online’ı koruma"
description: "Çalışanların iş e-postalarına erişimini sağlayın. Cihaz yönetimi gerekli değildir."
keywords: "Office 365 Exchange e-posta erişimi"
author: arob98
manager: angrobe
ms.date: 08/27/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 88a0d3b9-2622-403b-8374-1396afd8066e
ms.reviewer: pchacon
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3e27f8ae8b42617f73d44fdf128772204f1963ed
ms.sourcegitcommit: 86687a8272ee3269aa7330e85022661b20450059
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/27/2017
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