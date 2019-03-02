---
title: Microsoft Intune’da cihaz profilleri atama | Microsoft Docs
description: Kullanıcılara ve cihazlara cihaz profilleri ve ilkeleri atamak için Azure portalını kullanın. Microsoft Intune'da grupları bir profil atamasının dışında tutmayı öğrenin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/01/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f6f5414d-0e41-42fc-b6cf-e7ad76e1e06d
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8263bc7a6a38431d942bd8714b1911a94cb4a24a
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57239025"
---
# <a name="assign-user-and-device-profiles-in-microsoft-intune"></a>Microsoft Intune'da kullanıcı ve cihaz profilleri atama

Bir profil oluşturduktan sonra, profili Azure Active Directory (Azure AD) gruplarına atayabilirsiniz.

## <a name="assign-a-device-profile"></a>Bir cihaz profili atama

1. [Azure portalında](https://portal.azure.com), **Tüm Hizmetler**’i seçin ve **Microsoft Intune** araması yapın.
2. **Microsoft Intune**’da, **Cihaz yapılandırması**’nı ve **Profiller**’i seçin.
3. Profil listesinde, atamak istediğiniz profili ve ardından **Atamalar**’ı seçin.
4. Grupları **Dahil Etmeyi** veya **Dışlamayı** seçin ve sonra da grupları belirtin.  

    ![Grupları bir profil atamasına dahil etme veya atamadan dışlama seçeneklerinin ekran görüntüsü](./media/group-include-exclude.png)

5. Gruplarınızı seçtiğinizde, bir Azure AD grubu seçersiniz. Birden çok grup seçmek için **Ctrl** tuşunu basılı tutun.
6. İşiniz bittiğinde **Kaydet**‘i seçin.

## <a name="exclude-groups-from-a-profile-assignment"></a>Grupları bir profil atamasından dışlama

Intune cihaz yapılandırma profilleri, grupları ilke atamasından dışlamanıza olanak tanır. Örneğin **Tüm şirket kullanıcıları** grubuna bir cihaz profili atayabilir ve **Üst Düzey Yönetim Kadrosu** grubundan istediğiniz üyeleri dışlayabilirsiniz.

Grupları bir atamadan dışladığınızda, yalnızca kullanıcıları dışlayın ya da yalnızca cihaz gruplarını dışlayın (grupların bir karışımını değil); Intune herhangi bir kullanıcı-cihaz ilişkisini dikkate almaz. Kullanıcı gruplarını dahil ederken cihaz gruplarını dışlamak, istediğiniz sonuçları vermeyebilir. Karışık gruplar kullanmanız veya başka çakışmaların ortaya çıkması durumunda, dahil etme işleminin dışlama işlemine önceliği vardır.

Örneğin kuruluşunuzda bilgi noktası cihazları hariç tüm cihazlara cihaz profilleri atamak istiyorsunuz. Bunun için **Tüm Kullanıcılar** grubunu dahil edip **Tüm Cihazlar** grubunu dışlıyorsunuz. Bu durumda, cihazı **Tüm Cihazlar** grubunun parçası olan kullanıcılar bile dahil olmak üzere tüm kullanıcılarınız ve onların cihazları bu ilkeyi alır.

Dışlama işlemi yalnızca grupların doğrudan üyesi olanları değerlendirmeye alır ve bir kullanıcıyla ilişkili cihazları dikkate almaz. Ancak, bir kullanıcısı olmayan cihazlara ilke uygulanmaz. Bunun nedeni, bu cihazların **Tüm Kullanıcılar** grubuyla ilişkisi olmamasıdır.

**Tüm Cihazlar** grubunu dahil edip **Tüm Kullanıcılar** grubunu dışlarsanız ilkeyi tüm gruplar alacaktır. Bu senaryodaki amaç, ilişkili kullanıcısı olan cihazları bu ilkeden dışlamaktır. Ancak cihazlar dışlanmaz çünkü dışlama, yalnızca grupların doğrudan üyesi olanları hesaba katar.

## <a name="next-steps"></a>Sonraki adımlar
Cihaz profili atamaları izleme hakkında yönergeler için [Cihaz profillerini izleme](device-profile-monitor.md) konusuna bakın.
