---
title: "Intune’da macOS cihazları kaydetme"
titlesuffix: Azure portal
description: "Intune’da macOS cihazları kaydetmeyi öğrenin.\""
keywords: 
author: arob98
ms.author: angrobe
nmanager: angrobe
ms.date: 10/30/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a18aa5091c8be2095e2ac95717c2b8294b845cd5
ms.sourcegitcommit: 623c52116bc3fdd12680b9686dcd0e1eeb6ea5ed
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="enroll-macos-devices-in-intune"></a>Intune’da macOS cihazları kaydetme

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

## <a name="set-up-macos-enrollment"></a>macOS kaydını ayarlama

Intune, macOS cihazlarının kaydına varsayılan olarak zaten izin verir.

macOS cihazlarının kaydedilmesini engellemek için bkz. [Cihaz türü kısıtlamaları ayarlama](enrollment-restrictions-set.md).

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Kullanıcılarınıza, şirket kaynaklarına erişmek için cihazlarını nasıl kaydedeceklerini anlatın

Son kullanıcılarınıza [Şirket Portalı web sitesine](http://portal.manage.microsoft.com) gitmelerini ve istemleri izleyerek cihazlarını kaydetmelerini bildirmeniz gerekir. Kullanıcılara, çevrimiçi kaydolma adımlarını gösteren bir bağlantı da gönderebilirsiniz: [macOS cihazınızı Intune’a kaydetme](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos).

Diğer son kullanıcı görevleri hakkında daha fazla bilgi için şu makalelere bakın:

- [Microsoft Intune’da son kullanıcı deneyimi hakkında kaynaklar](end-user-educate.md)
- [iOS veya Mac OS cihazınızı Intune ile kullanma](https://docs.microsoft.com/intune-user-help/using-your-ios-or-mac-os-x-device-with-intune)
