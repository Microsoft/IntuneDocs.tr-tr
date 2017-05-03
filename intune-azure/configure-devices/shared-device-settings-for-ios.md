---
title: "iOS için Intune paylaşılan cihaz yapılandırma ayarları"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: iOS cihazı kilit ekranında bilgilerin görüntülenmesi için kullanabileceğiniz Intune ayarlarını öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 4/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f122e4ee-90e7-4b42-b801-8c1c7c0a5bf7
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: 2bc107054f438d5ed72de87dec85900f871c0acc
ms.lasthandoff: 04/19/2017


---

# <a name="shared-device-configuration-settings-to-display-messages-on-the-ios-device-lock-screen"></a>iOS cihazı kilit ekranında iletilerin gösterilmesi için Paylaşılan Cihaz yapılandırma ayarları

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Paylaşılan cihaz yapılandırma ayarları, oturum açma penceresinde ve kilit ekranında görüntülemek üzere isteğe bağlı bir metin belirtmenize olanak tanır (Örneğin, "Kaybolması Durumunda İade Edilecek Kişi" iletisi ve Varlık Etiketi Bilgileri). 

>[!IMPORTANT]
> Bu özellik iOS 9.3 ve üzeri sürümlerini çalıştıran denetimli cihazlarda desteklenir.

1. **Cihaz özellikleri** dikey penceresinde **Paylaşılan Cihaz Yapılandırması (yalnızca denetimli)** seçeneğini belirleyin.
2. **Paylaşılan Cihaz Yapılandırması (yalnızca denetimli)** dikey penceresinde, aşağıdakileri yapılandırın:
    - **Varlık etiketi bilgileri** - Cihazın varlık etiketi hakkındaki bilgileri girin. Örneğin: **Sahibi: Contoso Corp**. Girdiğiniz bilgiler bu profili atadığınız tüm cihazlara uygulanır.
    - **Kilit ekranı dipnotu** - Bir cihaz kaybolduğunda veya çalındığında geri alınmasına yardımcı olabilecek bir not girin. Örneğin: **Bulursanız lütfen şu numarayı arayın:**.
3. İşiniz bittiğinde, **Profil Oluştur** dikey penceresine dönene kadar **Tamam**’ı ve ardından **Oluştur**’u seçin. 

