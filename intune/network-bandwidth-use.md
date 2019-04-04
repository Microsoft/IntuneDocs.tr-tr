---
title: Microsoft Intune için ağ gereksinimleri ve bant genişliği ayrıntıları
titleSuffix: ''
description: Intune için ağ yapılandırma gereksinimlerini ve bant genişliği ayrıntılarını gözden geçirin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/03/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 0f737d48-24bc-44cd-aadd-f0a1d59f6893
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 189e1fdebeb3856c3e65d51d509b190a63d8372b
ms.sourcegitcommit: 219bbbfb44eba70ac2b751970d8b4b778cd28416
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/04/2019
ms.locfileid: "58920263"
---
# <a name="intune-network-configuration-requirements-and-bandwidth"></a>Intune ağ yapılandırma gereksinimleri ve bant genişliği

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

Bu kılavuz Intune yöneticilerinin Intune hizmeti için ağ gereksinimlerini anlamasına yardımcı olur. Buradaki bilgileri bant genişliği gereksinimlerini ve proxy ayarları için gereken IP adresi ve bağlantı noktası ayarlarını anlamak için kullanabilirsiniz.

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
|Endpoint Protection kötü amaçlı yazılım tanımı güncelleştirmeleri|Değişir<br /><br />Genellikle 40 KB ile 2 MB arasında|**Günlük**<br /><br />Günde en fazla üç kez.|
|Endpoint Protection altyapı güncelleştirmesi|5 MB|**Aylık**|
|Yazılım güncelleştirmeleri|Değişir<br /><br />Boyut, dağıttığınız güncelleştirmelere bağlıdır.|**Aylık**<br /><br />Genellikle, yazılım güncelleştirmeleri her ayın ikinci Salı günü yayınlanır.<br /><br />Yeni kaydedilen veya dağıtılan bir bilgisayar, daha önce yayınlanmış güncelleştirmelerinin tamamını indirirken daha fazla ağ bant genişliği kullanabilir.|
|Hizmet paketleri|Değişir<br /><br />Boyut, dağıttığınız her bir hizmet paketi için değişir.|**Değişir**<br /><br />Hizmet paketlerini ne zaman dağıttığınızda bağlıdır.|
|Yazılım dağıtımı|Değişir<br /><br />Boyut, dağıttığınız yazılıma bağlıdır.|**Değişir**<br /><br />Yazılımı ne zaman dağıttığınızda bağlıdır.|

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

Önbelleğe içerik almak için proxy sunucu kullanma hakkında bilgi için proxy sunucunuzun çözümünü içeren belgelere bakın.

### <a name="use-background-intelligent-transfer-service-bits-on-computers"></a>Bilgisayarlarda arka plan Akıllı Aktarım Hizmeti (BITS) kullanın
Yapılandırdığınız saatleri sırasında ağ bant genişliğini azaltmak üzere bir Windows bilgisayarda BITS kullanabilirsiniz. BITS ilkesini yapılandırabilirsiniz **ağ bant genişliği** Intune Aracısı ilkesinin sayfası.

BITS ve Windows bilgisayarlar hakkında daha fazla bilgi için TechNet Kitaplığında [Arka Plan Akıllı Aktarım Hizmeti](http://technet.microsoft.com/library/bb968799.aspx) konusuna bakın.

### <a name="use-branchcache-on-computers"></a>Bilgisayarlarda BranchCache kullanma
Intune istemcileri geniş alan ağı (WAN) trafiğini azaltmak için BranchCache kullanabilir. Aşağıdaki işletim sistemleri BranchCache’i desteklemektedir:

- Windows 7
- Windows 8.0
- Windows 8.1
- Windows 10

BranchCache özelliğini kullanmak için istemci bilgisayarda BranchCache etkin olmalı ve ardından **dağıtılmış önbellek modu** için yapılandırılmalıdır.

BranchCache ve dağıtılmış Önbellek modu, Intune istemcisini bilgisayarlara yüklendiğinde varsayılan olarak etkindir. Ancak, Grup İlkesi, BranchCache'i devre dışı ise Intune Bu ilkeyi geçersiz kılmaz ve BranchCache devre dışı kalır.

BranchCache kullanıyorsanız Grup İlkesini ve Intune Güvenlik Duvarı ilkesini yönetmek için kuruluşunuzdaki diğer yöneticilerle birlikte çalışın. BranchCache özelliğini veya güvenlik duvarı özel durumlarını devre dışı bırakan ilkeyi dağıtmanıza gerek yoktur emin olun. BranchCache hakkında daha fazla bilgi için bkz. [BranchCache Özelliğine Genel Bakış](http://technet.microsoft.com/library/hh831696.aspx).

## <a name="network-communication-requirements"></a>Ağ iletişimi gereksinimleri

Yönettiğiniz cihazlar ve bulut tabanlı hizmetler için gerekli uç noktaları arasında ağ iletişimlerini etkinleştirin.

Yalnızca bulutta yer alan hizmet olarak, Intune şirket içi altyapı sunucuları veya ağ geçitleri gibi gerektirmez.

Güvenlik duvarları ve proxy sunucuların arkasındaki cihazları yönetmek için Intune iletişimini etkinleştirmeniz gerekir.

- Intune istemcileri iki protokolü de kullandığından, proxy sunucusu hem **HTTP (80)** hem de **HTTPS (443)** desteklemelidir
- (Yazılım güncelleştirmeleri yükleme gibi) bazı görevler için Intune için Manage.microsoft.com adresine kimliği doğrulanmamış proxy sunucusu erişimi gerektirir.

Tek bir istemci bilgisayarın proxy sunucu ayarlarını değiştirebilirsiniz. Ayrıca, belirtilen proxy sunucusunun arkasında yer alan tüm istemci bilgisayarlar için ayarları değiştirmek için Grup İlkesi ayarlarını kullanabilirsiniz.


<!--
> [!NOTE] If Windows 8.1 devices haven't cached proxy server credentials, enrollment might fail because the request doesn't prompt for credentials. Enrollment fails without warning as the request wait for a connection. If users might experience this issue, instruct them to open their browser settings and save proxy server settings to enable a connection.   -->

Yönetilen cihazlar, **Tüm Kullanıcıların** güvenlik duvarları üzerinden hizmetlere erişmesine izin veren yapılandırmalar gerektirir.

Aşağıdaki tabloda Intune istemcisinin eriştiği bağlantı noktaları ve hizmetler listelenir:

|**Etki alanları**|**IP adresi**|
|---------------------|-----------|
|login.microsoftonline.com | Daha fazla bilgi için [Office 365 URL’leri ve IP adres aralıkları](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) |
|portal.manage.microsoft.com<br> m.manage.microsoft.com |52.175.12.209<br>20.188.107.228<br>52.138.193.149<br>51.144.161.187<br>52.160.70.20<br>52.168.54.64 |
| sts.manage.microsoft.com | 13.93.223.241 <br>52.170.32.182 <br>52.164.224.159 <br>52.174.178.4 <br>13.75.122.143 <br>52.163.120.84|
|Manage.microsoft.com <br>i.manage.microsoft.com <br>r.manage.microsoft.com <br>a.manage.microsoft.com <br>p.manage.microsoft.com <br>EnterpriseEnrollment.manage.microsoft.com <br>EnterpriseEnrollment-s.manage.microsoft.com | 40.83.123.72<br>13.76.177.110<br>52.169.9.87<br>52.174.26.23<br>104.40.82.191<br>13.82.96.212|
|fei.msua01.manage.microsoft.com<br>portal.fei.msua01.manage.microsoft.com <br>m.fei.msua01.manage.microsoft.com<br>fei.msua02.manage.microsoft.com<br>portal.fei.msua02.manage.microsoft.com<br>m.fei.msua02.manage.microsoft.com<br>fei.msua04.manage.microsoft.com<br>portal.fei.msua04.manage.microsoft.com <br>m.fei.msua04.manage.microsoft.com<br>fei.msua05.manage.microsoft.com <br>portal.fei.msua05.manage.microsoft.com <br>m.fei.msua05.manage.microsoft.com<br>fei.amsua0502.manage.microsoft.com <br>portal.fei.amsua0502.manage.microsoft.com <br>m.fei.amsua0502.manage.microsoft.com<br>fei.msua06.manage.microsoft.com <br>portal.fei.msua06.manage.microsoft.com <br>m.fei.msua06.manage.microsoft.com<br>fei.amsua0602.manage.microsoft.com <br>portal.fei.amsua0602.manage.microsoft.com <br>m.fei.amsua0602.manage.microsoft.com<br>fei.amsua0202.Manage.microsoft.com <br>portal.fei.amsua0202.manage.microsoft.com <br>m.fei.amsua0202.manage.microsoft.com<br>fei.amsua0402.Manage.microsoft.com <br>portal.fei.amsua0402.manage.microsoft.com <br>m.fei.amsua0402.manage.microsoft.com|52.160.70.20<br>52.168.54.64 |
|fei.msub01.manage.microsoft.com <br>portal.fei.msub01.manage.microsoft.com <br>m.fei.msub01.manage.microsoft.com<br>fei.amsub0102.manage.microsoft.com <br>portal.fei.amsub0102.manage.microsoft.com <br>m.fei.amsub0102.manage.microsoft.com<br>fei.msub02.manage.microsoft.com <br>portal.fei.msub02.manage.microsoft.com <br>m.fei.msub02.manage.microsoft.com<br>fei.msub03.manage.microsoft.com <br>portal.fei.msub03.manage.microsoft.com <br>m.fei.msub03.manage.microsoft.com<br>fei.msub05.manage.microsoft.com <br>portal.fei.msub05.manage.microsoft.com <br>m.fei.msub05.manage.microsoft.com<br>fei.amsub0202.Manage.microsoft.com <br>portal.fei.amsub0202.manage.microsoft.com <br>m.fei.amsub0202.manage.microsoft.com<br>fei.amsub0302.Manage.microsoft.com <br>portal.fei.amsub0302.manage.microsoft.com <br>m.fei.amsub0302.manage.microsoft.com|52.138.193.149<br>51.144.161.187|
|fei.msuc01.manage.microsoft.com <br>portal.fei.msuc01.manage.microsoft.com <br>m.fei.msuc01.manage.microsoft.com<br>fei.msuc02.manage.microsoft.com <br>portal.fei.msuc02.manage.microsoft.com <br>m.fei.msuc02.manage.microsoft.com<br>fei.msuc03.manage.microsoft.com <br>portal.fei.msuc03.manage.microsoft.com <br>m.fei.msuc03.manage.microsoft.com<br>fei.msuc05.manage.microsoft.com <br>portal.fei.msuc05.manage.microsoft.com <br>m.fei.msuc05.manage.microsoft.com|52.175.12.209<br>20.188.107.228|
|fef.msua01.manage.microsoft.com|138.91.243.97|
|fef.msua02.manage.microsoft.com|52.177.194.236|
|fef.msua04.manage.microsoft.com|23.96.112.28|
|fef.msua05.manage.microsoft.com|138.91.244.151|
|fef.msua06.manage.microsoft.com|13.78.185.97|
|fef.msua07.manage.microsoft.com|52.175.208.218|
|fef.msub01.manage.microsoft.com|137.135.128.214|
|fef.msub02.manage.microsoft.com|137.135.130.29|
|fef.msub03.manage.microsoft.com|52.169.82.238|
|fef.msub05.manage.microsoft.com|23.97.166.52|
|fef.msuc01.manage.microsoft.com|52.230.19.86|
|fef.msuc02.manage.microsoft.com|23.98.66.118|
|fef.msuc03.manage.microsoft.com|23.101.0.100|
|fef.msuc05.manage.microsoft.com|52.230.16.180|
|fef.amsua0202.Manage.microsoft.com|52.165.165.17|
|fef.amsua0402.Manage.microsoft.com|40.69.157.122|
|fef.amsua0502.Manage.microsoft.com|13.85.68.142|
|fef.amsua0602.Manage.microsoft.com|52.161.28.64|
|fef.amsub0102.Manage.microsoft.com|40.118.98.207|
|fef.amsub0202.Manage.microsoft.com|40.69.208.122|
|fef.amsub0302.Manage.microsoft.com|13.74.145.65|
|enterpriseregistration.windows.net|52.175.211.189|
|Admin.Manage.microsoft.com|52.224.221.227<br>52.161.162.117<br>52.178.44.195<br>52.138.206.56<br>52.230.21.208<br>13.75.125.10|
|wip.mam.manage.microsoft.com|52.187.76.84<br>13.76.5.121<br>52.165.160.237<br>40.86.82.163<br>52.233.168.142<br>168.63.101.57|
|mam.manage.microsoft.com|104.40.69.125<br>13.90.192.78<br>40.85.174.177<br>40.85.77.31<br>137.116.229.43<br>52.163.215.232<br>52.174.102.180|






### <a name="apple-device-network-information"></a>Apple cihaz ağ bilgileri

|         Ana bilgisayar adı         |                                        URL (IP adresi/alt ağ)                                        |  Protokol  |     Bağlantı Noktası     |                          Cihaz                           |
|--------------------------|-------------------------------------------------------------------------------------------------------|------------|--------------|-----------------------------------------------------------|
|      Yönetici Konsolu       |                                  gateway.push.apple.com (17.0.0.0/8)                                  |    TCP     |     2195     |                    Apple iOS ve macOS                    |
|      Yönetici Konsolu       |                                  feedback.push.apple.com(17.0.0.0/8)                                  |    TCP     |     2196     |                    Apple iOS ve macOS                    |
|      Yönetici Konsolu       | Apple iTunesitunes.apple.com, \*.mzstatic.com, \*.phobos.apple.com, \*.phobos.apple.com.edgesuite.net |    HTTP    |      80      |                    Apple iOS ve macOS                    |
|        PI Sunucusu         |                gateway.push.apple.com(17.0.0.0/8) feedback.push.apple.com(17.0.0.0/8)                 |    TCP     |  2195, 2196  |         Apple iOS ve macOS bulut mesajlaşma için.          |
|     Cihaz Hizmetleri      |                                        gateway.push.apple.com                                         |    TCP     |     2195     |                           Apple                           |
|     Cihaz Hizmetleri      |                                        feedback.push.apple.com                                        |    TCP     |     2196     |                           Apple                           |
|     Cihaz Hizmetleri      |   Apple iTunesitunes.apple.com \*.mzstatic.com\*.phobos.apple.com \*.phobos.apple.com.edgesuite.net   |    HTTP    |      80      |                           Apple                           |
| Cihazlar (Internet/Wi-Fi) |                                 #-courier.push.apple.com(17.0.0.0/8)                                  |    TCP     | 5223 ve 443 | Yalnızca Apple. &#39;#&#39; 0 ile 200 arasında rastgele bir sayıdır. |
| Cihazlar (Internet/Wi-Fi) |                           phobos.apple.comocsp.apple.comax.itunes.apple.com                           | HTTP/HTTPS |  80 veya 443   |                        Yalnızca Apple                         |

