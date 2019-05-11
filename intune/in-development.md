---
title: Geliştirme - Intune
titleSuffix: ''
description: Geliştirme Intune özellikleri
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/29/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7bba992c79f69a126f0199d9cdac52779910ff38
ms.sourcegitcommit: 068c4e4bc6e6d778ece4a83d000128c4d2b732db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/29/2019
ms.locfileid: "64910322"
---
# <a name="in-development-for-microsoft-intune---may-2019"></a>Microsoft Intune - Mayıs 2019 geliştirme

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


<!-- 1905 start-->


### <a name="deleting-a-device-in-the-apple-portal-will-be-reflected-in-the-intune-portal---2489996---"></a>Intune portalında bir cihaz Apple portalında silme yansıtılır <!--2489996 -->
Bir cihaz Apple aygıt kayıt programı veya Apple iş Manager portallarını silinirse, cihaz otomatik olarak Intune'dan sonraki eşitleme sırasında silinir.

### <a name="baseline-support-for-keyword-search-----3082036-----------"></a>Anahtar sözcüğü için temel desteği arayın  <!-- 3082036         -->
Oluşturma veya bir güvenlik taban çizgisi profil düzenleme sırasında yakında kullanmak mümkün olacaktır *arama* konsolda görüntüleme ayarları filtrelemek için.   

### <a name="reset-and-wipe-devices-in-bulk-by-using-the-graph-api----3295288---"></a>Sıfırla ve Graph API'sini kullanarak cihazları toplu olarak temizleme <!-- 3295288 -->
Sıfırlama ve Graph API'sini kullanarak toplu olarak en fazla 100 cihazları temizlemek mümkün olacaktır.

### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy----3617671---"></a>Bir Windows 10 cihaz uyumluluk İlkesi, TPM yonga denetle <!-- 3617671 -->
Güvenilir Platform Modülü (TPM) yonga kümeleri çok sayıda Windows 10 ve üzeri cihazlar vardır. Bu güncelleştirme, cihazın TPM yongası sürümü denetleyen yeni bir uyumluluk ayarı içerir. 

[Windows 10 ve üzeri uyumluluk İlkesi ayarları](compliance-policy-create-windows.md#device-security) Bu ayar açıklar.

Şunun için geçerlidir: Windows 10 ve üzeri

### <a name="intune-management-extension-powershell-scripts-----3734186------"></a>Intune yönetim uzantısı PowerShell betikleri  <!-- 3734186    -->
Kullanıcının yönetici ayrıcalıkları olan bir cihazda çalışan PowerShell betikleri yapılandırmak mümkün olacaktır. Daha fazla bilgi için [kullanım PowerShell betiklerini Windows 10 cihazlarda ıntune](intune-management-extension.md).

### <a name="prevent-end-users-from-modifying-their-personal-hotspot-and-disable-siri-server-logging-on-ios-supervised-devices----4097904----"></a>Son kullanıcılar kendi kişisel etkin nokta değiştirmesini önlemek ve denetimli cihazlarda iOS günlüğü Siri sunucusunu devre dışı bırak <!-- 4097904  --> 
İOS cihazında cihaz kısıtlama profili oluşturun (**cihaz Yapılandırması** > **profilleri** > **profili oluşturma**  >  **iOS** Platform > **cihaz kısıtlamaları** profil türü için). Bu güncelleştirme, yeni ayarları yapılandırabileceğiniz içerir:

- Kişisel etkin nokta
- Siri sunucusu günlüğü

Geçerli ayarları görmek için Git [izin vermek veya özellikleri kısıtlamak için iOS cihaz ayarlarını](device-restrictions-ios.md). 

İçin geçerlidir: iOS 12.2 ve daha yeni

### <a name="new-classroom-app-device-restriction-settings-for-dep-enrolled-macos-devices----4097905----"></a>Yeni classroom uygulamasını cihaz kısıtlama ayarları macOS DEP ile kaydedilen cihazlar için <!-- 4097905  --> 
MacOS cihazları için yapılandırma profilleri cihaz oluşturabilirsiniz (**cihaz Yapılandırması** > **profilleri** > **profili oluşturma**  >  **macOS** Platform > **cihaz kısıtlamaları** profil türü için). Bu güncelleştirme, iCloud fotoğraf Arşivi'devre dışı bırakma seçeneği ve DEP ile kaydedilen cihazlar için yeni sınıf uygulama ayarları içerir.

Geçerli ayarları görmek için Git [izin ver veya bunları kısıtlama özellikleri Intune kullanarak macOS cihaz ayarları](device-restrictions-macos.md).

İçin geçerlidir: macOS 10.14.4 ve daha yeni

### <a name="android-enterprise-app-management----4459905-idready---"></a>Android Kurumsal Uygulama Yönetimi <!-- 4459905 idready -->
BT yöneticileri, yapılandırma ve kullanma Android Kuruluş Yönetimi kolaylaştırmak için Intune otomatik olarak dört ekler ortak Android Kurumsal uygulamaları için Intune Yönetici konsolunda ilgili. Dört Android kurumsal uygulamalar şunlardır:

- **[Microsoft Intune](https://play.google.com/store/apps/details?id=com.microsoft.intune)**  - tam olarak yönetilen Android Enterprise senaryoları için kullanılır.
- **[Microsoft Authenticator](https://play.google.com/store/apps/details?id=com.azure.authenticator)**  -oturum hesaplarınıza iki aşamalı doğrulama kullanırsanız yardımcı olur.
- **[Intune Şirket portalı](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)**  - uygulama koruma ilkelerini (APP) ve kurumsal Android iş profili senaryoları için kullanılır.
- [Giriş ekranı yönetilen](https://play.google.com/store/apps/details?id=com.microsoft.launcher.enterprise) - Android Kurumsal ayrılmış/bilgi noktası senaryoları için kullanılır.

Daha önce BT yöneticilerinin el ile bulun ve bu uygulamaları onaylamanızı gerekir [yönetilen Google Play store](https://play.google.com/store/apps) kurulumunun parçası olarak. Bu değişiklik, daha kolay ve müşterilerin Android kuruluş yönetimi kullanmak daha hızlı hale getirmek için bu daha önce el ile adımlar kaldırır.

Yöneticiler, yönetilen Google Play'e Intune kiracısının ilk bağlanma, zaman otomatik olarak kendi Intune uygulamaları listesine eklendi. Bu dört uygulamalar görürsünüz. Daha fazla bilgi için [yönetilen Google Play hesabınıza Intune hesabınıza bağlanın](connect-intune-android-enterprise.md). Kendi Kiracı, zaten bağlanmış veya zaten Android Kurumsal kullanan kiracılar için hiçbir şey yoktur yöneticilerinin yapmanız gerekir. Bu dört uygulamaları Mayıs 2019 hizmet dağıtım tamamlanma 7 gün içinde otomatik olarak gösterilir.

<!-- 1904 start-->

### <a name="advanced-settings-for-windows-defender-firewall----1311949---"></a>Windows Defender Güvenlik Duvarı için Gelişmiş ayarları <!-- 1311949 -->
Yakında istemciler için Windows Defender'ın özel bir güvenlik duvarı kurallarını yönetmek için Intune kullanmak mümkün olacaktır. Kural, uygulamalar, ağ adresleri ve bağlantı noktalarına gelen ve giden davranış belirtebilirsiniz. 


### <a name="device-users-can-view-all-managed-apps-theyve-installed-or-tried-to-install----2352913---"></a>Cihaz kullanıcılarının yüklü veya yüklemeyi denedi tüm yönetilen uygulamalar görüntüleyebilirsiniz. <!-- 2352913 -->
Tüm yönetilen uygulamalar için Şirket portalı Windows listeler&ndash; hem gerekli hem de kullanılabilir&ndash; bir kullanıcı cihazında yüklü. Kullanıcılar, denenen görüntülemek ve bekleyen uygulama yüklemelerini ve bunların geçerli durumlarını mümkün olacaktır. Kuruluşunuzun uygulamalarını gerekli veya kullanılabilir duruma getirilmez, kullanıcılar şirket uygulama yüklenmiş olduğunu açıklayan bir ileti görür. Kullanıcılar ayrıca sıralamak veya uygulamalarını yükleme durumuna göre filtre uygulamak mümkün olacaktır.

### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910---"></a>"Uygulanabilirlik kuralları" kullandığınızda Windows 10 cihaz yapılandırma profilleri oluşturma <!-- 2549910 -->
Windows 10 cihaz yapılandırma profilleri oluşturma (**cihaz Yapılandırması** > **profilleri** > **profili oluşturma**  >  **Windows 10** platform için). Oluşturma tutulacak bir **Uygulanabilirlik kuralı** profili yalnızca bir belirli sürüm veya belirli bir sürüme uygular. Örneğin, bazı BitLocker ayarları sağlayan bir profil oluşturun. Profili eklediğinizde profil, yalnızca Windows 10 Enterprise çalıştıran cihazlar için uygular bir geçerlilik kuralı kullanın.

Şunun için geçerlidir: 
- Windows 10 ve üzeri

###  <a name="intune-security-tasks-for-defender-atp-in-public-preview----3208597---"></a>Intune güvenlik görevleri için Defender ATP (genel Önizleme) <!-- 3208597 -->
Genel önizleme olarak kullanıma sunulacak, Intune hemen güvenlik görevlerini yeni duyurulan Microsoft Defender tehdit ve güvenlik açığı yönetimi için ekler.  Bu tümleştirme sayesinde güvenlik işlemleri yöneticileri Windows Defender ATP (WDATP) Intune yöneticileri için ortaya çıkan tehditleri için önerilen düzeltmeler daha etkili bir şekilde iletişim kurabilir. Güvenlik görevlerini eklenmesi, keşfedin, öncelik sırasına sokmanıza ve uç noktası Güvenlik Açıkları ve yanlış yapılandırmalarını düzeltmek için risk tabanlı bir yaklaşım ekler.

Intune'da güvenlik görevler hakkında daha fazla bilgi için ilgili blog gönderisine bakın [Microsoft Defender ATP'nin güvenlik açığı yönetimi ve tehdit genişletmek için Intune güvenlik görevlerini kullanarak](https://techcommunity.microsoft.com/t5/Enterprise-Mobility-Security/Microsoft-Intune-security-tasks-extend-Microsoft-Defender-ATP-s/ba-p/369857). 

### <a name="windows-defender-advanced-threat-protection-baseline----3754134---"></a>Windows Defender Gelişmiş tehdit koruması temeli <!-- 3754134 -->
Windows Defender Gelişmiş tehdit koruması ayarları yapılandırmanıza yardımcı olması için yeni temeli eklemek için ekleyeceğiz.



## <a name="notices"></a>Bildirimler

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

### <a name="see-also"></a>Ayrıca bkz.
Son geliştirmelere ilişkin ayrıntılar için bkz. [Microsoft Intune’daki Yenilikler](whats-new.md).


