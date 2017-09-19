---
title: "iOS için Intune paylaşılan cihaz yapılandırma ayarları"
titlesuffix: Azure portal
description: "iOS cihazı kilit ekranında bilgilerin görüntülenmesi için kullanabileceğiniz Intune ayarlarını öğrenin.\""
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f122e4ee-90e7-4b42-b801-8c1c7c0a5bf7
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4f57daf2674f8817c1e88cf6598c55484b90d536
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/15/2017
---
# <a name="shared-device-configuration-settings-to-display-messages-on-the-ios-device-lock-screen"></a>iOS cihazı kilit ekranında ileti gösterilmesi için paylaşılan cihaz yapılandırma ayarları

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Paylaşılan cihaz yapılandırma ayarları, oturum açma penceresinde ve kilit ekranında görüntülenmek üzere isteğe bağlı bir metin belirtmenize olanak tanır. Buraya örneğin “Kaybolması Durumunda İade Edilecek Kişi” iletisi ve Varlık Etiketi Bilgileri girebilirsiniz. 

>[!IMPORTANT]
> Bu özellik iOS 9.3 ve üzeri sürümlerini çalıştıran denetimli cihazlarda desteklenir.

## <a name="create-shared-device-settings"></a>Paylaşılan cihaz ayarları oluşturma

1. **Cihaz özellikleri** dikey penceresinde **Paylaşılan Cihaz Yapılandırması (yalnızca denetimli)** penceresini açın.
2. **Paylaşılan Cihaz Yapılandırması (yalnızca denetimli)** dikey penceresinde, aşağıdaki ayarları yapılandırın:
    - **Varlık etiketi bilgileri** - Cihazın varlık etiketi hakkındaki bilgileri girin. Örneğin: **Sahibi: Contoso Corp**. Girdiğiniz bilgiler, bu profili atadığınız tüm cihazlara uygulanır.
    - **Kilit ekranı dipnotu** - Cihaz kaybolduğunda veya çalındığında iade edilmesine yardımcı olabilecek bir not girin. Örneğin: **Bulursanız lütfen şu numarayı arayın:**.
3. İşiniz bittiğinde, **Profil Oluştur** dikey penceresine dönene kadar **Tamam**’ı ve ardından **Oluştur**’u seçin. 


## <a name="next-steps"></a>Sonraki adımlar

Artık seçtiğiniz gruplara cihaz profilini atayabilirsiniz. Ayrıntılar için bkz. [Cihaz profilleri atama](device-profile-assign.md).
