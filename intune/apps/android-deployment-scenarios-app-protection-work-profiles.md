---
title: Microsoft Intune-Azure 'da uygulama koruma ilkeleri ve iş profilleri | Microsoft Docs
description: Microsoft Intune ' de kişisel veya KCG Android Kurumsal cihazları için uygulama koruma ilkeleri veya iş profilleri kullanmaya karar verirken farkları ve uzmanları ve dezavantajları inceleyin. Kayıt (APP-WE) ve Android kurumsal iş profilleri olmadan uygulama koruma ilkeleriyle aldığınız farkları ve özellikleri karşılaştırın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/13/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 9d078c2e94f775d995e990c7a33e29871819d561
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71731489"
---
# <a name="application-protection-policies-and-work-profiles-on-android-enterprise-devices-in-intune"></a>Intune 'da Android kurumsal cihazlarda uygulama koruma ilkeleri ve iş profilleri

Birçok kuruluşta, yöneticilerin kaynakları ve verileri farklı cihazlarda koruması gerekir. Bir zorluk, kendi cihazını getir (KCG) olarak da bilinen kişisel Android Kurumsal cihazları olan kullanıcılar için kaynakları koruyor. Microsoft Intune kendi cihazını getir (BYOD) için iki Android dağıtım senaryosunu destekler:

- Kayıt olmadan uygulama koruma ilkeleri (APP-WE)
- Android kurumsal iş profilleri

APP-WE ve Android iş profili dağıtım senaryoları, KCG ortamları için önemli olan aşağıdaki temel özellikleri içerir:

1. **Kuruluş tarafından yönetilen verilerin korunması ve**ayrımı: her iki çözüm de, kuruluş tarafından yönetilen verilerde veri kaybı önleme (DLP) denetimleri zorlayarak kuruluş verilerini korur. Bu korumalar, son kullanıcı yanlışlıkla kişisel bir uygulamayla veya hesapla paylaşıldığından, korunan verilerin yanlışlıkla sızıntılarını önler. Ayrıca, verilere erişen bir cihazın sağlıklı olduğundan ve güvenliğinin aşılmadığından emin olmak için de kullanılır.

2. **Son kullanıcı gizliliği**: App-we ve Android kurumsal iş profilleri, son kullanıcılara cihazdaki içeriği ve mobil cihaz YÖNETIMI (MDM) Yöneticisi tarafından yönetilen verileri ayırır. Her iki senaryoda da BT yöneticileri, kuruluş tarafından yönetilen uygulamalarda veya kimliklerden yalnızca PIN kimlik doğrulaması gibi ilkeleri uygular. BT yöneticileri, son kullanıcılar tarafından sahip olunan veya denetlenen verileri okuyamaz, erişemez veya silemez.

APP-WE veya Android kurumsal iş profillerinin KCG dağıtımınız için, gereksinimlerinize ve iş gereksinimlerinize göre değişir. Bu makalenin amacı, karar vermenize yardımcı olmak için rehberlik sağlamaktır.

## <a name="about-intune-app-protection-policies"></a>Intune uygulama koruma ilkeleri hakkında

Intune uygulama koruma ilkeleri (uygulama), kullanıcılara hedeflenmiş veri koruma ilkelerdir. İlkeler, uygulama düzeyinde veri kaybı koruması uygular. Intune UYGULAMASı, uygulama geliştiricilerinin oluşturdukları uygulamalarda uygulama özelliklerini etkinleştirmesini gerektirir.

Tek tek Android uygulamaları uygulama için birkaç şekilde etkinleştirilmiştir:

1. **Microsoft birinci taraf uygulamalarına yerel olarak tümleştirilmiş**: Android için Microsoft Office uygulamalar ve diğer Microsoft uygulamalarının bir seçimi olan Intune uygulaması yerleşik olarak sunulur. Word, OneDrive, Outlook vb. gibi bu Office uygulamaları, ilke uygulamak için daha fazla özelleştirmeye gerek kalmaz. Bu uygulamalar, son kullanıcılar tarafından doğrudan Google Play Store yüklenebilir.

2. **Intune SDK 'sını kullanan geliştiriciler tarafından uygulama Derlemeleriyle tümleşiktir**: uygulama geliştiricileri, Intune SDK 'sını Kaynak kodla tümleştirebilir ve Intune uygulama ilkesi özelliklerini desteklemek için uygulamalarını yeniden derleyebilirsiniz.

3. **Intune uygulaması sarmalama aracı kullanılarak sarmalandı**: bazı müşteriler Android uygulamalarını derler (. APK dosyası) kaynak koda erişim olmadan. Kaynak kodu olmadan geliştirici, Intune SDK ile tümleştirilemiyor. SDK olmadan uygulama ilkeleri için uygulamalarını etkinleştiremez. Geliştirici, uygulama ilkelerini desteklemek için uygulamayı değiştirmeli veya yeniden kodmalıdır.

    Intune, yardım almak için mevcut Android Uygulamaları (APKs) için **Uygulama sarmalama aracı** aracını IÇERIR ve uygulama ilkelerini tanıyan bir uygulama oluşturur.

    Bu araçla ilgili daha fazla bilgi için bkz. [iş kolu uygulamalarını uygulama koruma ilkeleri için hazırlama](../developer/apps-prepare-mobile-application-management.md).

UYGULAMAYLA etkinleştirilen uygulamaların listesini görmek için bkz. [yönetilen uygulamalar zengin bir mobil uygulama koruma ilkeleri kümesi](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

## <a name="deployment-scenarios"></a>Dağıtım senaryoları

Bu bölümde, APP-WE ve Android kurumsal iş profili dağıtım senaryolarına ilişkin önemli özellikler açıklanmaktadır.

### <a name="app-we"></a>UYGULAMA-WE

Bir APP-WE (kayıt olmadan uygulama koruma ilkeleri) dağıtımı, cihazlarda değil, uygulamalar üzerinde ilkeleri tanımlar. Bu senaryoda, cihazlar genellikle Intune gibi bir MDM yetkilisi tarafından kaydedilmemektedir veya yönetilmez. Uygulamaları korumak ve kurumsal verilere erişmek için yöneticiler uygulama yönetilebilir uygulamalar kullanır ve veri koruma ilkelerini bu uygulamalara uygular.

Bu özellik şu platformlarda geçerlidir:

- Android 4,4 ve üzeri

> [!TIP]
> Daha fazla bilgi için bkz. [Uygulama koruma Ilkeleri nelerdir?](app-protection-policy.md).

Uygulama-BIZ senaryolar, cihazlarında küçük bir kurumsal ayak izi isteyen son kullanıcılara yöneliktir ve MDM 'ye kaydolmak istemiyor. Yönetici olarak, yine de verilerinizi korumanız gerekir. Bu cihazlar yönetilmez. Bu nedenle, WiFi, cihaz VPN ve sertifika yönetimi gibi yaygın MDM görevleri ve özellikleri bu dağıtım senaryosunun bir parçası değildir.

### <a name="android-enterprise-work-profiles"></a>Android kurumsal iş profilleri

İş profilleri, temel Android kurumsal dağıtım senaryosudur ve KCG kullanım durumlarında hedeflenen tek senaryodur. İş profili, Android işletim sistemi düzeyinde oluşturulan ve Intune tarafından yönetilebilen ayrı bir bölümdür.

Bu özellik şu platformlarda geçerlidir:

- Google Mobile Services ile Android 5,0 ve üzeri cihazlar

Bir iş profili aşağıdaki özellikleri içerir:

- **Geleneksel MDM işlevselliği**: yönetilen Google Play kullanan uygulama yaşam döngüsü yönetimi gıbı temel MDM özellikleri, herhangi bir Android kurumsal senaryosunda kullanılabilir. Yönetilen Google Play, Kullanıcı müdahalesi olmadan uygulamaları yüklemek ve güncelleştirmek için güçlü bir deneyim sağlar. Ayrıca, uygulama yapılandırma ayarlarını kurumsal uygulamalara gönderebilir. Ayrıca son kullanıcıların bilinmeyen kaynaklardan yüklemelere izin vermeyi gerektirmez. Sertifikaları dağıtma, WiFi/VPN 'Ler yapılandırma ve cihaz geçiş kodlarını ayarlama gibi diğer yaygın MDM etkinlikleri, iş profilleriyle birlikte kullanılabilir.

- **İş profili sınırında DLP**: App-we gibi, veri koruma ilkelerini uygulayabilir. Bir iş profili ile DLP ilkeleri, uygulama düzeyinde değil iş profili düzeyinde zorlanır. Örneğin, Kopyala/Yapıştır koruması, bir uygulamaya uygulanan veya iş profili tarafından zorlanan uygulama ayarları tarafından zorlanır. Uygulama bir iş profiline dağıtıldığında, Yöneticiler bu ilkeyi uygulama düzeyinde kapatarak iş profiline kopyalama/yapıştırma korumasını duraklatabilir.

## <a name="tips-to-optimize-the-work-profile-experience"></a>İş profili deneyimini iyileştirmek için ipuçları

### <a name="when-to-use-app-within-work-profiles"></a>İş profilleri içinde uygulama ne zaman kullanılır?

Intune UYGULAMASı ve iş profilleri, birlikte veya ayrı olarak kullanılabilen tamamlayıcı teknolojilerdir. Mimari türsel olarak, her iki çözüm de farklı katmanlarda ilkeler uygular – tek tek uygulama katmanında uygulama ve profil katmanındaki iş profili. Bir uygulama ilkesiyle yönetilen uygulamaları iş profilindeki bir uygulamaya dağıtmak, geçerli ve desteklenen bir senaryodur. UYGULAMA, iş profilleri veya bir bileşim kullanmak için DLP gereksinimlerinize göre değişir.

İş profilleri ve uygulama, bir profilin kuruluşunuzun veri koruma gereksinimlerini karşılamazsa ek kapsam sağlayarak her birinin ayarlarını tamamlar. Örneğin iş profilleri, bir uygulamanın güvenilmeyen bir bulut depolama konumuna kaydedilmesini kısıtlamak için yerel olarak denetim sağlamayın. UYGULAMA bu özelliği içerir. Yalnızca iş profili tarafından sunulan DLP 'nin yeterli olduğunu ve uygulamayı kullanmayacağınıza karar verebilirsiniz. Ya da iki bir birleşimden korumalar gerekebilir.

### <a name="suppress-app-policy-for-work-profiles"></a>İş profilleri için uygulama ilkesini gösterme

Bir APP-WE senaryosunda ve yönetilen cihazlarda iş profillerine sahip olan birden çok cihazdan yönetilmeyen tek kullanıcıları desteklemeniz gerekebilir.

Örneğin, son kullanıcıların bir iş uygulamasını açarken PIN girmesini zorunlu kılabilirsiniz. Cihaza bağlı olarak, PIN özellikleri uygulama veya iş profili tarafından işlenir. APP-WE cihazlarında, uygulama tarafından başlatılan SABITLEME davranışı uygulanır. İş profili cihazları için işletim sistemi tarafından zorlanan bir cihaz veya iş profili PIN 'ı kullanabilirsiniz. Bu senaryoyu başarmak için uygulama ayarlarını, bir *uygulama bir iş profiline dağıtıldığında uygulanmayacak* şekilde yapılandırın. Bu şekilde yapılandırmazsanız, son kullanıcıya cihaz tarafından bir PIN istenir ve uygulama katmanında tekrar sorulur.

### <a name="control-multi-identity-behavior-in-work-profiles"></a>İş profillerinde çoklu kimlik davranışını denetleme

Outlook ve OneDrive gibi Office uygulamalarında "çoklu kimlik" davranışı vardır. Uygulamanın bir örneği içinde, Son Kullanıcı birden çok farklı hesaba veya bulut depolama konumuna bağlantı ekleyebilir. Uygulama içinde, bu konumlardan alınan veriler ayrı veya birleştirilebilir. Ve Kullanıcı, kişisel kimlikler (user@outlook.com) ve kuruluş kimlikleri (user@contoso.com) arasında geçiş yapabilir.

İş profillerini kullanırken, bu çoklu kimlik davranışını devre dışı bırakmak isteyebilirsiniz. Devre dışı bıraktığınızda, iş profilindeki uygulamanın bozuk örnekleri yalnızca bir kuruluş kimliğiyle yapılandırılabilir. Office Android uygulamalarını desteklemek için Izin verilen hesaplar uygulama yapılandırma ayarını kullanın.

Daha fazla bilgi için bkz. [iOS ve Android uygulama yapılandırma ayarları Için Outlook dağıtma](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-configuration-with-microsoft-intune).

## <a name="when-to-use-intune-app"></a>Intune UYGULAMASı ne zaman kullanılır?

Intune UYGULAMASıNıN kullanılması en iyi önerimiz olan birçok kurumsal Mobility senaryosu vardır.

### <a name="older-devices-running-android-44-51-are-being-used"></a>Android 4.4-5.1 çalıştıran eski cihazlar kullanılıyor

Resmi olarak, Google Mobile Services tüm Android cihaz 5,0 veya üzeri iş profillerini destekler ve bu şekilde yönetilmeye uygundur. Ancak, bazı OEM 'lerden bazı Android 5,0 ve 5,1 cihazları iş profillerini desteklemez.

İş profillerini desteklemeyen sürümleri kullanıyorsanız ve cihazlarda kuruluş verileri için DLP sağlamak istiyorsanız, Intune uygulama özelliklerini kullanmanız gerekir.

### <a name="no-mdm-no-enrollment-google-services-are-unavailable"></a>MDM yok, kayıt yok, Google hizmetleri kullanılamıyor

Bazı müşteriler, farklı nedenlerle iş profili yönetimi de dahil olmak üzere herhangi bir cihaz yönetimi biçimini istemiyor:

- Yasal ve sorumlulukların nedenleri
- Kullanıcı deneyiminin tutarlılığı için
- Android cihaz ortamı çok heterojen
- İş profili yönetimi için gerekli olan Google Services bağlantısı yok.

Örneğin, Android 'deki kullanıcılar, Google hizmetleri engellendiğinden Android cihaz yönetimini kullanamaz. Bu durumda, DLP için Intune UYGULAMASıNı kullanın.

## <a name="summary"></a>Özet

Intune 'u kullanarak, Android BYOD programınız için APP-WE ve Android kurumsal iş profillerinin her ikisi de mevcuttur. UYGULAMA seçmek için-BIZ veya iş profilleri, iş ve kullanım gereksinimlerinize bağlıdır. Özet bölümünde, yönetilen cihazlarda sertifika dağıtımı, uygulama gönderme gibi MDM etkinlikleri varsa iş profilleri ' ni kullanın. UYGULAMA kullanma-cihazları istemediğiniz veya yönetemezseniz ve yalnızca Intune uygulama özellikli uygulamaları kullanıyorsanız.

## <a name="next-steps"></a>Sonraki adımlar
[Uygulama koruma ilkelerini kullanmaya başlayın](app-protection-policy.md)veya [cihazlarınızı kaydedin](../enrollment/android-enroll.md).
