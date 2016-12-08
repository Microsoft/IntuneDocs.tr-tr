---
title: "0365’e uygulama tabanlı koşullu erişim | Microsoft Intune"
description: "O365 hizmetlerine hangi uygulamaların erişimi olacağını denetlemekte MAM CA’nın nasıl yardımcı olabileceğine ilişkin kavramları anlayın."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bd6bee60-5e39-42c8-a2e9-f5865ac3573f
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5083cb49e7a98f19ff21c1972149b00aee4ec93e
ms.openlocfilehash: e57280821168ddb043d093485ec74f042bbebfef


---

# Yalnızca Intune MAM ilkelerini destekleyen mobil uygulamalar için Office 365 hizmetlerine erişim izni verme
[Intune mobil uygulama yönetimi (MAM) ilkeleri](protect-apps-and-data-with-microsoft-intune.md) yönetilmek üzere Intune’da kayıtlı cihazlarda şirket verilerinizi korumaya yardımcı olur. MAM ilkelerini, **yönetilmek üzere Intune’da kaydedilmemiş çalışan cihazları** üzerinde de uygulayabilirsiniz.  Bu durumda, cihazı yönetmiyor olmanıza rağmen, şirket verilerinizin ve kaynaklarınızın korunmasını sağlamanız gerekir. MAM (MAM CA) için koşullu erişim kullanarak, Exchange Online gibi O365 hizmetlerine yalnızca Intune MAM ilkelerini destekleyen mobil uygulamaların erişimine izin veren bir ilke oluşturabilirsiniz.

Örneğin, yalnızca **Microsoft Outlook uygulamasının** Exchange Online'a erişmesine izin vermek için **Exchange Online**’dan e-posta almak üzere Intune MAM ilkeleri tarafından sağlanan veri korumasına sahip olmayan **iOS ve Android’de yerleşik posta uygulamalarını engelleyebilirsiniz**.

Aşağıdaki diyagramda MAM CA ilkeleri tarafından erişime ne zaman izin verilip ne zaman engelleneceğini belirlemek için kullanılan akış gösterilmektedir: ![Erişime izin verileceğini veya erişimin engelleneceğini belirlemek için dahil edilen çeşitli ölçütleri gösteren diyagram ](../media/mam-ca-decision-flow_simple.png).

Diyagramlarda kullanılan kısaltmaların açıklaması:
* **CP**: Şirket Portalı uygulaması
* **AA**: Azure Authenticator uygulaması
* **AAD**: Azure Active Directory
* **EAS**: Exchange Active Sync

## Önkoşullar
MAM CA ilkesini yapılandırmadan **önce**, bir **Enterprise Mobility + Security veya bir Azure Active Directory premium aboneliğinizin** olması ve kullanıcıların EMS veya Azure AD lisansına sahip olması gerekir. Daha fazla ayrıntı için bkz. [Enterprise Mobility fiyatlandırma sayfası](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility-pricing) veya [Azure Active Directory fiyatlandırma sayfası](https://azure.microsoft.com/en-us/pricing/details/active-directory/).


## Desteklenen uygulamalar
**Exchange Online**: Android ve iOS için **Microsoft Outlook**.

MAM CA ilkelerine sahip bir uygulama ile kullanıcı deneyimi hakkında bilgi edinmek için bkz. [MAM CA ile bir uygulama kullanırken beklenmesi gerekenler](use-apps-with-mam-ca.md).


## Sonraki adımlar
[MAM uygulamaları için bir Exchange Online İlkesi oluşturma](mam-ca-for-exchange-online.md)

[Modern kimlik doğrulaması olmayan uygulamaları engelleme](block-apps-with-no-modern-authentication.md)

### Ayrıca bkz.

[Uygulama verilerini MAM ilkeleriyle koruma](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Oct16_HO4-->


