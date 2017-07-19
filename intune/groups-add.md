---
title: "Intune’da kayıt kısıtlamalarını ayarlama"
titleSuffix: Intune on Azure
description: "Intune’da platforma göre kaydı kısıtlama ve cihaz kayıt sınırı ayarlama. \""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f0a2b858-a824-4598-ab81-bdd8e62ac3b3
ms.reviewer: amyros
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2c9d10e4e2a1d2a745b9e327bf9a8a9cd99e5ce4
ms.sourcegitcommit: fd5b7aa26446d2fa92c21638cb29371e43fe169f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2017
---
# <a name="add-groups-in-intune"></a>Intune’a grup ekleme
Intune, cihaz ve kullanıcıları yönetmek için Azure Active Directory (AD) gruplarını kullanır. Bir Intune yöneticisi olarak grupları, kuruluş gereksinimlerinize uyacak şekilde ayarlayabilirsiniz. Kullanıcı veya cihazları coğrafi konum, departman veya donanım özelliklerine göre düzenlemek için grup oluşturun. Büyük ölçekli görevleri yönetmek için grupları kullanın. Örneğin pek çok kullanıcı için ilkeler ayarlayabilir veya bir cihaz kümesine uygulamalar dağıtabilirsiniz.

Bu konuda, Intune'da kullanmak üzere nasıl grup ekleyeceğiniz açıklanmaktadır.

Aşağıdaki grup türlerini ekleyebilirsiniz:
- **Atanan gruplar** - Kullanıcı veya cihazları statik bir gruba el ile ekleme
- **Dinamik gruplar** - (Azure Active Directory Premium) Basit veya gelişmiş kurallarla tanımlanan kullanıcı veya cihaz gruplarını dinamik olarak derleme

## <a name="add-a-new-group"></a>Yeni bir grup ekleme

Yeni bir grup oluşturmak için aşağıdaki adımları kullanın.
1. Intune portalında **Gruplar**’a gidin ve sonra **Tüm gruplar** dikey penceresinde **Yeni grup**’u seçin.
  ![Yeni Grubun seçili olduğu Intune portalı ekran görüntüsü](./media/groups-add-new.png)
2. Yeni grup için **Ad** ve **Açıklama** belirtin. Bu özellikler, yalnızca Intune portalında görüntülenir ve kullanıcılara gösterilmez.

3. **Üyelik türü** seçin:
  - **Atanan** üyelik türünde, oluşturacağınız gruba üyeleri el ile atarsınız. [Azure AD atanan grupları](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal) hakkında daha fazla bilgi edinin.
  - **Dinamik Kullanıcı** üyelik türünde, **Dinamik sorgu** ile tanımlanan bir kullanıcı grubu oluşturursunuz.
  - **Dinamik Cihaz** üyelik türünde, **Dinamik sorgu** ile tanımlanan bir cihaz grubu oluşturursunuz.

  ![Ad, Açıklama, Üyelik türü, Office özelliklerini etkinleştir ve Üyeler ile Intune grubu özellikleri ekran görüntüsü](./media/groups-add-properties.png)

  Azure AD, üyeliği tanımlayan kurallara dayalı dinamik gruplar oluşturmanıza imkan verir. [Öznitelik tabanlı dinamik gruplar oluşturmayı](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) öğrenin.

4. **Office özelliklerini etkinleştir** ayarını seçerek grup üyelerine paylaşılan Office 365 uygulamaları için erişim sağlarsınız.
5. Yeni grubu eklemek için **Oluştur**’u seçin.

## <a name="see-also"></a>Ayrıca bkz.
[Azure Active Directory grupları ile kaynaklara erişimi yönetme](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
[Azure portalında klasik Intune grupları](groups-get-started.md)
