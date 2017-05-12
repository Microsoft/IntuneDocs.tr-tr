---
title: "Intune’da macOS cihazları kaydetme"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Intune Azure önizlemesinde macOS cihazlarını kaydetmeyi öğrenin."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 3758df744311392528be01c826527c2a9d879975
ms.openlocfilehash: 6fcbeb30fb11b6bc8def3a1c245bff56b3f7cca4
ms.contentlocale: tr-tr
ms.lasthandoff: 05/10/2017


---

# <a name="enroll-macos-devices-in-intune-azure-preview"></a>Intune Azure önizlemesinde macOS cihazlarını kaydetme

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Intune, macOS cihazlarını yönetmenize olanak sağlar. Cihaz yönetimini etkinleştirmek için, kullanıcılarınızın [Şirket Portalı web sitesine](http://portal.manage.microsoft.com) gidip istemleri izleyerek cihazlarını kaydetmeleri gerekir. macOS cihazlarını yönetim altına aldıktan sonra [macOS cihazlar için özel ayarlar oluşturabilirsiniz](../configure-devices/custom-for-macos.md). Daha fazla özellik yakında kullanıma sunulacaktır.

## <a name="prerequisites"></a>Önkoşullar

macOS cihaz kaydını ayarlamadan önce, aşağıdaki önkoşulları tamamlayın:

- [Etki alanlarını yapılandırma](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [MDM Yetkilisini ayarlama](set-mdm-authority.md)
- [Grup oluşturma](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [Şirket Portalı’nı yapılandırma](../manage-apps/company-portal-app.md)
- [Office 365 portalında](http://go.microsoft.com/fwlink/p/?LinkId=698854) kullanıcı lisanslarını atama
- [Bir MDM anında iletme sertifikası alma](get-an-apple-mdm-push-certificate.md)

## <a name="set-up-macos-enrollment"></a>macOS kaydını ayarlama

Intune, macOS cihazlarının kaydına varsayılan olarak zaten izin verir.

macOS cihazlarının kaydedilmesini engellemek için bkz. [Cihaz türü kısıtlamaları ayarlama](set-enrollment-restrictions.md#set-device-type-restrictions).

Bir kullanıcının kaydedebileceği en fazla cihaz sayısını ayarlamak için bkz. [Cihaz sınırı kısıtlamaları ayarlama](set-enrollment-restrictions.md#set-device-limit-restrictions).

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Kullanıcılarınıza, şirket kaynaklarına erişmek için cihazlarını nasıl kaydedeceklerini anlatın

Son kullanıcılarınıza [Şirket Portalı web sitesine](http://portal.manage.microsoft.com) gitmelerini ve istemleri izleyerek cihazlarını kaydetmelerini bildirmeniz gerekir. Kullanıcılara, çevrimiçi kaydolma adımlarını gösteren bir bağlantı da gönderebilirsiniz: [macOS cihazınızı Intune’a kaydetme](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-macos).

Diğer son kullanıcı görevleri hakkında daha fazla bilgi için şu makalelere bakın:

- [Microsoft Intune’da son kullanıcı deneyimi hakkında kaynaklar](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune)
- [iOS veya Mac OS cihazınızı Intune ile kullanma](https://docs.microsoft.com/intune/enduser/using-your-ios-or-mac-os-x-device-with-intune)

