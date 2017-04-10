---
title: "Uygulama yönetimi nedir?"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Microsoft Intune’la uygulama yönetimi hakkındaki temel bilgileri edinmek için bu konuyu kullanın"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1975a2dc-3a14-4cb9-9afb-e2ba01a1c51b
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 33def827fc7417930338e56c650d01df4dad85fb
ms.lasthandoff: 02/18/2017


---

# <a name="what-is-microsoft-intune-app-management"></a>Microsoft Intune uygulama yönetimi nedir?


[!INCLUDE[azure_preview](../includes/azure_preview.md)]


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

<sup>1</sup> Windows 10 çalıştıran cihazlarda uygulamaları korumak için [Windows Bilgi Koruması](/intune-azure/configure-devices/how-to-configure-windows-information-protection)’nu kullanmayı göz önüne alabilirsiniz.

<sup>2</sup>Yalnızca Intune tarafından yönetilen cihazlar için geçerlidir.


## <a name="how-to-get-started"></a>Nereden başlayacaksınız

Aşağıda gösterilen yolla erişilen **Mobil Uygulamalar** iş yükünde, uygulamayla ilgili bilgilerin çoğunu bulabilirsiniz:

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Uygulamaları yönet**’i seçin.

    ![Mobil Uygulamalar iş yükü](./media/apps-workload.png)

### <a name="manage"></a>Bilgisayarlarda
- **Uygulamalar** - Burası, uygulamalarınızın çoğunu eklediğiniz, atadığınız ve izlediğiniz yerdir. 
    - [Uygulamaları ekleme](add-apps.md)
    - [Uygulamaları atama](deploy-apps.md)
    - [Uygulamaları izleme](monitor-apps.md)
- **Lisanslı Uygulamalar** - Uygulama mağazalarından toplu satın alınan uygulamaları görüntüleyin, dağıtın ve izleyin.
    - [İş İçin Windows Mağazası’ndan toplu satın alınan uygulamalar](wsfb-apps.md)
- **Uygulama Yapılandırma İlkeleri** - Uygulanma yapılandırma ilkeleri, kullanıcı bir uygulama çalıştırdığında gerekebilecek ayarları sağlamanıza olanak tanır. Ayrıntılar için bkz.
    - [Uygulama yapılandırma ilkeleri](app-configuration-policies.md)
- **Uygulama Koruma İlkeleri** - Uygulamanın kullandığı şirket verilerini korumaya yardımcı olması için ayarları uygulamayla ilişkilendirmenizi sağlar. Örneğin, bir uygulamanın diğer uygulamalarla iletişim kurma özelliklerini kısıtlayabilir veya kullanıcının şirket uygulamasına erişmek için PIN girmesini isteyebilirsiniz.
    - [Uygulama koruma ilkeleri](app-protection-policies.md)
- **Uygulama Seçmeli Silme** - Seçtiğiniz kullanıcının cihazından yalnızca şirket verilerini kaldırın.
    - [Uygulama seçmeli silme](app-selective-wipe.md)

### <a name="monitor"></a>İzle
- **Bulunan Uygulamalar** - Intune tarafından atanan ve bir cihaza yüklenen tüm uygulamaları gösterir.
- **Uygulama Yükleme Durumu** - Oluşturduğunuz uygulama atamasının durumunu gösterir.
- **Uygulama Koruma Kullanıcı Durumu** - Seçtiğiniz kullanıcı için uygulama koruma ilkesinin durumunu gösterir.

Ayrıntılar için bkz. [Uygulamaları izleme](monitor-apps.md)

### <a name="setup"></a>Setup
<!--- **iOS VPP Tokens**
    - [iOS volume-purchased apps](ios-vpp-apps.md) --->
- **İş İçin Windows Mağazası** - İş İçin Windows Mağazası’na tümleştirmeyi kurun. Bunu yaptıktan sonra, satın alınan uygulamaları Intune’a eşitleyebilir, bunları atayabilir ve lisans kullanımınızı izleyebilirsiniz. 
    - [İş İçin Windows Mağazası’ndan toplu satın alınan uygulamalar](wsfb-apps.md)
- **Şirket Portalı Markası** - Şirket Portalı’nı özelleştirerek şirketinizin markasını ekleyin. 
    - [Şirket portalı yapılandırması](company-portal-app.md)

