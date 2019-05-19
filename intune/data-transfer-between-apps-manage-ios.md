---
title: iOS uygulamaları arasında veri aktarımını yönetme
titleSuffix: Microsoft Intune
description: Uygulamalar arasında veri aktarımlarını yönetmek için Microsoft Intune'da mobil uygulama yönetimi ilkelerinin nasıl kullanılacağını öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/08/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d10b2d64-8c72-4e9b-bd06-ab9d9486ba5e
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: dffdf67597ccb7a1719b2b769a79a6a5f365198c
ms.sourcegitcommit: 5fec35341d83b16023a92fc4b2b3e9237fc6c9ab
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2019
ms.locfileid: "65853900"
---
# <a name="how-to-manage-data-transfer-between-ios-apps-in-microsoft-intune"></a>Microsoft Intune’da iOS uygulamaları arasında veri aktarımını yönetme

Şirket verilerini korumaya yardımcı olmak için dosya aktarımlarını yönettiğiniz uygulamaların kısıtlayın. iOS uygulamalarını aşağıdaki yollarla yönetebilirsiniz:

-   Diyoruz uygulamalar için uygulama koruma İlkesi yapılandırarak şirkette veri kaybını önleyin **ilkeyle yönetilen** uygulamalar. [Uygulama koruma ilkesi ile yönetebileceğiniz tüm Intune ile yönetilen uygulamalara](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) bakın.

-   İle uygulamaları dağıtma ve yönetme **MDM kanalı**, bir mobil cihaz Yönetimi (MDM) çözümde kaydetmek için cihazlarınıza gerektirir. Dağıttığınız uygulamaları olabilir **ilkeyle yönetilen** uygulamaları veya diğer yönetilen uygulamalar.

iOS cihazları için **Yönetimde açma** özelliği, dosya aktarımlarını yalnızca **MDM kanalı** aracılığıyla dağıtılan uygulamalar arasında gerçekleşecek şekilde sınırlandırabilir. Ayarlama *yönetimde açma* yapılandırma ayarlarında kısıtlamaları ve bunları MDM çözümünüz aracılığıyla dağıtabilirsiniz.  Bir kullanıcı dağıtılan uygulamayı yüklendiğinde, ayarladığınız kısıtlamalar uygulanır.

##  <a name="use-app-protection-with-ios-apps"></a>Uygulama koruma iOS uygulamalarıyla kullanma
İOS uygulama koruma ilkeleri kullanma **yönetimde açma** özelliği, şirket verileri aşağıdaki yollarla korunabilir:

-   **Çalışana ait herhangi bir MDM çözümü tarafından yönetilmeyen cihazlar:** Uygulama koruma İlkesi ayarlarını ayarlayabilirsiniz **uygulamanın yalnızca ilkeyle yönetilen uygulamalara veri aktarmasına izin ver**. *Açma* davranışı ilke ile yönetilen bir uygulamada yalnızca diğer ilkeyle yönetilen uygulamalara paylaşmak için seçenekleri sunar. Bir kullanıcı, ilkeyle korunan bir dosyayı yerel posta uygulaması onedrive'dan bir ek olarak göndermeye çalışırsa, dosya okunamaz durumda.

-   **Intune tarafından yönetilen cihazlar:** Intune'a kayıtlı cihazlar için uygulama koruma ilkelerine sahip uygulamalar arasında veri aktarımı ve Intune aracılığıyla dağıtılan diğer yönetilen iOS uygulamaları otomatik olarak verilir. Diğer uygulamalara veri aktarımına izin nasıl istediğinizi belirtmek için etkinleştirin **uygulamanın diğer uygulamalara veri aktarmasına izin ver** paylaşımı, tercih edilen düzeyini seçin. Bir uygulamanın diğer uygulamalardan veri almasına izin vermek nasıl istediğinizi belirtmek için etkinleştirin **uygulamanın diğer uygulamalardan veri almasına izin ver** veri almak, tercih edilen düzeyini seçin. **Yönetimde açma** özelliğini kullanarak Intune aracılığıyla dağıtılmış uygulamalar arasındaki veri aktarımını denetleyebilirsiniz. Uygulama verilerinin alınması ve paylaşılması hakkında daha fazla bilgi için bkz. [Verileri yeniden konumlandırma ayarları](app-protection-policy-settings-ios.md#data-protection).   

-   **Bir üçüncü taraf MDM çözümü tarafından yönetilen cihazlar:** İOS kullanarak veri aktarımını yalnızca yönetilen uygulamalarla kısıtlayabilirsiniz **yönetimde açma** özelliği.
Bir üçüncü taraf MDM çözümünüzü kullanarak dağıttığınız uygulamalar da Intune uygulama koruma ilkeleri ile ilişkili olduğundan emin olmak için Kullanıcı UPN ayarını aşağıdaki bölümde anlatılan şekilde yapılandırın [Kullanıcı UPN ayarını yapılandırma](#configure-user-upn-setting-for-microsoft-intune-or-third-party-emm). Uygulamalar Kullanıcı UPN ayarı ile dağıttığınızda, kullanıcı iş hesabını kullanarak oturum açtığında, uygulama koruma ilkeleri uygulamaya uygulanır.

## <a name="configure-user-upn-setting-for-microsoft-intune-or-third-party-emm"></a>Microsoft Intune veya üçüncü taraf EMM için kullanıcı UPN ayarını yapılandırma
Kullanıcı UPN ayarını yapılandırmak, Intune veya üçüncü taraf EMM çözümü tarafından yönetilen cihazlar için **gereklidir**. UPN yapılandırma, Intune'dan dağıttığınız uygulama koruma ilkeleri ile birlikte çalışır. Aşağıdaki yordam, UPN ayarını ve sonuçta elde edilen kullanıcı deneyimini nasıl yapılandırılacağı hakkında genel bir akış kullanılır:

1.  [Azure portalında](https://portal.azure.com), iOS için [bir uygulama koruma ilkesi oluşturup bunu atayın](app-protection-policies.md). İlke ayarlarını şirket gereksinimlerinize göre yapılandırın ve bu ilkeye sahip olacak iOS uygulamalarını seçin.

2.  Uygulamaları ve yönetilen Intune veya aşağıdaki Genelleştirilen adımları kullanarak, üçüncü taraf MDM çözümünüz istediğiniz e-posta profilini dağıtın. Bu deneyimi de kapsamına giren *örnek 1*.

3.  Yönetilen cihaz için uygulamayı şu uygulama yapılandırma ayarlarıyla dağıtın:

      **anahtar** = ıntunemamupn, **değeri** = <username@company.com>

      Örnek: [‘IntuneMAMUPN’, ‘jondoe@microsoft.com’]
      
       > [!NOTE]
       > Intune, uygulama yapılandırma ilkesi için kayıt türü "Yönetilen cihazlar" olması gerekir.
       > Addicionally, uygulama ya da Intune şirket Portalı'ndan yüklediyseniz kullanılabilir veya ittiğinizden cihaza gerektiği gibi olarak ayarlanmış olması gerekir. 

4.  Intune veya üçüncü taraf MDM sağlayıcınızı kullanarak kayıtlı cihazlara, **Birlikte açma yönetimi** ilkesini dağıtın.


### <a name="example-1-admin-experience-in-intune-or-third-party-mdm-console"></a>Örnek 1: Intune veya üçüncü taraf MDM konsolunda yönetici deneyimi

1. Intune veya üçüncü taraf MDM sağlayıcınızın yönetici konsoluna gidin. Uygulama yapılandırma ayarlarını kayıtlı iOS cihazlarına dağıttığınız konsol bölümüne gidin.

2. Uygulama Yapılandırması bölümünde aşağıdaki ayarı girin:

   **anahtar** = ıntunemamupn, **değeri** = <username@company.com>

   Anahtar/değer çiftinin tam söz dizimi, üçüncü taraf MDM sağlayıcınıza göre farklılık gösterebilir. Aşağıdaki tabloda, üçüncü taraf MDM sağlayıcıları örnekleri ve anahtar/değer çifti için girmeniz tam değerlerini gösterir.

   |Üçüncü taraf MDM sağlayıcısı| Yapılandırma Anahtarı | Değer Türü | Yapılandırma Değeri|
   | ------- | ---- | ---- | ---- |
   |Microsoft Intune| IntuneMAMUPN | Dize | {{UserPrincipalName}}|
   |VMware AirWatch| IntuneMAMUPN | Dize | {UserPrincipalName}|
   |MobileIron | IntuneMAMUPN | Dize | ${userUPN} **veya** ${userEmailAddress} |
   |Citrix uç nokta Yönetim | IntuneMAMUPN | Dize | ${user.userprincipalname} |
   |ManageEngine Mobil Cihaz Yöneticisi | IntuneMAMUPN | Dize | %upn% |


### <a name="example-2-end-user-experience"></a>Örnek 2: Son kullanıcı deneyimi

1.  Bir kullanıcı bir cihaza Microsoft Word uygulamasını yükler.

2.  Kullanıcı e-postasına erişmek için yönetilen yerel e-posta uygulamasını başlatır.

3.  Kullanıcı Microsoft Word'de yerel postadan belgeyi açmaya çalışır.

4.  Word uygulaması başlatıldığında, kullanıcı iş hesaplarıyla oturum istenir. Kullanıcı hesabı, Microsoft Word uygulaması için uygulama yapılandırma ayarlarında belirttiğiniz hesapla eşleşmelidir.

    > [!NOTE]
    > Kullanıcı ekleyebilir ve Word ile kişisel hesaplarında kullanabilirsiniz. Uygulama koruma ilkeleri, kullanıcı iş bağlamı dışında sözcük kullandığında geçerli değildir. 

5.  Oturum açma işleminden sonra uygulama koruma İlkesi ayarları Word uygulamasına uygulanır.

6.  Veri aktarımı başarılı olur ve belge, uygulamada şirket kimliği ile etiketlenir.  Veriler iş bağlamında ele alınır ve ilke ayarlarını uygulayın. 

### <a name="validate-user-upn-setting-for-third-party-emm"></a>Üçüncü taraf EMM için kullanıcı UPN ayarını doğrulama

Kullanıcı UPN ayarını yapılandırdıktan sonra iOS uygulamanın özelliği almak için Intune uygulama koruma ilkesi için uyumlu doğrulayın.

Örneğin, **uygulama PIN'i gerekliliği** ilkeyi test etmek kolaydır. İlke ayarı, eşittir **Evet**, kullanıcı ayarlayın veya şirket verilerine erişebilmeniz için önce bir PIN girmesini isteyen bir ileti görmeniz gerekir.

İlk olarak iOS uygulamasına yönelik [bir uygulama koruma ilkesi oluşturup bunu atayın](app-protection-policies.md). Uygulama koruma ilkesini test etme hakkında daha fazla bilgi için bkz. [uygulama koruma ilkelerini doğrulama](app-protection-policies-validate.md).


### <a name="see-also"></a>Ayrıca bkz.
[Intune uygulama koruma ilkesi nedir](app-protection-policy.md)
