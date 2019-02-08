---
title: Hızlı Başlangıç - Kullanıcıları yönetmek için grup oluşturma
titlesuffix: Microsoft Intune
description: Bu hızlı başlangıçta mevcut kullanıcılara dayanan bir grup oluşturmak için Microsoft Intune kullanacaksınız.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/11/2019
ms.topic: quickstart
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 723f4b4e-3090-4811-84ff-6af652abea5a
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 95db6ca8cbcb6e4e80b549b26a352c748f20c7f5
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55847226"
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

Daha sonra bu hızlı başlangıç serisinde kullanılacak bir grup oluşturacaksınız.

1. **Microsoft Intune** bölmesini açtığınızda **Gruplar** > **Yeni grup**'u seçin.
2. Açılan **Grup türü** kutusunda **Güvenlik**’i seçin.
3. **Ad**'ı "Contoso Testers" olarak ayarlayın ve grup için bir **Açıklama** girin.
4. **Üyelik türü**’nü **Atandı** olarak ayarlayın. 
5. **Üyeler**’e tıklayın ve mevcut listeden grup için bir veya daha fazla üye seçin.

    ![Microsoft Intune'da grup oluşturma işleminin ekran görüntüsü](./media/quickstart-use-groups-01.png)

6. **Seç** > **Oluştur**’a tıklayın.

Grup başarıyla oluşturulduğunda **Tüm gruplar** listesinde görünür. 

## <a name="next-steps"></a>Sonraki adımlar

Bu hızlı başlangıçta mevcut bir kullanıcıya dayanan bir grup oluşturmak için Intune kullanacaksınız. Intune’a grup ekleme hakkında daha fazla bilgi için bkz. [Kullanıcıları ve cihazları düzenlemek için grup ekleme](groups-add.md).

Bu Intune hızlı başlangıç serisini takip etmek için bir sonraki hızlı başlangıca ilerleyin.

> [!div class="nextstepaction"]
> [Hızlı Başlangıç: Windows 10 cihazları için otomatik kaydını ayarlama](quickstart-setup-auto-enrollment.md)
