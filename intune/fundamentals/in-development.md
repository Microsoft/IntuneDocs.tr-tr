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
ms.openlocfilehash: ea5fae72f6e2057ef0b03a7bd295085ed1ac3bbd
ms.sourcegitcommit: 5807f4db4a45a093ce2fd6cb0c480bec384ec1ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72601538"
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

### <a name="assign-the-microsoft-edge-beta-for-macos----4678761----"></a>MacOS için Microsoft Edge Beta 'yı atama <!-- 4678761  -->
MacOS cihazları için Microsoft Edge Beta 'nın en son sürümünü Intune 'a ekleyip atayabileceksiniz. 

MacOS cihazları için Microsoft Edge Beta 'yı atamak için:
1. Intune 'da **istemci uygulamaları** > **uygulamalar** > **Uygulama Ekle** > **Microsoft Edge-MacOS**' u seçin. 
1. Microsoft Edge Beta 'yı amaçlanan gruplara atayın. Microsoft otomatik güncelleştirme (MAU), Microsoft Edge 'i güncel tutar. 
 
Microsoft Edge hakkında daha fazla bilgi için, [Microsoft Intune Ile Microsoft Edge kullanarak Web erişimini yönetme](../apps/manage-microsoft-edge.md)makalesine bakın.

### <a name="configure-app-notification-content-for-organization-accounts----2576686---"></a>Kuruluş hesapları için uygulama bildirim içeriğini yapılandırma <!-- 2576686 -->
Android ve iOS cihazlarında Intune UYGULAMASı, kuruluş hesapları için uygulama bildirim içeriğini denetlemenize olanak tanır. Bu özellik, uygulamalardan destek gerektirecektir ve uygulama özellikli tüm uygulamalar için kullanılamayabilir. UYGULAMA hakkında daha fazla bilgi için bkz. [Uygulama koruma Ilkeleri nelerdir?](../apps/app-protection-policy.md)


<!-- ***********************************************-->
## <a name="device-configuration"></a>Cihaz yapılandırması

### <a name="new-device-firmware-configuration-interface-profile-for-devices-that-run-windows-10-and-later----2266073----"></a>Windows 10 ve üzeri çalıştıran cihazlar için yeni cihaz üretici yazılımı yapılandırma arabirimi profili <!-- 2266073  -->
Windows 10 ve üzeri sürümlerde, ayarları ve özellikleri denetlemek için bir cihaz yapılandırma profili oluşturabilirsiniz: 

1. **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**'u seçin.
1. Platform için **Windows 10 ve üzeri**' i seçin. 
 
Yeni bir cihaz üretici yazılımı yapılandırma arabirimi profil türü, Intune 'un UEFı (BIOS) ayarlarını yönetmesine olanak tanır.

Yapılandırabileceğiniz geçerli ayarlar hakkında daha fazla bilgi için, bkz. [Microsoft Intune cihaz profillerini kullanarak cihazlarınızda özellikleri ve ayarları uygulama](../configuration/device-profiles.md).

Bu özellik, select cihazlarda Windows 10 RS5 (1809) ve üzeri için geçerlidir.
 

<!-- ***********************************************-->
## <a name="device-enrollment"></a>Cihaz kaydı

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

### <a name="target-macos-user-groups-to-require-jamf-management----4061739---"></a>JAMF yönetimini gerektirecek macOS Kullanıcı gruplarını hedefleme <!-- 4061739 -->
Belirli kullanıcı gruplarını, macOS cihazlarının JAMF tarafından yönetilmesini gerektirecek şekilde hedefleyebilir. Bu hedefleme, diğer cihazlar Intune tarafından yönetilmeye devam ederken, bir macOS cihazları alt kümesine JAMF uyumluluk tümleştirmesini uygulamanızı sağlayacaktır. Hedefleme, kullanıcıların cihazlarını bir mobil cihaz yönetimi (MDM) sisteminden diğerine kademeli olarak geçireceğinizi de sağlar.

### <a name="deploy-software-updates-to-macos-devices----3194876---"></a>MacOS cihazlarına yazılım güncelleştirmeleri dağıtma <!-- 3194876 -->
MacOS cihazları gruplarına yazılım güncelleştirmeleri dağıtabileceksiniz. Bu özellik kritik, bellenim, yapılandırma dosyası ve diğer güncelleştirmeleri içerir. Sonraki cihaz iadede güncelleştirmeleri gönderebilirsiniz. İsterseniz güncelleştirmeleri dağıtmak için haftalık bir zamanlama seçerek veya ayarladığınız süreleri alabilir. 

Bu özellik, yardım masanızın tam olarak çalıştığı zaman, cihazları standart çalışma saatleri veya dış saatler dışında güncelleştirmek istediğinizde yardımcı olur. Ayrıca güncelleştirmelerin dağıtıldığı tüm macOS cihazlarının ayrıntılı bir raporunu alırsınız. Belirli bir güncelleştirmenin durumunu görmek için raporun cihaza gidebilirsiniz.

<!-- ***********************************************-->
## <a name="monitoring-and-troubleshooting"></a>İzleme ve sorun giderme

### <a name="android-report-on-the-devices-overview-page----2984353----"></a>Cihazlara Genel Bakış sayfasında Android raporuna <!-- 2984353  -->
**Cihazlara genel bakış** sayfasına yeni bir rapor ekleyeceğiz. Rapor, her bir cihaz yönetimi çözümüne kaç tane Android cihaz kaydedildiğini gösterir. Grafik, iş profili için cihaz sayısını, tam olarak yönetilen, adanmış ve Cihaz Yöneticisi kayıtlı olduğunu gösterir. 

Raporu görmek için **ıntune** > **cihaz** > **genel bakış**' ı seçin.

### <a name="updated-support-experience-------5012398------"></a>Güncelleştirilmiş destek deneyimi   <!--  5012398    -->
Geliştirmeye devam etmenin bir parçası olarak, Intune için konsol içi destek deneyimini güncelleştireceğiz.  Genel sorunlar için konsol içi arama ve geri bildirim işlemlerini geliştireceğiz ve destek ile iletişim kurmak için iş akışını kolaylaştırıyoruz.     

<!-- ***********************************************-->
<!--## Security-->


<!-- ***********************************************-->
## <a name="notices"></a>Bildirimler

[!INCLUDE [Intune notices](../includes/intune-notices.md)]

## <a name="see-also"></a>Ayrıca bkz:
Son gelişmeler hakkında daha fazla bilgi için bkz. [Microsoft Intune](whats-new.md)yenilikleri.
