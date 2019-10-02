---
title: Microsoft Intune kiracı durumu sayfası
titleSuffix: Microsoft Intune
description: Intune portalından çıkmadan önemli kiracı ayrıntılarını görüntülemek için Intune kiracı durumu sayfasını kullanın
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 09/05/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b55623dec2a89df700da8c0adb1c64e7e754043f
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71729417"
---
# <a name="use-the-intune-tenant-status-page"></a>Intune kiracı durumu sayfasını kullanın
Microsoft Intune kiracı durumu sayfası, kiracınız hakkındaki güncel ve önemli ayrıntıları görüntüleyebileceğiniz merkezi bir merkezdir. Ayrıntılar lisans kullanılabilirliği ve kullanımı, bağlayıcı durumu ve Intune hizmeti hakkındaki önemli iletişimleri içerir.  

Panoyu görüntülemek için [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) 'da oturum açın ve ardından **kiracı durumu**' nu seçin.  *Kiracı durumu* **Yardım ve destek**altında görünür.  

Sayfa üç sekmeye bölünür:

## <a name="tenant-details"></a>Kiracı ayrıntıları
Kiracı ayrıntıları kiracınız hakkında bir bakışta bilgi sağlar. Kiracı adınız ve konumunuz, MDM yetkiliniz ve kiracılar hizmeti yayın numaranız gibi ayrıntıları görüntüleyin. Hizmet sürüm numarası, Microsoft docs *'Taki Intune 'daki* yenilikler makalesinde açılan bir bağlantıdır. Yenilikler *bölümünde,* Intune hizmetine yönelik en son özellikler ve güncelleştirmeler hakkında bilgi edinebilirsiniz.  

Bu sekmede ayrıca, kullanılabilir lisanslarınızla ilgili temel bilgileri ve kullanıcılara kaç tane atandığını bulabilirsiniz. Cihazlar için lisanslar gösterilmez.

## <a name="connector-status"></a>Bağlayıcı durumu
Bağlayıcı durumu, Intune için kullanılabilir olan tüm bağlayıcıların durumunu gözden geçirmek için tek durağı olan bir konumdur.  

Bağlayıcılar şunlardır:
- **Dış hizmetlere yapılandırdığınız bağlantılar**. Örneğin, *Apple Volume Purchase program* hizmeti veya *Windows Autopilot* hizmeti.  Bu tür bağlayıcının durumu, son başarılı eşitleme zamanına göre belirlenir.
- *Apple Push bildirim hizmetleri* (APNs) sertifikaları gibi **bir dış yönetilmeyen hizmete bağlanmak için gereken sertifikalar veya kimlik bilgileri**. Bu tür bağlayıcının durumu, sertifikanın veya kimlik bilgisinin süre sonu zaman damgasına göre belirlenir.  

*Bağlayıcı durumu* sekmesini açtığınızda, sağlıksız bağlayıcılar listenin en üstünde görüntülenir. Ardından uyarılar içeren bağlayıcılar, sonra sağlıklı bağlayıcılar listesi. Henüz yapılandırmadığınız bağlayıcılar en son *etkin değil*olarak görünür.

Herhangi bir türden birden fazla bağlayıcı varsa, bu durum aynı bağlayıcıların hepsi için bir özettir. Tek bir bağlayıcının en az sağlıklı durumu, grup için sistem durumu olarak kullanılır.  

**Bağlayıcı durumu:**
- **Sağlıksız**
  - Sertifika veya kimlik bilgisinin süresi doldu
  - Son eşitleme üç veya daha fazla gün önce
- **Warning**
  - Sertifikanın veya kimlik bilgisinin süresi yedi gün içinde dolacak
  - Son eşitleme bir günden daha önce
- **Sağlıklı**
  - Sertifika veya kimlik bilgisinin süresi önümüzdeki yedi gün içinde dolacak
  - Son eşitleme bir günden daha önce  

Listeden bir bağlayıcı seçtiğinizde, Portal bu bağlayıcı ile ilgili olan portal sayfasını gösterir. Bağlayıcılar sayfasından, daha önce yapılandırılmış bağlayıcıların durumunu görüntüleyebilir veya bu türde yeni bir bağlayıcı eklemek veya oluşturmak için seçenekleri belirleyebilirsiniz.

Örneğin, **VPP süre sonu tarihi** bağlayıcısını seçerseniz, o bağlayıcı hakkında daha fazla ayrıntıyı görüntüleyebileceğiniz **IOS toplu satın alınan program belirteçleri** sayfası açılır. Ayrıca, yeni bir yapılandırma oluşturabilir veya var olan bir yapılandırma sorunlarını düzenleyebilir ve giderebilirsiniz.

## <a name="service-health-dashboard"></a>Hizmet durumu panosu  
Hizmet durumu panosunda, kiracınızı etkileyen *hizmet olaylarına* ilişkin ayrıntıları ve güncelleştirmeler ve planlanan değişiklikler hakkında bilgi sağlayan *Intune haberlerini* görüntüleyebilirsiniz.

### <a name="intune-service-health"></a>Intune hizmet durumu
Microsoft 365 hizmet durumu panosuna veya her ikisi de [Microsoft 365 Yönetim merkezinde](https://admin.microsoft.com)bulunan ileti merkezine gitmek zorunda kalmadan etkin olaylar ve Danışma belgeleri ayrıntılarını görüntüleyin. Yalnızca kiracınızı etkileyen olaylar gösterilir.  

Bir olay seçtiğinizde, olay ayrıntıları doğrudan kiracı durumu sayfasında sunulur. Geçmiş Danışma belgelerini ve olayları görüntülemek için **Geçmiş olayları/Danışma belgelerini**göster ' i seçin. Microsoft 365 Yönetim Merkezi açılır ve kiracınız için son 30 günden sonra Danışma belgelerini ve olayları görüntüleyebilirsiniz.  

*Intune hizmet durumu*bilgilerini görüntülemek için, hesabınız Azure Active Directory veya Microsoft 365 Yönetim Merkezi 'Nde **genel yönetici** veya **Hizmet Yöneticisi** rolüne sahip olmalıdır. Bu izinleri atamak için, [Microsoft 365 Yönetim merkezinde](https://admin.microsoft.com) genel yönetici izinleriyle oturum açın. **Etkin kullanıcılar > kullanıcılar**' ı seçin ve ardından erişim gerektiren hesabı seçin. Roller için **Düzenle** ' yi seçin, *Hizmet Yöneticisi* veya *genel yönetici*' yi seçin ve ardından Izinleri atamak için Düzenle ' yi **kaydedin** .  

Intune hizmet durumu için iletişim tercihlerinizi yalnızca Microsoft 365 Yönetim Merkezi aracılığıyla ayarlayabilirsiniz.

### <a name="intune-news"></a>Intune haberleri  
Office Ileti merkezine gitmek zorunda kalmadan Intune hizmet ekibinin bilgilendirici iletişimlerini görüntüleyin. İletişimler, son zamanlarda Intune hizmetinde gerçekleşen veya kiracınızın bir yolu olan değişikliklerle ilgili mesajlar içerir.  

Varsayılan olarak, en son 10 ve etkin iletiler görüntülenir. Eski iletileri görüntülemek için, Microsoft 365 Yönetim merkezinde *ileti merkezini* açmak üzere **geçmiş iletileri göster** ' i seçin.  

Intune haberleri bilgilerini görüntülemek için hesabınızın Azure Active Directory **genel yönetici** veya **hizmet yöneticisi** rolüne veya Microsoft 365 Yönetim merkezinde **ileti merkezi okuyucu** rolüne sahip olması gerekir.  Bu izni atamak için yönetici izinlerine sahip [Microsoft 365 Yönetim merkezinde](https://admin.microsoft.com) oturum açın. **Etkin kullanıcılar > kullanıcılar**' ı seçin ve ardından erişim gerektiren hesabı seçin. *Roller*için **Düzenle** ' yi seçin, *takımlar iletişim Yöneticisi*' ni seçin ve ardından Izinleri atamak için Düzenle ' yi **kaydedin** .  

Yalnızca Microsoft 365 Yönetim Merkezi aracılığıyla Intune haberleri için iletişim tercihlerinizi ayarlayabilirsiniz.
