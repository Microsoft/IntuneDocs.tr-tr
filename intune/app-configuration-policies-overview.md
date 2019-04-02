---
title: Microsoft Intune için uygulama yapılandırma ilkeleri
titleSuffix: ''
description: Microsoft Intune ile bir iOS veya Android cihazında uygulama yapılandırma ilkelerini nasıl kullanacağınızı öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/03/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 834B4557-80A9-48C0-A72C-C98F6AF79708
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 844342d0d21110f46ac9a344edbd7409f7d779cb
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58797967"
---
# <a name="app-configuration-policies-for-microsoft-intune"></a>Microsoft Intune için uygulama yapılandırma ilkeleri

Bir iOS veya Android uygulamasına yapılandırma ayarları sağlamak için Microsoft Intune’daki uygulama yapılandırma ilkelerini kullanın. Bu yapılandırma ayarları, uygulamanın özelleştirilebilmesini sağlar. Bu yapılandırma ilkelerini kullanıcılara ve cihazlara doğrudan atamazsınız. Bunun yerine, yapılandırma ilkesini bir uygulamayla ilişkilendirin ve bu uygulamayı atayın. Yapılandırma ilkesi ayarları, uygulama tarafından denetim gerçekleştirildiğinde, genellikle de uygulama ilk defa çalıştırıldığında kullanılır.

Dahil etme ve dışlama atamalarının birleşimini kullanarak kullanıcı ve cihaz gruplarına bir uygulama yapılandırma ilkesi atayabilirsiniz. Bir uygulama yapılandırma ilkesini ekledikten sonra bu uygulama yapılandırma ilkesi için atamaları ayarlayabilirsiniz. İlke için atamaları ayarladıktan sonra ilkenin uygulandığı kullanıcı gruplarını dahil etmeyi veya dışlamayı seçebilirsiniz. Bir veya daha fazla grubu dahil etmeyi seçtiğinizde, belirli grupları dahil etmeyi veya yerleşik grupları kullanmayı seçebilirsiniz. Yerleşik gruplar, **Tüm Kullanıcılar**, **Tüm Cihazlar** ve **Tüm Kullanıcılar + Tüm Cihazlar** şeklindedir.

Örneğin bir uygulama, aşağıdaki ayrıntılardan birini belirtmenizi gerektirebilir:

- Özel bağlantı noktası numarası
- Dil ayarları
- Güvenlik ayarları
- Bir şirket logosu gibi marka ayarları

Kullanıcılar, bu ayarları hatalı şekilde girerse yardım masanız üzerindeki yük artabilir ve yeni uygulamaların benimsenmesi yavaşlayabilir.

Uygulama yapılandırma ilkeleri, kullanıcılarınız uygulamayı çalıştırmadan önce bu ayarları bir ilke ile kullanıcılara atamanıza imkan vererek bu sorunları ortadan kaldırmanıza yardımcı olabilir. Daha sonra ayarlar otomatik olarak sağlanır ve kullanıcıların herhangi bir eylem yapması gerekmez.

Uygulama bu ayrıntıları her denetlediğinde yapılandırma ayarları kullanılır. Bir uygulama genellikle kullanıcı tarafından ilk çalıştırıldığında yapılandırma ayarlarını denetler.

Intune’la uygulama yapılandırmalarını kullanmak için iki seçeneğiniz vardır:
 - **Yönetilen cihazlar** - Cihaz, mobil cihaz yetkilisi (MDM) sağlayıcısı olarak Intune tarafından yönetilir.
 - **Yönetilmeyen cihazlar** - Uygulama, cihaz kaydı olmadan yönetilir.

> [!NOTE]
> Microsoft Intune yöneticisi olarak yönetilen cihazlarda hangi kullanıcı hesaplarının Microsoft Office uygulamalarına eklendiğini denetleyebilirsiniz. Erişimi yalnızca izin verilen kullanıcı hesaplarıyla sınırlayabilecek ve kayıtlı cihazlarda kişisel hesapları engelleyebilirsiniz. Destekleyen uygulamalar, uygulama yapılandırmasını işler ve onaylanmamış hesapları kaldırıp engeller.

## <a name="apps-that-support-app-configuration"></a>Uygulama yapılandırmasını destekleyen uygulamalar

Destekleyen uygulamalar için uygulama yapılandırma ilkelerini kullanabilirsiniz. Intune uygulamalarında uygulama yapılandırmasını desteklemek için uygulamalar, uygulama yapılandırmaları kullanımını desteklemek üzere yazılmış olmalıdır. Ayrıntılar için uygulama satıcınıza başvurun.

Intune Uygulama SDK’sını uygulamaya ekleyerek veya uygulamayı geliştirildikten sonra sarmalayarak iş kolu uygulamalarınızı hazırlayabilirsiniz. Intune uygulama SDK'sı, iOS ve Android için kullanılabilir, uygulamanızı Intune uygulama yapılandırma ilkeleri için etkinleştirir. Uygulama geliştiricisinin yapması gereken kod değişikliklerini en aza indirme çabası içindedir. Daha fazla bilgi için bkz. [Intune Uygulama SDK’sına genel bakış](app-sdk.md).

## <a name="graph-api-support-for-app-configuration"></a>Uygulama yapılandırması için Graph API desteği

Ayrıca uygulama yapılandırma görevlerini tamamlamak için Graph API’si de kullanabilirsiniz. Ayrıntılar için bkz. [Graph API’si Başvurusu MAM Hedefli Yapılandırma](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create).

## <a name="next-steps"></a>Sonraki adımlar

### <a name="managed-devices"></a>Yönetilen cihazlar

 - iOS cihazlarınızla uygulama yapılandırmasını kullanma hakkında bilgi edinin.  Bkz. [Yönetilen iOS cihazları için uygulama yapılandırma ilkeleri ekleme](app-configuration-policies-use-ios.md).
 - Android cihazlarınızla uygulama yapılandırmasını kullanma hakkında bilgi edinin.  Bkz. [Yönetilen Android cihazları için uygulama yapılandırma ilkeleri ekleme](app-configuration-policies-use-android.md).

### <a name="managed-apps"></a>Yönetilen uygulamalar

 - Yönetilen uygulamalarla uygulama yapılandırmasını kullanma hakkında bilgi edinin. Bkz. [Cihaz kaydı olmadan yönetilen uygulamalar için uygulama yapılandırma ilkeleri ekleme](app-configuration-policies-managed-app.md).
