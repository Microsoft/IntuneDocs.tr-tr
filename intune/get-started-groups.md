---
title: Microsoft Intune’da bir grup oluşturma
titleSuffix: ''
description: Erişebilecekleri ilke ve uygulamaları yönetmeyi kolaylaştırmak için kullanıcıları gruplara ayırın.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 39a93fb5-d318-4997-a409-b64549a00e7a
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: fcf6f3071e50304216a182a21dd542cace1b6390
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52186469"
---
# <a name="create-a-group-to-manage-your-users-and-data-access"></a>Kullanıcılarınızı ve veri erişimini yönetmek için bir grup oluşturma

Gruplar, kullanıcılarınızı yönetmek ve çalışanlarınızın şirket kaynaklarınıza erişimini denetlemek için kullanılır. Bu kaynaklar, dizininizin parçası veya SaaS uygulamaları ya da SharePoint siteleri gibi dış kaynaklar olabilir.

Microsoft Intune, şirket kaynaklarına erişimi yönetmek için Azure Active Directory’yi (Azure AD) kullanır. Bu erişim, dizindeki roller kullanılarak denetlenir. Daha sonra Intune, bu mobil cihazlara erişimi yönetir ve bu grubun üyelerinin kaynaklara erişmesini sağlar.

## <a name="how-do-i-create-a-group"></a>Nasıl bir grup oluştururum?

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Microsoft Intune** bölmesini açtıktan sonra **Gruplar**’ı seçin.
4. **Kullanıcılar ve gruplar – Tüm gruplar** bölmesinde **Yeni grup** komutunu seçin.
5. **Grup** bölmesinde bir **Grup türü** seçin.
5. Grup için bir **Ad** ve **Açıklama** ekleyin.
6. **Üyelik türü**’nü **Atandı** olarak ayarlayın. Sınama grubu için **Office özelliklerini etkinleştir** komutunu seçmeyin.
7. Grup için **Üyeler**’i seçin.
7. **Oluştur**'a tıklayın.

Bir grup başarıyla oluşturulduktan sonra **Tüm gruplar** listesinde yer alır. Grubunuz burada görünmüyorsa başka bir grup oluşturmayı deneyin.

## <a name="next-steps"></a>Sonraki adımlar

[İlkeleri kullanmaya başlama](get-started-policies.md) - Kullanıcıların cihazları ile yetkilendirilmedikleri şeyler yapmasını önlemek için ilkeler oluşturun.

## <a name="learn-more"></a>Daha fazlasını öğrenin

* [Intune’da grupları kullanarak kayıt kısıtlamaları ayarlama](groups-add.md)
* [Azure Active Directory’de grupları kullanarak şirket kaynaklarına erişimi yönetme](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
