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
ms.openlocfilehash: 7aad054f0861522174faa01b979083a818c106af
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/03/2017
---
# <a name="help-users-with-the-troubleshooting-portal-in-microsoft-intune"></a>Microsoft Intune’daki Sorun Giderme portalıyla kullanıcılara yardımcı olun

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Sorun giderme portalı, yardım masası operatörlerinin ve Intune yöneticilerinin kullanıcı yardım isteklerini karşılamak için kullanıcı bilgilerini görüntülemesine izin verir. Kadrolarının bir parçası olarak yardım masası operatörleri olan kuruluşlar **Yardım masası operatörünü** bir grup kullanıcıya atayabilir ve operatör daha sonra kullanıcılara yardım etmek için Sorun Giderme dikey penceresini kullanabilir.

Örneğin, bir kullanıcı Intune ile ilgili teknik bir sorun için destekle bağlantı kurduğunda, yardım masası operatörü kullanıcının adını girer. Intune, şunlar dahil olmak üzere pek çok katman 1 sorununu çözmeye yardımcı veri sunar:
- Kullanıcı durumu
- Atamalar
- Uygulama yükleme hatası
- Uyumluluk sorunları
- Cihaz yanıt vermiyor
-   Cihaz VPN veya Wi-Fi ayarlarını alamıyor
-   Uygulama yükleme hatası


## <a name="add-help-desk-operators"></a>Yardım masası operatörleri ekleme
Bir Intune yöneticisi olarak bir kullanıcı grubuna Yardım Masası Operatörü rolü atayabilirsiniz. Bu grubun üyeleri, kullanıcı sorunlarını gidermek için yönetici portalını kullanabilir. Intune portalına erişmek için her yardım masası operatörünün bir Intune lisansı olması gerekir. [Intune kullanıcı lisanslarını atamayı](licenses-assign.md) öğrenin.

Yardım masası kullanıcıları eklemek için:
1. Gerekirse [Intune’a bir kullanıcı ekleyin](users-add.md)
2. [Bir yardım masası grubu oluşturun](groups-add.md) ve gruba kullanıcı ekleyin
3. [RBAC Yardım Masası Operatörü rolü atayın](role-based-access-control.md#built-in-roles) veya aşağıdaki izinlere sahip [özel bir rol oluşturun](role-based-access-control.md#custom-roles):
  - MobileApps: Okuma
  - ManagedApps: Okuma
  - ManagedDevices: Okuma
  - Organization: Okuma
  - DeviceCompliancePolices: Okuma
  - DeviceConfigurations: Okuma

  ![Intune rollerinin vurgulandığı ve Yardım Masası Operatörü dahil yerleşik rollerin bir listesini içeren Intune portalını gösteren ekran görüntüsü](./media/help-desk-user-add.png)

4. Yardım masası operatörlerine hizmet durumunu görüntüleme ve Intune için destek bileti açma izinleri vermek için bir **Hizmet yöneticisi** hesabıyla [kullanıcılara yönetici izinleri verin](https://docs.microsoft.com/azure/active-directory/active-directory-users-assign-role-azure-portal). **Intune Hizmet yöneticisi** iznini vermeyin çünkü bu dizin rolünde yardım masası operatörleri için gerekenden fazla hak vardır.

## <a name="access-the-troubleshooting-portal"></a>Sorun giderme portalına erişme

Yardım masası personeli ve Intune yöneticileri sorun giderme portalına iki yolla erişebilir:
- Bir web tarayıcısında [http://aka.ms/intunetroubleshooting](http://aka.ms/intunetroubleshooting) adresine gidin ve yalnızca sorun giderme portalını görüntüleyin.
  ![Sorun Giderme konsolu ekran görüntüsü](./media/help-desk-console.png)
- Azure portalında oturum açın, **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’a ve daha sonra **Yardım ve Destek** > **Sorun Giderme**’ye gidin.

**Kullanıcı seç**’e tıklayarak bir kullanıcıyı ve ayrıntılarını görüntüleyin.

![Kullanıcı Seç bağlantısı ile Intune Sorun Giderme iş yükü ekran görüntüsü](media/help-desk-user.png)

## <a name="use-the-troubleshooting-portal"></a>Sorun giderme portalını kullanma

Sorun giderme portalında, kullanıcıların bilgilerini görüntülemek için **Kullanıcı seç**’e tıklayın. Kullanıcı bilgileri, kullanıcıların ve cihazlarının geçerli durumunu anlamanıza yardımcı olabilir. Sorun giderme portalı aşağıdaki sorun giderme ayrıntılarını gösterir:
- **Hesap durumu**
- **Kullanıcı durumu**
- **Cihazlar** ile cihaz eylemleri
- **Grup üyeliği**
- **Uygulama koruma durumu**
