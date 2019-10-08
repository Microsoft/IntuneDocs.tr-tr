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
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0e7c4e5ed45455dda941fb0c61c989c12c57135d
ms.sourcegitcommit: 29b1113dc04534c4c87c33c773c5a0e24266e042
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/07/2019
ms.locfileid: "71999314"
---
# <a name="in-development-for-microsoft-intune---october-2019"></a>Microsoft Intune için geliştirme sırasında-Ekim 2019

Hazırlık ve planlamada yardımcı olması için, bu sayfada Intune Kullanıcı Arabirimi güncelleştirmeleri ve geliştirme aşamasında olan ancak henüz yayınlanmayan özellikler listelenir. Bunlara ek olarak:

- Bir değişiklikten önce işlem yapmanız gerektiğini düşünüyorsanız, tamamlayıcı bir Office Ileti merkezi gönderisini yayımlayacağız.
- Bir özellik üretimde başlatıldığında, önizleme veya genel kullanıma açık olarak, özellik açıklaması bu sayfayı ve yenilikler [sayfasına](whats-new.md)taşınır.
- Bu sayfa ve yenilikler [sayfası](whats-new.md) düzenli aralıklarla güncelleştirilir. Ek güncelleştirmeler için yeniden denetleyin.
- Stratejik teslim edilebilirler ve zaman çizelgeleri için [M365 yol haritasını](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS) inceleyin.

> [!Note]
> Bu öğeler, gelecek sürümlerde sunulan Intune özellikleri hakkında Microsoft 'un geçerli beklentilerini yansıtır. Tarihler ve bireysel Özellikler değişebilir. Geliştirmede tüm öğelerin bu sayfada bir özellik açıklaması yoktur.

**RSS akışı**: Şu URL 'yi kopyalayıp akış okuyucunuzun içine yapıştırarak, Bu sayfa güncelleştirildikten sonra bildirim alın: `https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`

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

### <a name="additional-app-configuration-variable-available----4969237----"></a>Ek uygulama yapılandırma değişkeni kullanılabilir <!-- 4969237  -->
Bir uygulama yapılandırma ilkesi oluştururken, `AAD Device ID` yapılandırma değişkenini yapılandırma ayarlarınızın bir parçası olarak dahil edebilirsiniz. Intune 'da, **istemci uygulamaları** > **uygulama yapılandırma ilkeleri** > **Ekle**' yi seçin. Yapılandırma **ayarları** dikey penceresini görüntülemek için yapılandırma ilkesi ayrıntılarınızı girip **yapılandırma ayarları** ' nı seçin.

### <a name="dark-mode-for-ios-company-portal----4911422----"></a>İOS Şirket Portalı için koyu mod <!-- 4911422  -->
İOS Şirket Portalı için koyu mod planlanmaktadır. Şirket uygulamalarını indirin, cihazlarınızı yönetin ve seçtiğiniz renk düzeninde BT desteği alın. İOS Şirket Portalı hakkında daha fazla bilgi için bkz. [Microsoft Intune şirket portalı uygulamasını yapılandırma](../apps/company-portal-app.md).

### <a name="prevent-installation-of-apps-from-unknown-sources-on-android-enterprise-devices----4760025----"></a>Android kurumsal cihazlarda bilinmeyen kaynaklardan uygulama yüklenmesini engelleyin <!-- 4760025  -->
Android kurumsal iş profili cihazında, son kullanıcıların, bilinmeyen kaynaklardan gelen uygulamaları iş profiline yüklemesi hiçbir şekilde mümkün değildir. İsteğe bağlı olarak bu kısıtlamayı kişisel profile de genişletebilirsiniz. Bu kısıtlamayı etkinleştirirseniz, Android kurumsal iş profili cihazlarındaki son kullanıcıların da, bilinmeyen kaynaklardan gelen uygulamaların cihazın kişisel tarafına dışarıdan yüklenmesi engellenir. 

### <a name="update-to-app-protection-ui-and-ios-app-provisioning-ui----4102027-4102029----"></a>Uygulama koruma Kullanıcı arabirimi ve iOS uygulama sağlama Kullanıcı arabirimine güncelleştirme <!-- 4102027, 4102029  -->
Intune 'da uygulama koruma ilkeleri ve iOS uygulama sağlama profilleri oluşturma ve düzenleme için Kullanıcı arabirimi güncelleştirilir. UI değişiklikleri şunları içerir:
- Bir dikey pencere içinde bir sihirbaz stili biçim kullanılarak basitleştirilmiş bir deneyim. 
- Atamaları eklemek için akış oluşturma için bir güncelleştirme.
- Yeni bir ilke oluşturmadan veya bir özellik düzenlenirken önce özellikleri görüntülerken ayarlanan tüm öğelerin özetlenen sayfası. Ayrıca, Özellikler düzenlenirken, Özet yalnızca düzenlenmekte olan özellikler kategorisinden öğe listesini gösterir.

### <a name="create-groups-of-management-objects-called-policy-sets----3762880----"></a>Ilke kümeleri olarak adlandırılan yönetim nesnesi grupları oluşturma <!-- 3762880  -->
İlke kümeleri, önceden tanımlanmış, hedeflenen ve tek bir kavramsal birim olarak izlenmesi gereken yönetim varlıklarının başvuruları için bir paket oluşturmanıza olanak sağlar. İlke kümeleri varolan kavramları veya nesneleri değiştirmez. Yönetici, nesneleri bugün olduğu gibi ayrı ayrı atamaya devam edebilir. Ayrı ayrı nesnelere bir Ilke kümesi tarafından başvurulur. Bu nedenle, bağımsız nesnelerde yapılan tüm değişiklikler Ilke kümesine yansıtılır.  Intune 'da, **ilke kümelerini** > **Oluştur** ' u seçerek yeni bir ilke kümesi oluşturabilirsiniz. 

### <a name="win32-apps-on-windows-10-s-mode-devices----3747604----"></a>Windows 10 S modundaki cihazlarda Win32 uygulamaları <!-- 3747604  --> 
Windows 10 S modunda yönetilen cihazlara Win32 uygulamaları yükleyip çalıştırabileceksiniz. Windows Defender uygulama denetimi (WDAC) PowerShell araçlarını kullanarak S modu için bir veya daha fazla ek ilke oluşturabileceksiniz. Ek ilkeleri Device Guard Imzalama portalı ile imzalayın ve ardından Intune aracılığıyla ilkeleri karşıya yükleyin ve dağıtın. Intune 'da, bu özelliği **istemci uygulamalar** > **Windows 10 S ek ilkeleri**' ni seçerek bulacaksınız. 

### <a name="set-app-availability-based-on-a-date-and-time----3510685----"></a>Bir tarih ve saate göre uygulama kullanılabilirliğini ayarlama <!-- 3510685  -->
Yönetici olarak, gerekli bir uygulama için başlangıç saatini ve son tarih saatini yapılandırabileceksiniz. Başlangıç zamanında, Intune yönetim uzantısı uygulama içeriğini indirmeyi başlatacak ve önbelleğe alacak. Uygulama son tarihte yüklenecektir. Kullanılabilir uygulamalar için, uygulama Şirket Portalı görünür olduğunda başlangıç zamanı görüntülenir. Intune 'da, **istemci uygulamaları** > **uygulamalar**' ı seçin. Ardından, listeden belirli bir uygulama seçin veya yeni bir uygulama eklemek için **Ekle** ' yi seçin. Uygulama dikey penceresinde **atamalar** > **Grup Ekle**' yi seçin. **Atama türünü** **gerekli** olarak ayarlayın ve ardından **dahil edilen gruplar**' ı seçin. **Bu uygulamayı tüm kullanıcılar için gerekli yap** seçeneğini belirleyin ve **Son Kullanıcı deneyimi** seçeneklerini değiştirmek için **Düzenle** **' yi** seçin. **Son Kullanıcı deneyimi** dikey penceresinde, gereken **yazılım kullanım süresini** ayarlayın. Uygulama ekleme hakkında daha fazla bilgi için bkz. [Microsoft Intune uygulama ekleme](../apps/apps-add.md).

### <a name="require-win32-apps-to-restart----3136567----"></a>Win32 uygulamalarının yeniden başlatılmasını gerektir <!-- 3136567  -->
Başarılı bir yüklemeden sonra bir Win32 uygulamasının yeniden başlatılması gerekebilir. Ayrıca, yeniden başlatmanın gerçekleşmesi için gereken süreyi (yetkisiz kullanım süresi) seçebileceksiniz.

### <a name="company-portal-app-on-windows----1808082----"></a>Windows üzerinde Şirket Portalı uygulaması <!-- 1808082  -->
Windows cihazlarındaki Şirket Portalı uygulaması, uygulama kapatıldığında bile kullanıcılara bildirimler görüntülenecek şekilde güncelleştirilecektir. Güncelleştirme, yalnızca yüklemenin durumu tamamlandığında veya başarısız olduğunda kullanılabilir uygulamalar için bildirimleri gösterir. Şirket Portalı uygulama gerekli uygulamalar için bildirimleri göstermez.

### <a name="company-portal-app-installation-status-messages----2514416----"></a>Uygulama yükleme durum iletilerini Şirket Portalı <!-- 2514416  -->
Şirket Portalı uygulama son kullanıcılara ek uygulama yükleme durumu iletileri gösterecektir. Yeni Win32 bağımlılık özellikleri için aşağıdaki koşullar geçerli olacaktır:
- Uygulama yüklenemedi. Yönetici tarafından tanımlanan bağımlılıklar karşılanmadı.
- Uygulama başarıyla yüklendi, ancak yeniden başlatma gerekiyor.
- Uygulama yükleme sürecinde, ancak devam etmek için yeniden başlatma gerekiyor.

#### <a name="assign-microsoft-edge-beta-for-macos----4678761----"></a>MacOS için Microsoft Edge Beta ata <!-- 4678761  -->
MacOS cihazları için Microsoft Edge Beta 'nın en son sürümünü Intune 'a ekleyebilir ve atayabilirsiniz. Intune 'da **istemci uygulamaları** > **uygulamalar** > **Uygulama Ekle** > **Microsoft Edge-MacOS**' u seçin. Ardından, Microsoft Edge Beta 'yı amaçlanan gruplara atayın. Microsoft otomatik güncelleştirme (MAU), Microsoft Edge 'i güncel tutar. Microsoft Edge hakkında daha fazla bilgi için, [Microsoft Intune Ile Microsoft Edge kullanarak Web erişimini yönetme](../apps/manage-microsoft-edge.md)makalesine bakın.

### <a name="configure-app-notification-content-for-organization-accounts----2576686---"></a>Kuruluş hesapları için uygulama bildirim içeriğini yapılandırma <!-- 2576686 -->
Android ve iOS cihazlarında Intune uygulama koruma ilkeleri (uygulama), kuruluş hesapları için uygulama bildirim içeriğini denetlemenize olanak tanır. Bu özellik, uygulamalardan destek isteyecek ve UYGULAMANıN etkin olduğu tüm uygulamalarda kullanılamayabilir. UYGULAMA hakkında daha fazla bilgi için bkz. [Uygulama koruma ilkeleri nelerdir?](../apps/app-protection-policy.md).

### <a name="available-google-play-app-reporting-for-android-work-profiles----3041956----"></a>Android iş profilleri için kullanılabilir Google Play uygulama raporlaması <!-- 3041956  -->
Android iş profili cihazlarına kullanılabilir uygulama yüklemeleri için, uygulama yükleme durumunu ve yönetilen Google Play uygulamalarının yüklü sürümünü görüntüleyebilirsiniz. Daha fazla bilgi için bkz. [Uygulama koruma ilkelerini izleme](../apps/app-protection-policies-monitor.md), [Android Iş profili cihazlarını Intune ile yönetme](../enrollment/android-enterprise-overview.md) ve [uygulama türü ile yönetilen Google Play](../apps/apps-add-android-for-work.md#managed-google-play-app-types).

<!-- ***********************************************-->
## <a name="device-configuration"></a>Cihaz yapılandırması


### <a name="new-device-configuration-settings-for-supervised-ios-and-ipados-devices----5199328----"></a>Denetimli iOS ve ıpados cihazları için yeni cihaz yapılandırma ayarları <!-- 5199328  -->
İOS ve ıpados cihazlarında, cihazlarda özellikleri ve ayarları kısıtlamak için bir profil oluşturabilirsiniz (**cihaz yapılandırma** > **profilleri** >  platform > cihaz Için  > **iOS/ıpados** **oluşturma**profil türü için kısıtlamalar). Denetleyebilmeniz için yeni ayarlar olacaktır: 
- Dosyalar uygulamasındaki ağ sürücüsüne erişim  
- Dosyalar uygulamasındaki USB sürücüsüne erişim 
- Wi-Fi her zaman açık 

Geçerli ayarları görmek için [iOS cihaz ayarları ' na giderek Intune kullanarak özelliklere izin verin veya kısıtlayın](../configuration/device-restrictions-ios.md).

Uygulama alanı:
- iOS 13,0 ve üzeri
- ıpados 13,0 ve üzeri

### <a name="connect-automatically-setting-is-removed-in-wi-fi-profiles-on-android-and-android-enterprise----5021055----"></a>Android ve Android Enterprise 'ta Wi-Fi profillerindeki otomatik bağlanma ayarı kaldırılıyor <!-- 5021055  -->
Android ve Android kurumsal cihazlarda, farklı ayarları yapılandırmak için bir Wi-Fi profili oluşturabilirsiniz (**cihaz yapılandırma** > **profilleri** > **Profil oluştur** > **Android** veya **Android Enterprise** platform için > **Wi-Fi** for profile yazın). **Otomatik bağlan** ayarı, [Android tarafından](https://developer.android.com/reference/android/net/wifi/WifiManager.html#enableNetwork%28int%2c%20boolean%29)desteklenmeyen şekilde kaldırılır. 

Bu ayarı bir Wi-Fi profilinde kullanırsanız, **Connect 'in otomatik olarak** çalışmayacak olduğunu fark edebilirsiniz. Herhangi bir işlem yapmanız gerekmez, ancak bu ayarın Intune kullanıcı arabiriminde kaldırıldığını unutmayın.

Geçerli ayarları görmek için [Android Wi-Fi ayarları](../configuration/wi-fi-settings-android.md) veya [Android Enterprise Wi-Fi ayarları](../configuration/wi-fi-settings-android-enterprise.md)' na gidin.

Uygulama alanı:
- Android
- Android kurumsal

### <a name="create-a-global-http-proxy-on-android-enterprise-device-owner-devices----4816339----"></a>Android kurumsal cihaz sahibi cihazlarda genel HTTP proxy oluşturma <!-- 4816339  -->
Android kurumsal cihazlarda, kuruluşunuzun Web tarama standartlarını (**cihaz yapılandırma** > **profilleri** > **Profil oluştur** > **ANDROID Enterprise** ) karşılamak için genel bir http proxy 'si yapılandırabilirsiniz. Platform > **cihaz sahibi >** profil türü > **bağlantı**) için cihaz kısıtlamaları. Yapılandırıldıktan sonra tüm HTTP trafiği bu proxy 'yi kullanır.

Uygulama alanı:
- Android kurumsal cihaz sahibi

### <a name="new-device-firmware-configuration-interface-profile-for-windows-10-and-later-devices----2266073----"></a>Windows 10 ve üzeri cihazlar için yeni cihaz üretici yazılımı yapılandırma arabirimi profili <!-- 2266073  -->
Windows 10 ve üzeri sürümlerde, ayarları ve özellikleri denetlemek için bir cihaz yapılandırma profili oluşturabilirsiniz (**cihaz yapılandırma** > **profilleri** > **Profil oluştur** >  Platform için**Windows 10 ve üzeri** ). Intune 'un UEFı (BIOS) ayarlarını yönetmesine izin veren yeni bir cihaz üretici yazılımı yapılandırma arabirimi profil türü olacaktır.

Yapılandırabileceğiniz tüm geçerli ayarları görmek için, bkz. [Microsoft Intune cihaz profillerini kullanarak cihazlarınızda özellikleri ve ayarları uygulama](../configuration/device-profiles.md).

Uygulama alanı:
- Windows 10 RS5 (1809) ve daha yeni bir cihaz seçin

### <a name="pkcs-certificates-for-macos-----1333650------------------"></a>MacOS için PKCS sertifikaları  <!-- 1333650                -->
MacOS çalıştıran cihazlarda PKCS sertifikaları için tam destek ekleyeceğiz. Kullanıcılar, özelleştirme konusu ve konu alternatif adı alanlarıyla Kullanıcı ve cihaz sertifikaları dağıtabilecek. Ayrıca, tüm uygulamalara erişime Izin veren yeni bir ayarımız olacaktır, bu da etkinleştirerek tüm ilişkili uygulamaların özel anahtara erişmesini sağlar. Bu ayar hakkında daha fazla bilgi için şu Apple belgelerini ziyaret edin: https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf.

###   <a name="derived-credentials-to-provision-mobile-devices-with-certificates----------1736036-1736037-1772050--------"></a>Sertifikaları olan mobil cihazları sağlamak için türetilmiş kimlik bilgileri      <!--  1736036, 1736037, 1772050      --> 
Sertifikaları cihazlara dağıtmak için *ulusal standartlar ve Teknoloji Enstitüsü (NIST) 800-157* standardını destekleyen türetilmiş kimlik bilgileri için destek ekleyeceğiz.  Türetilmiş kimlik bilgileri, akıllı kart gibi kişisel kimlik doğrulama (PıV) veya ortak erişim kartı (CAC) kartının kullanımına dayanır. Kullanıcılar bir bilgisayardaki akıllı kartıyla kimlik doğrular ve ardından, türetilmiş kimlik bilgisi sağlayıcısı tarafından istenen işlemden sonra yönetilen cihazları için bir sertifika isteği gönderir.   

Bir sertifikayı almak için türetilmiş kimlik bilgilerini kullanma işlemi, SCEP veya PKCS sertifika profillerini kullanmaktan farklıdır, ancak nihai sonuç, uygulama kimlik doğrulaması, VPN, Wi-Fi veya e-posta için kullanılabilen kimlik doğrulaması sertifikalarına sahip mobil cihazlardır. lerinize.   

Daha fazla bilgi için bkz. www.nccoe.nist.gov adresinde [TÜRETILEN PIV kimlik bilgileri](https://www.nccoe.nist.gov/projects/building-blocks/piv-credentials) .

Türetilmiş kimlik bilgilerinin ilk sürümü, iOS üzerinde Entrust Datacard, ıntercede ve DıŞA geçmiş Rebred 'yi destekleyecektir. Ek platformlar ve türetilmiş kimlik bilgileri sağlayıcıları sonraki sürümlerde desteklenecektir.   

<!-- ***********************************************-->
## <a name="device-enrollment"></a>Cihaz kaydı

### <a name="specify-which-android-device-operating-system-versions-enroll-with-work-profile-or-device-administrator-enrollment----4350697---"></a>Hangi Android cihaz işletim sistemi sürümlerinin iş profili veya cihaz yöneticisi kaydıyla kaydedileceğini belirtin <!-- 4350697 -->
Intune cihaz türü kısıtlamalarını kullanarak, Android kurumsal iş profili kaydı veya Android Cihaz Yöneticisi kaydını hangi kullanıcı cihazlarının kullanacağı belirlemek için cihazın işletim sistemi sürümünü kullanabilirsiniz. Bunu yapmak için **ıntune** > **cihaz kaydı** > **Kayıt kısıtlamaları** >  tür**kısıtlaması oluşturma** > **cihaz türü kısıtlaması** > **Platform ayarları**' na gidin.

### <a name="edit-device-name-value-for-autopilot-devices----4816775---"></a>Autopilot cihazlar için cihaz adı değerini Düzenle <!-- 4816775 -->
Azure AD 'ye katılmış Autopilot cihazları için cihaz adı değerini düzenleyebileceksiniz. Bunu yapmak için **ıntune** > **cihaz kaydı** > **Windows kaydı** > **Windows Autopilot** > **cihazları** > sağ bölmedeki cihaz adı değerini değiştirin > **Kaydet >** .

### <a name="for-ios-devices-customize-the-enrollment-process-privacy-screen-of-the-company-portal----4394993----"></a>İOS cihazları için Şirket Portalı kayıt işlemi gizlilik ekranını özelleştirin <!-- 4394993  -->
Marku kullanarak, son kullanıcıların iOS kaydı sırasında göreceği Şirket Portalı gizlilik ekranını özelleştirebileceksiniz. Özellikle, kuruluşunuzun cihazı göremeyecek veya cihaz üzerinde yapaamayacak işlerin listesini özelleştirebilirsiniz.

<!-- ***********************************************-->
## <a name="device-management"></a>Cihaz yönetimi


### <a name="edit-group-tag-value-for-autopilot-devices---4816775---"></a>Autopilot cihazlar için Grup etiketi değerini Düzenle<!-- 4816775 -->
Autopilot cihazları için Grup etiketi değerini düzenleyebileceksiniz. Bunu yapmak için **ıntune** > **cihaz kaydı** > **Windows kaydı** > **Windows Autopilot** > **cihazları** > sağ bölmedeki Grup etiketi değerini değiştirin > **Kaydet >** .

### <a name="ui-update-for-creating-and-editing-windows-10-update-rings-----4099089------------"></a>Windows 10 güncelleştirme halkalarını oluşturma ve düzenlemeyle ilgili Kullanıcı arabirimi güncelleştirmesi  <!-- 4099089          -->   
Intune için Windows 10 güncelleştirme halkaları için güncelleştirilmiş bir oluşturma ve düzenleme kullanıcı arabirimi deneyimi kullanıma sunuyoruz.  Kullanıcı arabirimindeki değişiklikler şunları içerir:  
- Bir dikey pencerede bir sihirbaz stili biçimi kullanarak mevcut deneyimi kolaylaştırın. Bu Kullanıcı arabirimi güncelleştirmesi, BT uzmanlarının derin dikey pencere ile detaya gitmeyi gerektiren dikey pencere genişlemesine ile çalışır.   
- Atamaları dahil etmek için akış oluştur öğesini gözden geçirin.  
- Özellikleri görüntülerken, yeni bir güncelleştirme halkası oluşturmadan önce ve bir özellik düzenlenirken, her şeyin özetlenen bir sayfanın eklenmesi. Düzenleme sırasında, Özet yalnızca düzenlenmekte olan özelliklerin bir kategorisi içinde ayarlanan öğelerin listesini gösterir.

### <a name="ui-update-for-creating-and-editing-ios-software-updates-----4099090----------"></a>İOS yazılım güncelleştirmelerini oluşturma ve düzenlemeyle ilgili Kullanıcı arabirimi güncelleştirmesi  <!-- 4099090        -->   
Intune 'a iOS yazılım güncelleştirmeleri için güncelleştirilmiş bir oluşturma ve düzenleme kullanıcı arabirimi deneyimi sunuyoruz. Kullanıcı arabirimindeki değişiklikler şunları içerir:
- Bir dikey pencerede bir sihirbaz stili biçimi kullanarak mevcut deneyimi kolaylaştırın. Bu Kullanıcı arabirimi güncelleştirmesi, BT uzmanlarının derin dikey pencere ile detaya gitmeyi gerektiren dikey pencere genişlemesine ile çalışır.  
- İOS yazılım güncelleştirme ilkesi oluşturma akışı, atamaları içerecek şekilde güncelleştirilecek 
- İOS yazılım güncelleştirme ilkesi, yeni bir ilke oluşturulmadan ve bir özelliği düzenlenirken önce özellikleri görüntülerken ayarlanan tüm öğelerin bir özetlenen sayfasını içerir. Düzenleme sırasında, Özet yalnızca düzenlenmekte olan özelliklerin bir kategorisi içinde ayarlanan öğelerin listesini gösterir.

### <a name="target-macos-user-groups-to-require-jamf-management----4061739---"></a>JAMF yönetimini gerektirecek macOS Kullanıcı gruplarını hedefleme <!-- 4061739 -->
Belirli kullanıcı gruplarını, macOS cihazlarının JAMF tarafından yönetilmesini gerektirecek şekilde hedefleyebilir. Bu hedefleme, diğer cihazlar Intune tarafından yönetilmeye devam ederken, bir macOS cihazları alt kümesine JAMF uyumluluk tümleştirmesini uygulamanızı sağlayacaktır. Ayrıca, kullanıcıların cihazlarını bir MDM 'den diğerine kademeli olarak geçireceğinizi de sağlar.

### <a name="new-restrictions-for-renaming-windows-devices----3478938---"></a>Windows cihazlarını yeniden adlandırmaya yönelik yeni kısıtlamalar <!-- 3478938 -->
Cihaz adlarının bu kuralları izlemesi gerekir:
- 15 karakter veya daha az (63 bayttan küçük veya buna eşit olmalı, sondaki NULL dahil değildir)
- Null veya boş dize değil
- İzin verilen ASCII: harfler (a-z, A-Z), sayılar (0-9) ve tireler
- İzin verilen Unicode: karakterler > = 0x80, geçerli UTF8 olmalıdır; ıDN eşleme olmalıdır (Rtlıdntonameprepunıcode başarılı; bkz. RFC 3492)
- Adlar yalnızca sayı içeremez veya sayı ile başlamalıdır
- Adda boşluk yok
- İzin verilmeyen karakterler: {|} ~ [\] ^ ':; < = >? & @! " # $ % ` ( ) + / , . _ *)

### <a name="deploy-software-updates-to-macos-devices----3194876---"></a>MacOS cihazlarına yazılım güncelleştirmeleri dağıtma <!-- 3194876 -->
MacOS cihazları gruplarına yazılım güncelleştirmeleri dağıtabileceksiniz. Bu özellik kritik, bellenim, yapılandırma dosyası ve diğer güncelleştirmeleri içerir. Güncelleştirmeleri bir sonraki cihaz iadede gönderebilecek veya zaman içinde güncelleştirmeleri dağıtmak için haftalık bir zamanlama seçebileceğiniz şekilde ayarlayabilirsiniz. Bu özellik, cihazları standart çalışma saatleri dışında veya yardım masanıza tam olarak çalıştırıldığında güncelleştirmek istediğinizde yardımcı olur. Ayrıca güncelleştirmelerin dağıtıldığı tüm macOS cihazlarının ayrıntılı bir raporunu alırsınız. Belirli güncelleştirmelerin durumlarını görmek için, raporu cihaz başına temelinde inceleyebilirsiniz.

<!-- ***********************************************-->
## <a name="monitor-and-troubleshoot"></a>İzleme ve sorun giderme

### <a name="new-android-report-on-devices-overview-page----2984353----"></a>Cihazlara ilişkin yeni Android raporuna genel bakış sayfası <!-- 2984353  -->
Cihazlara genel bakış sayfasına, her bir cihaz yönetimi çözümüne kaç tane Android cihaz kaydedildiğini gösteren yeni bir rapor ekleyeceğiz. Bu grafik iş profilini, tam olarak yönetilen, adanmış ve Cihaz Yöneticisi kayıtlı cihaz sayılarını gösterir. Raporu görmek için **ıntune** > **cihaz** > **genel bakış**' ı seçin.

### <a name="windows-autopilot-deployment-reports----3856172----"></a>Windows Autopilot dağıtım raporları <!-- 3856172  -->
Yeni bir rapor, Windows Autopilot aracılığıyla dağıtılan her bir cihaza ayrıntı sağlayacaktır. Bu veriler dağıtımdan sonra 30 gün boyunca kullanılabilir olacaktır. Raporu görmek için **ıntune** > **cihaz kaydı** > **monitör** > **Autopilot dağıtımlar**' a gidin.

### <a name="updated-support-experience-------5012398------"></a>Güncelleştirilmiş destek deneyimi   <!--  5012398    -->
Geliştirmeye devam etmenin bir parçası olarak, Intune için konsol içi destek deneyimini güncelleştiriyoruz.  Genel sorunlar için konsol içi aramayı ve geri bildirimleri geliştireceğiz ve desteğe başvurmak için iş akışını kolaylaştırıyoruz.     

<!-- ***********************************************-->
<!--## Security-->


<!-- ***********************************************-->
## <a name="notices"></a>Bildirimleri

[!INCLUDE [Intune notices](../includes/intune-notices.md)]

## <a name="see-also"></a>Ayrıca bkz.
Son geliştirmelerin ayrıntıları için [Microsoft Intune](whats-new.md) yenilikleri inceleyin.




