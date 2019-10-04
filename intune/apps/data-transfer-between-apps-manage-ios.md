---
title: İOS uygulamaları arasında veri aktarımını yönetme
titleSuffix: Microsoft Intune
description: Uygulamalar arasındaki veri aktarımlarını yönetmek için Microsoft Intune 'de mobil uygulama yönetimi ilkelerinin nasıl kullanılacağını anlayın.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/03/2019
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
ms.openlocfilehash: b9b93ec96eb6480c04514f1505a787332dd13625
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71940018"
---
# <a name="how-to-manage-data-transfer-between-ios-apps-in-microsoft-intune"></a>Microsoft Intune 'de iOS uygulamaları arasında veri aktarımını yönetme

Şirket verilerini korumaya yardımcı olmak için dosya aktarımlarını yalnızca yönettiğiniz uygulamalarla kısıtlayın. İOS uygulamalarını aşağıdaki yollarla yönetebilirsiniz:

- Uygulamalar için bir uygulama koruma ilkesi yapılandırarak iş veya okul hesapları için Kuruluş verilerini koruyun. *ilke ile yönetilen uygulamaları*çağırıyoruz.  [Uygulama koruma ilkesiyle yönetebileceğiniz tüm Intune tarafından yönetilen uygulamalara](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) bakın

- Cihazların bir mobil cihaz yönetimi (MDM) çözümüne kaydolmasını gerektiren iOS cihaz yönetimi aracılığıyla uygulamaları dağıtın ve yönetin. Dağıttığınız uygulamalar *ilkeyle yönetilen uygulamalar* veya iOS tarafından yönetilen diğer uygulamalar olabilir.

Kayıtlı iOS cihazları için **Açık yönetim** özelliği, iOS tarafından yönetilen uygulamalar arasında dosya aktarımlarını sınırlayabilir. Yapılandırma ayarları ' nda *Açık yönetim* kısıtlamalarını ayarlayın ve ardından bunları MDM çözümünüzü kullanarak dağıtın.  Kullanıcı dağıtılan uygulamayı yüklediğinde, ayarladığınız kısıtlamalar uygulanır.

## <a name="use-app-protection-with-ios-apps"></a>İOS uygulamalarıyla uygulama korumasını kullanma
Aşağıdaki yollarla şirket verilerini korumak için iOS **Açık yönetim** özelliği ile uygulama koruma ilkelerini kullanın:

- **Herhangi BIR MDM çözümü tarafından yönetilmeyen cihazlar:** Uygulama koruma ilkesi ayarlarını, diğer uygulamalarla birlikte *açma* veya *Paylaşım uzantıları*aracılığıyla veri paylaşımını denetlemek için ayarlayabilirsiniz.  Bunu yapmak için, **açık/paylaşılan filtreleme değeriyle ilke ile yönetilen uygulamalar** için **Kuruluş verilerini diğer uygulamaya gönder** ayarını yapılandırın.  *İlke ile yönetilen uygulamadaki* *Açık/paylaşım* davranışı, paylaşım seçenekleri olarak yalnızca diğer *ilkeyle yönetilen uygulamalar* sunar. 

- **MDM çözümleri tarafından yönetilen cihazlar**: Intune veya üçüncü taraf MDM çözümlerine kayıtlı cihazlar için uygulama koruma ilkelerine sahip uygulamalar ve MDM aracılığıyla dağıtılan diğer yönetilen iOS uygulamaları arasında veri paylaşımı, Intune uygulama Ilkeleri ve iOS açık tarafından denetlenir  **Yönetim** özelliği. Bir MDM çözümünü kullanarak dağıttığınız uygulamaların de Intune uygulama koruma ilkeleriniz ile ilişkilendirildiğini doğrulamak için, Kullanıcı UPN ayarını aşağıdaki bölümde açıklandığı gibi yapılandırın, [Kullanıcı UPN ayarını yapılandırın](data-transfer-between-apps-manage-ios.md#configure-user-upn-setting-for-microsoft-intune-or-third-party-emm). Diğer uygulamalara veri aktarımına nasıl izin vermek istediğinizi belirtmek için, **diğer uygulamalara kuruluş verisi gönder** ' i etkinleştirin ve tercih ettiğiniz paylaşım düzeyini seçin. Uygulamanın diğer uygulamalardan veri almasına nasıl izin vermek istediğinizi belirtmek için, **diğer uygulamalardan veri al** seçeneğini etkinleştirin ve tercih ettiğiniz alan düzeyini seçin. Uygulama verilerini alma ve paylaşma hakkında daha fazla bilgi için bkz. [veri değiştirme ayarları](app-protection-policy-settings-ios.md#data-protection).

## <a name="configure-user-upn-setting-for-microsoft-intune-or-third-party-emm"></a>Microsoft Intune veya üçüncü taraf EMM için Kullanıcı UPN ayarını yapılandırma
Kullanıcı UPN ayarını yapılandırmak, kayıtlı Kullanıcı hesabını tanımlamak için Intune veya üçüncü taraf EMM çözümü tarafından yönetilen cihazlar için **gereklidir** . UPN yapılandırması, Intune 'dan dağıttığınız uygulama koruma ilkeleriyle birlikte kullanılabilir. Aşağıdaki yordam, UPN ayarının ve elde edilen kullanıcı deneyiminin nasıl yapılandırılacağı hakkında genel bir akışdır:

1. [Azure Portal](https://portal.azure.com), iOS için [bir uygulama koruma ilkesi oluşturun ve atayın](app-protection-policies.md) . İlke ayarlarını Şirket gereksinimlerinize göre yapılandırın ve bu ilkeye sahip olması gereken iOS uygulamalarını seçin.

2. Aşağıdaki Genelleştirilmiş adımları kullanarak, Intune veya üçüncü taraf MDM çözümünüz aracılığıyla yönetilmesini istediğiniz uygulamaları ve e-posta profilini dağıtın. Bu deneyim *Örnek 1*' de de ele alınmıştır.

3. Aşağıdaki uygulama yapılandırma ayarlarıyla uygulamayı yönetilen cihaza dağıtın:

      **anahtar** = ıntunemamupn, **değer** =  @ no__t-3

      Örnek: [' ıntunemamupn ', ' janellecraig@contoso.com ']
      
     > [!NOTE]
     > Intune 'da, uygulama yapılandırma ilkesi kayıt türü, **yönetilen cihazlar**olarak ayarlanmalıdır.
     > Ayrıca, uygulamanın Intune Şirket Portalı yüklenilmesi (kullanılabilir olarak ayarlandıysa) veya cihaza gerektiği şekilde itilmesi gerekir. 

4. Intune 'u veya üçüncü taraf MDM sağlayıcınızı kullanarak kayıtlı cihazlara **Açık yönetim** ilkesini dağıtın.


### <a name="example-1-admin-experience-in-intune-or-third-party-mdm-console"></a>Örnek 1: Intune veya üçüncü taraf MDM konsolunda yönetici deneyimi

1. Intune veya üçüncü taraf MDM sağlayıcınızın Yönetici konsoluna gidin. Uygulama yapılandırma ayarlarını kayıtlı iOS cihazlarına dağıttığınız konsolun bölümüne gidin.

2. Uygulama Yapılandırması bölümünde aşağıdaki ayarı girin:

   **anahtar** = ıntunemamupn, **değer** =  @ no__t-3

   Anahtar/değer çiftinin tam sözdizimi, üçüncü taraf MDM sağlayıcınıza göre farklılık gösterebilir. Aşağıdaki tabloda, üçüncü taraf MDM sağlayıcılarının örnekleri ve anahtar/değer çifti için girmeniz gereken tam değerler gösterilmektedir.

   |Üçüncü taraf MDM sağlayıcısı| Yapılandırma anahtarı | Değer türü | Yapılandırma değeri|
   | ------- | ---- | ---- | ---- |
   |Microsoft Intune| Intunemamupn | Dize | {{UserPrincipalName}}|
   |VMware AirWatch| Intunemamupn | Dize | UserPrincipalName|
   |MobileIron | Intunemamupn | Dize | $ {userUPN} **veya** $ {useremadresi} |
   |Citrix uç nokta yönetimi | Intunemamupn | Dize | $ {User. UserPrincipalName} |
   |ManageEngine Mobil Aygıt Yöneticisi | Intunemamupn | Dize | 'le |

> [!NOTE]  
> İOS 'ta Outlook uygulaması için, "yapılandırma tasarımcısını kullanma" seçeneğiyle bir uygulama yapılandırma Ilkesi dağıtırsanız, ilke için arka planda otomatik olarak yapılandırma anahtarı ıntunemamupn yapılandırma anahtarı yapılandırılır. [Yeni Outlook for iOS ve Android uygulama yapılandırma Ilkesi deneyimi](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/New-Outlook-for-iOS-and-Android-App-Configuration-Policy/ba-p/370481)hakkında daha fazla bilgi için bkz. genel uygulama yapılandırması. 


### <a name="example-2-end-user-experience"></a>Örnek 2: Son Kullanıcı deneyimi

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

### <a name="validate-user-upn-setting-for-third-party-emm"></a>Üçüncü taraf EMM için Kullanıcı UPN ayarını doğrulama

Kullanıcı UPN ayarını yapılandırdıktan sonra, iOS uygulamasının Intune uygulama koruma ilkesini alma ve bunlara uyum sağlama yeteneğini doğrulayın.

Örneğin, **uygulama PIN 'ı gerektir** ilke ayarının test edilmesi kolaydır. İlke ayarı izin **iste**' ye eşitse, Kullanıcı şirket verilerine erişebilmek IÇIN bir PIN ayarlaması veya girmesi için bir istem görmeniz gerekir.

İlk olarak, iOS uygulamasına [bir uygulama koruma ilkesi oluşturun ve atayın](app-protection-policies.md) . Uygulama koruma ilkesini test etme hakkında daha fazla bilgi için bkz. [Uygulama koruma Ilkelerini doğrulama](app-protection-policies-validate.md).


## <a name="see-also"></a>Ayrıca bkz.
[Intune uygulama koruma ilkesi nedir?](app-protection-policy.md)
