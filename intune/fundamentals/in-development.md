---
title: Geliştirme-Microsoft Intune
titleSuffix: ''
description: Geliştirmede Microsoft Intune Özellikler
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 12/19/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.assetid: 25b3c26e-cf4e-4152-8306-bf4be4af2ad1
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 35e4612c9aa482204ea61c46c5cc56051874e6de
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/19/2019
ms.locfileid: "75207409"
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

### <a name="user-licensed-vpp-apps-for-user-enrollment-ios-devices---5619268---"></a>Kullanıcı kaydı iOS cihazları için Kullanıcı lisanslı VPP uygulamaları<!-- 5619268 -->
Kullanıcı kaydı iOS cihazlarında, son kullanıcılar artık kullanılabilir olarak dağıtılan cihaz lisanslı VPP uygulamalarıyla birlikte sunulmayacaktır. Ancak, son kullanıcılar Şirket Portalı içindeki Kullanıcı lisanslı tüm VPP uygulamalarını görmeye devam eder. VPP uygulamaları hakkında daha fazla bilgi için bkz. [Microsoft Intune ile Apple Volume Purchase program aracılığıyla satın alınan iOS ve macOS uygulamalarını yönetme](~/apps/vpp-apps-ios.md).

### <a name="retrieve-personal-recovery-key-from-mem-encrypted-macos-devices---4851745---"></a>MEM şifreli macOS cihazlarından kişisel kurtarma anahtarını alma<!-- 4851745 -->
Son kullanıcılar, iOS Şirket Portalı uygulamasını kullanarak kişisel kurtarma anahtarını (Filekasası anahtarı) alabilecektir. Kişisel kurtarma anahtarına sahip olan cihaz Intune 'a kaydolmalıdır ve Intune aracılığıyla Filekasasıyla şifrelenir. Son Kullanıcı iOS Şirket Portalı uygulamasını kullanarak Safari web görünümünü açabilir ve kişisel kurtarma anahtarlarını alabilir. Intune 'da, *şifreli ve kayıtlı macOS cihazı* > **kurtarma anahtarı al** > **cihazları** ' nı seçin. Filekasası hakkında daha fazla bilgi için bkz. [macOS Için dosya Kasası şifrelemesi](~/protect/encrypt-devices.md#filevault-encryption-for-macos).

### <a name="display-notifications-for-the-company-portal-app-on-windows---1808082----"></a>Windows 'da Şirket Portalı uygulama için bildirimleri görüntüle<!-- 1808082  -->
Windows cihazlarındaki Şirket Portalı uygulamasını, uygulama kapatıldığında bile kullanıcılara bildirimler görüntüleyecek şekilde güncelleştireceğiz. Güncelleştirme, kullanılabilir uygulamalara ilişkin bildirimleri yalnızca yükleme durumu tamamlandığında veya başarısız olduğunda gösterir. Şirket Portalı uygulama gerekli uygulamalar için bildirimleri göstermez.

### <a name="display-installation-status-messages-for-the-company-portal-app---2514416----"></a>Şirket Portalı uygulaması için yükleme durum iletilerini görüntüle<!-- 2514416  -->
Şirket Portalı uygulama son kullanıcılara ek uygulama yükleme durumu iletileri gösterecektir. Yeni Win32 bağımlılık özellikleri için aşağıdaki koşullar geçerli olacaktır:
- Uygulama yüklenemedi. Yönetici tarafından tanımlanan bağımlılıklar karşılanmadı.

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


<!-- ***********************************************-->
<!--## Device enrollment-->

<!-- ***********************************************-->
<!--## Device management-->


<!-- ***********************************************-->
<!--## Intune apps-->
 

<!-- ***********************************************-->

<!--
## Monitoring and troubleshooting
-->


<!-- ***********************************************-->
<!--## Role-based access control-->


<!-- ***********************************************-->

<!--
## Security
-->

<!-- ***********************************************-->
## <a name="notices"></a>Bildirimler

[!INCLUDE [Intune notices](../includes/intune-notices.md)]

## <a name="see-also"></a>Ayrıca bkz:
Son gelişmeler hakkında daha fazla bilgi için bkz. [Microsoft Intune](whats-new.md)yenilikleri.


