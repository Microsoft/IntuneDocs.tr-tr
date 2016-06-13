---
# required metadata

title: Etkinleştirme Kilidi’ni atlama ile iOS cihazlarının korunmasına yardımcı olma | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: bb49e926-15c4-4f01-b6eb-cee6f7ee1984

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune için Etkinleştirme Kilidi’ni atlama ile iOS cihazlarının korunmasına yardımcı olma
Microsoft Intune, iOS 7.1 ve daha sonraki sürümlere sahip cihazlar için iPhone’umu Bul uygulamasının bir özelliği olan iOS Etkinleştirme Kilidi’ni yönetmenize yardımcı olabilir. Bir cihazda iPhone’umu Bul uygulaması kullanıldığında Etkinleştirme Kilidi otomatik olarak etkinleştirilir. Bu özellik etkinleştirildikten sonra şunların yapılabilmesi için Apple kimliği ve parolasının girilmesi gerekir:

-   iPhone’umu Bul özelliğini kapatma

-   Cihazı silme

-   Cihazı yeniden etkinleştirme

## Etkinleştirme Kilidi sizi nasıl etkiler
Etkinleştirme Kilidi iOS cihazlarının korunmasına yardımcı olur ve cihazın kaybolması ya da çalınması durumunda bulunmasını kolaylaştırır, ancak bir BT yöneticisi olarak size belirli zorluklar çıkarabilir. Örneğin:

-   Kullanıcılarınızdan biri, bir cihazda Etkinleştirme Kilidi’ni ayarlar. Daha sonra kullanıcı şirketten ayrılır ve cihazı iade eder. Kullanıcının Apple Kimliği ve parolası olmadan cihazı yeniden etkinleştirmenin yolu yoktur.

-   Etkinleştirme Kilidi’nin etkinleştirildiği tüm cihazların raporunu almanız gerekir.

-   Kurumunuzda bir cihaz yenileme işlemi sırasında bazı cihazları farklı bir birime atamak istiyorsunuz. Yalnızca Etkinleştirme Kilidi etkin olmayan cihazları yeniden atayabilirsiniz.

Apple bu sorunların çözülmesine yardımcı olmak için iOS 7.1’de Etkinleştirme Kilidi’ni atlama özelliğini kullanıma sunmuştur. Bu özellik, denetlenen cihazların Etkinleştirme Kilidi’ni kullanıcının Apple kimliği ve parolası olmadan kaldırmanıza imkan sağlar. Denetlenen cihazlar, Apple’ın etkinleştirme sunucusunda depolanan, cihaza özgü bir Etkinleştirme Kilidi’ni atlama kodu oluşturabilir.

> [!TIP]
> iOS cihazları için denetimli mod, Apple Yapılandırıcı Aracı’nı kullanarak bir cihazın işlevselliğini işe dönük belirli amaçlarla sınırlandırmak için bir cihazı kilitlemenize imkan tanır. Denetimli mod genellikle yalnızca şirkete ait cihazlar içindir.

## Intune, Etkinleştirme Kilidi’ni yönetmenize nasıl yardımcı olur
Intune, iOS 7.1 ve sonraki sürümleri çalıştıran hem denetimli hem de denetimsiz cihazların Etkinleştirme Kilidi durumunu isteyebilir. Intune, yalnızca denetlenen cihazlar için Etkinleştirme Kilidi atlama kodunu alabilir ve doğrudan cihaza gönderebilir. Cihaz silinmişse, kodu kullanıcı adı gibi kullanarak, parolayı da boş bırakarak cihaza doğrudan erişebilirsiniz.

**Bu özelliğin işletme açısından faydaları şunlardır:**

-   Kullanıcı, iPhone’umu Bul Uygulamasının sunduğu güvenlik avantajlarından yararlanır.

-   Kullanıcının kendi işlerini yapmasına imkan tanırken, cihazın başka bir amaçla kullanılması gerektiğinde cihazı devre dışı bırakabileceğinizi veya cihazın kilidini açabileceğinizi bilirsiniz.

## Intune yönetim konsolundan Etkinleştirme Kilidi’ni atlama özelliğini kullanma
> [!IMPORTANT]
> Bir cihazda Etkinleştirme Kilidi’ni atladıktan sonra iPhone’umu Bul Uygulaması açılırsa cihaz otomatik olarak yeni bir etkinleştirme kilidi uygular. Bu nedenle, **bu yordamı izlemeden önce cihaza fiziksel olarak sahip olmanız gerekir**.

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com), **Gruplar** &gt; **Tüm Cihazlar** &gt; **Şirkete Ait Tüm Cihazlar** öğesini seçin.

2.  Etkinleştirme Kilidi’ni atlamak istediğiniz cihazı seçin. **Etkinleştirme Kilidini Atlama**’yı seçin.

3.  Uyarı iletisini okuyun. Devam etmek için **Evet**’i seçin.

Cihaz ayrıntıları sayfasında kilit açma isteğinin durumunu inceleyebilirsiniz.

## Hangi cihazların etkinleştirme kilidi kullandığını görme
Hangi cihazların Etkinleştirme Kilidi kullandığını iki yolla görebilirsiniz:

-    **Mobil Cihaz Envanteri Raporları**’nı çalıştırın. Bu rapor, cihazların durumunu göstermek için **Etkinleştirme Kilidi Durumu** ve **Denetimli** sütunlarını görüntüler.  **Denetimli** sütunundaki değerler **Evet** veya **Hayır**, **Etkinleştirme Kilidi Durumu** sütunundakilerse şunlardır:

    -   Atlama koduyla etkinleştirildi

    -   Atlama kodu olmadan etkinleştirildi (cihaz denetlenmiyor)

    -   Atlama kodu olmadan etkinleştirildi (cihaza ulaşılamıyor)

    -   Etkin değil

     **Etkinleştirme Kilidi Durumu** alanı, iOS 7.1 veya sonraki sürümleri çalıştırmayan cihazlar için boştur.

-   Bir grup görünümünde bir cihaz seçtiğinizde, cihaz ayrıntıları bölmesinde Etkinleştirme Kilidi durumunu görebilirsiniz.

    **Şirkete Ait Tüm Cihazlar** düğümündeki bir cihazı seçerseniz ve cihaz için Etkinleştirme Kilidi etkinleştirilmişse atlama kodunu da görebilirsiniz. Bu kod kullanılarak el ile Etkinleştirme Kilidi’ni atlama komutu gönderilebilir.

### Ayrıca bkz.
[Cihazları devre dışı bırakma](retire-devices-from-microsoft-intune-management.md)
[Uzak kilitleme ve parola sıfırlama özellikleriyle cihazlarınızın korunmasına yardımcı olma](use-remote-lock-and-passcode-reset-in-microsoft-intune.md)


<!--HONumber=May16_HO3-->


