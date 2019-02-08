---
title: Microsoft Intune’da hüküm ve koşulları ayarlama
titlesuffix: ''
description: Intune Şirket Portalı’nda kullanıcıların göreceği hüküm ve koşulları ayarlayın.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/20/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4a3a11a8-9c0c-4334-8c6b-6fea4d0a2efb
ms.reviewer: amyro
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: d126852366ff67adbbfecd2eb5ebe14a129c5945
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55839241"
---
# <a name="terms-and-conditions-for-user-access"></a>Hüküm ve koşullar kullanıcı erişimi

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bir Intune yöneticisi olarak, aşağıdaki eylemleri gerçekleştirebilmeleri için kullanıcıların şirketinizin hüküm ve koşullarını kabul etmesini zorunlu tutabilirsiniz:
- Cihaz kaydetme
- Şirket uygulamaları ve e-postası gibi kaynaklara erişme.    
Hüküm ve koşulların yapılandırması isteğe bağlıdır.

Farklı gruplara yönelik olarak, örneğin farklı dillere destek sağlamak için birden çok koşul kümesi oluşturabilirsiniz.

Şirketinizin hüküm ve koşullarını oluşturmanın iki yolu vardır:
- Bu makalede açıklandığı gibi Intune kullanarak.
- [Azure Active Directory kullanım koşulları özelliğini](https://docs.microsoft.com/azure/active-directory/governance/active-directory-tou) kullanarak. Hangi yöntemin size en uygun olduğunu öğrenmek için [Kuruluşunuz için doğru Koşul çözümünü seçme blog gönderisine](https://go.microsoft.com/fwlink/?linkid=2010506&clcid=0x409) göz atın. 

## <a name="create-terms-and-conditions"></a>Hüküm ve koşulları oluşturma
Hüküm ve koşulları oluşturmak için şu adımları tamamlayın. Görüntü adı ve açıklama yönetimin kullanımına yöneliktir; öte yandan, koşul özellikleri Şirket Portalı’nda kullanıcılara görüntülenir.

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** bölmesinde **Cihaz kaydı** > **Hüküm ve Koşullar**’ı seçin.
2. **Oluştur**’u seçin.
![Hüküm ve koşullar için Oluştur düğmesinin gösterildiği Azure portalının ekran görüntüsü](media/terms-create-terms.png)
3. Genişletilmiş bölmede aşağıdaki bilgileri belirtin:

   - **Görünen ad**: Azure portalında koşulların adı. Kullanıcılar bu adı görmez.

   - **Açıklama**: Azure portalında koşul kümesini tanımlamanıza yardımcı olan isteğe bağlı ayrıntılar.

4. Hüküm ve Koşullar bölmesini açmak için **Kullanım koşullarını tanımla**’nın yanındaki oku seçin ve ardından aşağıdaki bilgileri girin:

   ![Koşul özetleriyle birlikte son kullanıcı hüküm ve koşullarını kabul etme ekranını gösteren ekran görüntüsü](./media/terms-summary-create.png)

   - **Başlık**: Yukarıdaki şirket portalında kullanıcıların gördüğü koşullarınıza adı **özeti**.
   - **Koşulların özeti**: Kullanıcılar koşulları kabul ettiğinde ne anlama geldiğini açıklayan metin. Örneğin, “Cihazınızı kaydettiğinizde, Contoso tarafından belirlenmiş kullanım koşullarını kabul etmiş olursunuz. Devam etmeden önce koşulları dikkatle okuyun."
   - **Hüküm ve koşullar**: Hüküm ve kullanıcılar bakın ve kabul Reddet veya gereken koşulları.

5. **Tamam** > **Oluştur**’u seçin.

## <a name="see-how-terms-are-displayed-to-your-users"></a>Hükümlerin kullanıcılarınıza nasıl görüntüleneceğini görün
Aşağıdaki örnekte, **Başlık** ve **Koşulların Özeti** yönetim konsolunda ve Şirket Portalı'nda gösterilmektedir.

![Başlık'ın ve Koşulların Özeti'nin yönetim konsolundaki ve Şirket Portalı'ndaki ekran görüntüsü.](./media/terms-summary-terms.png)

Aşağıdaki örnekte hüküm ve koşullar yönetim konsolunda ve Şirket Portalı'nda gösterilmektedir.

![Hüküm ve koşullar'ın yönetim konsolundaki ve Şirket Portalı'ndaki ekran görüntüsü.](./media/terms-properties-terms.png)

## <a name="assign-terms-and-conditions"></a>Hüküm ve koşulları atama

Hüküm ve koşulları kullanıcı gruplarına atayabilirsiniz; bu kullanıcıların Şirket Portalı’nı kullanmak için önce bunları kabul etmesi gerekir.

1. Azure portalında **Cihaz kaydı**’nı ve ardından **Hüküm ve Koşullar**’ı seçin.
2. Hüküm ve koşullar listesinde, atamak istediğiniz koşulları seçin > **Yönet** > **Atamalar**’a tıklayın.
![Azure portalında hüküm ve koşulların atanması için Grup Seç düğmesinin gösterildiği Grup Ata bölmesinin ekran görüntüsü](media/terms-assign-groups.png)
3. **Dahil edilecek grupları seç** seçeneğini belirleyin > hükümlerin atanmasını istediğiniz grupları seçin > **Seç** düğmesini seçin. Hüküm ve Koşullar dinamik gruplara atanamaz.
4. **Atanan Gruplar** bölmesinde **Kaydet**’e tıklayın.  Artık hükümler ve koşullar seçili grupların kullanıcılarına atanır. Bir sonraki Şirket Portalı erişimi sırasında kullanıcılardan koşulları kabul etmeleri istenir. Hüküm ve koşulların yalnızca bir kez kabul edilmesi gerekir. Birden çok cihazı olan kullanıcıların her cihazda ayrıca kabul etmesi gerekmez.


## <a name="monitor-terms-and-conditions"></a>Hüküm ve koşulları izleme

1. Azure portalında **Tüm Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin. 
1. Intune bölmesinde **Cihaz kaydı** > **Hüküm ve Koşullar**’ı seçin.
2. Hüküm ve koşullar listesinde, kabul durumunu görüntülemek istediğiniz koşulları seçin > **Kabul Raporlama**’yı seçin.

## <a name="work-with-multiple-versions-of-terms-and-conditions"></a>Hüküm ve koşulların birden çok sürümü ile çalışma
Hüküm ve koşullarınızı düzenleyebilir ve bunların sürümlerini yönetebilirsiniz. Hüküm ve koşullarınızda büyük değişiklikler yaptığınızda her zaman şunları yapmalısınız:
- Sürüm numarasını artırmak
- Kullanıcıların yeni hüküm ve koşulları kabul etmesini gerekli kılmak. Harf hatalarını düzeltmek veya biçimlendirmeyi değiştirmek gibi eylemler gerçekleştirdiyseniz geçerli sürüm numarasını kullanmaya devam edebilirsiniz.

1. Azure portalında **Tüm Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.

2. Intune bölmesinde sırasıyla şunları seçin: **Cihaz kaydı** > **Hüküm ve Koşullar** > değiştirmek istediğiniz hüküm ve koşullar > **Özellikler**.

4. **Özellikler** bölmesinde **Hüküm ve Koşullar**’ı seçin ve ardından **Başlık**, **Koşulların Özeti** ve **Hüküm ve Koşullar**’da gerekli değişiklikleri yapın. Yaptığınız değişiklikler kullanıcıların koşulları yeniden kabul etmesini gerektiriyorsa **Kullanıcıların yeniden kabul etmesini ve sürüm numarasını şuna güncelleştirmesini gerektir** seçeneğini belirleyin

4.  **Tamam** > **Kaydet**’i seçin.

Kullanıcıların güncelleştirilen hüküm ve koşulları yalnızca bir kez kabul etmesi gerekir. Birden çok cihazı olan kullanıcıların hüküm ve koşulları her cihazda ayrıca kabul etmesi gerekmez.
