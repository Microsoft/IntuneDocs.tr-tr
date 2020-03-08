---
title: Intune ile iOS/ıpados Etkinleştirme Kilidi atlama
titleSuffix: Microsoft Intune
description: Kilitli cihazlara erişmek üzere iOS/ıpados Etkinleştirme Kilidi atlamak için Intune 'u kullanmayı öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/27/2020
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
ms.openlocfilehash: 7a322788dba092f44af2f0664fe810f8392b9f56
ms.sourcegitcommit: 25e4847ead0f56c269cfefe1e01c1b9106a28cf1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78855992"
---
# <a name="disable-activation-lock-on-supervised-iosipados-devices-with-intune"></a>Denetimli iOS/ıpados cihazlarında Intune ile Etkinleştirme Kilidi devre dışı bırakma


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Microsoft Intune iOS/ıpados Etkinleştirme Kilidi, iOS için My iPhone uygulamamın/ıpados 8,0 ve üzeri cihazların bir özelliğidir. Bir cihazda kullanıcı tarafından iPhone’umu Bul uygulaması açıldığında Etkinleştirme Kilidi otomatik olarak etkinleştirilir. Bu özellik etkinleştirildikten sonra şunların yapılabilmesi için Apple kimliği ve parolasının girilmesi gerekir:

- iPhone’umu Bul özelliğini kapatma
- Cihazı silme
- Cihazı yeniden etkinleştirme

## <a name="how-activation-lock-affects-you"></a>Etkinleştirme Kilidi sizi nasıl etkiler

Etkinleştirme Kilidi iOS/ıpados cihazlarının güvenliğinin sağlanmasına yardımcı olur ve kayıp veya çalınmış bir cihazı kurtarma olasılığınızı geliştirirken, bu özellik sizi bir BT Yöneticisi olarak, bir dizi zorluk sunacak şekilde sağlayabilir. Örneğin:

- Bir kullanıcı bir cihazda Etkinleştirme Kilidi’ni ayarlar. Daha sonra kullanıcı şirketten ayrılır ve cihazı iade eder. Kullanıcının Apple Kimliği ve parolası olmadan cihazı yeniden etkinleştirmenin yolu yoktur.
- Etkinleştirme Kilidi’nin etkinleştirildiği tüm cihazların raporunu almanız gerekir.
- Kurumunuzda cihaz yenileme işlemi sırasında bazı cihazları farklı bir birime atamak istiyorsunuz. Yalnızca Etkinleştirme Kilidi etkin olmayan cihazları yeniden atayabilirsiniz.

Bu sorunları çözmeye yardımcı olmak için, Apple, iOS/ıpados 7,1 ' de devre dışı Etkinleştirme Kilidi sunmuştur. Etkinleştirme Kilidi devre dışı bırak, denetimli cihazlardan Etkinleştirme Kilidi kullanıcının Apple KIMLIĞI ve parolası olmadan kaldırmanızı sağlar. Denetlenen cihazlar, Apple’ın etkinleştirme sunucusunda depolanan, cihaza özgü bir Etkinleştirme Kilidi’ni atlama kodu oluşturabilir.

>[!TIP]
>İOS/ıpados cihazları için denetimli mod, bir cihazı kilitlemek ve işlevselliği belirli iş amaçlarına sınırlamak için Apple Configurator kullanmanıza imkan sağlar. Denetimli mod yalnızca şirkete ait cihazlar içindir.

Etkinleştirme Kilidi hakkında [Apple'ın web sitesinde](https://support.apple.com/HT201365) daha fazla bilgi bulabilirsiniz.

## <a name="how-intune-helps-you-manage-activation-lock"></a>Intune, Etkinleştirme Kilidi’ni yönetmenize nasıl yardımcı olur
Intune, iOS/ıpados 8,0 ve üstünü çalıştıran denetimli cihazların Etkinleştirme Kilidi durumunu talep edebilir. Intune yalnızca denetimli cihazlar için devre dışı Etkinleştirme Kilidi kodunu alabilir ve doğrudan cihaza gönderebilir. Cihaz silinmişse kullanıcı adını boş bırakıp, parola olarak kodu kullanıp cihaza doğrudan erişebilirsiniz.

**Etkinleştirme Kilidi’ni yönetmek için Intune kullanmanın iş açısından avantajları şunlardır:**

- Kullanıcı, iPhone’umu Bul Uygulamasının sunduğu güvenlik avantajlarından yararlanır.
- Kullanıcıların kendi işlerini yapmasına imkan tanıyabilir ve cihazın başka bir amaçla kullanılması gerektiğinde cihazı devre dışı bırakabileceğinizi ya da cihazın kilidini açabileceğinizi bilirsiniz.

## <a name="before-you-start"></a>Başlamadan önce
Cihazlarda Etkinleştirme Kilidi devre dışı bırakabilmeniz için bu yönergeleri izleyerek etkinleştirmeniz gerekir:

1. [Cihaz kısıtlama ayarlarını yapılandırma](../configuration/device-restrictions-configure.md)bölümündeki bilgileri kullanarak IOS/ıpados Için bir Intune cihaz kısıtlama profili yapılandırın.
2. [İOS/ıpados için cihaz kısıtlama ayarları](../configuration/device-restrictions-ios.md)' nda, **genel** ayarlar altında, **Etkinleştirme Kilidi**seçeneğini etkinleştirin.
3. Profili kaydedin ve ardından devre dışı bırak Etkinleştirme Kilidi yönetmek istediğiniz cihazlara [atayın](../configuration/device-profile-assign.md) .


## <a name="how-to-use-disable-activation-lock"></a>Devre dışı bırakma Etkinleştirme Kilidi kullanma

>[!IMPORTANT]
>Bir cihazda Etkinleştirme Kilidi devre dışı bıraktıktan sonra, iPhone 'Umu bul uygulaması başlatılırsa, yeni bir Etkinleştirme Kilidi otomatik olarak uygulanır. Bu nedenle, **bu yordamı izlemeden önce cihaza fiziksel olarak sahip olmanız gerekir**.

Intune Etkinleştirme Kilidi uzak cihazı **devre dışı bırak** eylemi, kullanıcının Apple Kimliği ve parolası gerekmeden Etkinleştirme Kilidi bir IOS/ıpados cihazından kaldırır. Etkinleştirme Kilidi devre dışı bıraktıktan sonra, iPhone 'Umu bul uygulaması başladığında cihaz Etkinleştirme Kilidi yeniden açar. Yalnızca cihaza fiziksel erişiminiz varsa Etkinleştirme Kilidi devre dışı bırakın.

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
3. **Intune** dikey penceresinde **Cihazlar**’ı seçin.
4. **Cihazlar** dikey penceresinde **Tüm cihazlar**'ı seçin.
5. Yönettiğiniz cihazların listesinde uzak cihaz **Etkinleştirme Kilidi devre dışı bırak** eylemini seçin.
6. Cihazın "donanım" bölümüne gidin ve sonra **koşullu erişim**altında **Etkinleştirme Kilidi atlama kodu** değerini kopyalayın.

    >[!NOTE]
    >Cihazı silmeden önce atlama kodunu kopyalayın. Kodu kopyalamadan önce cihaz ayarlarını sıfırlarsanız kod Azure’dan kaldırılır.

7. Cihazın **Genel bakış** dikey penceresine gidin ve **Sil**’i seçin.
8. Cihaz sıfırlandıktan sonra *Apple kimliğiniz* ve *parolanız* istenir. *Kimlik* alanını boş bırakın ve ardından **parola** için *atlama kodunu* girin. Bu işlem, hesabı cihazdan kaldırır. 


## <a name="next-steps"></a>Sonraki adımlar

Kilit açma isteğinin durumunu cihazın ayrıntılar sayfasındaki **Cihazları yönet** iş yükünde inceleyebilirsiniz.
