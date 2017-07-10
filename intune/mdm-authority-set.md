---
title: "Mobil cihaz yönetimi yetkilisini ayarlayın"
titleSuffix: Intune on Azure
description: "Intune'da mobil cihaz yönetimi yetkilisini ayarlamayı öğrenin. \""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 05/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 449c45e0edcc0d0a33352ba154ad68fa6c4725c0
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="set-the-mobile-device-management-authority"></a>Mobil cihaz yönetimi yetkilisini ayarlayın

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Mobil cihaz yönetimi (MDM) yetkili ayarı, cihazlarınızı yönetme şeklinizi belirler. Kullanıcıların yönetilmek üzere cihaz kaydedebilmeleri için, BT yöneticisi olarak bir MDM yetkilisi ayarlamanız gerekir.

Olası yapılandırmalar şunlardır:

- **Intune Tek Başına** - Azure Portal’ı kullanarak yapılandırdığınız yalnızca bulut yönetimi. Intune’un sunduğu özelliklerin tamamını içerir. [MDM yetkilisini Intune konsolundan ayarlama](#mdm-authority-set-to-intune).

- **Intune Karma** - Intune bulut çözümünün System Center Configuration Manager ile tümleştirmesi. Configuration Manager konsolunu kullanarak Intune’u siz yapılandırırsınız. [MDM yetkilisini Yapılandırma Yöneticisi’nden ayarlama](https://docs.microsoft.com/sccm/mdm/deploy-use/configure-intune-subscription).

- **Office 365 için Mobil Cihaz Yönetimi** - Office 365’in Intune bulut çözümüyle tümleştirmesi. Office 365 Yönetim Merkezi’nden Intune’u siz yapılandırırsınız. Intune Tek Başına ile sağlanan özelliklerin bir alt kümesini içerir. MDM yetkilisini Office 365 Yönetim Merkezi’nden ayarlama.

>[!IMPORTANT]    
Configuration Manager'ın 1610 veya sonraki bir sürümü ve Microsoft Intune'un 1705 sürümünde, MDM yetkilisini, Microsoft Destek ile iletişim kurmaya ve mevcut yönetilen cihazlarınızın kaydını silip tekrar kaydetmeye gerek kalmadan değiştirebilirsiniz. Ayrıntılar için bkz. [Yanlış MDM yetkilisi ayarı seçilirse yapılacaklar](/intune-classic/deploy-use/prerequisites-for-enrollment#what-to-do-if-you-choose-the-wrong-mdm-authority-setting).

## <a name="set-mdm-authority-to-intune"></a>MDM yetkilisini Intune olarak ayarlama

1. Azure portalında **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
  ![Intune Sorun Giderme iş yükünün Kullanıcı Seçme bağlantısıyla ekran görüntüsü](media/set-mdm-auth.png)
2. Intune dikey penceresinde **Cihaz kaydetme**’yi ve ardından **Genel Bakış**’ı seçin.

3. **Cihazları yönetmeye başla** dikey penceresinde **MDM Yetkilisini Intune olarak ayarla**’yı seçin. MDM yetkilinizi başarıyla Intune olarak ayarladığınızı bildiren bir ileti görüntülenir.

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>MDM sertifikası süre sonunda mobil cihazı temizleme

Mobil cihazlar Intune hizmetiyle iletişim kurduğunda MDM sertifikası otomatik olarak yenilenir. Mobil cihazlar temizlendiğinde veya belirli bir süre boyunca Intune hizmetiyle iletişim kuramadığında, MDM sertifikası yenilenmez. MDM sertifikasının süre sonundan 180 gün sonra, cihaz Azure Portal’dan kaldırılır.
