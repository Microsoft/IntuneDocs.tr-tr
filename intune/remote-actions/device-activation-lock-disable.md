---
title: Intune ile iOS Etkinleştirme Kilidini atlama
titleSuffix: Microsoft Intune
description: Intune'u kilitli cihazlara erişmek üzere iOS Etkinleştirme Kilidini atlamak için nasıl kullanacağınızı öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 9ca3b0ba-e41c-45fb-af28-119dff47c59f
ms.reviewer: coferro
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1c3847890a4871b784764a5beca46f6776d52d3f
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2020
ms.locfileid: "76761280"
---
# <a name="disable-activation-lock-on-supervised-ios-devices-with-intune"></a>Denetimli iOS cihazlarında Intune ile Etkinleştirme Kilidi devre dışı bırakma


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Microsoft Intune, iOS 8.0 ve daha sonraki sürümlere sahip cihazlar için iPhone’umu Bul uygulamasının bir özelliği olan iOS Etkinleştirme Kilidi’ni yönetmenize yardımcı olabilir. Bir cihazda kullanıcı tarafından iPhone’umu Bul uygulaması açıldığında Etkinleştirme Kilidi otomatik olarak etkinleştirilir. Bu özellik etkinleştirildikten sonra şunların yapılabilmesi için Apple kimliği ve parolasının girilmesi gerekir:

- iPhone’umu Bul özelliğini kapatma
- Cihazı silme
- Cihazı yeniden etkinleştirme

## <a name="how-activation-lock-affects-you"></a>Etkinleştirme Kilidi sizi nasıl etkiler

Etkinleştirme Kilidi iOS cihazlarının korunmasına yardımcı olmasına ve kaybolan ya da çalınan cihazların bulunma ihtimalini artırmasına rağmen, bir BT yöneticisi olarak size belirli zorluklar çıkarabilir. Örneğin:

- Bir kullanıcı bir cihazda Etkinleştirme Kilidi’ni ayarlar. Daha sonra kullanıcı şirketten ayrılır ve cihazı  iade eder. Kullanıcının Apple Kimliği ve parolası olmadan cihazı yeniden etkinleştirmenin yolu yoktur.
- Etkinleştirme Kilidi’nin etkinleştirildiği tüm cihazların raporunu almanız gerekir.
- Kurumunuzda cihaz yenileme işlemi sırasında bazı cihazları farklı bir birime atamak istiyorsunuz. Yalnızca Etkinleştirme Kilidi etkin olmayan cihazları yeniden atayabilirsiniz.

Bu sorunları çözmeye yardımcı olmak için, Apple, iOS 7,1 ' de devre dışı Etkinleştirme Kilidi sunmuştur. Etkinleştirme Kilidi devre dışı bırak, denetimli cihazlardan Etkinleştirme Kilidi kullanıcının Apple KIMLIĞI ve parolası olmadan kaldırmanızı sağlar. Denetlenen cihazlar, Apple’ın etkinleştirme sunucusunda depolanan, cihaza özgü bir Etkinleştirme Kilidi’ni atlama kodu oluşturabilir.

>[!TIP]
>iOS cihazları için denetimli mod, Apple Configurator’ı kullanarak bir cihazı kilitlemenize ve cihaz işlevselliğini işe dönük belirli amaçlarla sınırlandırmanıza imkan tanır. Denetimli mod yalnızca şirkete ait cihazlar içindir.

Etkinleştirme Kilidi hakkında [Apple'ın web sitesinde](https://support.apple.com/HT201365) daha fazla bilgi bulabilirsiniz.

## <a name="how-intune-helps-you-manage-activation-lock"></a>Intune, Etkinleştirme Kilidi’ni yönetmenize nasıl yardımcı olur
Intune, iOS 8.0 ve üzerini çalıştıran denetimli cihazların Etkinleştirme Kilidi durumunu isteyebilir. Intune yalnızca denetimli cihazlar için devre dışı Etkinleştirme Kilidi kodunu alabilir ve doğrudan cihaza gönderebilir. Cihaz silinmişse kullanıcı adını boş bırakıp, parola olarak kodu kullanıp cihaza doğrudan erişebilirsiniz.

**Etkinleştirme Kilidi’ni yönetmek için Intune kullanmanın iş açısından avantajları şunlardır:**

- Kullanıcı, iPhone’umu Bul Uygulamasının sunduğu güvenlik avantajlarından yararlanır.
- Kullanıcıların kendi işlerini yapmasına imkan tanıyabilir ve cihazın başka bir amaçla kullanılması gerektiğinde cihazı devre dışı bırakabileceğinizi ya da cihazın kilidini açabileceğinizi bilirsiniz.

## <a name="before-you-start"></a>Başlamadan önce
Cihazlarda Etkinleştirme Kilidi devre dışı bırakabilmeniz için bu yönergeleri izleyerek etkinleştirmeniz gerekir:

1. [Cihaz kısıtlama ayarlarını yapılandırma](/intune-azure/configure-devices/how-to-configure-device-restrictions) bölümündeki bilgileri kullanarak iOS için bir Intune cihaz kısıtlama profili yapılandırın.
2. [iOS için cihaz kısıtlama ayarları](../configuration/device-restrictions-ios.md) kısmında, **Genel** ayarların altında **Etkinleştirme Kilidi** seçeneğini etkinleştirin.
3. Profili kaydedin ve ardından devre dışı bırak Etkinleştirme Kilidi yönetmek istediğiniz cihazlara [atayın](../configuration/device-profile-assign.md) .


## <a name="how-to-use-disable-activation-lock"></a>Devre dışı bırakma Etkinleştirme Kilidi kullanma

>[!IMPORTANT]
>Bir cihazda Etkinleştirme Kilidi devre dışı bıraktıktan sonra, iPhone 'Umu bul uygulaması başlatılırsa, yeni bir Etkinleştirme Kilidi otomatik olarak uygulanır. Bu nedenle, **bu yordamı izlemeden önce cihaza fiziksel olarak sahip olmanız gerekir**.

Intune Etkinleştirme Kilidi uzak cihazı **devre dışı bırak** eylemi, kullanıcının Apple Kimliği ve parolası gerekmeden Etkinleştirme Kilidi bir iOS cihazından kaldırır. Etkinleştirme Kilidi devre dışı bıraktıktan sonra, iPhone 'Umu bul uygulaması başladığında cihaz Etkinleştirme Kilidi yeniden açar. Yalnızca cihaza fiziksel erişiminiz varsa Etkinleştirme Kilidi devre dışı bırakın.

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
3. **Intune** dikey penceresinde **Cihazlar**’ı seçin.
4. **Cihazlar** dikey penceresinde **Tüm cihazlar**'ı seçin.
5. Yönettiğiniz cihazların listesinde uzak cihaz **Etkinleştirme Kilidi devre dışı bırak** eylemini seçin.
6. Cihazın “Donanım” bölümüne gidin ve **Etkinleştirme kilidi atlama kodu** değerini **Koşullu Erişim**’in altına kopyalayın.

    >[!NOTE]
    >Cihazı silmeden önce atlama kodunu kopyalayın. Kodu kopyalamadan önce cihaz ayarlarını sıfırlarsanız kod Azure’dan kaldırılır.

7. Cihazın **Genel bakış** dikey penceresine gidin ve **Sil**’i seçin.
8. Cihaz sıfırlandıktan sonra *Apple kimliğiniz* ve *parolanız* istenir. *Kimlik* alanını boş bırakın ve ardından *parola* için **atlama kodunu** girin. Bu işlem, hesabı cihazdan kaldırır. 


## <a name="next-steps"></a>Sonraki adımlar

Kilit açma isteğinin durumunu cihazın ayrıntılar sayfasındaki **Cihazları yönet** iş yükünde inceleyebilirsiniz.
