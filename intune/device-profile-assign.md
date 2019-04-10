---
title: Microsoft Intune’da cihaz profilleri atama | Microsoft Docs
description: Kullanıcılara ve cihazlara cihaz profilleri ve ilkeleri atamak için Azure portalını kullanın. Microsoft Intune profil atamalarından grupların hariç öğrenin.
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
ms.sourcegitcommit: 02803863eba37ecf3d8823a7f1cd7c4f8e3bb42c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59423856"
---
# <a name="assign-user-and-device-profiles-in-microsoft-intune"></a>Microsoft Intune'da kullanıcı ve cihaz profilleri atama

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Profil oluşturma ve girdiğiniz tüm ayarları içerir. Sonraki adım, dağıtmak veya ", Azure Active Directory (Azure AD) kullanıcı veya cihaz grubuna profili atama" şeklindedir. Atandığında, kullanıcıları ve cihazları profilinizi almak ve girdiğiniz ayarları uygulanır.

Bu makalede, profil atama işlemini göstermektedir ve profillerinize ilişkin kapsam etiketleri kullanma hakkında bazı bilgiler içerir.

## <a name="assign-a-device-profile"></a>Bir cihaz profili atama

1. İçinde [Azure portalında](https://portal.azure.com)seçin **tüm hizmetleri** > Filtre **Intune** > seçin **Intune**.
2. **Cihaz yapılandırması** > **Profiller**'i seçin. Tüm profilleri listelenir.
3. Atamak istediğiniz profili seçin > **atamaları**.
4. Tercih **INCLUDE** grupları veya **hariç** gruplandırır ve gruplarınızı'ı seçin. Gruplarınızı seçtiğinizde, bir Azure AD grubu seçersiniz. Birden çok grup seçmek için basılı **Ctrl** anahtar ve grupları seçin.

    ![Grupları bir profil atamasına dahil etme veya atamadan dışlama seçeneklerinin ekran görüntüsü](./media/group-include-exclude.png)

5. Yaptığınız değişiklikleri **kaydedin**.

### <a name="evaluate-how-many-users-are-targeted"></a>Kaç kullanıcının hedeflendiğini değerlendirin

Profili atadığınızda, ayrıca **değerlendir** kaç kullanıcının etkilendiğini. Bu özellik, kullanıcıları hesaplar; Bu cihazları hesaplamaz.

1. Intune'da seçin **cihaz Yapılandırması** > **profilleri**.
2. Bir profili seçin > **atamaları** > **değerlendir**. Bir ileti bu profil tarafından kaç kullanıcının hedeflendiğini gösterir.

Varsa **değerlendir** düğmesi gri, profili bir veya daha fazla gruba atanmış olduğundan emin olun.


## <a name="use-scope-tags"></a>Kapsam etiketlerini kullanma

Oluştururken veya profil güncelleştirme, kapsam etiketleri profiline ekleyebilirsiniz.

**Kapsam etiketleri** atayın ve İnsan kaynakları veya tüm ABD NC gibi belirli gruplara ilkeler filtrelemek için harika bir yoludur çalışanlar. [Dağıtılmış için RBAC ve kapsam etiketleri kullanmak BT](scope-tags.md) daha fazla bilgi bulunur.

## <a name="exclude-groups-from-a-profile-assignment"></a>Grupları bir profil atamasından dışlama

Intune cihaz yapılandırma profilleri, grupları ilke atamasından dışlamanıza olanak tanır. Örneğin, bir cihaz profili atayabilir **tüm şirket kullanıcıları** Grup ancak üyeleri hariç tut **üst düzey yönetim kadrosu** grubu.

Ne zaman yalnızca kullanıcıları, grupları hariç tutma veya yalnızca cihaz gruplarından (değil grupların bir karışımını) atama, Intune kullanıcı cihaz ilişkileri görünmüyor. Kullanıcı gruplarını dahil ederken cihaz gruplarını dışlamak, istediğiniz sonuçları alamayabilirsiniz. Karışık gruplar kullanırken veya başka çakışmaların ise, ekleme, dışlama öncelik kazanır.

Örneğin kuruluşunuzda bilgi noktası cihazları hariç tüm cihazlara cihaz profilleri atamak istiyorsunuz. Bunun için **Tüm Kullanıcılar** grubunu dahil edip **Tüm Cihazlar** grubunu dışlıyorsunuz. Kullanıcının cihaz olsa bile bu durumda, tüm kullanıcılarınız ve onların cihazlarını Bu ilkeyi alır **tüm cihazlar** grubu.

Dışlama, yalnızca grubunun doğrudan üyeleri arar. Bu, bir kullanıcıyla ilişkili cihazları dikkate almaz. Ancak, bir kullanıcısı olmayan cihazlara ilke uygulanmaz. Bu cihazlar herhangi bir ilişkisi olduğundan böyle **tüm kullanıcılar** grubu.

**Tüm Cihazlar** grubunu dahil edip **Tüm Kullanıcılar** grubunu dışlarsanız ilkeyi tüm gruplar alacaktır. Bu senaryodaki amaç, ilişkili kullanıcısı olan cihazları bu ilkeden dışlamaktır. Ancak cihazlar dışlanmaz çünkü dışlama, yalnızca grupların doğrudan üyesi olanları hesaba katar.

## <a name="next-steps"></a>Sonraki adımlar

Bkz: [cihaz profillerini izleme](device-profile-monitor.md) profillerinizi ve profillerinizi çalıştıran cihazları izleme hakkında yönergeler için.