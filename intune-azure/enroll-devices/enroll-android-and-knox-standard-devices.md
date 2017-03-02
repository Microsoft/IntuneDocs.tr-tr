---
title: "Intune’da Android cihazlarını kaydetme | Intune Azure önizlemesi | Microsoft Docs"
description: "Intune Azure önizlemesi: Intune Azure önizlemesinde Android cihazlarını kaydetmeyi öğrenin."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 08dad848a48adad7d9c6f0b5b3286f6550a266bd
ms.openlocfilehash: 99b790e33843efcf83a4687490b186a6e174bd81
ms.lasthandoff: 02/15/2017


---

# <a name="enroll-android-devices"></a>Android cihazlarını kaydetme

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Intune, Samsung Knox Standard cihazları dahil olmak üzere Android cihazlarını yönetmenize olanak tanır. Cihaz yönetimini etkinleştirmek için, kullanıcılarınızın Google Play'de bulunan Intune Şirket Portalı uygulamasını indirmeleri ve ardından uygulamayı açıp kaydolmaya yönelik istemleri izleyerek cihazlarını kaydetmeleri gerekir. Android cihazlarını yönetim altına aldıktan sonra [uyumluluk ilkeleri oluşturabilir](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-android), [uygulamaları yönetebilir](https://docs.microsoft.com/intune-azure/manage-apps/what-is-app-management)ve daha fazlasını yapabilirsiniz.

## <a name="prerequisite"></a>Önkoşul

Mobil cihazların yönetimine hazırlık olarak, **Microsoft Intune**’a MDM yetkilisi ayarlamanız gerekir. Yönergeler için bkz. [MDM yetkilisini ayarlama](set-mdm-authority.md). Intune’u mobil cihaz yönetimi için ilk kez ayarladığınız sırada bu öğeyi tek bir kez ayarlarsınız; dolayısıyla zaten ayarlamış olabilirsiniz. 

## <a name="set-up-android-enrollment"></a>Android kaydını ayarlama

Intune, Android ve Samsung Knox Standard cihazlarının kaydına varsayılan olarak zaten izin verir. 

Android cihazların veya yalnızca kişisel Android cihazların kaydedilmesini engellemek için bkz. [Cihaz türü kısıtlamaları ayarlama](https://docs.microsoft.com/intune-azure/enroll-devices/set-enrollment-restrictions#set-device-type-restrictions). 

Bir kullanıcının kaydedebileceği en fazla cihaz sayısını ayarlamak için bkz. [Cihaz sınırı kısıtlamaları ayarlama](https://docs.microsoft.com/intune-azure/enroll-devices/set-enrollment-restrictions#set-device-limit-restrictions).

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Kullanıcılarınıza, şirket kaynaklarına erişmek için cihazlarını nasıl kaydedeceklerini anlatın

Son kullanıcılarınıza, Google Play’e gidip Intune Şirket Portalı uygulamasını indirmelerini ve ardından uygulamayı açıp istemleri izleyerek cihazlarını kaydetmelerini bildirmeniz gerekir. Uygulama, kullanıcılara kayıt süreci boyunca yol gösterir, kullanıcıların neler bekleyebileceklerini ve BT yöneticilerinin cihazlarında neler görüp göremeyeceklerini açıklar.

Kullanıcılara, çevrimiçi kaydolma adımlarını gösteren bir bağlantı da gönderebilirsiniz: [Android cihazınızı Intune’a kaydetme](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-android). 

Diğer son kullanıcı görevleri hakkında daha fazla bilgi için şu makalelere bakın:

- [Microsoft Intune’da son kullanıcı deneyimi hakkında kaynaklar](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune)
- [Android cihazınızı Intune ile kullanma](https://docs.microsoft.com/intune/enduser/using-your-android-device-with-intune)
