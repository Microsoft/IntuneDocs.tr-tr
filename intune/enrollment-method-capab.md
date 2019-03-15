---
title: Windows cihazları için Intune kayıt yöntemi özellikleri
titlesuffix: Microsoft Intune
description: Windows cihazlar için her bir kayıt yöntemi için özellikleri.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/21/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: e6f3db2034bdc71e656f468913394baf455d47e8
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57528250"
---
# <a name="intune-enrollment-method-capabilities-for-windows-devices"></a>Windows cihazları için Intune kayıt yöntemi özellikleri
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

İş gücünüzün cihazlarını Intune'a kaydetmek için çeşitli yöntemler vardır. Aşağıdaki tabloda gösterildiği gibi her yöntemin farklı en iyi yöntemleri ve özellikleri vardır.

## <a name="best-practices-by-enrollment-method"></a>Kayıt yöntemine göre en iyi yöntemler
| **En iyi uygulamalar** | **[Azure AD'ye katılanlar](windows-enroll.md#enable-windows-10-automatic-enrollment)**|**[Autopilot (temelli kullanıcı modu) ile Azure AD'ye katılmış](enrollment-autopilot.md)** |**[Azure AD'ye katılmış Autopilot (kendi modunu dağıtma)](enrollment-autopilot.md)** |**[Toplu](windows-bulk-enroll.md)**|**[DEM](device-enrollment-manager-enroll.md)** | **[KCG](device-enrollment.md#bring-your-own-device)** | **[GPO](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)** | **[Ortak yönetim](https://docs.microsoft.com/sccm/core/clients/manage/co-management-overview)** |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|Eğitimde yaygın olarak kullanılanlar|![X](media/xmark.png)|![Onay işareti](media/checkmark.png)|![X](media/xmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Cihazlar, paylaşılan cihazlar olarak kullanılabilir|![X](media/xmark.png)|![X](media/xmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Kişisel cihazlar şirket kaynaklarına erişmelidir|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Onay işareti](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Uygulamalara self servis bakım|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|

## <a name="capabilities-by-enrollment-method"></a>Kayıt yöntemine göre özellikler

| **Yetenekler** | **[Azure AD'ye katılanlar](windows-enroll.md#enable-windows-10-automatic-enrollment)**|**[Autopilot (temelli kullanıcı modu) ile Azure AD'ye katılmış](enrollment-autopilot.md)** |**[Azure AD'ye katılmış Autopilot (kendi modunu dağıtma)](enrollment-autopilot.md)** |**[Toplu](windows-bulk-enroll.md)**|**[DEM](device-enrollment-manager-enroll.md)** | **[KCG](device-enrollment.md#bring-your-own-device)** | **[GPO](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)** | **[Ortak yönetim](https://docs.microsoft.com/sccm/core/clients/manage/co-management-overview)** |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|Koşullu erişim                                      |![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|
|Kullanıcılar cihazla ilişkilendirilir                    |![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|
|Azure AD Premium gerektirir                               |![X](media/xmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|
|Cihaz CA tarafından korunan kaynakları değerlendirebilir             |![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![X](media/xmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|
|Kullanıcılar cihazlarında yönetici olmamalıdır               |![X](media/xmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Cihaz kurulum deneyimini yapılandırma olanağı        |![X](media/xmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Cihazları kullanıcı etkileşimi olmadan kaydetme olanağı      |![X](media/xmark.png)|![X](media/xmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![X](media/xmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|
|PowerShell betikleri çalıştırma olanağı                       |![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)| 
|AD etki alanına katılmadan sonra otomatik kaydı destekler      |![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|
|Hibrit Azure AD'ye katılmadan sonra otomatik kaydı destekler|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|
|Hibrit Azure AD'ye katılmadan sonra otomatik kaydı destekler       |![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|

## <a name="next-steps"></a>Sonraki adımlar

[Windows kaydını ayarlama ](windows-enroll.md)

