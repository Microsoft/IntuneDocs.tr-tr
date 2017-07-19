---
title: "Yardım masası sorun giderme portalı"
titleSuffix: Intune on Azure
description: "Yardım masası personeli, kullanıcıların teknik sorunlarını çözmek için sorun giderme portalını kullanır"
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: sumitp
ms.custom: intune-azure
ms.openlocfilehash: 7a61c3703cd1016ef63c8baa371c3a21dca127fc
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="help-users-with-the-troubleshooting-portal-in-microsoft-intune"></a>Microsoft Intune’daki Sorun Giderme portalıyla kullanıcılara yardımcı olun

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Sorun giderme portalı, yardım masası operatörlerinin ve Intune yöneticilerinin kullanıcı yardım isteklerini karşılamak için kullanıcı bilgilerini görüntülemesine izin verir. Kadrolarının bir parçası olarak yardım masası operatörleri olan kuruluşlar **Yardım masası operatörünü** bir grup kullanıcıya atayabilir ve operatör daha sonra kullanıcılara yardım etmek için Sorun Giderme dikey penceresini kullanabilir.

Örneğin, bir kullanıcı Intune ile ilgili teknik bir sorun için destekle bağlantı kurduğunda, yardım masası operatörü kullanıcının adını girer. Intune; kullanıcı durumu, uygulama yükleme hatası veya uyumluluk sorunları gibi pek çok katman 1 sorununu çözümlemeye yardımcı olabilecek ilgili bilgileri görüntüler. Giderilen sorunlar şunları içerebilir:
- Cihaz yanıt vermiyor
-   Cihaz VPN veya Wi-Fi ayarlarını alamıyor
-   Uygulama yükleme hatası


## <a name="add-help-desk-operators"></a>Yardım masası operatörleri ekleme
Bir Intune yöneticisi, kullanıcılara yardım masası operatörü iznini iki şekilde atayabilir:
- Yerleşik **Yardım Masası Operatörü** rolü atama
- Özel bir rol oluşturup atayarak

## <a name="assign-help-desk-operator-role"></a>Yardım masası operatörü rolü atama
Bir Intune yöneticisi olarak bir kullanıcı grubuna Yardım Masası Operatörü rolü atayabilirsiniz. Bu grubun üyeleri yönetici portalını kullanabilir. Intune portalına erişmek için her yardım masası operatörünün bir Intune lisansı olması gerekir. [Intune kullanıcı lisanslarını atamayı](licenses-assign.md) öğrenin.

1. Bir Intune yöneticisi olarak Intune portalında oturum açın ve **Intune rollerini** seçin.
2. **Intune rolleri** iş yükünde, **Yardım Masası Operatörü** > **Atamalar**'ı, sonra **Ata**'yı seçin.
  ![Intune rollerinin vurgulanmış olduğu ve Atama özelliği çevresinde Atamalar’ın vurgulandığı Yardım Masası Operatörü dahil yerleşik rollerin listesini içeren Intune portalının ekran görüntüsü](./media/help-desk-user-assign.png)
3. Bir **Atama adı** (gerekli), bir **Atama açıklaması** (isteğe bağlı) girin ve ardından **Üyeler (Gruplar)** ve **Kapsam (Gruplar)** atayın.
4. Yardım Masası Operatör rolü üyeleri artık sorun giderme portalını kullanabilir.

Intune rolleri hakkında daha fazla bilgi için bkz. [Intune rolleri (RBAC)](role-based-access-control.md).

## <a name="create-a-custom-role-for-troubleshooting"></a>Sorun giderme için özel bir rol oluşturma
Bir Intune yöneticisi olarak kullanıcıların, kuruluşunuzun ihtiyaçlarına uyan izinlere sahip sorun giderme portalını kullanması için özel bir rol oluşturabilirsiniz. Intune rolleri hakkında daha fazla bilgi için bkz. [Intune rolleri (RBAC)](role-based-access-control.md).

![Intune rollerinin vurgulandığı ve Yardım Masası Operatörü dahil yerleşik rollerin bir listesini içeren Intune portalını gösteren ekran görüntüsü](./media/help-desk-user-add.png)

Bir yardım masası görünümünde Intune konsolunu kullanmak için özel bir yardım masası rolü şu izinlere sahip olmalıdır:
- MobileApps: Okuma
- ManagedApps: Okuma
- ManagedDevices: Okuma
- Organization: Okuma

## <a name="access-the-troubleshooting-portal"></a>Sorun giderme portalına erişme

Yardım masası personeli ve Intune yöneticileri sorun giderme portalına iki yolla erişebilir:
- Bir web tarayıcısında [http://aka.ms/intunetroubleshooting](http://aka.ms/intunetroubleshooting) adresini açın.
- Intune portalında **Yardım ve Destek** > **Sorun Gider**'e gidin.

![Kullanıcı Seç bağlantısı ile Intune Sorun Giderme iş yükü ekran görüntüsü](media/help-desk-user.png)

## <a name="use-the-troubleshooting-portal"></a>Sorun giderme portalını kullanma

Sorun giderme portalında, kullanıcıların bilgilerini görüntülemek için **Kullanıcı seç**’e tıklayın. Kullanıcı bilgileri, kullanıcıların ve cihazlarının geçerli durumunu anlamanıza yardımcı olabilir. Sorun giderme portalı aşağıdaki sorun giderme ayrıntılarını gösterir:
- **Kiracı durumu**
- **Kullanıcı durumu**
- **Cihazlar** ve cihaz eylemleri
- **Grup üyeliği**
- **Uygulama koruma durumu**
