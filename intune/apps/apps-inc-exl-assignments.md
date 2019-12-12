---
title: Microsoft Intune’da uygulama atamalarını dahil etme ve dışlama
titleSuffix: ''
description: Uygulama atamalarını dahil etmek ve dışlamak için Microsoft Intune’u nasıl kullanabileceğinizi öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: c59f6df5-3317-4dff-8f19-fdeec33faedf
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 40cbb62a620d6e174ab8acb76798ba53080b78cf
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74563973"
---
# <a name="include-and-exclude-app-assignments-in-microsoft-intune"></a>Microsoft Intune’da uygulama atamalarını dahil etme ve dışlama

Intune'da, dahil etmek ve dışlamak üzere kullanıcı gruplarını atayarak bir uygulamaya kimin erişebileceğini belirleyebilirsiniz. Uygulamaya grupları atamadan önce uygulamanın atama türünü ayarlamanız gerekir. Atama türü uygulamayı kullanılabilir veya gerekli duruma getirir ya da kaldırır. 

Uygulamanın kullanılabilirliğini ayarlamak için, bir dahil etme ve dışlama grup atamaları bileşimi kullanarak bir kullanıcı veya cihaz grubuna uygulama atamalarını dahil edebilir veya dışlayabilirsiniz. Bu özellik, büyük bir grubu dahil ederek uygulamayı sunup daha sonra küçük bir grubu dışlayarak seçili kullanıcıları azalttığınızda kullanışlı olabilir. Bu küçük grup, bir test grubu veya yönetici grubu olabilir. 

En iyi uygulama olarak, özel olarak Kullanıcı gruplarınız için uygulamalar oluşturup, cihaz gruplarınız için ayrı olarak atayın. Gruplar hakkında daha fazla bilgi için bkz. [kullanıcıları ve cihazları düzenlemek için grup ekleme](~/fundamentals/groups-add.md).  

Uygulama atamalarını dahil etmek veya hariç bırakmak için önemli senaryolar vardır:

- Dışlama, aşağıdaki aynı grup türü senaryolarına dahil edilmeye göre önceliklidir:
    - Uygulama atarken Kullanıcı gruplarını ve Kullanıcı gruplarını dışlayarak ekleme
    - Uygulama atarken cihaz gruplarını ekleme ve cihaz grubunu hariç tutma

    Örneğin, **tüm kurumsal kullanıcılar Kullanıcı** grubuna bir cihaz grubu atarsanız, ancak üst **düzey yönetim personeli** Kullanıcı grubundaki üyeleri dışladığınızda, üst **düzey yönetim personeli** hariç **tüm kurumsal kullanıcılar** atama alır, çünkü her iki grup da kullanıcı gruplarıdır.
- Intune, Kullanıcı-cihaz grubu ilişkilerini değerlendirmez. Uygulamaları karışık gruplara atarsanız, sonuçlar istediğiniz gibi olabilir veya beklenmez.

    Örneğin, **tüm kullanıcılar** kullanıcı grubuna bir cihaz grubu atarsanız, ancak **tüm kişisel cihazlar** cihaz grubunu dışlayabilirsiniz. Bu karma Grup uygulaması atamasında, **tüm kullanıcılar** uygulamayı alır. Dışlama uygulanmaz.

Sonuç olarak, karışık gruplara uygulama atanması önerilmez.

> [!NOTE]
> Bir uygulama için grup ataması ayarlarken, **Uygulanamaz** türü kullanım dışıdır ve bunun yerini grup dışlama işlevi almıştır. 
>
> Intune konsolda önceden oluşturulmuş **Tüm Kullanıcılar** ve **Tüm Cihazlar** gruplarını sağlar. Size kolaylık sağlamak için grupların yerleşik iyileştirmeleri vardır. Tüm kullanıcı ve cihazları hedeflemek için kendi oluşturabileceğiniz "tüm kullanıcılar" veya "tüm cihazlar" grupları yerine bu grupları kullanmanızı kesinlikle öneririz.  
>
> Android kurumsal, grupları dahil etmeyi ve dışlamayı destekler. Android kurumsal uygulama ataması için yerleşik **Tüm Kullanıcılar** ve **Tüm Cihazlar** gruplarından yararlanabilirsiniz. 

## <a name="include-and-exclude-groups-when-assigning-apps"></a>Uygulama atarken grupları dahil etme ve dışlama 
Dahil etme ve dışlama atamasını kullanarak gruplara uygulama atamak için:
1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. **Tüm uygulamalar** > **uygulamalar** ' ı seçin. Eklenen uygulamalar listesi gösterilir.
3. Atamak istediğiniz uygulamayı seçin. Bir panoda uygulama hakkındaki bilgiler görüntülenir. 
4. Menünün **Yönet** bölümünde **Atamalar**’ı seçin. 

    ![Uygulama atarken uygulama atamalarını dahil etme](./media/apps-inc-exl-assignments/apps-inc-exl-01.png)

5. **Grup ekle**’yi seçerek uygulamaya atanmış kullanıcı gruplarını ekleyin. 
6. **Grup ekle** bölmesindeki kullanılabilir atama türlerinden bir **Atama türü** seçin.
7. Atama türü olarak **Kayıtlı veya kayıtsız olarak kullanılabilir**’i seçin.

    ![Intune uygulama atamaları - Grup ekle](./media/apps-inc-exl-assignments/apps-inc-exl-02.png)
8. **Dahil Edilen Gruplar**’a tıklayarak bu uygulamaya erişmesini istediğiniz kullanıcı gruplarını seçin.

    > [!NOTE]
    > Grup eklerken, belirli bir atama türü için başka bir grup önceden dahil edilmişse, uygulama diğer dahil etme atama türleri için önceden seçilmiştir ve değiştirilemez. Kullanılmış olan grup, dahil edilmiş bir grup olarak kullanılamaz.

9. **Evet**’i seçerek bu uygulamayı tüm kullanıcılar için kullanılabilir yapın.

    ![Intune uygulama atamaları - Grup dahil et](./media/apps-inc-exl-assignments/apps-inc-exl-03.png)
10. Dahil edilecek grubu ayarlamak için **Tamam**’ı seçin.
11. **Dışlanan Gruplar**’a tıklayarak bu uygulamaya erişmesini istemediğiniz kullanıcı gruplarını seçin. 
12. Dışlanacak grupları seçin. Bu işlem, bu uygulamanın söz konusu gruplar için kullanılamaz olmasını sağlar.

    ![Intune uygulama atamaları - Grup dışla](./media/apps-inc-exl-assignments/apps-inc-exl-04.png)
13. **Seç**’i seçerek grup seçiminizi tamamlayın.
14. **Grup ekle** bölmesinde **Tamam**’ı seçin. Uygulamanın **Atamalar** listesi görüntülenir.
15. **Kaydet**’e tıklayarak uygulama için grup atamalarınızı etkinleştirin.

Grup atamaları yaparken, zaten atanmış olan gruplar değiştirilemez. Şu anda kullanılamaz durumda olan bir grubu seçmek isterseniz, önce uygulamanın atanmış listesinden uygulamayı kaldırın. 

Atamaları düzenlemek için, uygulamanın **Atamalar** listesinde değiştirmek istediğiniz atamayı içeren satırı seçin. Ayrıca, satırın sonundaki üç noktayı ( **…** ) ve sonra da **Kaldır**'ı seçerek de atamayı kaldırabilirsiniz. **Atamalar** listesinin görünümünü değiştirmek için **Atama türü**’ne veya **Dahil edilen/Dışlanan**’a göre gruplandırın.

![Intune uygulama atamaları - Tamamlandı](./media/apps-inc-exl-assignments/apps-inc-exl-05.png)

## <a name="next-steps"></a>Sonraki adımlar

- Uygulamalara yönelik grup atamaları dahil etme veya dışlama hakkında daha fazla bilgi için bkz. [Microsoft Intune blogu](https://aka.ms/new_app_assignment_process).
- [Uygulama bilgilerini ve atamaları izlemeyi](apps-monitor.md) öğrenin.
