---
title: Geliştirme-Microsoft Intune
titleSuffix: ''
description: Geliştirmede Microsoft Intune Özellikler
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/19/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.assetid: 25b3c26e-cf4e-4152-8306-bf4be4af2ad1
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 796439581ca0ae91e788a91ab0bc2ef8f6019626
ms.sourcegitcommit: 01fb3d844958a0e66c7b87623160982868e675b0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74199334"
---
# <a name="in-development-for-microsoft-intune---december-2019"></a>Microsoft Intune için geliştirme sırasında-Aralık 2019

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

### <a name="ios-user-licensed-vpp-apps---5619268-idready---"></a>iOS Kullanıcı lisanslı VPP uygulamaları<!-- 5619268 idready -->
Kullanıcı kaydı iOS cihazlarında, son kullanıcılar artık kullanılabilir olarak dağıtılan cihaz lisanslı VPP uygulamalarıyla birlikte sunulmayacaktır. Ancak, son kullanıcılar Şirket Portalı içindeki Kullanıcı lisanslı tüm VPP uygulamalarını görmeye devam eder. VPP uygulamaları hakkında daha fazla bilgi için bkz. [Microsoft Intune ile Apple Volume Purchase program aracılığıyla satın alınan iOS ve macOS uygulamalarını yönetme](~/apps/vpp-apps-ios.md).

### <a name="retrieve-personal-recovery-key-from-mem-encrypted-macos-devices---4851745-idready---"></a>MEM şifreli macOS cihazlarından kişisel kurtarma anahtarını alma<!-- 4851745 idready -->
Son kullanıcılar, iOS Şirket Portalı uygulamasını kullanarak kişisel kurtarma anahtarını (Filekasası anahtarı) alabilecektir. Kişisel kurtarma anahtarına sahip olan cihaz Intune 'a kaydolmalıdır ve Intune aracılığıyla Filekasasıyla şifrelenir. Son Kullanıcı iOS Şirket Portalı uygulamasını kullanarak Safari web görünümünü açabilir ve kişisel kurtarma anahtarlarını alabilir. Intune 'da, *şifreli ve kayıtlı macOS cihazı* > **kurtarma anahtarı al** > **cihazları** ' nı seçin. Filekasası hakkında daha fazla bilgi için bkz. [macOS Için dosya Kasası şifrelemesi](~/protect/encrypt-devices.md#filevault-encryption-for-macos).

### <a name="microsoft-app-icons-update--4677605--"></a>Microsoft uygulama simgeleri güncelleştirmesi<!--4677605-->
Uygulama koruma ilkeleri ve uygulama yapılandırma ilkeleri için uygulama hedefleme bölmesinde Microsoft uygulamaları için kullanılan simgeler güncelleştirilir.

### <a name="smime-support-for-microsoft-outlook-mobile---2669398----"></a>Microsoft Outlook Mobile için S/MIME desteği<!-- 2669398  -->
Intune, iOS ve Android 'de Outlook Mobile ile kullanılabilen S/MIME imzalama ve şifreleme sertifikalarının teslim edilmesini destekleyecektir. İlgili bilgiler için bkz. [iOS cihazları için e-posta ayarları](~/configuration/email-settings-ios.md) ve [Android cihazlar için e-posta ayarları](~/configuration/email-settings-android.md).

### <a name="custom-settings-support-for-macos-applications---4736278----"></a>MacOS uygulamaları için özel ayarlar desteği<!-- 4736278  -->
Intune, macOS uygulamalarını ve cihazı yapılandırmak için mevcut bir Tercihler özellik listesi (. plist) dosyasına belirli anahtarlar ve değerler eklemenize olanak sağlayan özel ayarları destekleyecektir. Tüm uygulamalar yönetilen tercihleri desteklemez ve bazı durumlarda yalnızca belirli ayarlar yönetilebilir. Ayarlar yalnızca cihaz kanalı aracılığıyla dağıtılır. Yalnızca cihaz kanalı ayarlarını hedef alan özellik listesi dosyalarını veya. xml dosyalarını karşıya yüklemeniz gerekir.

### <a name="display-notifications-for-the-company-portal-app-on-windows---1808082----"></a>Windows 'da Şirket Portalı uygulama için bildirimleri görüntüle<!-- 1808082  -->
Windows cihazlarındaki Şirket Portalı uygulamasını, uygulama kapatıldığında bile kullanıcılara bildirimler görüntüleyecek şekilde güncelleştireceğiz. Güncelleştirme, kullanılabilir uygulamalara ilişkin bildirimleri yalnızca yükleme durumu tamamlandığında veya başarısız olduğunda gösterir. Şirket Portalı uygulama gerekli uygulamalar için bildirimleri göstermez.

### <a name="display-installation-status-messages-for-the-company-portal-app---2514416----"></a>Şirket Portalı uygulaması için yükleme durum iletilerini görüntüle<!-- 2514416  -->
Şirket Portalı uygulama son kullanıcılara ek uygulama yükleme durumu iletileri gösterecektir. Yeni Win32 bağımlılık özellikleri için aşağıdaki koşullar geçerli olacaktır:
- Uygulama yüklenemedi. Yönetici tarafından tanımlanan bağımlılıklar karşılanmadı.

### <a name="configure-app-notification-content-for-organization-accounts---2576686---"></a>Kuruluş hesapları için uygulama bildirim içeriğini yapılandırma<!-- 2576686 -->
Android ve iOS cihazlarında Intune UYGULAMASı, kuruluş hesapları için uygulama bildirim içeriğini denetlemenize olanak tanır. Bu özellik, uygulamalardan destek gerektirecektir ve uygulama özellikli tüm uygulamalar için kullanılamayabilir. UYGULAMA hakkında daha fazla bilgi için bkz. [Uygulama koruma Ilkeleri nelerdir?](../apps/app-protection-policy.md)

<!-- ***********************************************-->
## <a name="device-configuration"></a>Cihaz yapılandırması

### <a name="block-users-from-configuring-certificate-credentials-in-the-managed-keystore-on-android-enterprise-device-owner-devices---3311998-idready---"></a>Kullanıcıların, Android kurumsal cihaz sahibi cihazlarda yönetilen anahtar deposunda sertifika kimlik bilgilerini yapılandırmalarını engelleyin<!-- 3311998 idready -->
Android kurumsal cihaz sahibi cihazlarda, kullanıcıların yönetilen anahtar deposunda (**cihaz yapılandırma** > **profiller** ** > sertifika** kimlik bilgilerini yapılandırmalarını engelleyen yeni bir ayar olacaktır. > **Android Enterprise** for platform > cihaz sahibi yalnızca profil türü > **Kullanıcılar + hesaplar**) için **cihaz kısıtlamalarını >** .

Geçerli ayarları görmek için [Android kurumsal cihaz ayarları ' na giderek Intune kullanarak özelliklere izin verin veya kısıtlayın](../configuration/device-restrictions-android-for-work.md).

Şunun için geçerlidir:
- Adanmış ve tam olarak yönetilen cihazlar dahil Android kurumsal cihaz sahibi

### <a name="wired-network-device-configuration-profiles-for-macos-devices---3508686-idready---"></a>MacOS cihazları için kablolu ağ cihaz yapılandırma profilleri<!-- 3508686 idready -->
MacOS cihazlarında, gelecekteki bir güncelleştirme, kablolu ağları yapılandıran yeni bir cihaz yapılandırma profili (**cihaz yapılandırma** > **profilleri** ** > ,** > Platform için **MacOS** > profil türü için **kablolu ağ** ) içerir. Kablolu ağları yönetmek için 802.1 x profilleri oluşturmak ve bu kablolu ağları macOS cihazlarınıza dağıtmak için bu özelliği kullanın.

Şunun için geçerlidir:
- Mac OS

### <a name="add-automatic-proxy-settings-to-wi-fi-profiles-for-android-enterprise-work-profiles---4490822-idready---"></a>Android kurumsal iş profillerine yönelik Wi-Fi profillerine otomatik ara sunucu ayarları ekleme<!-- 4490822 idready -->
Android kurumsal Iş profili cihazlarında Wi-Fi profilleri oluşturabilirsiniz. Wi-Fi kurumsal türünü seçtiğinizde, Wi-Fi ağınızda kullanılan Genişletilebilir Kimlik Doğrulama Protokolü (EAP) türünü de girebilirsiniz.

Gelecekteki bir güncelleştirmede kurumsal tür ' i seçtiğinizde, `proxy.contoso.com`gibi bir proxy sunucu URL 'SI de dahil olmak üzere otomatik proxy ayarlarını girebilirsiniz.

Yapılandırabileceğiniz geçerli Wi-Fi ayarlarını görmek için [Microsoft Intune ' de Android Enterprise ve Android bilgi noktası çalıştıran cihazlar Için Wi-Fi ayarları ekle](../configuration/wi-fi-settings-android-enterprise.md)' ye gidin.

Şunun için geçerlidir:
- Android kurumsal iş profili

### <a name="enable-network-access-control-nac-with-cisco-anyconnect-vpn-on-ios-devices---4860111-idready---"></a>İOS cihazlarında Cisco AnyConnect VPN ile ağ erişim denetimi 'ni (NAC) etkinleştirme<!-- 4860111 idready -->
İOS cihazlarında, bir VPN profili oluşturabilir ve Cisco AnyConnect (**cihaz yapılandırma** > **profilleri** >  > farklı bağlantı türleri kullanabilirsiniz. Örneğin, bağlantı türü için **Cisco AnyConnect** **> profil** türü için **iOS** > **VPN** platformu. 

Gelecekteki bir güncelleştirmede, Cisco AnyConnect ile ağ erişim denetimi 'ni (NAC) etkinleştirebileceksiniz. Bu özelliği kullanmak için:

1. [Cisco kimlik hizmetleri altyapısı yönetici kılavuzunda](https://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html), Azure 'Da Cisco Identity Services altyapısını (ISE) YAPıLANDıRMAK Için **MDM sunucusu olarak Microsoft Intune yapılandırma** bölümündeki adımları kullanın.
2. Intune cihaz yapılandırma profilinde **ağ Access Control etkinleştir (NAC)** ayarını seçin.

Tüm kullanılabilir VPN ayarlarını görmek için [iOS CIHAZLARıNDA VPN ayarlarını yapılandırma](../configuration/vpn-settings-ios.md)bölümüne gidin.

Şunun için geçerlidir:
- iOS

### <a name="updated-single-sign-on-experience-for-apps-and-websites-on-your-ios-ipados-and-macos-devices---4999578-idready---"></a>İOS, ıpados ve macOS cihazlarınızdaki uygulamalar ve Web siteleri için çoklu oturum açma deneyimi güncelleştirildi<!-- 4999578 idready -->
Intune, iOS, ıpados ve macOS cihazları için daha çoklu oturum açma ayarları ekliyor. Şu anda Intune 'da kimlik bilgisi SSO uygulama uzantılarını ve Apple 'ın yerleşik Kerberos uzantısını yapılandırabilirsiniz. Gelecekteki bir güncelleştirmede, kuruluşunuz tarafından veya kimlik sağlayıcınız tarafından yazılmış yeniden yönlendirme SSO uygulaması uzantılarını yapılandırabileceksiniz. 

OAuth ve SAML2 gibi modern kimlik doğrulama yöntemlerini kullanan uygulamalar ve Web siteleri için sorunsuz bir çoklu oturum açma deneyimi yapılandırmak üzere bu ayarları kullanın. 

Yapılandırabileceğiniz SSO uygulama uzantısı ayarlarını görmek için, [macOS 'Ta](../configuration/macos-device-features-settings.md#single-sign-on-app-extension)IOS ve SSO ['daki SSO](../configuration/ios-device-features-settings.md#single-sign-on-app-extension) ' ya gidin.

Şunun için geçerlidir:
- iOS/ıpados
- Mac OS

### <a name="require-use-of-approved-keyboards-on-android--4761794-idready---"></a>Android üzerinde onaylanan Klavye kullanımını gerektir<!--4761794 IDready -->
Yönetilen Android uygulamalarında kullanılmak üzere onaylanan klavyeler listesini belirleyebileceksiniz. Yönetilen uygulamadan, kullanıcının cihazlarından zaten yüklü olan onaylanmış klavyelerin birine geçmesi istenir veya gerekirse, onaylanan klavyelerin birini indirmek ve ayarlamak için Google Play Store yönlendirilir. Kullanıcı, yönetilen bir uygulamadaki metin alanlarını yalnızca etkin klavyesi onaylanan klavyeleri kullanıyorsa düzenleyebilecektir.

### <a name="use-pkcs-certificates-with-wi-fi-profiles-on-windows-10-and-later-devices---3246388----"></a>Windows 10 ve üzeri cihazlarda Wi-Fi profilleriyle PKCS sertifikaları kullanma<!-- 3246388  -->
Şu anda, Windows Wi-Fi profillerinin kimlik doğrulamasını, SCEP sertifikaları (**cihaz yapılandırma** > **profilleri** > profil **oluşturma** > **Windows 10 ve üzeri** için, > **kurumsal** > **EAP türü**) için bir for platform > **Wi-Fi** . Windows Wi-Fi profilleriniz ile PKCS sertifikalarını kullanabileceksiniz. Bu özellik, kiracınızdaki yeni veya mevcut PKCS sertifika profillerini kullanarak Wi-Fi profillerinin kimlik doğrulamasından geçmesini sağlar. 

Wi-Fi profilleri hakkında daha fazla bilgi için bkz. [Intune 'Da Windows 10 ve üzeri cihazlar Için Wi-Fi ayarları ekleme](../configuration/wi-fi-settings-windows.md).

Şunun için geçerlidir:
- Windows 10 ve üzeri

### <a name="new-exchangeactivesync-settings-when-creating-an-email-device-configuration-profile-on-ios-devices---4892824----"></a>İOS cihazlarında bir e-posta cihaz yapılandırma profili oluştururken yeni ExchangeActiveSync ayarları<!-- 4892824  --> 
İOS/ıpados cihazlarında, bir cihaz yapılandırma profilinde e-posta bağlantısını yapılandırabilirsiniz (**cihaz yapılandırma** > **profilleri** > profil **oluşturmak** > için **IOS/ıpados** > profil türü **e-postası** ). 

Aşağıdakiler dahil olmak üzere yeni ExchangeActiveSync ayarları kullanılabilir olacaktır:
- E-posta, takvim ve kişiler gibi eşitlenecek Hizmetleri (veya eşitlemeyi engellemeyi) seçin.
- Kullanıcıların cihazlarında bu hizmetler için eşitleme ayarlarını değiştirmesine izin verin (veya engelleyin). 

Geçerli ayarları görmek için [Intune 'Da iOS cihazları Için e-posta profili ayarları](../configuration/email-settings-ios.md)' na gidin.

Şunun için geçerlidir:
- iOS 13,0 ve üzeri
- ıpados 13,0 ve üzeri

### <a name="prevent-users-from-adding-personal-google-accounts-to-android-enterprise-device-owner-and-dedicated-devices---5353228----"></a>Kullanıcıların Android kurumsal cihaz sahibine ve adanmış cihazlara kişisel Google hesapları eklemesini engelleyin<!-- 5353228  -->
Kullanıcıların Android kurumsal cihaz sahibine ve adanmış cihazlara (**cihaz yapılandırma** > **profiller** > **profil oluşturmak** Için > **Android Enterprise** > cihaz sahibine yalnızca > **Kullanıcılar ve hesaplar ayarları**için **cihaz kısıtlamaları >** ) sahip kişisel Google hesapları oluşturmasını engelleyebilirsiniz.

Yapılandırabileceğiniz geçerli ayarları görmek için [Android kurumsal cihaz ayarları ' na giderek Intune kullanarak özelliklere izin verin veya kısıtlayın](../configuration/device-restrictions-android-for-work.md).

Şunun için geçerlidir:
- Android kurumsal cihaz sahibi
- Android kurumsal adanmış cihazlar

### <a name="server-side-logging-for-siri-commands-setting-is-removed-in-ios-device-restrictions-profile---5468501----"></a>Siri komutları ayarı için sunucu tarafı günlüğü, iOS cihaz kısıtlamaları profilinde kaldırılıyor<!-- 5468501  -->
İOS cihazlarında, Siri komutları için sunucu tarafında günlüğe kaydetmeyi yapılandıran bir cihaz kısıtlama profili oluşturabilirsiniz (**cihaz yapılandırma** > **profilleri** > profil > **oluşturmak** Için **iOS/ıpados** > **cihaz kısıtlamaları** > **yerleşik uygulamalar**). **Siri komutları Için sunucu tarafı günlüğü** ayarı kaldırılır.

Bu ayar, Intune yönetim konsolundan kaldırılacak. Bu ayarın yapılandırılmış olduğu mevcut ilkeler ayarı göstermeye devam edebilse de, bu ayarın cihaz üzerinde hiçbir etkisi yoktur. Bu ayarı mevcut ilkelerden kaldırmak istiyorsanız, ilkeye gidin, küçük bir düzenleme yapın, kaydedin ve ilke güncelleştirilir.

Yapılandırabileceğiniz ayarları görmek için bkz. [Intune kullanarak özelliklere izin vermek veya erişimi kısıtlamak Için iOS ve ıpados cihaz ayarları](../configuration/device-restrictions-ios.md).

Şunun için geçerlidir:
- iOS

<!-- ***********************************************-->
<!--## Device enrollment-->

<!-- ***********************************************-->
## <a name="device-management"></a>Cihaz yönetimi



### <a name="edit-device-name-value-for-autopilot-devices---2640074----"></a>Autopilot cihazlar için cihaz adı değerini Düzenle<!-- 2640074  -->
Azure AD 'ye katılmış Autopilot cihazları için cihaz adı değerini düzenleyebileceksiniz. Bunu yapmak için **Intune** 'a gidin > **cihaz kaydı** > **windows kaydı** > **Windows Autopilot** > **cihazları** > sağ bölmedeki cihaz **adı** değerini değiştirin > **Kaydet**' e tıklayın.

### <a name="edit-the-group-tag-value-for-autopilot-devices---4816775---"></a>Autopilot cihazlar için Grup etiketi değerini düzenleme<!-- 4816775 -->
Autopilot cihazlar için **Grup etiketi** değerini düzenleyebileceksiniz:

1. **Intune** > **cihaz kaydı** > Windows **kaydı** > **Windows Autopilot** > **cihazları**' nı seçin.
1. Cihazı seçin.
1. Sağdaki bölmede, **Grup etiketi** değerini değiştirin.
1. **Kaydet**’i seçin.

### <a name="target-macos-user-groups-to-require-jamf-management---4061739---"></a>JAMF yönetimini gerektirecek macOS Kullanıcı gruplarını hedefleme<!-- 4061739 -->
Belirli kullanıcı gruplarını, macOS cihazlarının JAMF tarafından yönetilmesini gerektirecek şekilde hedefleyebilir. Bu hedefleme, diğer cihazlar Intune tarafından yönetilmeye devam ederken, bir macOS cihazları alt kümesine JAMF uyumluluk tümleştirmesini uygulamanızı sağlayacaktır. Hedefleme, kullanıcıların cihazlarını bir mobil cihaz yönetimi (MDM) sisteminden diğerine kademeli olarak geçireceğinizi de sağlar.

<!-- ***********************************************-->
## <a name="intune-apps"></a>Intune uygulamaları

### <a name="improved-macos-enrollment-experience-in-company-portal---5074349----"></a>Şirket Portalı 'de geliştirilmiş macOS kayıt deneyimi<!-- 5074349  -->
MacOS kayıt deneyimi için Şirket Portalı, iOS kayıt deneyimi için Şirket Portalı daha yakından uyum sağlayacak daha basit bir kayıt işlemine sahip olacaktır. Cihaz kullanıcıları şunları görür:  

* Bir uyleyici Kullanıcı arabirimi.  
* İyileştirilmiş bir kayıt denetim listesi.  
* Cihazlarını nasıl kaydedebileceğinize ilişkin daha net yönergeler.  
* Gelişmiş sorun giderme seçenekleri.  

<!-- ***********************************************-->
## <a name="monitoring-and-troubleshooting"></a>İzleme ve sorun giderme

### <a name="centralized-audit-logs--5603185-5697164--"></a>Merkezi denetim günlükleri<!--5603185, 5697164-->
Yeni bir merkezi denetim günlüğü deneyimi, tüm kategorilerin denetim günlüklerini tek bir sayfada toplar. Arama yaptığınız verileri almak için günlükleri filtreleyebileceksiniz. Denetim günlüklerini görmek için, **kiracı yönetimi** > **Denetim günlükleri**' ne gidin. Daha fazla bilgi için bkz. [Intune 'Da denetim günlüklerine yaklaşan değişiklikler](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Upcoming-change-to-Audit-logs-in-Intune/ba-p/1015858).

<!-- ***********************************************-->
## <a name="role-based-access-control"></a>Rol tabanlı erişim denetimi

### <a name="duplicate-custom-or-built-in-roles---1081938---"></a>Yinelenen özel veya yerleşik roller<!-- 1081938 -->
Yerleşik ve özel rolleri kopyalayabileceksiniz. Bunu yapmak için **ıntune** > **Roller** > **tüm roller** ' e gidin > listede bir rol seçin > **Yinele**' ye tıklayın. Benzersiz olan yeni bir ad girdiğinizden emin olun.

<!-- ***********************************************-->

## <a name="security"></a>Güvenlik

### <a name="use-pkcs-certificate-profiles-to-provision-devices-with-certificates---2317124-2317130-2317139-2340517-2340528-2340529-idready---"></a>Sertifikalar ile cihaz sağlamak için PKCS sertifika profillerini kullanma<!-- 2317124, 2317130, 2317139, 2340517, 2340528, 2340529 IDready -->
Cihazlara sertifika vermek için, Kullanıcı tabanlı sertifikalara yönelik geçerli desteğimizi genişleterek bir PKCS sertifika profili kullanabilirsiniz. Cihaz tabanlı sertifikalar, Android, iOS ve Windows platformlarını desteklenecektir ve Wi-Fi ve VPN profilleri için kullanılabilir.

<!-- ***********************************************-->
## <a name="notices"></a>Bildirimler

[!INCLUDE [Intune notices](../includes/intune-notices.md)]

## <a name="see-also"></a>Ayrıca bkz:
Son gelişmeler hakkında daha fazla bilgi için bkz. [Microsoft Intune](whats-new.md)yenilikleri.


