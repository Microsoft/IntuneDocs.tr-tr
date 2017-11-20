---
title: "iOS uygulamaları arasında veri aktarımını yönetme"
titlesuffix: Azure portal
description: "Bu konuyu, uygulamalar arasındaki veri aktarımlarını yönetmek amacıyla iOS Birlikte açma özelliğini ve mobil uygulama yönetimi ilkelerini nasıl kullanabileceğinizi anlamak için kullanın.\""
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d10b2d64-8c72-4e9b-bd06-ab9d9486ba5e
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3e4dcd7767620d6d3939686f69ad9d72f6a2d8e2
ms.sourcegitcommit: e692be57ec7044dfc224b70941affbfd7efba421
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/08/2017
---
# <a name="how-to-manage-data-transfer-between-ios-apps"></a>iOS uygulamaları arasında veri aktarımını yönetme
## <a name="manage-ios-apps"></a>iOS uygulamalarını yönetme
Şirket verilerinizin korunması, dosya aktarımlarının tarafınızdan yönetilen uygulamalarla kısıtlanmasını da içerir.  iOS uygulamalarını aşağıdaki yollarla yönetebilirsiniz:

-   Uygulamalar için uygulama koruma ilkesi yapılandırarak şirkette veri kaybını önleyin. Biz buna **ilkeyle yönetilen** uygulamalar diyeceğiz. [Uygulama koruma ilkesi ile yönetebileceğiniz tüm Intune kullanan uygulamalara](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) bakın.

-   Uygulamaları **MDM kanalı** üzerinden de dağıtıp yönetebilirsiniz.  Bunun için cihazların MDM çözümüne kaydedilmesi gerekir. Bunlar **ilkeyle yönetilen** uygulamaları veya diğer yönetilen uygulamalar olabilir.

iOS cihazları için **Yönetimde açma** özelliği, dosya aktarımlarını yalnızca **MDM kanalı** aracılığıyla dağıtılan uygulamalar arasında gerçekleşecek şekilde sınırlandırabilir. Yönetimde açma kısıtlamaları, yapılandırma ayarlarında belirlenir ve MDM çözümünüz aracılığıyla dağıtılır.  Kullanıcı dağıtılan uygulamayı yüklendiğinde, ayarladığınız kısıtlamalar uygulanır.

##  <a name="using-app-protection-with-ios-apps"></a>Uygulama korumayı iOS uygulamalarıyla kullanma
Uygulama koruma ilkeleri iOS **Yönetimde açma** özelliğiyle birlikte kullanıldığında, şirket verileri aşağıdaki yollarla korunabilir:

-   **Herhangi bir MDM çözümüyle yönetilmeyen, çalışana ait cihazlar:** Uygulama koruma ilkesi ayarlarını **Uygulamanın yalnızca İlkeyle Yönetilen uygulamalara veri aktarmasına izin ver** olarak belirleyebilirsiniz. İlkeyle Yönetilen bir uygulamadaki İçinde Açma davranışı, diğer İlkeyle Yönetilen uygulamaları yalnızca bir paylaşım seçeneği olarak sunar. Bir kullanıcı, ilkeyle korunan bir dosyayı yerel postada OneDrive'dan bir ek olarak göndermeye çalışırsa, dosya okunamaz hale gelir.

-   **Intune tarafından yönetilen cihazlar:** Intune’a kayıtlı cihazlar için, uygulama koruma ilkelerine sahip uygulamalarla Intune aracılığıyla dağıtılan diğer yönetilen iOS uygulamaları arasında veri aktarımına otomatik olarak izin verilir. Uygulamak koruma ilkelerine sahip uygulamalar arasında veri aktarımına izin vermek için, **Uygulamanın yalnızca yönetilen uygulamalara veri aktarmasına izin ver** ayarını etkinleştirin. **Yönetimde açma** özelliğini kullanarak Intune aracılığıyla dağıtılmış uygulamalar arasındaki veri aktarımını denetleyebilirsiniz.   

-   **Üçüncü taraf MDM çözümü tarafından yönetilen cihazlar:** iOS **Yönetimde açma** özelliğini kullanarak veri aktarımını yalnızca yönetilen uygulamalarla kısıtlayabilirsiniz.
Üçüncü taraf MDM çözümünüzü kullanarak dağıttığınız uygulamaların Intune’da yapılandırdığınız uygulama koruma ilkeleriyle de ilişkilendirildiğinden emin olmak için, [Kullanıcı UPN ayarını yapılandırma](#configure-user-upn-setting-for-third-party-emm) yönergesinde açıklandığı gibi kullanıcı UPN ayarını yapılandırmalısınız.  Uygulamalar kullanıcı UPN ayarı ile dağıtılırken, son kullanıcı iş hesabını kullanarak oturum açtığında uygulamaya uygulama koruma ilkeleri uygulanır.

## <a name="configure-user-upn-setting-for-microsoft-intune-or-third-party-emm"></a>Microsoft Intune veya üçüncü taraf EMM için kullanıcı UPN ayarını yapılandırma
Kullanıcı UPN ayarını yapılandırmak, Intune veya üçüncü taraf EMM çözümü tarafından yönetilen cihazlar için **gereklidir**. Aşağıda açıklanan yordam, UPN ayarının nasıl yapılandırılacağı ve ortaya çıkan son kullanıcı deneyimi hakkında genel bir bakış sunar:

1.  [Azure portalında](https://portal.azure.com), iOS için [bir uygulama koruma ilkesi oluşturup bunu atayın](app-protection-policies.md). İlke ayarlarını şirket gereksinimlerinize göre yapılandırın ve bu ilkeye sahip olacak iOS uygulamalarını seçin.

2.  Aşağıda genelleştirilen adımları kullanarak, Intune veya üçüncü taraf MDM çözümünüz aracılığıyla yönetilmesini istediğiniz uygulamaları ve e-posta profilini dağıtın. Bu deneyim Örnek 1’de de ele alınmıştır.

3.  Uygulamayı, aşağıdaki uygulama yapılandırma ayarlarıyla dağıtın:

      **anahtar** = IntuneMAMUPN,  **değer** = <username@company.com>

      Örnek: [‘IntuneMAMUPN’, ‘jondoe@microsoft.com’]

4.  Intune veya üçüncü taraf MDM sağlayıcınızı kullanarak kayıtlı cihazlara, **Birlikte açma yönetimi** ilkesini dağıtın.


### <a name="example-1-admin-experience-in-intune-or-third-party-mdm-console"></a>Örnek 1: Intune veya üçüncü taraf MDM konsolunda yönetici deneyimi

1. Intune veya üçüncü taraf MDM sağlayıcınızın yönetici konsoluna gidin. Uygulama yapılandırma ayarlarını kayıtlı iOS cihazlarına dağıttığınız konsol bölümüne gidin.

2. Uygulama Yapılandırması bölümünde aşağıdaki ayarı girin:

  **anahtar** = IntuneMAMUPN,  **değer** = <username@company.com>

  Anahtar/değer çiftinin tam söz dizimi, üçüncü taraf MDM sağlayıcınıza göre farklılık gösterebilir. Aşağıdaki tabloda, üçüncü taraf MDM sağlayıcıları ve anahtar/değer çifti için tam olarak girmeniz gereken değer örnekleri yer almaktadır.

|Üçüncü taraf MDM sağlayıcısı| Yapılandırma Anahtarı | Değer Türü | Yapılandırma Değeri|
| ------- | ---- | ---- | ---- |
|Microsoft Intune| IntuneMAMUPN | Dize | {UserPrincipalName}|
|VMware AirWatch| IntuneMAMUPN | Dize | {UserPrincipalName}|
|MobileIron | IntuneMAMUPN | Dize | ${userUPN} **veya** ${userEmailAddress} |


### <a name="example-2-end-user-experience"></a>Örnek 2: Son kullanıcı deneyimi

1.  Son kullanıcı cihaza Microsoft Word uygulamasını yükler.

2.  Son kullanıcı, e-postasına erişmek için yönetilen yerel e-posta uygulamasını başlatır.

3.  Son kullanıcı Microsoft Word’de yerel postadan belgeyi açmaya çalışır.

4.  Word uygulaması başlatıldığında son kullanıcıdan kendi iş hesabını kullanarak oturum açması istenir.  İstendiğinde son kullanıcının girdiği bu iş hesabı, Microsoft Word uygulaması için uygulama yapılandırma ayarlarında belirttiğiniz hesapla eşleşmelidir.

    > [!NOTE]
    > Son kullanıcı kişisel çalışmaları için Word’e başka kişisel hesaplar ekleyebilir ve Word uygulamasını kişisel bağlamda kullanırken uygulama koruma ilkelerinden etkilenmez.

5.  Oturum açma başarılı olduğunda uygulama koruma ilkesi ayarları Word uygulamasına uygulanır.

6.  Veri aktarımı başarılı olur ve belge, uygulamada şirket kimliği ile etiketlenir. Ayrıca, veriler iş bağlamında ele alınır ve ilke ayarları buna göre uygulanır.

### <a name="validate-user-upn-setting-for-third-party-emm"></a>Üçüncü taraf EMM için kullanıcı UPN ayarını doğrulama

Kullanıcı UPN ayarını yapılandırdıktan sonra, iOS uygulamasının Intune uygulama koruma ilkesi alabildiğini ve buna uyabildiğini doğrulamalısınız.

Örneğin, **Uygulama PIN’i iste** ilke ayarını bir cihazda görsel olarak test etmek kolaydır. İlke ayarı **Evet**’e ayarlıysa son kullanıcı, şirket verilerine erişmeye çalıştığında bir PIN ayarlaması veya girmesi gerektiğini belirten bir istem görmelidir.

İlk olarak iOS uygulamasına yönelik [bir uygulama koruma ilkesi oluşturup bunu atayın](app-protection-policies.md). Uygulama koruma ilkesini test etme hakkında daha fazla bilgi için bkz. [Uygulama koruma ilkelerini doğrulama](app-protection-policies-validate.md).


### <a name="see-also"></a>Ayrıca bkz.
[Intune uygulama koruma ilkesi nedir](app-protection-policy.md)
