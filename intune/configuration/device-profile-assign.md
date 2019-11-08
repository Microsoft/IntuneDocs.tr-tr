---
title: Microsoft Intune’da cihaz profilleri atama | Microsoft Docs
description: Kullanıcılara ve cihazlara cihaz profilleri ve ilkeleri atamak için Azure portalını kullanın. Microsoft Intune'da grupları bir profil atamasının dışında tutmayı öğrenin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/05/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f6f5414d-0e41-42fc-b6cf-e7ad76e1e06d
ms.reviewer: altsou
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 50b91251572e45669f197df7ac4e5ff94caf47a1
ms.sourcegitcommit: 1a7f04c80548e035be82308d2618492f6542d3c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73755324"
---
# <a name="assign-user-and-device-profiles-in-microsoft-intune"></a>Microsoft Intune'da kullanıcı ve cihaz profilleri atama

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Bir profil oluşturursunuz ve girdiğiniz tüm ayarlar burada saklanır. Bir sonraki adım, profili Azure Active Directory (Azure AD) kullanıcı veya cihaz gruplarınıza dağıtmak veya "atamaktır". Atanan profiller kullanıcılara ve cihazlara ulaşır ve girdiğiniz ayarlar uygulanır.

Bu makalede profil atama yöntemlerinin yanı sıra profillerinizde kapsam etiketlerini kullanma adımları hakkında bilgilere yer verilmiştir.

> [!NOTE]  
> Bir ilke kaldırıldığında veya bir cihaza artık atanmadıysa, ayar varolan değeri tutabilir. Ayar varsayılan değere dönmez. Ayarı farklı bir değer olarak değiştirmek için yeni bir ilke oluşturun ve atayın.

## <a name="before-you-begin"></a>Başlamadan önce

İlke atamak için uygun role sahip olduğunuzdan emin olun. Daha fazla bilgi için bkz. [Microsoft Intune Ile rol tabanlı erişim denetimi (RBAC)](../fundamentals/role-based-access-control.md).

## <a name="assign-a-device-profile"></a>Bir cihaz profili atama

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. **Yapılandırma profillerinin** > **cihazları** ' nı seçin. Tüm profiller listelenir.
3. Atamak istediğiniz profili ve ardından **Atamalar**'ı seçin.
4. Grupları **Dahil Etmeyi** veya **Dışlamayı** seçin ve sonra da gruplarınızı belirtin. Gruplarınızı seçtiğinizde, bir Azure AD grubu seçersiniz. Birden çok grup seçmek için grupları seçerken **Ctrl** tuşunu basılı tutun.

    ![Grupları bir profil atamasına dahil etme veya atamadan dışlama seçeneklerinin ekran görüntüsü](./media/device-profile-assign/group-include-exclude.png)

5. Yaptığınız değişiklikleri **kaydedin**.

### <a name="evaluate-how-many-users-are-targeted"></a>Kaç kullanıcının hedeflendiğini değerlendirme

Profili atadıktan sonra etkilenen kullanıcı sayısını da **değerlendirebilirsiniz**. Bu özellik, cihaz değil kullanıcı sayısını hesaplar.

1. Yönetim merkezinde **cihazlar** > **yapılandırma profilleri**' ni seçin.
2. Bir profil seçip **Atamalar** > **Değerlendir** yolunu izleyin. Bu profilin kaç kullanıcıyı hedeflediğini gösteren bir ileti görüntülenir.

**Değerlendir** düğmesi gri gösteriliyorsa, profilin bir veya birden fazla gruba atandığından emin olun.

## <a name="use-scope-tags-or-applicability-rules"></a>Kapsam etiketlerini veya uygulanabilirlik kurallarını kullanma

Bir profil oluşturduğunuzda veya güncelleştirdiğinizde, profile kapsam etiketleri ve Uygulanabilirlik kuralları da ekleyebilirsiniz.

**Kapsam etiketleri**, ilkeleri İnsan Kaynakları veya Merkez ofis çalışanları gibi belirli gruplara atamak ve filtreleme yapmak için kullanabileceğiniz bir yöntemdir. Daha fazla bilgi için bkz. [Dağıtılmış BT için RBAC ve kapsam etiketlerini kullanma](../fundamentals/scope-tags.md).

Windows 10 cihazlarında, profil yalnızca belirli bir işletim sistemi sürümü veya belirli bir Windows sürümü için geçerli olacak şekilde **uygulanabilirlik kuralları** ekleyebilirsiniz. [Uygulanabilirlik kurallarında](device-profile-create.md#applicability-rules) daha fazla bilgi bulunur.

## <a name="exclude-groups-from-a-profile-assignment"></a>Grupları bir profil atamasından dışlama

Intune cihaz yapılandırma profilleri, ilke atamasından grupları eklemenizi ve dışlanmasını sağlar.

En iyi uygulama olarak, Kullanıcı gruplarınız için özel ilkeler oluşturun ve atayın. Ve, özel olarak cihaz gruplarınız için farklı ilkeler oluşturun ve atayın. Gruplar hakkında daha fazla bilgi için bkz. [kullanıcıları ve cihazları düzenlemek için grup ekleme](../fundamentals/groups-add.md).

İlkelerinizi atadığınızda, grupları dahil etmek ve dışlamak için aşağıdaki tabloyu kullanın. Onay işareti, atamanın desteklendiği anlamına gelir:

![Desteklenen seçenekler bir profil atamasında grupları içerir veya hariç tutar](./media/device-profile-assign/include-exclude-user-device-groups.png)

### <a name="what-you-should-know"></a>Bilmeniz gerekenler

- Dışlama, aşağıdaki aynı grup türü senaryolarına dahil edilmeye göre önceliklidir:

  - Kullanıcı gruplarını dahil etme ve Kullanıcı gruplarını hariç tutma
  - Cihaz gruplarını ekleme ve cihaz grubunu hariç tutma

  Örneğin, **tüm kurumsal kullanıcılar** kullanıcı grubuna bir cihaz profili atarsınız, ancak üst **düzey yönetim personeli** Kullanıcı grubundaki üyeleri dışlayabilirsiniz. Her iki grup da Kullanıcı grupları olduğundan, üst **düzey yönetim personeli** hariç **tüm kurumsal kullanıcılar** ilkeyi alır.

- Intune, Kullanıcı-cihaz grubu ilişkilerini değerlendirmez. Karışık gruplara ilke atarsanız, sonuçlar istediğiniz veya beklediğiniz gibi olabilir.

  Örneğin, **tüm kullanıcılar** kullanıcı grubuna bir cihaz profili atarsınız, ancak **tüm kişisel cihazlar** cihaz grubunu dışlayamazsınız. Bu karma Grup İlkesi atamasında, **tüm kullanıcılar** ilkeyi alır. Dışlama uygulanmaz.

  Sonuç olarak, karışık gruplara ilke atanması önerilmez.

## <a name="next-steps"></a>Sonraki adımlar

Profillerinizi ve profillerinizin çalıştığı cihazları izleme konusunda bilgi için bkz. [Cihaz profillerini izleme](device-profile-monitor.md).
