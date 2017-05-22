---
title: "0365’e uygulama tabanlı koşullu erişim"
description: "O365 hizmetlerine hangi uygulamaların erişimi olacağını denetlemekte MAM CA’nın nasıl yardımcı olabileceğine ilişkin kavramları anlayın."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/05/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bd6bee60-5e39-42c8-a2e9-f5865ac3573f
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: 8fc53e8717277a4075bc7ecde31fd60c3539a5f7
ms.lasthandoff: 04/19/2017


---

# <a name="allow-only-mobile-apps-that-support-intune-app-protection-policies-to-access-office-365-services"></a>Yalnızca Intune uygulama koruma ilkelerini destekleyen mobil uygulamaların Office 365 hizmetlerine erişimine izni verme

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

[Intune uygulama koruma ilkeleri](protect-apps-and-data-with-microsoft-intune.md) yönetilmek üzere Intune’da kayıtlı cihazlarda şirket verilerinizi korumaya yardımcı olur. Uygulama koruma ilkelerini, **yönetilmek üzere Intune’da kaydedilmemiş çalışan cihazları** üzerinde de uygulayabilirsiniz.  Bu durumda, cihazı yönetmiyor olmanıza rağmen, şirket verilerinizin ve kaynaklarınızın korunmasını sağlamanız gerekir. MAM ile Uygulama tabanlı koşullu erişim kullanarak, Exchange Online gibi O365 hizmetlerine yalnızca Intune uygulama koruma ilkelerini destekleyen mobil uygulamaların erişimine izin veren bir ilke oluşturabilirsiniz.

Örneğin, yalnızca **Microsoft Outlook uygulamasının** Exchange Online'a erişmesine izin vermek için **Exchange Online**’dan e-posta almak üzere Intune MAM ilkeleri tarafından sağlanan veri korumasına sahip olmayan **iOS ve Android’de yerleşik posta uygulamalarını engelleyebilirsiniz**. Veya Intune MAM desteği olmayan mobil uygulamaların **SharePoint Online**’a erişmesini engelleyebilirsiniz.

Aşağıdaki diyagramda Uygulama tabanlı koşullu erişim ilkeleri tarafından erişime ne zaman izin verilip ne zaman engelleneceğini belirlemek için kullanılan akış gösterilmektedir: ![Erişime izin verileceğini veya erişimin engelleneceğini belirlemek için dahil edilen çeşitli ölçütleri gösteren diyagram ](../media/mam-ca-decision-flow_simple.png).

Diyagramlarda kullanılan kısaltmaların açıklaması:
* **CP**: Şirket Portalı uygulaması
* **AA**: Azure Authenticator uygulaması
* **AAD**: Azure Active Directory
* **EAS**: Exchange Active Sync

## <a name="prerequisites"></a>Önkoşullar
Bir Uygulama tabanlı koşullu erişim ilkesi yapılandırmadan **önce**, bir **Enterprise Mobility + Security veya bir Azure Active Directory premium aboneliğinizin** olması ve kullanıcıların EMS veya Azure AD lisansına sahip olması gerekir. Daha fazla ayrıntı için bkz. [Enterprise Mobility fiyatlandırma sayfası](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) veya [Azure Active Directory fiyatlandırma sayfası](https://azure.microsoft.com/pricing/details/active-directory/).


## <a name="supported-apps"></a>Desteklenen uygulamalar
**Exchange Online**:
* Android ve iOS için **Microsoft Outlook**.

**SharePoint Online**
* iOS ve Android için Microsoft Word
* iOS ve Android için Microsoft Excel
* iOS ve Android için PowerPoint
* iOS ve Android için Microsoft OneDrive İş
* iOS için Microsoft OneNote

>[!IMPORTANT]
>Android cihazlarda, ilk cihaz kaydı OneDrive uygulamasında veya Outlook uygulamasında oturum açılarak yapılmalıdır. Android için OneNote uygulaması, kaydolmadan MAM desteğine henüz sahip değildir.

Uygulama tabanlı koşullu erişim ilkelerine sahip bir uygulama ile kullanıcı deneyimi hakkında bilgi edinmek için bkz. [MAM CA ile bir uygulama kullanırken beklenmesi gerekenler](use-apps-with-mam-ca.md).


## <a name="next-steps"></a>Sonraki adımlar
[MAM uygulamaları için bir Exchange Online İlkesi oluşturma](mam-ca-for-exchange-online.md)

[MAM uygulamaları için bir SharePoint Online İlkesi oluşturma](mam-ca-for-sharepoint-online.md)

[Modern kimlik doğrulaması olmayan uygulamaları engelleme](block-apps-with-no-modern-authentication.md)

### <a name="see-also"></a>Ayrıca bkz.

[Uygulama verilerini uygulama koruma ilkeleriyle koruma](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)
