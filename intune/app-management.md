---
title: "Uygulama yönetimi nedir?"
titleSuffix: Intune on Azure
description: "Microsoft Intune’la uygulama yönetimi hakkındaki temel bilgileri edinmek için bu konuyu kullanın\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/11/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1975a2dc-3a14-4cb9-9afb-e2ba01a1c51b
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 33ddb60df7aebe36ff652e1da6da592442b96d4b
ms.sourcegitcommit: fb17b59f4aa2b994b149fcc6d32520f74b0de6a5
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2017
---
# Microsoft Intune uygulama yönetimi nedir?
<a id="what-is-microsoft-intune-app-management" class="xliff"></a>


[!INCLUDE[azure_portal](./includes/azure_portal.md)]


BT yöneticisi olarak, son kullanıcılarınızın işlerini yapmak için ihtiyaçları olan uygulamalara erişmelerini sağlamak sizin sorumluluğunuzdur. Bu zor olabilir çünkü:
- Çok çeşitli cihaz platformları ve uygulama türleri vardır.
- Şirket cihazlarındaki uygulamaları ve kullanıcıların kendi cihazlarındaki uygulamaları yönetmeniz gerekebilir.
- Ağınızın ve verilerinizi güvenli kaldığından emin olmanız gerekir.

Buna ek olarak, Intune’a kaydolmamış cihazlarda uygulamaları atamak ve yönetmek isteyebilirsiniz.

Intune, ihtiyacınız olan uygulamaları istediğiniz cihazlara almanıza yardımcı olacak çeşitli özellikler sunar.

## Platforma göre uygulama yönetimi özellikleri
<a id="app-management-capabilities-by-platform" class="xliff"></a>

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

<sup>1</sup> Windows 10 çalıştıran cihazlarda uygulamaları korumak için [Windows Bilgi Koruması](windows-information-protection-configure.md)’nu kullanmayı göz önüne alabilirsiniz.

<sup>2</sup>Yalnızca Intune tarafından yönetilen cihazlar için geçerlidir.

## Nereden başlayacaksınız
<a id="how-to-get-started" class="xliff"></a>

Aşağıda gösterilen yolla erişilen **Mobil Uygulamalar** iş yükünde, uygulamayla ilgili bilgilerin çoğunu bulabilirsiniz:

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Mobil uygulamalar**’ı seçin.

    ![Mobil Uygulamalar iş yükü](./media/apps-workload.png)

### Bilgisayarlarda
<a id="manage" class="xliff"></a>
- **Uygulamalar** - Bu düğüm, uygulamalarınızın çoğunu eklediğiniz, atadığınız ve izlediğiniz yerdir.
    - [Uygulamaları ekleme](apps-add.md)
    - [Uygulamaları atama](apps-deploy.md)
    - [Uygulamaları izleme](apps-monitor.md)
- **Uygulama yapılandırma ilkeleri** - Uygulama yapılandırma ilkeleri, kullanıcı bir uygulama çalıştırdığında gerekebilecek ayarları sağlamanıza olanak tanır.
    - [iOS uygulama yapılandırma ilkeleri](app-configuration-policies-use-ios.md)
    - [Android uygulama yapılandırma ilkeleri](app-configuration-policies-use-android.md)
- **Uygulama koruma ilkeleri** - Uygulamanın kullandığı şirket verilerini korumaya yardımcı olması için ayarları uygulamayla ilişkilendirmenizi sağlar. Örneğin, bir uygulamanın diğer uygulamalarla iletişim kurma özelliklerini kısıtlayabilir veya kullanıcının şirket uygulamasına erişmek için PIN girmesini isteyebilirsiniz.
    - [Uygulama koruma ilkeleri](app-protection-policies.md)
- **Uygulama seçmeli silme** - Seçtiğiniz kullanıcının cihazından yalnızca şirket verilerini kaldırın.
    - [Uygulama seçmeli silme](apps-selective-wipe.md)
- **iOS sağlama profilleri** - iOS uygulamaları, bir sağlama profili ve bir sertifika tarafından imzalanmış kod içerir. Sertifikanın süresi dolduğunda, uygulama artık çalıştırılamaz. Intune size süresi dolmak üzere olan uygulamaların bulunduğu cihazlara yeni sağlama profili ilkesini önceden atamak için araçlar verir.
    - [iOS uygulama sağlama profilleri](app-provisioning-profile-ios.md)

### İzle
<a id="monitor" class="xliff"></a>
- **Lisanslı Uygulamalar** - Uygulama mağazalarından toplu satın alınan uygulamaları görüntüleyin, atayın ve izleyin.
    - [İş İçin Windows Mağazası’ndan toplu satın alınan uygulamalar](windows-store-for-business.md)
- **Bulunan Uygulamalar** - Intune tarafından atanan ve bir cihaza yüklenen tüm uygulamaları gösterir.
- **Uygulama Yükleme Durumu** - Oluşturduğunuz uygulama atamasının durumunu gösterir.
- **Uygulama koruma durumu** - Seçtiğiniz kullanıcı için uygulama koruma ilkesinin durumunu gösterir.

Ayrıntılar için bkz. [Uygulamaları izleme](apps-monitor.md)

### Setup
<a id="setup" class="xliff"></a>
<!--- **iOS VPP Tokens**
    - [iOS volume-purchased apps](vpp-apps-ios.md) --->
- **İş İçin Windows Mağazası** - İş İçin Windows Mağazası’na tümleştirmeyi kurun. Bundan sonra, satın alınan uygulamaları Intune’a eşitleyebilir, bunları atayabilir ve lisans kullanımınızı izleyebilirsiniz.
    - [İş İçin Windows Mağazası’ndan toplu satın alınan uygulamalar](windows-store-for-business.md)
- **Şirket Portalı markası** - Şirket Portalı’nı özelleştirerek şirketinizin markasını ekleyin.
    - [Şirket portalı yapılandırması](company-portal-app.md)
