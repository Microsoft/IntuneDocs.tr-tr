---
title: iOS için Microsoft Intune paylaşılan cihaz yapılandırma ayarları
titlesuffix: ''
description: iOS cihazı kilit ekranında bilgilerin görüntülenmesi için kullanabileceğiniz Microsoft Intune ayarlarını öğrenin.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/5/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 73c4f96e3057227bc601175c4e8f42802eb322bc
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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
