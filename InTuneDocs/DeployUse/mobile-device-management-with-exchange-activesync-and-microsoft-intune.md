---
title: "Exchange ActiveSync Cihaz Yönetimi | Microsoft Intune"
description: "Kullanıcıların Exchange ActiveSync (EAS) yönetimine kaydetmediği mobil cihazları Exchange bağlayıcısını kullanarak doğrudan yönetin"
keywords: 
author: nathbarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 14f5cf53-6764-4e22-a18b-fa750b3acd41
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e9cbf5858cc4e860b540f421b6d463b8e7a429cf
ms.openlocfilehash: f545c7db4c29690a72c5a84dfcab6f179cbe72a2


---

# Exchange ActiveSync ve Microsoft Intune ile mobil cihaz yönetimi
Mobil cihazların Microsoft Intune tarafından doğrudan yönetilebilmesi için kullanıcıların cihazları Intune’a kaydetmeleri gerekir. Kullanıcıların kaydetmediği mobil cihazlar için Exchange bağlayıcısını kullanarak Exchange ActiveSync (EAS) yönetimini etkinleştirebilirsiniz. Cihazları hem Şirket İçi Exchange sunucularda hem de Microsoft Office 365'te bulutta barındırılan Exchange’de yönetilebilir.

## Mobil cihazlar için Exchange erişim kuralları ##

Exchange’e, mobil cihazlar EAS’a bağlanmaya çalıştığında ne olacağını tanımlayan bir dizi kural gerekir. Bu kurallar, Intune yönetim konsolunda yönetilir.

[Mobil cihazlar için Exchange erişim kuralları](exchange-access-rules-for-mobile-devices.md)

## Exchange bağlayıcısını yükleme
Exchange bağlayıcısı, Intune konsolunda Exchange dağıtımınızı yönetmenize olanak tanır. Öncelikle uygun Intune-Exchange bağlayıcısını yüklemeli ve yapılandırmalısınız. Exchange sunucunuzun şirket içinde mi yoksa hizmet olarak bulutta mı barındırıldığına bağlı olarak, uygun seçeneği belirtin:

-   [Şirket İçi Exchange için Intune bağlayıcısını yükleme](intune-on-premises-exchange-connector.md)
-   [Barındırılan Exchange için Intune Hizmetten Hizmete bağlayıcısını yapılandırma](intune-service-to-service-exchange-connector.md)

## Exchange tarafından yönetilen mobil cihazlara ilke uygulama
İlke ayarları Intune konsolu aracılığıyla uygulanabilir. Bkz. [Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md). Belirli mobil cihazlar tarafından desteklenen Exchange ActiveSync ilke ayarları ve özelliklerinin listesi için, bkz. [Exchange ActiveSync İstemci Karşılaştırma Tablosu](http://go.microsoft.com/fwlink/?LinkId=247270).

> [!NOTE]
> Intune’u Microsoft Exchange ortamına bağladıktan sonra, Intune içinde daha belirgin bir ilke tanımlanmadığı sürece, tüm kullanıcılar için Intune aracılığıyla yönetilen EAS ilkesi Microsoft Exchange sunucusundaki geçerli varsayılan ilkeye sıfırlanır.

## Mobil cihazlardan şirket verileri temizleme
Son olarak, şirket verileri artık kullanılmıyorsa ya da cihazlar kaybolur veya çalınırsa, [şirket verilerini EAS ile yönetilen mobil cihazlardan temizleyebilirsiniz](wipe-for-exchange-managed-mobile-devices.md).



<!--HONumber=Jul16_HO4-->


