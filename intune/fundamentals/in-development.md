---
title: Geliştirme-Microsoft Intune
titleSuffix: ''
description: Geliştirmede Microsoft Intune Özellikler
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/03/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.assetid: 25b3c26e-cf4e-4152-8306-bf4be4af2ad1
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: e099537bce6327e9a8991bc42f406e4abd3dfd2e
ms.sourcegitcommit: 6608dc70d01376e0cd90aa620a2fe01337f6a2f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2020
ms.locfileid: "78260240"
---
# <a name="in-development-for-microsoft-intune---march-2020"></a>Microsoft Intune için geliştirme sırasında-Mart 2020

Hazırlık ve planlamada yardımcı olması için bu sayfada Intune Kullanıcı Arabirimi güncelleştirmeleri ve geliştirme aşamasında olan ancak henüz yayınlanmayan özellikler listelenir. Bu sayfadaki bilgilere ek olarak: 

- Bir değişiklikten önce işlem yapmanız gerektiğini düşünüyorsanız, Office ileti merkezi 'nde tamamlayıcı bir gönderi yayımlayacağız.
- Bir özellik üretim girdiğinde, bir önizleme veya genel kullanıma sunulduktan sonra özellik açıklaması bu [sayfadan yenilikler 'e taşınır.](whats-new.md)
- Bu [sayfa ve yenilikler sayfası düzenli](whats-new.md) aralıklarla güncelleştirilir. Ek güncelleştirmeleri daha sonra denetleyin.
- Stratejik teslim edilebilirler ve zaman çizelgeleri için [Microsoft 365 yol haritasını](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS) inceleyin.

> [!NOTE]
> Bu sayfa, gelecekteki bir sürümde Intune özelliklerine ilişkin geçerli beklentilerimizi yansıtır. Tarihler ve bireysel Özellikler değişebilir. Bu sayfa, geliştirmede tüm özellikleri tanımlamaz.

**RSS akışı**: Şu URL 'yi kopyalayıp akış okuyucunuzun içine yapıştırarak bu sayfanın ne zaman güncelleştirileceğini öğrenin: `https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`

<!--
## What's coming to Intune in the Azure portal 
## What's coming to Intune apps
## Notices
-->

<!-- Common categories:  
## App management
## Device configuration
## Device enrollment
## Device management
## Intune apps
## Monitor and troubleshoot
## Role-based access control
## Security

-->
 
<!-- ***********************************************-->
## <a name="app-management"></a>Uygulama yönetimi

### <a name="retarget-web-clips-to-microsoft-edge-on-iosipados-devices---5455276---"></a>Web kliplerini iOS/ıpados cihazlarında Microsoft Edge 'e yeniden hedefle<!-- 5455276 -->
İOS/ıpados cihazlarında sabitlenmiş Web uygulamaları olarak davranan web klipleri güncelleştirilmeleri gerekecektir. Yeni dağıtılan web klipleri, korumalı bir tarayıcıda açmak gerekirse Intune Managed Browser yerine Microsoft Edge 'de açılır. Managed Browser yerine Microsoft Edge 'de açıldıklarından emin olmak için önceden mevcut web kliplerini yeniden hedeflemeniz gerekir.

### <a name="macos-and-ios-company-portal-updates---5779439-5780234----"></a>macOS ve iOS Şirket Portalı güncelleştirmeleri<!-- 5779439, 5780234  -->
MacOS ve iOS Şirket Portalı profil bölmesi, oturumu Kapat düğmesine dahil olacak şekilde güncelleştirilecektir. Ayrıca, bu güncelleştirme, macOS Şirket Portalı profil bölmesine yönelik kullanıcı arabirimi geliştirmelerini içerir. Şirket Portalı hakkında daha fazla bilgi için bkz. [Microsoft Intune şirket portalı uygulamasını yapılandırma](~/apps/company-portal-app.md).

### <a name="updates-to-branding-and-customization-pane---5236032---"></a>Marka ve özelleştirme bölmesindeki güncelleştirmeler<!-- 5236032 -->
Şu anda "marka ve özelleştirme" adlı Intune bölmesini, aşağıdakiler de dahil olmak üzere güncelleştiriyoruz:

- Bölmeyi **özelleştirmek**için yeniden adlandırma.
- Kuruluş ve ayarların tasarımını geliştirme.
- Ayarlar metin ve araç ipuçlarını geliştirme.

Bu ayarı Intune 'da bulmak için [Microsoft Endpoint Manager Yönetim Merkezi](https://go.microsoft.com/fwlink/?linkid=2109431) ' ne gidin ve **Kiracı Yönetimi** > **Özelleştirme**' yi seçin. Varolan özelleştirme hakkında daha fazla bilgi için bkz. [Microsoft Intune şirket portalı uygulamasını yapılandırma](~/apps/company-portal-app.md).

### <a name="configure-the-ios-microsoft-azure-ad-sso-app-extension---567534----"></a>İOS Microsoft Azure AD SSO uygulama uzantısını yapılandırma<!-- 567534  -->
Microsoft Azure AD ekibi, iOS ve ıpados 13.0 + kullanıcılarına tek bir oturum açma ile Microsoft uygulamalarına ve Web sitelerine sorunsuz bir şekilde erişim elde etmesine olanak tanımak için bir yeniden yönlendirme çoklu oturum açma (SSO) uygulama uzantısı geliştirmektedir. AAD SSO uygulama uzantısı yayımlandığında, SSO uzantısını en az tıklamayla Yönetici konsolundaki **Çoklu oturum açma uygulama uzantısı** profili > **cihaz özellikleriyle** yapılandırabileceksiniz. 

İOS SSO uygulama uzantıları veya cihaz özelliklerinin nasıl yapılandırılacağı hakkında daha fazla bilgi için bkz. [Çoklu oturum açma uygulama uzantısı](~/configuration/device-features-configure.md#single-sign-on-app-extension).

### <a name="company-portal-for-ios-to-support-landscape-mode--6048329----"></a>İOS için Şirket Portalı yatay modunu destekleyecek şekilde<!--6048329  -->
Kullanıcılar cihazlarını kaydedebilir, uygulama bulabilir ve tercih ettikleri ekran yönünü kullanarak BT desteği alabilir. Kullanıcılar ekranı dikey modda kilitlemedikleri takdirde uygulama ekranları dikey veya yatay moda uyacak şekilde otomatik olarak algılar ve ayarlar. 

### <a name="configure-if-enrollment-is-available-in-company-portal-for-android-and-ios---4260128-idready-idstaged---"></a>Şirket Portalı, Android ve iOS için kayıt için kullanılabilir olup olmadığını yapılandırın<!-- 4260128 idready idstaged -->
Android ve iOS cihazlarındaki Şirket Portalı cihaz kaydının, istemler olmadan kullanılabilir veya kullanıcılar için kullanılamaz durumda olup olmadığını yapılandırmanıza olanak tanıyan yeni bir ayar sunulacaktır. Bu ayarı Intune 'da bulmak için [Microsoft Endpoint Manager Yönetim Merkezi](https://go.microsoft.com/fwlink/?linkid=2109431) ' ne gidin ve > **cihaz kaydını** **düzenlemek** > **Kiracı Yönetimi** > **Özelleştirme** ' yi seçin. Varolan Şirket Portalı özelleştirmesi hakkında daha fazla bilgi için bkz. [Microsoft Intune şirket portalı uygulamasını yapılandırma](~/apps/company-portal-app.md).

### <a name="improved-sign-in-experience-in-company-portal-for-android---6103997----"></a>Android için Şirket Portalı 'de geliştirilmiş oturum açma deneyimi<!-- 6103997  -->
Daha modern, basit ve kullanıcılar için temiz bir deneyim sunmak amacıyla Android için Şirket Portalı uygulamasındaki çeşitli oturum açma ekranlarının yerleşimini güncelleştiriyoruz.

<!-- ***********************************************-->
## <a name="device-configuration"></a>Cihaz yapılandırması

### <a name="wired-network-device-configuration-profiles-for-macos-devices---3508686----"></a>MacOS cihazları için kablolu ağ cihaz yapılandırma profilleri<!-- 3508686  -->
Kablolu ağları yapılandıran yeni bir macOS cihaz yapılandırma profili kullanılabilir (**cihaz yapılandırma** > **profilleri** ** > ,** > Platform için **MacOS** > profil türü için **kablolu ağ** ). Kablolu ağları yönetmek için 802.1 x profilleri oluşturmak ve bu kablolu ağları macOS cihazlarınıza dağıtmak için bu özelliği kullanın.

Uygulama alanı:
- Mac OS

### <a name="vpn-profiles-with-ikev2-vpn-connections-can-use-always-on-with-iosipados-devices----1947932----"></a>IKEv2 VPN bağlantılarına sahip VPN profilleri, her zaman iOS/ıpados cihazlarıyla birlikte kullanılabilir <!-- 1947932  -->
İOS/ıpados cihazlarında, Ikev2 bağlantısı kullanan bir VPN profili oluşturabilirsiniz (**cihaz yapılandırma** > **profilleri** > profil **oluşturmak** için **iOS/IPA> DOS > iOS/ıpados** ). Gelecekteki bir güncelleştirmede, her zaman Ikev2 ile yapılandırabilirsiniz. Yapılandırıldığında, IKEv2 VPN profilleri otomatik olarak bağlanır ve VPN 'ye bağlı (veya hızlı bir şekilde yeniden bağlantı) kalır. Ağlar arasında hareket etmekle veya cihazları yeniden başlatırken bile bağlı kalır.

İOS/ıpados 'da, her zaman VPN Ikev2 profilleriyle sınırlıdır.

Yapılandırabileceğiniz geçerli Ikev2 ayarlarını görmek için [Microsoft Intune ' deki iOS/ıpados CIHAZLARıNDA VPN ayarları ekle](../configuration/vpn-settings-ios.md#ikev2-settings)' ye gidin.

Uygulama alanı:
- iOS

### <a name="improved-user-interface-experience-when-creating-configuration-profiles-on-iosipados-and-macos-devices---5569008-5569039-5569057-5569110-5569116-5569131-5569139-5569153-5859984----"></a>İOS/ıpados ve macOS cihazlarında yapılandırma profilleri oluştururken Geliştirilmiş kullanıcı arabirimi deneyimi<!-- 5569008-5569039-5569057-5569110-5569116-5569131-5569139-5569153-5859984  -->
İOS/ıpados veya macOS cihazları için bir profil oluşturduğunuzda, uç nokta yönetimi Yönetim Merkezi 'ndeki deneyim güncelleştirilir. Bu değişiklik, aşağıdaki cihaz yapılandırma profillerini**etkiler (cihaz** > **yapılandırma profilleri** > platform Için **iOS** veya **MacOS** > **profili oluşturma** ):

- Özel: iOS/ıpados, macOS
- Cihaz özellikleri: iOS/ıpados, macOS
- Cihaz kısıtlamaları: iOS/ıpados, macOS
- Endpoint Protection: macOS
- Uzantılar: macOS
- Tercih dosyası: macOS

### <a name="improved-user-interface-experience-when-creating-oemconfig-configuration-profiles-on-android-enterprise-devices---5568645-----"></a>Android kurumsal cihazlarda OEMConfig yapılandırma profilleri oluştururken Geliştirilmiş kullanıcı arabirimi deneyimi<!-- 5568645   -->
Android Kurumsal cihazları için bir OEMConfig profili oluştururken veya düzenlerken, Endpoint Management Yönetim Merkezi 'ndeki deneyim güncellenir. Güncelleştirilmiş deneyim, bir bakışta yapılandırdığınız ayarların özetini sağlayacaktır. Bu değişiklik, OEMConfig cihaz yapılandırma profilini (**cihazlar** > **yapılandırma profillerini** etkiler > platform için **Android Enterprise** >, profil türü için **oemconfig** ) > **oluşturur** .

Bu özellik şu platformlarda geçerlidir:
- Android Kurumsal 

### <a name="enterprise-app-trust-settings-modification-setting-will-be-removed-from-iosipados-device-restriction-profiles---6225131----"></a>Kurumsal uygulama güven ayarları değiştirme ayarı, iOS/ıpados cihaz kısıtlama profillerden kaldırılacak<!-- 6225131  -->
İOS/ıpados cihazlarında, bir cihaz kısıtlama profili (**cihazlar** > **yapılandırma profilleri** oluşturma > profil **oluşturma** için **iOS/IPA> DOS** > profil türü için **cihaz kısıtlamaları** ) oluşturun. **Kurumsal uygulama güven ayarları değiştirme** ayarı Apple tarafından kaldırılacak ve Intune 'dan kaldırılacak. Şu anda bu ayarı bir profilde kullanıyorsanız, bir etkisi yoktur ve yeni bir profil oluşturana kadar profilinizde kalır. Bu ayar ayrıca, Intune 'daki herhangi bir raporlamadan da kaldırılır.

Uygulama alanı:
- iOS/iPadOS

Kısıtlayacakları ayarları görmek için [iOS ve ıpados cihaz ayarları ' na giderek özelliklere izin verin veya kısıtlayın](../configuration/device-restrictions-ios.md).

### <a name="device-configuration-profile-settings-and-values-will-be-updated-for-windows-platforms---4091122---"></a>Cihaz yapılandırma profili ayarları ve değerleri Windows platformları için güncelleştirilecektir<!-- 4091122 -->
Windows platformları için cihaz yapılandırma profilleri oluşturduğunuzda (**cihaz** > **yapılandırma profilleri** > platform için herhangi bir **Windows** seçeneği > **profil oluşturma** ), bazı ayarlar ve bunların değerleri CSP 'den farklıdır ve kafa karıştırıcı olabilir. Ayar adları ve değerleri daha açık olacak şekilde güncelleştirilecektir.

Uygulama alanı:

- Windows 10 ve üzeri cihaz yapılandırma profilleri
- Windows holographic for Business cihaz yapılandırma profilleri
- Windows 8.1 cihaz yapılandırma profilleri
- Windows Phone 8,1 cihaz yapılandırma profilleri

### <a name="improved-user-interface-experience-when-creating-device-restrictions-profiles-on-android-and-android-enterprise-devices---5841361---"></a>Android ve Android kurumsal cihazlarda cihaz kısıtlama profilleri oluştururken Geliştirilmiş kullanıcı arabirimi deneyimi<!-- 5841361 -->
Android veya Android Kurumsal cihazları için bir profil oluşturduğunuzda, uç nokta yönetimi Yönetim Merkezi 'ndeki deneyim güncelleştirilir. Bu değişiklik aşağıdaki cihaz yapılandırma profillerini etkiler (**cihazlar** > **yapılandırma profilleri** > **profil oluşturma** > **Android Cihaz Yöneticisi** veya platform için **Android Enterprise** ):

- Cihaz kısıtlamaları: Android Cihaz Yöneticisi
- Cihaz kısıtlamaları: Android kurumsal cihaz sahibi
- Cihaz kısıtlamaları: Android kurumsal iş profili

Yapılandırabileceğiniz cihaz kısıtlamaları hakkında daha fazla bilgi için bkz. [Android Cihaz Yöneticisi](../configuration/device-restrictions-android.md) ve [Android Enterprise](../configuration/device-restrictions-android-for-work.md).

### <a name="delete-bundles-and-bundle-arrays-in-oemconfig-device-configuration-profiles-on-android-enterprise-devices---5550355----"></a>Android kurumsal cihazlarda OEMConfig cihaz yapılandırma profillerindeki paketleri ve paket dizilerini silme<!-- 5550355  -->
Android kurumsal cihazlarda, OEMConfig profilleri oluşturun ve güncelleştirin. Kullanıcılar, Intune 'daki **yapılandırma tasarımcısını** kullanarak paket ve paket dizilerini silebilir.

OEMConfig profilleri hakkında daha fazla bilgi için bkz. [Microsoft Intune 'de oemconfig Ile Android Kurumsal cihazları kullanma ve yönetme](../configuration/android-oem-configuration-overview.md).

Bu özellik şu platformlarda geçerlidir:
- Android Kurumsal

### <a name="support-for-wpa-and-wpa2-in-ios-enterprise-wi-fi-profiles--6215273-----"></a>İOS Enterprise Wi-Fi profillerinde WPA ve WPA2 desteği<!--6215273   -->
*Güvenlik türü* alanını [IOS için Enterprise Wi-Fi profiline](../configuration/wi-fi-settings-ios.md) (**cihazlar** > **yapılandırma profilleri** > **Profil oluştur** ve *Platform* Için **iOS/ıpados** ' ı ve *profil* için **Wi-Fi** ' i seçin) ekliyoruz. Bu, iOS için temel bir Wi-Fi profili için kullanılabilen seçeneklere benzerdir. Bu değişiklik ile, **WPA-Kuruluş** veya **WPA/WPA2-Kuruluş**güvenlik türünü belirten yeni profiller oluşturabilir ve ardından *EAP türü*için bir seçim belirtebilirsiniz.

### <a name="new-user-experience-for-certificate-email-vpn-and-wi-fi-profiles---5615208-----"></a>Sertifika, e-posta, VPN ve Wi-Fi profilleri için yeni kullanıcı deneyimi<!-- 5615208   -->
, Aşağıdaki profil türlerini oluşturmak ve değiştirmek için uç nokta yönetimi Yönetim merkezinde (**cihazlar** > **yapılandırma profilleri** > **profil oluşturma**) [Kullanıcı deneyimini](../configuration/device-profile-create.md) güncelleştirdi. Yeni deneyim daha önce olduğu gibi aynı ayarları sunacaktır, ancak çok yatay kaydırma gerektirmeyen sihirbaza benzer bir deneyim kullanır. Mevcut konfigürasyonları yeni deneyimle değiştirmeniz gerekmez.
- Türetilmiş kimlik bilgileri
- E-posta
- PKCS sertifikası
- PKCS içeri aktarılmış sertifikası
- SCEP sertifikası
- Güvenilir sertifika
- VPN
- Wi-Fi

(**Cihazlar** > **yapılandırma profillerini** **Profil oluştur** > ve sonra *profil türü* için önceki profillerden herhangi birini seçin.)

### <a name="configure-the-microsoft-defender-atp-app-for-macos-----5520115----"></a>MacOS için Microsoft Defender ATP uygulamasını yapılandırma  <!-- 5520115  -->
Yakında bir Endpoint Protection cihaz yapılandırma profilinin parçası olarak macOS çalıştıran cihazlar için Microsoft Defender ATP uygulamasının [ayarlarını](../protect/endpoint-protection-macos.md) yapılandırabilirsiniz (**cihaz** > **yapılandırma profillerinin** > **profil oluşturma**, *Platform*için **MacOS** ve ardından *profil türü*için **Endpoint Protection** ). MacOS cihaz yapılandırması için sekiz ayar olacaktır. 

Defender ATP, macOS 10,13 (High Sierra) ve üzeri sürümlerde desteklenir ve bu ayar uygulandıktan *sonra* [Microsoft Defender ATP](../apps/apps-advanced-threat-protection-macos.md) uygulamasının cihaza dağıtılması gerekir. Uygulama dağıtılmadan önce ayarların cihaza gönderilmesi gerekir. MacOS 'un beta sürümleri desteklenmez.

### <a name="new-filevault-setting-for-macos-endpoint-protection-device-configuration-policy---5459801-----"></a>MacOS Endpoint Protection cihaz yapılandırma ilkesi için yeni Filekasası ayarı<!-- 5459801   -->
[MacOS Endpoint Protection](../protect/endpoint-protection-macos.md) şablonu Içindeki filekasası kategorisine yeni bir ayar ekliyoruz: kurtarma anahtarını gizleyin. (**Cihazlar** > **yapılandırma profillerini** **Profil oluştur** > , *Platform* için **MacOS** ' u ve ardından *profil türü*için **Endpoint Protection** ' ı seçin. Bu ayar, Filekasa2 şifrelemesi sırasında son kullanıcıdan kişisel anahtarı gizler. Bir cihaz kullanıcısı, kişisel kurtarma anahtarını iOS şirket portalı uygulamasından veya şifrelenmiş macOS cihazının Şirket portalı Web sitesinden dilediğiniz zaman görüntüleyebilir. Kişisel kurtarma anahtarını görüntülemek için cihaz ayrıntılarına gidebilir ve *Kurtarma anahtarı al*' a tıklayabilirsiniz.

Bu ayar, önceden oluşturulan ilkede kullanılamaz. Bu ayarı kullanmak üzere yapılandırmak için dosya Kasası ilkelerini yeniden oluşturmanız gerekir. 

###  <a name="ui-update-when-configuring-compliance-policy----3961639----"></a>Uyumluluk ilkesini yapılandırırken kullanıcı arabirimi güncelleştirmesi <!-- 3961639  -->
Microsoft Endpoint Manager 'daki uyumluluk ilkelerini yapılandırma kullanıcı arabirimini (**cihazlar** > **Uyumluluk Ilkeleri** > **ilkeleri** **ilke oluştur** > güncelleştiriyoruz. Daha önce kullandığınız ayarların ve ayrıntıların aynısını sağlayan yeni bir kullanıcı deneyimi görürsünüz. Yeni deneyim, bir uyumluluk ilkesi oluşturmak için sihirbaza benzer bir işlem izler ve ilke için *atamalar* ekleyebileceğiniz sayfayı ve ilkeyi oluşturmadan önce yapılandırmanızı gözden geçirebileceğiniz bir *Özet* sayfasını içerir. 

### <a name="configure-delivery-optimization-agent-when-downloading-win32-app-content---5410945----"></a>Win32 uygulama içeriğini indirirken teslim Iyileştirme aracısını yapılandırma<!-- 5410945  -->
Teslim Iyileştirme aracısını, atamaya göre arka planda veya ön plan modunda Win32 uygulama içeriğini indirmek için yapılandırabileceksiniz. Mevcut Win32 uygulamaları için içerik arka plan modunda indirilmeye devam edecektir. [Microsoft Endpoint Manager Yönetim Merkezi](https://go.microsoft.com/fwlink/?linkid=2109431)'Nde, **cihaz** > **yapılandırma profilleri** > **Profil oluştur**' u seçin. **Platform**olarak **Windows 10 ve üzeri '** i seçin. **Profil türü**altında **teslim iyileştirmesi**' nı seçin. Teslim Iyileştirme hakkında daha fazla bilgi için bkz. [Win32 uygulama yönetimi-teslim iyileştirmesi](~/apps/apps-win32-app-management.md#delivery-optimization).


<!-- ***********************************************-->
<!--## Device enrollment-->

<!-- ***********************************************-->
## <a name="device-management"></a>Cihaz yönetimi

### <a name="change-primary-user-for-windows-devices----3794742---"></a>Windows cihazları için birincil kullanıcıyı değiştirme <!-- 3794742 -->
Windows karma ve Azure AD 'ye katılmış cihazlar için birincil kullanıcıyı değiştirebileceksiniz. Bunu yapmak için **ıntune** > **cihazlar** > **tüm cihazlar** ' a gidin > bir cihaz > **özellikleri** > **birincil Kullanıcı**seçin. 

### <a name="new-android-report-on-android-devices-overview-page---5435435---"></a>Android cihazlarına yeni Android raporuna genel bakış sayfası<!-- 5435435 -->
Her bir cihaz yönetimi çözümüne kaç tane Android cihaz kaydedildiğini gösteren Android cihazlara Genel Bakış sayfasında Microsoft Endpoint Manager yönetim konsoluna bir rapor ekliyoruz. Bu grafik (Azure konsolunda aynı grafik gibi), iş profilini, tam olarak yönetilen, adanmış ve Cihaz Yöneticisi kayıtlı cihaz sayısını gösterir. Raporu görmek için **cihazlar** > **Android** > **genel bakış**' ı seçin.

### <a name="powershell-scripts-support-for-byod-devices---1862833----"></a>KCG cihazları için PowerShell betikleri desteği<!-- 1862833  -->
PowerShell betikleri, Intune 'da Azure AD kayıtlı cihazlarını destekleyecektir. PowerShell hakkında daha fazla bilgi için bkz. [Intune 'Da Windows 10 cihazlarda PowerShell betiklerini kullanma](~/apps/intune-management-extension.md). Bu işlevsellik, Windows 10 Home Edition çalıştıran cihazları desteklemez.

### <a name="additional-data-warehouse-device-inventory-properties---6125732----"></a>Ek veri ambarı cihaz envanteri özellikleri<!-- 6125732  -->
Intune veri ambarı kullanılarak ek cihaz envanteri özellikleri sunulacaktır. Aşağıdaki özellikler [cihazlar](~/developer/intune-data-warehouse-collections.md#devices) koleksiyonu aracılığıyla kullanıma sunulacaktır:
- Depolama kapasitesi 
- Bellek kapasitesi
- Office 365 sürümü
- Cihaz modeli

Veri ambarı hakkında daha fazla bilgi için bkz. [Microsoft Intune veri ambarı API 'si](~/developer/reports-nav-intune-data-warehouse.md).

### <a name="guide-users-from-android-device-administrator-management-to-work-profile-management--5857738--"></a>Android Cihaz Yöneticisi yönetiminden iş profili yönetimine kadar Kullanıcı Kılavuzu<!--5857738-->
Android Cihaz Yöneticisi platformu için yeni bir uyumluluk ayarı yayınlıyoruz. Bu ayar cihaz yöneticisiyle yönetiliyorsa bir cihazı uyumsuz hale getirme olanağı sağlar.

Uyumlu olmayan bu cihazlarda, **cihaz ayarlarını Güncelleştir** sayfasında kullanıcılar **yeni cihaz yönetimi kurulum** iletisi ' ne git ' i görür. Bunlar **Çözümle** düğmesine dokunduğunda şu şekilde gezinirler:

1. Cihaz Yöneticisi yönetiminden kaydı geri al
2. İş profili yönetimine kaydolma
3. Uyumluluk sorunlarını çözme 
 
Google, Android Enterprise ile modern, daha zengin ve daha güvenli cihaz yönetimine geçme çabasında yeni Android sürümlerindeki Cihaz Yöneticisi desteğini düşürdüğünde.  Intune, yalnızca S2 CY2020 aracılığıyla Android 10 ve üzeri çalıştıran cihaz yönetici tarafından yönetilen Android cihazları için tam destek sağlayabilir. Android 10 veya sonraki sürümleri çalıştıran Cihaz Yöneticisi tarafından yönetilen cihazlar (Samsung hariç), tamamen yönetilemez. Özellikle, etkilenen cihazlar yeni parola gereksinimleri almaz. Daha fazla bilgi için bu [bildirimin](#decreasing-support-for-android-device-administrator)bölümüne bakın.

### <a name="retire-noncompliant-devices---1827291---"></a>Uyumsuz cihazları devre dışı bırak<!-- 1827291 -->
Uyumsuz bir cihazı devre dışı bırakmaya yönelik yeni bir isteğe bağlı uyumluluk eylemi ekledik (**cihaz** > **uyumluluk ilkeleri** > **ilkeleri** **Ilke oluştur** > ve ardından *uyumsuzluk için Eylemler* sayfasında kullanılabilir *eylemleri* görüntüler).  Uyumsuz bir cihazı devre dışı bırakma, bundan tüm şirket verilerini kaldırır ve ayrıca cihazın Intune tarafından yönetilmesini da kaldırır. Bu eylem, gün cinsinden yapılandırılan değere ulaşıldığında çalışır. Minimum değer 30 gündür.  Yöneticilerin uygun olan tüm cihazları devre dışı bırakabileceği *uyumlu olmayan cihazları devre* dışı bırak bölümü kullanılarak cihazları devre dışı bırakmak IÇIN açık BT yöneticisi onayı gerekecektir.

### <a name="new-information-in-device-details---5604099---"></a>Cihaz ayrıntılarında yeni bilgiler<!-- 5604099 -->
Aşağıdaki bilgiler cihazların **genel bakış** sayfasında olacaktır:
- Depolama kapasitesi (cihazdaki fiziksel depolama miktarı)
- Bellek kapasitesi (cihazdaki fiziksel bellek miktarı)

### <a name="script-support-for-macos-devices---4280361----"></a>MacOS cihazları için betik desteği<!-- 4280361  -->
MacOS cihazlarına komut dosyaları ekleyebilir ve bunları dağıtabileceksiniz. Bu destek, MacOS cihazlarındaki yerel MDM yeteneklerini kullanarak, macOS cihazlarını mümkün olduğunca fazla yapılandırma yeteneğinizi genişletmektedir. 

<!-- ***********************************************-->
<!--## Intune apps-->
 

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
## <a name="monitor-and-troubleshoot"></a>İzleme ve sorun giderme

### <a name="help-and-support-workflow-update-to-support-additional-services---5654170---"></a>Ek hizmetleri desteklemek için yardım ve destek iş akışı güncelleştirmesi<!-- 5654170 -->
Microsoft Endpoint Manager Yönetim merkezinde yardım ve destek sayfasını güncelleştiriyoruz. böylece, belirli destek sağlamak için kullandığınız yönetim türünü (**sorun giderme + destek** >  **Yardım ve destek**) seçebileceksiniz. Bu değişiklik ile aşağıdaki yönetim türlerinden seçim yapabilirsiniz:
- Configuration Manager (Masaüstü analizlerini içerir)
- Intune
- Ortak yönetim

<!-- ***********************************************-->
<!--
## Role-based access control
-->

<!-- ***********************************************-->
## <a name="security"></a>Güvenlik

### <a name="derived-credentials-support-on-android-cobo-devices--4839592--"></a>Android COBO cihazlarında türetilmiş kimlik bilgileri desteği<!--4839592-->
Android kurumsal tam olarak yönetilen cihazlarda türetilmiş kimlik bilgilerini kullanabilirsiniz. Entrust Datacard, ıntercede ve DıŞA purebred için türetilmiş bir kimlik bilgisi almak üzere destek eklenecektir. Uygulama kimlik doğrulaması, Wi-Fi, VPN veya S/MIME imzalama ve/veya şifrelemeyi destekleyen uygulamalarla şifreleme için türetilmiş bir kimlik bilgisi kullanabileceksiniz.

### <a name="use-antivirus-policy-to-manage-settings-for-microsoft-defender-antivirus-and-the-windows-security-experience--6131401---"></a>Microsoft Defender virüsten koruma ve Windows Güvenlik deneyimiyle ilgili ayarları yönetmek için virüsten koruma ilkesini kullanın<!--6131401 -->
*Uç nokta güvenlik* düğümünden **Virüsten koruma**ayarlarını yapılandırabileceksiniz. İlkeyi virüsten koruma için yapılandırdığınızda, Windows 10 cihazlarınızın ayarlarını iki profil türü aracılığıyla tanımlayacaksınız:

- Microsoft Defender virüsten koruma: bulut koruması, virüsten koruma dışlamaları, düzeltme, tarama seçenekleri ve daha fazlası için ayarları yönetin.
- Windows Güvenlik deneyimi: kullanıcıların cihazlarında Windows güvenlik ayarlarını nasıl deneymelerini yönetin. Microsoft Defender Güvenlik Merkezi 'nde ve aldıkları bildirimlerde son kullanıcıların neleri görüntüleyebileceklerini yapılandırabileceksiniz.

### <a name="users-personal-encrypted-recovery-key---6273943---"></a>Kullanıcının kişisel şifreli kurtarma anahtarı<!-- 6273943 -->
Kullanıcıların, Android Şirket Portalı uygulaması veya Android Intune uygulaması aracılığıyla Mac cihazları için kişisel şifreli **Filekasasını** kurtarma anahtarını almasına olanak sağlayan yeni bir Intune özelliği sunulacaktır. Kullanıcının Mac cihazlarına erişmek için gereken **Filekasasını** kurtarma anahtarını görebildiği, Web şirket portalı bir Chrome tarayıcısı açan Şirket portalı uygulama ve Intune uygulamasında bir bağlantı olacaktır. Şifreleme hakkında daha fazla bilgi için bkz. [Intune ile cihaz şifrelemesini kullanma](~/protect/encrypt-devices.md).

### <a name="privacy-preferences-settings-for-macos-devices---2934232---"></a>MacOS cihazları için Gizlilik Tercihleri ayarları<!-- 2934232 --> 
MacOS Catalina 10,15 sürümü sayesinde, Apple yeni güvenlik ve gizlilik iyileştirmeleri ekledi. Varsayılan olarak, uygulamalar ve süreçler Kullanıcı izni olmadan belirli verilere erişemez. Kullanıcılar onay sağlamıyorsa, uygulamalar ve süreçler çalışmayabilir. Intune, macOS 10,14 ve üstünü çalıştıran cihazlarda son kullanıcılar adına, BT yöneticilerinin veri erişimine izin vermesini veya bu izni vermemeyi sağlayan ayarlar için destek ekliyor. Bu ayarlar, uygulamaların ve işlemlerin düzgün şekilde çalışmaya devam etmesini ve son kullanıcıların deneyimlerine yönelik istem sayısını azaltmasını sağlar. 

### <a name="updated-ui-text-and-labels-for-windows-10-endpoint-protection-profile-settings---5983747---"></a>Windows 10 Endpoint Protection profili ayarları için Kullanıcı arabirimi metni ve Etiketler güncelleştirildi<!-- 5983747 -->
Kullanım ve sonuç olarak tasarlanan ayarları daha kolay anlamak için Windows 10 cihaz yapılandırma profilleri olarak yapılandırdığınız çeşitli ayarların metnini güncelleştiriyoruz. 

Güncelleştiriyoruz ayarlar şunlar için Windows 10 cihaz yapılandırma profillerini içerir: 
- Microsoft Defender virüsten koruma > [cihaz kısıtlamaları](../configuration/device-restrictions-windows-10.md#microsoft-defender-antivirus)  
- [Endpoint Protection](../protect/endpoint-protection-windows-10.md) > Microsoft Defender virüsten koruma

Intune ile desteklenen ayarlar değişmemektedir. Bu yalnızca Microsoft uç nokta yönetimi Yönetim Merkezi 'ndeki Kullanıcı arabirimi metnine yönelik bir güncelleştirmedir. 


<!-- ***********************************************-->
## <a name="notices"></a>Bildirimler

[!INCLUDE [Intune notices](../includes/intune-notices.md)]

## <a name="see-also"></a>Ayrıca bkz.
Son gelişmeler hakkında daha fazla bilgi için bkz. [Microsoft Intune](whats-new.md)yenilikleri.



