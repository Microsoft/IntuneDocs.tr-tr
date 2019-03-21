---
title: GCC yüksek ve DoD ortamları için uygulamalar
titlesuffix: Microsoft Intune
description: Microsoft Intune kullanarak GCC yüksek ve DoD ortamları içeren uygulamalar hakkında bilgi edinin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/18/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 29329f86-1aa5-434f-9925-8dc28bf35348
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: fb49cd97e029e45d7d098ec1898fd0e27efa1132
ms.sourcegitcommit: 4049a3aed15f2d8d21bb814410875a13f613e4ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/20/2019
ms.locfileid: "58283234"
---
# <a name="deploying-apps-using-intune-on-the-gcc-high-and-dod-environments"></a>GCC yüksek ve DoD ortamları Intune kullanarak uygulamaları dağıtma 

Kiracı yöneticileri tarafından Microsoft Intune gücünün uygulamalarını dağıtmak için kullanılabilir. İş gücü kullanıcılar uygulamaları şirket çalışanı olan. GCC yüksek veya DoD ortamları ıntune'dan dağıtılan uygulamaların birçok türü vardır. Yöneticinin karşıya yüklemek ve üçüncü taraf satıcıları ile oluşturulan bir GCC yüksek veya özel, DoD hedef kitle için hedeflenen bir Windows uygulaması dağıtmak gerekiyorsa veya çevrimdışı bir uygulama yüklendiği [iş için Microsoft Store](https://businessstore.microsoft.com/store), Yönetici olarak dağıtmak seçim yapabileceğiniz bir [iş kolu satır uygulama](apps-add.md#app-types-in-microsoft-intune).  

> [!NOTE]
> GCC yüksek ve DoD ortamları için bu hizmet kullanılabilir değil ancak ticari ortamları için bir kiracı Yöneticisi, Intune ile iş için kendi Store eşitleyebilirsiniz. Yöneticiler bu durumda bir uygulamayı Intune'a doğrudan yükleyerek dağıtmanız gerekir.  

## <a name="add-line-of-business-apps-using-intune"></a>Intune kullanarak iş kolu satır uygulama ekleme 

Intune kullanarak bir yüksek GCC veya DoD ortamı için amaçlanan bir iş kolu satır uygulama eklemek için izleyebileceğiniz [Windows LOB uygulaması](lob-apps-windows.md) yönergeleri. Şirket portalı, iş için Microsoft Store ' dan önce dağıtmak tercih edebilirsiniz. Şirket portalı kullanmayı seçerseniz, el ile yükleyebilir ve şirket Portalı'nı dağıtma. Daha fazla bilgi için [Microsoft Intune Şirket portalı uygulamasını yapılandırma](company-portal-app.md). 

## <a name="distribute-offline-apps-from-the-store-for-business-using-intune"></a>Çevrimdışı ıntune'u iş için Store uygulamaları dağıtma  

Gerekirse [çevrimdışı lisanslı uygulama](https://docs.microsoft.com/microsoft-store/distribute-offline-apps#download-an-offline-licensed-app) iş için Microsoft Store uygulamayı indirmek için aşağıdaki adımları izleyin: 

1. Oturum [iş Store](https://businessstore.microsoft.com/).
2. Seçin **yönetme** > **ayarları**.
3. Altında **alışveriş deneyimi**ayarlayın **çevrimdışı uygulamaları Göster** için **üzerinde**.

Çevrimdışı bir sürüm varsa, uygulamalar için alışveriş yaparken çevrimdışı lisans türünü değiştirmek seçebilirsiniz. Uygulamayı aldıktan sonra ardından bunu seçerek yönetebileceğiniz **Yönet** > **ürünler ve Hizmetler** içinde [iş Store](https://businessstore.microsoft.com/). Ayrıca, uygulamayı ve bağımlılıklarını yükleyebilirsiniz. Ardından, Intune kullanan kullanıcılar indirilen bu uygulamayı (ve bağımlılıklarını) dağıtabilirsiniz.  

## <a name="syncing-intune-to-the-store-for-business"></a>İş için Intune'a Store eşitleniyor 

Bir ticari (resmi olmayan) ortamında, bir yönetici iş için Microsoft Store Intune'a eşitleyebilir. Bu, kamu ortamlarda kullanılabilir bir özellik değildir. Kamu ortamları için Intune ticari ortamlarda ile Intune arasındaki farklar hakkında daha fazla ayrıntı için bkz: [Enterprise Mobility + Security ABD devlet hizmeti açıklaması için](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-govt-service-description).  

İş hesabı, Store Intune'a eşitlemek için bkz: [Intune Microsoft ile iş için Microsoft Store ' ndan satın aldığınız uygulamaları yönetme](windows-store-for-business.md).  

## <a name="compliance"></a>Uyumluluk 

Gizlilik ve uyumluluk bilgilerinin uygulamaları gözden geçirin ve kuruluşunuzun uyumluluk, güvenlik ve gizlilik gereksinimlerini uygun hizmetlerin kullanımını değerlendirirken karşılaştırın.   

## <a name="next-steps"></a>Sonraki adımlar

Daha fazla ilgili dağıtmak ve uygulamaları atama bilgi edinmek için [Intune gruplara uygulama atama](apps-deploy.md).

 
