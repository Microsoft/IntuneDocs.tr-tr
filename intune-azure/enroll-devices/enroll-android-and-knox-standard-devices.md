---
title: "Intune’da Android cihazlarını kaydetme | Intune Azure önizlemesi | Microsoft Docs"
description: "Intune Azure önizlemesi: Intune Azure önizlemesinde Android cihazlarını kaydetmeyi öğrenin."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 12/16/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: edd6303f3bb05dfff758cbb7d4bd08e21f083998


---

# <a name="enroll-android-devices"></a>Android cihazlarını kaydetme

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Bir Intune yöneticisi olarak Samsung Knox Standard cihazlar da dahil olmak üzere Android cihazlarının yönetimini Şirket Portalı’ndan etkinleştirebilirsiniz. Kullanıcılar, cihazlarını Google Play’den edinilebilecek Şirket Portalı uygulamasını kullanarak kaydedebilir.

## <a name="prerequisite"></a>Önkoşul

Mobil cihazların yönetimine hazırlık olarak, **Microsoft Intune**’a MDM yetkilisi ayarlamanız gerekir. Yönergeler için bkz. [MDM yetkilisini ayarlama](set-mdm-authority.md). Intune’u mobil cihaz yönetimi için ilk kez ayarladığınız sırada bu öğeyi tek bir kez ayarlarsınız; dolayısıyla zaten ayarlamış olabilirsiniz. 

## <a name="set-up-android-enrollment"></a>Android kaydını ayarlama

Varsayılan olarak Intune, Android ve Samsung Knox Standard cihazlarının kaydına izin verecek şekilde ayarlanır. 

Android cihazlarının kaydına izin verme veya bunu engelleme ayarını görmek için, Azure Portal’da Intune dikey penceresine gidin ve **Kayıt** > **Kayıt Kısıtlamaları**’nı seçin. 

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Kullanıcılarınıza, şirket kaynaklarına erişmek için cihazlarını nasıl kaydedeceklerini anlatın

Son kullanıcı kayıt talimatları için bkz. [Android cihazınızı Intune'a kaydetme](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-android). Kayıt işlemi kullanıcıları neler bekleyebilecekleri ve BT yöneticilerinin görebileceği ve göremeyeceği cihaz içeriği hakkında bilgilendirir.

Diğer son kullanıcı görevleri hakkında daha fazla bilgi için şu makalelere bakın:

- [Microsoft Intune’da son kullanıcı deneyimi hakkında kaynaklar](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune)
- [Android cihazınızı Intune ile kullanma](https://docs.microsoft.com/intune/enduser/using-your-android-device-with-intune)


<!--HONumber=Feb17_HO1-->


