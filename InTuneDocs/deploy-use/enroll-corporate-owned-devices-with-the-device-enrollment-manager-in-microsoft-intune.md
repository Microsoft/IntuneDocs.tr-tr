---
title: "Cihaz kayıt yöneticisine kaydolma | Microsoft Docs"
description: "Cihaz kayıt yöneticisi (DEM) hesabı, paylaşılan, şirkete ait çok sayıda mobil cihazı tek bir kullanıcı hesabı ile yönetebilir."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 01/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a23abc61-69ed-44f1-9b71-b86aefc6ba03
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 8b2bd3ecba0b597bc742ea08872ffe8fc58155cf
ms.openlocfilehash: ea57a51f2855dea416ad4a76e657e1846ffe41f1
ms.lasthandoff: 04/24/2017


---


# <a name="enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune"></a>Şirkete ait cihazları Microsoft Intune'daki cihaz kayıt yöneticisi ile kaydetme

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Kuruluşlar, çok sayıda mobil cihazı tek bir kullanıcı hesabıyla yönetmek için Intune'u kullanabilir. *Cihaz kayıt yöneticisi* (DEM) hesabı, 1.000’e kadar cihazı kaydedebilen özel bir kullanıcı hesabıdır. Varolan kullanıcılara özel DEM yetenekleri vermek için kullanıcıları DEM hesabına ekleyin. Kaydedilen her cihaz tek bir lisans kullanır. Bu hesap aracılığıyla kaydedilen cihazları, kişisel ("KCG") cihazlar olarak değil paylaşılan cihazlar (kullanıcı benzeşimi olmayan) olarak kullanmanızı öneririz.  

Kullanıcıların, cihaz kayıt yöneticileri olarak eklenmesi için Azure portalında mevcut olmaları gerekir. En iyi güvenlik için DEM kullanıcısının Intune yöneticisi olmaması gerekir.

>[!NOTE]
>DEM kayıt yöntemi, [Apple Configurator Kurulum Yardımcısı](ios-setup-assistant-enrollment-in-microsoft-intune.md) veya [doğrudan kayıt](ios-direct-enrollment-in-microsoft-intune.md) ya da [DEP kayıt yöntemi](ios-device-enrollment-program-in-microsoft-intune.md) ile birlikte kullanılamaz.

## <a name="example-of-a-device-enrollment-manager-scenario"></a>Cihaz kayıt yöneticisi senaryo örneği

Bir restoran, garsonlar için 50 satış noktası tableti, mutfak çalışanları içinse sipariş izleyici istiyor. Çalışanların hiçbir zaman şirket verilerine erişmesi veya kullanıcı olarak oturum açması gerekmiyor. Intune yöneticisi, cihaz kayıt yöneticisi hesabı oluşturur ve DEM yetenekleri vermek için restoran yöneticisini DEM hesabına ekler. Yönetici, artık DEM kimlik bilgilerini kullanarak 50 tableti kaydedebilir.

Yalnızca Intune konsolundaki kullanıcılar cihaz kayıt yöneticileri olabilir. Cihaz kayıt yöneticisi bir Intune yöneticisi olamaz.

DEM kullanıcısı şunları yapabilir:

-   1000’e kadar cihazı Intune'a kaydeder
-   Şirket uygulamalarını almak için Şirket Portalı’nı kullanır
-   Role özgü uygulamaları tabletlere dağıtarak şirket verilerine erişimi yapılandırır

## <a name="limitations-of-devices-that-are-enrolled-with-a-dem-account"></a>Bir DEM hesabıyla kaydedilen cihazların kısıtlamaları

Bir cihaz kayıt yöneticisi hesabıyla kaydedilen cihazlarda aşağıdaki kısıtlamalar söz konusudur:

  - Özel bir cihaz "kullanıcısı" yoktur. Bu yüzden e-posta veya şirket verileri erişimi yoktur. Ancak örneğin VPN, verilere erişimi olan cihaz uygulamaları sağlamak için kullanılabilir.

  - Koşullu erişim yoktur çünkü bunlar kullanıcı başına senaryolardır.

  - DEM kullanıcısı, Şirket Portalı’nı kullanarak cihazın kendisinde DEM’e kaydedilen cihazların kaydını kaldıramaz. Intune yöneticisinin bu yeteneği vardır ancak DEM kullanıcısının yoktur.

  - Şirket Portalı uygulamasında veya web sitesinde yalnızca yerel cihaz görünür.

  - Kullanıcılar, uygulama yönetimi için kullanıcı başına Apple ID gereksinimlerinden dolayı Apple Volume Purchase Program (VPP) uygulamalarını kullanamaz.

  - (Yalnızca iOS) iOS cihazlarını kaydetmek için DEM kullanırsanız cihazları kaydetmek için Apple Configurator veya Apple Aygıt Kayıt Programı’nı (DEP) kullanamazsınız.

> [!NOTE]
> Cihaz kayıt yöneticisiyle yönetilen cihazlara şirket uygulaması dağıtmak için Şirket Portalı uygulamasını cihaz kayıt yöneticisinin kullanıcı hesabına **Gerekli Yükleme** olarak dağıtın.
> Performansı geliştirmek amacıyla, DEM cihazında Şirket Portalı uygulaması görüntülendiğinde yalnızca yerel cihaz gösterilir. Diğer DEM cihazlarının uzaktan yönetimi, yalnızca Intune yönetici konsolundan gerçekleştirilebilir.


## <a name="add-a-device-enrollment-manager"></a>Cihaz kayıt yöneticisi ekleme

1.  DEM hesabına eklemek istediğiniz kullanıcının zaten mevcut olduğundan emin olun. Kullanıcıyı eklemeniz gerekiyorsa [Office 365 portalı](https://go.microsoft.com/fwlink/p/?LinkId=698854)’nda oturum açın ve [Kullanıcıları Office 365 portalına tek tek veya toplu halde ekleme](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec) bölümündeki adımları takip edin.

2.  [Microsoft Intune yönetim konsolu](https://manage.microsoft.com)’nda yönetici kimlik bilgilerinizle oturum açın.

3.  Gezinti bölmesinde, **Yönetici**'yi seçin, **Yönetici Yönetimi**'ne gidin ve **Cihaz Kayıt Yöneticisi**'ni seçin. **Cihaz Kayıt Yöneticileri** sayfası açılır.

4.  **Ekle...**’yi seçin. **Cihaz Kayıt Yöneticisi Ekle** iletişim kutusu açılır.

5.  Intune hesabının **Kullanıcı Kimliği**'ni girin ve ardından **Tamam**'ı seçin.

    DEM kullanıcısı artık, bir son kullanıcının KCG senaryosu için Şirket Portalı’nda kullandığı yordamı kullanarak mobil cihazları kaydedebilir. Yönetici son kullanıcı, Şirket Portalı uygulamasını yükleyip, kendi DEM kimlik bilgilerini en fazla 1000 cihaz üzerinde kullanarak cihazı kaydedebilir. Her bir platformda son kullanıcı kayıt adımları için bkz.

  - [iOS cihazınızı Intune'a kaydetme](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-ios)
  - [macOS cihazınızı Intune'a kaydetme](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-macos)
  - [Android cihazınızı Intune’a kaydetme](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-android)
  - [Windows cihazınızı Intune'a kaydetme](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-windows)

## <a name="delete-a-device-enrollment-manager-from-intune"></a>Delete a device enrollment manager from Intune

1.  [Microsoft Intune yönetici portalında](https://manage.microsoft.com) yönetici kimlik bilgilerinizle oturum açın.

2.  Gezinti bölmesinde, **Yönetici**'yi seçin, **Yönetici Yönetimi**'ne gidin ve **Cihaz Kayıt Yöneticisi**'ni seçin. **Cihaz Kayıt Yöneticileri** sayfası açılır.

3.  Silmek istediğiniz cihaz kayıt yöneticisi **Kullanıcı** 'yı silin ve ardından **Sil**'i seçin. Bu kullanıcı Intune'dan silinmez ve bu kullanıcının yönettiği cihazlar Intune'da kayıtlı kalır. Bir cihaz kayıt yöneticisini silme, bu kullanıcının Intune'a daha fazla cihaz kaydetmesini engeller.

4.  Cihaz kayıt yöneticisini silmek istediğinizi doğrulamak için **Evet**’i seçin.

Bir cihaz kayıt yöneticisinin silinmesi, kaydedilen cihazları etkilemez. Bir cihaz kayıt yöneticisi silindiğinde:

-   Kaydedilen hiçbir cihaz bundan etkilenmez.

-   Kaydedilen cihazlar tam olarak yönetilmeye devam eder.

-   Silinen cihaz kayıt yöneticisinin hesap kimlik bilgileri, Şirket Portalı’nda oturum açıp uygulamalara erişmek için geçerliliğini korur.

-   Silinen cihaz kayıt yöneticisi hesabının kimlik bilgileri yine de cihazları temizleyemez ve kullanımdan kaldıramaz.

-   Silinen cihaz kayıt yöneticisi hesabının kayıtlı cihazlar ile ilişkisi devam eder, ancak başka bir cihaz kaydedilemez.

