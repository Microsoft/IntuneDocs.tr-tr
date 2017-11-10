---
title: "Intune için uygulama yapılandırma ilkeleri | Microsoft Docs"
titlesuffix: Azure portal
description: "Intune için uygulama yapılandırma ilkelerini kullanma hakkında bilgi edinin."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 834B4557-80A9-48C0-A72C-C98F6AF79708
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b690f691278d0cc708ed7e586e30aee4ed6e807a
ms.sourcegitcommit: 67c037af31c1f167ec9b4f4baa754631c817e7d1
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2017
---
# <a name="app-configuration-policies-for-intune"></a>Intune için uygulama yapılandırma ilkeleri

Kullanıcılar Microsoft Intune’daki uygulama yapılandırma ilkeleriyle bir iOS veya Android uygulamasını çalıştırdığında ayarları sağlayın. Örneğin, bir uygulama kullanıcıların şunları belirtmesini gerektirebilir:

- Özel bağlantı noktası numarası
- Dil ayarları
- Güvenlik ayarları
- Bir şirket logosu gibi marka ayarları

Kullanıcılar, bu ayarları hatalı şekilde girerse yardım masanız üzerindeki yük artabilir ve yeni uygulamaların benimsenmesi yavaşlayabilir.

Uygulama yapılandırma ilkeleri, kullanıcılarınız uygulamayı çalıştırmadan önce bu ayarları bir ilke ile kullanıcılara atamanıza imkan vererek bu sorunları ortadan kaldırmanıza yardımcı olabilir. Daha sonra ayarlar otomatik olarak sağlanır ve kullanıcıların herhangi bir eylem yapması gerekmez.

Bu ilkeleri kullanıcılara ve cihazlara doğrudan atamazsınız. Bunun yerine, ilkeyi bir uygulamayla ilişkilendirir ve uygulamayı atarsınız. İlke ayarları, uygulama tarafından ilke denetimi gerçekleştirildiğinde (genellikle ilk çalıştırıldığında) kullanılır.

Intune’la uygulama yapılandırmalarını kullanmak için iki seçeneğiniz vardır:
 - **Yönetilen cihazlar**  
   Cihaz MDM sağlayıcısı olarak Intune tarafından yönetilir.
 - **Yönetilen uygulamalar**  
   Uygulama cihaz kaydı olmadan yönetilir.

## <a name="apps-that-support-app-configuration"></a>Uygulama yapılandırmasını destekleyen uygulamalar

Destekleyen uygulamalar için uygulama yapılandırma ilkelerini kullanabilirsiniz. Intune Uygulamalarında uygulama yapılandırmasını desteklemek için, uygulamalar, uygulama yapılandırmaları kullanımını desteklemek üzere yazılmış olmalıdır. Ayrıntılar için uygulama satıcınıza başvurun.

Intune Uygulama SDK’sını uygulamaya ekleyerek veya uygulamayı geliştirildikten sonra sarmalayarak iş kolu uygulamalarınızı hazırlayabilirsiniz. iOS ve Android için kullanılabilen Intune uygulama SDK'sı, uygulamanızı Intune uygulama koruma ilkeleri için etkinleştirir. Uygulama geliştiricisinin yapması gereken kod değişikliklerini en aza indirme çabası içindedir. Daha fazla bilgi için bkz. [Intune Uygulama SDK’sına genel bakış](app-sdk.md).

## <a name="graph-api-support-for-app-configuration"></a>Uygulama yapılandırması için Graph API desteği

Ayrıca uygulama yapılandırma görevlerini tamamlamak için Graph API’si de kullanabilirsiniz. Ayrıntılar için bkz. [Graph API’si Başvurusu MAM Hedefli Yapılandırma](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create).

## <a name="next-steps"></a>Sonraki adımlar

### <a name="managed-devices"></a>Yönetilen cihazlar

 - iOS cihazlarınızla uygulama yapılandırmasını kullanma hakkında bilgi edinin.  Bkz. [Yönetilen iOS cihazları için uygulama yapılandırma ilkeleri ekleme](app-configuration-policies-use-ios.md).
 - Android cihazlarınızla uygulama yapılandırmasını kullanma hakkında bilgi edinin.  Bkz. [Yönetilen Android cihazları için uygulama yapılandırma ilkeleri ekleme](app-configuration-policies-use-android.md).

### <a name="managed-apps"></a>Yönetilen uygulamalar

 - Yönetilen uygulamalarla uygulama yapılandırmasını kullanma hakkında bilgi edinin. Bkz. [Cihaz kaydı olmadan yönetilen uygulamalar için uygulama yapılandırma ilkeleri ekleme](app-configuration-policies-managed-app.md).