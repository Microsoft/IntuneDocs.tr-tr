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
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 4a3a11a8-9c0c-4334-8c6b-6fea4d0a2efb
ms.reviewer: amyro
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3fb5818609763753878fec7a84fd8c19eb154f88
ms.sourcegitcommit: e75718ee6cf93c0e6c915f2776b785fe8db9f7e0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74955448"
---
# <a name="terms-and-conditions-for-user-access"></a>Kullanıcı erişimi için hüküm ve koşullar

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

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

1. [Microsoft Endpoint Manager Yönetim Merkezi](https://go.microsoft.com/fwlink/?linkid=2109431)' nde oturum açın, **Kiracı Yönetimi** > **hüküm ve koşullar**' ı seçin.
2. **Oluştur**’u seçin.
3. **Temel bilgiler** sayfasında, aşağıdaki bilgileri belirtin:

   - **Ad**: Azure Portal koşulların adı. Kullanıcılar bu adı görmez.
   - **Açıklama**: Azure portalında bu koşul kümesini tanımlamanıza yardımcı olacak isteğe bağlı ayrıntılar.

    ![Hüküm ve koşullar için temel bilgiler sayfasını gösteren Azure portal ekran görüntüsü](./media/terms-and-conditions-create/terms-basics-page.png)

4. **Şartlar** sayfasına gitmek için **İleri ' yi** seçin ve aşağıdaki bilgileri sağlayın:

   - **Başlık**: Kullanıcıların Şirket Portalı'nda **Özet**'in yukarısında gördüğü koşullarınızın adı.
   - **Hüküm ve Koşullar**: Kullanıcılara gösterilen ve kabul etmeleri veya reddetmeleri gereken hüküm ve koşullar.
   - **Koşulların Özeti**: Kullanıcılar koşulları kabul ettiğinde bunun ne anlama geldiğini açıklayan metin. Örneğin, “Cihazınızı kaydettiğinizde, Contoso tarafından belirlenmiş kullanım koşullarını kabul etmiş olursunuz. Devam etmeden önce koşulları dikkatle okuyun."

5. **Kapsam etiketleri** sayfasına gitmek için **İleri ' yi** seçin.

6. **Kapsam etiketlerini Seç**' i seçin, bu hüküm ve koşullara atamak istediğiniz kapsam etiketlerini seçin ve ardından **Seç**' i seçin. 

7. **Atamalar** sayfasına gitmek için **İleri** ' yi seçin ve **ata**için aşağıdaki seçeneklerden birini belirleyin:
    - **Tüm kullanıcılar**: Bu hüküm ve koşulları tüm kullanıcılara atamak için bu seçeneği belirleyin.
    - **Grupları seçin**: Bu hüküm ve koşulları, **dahil edilecek grupları seç ' i**seçerek belirlediğiniz gruplardaki herkese atamak için bu seçeneği belirleyin.

8. **Oluştur**' > **İleri ' yi** seçin.

## <a name="see-how-terms-are-displayed-to-your-users"></a>Hükümlerin kullanıcılarınıza nasıl görüntüleneceğini görün
Aşağıdaki örnekte, **Başlık** ve **Koşulların Özeti** yönetim konsolunda ve Şirket Portalı'nda gösterilmektedir.

![Başlık'ın ve Koşulların Özeti'nin yönetim konsolundaki ve Şirket Portalı'ndaki ekran görüntüsü.](./media/terms-and-conditions-create/terms-summary-terms.png)

Aşağıdaki örnekte hüküm ve koşullar yönetim konsolunda ve Şirket Portalı'nda gösterilmektedir.

![Hüküm ve koşullar'ın yönetim konsolundaki ve Şirket Portalı'ndaki ekran görüntüsü.](./media/terms-and-conditions-create/terms-properties-terms.png)


## <a name="monitor-terms-and-conditions"></a>Hüküm ve koşulları izleme

1. [Microsoft Endpoint Manager Yönetim Merkezi](https://go.microsoft.com/fwlink/?linkid=2109431)' nde oturum açın, **Kiracı Yönetimi** > **hüküm ve koşullar**' ı seçin.
2. Hüküm ve koşullar listesinde, kabul durumunu görüntülemek istediğiniz koşulları seçin > **Kabul Raporlama**’yı seçin.

## <a name="work-with-multiple-versions-of-terms-and-conditions"></a>Hüküm ve koşulların birden çok sürümü ile çalışma
Hüküm ve koşullarınızı düzenleyebilir ve bunların sürümlerini yönetebilirsiniz. Hüküm ve koşullarınızda büyük değişiklikler yaptığınızda her zaman şunları yapmalısınız:
- Sürüm numarasını artırmak
- kullanıcıların yeni hüküm ve koşulları kabul etmesini gerektir

Örneğin, yazım hatalarını düzeltiyor veya biçimlendirmeyi değiştiriyorsanız geçerli sürüm numarasını saklayın.

1. [Microsoft Endpoint Manager Yönetim Merkezi](https://go.microsoft.com/fwlink/?linkid=2109431)' nde oturum açın, **Kiracı Yönetimi** > **hüküm ve koşullar** ' ı seçin > > **özelliklerini**değiştirmek istediğiniz hüküm ve koşulları seçin.

2. **Özellikler** bölmesinde **Hüküm ve Koşullar**’ı seçin ve ardından **Başlık**, **Koşulların Özeti** ve **Hüküm ve Koşullar**’da gerekli değişiklikleri yapın. Yaptığınız değişiklikler kullanıcıların koşulları yeniden kabul etmesini gerektiriyorsa **Kullanıcıların yeniden kabul etmesini ve sürüm numarasını şuna güncelleştirmesini gerektir** seçeneğini belirleyin

3. **Tamam** > **Kaydet**’i seçin.

Kullanıcıların güncelleştirilen hüküm ve koşulları yalnızca bir kez kabul etmesi gerekir. Birden çok cihazı olan kullanıcıların hüküm ve koşulları her cihazda ayrıca kabul etmesi gerekmez.
