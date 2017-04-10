---
title: "Office 365 mobil uygulamalarından şirket veri sızıntılarını önleme | Microsoft Docs"
description: "Office 365 mobil uygulamalarından veya diğer iş kolu (LOB) uygulamalarından şirket verilerinin sızmasını önlemeye yardımcı olan mobil uygulama yönetimi (MAM) ilkeleri ile kuruluşunuzun verilerinin güvenliğini sağlamak için Intune kullanın."
keywords: 
author: jeffgilb
ms.author: jeffgilb
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 19be3de7-539c-49f5-8c46-5363b987fef9
ms.reviewer: pchacon
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: f268cf29461447306d0f5c3ca06d541d9a03a49d
ms.openlocfilehash: 0288ecd940d650304d83b7dd5803a56f69b936f7


---

# <a name="quick-start-guide-prevent-company-data-leaks-from-office-365-mobile-apps"></a>Hızlı Başlangıç Kılavuzu: Office 365 mobil uygulamalarından şirket veri sızıntılarını önleme

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune, Office 365 mobil uygulamalarından veya diğer iş kolu (LOB) uygulamalarından şirket verilerinin sızmasını önlemeye yardımcı olan mobil uygulama yönetimi (MAM) ilkelerini kullanarak kuruluşunuzun verilerinin güvenliğini sağlamanıza yardımcı olabilir. Intune MAM ilkeleri, son kullanıcıların cihazlarını Intune mobil cihaz yönetimine (MDM) kaydetmesini gerektirmeden kullanılabilir. Bu nedenle, BYOD iOS veya Android mobil cihazlarını bir Microsoft MDM çözümüne (Intune, Configuration Manager veya EAS) kaydetmek istemeyen kullanıcılarınız varsa, kurumsal verileri son kullanıcı cihazlarını yönetmeden korumak istiyorsanız veya zaten Microsoft olmayan bir MDM çözümünü kullanıyorsanız, Intune şirketinizin veri güvenliğini artırmanıza yardımcı olabilir.   

## <a name="is-this-quick-start-guide-right-for-me"></a>Bu hızlı başlangıç kılavuzu bana uygun mu?
Son kullanıcılarınızın bir Mobil Cihaz Yönetimi (MDM) çözümüne cihaz kaydetmek zorunda kalmadan iOS ve Android cihazlarından Office 365 ve LOB uygulaması verilerine erişmesine izin vermek, ancak bu verilerle bunları kopyalayıp kişisel uygulamalarına yapıştırmak gibi yapabilecekleri veya yapamayacakları şeyleri denetlemeyi de sürdürmek istiyor musunuz?

Yanıtınız evet ise, Microsoft Intune, iOS ve Android cihazlarda Office 365 mobil uygulamaları için kes/kopyala/yapıştır kısıtlamaları koyma, ‘farklı-kaydet’ işlevini engelleme, PIN gereksinimlerini ayarlama ve MAM ile korunan verileri uzaktan silme olanağı gibi MAM ilkeleri belirlemenize izin verir.  Bu özellik, kullanıcıların cihazlarını bir MDM çözümüne kaydetmelerini gerektirmeden şirket verilerini korurken Office mobil uygulamalarında da çok iyi bir kullanıcı deneyimi sağlar.

## <a name="how-do-i-do-it"></a>Bunu nasıl yaparım?
1.    [Intune mobil uygulama yönetiminin (MAM)](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) nasıl çalıştığını temel düzeyde anlayın.
2.    Azure portalında [MAM ilkeleri oluşturmak için önce neler yapmanız gerektiğini](/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) öğrenin.
3.    Intune ile [MAM ilkeleri oluşturun ve dağıtın](/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune).

### <a name="additional-information"></a>Ek bilgiler:
- MAM etkinleştirilmiş uygulamalarla [son kullanıcı deneyimi](/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune).
- [Intune ile MAM için LOB uygulamaları hazırlama](/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune)
- <a href="https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners" target="_blank">MAM özellikli uygulamalar sağlayan Microsoft Intune uygulaması iş ortaklarının listesi &rarr;</a>.

## <a name="what-should-i-do-next"></a>Bundan sonra ne yapmalıyım?
[Microsoft olmayan bir MDM çözümünden Microsoft Intune’a geçme](/intune/deploy-use/migrate-to-intune)

[Intune MDM'ye cihaz kaydetme](/intune/deploy-use/enroll-devices-in-microsoft-intune)



<!--HONumber=Dec16_HO3-->


