---
title: Intune ile iOS Etkinleştirme Kilidini atlama
titlesuffix: Microsoft Intune
description: Intune'u kilitli cihazlara erişmek üzere iOS Etkinleştirme Kilidini atlamak için nasıl kullanacağınızı öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9ca3b0ba-e41c-45fb-af28-119dff47c59f
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2a8c14e523d33c9e0994134ff1ef468b290b3992
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31022518"
---
# <a name="bypass-activation-lock-on-supervised-ios-devices-with-intune"></a>Denetimli iOS cihazlarda Intune ile Etkinleştirme Kilidini atlama


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Microsoft Intune, iOS 8.0 ve daha sonraki sürümlere sahip cihazlar için iPhone’umu Bul uygulamasının bir özelliği olan iOS Etkinleştirme Kilidi’ni yönetmenize yardımcı olabilir. Bir cihazda kullanıcı tarafından iPhone’umu Bul uygulaması açıldığında Etkinleştirme Kilidi otomatik olarak etkinleştirilir. Bu özellik etkinleştirildikten sonra şunların yapılabilmesi için Apple kimliği ve parolasının girilmesi gerekir:

- iPhone’umu Bul özelliğini kapatma
- Cihazı silme
- Cihazı yeniden etkinleştirme

## <a name="how-activation-lock-affects-you"></a>Etkinleştirme Kilidi sizi nasıl etkiler

Etkinleştirme Kilidi iOS cihazlarının korunmasına yardımcı olmasına ve kaybolan ya da çalınan cihazların bulunma ihtimalini artırmasına rağmen, bir BT yöneticisi olarak size belirli zorluklar çıkarabilir. Örneğin:

- Bir kullanıcı bir cihazda Etkinleştirme Kilidi’ni ayarlar. Daha sonra kullanıcı şirketten ayrılır ve cihazı iade eder. Kullanıcının Apple Kimliği ve parolası olmadan cihazı yeniden etkinleştirmenin yolu yoktur.
- Etkinleştirme Kilidi’nin etkinleştirildiği tüm cihazların raporunu almanız gerekir.
- Kurumunuzda cihaz yenileme işlemi sırasında bazı cihazları farklı bir birime atamak istiyorsunuz. Yalnızca Etkinleştirme Kilidi etkin olmayan cihazları yeniden atayabilirsiniz.

Apple bu sorunların çözülmesine yardımcı olmak için iOS 7.1’de Etkinleştirme Kilidi’ni atlama özelliğini kullanıma sunmuştur. Etkinleştirme Kilidi’ni atlama, denetlenen cihazların Etkinleştirme Kilidi’ni kullanıcının Apple kimliği ve parolası olmadan kaldırmanıza imkan sağlar. Denetlenen cihazlar, Apple’ın etkinleştirme sunucusunda depolanan, cihaza özgü bir Etkinleştirme Kilidi’ni atlama kodu oluşturabilir.

>[!TIP]
>iOS cihazları için denetimli mod, Apple Configurator’ı kullanarak bir cihazı kilitlemenize ve cihaz işlevselliğini işe dönük belirli amaçlarla sınırlandırmanıza imkan tanır. Denetimli mod yalnızca şirkete ait cihazlar içindir.

Etkinleştirme Kilidi hakkında [Apple'ın web sitesinde](https://support.apple.com/HT201365) daha fazla bilgi bulabilirsiniz.

## <a name="how-intune-helps-you-manage-activation-lock"></a>Intune, Etkinleştirme Kilidi’ni yönetmenize nasıl yardımcı olur
Intune, iOS 8.0 ve üzerini çalıştıran denetimli cihazların Etkinleştirme Kilidi durumunu isteyebilir. Intune, yalnızca denetlenen cihazlar için Etkinleştirme Kilidi atlama kodunu alabilir ve doğrudan cihaza gönderebilir. Cihaz silinmişse kullanıcı adını boş bırakıp, parola olarak kodu kullanıp cihaza doğrudan erişebilirsiniz.

**Etkinleştirme Kilidi’ni yönetmek için Intune kullanmanın iş açısından avantajları şunlardır:**

- Kullanıcı, iPhone’umu Bul Uygulamasının sunduğu güvenlik avantajlarından yararlanır.
- Kullanıcıların kendi işlerini yapmasına imkan tanıyabilir ve cihazın başka bir amaçla kullanılması gerektiğinde cihazı devre dışı bırakabileceğinizi ya da cihazın kilidini açabileceğinizi bilirsiniz.

## <a name="before-you-start"></a>Başlamadan önce
Cihazlarda Etkinleştirme Kilidi’ni atlayabilmeniz için aşağıdaki yönergeleri izleyerek bu kilidi etkinleştirmeniz gerekir:

1. [Cihaz kısıtlama ayarlarını yapılandırma](/intune-azure/configure-devices/how-to-configure-device-restrictions) bölümündeki bilgileri kullanarak iOS için bir Intune cihaz kısıtlama profili yapılandırın.
2. [iOS için cihaz kısıtlama ayarları](device-restrictions-ios.md) kısmında, **Genel** ayarların altında **Etkinleştirme Kilidi** seçeneğini etkinleştirin.
3. Profili kaydedin, ardından Etkinleştirme Kilidi atlamayı yönetmek istediğiniz cihazlara [atayın](device-profile-assign.md).


## <a name="how-to-use-activation-lock-bypass"></a>Etkinleştirme Kilidi atlama özelliğini kullanma

>[!IMPORTANT]
>Bir cihazda Etkinleştirme Kilidi’ni atladıktan sonra iPhone’umu Bul Uygulaması’nı açarsanız cihaza otomatik olarak yeni bir Etkinleştirme Kilidi uygulanır. Bu nedenle, **bu yordamı izlemeden önce cihaza fiziksel olarak sahip olmanız gerekir**.

Intune **Etkinleştirme Kilidini Atla** uzak cihaz eylemi, bir iOS cihazından etkinleştirme kilidini kullanıcının Apple Kimliği ve parolası olmadan kaldırır. Siz etkinleştirme kilidini atladıktan sonra, iPhone’umu Bul uygulaması başlatıldığında cihaz etkinleştirme kilidini yeniden açar. Etkinleştirme kilidini, ancak cihaza fiziksel erişiminiz varsa atlayın.

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** dikey penceresinde **Cihazlar**’ı seçin.
4. **Cihazlar** dikey penceresinden **Tüm cihazlar**'ı seçin.
5. Yönettiğiniz cihazların listesinden denetimli bir iOS cihazı seçin, **...Daha Fazla**’yı ve ardından **Etkinleştirme Kilidini Atla** uzak cihaz eylemini seçin.

## <a name="next-steps"></a>Sonraki adımlar

Kilit açma isteğinin durumunu cihazın ayrıntılar sayfasındaki **Cihazları yönet** iş yükünde inceleyebilirsiniz.
