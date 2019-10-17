---
title: Windows cihazları için Intune kayıt yöntemi özellikleri
titleSuffix: Microsoft Intune
description: Windows cihazlarına yönelik kayıt yöntemlerinin özellikleri.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/21/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: c6b12bb0066c37eb470065a169a3ad7866c69a17
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72503272"
---
# <a name="intune-enrollment-method-capabilities-for-windows-devices"></a>Windows cihazları için Intune kayıt yöntemi özellikleri
[!INCLUDE[azure_portal](../includes/azure_portal.md)]

İş gücünüzün cihazlarını Intune'a kaydetmek için kullanabileceğiniz birçok yöntem vardır. Aşağıdaki tabloda gösterildiği gibi her yöntemin farklı en iyi yöntemleri ve özellikleri vardır.

## <a name="best-practices-by-enrollment-method"></a>Kayıt yöntemine göre en iyi yöntemler
| **En iyi uygulamalar** | **[Azure AD'ye katılanlar](windows-enroll.md#enable-windows-10-automatic-enrollment)**|**[Azure AD'ye Autopilot ile katılanlar (Kullanıcı sürümlü mod)](enrollment-autopilot.md)** |**[Azure AD'ye Autopilot ile katılanlar (Otomatik dağıtım modu)](enrollment-autopilot.md)** |**[Toplu](windows-bulk-enroll.md)**|**[DEM](device-enrollment-manager-enroll.md)** | **[KCG](device-enrollment.md#bring-your-own-device)** | **[GPO](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)** | **[Ortak yönetim](https://docs.microsoft.com/sccm/core/clients/manage/co-management-overview)** |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|Eğitimde yaygın olarak kullanılanlar|![X](./media/enrollment-method-capab/xmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|
|Cihazlar, paylaşılan cihazlar olarak kullanılabilir|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|
|Kişisel cihazlar şirket kaynaklarına erişmelidir|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|
|Uygulamalara self servis bakım|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|

## <a name="capabilities-by-enrollment-method"></a>Kayıt yöntemine göre özellikler

| **Yetenekler** | **[Azure AD'ye katılanlar](windows-enroll.md#enable-windows-10-automatic-enrollment)**|**[Azure AD'ye Autopilot ile katılanlar (Kullanıcı sürümlü mod)](enrollment-autopilot.md)** |**[Azure AD'ye Autopilot ile katılanlar (Otomatik dağıtım modu)](enrollment-autopilot.md)** |**[Toplu](windows-bulk-enroll.md)**|**[DEM](device-enrollment-manager-enroll.md)** | **[KCG](device-enrollment.md#bring-your-own-device)** | **[GPO](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)** | **[Ortak yönetim](https://docs.microsoft.com/sccm/core/clients/manage/co-management-overview)** |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|Conditional Access                                      |![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|
|Kullanıcılar cihazla ilişkilendirilir                    |![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|
|Azure AD Premium gerektirir                               |![X](./media/enrollment-method-capab/xmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|
|Cihaz CA tarafından korunan kaynakları değerlendirebilir             |![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|
|Kullanıcılar cihazlarında yönetici olmamalıdır               |![X](./media/enrollment-method-capab/xmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|
|Cihaz kurulum deneyimini yapılandırma olanağı        |![X](./media/enrollment-method-capab/xmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|
|Cihazları kullanıcı etkileşimi olmadan kaydetme olanağı      |![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|
|PowerShell betikleri çalıştırma olanağı                       |![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/checkmark.png)\*| 
|AD etki alanına katılmadan sonra otomatik kaydı destekler      |![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|
|Hibrit Azure AD'ye katılmadan sonra otomatik kaydı destekler|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|
|Hibrit Azure AD'ye katılmadan sonra otomatik kaydı destekler       |![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![Onay işareti](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|

Configuration Manager \* Istemci uygulaması iş yükleri, Intune pilot veya Intune 'a taşınmalıdır.

## <a name="next-steps"></a>Sonraki adımlar

[Windows için kayıt ayarlama](windows-enroll.md)

