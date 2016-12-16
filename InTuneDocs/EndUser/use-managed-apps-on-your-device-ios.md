---
title: "iOS cihazınızdaki yönetilen uygulamaları kullanma | Microsoft Intune"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/24/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3232c5c1-cb9f-45ca-806f-7e74eeb3533e
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: maxles
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2f92ce22c9e6a87bccc7ab17144d0d52ff6cfc7b
ms.openlocfilehash: 340c160b2741856c91e7136fa60318c83b1ea8bb


---


# <a name="use-managed-apps-on-your-ios-device"></a>iOS cihazınızdaki yönetilen uygulamaları kullanma

Yönetilen uygulamalar, BT yöneticinizin ilgili uygulamada erişebildiğiniz şirket verilerini korumak üzere ayarlayabildiği uygulamalardır. iOS cihazınızdaki yönetilen bir uygulamada bulunan şirket verilerine eriştiğinizde uygulamanın beklediğinizden biraz farklı çalıştığını fark edebilirsiniz. Örneğin, korunan şirket verilerini kopyalayıp yapıştıramayabilir veya bu verileri belirli konumlara kaydedemeyebilirsiniz.

Ayrıca, günlük görevlerinizi yapmanıza imkan tanırken şirket verilerinizi korumayı sürdürmek için cihazınızda farklı yönetilen uygulamalar birlikte çalışabilir. Örneğin, yönetilen bir uygulamada bir şirket dosyası açarsanız ve bu dosyayı görüntülemek için başka bir yönetilen uygulama gerekli olursa, dosyayı görüntülemenizi sağlayan yönetilen uygulama otomatik olarak açılır. Gerekli bir uygulama kullanılabilir değilse, belge açma veya yönetilen bir belgeden bir web bağlantısına erişme gibi bazı eylemler gerçekleştirilemeyebilir.

Yönetilen bir uygulamadaki şirket verilerine eriştiğinizde, açmakta olduğunuz uygulamanın yönetildiğini bildiren aşağıdaki gibi bir ileti görürsünüz.

![managed-apps-message-ios](./media/managed-apps-message.png)

### <a name="how-do-i-get-managed-apps"></a>Yönetilen uygulamaları nasıl edinirim?
Yönetilen uygulamaları birkaç farklı yöntemle edinebilirsiniz:

-   Cihazınız Microsoft Intune’a kaydolduğunda uygulamayı Şirket Portalı uygulamasından veya Şirket Portalı web sitesinden yükleyebilirsiniz ya da uygulama BT yöneticiniz tarafından cihazınıza yüklenebilir. Kayıt hakkında bilgi edinmek için bkz. [iOS cihazınızı Intune’a kaydetme](enroll-your-device-in-intune-ios.md) veya [Mac OS X cihazınızı Intune’a kaydetme](enroll-your-device-in-intune-macos.md).

-   Bir uygulamayı App Store’dan yükleyin ve ardından Intune tarafından yönetilen şirket kullanıcı hesabınızla oturum açın.

### <a name="what-can-my-it-admin-manage-in-an-app"></a>BT yöneticim bir uygulamada neyi yönetebilir?
BT yöneticinizin bir uygulamada yönetebileceği ve cihazınızdaki şirket verileriyle etkileşimlerinizi etkileyebilecek seçeneklerin bazı örnekleri aşağıda verilmiştir:

-   Belirli web sitelerine erişim

-   Uygulamalar arasında veri aktarımları

-   Dosyaları kaydetme

-   Kopyalama ve yapıştırma işlemleri

-   PIN erişimi gereksinimleri

-   Şirket kimlik bilgilerini kullanarak oturum açma

-   Buluta yedekleme özelliği

-   Ekran görüntüleri alma özelliği

-   Veri şifreleme gereksinimleri


Cihazınızdaki yönetilen uygulamalar hakkında daha fazla bilgi için BT yöneticinizle iletişim kurun. Kişi bilgileri için [Şirket Portalı Web sitesine](http://portal.manage.microsoft.com) bakın.



<!--HONumber=Dec16_HO2-->


