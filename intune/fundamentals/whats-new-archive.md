---
title: Microsoft Intune-Azure 'da önceki aylardaki yenilikler | Microsoft Docs
titleSuffix: ''
description: Intune 'un yenilikler sayfasındaki eski duyuruları gözden geçirin
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 7/8/2019
ms.topic: archived
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 9ba01d60-4a03-4e3e-9aba-8be905c0054c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1af106227442e91121f6c8c653c261bd677f3a9f
ms.sourcegitcommit: f04e21ec459998922ba9c7091ab5f8efafd8a01c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71814185"
---
# <a name="whats-new-in-the-microsoft-intune---previous-months"></a>Microsoft Intune yenilikler-önceki aylar

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

<!-- ########################## -->
## <a name="december-2018"></a>Aralık 2018

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="updates-for-application-transport-security----748318---"></a>Uygulama taşıma güvenliği için güncelleştirmeler <!-- 748318 -->

Microsoft Intune, Intune 'un varsayılan olarak daha güvenli olmasını sağlamak ve Microsoft Office 365 gibi diğer Microsoft hizmetleriyle hizalamak için, Aktarım Katmanı Güvenliği 'ni (TLS) 1.2 + 'yi destekler. Bu gereksinimi karşılamak için iOS ve macOS şirket portalları, Apple 'ın güncelleştirilmiş uygulama taşıma güvenliği (ATS) gereksinimlerini (Ayrıca, TLS 1.2 + gerektiren) zorlayacaktır. ATS, HTTPS üzerinden tüm uygulama iletişimlerinde daha sıkı güvenlik sağlamak için kullanılır. Bu değişiklik, iOS ve macOS Şirket Portalı uygulamalarını kullanarak Intune müşterilerini etkiler. Daha fazla bilgi için bkz. [Intune destek blogu](https://aka.ms/compportalats).

#### <a name="the-intune-app-sdk-will-support-256-bit-encryption-keys----1832174---"></a>Intune uygulama SDK 'Sı 256 bit şifreleme anahtarlarını destekleyecektir <!-- 1832174 -->
Android için Intune uygulama SDK 'Sı artık şifreleme uygulama koruma Ilkeleri tarafından etkinleştirildiğinde 256 bit şifreleme anahtarlarını kullanır. SDK, eski SDK sürümlerini kullanan içerik ve uygulamalarla uyumluluk için 128 bitlik anahtarlar desteği sağlamaya devam edecektir.

#### <a name="microsoft-auto-update-version-450-required-for-macos-devices----3503442---"></a>MacOS cihazları için Microsoft Auto Update sürüm 4.5.0 gereklidir <!-- 3503442 -->
Şirket Portalı ve diğer Office uygulamalarına yönelik güncelleştirmeleri almaya devam etmek için Intune tarafından yönetilen macOS cihazlarının Microsoft Auto Update 4.5.0 'e yükseltilmesi gerekir. Kullanıcılar Office uygulamaları için bu sürüme zaten sahip olabilir.

### <a name="device-management"></a>Cihaz yönetimi

#### <a name="intune-requires-macos-1012-or-later----2827778---"></a>Intune macOS 10,12 veya üstünü gerektirir <!-- 2827778 -->
Intune artık macOS sürüm 10,12 veya üstünü gerektiriyor. Önceki macOS sürümlerini kullanan cihazlar Intune 'a kaydolmak için Şirket Portalı kullanamaz. Destek yardımını ve yeni özellikleri almak için, kullanıcıların cihazlarını macOS 10,12 veya sonraki bir sürüme yükseltmeleri ve Şirket Portalı en son sürüme yükseltmesi gerekir.

<!-- ########################## -->
## <a name="november-2018"></a>2018 Kasım

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="uninstalling-apps-on-corporate-owned-supervised-ios-devices----1281677---"></a>Şirkete ait denetimli iOS cihazlarında uygulamaları kaldırma <!-- 1281677 -->
Şirkete ait denetimli iOS cihazlarında herhangi bir uygulamayı kaldırabilirsiniz. Bir **kaldırma** atama türü ile Kullanıcı veya cihaz gruplarını hedefleyerek herhangi bir uygulamayı kaldırabilirsiniz. Kişisel veya denetimli iOS cihazlarda yalnızca Intune kullanılarak yüklenen uygulamaları kaldırmaya devam edersiniz.

#### <a name="downloading-intune-win32-app-content----2617320---"></a>Intune Win32 uygulama içeriği indiriliyor <!-- 2617320 -->
Windows 10 RS3 ve üzeri istemciler, Windows 10 istemcisinde teslim Iyileştirme bileşeni kullanarak Intune Win32 uygulama içeriğini indirir. Teslim iyileştirme, varsayılan olarak açık olan eşler arası işlevsellik sağlar. Dağıtım iyileştirmesi Şu anda Grup İlkesi tarafından yapılandırılabilir. Daha fazla bilgi için bkz. [Windows 10 Için teslim iyileştirmesi](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization).

#### <a name="end-user-device-and-app-content-menu----2771453---"></a>Son Kullanıcı cihaz ve uygulama içeriği menüsü <!-- 2771453 -->
Son kullanıcılar artık cihaz ve uygulamalar üzerinde bağlam menüsünü kullanarak bir cihazı yeniden adlandırma veya uyumluluğu denetleme gibi yaygın eylemleri tetikleyebilirler.

#### <a name="set-custom-background-in-managed-home-screen-app-----3041945---"></a>Yönetilen giriş ekranı uygulamasında özel arka plan ayarla  <!-- 3041945 -->
Android Enterprise, çok uygulama, bilgi noktası modundaki cihazlarda yönetilen giriş ekranı uygulamasının arka plan görünümünü özelleştirmenizi sağlayan bir ayar ekliyoruz.  **Özel URL arka planını**yapılandırmak için Azure Portal > cihaz yapılandırmasında Intune 'a gidin. Bilgi noktası ayarlarını düzenlemek için geçerli bir cihaz yapılandırma profili seçin veya yeni bir cihaz oluşturun.
Bilgi noktası ayarlarını görmek için bkz. [Android kurumsal cihaz kısıtlamaları](../configuration/device-restrictions-android-for-work.md).

#### <a name="app-protection-policy-assignment-save-and-apply----3104570---"></a>Uygulama koruma ilkesi ataması Kaydet ve Uygula <!-- 3104570 -->
Artık [Uygulama koruma ilkesi atamalarınız](../apps/app-protection-policies.md#deploy-a-policy-to-users)üzerinde daha iyi denetime sahipsiniz. Bir ilkenin atamalarını ayarlamak veya düzenlemek için *atamalar* ' ı seçtiğinizde, değişikliğin geçerli olması Için yapılandırmanızı **kaydetmelisiniz** . Ekleme veya dışlama listelerinde değişiklik yapmadan yaptığınız tüm değişiklikleri temizlemek için **at** ' i kullanın.  Kaydetmeyi veya atmayı zorunlu kılarak yalnızca sizin istediğiniz kullanıcılara bir uygulama koruma ilkesi atanır.

#### <a name="new-microsoft-edge-browser-settings-for-windows-10-and-later----3174639---"></a>Windows 10 ve üzeri için yeni Microsoft Edge tarayıcı ayarları <!-- 3174639 -->
Bu güncelleştirme, cihazlarınızda Microsoft Edge tarayıcısını denetlemeye ve yönetmeye yardımcı olacak yeni ayarlar içerir. Bu ayarların listesi için bkz. [Windows 10 Için cihaz kısıtlaması (ve daha yeni)](../configuration/device-restrictions-windows-10.md#microsoft-edge-browser).

#### <a name="new-apps-support-with-app-protection-policies----3330037---"></a>Uygulama koruma ilkeleriyle yeni uygulama desteği <!-- 3330037 -->
Artık aşağıdaki uygulamaları [Intune uygulama koruma ilkeleriyle](../apps/app-protection-policies.md)yönetebilirsiniz:
- Stream (iOS)
- YAPıLACAKLAR (Android, iOS)
- PowerApps (Android, iOS)
- Flow (Android, iOS)

Şirket verilerini korumak ve Intune ilkesi tarafından yönetilen diğer uygulamalar gibi bu uygulamalar için veri aktarımını denetlemek için uygulama koruma ilkelerini kullanın. Not: akış henüz konsolda görünmüyorsa, uygulama koruma ilkeleri oluştururken veya düzenlerken akış eklersiniz. Bunu yapmak için **+ diğer uygulamalar** seçeneğini kullanın ve giriş alanında Flow IÇIN *uygulama kimliği* ' ni belirtin. Android için *com. Microsoft. Flow*ve iOS için *com. Microsoft. procsımo*kullanın.


### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="support-for-ios-12-oauth-in-ios-email-profiles---2155106---"></a>İOS için iOS e-posta profillerinde iOS 12 OAuth desteği <!--2155106 -->
Intune 'un iOS e-posta profilleri iOS 12 Open Authorization (OAuth) desteği. Bu özelliği görmek için, yeni bir profil oluşturun (**cihaz yapılandırma** > **profilleri** >  profil**oluştur** > **IOS** > için profil türü için bir **e-posta** ) veya mevcut bir iOS e-posta profilini güncelleştirin. Kullanıcılara zaten dağıtılan bir profilde OAuth 'yı etkinleştirirseniz, kullanıcılardan yeniden kimlik doğrulaması yapması ve e-postalarını tekrar indirmesi istenir.

[iOS e-posta profillerinde](../configuration/email-settings-ios.md) bir e-posta profilinde OAuth kullanımı hakkında daha fazla bilgi bulunur.

#### <a name="network-access-control-nac-support-for-citrix-sso-for-ios----3259404---"></a>İOS için Citrix SSO için ağ Access Control (NAC) desteği <!-- 3259404 -->
Citrix, Intune 'da iOS için Citrix SSO için ağ Access Control (NAC) izin vermek üzere Citrix Gateway 'e bir güncelleştirme yayımlamıştır. Intune 'da bir VPN profiline cihaz KIMLIĞI eklemek ve ardından bu profili iOS cihazlarınıza göndermek için kabul edebilirsiniz. Bu işlevselliği kullanmak için Citrix Gateway 'e en son güncelleştirmeyi yüklemeniz gerekir.

[İOS CIHAZLARıNDA VPN ayarlarını yapılandırma](../configuration/vpn-settings-ios.md#base-vpn-settings) bazı ek gereksinimler de dahil olmak üzere NAC kullanma hakkında daha fazla bilgi sağlar. 

#### <a name="ios-and-macos-version-numbers-and-build-numbers-are-shown----1892471---"></a>iOS ve macOS sürüm numaraları ve derleme numaraları gösterilir <!-- 1892471 -->
**Cihaz uyumluluğu** > **cihaz uyumluluğu**' nda iOS ve MacOS işletim sistemi sürümleri gösterilir ve uyumluluk ilkelerinde kullanılabilir. Bu güncelleştirme, her iki platformda de yapılandırılabilir olan yapı numarasını içerir.
Güvenlik güncelleştirmeleri yayınlandığında, Apple genellikle sürüm numarasını olduğu gibi bırakır, ancak yapı numarasını günceller. Bir uyumluluk ilkesinde derleme numarasını kullanarak, bir güvenlik açığı güncelleştirmesinin yüklenip yüklenmediğini kolayca kontrol edebilirsiniz.
Bu özelliği kullanmak için bkz. [iOS](../protect/compliance-policy-create-ios.md#device-health) ve [MacOS](../protect/compliance-policy-create-mac-os.md#device-properties) uyumluluk ilkeleri.

#### <a name="update-rings-are-being-replaced-with-delivery-optimization-settings-for-windows-10-and-later----2753807---"></a>Güncelleştirme halkaları Windows 10 ve üzeri için teslim Iyileştirme ayarları ile değiştiriliyor <!-- 2753807 -->
Teslim iyileştirme, Windows 10 ve üzeri için yeni bir yapılandırma profilidir. Bu özellik, kuruluşunuzdaki cihazlara yazılım güncelleştirmeleri sunmaya yönelik daha kolaylaştırılmış bir deneyim sunar. Bu güncelleştirme ayrıca bir yapılandırma profili kullanarak yeni ve mevcut güncelleştirme halkaları için ayarları teslim etmenize yardımcı olur.
Teslim iyileştirme yapılandırma profilini yapılandırmak için, bkz. [Windows 10 (ve daha yeni) teslim iyileştirme ayarları](../configuration/delivery-optimization-windows.md).

#### <a name="new-device-restriction-settings-added-to-ios-and-macos-devices----2827760---"></a>İOS ve macOS cihazlarına yeni cihaz kısıtlama ayarları eklendi <!-- 2827760 -->
Bu güncelleştirme iOS ve macOS cihazlarınız için iOS 12 ile yayınlanan yeni ayarları içerir:

**iOS ayarları**: 
- Genel: Uygulama kaldırmayı engelle (yalnızca denetimli)
- Genel: blok USB kısıtlı modu (yalnızca denetimli)
- Genel: otomatik tarih ve saati zorla (yalnızca denetimli)
- Parola: blok parola otomatik doldurma (yalnızca denetimli)
- Parola: parola yakınlık isteklerini engelle (yalnızca denetimli)
- Parola: parola paylaşımını engelle (yalnızca denetimli)

**MacOS ayarları**: 
- Parola: blok parola otomatik doldurma
- Parola: parola yakınlığı isteklerini engelle
- Parola: parola paylaşımını engelle

Bu ayarlar hakkında daha fazla bilgi edinmek için bkz. [iOS](../configuration/device-restrictions-ios.md) ve [MacOS](../configuration/device-restrictions-macos.md) cihaz kısıtlama ayarları.

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="autopilot-support-for-hybrid-azure-active-directory-joined-devices-preview----1048100--"></a>Karma Azure Active Directory katılmış cihazlar için Autopilot desteği (Önizleme) <!-- 1048100-->
Artık, Autopilot kullanarak karma Azure Active Directory katılmış cihazları ayarlayabilirsiniz. Karma Autopilot özelliğini kullanmak için cihazların kuruluşunuzun ağına katılması gerekir. Daha fazla bilgi için bkz. [Intune ve Windows Autopilot kullanarak karma Azure AD 'ye katılmış cihazları dağıtma](../enrollment/windows-autopilot-hybrid.md).
Bu özellik, sonraki birkaç gün boyunca kullanıcı tabanına göre kullanıma alınıyor. Bu nedenle, hesabınıza çıkana kadar bu adımları izleyemeyebilirsiniz.

#### <a name="select-apps-tracked-on-the-enrollment-status-page---2531007---"></a>Kayıt durumu sayfasında izlenen uygulamaları seçin<!-- 2531007 -->
Kayıt durumu sayfasında hangi uygulamaların izleneceğini seçebilirsiniz. Bu uygulamalar yüklenene kadar, Kullanıcı cihazı kullanamaz. Daha fazla bilgi için bkz. [kayıt durumu sayfası ayarlama](../enrollment/windows-enrollment-status.md).

#### <a name="search-for-autopilot-device-by-serial-number---2595788---"></a>Autopilot cihazı seri numarasına göre ara <!--2595788 -->
Artık, Autopilot cihazlarını seri numarasına göre arayabilirsiniz. Bunu yapmak için, **cihaz kaydı** > **Windows kaydı** > **cihazları** ' nı seçin > **seri numarasına göre ara** kutusuna bir seri numarası yazın > Enter tuşuna basın.

#### <a name="track-installation-of-office-proplus---2620217---"></a>Office ProPlus yüklemesini izleyin <!--2620217 -->
Kullanıcılar, [kayıt durumu sayfasını](../enrollment/windows-enrollment-status.md)kullanarak, [Office ProPlus](../apps/apps-add-office365.md) 'ın yükleme ilerlemesini izleyebilir. Daha fazla bilgi için bkz. [kayıt durumu sayfası ayarlama](../enrollment/windows-enrollment-status.md).

#### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low----2237572---"></a>Süresi dolan VPP belirteci veya Şirket Portalı lisansı düşük çalışıyor uyarıları <!-- 2237572 -->
DEP kaydı sırasında Şirket Portalı önceden sağlamak için toplu satın alma programı 'nı (VPP) kullanıyorsanız, Intune, VPP belirtecinin sona ermek üzereyken ve Şirket Portalı lisansları düşük çalıştığında sizi uyarır.

#### <a name="macos-device-enrollment-program-support-for-apple-school-manager-accounts---3006133---"></a>macOS Aygıt Kayıt Programı Apple Okul Yöneticisi hesapları için destek <!--3006133 -->
Intune artık, Apple Okul Yöneticisi hesapları için macOS cihazlarında Aygıt Kayıt Programı kullanımını desteklemektedir.  Daha fazla bilgi için bkz. [macOS cihazlarını Apple Okul Yöneticisi veya aygıt kayıt programı Ile otomatik olarak kaydetme](../enrollment/device-enrollment-program-enroll-macos.md).

#### <a name="new-intune-device-subscription-sku---3312071--"></a>Yeni Intune cihaz aboneliği SKU 'SU <!--3312071-->
Kurumdaki cihazların yönetilmesi maliyetini azaltmaya yardımcı olmak için, yeni bir cihaz tabanlı abonelik SKU 'SU kullanıma sunulmuştur. Bu Intune cihaz SKU 'SU, aylık olarak cihaz başına lisanslanır. Fiyat, lisans programına göre farklılık gösterir. Doğrudan Microsoft 365 Yönetim Merkezi aracılığıyla ve [Kurumsal Anlaşma](https://www.microsoft.com/licensing/licensing-programs/enterprise?activetab=enterprise-tab:primaryr2) (EA), [Microsoft ürün ve hizmet sözleşmesi](https://www.microsoft.com/licensing/mpsa/default) (MPSA), [Microsoft açık anlaşmalar](https://partner.microsoft.com/licensing/licensing-agreements)ve [bulut çözümü sağlayıcısı](https://www.microsoftpartnercommunity.com/t5/Partnership-101/What-is-the-Cloud-Solution-Provider-CSP-program/td-p/2453) (CSP) aracılığıyla kullanılabilir .

### <a name="device-management"></a>Cihaz yönetimi

#### <a name="temporarily-pause-kiosk-mode-on-android-devices-to-make-changes----3041935---"></a>Değişiklik yapmak için Android cihazlarda bilgi noktası modunu geçici olarak duraklatma <!-- 3041935 -->
Android cihazlarını çok uygulama bilgi noktası modunda kullanırken, bir BT yöneticisinin cihazda değişiklik yapması gerekebilir. Bu güncelleştirme, bir BT yöneticisinin PIN kullanarak bilgi noktası modunu geçici olarak duraklatmasını ve tüm cihaza erişmesini sağlayan yeni çok uygulama bilgi noktası ayarları içerir.
Bilgi noktası ayarlarını görmek için bkz. [Android kurumsal cihaz kısıtlamaları](../configuration/device-restrictions-android-for-work.md).

#### <a name="enable-virtual-home-button-on-android-enterprise-kiosk-devices-----3042021---"></a>Android kurumsal bilgi noktası cihazlarda sanal giriş düğmesini etkinleştirme  <!-- 3042021 -->
Yeni bir ayar, kullanıcıların cihazındaki bir geçici düğmeye dokunarak yönetilen giriş ekranı uygulaması ve diğer atanmış uygulamalar arasında çok uygulama bilgi noktası cihazında geçiş yapmasına olanak tanır. Bu ayar özellikle bir kullanıcının bilgi noktası uygulamasının "geri" düğmesine uygun şekilde yanıt vermediği senaryolarda yararlıdır. Bu ayarı şirkete ait, tek kullanım Android cihazları için yapılandırabileceksiniz. **Sanal giriş düğmesini**etkinleştirmek veya devre dışı bırakmak için Azure Portal > cihaz yapılandırmasında Intune 'a gidin. Bilgi noktası ayarlarını düzenlemek için geçerli bir cihaz yapılandırma profili seçin veya yeni bir cihaz oluşturun.
Bilgi noktası ayarlarını görmek için bkz. [Android kurumsal cihaz kısıtlamaları](../configuration/device-restrictions-android-for-work.md).




<!-- ########################## -->
## <a name="october-2018"></a>Ekim 2018

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="access-to-key-profile-properties-using-the-company-portal-app----772203---"></a>Şirket Portalı uygulamasını kullanarak anahtar profili özelliklerine erişim <!-- 772203 -->
Son kullanıcılar artık, Şirket portalı uygulamasından parola sıfırlama gibi anahtar hesap özelliklerine ve eylemlerine erişebilir. 

#### <a name="3rd-party-keyboards-can-be-blocked-by-app-settings-on-ios----1248481---"></a>üçüncü taraf klavyeler, iOS üzerindeki uygulama ayarları tarafından engellenebilir <!-- 1248481 -->
İOS cihazlarında, Intune yöneticileri, ilkeyle korunan uygulamalardaki kuruluş verilerine erişirken 3. taraf klavye kullanımını engelleyebilirler. Uygulama koruma Ilkesi (APP) 3. parti klavyeleri engelleyecek şekilde ayarlandığında, cihaz kullanıcısı üçüncü taraf bir klavye kullanırken kurumsal verilerle etkileşime geçen her seferinde bir ileti alır. Yerel klavye dışındaki tüm seçenekler engellenir ve cihaz kullanıcıları bu ayarları görmez. Cihaz kullanıcıları iletişim kutusu iletisini yalnızca bir kez görür. 

#### <a name="user-account-access-of-intune-apps-on-managed-android-and-ios-devices----1248496---"></a>Yönetilen Android ve iOS cihazlarda Intune uygulamalarına Kullanıcı hesabı erişimi <!-- 1248496 -->
Microsoft Intune Yöneticisi olarak, yönetilen cihazlarda Microsoft Office uygulamalara hangi kullanıcı hesaplarının ekleneceğini denetleyebilirsiniz. Erişimi yalnızca izin verilen kuruluş Kullanıcı hesaplarıyla sınırlayabilir ve kayıtlı cihazlarda kişisel hesapları engelleyebilirsiniz. 

#### <a name="outlook-ios-and-android-app-configuration-policy---1828527---"></a>Outlook iOS ve Android uygulama yapılandırma ilkesi <!--1828527 -->
Artık, ActiveSync protokolü ile temel kimlik doğrulamasından yararlanan şirket içi kullanıcılar için iOS ve Android için bir Outlook iOS ve Android uygulama yapılandırma ilkesi oluşturabilirsiniz. İOS ve Android için Outlook 'Ta etkinleştirildiğinden ek yapılandırma ayarları eklenecektir.

#### <a name="office-365-pro-plus-language-packs----1833450---"></a>Office 365 Pro Plus dil paketleri <!-- 1833450 -->
Intune Yöneticisi olarak, Intune aracılığıyla yönetilen Office 365 Pro Plus uygulamaları için ek diller dağıtabileceksiniz. Kullanılabilir dillerin listesi dil paketinin **türünü** (çekirdek, kısmi ve yazım denetimi) içerir. Azure portal, **Microsoft Intune** > **istemci uygulamalarını** > **uygulama** > **Ekle**' yi seçin. **Uygulama Ekle** dikey penceresinin **uygulama türü** listesinde, **Office 365 paketi**altında **Windows 10** ' u seçin. **Uygulama paketi ayarları** dikey penceresinde **Diller** ' i seçin.

#### <a name="windows-line-of-business-lob-apps-file-extensions----1884873---"></a>Windows iş kolu (LOB) uygulamaları dosya uzantıları <!-- 1884873 -->
Windows LOB uygulamalarına yönelik dosya uzantıları artık *. msi*, *. appx*, *. appxdemeti*, *. msix*ve *. msixdemeti*içerir. **İstemci uygulamaları**@no__t **-1 @no__t**-3**Ekle**' i seçerek Microsoft Intune bir uygulama ekleyebilirsiniz. Uygulama **Ekle** bölmesi görüntülenir ve bu **uygulama türünü**seçmenizi sağlar. Windows LOB uygulamaları için uygulama türü olarak **Iş kolu** uygulaması ' nı seçin, **uygulama paketi dosyasını**seçin ve ardından uygun uzantıya sahip bir yükleme dosyası girin.

#### <a name="windows-10-app-deployment-using-intune----2309001---"></a>Intune kullanarak Windows 10 uygulama dağıtımı <!-- 2309001 -->
Yöneticiler, iş kolu (LOB) uygulamaları ve Microsoft Store Iş uygulamaları için mevcut destek üzerine binanın yanı sıra Intune 'u, kuruluşunuzun mevcut uygulamalarının çoğunu Windows 10 cihazlarındaki son kullanıcılara dağıtmak için kullanabilir. Yöneticiler, MSU, Setup. exe veya MSP gibi çeşitli biçimlerde Windows 10 kullanıcıları için uygulama ekleyebilir, yükleyebilir ve kaldırabilir. Intune, Windows 10 Işlem merkezini kullanarak durum veya yeniden başlatma gereksinimlerinin son kullanıcılarına bildirimde bulunmak ve yüklemeden önce gereksinim kurallarını değerlendirir. Bu işlevsellik, bu iş yükünü Intune 'a ve buluta kaydırmakla ilgilenen kuruluşların engellemesini etkin bir şekilde engellemeyi caktır. Bu özellik şu anda genel önizleme aşamasındadır ve sonraki birkaç aya göre özelliğe önemli yeni özellikler eklemenizi bekliyoruz. 

#### <a name="app-protection-policy-app-settings-for-web-data----2662995---"></a>Web verileri için uygulama koruma Ilkesi (uygulama) ayarları <!-- 2662995 -->
Hem Android hem de iOS cihazlarında Web içeriği için uygulama ilkesi ayarları, hem http hem de HTTPS web bağlantılarını daha iyi işleyecek ve iOS Universal bağlantıları ve Android uygulama bağlantıları aracılığıyla veri aktarımı sağlayacak şekilde güncelleştirilecektir. 

#### <a name="end-user-device-and-app-content-menu----2771453---"></a>Son Kullanıcı cihaz ve uygulama içeriği menüsü <!-- 2771453 -->
Son kullanıcılar artık cihaz ve uygulamalardaki bağlam menüsünü kullanarak bir cihazı yeniden adlandırma veya uyumluluğu denetleme gibi yaygın eylemleri tetikleyebilirler. 

#### <a name="windows-company-portal-keyboard-shortcuts----2771518---"></a>Windows Şirket Portalı klavye kısayolları <!-- 2771518 -->
Son kullanıcılar artık klavye kısayollarını (Hızlandırıcılar) kullanarak Windows Şirket Portalı uygulama ve cihaz eylemlerini tetikleyebilecektir.

#### <a name="require-non-biometric-pin-after-a-specified-timeout----1506985---"></a>Belirtilen zaman aşımından sonra biyometrik olmayan PIN gerektir <!-- 1506985 -->
Yönetici tarafından belirtilen zaman aşımından sonra biyometrik olmayan bir PIN isteyerek, Intune şirket verilerine erişim için biyometrik kimlik kullanımını kısıtlayarak mobil uygulama yönetimi (MAM) özellikli uygulamalar için geliştirilmiş güvenlik sağlar. Ayarlar, uygulama/MAM özellikli uygulamalarına erişmek için Touch ID (iOS), yüz KIMLIĞI (iOS), Android Biyometri veya diğer gelecekteki biyometrik kimlik doğrulama yöntemlerini kullanan kullanıcıları etkiler. Bu ayarlar, Intune yöneticilerinin Kullanıcı erişimi üzerinde daha ayrıntılı denetime sahip olmasını sağlar ve birden çok parmak izi içeren bir cihazın ya da başka bir biyometrik erişim yönteminin şirket verilerini yanlış bir kullanıcıya açığa çıkardığından bu durumları ortadan kaldırır. Azure portal, **Microsoft Intune**açın. **İstemci uygulamalarını**seçin  > **uygulama koruma ilkeleri** > **Ilke** > **ayarları**ekleyin. Belirli ayarlar için **erişim** bölümünü bulun. Erişim ayarları hakkında daha fazla bilgi için bkz. [iOS ayarları](../apps/app-protection-policy-settings-ios.md#access-requirements) ve [Android ayarları](../apps/app-protection-policy-settings-android.md#access-requirements).

#### <a name="intune-app-data-transfer-settings-on-ios-mdm-enrolled-devices----2244713---"></a>İOS MDM 'ye kayıtlı cihazlarda Intune uygulama veri aktarımı ayarları <!-- 2244713 -->
İOS MDM 'ye kayıtlı cihazlarda Intune uygulama veri aktarımı ayarlarının denetimini, Kullanıcı asıl adı (UPN) olarak da bilinen kayıtlı kullanıcının kimliğini belirtmekten ayırabilirsiniz. Intunemamupn kullanmayan Yöneticiler bir davranış değişikliğini gözlemetmez. Bu işlevsellik kullanılabilir olduğunda, kayıtlı cihazlarda veri aktarımı davranışını denetlemek için ıntunemamupn kullanan yöneticiler yeni ayarları gözden geçirmeli ve uygulama ayarlarını gerektiği şekilde güncelleştirmelidir.

#### <a name="windows-10-win32-apps----2617325---"></a>Windows 10 Win32 uygulamaları <!-- 2617325 -->
Win32 uygulamalarınızı, bireysel kullanıcılar için kullanıcı bağlamında yüklenecek şekilde yapılandırabilir ve uygulamayı cihazın tüm kullanıcıları için yükleyebilirsiniz.

#### <a name="windows-win32-apps-and-powershell-scripts----2617330---"></a>Windows Win32 uygulamaları ve PowerShell betikleri <!-- 2617330 -->
Win32 uygulamaları yüklemek veya PowerShell betikleri yürütmek için son kullanıcıların artık cihazda oturum açması gerekmez. 

#### <a name="troubleshooting-client-app-installation----1363711---"></a>İstemci uygulaması yüklemesinde sorun giderme <!-- 1363711 -->
**Sorun giderme** dikey penceresinde **uygulama yükleme** etiketli sütunu inceleyerek istemci uygulamalarının yükleme başarısını giderebilirsiniz. **Sorun giderme** dikey penceresini görüntülemek Için, Intune portalında, **Yardım ve destek**altında **sorun gider** ' i seçin.

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="create-dns-suffixes-in-vpn-configuration-profiles-on-devices-running-windows-10---1333668---"></a>Windows 10 çalıştıran cihazlarda VPN yapılandırma profillerinde DNS sonekleri oluşturma<!-- 1333668 -->
Bir VPN cihaz yapılandırma profili oluşturduğunuzda (**cihaz yapılandırma** > **profilleri** > **Profil oluştur** > **Windows 10 ve üzeri** platform > **VPN** profili türü), bazı DNS ayarlarını girersiniz. Bu güncelleştirmeyle, Intune 'da birden fazla **DNS soneki** de girebilirsiniz. DNS son eklerini kullanırken, tam etki alanı adı (FQDN) yerine, kısa adını kullanarak bir ağ kaynağı araması yapabilirsiniz. Bu güncelleştirme ayrıca Intune 'daki DNS sonekleri sırasını değiştirmenize de olanak tanır.
[Windows 10 VPN ayarları](../configuration/vpn-settings-windows-10.md#dns-settings) geçerli DNS ayarlarını listeler.
Uygulama hedefi: Windows 10 cihazları

#### <a name="support-for-always-on-vpn-for-android-enterprise-work-profiles----1333705---"></a>Android kurumsal iş profilleri için Always on VPN desteği <!-- 1333705 -->
Bu güncelleştirmede, yönetilen iş profilleriyle Android kurumsal cihazlarda her zaman açık VPN bağlantılarını kullanabilirsiniz. Her zaman açık VPN bağlantıları bağlı kalır veya Kullanıcı cihazının kilidini açtığında, cihaz yeniden başlatıldığında veya kablosuz ağ değiştiğinde hemen yeniden bağlantı kurar. Ayrıca, bağlantıyı "kilitleme" moduna koyabilirsiniz, bu da VPN bağlantısı etkin olana kadar tüm ağ trafiğini engeller.
**Cihaz yapılandırma** > **PROFILLERDEKI**her zaman VPN 'yi etkinleştirebilirsiniz @no__t **-3 platform**> **cihaz kısıtlamaları** > **bağlantı** ayarları  > **Android Enterprise** .

#### <a name="issue-scep-certificates-to-user-less-devices----1744554---"></a>Kullanıcı-daha az cihazlara SCEP sertifikaları verme <!-- 1744554 -->
Şu anda kullanıcılara sertifika verilir. Bu güncelleştirme ile, bilgi noktaları (**cihaz yapılandırma** > **profilleri** >  Platform**oluşturma** > **Windows 10 ve ÜZERI** platformu) dahil olmak üzere cihazlara SCEP sertifikaları verilebilir > Profil için **SCEP sertifikası** ). Diğer güncelleştirmeler şunlardır:
- Bir SCEP profilindeki **Konu** özelliği artık özel bir metin kutusu ve yeni değişkenler içerebilir. 
- Bir SCEP profilindeki **konu alternatif adı (San)** özelliği artık bir tablo biçimidir ve yeni değişkenler içerebilir. Tabloda, bir yönetici öznitelik ekleyebilir ve değeri özel bir metin kutusuna doldurabilir. SAN aşağıdaki öznitelikleri destekleyecektir: 
  - DNS
  - E-posta adresi
  - 'LE

  Bu yeni değişkenler, statik metinle birlikte özel bir değer metin kutusuna eklenebilir. Örneğin, DNS özniteliği `DNS = {{AzureADDeviceId}}.domain.com` olarak eklenebilir.

  > [!NOTE]
  > Süslü ayraç, noktalı virgül ve "{}; |" kanal sembolleri, SAN 'ın statik metninde çalışmayacaktır. Küme ayraçları yalnızca `Subject` ya da `Subject alternative name` için kabul edilecek yeni cihaz sertifikası değişkenlerinden birini içermelidir. 

Yeni cihaz sertifikası değişkenleri:  

```
"{{AAD_Device_ID}}",
"{{Device_Serial}}",
"{{Device_IMEI}}",
"{{SerialNumber}}",
"{{IMEINumber}}",
"{{AzureADDeviceId}}",
"{{WiFiMacAddress}}",
"{{IMEI}}",
"{{DeviceName}}",
"{{FullyQualifiedDomainName}}",
"{{MEID}}",
```

> [!NOTE]
> - `{{FullyQualifiedDomainName}}` yalnızca Windows ve etki alanına katılmış cihazlar için geçerlidir. 
> - Bir cihaz sertifikası için konu veya SAN 'da ıMEı, seri numarası ve tam etki alanı adı gibi cihaz özelliklerini belirtirken, bu özelliklerin cihaza erişimi olan bir kişi tarafından taklit edilebilir olduğunu unutmayın. 

[Bir SCEP sertifika profili oluşturma](../protect/certificates-profile-scep.md#create-a-scep-certificate-profile) bir SCEP yapılandırma profili oluştururken geçerli değişkenleri listeler. 

Uygulama hedefi: Wi-Fi için desteklenen Windows 10 ve üzeri ve iOS

#### <a name="remotely-lock-uncompliant-devices----2064495---"></a>Uyumlu olmayan cihazları uzaktan kilitleme <!-- 2064495 -->
Bir cihaz uyumlu olmadığında, uyumluluk ilkesinde cihazı uzaktan kilitleyen bir eylem oluşturabilirsiniz. Intune > **cihaz uyumluluğu**, yeni bir ilke oluşturun veya var olan bir Ilke > **özellikleri**seçin. Uyumsuzluk  > **Ekle** **eylemini**seçin ve cihazı uzaktan kilitlemeyi seçin.
Desteklenen: 
- Android
- iOS
- macOS
- Windows 10 Mobile 
- Windows Phone 8,1 ve üzeri 

#### <a name="windows-10-and-later-kiosk-profile-improvements-in-the-azure-portal----2748224---"></a>Azure portal Windows 10 ve üzeri bilgi noktası profili geliştirmeleri <!-- 2748224 -->
Bu güncelleştirme, Windows 10 bilgi noktası cihaz yapılandırma profiline yönelik aşağıdaki geliştirmeleri içerir (**cihaz yapılandırma** > **profilleri** >  Platform**için @no__t-** 5**Windows 10 ve üzeri sürümler** >  **Profil türü için bilgi noktası önizlemesi** ): 
- Şu anda, aynı cihazda birden çok bilgi noktası profili oluşturabilirsiniz. Bu güncelleştirmeyle Intune, cihaz başına yalnızca bir bilgi noktası profilini destekleyecektir. Tek bir cihazda birden çok bilgi noktası profiline ihtiyacınız varsa, özel bir URI kullanabilirsiniz.
- **Birden çok uygulama bilgi noktası** profilinde, uygulama kılavuzundaki **Başlangıç menüsü düzeni** için uygulama kutucuğu boyutunu ve sırasını seçebilirsiniz. Daha fazla özelleştirmeyi tercih ediyorsanız bir XML dosyasını karşıya yüklemeye devam edebilirsiniz.
- Bilgi noktası tarayıcı ayarları **bilgi noktası** ayarlarına taşınıyor. Şu anda **bilgi noktası Web tarayıcısı** ayarlarının Azure Portal kendi kategorileri vardır.
Uygulama hedefi: Windows 10 ve üzeri

#### <a name="pin-prompt-when-you-change-fingerprints-or-face-id-on-an-ios-device-----2637704----"></a>Bir iOS cihazında parmak izlerini veya yüz KIMLIĞINI değiştirdiğinizde PIN istemi  <!-- 2637704  -->
Artık iOS cihazlarında biyometrik değişiklikler yaptıktan sonra kullanıcılardan PIN kodu istenir. Bu, kayıtlı parmak izleri veya yüz KIMLIĞI değişikliklerini içerir. İstem zamanlaması, *erişim gereksinimlerini yeniden denetle (dakika)* zaman aşımı ' nin yapılandırmasının nasıl yapıldığını gösterir.  Hiçbir PIN ayarlanmamışsa, kullanıcıdan bir tane ayarlaması istenir. 
 
Bu özellik yalnızca iOS için kullanılabilir ve iOS, sürüm 9.0.1 veya üzeri için Intune uygulama SDK 'sını tümleştiren uygulamaların katılımını gerektirir. Uygulamanın hedeflenen uygulamalarda zorlanabilmesi için SDK tümleştirme gereklidir. Bu tümleştirme, temelinde gerçekleşir ve belirli uygulama ekiplerine bağımlıdır. Katılan bazı uygulamalar WXP, Outlook, Managed Browser ve Yammer içerir.

#### <a name="network-access-control-support-on-ios-vpn-clients----1333693---"></a>İOS VPN istemcilerinde Ağ erişim denetimi desteği <!-- 1333693 -->
Bu güncelleştirmeyle, Cisco AnyConnect, F5 Access ve iOS için Citrix SSO için bir VPN yapılandırma profili oluştururken ağ Access Control (NAC) etkinleştiren yeni bir ayar vardır. Bu ayar, cihazın NAC KIMLIĞININ VPN profiline dahil edilmesini sağlar. Şu anda, bu yeni NAC KIMLIĞINI destekleyen hiçbir VPN istemcisi ya da NAC iş ortağı çözümü yoktur, ancak bunu yaparken [destek blog gönderimizle](ttps://aka.ms/iOS12_and_vpn) size bilgi vereceğiz.

NAC 'yi kullanmak için şunları yapmanız gerekir:
1. Intune 'un VPN profillerine cihaz kimlikleri eklemesine izin vermeyi tercih et
2. NAC sağlayıcı yazılımınızı/belleniminizi doğrudan NAC sağlayıcınızdan kılavuzluk kullanarak güncelleştirin

Bir iOS VPN profili içindeki bu ayarla ilgili bilgi için, bkz. [Microsoft Intune iOS CIHAZLARıNDA VPN ayarları ekleme](../configuration/vpn-settings-ios.md). Ağ erişim denetimi hakkında daha fazla bilgi için bkz. [Intune Ile ağ erişim denetimi (NAC) Tümleştirmesi](../protect/network-access-control-integrate.md). 

Uygulama hedefi: iOS

#### <a name="remove-an-email-profile-from-a-device-even-when-theres-only-one-email-profile----1818139---"></a>Yalnızca bir e-posta profili olduğunda bile cihazdan e-posta profilini kaldırma <!-- 1818139 -->
Daha önce, tek e-posta profilinde bir e-posta *profilini cihazdan* kaldıramadık. Bu güncelleştirmeyle, bu davranış değişir. Artık, cihazdaki tek e-posta profili olsa da bir e-posta profilini kaldırabilirsiniz. Ayrıntılar için bkz. [Intune kullanarak cihazlara e-posta ayarları ekleme](../configuration/email-settings-configure.md) .

#### <a name="powershell-scripts-and-aad----2309469---"></a>PowerShell betikleri ve AAD <!-- 2309469 -->
Intune 'daki PowerShell betikleri AAD cihaz güvenlik gruplarını hedefleyebilir.

#### <a name="new-required-password-type-default-setting-for-android-android-enterprise---2649963---"></a>Android, Android Enterprise için yeni "gerekli parola türü" varsayılan ayarı<!-- 2649963 -->
Yeni bir uyumluluk ilkesi oluşturduğunuzda (**ıntune** > **cihaz uyumluluğu**@no__t **-3** **ilke** >  Platform için  > **Android** veya **Android Enterprise** > sistem güvenliği), **gerekli parola türü** değişiklikleri için varsayılan değer:

Kimden: cihaz varsayılanı: en az sayısal

Uygulama hedefi: Android, Android Enterprise

Bu ayarları görmek için [Android](../protect/compliance-policy-create-android.md) ve [Android Enterprise](../protect/compliance-policy-create-android-for-work.md)'a gidin.

#### <a name="use-a-pre-shared-key-in-a-windows-10-wi-fi-profile----2662938---"></a>Windows 10 Wi-Fi profilinde önceden paylaşılan anahtar kullanma <!-- 2662938 -->
Bu güncelleştirmeyle, Windows 10 için Wi-Fi yapılandırma profilinin kimliğini doğrulamak üzere WPA/WPA2-Kişisel güvenlik protokolü ile önceden paylaşılan anahtar (PSK) kullanabilirsiniz. Windows 10 Ekim 2018 Güncelleştirmesi ' nde cihazlar için tarifeli ağ için maliyet yapılandırmasını da belirtebilirsiniz.

Şu anda, bir Wi-Fi profilini içeri aktarmanız veya önceden paylaşılan bir anahtar kullanmak için özel bir profil oluşturmanız gerekir. [Windows 10 Için Wi-Fi ayarları](../configuration/wi-fi-settings-windows.md) geçerli ayarları listeler. 

#### <a name="remove-pkcs-and-scep-certificates-from-your-devices----3218390---"></a>Cihazlarınızdan PKCS ve SCEP sertifikalarını kaldırın <!-- 3218390 -->
Bazı senaryolarda, PKCS ve SCEP sertifikaları bir gruptan bir ilkeyi kaldırırken, bir yapılandırma veya uyumluluk dağıtımını silerken ya da mevcut bir SCEP veya PKCS profilini güncelleştiren bir yöneticinin bile cihazlarda kaldığı yerden sonuçlanır. Bu güncelleştirme davranışı değiştirir. PKCS ve SCEP sertifikalarının cihazlardan kaldırıldığı bazı senaryolar ve bu sertifikaların cihazda kaldığı bazı senaryolar vardır. Bu senaryolar için [MICROSOFT INTUNE SCEP ve PKCS sertifikalarını kaldırma](../protect/remove-certificates.md) bölümüne bakın.

#### <a name="use-gatekeeper-on-macos-devices-for-compliance----2504381---"></a>Uyumluluk için macOS cihazlarda geçit kullanma <!-- 2504381 -->
Bu güncelleştirme, cihazları uyumluluk için değerlendirmek üzere macOS Gatekeeper ' i içerir. Gatekeeper özelliğini ayarlamak için, [macOS cihazları için bir cihaz uyumluluk Ilkesi ekleyin](../protect/compliance-policy-create-mac-os.md).


### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="apply-autopilot-profile-to-enrolled-win-10-devices-not-already-registered-for-autopilot----1558983---"></a>Autopilot için kaydedilmemiş olan kayıtlı Win 10 cihazlarına Autopilot profili Uygula <!-- 1558983 -->
Daha önce Autopilot için kaydedilmemiş olan kayıtlı Win 10 cihazlarına Autopilot profilleri uygulayabilirsiniz. Autopilot profilinde, Autopilot olmayan cihazları Autopilot dağıtım hizmetiyle otomatik olarak kaydetmek için **tüm hedeflenen cihazları Autopilot 'ye Dönüştür** seçeneğini belirleyin. Kaydın işlenmesine 48 saat izin verin. Cihazın kaydı kaldırılırken ve sıfırlandığında, Autopilot bunu sağlayacaktır.

#### <a name="create-and-assign-multiple-enrollment-status--page-profiles-to-azure-ad-groups----2526564---"></a>Birden çok kayıt durumu sayfası profilini Azure AD gruplarına oluşturma ve atama <!-- 2526564 -->
Artık Azure Grup Ekle ' ye birden çok kayıt durumu sayfası profili [oluşturabilir ve atayabilirsiniz](../enrollment/windows-enrollment-status.md) .

#### <a name="migration-from-device-enrollment-program-to-apple-business-manager-in-intune---2748613--"></a>Aygıt Kayıt Programı Intune 'da Apple Business Manager 'a geçiş <!--2748613-->
Apple Business Manager (ABD) Intune 'da çalışarak, hesabınızı Aygıt Kayıt Programı (DEP) konumundan ABD 'ye yükseltebilirsiniz. Intune 'daki işlem aynıdır. Apple hesabınızı DEP 'den ABD 'ye yükseltmek için [https://support.apple.com/HT208817]( https://support.apple.com/HT208817)' e gidin.

#### <a name="alert-and-enrollment-status-tabs-on-the-device-enrollment-overview-page---2748656--"></a>Cihaz kaydına Genel Bakış sayfasında uyarı ve kayıt durumu sekmeleri <!--2748656-->
Uyarılar ve kayıt sorunları artık cihaz kaydına Genel Bakış sayfasında ayrı sekmelerde görüntülenir.

#### <a name="enrollment-abandonment-report----1382924---"></a>Kayıt bırakma raporu <!-- 1382924 -->
Terk edilmiş kayıtlar hakkında ayrıntılar sağlayan yeni bir rapor, **cihaz kaydı** > **İzleyicisi**altında bulunabilir. Daha fazla bilgi için bkz. [Şirket portalı bırakma raporu](../enrollment/enrollment-report-company-portal-abandon.md).

#### <a name="new-azure-active-directory-terms-of-use-feature----2870393---"></a>Yeni Azure Active Directory kullanım koşulları özelliği <!-- 2870393 -->
Azure Active Directory, mevcut Intune hüküm ve koşulları yerine kullanabileceğiniz bir kullanım koşulları özelliğine sahiptir. Azure AD kullanım koşulları özelliği, hangi şartlar gösterileceği ve gösterileceği, daha iyi yerelleştirme desteğinin, koşulların nasıl işlendiği ve iyileştirildiğine ilişkin daha fazla esneklik sağlar. Azure AD kullanım koşulları özelliği, ayrıca Enterprise Mobility + Security E3 Suite 'in bir parçası olan Azure Active Directory Premium P1 gerektirir. Daha fazla bilgi edinmek için, [Kullanıcı erişimi için şirketinizin hüküm ve koşullarını Yönetme makalesine](../enrollment/terms-and-conditions-create.md)bakın.

#### <a name="android-device-owner-mode-support---3188762--"></a>Android cihaz sahibi modu desteği <!--3188762-->
Samsung KNOX mobil kaydı için, Intune artık cihazların Android cihaz sahibi yönetim moduna kaydedilmesini desteklemektedir. WiFi veya hücresel ağlardaki kullanıcılar cihazlarını ilk kez açtığında yalnızca birkaç dokunmasıyla kayıt yapabilir. Daha fazla bilgi için bkz. [Samsung 's Knox mobil kaydı kullanarak Android cihazlarını otomatik olarak kaydetme](../enrollment/android-samsung-knox-mobile-enroll.md).

### <a name="device-management"></a>Cihaz yönetimi
#### <a name="new-settings-for-software-updates------1907869---"></a>Yazılım güncelleştirmeleri için yeni ayarlar   <!-- 1907869 -->  
- Artık son kullanıcılara uyarı veren bazı bildirimleri, en son yazılım güncelleştirmelerini yüklemeyi bitirmek için gereken yeniden başlatmalar hakkında daha fazla bilgi yapılandırabilirsiniz.   
- Artık, KCG senaryolarını destekleyen iş saatleri dışında gerçekleşen yeniden başlatmalar için yeniden başlatma uyarı istemi yapılandırabilirsiniz.

#### <a name="group-windows-autopilot-enrolled-devices-by-correlator-id----2075110---"></a>Windows Autopilot-kayıtlı cihazlarını ilişkilendirici KIMLIĞINE göre Gruplandır <!-- 2075110 -->
Intune artık Configuration Manager aracılığıyla [mevcut cihazlarda Autopilot](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/New-Windows-Autopilot-capabilities-and-expanded-partner-support/ba-p/260430) kullanarak Windows cihazlarını BIR ilişkilendirici kimliğiyle gruplandırmayı desteklemektedir. İlişkilendirici KIMLIĞI, Autopilot yapılandırma dosyasının bir parametresidir. Intune, [Azure AD cihaz özniteliği KayıtAdı](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#rules-for-devices) "OfflineAutopilotprofile-<correlator ID>" değerine eşit olacak şekilde otomatik olarak ayarlanır. Bu, Azure AD dinamik gruplarının, çevrimdışı Autopilot kayıtları için KayıtAdı özniteliği aracılığıyla ilişkilendirici KIMLIĞINI temel alarak oluşturulmasına olanak sağlar. Daha fazla bilgi için bkz. [var olan cihazlar Için Windows Autopilot](../enrollment/enrollment-autopilot.md#windows-autopilot-for-existing-devices).

#### <a name="intune-app-protection-policies----2984657---"></a>Intune uygulama koruma ilkeleri <!-- 2984657 -->
Intune uygulama koruma ilkeleri, Intune korumalı uygulamalar için Microsoft Outlook ve Microsoft Word gibi çeşitli veri koruma ayarları yapılandırmanıza olanak tanır. Tek tek ayarları bulmayı kolaylaştırmak için hem [iOS](../apps/app-protection-policy-settings-ios.md) hem de [Android](../apps/app-protection-policy-settings-android.md) için bu ayarların görünümünü değiştirdik. İlke ayarlarının üç kategorisi vardır:
- **Verileri yeniden konumlandırma** -bu grup, kesme, kopyalama, yapıştırma ve farklı kaydet kısıtlamaları gibi veri kaybı önleme (DLP) denetimlerini içerir. Bu ayarlar, kullanıcıların uygulamalardaki verilerle nasıl etkileşime gireceğini tespit ediyor.
- **Erişim gereksinimleri** -bu grup, son kullanıcının uygulamalara iş bağlamında nasıl eriştiğini tespit eden uygulama başına PIN seçeneklerini içerir.  
- **Koşullu başlatma** -bu grup, en düşük işletim sistemi ayarları, jailbreak ve kökü belirtilmiş cihaz algılama ve çevrimdışı kullanım süreleri gibi ayarları barındırır.  
  
Ayarların işlevselliği değişmez, ancak ilke yazma akışında çalışırken bu ayarları bulmak daha kolay olacaktır.

#### <a name="restricts-apps-and-block-access-to-company-resources-on-android-devices----2451462----"></a>Android cihazlarda uygulamaları kısıtlar ve şirket kaynaklarına erişimi engelleyin <!-- 2451462  -->  
**Cihaz uyumluluğu** >  ilke **@no__t-** 3**Ilke oluştur** > **Android** > **sistem güvenliği**, *cihaz güvenliği* bölümünün altında **Kısıtlanmış uygulamalar**adlı yeni bir ayar vardır. **Sınırlı uygulamalar** ayarı, cihazda belirli uygulamalar yüklüyse şirket kaynaklarına erişimi engellemek için bir uyumluluk ilkesi kullanır. Sınırlı uygulamalar cihazdan kaldırılana kadar cihaz uyumlu değil olarak değerlendirilir.
Şunlara uygulanır 
- Android

### <a name="intune-apps"></a>Intune uygulamaları

#### <a name="intune-will-support-a-maximum-package-size-of-8-gb-for-lob-apps----1727158---"></a>Intune, LOB uygulamaları için en fazla 8 GB paket boyutunu destekleyecektir <!-- 1727158 -->
Intune, iş kolu (LOB) uygulamaları için maksimum paket boyutunu 8 GB olarak artırmıştır. Daha fazla bilgi için bkz. [Microsoft Intune uygulama ekleme](../apps/apps-add.md).

#### <a name="add-custom-brand-image-for-company-portal-app----1916266---"></a>Şirket Portalı uygulaması için özel marka görüntüsü ekleme <!-- 1916266 -->
Microsoft Intune Yöneticisi olarak, iOS Şirket Portalı uygulamasındaki kullanıcının profil sayfasında arka plan görüntüsü olarak görüntülenecek özel bir marka görüntüsünü karşıya yükleyebilirsiniz. Şirket Portalı uygulamasını yapılandırma hakkında daha fazla bilgi için bkz. [Microsoft Intune şirket portalı uygulamasını yapılandırma](../apps/company-portal-app.md).

#### <a name="intune-will-maintain-the-office-localized-language-when-updating-office-on-end-users-machines----2971030---"></a>Intune, son kullanıcılar makinelerinde Office 'i güncelleştirirken Office yerelleştirilmiş dilini koruyacaktır <!-- 2971030 -->
Intune Son Kullanıcı makinelerinize Office yüklediğinde, son kullanıcılar önceki ile sahip oldukları dil paketlerini otomatik olarak alır. MSI Office yüklemeleri. Daha fazla bilgi için bkz. [Microsoft Intune Ile Office 365 uygulamalarını Windows 10 cihazlarına atama](../apps/apps-add-office365.md).

### <a name="monitor-and-troubleshoot"></a>İzleme ve sorun giderme

#### <a name="new-intune-support-experience-in-the-microsoft-365-device-management-portal----3076965---"></a>Microsoft 365 cihaz yönetimi portalında yeni Intune destek deneyimi <!-- 3076965 -->
[Microsoft 365 cihaz yönetim portalı]( http://devicemanagement.microsoft.com)'nda Intune için yeni bir yardım ve destek deneyimi sunuyoruz. Yeni deneyim, sorununuzu kendi sözcüklerinizle açıklamanıza ve sorun giderme öngörüleri ve Web tabanlı düzeltme içerikleri almanıza olanak sağlar. Bu çözümler, Kullanıcı sorguları tarafından yönetilen kural tabanlı makine öğrenimi algoritması aracılığıyla sunulur.  

Soruna özgü kılavuza ek olarak, yeni durum oluşturma iş akışını da kullanarak e-posta veya telefon ile bir destek talebi açabilirsiniz.  

Piyasaya çıkma kapsamında olan müşteriler için, bu yeni deneyim, yardım ve destek ' i açtığınızda kullandığınız konsolun alanını temel alan, önceden seçilmiş bir statik seçenek kümesinin geçerli yardım ve destek deneyiminin yerini alır.  

*Bu yeni yardım ve destek deneyimi, tüm kiracılara değil, ancak cihaz yönetim portalında kullanılabilir. Bu yeni deneyim için katılımcılar, kullanılabilir Intune kiracılarından rastgele seçilir. Dağıtımı genişlettiğimiz için yeni kiracılar eklenecektir.*  

Daha fazla bilgi için bkz. destek alma konusunda [Yardım ve destek deneyimi](get-support.md#help-and-support-experience) Microsoft Intune.  

#### <a name="powershell-module-for-intune--preview-available----951068---"></a>Intune için PowerShell modülü – önizleme kullanılabilir <!-- 951068 -->
Intune API 'SI için Microsoft Graph aracılığıyla destek sağlayan yeni bir PowerShell modülü artık [GitHub](https://aka.ms/intunepowershell)'da önizleme için kullanılabilir. Bu modülün nasıl kullanılacağına ilişkin ayrıntılar için, bu konumdaki Benioku dosyasına bakın.

<!-- ########################## -->
## <a name="september-2018"></a>Eylül 2018

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="remove-duplication-of-app-protection-status-tiles----3083391---"></a>Uygulama koruma durumu kutucuklarının çoğaltılmasını kaldır <!-- 3083391 -->
**İOS Için Kullanıcı durumu** ve Android kutucukları **için Kullanıcı durumu** , hem **istemci uygulamaları-genel bakış** sayfasında hem de **istemci uygulamaları-uygulama koruma durumu** sayfasında bulunur. Durum kutucukları, çoğaltmayı önlemek için **Istemci uygulamalar-genel bakış** sayfasından kaldırılmıştır. 

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="support-for-more-third-party-certification-authorities-ca----3093107---"></a>Diğer üçüncü taraf sertifika yetkilileri (CA) için destek <!-- 3093107 -->
Basit Sertifika Kayıt Protokolü (SCEP) kullanarak artık Windows, iOS, Android ve macOS kullanarak mobil cihazlarda yeni sertifikalar verebilir ve sertifikaları yenileyebilirsiniz.

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="intune-moves-to-support-ios-10-and-later----2454656---"></a>Intune, iOS 10 ve üstünü destekleyecek şekilde taşınıyor <!-- 2454656 -->  
Intune kaydı, Şirket Portalı ve Managed Browser artık yalnızca iOS 10 ve üstünü çalıştıran iOS cihazlarını destekler. Kuruluşunuzda etkilenen cihazları veya kullanıcıları denetlemek için Azure portal > **cihazlar** > **tüm cihazlarda**Intune 'a gidin. IŞLETIM sistemine göre filtreleyin ve ardından, işletim sistemi sürümü ayrıntılarını bırakmak için **sütunlar** 'a tıklayın. Bu kullanıcılardan cihazlarını desteklenen bir işletim sistemi sürümüne yükseltmesini isteyin.  

Aşağıda listelenen bir cihaz varsa veya aşağıda listelenen cihazlardan herhangi birini kaydetmek istiyorsanız yalnızca iOS 9 ve önceki sürümlerini destekledikleri farkında olun.  Intune Şirket Portalı erişmeye devam etmek için, bu cihazları iOS 10 veya üstünü destekleyen cihazlara yükseltmeniz gerekir:  

* iPhone 4S 
* iPod Touch  
* iPad 2 
* iPad (3. nesil) 
* iPad mini (1. nesil)  

### <a name="device-management"></a>Cihaz yönetimi

#### <a name="microsoft-365-device-management-administration-center----3078424---"></a>Microsoft 365 cihaz yönetimi Yönetim Merkezi <!-- 3078424 -->
Microsoft 365 ilden biri basitleştirilmiştir ve arka uç Microsoft 365 hizmetlerini Intune ve Azure AD koşullu erişim gibi uçtan uca senaryolar sunacak şekilde tümleştirdik. Yeni [Microsoft 365 Yönetim Merkezi](http://devicemanagement.microsoft.com) , yönetim deneyimini birleştirmek, basitleştirmek ve bütünleştirmek için yer. Cihaz yönetimi için uzman çalışma alanı, kuruluşunuzun ihtiyaç duyacağı tüm cihaz ve Uygulama Yönetimi bilgilerine ve görevlere kolay erişim sağlar. Bu işlemin, kurumsal Son Kullanıcı bilgi işlem ekipleri için birincil bulut çalışma alanı olmasını bekledik.


<!-- ########################## -->
## <a name="august-2018"></a>Ağustos 2018

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="packet-tunnel-support-for-ios-per-app-vpn-profiles-for-custom-and-pulse-secure-connection-types----1520957---"></a>Özel ve darbeli güvenli bağlantı türleri için iOS uygulama başına VPN profilleri için paket tüneli desteği <!-- 1520957 -->
İOS uygulama başına VPN profilleri kullanırken, uygulama katmanı Tüneli (App-proxy) veya paket düzeyinde tünel oluşturma (paket-tünel) seçeneğini kullanabilirsiniz. Bu seçenekler aşağıdaki bağlantı türleriyle kullanılabilir:
- Özel VPN
- Pulse Secure hangi değerin kullanılacağı konusunda emin değilseniz, VPN sağlayıcınızın belgelerine başvurun.

#### <a name="delay-when-ios-software-updates-are-shown-on-the-device----1949583---"></a>Cihazda iOS yazılım güncelleştirmeleri gösterildiğinde gecikme <!-- 1949583 -->
Intune > **yazılım güncelleştirmeleri** > **güncelleştirme ilkesi iOS için**, cihazların herhangi bir güncelleştirme yüklemesini istemediğiniz gün ve saatleri yapılandırabilirsiniz. Gelecekteki bir güncelleştirmede, cihazda 1-90 günden itibaren bir yazılım güncelleştirmesi ekranda gösterildiğinde geciktirebileceksiniz. 
[İOS güncelleştirme Ilkelerini yapılandırma Microsoft Intune](../protect/software-updates-ios.md) geçerli ayarları listeler.

#### <a name="office-365-proplus-version----2213968---"></a>Office 365 ProPlus sürümü <!-- 2213968 -->
Intune kullanarak Office 365 ProPlus uygulamalarını Windows 10 cihazlarına atarken Office sürümünü seçebilirsiniz. Azure portal, **Microsoft Intune** > **uygulamalar** > **Uygulama Ekle**' yi seçin. Daha sonra **tür** açılan listesinden **Office 365 ProPlus Suite (Windows 10)** seçeneğini belirleyin. İlişkili dikey pencereyi göstermek için **uygulama paketi ayarları** ' nı seçin. **Güncelleştirme kanalını** , **aylık**gibi bir değere ayarlayın. İsteğe bağlı olarak, **Evet**' i seçerek Office 'in diğer sürümünü (MSI) son kullanıcı cihazlarından kaldırın. Son Kullanıcı cihazlarındaki seçili kanal için belirli bir Office sürümünü yüklemek için **özel** ' i seçin. Bu noktada, Office 'in kullanacağı belirli bir **sürümünü** seçebilirsiniz. Kullanılabilir sürümler zamanla değişecektir. Bu nedenle, yeni bir dağıtım oluştururken, kullanılabilen sürümler daha yeni olabilir ve kullanılabilir bazı eski sürümleri olmayabilir. Geçerli dağıtımlar eski sürümü dağıtmaya devam edecek, ancak sürüm listesi kanal başına sürekli olarak güncelleştirilir. Daha fazla bilgi için bkz. [Office 365 ProPlus güncelleştirme kanallarına genel bakış](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus).

#### <a name="support-for-register-dns-setting-for-windows-10-vpn----2282852---"></a>Windows 10 VPN için Register DNS ayarı desteği <!-- 2282852 -->
Bu güncelleştirmeyle, Windows 10 VPN profillerini, iç DNS ile VPN arabirimine atanan IP adreslerini özel profiller kullanılmasına gerek kalmadan dinamik olarak kaydetmek üzere yapılandırabilirsiniz.
Mevcut VPN profili ayarları hakkında daha fazla bilgi için bkz. [Windows 10 VPN ayarları](../configuration/vpn-settings-windows-10.md).

#### <a name="the-macos-company-portal-installer-now-includes-the-version-number-in-the-installer-file-name---2652728--"></a>MacOS Şirket Portalı yükleyicisi artık yükleyici dosya adındaki sürüm numarasını içermektedir <!--2652728-->

#### <a name="ios-automatic-app-updates----2729759---"></a>iOS otomatik uygulama güncelleştirmeleri <!-- 2729759 -->
Otomatik uygulama güncelleştirmeleri, iOS sürüm 11,0 ve üzeri için hem cihaz hem de Kullanıcı lisanslı uygulamalar için çalışır.

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="windows-hello-will-target-users-and-devices----1106609---"></a>Windows Hello, kullanıcıları ve cihazları hedefleyecek <!-- 1106609 -->
[İş Için Windows Hello](../protect/windows-hello.md) ilkesi oluşturduğunuzda, bu, kuruluştaki tüm kullanıcılar için geçerlidir (kiracı genelinde). Bu güncelleştirmeyle, ilke bir cihaz yapılandırma ilkesi (**cihaz yapılandırma** > **profilleri** > **Profil oluştur** > **kimlik @no koruması**kullanarak belirli kullanıcılara veya belirli cihazlara da uygulanabilir. __T-7**iş Için Windows Hello**).
Azure portal Intune 'da, Windows Hello yapılandırması ve ayarları artık hem **cihaz kaydında** hem de **cihaz yapılandırmasında**bulunur. **Cihaz kaydı** , kuruluşun tamamını (kiracı genelinde) hedefler ve Windows AUTOPILOT (OOBE) destekler. **Cihaz yapılandırması** , cihazları ve kullanıcıları iade sırasında uygulanan bir ilkeyi kullanarak hedefler.
Bu özellik için geçerlidir:  
- Windows 10 ve üzeri
- Windows holographic for Business

#### <a name="zscaler-is-an-available-connection-for-vpn-profiles-on-ios----1769858---"></a>Zscaler, iOS üzerinde VPN profilleri için kullanılabilir bir bağlantıdır <!-- 1769858 -->
Bir iOS VPN cihaz yapılandırma profili oluşturduğunuzda (**cihaz yapılandırma** > **profilleri** > **Profil oluştur** > **iOS** platformu > **VPN** profili türü), birkaç bağlantı türü vardır. Cisco, Citrix ve daha fazlasını içeren. Bu güncelleştirme, Zscaler 'ı bağlantı türü olarak ekler. 
[İOS çalıştıran cihazlar Için VPN ayarları](../configuration/vpn-settings-ios.md) , kullanılabilir bağlantı türlerini listeler.

#### <a name="fips-mode-for-enterprise-wi-fi-profiles-for-windows-10----1879077---"></a>Windows 10 için Enterprise Wi-Fi profilleri için FIPS modu <!-- 1879077 -->
Artık Intune Azure portal Windows 10 için Enterprise Wi-Fi profilleri için Federal bilgi Işleme standartları (FIPS) modunu etkinleştirebilirsiniz. Wi-Fi profilinizde etkinleştirmek istiyorsanız, Wi-Fi altyapınızda FIPS modunun etkinleştirildiğinden emin olun.
[Intune 'Da Windows 10 ve üzeri cihazlar Için Wi-Fi ayarları](../configuration/wi-fi-settings-windows.md) , Wi-Fi profili oluşturmayı gösterir.

#### <a name="control-s-mode-on-windows-10-and-later-devices---public-preview----1958649---"></a>Windows 10 ve üzeri cihazlarda denetim S modu-genel önizleme <!-- 1958649 -->
Bu özellik güncelleştirmesiyle, bir Windows 10 cihazını S modunda değiştiren bir cihaz yapılandırma profili oluşturabilir veya kullanıcıların cihazı S-Mode dışına almasını engelleyebilirsiniz. Bu özellik Intune > **cihaz yapılandırması** > **profil** >  **Windows 10 ve üzeri** > **sürüm yükseltme ve mod anahtarı**.
[Windows 10 ' da s modunda giriş](https://www.microsoft.com/windows/s-mode) , s modu hakkında daha fazla bilgi sağlar.
Uygulama hedefi: en son [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) derlemesi (Önizleme aşamasında).

#### <a name="windows-defender-atp-configuration-package-automatically-added-to-configuration-profile----2144658---"></a>Windows Defender ATP yapılandırma paketi otomatik olarak yapılandırma profiline eklendi <!-- 2144658 -->
Intune 'da [Gelişmiş tehdit koruması ve ekleme](../protect/advanced-threat-protection.md#onboard-devices-by-using-a-configuration-profile) cihazları kullanırken, daha önce bir yapılandırma paketini indirmeniz ve yapılandırma profilinize eklemeniz gerekiyordu. Bu güncelleştirmeyle Intune, paketi otomatik olarak Windows Defender Güvenlik Merkezi 'nden alır ve profilinize ekler.
Windows 10 ve üzeri için geçerlidir.

#### <a name="require-users-to-connect-during-device-setup---2311457--"></a>Kullanıcıların cihaz kurulumu sırasında bağlanmasını gerektir <!--2311457-->
Artık cihaz profillerini, Windows 10 kurulumu sırasında ağ sayfasını geçmeden önce cihazın bir ağa bağlanmasını gerektirecek şekilde ayarlayabilirsiniz. Bu özellik önizlemedeyken, bu ayarı kullanmak için bir Windows Insider Build 1809 veya üzeri gereklidir.
Uygulama hedefi: en son [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) derlemesi (Önizleme aşamasında).

#### <a name="restricts-apps-and-block-access-to-company-resources-on-ios-and-android-enterprise-devices----2451462---"></a>İOS ve Android kurumsal cihazlarda uygulamaları kısıtlar ve şirket kaynaklarına erişimi engelleyin <!-- 2451462 -->
**Cihaz uyumluluk**@no__t **-1**ilke  > **Ilke oluştur** > **iOS** > **sistem güvenliği**, yeni bir **kısıtlı uygulamalar** ayarı vardır. Bu yeni ayar, cihazda belirli uygulamalar yüklüyse şirket kaynaklarına erişimi engellemek için bir uyumluluk ilkesi kullanır. Sınırlı uygulamalar cihazdan kaldırılana kadar cihaz uyumlu değil olarak değerlendirilir.
Uygulama hedefi: iOS

#### <a name="modern-vpn-support-updates-for-ios----2459928-1819876-and-2650856---"></a>İOS için modern VPN desteği güncelleştirmeleri <!-- 2459928, 1819876, and 2650856 -->
Bu güncelleştirme, aşağıdaki iOS VPN istemcilerine destek ekler:
- F5 erişimi (sürüm 3.0.1 ve üzeri)
- Citrix SSO
- Palo Alto Networks, bu güncelleştirmede de GlobalProtect sürüm 5,0 ve üzeri.
- Mevcut **F5 erişimi** bağlantı türü, IOS Için **eski F5 erişimi** olarak yeniden adlandırıldı.
- Mevcut **Palo Alto Networks GlobalProtect** bağlantı türü, IOS Için **GlobalProtect (eski) ağları Için Palo Alto** olarak yeniden adlandırıldı.
Bu bağlantı türlerine sahip mevcut profiller, ilgili eski VPN istemcisiyle çalışmaya devam eder. Cisco eski AnyConnect, F5 Access Legacy, Citrix VPN veya Palo Alto Networks ile iOS koruma 4,1 ve önceki bir sürümünü kullanıyorsanız yeni uygulamalara geçmeniz gerekir. İOS 12 ' ye güncelleştirdiklerinde iOS cihazlarında VPN erişiminin kullanılabilir olduğundan emin olmak için bunu mümkün olan en kısa sürede yapın.
İOS 12 ve VPN profilleri hakkında daha fazla bilgi için bkz. [destek ekibi blogu Microsoft Intune](https://go.microsoft.com/fwlink/?linkid=2013806).

#### <a name="export-azure-classic-portal-compliance-policies-to-recreate-these-policies-in-the-intune-azure-portal----2469637---"></a>Bu ilkeleri Intune 'da yeniden oluşturmak için klasik Azure portalı uyumluluk ilkelerini dışarı aktarın Azure portal <!-- 2469637 -->
Klasik Azure portalında oluşturulan uyumluluk ilkeleri kullanım dışı olacaktır. Var olan herhangi bir Uyumluluk ilkesini gözden geçirebilir ve silebilirsiniz, ancak bunları güncelleştiremezsiniz. Herhangi bir Uyumluluk ilkesini geçerli Intune Azure portal geçirmeniz gerekiyorsa, ilkeleri virgülle ayrılmış bir dosya ( *. csv* dosyası) olarak dışarı aktarabilirsiniz. Ardından, bu ilkeleri Intune Azure portal yeniden oluşturmak için dosyadaki ayrıntıları kullanın.

> [!IMPORTANT]
> Klasik Azure portalı yeniden oluşturulduğunda, uyumluluk ilkelerinize erişemeyeceksiniz veya bu ilkeleri görüntüleyemezsiniz. Bu nedenle, ilkelerinizi dışarı aktarıp klasik Azure portalı 'ndan önce Azure portal yeniden oluşturun.

#### <a name="better-mobile---new-mobile-threat-defense-partner----22662717---"></a>Daha iyi mobil-yeni Mobile Threat Defense iş ortağı <!-- 22662717 -->
Microsoft Intune ile tümleştirilen bir mobil tehdit savunması çözümü olan daha Iyi mobil tarafından gerçekleştirilen risk değerlendirmesine dayalı koşullu erişimi kullanarak mobil cihaz erişimini kontrol edebilirsiniz.

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="lock-the-company-portal-in-single-app-mode-until-user-sign-in---1067692---"></a>Kullanıcı oturum açana kadar Şirket Portalı tek uygulama modunda kilitle <!--1067692 --> 
DEP kaydı sırasında Kurulum Yardımcısı yerine Şirket Portalı aracılığıyla bir kullanıcının kimliğini doğruladıysanız, artık Şirket Portalı tek uygulama modunda çalıştırma seçeneğiniz vardır. Bu seçenek, bir kullanıcının cihaza erişmek için oturum açması için Kurulum Yardımcısı tamamlandıktan hemen sonra cihazı kilitler. Bu işlem, cihazın ekleme işlemini tamamlamasına ve herhangi bir kullanıcı bağlı olmadan bir durumda sahipsiz olmadığından emin olur.

#### <a name="assign-a-user-and-friendly-name-to-an-autopilot-device---1346521---"></a>Bir Autopilot cihazına Kullanıcı ve kolay ad atama <!--1346521 -->
Artık [bir kullanıcıyı tek bir Autopilot cihazına atayabilirsiniz](../enrollment/enrollment-autopilot.md). Yöneticiler ayrıca, Autopilot ile cihazlarını ayarlarken Kullanıcı tarafından karşılanırlar 'e kolay adlar verebilir.
Uygulama hedefi: en son [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) derlemesi (Önizleme aşamasında).

#### <a name="use-vpp-device-licenses-to-pre-provision-the-company-portal-during-dep-enrollment----1608345---"></a>DEP kaydı sırasında Şirket Portalı önceden sağlamak için VPP cihaz lisanslarını kullanma <!-- 1608345 -->
Artık toplu satın alma programı (VPP) cihaz lisanslarını, Aygıt Kayıt Programı (DEP) kayıtları sırasında Şirket Portalı önceden sağlamak için kullanabilirsiniz. Bunu yapmak için [bir kayıt profili oluştururken veya düzenlediğinizde](../enrollment/device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile), Şirket portalı yüklemek için kullanmak istediğiniz VPP belirtecini belirtin. Belirtecin süre sonu olmadığından ve Şirket Portalı uygulama için yeterli lisansa sahip olduğunuzdan emin olun. Belirtecin süresi dolduğu veya lisansların tükenme durumlarında, Intune uygulama mağazasını Şirket Portalı (bir Apple KIMLIĞI ister.) olur.

#### <a name="confirmation-required-to-delete-vpp-token-that-is-being-used-for-company-portal-pre-provisioning----2237634---"></a>Şirket Portalı önceden sağlama için kullanılmakta olan VPP belirtecini silmek için onay gerekiyor <!-- 2237634 -->
Bir toplu satın alma programı (VPP) belirtecini silmek için, DEP kaydı sırasında Şirket Portalı önceden sağlamak üzere kullanılıyorsa bir onay gereklidir.

#### <a name="block-windows-personal-device-enrollments----1849498---"></a>Windows kişisel cihaz kayıtlarını engelle <!-- 1849498 -->
[Windows kişisel cihazların](../enrollment/enrollment-restrictions-set.md) Intune 'da [mobil cihaz yönetimine](../enrollment/windows-enroll.md) kaydedilmesini engelleyebilirsiniz. [INTUNE bilgisayar aracısına](../manage-windows-pcs-with-microsoft-intune.md) kayıtlı cihazlar bu özellikle engellenmiyor. Bu özellik, sonraki birkaç haftada bir kullanıma alınıyor, bu nedenle bunu Kullanıcı arabiriminde hemen görmeyebilirsiniz.

#### <a name="specify-machine-name-patterns-in-an-autopilot-profile---1849855--"></a>Autopilot profilinde makine adı desenleri belirtme <!--1849855-->
Autopilot kaydı sırasında [bilgisayar adını](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) oluşturmak ve ayarlamak için [bir bilgisayar adı şablonu belirtebilirsiniz](../enrollment/enrollment-autopilot.md#create-an-autopilot-deployment-profile) . Uygulama hedefi: en son [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) derlemesi (Önizleme aşamasında).

#### <a name="for-windows-autopilot-profiles-hide-the-change-account-options-on-the-company-sign-in-page-and-domain-error-page---1901669---"></a>Windows Autopilot profilleri için şirket oturum açma sayfası ve etki alanı hata sayfasında hesabı Değiştir seçeneklerini gizleyin. <!--1901669 -->
Yöneticilerin şirket oturum açma ve etki alanı hata sayfalarında değişiklik hesabı seçeneklerini gizleyebilmek için [Yeni Windows Autopilot profil seçenekleri](../enrollment/enrollment-autopilot.md#create-an-autopilot-deployment-profile) vardır. Bu seçeneklerin gizlenmesi için şirket markası 'nin Azure Active Directory ' de yapılandırılması gerekir. Uygulama hedefi: en son [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) derlemesi (Önizleme aşamasında).

### <a name="macos-support-for-apple-device-enrollment-program----747651---"></a>Apple Aygıt Kayıt Programı için macOS desteği <!-- 747651 -->
Intune artık macOS cihazlarının Apple Aygıt Kayıt Programı 'a (DEP) kaydedilmesini desteklemektedir. Daha fazla bilgi için bkz. [macOS cihazlarını Apple 'ın aygıt kayıt programı otomatik olarak kaydetme](../enrollment/device-enrollment-program-enroll-macos.md).

### <a name="device-management"></a>Cihaz yönetimi

#### <a name="delete-jamf-devices----2653306--"></a>JAMF cihazlarını silme <!-- 2653306-->
**Cihazlara** giderek JAMF tarafından yönetilen **cihazları silebilirsiniz > >** JAMF cihazını seçin.

#### <a name="change-terminology-to-retire-and-wipe----2175759---"></a>Terminolojiyi "devre dışı bırak" ve "Sil" olarak değiştirin <!-- 2175759 -->
Graph API ile tutarlı olması için, Intune kullanıcı arabirimi ve belgeleri aşağıdaki koşulları değiştirmiştir:
- **Şirket verilerini kaldırma** , "devre dışı bırak" olarak değiştirilecek
- **Fabrika Sıfırlaması** , **Temizleme** olarak değiştirilecek

#### <a name="confirmation-dialog-if-admin-tries-to-delete-mdm-push-certificate----297909500--"></a>Yönetici MDM Anında İletme Sertifikası silmeye çalışırsa onay iletişim kutusu <!-- 297909500-->
Bir Apple MDM anında Iletme sertifikasını silmeye çalışırsa, ilgili iOS ve macOS cihazlarının sayısını bir onay iletişim kutusu görüntüler. Sertifika silinirse, bu cihazların yeniden kaydedilmesi gerekir.

#### <a name="additional-security-settings-for-windows-installer----2282430---"></a>Windows Installer için ek güvenlik ayarları <!-- 2282430 -->
Kullanıcıların uygulama yüklemelerini denetlemesine izin verebilirsiniz. Etkinleştirilirse, aksi takdirde durdurulmuş olabilecek yüklemelerin bir güvenlik ihlali nedeniyle devam etmesine izin verilir. Windows Installer 'ı bir sisteme herhangi bir program yüklerken yükseltilmiş izinleri kullanacak şekilde yönlendirebilirsiniz. Ayrıca, dizine eklenecek Windows Information Protection (WıP) öğelerini ve bunlar hakkında şifrelenmemiş bir konumda depolanan meta verileri de etkinleştirebilirsiniz. İlke devre dışı bırakıldığında, WıP korumalı öğelerin dizini oluşturulmaz ve Cortana veya dosya Gezgini sonuçlarında gösterilmez. Bu seçeneklere yönelik işlevsellik varsayılan olarak devre dışıdır. 

#### <a name="new-user-experience-update-for-the-company-portal-website---2000968---"></a>Şirket Portalı Web sitesi için yeni kullanıcı deneyimi güncelleştirmesi <!--2000968 -->
Müşterilerin geri bildirimlerine göre Şirket Portalı Web sitesine yeni özellikler ekledik. Cihazlarınızdan mevcut işlevlerde ve kullanışlılığın önemli bir gelişmesini öğreneceksiniz. @ No__t-0sitesinin cihaz ayrıntıları, geri bildirim ve destek ve cihaza genel bakış @ no__t-1gibi alanlarda yeni, modern ve hızlı yanıt veren bir tasarım almış. Ayrıca şunları görürsünüz:

- Tüm cihaz platformları genelinde kolaylaştırılmış iş akışları
- İyileştirilmiş cihaz tanımlama ve kayıt akışları
- Daha yararlı hata iletileri
- Kolay bir dil, daha az teknik öğretmek
- Uygulamalara doğrudan bağlantıları paylaşma özelliği
- Büyük uygulama katalogları için geliştirilmiş performans
- Tüm kullanıcılar için daha fazla erişilebilirlik  

[Intune şirket portalı Web sitesi belgeleri](https://docs.microsoft.com/intune-user-help/using-the-intune-company-portal-website) bu değişiklikleri yansıtacak şekilde güncelleştirilmiştir. Uygulama geliştirmeleriyle ilgili bir örnek görüntülemek için bkz. [Intune son kullanıcı uygulamaları Için Kullanıcı Arabirimi güncelleştirmeleri](../whats-new-app-ui.md).  

### <a name="monitor-and-troubleshoot"></a>İzleme ve sorun giderme

#### <a name="enhanced-jailbreak-detection-in-compliance-reporting---2198738---"></a>Uyumluluk raporlamada gelişmiş jailbreak algılama<!-- 2198738 -->
Gelişmiş jailbreak algılama ayarı durumları artık yönetim konsolundaki Tüm uyumluluk raporlarında görüntülenir.

### <a name="role-based-access-control"></a>Rol tabanlı erişim denetimi

#### <a name="scope-tags-for-policies---1081974---"></a>İlkeler için kapsam etiketleri <!--1081974 -->
Intune kaynaklarına erişimi sınırlandırmak için [kapsam etiketleri oluşturabilirsiniz](scope-tags.md) . Bir rol atamasına kapsam etiketi ekleyin ve ardından kapsam etiketini bir yapılandırma profiline ekleyin. Rol yalnızca, eşleşen kapsam etiketleri olan (veya kapsam etiketi olmayan) yapılandırma profillerine sahip kaynaklara erişebilir.





<!-- ########################## -->
## <a name="july-2018"></a>Temmuz 2018

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="line-of-business-lob-app-support-for-macos----1895847---"></a>MacOS için iş kolu (LOB) uygulama desteği <!-- 1895847 -->
Microsoft Intune, macOS LOB uygulamalarının **gerektiği** şekilde dağıtılmasını veya **kayıt ile kullanılabilmesini**sağlar. Son kullanıcılar, macOS için Şirket Portalı veya [Şirket portalı Web sitesi](https://portal.manage.microsoft.com)kullanarak **kullanılabilir** olarak dağıtılan uygulamaları alabilir.

#### <a name="ios-built-in-app-support-for-kiosk-mode----2051098---"></a>bilgi noktası modu için iOS yerleşik uygulama desteği <!-- 2051098 -->
Uygulamaları ve yönetilen uygulamaları depolamanın yanı sıra, artık iOS cihazında bilgi noktası modunda çalışan bir yerleşik uygulama (örneğin Safari) seçebilirsiniz.

#### <a name="edit-your-office-365-pro-plus-app-deployments----2150145---"></a>Office 365 Pro Plus uygulama dağıtımlarınızı düzenleyin <!-- 2150145 -->
Microsoft Intune Yöneticisi olarak, Office 365 Pro Plus uygulama dağıtımlarınızı düzenlemenize daha fazla olanak vardır. Ayrıca, paketin özelliklerinden herhangi birini değiştirmek için dağıtımlarınızı silmeniz artık gerekmez. Azure portal, **Microsoft Intune** > **istemci uygulamalarını** > **uygulama**' yı seçin. Uygulamalar listesinden Office 365 Pro Plus Suite ' i seçin.  

#### <a name="updated-intune-app-sdk-for-android-is-now-available----2744271--"></a>Android için güncelleştirilmiş Intune uygulama SDK 'Sı artık kullanılabilir <!-- 2744271-->
Android için Intune uygulama SDK 'sının güncelleştirilmiş bir sürümü, Android P sürümünü desteklemek için kullanılabilir. Uygulama geliştiricisiyseniz ve Android için Intune SDK 'sını kullanıyorsanız, Android uygulamalarınızda Intune işlevselliğinin Android P cihazlarında beklendiği gibi çalışmaya devam etmesini sağlamak için Intune uygulama SDK 'sının güncelleştirilmiş sürümünü yüklemelisiniz. Intune uygulama SDK 'sının bu sürümü, SDK güncelleştirmelerini gerçekleştiren yerleşik bir eklenti sağlar. Tümleştirilen mevcut kodu yeniden yazmanız gerekmez. Ayrıntılar için bkz. [Android Için ıNTUNE SDK](https://github.com/msintuneappsdk/ms-intune-app-sdk-android). Intune için eski bir rozet stili kullanıyorsanız evrak çantası simgesini kullanmanızı öneririz. Marka ayrıntıları için [Bu GitHub deposuna](https://github.com/msintuneappsdk/intune-app-partner-badge)bakın.

#### <a name="more-opportunities-to-sync-in-the-company-portal-app-for-windows"></a>Windows için şirket portalı uygulamasında eşitlenecek daha fazla fırsat  
Windows için Şirket Portalı uygulaması artık Windows görev çubuğundan ve başlangıç menüsünden doğrudan eşitleme başlatabilmenizi sağlar. Bu özellik özellikle, tek göreviniz cihazları eşitlemek ve şirket kaynaklarına erişim sağlamak için yararlıdır. Yeni özelliğe erişmek için, görev çubuğunuzun veya başlangıç menünüzün sabitlendiği Şirket portalı simgesine sağ tıklayın. Menü seçeneklerinde (bir sıçrama listesi olarak da adlandırılır), **Bu cihazı Eşitle**' yi seçin. Şirket Portalı, **Ayarlar** sayfası açılır ve eşitleme işlemini başlatır. Yeni işlevlere göz atmak için bkz. [Kullanıcı arabirimindeki](../whats-new-app-ui.md)yenilikler.   

#### <a name="new-browsing-experiences-in-the-company-portal-app-for-windows"></a>Windows için şirket portalı uygulamasında yeni gözatma deneyimleri  
Artık Windows için Şirket Portalı uygulamasındaki uygulamalar taranırken veya ararken, var olan **Kutucuklar** görünümü ve yeni eklenen **Ayrıntılar** görünümü arasında geçiş yapabilirsiniz. Yeni görünüm, ad, Yayımcı, Yayın tarihi ve yükleme durumu gibi uygulama ayrıntılarını listeler.  

**Uygulamalar** sayfasının **yüklü** görünümü, tamamlanmış ve sürmekte olan uygulama yüklemeleri hakkındaki ayrıntıları görmenizi sağlar. Yeni görünümün nasıl göründüğünü görmek için bkz. [Kullanıcı arabirimindeki](../whats-new-app-ui.md)yenilikler.  

#### <a name="improved-company-portal-app-experience-for-device-enrollment-managers"></a>Cihaz Kayıt yöneticileri için Şirket Portalı uygulama deneyimi geliştirildi  
Bir cihaz kayıt Yöneticisi (DEM), Windows için Şirket Portalı uygulamasında oturum açtığında, uygulama artık yalnızca DEM 'nin geçerli, çalışan cihazını listelecektir. Bu geliştirme, uygulama, DEM 'ye kayıtlı tüm cihazları göstermeyi denediğinde daha önce gerçekleşen zaman aşımlarını azaltır.  

#### <a name="block-app-access-based-on-unapproved-device-vendors-and-models-----1425689----"></a>Onaylanmamış cihaz satıcılarına ve modellerine bağlı olarak uygulama erişimini engelleyin  <!-- 1425689 ! -->
Intune BT Yöneticisi, belirli bir Android üreticisi listesini ve/veya iOS modellerini Intune Uygulama Koruması Ilkeleri aracılığıyla zorunlu kılabilir. BT Yöneticisi, Android ilkeleri ve iOS ilkelerine yönelik cihaz modelleri için bir dizi üretici için noktalı virgülle ayrılmış bir liste sağlayabilir. Intune Uygulama Koruması Ilkeleri yalnızca Android ve iOS içindir. Bu belirtilen listede gerçekleştirilen iki ayrı eylem vardır:
- Belirtilmeyen cihazlarda uygulama erişiminin bloğu.
- Veya, belirtilen cihazlarda kurumsal verilerin seçmeli bir şekilde silinmesini. 

İlke üzerindeki gereksinimler karşılanmazsa, Kullanıcı hedeflenen uygulamaya erişemez. Ayarlar temelinde, Kullanıcı engellenmiş olabilir veya uygulama içindeki şirket verilerinin seçmeli olarak silinmesine neden olabilir. İOS cihazlarında bu özellik, bu özellik için Intune uygulama SDK 'sını hedeflenen uygulamalarla zorunlu hale getirmek üzere uygulamaların (WXP, Outlook, Managed Browser, Yammer) katılımını gerektirir. Bu tümleştirme, temelinde gerçekleşir ve belirli uygulama ekiplerine bağımlıdır. Android 'de, bu özellik en son Şirket Portalı gerektirir. 

Son Kullanıcı cihazlarında, Intune istemcisi uygulama koruma Ilkeleri için Intune dikey penceresinde belirtilen dizelerin basit bir eşleştirmesine dayalı olarak eylem alır. Bu, tamamen cihazın rapor veren değere bağlıdır. Bu nedenle, BT Yöneticisi amaçlanan davranışın doğru olduğundan emin olmak için önerilir. Bu, küçük bir kullanıcı grubuna hedeflenmiş çeşitli cihaz üreticilerine ve modellere göre bu ayar test edilirken gerçekleştirilebilir. Microsoft Intune, uygulama koruma ilkelerini görüntülemek ve eklemek için **istemci uygulamaları** > **Uygulama koruma ilkeleri** ' ni seçin. Uygulama koruma ilkeleri hakkında daha fazla bilgi için bkz. [Uygulama koruma Ilkeleri nedir](../apps/app-protection-policy.md) ve [Intune 'da uygulama koruma ilkesi erişim eylemlerini kullanarak verileri seçmeli olarak silme](../apps/app-protection-policies-access-actions.md).

#### <a name="access-to-macos-company-portal-pre-release-build----1734766---"></a>MacOS Şirket Portalı yayın öncesi yapıya erişim <!-- 1734766 -->
Microsoft otomatik güncelleştirme 'yi kullanarak, Insider programına katılarak derlemeleri daha erken almak için kaydolabilirsiniz. Kaydolma, son kullanıcılarınız için kullanılabilir olmadan önce güncelleştirilmiş Şirket Portalı kullanmanıza olanak sağlar. Daha fazla bilgi için [Microsoft Intune bloguna](https://blogs.technet.microsoft.com/intunesupport/2018/07/13/use-microsoft-autoupdate-for-early-access-to-the-macos-company-portal-app/)bakın.

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="create-device-compliance-policy-using-firewall-settings-on-macos-devices----1497640---"></a>MacOS cihazlarında güvenlik duvarı ayarlarını kullanarak cihaz uyumluluk ilkesi oluşturma <!-- 1497640 -->
Yeni bir macOS uyumluluk ilkesi oluşturduğunuzda (**cihaz uyumluluk** > **ilkeleri** > **Ilke oluştur** > **Platform: MacOS** > **sistem güvenliği**), bazı yeni **güvenlik duvarı** ayarları vardır kullanılabileceğini 

- **Güvenlik duvarı**: ortamınızda gelen bağlantıları nasıl ele alındığını yapılandırın.
- **Gelen bağlantılar**: DHCP, Bonjour ve IPSec gibi temel Internet Hizmetleri için gerekenler hariç tüm gelen bağlantıları **engelleyin** . Bu ayar tüm paylaşım hizmetlerini de engeller.
- **Gizli mod**: cihazın yoklama isteklerine yanıt vermesini engellemek için gizli modu **etkinleştirin** . Cihaz, yetkili uygulamalar için gelen istekleri yanıtlamaya devam eder.

Uygulama hedefi: macOS 10,12 ve üzeri

#### <a name="new-wi-fi-device-configuration-profile-for-windows-10-and-later----1879077---"></a>Windows 10 ve üzeri için yeni Wi-Fi cihaz yapılandırma profili <!-- 1879077 -->
Şu anda, XML dosyalarını kullanarak Wi-Fi profillerini içeri ve dışarı aktarabilirsiniz. Bu güncelleştirmeyle, tıpkı diğer platformlar gibi doğrudan Intune 'da Wi-Fi cihaz yapılandırma profili oluşturabilirsiniz.

Profili oluşturmak için, **cihaz yapılandırma** > **profilleri**' ni açın  > **Profil oluştur** > **Windows 10 ve üzeri** > **Wi-Fi**. 

Windows 10 ve üzeri için geçerlidir.

#### <a name="kiosk---obsolete-is-grayed-out-and-cant-be-changed----2149998---"></a>Bilgi noktası-kullanımdan kalktı ve değiştirilemez <!-- 2149998 -->
Bilgi noktası (Önizleme) özelliği (**cihaz yapılandırma** > **profilleri** > **Profil oluştur** > **Windows 10 ve üzeri** > **cihaz kısıtlamaları**) kullanımdan kalkmıştır ve bu, [için bilgi noktası ayarlarıyla değiştirilmiştir Windows 10 ve üzeri](../configuration/kiosk-settings.md). Bu güncelleştirmeyle, **bilgi noktası-Kullanımdan kaldırılmış** özelliği gri olur ve Kullanıcı arabirimi değiştirilemez veya güncelleştirilemez. 

Bilgi noktası modunu etkinleştirmek için bkz. [Windows 10 ve üzeri Için bilgi noktası ayarları](../configuration/kiosk-settings.md).

Windows 10 ve üzeri için geçerlidir, Windows holographic for Business

#### <a name="apis-to-use-3rd-party-certification-authorities----2184013---"></a>3\. taraf sertifika yetkililerini kullanmak için API 'Ler <!-- 2184013 -->
Bu güncelleştirmede, üçüncü taraf sertifika yetkililerinin Intune ve SCEP ile tümleşmesini sağlayan bir Java API 'SI vardır. Ardından, kullanıcılar SCEP sertifikasını bir profile ekleyebilir ve MDM 'yi kullanarak cihazlara uygulayabilir.

Intune Şu anda [Active Directory Sertifika Hizmetleri kullanan SCEP isteklerini](../protect/certificates-scep-configure.md)destekler.

#### <a name="toggle-to-show-or-not-show-the-end-session-button-on-a-kiosk-browser----2455253---"></a>Bilgi noktası tarayıcısında oturumu sonlandır düğmesini göstermek veya göstermek için değiştirin <!-- 2455253 -->
Artık bilgi noktası tarayıcılarının oturumu Bitir düğmesini gösterip göstermediğini yapılandırabilirsiniz. Denetimi **cihaz yapılandırması** > **bilgi noktası (Önizleme)**  > **bilgi noktası Web tarayıcısında**görebilirsiniz. Açıksa, bir Kullanıcı düğmeye tıkladığında, uygulamanın oturumu sonlandırmasına onay ister. Onaylanırsa, tarayıcı tüm tarama verilerini temizler ve varsayılan URL 'ye geri gider.

#### <a name="create-an-esim-cellular-configuration-profile----2564077---"></a>Esım hücresel yapılandırma profili oluşturma <!-- 2564077 -->
**Cihaz yapılandırması**' nda bir esım hücresel profili oluşturabilirsiniz. Cep telefonu operatörünüz tarafından sunulan hücresel etkinleştirme kodlarını içeren bir dosyayı içeri aktarabilirsiniz. Daha sonra bu profilleri, Surface Pro LTE ve diğer esım özellikli cihazlar gibi esım LTE etkin Windows 10 cihazlarınıza dağıtabilirsiniz.

[Cihazlarınızın esım profillerini destekliyor](https://support.microsoft.com/help/4020763/windows-10-use-esim-for-cellular-data)olup olmadığını denetleyin.

Windows 10 ve üzeri için geçerlidir.

#### <a name="select-device-categories-by-using-the-access-work-or-school-settings----1058963-eenotready---"></a>Erişim Iş veya okul ayarlarını kullanarak cihaz kategorilerini seçme <!-- 1058963 eenotready --> 
[Cihaz grubu eşlemeyi](../enrollment/device-group-mapping.md)etkinleştirdiyseniz, Windows 10 ' daki kullanıcılardan, **Ayarlar** > **Hesap** > **Access Work veya okuldaki** **Bağlan** düğmesine kaydolduktan sonra bir cihaz kategorisi seçmesi istenir. 

#### <a name="use-samaccountname-as-the-account-username-for-email-profiles----1500307---"></a>E-posta profilleri için hesap Kullanıcı adı olarak sAMAccountName kullanın <!-- 1500307 -->
Android, iOS ve Windows 10 için e-posta profillerinin hesap Kullanıcı adı olarak şirket içi **sAMAccountName** öğesini kullanabilirsiniz. Etki alanını, Azure Active Directory (Azure AD) `domain` veya `ntdomain` özniteliğinden da alabilirsiniz. Veya özel bir statik etki alanı girin.

Bu özelliği kullanmak için şirket içi Active Directory ortamınızdan `sAMAccountName` özniteliğini Azure AD 'ye eşitlemeniz gerekir.

[Android](../configuration/email-settings-android.md), [iOS](../configuration/email-settings-ios.md), [Windows 10 ve üzeri](../configuration/email-settings-windows-10.md) için geçerlidir

#### <a name="see-device-configuration-profiles-in-conflict----1556983---"></a>Bkz. çakışan cihaz yapılandırma profilleri <!-- 1556983 -->
**Cihaz yapılandırmasında**, var olan profillerin bir listesi gösterilir. Bu güncelleştirmeyle, çakışma olan profillerle ilgili ayrıntılar sağlayan yeni bir sütun eklenir. Çakışmaya neden olan ayarı ve profili görmek için çakışan bir satır seçebilirsiniz. 

[Yapılandırma profillerini yönetme](../configuration/device-profile-monitor.md#view-conflicts)hakkında daha fazla bilgi.

#### <a name="new-status-for-devices-in-device-compliance----2308882---"></a>Cihaz uyumluluğuyla cihazların yeni durumu <!-- 2308882 -->
**Cihaz uyumluluğu** > **ilkeler** > bir ilke > **genel bakış**' a bir ilke seçerek aşağıdaki yeni durumlar eklenmiştir:
- Baarı
- error
- Uzantıları
- Yayınlan
- uygun değil, farklı bir platformun cihaz sayısını gösteren bir görüntü de gösteriliyor. Örneğin, bir iOS profiline bakıyorsanız, yeni kutucuk bu profile atanan iOS olmayan cihazların sayısını gösterir. Bkz. [cihaz uyumluluk ilkeleri](../protect/compliance-policy-monitor.md#view-status-of-device-policies).

#### <a name="device-compliance-supports-3rd-party-anti-virus-solutions----2325484---"></a>Cihaz uyumluluğu üçüncü taraf anti-virüs çözümlerini destekler <!-- 2325484 -->
Cihaz uyumluluk ilkesi oluşturduğunuzda (**cihaz uyumluluk** > **ilkeleri** > **Ilke oluştur** > **platformu: Windows 10 ve üzeri** > **ayarları** > **sistem güvenliği**) Yeni **[cihaz güvenlik](../protect/compliance-policy-create-windows.md)** seçenekleridir: 
- **Virüsten koruma**: **gerekli**olarak ayarlandığında, Windows Güvenlik Merkezi ile kaydedilen ve Symantec ve Windows Defender gibi virüsten koruma çözümlerini kullanarak uyumluluğu kontrol edebilirsiniz. 
- **Casus yazılımdan koruma**: **gerekli**olarak ayarlandığında, Windows Güvenlik Merkezi ile kaydedilen ve Symantec ve Windows Defender gibi casus yazılımdan koruma çözümlerini kullanarak uyumluluğu kontrol edebilirsiniz. 

Uygulama hedefi: Windows 10 ve üzeri 

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="automatically-mark-android-devices-enrolled-by-using-samsung-knox-mobile-enrollment-as-corporate----2404851---"></a>Samsung KNOX mobil kaydını "Şirket" olarak kullanarak kaydedilen Android cihazları otomatik olarak işaretleyin. <!-- 2404851 -->
Varsayılan olarak, Samsung KNOX mobil kayıt kullanılarak kaydedilen Android cihazları artık **cihaz sahipliği**kapsamında **Şirket** olarak işaretlenir. Knox mobil kaydı kullanarak kayıt yapmadan önce ıMEı veya seri numaralarını kullanarak şirket cihazlarını el ile belirlemeniz gerekmez.

#### <a name="devices-without-profiles-column-in-the-list-of-enrollment-program-tokens----1853904---"></a>Kayıt programı belirteçleri listesinde Profilsiz olmayan cihazlar sütunu <!-- 1853904 -->
Kayıt programı belirteçleri listesinde, profil atanmayan cihaz sayısını gösteren yeni bir sütun vardır. Bu, yöneticilerin kullanıcılara teslim etmeden önce profilleri bu cihazlara atamasını sağlar. Yeni sütunu görmek için **cihaz kaydı** > **Apple kayıt** > **kayıt programı belirteçleri**' ne gidin.

### <a name="device-management"></a>Cihaz yönetimi

#### <a name="bulk-delete-devices-on-devices-blade----1793693---"></a>Cihazlarda cihazları toplu silme dikey penceresi <!-- 1793693 -->
Artık cihazlar dikey penceresinde birden çok cihazı tek seferde silebilirsiniz. **Cihazlar** > **tüm cihazlar** ' ı seçin > silmek Istediğiniz cihazları seçin > **silin**. Silinemeyen cihazlarda bir uyarı görüntülenir.

#### <a name="google-name-changes-for-android-for-work-and-play-for-work---842873---"></a>Android for Work için Google ad değişiklikleri ve Iş için Yürüt <!--842873 -->
Intune, "Android for Work" terminolojisini Google marka değişikliklerini yansıtacak şekilde güncelleştirmiştir. "Android for Work" ve "for Work" terimleri artık kullanılmıyor. Bağlama göre farklı terminoloji kullanılır:
- "Android kurumsal", genel modern Android yönetim yığınını ifade eder.
- "İş profili" veya "Profil sahibi" iş profilleriyle yönetilen KCG cihazlarını ifade eder.
- "Managed Google Play", Google App Store 'a başvurur.

#### <a name="rules-for-removing-devices----1609459---"></a>Cihazları kaldırma kuralları <!-- 1609459 -->
Ayarladığınız bir dizi gün boyunca Denetlenmemiş cihazları otomatik olarak kaldırmanıza olanak sağlayan yeni kurallar mevcuttur. Yeni kuralı görmek için **Intune** bölmesine gidin, **cihazlar**' ı seçin ve **cihaz temizleme kuralları**' nı seçin.

#### <a name="corporate-owned-single-use-support-for-android-devices----1630973---"></a>Android cihazları için şirkete ait, tek kullanım desteği <!-- 1630973 -->

Intune artık yüksek oranda yönetilen, kilitlenmiş, bilgi noktası stili Android cihazları desteklemektedir. Bu, yöneticilerin bir cihazın kullanımını tek bir uygulamayla veya küçük bir uygulama kümesiyle daha fazla kilitlemesine olanak sağlar ve kullanıcıların diğer uygulamaları ve cihazdaki diğer işlemleri gerçekleştirmesini engeller. Android bilgi noktası ayarlamak için Intune > **cihaz kaydı** > **Android kayıt** > **bilgi noktası ve görev cihaz**kayıtları ' na gidin. Daha fazla bilgi için bkz. [Android kurumsal bilgi noktası cihazlarının kaydını ayarlama](../enrollment/android-kiosk-enroll.md).

#### <a name="per-row-review-of-duplicate-corporate-device-identifiers-uploaded----2203794--"></a>Yinelenen kurumsal cihaz tanımlayıcılarının satır başına incelenmesi karşıya yüklendi <!-- 2203794-->
Şirket kimlikleri karşıya yüklenirken, Intune artık yinelenen bir liste sağlar ve mevcut bilgileri değiştirme veya tutma seçeneğini sunar. **Cihaz kaydı**' nı seçtikten sonra yinelenen bir değer varsa rapor görünür  > **tanımlayıcı Ekle** **@no__t.** 

#### <a name="manually-add-corporate-device-identifiers----2203803---"></a>Kurumsal cihaz tanımlayıcılarını el ile ekleme <!-- 2203803 -->
Artık kurumsal cihaz kimliklerini el ile ekleyebilirsiniz. **Cihaz kaydı** > **şirket cihaz tanımlayıcıları** > **Ekle**' yi seçin. 


<!-- ########################## -->
## <a name="june-2018"></a>Haziran 2018

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="microsoft-edge-mobile-support-for-intune-app-protection-policies----1817882---"></a>Intune uygulama koruma ilkeleri için Microsoft Edge mobil desteği <!-- 1817882 -->
Mobil cihazlar için Microsoft Edge tarayıcısı artık Intune 'da tanımlanan uygulama koruma ilkelerini desteklemektedir.

#### <a name="retrieve-the-associated-app-user-model-id-aumid-for-microsoft-store-for-business-apps-in-kiosk-mode----1560077----"></a>Iş kolu uygulamaları için Microsoft Store bilgi noktası modunda ilişkili uygulama kullanıcı modeli KIMLIĞINI (AUMıD) alma <!-- 1560077 ! -->
Intune artık bilgi noktası profilinin daha iyi yapılandırılmasını sağlamak üzere Microsoft Store for Business (WSfB) uygulamaları için uygulama kullanıcı modeli kimliklerini (AUMIDs) alabilir.

Iş uygulamaları için Microsoft Store hakkında daha fazla bilgi için bkz. [iş için Microsoft Store uygulamaları yönetme](../apps/windows-store-for-business.md).

#### <a name="new-company-portal-branding-page----1916370---"></a>Yeni Şirket Portalı marka sayfası <!-- 1916370 -->
Şirket Portalı marka sayfası yeni bir düzen, ileti ve araç ipuçları içerir.


### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="pradeo---new-mobile-threat-defense-partner----1169249---"></a>Pradeo-yeni Mobile Threat Defense iş ortağı <!-- 1169249 -->
Microsoft Intune ile tümleşen bir mobil tehdit savunması çözümü olan Pradeo tarafından gerçekleştirilen risk değerlendirmesine dayalı koşullu erişimi kullanarak mobil cihaz erişimini kontrol edebilirsiniz.

#### <a name="use-fips-mode-with-the-ndes-certificate-connector----1333688---"></a>NDES sertifika Bağlayıcısı ile FIPS modunu kullanma <!-- 1333688 -->
Federal bilgi Işleme standardı (FIPS) modu etkin olan bir bilgisayara NDES sertifika bağlayıcısını yüklediğinizde, sertifika verme ve iptal etme işlemi beklendiği gibi çalışmaz. Bu güncelleştirmeyle, NDES desteği NDES sertifika Bağlayıcısı 'nda bulunur. 

Bu güncelleştirme ayrıca şunları içerir:

- NDES sertifika Bağlayıcısı, Windows Server 2016 ve Windows Server 2012 R2 'ye otomatik olarak eklenen .NET 4,5 Framework gerektirir. Daha önce, .NET 3,5 Framework gerekli en düşük sürümdür.
- TLS 1,2 desteği NDES sertifika Bağlayıcısı 'na dahildir. Bu nedenle NDES sertifika Bağlayıcısı yüklü sunucu TLS 1,2 ' yi destekliyorsa, TLS 1,2 kullanılır. Sunucu TLS 1,2 ' i desteklemiyorsa TLS 1,1 kullanılır. Şu anda, cihazlar ve sunucu arasında kimlik doğrulaması için TLS 1,1 kullanılır.

Daha fazla bilgi için bkz. [SCEP sertifikalarını yapılandırma ve kullanma](../protect/certificates-scep-configure.md) ve [PKCS sertifikalarını yapılandırma ve kullanma](../protect/certficates-pfx-configure.md).

#### <a name="support-for-palo-alto-networks-globalprotect-vpn-profiles----1333680----"></a>Palo Alto ağları için destek GlobalProtect VPN profilleri <!-- 1333680 ! -->
Bu güncelleştirmeyle, Intune 'da VPN profilleri için bir VPN bağlantı türü olarak GlobalProtect, Palo Alto ağlarını seçebilirsiniz (**cihaz yapılandırma** > **profilleri** > **profil oluşturma** > **profil türü** > **VPN** ). Bu sürümde, aşağıdaki platformlar desteklenir: 

- iOS
- Windows 10

#### <a name="additions-to-local-device-security-options-settings----1403702---"></a>Yerel cihaz güvenlik seçenekleri ayarlarına eklemeler <!-- 1403702 -->
Artık Windows 10 cihazları için ek yerel cihaz güvenlik seçenekleri ayarlarını yapılandırabilirsiniz. Microsoft ağ Istemcisi, Microsoft ağ sunucusu, ağ erişimi ve güvenlik ve etkileşimli oturum açma alanlarında ek ayarlar bulunur. Windows 10 cihaz yapılandırma ilkesi oluştururken Endpoint Protection kategorisinde bu ayarları bulun.

#### <a name="enable-kiosk-mode-on-windows-10-devices----1560072----"></a>Windows 10 cihazlarında bilgi noktası modunu etkinleştirme <!-- 1560072 ! -->
Windows 10 cihazlarında bir yapılandırma profili oluşturabilir ve bilgi noktası modunu etkinleştirebilirsiniz (**cihaz yapılandırma** > **profilleri** > **Profil oluştur** > **Windows 10** > **cihaz kısıtlamaları** >  **Bilgi noktası**). Bu güncelleştirmede **bilgi noktası (Önizleme)** ayarı **bilgi noktası (eski)** olarak yeniden adlandırıldı. **Bilgi noktası (eski)** artık kullanım için önerilmez, ancak Temmuz güncelleştirmesine kadar çalışmaya devam edecektir. **Bilgi noktası (eski)** , WINDOWS 10 RS4 ve sonraki sürümlerde kiosks 'i yapılandırma ayarlarını Içerecek yeni **bilgi noktası** profili türü (**profil oluşturma** > **Windows 10** > **bilgi noktası (Önizleme)** ) ile değiştirilmiştir.

Windows 10 ve üzeri için geçerlidir.

#### <a name="device-profile-graphical-user-chart-is-back----2160133---"></a>Cihaz profili Grafik Kullanıcı Grafiği geri <!-- 2160133 -->
Cihaz profili grafik grafiğinde gösterilen sayısal sayıları geliştirirken (**cihaz yapılandırma** > **profilleri** > var olan bir profili seçin > **genel bakış**), Grafik Kullanıcı Grafiği geçici olarak kaldırılmıştır.

Bu güncelleştirmeyle, grafik kullanıcı grafiği geri yüklenir ve Azure portal gösterilir.

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="support-for-windows-autopilot-enrollment-without-user-authentication----1165118---"></a>Kullanıcı kimlik doğrulaması olmadan Windows Autopilot kaydı desteği <!-- 1165118 -->
Intune artık Kullanıcı kimlik doğrulaması olmadan Windows Autopilot kaydını destekliyor. Bu, "Autopilot dağıtım modundaki" Windows Autopilot dağıtım profilinde "kendi kendine dağıtım" olarak ayarlanan yeni bir seçenektir.  Cihazın Windows 10 Insider Preview derlemesi 17672 veya üstünü çalıştırması ve bu kayıt türünü başarıyla tamamlaması için bir TPM 2,0 yongasına sahip olması gerekir. Kullanıcı kimlik doğrulaması gerekli olmadığından, bu seçeneği yalnızca fiziksel denetim sahibi olduğunuz cihazlara atamanız gerekir.

#### <a name="new-languageregion-setting-when-configuring-oobe-for-autopilot----1821766---"></a>Autopilot için OOBE yapılandırılırken yeni dil/bölge ayarı <!-- 1821766 -->
Hazır olmayan deneyim sırasında Autopilot profillerinin dilini ve bölgesini ayarlamak için yeni bir yapılandırma ayarı vardır. Yeni ayarı görmek için **cihaz kaydı**@no__t seçin-1**Windows kaydı** > **dağıtım profilleri** > **profil oluşturma** > **dağıtım modu** = **kendi kendine dağıtma** > 1 **Varsayılanlar yapılandırıldı**.

#### <a name="new-setting-for-configuring-device-keyboard----1821768---"></a>Cihaz klavyesini yapılandırmaya yönelik yeni ayar <!-- 1821768 -->
Kullanıma hazır deneyim sırasında Autopilot profillerinin klavyesini yapılandırmak için yeni bir ayar kullanılabilecek. Yeni ayarı görmek için **cihaz kaydı**@no__t seçin-1**Windows kaydı** > **dağıtım profilleri** > **profil oluşturma** > **dağıtım modu** = **kendi kendine dağıtma** > 1 **Varsayılanlar yapılandırıldı**.

#### <a name="autopilot-profiles-moving-to-group-targeting----1877935---"></a>Autopilot profilleri grup hedeflemeye taşınıyor <!-- 1877935 -->
AutoPilot dağıtım profilleri, AutoPilot cihazları içeren Azure AD gruplarına atanabilir.

### <a name="device-management"></a>Cihaz yönetimi

#### <a name="set-compliance-by-device-location----851881----"></a>Cihaz konumuna göre uyumluluğu ayarla <!-- 851881 ! -->
Bazı durumlarda, şirket kaynaklarına erişimi bir ağ bağlantısıyla tanımlanan belirli bir konumla kısıtlamak isteyebilirsiniz. Artık cihazın IP adresine bağlı olarak bir uyumluluk ilkesi (**cihaz uyumluluk** > **konum**) oluşturabilirsiniz. Cihaz IP aralığının dışına taşınırsa, cihaz şirket kaynaklarına erişemez.

İçin geçerlidir: güncelleştirilmiş Şirket Portalı uygulamayla Android cihazlar 6,0 ve üzeri

#### <a name="prevent-consumer-apps-and-experiences-on-windows-10-enterprise-rs4-autopilot-devices---1621980---"></a>Windows 10 Enterprise RS4 Autopilot cihazlarında tüketici uygulamalarını ve deneyimlerini engelleyin<!-- 1621980 -->
Windows 10 Enterprise RS4 AutoPilot cihazlarınızda tüketici uygulamalarının ve deneyimlerinin yüklenmesini engelleyebileceksiniz. Bu özelliği görmek için **ıntune** > **cihaz yapılandırması** > **profiller** > **profil oluşturma** > **Platform** = **Windows 10 veya üzeri**1**profil türü**@no__ t-13**cihaz kısıtlamaları**5 7**Windows spot**9**Tüketici özelliklerini** **yapılandırın**. 

#### <a name="uninstall-the-latest-from-windows-10-software-updates----1732948---"></a>En son Windows 10 yazılım güncelleştirmelerinden kaldırma <!-- 1732948 -->
Windows 10 makinelerinizde bir sorun bulmalı, en son özellik güncelleştirmesini veya en son kalite güncelleştirmesini kaldırmayı (geri alma) seçebilirsiniz. Bir özellik veya kalite güncelleştirmesini kaldırmak yalnızca cihazın açık olduğu hizmet kanalı için kullanılabilir. Kaldırma, Windows 10 makinelerinizde önceki güncelleştirmeyi geri yüklemek için bir ilke tetikler. Özellikle özellik güncelleştirmeleri için, en son sürümü kaldırma özelliğinin uygulanabileceğini 2-60 gün süreyle sınırlayabilirsiniz. Yazılım güncelleştirme kaldırma seçeneklerini ayarlamak için Azure portal içindeki **Microsoft Intune** dikey penceresinden **yazılım güncelleştirmeleri** ' ni seçin. Ardından, **yazılım güncelleştirmeleri** dikey penceresinden **Windows 10 güncelleştirme halkaları** ' nı seçin. Daha sonra **genel bakış** bölümünden **Kaldır** seçeneğini belirleyebilirsiniz.

#### <a name="search-all-devices-for-imei-and-serial-number----1793685---"></a>Tüm cihazları ıMEı ve seri numarasına göre ara <!-- 1793685 -->
Artık tüm cihazlar dikey penceresinde ıMEı ve seri numaralarını arayabilirsiniz (e-posta, UPN, cihaz adı ve yönetim adı hala kullanılabilir). Intune 'da, **cihazlar** > **tüm cihazlar** ' ı seçin > Arama kutusuna aramanızı girin.

#### <a name="management-name-field-will-be-editable----1875989---"></a>Yönetim adı alanı düzenlenebilir olacak <!-- 1875989 -->
Artık bir cihazın **Özellikler** dikey penceresinde yönetim adı alanını düzenleyebilirsiniz. Bu alanı düzenlemek için **cihazlar** > **tüm cihazlar** ' ı seçin > Cihaz > **özelliklerini**seçin. Bir cihazı benzersiz bir şekilde tanımlamak için yönetim adı alanını kullanabilirsiniz.

#### <a name="new-all-devices-filter-device-category----1878520---"></a>Yeni tüm cihazlar filtresi: cihaz kategorisi <!-- 1878520 -->
Artık **tüm cihazlar** listesini cihaz kategorisine göre filtreleyebilirsiniz. Bunu yapmak için **cihazlar** > **tüm cihazlar** > **filtre** > **cihaz kategorisi**' ni seçin.

#### <a name="use-teamviewer-to-screen-share-ios-and-macos-devices----1985547---"></a>İOS ve MacOS cihazları paylaşmak için TeamViewer kullanma <!-- 1985547 -->
Yöneticiler artık [TeamViewer](../remote-actions/teamviewer-support.md)'a bağlanabilir ve IOS ve MacOS cihazlarıyla bir ekran paylaşım oturumu başlatabilir. iPhone, iPad ve macOS kullanıcıları, ekranlarını diğer masaüstü veya mobil cihazla canlı olarak paylaşabilir. 

#### <a name="multiple-exchange-connector-support----2070451---"></a>Birden çok Exchange Connector desteği <!-- 2070451 -->
Kiracı başına bir Microsoft Intune Exchange Connector artık sınırlandırılırsınız. Intune, Intune koşullu erişimini birden çok şirket içi Exchange kuruluşu ile ayarlayabilmeniz için artık birden çok Exchange Bağlayıcısı desteklemektedir.

Intune şirket içi Exchange bağlayıcısıyla, cihazın Intune 'a kaydedilip kaydedilmediğini ve Intune cihaz uyumluluk ilkeleriyle uyumlu olup olmadığına bağlı olarak şirket içi Exchange posta kutularına cihaz erişimini yönetebilirsiniz. Bir bağlayıcı kurmak için, Intune şirket içi Exchange bağlayıcısını Azure portal indirip Exchange kuruluşunuzdaki bir sunucuya yüklersiniz. Microsoft Intune panosunda **Şirket içi erişim**' i seçin ve ardından **Kurulum**altında **Exchange ActiveSync Bağlayıcısı**' nı seçin. Şirket içi Exchange bağlayıcısını indirin ve Exchange kuruluşunuzdaki bir sunucuya yükleyin. Artık kiracı başına bir Exchange bağlayıcısıyla sınırlı kaldığınıza göre, ek Exchange kuruluşlarınız varsa, her ek Exchange kuruluşu için bir bağlayıcı indirmek ve yüklemek üzere bu süreci takip edebilirsiniz.

#### <a name="new-device-hardware-detail-ccid----2156657---"></a>Yeni cihaz donanım ayrıntısı: CCıD <!-- 2156657 -->
Yonga kartı arabirim aygıtı (CCıD) bilgileri artık her bir cihaza dahildir. Bunu görmek için **cihazlar** > **tüm cihazlar** ' ı seçin > cihaz > **donanımı**seçin > **ağ ayrıntıları**altında denetle >

#### <a name="assign-all-users-and-all-devices-as-scope-groups----2196803---"></a>Tüm kullanıcıları ve tüm cihazları kapsam grupları olarak ata <!-- 2196803 -->
Artık tüm kullanıcıları, tüm cihazları ve tüm kullanıcıları ve kapsam gruplarındaki tüm cihazları atayabilirsiniz. Bunu yapmak için, **Intune rollerini** > **tüm roller** > **ilke ve Profil Yöneticisi** > **atamaları** seçin > atama > **kapsam (gruplar)** seçin.

#### <a name="udid-information-now-included-for-ios-and-macos-devices----2219806---"></a>İOS ve macOS cihazlarına artık UıDıD bilgileri eklendi <!-- 2219806 -->
İOS ve macOS cihazları için benzersiz cihaz tanımlayıcısı 'nı (UDıD) görmek için **cihazlar** >  ' e gidin **> cihaz >** **donanımı**seçin. UıDıD yalnızca şirket cihazları için kullanılabilir ( **cihazlar** >  ' in**tüm cihazlar** > bir cihaz > **Özellikler** > **cihaz sahipliği**) seçin.

### <a name="intune-apps"></a>Intune uygulamaları

#### <a name="improved-troubleshooting-for-app-installation----928990---"></a>Uygulama yüklemesi için geliştirilmiş sorun giderme <!-- 928990 -->
MDM ile yönetilen cihazlarda Microsoft Intune, bazen uygulama yüklemeleri başarısız olabilir. Bu uygulama başarısız olduğunda hata nedenini anlamak veya sorunu gidermek zor olabilir. Uygulama sorun giderme özelliklerimizin genel önizlemesine gönderim yapıyoruz. **Yönetilen uygulamalar**adlı her bir cihaz altında yeni bir düğüm fark edeceksiniz. Bu, Intune MDM aracılığıyla teslim edilen uygulamaları listeler. Düğüm içinde uygulama yüklemesi durumlarının listesini görürsünüz. Tek bir uygulamayı seçerseniz, bu belirli uygulama için sorun giderme görünümünü görürsünüz. Sorun giderme görünümünde, uygulamanın, uygulamanın ne zaman oluşturulduğu, değiştirildiği, hedeflediği ve bir cihaza teslim edildiği gibi uçtan uca yaşam döngüsünü görürsünüz. Ayrıca, uygulama yüklemesi başarılı olmazsa hata kodu ve hatanın nedeni ile ilgili yararlı bir ileti gösterilir. 

#### <a name="intune-app-protection-policies-and-microsoft-edge----1818968---"></a>Intune uygulama koruma ilkeleri ve Microsoft Edge <!-- 1818968 -->
Mobil cihazlar (iOS ve Android) için Microsoft Edge tarayıcısı artık Microsoft Intune uygulama koruma ilkelerini desteklemektedir. Microsoft Edge uygulamasındaki kurumsal Azure AD hesaplarıyla oturum açan iOS ve Android cihazlarının kullanıcıları, Intune tarafından korunur. İOS cihazlarında, **Web içeriği için yönetilen tarayıcı gerektir** ilkesi, kullanıcıların yönetildiğinde Microsoft Edge 'de bağlantıları açmasına olanak sağlar.

<!-- ########################## -->
## <a name="may-2018"></a>Mayıs 2018

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="configuring-your-app-protection-policies----2144597-part-2---"></a>Uygulama koruma ilkelerinizi yapılandırma <!-- 2144597 Part 2 -->

Azure portal, Intune Uygulama Koruması hizmeti dikey penceresine gitmek yerine artık Intune 'a gitmeniz yeterlidir. Artık Intune 'da uygulama koruma ilkeleri için yalnızca bir konum vardır. Tüm uygulama koruma ilkelerinizin, **Uygulama koruma ilkeleri**altında Intune 'da **mobil uygulama** dikey penceresinde olduğunu unutmayın. Bu tümleştirme, bulut yönetimi yönetimini basitleştirmeye yardımcı olur. Tüm uygulama koruma ilkelerinin zaten Intune 'da olduğunu ve daha önce yapılandırdığınız ilkelerden herhangi birini değiştirebileceğinizi unutmayın. Intune uygulama Ilkesi koruması (uygulama) ve koşullu erişim (CA) ilkeleri artık **Microsoft Intune** dikey penceresindeki **Yönet** bölümünde veya Içindeki **güvenlik** bölümünde bulunan **koşullu erişim**aşamasındadır.  **Azure Active Directory** dikey pencere. Koşullu erişim ilkelerini değiştirme hakkında daha fazla bilgi için bkz. [Azure Active Directory Koşullu erişim](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal). Daha fazla bilgi için bkz. [Uygulama koruma Ilkeleri nelerdir?](../apps/app-protection-policy.md)

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="require-installation-of-policies-apps-certificate-and-network-profiles----1553555---"></a>İlkelerin, uygulamaların, sertifikaların ve ağ profillerinin yüklenmesini gerektir <!-- 1553555 -->
Yöneticiler, AutoPilot cihazlarının sağlanması sırasında Intune ilke, uygulama ve sertifika ve ağ profilleri yükleene kadar son kullanıcıların Windows 10 RS4 masaüstüne erişmesini engelleyebilir. Daha fazla bilgi için bkz. [kayıt durumu sayfası ayarlama](../enrollment/windows-enrollment-status.md).

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="samsung-knox-mobile-enrollment-support---1112863--"></a>Samsung KNOX mobil kayıt desteği <!--1112863-->
Intune 'U Samsung KNOX mobil kaydı (KME) ile birlikte kullanırken, şirkete ait çok sayıda Android cihazı kaydedebilirsiniz. WiFi veya hücresel ağlardaki kullanıcılar cihazlarını ilk kez açtığında yalnızca birkaç dokunmasıyla kayıt yapabilir. Knox dağıtım uygulamasını kullanırken, cihazlar Bluetooth veya NFC kullanılarak kaydedilebilir. Daha fazla bilgi için bkz. [Samsung 's Knox mobil kaydı kullanarak Android cihazlarını otomatik olarak kaydetme](../enrollment/android-samsung-knox-mobile-enroll.md).

### <a name="monitor-and-troubleshoot"></a>İzleme ve sorun giderme 

#### <a name="requesting-help-in-the-company-portal-for-windows-10----1874137---"></a>Windows 10 için Şirket Portalı yardım isteme <!-- 1874137 -->
Windows 10 için Şirket Portalı artık Kullanıcı iş akışını başlattığınızda bir sorunla ilgili yardım almak için uygulama günlüklerini doğrudan Microsoft 'a gönderecektir. Bu, Microsoft 'a yükseltilen sorunları gidermeye ve çözmeye daha kolay hale gelir.

<!-- ########################## -->
## <a name="april-2018"></a>Nisan 2018

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="passcode-support-for-mam-pin-on-android---1438086---"></a>Android 'de MAM PIN için geçiş kodu desteği<!-- 1438086 -->

Intune yöneticileri, bir sayısal MAM PIN 'ı yerine bir geçiş kodu zorlamak için uygulama başlatma gereksinimi ayarlayabilir. Yapılandırıldıysa, kullanıcının MAM özellikli uygulamalara erişim almadan önce istendiğinde bir geçiş kodu ayarlaması ve kullanması gerekir. Bir geçiş kodu, en az bir özel karakter veya büyük/küçük harflerden oluşan sayısal bir PIN olarak tanımlanır. Intune, geçiş kodunu mevcut sayısal PIN 'e benzer bir şekilde destekler... Yönetici Konsolu aracılığıyla karakter ve sıralara yineleme sağlayan minimum uzunluğu ayarlayabiliyor. Bu özellik Android üzerinde Şirket Portalı en son sürümünü gerektirir. Bu özellik zaten iOS için kullanılabilir.

#### <a name="line-of-business-lob-app-support-for-macos----1473977---"></a>MacOS için iş kolu (LOB) uygulama desteği <!-- 1473977 -->
Microsoft Intune, macOS LOB uygulamalarını Azure portal yüklemesine olanak sağlar. Bir macOS LOB uygulamasını, GitHub 'da bulunan araç tarafından önceden işlendikten sonra Intune 'a ekleyebileceksiniz. Azure portal **Intune** dikey penceresinde **istemci uygulamalar** ' ı seçin. **İstemci uygulamaları** dikey penceresinde **uygulamalar** > **Ekle**' yi seçin. **Uygulama Ekle** dikey penceresinde, **iş kolu uygulaması**' nı seçin. 

#### <a name="built-in-all-users-and-all-devices-group-for-android-enterprise-work-profile-app-assignment----1813073---"></a>Android kurumsal iş profili uygulama ataması için yerleşik tüm kullanıcılar ve tüm cihazlar grubu <!-- 1813073 -->
Android kurumsal iş profili uygulama ataması için yerleşik **tüm kullanıcılar** ve **tüm cihazlar** gruplarından yararlanabilirsiniz. Daha fazla bilgi için, bkz. [Microsoft Intune uygulama atamalarını dahil etme ve hariç tutma](../apps/apps-inc-exl-assignments.md).

#### <a name="intune-will-reinstall-required-apps-that-are-uninstalled-by-users----1947010---"></a>Intune, kullanıcılar tarafından kaldırılan gerekli uygulamaları yeniden yükler <!-- 1947010 -->
Son Kullanıcı gerekli bir uygulamayı kaldırırsa, Intune 7 günlük yeniden değerlendirme döngüsünü beklemek yerine uygulamayı 24 saat içinde otomatik olarak yeniden yükler.

#### <a name="update-where-to-configure-your-app-protection-policies----2144597---"></a>Uygulama koruma ilkelerinizin nerede yapılandırılacağını güncelleştirme <!-- 2144597 -->

Microsoft Intune hizmeti içindeki Azure portal, **Intune uygulama koruması** hizmeti dikey penceresinden **mobil uygulama** dikey penceresine geçici olarak yönlendiriyoruz. Tüm uygulama koruma ilkelerinizin zaten Intune 'da uygulama yapılandırması altındaki **mobil uygulama** dikey penceresinde bulunduğunu unutmayın. Intune Uygulama Koruması gitmek yerine yalnızca Intune 'a gidebilirsiniz. Intune 'da uygulama koruma ilkeleri için yalnızca bir konum olduğundan, 2018 Nisan 'da yeniden yönlendirmeyi durduracak ve **Intune uygulama koruması** hizmeti dikey penceresini tamamen kaldıracağız. 

**Bu, beni nasıl etkiler?**
Bu değişiklik hem Intune tek başına müşterilerini hem de karma (Intune Configuration Manager) müşterilerini etkileyecektir. Bu tümleştirme, bulut yönetimi yönetiminizi basitleştirmeye yardımcı olur.

**Bu değişikliğe hazırlanmak için ne yapmam gerekir?**
Lütfen **Intune** 'u **Intune uygulama koruması** hizmet dikey penceresi yerine sık kullanılan olarak etiketleyin ve Intune 'daki **Mobil** uygulama dikey penceresinde uygulama koruma ilkesi iş akışını bildiğiniz bir bilgi sahibi olduğunuzdan emin olun. Kısa bir süre boyunca yönlendiriyoruz ve sonra **Uygulama koruma** dikey penceresini kaldıracağız. Tüm uygulama koruma ilkelerinin zaten Intune 'da olduğunu ve koşullu erişim ilkelerinizin herhangi birini değiştirebileceğinizi unutmayın. Koşullu erişim ilkelerini değiştirme hakkında daha fazla bilgi için bkz. [Azure Active Directory Koşullu erişim](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal). Daha fazla bilgi için bkz. [Uygulama koruma Ilkeleri nelerdir?](../apps/app-protection-policy.md) 

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="device-profile-chart-and-status-list-show-all-devices-in-a-group----1449153---"></a>Cihaz profili grafiği ve durum listesi bir gruptaki tüm cihazları gösterir <!-- 1449153 -->
Bir cihaz profili (**cihaz yapılandırması** > **profilleri**) yapılandırdığınızda, iOS gibi cihaz profilini seçersiniz. Bu profili iOS cihazlarını ve iOS olmayan cihazları içeren bir gruba atarsınız. Grafik grafik sayısı, profilin iOS 'a *ve* iOS olmayan cihazlara uygulanacağını gösterir (**cihaz yapılandırma** > **profilleri** > var olan bir profili seçin > **genel bakış**). **Genel bakış** sekmesinde grafik grafik ' i seçtiğinizde, **cihaz durumu** gruptaki yalnızca iOS cihazları yerine tüm cihazları listeler. 

Bu güncelleştirmeyle, grafik grafik (**cihaz yapılandırma** > **profilleri** > var olan bir profili seçin > **genel bakış**) yalnızca belirli bir cihaz profilinin sayımını gösterir. Örneğin, yapılandırma cihaz profili iOS cihazları için geçerliyse, grafik yalnızca iOS cihazlarının sayısını listeler. Grafik grafiğin seçilmesi ve **cihaz durumunun** açılması yalnızca iOS cihazlarını listeler.

Bu güncelleştirme yapıldıkça, Grafik Kullanıcı Grafiği geçici olarak kaldırılır. 

#### <a name="always-on-vpn-for-windows-10---1333666---"></a>Windows 10 için her zaman VPN üzerinde <!--1333666 -->

Şu anda, [her zaman açık](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-auto-trigger-profile#always-on) , OMA-URI kullanılarak oluşturulan özel bir sanal özel ağ (VPN) profili kullanılarak Windows 10 cihazlarında kullanılabilir.

Bu güncelleştirmeyle, Yöneticiler Azure portal doğrudan Intune 'da Windows 10 VPN profilleri için her zaman açık ' i etkinleştirebilir. Her zaman VPN profilleri şu durumlarda otomatik olarak bağlanır:

- Kullanıcılar cihazlarında oturum açtığında
- Cihazdaki ağ değiştiğinde
- Cihazdaki ekran devre dışı bırakıldıktan sonra yeniden açılır

#### <a name="new-printer-settings-for-education-profiles----1308900---"></a>Eğitim profilleri için yeni yazıcı ayarları <!-- 1308900 -->

Eğitim profilleri için yeni ayarlar **Yazıcılar** kategorisi altında kullanılabilir: **Yazıcılar**, **varsayılan yazıcı**, **Yeni Yazıcı Ekle**.

#### <a name="show-caller-id-in-personal-profile---android-enterprise-work-profile---1098984---"></a>Kişisel profilde arayan KIMLIĞINI göster-Android kurumsal iş profili <!--1098984 -->
Bir cihazda kişisel bir profil kullanırken, son kullanıcılar iş kişağından arayan KIMLIĞI ayrıntılarını göremeyebilir. 

Bu güncelleştirmeyle, **Android Enterprise** > **cihaz kısıtlamalarında** > **iş profili ayarları**için yeni bir ayar vardır:
- Kişisel profilde iş kişisi arayan kimliğini görüntüle

Etkinleştirildiğinde (yapılandırılmadığında), iş iletişim çağıranu ayrıntıları kişisel profilde görüntülenir. Bloke edildiğinde, iş iletişim arayan numarası kişisel profilde gösterilmez. 

Uygulama hedefi: Android OS v 6.0 ve üzeri sürümlerde Android iş profili cihazları

#### <a name="new-windows-defender-credential-guard-settings-added-to-endpoint-protection-settings---1102252-----from-1802-and-1804--"></a>Endpoint Protection ayarlarına yeni Windows Defender Credential Guard ayarları eklendi <!--1102252 --><!--from 1802 and 1804-->

Bu güncelleştirmeyle, [Windows Defender Credential Guard](https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard) (**cihaz yapılandırma** > **profilleri** > **Endpoint Protection**) aşağıdaki ayarları içerir: 

- **Windows Defender Credential Guard**: kimlik bilgisi koruyucusunu sanallaştırma tabanlı güvenlik ile açar. Bu özelliği etkinleştirmek, güvenli önyükleme ve **sanallaştırma tabanlı güvenlik** **Ile platform güvenlik düzeyi** etkinleştirildiğinde kimlik bilgilerinin bir sonraki yeniden başlatmada korunmasını sağlar. Seçeneklere şunlar dahildir:
  - **Devre dışı**: Credential Guard daha önce **kilitleme olmadan etkin**olarak açıksa, Credential Guard 'ı uzaktan kapatır.

  - **UEFI kilidi Ile etkinleştirildi**: Credential Guard 'ın bir kayıt defteri anahtarı kullanılarak veya Grup İlkesi kullanılarak devre dışı bırakılamaz. Bu ayarı kullandıktan sonra Credential Guard 'ı devre dışı bırakmak için grup ilkesi "devre dışı" olarak ayarlamanız gerekir. Ardından, her bir bilgisayardan güvenlik işlevini, fiziksel olarak bulunan bir kullanıcıyla kaldırın. Bu adımlar, UEFı 'de kalıcı yapılandırmayı temizler. UEFı yapılandırması devam ettiği sürece, Credential Guard etkinleştirilir.

  - **Kilitleme olmadan etkinleştirildi**: Grup İlkesi kullanarak Credential Guard 'ın uzaktan devre dışı olmasına izin verir. Bu ayarı kullanan cihazların en az Windows 10 (sürüm 1511) çalıştırması gerekir.

Credential Guard yapılandırılırken aşağıdaki bağımlı teknolojiler otomatik olarak etkinleştirilir: 

- **Sanallaştırma tabanlı güvenliği (VBS) etkinleştir**: bir sonraki yeniden başlatmada sanallaştırma tabanlı GÜVENLIĞI (VBS) açar. Sanallaştırma tabanlı güvenlik, güvenlik hizmetleri için destek sağlamak üzere Windows Hiper Yöneticisi 'ni kullanır ve güvenli önyükleme gerektirir.
- **Doğrudan bellek erişimi (DMA) Ile güvenli önyükleme**: güvenli önyükleme ve doğrudan bellek ERIŞIMI ile vbs 'yi açar. DMA koruması, donanım desteği gerektirir ve yalnızca düzgün yapılandırılmış cihazlarda etkindir. 

#### <a name="use-a-custom-subject-name-on-scep-certificate----2064190---"></a>SCEP sertifikasında özel bir konu adı kullanın <!-- 2064190 -->
Ortak adı **OnPremisesSamAccountName** bir SCEP sertifika profilinde özel bir konu içinde kullanabilirsiniz. Örneğin, `CN={OnPremisesSamAccountName})` ' ı kullanabilirsiniz.

#### <a name="block-camera-and-screen-captures-on-android-enterprise-work-profiles----1098977---"></a>Android kurumsal iş profillerindeki kamera ve ekran yakalamaları engelleme <!-- 1098977 -->
Android cihazları için cihaz kısıtlamalarını yapılandırırken engellenecek iki yeni özellik mevcuttur: 
- Kamera: cihazdaki tüm kameralara erişimi engeller
- Ekran yakalama: ekran yakalamayı engeller ve ayrıca içeriğin güvenli bir video çıkışına sahip olmayan görüntü cihazlarında gösterilmesini önler

Android kurumsal iş profilleri için geçerlidir.

#### <a name="use-cisco-anyconnect-client-for-ios----1333708---"></a>İOS için Cisco AnyConnect istemcisi kullanma <!-- 1333708 -->

İOS için yeni bir VPN profili oluşturduğunuzda Şu anda iki seçenek vardır: **Cisco AnyConnect** ve **Cisco Legacy AnyConnect**. Cisco AnyConnect profilleri 4.0.7 x ve daha yeni sürümleri destekler. Mevcut iOS Cisco AnyConnect VPN profilleri, **Cisco eski AnyConnect**olarak etiketlidir ve bugün olduğu gibi Cisco AnyConnect 4.0.5 x ve daha eski sürümlerle çalışmaya devam eder.

> [!NOTE]
> Bu değişiklik yalnızca iOS için geçerlidir. Android, Android kurumsal iş profilleri ve macOS platformları için yalnızca bir Cisco AnyConnect seçeneği olmaya devam eder.


### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="new-enrollment-steps-for-users-on-devices-with-macos-high-sierra-10132---1734567---"></a>MacOS High Sierra 10.13.2 + cihazlarındaki kullanıcılar için yeni kayıt adımları <!--1734567 -->
macOS High Sierra 10.13.2, "Kullanıcı onaylı" MDM kaydı kavramını sunmuştur. Onaylanan kayıtlar, Intune 'un güvenlikle duyarlı bazı ayarları yönetmesine izin verir. Daha fazla bilgi için Apple 'ın destek belgelerine bakın: https://support.apple.com/HT208019.

MacOS Şirket Portalı kullanılarak kaydedilen cihazlar, Son Kullanıcı sistem tercihlerini açıp el ile onay sunmadığı takdirde "Kullanıcı onaylı değil" olarak değerlendirilir. Bu uçta macOS Şirket Portalı artık macOS 10.13.2 ve üzeri kullanıcıların kayıt işleminin sonunda kaydını el ile onaylamasını sağlar. Kayıtlı bir cihaz Kullanıcı tarafından onaylanırsa, Intune yönetici konsolu üzerinde rapor alınacaktır.

#### <a name="jamf-enrolled-macos-devices-can-now-register-with-intune----2370684---"></a>JAMF kayıtlı macOS cihazları artık Intune 'a kaydolmuş olabilir <!-- 2370684 -->
MacOS Şirket portalı 'nın 1,3 ve 1,4 sürümleri, JAMF cihazlarını Intune 'a başarıyla kaydedemedi. MacOS portalının sürüm 1.4.2 Bu sorunu düzeltir.

#### <a name="updated-help-experience-in-company-portal-app-for-android----1631531---"></a>Android için Şirket Portalı App 'teki güncelleştirilmiş yardım deneyimi <!-- 1631531 -->
Android platformu için en iyi uygulamalarla uyum sağlamak üzere Android için Şirket Portalı uygulamasındaki Yardım deneyimini güncelleştirdik. Artık kullanıcılar uygulamada bir sorunla karşılaştığında, **menü** > **Yardım** ve şunları yapabilirsiniz:
- Tanılama günlüklerini Microsoft 'a yükleyin.
- Sorunu ve olay KIMLIĞINI bir şirket desteği kişisine açıklayan bir e-posta gönderin.  

Güncelleştirilmiş Yardım deneyimini kullanıma almak için, [e-posta kullanarak günlükleri gönderme](/intune-user-help/send-logs-to-your-it-admin-by-email-android) ve [Microsoft 'a hata gönderme](/intune-user-help/send-logs-to-microsoft-android)bölümüne gidin.


#### <a name="new-enrollment-failure-trend-chart-and-failure-reasons-table----1471783---"></a>Yeni kayıt hatası eğilimi grafiği ve hata nedenleri tablosu <!-- 1471783 -->
Kayıt genel bakış sayfasında, kayıt hatalarının eğilimini ve hataların en üstteki beş nedenini görüntüleyebilirsiniz. Grafiğe veya tabloya tıklayarak sorun giderme önerisi ve düzeltme önerilerini bulmak için ayrıntılara gidebilirsiniz.


### <a name="device-management"></a>Cihaz yönetimi

#### <a name="advanced-threat-protection-atp-and-intune-are-fully-integrated----1629303---"></a>Gelişmiş tehdit koruması (ATP) ve Intune tamamen tümleşiktir <!-- 1629303 -->

[Gelişmiş tehdit koruması (ATP)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/dashboard-windows-defender-advanced-threat-protection) , Windows 10 cihazlarının risk düzeyini gösterir. Windows Defender Güvenlik Merkezi 'nde (ATP portalı) Microsoft Intune bir bağlantı oluşturabilirsiniz. Bir Intune uyumluluk ilkesi oluşturulduktan sonra, kabul edilebilir tehdit düzeyini tespit etmek için kullanılır. Tehdit düzeyi aşılırsa, bir Azure Active Directory (AD) koşullu erişim ilkesi daha sonra kuruluşunuzdaki farklı uygulamalara erişimi engelleyebilir.

Bu özellik, ATP 'nin dosyaları taramasına, tehditleri algılamasına ve Windows 10 cihazlarınıza herhangi bir riski rapor etmesine olanak tanır.

Bkz. [Intune 'Da koşullu ERIŞIMLE ATP 'Yi etkinleştirme](../protect/advanced-threat-protection.md).

#### <a name="support-for-user-less-devices----1637553---"></a>Kullanıcı-daha az cihazlar için destek <!-- 1637553 -->
Intune, Microsoft Surface Hub gibi kullanıcı tarafından daha az bir cihazda uyumluluğu değerlendirebilme özelliğini destekler. Uyumluluk ilkesi, belirli cihazları hedefleyebilir. Bu nedenle, ilişkili bir kullanıcısı olmayan cihazlarda uyumluluk (ve uyumsuzluk) belirlenebilir.

#### <a name="delete-autopilot-devices----1713650---"></a>Autopilot cihazlarını Sil <!-- 1713650 -->
Intune yöneticileri, [Autopilot cihazlarını silebilir](../enrollment/enrollment-autopilot.md#delete-autopilot-devices).

#### <a name="improved-device-deletion-experience---1832333---"></a>İyileştirilmiş cihaz silme deneyimi <!--1832333 -->
Artık [bir cihazı Intune 'dan silmeden](../remote-actions/devices-wipe.md#delete-devices-from-the-intune-portal)önce şirket verilerini kaldırmanız veya cihazı fabrika ayarlarına sıfırlamamak zorunda değilsiniz.

Yeni deneyimi görmek için Intune 'da oturum açın ve **cihaz  >  ' i seçin** **tüm cihazlar** > **Sil**' e tıklayın.

Hala temizleme/devre dışı bırakma onayı istiyorsanız, **silme**işleminden önce **Şirket verilerini kaldır** ve **Fabrika Sıfırlaması** vererek standart cihaz yaşam döngüsü yolunu kullanabilirsiniz. 

#### <a name="play-sounds-on-ios-when-in-lost-mode----1947769---"></a>Kayıp modundayken iOS 'ta ses çal <!-- 1947769 -->
Denetimli iOS cihazları mobil cihaz yönetimi (MDM) [kayıp modunda](../remote-actions/device-lost-mode.md)olduğunda [bir ses](../remote-actions/device-locate.md#activate-lost-mode-sound-alert-on-an-ios-device) (**cihazlar** >  ' e kadar**tüm cihazları** > bir iOS cihazı seçebilir > **genel bakış** > **daha fazla**) kullanabilirsiniz. Cihaz kayıp modundan kaldırılana kadar veya bir Kullanıcı cihazda sesi devre dışı bırakılana kadar ses oynatılmaya devam eder. İOS cihazları 9,3 ve üzeri için geçerlidir.

#### <a name="block-or-allow-web-results-in-searches-made-on-an-intune-device---1972804--"></a>Intune cihazında yapılan aramalardaki Web sonuçlarının engellenmesini veya bunlara izin vermeyi <!--1972804-->

Yöneticiler artık bir cihazda gerçekleştirilen aramalardan Web sonuçlarını engelleyebilir.

#### <a name="improved-error-messaging-for-apple-mdm-push-certificate-upload-failure----2172331---"></a>Apple MDM Anında İletme Sertifikası karşıya yükleme hatası için geliştirilmiş hata iletileri <!-- 2172331 -->

Hata iletisi, mevcut bir MDM sertifikası yenilenirken aynı Apple KIMLIĞI 'nin kullanılması gerektiğini açıklar.

#### <a name="test-the-company-portal-for-macos-on-virtual-machines----2216679---"></a>Sanal makinelerde macOS için Şirket Portalı test etme <!-- 2216679 -->

BT yöneticilerinin Parallels Desktop ve VMware Fusion 'daki sanal makinelerde macOS için Şirket Portalı uygulamasını test etmenize yardımcı olacak yönergeler yayımladık. [Test için sanal macOS makinelerini kaydetme konusunda](../enrollment/macos-enroll.md#enroll-virtual-macos-machines-for-testing)daha fazla bilgi edinin.

### <a name="intune-apps"></a>Intune uygulamaları

#### <a name="user-experience-update-for-the-company-portal-app-for-ios---1412866---"></a>İOS için Şirket Portalı App için Kullanıcı deneyimi güncelleştirmesi <!--1412866 -->
İOS için Şirket Portalı uygulamasına büyük bir kullanıcı deneyimi güncelleştirmesi yayımladık. Güncelleştirme, modernlanmış bir görünüm içeren ve tüm görsel yeniden tasarlayabilme özelliği içerir. Uygulamanın işlevselliğini yaptık, ancak kullanılabilirliğini ve erişilebilirliğini artırdık.  

Ayrıca şunları görürsünüz:
- İPhone X için destek.
- Kullanıcıların süresini kaydetmek için daha hızlı uygulama başlatma ve yükleme yanıtları.
- Kullanıcılara en güncel durum bilgilerini sağlamak için ek ilerleme çubukları.
- Kullanıcıların günlükleri karşıya yükleme yöntemiyle yapılan geliştirmeler, bir şeyler yanlış olursa raporlamak daha kolay olur.  

Güncelleştirilmiş görünümü görmek için [uygulama kullanıcı arabirimindeki](../whats-new-app-ui.md)yenilikler ' e gidin.

#### <a name="protect-on-premises-exchange-data-using-intune-app-and-ca----1056954---"></a>Intune UYGULAMASı ve CA kullanarak şirket içi Exchange verilerini koruma <!-- 1056954 -->
Artık, Outlook Mobile ile şirket içi Exchange verilerine erişimi korumak için Intune uygulama Ilkesi koruması (uygulama) ve koşullu erişim (CA) kullanabilirsiniz. Azure portal içinde bir uygulama koruma ilkesi eklemek veya değiştirmek için, **Microsoft Intune** > **istemci uygulamaları** > **Uygulama koruma ilkeleri**' ni seçin. Bu özelliği kullanmadan önce [iOS ve Android Için Outlook gereksinimlerini](https://technet.microsoft.com/library/mt846639(v=exchg.160).aspx)karşıladığınızdan emin olun.


### <a name="user-interface"></a>Kullanıcı arabirimi

#### <a name="improved-device-tiles-in-the-windows-10-company-portal---2213364---"></a>Windows 10 ' da geliştirilmiş cihaz kutucukları Şirket Portalı <!--2213364 -->

Kutucuklar, düşük Vision kullanıcılarına daha erişilebilir olacak şekilde güncelleştirilmiştir ve ekran okuma araçları için daha iyi performans sağlar.

#### <a name="send-diagnostic-reports-in-company-portal-app-for-macos----2216677---"></a>MacOS için Şirket Portalı App 'te tanılama raporları gönderme <!-- 2216677 -->
MacOS cihazları için Şirket Portalı uygulaması, kullanıcıların Intune ile ilgili hataları bildirme biçimini geliştirmek üzere güncelleştirildi. Şirket Portalı uygulamasından çalışanlarınız şunları yapabilir:

- Tanılama raporlarını doğrudan Microsoft Geliştirici ekibine yükleyin.
- Şirketinizin BT destek ekibine bir olay KIMLIĞI e-postası gönderin.

Daha fazla bilgi için bkz. [macOS Için gönderme hataları](/intune-user-help/send-errors-macos).

#### <a name="intune-adapts-to-fluent-design-system-in-the-company-portal-app-for-windows-10----1195010---"></a>Intune, Windows 10 için Şirket Portalı uygulamasında, akıcı tasarım sistemine uyum sağlar <!-- 1195010 -->
Windows 10 için Intune Şirket Portalı uygulaması, [akıcı tasarım sisteminin Gezinti görünümü](https://docs.microsoft.com/windows/uwp/design/basics/navigation-basics)ile güncelleştirilmiştir. Uygulamanın yanında, tüm üst düzey sayfaların statik, dikey bir listesini görürsünüz. Sayfaları hızlıca görüntülemek ve aralarında geçiş yapmak için herhangi bir bağlantıya tıklayın. Bu, Intune 'da daha Uyarlamalı, empathetic ve tanıdık bir deneyim oluşturmak için devam eden çabamızın bir parçası olarak göreceğiniz birkaç güncelleştirmenin ilkidir. Güncelleştirilmiş görünümü görmek için [uygulama kullanıcı arabirimindeki](../whats-new-app-ui.md)yenilikler ' e gidin.

<!-- ########################## -->
## <a name="march-2018"></a>Mart 2018

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="alerts-for-expiring-ios-line-of-business-lob-apps-for-microsoft-intune----748789---"></a>Microsoft Intune için süresi dolan iOS iş kolu (LOB) uygulamalarına yönelik uyarılar <!-- 748789 -->

Azure portal, Intune, süreleri dolacak olan iOS iş kolu uygulamaları için sizi uyarır. İOS iş kolu uygulamasının yeni bir sürümünü karşıya yükledikten sonra Intune, süre sonu bildirimini uygulama listesinden kaldırır. Bu süre sonu bildirimi yalnızca yeni yüklenen iOS iş kolu uygulamaları için etkin olacaktır. İOS LOB uygulaması sağlama profilinin süresi dolmadan önce 30 gün önce bir uyarı görüntülenir. Süresi dolduğunda, uyarının süresi dolan olarak değişir.

#### <a name="customize-your-company-portal-themes-with-hex-codes---1049561---"></a>Şirket Portalı temalarınızı onaltılık kodlarla özelleştirme <!--1049561 -->

Şirket Portalı uygulamalardaki tema rengini onaltılık kodlar kullanarak özelleştirebilirsiniz. Onaltılık kodunuzu girdiğinizde, Intune metin rengi ile arka plan rengi arasında en yüksek düzeyde karşıtlık sağlayan metin rengini belirler. @No__t-1**Şirket portalı** **istemci uygulamalardaki**renge karşı hem metin rengini hem de şirket logonuzu önizleyebilirsiniz.

### <a name="including-and-excluding-app-assignment-based-on-groups-for-android-enterprise----1813081---"></a>Android Enterprise gruplarına göre uygulama atamasını dahil etme ve hariç tutma <!-- 1813081 -->

Android Enterprise (eski adıyla Android for Work), grupların dahil ve dışlanmasını destekler, ancak önceden oluşturulmuş **tüm kullanıcıları** ve **tüm cihazlar** yerleşik gruplarını desteklemez. Daha fazla bilgi için, bkz. [Microsoft Intune uygulama atamalarını dahil etme ve hariç tutma](../apps/apps-inc-exl-assignments.md).


### <a name="device-management"></a>Cihaz yönetimi

### <a name="export-all-devices-into-csv-files-in-ie-microsoft-edge-or-chrome----2258071---"></a>Tüm cihazları IE, Microsoft Edge veya Chrome 'daki CSV dosyalarına aktarma <!-- 2258071 -->
Cihazlar **@no__t-** 1**tüm cihazlar**' da, cihazları csv biçimli bir listeye **dışarı aktarabilirsiniz** . > 10000 cihazı olan Internet Explorer (IE) kullanıcıları cihazlarını birden çok dosyaya başarıyla aktarabilir. Her bir dosyanın 10.000 ' e kadar cihazı vardır.

> 30000 cihazlarındaki Microsoft Edge ve Chrome kullanıcıları, cihazlarını birden çok dosyaya başarıyla aktarabilir. Her bir dosyanın 30.000 ' e kadar cihazı vardır.

[Cihazları yönetme](../remote-actions/device-management.md) , yönettiğiniz cihazlarla yapabilecekleriniz hakkında daha fazla ayrıntı sağlar.

#### <a name="new-security-enhancements-in-the-intune-service-----1637539---"></a>Intune hizmetinde yeni güvenlik geliştirmeleri  <!-- 1637539 -->   

Intune 'un tek başına müşterilerinin, cihazları **uyumlu** (güvenlik özelliği kapalı) olarak atanmış herhangi bir ilke olmadan değerlendirmek veya bu cihazları **uyumsuz** (güvenlik özelliği) olarak kabul etmek için kullanabileceği, Azure 'da Intune 'da bir geçiş yaptık. Bu, yalnızca cihaz uyumluluğu değerlendirildikten sonra kaynaklara erişimi sağlar.

Bu özellik, zaten atanmış uyumluluk ilkelerine sahip olup olmadığına bağlı olarak farklı şekilde etkiler.

- Yeni veya mevcut bir hesabınız varsa ve cihazlarınıza atanmış bir uyumluluk ilkesi yoksa, geçiş otomatik olarak **uyumlu**olarak ayarlanır. Bu özellik konsolunda varsayılan ayar olarak kapalıdır. Son Kullanıcı etkisi yoktur.
- Mevcut bir hesabınız varsa ve bu hesaba atanmış bir uyumluluk ilkesi varsa, geçiş otomatik olarak **uyumlu değil**olarak ayarlanır. Bu özellik, Mart güncelleştirmesi dışarı geldiğinde varsayılan ayar olarak açık olur.

Uyumluluk ilkelerini koşullu erişim (CA) ile birlikte kullanıyorsanız ve özelliği açıksa, en az bir uyumluluk ilkesi atanmamış cihazlar artık CA tarafından engellenir. Tüm cihazlara en az bir uyumluluk ilkesi atamadığınız müddetçe, daha önce e-postaya erişim izni verilen bu cihazlarla ilişkilendirilmiş son kullanıcılar.   

Varsayılan geçiş durumu, Intune hizmeti Mart güncelleştirmeleri ile hemen Kullanıcı arabiriminde görüntülense de, bu geçiş durumu hemen uygulanmaz. Geçiş sırasında yaptığınız tüm değişiklikler, hesabınızı çalışma geçişi olmadan yapana kadar cihaz uyumluluğunu etkilemez. Hesabınızı uçucağımız zaman Ileti Merkezi aracılığıyla size haber göndereceğiz. Bu işlem, Intune hizmetinizin Mart için güncelleştirildikten birkaç gün sürebilir.

**Ek bilgi**: [https://aka.ms/compliance_policies](https://aka.ms/compliance_policies)

#### <a name="enhanced-jailbreak-detection----846515---"></a>Gelişmiş jailbreak algılama <!-- 846515 -->

Gelişmiş jailbreak algılama, Intune 'un jailbreak uygulanmış cihazlarını değerlendirme şeklini geliştiren yeni bir uyumluluk ayarıdır. Ayar, cihazın Intune 'a daha sık iade edilmesine neden olur; bu da cihazın konum hizmetlerini kullanır ve pil kullanımını etkiler.

#### <a name="reset-passwords-for-android-o-devices----1238299---"></a>Android O cihazlar için parolaları sıfırlama <!-- 1238299 -->
Kayıtlı Android 8,0 cihazlarının parolalarını Iş profilleriyle sıfırlayabileceksiniz. Android 8,0 cihazına bir "parola sıfırlama" isteği gönderdiğinizde, geçerli kullanıcıya yeni bir cihaz kilidi açma parolası veya yönetilen profil sınaması ayarlar. Parola veya zorluk gönderilir ve anında devreye girer.

#### <a name="targeting-compliance-policies-to-devices-in-device-groups---1307012---"></a>Uyumluluk ilkelerini cihaz gruplarındaki cihazlara hedefleme <!--1307012 -->

Uyumluluk ilkelerini Kullanıcı gruplarındaki kullanıcılara hedefleyebilirsiniz. Bu güncelleştirmeyle uyumluluk ilkelerini cihaz gruplarındaki cihazlara hedefleyebilirsiniz. Cihaz gruplarının bir parçası olarak hedeflenen cihazlar herhangi bir uyumluluk eylemi almaz.

#### <a name="new-management-name-column----1333586---"></a>Yeni yönetim adı sütunu <!-- 1333586 -->
 Cihazlar dikey penceresinde **Yönetim adı** adlı yeni bir sütun kullanılabilir. Bu, aşağıdaki formüle göre cihaz başına atanan otomatik oluşturulmuş, düzenlenemeyen bir addır:
- Tüm cihazlar için varsayılan ad: <username> @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4
- Toplu eklenen cihazlar için: < PackageID/ProfileId > <em> @ no__t-1 @ no__t-2 @ no__t-3

Bu, cihazlar dikey penceresinde isteğe bağlı bir sütundur. Varsayılan olarak kullanılamaz ve yalnızca sütun seçiciyi kullanarak erişebilirsiniz. Cihaz adı bu yeni sütundan etkilenmez.

#### <a name="ios-devices-are-prompted-for-a-pin-every-15-minutes---1550837---"></a>iOS cihazlarına 15 dakikada bir PIN sorulur <!--1550837 -->
Bir iOS cihazına uyumluluk veya yapılandırma ilkesi uygulandıktan sonra, kullanıcılardan 15 dakikada bir PIN ayarlaması istenir. PIN ayarlanana kadar kullanıcılara sürekli olarak sorulur.

#### <a name="schedule-your-automatic-updates---1805514---"></a>Otomatik güncelleştirmelerinizi zamanlayın <!--1805514 -->
Intune, [Windows Update halka ayarlarını](../protect/windows-update-for-business-configure.md)kullanarak otomatik güncelleştirmeleri yüklemeye yönelik denetim sağlar. Bu güncelleştirmeyle, hafta, gün ve saat dahil olmak üzere yeniden gerçekleşen güncelleştirmeler zamanlayabilirsiniz.

#### <a name="use-fully-distinguished-name-as-subject-for-scep-certificate---2221763---"></a>SCEP sertifikası için konu olarak tam ayırt edici ad kullan <!--2221763 -->
Bir SCEP sertifika profili oluştururken, konu adını girersiniz. Bu güncelleştirmeyle, konu olarak tam ayırt edici adı kullanabilirsiniz. **Konu adı**için **özel**' i seçin ve ardından `CN={{OnPrem_Distinguished_Name}}` yazın. @No__t-0 değişkenini kullanmak için, Azure AD 'nize [Azure Active Directory (ad)](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) kullanarak `onpremisesdistingishedname` Kullanıcı özniteliğini eşitlediğinizden emin olun.

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="enable-bluetooth-contact-sharing---android-for-work---1098983---"></a>Bluetooth kişi paylaşımını etkinleştirme-Android for Work <!--1098983 -->
Varsayılan olarak, Android iş profilindeki kişilerin Bluetooth cihazlarla eşitlenmesini engeller. Sonuç olarak, iş profili kişileri Bluetooth cihazları için arayan KIMLIĞINDE gösterilmez.

Bu güncelleştirmeyle, **Android for work** > **cihaz kısıtlamalarına** > **iş profili ayarları**için yeni bir ayar vardır:
- Bluetooth ile kişi paylaşımı

Intune Yöneticisi bu ayarları paylaşımı etkinleştirecek şekilde yapılandırabilir. Bu, sorunsuz kullanım için arayan KIMLIĞINI görüntüleyen bir otomobil tabanlı Bluetooth cihazındaki bir cihazı eşleştirmesinde yararlı olur. Etkinleştirildiğinde, iş profili kişileri görüntülenir. Etkinleştirilmediğinde, iş profili kişileri görüntülenmez.

#### <a name="configure-gatekeeper-to-control-macos-app-download-source----1690459---"></a>MacOS uygulama indirme kaynağını denetlemek için ağ geçidi denetleyicisini yapılandırma <!-- 1690459 -->

Uygulamaların nereden indirilebileceğini denetleyerek cihazları uygulamalardan korumak için ağ geçidi denetleyicisini yapılandırabilirsiniz. Aşağıdaki indirme kaynaklarını yapılandırabilirsiniz: **Mac App Store**, **Mac App Store ve tanımlanan geliştiriciler**veya **her yerde**. Kullanıcıların, bu ağ geçidi denetleyicisi denetimlerini geçersiz kılmak için Control-Click ' i kullanarak bir uygulamayı yükleyip yükleyemeyeceğini yapılandırabilirsiniz.

Bu ayarlar **cihaz yapılandırma** -> **profil oluşturma** -> **MacOS** -> **uç nokta koruması**altında bulunabilir.

#### <a name="configure-the-mac-application-firewall----1690461---"></a>Mac uygulaması güvenlik duvarını yapılandırma <!-- 1690461 -->

Mac uygulaması güvenlik duvarını yapılandırabilirsiniz. Bu bağlantıyı, her bağlantı noktası temelinde değil uygulama başına temelinde denetlemek için kullanabilirsiniz. Bu, güvenlik duvarı korumasının avantajlarını daha kolay hale getirir ve istenmeyen uygulamaların meşru uygulamalar için açık ağ bağlantı noktaları denetimini almasını önlemeye yardımcı olur.

Bu özellik **cihaz yapılandırma** -> **profil oluşturma** -> **MacOS** -> **uç nokta koruması**altında bulunabilir.

Güvenlik duvarı ayarını etkinleştirdikten sonra, güvenlik duvarını iki strateji kullanarak yapılandırabilirsiniz:

- Tüm gelen bağlantıları engelle

   Hedeflenen cihazlar için tüm gelen bağlantıları engelleyebilirsiniz. Bunu yapmak isterseniz, tüm uygulamalar için gelen bağlantılar engellenir.

- Belirli uygulamalara izin ver veya engelle

   Belirli uygulamaların gelen bağlantıları almasına izin verebilir veya onları engelleyebilirsiniz. Ayrıca, yoklama isteklerine yönelik yanıtları engellemek için gizli modu da etkinleştirebilirsiniz.

#### <a name="detailed-error-codes-and-messages----1376342---"></a>Ayrıntılı hata kodları ve iletileri <!-- 1376342 -->

Cihaz yapılandırmanızda, daha ayrıntılı hata kodları ve görebileceğiniz hata iletileri mevcuttur. Bu geliştirilmiş raporlama, ayarları, bu ayarların durumunu ve sorun giderme hakkındaki ayrıntıları gösterir.

##### <a name="more-information"></a>Daha fazla bilgi

- Tüm gelen bağlantıları engelle

   Bu, tüm paylaşım hizmetlerinin (dosya paylaşımı ve ekran paylaşımı gibi) gelen bağlantıları almasını engeller. Gelen bağlantıları almasına hala izin verilen sistem hizmetleri şunlardır:
  - configd-DHCP ve diğer ağ yapılandırma hizmetlerini uygular
  - Mdnsyanıtlayıcısı-Bonjour uygular
  - Pcoon-IPSec uygular

    Paylaşım hizmetlerini kullanmak için **gelen bağlantıların** **Yapılandırılmadı** ( **blok**değil) olarak ayarlandığından emin olun.

- Gizli mod

   Bilgisayarın yoklama isteklerine yanıt vermesini engellemek için bunu etkinleştirin. Bilgisayar, yetkili uygulamalar için gelen istekleri yine de yanıtlar. ICMP (ping) gibi beklenmeyen istekler yok sayılır.

#### <a name="disable-checks-on-device-restart---1805490---"></a>Cihaz yeniden başlatıldığında denetimleri devre dışı bırak <!--1805490 -->
Intune, [yazılım güncelleştirmelerini yönetmek](../protect/windows-update-for-business-configure.md)için denetim sağlar. Bu güncelleştirmeyle, <strong>yeniden başlatma denetimleri</strong> özelliği kullanılabilir ve varsayılan olarak etkindir. Bir cihazı (örneğin, etkin kullanıcılar, pil düzeyleri vb.) yeniden başlattığınızda gerçekleşen tipik denetimleri atlamak için <strong>Atla</strong>' yı seçin.

#### <a name="new-windows-10-insider-preview-channels-available-for-deployment-rings----1746293---"></a>Yeni Windows 10 Insider Preview kanalları dağıtım halkaları için kullanılabilir <!-- 1746293 -->
Artık bir Windows 10 dağıtım halkası oluştururken aşağıdaki Windows 10 Insider Preview bakım kanallarını seçme seçeneğiniz vardır:
- Windows Insider derleme &#8208; Fast
- Windows Insider derlemesi &#8208; yavaş
- Windows Insider derlemesini yayınla 

Bu kanallar hakkında daha fazla bilgi için bkz. [Insider Preview derlemelerini yönetme](https://insider.windows.com/for-business-organization-admin/).   
Intune 'da dağıtım kanalları oluşturma hakkında daha fazla bilgi için bkz. [Intune 'da yazılım güncelleştirmelerini yönetme](../protect/windows-update-for-business-configure.md).

### <a name="new-windows-defender-exploit-guard-settings----1631893---"></a>Yeni Windows Defender Exploit Guard ayarları <!-- 1631893 -->

Altı yeni <strong>saldırı yüzeyi azaltma</strong> ayarı ve genişletilmiş <strong>denetimli klasör erişimi: klasör koruma</strong> özellikleri artık kullanılabilir. Bu ayarlar şurada bulunabilir: Device configuration\Profiles\
Profile\Endpoint protection\Windows Defender Exploit Guard oluşturun.

#### <a name="attack-surface-reduction"></a>Saldırı yüzeyi azaltma

|Ayar adı  |Ayar seçenekleri  |Açıklama  |
|---------|---------|---------|
|Gelişmiş fidye yazılımı koruması|Etkin, denetim, yapılandırılmadı|Agresif fidye yazılımı korumasını kullanın.|
|Windows yerel güvenlik yetkilisi alt sisteminden kimlik bilgisi çalmasını işaretle|Etkin, denetim, yapılandırılmadı|Windows yerel güvenlik yetkilisi alt sisteminden (Lsass. exe) kimlik bilgisi çalmasını işaretle.|
|PSExec ve WMI komutlarından işlem oluşturma|Engelleme, denetim, yapılandırılmadı|PSExec ve WMI komutlarından kaynaklanan işlem oluşturma işlemlerini engelleyin.|
|USB 'den çalıştırılan güvenilmeyen ve imzasız süreçler|Engelleme, denetim, yapılandırılmadı|USB 'den çalıştırılan güvenilmeyen ve imzasız işlemlere engel olmak.|
|Yaygınlık, Yaş veya güvenilen liste ölçütlerine uymayan yürütülebilir dosyalar|Engelleme, denetim, yapılandırılmadı|Bir Preter, Age veya güvenilir liste ölçütlerine uymadıkları takdirde yürütülebilir dosyaların çalıştırılmasını engelleyin.|

#### <a name="controlled-folder-access"></a>Denetlenen klasör erişimi

|              Ayar adı               |                                                              Ayar seçenekleri                                                              | Açıklama |
|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|-------------|
| Klasör koruma (zaten uygulanmış) | Yapılandırılmadı, etkinleştir, yalnızca denetle (zaten uygulanmış)<br><br> <strong>Yeni</strong><br>Disk değişikliğini engelle, disk değişikliğini denetle |             |

Dosya ve klasörleri, kolay olmayan uygulamalar tarafından yetkilendirilmemiş değişikliklerden koruyun.<br><br>**Etkinleştir**: güvenilmeyen uygulamaların korunan klasörlerdeki dosyaları değiştirmesini veya silmesini ve disk sektörlerine yazılmasını engelleyin.<br><br>
**Yalnızca disk değişikliğini engelle**:<br>Güvenilmeyen uygulamaların disk sektörlerine yazmasını engelleyin. Güvenilmeyen uygulamalar, korunan klasörlerdeki dosyaları değiştirmeye veya silmeye devam edebilir. |

### <a name="intune-apps"></a>Intune uygulamaları

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Azure Active Directory Web siteleri Intune Managed Browser uygulamayı gerektirebilir ve Managed Browser (Genel Önizleme) için çoklu oturum açma desteği sağlayabilir <!-- 710595 -->

Azure Active Directory (Azure AD) kullanarak, artık mobil cihazlardaki web sitelerine erişimi Intune Managed Browser uygulamasına kısıtlayabilirsiniz. Managed Browser Web sitesi verileri, Son Kullanıcı kişisel verilerinden güvenli ve ayrı kalacak. Ayrıca Managed Browser, Azure AD tarafından korunan siteler için çoklu oturum açma yeteneklerini destekleyecektir. Managed Browser oturum açma veya Intune tarafından yönetilen başka bir uygulamayla bir cihazda Managed Browser kullanma, Managed Browser kullanıcının kimlik bilgilerini girmesi gerekmeden Azure AD tarafından korunan kurumsal sitelere erişmesine izin verir. Bu işlevsellik, Outlook Web Erişimi (OWA) ve SharePoint Online gibi sitelerde ve Azure uygulama proxy 'Si aracılığıyla erişilen intranet kaynakları gibi diğer kurumsal sitelerde geçerlidir. Daha fazla bilgi için bkz. [Azure Active Directory Koşullu erişim Içindeki erişim denetimleri](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-controls).

#### <a name="company-portal-app-for-android-visual-updates---976944---"></a>Android görsel güncelleştirmeleri için Şirket Portalı uygulaması <!--976944 -->

Android için Şirket Portalı uygulamasını, Android 'in [malzeme tasarımı](https://material.io/) yönergelerine uymak üzere güncelleştirdik. Yeni simgelerin görüntülerini, [uygulama arabirimindeki yenilikler](../whats-new-app-ui.md) makalesinde görebilirsiniz.

#### <a name="company-portal-enrollment-improved----1874230-eeready--"></a>Şirket Portalı kaydı geliştirildi <!-- 1874230 eeready-->
Windows 10 Build 1703 ve üzerinde Şirket Portalı kullanarak bir cihazı kaydeden kullanıcılar artık uygulamadan çıkmadan kaydın ilk adımını tamamlayabiliyor.
#### <a name="hololens-and-surface-hub-now-appear-in-device-lists---1725868---"></a>HoloLens ve Surface Hub artık cihaz listelerinde görünüyor <!--1725868 -->
Intune 'a kayıtlı HoloLens ve Surface Hub cihazlarını Android için Şirket Portalı uygulamasına göstermek için destek ekledik.

#### <a name="custom-book-categories-for-volume-purchase-program-vpp-ebooks----1488911---"></a>Toplu satın alma programı (VPP) eBooks için özel kitap kategorileri <!-- 1488911 -->
Özel eKitap kategorileri oluşturabilir ve ardından bu özel eKitap kategorilerine VPP eBooks atayabilirsiniz. Son kullanıcılar daha sonra kategorilere atanmış yeni oluşturulan eKitap kategorilerini ve kitaplarını görebilir. Daha fazla bilgi için bkz. [Microsoft Intune ile toplu satın alınan uygulamaları ve kitapları yönetme](../apps/vpp-apps.md).  

#### <a name="support-changes-for-company-portal-app-for-windows-send-feedback-option----2070166---"></a>Windows için Şirket Portalı uygulaması için destek geri bildirim gönder seçeneği <!-- 2070166 -->
30 Nisan 2018 ' den itibaren, Windows için Şirket Portalı uygulamasındaki **geri bildirim gönder** seçeneği, yalnızca Windows 10 yıldönümü güncelleştirmesi (1607) ve üstünü çalıştıran cihazlarda çalışacaktır. Windows için Şirket Portalı uygulaması kullanılırken geri bildirim gönderme seçeneği artık desteklenmez:  
- Windows 10, 1507 sürümü  
- Windows 10, 1511 sürümü  
- Windows Phone 8,1 

Cihazınız Windows 10 RS1 veya sonraki sürümlerde çalışıyorsa, mağazadan Windows Şirket Portalı uygulamasının en son sürümünü indirin. Desteklenmeyen bir sürüm çalıştırıyorsanız, lütfen aşağıdaki kanallar aracılığıyla geri bildirim gönderilmeye devam edin: 
- Windows 10 ' da geri bildirim Merkezi uygulaması
- E-posta WinCPfeedback@microsoft.com  

#### <a name="new-windows-defender-application-guard-settings----1631890---"></a>Yeni Windows Defender Application Guard ayarları <!-- 1631890 -->

- **Grafik hızlandırmasını etkinleştir**: Yöneticiler, Windows Defender Application Guard için bir sanal grafik işlemcisini etkinleştirebilir. Bu ayar, CPU 'nun vGPU 'ye grafik işlemesini boşaltması için izin verir. Bu, grafik güçlü web siteleriyle çalışırken veya kapsayıcı içinde video izlerken performansı iyileştirebilir.

- **Savefilestohost**: Yöneticiler, dosyaların kapsayıcıda çalışan Microsoft Edge 'den konak dosya sistemine geçmesine izin verebilir. Bunu açmak, kullanıcıların kapsayıcıda Microsoft Edge 'den konak dosya sistemine dosya indirmesini sağlar.

#### <a name="mam-protection-policies-targeted-based-on-management-state----1665993---"></a>Yönetim durumu temelinde hedeflenen MAM koruma ilkeleri <!-- 1665993 -->
MAM ilkelerini, cihazın yönetim durumuna göre hedefleyebilirsiniz:
- **Android cihazlar** -yönetilmeyen cihazları, Intune yönetilen cihazlarını ve Intune tarafından yönetilen Android kurumsal profillerini (eski adıyla Android for Work) hedefleyebilirsiniz.
- **iOS cihazları** -yönetilmeyen cihazları (yalnızca MAM) veya Intune tarafından yönetilen cihazları hedefleyebilirsiniz.

    > [!NOTE]
    > - Bu işlevsellik için iOS desteği, Nisan 2018 ' de kullanıma alınıyor.

Daha fazla bilgi için bkz. [cihaz yönetim durumuna bağlı olarak hedef uygulama koruma ilkeleri](../apps/app-protection-policies.md).

#### <a name="improvements-to-the-language-in-the-company-portal-app-for-windows----1683758---"></a>Windows için Şirket Portalı uygulamasındaki dilde geliştirmeler <!-- 1683758 -->
Windows 10 için Şirket Portalı dilini daha kolay ve şirketinize özgü olacak şekilde geliştirdik. Yaptığımız nesnelerin bazı örnek görüntülerini görmek için bkz. [uygulama kullanıcı arabirimindeki](../whats-new-app-ui.md)yenilikler.

#### <a name="new-additions-to-our-docs-about-user-privacy----1440709---"></a>Kullanıcı gizliliği hakkında belgelerimize yeni ekler <!-- 1440709 -->
Son kullanıcılara verileri ve gizliliği üzerinde daha fazla denetim verme çabamız kapsamında, docs. Şirket Portalı uygulamalar tarafından yerel olarak depolanan verilerin nasıl görüntüleneceğini ve kaldırılacağını açıklayan güncelleştirmeler yayımladık. Bu güncelleştirmeleri şurada bulabilirsiniz:

- **Android**: [Android cihazınızı Intune 'dan kaldırma](/intune-user-help/unenroll-your-device-from-intune-android)
- **Android, Kullanıcı kullanım koşullarını reddetdiyse**: ["Kullanım Koşulları" nı reddettiyseniz cihaz yönetimini kaldırın](/intune-user-help/unenroll-your-device-from-intune-if-you-declined-terms-of-use-android)
- **iOS**: [iOS cihazınızı Intune 'dan kaldırma](/intune-user-help/unenroll-your-device-from-intune-ios)
- **Windows**: [Windows cihazınızı Intune 'dan kaldırma](/intune-user-help/unenroll-your-device-from-intune-windows)

<!-- ########################## -->
## <a name="february-2018"></a>Şubat 2018

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685---"></a>Birden çok Apple DEP/Apple Okul Yöneticisi hesabı için Intune desteği <!-- 747685 -->

Intune artık cihazların 100 farklı [apple aygıt kayıt programı (DEP)](../enrollment/device-enrollment-program-enroll-ios.md) veya [Apple Okul Yöneticisi](../enrollment/apple-school-manager-set-up-ios.md) hesaplarından kaydedilmesini desteklemektedir. Karşıya yüklenen her belirteç, kayıt profilleri ve cihazlar için ayrı olarak yönetilebilir. Farklı bir kayıt profili, DEP/okul yöneticisi belirteci başına otomatik olarak atanabilir. Birden çok okul yöneticisi belirteci karşıya yüklenirse, tek seferde Microsoft okul veri eşitleme ile yalnızca bir tane paylaşılabilir.

Geçişten sonra, Beta Graph API 'Leri ve Apple DEP veya ASM 'YI grafik üzerinde bir şekilde yönetmeye yönelik yayımlanmış betikler artık çalışmayacaktır. Yeni beta Graph API 'Leri geliştirme aşamasındadır ve geçişten sonra yayınlanacaktır.

#### <a name="see-enrollment-restrictions-per-user----1634444-eeready-wnready---"></a>Kullanıcı başına kayıt kısıtlamalarına bakın <!-- 1634444 eeready wnready -->
**Sorun giderme** dikey penceresinde, artık **atamalar** listesinden **Kayıt kısıtlamaları** ' nı seçerek her kullanıcı için geçerli olan [kayıt kısıtlamalarını](../enrollment/enrollment-restrictions-set.md) görebilirsiniz.

#### <a name="new-option-for-user-authentication-for-apple-bulk-enrollment----747625-eeready---"></a>Apple toplu kayıt için Kullanıcı kimlik doğrulaması için yeni seçenek <!-- 747625 eeready -->

> [!NOTE]
> Yeni kiracılar bu hakkı hemen görür. Mevcut kiracılar için bu özellik Nisan ayında kullanıma sunulacaktır. Bu kullanıma alma tamamlanana kadar bu yeni özelliklere erişiminiz olmayabilir.

Intune artık aşağıdaki kayıt yöntemleri için Şirket Portalı uygulamasını kullanarak cihazların kimliğini doğrulama seçeneği sunar:

- Apple Aygıt Kayıt Programı
- Apple Okul Yöneticisi
- Apple Configurator kaydı

Şirket Portalı seçeneği kullanılırken, bu kayıt yöntemlerinin engellenmeksizin Multi-Factor Authentication Azure Active Directory zorlanabilir.

Şirket Portalı seçeneği kullanılırken, Intune Kullanıcı benzeşimi kaydı için iOS Kurulum Yardımcısı 'nda Kullanıcı kimlik doğrulamasını atlar. Bu, cihazın başlangıçta kullanıcısız bir cihaz olarak kaydedildiği ve dolayısıyla kullanıcı gruplarının yapılandırmasını ya da ilkelerini almamasıdır. Yalnızca cihaz gruplarına yönelik yapılandırma ve ilkeleri alır. Ancak, Intune Şirket Portalı uygulamasını cihaza otomatik olarak yükler. Şirket Portalı uygulamayı başlatmak ve oturum açmak için kullanacağınız ilk Kullanıcı, Intune 'daki cihazla ilişkilendirilir. Bu noktada, Kullanıcı Kullanıcı gruplarının yapılandırmasını ve ilkelerini alır. Kullanıcı ilişkilendirmesi yeniden kayıt olmadan değiştirilemez.

#### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685-eeready---"></a>Birden çok Apple DEP/Apple Okul Yöneticisi hesabı için Intune desteği <!-- 747685 eeready -->

Intune artık cihazların 100 farklı Apple Aygıt Kayıt Programı (DEP) veya Apple Okul Yöneticisi hesaplarından kaydedilmesini desteklemektedir. Karşıya yüklenen her belirteç, kayıt profilleri ve cihazlar için ayrı olarak yönetilebilir. Farklı bir kayıt profili, DEP/okul yöneticisi belirteci başına otomatik olarak atanabilir. Birden çok okul yöneticisi belirteci karşıya yüklenirse, tek seferde Microsoft okul veri eşitleme ile yalnızca bir tane paylaşılabilir.

Geçişten sonra, Beta Graph API 'Leri ve Apple DEP veya ASM 'YI grafik üzerinde bir şekilde yönetmeye yönelik yayımlanmış betikler artık çalışmayacaktır. Yeni beta Graph API 'Leri geliştirme aşamasındadır ve geçişten sonra yayınlanacaktır.

### <a name="remote-printing-over-a-secure-network----1709994----"></a>Güvenli bir ağ üzerinden uzaktan yazdırma <!-- 1709994  -->
PrinterOn 'un kablosuz mobil yazdırma çözümleri, kullanıcıların güvenli bir ağ üzerinden dilediğiniz zaman uzaktan yazdırmasını sağlar. PrinterOn, hem iOS hem de Android için Intune uygulama SDK 'Sı ile tümleşir. Yönetici konsolundaki Intune **Uygulama koruma ilkeleri** dikey penceresi aracılığıyla uygulama koruma ilkelerini bu uygulamaya hedefleyebilirsiniz. Son kullanıcılar, Intune ekosistemi içinde kullanmak üzere Play Store veya iTunes ' dan Microsoft 'a ' PrinterOn ' uygulamasını indirebilecektir.

### <a name="macos-company-portal-support-for-enrollments-that-use-the-device-enrollment-manager----1352411---"></a>macOS Şirket Portalı cihaz kayıt yöneticisini kullanan kayıtlar için destek <!-- 1352411 -->

Kullanıcılar artık macOS Şirket Portalı kaydolurken cihaz kayıt yöneticisi 'Ni kullanabilir.

### <a name="device-management"></a>Cihaz yönetimi

#### <a name="windows-defender-health-status-and-threat-status-reports---854704---"></a>Windows Defender sistem durumu ve tehdit durumu raporları <!--854704 -->

Windows Defender 'ın durumunu anlama, Windows bilgisayarlarını yönetme anahtarıdır.  Bu güncelleştirmeyle Intune, Windows Defender aracısının durumu ve durumuna yeni raporlar ve eylemler ekler. [Cihaz uyumluluğu iş](../protect/compliance-policy-monitor.md)yükünde bir durum toplama raporu kullanarak, aşağıdakilerden herhangi birine ihtiyacı olan cihazları görebilirsiniz:
- imza güncelleştirmesi
- Yeniden Başlatma
- el ile müdahale
- tam tarama
- müdahale gerektiren diğer aracı durumları

Her bir durum kategorisi için bir detaya gitme raporu, ilgilenilmesi gereken bireysel bilgisayarları veya **temiz**olarak raporlananlar listesini listeler.

#### <a name="new-privacy-settings-for-device-restrictions---1308926---"></a>Cihaz kısıtlamaları için yeni gizlilik ayarları <!--1308926 -->
Cihazlar için [iki yeni gizlilik ayarı](../configuration/device-restrictions-windows-10.md#privacy) artık kullanılabilir:
- **Kullanıcı etkinliklerini Yayımla**: görev değiştiricide paylaşılan deneyimleri ve son kullanılan kaynakların bulunmasını engellemek Için bunu **bloğa** ayarlayın.
- **Yalnızca yerel etkinlikler**: Bu ayarı, paylaşılan deneyimleri ve yalnızca yerel etkinliğe göre görev değiştiricisinde son kullanılan kaynakları bulmayı **engelleyecek şekilde ayarlayın** .

#### <a name="new-settings-for-the-microsoft-edge-browser---1469166---"></a>Microsoft Edge tarayıcısı için yeni ayarlar <!--1469166 -->
Microsoft Edge tarayıcısı olan cihazlar için [iki yeni ayar](../configuration/device-restrictions-windows-10.md#microsoft-edge-browser) artık kullanılabilir: **Sık Kullanılanlar dosyasının yolu** ve **sık kullanılanlarda değişiklikler**.

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="protocol-exceptions-for-applications---1035509---"></a>Uygulamalar için protokol özel durumları <!--1035509 -->

Artık belirli yönetilmeyen uygulamaları açmak için Intune mobil uygulama yönetimi (MAM) veri aktarımı ilkesi için özel durumlar oluşturabilirsiniz. Bu tür uygulamalara güvenilmesi gerekir. Oluşturduğunuz özel durumlar dışında, veri aktarımı ilkeniz **yalnızca yönetilen uygulamalar**olarak ayarlandığında veri aktarımı Intune tarafından yönetilen uygulamalarla sınırlandırılır. Kısıtlamaları protokol (iOS) veya paketler (Android) kullanarak oluşturabilirsiniz.

Örneğin, WebEx paketini MAM veri aktarımı ilkesine bir özel durum olarak ekleyebilirsiniz. Bu, yönetilen bir Outlook e-posta iletisindeki WebEx bağlantılarının doğrudan WebEx uygulamasında açılmasını sağlar. Veri aktarımı, diğer yönetilmeyen uygulamalarda de kısıtlanacaktır. Daha fazla bilgi için bkz. [uygulamalar Için veri aktarım ilkesi özel durumları](../apps/app-protection-policies-exception.md).

#### <a name="windows-information-protection-wip-encrypted-data-in-windows-search-results----1469193---"></a>Windows Search sonuçlarında Windows Information Protection (WıP) şifrelenmiş veriler <!-- 1469193 -->
Windows Information Protection (WıP) ilkesindeki bir ayar artık Windows Search sonuçlarına WıP ile şifrelenmiş verilerin dahil edilip edilmeyeceğini denetlemenize olanak tanır. Windows Information Protection ilkesinin **Gelişmiş ayarlarında** **Windows Search Dizin Oluşturucu 'nun şifrelenmiş öğeleri aramasına izin ver** ' i seçerek bu uygulama koruma ilkesi seçeneğini belirleyin. Uygulama koruma ilkesi *Windows 10* platformuna ayarlanmalıdır ve uygulama ilkesi **kayıt durumu** **kayıt ile**olarak ayarlanmalıdır. Daha fazla bilgi için bkz. [Windows Search Dizin Oluşturucu 'nun şifrelenmiş öğeleri aramasına Izin verme](../apps/windows-information-protection-policy-create.md#allow-windows-search-indexer-to-search-encrypted-items).

#### <a name="configuring-a-self-updating-mobile-msi-app----1740840---"></a>Kendi kendini güncelleştiren bir mobil MSI uygulaması yapılandırma <!-- 1740840 -->
Sürüm denetimi işlemini yok saymak için, bilinen bir kendi kendini güncelleştiren mobil MSI uygulaması yapılandırabilirsiniz. Bu yetenek, yarış durumuna ulaşmaktan kaçınmak için yararlıdır. Örneğin, uygulama geliştirici tarafından otomatik olarak güncellenmekte olan uygulamanın Intune tarafından da güncelleştirilmesi durumunda bu yarış durumu türü gerçekleşebilir. Her ikisi de bir Windows istemcisinde uygulamanın bir sürümünü zorlamaya çalışabilir, bu da bir çakışma oluşturabilir. Bu otomatik olarak güncellenen MSI uygulamaları için **uygulama bilgileri** dikey penceresinde **uygulama sürümünü yoksay** ayarını yapılandırabilirsiniz. Bu ayar **Evet**'e geçildiğinde, Microsoft Intune Windows istemcisinde yüklü olan uygulama sürümünü yoksayar.

#### <a name="related-sets-of-app-licenses-supported-in-intune----1864117---"></a>Intune 'da desteklenen ilgili uygulama lisansı kümeleri <!-- 1864117 -->
Azure portal Intune, artık Kullanıcı arabiriminde tek bir uygulama öğesi olarak ilgili uygulama lisansı kümelerini desteklemektedir. Ayrıca, Microsoft Store Iş için eşitlenen tüm çevrimdışı lisanslı uygulamalar tek bir uygulama girişi ile birleştirilir ve tek tek paketlerden dağıtım ayrıntıları tek girişe geçirilir. Azure portal ilgili uygulama lisansı kümelerini görüntülemek için **istemci uygulamalar** dikey penceresinden **uygulama lisansları** ' nı seçin.

### <a name="device-configuration"></a>Cihaz yapılandırması
#### <a name="windows-information-protection-wip-file-extensions-for-automatic-encryption----1463582---"></a>Otomatik şifreleme için Windows Information Protection (WıP) dosya uzantıları <!-- 1463582 -->
Windows Information Protection (WıP) ilkesindeki bir ayar artık, WıP ilkesinde tanımlandığı şekilde kurumsal sınır içindeki bir sunucu Ileti bloğu (SMB) paylaşımından kopyalarken hangi dosya uzantılarının otomatik olarak şifreleneceğini belirtmenize olanak tanır.

#### <a name="configure-resource-account-settings-for-surface-hubs"></a>Surface Hub 'Lar için kaynak hesap ayarlarını yapılandırma

Artık Surface Hub 'Lar için kaynak hesap ayarlarını uzaktan yapılandırabilirsiniz.

Kaynak hesabı, Skype/Exchange 'e göre kimlik doğrulaması yapmak için bir Surface Hub tarafından kullanılır; böylece bir toplantıya katılabilir.
Surface Hub toplantıda konferans odası olarak görünmesi için benzersiz bir kaynak hesabı oluşturmanız gerekir.
Örneğin, **konferans odası B41/6233**gibi bir kaynak hesabı.

> [!NOTE]
> - Alanları boş bırakırsanız, cihazda önceden yapılandırılmış öznitelikleri geçersiz kılabilirsiniz.
>
> - Kaynak hesabı özellikleri Surface Hub dinamik olarak değiştirilebilir. Örneğin, parola döndürme açık ise. Bu nedenle, Azure konsolundaki değerlerin cihazdaki gerçekliği yansıtması biraz zaman alabilir.
>
>   Surface Hub Şu anda yapılandırıldığını anlamak için, kaynak hesap bilgileri donanım envanterine (zaten 7 gün aralığına sahip) veya salt okuma özelliklerine dahil edilebilir. Uzak eylem gerçekleştirildikten sonra doğruluğu iyileştirmek için, Surface Hub hesabı/parametreleri güncelleştirmek üzere eylemi çalıştırdıktan hemen sonra parametrelerin durumunu alabilirsiniz.

##### <a name="attack-surface-reduction"></a>Saldırı yüzeyi azaltma

|Ayar adı  |Ayar seçenekleri  |Açıklama  |
|---------|---------|---------|
|Parola korumalı yürütülebilir içeriğin e-postayla yürütülmesi|Engelleme, denetim, yapılandırılmadı|E-posta üzerinden indirilen parola korumalı yürütülebilir dosyaları çalışır şekilde engelleyin.|
|Gelişmiş fidye yazılımı koruması|Etkin, denetim, yapılandırılmadı|Agresif fidye yazılımı korumasını kullanın.|
|Windows yerel güvenlik yetkilisi alt sisteminden kimlik bilgisi çalmasını işaretle|Etkin, denetim, yapılandırılmadı|Windows yerel güvenlik yetkilisi alt sisteminden (Lsass. exe) kimlik bilgisi çalmasını işaretle.|
|PSExec ve WMI komutlarından işlem oluşturma|Engelleme, denetim, yapılandırılmadı|PSExec ve WMI komutlarından kaynaklanan işlem oluşturma işlemlerini engelleyin.|
|USB 'den çalıştırılan güvenilmeyen ve imzasız süreçler|Engelleme, denetim, yapılandırılmadı|USB 'den çalıştırılan güvenilmeyen ve imzasız işlemlere engel olmak.|
|Yaygınlık, Yaş veya güvenilen liste ölçütlerine uymayan yürütülebilir dosyalar|Engelleme, denetim, yapılandırılmadı|Bir Preter, Age veya güvenilir liste ölçütlerine uymadıkları takdirde yürütülebilir dosyaların çalıştırılmasını engelleyin.|

##### <a name="controlled-folder-access"></a>Denetlenen klasör erişimi

|              Ayar adı               |                                                              Ayar seçenekleri                                                              | Açıklama |
|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|-------------|
| Klasör koruma (zaten uygulanmış) | Yapılandırılmadı, etkinleştir, yalnızca denetle (zaten uygulanmış)<br><br> <strong>Yeni</strong><br>Disk değişikliğini engelle, disk değişikliğini denetle |             |

Dosya ve klasörleri, kolay olmayan uygulamalar tarafından yetkilendirilmemiş değişikliklerden koruyun.<br><br>**Etkinleştir**: güvenilmeyen uygulamaların korunan klasörlerdeki dosyaları değiştirmesini veya silmesini ve disk sektörlerine yazılmasını engelleyin.<br><br>
**Yalnızca disk değişikliğini engelle**:<br>Güvenilmeyen uygulamaların disk sektörlerine yazmasını engelleyin. Güvenilmeyen uygulamalar, korunan klasörlerdeki dosyaları değiştirmeye veya silmeye devam edebilir. |

#### <a name="additions-to-system-security-settings-for-windows-10-and-later-compliance-policies---1704133--"></a>Windows 10 ve üzeri uyumluluk ilkeleri için sistem güvenlik ayarlarına eklemeler <!--1704133-->

Windows 10 uyumluluk ayarlarına ek olarak, güvenlik duvarı ve Windows Defender virüsten koruma gerektirme dahil, artık kullanılabilir.

### <a name="intune-apps"></a>Intune uygulamaları

#### <a name="support-for-offline-apps-from-the-microsoft-store-for-business---1222672--"></a>Microsoft Store Iş için çevrimdışı uygulamalar için destek <!--1222672-->
Iş için Microsoft Store satın aldığınız çevrimdışı uygulamalar artık Azure portal eşitlenir. Bu uygulamaları cihaz gruplarına veya Kullanıcı gruplarına dağıtabilirsiniz. Çevrimdışı uygulamalar, mağaza tarafından değil Intune tarafından yüklenir.

#### <a name="prevent-end-users-from-manually-adding-or-removing-accounts-in-the-work-profile----1728700---"></a>Son kullanıcıların iş profilinde hesapları el ile eklemesini veya kaldırmasını engelleyin <!-- 1728700 -->

Gmail uygulamasını bir Android for Work profiline dağıttığınızda, artık Android for Work cihaz kısıtlama profilindeki **Hesap Ekle veya Kaldır** ayarını kullanarak son kullanıcıların iş profilinde hesapları el ile eklemesini veya kaldırmasını engelleyebilirsiniz.

<!-- ########################## -->
## <a name="january-2018"></a>Ocak 2018

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="alerts-for-expired-tokens-and-tokens-that-will-soon-expire----1639263---"></a>Zaman aşımına uğrayacak süre sonu belirteçleri ve belirteçleri için uyarılar <!-- 1639263 -->
Genel Bakış sayfası artık süreleri dolan belirteçlerin ve kısa süre önce dolacak belirteçlerin uyarılarını gösterir. Tek bir belirteç için bir uyarıya tıkladığınızda, belirtecin ayrıntılar sayfasına gidebilirsiniz.  Birden çok belirteçle uyarı ' a tıkladığınızda, tüm belirteçlerin durumlarına sahip olan bir listeye gidebilirsiniz. Yöneticiler, süre sonu tarihinden önce belirteçlerini yenilemelidir.

### <a name="device-management"></a>Cihaz yönetimi

#### <a name="remote-erase-command-support-for-macos-devices----1438084---"></a>MacOS cihazları için uzaktan "Sil" komutu desteği <!-- 1438084 -->

Yöneticiler, macOS cihazları için uzaktan silme komutu verebilir.

> [!IMPORTANT]
> Erase komutu ters çevrilemez ve dikkatli kullanılmalıdır.

Erase komutu, işletim sistemi dahil olmak üzere tüm verileri bir cihazdan kaldırır. Ayrıca, cihazı Intune yönetiminden kaldırır. Kullanıcıya hiçbir uyarı verilmez ve komut verildikten sonra silinme hemen meydana gelir.

6 basamaklı bir kurtarma PIN 'ı yapılandırmanız gerekir. Bu PIN, silinen cihazın kilidini açmak için kullanılabilir, bu da işletim sisteminin yeniden yüklenmesi başlayacaktır. Silinme başladıktan sonra, PIN Intune 'da cihazın genel bakış dikey penceresinde bir durum çubuğunda görüntülenir. Silinme devam ettiği sürece PIN kalır. Silinme tamamlandıktan sonra, cihaz tamamen Intune yönetiminden kaybolur. Cihazın geri yüklenmesi için kurtarma PIN 'ini kaydettiğinizden emin olun.

#### <a name="revoke-licenses-for-an-ios-volume-purchasing-program-token----820870---"></a>İOS toplu satın alma programı belirteci için lisansları iptal etme <!-- 820870 -->
Belirli bir VPP belirteci için tüm iOS toplu satın alma programı (VPP) uygulamalarının lisansını iptal edebilirsiniz.

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="revoking-ios-volume-purchase-program-apps-----820863---"></a>İOS toplu satın alma programı uygulamalarını iptal etme  <!-- 820863 -->
Bir veya daha fazla iOS toplu satın alma programı (VPP) uygulaması olan belirli bir cihaz için, cihaz için ilişkili cihaz tabanlı uygulama lisansını iptal edebilirsiniz. Uygulama lisansını iptal etmek ilgili VPP uygulamasını cihazdan kaldırmaz. Bir VPP uygulamasını kaldırmak için, atama eylemini **Kaldır**olarak değiştirmeniz gerekir. Daha fazla bilgi için, [Microsoft Intune ile toplu satın alma programı aracılığıyla satın alınan iOS uygulamalarını yönetme](../apps/vpp-apps-ios.md)bölümüne bakın.

#### <a name="assign-office-365-mobile-apps-to-ios-and-android-devices-using-built-in-app-type----1332318---"></a>Yerleşik uygulama türünü kullanarak iOS ve Android cihazlarına Office 365 mobil uygulamaları atama <!-- 1332318 -->
**Yerleşik** uygulama türü, yönettiğiniz IOS ve Android cihazlarına Office 365 uygulamaları oluşturup atamanızı kolaylaştırır. Bu uygulamalar Word, Excel, PowerPoint ve OneDrive gibi 0365 uygulamaları içerir. Uygulama türüne belirli uygulamaları atayabilir ve uygulama bilgileri yapılandırmasını düzenleyebilirsiniz.

#### <a name="including-and-excluding-app-assignment-based-on-groups----1406920---"></a>Gruplar temelinde uygulama atamasını dahil etme ve hariç tutma <!-- 1406920 -->

Uygulama ataması sırasında ve bir atama türü seçtikten sonra, dahil edilecek grupları ve hariç tutulacak grupları seçebilirsiniz.

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="you-can-assign-an-application-configuration-policy-to-groups-by-including-and-excluding-assignments-----1480316---"></a>Atamaları ekleyerek ve dışlayarak gruplara bir uygulama yapılandırma ilkesi atayabilirsiniz  <!-- 1480316 -->

Bir uygulama yapılandırma ilkesini, bir Kullanıcı ve cihaz grubuna, atamaları dahil ve hariç tutma bileşimini kullanarak atayabilirsiniz. Atamalar, özel grup seçimi veya bir sanal grup olarak seçilebilir. Bir sanal grup **tüm kullanıcılar**, **Tüm**cihazlar ve tüm **Kullanıcılar + tüm cihazlar**' A dahil olabilir.

#### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a>Windows 10 sürüm yükseltme ilkesi desteği   <!-- 903672(archived), 1119689 -->  
Windows 10 cihazlarını Windows 10 eğitimi, Windows 10 eğitim N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional eğitimi ve Windows 10 Professional Eğitim N 'ye yükselten bir Windows 10 sürüm yükseltme ilkesi oluşturabilirsiniz. Windows 10 sürüm yükseltmeleri hakkında daha fazla bilgi için bkz. [Windows 10 sürüm yükseltmelerini yapılandırma](../configuration/edition-upgrade-configure-windows-10.md).

#### <a name="conditional-access-policies-for-intune-is-only-available-from-the-azure-portal-----1737088-1634311---"></a>Intune için koşullu erişim ilkeleri yalnızca Azure portal kullanılabilir  <!-- 1737088 1634311 -->

Bu sürümden itibaren, koşullu erişim ilkelerinizi [Azure portal](https://portal.azure.com) **Azure Active Directory** > **koşullu erişimi**arasından yapılandırmanız ve yönetmeniz gerekir. Size kolaylık olması için, **ıntune** > **koşullu erişimi**Azure Portal Intune 'dan bu dikey pencereye de erişebilirsiniz.

#### <a name="updates-to-compliance-emails---1637547---"></a>Uyumluluk e-postalarında güncelleştirmeler <!--1637547 -->

Uyumsuz bir cihazı raporlamak için bir e-posta gönderildiğinde, uyumsuz cihaz hakkındaki ayrıntılar dahil edilir.

### <a name="intune-apps"></a>Intune uygulamaları

#### <a name="new-functionality-for-the-resolve-action-for-android-devices---1583480--"></a>Android cihazları için "çözümle" eylemi için yeni işlevsellik <!--1583480-->

Android için Şirket Portalı uygulaması, cihaz [şifreleme sorunlarını](/intune-user-help/encrypt-your-device-android)çözmek üzere **cihaz ayarlarını güncelleştirme** için "çözümle" eylemini genişletiyor.

#### <a name="remote-lock-available-in-company-portal-app-for-windows-10---676506--"></a>Windows 10 için Şirket Portalı uygulamasında uzaktan kilitleme kullanılabilir <!--676506-->
Son kullanıcılar artık Windows 10 için Şirket Portalı uygulamasından cihazlarını uzaktan kilitleyebilirler. Bu, etkin olarak kullandıkları yerel cihaz için görüntülenmez.

#### <a name="easier-resolution-of-compliance-issues-for-the-company-portal-app-for-windows-10---676546--"></a>Windows 10 için Şirket Portalı uygulamasına yönelik uyumluluk sorunlarının daha kolay çözümlenmesi <!--676546-->
Windows cihazlarıyla son kullanıcılar Şirket Portalı uygulamasındaki uyumsuzluk nedenine dokunabilirsiniz. Mümkün olduğunda, bu işlem, sorunu gidermek için doğrudan ayarlar uygulamasındaki doğru konuma götürür.

<!-- ########################## -->
## <a name="december-2017"></a>Aralık 2017

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="new-automatic-redeployment-setting----1469168---"></a>Yeni otomatik yeniden dağıtım ayarı <!-- 1469168 -->
**Otomatik yeniden dağıtım** ayarı, yönetici haklarına sahip olan kullanıcıların cihaz kilidi ekranında **CTRL + Win + R** kullanarak tüm Kullanıcı verilerini ve ayarlarını silmesine izin verir. Cihaz otomatik olarak yeniden yapılandırılır ve yönetime yeniden kaydedilir. Bu ayar Windows 10 > cihaz kısıtlamalarının altında, Genel > otomatik yeniden dağıtımı > bulunabilir. Ayrıntılar için bkz. [Windows 10 Için Intune cihaz kısıtlama ayarları](../configuration/device-restrictions-windows-10.md#general).

#### <a name="support-for-additional-source-editions-in-the-windows-10-edition-upgrade-policy-----903672--1119689---"></a>Windows 10 sürüm yükseltme ilkesinde ek kaynak sürümleri için destek  <!-- 903672,  1119689 -->
Artık Windows 10 sürüm yükseltme ilkesini, ek Windows 10 sürümlerinden (Windows 10 Pro, eğitim için Windows 10 Pro, Windows 10 bulutu vb.) yükseltmek için kullanabilirsiniz. Bu sürümden önce, desteklenen sürüm yükseltme yolları daha sınırlandırıldı. Ayrıntılar için bkz. [Windows 10 sürüm yükseltmelerini yapılandırma](../configuration/edition-upgrade-configure-windows-10.md).

#### <a name="new-windows-defender-security-center-wdsc-device-configuration-profile-settings----1335507---"></a>Yeni Windows Defender Güvenlik Merkezi (WDSC) cihaz yapılandırması profil ayarları <!-- 1335507 -->

Intune, **Windows Defender Güvenlik Merkezi**adlı Endpoint Protection altında cihaz yapılandırma profili ayarlarının yeni bir bölümünü ekler. BT yöneticileri, son kullanıcıların Windows Defender Güvenlik Merkezi uygulamasının hangi piline erişebileceğini yapılandırabilirler. BT Yöneticisi Windows Defender Güvenlik Merkezi uygulamasında bir ekran listesini gizlediyseniz, gizli pillerle ilgili tüm bildirimler kullanıcının cihazında görüntülenmez.

Yöneticiler Windows Defender Güvenlik Merkezi cihaz yapılandırma profili ayarlarından gizlenebilir.
- Virüs ve tehdit koruması
- Cihaz performansı ve sistem durumu
- Güvenlik Duvarı ve ağ korumaları
- Uygulama ve tarayıcı denetimi
- Aile seçenekleri

BT yöneticileri, kullanıcıların hangi bildirimleri alacağını da özelleştirebilir. Örneğin, kullanıcıların WDSC 'de görünür sütunlar veya yalnızca kritik bildirimler tarafından oluşturulan tüm bildirimleri alıp almamadığını yapılandırabilirsiniz. Kritik olmayan bildirimler, taramalar tamamlandığında Windows Defender virüsten koruma etkinliğinin ve bildirimlerinin düzenli özetlerini içerir. Diğer tüm bildirimler kritik olarak değerlendirilir. Ayrıca, bildirim içeriğinin kendisini de özelleştirebilirsiniz, örneğin, kullanıcıların cihazlarında görünen bildirimlere eklemek için BT iletişim bilgilerini sağlayabilirsiniz.

#### <a name="multiple-connector-support-for-scep-and-pfx-certificate-handling----1361755---"></a>SCEP ve PFX Sertifika işleme için çoklu bağlayıcı desteği <!-- 1361755 -->

Şirket içi NDES bağlayıcısını kullanarak cihazlara sertifika sunmaya yönelik müşteriler artık tek bir kiracıda birden çok bağlayıcıyı yapılandırabilir.

Bu yeni özellik aşağıdaki senaryoyu destekler:

- **Yüksek kullanılabilirlik**

Her NDES Bağlayıcısı, Intune 'dan sertifika istekleri çeker.  Bir NDES Bağlayıcısı çevrimdışı olursa, diğer bağlayıcı istekleri işlemeye devam edebilir.

#### <a name="customer-subject-name-can-use-aad_device_id-variable-----1468599---"></a>Müşteri konu adı, AAD_DEVICE_ID değişkenini kullanabilir  <!-- 1468599 -->

Intune 'da bir SCEP sertifika profili oluşturduğunuzda, özel konu adını oluştururken artık AAD_DEVICE_ID değişkenini kullanabilirsiniz.   Sertifika bu SCEP profilini kullanarak istendiğinde, değişken, sertifika isteğini yapan cihazın AAD cihaz KIMLIĞI ile değiştirilmiştir.


### <a name="device-management"></a>Cihaz yönetimi

#### <a name="manage-jamf-enrolled-macos-devices-with-intunes-device-compliance-engine----1592747---"></a>Intune 'un cihaz uyumluluk altyapısı ile JAMF ile kaydedilen macOS cihazlarını yönetme <!-- 1592747 -->
Artık JAMF 'yi, macOS cihaz durumu bilgilerini Intune 'a göndermek için Intune konsolunda tanımlanan ilkelerle uyumluluk açısından değerlendirecek şekilde kullanabilirsiniz. Cihaz uyumluluk durumuna ve diğer koşullara (konum, Kullanıcı riski vb.) bağlı olarak, koşullu erişim, Azure AD ile bağlantılı bulut ve şirket içi uygulamalara ve Office 365 dahil olmak üzere şirket içi uygulamalara erişen macOS cihazları için uyumluluğu zorlayacaktır. JAMF [tümleştirmesi ayarlama](../protect/conditional-access-integrate-jamf.md) ve [JAMF tarafından yönetilen cihazlar için uyumluluğu zorlama](../protect/conditional-access-assign-jamf.md)hakkında daha fazla bilgi edinin.

#### <a name="new-ios-device-action------1424701---"></a>Yeni iOS cihaz eylemi   <!-- 1424701 -->

Artık iOS 10,3 denetimli cihazları kapatabilirsiniz. Bu eylem, son kullanıcıya uyarı vermeden cihazı hemen kapatır. **Cihaz** iş yükünde bir cihaz seçtiğinizde, **kapatma (yalnızca denetimli)** eylemi cihaz özelliklerinde bulunabilir.

#### <a name="disallow-datetime-changes-to-samsung-knox-devices----1468103---"></a>Samsung KNOX cihazlarında tarih/saat değişikliklerine izin verme <!-- 1468103 -->

Samsung KNOX cihazlarında tarih ve saat değişikliklerini engellemenizi sağlayan yeni bir özellik ekledik. Bunu, **cihaz yapılandırma profillerinde** > **cihaz kısıtlamaları (Android)**  > **genel**' de bulabilirsiniz.

#### <a name="surface-hub-resource-account-supported----1566442----"></a>Surface Hub kaynak hesabı destekleniyor <!-- 1566442  -->

Yöneticilerin bir Surface Hub ile ilişkili kaynak hesabını tanımlayıp güncelleştirebilmesi için yeni bir cihaz eylemi eklenmiştir.

Kaynak hesabı, Skype/Exchange ile kimlik doğrulaması yapmak için bir Surface Hub tarafından kullanılır; böylece bir toplantıya katılabilir. Surface Hub toplantıda konferans odası olarak görünmesi için benzersiz bir kaynak hesabı oluşturabilirsiniz. Örneğin, kaynak hesabı, *konferans odası B41/6233*olarak görünebilir. Surface Hub için kaynak hesabının (cihaz hesabı olarak bilinir) genellikle konferans odası konumu ve diğer kaynak hesabı parametrelerinin değiştirilmesi gerektiğinde yapılandırılması gerekir.

Yöneticiler bir cihazdaki kaynak hesabını güncelleştirmek istediklerinde, cihaz ile ilişkili geçerli Active Directory/Azure Active Directory kimlik bilgilerini sağlamaları gerekir. Cihaz için parola döndürme açık ise, yöneticilerin parolayı bulmak için Azure Active Directory 'e gitmesi gerekir.

> [!NOTE]
> Tüm alanlar bir paket içinde gönderilir ve daha önce yapılandırılmış tüm alanların üzerine yazılır. Boş alanlar var olan alanların üzerine de yazılır.

Yöneticilerin yapılandırakullanabilecekleri ayarlar şunlardır:

- **Kaynak hesap**
  - **Active Directory Kullanıcı**

    Etkialanı \ KullanıcıAdı veya Kullanıcı asıl adı (UPN): user@domainname.com

  - **Parola**

- **Isteğe bağlı kaynak hesap parametreleri** (belirtilen kaynak hesabı kullanılarak ayarlanmalıdır)

  - **Parola döndürme dönemi**

    Hesap parolasının, güvenlik nedenleriyle her hafta Surface Hub tarafından otomatik olarak güncelleştirilmesini sağlar. Bu etkinleştirildikten sonra herhangi bir parametreyi yapılandırmak için, Azure Active Directory ' deki hesabın ilk olarak parola sıfırlaması gerekir.

  - **SIP (oturum başlatma Protokolü) adresi**

    Yalnızca otomatik bulma başarısız olduğunda kullanılır.

  - **E-posta**

    Cihaz/kaynak hesabının e-posta adresi.

  - **Exchange Server**

    Yalnızca otomatik bulma başarısız olduğunda gereklidir.

  - **Takvim eşitleme**

    Takvim eşitleme ve diğer Exchange Server hizmetlerinin etkinleştirilip etkinleştirilmeyeceğini belirtir. Örneğin: toplantı eşitleme.

#### <a name="install-office-apps-on-macos-devices----1494311---"></a>MacOS cihazlarına Office uygulamalarını yükler <!-- 1494311 -->
Artık, macOS cihazlarına Office uygulamaları yükleyebilirsiniz. Bu yeni uygulama türü, Word, Excel, PowerPoint, Outlook ve OneNote yüklemenize olanak sağlayacak. Uygulamalarınızı güvenli ve güncel tutmaya yardımcı olmak için bu uygulamalar Microsoft otomatik güncelleştirme (MAU) ile birlikte da gelir.

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="delete-an-ios--volume-purchasing-program-token----820879---"></a>İOS toplu satın alma programı belirtecini silme <!-- 820879 -->
Konsolunu kullanarak iOS toplu satın alma programı (VPP) belirtecini silebilirsiniz. Bu, bir VPP belirtecinin yinelenen örneklerine sahip olduğunuzda gerekli olabilir.

### <a name="intune-apps"></a>Intune uygulamaları


### <a name="role-based-access-control"></a>Rol tabanlı erişim denetimi

#### <a name="a-new-entity-collection-named-current-user-is-limited-to-currently-active-user-data----1667026---"></a>Geçerli Kullanıcı adlı yeni bir varlık koleksiyonu şu anda etkin olan kullanıcı verileriyle sınırlı <!-- 1667026 -->

**Kullanıcılar** varlık koleksiyonu, kuruluşunuzda lisanslanmış lisansa sahip tüm Azure Active Directory (Azure AD) kullanıcılarını içerir. Örneğin, bir Kullanıcı Intune 'a eklenebilir ve son ayın kursu sırasında kaldırılabilir. Bu Kullanıcı rapor sırasında mevcut olmadığından, veride Kullanıcı ve durum bulunur. Verilerdeki geçmiş olma süresini gösteren bir rapor oluşturabilirsiniz.

Buna karşılık, yeni **Geçerli Kullanıcı** varlık koleksiyonu yalnızca kaldırılmayan kullanıcıları içerir. **Geçerli Kullanıcı** varlık koleksiyonu yalnızca şu anda etkin kullanıcıları içerir. **Geçerli Kullanıcı** varlık koleksiyonu hakkında daha fazla bilgi için bkz. [geçerli kullanıcı varlığı için başvuru](../developer/reports-ref-data-model.md).

### <a name="updated-graph-apis----1736360---"></a>Güncelleştirilmiş Graph API 'Leri <!-- 1736360 -->

Bu sürümde, Beta 'da olan Intune için Graph API birkaçını güncelleştirdik. Daha fazla bilgi için lütfen aylık [Graph API changelog](https://developer.microsoft.com/graph/docs/concepts/changelog) 'u inceleyin.

### <a name="monitor-and-troubleshoot"></a>İzleme ve sorun giderme

#### <a name="intune-supports-windows-information-protection-wip-denied-apps----1479103---"></a>Intune, Windows Information Protection (WıP) tarafından reddedilen uygulamaları destekler <!-- 1479103 -->
Intune 'da reddedilen uygulamaları belirtebilirsiniz. Bir uygulama reddedilirse, izin verilen uygulamalar listesinin tersine etkin bir şekilde şirket bilgilerine erişimi engellenir. Daha fazla bilgi için bkz. [Windows Information Protection Için önerilen reddetme listesi](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp?f=255&MSPPError=-2147217396#recommended-deny-list-for-windows-information-protection).

<!-- ########################## -->
## <a name="november-2017"></a>2017 Kasım

### <a name="troubleshoot-enrollment-issues-----746324---"></a>Kayıt sorunlarını giderme  <!-- 746324 -->

**Sorun giderme** çalışma alanı artık Kullanıcı kayıt sorunlarını gösterir. Sorun ve önerilen düzeltme adımları hakkındaki ayrıntılar, yöneticilerin ve yardım masası işletmenlerinin sorunları gidermelerine yardımcı olabilir. Bazı kayıt sorunları yakalanmaz ve bazı hatalar düzeltme önerilerinde bulunmayabilir.

### <a name="group-assigned-enrollment-restrictions----747598---"></a>Gruba atanan kayıt kısıtlamaları <!-- 747598 -->

Bir Intune Yöneticisi olarak, artık [Kullanıcı grupları için özel cihaz türü ve cihaz sınırı kayıt kısıtlamaları oluşturabilirsiniz](../enrollment/enrollment-restrictions-set.md).

Intune Azure portal, her kısıtlama türü için en fazla 25 örnek oluşturmanıza olanak sağlar ve bu daha sonra Kullanıcı gruplarına atanabilir. Grup tarafından atanan kısıtlamalar varsayılan kısıtlamaları geçersiz kılar.

Kısıtlama türünün tüm örnekleri, tam olarak sıralanmış bir listede tutulur. Bu sıra, çakışma çözümü için bir öncelik değeri tanımlar. Birden fazla kısıtlama örneğinden etkilenen bir Kullanıcı yalnızca en yüksek öncelik değerine sahip olan örnekle kısıtlıdır. Belirli bir örneğin önceliğini listede farklı bir konuma sürükleyerek değiştirebilirsiniz.

Bu işlevsellik, Android for Work kayıt menüsünden kayıt kısıtlamaları menüsüne geçiş için Android for Work ayarlarından birlikte yayımlanacak. Bu geçiş birkaç gün sürelediğinden, hesap kısıtlamaları için Grup atamasını etkinleştirmeden önce, hesabınız Kasım sürümünün diğer bölümleri için yükseltilebilir.

### <a name="support-for-multiple-network-device-enrollment-service-ndes-connectors----1528104---"></a>Birden çok ağ cihazı kayıt hizmeti (NDES) Bağlayıcısı desteği <!-- 1528104 -->

NDES, etki alanı kimlik bilgileri olmadan çalışan mobil cihazların Basit Sertifika Kayıt Protokolü (SCEP) temel alarak sertifikaları elde etmesine olanak tanır.
Bu güncelleştirme ile birden çok NDES Bağlayıcısı desteklenir.

### <a name="manage-android-for-work-devices-independently-from-android-devices----1490731-eeready--"></a>Android for Work cihazlarını Android cihazlarından bağımsız olarak yönetme <!-- 1490731 EEready-->

Intune, Android for Work cihazlarının Android platformundan bağımsız olarak kaydını yönetmeyi destekler. Bu ayarlar, **cihaz kaydı** **@no__t @no__t-** 3**cihaz türü kısıtlamaları**altında yönetilir. (Bunlar daha önce **cihaz kaydı** > **Android for Work kaydı** > **Android for Work kayıt ayarları**altında bulunuyordu.)

Varsayılan olarak, Android for Work cihaz ayarlarınız, Android cihazlarınızla ilgili ayarlarınızla aynıdır. Ancak, Android for Work ayarlarınızı değiştirdikten sonra artık bu durum olmayacaktır.

Kişisel Android for Work kaydını engellerseniz yalnızca şirket Android cihazları Android for Work olarak kaydedebilir.

Yeni ayarlarla çalışırken aşağıdaki noktaları dikkate alın:

#### <a name="if-you-have-never-previously-onboarded-android-for-work-enrollment"></a>Daha önce, Android for Work kaydına hiç eklendi

Yeni Android for Work platformu varsayılan cihaz türü kısıtlamalarında engellenir. Özelliği ekledikten sonra cihazların Android for Work ile kaydolmasına izin verebilirsiniz. Bunu yapmak için varsayılanı değiştirin veya varsayılan cihaz türü kısıtlamasının yerini almak için yeni bir cihaz türü kısıtlaması oluşturun.

#### <a name="if-you-have-onboarded-android-for-work-enrollment"></a>Eklendi Android for Work kaydınız varsa

Daha önce eklendi, durumunuz seçtiğiniz ayara bağlıdır:

| Ayar | Varsayılan cihaz türü kısıtlamasında Android for Work durumu | Notlar |
| --- | --- | --- |
| **Tüm cihazları Android olarak Yönet** | Engellendiğini | Tüm Android cihazların Android for Work olmadan kaydedilmesi gerekir. |
| **Desteklenen cihazları Android for Work olarak yönetme** | İzin verilen | Android for Work destekleyen tüm Android cihazların Android for Work 'e kaydolması gerekir. |
| **Yalnızca bu gruplardaki kullanıcılar için desteklenen cihazları Android for Work olarak Yönet** | Engellendiğini | Varsayılanı geçersiz kılmak için ayrı bir cihaz türü kısıtlama ilkesi oluşturuldu. Bu ilke, Android for Work kaydına izin vermek için önceden seçtiğiniz grupları tanımlar. Seçili gruplardaki kullanıcıların Android for Work cihazlarını kaydetmesine izin verilmeye devam edilir. Diğer tüm kullanıcıların Android for Work 'e kaydolmaları kısıtlıdır. |

Her durumda, hedeflenen Yönetmeliği korunur. Ortamınızda Android for Work 'ün küresel veya grup başına tahsisatından sorumlu olması için herhangi bir işlem yapmanız gerekmez.

### <a name="google-play-protect-support-on-android----908720---"></a>Android 'de desteği koruma Google Play <!-- 908720 -->

Android Oreo sürümü sayesinde, Google, kullanıcıların ve kuruluşların güvenli uygulamalar çalıştırmasına ve Android görüntülerini güvenli hale getirmelerine olanak tanıyan Google Play koruma adlı bir güvenlik özellikleri paketi sunar. Intune artık SafetyNet uzak kanıtlama dahil Google Play koruma özelliklerini desteklemektedir. Yöneticiler, Google Play korumak ve sağlıklı olması gereken uyumluluk ilkesi gereksinimlerini ayarlayabilir.
**SafetyNET cihaz kanıtlama** ayarı cihazın sağlıklı olduğunu ve güvenliğinin aşıldığını doğrulamak için cihazın bir Google hizmetine bağlanmasını gerektirir. Yöneticiler, yüklü uygulamaların Google Play hizmetleri tarafından doğrulanmasını gerektirmek için Android for Work için bir yapılandırma profili ayarı da ayarlayabilir. Bir cihaz Google Play koruma gereksinimleriyle uyumlu değilse, koşullu erişim kullanıcıların şirket kaynaklarına erişimini engelleyebilir.

- [Google Play koruma sağlamak için bir cihaz uyumluluk ilkesi oluşturmayı](../protect/compliance-policy-create-android.md)öğrenin.

### <a name="text-protocol-allowed-from-managed-apps----1414050----"></a>Yönetilen uygulamalardan izin verilen metin Protokolü <!-- 1414050  -->

Intune uygulama SDK 'Sı tarafından yönetilen uygulamalar SMS mesajları gönderebilir.


### <a name="app-install-report-updated-to-include-install-pending-status----1249446---"></a>Uygulama yüklemesi raporu, yüklemeyi bekleyen durumu içerecek şekilde güncelleştirildi <!-- 1249446 -->  

**İstemci uygulamaları** Iş yükünde **uygulama** listesi aracılığıyla her bir uygulama için erişilebilen **uygulama yüklemesi durum** raporu, artık kullanıcılar ve cihazlar için bir **yüklemesi bekleyen** sayısı içerir.

### <a name="ios-11-app-inventory-api-for-mobile-threat-detection----1391759---"></a>Mobile Threat Detection için iOS 11 uygulama envanteri API 'SI <!-- 1391759 -->

Intune, kişisel ve şirkete ait cihazlardan uygulama envanter bilgilerini toplayıp Lookout for Work gibi mobil tehdit algılama (MTD) sağlayıcılarının kullanımına sunar. İOS 11 + cihazlarındaki kullanıcılardan bir uygulama envanteri toplayabilirsiniz.

**Uygulama envanteri**  
Şirkete ait iOS 11 + ve kişisel cihazlarındaki envanterler MTD hizmet sağlayıcınıza gönderilir. Uygulama envanterindeki veriler şunları içerir:

- Uygulama Kimliği
- Uygulama sürümü
- Uygulama kısa sürümü
- Uygulama adı
- Uygulama paketi boyutu
- Uygulama dinamik boyutu
- Uygulama doğrulanıp doğrulanmadı
- Uygulama yönetiliyor veya değil

### <a name="migrate-hybrid-mdm-users-and-devices-to-intune-standalone----1463747-wnready---"></a>Karma MDM kullanıcıları ve cihazlarını tek başına Intune 'a geçirme <!-- 1463747 wnready -->
Artık kullanıcıları ve cihazlarını karma MDM 'den Intune 'a taşımaya yönelik yeni süreçler ve araçlar Azure portal, aşağıdaki görevleri gerçekleştirebilirsiniz:
- Configuration Manager konsolundan ilke ve profilleri Azure portal Intune 'a kopyalama
- Kullanıcıların bir alt kümesini Azure portal Intune 'a taşıyın, Rest 'i karma MDM 'de tutun
- Cihazları yeniden kaydetmeniz gerekmeden Azure portal Intune 'a geçirme

Ayrıntılar için bkz. [karma MDM kullanıcıları ve cihazlarını tek başına Intune 'A geçirme](https://docs.microsoft.com/sccm/mdm/deploy-use/migrate-hybridmdm-to-intunesa).

### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Şirket içi Exchange Connector yüksek kullanılabilirlik desteği  <!-- 676614 -->
Exchange Connector, belirtilen Istemci erişim sunucusu (CAS) kullanarak Exchange 'e bir bağlantı oluşturduktan sonra, bağlayıcının artık diğer CASs 'leri bulma özelliği vardır. Birincil CA 'LAR kullanılamaz hale gelirse, birincil CA 'LAR kullanılabilir hale gelene kadar bağlayıcı, varsa, başka bir CA 'ya yük devreder. Ayrıntılar için bkz. Şirket [Içi Exchange Connector yüksek kullanılabilirlik desteği](../protect/exchange-connector-install.md#on-premises-intune-exchange-connector-high-availability-support).

### <a name="remotely-restart-ios-device-supervised-only----1424595---"></a>İOS cihazını uzaktan yeniden Başlat (yalnızca denetimli) <!-- 1424595 -->

Artık bir cihaz eylemi kullanarak yeniden başlatmak için denetimli bir iOS 10.3 + cihazını tetikleyebilirsiniz. Cihaz yeniden başlatma eylemini kullanma hakkında daha fazla bilgi için bkz. [Intune ile cihazları uzaktan yeniden başlatma](../remote-actions/device-restart.md).

> [!Note]
> Bu komut denetimli cihazlar ve **Cihaz kilidi** erişim hakkı gerektirir. Cihaz hemen yeniden başlatılır. Geçiş kodu-kilitli iOS cihazları, yeniden başlatmadan sonra bir Wi-Fi ağına yeniden katılmaz; yeniden başlattıktan sonra, sunucuyla iletişim kuramayabilirler.

### <a name="single-sign-on-support-for-ios----1333645---"></a>İOS için çoklu oturum açma desteği <!-- 1333645 -->  

İOS kullanıcıları için çoklu oturum açma kullanabilirsiniz. Çoklu oturum açma yükünde Kullanıcı kimlik bilgilerini aramak için kodlanmış iOS uygulamaları, bu yük yapılandırma güncelleştirmesiyle çalışır. Birincil adı ve bölgeyi yapılandırmak için UPN ve Intune cihaz KIMLIĞINI de kullanabilirsiniz. Ayrıntılar için bkz. [iOS Için Intune cihaz çoklu oturum açma](../configuration/ios-device-features-settings.md#single-sign-on).

### <a name="add-find-my-iphone-for-personal-devices---1427287--"></a>Kişisel cihazlar için "iPhone 'umu bul" Ekle <!--1427287-->
Artık iOS cihazlarının Etkinleştirme Kilidi açık olup olmadığını görebilirsiniz. Bu özellik daha önce klasik portalda Intune 'da bulunabilir.

### <a name="remotely-lock-managed-macos-device-with-intune----1437691---"></a>Yönetilen macOS cihazını Intune ile uzaktan kilitleme <!-- 1437691 -->

Kayıp bir macOS cihazını kilitleyebilir ve 6 basamaklı bir kurtarma PIN kodu ayarlayabilirsiniz. Kilitlendiğinde, **cihaza genel bakış** dikey penceresi, başka bir cihaz eylemi gönderilene kadar PIN 'i görüntüler.

Daha fazla bilgi için bkz. [Intune ile yönetilen cihazları uzaktan kilitleme](../remote-actions/device-remote-lock.md).

### <a name="new-scep-profile-details-supported----1559808---"></a>Yeni SCEP profili ayrıntıları destekleniyor <!-- 1559808 -->

Yöneticiler artık Windows, iOS, macOS ve Android platformlarında bir SCEP profili oluştururken ek ayarlar ayarlayabiliyor.  Yöneticiler ıMEı, seri numarası veya konu adı biçiminde e-posta dahil ortak ad ayarlayabilir.

<!-- #### Update to what device details your company may see -1616825
The Company Portal app for Android can now use geofencing to protect access to company resources. It uses network details such as IP address, default gateway address, and Domain Name System (DNS) to determine whether to allow access to protected company resources. -->

### <a name="retain-data-during-a-factory-reset----1588489---"></a>Fabrika Sıfırlaması sırasında verileri koruma  <!--1588489 -->
Windows 10 sürüm 1709 ve üstünü fabrika ayarlarına sıfırlarken yeni bir özellik mevcuttur. Yöneticiler, cihaz kaydı ve diğer sağlanan verilerin bir cihazda fabrika sıfırlaması aracılığıyla korunup korunmadığını belirtebilir.

Aşağıdaki veriler bir fabrika sıfırlaması aracılığıyla tutulur:
- Cihazla ilişkili kullanıcı hesapları
- Makine durumu (etki alanına katılma, Azure Active Directory katılmış)
- MDM kaydı
- OEM tarafından yüklenen uygulamalar (mağaza ve Win32 uygulamaları)
- Kullanıcı profili
- Kullanıcı profili dışındaki Kullanıcı verileri
- Kullanıcı oturum açma

Aşağıdaki veriler korunmaz:
- Kullanıcı dosyaları
- Kullanıcı tarafından yüklenen uygulamalar (mağaza ve Win32 uygulamaları)
- Varsayılan olmayan cihaz ayarları


### <a name="window-10-update-ring-assignments-are-displayed----1621837---"></a>Windows 10 güncelleştirme halkası atamaları görüntülenir <!-- 1621837 -->
**Sorun giderirken,** görüntülediğiniz Kullanıcı için Windows 10 güncelleştirme halkalarının atamalarını görebilirsiniz.  

### <a name="windows-defender-advanced-threat-protection-reporting-frequency-settings-----1455974----"></a>Windows Defender Gelişmiş tehdit koruması raporlama sıklığı ayarları  <!-- 1455974  -->
Windows Defender Gelişmiş tehdit koruması (WDADTP) hizmeti, yöneticilerin yönetilen cihazlar için raporlama sıklığını yönetmesine olanak tanır. Yeni **hızlama telemetri raporlama sıklığı** seçeneğiyle, wdadtp verileri ve değerlendirir risklerini daha sık toplar. Raporlama için varsayılan değer hız ve performansı iyileştirir. Raporlama sıklığını artırma, yüksek riskli cihazlar için değerli olabilir. Bu ayar, **cihaz yapılandırmalarında** **Windows Defender ATP** profilinde bulunabilir.

### <a name="audit-updates----1412961---"></a>Güncelleştirmeleri denetle <!-- 1412961 -->  
Intune denetimi, Intune ile ilgili değişiklik işlemlerinin bir kaydını sağlar.  Tüm oluşturma, güncelleştirme, silme ve uzak görev işlemleri yakalanır ve bir yıl boyunca saklanır.  Azure portal, her iş yükünde son 30 günün denetim verileri için bir görünüm sağlar ve filtrelenebilir.  Karşılık gelen Graph API, geçen yıl için depolanan denetim verilerinin alınmasına izin verir.

Denetim, **izleyici** grubu altında bulunur. Her iş yükü için bir **Denetim günlükleri** menü öğesi vardır.

### <a name="company-portal-app-for-macos-is-available---1541700--"></a>MacOS için Şirket Portalı uygulaması kullanılabilir <!--1541700-->
MacOS üzerindeki Intune Şirket Portalı, kullanıcılarınızın kaydolduğu tüm cihazlar için ihtiyaç duyduğu tüm bilgileri ve Uyumluluk bildirimlerini düzgün bir şekilde görüntülemesi için iyileştirilmiş güncelleştirilmiş bir deneyimle sahiptir. Ayrıca, Intune Şirket Portalı bir cihaza dağıtıldıktan sonra, macOS için Microsoft otomatik güncelleştirme 'nin güncelleştirme sağlaması gerekir. MacOS için yeni Intune Şirket Portalı, macOS cihazından Intune Şirket Portalı Web sitesinde oturum açarak indirebilirsiniz.

### <a name="microsoft-planner-is-now-part-of-the-mobile-app-management-mam-list-of-approved-apps-----1248473---"></a>Microsoft Planner artık onaylanan uygulamaların mobil uygulama yönetimi (MAM) listesinin bir parçasıdır  <!-- 1248473 -->
İOS ve Android için Microsoft Planner uygulaması artık mobil uygulama yönetimi (MAM) için onaylanan uygulamaların bir parçasıdır. Uygulama, tüm kiracılara Azure portal Intune Uygulama Koruması dikey penceresinde yapılandırılabilir.
- [Onaylanan uygulamalar mam listesi](https://www.microsoft.com/cloud-platform/microsoft-intune-apps)hakkında daha fazla bilgi edinin.

### <a name="per-app-vpn-requirement-update-frequency-on-ios-devices------1547061---"></a>İOS cihazlarında uygulama başına VPN gereksinimi güncelleştirme sıklığı   <!-- 1547061 -->  
Yöneticiler artık iOS cihazlarındaki uygulamalar için uygulama başına VPN gereksinimlerini kaldırabilir; Etkilenen cihazlar, genellikle 15 dakika içinde gerçekleşen bir sonraki Intune iadeden sonra olur.  

### <a name="support-for-system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Exchange Connector için System Center Operations Manager yönetim paketi desteği <!-- 885457 -->
Exchange Connector için System Center Operations Manager yönetim paketi artık Exchange Connector günlüklerini ayrıştırmanıza yardımcı olmak için kullanılabilir. Bu özellik, sorunları gidermeniz gerektiğinde hizmeti izlemenin farklı yollarını sağlar.

### <a name="co-management-for-windows-10-devices-----1243445---"></a>Windows 10 cihazları için ortak yönetim  <!-- 1243445 -->
Ortak yönetim, geleneksel ve modern yönetime köprü sağlayan bir çözümdür ve bir aşamalı yaklaşım kullanarak geçişi yapmak için bir yol sağlar. Ortak yönetim, temel olarak Windows 10 cihazlarının Configuration Manager ve Microsoft Intune tarafından eşzamanlı olarak yönetildiği ve Active Directory (AD) ve Azure Active Directory (Azure AD) ile birleştirilme çözümüdür.  Bu yapılandırma, size zaman içinde modernleştirin için bir yol sağlar. Bu, tümünü bir kez taşıyabilmeniz halinde kuruluşunuz için en uygun hızdaki bir yoldur.  

### <a name="restrict-windows-enrollment-by-os-version----245498---"></a>Windows kaydını işletim sistemi sürümüne göre kısıtla <!-- 245498 -->
Bir Intune Yöneticisi olarak, artık cihaz kayıtları için Windows 10 ' un en düşük ve en yüksek sürümünü belirtebilirsiniz. Bu kısıtlamaları **Platform yapılandırması** dikey penceresinde ayarlayabilirsiniz.

Intune, Windows 8.1 bilgisayarları ve telefonları kaydetmeyi desteklemeye devam edecektir. Ancak, yalnızca Windows 10 sürümleri minimum ve maksimum limitlerle ayarlanabilir. 8,1 cihazların kaydına izin vermek için, en düşük sınırı boş bırakın.

### <a name="alerts-for-windows-autopilot-unassigned-devices-----1631236---"></a>Windows AutoPilot atanmamış cihazlar için uyarılar  <!-- 1631236 -->
**Microsoft Intune** > **cihaz kaydı** > **genel bakış** sayfasında Windows Autopilot atanmamış cihazlar için yeni bir uyarı vardır. Bu uyarı, AutoPilot programından kaç cihaza AutoPilot dağıtım profillerinin atanmadığı gösterilmektedir. Profil oluşturmak ve bunları atanmamış cihazlara atamak için uyarıdaki bilgileri kullanın. Uyarıya tıkladığınızda, Windows AutoPilot cihazlarının tam listesini ve bunlarla ilgili ayrıntılı bilgileri görürsünüz. Daha fazla bilgi için bkz. [Windows Autopilot Dağıtım programını kullanarak Windows cihazlarını kaydetme](../enrollment/enrollment-autopilot.md).


### <a name="refresh-button-for-devices-list-------1333581---"></a>Cihazlar listesi için yenileme düğmesi    <!-- 1333581 -->
Cihaz listesi otomatik olarak yenilenmediğinden, listede görüntülenen cihazları güncelleştirmek için yeni Yenile düğmesini kullanabilirsiniz.

### <a name="support-for-symantec-cloud-certification-authority-ca-----1333638---"></a>Symantec Cloud sertifika yetkilisi (CA) desteği  <!-- 1333638 -->    
Intune artık Symantec Cloud CA 'yı desteklemektedir. Bu, Intune sertifika bağlayıcısının Symantec bulut CA 'dan Intune ile yönetilen cihazlara PKCS sertifikaları vermesine olanak tanır. Intune sertifika bağlayıcısını zaten Microsoft sertifika yetkilisi (CA) ile kullanıyorsanız, Symantec CA desteğini eklemek için mevcut Intune sertifika Bağlayıcısı kurulumunu kullanabilirsiniz.

### <a name="new-items-added-to-device-inventory-----1404455---"></a>Cihaz envanterine eklenen yeni öğeler   <!--1404455 -->
Aşağıdaki yeni öğeler artık [Kayıtlı cihazlar tarafından alınan envanterde](../remote-actions/device-inventory.md)kullanılabilir:

- Wi-Fi MAC adresi
- Toplam depolama alanı
- Toplam boş alan
- MEıD
- Abone taşıyıcısı

### <a name="set-access-for-apps-by-minimum-android-security-patch-on-the-device---1278463---"></a>Cihazda en düşük Android güvenlik düzeltme ekine göre uygulamalar için erişimi ayarla<!-- 1278463 -->   
Yönetici, yönetilen bir hesap altındaki yönetilen bir uygulamaya erişim kazanmak için cihazda yüklü olması gereken en düşük Android güvenlik düzeltme ekini tanımlayabilir.

> [!Note]  
> Bu özellik yalnızca Android 6.0 + cihazlarda Google tarafından yayınlanan güvenlik düzeltme eklerini kısıtlar.

### <a name="app-conditional-launch-support----1193313---"></a>Uygulama-koşullu başlatma desteği <!-- 1193313 -->
BT yöneticileri artık uygulama başlatıldığında bir geçiş kodunu mobil uygulama yönetimi (MAM) aracılığıyla bir sayısal PIN yerine zorlamak için Azure Yönetim Portalı aracılığıyla bir gereksinim ayarlayabilir. Yapılandırıldıysa, kullanıcının MAM özellikli uygulamalara erişim almadan önce istendiğinde bir geçiş kodu ayarlaması ve kullanması gerekir. Bir geçiş kodu, en az bir özel karakter veya büyük/küçük harflerden oluşan sayısal bir PIN olarak tanımlanır. Intune 'un bu sürümü **yalnızca iOS 'ta**bu özelliği etkinleştirir. Intune, sayısal PIN 'e benzer bir şekilde geçiş kodunu destekler, en düşük uzunlukta bir değer ayarlar ve tekrar karakter ve sıralara izin verir. Bu özellik, Intune uygulama SDK 'sını, geçiş kodu ayarlarının hedeflenen uygulamalarda zorlanmasını sağlamak için bu özelliğe yönelik kodla bütünleştirmek üzere uygulamaların (yani, WXP, Outlook, Managed Browser, Yammer) katılımını gerektirir.

### <a name="app-version-number-for-line-of-business-in-device-install-status-report----1233999---"></a>Cihaz yüklemesi durum raporundaki iş kolu için uygulama sürüm numarası <!-- 1233999 -->
Bu sürümde, cihaz yüklemesi durumu raporu iOS ve Android için iş kolu uygulamaları için uygulama sürüm numarasını görüntüler. Uygulamalarınızın sorunlarını gidermek veya güncel olmayan uygulama sürümlerini çalıştıran cihazları bulmak için bu bilgileri kullanabilirsiniz.

### <a name="admins-can-now-configure-the-firewall-settings-on-a-device-using-a-device-configuration-profile----951708---"></a>Yöneticiler artık bir cihaz yapılandırma profili kullanarak bir cihazda güvenlik duvarı ayarlarını yapılandırabilir <!-- 951708 -->   
Yöneticiler cihazların güvenlik duvarını açabilir ve ayrıca etki alanı, özel ve ortak ağlar için çeşitli protokoller yapılandırabilir.  Bu güvenlik duvarı ayarları "Endpoint Protection" profilinde bulunabilir.

### <a name="windows-defender-application-guard-helps-protect-devices-from-untrusted-websites-as-defined-by-your-organization----958257---"></a>Windows Defender Application Guard, kuruluşunuz tarafından tanımlanan güvenilmeyen Web sitelerinden cihazları korumanıza yardımcı olur <!-- 958257 -->   
Yöneticiler, siteleri "güvenilir" veya "Kurumsal" olarak, bir Windows Information Protection iş akışı veya cihaz yapılandırmalarında yeni "ağ sınırı" profili ile tanımlayabilir. Bunlar Microsoft Edge ile görüntülenecekse, bir Hyper-V sanal bilgisayarındaki bir tarayıcıda bunun yerine 64 bitlik bir Windows 10 cihazının güvenilir ağ sınırında listelenmemiş tüm siteler açılır.

Application Guard, "Endpoint Protection" profilinde cihaz yapılandırma profillerinde bulunabilir. Yöneticiler buradan, sanallaştırılmış tarayıcı ile konak makine, güvenilir olmayan siteler ve güvenilen siteler arasında etkileşim yapılandırabilir ve sanallaştırılmış tarayıcıda oluşturulan verileri depolar. Application Guard 'ı bir cihazda kullanmak için, önce bir ağ sınırının yapılandırılması gerekir. Bir cihaz için yalnızca bir ağ sınırı tanımlamak önemlidir.  

### <a name="windows-defender-application-control-on-windows-10-enterprise-provides-mode-to-trust-only-authorized-apps----1031096---"></a>Windows 10 Enterprise 'da Windows Defender uygulama denetimi, yalnızca yetkili uygulamalara güvenmek için mod sağlar <!-- 1031096 -->    
Her gün oluşturulan binlerce yeni kötü amaçlı dosya sayesinde, virüsten koruma imza tabanlı algılama kullanılması, kötü amaçlı yazılımlara karşı daha uygun bir savunma sunmayabilir. Windows 10 Enterprise 'da Windows Defender uygulama denetimi 'ni kullanarak, cihaz yapılandırmasını, uygulamaların bir virüsten koruma veya başka bir güvenlik çözümü tarafından engellenmediği bir moddan, işletim sisteminin yalnızca tarafından yetkilendirilen uygulamalara güvendiği bir moda değiştirebilirsiniz. Kuruluşunuz. Windows Defender uygulama denetimindeki uygulamalara güven atarsınız.

Intune 'u kullanarak, uygulama denetim ilkelerini "yalnızca denetim" modunda veya zorunlu modda yapılandırabilirsiniz. Uygulamalar, "yalnızca denetim" modunda çalıştırıldığında engellenmemektedir. "Yalnızca denetim" modu tüm olayları yerel istemci günlüklerine kaydeder. Ayrıca, yalnızca Windows bileşenlerinin ve Microsoft Store uygulamalarının çalışmasına izin verilip verilmeyeceğini veya Intelligent Security Graph tarafından tanımlanan iyi itibarlı ek uygulamaların çalışmasına izin verilip verilmeyeceğini de yapılandırabilirsiniz.

### <a name="window-defender-exploit-guard-is-a-new-set-of-intrusion-prevention-capabilities-for-windows-10----1063615---"></a>Windows Defender Exploit Guard, Windows 10 için yeni bir yetkisiz giriş önleme özellikleri kümesidir <!-- 1063615 -->   
Windows Defender Exploit Guard, uygulamaların kötüye kullanılabilirlik azaltmak için özel kurallar içerir, makro ve betik tehditlerini önler, ağ bağlantılarını alt sayıp adreslerine karşı otomatik olarak engeller ve fidye ve bilinmeyen verileri güvenli hale getirebilirsiniz tehditleri. Windows Defender Exploit Guard aşağıdaki bileşenlerden oluşur:

- **Saldırı yüzeyi azaltma** , makro, komut dosyası ve e-posta tehditlerini engellemenizi sağlayan kurallar sağlar.
- **Denetlenen klasör erişimi** , korumalı klasörlerin içeriğine erişimi otomatik olarak engeller.
- **Ağ filtresi** , herhangi bir uygulamadan giden bağlantıyı düşük rep IP/etki alanına engelliyor
- **Yararlanma koruması** , bir uygulamayı kötüye kullanma olanağı sağlamak için kullanılabilecek bellek, denetim akışı ve ilke kısıtlamaları sağlar.

### <a name="manage-powershell-scripts-in-intune-for-windows-10-devices----790537---"></a>Windows 10 cihazları için Intune 'da PowerShell betiklerini yönetme <!-- 790537 -->

Intune yönetim uzantısı, Windows 10 cihazlarında çalıştırmak için Intune 'da PowerShell betiklerini karşıya yüklemenize olanak sağlar. Uzantı Windows 10 mobil cihaz yönetimi (MDM) özelliklerini tamamlar ve modern yönetime geçiş yapmayı kolaylaştırır. Ayrıntılar için bkz. [Windows 10 cihazlar Için Intune 'Da PowerShell betiklerini yönetme](../apps/intune-management-extension.md).

### <a name="new-device-restriction-settings-for-windows-10---------1308850---"></a>Windows 10 için yeni cihaz kısıtlama ayarları      <!-- 1308850 -->
- Mesajlaşma (yalnızca mobil)-sınama veya MMS iletilerini devre dışı bırak
- Parola-kimlik doğrulaması için FIPS ve Windows Hello cihazlarının ikincil cihazlarının kullanımını etkinleştirme 
- Eski uygulamalar için GDI ölçeklendirmeyi açma veya kapatma ayarlarını görüntüleme

### <a name="windows-10-kiosk-mode-device-restrictions----1308872---"></a>Windows 10 bilgi noktası modu cihaz kısıtlamaları <!-- 1308872 -->   
Windows 10 cihaz kullanıcılarını bilgi noktası moduna kısıtlayabilir, bu da kullanıcıları önceden tanımlanmış bir uygulamalar kümesiyle sınırlandırır.  Bunu yapmak için bir Windows 10 cihaz kısıtlama profili oluşturun ve bilgi noktası ayarlarını ayarlayın.

Bilgi noktası modu iki modu destekler: **tek uygulama** (bir kullanıcının yalnızca bir uygulama çalıştırmasına izin verir) veya **birden çok uygulama** (bir uygulama kümesine erişime izin verir).  Kullanıcı hesabını ve desteklenen uygulamaları belirleyen cihaz adını tanımlarsınız.  Kullanıcı oturum açtığında, tanımlanan uygulamalarla sınırlı olurlar.  Daha fazla bilgi edinmek için bkz. [atanan](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp). 

Bilgi noktası modu şunları gerektirir:

- Intune, MDM yetkilisi olmalıdır.
- Uygulamalar, hedef cihaza zaten yüklenmiş olmalıdır.
- Cihazın [düzgün sağlanması](https://docs.microsoft.com/windows/configuration/set-up-a-kiosk-for-windows-10-for-desktop-editions)gerekiyor.

### <a name="new-device-configuration-profile-for-creating-network-boundaries----1311967---"></a>Ağ sınırları oluşturmak için yeni cihaz yapılandırma profili <!-- 1311967 -->   
Diğer cihaz yapılandırma profilleriniz ile **ağ sınırı** adlı yeni bir cihaz yapılandırma profili bulunabilir. Şirket ve güvenilir olarak kabul edilmesini istediğiniz çevrimiçi kaynakları tanımlamak için bu profili kullanın. *Cihazda Windows* Defender Application Guard ve Windows Information Protection 'nin kullanılabilmesi için bir ağ sınırı tanımlamanız gerekir. Her cihaz için yalnızca bir ağ sınırı tanımlamak önemlidir.

Güvenilen olarak kabul edilmesini istediğiniz kurumsal bulut kaynaklarını, IP adresi aralıklarını ve iç proxy sunucularını tanımlayabilirsiniz. Tanımlandıktan sonra ağ sınırı, Windows Defender Application Guard ve Windows Information Protection gibi diğer özellikler tarafından tüketilebilir.

### <a name="two-additional-settings-for-windows-defender-antivirus----1338409---"></a>Windows Defender virüsten koruma için iki ek ayar <!-- 1338409 -->  
**Dosya Engelleme düzeyi**

| | |
|---|---|
| Yapılandırılmadı | **Yapılandırılmadı** , varsayılan Windows Defender virüsten koruma engelleme düzeyini kullanır ve meşru dosyaları algılama riskini arttırmadan güçlü algılama sağlar. |
| Yüksek | **Yüksek** , güçlü bir algılama düzeyi uygular.
| Yüksek +  | **High +** , istemci performansını etkileyebilecek ek koruma ölçüleriyle yüksek düzey sağlar.
| Sıfır tolerans  | **Sıfır tolerans** tüm bilinmeyen yürütülebilir dosyaları engeller. |

**Büyük olasılıkla yüksek** olarak ayarlandığında bazı meşru dosyaların algılanmasına neden olabilir.
Dosya engelleme düzeyini **Yapılandırılmadı**, varsayılan olarak ayarlamanızı öneririz.

**Bulut tarafından dosya tarama için zaman aşımı uzantısı**  

| | |
|--|--|
| Saniye sayısı (0-50) | Windows Defender virüsten koruma 'nın buluttan bir sonuç beklerken bir dosyayı engellemesini gerektiren en uzun süreyi belirtin. Varsayılan miktar 10 saniyedir: burada belirtilen ek saat (50 saniyeye kadar) bu 10 saniyeye eklenir. Çoğu durumda, tarama en büyük boyuttan çok daha az zaman alır. Sürenin uzatılması, bulutun şüpheli dosyaları kapsamlı bir şekilde araştırmalarını sağlar. Bu ayarı etkinleştirmenizi ve en az 20 ek saniye belirtmenizi öneririz. |

### <a name="citrix-vpn-added-for-windows-10-devices----1512457---"></a>Windows 10 cihazları için Citrix VPN eklendi <!-- 1512457 -->  
Windows 10 cihazları için Citrix VPN 'i yapılandırabilirsiniz. Windows 10 ve üzeri için bir VPN yapılandırırken, **temel VPN** dikey penceresinde *bir bağlantı türü SEÇIN* listesinden Citrix VPN ' yi seçebilirsiniz.

> [!Note]
> İOS ve Android için Citrix yapılandırması var.

### <a name="wi-fi-connections-support-pre-shared-keys-on-ios----1550823---"></a>Wi-Fi bağlantıları iOS 'ta önceden paylaşılan anahtarları destekler <!-- 1550823 -->
Müşteriler, iOS cihazlarda WPA/WPA2 Kişisel bağlantıları için önceden paylaşılan anahtarları (PSK) kullanmak üzere Wi-Fi profillerini yapılandırabilir. Bu profiller, cihaz Intune 'a kaydolduğunda kullanıcının cihazına gönderilir.

Profil cihaza itildiğinde, sonraki adım profil yapılandırmasına bağlıdır.  Otomatik olarak bağlan olarak ayarlandıysa, ağın bir sonraki ihtiyacı olduğunda bunu yapar.  Profil el ile bağlandığı zaman, kullanıcının bağlantıyı el ile etkinleştirmeleri gerekir.  

### <a name="access-to-managed-app-logs-for-ios----1469920---"></a>İOS için yönetilen uygulama günlüklerine erişim <!-- 1469920 -->
Managed Browser yüklü olan son kullanıcılar artık Microsoft tarafından yayımlanan tüm uygulamaların yönetim durumunu görüntüleyebilir ve yönetilen iOS uygulamalarının sorunlarını gidermeye yönelik Günlükler gönderebilir.

İOS cihazındaki Managed Browser sorun giderme modunu nasıl etkinleştireceğinizi öğrenin, bkz. [iOS üzerinde Managed Browser kullanarak yönetilen uygulama günlüklerine erişme](../apps/app-configuration-managed-browser.md#how-to-access-to-managed-app-logs-using-the-managed-browser-on-ios).

### <a name="improvements-to-device-setup-workflow-in-the-company-portal-for-ios-in-version-290----1417174---"></a>2\.9.0 sürümündeki iOS için Şirket Portalı cihaz kurulumu iş akışında iyileştirmeler <!-- 1417174 -->

İOS için Şirket Portalı App 'te cihaz kurulumu iş akışı geliştirildi. Dil daha kolay ve ekranları mümkün olduğunca birleştirdik. Bu dil, kurulum metni boyunca şirket adınızı kullanarak şirketinize daha özeldir. Bu güncelleştirilmiş iş akışını [uygulama arabirimindeki Yenilikler sayfasında](../whats-new-app-ui.md)görebilirsiniz.


### <a name="user-entity-contains-latest-user-data-in-data-warehouse-data-model----1544273---"></a>Kullanıcı varlığı, veri ambarı veri modelinde en son kullanıcı verilerini içerir <!-- 1544273 -->
Intune veri ambarı veri modelinin ilk sürümü yalnızca son, geçmiş Intune verilerini içerir. Rapor üreticileri bir kullanıcının geçerli durumunu yakalayamaz. Bu güncelleştirmede, **Kullanıcı varlığı** en son kullanıcı verileriyle doldurulur.

<!-- ########################## -->
## <a name="october-2017"></a>2017 Ekim

### <a name="ios-and-android-line-of-business-app-version-number-is-visible----1380712---"></a>iOS ve Android iş kolu uygulaması sürüm numarası görünür <!-- 1380712 -->

Intune 'da bulunan uygulamalar artık iOS ve Android iş kolu uygulamaları için sürüm numarasını görüntüler. Numara, uygulama listesinde ve uygulamaya genel bakış dikey penceresinde Azure portal görüntülenir. Son kullanıcılar uygulama numarasını Şirket Portalı uygulamasında ve web portalında görebilirler.

__Tam sürüm numarası__ Tam sürüm numarası, uygulamanın belirli bir sürümünü tanımlar. Sayı _Sürüm_(_derleme_) olarak görünür. Örneğin, 2.2 (2.2.17560800)

Tam sürüm numarasının iki bileşeni vardır:

- **Sürüm**  
  Sürüm numarası, uygulamanın insan tarafından okunabilen serbest bırakma numarasıdır. Bu, son kullanıcılar tarafından uygulamanın farklı sürümlerini belirlemek için kullanılır.

- **Yapı numarası**  
  Yapı numarası, uygulama algılamasında ve uygulamayı programlı bir şekilde yönetmek için kullanılabilecek dahili bir sayıdır. Yapı numarası, koddaki değişikliklere başvuran uygulamanın bir yinelemesini ifade eder.

[Microsoft Intune uygulama SDK 'sını kullanmaya başlama](../developer/app-sdk-get-started.md#line-of-business-app-version-numbers)bölümünde sürüm numaraları ve iş kolu uygulamaları geliştirme hakkında daha fazla bilgi edinin.

### <a name="device-and-app-management-integration----677972---"></a>Cihaz ve uygulama yönetimi tümleştirmesi <!-- 677972 -->   
Artık Intune 'un mobil cihaz yönetimi (MDM) ve mobil uygulama yönetimi (MAM) Azure portal 'tan erişilebilir olduğuna göre, Intune, BT Yöneticisi deneyimini uygulama ve cihaz yönetimi ile tümleştirmeyle başlamıştır. Bu değişiklikler, cihaz ve uygulama yönetimi deneyiminizi basitleştirmek için tasarlanmıştır.

[Intune destek ekibi blogu](https://blogs.technet.microsoft.com/intunesupport/2017/09/19/support-tip-setting-up-communication-between-mam-managed-and-mdm-managed-apps/)'NDA duyurulan MDM ve Mam değişiklikleri hakkında daha fazla bilgi edinin.

### <a name="new-enrollment-alerts-for-apple-devices----1471790---"></a>Apple cihazları için yeni kayıt uyarıları <!-- 1471790 -->
Kayıt için genel bakış sayfasında, BT yöneticileri için Apple cihazlarının yönetimiyle ilgili yararlı uyarılar gösterilir. Apple MDM anında iletme sertifikasının süresi dolduğunda veya süresi dolduğunda uyarılar Genel Bakış sayfasında görünür; Aygıt Kayıt Programı belirtecinin süresi dolduğunda veya süresi zaten dolmuşsa; Aygıt Kayıt Programı, ve ' de atanmamış cihazlar olduğunda.

### <a name="support-token-replacement-for-app-configuration-without-device-enrollment----1080364---"></a>Cihaz kaydı olmadan uygulama yapılandırması için belirteç değişimini destekleme <!-- 1080364 -->

Kayıtlı olmayan cihazlarda uygulamalar için uygulama yapılandırmalarında dinamik değerler için belirteçleri kullanabilirsiniz. Daha fazla bilgi için bkz. [cihaz kaydı olmadan yönetilen uygulamalar için uygulama yapılandırma Ilkeleri ekleme](../apps/app-configuration-policies-managed-app.md).

### <a name="updates-to-the-company-portal-app-for-windows-10---1299474--"></a>Windows 10 için Şirket Portalı uygulamasına yönelik güncelleştirmeler <!--1299474-->
Windows 10 için Şirket Portalı uygulamasındaki ayarlar sayfası, ayarların ve hedeflenen Kullanıcı eylemlerinin tüm ayarlar arasında daha tutarlı olmasını sağlamak üzere güncelleştirilmiştir. Ayrıca, diğer Windows uygulamalarının düzeniyle eşleşecek şekilde güncelleştirilmiştir. [Uygulama kullanıcı arabirimindeki](../whats-new-app-ui.md) Yenilikler sayfasında resimleri daha önce/sonra bulabilirsiniz.

### <a name="inform-end-users-what-device-information-can-be-seen-for-windows-10-devices---1337920--"></a>Son kullanıcılara Windows 10 cihazlarda hangi cihaz bilgilerinin görülebileceği hakkında bilgi verme <!--1337920-->
Windows 10 için Şirket Portalı uygulamasındaki cihaz ayrıntıları ekranına **sahiplik türü** ekledik. Bu, kullanıcıların doğrudan bu sayfadan Intune Son Kullanıcı belgelerinden gizlilik hakkında daha fazla bilgi bulmasına olanak tanır. Ayrıca, bu bilgileri **hakkında** ekranında bulabilirsiniz.

### <a name="feedback-prompts-for-the-company-portal-app-for-android---1165249--"></a>Android için Şirket Portalı uygulamasına yönelik geri bildirim istemleri <!--1165249-->
Android için Şirket Portalı uygulaması artık Son Kullanıcı geri bildirimi istiyor. Bu geri bildirim doğrudan Microsoft 'a gönderilir ve son kullanıcılara uygulamayı genel Google Play deposunda gözden geçirmek için bir fırsat sağlar. Geri bildirim gerekli değildir ve kullanıcılar uygulamayı kullanmaya devam edebilmek için kolayca kapatılabilir.

<!-- #### Update to what device details an organization can see 1616825
The Company Portal app for Android can now use geofencing to protect access to company resources. It uses network details such as IP address, default gateway address, and Domain Name System (DNS) to determine whether to allow access to protected company resources.-->

### <a name="helping-your-users-help-themselves-with-the-company-portal-app-for-android----1573324-1573150-1558616-1564878---"></a>Kullanıcılarınızın Android için Şirket Portalı uygulamasına yardımcı olma <!-- 1573324, 1573150, 1558616, 1564878 -->

Android için Şirket Portalı uygulaması, son kullanıcıların yeni kullanım durumlarını anlamaları ve mümkün olduğunda kendi kendine çözmelerine yardımcı olmaya yönelik yönerge eklemiştir.
- Son kullanıcılar, eklemesi izin verilen en fazla cihaz sayısına ulaştıysa bir cihazı kaldırmak için [Azure Active Directory portalına](https://account.activedirectory.windowsazure.com/r/#/profile) kılavuzluk eder.
- Son kullanıcılara, [Samsung KNOX cihazlarında Etkinleştirme hatalarını çözmesine](https://go.microsoft.com/fwlink/?linkid=859718) veya [güç tasarrufu modunu kapatmaya](/intune-user-help/power-saving-mode-android)yardımcı olmak üzere izlenecek adımlar verilir. Bu çözümlerin hiçbiri sorunu çözmezse, [günlüklerin Microsoft 'a nasıl gönderileceği](/intune-user-help/send-logs-to-microsoft-android)hakkında bir açıklama sağlıyoruz.

### <a name="new-resolve-action-available-for-android-devices----1583480---"></a>Android cihazlar için yeni ' Çözümle ' eylemi kullanılabilir <!-- 1583480 -->

Android için Şirket Portalı uygulaması, _cihaz ayarlarını Güncelleştir_ sayfasında bir ' Çözümle ' eylemi tanıtıyor. Bu seçeneğin belirlenmesi, son kullanıcıyı cihazının uyumsuz olmasına neden olan ayarı doğrudan ele alır. Android için Şirket Portalı uygulaması şu anda bu eylemi [cihaz geçiş kodu](/intune-user-help/set-your-pin-or-password-android), [USB hata ayıklama](/intune-user-help/you-need-to-turn-off-usb-debugging-android)ve [Bilinmeyen kaynaklar](/intune-user-help/you-need-to-turn-off-unknown-sources-android) ayarları için desteklemektedir.

### <a name="device-setup-progress-indicator-in-android-company-portal----1565657---"></a>Android Şirket Portalı cihaz kurulumu ilerleme göstergesi <!-- 1565657 -->
Android için Şirket Portalı uygulaması, bir kullanıcı cihazını kaydederken bir cihaz kurulumu ilerleme göstergesi gösterir. Gösterge, "cihazınızı ayarlama...", ardından "cihazınız kaydediliyor...", ardından "cihazınızı kaydetme tamamlanıyor...", ardından "cihazınızın kurulması tamamlanıyor..." ile başlayan yeni durumları gösterir.

### <a name="certificate-based-authentication-support-on-the-company-portal-for-ios---1029830--"></a>İOS için Şirket Portalı sertifika tabanlı kimlik doğrulama desteği <!--1029830-->
İOS için Şirket Portalı uygulamasına sertifika tabanlı kimlik doğrulaması (CBA) desteği ekledik. CBA 'ya sahip kullanıcılar Kullanıcı adını girip "sertifikayla oturum aç" bağlantısına dokunun. CBA, Android ve Windows için Şirket Portalı uygulamalarında zaten desteklenmektedir. [Şirket Portalı Uygulama sayfasında oturum açma](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal) hakkında daha fazla bilgi edinebilirsiniz.

### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment----1334712---"></a>Kayıt olmadan veya kayıt olmadan kullanılabilen uygulamalar artık kayıt istenmeden yüklenebilir. <!-- 1334712 -->

Android Şirket Portalı uygulamasında kayıt olmadan veya bunlarla kayıt yapılmadan kullanılabilir hale getirilen Şirket uygulamaları artık kaydolmak için bir istem olmadan yüklenebilir.

### <a name="windows-autopilot-deployment-program-support-in-microsoft-intune-----747617----"></a>Microsoft Intune 'da Windows AutoPilot dağıtım programı desteği  <!-- 747617  -->
Artık Windows AutoPilot dağıtım programı ile Microsoft Intune kullanarak kullanıcılarınızın kurumsal cihazlarını bunlara dahil etmeden sağlamasını güçlendirin. Kullanıma hazır deneyimi (OOBE) özelleştirebilir ve kullanıcıların cihazlarını Azure AD 'ye katmalarını ve Intune 'a kaydolmasını kılavuza ekleyebilirsiniz. Birlikte çalışarak, Microsoft Intune ve Windows AutoPilot işletim sistemi görüntülerini dağıtma, sürdürme ve yönetme ihtiyacını ortadan kaldırır. Ayrıntılar için bkz. [Windows Autopilot Dağıtım programını kullanarak Windows cihazlarını kaydetme](../enrollment/enrollment-autopilot.md).

### <a name="quickstart-for-device-enrollment-----1425655---"></a>Cihaz kaydı için hızlı başlangıç  <!-- 1425655 --> 
Hızlı başlangıç artık **cihaz kaydında** kullanılabilir ve platformları yönetmek ve kayıt işlemini yapılandırmak için bir başvuru tablosu sağlar. Her öğe için kısa bir açıklama ve adım adım yönergeler ile belgelere yapılan bağlantılar, kullanmaya başlamanıza yardımcı olacak yararlı belgeler sağlar.

### <a name="device-categorization----1427491---"></a>Cihaz kategorisi <!-- 1427491 -->
Cihazların kayıtlı cihazlar platformu grafiği **> genel bakış** dikey penceresi, cihazları Android, IOS, MacOS, Windows ve Windows Mobile gibi platforma göre düzenler.  Diğer işletim sistemlerini çalıştıran cihazlar "diğer" halinde gruplandırılır.  Bu, BlackBerry, NOKIA ve diğerleri tarafından üretilen cihazları içerir.  

Kiracınızda hangi cihazların etkilendiğini öğrenmek için, **tüm cihazlar > Yönet** ' i seçin ve ardından **filtre** ' yi kullanarak **işletim sistemi** alanını sınırlandırın.

### <a name="zimperium---new-mobile-threat-defense-partner------954681---"></a>Zyium-yeni Mobile Threat Defense iş ortağı   <!-- 954681 -->  
Microsoft Intune ile tümleştirilen bir mobil tehdit savunması çözümü olan Zemium tarafından gerçekleştirilen risk değerlendirmesine dayalı koşullu erişimi kullanarak mobil cihaz erişimini kontrol edebilirsiniz.

#### <a name="how-integration-with-intune-works"></a>Intune ile tümleştirme nasıl işe yarar?
Risk, Zlaium çalıştıran cihazlardan toplanan telemetriye göre değerlendirilir. Intune cihaz uyumluluk ilkeleri aracılığıyla etkinleştirilen zem riskli risk değerlendirmesi temelinde EMS koşullu erişim ilkelerini yapılandırabilirsiniz. Bu, uyumlu olmayan cihazların algılanan tehditlere dayalı olarak şirket kaynaklarına erişmesine izin vermek veya erişimi engellemek için kullanabilirsiniz.

### <a name="new-settings-for-windows-10-device-restriction-profile------978575-1308849---"></a>Windows 10 cihaz kısıtlama profili için yeni ayarlar  <!--- 978575, 1308849, -->  
Windows Defender SmartScreen kategorisindeki Windows 10 cihaz kısıtlama profiline yeni ayarlar ekliyoruz.

Windows 10 cihaz kısıtlama profili hakkında daha fazla bilgi için bkz. [Windows 10 ve üzeri cihaz kısıtlama ayarları](../configuration/device-restrictions-windows-10.md).

### <a name="remote-support-for-windows-and-windows-mobile-devices------1070473---"></a>Windows ve Windows Mobile cihazlar için uzak destek   <!-- 1070473 -->  
Intune artık Windows ve Windows Mobile cihazları çalıştıran kullanıcılarınıza uzaktan yardım vermenizi sağlamak için Ayrıca satın alınan [TeamViewer](https://www.teamviewer.com) yazılımını kullanabilir.

### <a name="scan-devices-with-windows-defender----1280988--1280990-----"></a>Windows Defender ile cihazları tarama <!-- 1280988  1280990   -->
Artık, yönetilen Windows 10 cihazlarında Windows Defender virüsten koruma ile **hızlı tarama**, **tam tarama**ve **imza güncelleştirme** çalıştırabilirsiniz. Cihazın genel bakış dikey penceresinde, cihazda çalıştırılacak eylemi seçin. Komut cihaza gönderilmeden önce eylemi onaylamanız istenir. 

**Hızlı tarama**: hızlı tarama, kayıt defteri anahtarları ve bilinen Windows başlangıç klasörleri gibi kötü amaçlı yazılımların başlayacağı konumları tarar. Hızlı tarama beş dakikalık bir ortalama sürer. Açık, kapalı olduğunda ve bir Kullanıcı bir klasöre gittiğinde her **zaman açık gerçek zamanlı koruma** ayarıyla birlikte, bir hızlı tarama, sistemde veya çekirdekte olabilecek kötü amaçlı yazılımlara karşı koruma sağlamaya yardımcı olur. Kullanıcılar tamamlandığında tarama sonuçlarını cihazlarına görürler. 

**Tam tarama**: tam tarama, daha kapsamlı bir temizlik gerektiren etkin olmayan bir bileşen olup olmadığını belirlemek için kötü amaçlı yazılım tehdidi ile karşılaşan cihazlarda yararlı olabilir ve isteğe bağlı taramalar çalıştırmak için yararlıdır. Tam taramanın çalışması bir saat sürebilir. Kullanıcılar tamamlandığında tarama sonuçlarını cihazlarına görürler. 

**Imzaları Güncelleştir**: imza Güncelleştir komutu, Windows Defender virüsten koruma kötü amaçlı yazılım tanımlarını ve imzalarını güncelleştirir. Bu, Windows Defender virüsten koruma 'nın kötü amaçlı yazılımı tespit etmek için etkili olmasını sağlar Bu özellik yalnızca Windows 10 cihazlarına, bekleyen cihaz internet bağlantısına yöneliktir. 

### <a name="the-enabledisable-button-is-removed-from-the-intune-certificate-authority-page-of-the-intune-azure-portal-----1400455---"></a>Etkinleştir/devre dışı bırak düğmesi Intune 'un Intune sertifika yetkilisi sayfasından kaldırılır Azure portal  <!-- 1400455 -->
 Intune 'da sertifika bağlayıcısını ayarlama konusunda ek bir adım ortadan kalkar. Şu anda, sertifika bağlayıcısını indirip Intune konsolunda etkinleştirirsiniz. Ancak, Intune konsolunda bağlayıcıyı devre dışı bıraktığınızda bağlayıcı, sertifika vermeye devam eder.

#### <a name="how-does-this-affect-me"></a>Bu, beni nasıl etkiler?
Ekim 'den itibaren, etkinleştir/devre dışı bırak düğmesi artık Azure portal sertifika yetkilisi sayfasında görünmez. Bağlayıcı işlevselliği aynı kalır. Sertifikalar hala Intune 'a kayıtlı cihazlara dağıtılır. Sertifika bağlayıcısını indirip yüklemeye devam edebilirsiniz. Sertifikaların verilme işlemini durdurmak için artık sertifika bağlayıcısını devre dışı bırakmak yerine kaldırırsınız.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapmam gerekir?
Şu anda sertifika Bağlayıcısı devre dışı bırakılmışsa, kaldırmanız gerekir.

### <a name="new-settings-for-windows-10-team-device-restriction-profile-------1308838---"></a>Windows 10 Team cihaz kısıtlama profili için yeni ayarlar   <!--- 1308838 -->
Bu sürümde, Surface Hub cihazları denetlemenize yardımcı olması için Windows 10 Team cihaz kısıtlama profiline pek çok yeni ayar ekledik.

Bu profil hakkında daha fazla bilgi için bkz. [Windows 10 Team cihaz kısıtlama ayarları](../configuration/device-restrictions-windows-10-teams.md).

### <a name="prevent-users-of-android-devices-from-changing-their-device-date-and-time-----1333292---"></a>Android cihaz kullanıcılarının kendi cihaz tarih ve saatini değiştirmesini engelleyin  <!-- 1333292 -->
Android cihaz kullanıcılarının cihaz tarih ve saatini değiştirmelerini engellemek için bir [Android özel cihaz ilkesi](../configuration/custom-settings-android.md) kullanabilirsiniz.

Bunu yapmak için, URI ayarı olan bir Android özel ilkesi yapılandırın./Vendor/MSFT/PolicyManager/My/System/AllowDateTimeChange bunu **true**olarak ayarlayın ve gerekli gruplara atayın.

### <a name="bitlocker-device-configuration----1397398---"></a>BitLocker cihaz yapılandırması <!-- 1397398 -->
**Windows şifreleme > temel ayarları** , kullanıcının cihazında kullanımda olabilecek diğer disk şifrelemesi için [Uyarı isteğini](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#allowwarningforotherdiskencryption) devre dışı bırakmanızı sağlayan **başka bir disk şifreleme ayarı için** yeni bir uyarı içerir.  Uyarı istemi, cihazda BitLocker ayarlamadan önce son kullanıcı onayı gerektirir ve son kullanıcı tarafından onaylanana kadar BitLocker kurulumunu engeller.  Yeni ayar, Son Kullanıcı uyarısını devre dışı bırakır.


### <a name="volume-purchase-program-for-business-apps-will-now-sync-to-your-intune-tenant----800882---"></a>Iş için toplu satın alma programı uygulamaları artık Intune kiracınızla eşitlenecek <!-- 800882 -->  
Üçüncü taraf geliştiriciler, iTunes Connect 'te belirtilen Iş üyeleri için yetkili toplu satın alma programı 'na (VPP) özel olarak uygulama dağıtabilir. Bu Iş için VPP üyeleri toplu satın alma programı uygulama mağazasındaki oturum açabilir ve uygulamalarını satın alabilir.

Bu sürümle birlikte, son kullanıcı tarafından satın alınan Iş için VPP uygulamaları artık Intune kiracılarıyla eşitlemeye başlar.

### <a name="select-apple-countryregion-store-to-sync-vpp-apps-----1332311---"></a>VPP uygulamalarını eşitlemek için Apple ülke/bölge deposunu seçin  <!-- 1332311 -->  
VPP belirtecinizi karşıya yüklerken Volume Purchase program (VPP) ülke/bölge deposunu yapılandırabilirsiniz. Intune, VPP uygulamalarını belirtilen VPP ülke/bölge deposundan tüm yerel ayarlar için eşitler.

> [!NOTE]  
> Intune, günümüzde yalnızca Intune kiracısının oluşturulduğu Intune yerel ayarıyla eşleşen VPP ülke/bölge deposundan VPP uygulamalarını eşitler.


### <a name="block-copy-and-paste-between-work-and-personal-profiles-in-android-for-work----1098994---"></a>Android for Work 'te iş ve kişisel profiller arasında kopyalama ve yapıştırmayı engelle <!-- 1098994 -->
Bu sürümle birlikte, Android for Work için iş profilini, iş ve kişisel uygulamalar arasında kopyalama ve yapıştırmayı engelleyecek şekilde yapılandırabileceksiniz. Bu yeni ayarı, **iş profili ayarlarındaki** **Android for Work** platformu için **cihaz kısıtlamaları** profilinde bulabilirsiniz.

### <a name="create-ios-apps-limited-to-specific-regional-apple-app-stores----1281692---"></a>Belirli bölgesel Apple uygulama depolarıyla sınırlı iOS uygulamaları oluşturma <!-- 1281692 -->
Apple App Store yönetilen uygulamasının oluşturulması sırasında ülke/bölge yerel ayarını belirleyebileceksiniz.

> [!Note]  
> Şu anda yalnızca ABD ülke/bölge deposunda bulunan Apple App Store yönetilen uygulamaları oluşturabilirsiniz.

### <a name="update-ios-vpp-user-and-device-licensed-apps-----1305564---"></a>İOS VPP Kullanıcı ve cihaz lisanslı uygulamalarını güncelleştirme  <!-- 1305564 -->  
İOS VPP belirtecini, bu belirteç için satın alınan tüm uygulamaları Intune hizmeti aracılığıyla güncelleştirmek üzere yapılandıracaksınız. Intune, uygulama mağazasındaki VPP uygulama güncelleştirmelerini algılayacak ve cihaz iade edildiğinde onları cihaza otomatik olarak gönderecektir.

Bir VPP belirteci ayarlama ve otomatik güncelleştirmeleri etkinleştirme adımları için bkz. [Microsoft Intune ile toplu satın alma programı aracılığıyla satın alınan iOS uygulamalarını yönetme] (/inTune/VPP-Apps-iOS).


### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Intune veri ambarı veri modeline eklenen Kullanıcı cihaz ilişkilendirmesi varlık koleksiyonu <!-- 1187917 -->
Artık Kullanıcı ve cihaz varlık koleksiyonlarını ilişkilendiren Kullanıcı cihaz ilişki bilgilerini kullanarak rapor ve veri görselleştirmeleri oluşturabilirsiniz. Veri modeline, veri ambarı Intune sayfasından, OData uç noktasından alınan Power BI dosyası (PBIX) aracılığıyla veya özel bir istemci geliştirilerek erişilebilir.

### <a name="review-policy-compliance-for-windows-10-update-rings----1067886---"></a>Windows 10 güncelleştirme halkaları için ilke uyumluluğunu gözden geçirme <!-- 1067886 -->
Güncelleştirme halkası dağıtım durumu başına > yazılım güncelleştirmeleri 'nden Windows 10 güncelleştirme halkalarınız için bir ilke raporu inceleyebilirsiniz. İlke raporu, yapılandırdığınız güncelleştirme halkaları için dağıtım durumunu içerir. 

### <a name="new-report-that-lists-ios-devices-with-older-ios-versions------1352223---"></a>İOS cihazlarını daha eski iOS sürümleriyle listeleyen yeni rapor   <!-- 1352223 -->
**Güncel olmayan IOS cihazları** raporu, **yazılım güncelleştirmeleri** çalışma alanında kullanılabilir. Raporda, bir iOS güncelleştirme ilkesi tarafından hedeflenen ve kullanılabilir güncelleştirmelerin bulunduğu denetimli iOS cihazların listesini görüntüleyebilirsiniz. Her cihaz için cihazın neden otomatik olarak güncellenmediğini bir durum görüntüleyebilirsiniz. 

### <a name="view-app-protection-policy-assignments-for-troubleshooting-----1475003---"></a>Sorun giderme için uygulama koruma ilkesi atamalarını görüntüleme <!--  1475003 -->
Yaklaşan bu sürümde, **Uygulama koruma ilkesi** seçeneği, sorun giderme dikey penceresinde bulunan **atamalar** açılan listesine eklenecektir. Artık seçili kullanıcılara atanan uygulama koruma ilkelerini görmek için uygulama koruma ilkeleri ' ni seçebilirsiniz.



### <a name="improvements-to-device-setup-workflow-in-company-portal---1490692--"></a>Şirket Portalı cihaz kurulumu iş akışında iyileştirmeler <!--1490692-->
Android için Şirket Portalı uygulamasındaki cihaz kurulumu iş akışını geliştirdik. Bu dil, daha kolay ve şirketinize özgü bir dildir ve ekranları mümkün olduğunca birleştiriyoruz. Bunları, [uygulama kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md#week-of-october-2-2017) sayfasında görebilirsiniz.

### <a name="improved-guidance-around-the-request-for-access-to-contacts-on-android-devices---1484985--"></a>Android cihazlarda kişilere erişim isteği etrafında geliştirilmiş yönergeler <!--1484985-->

Android için Şirket Portalı uygulaması genellikle son kullanıcının kişiler iznini kabul etmesini gerektirir. Son Kullanıcı bu erişimi reddederse, bundan sonra koşullu erişim sağlamak için bunları uyaran bir uygulama içi bildirim görür. 

### <a name="secure-startup-remediation-for-android---1490712--"></a>Android için güvenli başlangıç düzeltmesi <!--1490712-->

Android cihazları olan son kullanıcılar Şirket Portalı uygulamasında uyumsuzluk nedenine dokunabilir. Mümkün olduğunda, bu işlem, sorunu gidermek için doğrudan ayarlar uygulamasındaki doğru konuma götürür. 

### <a name="additional-push-notifications-for-end-users-on-the-company-portal-app-for-android-oreo---1475932--"></a>Android için Şirket Portalı uygulamasındaki son kullanıcılar için ek anında iletme bildirimleri Oreo <!--1475932-->

Android Oreo için Şirket Portalı uygulaması, Intune hizmetinden ilke alma gibi arka plan görevleri gerçekleştirirken, son kullanıcılar bu kullanıcılara işaret eden ek bildirimler görür. Bu, Şirket Portalı, son kullanıcıların cihazında yönetim görevleri gerçekleştirirken bu saydamlığı artırır. Bu, Android Oreo için Şirket Portalı uygulamasının [Şirket portalı Kullanıcı arabiriminin genel iyileştirmesinin](https://blogs.technet.microsoft.com/intunesupport/2017/08/21/android-8-0-o-behaviour-changes-and-microsoft-intune) bir parçasıdır. 

Android Oreo 'de etkin olan yeni kullanıcı arabirimi öğeleri için daha fazla iyileştirmeler vardır.  Son kullanıcılar, Şirket Portalı Intune hizmetinden ilke alma gibi arka plan görevleri gerçekleştirirken bu kullanıcılara işaret edecek ek bildirimler görür.  Bu, Şirket Portalı cihazda yönetim görevleri gerçekleştirirken son kullanıcıların saydamlığını artırır.

### <a name="new-behaviors-for-the-company-portal-app-for-android-with-work-profiles----1485783---"></a>İş profilleriyle Android için Şirket Portalı uygulaması için yeni davranışlar <!-- 1485783 -->

İş profiline sahip bir Android for Work cihazını kaydettiğinizde, cihaz üzerinde yönetim görevlerini gerçekleştiren iş profilindeki Şirket Portalı uygulamasıdır. 

Kişisel profilde MAM özellikli bir uygulama kullanmadığınız takdirde, Android için Şirket Portalı uygulaması artık herhangi bir kullanıma hizmet vermez. Intune, iş profili deneyimini geliştirmek için, başarılı bir iş profili kaydından sonra kişisel Şirket Portalı uygulamasını otomatik olarak gizleyecek.

Android için Şirket Portalı uygulaması, [Play Store Şirket portalı](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) göz atarak ve **Etkinleştir**' e dokunarak kişisel profilde dilediğiniz zaman etkinleştirilebilir.

### <a name="company-portal-for-windows-81-and-windows-phone-81-moving-to-sustaining-mode---1428681--"></a>Windows 8.1 ve Windows Phone 8,1 Şirket Portalı susme moduna geçme <!--1428681-->

2017 Ekim 'den başlayarak, Windows 8.1 ve Windows Phone 8,1 için Şirket Portalı uygulamalar, susme moduna geçmeyecektir. Bu, uygulamaların ve kayıt ve uyumluluk gibi mevcut senaryoların bu platformlar için desteklenmeye devam edemeyeceği anlamına gelir. Bu uygulamalar, Microsoft Store gibi mevcut yayın kanalları aracılığıyla indirilebilir olmaya devam edecektir. 

Bu uygulamalar, susme modundayken yalnızca kritik güvenlik güncelleştirmelerini alacaktır. Bu uygulamalar için yayımlanmış başka güncelleştirmeler veya özellikler olmayacaktır. Yeni özellikler için cihazları Windows 10 veya Windows 10 Mobile 'a güncelleştirmenizi öneririz. 


### <a name="block-unsupported-samsung-knox-device-enrollment-----1490695---"></a>Desteklenmeyen Samsung KNOX cihaz kaydını engelle  <!-- 1490695 -->

Şirket Portalı uygulama yalnızca desteklenen Samsung KNOX cihazlarını kaydetmeyi dener. MDM kaydını önleyen Knox etkinleştirme hatalarının önüne geçmek için, cihaz kaydı yalnızca cihazın [Samsung tarafından yayınlanan cihazlar listesinde](https://www.samsungknox.com/knox-supported-devices/knox-workspace)görünmesi denendiğinde denenir. Samsung cihazlarda Knox destekleyen model numaraları olabilir, ancak diğerleri desteklemez. Satın alma ve dağıtımdan önce cihaz satıcınızla birlikte Knox uyumluluğunu doğrulayın. Doğrulanan cihazların tam listesini [Android ve Samsung KNOX Standard ilke ayarları](supported-devices-browsers.md#intune-supported-web-browsers)' nda bulabilirsiniz.

### <a name="end-of-support-for-android-43-and-lower----1171126-1326920---"></a>Android 4,3 ve daha düşük sürümleri için destek sonu <!-- 1171126, 1326920 -->
Yönetilen uygulamalar ve Android için Şirket Portalı uygulaması, şirket kaynaklarına erişmek için Android 4,4 ve üstünü gerektirir. Aralık ayında, tüm kayıtlı cihazlar Aralık ayında zorla devre dışı bırakılır ve şirket kaynaklarına erişim kaybı ile sonuçlanır. MDM olmadan uygulama koruma ilkeleri kullanıyorsanız, uygulamalar güncelleştirmeleri almaz ve deneyiminin kalitesi zaman içinde azalacaktır.

### <a name="inform-end-users-what-device-information-can-be-seen-on-enrolled-devices---1165314--"></a>Son kullanıcılara kayıtlı cihazlarda hangi cihaz bilgilerinin görülebileceği hakkında bilgi verme <!--1165314-->
Tüm Şirket Portalı uygulamalardaki cihaz ayrıntıları ekranına **sahiplik türü** ekliyoruz. Bu, kullanıcıların [, şirketinizin neleri görebileceklerini](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune) öğrenmek için doğrudan gizlilik hakkında daha fazla bilgi bulmasına olanak tanır. Bu, yakın gelecekte tüm Şirket Portalı uygulamalar arasında kullanıma sunulacaktır. [Eylül ayında](#september-2017)Bu iOS için bunu duyurduk.

<!-- ########################## -->
## <a name="september-2017"></a>Eylül 2017

### <a name="intune-supports-ios-11---1428975--"></a>Intune, iOS 11 ' i destekler <!--1428975-->
Intune, iOS 11 ' i destekler. Bu, daha önce [Intune destek blogu](https://blogs.technet.microsoft.com/intunesupport/2017/09/12/support-tip-intune-support-for-ios-11/)' na duyuruldu.

### <a name="end-of-support-for-ios-80----1164477---"></a>İOS 8,0 için destek sonu <!-- 1164477 -->
Yönetilen uygulamalar ve iOS için Şirket Portalı uygulaması, şirket kaynaklarına erişmek için iOS 9,0 ve üstünü gerektirir. Bu Eylül 'den önce güncelleştirilmemiş cihazlar artık Şirket Portalı veya bu uygulamalara erişemeyecek. 

### <a name="refresh-action-added-to-the-company-portal-app-for-windows-10---1132468--"></a>Windows 10 için Şirket Portalı uygulamasına yenileme eylemi eklendi <!--1132468-->
Windows 10 için Şirket Portalı uygulaması, kullanıcıların yenileme veya masaüstleri üzerinde, F5 tuşuna basarak uygulamadaki verileri yenilemesini sağlar.

### <a name="inform-end-users-what-device-information-can-be-seen-for-ios---739894--"></a>Son kullanıcılara iOS için hangi cihaz bilgilerinin görülebileceği hakkında bilgi verme <!--739894-->

İOS için Şirket Portalı App 'teki cihaz ayrıntıları ekranına **sahiplik türü** ekledik. Bu, kullanıcıların doğrudan bu sayfadan Intune Son Kullanıcı belgelerinden gizlilik hakkında daha fazla bilgi bulmasına olanak tanır. Ayrıca, bu bilgileri hakkında ekranında bulabilirsiniz.

### <a name="allow-end-users-to-access-the-company-portal-app-for-android-without-enrollment----1169910---"></a>Son kullanıcıların kayıt olmadan Android için Şirket Portalı uygulamasına erişmesine izin ver <!---1169910--->

Son kullanıcıların, Android için Şirket Portalı uygulamasına erişmek için cihazını kaydetmesi yakında olmayacaktır. Uygulama koruma Ilkelerini kullanan kuruluşların son kullanıcıları artık Şirket Portalı uygulamasını açtıklarında cihazlarını kaydetmeleri için istem almaz. Ayrıca, son kullanıcılar, cihazı kaydetmeden Şirket Portalı da uygulama yükleyebilecektir. 


### <a name="easier-to-understand-phrasing-for-the-company-portal-app-for-android----1396349---"></a>Android için Şirket Portalı uygulamasına yönelik daha kolay anlaşılır ifade <!---1396349--->  

Android için Şirket Portalı uygulamasına yönelik kayıt işlemi, son kullanıcıların kaydolmasını kolaylaştırmak için yeni metinle basitleştirilmiştir. Özel kayıt belgelerinize sahipseniz, bunu yeni ekranları yansıtacak şekilde güncellemek isteyeceksiniz. [Intune son kullanıcı uygulamaları Için Kullanıcı arabirimi güncelleştirmelerimiz](whats-new-app-ui.md#week-of-september-11-2017) sayfasında örnek görüntüler bulabilirsiniz.

### <a name="windows-10-company-portal-app-added-to-windows-information-protection-allow-policy----677129---"></a>Windows Information Protection ilkeye izin verme Şirket Portalı Windows 10 uygulaması eklendi <!-- 677129 -->

Windows 10 Şirket Portalı uygulaması, Windows Information Protection (WıP) desteğini destekleyecek şekilde güncelleştirilmiştir. Uygulama, WıP izin ver ilkesine eklenebilir. Bu değişiklik ile uygulamanın artık **dışlama** listesine eklenmesi gerekmez.


<!-- ########################## -->
## <a name="august-2017"></a>Ağustos 2017

### <a name="improvements-to-device-overview----1404453---"></a>Cihaza genel bakış geliştirmeleri <!-- 1404453 -->  
Cihaza genel bakış geliştirmeleri artık kayıtlı cihazları görüntüleyebilir, ancak Exchange ActiveSync tarafından yönetilen cihazları dışlar. Exchange ActiveSync cihazları kayıtlı cihazlarla aynı yönetim seçeneklerine sahip değildir. Intune 'da Azure portal kayıtlı cihazların ve kayıtlı cihazların sayısını Intune 'da görüntülemek için **cihazlara** > **Genel Bakış ' a**gidin.

### <a name="improvements-to-device-inventory-collected-by-intune"></a>Intune tarafından toplanan cihaz envanterine yönelik iyileştirmeler
<!-- 961134, 1104426, 1281327, 1333543 -->
Bu sürümde, yönettiğiniz cihazlar tarafından toplanan envanter bilgileri için aşağıdaki geliştirmeleri yaptık:
 
- Android cihazlarda artık cihaz envanterine her bir cihaz için en son düzeltme eki düzeyini gösteren bir sütun ekleyebilirsiniz. Bunu görmek için, cihaz listenize **güvenlik düzeltme eki düzeyi** sütununu ekleyin.
- Cihaz görünümünü filtreleyerek artık cihazları kayıt tarihine göre filtreleyebilirsiniz. Örneğin, yalnızca belirttiğiniz bir tarihten sonra kaydedilmiş olan cihazları görüntüleyebilirsiniz.
- **Son Iade tarihi** öğesi tarafından kullanılan filtreye yönelik iyileştirmeler yaptık.
- Cihaz listesinde, artık şirkete ait cihazların telefon numarasını görüntüleyebilirsiniz.
Ayrıca, telefon numarasına göre cihaz aramak için Filtre bölmesini kullanabilirsiniz.

Cihaz envanteri hakkında daha fazla ayrıntı için bkz. [Intune cihaz envanterini görüntüleme](../remote-actions/device-inventory.md).

### <a name="conditional-access-support-for-macos-devices"></a>MacOS cihazlar için koşullu erişim desteği 
<!-- 720172 -->
Artık, Mac cihazların Intune 'a kaydedilmesini ve cihaz uyumluluk ilkeleriyle uyumlu olmasını gerektiren bir koşullu erişim ilkesi ayarlayabilirsiniz. Örneğin, kullanıcılar macOS için Intune Şirket Portalı uygulamasını indirebilir ve Mac cihazlarını Intune 'a kaydedebilir. Intune, Mac cihazının PIN, şifreleme, işletim sistemi sürümü ve sistem bütünlüğü gibi gereksinimlerle uyumlu olup olmadığını değerlendirin.

- [MacOS cihazları Için koşullu erişim desteği](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)hakkında daha fazla bilgi edinin.

### <a name="company-portal-app-for-macos-is-in-public-preview----1484796---"></a>MacOS için Şirket Portalı uygulaması genel önizlemede <!---1484796--->
MacOS için Şirket Portalı uygulaması artık Enterprise Mobility + Security koşullu erişim için genel önizlemenin bir parçası olarak kullanılabilir. Bu sürüm, macOS 10,11 ve üstünü destekler. [@No__t-1](https://aka.ms/macOScompanyportal)' den alın. 


### <a name="new-device-restriction-settings-for-windows-10"></a>Windows 10 için yeni cihaz kısıtlama ayarları    
<!--1063965, 1308850  -->
Bu sürümde, [Windows 10 cihaz kısıtlama profili](/intune/device-restrictions-windows-10) için aşağıdaki kategorilere yeni ayarlar ekledik:

- Windows Defender SmartScreen
- Uygulama mağazası

### <a name="updates-to-the-windows-10-endpoint-protection-device-profile-for-bitlocker-settings"></a>BitLocker ayarları için Windows 10 Endpoint Protection cihaz profili güncelleştirmeleri
<!--1459533 -->    
Bu sürümde, Windows 10 Endpoint Protection cihaz profilinde BitLocker ayarlarının nasıl çalıştığı konusunda aşağıdaki geliştirmeleri yaptık:
 
- BitLocker **işletim sistemi sürücüsü ayarları**' nın altında, **BITLOCKER uyumlu olmayan TPM yongasıyla**, daha önce **Engelle**' yi seçtiğinizde bu durum, BitLocker 'ın gerçekten izin vermesine neden olur. Bu, seçili olduğunda BitLocker 'ı engellemek için bunu düzelttik.
- **BitLocker işletim sistemi sürücüsü ayarları**' nın altında, **sertifika tabanlı veri kurtarma aracısı**ayarı için artık sertifika tabanlı veri kurtarma aracısını açıkça engelleyebilirsiniz. Ancak, varsayılan olarak aracıya izin verilir.
- **BitLocker sabit veri sürücüsü ayarları**' nın altında, **veri kurtarma aracısı**ayarı için artık veri kurtarma aracısını açıkça engelleyebilirsiniz.
Daha fazla bilgi için bkz. [Windows 10 ve üzeri Için Endpoint Protection ayarları](../protect/endpoint-protection-windows-10.md).


### <a name="new-signed-in-experience-for-android-company-portal-users-and-app-protection-policy-users----621669---"></a>Android Şirket Portalı kullanıcıları ve uygulama koruma Ilkesi kullanıcıları için oturum açmış yeni deneyim <!-- 621669 -->
Son kullanıcılar artık Android cihazlarını kaydetmeden Android Şirket Portalı uygulamasını kullanarak uygulamalara gözatabilir, cihazları yönetebilir ve BT iletişim bilgilerini görüntüleyebiliyor. Ayrıca, son kullanıcı zaten Intune Uygulama Koruması Ilkeleri tarafından korunan bir uygulama kullanıyorsa ve Android Şirket Portalı başlatırsa, Son Kullanıcı artık cihazı kaydetmek için bir istem almaz.

### <a name="new-setting-in-the-android-company-portal-app-to-toggle-battery-optimization---1405990--"></a>Pil iyileştirmesini değiştirmek için Android Şirket Portalı uygulamasındaki yeni ayar <!--1405990-->
Android için Şirket Portalı uygulamasındaki **Ayarlar** sayfasında, kullanıcıların Şirket Portalı ve Microsoft Authenticator uygulamaları için pil iyileştirmesini kapatmasına kolayca izin veren yeni bir ayar vardır. Ayarda gösterilen uygulama adı, iş hesabını hangi uygulamanın yönettiğini bağlı olarak değişir. E-posta ve verileri eşitleyen iş uygulamalarının daha iyi performansı için kullanıcıların pil iyileştirmesini kapatmasını öneririz. 

### <a name="multi-identity-support-for-onenote-for-ios---------1234281---"></a>İOS için OneNote için çoklu kimlik desteği      <!-- 1234281 -->
Son kullanıcılar artık iOS için Microsoft OneNote ile farklı hesaplar (iş ve kişisel) kullanabilir. Uygulama koruma ilkeleri, kişisel not defterlerini etkilemeden iş not defterlerinde şirket verilerine uygulanabilir. Örneğin, bir ilke kullanıcının iş not defterlerinde bilgi bulmasına izin verebilir, ancak kullanıcının iş Not defterinden kişisel bir not defterine veri kopyalamasını ve yapıştırmasını engeller.
 
- Intune ile [uygulama korumayı ve çoklu kimliği](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) destekleyen uygulamalar hakkında daha fazla bilgi edinin.

### <a name="new-settings-to-allow-and-block-apps-on-samsung-knox-standard-devices"></a>Samsung KNOX Standard cihazlarında uygulamalara izin vermek ve bunları engellemek için yeni ayarlar
<!-- 1305423 822899-->  
Bu sürümde, aşağıdaki uygulama listelerini belirtmenizi sağlayan yeni [cihaz kısıtlama ayarları](../configuration/device-restrictions-android.md) ekliyoruz:
 
- Kullanıcıların yüklemesine izin verilen uygulamalar
- Kullanıcıların çalışması engellenen uygulamalar
- Cihazdaki kullanıcıdan gizlenen uygulamalar
 
Uygulamayı URL, paket adı veya yönettiğiniz uygulamalar listesinden belirtebilirsiniz.

### <a name="new-azure-ad-app-based-conditional-access-policy-ui-link-from-intune"></a>Intune 'dan yeni Azure AD uygulama tabanlı koşullu erişim ilkesi kullanıcı arabirimi bağlantısı
<!-- 1016201 -->
BT yöneticileri artık Azure AD iş yükünde yeni koşullu erişim ilkesi kullanıcı arabirimi aracılığıyla uygulama tabanlı koşullu ilkeler ayarlayabilir. Azure portal Intune Uygulama Koruması bölümünde yer alan uygulama tabanlı koşullu erişim, zamanında kalır ve yan yana zorlanır. Ayrıca, Intune iş yükünde yeni koşullu erişim ilkesi Kullanıcı arabirimine de kolaylık olan bir bağlantı vardır.

- [Azure AD 'de uygulama tabanlı koşullu erişim](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-technical-reference)hakkında daha fazla bilgi edinin.

<!-- ########################## -->
## <a name="july-2017"></a>2017 Temmuz

### <a name="restrict-android-and-ios-device-enrollment-restriction-by-os-version------1333256--1245463----"></a>Android ve iOS cihaz kaydı kısıtlamasını işletim sistemi sürümüne göre kısıtla  <!--- 1333256,  1245463 --->
Intune artık iOS ve Android kaydını işletim sistemi sürüm numarasına göre kısıtlamayı desteklemektedir. **Cihaz türü kısıtlaması**' nın altında, BT Yöneticisi artık en düşük ve en yüksek işletim sistemi değerleri arasında kaydı kısıtlamak için bir platform yapılandırması ayarlayabilir. Android işletim sistemi sürümleri, birincil. Ikincil. Build. Rev olarak belirtilmelidir; burada küçük, derleme ve Rev isteğe bağlıdır. iOS sürümleri birincil. Ikincil. derleme olarak belirtilmelidir; burada küçük ve derleme isteğe bağlıdır. [Cihaz Kayıt kısıtlamaları](../enrollment/enrollment-restrictions-set.md)hakkında daha fazla bilgi edinin.

>[!NOTE]
>Kaydı, Apple kayıt programları veya Apple Configurator ile kısıtlamayın.

### <a name="restrict-android-ios-and-macos-device-personally-owned-device-enrollment------1333272--1333275-1245709----"></a>Android, iOS ve macOS cihazı için kişisel cihaz kaydını kısıtlama  <!--- 1333272,  1333275, 1245709 --->
Intune, şirket cihazı ıMEı numaralarını beyaz listeye ekleyerek kişisel cihaz kaydını kısıtlayabilir. Intune artık cihaz seri numaralarını kullanarak bu işlevselliği iOS, Android ve macOS 'a genişletti. Seri numaralarını Intune 'a yükleyerek cihazları şirkete ait olarak önceden bildirebilirsiniz. Kayıt kısıtlamalarını kullanarak, kişisel olarak sahip olunan (BYOD) cihazları engelleyebilirsiniz ve yalnızca şirkete ait cihazlar için kayda izin verebilirsiniz. [Cihaz Kayıt kısıtlamaları](../enrollment/enrollment-restrictions-set.md)hakkında daha fazla bilgi edinin.

Seri numaralarını içeri aktarmak için **cihaz kaydı** > **Kurumsal cihaz tanımlayıcıları** ' na gidin ve **Ekle** ' ye tıklayın ve ardından bir yükleyin. CSV dosyası (üst bilgi, seri numarası için iki sütun ve ıMEı numaraları gibi ayrıntılar). Kişisel cihazları kısıtlamak için, **cihaz kaydı** > **Kayıt kısıtlamaları**' na gidin. **Cihaz türü kısıtlamaları**' nın altında **varsayılan** ' ı seçin ve ardından **Platform yapılandırması**' nı seçin. İOS, Android ve macOS için kişisel cihazlara **Izin verebilir** veya onları **engelleyebilirsiniz** .


### <a name="new-device-action-to-force-devices-to-sync-with-intune----711369---"></a>Cihazları Intune ile eşitlemeye zorlamak için yeni cihaz eylemi <!-- 711369 -->
Bu sürümde, seçili cihazı Intune ile hemen iade etmeye zorlayan yeni bir cihaz eylemi ekledik. Bir cihaz iade edildiğinde, kendisine atanmış bekleyen eylemleri veya ilkeleri hemen alır.  Bu eylem, bir sonraki zamanlanmış iadeyi beklemeden, atadığınız ilkeleri anında doğrulamanıza ve sorunlarını gidermenize yardımcı olabilir.
Ayrıntılar için bkz. [cihaz eşitlemeyi](../remote-actions/device-sync.md)

### <a name="force-supervised-ios-devices-to-automatically-install-the-latest-available-software-update----777100---"></a>Denetimli iOS cihazlarını, en son kullanılabilir yazılım güncelleştirmesini otomatik olarak yükleyecek şekilde zorla <!-- 777100 -->
Denetimli iOS cihazlarını, en son kullanılabilir yazılım güncelleştirmesini otomatik olarak yüklemeye zorgeçirebileceğiniz yazılım güncelleştirmeleri çalışma alanında yeni bir ilke kullanılabilir. Ayrıntılar için bkz. [iOS güncelleştirme Ilkelerini yapılandırma](/intune/software-updates-ios)

### <a name="check-point-sandblast-mobile---new-mobile-threat-defense-partner-----954651-1172027---"></a>Check Point SandBlast Mobile-yeni Mobile Threat Defense iş ortağı  <!-- 954651, 1172027 -->
Microsoft Intune ile tümleşen bir mobil tehdit savunması çözümü olan denetim noktası SandBlast Mobile tarafından gerçekleştirilen risk değerlendirmesine dayalı koşullu erişimi kullanarak mobil cihaz erişimini kontrol edebilirsiniz.

#### <a name="how-integration-with-intune-works"></a>Intune ile tümleştirme nasıl çalışıyor?
Risk, kontrol noktası SandBlast Mobile çalıştıran cihazlardan toplanan telemetriye göre değerlendirilir. Intune cihaz uyumluluk ilkeleri aracılığıyla etkinleştirilen denetim noktası SandBlast Mobile risk değerlendirmesini temel alan EMS koşullu erişim ilkelerini yapılandırabilirsiniz. Algılanan tehditlere dayalı olarak uyumlu olmayan cihazların şirket kaynaklarına erişmesine izin verebilir veya erişimi engelleyebilirsiniz.


### <a name="deploy-an-app-as-available-in-the-microsoft-store-for-business----748101---"></a>Iş için Microsoft Store bir uygulamayı kullanılabilir olarak dağıtma <!-- 748101 -->
Bu sürümle, Yöneticiler artık Iş için Microsoft Store kullanılabilir olarak atayabilirler. Kullanılabilir olarak ayarlandığında, son kullanıcılar Microsoft Store yeniden yönlendirilmeksizin uygulamayı Şirket Portalı uygulamadan veya Web sitesinden yükleyebilir.

### <a name="ui-updates-to-the-company-portal-website---1313244-part-1--"></a>Şirket Portalı Web sitesinde Kullanıcı Arabirimi güncelleştirmeleri <!--1313244 part 1-->
Son Kullanıcı deneyimini geliştirmek için [Şirket portalı Web sitesinin](https://portal.manage.microsoft.com) Kullanıcı arabiriminde birkaç güncelleştirme yaptık.

- __Uygulama kutucuklarına yönelik geliştirmeler__: uygulama simgeleri artık simgenin baskın rengine (algılanıyorsa) göre otomatik olarak oluşturulan bir arka planla görüntülenecektir. Bu arka plan, uygunsa, daha önce uygulama kutucuklarında görünen gri kenarlığın yerini alır.

    Şirket Portalı Web sitesi, gelecek sürümde mümkün olduğunda büyük simgeler görüntüler. BT yöneticilerinin, en az 120 120x120 piksel boyutuyla yüksek çözünürlüklü simgeler kullanarak uygulama yayımlamasını öneririz. 

- __Gezinti değişiklikleri__: gezinti çubuğu öğeleri sol üst kısımdaki hamburger menüsüne taşınır. Kategoriler sayfası kaldırılır. Kullanıcılar artık göz atarken içeriği kategoriye göre filtreleyebilir.

- __Öne çıkan uygulamalara yönelik güncelleştirmeler__: kullanıcıların, özelliği seçtiğiniz uygulamalara gözatabilecekleri ve giriş sayfasındaki öne çıkan bölümde bazı Kullanıcı arabirimi tiknoktaları yapmış olduğu siteye adanmış bir sayfa ekledik.

### <a name="ibooks-support-for-the-company-portal-website---1231841--"></a>Şirket Portalı Web sitesi için iBooks desteği <!--1231841-->
Şirket Portalı Web sitesine, kullanıcıların iBooks 'a gözatmasına ve indirmesine izin veren özel bir sayfa ekledik. 


### <a name="additional-help-desk-troubleshooting-details------applies-to-1263399-1326964-1341642----"></a>Ek Yardım Masası sorun giderme ayrıntıları <!---  Applies to 1263399, 1326964, 1341642 --->
Intune, sorun giderme görüntüsünü güncelleştirmiştir ve yöneticiler ve yardım masası personeli için sağladığı bilgilere eklenmiştir. Artık grup üyeliğine göre Kullanıcı için tüm atamaları özetleyen bir **atamalar** tablosu görebilirsiniz. Bu liste aşağıdakileri içerir:
- Mobil uygulamalar
- Uyumluluk ilkeleri
- Yapılandırma profilleri

Ayrıca, **cihazlar** tablosu artık **Azure AD JOIN türünü** ve **Azure AD uyumlu** sütunlarını içerir. Daha fazla bilgi için bkz. [kullanıcıların sorunları gidermelerine yardımcı olma](../help-desk-operators.md).



### <a name="intune-data-warehouse-public-preview"></a>Intune veri ambarı (Genel Önizleme)
Intune veri ambarı, kiracınızın geçmiş bir görünümünü sağlamak için verileri günlük olarak örnekler. Verilere bir Power BI dosyası (PBIX) kullanarak, birçok analiz araçlarıyla uyumlu bir OData bağlantısı, veya REST API etkileşimde bulunmak için erişebilirsiniz. Daha fazla bilgi için bkz. [Intune veri ambarını kullanma](../developer/reports-nav-create-intune-reports.md).


### <a name="light-and-dark-modes-available-for-the-company-portal-app-for-windows-10----676547---"></a>Windows 10 için Şirket Portalı uygulaması için açık ve koyu modlar mevcuttur <!---676547--->
Son kullanıcılar Windows 10 için Şirket Portalı uygulamasının renk modunu özelleştirebilecektir. Kullanıcı, Şirket Portalı uygulamasının ayarlar bölümünde değişiklik yapabilir. Değişiklik, Kullanıcı uygulamayı yeniden başlattıktan sonra görüntülenir. Windows 10 sürüm 1607 ve üzeri için uygulama modu varsayılan olarak sistem ayarında olacaktır. Windows 10 sürüm 1511 ve önceki sürümlerde, uygulama modu varsayılan olarak ışık moduna alınacaktır.

### <a name="enable-end-users-to-tag-their-device-group-in-the-company-portal-app-for-windows-10----807046--"></a>Son kullanıcıların Windows 10 için Şirket Portalı uygulamasında cihaz gruplarını etiketlamalarını sağlama <!---807046-->
Son kullanıcılar artık Windows 10 için Şirket Portalı uygulamasının içinden etiketleyerek cihazlarından hangi grubun ait olduğunu seçebiliyor.

<!-- ########################## -->
## <a name="june-2017"></a>Haziran 2017

### <a name="new-role-based-administration-access-for-intune-admins------1099990---"></a>Intune yöneticileri için yeni rol tabanlı yönetim erişimi   <!-- 1099990 -->  
Azure AD koşullu erişim ilkelerini görüntülemek, oluşturmak, değiştirmek ve silmek için yeni bir koşullu erişim Yöneticisi rolü ekleniyor. Daha önce yalnızca genel Yöneticiler ve güvenlik yöneticileri bu izne sahipti. Bu rol izniyle, koşullu erişim ilkelerine erişimi olacak şekilde Intune yöneticileri verilebilir.


### <a name="tag-corporate-owned-devices-with-serial-number----1215070---"></a>Şirkete ait cihazları seri numarasına göre etiketle <!-- 1215070 -->  
Intune artık iOS, macOS ve Android seri numaralarını kurumsal cihaz tanımlayıcıları olarak karşıya yüklemeyi desteklemektedir. Seri numaraları kayıt sırasında doğrulanmadığı için, kişisel cihazların bu kez kaydedilmesini engellemek üzere seri numaralarını kullanamazsınız. Kişisel cihazların seri numarasına göre engellenmesi yakın gelecekte yayımlanacak.


### <a name="new-remote-actions-for-ios-devices----854689---"></a>İOS cihazları için yeni uzak eylemler <!-- 854689 -->
Bu sürümde, Apple derslik uygulamasını yöneten paylaşılan iPad cihazları için iki yeni uzak cihaz eylemi ekledik:

- [Geçerli kullanıcının oturumunu kapat](../remote-actions/device-logout-user.md) -seçtiğiniz bir iOS cihazının geçerli kullanıcısı oturumunu kapatır.
- [Kullanıcıyı kaldır](../remote-actions/device-remove-user.md) -bir iOS cihazında yerel önbellekten seçtiğiniz bir kullanıcıyı siler.


### <a name="support-for-shared-ipads-with-the-ios-classroom-app----1044681---"></a>İOS sınıf uygulamasıyla paylaşılan IPad 'ler için destek <!-- 1044681 -->
Bu sürümde, yönetilen Apple KIMLIKLERINI kullanarak paylaşılan IPad 'lerde oturum açan öğrencileri dahil etmek için iOS derslik uygulamasının yönetilmesi desteğini genişlettik.


### <a name="changes-to-intune-built-in-apps----1332306---"></a>Intune yerleşik uygulamalarında yapılan değişiklikler <!-- 1332306 -->
Daha önce Intune, hızlı bir şekilde atayabileceğiniz çeşitli yerleşik uygulamalar içeriyordu. Geri bildirimlerinize bağlı olarak, bu listeyi kaldırdık, artık yerleşik uygulamaları görmeyecektir.
Ancak, herhangi bir yerleşik uygulamayı önceden atadıysanız bu uygulamalar, uygulama listesinde görünmeye devam edecektir. Bu uygulamaları gerektiği şekilde atamaya devam edebilirsiniz.
Sonraki bir sürümde, Azure portal yerleşik uygulamaları seçmek ve atamak için daha kolay bir yöntem eklemeyi planlıyoruz.

### <a name="easier-installation-of-office-365-apps-----1121362----"></a>Office 365 uygulamalarının daha kolay yüklenmesi <!--- 1121362 --->
Yeni **office 365 ProPlus** uygulama türü, Windows 10 ' un en son sürümünü çalıştıran yönettiğiniz cihazlara Office 365 ProPlus 2016 uygulamaları atamanızı kolaylaştırır. Ayrıca, lisans sahibiyseniz, Microsoft Project ve Microsoft Visio da yükleyebilirsiniz. İstediğiniz uygulamalar birlikte paketlenir ve Intune konsolundaki uygulamalar listesinde tek bir uygulama olarak görünür.
Daha fazla bilgi için bkz. [Windows 10 Için Office 365 uygulamaları ekleme](../apps/apps-add-office365.md).


### <a name="support-for-offline-apps-from-the-microsoft-store-for-business-----777044----"></a>Microsoft Store Iş için çevrimdışı uygulamalar için destek <!--- 777044 --->
Iş için Microsoft Store satın aldığınız çevrimdışı uygulamalar artık Azure portal eşitlenecek. Daha sonra bu uygulamaları cihaz gruplarına veya Kullanıcı gruplarına dağıtabilirsiniz. Çevrimdışı uygulamalar, mağaza tarafından değil Intune tarafından yüklenir.

### <a name="microsoft-teams-is-now-part-of-the-app-based-ca-list-of-approved-apps------1257019---"></a>Microsoft ekipleri artık onaylanan uygulamaların uygulama tabanlı CA listesinin bir parçasıdır   <!-- 1257019 -->
İOS ve Android için Microsoft ekipleri uygulaması artık Exchange ve SharePoint Online için uygulama tabanlı koşullu erişim ilkelerine yönelik onaylanan uygulamaların bir parçasıdır. Uygulama, şu anda uygulama tabanlı koşullu erişim kullanan tüm kiracılara Azure portal Intune Uygulama Koruması dikey penceresinde yapılandırılabilir.

### <a name="managed-browser-and-app-proxy-integration----1287310---"></a>Yönetilen tarayıcı ve uygulama proxy 'si tümleştirmesi <!-- 1287310 -->
Intune Managed Browser, kullanıcıların uzaktan çalıştıkları zaman bile iç Web sitelerine erişmesine izin vermek için artık Azure AD Uygulama Ara Sunucusu hizmeti ile tümleştirilebilir. Tarayıcı kullanıcıları genellikle her zamanki gibi site URL 'sini girip Managed Browser isteği uygulama proxy 'si Web ağ geçidi üzerinden yönlendirir. Daha fazla bilgi için bkz. [yönetilen tarayıcı ilkelerini kullanarak Internet erişimini yönetme](../apps/app-configuration-managed-browser.md).

### <a name="new-app-configuration-settings-for-the-intune-managed-browser----682951---"></a>Intune Managed Browser için yeni uygulama yapılandırma ayarları <!-- 682951 -->
Bu sürümde, iOS ve Android için Intune Managed Browser uygulamasına yönelik daha fazla yapılandırma ekledik. Artık tarayıcının varsayılan giriş sayfasını ve yer işaretlerini yapılandırmak için bir uygulama yapılandırma ilkesi kullanabilirsiniz.
Daha fazla bilgi için bkz. [yönetilen tarayıcı ilkelerini kullanarak Internet erişimini yönetme](../apps/app-configuration-managed-browser.md)

### <a name="bitlocker-settings-for-windows-10-----951707---"></a>Windows 10 için BitLocker ayarları  <!-- 951707 -->
Artık, yeni bir Intune cihaz profili kullanarak Windows 10 cihazları için BitLocker ayarlarını yapılandırabilirsiniz. Örneğin, cihazların şifrelenmesini zorunlu kılabilir ve ayrıca BitLocker açıldığında uygulanan diğer ayarları da yapılandırabilirsiniz.
Daha fazla bilgi için bkz. [Windows 10 ve üzeri Için Endpoint Protection ayarları](../protect/endpoint-protection-windows-10.md).

### <a name="new-settings-for-windows-10-device-restriction-profile-----978527--978550-978569-1050031-1058611-----"></a>Windows 10 cihaz kısıtlama profili için yeni ayarlar <!--- 978527,  978550, 978569, 1050031, 1058611,  --->
Bu sürümde, Windows 10 cihaz kısıtlama profili için aşağıdaki kategorilere yeni ayarlar ekledik:

- Windows Defender
- Hücresel ve bağlantı
- Kilit ekranı deneyimi
- Gizlilik
- Arama
- Windows spot
- Microsoft Edge tarayıcısı

Windows 10 ayarları hakkında daha fazla bilgi için bkz. [Windows 10 ve üzeri cihaz kısıtlama ayarları](../configuration/device-restrictions-windows-10.md).


### <a name="company-portal-app-for-android-now-has-a-new-end-user-experience-for-app-protection-policies---1305217--"></a>Android için Şirket Portalı uygulamasının artık uygulama koruma Ilkeleri için yeni bir son kullanıcı deneyimi vardır <!--1305217-->
Müşteri geri bildirimlerine göre, Android için Şirket Portalı uygulamasını, bir **erişim şirket içeriği** düğmesini gösterecek şekilde değiştirdik. Amaç, yalnızca Intune mobil uygulama yönetiminin bir özelliği olan uygulama koruma Ilkelerini destekleyen uygulamalara erişmesi gerektiğinde son kullanıcıların, kayıt işlemini gereksiz yere yapmasını önlemektir. Bu değişiklikleri [uygulama arabirimindeki yenilikler](whats-new-app-ui.md) sayfasında görebilirsiniz.

### <a name="new-menu-action-to-easily-remove-company-portal---1164569--"></a>Şirket Portalı kolayca kaldırmak için yeni menü eylemi <!--1164569-->
Kullanıcı geri bildirimlerine göre, Android için Şirket Portalı uygulaması, Şirket Portalı cihazınızdan kaldırmayı başlatmak için yeni bir menü eylemi eklemiştir. Bu eylem, uygulamanın cihazdan Kullanıcı tarafından kaldırılabilmesi için cihazı Intune yönetiminden kaldırır. Bu değişiklikleri [uygulama kullanıcı arabirimindeki](whats-new-app-ui.md) Yenilikler sayfasında ve [Android son kullanıcı belgelerinde](/intune-user-help/unenroll-your-device-from-intune-android)görebilirsiniz.

### <a name="improvements-to-app-syncing-with-windows-10-creators-update---676505--"></a>Windows 10 Creators Update ile uygulama eşitlemeye yönelik iyileştirmeler <!--676505-->
Windows 10 için Şirket Portalı uygulaması, Windows 10 Creators Update (sürüm 1703) ile cihazlara yönelik uygulama yüklemesi istekleri için otomatik olarak eşitleme başlatacak. Bu, "bekleyen eşitleme" durumu sırasında uygulama yükleme sorununu azaltır. Ayrıca, kullanıcılar uygulamayı içinden el ile bir eşitleme başlatabilir. Bu değişiklikleri [uygulama arabirimindeki yenilikler](whats-new-app-ui.md) sayfasında görebilirsiniz.

### <a name="new-guided-experience-for-windows-10-company-portal----1058938---"></a>Windows 10 için yeni Kılavuzlu deneyim Şirket Portalı <!---1058938--->
Windows 10 için Şirket Portalı uygulaması, tanımlanmamış veya kaydedilmemiş cihazlar için Kılavuzlu bir Intune izlenecek yol deneyimi içerecektir. Yeni deneyim, kullanıcıya Azure Active Directory (koşullu erişim özellikleri için gereklidir) ve MDM kaydının (cihaz yönetim özellikleri için gereklidir) kaydını yaparak kılavuzluk eden adım adım yönergeler sağlar. Kılavuzlu deneyime Şirket Portalı giriş sayfasından erişilebilecektir. Kullanıcılar kayıt ve kayıt tamamlanmadığında uygulamayı kullanmaya devam edebilir, ancak sınırlı işlevlere de karşılaşabilir.

Bu güncelleştirme yalnızca Windows 10 yıldönümü Güncelleştirmesi (derleme 1607) veya üstünü çalıştıran cihazlarda görülebilir. Bu değişiklikleri [uygulama arabirimindeki yenilikler](whats-new-app-ui.md) sayfasında görebilirsiniz.


### <a name="microsoft-intune-and-conditional-access-admin-consoles-are-generally-available"></a>Microsoft Intune ve koşullu erişim yönetici konsolları genel kullanıma sunulmuştur
Azure portal Yönetici Konsolu ve koşullu erişim Yönetici Konsolu 'ndaki yeni Intune 'un genel kullanıma sunulduğunu duyuruyoruz. Azure portal Intune aracılığıyla, artık tüm Intune MAM ve MDM özelliklerini tek bir birleştirilmiş yönetici deneyiminde yönetebilir ve Azure AD gruplama ve hedefleme özelliğinden yararlanabilirsiniz. Azure 'da koşullu erişim, Azure AD ve Intune üzerinde zengin özellikleri tek bir birleştirilmiş konsolda birlikte sunar. Azure platformuna geçmek, yönetim deneyiminden modern tarayıcılar kullanmanıza olanak sağlar.

Intune artık portal.azure.com adresindeki Azure portal **Önizleme** etiketi olmadan görünür.

İleti merkezinde, gruplarınızı geçirebilmemiz için işlem yapmanız gereken bir ileti serilerinden birini almadıysanız, şu anda mevcut müşteriler için herhangi bir işlem yapmanız gerekmez. Ayrıca, bu geçişin bizim sunduğumuz hatalar nedeniyle daha uzun sürdüğünü bildiren bir ileti merkezi bildirimi de almış olabilirsiniz. Etkilenen müşterileri geçirmeye yönelik olarak çalışmaya devam ediyoruz.

### <a name="improvements-to-the-app-tiles-in-the-company-portal-app-for-ios"></a>İOS için Şirket Portalı uygulamasındaki uygulama kutucuklarında iyileştirmeler
Giriş sayfasındaki uygulama kutucuklarının tasarımını, Şirket Portalı için ayarladığınız marka rengini yansıtacak şekilde güncelleştirdik. Daha fazla bilgi için bkz. [uygulama kullanıcı arabirimindeki](whats-new-app-ui.md)yenilikler.

### <a name="account-picker-now-available-for-the-company-portal-app-for-ios"></a>İOS için Şirket Portalı App için artık hesap seçici kullanılabilir
İOS cihazlarının kullanıcıları, diğer Microsoft uygulamalarında oturum açmak için iş veya okul hesaplarını kullandıklarında Şirket Portalı oturum açtıklarında yeni hesap seçicimizi görebilirler. Daha fazla bilgi için bkz. [uygulama kullanıcı arabirimindeki](whats-new-app-ui.md)yenilikler.

<!-- ########################## -->
## <a name="may-2017"></a>Mayıs 2017

### <a name="change-your-mdm-authority-without-unenrolling-managed-devices---1103950--"></a>Yönetilen cihazların kaydını kaldırmadan MDM yetkilinizi değiştirme <!--1103950-->
Artık Microsoft Desteği iletişim kurmak zorunda kalmadan MDM yetkilinizi değiştirebilir ve mevcut yönetilen cihazlarınızın kaydını silmek ve yeniden kaydetmek zorunda kalmadan değişiklik yapabilirsiniz. Configuration Manager konsolunda, [MDM yetkilinizi](/sccm/mdm/deploy-use/change-mdm-authority) Configuration Manager (karma) olarak Microsoft Intune (tek başına) veya bunun tersini değiştirebilirsiniz.


### <a name="improved-notification-for-samsung-knox-startup-pins---1087143--"></a>Samsung KNOX başlangıç PIN 'leri için geliştirilmiş bildirim <!--1087143-->
Son kullanıcıların, şifreleme ile uyumlu hale gelmesi için Samsung KNOX cihazlarında bir başlangıç PIN 'ı ayarlaması gerektiğinde, son kullanıcılara görüntülenecek bildirim, bildirim dokunulduğunda ayarlar uygulamasındaki tam yere gelir.  Daha önce bildirim, son kullanıcıyı parola değiştirme ekranına getirmişti.

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="apple-school-manager-asm-support-with-shared-ipad----748864-770395--"></a>Paylaşılan iPad ile Apple Okul Yöneticisi (ASM) desteği <!-- 748864, 770395-->

Intune artık iOS cihazlarının hazır kaydını sağlamak için Apple Aygıt Kayıt Programı yerine Apple Okul Yöneticisi 'nin (ASM) kullanımını desteklemektedir. Paylaşılan IPad 'ler için derslik uygulamasını kullanmak üzere ASM ekleme gereklidir ve Microsoft okul veri eşitlemesi (SDS) aracılığıyla ASM 'den Azure Active Directory veri eşitlemesini etkinleştirmek için gereklidir. Daha fazla bilgi için bkz. [Apple Okul yöneticisiyle iOS cihaz kaydını etkinleştirme](../enrollment/apple-school-manager-set-up-ios.md).

> [!NOTE]
> Paylaşılan IPad 'leri sınıf uygulamasıyla çalışacak şekilde yapılandırmak, Azure 'da iOS Eğitim yapılandırmalarının henüz mevcut olmadığından emin olmanızı gerektirir.  Bu işlevsellik yakında eklenecektir.

### <a name="device-management"></a>Cihaz yönetimi

#### <a name="provide-remote-assistance-to-android-devices-using-teamviewer----675418---"></a>TeamViewer kullanarak Android cihazlara uzaktan yardım sağlama <!-- 675418 -->

Intune artık, Android cihazları çalıştıran kullanıcılarınıza uzaktan yardım vermenizi sağlamak için Ayrıca satın alınan [TeamViewer](https://www.teamviewer.com) yazılımını kullanabilir. Daha fazla bilgi için bkz. [Intune ile yönetilen Android cihazları için uzaktan yardım sağlama](../remote-actions/teamviewer-support.md).

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="new-app-protection-policies-conditions-for-mam----679864---"></a>MAM için yeni uygulama koruma ilkeleri koşulları <!-- 679864 -->

Artık, aşağıdaki ilkeleri zorlayan kayıt kullanıcıları olmadan MAM için bir gereksinim ayarlayabilirsiniz:

- En düşük uygulama sürümü
- En düşük işletim sistemi sürümü
- Hedeflenen uygulamanın en düşük Intune uygulama SDK sürümü (yalnızca iOS)

Bu özellik hem Android hem de iOS 'ta kullanılabilir. Intune, işletim sistemi platformu sürümleri, uygulama sürümleri ve Intune uygulama SDK 'Sı için en düşük sürüm zorlamayı destekler. İOS 'ta, SDK 'nın tümleştirildiği uygulamalar, SDK düzeyinde en düşük sürüm zorlamasını de ayarlayabilir. Uygulama koruma İlkesi üzerinden en düşük gereksinimler, yukarıda belirtilen üç farklı düzeyde karşılanmazsa, Kullanıcı hedeflenen uygulamaya erişemez. Bu noktada, Kullanıcı hesabını kaldırabilir (çok kimlikli uygulamalarda), uygulamayı kapatabilir veya işletim sistemi ya da uygulamanın sürümünü güncelleştirebilir.

Ayrıca, işletim sistemi veya uygulama yükseltmesi öneren engelleyici olmayan bir bildirim sağlamak için ek ayarlar da yapılandırabilirsiniz. Bu bildirim kapatılabilir ve uygulama normal şekilde kullanılıyor olabilir.

Daha fazla bilgi için bkz. [iOS uygulama koruma ilkesi ayarları](../apps/app-protection-policy-settings-ios.md) ve [Android uygulama koruma ilkesi ayarları](../apps/app-protection-policy-settings-android.md).

#### <a name="configure-app-configurations-for-android-for-work----621621---"></a>Android for Work için uygulama konfigürasyonları yapılandırma <!-- 621621 -->
Mağazadan alınan bazı Android Uygulamaları, bir BT yöneticisinin bir uygulamanın iş profilinde nasıl çalıştığını denetlemesine izin veren yönetilen yapılandırma seçeneklerini destekler. Intune ile artık bir uygulama tarafından desteklenen yapılandırmaları görüntüleyebilir ve bunları bir yapılandırma Tasarımcısı veya JSON Düzenleyicisi ile Azure portal yapılandırabilirsiniz. Daha fazla bilgi için bkz. [Android for Work için uygulama yapılandırmasını kullanma](../apps/app-configuration-policies-use-android.md).

#### <a name="new-app-configuration-capability-for-mam-without-enrollment----677969---"></a>Kayıt olmadan MAM için yeni uygulama yapılandırma özelliği <!-- 677969 -->
Artık, kayıt kanalı olmadan MAM aracılığıyla uygulama yapılandırma ilkeleri oluşturabilirsiniz. Bu özellik, mobil cihaz yönetimi (MDM) uygulama yapılandırmasında bulunan uygulama yapılandırma ilkelerine eşdeğerdir. Kayıt olmadan MAM kullanan uygulama yapılandırmasına bir örnek için, bkz. [Microsoft Intune Ile yönetilen tarayıcı ilkelerini kullanarak Internet erişimini yönetme](../apps/app-configuration-managed-browser.md).

#### <a name="configure-allowed-and-blocked-url-lists-for-the-managed-browser----682960---"></a>Managed Browser için izin verilen ve engellenen URL listelerini yapılandırın <!-- 682960 -->
Artık Azure portal uygulama yapılandırma ayarlarını kullanarak Intune Managed Browser için izin verilen ve engellenen etki alanları ve URL 'Lerin bir listesini yapılandırabilirsiniz. Bu ayarlar, yönetilen veya yönetilmeyen bir cihazda kullanılıp kullanılmadığına bakılmaksızın yapılandırılabilir. Daha fazla bilgi için bkz. [Microsoft Intune Ile yönetilen tarayıcı ilkelerini kullanarak Internet erişimini yönetme](../apps/app-configuration-managed-browser.md).

#### <a name="app-protection-policy-helpdesk-view----1069473---"></a>Uygulama koruma ilkesi Yardım Masası görünümü <!-- 1069473 -->
BT yardım masası, kullanıcılar artık Kullanıcı Lisans durumunu ve sorun giderme dikey penceresinde kullanıcılara atanan uygulama koruma İlkesi uygulamalarının durumunu denetleyebilir. Ayrıntılar için bkz. [sorun giderme](./help-desk-operators.md).

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="control-website-visits-on-ios-devices----723832---"></a>İOS cihazlarında Web sitesi ziyaretlerini denetleme <!-- 723832 -->
Artık iOS cihazlarının kullanıcılarının hangi web sitelerini ziyaret edebileceklerini aşağıdaki iki yöntemden birini kullanarak denetleyebilirsiniz:

- Elmalar yerleşik web içeriği filtresini kullanarak izin verilen ve engellenen URL 'Ler ekleyin.

- Safari tarayıcısı tarafından yalnızca belirtilen Web sitelerine erişilmesine izin verin. Yer işaretleri, belirttiğiniz her site için Safari 'de oluşturulur.

Daha fazla bilgi için bkz. [iOS cihazları Için Web içeriği filtresi ayarları](../configuration/ios-device-features-settings.md#web-content-filter).

#### <a name="preconfigure-device-permissions-for-android-for-work-apps----621614---"></a>Android for Work uygulamaları için cihaz izinlerini önceden yapılandırın <!-- 621614 -->
Android for Work cihaz iş profillerine dağıtılan uygulamalar için artık tek tek uygulamalar için izin durumunu yapılandırabilirsiniz.  Varsayılan olarak, konuma veya cihaz kamerasına erişim gibi cihaz izinleri gerektiren Android Uygulamaları, kullanıcılardan izinleri kabul etmesini veya reddetmesini ister.  Örneğin, bir uygulama cihazın mikrofonunu kullanıyorsa, son kullanıcıdan mikrofonu kullanmak için uygulamaya izin vermesi istenir. Bu özellik, son kullanıcı adına izinleri tanımlamanızı sağlar.  Kullanıcıya, b) kullanıcıya bildirmeden otomatik olarak Reddet veya c) kullanıcıdan kabul etmesini veya reddetmesini istemek için, bir ' a bir) izin yapılandırabilirsiniz. Daha fazla bilgi için bkz. [Microsoft Intune Android for Work cihaz kısıtlama ayarları](../configuration/device-restrictions-android-for-work.md).

#### <a name="define-app-specific-pin-for-android-for-work-devices----728976-1102534---"></a>Android for Work cihazlar için uygulamaya özgü PIN tanımlayın <!-- 728976, 1102534 -->
Android for Work cihazı olarak yönetilen bir iş profili olan Android 7,0 ve üzeri cihazlar, yöneticinin yalnızca iş profilindeki uygulamalar için geçerli olan bir geçiş kodu ilkesi tanımlamasına olanak tanır.  Seçeneklere şunlar dahildir:

- Yalnızca cihaz genelinde bir geçiş kodu ilkesi tanımlama-Bu, kullanıcının tüm cihaz kilidini açmak için kullanması gereken geçiş kodudur.
- Yalnızca bir iş profili geçiş kodu ilkesi tanımlama-iş profilindeki bir uygulama her açıldığında kullanıcılardan bir geçiş kodu girmesi istenir.
- Hem cihaz hem iş profili ilkesi tanımlama-BT Yöneticisi, farklı güçlerle hem cihaz geçiş kodu ilkesi hem de iş profili geçiş kodu ilkesi tanımlama seçeneğine sahiptir (örneğin, cihazın kilidini açmak için dört basamaklı bir PIN, ancak herhangi bir iş uygulamasını açmak için altı basamaklı bir PIN).

Daha fazla bilgi için bkz. [Microsoft Intune Android for Work cihaz kısıtlama ayarları](../configuration/device-restrictions-android-for-work.md).

> [!NOTE]
> Bu yalnızca Android 7,0 ve üzeri sürümlerde kullanılabilir.  Varsayılan olarak, Son Kullanıcı iki ayrı tanımlı PIN 'i kullanabilir ya da iki tanımlı PIN 'i ikisinin en güçlü Çine birleştirmeyi seçebilirler.

#### <a name="new-settings-for-windows-10-devices----978585---"></a>Windows 10 cihazları için yeni ayarlar <!-- 978585 -->
Kablosuz ekranlar, cihaz bulma, görev geçişi ve SIM kart hata iletileri gibi özellikleri denetleyen yeni [Windows cihaz kısıtlama ayarları](../configuration/device-restrictions-windows-10.md) ekledik.

#### <a name="updates-to-certificate-configuration----918991-and-823198---"></a>Sertifika yapılandırması güncelleştirmeleri <!-- 918991 and 823198 -->
<strong>Konu adı biçimi</strong>IÇIN bir SCEP sertifika profili oluştururken, IOS, Android ve Windows cihazlarında <strong>özel</strong> seçeneği kullanılabilir. Bu güncelleştirmeden önce, <strong>özel</strong> alan yalnızca iOS cihazları için kullanılabilir. Daha fazla bilgi için bkz. [SCEP sertifika profili oluşturma](../protect/certificates-profile-scep.md).

Bir PKCS sertifika profili oluştururken, **konu alternatif adı**Için **özel Azure ad özniteliği** kullanılabilir. **Departman** seçeneği, **özel Azure ad özniteliği**' ni seçtiğinizde kullanılabilir. Daha fazla bilgi için bkz. [PKCS sertifika profili oluşturma](../protect/certficates-pfx-configure.md#create-a-pkcs-certificate-profile).

#### <a name="configure-multiple-apps-that-can-run-when-an-android-device-is-in-kiosk-mode----662059---"></a>Bir Android cihazı bilgi noktası modundayken çalışabilecek birden çok uygulamayı yapılandırma <!-- 662059 -->
Bir Android cihazı bilgi noktası modundayken, daha önce yalnızca çalışmasına izin verilen bir uygulamayı yapılandırabilirsiniz. Artık uygulama KIMLIĞI, mağaza URL 'SI kullanarak veya zaten yönettiğiniz bir Android uygulamasını seçerek birden çok uygulamayı yapılandırabilirsiniz. Daha fazla bilgi için bkz. [bilgi noktası modu ayarları](../configuration/device-restrictions-android.md#kiosk).

<!-- ########################## -->
## <a name="april-2017"></a>2017 Nisan

### <a name="support-for-managing-the-apple-classroom-app"></a>Apple derslik uygulamasının yönetilmesi için destek
Artık iPad cihazlarda iOS sınıf uygulamasını yönetebilirsiniz. Öğretmen iPad üzerinde, doğru sınıf ve öğrenci verileriyle ders uygulamasını ayarlayın, ardından uygulamayı kullanarak denetleyebilmeniz için bir sınıfa kayıtlı öğrenci Iplüleri yapılandırın.
Ayrıntılar için bkz. [iOS Eğitim ayarlarını yapılandırma](education-settings-configure-ios.md).

### <a name="support-for-managed-configuration-options-for-android-apps----621621---"></a>Android uygulamaları için yönetilen yapılandırma seçenekleri desteği <!-- 621621 -->
Play Store 'da, yönetilen yapılandırma seçeneklerini destekleyen Android uygulamaları artık Intune tarafından yapılandırılabilir.  Bu özellik, bir uygulama tarafından desteklenen yapılandırma değerlerinin listesini görüntülemesine olanak sağlar ve bu değerleri yapılandırmalarına izin vermek için, Kılavuzlu, birinci sınıf bir kullanıcı arabirimi sağlar.

### <a name="new-android-policy-for-complex-pins----722069---"></a>Karmaşık PIN 'Ler için yeni Android İlkesi <!-- 722069 -->
Artık Android 5,0 ve üstünü çalıştıran cihazlar için bir Android cihaz profilinde sayısal karmaşık olarak gerekli bir [parola](../configuration/device-restrictions-android.md#password) türü ayarlayabilirsiniz.  Cihaz kullanıcılarının 1111 veya 1234 gibi yinelenen veya ardışık sayılar içeren bir PIN oluşturmasını engellemek için bu ayarı kullanın.

### <a name="additional-support-for-android-for-work-devices"></a>Android for Work cihazları için ek destek
- **Parola ve iş profili ayarlarını yönetme** <!-- 612808 -->

  Bu yeni Android for Work cihaz kısıtlama ilkesi artık yönettiğiniz Android for Work cihazlarında parola ve iş profili ayarlarını yönetmenizi sağlar.

- **İş ve kişisel profiller arasında veri paylaşımına izin ver** <!-- 1045102 -->

Bu Android for Work cihaz kısıtlama profili artık iş ve kişisel profiller arasında veri paylaşımını yapılandırmanıza yardımcı olacak yeni seçeneklere sahiptir.

- **İş ve kişisel profiller arasında kopyalama ve yapıştırmayı kısıtla** <!-- 1046094 -->

  Android for Work cihazları için yeni bir özel cihaz profili artık iş ve kişisel uygulamalar arasında kopyalama ve yapıştırma eylemlerine izin verilip verilmeyeceğini kısıtlamanızı sağlar.

Daha fazla bilgi için bkz. [Android for Work Için cihaz kısıtlamaları](../configuration/device-restrictions-android-for-work.md).

### <a name="assign-lob-apps-to-ios-and-android-devices----1057568---"></a>İOS ve Android cihazlara LOB uygulamaları atama <!-- 1057568 -->
Artık, [iOS](../apps/lob-apps-ios.md) (. ipa dosyaları) ve [Android](../apps/lob-apps-android.md) (. apk dosyaları) IÇIN iş kolu (LOB) uygulamalarını kullanıcılara veya cihazlara atayabilirsiniz.


### <a name="new-device-policies-for-ios----723774-723815-723826-723830---"></a>İOS için yeni cihaz ilkeleri <!-- 723774, 723815, 723826, 723830 -->
- **Giriş ekranındaki uygulamalar** -kullanıcıların [iOS cihazlarının giriş ekranında](../configuration/ios-device-features-settings.md#home-screen-layout)hangi uygulamaların görmelerini denetler. Bu ilke, giriş ekranının yerleşimini değiştirir, ancak herhangi bir uygulama dağıtmaz.

- **AirPrint cihazlarıyla bağlantı** -iOS cihazının son kullanıcılarının bağlanabileceği [AirPrint cihazlarını](../configuration/ios-device-features-settings.md#airprint) (ağ yazıcılarını) denetler.

- **AirPlay cihazlarıyla bağlantı** -iOS cihazının son kullanıcılarının bağlanabileceği [AirPlay CIHAZLARıNı](../configuration/ios-device-features-settings.md) (Apple TV gibi) denetler.

- **Özel kilit ekranı iletisi** -kullanıcıların, varsayılan kilit ekranı iletisinin yerini aldığı iOS cihazlarının kilit ekranında göreceği özel bir ileti yapılandırır. Daha fazla bilgi için bkz. [iOS cihazlarda kayıp modunu etkinleştirme](../remote-actions/device-lost-mode.md)

### <a name="restrict-push-notifications-for-ios-apps----723767---"></a>İOS uygulamaları için anında iletme bildirimlerini kısıtla <!-- 723767 -->
Bir Intune cihaz kısıtlama profilinde, artık iOS cihazları için aşağıdaki [bildirim ayarlarını](../configuration/ios-device-features-settings.md#app-notifications) yapılandırabilirsiniz:

- Belirtilen bir uygulama için bildirimi tamamen aç veya kapat.
- Belirtilen bir uygulama için bildirim merkezindeki bildirimi açın veya kapatın.
- Uyarı türü, **yok**, **başlık**veya **kalıcı uyarı**belirtin.
- Bu uygulama için rozetlere izin verilip verilmeyeceğini belirtin.
- Bildirim seslerine izin verilip verilmeyeceğini belirtin.

### <a name="configure-ios-apps-to-run-in-single-app-mode-autonomously----737837---"></a>İOS uygulamalarını tek uygulama modunda çalışacak şekilde yapılandırma olarak çalışabilen <!-- 737837 -->
Artık iOS cihazlarını, belirtilen uygulamaları [otonom tek uygulama modunda](../configuration/device-restrictions-ios.md#autonomous-single-app-mode)çalıştıracak şekilde yapılandırmak Için bir Intune cihaz profili kullanabilirsiniz. Bu mod yapılandırıldığında ve uygulama çalıştırıldığında, cihaz yalnızca o uygulamayı çalıştıracak şekilde kilitlenir. Bunun bir örneği, kullanıcıların cihazda bir test geçirmesine imkan tanıyan bir uygulama yapılandırdığınızda oluşur. Uygulamanın eylemleri tamamlandığında veya bu ilkeyi kaldırdığınızda cihaz normal durumuna geri döner.

### <a name="configure-trusted-domains-for-email-and-web-browsing-on-ios-devices----723765---"></a>İOS cihazlarında e-posta ve Web 'e göz atmak için güvenilen etki alanlarını yapılandırma <!-- 723765 -->
Bir iOS cihaz kısıtlama profilinden, artık aşağıdaki [etki alanı ayarlarını](../configuration/device-restrictions-ios.md#domains)yapılandırabilirsiniz:

- **İşaretlenmemiş e-posta etki alanları** -Kullanıcı tarafından gönderilen veya alınan ve burada belirttiğiniz etki alanlarıyla eşleşmeyen e-postalar, güvenilmeyen olarak işaretlenir.

- **Yönetilen Web etki alanları** -burada belirttiğiniz URL 'lerden indirilen belgeler, yönetilen olarak değerlendirilir (yalnızca Safari).  

- **Safari parola otomatik doldur etki alanları** -kullanıcılar, yalnızca burada belirttiğiniz desenlerle eşleşen URL 'lerden oturum açabilirler. Bu ayarı kullanmak için cihazın denetimli modda olması ve birden çok kullanıcı için yapılandırılmamış olması gerekir. (iOS 9,3 +)


### <a name="vpp-apps-available-in-ios-company-portal----748782---"></a>İOS Şirket Portalı 'de bulunan VPP uygulamaları <!-- 748782 -->
Artık iOS toplu satın alınan (VPP) uygulamalarını, son kullanıcılara **kullanılabilir** yüklemeler olarak atayabilirsiniz. Son kullanıcıların uygulamayı yüklemek için bir Apple Mağazası hesabına ihtiyacı olacak.

### <a name="synchronize-ebooks-from-apple-vpp-store----800878---"></a>Apple VPP mağazasından eBooks eşitlemesini <!-- 800878 -->
Artık, Apple Volume Purchase program mağazasından satın aldığınız kitapları Intune ile [eşitleyebilir](../apps/vpp-apps-ios.md) ve bu kitapları kullanıcılara atayabilirsiniz.

### <a name="multi-user-management-for-samsung-knox-standard-devices----971988---"></a>Samsung KNOX Standard cihazları için birden çok kullanıcı yönetimi <!-- 971988 -->
Samsung KNOX Standard çalıştıran cihazlar artık Intune tarafından çok kullanıcılı [Yönetim](../enrollment/android-enroll.md) için desteklenmektedir. Bu, son kullanıcıların Azure Active Directory kimlik bilgileriyle cihazda oturum açıp kaydetmeyeceği ve cihazın kullanımda olup olmadığını merkezi olarak yönetilebilecek anlamına gelir.  Son kullanıcılar oturum açtığında uygulamalara erişimi vardır ve bunlara uygulanan herhangi bir ilkeyi alırlar. Kullanıcılar oturumunu kapattığınızda tüm uygulama verileri temizlenir.

### <a name="additional-windows-device-restriction-settings----818566---"></a>Ek Windows cihaz kısıtlama ayarları <!-- 818566 -->
Ek Microsoft Edge tarayıcı desteği, cihaz kilit ekranı özelleştirmesi, Başlat menüsü özelleştirmeleri, Windows spot araması duvar kağıdı ve proxy ayarı gibi ek [Windows cihaz kısıtlama ayarları](../configuration/device-restrictions-windows-10.md) için destek ekledik.

### <a name="multi-user-support-for-windows-10-creators-update----822547---"></a>Windows 10 Creators Update için çoklu Kullanıcı desteği <!-- 822547 -->
Windows 10 Creators Update çalıştıran ve Azure Active Directory etki alanına katılmış cihazlar için [birden çok kullanıcı yönetimi](../enrollment/windows-enroll.md) desteği ekledik. Diğer bir deyişle, farklı standart kullanıcılar, Azure AD kimlik bilgileriyle cihazda oturum açtığında, Kullanıcı adına atanan tüm uygulama ve ilkeleri alırlar. Kullanıcılar şu anda uygulama yükleme gibi self servis senaryoları için Şirket Portalı kullanamaz.

### <a name="fresh-start-for-windows-10-pcs---1004830---"></a>Windows 10 bilgisayarları için yeni başlangıç<!-- 1004830 -->
Windows 10 bilgisayarları için yeni bir yeni [Başlangıç cihaz eylemi](../remote-actions/device-fresh-start.md) kullanıma sunuldu.  Bu eylemi yaptığınızda, bılgısayarda yüklü olan tüm uygulamalar kaldırılır ve bılgısayar otomatik olarak en son Windows sürümüne güncelleştirilir. Bu, genellikle yeni bir bılgısayarla birlikte sunulan önceden yüklenmiş OEM uygulamalarının kaldırılmasına yardımcı olması için kullanılabilir. Bu cihaz eylemi verildiğinde Kullanıcı verilerinin korunup korunmadığı bir şekilde yapılandırabilirsiniz.

### <a name="additional-windows-10-upgrade-paths----903672---"></a>Ek Windows 10 yükseltme yolları <!-- 903672 -->
Artık, cihazları aşağıdaki ek Windows 10 sürümlerine [yükseltmek için bir sürüm yükseltme ilkesi](../configuration/edition-upgrade-configure-windows-10.md) oluşturabilirsiniz:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional eğitimi
- Windows 10 Professional eğitimi N

### <a name="bulk-enroll-windows-10-devices----747607---"></a>Windows 10 cihazlarını toplu kaydetme <!-- 747607 -->
Artık Windows yapılandırma Tasarımcısı (WCD) ile Azure Active Directory ve Intune için Windows 10 Creators Update çalıştıran çok sayıda cihaza katılabilmeniz gerekir. Azure AD kiracınızda [toplu MDM kaydını](../enrollment/windows-bulk-enroll.md) etkinleştirmek Için Windows yapılandırma Tasarımcısı 'nı kullanarak CIHAZLARı Azure AD kiracınıza birleştiren bir sağlama paketi oluşturun ve paketi toplu kaydetmek ve yönetmek istediğiniz şirkete ait cihazlara uygulayın. Paketler cihazlarınıza uygulandıktan sonra Azure AD 'ye katılır, Intune 'a kaydolur ve Azure AD kullanıcılarınızın oturum açmasını sağlayacak şekilde hazırlanacaktır.  Azure AD kullanıcıları, bu cihazlarda standart kullanıcılardır ve atanan ilkeleri ve gerekli uygulamaları alır. Self servis ve Şirket Portalı senaryoları Şu anda desteklenmiyor.

### <a name="new-mam-settings-for-pin-and-managed-storage-locations----581122-736644---"></a>PIN ve yönetilen depolama konumları için yeni MAM ayarları <!-- 581122, 736644 -->
Mobil uygulama yönetimi (MAM) senaryolarında size yardımcı olacak iki yeni uygulama ayarı artık kullanılabilir:

- **Cihaz PIN 'i yönetildiğinde uygulama PIN 'Ini devre dışı bırak** -kayıtlı cihazda bir cihaz PIN 'inin mevcut olup olmadığını algılar ve bu durumda uygulama koruma ilkeleri tarafından tetiklenen uygulama PIN 'ini atlar. Bu ayar, kayıtlı bir cihazda MAM özellikli bir uygulama açan kullanıcılara bir PIN isteminin kaç kez görüntülendiğini azaltmak için izin verir. Bu özellik hem Android hem de iOS için kullanılabilir.

- **Şirket verilerinin kaydedilenebilir depolama hizmetleri** ' ni seçin-şirket verilerinin kaydedileceği depolama konumlarını belirtmenizi sağlar. Kullanıcılar seçili depolama konumu hizmetleri 'ne kaydedebilir, bu da listelenen diğer tüm depolama konumu hizmetleri engellenecek anlamına gelir.

  Desteklenen depolama konumu hizmetleri listesi:

  - OneDrive
  - İş SharePoint Online
  - Yerel depolama

### <a name="help-desk-troubleshooting-portal----907448---"></a>Yardım Masası sorun giderme portalı <!-- 907448 -->
Yeni [sorun giderme portalı](../help-desk-operators.md) , yardım masası işletmenlerinin ve Intune yöneticilerinin kullanıcıları ve cihazlarını görüntülemesine ve Intune teknik sorunlarını çözmek için görevler gerçekleştirmesine olanak sağlar.

<!-- ########################## -->
## <a name="march-2017"></a>Mart 2017

### <a name="support-for-ios-lost-mode---431695--"></a>İOS kayıp modu desteği <!--431695-->
İOS 9,3 ve üzeri cihazlarda, Intune **kayıp modu**desteği eklemiştir. Artık, tüm kullanımı engellemek ve cihaz kilidi ekranının telefon numarası ile iletişim kurmak için bir cihazı kilitleyebilir.

Yönetici kayıp modunu devre dışı bırakana kadar Son Kullanıcı cihazın kilidini açamaz. Kayıp modu etkin olduğunda cihaz **bul** eylemini kullanarak cihazın coğrafi konumunu Intune konsolundaki bir haritada görüntüleyebilirsiniz.

Cihazın, denetimli modda olan DEP aracılığıyla kaydedilmiş, şirkete ait bir iOS cihazı olması gerekir.

Daha fazla bilgi için bkz. [Microsoft Intune cihaz yönetimi](../remote-actions/device-management.md)nedir?

### <a name="improvements-to-device-actions-report---677150--"></a>Cihaz eylemleri raporuna yönelik iyileştirmeler <!--677150-->
Performansı artırmak için cihaz eylemleri raporunda iyileştirmeler yaptık. Ayrıca, artık raporu duruma göre filtreleyebilirsiniz. Örneğin, yalnızca tamamlanan cihaz eylemlerini göstermek için raporu filtreleyebilirsiniz. "

### <a name="custom-app-categories---748805--"></a>Özel uygulama kategorileri <!--748805-->
Artık Intune 'a eklediğiniz uygulamalar için kategoriler oluşturabilir, düzenleyebilir ve atayabilirsiniz. Şu anda Kategoriler yalnızca Ingilizce olarak belirtilebilir.
Bkz. [Intune 'a uygulama ekleme](../apps/apps-add.md).

### <a name="assign-lob-apps-to-users-with-unenrolled-devices---748823--"></a>Kayıtlı olmayan cihazlara sahip kullanıcılara LOB uygulamaları atama <!--748823-->
Artık, cihazları Intune 'a kayıtlı olup olmadığına bakılmaksızın, kullanıcılara mağazadan iş kolu uygulamalarını atayabilirsiniz. Kullanıcının cihazı Intune 'a kaydedilmediyse, Şirket Portalı uygulaması yerine, yüklemek için Şirket Portalı Web sitesine gitmeleri gerekir.

### <a name="new-compliance-reports---846671--"></a>Yeni uyumluluk raporları <!--846671-->
Artık şirketinizdeki cihazların uyumluluk durumunu sağlayan ve kullanıcılarınızın karşılaştığı uyumlulukla ilgili sorunları hızlı bir şekilde gidermenize izin veren uyumluluk raporlarınız var. Hakkında bilgi görüntüleyebilirsiniz

- Cihazların genel uyumluluk durumu
- Tek bir ayar için uyumluluk durumu
- Tek bir ilkenin uyumluluk durumu

Bu raporları Ayrıca, bu cihazı etkileyen belirli ayarları ve ilkeleri görüntülemek için tek bir cihazın ayrıntılarına gitmek üzere de kullanabilirsiniz.

<!--- You can now create an edition upgrade policy to upgrade devices to the following additional Windows 10 editions:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N --->

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Apple kayıt senaryolarına doğrudan erişim <!--951869-->
Intune, 2017 Ocak 'tan sonra oluşturulan Intune hesaplarında, Azure portal cihazları kaydet iş yükünü kullanarak Apple kayıt senaryolarına doğrudan erişimi etkinleştirdi. Daha önce, Apple kayıt önizlemesine yalnızca Azure portal bağlantılardan erişilebilir. Bu özelliklerin Azure 'da kullanılabilmesi için, Ocak 2017 ' den önce oluşturulan Intune hesaplarında tek seferlik bir geçiş yapılması gerekir. Geçiş zamanlaması henüz duyurulmadı, ancak Ayrıntılar mümkün olan en kısa sürede kullanıma sunulacaktır. Mevcut hesabınız önizlemeye erişemediğimizde yeni deneyimi test etmek için bir deneme hesabı oluşturmanızı kesinlikle öneririz.


<!-- ########################## -->
## <a name="february-2017"></a>Şubat 2017

### <a name="ability-to-restrict-mobile-device-enrollment---747600-795782--"></a>Mobil cihaz kaydını kısıtlama özelliği <!--747600, 795782-->
Intune, hangi mobil cihaz platformlarının kaydetmesine izin verileceğini denetleyen yeni kayıt kısıtlamaları ekliyor. Intune, mobil cihaz platformlarını iOS, macOS, Android, Windows ve Windows Mobile olarak ayırır.

- Mobil cihaz kaydını kısıtlamak, bılgısayar istemci kaydını kısıtlamaz.  
- Yalnızca iOS ve Android için, kişisel cihazların kaydedilmesini engelleyen bir ek seçenek vardır.

BT Yöneticisi [Bu makalede](../enrollment/device-enrollment.md)açıklandığı gibi, BT Yöneticisi tarafından şirkete ait olarak işaretlemek için işlem yapmadığınız sürece Intune tüm yeni cihazları kişisel olarak işaretler.

### <a name="view-all-actions-on-managed-devices---677150--"></a>Yönetilen cihazlarda tüm eylemleri görüntüleme <!--677150-->
Yeni bir __cihaz eylemleri__ raporu, cihazlarda fabrika sıfırlaması gibi uzak eylemleri kimin gerçekleştirmiş olduğunu ve ek olarak bu eylemin durumunu gösterir. Bkz. [cihaz yönetimi nedir?](../remote-actions/device-management.md).

### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Yönetilmeyen cihazlar atanmış uygulamalara erişebilir <!--664691-->
Şirket Portalı Web sitesinde Tasarım değişikliklerinin bir parçası olarak iOS ve Android kullanıcıları, yönetilmeyen cihazlarda "kayıt olmadan kullanılabilir" olarak kendilerine atanmış uygulamaları yükleyebilecektir. Kullanıcılar, Intune kimlik bilgilerini kullanarak Şirket Portalı Web sitesinde oturum açabilirler ve bunlara atanan uygulamaların listesini görebilirler. "Kayıt olmadan kullanılabilir" uygulamaları uygulama paketleri Şirket Portalı Web sitesi aracılığıyla indirilebilir hale getirilir. Yükleme için kayıt gerektiren uygulamalar bu değişiklikten etkilenmez, böylece kullanıcılar bu uygulamaları yüklemek istediklerinde cihazlarını kaydetmeleri istenir.

### <a name="custom-app-categories---748805--"></a>Özel uygulama kategorileri <!--748805-->
Artık Intune 'a eklediğiniz uygulamalar için kategoriler oluşturabilir, düzenleyebilir ve atayabilirsiniz. Şu anda Kategoriler yalnızca Ingilizce olarak belirtilebilir.
Bkz. [Intune 'a uygulama ekleme](../apps/apps-add.md).

### <a name="display-device-categories---814654--"></a>Cihaz kategorilerini görüntüle <!--814654-->
Artık cihaz kategorisini cihaz listesinden bir sütun olarak görebilirsiniz. Kategoriyi cihaz özellikleri dikey penceresinin özellikler bölümünden de düzenleyebilirsiniz. Bkz. [Intune 'a uygulama ekleme](../apps/apps-add.md).

### <a name="configure-windows-update-for-business-settings---776716--"></a>Iş için Windows Update ayarlarını yapılandırma <!--776716-->

Hizmet olarak Windows, Windows 10 için güncelleştirmeleri sağlamanın yeni yoludur. Windows 10 ' dan itibaren tüm yeni özellik güncelleştirmeleri ve kalite güncelleştirmeleri, önceki tüm güncelleştirmelerin içeriğini içerecektir. Bu, en son güncelleştirmeyi yüklediğiniz sürece Windows 10 cihazlarınızın tamamen güncel olduğunu bildiğiniz anlamına gelir. Önceki Windows sürümlerinden farklı olarak, bir güncelleştirmenin parçası yerine artık tüm güncelleştirmeyi yüklemelisiniz.

Iş için Windows Update kullanarak, cihaz gruplarının tek tek güncelleştirmelerini onaylamanız gerekmiyorsa güncelleştirme yönetimi deneyimini basitleştirebilirsiniz. Bir güncelleştirme dağıtım stratejisi yapılandırarak ortamlarınızdaki riski yine de yönetebilir ve Windows Update güncelleştirmelerin doğru zamanda yüklendiğinden emin olur. Microsoft Intune, cihazlarda güncelleştirme ayarlarını yapılandırma olanağı sağlar ve güncelleştirme yüklemesini erteleyebilme olanağı tanır. Intune güncelleştirmeleri depolamaz, ancak yalnızca güncelleştirme ilkesi atamasını depolar. Cihazlar Windows Update doğrudan güncelleştirmeler için erişim. **Windows 10 güncelleştirme halkalarını**yapılandırmak ve yönetmek Için Intune 'u kullanın. Güncelleştirme halkası, Windows 10 güncelleştirmelerinin ne zaman ve nasıl yükleneceğini yapılandıran bir dizi ayar içerir. Ayrıntılar için bkz. [iş için Windows Update yapılandırma](../protect/windows-update-for-business-configure.md).
