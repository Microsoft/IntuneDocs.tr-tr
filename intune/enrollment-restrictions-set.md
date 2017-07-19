---
title: "Intune’da kayıt kısıtlamalarını ayarlama"
titleSuffix: Intune on Azure
description: "Intune’da platforma göre kaydı kısıtlama ve cihaz kayıt sınırı ayarlama. \""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2dfcba8c788f262ce816dcd23dc2921fd57f331b
ms.sourcegitcommit: d1ad84edf4f03cb4c11fe55131556b43fc3a4500
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/05/2017
---
# <a name="set-enrollment-restrictions"></a>Kayıt kısıtlamalarını ayarlama

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Bir Intune yöneticisi olarak hangi cihazların Intune yönetimine kaydedilebileceğini belirleyebilirsiniz. Aşağıdaki cihaz kayıt kısıtlamalarını ayarlamak için Intune portalını kullanın:

- Kayıtlı cihaz sayısı üst sınırı
- Kaydedilebilecek cihaz platformları:
  - Android
  - iOS
  - Mac OS
  - Windows
- Kişisel cihazları kısıtla (yalnızca iOS ve Android)

>[!NOTE]
>Kayıt kısıtlaması bir güvenlik özelliği değildir. Güvenliği aşılan cihazlar karakterlerini yanlış gösterebilir. Bu kısıtlamalar, kötü amaçlı olmayan kullanıcılara yönelik olabilecek en iyi engeldir.

## <a name="set-device-type-restrictions"></a>Cihaz türü kısıtlamalarını ayarlama
Varsayılan kayıt kısıtlamaları, daha yüksek öneme sahip kayıt kısıtlamaları atanmamış tüm kullanıcılara uygulanır.  
1. Intune portalında, **Cihaz kaydı**’nı seçtikten sonra **Kayıt kısıtlamaları**’nı seçin.
![Varsayılan cihaz türü kısıtlamaları ve cihaz sınır kısıtlamaları ile cihaz kısıtlamaları iş alanının ekran görüntüsü.](media/device-restrictions-set-default.png)
2. **Kayıt kısıtlamaları** > **Cihaz Türü Kısıtlamaları** altında **Varsayılan**’ı seçin.
3. **Tüm Kullanıcılar** altında **Platformlar**’ı seçin. Her platform için **İzin Ver** veya **Engelle** seçeneklerini belirtin:
  - **Android**
  - **Android**
  - **macOS**
  - **Windows**

  **Kaydet**'e tıklayın.
4. **Tüm Kullanıcılar** altında **Platform Yapılandırmaları**’nı seçin ve aşağıdaki yapılandırmaları seçin:
  - **Kişisel** - Android ve iOS cihazlar için **İzin Ver** veya **Engelle** seçeneklerinden birini belirtin.
  ![Varsayılan cihaz platform yapılandırmaları ile cihaz kısıtlamaları iş alanının, kişisel ayarların yapılandırıldığını gösteren ekran görüntüsü.](media/device-restrictions-platform-configurations.png)
  **Kaydet**'e tıklayın.

>[!NOTE]
>Kişisel Android cihazların kaydını engellerseniz Android for Work cihazlar hala kaydedilebilir durumda olacaktır.

## <a name="set-device-limit-restrictions"></a>Cihaz sınırı kısıtlamalarını ayarlama
Varsayılan kayıt kısıtlamaları, daha yüksek öneme sahip kayıt kısıtlamaları atanmamış tüm kullanıcılara uygulanır.  
1. Intune portalında, **Cihaz kaydı**’nı seçtikten sonra **Kayıt kısıtlamaları**’nı seçin.
2. **Kayıt kısıtlamaları** > **Cihaz Sınır Kısıtlamaları**’nı seçin.
3. **Tüm Kullanıcılar** altında **Cihaz Sınırı**’nı seçin. Kullanıcı başına düşen kayıtlı cihaz sayısı üst sınırını belirtin.  
![Cihaz sınır kısıtlamaları ile cihaz sınır kısıtlamaları dikey penceresinin ekran görüntüsü.](./media/device-restrictions-limit.png)

  **Kaydet**'e tıklayın.
