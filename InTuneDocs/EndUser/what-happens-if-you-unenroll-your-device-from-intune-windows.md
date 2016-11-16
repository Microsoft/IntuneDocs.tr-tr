---
title: "Windows cihazınızın Intune kaydını sildiğinizde ne olur? | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
ms.author: stabar
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47e03edb-0c57-4e25-8e89-4a1069267b8c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 8975e57c604565c57c86472564ab660aed560a7b
ms.openlocfilehash: 22179d5d80d2b24e61778249367bec6845290206


---


# Windows cihazınızın Intune kaydını sildiğinizde ne olur?

Bu sayfanın sağ tarafında, **Bu makalede** bölümü altındaki bağlantıları kullanarak kullandığınız cihaz türü hakkında bilgi alabilirsiniz.


## Windows 10, Windows 8.1, Windows 8, Windows 7, Windows Vista

-   Cihazınız artık Şirket Portalı’nda görünmez ve Şirket Portalı’ndan uygulama yükleyemezsiniz.

-   Intune istemci yazılımını yüklediyseniz, bilgisayarınızdan kaldırılır.

-   Intune Endpoint Protection yazılımı bilgisayarınızdan kaldırılır. Bilgisayarınızda başka bir virüsten koruma yazılımı yüklüyse ve yazılım devre dışıysa, Intune Endpoint Protection kaldırıldıktan sonra bu yazılım yeniden etkinleştirilebilir. Şirket Portalı’ndan kaldırdıktan sonra bilgisayarınızı kontrol edin.

    > [!IMPORTANT]
    > Diğer bir virüsten koruma yazılımı yeniden etkinleştirilmediyse veya bir virüsten koruma yazılımı yüklü değilse, bilgisayarınız virüs ve kötü amaçlı yazılımlara açık halde olabilir.

-   Cihazı eklediğinizde değiştirilen tüm ayarlar, mesela kamerayı devre dışı bırakmak gibi ayarlar geçerliliğini kaybeder.

-   Bilgisayarınız artık Intune hizmetinden otomatik yazılım güncelleştirmeleri veya virüsten koruma yazılımı güncelleştirmeleri almaz. Ancak, bilgisayarınızın nasıl ayarlandığına bağlı olarak Windows Server Update Services, Windows Update veya Microsoft Update'den güncelleştirme almaya devam edebilir.

Ayrıca, Windows 8.1 için:

-   Cihazınızda artık şirket uygulamalarını ve şirket verilerini kullanamazsınız.

-   Windows Mail gibi bazı e-posta uygulamaları artık cihazınızda depolanan şirket e-postalarına erişemez.

-   Wi-Fi veya bir sanal özel ağ kullanarak şirket ağınıza bağlanamayabilirsiniz.

-   Dosya paylaşımları veya dahili web siteleri gibi şirket kaynaklarına erişemeyebilirsiniz.

## Windows 10 Mobile ve Windows Phone 8.1

-   Şirket Portalı uygulaması cihazınızdan kaldırılır. Bu, cihazınızın artık Şirket Portalı’nda görünmeyeceği ve Şirket Portalı uygulamasından veya Şirket Portalı web sitesinden uygulama yükleyemeyeceğiniz anlamına gelir.

-   Cihazınızda artık şirket uygulamalarını ve şirket verilerini kullanamazsınız.

-   Cihazı eklediğinizde değiştirilen tüm ayarlar, mesela kamerayı devre dışı bırakmak veya belirli bir parola uzunluğu gerekliliği gibi ayarlar geçerliliğini kaybeder.

    > [!IMPORTANT]
    > Bu durumda geçerli olmaya devam edecek tek özel durum şifreleme ilkesidir. Şirket ilkeniz Windows Phone'unuzun şifrelenmesini gerektiriyorsa, telefonunuzun şifresini kaldırmanın tek yolu **Ayarlar** menüsünü kullanarak telefonunuzu sıfırlamaktır.

## Windows 8.1 çalıştıran Windows RT

-   Şirket Portalı uygulaması cihazınızdan kaldırılır. Bu, cihazınızın artık Şirket Portalı’nda görünmeyeceği ve Şirket Portalı’ndan uygulama yükleyemeyeceğiniz anlamına gelir.

-   Cihazınızda artık şirket uygulamalarını ve şirket verilerini kullanamazsınız.

-   Cihazı eklediğinizde değiştirilen tüm ayarlar, mesela kamerayı devre dışı bırakmak veya belirli bir parola uzunluğu gerekliliği gibi ayarlar geçerliliğini kaybeder.

-   Wi-Fi veya bir sanal özel ağ kullanarak şirket ağınıza bağlanamayabilirsiniz.

-   Dosya paylaşımları veya dahili web siteleri gibi şirket kaynaklarına erişemeyebilirsiniz.

-   Windows Mail gibi bazı e-posta uygulamaları artık cihazınızda depolanan şirket e-postalarına erişemez.

Windows RT cihazınızı kaldırdığınızda şunlar olur:

-   Şirket Portalı uygulaması cihazınızdan kaldırılır. Bu, cihazınızın artık Şirket Portalı’nda görünmeyeceği ve Şirket Portalı’ndan uygulama yükleyemeyeceğiniz anlamına gelir.

-   Cihazınızda artık şirket uygulamalarını ve şirket verilerini kullanamazsınız.

-   Cihazı eklediğinizde değiştirilen tüm ayarlar, mesela kamerayı devre dışı bırakmak veya belirli bir parola uzunluğu gerekliliği gibi ayarlar geçerliliğini kaybeder.

Sorularınız varsa BT yöneticinizle iletişime geçin. Kişi bilgileri için [Şirket Portalı Web sitesine](http://portal.manage.microsoft.com) bakın.



<!--HONumber=Oct16_HO3-->


