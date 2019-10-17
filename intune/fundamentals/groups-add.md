---
title: Kullanıcıları ve cihazları düzenlemek için grup ekleme
titleSuffix: Microsoft Intune
description: Kullanıcıları ve cihazları coğrafi konum, bölüm veya donanım belirtimlerine göre düzenlemek için gruplar ekleyin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/13/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f0a2b858-a824-4598-ab81-bdd8e62ac3b3
ms.reviewer: altsou
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0702eebdd3899c6da527af0078e5e7d47cf95194
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72510243"
---
# <a name="add-groups-to-organize-users-and-devices"></a>Kullanıcıları ve cihazları düzenlemek için grup ekleme
Intune, cihaz ve kullanıcıları yönetmek için Azure Active Directory (AD) gruplarını kullanır. Bir Intune yöneticisi olarak grupları, kuruluş gereksinimlerinize uyacak şekilde ayarlayabilirsiniz. Kullanıcı veya cihazları coğrafi konum, departman veya donanım özelliklerine göre düzenlemek için grup oluşturun. Büyük ölçekli görevleri yönetmek için grupları kullanın. Örneğin pek çok kullanıcı için ilkeler ayarlayabilir veya bir cihaz kümesine uygulamalar dağıtabilirsiniz.

Aşağıdaki grup türlerini ekleyebilirsiniz:
- **Atanan gruplar** - Kullanıcı veya cihazları statik bir gruba el ile ekleme
- **Dinamik gruplar** - (Azure Active Directory Premium kullanarak) Basit veya gelişmiş kurallarla tanımlanan kullanıcı veya cihaz gruplarını dinamik olarak derlemenize imkan tanır

## <a name="add-a-new-group"></a>Yeni bir grup ekleme

Yeni bir grup oluşturmak için aşağıdaki adımları kullanın.
1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
3. **Intune** bölmesinde, **Gruplar**’ı, ardından da **Tüm gruplar** bölmesinde **Yeni grup**’u seçin.
   ![Yeni Grup seçeneğinin belirlendiği Intune portalı ekran görüntüsü](./media/groups-add/groups-add-new.png)
4. **Grup türü**için, aşağıdaki seçeneklerden birini seçin:
    - **Güvenlik**: güvenlik grupları, Kullanıcı gruplarını doldurduğunuzda kullanılacak iyi bir kaynaktır. Güvenlik gruplarınız kimlerin hangi kaynaklara erişiminin olacağını tanımladığından, güvenlik grupları iyi bir şekilde Intune kullanıcı gruplarına çevrilebilir. Active Directory 'ten Azure Active Directory veya Azure Active Directory doğrudan Microsoft 365 Yönetim Azure portal merkezi aracılığıyla oluşturduğunuz ya da Intune 'da Kullanıcı grupları oluştururken kullanabileceğiniz güvenlik grupları.
    - **Office 365**

5. Yeni grup için bir **ad** ve **Açıklama** yazın. Bu özellikler, yalnızca yönetim portalında görüntülenir ve kullanıcılara gösterilmez.

6. **Üyelik türü** seçin:
   - **Atanan** üyelik türünde, oluşturacağınız gruba üyeleri el ile atarsınız. [Azure AD atanan grupları](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal) hakkında daha fazla bilgi edinin.
   - **Dinamik Kullanıcı** üyelik türünde, **Dinamik sorgu** ile tanımlanan bir kullanıcı grubu oluşturursunuz.
   - **Dinamik Cihaz** üyelik türünde, **Dinamik sorgu** ile tanımlanan bir cihaz grubu oluşturursunuz.

   ![Intune grup özelliklerinin ekran görüntüsü](./media/groups-add/groups-add-properties.png)

   Azure AD, üyeliği tanımlayan kurallara dayalı dinamik gruplar oluşturmanıza imkan verir. [Öznitelik tabanlı dinamik gruplar oluşturmayı](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) öğrenin.

7. **Office özelliklerini etkinleştir** ayarını seçerek grup üyelerine paylaşılan Office 365 uygulamaları için erişim sağlarsınız. [Office 365 Grupları](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2) hakkında daha fazla bilgi edinin.
8. Yeni grubu eklemek için **Oluştur**’u seçin.

## <a name="groups-and-policies"></a>Gruplar ve ilkeler

Grupları oluştururken, [ilkeleri](../protect/device-compliance-get-started.md)nasıl uygulayacağınızı düşünün. Örneğin, cihaz işletim sistemine özgü ilkeleriniz veya Active Directory’de zaten tanımlamış olduğunuz kuruluşunuzdaki farklı rollere veya kuruluş birimlerine özgü ilkeleriniz olabilir. iOS, Android ve Windows için ayrı cihaz gruplarına ve her bir kurumsal rol için kullanıcı gruplarına sahip olmak yararlı olabilir.

Ayrıca kuruluşunuzun temel uyumluluk gereksinimlerini belirlemek için tüm gruplara ve cihazlara uygulanan varsayılan bir ilke oluşturmak isteyebilirsiniz. Ardından, en geniş kullanıcı ve cihaz kategorileri için daha özel ilkeler oluşturabilirsiniz. Örneğin, her cihaz işletim sistemi için e-posta ilkeleri oluşturabilirsiniz.



## <a name="see-also"></a>Ayrıca bkz:
- [Azure Active Directory grupları ile kaynaklara erişimi yönetme](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
- [Azure portalında klasik Intune grupları](groups-get-started.md)
