---
title: MAM CA bulunan uygulamaları kullanma
description: O365 hizmetlerine hangi uygulamaların erişimi olacağını denetlemekte MAM CA’nın nasıl yardımcı olabileceğine ilişkin kavramları anlayın.
keywords: ''
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/24/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 71dcf9bc-bfd1-4e06-b7ad-14b33a2288d0
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2f313fcbfa26c8f82708f8f830404da97a3eca25
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="what-to-expect-when-using-an-app-with-app-based-ca"></a>Uygulama tabanlı CA ile bir uygulama kullanırken beklenmesi gerekenler

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Uygulama tabanlı CA, onaylanan uygulamanın kimliğini, cihazda bulunması gereken bir aracı uygulama ile doğrular:
*  **iOS**’ta, **Azure Authenticator uygulaması** aracı uygulamadır.
* **Android**’de, **Intune Şirket Portalı uygulaması** aracı uygulamadır. 

OneDrive veya Outlook gibi uygulama tabanlı CA tarafından desteklenen bir uygulamada ilk kez oturum açan son kullanıcılardan aracı uygulamayı yüklemeleri ve cihazı Azure AD’ye kaydetmeleri istenir. Azure AD'de cihaz kaydetmek (eski adı Çalışma Alanına Katılma idi) bir cihaz kaydı ve karşılığında belirteçlerin yayınlandığı bir sertifika oluşturur.  Bu **MDM kaydı** ile aynı **değildir**. Yönetim profilleri veya ilkeleri uygulanmaz ve cihazdaki uygulamalardan envanter alınmaz.  Aracı uygulamayı yükleme ve cihazı kaydetme işlemi yalnızca yönetilen bir uygulama ilk kez kullanıldığında gerçekleştirilir.

Aşağıda doğrudan cihazdan türetilen özelliklerin listesi verilmiştir:

* alternativeSecurityIds (Azure Active Directory Sertifika parmak izi ve ortak anahtar karması)
* deviceOSType
* deviceOSVersion
* displayName

> [!NOTE]
> Android cihazlarda:
>   * Cihazda Şirket Portalı uygulamasının yüklü olması gerekir, ancak son kullanıcının uygulamada oturum açması gerekli değildir.
>   * Cihaz kaydı OneDrive veya Outlook uygulaması aracılığıyla yapılmalıdır.

## <a name="to-remove-a-device-from-azure-ad-registration"></a>Azure AD kaydından bir cihazı kaldırmak için.
Cihaz kaydını kaldırmanın bir yolu, Azure AD yönetici konsolundan kaldırmaktır ve bu işlem genelde BT yöneticileri tarafından yapılır.  Kaldırma işlemi aynı zamanda son kullanıcının cihazında da gerçekleştirilebilir.

* **Azure AD yönetici konsolu**: Azure AD yönetici konsolunda** kaldırmak istediğiniz cihazı silin.
* **iOS cihazı**: Azure Authenticator uygulamasını açın, hesabı sola kaydırın ve kaydı silin.  
* **Android cihazı**: Şirket portalı uygulamasını kaldırın veya hesabı **Sistem ayarları** sayfasından silin.

## <a name="app-based-ca-with-device-based-ca"></a>Cihaz tabanlı CA ile uygulama tabanlı CA  

[Cihaz uyumluluğu tabanlı koşullu erişimi](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) (<strong>Cihaz CA</strong>) [Intune yönetici konsolunda](https://manage.microsoft.com) veya [Azure AD Premium yönetici konsolunda](https://manage.windowsazure.com) yapılandırabilirsiniz. Cihaz CA, kullanıcıların yalnızca Intune cihaz uyumluluk ilkesi ile uyumlu Intune yönetilen cihazlarla veya etki alanına katılan bilgisayarlarla Exchange Online’a bağlanmasına izin verir.  Bir kullanıcı, hem uygulama tabanlı CA hem de Cihaz CA ilkeleri için hedeflenen bir veya daha fazla kullanıcı grubuna dahilse, kullanıcının iki gereksinimden birini karşılaması gerekir:
* Hizmete erişmek için kullanılan uygulama, 
* tarafından desteklenen bir mobil uygulamadır ve uygulamanın üzerinde çalıştığı cihazda, **iOS Authenticator (iOS cihazlar için)** veya **Şirket Portalı uygulaması (Android cihazlar için)** yüklüdür.
* Hizmete erişmek için **Intune tarafından yönetilen ve Intune cihaz uyumluluğu ilkesi ile uyumlu** bir cihaz veya bir **etki alanına katılan bilgisayar** kullanılır.  Aşağıda bunu göstermeye yardımcı olmaya yönelik bazı örnekler verilmiştir:
  * Bir kullanıcı, **yerel iOS e-posta uygulamasından** bağlanmayı deniyorsa, yerel posta uygulaması uygulama tabanlı CA tarafından desteklenmediği için **yönetilen ve uyumlu bir cihaz** kullanmalıdır.
  * Bir kullanıcı **Windows ev bilgisayarından** bağlanmayı denerse, etki alanına katılan bir bilgisayar kullanmasını gerektiren **Cihaz CA ilkesi** uygulanır.

## <a name="next-steps"></a>Sonraki adımlar
[MAM uygulamaları için bir Exchange Online İlkesi oluşturma](mam-ca-for-exchange-online.md)

[Modern kimlik doğrulaması olmayan uygulamaları engelleme](block-apps-with-no-modern-authentication.md)

### <a name="see-also"></a>Ayrıca bkz:

[Uygulama verilerini uygulama koruma ilkeleriyle koruma](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)
