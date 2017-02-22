---
title: "Intune’da macOS cihazlarını kaydetme | Intune Azure önizlemesi | Microsoft Docs"
description: "Intune Azure önizlemesi: Intune Azure önizlemesinde macOS cihazlarını kaydetmeyi öğrenin."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 1/3/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ba2affcdbcdfcd690d671c7b20f9d1e14a74f764
ms.openlocfilehash: 171175689adca027181f3da4d05222117de97e13


---

# <a name="enroll-macos-devices-in-intune-azure-preview"></a>Intune Azure önizlemesinde macOS cihazlarını kaydetme

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Intune yöneticisi olarak, macOS cihazlarını yönetebilirsiniz. Varsayılan olarak, Azure Portal kullanıcıların macOS cihazlarını kaydetmesine izin verir. Yalnızca kullanıcılarınıza [Şirket Portalı web sitesine](http://portal.manage.microsoft.com) gitmelerini ve macOS cihazlarını kaydetmelerini söylemeniz yeterlidir. 

## <a name="prerequisites"></a>Önkoşullar

macOS cihaz kaydını ayarlamadan önce, aşağıdaki önkoşulları tamamlayın:

- [Etki alanlarını yapılandırma](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [MDM Yetkilisini ayarlama](set-mdm-authority.md)
- [Grup oluşturma](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [Şirket Portalı’nı yapılandırma](/intune-azure/manage-apps/company-portal-app.md)
- [Office 365 portalında](http://go.microsoft.com/fwlink/p/?LinkId=698854) kullanıcı lisanslarını atama
- [Bir MDM anında iletme sertifikası alma](get-an-apple-mdm-push-certificate.md)

## <a name="set-up-macos-enrollment"></a>macOS kaydını ayarlama

Varsayılan olarak, Intune zaten macOS cihazlarının kaydına izin verecek şekilde ayarlanmıştır. 

macOS cihazlarının kaydına izin verme veya bunu engelleme ayarını görmek için, Azure Portal’da Intune dikey penceresine gidin ve **Kayıt** > **Kayıt Kısıtlamaları**’nı seçin. 

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Kullanıcılarınıza, şirket kaynaklarına erişmek için cihazlarını nasıl kaydedeceklerini anlatın

Son kullanıcı kayıt yönergeleri için bkz. [macOS cihazınızı Intune'a kaydetme](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-macos). Kayıt işlemi kullanıcıları neler bekleyebilecekleri ve BT yöneticilerinin görebileceği ve göremeyeceği cihaz içeriği hakkında bilgilendirir.

Diğer son kullanıcı görevleri hakkında daha fazla bilgi için şu makalelere bakın:

- [Microsoft Intune’da son kullanıcı deneyimi hakkında kaynaklar](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune)
- [iOS veya Mac OS cihazınızı Intune ile kullanma](https://docs.microsoft.com/intune/enduser/using-your-ios-or-mac-os-x-device-with-intune)


<!--HONumber=Feb17_HO1-->


