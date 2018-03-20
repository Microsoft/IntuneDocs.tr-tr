---
title: "Microsoft Intune’da hüküm ve koşulları ayarlama"
titlesuffix: 
description: "Intune Şirket Portalı’nda kullanıcıların göreceği hüküm ve koşulları ayarlayın."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/28/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a3a11a8-9c0c-4334-8c6b-6fea4d0a2efb
ms.reviewer: amyro
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8fb386948d14fcbd26cffcd1b531b6ae61e9d669
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2018
---
# <a name="manage-your-companys-terms-and-conditions-for-user-access"></a>Kullanıcı erişimi için şirketinizin hüküm ve koşullarını yönetme

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Bir Intune yöneticisi olarak, cihazlarını kaydetmek ve uygulama ve e-posta gibi şirket kaynaklarına erişmek üzere Şirket Portalı’nı kullanabilmeleri için önce şirketin hüküm ve koşullarını kabul etmelerini zorunlu tutabilirsiniz. Hüküm ve koşulların yapılandırması isteğe bağlıdır.

Farklı gruplara yönelik olarak, örneğin farklı dillere destek sağlamak için birden çok koşul kümesi oluşturabilirsiniz.

## <a name="create-terms-and-conditions"></a>Hüküm ve koşulları oluşturma
Hüküm ve koşulları oluşturmak için şu adımları tamamlayın. Görüntü adı ve açıklama yönetimin kullanımına yöneliktir; öte yandan, koşul özellikleri Şirket Portalı’nda kullanıcılara görüntülenir.

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** bölmesinde **Cihaz kaydı**’nı ve ardından **Hüküm ve Koşullar**’ı seçin.
2. **Oluştur**’u seçin.
![Hüküm ve koşullar için Oluştur düğmesinin gösterildiği Azure portalının ekran görüntüsü](media/terms-create-terms.png)
3. Genişletilmiş bölmede aşağıdaki bilgileri belirtin:

   - **Görünen ad**: Azure portalında koşulların adı. Kullanıcılar bu adı görmez.

   - **Açıklama**: Azure portalında bu koşul kümesini tanımlamanıza yardımcı olacak isteğe bağlı ayrıntılar.

4. Hükümler ve Koşullar bölmesini açmak için **Kullanım koşullarını tanımla**’nın yanındaki oku seçin ve ardından aşağıdaki bilgileri girin:

   ![Son kullanıcı koşulları ve koşul özetlerinin bulunduğu hüküm ve koşulların kabulünü gösteren ekran görüntüsü](./media/terms-summary-create.png)

   - **Başlık**: Kullanıcıların Şirket Portalı'nda **Özet**'in yukarısında gördüğü koşullarınızın adı.
   - **Koşulların Özeti**: Kullanıcılar koşulları kabul ettiğinde bunun ne anlama geldiğini açıklayan metin. Örneğin, "Cihazınızı kaydettiğinizde, Contoso tarafından belirlenmiş kullanım koşullarını kabul etmiş olursunuz. Devam etmeden önce koşulları dikkatle okuyun."
   - **Hüküm ve Koşullar**: Kullanıcılara gösterilen ve kabul etmeleri veya reddetmeleri gereken hüküm ve koşullar.

5. **Tamam**’ı ve ardından **Oluştur**’u seçin.

## <a name="see-how-terms-are-displayed-to-your-users"></a>Hükümlerin kullanıcılarınıza nasıl görüntüleneceğini görün
Aşağıdaki örnekte, **Başlık** ve **Koşulların Özeti** yönetim konsolunda ve Şirket Portalı'nda gösterilmektedir.

![Başlık'ın ve Koşulların Özeti'nin yönetim konsolundaki ve Şirket Portalı'ndaki ekran görüntüsü.](./media/terms-summary-terms.png)

Aşağıdaki örnekte hüküm ve koşullar yönetim konsolunda ve Şirket Portalı'nda gösterilmektedir.

![Hüküm ve koşullar'ın yönetim konsolundaki ve Şirket Portalı'ndaki ekran görüntüsü.](./media/terms-properties-terms.png)

## <a name="assign-terms-and-conditions"></a>Hüküm ve koşulları atama

Hüküm ve koşulları kullanıcı gruplarına atayabilirsiniz; bu kullanıcıların Şirket Portalı’nı kullanmak için önce bunları kabul etmesi gerekir.

1. Azure portalında **Cihaz kaydı**’nı ve ardından **Hüküm ve Koşullar**’ı seçin.
2. Hüküm ve koşullar listesinde, atamak istediğiniz koşulları seçin ve sonra da **Yönet** > **Atamalar**’ı seçin.
![Azure portalında hüküm ve koşulların atanması için Grup Seç düğmesinin gösterildiği Grup Ata bölmesinin ekran görüntüsü](media/terms-assign-groups.png)
3. **Dahil edilecek grupları seçin** öğesine tıklayın, hükümlerin atanmasını istediğiniz grupları seçin ve ardından **Seç** düğmesini seçin. Hüküm ve Koşullar dinamik gruplara atanamaz.
4. **Atanan Gruplar** bölmesinde **Kaydet**’e tıklayın.  Artık hükümler ve koşullar seçili grupların kullanıcılarına atanır. Bir sonraki Şirket Portalı erişimi sırasında kullanıcılardan koşulları kabul etmeleri istenir. Hüküm ve koşulların yalnızca bir kez kabul edilmesi gerekir. Birden çok cihazı olan kullanıcıların her cihazda ayrıca kabul etmesi gerekmez.


## <a name="monitor-terms-and-conditions"></a>Hüküm ve koşulları izleme

1. Azure portalında **Tüm Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin. 
1. Intune bölmesinde **Cihaz kaydı**’nı ve ardından **Hüküm ve Koşullar**’ı seçin.
2. Hüküm ve koşullar listesinde, kabul durumunu görüntülemek istediğiniz koşulları seçin ve sonra da **Kabul Raporlama**’yı seçin.

## <a name="work-with-multiple-versions-of-terms-and-conditions"></a>Hüküm ve koşulların birden çok sürümü ile çalışma
Hüküm ve koşullarınızı düzenleyebilir ve bunların sürümlerini yönetebilirsiniz. Hüküm ve koşullarınızda önemli değişiklikler yaptığınızda sürüm numarasını artırmanızı ve kabul şartı koşmanızı öneririz. Örneğin, yazım hatalarını düzeltiyor veya biçimlendirmeyi değiştiriyorsanız geçerli sürüm numarasını kullanmaya devam edin.

1. Azure portalında **Tüm Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.

2. Intune bölmesinde **Cihaz kaydı**’nı seçin, **Hüküm ve Koşullar**’ı seçin, değiştirmek istediğiniz hüküm ve koşulları seçin, sonra da **Özellikler**’i seçin.

4. **Özellikler** bölmesinde **Hüküm ve Koşullar**’ı seçin ve ardından **Başlık**, **Koşulların Özeti** ve **Hüküm ve Koşullar**’da gerekli değişiklikleri yapın. Yaptığınız değişiklikler kullanıcıların yeni koşulları yeniden kabul etmesini gerektiriyorsa şu seçeneğe tıklayın: **Kullanıcıların yeniden kabul etmesini ve sürüm numarasını şuna artırmasını gerektirin:**

4.  **Tamam**’ı ve ardından **Kaydet**’i seçin.

Kullanıcıların güncelleştirilen hüküm ve koşulları yalnızca bir kez kabul etmesi gerekir. Birden çok cihazı olan kullanıcıların hüküm ve koşulları her cihazda ayrıca kabul etmesi gerekmez.
