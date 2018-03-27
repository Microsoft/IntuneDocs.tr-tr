---
title: iOS uygulamaları arasında veri aktarımını yönetme
description: Bu konuyu, uygulamalar arasındaki veri aktarımlarını yönetmek amacıyla iOS Birlikte açma özelliğini ve mobil uygulama yönetimi ilkelerini nasıl kullanabileceğinizi anlamak için okuyun.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 11/14/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3a4515c1-b325-4ac1-9f0a-45ac27e00681
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6b83e5fa37f9a9844e3011cded3c3cd58f268521
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2018
---
# <a name="manage-data-transfer-between-ios-apps-with-microsoft-intune"></a>Microsoft Intune ile iOS uygulamaları arasında veri aktarımını yönetme

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="manage-ios-apps"></a>iOS uygulamalarını yönetme
Şirket verilerinizin korunması, dosya aktarımlarının tarafınızdan yönetilen uygulamalarla kısıtlanmasını da içerir.  iOS uygulamalarını aşağıdaki yollarla yönetebilirsiniz:

-   Uygulamalar için uygulama koruma ilkesi yapılandırarak şirkette veri kaybını önleyin. Biz buna **ilkeyle yönetilen** uygulamalar diyeceğiz.

-   Uygulamaları **MDM kanalı** üzerinden de dağıtıp yönetebilirsiniz.  Bunun için cihazların MDM çözümüne kaydedilmesi gerekir. Bunlar **ilkeyle yönetilen** uygulamaları veya diğer yönetilen uygulamalar olabilir.

iOS cihazları için **Yönetimde açma** özelliği, dosya aktarımlarını yalnızca **MDM kanalı** aracılığıyla dağıtılan uygulamalar arasında gerçekleşecek şekilde sınırlandırabilir. Yönetimde açma kısıtlamaları, yapılandırma ayarlarında belirlenir ve MDM çözümünüz aracılığıyla dağıtılır.  Kullanıcı dağıtılan uygulamayı yüklendiğinde, ayarladığınız kısıtlamalar uygulanır.

##  <a name="manage-data-transfer-between-ios-apps"></a>iOS uygulamaları arasında veri aktarımını yönetme
Uygulama koruma ilkeleri, iOS **Yönetimde açma** özelliğiyle birlikte kullanıldığında, şirket verileri aşağıdaki yollarla korunabilir:

-   **Herhangi bir MDM çözümüyle yönetilmeyen, çalışana ait cihazlar:** [Uygulama koruma ilkesi ayarını](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md), **Uygulamanın yalnızca yönetilen uygulamalara veri aktarmasına izin ver** olarak belirleyebilirsiniz. Son kullanıcı ilkeyle yönetilmeyen bir uygulamada korunan bir dosyayı açtığında dosya okunamaz.

-   **Intune tarafından yönetilen cihazlar:** Intune’a kayıtlı cihazlar için uygulama koruma ilkelerine sahip uygulamalarla Intune aracılığıyla dağıtılan diğer yönetilen iOS uygulamaları arasında veri aktarımına otomatik olarak izin verilir. Uygulamak koruma ilkelerine sahip uygulamalar arasında veri aktarımına izin vermek için, **Uygulamanın yalnızca yönetilen uygulamalara veri aktarmasına izin ver** ayarını etkinleştirin. **Yönetimde açma** özelliğini kullanarak Intune aracılığıyla dağıtılmış uygulamalar arasındaki veri aktarımını denetleyebilirsiniz.   

-   **Üçüncü taraf MDM çözümü tarafından yönetilen cihazlar:** iOS **Yönetimde açma** özelliğini kullanarak veri aktarımını yalnızca yönetilen uygulamalarla kısıtlayabilirsiniz.
Üçüncü taraf MDM çözümünüzü kullanarak dağıttığınız uygulamaların Intune’da yapılandırdığınız uygulama koruma ilkeleriyle de ilişkilendirildiğinden emin olmak için, [Kullanıcı UPN ayarını yapılandırma](#configure-user-upn-setting-for-third-party-emm) yönergesinde açıklandığı gibi kullanıcı UPN ayarını yapılandırmalısınız.  Uygulamalar kullanıcı UPN ayarı ile dağıtılırken, son kullanıcı iş hesabını kullanarak oturum açtığında uygulamaya uygulama koruma ilkeleri uygulanır.

> [!IMPORTANT]
> Kullanıcı UPN ayarı yalnızca bir üçüncü taraf MDM tarafından yönetilen cihazlara dağıtılan uygulamalar için gereklidir.  Intune ile yönetilen cihazlar için bu ayar gerekli değildir.

## <a name="configure-user-upn-setting-for-third-party-emm"></a>Üçüncü taraf EMM için kullanıcı UPN ayarını yapılandırma
Kullanıcı UPN ayarını yapılandırmak, üçüncü taraf EMM çözümü tarafından yönetilen cihazlar için **gereklidir**. Aşağıda açıklanan yordam, UPN ayarının nasıl yapılandırılacağı ve ortaya çıkan son kullanıcı deneyimi hakkında genel bir bakış sunar:


1.  Azure portalında, iOS platformu için [bir uygulama koruma ilkesi yapılandırın](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md). İlke ayarlarını şirket gereksinimlerinize göre yapılandırın ve bu ilkeye sahip olacak uygulamaları seçin.

2.  Aşağıda genelleştirilen adımları kullanarak, **üçüncü taraf MDM çözümünüz aracılığıyla** yönetilmesini istediğiniz uygulamaları ve e-posta profilini dağıtın. Bu deneyim Örnek 1’de de ele alınmıştır.

  1.  Uygulamayı, aşağıdaki uygulama yapılandırma ayarlarıyla dağıtın:

      **anahtar** = IntuneMAMUPN,  **değer** = <username@company.com>

      Örnek: [‘IntuneMAMUPN’, ‘jondoe@microsoft.com’]

  2.  Üçüncü taraf MDM sağlayıcınızı kullanarak kayıtlı cihazlara, Birlikte açma yönetimi ilkesini dağıtın.


### <a name="example-1-admin-experience-in-third-party-mdm-console"></a>Örnek 1: Üçüncü taraf MDM konsolunda yönetici deneyimi

1. Üçüncü taraf MDM sağlayıcınızın yönetici konsoluna gidin. Uygulama yapılandırma ayarlarını kayıtlı iOS cihazlarına dağıttığınız konsol bölümüne gidin.

2. Uygulama Yapılandırması bölümünde aşağıdaki ayarı girin:

  **anahtar** = IntuneMAMUPN,  **değer** = <username@company.com>

  Anahtar/değer çiftinin tam söz dizimi, üçüncü taraf MDM sağlayıcınıza göre farklılık gösterebilir. Aşağıdaki tabloda, üçüncü taraf MDM sağlayıcıları ve anahtar/değer çifti için tam olarak girmeniz gereken değer örnekleri yer almaktadır.

|Üçüncü taraf MDM sağlayıcısı| Yapılandırma Anahtarı | Değer Türü | Yapılandırma Değeri|
| ------- | ---- | ---- | ---- |
| VMware AirWatch | IntuneMAMUPN | Dize | {UserPrincipalName}|
| MobileIron Core | IntuneMAMUPN | Dize | $EMAIL$ **veya** $USER_UPN$ |
| MobileIron Cloud | IntuneMAMUPN | Dize | ${userUPN} **veya** ${userEmailAddress} |
| ManageEngine Mobil Cihaz Yöneticisi | IntuneMAMUPN | Dize | %upn% |

### <a name="example-2-end-user-experience"></a>Örnek 2: Son kullanıcı deneyimi

1.  Son kullanıcı cihaza Microsoft Word uygulamasını yükler.

2.  Son kullanıcı, e-postasına erişmek için yönetilen yerel e-posta uygulamasını başlatır.

3.  Son kullanıcı Microsoft Word’de yerel postadan belgeyi açmaya çalışır.

4.  Word uygulaması başlatıldığında son kullanıcıdan kendi iş hesabını kullanarak oturum açması istenir.  İstendiğinde son kullanıcının girdiği bu iş hesabı, Microsoft Word uygulaması için uygulama yapılandırma ayarlarında belirttiğiniz hesapla eşleşmelidir.

    > [!NOTE]
    > Son kullanıcı kişisel çalışmaları için Word’e başka kişisel hesaplar ekleyebilir ve Word uygulamasını kişisel bağlamda kullanırken uygulama koruma ilkelerinden etkilenmez.

5.  Oturum açma başarılı olduğunda uygulama koruma ilkesi ayarları Word uygulamasına uygulanır.

6.  Dosya aktarımı başarılı olmuştur ve belge, uygulamada şirket kimliği ile etiketlenmiştir. Ayrıca dosya, iş bağlamında ele alınır ve ilke ayarları buna göre uygulanır.

### <a name="validate-user-upn-setting-for-third-party-emm"></a>Üçüncü taraf EMM için kullanıcı UPN ayarını doğrulama

Kullanıcı UPN ayarını yapılandırdıktan sonra, iOS uygulamasının Intune uygulama koruma ilkesi alabildiğini ve buna uyabildiğini doğrulamalısınız.

Örneğin, **Uygulama PIN’i iste** ilke ayarını bir cihazda görsel olarak test etmek kolaydır. İlke ayarı **Evet**’e ayarlıysa son kullanıcı, şirket verilerine erişmeye çalıştığında bir PIN ayarlaması veya girmesi gerektiğini belirten bir istem görür.

İlk olarak iOS uygulamasında [uygulama koruma ilkesi oluşturup dağıtın](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md). Uygulama koruma ilkesini test etme hakkında daha fazla bilgi için bkz. [Uygulama koruma ilkelerini doğrulama](validate-mobile-application-management.md).



### <a name="see-also"></a>Ayrıca bkz:
[Microsoft Intune ile uygulama koruma ilkelerini kullanarak uygulama verilerini koruma](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)
