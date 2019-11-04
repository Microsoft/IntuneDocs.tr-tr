---
title: iOS uygulamaları arasında veri aktarımını yönetme
titleSuffix: Microsoft Intune
description: Uygulamalar arasında veri aktarımlarını yönetmek için Microsoft Intune'da mobil uygulama yönetimi ilkelerinin nasıl kullanılacağını öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/03/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d10b2d64-8c72-4e9b-bd06-ab9d9486ba5e
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: cdc849405b7404203faa6e86d3fed1ea8e35ec43
ms.sourcegitcommit: 60f0ff6d2efbae0f2ce14b9a9f3f9267309e209b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73414630"
---
# <a name="how-to-manage-data-transfer-between-ios-apps-in-microsoft-intune"></a>Microsoft Intune’da iOS uygulamaları arasında veri aktarımını yönetme

Şirket verilerini korumaya yardımcı olmak için dosya aktarımlarını yalnızca yönettiğiniz uygulamalarla kısıtlayın. iOS uygulamalarını aşağıdaki yollarla yönetebilirsiniz:

- Uygulamalar için bir uygulama koruma ilkesi yapılandırarak iş veya okul hesapları için Kuruluş verilerini koruyun. *ilke ile yönetilen uygulamaları*çağırıyoruz.  [Uygulama koruma ilkesi ile yönetebileceğiniz tüm Intune ile yönetilen uygulamalara](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) bakın.

- Cihazların bir mobil cihaz yönetimi (MDM) çözümüne kaydolmasını gerektiren iOS cihaz yönetimi aracılığıyla uygulamaları dağıtın ve yönetin. Dağıttığınız uygulamalar *ilkeyle yönetilen uygulamalar* veya iOS tarafından yönetilen diğer uygulamalar olabilir.

Kayıtlı iOS cihazları için **Açık yönetim** özelliği, iOS tarafından yönetilen uygulamalar arasında dosya aktarımlarını sınırlayabilir. Yapılandırma ayarları ' nda *Açık yönetim* kısıtlamalarını ayarlayın ve ardından bunları MDM çözümünüzü kullanarak dağıtın.  Kullanıcı dağıtılan uygulamayı yüklediğinde, ayarladığınız kısıtlamalar uygulanır.

## <a name="use-app-protection-with-ios-apps"></a>İOS uygulamalarıyla uygulama korumasını kullanma
Aşağıdaki yollarla şirket verilerini korumak için iOS **Açık yönetim** özelliği ile uygulama koruma ilkelerini kullanın:

- **Herhangi BIR MDM çözümü tarafından yönetilmeyen cihazlar:** Uygulama koruma ilkesi ayarlarını, diğer uygulamalarla birlikte *açma* veya *Paylaşım uzantıları*aracılığıyla veri paylaşımını denetlemek için ayarlayabilirsiniz.  Bunu yapmak için, **açık/paylaşılan filtreleme değeriyle ilke ile yönetilen uygulamalar** için **Kuruluş verilerini diğer uygulamaya gönder** ayarını yapılandırın.  *İlke ile yönetilen uygulamadaki* *Açık/paylaşım* davranışı, paylaşım seçenekleri olarak yalnızca diğer *ilkeyle yönetilen uygulamalar* sunar. 

- **MDM çözümleri tarafından yönetilen cihazlar**: Intune veya üçüncü taraf MDM çözümlerine kayıtlı cihazlar için uygulama koruma ilkelerine sahip uygulamalar ve MDM aracılığıyla dağıtılan diğer yönetilen iOS uygulamaları arasında veri paylaşımı, Intune uygulama Ilkeleri ve iOS açık tarafından denetlenir  **Yönetim** özelliği. Bir MDM çözümünü kullanarak dağıttığınız uygulamaların de Intune uygulama koruma ilkeleriniz ile ilişkilendirildiğini doğrulamak için, Kullanıcı UPN ayarını aşağıdaki bölümde açıklandığı gibi yapılandırın, [Kullanıcı UPN ayarını yapılandırın](data-transfer-between-apps-manage-ios.md#configure-user-upn-setting-for-microsoft-intune-or-third-party-emm). Diğer uygulamalara veri aktarımına nasıl izin vermek istediğinizi belirtmek için, **diğer uygulamalara kuruluş verisi gönder** ' i etkinleştirin ve tercih ettiğiniz paylaşım düzeyini seçin. Uygulamanın diğer uygulamalardan veri almasına nasıl izin vermek istediğinizi belirtmek için, **diğer uygulamalardan veri al** seçeneğini etkinleştirin ve tercih ettiğiniz alan düzeyini seçin. Uygulama verilerinin alınması ve paylaşılması hakkında daha fazla bilgi için bkz. [Verileri yeniden konumlandırma ayarları](app-protection-policy-settings-ios.md#data-protection).

## <a name="configure-user-upn-setting-for-microsoft-intune-or-third-party-emm"></a>Microsoft Intune veya üçüncü taraf EMM için kullanıcı UPN ayarını yapılandırma
Kullanıcı UPN ayarını yapılandırmak, kayıtlı Kullanıcı hesabını tanımlamak için Intune veya üçüncü taraf EMM çözümü tarafından yönetilen cihazlar için **gereklidir** . UPN yapılandırması, Intune 'dan dağıttığınız uygulama koruma ilkeleriyle birlikte kullanılabilir. Aşağıdaki yordam, UPN ayarının ve elde edilen kullanıcı deneyiminin nasıl yapılandırılacağı hakkında genel bir akışdır:

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
> İOS için Outlook için, "yapılandırma Tasarımcısı 'nı kullanma" seçeneğiyle yönetilen bir cihazlar uygulama yapılandırma Ilkesi dağıtırsanız ve **yalnızca iş veya okul hesaplarına Izin ver**' i etkinleştirirseniz, ıntunemamupn yapılandırma anahtarı arka planda otomatik olarak yapılandırılır ilkesi için. Daha fazla ayrıntı [için, yeni Outlook for iOS ve Android uygulama yapılandırma Ilkesi deneyimi-genel uygulama yapılandırması](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/New-Outlook-for-iOS-and-Android-App-Configuration-Policy/ba-p/370481)konusundaki SSS bölümünde bulabilirsiniz. 


### <a name="example-2-end-user-experience"></a>Örnek 2: Son kullanıcı deneyimi

İlke ile yönetilen bir uygulamayı *işletim sistemi paylaşımıyla diğer uygulamalara* *paylaşma*

1. Bir Kullanıcı Microsoft OneDrive uygulamasını kayıtlı bir iOS cihazında açar ve iş hesabında oturum açar.  Kullanıcının girdiği hesap, Microsoft OneDrive uygulamasının uygulama yapılandırma ayarlarında belirtilen hesap UPN 'si ile aynı olmalıdır.

2. Oturum açtıktan sonra, yönetici tarafından yapılandırılan uygulama ayarları Microsoft OneDrive 'daki Kullanıcı hesabı için geçerlidir.  Bu, **işletim sistemi paylaşım değeriyle ilkeyle yönetilen uygulamalar** için **diğer uygulamalara kuruluş verileri gönder** ayarının yapılandırılmasını içerir.

3. Kullanıcı bir iş dosyasını önizleyip, iOS ile yönetilen uygulama ile birlikte açma ile paylaşmaya çalışır.  

4. Veri aktarımı başarılı olur ve veriler artık iOS yönetilen uygulamasındaki **Açık yönetim** tarafından korunur.  Intune UYGULAMASı, *ilkeyle yönetilen uygulamalar*olmayan uygulamalar için geçerlidir.

İOS ile yönetilen bir uygulamadan *, gelen kuruluş verileriyle* ilkeyle yönetilen *bir* uygulamayla *paylaşma*

1. Kullanıcı, kayıtlı bir iOS cihazında yönetilen bir e-posta profiliyle yerel posta açar.  

1. Kullanıcı yerel postadan Microsoft Word 'e bir iş belgesi eki açar.

1. Word uygulaması başlatıldığında, iki deneyimden biri oluşur:
   1. Veriler şu durumlarda Intune UYGULAMASı tarafından korunur:
      - Kullanıcı, Microsoft Word uygulamasının uygulama yapılandırma ayarlarında belirttiğiniz hesap UPN 'siyle eşleşen iş hesabında oturum açtı. 
      - Yönetici tarafından yapılandırılan uygulama ayarları, Microsoft Word 'deki Kullanıcı hesabı için geçerlidir.  Bu, **diğer uygulamalardan veri al** ayarının, **gelen kuruluş veri değerine sahip tüm uygulamalara** yapılandırılmasını içerir.
      - Veri aktarımı başarılı olur ve belge, uygulamadaki iş kimliğiyle etiketlenir.  Intune UYGULAMASı, belge için kullanıcı eylemlerini korur.
   1. Veriler şu durumlarda Intune UYGULAMASı **tarafından korunmaz:**
      - Kullanıcı **, iş hesabında oturum açmamış** .
      - Kullanıcı oturum açmamış olduğundan, yönetici tarafından yapılandırılan ayarlar Microsoft Word **'e uygulanmıyor.**
      - Veri aktarımı başarılı olur ve **belge, uygulamadaki iş kimliğiyle etiketlenemez** .  Intune UYGULAMASı, etkin olmadığından belge için kullanıcı eylemlerini **korumaz** .

    > [!NOTE]
    > Kullanıcı kişisel hesaplarını Word 'e ekleyebilir ve kullanabilir. Kullanıcı Word 'Ü iş bağlamı dışında kullandığında uygulama koruma ilkeleri uygulanmaz. 

### <a name="validate-user-upn-setting-for-third-party-emm"></a>Üçüncü taraf EMM için kullanıcı UPN ayarını doğrulama

Kullanıcı UPN ayarını yapılandırdıktan sonra, iOS uygulamasının Intune uygulama koruma ilkesini alma ve bunlara uyum sağlama yeteneğini doğrulayın.

Örneğin, **uygulama PIN 'ı gerektir** ilke ayarının test edilmesi kolaydır. İlke ayarı izin **iste**' ye eşitse, Kullanıcı şirket verilerine erişebilmek IÇIN bir PIN ayarlaması veya girmesi için bir istem görmeniz gerekir.

İlk olarak iOS uygulamasına yönelik [bir uygulama koruma ilkesi oluşturup bunu atayın](app-protection-policies.md). Uygulama koruma ilkesini test etme hakkında daha fazla bilgi için bkz. [Uygulama koruma Ilkelerini doğrulama](app-protection-policies-validate.md).


## <a name="see-also"></a>Ayrıca bkz:
[Intune uygulama koruma ilkesi nedir](app-protection-policy.md)
