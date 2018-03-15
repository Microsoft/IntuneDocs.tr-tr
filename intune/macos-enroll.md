---
title: "macOS cihazların kaydını ayarlama"
titlesuffix: Microsoft Intune
description: "Intune’da macOS cihazların kaydının nasıl ayarlandığını öğrenin."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/30/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 77a1551321079765f00f0e35d57211ae4c99e5a6
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2018
---
# <a name="set-up-enrollment-for-macos-devices-in-intune"></a>Intune’da macOS cihazların kaydını ayarlama

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune, macOS cihazlarını yönetmenize olanak sağlar. Cihaz yönetimini etkinleştirmek için, kullanıcılarınızın [Şirket Portalı web sitesine](http://portal.manage.microsoft.com) gidip istemleri izleyerek cihazlarını kaydetmeleri gerekir. macOS cihazlarını yönetim altına aldıktan sonra [macOS cihazlar için özel ayarlar oluşturabilirsiniz](custom-settings-macos.md). Daha fazla özellik yakında kullanıma sunulacaktır.

## <a name="prerequisites"></a>Önkoşullar

macOS cihaz kaydını ayarlamadan önce, aşağıdaki önkoşulları tamamlayın:

- [Etki alanlarını yapılandırma](custom-domain-name-configure.md)
- [MDM Yetkilisini ayarlama](mdm-authority-set.md)
- [Grup oluşturma](https://docs.microsoft.com/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [Şirket Portalı’nı yapılandırma](company-portal-app.md)
- [Office 365 portalında](http://go.microsoft.com/fwlink/p/?LinkId=698854) kullanıcı lisanslarını atama
- [Bir MDM anında iletme sertifikası alma](apple-mdm-push-certificate-get.md)

## <a name="user-owned-ios-devices-byod"></a>Kullanıcıya ait iOS cihazları (KCG)

Kullanıcıların kendi cihazlarını Intune yönetimine kaydetmesine izin verebilirsiniz. Bu, “kendi cihazını getir” veya KCG olarak bilinir. Siz önkoşulları tamamlayıp kullanıcılara lisans atadıktan sonra kullanıcılar, App Store’dan macOS Şirket Portalı’nı indirip uygulamadaki kayıt yönergelerini izleyebilir.

## <a name="company-owned-ios-devices"></a>Şirkete ait iOS cihazlar
Kullanıcılarına cihaz satın alan kuruluşlar için Intune, şirkete ait olan MacOS cihazlarını bir [cihaz kayıt yöneticisi](device-enrollment-manager-enroll.md) hesabıyla kaydetmeyi destekler.

## <a name="set-up-macos-enrollment"></a>macOS kaydını ayarlama

Intune, macOS cihazlarının kaydına varsayılan olarak zaten izin verir.

macOS cihazlarının kaydedilmesini engellemek için bkz. [Cihaz türü kısıtlamaları ayarlama](enrollment-restrictions-set.md).

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Kullanıcılarınıza, şirket kaynaklarına erişmek için cihazlarını nasıl kaydedeceklerini anlatın

Son kullanıcılarınıza [Şirket Portalı web sitesine](http://portal.manage.microsoft.com) gitmelerini ve istemleri izleyerek cihazlarını kaydetmelerini bildirin. Kullanıcılara, çevrimiçi kaydolma adımlarını gösteren bir bağlantı da gönderebilirsiniz: [macOS cihazınızı Intune’a kaydetme](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos).

Diğer son kullanıcı görevleri hakkında daha fazla bilgi için şu makalelere bakın:

- [Microsoft Intune’da son kullanıcı deneyimi hakkında kaynaklar](end-user-educate.md)
- [macOS cihazınızı Intune ile kullanma](/intune-user-help/using-your-macos-device-with-intune)
