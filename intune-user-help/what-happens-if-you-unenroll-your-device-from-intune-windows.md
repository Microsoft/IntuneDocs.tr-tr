---
title: Windows cihazınızın kaydını sildiğinizde ne olur? | Microsoft Docs
description: ''
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 01/23/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 47e03edb-0c57-4e25-8e89-4a1069267b8c
searchScope:
- User help
ROBOTS: ''
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 92cd7969dafb133cf044e2bf5fd2c6d0f829f6ff
ms.sourcegitcommit: 490365fb8b5405f323b4358fb1ec9dfdd9ff2d58
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43150387"
---
# <a name="what-happens-if-you-unenroll-your-windows-device-from-intune"></a>Windows cihazınızın Intune kaydını sildiğinizde ne olur?

Bu sayfanın sağ tarafında, **Bu makalede** bölümü altındaki bağlantıları kullanarak kullandığınız cihaz türü hakkında bilgi alabilirsiniz.


## <a name="windows-10-windows-81-windows-8-windows-7-windows-vista"></a>Windows 10, Windows 8.1, Windows 8, Windows 7, Windows Vista

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

## <a name="windows-10-mobile-and-windows-phone-81"></a>Windows 10 Mobile ve Windows Phone 8.1

-   Şirket Portalı uygulaması cihazınızdan kaldırılır. Bu, cihazınızın artık Şirket Portalı’nda görünmeyeceği ve Şirket Portalı uygulamasından veya Şirket Portalı web sitesinden uygulama yükleyemeyeceğiniz anlamına gelir.

-   Cihazınızda artık şirket uygulamalarını ve şirket verilerini kullanamazsınız.

-   Cihazı eklediğinizde değiştirilen tüm ayarlar, mesela kamerayı devre dışı bırakmak veya belirli bir parola uzunluğu gerekliliği gibi ayarlar geçerliliğini kaybeder.

    > [!IMPORTANT]
    > Bu durumda geçerli olmaya devam edecek tek özel durum şifreleme ilkesidir. Şirket ilkeniz Windows Phone'unuzun şifrelenmesini gerektiriyorsa, telefonunuzun şifresini kaldırmanın tek yolu **Ayarlar** menüsünü kullanarak telefonunuzu sıfırlamaktır.

## <a name="windows-rt-running-windows-81"></a>Windows 8.1 çalıştıran Windows RT

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

Sorularınız varsa şirketinizin destek birimiyle iletişime geçin. Kişi bilgileri için [Şirket Portalı Web sitesine](https://go.microsoft.com/fwlink/?linkid=2010980) bakın.
