---
title: GCC High ve DoD ortamları için uygulamalar
titleSuffix: Microsoft Intune
description: Microsoft Intune kullanarak GCC High ve DoD ortamlarını içeren uygulamalar hakkında bilgi edinin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/02/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 29329f86-1aa5-434f-9925-8dc28bf35348
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8a6c430ab15c40166e8c3afbccd6fcc7c2c5976d
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72507260"
---
# <a name="deploying-apps-using-intune-on-the-gcc-high-and-dod-environments"></a>GCC High ve DoD ortamlarında Intune kullanarak uygulama dağıtma 

Microsoft Intune, kiracı yöneticileri tarafından iş gücünün uygulamalarına dağıtılması için kullanılabilir. İş gücü, uygulamaların kullanıcıları olan şirket çalışandır. GCC High veya DoD ortamlarında Intune 'dan dağıtılabilecek birçok tür uygulama vardır. Yöneticinin özel olarak oluşturulmuş, üçüncü taraf satıcılar tarafından oluşturulan ve [iş için Microsoft Store](https://businessstore.microsoft.com/store)indirilen çevrimdışı bir uygulama olarak bir Windows uygulamasını karşıya yüklemesi ve dağıtması gerekiyorsa, yönetici şunları yapabilir Bunu [iş kolu uygulaması](apps-add.md#app-types-in-microsoft-intune)olarak dağıtın.  

> [!NOTE]
> Ticari ortamlarda, bir kiracı yöneticisi Iş mağazalarını Intune ile eşitleyebilir, ancak GCC High ve DoD ortamları için bu hizmet kullanılamaz. Bu durumda Yöneticiler doğrudan Intune 'a yükleyerek bir uygulama dağıtmalıdır.  

## <a name="add-line-of-business-apps-using-intune"></a>Intune kullanarak iş kolu uygulamaları ekleme 

Intune kullanarak GCC High veya DoD ortamına yönelik bir iş kolu uygulaması eklemek için [WINDOWS lob uygulaması](lob-apps-windows.md) yönergeleri ' ni izleyebilirsiniz. Şirket Portalı ilk Microsoft Store Iş için dağıtmayı tercih edebilirsiniz. Şirket Portalı kullanmayı seçerseniz Şirket Portalı el ile yükleyebilir ve dağıtabilirsiniz. Daha fazla bilgi için bkz. [Microsoft Intune şirket portalı uygulamasını yapılandırma](company-portal-app.md). 

## <a name="distribute-offline-apps-from-the-store-for-business-using-intune"></a>Intune kullanarak Iş için mağazadan çevrimdışı uygulamalar dağıtma  

Iş için Microsoft Store [çevrimdışı lisansa sahip bir uygulamayı indirmeniz](https://docs.microsoft.com/microsoft-store/distribute-offline-apps#download-an-offline-licensed-app) gerekiyorsa, uygulamayı indirmek için şu adımları izleyin: 

1. [İş Için mağazada](https://businessstore.microsoft.com/)oturum açın.
2. @No__t **Yönet**-1**ayarları**' nı seçin.
3. **Alışveriş deneyimi**altında **çevrimdışı uygulamaları** **Açık**olarak göster ' i ayarlayın.

Uygulamalar için alışveriş yaparken, çevrimdışı bir sürüm varsa, lisans türünü çevrimdışı olarak değiştirmeyi seçebilirsiniz. Uygulamayı aldıktan sonra, [Iş mağazasındaki](https://businessstore.microsoft.com/) >  ürünlerini **Yönet** **& Hizmetleri** ' ni seçerek bunu yönetebilirsiniz. Ayrıca, uygulamayı ve bağımlılıklarını indirebilirsiniz. Daha sonra, bu indirilen uygulamayı (ve bağımlılıklarını) Intune kullanarak kullanıcılara dağıtabilirsiniz.  

## <a name="syncing-intune-to-the-store-for-business"></a>Intune 'U Iş için mağazaya eşitleme 

Ticari (kamu dışı) bir ortamda yönetici, Intune 'u Iş için Microsoft Store eşitlenebilir. Bu, kamu ortamlarında kullanılabilir bir özellik değildir. Ticari ortamlarda Intune ve kamu ortamları için Intune arasındaki farklılıklar hakkında daha fazla bilgi için bkz. [US kamu hizmet açıklaması için Enterprise Mobility + Security](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-govt-service-description).  

Intune 'U Iş için mağaza hesabınıza eşitlemek için, [Microsoft Intune iş için Microsoft Store satın aldığınız uygulamaları yönetme](windows-store-for-business.md)bölümüne bakın.  

## <a name="compliance"></a>Uyumluluk 

Uygulamaların gizlilik ve Uyumluluk bildirimlerini gözden geçirin ve bu hizmetlerin uygun kullanımını değerlendirmek için bunları kuruluşunuzun uyumluluk, güvenlik ve gizlilik gereksinimleriyle karşılaştırın.   

## <a name="next-steps"></a>Sonraki adımlar

Uygulama dağıtma ve atama hakkında daha fazla bilgi edinmek için bkz. [Microsoft Intune olan gruplara uygulama atama](apps-deploy.md).

 
