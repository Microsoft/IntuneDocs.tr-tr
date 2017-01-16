---
title: "MAM CA ile uygulamaları kullanma | Microsoft Docs"
description: "O365 hizmetlerine hangi uygulamaların erişimi olacağını denetlemekte MAM CA’nın nasıl yardımcı olabileceğine ilişkin kavramları anlayın."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/24/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 71dcf9bc-bfd1-4e06-b7ad-14b33a2288d0
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 22746475bf50f8e4775c81e6833428c7f2ef9eba


---
# <a name="what-to-expect-when-using-an-app-with-mam-ca"></a>MAM CA ile bir uygulama kullanırken beklenmesi gerekenler

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

MAM CA, onaylanan uygulamanın kimliğini, cihazda bulunması gereken bir aracı uygulama ile doğrular:
*  **iOS**’ta, **Azure Authenticator uygulaması** aracı uygulamadır.
* **Android**’de, **Intune Şirket Portalı uygulaması** aracı uygulamadır. 

OneDrive veya Outlook gibi MAM CA tarafından desteklenen bir uygulamada ilk kez oturum açan son kullanıcılardan aracı uygulamayı yüklemeleri ve cihazı Azure AD’ye kaydetmeleri istenir. Azure AD'de cihaz kaydetmek (eski adı Çalışma Alanına Katılma idi) bir cihaz kaydı ve karşılığında belirteçlerin yayınlandığı bir sertifika oluşturur.  Bu **MDM kaydı** ile aynı **değildir**. Yönetim profilleri veya ilkeleri uygulanmaz ve cihazdaki uygulamalardan envanter alınmaz.  Aracı uygulamayı yükleme ve cihazı kaydetme işlemi yalnızca yönetilen bir uygulama ilk kez kullanıldığında gerçekleştirilir.

Aşağıda doğrudan cihazdan türetilen özelliklerin listesi verilmiştir:

* alternativeSecurityIds (Azure Active Directory Sertifika parmak izi ve ortak anahtar karması)
* deviceOSType
* deviceOSVersion
* displayName

## <a name="to-remove-a-device-from-azure-ad-registration"></a>Azure AD kaydından bir cihazı kaldırmak için.
Cihaz kaydını kaldırmanın bir yolu, Azure AD yönetici konsolundan kaldırmaktır ve bu işlem genelde BT yöneticileri tarafından yapılır.  Kaldırma işlemi aynı zamanda son kullanıcının cihazında da gerçekleştirilebilir.

* **Azure AD yönetici konsolu**: Azure AD yönetici konsolunda** kaldırmak istediğiniz cihazı silin.
* **iOS cihazı**: Azure Authenticator uygulamasını açın, hesabı sola kaydırın ve kaydı silin.  
* **Android cihazı**: Şirket portalı uygulamasını kaldırın veya hesabı **Sistem ayarları** sayfasından silin.



## <a name="mam-ca-with-conditional-access-based-on-device-compliance"></a>Cihaz uyumluluğuna göre koşullu erişim ile MAM CA  

[Cihaz uyumluluğu tabanlı koşullu erişimi](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) (**Cihaz CA**) [Intune yönetici konsolunda](https://manage.microsoft.com) veya [Azure AD Premium yönetici konsolunda] (https://manage.windowsazure.com) yapılandırabilirsiniz. Cihaz CA, kullanıcıların yalnızca Intune cihaz uyumluluk ilkesi ile uyumlu Intune yönetilen cihazlarla veya etki alanına katılan bilgisayarlarla Exchange Online’a bağlanmasına izin verir.  Bir kullanıcı hem MAM CA hem de cihaz CA ilkeleri için hedeflenen bir veya daha fazla kullanıcı grubuna dahilse, kullanıcının iki gereksinimden birini karşılaması gerekir:
* Hizmete erişmek için kullanılan uygulama MAM CA tarafından desteklenen bir mobil uygulamadır ve uygulamanın üzerinde çalıştığı cihazda **iOS Authenticator (iOS cihazlar için)** veya **Şirket Portalı uygulaması (Android cihazlar için)** yüklüdür.
* Hizmete erişmek için **Intune tarafından yönetilen ve Intune cihaz uyumluluğu ilkesi ile uyumlu** bir cihaz veya bir **etki alanına katılan bilgisayar** kullanılır.  Aşağıda bunu göstermeye yardımcı olmaya yönelik bazı örnekler verilmiştir:
  * Bir kullanıcı **yerel iOS e-posta uygulamasından** bağlanmayı denerse, yerel posta uygulaması MAM CA tarafından desteklenmediği için **yönetilen ve uyumlu bir cihaz** kullanması gerekir.
  * Bir kullanıcı **Windows ev bilgisayarından** bağlanmayı denerse, etki alanına katılan bir bilgisayar kullanmasını gerektiren **Cihaz CA ilkesi** uygulanır.




## <a name="next-steps"></a>Sonraki adımlar
[MAM uygulamaları için bir Exchange Online İlkesi oluşturma](mam-ca-for-exchange-online.md)

[Modern kimlik doğrulaması olmayan uygulamaları engelleme](block-apps-with-no-modern-authentication.md)

### <a name="see-also"></a>Ayrıca bkz.

[Uygulama verilerini MAM ilkeleriyle koruma](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


