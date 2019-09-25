---
title: Microsoft Intune için ağ gereksinimleri ve bant genişliği ayrıntıları
titleSuffix: ''
description: Intune için ağ yapılandırma gereksinimlerini ve bant genişliği ayrıntılarını gözden geçirin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/17/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 0f737d48-24bc-44cd-aadd-f0a1d59f6893
ms.reviewer: kerimh
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: e6d5e8d76a06ac45fed2b9759e519ffc7fabf7ec
ms.sourcegitcommit: d2989b9992d10d133573d9bc31479659fb7e242c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2019
ms.locfileid: "71238301"
---
# <a name="intune-network-configuration-requirements-and-bandwidth"></a>Intune ağ yapılandırma gereksinimleri ve bant genişliği

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

Intune dağıtımlarınızın bant genişliği gereksinimlerini anlamak için bu bilgileri kullanabilirsiniz.

## <a name="average-network-traffic"></a>Ortalama ağ trafiği
Bu tabloda her istemci için ağ üzerinden geçen ortak içeriğin yaklaşık boyutu ve sıklığı listelenmiştir.

> [!NOTE]
> Cihazların Intune güncelleştirmeleri ve içeriklerini alabilmeleri için düzenli aralıklarla İnternet’e bağlanmaları gerekir. Güncelleştirmeleri veya içerikleri almak için gereken süre farklılık gösterir, ancak cihazların her gün en az bir saat boyunca kesintisiz olarak İnternet’e bağlı kalması gerekir.

|İçerik türü|Yaklaşık boyut|Sıklık ve ayrıntılar|
|----------------|--------------------|-------------------------|
|Intune istemci yüklemesi<br /><br />**Aşağıdaki gereksinimler Intune istemci yüklemesine ek niteliğindedir**|125 MB|**Bir kez**<br /><br />İstemcinin boyutu, istemci bilgisayarın işletim sistemine bağlı olarak değişir.|
|İstemci kayıt paketi|15 MB|**Bir kez**<br /><br />Bu içerik türü için güncelleştirmeler olduğunda ek indirmeler yapılabilir.|
|Endpoint Protection aracısı|65 MB|**Bir kez**<br /><br />Bu içerik türü için güncelleştirmeler olduğunda ek indirmeler yapılabilir.|
|Operations Manager aracısı|11 MB|**Bir kez**<br /><br />Bu içerik türü için güncelleştirmeler olduğunda ek indirmeler yapılabilir.|
|İlke aracısı|3 MB|**Bir kez**<br /><br />Bu içerik türü için güncelleştirmeler olduğunda ek indirmeler yapılabilir.|
|Microsoft Easy Assist aracısı üzerinden Uzak Yardım|6 MB|**Bir kez**<br /><br />Bu içerik türü için güncelleştirmeler olduğunda ek indirmeler yapılabilir.|
|Günlük istemci işlemleri|6 MB|**Günlük**<br /><br />Intune istemcisi güncelleştirmeleri ve ilkeleri denetlemek ve istemcinin durumunu hizmete raporlamak üzere Intune hizmetiyle düzenli olarak iletişim kurar.|
|Endpoint Protection kötü amaçlı yazılım tanımı güncelleştirmeleri|Varies<br /><br />Genellikle 40 KB ile 2 MB arasında|**Günlük**<br /><br />Günde en fazla üç kez.|
|Endpoint Protection altyapı güncelleştirmesi|5 MB|**Aylık**|
|Yazılım güncelleştirmeleri|Varies<br /><br />Boyut, dağıttığınız güncelleştirmelere bağlıdır.|**Aylık**<br /><br />Genellikle, yazılım güncelleştirmeleri her ayın ikinci Salı günü yayınlanır.<br /><br />Yeni kaydedilen veya dağıtılan bir bilgisayar, daha önce yayınlanmış güncelleştirmelerinin tamamını indirirken daha fazla ağ bant genişliği kullanabilir.|
|Hizmet paketleri|Değişir<br /><br />Boyut, dağıttığınız her bir hizmet paketi için değişir.|**Değişir**<br /><br />Hizmet paketlerini ne zaman dağıttığınızda bağlıdır.|
|Yazılım dağıtımı|Varies<br /><br />Boyut, dağıttığınız yazılıma bağlıdır.|**Değişir**<br /><br />Yazılımı ne zaman dağıttığınızda bağlıdır.|

## <a name="ways-to-reduce-network-bandwidth-use"></a>Ağ bant genişliği kullanımını azaltmanın yolları
Intune istemcilerinin ağ bant genişliği kullanımını azaltmak için aşağıdaki yöntemlerden birini veya daha fazlasını kullanabilirsiniz.

### <a name="use-a-proxy-server-to-cache-content-requests"></a>İçerik isteklerini önbelleğe almak için proxy sunucusu kullanma
Bir ara sunucu, yinelenen indirmeleri azaltmak ve İnternet’ten alınan içeriğin ağ bant genişliğini düşürmek için içerikleri önbelleğe alabilir.

İstemcilerden içerik istekleri alan bir önbelleğe alma ara sunucusu, bu içeriği alıp web yanıtları ve indirmeleri önbelleğe alabilir. Sunucu, istemcilerden daha sonra gelecek istekleri yanıtlamak için önbelleğe alınmış verileri kullanır.

Intune istemcileri için içerikleri önbelleğe alan bir proxy sunucunun kullandığı genel ayarlar aşağıda verilmiştir.


|          Ayar           |           Önerilen değer           |                                                                                                  Ayrıntılar                                                                                                  |
|----------------------------|---------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|         Önbellek boyutu         |             5 GB ila 30 GB             | Bu değer, ağınızdaki istemci bilgisayarların sayısına ve kullandığınız yapılandırmalara bağlı olarak değişir. Dosyaların çok kısa sürede silinmesini önlemek için ortamınıza yönelik önbellek boyutunu ayarlayın. |
| Tek önbellek dosyası boyutu |                950 MB                 |                                                                     Bu ayar, tüm önbelleğe alan proxy sunucularında kullanılamayabilir.                                                                     |
|   Önbelleğe alınacak nesne türleri    | HTTP<br /><br />HTTPS<br /><br />BİT |                                               Intune paketleri HTTP üzerinden Arka Plan Akıllı Aktarım Hizmeti (BITS) indirmesi tarafından alınan CAB dosyalarıdır.                                               |
> [!NOTE]
> İçerik isteklerini önbelleğe almak için bir ara sunucu kullanıyorsanız, istemci ile ara sunucu arasındaki ve ara sunucudan Intune'a giden trafik şifrelenir. İstemci ile Intune arasındaki bağlantıda uçtan uca şifreleme uygulanmaz.

Önbelleğe içerik almak için proxy sunucu kullanma hakkında bilgi için proxy sunucunuzun çözümünü içeren belgelere bakın.

### <a name="use-background-intelligent-transfer-service-bits-on-computers"></a>Bilgisayarlarda Arka Plan Akıllı Aktarım Hizmeti'ni (BITS) kullanma
Ağ bant genişliğini azaltmak için belirlediğiniz saatlerde Windows yüklü bir bilgisayar üzerinde BITS hizmetini kullanabilirsiniz. BITS ilkesini Intune Aracısı ilkesinin **Ağ bant genişliği** sayfasında yapılandırabilirsiniz.

> [!NOTE]
> Windows üzerinde MDM yönetimi için yalnızca işletim sisteminin MobileMSI uygulama türüne ait yönetim arabirimi indirme işlemler için BITS hizmetini kullanır. AppX/MsiX, kendi BITS olmayan indirme yığınını kullanırken Intune aracısı üzerinden erişilene Win32 uygulamaları da BITS yerine Teslim İyileştirme özelliğinden faydalanır.

BITS ve Windows bilgisayarlar hakkında daha fazla bilgi için TechNet Kitaplığında [Arka Plan Akıllı Aktarım Hizmeti](https://technet.microsoft.com/library/bb968799.aspx) konusuna bakın.

### <a name="delivery-optimization"></a>Teslim Iyileştirme
Teslim Iyileştirme, Windows 10 cihazlarınız uygulamaları ve güncelleştirmeleri indirdiğinizde bant genişliği tüketimini azaltmak için Intune 'U kullanmanızı sağlar. Kendini düzenleme dağıtılan bir önbellek kullanarak, indirme işlemleri geleneksel sunuculardan ve diğer kaynaklardan (ağ eşleri gibi) çekerek yapılabilir.

Teslim Iyileştirme tarafından desteklenen Windows 10 sürümlerinin ve içerik türlerinin tam listesini görmek için, bkz. [Windows 10 Için teslim iyileştirme güncelleştirmeleri makalesi](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization#requirements).

[Teslim iyileştirme](delivery-optimization-settings.md) 'yi cihaz yapılandırma profillerinizin bir parçası olarak ayarlayabilirsiniz.


### <a name="use-branchcache-on-computers"></a>Bilgisayarlarda BranchCache kullanma
Intune istemcileri geniş alan ağı (WAN) trafiğini azaltmak için BranchCache kullanabilir. Aşağıdaki işletim sistemleri BranchCache’i desteklemektedir:

- Windows 7
- Windows 8.0
- Windows 8.1
- Windows 10

BranchCache özelliğini kullanmak için istemci bilgisayarda BranchCache etkin olmalı ve ardından **dağıtılmış önbellek modu** için yapılandırılmalıdır.

Intune istemcisi bilgisayarlara yüklendiğinde BranchCache ve dağıtılmış önbellek modu varsayılan olarak etkindir. Ancak bir Grup İlkesi, BranchCache’i devre dışı bıraktıysa Intune bu ilkeyi geçersiz kılmaz ve BranchCache devre dışı kalmaya devam eder.

BranchCache kullanıyorsanız Grup İlkesini ve Intune Güvenlik Duvarı ilkesini yönetmek için kuruluşunuzdaki diğer yöneticilerle birlikte çalışın. Diğer yöneticilerin, BranchCache veya Güvenlik Duvarı özel durumlarını devre dışı bırakan bir ilke dağıtmadığından emin olun. BranchCache hakkında daha fazla bilgi için bkz. [BranchCache Özelliğine Genel Bakış](https://technet.microsoft.com/library/hh831696.aspx).

> [!NOTE]
> Windows bilgisayarlarını [mobil cihaz yönetimi (MDM) ile mobil cihazlar olarak](windows-enroll.md) veya Intune yazılım istemcisi ile bilgisayar olarak yönetmek için Microsoft Intune kullanabilirsiniz. Microsoft, müşterilerin mümkün olduğunda [MDM yönetim çözümünü kullanmalarını](windows-enroll.md) önerir. Bu şekilde yönetildiğinde BranchCache desteklenmez. Daha fazla bilgi için bkz. [Windows bilgisayarlarını bilgisayar veya mobil cihaz olarak yönetmeyi karşılaştırın](pc-management-comparison.md).


## <a name="next-steps"></a>Sonraki adımlar

[Intune için uç noktaları gözden geçirin](intune-endpoints.md)

