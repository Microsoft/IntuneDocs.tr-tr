---
title: Microsoft Intune’da uygulama yönetimi nedir?
titleSuffix: ''
description: Microsoft Intune tarafından sağlanan platforma göre istemci uygulaması yönetim özellikleri hakkında bilgi edinin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/05/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 1975a2dc-3a14-4cb9-9afb-e2ba01a1c51b
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2c7378540d1ec9e19db57baae21c999c80b4d1d9
ms.sourcegitcommit: 25e4847ead0f56c269cfefe1e01c1b9106a28cf1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78856263"
---
# <a name="what-is-microsoft-intune-app-management"></a>Microsoft Intune uygulama yönetimi nedir?


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

BT yöneticisi olarak Microsoft Intune'u şirketinizin iş gücünün kullandığı istemci uygulamaları yönetmek için kullanabilirsiniz. Bu işlev, cihazları yönetmeye ve verileri korumaya ek niteliğindedir. Yöneticinin önceliklerinden biri, son kullanıcıların işlerini yapabilmeleri için gereken uygulamalara erişimleri olduğundan emin olmaktır. Bu amaca ulaşmak zor olabilir çünkü:
- Çok çeşitli cihaz platformları ve uygulama türleri vardır.
- Hem şirket cihazlarındaki hem de kullanıcıların kişisel cihazlarındaki uygulamaları yönetmeniz gerekebilir.
- Ağınızın ve verilerinizi güvenli kaldığından emin olmanız gerekir.

Buna ek olarak, Intune’a kaydolmamış cihazlarda uygulamaları atamak ve yönetmek isteyebilirsiniz.

## <a name="mobile-application-management-mam-basics"></a>Mobil uygulama yönetimi (MAM) temelleri

[Intune mobil uygulama yönetimi](app-lifecycle.md), kullanıcılarınız için mobil uygulamaları yayımlama, gönderme, yapılandırma, güvenlik altına alma, izleme ve güncelleştirme gibi eylemler gerçekleştirmenize olanak tanıyan Intune yönetim özellikleri paketini ifade eder.

MAM, kuruluşunuzun verilerini bir uygulama içinde yönetmenizi ve korumanızı sağlar. **Kayıt olmadan mam** (mam-we) ile, hassas veriler içeren iş veya okul ile ilgili bir uygulama, **kendi cihazını getir** (KCG) senaryolarında kişisel cihazlar dahil olmak üzere neredeyse her [cihazda](app-management.md#app-management-capabilities-by-platform)yönetilebilir. Microsoft Office uygulamaları gibi birçok üretkenlik uygulaması Intune MAM tarafından yönetilebilir. Genel kullanıma sunulan [Microsoft Intune korunan uygulamaların](apps-supported-intune-apps.md) resmi listesine bakın.

Intune MAM iki yapılandırmayı destekler:
- **Intune MDM + MAM**: BT yöneticileri, yalnızca Intune mobil cihaz yönetiminde (MDM) kayıtlı cihazlarda MAM ve uygulama koruma ilkelerini kullanarak uygulamaları yönetebilir. Uygulamaları MAM-WE kullanarak yönetmek için, müşterilerin https://portal.azure.com adresindeki Azure portalında Intune konsolunu kullanması gerekir.
- **Cihaz kaydı olmadan MAM**: Cihaz kaydı olmadan MAM ya da diğer adıyla MAM-WE, BT yöneticilerinin Intune MDM’de kayıtlı olmayan cihazlarda MAM ve uygulama koruma ilkelerini kullanarak uygulamaları yönetmesine olanak sağlar. Bu, uygulamaların üçüncü taraf EMM sağlayıcılarında kayıtlı cihazlarda Intune tarafından yönetilebileceği anlamına gelir. Uygulamaları MAM-WE kullanarak yönetmek için, müşterilerin https://portal.azure.com adresindeki Azure portalında Intune konsolunu kullanması gerekir. Ayrıca uygulamalar, üçüncü taraf Enterprise Mobility Management (EMM) sağlayıcıları ile kaydedilmiş veya hiçbir MDM ile kaydedilmemiş cihazlarda uygulamalar Intune ile yönetilebilir. KCG ve Microsoft 'un EMS hakkında daha fazla bilgi için, [Microsoft Enterprise Mobility + Security (EMS) ile KCG 'yi etkinleştirmek Için teknoloji kararları](../fundamentals/byod-technology-decisions.md)bölümüne bakın.

## <a name="app-management-capabilities-by-platform"></a>Platforma göre uygulama yönetimi özellikleri

Intune, ihtiyacınız olan uygulamaları çalıştırmak istediğiniz cihazlara almanıza yardımcı olacak çeşitli özellikler sunar. Aşağıdaki tablo, uygulama yönetimi özelliklerinin bir özetini sağlar.

|  | Android/Android Kurumsal | iOS/iPadOS | Mac OS | Windows 10 | WVPN profillerinidows Phone 8.1 |
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

<sup>1</sup> Windows 10 çalıştıran cihazlarda uygulamaları korumak için [Windows Bilgi Koruması](../protect/windows-information-protection-configure.md)’nu kullanmayı göz önüne alabilirsiniz.<br>
<sup>2</sup> Yalnızca Intune tarafından yönetilen cihazlar için geçerlidir.<br>
<sup>3</sup> Intune, Android Kurumsal cihazlarda Yönetilen Google Play mağazasında kullanılabilen uygulamaları destekler.<br>
<sup>4</sup> Intune, standart Android Kurumsal cihazlarda web bağlantısı biçiminde uygulama kısayolu yüklenmesi seçeneğini sunmaz. Ancak web bağlantısı desteği [çoklu uygulama için ayrılmış Android Kurumsal cihazlarında](../configuration/device-restrictions-android-for-work.md#dedicated-device-settings) desteklenir. 


## <a name="get-started"></a>Kullanmaya başlayın

Uygulamalarla ilgili birçok bilgiyi **uygulamalar** iş yükünde bulabilirsiniz ve aşağıdakileri yaparak erişebilirsiniz:

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
3. **Uygulamalar**' ı seçin.

    ![Uygulamalar iş yükü bölmesi](./media/app-management/apps-workload.png)

Uygulamalar iş yükü, genel uygulama bilgilerine ve işlevlerine erişim için bağlantılar sağlar. 

Uygulama iş yükü gezinti menüsünün en üst kısmında, yaygın olarak kullanılan uygulama ayrıntıları sağlanır:
- **Genel bakış**: kiracı adını, MDM yetkilisini, kiracı konumunu, hesap durumunu, uygulama yükleme durumunu ve uygulama koruma ilkesi durumunu görüntülemek için bu seçeneği belirleyin.
- **Tüm uygulamalar**: kullanılabilir tüm uygulamaların listesini göstermek için bu seçeneği belirleyin. Bu sayfadan başka uygulamalar ekleyebilirsiniz. Ayrıca, her bir uygulamanın durumunu ve her uygulamanın atanıp atanmadığını da görebilirsiniz. Daha fazla bilgi için bkz. [uygulama ekleme](apps-add.md) ve [uygulama atama](apps-deploy.md).
- **Uygulamaları izleme**
    - **Uygulama lisansları**: Uygulama mağazalarından toplu satın alınan uygulamaları görüntüleyin, atayın ve izleyin. Daha fazla bilgi için bkz. [iOS toplu satın alınan program (VPP) uygulamaları](vpp-apps-ios.md) ve [Microsoft Store iş toplu satın alınan uygulamalar için](windows-store-for-business.md).
    - **Bulunan uygulamalar**: Intune tarafından atanan veya bir cihaza yüklenen uygulamaları görüntüleyin. Daha fazla bilgi için bkz. [Intune bulunan uygulamalar](app-discovered-apps.md).
    - **Uygulama yüklemesi durumu**: oluşturduğunuz uygulama atamasının durumunu görüntüleyin. Daha fazla bilgi için bkz. [Microsoft Intune ile uygulama bilgilerini ve atamalarını izleme](apps-monitor.md#device-and-user-status-graphs).
    - **Uygulama koruma durumu**: Seçtiğiniz kullanıcı için uygulama koruma ilkesinin durumunu görüntüleyin.
- **Platforma göre**: kullanılabilir uygulamaları platforma göre görüntülemek için bu platformları seçin.
    - Windows
    - iOS
    - Mac OS
    - Android
- **İlke**:
    - **Uygulama koruma ilkeleri**: Ayarları uygulamayla ilişkilendirmek ve kullandığı şirket verilerini korumaya yardımcı olmak için bu seçeneği seçin. Örneğin, bir uygulamanın diğer uygulamalarla iletişim kurma özelliklerini kısıtlayabilir veya kullanıcının şirket uygulamasına erişmek için PIN girmesini isteyebilirsiniz. Daha fazla bilgi için bkz. [Uygulama koruma ilkeleri](app-protection-policies.md).
    - **Uygulama yapılandırma ilkeleri**: Kullanıcı bir uygulama çalıştırdığında gerekebilecek ayarları sağlamak için bu ayarı kullanın. Daha fazla bilgi için bkz. [uygulama yapılandırma ilkeleri](app-configuration-policies-use-ios.md), [iOS uygulama yapılandırma ilkeleri](app-configuration-policies-use-ios.md)ve [Android uygulama yapılandırma ilkeleri](app-configuration-policies-overview.md).
    - **iOS uygulama sağlama profilleri**: iOS uygulamaları, bir sağlama profili ve bir sertifika tarafından imzalanmış kod içerir. Sertifikanın süresi dolduğunda, uygulama artık çalıştırılamaz. Intune size süresi dolmak üzere olan uygulamaların bulunduğu cihazlara yeni sağlama profili ilkesini önceden atamak için araçlar verir. Daha fazla bilgi için bkz. [iOS uygulama sağlama profilleri](app-provisioning-profile-ios.md).
    - **S modu ek ilkeleri**: yönetilen S modundaki cihazlarınızda çalışacak ek uygulamalar yetkilendirmek için bu seçeneği belirleyin. Daha fazla bilgi için bkz. [S modu ek ilkeleri](~/apps/apps-win32-s-mode.md).
    - **İlke kümeleri**: Bu seçeneği, oluşturduğunuz uygulama, ilke ve diğer yönetim nesnelerinin atanabilir bir koleksiyonunu oluşturmak için seçin. Daha fazla bilgi için bkz. [ilke kümeleri](~/fundamentals/policy-sets.md).
- **Diğer**:   
    - **Uygulama seçmeli silme**: Seçili bir kullanıcının cihazından yalnızca şirket verilerini kaldırmak için bu seçeneği kullanın. Daha fazla bilgi için bkz. [uygulama seçmeli silme](apps-selective-wipe.md).
    - **Uygulama kategorileri**: Uygulama kategorisi adlarını ekleyin, sabitleyin ve silin.
    - **E-kitaplar**: bazı uygulama depoları, şirketinizde kullanmak istediğiniz bir uygulama veya kitap için birden fazla lisans satın almanıza olanak sağlar. Daha fazla bilgi için bkz. [Toplu satın alınan uygulama ve kitapları Microsoft Intune ile yönetme](~/apps/vpp-apps.md).
- **Yardım ve destek**: Sorun giderin, destek isteyin veya Intune durumunu görüntüleyin. Daha fazla bilgi için bkz. sorun [giderme](../fundamentals/help-desk-operators.md).

## <a name="additional-information"></a>Ek bilgiler
Konsolun içindeki aşağıdaki öğeler uygulamayla ilgili işlevsellik sağlar:
- **İş İçin Microsoft Mağazası**: İş İçin Microsoft Mağazası’na tümleştirmeyi kurun. Bundan sonra, satın alınan uygulamaları Intune’a eşitleyebilir, bunları atayabilir ve lisans kullanımınızı izleyebilirsiniz. Daha fazla bilgi için, bkz. [iş toplu satın alınan uygulamalar için Microsoft Store](windows-store-for-business.md).
- **Windows Enterprise sertifikası**: Yönetilen Windows cihazlarınıza iş kolu uygulamalarını dağıtmak için kullanılan kod imzalama sertifikasını uygulayın veya durumunu görüntüleyin.
- **Windows Symantec sertifikası**: Windows 10 Mobile cihazlarına XAP ve WP8.x appx dosyalarını dağıtmak için gereken kod imzalama sertifikasını uygulayın veya durumunu görüntüleyin.
- **Windows dışarıdan yükleme anahtarları**: Uygulamayı Windows mağazasından yayımlamak ve indirmek yerine doğrudan cihazlara yüklemek için kullanılabilecek bir Windows dışarıdan yükleme anahtarı ekleyin. Daha fazla bilgi için bkz. [bir Windows uygulamasını dışarıdan yükleme](app-sideload-windows.md).
- **Apple VPP belirteçleri**: IOS/ıpados toplu satın alma programı (VPP) lisanslarınızı uygulayın ve görüntüleyin. Daha fazla bilgi için bkz. [iOS/ıpados toplu satın alınan uygulamalar](vpp-apps-ios.md).
- **Yönetilen Google Play**: yönetilen Google Play, Google 'ın kurumsal uygulama mağazası ve Android Enterprise uygulamalarının tek kaynağıdır. Daha fazla bilgi için bkz. [Intune Ile Android Enterprise cihazlarına yönetilen Google Play uygulamaları ekleme](~/apps/apps-add-android-for-work.md).
- **Marka ve özelleştirme**: şirketinizin markalamasını sağlamak için şirket portalı özelleştirin. Daha fazla bilgi için bkz. [Şirket portalı Configuration](company-portal-app.md).

## <a name="next-steps"></a>Sonraki adımlar

- [Microsoft Intune’a uygulama ekleme](apps-add.md)
