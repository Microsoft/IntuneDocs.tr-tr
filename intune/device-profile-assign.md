---
title: Intune ile cihaz profilleri atama
titlesuffix: Azure portal
description: "Intune cihaz profilini oluşturduktan sonra, bu profili cihazlara atamayı öğrenmek için bu konuyu kullanın.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f6f5414d-0e41-42fc-b6cf-e7ad76e1e06d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 36b967ac740cc2f39d631c17556f73abb9f2f785
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/09/2017
---
# <a name="how-to-assign-microsoft-intune-device-profiles"></a>Microsoft Intune cihaz profillerini atama

## <a name="assign-a-device-profile"></a>Bir cihaz profili atama

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihaz yapılandırması**’nı seçin.
1. **Cihaz yapılandırması** dikey penceresinde **Yönet** > **Profiller**’i seçin.
2. Profil listesi dikey penceresinde yönetmek istediğiniz profili seçin ve ardından <*profil adı*> **Raporlar** dikey penceresinde **Yönet** > **Atamalar**’ı seçin.
3. Gelecek dikey pencerede **Dahil et** (grupları dahil etmek için) veya **Dışla** (grupları dışlamak için) seçeneklerinden birini belirtin, daha sonra **Grup seç**’e tıklayın.
![Grupları bir profil atamasına dahil etme veya atamadan dışlama](./media/group-include-exclude.png)
4. **Grup seç** dikey penceresinde, atamaya dahil etmek veya atamadan dışlamak istediğiniz Azure AD gruplarını seçin. **CTRL** tuşunu basılı tutarak birden çok grup seçebilirsiniz.
4. Bitirdiğinizde, **Grupları seçin** dikey penceresinde **Seç** düğmesini seçin.



## <a name="how-to-exclude-groups-from-a-device-profile-assignment"></a>Grupları bir cihaz profil atamasından dışlama

Intune cihaz yapılandırma profilleri, grupları ilke atamasından dışlamanıza olanak tanır. Örneğin **Tüm şirket kullanıcıları** grubuna bir cihaz profili atayabilir ve **Üst Düzey Yönetim Kadrosu** grubundan istediğiniz üyeleri dışlayabilirsiniz.

Bir atamadan grupları dışlarken yalnızca kullanıcı veya yalnızca cihaz gruplarını dışlayın, grupları karışık olarak dışlamayın. Intune, grupları dışlarken kullanıcı cihaz ilişkisini göz önünde bulundurmaz. Kullanıcı gruplarını dahil ederken cihaz gruplarını dışlamak, istediğiniz sonuçları vermeyebilir. Karışık gruplar kullanmanız veya başka çakışmaların ortaya çıkması durumunda, dahil etme işleminin dışlama işlemine önceliği vardır.

Örneğin kuruluşunuzda bilgi noktası cihazları hariç tüm cihazlara cihaz profilleri atamak istiyorsunuz. Bunun için **Tüm Kullanıcılar** grubunu dahil edip **Tüm Cihazlar** grubunu dışlıyorsunuz.

Bu durumda, cihazı **Tüm Cihazlar** grubunun parçası olan kullanıcılar bile dahil olmak üzere tüm kullanıcılarınız ve onların cihazları bu ilkeyi alır. 

Dışlama işlemi yalnızca grupların doğrudan üyesi olanları değerlendirmeye alır ve bir kullanıcıyla ilişkili cihazları dikkate almaz. Ancak kullanıcısı olmayan cihazlar bu ilkeyi almaz çünkü bu cihazların **Tüm Kullanıcılar** grubuyla bir ilişkisi yoktur. 

**Tüm Cihazlar** grubunu dahil edip **Tüm Kullanıcılar** grubunu dışlarsanız ilkeyi tüm gruplar alacaktır. Bu örnekteki amaç, ilişkili kullanıcısı olan cihazları bu ilkeden dışlamaktır. Ancak cihazlar dışlanamaz çünkü dışlama özelliği, yalnızca grupların doğrudan üyesi olanları hesaba katar. 

>[!Tip]
>Dışlama özelliği, uyumluluk ilkeleri ve uygulama atama için şu anda kullanılabilir değildir. Üyeleri bir atamadan dışlamak için Kullanılabilir ve Uygulanamaz atama amaçlarını kullanabilirsiniz. Örneğin bir uygulamayı **Kullanılabilir** amacıyla **Tüm şirket kullanıcıları** grubuna, **Uygulanamaz** amacıyla **Üst Düzey Yönetim Kadrosu** grubuna atarsanız uygulama, **Üst Düzey Yönetim Kadrosu** grubundaki kullanıcılar *hariç* tüm kullanıcılara atanır. Uygulamayı **Gerekli** amacıyla **Tüm şirket kullanıcıları** grubuna atarsanız **Üst Düzey Yönetim Kadrosu** grubundaki kullanıcılar dışlanmaz.
 
    
## <a name="next-steps"></a>Sonraki adımlar
Cihaz profili atamalarını izlemenize yardımcı olacak bilgiler için bkz. [Cihaz profillerini izleme](device-profile-monitor.md).
