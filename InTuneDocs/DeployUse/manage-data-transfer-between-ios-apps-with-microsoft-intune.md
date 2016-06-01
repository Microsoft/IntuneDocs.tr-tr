---
# required metadata

title: iOS uygulamaları arasında veri aktarımını yönetme | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 3a4515c1-b325-4ac1-9f0a-45ac27e00681

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune ile iOS uygulamaları arasında veri aktarımını yönetme
## iOS uygulamalarını yönetme
Şirket verilerinizin korunması, dosya aktarımlarının tarafınızdan yönetilen uygulamalarla kısıtlanmasını da içerir.  iOS uygulamalarını aşağıdaki yollarla yönetebilirsiniz:

-   Uygulamalar için bir MAM ilkesi yapılandırarak şirkette veri kaybını önleyin. Biz buna **ilkeyle yönetilen** uygulamalar diyeceğiz.

-   Uygulamaları **MDM kanalı** üzerinden de dağıtıp yönetebilirsiniz.  Bunun için cihazların MDM çözümüne kaydedilmesi gerekir. Bunlar **ilkeyle yönetilen** uygulamaları veya diğer yönetilen uygulamalar olabilir.

iOS cihazları için **Yönetimde açma** özelliği, dosya aktarımlarını yalnızca **MDM kanalı** aracılığıyla dağıtılan uygulamalar arasında gerçekleşecek şekilde sınırlandırabilir. Yönetimde açma kısıtlamaları, yapılandırma ayarlarında belirlenir ve MDM çözümünüz aracılığıyla dağıtılır.  Kullanıcı dağıtılan uygulamayı yüklendiğinde, ayarladığınız kısıtlamalar uygulanır.
##  iOS uygulamalarıyla MAM’yi kullanma
Mobil uygulama yönetimi (MAM) ilkeleri iOS **Yönetimde açma** özelliğiyle birlikte kullanıldığında, şirket verileri aşağıdaki yollarla korunabilir:

-   **Herhangi bir MDM çözümü tarafından yönetilmeyen, çalışanın sahip olduğu cihazlar:** MAM ilke ayarlarını **Uygulamanın yalnızca yönetilen uygulamalara veri aktarmasına izin ver** olarak belirleyebilirsiniz. Son kullanıcı ilkeyle yönetilmeyen bir uygulamada korunan bir dosyayı açtığında dosya okunamaz.

-   **Intune tarafından yönetilen cihazlar:** Intune’a kayıtlı cihazlar için, MAM ilkelerine sahip uygulamalarla Intune aracılığıyla dağıtılan diğer yönetilen iOS uygulamaları arasında veri aktarımına otomatik olarak izin verilir. MAM ilkelerine sahip uygulamalar arasında veri aktarımına izin vermek için, **Uygulamanın yalnızca yönetilen uygulamalara veri aktarmasına izin ver** ayarını etkinleştirin. **Yönetimde açma** özelliğini kullanarak Intune aracılığıyla dağıtılmış uygulamalar arasındaki veri aktarımını denetleyebilirsiniz.   

-   **Üçüncü taraf MDM çözümü tarafından yönetilen cihazlar:** iOS **Yönetimde açma** özelliğini kullanarak veri aktarımını yalnızca yönetilen uygulamalarla kısıtlayabilirsiniz.
Üçüncü taraf MDM çözümünüzü kullanarak dağıttığınız uygulamaların Intune’da yapılandırdığınız MAM ilkeleriyle de ilişkilendirildiğinden emin olmak için, [Kullanıcı UPN ayarını yapılandırma](#configure-user-upn-setting) yönergesinde açıklandığı gibi kullanıcı UPN ayarını yapılandırmalısınız.  Uygulamalar kullanıcı UPN ayarı ile dağıtılırken, son kullanıcı iş hesabını kullanarak oturum açtığında uygulamaya MAM ilkeleri uygulanır.

> [!IMPORTANT]
> Kullanıcı UPN ayarı yalnızca bir üçüncü taraf MDM tarafından yönetilen cihazlara dağıtılan uygulamalar için gereklidir.  Intune ile yönetilen cihazlar için bu ayar gerekli değildir.

## Kullanıcı UPN ayarını yapılandırma
Bu yapılandırma bir üçüncü taraf MDM çözümü tarafından yönetilen cihazlar için gereklidir. Aşağıda açıklanan yordam, UPN ayarının nasıl uygulanacağı ve ortaya çıkan son kullanıcı deneyimi hakkında genel bir akış sunar:


1.  iOS platformu için bir mobil uygulama yönetimi ilkesi yapılandırın. İlke ayarlarını şirket gereksinimlerinize göre yapılandırın ve bu ilkeye sahip olacak uygulamaları seçin.

2.  3. ve 4. adımlarda açıklanan ayarı kullanarak, üçüncü taraf MDM çözümünüz aracılığıyla yönetilmesini istediğiniz uygulamaları ve e-posta profilini dağıtın.

3.  Uygulamayı şu yapılandırma ayarlarıyla dağıtın: key=IntuneMAMUPN, Value=<kullanıcıadı@şirket.com> [örnek: ‘IntuneMAMUPN’, ‘alikara@microsoft.com’]

4.  Birlikte açma yönetimi ilkesini kayıtlı cihazlara dağıtın.

### Son kullanıcı deneyimi örneği

1.  Son kullanıcı cihaza Microsoft Word uygulamasını yükler.

2.  Son kullanıcı, e-postasına erişmek için yönetilen yerel e-posta uygulamasını başlatır.

3.  Son kullanıcı Microsoft Word’de yerel postadan belgeyi açmaya çalışır.

4.  Word uygulaması başlatıldığında son kullanıcıdan kendi iş hesabını kullanarak oturum açması istenir.  İstendiğinde son kullanıcının girdiği bu iş hesabı, Microsoft Word uygulaması için uygulama yapılandırma ayarlarında belirttiğiniz hesapla eşleşmelidir.

    > Son kullanıcı kişisel çalışmaları için Word’e başka kişisel hesaplar ekleyebilir ve Word uygulamasını kişisel bağlamda kullanırken MAM ilkelerinden etkilenmez.

5.  Oturum açma başarılı olduğunda uygulama ilkesi ayarları Word uygulamasına uygulanır.

6.  Veri aktarımı başarılı olmuştur ve belge, uygulamada şirket kimliği olarak etiketlenmiştir. Ayrıca, veriler iş bağlamında ele alınır ve ilke ayarları buna göre uygulanır.

### Ayrıca bkz.
[Microsoft Intune ile mobil uygulama yönetimi ilkelerini kullanarak uygulama verilerini koruma](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)


<!--HONumber=May16_HO2-->


