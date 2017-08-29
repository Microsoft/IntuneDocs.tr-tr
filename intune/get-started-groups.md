---
title: "Grupları kullanmaya başlama"
titleSuffix: Intune on Azure
description: "Erişebilecekleri ilke ve uygulamaları yönetmeyi kolaylaştırmak için kullanıcıları gruplara ayırın."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 08/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 39a93fb5-d318-4997-a409-b64549a00e7a
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 276a594abdd3c92051041a5faa34d3ee7633e32c
ms.sourcegitcommit: 45204e0fb8cb4cce449e65f2f1d7bb6f6ac4ccf5
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2017
---
# <a name="get-started-with-groups"></a>Grupları kullanmaya başlama

Gruplar, kullanıcılarınızı yönetmek ve çalışanlarınızın şirket kaynaklarınıza erişimini denetlemek için kullanılır. Bu kaynaklar, dizininizin parçası veya SaaS uygulamaları ya da SharePoint siteleri gibi dış kaynaklar olabilir.

Microsoft Intune, şirket kaynaklarına erişimi yönetmek için Azure Active Directory’yi (Azure AD) kullanır. Bu erişim, dizindeki roller kullanılarak denetlenir. Daha sonra Intune, bu mobil cihazlara erişimi yönetir ve bu grubun üyelerinin kaynaklara erişmesini sağlar.

## <a name="how-do-i-create-a-group"></a>Nasıl bir grup oluştururum?

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Kaynak ara**'yı kullanarak **Intune**'u arayın.
3. **Microsoft Intune** dikey penceresini açtıktan sonra **Gruplar**’ı seçin.
4. **Kullanıcılar ve gruplar – Tüm gruplar** dikey penceresinde **Yeni grup** komutunu seçin.
5. **Grup** dikey penceresinde grup için bir **Ad** ve **Açıklama** ekleyin.
6. **Üyelik türü**’nü **Atandı** olarak ayarlayın. Sınama grubu için **Office özelliklerini etkinleştir** komutunu seçmeyin.
7. **Oluştur**'a tıklayın.

Bir grup başarıyla oluşturulduktan sonra **Tüm gruplar** listesinde yer alır. Grubunuz burada görünmüyorsa başka bir grup oluşturmayı deneyin.

## <a name="next-steps"></a>Sonraki adımlar

[İlkeleri kullanmaya başlama](get-started-policies.md) - Kullanıcıların cihazları ile yetkilendirilmedikleri şeyler yapmasını önlemek için ilkeler oluşturun.

## <a name="learn-more"></a>Daha fazlasını öğrenin

* [Intune’da grupları kullanarak kayıt kısıtlamaları ayarlama](groups-add.md)
* [Azure Active Directory’de grupları kullanarak şirket kaynaklarına erişimi yönetme](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
