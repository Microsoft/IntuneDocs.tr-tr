---
title: "Mobil cihaz yönetimi yetkilisini ayarlama | Intune Azure önizlemesi | Microsoft Docs"
description: "Intune Azure önizlemesi: Intune’da mobil cihaz yönetimi yetkilisini ayarlamayı öğrenin. "
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 01/06/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 08dad848a48adad7d9c6f0b5b3286f6550a266bd
ms.openlocfilehash: 72a162175e278faa236add5698d65233fa851c7b
ms.lasthandoff: 02/15/2017

---

# <a name="set-the-mobile-device-management-authority"></a>Mobil cihaz yönetimi yetkilisini ayarlayın 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Mobil cihaz yönetimi yetkilisi ayarı, cihazları nasıl yönettiğinizi belirler. Olası yapılandırmalar şunlardır:

- **Intune Tek Başına** - Azure Portal’ı kullanarak yapılandırdığınız yalnızca bulut yönetimi. Intune’un sunduğu özelliklerin tamamını içerir.

- **Intune Karma** - Intune bulut çözümünün System Center Configuration Manager ile tümleştirmesi. Configuration Manager konsolunu kullanarak Intune’u siz yapılandırırsınız.

- **Office 365 için Mobil Cihaz Yönetimi** - Office 365’in Intune bulut çözümüyle tümleştirmesi. Office 365 Yönetim Merkezi’nden Intune’u siz yapılandırırsınız. Intune Tek Başına ile sağlanan özelliklerin bir alt kümesini içerir.

>[!IMPORTANT]
>Mobil cihaz yönetimi yetkilisini ayarladıktan sonra, değiştirmek için [Microsoft Desteği](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune)’ne başvurmanız gerekir; dolayısıyla seçiminizi yaparken özen gösterin.

**Mobil cihaz yönetimi yetkilisini ayarlamak için:**

1. Azure portalında **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.

2. Intune dikey penceresinde **Cihazları kaydet**’i ve ardından **Genel Bakış**’ı seçin.

3. **Cihazları yönetmeye başla** dikey penceresinde **MDM Yetkilisini Intune olarak ayarla**’yı seçin. MDM yetkilinizi başarıyla Intune olarak ayarladığınızı bildiren bir ileti görüntülenir.

