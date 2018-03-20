---
title: "Microsoft Intune’da uygulama atamalarını dahil etme ve dışlama"
titlesuffix: 
description: "Uygulama atamalarını dahil etmek ve dışlamak için Microsoft Intune’u nasıl kullanabileceğinizi öğrenin."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/08/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c59f6df5-3317-4dff-8f19-fdeec33faedf
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dbe8669dc2bf448e0738147758d90ba6d2d69b06
ms.sourcegitcommit: 8a235b7af6ec3932c29a76d0b1aa481d983054bc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
---
# <a name="include-and-exclude-app-assignments-in-microsoft-intune"></a>Microsoft Intune’da uygulama atamalarını dahil etme ve dışlama

Intune ile, grupları hem dahil etmek hem de dışlamak üzere atayarak bir uygulamaya kimin erişebileceğini belirleyebilirsiniz. Öte yandan, uygulamaya grupları atamadan önce uygulamanın atama türünü ayarlamanız gerekir. Atama türü uygulamayı kullanılabilir veya gerekli duruma getirir ya da kaldırır. 

Uygulamanın kullanılabilirliğine odaklandığınızda, birtakım dahil etme ve dışlama grup atamaları kullanarak bir kullanıcı veya cihaz grubuna uygulama atamalarını dahil edebilir veya dışlayabilirsiniz. Bu özellik, büyük bir grubu dahil ederek uygulamayı sunup daha sonra küçük bir grubu dışlayarak seçili kullanıcıları azalttığınızda kullanışlı olabilir. Bu küçük grup, bir test grubu veya yönetici grubu olabilir. 

Uygulama atamasından grupları dışlarken, grupları karışık olarak dışlamak yerine yalnızca kullanıcı veya yalnızca cihaz gruplarını dışlamanız gerekir. Intune, grupları dışlarken kullanıcı cihaz ilişkisini göz önünde bulundurmaz. Kullanıcı gruplarını dahil ederken cihaz gruplarını dışlamak, istediğiniz sonuçları vermeyebilir. Çünkü dahil etme işleminin dışlama işlemine önceliği vardır. Örneğin bir iOS uygulamasını **Tüm Kullanıcılar** olarak hedefler ancak **Tüm iPad’ler** grubunu dışlarsanız, sonuç olarak iPad’i olan tüm kullanıcılar uygulamayı yine de alır. Ancak iOS uygulamasını **Tüm Cihazlar** olarak hedefler ve **Tüm iPad’ler** grubunu dışlarsanız, o zaman dağıtım başarılı olur.  

>[!NOTE]
>Bir uygulama için grup ataması ayarlarken, **Uygun değil** türü kullanım dışıdır ve grup dışlama işleviyle yer değiştirir. 
>
>Intune size kolaylık sağlamak adına konsolda önceden oluşturulmuş ve yerleşik iyileştirmeleri bulunan **Tüm Kullanıcılar** ve **Tüm Cihazlar** gruplarını sağlar. Tüm kullanıcı ve cihazları hedeflemek için kendi oluşturacağınız “Tüm kullanıcılar” veya “Tüm cihazlar” grupları yerine bu grupları kullanmanızı kesinlikle öneririz.  

## <a name="including-and-excluding-groups-when-assigning-apps"></a>Uygulama atarken grup dahil etme ve dışlama 
Dahil etme ve dışlama atamasını kullanarak bir uygulamayı gruplara atamak için:
1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. Microsoft Intune dikey penceresinde **Mobil uygulamalar**’ı seçin.
4. **Mobil uygulamalar** dikey penceresinde **Uygulamalar**’ı seçin. Eklenen uygulamalar listesi görüntülenir.
5. Atamak istediğiniz uygulamayı seçin. Uygulamayla ilgili bir pano görüntülenir. 
6. **Yönet** bölümünün altında **Atamalar**’ı seçin. 

    ![Intune uygulama atamaları](./media/apps-inc-exl-01.png)
7. **Grup ekle**’yi seçerek uygulamaya atanmış kullanıcı gruplarını ekleyin. 
8. **Grup ekle** bölmesindeki kullanılabilir atama türlerinden bir **Atama türü** seçin.
9. Atama türü olarak **Kayıt ile veya kayıtsız kullanılabilir**’i seçin.

    ![Intune uygulama atamaları - Grup ekle](./media/apps-inc-exl-02.png)
10. **Dahil Edilen Gruplar**’a tıklayarak bu uygulamaya erişmesini istediğiniz kullanıcı gruplarını seçin.

    >[!NOTE]
    >Bir grup eklerken, herhangi bir atama türü için başka bir grup önceden dahil edilmişse bu grup, diğer dahil etme atama türleri için önceden seçili ve değiştirilemez bir biçimde görüntülenir. Dolayısıyla bu grup zaten kullanılmıştır ve dahil edilmiş bir grup olarak kullanılamaz.

11. **Evet**’i seçerek bu uygulamayı tüm kullanıcılar için kullanılabilir yapın.

    ![Intune uygulama atamaları - Grup dahil et](./media/apps-inc-exl-03.png)
12. Dahil edilecek grubu ayarlamak için **Tamam**’a tıklayın.
13. **Dışlanan Gruplar**’a tıklayarak bu uygulamaya erişmesini istemediğiniz kullanıcı gruplarını seçin. 
14. Dışlanacak grupları seçin, böylece bu gruplar için uygulama kullanılamaz olur.

    ![Intune uygulama atamaları - Grup dışla](./media/apps-inc-exl-04.png)
15. **Seç**’e tıklayarak grup seçiminizi tamamlayın.
16. **Grup ekle** dikey penceresinde **Tamam**’a tıklayın. Uygulamanın **Atamalar** listesi görüntülenir.
17. **Kaydet**’e tıklayarak uygulama için grup atamalarınızı etkinleştirin.

Grup atamaları yaparken, önceden atanmış veya seçilmiş gruplar devre dışıdır. Mevcut durumda devre dışı olan bir grubu seçmek isterseniz, bu grubu uygulamanın atanmış listesinden kaldırın. Değiştirmek istediğiniz atamayı barındıran satırı seçerek uygulamanın **Atamalar** listesinde atamaları düzenleyebilirsiniz. Ayrıca bir satırın sonundaki üç noktaya (...) tıklayıp **Kaldır**’ı seçerek bir atamayı kaldırabilirsiniz. Bunun yanı sıra **Atama türü**’ne veya **Dahil edilen/Dışlanan**’a göre gruplamayı seçerek **Atamalar** listesinin görünümünü değiştirebilirsiniz.

![Intune uygulama atamaları - Tamamlandı](./media/apps-inc-exl-05.png)

## <a name="next-steps"></a>Sonraki adımlar

- Uygulamalar için grup atamaları dahil etme veya dışlana hakkında daha fazla bilgi için bkz. [Microsoft Intune Blogu](https://aka.ms/new_app_assignment_process).
- [Uygulama bilgilerini ve atamaları izleme](apps-monitor.md)