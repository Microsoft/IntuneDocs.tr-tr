---
title: Intune'da ayarlanan erişim noktası kısıtlamalarını çözme
description: Intune'un erişim noktası kısıtlama ilkeleri için 3 ortak iletiyi gözden geçirin ve bunların nasıl çözüleceğini öğrenin
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 05/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
searchScope:
- User help
ROBOTS: ''
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: aefde274ec7ca925d45dd101ee0ebef1083f7f19
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "55851279"
---
# <a name="resolve-access-point-restrictions"></a>Erişim noktası kısıtlamalarını çözme

Kuruluşların cihazların şirket verilerine hangi konumlardan erişeceğini kısıtlayabilir.
Bu *erişim noktası kısıtlamalarını* yapılandırmak için, onaylanan ağ konumlarını belirtir ve ayarlarlar.  

Tanınmayan veya onaylanmamış bir ağa bağlanmayı denediğinizde, aşağıdaki iletilerden birini veya birden çoğunu alabilirsiniz:

* Erişim noktası kısıtlamaları ayarlanmadı.
* Onaylanan bir ağa bağlı değilsiniz.
* Bir hata oluştu ve erişim noktası kısıtlamaları zorunlu tutulamadı.

 Aşağıdaki tabloda iletiler, anlamları ve iş kaynaklarınıza yeniden nasıl erişebileceğiniz listelenir.

## <a name="access-point-restrictions-not-set-up"></a>Erişim noktası kısıtlamaları ayarlanmadı  
| Şirket Portalı iletisi | İletinin anlamı | Yapmanız gerekenler                                                               
|------------------------|--------------------------|--------------------------|
| **Erişim noktası kısıtlamaları ayarlanmadı – Erişim noktası kısıtlamaları etkindir ve ayarlanması gerekir.** | Şirket cihazınıza erişim noktası kısıtlamaları uygulamıştır. Bu ayar, Şirket Portalı uygulamasının cihazınızda birkaç ağ ayarını doğrulamasını gerektirir. | **Çözümle**'ye dokunun. Şirket Portalı uygulaması, şirketin onayladığı bir ağa bağlı olduğunuzdan emin olmak için bunu denetler. |

## <a name="not-connected-to-an-approved-network"></a>Onaylanan bir ağa bağlı değildir  

| Şirket Portalı iletisi | İletinin anlamı | Yapmanız gerekenler                                                                   
|------------------------|-----------------------------------|--------------------------|
| **Cihaz onaylanan bir ağa bağlı değildir – Onaylanan bir kablosuz ağa bağlanın.** | İş erişimi için onaylanmamış bir ağa bağlandınız. Bu ağa bağlı olduğunuz sürece, iş e-postasına, uygulamalarına ve diğer korunan şirket kaynaklarına erişemezsiniz. | Şirket tarafından onaylanan bir ağa bağlayın. Ardından **Çözümle**'ye dokunarak yeniden deneyin. |

## <a name="restrictions-couldnt-be-enforced"></a>Kısıtlamalar zorunlu tutulamadı  

| Şirket Portalı iletisi | İletinin anlamı | Yapmanız gerekenler                                                                      
|------------------------|-----------------------------------|--------------------------|
| **Erişim noktası kısıtlamaları zorunlu tutulamadı – Şirket Portalı hatayla karşılaştı.** | Intune, onaylanan bir ağa bağlı olup olmadığınızı belirleyemiyor. Bu hata zayıf ağ bağlantısından, düşük pil düzeyinden, pil tasarrufu modundan veya Şirket Portalı hatasından kaynaklanabilir. | Ağ sinyal düzeyinizin güçlü olduğunu doğrulayın. Pil tasarrufu modunu kapatın ve kalan pil ömrünüzün en az %30 düzeyinde olduğundan emin olun. Ardından **Çözümle**'ye dokunarak yeniden deneyin. 

Bu bilgiler yardımcı olmadı mı? Şirketinizin destek birimine başvurmanızı öneririz. Belirli iletişim bilgileri için [Şirket Portalı Web sitesine](https://portal.manage.microsoft.com/#HelpDeskDialog) gidin.
