---
title: Uygulama koruma ilkeleri ve çalışma profilleri Microsoft Intune - Azure | Microsoft Docs
description: Farklılıklar ve Artıları ve eksileri uygulama koruma ilkelerini kullanmak veya kişisel veya KCG Android Kurumsal cihaz profilleri Intune iş karar verirken bakın. Farklılıklar ve özellikleri Al kaydı olmadan uygulama koruma ilkeleriyle Karşılaştır (APP-BİZ) ve Android iş profilleri Kurumsal.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/13/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 6fd12432d07d1486e0943f88c0cf8b4536e651bc
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57236509"
---
# <a name="application-protection-policies-and-work-profiles-on-android-enterprise-devices-in-intune"></a>Android Kurumsal cihazlarda ıntune uygulama koruma ilkeleri ve çalışma profilleri

Birçok kuruluşta, kaynaklar ve farklı cihazlardaki verileri korumanın Yöneticiler tanımlamaları gerekmektedir. Bir challenge, kişisel Android kuruluş cihazlarının ile olarak da bilinen-kendi-cihazını getir (KCG) kullanıcılar için kaynaklar korumaktır. Microsoft Intune-kendi-cihazını Getir için (KCG) iki Android dağıtımı senaryoları destekler:

- Kayıt olmadan uygulama koruma ilkelerini (APP-BİZ)
- Android kurumsal iş profilleri

APP-EDİYORUZ ve Android iş profili dağıtım senaryoları KCG ortamlar için önemli aşağıdaki temel özellikleri şunlardır:

1. **Koruma ve kuruluş tarafından yönetilen veri ayrımı**: Her iki çözüm de, veri kaybı önleme (DLP) denetimleri kuruluş tarafından yönetilen veri çubuğunda zorlayarak kuruluş verileri koruyun. Bu korumalar gibi bir kişisel uygulama veya hesap paylaşımı yanlışlıkla bir son kullanıcının korunan verilerin yanlışlıkla sızıntılarını önleme. Ayrıca veriye erişen bir cihaz sağlıklı ve güvenliği aşılan değil olduğundan emin olmak için sağladıkları.

2. **Son kullanıcı gizlilik**: APP-BİZ Android kurumsal iş profilleri ayrı cihazda son kullanıcılara içerik ve veri yönetilen mobil cihaz yönetimine (MDM) yönetici. Her iki senaryoda, BT yöneticileri, kuruluş tarafından yönetilen uygulamaların veya kimlikleri yalnızca PIN kimlik doğrulama gibi ilkelerini zorunlu tutun. BT yöneticileri, okuma, erişim veya son kullanıcılar tarafından sahip olunan veya denetimli verileri silme belirleyemiyoruz.

Uygulama olup olmadığınıza-BİZ veya Kurumsal Android iş profilleri için gereksinimler ve iş KCG dağıtımınızın bağımlı gerekiyor. Bu makalenin amacı, karar vermenize yardımcı olacak rehberlik sağlamaktır.

## <a name="about-intune-app-protection-policies"></a>Intune uygulama koruma ilkeleri hakkında

Veri koruma ilkelerinin hedeflenen kullanıcılar için Intune uygulama koruma ilkelerini (APP) var. Veri kaybı korumasını uygulama düzeyinde ilkeler geçerlidir. Intune uygulama, uygulama geliştiricilerinin oluşturdukları uygulamaları uygulama özellikleri etkinleştirme gerektirir.

Tek tek Android uygulamaları için uygulama birkaç yöntemle etkinleştirilir:

1. **Microsoft birinci taraf uygulamalara yerel olarak tümleşik**: Android ve diğer Microsoft uygulamalarında seçimi için Microsoft Office uygulamaları, Intune uygulama yerleşik ile gelir. Bu Office uygulamaları, Word, OneDrive, Outlook ve benzeri gibi ilkeleri uygulamak için daha fazla özelleştirme gerekmez. Bu uygulamalar Google Play Store doğrudan son kullanıcılar tarafından yüklenebilir.

2. **Intune SDK'sı kullanan geliştiriciler tarafından uygulama derleme tümleşik**: Uygulama geliştiricileri kaynak kodlarını Intune SDK'sı tümleştirebilir ve uygulamalarını Intune uygulama ilke özellikleri destekleyecek şekilde yeniden derleyin.

3. **Intune uygulama sarmalama aracı kullanılarak Sarmalanan**: Bazı müşteriler Android uygulamaları derleyin (. APK dosyası) kaynak koduna erişmeden. Kaynak kodu, geliştirici, Intune SDK'sı ile tümleştiremezsiniz. SDK, bunlar uygulama ilkeleri için uygulama etkinleştirilemiyor. Geliştirici, değiştirme veya uygulama ilkelerini destekleyen uygulamanın recode gerekir.

    Yardımcı olmak için Intune içeren **uygulama sarmalama aracı** aracı var olan Android uygulamaları (Apk'lar) ve uygulama ilkelerini tanıyan uygulama oluşturur.

    Bu araç hakkında daha fazla bilgi için bkz. [satır iş kolu uygulamalarını uygulama koruma ilkeleri için repare](apps-prepare-mobile-application-management.md).

Uygulamayla etkinleştirilmiş uygulamaların bir listesini görmek için bkz: [zengin bir mobil uygulama koruma ilkeleri ile yönetilen uygulamalar](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

## <a name="deployment-scenarios"></a>Dağıtım senaryoları

Bu bölümde uygulama önemli özelliklerini açıklar-EDİYORUZ ve dağıtım senaryoları profil Android kurumsal iş.

#### <a name="app-we"></a>APP-EDİYORUZ

Bir APP-BİZ (kaydı olmadan uygulama koruma ilkeleri) dağıtım olmayan cihazlara uygulamaları üzerinde ilkeleri tanımlar. Bu senaryoda, cihazlar genellikle kayıtlı veya Intune gibi bir MDM yetkilisi tarafından yönetiliyor. Uygulama ve kuruluş verilerine erişimi korumak için Yöneticiler uygulama yönetilebilir uygulamaları kullanma ve veri koruma ilkeleri bu uygulamalara uygulamanız.

Bu özellik şu platformlarda geçerlidir:

- Android 4.4 ve üzeri

> [!TIP]
> Daha fazla bilgi için [uygulama koruma ilkeleri nelerdir?](app-protection-policy.md).

APP-cihazlarından Kurumsal küçük ayak izine istediğiniz ve MDM içinde kaydetmek istemeyeceğiniz son kullanıcılar BİZ senaryoları içindir Yönetici olarak, verilerinizi korumak yine. Bu cihaz yönetilmiyor. Bu nedenle genel MDM görevleri ve Wi-Fi, VPN cihaz ve sertifika yönetimi gibi özellikler bu dağıtım senaryosu bir parçası değildir.

#### <a name="android-enterprise-work-profiles"></a>Android kurumsal iş profilleri

Çekirdek Android kurumsal dağıtım senaryosu iş profilleri olan ve tek senaryo KCG hedeflenen kullanım örnekleri. İş profili, Intune tarafından yönetilen Android işletim sistemi düzeyinde oluşturulan ayrı bir bölümdür.

Bu özellik şu platformlarda geçerlidir:

- Google Mobile Services Android 5.0 ve üstü cihazları

Bir iş profili aşağıdaki özellikleri içerir:

- **Geleneksel MDM işlevselliğini**: Tüm Android Kurumsal senaryoda anahtarı MDM özellikleri, uygulama yaşam döngüsü yönetimi kullanılarak yönetilen Google Play gibi kullanılabilir. Yönetilen Google Play, kullanıcı müdahalesi olmadan uygulamaları yüklemek ve güncelleştirmek için sağlam bir deneyim sağlar. BT kuruluş uygulamaları için uygulama yapılandırma ayarları da gönderebilirsiniz. Ayrıca, bilinmeyen kaynaklardan yüklemeleri izin vermek, son kullanıcılar ayrıca gerektirmez. Wi-Fi/VPN yapılandırma ve ayarlama cihaz geçiş kodlarını sertifikaları dağıtma gibi diğer genel MDM etkinlikleri, iş profilleri ile kullanılabilir.

- **İş profili sınırının üzerinde DLP**: İster APP-WE, BT veri koruma ilkeleri zorunlu kılabilir. Bir iş profiliyle iş profili düzeyinde uygulama düzeyinde değil DLP ilkeleri uygulanır. Örneğin, kopyala/yapıştır koruma, bir uygulama için geçerli veya iş profili tarafından zorlanan uygulama ayarları olarak zorunlu kılınmıştır. İş profiline uygulama dağıtıldığında, Yöneticiler bu ilke, uygulama düzeyinde devre dışı bırakarak iş profilini kopyalama/yapıştırma koruma duraklatabilirsiniz.

## <a name="tips-to-optimize-the-work-profile-experience"></a>İş profili iyileştirmek için ipuçları deneyimi

### <a name="when-to-use-app-within-work-profiles"></a>Ne zaman uygulama iş profillerinde kullanılır?

Intune uygulama ve iş profilleri birlikte veya ayrı ayrı kullanılabilir tamamlayıcı teknolojilerdir. Mimari, her iki çözüm de farklı katmanları – tek tek uygulama katmanında, uygulama düzeyinde ilkeleri zorunlu tutmanıza ve iş profili katmanında profili. İş profilindeki bir uygulama için bir uygulama ilkesiyle yönetilen uygulamalar dağıtma, geçerli ve desteklenen bir senaryodur. Uygulamayı kullanmak için DLP gereksinimlerinize göre iş profilleri veya bir birleşimine bağlıdır.

İş profilleri ve uygulama diğer kişilerin ayarları bir profil, kuruluşunuzun veri koruma gereksinimlerini karşılamıyorsa ek kapsamı sunarak tamamlar. Örneğin, iş profilleri yerel olarak bir uygulama, güvenilmeyen bir bulut depolama konumuna kaydedilmesi kısıtlamak için denetimleri sunmaz. Uygulama, bu özellik içerir. Yalnızca iş profili tarafından sağlanan DLP yeterlidir ve uygulamayı kullanmayı tercih karar verebilirsiniz. Veya ikisinin bir birleşiminden korumaları gerektirebilir.

### <a name="suppress-app-policy-for-work-profiles"></a>İş profilleri için uygulama ilkesi Gizle

Birden çok cihaz - yönetilmeyen cihazları bir uygulamada kullanan bireysel kullanıcılar desteklemesi gerekebilir-şu senaryonun ve yönetilen cihazları iş profilleriyle. 

Örneğin, son kullanıcıların bir iş uygulaması açarken bir PIN girmesini gerektirir. Cihaza bağlı olarak, PIN özellikleri, iş profiline veya uygulama tarafından işlenir. Uygulama için-BİZ cihazları, PIN başlatma davranışını, uygulama tarafından zorlanır. İş profili cihazları için bir cihaz kullanın veya iş profili PIN işletim sistemi tarafından zorlanır. Bu senaryoyu gerçekleştirmek için geçerli değildir, uygulama ayarlarını yapılandırma *olduğunda* iş profiline bir uygulama dağıtılır. Bu şekilde yapılandırmazsanız, son kullanıcı, cihaz ve uygulama katmanında yeniden bir PIN istenir.

### <a name="control-multi-identity-behavior-in-work-profiles"></a>İş profillerinde birden çok kimliği davranışını denetleme

Outlook ve OneDrive gibi Office uygulamaları "birden çok kimliği" davranışa sahip. Uygulamanın bir örneğini içinde son kullanıcı bağlantıları için birden çok farklı hesap ekleyebilir veya Bulut depolama konumlarına. Uygulama içinde şu konumlardan alınan verileri ayrı veya birleştirilmiş olabilir. Ve kullanıcının kişisel kimlikleri arasında bağlamı geçiş yapabilirsiniz (user@outlook.com) ve kuruluş kimlikleri (user@contoso.com).

İş profilleri kullanırken, bu çoklu kimlik davranışı devre dışı bırakmak isteyebilirsiniz. Bunu devre dışı bıraktığınızda, iş profilindeki Uygulama badged örneklerini yalnızca bir kuruluş kimliği ile yapılandırılabilir. Office Android uygulamaları desteklemek için izin verilen hesaplar uygulama yapılandırma ayarı kullanın.

Daha fazla bilgi için [Outlook iOS ve Android uygulama yapılandırma ayarlarını dağıtma](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-configuration-with-microsoft-intune).

## <a name="when-to-use-intune-app"></a>Intune uygulamayı kullanmak ne zaman

Çeşitli Kurumsal hareketlilik senaryoları Intune uygulama kullanıldığında olan en iyi öneri vardır.

#### <a name="older-devices-running-android-44-51-are-being-used"></a>Android 4.4 5.1 çalıştıran eski cihazları kullanılır

Resmi olarak, herhangi bir Android cihaz 5.0 veya Google mobil hizmetlerle iş profilleri destekler ve bu şekilde yönetilmesi uygundur. Ancak, bazı Android 5.0 ve OEM'leri 5.1 cihazlardan iş profilleri desteklemez.

İş profilleri desteklemeyen sürümleri kullanıyorsanız ve cihazlarda kuruluş verileri için DLP emin olmak için Intune uygulama özelliklerini kullanın.

#### <a name="no-mdm-no-enrollment-google-services-are-unavailable"></a>Hiçbir MDM, hiçbir kayıt, Google Hizmetleri kullanılamaz

Bazı müşteriler, cihaz yönetimi, farklı nedenlerden dolayı iş profili yönetimi dahil olmak üzere herhangi bir biçimde istemiyorsanız:

- Yasal ve Sorumluluk nedenleri
- Tutarlılık için kullanıcı deneyimi
- Android cihaz yüksek oranda heterojen ortamıdır
- İş profili yönetimi için gerekli olan Google hizmetlerine herhangi bir bağlantı yoktur.

Örneğin, müşteriler veya kullanıcıları, Çin'de, Android cihaz yönetimini kullanamaz, Google Hizmetleri engellenir olduğundan. Bu durumda, Intune uygulama için DLP kullanın.

## <a name="summary"></a>Özet

Intune, hem uygulama kullanarak-EDİYORUZ ve kurumsal Android iş profilleri Android KCG programınızın kullanılabilir. Uygulamasını seçin.-BİZ veya iş profilleri iş ve kullanım gereksinimlerine göre değişir. Sertifika dağıtımı, gönderme ve benzeri gibi yönetilen cihazlarda MDM etkinlikleri gerekiyorsa Özet olarak, iş profillerini kullanın. Bir uygulama kullanma-BİZ istemiyorsanız veya cihazlarını yönetemezsiniz ve yalnızca Intune APP etkin uygulamalar kullanıyorsanız.

## <a name="next-steps"></a>Sonraki adımlar
[Uygulama koruma ilkeleri kullanmaya başlama](app-protection-policy.md), veya [cihazları kaydetme](android-enroll.md).
