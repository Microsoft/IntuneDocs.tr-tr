---
title: "0365’e uygulama tabanlı koşullu erişim | Microsoft Intune"
description: "O365 hizmetlerine hangi uygulamaların erişimi olacağını denetlemekte MAM CA’nın nasıl yardımcı olabileceğine ilişkin kavramları anlayın."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bd6bee60-5e39-42c8-a2e9-f5865ac3573f
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 64eaba6918c4a5c7ccc39fb8ccfeae729a34ff4c
ms.openlocfilehash: a03faa57f9bf1ec6784f0b1ec2d41d3f4cd88a12


---

# Yalnızca Intune MAM ilkelerini destekleyen mobil uygulamalara Office 365 hizmetlerine erişim izni veren bir ilke oluşturma
[Intune mobil uygulama yönetimi (MAM) ilkeleri](protect-apps-and-data-with-microsoft-intune.md) yönetilmek üzere Intune’da kayıtlı cihazlarda şirket verilerinizi korumaya yardımcı olur. MAM ilkelerini, **yönetilmek üzere Intune’da kaydedilmemiş çalışan cihazları** üzerinde de uygulayabilirsiniz.  Bu durumda, cihazı yönetmiyor olmanıza rağmen, şirket verilerinizin ve kaynaklarınızın korunmasını sağlamanız gerekir. MAM (MAM CA) için koşullu erişim kullanarak, Exchange Online gibi O365 hizmetlerine yalnızca Intune MAM ilkelerini destekleyen mobil uygulamaların erişimine izin veren bir ilke oluşturabilirsiniz.

Örneğin, yalnızca **Microsoft Outlook uygulamasının** Exchange Online'a erişmesine izin vermek için **Exchange Online**’dan e-posta almak üzere Intune MAM ilkeleri tarafından sağlanan veri korumasına sahip olmayan **iOS ve Android’de yerleşik posta uygulamalarını engelleyebilirsiniz**.

## Önkoşullar
MAM CA ilkesini yapılandırmadan **önce**, bir **Enterprise Mobility + Security veya bir Azure Active Directory premium aboneliğinizin** olması ve kullanıcıların EMS veya Azure AD lisansına sahip olması gerekir. Daha fazla ayrıntı için bkz. [Enterprise Mobility fiyatlandırma sayfası](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility-pricing) veya [Azure Active Directory fiyatlandırma sayfası](https://azure.microsoft.com/en-us/pricing/details/active-directory/).


## Desteklenen uygulamalar
**Exchange Online**
* Android ve iOS için Microsoft Outlook

## Diğer koşullu erişim ve kimlik doğrulama yöntemleri ile çakışma
### Azure Active Directory sertifika tabanlı kimlik doğrulaması ile MAM CA

MAM CA, Azure Active Directory (Azure AD) sertifika tabanlı kimlik doğrulaması ile kullanılmamalıdır. Aynı anda bunlardan yalnızca biri yapılandırılmış olabilir.
### Cihaz uyumluluğuna göre koşullu erişim ile MAM CA  

[Cihaz uyumluluğu tabanlı koşullu erişimi](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) (**Cihaz CA**) [Intune yönetici konsolunda](https://manage.microsoft.com) veya [Azure AD Premium yönetici konsolunda] (https://manage.windowsazure.com) yapılandırabilirsiniz. Cihaz CA, kullanıcıların yalnızca Intune cihaz uyumluluk ilkesi ile uyumlu Intune yönetilen cihazlarla veya etki alanına katılan bilgisayarlarla Exchange Online’a bağlanmasına izin verir.  Bir kullanıcı hem MAM CA hem de cihaz CA ilkeleri için hedeflenen bir veya daha fazla kullanıcı grubuna dahilse, kullanıcının iki gereksinimden birini karşılaması gerekir:
* Hizmete erişmek için kullanılan uygulama MAM CA tarafından desteklenen bir mobil uygulamadır ve uygulamanın üzerinde çalıştığı cihazda **iOS Authenticator (iOS cihazlar için)** veya **Şirket Portalı uygulaması (Android cihazlar için)** yüklüdür.
* Hizmete erişmek için **Intune tarafından yönetilen ve Intune cihaz uyumluluğu ilkesi ile uyumlu** bir cihaz veya bir **etki alanına katılan bilgisayar** kullanılır.  Aşağıda bunu göstermeye yardımcı olmaya yönelik bazı örnekler verilmiştir:
  * Bir kullanıcı **yerel iOS e-posta uygulamasından** bağlanmayı denerse, yerel posta uygulaması MAM CA tarafından desteklenmediği için **yönetilen ve uyumlu bir cihaz** kullanması gerekir.
  * Bir kullanıcı **Windows ev bilgisayarından** bağlanmayı denerse, etki alanına katılan bir bilgisayar kullanmasını gerektiren **Cihaz CA ilkesi** uygulanır.


## MAM CA ile bir uygulama kullanırken beklenmesi gerekenler
MAM CA, onaylanan uygulamanın kimliğini, cihazda bulunması gereken bir aracı uygulama ile doğrular:
*  **iOS**’ta, **Azure Authenticator uygulaması** aracı uygulamadır.
* **Android**’de, **Intune Şirket Portalı uygulaması** aracı uygulamadır. 

OneDrive veya Outlook gibi MAM CA tarafından desteklenen bir uygulamada ilk kez oturum açan son kullanıcılardan aracı uygulamayı yüklemeleri ve cihazı Azure AD’ye kaydetmeleri istenir. Azure AD'de cihaz kaydetmek (eski adı Çalışma Alanına Katılma idi) bir cihaz kaydı ve karşılığında belirteçlerin yayınlandığı bir sertifika oluşturur.  Bu **MDM kaydı** ile aynı **değildir**. Yönetim profilleri veya ilkeleri uygulanmaz ve cihazdaki uygulamalardan envanter alınmaz.  Aracı uygulamayı yükleme ve cihazı kaydetme işlemi yalnızca yönetilen bir uygulama ilk kez kullanıldığında gerçekleştirilir.


## Sonraki adımlar
[MAM uygulamaları için bir Exchange Online İlkesi oluşturma](mam-ca-for-exchange-online.md)

[Modern kimlik doğrulaması olmayan uygulamaları engelleme](block-apps-with-no-modern-authentication.md)

### Ayrıca bkz.

[Uygulama verilerini MAM ilkeleriyle koruma](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Oct16_HO2-->


