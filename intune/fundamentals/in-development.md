---
title: Geliştirme-Microsoft Intune
titleSuffix: ''
description: Geliştirmede Microsoft Intune Özellikler
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/03/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.assetid: 25b3c26e-cf4e-4152-8306-bf4be4af2ad1
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1b590e8564f14ce9958c5a1c126edf5dd6740cd1
ms.sourcegitcommit: 47c9af81c385c7e893fe5a85eb79cf08e69e6831
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/25/2020
ms.locfileid: "77576392"
---
# <a name="in-development-for-microsoft-intune---february-2020"></a>Microsoft Intune için geliştirme sırasında-Şubat 2020

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

### <a name="retarget-web-clips-to-microsoft-edge-on-iosipados-devices---5455276---"></a>Web kliplerini iOS/ıpados cihazlarında Microsoft Edge 'e yeniden hedefle<!-- 5455276 -->
İOS/ıpados cihazlarında sabitlenmiş Web uygulamaları olarak davranan web klipleri güncelleştirilmeleri gerekecektir. Yeni dağıtılan web klipleri, korumalı bir tarayıcıda açmak gerekirse Intune Managed Browser yerine Microsoft Edge 'de açılır. Managed Browser yerine Microsoft Edge 'de açıldıklarından emin olmak için önceden mevcut web kliplerini yeniden hedeflemeniz gerekir.


<!-- ***********************************************-->
## <a name="device-configuration"></a>Cihaz yapılandırması

### <a name="wired-network-device-configuration-profiles-for-macos-devices---3508686----"></a>MacOS cihazları için kablolu ağ cihaz yapılandırma profilleri<!-- 3508686  -->
Kablolu ağları yapılandıran yeni bir macOS cihaz yapılandırma profili kullanılabilir (**cihaz yapılandırma** > **profilleri** ** > ,** > Platform için **MacOS** > profil türü için **kablolu ağ** ). Kablolu ağları yönetmek için 802.1 x profilleri oluşturmak ve bu kablolu ağları macOS cihazlarınıza dağıtmak için bu özelliği kullanın.

Uygulama alanı:
- Mac OS

### <a name="vpn-profiles-with-ikev2-vpn-connections-can-use-always-on-with-iosipados-devices----1947932-idready---"></a>IKEv2 VPN bağlantılarına sahip VPN profilleri, her zaman iOS/ıpados cihazlarıyla birlikte kullanılabilir <!-- 1947932 idready -->
İOS/ıpados cihazlarında, Ikev2 bağlantısı kullanan bir VPN profili oluşturabilirsiniz (**cihaz yapılandırma** > **profilleri** > profil **oluşturmak** için **iOS/IPA> DOS > iOS/ıpados** ). Gelecekteki bir güncelleştirmede, her zaman Ikev2 ile yapılandırabilirsiniz. Yapılandırıldığında, IKEv2 VPN profilleri otomatik olarak bağlanır ve VPN 'ye bağlı (veya hızlı bir şekilde yeniden bağlantı) kalır. Ağlar arasında hareket etmekle veya cihazları yeniden başlatırken bile bağlı kalır.

İOS/ıpados 'da, her zaman VPN Ikev2 profilleriyle sınırlıdır.

Yapılandırabileceğiniz geçerli Ikev2 ayarlarını görmek için [Microsoft Intune ' deki iOS/ıpados CIHAZLARıNDA VPN ayarları ekle](../configuration/vpn-settings-ios.md#ikev2-settings)' ye gidin.

Uygulama alanı:
- iOS

### <a name="improved-user-interface-experience-when-creating-configuration-profiles-on-iosipados-and-macos-devices---5569008-5569039-5569057-5569110-5569116-5569131-5569139-5569153-5859984-idready---"></a>İOS/ıpados ve macOS cihazlarında yapılandırma profilleri oluştururken Geliştirilmiş kullanıcı arabirimi deneyimi<!-- 5569008-5569039-5569057-5569110-5569116-5569131-5569139-5569153-5859984 idready -->
İOS/ıpados veya macOS cihazları için bir profil oluşturduğunuzda, uç nokta yönetimi Yönetim Merkezi 'ndeki deneyim güncelleştirilir. Bu değişiklik, aşağıdaki cihaz yapılandırma profillerini**etkiler (cihaz** > **yapılandırma profilleri** > platform Için **iOS** veya **MacOS** > **profili oluşturma** ):

- Özel: iOS/ıpados, macOS
- Cihaz özellikleri: iOS/ıpados, macOS
- Cihaz kısıtlamaları: iOS/ıpados, macOS
- Endpoint Protection: macOS
- Uzantılar: macOS
- Tercih dosyası: macOS

### <a name="improved-user-interface-experience-when-creating-oemconfig-configuration-profiles-on-android-enterprise-devices---5568645-idready----"></a>Android kurumsal cihazlarda OEMConfig yapılandırma profilleri oluştururken Geliştirilmiş kullanıcı arabirimi deneyimi<!-- 5568645 idready  -->
Android Kurumsal cihazları için bir OEMConfig profili oluştururken veya düzenlerken, Endpoint Management Yönetim Merkezi 'ndeki deneyim güncellenir. Güncelleştirilmiş deneyim, bir bakışta yapılandırdığınız ayarların özetini sağlayacaktır. Bu değişiklik, OEMConfig cihaz yapılandırma profilini (**cihazlar** > **yapılandırma profillerini** etkiler > platform için **Android Enterprise** >, profil türü için **oemconfig** ) > **oluşturur** .

Bu özellik şu platformlarda geçerlidir:
- Android Kurumsal 


<!-- ***********************************************-->
<!--## Device enrollment-->


<!-- ***********************************************-->
## <a name="device-management"></a>Cihaz yönetimi

### <a name="change-primary-user-for-windows-devices----3794742---"></a>Windows cihazları için birincil kullanıcıyı değiştirme <!-- 3794742 -->
Windows karma ve Azure AD 'ye katılmış cihazlar için birincil kullanıcıyı değiştirebileceksiniz. Bunu yapmak için **ıntune** > **cihazlar** > **tüm cihazlar** ' a gidin > bir cihaz > **özellikleri** > **birincil Kullanıcı**seçin. 


<!-- ***********************************************-->
<!--## Intune apps-->
 

<!-- ***********************************************-->
<!--
## Monitoring and troubleshooting
-->

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

<!-- ***********************************************-->
## <a name="notices"></a>Bildirimler

[!INCLUDE [Intune notices](../includes/intune-notices.md)]

## <a name="see-also"></a>Ayrıca bkz.
Son gelişmeler hakkında daha fazla bilgi için bkz. [Microsoft Intune](whats-new.md)yenilikleri.


