---
title: "Kayıtlı olmayan cihazlardaki LOB uygulamalarını koruma | Microsoft Docs"
description: "Bu konu başlığı altında, veri kaybını önlemeye yardımcı olabilecek mobil uygulama yönetimi ilkelerini uygulayabilmek için özel iş kolu uygulamalarınızı nasıl hazırlayacağınız açıklanmaktadır."
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00219467-a62e-43b6-954b-3084f54c45ba
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 1d3efa5d35e346ea668c71ba8b46ba21b11c39e7


---

# <a name="protect-line-of-business-apps-and-data-on-devices-that-are-not-enrolled-in-microsoft-intune"></a>Microsoft Intune'da kayıtlı olmayan cihazlardaki iş kolu uygulamalarını ve verilerini koruma

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Mobil uygulama yönetimi (MAM) ilkeleri, şirket verilerinin dışarıya sızmasına neden olabilecek eylemleri kısıtlayarak ve bir uygulama PIN'i gibi veri erişim gereksinimleri uygulayarak şirket verilerinin korunmasına yardımcı olur. iOS ve Android iş kolu uygulamalarına MAM ilkeleri uygulamak için önce Microsoft Intune Uygulama Sarmalama Aracı ile uygulamayı sarmalamanız gerekir. Uygulama sarmalama, temel uygulamada hiçbir değişiklik yapılmasına gerek kalmadan mobil uygulamaya bir yönetim katmanı uygulama işlemidir. Uygulama sarmalandıktan sonra uygulamaya MAM ilkeleri uygulayabilir ve uygulamayı kullanıcılarınıza dağıtabilirsiniz.  

Bu konu başlığı altında, **çalışana ait yönetilmeyen cihazlarda** ve **üçüncü taraf bir mobil cihaz yönetimi (MDM) çözümü** tarafından yönetilen cihazlarda erişilen uygulamalara MAM ilkeleri uygulamak için gereken adımlar açıklanmaktadır.  **Intune MDM'ye kaydedilmiş cihazlarda** çalıştırılan iş kolu uygulamalarınızı hazırlamak için bkz. [Uygulamaların Microsoft Intune ile mobil uygulama yönetimi için nasıl hazırlanacağına karar verme](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md).


##  <a name="step-1-prepare-the-app"></a>1. Adım: Uygulamayı hazırlama

Bir uygulamaya MAM ilkeleri uygulayabilmeniz için önce [iOS](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) ve [Android](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) için Microsoft Intune Uygulama Sarmalama Aracı'nı kullanarak uygulamayı sarmalamanız veya Intune uygulama koruma özelliklerini elle tümleştirmek için [Intune Uygulama SDK'sını](../develop/intune-app-sdk.md) kullanmanız gerekir.

Uygulama Sarmalama Aracı'nı ya da SDK'yı kullanma hakkında daha fazla bilgi için bkz. [Uygulamaların Microsoft Intune ile mobil uygulama yönetimi için nasıl hazırlanacağına karar verme](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md).

## <a name="step-2-add-the-app"></a>2. Adım: Uygulamayı ekleme

İş kolu uygulamanızı MAM ilkeleriyle ilişkilendirmek için uygulama ayrıntılarını aşağıdaki adımları kullanarak Intune aboneliğinize/kiracınıza eklemelisiniz:

1. [Azure portalında](https://portal.azure.com/) **Intune mobil uygulama yönetimi** > **Ayarlar**'a gidin ve **İş kolu uygulamaları**'nı seçin.

  ![İş kolu seçeneğiyle Ayarlar dikey penceresinin ekran görüntüsü](../media/mam-azure-portal-lob-on-settings.png)

2. **İş kolu uygulamaları** dikey penceresinde **Özel uygulama ekle**'yi seçin.

  ![En üstünde Özel uygulama ekle düğmesiyle iş kolu uygulamaları dikey penceresinin ekran görüntüsü](../media/mam-azure-portal-add-lob-app-action.png)
3.    Uygulama için bir ad, Uygulama Tanımlayıcısı alanına paket tanımlayıcısı ve platformu (iOS veya Android) girin.

  ![Özel uygulama ekle dikey penceresinin ekran görüntüsü](../media/mam-azure-portal-add-app-details.png)

  Bu adım, uygulamanızın benzersiz bir listesini oluşturmanıza yardımcı olur. Uygulama, sonraki adımda açıklandığı gibi kiracınızın MAM ilkesine ilişkin Hedeflenen uygulamalar listesinde de görüntülenir.

## <a name="step-3-apply-mam-policies"></a>3. Adım: MAM ilkelerini uygulama
Uygulama meta verileri hizmete yüklendikten sonra uygulama, uygulamalar listesinde gösterilir. Artık [yeni ilke oluşturabilir veya mevcut bir ilkeyi kullanabilir](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) ve bu ilkeyi 2. adımda eklediğiniz iş kolu uygulamasına uygulayabilirsiniz.

>[!IMPORTANT]
>MAM ilkesiyle, sarmalanan uygulamayı kullanacak olan kullanıcıları hedeflemelisiniz.  Kendilerine bu ilke dağıtılmayan kullanıcılar uygulamayı kullanamaz.


  ![Yeni iş kolu uygulamasının gösterildiği Hedeflenen uygulamalar listesi dikey penceresinin ekran görüntüsü](../media/mam-azure-portal-lob-on-targeted-app-list.png)
## <a name="step-4-distribute-the-app"></a>4. Adım: Uygulamayı dağıtma
Uygulamaları kullanıcılarınıza aşağıdaki yollarla dağıtabilirsiniz:
* Üçüncü taraf bir MDM çözümüne kayıtlı cihazlarda, uygulamaları MDM çözümünüz aracılığıyla dağıtabilirsiniz.
* Hiçbir MDM çözümüyle yönetilmeyen cihazlarda, özel bir çözüme ihtiyacınız vardır. Kullanıcıların uygulamayı indirmesi ve cihaza yüklemesi gerekir.

## <a name="change-the-metadata"></a>Meta verileri değiştirme
Uygulamanın adı veya Paket tanımlayıcısı gibi uygulama ayrıntılarını değiştirmeniz gerekiyorsa, [uygulamayı kaldırmalı](#remove-apps) ve yeni meta verilerle [eklemelisiniz](#step-2-add-the-app).

##  <a name="remove-apps"></a>Uygulamaları kaldırma
Uygulama listesinden bir iş kolu uygulamasını kaldırabilirsiniz. Bu işlem uygulamayı listeden kaldırır ve MAM ilkeleriyle ilişkisini siler ancak uygulamayı kullanıcının cihazından kaldırmaz.  

1.    [Azure portalında](https://portal.azure.com/) **Intune mobil uygulama yönetimi** > **Ayarlar**'a gidin. **Ayarlar** dikey penceresinde **İş kolu**’nu seçerek var olan uygulamalar listesini açın.  
2.    Kaldırmak istediğiniz uygulamayı ve ardından **(…) bağlam** menüsünü seçin.

  ![Üç noktalı iş kolu uygulamaları dikey penceresinin ekran görüntüsü](../media/mam-azure-portal-lob-context-menu.png)
3.    Uygulamayı silmek için **Uygulama Sil**’i seçin.

  ![Uygulamayı sil seçeneğiyle iş kolu uygulaması dikey penceresinin ekran görüntüsü](../media/mam-azure-portal-delete-app.png)

  Bu işlem, uygulamaları iş kolu uygulamaları listesinden ve MAM ilkesindeki Hedeflenen uygulamalar listesinden kaldırır.



<!--HONumber=Dec16_HO2-->


