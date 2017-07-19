---
title: "Koşullu erişim ilkelerini Klasik Intune portalından yeni Azure portalına geçirin."
titleSuffix: Intune on Azure
description: "Koşullu erişim ilkelerini Klasik Intune portalından yeni Azure portalına geçirin."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 301159ad-5f7e-4fcc-86c7-f72a71701ff4
ms.reviewer: chrisgree
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2450a878424d8c992a43e8028ba59b7136e1d530
ms.sourcegitcommit: fd5b7aa26446d2fa92c21638cb29371e43fe169f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2017
---
# <a name="reassign-conditional-access-policies-from-intune-classic-portal-to-the-new-azure-portal"></a>Koşullu erişim ilkelerini Klasik Intune portalından yeni Azure portalına yeniden atama

Yeni Azure portalı ile koşullu erişim, uygulama başına birden çok ilke için desteğin yanında artırılmış özelleştirilebilirlik sunuyor.

## <a name="before-you-begin"></a>Başlamadan önce

Yeni Azure portalına geçmeye hazırsanız klasik Intune portalında önceden oluşturulmuş koşullu erişim ilkelerini yeniden atamak için aşağıdaki adımları izleyebilirsiniz:

- Klasik Intune portalında önceden oluşturulmuş koşullu erişim ilkelerini toplayın, böylece daha sonra hangi ayarları yeniden atayacağınızı bilirsiniz.

- Bu ilkeleri yeni Azure portalında yeniden oluşturmak için bu konudaki adımları takip edin.

- Yeni ilkelerin yeni Azure portalında olması gerektiği gibi çalıştığını doğruladıktan sonra klasik Intune konsolunda koşullu erişim ilkelerini devre dışı bırakın.
<br /><br />
    - Klasik Intune portalında koşullu erişim ilkelerini **devre dışı bırakmadan önce**, kullanıcıları yeni ilkeye nasıl taşıyacağınızı planlayın. Bunun için iki yaklaşım vardır:
<br /><br />
        - **Yeni Azure portalında oluşturulan ilkeleri uygulamak için aynı ekleme grubunu kullanın ve klasik Intune portalı tarafından uygulanan ilkelerle birlikte kullanmak üzere yeni bir çıkarma grubu oluşturun**.
            - Aşamalı olarak bazı kullanıcıları klasik portalda belirtilen çıkarma grubuna taşıyın.  Bu şekilde taşımak, klasik Intune portalının uygulamayı hedeflediği ilkeleri önler. Yeni Azure portalında oluşturulan ve aynı kullanıcı grubunu hedefleyen ilkeler, klasik Intune portalında uygulananlara ek olarak uygulanır. 
<br /><br />
        - **Yeni Azure portalındaki koşullu ilkeleri hedefleyeceği yeni bir grup oluşturun**. Bu yaklaşımı seçerseniz şunları yapmanız gerekir:
            - Klasik Intune portalında, kendisine hedeflenen koşullu erişim ilkeleri bulunan güvenlik gruplarından kullanıcıları aşamalı olarak kaldırın.
            - Yeni ilkenin bu kullanıcılarda çalıştığını onayladıktan sonra klasik Intune portalında bu ilkeyi devre dışı bırakabilirsiniz. 
<br /><br />
- Klasik Intune portalında koşullu erişim ilkesi ayarlarınızı Exchange Active Sync (EAS) kullanmak üzere yapılandırdıysanız [bu konudaki yönergeleri](#to-reassign-intune-device-based-conditional-access-policies-for-eas-clients) izleyerek **yeni Azure portalında EAS koşullu erişim ilkesi ayarlarını yeniden atayın**.

### <a name="to-verify-your-device-based-conditional-access-policies-in-the-intune-classic-portal"></a>Cihaz temelli koşullu erişim ilkelerinizi klasik Intune portalında doğrulamak için

1.  [Klasik Intune portalına](https://manage.microsoft.com) gidin ve kimlik bilgilerinizle oturum açın.

2.  Soldaki menüden **İlkeler**’i seçin.

3.  **Koşullu Erişim**’i seçin ve daha sonra hangi Microsoft bulut hizmeti için (Exchange Online, SharePoint Online gibi) ilke oluşturduysanız onu seçin.

4.  Koşullu erişim ayarlarınızı not edin ve yeni Azure portalında aynı koşullu erişim ilkelerini oluşturmak için bu notları kullanın.

### <a name="app-and-device-based-conditional-access-policies-working-together"></a>Uygulama ve cihaz temelli koşullu erişim ilkelerinin birlikte çalışması

Yeni Azure portalındaki **Intune Uygulama Koruması** dikey penceresi, yöneticilerin uygulama temelli koşullu kurallar ayarlamasına imkan verir. Böylece yalnızca Intune uygulama korumasını destekleyen uygulamalar şirket kaynaklarına erişebilir. Cihaz temelli koşullu erişim ilkelerini kullanarak bu uygulama temelli koşullu erişim ilkelerini çakıştırmayı seçebilirsiniz. Bu, cihaz temelli ve uygulama temelli koşullu erişim ilkelerini birleştirmenize (mantıksal VE) veya bir seçenek sağlamanıza (mantıksal VEYA) bağlıdır. Koşullu erişim ilkesi gereksinimleriniz şu şekildeyse:

- Uyumlu cihaz gerektir **VE** onaylı uygulamayı kullan.
    - O halde koşullu erişim ilkenizi, [Azure AD koşullu erişim dikey penceresi](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) ve [Intune Uygulama Koruması dikey penceresi](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0) kullanarak ayarlamalısınız.
<br /><br />
- Uyumlu cihaz gerektir **VEYA** onaylı uygulamayı kullan.
    - O halde koşullu erişim ilkenizi, [klasik Intune portalı](https://manage.microsoft.com) ve [Intune Uygulama Koruması dikey penceresi](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0) kullanarak ayarlamalısınız.

> [!TIP] 
> Bu konuda, klasik Intune portalı ve yeni Azure portalı kullanıcı deneyimini karşılaştıran ekran görüntüleri sağlanmaktadır.

## <a name="to-re-assign-intune-device-based-conditional-access-policies"></a>Intune cihaz temelli koşullu erişim ilkelerini yeniden atamak için

1. [Yeni Azure portalında koşullu erişime](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) gidin ve kimlik bilgilerinizle oturum açın.

2. **Yeni ilke**’yi seçin.

3. İlke için bir ad sağlayın.

4. Yeni koşullu erişim ilkesinin hedefini belirlemek için **Atamalar** kısmında bulunan **Kullanıcılar ve grupları**’ı seçin.
    
    ![Klasik Intune ve Yeni Azure portalları arasında kullanıcı grubu kullanıcı arabirimi karşılaştırması](./media/reassign-ca-1.png)

    > [!IMPORTANT] 
    > Klasik Intune portalında tüm kullanıcıları seçtiyseniz Tüm kullanıcıları dahil edin. Bu, gruplarda da aynı şekilde geçerlidir; seçtiğiniz grupları dahil etmek için **kullanıcı ve grupları tek tek seç** komutunu belirtmeniz gerekir. Ayrıca klasik Intune portalında **Grupları çıkar** seçeneğini belirttiyseniz bu grupları yeni Azure portalında dışlamanız gerekir.

5. Grubunuzu belirledikten sonra **Seç**’e ve ardından **Bitti**’ye tıklayın.

6. **Atamalar** kısmındaki **Bulut uygulamaları**’nı seçin.

7. **Bulut uygulamaları** dikey penceresinde **Uygulama seç**’e tıklayın.

8. Yeni koşullu erişim ilkesini uygulamak istediğiniz uygulamayı belirleyin ve **Seç**’e tıklayın.

9. **Bitti**’ye tıklayın.

    ![Klasik Intune ve Yeni Azure portalları arasında bulut uygulaması kullanıcı arabirimi karşılaştırması](./media/reassign-ca-3.png)

    > [!TIP] 
    > Aynı ilkeye sahip birden çok uygulamanız varsa yeni Azure portalında bunları tek bir ilke altında birleştirmeyi tercih edebilirsiniz.

10. **Atamalar** kısmında bulunan **Koşullar**’ı seçin.

11. **Koşullar** dikey penceresinde **Cihaz platformları**’nı ve ardından uygun cihaz platformlarını seçin.

12. Cihaz platformlarını seçme işleminizi tamamladıktan sonra **Bitti**’ye iki kere tıklayın.

    ![Klasik Intune ve Yeni Azure portalları arasında cihaz platformu kullanıcı arabirimi karşılaştırması](./media/reassign-ca-4.png)

    > [!TIP] 
    > Klasik Intune portalında tek tek platformlar seçtiyseniz bu platformları yeni Azure portalında da seçin.

    > [!NOTE] 
    > Windows için etki alanına katılım veya uyumluluk seçeneklerini daha sonra belirtebilirsiniz.

13. **Atamalar** kısmında bulunan **Koşullar**’ı seçin.

14. **Koşullar** dikey penceresinde **İstemci uygulamalar**’ı seçin, daha sonra uygun istemci uygulamayı seçin.

15. İstemci uygulamasını seçme işleminizi tamamladıktan sonra **Bitti**’ye iki kere tıklayın.

    ![Klasik Intune ve Yeni Azure portalları arasında istemci uygulama kullanıcı arabirimi karşılaştırması](./media/reassign-ca-6.png)

16. Klasik Intune portalında tarayıcı ayarlarınızı seçtiyseniz yeni Azure portalında **Tarayıcı** ve **Mobil uygulamalar ve masaüstü istemciler**’i seçin. Klasik Intune portalında tarayıcı ayarlarını seçmediyseniz yalnızca **Mobil uygulamalar ve masaüstü istemciler**’i seçin. 

17. **Erişim denetimleri** kısmında **Ver**’e tıklayın.

18. **Erişim Denetimleri Ver**’in altında **Cihazın uyumlu olarak işaretlenmesini gerektir**’i seçin ve **Seç**’e tıklayın.

19. Etki alanına katılmış Windows cihazlar gerektiren bir ilkeniz varsa ve Intune ile kaydedilmiş ve Intune uyumlu Windows cihazlara da izin veriyorsanız **Etki alanına katılmış hizmet gerektir** ve **Cihazın uyumlu olarak işaretlenmesini gerektir** ile **Seçili denetimlerden birini gerektir**’i seçin.

20. Intune ile kaydedilmiş ve Intune uyumlu Windows cihazlarına izin vermiyorsanız Windows ilkesini mevcut ilkeden çıkarın ve daha sonra **Cihaz platformları** **Windows** olarak ayarlı olan ayrı bir ilke oluşturun, diğer koşulları yukarıda belirtilen şekilde dahil edin ve **Erişim Denetimleri Ver**’in altında **Etki alanına katılmış hizmet gerektir**’i seçin.

21. **Yeni** koşullu erişim ilkesi dikey penceresinde **İlkeyi etkinleştir**’i açın ve sonra **Oluştur**’a tıklayın.

    ![Klasik Intune ve Yeni Azure portalları arasında CA ilkesi kullanıcı etkinleştirme arabirim karşılaştırması](./media/reassign-ca-11.png)

## <a name="to-reassign-intune-device-based-conditional-access-policies-for-eas-clients"></a>EAS istemcilerde Intune cihaz temelli koşullu erişim ilkelerini yeniden atamak için

Klasik Intune portalında bir Exchange Online ilkesinin parçası olarak Exchange Active Sync (EAS) ayarları yapılandırdıysanız yeni Azure portalında ikinci bir koşullu erişim ilkesi oluşturmanız gerekir.

1. [Yeni Azure portalında koşullu erişime](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) gidin ve kimlik bilgilerinizle oturum açın.

2. **Yeni ilke**’yi seçin.

3. İlke için bir ad sağlayın.

4. Yeni koşullu erişim ilkesinin hedefini belirlemek için **Atamalar** kısmında bulunan **Kullanıcılar ve grupları**’ı seçin.

    ![Klasik Intune ve Yeni Azure portalları arasında kullanıcı grubu kullanıcı arabirimi karşılaştırması](./media/reassign-ca-12.png)

    > [!IMPORTANT] 
    > Klasik Intune portalında tüm kullanıcıları seçtiyseniz Tüm kullanıcıları dahil edin. Bu, gruplarda da aynı şekilde geçerlidir; seçtiğiniz grupları dahil etmek için **kullanıcı ve grupları tek tek seç** komutunu belirtmeniz gerekir. Ayrıca klasik Intune portalında **Grupları çıkar** seçeneğini belirttiyseniz bu grupları yeni Azure portalında dışlamanız gerekir.

5. Grubunuzu belirledikten sonra **Seç**’e ve ardından **Bitti**’ye tıklayın.

6. **Atamalar** kısmındaki **Bulut uygulamaları**’nı seçin.

7. **Bulut uygulamaları** dikey penceresinde **Seçili uygulamalar**’a tıklayın, **Exchange Online**’ı seçin, **Seç**’e ve ardından **Bitti**’ye tıklayın.

    ![Klasik Intune ve Yeni Azure portalları arasında bulut uygulamaları kullanıcı arabirimi karşılaştırması](./media/reassign-ca-14.png)

    > [!IMPORTANT] 
    > EAS istemciler için Koşullu Erişim ilkeleri, başka bulut uygulamalarını barındıramaz.

8. **Koşullar** dikey penceresinde **İstemci uygulamalar**’ı seçin, daha sonra uygun istemci uygulamayı seçin. Intune tarafından desteklenmeyen istemcileri engellemeyi seçtiyseniz **İlkeyi yalnızca desteklenen platformlara uygula** seçeneğini kullanın.

    ![Klasik Intune ve Yeni Azure portalları arasında istemci uygulama kullanıcı arabirimi karşılaştırması](./media/reassign-ca-15.png)

9. İstemci uygulamasını seçme işleminizi tamamladıktan sonra **Bitti**’ye iki kere tıklayın.

10. **Erişim denetimleri** kısmında **Ver**’e tıklayın.

11. **Erişim Denetimleri Ver**’in altında **Cihazın uyumlu olarak işaretlenmesini gerektir**’i seçin ve **Seç**’e tıklayın.

    ![Klasik Intune ve Yeni Azure portalları arasında erişim verme kullanıcı arabirimi karşılaştırması](./media/reassign-ca-16.png)

12. **Yeni** koşullu erişim ilkesi dikey penceresinde **İlkeyi etkinleştir**’i açın ve sonra **Oluştur**’a tıklayın.

    ![Klasik Intune ve Yeni Azure portalları arasında CA ilkesi kullanıcı etkinleştirme arabirim karşılaştırması](./media/reassign-ca-17.png)

## <a name="disable-conditional-access-policies-in-the-intune-classic-portal"></a>Klasik Intune portalında koşullu erişim ilkelerini devre dışı bırakma
### <a name="before-you-start"></a>Başlamadan önce

Yeni Azure portalında koşullu erişim ilkelerinizi yeniden atadıktan sonra klasik Intune portalında önceden oluşturulmuş koşullu erişim ilkelerini aşamalı olarak devre dışı bırakmanız önemlidir. Ayrıca yeni Azure portalında oluşturulan koşullu erişim ilkelerini uygulamak için aynı güvenlik grubunu kullanmanız gerekebilir

- Klasik Intune portalında koşullu erişim ilkelerini devre dışı bırakmadan önce bu konunun başında bulunan [başlamadan önce](#before-you-begin) kısmına göz atın.

### <a name="to-disable-the-conditional-access-policies"></a>Koşullu erişim ilkelerini devre dışı bırakmak için

1.  [Klasik Intune portalına](https://manage.microsoft.com) gidin ve kimlik bilgilerinizle oturum açın.

2.  Soldaki menüden **İlkeler**’i seçin.

3.  **Koşullu Erişim**’i seçin ve daha sonra hangi Microsoft bulut hizmeti için (Exchange Online, SharePoint Online gibi) ilke oluşturduysanız onu seçin.

4.  **Koşullu erişim ilkesini etkinleştir** seçeneğinin onayını kaldırın ve **Kaydet**’e tıklayın.

    ![Klasik Intune portalında koşullu erişim ilkelerini devre dışı bırakma](./media/reassign-ca-18.png)

## <a name="see-also"></a>Ayrıca bkz.

- [Intune ile koşullu erişim kullanmanın yaygın yolları](conditional-access-intune-common-ways-use.md)
- [Intune ile uygulama tabanlı koşullu erişim](app-based-conditional-access-intune.md)
- [Azure Active Directory’de Koşullu Erişim](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)