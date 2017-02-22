---
title: "iOS uygulamaları arasında veri aktarımını yönetme |Intune Azure önizlemesi | Microsoft Docs"
description: "Intune Azure önizlemesi: Uygulamalar arasındaki veri aktarımlarını yönetmek amacıyla iOS Birlikte açma özelliğini ve mobil uygulama yönetimi ilkelerini nasıl kullanabileceğinizi anlamak için bu konuyu okuyun."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d10b2d64-8c72-4e9b-bd06-ab9d9486ba5e
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 424fae862592c1ab5b4221fb5ad40a52c39f6760
ms.openlocfilehash: 8846417efd34db32d5a5c872ef438f5a0bc57e36


---

# <a name="how-to-manage-data-transfer-between-ios-apps"></a>iOS uygulamaları arasında veri aktarımını yönetme 
## <a name="manage-ios-apps"></a>iOS uygulamalarını yönetme
Şirket verilerinizin korunması, dosya aktarımlarının tarafınızdan yönetilen uygulamalarla kısıtlanmasını da içerir.  iOS uygulamalarını aşağıdaki yollarla yönetebilirsiniz:

-   Uygulamalar için uygulama koruma ilkesi yapılandırarak şirkette veri kaybını önleyin. Biz buna **ilkeyle yönetilen** uygulamalar diyeceğiz.

-   Uygulamaları **MDM kanalı** üzerinden de dağıtıp yönetebilirsiniz.  Bunun için cihazların MDM çözümüne kaydedilmesi gerekir. Bunlar **ilkeyle yönetilen** uygulamaları veya diğer yönetilen uygulamalar olabilir.

iOS cihazları için **Yönetimde açma** özelliği, dosya aktarımlarını yalnızca **MDM kanalı** aracılığıyla dağıtılan uygulamalar arasında gerçekleşecek şekilde sınırlandırabilir. Yönetimde açma kısıtlamaları, yapılandırma ayarlarında belirlenir ve MDM çözümünüz aracılığıyla dağıtılır.  Kullanıcı dağıtılan uygulamayı yüklendiğinde, ayarladığınız kısıtlamalar uygulanır.
##  <a name="using-app-protection-with-ios-apps"></a>Uygulama korumayı iOS uygulamalarıyla kullanma
Uygulama koruma ilkeleri iOS **Yönetimde açma** özelliğiyle birlikte kullanıldığında, şirket verileri aşağıdaki yollarla korunabilir:

-   **Herhangi bir MDM çözümüyle yönetilmeyen, çalışana ait cihazlar:** Uygulama koruma ilkesi ayarlarını **Uygulamanın yalnızca yönetilen uygulamalara veri aktarmasına izin ver** olarak belirleyebilirsiniz. Son kullanıcı ilkeyle yönetilmeyen bir uygulamada korunan bir dosyayı açtığında dosya okunamaz.

-   **Intune tarafından yönetilen cihazlar:** Intune’a kayıtlı cihazlar için, uygulama koruma ilkelerine sahip uygulamalarla Intune aracılığıyla dağıtılan diğer yönetilen iOS uygulamaları arasında veri aktarımına otomatik olarak izin verilir. Uygulamak koruma ilkelerine sahip uygulamalar arasında veri aktarımına izin vermek için, **Uygulamanın yalnızca yönetilen uygulamalara veri aktarmasına izin ver** ayarını etkinleştirin. **Yönetimde açma** özelliğini kullanarak Intune aracılığıyla dağıtılmış uygulamalar arasındaki veri aktarımını denetleyebilirsiniz.   

-   **Üçüncü taraf MDM çözümü tarafından yönetilen cihazlar:** iOS **Yönetimde açma** özelliğini kullanarak veri aktarımını yalnızca yönetilen uygulamalarla kısıtlayabilirsiniz.
Üçüncü taraf MDM çözümünüzü kullanarak dağıttığınız uygulamaların Intune’da yapılandırdığınız uygulama koruma ilkeleriyle de ilişkilendirildiğinden emin olmak için, [Kullanıcı UPN ayarını yapılandırma](#configure-user-upn-setting) yönergesinde açıklandığı gibi kullanıcı UPN ayarını yapılandırmalısınız.  Uygulamalar kullanıcı UPN ayarı ile dağıtılırken, son kullanıcı iş hesabını kullanarak oturum açtığında uygulamaya uygulama koruma ilkeleri uygulanır.

> [!IMPORTANT]
> Kullanıcı UPN ayarı yalnızca bir üçüncü taraf MDM tarafından yönetilen cihazlara dağıtılan uygulamalar için gereklidir.  Intune ile yönetilen cihazlar için bu ayar gerekli değildir.

## <a name="configure-user-upn-setting"></a>Kullanıcı UPN ayarını yapılandırma
Bu yapılandırma bir üçüncü taraf MDM çözümü tarafından yönetilen cihazlar için gereklidir. Aşağıda açıklanan yordam, UPN ayarının nasıl uygulanacağı ve ortaya çıkan son kullanıcı deneyimi hakkında genel bir akış sunar:


1.  Azure portalında, iOS platformu için [bir mobil uygulama yönetimi ilkesi yapılandırın](app-protection-policies.md). İlke ayarlarını şirket gereksinimlerinize göre yapılandırın ve bu ilkeye sahip olacak uygulamaları seçin.

2.  3. ve 4. adımlarda açıklanan ayarı kullanarak, **üçüncü taraf MDM çözümünüz aracılığıyla** yönetilmesini istediğiniz uygulamaları ve e-posta profilini dağıtın.

3.  Uygulamayı şu uygulama yapılandırma ayarları ile dağıtın: key=IntuneMAMUPN, Value=<username@company.com> [örnek: ‘IntuneMAMUPN’, ‘jondoe@microsoft.com’]

4.  Birlikte açma yönetimi ilkesini kayıtlı cihazlara dağıtın.

### <a name="example-end-user-experience"></a>Son kullanıcı deneyimi örneği

1.  Son kullanıcı cihaza Microsoft Word uygulamasını yükler.

2.  Son kullanıcı, e-postasına erişmek için yönetilen yerel e-posta uygulamasını başlatır.

3.  Son kullanıcı Microsoft Word’de yerel postadan belgeyi açmaya çalışır.

4.  Word uygulaması başlatıldığında son kullanıcıdan kendi iş hesabını kullanarak oturum açması istenir.  İstendiğinde son kullanıcının girdiği bu iş hesabı, Microsoft Word uygulaması için uygulama yapılandırma ayarlarında belirttiğiniz hesapla eşleşmelidir.

    > [!NOTE]
    > Son kullanıcı kişisel çalışmaları için Word’e başka kişisel hesaplar ekleyebilir ve Word uygulamasını kişisel bağlamda kullanırken uygulama koruma ilkelerinden etkilenmez.

5.  Oturum açma başarılı olduğunda uygulama ilkesi ayarları Word uygulamasına uygulanır.

6.  Veri aktarımı başarılı olmuştur ve belge, uygulamada şirket kimliği olarak etiketlenmiştir. Ayrıca, veriler iş bağlamında ele alınır ve ilke ayarları buna göre uygulanır.

### <a name="see-also"></a>Ayrıca bkz.
[Intune uygulama koruma ilkesi nedir](what-is-app-protection-policy.md)



<!--HONumber=Feb17_HO1-->


