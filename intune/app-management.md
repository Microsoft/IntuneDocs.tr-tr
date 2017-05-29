---
title: "Uygulama yönetimi nedir? | Microsoft Docs"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Microsoft Intune’la uygulama yönetimi hakkındaki temel bilgileri edinmek için bu konuyu kullanın"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/04/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1975a2dc-3a14-4cb9-9afb-e2ba01a1c51b
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 56eefde5969f5426886c07bd6e9a548c8526e82e
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---

# <a name="what-is-microsoft-intune-app-management"></a>Microsoft Intune uygulama yönetimi nedir?


[!INCLUDE[azure_preview](./includes/azure_preview.md)]


BT yöneticisi olarak, son kullanıcılarınızın işlerini yapmak için ihtiyaçları olan uygulamalara erişmelerini sağlamak büyük olasılıkla sizin görevinizdir. Bu zor olabilir çünkü:
- Çok çeşitli cihaz platformları ve uygulama türleri vardır.
- Şirket cihazlarındaki uygulamalara ek olarak kullanıcıların kendi cihazlarındaki uygulamaları da yönetmeniz gerekebilir.
- Tüm bunları yaparken, ağınızın ve verilerinizin de güvenliğini korumanız gerekir. 

Buna ek olarak, Intune’a kaydolmamış cihazlarda uygulamaları atamak ve yönetmek isteyebilirsiniz.

Intune, ihtiyacınız olan uygulamaları istediğiniz cihazlara almanıza yardımcı olacak çeşitli özellikler sunar.

## <a name="app-management-capabilities-by-platform"></a>Platforma göre uygulama yönetimi özellikleri

||||||
|-|-|-|-|-|
|&nbsp; |Android|iOS|Windows Phone 8.1|Windows 10|
|Cihazlara ve kullanıcılara uygulamaları ekleme ve atama|Evet|Evet|Evet|Evet|
|Intune’a kayıtlı olmayan cihazlara uygulamaları atama|Evet|Evet|Hayır|Hayır|
|Uygulamaların başlangıç davranışını denetlemek için uygulama yapılandırma ilkelerini kullanma|Hayır|Evet|Hayır|Hayır|
|Süresi dolan uygulamaları yenilemek için mobil uygulama sağlama ilkeleri kullanma|Hayır|Evet|Hayır|Hayır|
|Uygulama koruma ilkeleriyle uygulamalardaki şirket verilerini koruma|Evet|Evet|Hayır|Hayır<sup>1</sup>|
|Yüklü uygulamadan yalnızca şirket verilerini kaldırma (Uygulama seçmeli silme)|Evet|Evet|Evet|Evet|
|Uygulama atamalarını izleme|Evet|Evet|Evet|Evet|
|Uygulama mağazasından toplu satın alınan uygulamaları atama ve izleme|Hayır|Hayır|Hayır|Evet|
|Cihazlara uygulamaları zorunlu yükleme (Gerekli)<sup>2</sup>|Evet|Evet|Evet|Evet|
|Şirket Portalı’ndan cihazlara isteğe bağlı yükleme (Kullanılabilir yükleme)|Evet|Evet|Evet|Evet|
|Web’deki bir uygulamanın kısayolunu yükleme (web klibi)|Evet|Evet|Evet|Evet|
|Şirket içi (iş kolu) uygulamalar|Evet|Evet|Hayır|Hayır|
|Mağazadan uygulamalar|Evet|Evet|Evet|Evet|
|Uygulamaları güncelleştirme|Evet|Evet|Evet|Evet|

<sup>1</sup> Windows 10 çalıştıran cihazlardaki uygulamaları korumak için [Windows Bilgi Koruması]windows-information-protection-configure.md) kullanabilirsiniz.

<sup>2</sup>Yalnızca Intune tarafından yönetilen cihazlar için geçerlidir.


## <a name="how-to-get-started"></a>Nereden başlayacaksınız

Aşağıda gösterilen yolla erişilen **Mobil Uygulamalar** iş yükünde, uygulamayla ilgili bilgilerin çoğunu bulabilirsiniz:

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Mobil uygulamalar**’ı seçin.

    ![Mobil Uygulamalar iş yükü](./media/apps-workload.png)

### <a name="manage"></a>Bilgisayarlarda
- **Uygulamalar** - Burası, uygulamalarınızın çoğunu eklediğiniz, atadığınız ve izlediğiniz yerdir. 
    - [Uygulamaları ekleme](apps-add.md)
    - [Uygulamaları atama](apps-deploy.md)
    - [Uygulamaları izleme](apps-monitor.md)
- **Uygulama yapılandırma ilkeleri** - Uygulama yapılandırma ilkeleri, kullanıcı bir uygulama çalıştırdığında gerekebilecek ayarları sağlamanıza olanak tanır. Ayrıntılar için bkz.
    - [Uygulama yapılandırma ilkeleri](app-configuration-policies.md)
- **Uygulama koruma ilkeleri** - Uygulamanın kullandığı şirket verilerini korumaya yardımcı olması için ayarları uygulamayla ilişkilendirmenizi sağlar. Örneğin, bir uygulamanın diğer uygulamalarla iletişim kurma özelliklerini kısıtlayabilir veya kullanıcının şirket uygulamasına erişmek için PIN girmesini isteyebilirsiniz.
    - [Uygulama koruma ilkeleri](app-protection-policies.md)
- **Uygulama seçmeli silme** - Seçtiğiniz kullanıcının cihazından yalnızca şirket verilerini kaldırın.
    - [Uygulama seçmeli silme](apps-selective-wipe.md)
- **iOS sağlama profilleri** - iOS uygulamaları, bir sağlama profili ve bir sertifika tarafından imzalanmış kod içerir. Sertifikanın süresi dolduğunda, uygulama artık çalıştırılamaz. Intune size süresi dolmak üzere olan uygulamaların bulunduğu cihazlara yeni sağlama profili ilkesini önceden atamak için araçlar verir.
    - [iOS uygulama sağlama profilleri](app-provisioning-profile-ios.md)

### <a name="monitor"></a>İzle
- **Lisanslı Uygulamalar** - Uygulama mağazalarından toplu satın alınan uygulamaları görüntüleyin, atayın ve izleyin.
    - [İş İçin Windows Mağazası’ndan toplu satın alınan uygulamalar](windows-store-for-business.md)
- **Bulunan Uygulamalar** - Intune tarafından atanan ve bir cihaza yüklenen tüm uygulamaları gösterir.
- **Uygulama Yükleme Durumu** - Oluşturduğunuz uygulama atamasının durumunu gösterir.
- **Uygulama koruma durumu** - Seçtiğiniz kullanıcı için uygulama koruma ilkesinin durumunu gösterir.

Ayrıntılar için bkz. [Uygulamaları izleme](apps-monitor.md)

### <a name="setup"></a>Setup
<!--- **iOS VPP Tokens**
    - [iOS volume-purchased apps](vpp-apps-ios.md) --->
- **İş İçin Windows Mağazası** - İş İçin Windows Mağazası’na tümleştirmeyi kurun. Bunu yaptıktan sonra, satın alınan uygulamaları Intune’a eşitleyebilir, bunları atayabilir ve lisans kullanımınızı izleyebilirsiniz. 
    - [İş İçin Windows Mağazası’ndan toplu satın alınan uygulamalar](windows-store-for-business.md)
- **Şirket Portalı markası** - Şirket Portalı’nı özelleştirerek şirketinizin markasını ekleyin. 
    - [Şirket portalı yapılandırması](company-portal-app.md)

