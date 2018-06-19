---
title: Cihazlarda iOS Etkinleştirme Kilidi’ni yönetme
description: Microsoft Intune, iOS 7.1 ve daha sonraki sürümlere sahip cihazlar için iPhone’umu Bul uygulamasının bir özelliği olan iOS Etkinleştirme Kilidi’ni yönetmenize yardımcı olabilir.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 04/24/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: bb49e926-15c4-4f01-b6eb-cee6f7ee1984
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 37593e8c554cad73182873b01f6388bdb9cb0035
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31020138"
---
# <a name="help-protect-ios-devices-with-activation-lock-bypass-for-microsoft-intune"></a>Microsoft Intune için Etkinleştirme Kilidi’ni atlama ile iOS cihazlarının korunmasına yardımcı olma

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Microsoft Intune, iOS 8.0 ve daha sonraki sürümlere sahip cihazlar için iPhone’umu Bul uygulamasının bir özelliği olan iOS Etkinleştirme Kilidi’ni yönetmenize yardımcı olabilir. Bir cihazda kullanıcı tarafından iPhone’umu Bul uygulaması açıldığında Etkinleştirme Kilidi otomatik olarak etkinleştirilir. Bu özellik etkinleştirildikten sonra şunların yapılabilmesi için Apple kimliği ve parolasının girilmesi gerekir: 

-   iPhone’umu Bul özelliğini kapatma

-   Cihazı silme

-   Cihazı yeniden etkinleştirme

## <a name="how-activation-lock-affects-you"></a>Etkinleştirme Kilidi sizi nasıl etkiler
Etkinleştirme Kilidi iOS cihazlarının korunmasına yardımcı olmasına ve kaybolan ya da çalınan cihazların bulunma ihtimalini artırmasına rağmen, bir BT yöneticisi olarak size belirli zorluklar çıkarabilir. Örneğin:

-   Bir kullanıcı bir cihazda Etkinleştirme Kilidi’ni ayarlar. Daha sonra kullanıcı şirketten ayrılır ve cihazı iade eder. Kullanıcının Apple Kimliği ve parolası olmadan cihazı yeniden etkinleştirmenin yolu yoktur.

-   Etkinleştirme Kilidi’nin etkinleştirildiği tüm cihazların raporunu almanız gerekir.

-   Kurumunuzda cihaz yenileme işlemi sırasında bazı cihazları farklı bir birime atamak istiyorsunuz. Yalnızca Etkinleştirme Kilidi etkin olmayan cihazları yeniden atayabilirsiniz.

Apple bu sorunların çözülmesine yardımcı olmak için iOS 7.1’de Etkinleştirme Kilidi’ni atlama özelliğini kullanıma sunmuştur. Bu özellik, denetlenen cihazların Etkinleştirme Kilidi’ni kullanıcının Apple kimliği ve parolası olmadan kaldırmanıza imkan sağlar. Denetlenen cihazlar, Apple’ın etkinleştirme sunucusunda depolanan, cihaza özgü bir Etkinleştirme Kilidi’ni atlama kodu oluşturabilir.

> [!TIP]
> iOS cihazları için denetimli mod, Apple Configurator’ı kullanarak bir cihazı kilitlemenize ve cihaz işlevselliğini işe dönük belirli amaçlarla sınırlandırmanıza imkan tanır. Denetimli mod genellikle yalnızca şirkete ait cihazlar içindir.

Etkinleştirme Kilidi hakkında daha fazla bilgiyi [buradan](https://support.apple.com/en-us/HT201365) edinebilirsiniz.

## <a name="how-intune-helps-you-manage-activation-lock"></a>Intune, Etkinleştirme Kilidi’ni yönetmenize nasıl yardımcı olur
Intune, iOS 8.0 ve üzerini çalıştıran denetimli cihazların Etkinleştirme Kilidi durumunu isteyebilir. Intune, yalnızca denetlenen cihazlar için Etkinleştirme Kilidi atlama kodunu alabilir ve doğrudan cihaza gönderebilir. Cihaz silinmişse kullanıcı adını boş bırakıp, parola olarak kodu kullanıp cihaza doğrudan erişebilirsiniz.

**Bu özelliğin işletme açısından faydaları şunlardır:**

-   Kullanıcı, iPhone’umu Bul Uygulamasının sunduğu güvenlik avantajlarından yararlanır.

-   Kullanıcının işlerini yapmasına imkan tanırken, cihazın başka bir amaçla kullanılması gerektiğinde cihazı devre dışı bırakabileceğinizi veya cihazın kilidini açabileceğinizi bilirsiniz.

## <a name="before-you-start"></a>Başlamadan önce

Cihazlarda Etkinleştirme Kilidini atlayabilmeniz için önce bu kilidi etkinleştirmeniz gerekir. Bunu yapmak için:

1. [Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](/intune-classic/deploy-use/ios-policy-settings-in-microsoft-intune) konusundaki bilgileri kullanın.
2. **Kayıt** bölümünde, ayarlar sayfasında, **Cihaz denetimli moddayken Etkinleştirme Kilidi’ne izin ver**’i **Evet** olarak ayarlayın.
3. İlkeyi kaydedin ve Etkinleştirme Kilidini atlamayı yönetmek istediğiniz cihazlara dağıtın.

## <a name="how-to-use-activation-lock-bypass-from-the-intune-admin-console"></a>Intune yönetim konsolundan Etkinleştirme Kilidi’ni atlama özelliğini kullanma
> [!IMPORTANT]
> Bir cihazda Etkinleştirme Kilidi’ni atladıktan sonra iPhone’umu Bul Uygulaması’nı açarsanız cihaza otomatik olarak yeni bir etkinleştirme kilidi uygulanır. Bu nedenle, **bu yordamı izlemeden önce cihaza fiziksel olarak sahip olmanız gerekir**.

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com), **Gruplar** &gt; **Tüm Cihazlar** &gt; **Şirkete Ait Tüm Cihazlar** öğesini seçin.

2.  Etkinleştirme Kilidi’ni atlamak istediğiniz cihazı seçin. **Etkinleştirme Kilidini Atlama**’yı seçin.

3.  Uyarı iletisini okuyun. Devam etmek için **Evet**’i seçin.

Cihaz ayrıntıları sayfasında kilit açma isteğinin durumunu inceleyebilirsiniz.

## <a name="how-to-see-which-devices-are-using-activation-lock"></a>Hangi cihazların etkinleştirme kilidi kullandığını görme
Hangi cihazların Etkinleştirme Kilidi kullandığını iki yolla görebilirsiniz:

-   **Mobil Cihaz Envanteri Raporları**’nı çalıştırın. Bu rapor, cihazların durumunu belirtmek için **Etkinleştirme Kilidi Durumu** ve **Denetimli** sütunlarını gösterir. **Denetimli** sütunundaki değerler **Evet** veya **Hayır**, **Etkinleştirme Kilidi Durumu** sütunundakilerse şunlardır:

    -   Atlama koduyla etkinleştirildi

    -   Atlama kodu olmadan etkinleştirildi (cihaz denetlenmiyor)

    -   Atlama kodu olmadan etkinleştirildi (cihaza ulaşılamıyor)

    -   Etkin değil

    **Etkinleştirme Kilidi Durumu** kutusu, iOS 8.0 veya üzerini çalıştırmayan cihazlar için boştur.

-   Cihaz ayrıntıları bölmesinde Etkinleştirme Kilidi durumunu görmek için grup görünümünde bir cihaz seçin.

    **Şirkete Ait Tüm Cihazlar** düğümündeki bir cihazı seçerseniz ve cihaz için Etkinleştirme Kilidi etkinleştirilmişse atlama kodunu da görebilirsiniz. Bu kod kullanılarak el ile Etkinleştirme Kilidi’ni atlama komutu gönderilebilir.

    > [!IMPORTANT]
    >Intune, Etkinleştirme Kilidi için her yedi günde bir cihazlardan envanter alır. Bu nedenle, Intune konsolunda cihazların Etkinleştirme Kilidi durumu hemen görüntülenmeyebilir.


### <a name="see-also"></a>Ayrıca bkz:
[Cihazları devre dışı bırakma](retire-devices-from-microsoft-intune-management.md)
[Uzak kilitleme ve parola sıfırlama özellikleriyle cihazlarınızın korunmasına yardımcı olma](use-remote-lock-and-passcode-reset-in-microsoft-intune.md)
