---
title: Geliştirme-Microsoft Intune
titleSuffix: ''
description: Geliştirmede Microsoft Intune Özellikler
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/28/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.assetid: 25b3c26e-cf4e-4152-8306-bf4be4af2ad1
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4beb9c841cb2f4a5b7198fe031caa67da9e28842
ms.sourcegitcommit: 4bf23327af734a9811d555fbd566c31239e2acd6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2019
ms.locfileid: "72999430"
---
# <a name="in-development-for-microsoft-intune---november-2019"></a>Microsoft Intune için geliştirme sırasında-Kasım 2019

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

### <a name="smime-support-for-microsoft-outlook-mobile----2669398----"></a>Microsoft Outlook Mobile için S/MIME desteği <!-- 2669398  -->
Intune, iOS ve Android 'de Outlook Mobile ile kullanılabilen S/MIME imzalama ve şifreleme sertifikalarının teslim edilmesini destekleyecektir. İlgili bilgiler için bkz. [iOS cihazları için e-posta ayarları](~/configuration/email-settings-ios.md) ve [Android cihazlar için e-posta ayarları](~/configuration/email-settings-android.md).

### <a name="custom-settings-support-for-macos-applications----4736278----"></a>MacOS uygulamaları için özel ayarlar desteği <!-- 4736278  -->
Intune, macOS uygulamalarını ve cihazı yapılandırmak için mevcut bir Tercihler özellik listesi (. plist) dosyasına belirli anahtarlar ve değerler eklemenize olanak sağlayan özel ayarları destekleyecektir. Tüm uygulamalar yönetilen tercihleri desteklemez ve bazı durumlarda yalnızca belirli ayarlar yönetilebilir. Ayarlar yalnızca cihaz kanalı aracılığıyla dağıtılır. Yalnızca cihaz kanalı ayarlarını hedef alan özellik listesi dosyalarını veya. xml dosyalarını karşıya yüklemeniz gerekir.

### <a name="assignment-type-value-in-windows-company-portal----5459950----"></a>Windows Şirket Portalı atama türü değeri <!-- 5459950  -->
Windows Şirket Portalı uygulamasının **yüklü uygulamalar** sayfası güncelleştirilecektir. **Yüklü uygulamalar** sayfasının **atama türü** sütunu, "kuruluşunuz tarafından gerektirilir" olarak güncelleştirilmiştir. Gerekli ve kullanılabilir uygulamaları belirlemek için, olası değerler **Evet** veya **Hayır** ' tir. Bu değişiklik, bazı Son Kullanıcı karışıklığına yanıt olarak yapılıyor. Windows Şirket portalı hakkında daha fazla bilgi için bkz. [Microsoft Intune şirket portalı uygulamasını yapılandırma](~/apps/company-portal-app.md).

### <a name="apply-dark-mode-in-ios-company-portal----4911422----"></a>İOS Şirket Portalı koyu modunu Uygula <!-- 4911422  -->
Koyu modda iOS Şirket Portalı planlanmaktadır. Şirket uygulamalarını indirebilir, cihazlarınızı yönetebilir ve tercih ettiğiniz renk şemasında bu destek alabilirsiniz. İOS Şirket Portalı hakkında daha fazla bilgi için bkz. [Microsoft Intune şirket portalı uygulamasını yapılandırma](../apps/company-portal-app.md).

### <a name="run-win32-apps-on-windows-10-s-mode-devices----3747604----"></a>Win32 uygulamalarını Windows 10 S modu cihazlarda çalıştırma <!-- 3747604  --> 
Windows 10 S modunda yönetilen cihazlara Win32 uygulamaları yükleyip çalıştırabileceksiniz. Windows Defender uygulama denetimi (WDAC) PowerShell araçlarını kullanarak S modu için bir veya daha fazla ek ilke oluşturun. Ek ilkeleri imzalamak için Device Guard imzalama portalını kullanın. Ardından Intune aracılığıyla ilkeleri karşıya yükleyin ve dağıtın. 

Intune 'da, bu özelliği **istemci uygulamalar** > **Windows 10 S ek ilkeleri**' ni seçerek bulacaksınız. 

### <a name="set-app-availability-based-on-a-date-and-time----3510685----"></a>Bir tarih ve saate göre uygulama kullanılabilirliğini ayarlama <!-- 3510685  -->
Yönetici olarak, gerekli bir uygulama için başlangıç saatini ve son tarihi yapılandırabileceksiniz. Başlangıç zamanında, Intune yönetim uzantısı uygulama içeriğini indirir ve önbelleğe alacak. Uygulama son tarihte yüklenecektir. Kullanılabilir uygulamalar için, uygulama Şirket Portalı görünür olduğunda başlangıç saati görüntülenir. 

Uygulama kullanılabilirliğini tarih ve saate göre ayarlamak için:

1. Intune 'da, **istemci uygulamaları** > **uygulamalar**' ı seçin. 
1. Listeden bir uygulama seçin veya **Ekle**' yi seçerek yeni bir tane ekleyin. 
1. Uygulama dikey penceresinde **atamalar** > **Grup Ekle**' yi seçin. 
1. **Atama türünü** **gerekli** olarak ayarlayın ve ardından **dahil edilen gruplar**' ı seçin. 
1. **Bu uygulamayı tüm kullanıcılar için gerekli yap** ayarını **Evet**olarak belirleyin. 
1. **Son Kullanıcı deneyimi** seçeneklerini değiştirmek için **Düzenle** ' yi seçin. 
1. **Son Kullanıcı deneyimi** dikey penceresinde, gereken **yazılım kullanım süresini** ayarlayın. 

Daha fazla bilgi için bkz. [Microsoft Intune’a uygulama ekleme](../apps/apps-add.md).

### <a name="require-win32-apps-to-restart----3136567----"></a>Win32 uygulamalarının yeniden başlatılmasını gerektir <!-- 3136567  -->
Başarılı bir yüklemeden sonra bir Win32 uygulamasının yeniden başlatılmasını isteyebilirsiniz. Yeniden başlatmadan önce geçen süreyi (yetkisiz kullanım süresi) seçebilirsiniz.

### <a name="display-notifications-for-the-company-portal-app-on-windows----1808082----"></a>Windows 'da Şirket Portalı uygulama için bildirimleri görüntüle <!-- 1808082  -->
Windows cihazlarındaki Şirket Portalı uygulamasını, uygulama kapatıldığında bile kullanıcılara bildirimler görüntüleyecek şekilde güncelleştireceğiz. Güncelleştirme, kullanılabilir uygulamalara ilişkin bildirimleri yalnızca yükleme durumu tamamlandığında veya başarısız olduğunda gösterir. Şirket Portalı uygulama gerekli uygulamalar için bildirimleri göstermez.

### <a name="display-installation-status-messages-for-the-company-portal-app----2514416----"></a>Şirket Portalı uygulaması için yükleme durum iletilerini görüntüle <!-- 2514416  -->
Şirket Portalı uygulama son kullanıcılara ek uygulama yükleme durumu iletileri gösterecektir. Yeni Win32 bağımlılık özellikleri için aşağıdaki koşullar geçerli olacaktır:
- Uygulama yüklenemedi. Yönetici tarafından tanımlanan bağımlılıklar karşılanmadı.
- Uygulama başarıyla yüklendi, ancak yeniden başlatma gerekiyor.
- Uygulama yükleme sürecinde, ancak devam etmek için yeniden başlatma gerekiyor.

### <a name="configure-app-notification-content-for-organization-accounts----2576686---"></a>Kuruluş hesapları için uygulama bildirim içeriğini yapılandırma <!-- 2576686 -->
Android ve iOS cihazlarında Intune UYGULAMASı, kuruluş hesapları için uygulama bildirim içeriğini denetlemenize olanak tanır. Bu özellik, uygulamalardan destek gerektirecektir ve uygulama özellikli tüm uygulamalar için kullanılamayabilir. UYGULAMA hakkında daha fazla bilgi için bkz. [Uygulama koruma Ilkeleri nelerdir?](../apps/app-protection-policy.md)


<!-- ***********************************************-->
## <a name="device-configuration"></a>Cihaz yapılandırması

### <a name="use-pkcs-certificates-with-wi-fi-profiles-on-windows-10-and-later-devices----3246388----"></a>Windows 10 ve üzeri cihazlarda Wi-Fi profilleriyle PKCS sertifikaları kullanma <!-- 3246388  -->
Şu anda Windows Wi-Fi profillerinin kimlik doğrulamasını, SCEP sertifikaları (**cihaz yapılandırma** > **profilleri** > için **windows 10 ve üzeri** platform > **Wi-Fi** için > **oluşturma** > **kurumsal** > **EAP türü**) profil türü. Windows Wi-Fi profilleriniz ile PKCS sertifikalarını kullanabileceksiniz. Bu özellik, kiracınızdaki yeni veya mevcut PKCS sertifika profillerini kullanarak Wi-Fi profillerinin kimlik doğrulamasından geçmesini sağlar. 

Wi-Fi profilleri hakkında daha fazla bilgi için bkz. [Intune 'Da Windows 10 ve üzeri cihazlar Için Wi-Fi ayarları ekleme](../configuration/wi-fi-settings-windows.md).

Uygulama hedefi:
- Windows 10 ve üzeri

### <a name="new-exchangeactivesync-settings-when-creating-an-email-device-configuration-profile-on-ios-devices----4892824----"></a>İOS cihazlarında bir e-posta cihaz yapılandırma profili oluştururken yeni ExchangeActiveSync ayarları <!-- 4892824  --> 
İOS/ıpados cihazlarında, bir cihaz yapılandırma profilinde (**cihaz yapılandırma** > **profiller** > **profil oluşturma** > **IOS/ıpados** > **e-posta** ile e-posta bağlantısını yapılandırabilirsiniz profil türü için). 

Aşağıdakiler dahil olmak üzere yeni ExchangeActiveSync ayarları kullanılabilir olacaktır:
- E-posta, takvim ve kişiler gibi eşitlenecek Hizmetleri (veya eşitlemeyi engellemeyi) seçin.
- Kullanıcıların cihazlarında bu hizmetler için eşitleme ayarlarını değiştirmesine izin verin (veya engelleyin). 

Geçerli ayarları görmek için [Intune 'Da iOS cihazları Için e-posta profili ayarları](../configuration/email-settings-ios.md)' na gidin.

Uygulama hedefi:
- iOS 13,0 ve üzeri
- ıpados 13,0 ve üzeri

### <a name="prevent-users-from-adding-personal-google-accounts-to-android-enterprise-device-owner-and-dedicated-devices----5353228----"></a>Kullanıcıların Android kurumsal cihaz sahibine ve adanmış cihazlara kişisel Google hesapları eklemesini engelleyin <!-- 5353228  -->
Kullanıcıların Android kurumsal cihaz sahibi ve adanmış cihazlarda (**cihaz yapılandırma** > **profiller** > , Android Enterprise > **profil oluşturma** ) kişisel Google hesapları oluşturmasını engelleyebilirsiniz.platform > cihaz sahibi yalnızca > **Kullanıcı ve hesap ayarları**) profil türü için **cihaz kısıtlamalarını >** .

Yapılandırabileceğiniz geçerli ayarları görmek için [Android kurumsal cihaz ayarları ' na giderek Intune kullanarak özelliklere izin verin veya kısıtlayın](../configuration/device-restrictions-android-for-work.md).

Uygulama hedefi:
- Android kurumsal cihaz sahibi
- Android kurumsal adanmış cihazlar

### <a name="server-side-logging-for-siri-commands-setting-is-removed-in-ios-device-restrictions-profile----5468501----"></a>Siri komutları ayarı için sunucu tarafı günlüğü, iOS cihaz kısıtlamaları profilinde kaldırılıyor <!-- 5468501  -->
İOS cihazlarında, Siri komutları için sunucu tarafında günlüğe kaydetmeyi yapılandıran bir cihaz kısıtlama profili oluşturabilirsiniz (**cihaz yapılandırma** > **profilleri** > platform Için **iOS/ıpados** > **profil oluşturma** > **Yerleşik uygulamalar**> profil türü için **cihaz kısıtlamalarını** . **Siri komutları Için sunucu tarafı günlüğü** ayarı kaldırılır.

Bu ayar, Intune yönetim konsolundan kaldırılacak. Bu ayarın yapılandırılmış olduğu mevcut ilkeler ayarı göstermeye devam edebilse de, bu ayarın cihaz üzerinde hiçbir etkisi yoktur. Bu ayarı mevcut ilkelerden kaldırmak istiyorsanız, ilkeye gidin, küçük bir düzenleme yapın, kaydedin ve ilke güncelleştirilir.

Yapılandırabileceğiniz ayarları görmek için bkz. [Intune kullanarak özelliklere izin vermek veya erişimi kısıtlamak Için iOS ve ıpados cihaz ayarları](../configuration/device-restrictions-ios.md).

Uygulama hedefi:
- iOS


<!-- ***********************************************-->
<!--## Device enrollment-->

<!-- ***********************************************-->
## <a name="device-management"></a>Cihaz yönetimi

### <a name="edit-device-name-value-for-autopilot-devices---2640074----"></a>Autopilot cihazlar için cihaz adı değerini Düzenle<!-- 2640074  -->
Azure AD 'ye katılmış Autopilot cihazları için cihaz adı değerini düzenleyebileceksiniz. Bunu yapmak için **Intune** 'a gidin > **cihaz kaydı** > **windows kayıt** > **Windows Autopilot** > **cihazları** > cihazı seçin > sağ bölmedeki **Cihaz adı** değerini değiştirin > **Kaydedin**.


### <a name="edit-the-group-tag-value-for-autopilot-devices---4816775---"></a>Autopilot cihazlar için Grup etiketi değerini düzenleme<!-- 4816775 -->
Autopilot cihazlar için **Grup etiketi** değerini düzenleyebileceksiniz:

1. **Intune** > **cihaz kaydı** > **Windows kaydı** > **Windows Autopilot** > **cihazları**' nı seçin.
1. Cihazı seçin.
1. Sağdaki bölmede, **Grup etiketi** değerini değiştirin.
1. **Kaydet**’i seçin.

### <a name="target-macos-user-groups-to-require-jamf-management----4061739---"></a>JAMF yönetimini gerektirecek macOS Kullanıcı gruplarını hedefleme <!-- 4061739 -->
Belirli kullanıcı gruplarını, macOS cihazlarının JAMF tarafından yönetilmesini gerektirecek şekilde hedefleyebilir. Bu hedefleme, diğer cihazlar Intune tarafından yönetilmeye devam ederken, bir macOS cihazları alt kümesine JAMF uyumluluk tümleştirmesini uygulamanızı sağlayacaktır. Hedefleme, kullanıcıların cihazlarını bir mobil cihaz yönetimi (MDM) sisteminden diğerine kademeli olarak geçireceğinizi de sağlar.

<!-- ***********************************************-->
## <a name="intune-apps"></a>Intune uygulamaları

### <a name="improved-macos-enrollment-experience-in-company-portal----5074349----"></a>Şirket Portalı 'de geliştirilmiş macOS kayıt deneyimi <!-- 5074349  -->
MacOS kayıt deneyimi için Şirket Portalı, iOS kayıt deneyimi için Şirket Portalı daha yakından uyum sağlayacak daha basit bir kayıt işlemine sahip olacaktır. Cihaz kullanıcıları şunları görür:  

* Bir uyleyici Kullanıcı arabirimi.  
* İyileştirilmiş bir kayıt denetim listesi.  
* Cihazlarını nasıl kaydedebileceğinize ilişkin daha net yönergeler.  
* Gelişmiş sorun giderme seçenekleri.  

### <a name="improved-checklist-design-in-company-portal-app-for-android---5550857----"></a>Android için Şirket Portalı App 'te geliştirilmiş denetim listesi tasarımı<!-- 5550857  -->
Android için Şirket Portalı uygulamasındaki kurulum denetim listesi, hafif bir tasarım ve yeni simgelerle güncelleştirilir. Değişiklikler, iOS için Şirket Portalı uygulamasına yapılan son güncelleştirmelerle hizalanır.

<!-- ***********************************************-->
## <a name="monitoring-and-troubleshooting"></a>İzleme ve sorun giderme

### <a name="updated-support-experience-------5012398------"></a>Güncelleştirilmiş destek deneyimi   <!--  5012398    -->
Geliştirmeye devam etmenin bir parçası olarak, Intune için konsol içi destek deneyimini güncelleştireceğiz.  Genel sorunlar için konsol içi arama ve geri bildirim işlemlerini geliştireceğiz ve destek ile iletişim kurmak için iş akışını kolaylaştırıyoruz.     

<!-- ***********************************************-->
## <a name="role-based-access-control"></a>Rol tabanlı erişim denetimi

### <a name="duplicate-custom-or-built-in-roles----1081938---"></a>Yinelenen özel veya yerleşik roller <!-- 1081938 -->
Yerleşik ve özel rolleri kopyalayabileceksiniz. Bunu yapmak için **ıntune** > **Roller** > **tüm roller** ' e gidin > listede bir rol seçin > **Yinele**' ye tıklayın. Benzersiz olan yeni bir ad girdiğinizden emin olun.

<!-- ***********************************************-->

## <a name="security"></a>Güvenlik

### <a name="bitlocker-key-rotation--------2564951--------"></a>BitLocker anahtar döndürme     <!-- 2564951      -->
Windows sürüm 1909 veya üzerini çalıştıran yönetilen cihazların BitLocker kurtarma anahtarlarını döndürmek için Intune 'U kullanabilirsiniz. 

<!-- ***********************************************-->
## <a name="notices"></a>Bildirimler

[!INCLUDE [Intune notices](../includes/intune-notices.md)]

## <a name="see-also"></a>Ayrıca bkz:
Son gelişmeler hakkında daha fazla bilgi için bkz. [Microsoft Intune](whats-new.md)yenilikleri.
