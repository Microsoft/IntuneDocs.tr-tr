---
title: Hızlı Başlangıç - Kullanıcıları yönetmek için grup oluşturma
titleSuffix: Microsoft Intune
description: Bu hızlı başlangıçta mevcut kullanıcılara dayanan bir grup oluşturmak için Microsoft Intune kullanacaksınız.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/25/2019
ms.topic: quickstart
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 723f4b4e-3090-4811-84ff-6af652abea5a
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7cbfe19e4f7aea28c16cae50c9b79336be81c8fa
ms.sourcegitcommit: 79baf89e4a7a7b1cecb8ccf5cb976736ae6a7286
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58871336"
---
# <a name="quickstart-create-a-group-to-manage-users"></a>Hızlı Başlangıç: Kullanıcıları yönetmek için bir grup oluşturun

Bu hızlı başlangıçta mevcut bir kullanıcıya dayanan bir grup oluşturmak için Intune kullanacaksınız. Gruplar, kullanıcılarınızı yönetmek ve çalışanlarınızın şirket kaynaklarınıza erişimini denetlemek için kullanılır. Bu kaynaklar şirketinizin intranetinin bir parçası veya SharePoint siteleri, SaaS uygulamaları ve web uygulamaları gibi dış kaynaklar olabilir.

Bir Intune aboneliğiniz yoksa [ücretsiz bir deneme hesabı için kaydolun](free-trial-sign-up.md).

>[!NOTE]
>Intune size kolaylık sağlamak adına konsolda önceden oluşturulmuş ve yerleşik iyileştirmeleri bulunan **Tüm Kullanıcılar** ve **Tüm Cihazlar** gruplarını sağlar.

## <a name="prerequisites"></a>Önkoşullar

- Bu hızlı başlangıcı tamamlamak için [bir kullanıcı oluşturmanız](quickstart-create-user.md) gerekir.

## <a name="sign-in-to-intune"></a>Intune'da oturum açma

Oturum [Intune portalı](https://aka.ms/intuneportal) olarak bir [genel yönetici veya Intune Hizmet Yöneticisi](users-add.md#types-of-administrators). Intune Deneme aboneliği oluşturduysanız aboneliği oluşturduğunuz hesap Genel yönetici rolüne sahip olur.

## <a name="create-a-group"></a>Grup oluşturma

Daha sonra bu hızlı başlangıç serisinde kullanılacak bir grup oluşturacaksınız. Bir grup oluşturmak için:

1. **Microsoft Intune** bölmesini açtığınızda **Gruplar** > **Yeni grup**'u seçin.
2. Açılan **Grup türü** kutusunda **Güvenlik**’i seçin.
3. İçinde **grup adı** alanında, yeni grup adını girin (örneğin, **Contoso sınayıcılar**).
4. Ekleme bir **açıklama** grubu için.
5. **Üyelik türü**’nü **Atandı** olarak ayarlayın. 
6. Tıklayın **üyeleri** ve listeden bir veya daha fazla grup üyelerini seçin.

    ![Microsoft Intune'da grup oluşturma işleminin ekran görüntüsü](./media/quickstart-use-groups-01.png)

7. **Seç** > **Oluştur**’a tıklayın.

Grup başarıyla oluşturulduğunda **Tüm gruplar** listesinde görünür. 

## <a name="next-steps"></a>Sonraki adımlar

Bu hızlı başlangıçta mevcut bir kullanıcıya dayanan bir grup oluşturmak için Intune kullanacaksınız. Intune’a grup ekleme hakkında daha fazla bilgi için bkz. [Kullanıcıları ve cihazları düzenlemek için grup ekleme](groups-add.md).

Bu Intune hızlı başlangıç serisini takip etmek için bir sonraki hızlı başlangıca ilerleyin.

> [!div class="nextstepaction"]
> [Hızlı Başlangıç: Windows 10 cihazları için otomatik kaydını ayarlama](quickstart-setup-auto-enrollment.md)
