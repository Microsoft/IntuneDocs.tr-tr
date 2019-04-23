---
title: Microsoft Intune - Azure'da Android kuruluş cihazlarının OEMConfig kullanın | Microsoft Docs
description: Yönetme ve kullanma OEMConfig ile Android Enterprise çalıştıran cihazlar için Microsoft Intune kullanın. Genel bir bakış da dahil olmak üzere tüm adımlara bakın, önkoşullara bakın, Intune yapılandırma profili oluşturma ve desteklenen OEMConfig uygulamaların listesini görmek.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/17/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: ''
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 022bbcf98a5e00888f33e22941515ca03c5f6995
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2019
ms.locfileid: "59901830"
---
# <a name="use-and-manage-android-enterprise-devices-with-oemconfig-in-microsoft-intune"></a>Kullanımı ve Microsoft Intune OEMConfig ile Android Kurumsal cihaz Yönetimi

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Microsoft Intune OEMConfig eklemek, oluşturmak ve Android kuruluş cihazlarının için OEM özgü ayarları özelleştirmek için kullanabilirsiniz. OEMConfig genellikle, Intune'da yerleşik olarak bulunmaz ayarlarını yapılandırmak için kullanılır. Farklı OEM'ler farklı ayarlar içerir. Bu nedenle kullanılabilir ayarlar ne OEM OEMConfig uygulamalarının içerir üzerinde bağlıdır.

Bu özellik şu platformlarda geçerlidir:  

- Android Kurumsal

Bu makalede OEMConfig, ne işe yarar, ıntune'da desteklenen OEMConfig uygulamaları listeler önkoşulları listeler ve bir yapılandırma profili oluşturma işlemi gösterilmektedir.

## <a name="overview"></a>Genel Bakış

OEMConfig ilkeleri, cihaz yapılandırma İlkesi çok benzer bir özel tür [uygulama yapılandırma İlkesi](app-configuration-policies-overview.md). OEMConfig tarafından tanımlanan bir standart olan [AppConfig topluluk](https://www.appconfig.org/android-oemconfig/) (başka bir web sitesini açar) sağlayan OEM'ler (orijinal donanım üreticileri) ve EMMs (Kurumsal mobilite Yönetimi) oluşturun ve OEM özgü özellikleri desteklemek bir standartlaştırılmış bir yol. Tarihsel olarak, OEM tarafından sunulan sonra Intune gibi bir EMMs OEM özgü özellikleri için destek el ile oluşturun. Bu yaklaşım, yinelenen çabaları ve yavaş benimseme için yol açar.

OEMConfig ile OEM OEM özgü özelliklerini tanımlayan bir şema oluşturur. OEM şema uygulamaya ekler ve ardından bu uygulamayı Google Play'den geçirir. EMM uygulamadan şemayı okur ve şema EMM yönetici Konsolu'ndaki kullanıma sunar. Konsolu, şemada ayarlarını yapılandırmak Intune yöneticileri sağlar.

OEMConfig uygulama bir cihazda yüklü olduğunda, EMM Yönetici konsolunda yapılandırılan ayarlar cihazı yönetmek için kullanabilirsiniz. Cihaz ayarları EMM tarafından oluşturulan bir MDM Aracısı yerine OEMConfig uygulama tarafından yürütülür.

OEM ekler ve yönetim özelliklerini geliştirir, OEM Google Play uygulamada de güncelleştirir. Yönetici olarak, bu yeni özellikler ve güncelleştirmeleri (düzeltmeler de dahil) bu güncelleştirmeler dahil etmek için EMMs beklemeden sahip olursunuz.

> [!TIP]
> Bu gibi durumlarda, OEMConfig yalnızca bu özelliği destekleyen ve karşılık gelen bir OEMConfig uygulamasına sahip cihazlarla kullanabilirsiniz. OEM için belirli ayrıntıları inceleyin.

## <a name="before-you-begin"></a>Başlamadan önce

OEMConfig kullanırken, aşağıdaki bilgileri unutmayın:

- Bunu yapılandırmak için Intune OEMConfig uygulamanın şema kullanıma sunar. Intune, doğrulama veya uygulama tarafından sağlanan şema değiştirme değil. Bu nedenle şema yanlış, veya yanlış bir veri varsa bu veriler yine de cihazlara gönderilir. Şemada kaynaklanan bir sorun bulursanız, kılavuzu için OEM ile iletişim kurun.
- Intune, etkilemek veya uygulama şemasının içeriği denetim değil. Örneğin, Intune, dizeler, dil, izin verilen eylemleri ve benzeri herhangi bir denetime sahip değil. Ayrıntılar ve OEMConfig cihazlarını yönetmek için en iyi yöntemler için OEM başvurarak öneririz.
- Herhangi bir zamanda OEM'ler kendi desteklenen özellikler ve şemaları güncelleştirebilir ve yeni bir uygulama Google Play'e yükle. Intune, Google play'den OEMConfig uygulamasının en son sürümü her zaman eşitlenir. Intune, şema veya uygulamanın eski sürümleri korumak değil. Sürüm çakışmaları çalıştırırsanız, daha fazla bilgi için OEM başvurarak öneririz.
- Bir cihaz için yalnızca bir OEMConfig profili atamanız gerekir. Aynı cihaza birden çok profil atanmışsa, tutarsız davranışa görebilirsiniz. OEMConfig modeli, cihaz başına tek bir ilke yalnızca destekler.

## <a name="prerequisites"></a>Önkoşullar

Cihazlarınızda OEMConfig kullanmak için aşağıdaki gereksinimlere sahip olduğunuzdan emin olun:

- Android Kurumsal cihaz Intune'a kayıtlı.
- OEMConfig uygulama OEM tarafından oluşturulan ve Google Play'e yüklendi. Google Play'den değilse, daha fazla bilgi için OEM ile iletişim kurun.
- Intune yönetici için rol tabanlı erişim denetimi (RBAC) izinlerine sahip **mobil uygulamalar** ve **DeviceConfigurations**. OEMConfig profilleri olun nedeni yönetilen uygulama yapılandırmalarını cihaz yapılandırmalarını yönetmek için kullanabilirsiniz.

## <a name="prepare-the-oemconfig-app"></a>OEMConfig uygulamayı hazırlama

Doğru OEMConfig uygulamayı Intune'a eklenmiş olan ve uygulamayı cihazda yüklü olan OEMConfig cihaz desteklediğinden emin olun. Bu bilgi için OEM başvurun.

> [!TIP] 
> OEMConfig uygulamalar için OEM özgüdür. Örneğin, bir Sony OEMConfig uygulaması Zebra teknolojileri cihazda yüklü hiçbir şey yapmıyor.

1. OEMConfig uygulamayı yönetilen Google Play Store ' edinin. [Yönetilen Google Play uygulamaları Android kuruluş cihazlarının ekleme](apps-add-android-for-work.md) adımları listelenir.
2. OEM'leri cihazları önceden yüklenmiş OEMConfig uygulamayla birlikte. Uygulamayı önceden değil, ıntune'u [ekleme ve cihazlara uygulama dağıtma](apps-deploy.md).

## <a name="create-an-oemconfig-profile"></a>OEMConfig profili oluşturma

1. İçinde [Azure portalında](https://portal.azure.com)seçin **tüm hizmetleri** > Filtre **Intune** > seçin **Intune**.
2. **Cihaz Yapılandırması** > **Profiller** > **Profil oluştur**’u seçin.
3. Aşağıdaki özellikleri girin:

    - **Ad**: Yeni profil için açıklayıcı bir ad girin.
    - **Açıklama**: Profil için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
    - **Platform**: Seçin **Android Kurumsal**.
    - **Profil türü**: Seçin **OEMConfig**.

4. Seçin **ilişkili uygulama**, daha önce eklediğiniz mevcut bir OEMConfig uygulamayı seçin. İlkeyi atama cihazlar için doğru OEMConfig uygulama'ı seçtiğinizden emin olun.

    Listelenen tüm uygulamalar görmüyorsanız, yönetilen Google Play ayarlayın ve yönetilen Google Play Mağazası'ndan uygulama alın. [Yönetilen Google Play uygulamaları Android kuruluş cihazlarının ekleme](apps-add-android-for-work.md) adımları listelenir.

    > [!IMPORTANT]
    > OEMConfig uygulama eklendi ve Google Play'e eşitlenmiş halde olarak listelenmemiş bir **ilişkili uygulama**, Intune uygulama için dahili başvurmanız gerekebilir. Bkz: [yeni uygulama ekleme](#supported-oemconfig-apps) (Bu makaledeki).

5. Seçin **yapılandırma** sekmesi.

    Katıştırılmış uygulamada yapılandırma şeması için bir şablon ile JSON Düzenleyicisi açılır. Düzenleyici'de şablonun farklı yapılandırma ayarları için değerleri özelleştirin. 
    
    OEMConfig şemaları, büyük ve karmaşık olabilir. bu yana kullanabileceğiniz **JSON şablonu indir** şablon dosyası olarak almak için düğme. Bu şablon dosyasını tercih ettiğiniz bir düzenleyicide yapılandırın ve ardından Intune yönetim konsolunda oturum içeriğini kopyalayın.

6. Seçin **Tamam** > **Ekle** yaptığınız değişiklikleri kaydedin. İlke oluşturulur ve listede gösterilen.

Mutlaka [profili atama](device-profile-assign.md) ve [atamanın durumunu izlemenize](device-profile-monitor.md).
    
 > [!NOTE]
 > Her cihaz için bir profil atayın. OEMConfig modeli, cihaz başına bir ilke yalnızca destekler.

Cihaz denetlediğinde yapılandırma güncelleştirmelerini, yapılandırdığınız OEM özgü ayarları OEMConfig uygulamaya uygulanır.

## <a name="supported-oemconfig-apps"></a>Desteklenen OEMConfig uygulamaları

Standart uygulamalar için karşılaştırıldığında, daha karmaşık şemaları desteklemek için Google tarafından verilen yönetilen yapılandırmalar ayrıcalıkları OEMConfig uygulamaları genişletin. Intune şu anda aşağıdaki OEMConfig uygulamaları destekler:

-----------------

| OEM | Paket Kimliği |
| --- | --- |
| Samsung | com.samsung.android.knox.kpu |

-----------------

Yeni bir OEMConfig uygulama konaklarınızda istemek için e-posta `IntuneOEMConfig@microsoft.com`.

> [!NOTE]
> OEMConfig profilleriyle yapılandırılabilmesi konaklarınızda Intune tarafından OEMConfig uygulamaları gerekir.

## <a name="next-steps"></a>Sonraki adımlar

- [Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).
