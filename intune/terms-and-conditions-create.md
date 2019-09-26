---
title: Microsoft Intune’da hüküm ve koşulları ayarlama
titleSuffix: ''
description: Intune Şirket Portalı’nda kullanıcıların göreceği hüküm ve koşulları ayarlayın.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/20/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 4a3a11a8-9c0c-4334-8c6b-6fea4d0a2efb
ms.reviewer: amyro
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6d05b811ed371755ea61481a7b6e26f9fc43adee
ms.sourcegitcommit: c19584b36448bbd4c8638d7cab552fe9b3eb3408
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/20/2019
ms.locfileid: "71302873"
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
- [Azure Active Directory kullanım koşulları özelliğini](https://docs.microsoft.com/azure/active-directory/governance/active-directory-tou) kullanarak

Hangi yöntemin sizin için en uygun olduğunu öğrenmek için [kuruluşunuzun blog gönderisine yönelik doğru terimleri seçme çözümüne](https://go.microsoft.com/fwlink/?linkid=2010506&clcid=0x409)göz atın. 

## <a name="create-terms-and-conditions"></a>Hüküm ve koşulları oluşturma
Hüküm ve koşulları oluşturmak için şu adımları tamamlayın. Görüntü adı ve açıklama yönetimin kullanımına yöneliktir; öte yandan, koşul özellikleri Şirket Portalı’nda kullanıcılara görüntülenir.

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. **Intune** bölmesinde **Cihaz kaydı** > **Hüküm ve Koşullar**’ı seçin.
3. **Oluştur**’u seçin.
4. **Temel bilgiler** sayfasında, aşağıdaki bilgileri belirtin:

   - **Ad**: Azure portalında koşulların adı. Kullanıcılar bu adı görmez.
   - **Açıklama**: Azure portalında bu koşul kümesini tanımlamanıza yardımcı olacak isteğe bağlı ayrıntılar.

    ![Hüküm ve koşullar için temel bilgiler sayfasını gösteren Azure portal ekran görüntüsü](media/terms-basics-page.png)

5. **Şartlar** sayfasına gitmek için **İleri ' yi** seçin ve aşağıdaki bilgileri sağlayın:

   - **Başlık**: Kullanıcıların Şirket Portalı'nda **Özet**'in yukarısında gördüğü koşullarınızın adı.
   - **Hüküm ve Koşullar**: Kullanıcılara gösterilen ve kabul etmeleri veya reddetmeleri gereken hüküm ve koşullar.
   - **Koşulların Özeti**: Kullanıcılar koşulları kabul ettiğinde bunun ne anlama geldiğini açıklayan metin. Örneğin, “Cihazınızı kaydettiğinizde, Contoso tarafından belirlenmiş kullanım koşullarını kabul etmiş olursunuz. Devam etmeden önce koşulları dikkatle okuyun."

6. **Kapsam etiketleri** sayfasına gitmek için **İleri ' yi** seçin.

7. **Kapsam etiketlerini Seç**' i seçin, bu hüküm ve koşullara atamak istediğiniz kapsam etiketlerini seçin ve ardından **Seç**' i seçin. 

8. **Atamalar** sayfasına gitmek için **İleri** ' yi seçin ve **ata**için aşağıdaki seçeneklerden birini belirleyin:
    - **Tüm kullanıcılar**: Bu hüküm ve koşulları tüm kullanıcılara atamak için bu seçeneği belirleyin.
    - **Grupları seçin**: Bu hüküm ve koşulları, **dahil edilecek grupları seç ' i**seçerek belirlediğiniz gruplardaki herkese atamak için bu seçeneği belirleyin.

9. **İleri** > **Oluştur**seçeneğini belirleyin.

## <a name="see-how-terms-are-displayed-to-your-users"></a>Hükümlerin kullanıcılarınıza nasıl görüntüleneceğini görün
Aşağıdaki örnekte, **Başlık** ve **Koşulların Özeti** yönetim konsolunda ve Şirket Portalı'nda gösterilmektedir.

![Başlık'ın ve Koşulların Özeti'nin yönetim konsolundaki ve Şirket Portalı'ndaki ekran görüntüsü.](./media/terms-summary-terms.png)

Aşağıdaki örnekte hüküm ve koşullar yönetim konsolunda ve Şirket Portalı'nda gösterilmektedir.

![Hüküm ve koşullar'ın yönetim konsolundaki ve Şirket Portalı'ndaki ekran görüntüsü.](./media/terms-properties-terms.png)


## <a name="monitor-terms-and-conditions"></a>Hüküm ve koşulları izleme

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın. 
1. Intune bölmesinde **Cihaz kaydı** > **Hüküm ve Koşullar**’ı seçin.
2. Hüküm ve koşullar listesinde, kabul durumunu görüntülemek istediğiniz koşulları seçin > **Kabul Raporlama**’yı seçin.

## <a name="work-with-multiple-versions-of-terms-and-conditions"></a>Hüküm ve koşulların birden çok sürümü ile çalışma
Hüküm ve koşullarınızı düzenleyebilir ve bunların sürümlerini yönetebilirsiniz. Hüküm ve koşullarınızda büyük değişiklikler yaptığınızda her zaman şunları yapmalısınız:
- Sürüm numarasını artırmak
- kullanıcıların yeni hüküm ve koşulları kabul etmesini gerektir

Örneğin, yazım hatalarını düzeltiyor veya biçimlendirmeyi değiştiriyorsanız geçerli sürüm numarasını saklayın.

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.

2. Intune bölmesinde sırasıyla şunları seçin: **Cihaz kaydı** > **Hüküm ve Koşullar** > değiştirmek istediğiniz hüküm ve koşullar > **Özellikler**.

4. **Özellikler** bölmesinde **Hüküm ve Koşullar**’ı seçin ve ardından **Başlık**, **Koşulların Özeti** ve **Hüküm ve Koşullar**’da gerekli değişiklikleri yapın. Yaptığınız değişiklikler kullanıcıların koşulları yeniden kabul etmesini gerektiriyorsa **Kullanıcıların yeniden kabul etmesini ve sürüm numarasını şuna güncelleştirmesini gerektir** seçeneğini belirleyin

4. **Tamam** > **Kaydet**’i seçin.

Kullanıcıların güncelleştirilen hüküm ve koşulları yalnızca bir kez kabul etmesi gerekir. Birden çok cihazı olan kullanıcıların hüküm ve koşulları her cihazda ayrıca kabul etmesi gerekmez.
