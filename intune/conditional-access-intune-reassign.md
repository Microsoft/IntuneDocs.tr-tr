---
title: Azure portalına koşullu erişim geçişi
titlesuffix: Microsoft Intune
description: Önceden klasik Intune portalında oluşturduğunuz koşullu erişim ilkelerini Azure portalına yeniden atayın.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 09/25/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 301159ad-5f7e-4fcc-86c7-f72a71701ff4
ms.reviewer: chrisgree
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 00c657700cd8c27e4758b9cc94292ba83b2db3cd
ms.sourcegitcommit: fffa64f28278573dc83a846b647315def2108781
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48231721"
---
# <a name="reassign-conditional-access-policies-from-intune-classic-portal-to-the-azure-portal"></a>Koşullu erişim ilkelerini Klasik Intune portalından Azure portalına yeniden atama

Yeni Azure portalı ile koşullu erişim, uygulama başına birden çok ilke için desteğin yanında artırılmış özelleştirilebilirlik sunuyor. Önceden klasik Intune portalında koşullu erişim ilkeleri oluşturduysanız, bunları Azure portalına geçirebilirsiniz. 

## <a name="before-you-begin"></a>Başlamadan önce

Azure portalına geçmeye hazırsanız klasik Intune portalında önceden oluşturduğunuz koşullu erişim ilkelerini yeniden atamak için bu konudaki adımları izleyin:

- İleride hangi ayarları yeniden atayacağınızı bulabilmek adına önceden oluşturulmuş koşullu erişim ilkelerini toplayın.

- Bu ilkeleri Azure portalında yeniden oluşturmak için bu konudaki adımları takip edin.

- Yeni ilkelerin Azure portalında olması gerektiği gibi çalıştığını doğruladıktan sonra klasik Intune portalında koşullu ilkeleri devre dışı bırakın.
<br /><br />
    - Klasik Intune portalında koşullu erişim ilkelerini **devre dışı bırakmadan önce**, kullanıcıları yeni ilkeye nasıl taşıyacağınızı planlayın. Bunun için iki yaklaşım vardır:
<br /><br />
        - **Azure portalında oluşturulan ilkeleri uygulamak için aynı ekleme grubunu kullanın ve klasik Intune portalı tarafından uygulanan ilkelerle birlikte kullanmak üzere yeni bir çıkarma grubu oluşturun**.
            - Aşamalı olarak bazı kullanıcıları klasik portalda belirtilen çıkarma grubuna taşıyın. Bu şekilde taşımak, klasik Intune portalının hedeflediği ilkelerin uygulanmasını önler. Klasik Intune portalında uygulanan ilkelere ek olarak, Azure portalında oluşturulan ve aynı kullanıcı grubunu hedefleyen ilkeler uygulanır. 
<br /><br />
        - **Azure portalında koşullu ilkelerin hedefleyeceği yeni bir grup oluşturun**. Bu yaklaşımı seçerseniz şunları yapmanız gerekir:
            - Klasik Intune portalında, kendisine bazı koşullu erişim ilkeleri hedeflenmiş güvenlik gruplarından kullanıcıları aşamalı olarak kaldırın.
            - Yeni ilkenin bu kullanıcılarda çalıştığını onayladıktan sonra klasik Intune portalında bu ilkeyi devre dışı bırakabilirsiniz. 
<br /><br />
- Klasik Intune portalında koşullu erişim ilkesi ayarlarınızı Exchange ActiveSync (EAS) kullanmak üzere yapılandırdıysanız [bu konudaki yönergeleri](#to-reassign-intune-device-based-conditional-access-policies-for-eas-clients) izleyerek **Azure portalında EAS koşullu erişim ilkesi ayarlarını yeniden atayın**.

### <a name="to-verify-your-device-based-conditional-access-policies-in-the-intune-classic-portal"></a>Cihaz temelli koşullu erişim ilkelerinizi klasik Intune portalında doğrulamak için

1.  [Klasik Intune portalına](https://manage.microsoft.com) gidin ve kimlik bilgilerinizle oturum açın.

2.  Soldaki menüden **İlkeler**’i seçin.

3.  **Koşullu Erişim**’i seçin ve daha sonra hangi Microsoft bulut hizmeti için (Exchange Online veya SharePoint Online gibi) ilke oluşturduysanız onu seçin.

4.  Koşullu erişim ayarlarınızı not edin ve Azure portalında aynı koşullu erişim ilkelerini oluştururken bu notlardan faydalanın.

### <a name="app-and-device-based-conditional-access-policies-working-together"></a>Uygulama ve cihaz temelli koşullu erişim ilkelerinin birlikte çalışması

Azure portalındaki **Intune Uygulama Koruması** dikey penceresi, yöneticilerin uygulama temelli koşullu kurallar ayarlamasına imkan verir. Böylece yalnızca Intune uygulama korumasını destekleyen uygulamalar şirket kaynaklarına erişebilir. Cihaz temelli koşullu erişim ilkelerini kullanarak bu uygulama temelli koşullu erişim ilkelerini çakıştırmayı seçebilirsiniz. Cihaz tabanlı ve uygulama tabanlı koşullu ilkelerini birleştirebilir (mantıksal VE) veya bu iki seçenekten yalnızca birini belirtebilirsiniz (mantıksal VEYA). Koşullu erişim ilkesi gereksinimleriniz şu şekildeyse:

- Uyumlu cihaz gerektir **VE** onaylı uygulamayı kullan.
    - O halde koşullu erişim ilkenizi, [Azure Active Directory koşullu erişim dikey penceresi](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) ve [Intune Uygulama Koruması dikey penceresi](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0) kullanarak ayarlamalısınız.
<br /><br />
- Uyumlu cihaz gerektir **VEYA** onaylı uygulamayı kullan.
    - O halde koşullu erişim ilkenizi, [klasik Intune portalı](https://manage.microsoft.com) ve [Intune Uygulama Koruması dikey penceresi](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0) kullanarak ayarlamalısınız.

> [!TIP] 
> Bu konuda, klasik Intune portalı ve Azure portalı kullanıcı deneyimini karşılaştıran ekran görüntüleri sağlanır.

## <a name="reassign-intune-device-based-conditional-access-policies"></a>Intune cihaz temelli koşullu erişim ilkelerini yeniden atama

1. [Azure portalında koşullu erişime](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) gidin ve kimlik bilgilerinizle oturum açın.

2. **Yeni ilke**’yi seçin.

3. İlke için bir ad sağlayın.

4. **Atamalar kısmında** yeni koşullu erişim ilkesinin hedefleyeceği **Kullanıcılar ve grupları**’ı seçin.
    
    ![Intune ve Azure portalları arasında kullanıcı grubu kullanıcı arabirimi karşılaştırmasını gösteren resim](./media/reassign-ca-1.png)

    > [!IMPORTANT] 
    > Klasik portal için yaptığınız bu seçim, Azure portalında yaptığınızla ilişkili olmalıdır. Örneğin klasik Intune portalında tüm kullanıcıları seçtiyseniz Azure portalında da **Tüm kullanıcılar**’ı seçin. Ayrıca klasik Intune portalında **Grupları çıkar** seçeneğini seçtiyseniz bu grupları Azure portalında da dışlayın.

5. Grubunuzu belirledikten sonra **Seç**’e ve ardından **Bitti**’ye tıklayın.

6. **Atamalar** kısmındaki **Bulut uygulamaları**’nı seçin.

7. **Bulut uygulamaları** dikey penceresinde **Uygulama seç**’e tıklayın.

8. Yeni koşullu erişim ilkesini uygulamak istediğiniz uygulamayı belirleyin ve **Seç**’e tıklayın.

9. **Bitti**’ye tıklayın.

    ![Intune ve Azure portalları arasında bulut uygulaması kullanıcı arabirimi karşılaştırmasını gösteren resim](./media/reassign-ca-3.png)

    > [!TIP] 
    > Aynı ilkeye sahip birden çok uygulamanız varsa Azure portalında bunları tek bir ilke altında birleştirmeyi tercih edebilirsiniz.

10. **Atamalar** kısmında bulunan **Koşullar**’ı seçin.

11. **Koşullar** dikey penceresinde **Cihaz platformları**’na gidin ve uygun cihaz platformlarını seçin.

12. Cihaz platformlarını seçme işleminizi tamamladıktan sonra **Bitti**’ye iki kere tıklayın.

    ![Intune ve Azure portalları arasında cihaz platformu kullanıcı arabirimi karşılaştırmasını gösteren resim](./media/reassign-ca-4.png)

    > [!TIP] 
    > Klasik Intune portalında tek tek platformlar seçtiyseniz bu platformları Azure portalında da seçin.

    > [!NOTE] 
    > Windows için etki alanına katılım veya uyumluluk seçeneklerini daha sonra belirtebilirsiniz.

13. **Atamalar** kısmında bulunan **Koşullar**’ı seçin.

14. **Koşullar** dikey penceresinde **İstemci uygulamalar**’ı seçin ve daha sonra uygun istemci uygulamayı seçin.

15. İstemci uygulamayı seçme işleminizi tamamladıktan sonra **Bitti**’ye iki kere tıklayın.

    ![Intune ve Azure portalları arasında istemci uygulamaları kullanıcı arabirimi karşılaştırmasını gösteren resim](./media/reassign-ca-6.png)

16. Klasik Intune portalında tarayıcı ayarlarınızı seçtiyseniz Azure portalında **Tarayıcı** ve **Mobil uygulamalar ve masaüstü istemciler**’i seçin. Klasik Intune portalında tarayıcı ayarlarını seçmediyseniz yalnızca **Mobil uygulamalar ve masaüstü istemciler**’i seçin. 

17. **Erişim denetimleri** kısmında **Ver**’e tıklayın.

18. **Erişim Denetimleri Ver**’in altında **Cihazın uyumlu olarak işaretlenmesini gerektir**’i seçin ve **Seç**’e tıklayın.

19. Etki alanına katılmış Windows cihazlar gerektiren bir ilkeniz varsa ve Intune ile kaydedilmiş ve Intune uyumlu Windows cihazlara da izin veriyorsanız **Etki alanına katılmış hizmet gerektir**, **Cihazın uyumlu olarak işaretlenmesini gerektir** ve **Seçili denetimlerden birini gerektir**’i seçin.

20. Intune’a kayıtlı ve Intune uyumlu Windows cihazlarına izin vermiyorsanız geçerli ilkeden Windows ilkesini çıkarın. Daha sonra **Cihaz platformları** **Windows** olarak ayarlı olan ayrı bir ilke oluşturun, diğer koşulları yukarıda belirtilen şekilde dahil edin ve **Erişim Denetimleri Ver**’in altında **Etki alanına katılmış cihaz gerektir**’i seçin.

21. **Yeni** koşullu erişim ilkesi dikey penceresinde **İlkeyi etkinleştir**’i açın ve sonra **Oluştur**’a tıklayın.

    ![Intune ve Azure portalları arasında koşullu erişim ilkelerini etkinleştirme kullanıcı arabirimi karşılaştırmasını gösteren resim](./media/reassign-ca-11.png)

## <a name="reassign-intune-device-based-conditional-access-policies-for-eas-clients"></a>EAS istemcilerde Intune cihaz temelli koşullu erişim ilkelerini yeniden atama

Klasik Intune portalında bir Exchange Online ilkesinin parçası olarak Exchange Active Sync ayarları yapılandırdıysanız Azure portalında ikinci bir koşullu erişim ilkesi oluşturmanız gerekir.

1. [Azure portalında koşullu erişime](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) gidin ve kimlik bilgilerinizle oturum açın.

2. **Yeni ilke**’yi seçin.

3. İlke için bir ad sağlayın.

4. **Atamalar** kısmında yeni koşullu erişim ilkesinin hedefleyeceği **Kullanıcılar ve grupları**’ı seçin.

    ![Intune ve Azure portalları arasında kullanıcı grubu kullanıcı arabirimi karşılaştırmasını gösteren resim](./media/reassign-ca-12.png)

    > [!IMPORTANT] 
    > Azure portalı için yaptığınız bu seçim, Azure portalında yaptığınızla ilişkili olmalıdır. Örneğin klasik Intune portalında tüm kullanıcıları seçtiyseniz Azure portalında da **Tüm kullanıcılar**’ı seçin. Ayrıca klasik Intune portalında **Grupları çıkar** seçeneğini seçtiyseniz bu grupları Azure portalında da dışlayın.

5. Grubunuzu belirledikten sonra **Seç**’e ve ardından **Bitti**’ye tıklayın.

6. **Atamalar** kısmındaki **Bulut uygulamaları**’nı seçin.

7. **Bulut uygulamaları** dikey penceresinde **Uygulama seç**’e tıklayın ve **Exchange Online**’ı seçin. Daha sonra **Seç** ve **Bitti**’ye tıklayın.

    ![Intune ve Azure portalları arasında bulut uygulamaları kullanıcı arabirimi karşılaştırmasını gösteren resim](./media/reassign-ca-14.png)

    > [!IMPORTANT] 
    > EAS istemciler için koşullu erişim ilkeleri, başka bulut uygulamalarını barındıramaz.

8. **Koşullar** dikey penceresinde **İstemci uygulamalar**’ı seçin ve daha sonra uygun istemci uygulamayı seçin. Intune tarafından desteklenmeyen istemcileri engellemeyi seçtiyseniz **İlkeyi yalnızca desteklenen platformlara uygula** seçeneğini kullanın.

    ![Intune ve Azure portalları arasında istemci uygulamaları kullanıcı arabirimi karşılaştırmasını gösteren resim](./media/reassign-ca-15.png)

9. İstemci uygulamayı seçme işleminizi tamamladıktan sonra **Bitti**’ye iki kere tıklayın.

10. **Erişim denetimleri** kısmında **Ver**’e tıklayın.

11. **Erişim Denetimleri Ver**’in altında **Cihazın uyumlu olarak işaretlenmesini gerektir**’i seçin ve **Seç**’e tıklayın.

    ![Intune ve Azure portalları arasında erişim verme kullanıcı arabirimi karşılaştırmasını gösteren resim](./media/reassign-ca-16.png)

12. **Yeni** koşullu erişim ilkesi dikey penceresinde **İlkeyi etkinleştir**’i açın ve sonra **Oluştur**’a tıklayın.

    ![Intune ve Azure portalları arasında koşullu erişim ilkelerini etkinleştirme kullanıcı arabirimi karşılaştırmasını gösteren resim](./media/reassign-ca-17.png)

> [!NOTE]
> **Cihaz platformları**'nı yapılandırırsanız, ilkeyi kaydetme "İlke yapılandırması desteklenmiyor" hatasıyla başarısız olur. Exchange ActiveSync, bağlanan cihazın kullandığı platformu tanımlayamaz. Bu nedenle Exchange ActiveSync cihazları için bir ilke oluştururken özel cihaz platformları yapılandırma desteklenmez.

## <a name="disable-conditional-access-policies-in-the-intune-classic-portal"></a>Klasik Intune portalında koşullu erişim ilkelerini devre dışı bırakma

Azure portalında koşullu erişim ilkelerinizi yeniden atadıktan sonra klasik Intune portalında önceden oluşturulmuş koşullu erişim ilkelerini aşamalı olarak devre dışı bırakmanız önemlidir. Ayrıca Azure portalında oluşturulan koşullu erişim ilkelerini uygulamak için aynı güvenlik grubunu kullanmanız gerekebilir.

> [!NOTE]
> Klasik Intune portalında koşullu erişim ilkelerini devre dışı bırakmadan önce bu konunun başında bulunan [Başlamadan önce](#before-you-begin) kısmına göz atın.

### <a name="to-disable-the-conditional-access-policies"></a>Koşullu erişim ilkelerini devre dışı bırakmak için

1.  [Klasik Intune portalına](https://manage.microsoft.com) gidin ve kimlik bilgilerinizle oturum açın.

2.  Soldaki menüden **İlkeler**’i seçin.

3.  **Koşullu Erişim**’i seçin ve daha sonra hangi Microsoft bulut hizmeti için (Exchange Online veya SharePoint Online gibi) ilke oluşturduysanız onu seçin.

4.  **Koşullu erişim ilkesini etkinleştir** seçeneğinin onayını kaldırın ve **Kaydet**’e tıklayın.

    ![Klasik Intune portalında koşullu erişim ilkelerini devre dışı bırakmayı gösteren resim](./media/reassign-ca-18.png)

## <a name="see-also"></a>Ayrıca bkz:

- [Intune ile koşullu erişim kullanmanın yaygın yolları](conditional-access-intune-common-ways-use.md)
- [Intune ile uygulama tabanlı koşullu erişim](app-based-conditional-access-intune.md)
- [Azure Active Directory’de Koşullu Erişim](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)
