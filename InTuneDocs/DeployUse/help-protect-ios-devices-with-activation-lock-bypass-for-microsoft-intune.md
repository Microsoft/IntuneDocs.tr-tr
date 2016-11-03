---
title: "Cihazlarda iOS Etkinleştirme Kilidi’ni yönetme | Microsoft Intune"
description: "Microsoft Intune, iOS 7.1 ve daha sonraki sürümlere sahip cihazlar için iPhone’umu Bul uygulamasının bir özelliği olan iOS Etkinleştirme Kilidi’ni yönetmenize yardımcı olabilir."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb49e926-15c4-4f01-b6eb-cee6f7ee1984
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d9e08429fb6c834476fd0029d559059c5132afca
ms.openlocfilehash: 2b44779fdac0764a3e7a18f1c365050e9800f902


---

# Microsoft Intune için Etkinleştirme Kilidi’ni atlama ile iOS cihazlarının korunmasına yardımcı olma
Microsoft Intune, iOS 8.0 ve daha sonraki sürümlere sahip cihazlar için iPhone’umu Bul uygulamasının bir özelliği olan iOS Etkinleştirme Kilidi’ni yönetmenize yardımcı olabilir. Bir cihazda kullanıcı tarafından iPhone’umu Bul uygulaması açıldığında Etkinleştirme Kilidi otomatik olarak etkinleştirilir. Bu özellik etkinleştirildikten sonra şunların yapılabilmesi için Apple kimliği ve parolasının girilmesi gerekir: 

-   iPhone’umu Bul özelliğini kapatma

-   Cihazı silme

-   Cihazı yeniden etkinleştirme

## Etkinleştirme Kilidi sizi nasıl etkiler
Etkinleştirme Kilidi iOS cihazlarının korunmasına yardımcı olmasına ve kaybolan ya da çalınan cihazların bulunma ihtimalini artırmasına rağmen, bir BT yöneticisi olarak size belirli zorluklar çıkarabilir. Örneğin:

-   Bir kullanıcı bir cihazda Etkinleştirme Kilidi’ni ayarlar. Daha sonra kullanıcı şirketten ayrılır ve cihazı iade eder. Kullanıcının Apple Kimliği ve parolası olmadan cihazı yeniden etkinleştirmenin yolu yoktur.

-   Etkinleştirme Kilidi’nin etkinleştirildiği tüm cihazların raporunu almanız gerekir.

-   Kurumunuzda cihaz yenileme işlemi sırasında bazı cihazları farklı bir birime atamak istiyorsunuz. Yalnızca Etkinleştirme Kilidi etkin olmayan cihazları yeniden atayabilirsiniz.

Apple bu sorunların çözülmesine yardımcı olmak için iOS 7.1’de Etkinleştirme Kilidi’ni atlama özelliğini kullanıma sunmuştur. Bu özellik, denetlenen cihazların Etkinleştirme Kilidi’ni kullanıcının Apple kimliği ve parolası olmadan kaldırmanıza imkan sağlar. Denetlenen cihazlar, Apple’ın etkinleştirme sunucusunda depolanan, cihaza özgü bir Etkinleştirme Kilidi’ni atlama kodu oluşturabilir.

> [!TIP]
> iOS cihazları için denetimli mod, Apple Configurator’ı kullanarak bir cihazı kilitlemenize ve cihaz işlevselliğini işe dönük belirli amaçlarla sınırlandırmanıza imkan tanır. Denetimli mod genellikle yalnızca şirkete ait cihazlar içindir.

## Intune, Etkinleştirme Kilidi’ni yönetmenize nasıl yardımcı olur
Intune, iOS 8.0 ve üzerini çalıştıran hem denetimli hem de denetimsiz cihazların Etkinleştirme Kilidi durumunu isteyebilir. Intune, yalnızca denetlenen cihazlar için Etkinleştirme Kilidi atlama kodunu alabilir ve doğrudan cihaza gönderebilir. Cihaz silinmişse, kodu kullanıcı adı gibi kullanıp parolayı boş bırakarak cihaza doğrudan erişebilirsiniz.

**Bu özelliğin işletme açısından faydaları şunlardır:**

-   Kullanıcı, iPhone’umu Bul Uygulamasının sunduğu güvenlik avantajlarından yararlanır.

-   Kullanıcıların kendi işlerini yapmasına imkan tanıyabilir ve cihazın başka bir amaçla kullanılması gerektiğinde cihazı devre dışı bırakabileceğinizi ya da cihazın kilidini açabileceğinizi bilirsiniz.

## Intune yönetim konsolundan Etkinleştirme Kilidi’ni atlama özelliğini kullanma
> [!IMPORTANT]
> Bir cihazda Etkinleştirme Kilidi’ni atladıktan sonra iPhone’umu Bul Uygulaması’nı açarsanız cihaza otomatik olarak yeni bir etkinleştirme kilidi uygulanır. Bu nedenle, **bu yordamı izlemeden önce cihaza fiziksel olarak sahip olmanız gerekir**.

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com), **Gruplar** &gt; **Tüm Cihazlar** &gt; **Şirkete Ait Tüm Cihazlar** öğesini seçin.

2.  Etkinleştirme Kilidi’ni atlamak istediğiniz cihazı seçin. **Etkinleştirme Kilidini Atlama**’yı seçin.

3.  Uyarı iletisini okuyun. Devam etmek için **Evet**’i seçin.

Cihaz ayrıntıları sayfasında kilit açma isteğinin durumunu inceleyebilirsiniz.

## Hangi cihazların etkinleştirme kilidi kullandığını görme
Hangi cihazların Etkinleştirme Kilidi kullandığını iki yolla görebilirsiniz:

-    **Mobil Cihaz Envanteri Raporları**’nı çalıştırın. Bu rapor, cihazların durumunu belirtmek için **Etkinleştirme Kilidi Durumu** ve **Denetimli** sütunlarını gösterir.  **Denetimli** sütunundaki değerler **Evet** veya **Hayır**, **Etkinleştirme Kilidi Durumu** sütunundakilerse şunlardır:

    -   Atlama koduyla etkinleştirildi

    -   Atlama kodu olmadan etkinleştirildi (cihaz denetlenmiyor)

    -   Atlama kodu olmadan etkinleştirildi (cihaza ulaşılamıyor)

    -   Etkin değil

    **Etkinleştirme Kilidi Durumu** kutusu, iOS 8.0 veya üzerini çalıştırmayan cihazlar için boştur.

-   Cihaz ayrıntıları bölmesinde Etkinleştirme Kilidi durumunu görmek için grup görünümünde bir cihaz seçin.

    **Şirkete Ait Tüm Cihazlar** düğümündeki bir cihazı seçerseniz ve cihaz için Etkinleştirme Kilidi etkinleştirilmişse atlama kodunu da görebilirsiniz. Bu kod kullanılarak el ile Etkinleştirme Kilidi’ni atlama komutu gönderilebilir.

    > [!IMPORTANT]
    >Intune, Etkinleştirme Kilidi için her yedi günde bir cihazlardan envanter alır. Bu nedenle, Intune konsolunda cihazların Etkinleştirme Kilidi durumu hemen görüntülenmeyebilir.


### Ayrıca bkz.
[Cihazları devre dışı bırakma](retire-devices-from-microsoft-intune-management.md)
[Uzak kilitleme ve parola sıfırlama özellikleriyle cihazlarınızın korunmasına yardımcı olma](use-remote-lock-and-passcode-reset-in-microsoft-intune.md)



<!--HONumber=Sep16_HO2-->


