---
title: Azure portalında koşullu erişim geçişi
titleSuffix: Microsoft Intune
description: Azure portalında Klasik Intune portalında önceden oluşturulmuş koşullu erişim ilkelerini yeniden atama.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/02/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 301159ad-5f7e-4fcc-86c7-f72a71701ff4
ms.reviewer: chrisgree
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8bcc9aa527ed27ef35db901117ceb8f4c8d10c97
ms.sourcegitcommit: bccfbf1e3bdc31382189fc4489d337d1a554e6a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/03/2019
ms.locfileid: "67546893"
---
# <a name="reassign-conditional-access-policies-from-intune-classic-portal-to-the-azure-portal"></a>Azure portalında Klasik Intune portalından koşullu erişim ilkelerini yeniden atama

Yeni Azure portalında koşullu erişim özelleştirilebilirlik, uygulama başına birden çok ilke için destek sunuyor. Önceden Klasik Intune portalında koşullu erişim ilkeleri oluşturduysanız, bunları Azure portalına geçirebilirsiniz. 

## <a name="before-you-begin"></a>Başlamadan önce

Azure portalına geçmeye hazırsanız Klasik Intune portalında önceden oluşturulmuş koşullu erişim ilkelerini yeniden atamak için bu konudaki adımları izleyin:

- Önceden oluşturulmuş koşullu erişim ilkelerini toplayın, hangi ayarları bilmeniz böylece daha sonra yeniden atamanız gerekir.

- Bu ilkeleri Azure portalında yeniden oluşturmak için bu konudaki adımları takip edin.

- Yeni ilkelerin Azure portalında olması gerektiği gibi çalıştığını doğruladıktan sonra klasik Intune portalında koşullu ilkeleri devre dışı bırakın.
<br /><br />
    - **Devre dışı bırakmadan önce** koşullu erişim ilkelerini Klasik Intune portalında, nasıl, kullanıcıları yeni ilkeye taşıyacağınızı planlayın. Bunun için iki yaklaşım vardır:
<br /><br />
        - **Azure portalında oluşturulan ilkeleri uygulamak için aynı ekleme grubunu kullanın ve klasik Intune portalı tarafından uygulanan ilkelerle birlikte kullanmak üzere yeni bir çıkarma grubu oluşturun**.
            - Aşamalı olarak bazı kullanıcıları klasik portalda belirtilen çıkarma grubuna taşıyın. Bu şekilde taşımak, klasik Intune portalının hedeflediği ilkelerin uygulanmasını önler. Klasik Intune portalında uygulanan ilkelere ek olarak, Azure portalında oluşturulan ve aynı kullanıcı grubunu hedefleyen ilkeler uygulanır. 
<br /><br />
        - **Azure portalında koşullu erişim ilkeleri hedefleyeceği yeni bir grup oluşturun**. Bu yaklaşımı seçerseniz şunları yapmanız gerekir:
            - Aşamalı olarak koşullu erişim ilkeleri için bunları Klasik Intune portalında hedeflenen güvenlik gruplarından kullanıcıları kaldırın.
            - Yeni ilkenin bu kullanıcılarda çalıştığını onayladıktan sonra klasik Intune portalında bu ilkeyi devre dışı bırakabilirsiniz. 
<br /><br />
- Klasik Intune portalında Exchange ActiveSync (EAS) kullanmak üzere yapılandırdıysanız, koşullu erişim ilkesi ayarlarınızı varsa [bu konudaki yönergeler](#reassign-intune-device-based-conditional-access-policies-for-eas-clients) için **, EAS koşullu erişim ilkesi ayarlarını yeniden atayın Azure portalında**.

### <a name="to-verify-your-device-based-conditional-access-policies-in-the-intune-classic-portal"></a>Cihaz tabanlı koşullu erişim ilkelerini Klasik Intune portalında doğrulamak için

1. [Klasik Intune portalına](https://manage.microsoft.com) gidin ve kimlik bilgilerinizle oturum açın.

2. Soldaki menüden **İlkeler**’i seçin.

3. Seçin **koşullu erişim**, ve seçip Microsoft bulut hizmeti (örneğin, Exchange Online veya SharePoint Online) için bir koşullu erişim ilkesi oluşturdunuz.

4. Koşullu erişim ayarlarınızı not edin ve Azure portalında aynı koşullu erişim ilkelerini oluştururken başvurun.

### <a name="app-and-device-based-conditional-access-policies-working-together"></a>Uygulama ve cihaz tabanlı koşullu erişim ilkeleriyle birlikte çalışma

Azure portalındaki **Intune Uygulama Koruması** dikey penceresi, yöneticilerin uygulama temelli koşullu kurallar ayarlamasına imkan verir. Böylece yalnızca Intune uygulama korumasını destekleyen uygulamalar şirket kaynaklarına erişebilir. Cihaz tabanlı koşullu erişim ilkelerini kullanarak bu uygulama tabanlı koşullu erişim ilkelerini çakıştırmayı seçebilirsiniz. Cihaz tabanlı ve uygulama tabanlı koşullu ilkelerini birleştirebilir (mantıksal VE) veya bu iki seçenekten yalnızca birini belirtebilirsiniz (mantıksal VEYA). Koşullu erişim ilkesi gereksinimleriniz şu şekildeyse:

- Uyumlu cihaz gerektir **VE** onaylı uygulamayı kullan.
    - Koşullu erişim ilkenizi kullanarak ayarlamalısınız [Azure Active Directory koşullu erişim dikey penceresi](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) ve [Intune uygulama koruması dikey penceresi](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0).
<br /><br />
- Uyumlu cihaz gerektir **VEYA** onaylı uygulamayı kullan.
    - Koşullu erişim ilkenizi kullanarak ayarlamalısınız [Klasik Intune portalında](https://manage.microsoft.com) ve [Intune uygulama koruması dikey penceresi](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0).

> [!TIP] 
> Bu konuda, klasik Intune portalı ve Azure portalı kullanıcı deneyimini karşılaştıran ekran görüntüleri sağlanır.

## <a name="reassign-intune-device-based-conditional-access-policies"></a>Intune cihaz temelli koşullu erişim ilkelerini yeniden atama

1. Git [Azure portalında koşullu erişim](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies)ve kimlik bilgilerinizle oturum açın.

2. **Yeni ilke**’yi seçin.

3. İlke için bir ad sağlayın.

4. Altında **atamalar kısmında**, seçin **kullanıcılar ve gruplar** yeni koşullu erişim ilkesinin hedefleyeceği.

    ![Görüntü karşılaştırır, kullanıcı grubu Intune ve Azure portalları arasında kullanıcı Arabirimi](./media/reassign-ca-1.png)

    > [!IMPORTANT] 
    > Klasik portal için yaptığınız bu seçim, Azure portalında yaptığınızla ilişkili olmalıdır. Örneğin klasik Intune portalında tüm kullanıcıları seçtiyseniz Azure portalında da **Tüm kullanıcılar**’ı seçin. Ayrıca klasik Intune portalında **Grupları çıkar** seçeneğini seçtiyseniz bu grupları Azure portalında da dışlayın.

5. Grubunuzu belirledikten sonra **Seç**’e ve ardından **Bitti**’ye tıklayın.

6. **Atamalar** kısmındaki **Bulut uygulamaları**’nı seçin.

7. **Bulut uygulamaları** dikey penceresinde **Uygulama seç**’e tıklayın.

8. Yeni koşullu Erişim İlkesi Uygula ve istediğiniz uygulamayı seçin **seçin**.

9. **Bitti**’ye tıklayın.

    ![Intune ve Azure portalları arasında bulut uygulaması kullanıcı Arabirimi karşılaştırmasını görüntüsü](./media/reassign-ca-3.png)

    > [!TIP] 
    > Aynı ilkeye sahip birden çok uygulamanız varsa Azure portalında bunları tek bir ilke altında birleştirmeyi tercih edebilirsiniz.

10. **Atamalar** kısmında bulunan **Koşullar**’ı seçin.

11. **Koşullar** dikey penceresinde **Cihaz platformları**’na gidin ve uygun cihaz platformlarını seçin.

12. Cihaz platformlarını seçme işleminizi tamamladıktan sonra **Bitti**’ye iki kere tıklayın.

    ![Intune ve Azure Portalı'ndan cihaz platformu kullanıcı Arabirimi karşılaştıran resim](./media/reassign-ca-4.png)

    > [!TIP] 
    > Klasik Intune portalında tek tek platformlar seçtiyseniz bu platformları Azure portalında da seçin.

    > [!NOTE] 
    > Windows için etki alanına katılım veya uyumluluk seçeneklerini daha sonra belirtebilirsiniz.

13. **Atamalar** kısmında bulunan **Koşullar**’ı seçin.

14. **Koşullar** dikey penceresinde **İstemci uygulamalar**’ı seçin ve daha sonra uygun istemci uygulamayı seçin.

15. İstemci uygulamayı seçme işleminizi tamamladıktan sonra **Bitti**’ye iki kere tıklayın.

    ![İstemci uygulamaları Intune ve Azure portalları arasında kullanıcı Arabirimi karşılaştıran resim](./media/reassign-ca-6.png)

16. Klasik Intune portalında tarayıcı ayarlarınızı seçtiyseniz Azure portalında **Tarayıcı** ve **Mobil uygulamalar ve masaüstü istemciler**’i seçin. Klasik Intune portalında tarayıcı ayarlarını seçmediyseniz yalnızca **Mobil uygulamalar ve masaüstü istemciler**’i seçin. 

17. **Erişim denetimleri** kısmında **Ver**’e tıklayın.

18. **Erişim Denetimleri Ver**’in altında **Cihazın uyumlu olarak işaretlenmesini gerektir**’i seçin ve **Seç**’e tıklayın.

19. Etki alanına katılmış Windows cihazlar gerektiren bir ilkeniz varsa ve Intune ile kaydedilmiş ve Intune uyumlu Windows cihazlara da izin veriyorsanız **Etki alanına katılmış hizmet gerektir**, **Cihazın uyumlu olarak işaretlenmesini gerektir** ve **Seçili denetimlerden birini gerektir**’i seçin.

20. Intune’a kayıtlı ve Intune uyumlu Windows cihazlarına izin vermiyorsanız geçerli ilkeden Windows ilkesini çıkarın. Daha sonra **Cihaz platformları** **Windows** olarak ayarlı olan ayrı bir ilke oluşturun, diğer koşulları yukarıda belirtilen şekilde dahil edin ve **Erişim Denetimleri Ver**’in altında **Etki alanına katılmış cihaz gerektir**’i seçin.

21. Üzerinde **yeni** koşullu erişim ilkesi dikey penceresinde açma **ilkesini etkinleştir** değiştirin ve ardından **Oluştur**.

    ![Koşullu erişimi etkinleştir ilkesini Intune ve Azure arasında kullanıcı Arabirimi karşılaştırması](./media/reassign-ca-11.png)

## <a name="reassign-intune-device-based-conditional-access-policies-for-eas-clients"></a>EAS istemcilerde Intune cihaz temelli koşullu erişim ilkelerini yeniden atama

Klasik Intune portalında bir Exchange Online ilkesinin parçası olarak Exchange ActiveSync ayarları yapılandırdıysanız Azure portalında ikinci bir koşullu erişim ilkesi oluşturmanız gerekir.

1. Git [Azure portalında koşullu erişim](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies)ve kimlik bilgilerinizle oturum açın.

2. **Yeni ilke**’yi seçin.

3. İlke için bir ad sağlayın.

4. Altında **atamaları** bölümünde, seçin **kullanıcılar ve gruplar** yeni koşullu erişim ilkesinin hedefleyeceği.

    ![Bir Azure ve Intune portalları arasında kullanıcı grubu kullanıcı Arabirimi karşılaştırmasını gösteren resim](./media/reassign-ca-12.png)

    > [!IMPORTANT] 
    > Azure portalı için yaptığınız bu seçim, Azure portalında yaptığınızla ilişkili olmalıdır. Örneğin klasik Intune portalında tüm kullanıcıları seçtiyseniz Azure portalında da **Tüm kullanıcılar**’ı seçin. Ayrıca klasik Intune portalında **Grupları çıkar** seçeneğini seçtiyseniz bu grupları Azure portalında da dışlayın.

5. Grubunuzu belirledikten sonra **Seç**’e ve ardından **Bitti**’ye tıklayın.

6. **Atamalar** kısmındaki **Bulut uygulamaları**’nı seçin.

7. **Bulut uygulamaları** dikey penceresinde **Uygulama seç**’e tıklayın ve **Exchange Online**’ı seçin. Daha sonra **Seç** ve **Bitti**’ye tıklayın.

    ![Intune ve Azure portalları arasında bulut uygulamaları kullanıcı Arabirimi karşılaştırmasını görüntüsü](./media/reassign-ca-14.png)

    > [!IMPORTANT] 
    > EAS istemciler için Koşullu Erişim ilkeleri, başka bulut uygulamalarını barındıramaz.

8. **Koşullar** dikey penceresinde **İstemci uygulamalar**’ı seçin ve daha sonra uygun istemci uygulamayı seçin. Intune tarafından desteklenmeyen istemcileri engellemeyi seçtiyseniz **İlkeyi yalnızca desteklenen platformlara uygula** seçeneğini kullanın.

    ![Bir istemci uygulamaları Azure ve Intune portalları arasında kullanıcı Arabirimi karşılaştırmasını gösteren resim](./media/reassign-ca-15.png)

9. İstemci uygulamayı seçme işleminizi tamamladıktan sonra **Bitti**’ye iki kere tıklayın.

10. **Erişim denetimleri** kısmında **Ver**’e tıklayın.

11. **Erişim Denetimleri Ver**’in altında **Cihazın uyumlu olarak işaretlenmesini gerektir**’i seçin ve **Seç**’e tıklayın.

    ![UI Intune ve Azure portalları arasında erişim verme karşılaştıran resim](./media/reassign-ca-16.png)

12. Üzerinde **yeni** koşullu erişim ilkesi dikey penceresinde açma **ilkesini etkinleştir** değiştirin ve ardından **Oluştur**.

    ![Koşullu erişimi etkinleştir ilkesini Intune ve Azure arasında kullanıcı Arabirimi karşılaştırması](./media/reassign-ca-17.png)

> [!NOTE]
> **Cihaz platformları**'nı yapılandırırsanız, ilkeyi kaydetme "İlke yapılandırması desteklenmiyor" hatasıyla başarısız olur. Exchange ActiveSync, bağlanan cihazın kullandığı platformu tanımlayamaz. Bu nedenle Exchange ActiveSync cihazları için bir ilke oluştururken özel cihaz platformları yapılandırma desteklenmez.

## <a name="disable-conditional-access-policies-in-the-intune-classic-portal"></a>Klasik Intune portalında koşullu erişim ilkelerini devre dışı bırakın

Azure portalında koşullu erişim ilkelerinizi yeniden atadıktan sonra Klasik Intune portalında önceden oluşturulmuş koşullu erişim ilkelerini aşamalı olarak devre dışı önemlidir. Ayrıca, Azure portalında oluşturulan koşullu erişim ilkelerini uygulamak için aynı güvenlik grubunu kullanmanız gerekebilir.

> [!NOTE]
> Klasik Intune portalında koşullu erişim ilkelerinizi devre dışı bırakmadan önce bkz [başlamadan önce](#before-you-begin) bu konunun başında bölümünde.

### <a name="to-disable-the-conditional-access-policies"></a>Koşullu erişim ilkelerini devre dışı bırakmak için

1. [Klasik Intune portalına](https://manage.microsoft.com) gidin ve kimlik bilgilerinizle oturum açın.

2. Soldaki menüden **İlkeler**’i seçin.

3. Seçin **koşullu erişim**ve ardından oluşturduğunuz koşullu erişim ilkesi için Microsoft bulut hizmeti (örneğin, Exchange Online veya SharePoint Online) seçin.

4. Seçeneğinin işaretini kaldırın **koşullu erişimi etkinleştir ilkesini**ve ardından **Kaydet**.

    ![Devre dışı koşullu erişim ilkelerini Klasik Intune portalında görüntüsü](./media/reassign-ca-18.png)

## <a name="see-also"></a>Ayrıca bkz.

- [Intune ile koşullu erişim kullanmanın yaygın yolları](conditional-access-intune-common-ways-use.md)
- [Intune ile uygulama tabanlı koşullu erişim](app-based-conditional-access-intune.md)
- [Azure Active Directory’de Koşullu Erişim](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)
