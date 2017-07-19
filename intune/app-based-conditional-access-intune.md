---
title: "Intune ile uygulama tabanlı koşullu erişim"
description: "Uygulama tabanlı koşullu erişimin Intune ile nasıl çalıştığına ilişkin kavramları anlayın."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 05/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b399fba0-5dd4-4777-bc9b-856af038ec41
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0893d511c73e4154c61063d96e26937ea2825467
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="app-based-conditional-access-with-intune"></a>Intune ile uygulama tabanlı koşullu erişim

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

[Intune uygulama koruma ilkeleri](app-protection-policy.md) Intune’da kayıtlı cihazlarda şirket verilerinizi korumaya yardımcı olur. Uygulama koruma ilkelerini, yönetilmek üzere Intune’da kaydedilmemiş çalışan cihazları üzerinde de uygulayabilirsiniz. Bu durumda, şirketiniz cihazı yönetmiyor olmasına rağmen, şirket verilerinizin ve kaynaklarınızın korunmasını sağlamanız gerekir.

Uygulama tabanlı koşullu erişim ve mobil uygulama yönetimi Exchange online ve diğer Office 365 hizmetlerine yalnızca Intune uygulama koruma ilkelerini destekleyen mobil uygulamaların erişmesine izin vererek bir güvenlik katmanı ekler.

> [!NOTE]
> Yönetilen bir uygulama, uygulama koruma ilkelerinin uygulandığı ve Intune tarafından yönetilebilen bir uygulamadır.

Exchange Online'a yalnızca Microsoft Outlook uygulamasının erişmesine izin verdiğinizde, iOS ve Android üzerindeki yerleşik posta uygulamalarını engelleyebilirsiniz. Ayrıca, Intune uygulama koruma ilkelerinin uygulanmadığı uygulamaların SharePoint Online'a erişmesini engelleyebilirsiniz.

## <a name="prerequisites"></a>Önkoşullar
Bir Uygulama tabanlı koşullu erişim ilkesi oluşturmadan önce aşağıdakilere sahip olmanız gerekir:

- **Enterprise Mobility + Security veya Azure Active Directory premium aboneliğiniz** olmalıdır ve kullanıcılar EMS veya Azure AD lisansına sahip olmalıdır.
    - Daha fazla ayrıntı için bkz. [Enterprise Mobility fiyatlandırma sayfası](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) veya [Azure Active Directory fiyatlandırma sayfası](https://azure.microsoft.com/pricing/details/active-directory/).

## <a name="supported-apps"></a>Desteklenen uygulamalar

- **Exchange Online**:
    - Android ve iOS için Microsoft Outlook.
<br></br>
- **SharePoint Online**
    - iOS ve Android için Microsoft Word
    - iOS ve Android için Microsoft Excel
    - iOS ve Android için PowerPoint
    - iOS ve Android için Microsoft OneDrive İş
    - iOS için Microsoft OneNote
<br></br>
- **Microsoft Teams**

    > [!NOTE] 
    > Uygulama tabanlı koşullu erişim [LOB uygulamalarını destekler](https://docs.microsoft.com/intune-classic/deploy-use/block-apps-with-no-modern-authentication), ancak bu uygulamaların [Office 365 modern kimlik doğrulaması](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) kullanması gerekir.

## <a name="how-app-based-conditional-access-works"></a>Uygulama tabanlı koşullu erişim nasıl çalışır?

Bu örnekte, yönetici Outlook uygulamasına uygulama koruma ilkeleri uygulamış, ardından Outlook uygulamasını kurumsal e-postaya erişirken kullanılabilecek onaylı uygulamalar listesine ekleyen bir koşullu erişim ilkesi eklemiştir.

> [!NOTE] 
> Aşağıdaki akış çizelgesi yapısı diğer yönetilen uygulamalar için kullanılabilir.

![Intune akış çizelgesi ile uygulama tabanlı koşullu erişim](./media/ca-intune-common-ways-3.png)

1.  Kullanıcı, Azure AD kimlik doğrulamasını Outlook uygulamasından gerçekleştirmeye çalışır.

2.  Kullanıcı ilk kez kimlik doğrulamaya çalıştığında, aracı bir uygulama yüklemek üzere uygulama mağazasına yönlendirilir. Aracı uygulama, iOS için Microsoft Authenticator ya da Android cihazlar için Microsoft Şirket portalı olabilir.

    > [!NOTE]
    > Bu senaryoda, kullanıcılar yerel bir e-posta uygulaması kullanmaya çalışırsa, önce uygulama mağazasına yeniden yönlendirilirler ve ardından Outlook uygulamasını yüklemeleri gerekir.

3.  Aracı uygulama cihaza yüklenir.

4.  Aracı uygulama, Azure AD'de bir cihaz kaydı oluşturan Azure AD kayıt işlemini başlatır. Bu, mobil cihaz yönetimi (MDM) kayıt işlemi ile aynı değildir, ancak koşullu erişim ilkelerinin cihazda uygulanabilmesi için bu kayıt gereklidir.

5.  Aracı uygulama, uygulamanın kimliğini doğrular. Aracı uygulamanın kullanıcı tarafından kullanılma yetkisi olup olmadığının doğrulayabilmesi için bir güvenlik katmanı vardır.

6.  Aracı uygulama, kullanıcı kimlik doğrulama işleminin bir parçası olarak Uygulama İstemci kimliğini Azure AD’ye gönderir ve böylece bunun onaylı ilke listesinde olup olmadığı denetlenebilir.

7.  Azure AD, kullanıcının onaylı ilke listesine dayalı olarak uygulamanın kimliğini doğrulamasına ve kullanmasına olanak sağlar. Uygulama onaylı ilke listesinde değilse, Azure AD uygulamaya erişimi engeller.

8.  Outlook uygulaması, Exchange Online ile iletişim başlatmak için Outlook Bulut Hizmeti ile iletişim kurar.

9.  Outlook Bulut Hizmeti, kullanıcı için Exchange Online hizmet erişim belirteci almak için Azure AD ile iletişim kurar.

10.  Outlook uygulaması kullanıcının şirket e-postasını almak için Exchange Online ile iletişim kurar.

11.  Şirket e-postası kullanıcının posta kutusuna gönderilir.

## <a name="next-steps"></a>Sonraki adımlar
[Uygulama tabanlı bir koşullu erişim ilkesi oluşturma](app-based-conditional-access-intune-create.md)

[Modern kimlik doğrulaması olmayan uygulamaları engelleme](app-modern-authentication-block.md)
