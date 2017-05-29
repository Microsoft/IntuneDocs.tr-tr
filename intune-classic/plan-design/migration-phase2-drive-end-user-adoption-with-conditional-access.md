---
title: "Koşullu erişimle son kullanıcı benimsemesi sağlama | Microsoft Docs"
description: "Bu makalenin amacı, Intune kaydını teşvik etmek için koşullu erişimden nasıl yararlanılacağına ilişkin öngörüler sağlamaktır."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c2d7ce3f-fe97-4044-ad9e-25ac8fa301c9
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 55e437fa33af9d27223798cbac9f541b0bc1be2d
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---

# <a name="phase-2-drive-end-user-adoption-with-conditional-access"></a>2. Aşama: Koşullu erişimle son kullanıcı benimsemesi sağlama

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Kaydı silinen cihazlar için e-posta engellemek gibi koşullu erişim özelliklerini Intune ile etkinleştirme, cihaz kaydına ve uyumluluğuna yardımcı olabilir ancak geçiş işleminin başarılı olması için gerekli değildir. Geçiş benimseme hedefleri ve güvenlik gereksinimleriniz başarıyı belirleyen unsurlar olmalıdır.

## <a name="migration-campaign-with-conditional-access"></a>Koşullu erişim ile geçiş kampanyası

Koşullu erişim ile bir geçiş kampanyasını geliştirme için tipik bir yaklaşım şöyledir:

1.  Tüm kullanıcılar için uygulanacak koşullu erişim kuralları ayarlayın ancak eski MDM sağlayıcısından geçiş yapacak kullanıcıları özellikle dışlayın. Tüm koşullu erişimden dışlanan bir Azure AD kullanıcı grubu oluşturabilirsiniz.

2.  Kullanıcılar geçiş yaptıkça, bunları koşullu erişim dışlama grubundan kaldırın.

3.  Geçiş tamamlandıktan sonra, Intune erişime izin vermedikçe varsayılan olarak tüm koşullu erişim ilkelerini engellemek için yapılandırın.

### <a name="advantages"></a>Yararları

-   Yeni kullanıcı hesapları veya önceki çözüm tarafından yönetilmeyen kullanıcı hesabı için erişim denetimi sağlar.

-   Geçişte önceki çözümün kullanıcıları için mehil süresi sağlar.

-   Üretkenlik kaybını en aza indirir

### <a name="disadvantages"></a>Dezavantajlar

-   Önceki çözümün kullanıcıları, koşullu erişim bu kullanıcılar için etkinleştirilene kadar yönetilmeyen cihazları kullanarak kaynaklara potansiyel olarak erişebilir.

> [!TIP]
> Bu birçok yaklaşımdan biridir. Her aşama için kayıt talimatı alındıktan sonra tüm koşullu erişimi etkileyen daha basit bir süreç seçebilir veya koşullu erişimi en baştan uygulayan ve erişim için tam uyumluluk gerektiren daha sıkı bir süreç seçebilirsiniz.

-   [Koşullu erişim](https://docs.microsoft.com/intune/conditional-access) hakkında daha fazla bilgi edinin.

## <a name="task-list-for-conditional-access"></a>Koşullu erişim için görev listesi

### <a name="task-1-get-ready-for-intune-conditional-access"></a>1. Görev: Intune koşullu erişim için hazırlanın

-   [Koşullu erişimi yapılandırmayı](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune) öğrenin.

### <a name="task-2-set-up-intune-conditional-access"></a>2. Görev: Intune koşullu erişimi ayarlayın

Daha fazla bilgi edinmek için aşağıdaki koşullu erişim ilkesi türlerinden birini seçin:

-   [Exchange Online ve yeni Exchange Online ayrılmış](/intune-classic/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)

-   [Şirket İçi Exchange ve eski Exchange Online ayrılmış](/intune-classic/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)

-   [SharePoint Online](/intune-classic/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune)

-   [Skype Kurumsal Çevrimiçi Sürüm](/intune-classic/deploy-use/restrict-access-to-skype-for-business-online-with-microsoft-intune)

-   [Dynamics CRM Online](/intune-classic/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune)

-   [Örnek e-posta erişimi senaryoları](/intune-classic/deploy-use/restrict-email-access-example-scenarios)

## <a name="next-steps"></a>Sonraki adımlar

[2. Aşama: Tipik Geçiş Döngüsü](/intune-classic/plan-design/migration-phase2-typical-migration-cycle)

