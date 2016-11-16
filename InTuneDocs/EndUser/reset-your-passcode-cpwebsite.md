---
title: "Şirket Portalı web sitesinden cihaz geçiş kodunuzu sıfırlama | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
ms.author: stabar
manager: angrobe
ms.date: 09/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4fa3255b-9d1e-42d5-bd8b-70963dcf2d86
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2aea845bc00c153f070e04abb67582a5d5a726ca
ms.openlocfilehash: 47b36616f7a8ee23d4d47b41a1db2c41c185c6f5


---


# Şirket Portalı web sitesinden cihaz geçiş kodunuzu sıfırlama

Intune’a kaydettiğiniz bir cihazın PIN kodunu veya parolasını kaybederseniz, sıfırlamak için [Şirket Portalı web sitesini](http://portal.manage.microsoft.com) kullanabilirsiniz. Intune’a kaydettiğiniz bilgisayarları ve cihazları yönetmek ve Şirket Portalı uygulamasını kullanırken gerçekleştirebileceğiniz görevlerin çoğunu yapmak için Şirket Portalı web sitesini kullanabilirsiniz.

> [!NOTE]
> BT yöneticinizin Intune’u nasıl yapılandırdığına bağlı olarak, Şirket Portalı web sitesinde **Geçiş Kodunu Sıfırla** düğmesini görmeyebilirsiniz. Windows 8.1 cihazlarında Geçiş kodu sıfırlama desteklenmez.

Geçiş kodunuzu sıfırlamak için:

1.  [Şirket Portalı web sitesini](http://portal.manage.microsoft.com) açın ve geçiş kodunu sıfırlamak istediğiniz cihazı seçin.

2.  **Geçiş Kodunu Sıfırla**’yı seçin.

    ![Geçiş Kodunu Sıfırla düğmesi ile cihaz ayrıntıları](./media/iwp-screen-with-all-options.png)

3.  **Oturumu kapat**’ı seçin ve ardından iş veya okul kimlik bilgilerinizi kullanarak yeniden oturum açın. Beş dakika içinde yeniden oturum açmanız gerekir.

    ![Oturum kapatma düğmesi ile sıfırlama iletisi](./media/iwp-2-sign-out.png)

4.  **Geçiş Kodunu Sıfırla**’yı seçin.

    ![Geçiş kodunu sıfırladığınızda neler olacağını açıklayan ileti](./media/iwp-3-tap-reset-passcode-after-signin.png)

    **Geçiş Kodu Sıfırlama** işleminin cihazınızda nasıl çalıştığını görmek için tabloyu gözden geçirin.

    |Platform|Support|
    |------------|-----------|
    |Android|Geçici, alfasayısal bir geçiş kodu oluşturur.|
    |iOS|Geçiş kodu cihazdan kaldırılır ve geçici geçiş kodu oluşturulmaz. Touch ID kullanıyorsanız, cihazınızda bunu yeniden ayarlamanız gerekir çünkü geçiş kodunuzu sıfırladığınızda o da kaldırılır.|
    |Windows 10 (yalnızca mobil cihazlar)|Geçici, alfasayısal bir geçiş kodu oluşturur. Windows Hello desteklenir.|
    |Windows Phone 8.1|Geçici, sayısal bir geçiş kodu oluşturur.|
    Cihazınızın kilidini açtıktan sonra, cihazda **Ayarlar**’a giderek yeni bir geçiş kodu ayarlayabilirsiniz.

5.  Cihazınızın kilidini açın ve cihazda **Ayarlar**’a giderek yeni bir geçiş kodu ayarlayın veya geçici geçiş kodunu değiştirin.

    Parolanızın başarıyla sıfırlandığını onaylayan bir bildirim görmek için, Şirket Portalı web sitesinin sağ üst kısmındaki bildirim bayrağına tıklayın.

Bu bilgiler yardımcı olmadı mı? BT yöneticinize başvurun. Kişi bilgileri için [Şirket Portalı Web sitesine](http://portal.manage.microsoft.com) bakın.



<!--HONumber=Oct16_HO3-->


