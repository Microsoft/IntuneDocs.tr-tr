---
title: Windows cihazlarına için kayıt yöntemine göre Intune özellikleri
titlesuffix: Microsoft Intune
description: Windows cihazları için her kayıt yönteminin hangi özellikleri desteklediğine bakın.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c9e440aef7f434cbe675506fd6f22a9bd26b2c31
ms.sourcegitcommit: 528d2bc70bfd25803a2d9f0fe9372c8a5f5e7dad
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/28/2018
ms.locfileid: "47446829"
---
# <a name="capabilities-by-enrollment-method-for-windows-devices"></a>Windows cihazlarına için kayıt yöntemine göre özellikler
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune; iş gücünüzün cihazları, uygulamaları ve şirket verilerinize erişimini yönetmenizi sağlar. Cihazların önce Intune hizmetine kaydedilmesi gerekir. İş gücünüzün cihazlarını kaydetmek için çeşitli yöntemler vardır. Aşağıdaki tabloda gösterildiği gibi her yöntemin farklı en iyi yöntemleri ve özellikleri vardır.

## <a name="best-practices-by-enrollment-method"></a>Kayıt yöntemine göre en iyi yöntemler
| **En iyi uygulamalar** | **[Azure AD'ye katılanlar](windows-enroll.md#enable-windows-10-automatic-enrollment)**|**[Azure AD'ye AutoPilot ile katılanlar](enrollment-autopilot.md)** |**[Toplu](windows-bulk-enroll.md)**|**[DEM](device-enrollment-manager-enroll.md)** | **[KCG](device-enrollment.md#bring-your-own-device)** | **GPO** |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|Eğitimde yaygın olarak kullanılanlar|![X](media/xmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Cihazlar, paylaşılan cihazlar olarak kullanılabilir|![X](media/xmark.png)|![X](media/xmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Kişisel cihazlar şirket kaynaklarına erişmelidir|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Onay işareti](media/checkmark.png)|![X](media/xmark.png)|
|Uygulamalara self servis bakım|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|

## <a name="capabilities-by-enrollment-method"></a>Kayıt yöntemine göre özellikler

| **Yetenekler** | **[Azure AD'ye katılanlar](windows-enroll.md#enable-windows-10-automatic-enrollment)**|**[Azure AD'ye AutoPilot ile katılanlar](enrollment-autopilot.md)** |**[Toplu](windows-bulk-enroll.md)**|**[DEM](device-enrollment-manager-enroll.md)** | **[KCG](device-enrollment.md#bring-your-own-device)** | **GPO** |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|Koşullu erişim                                      |![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|
|Kullanıcılar cihazla ilişkilendirilir                    |![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|
|Azure AD Premium gerektirir                               |![X](media/xmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Onay işareti](media/checkmark.png)|
|Cihaz CA tarafından korunan kaynakları değerlendirebilir             |![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![X](media/xmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|
|Kullanıcılar cihazlarında yönetici olmamalıdır               |![X](media/xmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Cihaz kurulum deneyimini yapılandırma olanağı        |![X](media/xmark.png)|![Onay işareti](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Cihazları kullanıcı etkileşimi olmadan kaydetme olanağı      |![X](media/xmark.png)|![X](media/xmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![X](media/xmark.png)|![Onay işareti](media/checkmark.png)|
|PowerShell betikleri çalıştırma olanağı                       |![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)| 
|AD etki alanına katılmadan sonra otomatik kaydı destekler      |![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Onay işareti](media/checkmark.png)|
|Hibrit Azure AD'ye katılmadan sonra otomatik kaydı destekler|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Onay işareti](media/checkmark.png)|
|Hibrit Azure AD'ye katılmadan sonra otomatik kaydı destekler       |![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![Onay işareti](media/checkmark.png)|![X](media/xmark.png)|

## <a name="next-steps"></a>Sonraki adımlar

[Kayıt seçenekleri](enrollment-options.md)

