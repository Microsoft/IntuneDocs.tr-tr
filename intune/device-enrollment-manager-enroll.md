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
ms.openlocfilehash: 0a32eb1d65710bf09d61c0846a8d949d5cd99ed2
ms.sourcegitcommit: 91802e78cd5014d20a828ca25a54a381d452f0f8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/16/2018
ms.locfileid: "34216335"
---
# <a name="enroll-devices-by-using-a-device-enrollment-manager-account"></a>Cihaz kayıt yöneticisi hesabı kullanarak cihazları kaydetme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Kuruluşlar, çok sayıda mobil cihazı tek bir kullanıcı hesabıyla yönetmek için Intune'u kullanabilir. *Cihaz kayıt yöneticisi* (DEM) hesabı, 1.000’e kadar cihazı kaydedebilen özel bir kullanıcı hesabıdır. Varolan kullanıcılara özel DEM yetenekleri vermek için kullanıcıları DEM hesabına ekleyin. Kaydedilen her cihaz tek bir lisans kullanır. Bu hesap aracılığıyla kaydedilen cihazları, kişisel ("KCG") cihazlar olarak değil paylaşılan cihazlar olarak kullanmanızı öneririz.  

Kullanıcıların, cihaz kayıt yöneticileri olarak eklenmesi için [Azure portalında](https://portal.azure.com) mevcut olmaları gerekir. En iyi güvenlik için DEM kullanıcısının Intune yöneticisi olmaması gerekir.

>[!NOTE]
>DEM kayıt yöntemi şu kayıt yöntemleriyle birlikte kullanılamaz: [Kurulum Yardımcısı ile Apple Configurator](apple-configurator-setup-assistant-enroll-ios.md), [doğrudan kayıt ile Apple Configurator](apple-configurator-direct-enroll-ios.md), [Apple School Manager (ASM)](apple-school-manager-set-up-ios.md) veya [Cihaz Kayıt Programı (DEP)](device-enrollment-program-enroll-ios.md).

## <a name="example-of-a-device-enrollment-manager-scenario"></a>Cihaz kayıt yöneticisi senaryo örneği

Bir restoran, garsonlar için 50 satış noktası tableti, mutfak çalışanları içinse sipariş izleyici istiyor. Çalışanların hiçbir zaman şirket verilerine erişmesi veya kullanıcı olarak oturum açması gerekmiyor. Intune yöneticisi, cihaz kayıt yöneticisi hesabı oluşturur ve bir restoran yöneticisini DEM hesabına ekler. Yönetici artık DEM yeteneklerine sahiptir. Yönetici, artık DEM kimlik bilgilerini kullanarak 50 tableti kaydedebilir.

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
  - (Yalnızca iOS) iOS cihazlarını kaydetmek için DEM kullanıyorsanız, cihaz kaydetmek için Apple Configurator, Apple Aygıt Kayıt Programı (DEP) veya Apple School Manager (ASM) kullanamazsınız.
  - (Yalnızca Android) Tek bir DEM hesabıyla kaydedilebilen Android for Work cihaz sayısı sınırlıdır. DEM hesabı başına en fazla 10 Android iş profili cihazı kaydedilebilir. Bu sınırlama eski Android kayıtları için geçerli değildir.
  - Cihazlar, cihaz lisansına sahipse VPP uygulamalarını yükleyebilir.
  - Her cihaz bir cihaz lisansı gerektirir. [Kullanıcı ve cihaz lisansları](licenses-assign.md#how-user-and-device-licenses-affect-access-to-services) hakkında daha fazla bilgi edinin.


> [!NOTE]
> Şirket uygulamalarını, cihaz kayıt yöneticisi tarafından yönetilen cihazlara dağıtabilirsiniz. Şirket Portalı uygulamasını **Gerekli Yükleme** olarak cihaz kayıt yöneticisinin kullanıcı hesabına dağıtın.
> Performansı geliştirmek amacıyla, DEM cihazında Şirket Portalı uygulaması görüntülendiğinde yalnızca yerel cihaz gösterilir. Diğer DEM cihazlarının uzaktan yönetimi, yalnızca Intune yönetici konsolundan gerçekleştirilebilir.


## <a name="add-a-device-enrollment-manager"></a>Cihaz kayıt yöneticisi ekleme

1.  [Azure portalında Intune](https://aka.ms/intuneportal)’da, **Cihaz kaydı** > **Cihaz kayıt yöneticileri**’ni seçin.

2.  **Ekle**’yi seçin.

3.  **Kullanıcı Ekle** dikey penceresinde, DEM kullanıcısı için bir kullanıcı asıl adı girin ve **Ekle**’yi seçin. DEM kullanıcısı, DEM kullanıcıları listesine eklenir.

## <a name="permissions-for-dem"></a>DEM izinleri

Genel veya Intune Hizmet Yöneticisi Azure AD rollerinin Yönetici Portalında DEM kaydıyla ilgili görevleri gerçekleştirmesi gerekir. Ayrıca özel Kullanıcı rolü altında RBAC izinlerinin de listelenmesine karşın, tüm DEM kullanıcılarını görmek için de bu roller gereklidir. Genel Yönetici veya Intune Hizmet Yöneticisi rolü atanmamış ancak Cihaz Kayıt Yöneticileri rolü için okuma izinlerine sahip bir kullanıcı yalnızca kendi oluşturduğu DEM kullanıcılarını görebilir. Bu özellikler için RBAC rolü desteği gelecekte duyurulacaktır.

Kullanıcıya Genel Yönetici veya Intune Hizmet Yöneticisi rolü atanmadıysa ancak Cihaz Kayıt Yöneticileri rolü için okuma izinleri etkinleştirildiyse yalnızca kendi oluşturduğu DEM kullanıcılarını görebilir.

## <a name="remove-a-device-enrollment-manager"></a>Cihaz kayıt yöneticisini kaldırma

Cihaz kayıt yöneticisinin kaldırılması, kayıtlı cihazları etkilemez. Cihaz kayıt yöneticisi kaldırıldığında:

-   Kayıtlı cihazlar bunlardan etkilenmez ve tam olarak yönetilmeye devam eder.
-   Kaldırılan cihaz kayıt yöneticisi hesabının kimlik bilgileri geçerli olmaya devam eder.
-   Kaldırılan cihaz kayıt yöneticisi yine cihazları temizleyemez ve kullanımdan kaldıramaz.
-   Kaldırılan cihaz kayıt yöneticisi, yalnızca Intune yöneticisinin yapılandırdığı kullanıcı başına cihaz sayısı sınırına kadar cihaz kaydedebilir.

**Cihaz kayıt yöneticisi kaldırmak için**

1. [Azure portalında Intune](https://aka.ms/intuneportal)’da **Cihaz kaydı**’nı ve ardından **Cihaz kayıt yöneticileri**’ni seçin.
2. **Cihaz kayıt yöneticileri** dikey penceresinde DEM kullanıcısını ve **Sil**’i seçin.

## <a name="view-the-properties-of-a-device-enrollment-manager"></a>Cihaz kayıt yöneticisinin özelliklerini görüntüleme

1. [Azure portalında](https://portal.azure.com) **Cihaz kaydı**’nı ve ardından **Cihaz kayıt yöneticileri**’ni seçin.
2. **Cihaz kayıt yöneticileri** dikey penceresinde DEM kullanıcısına sağ tıklayın ve **Özellikler**’i seçin.
