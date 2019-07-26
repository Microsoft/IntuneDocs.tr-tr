---
title: Hızlı Başlangıç - Kullanıcıları yönetmek için grup oluşturma
titleSuffix: Microsoft Intune
description: Bu hızlı başlangıçta mevcut kullanıcılara dayanan bir grup oluşturmak için Microsoft Intune kullanacaksınız.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/24/2019
ms.topic: quickstart
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 723f4b4e-3090-4811-84ff-6af652abea5a
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8a8a444f886a5b754fd6ba3763e183db0fe95d5f
ms.sourcegitcommit: d2ac912b834c4840de9cc92ba1815b6ecfbfb52b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/25/2019
ms.locfileid: "68482978"
---
# <a name="quickstart-create-a-group-to-manage-users"></a>Hızlı başlangıç Kullanıcıları yönetmek için bir grup oluşturma

Bu hızlı başlangıçta mevcut bir kullanıcıya dayanan bir grup oluşturmak için Intune kullanacaksınız. Gruplar, kullanıcılarınızı yönetmek ve çalışanlarınızın şirket kaynaklarınıza erişimini denetlemek için kullanılır. Bu kaynaklar şirketinizin intranetinin bir parçası veya SharePoint siteleri, SaaS uygulamaları ve web uygulamaları gibi dış kaynaklar olabilir.

Bir Intune aboneliğiniz yoksa [ücretsiz bir deneme hesabı için kaydolun](free-trial-sign-up.md).

>[!NOTE]
>Intune size kolaylık sağlamak adına konsolda önceden oluşturulmuş ve yerleşik iyileştirmeleri bulunan **Tüm Kullanıcılar** ve **Tüm Cihazlar** gruplarını sağlar.

## <a name="prerequisites"></a>Önkoşullar

- Bu hızlı başlangıcı tamamlamak için [bir kullanıcı oluşturmanız](quickstart-create-user.md) gerekir.

## <a name="sign-in-to-intune"></a>Intune'da oturum açma

[Intune portalında](https://aka.ms/intuneportal) [genel yönetici veya Intune Hizmet Yöneticisi](users-add.md#types-of-administrators)olarak oturum açın. Intune Deneme aboneliği oluşturduysanız aboneliği oluşturduğunuz hesap Genel yönetici rolüne sahip olur.

## <a name="create-a-group"></a>Grup oluşturma

Daha sonra bu hızlı başlangıç serisinde kullanılacak bir grup oluşturacaksınız. Bir grup oluşturmak için:

1. **Microsoft Intune** bölmesini açtığınızda **Gruplar** > **Yeni grup**'u seçin.
2. Açılan **Grup türü** kutusunda **Güvenlik**’i seçin.
3. **Grup adı** alanına yeni grup için bir ad girin (örneğin, **contoso Sınayıcılar**).
4. Grup için bir **Açıklama** ekleyin.
5. **Üyelik türü**’nü **Atandı** olarak ayarlayın. 
6. **Üyeler** ' e tıklayın ve listeden Grup için bir veya daha fazla üye seçin.

    ![Microsoft Intune'da grup oluşturma işleminin ekran görüntüsü](./media/quickstart-use-groups-01.png)

7. **Seç** > **Oluştur**’a tıklayın.

Grup başarıyla oluşturulduğunda **Tüm gruplar** listesinde görünür. 

## <a name="next-steps"></a>Sonraki adımlar

Bu hızlı başlangıçta mevcut bir kullanıcıya dayanan bir grup oluşturmak için Intune kullanacaksınız. Intune’a grup ekleme hakkında daha fazla bilgi için bkz. [Kullanıcıları ve cihazları düzenlemek için grup ekleme](groups-add.md).

Bu Intune hızlı başlangıç serisini takip etmek için bir sonraki hızlı başlangıca ilerleyin.

> [!div class="nextstepaction"]
> [Hızlı başlangıç Windows 10 cihazları için otomatik kaydı ayarlama](quickstart-setup-auto-enrollment.md)
