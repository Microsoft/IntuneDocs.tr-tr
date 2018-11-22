---
title: iOS uygulamaları arasında veri aktarımını yönetme
titlesuffix: Microsoft Intune
description: Uygulamalar arasında veri aktarımlarını yönetmek için Microsoft Intune'da mobil uygulama yönetimi ilkelerinin nasıl kullanılacağını öğrenin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d10b2d64-8c72-4e9b-bd06-ab9d9486ba5e
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: d5a2bc0939da5ee4cb35585a930f145b832a58ad
ms.sourcegitcommit: 0dbce0415e53fe963dc7f927ac4b0c06411f199c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2018
ms.locfileid: "52281114"
---
# <a name="how-to-manage-data-transfer-between-ios-apps-in-microsoft-intune"></a>Microsoft Intune’da iOS uygulamaları arasında veri aktarımını yönetme

Şirket verilerini korumaya yardımcı olmak için dosya aktarımlarını yönettiğiniz uygulamaların kısıtlayın. iOS uygulamalarını aşağıdaki yollarla yönetebilirsiniz:

-   Diyoruz uygulamalar için uygulama koruma İlkesi yapılandırarak şirkette veri kaybını önleyin **ilkeyle yönetilen** uygulamalar. [Uygulama koruma ilkesi ile yönetebileceğiniz tüm Intune ile yönetilen uygulamalara](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) bakın.

-   İle uygulamaları dağıtma ve yönetme **MDM kanalı**, bir mobil cihaz Yönetimi (MDM) çözümde kaydetmek için cihazlarınıza gerektirir. Dağıttığınız uygulamaları olabilir **ilkeyle yönetilen** uygulamaları veya diğer yönetilen uygulamalar.

iOS cihazları için **Yönetimde açma** özelliği, dosya aktarımlarını yalnızca **MDM kanalı** aracılığıyla dağıtılan uygulamalar arasında gerçekleşecek şekilde sınırlandırabilir. Ayarlama *yönetimde açma* yapılandırma ayarlarında kısıtlamaları ve bunları MDM çözümünüz aracılığıyla dağıtabilirsiniz.  Bir kullanıcı dağıtılan uygulamayı yüklendiğinde, ayarladığınız kısıtlamalar uygulanır.

##  <a name="use-app-protection-with-ios-apps"></a>Uygulama koruma iOS uygulamalarıyla kullanma
İOS uygulama koruma ilkeleri kullanma **yönetimde açma** özelliği, şirket verileri aşağıdaki yollarla korunabilir:

-   **Herhangi bir MDM çözümüyle yönetilmeyen, çalışana ait cihazlar:** Uygulama koruma ilkesi ayarlarını **Uygulamanın yalnızca İlkeyle Yönetilen uygulamalara veri aktarmasına izin ver** olarak belirleyebilirsiniz. *Açma* davranışı ilke ile yönetilen bir uygulamada yalnızca diğer ilkeyle yönetilen uygulamalara paylaşmak için seçenekleri sunar. Bir kullanıcı, ilkeyle korunan bir dosyayı yerel posta uygulaması onedrive'dan bir ek olarak göndermeye çalışırsa, dosya okunamaz durumda.

-   **Intune tarafından yönetilen cihazlar:** Intune’a kayıtlı cihazlar için uygulama koruma ilkelerine sahip uygulamalarla Intune aracılığıyla dağıtılan diğer yönetilen iOS uygulamaları arasında veri aktarımına otomatik olarak izin verilir. Diğer uygulamalara veri aktarımına izin nasıl istediğinizi belirtmek için etkinleştirin **uygulamanın diğer uygulamalara veri aktarmasına izin ver** paylaşımı, tercih edilen düzeyini seçin. Bir uygulamanın diğer uygulamalardan veri almasına izin vermek nasıl istediğinizi belirtmek için etkinleştirin **uygulamanın diğer uygulamalardan veri almasına izin ver** veri almak, tercih edilen düzeyini seçin. **Yönetimde açma** özelliğini kullanarak Intune aracılığıyla dağıtılmış uygulamalar arasındaki veri aktarımını denetleyebilirsiniz. Uygulama verilerinin alınması ve paylaşılması hakkında daha fazla bilgi için bkz. [Verileri yeniden konumlandırma ayarları](app-protection-policy-settings-ios.md#data-relocation-settings).   

-   **Bir üçüncü taraf MDM çözümü tarafından yönetilen cihazlar:** iOS kullanarak veri aktarımını yalnızca yönetilen uygulamalarla kısıtlayabilirsiniz **yönetimde açma** özelliği.
Bir üçüncü taraf MDM çözümünüzü kullanarak dağıttığınız uygulamalar da Intune uygulama koruma ilkeleri ile ilişkili olduğundan emin olmak için Kullanıcı UPN ayarını aşağıdaki bölümde anlatılan şekilde yapılandırın [Kullanıcı UPN ayarını yapılandırma](#configure-user-upn-setting-for-microsoft-intune-or-third-party-emm). Uygulamalar Kullanıcı UPN ayarı ile dağıttığınızda, kullanıcı iş hesabını kullanarak oturum açtığında, uygulama koruma ilkeleri uygulamaya uygulanır.

## <a name="configure-user-upn-setting-for-microsoft-intune-or-third-party-emm"></a>Microsoft Intune veya üçüncü taraf EMM için kullanıcı UPN ayarını yapılandırma
Kullanıcı UPN ayarını yapılandırmak, Intune veya üçüncü taraf EMM çözümü tarafından yönetilen cihazlar için **gereklidir**. UPN yapılandırma, Intune'dan dağıttığınız uygulama koruma ilkeleri ile birlikte çalışır. Aşağıdaki yordam, UPN ayarını ve sonuçta elde edilen kullanıcı deneyimini nasıl yapılandırılacağı hakkında genel bir akış kullanılır:

1.  [Azure portalında](https://portal.azure.com), iOS için [bir uygulama koruma ilkesi oluşturup bunu atayın](app-protection-policies.md). İlke ayarlarını şirket gereksinimlerinize göre yapılandırın ve bu ilkeye sahip olacak iOS uygulamalarını seçin.

2.  Uygulamaları ve yönetilen Intune veya aşağıdaki Genelleştirilen adımları kullanarak, üçüncü taraf MDM çözümünüz istediğiniz e-posta profilini dağıtın. Bu deneyimi de kapsamına giren *örnek 1*.

3.  Uygulamayı, aşağıdaki uygulama yapılandırma ayarlarıyla dağıtın:

      **anahtar** = IntuneMAMUPN,  **değer** = <username@company.com>

      Örnek: [‘IntuneMAMUPN’, ‘jondoe@microsoft.com’]

4.  Intune veya üçüncü taraf MDM sağlayıcınızı kullanarak kayıtlı cihazlara, **Birlikte açma yönetimi** ilkesini dağıtın.


### <a name="example-1-admin-experience-in-intune-or-third-party-mdm-console"></a>Örnek 1: Intune veya üçüncü taraf MDM konsolunda yönetici deneyimi

1. Intune veya üçüncü taraf MDM sağlayıcınızın yönetici konsoluna gidin. Uygulama yapılandırma ayarlarını kayıtlı iOS cihazlarına dağıttığınız konsol bölümüne gidin.

2. Uygulama Yapılandırması bölümünde aşağıdaki ayarı girin:

   **anahtar** = IntuneMAMUPN,  **değer** = <username@company.com>

   Anahtar/değer çiftinin tam söz dizimi, üçüncü taraf MDM sağlayıcınıza göre farklılık gösterebilir. Aşağıdaki tabloda, üçüncü taraf MDM sağlayıcıları örnekleri ve anahtar/değer çifti için girmeniz tam değerlerini gösterir.

   |Üçüncü taraf MDM sağlayıcısı| Yapılandırma Anahtarı | Değer Türü | Yapılandırma Değeri|
   | ------- | ---- | ---- | ---- |
   |Microsoft Intune| IntuneMAMUPN | Dize | {{UserPrincipalName}}|
   |VMware AirWatch| IntuneMAMUPN | Dize | {UserPrincipalName}|
   |MobileIron | IntuneMAMUPN | Dize | ${userUPN} **veya** ${userEmailAddress} |
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
