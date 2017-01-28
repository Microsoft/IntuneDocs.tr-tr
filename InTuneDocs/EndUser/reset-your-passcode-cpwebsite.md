---
title: "Şirket Portalı web sitesinden cihaz geçiş kodunuzu sıfırlama | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4fa3255b-9d1e-42d5-bd8b-70963dcf2d86
searchScope:
- Company Portal
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: beba9603ffb43d025132d2d86f0996ff505a9019
ms.openlocfilehash: f9d66fe07173245ff831f204dd120598ad7564db


---

# <a name="how-to-reset-your-device-passcode-from-the-company-portal-website"></a>Şirket Portalı web sitesinden cihaz geçiş kodunuzu sıfırlama

Intune’a kaydettiğiniz bir cihazın PIN kodunu veya parolasını kaybederseniz, sıfırlamak için [Şirket Portalı web sitesini](http://portal.manage.microsoft.com) kullanabilirsiniz. Intune’a kaydettiğiniz bilgisayarları ve cihazları yönetmek ve Şirket Portalı uygulamasını kullanırken gerçekleştirebileceğiniz görevlerin çoğunu yapmak için Şirket Portalı web sitesini kullanabilirsiniz.

> [!NOTE]
> Şirket Portalı web sitesinde **Geçiş Kodunu Sıfırlama ** düğmesini görmemeniz olasıdır. Görmezseniz, Şirket Portalı web sitesinden destek almak için BT yöneticinize başvurmanız gerekir.

Geçiş kodunuzu sıfırlamak için:

1.  [Şirket Portalı web sitesini](http://portal.manage.microsoft.com) açın ve geçiş kodunu sıfırlamak istediğiniz cihazı seçin.

2.  **Geçiş Kodunu Sıfırla**’yı seçin.

    ![Geçiş Kodunu Sıfırla düğmesi ile cihaz ayrıntıları](./media/iwp-screen-with-all-options.png)

3.  **Oturumu kapat**’ı seçin ve ardından iş veya okul kimlik bilgilerinizi kullanarak yeniden oturum açın. Beş dakika içinde yeniden oturum açmanız gerekir.

    ![Oturum kapatma düğmesi ile sıfırlama iletisi](./media/iwp-2-sign-out.png)

4.  **Geçiş Kodunu Sıfırla**’yı seçin.

    ![Geçiş kodunu sıfırladığınızda neler olacağını açıklayan ileti](./media/iwp-3-tap-reset-passcode-after-signin.png)

    **Geçiş Kodu Sıfırlama** işleminin cihazınızda nasıl çalıştığını görmek için tabloyu gözden geçirin.

    |Cihaz Türü|Sıfırladığınızda Ne Olur|
    |------------|-----------|
    |Android|Mevcut geçiş kodu kaldırılır ve harf ve sayılarla geçici bir geçiş kodu oluşturulur|
    |iOS|Geçiş kodu kaldırılır ve geçici bir geçiş kodu oluşturulmaz. Cihazınızı açmak veya satın alma işlemleri yapmak için Touch ID parmak izi tarayıcısını kullanıyorsanız, yeniden kurmanız gerekecektir.|
    |Windows 10 Mobile|Mevcut geçiş kodu kaldırılır ve harf ve sayılarla geçici bir geçiş kodu oluşturulur. Oturum açmak için Windows Hello yüz tanımayı kullanıyorsanız yine de desteklenecektir.|
    |Windows Phone 8.1|Mevcut geçiş kodu kaldırılır ve sayılarla geçici bir geçiş kodu oluşturulur.|

    5.  Cihazınızın kilidini açın ve yeni bir geçiş kodu ayarlayın veya cihazınızın **Ayarlar**’ına giderek geçici geçiş kodunu değiştirin.

    Parolanızın başarıyla sıfırlandığını onaylayan bir bildirim görmek için, Şirket Portalı web sitesinin sağ üst kısmındaki bildirim bayrağına tıklayın.

Bu bilgiler yardımcı olmadı mı? BT yöneticinize başvurun. Kişi bilgileri için [Şirket Portalı Web sitesine](http://portal.manage.microsoft.com) bakın.



<!--HONumber=Jan17_HO1-->


