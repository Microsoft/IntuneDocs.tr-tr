---
title: "Şirket Portalı web sitesinden geçiş kodunuzu sıfırlama | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4fa3255b-9d1e-42d5-bd8b-70963dcf2d86
searchScope:
- User help
ROBOTS: 
ms.reviewer: mamoriss
ms.suite: ems
ms.custom: intune-enduser
translationtype: Human Translation
ms.sourcegitcommit: f293901d3865f0b10ed876e83b151cf59a046cba
ms.openlocfilehash: 68725bb63ae2750e89a03c16027f8b4fd9111255
ms.lasthandoff: 02/24/2017


---

# <a name="how-to-reset-your-device-passcode-from-the-company-portal-website"></a>Şirket Portalı web sitesinden cihaz geçiş kodunuzu sıfırlama

Intune’a kaydettiğiniz bir cihazın PIN kodunu veya parolasını kaybederseniz, sıfırlamak için [Şirket Portalı web sitesini](http://portal.manage.microsoft.com) kullanabilirsiniz. Intune’a kaydettiğiniz bilgisayarları ve cihazları yönetmek ve Şirket Portalı uygulamasını kullanırken gerçekleştirebileceğiniz görevlerin çoğunu yapmak için Şirket Portalı web sitesini kullanabilirsiniz.

> [!NOTE]
> Şirket Portalı web sitesinde **Geçiş Kodunu Sıfırlama ** düğmesini görmemeniz olasıdır. Görmezseniz, Şirket Portalı web sitesinden destek almak için BT yöneticinize başvurmanız gerekir.

Geçiş kodunuzu sıfırlamak için:

1.    [Şirket Portalı web sitesinde](http://portal.manage.microsoft.com), __menü__ düğmesine dokunun ![Üç yatay çubuk paralel olarak dizili şekilde menü düğmesinin küçük bir resmi.](/Intune/whats-new/media/CP_hamburger_menu.png), ardından __Cihazlarım__’ı seçin.

2. __Cihazlarım__ sayfasında, geçiş kodunu sıfırlamak istediğiniz cihazın adını seçin.

  ![Listelenmemiş cihazları kaydetme veya tanımlanmamış cihazları tanımlama başlık isteminin üzerinde birkaç tanımlanmamış cihazın belirtildiği Cihazlarım sayfasının ekran görüntüsü.](./media/macOS_enroll_002_tap_here_banner.png)

3.    Cihaz, bir açılan pencere içinde açılır. **Geçiş Kodunu Sıfırla** düğmesini seçin.

    ![Şirket Portalı web sitesinde seçilen bir cihaza yönelik Yeniden Adlandır, Kaldır, Cihazı Sıfırla, Geçiş Kodunu Sıfırla ve Uzaktan Kilitleme dahil tüm seçenekler. ](./media/iwp-screen-with-all-options.png)

4.  Geçiş kodunuzu sıfırlamak istediğinizi doğrulamanızı isteyen bir başlık görünür ve bunu yaptıktan sonra cihazınız oturumunuzu kapatır. Tekrar oturum açmadan önce 5 dakika beklemeniz gerekir.

  ![Geçiş kodunu sıfırlama ve kullanıcının oturumunun nasıl kapatılacağı hakkında uyarı içeren geçiş kodunu sıfırlama başlığı. Oturumu Kapat ve İptal Et, kullanıcı girişine yönelik düğmelerdir.](./media/iwp-reset-passcode-popup.png)

4.  **Oturumu kapat**’ı seçmenizle birlikte, cihazdan geçiş kodunun kaldırıldığını size bildiren son iletiyi alırsınız. Cihaz yanınızda değilse geçiş kodunu kaldırmayın, aksi takdirde cihaza fiziksel erişimi olan herhangi biri, cihazdaki bilgilerin (şirket bilgileri veya kişisel bilgiler) çoğuna erişebilir.

  ![Cihaz geçiş kodunu sıfırlama ve geçiş kodunun cihazdan nasıl kaldırılacağı uyarısıyla birlikte ikinci geçiş kodunu sıfırlama başlığı. Cihaz ayarlarına giderek yeni bir geçiş kodu belirlemenizi de önerir.](./media/iwp-reset-passcode-2nd-popup.png)


Farklı cihazlar farklı türde geçiş kodlarına sahip olduğundan, geçiş kodunuzu sıfırlamanın belirli cihazınızı nasıl etkileyeceğini aşağıdaki tabloda görebilirsiniz. 

    |Cihaz Türü|Sıfırladığınızda Ne Olur|
    |------------|-----------|
    |Android|Mevcut geçiş kodu kaldırılır ve harf ve sayılarla geçici bir geçiş kodu oluşturulur|
    |iOS|Geçiş kodu kaldırılır ve geçici bir geçiş kodu oluşturulmaz. Cihazınızı açmak veya satın alma işlemleri yapmak için Touch ID parmak izi tarayıcısını kullanıyorsanız, yeniden kurmanız gerekecektir.|
    |Windows 10 Mobile|Mevcut geçiş kodu kaldırılır ve harf ve sayılarla geçici bir geçiş kodu oluşturulur. Oturum açmak için Windows Hello yüz tanımayı kullanıyorsanız yine de desteklenecektir.|
    |Windows Phone 8.1|Mevcut geçiş kodu kaldırılır ve sayılarla geçici bir geçiş kodu oluşturulur.|

    5.  Cihazınızın kilidini açın ve yeni bir geçiş kodu ayarlayın veya cihazınızın **Ayarlar**’ına giderek geçici geçiş kodunu değiştirin.

    Parolanızın başarıyla sıfırlandığını onaylayan bir bildirim görmek için, Şirket Portalı web sitesinin sağ üst kısmındaki bildirim bayrağına tıklayın.

Bu bilgiler yardımcı olmadı mı? BT yöneticinize başvurun. Kişi bilgileri için [Şirket Portalı Web sitesine](http://portal.manage.microsoft.com) bakın.

