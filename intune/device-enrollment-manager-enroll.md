---
title: Cihaz kayıt yöneticisi hesabı kullanarak cihazları kaydetme
titlesuffix: Microsoft Intune
description: Intune'a cihaz kaydetmek için cihaz kayıt yöneticisi hesabını kullanın. "
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 7196b33e-d303-4415-ad0b-2ecdb14230fd
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8e0d8d6aba74a37d1c07fa8445aa98adf5943be2
ms.sourcegitcommit: 8fdddb684ecf5eabf071907168413bcd89a2f702
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44141618"
---
# <a name="enroll-devices-by-using-a-device-enrollment-manager-account"></a>Cihaz kayıt yöneticisi hesabı kullanarak cihazları kaydetme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Kuruluşlar, çok sayıda mobil cihazı tek bir kullanıcı hesabıyla yönetmek için Intune'u kullanabilir. *Cihaz kayıt yöneticisi* (DEM) hesabı, 1.000’e kadar cihazı kaydedebilen özel bir kullanıcı hesabıdır. Varolan kullanıcılara özel DEM seçenekleri vermek için kullanıcıları DEM hesabına ekleyin. Kaydedilen her cihaz tek bir lisans kullanır. Bu hesap aracılığıyla kaydedilen cihazları, kişisel ("KCG") cihazlar olarak değil paylaşılan cihazlar olarak kullanmanızı öneririz.  

Kullanıcıların, cihaz kayıt yöneticileri olarak eklenmesi için [Azure portalında](https://portal.azure.com) mevcut olmaları gerekir. En iyi güvenlik için DEM kullanıcısının Intune yöneticisi olmaması gerekir.

>[!NOTE]
>DEM kayıt yöntemi şu kayıt yöntemleriyle birlikte kullanılamaz: [Kurulum Yardımcısı ile Apple Configurator](apple-configurator-setup-assistant-enroll-ios.md), [doğrudan kayıt ile Apple Configurator](apple-configurator-direct-enroll-ios.md), [Apple School Manager (ASM)](apple-school-manager-set-up-ios.md) veya [Cihaz Kayıt Programı (DEP)](device-enrollment-program-enroll-ios.md).

## <a name="example-of-a-device-enrollment-manager-scenario"></a>Cihaz kayıt yöneticisi senaryo örneği

Bir restoran, garsonlar için 50 satış noktası tableti, mutfak çalışanları içinse sipariş izleyici istiyor. Çalışanların hiçbir zaman şirket verilerine erişmesi veya kullanıcı olarak oturum açması gerekmiyor. Intune yöneticisi, bir restoran yöneticisi için yeni cihaz kayıt yöneticisi hesabı oluşturur.  Bu hesap, yöneticinin birincil hesabından ayrıdır ve yalnızca paylaşılan cihazları Intune’a kaydetmek için kullanılır. Yönetici, artık DEM kimlik bilgilerini kullanarak 50 tableti kaydedebilir.

Yalnızca [Azure portalındaki](https://portal.azure.com) kullanıcılar cihaz kayıt yöneticileri olabilir. Cihaz kayıt yöneticisi bir Intune yöneticisi olamaz.

DEM kullanıcısı şunları yapabilir:

-   1000’e kadar cihazı Intune'a kaydeder
-   Şirket uygulamalarını almak için Şirket Portalı’nda oturum açın
-   Role özgü uygulamaları tabletlere dağıtarak şirket verilerine erişimi yapılandırır

## <a name="limitations-of-devices-that-are-enrolled-with-a-dem-account"></a>Bir DEM hesabıyla kaydedilen cihazların kısıtlamaları

Bir cihaz kayıt yöneticisi hesabıyla kaydedilen cihazlarda aşağıdaki kısıtlamalar söz konusudur:

  - Kullanıcı başına erişim yoktur. Cihazların atanmış bir kullanıcısı olmadığından, cihaz e-postaya veya şirket verilerine erişemez. Örneğin cihaz uygulamalarına verilere erişim sağlamak için VPN yapılandırmaları kullanmaya devam edilebilir.
  - DEM kullanıcısı, Şirket Portalı’nı kullanarak cihazın kendisinde DEM’e kaydedilen cihazların kaydını kaldıramaz. Intune yöneticisi kayıt silme işlemi gerçekleştirebilir.
  - Şirket Portalı uygulamasında veya web sitesinde yalnızca yerel cihaz görünür.
  - Kullanıcılar, uygulama yönetimi için kullanıcı başına Apple Kimliği gereksinimlerinden dolayı kullanıcı lisanslarıyla Apple Volume Purchase Program (VPP) uygulamalarını kullanamaz.
  - (Yalnızca iOS) iOS cihazlarını kaydetmek için DEM kullanıyorsanız, cihaz kaydetmek için Apple Configurator, Apple Aygıt Kayıt Programı (DEP) veya Apple School Manager (ASM) kullanamazsınız. Yani cihazı denetimli moda alamazsınız, bu sebeple de bazı yapılandırma seçeneklerine erişemezsiniz.
  - (Yalnızca Android) Tek bir DEM hesabıyla kaydedilebilen Android iş profili cihaz sayısı sınırlıdır. DEM hesabı başına en fazla 10 Android iş profili cihazı kaydedilebilir. Bu sınırlama eski Android kayıtları için geçerli değildir.
  - Cihazlar, cihaz lisansına sahipse VPP uygulamalarını yükleyebilir.
  - DEM kullanmak için bir Intune cihaz lisansı gerekli değildir. [Kullanıcı ve cihaz lisansları](licenses-assign.md#how-user-and-device-licenses-affect-access-to-services) hakkında daha fazla bilgi edinin.


> [!NOTE]
> Şirket uygulamalarını, cihaz kayıt yöneticisi tarafından yönetilen cihazlara dağıtabilirsiniz. Şirket Portalı uygulamasını **Gerekli Yükleme** olarak cihaz kayıt yöneticisinin kullanıcı hesabına dağıtın.
> Performansı geliştirmek amacıyla, DEM cihazında Şirket Portalı uygulaması görüntülendiğinde yalnızca yerel cihaz gösterilir. Diğer DEM cihazlarının uzaktan yönetimi, yalnızca Intune yönetici konsolundan gerçekleştirilebilir.


## <a name="add-a-device-enrollment-manager"></a>Cihaz kayıt yöneticisi ekleme

1.  [Azure portalında Intune](https://aka.ms/intuneportal)’da, **Cihaz kaydı** > **Cihaz kayıt yöneticileri**’ni seçin.

2.  **Ekle**’yi seçin.

3.  **Kullanıcı Ekle** dikey penceresinde, DEM kullanıcısı için bir kullanıcı asıl adı girin ve **Ekle**’yi seçin. DEM kullanıcısı, DEM kullanıcıları listesine eklenir.

## <a name="permissions-for-dem"></a>DEM izinleri

Yönetici Portalında DEM kaydıyla ilgili görevleri tamamlamak için,
- Genel Yönetici veya Intune Hizmet Yöneticisi Azure AD rolleri gerekir
- Özel Kullanıcı rolü altında RBAC izinlerinin de listelenmesine karşın, tüm DEM kullanıcılarına bakın.

Genel Yönetici veya Intune Hizmet Yöneticisi rolü atanmamış ancak Cihaz Kayıt Yöneticileri rolü için okuma izinlerine sahip bir kullanıcı yalnızca kendi oluşturduğu DEM kullanıcılarını görebilir. Bu özellikler için RBAC rolü desteği gelecekte duyurulacaktır.


## <a name="remove-a-device-enrollment-manager"></a>Cihaz kayıt yöneticisini kaldırma

Cihaz kayıt yöneticisi kaldırıldığında:

-   Kayıtlı cihazlar bunlardan etkilenmez ve tam olarak yönetilmeye devam eder.
-   Kaldırılan DEM hesabı kimlik bilgileri hala geçerlidir.
-   Kaldırılan DEM cihazları temizleyemez veya kullanım dışı bırakamaz.
-   Kaldırılan DEM, yalnızca Intune yöneticisinin yapılandırdığı kullanıcı başına cihaz sayısı sınırına kadar cihaz kaydedebilir.

**Cihaz kayıt yöneticisi kaldırmak için**

1. [Azure portalında Intune](https://aka.ms/intuneportal)’da **Cihaz kaydı**’nı ve ardından **Cihaz kayıt yöneticileri**’ni seçin.
2. **Cihaz kayıt yöneticileri** dikey penceresinde DEM kullanıcısını ve **Sil**’i seçin.

