---
title: "Şirket Portalı web sitesinden cihaz geçiş kodunuzu sıfırlama | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4fa3255b-9d1e-42d5-bd8b-70963dcf2d86
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 08eeb1f330ed8fcea5da41f71ded0ccf124da7c5
ms.openlocfilehash: 552217a59b7bfd9d75f8be1ce4c401d015ba84f7


---


# Şirket Portalı web sitesinden cihaz geçiş kodunuzu sıfırlama

Intune’a kaydettiğiniz bir cihazın PIN kodunu veya parolasını kaybederseniz, sıfırlamak için [Şirket Portalı web sitesini](http://portal.manage.microsoft.com) kullanabilirsiniz. Şirket Portalı web sitesi, Intune’a kaydettiğiniz bilgisayarları ve cihazları yönetmek ve Şirket Portalı uygulamasını kullanırken gerçekleştirebileceğiniz görevlerin çoğunu yapmak için kullanabileceğiniz bir web sayfasıdır.

> [!NOTE]
> BT yöneticinizin Intune’u nasıl yapılandırdığına bağlı olarak, Şirket Portalı web sitesinde Geçiş Kodunu Sıfırla düğmesini görmeyebilirsiniz. Windows 8.1 ve Windows RT cihazlarında Geçiş Kodu Sıfırlama desteklenmez.

Geçiş kodunuzu sıfırlamak için:

1.  [Şirket Portalı web sitesini](http://portal.manage.microsoft.com) açın ve geçiş kodunu sıfırlamak istediğiniz cihaza dokunun.

2.  **Geçiş Kodunu Sıfırla**’ya dokunun.

    ![resetp-passcode-option-on-company-portal-website](./media/iwp-screen-with-all-options.png)

3.  **Oturumu kapat**’a dokunun ve ardından iş veya okul kimlik bilgilerinizi kullanarak yeniden oturum açın. Beş dakika içinde yeniden oturum açmanız gerekir.

    ![sign-out-sign-back-in](./media/iwp-2-sign-out.png)

4.  **Geçiş Kodunu Sıfırla**’ya dokunun.

    ![tap-reset-passcode](./media/iwp-3-tap-reset-passcode-after-signin.png)

    Geçiş Kodu Sıfırlama işleminin cihazınızda nasıl çalıştığını görmek için tabloyu gözden geçirin.

    |Platform|Support|
    |------------|-----------|
    |Android|Yeni, geçici, alfasayısal bir geçiş kodu oluşturur.|
    |iOS|Geçiş kodu cihazdan kaldırılır ve yeni bir geçici geçiş kodu oluşturulmaz. Touch ID kullanıyorsanız, cihazınızda bunu yeniden ayarlamanız gerekir çünkü geçiş kodunuzu sıfırladığınızda o da kaldırılır.|
    |Windows 10 (yalnızca mobil cihazlar)|Yeni, geçici, alfasayısal bir geçiş kodu oluşturur. Windows Hello desteklenir.|
    |Windows Phone 8.1|Yeni, geçici, sayısal bir geçiş kodu oluşturur.|
    Cihazınızın kilidini açtıktan sonra, cihazda **Ayarlar**’a giderek yeni bir geçiş kodu ayarlayabilirsiniz.

5.  Cihazınızın kilidini açın ve cihazda **Ayarlar**’a giderek yeni bir geçiş kodu ayarlayın veya geçici geçiş kodunu değiştirin.

    Parolanızın başarıyla sıfırlandığını onaylayan bir bildirim görmek için, Şirket Portalı web sitesinin sağ üst kısmındaki bildirim bayrağına tıklayın.

Bu bilgiler yardımcı olmadı mı? BT yöneticinize başvurun. Kişi bilgileri için [Şirket Portalı Web sitesine](http://portal.manage.microsoft.com) bakın.





<!--HONumber=Aug16_HO5-->


