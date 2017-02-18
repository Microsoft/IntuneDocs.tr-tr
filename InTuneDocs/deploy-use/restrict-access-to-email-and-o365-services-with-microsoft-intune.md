---
title: "E-posta ve Office 365’i koruma | Microsoft Docs"
description: "Bu konu başlığı altında, SharePoint Online’daki ve diğer hizmetlerdeki şirket e-postasına ve şirket verilerine yalnızca uyumlu cihazların erişmesine izin vermek için koşullu erişimi nasıl kullanabileceğiniz açıklanır."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c564d292-b83b-440d-bf08-3f5b299b7a5e
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 9f05e516723976dcf6862475dbb78f9dce2913be
ms.openlocfilehash: 399c6260a98d51417a067d001c0fd42c926c1513


---

# <a name="protect-access-to-email-office-365-and-other-services-with-microsoft-intune"></a>Microsoft Intune ile e-posta, Office 365 ve diğer hizmetlere erişimi koruma

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Enterprise Mobility + Security (EMS) Koşullu Erişim kullanarak şirket e-postanıza, **Şirket İçi Exchange**, **Exchange Online**, **Adanmış Exchange Online**, **SharePoint Online**, **Skype Kurumsal Çevrimiçi Sürüm** gibi Office 365 hizmetlerine ve diğer hizmetlere erişimi koruyabilirsiniz. Bu özellik, şirketinizin e-postasına ve Office 365 hizmetlerine erişimin, Intune yönetim konsolunda veya Azure klasik portalında ayarladığınız koşullu erişim kurallarına uyan cihazlarla sınırlı olduğundan emin olmanızı sağlar.
## <a name="how-does-conditional-access-work"></a>Koşullu erişim nasıl çalışır?
Uyumluluk ilkesi ayarları kullanarak cihazın uyumluluğunu değerlendirebilirsiniz. Koşullu erişim, belirli bir hizmete erişimi kısıtlamak veya erişim izni vermek için bu değerlendirmeyi kullanır. Koşullu erişim ilkesini bir cihaz uyumluluk ilkesiyle birlikte kullandığınızda, yalnızca uyumlu cihazların hizmete erişmesine izin verilir. Uyumluluk ilkesi ve koşullu erişim ilkesi kullanıcıya dağıtılır. Kullanıcının hizmetlere erişirken kullandığı her cihaz, ilkelerle uyumluluk açısından denetlenir.

Cihazın uyumluluğunun değerlendirilebilmesi için cihazı kullanan kullanıcıya dağıtılmış bir uyumluluk ilkesi olması gerektiğini unutmayın.
Kullanıcıya hiçbir uyumluluk ilkesi dağıtılmadıysa, cihaz uyumlu olarak kabul edilir ve hiçbir erişim kısıtlaması uygulanmaz.

Cihazlar ilkelerde ayarlanan koşulları karşılamadığında, kullanıcı cihazı kaydetme ve cihazın uyumlu olmasını önleyen sorunu düzeltme sürecinde yönlendirilir.

Tipik bir koşullu erişim akışı:

![Şemada, bir cihazın hizmete erişimine izin verilmesini veya bu erişimin engellenmesini belirlemek için kullanılan karar noktaları gösterilmektedir](../media/ConditionalAccess4.png)

## <a name="setup-considerations"></a>Kurulumda dikkat edilecek noktalar

### <a name="licensing"></a>Lisanslama

Microsoft Intune ve Azure Active Directory (Azure AD) Premium, EMS koşullu erişim aracılığıyla çok katmanlı denetim sağlamak için birlikte sorunsuz bir şekilde çalışır. Intune kullanarak koşullu erişim ilkeleri dağıtmak istiyorsanız her iki ürünün lisansına da sahip olmanız gerekir.

**Azure AD Premium lisansları**, tek başına bir hizmet veya Kurumsal anlaşmanın bir parçası olarak (Intune ile birlikte) satın alınabilir. Intune ile koşullu erişim ilkeleri dağıttıysanız uygun Azure AD Premium veya **EMS lisansları** edindiğinizden emin olun.

- [Enterprise Mobility fiyatlandırma sayfası](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility-pricing) veya [Azure Active Directory fiyatlandırma sayfası](https://azure.microsoft.com/en-us/pricing/details/active-directory/) hakkında daha fazla bilgi edinin.

Ayrıca, koşullu erişim ilkelerini uygulamayı planladığınız kullanıcılara [Azure AD Premium veya EMS lisansları atandığından](/Intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-4.md) emin olun.

### <a name="device-compliance-settings"></a>Cihaz uyumluluk ayarları

Koşullu erişimi ayarlamak için bir cihaz uyumluluk ilkesi ve koşullu erişim ilkesi ayarlayın. Uyumluluk ilkesi geçiş kodu, şifreleme ve cihazın yazılım kilidinin kırılmış olup olmadığı gibi ayarları içerir. Cihazın uyumlu kabul edilmesi için bu kurallara uyması gerekir.

- [Cihaz uyumluluk ilkesi ve nasıl çalıştığı](introduction-to-device-compliance-policies-in-microsoft-intune.md) hakkında daha fazla bilgi edinin.

### <a name="conditional-access-policy"></a>Koşullu erişim ilkesi

Koşullu erişim ilkesini ayarlayarak, erişimi aşağıdakiler temelinde koruyabilirsiniz:
- Cihaz uyumluluğunu durumu.
- Cihazda çalışan platform.
- Hizmetlere erişmek için kullanılan uygulamaların türü.

Diğer Intune ilkelerinden farklı olarak, koşullu erişim ilkelerini dağıtmazsınız. Bunun yerine, ilkeyi yapılandırdıktan ve ilkenin uygulanacağı kullanıcıları seçtikten sonra, ilke tüm hedeflenen kullanıcılara uygulanır. Bir kullanıcı ilke tarafından hedeflendiğinde, kaynaklara erişmek için kullandıkları her bir cihaz uyumlu olmalıdır.


## <a name="next-steps"></a>Sonraki adımlar


2. [Cihaz uyumluluğu ilkesi oluşturma](create-a-device-compliance-policy-in-microsoft-intune.md).

2.  Aşağıdaki Microsoft bulut hizmetleri/ürünlerinden biri için koşullu erişim ilkesi oluşturun:
> [!div class="op_single_selector"]
  - [Exchange Online için koşullu erişim ilkesi oluşturma](restrict-access-to-exchange-online-with-microsoft-intune.md)
  - [Şirket İçi Exchange için koşullu erişim ilkesi oluşturma](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  - [Yeni Ayrılmış Exchange Online için koşullu erişim ilkesi oluşturma](restrict-access-to-exchange-online-with-microsoft-intune.md)
  - [Eski Ayrılmış Exchange Online için koşullu erişim ilkesi oluşturma](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  - [SharePoint Online için koşullu erişim ilkesi oluşturma](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
  - [Skype Kurumsal Çevrimiçi Sürüm için koşullu erişim ilkesi oluşturma](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
  - [Dynamics CRM Online için koşullu erişim ilkesi oluşturma](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)



<!--HONumber=Feb17_HO1-->


