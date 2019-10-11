---
title: Microsoft Intune-Azure 'da cihaz profilleri atama | Microsoft Docs
description: Kullanıcılara ve cihazlara cihaz profilleri ve ilkeleri atamak için Azure portal kullanın. Microsoft Intune bir profil atamasından grupları nasıl dışleyeceğinizi öğrenin.
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
ms.openlocfilehash: db1f0944a6725d1f361ea20c972d8ffa8f5d9035
ms.sourcegitcommit: a50a1ca123ecc2c5ac129f112f73838748f56476
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/10/2019
ms.locfileid: "72237205"
---
# <a name="assign-user-and-device-profiles-in-microsoft-intune"></a>Microsoft Intune kullanıcı ve cihaz profilleri atama

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Bir profil oluşturun ve girdiğiniz tüm ayarları içerir. Sonraki adım, profili Azure Active Directory (Azure AD) Kullanıcı veya cihaz gruplarına dağıtmaktır veya "atamanız". Atandığında, kullanıcılar ve cihazlar profilinizi alır ve girdiğiniz ayarlar uygulanır.

Bu makalede profil atama ve profillerinizin kapsam etiketlerini kullanma hakkında bazı bilgiler yer almaktadır.

> [!NOTE]  
> Bir ilke kaldırıldığında veya bir cihaza artık atanmadıysa, ayar varolan değeri tutabilir. Ayar varsayılan değere dönmez. Ayarı farklı bir değer olarak değiştirmek için yeni bir ilke oluşturun ve atayın.

## <a name="assign-a-device-profile"></a>Bir cihaz profili atama

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. **Cihaz yapılandırma** > **profilleri**' ni seçin. Tüm profiller listelenir.
3. > **Atamalarını**atamak istediğiniz profili seçin.
4. Grupları **dahil** etmek veya **hariç tutmak** için seçin ve sonra gruplarınızı seçin. Gruplarınızı seçerken bir Azure AD grubu seçersiniz. Birden çok Grup seçmek için **CTRL** tuşunu basılı tutun ve gruplarınızı seçin.

    ![Bir profil atamasında grupları dahil etme veya hariç tutma seçeneklerinin ekran görüntüsü](./media/device-profile-assign/group-include-exclude.png)

5. Değişikliklerinizi **kaydedin** .

### <a name="evaluate-how-many-users-are-targeted"></a>Kaç kullanıcının hedeflenmekte olduğunu değerlendirin

Profili atadığınızda, kaç kullanıcının etkilendiğini de **değerlendirebilirsiniz** . Bu özellik kullanıcıları hesaplar; cihazları hesaplamaz.

1. Intune ' da, **cihaz yapılandırması** > **profilleri**' ni seçin.
2. > **Atamaları** > **değerlendir**' i seçin. Bu profil tarafından kaç kullanıcının hedeflendiğinden bir ileti gösterilir.

**Değerlendir** düğmesi gri ise, profilin bir veya daha fazla gruba atandığından emin olun.

## <a name="use-scope-tags-or-applicability-rules"></a>Kapsam etiketlerini veya uygulanabilirlik kurallarını kullanma

Bir profil oluşturduğunuzda veya güncelleştirdiğinizde, profile kapsam etiketleri ve Uygulanabilirlik kuralları da ekleyebilirsiniz.

**Kapsam etiketleri** , Ilkeleri, insan kaynakları veya tüm ABD-NC çalışanları gibi belirli gruplara atamak ve filtrelemek için harika bir yoldur. [Dağıtılmış BT IÇIN RBAC ve kapsam etiketlerini kullanma](../fundamentals/scope-tags.md) daha fazla bilgi içerir.

Windows 10 cihazlarında, profil yalnızca belirli bir işletim sistemi sürümü veya belirli bir Windows sürümü için geçerli olacak şekilde **uygulanabilirlik kuralları** ekleyebilirsiniz. [Uygulanabilirlik kurallarında](device-profile-create.md#applicability-rules) daha fazla bilgi bulunur.

## <a name="exclude-groups-from-a-profile-assignment"></a>Grupları bir profil atamasından dışlama

Intune cihaz yapılandırma profilleri, ilke atamasından grupları dışlayamazsınız.

Intune, Kullanıcı-cihaz grubu ilişkilerine bakar. Cihaz gruplarını dışlarken Kullanıcı gruplarının dahil edilmesi, bekleyen sonuçları alamaz. Kullanıcı grubundan Kullanıcı grubu ve cihaz grubundan cihaza grup senaryolarında dışlama, dahil edilmeye göre önceliklidir.

Örneğin, **tüm kurumsal kullanıcılar** kullanıcı grubuna bir cihaz profili atarsınız, ancak üst **düzey yönetim personeli** Kullanıcı grubundaki üyeleri dışlayabilirsiniz. Her iki grup da Kullanıcı grupları olduğundan, **tüm şirket kullanıcıları** dahil et grubunun üyesi olsalar dahi, üst **düzey yönetim personelinin** tüm üyeleri ilkeden çıkarılır.

Ekleme, Kullanıcı grubundan cihaza grup veya cihaz grubundan Kullanıcı grubu gibi karma grupları kullanırken dışlamaya göre önceliklidir.

Örneğin, kuruluşunuzdaki tüm kullanıcılara bilgi noktası cihazları dışında bir cihaz profili atamak istiyorsunuz. **Tüm kullanıcılar** grubunu dahil edersiniz, ancak **tüm cihazlar** grubunu dışlayamazsınız. Bu durumda, Kullanıcı aygıtı **tüm cihazlar** grubunda olsa bile, tüm kullanıcılarınız ve cihazlarınız ilkeyi alırlar.

Dışlama yalnızca grubun doğrudan üyelerine bakar. Bir kullanıcıyla ilişkili cihazları içermez. Ancak, bir kullanıcısı olmayan cihazlar, ilke almaz. Bu davranış, kullanıcıları olmayan cihazların **tüm kullanıcılar** grubuyla ilişkisi olmadığı için oluşur.

**Tüm cihazları**dahil ederseniz ve **tüm kullanıcıları**dışladığınızda, tüm cihazlar ilkeyi alır. Bu senaryoda amaç, ilişkili bir kullanıcıya sahip olan cihazları bu ilkeden dışmaktır. Ancak, dışlama yalnızca doğrudan grup üyelerini karşılaştırdığından, cihazları dışmaz.

## <a name="next-steps"></a>Sonraki adımlar

Profillerinizi izlemeye ve profillerinizi çalıştıran cihazlara yönelik yönergeler için bkz. [Cihaz profillerini](device-profile-monitor.md) izleme.
