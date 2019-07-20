---
title: iOS uygulamaları arasında veri aktarımını yönetme
titleSuffix: Microsoft Intune
description: Uygulamalar arasında veri aktarımlarını yönetmek için Microsoft Intune'da mobil uygulama yönetimi ilkelerinin nasıl kullanılacağını öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/08/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d10b2d64-8c72-4e9b-bd06-ab9d9486ba5e
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9a1e370b65d8bfd7e61562347323bf1455dfe55b
ms.sourcegitcommit: bd09decb754a832574d7f7375bad0186a22a15ab
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/19/2019
ms.locfileid: "68354307"
---
# <a name="how-to-manage-data-transfer-between-ios-apps-in-microsoft-intune"></a>Microsoft Intune’da iOS uygulamaları arasında veri aktarımını yönetme

Şirket verilerini korumaya yardımcı olmak için dosya aktarımlarını yalnızca yönettiğiniz uygulamalarla kısıtlayın. iOS uygulamalarını aşağıdaki yollarla yönetebilirsiniz:

- Uygulamalar için bir uygulama koruma ilkesi yapılandırarak, **ilkeyle yönetilen** uygulamalar çağırdığımız şirket veri kaybını önleyin. [Uygulama koruma ilkesi ile yönetebileceğiniz tüm Intune ile yönetilen uygulamalara](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) bakın.

- Uygulamaların bir mobil cihaz yönetimi (MDM) çözümüne kaydolmasını gerektiren **MDM kanalı**aracılığıyla uygulamaları dağıtın ve yönetin. Dağıttığınız uygulamalar **ilkeyle yönetilen** uygulamalar veya diğer yönetilen uygulamalar olabilir.

iOS cihazları için **Yönetimde açma** özelliği, dosya aktarımlarını yalnızca **MDM kanalı** aracılığıyla dağıtılan uygulamalar arasında gerçekleşecek şekilde sınırlandırabilir. Yapılandırma ayarları ' nda *Açık yönetim* kısıtlamaları ' nı ayarlayın ve ardından bunları MDM çözümünüzü kullanarak dağıtın.  Kullanıcı dağıtılan uygulamayı yüklediğinde, ayarladığınız kısıtlamalar uygulanır.

## <a name="use-app-protection-with-ios-apps"></a>İOS uygulamalarıyla uygulama korumasını kullanma
Şirket verilerini aşağıdaki yollarla korumak için iOS **Open Management** özelliği ile uygulama koruma ilkelerini kullanın:

- **Çalışanlara ait cihazlar herhangi bir MDM çözümü tarafından yönetilmiyor:** Uygulama koruma ilkesi ayarlarını, **uygulamanın yalnızca Ilkeyle yönetilen uygulamalara veri aktarmasına izin**verecek şekilde ayarlayabilirsiniz. Ilke ile yönetilen bir uygulamadaki *Açık* davranış, paylaşım seçenekleri olarak yalnızca diğer ilkeyle yönetilen uygulamalar sunar. Kullanıcı, ilke korumalı bir dosyayı yerel posta uygulamasında OneDrive 'dan ek olarak göndermeyi denediğinde bu dosya okunamaz.

- **MDM çözümleri tarafından yönetilen cihazlar**: Intune veya üçüncü taraf MDM çözümlerine kayıtlı cihazlarda, uygulama koruma ilkelerine sahip uygulamalar ve MDM aracılığıyla dağıtılan diğer yönetilen iOS uygulamaları arasında veri paylaşımı, Intune uygulama ilkeleri ve iOS **'Da Open Management** özelliği tarafından denetlenir. Bir MDM çözümünü kullanarak dağıttığınız uygulamaların de Intune uygulama koruma ilkeleriniz ile ilişkilendirildiğini doğrulamak için, Kullanıcı UPN ayarını aşağıdaki bölümde açıklandığı gibi yapılandırın, [Kullanıcı UPN ayarını yapılandırın](data-transfer-between-apps-manage-ios.md#configure-user-upn-setting-for-microsoft-intune-or-third-party-emm). Diğer uygulamalara veri aktarımına nasıl izin vermek istediğinizi belirtmek için, **diğer uygulamalara kuruluş verisi gönder** ' i etkinleştirin ve tercih ettiğiniz paylaşım düzeyini seçin. Uygulamanın diğer uygulamalardan veri almasına nasıl izin vermek istediğinizi belirtmek için, **diğer uygulamalardan veri al** seçeneğini etkinleştirin ve tercih ettiğiniz alan düzeyini seçin. Uygulama verilerinin alınması ve paylaşılması hakkında daha fazla bilgi için bkz. [Verileri yeniden konumlandırma ayarları](app-protection-policy-settings-ios.md#data-protection).

## <a name="configure-user-upn-setting-for-microsoft-intune-or-third-party-emm"></a>Microsoft Intune veya üçüncü taraf EMM için kullanıcı UPN ayarını yapılandırma
Kullanıcı UPN ayarını yapılandırmak, Intune veya üçüncü taraf EMM çözümü tarafından yönetilen cihazlar için **gereklidir**. UPN yapılandırması, Intune 'dan dağıttığınız uygulama koruma ilkeleriyle birlikte kullanılabilir. Aşağıdaki yordam, UPN ayarının ve elde edilen kullanıcı deneyiminin nasıl yapılandırılacağı hakkında genel bir akışdır:

1. [Azure portalında](https://portal.azure.com), iOS için [bir uygulama koruma ilkesi oluşturup bunu atayın](app-protection-policies.md). İlke ayarlarını şirket gereksinimlerinize göre yapılandırın ve bu ilkeye sahip olacak iOS uygulamalarını seçin.

2. Aşağıdaki Genelleştirilmiş adımları kullanarak, Intune veya üçüncü taraf MDM çözümünüz aracılığıyla yönetilmesini istediğiniz uygulamaları ve e-posta profilini dağıtın. Bu deneyim *Örnek 1*' de de ele alınmıştır.

3. Aşağıdaki uygulama yapılandırma ayarlarıyla uygulamayı yönetilen cihaza dağıtın:

      **anahtar** = ıntunemamupn, **değer** = <username@company.com>

      Örnek: [‘IntuneMAMUPN’, ‘janellecraig@contoso.com’]
      
     > [!NOTE]
     > Intune 'da, uygulama yapılandırma ilkesi kayıt türü, **yönetilen cihazlar**olarak ayarlanmalıdır.
     > Ayrıca, uygulamanın Intune Şirket Portalı yüklenilmesi (kullanılabilir olarak ayarlandıysa) veya cihaza gerektiği şekilde itilmesi gerekir. 

4. Intune veya üçüncü taraf MDM sağlayıcınızı kullanarak kayıtlı cihazlara, **Birlikte açma yönetimi** ilkesini dağıtın.


### <a name="example-1-admin-experience-in-intune-or-third-party-mdm-console"></a>Örnek 1: Intune veya üçüncü taraf MDM konsolunda yönetici deneyimi

1. Intune veya üçüncü taraf MDM sağlayıcınızın yönetici konsoluna gidin. Uygulama yapılandırma ayarlarını kayıtlı iOS cihazlarına dağıttığınız konsol bölümüne gidin.

2. Uygulama Yapılandırması bölümünde aşağıdaki ayarı girin:

   **anahtar** = ıntunemamupn, **değer** = <username@company.com>

   Anahtar/değer çiftinin tam söz dizimi, üçüncü taraf MDM sağlayıcınıza göre farklılık gösterebilir. Aşağıdaki tabloda, üçüncü taraf MDM sağlayıcılarının örnekleri ve anahtar/değer çifti için girmeniz gereken tam değerler gösterilmektedir.

   |Üçüncü taraf MDM sağlayıcısı| Yapılandırma Anahtarı | Değer Türü | Yapılandırma Değeri|
   | ------- | ---- | ---- | ---- |
   |Microsoft Intune| IntuneMAMUPN | Dize | {{UserPrincipalName}}|
   |VMware AirWatch| IntuneMAMUPN | Dize | {UserPrincipalName}|
   |MobileIron | IntuneMAMUPN | Dize | ${userUPN} **veya** ${userEmailAddress} |
   |Citrix uç nokta yönetimi | IntuneMAMUPN | Dize | $ {User. UserPrincipalName} |
   |ManageEngine Mobil Cihaz Yöneticisi | IntuneMAMUPN | Dize | %upn% |

> [!NOTE]  
> İOS 'ta Outlook uygulaması için, "yapılandırma tasarımcısını kullanma" seçeneğiyle bir uygulama yapılandırma Ilkesi dağıtırsanız, ilke için arka planda otomatik olarak yapılandırma anahtarı ıntunemamupn yapılandırma anahtarı yapılandırılır. [Yeni Outlook for iOS ve Android uygulama yapılandırma Ilkesi deneyimi](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/New-Outlook-for-iOS-and-Android-App-Configuration-Policy/ba-p/370481)hakkında daha fazla bilgi için bkz. genel uygulama yapılandırması. 


### <a name="example-2-end-user-experience"></a>Örnek 2: Son kullanıcı deneyimi

1. Bir Kullanıcı Microsoft Word uygulamasını bir cihaza yüklerse.

2. Kullanıcı, e-postasına erişmek için yönetilen yerel e-posta uygulamasını başlatır.

3. Kullanıcı Microsoft Word 'de yerel postadaki bir belgeyi açmaya çalışır.

4. Word uygulaması başlatıldığında, kullanıcıdan iş hesabıyla oturum açması istenir. Kullanıcının girdiği hesap, Microsoft Word uygulamasının uygulama yapılandırma ayarlarında belirttiğiniz hesapla aynı olmalıdır.

    > [!NOTE]
    > Kullanıcı kişisel hesaplarını Word 'e ekleyebilir ve kullanabilir. Kullanıcı Word 'Ü iş bağlamı dışında kullandığında uygulama koruma ilkeleri uygulanmaz. 

5. Oturum açtıktan sonra, uygulama koruma ilkesi ayarları Word uygulamasına uygulanır.

6. Veri aktarımı başarılı olur ve belge, uygulamada şirket kimliği ile etiketlenir.  Veriler bir iş bağlamında değerlendirilir ve ilke ayarları uygulanır. 

### <a name="validate-user-upn-setting-for-third-party-emm"></a>Üçüncü taraf EMM için kullanıcı UPN ayarını doğrulama

Kullanıcı UPN ayarını yapılandırdıktan sonra, iOS uygulamasının Intune uygulama koruma ilkesini alma ve bunlara uyum sağlama yeteneğini doğrulayın.

Örneğin, **uygulama PIN 'ı gerektir** ilke ayarının test edilmesi kolaydır. İlke ayarı **Evet 'e**eşitse, Kullanıcı, şirket verilerine erişebilmek IÇIN bir PIN ayarlaması veya girmesi için bir istem görmeniz gerekir.

İlk olarak iOS uygulamasına yönelik [bir uygulama koruma ilkesi oluşturup bunu atayın](app-protection-policies.md). Uygulama koruma ilkesini test etme hakkında daha fazla bilgi için bkz. [Uygulama koruma Ilkelerini doğrulama](app-protection-policies-validate.md).


## <a name="see-also"></a>Ayrıca bkz.
[Intune uygulama koruma ilkesi nedir](app-protection-policy.md)
