---
title: Geliştirme - Intune
titleSuffix: ''
description: Geliştirme Intune özellikleri
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/03/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4e9a640a343efd4ad786d7697439531de3cd4ed3
ms.sourcegitcommit: 2f32f6d2129bc10cc4a02115732e995edceb37d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/11/2019
ms.locfileid: "66828968"
---
# <a name="in-development-for-microsoft-intune---june-2019"></a>Microsoft Intune - Haziran 2019 geliştirme

İçinde hazırlık ve planlama, bu sayfa yardımcı olmak için Intune kullanıcı Arabirimi güncelleştirmeleri ve özelliklerinin listesi geliştirme aşamasındadır ancak henüz serbest. Buna ek olarak:

- Bir değişiklik önce harekete gerekecektir tahmin, biz tamamlayıcı bir Office ileti Merkezi'nde gönderi yayınlayacaksınız.
- Ne zaman bir özellik, üretimde ya da önizleme olarak başlatılır veya genel kullanıma sunulan özellik açıklaması bu sayfayı kapatmak ve üzerine taşınır [yenilikler](whats-new.md).
- Bu sayfada ve [yenilikler](whats-new.md) düzenli olarak güncelleştirilir. Ek güncelleştirmeleri daha sonra denetleyin.
- Başvurmak [M365 yol haritası](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS) stratejik teslim edilebilirleri ve zaman çizelgeleri için.

> [!Note]
> Bu öğeler, gelecekteki bir sürümde sunulacak Intune özellikleri hakkında daha fazla geçerli beklentileri Microsoft'un yansıtır. Tarih ve tek tek özellikler değişebilir. Geliştirme tüm öğeler, bu sayfada bir özellik açıklaması içerir.

**RSS akışı**: Bu sayfa aşağıdaki URL'yi kullanarak akış okuyucuya yapıştırarak güncelleştirildiğinde bildirim alın: `https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`

<!--
## What's coming to Intune in the Azure portal 
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Azure portalında Intune

<!-- ***********************************************-->
### <a name="app-management"></a>Uygulama yönetimi

#### <a name="device-users-can-view-all-managed-apps-theyve-installed-or-tried-to-install----2352913---"></a>Cihaz kullanıcılarının yüklü veya yüklemeyi denedi tüm yönetilen uygulamalar görüntüleyebilirsiniz. <!-- 2352913 -->
Bir kullanıcı cihazında yüklü (gerekli ve kullanılabilir) tüm yönetilen uygulamalar için Şirket portalı Windows listeler. Kullanıcılar, denenen görüntülemek ve bekleyen uygulama yüklemelerini ve bunların geçerli durumlarını mümkün olacaktır. Kuruluşunuzun uygulamalarını gerekli veya kullanılabilir duruma getirilmez, kullanıcılar şirket uygulama yüklenmiş olduğunu açıklayan bir ileti görür. Kullanıcılar ayrıca sıralamak veya uygulamalarını yükleme durumuna göre filtre uygulamak mümkün olacaktır.

#### <a name="configure-which-browser-is-allowed-to-link-to-organization-data----3145939---"></a>Tarayıcı kuruluş verilerine bağlanan yapılandırabilirsiniz <!-- 3145939 -->
Android ve iOS cihazlarında Intune uygulama koruma ilkelerini (APP) Org web bağlantılarını Intune Managed Browser ya da Microsoft Edge ötesinde belirli bir tarayıcıya aktarmanıza imkan sağlar.  Uygulama hakkında daha fazla bilgi için bkz. [uygulama koruma ilkeleri nelerdir?](app-protection-policy.md).

#### <a name="installed-apps-page-on-the-company-portal-website-----4224326---"></a>Uygulama sayfası Şirket portalı Web sitesinde yüklü  <!-- 4224326 -->
[Şirket portalı Web sitesine](https://portal.manage.microsoft.com/) kullanıcıları göstermek için yeni bir sayfa içerecektir tüm cihazlarında yüklü uygulamaları. Bu liste, kullanılabilir uygulamaları hem kuruluş tarafından gerekli uygulamaları içerir. Bu sayfada, kullanıcıların cihazlarında uygulamaları yükleme ve gereksinim durumları görmek mümkün olacaktır. Şirket portalı Web sitesi hakkında daha fazla bilgi için bkz. [Intune Şirket portalı Web sitesini kullanarak](/intune-user-help/using-the-intune-company-portal-website.md) ve [Microsoft Intune Şirket portalı uygulamasını yapılandırma](company-portal-app.md).

#### <a name="call-graph-api-read-operations-from-an-application-without-user-credentials----4655885---"></a>Kullanıcı kimlik bilgileri olmayan bir uygulamadan okuma işlemleri Graph API çağırma <!-- 4655885 -->
Uygulamalar, okuma işlemleri kullanıcı kimlik bilgileri olmadan uygulama kimliği ile Intune Graph API'sini çağırmak mümkün olacaktır. Daha fazla bilgi için bkz. [bir kullanıcı olmaksızın erişim elde](https://docs.microsoft.com/graph/auth-v2-service).

<!-- ***********************************************-->
### <a name="device-configuration"></a>Cihaz yapılandırması


#### <a name="support-for-ikev2-vpn-profiles-for-ios----1943438---"></a>İOS için Ikev2 VPN profilleri için destek <!-- 1943438 -->
Ikev2 protokolü kullanarak iOS yerel VPN istemcisi için VPN profillerini oluşturmak mümkün olacaktır. Ikev2, yeni bir bağlantı türü olduğundan **cihaz Yapılandırması** > **profilleri** > **profili oluşturma** > **iOS**  Platform > **VPN** profil türü için > **ayarları**.

Bu VPN profillerini yerel VPN istemcisini yapılandırın. Bu nedenle, hiçbir VPN istemci uygulamaları yüklü veya yönetilen cihazlara gönderildi. Bu özellik cihazlar gerektirir kaydedilmesi gereken Intune'a (MDM kaydı).

Yapılandırabileceğiniz geçerli VPN ayarları görmek için Git [Microsoft Intune iOS cihazlarında VPN yapılandırma ayarları](vpn-settings-ios.md).

Şunun için geçerlidir: iOS

#### <a name="configure-settings-for-kernel-extensions-on-macos-devices----20430240---"></a>MacOS cihazlarında çekirdek uzantıları için ayarları yapılandırma <!-- 20430240 -->
MacOS cihazlarında cihaz yapılandırma profili oluşturabilirsiniz (**cihaz Yapılandırması** > **profilleri** > **profili oluşturma** > seçin **macOS** platform için). Gelecekte yapılacak bir güncelleştirmenin yapılandırmak ve çekirdek uzantıları cihazlarınızda kullanmanıza olanak tanıyan ayarlar yeni bir grup içerir.

İçin geçerlidir: macOS 10.13.2 ve üzeri

#### <a name="baseline-support-for-keyword-search-----3082036-----------"></a>Anahtar sözcüğü için temel desteği arayın  <!-- 3082036         -->
Oluşturma veya bir güvenlik taban çizgisi profil düzenleme sırasında yakında kullanmak mümkün olacaktır *arama* konsolda görüntüleme ayarları filtrelemek için.   

#### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910---"></a>"Uygulanabilirlik kuralları" kullandığınızda Windows 10 cihaz yapılandırma profilleri oluşturma <!-- 2549910 -->
Windows 10 cihaz yapılandırma profilleri oluşturma (**cihaz Yapılandırması** > **profilleri** > **profili oluşturma**  >  **Windows 10** platform için). Oluşturma tutulacak bir **Uygulanabilirlik kuralı** profili yalnızca bir belirli sürüm veya belirli bir sürüme uygular. Örneğin, bazı BitLocker ayarları sağlayan bir profil oluşturun. Profili eklediğinizde profil, yalnızca Windows 10 Enterprise çalıştıran cihazlar için uygular bir geçerlilik kuralı kullanın.

Şunun için geçerlidir: 
- Windows 10 ve üzeri

#### <a name="apps-from-the-store-only-setting-for-windows-10-devices-includes-more-configuration-options----2697002----"></a>Daha fazla yapılandırma seçeneği yalnızca Windows 10 cihazlar için ayar Mağazası'ndan uygulama içerir <!-- 2697002  -->

Windows cihazları için cihaz kısıtlama profili oluşturduğunuzda, kullanabileceğiniz **uygulamaları yalnızca mağazadan** kullanıcılar, uygulamaları yalnızca Windows App Store ' yükler. Bu nedenle ayarlama (**cihaz Yapılandırması**  >  **Profilleri** > **profili oluşturma** > **Windows 10 ve üzeri** Platform > **cihaz kısıtlamaları** profil türü için). Daha fazla seçenek desteklemek için bu ayarı gelecekteki bir güncelleştirmede genişletilir. 

Geçerli ayarları görmek için Git [izin vermek veya Intune kullanarak özellikleri kısıtlamak için Windows 10 (ve üzeri) cihaz ayarları](device-restrictions-windows-10.md#app-store).

Şunun için geçerlidir: Windows 10 ve üzeri

#### <a name="deploy-multiple-zebra-mobility-extensions-device-profiles-to-a-device-same-user-group-or-same-devices-group----4089955---"></a>Bir cihaz, aynı kullanıcı grubuna veya aynı cihaz grubu birden çok Zebra mobility uzantıları cihaz profilleri dağıtma <!-- 4089955 -->
Intune'da ayarlarını özelleştirmek için bir cihaz yapılandırma profilinde de Zebra mobility Uzantıları (MX) kullanın veya değil yerleşik ayarları Intune'a ekleyin. Şu anda tek bir cihaz için bir profil dağıtabilirsiniz. Gelecekteki bir güncelleştirmede birden çok profillere dağıtmak mümkün olacaktır:

- Aynı kullanıcı grubunu
- Aynı aygıtları grubu
- Tek bir cihaz

[Kullanma ve Microsoft Intune Zebra Mobility uzantılarıyla Zebra cihazları yönetme](android-zebra-mx-overview.md) Intune'da MX kullanmayı gösterir.

Şunun için geçerlidir: Android

#### <a name="some-kiosk-settings-on-ios-devices-are-set-using-block-replacing-allow----4404075----"></a>"Blok"İzin ver"değiştirme", kullanarak bazı iOS cihazlarda bilgi noktası ayarlarını ayarlayın <!-- 4404075  -->
İOS cihazlarında cihaz kısıtlama profili oluşturduğunuzda (**cihaz Yapılandırması** > **profilleri** > **profili oluşturma**  >  **iOS** Platform > **cihaz kısıtlamaları** profil türü için > **bilgi noktası**), ayarladığınız **otomatik kilit**, **Açma/kapama**, **ekran döndürme**, **ekran Uyku düğmesi**, ve **ses düzeyi düğmelerine**. 

Bu ayarlar kullanılarak şu anda yapılandırılmış olan **izin** (özellik engeller) veya **yapılandırılmadı** (özellik izin verir). Gelecekteki bir güncelleştirmede değerler şöyle olacaktır **blok** (özellik engeller) veya **yapılandırılmadı** (özellik izin verir).

Geçerli ayarları görmek için Git [izin vermek veya özellikleri kısıtlamak için iOS cihaz ayarlarını](device-restrictions-ios.md). 

Şunun için geçerlidir: iOS

#### <a name="use-face-id-for-password-authentication-on-ios-devices----4490704----"></a>İOS cihazlarda parola kimlik doğrulaması için face ID kullanın <!-- 4490704  -->
İOS cihazları için cihaz kısıtlama profili oluşturduğunuzda, parmak izi parolasını kullanabilirsiniz. Gelecekteki bir güncelleştirmede parmak izi parola ayarlarını da yüz tanıma sağlayacak (**cihaz Yapılandırması** > **profilleri** > **profili oluşturma**   >  **iOS** Platform > **cihaz kısıtlamaları** profil türü için > **parola**). Sonuç olarak, aşağıdaki ayarları değiştirme:

- **Parmak iziyle kilit açma** artık **Touch ID ve Face ID ile kilidini**.
- **Parmak izi değişikliği (yalnızca denetimli)** artık **Touch ID ve Face ID değişikliği (yalnızca denetimli)** .

Face ID bulunan iOS 11.0 ve sonraki sürümleri. Geçerli ayarları görmek için Git [izin vermek veya Intune kullanarak özellikleri kısıtlamak için iOS cihaz ayarlarını](device-restrictions-ios.md#password).

Şunun için geçerlidir: iOS

#### <a name="apps-feature-is-dependent-on-ratings-region-when-restricting-gaming-and-app-store-features-on-ios-devices----4593948----"></a>Özellikleri, iOS cihazlarında depoladığınızda kısıtlama oyun ve uygulama apps özelliğini derecelendirme bölgesine bağlıdır <!-- 4593948  -->
İOS cihazlarında izin vermek veya kısıtlamak oyun, uygulama mağazasından ve belgeleri görüntülemek için ilgili özellikleri (**cihaz Yapılandırması** > **profilleri**  >   **Profil oluşturma** > **iOS** Platform > **cihaz kısıtlamaları** profil türü için > **App Store, belge görüntüleme, oyun**). Amerika Birleşik Devletleri gibi derecelendirme bölgesi de seçebilirsiniz. Gelecekteki bir güncelleştirmede **uygulamaları** özellik alt olacak şekilde taşınır **derecelendirme bölgesi**ve bağımlı olduğu **derecelendirme bölgesi**.

Geçerli ayarları görmek için Git [izin vermek veya Intune kullanarak özellikleri kısıtlamak için iOS cihaz ayarlarını](device-restrictions-ios.md#app-store-doc-viewing-gaming).

Şunun için geçerlidir: iOS

#### <a name="administrative-templates-for-group-policy---------3510695---"></a>Grup İlkesi Yönetim Şablonları     <!--  3510695 -->
Bulutta cihazlar için güvenlik geliştirmeye yardımcı olmak için biz Windows bilgisayarlar için select Grup İlkesi ayarlarını yapılandırmak için Intune'u kullanmayı olanak tanıyan Yönetim Şablonları yayımlar.  Bu şablonlar, Office, Windows ve OneDrive 2500 ek ayarlar kadar sağlamak için ilke yapılandırma hizmet sağlayıcısı (CSP) kullanın.

####  <a name="new-settings-for-the-windows-security-baseline-----3534649-4217151------------"></a>Windows Güvenlik taban çizgisi için yeni ayarlar  <!-- 3534649, 4217151          -->
Windows Güvenlik taban çizgisi için yeni ayarlar ekliyoruz. Sanallaştırma tabanlı Güvenli Önyükleme gerektiren güvenlik için ilk ayarıdır. İkinci ayar ekranı kilitliyken sesli etkinleştirme Windows uygulamalarını yönetmenizi sağlar.

#### <a name="security-baselines-will-be-generally-available------3785395---------"></a>Güvenlik temellerini genel kullanıma sunulacaktır.  <!--  3785395       -->
Güvenlik temellerini özellik yakında Önizleme, yetersiz ve genel kullanıma sunulacaktır. 

#### <a name="the-windows-security-baseline-template-will-be-generally-available-------3794072---------"></a>Windows Güvenlik temel şablon genel kullanıma sunulacaktır.   <!--  3794072       -->
Windows Güvenlik temel şablon, Önizleme, yetersiz ve genel kullanıma sunulan Yakında sunulacak. Şablon Önizleme sürümünü kullanımdan kaldırılacak ve yeni bir şablon kullanılabilir.

<!-- ***********************************************-->
### <a name="device-management"></a>Cihaz yönetimi

#### <a name="assign-scope-tags-to-all-managed-devices-in-a-security-group----3173810---"></a>Bir güvenlik grubundaki tüm yönetilen cihazlar için kapsam etiketleri Ata <!-- 3173810 -->
Bir cihaz için her cihazı 's giderek bir kapsam etiketi şu anda atayabilirsiniz **özellikleri** sayfası ve kapsam etiketleri seçmenin. Gelecekte yapılacak bir güncelleştirme için bir güvenlik grubu kapsamı etiketleri atamak mümkün olacaktır ve güvenlik grubundaki tüm cihazlar da bu kapsam etiketleri ile ilişkilendirilecek. Bunu yapmak için **Intune** > **rolleri** > **kapsam (etiketler)**  > **Oluştur**  >  **Kapsam (etiketler)** > kapsam etiketinde atamak istediğiniz grupları seçin. Bu gruplardaki tüm cihazlar aynı zamanda kapsam etiketi atanır. Bu özelliği ile kapsam etiketleri geçerli cihaz kapsamı etiketleri akışı kümesi kapsam etiketleri üzerine yazar. (Gelecekteki bir güncelleştirmede kapsam etiketleri cihazlara atamak için geçerli akış salt okunur yapılır.)

#### <a name="see-the-security-patch-level-for-android-devices----4461911----"></a>Android cihazlar için güvenlik düzeltme eki düzeyi bakın <!-- 4461911  -->
Android cihazlar için güvenlik düzeltme eki düzeyi görmeye devam. Bunu yapmak için **Intune** > **cihazları** > **tüm cihazlar** > bir cihaz seçin > **İzleyici**  >  **Donanım**.


<!-- ***********************************************-->
## <a name="notices"></a>Bildirimler

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

### <a name="see-also"></a>Ayrıca bkz.
Son geliştirmelere ilişkin ayrıntılar için bkz. [Microsoft Intune’daki Yenilikler](whats-new.md).


