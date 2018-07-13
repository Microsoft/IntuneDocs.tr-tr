---
title: Microsoft Intune’da uygulama yönetimi nedir?
titlesuffix: ''
description: Microsoft Intune ile uygulama yönetimi hakkındaki temel bilgileri öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1975a2dc-3a14-4cb9-9afb-e2ba01a1c51b
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5aa03cad0785e0d9b3d64df97a3ba6d344f0c7b5
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/07/2018
ms.locfileid: "37906116"
---
# <a name="what-is-microsoft-intune-app-management"></a>Microsoft Intune uygulama yönetimi nedir?


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

BT yöneticisi olarak, şirketinizin iş gücünün kullandığı mobil uygulamaları yönetmek için Microsoft Intune’u kullanabilirsiniz. Bu işlev, cihazları yönetmeye ve verileri korumaya ek niteliğindedir. Yöneticinin önceliklerinden biri, son kullanıcıların işlerini yapabilmeleri için gereken uygulamalara erişimleri olduğundan emin olmaktır. Bu amaca ulaşmak zor olabilir çünkü:
- Çok çeşitli cihaz platformları ve uygulama türleri vardır.
- Hem şirket cihazlarındaki hem de kullanıcıların kişisel cihazlarındaki uygulamaları yönetmeniz gerekebilir.
- Ağınızın ve verilerinizi güvenli kaldığından emin olmanız gerekir.

Buna ek olarak, Intune’a kaydolmamış cihazlarda uygulamaları atamak ve yönetmek isteyebilirsiniz.

Intune, ihtiyacınız olan uygulamaları çalıştırmak istediğiniz cihazlara almanıza yardımcı olacak çeşitli özellikler sunar. Aşağıdaki tablo, uygulama yönetimi özelliklerinin bir özetini göstermektedir: 

## <a name="app-management-capabilities-by-platform"></a>Platforma göre uygulama yönetimi özellikleri

||||||
|-|-|-|-|-|
| |Android|iOS|Windows Phone 8.1|Windows 10|
|Cihazlara ve kullanıcılara uygulamaları ekleme ve atama|Evet|Evet|Evet|Evet|
|Intune’a kayıtlı olmayan cihazlara uygulamaları atama|Evet|Evet|Hayır|Hayır|
|Uygulamaların başlangıç davranışını denetlemek için uygulama yapılandırma ilkelerini kullanma|Hayır|Evet|Hayır|Hayır|
|Süresi dolan uygulamaları yenilemek için mobil uygulama sağlama ilkeleri kullanma|Hayır|Evet|Hayır|Hayır|
|Uygulama koruma ilkeleriyle uygulamalardaki şirket verilerini koruma|Evet|Evet|Hayır|Hayır<sup>1</sup>|
|Yüklü uygulamadan yalnızca şirket verilerini kaldırma (uygulama seçmeli silme)|Evet|Evet|Evet|Evet|
|Uygulama atamalarını izleme|Evet|Evet|Evet|Evet|
|Uygulama mağazasından toplu satın alınan uygulamaları atama ve izleme|Hayır|Hayır|Hayır|Evet|
|Cihazlara uygulamaları zorunlu yükleme (gerekli)<sup>2</sup>|Evet|Evet|Evet|Evet|
|Şirket Portalı’ndan cihazlara isteğe bağlı yükleme (kullanılabilir yükleme)|Evet|Evet|Evet|Evet|
|Web’deki bir uygulamanın kısayolunu yükleme (web bağlantısı)|Evet|Evet|Evet|Evet|
|Şirket içi (iş kolu) uygulamalar|Evet|Evet|Hayır|Evet|
|Mağazadan uygulamalar|Evet|Evet|Evet|Evet|
|Uygulamaları güncelleştirme|Evet|Evet|Evet|Evet|

<sup>1</sup> Windows 10 çalıştıran cihazlarda uygulamaları korumak için [Windows Bilgi Koruması](windows-information-protection-configure.md)’nu kullanmayı göz önüne alabilirsiniz.

<sup>2</sup> Yalnızca Intune tarafından yönetilen cihazlar için geçerlidir.

## <a name="get-started"></a>Başlarken

Aşağıda gösterilen yolla erişilen **Mobil Uygulamalar** iş yükünde, uygulamayla ilgili bilgilerin çoğunu bulabilirsiniz:

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin.  
    Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Microsoft Intune** bölmesinde **Mobil uygulamalar**’ı seçin.

    ![“Mobil uygulamalar” iş yükü bölmesi](./media/apps-workload.png)

Sıradaki dört bölüm, **Mobil uygulamalar** bölmesindeki kullanılabilir seçenekleri açıklar.

### <a name="manage"></a>Bilgisayarlarda
- **Uygulamalar**: İş gücünüz tarafından kullanılan uygulamaları eklemek, görüntülemek, atamak ve izlemek için bu seçeneği belirleyin. Daha fazla bilgi için bkz.:
    - [Uygulama ekleme](apps-add.md).
    - [Uygulama atama](apps-deploy.md).
    - [Uygulama izleme](apps-monitor.md).
- **Uygulama yapılandırma ilkeleri**: Kullanıcı bir uygulama çalıştırdığında gerekebilecek ayarları sağlamak için bu ayarı kullanın. Daha fazla bilgi için bkz.:
    - [Intune için uygulama yapılandırma ilkeleri](app-configuration-policies-overview.md).
        - [iOS uygulama yapılandırma ilkeleri](app-configuration-policies-use-ios.md).
        - [Android uygulama yapılandırma ilkeleri](app-configuration-policies-use-android.md).
- **Uygulama koruma ilkeleri**: Ayarları uygulamayla ilişkilendirmek ve kullandığı şirket verilerini korumaya yardımcı olmak için bu seçeneği seçin. Örneğin, bir uygulamanın diğer uygulamalarla iletişim kurma özelliklerini kısıtlayabilir veya kullanıcının şirket uygulamasına erişmek için PIN girmesini isteyebilirsiniz. Daha fazla bilgi için bkz.:
    - [Uygulama koruma ilkeleri](app-protection-policies.md).
- **Uygulama seçmeli silme**: Seçili bir kullanıcının cihazından yalnızca şirket verilerini kaldırmak için bu seçeneği kullanın. Daha fazla bilgi için bkz.:
    - [Uygulama seçmeli silme](apps-selective-wipe.md).
- **iOS uygulama sağlama profilleri**: iOS uygulamaları, bir sağlama profili ve bir sertifika tarafından imzalanmış kod içerir. Sertifikanın süresi dolduğunda, uygulama artık çalıştırılamaz. Intune size süresi dolmak üzere olan uygulamaların bulunduğu cihazlara yeni sağlama profili ilkesini önceden atamak için araçlar verir. Daha fazla bilgi için bkz.:
    - [iOS uygulama sağlama profilleri](app-provisioning-profile-ios.md).

Bu bölüm hakkında daha fazla bilgi için bkz. [Uygulama yönetme](app-management.md).

### <a name="monitor"></a>İzle
- **Uygulama lisansları**: Uygulama mağazalarından toplu satın alınan uygulamaları görüntüleyin, atayın ve izleyin. Daha fazla bilgi için bkz.:
    - [iOS Volume-Purchased Program (VPP) uygulamaları](vpp-apps-ios.md).
    - [İş İçin Microsoft Store’dan toplu satın alınan uygulamalar](windows-store-for-business.md).
- **Bulunan Uygulamalar**: Intune tarafından atanan ve bir cihaza yüklenen tüm uygulamaları görüntüleyin.
- **Uygulama Yükleme Durumu** - Oluşturduğunuz uygulama atamasının durumunu gösterir.
- **Uygulama koruma durumu**: Seçtiğiniz kullanıcı için uygulama koruma ilkesinin durumunu görüntüleyin.
- **Denetim günlükleri**: Tüm BT yöneticileri tarafından gerçekleştirilen Intune uygulamasıyla ilgili etkinlikleri görüntüleyin.

Bu bölüm hakkında daha fazla bilgi için bkz. [Uygulama izleme](apps-monitor.md).

### <a name="set-up"></a>Ayarlama
- **iOS VPP belirteçleri**: iOS Volume Purchase Program (VPP) lisanslarınızı uygulayın ve görüntüleyin. Daha fazla bilgi için bkz.:
    - [Toplu satın alınan iOS uygulamaları](vpp-apps-ios.md)
- **Windows Enterprise sertifikası**: Yönetilen Windows cihazlarınıza iş kolu uygulamalarını dağıtmak için kullanılan kod imzalama sertifikasını uygulayın veya durumunu görüntüleyin.
- **Windows Symantec sertifikası**: Windows 10 Mobile cihazlarına XAP ve WP8.x appx dosyalarını dağıtmak için gereken kod imzalama sertifikasını uygulayın veya durumunu görüntüleyin.
- **İş İçin Microsoft Mağazası**: İş İçin Microsoft Mağazası’na tümleştirmeyi kurun. Bundan sonra, satın alınan uygulamaları Intune’a eşitleyebilir, bunları atayabilir ve lisans kullanımınızı izleyebilirsiniz. Daha fazla bilgi için bkz.:
    - [İş İçin Microsoft Store’dan toplu satın alınan uygulamalar](windows-store-for-business.md).
- **Windows dışarıdan yükleme anahtarları**: Uygulamayı Windows mağazasından yayımlamak ve indirmek yerine doğrudan cihazlara yüklemek için kullanılabilecek bir Windows dışarıdan yükleme anahtarı ekleyin. Daha fazla bilgi için bkz.:
    - [Bir Windows uygulamasını dışarıdan yükleme](app-sideload-windows.md).
- **Şirket Portalı markası**: Şirket Portalı’nı özelleştirerek şirketinizin markasını ekleyin. Daha fazla bilgi için bkz.:
    - [Şirket Portalı yapılandırması](company-portal-app.md).
- **Uygulama kategorileri**: Uygulama kategorisi adlarını ekleyin, sabitleyin ve silin.
- **Android iş profili**: Kuruluşunuz için onayladığınız uygulamaları onaylayın ve eşitleyin. Daha fazla bilgi için bkz.:
    - [Android iş profili uygulamaları](apps-add-android-for-work.md).

### <a name="help-and-support"></a>Yardım ve destek
- **Yardım ve destek**: Sorun giderin, destek isteyin veya Intune durumunu görüntüleyin. Daha fazla bilgi için bkz.:
    - [Sorunları giderme](help-desk-operators.md).

## <a name="next-steps"></a>Sonraki adımlar

- [Microsoft Intune’a uygulama ekleme](apps-add.md)
