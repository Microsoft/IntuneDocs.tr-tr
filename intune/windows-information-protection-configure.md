---
title: Microsoft Intune’da Windows Bilgi Koruması ayarları
titleSuffix: ''
description: Windows Bilgi Koruması’nı yönetmek için kullanabileceğiniz Microsoft Intune ayarlarını öğrenin.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 1/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1ec649134d4c3d28c99863aa3f04d2a89d4e029f
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-configure-windows-information-protection-in-microsoft-intune"></a>Microsoft Intune’da Windows Bilgi Koruması’nı yapılandırma

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Kuruluşta çalışanlara ait cihazlar arttıkça, kuruluşun denetimi dışında kalan e-posta, sosyal medya ve genel bulut gibi uygulamalar ve hizmetler aracılığıyla yanlışlıkla veri sızıntıları yaşama riski de artar. Örneğin, bir çalışan en son mühendislik çalışmalarının resimlerini kişisel bir e-posta hesabından gönderebilir, ürün bilgilerini bir tweet’e kopyalayıp yapıştırabilir veya hazırlanması devam eden satış raporunu genel bulut depolama alanına kaydedebilir.

**Windows Bilgi Koruması**, çalışanın deneyimine başka hiçbir şekilde müdahale etmeden bu olası veri sızıntılarına karşı koruma sağlamaya yardımcı olur. Ayrıca, ortamınızda veya diğer uygulamalarda değişiklik yapmaya gerek kalmadan, kuruluşa ait cihazlarda ve çalışanların iş yerine getirdiği kişisel cihazlarda yanlışlıkla ortaya çıkabilecek veri sızıntılarına karşı kurumsal uygulamaları ve verileri korumaya da yardımcı olur.

Bu Intune ilkesi, Windows Information Protection tarafından korunan uygulamalar listesini, kurumsal ağ konumlarını, koruma düzeyini ve şifreleme ayarlarını yönetir.

>[!NOTE]
> Windows 10 Şirket Portalı uygulamasını Windows Bilgi Koruması ile kullanmak için Şirket Portalı uygulamasını Windows Bilgi Koruması’nın **Muaf** modu altına eklemeniz gerekir. 

### <a name="next-steps"></a>Sonraki adımlar
Daha fazla bilgi için bkz.:
-  [Windows Bilgi Koruması’nı kullanarak kuruluş verilerinizi koruma](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip).
- [Microsoft Intune klasik konsolunu kullanarak bir Windows Bilgi Koruması (WIP) ilkesi oluşturma](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune)
- [Microsoft Intune Azure portalını kullanarak MDM ile bir Windows Bilgi Koruması (WIP) ilkesi oluşturma](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune-azure)
- [Microsoft Intune Azure portalını kullanarak MAM ile bir Windows Bilgi Koruması (WIP) ilkesi oluşturma](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-mam-intune-azure)
