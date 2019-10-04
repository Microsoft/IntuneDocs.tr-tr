---
title: Microsoft Intune 'de uygulama yönetimi nedir?
titleSuffix: ''
description: Microsoft Intune için platforma göre istemci uygulama yönetimi özellikleri hakkında bilgi edinin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/23/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 1975a2dc-3a14-4cb9-9afb-e2ba01a1c51b
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8b630709646b2f4489cbfea6284689c9436798ca
ms.sourcegitcommit: 78f9750712c254d8b123ef15b74f30ca999aa128
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/03/2019
ms.locfileid: "71916360"
---
# <a name="what-is-microsoft-intune-app-management"></a>Microsoft Intune uygulama yönetimi nedir?


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

BT Yöneticisi olarak, şirketinizin iş gücünün kullandığı istemci uygulamalarını yönetmek için Microsoft Intune kullanabilirsiniz. Bu işlev, cihazları yönetmeye ve verileri korumaya ek niteliğindedir. Yönetici önceliklerinden biri, son kullanıcıların işlerini yapmak için ihtiyaç duydukları uygulamalara erişmesini sağlamaktır. Bu amaç bir sorun olabilir, çünkü:
- Çok çeşitli cihaz platformları ve uygulama türleri vardır.
- Hem şirket cihazlarındaki hem de kullanıcıların kişisel cihazlarındaki uygulamaları yönetmeniz gerekebilir.
- Ağınızın ve verilerinizin güvende olduğundan emin olmanız gerekir.

Ayrıca, Intune 'a kayıtlı olmayan cihazlarda uygulama atamak ve yönetmek isteyebilirsiniz.

## <a name="mobile-application-management-mam-basics"></a>Mobil uygulama yönetimi (MAM) temelleri

[Intune mobil uygulama yönetimi](app-lifecycle.md) , kullanıcılarınız için mobil uygulamaları yayımlama, gönderme, yapılandırma, güvenli hale getirme, izleme ve güncelleştirme olanağı sağlayan Intune yönetim özellikleri paketini ifade eder.

MAM, kuruluşunuzun verilerini bir uygulama içinde yönetmenizi ve korumanızı sağlar. **Kayıt olmadan mam** (mam-we) ile, hassas veriler içeren iş veya okul ile ilgili bir uygulama, **kendi cihazını getir** (KCG) senaryolarında kişisel cihazlar dahil olmak üzere neredeyse her [cihazda](app-management.md#app-management-capabilities-by-platform)yönetilebilir. Microsoft Office uygulamalar gibi birçok üretkenlik uygulaması, Intune MAM tarafından yönetilebilir. Genel kullanıma sunulan [Microsoft Intune korunan uygulamaların](apps-supported-intune-apps.md) resmi listesine bakın.

Intune MAM iki yapılandırmayı destekler:
- **INTUNE MDM + mam**: BT yöneticileri, yalnızca Intune mobil cihaz YÖNETIMI (MDM) ile KAYDEDILEN cihazlarda mam ve uygulama koruma ilkelerini kullanarak uygulamaları yönetebilir. MDM + MAM kullanarak uygulamaları yönetmek için müşteriler Azure portal Intune konsolunu https://portal.azure.com ' da kullanmalıdır.
- **Cihaz kaydı olmadan mam**: cihaz kaydı olmadan MAM veya mam-we, BT YÖNETICILERININ Intune MDM 'ye kayıtlı olmayan cihazlarda mam ve uygulama koruma ilkelerini kullanarak uygulamaları yönetmesine olanak tanır. Bu, uygulamaların, üçüncü taraf EMM sağlayıcılarına kayıtlı cihazlarda Intune tarafından yönetilebileceği anlamına gelir. Uygulamaları MAM-WE kullanarak yönetmek için, müşteriler Azure portal Intune konsolunu https://portal.azure.com ' da kullanmalıdır. Ayrıca, uygulamalar, üçüncü taraf Enterprise Mobility Management (EMM) sağlayıcılarıyla kaydedilmiş cihazlarda veya bir MDM ile kayıtlı olmayan cihazlarda Intune tarafından yönetilebilir. KCG ve Microsoft 'un EMS hakkında daha fazla bilgi için, [Microsoft Enterprise Mobility + Security (EMS) ile KCG 'yi etkinleştirmek Için teknoloji kararları](../fundamentals/byod-technology-decisions.md)bölümüne bakın.

## <a name="app-management-capabilities-by-platform"></a>Platforma göre uygulama yönetimi özellikleri

Intune, ihtiyacınız olan uygulamaları çalıştırmak istediğiniz cihazlara almanıza yardımcı olacak bir dizi özellik sunar. Aşağıdaki tabloda, uygulama yönetimi yeteneklerinin bir özeti verilmiştir.

|  | Android/Android kurumsal | iOS | macOS | Windows 10 | Windows Phone 8.1 |
|-------------------------------------------------------------------------------------|---------|-----|-------|------------|-------------------|
| Cihazlara ve kullanıcılara uygulama ekleme ve atama | Evet | Evet | Evet | Evet | Evet |
| Intune 'a kayıtlı olmayan cihazlara uygulama atama | Evet | Evet | Hayır | Hayır | Hayır |
| Uygulamaların başlangıç davranışını denetlemek için uygulama yapılandırma ilkelerini kullanma | Evet | Evet | Hayır | Hayır | Hayır |
| Vadesi geçen uygulamaları yenilemek için mobil uygulama sağlama ilkelerini kullanma | Hayır | Evet | Hayır | Hayır | Hayır |
| Uygulama koruma ilkeleriyle uygulamalardaki şirket verilerini koruma | Evet | Evet | Hayır | <sup>1</sup> yok | Hayır |
| Yüklü bir uygulamadan yalnızca şirket verilerini kaldırma (uygulama seçmeli silme) | Evet | Evet | Hayır | Evet | Evet |
| Uygulama atamalarını izleme | Evet | Evet | Evet | Evet | Evet |
| Bir App Store 'dan toplu satın alınan uygulamaları atama ve izleme | Hayır | Hayır | Hayır | Evet | Hayır |
| Cihazlarda uygulamaların zorunlu yüklenmesi (gerekli) <sup>2</sup> | Evet | Evet | Evet | Evet | Evet |
| Şirket Portalı cihazlarda isteğe bağlı yükleme (kullanılabilir yükleme) | Evet <sup>3</sup> | Evet | Evet | Evet | Evet |
| Web üzerinde bir uygulamaya kısayol yükler (Web bağlantısı) | Evet <sup>4</sup> | Evet | Evet | Evet | Evet |
| Şirket içi (iş kolu) uygulamalar | Evet | Evet | Evet | Evet | Hayır |
| Bir mağazadan uygulamalar | Evet | Evet | Hayır | Evet | Evet |
| Uygulamaları güncelleştirme | Evet | Evet | Hayır | Evet | Evet |

<sup>1</sup> Windows 10 çalıştıran cihazlardaki uygulamaları korumak için [Windows Information Protection](../protect/windows-information-protection-configure.md) kullanmayı düşünün.<br>
<sup>2</sup> yalnızca Intune tarafından yönetilen cihazlara uygulanır.<br>
<sup>3</sup> Intune, Android kurumsal cihazlarda yönetilen Google Play deposundan kullanılabilir uygulamaları destekler.<br>
<sup>4</sup> Intune, standart Android kurumsal cihazlarda bir Web bağlantısı olarak uygulamanın kısayolunu yüklemeyi sağlamaz. Öte yandan, [çok uygulamayla ayrılmış Android Kurumsal cihazları](../configuration/device-restrictions-android-for-work.md#dedicated-device-settings)için Web bağlantısı desteği sağlanır. 


## <a name="get-started"></a>Kullanmaya başlayın

Aşağıdaki işlemleri gerçekleştirerek erişebileceğiniz **Istemci uygulamaları** iş yükünde uygulamayla ilgili bilgilerin çoğunu bulabilirsiniz:

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
3. **Microsoft Intune** bölmesinde, **istemci uygulamaları**' nı seçin.

    !["Istemci uygulamaları" iş yükü bölmesi](./media/app-management/apps-workload.png)

Sonraki dört bölüm, **istemci uygulamaları** bölmesinde bulunan seçenekleri anlatmaktadır.

### <a name="manage"></a>Yönetebilmeniz
- **Uygulamalar**: iş gücünüzün kullandığı uygulamaları eklemek, görüntülemek, atamak ve izlemek için bu seçeneği belirleyin. Daha fazla bilgi için bkz.:
  - [Uygulamalar ekleyin](apps-add.md).
  - [Uygulama atama](apps-deploy.md).
  - [Uygulamaları izleyin](apps-monitor.md).
- **Uygulama yapılandırma ilkeleri**: Kullanıcı bir uygulama çalıştırdığında gerekebilecek ayarları sağlamak için bu seçeneği belirleyin. Daha fazla bilgi için bkz.:
  - [Intune Için uygulama yapılandırma ilkeleri](app-configuration-policies-overview.md).
    - [iOS uygulama yapılandırma ilkeleri](app-configuration-policies-use-ios.md).
    - [Android uygulama yapılandırma ilkeleri](app-configuration-policies-use-android.md).
- **Uygulama koruma ilkeleri**: ayarları bir uygulamayla ilişkilendirmek ve kullandığı şirket verilerinin korunmasına yardımcı olmak için bu seçeneği belirleyin. Örneğin, bir uygulamanın yeteneklerini diğer uygulamalarla iletişim kuracak şekilde kısıtlayabilir veya kullanıcının bir şirket uygulamasına erişmek için PIN girmesini isteyebilirsiniz. Daha fazla bilgi için bkz.:
  - [Uygulama koruma ilkeleri](app-protection-policies.md).
- **Uygulama seçmeli silme**: seçili bir kullanıcının cihazından yalnızca şirket verilerini kaldırmak için bu seçeneği belirleyin. Daha fazla bilgi için bkz.:
  - [Uygulama seçmeli silme](apps-selective-wipe.md).
- **iOS uygulama sağlama profilleri**: iOS uygulamaları, bir sertifika tarafından imzalanmış bir sağlama profili ve kodu içerir. Sertifikanın süresi dolarsa, uygulama artık çalıştırılamaz. Intune, size süresi dolmak üzere olan uygulamaların bulunduğu cihazlara yeni sağlama profili ilkesini önceden atamak için araçlar sağlar. Daha fazla bilgi için bkz.:
  - [iOS uygulama sağlama profilleri](app-provisioning-profile-ios.md).

Bu bölüm hakkında daha fazla bilgi için bkz. [Uygulamaları yönetme](app-management.md).

### <a name="monitor"></a>İzle
- **Uygulama lisansları**: uygulama mağazalarından toplu satın alınan uygulamaları görüntüleyin, atayın ve izleyin. Daha fazla bilgi için bkz.:
  - [iOS toplu satın alınan program (VPP) uygulamaları](vpp-apps-ios.md).
  - [Toplu satın alınan uygulamalar için Microsoft Store](windows-store-for-business.md).
- **Bulunan uygulamalar**: Intune tarafından atanan veya bir cihaza yüklenen uygulamaları görüntüleyin. Daha fazla bilgi için bkz. [Intune bulunan uygulamalar](app-discovered-apps.md).
- **Uygulama yüklemesi durumu**: oluşturduğunuz uygulama atamasının durumunu görüntüleyin. Daha fazla bilgi için bkz. [Microsoft Intune ile uygulama bilgilerini ve atamaları izleme](apps-monitor.md#device-and-user-status-graphs).
- **Uygulama koruma durumu**: seçtiğiniz bir kullanıcı için uygulama koruma ilkesinin durumunu görüntüleyin.
- **Denetim günlükleri**: tüm BT yöneticilerinin Intune uygulamasıyla ilgili etkinliğini görüntüleyin.

Bu bölüm hakkında daha fazla bilgi için bkz. [uygulamaları izleme](apps-monitor.md).

### <a name="set-up"></a>Ayarla
- **IOS VPP belirteçleri**: IOS toplu satın alma programı (VPP) lisanslarınızı uygulayın ve görüntüleyin. Daha fazla bilgi için bkz.:
  - [iOS toplu satın alınan uygulamalar](vpp-apps-ios.md)
- **Windows Enterprise sertifikası**: iş kolu uygulamalarını yönetilen Windows cihazlarınıza dağıtmak için kullanılan kod imzalama sertifikasının durumunu uygulayın veya görüntüleyin.
- **Windows Symantec sertifikası**: Windows 10 MOBILE cihazlarına XAP ve WP8. x appx dosyalarını dağıtmak için gereken bir Symantec kod imzalama sertifikasının durumunu uygulayın veya görüntüleyin.
- **İş Microsoft Store**: iş için Microsoft Store tümleştirmesini ayarlayın. Daha sonra, satın alınan uygulamaları Intune 'a eşitleyebilir, bunları atayabilir ve lisans kullanımınızı izleyebilirsiniz. Daha fazla bilgi için bkz.:
  - [Toplu satın alınan uygulamalar için Microsoft Store](windows-store-for-business.md).
- **Windows dışarıdan yükleme anahtarları**: uygulamayı Windows Mağazası 'ndan yayımlamak ve indirmek yerine doğrudan cihazlara yüklemek için kullanılabilecek bir Windows dışarıdan yükleme anahtarı ekleyin. Daha fazla bilgi için bkz.:
  - [Bir Windows uygulamasını dışarıdan yükleyin](app-sideload-windows.md).
- **Şirket portalı marka**: şirketinizin markalamasını sağlamak için şirket portalı özelleştirin. Daha fazla bilgi için bkz.:
  - [Şirket portalı yapılandırma](company-portal-app.md).
- **Uygulama kategorileri**: uygulama kategorisi adlarını ekleyin, sabitleyin ve silin.
- **Android iş profili**: kuruluşunuz için onayladığınız uygulamaları onaylayın ve eşitleyin. Daha fazla bilgi için bkz.:
  - [Android iş profili uygulamaları](apps-add-android-for-work.md).

### <a name="help-and-support"></a>Yardım ve destek
- **Yardım ve destek**: sorun giderin, destek Isteyin veya Intune durumunu görüntüleyin. Daha fazla bilgi için bkz.:
  - [Sorunları giderin](../fundamentals/help-desk-operators.md).

## <a name="next-steps"></a>Sonraki adımlar

- [Microsoft Intune bir uygulama ekleyin](apps-add.md)
