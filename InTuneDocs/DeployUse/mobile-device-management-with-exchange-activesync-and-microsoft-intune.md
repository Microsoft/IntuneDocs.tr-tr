---
title: "Exchange ActiveSync Cihaz Yönetimi | Microsoft Intune"
description: "Exchange bağlayıcısını kullanarak Exchange ActiveSync (EAS) yönetimi ile mobil cihaz yönetme"
keywords: 
author: nathbarn
manager: angrobe
ms.date: 07/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 14f5cf53-6764-4e22-a18b-fa750b3acd41
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c880bd9dfb998355a18e78af898a96d4cee393f7
ms.openlocfilehash: 9518381dfd967b8cbf8d01bf834d8148d2c2501b


---

# Microsoft Intune ile Exchange ActiveSync mobil cihaz yönetimi
Microsoft Intune’un mobil cihazları doğrudan yönetebilmesi için cihazların [Intune’da kayıtlı](prerequisites-for-enrollment.md) olması gerekir. Alternatif olarak yöneticiler, Exchange ActiveSync (EAS) yönetimini Exchange bağlayıcısıyla kullanan, daha kısıtlı bir yönetim çözümü etkinleştirebilir. Cihazlar, şirket içi Exchange sunucularıyla veya Office 365 kullanılarak Exchange Online ile yönetilebilir. Intune, abonelik başına herhangi bir türde tek bir Exchange bağlayıcısı bağlantısını destekler.

## Mobil cihazlar için Exchange erişim kuralları ##

Exchange’e, mobil cihazlar EAS’a bağlanmaya çalıştığında ne olacağını tanımlayan bir dizi kural gerekir. Bu kurallar, Intune yönetim konsolunda yönetilir.

[Mobil cihazlar için Exchange erişim kuralları](exchange-access-rules-for-mobile-devices.md)

## Exchange bağlayıcısını yükleme
Exchange bağlayıcısı, Intune konsolunda Exchange dağıtımınızı yönetmenize olanak tanır. Öncelikle uygun Intune-Exchange bağlayıcısını yüklemeli ve yapılandırmalısınız. Exchange sunucunuzun şirket içinde mi yoksa hizmet olarak bulutta mı barındırıldığına bağlı olarak, uygun seçeneği belirtin:

-   [Exchange Online için Intune veya yeni Exchange Online Ayrılmış ortamları yapılandırma](intune-service-to-service-exchange-connector.md)
-   [Şirket içi Exchange sunucuları ve eski Exchange Online Ayrılmış ortamları için Intune bağlayıcısını yükleme](intune-on-premises-exchange-connector.md)


## Exchange tarafından yönetilen mobil cihazlara ilke uygulama
Intune konsolu, [EAS ilke ayarlarını](exchange-activesync-policy-settings-in-microsoft-intune.md) yönetmek ve [şirket kaynaklarına erişimi kısıtlamak](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) için kullanılabilir. Belirli mobil cihazlar tarafından desteklenen Exchange ActiveSync ilke ayarları ve özelliklerinin listesi için, bkz. [Exchange ActiveSync İstemci Karşılaştırma Tablosu](http://go.microsoft.com/fwlink/?LinkId=247270).

> [!NOTE]
> Intune’u Microsoft Exchange ortamına bağladıktan sonra, Intune içinde daha belirgin bir ilke tanımlanmadığı sürece, tüm kullanıcılar için Intune aracılığıyla yönetilen EAS ilkesi Microsoft Exchange sunucusundaki geçerli varsayılan ilkeye sıfırlanır.

## Mobil cihazlardan şirket verileri temizleme
Son olarak, şirket verileri artık kullanılmıyorsa ya da cihazlar kaybolur veya çalınırsa, [şirket verilerini EAS ile yönetilen mobil cihazlardan temizleyebilirsiniz](wipe-for-exchange-managed-mobile-devices.md).



<!--HONumber=Sep16_HO4-->


