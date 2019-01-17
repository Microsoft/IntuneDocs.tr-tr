---
title: Microsoft Intune Kiracı durumu sayfası
titleSuffix: Microsoft Intune
description: Intune portalından ayrılmak zorunda kalmadan önemli Kiracı ayrıntılarını görüntülemek için Intune Kiracı durumu sayfasını kullanabilirsiniz
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/09/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 98b3180bc90c7b54213781ddf8b6668918b22dd3
ms.sourcegitcommit: 4a7421470569ce4efe848633bd36d5946f44fc8d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2019
ms.locfileid: "54203797"
---
# <a name="intune-tenant-status-page"></a>Intune Kiracı durumu sayfası
Kiracı durumu sayfası, Kiracı, lisans kullanılabilirlik ve kullanımı, bağlayıcı durumu ve Intune hizmeti hakkında önemli iletişimleri hakkında önemli ayrıntıları güncel kalın için merkezi bir merkez olarak kullanın.  

Azure portal gidin, panoyu görüntülemek için **Intune > Kiracı durumu**.  Kiracı durumu altında görünür **Yardım ve Destek grubu**.  

Sayfa dört alana ayrılır:

## <a name="tenant-details"></a>Kiracı ayrıntıları
Kiracınızın ayrıntılarının kiracınız hakkında bir bakışta bilgiler sağlar. Ayrıntıları Görüntüle, Kiracı adınızın ve konumu, MDM yetkilinizi ve kiracılara hizmet sürüm numaranızı gibi. Hizmet sürüm numarasıdır açan bir bağlantıya *Intune'daki yenilikler* burada okuyabilir en son özellikler ve güncelleştirmeler hakkında Microsoft docs'ta makale Intune hizmetine.  

Bu bölüm, ayrıca mevcut lisanslarınızı ve kaç kullanıcılara atanan ve hakkındaki temel bilgileri sağlar. Cihazlar için lisans gösterilmez.

## <a name="connector-status"></a>Bağlayıcı durumu
Bağlayıcı durumu, Intune için tüm kullanılabilir bağlayıcılar durumunu gözden geçirmek için bir tek yerdir.  

Bağlayıcılar şunlardır:
- **Dış hizmetler için yapılandırdığınız bağlantı**. Örneğin, *Apple Volume Purchase Program* hizmet veya *Windows Autopilot* hizmeti.  Durum bu tür bir bağlayıcı için son başarılı eşitleme zamanını üzerinde temel alır.
- **Sertifikaları veya yönetilmeyen bir dış hizmete bağlanmak için gerekli kimlik bilgilerini**gibi *Apple anında iletme bildirimi Hizmetleri* (APNS) sertifikaları. Bu tür bir bağlayıcı için durumu, sertifika veya kimlik bilgisi bitiş zaman damgası üzerinde temel alır.  

Varsayılan olarak, yalnızca beş bağlayıcı görüntülenir. Seçebileceğiniz **tüm bağlayıcıların** kullanılmak üzere yapılandırılmış henüz bağlayıcılar dahil olmak üzere tüm kullanılabilir bağlayıcılar görüntülemek için bu listeyi genişletin.  

Yoktur, herhangi bir türde tek bir bağlayıcıyı birden fazla durum aynı söz konusu bağlayıcıların tümü için özetidir. Tek bir bağlayıcıyı az sağlıklı durumu sistem grubu için kullanılır.  

Sağlıksız bağlayıcılar her zaman listenin en üstünde görüntüler. Sonraki bağlayıcılar uyarıları ve Sağlıklı bağlayıcıların listesi var. Bağlayıcılar henüz yapılandırmadıysanız, son görünür.

**Bağlayıcı durumu:**
- **Sağlıksız:**
    - Sertifika veya kimlik bilgisi süresi doldu
    - Son eşitleme en az üç gün öncesine ait
- **Uyarı:**
    - Sertifika veya kimlik bilgisi yedi gün içinde sona erecek
    - Son eşitleme bir günden daha önce olduğu
- **İyi durumda:**
    - Sertifika veya kimlik bilgisi sonraki yedi gün içinde süresi dolacak olmaz
    - Son eşitleme bir günden kısa süre önce oluştu  

Listeden bir bağlayıcı'yı seçtiğinizde, portal, oluşturma veya bu bağlayıcıyı yapılandırma ile ilgili portal sayfasının sunar.  Örneğin, seçtiğinizde, **VPP sona erme tarihi** bağlayıcısını **iOS toplu satın alma programı belirteçleri** sayfası bu Bağlayıcısı hakkında daha fazla ayrıntı görüntüleyebileceğiniz açılır. Ardından yeni bir yapılandırma oluşturmak veya da düzenleyebilir ve mevcut bir sorunları giderin.  

## <a name="intune-service-health"></a>Intune hizmet durumu  
Microsoft 365 hizmet durumu panosu veya ileti merkezi gitmek zorunda kalmadan etkin olaylar ve önerileri ayrıntılarını görüntüleyebilir, hem Microsoft 365 Yönetim merkezinde bulunan https://portal.office.com. Burada etkisi kiracınız etkilemek için Not olayları gösterilmektedir.  

Bir olay seçtiğinizde, olay ayrıntılarını Kiracı durumu sayfasında doğrudan sunulur. Önerileri ve olayları görüntülemek için seçin **olaylar/önerileri görmek**. Microsoft 365 Yönetici merkezi açılır ve kiracınız için ardından önerileri ve son 30 güne ait olayları görüntüleyebilir.  

Bilgilerini görüntülemek için *Intune hizmet durumu*, hesabınızın olması gerekir **genel yönetici** veya **Hizmet Yöneticisi** Azure Active Directory'de rolü veya Office Yönetim Portalı. Bu izinleri atamak üzere oturum [Microsoft 365 Yönetim merkezini](https://portal.officeppe.com/AdminPortal/Home#/homepage) genel yönetici izinlerine sahip. Seçin **kullanıcılar > etkin kullanıcılar**ve ardından erişim gerektiren bir hesabı seçin. Seçin **Düzenle** rolleri için seçin *Hizmet Yöneticisi* veya *genel yönetici*, ardından **Kaydet** atamak için Düzenle izinler.  

İletişim tercihlerinizi Microsoft 365 Yönetim merkezinden Intune hizmet durumu yalnızca ayarlayabilirsiniz.

## <a name="intune-news"></a>Intune Haberleri  
Intune hizmet ekibi bilgilendirme iletişimi, Office ileti merkezine gitmek zorunda kalmadan görüntüleyin. İletişim, Intune hizmetine yakın zamanda gerçekleşen veya şekilde kiracınız için olan değişiklikler hakkında iletileri içerir.  

Varsayılan olarak, son 10 etkin iletileri görüntüleyin. Eski iletileri görüntülemek için seçin **iletilere bakın** açmak için *ileti Merkezi* Microsoft 365 Yönetim Merkezi portalında.  

Intune haber bilgilerini görüntülemek için hesabınızın olması gerekir **genel yönetici** veya **Hizmet Yöneticisi** Azure Active Directory'de rol veya atanmış **ileti merkezi okuyucusu**  rol Office Yönetim Portalı'nda.  Bu izin atamak için oturum açın [Microsoft 365 Yönetim merkezini](https://portal.officeppe.com/AdminPortal/Home#/homepage) yönetici izinlerine sahip. Seçin **kullanıcılar > etkin kullanıcılar**ve ardından erişim gerektiren bir hesabı seçin. Seçin **Düzenle** için *rolleri*seçin *takımlar iletişimleri Yöneticisi*, ardından **Kaydet** izinleri atamak için düzenleme.  

İletişim tercihlerinizi Microsoft 365 Yönetim merkezinden Intune haber yalnızca ayarlayabilirsiniz.