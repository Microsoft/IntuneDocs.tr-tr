---
title: Microsoft Intune’da uygulama yönetimi nedir?
titleSuffix: ''
description: Microsoft Intune tarafından sağlanan platforma göre istemci uygulaması yönetim özellikleri hakkında bilgi edinin.
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
ms.openlocfilehash: 063e78fb716d27843ce017389da7a01f12fee70b
ms.sourcegitcommit: c8cb314256c4896e838918f015ffaefb8f00ace5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/23/2019
ms.locfileid: "71303778"
---
# <a name="what-is-microsoft-intune-app-management"></a>Microsoft Intune uygulama yönetimi nedir?


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

BT yöneticisi olarak Microsoft Intune'u şirketinizin iş gücünün kullandığı istemci uygulamaları yönetmek için kullanabilirsiniz. Bu işlev, cihazları yönetmeye ve verileri korumaya ek niteliğindedir. Yöneticinin önceliklerinden biri, son kullanıcıların işlerini yapabilmeleri için gereken uygulamalara erişimleri olduğundan emin olmaktır. Bu amaca ulaşmak zor olabilir çünkü:
- Çok çeşitli cihaz platformları ve uygulama türleri vardır.
- Hem şirket cihazlarındaki hem de kullanıcıların kişisel cihazlarındaki uygulamaları yönetmeniz gerekebilir.
- Ağınızın ve verilerinizi güvenli kaldığından emin olmanız gerekir.

Buna ek olarak, Intune’a kaydolmamış cihazlarda uygulamaları atamak ve yönetmek isteyebilirsiniz.

## <a name="mobile-application-management-mam-basics"></a>Mobil uygulama yönetimi (MAM) temelleri

[Intune mobil uygulama yönetimi](app-lifecycle.md), kullanıcılarınız için mobil uygulamaları yayımlama, gönderme, yapılandırma, güvenlik altına alma, izleme ve güncelleştirme gibi eylemler gerçekleştirmenize olanak tanıyan Intune yönetim özellikleri paketini ifade eder.

MAM, kuruluşunuzun verilerini bir uygulama içinde yönetmenizi ve korumanızı sağlar. **Kayıt olmadan mam** (mam-we) ile, hassas veriler içeren iş veya okul ile ilgili bir uygulama, **kendi cihazını getir** (KCG) senaryolarında kişisel cihazlar dahil olmak üzere neredeyse her [cihazda](app-management.md#app-management-capabilities-by-platform)yönetilebilir. Microsoft Office uygulamaları gibi birçok üretkenlik uygulaması Intune MAM tarafından yönetilebilir. Genel kullanıma sunulan [Microsoft Intune korunan uygulamaların](apps-supported-intune-apps.md) resmi listesine bakın.

Intune MAM iki yapılandırmayı destekler:
- **INTUNE MDM + mam**: BT yöneticileri, yalnızca Intune mobil cihaz yönetiminde (MDM) kayıtlı cihazlarda MAM ve uygulama koruma ilkelerini kullanarak uygulamaları yönetebilir. Uygulamaları MAM-WE kullanarak yönetmek için, müşterilerin https://portal.azure.com adresindeki Azure portalında Intune konsolunu kullanması gerekir.
- **Cihaz kaydı olmadan mam**: Cihaz kaydı olmadan MAM veya MAM-WE, BT yöneticilerinin Intune MDM 'ye kayıtlı olmayan cihazlarda MAM ve uygulama koruma ilkelerini kullanarak uygulamaları yönetmesine olanak tanır. Bu, uygulamaların üçüncü taraf EMM sağlayıcılarında kayıtlı cihazlarda Intune tarafından yönetilebileceği anlamına gelir. Uygulamaları MAM-WE kullanarak yönetmek için, müşterilerin https://portal.azure.com adresindeki Azure portalında Intune konsolunu kullanması gerekir. Ayrıca uygulamalar, üçüncü taraf Enterprise Mobility Management (EMM) sağlayıcıları ile kaydedilmiş veya hiçbir MDM ile kaydedilmemiş cihazlarda uygulamalar Intune ile yönetilebilir. KCG ve Microsoft 'un EMS hakkında daha fazla bilgi için, [Microsoft Enterprise Mobility + Security (EMS) ile KCG 'yi etkinleştirmek Için teknoloji kararları](byod-technology-decisions.md)bölümüne bakın.

## <a name="app-management-capabilities-by-platform"></a>Platforma göre uygulama yönetimi özellikleri

Intune, ihtiyacınız olan uygulamaları çalıştırmak istediğiniz cihazlara almanıza yardımcı olacak çeşitli özellikler sunar. Aşağıdaki tablo, uygulama yönetimi özelliklerinin bir özetini sağlar.

|  | Android/Android Kurumsal | iOS | Mac OS | Windows 10 | Windows Phone 8.1 |
|-------------------------------------------------------------------------------------|---------|-----|-------|------------|-------------------|
| Cihazlara ve kullanıcılara uygulamaları ekleme ve atama | Evet | Evet | Evet | Evet | Evet |
| Intune’a kayıtlı olmayan cihazlara uygulamaları atama | Evet | Evet | Hayır | Hayır | Hayır |
| Uygulamaların başlangıç davranışını denetlemek için uygulama yapılandırma ilkelerini kullanma | Evet | Evet | Hayır | Hayır | Hayır |
| Süresi dolan uygulamaları yenilemek için mobil uygulama sağlama ilkelerini kullanma | Hayır | Evet | Hayır | Hayır | Hayır |
| Uygulama koruma ilkeleriyle uygulamalardaki şirket verilerini koruma | Evet | Evet | Hayır | Hayır <sup>1</sup> | Hayır |
| Yüklü uygulamadan yalnızca şirket verilerini kaldırma (uygulama seçmeli silme) | Evet | Evet | Hayır | Evet | Evet |
| Uygulama atamalarını izleme | Evet | Evet | Evet | Evet | Evet |
| Uygulama mağazasından toplu satın alınan uygulamaları atama ve izleme | Hayır | Hayır | Hayır | Evet | Hayır |
| Cihazlara uygulamaları zorunlu yükleme (gerekli) <sup>2</sup> | Evet | Evet | Evet | Evet | Evet |
| Şirket Portalı’ndan cihazlara isteğe bağlı yükleme (kullanılabilir yükleme) | Evet <sup>3</sup> | Evet | Evet | Evet | Evet |
| Web’deki bir uygulamanın kısayolunu yükleme (web bağlantısı) | Evet <sup>4</sup> | Evet | Evet | Evet | Evet |
| Şirket içi (iş kolu) uygulamaları | Evet | Evet | Evet | Evet | Hayır |
| Mağazadan uygulamalar | Evet | Evet | Hayır | Evet | Evet |
| Uygulamaları güncelleştirme | Evet | Evet | Hayır | Evet | Evet |

<sup>1</sup> Windows 10 çalıştıran cihazlarda uygulamaları korumak için [Windows Bilgi Koruması](windows-information-protection-configure.md)’nu kullanmayı göz önüne alabilirsiniz.<br>
<sup>2</sup> Yalnızca Intune tarafından yönetilen cihazlar için geçerlidir.<br>
<sup>3</sup> Intune, Android Kurumsal cihazlarda Yönetilen Google Play mağazasında kullanılabilen uygulamaları destekler.<br>
<sup>4</sup> Intune, standart Android Kurumsal cihazlarda web bağlantısı biçiminde uygulama kısayolu yüklenmesi seçeneğini sunmaz. Ancak web bağlantısı desteği [çoklu uygulama için ayrılmış Android Kurumsal cihazlarında](device-restrictions-android-for-work.md#dedicated-device-settings) desteklenir. 


## <a name="get-started"></a>başlarken

Aşağıda gösterilen yolla erişilen **İstemci uygulamaları** iş yükünde, uygulamayla ilgili bilgilerin çoğunu bulabilirsiniz:

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
3. **Microsoft Intune** bölmesinde **İstemci uygulamaları**’nı seçin.

    !["İstemci uygulamaları" iş yükü bölmesi](./media/apps-workload.png)

Sıradaki dört bölüm, **İstemci uygulamaları** bölmesindeki kullanılabilir seçenekleri açıklar.

### <a name="manage"></a>Bilgisayarlarda
- **Uygulamalar**: İş gücünüz tarafından kullanılan uygulamaları eklemek, görüntülemek, atamak ve izlemek için bu seçeneği belirleyin. Daha fazla bilgi için bkz.
  - [Uygulama ekleme](apps-add.md).
  - [Uygulama atama](apps-deploy.md).
  - [Uygulama izleme](apps-monitor.md).
- **Uygulama yapılandırma ilkeleri**: Kullanıcı bir uygulama çalıştırdığında gerekebilecek ayarları sağlamak için bu ayarı kullanın. Daha fazla bilgi için bkz.
  - [Intune için uygulama yapılandırma ilkeleri](app-configuration-policies-overview.md).
    - [iOS uygulama yapılandırma ilkeleri](app-configuration-policies-use-ios.md).
    - [Android uygulama yapılandırma ilkeleri](app-configuration-policies-use-android.md).
- **Uygulama koruma ilkeleri**: Ayarları uygulamayla ilişkilendirmek ve kullandığı şirket verilerini korumaya yardımcı olmak için bu seçeneği belirleyin. Örneğin, bir uygulamanın diğer uygulamalarla iletişim kurma özelliklerini kısıtlayabilir veya kullanıcının şirket uygulamasına erişmek için PIN girmesini isteyebilirsiniz. Daha fazla bilgi için bkz.
  - [Uygulama koruma ilkeleri](app-protection-policies.md).
- **Uygulama seçmeli silme**: Seçili bir kullanıcının cihazından yalnızca şirket verilerini kaldırmak için bu seçeneği belirleyin. Daha fazla bilgi için bkz.
  - [Uygulama seçmeli silme](apps-selective-wipe.md).
- **iOS uygulama sağlama profilleri**: iOS uygulamaları, bir sağlama profili ve bir sertifika tarafından imzalanmış kod içerir. Sertifikanın süresi dolduğunda, uygulama artık çalıştırılamaz. Intune size süresi dolmak üzere olan uygulamaların bulunduğu cihazlara yeni sağlama profili ilkesini önceden atamak için araçlar verir. Daha fazla bilgi için bkz.
  - [iOS uygulama sağlama profilleri](app-provisioning-profile-ios.md).

Bu bölüm hakkında daha fazla bilgi için bkz. [Uygulama yönetme](app-management.md).

### <a name="monitor"></a>İzleme
- **Uygulama lisansları**: Uygulama mağazalarından toplu satın alınan uygulamaları görüntüleyin, atayın ve izleyin. Daha fazla bilgi için bkz.
  - [iOS Volume-Purchased Program (VPP) uygulamaları](vpp-apps-ios.md).
  - [İş İçin Microsoft Store’dan toplu satın alınan uygulamalar](windows-store-for-business.md).
- **Bulunan Uygulamalar**: Intune tarafından atanan veya bir cihaza yüklenen uygulamaları görüntüleyin. Daha fazla bilgi için bkz. [Intune bulunan uygulamalar](app-discovered-apps.md).
- **Uygulama Yükleme Durumu**: Oluşturduğunuz uygulama atamasının durumunu gösterir. Daha fazla bilgi için bkz. [Microsoft Intune ile uygulama bilgilerini ve atamalarını izleme](apps-monitor.md#device-and-user-status-graphs).
- **Uygulama koruma durumu**: Seçtiğiniz kullanıcı için uygulama koruma ilkesinin durumunu görüntüleyin.
- **Denetim günlükleri**: Tüm BT yöneticileri tarafından gerçekleştirilen Intune uygulamasıyla ilgili etkinlikleri görüntüleyin.

Bu bölüm hakkında daha fazla bilgi için bkz. [Uygulama izleme](apps-monitor.md).

### <a name="set-up"></a>Ayarlama
- **iOS VPP belirteçleri**: iOS Volume Purchase Program (VPP) lisanslarınızı uygulayın ve görüntüleyin. Daha fazla bilgi için bkz.
  - [iOS toplu satın alınan uygulamalar](vpp-apps-ios.md)
- **Windows Enterprise sertifikası**: Yönetilen Windows cihazlarınıza iş kolu uygulamalarını dağıtmak için kullanılan kod imzalama sertifikasını uygulayın veya durumunu görüntüleyin.
- **Windows Symantec sertifikası**: Windows 10 Mobile cihazlarına XAP ve WP8.x appx dosyalarını dağıtmak için gereken kod imzalama sertifikasını uygulayın veya durumunu görüntüleyin.
- **İş İçin Microsoft Mağazası**: İş İçin Microsoft Mağazası’na tümleştirmeyi kurun. Bundan sonra, satın alınan uygulamaları Intune’a eşitleyebilir, bunları atayabilir ve lisans kullanımınızı izleyebilirsiniz. Daha fazla bilgi için bkz.
  - [İş İçin Microsoft Store’dan toplu satın alınan uygulamalar](windows-store-for-business.md).
- **Windows dışarıdan yükleme anahtarları**: Uygulamayı Windows mağazasından yayımlamak ve indirmek yerine doğrudan cihazlara yüklemek için kullanılabilecek bir Windows dışarıdan yükleme anahtarı ekleyin. Daha fazla bilgi için bkz.
  - [Bir Windows uygulamasını dışarıdan yükleme](app-sideload-windows.md).
- **Şirket Portalı markası**: Şirket Portalı’nı özelleştirerek şirketinizin markasını ekleyin. Daha fazla bilgi için bkz.
  - [Şirket Portalı yapılandırması](company-portal-app.md).
- **Uygulama kategorileri**: Uygulama kategorisi adlarını ekleyin, sabitleyin ve silin.
- **Android iş profili**: Kuruluşunuz için onayladığınız uygulamaları onaylayın ve eşitleyin. Daha fazla bilgi için bkz.
  - [Android iş profili uygulamaları](apps-add-android-for-work.md).

### <a name="help-and-support"></a>Yardım ve destek
- **Yardım ve destek**: Sorun giderin, destek isteyin veya Intune durumunu görüntüleyin. Daha fazla bilgi için bkz.
  - [Sorunları giderme](help-desk-operators.md).

## <a name="next-steps"></a>Sonraki adımlar

- [Microsoft Intune’a uygulama ekleme](apps-add.md)
