---
title: Hızlı Başlangıç - Kullanıcıları yönetmek için grup oluşturma
titlesuffix: Microsoft Intune
description: Bu hızlı başlangıçta mevcut kullanıcılara dayanan bir grup oluşturmak için Microsoft Intune kullanacaksınız.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/21/2018
ms.topic: quickstart
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 723f4b4e-3090-4811-84ff-6af652abea5a
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3a4468f2e6919349095d934790740afc8c347282
ms.sourcegitcommit: 27eed5aba5c8bfafb079171081b68f75a6cbffaf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/22/2018
ms.locfileid: "46581799"
---
# <a name="quickstart-create-a-group-to-manage-users"></a>Hızlı Başlangıç: Kullanıcıları yönetmek için grup oluşturma

Bu hızlı başlangıçta mevcut bir kullanıcıya dayanan bir grup oluşturmak için Intune kullanacaksınız. Gruplar, kullanıcılarınızı yönetmek ve çalışanlarınızın şirket kaynaklarınıza erişimini denetlemek için kullanılır. Bu kaynaklar şirketinizin intranetinin bir parçası veya SharePoint siteleri, SaaS uygulamaları ve web uygulamaları gibi dış kaynaklar olabilir.

Bir Intune aboneliğiniz yoksa [ücretsiz bir deneme hesabı için kaydolun](free-trial-sign-up.md).

>[!NOTE]
>Intune size kolaylık sağlamak adına konsolda önceden oluşturulmuş ve yerleşik iyileştirmeleri bulunan **Tüm Kullanıcılar** ve **Tüm Cihazlar** gruplarını sağlar.

## <a name="prerequisites"></a>Önkoşullar

- Bu hızlı başlangıcı tamamlamak için [bir kullanıcı oluşturmanız](quickstart-create-user.md) gerekir.

## <a name="sign-in-to-intune"></a>Intune'da oturum açma

[Intune](https://aka.ms/intuneportal)'da Genel Yönetici veya Intune Hizmet Yöneticisi olarak oturum açın. Intune, Azure portalında **Tüm hizmetler** > **Intune** seçilerek bulunur. Intune, **İzleme + Yönetim** bölümünde bulunur.

## <a name="create-a-group"></a>Grup oluşturma
1. **Microsoft Intune** bölmesini açtığınızda **Gruplar** > **Yeni grup**'u seçin.
2. **Grup** bölmesinde **Grup türü** > **Güvenlik**'i seçin.
3. **Ad**'ı "Contoso Testers" olarak ayarlayın ve grup için bir **Açıklama** girin.
4. **Üyelik türü**’nü **Atandı** olarak ayarlayın. 
5. **Üyeler**'e tıklayın ve mevcut listeden grup için **Üyeler** seçin.

    ![Microsoft Intune'da grup oluşturma işleminin ekran görüntüsü](./media/quickstart-use-groups-01.png)

6. **Seçin**’e tıklayın.
7. **Oluştur**'a tıklayın.

Başarıyla oluşturduysanız grup **Tüm gruplar** listesinde görünür. 

## <a name="next-steps"></a>Sonraki adımlar

Bu hızlı başlangıçta mevcut bir kullanıcıya dayanan bir grup oluşturmak için Intune kullanacaksınız.

> [!div class="nextstepaction"]
> [Cihaz uyumluluğu ilkesi oluşturma](quickstart-create-policy.md)
