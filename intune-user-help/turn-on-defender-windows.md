---
title: Windows Defender’ı etkinleştirme | Microsoft Docs
description: Şirket kaynaklarına erişmek için Windows Defender’ı etkinleştirme hakkında bilgi edinin.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 11/08/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d16dd2de-3ed5-474f-a04b-36dcd350162c
searchScope:
- User help
ROBOTS: ''
ms.reviewer: shburbid
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8d51e9db367925442c7b6c735b1de86891e05856
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55845287"
---
# <a name="turn-on-windows-defender-to-access-company-resources"></a>Şirket kaynaklarına erişmek için Windows Defender’ı etkinleştirme

İşiniz veya okulunuz, kaynaklarına erişen cihazların güvenli olduğundan emin olmak ister. Windows’un kötü amaçlı yazılımlara karşı yerleşik koruması olan [Windows Defender](https://www.microsoft.com/safety/pc-security/windows-defender.aspx)’ı kullanmalarının birkaç yolu vardır.

Erişim sorunlarını düzeltmek için Windows Defender’ınızda değiştirmeniz gereken birkaç ayar vardır. Bu adımlar, bilgisayarınızda birkaç farklı yere gitmenizi gerektirebilir.

## <a name="turn-on-windows-defender"></a>Windows Defender’ı etkinleştirme

1. **Başlangıç**’ta **Denetim Masası**’nı açın.
2. **Yönetimsel Araçlar** > **Grup ilkesi düzenleme**’yi açın. Bu, **Yerel Grup İlkesi Düzenleyicisi**’ni yeni bir pencerede açar.
3. **Bilgisayar Yapılandırması** > **Yönetim Şablonları** > **Windows Bileşenleri** > **Windows Defender Antivirüs**’ü açın. **Windows Defender Antivirüs’ü kapatma** ayarı, diğer ayar klasörlerinin altındadır. 
4. **Windows Defender Antivirüs’ü kapatma**’yı açın ve **Devre dışı** veya **Yapılandırılmamış** olarak ayarlı olduğundan emin olun.

## <a name="turn-on-real-time-protection"></a>Gerçek zamanlı korumayı etkinleştirme

**Başlangıç**’a gidip **Windows Defender Güvenlik Merkezi** için arama yaparak Gerçek Zamanlı Korumanın etkin olduğundan emin olun. **Virüs ve tehdit koruma ayarları**’nı seçin ve **Gerçek zamanlı koruma** ile **Bulut ile sunulan koruma**’nin **Açık** olarak ayarlı olduğunu onaylayın. Bu seçenekler görünmüyorsa, etkin olmaları için şunları yapın:

1. **Başlangıç**’ta **Denetim Masası**’nı açın.
2. **Yönetimsel Araçlar** > **Grup ilkesi düzenleme**’yi açın. Bu, **Yerel Grup İlkesi Düzenleyicisi**’ni yeni bir pencerede açar.
3. **Bilgisayar Yapılandırması** > **Yönetim Şablonları** > **Windows Bileşenleri** > **Windows Defender Güvenlik Merkezi** > **Virüs ve tehdit koruması**’nı açın.
4. **Virüs ve tehdit koruma alanı** ayarını açın ve **Devre dışı** olarak ayarlayın.

## <a name="update-your-antivirus-definitions"></a>Antivirüs tanımlarınızı güncelleştirme

**Başlangıç**’a gidip **Windows Defender Güvenlik Merkezi** için arama yaparak antivirüs tanımlarınızın güncel olduğundan emin olun. **Koruma güncelleştirmeleri**’ni seçin ve **Güncelleştirmeleri denetle**’ye tıklayarak cihazınızın virüslere karşı korumasının güncel olduğundan emin olun. Bu seçenek görünmüyorsa, [Gerçek Zamanlı Korumayı etkinleştirme](turn-on-defender-windows.md#turn-on-real-time-protection) adımlarını izleyin

Bu bilgiler yardımcı olmadı mı? Şirketinizin destek bölümüne başvurun. Kişi bilgileri için [Şirket Portalı Web sitesine](https://go.microsoft.com/fwlink/?linkid=2010980) bakın.
