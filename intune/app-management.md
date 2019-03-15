---
title: Microsoft Intune’da uygulama yönetimi nedir?
titlesuffix: ''
description: İstemci uygulama yönetim özelliklerini Intune için platforma göre öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/19/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 1975a2dc-3a14-4cb9-9afb-e2ba01a1c51b
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6d9b10c8bf06e0e0a5aa481afebb01c980fc20a9
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57394508"
---
# <a name="what-is-microsoft-intune-app-management"></a>Microsoft Intune uygulama yönetimi nedir?


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

BT yöneticisi olarak Microsoft Intune'u şirketinizin iş gücünün kullandığı istemci uygulamaları yönetmek için kullanabilirsiniz. Bu işlev, cihazları yönetmeye ve verileri korumaya ek niteliğindedir. Yöneticinin önceliklerinden biri, son kullanıcıların işlerini yapabilmeleri için gereken uygulamalara erişimleri olduğundan emin olmaktır. Bu amaca ulaşmak zor olabilir çünkü:
- Çok çeşitli cihaz platformları ve uygulama türleri vardır.
- Hem şirket cihazlarındaki hem de kullanıcıların kişisel cihazlarındaki uygulamaları yönetmeniz gerekebilir.
- Ağınızın ve verilerinizi güvenli kaldığından emin olmanız gerekir.

Buna ek olarak, Intune’a kaydolmamış cihazlarda uygulamaları atamak ve yönetmek isteyebilirsiniz.

Intune, ihtiyacınız olan uygulamaları çalıştırmak istediğiniz cihazlara almanıza yardımcı olacak çeşitli özellikler sunar. Aşağıdaki tablo, uygulama yönetimi özelliklerinin bir özetini göstermektedir: 

## <a name="app-management-capabilities-by-platform"></a>Platforma göre uygulama yönetimi özellikleri

|  | Android | iOS | Mac OS | Windows 10 | Windows Phone 8.1 |
|-------------------------------------------------------------------------------------|---------|-----|-------|------------|-------------------|
| Cihazlara ve kullanıcılara uygulamaları ekleme ve atama | Evet | Evet | Evet | Evet | Evet |
| Intune’a kayıtlı olmayan cihazlara uygulamaları atama | Evet | Evet | Hayır | Hayır | Hayır |
| Uygulamaların başlangıç davranışını denetlemek için uygulama yapılandırma ilkelerini kullanma | Hayır | Evet | Hayır | Hayır | Hayır |
| Süresi dolan uygulamaları yenilemek için mobil uygulama sağlama ilkelerini kullanma | Hayır | Evet | Hayır | Hayır | Hayır |
| Uygulama koruma ilkeleriyle uygulamalardaki şirket verilerini koruma | Evet | Evet | Hayır | Hayır1 | Hayır |
| Yüklü uygulamadan yalnızca şirket verilerini kaldırma (uygulama seçmeli silme) | Evet | Evet | Hayır | Evet | Evet |
| Uygulama atamalarını izleme | Evet | Evet | Evet | Evet | Evet |
| Uygulama mağazasından toplu satın alınan uygulamaları atama ve izleme | Hayır | Hayır | Hayır | Evet | Hayır |
| Cihazlara uygulamaları zorunlu yükleme (gerekli)2 | Evet | Evet | Evet | Evet | Evet |
| Şirket Portalı’ndan cihazlara isteğe bağlı yükleme (kullanılabilir yükleme) | Evet | Evet | Evet | Evet | Evet |
| Web’deki bir uygulamanın kısayolunu yükleme (web bağlantısı) | Evet | Evet | Evet | Evet | Evet |
| Şirket içi (iş kolu) uygulamaları | Evet | Evet | Evet | Evet | Hayır |
| Mağazadan uygulamalar | Evet | Evet | Hayır | Evet | Evet |
| Uygulamaları güncelleştirme | Evet | Evet | Hayır | Evet | Evet |

<sup>1</sup> Windows 10 çalıştıran cihazlarda uygulamaları korumak için [Windows Bilgi Koruması](windows-information-protection-configure.md)’nu kullanmayı göz önüne alabilirsiniz.

<sup>2</sup> Yalnızca Intune tarafından yönetilen cihazlar için geçerlidir.

## <a name="get-started"></a>başlarken

Aşağıda gösterilen yolla erişilen **İstemci uygulamaları** iş yükünde, uygulamayla ilgili bilgilerin çoğunu bulabilirsiniz:

1. [Azure Portal](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin.  
    Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Microsoft Intune** bölmesinde **İstemci uygulamaları**’nı seçin.

    !["İstemci uygulamaları" iş yükü bölmesi](./media/apps-workload.png)

Sıradaki dört bölüm, **İstemci uygulamaları** bölmesindeki kullanılabilir seçenekleri açıklar.

### <a name="manage"></a>Bilgisayarlarda
- **Uygulamaları**: Eklemek, görüntülemek, atamak ve gücünüz tarafından kullanılan uygulamaları izlemek için bu seçeneği belirleyin. Daha fazla bilgi için bkz.
    - [Uygulama ekleme](apps-add.md).
    - [Uygulama atama](apps-deploy.md).
    - [Uygulama izleme](apps-monitor.md).
- **Uygulama yapılandırma ilkeleri**: Bir kullanıcı bir uygulama çalıştırdığında gerekebilecek ayarları sağlamak için bu seçeneği belirleyin. Daha fazla bilgi için bkz.
    - [Intune için uygulama yapılandırma ilkeleri](app-configuration-policies-overview.md).
        - [iOS uygulama yapılandırma ilkeleri](app-configuration-policies-use-ios.md).
        - [Android uygulama yapılandırma ilkeleri](app-configuration-policies-use-android.md).
- **Uygulama koruma ilkeleri**: Ayarları bir uygulamayla ilişkilendirmek için bu seçeneği seçin ve uygulamanın kullandığı şirket verilerini korumaya yardımcı olur. Örneğin, bir uygulamanın diğer uygulamalarla iletişim kurma özelliklerini kısıtlayabilir veya kullanıcının şirket uygulamasına erişmek için PIN girmesini isteyebilirsiniz. Daha fazla bilgi için bkz.
    - [Uygulama koruma ilkeleri](app-protection-policies.md).
- **Uygulama seçmeli silme**: Seçilen kullanıcının cihazından yalnızca şirket verilerini kaldırmak için bu seçeneği belirleyin. Daha fazla bilgi için bkz.
    - [Uygulama seçmeli silme](apps-selective-wipe.md).
- **iOS uygulama sağlama profilleri**: iOS uygulamaları, bir sağlama profili ve bir sertifika tarafından imzalanmış kod içerir. Sertifikanın süresi dolduğunda, uygulama artık çalıştırılamaz. Intune size süresi dolmak üzere olan uygulamaların bulunduğu cihazlara yeni sağlama profili ilkesini önceden atamak için araçlar verir. Daha fazla bilgi için bkz.
    - [iOS uygulama sağlama profilleri](app-provisioning-profile-ios.md).

Bu bölüm hakkında daha fazla bilgi için bkz. [Uygulama yönetme](app-management.md).

### <a name="monitor"></a>İzleme
- **Uygulama lisansları**: Görüntüleyin, atayın ve uygulama mağazalarından toplu satın alınan uygulamaları izleyin. Daha fazla bilgi için bkz.
    - [iOS Volume-Purchased Program (VPP) uygulamaları](vpp-apps-ios.md).
    - [İş İçin Microsoft Store’dan toplu satın alınan uygulamalar](windows-store-for-business.md).
- **Bulunan uygulamalar**: Intune tarafından atanan veya bir cihazda yüklü uygulamaları görüntüleme. Daha fazla bilgi için bkz. [Microsoft Intune ile cihaz ayrıntılarını görüntüleme](device-inventory.md).
- **Uygulama yükleme durumu**: Oluşturduğunuz uygulama atamasının durumunu görüntüleyin. Daha fazla bilgi için bkz. [Microsoft Intune ile uygulama bilgilerini ve atamalarını izleme](apps-monitor.md#device-and-user-status-graphs).
- **Uygulama koruma durumu**: Seçtiğiniz kullanıcı için uygulama koruma ilkesinin durumunu görüntüleyin.
- **Denetim günlükleri**: Tüm BT yöneticileri, Intune uygulamasıyla ilgili etkinlikleri görüntüleyin.

Bu bölüm hakkında daha fazla bilgi için bkz. [Uygulama izleme](apps-monitor.md).

### <a name="set-up"></a>Ayarlama
- **iOS VPP belirteçleri**: Uygulayın ve iOS Volume Purchase Program (VPP) lisanslarınızı görüntüleyin. Daha fazla bilgi için bkz.
    - [iOS toplu satın alınan uygulamalar](vpp-apps-ios.md)
- **Windows enterprise sertifikası**: Uygulama veya yönetilen Windows cihazlarınıza satır iş kolu uygulamalarını dağıtmak için kullanılan kod imzalama sertifikası durumunu görüntüleyin.
- **Windows Symantec sertifikası**: Uygulama veya Windows 10 Mobile cihazlarına XAP ve WP8.x appx dosyalarını dağıtmak için gerekli olan bir Symantec kod imzalama sertifikası durumunu görüntüleyin.
- **İş için Microsoft Store**: İş için Microsoft Store tümleştirmeyi kurun. Bundan sonra, satın alınan uygulamaları Intune’a eşitleyebilir, bunları atayabilir ve lisans kullanımınızı izleyebilirsiniz. Daha fazla bilgi için bkz.
    - [İş İçin Microsoft Store’dan toplu satın alınan uygulamalar](windows-store-for-business.md).
- **Windows dışarıdan yükleme anahtarları**: Cihazlar yerine, yayımlamak ve Windows Mağazası'ndan uygulama indirmek için doğrudan bir uygulama yüklemek için kullanılan bir Windows dışarıdan yükleme anahtarı ekleyin. Daha fazla bilgi için bkz.
    - [Bir Windows uygulamasını dışarıdan yükleme](app-sideload-windows.md).
- **Şirket portalı markası**: Şirket portalı, şirketinizin markasını özelleştirin. Daha fazla bilgi için bkz.
    - [Şirket Portalı yapılandırması](company-portal-app.md).
- **Uygulama kategorileri**: Ekleme, PIN ve uygulama kategorisi adlarını silin.
- **Android iş profili**: Onayla ve kuruluşunuz için onayladığınız uygulamaları eşitleyin. Daha fazla bilgi için bkz.
    - [Android iş profili uygulamaları](apps-add-android-for-work.md).

### <a name="help-and-support"></a>Yardım ve destek
- **Yardım ve Destek**: Sorun giderme, destek isteyin veya Intune durumunu görüntüleyin. Daha fazla bilgi için bkz.
    - [Sorunları giderme](help-desk-operators.md).

## <a name="next-steps"></a>Sonraki adımlar

- [Microsoft Intune’a uygulama ekleme](apps-add.md)
