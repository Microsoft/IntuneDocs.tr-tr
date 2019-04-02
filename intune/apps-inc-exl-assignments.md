---
title: Microsoft Intune’da uygulama atamalarını dahil etme ve dışlama
titleSuffix: ''
description: Uygulama atamalarını dahil etmek ve dışlamak için Microsoft Intune’u nasıl kullanabileceğinizi öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/20/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: c59f6df5-3317-4dff-8f19-fdeec33faedf
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 771092b193154680c7755460d53b7c95efe592cf
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58799587"
---
# <a name="include-and-exclude-app-assignments-in-microsoft-intune"></a>Microsoft Intune’da uygulama atamalarını dahil etme ve dışlama

Intune'da, dahil etmek ve dışlamak üzere kullanıcı gruplarını atayarak bir uygulamaya kimin erişebileceğini belirleyebilirsiniz. Uygulamaya grupları atamadan önce uygulamanın atama türünü ayarlamanız gerekir. Atama türü uygulamayı kullanılabilir veya gerekli duruma getirir ya da kaldırır. 

Uygulamanın kullanılabilirliğini ayarlamak için, bir dahil etme ve dışlama grup atamaları bileşimi kullanarak bir kullanıcı veya cihaz grubuna uygulama atamalarını dahil edebilir veya dışlayabilirsiniz. Bu özellik, büyük bir grubu dahil ederek uygulamayı sunup daha sonra küçük bir grubu dışlayarak seçili kullanıcıları azalttığınızda kullanışlı olabilir. Bu küçük grup, bir test grubu veya yönetici grubu olabilir. 

Uygulama atamasından grupları dışlarken, yalnızca kullanıcı gruplarını veya yalnızca cihaz gruplarını dışlamanız gerekir. Kullanıcı gruplarıyla cihaz gruplarının bir bileşimini dışlayamazsınız. 

Intune, grupları dışlarken kullanıcı-cihaz ilişkisini dikkate almaz. Kullanıcı gruplarını dahil ederken cihaz gruplarını dışlamak, istediğiniz sonuçları vermeyebilir. Dahil etme, dışlamadan önceliklidir. Örneğin bir iOS uygulamasını **Tüm Kullanıcılar** olarak hedefler ancak **Tüm iPad’ler** grubunu dışlarsanız, sonuç olarak iPad’i olan tüm kullanıcılar uygulamayı yine de alır. Öte yandan, iOS uygulamasını **Tüm Cihazlar** olarak hedefler ve **Tüm iPad’ler** grubunu dışlarsanız, o zaman dağıtım başarılı olur.  

> [!NOTE]
> Bir uygulama için grup ataması ayarlarken, **Uygulanamaz** türü kullanım dışıdır ve bunun yerini grup dışlama işlevi almıştır. 
>
> Intune konsolda önceden oluşturulmuş **Tüm Kullanıcılar** ve **Tüm Cihazlar** gruplarını sağlar. Size kolaylık sağlamak için grupların yerleşik iyileştirmeleri vardır. Tüm kullanıcı ve cihazları hedeflemek için kendi oluşturabileceğiniz "tüm kullanıcılar" veya "tüm cihazlar" grupları yerine bu grupları kullanmanızı kesinlikle öneririz.  
>
> Android kurumsal, grupları dahil etmeyi ve dışlamayı destekler. Android kurumsal uygulama ataması için yerleşik **Tüm Kullanıcılar** ve **Tüm Cihazlar** gruplarından yararlanabilirsiniz. 


## <a name="include-and-exclude-groups-when-assigning-apps"></a>Uygulama atarken grupları dahil etme ve dışlama 
Dahil etme ve dışlama atamasını kullanarak gruplara uygulama atamak için:
1. [Azure Portal](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** menüsünde **İstemci uygulamaları**’nı seçin.
4. **İstemci uygulamaları** bölmesinde **Uygulamalar**’ı seçin. Eklenen uygulamalar listesi gösterilir.
5. Atamak istediğiniz uygulamayı seçin. Bir panoda uygulama hakkındaki bilgiler görüntülenir. 
6. Menünün **Yönet** bölümünde **Atamalar**’ı seçin. 

    ![Uygulama atarken uygulama atamalarını dahil](./media/apps-inc-exl-01.png)
7. **Grup ekle**’yi seçerek uygulamaya atanmış kullanıcı gruplarını ekleyin. 
8. **Grup ekle** bölmesindeki kullanılabilir atama türlerinden bir **Atama türü** seçin.
9. Atama türü olarak **Kayıtlı veya kayıtsız olarak kullanılabilir**’i seçin.

    ![Intune uygulama atamaları - Grup ekle](./media/apps-inc-exl-02.png)
10. **Dahil Edilen Gruplar**’a tıklayarak bu uygulamaya erişmesini istediğiniz kullanıcı gruplarını seçin.

    > [!NOTE]
    > Grup eklerken, belirli bir atama türü için başka bir grup önceden dahil edilmişse, uygulama diğer dahil etme atama türleri için önceden seçilmiştir ve değiştirilemez. Kullanılmış olan grup, dahil edilmiş bir grup olarak kullanılamaz.

11. **Evet**’i seçerek bu uygulamayı tüm kullanıcılar için kullanılabilir yapın.

    ![Intune uygulama atamaları - Grup dahil et](./media/apps-inc-exl-03.png)
12. Dahil edilecek grubu ayarlamak için **Tamam**’ı seçin.
13. **Dışlanan Gruplar**’a tıklayarak bu uygulamaya erişmesini istemediğiniz kullanıcı gruplarını seçin. 
14. Dışlanacak grupları seçin. Bu işlem, bu uygulamanın söz konusu gruplar için kullanılamaz olmasını sağlar.

    ![Intune uygulama atamaları - Grup dışla](./media/apps-inc-exl-04.png)
15. **Seç**’i seçerek grup seçiminizi tamamlayın.
16. **Grup ekle** bölmesinde **Tamam**’ı seçin. Uygulamanın **Atamalar** listesi görüntülenir.
17. **Kaydet**’e tıklayarak uygulama için grup atamalarınızı etkinleştirin.

Grup atamaları yaparken, zaten atanmış olan gruplar değiştirilemez. Şu anda kullanılamaz durumda olan bir grubu seçmek isterseniz, önce uygulamanın atanmış listesinden uygulamayı kaldırın. 

Atamaları düzenlemek için, uygulamanın **Atamalar** listesinde değiştirmek istediğiniz atamayı içeren satırı seçin. Ayrıca, satırın sonundaki üç noktayı (**…**) ve sonra da **Kaldır**'ı seçerek de atamayı kaldırabilirsiniz. **Atamalar** listesinin görünümünü değiştirmek için **Atama türü**’ne veya **Dahil edilen/Dışlanan**’a göre gruplandırın.

![Intune uygulama atamaları - Tamamlandı](./media/apps-inc-exl-05.png)

## <a name="next-steps"></a>Sonraki adımlar

- Uygulamalara yönelik grup atamaları dahil etme veya dışlama hakkında daha fazla bilgi için bkz. [Microsoft Intune blogu](https://aka.ms/new_app_assignment_process).
- [Uygulama bilgilerini ve atamaları izlemeyi](apps-monitor.md) öğrenin.
