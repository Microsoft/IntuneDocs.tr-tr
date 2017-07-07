---
title: "Intune ile iOS Etkinleştirme Kilidini atlama"
titleSuffix: Intune on Azure
description: "Intune'u, kilitli cihazlara erişmek üzere iOS Etkinleştirme Kilidini atlamak için nasıl kullanacağınızı öğrenin.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9ca3b0ba-e41c-45fb-af28-119dff47c59f
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0b92949efca2e4dac5836755e2f32b0527d4762d
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/03/2017
---
# <a name="bypass-activation-lock-on-supervised-ios-devices-with-intune"></a>Denetimli iOS cihazlarında Intune ile Etkinleştirme Kilidini atlama


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Microsoft Intune, iOS 8.0 ve daha sonraki sürümlere sahip cihazlar için iPhone’umu Bul uygulamasının bir özelliği olan iOS Etkinleştirme Kilidi’ni yönetmenize yardımcı olabilir. Bir cihazda kullanıcı tarafından iPhone’umu Bul uygulaması açıldığında Etkinleştirme Kilidi otomatik olarak etkinleştirilir. Bu özellik etkinleştirildikten sonra şunların yapılabilmesi için Apple kimliği ve parolasının girilmesi gerekir:

- iPhone’umu Bul özelliğini kapatma
- Cihazı silme
- Cihazı yeniden etkinleştirme

## <a name="how-activation-lock-affects-you"></a>Etkinleştirme Kilidi sizi nasıl etkiler

Etkinleştirme Kilidi iOS cihazlarının korunmasına yardımcı olmasına ve kaybolan ya da çalınan cihazların bulunma ihtimalini artırmasına rağmen, bir BT yöneticisi olarak size belirli zorluklar çıkarabilir. Örneğin:

- Bir kullanıcı bir cihazda Etkinleştirme Kilidi’ni ayarlar. Daha sonra kullanıcı şirketten ayrılır ve cihazı iade eder. Kullanıcının Apple Kimliği ve parolası olmadan cihazı yeniden etkinleştirmenin yolu yoktur.
- Etkinleştirme Kilidi’nin etkinleştirildiği tüm cihazların raporunu almanız gerekir.
- Kurumunuzda cihaz yenileme işlemi sırasında bazı cihazları farklı bir birime atamak istiyorsunuz. Yalnızca Etkinleştirme Kilidi etkin olmayan cihazları yeniden atayabilirsiniz.

Apple bu sorunların çözülmesine yardımcı olmak için iOS 7.1’de Etkinleştirme Kilidi’ni atlama özelliğini kullanıma sunmuştur. Bu özellik, denetlenen cihazların Etkinleştirme Kilidi’ni kullanıcının Apple kimliği ve parolası olmadan kaldırmanıza imkan sağlar. Denetlenen cihazlar, Apple’ın etkinleştirme sunucusunda depolanan, cihaza özgü bir Etkinleştirme Kilidi’ni atlama kodu oluşturabilir.

>[!TIP]
>iOS cihazları için denetimli mod, Apple Configurator’ı kullanarak bir cihazı kilitlemenize ve cihaz işlevselliğini işe dönük belirli amaçlarla sınırlandırmanıza imkan tanır. Denetimli mod genellikle yalnızca şirkete ait cihazlar içindir.

Etkinleştirme Kilidi hakkında [Apple'ın web sitesinde](https://support.apple.com/HT201365) daha fazla bilgi bulabilirsiniz.

## <a name="how-intune-helps-you-manage-activation-lock"></a>Intune, Etkinleştirme Kilidi’ni yönetmenize nasıl yardımcı olur
Intune, iOS 8.0 ve üzerini çalıştıran denetimli cihazların Etkinleştirme Kilidi durumunu isteyebilir. Intune, yalnızca denetlenen cihazlar için Etkinleştirme Kilidi atlama kodunu alabilir ve doğrudan cihaza gönderebilir. Cihaz silinmişse kullanıcı adını boş bırakıp, parola olarak kodu kullanıp cihaza doğrudan erişebilirsiniz.

**Bu özelliğin işletmeye sunduğu avantajlar şunlardır:**

- Kullanıcı, iPhone’umu Bul Uygulamasının sunduğu güvenlik avantajlarından yararlanır.
- Kullanıcının işlerini yapmasına imkan tanırken, cihazın başka bir amaçla kullanılması gerektiğinde cihazı devre dışı bırakabileceğinizi veya cihazın kilidini açabileceğinizi bilirsiniz.

## <a name="before-you-start"></a>Başlamadan önce
Cihazlarda Etkinleştirme Kilidini atlayabilmeniz için önce bu kilidi etkinleştirmeniz gerekir. Bunu yapmak için:

1. [Cihaz kısıtlama ayarlarını yapılandırma](/intune-azure/configure-devices/how-to-configure-device-restrictions) bölümündeki bilgileri kullanarak iOS için bir Intune cihaz kısıtlama profili yapılandırın.
2. **Kiosk** modu ayarı **Etkinleştirme Kilidi**'ni etkinleştirin.
3. Profili kaydedin, ardından Etkinleştirme Kilidi atlamayı yönetmek istediğiniz cihazlara atayın.


## <a name="how-to-use-activation-lock-bypass"></a>Etkinleştirme Kilidi atlama özelliğini kullanma

>[!IMPORTANT]
>Bir cihazda Etkinleştirme Kilidi’ni atladıktan sonra iPhone’umu Bul Uygulaması’nı açarsanız cihaza otomatik olarak yeni bir etkinleştirme kilidi uygulanır. Bu nedenle, **bu yordamı izlemeden önce cihaza fiziksel olarak sahip olmanız gerekir**.

Intune **Etkinleştirme Kilidini Atla** uzak cihaz eylemi, bir iOS cihazından etkinleştirme kilidini kullanıcının Apple Kimliği ve parolası olmadan kaldırır. Siz etkinleştirme kilidini atladıktan sonra, iPhone’umu Bul uygulaması başlatıldığında cihaz etkinleştirme kilidini yeniden açar. Etkinleştirme kilidini, ancak cihaza fiziksel erişiminiz varsa atlayın.

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihazlar**’ı seçin.
4. **Cihazlar ve gruplar** dikey penceresinde **Tüm cihazlar**’ı seçin.
5. Yönettiğiniz cihazların listesinden denetimli bir iOS cihazı seçin, ardından **Etkinleştirme Kilidini Atla** uzak cihaz eylemini seçin.

Kilit açma isteğinin durumunu cihazın ayrıntılar sayfasındaki **Cihazları yönet** iş yükünde inceleyebilirsiniz.
