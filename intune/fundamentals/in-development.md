---
title: Geliştirme-Microsoft Intune
titleSuffix: ''
description: Geliştirmede Microsoft Intune Özellikler
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/07/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.assetid: 25b3c26e-cf4e-4152-8306-bf4be4af2ad1
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: fa3309cc1aad3f82499e37cf0d009da336b15cca
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72502752"
---
# <a name="in-development-for-microsoft-intune---october-2019"></a>Microsoft Intune için geliştirme sırasında-Ekim 2019

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

### <a name="include-another-app-configuration-variable----4969237----"></a>Başka bir uygulama yapılandırma değişkeni Ekle <!-- 4969237  -->
Bir uygulama yapılandırma ilkesi oluştururken, `AAD Device ID` yapılandırma değişkenini yapılandırma ayarlarınızın bir parçası olarak dahil edebilirsiniz. 

@No__t-0 yapılandırma değişkenini eklemek için:
1. Intune 'da, **istemci uygulamaları** > **uygulama yapılandırma ilkeleri** > **Ekle**' yi seçin. 
1. Yapılandırma ilkesi ayrıntılarınızı girin.
1. **Yapılandırma ayarları** dikey penceresini görüntülemek için **yapılandırma ayarları**' nı seçin.

### <a name="apply-dark-mode-in-ios-company-portal----4911422----"></a>İOS Şirket Portalı koyu modunu Uygula <!-- 4911422  -->
Koyu modda iOS Şirket Portalı planlanmaktadır. Şirket uygulamalarını indirebilir, cihazlarınızı yönetebilir ve tercih ettiğiniz renk şemasında bu destek alabilirsiniz. İOS Şirket Portalı hakkında daha fazla bilgi için bkz. [Microsoft Intune şirket portalı uygulamasını yapılandırma](../apps/company-portal-app.md).

### <a name="prevent-installation-of-apps-from-unknown-sources-on-android-enterprise-devices----4760025----"></a>Android kurumsal cihazlarda bilinmeyen kaynaklardan uygulama yüklenmesini engelleyin <!-- 4760025  -->
Android kurumsal iş profili cihazlarında, son kullanıcılar hiçbir uygulamayı iş profilindeki bilinmeyen kaynaklardan hiçbir şekilde yükleyemez. Bu kısıtlamayı da kişisel profille genişletmeyi tercih edebilirsiniz. Bu kısıtlamayı etkinleştirirseniz, Android kurumsal iş profili cihazlarındaki son kullanıcılar, bilinmeyen kaynaklardan gelen uygulamaları cihazlarınızın kişisel tarafına dışarıdan yükleyemeyecektir. 

### <a name="use-an-updated-app-protection-ui-and-ios-app-provisioning-ui----4102027-4102029----"></a>Güncelleştirilmiş bir uygulama koruma Kullanıcı arabirimi ve iOS uygulama sağlama Kullanıcı arabirimi kullanma <!-- 4102027, 4102029  -->
Intune 'da uygulama koruma ilkeleri (uygulama) ve iOS uygulama sağlama profilleri oluşturmak ve düzenlemek için Kullanıcı arabirimini güncelleştireceğiz. UI değişiklikleri şunları içerir:
- Bir dikey pencerede Sihirbaz stili biçim kullanan Basitleştirilmiş bir deneyim. 
- Atamaları eklemek için akış oluşturma için bir güncelleştirme.
- Özet. Yeni bir ilke oluşturmadan veya bir özelliği düzenlerken, özellikleri görüntülediğinizde tüm ayarların Özet sayfasını görürsünüz. Ayrıca, özellikleri düzenlediğinizde Özet yalnızca düzenlemekte olduğunuz özelliklerin kategorisinden öğeleri listeler.

### <a name="create-groups-of-management-objects-called-policy-sets----3762880----"></a>İlke kümeleri olarak adlandırılan yönetim nesnesi grupları oluşturma <!-- 3762880  -->
Tek bir kavramsal birim olarak tanımlanması, hedeflenecek ve izlenmemesi gereken mevcut yönetim varlıklarına başvuru grubu oluşturmak için *ilke kümelerini* kullanabilirsiniz. İlke kümeleri varolan kavramları veya nesneleri değiştirmez. Yöneticiler, nesneleri bugün olduğu gibi ayrı ayrı atamaya devam edebilir. İlke ayrı nesneleri başvuru olarak ayarlar. Bu nedenle, bağımsız nesnelerde yapılan tüm değişiklikler ilke kümesine yansıtılır. 

Intune 'da bir ilke kümesi oluşturmak için,  > **Oluştur** **ilke kümelerini**seçersiniz. 

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

### <a name="assign-the-microsoft-edge-beta-for-macos----4678761----"></a>MacOS için Microsoft Edge Beta 'yı atama <!-- 4678761  -->
MacOS cihazları için Microsoft Edge Beta 'nın en son sürümünü Intune 'a ekleyip atayabileceksiniz. 

MacOS cihazları için Microsoft Edge Beta 'yı atamak için:
1. Intune 'da **istemci uygulamaları** > **uygulamalar** > **Uygulama Ekle** > **Microsoft Edge-MacOS**' u seçin. 
1. Microsoft Edge Beta 'yı amaçlanan gruplara atayın. Microsoft otomatik güncelleştirme (MAU), Microsoft Edge 'i güncel tutar. 
 
Microsoft Edge hakkında daha fazla bilgi için, [Microsoft Intune Ile Microsoft Edge kullanarak Web erişimini yönetme](../apps/manage-microsoft-edge.md)makalesine bakın.

### <a name="configure-app-notification-content-for-organization-accounts----2576686---"></a>Kuruluş hesapları için uygulama bildirim içeriğini yapılandırma <!-- 2576686 -->
Android ve iOS cihazlarında Intune UYGULAMASı, kuruluş hesapları için uygulama bildirim içeriğini denetlemenize olanak tanır. Bu özellik, uygulamalardan destek gerektirecektir ve uygulama özellikli tüm uygulamalar için kullanılamayabilir. UYGULAMA hakkında daha fazla bilgi için bkz. [Uygulama koruma Ilkeleri nelerdir?](../apps/app-protection-policy.md)

### <a name="available-google-play-app-reporting-for-android-work-profiles----3041956----"></a>Android iş profilleri için kullanılabilir Google Play uygulama raporlaması <!-- 3041956  -->
Android iş profili cihazlarındaki kullanılabilir uygulama yüklemeleri için, uygulama yükleme durumunu ve yönetilen Google Play uygulamalarının yüklü sürümünü görüntüleyebilirsiniz. Daha fazla bilgi için bkz. [Uygulama koruma ilkelerini izleme](../apps/app-protection-policies-monitor.md), [Intune ile Android iş profili cihazlarını yönetme](../enrollment/android-enterprise-overview.md)ve [yönetilen Google Play uygulama türleri](../apps/apps-add-android-for-work.md#managed-google-play-app-types).

<!-- ***********************************************-->
## <a name="device-configuration"></a>Cihaz yapılandırması


### <a name="new-device-configuration-settings-for-supervised-ios-and-ipados-devices----5199328----"></a>Denetimli iOS ve ıpados cihazları için yeni cihaz yapılandırma ayarları <!-- 5199328  -->
İOS ve ıpados cihazlarında, cihazlarda özellikleri ve ayarları kısıtlamak için bir profil oluşturabilirsiniz:

1. **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**'u seçin.
1. Platform için **iOS/ıpados**' ı seçin.
1. Profil türü için **cihaz kısıtlamaları**' nı seçin.

Yeni ayarları denetleyebileceksiniz: 
- Dosyalar uygulamasındaki ağ sürücüsüne erişin.  
- Dosyalar uygulamasındaki USB sürücüsüne erişin. 
- Wi-Fi ' ı açık tutun. 

Geçerli ayarlar hakkında daha fazla bilgi için bkz. [Intune kullanarak özelliklere izin vermek veya erişimi kısıtlamak Için iOS cihaz ayarları](../configuration/device-restrictions-ios.md).

Yeni ayarlar için geçerlidir:
- iOS 13,0 ve üzeri.
- ıpados 13,0 ve üzeri.

### <a name="removal-of-automatic-connection-in-wi-fi-profiles-on-android-and-android-enterprise----5021055----"></a>Android ve Android Enterprise 'ta Wi-Fi profillerindeki otomatik bağlantının kaldırılması <!-- 5021055  -->
Android ve Android kurumsal cihazlarda, farklı ayarları yapılandırmak için bir Wi-Fi profili oluşturabilirsiniz: 

1. **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**'u seçin.
1. Platform için **Android** veya **Android Enterprise**' ı seçin.
1. Profil türü için **Wi-Fi**' ı seçin. 

[Android tarafından desteklenmediğinden](https://developer.android.com/reference/android/net/wifi/WifiManager.html#enableNetwork%28int%2c%20boolean%29) **Otomatik bağlan** ayarı kaldırılacak.

Bu ayarı bir Wi-Fi profilinde kullanırsanız, **Connect 'in otomatik olarak** çalıştığını fark edebilirsiniz. Herhangi bir işlem yapmanız gerekmez, ancak bu ayarın Intune kullanıcı arabiriminden kaldırılacağına dikkat edin.

Geçerli ayarlar hakkında daha fazla bilgi için [Android Wi-Fi ayarları](../configuration/wi-fi-settings-android.md) veya [Android Enterprise Wi-Fi ayarları](../configuration/wi-fi-settings-android-enterprise.md)' na gidin.

Bu ayarın kaldırılması için geçerlidir:
- Android.
- Android kurumsal.

### <a name="global-http-proxy-on-android-enterprise-devices----4816339----"></a>Android kurumsal cihazlarda genel HTTP proxy 'si <!-- 4816339  -->
Android kurumsal cihazlarda, kuruluşunuzun Web tarama standartlarını karşılamak için genel bir HTTP proxy 'si yapılandırabileceksiniz:

1. **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**'u seçin.
1. Platform için **Android kurumsal**' i seçin.
1. **Cihaz sahibini**seçin.
1. Profil türü için **cihaz kısıtlamaları**' nı seçin. 
1. **Bağlantıyı**seçin. 
 
Ara sunucuyu yapılandırdıktan sonra tüm HTTP trafiği bunu kullanacaktır. Bu özellik, cihaz sahibi modunda olan Android Kurumsal cihazları için geçerlidir.

### <a name="new-device-firmware-configuration-interface-profile-for-devices-that-run-windows-10-and-later----2266073----"></a>Windows 10 ve üzeri çalıştıran cihazlar için yeni cihaz üretici yazılımı yapılandırma arabirimi profili <!-- 2266073  -->
Windows 10 ve üzeri sürümlerde, ayarları ve özellikleri denetlemek için bir cihaz yapılandırma profili oluşturabilirsiniz: 

1. **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**'u seçin.
1. Platform için **Windows 10 ve üzeri**' i seçin. 
 
Yeni bir cihaz üretici yazılımı yapılandırma arabirimi profil türü, Intune 'un UEFı (BIOS) ayarlarını yönetmesine olanak tanır.

Yapılandırabileceğiniz geçerli ayarlar hakkında daha fazla bilgi için, bkz. [Microsoft Intune cihaz profillerini kullanarak cihazlarınızda özellikleri ve ayarları uygulama](../configuration/device-profiles.md).

Bu özellik, select cihazlarda Windows 10 RS5 (1809) ve üzeri için geçerlidir.

### <a name="pkcs-certificates-for-macos-----1333650------------------"></a>MacOS için PKCS sertifikaları  <!-- 1333650                -->
MacOS çalıştıran cihazlarda ortak anahtar şifreleme standartları (PKCS) sertifikaları için tam destek ekleyeceğiz. Kullanıcılar, **Özelleştirme konusu** ve **konu alternatif adı**için alanları kullanarak Kullanıcı ve cihaz sertifikaları dağıtabilecektir. 

Ayrıca, **tüm uygulamalara erişime Izin ver**adlı yeni bir ayar de sunuyoruz. Tüm ilişkili uygulamaların özel anahtara erişimini sağlamak için bu ayarı etkinleştirin. Bu ayar hakkında daha fazla bilgi için bkz. Developer.Apple.com üzerindeki [yapılandırma profili başvurusu](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf) .

### <a name="derived-credentials-to-provision-mobile-devices-with-certificates----------1736036-1736037-1772050--------"></a>Sertifikaları olan mobil cihazları sağlamak için türetilmiş kimlik bilgileri      <!--  1736036, 1736037, 1772050      --> 
Sertifikaları cihazlara dağıtmak için *ulusal standartlar ve Teknoloji Enstitüsü (NIST) 800-157* standardını destekleyen türetilmiş kimlik bilgileri için destek ekleyeceğiz.  Türetilmiş kimlik bilgileri, akıllı kart gibi kişisel kimlik doğrulama (PıV) veya ortak erişim kartı (CAC) kullanımına dayanır. Kullanıcılar bir bilgisayardaki akıllı kartlarını kullanarak kimlik doğrular. Ardından, türetilmiş kimlik bilgisi sağlayıcısı 'nın gerektirdiği süreci izleyerek yönetilen cihazları için bir sertifika ister.   

Sertifikayı almak için türetilmiş kimlik bilgilerini kullanma işlemi, SCEP veya PKCS sertifika profillerini kullanan işlemlerden farklıdır. Ancak sonuç aynıdır: uygulama kimlik doğrulaması, VPN, Wi-Fi veya e-posta profilleri için kullanılabilen kimlik doğrulama sertifikalarına sahip mobil cihazlar. Daha fazla bilgi için bkz. NCCOE 'de [TÜRETILEN PIV kimlik bilgileri](https://www.nccoe.nist.gov/projects/building-blocks/piv-credentials) . NIST.gov.

Türetilmiş kimlik bilgilerinin ilk sürümü, iOS üzerinde Entrust Datacard, ıntercede ve DıŞA geçmiş Rebred 'yi destekleyecektir. Ek platformlar ve türetilmiş kimlik bilgileri sağlayıcıları sonraki sürümlerde desteklenecektir.   

<!-- ***********************************************-->
## <a name="device-enrollment"></a>Cihaz kaydı

### <a name="specify-which-android-device-os-versions-enroll-through-the-work-profile-and-which-enroll-through-the-device-administrator----4350697---"></a>Hangi Android cihaz işletim sistemi sürümlerinin iş profili aracılığıyla kaydedileceğini ve Cihaz Yöneticisi üzerinden kayıt olduğunu belirtin <!-- 4350697 -->
Intune cihaz türü kısıtlamalarını kullanarak, Android kurumsal iş profili kaydı veya Android Cihaz Yöneticisi kaydı kullanıp kullanmayacağını belirtmek için bir cihazın işletim sistemi sürümünü kullanabilirsiniz. Bunu yapmak için, Intune 'da **cihaz kaydı** > **Kayıt kısıtlamaları**' nı seçin  > **kısıtlama oluşturma** > **cihaz türü kısıtlama** > **Platform ayarları**.

### <a name="edit-the-device-name-value-for-autopilot-devices----4816775---"></a>Autopilot cihazlar için cihaz adı değerini düzenleme <!-- 4816775 -->
Azure AD 'ye katılmış Autopilot cihazları için **Cihaz adı** değerini düzenleyebileceksiniz:

1. **Intune** > **cihaz kaydı** > **Windows kaydı** > **Windows Autopilot** > **cihazları**' nı seçin.
1. Cihazı seçin.
1. Sağdaki bölmede **Cihaz adı** değerini değiştirin.
1. **Kaydet**’i seçin.

### <a name="for-ios-devices-customize-the-enrollment-privacy-window-of-company-portal----4394993----"></a>İOS cihazları için Şirket Portalı kayıt gizlilik penceresini özelleştirin <!-- 4394993  -->
Markaşağı kullanarak, son kullanıcıların iOS kaydı sırasında göreceği Şirket Portalı gizlilik penceresini özelleştirebilirsiniz. Özellikle, kuruluşunuzun cihazı göreyapabileceği veya cihazı üzerinde yapamıyorum işlerin listesini özelleştirebilirsiniz.

<!-- ***********************************************-->
## <a name="device-management"></a>Cihaz yönetimi


### <a name="edit-the-group-tag-value-for-autopilot-devices---4816775---"></a>Autopilot cihazlar için Grup etiketi değerini düzenleme<!-- 4816775 -->
Autopilot cihazlar için **Grup etiketi** değerini düzenleyebileceksiniz:

1. **Intune** > **cihaz kaydı** > **Windows kaydı** > **Windows Autopilot** > **cihazları**' nı seçin.
1. Cihazı seçin.
1. Sağdaki bölmede, **Grup etiketi** değerini değiştirin.
1. **Kaydet**’i seçin.

### <a name="ui-update-for-creating-and-editing-windows-10-update-rings-----4099089------------"></a>Windows 10 güncelleştirme halkalarını oluşturma ve düzenlemeyle ilgili Kullanıcı arabirimi güncelleştirmesi  <!-- 4099089          -->   
Windows 10 güncelleştirme halkaları için güncelleştirilmiş oluşturma ve düzenleme kullanıcı arabirimi deneyimlerini kullanıma sunacağız. Yeni Kullanıcı arabirimi şunları olur:  
- Bir dikey pencerede Sihirbaz stili biçim kullanarak mevcut deneyimi kolaylaştırın. Bu Kullanıcı arabirimi güncelleştirmesi, BT uzmanlarının derin dikey pencere olmasını gerektiren dikey pencere genişlemesine ortadan kaldıracak.   
- Atamaları dahil etmek için akış oluştur öğesini gözden geçirin.  
- Özet sayfası ekleyin. Bu Özet, özellikleri görüntülerken, bir güncelleştirme halkası oluşturmaya hazırlanırken ve bir özelliği düzenlediğinizde, tüm ayarları içerir. Bu öğe düzenlenirken, Özet yalnızca düzenlemekte olduğunuz özelliklerin kategorisi içindeki öğeleri listeler.

### <a name="ui-update-for-creating-and-editing-ios-software-updates-----4099090----------"></a>İOS yazılım güncelleştirmelerini oluşturma ve düzenlemeyle ilgili Kullanıcı arabirimi güncelleştirmesi  <!-- 4099090        -->   
Intune 'a iOS yazılım güncelleştirmelerine yönelik güncelleştirilmiş oluşturma ve düzenleme kullanıcı arabirimi deneyimlerini kullanıma sunacağız. Yeni Kullanıcı arabirimi şunları olur:
- Bir dikey pencerede Sihirbaz stili biçim kullanarak mevcut deneyimi kolaylaştırın. Bu Kullanıcı arabirimi güncelleştirmesi, BT uzmanlarının derin dikey pencere olmasını gerektiren dikey pencere genişlemesine ortadan kaldıracak.  
- Atamaları iOS yazılım güncelleştirme ilkesi oluşturma akışı ' na ekleyin. 
- İOS yazılım güncelleştirme ilkesine bir Özet sayfası ekleyin. Özet, bir ilke oluşturmaya hazırlanırken ve bir özelliği düzenlediğinizde, özellikleri görüntülerken tüm ayarları dahil eder. Bu öğe düzenlenirken, Özet yalnızca düzenlemekte olduğunuz özelliklerin kategorisi içindeki öğeleri listeler.

### <a name="target-macos-user-groups-to-require-jamf-management----4061739---"></a>JAMF yönetimini gerektirecek macOS Kullanıcı gruplarını hedefleme <!-- 4061739 -->
Belirli kullanıcı gruplarını, macOS cihazlarının JAMF tarafından yönetilmesini gerektirecek şekilde hedefleyebilir. Bu hedefleme, diğer cihazlar Intune tarafından yönetilmeye devam ederken, bir macOS cihazları alt kümesine JAMF uyumluluk tümleştirmesini uygulamanızı sağlayacaktır. Hedefleme, kullanıcıların cihazlarını bir mobil cihaz yönetimi (MDM) sisteminden diğerine kademeli olarak geçireceğinizi de sağlar.

### <a name="new-restrictions-for-renaming-windows-devices----3478938---"></a>Windows cihazlarını yeniden adlandırmaya yönelik yeni kısıtlamalar <!-- 3478938 -->
Cihaz adlarının bu kuralları izlemesi gerekir:
- 15 karakter veya daha az (63 bayttan daha az veya eşittir, sondaki NULL dahil değildir)
- Null veya boş dizeler yok
- İzin verilen ASCII: harfler (a-z, A-Z), sayılar (0-9) ve tireler
- İzin verilen Unicode: karakterler > = 0x80, geçerli UTF8, ıDN tarafından eşlenebilir (Rtlidntonameprepunıcode başarılı; bkz. RFC 3492)
- Adlar yalnızca sayı içeremez veya sayı ile başlamalıdır
- Adda boşluk yok
- İzin verilmeyen karakterler: {|} ~ [\] ^ ':; < = >? & @! " # $ % ` ( ) + / , . _ *

### <a name="deploy-software-updates-to-macos-devices----3194876---"></a>MacOS cihazlarına yazılım güncelleştirmeleri dağıtma <!-- 3194876 -->
MacOS cihazları gruplarına yazılım güncelleştirmeleri dağıtabileceksiniz. Bu özellik kritik, bellenim, yapılandırma dosyası ve diğer güncelleştirmeleri içerir. Sonraki cihaz iadede güncelleştirmeleri gönderebilirsiniz. İsterseniz güncelleştirmeleri dağıtmak için haftalık bir zamanlama seçerek veya ayarladığınız süreleri alabilir. 

Bu özellik, yardım masanızın tam olarak çalıştığı zaman, cihazları standart çalışma saatleri veya dış saatler dışında güncelleştirmek istediğinizde yardımcı olur. Ayrıca güncelleştirmelerin dağıtıldığı tüm macOS cihazlarının ayrıntılı bir raporunu alırsınız. Belirli bir güncelleştirmenin durumunu görmek için raporun cihaza gidebilirsiniz.

<!-- ***********************************************-->
## <a name="monitoring-and-troubleshooting"></a>İzleme ve sorun giderme

### <a name="android-report-on-the-devices-overview-page----2984353----"></a>Cihazlara Genel Bakış sayfasında Android raporuna <!-- 2984353  -->
**Cihazlara genel bakış** sayfasına yeni bir rapor ekleyeceğiz. Rapor, her bir cihaz yönetimi çözümüne kaç tane Android cihaz kaydedildiğini gösterir. Grafik, iş profili için cihaz sayısını, tam olarak yönetilen, adanmış ve Cihaz Yöneticisi kayıtlı olduğunu gösterir. 

Raporu görmek için **ıntune** > **cihaz** > **genel bakış**' ı seçin.

### <a name="windows-autopilot-deployment-reports----3856172----"></a>Windows Autopilot dağıtım raporları <!-- 3856172  -->
Yeni bir rapor, Windows Autopilot aracılığıyla dağıtılan her bir cihaza ayrıntı sağlayacaktır. Bu veriler dağıtımdan sonra 30 gün boyunca kullanılabilir olacaktır. 

Raporu görmek için **ıntune** > **cihaz kaydı** > **monitör** > **Autopilot dağıtımlar**' a gidin.

### <a name="updated-support-experience-------5012398------"></a>Güncelleştirilmiş destek deneyimi   <!--  5012398    -->
Geliştirmeye devam etmenin bir parçası olarak, Intune için konsol içi destek deneyimini güncelleştireceğiz.  Genel sorunlar için konsol içi arama ve geri bildirim işlemlerini geliştireceğiz ve destek ile iletişim kurmak için iş akışını kolaylaştırıyoruz.     

<!-- ***********************************************-->
<!--## Security-->


<!-- ***********************************************-->
## <a name="notices"></a>Bildirimler

[!INCLUDE [Intune notices](../includes/intune-notices.md)]

## <a name="see-also"></a>Ayrıca bkz:
Son gelişmeler hakkında daha fazla bilgi için bkz. [Microsoft Intune](whats-new.md)yenilikleri.
