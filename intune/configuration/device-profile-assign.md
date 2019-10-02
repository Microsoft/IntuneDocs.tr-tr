---
title: Microsoft Intune’da cihaz profilleri atama | Microsoft Docs
description: Kullanıcılara ve cihazlara cihaz profilleri ve ilkeleri atamak için Azure portalını kullanın. Microsoft Intune'da grupları bir profil atamasının dışında tutmayı öğrenin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/17/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f6f5414d-0e41-42fc-b6cf-e7ad76e1e06d
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 344ffdfefd8b354c9d2ab31f2d08c2a25456f970
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71730805"
---
# <a name="assign-user-and-device-profiles-in-microsoft-intune"></a>Microsoft Intune'da kullanıcı ve cihaz profilleri atama

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Bir profil oluşturursunuz ve girdiğiniz tüm ayarlar burada saklanır. Bir sonraki adım, profili Azure Active Directory (Azure AD) kullanıcı veya cihaz gruplarınıza dağıtmak veya "atamaktır". Atanan profiller kullanıcılara ve cihazlara ulaşır ve girdiğiniz ayarlar uygulanır.

Bu makalede profil atama yöntemlerinin yanı sıra profillerinizde kapsam etiketlerini kullanma adımları hakkında bilgilere yer verilmiştir.

## <a name="assign-a-device-profile"></a>Bir cihaz profili atama

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. **Cihaz yapılandırması** > **Profiller**'i seçin. Tüm profiller listelenir.
3. Atamak istediğiniz profili ve ardından **Atamalar**'ı seçin.
4. Grupları **Dahil Etmeyi** veya **Dışlamayı** seçin ve sonra da gruplarınızı belirtin. Gruplarınızı seçtiğinizde, bir Azure AD grubu seçersiniz. Birden çok grup seçmek için grupları seçerken **Ctrl** tuşunu basılı tutun.

    ![Grupları bir profil atamasına dahil etme veya atamadan dışlama seçeneklerinin ekran görüntüsü](./media/device-profile-assign/group-include-exclude.png)

5. Yaptığınız değişiklikleri **kaydedin**.

### <a name="evaluate-how-many-users-are-targeted"></a>Kaç kullanıcının hedeflendiğini değerlendirme

Profili atadıktan sonra etkilenen kullanıcı sayısını da **değerlendirebilirsiniz**. Bu özellik, cihaz değil kullanıcı sayısını hesaplar.

1. Intune'da **Cihaz yapılandırması** > **Profiller**'i seçin.
2. Bir profil seçip **Atamalar** > **Değerlendir** yolunu izleyin. Bu profilin kaç kullanıcıyı hedeflediğini gösteren bir ileti görüntülenir.

**Değerlendir** düğmesi gri gösteriliyorsa, profilin bir veya birden fazla gruba atandığından emin olun.

## <a name="use-scope-tags-or-applicability-rules"></a>Kapsam etiketlerini veya uygulanabilirlik kurallarını kullanma

Bir profil oluşturduğunuzda veya güncelleştirdiğinizde, profile kapsam etiketleri ve Uygulanabilirlik kuralları da ekleyebilirsiniz.

**Kapsam etiketleri**, ilkeleri İnsan Kaynakları veya Merkez ofis çalışanları gibi belirli gruplara atamak ve filtreleme yapmak için kullanabileceğiniz bir yöntemdir. Daha fazla bilgi için bkz. [Dağıtılmış BT için RBAC ve kapsam etiketlerini kullanma](../fundamentals/scope-tags.md).

Windows 10 cihazlarında, profil yalnızca belirli bir işletim sistemi sürümü veya belirli bir Windows sürümü için geçerli olacak şekilde **uygulanabilirlik kuralları** ekleyebilirsiniz. [Uygulanabilirlik kurallarında](device-profile-create.md#applicability-rules) daha fazla bilgi bulunur.

## <a name="exclude-groups-from-a-profile-assignment"></a>Grupları bir profil atamasından dışlama

Intune cihaz yapılandırma profilleri, grupları ilke atamasından dışlamanıza olanak tanır.

Intune, Kullanıcı-cihaz grubu ilişkilerine bakar. Kullanıcı gruplarını dahil ederken cihaz gruplarını dışlamak, istediğiniz sonuçları vermeyebilir. Kullanıcı grubundan Kullanıcı grubu ve cihaz grubundan cihaza grup senaryolarında dışlama, dahil edilmeye göre önceliklidir.

Örneğin, **tüm kurumsal kullanıcılar** kullanıcı grubuna bir cihaz profili atarsınız, ancak üst **düzey yönetim personeli** Kullanıcı grubundaki üyeleri dışlayabilirsiniz. Her iki grup da Kullanıcı grupları olduğundan, **tüm şirket kullanıcıları** dahil et grubunun üyesi olsalar dahi, üst **düzey yönetim personelinin** tüm üyeleri ilkeden çıkarılır.

Ekleme, Kullanıcı grubundan cihaza grup veya cihaz grubundan Kullanıcı grubu gibi karma grupları kullanırken dışlamaya göre önceliklidir.

Örneğin, kuruluşunuzdaki tüm kullanıcılara bilgi noktası cihazları dışında bir cihaz profili atamak istiyorsunuz. Bunun için **Tüm Kullanıcılar** grubunu dahil edip **Tüm Cihazlar** grubunu dışlıyorsunuz. Bu durumda, cihazı **Tüm Cihazlar** grubunun parçası olan kullanıcılar bile dahil olmak üzere tüm kullanıcılarınız ve onların cihazları bu ilkeyi alır.

Dışlama yalnızca doğrudan gruba üye olanları dikkate alır. Kullanıcıyla ilişkilendirilen cihazları dahil etmez. Ancak, bir kullanıcısı olmayan cihazlar, ilke almaz. Bu davranış, kullanıcıları olmayan cihazların **tüm kullanıcılar** grubuyla ilişkisi olmadığı için oluşur.

**Tüm Cihazlar** grubunu dahil edip **Tüm Kullanıcılar** grubunu dışlarsanız ilkeyi tüm gruplar alacaktır. Bu senaryodaki amaç, ilişkili kullanıcısı olan cihazları bu ilkeden dışlamaktır. Ancak cihazlar dışlanmaz çünkü dışlama, yalnızca grupların doğrudan üyesi olanları hesaba katar.

## <a name="next-steps"></a>Sonraki adımlar

Profillerinizi ve profillerinizin çalıştığı cihazları izleme konusunda bilgi için bkz. [Cihaz profillerini izleme](device-profile-monitor.md).
