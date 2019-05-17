---
title: Microsoft Intune’da cihaz profilleri atama | Microsoft Docs
description: Kullanıcılara ve cihazlara cihaz profilleri ve ilkeleri atamak için Azure portalını kullanın. Microsoft Intune'da grupları bir profil atamasının dışında tutmayı öğrenin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/08/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f6f5414d-0e41-42fc-b6cf-e7ad76e1e06d
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0c950efdd95fd8d856ec677385712a022dead870
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2019
ms.locfileid: "59898743"
---
# <a name="assign-user-and-device-profiles-in-microsoft-intune"></a>Microsoft Intune'da kullanıcı ve cihaz profilleri atama

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bir profil oluşturursunuz ve girdiğiniz tüm ayarlar burada saklanır. Bir sonraki adım, profili Azure Active Directory (Azure AD) kullanıcı veya cihaz gruplarınıza dağıtmak veya "atamaktır". Atanan profiller kullanıcılara ve cihazlara ulaşır ve girdiğiniz ayarlar uygulanır.

Bu makalede profil atama yöntemlerinin yanı sıra profillerinizde kapsam etiketlerini kullanma adımları hakkında bilgilere yer verilmiştir.

## <a name="assign-a-device-profile"></a>Bir cihaz profili atama

1. [Azure portalında](https://portal.azure.com) **Tüm Hizmetler**’i seçin > **Intune**’u filtreleyin ve **Intune**’u seçin.
2. **Cihaz yapılandırması** > **Profiller**'i seçin. Tüm profiller listelenir.
3. Atamak istediğiniz profili ve ardından **Atamalar**'ı seçin.
4. Grupları **Dahil Etmeyi** veya **Dışlamayı** seçin ve sonra da gruplarınızı belirtin. Gruplarınızı seçtiğinizde, bir Azure AD grubu seçersiniz. Birden çok grup seçmek için grupları seçerken **Ctrl** tuşunu basılı tutun.

    ![Grupları bir profil atamasına dahil etme veya atamadan dışlama seçeneklerinin ekran görüntüsü](./media/group-include-exclude.png)

5. Yaptığınız değişiklikleri **kaydedin**.

### <a name="evaluate-how-many-users-are-targeted"></a>Kaç kullanıcının hedeflendiğini değerlendirme

Profili atadıktan sonra etkilenen kullanıcı sayısını da **değerlendirebilirsiniz**. Bu özellik, cihaz değil kullanıcı sayısını hesaplar.

1. Intune'da **Cihaz yapılandırması** > **Profiller**'i seçin.
2. Bir profil seçip **Atamalar** > **Değerlendir** yolunu izleyin. Bu profilin kaç kullanıcıyı hedeflediğini gösteren bir ileti görüntülenir.

**Değerlendir** düğmesi gri gösteriliyorsa, profilin bir veya birden fazla gruba atandığından emin olun.


## <a name="use-scope-tags"></a>Kapsam etiketlerini kullanma

Profil oluşturma veya güncelleştirme sırasında kapsam etiketi de ekleyebilirsiniz.

**Kapsam etiketleri**, ilkeleri İnsan Kaynakları veya Merkez ofis çalışanları gibi belirli gruplara atamak ve filtreleme yapmak için kullanabileceğiniz bir yöntemdir. Daha fazla bilgi için bkz. [Dağıtılmış BT için RBAC ve kapsam etiketlerini kullanma](scope-tags.md).

## <a name="exclude-groups-from-a-profile-assignment"></a>Grupları bir profil atamasından dışlama

Intune cihaz yapılandırma profilleri, grupları ilke atamasından dışlamanıza olanak tanır. Örneğin **Tüm şirket kullanıcıları** grubuna bir cihaz profili atayabilir ve **Üst Düzey Yönetim Kadrosu** grubundan belirli üyeleri dışlayabilirsiniz.

Grupları, yalnızca kullanıcıları veya cihaz gruplarını (grupların bir karışımını değil) bir atamadan dışladığınızda; Intune herhangi bir kullanıcı-cihaz ilişkisini dikkate almaz. Kullanıcı gruplarını dahil ederken cihaz gruplarını dışlamak, istediğiniz sonuçları vermeyebilir. Karışık gruplar kullanmanız veya başka çakışmaların ortaya çıkması durumunda, dahil etme işleminin dışlama işlemine önceliği vardır.

Örneğin kuruluşunuzda bilgi noktası cihazları hariç tüm cihazlara cihaz profilleri atamak istiyorsunuz. Bunun için **Tüm Kullanıcılar** grubunu dahil edip **Tüm Cihazlar** grubunu dışlıyorsunuz. Bu durumda, cihazı **Tüm Cihazlar** grubunun parçası olan kullanıcılar bile dahil olmak üzere tüm kullanıcılarınız ve onların cihazları bu ilkeyi alır.

Dışlama yalnızca doğrudan gruba üye olanları dikkate alır. Kullanıcıyla ilişkilendirilen cihazları dahil etmez. Ancak, bir kullanıcısı olmayan cihazlara ilke uygulanmaz. Bunun nedeni, bu cihazların **Tüm Kullanıcılar** grubuyla ilişkisi olmamasıdır.

**Tüm Cihazlar** grubunu dahil edip **Tüm Kullanıcılar** grubunu dışlarsanız ilkeyi tüm gruplar alacaktır. Bu senaryodaki amaç, ilişkili kullanıcısı olan cihazları bu ilkeden dışlamaktır. Ancak cihazlar dışlanmaz çünkü dışlama, yalnızca grupların doğrudan üyesi olanları hesaba katar.

## <a name="next-steps"></a>Sonraki adımlar

Profillerinizi ve profillerinizin çalıştığı cihazları izleme konusunda bilgi için bkz. [Cihaz profillerini izleme](device-profile-monitor.md).