---
title: "iOS için Intune paylaşılan cihaz yapılandırma ayarları"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: iOS cihazı kilit ekranında bilgilerin görüntülenmesi için kullanabileceğiniz Intune ayarlarını öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f122e4ee-90e7-4b42-b801-8c1c7c0a5bf7
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 6a2aba8b2f062a3e06d517a572992b84fd977514
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---

# <a name="shared-device-configuration-settings-to-display-messages-on-the-ios-device-lock-screen"></a>iOS cihazı kilit ekranında iletilerin gösterilmesi için Paylaşılan Cihaz yapılandırma ayarları

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Paylaşılan cihaz yapılandırma ayarları, oturum açma penceresinde ve kilit ekranında görüntülemek üzere isteğe bağlı bir metin belirtmenize olanak tanır (Örneğin, "Kaybolması Durumunda İade Edilecek Kişi" iletisi ve Varlık Etiketi Bilgileri). 

>[!IMPORTANT]
> Bu özellik iOS 9.3 ve üzeri sürümlerini çalıştıran denetimli cihazlarda desteklenir.

1. **Cihaz özellikleri** dikey penceresinde **Paylaşılan Cihaz Yapılandırması (yalnızca denetimli)** seçeneğini belirleyin.
2. **Paylaşılan Cihaz Yapılandırması (yalnızca denetimli)** dikey penceresinde, aşağıdakileri yapılandırın:
    - **Varlık etiketi bilgileri** - Cihazın varlık etiketi hakkındaki bilgileri girin. Örneğin: **Sahibi: Contoso Corp**. Girdiğiniz bilgiler bu profili atadığınız tüm cihazlara uygulanır.
    - **Kilit ekranı dipnotu** - Bir cihaz kaybolduğunda veya çalındığında geri alınmasına yardımcı olabilecek bir not girin. Örneğin: **Bulursanız lütfen şu numarayı arayın:**.
3. İşiniz bittiğinde, **Profil Oluştur** dikey penceresine dönene kadar **Tamam**’ı ve ardından **Oluştur**’u seçin. 

