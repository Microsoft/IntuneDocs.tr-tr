---
title: "Yardım masası sorun giderme portalı | Microsoft Docs"
titleSuffix: Intune Azure preview
description: "Yardım masası personeli, kullanıcıların teknik sorunlarını çözmek için sorun giderme portalını kullanır"
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 03/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: sumitp
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 3758df744311392528be01c826527c2a9d879975
ms.openlocfilehash: 8cf12e434518c9f06c105a22f3b7aef2613fcdb0
ms.contentlocale: tr-tr
ms.lasthandoff: 05/10/2017

---
# <a name="help-users-with-the-troubleshooting-portal-in-microsoft-intune"></a>Microsoft Intune’daki Sorun Giderme portalıyla kullanıcılara yardımcı olun

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Sorun giderme portalı yardım masası operatörlerinin ve Intune yöneticilerinin, kullanıcıları ve cihazlarını görüntülemesine ve Intune teknik sorunlarını çözmek için görevler gerçekleştirmelerine izin verir.

## <a name="add-help-desk-operators"></a>Yardım masası operatörleri ekleme
Bir Intune yöneticisi, kullanıcılara yardım masası operatörü izni atayabilir. Ardından yardım masası kullanıcıları Intune portalını görüntüleyebilir ancak sorun giderme iş yükü dışındaki yönetim görevlerini görüntüleyemez veya yapamaz.

1. Bir Intune yöneticisi olarak [Azure portalında](https:portal.azure.com) oturum açın, **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune** seçeneğini belirleyin.
2. Sol gezinti bölmesi dikey penceresinde, **Intune rolleri**’ni seçin.
3. **Intune rolleri** iş yükünde, **Yardım Masası Operatörü** ve ardından **Ata**’yı seçin.
4. Bir **Atama adı** (gerekli), bir **Atama açıklaması** (isteğe bağlı) girin ve ardından **Üyeler (Gruplar)** ve **Kapsam (Gruplar)** atayın.
5. Yardım Masası Operatör rolü üyeleri artık sorun giderme portalını kullanabilir.

Intune rolleri hakkında daha fazla bilgi için bkz. [Intune rolleri (RBAC)](../access-control/role-based-access-control.md).

## <a name="access-the-troubleshooting-portal"></a>Sorun giderme portalına erişme

Yardım masası personeli ve Intune yöneticileri sorun giderme portalına iki yolla erişebilir:
- [Azure portalında](https://portal.azure.com) **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin ve ardından sol gezinti bölmesi dikey penceresinde **Sorun Giderme**’yi seçin. Diğer iş yükleri sol gezinti bölmesi dikey penceresinde görünür, ancak kullanılamaz.

![Kullanıcı Seç bağlantısı ile Intune Sorun Giderme iş yükü ekran görüntüsü](media/help-desk-user.png)
- Bir web tarayıcısında [http://aka.ms/intunetroubleshooting](http://aka.ms/intunetroubleshooting) adresini açın. Yalnızca Sorun giderme portalı görünür.

## <a name="use-the-troubleshooting-portal"></a>Sorun giderme portalını kullanma

Sorun giderme portalında, kullanıcıların bilgilerini görüntülemek için **Kullanıcı Seç**’e tıklayın. Kullanıcı bilgileri, kullanıcıların ve cihazlarının geçerli durumunu anlamanıza yardımcı olabilir. Sorun giderme portalı aşağıdaki Intune kullanıcı ve cihaz ayrıntılarını gösterir:
- Kullanıcı hesap bilgileri
- Kullanıcı grup üyeliği
- Cihaz ayrıntıları

Yardım masası kullanıcıları ayrıca, **Uzaktan kilitleme** gibi uzak görevleri gerçekleştirebilir.

