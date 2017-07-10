---
title: "Hüküm ve koşul ilkesi ayarları"
description: "Kayıt, iş kaynaklarına erişim ve Şirket Portalı uygulamasını kullanmanın cihazları ve kullanıcıları nasıl etkileyeceğini açıklamak için kullanıcı gruplarına Intune hüküm ve koşullarını dağıtabilirsiniz."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/11/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6edf0ac1-4f46-4543-a9e5-f484ac37e9a5
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2e8028abe5f25e4a05d79ae543d3029490c01668
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="terms-and-condition-policy-settings-in-microsoft-intune"></a>Microsoft Intune’da hüküm ve koşullar ilkesi ayarları

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Kayıt, iş kaynaklarına erişim ve Şirket Portalı uygulamasını kullanmanın cihazları ve kullanıcıları nasıl etkileyeceğini açıklamak için kullanıcı gruplarına Intune hüküm ve koşullarını dağıtabilirsiniz. Kullanıcıların çalışmalarını kaydedip bunlara erişmek üzere Şirket Portalı’nı kullanabilmeleri için önce bu hüküm ve koşulları kabul etmeleri gerekir.

Farklı hüküm ve koşullar içeren birden çok ilke oluşturup dağıtabilirsiniz. Ayrıca, aynı şart ve koşulların farklı dillerdeki sürümlerini oluşturabilir ve bunları uygun gruplara dağıtabilirsiniz.

## <a name="create-a-terms-and-conditions-policy"></a>Hüküm ve koşullar ilkesi oluşturma

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **İlke** &gt; **Hüküm ve Koşullar**’a tıklayın.

    ![Hüküm ve koşullar ilkesi ekran görüntüsü](./media/pol-sa-terms-conditions.png)

2.  Yeni hüküm ve koşullar ilkesi oluşturmak için **Ekle**’ye tıklayın.

    Ayrıca var olan bir ilkeyi **Düzenleyebilir** veya**Silebilirsiniz**.

3.  **Hüküm ve Koşullar Oluştur** sayfasında aşağıdaki bilgileri belirtin:

    -   **Ad**&mdash; Intune konsolunda görüntülenen benzersiz bir ilke adı.

    -   **Açıklama**&mdash; İlkeyi Intune konsolunda tanımlamanıza yardımcı olan ayrıntılar.

    -   **Başlık**&mdash;Kullanıcıların şirket portalında gördüğü başlık.

    -   **Kullanıcının kabul etmesinin ne anlama geldiğini açıklayan metin**&mdash;Kullanıcıların kabul etmesine ilişkin görünen etiket. Örneğin: "Hüküm ve koşulları kabul ediyorum."

4.  İşiniz bittiğinde **Kaydet**’e tıklayın. Yeni ilke, **İlke** çalışma alanının **Hüküm ve Koşullar** düğümünde görüntülenir.

## <a name="deploy-a-terms-and-conditions-policy"></a>Hüküm ve koşullar ilkesini dağıtma

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **İlke** &gt; **Hüküm ve Koşullar**’a tıklayın.

2.  **Hüküm ve Koşullar İlkeleri** listesinde, dağıtmak istediğiniz ilkeyi seçin ve ardından **Dağıtımı Yönet**’e tıklayın.

3.  **Dağıtımı Yönet** iletişim kutusunda ilkeyi dağıtmak istediğiniz kullanıcı grubunu seçin ve ardından **Tamam**’a tıklayın.

    Hedeflenen kullanıcılar şirket portalına eriştiğinde, Intune tarafından dağıttığınız hüküm ve koşullar görüntülenir. Kullanıcıların şirket kaynaklarına erişebilmesi için bu koşulları kabul etmesi gerekir.

## <a name="monitor-a-terms-and-conditions-policy"></a>Hüküm ve koşullar ilkesini izleme

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **İlke** &gt; **Hüküm ve Koşullar**’a tıklayın.

2.  **Yeni Rapor Oluştur** penceresinde **Raporu Görüntüle**’ye tıklayın. Dağıttığınız hüküm ve koşulları hangi kullanıcıların kabul ettiğiyle ilgili ayrıntılı bilgi içeren rapor açılır.

### <a name="updates-and-version-control-for-terms-and-conditions"></a>Hüküm ve koşullar için güncelleştirme ve sürüm denetimi
Varolan bir hüküm ve koşullar ilkesini düzenlediğinizde, ilkeyi dağıttığınızda gerçekleşecek davranışı seçebilirsiniz. Varolan hüküm ve koşullar ilkelerini güncelleştirmenize yardımcı olması için aşağıdaki yordamı kullanın.

## <a name="work-with-multiple-versions-of-terms-and-conditions"></a>Hüküm ve koşulların birden çok sürümü ile çalışma

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **İlke** &gt; **Hüküm ve Koşullar**’a tıklayın.

2.  Düzenlemek istediğiniz hüküm ve koşullar ilkesini seçin ve ardından **Düzenle**’ye tıklayın.

3.  **Hüküm ve Koşulları Düzenle** sayfasında, gerekli tüm düzenlemeleri yapın ve bu yeni sürümün tüm kullanıcıların hüküm ve koşulları kabul etmesini mi gerektirdiğini yoksa yalnızca yeni kullanıcıların mı yeni sürümü göreceğini belirtin.

    Hüküm ve koşullar ilkenizde önemli değişiklikler yaptığınızda sürüm numarasını artırmanızı ve kabul şartı koşmanızı öneririz. Örneğin, yazım hatalarını düzeltiyor veya biçimlendirmeyi değiştiriyorsanız geçerli sürüm numarasını kullanmaya devam edin.

### <a name="see-also"></a>Ayrıca bkz.
[Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
