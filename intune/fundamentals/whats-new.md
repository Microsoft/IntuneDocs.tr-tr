---
title: Microsoft Intune - Azure’daki yenilikler | Microsoft Docs
titleSuffix: ''
description: Intune Azure portalındaki yenilikleri keşfedin
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/23/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1a6f0786c5b11e30bf86b237bc1f5c05a55010d5
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71732349"
---
# <a name="whats-new-in-microsoft-intune"></a>Microsoft Intune'daki yenilikler

Microsoft Intune’daki haftalık yenilikleri öğrenin. Ayrıca, [önemli bildirimler](#notices), [Geçmiş yayınlar](whats-new-archive.md)ve [Intune hizmet güncelleştirmelerinin nasıl yayımlandığına](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Service-Updates/ba-p/358728)ilişkin bilgileri de bulabilirsiniz.

> [!Note]
> Her [aylık güncelleştirmenin](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Service-Updates/ba-p/358728) piyasaya çıkma üç güne kadar sürebilir ve şu sırada olacaktır:
>
> - Gün 1: Asya Pasifik (APAC)
> - Gün 2: Avrupa, Orta Doğu, Afrika (EMEA)
> - Gün 3: Kuzey Amerika
>
> Bazı özelliklerin piyasaya çıkması birkaç haftayı bulabilir ve tüm özellikler ilk hafta bütün müşterilerimize sunulmamış olabilir.
>
> Bir sürümdeki yaklaşan özelliklerin bir listesi için [geliştirme sayfasını](in-development.md) inceleyin.

**RSS akışı**: Şu URL 'yi kopyalayıp akış okuyucunuzun içine yapıştırarak, Bu sayfa güncelleştirildikten sonra bildirim alın: `https://docs.microsoft.com/api/search/rss?search=%22What%27s+new+in+microsoft+intune%3F+-+Azure%22&locale=en-us`

<!-- Common categories:  
### App management
### Device configuration
### Device enrollment
### Device management
### Device security
### Intune apps
### Monitor and troubleshoot
### Role-based access control

-->  

<!-- ########################## -->

## <a name="week-of-september-23-2019"></a>23 Eylül 2019 haftası

#### <a name="ios-user-enrollment-in-preview----4817900---"></a>Önizlemede iOS Kullanıcı kaydı <!-- 4817900 -->
Apple 'ın iOS 13,1 sürümü, iOS cihazları için basit yönetimin yeni bir biçimi olan Kullanıcı kaydını içerir. Bu, kişisel cihazlar için cihaz kaydı veya otomatik cihaz kaydı (eski adıyla Aygıt Kayıt Programı) yerine kullanılabilir. Intune 'un önizlemesi, bu özellik kümesini şunları yapmanıza izin vererek destekler:

- Kullanıcı kaydını Kullanıcı gruplarına hedefleyin.
- Son kullanıcılara cihazlarını kaydettiklerinde daha hafif Kullanıcı kaydı veya daha güçlü bir cihaz kaydı arasından seçim yapma olanağı sunun.

9/24/2019 ' den başlayarak, iOS 13,1 ' nin yayımlanmasından itibaren, bu güncelleştirmeleri tüm müşterilere teslim etmek ve önümüzdeki hafta sonuna kadar tamamlanmasını beklemek için çalışıyoruz.
Uygulama hedefi:

iOS 13,1 ve üzeri

#### <a name="intune-support-for-ipados-and-ios-131-devices---5439574--"></a>Idos ve iOS 13,1 cihazları için Intune desteği <!--5439574-->
Intune artık Idos ve iOS 13,1 cihazlarını yönetmeyi desteklemektedir. Daha fazla bilgi için [bu blog gönderisine](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Support-for-iOS-13-1-and-iPadOS/ba-p/873094) bakın.

<!-- ########################## -->

## <a name="week-of-september-16-2019"></a>16 Eylül 2019 haftası

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Uygulama yönetimi 

#### <a name="managed-google-play-private-lob-apps----1464182----"></a>Yönetilen Google Play özel LOB uygulamaları <!-- 1464182  -->
Intune artık BT yöneticilerinin Intune konsoluna katıştırılmış bir iframe aracılığıyla özel Android LOB uygulamalarını yönetilen Google Play yayımlamasına olanak tanır.  Daha önce BT yöneticileri, çeşitli adımları gerektiren ve zaman tüketen, LOB uygulamalarını doğrudan Google Play yayımlama konsoluna yayımlamak için gereklidir. Bu yeni özellik, Intune konsolundan ayrılmak zorunda kalmadan LOB uygulamalarının en az bir adım kümesiyle kolayca yayımlanmasını sağlar.  Yöneticiler artık Google ile bir geliştirici olarak el ile Kaydolmayacak ve artık Google $25 kayıt ücretini ödemem gerekmez.  Yönetilen Google Play kullanan Android kurumsal yönetim senaryolarından herhangi biri bu özellikten yararlanabilir (iş profili, adanmış, tam olarak yönetilen ve kayıtlı olmayan cihazlar). Intune 'da, **istemci uygulamaları** > **uygulama** > **Ekle**' yi seçin. Ardından, **uygulama türü** listesinden **yönetilen Google Play** ' yi seçin. Yönetilen Google Play uygulamalar hakkında daha fazla bilgi için bkz. [Intune Ile Android Enterprise cihazlarına yönetilen Google Play uygulamaları ekleme](../apps/apps-add-android-for-work.md).

#### <a name="windows-company-portal-experience----1473353-3598357---"></a>Windows Şirket Portalı deneyimi <!-- 1473353, 3598357 -->
Windows Şirket Portalı güncelleştiriliyor. Windows Şirket Portalı içindeki uygulamalar sayfasında birden çok filtre kullanabileceksiniz. Cihaz ayrıntıları sayfası, gelişmiş bir kullanıcı deneyimiyle de güncelleştiriliyor. Bu güncelleştirmeleri tüm müşterilere teslim etmek ve önümüzdeki hafta sonuna kadar tamamlanmasını beklemek istiyoruz.

#### <a name="macos-support-for-web-apps----3174427---"></a>Web uygulamaları için macOS desteği <!-- 3174427 -->
Web 'deki bir URL 'ye kısayol eklemenize olanak sağlayan Web Apps, macOS Şirket Portalı kullanılarak Dock 'a yüklenebilir. Son kullanıcılar, macOS Şirket Portalı bir Web uygulaması için uygulama ayrıntıları sayfasından **Install** eylemine erişebilir. **Web bağlantısı** uygulama türü hakkında daha fazla bilgi için bkz. [Microsoft Intune uygulama ekleme](../apps/apps-add.md) ve [Microsoft Intune Web uygulamaları ekleme](../apps/web-app.md).

#### <a name="macos-support-for-vpp-apps----3173501----"></a>VPP uygulamaları için macOS desteği <!-- 3173501  -->
Apple Business Manager kullanılarak satın alınan macOS uygulamaları, Apple VPP belirteçleri Intune 'da eşitlendiğinde konsolunda görüntülenir. Intune konsolunu kullanarak, gruplar için cihaz ve Kullanıcı tabanlı lisanslar atayabilir, iptal edebilir ve yeniden atayabilirsiniz. Microsoft Intune, şirketinizde kullanılmak üzere satın alınan VPP uygulamalarını şu şekilde yönetmenize yardımcı olur:

- Uygulama mağazasından lisans bilgilerini raporlama.
- Kaç lisans kullandığınızı izleme.
- Sahip olduğunuz uygulamanın daha fazla kopyasını yükleme zorunluluğunu ortadan kaldırır.

Intune ve VPP hakkında daha fazla bilgi için bkz. [Microsoft Intune ile toplu satın alınan uygulamaları ve kitapları yönetme](../apps/vpp-apps.md).

#### <a name="managed-google-play-iframe-support----2871756----"></a>Yönetilen Google Play iFrame desteği <!-- 2871756  -->
Intune artık yönetilen Google Play iframe aracılığıyla doğrudan Intune konsolunda Web bağlantıları ekleme ve yönetme desteği sağlar.  Bu, BT yöneticilerinin bir URL ve simge grafiği göndermesini sağlar ve ardından bu bağlantıları düzenli Android uygulamaları gibi cihazlara dağıtır. Yönetilen Google Play kullanan Android kurumsal yönetim senaryolarından herhangi biri bu özellikten yararlanabilir (iş profili, adanmış, tam olarak yönetilen ve kayıtlı olmayan cihazlar). Intune 'da, **istemci uygulamaları** > **uygulama** > **Ekle**' yi seçin. Ardından, **uygulama türü** listesinden **yönetilen Google Play** ' yi seçin. Yönetilen Google Play uygulamalar hakkında daha fazla bilgi için bkz. [Intune Ile Android Enterprise cihazlarına yönetilen Google Play uygulamaları ekleme](../apps/apps-add-android-for-work.md).

#### <a name="silently-install-android-lob-apps-on-zebra-devices----4252734----"></a>Android LOB uygulamalarını Zeköşeli cihazlara sessizce yüklemeyin <!-- 4252734  -->
Android iş kolu (LOB) uygulamalarını, her ikisi de LOB uygulaması indirip yüklemeniz istenmek yerine [Zeköşeli cihazlara](../configuration/android-zebra-mx-overview.md)yüklerken uygulamayı sessizce yükleyebilirsiniz. Intune 'da, **istemci uygulamaları** > **uygulama** > **Ekle**' yi seçin. **Uygulama ekle** bölmesinde **İş kolu uygulaması**’nı seçin. Daha fazla bilgi için bkz. [Microsoft Intune Android iş kolu uygulaması ekleme](../apps/lob-apps-android.md).

Şu anda, LOB uygulaması indirildikten sonra kullanıcının cihazında bir **indirme başarısı** bildirimi görüntülenir. Bildirim yalnızca bildirim gölgelede **Clear All** öğesine dokunarak kapatılabilir. Bu bildirim sorunu gelecek bir sürümde düzeltilecektir ve yükleme hiçbir görsel gösterge olmadan tamamen sessiz olacaktır.

#### <a name="read-and-write-graph-api-operations-for-intune-apps----5031704----"></a>Intune uygulamaları için okuma ve yazma Graph API işlemleri <!-- 5031704  -->
Uygulamalar, Kullanıcı kimlik bilgileri olmadan uygulama kimliği 'ni kullanarak hem okuma hem de yazma işlemlerinde Intune Graph API çağırabilir. Intune için Microsoft Graph API 'sine erişme hakkında daha fazla bilgi için, bkz. [Microsoft Graph Intune Ile çalışma](https://docs.microsoft.com/graph/api/resources/intune-graph-overview?view=graph-rest-1.0).

#### <a name="protected-data-sharing-and-encryption-for-intune-app-sdk-for-ios----3586942----"></a>İOS için Intune uygulama SDK 'Sı korumalı veri paylaşımı ve şifrelemesi <!-- 3586942  -->
İOS için Intune uygulama SDK 'Sı, uygulama koruma Ilkeleri tarafından şifreleme etkinleştirildiğinde 256 bitlik şifreleme anahtarlarını kullanacaktır. Korunan veri paylaşımına izin vermek için tüm uygulamaların bir SDK sürümü 8.1.1 olması gerekir.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="support-for-ikev2-vpn-profiles-for-ios----1943438-----"></a>İOS için IKEv2 VPN profilleri desteği <!-- 1943438   -->
Bu güncelleştirmede, Ikev2 protokolünü kullanarak iOS Native VPN istemcisi için VPN profilleri oluşturabilirsiniz. Ikev2, **cihaz yapılandırma** > **profillerdeki**yeni bir bağlantı türüdür @no__t **-3 SDK**için  > **iOS** > profil türü > **bağlantı türü**için **VPN** .

Bu VPN profilleri yerel VPN istemcisini yapılandırır, bu nedenle yönetilen cihazlara hiçbir VPN istemci uygulaması yüklenmeyecek veya gönderilmemiş. Bu özellik cihazların Intune 'A (MDM kaydı) kaydedilmesini gerektirir.

Yapılandırabileceğiniz geçerli VPN ayarlarını görmek için [iOS CIHAZLARıNDA VPN ayarlarını yapılandırma](../configuration/vpn-settings-ios.md)bölümüne gidin.

Uygulama hedefi:
- iOS

#### <a name="device-features-device-restrictions-and-extension-profiles-for-ios-and-macos-settings-are-shown-by-enrollment-type----4886161-----"></a>İOS ve macOS ayarları için cihaz özellikleri, cihaz kısıtlamaları ve uzantı profilleri kayıt türüne göre gösteriliyor <!-- 4886161   -->

Intune 'da iOS ve macOS cihazları için profiller oluşturursunuz (**cihaz yapılandırma** > **profilleri**@no__t **-3 platform**Için  > **iOS** veya **MacOS** > **cihaz özellikleri**, **cihaz kısıtlamalar**veya profil türü **uzantıları** ). 

Bu güncelleştirmede, Intune portalındaki kullanılabilir ayarlar, uygulanan kayıt türüne göre kategorilere ayrılır:

- iOS
  - Kullanıcı kaydı
  - Cihaz kaydı
  - Otomatik cihaz kaydı (denetimli)
  - Tüm kayıt türleri

- Mac OS
  - Kullanıcı onaylandı
  - Cihaz kaydı
  - Otomatik cihaz kaydı
  - Tüm kayıt türleri

Uygulama hedefi:
- iOS

#### <a name="new-voice-control-settings-for-supervised-ios-devices-running-in-kiosk-mode----4892835-----"></a>Denetimli iOS cihazları için bilgi noktası modunda çalışan yeni ses denetimi ayarları <!-- 4892835   -->
Intune 'da denetimli iOS cihazlarını bir bilgi noktası olarak çalıştırmak için ilkeler oluşturabilir veya adanmış bir cihaz (**cihaz yapılandırma** > **profilleri** >  Platform > cihaz kısıtlamaları Için 5**iOS** @no__t**oluşturun**profil türü > **bilgi noktası**) için. 

Bu güncelleştirmede, denetleyebilmeniz için yeni ayarlar vardır:
- **Ses denetimi**: bilgi noktası modundayken cihazda ses denetimini mümkün.
- **Ses denetimi değişikliği**: kullanıcıların bilgi noktası modundayken cihazdaki ses denetimi ayarını değiştirmesine izin verin.

Geçerli ayarları görmek için [IOS bilgi noktası ayarları](../configuration/device-restrictions-ios.md#kiosk)' na gidin.

Uygulama hedefi:
- iOS 13,0 ve üzeri

#### <a name="use-single-sign-on-for-apps-and-websites-on-your-ios-and-macos-devices----4893175-----"></a>İOS ve macOS cihazlarınızdaki uygulamalar ve Web siteleri için çoklu oturum açma kullanın <!-- 4893175   -->
Bu güncelleştirmede iOS ve macOS cihazları için yeni çoklu oturum açma ayarları vardır (**cihaz yapılandırma** > **profilleri**@no__t **-3 platform**Için  > **iOS** veya **MacOS** > **cihaz özellikleri** profil türü için).

Özellikle de Kerberos kimlik doğrulaması kullanan uygulamalar ve Web siteleri için çoklu oturum açma deneyimi yapılandırmak üzere bu ayarları kullanın. Genel kimlik bilgisi çoklu oturum açma uygulaması uzantısı ve Apple 'ın yerleşik Kerberos uzantısı arasında seçim yapabilirsiniz.

Yapılandırabileceğiniz geçerli cihaz özelliklerini görmek için [iOS cihaz özelliklerine](../configuration/ios-device-features-settings.md) ve [MacOS cihaz özelliklerine](../configuration/macos-device-features-settings.md)gidin.

Uygulama hedefi:
- iOS 13,0 ve üzeri
- macOS 10,15 ve üzeri

#### <a name="associate-domains-to-apps-on-macos-1015-devices----4898079-----"></a>MacOS 10.15 + cihazlarında etki alanlarını uygulamalarla ilişkilendirme <!-- 4898079   -->
MacOS cihazlarında, farklı özellikler yapılandırabilir ve bir ilke kullanarak bu özellikleri cihazlarınıza gönderebilirsiniz (**cihaz yapılandırma** > **profilleri** >  Platform > için**profil oluşturma** > **MacOS**profil türü özellikleri). Bu güncelleştirmede, etki alanlarını uygulamalarınızla ilişkilendirebilirsiniz. Bu özellik, uygulama ile ilgili web siteleriyle kimlik bilgilerinin paylaşılmasını sağlar ve Apple 'ın çoklu oturum açma uzantısı, evrensel bağlantılar ve parola otomatik doldurma ile kullanılabilir. 

Yapılandırabileceğiniz geçerli özellikleri görmek için [Intune 'Da MacOS cihaz özelliği ayarları](../configuration/macos-device-features-settings.md)' na gidin.

Uygulama hedefi:
- macOS 10,15 ve üzeri

#### <a name="use-itunes-and-apps-in-the-itunes-app-store-url-when-showing-or-hiding-apps-on-ios-supervised-devices----4928474-----"></a>İOS denetimli cihazlarda uygulamaları gösterirken veya gizlerken iTunes App Store URL 'sindeki "iTunes" ve "Apps" kullanın <!-- 4928474   --> 
Intune 'da, denetimli iOS cihazlarınızda uygulamaları göstermek veya gizlemek için ilkeler oluşturabilirsiniz (**cihaz yapılandırma** > **profilleri** >  platform için cihaz**oluşturma** > **iOS** > **cihaz kısıtlamaları** profil türü > **uygulamaları göster veya gizle**). 

@No__t-0 gibi iTunes App Store URL 'sini girebilirsiniz. Bu güncelleştirmede, URL 'de `apps` ve `itunes` kullanılabilir:
- `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8`
- `https://apps.apple.com/us/app/work-folders/id950878067?mt=8`

Bu ayarlar hakkında daha fazla bilgi için bkz. [uygulamaları gösterme veya gizleme](../configuration/device-restrictions-ios.md#show-or-hide-apps).

Uygulama hedefi:
- iOS

#### <a name="windows-10-compliance-policy-password-type-values-are-clearer-and-match-csp---5138985---"></a>Windows 10 uyumluluk ilkesi parola türü değerleri daha net ve ile eşleşiyor CSP<!-- 5138985 -->
Windows 10 cihazlarında, belirli parola özellikleri gerektiren bir uyumluluk ilkesi oluşturabilirsiniz (**cihaz uyumluluk** > **ilkeleri** >  Platform > sistemi için**Windows 10 ve üzeri** **ilke oluştur**@no__t  **Güvenlik**). Bu güncelleştirmede:
- **Parola türü** değerleri daha net ve [DeviceLock/alfanümerik ıdevicepasswordrequired CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-alphanumericdevicepasswordrequired)ile eşleşecek şekilde güncelleştirilir.
- **Parola süre sonu (gün)** ayarı 1-730 günden daha fazla değere izin verecek şekilde güncelleştirilir. 

Windows 10 uyumluluk ayarları hakkında daha fazla bilgi için bkz. [Windows 10 ve üzeri ayarları cihazları uyumlu veya uyumsuz olarak işaretleme](../protect/compliance-policy-create-windows.md). 

Uygulama hedefi:
- Windows 10 ve üzeri

 #### <a name="updated-ui-for-configuring-microsoft-exchange-on-premises-access-------4092920---"></a>Microsoft Exchange şirket içi erişimini yapılandırmak için güncelleştirilmiş Kullanıcı arabirimi    <!-- 4092920 -->  
[Microsoft Exchange şirket içi](../protect/conditional-access-exchange-create.md)erişim erişimini yapılandırdığınız konsolu güncelleştirdik. Şirket içi Exchange erişimi için tüm yapılandırmalara artık, *Şirket Içi Exchange erişim denetimini etkinleştirdiğiniz*konsolun aynı bölmesinde erişilebilir.  

#### <a name="allow-or-restrict-adding-app-widgets-to-the-home-screen-on-android-enterprise-work-profile-devices----1109650----"></a>Android kurumsal iş profili cihazlarındaki giriş ekranına uygulama pencere öğelerinin eklenmesine izin ver veya kısıtla <!-- 1109650  --> 
Android kurumsal cihazlarda iş profilindeki (**cihaz yapılandırma** > **profilleri** > **Profil oluştur** > **Android Enterprise** for platform > **yalnızca iş profili >** Profil türü için cihaz kısıtlamaları). Bu güncelleştirmede, kullanıcıların iş profili uygulamaları tarafından sunulan pencere öğelerini cihaz giriş ekranına eklemesine izin verebilirsiniz.

Yapılandırabileceğiniz ayarları görmek için [Android kurumsal cihaz ayarları ' na giderek Intune kullanarak özelliklere izin verin veya kısıtlayın](../configuration/device-restrictions-android-for-work.md).

Uygulama hedefi:
- Android kurumsal iş profili

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="new-tenants-will-default-away-from-android-device-administrator-management----4869790-----"></a>Yeni kiracılar varsayılan olarak Android Cihaz Yöneticisi yönetiminden uzaklaşacaktır <!-- 4869790   -->
Android 'in Cihaz Yöneticisi özellikleri, Android Enterprise tarafından değiştirildi. Bu nedenle, bunun yerine Android Enterprise 'ı yeni kayıtlar için kullanmanızı öneririz. Gelecekteki bir güncelleştirmede, yeni kiracıların Cihaz Yöneticisi yönetimini kullanmak için Android kaydında aşağıdaki önkoşul adımlarını tamamlaması gerekir: **Intune**'a git  > **cihaz kaydı** > **Android kayıt** >  **Cihaz yönetimi ayrıcalıklarına sahip kişisel ve şirkete ait cihazlar** > **cihazları yönetmek için cihaz yöneticisini kullanın**.

Mevcut kiracılar ortamlarında hiçbir değişikliğe karşılaşmayacak. 

Intune 'da Android Cihaz Yöneticisi hakkında daha fazla bilgi için bkz. [Android Cihaz Yöneticisi kaydı](https://docs.microsoft.com/intune/android-enroll-device-administrator).

#### <a name="list-of-dep-devices-associated-with-a-profile----5012045-idmiss---"></a>Bir profille ilişkili DEP cihazlarının listesi <!-- 5012045 idmiss -->
Artık, bir profille ilişkili Apple otomatik Aygıt Kayıt Programı (DEP) cihazlarının sayfalı bir listesini görebilirsiniz. Listede, listedeki herhangi bir sayfadan arama yapabilirsiniz. Listeyi görmek için **ıntune** > **cihaz kaydı** > **Apple kayıt** > **kayıt programı belirteçleri** ' ne gidin > bir belirteç > **profilleri** seçin > bir profil > profili seçin **(** **izleme**altında). 

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Cihaz yönetimi

#### <a name="more-android-fully-managed-support----3464667-4631425-4631440-5227935-4062195-----"></a>Daha fazla Android tam yönetilen desteği <!-- 3464667, 4631425, 4631440, 5227935, 4062195   -->
Android tam olarak yönetilen cihazlar için aşağıdaki desteği ekledik:

- Tam olarak yönetilen Android için SCEP sertifikaları, cihaz sahibi olarak yönetilen cihazlarda sertifika kimlik doğrulaması için kullanılabilir. SCEP sertifikaları Iş profili cihazlarında zaten destekleniyor.  Cihaz sahibi için SCEP sertifikalarıyla şunları yapabilirsiniz: <!-- 5227935 -->
    - Android Enterprise 'ın YAPıLACAKLAR bölümünde SCEP profili oluşturma
    - kimlik doğrulaması için SCEP sertifikalarını Wi-Fi profili için bağlama
    - kimlik doğrulaması için SCEP sertifikalarını VPN profillerine bağlama
    - SCEP sertifikalarını kimlik doğrulaması için e-posta profillerine bağlama (AppConfig aracılığıyla)
- Sistem uygulamaları, Android kurumsal cihazlarda desteklenir. Intune 'da, **istemci uygulamaları** > **uygulamalar** > **Ekle**' yi seçerek bir Android kurumsal sistem uygulaması ekleyin. **Uygulama türü** listesinde, **Android kurumsal sistem uygulaması**' nı seçin. Daha fazla bilgi için bkz. [Microsoft Intune Android kurumsal sistem uygulamaları ekleme](../apps/apps-ae-system.md). <!-- 4062195 -->
- **Cihaz uyumluluğu** > **Android Enterprise** > **cihaz sahibi**' de, Google SafetyNET kanıtlama düzeyini ayarlayan bir uyumluluk ilkesi oluşturabilirsiniz.   <!-- 4631425 -->
- Android kurumsal tam yönetilen cihazlarda, mobil tehdit savunma sağlayıcıları desteklenir. **Cihaz uyumluluğu** > **Android Enterprise** > **cihaz sahibi**' de, kabul edilebilir tehdit düzeyi seçebilirsiniz. <!-- 4631440 --> [Intune kullanarak cihazları uyumlu veya uyumsuz olarak işaretlemek Için Android kurumsal ayarları](../protect/compliance-policy-create-android-for-work.md#device-owner) geçerli ayarları listeler.
- Android kurumsal tam olarak yönetilen cihazlarda, Microsoft başlatıcı uygulaması artık tam olarak yönetilen cihazda standartlaştırılmış bir son kullanıcı deneyimine izin vermek için uygulama koruma ilkeleri aracılığıyla yapılandırılabilir. Microsoft başlatıcısı uygulaması, Android cihazınızı kişiselleştirmek için kullanılabilir. Uygulamayı bir Microsoft hesabı veya iş/okul hesabıyla birlikte kullanarak, kişiselleştirilmiş akışınızdaki takvim, belgeleriniz ve son etkinliklerinize erişebilirsiniz. <!-- 5334044 -->

Bu güncelleştirmeyle, Android kurumsal tam olarak yönetilen Intune desteğinin artık genel kullanıma sunulduğunu duyurmaktan mutluluk duyuyoruz.

Uygulama hedefi:

- Android kurumsal tam yönetilen cihazlar

#### <a name="send-custom-notifications-to-a-single-device-----4928910---"></a>Tek bir cihaza özel bildirimler gönderme  <!-- 4928910 -->
Artık tek bir cihaz seçebilir ve ardından bir uzak cihaz eylemi kullanarak [yalnızca bu cihaza özel bir bildirim gönderebilirsiniz](../remote-actions/custom-notifications.md#send-a-custom-notification-to-a-single-device).

#### <a name="wipe-and-passcode-reset-actions-arent-available-for-ios-devices-that-are-enrolled-by-using-user-enrollment----4950491---"></a>Silme ve geçiş kodu sıfırlama eylemleri, Kullanıcı kaydı kullanılarak kaydedilen iOS cihazları için kullanılamaz <!-- 4950491 -->
Kullanıcı kaydı, yeni bir Apple cihaz kaydı türüdür. Kullanıcı kaydını kullanarak cihazları kaydettiğinizde, bu tür cihazlarda silme ve geçiş kodu sıfırlama uzak eylemleri kullanılamaz.

#### <a name="intune-support-for-ios-13-and-macos-catalina-devices----4665317---"></a>İOS 13 ve macOS Catalina cihazları için Intune desteği <!-- 4665317 -->
Intune artık iOS 13 ve macOS Catalina cihazlarının yönetimini desteklemektedir. Daha fazla bilgi için bkz. [iOS 13 ve ıpados blog gönderisi Microsoft Intune desteği](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Support-for-iOS-13-and-iPadOS/ba-p/861998).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-security"></a>Cihaz güvenliği

#### <a name="bitlocker-support-for-client-driven-recovery-password-rotation-------3444125---"></a>İstemci tabanlı kurtarma parolası dönüşü için BitLocker desteği   <!--  3444125 -->
Windows sürüm 1909 veya üstünü çalıştıran cihazlarda BitLocker için [istemci odaklı kurtarma parolası döndürmeyi](../protect/endpoint-protection-windows-10.md#windows-encryption) yapılandırmak için Intune Endpoint Protection ayarlarını kullanın.

Bu ayar, bir işletim sistemi sürücüsü kurtarmasından (Bootmgr veya WinRE kullanılarak) ve bir sabit veri sürücüsünde kurtarma parolası kilidi açma işleminden sonra istemci temelli kurtarma parolası yenileme işlemini başlatır. Bu ayar, kullanılan belirli kurtarma parolasını yeniler ve birimdeki diğer kullanılmayan parolalar değişmeden kalır. Daha fazla bilgi için bkz. [ConfigureRecoveryPasswordRotation](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp)IÇIN BitLocker CSP belgeleri.

#### <a name="tamper-protection-for-windows-defender-antivirus-----4705448----------"></a>Windows Defender virüsten koruma için yetkisiz koruma  <!-- 4705448        -->
Windows Defender virüsten koruma için yetkisiz *korumayı* yönetmek üzere Intune 'u kullanın. Windows 10 Endpoint Protection için cihaz yapılandırma profillerini kullanırken, Microsoft Defender güvenlik merkezi grubunda, yetkisiz [koruma ayarını](../protect/endpoint-protection-windows-10.md#windows-defender-security-center) bulabilirsiniz. Temper koruma kısıtlamalarını açmak için devre dışı bırakma korumasını etkinleştirmek, devre dışı bırakmak için *devre dışı* bırakmak veya cihazları güncel yapılandırmayı yerinde bırakmak için*yapılandırılmamış* *olarak ayarlamanız* gerekir.  

Daha fazla koruma hakkında daha fazla bilgi için bkz. Windows belgelerindeki [güvenlik ayarlarını önleme korumasıyla](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection) değiştirme. 

#### <a name="advanced-settings-for-windows-defender-firewall-are-now-generally-available-----5317392---------"></a>Windows Defender Güvenlik Duvarı Gelişmiş ayarları artık genel kullanıma sunuldu <!--  5317392       -->  
Cihaz yapılandırma profilinin bir parçası olarak yapılandırdığınız [Endpoint Protection Için Windows Defender özel güvenlik duvarı kuralları](../protect/endpoint-protection-configure.md#add-custom-firewall-rules-for-windows-10-devices)genel önizleme aşamasındadır ve genel olarak KULLANILABILIR (GA).  Uygulamalar, ağ adresleri ve bağlantı noktalarına gelen ve giden davranışı belirtmek için bu kuralları kullanabilirsiniz. Bu kurallar, Temmuz 'da genel önizleme olarak yayımlanmıştır. 

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="role-based-access-control"></a>Rol tabanlı erişim denetimi

#### <a name="scope-tags-now-support-terms-of-use-policies----2358863-idmiss---"></a>Kapsam etiketleri artık kullanım ilkeleri koşullarını destekliyor <!-- 2358863 idmiss -->
Artık kullanım ilkeleri koşullarına [kapsam etiketleri](scope-tags.md) atayabilirsiniz. Bunu yapmak için **ıntune** > **cihaz kaydı** > **hüküm ve koşullara** gidin > listeden bir öğe seçin > **Özellikler** > **kapsam etiketleri** > kapsam etiketi seçin.

## <a name="week-of-september-9-2019"></a>9 Eylül 2019 haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="updates-to-microsoft-intune-app----4997846---"></a>Microsoft Intune uygulama güncelleştirmeleri <!-- 4997846 -->
Android için Microsoft Intune uygulaması aşağıdaki geliştirmelerle güncelleştirilmiştir:
- En önemli eylemler için alt gezinti eklemek üzere Düzen güncelleştirildi ve geliştirildi.
- Kullanıcının profilini gösteren ek bir sayfa eklendi.
- Kullanıcı için, cihaz ayarlarını güncelleştirme ihtiyacı gibi eyleme dönüştürülebilir bildirimlerin görüntüsü eklendi.
- İOS ve Android için Şirket Portalı uygulamasına son eklenen destek ile uygulamayı hizalamak için özel anında iletme bildirimlerinin görüntüsü eklendi. Daha fazla bilgi için bkz. [Intune 'da özel bildirimler gönderme](../remote-actions/custom-notifications.md).

#### <a name="for-ios-devices-customize-the-enrollment-process-privacy-screen-of-the-company-portal----4394993---"></a>İOS cihazları için Şirket Portalı kayıt işlemi gizlilik ekranını özelleştirin <!-- 4394993 -->
Marku kullanarak, son kullanıcıların iOS kaydı sırasında göreceği Şirket Portalı gizlilik ekranını özelleştirebilirsiniz. Özellikle, kuruluşunuzun cihazı göremeyecek veya cihaz üzerinde yapaamayacak işlerin listesini özelleştirebilirsiniz. Daha fazla bilgi için bkz. [Intune şirket portalı uygulamasını yapılandırma](../apps/company-portal-app.md#privacy-statement-customization).


## <a name="week-of-september-2-2019"></a>2 Eylül 2019 haftası

### <a name="monitor-and-troubleshoot"></a>İzleme ve sorun giderme

#### <a name="intune-user-interface-update--tenant-status-dashboard-----5273210----"></a>Intune kullanıcı arabirimi güncelleştirmesi – kiracı durumu panosu  <!-- 5273210  -->
Kiracı durum panosu için Kullanıcı arabirimi, Azure Kullanıcı arabirimi stilleriyle hizalanacak şekilde güncelleştirilmiştir. Daha fazla bilgi için bkz. [kiracı durumu](../tenant-status.md).


## <a name="week-of-august-26-2019"></a>26 Ağustos 2019 haftası

### <a name="configure-microsoft-edge-settings-using-administrative-templates-for-windows-10-and-newer----5228061---"></a>Windows 10 ve üzeri için Yönetim Şablonları kullanarak Microsoft Edge ayarlarını yapılandırma <!-- 5228061 -->

Windows 10 ve daha yeni cihazlarda, Intune 'da Grup İlkesi ayarlarını yapılandırmak için yönetim şablonları oluşturabilirsiniz. Bu güncelleştirmede, Microsoft Edge sürüm 77 ve daha yeni sürümleri için uygulanan ayarları yapılandırabilirsiniz.

Yönetim Şablonları hakkında daha fazla bilgi edinmek için bkz. [Intune 'da Grup İlkesi ayarlarını yapılandırmak Için Windows 10 şablonlarını kullanma](../configuration/administrative-templates-windows.md).

Uygulama hedefi:

- Windows 10 ve üzeri (Windows RS4 +)

## <a name="week-of-august-12-2019"></a>12 Ağustos 2019 haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="control-ios-app-uninstall-behavior-at-device-unenrollment----3504144-----"></a>Cihaz kaydı kaldırılırken iOS uygulaması kaldırma davranışını denetleme <!-- 3504144   -->
Yöneticiler, cihazın bir kullanıcı veya cihaz grubu düzeyinde kaydı kaldırıldığında cihazda bir uygulamanın kaldırılıp kaldırılmadığını veya korunduğunu yönetebilir. 

#### <a name="categorize-microsoft-store-for-business-apps----3926922---"></a>Iş uygulamaları için Microsoft Store kategorilere ayırın <!-- 3926922 -->
Iş uygulamaları için Microsoft Store kategorilere ayırabilirsiniz. Bunu yapmak için **ıntune** > **istemci uygulamalarını** > **uygulamalar** ' ı seçin > bir Microsoft Store iş uygulaması > **uygulama bilgileri** > **kategorisi**seçin. Açılan menüden bir kategori atayın.

#### <a name="customized-notifications-for-microsoft-intune-app-users----4843354----"></a>Microsoft Intune uygulama kullanıcıları için özelleştirilmiş bildirimler <!-- 4843354  -->
Android için Microsoft Intune uygulaması artık özel anında iletme bildirimlerinin görüntülenmesini destekler, bu da iOS ve Android için Şirket Portalı uygulamalarına son eklenen destek ile hizalanmıştır. Daha fazla bilgi için bkz. [Intune 'da özel bildirimler gönderme](../remote-actions/custom-notifications.md).

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="new-features-for-android-enterprise-dedicated-devices-in-multi-app-mode----3755304-3041943-3041946-----"></a>Çok uygulama modundaki Android kurumsal adanmış cihazlar için yeni özellikler <!-- 3755304 3041943 3041946   -->

Intune 'da, Android kurumsal adanmış cihazlarınızda (**cihaz yapılandırma** > **profilleri** > **Profil oluştur** > **Android Enterprise** ) bilgi noktası stili bir deneyimde özellikleri ve ayarları kontrol edebilirsiniz. Platform > **yalnızca cihaz sahibi,** profil türü için cihaz kısıtlamaları).

Bu güncelleştirmede aşağıdaki özellikler ekleniyor:

- **Adanmış cihazlar** > **çoklu uygulama**: **Sanal giriş düğmesi** cihaza çekerek veya ekranda kayan, böylece kullanıcıların taşıyabilmesi için görüntülenebilir.
- **Adanmış cihazlar** > **çoklu uygulama**: **Flashlight Access** kullanıcıların Flashlight kullanmasına izin verir. 
- **Adanmış cihazlar** > **çoklu uygulama**: **medya birimi denetimi** , kullanıcıların bir kaydırıcı kullanarak cihazın medya birimini denetlemesine olanak tanır. 
- **Adanmış cihazlar** > **çoklu uygulama**: **ekran koruyucuyu etkinleştirme**, özel bir görüntü yükleme ve ekran koruyucusuna ne zaman gösterildiğini denetleme.

Geçerli ayarları görmek için [Android kurumsal cihaz ayarları ' na giderek Intune kullanarak özelliklere izin verin veya kısıtlayın](../configuration/device-restrictions-android-for-work.md#dedicated-device-settings).

Uygulama hedefi:

- Android kurumsal adanmış cihazlar

#### <a name="new-app-and-configuration-profiles-for-android-enterprise-fully-managed-devices----3574215-3574238-3574235-3574232-----"></a>Android kurumsal tam olarak yönetilen cihazlar için yeni uygulama ve yapılandırma profilleri <!-- 3574215 3574238 3574235 3574232   -->
Profilleri kullanarak, Android kurumsal cihaz sahibi (tam olarak yönetilen) cihazlarınıza VPN, e-posta ve Wi-Fi ayarlarını uygulayan ayarları yapılandırabilirsiniz. Bu güncelleştirmede şunları yapabilirsiniz:

- Outlook, Gmail ve dokuz Iş e-posta ayarlarını dağıtmak için [uygulama yapılandırma ilkelerini](../apps/app-configuration-policies-use-android.md) kullanın.
- [Güvenilen kök sertifika ayarlarını](../protect/certificates-configure.md)dağıtmak için cihaz yapılandırma profillerini kullanın.
- [VPN](../configuration/vpn-settings-android-enterprise.md) ve [Wi-Fi](../configuration/wi-fi-settings-android-enterprise.md) ayarlarını dağıtmak için cihaz yapılandırma profillerini kullanın.

> [!IMPORTANT]
> Bu özellikle, kullanıcılar VPN, Wi-Fi ve e-posta profilleri için Kullanıcı adı ve parolasıyla kimlik doğrular. Sertifika tabanlı kimlik doğrulaması şu anda kullanılamıyor.

Uygulama hedefi:  
- Android kurumsal cihaz sahibi (tam olarak yönetilen)

#### <a name="control-the-apps-files-documents-and-folders-that-open-when-users-sign-in-to-macos-devices---3914202-----"></a>Kullanıcılar macOS cihazlarında oturum açtıklarında açık olan uygulamaları, dosyaları, belgeleri ve klasörleri denetleyin <!--3914202   -->
MacOS cihazlarındaki özellikleri etkinleştirebilir ve yapılandırabilirsiniz (**cihaz yapılandırma** > **profilleri** >  profil**Oluştur** > **MacOS** for platform > **cihaz özellikleri** profil türü). 

Bu güncelleştirmede, Kullanıcı kayıtlı cihazda oturum açtığında hangi uygulamaların, dosyaların, belgelerin ve klasörlerin açık olduğunu denetleyen yeni bir oturum açma öğeleri ayarı vardır. 

Geçerli ayarları görmek için [Intune 'Da MacOS cihaz özelliği ayarları](../configuration/macos-device-features-settings.md)' na gidin.

Uygulama hedefi:  
- Mac OS

#### <a name="deadlines-replace-engaged-restart-settings-for-windows-update-rings------4464404----------"></a>Son tarihler Windows Update halkalar için bağlı yeniden başlatma ayarlarını değiştirir   <!-- 4464404        -->
Intune ['un Windows 10](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903#servicing)güncelleştirme halkaları, son [tarihleri için ayarları desteklemeye yöneliktir](../protect/windows-update-settings.md). *Son tarihler* , bir cihazın özellik ve güvenlik güncelleştirmelerini ne zaman yükleceğini belirlenir.  Windows 10 1903 veya üzerini çalıştıran cihazlarda, *son tarihleri* , ara *yeniden başlatma*yapılandırmalarının yerini alır.  Gelecekte, *son tarihleri* Windows 10 ' un önceki sürümlerinde de *bağlı yeniden başlatmanın* yerini alır.  

*Son tarihleri*yapılandırma ' ya yönelik cihaz, cihazların ara *yeniden* başlatma ayarlarını kullanmaya devam eder, ancak Intune, gelecekteki bir güncelleştirmede, [ara yeniden başlatma ayarları desteğini kullanımdan kaldırır](whats-new.md#plan-for-change-new-windows-updates-settings-in-intune-) .  

Tüm Windows 10 cihazlarınız için *son tarihleri* kullanmayı planlayın. *Son tarihler* için ayarlar gerçekleştirildikten sonra, Intune yapılandırmalarınızı, ara *yeniden başlatmaya* yönelik olarak yapılandırmak üzere değiştirebilirsiniz. , Yapılandırılmadı olarak ayarlandığında, Intune bu ayarları cihazlarda yönetmeyi bırakır, ancak bu ayarın son yapılandırmasını cihazdan kaldırmaz. Bu nedenle, etkin *yeniden başlatma* için ayarlanan son yapılandırma, bu ayarlar Intune dışında bir yöntem tarafından değiştirilene kadar etkin ve cihazlarda kullanımda kalır. Daha sonra, Windows 'un cihazlar sürümü değiştiğinde ya da *son tarihleri* için Intune desteği cihazların Windows sürümüne genişlediğinde cihaz, zaten yerinde olan yeni ayarları kullanmaya başlayacaktır.

#### <a name="support-for-multiple-microsoft-intune-certificate-connectors--------4704642--------"></a>Birden çok Microsoft Intune sertifika Bağlayıcısı desteği   <!--   4704642      -->
Intune artık, [PKCS işlemleri için birden çok Microsoft Intune sertifika Bağlayıcısı](../protect/certficates-pfx-configure.md)yüklemeyi ve kullanımını desteklemektedir. Bu değişiklik, bağlayıcının yük dengelemesini ve yüksek kullanılabilirliğini destekler. Her bağlayıcı örneği, Intune 'dan gelen sertifika isteklerini işleyebilir.  Bir bağlayıcı kullanılamıyorsa, diğer bağlayıcılar istekleri işlemeye devam eder. 

Birden çok bağlayıcı kullanmak için bağlayıcı yazılımının en son sürümüne yükseltmeniz gerekmez.  

#### <a name="new-settings-and-changes-to-existing-settings-to-restrict-features-on-ios-and-macos-devices----4867699-4867709-----"></a>İOS ve macOS cihazlarındaki özellikleri kısıtlamak için yeni ayarlar ve var olan ayarlarda yapılan değişiklikler <!-- 4867699 4867709   -->
İOS ve macOS çalıştıran cihazlarda ayarları kısıtlamak için profiller oluşturabilirsiniz (**cihaz yapılandırma** > **profilleri** >  platform türü >**cihaz oluşturma** > **iOS** veya **MacOS**  **kısıtlamalar**). Bu güncelleştirme aşağıdaki özellikleri içerir:

- On **macos** > **bulut ve depolama** **@no__t,** kullanıcıların bir MacOS cihazında çalışmayı başlatmasını engellemek için yeni **Iletim** ayarını kullanın ve başka bir MacOS veya iOS cihazında çalışmaya devam edin.

  Geçerli ayarları görmek için, [Intune kullanarak özelliklere izin vermek veya erişimi kısıtlamak üzere MacOS cihaz ayarları](../configuration/device-restrictions-macos.md)' na gidin.

- **İOS** > **cihaz kısıtlamalarında**, bazı değişiklikler vardır:

  - **Yerleşik uygulamalar** > **IPhone 'umu bul (yalnızca denetimli)** : uygulamamı bul özelliğinde bu özelliği engelleyen yeni ayar. 
  - **Yerleşik uygulamalar** > **Arkadaşlarımı bul (yalnızca denetimli)** : uygulamamı bul özelliğinde bu özelliği engelleyen yeni ayar. 
  - **Kablosuz**@no__t-**Wi-Fi durumu değişikliği (yalnızca denetimli)** : kullanıcıların cihazda Wi-Fi ' i açmasını veya kapatmasını engelleyen yeni ayar.
  - **Klavye ve sözlük** > **hızlı yol (yalnızca denetimli)** : QuickPath özelliğini engelleyen yeni ayar.
  - **Bulut ve depolama**: **etkinlik devamlılığı** iletime olarak yeniden **adlandırıldı.**

  Geçerli ayarları görmek için [iOS cihaz ayarları ' na giderek Intune kullanarak özelliklere izin verin veya kısıtlayın](../configuration/device-restrictions-ios.md).

Uygulama hedefi:  
- macOS 10,15 ve üzeri
- iOS 13 ve üzeri

#### <a name="some-unsupervised-ios-device-restrictions-will-become-supervised-only-with-the-ios-130-release----4867809-----"></a>Denetlenmeyecek bazı iOS cihaz kısıtlamaları yalnızca iOS 13,0 sürümüyle denetimli olacak. <!-- 4867809   -->
Bu güncelleştirmede, bazı ayarlar iOS 13,0 sürümü ile yalnızca denetimli cihazlar için geçerlidir. Bu ayarlar yapılandırıldıysa ve iOS 13,0 sürümünden önce denetlenmeden önce cihazlara atanırsa, ayarlar hala bu denetlenmeden bu cihazlara uygulanır. Cihazlar iOS 13,0 ' e yükseltildikten sonra da hala geçerlidir. Bu kısıtlamalar, yedeklenen ve geri yüklenen denetimli cihazlarda kaldırılır. 

Bu ayarlar şunlardır:

- Uygulama Mağazası, Belge Görüntüleme, Oyun
  - Uygulama mağazası
  - Açık iTunes, müzik, podcast veya News içeriği
  - Game Center arkadaş ekleme
  - Çok oyunculu oyun
- Yerleşik Uygulamalar
  - Kamera
    - FaceTime
  - Safari
    - İse
- Bulut ve Depolama
  - İCloud 'a yedekleme
  - İCloud Belge eşitlemesini engelle
  - İCloud Anahtarlık eşitlemesini engelle

Geçerli ayarları görmek için [iOS cihaz ayarları ' na giderek Intune kullanarak özelliklere izin verin veya kısıtlayın](../configuration/device-restrictions-ios.md).

Uygulama hedefi:  
- iOS 13,0 ve üzeri

#### <a name="improved-device-status-for-macos-filevault-encryption-----4944983-----------"></a>MacOS Filekasası şifrelemesi için iyileştirilmiş cihaz durumu  <!-- 4944983         -->
MacOS cihazlarında dosya Kasası şifrelemesi için birçok [cihaz durumu iletisini](../protect/encryption-monitor.md#device-encryption-status) güncelleştirdik.

#### <a name="some-windows-defender-antivirus-scan-settings-in-the-reporting-show-a-failed-status----5119229---"></a>Raporlamadaki bazı Windows Defender virüsten koruma tarama ayarları başarısız durumu gösteriyor <!-- 5119229 -->
Intune 'da Windows 10 cihazlarınızı (**cihaz yapılandırma** > **profilleri**@no__t **-3 platform**için  > **Windows 10 ve üzeri** ) taramak üzere windows Defender virüsten koruma kullanmak üzere ilkeler oluşturabilirsiniz > **Windows Defender virüsten koruma**> profil türü için cihaz kısıtlamaları. **Günlük hızlı tarama gerçekleştirme süresi** ve raporlama **gerçekleştirmek Için sistem taraması türü** , aslında başarılı bir durum olduğunda başarısız durumu gösterir. 

Bu güncelleştirmede, bu davranış düzeltilmiştir. Bu nedenle, ayarları gerçekleştirmek için **günlük hızlı tarama** ve **sistem taraması türü** , taramalar başarıyla tamamlandığında başarı durumunu gösterir ve ayarlar uygulanamadığında başarısız bir durum gösterir. 

Windows Defender virüsten koruma ayarları hakkında daha fazla bilgi için bkz. [Windows 10 (ve daha yeni) cihaz ayarları Intune kullanarak özellik sağlamak veya kısıtlamak için](../configuration/device-restrictions-windows-10.md#microsoft-defender-antivirus). 

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="default-scope-tags----3702875----"></a>Varsayılan kapsam etiketleri <!-- 3702875  -->
Yeni bir yerleşik varsayılan kapsam etiketi artık kullanılabilir. Kapsam etiketlerini destekleyen tüm etiketli Intune nesneleri varsayılan kapsam etiketine otomatik olarak atanır. **Varsayılan** kapsam etiketi, günümüzde yönetici deneyimiyle eşliği sağlamak için mevcut tüm rol atamalarına eklenir. Yöneticinin varsayılan kapsam etiketiyle Intune nesnelerini görmesini istemiyorsanız, varsayılan kapsam etiketini rol atamasından kaldırın. Bu özellik, System Center Configuration Manager güvenlik kapsamları özelliğine benzer. Daha fazla bilgi için bkz. [Dağıtılmış BT IÇIN RBAC ve kapsam etiketlerini kullanma](scope-tags.md).

#### <a name="android-enrollment-device-administrator-support----4869749-----"></a>Android kayıt cihazı yöneticisi desteği <!-- 4869749   -->
Android Cihaz Yöneticisi kayıt seçeneği, Android kayıt sayfasına eklendi (**ıntune** > **cihaz kaydı** > **Android kaydı**). Android Cihaz Yöneticisi, tüm kiracılar için varsayılan olarak hala etkinleştirilecek.  Daha fazla bilgi için bkz. [Android Cihaz Yöneticisi kaydı](../enrollment/android-enroll-device-administrator.md).

#### <a name="skip-more-screens-in-setup-assistant---4877451----"></a>Kurulum Yardımcısı 'nda daha fazla ekran atlayın <!--4877451  -->
Aşağıdaki Kurulum Yardımcısı ekranlarını atlamak için Aygıt Kayıt Programı profilleri ayarlayabilirsiniz:
- iOS için
    - Görünümünde
    - Hızlı dil
    - Tercih edilen dil
    - Cihazdan cihaza geçişe
- MacOS için
    - Ekran zamanı
    - Dokunma KIMLIĞI kurulumu

Kurulum Yardımcısı özelleştirmesi hakkında daha fazla bilgi için bkz. [iOS Için Apple kayıt profili oluşturma](../enrollment/device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile) ve [MacOS için Apple kayıt profili oluşturma ](../enrollment/device-enrollment-program-enroll-macos.md#create-an-apple-enrollment-profile).

#### <a name="add-a-user-column-to-the-autopilot-device-csv-upload-process----3823054---"></a>Autopilot Device CSV yükleme işlemine bir kullanıcı sütunu ekleyin <!-- 3823054 -->
Artık Autopilot cihazlara CSV yüklemesine bir kullanıcı sütunu ekleyebilirsiniz. Bu, CSV 'yi içeri aktarırken kullanıcıları toplu olarak atayabilmenizi sağlar. Daha fazla bilgi için bkz. [Windows Autopilot kullanarak Intune 'Da Windows cihazlarını kaydetme](../enrollment/enrollment-autopilot.md).


### <a name="device-management"></a>Cihaz yönetimi

#### <a name="configure-automatic-device-clean-up-time-limit-down-to-30-days---4231059----"></a>Otomatik cihaz temizleme süresi limitini 30 güne kadar yapılandırma <!--4231059  -->
Otomatik cihaz temizleme süresi sınırını, son oturum açma işleminden sonra 30 gün (önceki 90 gün yerine) kadar kısa bir süre sonra ayarlayabilirsiniz. Bunu yapmak için **ıntune** > **cihazlara** > **Kurulum** > **cihaz temizleme kuralları**' na gidin.

#### <a name="build-number-included-on-android-device-hardware-page----4461910-----"></a>Android cihaz donanımı sayfasına dahil edilen derleme numarası <!-- 4461910   -->
Her Android cihazının donanım sayfasında yeni bir giriş, cihazın işletim sistemi yapı numarasını içerir. Daha fazla bilgi için bkz. [Intune 'da cihaz ayrıntılarını görüntüleme](../remote-actions/device-inventory.md).


<!-- ########################## -->

## <a name="week-of-august-5-2019"></a>5 Ağustos 2019 haftası

### <a name="zebra-technologies-is-a-supported-oem-for-oemconfig-on-android-enterprise-devices-----4843713---"></a>Zeköşeli teknolojiler, Android kurumsal cihazlarda OEMConfig için desteklenen bir OEM 'dir  <!-- 4843713 -->

Intune 'da, cihaz yapılandırma profilleri oluşturabilir ve OEMConfig kullanarak Android kurumsal cihazlara ayarlar uygulayabilirsiniz (**cihaz yapılandırma** > **profilleri** > **Profil oluştur** > **Android Enterprise** Platform > için **Oemconfig** for profile yazın).

Bu güncelleştirmede, Zeköşeli teknolojiler, OEMConfig için desteklenen bir özgün ekipman üreticisi (OEM). OEMConfig hakkında daha fazla bilgi için bkz. [oemconfig Ile Android kurumsal cihazlarını kullanma ve yönetme](../configuration/android-oem-configuration-overview.md).

Uygulama hedefi:  
- Android kurumsal

<!-- ########################## -->

## <a name="week-of-july-22-2019"></a>22 Temmuz 2019 haftası 

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="customized-notifications-for-users-and-groups-------16766574------------"></a>Kullanıcılar ve gruplar için özelleştirilmiş bildirimler    <!-- 16766574          -->
Intune ile yönettiğiniz iOS ve Android cihazlarda kullanıcılara Şirket Portalı uygulamadan özel anında iletme bildirimleri gönderin. Bu mobil anında iletme bildirimleri, ücretsiz metinle yüksek düzeyde özelleştirilebilir ve herhangi bir amaçla kullanılabilir. Bunları kuruluşunuzdaki farklı Kullanıcı gruplarına hedefleyebilirsiniz. Daha fazla bilgi için bkz. [özel bildirimler](../remote-actions/custom-notifications.md).

#### <a name="googles-device-policy-controller-app----3041950----"></a>Google 'ın cihaz Ilkesi denetleyicisi uygulaması <!-- 3041950  -->
Yönetilen giriş ekranı uygulaması artık Google 'ın Android cihaz Ilkesi uygulamasına erişim sağlar. Yönetilen giriş ekranı uygulaması, Intune 'A kayıtlı cihazlar için çok uygulama bilgi noktası modunu kullanan Android kurumsal (AE) adanmış cihazlar olarak kullanılan özel bir başlatıdır. Android cihaz Ilkesi uygulamasına erişebilir veya destek ve hata ayıklama amacıyla kullanıcılara Android cihaz Ilkesi uygulamasına rehberlik edebilirsiniz. Bu başlatma özelliği, cihazın ne zaman kaydolur ve yönetilen giriş ekranına kilitlediği sırada kullanılabilir. Bu işlevselliği kullanmak için ek yükleme gerekmez.

#### <a name="outlook-protection-settings-for-ios-and-android-devices----3212619---"></a>İOS ve Android cihazlar için Outlook koruması ayarları <!-- 3212619 -->
Artık, cihaz kaydı olmadan basit Intune yönetici denetimlerini kullanarak iOS ve Android için Outlook için hem genel uygulama hem de veri koruma yapılandırma ayarlarını yapılandırabilirsiniz. Genel uygulama yapılandırma ayarları, yöneticilerin iOS ve Android 'e kayıtlı cihazlarda Outlook 'U yönetirken Etkinleştirebileceği ayarlar ile eşlik sağlar. Outlook ayarları hakkında daha fazla bilgi için bkz. [iOS ve Android Için Outlook dağıtımı yapılandırma ayarları](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-configuration-with-microsoft-intune).

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910-eeready---idstaged---"></a>Windows 10 cihaz yapılandırma profilleri oluştururken "uygulanabilirlik kuralları" nı kullanın <!-- 2549910 eeready   idstaged -->

Windows 10 cihaz yapılandırma profilleri (**cihaz yapılandırma** > **profilleri** > **Profil oluştur** >  Platform > **uygulanabilirlik kuralları**için**Windows 10** ) oluşturursunuz. Bu güncelleştirmede, profil yalnızca belirli bir sürüm veya belirli bir sürüm için geçerli olacak şekilde bir **uygulanabilirlik kuralı** oluşturabilirsiniz. Örneğin, bazı BitLocker ayarlarını sağlayan bir profil oluşturursunuz. Profili ekledikten sonra, profilin yalnızca Windows 10 Enterprise çalıştıran cihazlara uygulanması için bir uygulanabilirlik kuralı kullanın.

Bir uygulanabilirlik kuralı eklemek için bkz. [uygulanabilirlik kuralları](../configuration/device-profile-create.md#applicability-rules).

Şunlar için geçerlidir: Windows 10 ve üzeri

#### <a name="use-tokens-to-add-device-specific-information-in-custom-profiles-for-ios-and-macos-devices----3330008----"></a>İOS ve macOS cihazları için özel profillere cihaza özgü bilgileri eklemek için belirteçleri kullanın <!-- 3330008  -->
İOS ve macOS cihazlarında özel profilleri, Intune 'da yerleşik olmayan ayarları ve özellikleri yapılandırmak için kullanabilirsiniz (**cihaz yapılandırma** > **profilleri** > **Create profile** > **iOS** veya **MacOS** for platform Profil türü için **özel** >). Bu güncelleştirmede, cihaza özgü bilgileri eklemek için `.mobileconfig` dosyalarınıza belirteçler ekleyebilirsiniz. Örneğin, cihazın seri numarasını göstermek için yapılandırma dosyanıza `Serial Number: {{serialnumber}}` ekleyebilirsiniz.

Özel bir profil oluşturmak için bkz. [iOS özel ayarları](../configuration/custom-settings-ios.md) veya [MacOS özel ayarları](../configuration/custom-settings-macos.md).

Uygulama hedefi:
- iOS
- Mac OS

#### <a name="new-configuration-designer-when-creating-an-oemconfig-profile-for-android-enterprise----3712769-----"></a>Android Enterprise için bir OEMConfig profili oluştururken yeni yapılandırma Tasarımcısı <!-- 3712769   -->
Intune 'da, bir OEMConfig uygulaması kullanan bir cihaz yapılandırma profili oluşturabilirsiniz (cihaz yapılandırma > profilleri > > SDK için Android Enterprise > profil türü için OEMConfig). Bunu yaptığınızda bir JSON Düzenleyicisi, değiştirmeniz için bir şablon ve değerlerle açılır. 

Bu güncelleştirme; başlıklar, açıklamalar ve daha fazlası dahil olmak üzere uygulamada Embedded ayrıntıları gösteren gelişmiş bir kullanıcı deneyimine sahip bir yapılandırma Tasarımcısı içerir. JSON Düzenleyicisi hala kullanılabilir ve yapılandırma tasarımcısında yaptığınız tüm değişiklikleri gösterir.

Geçerli ayarları görmek için, bkz. [OEMConfig Ile Android kurumsal cihazlarını kullanma ve yönetme](../configuration/android-oem-configuration-overview.md).

Uygulama hedefi: Android Enterprise

#### <a name="updated-ui-for-configuring-windows-hello-----4089576--------------"></a>Windows Hello 'Yu yapılandırmak için güncelleştirilmiş Kullanıcı arabirimi  <!-- 4089576            -->
[Intune 'U iş Için Windows Hello 'yu kullanacak şekilde yapılandırdığınız](../protect/windows-hello.md)konsolu güncelleştirdik. Tüm yapılandırma ayarları artık konsolun Windows Hello desteğini etkinleştirdiğiniz bölmesinde de mevcuttur. 


#### <a name="intune-powershell-sdk----4924113---"></a>Intune PowerShell SDK 'Sı <!-- 4924113 --> 
Intune API 'SI için Microsoft Graph aracılığıyla destek sağlayan Intune PowerShell SDK, 6.1907.1.0 sürümüne güncelleştirilmiştir. SDK artık şunları desteklemektedir:
- Azure Otomasyonu ile birlikte kullanılır.
- Yalnızca uygulama kimlik doğrulama okuma işlemlerini destekler. 
- Kolay kısaltılmış adları diğer ad olarak destekler.
- PowerShell adlandırma kurallarına uyar. Özellikle, `PSCredential` parametresi (`Connect-MSGraph` cmdlet 'inde) `Credential` olarak yeniden adlandırıldı.
- @No__t-1 cmdlet 'i kullanılırken `Content-Type` üst bilgisinin değerini el ile belirtmeyi destekler.

Daha fazla bilgi için bkz. [Microsoft Intune Graph API Için POWERSHELL SDK](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune).


### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="updates-for-enrollment-restrictions-----2871968---"></a>Kayıt kısıtlamaları için güncelleştirmeler  <!-- 2871968 -->
Yeni kiracılar için kayıt kısıtlamaları, Android kurumsal iş profillerinin varsayılan olarak izin verdiği şekilde güncelleştirilmiştir. Mevcut kiracılar hiçbir değişikliğe karşı karşılaşacaktır. Android kurumsal iş profillerini kullanmak için yine de [Intune hesabınızı yönetilen Google Play hesabınıza bağlamanız](../enrollment/connect-intune-android-enterprise.md)gerekir.

#### <a name="ui-updates-for-apple-enrollment-and-enrollment-restrictions---4089575-4089579----"></a>Apple kaydı ve kayıt kısıtlamaları için Kullanıcı Arabirimi güncelleştirmeleri <!--4089575, 4089579  -->
Aşağıdaki işlemlerin her ikisi de bir sihirbaz stili Kullanıcı arabirimi kullanır:
- Apple cihaz kaydı. Daha fazla bilgi için bkz. [Apple aygıt kayıt programı iOS cihazlarını otomatik olarak kaydetme](../enrollment/device-enrollment-program-enroll-ios.md).
- Kayıt kısıtlaması oluşturma. Daha fazla bilgi için bkz. [kayıt kısıtlamalarını ayarlama](../enrollment/enrollment-restrictions-set.md).

#### <a name="handling-pre-configuration-of-corporate-device-identifiers-for-android-q-devices----4711509--idmiss---"></a>Android Q cihazları için kurumsal cihaz tanımlayıcılarının ön yapılandırmasını işleme <!-- 4711509  idmiss -->
Android soru-cevap (ile v10 arasındaki) içinde, Google, eski yönetilen (Cihaz Yöneticisi) Android cihazlarındaki MDM aracılarının cihaz tanımlayıcı bilgilerini toplamasını sağlayacak özelliği kaldırır.  Intune, BT yöneticilerinin bu cihazları şirkete ait olarak otomatik olarak etiketleyebilmesi için [cihaz seri numaralarının bir listesini önceden yapılandırmasını](../enrollment/corporate-identifiers-add.md#identify-corporate-owned-devices-with-imei-or-serial-number) sağlayan bir özelliğe sahiptir. Bu özellik cihaz yöneticisi tarafından yönetilen Android Q cihazları için çalışmaz.  Cihazın seri numarası veya ıMEı 'nin karşıya yüklenip yüklenmediğine bakılmaksızın, Intune kaydı sırasında her zaman kişisel olduğu kabul edilir.  Kayıt işleminden sonra sahipliğini el ile şirkete geçirebilirsiniz.  Bu yalnızca yeni kayıtları etkiler ve mevcut kayıtlı cihazlar etkilenmez.  İş profilleriyle yönetilen Android cihazları bu değişiklikten etkilenmez ve bugün olduğu gibi çalışmaya devam edecektir.  Buna ek olarak, cihaz yöneticisi olarak kaydedilen Android Q cihazları artık Intune konsolundaki seri numarasını veya ıMEı 'yi cihaz özellikleri olarak bildiremeyecektir.

#### <a name="icons-have-changed-for-android-enterprise-enrollments-work-profile-dedicated-devices-and-fully-managed-devices----4977730---"></a>Android kurumsal kayıtları (iş profili, adanmış cihazlar ve tam olarak yönetilen cihazlar) için simgeler değiştirilmiştir <!-- 4977730 -->
Android kurumsal kayıt profillerinin simgeleri değişmiştir. Yeni simgeleri görmek için **ıntune** > **kayıt** > **Android kayıt** > **kayıt profilleri**bölümüne bakın.


#### <a name="windows-diagnostic-data-collection-change----4113859---"></a>Windows tanılama veri koleksiyonu değişikliği <!-- 4113859 -->
Windows 10, sürüm 1903 ve üzeri sürümleri çalıştıran cihazlarda tanılama veri toplama için varsayılan değer değişmiştir. Windows 10 1903 ile başlayarak, tanılama veri toplama varsayılan olarak etkindir. Windows Tanılama verileri, Windows cihazlarından, cihaz ve Windows ile ilgili yazılımların nasıl çalıştığı hakkında önemli teknik verilere sahiptir. Daha fazla bilgi için bkz. [Kuruluşunuzda Windows tanılama verilerini yapılandırma](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization). Autopilot cihazlar, aksi durumda [System/Allowtelemetri](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry)ile Autopilot profilinde ayarlanmamışsa, "tam" telemetrisine de sahiptir.

### <a name="device-management"></a>Cihaz yönetimi

#### <a name="improve-device-location---3855417----"></a>Cihaz konumunu iyileştirme<!-- 3855417  -->
**Cihazı bul** eylemini kullanarak bir cihazın tam koordinatlarıyla yakınlaştırma yapabilirsiniz. Kayıp iOS cihazlarını bulma hakkında daha fazla bilgi için bkz. [kayıp iOS cihazlarını bulma](../remote-actions/device-locate.md).


### <a name="device-security"></a>Cihaz güvenliği

#### <a name="advanced-settings-for-windows-defender-firewall--public-preview------1311949-------"></a>Windows Defender güvenlik duvarı için Gelişmiş ayarlar (Genel Önizleme)  <!--  1311949     -->  
Windows 10 ' da Endpoint Protection için [cihaz yapılandırma profilinin bir parçası olarak özel güvenlik duvarı kurallarını](../protect/endpoint-protection-configure.md#add-custom-firewall-rules-for-windows-10-devices) yönetmek Için Intune 'u kullanın. Kurallar, uygulamalar, ağ adresleri ve bağlantı noktaları için gelen ve giden davranışı belirtebilir. 

#### <a name="updated-ui-for-managing-security-baselines------4091125-------"></a>Güvenlik temellerini yönetmek için güncelleştirilmiş Kullanıcı arabirimi   <!-- 4091125     -->
Güvenlik temellerimiz için Intune konsolundaki [oluşturma ve düzenleme deneyimini](../protect/security-baselines.md#create-the-profile) güncelleştirdik. Değişiklikler şunları içerir:

Tek bir dikey pencereye daraltılmış daha basit bir sihirbaz stili biçimi. bir dikey pencere içinde. Bu yeni tasarım, BT uzmanlarının birkaç ayrı bölmeye detaya gitmeyi gerektiren dikey pencere genişlemesine.  
Artık, temelleri atamak için daha sonra dönmek zorunda kalmak yerine oluşturma ve düzenleme deneyiminin bir parçası olarak atamalar oluşturabilirsiniz. Yeni bir taban çizgisi oluşturmadan ve mevcut bir temeli düzenlediğinizde, görüntüleyebileceğiniz ayarların bir özetini ekledik. Düzenleme sırasında, Özet yalnızca düzenlenmekte olan özelliklerin bir kategorisi içinde ayarlanan öğelerin listesini gösterir.



<!-- ########################## -->

## <a name="week-of-july-15-2019"></a>15 Temmuz 2019 haftası 

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="managed-home-screen-and-managed-settings-icons----4918107---"></a>Yönetilen giriş ekranı ve yönetilen ayarlar simgeleri <!-- 4918107 -->
Yönetilen giriş ekranı uygulaması simgesi ve **yönetilen ayarlar** simgesi güncelleştirildi. Yönetilen giriş ekranı uygulaması yalnızca Intune 'A Android kurumsal (AE) adanmış cihazlar olarak kaydedilmiş ve çok uygulama bilgi noktası modunda çalışan cihazlar tarafından kullanılır. Yönetilen giriş ekranı uygulaması hakkında daha fazla bilgi için bkz. [Android Enterprise Için Microsoft yönetilen giriş ekranı uygulamasını yapılandırma](../apps/app-configuration-managed-home-screen-app.md).

#### <a name="android-device-policy-on-android-enterprise-dedicated-devices----4918136---"></a>Android kurumsal adanmış cihazlarda Android cihaz Ilkesi <!-- 4918136 -->
Android cihaz Ilkesi uygulamasına, yönetilen giriş ekranı uygulamasının hata ayıklama ekranından erişebilirsiniz. Yönetilen giriş ekranı uygulaması yalnızca Intune 'A Android kurumsal (AE) adanmış cihazlar olarak kaydedilmiş ve çok uygulama bilgi noktası modunda çalışan cihazlar tarafından kullanılır. Daha fazla bilgi için bkz. [Android Enterprise Için Microsoft yönetilen giriş ekranı uygulamasını yapılandırma](../apps/app-configuration-managed-home-screen-app.md).

#### <a name="ios-company-portal-updates----3902931---"></a>iOS Şirket Portalı güncelleştirmeleri <!-- 3902931 -->
İOS uygulama yönetimi istemlerinde şirketinizin adı, geçerli "i.manage.microsoft.com" metninin yerini alır. Örneğin, kullanıcılar Şirket Portalı bir iOS uygulaması yüklemeye çalıştıklarında veya kullanıcılar uygulamanın yönetimine izin vereceği zaman, kullanıcılar şirket adını "i.manage.microsoft.com" yerine görür. Bu, önümüzdeki birkaç gün içinde tüm müşterilere alınacaktır.

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="manage-filevault-for-macos-------3858502--4557986--1210104----"></a>MacOS için dosya kasasını yönetme   <!--  3858502 + 4557986 + 1210104  -->
[MacOS cihazları Için dosya Kasası anahtar şifrelemesini yönetmek](../protect/encrypt-devices.md)üzere Intune 'u kullanabilirsiniz. Cihazları şifrelemek için bir Endpoint Protection cihaz yapılandırma profili kullanırsınız.

Dosya Kasası desteğiniz şifrelenmemiş cihazları şifreleme, bir cihaz kişisel kurtarma anahtarı, kişisel şifreleme anahtarlarının otomatik veya el ile dönüşü ve şirket cihazlarınız için anahtar alımı içerir. Son kullanıcılar, şifreli cihazlarına kişisel kurtarma anahtarını almak için Şirket Portalı Web sitesini de kullanabilir. 

Ayrıca, tüm cihaz şifreleme ayrıntılarınızı tek bir yerde görüntüleyebilmeniz için, şifreleme raporunu BitLocker 'a yönelik dosya tarafı bilgileri [hakkında bilgi](../protect/encryption-monitor.md) içerecek şekilde genişlettik. 

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="windows-autopilot-reset-removes-the-devices-primary-user----4156123---"></a>Windows Autopilot sıfırlaması cihazın birincil kullanıcısını kaldırır <!-- 4156123 -->
Bir cihazda Autopilot Reset kullanıldığında, cihazın birincil kullanıcısı kaldırılır. Sıfırlamadan sonra oturum açan bir sonraki Kullanıcı, birincil kullanıcı olarak ayarlanır. Bu özellik önümüzdeki birkaç gün içinde tüm müşterilere alınacaktır.

## <a name="week-of-july-8-2019"></a>8 Temmuz 2019 haftası

### <a name="new-office-windows-and-onedrive-settings-in-windows-10-administrative-templates----3510695---"></a>Windows 10 Yönetim şablonlarında yeni Office, Windows ve OneDrive ayarları <!-- 3510695 -->

Intune 'da şirket içi Grup İlkesi yönetimini taklit eden Yönetim şablonları oluşturabilirsiniz (**cihaz yönetimi** > **profilleri** >  platform Için  > **Windows 10 ve üzeri bir sürüm** **oluşturun**>Profil türü için yönetim şablonu).

Bu güncelleştirme, şablonlarınıza ekleyebileceğiniz diğer Office, Windows ve OneDrive ayarlarını içerir. Bu yeni ayarlarla artık% 100 bulut tabanlı 2500 ' den fazla ayarı yapılandırabilirsiniz.

Bu özellik hakkında daha fazla bilgi edinmek için bkz. [Intune 'da Grup İlkesi ayarlarını yapılandırmak Için Windows 10 şablonlarını kullanma](../configuration/administrative-templates-windows.md).

Şunlar için geçerlidir: Windows 10 ve üzeri

## <a name="week-of-july-1-2019"></a>1 Temmuz 2019 haftası 

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="aad-and-app-on-android-enterprise-devices----3574267---"></a>Android kurumsal cihazlarda AAD ve uygulama <!-- 3574267 -->
Tam olarak yönetilen Android Kurumsal cihazları eklerken, kullanıcılar yeni veya fabrika sıfırlaması cihazının ilk kurulumu sırasında artık Azure Active Directory (AAD) ile kaydolacaktır. Daha önce tam olarak yönetilen bir cihaz için, Kurulum tamamlandıktan sonra kullanıcının AAD kaydını başlatmak üzere Microsoft Intune uygulamasını el ile başlatması gerekiyordu. Artık Kullanıcı İlk kurulumdan sonra cihaz giriş sayfasına kaydolduğunda, cihazın kaydı kaydedilir ve kaydedilir.

AAD güncelleştirmelerine ek olarak, Intune uygulama koruma ilkeleri (uygulama) artık tam olarak yönetilen Android kurumsal cihazlarda desteklenmektedir. Bu işlev, geliştirdiğimiz için kullanılabilir hale gelir. Daha fazla bilgi için bkz. [Intune Ile Android Enterprise cihazlarına yönetilen Google Play uygulamaları ekleme](../apps/apps-add-android-for-work.md).

## <a name="week-of-june-24-2019"></a>24 Haziran 2019 haftası 

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="configure-which-browser-is-allowed-to-link-to-organization-data----3145939---"></a>Hangi tarayıcının kuruluş verilerine bağlantı yapmasına izin verileceğini yapılandırın <!-- 3145939 -->
Android ve iOS cihazlarında Intune Uygulama Koruması Ilkeleri (uygulama) artık Intune Managed Browser veya Microsoft Edge 'in ötesinde belirli bir tarayıcıya kuruluş web bağlantıları aktarmanızı sağlar.  UYGULAMA hakkında daha fazla bilgi için bkz. [Uygulama koruma ilkeleri nelerdir?](../apps/app-protection-policy.md).

#### <a name="all-apps-page-identifies-onlineoffline-microsoft-store-for-business-apps--4089647---"></a>Tüm uygulamalar sayfası Iş uygulamaları için çevrimiçi/çevrimdışı Microsoft Store tanımlar<!--4089647 -->
**Tüm uygulamalar** sayfası artık çevrimiçi veya çevrimdışı uygulamalar olarak Microsoft Store for Business (msfb) uygulamalarını belirlemek için etiketleme içerir. Her bir MSFB uygulaması artık **çevrimiçi** veya **çevrimdışı**için bir sonek içeriyor. Uygulama Ayrıntıları sayfası, **lisans türünü** de içerir ve **cihaz bağlamı yüklemeyi destekler** (yalnızca çevrimdışı lisanslı uygulamalar) bilgileri de vardır.

#### <a name="company-portal-app-on-windows-shared-devices---4393553---"></a>Windows paylaşılan cihazlarında uygulama Şirket Portalı <!--4393553 -->
Kullanıcılar artık Windows paylaşılan cihazlarındaki Şirket Portalı uygulamasına erişebilir. Son kullanıcılar cihaz kutucuğunda **paylaşılan** bir etiket görür. Bu, Windows Şirket Portalı App sürümü 10.3.45609.0 ve üzeri için geçerlidir.

#### <a name="view-all-installed-apps-from-new-company-portal-web-page----4224326---"></a>Yeni Şirket Portalı Web sayfasından yüklü tüm uygulamaları görüntüle <!-- 4224326 -->
Şirket Portalı Web sitesinin yeni **yüklü uygulamalar** sayfasında, bir kullanıcının cihazlarında yüklü olan tüm yönetilen uygulamalar (hem gerekli hem de kullanılabilir) listelenir. Atama türüne ek olarak, kullanıcılar uygulamanın yayımcısını, yayımlanma tarihini ve geçerli yükleme durumunu görebilirler. Kullanıcılarınız için gerekli veya kullanılabilir bir uygulama yapmadıysanız, hiçbir şirket uygulaması yüklenmediğini açıklayan bir ileti görür. Web 'deki yeni sayfayı görmek için [Şirket portalı Web sitesine](https://portal.manage.microsoft.com) gidin ve **yüklü uygulamalar**' a tıklayın.  

#### <a name="new-view-lets-app-users-see-all-managed-apps-installed-on-device----2352913---"></a>Yeni görünüm, uygulama kullanıcılarının cihazda yüklü olan tüm yönetilen uygulamaları görmesini sağlar <!-- 2352913 -->  
Windows için Şirket Portalı uygulaması artık bir kullanıcının cihazında yüklü olan tüm yönetilen uygulamaları (hem gerekli hem de kullanılabilir) listeler. Kullanıcılar ayrıca, denenen ve bekleyen uygulama yüklemelerini ve bunların geçerli durumlarını görebilir. Kullanıcılarınız için gerekli olan veya kullanıcılarınızın kullanabildiği uygulamalar yapmadıysanız, hiçbir şirket uygulaması yüklenmediğini açıklayan bir ileti görür. Yeni görünümü görmek için Şirket Portalı gezinti bölmesine gidin ve **uygulamalar** > **yüklü uygulamalar**' ı seçin.    

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="configure-settings-for-kernel-extensions-on-macos-devices----2043024---"></a>MacOS cihazlarında çekirdek uzantıları ayarlarını yapılandırma <!-- 2043024 -->
MacOS cihazlarında, bir cihaz yapılandırma profili (**cihaz yapılandırma** > **profilleri** > **Profil oluştur** > Platform için **MacOS** seçin) oluşturabilirsiniz. Bu güncelleştirme, cihazlarınız üzerinde çekirdek uzantıları yapılandırmanıza ve kullanmanıza olanak sağlayan yeni bir ayar grubu içerir. Belirli uzantıları ekleyebilir veya belirli bir iş ortağının veya geliştiriciden tüm uzantılara izin verebilirsiniz.

Bu özellik hakkında daha fazla bilgi edinmek için bkz. [çekirdek uzantılarına genel bakış](../configuration/kernel-extensions-overview-macos.md) ve [çekirdek uzantısı ayarları](../configuration/kernel-extensions-settings-macos.md).

Uygulama hedefi: macOS 10.13.2 ve üzeri

#### <a name="apps-from-the-store-only-setting-for-windows-10-devices-includes-more-configuration-options----2697002---"></a>Yalnızca Windows 10 cihazları için mağaza ayarındaki uygulamalar daha fazla yapılandırma seçeneği içerir <!-- 2697002 -->
Windows cihazları için bir cihaz kısıtlamaları profili oluşturduğunuzda, **kullanıcıların uygulamaları yalnızca** Windows App Store 'Dan (**cihaz yapılandırması** > **profiller** > **Oluştur** profil türü için  > **Windows 10 ve üzeri** profil > **cihaz kısıtlamaları** . Bu güncelleştirmede, daha fazla seçenek desteklemek için bu ayar genişletilir. 

Yeni ayarı görmek için, [özelliklere izin vermek veya erişimi kısıtlamak üzere Windows 10 (ve daha yeni) cihaz ayarları](../configuration/device-restrictions-windows-10.md#app-store)' na gidin.

Şunlar için geçerlidir: Windows 10 ve üzeri

#### <a name="deploy-multiple-zebra-mobility-extensions-device-profiles-to-a-device-same-user-group-or-same-devices-group----4089955---"></a>Bir cihaza, aynı kullanıcı grubuna veya aynı cihazlar grubuna birden çok Zeköşeli Mobility uzantıları cihaz profili dağıtma <!-- 4089955 -->
Intune 'da yerleşik olmayan Zeköşeli cihazlara yönelik ayarları özelleştirmek için bir cihaz yapılandırma profilinde Zeköşeli Mobility uzantıları (MX) kullanabilirsiniz. Şu anda tek bir cihaza bir profil dağıtabilirsiniz. Bu güncelleştirmede, aşağıdakileri yapmak için birden çok profil dağıtabilirsiniz:
- Aynı kullanıcı grubu
- Aynı cihazlar grubu
- Tek bir cihaz

[Microsoft Intune ' deki Zeköşeli Mobility uzantıları Ile zeköşeli cihazlarını kullanın ve yönetin](../configuration/android-zebra-mx-overview.md) ıNTUNE 'da MX 'in nasıl kullanılacağını gösterir.

Uygulama hedefi: Android

#### <a name="some-kiosk-settings-on-ios-devices-are-set-using-block-replacing-allow----4404075----"></a>İOS cihazlarındaki bazı bilgi noktası ayarları "engelle" kullanılarak ayarlanır ve "Izin ver" olarak değiştiriliyor <!-- 4404075  -->
İOS cihazlarında bir cihaz kısıtlamaları profili oluştururken (**cihaz yapılandırma** > **profilleri** >  profil**oluşturma** > **iOS** for platform > **cihaz kısıtlamaları** profil türü > **bilgi noktası** ) **otomatik kilit**, **zil**düğmesi, **ekran döndürme**, **ekran uyku düğmesi**ve **Ses düğmelerini**ayarlarsınız. 

Bu güncelleştirmede değerler **blok** (özelliği engeller) ve **Yapılandırılmadı** (özelliğe izin verir). Ayarları görmek için [iOS cihaz ayarları ' na giderek özelliklere izin verin veya kısıtlayın](../configuration/device-restrictions-ios.md#kiosk). 

Şunun için geçerlidir: iOS

#### <a name="use-face-id-for-password-authentication-on-ios-devices----4490704---"></a>İOS cihazlarında parola kimlik doğrulaması için yüz KIMLIĞI kullan <!-- 4490704 -->
İOS cihazları için bir cihaz kısıtlamaları profili oluşturduğunuzda, bir parola için parmak izi kullanabilirsiniz. Bu güncelleştirmede, parmak izi parola ayarları yüz tanıma izin verir (**cihaz yapılandırma** > **profilleri** >  profil**Oluştur** > **iOS** for platform > **cihaz kısıtlamaları** > **parola**) yazın. Sonuç olarak, aşağıdaki ayarlar değiştirilmiştir:

- **Parmak iziyle kilit açma** artık **dokunma KIMLIĞI ve yüz kimliği kilidi**.
- **Parmak izi değişikliği (yalnızca denetimli)** artık **dokunma KIMLIĞI ve yüz kimliği değişikliği (yalnızca denetimli)** .

Yüz KIMLIĞI, iOS 11,0 ve üzeri sürümlerde kullanılabilir. Ayarları görmek için [iOS cihaz ayarları ' na giderek Intune kullanarak özelliklere izin verin veya kısıtlayın](../configuration/device-restrictions-ios.md#password).

Şunun için geçerlidir: iOS

#### <a name="restricting-gaming-and-app-store-features-on-ios-devices-is-now-dependent-on-ratings-region----4593948---"></a>İOS cihazlarında oyun ve uygulama mağazası özelliklerinin sınırlandırılması artık derecelendirme bölgesine bağımlıdır <!-- 4593948 -->
İOS cihazlarında, Oyunlar, uygulama mağazası ve görüntüleme belgeleri (**cihaz yapılandırma** > **profilleri** >  platform > cihaz**oluşturma** > **iOS** ) ile ilgili özelliklere izin verebilir veya bunları kısıtlayabilirsiniz> **App Store, belge görüntüleme, oyun**) profil türü için kısıtlamalar. Ayrıca, Birleşik Devletler gibi derecelendirme bölgesini de seçebilirsiniz. 

Bu güncelleştirmede, **uygulamalar** özelliği bir alt öğe **Derecelendirme bölgesine**taşınır ve **Derecelendirme bölgesine**bağımlıdır. Ayarları görmek için [iOS cihaz ayarları ' na giderek Intune kullanarak özelliklere izin verin veya kısıtlayın](../configuration/device-restrictions-ios.md#app-store-doc-viewing-gaming).

Şunun için geçerlidir: iOS

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="windows-autopilot-support-for-hybrid-azure-ad-join----4809146--"></a>Karma Azure AD katılımı için Windows Autopilot desteği <!-- 4809146-->
Mevcut cihazlar için Windows Autopilot artık karma Azure AD JOIN 'i destekliyor (mevcut Azure AD JOIN desteğine ek olarak). Windows 10 sürüm 1809 ve üzeri cihazlar için geçerlidir. Daha fazla bilgi için bkz. [var olan cihazlar Için Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/existing-devices).



### <a name="device-management"></a>Cihaz yönetimi

#### <a name="see-the-security-patch-level-for-android-devices----4461911---"></a>Android cihazlar için güvenlik düzeltme eki düzeyine bakın <!-- 4461911 -->
Artık Android cihazlar için güvenlik düzeltme eki düzeyini görebilirsiniz. Bunu yapmak için **ıntune**@no__t **-1 cihaz** >  ' ü seçin >**tüm cihazlar** ' a bir cihaz > **donanımı**seçin.
Düzeltme eki düzeyi, **Işletim sistemi** bölümünde listelenir.

#### <a name="assign-scope-tags-to-all-managed-devices-in-a-security-group----3173810---"></a>Kapsam etiketlerini bir güvenlik grubundaki tüm yönetilen cihazlara ata <!-- 3173810 -->
Artık kapsam etiketlerini bir güvenlik grubuna atayabilirsiniz ve güvenlik grubundaki tüm cihazlar da bu kapsam etiketleriyle ilişkilendirilecektir. Bu gruplardaki tüm cihazlara de kapsam etiketi atanır. Bu özellikle ayarlanan kapsam etiketleri, geçerli cihaz kapsamı etiketleri akışıyla ayarlanmış kapsam etiketlerinin üzerine yazar. Daha fazla bilgi için bkz. [Dağıtılmış BT IÇIN RBAC ve kapsam etiketlerini kullanma](scope-tags.md).

### <a name="device-security"></a>Cihaz güvenliği

#### <a name="use-keyword-search-with-security-baselines-------"></a>Anahtar sözcük aramasını güvenlik temel bilgileriyle kullanma <!--  -->
[Güvenlik temel profilleri](../protect/security-baselines.md#create-the-profile)oluştururken veya düzenlerken, kullanılabilir ayar gruplarını arama ölçütlerinize sahip olanlarla filtrelemek Için yeni *arama* çubuğunda anahtar sözcükler belirtebilirsiniz. 

#### <a name="the-security-baselines-feature-is-now-generally-available-----3785395---"></a>Güvenlik temelleri özelliği artık genel kullanıma sunuldu  <!-- 3785395 -->
**Güvenlik temelleri** özelliği önizleme aşamasındadır ve genel kullanıma sunuldu (GA).  Bu, özelliğin üretimde kullanıma hazırlanmasıdır. Ancak, tek başına temel şablonlar önizlemede kalabilir ve Kendi zamanlamalarında GA olarak değerlendirilir ve bu şekilde serbest bırakılır.

#### <a name="the-mdm-security-baseline-template-is-now-generally-available------3794072-4217151--3534649---"></a>MDM güvenlik temeli şablonu genel kullanıma sunuldu   <!-- 3794072, 4217151,  3534649 -->
MDM güvenlik temeli şablonu önizleme dışına taşındı ve genel kullanıma sunuldu (GA). GA şablonu, **2019 Mayıs Için MDM güvenlik temeli**olarak tanımlanır.  Bu yeni bir şablondur ve önizleme sürümünden yükseltme değildir.  Yeni bir şablon olarak, [içerdiği ayarları](../protect/security-baseline-settings-mdm.md)gözden geçirmeniz ve sonra şablonu cihazınıza dağıtmak için yeni profiller oluşturmanız gerekir. Diğer güvenlik temeli şablonları önizlemede kalabilir. Kullanılabilir temellerin listesi için bkz. [kullanılabilir güvenlik temelleri](../protect/security-baselines.md#available-security-baselines).  

Yeni bir şablon olmanın yanı sıra, *2019 Mayıs şablonuna yönelik MDM güvenlik taban çizgisi* , en kısa zamanda geliştirme makaleimizde duyurduğumuz iki ayarı içerir:  
- Kilit üzerinde: uygulamaları kilitli bir ekrandan etkinleştirin  
- DeviceGuard: cihazların bir sonraki yeniden başlatmada sanallaştırma tabanlı güvenlik (VBS) kullanın.  

*2019 Mayıs Için MDM güvenlik temeli* Ayrıca birkaç yeni ayarın eklenmesi, diğerlerinin kaldırılması ve bir ayarın varsayılan değerinin düzeltilmesi içerir. Önizlemedeki değişikliklerin ayrıntılı bir listesi için, bkz. **Yeni şablonda nelerin değiştiğini**.

#### <a name="security-baseline-versioning-----3194322---"></a>Güvenlik temel sürümü oluşturma  <!-- 3194322 -->
Intune desteği sürümü oluşturma için güvenlik temelleri. Bu destek sayesinde, her bir güvenlik temelinin yeni sürümleri yayınlandığından, sıfırdan yeni bir taban çizgisi yeniden oluşturup dağıtmak zorunda kalmadan, mevcut güvenlik taban çizgisi profillerinizi daha yeni temel sürümü kullanacak şekilde güncelleştirebilirsiniz. Buna ek olarak, Intune konsolunda, her bir taban çizgisi hakkındaki bilgileri, temeli kullanan bireysel profillerin sayısı, profillerinizin kaç farklı temel sürümünün kullanıldığı ve belirli bir güvenliğin en son sürümü gibi bilgileri görüntüleyebilirsiniz. taban çizgisi idi.  Daha fazla bilgi için bkz. **güvenlik temelleri**.

#### <a name="the-use-security-keys-for-sign-in-setting-has-moved-----4501151---"></a>Oturum açma ayarı için güvenlik anahtarlarını kullan ayarı taşındı  <!-- 4501151 -->
**Oturum açma için güvenlik anahtarlarını kullan** adlı kimlik koruması için cihaz yapılandırma ayarı artık *Iş Için Windows Hello 'yu Yapılandır*alt ayarı olarak bulunmaz. Iş için Windows Hello 'Yu kullanmanıza izin vermeseniz bile, her zaman kullanılabilir olan en üst düzey bir ayardır. Daha fazla bilgi için bkz. [kimlik koruması](../protect/identity-protection-windows-settings.md).

### <a name="role-based-access-control"></a>Rol tabanlı erişim denetimi

#### <a name="new-permissions-for-assigned-group-admins------4504437-----"></a>Atanan Grup yöneticileri için yeni izinler   <!-- 4504437   -->
Intune 'un yerleşik okul yönetici rolünde, yönetilen uygulamalar için oluşturma, okuma, güncelleştirme ve silme (CRUD) izinleri artık vardır. Bu güncelleştirme, Eğitim için Intune ' de bir grup yöneticisi olarak atandıysanız, artık iOS MDM Anında İletme Sertifikası, iOS MDM sunucu belirteçlerini ve iOS VPP belirteçlerini ve [sahip olduğunuz tüm mevcut izinleri](https://docs.microsoft.com/intune-education/group-admin-delegate#group-admin-permissions)oluşturabilir, görüntüleyebilir, güncelleştirebilir ve silebilirsiniz. Bu eylemlerden herhangi birini gerçekleştirmek için **kiracı ayarları** > **iOS cihaz yönetimi**' ne gidin.  

#### <a name="applications-can-use-the-graph-api-to-call-read-operations-without-user-credentials----4655885---"></a>Uygulamalar, Kullanıcı kimlik bilgileri olmadan okuma işlemlerini çağırmak için Graph API kullanabilir <!-- 4655885 -->
Uygulamalar, Kullanıcı kimlik bilgileri olmadan uygulama kimliği ile Intune Graph API okuma işlemlerini çağırabilir. Intune için Microsoft Graph API 'sine erişme hakkında daha fazla bilgi için, bkz. [Microsoft Graph Intune Ile çalışma](https://docs.microsoft.com/graph/api/resources/intune-graph-overview?view=graph-rest-1.0).

#### <a name="apply-scope-tags-to-microsoft-store-for-business-apps----4392555---"></a>Iş uygulamalarına yönelik Microsoft Store kapsam etiketleri uygulama <!-- 4392555 -->
Artık Microsoft Store for Business uygulamalarına kapsam etiketleri uygulayabilirsiniz. Kapsam etiketleri hakkında daha fazla bilgi için bkz. [Dağıtılmış BT için rol tabanlı erişim denetimi (RBAC) ve kapsam etiketleri kullanma](scope-tags.md).

## <a name="week-of-june-17-2019"></a>17 Haziran 2019 haftası 

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="new-features-in-microsoft-intune-app"></a>Microsoft Intune uygulamasındaki yeni özellikler
Android için Microsoft Intune uygulamasına (Önizleme) yeni özellikler ekledik. Tam olarak yönetilen Android cihazlarındaki kullanıcılar artık şunları yapabilir:  

* Intune Şirket Portalı veya Microsoft Intune uygulaması aracılığıyla kaydolduğu cihazları görüntüleyin ve yönetin.    
* Destek için kuruluşunuzla iletişim kurun.    
* Geri bildirimlerini Microsoft 'a gönderin.    
* Kuruluş tarafından ayarlandıysa hüküm ve koşulları görüntüleyin.    

## <a name="week-of-june-10-2019"></a>10 Haziran 2019 haftası 

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="new-sample-apps-showing-intune-sdk-integration-available-on-github----2653471---"></a>GitHub 'da kullanılabilen Intune SDK tümleştirmesini gösteren yeni örnek uygulamalar <!-- 2653471 -->
Msıntuneappsdk GitHub hesabı, iOS (Swift), Android, Xamarin. iOS, Xamarin Forms ve Xamarin. Android için yeni örnek uygulamalar ekledi. Bu uygulamalar, mevcut belgelerimizi tamamlamak ve Intune uygulama SDK 'sını kendi mobil uygulamalarınıza tümleştirme hakkında gösteriler sağlamaktır. Ek Intune SDK rehberlik gerektiren bir uygulama geliştiricisiyseniz aşağıdaki bağlantılı örneklere bakın:
- [Chatr](https://github.com/msintuneappsdk/Chatr-Sample-Intune-iOS-App) -aracılı kimlik doğrulaması Için Azure Active Directory kimlik doğrulama kitaplığı 'Nı (ADAL) kullanan bir yerel IOS (Swift) anlık ileti uygulaması.
- [Taskr](https://github.com/msintuneappsdk/Taskr-Sample-Intune-Android-App) -aracılı kimlik doğrulaması için ADAL kullanan yerel bir Android yapılacaklar listesi uygulamasıdır.
- [Taskr](https://github.com/msintuneappsdk/Taskr-Sample-Intune-Xamarin-Android-Apps) -aracılı kimlik doğrulaması için ADAL kullanan bir Xamarin. Android yapılacaklar listesi uygulaması, bu deponun de Xamarin. Forms uygulaması vardır.
- [Xamarin. iOS örnek uygulaması](https://github.com/msintuneappsdk/sample-intune-xamarin-ios) -bir barekemikler Xamarin. iOS örnek uygulaması.

## <a name="week-of-may-27-2019"></a>27 Mayıs 2019 haftası 

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="reporting-for-potentially-harmful-apps-on-android-devices----4223162---"></a>Android cihazlarda zararlı olabilecek uygulamalar için raporlama <!-- 4223162 -->
Intune artık Android cihazlarda zararlı olabilecek uygulamalar hakkında ek raporlama bilgileri sağlamaktadır. 

## <a name="week-of-may-20-2019"></a>20 Mayıs 2019 haftası 

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="windows-company-portal-app----3316993---"></a>Windows Şirket Portalı uygulaması <!-- 3316993 -->
Windows Şirket Portalı uygulamasının artık **cihaz**etiketli yeni bir sayfası olacak. **Cihazlar** sayfasında, son kullanıcılar tüm kayıtlı cihazlarını gösterecektir. Kullanıcılar, 10.3.4291.0 ve sonraki sürümleri kullandıklarında bu değişikliği Şirket Portalı görür. Şirket Portalı yapılandırma hakkında daha fazla bilgi için bkz. [Microsoft Intune şirket portalı uygulamasını yapılandırma](../apps/company-portal-app.md).

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="autopilot-device-orderid-attribute-name-changed-to-group-tag----4659453---"></a>Autopilot cihaz OrderID özniteliği adı Grup etiketi olarak değiştirildi <!-- 4659453 -->

Daha sezgisel hale getirmek için Autopilot cihazlarındaki **OrderID** özniteliği Name **Grup etiketi**olarak değiştirilmiştir. CSV 'yi Autopilot cihaz bilgilerini karşıya yüklemek için kullanırken, Grup etiketi ' ni, OrderID değil, sütun üst bilgisi olarak kullanmanız gerekir.  

## <a name="week-of-may-13-2019"></a>13 Mayıs 2019 haftası 

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="intune-policies-update-authentication-method-and-company-portal-app-installation-----1927359----"></a>Intune ilkeleri kimlik doğrulama yöntemini güncelleştirme ve uygulama yükleme Şirket Portalı  <!-- 1927359  -->
Apple 'ın kurumsal cihaz kayıt yöntemlerinden biri aracılığıyla Kurulum Yardımcısı aracılığıyla zaten kaydedilmiş cihazlarda, Intune artık son kullanıcılar tarafından App Store 'dan el ile yüklendiğinde Şirket Portalı desteklememektedir. Bu değişiklik yalnızca kayıt sırasında Apple Kurulum Yardımcısı ile kimlik doğrulaması yaptığınızda geçerlidir. Bu değişiklik yalnızca aracılığıyla kaydedilen iOS cihazlarını da etkiler:  
* Apple Configurator

* Apple Business Manager

* Apple School Manager

* Apple Aygıt Kayıt Programı (DEP)

Kullanıcılar Şirket Portalı uygulamayı App Store 'dan yüklerse ve sonra bu cihazları bu cihaz üzerinden kaydetmeyi denerseniz, bir hata alırlar. Bu cihazların yalnızca Şirket Portalı, kayıt sırasında Intune tarafından otomatik olarak gönderildiği sırada kullanması beklenir. Azure portal Intune 'daki kayıt profilleri, cihazların kimliğini nasıl doğrulayacağınızı ve Şirket Portalı uygulamasını alıp almamasını belirleyebilmeniz için güncelleştirilir. DEP cihaz kullanıcılarınızın Şirket Portalı sahip olmasını istiyorsanız, tercihlerinizi bir kayıt profilinde belirtmeniz gerekecektir. 

Ayrıca, iOS Şirket Portalı **cihaz ekranınızı belirler** . Bu nedenle, koşullu erişimi etkinleştirmek veya şirket uygulamalarını dağıtmak isteyen yöneticiler DEP kayıt profilini güncelleştirmemelidir. Bu gereksinim yalnızca DEP kaydının kimlik doğrulaması Kurulum Yardımcısı ile doğrulanmışsa geçerlidir. Bu durumda, Şirket Portalı cihaza göndermeniz gerekir. Bunu yapmak için, **ıntune** > **cihaz kaydı** > **Apple kayıt** > **kayıt programı belirteçleri** seçin > bir belirteç > **profilleri** seçin > bir profil > **Özellikler** seçin > ayarla  **Şirket Portalı** **Evet**'e yüklemek.

Şirket Portalı, zaten kayıtlı DEP cihazlarına yüklemek için Intune > Istemci uygulamalarına gitmeniz ve uygulamayı uygulama yapılandırma ilkeleriyle yönetilen bir uygulama olarak göndermeniz gerekir. 

#### <a name="configure-how-end-users-update-a-line-of-business-lob-app-using-an-app-protection-policy----3568384---"></a>Son kullanıcıların bir uygulama koruma ilkesi kullanarak iş kolu (LOB) uygulamasını nasıl güncelleştirmelerini yapılandırma <!-- 3568384 -->
Artık son kullanıcılarınızın, iş kolu (LOB) uygulamasının güncelleştirilmiş bir sürümünü nereden alabilirim? Son kullanıcılar bu özelliği **En düşük uygulama sürümü** koşullu başlatma iletişim kutusunda görür. Bu, son kullanıcıların lob uygulamasının en düşük bir sürümüne güncelleştirilmesini ister. Bu güncelleştirme ayrıntılarını, LOB uygulama koruma ilkenizin (APP) bir parçası olarak sağlamanız gerekir. Bu özellik iOS ve Android 'de kullanılabilir. İOS 'ta, bu özellik, uygulamanın iOS için Intune SDK 'Sı ile tümleştirilebilmesi (veya sarmalama aracı kullanılarak sarmalanması) gerekir. 10.0.7 veya üzeri. Android 'de, bu özellik en son Şirket Portalı gerektirir. Bir son kullanıcının bir LOB uygulamasını nasıl güncelleştirmiş olduğunu yapılandırmak için, uygulamaya bir yönetilen uygulama yapılandırma ilkesine, `com.microsoft.intune.myappstore` anahtarı ile gönderilmesi gerekir. Gönderilen değer, son kullanıcının uygulamayı hangi depoya indirecek tanımlar. Uygulama Şirket Portalı aracılığıyla dağıtılırsa, değer `CompanyPortal` olmalıdır. Diğer herhangi bir mağaza için, URL 'nin tamamını girmeniz gerekir.

#### <a name="intune-management-extension-powershell-scripts-----3734186----"></a>Intune yönetim uzantısı PowerShell betikleri  <!-- 3734186  -->
PowerShell betiklerini, kullanıcının cihazdaki yönetici ayrıcalıklarıyla çalışacak şekilde yapılandırabilirsiniz. Daha fazla bilgi için bkz. [Intune 'Da Windows 10 cihazlarında PowerShell betikleri kullanma](../apps/intune-management-extension.md) ve [Win32 uygulama yönetimi](../apps/app-management.md).

#### <a name="android-enterprise-app-management----4459905---"></a>Android kurumsal uygulama yönetimi <!-- 4459905 -->
BT yöneticilerinin Android kurumsal yönetimini yapılandırmasını ve kullanmasını kolaylaştırmak için Intune, Intune yönetici konsoluna dört ortak Android kurumsal ilgili uygulamayı otomatik olarak ekler. Dört Android kurumsal uygulama aşağıdaki uygulamalardır:

- **[Microsoft Intune](https://play.google.com/store/apps/details?id=com.microsoft.intune)** -Android kurumsal tam olarak yönetilen senaryolar için kullanılır.
- **[Microsoft Authenticator](https://play.google.com/store/apps/details?id=com.azure.authenticator)** -iki öğeli doğrulama kullanırsanız, hesaplarınızda oturum açmanıza yardımcı olur.
- **[Intune şirket portalı](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)** -uygulama koruma ILKELERI (uygulama) ve Android kurumsal iş profili senaryoları için kullanılır.
- [Yönetilen giriş ekranı](https://play.google.com/store/apps/details?id=com.microsoft.launcher.enterprise) -Android kurumsal adanmış/bilgi noktası senaryolarında kullanılır.

Daha önce BT yöneticilerinin, kurulum kapsamında bu uygulamaları [yönetilen Google Play deposunda](https://play.google.com/store/apps) el ile bulması ve onaylaması gerekir. Bu değişiklik, müşterilerin Android kurumsal yönetimini kullanmasını kolaylaştıran ve daha hızlı hale getirmeye yönelik daha önceden el ile yapılan adımları ortadan kaldırır.

Yöneticiler, Intune kiracılarını yönetilen Google Play ilk kez bağlandıklarında Intune uygulamaları listesine otomatik olarak eklenen bu dört uygulamayı görür. Daha fazla bilgi için bkz. [Intune hesabınızı yönetilen Google Play hesabınıza bağlama](../enrollment/connect-intune-android-enterprise.md). Kiracılarına zaten bağlı olan veya Android Enterprise kullanan kiracılar için yöneticilerin yapması gereken hiçbir şey yoktur. Bu dört uygulama, Mayıs 2019 servis dağıtımı tamamlandığında otomatik olarak 7 gün içinde görünür.

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="updated-pfx-certificate-connector-for-microsoft-intune-----1533038---"></a>Microsoft Intune için PFX Sertifika Bağlayıcısı güncelleştirildi  <!-- 1533038 -->
Mevcut PFX sertifikalarının yeniden işlenmesine devam edildiği bir sorunu gideren [Microsoft Intune Için PFX Sertifika Bağlayıcısı](../protect/certficates-pfx-configure.md#whats-new-for-connectors) için bir güncelleştirme yayımladık ve bu, bağlayıcının yeni istekleri işlemeyi durdurmasına neden oluyor.

#### <a name="intune-security-tasks-for-defender-atp-in-public-preview--------3208597---"></a>Defender ATP için Intune güvenlik görevleri (genel önizlemede)     <!-- 3208597 -->
Genel önizlemede, [Microsoft Defender Gelişmiş tehdit koruması (ATP) için güvenlik görevlerini](../protect/atp-manage-vulnerabilities.md)yönetmek üzere Intune 'u kullanabilirsiniz. Bu ATP ile tümleştirme ve uç nokta güvenlik açıklarını ve yapılandırmalarını düzeltmeye, önceliklendirmeye ve düzeltmeye yönelik risk tabanlı bir yaklaşım ekler ve hafifletme için bulma arasındaki süreyi azaltmaktadır.

#### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy----3617671---idstaged--"></a>Windows 10 cihaz uyumluluk ilkesinde TPM yonga kümesini denetleme <!-- 3617671   idstaged-->
Birçok Windows 10 ve üzeri cihazda Güvenilir Platform Modülü (TPM) yonga kümeleri vardır. Bu güncelleştirme, cihazdaki TPM yonga sürümünü denetleyen yeni bir uyumluluk ayarı içerir. 

[Windows 10 ve üzeri uyumluluk ilkesi ayarları](../protect/compliance-policy-create-windows.md#device-security) bu ayarı açıklar.

Şunlar için geçerlidir: Windows 10 ve üzeri

#### <a name="prevent-end-users-from-modifying-their-personal-hotspot-and-disable-siri-server-logging-on-ios-devices----4097904-----"></a>Son kullanıcıların kendi kişisel etkin kullanımlarını değiştirmesini engelleyin ve iOS cihazlarında Siri sunucu günlüğünü devre dışı bırakın <!-- 4097904   -->  
İOS cihazında bir cihaz kısıtlamaları profili oluşturursunuz (**cihaz yapılandırma** > **profilleri** >  platform Için  > **IOS** **> profil türü**için **cihaz kısıtlamaları** ). Bu güncelleştirme, yapılandırabileceğiniz yeni ayarları içerir:

- **Yerleşik uygulamalar**: Siri komutları için sunucu tarafında günlüğe kaydetme
- **Kablosuz**: kişisel etkin noktanın Kullanıcı değişikliği (yalnızca denetimli)

Bu ayarları görmek için [iOS için yerleşik uygulama ayarları](../configuration/device-restrictions-ios.md#built-in-apps) ' na ve [iOS için kablosuz ayarlar](../configuration/device-restrictions-ios.md#wireless)' a gidin.

Uygulama hedefi: iOS 12,2 ve üzeri

#### <a name="new-classroom-app-device-restriction-settings-for-macos-devices----4097905-----"></a>MacOS cihazları için yeni sınıf uygulaması cihaz kısıtlama ayarları <!-- 4097905   --> 
MacOS cihazları için cihaz yapılandırma profilleri oluşturabilirsiniz (**cihaz yapılandırma** > **profilleri** >  profil**Oluştur** > **MacOS** for platform > **cihaz kısıtlamaları** profil türü). Bu güncelleştirme, yeni sınıf uygulaması ayarlarını, ekran görüntülerini engelleme seçeneğini ve iCloud Fotoğraf kitaplığını devre dışı bırakma seçeneğini içerir.

Geçerli ayarları görmek için, [Intune kullanarak özelliklere izin vermek veya erişimi kısıtlamak üzere MacOS cihaz ayarları](../configuration/device-restrictions-macos.md)' na gidin.

Uygulama hedefi: macOS

#### <a name="the-ios-password-to-access-app-store-setting-is-renamed---4557891----"></a>App Store 'a erişmek için iOS parolası ayarı yeniden adlandırıldı<!-- 4557891  -->
**App Store 'a erişim parolası** , **tüm satın alımlarda ITunes mağazası parolası gerektirecek** şekilde yeniden adlandırılır **(cihaz yapılandırması** > **profilleri** >  Platform Için 7.**Profil oluştur** > **iOS** > > **App Store, belge görüntüleme ve oyun**için profil türü için **cihaz kısıtlamaları** .

Kullanılabilir ayarları görmek için [App Store, belge görüntüleme, oyun iOS ayarları '](../configuration/device-restrictions-ios.md#app-store-doc-viewing-gaming)na gidin.

Şunun için geçerlidir: iOS

#### <a name="microsoft-defender-advanced-threat-protection--baseline--preview------3754134---"></a>Microsoft Defender Gelişmiş tehdit koruması temeli (Önizleme)  <!--  3754134 -->
[Microsoft Defender Gelişmiş tehdit koruması](../protect/security-baseline-settings-defender-atp.md) ayarları için bir güvenlik temeli önizlemesi ekledik. Bu taban çizgisi, ortamınız [Microsoft Defender Gelişmiş tehdit koruması](../protect/advanced-threat-protection.md#prerequisites)kullanımı için önkoşulları karşılıyorsa kullanılabilir.

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="windows-enrollment-status-page-esp-is-now-generally-available----3605348---"></a>Windows kayıt durumu sayfası (ESP) artık genel kullanıma sunuldu <!-- 3605348 -->
Kayıt durumu sayfası artık önizleme aşamasındadır. Daha fazla bilgi için bkz. [kayıt durumu sayfası ayarlama](../enrollment/windows-enrollment-status.md).


#### <a name="intune-user-interface-update---autopilot-enrollment-profile-creation-----4593669---"></a>Intune kullanıcı arabirimi güncelleştirmesi-Autopilot kayıt profili oluşturma  <!-- 4593669 -->
Autopilot kayıt profili oluşturmaya yönelik kullanıcı arabirimi, Azure Kullanıcı arabirimi stilleriyle hizalanacak şekilde güncelleştirilmiştir. Daha fazla bilgi için bkz. [Autopilot kayıt profili oluşturma](../enrollment/enrollment-autopilot.md#create-an-autopilot-deployment-profile). İleri hareket ettirilerek, ek Intune senaryoları bu yeni kullanıcı arabirimi stiline güncelleştirilecektir.

#### <a name="enable-autopilot-reset-for-all-windows-devices----4225665---"></a>Tüm Windows cihazları için Autopilot sıfırlamayı etkinleştir <!-- 4225665 -->
Autopilot Reset, kayıt durumu sayfasını kullanmak üzere yapılandırılmamış olsalar dahi, tüm Windows cihazlarında çalışmaktadır. İlk cihaz kaydı sırasında cihaz için bir kayıt durumu sayfası yapılandırılmamışsa, cihaz, oturum açma işleminden sonra doğrudan masaüstüne gidecektir. Eşitlemek ve Intune ile uyumlu görünmesi sekiz saate kadar sürebilir. Daha fazla bilgi için bkz. [uzak Windows Autopilot sıfırlaması ile cihazları sıfırlama](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-reset-remote).

#### <a name="exact-imei-format-not-required-when-searching-all-devices---30407680---"></a>Tüm cihazlar aranırken tam ıMEı biçimi gerekli değildir <!--30407680 -->
**Tüm cihazları**ararken IMEI numaralarına boşluk eklemeniz gerekmez.

#### <a name="deleting-a-device-in-the-apple-portal-will-be-reflected-in-the-intune-portal---2489996---"></a>Apple portalında bir cihazın silinmesi, Intune portalında yansıtılacaktır <!--2489996 -->
Bir cihaz Apple 'ın Aygıt Kayıt Programı veya Apple Business Manager portallarından silinirse, bir sonraki eşitleme sırasında cihaz otomatik olarak Intune 'dan silinir.

### <a name="the-enrollment-status-page-now-tracks-win32-apps----2714451---"></a>Kayıt durumu sayfası artık Win32 uygulamalarını izler <!-- 2714451 -->
Bu, yalnızca Windows 10 sürüm 1903 ve üstünü çalıştıran cihazlar için geçerlidir. Daha fazla bilgi için bkz. [kayıt durumu sayfası ayarlama](../enrollment/windows-enrollment-status.md).

### <a name="device-management"></a>Cihaz yönetimi

#### <a name="reset-and-wipe-devices-in-bulk-by-using-the-graph-api----3295288---"></a>Graph API kullanarak cihazları toplu olarak sıfırlayın ve temizleyin <!-- 3295288 -->
Artık Graph API kullanarak en fazla 100 cihazı toplu olarak sıfırlayabilir ve silebilirsiniz.


### <a name="monitor-and-troubleshoot"></a>İzleme ve sorun giderme

#### <a name="the-encryption-report-is-out-of-public-preview------4587546--------"></a>Şifreleme raporu genel önizleme dışında   <!-- 4587546      -->
[BitLocker ve cihaz şifrelemesi için rapor](../protect/encryption-monitor.md) artık genel önizlemeye sunuldu ve artık genel önizlemenin bir parçası değil. 

<!-- ########################## -->

#### <a name="outlook-signature-and-biometric-settings-for--ios-and-android-devices----4050557---"></a>İOS ve Android cihazlar için Outlook imzası ve biyometrik ayarlar <!-- 4050557 -->
Artık, varsayılan imzanın iOS ve Android cihazlarda Outlook 'ta etkinleştirilip etkinleştirilmediğini belirtebilirsiniz. Ayrıca, kullanıcıların iOS üzerinde Outlook 'ta biyometrik ayarını değiştirmesine izin vermeyi de seçebilirsiniz.

## <a name="week-of-may-6-2019"></a>6 Mayıs 2019 haftası 

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="network-access-control-nac-support-for-f5-access-for-ios-devices----4500808---"></a>İOS cihazlarına yönelik F5 erişimi için ağ Access Control (NAC) desteği <!-- 4500808 -->

F5, Intune 'da iOS üzerinde F5 erişimi için NAC işlevselliğine izin veren büyük IP 13 için bir güncelleştirme yayınladı. Bu özelliği kullanmak için:

- BÜYÜK IP 'yi 13.1.1.5 yenilemeye güncelleştirin. BÜYÜK IP 14 desteklenmez.
- NAC için büyük IP 'yi Intune ile tümleştirin. [Genel bakış: uç nokta yönetim sistemleriyle cihaz gönderme denetimleri IÇIN APM yapılandırma](https://techdocs.f5.com/kb/en-us/products/big-ip_apm/manuals/product/apm-client-configuration-7-1-6/6.html).
- Intune 'da VPN profilindeki **ağ Access Control etkinleştir (NAC)** ayarını denetleyin.

Kullanılabilir ayarı görmek için [iOS CIHAZLARıNDA VPN ayarlarını yapılandırma](../configuration/vpn-settings-ios.md)bölümüne gidin.

Şunun için geçerlidir: iOS

#### <a name="updated-pfx-certificate-connector-for-microsoft-intune----doc-vso-1521237----"></a>Microsoft Intune için PFX Sertifika Bağlayıcısı güncelleştirildi <!-- doc-vso 1521237  -->  
[Microsoft Intune Için PFX Sertifika Bağlayıcısı](../protect/certficates-pfx-configure.md#whats-new-for-connectors) için bir güncelleştirme yayımladık ve yoklama aralığını 5 dakikadan 30 saniyeye bırakıyor.

## <a name="week-of-april-22-2019"></a>22 Nisan 2019 haftası

### <a name="use-compliance-manager-to-create-assessments-for-microsoft-intune---4404750---"></a>Uyumluluk Yöneticisi 'Ni kullanarak Microsoft Intune için değerlendirmeler oluşturma<!-- 4404750 -->

[Uyumluluk Yöneticisi](https://servicetrust.microsoft.com/ComplianceManager) (başka bir Microsoft site açar), Microsoft hizmet güveni portalındaki iş akışı tabanlı risk değerlendirmesi aracıdır. Kuruluşunuzun Microsoft hizmetleriyle ilgili yasal uyumluluk etkinliklerini izlemenize, atamanıza ve doğrulamanıza olanak sağlar. Office 365, Azure, Dynamics, Professional Hizmetleri ve Intune ile kendi uyumluluk değerlendirmenizi oluşturabilirsiniz. Intune 'da kullanılabilir iki değerlendirme vardır-FFIEC ve GDPR.

Uyumluluk Yöneticisi, Microsoft tarafından yönetilen denetimleri ve kuruluşunuz tarafından yönetilen denetimleri kırarak çabalarınıza odaklanmanıza yardımcı olur. Değerlendirmeleri tamamlayabilir ve sonra değerlendirmeleri dışa aktarabilir ve yazdırabilirsiniz.

[Federal Finans kurumları Inceleme Council (FFIEC)](https://www.microsoft.com/trustcenter/compliance/FFIEC) (başka bir Microsoft site açar) uyumluluk, ffiec tarafından verilen çevrimiçi bankacılık için bir standartlar kümesidir. Bu, Intune kullanan finansal kurumlar için en çok istenen değerlendirmede yapılır. Intune 'un genel bulut iş yükleri ile ilgili FFIEC siber güvenlik yönergelerine nasıl yardımcı olduğunu yorumlar. Intune 'un FFIEC değerlendirmesi, uyumluluk Yöneticisi 'nde ikinci FFIEC değerlendirmesi olur.

Aşağıdaki örnekte, FFIEC denetimlerinin dökümünü görebilirsiniz. Microsoft, 64 denetimlerini içerir. Kalan 12 denetimden sorumlu olursunuz.

![Müşteri eylemleri ve Microsoft eylemleri dahil olmak üzere FFIEC için örnek bir Intune değerlendirmesi konusuna bakın](./media/whats-new/intune-ffiec-assessment-status.png)

[Genel veri koruma yönetmeliği (GDPR)](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-overview) (başka bir Microsoft sitesini açar), kişilerin ve bunların verilerinin haklarının korunmasına yardımcı olan bir Avrupa BIRLIĞI (AB) yasasıdır. GDPR gizlilik düzenlemelerine uyum sağlamaya yardımcı olmak için en istenen değerlendirmesi. 

Aşağıdaki örnekte, GDPR denetimlerinin dökümünü görürsünüz. Microsoft, 49 denetimlerini içerir. Kalan 66 denetimlerinden sorumlu olursunuz.

![Müşteri eylemleri ve Microsoft eylemleri dahil olmak üzere GDPR için örnek Intune değerlendirmesi konusuna bakın](./media/whats-new/intune-assessment-status.png)

## <a name="week-of-april-15-2019"></a>15 Nisan 2019 haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="openssl-encryption-for-android-app-protection-policies----3747362---"></a>Android uygulama koruma ilkeleri için OpenSSL şifrelemesi <!-- 3747362 -->
Android cihazlarda Intune uygulama koruma ilkeleri (uygulama) artık FIPS 140-2 uyumlu bir OpenSSL şifreleme kitaplığı kullanıyor. Daha fazla bilgi için [Microsoft Intune Android uygulama koruma ilkesi ayarlarının](../apps/app-protection-policy-settings-android.md) [şifreleme](../apps/app-protection-policy-settings-android.md#encryption) bölümüne bakın.

#### <a name="enable-win32-app-dependencies----2617348----"></a>Win32 uygulama bağımlılıklarını etkinleştir <!-- 2617348  -->
Yönetici olarak, Win32 uygulamanızı yüklemeden önce diğer uygulamaların bağımlılık olarak yüklenmesini zorunlu kılabilirsiniz. Özellikle, cihazın Win32 uygulamasını yüklemeden önce bağımlı uygulamaları yüklemesi gerekir. Intune 'da, **Uygulama Ekle** dikey penceresini göstermek için **istemci uygulamaları** > **uygulamalar** > **Ekle** ' yi seçin. **Uygulama türü**olarak **Windows uygulaması (Win32)** seçeneğini belirleyin. Uygulamayı ekledikten sonra, Win32 uygulaması yüklenmeden önce yüklenmesi gereken bağımlı uygulamaları eklemek için **Bağımlılıklar** ' ı seçebilirsiniz. Daha fazla bilgi için bkz. [Intune tek başına-Win32 uygulama yönetimi](./../apps/app-management.md). 

#### <a name="app-version-installation-information-for-microsoft-store-for-business-apps----3537391-----"></a>Iş uygulamaları için Microsoft Store uygulama sürümü yükleme bilgileri <!-- 3537391   -->
Uygulama yükleme raporları Microsoft Store Iş uygulamaları için uygulama sürümü bilgilerini içerir. Intune 'da, **istemci uygulamaları** > **uygulamalar**' ı seçin. **İş için bir Microsoft Store** seçin ve ardından **izleyici** bölümünde **cihaz yüklemesi durumu** ' nu seçin.

#### <a name="additions-to-win32-apps-requirement-rules----3676883-----"></a>Win32 uygulamaları gereksinim kurallarına ekler <!-- 3676883   -->
PowerShell betikleri, kayıt defteri değerleri ve dosya sistemi bilgilerini temel alan gereksinim kuralları oluşturabilirsiniz. Intune 'da, **istemci uygulamaları** > **uygulama** > **Ekle**' yi seçin. Ardından **Uygulama Ekle** dikey penceresinde **uygulama türü** olarak **Windows uygulaması (Win32)** seçeneğini belirleyin.  Ek gereksinim kurallarını yapılandırmak için @no__t **gereksinimleri**-1**Ekle** ' yi seçin. Daha sonra, **Gereksinim türü**olarak **dosya türü**, **kayıt defteri**veya **komut dosyası** seçeneklerinden birini belirleyin. Daha fazla bilgi için bkz. [Win32 uygulama yönetimi](./../apps/app-management.md).

#### <a name="configure-your-win32-apps-to-be-installed-on-intune-enrolled-azure-ad-joined-devices----3695227----"></a>Win32 uygulamalarınızı Intune 'a kayıtlı Azure AD 'ye katılmış cihazlara yüklenecek şekilde yapılandırma <!-- 3695227  -->
Win32 uygulamalarınızı, Intune 'a kayıtlı Azure AD 'ye katılmış cihazlara yüklenecek şekilde atayabilirsiniz. Intune 'da Win32 uygulamaları hakkında daha fazla bilgi için bkz. [Win32 uygulama yönetimi](./../apps/app-management.md).

#### <a name="device-overview-shows-primary-user---3794259----"></a>Cihaza genel bakış birincil kullanıcıyı gösterir <!--3794259  -->
Cihaza genel bakış sayfası, Kullanıcı cihaz benzeşimi kullanıcısı (UDA) olarak da bilinen birincil kullanıcıyı gösterir. Bir cihazın birincil kullanıcısını görmek için **ıntune**@no__t **-1 cihaz** > **tüm cihazlar** ' ı seçin > cihaz seçin. Birincil Kullanıcı **genel bakış** sayfasının en üstünde görünür.

#### <a name="additional-managed-google-play-app-reporting-for-android-enterprise-work-profile-devices----4105925----"></a>Android Kurumsal iş profili cihazları için ek Yönetilen Google Play uygulaması raporlaması <!-- 4105925  -->
Android Kurumsal iş profili cihazlarına dağıtılan Yönetilen Google Play uygulamaları için, cihazda yüklü olan uygulamanın sürüm numarasını görüntüleyebilirsiniz. Bu yalnızca gerekli uygulamalar için geçerlidir.  

#### <a name="ios-third-party-keyboards----4111843-----"></a>iOS üçüncü taraf klavyeleri <!-- 4111843   -->
İOS platformu değişikliği nedeniyle, iOS için **üçüncü taraf klavye** ayarları için Intune uygulama koruma IlkesI (App) desteği artık desteklenmiyor. Bu ayarı Intune yönetici konsolunda yapılandıramayacak ve Intune uygulama SDK 'sında istemci üzerinde zorlanmaz.

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="set-login-settings-and-control-restart-options-on-macos-devices----1210083----"></a>MacOS cihazlarında oturum açma ayarlarını ve denetim yeniden başlatma seçeneklerini ayarlama <!-- 1210083  -->
MacOS cihazlarında, bir cihaz yapılandırma profili (**cihaz yapılandırma** > **profilleri**oluşturabilirsiniz  > **Profil oluştur** >, platform için **MacOS** > **cihaz özellikleri** ' ni seçin). Bu güncelleştirme, özel bir başlık gösterme, kullanıcıların oturum açma şeklini seçme, güç ayarlarını gösterme veya gizleme gibi yeni oturum açma penceresi ayarlarını içerir.

Bu ayarları görmek için, [MacOS cihaz özelliği ayarları](../configuration/macos-device-features-settings.md)' na gidin.

#### <a name="configure-wifi-on-android-enterprise-device-owner-dedicated-devices-running-in-multi-app-kiosk-mode---3041940----"></a>Çok uygulama bilgi noktası modunda çalışan Android Enterprise, cihaz sahibi adanmış cihazları üzerinde WiFi yapılandırma <!--3041940  -->
Çok uygulama bilgi noktası modunda adanmış bir cihaz olarak çalışırken Android Enterprise, cihaz sahibi ayarlarını etkinleştirebilirsiniz. Bu güncelleştirmede, kullanıcıların WiFi ağlarını yapılandırmalarını ve bağlanmasını sağlayabilirsiniz (**ıntune** > **cihaz yapılandırması** > **profilleri**@no__t **-5 platform**için  > **Android Enterprise** >  **Yalnızca cihaz sahibi,** profil türü Için cihaz kısıtlamaları > **adanmış cihazlar**1**bilgi noktası modu**: **çoklu uygulama**4**WiFi yapılandırması**). 

Yapılandırabileceğiniz tüm ayarları görmek için [Android kurumsal cihaz ayarları ' na giderek özelliklere izin verin veya kısıtlayın](../configuration/device-restrictions-android-for-work.md).

Uygulama hedefi: çok uygulamayla bilgi noktası modunda çalışan Android kurumsal adanmış cihazlar


#### <a name="configure-bluetooth-and-pairing-on-android-enterprise-device-owner-dedicated-devices-running-in-multi-app-kiosk-mode----3041941----"></a>Android Enterprise 'ta Bluetooth ve eşleştirme, çok uygulama bilgi noktası modunda çalışan cihaz sahibi adanmış cihazları yapılandırma <!-- 3041941  -->
Çok uygulama bilgi noktası modunda adanmış bir cihaz olarak çalışırken Android Enterprise, cihaz sahibi ayarlarını etkinleştirebilirsiniz. Bu güncelleştirmede, son kullanıcıların Bluetooth 'u etkinleştirmesine ve cihazları Bluetooth üzerinden eşleştirmesine izin verebilirsiniz (**ıntune** > **cihaz yapılandırması** > **profilleri** > **profil oluşturma** > **Android Enterprise** yalnızca platform > **cihaz sahibi,** profil türü için cihaz kısıtlamaları > **adanmış cihazlar**1**bilgi noktası modu**: **çok uygulama**4**Bluetooth yapılandırması**). 

Yapılandırabileceğiniz tüm ayarları görmek için [Android kurumsal cihaz ayarları ' na giderek özelliklere izin verin veya kısıtlayın](../configuration/device-restrictions-android-for-work.md).

Uygulama hedefi: çok uygulamayla bilgi noktası modunda çalışan Android kurumsal adanmış cihazlar

#### <a name="create-and-use-oemconfig-device-configuration-profiles-in-intune----3305883----"></a>Intune 'da OEMConfig cihaz yapılandırma profilleri oluşturma ve kullanma <!-- 3305883  -->
Bu güncelleştirmede, Intune, OEMConfig ile Android kurumsal cihazlarını yapılandırmayı destekler. Özellikle, bir cihaz yapılandırma profili oluşturabilir ve OEMConfig kullanarak Android kurumsal cihazlara ayarlar uygulayabilirsiniz (**cihaz yapılandırma** > **profilleri** > **Profil oluştur** > **Android Enterprise** platform için).

OEM desteği şu anda OEM başına temelde. İstediğiniz bir OEMConfig uygulaması OEMConfig Apps listesinde yoksa, `IntuneOEMConfig@microsoft.com` ' a başvurun.

Bu özellik hakkında daha fazla bilgi edinmek için [Microsoft Intune ' de OEMConfig Ile Android kurumsal cihazlarını kullanma ve yönetme](../configuration/android-oem-configuration-overview.md)bölümüne gidin.

Uygulama hedefi: Android Enterprise

#### <a name="windows-update-notifications-----3316758-3316782----"></a>Windows Update bildirimleri  <!-- 3316758, 3316782  -->
Intune konsolu içinden yönetebileceğiniz Windows Update halka yapılandırmalarına iki *Kullanıcı deneyimi ayarı* ekledik. Şimdi şunları yapabilirsiniz:
- Kullanıcıların [Windows güncelleştirmelerini taramasına](../protect/windows-update-settings.md)engel veya izin verir.
- Kullanıcıların göreceği [Windows Update bildirim düzeyini](../protect/windows-update-settings.md) yönetin.

#### <a name="new-device-restriction-settings-for-android-enterprise-device-owner----3574254----"></a>Android Enterprise için yeni cihaz kısıtlama ayarları, cihaz sahibi <!-- 3574254  -->
Android kurumsal cihazlarda, özelliklere izin vermek veya kısıtlamak, parola kuralları ayarlamak ve daha fazlasını yapmak için bir cihaz kısıtlama profili oluşturabilirsiniz (**cihaz yapılandırma** > **profilleri** > **Profil oluştur** > Android seçin  **Enterprise** for platform > **cihaz sahibi yalnızca profil türü için cihaz kısıtlamalarını >** ). 

Bu güncelleştirme, yeni parola ayarlarını içerir, tam olarak yönetilen cihazlarda Google Play Store uygulamalara tam erişim sağlar ve daha fazlasını sağlar. Ayarların geçerli listesini görmek için [Android kurumsal cihaz ayarları ' na giderek özelliklere izin verin veya kısıtlayın](../configuration/device-restrictions-android-for-work.md). 

Uygulama hedefi: Android kurumsal tam yönetilen cihazlar

#### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy----3617671---"></a>Windows 10 cihaz uyumluluk ilkesinde TPM yonga kümesini denetleme <!-- 3617671 -->

Bu özellik gecikiyor ve daha sonra yayınlanabilecek şekilde planlanmaktadır.

#### <a name="updated-ui-changes-for-microsoft-edge-browser-on-windows-10-and-later-devices----3775833-----"></a>Windows 10 ve üzeri cihazlarda Microsoft Edge tarayıcısı için güncelleştirilmiş UI değişiklikleri <!-- 3775833   -->
Bir cihaz yapılandırma profili oluşturduğunuzda, Windows 10 ve üzeri cihazlarda Microsoft Edge özelliklerine izin verebilir veya kısıtlayabilirsiniz (**cihaz yapılandırma** > **profilleri** > **Profil oluştur** > **Windows 10 ve üzeri** platform için, **Microsoft Edge Browser**> profil türü için **cihaz kısıtlamalarını** >. Bu güncelleştirmede, Microsoft Edge ayarları daha açıklayıcı ve anlaşılması daha kolay. 

Bu özellikleri görmek için [Microsoft Edge tarayıcı cihaz kısıtlama ayarları](../configuration/device-restrictions-windows-10.md#microsoft-edge-browser)' na gidin.

Şunlar için geçerlidir: Windows 10 ve üzeri

#### <a name="expanded-support-for-android-enterprise-fully-managed-devices--preview-------3903241-3903244-3903246-----"></a>Android kurumsal tam olarak yönetilen cihazlar için genişletilmiş destek (Önizleme)  <!--   3903241, 3903244, 3903246   -->
Hala genel önizlemede, Android kurumsal tam olarak yönetilen cihazlar desteğimizi genişlettik (ilk olarak aşağıdaki[2019 ' de](whats-new.md#week-of-january-14-2019) yer alır: 

- Tam olarak yönetilen ve ayrılmış cihazlarda, parola kuralları ve [](../protect/compliance-policy-create-android-for-work.md) işletim sistemi gereksinimleri (**cihaz uyumluluğu** > **Ilkeleri** > **ilke oluştur** > **Android** Platform için Enterprise > profil türü Için **cihaz sahibi** ). 

  Adanmış cihazlarda, cihaz **uyumlu değil**olarak gösterilebilir. Koşullu erişim adanmış cihazlarda kullanılamaz. Ayrılmış cihazların atanan ilkelerinizle uyumlu olmasını sağlamak için gerekli görevleri veya eylemleri gerçekleştirdiğinizden emin olun.

- [Koşullu erişim](../protect/conditional-access.md) -Android 'e uygulanan koşullu erişim Ilkeleri, Android kurumsal tam olarak yönetilen cihazlar için de geçerlidir. Kullanıcılar artık **Microsoft Intune uygulamasını**kullanarak tam olarak yönetilen cihazlarını Azure Active Directory kaydedebilir. Daha sonra, bkz. ve kuruluş kaynaklarına erişmek için tüm uyumluluk sorunlarını çözün.

- Yeni Son Kullanıcı uygulaması (Microsoft Intune uygulaması)-Android tam olarak yönetilen ve **Microsoft Intune**adlı cihazlar için yeni bir son kullanıcı uygulaması vardır. Bu yeni uygulama hafif ve modern bir uygulamadır, ancak tam olarak yönetilen cihazlar için Şirket Portalı uygulama olarak benzer işlevsellik sağlar. Daha fazla bilgi için bkz. [Google Play Microsoft Intune uygulama](https://play.google.com/store/apps/details?id=com.microsoft.intune).

Android tam olarak yönetilen cihazları ayarlamak için **cihaz kaydı** > **Android kaydı** > **şirkete ait, tam olarak yönetilen Kullanıcı cihazları**' na gidin. Tam olarak yönetilen Android cihazlar için destek önizlemede kalır ve bazı Intune özellikleri tam olarak işlevsel olmayabilir.  

Bu önizleme hakkında daha fazla bilgi edinmek için bkz. blog, [Android kurumsal tam olarak yönetilen cihazlar için Microsoft Intune-Preview 2](https://aka.ms/preview2_AE_fullymanaged).


### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="configure-profile-to-skip-some-screens-during-setup-assistant----2276470----"></a>Kurulum Yardımcısı sırasında bazı ekranları atlamak için profili yapılandırın <!-- 2276470  -->
Bir macOS kayıt profili oluşturduğunuzda, bir Kullanıcı Kurulum Yardımcısı 'ndan geçtiğinde aşağıdaki ekranlardan birini atlayacak şekilde yapılandırabilirsiniz:
- Görünümünde
- Görüntü Tonu
- ıhoparlör depolama yeni bir profil oluşturursanız veya bir profili düzenlerseniz, seçili atlama ekranlarının Apple MDM sunucusuyla eşitlenmesi gerekir.  Kullanıcılar, profil değişikliklerini çekerken bir gecikme olmaması için cihazların el ile eşitlenmesini verebilir.
Daha fazla bilgi için bkz. [macOS cihazlarını aygıt kayıt programı veya Apple Okul Yöneticisi Ile otomatik olarak kaydetme](../enrollment/device-enrollment-program-enroll-macos.md).

#### <a name="bulk-device-naming-when-enrolling-corporate-ios-devices--3566569----"></a>Kurumsal iOS cihazları kaydedilirken toplu cihaz adlandırma<!--3566569  -->
Apple 'ın şirket kayıt yöntemlerinden birini (DEP/ABı/ASM) kullanırken, gelen iOS cihazlarını otomatik olarak adlandırmak için bir cihaz adı biçimi ayarlayabilirsiniz. Şablonunuzda cihaz türünü ve seri numarasını içeren bir biçim belirtebilirsiniz. Bunu yapmak için **ıntune** > **cihaz kaydı** > **Apple kayıt** > **kayıt programı belirteçleri** > **bir belirteç seçin** >**profil oluşturma**1**cihaz adlandırma biçim**. Mevcut profilleri düzenleyebilirsiniz, ancak yalnızca yeni eşitlenen cihazlara uygulanan ad alınacaktır.

#### <a name="updated-default-timeout-message-on-enrollment-status-page----3959331---"></a>Kayıt durumu sayfasında varsayılan zaman aşımı iletisi güncelleştirildi <!-- 3959331 -->
Kullanıcıların, kayıt durumu sayfası (ESP), ESP profilinde belirtilen zaman aşımı değerini aştığında göreceğiniz varsayılan zaman aşımı iletisini güncelleştirdik. Yeni varsayılan ileti, kullanıcıların gördükleri ve ESP dağıtımıyla ilgili sonraki eylemleri anlamalarına yardımcı olur.  

### <a name="device-management"></a>Cihaz yönetimi

#### <a name="retire-noncompliant-devices-----1827291-----"></a>Uyumsuz cihazları devre dışı bırak  <!-- 1827291   -->
Bu özellik gecikti ve gelecek bir sürüm için planlanmıştır.


### <a name="monitor-and-troubleshoot"></a>İzleme ve sorun giderme

#### <a name="intune-data-warehouse-v10-changes-reflecting-back-to-beta----4403765---"></a>Intune veri ambarı V 1.0, Beta 'ya geri yansıtarak değişir <!-- 4403765 -->
V 1.0 ilk olarak 1808 sürümünde sunulunca Beta API 'sinden bazı önemli yollarla farklıydı. 1903 ' de, bu değişiklikler Beta API sürümüne geri yansıtılır. Beta API sürümünü kullanan önemli raporlarınız varsa, değişikliklerden kaçınmak için bu raporların V 1.0 'a geçişini kesinlikle öneririz. Daha fazla bilgi için bkz. [Intune veri ambarı API 'si Için değişiklik günlüğü](../developer/reports-changelog.md#1903-part-2).

#### <a name="monitor-security-baseline-status-public-preview----3082047---"></a>Güvenlik temel durumunu izleme (Genel Önizleme) <!-- 3082047 --> 
Güvenlik temellerini izlemeye [Kategori başına bir görünüm](../protect/security-baselines-monitor.md#per-category-view) ekledik. (Güvenlik temelleri önizlemede kalır). Kategori başına görünüm, bu kategori için her bir durum grubuna giren cihazların yüzdesiyle birlikte, her bir kategoriyi taban çizgisinden görüntüler. Artık, kaç cihazın tek tek kategoriler ile eşleşip eşleşmediği, yanlış yapılandırılmış veya geçerli olmadığı hakkında bilgi alabilirsiniz.

### <a name="role-based-access-control"></a>Rol tabanlı erişim denetimi

#### <a name="scope-tags-for-apple-vpp-tokens---2371886----"></a>Apple VPP belirteçleri için kapsam etiketleri <!--2371886  -->
Artık, Apple VPP belirteçlerine kapsam etiketleri ekleyebilirsiniz. Yalnızca aynı kapsam etiketiyle atanan kullanıcılar, bu etiketle birlikte Apple VPP belirtecine erişebilir. Bu belirteçle satın alınan VPP uygulamaları ve ekitapları, kapsam etiketlerini de alır. Kapsam etiketleri hakkında daha fazla bilgi için bkz. [RBAC ve kapsam etiketlerini kullanma](scope-tags.md).







## <a name="week-of-april-1-2019"></a>1 Nisan 2019 haftası

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="updated-certificate-connectors-----icm-113304612---"></a>Güncelleştirilmiş sertifika bağlayıcıları  <!-- ICM 113304612 -->
[Microsoft Intune için hem Intune sertifika Bağlayıcısı hem de PFX Sertifika Bağlayıcısı](../protect/certficates-pfx-configure.md#whats-new-for-connectors)için güncelleştirmeler yayımladık. Yeni yayınlar bazı bilinen sorunları düzeltir.  

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="user-experience-update-for-the-company-portal-app-for-ios----2536024---"></a>iOS için Şirket Portalı uygulamasında kullanıcı deneyimi güncelleştirmesi <!-- 2536024 -->
İOS cihazları için Şirket Portalı uygulamasının ana sayfası yeniden tasarlanmıştır. Bu değişiklik ile, giriş sayfası iOS Kullanıcı arabirimi desenlerini daha iyi izler ve ayrıca uygulamalar ve e-kitaplar için geliştirilmiş bulunabilirliği sağlar.

#### <a name="changes-to-company-portal-enrollment-for-ios-12-device-users---3448635---"></a>İOS 12 cihaz kullanıcıları için Şirket Portalı kaydında yapılan değişiklikler <!--3448635 -->  
İOS kayıt ekranları ve adımları için Şirket Portalı, Apple iOS 12,2 ' de yayınlanan MDM kaydı değişiklikleriyle uyum sağlamak üzere güncelleştirilmiştir. Güncelleştirilmiş iş akışı kullanıcılardan şunları yapmanızı ister:  

* Safari 'nin Şirket Portalı Web sitesini açmasına ve Şirket Portalı uygulamasına döndürmeden önce yönetim profilini indirmesine izin verin.  
* Yönetim profilini cihazlarına yüklemek için Ayarlar uygulamasını açın.
* Kaydı tamamlamaya yönelik Şirket Portalı uygulamasına geri dönün.  

Güncelleştirilmiş kayıt adımları ve ekranları için bkz. [iOS cihazını Intune 'A kaydetme](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios).  

## <a name="week-of-march-25-2019"></a>25 Mart 2019 haftası

### <a name="monitor-and-troubleshoot"></a>İzleme ve sorun giderme

### <a name="support-for-the-power-bi-compliance-app-from-the-data-warehouse-blade-in-microsoft-intune----4260871---"></a>Microsoft Intune veri ambarı dikey penceresinden Power BI uyumluluk uygulaması desteği <!-- 4260871 -->
Daha önce, **Intune veri ambarı** dikey penceresindeki **Power BI dosya yükleme** bağlantısı bir Intune veri ambarı raporu (. pbix dosyası) indirilmiştir. Bu rapor Power BI uyumluluk uygulamasıyla değiştirilmiştir. Power BI uyumluluk uygulaması özel yükleme veya kurulum gerektirmez. Power BI çevrimiçi portalda doğrudan açılır ve kimlik bilgilerinizi temel alarak Intune kiracınız için özel olarak verileri görüntüler. Intune ' da, Intune dikey penceresinin sağ tarafındaki **Intune veri ambarını ayarla** bağlantısını seçin. Ardından **Power BI uygulamayı al**' a tıklayın. Daha fazla bilgi için bkz. [Power BI veri ambarına bağlanma](../developer/reports-proc-get-a-link-powerbi.md).

## <a name="week-of-march-18-2019"></a>18 Mart 2019 haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="deploy-microsoft-visio-and-microsoft-project----3725386----"></a>Microsoft Visio ve Microsoft Project 'i dağıtma <!-- 3725386  -->
Artık bu uygulamalar için lisanslarınız varsa, Microsoft Intune kullanarak Windows 10 cihazlarına bağımsız uygulamalar olarak Microsoft Visio 365 Pro 'yu ve Microsoft Project Online masaüstü Istemcisini dağıtabilirsiniz. Intune 'da, **Uygulama Ekle** dikey penceresini göstermek için **istemci uygulamaları** > **uygulamalar** > **Ekle** ' yi seçin. **Uygulama Ekle** dikey penceresinde, **uygulama türü**olarak **Windows 10** ' u seçin. Ardından, yüklenecek uygulamaları seçmek için **uygulama paketini Yapılandır** ' ı seçin. Windows 10 cihazları için Office 365 uygulamaları hakkında daha fazla bilgi için bkz. [Microsoft Intune Ile office 365 uygulamalarını Windows 10 cihazlarına atama](../apps/apps-add-office365.md).

#### <a name="microsoft-visio-pro-for-office-365-product-name-change----3593653----"></a>Office 365 için Microsoft Visio Pro ürün adı değişikliği <!-- 3593653  -->
**Office 365 Için Microsoft Visio Pro** , artık **Microsoft Visio Online Plan 2**olarak bilinirdi.  Microsoft Visio hakkında daha fazla bilgi için bkz. [Visio Online Plan 2](https://products.office.com/visio/visio-online-plan-2). Windows 10 cihazları için Office 365 uygulamaları hakkında daha fazla bilgi için bkz. [Microsoft Intune Ile office 365 uygulamalarını Windows 10 cihazlarına atama](../apps/apps-add-office365.md).

#### <a name="intune-app-protection-policy-app-character-limit-setting----3291302----"></a>Intune uygulama koruma ilkesi (uygulama) karakter sınırı ayarı <!-- 3291302  -->
Intune yöneticileri, Intune UYGULAMASıNıN **diğer uygulamalarla kesme, kopyalama ve yapıştırmayı kısıtla** ilke ayarıyla bir özel durum belirtebilir.  Yönetici olarak, yönetilen bir uygulamadan kesilmiş veya kopyalanmış olabilecek karakter sayısını belirtebilirsiniz. Bu ayar, "diğer uygulamalarla kesme, kopyalama ve yapıştırmayı kısıtla" ayarına bakmaksızın, belirtilen sayıda karakteri herhangi bir uygulamaya paylaşmaya izin verir. Android için Intune Şirket Portalı uygulama sürümünün sürüm 5.0.4364.0 veya üstünü gerektirdiğini unutmayın. Daha fazla bilgi için bkz. [iOS veri koruma](../apps/app-protection-policy-settings-ios.md#data-protection), [Android veri koruma](../apps/app-protection-policy-settings-android.md#data-protection)ve [Istemci uygulama koruma günlüklerini gözden geçirme](../apps/app-protection-policy-settings-log.md#app-protection-policy-settings).

#### <a name="office-deployment-tool-odt-xml-for-office-proplus-deployment----3192477-----"></a>Office ProPlus dağıtımı için Office dağıtım aracı (ODT) XML <!-- 3192477   -->
Intune yönetim konsolunda Office Pro Plus 'ın bir örneğini oluştururken Office dağıtım aracı (ODT) XML sağlayabileceksiniz. Bu, mevcut Intune kullanıcı arabirimi seçeneklerinin gereksinimlerinizi karşılamazsa daha özelleştirme daha büyük bir seçenek sağlar. Daha fazla bilgi için bkz. Office [dağıtım aracı için Microsoft Intune ve yapılandırma seçenekleriyle](https://docs.microsoft.com/DeployOffice/configuration-options-for-the-office-2016-deployment-tool) [Office 365 uygulamalarını Windows 10 cihazlarına atama](../apps/apps-add-office365.md) .

#### <a name="app-icons-will-now-be-displayed-with-an-automatically-generated-background----1429026----"></a>Uygulama simgeleri artık otomatik olarak oluşturulan bir arka planda görüntülenir <!-- 1429026  -->
Windows Şirket Portalı uygulamasında, uygulama simgeleri artık simgenin baskın rengine (algılanıyorsa) bağlı olarak otomatik olarak oluşturulan bir arka planla birlikte görüntülenir. Bu arka plan uygun olduğunda, daha önce uygulama kutucuklarında görünen gri kenarlığın yerini alır. Kullanıcılar, bu değişikliği 10.3.3451.0 ' den sonraki Şirket Portalı sürümlerinde görür.

#### <a name="install-available-apps-using-the-company-portal-app-after-windows-bulk-enrollment----2751523-----"></a>Windows toplu kayıt sonrasında Şirket Portalı uygulamasını kullanarak kullanılabilir uygulamaları yükler <!-- 2751523   -->
[Windows Toplu kaydı](../enrollment/windows-bulk-enroll.md) (sağlama paketleri) kullanılarak Intune 'a kaydedilen Windows cihazları, kullanılabilir uygulamaları yüklemek için şirket portalı uygulamasını kullanabilir. Şirket Portalı uygulaması hakkında daha fazla bilgi için bkz. [Windows 10 Şirket portalı el ile ekleme](../apps/store-apps-company-portal-app.md) ve [Microsoft Intune şirket portalı uygulamasını yapılandırma](../apps/company-portal-app.md).

#### <a name="the-microsoft-teams-app-can-be-selected-as-part-of-the-office-app-suite----3828932----"></a>Microsoft ekipleri uygulaması Office uygulama paketi 'nin bir parçası olarak seçilebilir <!-- 3828932  -->
Microsoft ekipleri uygulaması, Office Pro Plus App Suite yüklemesinin bir parçası olarak dahil edilebilir veya hariç tutulamaz. Bu özellik Office Pro Plus derleme numarası 16.0.11328.20116 + için geçerlidir. Yüklemenin tamamlanabilmesi için kullanıcının oturumu kapatıp cihazda oturum açması gerekir. Intune 'da, **istemci uygulamaları** > **uygulama** > **Ekle**' yi seçin. **Office 365 Suite** uygulama türlerinden birini seçin ve ardından **uygulama paketini Yapılandır**' ı seçin.

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="automatically-start-an-app-when-running-multiple-apps-in-kiosk-mode-on-windows-10-and-later-devices----2351390---"></a>Windows 10 ve üzeri cihazlarda bilgi noktası modunda birden çok uygulama çalıştırırken otomatik olarak bir uygulama Başlat <!-- 2351390 -->

Windows 10 ve üzeri cihazlarda, bir cihazı bilgi noktası modunda çalıştırabilir ve birçok uygulama çalıştırabilirsiniz. Bu güncelleştirmede bir **oto başlatma** ayarı (**cihaz yapılandırma** > **profilleri** >  profil**oluşturmak**için Platform > **bilgi** > **noktası  >  Windows 10 ve üzeri). Birden çok uygulama bilgi noktası**). Kullanıcı cihazda oturum açtığında uygulamayı otomatik olarak başlatmak için bu ayarı kullanın.

Tüm bilgi noktası ayarlarının listesini ve açıklamasını görmek için bkz. [Windows 10 ve üzeri cihaz ayarları Intune 'da bilgi noktası olarak çalışacak şekilde](../configuration/kiosk-settings-windows.md).

Şunlar için geçerlidir: Windows 10 ve üzeri

#### <a name="operational-logs-also-show-details-on-non-compliant-devices----4063755----"></a>İşlemsel günlüklerde Ayrıca uyumlu olmayan cihazlarda ayrıntılar gösterilir <!-- 4063755  -->
Intune günlüklerini Azure izleyici özelliklerine yönlendirdiğinizde, işletimsel günlükleri de yönlendirebilirsiniz. Bu güncelleştirmede, işletimsel Günlükler uyumlu olmayan cihazlar hakkında bilgi de sağlar. 

Bu özellik hakkında daha fazla bilgi için bkz. [Intune 'da günlük verilerini depolama, Olay Hub 'larına veya Log Analytics 'e gönderme](../review-logs-using-azure-monitor.md).

#### <a name="route-logs-to-azure-monitor-in-more-intune-workloads----3804627---"></a>Daha fazla Intune iş yüklerinde günlükleri Azure Izleyici 'ye yönlendirme <!-- 3804627 -->
Intune 'da, denetim ve işletimsel günlükleri Azure Izleyici 'de Olay Hub 'ları, depolama ve Log Analytics 'e yönlendirebilir (**ıntune** > **izleme** > **Tanılama ayarları**). Bu güncelleştirmede, bu günlükleri uyumluluk, konfigürasyonlar, istemci uygulamaları ve daha fazlası dahil olmak üzere daha fazla Intune iş yüküne yönlendirebilirsiniz. 

Günlükleri Azure Izleyici 'ye yönlendirme hakkında daha fazla bilgi edinmek için bkz. [depolama, Olay Hub 'ları veya Log Analytics 'e günlük verileri gönderme](../review-logs-using-azure-monitor.md).

#### <a name="create-and-use-mobility-extensions-on-android-zebra-devices-in-intune----3305880-----"></a>Intune 'da Android Zeköşeli cihazlarda Mobility uzantıları oluşturma ve kullanma <!-- 3305880   -->
Bu güncelleştirmede Intune, Android Zeköşeli cihazlarını yapılandırmayı destekler. Özellikle, bir cihaz yapılandırma profili oluşturabilir ve StageNow (**cihaz yapılandırma** > **profilleri** > **profil oluşturma tarafından oluşturulan Mobility uzantıları (MX) profillerini kullanarak Android zeköşeli cihazlarına ayarları uygulayabilirsiniz**  > **Android** for platform > **MX profile (yalnızca zeköşeli)** profil türü için).

Bu özellik hakkında daha fazla bilgi için bkz. [Intune 'da Mobility uzantıları Ile Zeköşeli cihazları kullanma ve yönetme](../configuration/android-zebra-mx-overview.md).

Uygulama hedefi: Android

### <a name="device-management"></a>Cihaz yönetimi

#### <a name="encryption-report-for-windows-10-devices-in-public-preview---2351538---"></a>Windows 10 cihazları için şifreleme raporu (genel önizlemede)<!-- 2351538 -->  
Windows 10 cihazlarınızın şifreleme durumuyla ilgili ayrıntıları görüntülemek için yeni [şifreleme raporu (Önizleme)](../protect/encryption-monitor.md) kullanın. Kullanılabilir Ayrıntılar arasında bir cihaz TPM sürümü, şifreleme hazırlığı ve durumu, hata raporlama ve daha fazlası bulunur.  

#### <a name="access-bitlocker-recovery-keys-from-the-intune-portal-in-public-preview----2351547-----"></a>Intune portalından BitLocker Kurtarma anahtarlarına erişme (genel önizlemede) <!-- 2351547   -->  
Artık Azure Active Directory 'tan BitLocker anahtar KIMLIĞI ve BitLocker kurtarma anahtarları hakkındaki [ayrıntıları görüntülemek](../protect/encryption-monitor.md) için Intune 'u kullanabilirsiniz.

#### <a name="microsoft-edge-support-for-intune-scenarios-on-ios-and-android-devices----3411007---"></a>İOS ve Android cihazlarda Intune senaryoları için Microsoft Edge desteği <!-- 3411007 -->
Microsoft Edge, son kullanıcı deneyimine yönelik geliştirmelerin eklenmesiyle birlikte Intune Managed Browser aynı yönetim senaryolarını destekleyecektir. Intune ilkeleri tarafından etkinleştirilen Microsoft Edge kurumsal özellikleri arasında çift kimlik, uygulama koruma ilkesi tümleştirmesi, Azure uygulama proxy tümleştirmesi ve yönetilen sık kullanılanlar ve giriş sayfası kısayolları bulunur. Daha fazla bilgi için bkz. [Microsoft Edge desteği](../apps/app-configuration-managed-browser.md#microsoft-edge-support).

#### <a name="exchange-onlineintune-connector-deprecate-support-for-eas-only-devices---3105122----"></a>Exchange Online/Intune Bağlayıcısı, yalnızca EAS cihazları için desteği kullanımdan kaldırır <!--3105122  -->
Intune Konsolu artık Intune Bağlayıcısı ile Exchange Online 'a bağlı olan EAS cihazların görüntülenmesini ve yönetilmesini desteklememektedir. Bunun yerine, aşağıdaki seçeneklere sahip olursunuz:
- Cihazları mobil cihaz yönetimine (MDM) kaydetme
- Cihazlarınızı yönetmek için Intune Uygulama Koruması Ilkeleri kullanma
- Exchange [Online 'Da istemciler ve mobil](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/clients-and-mobile-in-exchange-online) bölümünde özetlenen Exchange denetimlerini kullanın

### <a name="search-the-all-devices-page-for-an-exact-device-by-using-name---4254930---"></a>Tüm cihazlar sayfasında [ad] kullanarak tam bir cihaz arayın <!--4254930 -->
Artık tam bir cihaz adı araması yapabilirsiniz. **Intune** > **cihazlara**git  > **tüm cihazlar** arama kutusunda >, tam bir eşleşme aramak için cihaz adını {} ile çevreleyin. Örneğin, **{Device12345}** .

### <a name="monitor-and-troubleshoot"></a>İzleme ve sorun giderme

#### <a name="support-for-additional-connectors-on-the-tenant-status-page----3617202----"></a>Kiracı durum sayfasında ek bağlayıcılar için destek <!-- 3617202  -->
[Kiracı durumu sayfası](../tenant-status.md) artık *Windows Defender Gelişmiş tehdit koruması* (ATP) ve diğer Mobile Threat Defense bağlayıcıları dahil olmak üzere ek bağlayıcıların durum bilgilerini görüntüler.

### <a name="role-based-access-control"></a>Rol tabanlı erişim denetimi

#### <a name="granting-intune-read-only-access-to-some-azure-active-directory-roles----3637917----"></a>Intune 'un bazı Azure Active Directory rollerine salt okuma erişimi verme <!-- 3637917  -->
Intune salt okuma erişimi aşağıdaki Azure AD rollerine verildi. Azure AD rolleriyle verilen izinler, Intune rol tabanlı erişim denetimi (RBAC) ile verilen izinlerin yerini alır.

Intune denetim verilerine salt okuma erişimi:

- Uyumluluk Yöneticisi
- Uyumluluk verileri Yöneticisi

Tüm Intune verilerine salt okuma erişimi:

- Güvenlik Yöneticisi
- Güvenlik operatörü
- Güvenlik okuyucusu

Daha fazla bilgi için bkz. [rol tabanlı erişim denetimi](role-based-access-control.md).

#### <a name="scope-tags-for-ios-app-provisioning-profiles---2934430-----"></a>İOS uygulama sağlama profillerinin kapsam etiketleri <!--2934430   -->
Bir iOS uygulama sağlama profiline bir kapsam etiketi ekleyebilirsiniz, böylece yalnızca rollere sahip olan kişilerin iOS uygulama sağlama profiline erişimi vardır. Daha fazla bilgi için bkz. [RBAC ve kapsam etiketlerini kullanma](scope-tags.md).

#### <a name="scope-tags-for-app-configuration-policies---2371891-----"></a>Uygulama yapılandırma ilkeleri için kapsam etiketleri <!--2371891   -->
Bir uygulama yapılandırma ilkesine kapsam etiketi ekleyebilirsiniz, böylece yalnızca rollere sahip olan kişilerin uygulama yapılandırma ilkesine erişimi vardır. Uygulama yapılandırma ilkesi yalnızca aynı kapsam etiketine atanmış olan uygulamaları hedefleyebilir veya bunlarla ilişkilendirilebilir. Daha fazla bilgi için bkz. [RBAC ve kapsam etiketlerini kullanma](scope-tags.md).

### <a name="microsoft-edge-support-for-intune-scenarios-on-ios-and-android-devices----3411007---"></a>İOS ve Android cihazlarda Intune senaryoları için Microsoft Edge desteği <!-- 3411007 -->
Microsoft Edge, son kullanıcı deneyimine yönelik geliştirmelerin eklenmesiyle birlikte Intune Managed Browser aynı yönetim senaryolarını destekleyecektir. Intune ilkeleri tarafından etkinleştirilen Microsoft Edge kurumsal özellikleri arasında çift kimlik, uygulama koruma ilkesi tümleştirmesi, Azure uygulama proxy tümleştirmesi ve yönetilen sık kullanılanlar ve giriş sayfası kısayolları bulunur. Daha fazla bilgi için bkz. [Microsoft Edge desteği](../apps/app-configuration-managed-browser.md#microsoft-edge-support).

## <a name="week-of-february-25-2019"></a>25 Şubat 2019 haftası

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="intune-powershell-module----951068----"></a>Intune PowerShell modülü <!-- 951068  -->
Intune API 'SI için Microsoft Graph aracılığıyla destek sağlayan Intune PowerShell modülü, [Microsoft PowerShell Galerisi](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1902.1.10)artık kullanılabilir.

- [Bu modülün nasıl kullanıldığı hakkında ayrıntılar](https://github.com/Microsoft/Intune-PowerShell-SDK/blob/master/README.md)
- [Bu modülü kullanan senaryo örnekleri](https://github.com/Microsoft/Intune-PowerShell-SDK/blob/master/Samples/README.md)

#### <a name="improved-support-for-delivery-optimization----3183757----"></a>Teslim iyileştirme için geliştirilmiş destek  <!--3183757  -->
Teslim iyileştirme 'yi yapılandırmak için Intune 'da desteği genişlettik. Artık, bir [dağıtım iyileştirme ayarlarının](../configuration/delivery-optimization-settings.md) genişletilmiş bir listesini yapılandırabilir ve doğrudan Intune konsolundan cihazlarınıza hedefleyebilirsiniz.


## <a name="week-of-february-18-2019"></a>18 Şubat 2019 haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="intune-will-leverage-google-play-protect-apis-on-android-devices----2577355-----"></a>Intune, Android cihazlarda API 'Leri koruma Google Play faydalanır <!-- 2577355   -->
Bazı BT yöneticileri, son kullanıcıların mobil telefonlarını veya jailbreaking bir şekilde sona erdirmek için bir KCG yataya sahip olur. Bu davranış, bazen de çok daha fazla olmasa da, Son Kullanıcı cihazlarındaki kuruluşun verilerini korumak için ayarlanmış birçok Intune ilkesinin atlanmasına neden olur. Bu nedenle, Intune hem kayıtlı hem de kayıtlı olmayan cihazlar için kök ve jailbreak algılama sağlar. Bu sürümde, Intune artık kayıtlı olmayan cihazlar için mevcut kök algılama denetimlerimize eklemek üzere API 'Leri Google Play korur. Google, kök algılama denetimlerinden tamamen paylaşmadığı sürece, bu API 'Lerin cihazlarını, cihaz özelleştirmesinden, eski cihazlarda daha yeni işletim sistemi güncelleştirmelerini alabilmesi için kendilerine ait olan kullanıcıları algılamasını bekledik. Daha sonra bu kullanıcıların şirket verilerine erişimi engellenebilir veya şirket hesapları ilke etkin uygulamalarından silinebilirler. Daha fazla değer için, BT yöneticisinin artık Intune Uygulama Koruması dikey penceresinde birkaç raporlama güncelleştirmesi olacaktır. "bayraklı kullanıcılar" raporu, Google Play Protect 'ın SafetyNet API taraması aracılığıyla hangi kullanıcıların algılandığını gösterir, "olası zararlı uygulamalar" raporu Google 'ın uygulama API 'SI taramasını doğrulama aracılığıyla hangi uygulamaların algılandığını gösterir. Bu özellik Android 'de kullanılabilir.

#### <a name="win32-app-information-available-in-troubleshooting-blade----2617342-----"></a>Sorun giderme dikey penceresinde kullanılabilir Win32 uygulama bilgileri <!-- 2617342   -->
Artık, Intune uygulama **sorun giderme** dikey penceresinden bir Win32 uygulama yüklemesi için hata günlüğü dosyalarını toplayabilirsiniz. Uygulama yükleme sorunlarını giderme hakkında daha fazla bilgi için bkz. [uygulama yükleme sorunlarını giderme](./../apps/troubleshoot-app-install.md) ve [Win32 uygulama sorunlarını giderme](./../apps/troubleshoot-app-install.md#win32-app-installation-troubleshooting).

#### <a name="app-status-details-for-ios-apps----3761235-----"></a>İOS uygulamaları için uygulama durumu ayrıntıları <!-- 3761235   -->
Aşağıdakiler ile ilgili yeni uygulama yükleme hatası iletileri vardır:
- Paylaşılan iPad üzerine yüklerken VPP uygulamaları için hata
- Uygulama Mağazası devre dışı bırakıldığında hata
- Uygulama için VPP lisansı bulunamadı
- MDM sağlayıcısı ile sistem uygulamalarını yüklemede hata
- Cihaz kayıp modundayken veya bilgi noktası modundayken uygulamalar yüklenememesi
- Kullanıcı uygulama mağazası 'nda oturum açmamışsa uygulamanın yüklenmesi başarısız oldu

Intune 'da **istemci uygulamaları**@no__t **-1 >** "uygulama adı" > **cihaz yüklemesi durumu**' nu seçin. Yeni hata iletileri **durum ayrıntıları** sütununda kullanıma sunulacaktır.

#### <a name="new-app-categories-screen-in-the-company-portal-app-for-windows-10---3834780----"></a>Windows 10 için Şirket Portalı uygulamasındaki yeni uygulama kategorileri ekranı<!-- 3834780  -->
Windows 10 için Şirket Portalı ' de uygulama gözatma ve seçim deneyimini geliştirmek için **uygulama kategorileri** adlı yeni bir ekran eklenmiştir. Kullanıcılar, uygulamalarını **öne çıkan**, **eğitim**ve **üretkenlik**gibi Kategoriler altında sıralanmış olarak görecektir. Bu değişiklik, 10.3.3451.0 ve sonraki sürümlerde Şirket Portalı görüntülenir. Yeni ekranı görüntülemek için bkz. [uygulama kullanıcı arabirimindeki](whats-new-app-ui.md)yenilikler. Şirket Portalı uygulamalar hakkında daha fazla bilgi için bkz. [cihazınızdaki uygulamaları yükleyip paylaşma](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows).  

#### <a name="power-bi-compliance-app----1455231-doc-work-item---"></a>Uyumluluk uygulaması Power BI <!-- 1455231 doc-work-item -->
Intune [Uyumluluk (veri ambarı)](https://aka.ms/intune/datawarehouseapi/getpowerbiapp) uygulamasını kullanarak Power BI çevrimiçi ortamda Intune veri ambarınıza erişin. Bu Power BI uygulamayla, artık önceden oluşturulmuş raporlara herhangi bir kurulum olmadan ve Web tarayıcınızdan çıkmadan erişebilir ve bunları paylaşabilirsiniz. Daha fazla bilgi için bkz. [günlük Power BI uyumluluk uygulamasını değiştirme](../developer/reports-changelog.md#power-bi-compliance-app).


### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="powershell-scripts-can-run-in-a-64-bit-host-on-64-bit-devices----1862675-----"></a>PowerShell betikleri, 64 bit cihazlarda 64 bitlik bir konakta çalışabilir <!-- 1862675   -->
Bir cihaz yapılandırma profiline bir PowerShell betiği eklediğinizde, komut dosyası her zaman 64 bit işletim sistemlerinde bile 32 bit içinde yürütülür. Bu güncelleştirmeyle, bir yönetici, komut dosyasını 64 bit cihazlarda 64 bitlik bir PowerShell konağında çalıştırabilir (**cihaz yapılandırma** > **PowerShell betikleri** > **Add** > **yapılandırma** > **komut dosyasını 64 bit içinde Çalıştır PowerShell ana bilgisayarı**).

PowerShell kullanma hakkında daha fazla ayrıntı için bkz. [Intune 'Da PowerShell betikleri](../apps/intune-management-extension.md).

Şunlar için geçerlidir: Windows 10 ve üzeri

#### <a name="macos-users-are-prompted-to-update-their-password----1873216---"></a>macOS kullanıcılarının parolasını güncelleştirmesi istenir <!-- 1873216 -->
Intune, macOS cihazlarında **Changeatnextauth** ayarını zorlarken. Bu ayar, uyumluluk parolası ilkeleri veya cihaz kısıtlama parolası profilleri olan son kullanıcıları ve cihazları etkiler. Son kullanıcılara parolasını güncelleştirmek için bir kez sorulur. Bu istem, bir Kullanıcı, cihazda oturum açma gibi kimlik doğrulaması gerektiren bir görevi ilk kez çalıştırdığında oluşur. Kullanıcıların, anahtar zinciri erişimi istemek gibi yönetim ayrıcalıkları gerektiren her şeyi yaparken parolalarını güncelleştirmesi de istenebilir. 

Yönetici tarafından yeni veya var olan parola ilkesi değişiklikleri, son kullanıcılara parolasını güncelleştirmek üzere yeniden bir kez daha.

Uygulama hedefi:  
Mac OS

#### <a name="assign-scep-certificates-to-a-userless-macos-device-------2340521------"></a>Kullanıcısız macOS cihazına SCEP sertifikaları atama    <!-- 2340521    -->
Kullanıcı benzeşimi olmayan cihazlar dahil olmak üzere macOS cihazlarına cihaz özniteliklerini kullanarak Basit Sertifika Kayıt Protokolü (SCEP) sertifikaları atayabilir ve sertifika profilini Wi-Fi veya VPN profilleriyle ilişkilendirebilirsiniz. Bu, Windows, iOS ve Android çalıştıran [Kullanıcı benzeşimi ile ve olmayan CIHAZLARA SCEP sertifikaları atamak](../protect/certificates-profile-scep.md) için zaten sahip olduğumuz desteği genişletir.  Bu güncelleştirme, macOS için bir SCEP sertifika profili yapılandırırken *cihazın* sertifika türünü seçme seçeneğini ekler.

Uygulama hedefi: 
- Mac OS

#### <a name="intune-conditional-access-ui-update------2432313-----"></a>Intune koşullu erişim kullanıcı arabirimi güncelleştirmesi   <!-- 2432313   -->
Intune konsolunda koşullu erişim için Kullanıcı arabiriminde geliştirmeler yaptık. Bunlar şunları içerir:
- Intune *koşullu erişim* dikey penceresi Azure Active Directory dikey penceresinde değiştirildi. Bu, Intune konsolunun içinden [koşullu erişime](../protect/conditional-access.md) (Azure AD teknolojisi olarak kalır) yönelik ayarların ve yapılandırmaların tam aralığına erişmenizi sağlar. 
- *Şirket içi erişim* dikey penceresini *Exchange erişimi*olarak yeniden adlandırdık ve *Exchange hizmeti Bağlayıcısı* kurulumunu bu yeniden adlandırılmış dikey pencereye yeniden konumlandırdık.  Bu değişiklik, [Exchange Online ve şirket içi ile ilgili ayrıntıları yapılandırdığınız ve](../protect/exchange-connector-install.md)izlediğiniz yerleri birleştirir.  

#### <a name="kiosk-browser-and-microsoft-edge-browser-apps-can-run-on-windows-10-devices-in-kiosk-mode----2935135-----"></a>Bilgi noktası tarayıcısı ve Microsoft Edge tarayıcı uygulamaları, Windows 10 cihazlarında bilgi noktası modunda çalışabilir <!-- 2935135   -->
Windows 10 cihazlarını bilgi noktası modunda kullanarak bir uygulamayı veya birçok uygulamayı çalıştırabilirsiniz. Bu güncelleştirme, aşağıdakiler dahil olmak üzere tarayıcı uygulamalarını bilgi noktası modunda kullanmak için çeşitli değişiklikler içerir:

- Bilgi noktası cihazında (**cihaz yapılandırma** > **profilleri** > **Yeni profil** > **Windows 10 ve üzeri** profil türü Için platform > **bilgi noktası** için Microsoft Edge tarayıcı veya bilgi noktası tarayıcısı 'nı ekleyin ).
- Yeni özellikler ve ayarlar, izin verme veya kısıtlama (**cihaz yapılandırma** > **profilleri** > **Yeni profil** > **Windows 10 ve üzeri** profil türü için Platform > **cihaz kısıtlamaları** ) için kullanılabilir. işaretleriyle

- Microsoft Edge tarayıcısı:
  - Microsoft Edge bilgi noktası modunu kullan
  - Boşta kalma zamanından sonra tarayıcıyı yenile

- Sık Kullanılanlar ve arama:
  - Arama altyapısında değişikliklere izin ver

Bu ayarların listesi için bkz.:

- [Bilgi noktası olarak çalıştırılacak Windows 10 ve üzeri cihaz ayarları](../configuration/kiosk-settings-windows.md)
- [Microsoft Edge tarayıcı cihaz kısıtlamaları](../configuration/device-restrictions-windows-10.md#microsoft-edge-browser)
- [Sık Kullanılanlar ve arama cihaz kısıtlamaları](../configuration/device-restrictions-windows-10.md##favorites-and-search)

Şunlar için geçerlidir: Windows 10 ve üzeri

#### <a name="new-device-restriction-settings-for-ios-and-macos-devices----3448774-----"></a>İOS ve macOS cihazları için yeni cihaz kısıtlama ayarları <!-- 3448774   -->
İOS ve macOS çalıştıran cihazlarda bazı ayarları ve özellikleri kısıtlayabilirsiniz (**cihaz yapılandırma** > **profilleri** > **Yeni profil** > **IOS** veya **MacOS** for platform > **cihaz kısıtlamaları** profil türü için). Bu güncelleştirme, iOS cihazlarında ekran zamanını ayarlama, esım ayarlarını ve hücresel planları değiştirme dahil olmak üzere denetleyebilmeniz için daha fazla özellik ve ayar ekler. Ayrıca, kullanıcının yazılım güncelleştirmelerinin görünürlüğünü erteleyerek macOS cihazlarında içerik önbelleğe almayı engelleyerek. 

Kısıtlayabilecek özellikleri ve ayarları görmek için bkz.:

- [iOS cihaz kısıtlama ayarları](../configuration/device-restrictions-ios.md)
- [macOS cihaz kısıtlama ayarları](../configuration/device-restrictions-macos.md)

Uygulama hedefi:

- iOS
- Mac OS

#### <a name="kiosk-devices-are-now-called-dedicated-devices-on-android-enterprise-devices----3598402-----"></a>"Bilgi noktası" cihazları artık Android kurumsal cihazlarda "adanmış cihazlar" olarak adlandırılır <!-- 3598402   -->
Android terimlerle uyum sağlamak için, **bilgi noktası** , Android Kurumsal cihazları için **adanmış cihazlara** değiştirilmiştir (**cihaz yapılandırma** > **profilleri** > **Profil oluştur** > * * Android Enterprise for platform @No__t **yalnızca cihaz sahibi**>-8**cihaz kısıtlamaları**0**adanmış**cihaz).

Kullanılabilir ayarları görmek için cihaz ayarları ' na giderek [özelliklere izin verin veya kısıtlayın](../configuration/device-restrictions-android-for-work.md#dedicated-device-settings).

Uygulama hedefi:  
Android Kurumsal

#### <a name="safari-and-delaying-user-software-update-visibility-ios-settings-are-moving-in-the-intune-ui----3640850-3803313-----"></a>Safari ve erteleme Kullanıcı yazılımı güncelleştirme görünürlüğü iOS ayarları, Intune kullanıcı arabiriminde taşınıyor <!-- 3640850, 3803313   -->
İOS cihazları için Safari ayarlarını ayarlayabilir ve yazılım güncelleştirmelerini yapılandırabilirsiniz. Bu güncelleştirmede, bu ayarlar Intune kullanıcı arabiriminin farklı bölümlerine taşınıyor:

- Safari ayarları **Safari** 'den (**cihaz yapılandırma** > **profilleri** > **Yeni profil** > **iOS** , profil türü için Platform > **cihaz kısıtlamaları** ) **[yerleşik uygulamalara](../configuration/device-restrictions-ios.md#built-in-apps)** taşınır.
- **Denetimli iOS cihazları için Kullanıcı yazılım güncelleştirme görünürlüğünü geciktirme** ayarı (IOS için**yazılım güncelleştirmeleri** > **güncelleştirme ilkeleri**) **cihaz kısıtlamalarına**taşınıyor  >  **[genel](../configuration/device-restrictions-ios.md#general)** .  Var olan ilkelere etkisi hakkında ayrıntılar için bkz. [iOS yazılım güncelleştirmeleri](../protect/software-updates-ios.md#configure-the-policy). 

Ayarların listesi için bkz.:

- [iOS cihaz kısıtlamaları](../configuration/device-restrictions-ios.md) 
- [iOS yazılım güncelleştirmeleri](../protect/software-updates-ios.md)

Bu özellik şu platformlarda geçerlidir: 

- iOS

#### <a name="enabling-restrictions-in-the-device-settings-is-renamed-to-screen-time-on-ios-devices----3699164-----"></a>Cihaz ayarlarında kısıtlamaları etkinleştirme, iOS cihazlarında ekran zamanına göre yeniden adlandırılır <!-- 3699164   -->
Denetimli iOS cihazlarında **cihaz ayarlarında etkinleştirme kısıtlamalarını** yapılandırabilirsiniz (**cihaz yapılandırma** > **profilleri** > **Yeni profil** >  Platform > için**iOS** **cihaz** profil türü için kısıtlamalar > **genel**). Bu güncelleştirmede, bu ayar ekran zamanı olarak yeniden adlandırılır **(yalnızca denetimli)** . 

Davranış aynıdır. Engelle 

- iOS 11.4.1 ve önceki sürümler: **Block** , son kullanıcıların cihaz ayarlarında kendi kısıtlamalarını değiştirmesini engeller. 
- iOS 12,0 ve üzeri: **blok** , son kullanıcıların, içerik & Gizlilik kısıtlamaları da dahil olmak üzere cihaz ayarları 'Nda kendi **Ekran zamanını** ayarlamalarını engeller. İOS 12,0 ' e yükseltilen cihazlar artık cihaz ayarlarındaki kısıtlamalar sekmesini görmez. Bu ayarlar **Ekran Saati** altındadır. 

Ayarların listesi için bkz. [iOS cihaz kısıtlamaları](../configuration/device-restrictions-ios.md#general).

Uygulama hedefi: 
- iOS


### <a name="device-management"></a>Cihaz yönetimi

#### <a name="rename-an-enrolled-windows-device----1911112----"></a>Kayıtlı bir Windows cihazını yeniden adlandırma <!-- 1911112  -->
Artık kayıtlı bir Windows 10 cihazını (RS4 veya üzeri) yeniden adlandırabilirsiniz. Bunu yapmak için **ıntune**@no__t **-1 cihaz** > **tüm cihazlar** ' ı seçin > cihazı **Yeniden Adlandır**> bir cihaz seçin. Bu özellik şu anda karma Azure AD Windows cihazlarının yeniden adlandırılmasını desteklemiyor.

#### <a name="auto-assign-scope-tags-to-resources-created-by-an-admin-with-that-scope----3173823----"></a>Kapsam etiketlerini bu kapsama sahip bir yönetici tarafından oluşturulan kaynaklara otomatik olarak ata <!-- 3173823  -->
Yönetici bir kaynak oluşturduğunda, yöneticiye atanan tüm kapsam etiketleri bu yeni kaynaklara otomatik olarak atanır.

### <a name="monitor-and-troubleshoot"></a>İzleme ve sorun giderme

#### <a name="failed-enrollment-report-moves-to-the-device-enrollment-blade----3560202----"></a>Başarısız kayıt raporu cihaz kayıt dikey penceresine taşınıyor <!-- 3560202  -->
**Başarısız** kayıtları raporu, **cihaz kaydı** dikey **penceresinin izleyici** bölümüne taşınmıştır. İki yeni sütun (kayıt yöntemi ve işletim sistemi sürümü) eklenmiştir.

#### <a name="company-portal-abandonment-report-renamed-to-incomplete-user-enrollments---3815076-eemiss---"></a>Şirket Portalı bırakma raporu, tamamlanmamış Kullanıcı kayıtlarına yeniden adlandırıldı <!--3815076 eemiss -->
**Şirket portalı bırakma** raporu, **tamamlanmamış Kullanıcı**kayıtları olarak yeniden adlandırıldı.


<!-- ########################## -->
## <a name="week-of-february-4-2019"></a>4 Şubat 2019 haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="intune-macos-company-portal-dark-mode----3300524----"></a>Şirket Portalı koyu modda Intune macOS <!-- 3300524  -->
Intune macOS Şirket Portalı artık macOS için koyu modu desteklemektedir. MacOS 10.14 + cihazında koyu modu etkinleştirdiğinizde Şirket Portalı, görünümü bu modu yansıtan renklerle ayarlar.

<!-- ########################## -->
## <a name="week-of-january-21-2019"></a>21 Ocak 2019 haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="toast-notifications-for-win32-apps----3136566-----"></a>Win32 uygulamaları için bildirim bildirimleri <!-- 3136566   -->
Her uygulama ataması için son kullanıcı bildirim bildirimlerini göstermeyi bastırın. Intune 'da, **istemci uygulamaları** > **uygulamalar** ' ı seçin > Uygulama > **atamaları** > **Ekle grupları**' nı seçin. 

#### <a name="intune-app-protection-policies-ui-update----3251427----"></a>Intune uygulama koruma ilkeleri kullanıcı arabirimi güncelleştirmesi <!-- 3251427  -->
Intune uygulama koruması için ayarların ve düğmelerin etiketlerini, her birinin anlaşılması kolay hale getirmek üzere değiştirdik. Bazı değişiklikler şunları içerir:  
- Denetimler **evet**@no__t değiştirilir **-1 birincil** olarak **blok** / **izin ver** ve **devre dışı bırak** / **Etkinleştir** denetimleri. Etiketler de güncelleştirilir.  
- Ayarlar yeniden biçimlendirilir, bu nedenle daha iyi gezinti sağlamak için ayar ve etiketi denetimin içinde yan yana olur.   

Varsayılan ayarlar ve ayar sayısı aynı kalır, ancak bu değişiklik kullanıcının seçili uygulama koruma ilkelerini uygulamak için ayarları daha kolay anlamasına, gezinmeye ve kullanmasına olanak sağlar. Bilgi için bkz. [iOS ayarları](../apps/app-protection-policy-settings-ios.md) ve [Android ayarları](../apps/app-protection-policy-settings-android.md).

### <a name="additional-settings-for-outlook----3301182----"></a>Outlook için ek ayarlar <!-- 3301182  -->
Artık Intune kullanarak iOS ve Android için Outlook için aşağıdaki ek ayarları yapılandırabilirsiniz:

- İOS ve Android 'de Outlook 'ta yalnızca iş veya okul hesaplarının kullanılmasına izin ver
- Office 365 ve karma modern kimlik doğrulaması şirket içi hesaplar için modern kimlik doğrulaması dağıtma
- Temel kimlik doğrulaması seçildiğinde e-posta profilindeki Kullanıcı adı alanı için `SAMAccountName` kullanın
- Kişilerin kaydedilmesine izin ver
- Dış alıcıları yapılandırma posta Ipuçları
- **Odaklanmış gelen kutusu** yapılandırma
- İOS için Outlook 'a erişmek üzere Biyometri iste
- Dış görüntüleri engelle

> [!NOTE]
> Şirket kimliklerine erişimi yönetmek için Intune Uygulama Koruması ilkeleri kullanıyorsanız, **Biyometri gerektir**' i etkinleştirmemelisiniz. Daha fazla bilgi için bkz. [IOS erişim ayarları](../apps/app-protection-policy-settings-ios.md#access-requirements) ve [Android erişim ayarları](../apps/app-protection-policy-settings-android.md#access-requirements)için **erişim için kurumsal kimlik bilgileri gerektir** .

Daha fazla bilgi için bkz. [Microsoft Outlook yapılandırma ayarları](../apps/app-configuration-policies-outlook.md).

#### <a name="delete-android-enterprise-apps----1352553---"></a>Android kurumsal uygulamalarını silme <!-- 1352553 -->
Microsoft Intune yönetilen Google Play uygulamalarını silebilirsiniz. Yönetilen Google Play uygulamasını silmek için Azure portalında Microsoft Intune'u açın ve **İstemci uygulamaları** > **Uygulamalar**'ı seçin. Uygulama listesinden, yönetilen Google Play uygulamasının sağ tarafındaki üç noktayı (...) seçin ve görüntülenen listeden **Sil**'i seçin. Uygulama listesinden yönetilen Google Play uygulamasını sildikten sonra, yönetilen Google Play uygulamasının onayı otomatik olarak kaldırılır.

#### <a name="managed-google-play-app-type----1352580---"></a>Yönetilen Google Play uygulama türü <!-- 1352580 -->
**Yönetilen Google Play** uygulama türü, Intune 'a [yönetilen Google Play uygulamalarını](https://play.google.com/work/search?q=microsoft&c=apps) özel olarak eklemenize olanak tanır. Intune Yöneticisi olarak artık Intune 'da onaylanan yönetilen Google Play uygulamalarına gözatıp arayabilir, bunları onaylayabilir, eşitleyebilir ve atayabilirsiniz.  Artık ayrıca yönetilen Google Play konsoluna göz atmanız ve yeniden kimlik doğrulaması yapmanız gerekmez.  Intune 'da, **istemci uygulamaları** > **uygulama** > **Ekle**' yi seçin. **Uygulama türü** listesinde, uygulama türü olarak **yönetilen Google Play** ' yi seçin.

### <a name="default-android-pin-keyboard----3802457---"></a>Varsayılan Android PIN klavyesi <!-- 3802457 -->
Android cihazlarında ' numeric ' PIN türüyle Intune Uygulama Koruması Ilkesi (uygulama) PIN 'i ayarlamış olan son kullanıcılar için, daha önce tasarlanmış olan sabit Android Klavye Kullanıcı arabirimi yerine varsayılan Android klavye görüntülenir. Bu değişiklik, hem Android hem de iOS 'ta varsayılan klavye kullanılırken ' numeric ' ve/veya ' geçiş kodu ' olan her iki PIN türü için de tutarlı hale getirilir. Android 'de uygulama PIN 'i gibi son kullanıcı erişimi ayarları hakkında daha fazla bilgi için bkz. [Android erişim gereksinimleri](../apps/app-protection-policy-settings-android.md#access-requirements).

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="use-microsoft-recommended-settings-with-security-baselines-public-preview----2055484-----"></a>Microsoft tarafından önerilen ayarları güvenlik temellerinde kullanın (Genel Önizleme) <!-- 2055484   -->

Intune, Windows Defender ATP ve Office 365 ATP dahil güvenliğe odaklı diğer hizmetlerle tümleşir. Müşteriler, Microsoft 365 hizmetleri çapında ortak bir strateji ve birbiriyle bütünleşen bir dizi uçtan uca güvenlik iş akışı istiyor. Amacımız, stratejileri birbiriyle uyumlu hale getirmek ve güvenlik işlemleri ve sık kullanılan yönetici görevleri arasında bir köprü oluşturan çözümler geliştirmek. Intune olarak bu amaca Microsoft tarafından önerilen bir dizi "Güvenlik taban çizgisini" (**Intune** > **Güvenlik taban çizgileri**) yayımlayarak ulaşmayı hedefliyoruz.  Yönetici doğrudan bu temellerden güvenlik ilkeleri oluşturabilir ve bunları kullanıcılarına dağıtabilir. Kuruluşunuzun ihtiyaçlarını karşılamak için en iyi yöntem önerilerini de özelleştirebilirsiniz. Intune, cihazların bu taban çizgilerle uyumlu kalmasını sağlar ve yöneticilere uyumlu olmayan kullanıcıları ve cihazları bildirir.

Bu özellik genel önizlemede olduğundan, şimdi oluşturulan tüm profiller, genel kullanıma açık olan güvenlik temelleri şablonlarına (GA) geçmeyecektir. Üretim ortamınızda bu önizleme şablonlarını kullanmayı planlamalısınız.

Güvenlik temelleri hakkında daha fazla bilgi edinmek için bkz. [Intune 'Da Windows 10 güvenlik temeli oluşturma](../protect/security-baselines-monitor.md).

Bu özellik için geçerlidir: Windows 10 ve üzeri

#### <a name="non-administrators-can-enable-bitlocker-on-windows-10-devices-joined-to-azure-ad---2147379-----"></a>Yönetici olmayanlar, Azure AD 'ye katılmış Windows 10 cihazlarında BitLocker 'ı etkinleştirebilir<!-- 2147379   -->
Windows 10 cihazlarında BitLocker ayarlarını etkinleştirdiğinizde (**cihaz yapılandırma** > **profil @no__t-** 3 Platform >**Windows 10 ve üzeri Için,** profil türü için **uç nokta koruması** @no__t**oluşturma** > **Windows şifrelemesi**), BitLocker ayarlarını eklersiniz. 

Bu güncelleştirme, standart kullanıcıların (yönetici olmayanlar) şifrelemeyi etkinleştirmesine izin veren yeni bir BitLocker ayarı içerir. 

Ayarları görmek için [Windows 10 Için Endpoint Protection ayarları](../protect/endpoint-protection-windows-10.md#windows-encryption)' na gidin.

#### <a name="check-for-configuration-manager-compliance----2192052--eepublished----"></a>Configuration Manager uyumluluğunu denetle <!-- 2192052  eepublished  -->
Bu güncelleştirme, yeni bir System Center Configuration Manager uyumluluk ayarı içerir (**cihaz uyumluluk** > **ilkeleri** > **Ilke oluştur** > **Windows 10 ve üzeri** > **Configuration Manager Uyumluluk**). Configuration Manager, Intune uyumluluğuna sinyal gönderir. Bu ayarı kullanarak, tüm Configuration Manager sinyallerinin "uyumlu" döndürmesini zorunlu kılabilirsiniz.

Örneğin, tüm yazılım güncelleştirmelerinin cihazlarda yüklü olmasını gerektirirsiniz. Configuration Manager’da bu gereksinim, “Yüklü” durumundadır. Cihazdaki herhangi bir program bilinmeyen durumdaysa, cihaz Intune 'da uyumlu değildir.

[Configuration Manager uyumluluğu](../protect/compliance-policy-create-windows.md#configuration-manager-compliance) bu ayarı açıklar.

Şunlar için geçerlidir: Windows 10 ve üzeri

#### <a name="customize-wallpaper-on-supervised-ios-devices-using-a-device-configuration-profile----2809324-----"></a>Denetimli iOS cihazlarında bir cihaz yapılandırma profili kullanarak duvar kağıdını özelleştirme <!-- 2809324   -->
İOS cihazları için bir cihaz yapılandırma profili oluştururken, bazı özellikleri özelleştirebilirsiniz (**cihaz yapılandırma** > **profilleri** >  Platform**için @no__t-** 5**iOS** > **cihaz özellikleri** profil türü için). Bu güncelleştirme, yöneticinin ana ekranda veya kilit ekranında bir. png,. jpg veya. JPEG görüntüsü kullanmasına izin veren yeni **duvar kağıdı** ayarlarını içerir. Bu duvar kağıdı ayarları yalnızca denetimli cihazlar için geçerlidir. 

Bu ayarların listesi için bkz. [iOS cihaz özelliği ayarları](../configuration/ios-device-features-settings.md).

#### <a name="windows-10-kiosk-is-generally-available----3594661----"></a>Windows 10 bilgi noktası genel kullanıma sunuldu <!-- 3594661  -->
Bu güncelleştirmede, Windows 10 ve üzeri cihazlarda bilgi noktası özelliği genel kullanıma sunuldu (GA). Ekleyebileceğiniz ve yapılandırabileceğiniz tüm ayarları görmek için bkz. [Windows 10 Için bilgi noktası ayarları (ve üzeri)](../configuration/kiosk-settings.md).

#### <a name="contact-sharing-via-bluetooth-is-removed-in-device-restrictions--device-owner-for-android-enterprise----3598396-----"></a>Bluetooth aracılığıyla kişi paylaşımı, Android Enterprise için cihaz sahibi > cihaz kısıtlamalarında kaldırılmıştır <!-- 3598396   -->
Android kurumsal cihazlar için bir cihaz kısıtlamaları profili oluşturduğunuzda, **Bluetooth ayarı aracılığıyla bir Iletişim paylaşımı** vardır. Bu güncelleştirmede, **Bluetooth Ile kişi paylaşımı** ayarı kaldırılır (**cihaz yapılandırma** > **profilleri** > **profil oluşturma** > **Android Enterprise** for platform > **cihaz kısıtlamaları** Profil türü için > **genel**) cihaz sahibi >. 

**Bluetooth Ile kişi paylaşımı** ayarı, Android kurumsal cihaz sahibi yönetimi için desteklenmez. Bu ayar kaldırıldığında, bu ayar etkin ve ortamınızda yapılandırılmış olsa bile, hiçbir cihazı veya kiracıyı etkilemez.

Ayarların geçerli listesini görmek için [Android kurumsal cihaz ayarları ' na giderek özelliklere izin verin veya kısıtlayın](../configuration/device-restrictions-android-for-work.md).

Uygulama hedefi: Android kurumsal cihaz sahibi

### <a name="device-management"></a>Cihaz yönetimi

#### <a name="selective-wipe-support-for-wip-without-enrollment-devices----1434452---"></a>Kayıt cihazları olmadan WıP için seçmeli temizleme desteği <!-- 1434452 -->
Kayıt olmadan Windows Information Protection (WıP-WE), tüm MDM kaydına gerek duymadan müşterilerin Windows 10 cihazlarında kurumsal verilerini korumalarına olanak sağlar. Belgeler bir WıP-WE ilkesiyle korunduktan sonra, korunan veriler bir Intune Yöneticisi tarafından seçmeli olarak silinebilir. Kullanıcı ve cihazı seçip silme isteği gönderdiğinizde, WıP-WE ilkesi aracılığıyla korunan tüm veriler kullanılamaz hale gelir. Azure portalındaki Intune'dan **Mobil uygulama** > **Uygulama seçmeli silme**'yi seçin.

### <a name="monitor-and-troubleshoot"></a>İzleme ve sorun giderme

#### <a name="new-operational-logs-and-ability-to-send-logs-to-azure-monitor-services----3762211----"></a>Yeni işletimsel Günlükler ve Azure Izleyici hizmetlerine günlük gönderme yeteneği <!-- 3762211  -->
Intune 'da değişiklikler yapıldığından olayları izleyen yerleşik denetim günlüğü vardır. Bu güncelleştirme, aşağıdakiler de dahil olmak üzere yeni günlük özellikleri içerir: 
- Başarılı ve başarısız denemeler dahil olmak üzere, kayıtlı kullanıcılar ve cihazlarla ilgili ayrıntıları gösteren işletimsel Günlükler (Önizleme).
- Denetim günlükleri ve işletimsel Günlükler, depolama hesapları, Olay Hub 'ları ve Log Analytics de dahil olmak üzere Azure Izleyici 'ye gönderilebilir. Bu hizmetler, splunk ve QRadar gibi analizler kullanmanızı ve günlük verilerinizin görselleştirmelerini almanızı sağlar.

[Intune 'da günlük verilerini depolama, Olay Hub 'ları veya Log Analytics 'e gönderme](../review-logs-using-azure-monitor.md) , bu özellik hakkında daha fazla bilgi sağlar.

### <a name="skip-more-setup-assistant-screens-on-an-ios-dep-device----2687509----"></a>İOS DEP cihazında daha fazla Kurulum Yardımcısı ekranı atlayın <!-- 2687509  -->
Şu anda atlayabileceği ekranlarına ek olarak, iOS DEP cihazlarını, bir Kullanıcı cihazı kaydettiğinde Kurulum Yardımcısı 'ndaki aşağıdaki ekranları atlayacak şekilde ayarlayabilirsiniz: ekran tonu, gizlilik, Android geçişi, giriş düğmesi, IMessage & çok yönlü saat, ekleme, Izleme Geçiş, görünüm, ekran süresi, yazılım güncelleştirmesi, SIM kurulumu.
Atlanacak ekranları seçmek için, **cihaz kaydı** > **Apple kaydı** > **kayıt programı belirteçleri** > bir belirteç > **profilleri** seçin > bir profil > **Özellikler** > **Kurulum Yardımcı özelleştirme** > **Tamam**> atlamak Istediğiniz ekranlar için **Gizle** ' yi seçin.
Yeni bir profil oluşturursanız veya bir profili düzenlerseniz, seçili atlama ekranlarının Apple MDM sunucusuyla eşitlenmesi gerekir. Kullanıcılar, profil değişikliklerini çekerken bir gecikme olmaması için cihazların el ile eşitlenmesini verebilir.

#### <a name="android-enterprise-app-we-app-deployment----1171203---"></a>Android Enterprise APP-WE uygulaması dağıtımı <!-- 1171203 -->
Kayıt (APP-WE) dağıtım senaryosu olmayan kayıtlı olmayan bir uygulama koruma Ilkesinde Android cihazlarda, artık kullanıcılara Mağaza uygulamaları ve LOB uygulamaları dağıtmak için yönetilen Google Play kullanabilirsiniz. Özellikle, son kullanıcılara artık son kullanıcıların cihazların güvenlik duruşunu, bilinmeyen kaynaklardan yüklemelere izin vererek koruyabilmesine gerek duymayacak bir uygulama kataloğu ve yükleme deneyimi sağlayabilirsiniz. Ayrıca, bu dağıtım senaryosu gelişmiş bir son kullanıcı deneyimi sağlar.

<!-- ########################## -->
## <a name="week-of-january-14-2019"></a>14 Ocak 2019 haftası

### <a name="preview-of-support-for-android-corporate-owned-fully-managed-devices----1574342----"></a>Android şirkete ait, tam olarak yönetilen cihazlar için destek önizlemesi <!-- 1574342  -->
Intune artık cihazların tamamen yönettiği ve bireysel kullanıcılarla ilişkili olduğu şirkete ait bir "cihaz sahibi" senaryosu olan tam olarak yönetilen Android cihazlarını desteklemektedir. Bu, yöneticilerin tüm cihazı yönetmesine, iş profillerinin genişletilmiş bir dizi ilke denetimine zorlayacağına ve kullanıcıların yalnızca yönetilen Google Play uygulama yüklemesini kısıtlamalarına olanak tanır. Daha fazla bilgi için bkz. [Android tam olarak yönetilen cihazların Intune kaydını ayarlama](../enrollment/android-fully-managed-enroll.md) ve [adanmış cihazlarınızı veya tam olarak yönetilen cihazları kaydetme](../enrollment/android-dedicated-devices-fully-managed-enroll.md).  Bu özelliğin önizlemede olduğunu lütfen unutmayın. Sertifikalar, uyumluluk ve koşullu erişim gibi bazı Intune özellikleri şu anda Android tam olarak yönetilen Kullanıcı cihazlarıyla birlikte kullanılamaz.

<!-- ########################## -->
## <a name="week-of-january-7-2019"></a>7 Ocak 2019 haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="intune-app-pin----2298397---"></a>Intune uygulama PIN 'ı <!-- 2298397 -->
BT Yöneticisi olarak, bir son kullanıcının Intune uygulama PIN 'inin değişmesi için bekleyeceği gün sayısını yapılandırabilirsiniz. Yeni ayar, *gün sayısından sonra PIN sıfırlamadır* ve Azure portal **Intune** > **Istemci uygulamaları** > **Uygulama koruma ilkeleri** > **ilke oluştur** > **ayarları** 10 @no__t**erişim gereksinimleri**. [İOS](../apps/app-protection-policy-settings-ios.md) ve [Android](../apps/app-protection-policy-settings-android.md) cihazlarda kullanılabilir, bu özellik pozitif bir tamsayı değeri destekler.


#### <a name="intune-device-reporting-fields----2748738---"></a>Intune cihaz raporlama alanları <!-- 2748738 -->
Intune, uygulama kayıt KIMLIĞI, Android üreticisi, model ve güvenlik düzeltme eki sürümü ve iOS modelinin yanı sıra ek cihaz raporlama alanları sağlar. Intune 'da bu alanlar, **istemci uygulamaları** > **Uygulama koruma durumu** ' nu seçip **Uygulama koruma raporu: iOS, Android '** i seçerek kullanılabilir. Ayrıca, bu parametreler cihaz üreticisi için **Izin verilenler** listesi (Android), cihaz modeli Için **izin verilenler** listesi (Android ve iOS) ve en düşük Android güvenlik düzeltme eki sürümü ayarını yapılandırmanıza yardımcı olur. 


### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="administrative-templates-are-in-public-preview-and-moved-to-their-own-configuration-profile----3322847---"></a>Yönetim Şablonları genel önizlemede ve kendi yapılandırma profilinize taşınır <!-- 3322847 -->

Intune 'daki Yönetim Şablonları (**cihaz yapılandırma** > **Yönetim Şablonları**) Şu anda genel önizlemededir. Bu güncelleştirmeyle:

- Yönetim Şablonları, Intune 'da yönetilebilen 300 ayarlarını içerir. Daha önce bu ayarlar yalnızca Grup İlkesi Düzenleyicisi 'nde yer almaktadır.
- Yönetim Şablonları genel önizlemede kullanılabilir.
- Yönetim Şablonları **cihaz yapılandırma** > **Yönetim şablonlarından** **cihaz yapılandırmasına**taşınıyor  > **profiller** >  bir platformda**profil oluşturma** > ' iseçin  **Windows 10 ve üzeri** > **profil türünde**, **Yönetim Şablonları**' nı seçin.
- Raporlama etkin

Bu özellik hakkında daha fazla bilgi edinmek için, [Grup İlkesi ayarlarını yapılandırmak üzere Windows 10 şablonlarına](../configuration/administrative-templates-windows.md)gidin.

Şunlar için geçerlidir: Windows 10 ve üzeri

#### <a name="use-smime-to-encrypt-and-sign-multiple-devices-for-a-user-----1333642---"></a>Bir kullanıcı için birden çok cihazı şifrelemek ve imzalamak için S/MIME kullanın  <!-- 1333642 -->
Bu güncelleştirme, içeri aktarılmış yeni bir sertifika profili kullanan S/MIME e-posta şifrelemesi içerir (**Cihaz yapılandırması** > **Profiller** > **Profil oluşturun** > platform seçin > **PKCS içeri aktarılan sertifika** profil türü). Intune’da sertifikaları PFX biçiminde içeri aktarabilirsiniz. Intune, aynı sertifikaları tek bir kullanıcı tarafından kaydedilen birden fazla cihaza teslim edebilir. Ayrıca şunları da içerir:
- Yerel iOS e-posta profili, PFX biçiminde içeri aktarılan sertifikaları kullanan S/MIME şifrelemesini etkinleştirmeyi destekler.
- Windows Phone 10 cihazlarındaki yerel posta uygulaması otomatik olarak S/MIME sertifikasını kullanır.
- Özel sertifikalar, birden fazla platforma teslim edilebilir. Ancak tüm e-posta uygulamaları, S/MIME’yi desteklemez.
- Diğer platformlarda S/MIME’yi etkinleştirmek için posta uygulamasını el ile yapılandırmanız gerekebilir.  
- S/MIME şifrelemesini destekleyen e-posta uygulamaları, S/MIME e-posta şifrelemesi için sertifika alma işlemini MDM’nin destekleyemeyeceği bir şekilde halleder, ör. yayımcılarının sertifika deposundan okuma.
Bu özellik hakkında daha fazla bilgi için bkz. [S/MIME Overview e-postayı imzalama ve şifreleme](../protect/certificates-s-mime-encryption-sign.md).
Desteklenir: Windows, Windows Phone 10, macOS, iOS, Android

#### <a name="new-options-to-automatically-connect-and-persist-rules-when-using-dns-settings-on-windows-10-and-later-devices----1333665-2999078---"></a>Windows 10 ve üzeri cihazlarda DNS ayarlarını kullanırken kuralların otomatik olarak bağlanmasına ve kalıcı hale getirilmesi için yeni seçenekler <!-- 1333665, 2999078 -->
Windows 10 ve üzeri cihazlarda, contoso.com gibi etki alanlarını çözümlemek için DNS sunucularının bir listesini içeren bir VPN yapılandırma profili oluşturabilirsiniz. Bu güncelleştirme, ad çözümlemesi için yeni ayarlar içerir (**cihaz yapılandırma** > **profilleri** > **Profil oluştur** > Platform için **Windows 10 ve üstünü** seçin > profil türü için **VPN** seçin > **DNS ayarlar** >**ekleme**): 
- **Otomatik olarak bağlan**: **etkinleştirildiğinde**, cihaz girdiğiniz bir etki alanına (contoso.com gibi) BAĞLANDıĞıNDA cihaz otomatik olarak VPN 'e bağlanır.
- **Persistent**: varsayılan olarak, CIHAZ bu VPN profili kullanılarak bağlandığı sürece tüm ad çözümleme ilkesi tablosu (NRPT) kuralları etkin olur. Bu ayar bir NRPT kuralında **etkinleştirildiğinde** , VPN bağlantısı kesilse bile kural cihazda etkin kalır. Kural, VPN profili kaldırılana kadar veya kural el ile kaldırılana kadar veya PowerShell kullanılarak yapılabileceği sürece kalır.
[Windows 10 VPN ayarları](../configuration/vpn-settings-windows-10.md) , ayarları açıklar. 

#### <a name="use-trusted-network-detection-for-vpn-profiles-on-windows-10-devices----1500165---"></a>Windows 10 cihazlarda VPN profilleri için güvenilen ağ algılamayı kullanma <!-- 1500165 -->
Güvenilen ağ algılama kullanırken, Kullanıcı zaten güvenilir bir ağda olduğunda VPN profillerinin otomatik olarak bir VPN bağlantısı oluşturmasını engelleyebilirsiniz. Bu güncelleştirmeyle, Windows 10 ve üzeri sürümlerini çalıştıran cihazlarda güvenilen ağ algılamasını etkinleştirmek için DNS sonekleri ekleyebilirsiniz (**cihaz yapılandırma** > **profilleri** > **Profil oluştur** > **Windows 10 ve üzeri** için profil türü için Platform > **VPN** ).
[Windows 10 VPN ayarları](../configuration/vpn-settings-windows-10.md) geçerli VPN ayarlarını listeler.

#### <a name="manage-windows-holographic-for-business-devices-used-by-multiple-users----1907917-1063203---"></a>Birden çok kullanıcı tarafından kullanılan Windows holographic for Business cihazlarını yönetme <!-- 1907917, 1063203 -->
Şu anda, özel bir OMA-URI ayarı kullanarak Windows 10 ve Windows holographic for Business cihazlarında paylaşılan bılgısayar ayarlarını yapılandırabilirsiniz. Bu güncelleştirmeyle paylaşılan cihaz ayarlarını yapılandırmak için yeni bir profil eklenir (**cihaz yapılandırma** > **profilleri** > **Profil oluştur** > **Windows 10 ve üzeri** > **paylaşılan çok kullanıcılı cihaz**).
Bu özellik hakkında daha fazla bilgi edinmek için, [paylaşılan cihazları yönetmek üzere Intune ayarları](../configuration/shared-user-device-settings.md)' na gidin.
Uygulama hedefi: Windows 10 ve üzeri, Windows holographic for Business

#### <a name="new-windows-10-update-settings---2626030--2512994----"></a>Yeni Windows 10 güncelleştirme ayarları <!--2626030  2512994  -->
[Windows 10 güncelleştirme halkalarınız](../protect/windows-update-for-business-configure.md)için şunları yapılandırabilirsiniz:
- **Otomatik Güncelleştirme davranışı** - *Ekim 2018 güncelleştirmesini* çalıştıran makinelerde bir Windows 10 makinesinde özgün otomatik güncelleştirme ayarlarını geri yüklemek için yeni bir seçenek kullanın, *varsayılana sıfırlayın*
- **Kullanıcının Windows güncelleştirmelerini duraklatmasını engelle** -kullanıcılarınızın güncelleştirme yüklemesini kendi makinelerinin *ayarlarından* duraklatmalarına Izin veren yeni bir yazılım güncelleştirmeleri ayarı yapılandırın. 

#### <a name="ios-email-profiles-can-use-smime-signing-and-encryption----2662949---"></a>iOS e-posta profilleri, S/MIME imzalama ve şifrelemeyi kullanabilir <!-- 2662949 -->
Farklı ayarlar içeren bir e-posta profili oluşturabilirsiniz. Bu güncelleştirme, iOS cihazlarında e-posta iletişimleri imzalama ve şifreleme için kullanılabilen S/MIME ayarlarını içerir (**cihaz yapılandırma** > **profilleri** > **Profil oluştur** > Platform için **iOS** 'u seçin >  **Profil türü için e-posta** .
[iOS e-posta yapılandırma ayarları](../configuration/email-settings-ios.md) ayarları listeler.

#### <a name="some-bitlocker-settings-support-windows-10-pro-edition---2727036---"></a>Bazı BitLocker ayarları Windows 10 Pro Edition 'ı destekler<!-- 2727036 -->
BitLocker da dahil olmak üzere Windows 10 cihazlarında Endpoint Protection ayarlarını ayarlayan bir yapılandırma profili oluşturabilirsiniz. Bu güncelleştirme, bazı BitLocker ayarları için Windows 10 Professional Edition desteği ekler. Bu koruma ayarlarını görmek için [Windows 10 Için Endpoint Protection ayarları](../protect/endpoint-protection-windows-10.md#windows-encryption)' na gidin.

#### <a name="shared-device-configuration-is-renamed-to-lock-screen-message-for-ios-devices-in-the-azure-portal---2809362---"></a>Paylaşılan cihaz yapılandırması, Azure portal iOS cihazları için kilit ekranı Iletisi olarak yeniden adlandırıldı<!-- 2809362 -->
İOS cihazları için bir yapılandırma profili oluşturduğunuzda, kilit ekranında belirli bir metni göstermek üzere **paylaşılan cihaz yapılandırma** ayarları ekleyebilirsiniz. Bu güncelleştirme aşağıdaki değişiklikleri içerir: 
- Azure portal **paylaşılan cihaz yapılandırma** ayarları "kilit ekranı iletisi (yalnızca denetimli)" olarak yeniden adlandırılır (**cihaz yapılandırması** > **profiller** > **Profil oluştur** > Platform için **iOS** seçin > Profil türü için **cihaz özellikleri** > **kilit ekran iletisi**) seçin.
- Kilit ekranı iletileri eklerken, **varlık etiketi bilgileri** ve **kilit ekranı dipnotu**içinde değişken olarak bir seri numarası, cihaz adı veya cihaza özgü bir değer ekleyebilirsiniz. Örneğin, `Device name: {{devicename}}` veya `Serial number is {{serialnumber}}` girerek süslü ayraçları kullanabilirsiniz. [iOS belirteçleri](../apps/app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) , kullanılabilecek belirteçleri listeler.
[Kilit ekranında iletileri görüntüleme ayarları](../configuration/ios-device-features-settings.md#lock-screen-message) , ayarları listeler.

#### <a name="new-app-store-doc-viewing-gaming-device-restriction-settings-added-to-ios-devices----2827760--"></a>İOS cihazlarına yeni uygulama Mağazası, belge görüntüleme, oyun cihaz kısıtlama ayarları eklendi <!-- 2827760-->
**Cihaz yapılandırması**@no__t **-1 profil** >  cihaz**oluşturma** > **IOS** for platform > **cihaz kısıtlamaları** > **Uygulama Mağazası, belge görüntüleme, oyun**ve aşağıdaki ayarlar Eklendi: yönetilen uygulamaların, yönetilmeyen kişiler hesaplarına kişi yazmasına Izin ver ayarı, yönetilmeyen uygulamaların yönetilen kişiler hesaplarından okunmasını sağlar bu ayarları görmek Için [iOS cihaz kısıtlamalarına](../configuration/device-restrictions-ios.md#app-store-doc-viewing-gaming)gidin.

#### <a name="new-notification-hints-and-keyguard-settings-to-android-enterprise-device-owner-devices----3201839-3201843---"></a>Android kurumsal cihaz sahibi cihazlara yeni bildirim, ipucu ve keyguard ayarları <!-- 3201839 3201843 -->
Bu güncelleştirme, cihaz sahibi olarak çalışırken Android kurumsal cihazlarda çeşitli yeni özellikler içerir. Bu özellikleri kullanmak için **cihaz yapılandırma** > **profiller** >  **platformda** **Profil oluştur** > ' yi seçin, **Android kurumsal** > **profil türü**' ni seçin, **yalnızca cihaz sahibi**' i seçin @no__ t-9**cihaz kısıtlamaları**.

Yeni özellikler şunları içerir: 

- Gelen çağrılar, sistem uyarıları, sistem hataları ve daha fazlasını içeren sistem bildirimlerinin gösterilmesini devre dışı bırakın.
- İlk kez açılan uygulamalar için başlangıç öğreticilerini ve ipuçlarını atla ' yı önerir.
- Kamera, bildirimler, parmak izi kilidi açma ve daha fazlası gibi gelişmiş keyguard ayarlarını devre dışı bırakın.


Ayarları görmek için [Android kurumsal cihaz kısıtlama ayarları](../configuration/device-restrictions-android-for-work.md)' na gidin.

#### <a name="android-enterprise-device-owner-devices-can-use-always-on-vpn-connections----3202194---"></a>Android kurumsal cihaz sahibi cihazları her zaman VPN bağlantılarında kullanılabilir <!-- 3202194 -->
Bu güncelleştirmede, Android kurumsal cihaz sahibi cihazlarda her zaman açık VPN bağlantılarını kullanabilirsiniz. Her zaman açık VPN bağlantıları; kullanıcı cihazının kilidini açtığında, cihaz yeniden başlatıldığında veya kablosuz ağ değiştiğinde bağlı kalır veya hemen tekrar bağlanır. Bağlantıyı “kilitli”moduna da alabilirsiniz, böylece VPN bağlantısı etkin olana kadar tüm ağ trafiği engellenir.
**Cihaz yapılandırma** > **profillerdeki**her zaman VPN 'yi etkinleştirebilirsiniz  > **profil oluşturma** > **Android Enterprise** for platform > **cihaz** sahibi yalnızca **Bağlantı >** ayarlar. Ayarları görmek için [Android kurumsal cihaz kısıtlama ayarları](../configuration/device-restrictions-android-for-work.md)' na gidin.

#### <a name="new-setting-to-end-processes-in-task-manager-on-windows-10-devices----3285177---"></a>Windows 10 cihazlarında Görev Yöneticisi 'nde son işlemlerin yeni ayarı <!-- 3285177 --> 
Bu güncelleştirme, Windows 10 cihazlarında Görev Yöneticisi 'ni kullanarak son işlemlere yönelik yeni bir ayar içerir. Cihaz yapılandırma profili kullanma (**cihaz yapılandırma**@no__t **-1 profil** >  platformda**Profil oluştur** >, **profil türü**' nde **Windows > 10** ' u seçin, **cihaz kısıtlamaları** ' nı seçin.  > **genel** ayarları), bu ayarı izin vermeyi veya engellemeniz tercih edersiniz.
Bu ayarları görmek için [Windows 10 cihaz kısıtlama ayarları](../configuration/device-restrictions-windows-10.md)' na gidin.
Şunlar için geçerlidir: Windows 10 ve üzeri

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="more-detailed-enrollment-restriction-failure-messaging----3111564---"></a>Daha ayrıntılı kayıt kısıtlaması hata iletileri <!-- 3111564 -->
Kayıt kısıtlamaları karşılanmazsa daha ayrıntılı hata iletileri kullanılabilir. Bu iletileri görmek için **ıntune** >  >**sorun giderme** ' ye gidin ve kayıt hataları tablosunu denetleyin. Daha fazla bilgi için [kayıt hatalarının listesine](help-desk-operators.md#enrollment-failure-reference)bakın.

### <a name="monitor-and-troubleshoot"></a>İzleme ve sorun giderme

#### <a name="tenant-status-dashboard-----1124854---"></a>Kiracı durumu panosu  <!-- 1124854 -->
Yeni [kiracı durumu sayfası](tenant-status.md) , kiracınızın durumunu ve ilgili ayrıntılarını görüntüleyebileceğiniz tek bir konum sağlar.  Pano dört alana ayrılmıştır:
- **Kiracı ayrıntıları** -kiracı adınızı ve konumunuzu, MDM yetkilinizi, kiracınızdaki toplam kayıtlı cihazları ve lisans sayılarınızı içeren bilgileri görüntüler. Bu bölüm, kiracınız için geçerli hizmet sürümünü de listeler.
- **Bağlayıcı durumu** -yapılandırdığınız kullanılabilir bağlayıcılar hakkındaki bilgileri görüntüler ve henüz etkinleştirmediyseniz, bu bilgileri de listeleyebilir.  
   Her bağlayıcının geçerli durumuna bağlı olarak, bunlar sağlıklı, uyarı veya sağlıksız olarak işaretlenir. Detaya gitmek ve ayrıntıları görüntülemek veya ilgili ek bilgileri yapılandırmak için bir bağlayıcı seçin.
- **Intune hizmet durumu** -kiracınız için etkin olaylar veya kesintiler hakkındaki ayrıntıları görüntüler. Bu bölümdeki bilgiler doğrudan Office Ileti merkezinden alınır.
- **Intune haberleri** -kiracınız için etkin iletileri görüntüler. Kiracınız en son Intune özelliklerini aldığında, iletiler bildirimler gibi şeyler içerir.  Bu bölümdeki bilgiler doğrudan Office Ileti merkezinden alınır.

#### <a name="new-help-and-support-experience-in-company-portal-for-windows-10----1488939--"></a>Windows 10 için Şirket Portalı yeni yardım ve destek deneyimi <!-- 1488939-->
Yeni Şirket Portalı yardım & destek sayfası, kullanıcıların uygulama ve erişim sorunlarına yönelik sorun giderme ve yardım istemesine yardımcı olur. Yeni sayfadan hata ve tanılama günlüğü ayrıntılarına e-posta gönderebilir ve kuruluşunuzun yardım masası ayrıntılarını bulabilirsiniz. Ayrıca ilgili Intune belgelerinin bağlantılarıyla birlikte bir SSS bölümü de bulacaksınız. 

#### <a name="new-help-and-support-experience-for-intune------3307080---"></a>Intune için yeni yardım ve destek deneyimi   <!-- #3307080 -->
Sonraki birkaç güne kadar tüm kiracılara yönelik yeni yardım ve destek deneyimini kullanıma sunuyoruz. Bu yeni deneyim Intune için kullanılabilir ve [Azure Portal](https://portal.azure.com/)Intune Blade kullanılırken erişilebilir.
Yeni deneyim, sorununuzu kendi kelimelerinizle açıklamanıza ve sorun giderme içgörüleri ile Web tabanlı düzeltme içeriği almanıza olanak tanır. Bu çözümler, Kullanıcı tarafından yönetilen kural tabanlı makine öğrenimi algoritması aracılığıyla sunulur. Soruna özgü kılavuza ek olarak, yeni durum oluşturma iş akışını kullanarak e-posta veya telefon ile bir destek talebi açabilirsiniz. Bu yeni deneyim, yardım ve destek ' i açtığınızda kullandığınız konsolun alanını temel alan, önceden seçilmiş bir statik seçenekler kümesinin önceki yardım ve destek deneyiminin yerini alır. Daha fazla bilgi için bkz. [Microsoft Intune için destek alma](get-support.md).

### <a name="role-based-access-control"></a>Rol tabanlı erişim denetimi

#### <a name="scope-tags-for-apps----1081941---"></a>Uygulamalar için kapsam etiketleri <!-- 1081941 -->
Roller ve uygulamalar için erişimi sınırlandırmak üzere kapsam etiketleri oluşturabilirsiniz. Bir uygulamaya kapsam etiketi ekleyebilirsiniz, böylece bu kapsam etiketini yalnızca rollere sahip kişilerin uygulamaya erişimi vardır. Şu anda, yönetilen Google Play veya Apple Volume Purchase Program (VPP) kullanılarak satın alınan uygulamalardan Intune 'a eklenen uygulamalara kapsam etiketleri atanamaz (gelecekteki destek planlanmaktadır). Daha fazla bilgi için bkz. [ilkeleri filtrelemek için kapsam etiketlerini kullanma](scope-tags.md).

## <a name="notices"></a>Bildirimler

[!INCLUDE [Intune notices](../includes/intune-notices.md)]
