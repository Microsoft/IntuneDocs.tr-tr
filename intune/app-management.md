---
title: "Microsoft Intune’da uygulama yönetimi nedir?"
titlesuffix: 
description: "Microsoft Intune ile uygulama yönetimi hakkındaki temel bilgileri öğrenin."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/01/2018
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1975a2dc-3a14-4cb9-9afb-e2ba01a1c51b
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9372a77a63f48c8215a02ccd784fb0a812f5a12f
ms.sourcegitcommit: aafed032492c1b5861d7097a335f9bbb29ce3221
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/02/2018
---
# <a name="what-is-microsoft-intune-app-management"></a>Microsoft Intune uygulama yönetimi nedir?


[!INCLUDE[azure_portal](./includes/azure_portal.md)]


Microsoft Intune, BT yöneticisi olarak, şirketinizin iş gücünün kullandığı mobil uygulamaları yönetmenizi sağlar. Bu işlev, cihazları yönetmeye ve verileri korumaya ek niteliğindedir. Bu işlevin bir parçası olarak, önceliklerinizden biri son kullanıcılarınızın işlerini yapmak için ihtiyaç duydukları uygulamalara erişebilmelerini sağlamaktır. Bu zor olabilir çünkü:
- Çok çeşitli cihaz platformları ve uygulama türleri vardır.
- Hem şirket cihazlarındaki hem de kullanıcıların kendi cihazlarındaki uygulamaları yönetmeniz gerekebilir.
- Ağınızın ve verilerinizi güvenli kaldığından emin olmanız gerekir.

Buna ek olarak, Intune’a kaydolmamış cihazlarda uygulamaları atamak ve yönetmek isteyebilirsiniz.

Intune, ihtiyacınız olan uygulamaları istediğiniz cihazlara almanıza yardımcı olacak çeşitli özellikler sunar. Aşağıdaki tablo, uygulama yönetimi özelliklerinin bir özetini sağlar. Aşağıdaki tablo, Azure portalında Microsoft Intune'u anlamak için bir başlangıç noktasıdır. 

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
|Şirket içi (iş kolu) uygulamalar|Evet|Evet|Hayır|Evet|
|Mağazadan uygulamalar|Evet|Evet|Evet|Evet|
|Uygulamaları güncelleştirme|Evet|Evet|Evet|Evet|

<sup>1</sup> Windows 10 çalıştıran cihazlarda uygulamaları korumak için [Windows Bilgi Koruması](windows-information-protection-configure.md)’nu kullanmayı göz önüne alabilirsiniz.

<sup>2</sup>Yalnızca Intune tarafından yönetilen cihazlar için geçerlidir.

## <a name="how-to-get-started"></a>Nereden başlayacaksınız

Aşağıda gösterilen yolla erişilen **Mobil Uygulamalar** iş yükünde, uygulamayla ilgili bilgilerin çoğunu bulabilirsiniz:

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** dikey penceresinde **Mobil uygulamalar**’ı seçin.

    ![Mobil Uygulamalar iş yükü](./media/apps-workload.png)

### <a name="manage"></a>Bilgisayarlarda
- **Uygulamalar** - Bu düğüm, uygulamalarınızın çoğunu eklediğiniz, atadığınız ve izlediğiniz yerdir.
    - [Uygulamaları ekleme](apps-add.md)
    - [Uygulamaları atama](apps-deploy.md)
    - [Uygulamalarını izleme](apps-monitor.md)
- **Uygulama yapılandırma ilkeleri** - Uygulama yapılandırma ilkeleri, kullanıcı bir uygulama çalıştırdığında gerekebilecek ayarları sağlamanıza olanak tanır.
    - [iOS uygulama yapılandırma ilkeleri](app-configuration-policies-use-ios.md)
    - [Android uygulama yapılandırma ilkeleri](app-configuration-policies-use-android.md)
- **Uygulama koruma ilkeleri** - Uygulamanın kullandığı şirket verilerini korumaya yardımcı olması için ayarları uygulamayla ilişkilendirmenizi sağlar. Örneğin, bir uygulamanın diğer uygulamalarla iletişim kurma özelliklerini kısıtlayabilir veya kullanıcının şirket uygulamasına erişmek için PIN girmesini isteyebilirsiniz.
    - [Uygulama koruma ilkeleri](app-protection-policies.md)
- **Uygulama seçmeli silme** - Seçtiğiniz kullanıcının cihazından yalnızca şirket verilerini kaldırın.
    - [Uygulama seçmeli silme](apps-selective-wipe.md)
- **iOS sağlama profilleri** - iOS uygulamaları, bir sağlama profili ve bir sertifika tarafından imzalanmış kod içerir. Sertifikanın süresi dolduğunda, uygulama artık çalıştırılamaz. Intune size süresi dolmak üzere olan uygulamaların bulunduğu cihazlara yeni sağlama profili ilkesini önceden atamak için araçlar verir.
    - [iOS uygulama sağlama profilleri](app-provisioning-profile-ios.md)

Daha fazla ayrıntı için, bkz. [Uygulamaları yönetme](app-management.md).

### <a name="monitor"></a>İzle
- **Uygulama lisansları** - Uygulama mağazalarından toplu satın alınan uygulamaları görüntüleyin, atayın ve izleyin.
    - [İş İçin Microsoft Mağazası’ndan toplu satın alınan uygulamalar](windows-store-for-business.md)
- **Bulunan Uygulamalar** - Intune tarafından atanan ve bir cihaza yüklenen tüm uygulamaları gösterir.
- **Uygulama Yükleme Durumu** - Oluşturduğunuz uygulama atamasının durumunu gösterir.
- **Uygulama koruma durumu** - Seçtiğiniz kullanıcı için uygulama koruma ilkesinin durumunu gösterir.
- **Denetim günlükleri** - Tüm BT yöneticileri tarafından gerçekleştirilen Intune uygulamasıyla ilgili etkinlikleri gösterir.

Diğer ayrıntılar için bkz. [Uygulamaları izleme](apps-monitor.md).

### <a name="setup"></a>Setup
- **iOS VPP belirteçleri** - iOS Volume Purchase Program (VPP) lisanslarınızı uygulayın ve görüntüleyin.
    - [Toplu satın alınan iOS uygulamaları](vpp-apps-ios.md)
- **Windows Enterprise sertifikası** - Yönetilen Windows cihazlarınıza iş kolu uygulamalarını dağıtmak için kullanılan kod imzalama sertifikasını uygulayın veya durumunu görüntüleyin. 
- **Windows Symantec sertifikası** - Windows 10 Mobile cihazlarına XAP ve WP8.x appx dosyalarını dağıtmak için gereken kod imzalama sertifikasını uygulayın veya durumunu görüntüleyin. 
- **İş İçin Microsoft Mağazası** - İş İçin Microsoft Mağazası’na tümleştirmeyi kurun. Bundan sonra, satın alınan uygulamaları Intune’a eşitleyebilir, bunları atayabilir ve lisans kullanımınızı izleyebilirsiniz.
    - [İş İçin Microsoft Mağazası’ndan toplu satın alınan uygulamalar](windows-store-for-business.md)
- **Windows dışarıdan yükleme anahtarları** - Uygulamayı Windows mağazasından yayımlamak ve indirmek yerine doğrudan cihazlara yüklemek için kullanılabilecek bir Windows dışarıdan yükleme anahtarı ekleyebilirsiniz.
    - [Windows uygulamasını dışarıdan yükleme](app-sideload-windows.md) 
- **Şirket Portalı markası** - Şirket Portalı’nı özelleştirerek şirketinizin markasını ekleyin.
    - [Şirket portalı yapılandırması](company-portal-app.md)
- **Uygulama kategorileri** - Uygulama kategorisi adlarını ekleyin, sabitleyin ve silin.
- **Android for Work** - Kuruluşunuz için onayladığınız uygulamaları onaylayın ve eşitleyin.
    - [Android for Work uygulamalarını](apps-add-android-for-work.md) 

### <a name="help-and-support"></a>Yardım ve Destek
- **Yardım ve destek** - Sorun giderin, destek isteyin veya Intune durumunu görüntüleyin.
    - [Sorunları giderme](help-desk-operators.md)
    
## <a name="next-steps"></a>Sonraki adımlar

- [Microsoft Intune’a uygulama ekleme](apps-add.md)
