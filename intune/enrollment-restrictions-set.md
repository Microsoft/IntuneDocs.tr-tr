---
title: "Intune’da kayıt kısıtlamalarını ayarlama"
titlesuffix: Azure portal
description: "Intune’da platforma göre kaydı kısıtlama ve cihaz kayıt sınırı ayarlama. \""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 06c0c58992a2119aff7fd5be54ae90be886d2a53
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/09/2017
---
# <a name="set-enrollment-restrictions"></a>Kayıt kısıtlamalarını ayarlama

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Bir Intune yöneticisi olarak hangi cihazların Intune yönetimine kaydedilebileceğini belirleyebilirsiniz. Aşağıdaki cihaz kayıt kısıtlamalarını ayarlamak için Azure portalını kullanın:

- Kayıtlı cihaz sayısı üst sınırı
- Kaydedilebilecek cihaz platformları:
  - Android
  - iOS
  - Mac OS
  - Windows
- Platform işletim sistemi sürümü (yalnızca iOS ve Android)
  - En düşük sürüm
  - En yüksek sürüm
- Kişisel cihazları kısıtlama (yalnızca iOS, Android ve macOS)

>[!NOTE]
>Kayıt kısıtlamaları güvenlik özellikleri değildir. Güvenliği aşılan cihazlar karakterlerini yanlış gösterebilir. Bu kısıtlamalar, kötü amaçlı olmayan kullanıcılara yönelik olabilecek en iyi engeldir.

## <a name="set-device-type-restrictions"></a>Cihaz türü kısıtlamalarını ayarlama
Varsayılan kayıt kısıtlamaları tüm kullanıcılar ve kullanıcısız kayıtlar için geçerlidir.
1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Cihaz kaydı** > **Kayıt kısıtlamaları**’nı seçin.
4. **Kayıt kısıtlamaları** > **Cihaz Türü Kısıtlamaları** altında **Varsayılan**’ı seçin.
5. **Tüm Kullanıcılar** altında **Platformlar**’ı seçin. Her platform için **İzin Ver** veya **Engelle** seçeneklerini belirtin:
  - **Android**
  - **Android**
  - **macOS**
  - **Windows**

  **Kaydet**'e tıklayın.
6. **Tüm Kullanıcılar** altında **Platform Yapılandırmaları**’nı seçin ve aşağıdaki yapılandırmaları belirleyin. İzin verilen her platform için aşağıdaki seçenekleri yapılandırabilirsiniz:
  - **Sürümler** - Android ve iOS cihazları için **En Düşük** ve **En Yüksek** platform işletim sistemi sürümlerini belirtin. İşletim sistemi sürümleri, Aygıt Kayıt Programı, Apple School Manager veya Apple Configurator uygulaması ile kaydedilen cihazlar için geçerli değildir.
  - **Kişisel** - Android, iOS ve macOS cihazlar için **İzin Ver** veya **Engelle** seçeneklerinden birini belirtin.
  ![Varsayılan cihaz platform yapılandırmaları ile cihaz kısıtlamaları iş alanının, kişisel ayarların yapılandırıldığını gösteren ekran görüntüsü.](media/device-restrictions-platform-configurations.png)
  **Kaydet**'e tıklayın.

>[!NOTE]
>Kişisel Android cihazların kaydını engellerseniz kişisel Android for Work cihazlar hala kaydedilebilir durumda olacaktır.

## <a name="set-device-limit-restrictions"></a>Cihaz sınırı kısıtlamalarını ayarlama
Varsayılan kayıt kısıtlamaları tüm kullanıcılar için geçerlidir.
1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Cihaz kaydı** > **Kayıt kısıtlamaları**’nı seçin.
4. Azure portalında **Cihaz kaydı**’nı seçtikten sonra **Kayıt kısıtlamaları**’nı seçin.
5. **Kayıt kısıtlamaları** > **Cihaz Sınır Kısıtlamaları**’nı seçin.
6. **Tüm Kullanıcılar** altında **Cihaz Sınırı**’nı seçin. Kullanıcı başına düşen kayıtlı cihaz sayısı üst sınırını belirtin.  
![Cihaz sınır kısıtlamaları ile cihaz sınır kısıtlamaları dikey penceresinin ekran görüntüsü.](./media/device-restrictions-limit.png)

  **Kaydet**'e tıklayın.
