---
title: Geliştirme-Microsoft Intune
titleSuffix: ''
description: Geliştirmede Microsoft Intune Özellikler
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/07/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.assetid: 25b3c26e-cf4e-4152-8306-bf4be4af2ad1
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 01ea2f75d166e5cc6aef4b890dba5722a74c1f61
ms.sourcegitcommit: 8f56220e7cafc5bc43135940575a9acb5afde730
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2020
ms.locfileid: "75827828"
---
# <a name="in-development-for-microsoft-intune---january-2020"></a>Microsoft Intune için geliştirme aşamasında-Ocak 2020

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

### <a name="display-notifications-for-the-company-portal-app-on-windows---1808082----"></a>Windows 'da Şirket Portalı uygulama için bildirimleri görüntüle<!-- 1808082  -->
Windows cihazlarındaki Şirket Portalı uygulamasını, uygulama kapatıldığında bile kullanıcılara bildirimler görüntüleyecek şekilde güncelleştireceğiz. Güncelleştirme, kullanılabilir uygulamalara ilişkin bildirimleri yalnızca yükleme durumu tamamlandığında veya başarısız olduğunda gösterir. Şirket Portalı uygulama gerekli uygulamalar için bildirimleri göstermez. 

### <a name="display-installation-status-messages-for-the-company-portal-app---2514416----"></a>Şirket Portalı uygulaması için yükleme durum iletilerini görüntüle<!-- 2514416  -->
Şirket Portalı uygulama son kullanıcılara ek uygulama yükleme durumu iletileri gösterecektir. Yeni Win32 bağımlılık özellikleri için aşağıdaki koşullar geçerli olacaktır:
- Uygulama yüklenemedi. Yönetici tarafından tanımlanan bağımlılıklar karşılanmadı.

### <a name="retarget-web-clips-to-microsoft-edge-on-ios-devices---5455276-idready---"></a>Web kliplerini iOS cihazlarında Microsoft Edge 'e yeniden hedefle<!-- 5455276 idready -->
İOS cihazlarında sabitlenmiş Web uygulamaları olarak davranan web klipleri güncelleştirilmeleri gerekecektir. Yeni dağıtılan web klipleri, korumalı bir tarayıcıda açmak gerekirse Intune Managed Browser yerine Microsoft Edge 'de açılır. Managed Browser yerine Microsoft Edge 'de açıldıklarından emin olmak için önceden mevcut web kliplerini yeniden hedeflemeniz gerekir. 

### <a name="user-experience-change-when-adding-apps-to-intune---4705829-idready---"></a>Intune 'a uygulama eklenirken Kullanıcı deneyimi değişikliği<!-- 4705829 idready -->
Intune aracılığıyla uygulama eklerken yeni bir kullanıcı deneyimi görürsünüz. Bu deneyim, daha önce kullandığınız ayarların ve ayrıntıların aynısını sağlar ancak yeni deneyim, bir uygulamayı Intune 'a eklemeden önce sihirbaza benzer bir işlem izler. Bu yeni deneyim, uygulamayı eklemeden önce bir gözden geçirme sayfası da sağlar. [Microsoft Uç Nokta Yöneticisi Yönetim merkezinden](https://go.microsoft.com/fwlink/?linkid=2109431), **uygulamalar** > **tüm uygulamalar** > **Ekle**' yi seçin. Daha fazla bilgi için bkz. [Microsoft Intune’a uygulama ekleme](~/apps/apps-add.md).

#### <a name="require-win32-apps-to-restart----3136567--"></a>Win32 uygulamalarının yeniden başlatılmasını gerektir <!-- 3136567-->
Başarılı bir yüklemeden sonra bir Win32 uygulamasının yeniden başlatılmasını zorunlu kılabilirsiniz. Ayrıca, yeniden başlatmanın gerçekleşmesi için gereken süreyi (yetkisiz kullanım süresi) seçebilirsiniz.

<!-- ***********************************************-->
## <a name="device-configuration"></a>Cihaz yapılandırması

### <a name="add-automatic-proxy-settings-to-wi-fi-profiles-for-android-enterprise-work-profiles---4490822-idready---"></a>Android kurumsal iş profillerine yönelik Wi-Fi profillerine otomatik ara sunucu ayarları ekleme<!-- 4490822 idready -->
Android kurumsal Iş profili cihazlarında Wi-Fi profilleri oluşturabilirsiniz. Wi-Fi kurumsal türünü seçtiğinizde, Wi-Fi ağınızda kullanılan Genişletilebilir Kimlik Doğrulama Protokolü (EAP) türünü de girebilirsiniz.

Gelecekteki bir güncelleştirmede kurumsal tür ' i seçtiğinizde, `proxy.contoso.com`gibi bir proxy sunucu URL 'SI de dahil olmak üzere otomatik proxy ayarlarını girebilirsiniz.

Yapılandırabileceğiniz geçerli Wi-Fi ayarlarını görmek için [Microsoft Intune ' de Android Enterprise ve Android bilgi noktası çalıştıran cihazlar Için Wi-Fi ayarları ekle](../configuration/wi-fi-settings-android-enterprise.md)' ye gidin.

Uygulama hedefi:
- Android kurumsal iş profili

### <a name="wired-network-device-configuration-profiles-for-macos-devices---3508686----"></a>MacOS cihazları için kablolu ağ cihaz yapılandırma profilleri<!-- 3508686  -->
Kablolu ağları yapılandıran yeni bir macOS cihaz yapılandırma profili kullanılabilir (**cihaz yapılandırma** > **profilleri** ** > ,** > Platform için **MacOS** > profil türü için **kablolu ağ** ). Kablolu ağları yönetmek için 802.1 x profilleri oluşturmak ve bu kablolu ağları macOS cihazlarınıza dağıtmak için bu özelliği kullanın.

Uygulama hedefi:
- Mac OS

### <a name="vpn-profiles-with-ikev2-vpn-connections-can-use-always-on-with-ios-devices----1947932-idready---"></a>IKEv2 VPN bağlantılarına sahip VPN profilleri, her zaman iOS cihazlarıyla birlikte kullanılabilir <!-- 1947932 idready -->
İOS cihazlarında, bir Ikev2 bağlantısı kullanan bir VPN profili oluşturabilirsiniz (**cihaz yapılandırma** > **profilleri** > profil **oluşturmak** için **iOS/ıpados** > , profil türü için iOS > **VPN** ). Gelecekteki bir güncelleştirmede, her zaman Ikev2 ile yapılandırabilirsiniz. Yapılandırıldığında, IKEv2 VPN profilleri otomatik olarak bağlanır ve VPN 'ye bağlı (veya hızlı bir şekilde yeniden bağlantı) kalır. Ağlar arasında hareket etmekle veya cihazları yeniden başlatırken bile bağlı kalır.

İOS 'ta, her zaman VPN, Ikev2 profilleriyle sınırlıdır.

Yapılandırabileceğiniz geçerli Ikev2 ayarlarını görmek için [Microsoft Intune iOS CIHAZLARıNDA VPN ayarları ekle](../configuration/vpn-settings-ios.md#ikev2-settings)' ye gidin.

Uygulama hedefi:
- iOS

### <a name="improved-user-interface-experience-when-creating-configuration-profiles-on-ios-and-macos-devices---5569008-5569039-5569057-5569110-5569116-5569131-5569139-5569153-5859984-idready---"></a>İOS ve macOS cihazlarında yapılandırma profilleri oluştururken Geliştirilmiş kullanıcı arabirimi deneyimi<!-- 5569008-5569039-5569057-5569110-5569116-5569131-5569139-5569153-5859984 idready -->
İOS veya macOS cihazları için bir profil oluşturduğunuzda, uç nokta yönetimi Yönetim Merkezi 'ndeki deneyim güncelleştirilir. Bu değişiklik, aşağıdaki cihaz yapılandırma profillerini**etkiler (cihaz** > **yapılandırma profilleri** > platform Için **iOS** veya **MacOS** > **profili oluşturma** ):

- Özel: iOS, macOS
- Cihaz özellikleri: iOS, macOS
- Cihaz kısıtlamaları: iOS, macOS
- Endpoint Protection: macOS
- Uzantılar: macOS
- Tercih dosyası: macOS

### <a name="improved-user-interface-experience-when-creating-oemconfig-configuration-profiles-on-android-enterprise-devices---5568645-idready----"></a>Android kurumsal cihazlarda OEMConfig yapılandırma profilleri oluştururken Geliştirilmiş kullanıcı arabirimi deneyimi<!-- 5568645 idready  -->
Android Kurumsal cihazları için bir OEMConfig profili oluştururken veya düzenlerken, Endpoint Management Yönetim Merkezi 'ndeki deneyim güncellenir. Güncelleştirilmiş deneyim, bir bakışta yapılandırdığınız ayarların özetini sağlayacaktır. Bu değişiklik, OEMConfig cihaz yapılandırma profilini (**cihazlar** > **yapılandırma profillerini** etkiler > platform için **Android Enterprise** >, profil türü için **oemconfig** ) > **oluşturur** .

Bu özellik şu platformlarda geçerlidir:
- Android Kurumsal 

<!-- ***********************************************-->
## <a name="device-enrollment"></a>Cihaz kaydı

### <a name="block-android-enrollments-by-device-manufacturer--5197392-idready--"></a>Android kayıtlarını cihaz üreticisine göre engelle<!--5197392 idready-->
Cihazın üreticisine bağlı olarak cihazların kaydedilmesini engelleyebilirsiniz. Bu, Android Cihaz Yöneticisi ve Android kurumsal iş profili cihazları için geçerlidir. Kayıt kısıtlamalarını görmek için [Microsoft Endpoint Manager yönetim merkezi](https://go.microsoft.com/fwlink/?linkid=2109431)> **cihazlar** > **Kayıt kısıtlamaları**' na gidin.



<!-- ***********************************************-->
## <a name="device-management"></a>Cihaz yönetimi


### <a name="new-information-in-device-details---4471759-5604099----"></a>Cihaz ayrıntılarında yeni bilgiler<!-- 4471759 5604099  -->
Cihazlar için **genel bakış** sayfasına aşağıdaki bilgiler eklenecektir:
- Bellek kapasitesi (cihazdaki fiziksel bellek miktarı)
- Depolama kapasitesi (cihazdaki fiziksel depolama miktarı) 
- CPU Işlemci türü ve hızı
- RAM ve işlemci verileri

<!-- ***********************************************-->
<!--## Intune apps-->
 

<!-- ***********************************************-->

<!--
## Monitoring and troubleshooting
-->


<!-- ***********************************************-->
## <a name="role-based-access-control"></a>Rol tabanlı erişim denetimi

### <a name="new-intune-built-in-role-endpoint-security-manager--4253397-idready--"></a>Yeni Intune yerleşik rol uç noktası Güvenlik Yöneticisi<!--4253397 idready-->
Yeni bir Intune yerleşik rolü mevcut olacaktır: Endpoint Security Manager. Bu yeni rol, yöneticilere Intune 'daki Endpoint Manager düğümüne tam erişim ve diğer alanlara yalnızca erişim izni verir. Rol, Azure AD 'den "Güvenlik Yöneticisi" rolünün bir genişletmesinden oluşur. Şu anda yalnızca rol olarak genel yöneticileriniz varsa, hiçbir değişiklik yapmanız gerekmez. Rolleri kullanıyorsanız ve Endpoint Security Manager 'ın sağladığı ayrıntı düzeyini beğenmezseniz, bu rolü kullanılabilir olduğunda atayın. Yerleşik roller hakkında daha fazla bilgi için bkz. [rol tabanlı erişim denetimi](role-based-access-control.md).

### <a name="intune-roles-user-interface-changes-coming--5801612-idready--"></a>Intune rolleri Kullanıcı arabirimi değişiklikleri geliyor<!--5801612 idready-->
[Microsoft Endpoint Manager yönetim merkezi](https://go.microsoft.com/fwlink/?linkid=2109431) > **Kiracı Yönetimi** > **rolleri** için Kullanıcı arabirimi, daha kolay ve sezgisel bir tasarıma göre değişecek. Bu deneyim, şimdi kullandığınız ayarların ve ayrıntıların aynısını sağlar, ancak yeni deneyim sihirbaz benzeri bir işlem kullanır.


<!-- ***********************************************-->
## <a name="security"></a>Güvenlik

### <a name="derived-credentials-support-on-android-cobo-devices--4839592--"></a>Android COBO cihazlarında türetilmiş kimlik bilgileri desteği<!--4839592-->
Android kurumsal tam olarak yönetilen cihazlarda türetilmiş kimlik bilgilerini kullanabilirsiniz. Entrust Datacard, ıntercede ve DıŞA purebred için türetilmiş bir kimlik bilgisi almak üzere destek eklenecektir. Uygulama kimlik doğrulaması, Wi-Fi, VPN veya S/MIME imzalama ve/veya şifrelemeyi destekleyen uygulamalarla şifreleme için türetilmiş bir kimlik bilgisi kullanabileceksiniz. 

<!-- ***********************************************-->
## <a name="notices"></a>Bildirimler

[!INCLUDE [Intune notices](../includes/intune-notices.md)]

## <a name="see-also"></a>Ayrıca bkz:
Son gelişmeler hakkında daha fazla bilgi için bkz. [Microsoft Intune](whats-new.md)yenilikleri.


