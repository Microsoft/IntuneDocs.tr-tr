---
title: iOS için Microsoft Intune paylaşılan cihaz yapılandırma ayarları
titlesuffix: ''
description: iOS cihazı kilit ekranında bilgilerin görüntülenmesi için kullanabileceğiniz Microsoft Intune ayarlarını öğrenin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/5/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 638b4b3ebc83917faae0d34ec407b8ad47b4a4fb
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52183392"
---
# <a name="shared-device-configuration-settings-to-display-messages-on-the-ios-device-lock-screen"></a>iOS cihazı kilit ekranında ileti gösterilmesi için paylaşılan cihaz yapılandırma ayarları

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bu makalede, iOS cihazı kilit ekranında bilgilerin görüntülenmesi için kullanabileceğiniz Microsoft Intune ayarları gösterilir.

Paylaşılan cihaz yapılandırma ayarları, oturum açma penceresinde ve kilit ekranında görüntülenmek üzere isteğe bağlı bir metin belirtmenize olanak tanır. Buraya örneğin “Kaybolması Durumunda İade Edilecek Kişi” iletisi ve Varlık Etiketi Bilgileri girebilirsiniz. 

>[!IMPORTANT]
> Bu özellik iOS 9.3 ve üzeri sürümlerini çalıştıran denetimli cihazlarda desteklenir.

## <a name="create-shared-device-settings"></a>Paylaşılan cihaz ayarları oluşturma

1. [Azure Portalı’nda Intune](https://portal.azure.com)’dan, cihaz yapılandırma alanındaki [**Cihaz özellikleri**’ne gidin](device-features-configure.md). 
1. **Cihaz özellikleri** bölmesinde **Paylaşılan Cihaz Yapılandırması (yalnızca denetimli)** penceresini açın.
2. **Paylaşılan Cihaz Yapılandırması (yalnızca denetimli)** bölmesinde, aşağıdaki ayarları yapılandırın:
    - **Varlık etiketi bilgileri** - Cihazın varlık etiketi hakkındaki bilgileri girin. Örneğin: **Sahibi: Contoso Corp**. Girdiğiniz bilgiler, bu profili atadığınız tüm cihazlara uygulanır.
    - **Kilit ekranı dipnotu** - Cihaz kaybolduğunda veya çalındığında iade edilmesine yardımcı olabilecek bir not girin. Örneğin: **Bulursanız lütfen şu numarayı arayın:**.
3. İşiniz bittiğinde, **Profil oluştur** bölmesine dönene kadar **Tamam**’ı seçin ve sonra da **Oluştur**’u seçin. 


## <a name="next-steps"></a>Sonraki adımlar

Artık seçtiğiniz gruplara cihaz profilini atayabilirsiniz. Ayrıntılar için bkz. [Cihaz profilleri atama](device-profile-assign.md).
