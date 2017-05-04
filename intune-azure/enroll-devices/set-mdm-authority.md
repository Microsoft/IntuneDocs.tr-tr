---
title: "Mobil cihaz yönetimi yetkilisini ayarlayın"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Intune’da mobil cihaz yönetimi yetkilisini ayarlamayı öğrenin. "
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 04/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: dc08ba96eeea0ce2aad78e4d6ca0d94e709d885d
ms.openlocfilehash: 6cf7c56924091713f55fe8824fb11e522825b98f
ms.lasthandoff: 04/21/2017

---

# <a name="set-the-mobile-device-management-authority"></a>Mobil cihaz yönetimi yetkilisini ayarlayın

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Mobil cihaz yönetimi (MDM) yetkili ayarı, cihazlarınızı yönetme şeklinizi belirler. Kullanıcıların yönetilmek üzere cihaz kaydedebilmeleri için, BT yöneticisi olarak bir MDM yetkilisi ayarlamanız gerekir.

Olası yapılandırmalar şunlardır:

- **Intune Tek Başına** - Azure Portal’ı kullanarak yapılandırdığınız yalnızca bulut yönetimi. Intune’un sunduğu özelliklerin tamamını içerir. [MDM yetkilisini Intune konsolundan ayarlama](#set-mdm-authority-to-Intune).

- **Intune Karma** - Intune bulut çözümünün System Center Configuration Manager ile tümleştirmesi. Configuration Manager konsolunu kullanarak Intune’u siz yapılandırırsınız. [MDM yetkilisini Yapılandırma Yöneticisi’nden ayarlama](https://docs.microsoft.com/sccm/mdm/deploy-use/configure-intune-subscription).

- **Office 365 için Mobil Cihaz Yönetimi** - Office 365’in Intune bulut çözümüyle tümleştirmesi. Office 365 Yönetim Merkezi’nden Intune’u siz yapılandırırsınız. Intune Tek Başına ile sağlanan özelliklerin bir alt kümesini içerir. MDM yetkilisini Office 365 Yönetim Merkezi’nden ayarlama.

>[!IMPORTANT]
>Mobil cihaz yönetimi yetkilisini ayarladıktan sonra, değiştirmek için [Microsoft Desteği](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune)’ne başvurmanız gerekir; dolayısıyla seçiminizi yaparken özen gösterin.

## <a name="set-mdm-authority-to-intune"></a>MDM yetkilisini Intune olarak ayarlama

1. Azure portalında **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
  ![Intune Sorun Giderme iş yükünün Kullanıcı Seçme bağlantısıyla ekran görüntüsü](media/set-mdm-auth.png)
2. Intune dikey penceresinde **Cihaz kaydetme**’yi ve ardından **Genel Bakış**’ı seçin.

3. **Cihazları yönetmeye başla** dikey penceresinde **MDM Yetkilisini Intune olarak ayarla**’yı seçin. MDM yetkilinizi başarıyla Intune olarak ayarladığınızı bildiren bir ileti görüntülenir.

