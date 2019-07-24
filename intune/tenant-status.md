---
title: Microsoft Intune kiracı durumu sayfası
titleSuffix: Microsoft Intune
description: Intune portalından çıkmadan önemli kiracı ayrıntılarını görüntülemek için Intune kiracı durumu sayfasını kullanın
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/23/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 946d46baf17a5ffdd4b567adca32b651cacb72bb
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2019
ms.locfileid: "67882233"
---
# <a name="intune-tenant-status-page"></a>Intune kiracı durumu sayfası
Kiracı durumu sayfası, kiracınız hakkındaki güncel ve önemli ayrıntıları görüntüleyebileceğiniz merkezi bir merkezdir. Ayrıntılar lisans kullanılabilirliği ve kullanımı, bağlayıcı durumu ve Intune hizmeti hakkındaki önemli iletişimleri içerir.  

Panoyu görüntülemek için Azure portal **Intune 'a > kiracı durumu**' na gidin.  Kiracı durumu **Yardım ve destek grubu**altında görünür.  

Sayfa dört alana ayrılır:

## <a name="tenant-details"></a>Kiracı ayrıntıları
Kiracı ayrıntıları kiracınız hakkında bir bakışta bilgi sağlar. Kiracı adınız ve konumunuz, MDM yetkiliniz ve kiracılar hizmeti yayın numaranız gibi ayrıntıları görüntüleyin. Hizmet sürüm numarası, Microsoft docs *'Taki Intune 'daki* yenilikler makalesinde açılan bir bağlantıdır. Yenilikler bölümünde, Intune hizmetine yönelik en son özellikler ve güncelleştirmeler hakkında bilgi edinebilirsiniz.  

Bu bölüm, kullanılabilir lisanslarınızla ilgili temel bilgileri ve kullanıcılara kaç tane atandığını da sağlar. Cihazlar için lisanslar gösterilmez.

## <a name="connector-status"></a>Bağlayıcı durumu
Bağlayıcı durumu, Intune için kullanılabilir olan tüm bağlayıcıların durumunu gözden geçirmek için tek durağı olan bir konumdur.  

Bağlayıcılar şunlardır:
- **Dış hizmetlere yapılandırdığınız bağlantılar**. Örneğin, *Apple Volume Purchase program* hizmeti veya *Windows Autopilot* hizmeti.  Bu tür bağlayıcının durumu, son başarılı eşitleme zamanına göre belirlenir.
- *Apple Push bildirim hizmetleri* (APNs) sertifikaları gibi **bir dış yönetilmeyen hizmete bağlanmak için gereken sertifikalar veya kimlik bilgileri**. Bu tür bağlayıcının durumu, sertifikanın veya kimlik bilgisinin süre sonu zaman damgasına göre belirlenir.  

Varsayılan olarak, ekran en fazla beş bağlayıcı gösterir. Kullanım için yapılandırmadığınız bağlayıcılar da dahil olmak üzere tüm kullanılabilir bağlayıcıları görüntülemek için bu listeyi genişletmek üzere **Tüm bağlayıcıları** göster ' i seçebilirsiniz.  

Sağlıksız bağlayıcılar her zaman listenin en üstünde görüntülenir. Ardından uyarılar içeren bağlayıcılar, sonra sağlıklı bağlayıcılar listesi. Henüz yapılandırmadığınız bağlayıcılar son olarak görünür.

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

Listeden bir bağlayıcı seçtiğinizde, Portal bu bağlayıcıyı oluşturmaya veya yapılandırmaya uygun olan portal sayfasını gösterir.  Örneğin, **VPP süre sonu tarihi** bağlayıcısını seçtiğinizde, o bağlayıcı hakkında daha fazla ayrıntıyı görüntüleyebileceğiniz **IOS toplu satın alınan program belirteçleri** sayfası açılır. Daha sonra yeni bir yapılandırma oluşturabilir veya var olan bir yapılandırma sorunlarını düzenleyebilir ve çözebilirsiniz.  

## <a name="intune-service-health"></a>Intune hizmet durumu  
Microsoft 365 hizmet durumu panosuna veya her ikisi de [Microsoft 365 Yönetim merkezinde](https://admin.microsoft.com)bulunan ileti merkezine gitmek zorunda kalmadan etkin olaylar ve Danışma bilgilerini görüntüleyebilirsiniz. Yalnızca kiracınızı etkilemek için etkinin belirtildiği olaylar gösterilir.  

Bir olay seçtiğinizde, olay ayrıntıları doğrudan kiracı durumu sayfasında sunulur. Geçmiş Danışma belgelerini ve olayları görüntülemek için **Geçmiş olayları/Danışma belgelerini**göster ' i seçin. Microsoft 365 Yönetim Merkezi açılır ve kiracınız için son 30 günden sonra Danışma belgelerini ve olayları görüntüleyebilirsiniz.  

*Intune hizmet durumu*bilgilerini görüntülemek için, hesabınız Azure Active Directory veya Microsoft 365 Yönetim Merkezi 'Nde **genel yönetici** veya **Hizmet Yöneticisi** rolüne sahip olmalıdır. Bu izinleri atamak için, [Microsoft 365 Yönetim merkezinde](https://admin.microsoft.com) genel yönetici izinleriyle oturum açın. **Etkin kullanıcılar > kullanıcılar**' ı seçin ve ardından erişim gerektiren hesabı seçin. Roller için **Düzenle** ' yi seçin, *Hizmet Yöneticisi* veya *genel yönetici*' yi seçin ve ardından Izinleri atamak için Düzenle ' yi **kaydedin** .  

Intune hizmet durumu için iletişim tercihlerinizi yalnızca Microsoft 365 Yönetim Merkezi aracılığıyla ayarlayabilirsiniz.

## <a name="intune-news"></a>Intune haberleri  
Office Ileti merkezine gitmek zorunda kalmadan Intune hizmet ekibinin bilgilendirici iletişimlerini görüntüleyin. İletişimler, son zamanlarda Intune hizmetinde gerçekleşen veya kiracınızın bir yolu olan değişikliklerle ilgili mesajlar içerir.  

Varsayılan olarak, son 10 etkin ileti görüntülenir. Eski iletileri görüntülemek için, Microsoft 365 Yönetim merkezinde *ileti merkezini* açmak üzere **geçmiş iletileri göster** ' i seçin.  

Intune haberleri bilgilerini görüntülemek için hesabınızın Azure Active Directory **genel yönetici** veya **hizmet yöneticisi** rolüne veya Microsoft 365 Yönetim merkezinde **ileti merkezi okuyucu** rolüne sahip olması gerekir.  Bu izni atamak için yönetici izinlerine sahip [Microsoft 365 Yönetim merkezinde](https://admin.microsoft.com) oturum açın. **Etkin kullanıcılar > kullanıcılar**' ı seçin ve ardından erişim gerektiren hesabı seçin. *Roller*için **Düzenle** ' yi seçin, *takımlar iletişim Yöneticisi*' ni seçin ve ardından Izinleri atamak için Düzenle ' yi **kaydedin** .  

Yalnızca Microsoft 365 Yönetim Merkezi aracılığıyla Intune haberleri için iletişim tercihlerinizi ayarlayabilirsiniz.
