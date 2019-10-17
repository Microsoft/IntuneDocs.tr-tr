---
title: Azure portal koşullu erişimi geçirme
titleSuffix: Microsoft Intune
description: Klasik Intune portalında daha önce oluşturduğunuz koşullu erişim ilkelerini Azure portal olarak yeniden atayın.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/02/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 301159ad-5f7e-4fcc-86c7-f72a71701ff4
ms.reviewer: chrisgree
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 03b228795d7601647c57ea86b5adf7576b669c45
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72504570"
---
# <a name="reassign-conditional-access-policies-from-intune-classic-portal-to-the-azure-portal"></a>Koşullu erişim ilkelerini klasik Intune portalından Azure portal yeniden atama

Yeni Azure portal başlayarak, koşullu erişim, uygulama başına birden çok ilke için destek sağlar ve daha fazla özelleştirme. Klasik Intune portalında daha önce koşullu erişim ilkeleri oluşturduysanız, bunları Azure portal taşıyabilirsiniz. 

## <a name="before-you-begin"></a>Başlamadan önce

Azure portal taşımaya hazırsanız, klasik Intune portalında daha önce oluşturduğunuz koşullu erişim ilkelerini yeniden atamak için bu konudaki adımları izleyin:

- Daha önce oluşturulmuş koşullu erişim ilkelerini toplayın, böylece daha sonra yeniden atamanız gereken ayarları bilirsiniz.

- Bu ilkeleri Azure portalında yeniden oluşturmak için bu konudaki adımları takip edin.

- Yeni ilkelerin Azure portalında olması gerektiği gibi çalıştığını doğruladıktan sonra klasik Intune portalında koşullu ilkeleri devre dışı bırakın.
<br /><br />
  - Klasik Intune portalında koşullu erişim ilkelerini **devre dışı bırakmadan önce** , kullanıcıları yeni ilkeye nasıl taşıyabileceğinizi planlayın. Bunun için iki yaklaşım vardır:
<br /><br />
    - **Azure portalında oluşturulan ilkeleri uygulamak için aynı ekleme grubunu kullanın ve klasik Intune portalı tarafından uygulanan ilkelerle birlikte kullanmak üzere yeni bir çıkarma grubu oluşturun**.
      - Aşamalı olarak bazı kullanıcıları klasik portalda belirtilen çıkarma grubuna taşıyın. Bu şekilde taşımak, klasik Intune portalının hedeflediği ilkelerin uygulanmasını önler. Klasik Intune portalında uygulanan ilkelere ek olarak, Azure portalında oluşturulan ve aynı kullanıcı grubunu hedefleyen ilkeler uygulanır. 
<br /><br />
    - **Azure Portal koşullu erişim ilkelerini hedeflemek için yeni bir grup oluşturun**. Bu yaklaşımı seçerseniz şunları yapmanız gerekir:
      - Klasik Intune portalında, koşullu erişim ilkelerine hedeflenmiş güvenlik gruplarından kullanıcıları aşamalı olarak kaldırın.
      - Yeni ilkenin bu kullanıcılarda çalıştığını onayladıktan sonra klasik Intune portalında bu ilkeyi devre dışı bırakabilirsiniz. 
<br /><br />
- Klasik Intune portalında Exchange ActiveSync (EAS) kullanmak üzere yapılandırılmış koşullu erişim ilkesi ayarlarınız varsa, **Azure Portal EAS koşullu erişim ilkesi ayarlarını yeniden atamak**için [Bu konudaki yönergelere](#reassign-intune-device-based-conditional-access-policies-for-eas-clients) bakın.

### <a name="to-verify-your-device-based-conditional-access-policies-in-the-intune-classic-portal"></a>Klasik Intune portalında cihaz tabanlı koşullu erişim ilkelerinizi doğrulamak için

1. [Klasik Intune portalına](https://manage.microsoft.com) gidin ve kimlik bilgilerinizle oturum açın.

2. Soldaki menüden **İlkeler**’i seçin.

3. **Koşullu erişim**' i seçin ve daha sonra Için bir koşullu erişim Ilkesi oluşturduğunuz Microsoft bulut hizmetini (örneğin, Exchange Online veya SharePoint Online) seçin.

4. Koşullu erişim ayarlarınızı bir yere göz atın ve Azure portal aynı koşullu erişim ilkelerini oluştururken bu ayarları inceleyin.

### <a name="app-and-device-based-conditional-access-policies-working-together"></a>Birlikte çalışan uygulama ve cihaz tabanlı koşullu erişim ilkeleri

Azure portalındaki **Intune Uygulama Koruması** dikey penceresi, yöneticilerin uygulama temelli koşullu kurallar ayarlamasına imkan verir. Böylece yalnızca Intune uygulama korumasını destekleyen uygulamalar şirket kaynaklarına erişebilir. Cihaz tabanlı koşullu erişim ilkelerini kullanarak bu uygulama tabanlı koşullu erişim ilkelerinin çakışmasını seçebilirsiniz. Cihaz tabanlı ve uygulama tabanlı koşullu ilkelerini birleştirebilir (mantıksal VE) veya bu iki seçenekten yalnızca birini belirtebilirsiniz (mantıksal VEYA). Koşullu erişim ilkesi gereksinimleriniz şu şekilde yapılır:

- Uyumlu cihaz gerektir **VE** onaylı uygulamayı kullan.
  - Koşullu erişim ilkenizi [Azure Active Directory Koşullu erişim dikey penceresini](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) ve [Intune uygulama koruması dikey penceresini](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0)kullanarak ayarlamanız gerekir.
<br /><br />
- Uyumlu cihaz gerektir **VEYA** onaylı uygulamayı kullan.
  - [Klasik Intune portalını](https://manage.microsoft.com) ve [Intune uygulama koruması dikey penceresini](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0)kullanarak koşullu erişim ilkenizi ayarlamanız gerekir.

> [!TIP] 
> Bu konuda, klasik Intune portalı ve Azure portalı kullanıcı deneyimini karşılaştıran ekran görüntüleri sağlanır.

## <a name="reassign-intune-device-based-conditional-access-policies"></a>Intune cihaz tabanlı koşullu erişim ilkelerini yeniden atama

1. [Azure Portal koşullu erişime](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies)gidin ve kimlik bilgilerinizle oturum açın.

2. **Yeni ilke**’yi seçin.

3. İlke için bir ad sağlayın.

4. **Atamalar bölümünde**, yeni koşullu erişim ilkesini hedeflemek için **Kullanıcılar ve gruplar** ' ı seçin.

    ![Intune ve Azure portalları arasında Kullanıcı grubu Kullanıcı ARABIRIMINI karşılaştıran resim](./media/conditional-access-intune-reassign/reassign-ca-1.png)

    > [!IMPORTANT] 
    > Klasik portal için yaptığınız bu seçim, Azure portalında yaptığınızla ilişkili olmalıdır. Örneğin klasik Intune portalında tüm kullanıcıları seçtiyseniz Azure portalında da **Tüm kullanıcılar**’ı seçin. Ayrıca klasik Intune portalında **Grupları çıkar** seçeneğini seçtiyseniz bu grupları Azure portalında da dışlayın.

5. Grubunuzu belirledikten sonra **Seç**’e ve ardından **Bitti**’ye tıklayın.

6. **Atamalar** kısmındaki **Bulut uygulamaları**’nı seçin.

7. **Bulut uygulamaları** dikey penceresinde **Uygulama seç**’e tıklayın.

8. Yeni koşullu erişim ilkesini uygulamak istediğiniz uygulamayı seçin ve **Seç**' e tıklayın.

9. **Bitti**’ye tıklayın.

    ![Intune ve Azure portalları arasında bulut uygulaması kullanıcı arabirimi karşılaştırması](./media/conditional-access-intune-reassign/reassign-ca-3.png)

    > [!TIP] 
    > Aynı ilkeye sahip birden çok uygulamanız varsa Azure portalında bunları tek bir ilke altında birleştirmeyi tercih edebilirsiniz.

10. **Atamalar** kısmında bulunan **Koşullar**’ı seçin.

11. **Koşullar** dikey penceresinde **Cihaz platformları**’na gidin ve uygun cihaz platformlarını seçin.

12. Cihaz platformlarını seçme işleminizi tamamladıktan sonra **Bitti**’ye iki kere tıklayın.

    ![Intune ve Azure portallarından cihaz platformu kullanıcı arabirimini karşılaştıran resim](./media/conditional-access-intune-reassign/reassign-ca-4.png)

    > [!TIP] 
    > Klasik Intune portalında tek tek platformlar seçtiyseniz bu platformları Azure portalında da seçin.

    > [!NOTE] 
    > Windows için etki alanına katılım veya uyumluluk seçeneklerini daha sonra belirtebilirsiniz.

13. **Atamalar** kısmında bulunan **Koşullar**’ı seçin.

14. **Koşullar** dikey penceresinde **İstemci uygulamalar**’ı seçin ve daha sonra uygun istemci uygulamayı seçin.

15. İstemci uygulamayı seçme işleminizi tamamladıktan sonra **Bitti**’ye iki kere tıklayın.

    ![Intune ve Azure portalları arasında istemci uygulamaları kullanıcı arabirimini karşılaştıran resim](./media/conditional-access-intune-reassign/reassign-ca-6.png)

16. Klasik Intune portalında tarayıcı ayarlarınızı seçtiyseniz Azure portalında **Tarayıcı** ve **Mobil uygulamalar ve masaüstü istemciler**’i seçin. Klasik Intune portalında tarayıcı ayarlarını seçmediyseniz yalnızca **Mobil uygulamalar ve masaüstü istemciler**’i seçin. 

17. **Erişim denetimleri** kısmında **Ver**’e tıklayın.

18. **Erişim Denetimleri Ver**’in altında **Cihazın uyumlu olarak işaretlenmesini gerektir**’i seçin ve **Seç**’e tıklayın.

19. Etki alanına katılmış Windows cihazlar gerektiren bir ilkeniz varsa ve Intune ile kaydedilmiş ve Intune uyumlu Windows cihazlara da izin veriyorsanız **Etki alanına katılmış hizmet gerektir**, **Cihazın uyumlu olarak işaretlenmesini gerektir** ve **Seçili denetimlerden birini gerektir**’i seçin.

20. Intune’a kayıtlı ve Intune uyumlu Windows cihazlarına izin vermiyorsanız geçerli ilkeden Windows ilkesini çıkarın. Daha sonra **Cihaz platformları** **Windows** olarak ayarlı olan ayrı bir ilke oluşturun, diğer koşulları yukarıda belirtilen şekilde dahil edin ve **Erişim Denetimleri Ver**’in altında **Etki alanına katılmış cihaz gerektir**’i seçin.

21. **Yeni** koşullu erişim ilkesi dikey penceresinde **ilkeyi etkinleştir** ' i açın ve sonra **Oluştur**' a tıklayın.

    ![Intune ile Azure arasında koşullu erişim ilkesi Kullanıcı arabirimini karşılaştırma](./media/conditional-access-intune-reassign/reassign-ca-11.png)

## <a name="reassign-intune-device-based-conditional-access-policies-for-eas-clients"></a>EAS istemcileri için Intune cihaz tabanlı koşullu erişim ilkelerini yeniden atama

Klasik Intune portalında bir Exchange Online ilkesinin parçası olarak Exchange ActiveSync ayarlarını yapılandırdıysanız, Azure portal ikinci bir koşullu erişim ilkesi oluşturmanız gerekir.

1. [Azure Portal koşullu erişime](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies)gidin ve kimlik bilgilerinizle oturum açın.

2. **Yeni ilke**’yi seçin.

3. İlke için bir ad sağlayın.

4. **Atamalar** bölümünde, yeni koşullu erişim ilkesini hedeflemek için **Kullanıcılar ve gruplar** ' ı seçin.

    ![Azure ve Intune portalları arasında Kullanıcı grubu Kullanıcı ARABIRIMI karşılaştırmasını gösteren resim](./media/conditional-access-intune-reassign/reassign-ca-12.png)

    > [!IMPORTANT] 
    > Azure portalı için yaptığınız bu seçim, Azure portalında yaptığınızla ilişkili olmalıdır. Örneğin klasik Intune portalında tüm kullanıcıları seçtiyseniz Azure portalında da **Tüm kullanıcılar**’ı seçin. Ayrıca klasik Intune portalında **Grupları çıkar** seçeneğini seçtiyseniz bu grupları Azure portalında da dışlayın.

5. Grubunuzu belirledikten sonra **Seç**’e ve ardından **Bitti**’ye tıklayın.

6. **Atamalar** kısmındaki **Bulut uygulamaları**’nı seçin.

7. **Bulut uygulamaları** dikey penceresinde **Uygulama seç**’e tıklayın ve **Exchange Online**’ı seçin. Daha sonra **Seç** ve **Bitti**’ye tıklayın.

    ![Intune ve Azure portalları arasında bulut uygulamaları kullanıcı arabirimi karşılaştırması](./media/conditional-access-intune-reassign/reassign-ca-14.png)

    > [!IMPORTANT] 
    > EAS istemciler için Koşullu Erişim ilkeleri, başka bulut uygulamalarını barındıramaz.

8. **Koşullar** dikey penceresinde **İstemci uygulamalar**’ı seçin ve daha sonra uygun istemci uygulamayı seçin. Intune tarafından desteklenmeyen istemcileri engellemeyi seçtiyseniz **İlkeyi yalnızca desteklenen platformlara uygula** seçeneğini kullanın.

    ![Azure ve Intune portalları arasında istemci uygulamaları kullanıcı arabirimi karşılaştırmasını gösteren resim](./media/conditional-access-intune-reassign/reassign-ca-15.png)

9. İstemci uygulamayı seçme işleminizi tamamladıktan sonra **Bitti**’ye iki kere tıklayın.

10. **Erişim denetimleri** kısmında **Ver**’e tıklayın.

11. **Erişim Denetimleri Ver**’in altında **Cihazın uyumlu olarak işaretlenmesini gerektir**’i seçin ve **Seç**’e tıklayın.

    ![Intune ve Azure portalları arasında erişim verme Kullanıcı arabirimini karşılaştıran resim](./media/conditional-access-intune-reassign/reassign-ca-16.png)

12. **Yeni** koşullu erişim ilkesi dikey penceresinde **ilkeyi etkinleştir** ' i açın ve sonra **Oluştur**' a tıklayın.

    ![Intune ile Azure arasında koşullu erişim ilkesi Kullanıcı arabirimini etkinleştirme karşılaştırması](./media/conditional-access-intune-reassign/reassign-ca-17.png)

> [!NOTE]
> **Cihaz platformları**'nı yapılandırırsanız, ilkeyi kaydetme "İlke yapılandırması desteklenmiyor" hatasıyla başarısız olur. Exchange ActiveSync, bağlanan cihazın kullandığı platformu tanımlayamaz. Bu nedenle Exchange ActiveSync cihazları için bir ilke oluştururken özel cihaz platformları yapılandırma desteklenmez.

## <a name="disable-conditional-access-policies-in-the-intune-classic-portal"></a>Klasik Intune portalında koşullu erişim ilkelerini devre dışı bırakma

Koşullu erişim ilkelerinizi Azure portal yeniden atadıktan sonra klasik Intune portalında önceden oluşturulmuş koşullu erişim ilkelerini aşamalı olarak devre dışı bırakmanız önemlidir. Ayrıca, Azure portal oluşturulan koşullu erişim ilkelerini uygulamak için aynı güvenlik grubunu kullanmanız gerekebilir.

> [!NOTE]
> Klasik Intune portalında koşullu erişim ilkelerinizi devre dışı bırakmadan önce bu konunun başındaki başlamadan [önce](#before-you-begin) bölümüne bakın.

### <a name="to-disable-the-conditional-access-policies"></a>Koşullu erişim ilkelerini devre dışı bırakmak için

MDM, klasik Intune portalından kaldırıldığından, klasik bu ilkeleri görüntülemek/devre dışı bırakmak için aşağıdaki bağlantı verilmiştir:

[https://portal.azure.com/?microsoft_aad_iam_classicPolicyDontHide=true#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/ClassicPolicies](https://portal.azure.com/?microsoft_aad_iam_classicPolicyDontHide=true#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/ClassicPolicies)

## <a name="see-also"></a>Ayrıca bkz:

- [Intune ile koşullu erişim kullanmanın yaygın yolları](conditional-access-intune-common-ways-use.md)
- [Intune ile uygulama tabanlı koşullu erişim](app-based-conditional-access-intune.md)
- [Azure Active Directory’de Koşullu Erişim](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)
