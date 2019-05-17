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
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: dd1dbb3280fbbb93423796b18f6dd85a50a41f11
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2019
ms.locfileid: "59897412"
---
# <a name="intune-enrollment-method-capabilities-for-windows-devices"></a>Windows cihazları için Intune kayıt yöntemi özellikleri
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

İş gücünüzün cihazlarını Intune'a kaydetmek için kullanabileceğiniz birçok yöntem vardır. Aşağıdaki tabloda gösterildiği gibi her yöntemin farklı en iyi yöntemleri ve özellikleri vardır.

## <a name="best-practices-by-enrollment-method"></a>Kayıt yöntemine göre en iyi yöntemler
| **En iyi uygulamalar** | **[Azure AD'ye katılanlar](windows-enroll.md#enable-windows-10-automatic-enrollment)**|**[Azure AD'ye Autopilot ile katılanlar (Kullanıcı sürümlü mod)](enrollment-autopilot.md)** |**[Azure AD'ye Autopilot ile katılanlar (Otomatik dağıtım modu)](enrollment-autopilot.md)** |**[Toplu](windows-bulk-enroll.md)**|**[DEM](device-enrollment-manager-enroll.md)** | **[KCG](device-enrollment.md#bring-your-own-device)** | **[GPO](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)** | **[Ortak yönetim](https://docs.microsoft.com/sccm/core/clients/manage/co-management-overview)** |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|Eğitimde yaygın olarak kullanılanlar|![X](media/xmark.png)|![Onay işareti](media/checkmark.png)|![X](media/xmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Cihazlar, paylaşılan cihazlar olarak kullanılabilir|![X](media/xmark.png)|![X](media/xmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Kişisel cihazlar şirket kaynaklarına erişmelidir|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Onay işareti](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Uygulamalara self servis bakım|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|

## <a name="capabilities-by-enrollment-method"></a>Kayıt yöntemine göre özellikler

| **Yetenekler** | **[Azure AD'ye katılanlar](windows-enroll.md#enable-windows-10-automatic-enrollment)**|**[Azure AD'ye Autopilot ile katılanlar (Kullanıcı sürümlü mod)](enrollment-autopilot.md)** |**[Azure AD'ye Autopilot ile katılanlar (Otomatik dağıtım modu)](enrollment-autopilot.md)** |**[Toplu](windows-bulk-enroll.md)**|**[DEM](device-enrollment-manager-enroll.md)** | **[KCG](device-enrollment.md#bring-your-own-device)** | **[GPO](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)** | **[Ortak yönetim](https://docs.microsoft.com/sccm/core/clients/manage/co-management-overview)** |
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

[Windows için kaydı ayarlama](windows-enroll.md)

