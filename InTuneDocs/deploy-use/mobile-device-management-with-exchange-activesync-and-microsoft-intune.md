---
title: "Exchange ActiveSync Cihaz Yönetimi | Microsoft Docs"
description: "Exchange bağlayıcısını kullanarak Exchange ActiveSync (EAS) yönetimi ile mobil cihaz yönetme"
keywords: 
author: andredm7
ms.author: andredm
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
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 4d1fc1af29dbd42c639afe079020d35a92360eb3


---

# <a name="exchange-activesync-mobile-device-management-with-microsoft-intune"></a>Microsoft Intune ile Exchange ActiveSync mobil cihaz yönetimi

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune’un mobil cihazları doğrudan yönetebilmesi için cihazların [Intune’da kayıtlı](prerequisites-for-enrollment.md) olması gerekir. Yöneticiler alternatif olarak, Exchange ActiveSync (EAS) yönetimini Exchange bağlayıcısıyla kullanan, daha kısıtlı bir yönetim çözümü etkinleştirebilir. Cihazlar, şirket içi Exchange sunucularıyla veya Office 365 kullanılarak Exchange Online ile yönetilebilir. Intune, herhangi bir abonelik türü için sadece tek bir Exchange bağlayıcısı bağlantısını destekler.

## <a name="exchange-access-rules-for-mobile-devices"></a>Mobil cihazlar için Exchange erişim kuralları ##

Exchange’e, mobil cihazlar EAS’a bağlanmaya çalıştığında ne olacağını tanımlayan bir dizi kural gerekir. Bu kurallar, Intune yönetim konsolunda yönetilir.

[Mobil cihazlar için Exchange erişim kuralları](exchange-access-rules-for-mobile-devices.md)

## <a name="install-the-exchange-connector"></a>Exchange bağlayıcısını yükleme
Exchange bağlayıcısı, Intune konsolunda Exchange dağıtımınızı yönetmenize olanak tanır. Öncelikle uygun Intune-Exchange bağlayıcısını yüklemeli ve ayarlamalısınız. Exchange sunucunuzun şirket içinde mi yoksa hizmet olarak bulutta mı barındırıldığına bağlı olarak uygun seçeneği belirtin:

-   [Exchange Online için Intune veya yeni Ayrılmış Exchange Online ortamlarını yapılandırma](intune-service-to-service-exchange-connector.md)
-   [Şirket içi Exchange sunucuları ve eski Ayrılmış Exchange Online ortamları için Intune bağlayıcısını yükleme](intune-on-premises-exchange-connector.md)


## <a name="apply-policy-for-exchange-managed-mobile-devices"></a>Exchange tarafından yönetilen mobil cihazlara ilke uygulama
Intune konsolu, [EAS ilke ayarlarını](exchange-activesync-policy-settings-in-microsoft-intune.md) yönetmek ve [şirket kaynaklarına erişimi kısıtlamak](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) için kullanılabilir. Belirli mobil cihazlar tarafından desteklenen Exchange ActiveSync ilke ayarları ve özelliklerinin listesi için bkz. [Exchange ActiveSync İstemci Karşılaştırma Tablosu](http://go.microsoft.com/fwlink/?LinkId=247270).

> [!NOTE]
> Intune’u Microsoft Exchange ortamına bağladıktan sonra, Intune içinde daha belirgin bir ilke tanımlanmadığı sürece, tüm kullanıcılar için Intune aracılığıyla yönetilen EAS ilkesi Microsoft Exchange sunucusundaki geçerli varsayılan ilkeye sıfırlanır.

## <a name="wipe-company-data-from-mobile-devices"></a>Mobil cihazlardan şirket verileri temizleme
Son olarak, şirket verileri artık kullanılmıyorsa ya da cihazlar kaybolur veya çalınırsa, [şirket verilerini EAS ile yönetilen mobil cihazlardan temizleyebilirsiniz](wipe-for-exchange-managed-mobile-devices.md).



<!--HONumber=Dec16_HO2-->


