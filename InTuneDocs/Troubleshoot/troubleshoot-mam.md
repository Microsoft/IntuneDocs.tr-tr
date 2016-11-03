---
title:
- "Mobil uygulama yönetimi sorunlarını giderme | Microsoft Intune"
description: 
keywords: 
author: karaman
manager: angerobe
ms.date: 09/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd5a0a3b-0013-4be3-a233-ce6e9083149f
translationtype: Human Translation
ms.sourcegitcommit: 9cfb3694b2fae919fd0554a6e21b497cdcf19c72
ms.openlocfilehash: f33e8de82ee07bb4571a5bfaff63af72f9086376


---

# Mobil uygulama yönetimi sorunlarını giderme

Mobil uygulama yönetimi ile ilgili sorun yaşıyorsanız, buradan başlayın. Bu konuda, karşılaşabileceğiniz bazı yaygın sorunlar çözümleriyle birlikte sunulmuştur.


**Sorun:** Azure konsolundan Kayıt ilkesi bulunmayan MAM, Skype Kurumsal uygulamasına iOS ve Android cihazlarda uygulanamıyor.

Çözünürlük: Skype Kurumsal’ın modern kimlik doğrulaması için ayarlanması gerekir.  Skype için modern kimlik doğrulamasını ayarlamak için lütfen [Modern kimlik doğrulaması için kiracınızı etkinleştirme](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) bölümündeki yönergeleri izleyin.

**Sorun:** Kayıt ilkeleri bulunmayan MAM, herhangi bir kullanıcı için herhangi bir (desteklenen Office Uygulamasına)[https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners] uygulanamıyor.
 
Çözüm: Kullanıcının Intune lisansı olduğunu onaylayın.  

**Sorun:** BT yöneticisi Azure Portalı’nda MAM ilkelerini yapılandıramıyor

Çözüm: Azure Portalı’na aşağıdaki rollerin erişimi vardır:

- [Office Portalı](http://portal.office.com/)’nda ayarlayabileceğiniz genel yönetici
- [Azure Portalı](https://portal.azure.com/)’nda ayarlayabileceğiniz sahip.
- [Azure Portalı](https://portal.azure.com/)’nda ayarlayabileceğiniz katkıda bulunan.

Bu rolleri ayarlama konusunda yardım almak için bkz. [Microsoft Intune ile mobil uygulama yönetimi ilkelerinizi yapılandırmak için hazırlama](https://docs.microsoft.com/en-us/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune). 

**Sorun:** Uygulama raporu, MAM ilkesini son hedeflediğimiz kullanıcı veya kullanıcıları göstermiyor.

Çözüm: Bir kullanıcı bir MAM ilkesiyle yeni hedeflenmişse, raporlarda bu kullanıcının hedeflenen kullanıcı olarak görünmesi 24 saate kadar sürebilir. 

**Sorun:** İlke değişiklikleri/güncelleştirmelerinin uygulanması 8 saate kadar sürebiliyor.  

Çözüm: Son kullanıcı uygulama oturumunu kapatıp hizmetle eşitlemeyi zorlayarak tekrar oturum açabilir.  

**Sorun:** MAM ilkesi Apple DEP cihazlara uygulanmıyor

Çözüm: Lütfen Kullanıcı Benzeşimini Apple Aygıt Kayıt Programı (DEP) ile kullandığınızdan emin olun. Kullanıcı benzeşimi, DEP altında kullanıcı kimlik doğrulaması gerektiren her uygulama için gereklidir.
iOS DEP kaydı hakkında daha fazla bilgi için bkz. [Şirkete ait Cihaz Kayıt Programı iOS cihazlarını kaydetme](https://docs.microsoft.com/en-us/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune).


### Ayrıca bkz.
- [Mobil uygulama yönetimi kurulumunuzu doğrulama](https://docs.microsoft.com/en-us/intune/deploy-use/validate-mobile-application-management)
- [Microsoft Intune ile mobil uygulama yönetimi ilkelerinizi yapılandırmak için hazırlama](https://docs.microsoft.com/en-us/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) 





<!--HONumber=Sep16_HO2-->


