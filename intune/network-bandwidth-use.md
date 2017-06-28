---
title: "Intune ağ bant genişliğini kullanma"
description: "Intune ağ bant genişliği kullanımı"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/07/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0f737d48-24bc-44cd-aadd-f0a1d59f6893
ms.reviewer: angerobe
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: 030aa380a1491eb3be4fd8f480b0ddc9a7860448
ms.contentlocale: tr-tr
ms.lasthandoff: 06/08/2017


---

# <a name="intune-network-bandwidth-use"></a>Intune ağ bant genişliğini kullanma

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Bu kılavuz Intune yöneticilerinin Intune hizmeti için ağ gereksinimlerini anlamasına yardımcı olur. Buradaki bilgileri bant genişliği gereksinimlerini ve proxy ayarları için gereken IP adresi ve bağlantı noktası ayarlarını anlamak için kullanabilirsiniz.

## <a name="average-network-traffic"></a>Ortalama ağ trafiği
Bu tabloda her istemci için ağ üzerinden geçen ortak içeriğin yaklaşık boyutu ve sıklığı listelenmiştir.

> [!NOTE]
> Bilgisayarların ve mobil cihazların gerekli güncelleştirmeleri ve içerikleri Intune hizmetinden almasını sağlamak için bunların İnternet'e düzenli aralıklarla bağlanması gerekir. Güncelleştirmeleri veya içeriği almak için geçen süre farklılık gösterir, ancak her gün en az 1 saat boyunca kesintisiz olarak İnternet'e bağlı kalmaları gerekir.

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
Yinelenen indirmeleri ve İnternet'ten içerik isteyen istemcilerin ağ bant genişliği kullanımını azaltmak için içeriği önbelleğe alan bir proxy sunucu kullanabilirsiniz.

Önbelleğe alan proxy sunucusu, ağınızdaki istemci bilgisayarlardan içerik ister, İnternet'ten içerik alır ve ardından her iki HTTP yanıtını ve ikili indirmelerini önbelleğe alabilir. Sunucu, Intune istemci bilgisayarlarından gelen sonraki istekleri yanıtlamak için önbelleğe alınan bilgileri kullanır.

Intune istemcileri için içerikleri önbelleğe alan bir proxy sunucunun kullandığı genel ayarlar aşağıda verilmiştir.

|Ayar|Önerilen değer|Ayrıntılar|
|-----------|---------------------|-----------|
|Önbellek boyutu|5 GB ila 30 GB|Bu değer, ağınızdaki istemci bilgisayarların sayısına ve kullandığınız yapılandırmalara bağlı olarak değişir. Dosyaların çok kısa sürede silinmesini önlemek için ortamınıza yönelik önbellek boyutunu ayarlayın.|
|Tek önbellek dosyası boyutu|950 MB|Bu ayar, tüm önbelleğe alan proxy sunucularında kullanılamayabilir.|
|Önbelleğe alınacak nesne türleri|HTTP<br /><br />HTTPS<br /><br />BİT|Intune paketleri HTTP üzerinden Arka Plan Akıllı Aktarım Hizmeti (BITS) indirmesi tarafından alınan CAB dosyalarıdır.|
Önbelleğe içerik almak için proxy sunucu kullanma hakkında bilgi için proxy sunucunuzun çözümünü içeren belgelere bakın.

### <a name="use-background-intelligent-transfer-service-on-computers"></a>Bilgisayarlarda Arka Plan Akıllı Aktarım Hizmeti'ni kullanma
Intune, yapılandırma yaptığınız saatlerde kullanılan ağ bant genişliğini azaltmak üzere bir Windows bilgisayarda Arka Plan Akıllı Aktarım Hizmeti'nin (BITS) kullanılmasını destekler. BITS ilkesini Intune Aracısı ilkesinin **Ağ bant genişliği** sayfasında yapılandırabilirsiniz.

BITS ve Windows bilgisayarlar hakkında daha fazla bilgi için TechNet Kitaplığında [Arka Plan Akıllı Aktarım Hizmeti](http://technet.microsoft.com/library/bb968799.aspx) konusuna bakın.

### <a name="use-branchcache-on-computers"></a>Bilgisayarlarda BranchCache kullanma
Intune istemcileri geniş alan ağı (WAN) trafiğini azaltmak için BranchCache kullanabilir. İstemci olarak desteklenen aşağıdaki işletim sistemleri de BranchCache özelliğini destekler:

- Windows 7
- Windows 8.0
- Windows 8.1
- Windows 10

BranchCache özelliğini kullanmak için istemci bilgisayarda BranchCache etkin olmalı ve ardından **dağıtılmış önbellek modu** için yapılandırılmalıdır.

BranchCache ve dağıtılmış önbellek modu, Intune istemcisi yüklü olduğunda bilgisayarda varsayılan olarak etkinleştirilir. Ancak, istemci BranchCache özelliğini devre dışı bırakan Grup İlkesine zaten sahipse, Intune bu ilkeyi geçersiz kılmaz ve BranchCache söz konusu bilgisayarda devre dışı kalır.

BranchCache kullanıyorsanız, BranchCache özelliğini veya Güvenlik Duvarı özel durumlarını devre dışı bırakan ilkeyi dağıtmadıklarından emin olmak üzere kuruluşunuzda Grup İlkesini ve Intune Güvenlik Duvarı ilkesini yöneten diğer yöneticilerle iletişim kurmanız gerekir. BranchCache hakkında daha fazla bilgi için bkz. [BranchCache Özelliğine Genel Bakış](http://technet.microsoft.com/library/hh831696.aspx).

## <a name="network-communication-requirements"></a>Ağ iletişimi gereksinimleri

Yönettiğiniz ve Intune aboneliğiniz yönetmek için kullandığınız cihazlarla bulut tabanlı hizmetler için gerekli olan web siteleri arasında ağ iletişimi kurmanız gerekir.

Intune, Intune yazılımını çalıştıran sunucular gibi şirket içi altyapı kullanmaz ancak Exchange ve Active Directory eşitleme araçları da dahil olmak üzere şirket içi altyapı kullanma seçenekleri mevcuttur.

Güvenlik duvarlarının ve proxy sunucuların arkasındaki bilgisayarları yönetmek için güvenlik duvarlarını ve proxy sunucuları Intune iletişimine izin verecek şekilde ayarlamanız gerekir. Bir proxy sunucunun arkasındaki bilgisayarları yönetmek için aşağıdakileri dikkate alın:

-   Intune istemcileri iki protokolü de kullandığından, proxy sunucusu hem **HTTP (80)** hem de **HTTPS (443)** desteklemelidir
-   Intune kimliği doğrulanmamış proxy sunucuları destekler

Tek bir istemci bilgisayarın proxy sunucu ayarlarını değiştirebilir veya Grup İlkesi ayarlarını kullanarak belirtilen proxy sunucunun arkasında bulunan tüm istemci bilgisayarların ayarlarını değiştirebilirsiniz.

Yönetilen cihazlar, **Tüm Kullanıcıların** güvenlik duvarları üzerinden hizmetlere erişmesine izin veren yapılandırmalar gerektirir.

Aşağıdaki tabloda Intune istemcisinin eriştiği bağlantı noktaları ve hizmetler listelenir:

|**Etki alanları**|**IP adresi**|
|---------------------|-----------|
|portal.manage.microsoft.com<br> m.manage.microsoft.com |40.86.181.86<br>13.82.59.78<br>13.74.184.100<br>40.68.188.2<br>13.75.42.6<br>52.230.25.184 |
| sts.manage.microsoft.com | 13.93.223.241 <br>52.170.32.182 <br>52.164.224.159 <br>52.174.178.4 <br>13.75.122.143 <br>52.163.120.84|
|Manage.microsoft.com <br>i.manage.microsoft.com <br>r.manage.microsoft.com <br>a.manage.microsoft.com <br>p.manage.microsoft.com <br>EnterpriseEnrollment.manage.microsoft.com <br>EnterpriseEnrollment-s.manage.microsoft.com | 104.40.82.191 <br>13.82.96.212 <br>52.169.9.87 <br>52.174.26.23 <br>40.83.123.72 <br>13.76.177.110 |
|portal.fei.msua01.manage.microsoft.com<br>m.fei.msua01.manage.microsoft.com |13.64.196.170|
|fei.msua01.manage.microsoft.com<br> portal.fei.msua01.manage.microsoft.com <br>m.fei.msua01.manage.microsoft.com |40.71.34.120 |
|fei.msua02.manage.microsoft.com<br>portal.fei.msua02.manage.microsoft.com<br>m.fei.msua02.manage.microsoft.com |13.64.198.190|
|fei.msua02.manage.microsoft.com<br>portal.fei.msua02.manage.microsoft.com<br> m.fei.msua02.manage.microsoft.com |  13.64.198.190|
|fei.msua04.manage.microsoft.com<br> portal.fei.msua04.manage.microsoft.com <br>m.fei.msua04.manage.microsoft.com |13.64.188.173|
|fei.msua04.manage.microsoft.com<br> portal.fei.msua04.manage.microsoft.com <br>m.fei.msua04.manage.microsoft.com |40.71.32.174|
|fei.msua05.manage.microsoft.com <br>portal.fei.msua05.manage.microsoft.com <br>m.fei.msua05.manage.microsoft.com |13.64.197.181 |
|fei.msua05.manage.microsoft.com <br>portal.fei.msua05.manage.microsoft.com <br>m.fei.msua05.manage.microsoft.com |40.71.38.205|
|fei.amsua0502.manage.microsoft.com <br>portal.fei.amsua0502.manage.microsoft.com <br>m.fei.amsua0502.manage.microsoft.com |13.64.191.182 |
|fei.amsua0502.manage.microsoft.com <br>portal.fei.amsua0502.manage.microsoft.com <br>m.fei.amsua0502.manage.microsoft.com |40.71.37.51 |
|fei.msua06.manage.microsoft.com <br>portal.fei.msua06.manage.microsoft.com <br>m.fei.msua06.manage.microsoft.com |40.118.250.246 |
|fei.msua06.manage.microsoft.com <br>portal.fei.msua06.manage.microsoft.com <br>m.fei.msua06.manage.microsoft.com |13.90.142.194 |
|fei.amsua0602.manage.microsoft.com <br>portal.fei.amsua0602.manage.microsoft.com <br>m.fei.amsua0602.manage.microsoft.com |13.64.250.226 |
|fei.amsua0602.manage.microsoft.com <br>portal.fei.amsua0602.manage.microsoft.com <br>m.fei.amsua0602.manage.microsoft.com |13.90.151.142 |
|fei.msub01.manage.microsoft.com <br>portal.fei.msub01.manage.microsoft.com <br>m.fei.msub01.manage.microsoft.com |52.169.155.165 |
|fei.msub01.manage.microsoft.com <br>portal.fei.msub01.manage.microsoft.com <br>m.fei.msub01.manage.microsoft.com |52.174.188.97 |
|fei.amsub0102.manage.microsoft.com <br>portal.fei.amsub0102.manage.microsoft.com <br>m.fei.amsub0102.manage.microsoft.com |52.178.190.24 |
|fei.amsub0102.manage.microsoft.com <br>portal.fei.amsub0102.manage.microsoft.com <br>m.fei.amsub0102.manage.microsoft.com |52.174.16.215 |
|fei.msub02.manage.microsoft.com <br>portal.fei.msub02.manage.microsoft.com <br>m.fei.msub02.manage.microsoft.com |40.69.69.27 |
|fei.msub02.manage.microsoft.com <br>portal.fei.msub02.manage.microsoft.com <br>m.fei.msub02.manage.microsoft.com |52.166.196.199 |
|fei.msub03.manage.microsoft.com <br>portal.fei.msub03.manage.microsoft.com <br>m.fei.msub03.manage.microsoft.com |40.69.71.164 |
|fei.msub03.manage.microsoft.com <br>portal.fei.msub03.manage.microsoft.com <br>m.fei.msub03.manage.microsoft.com |52.174.182.102 |
|fei.msub05.manage.microsoft.com <br>portal.fei.msub05.manage.microsoft.com <br>m.fei.msub05.manage.microsoft.com |40.69.78.145 |
|fei.msub05.manage.microsoft.com <br>portal.fei.msub05.manage.microsoft.com <br>m.fei.msub05.manage.microsoft.com |52.174.192.105 |
|fei.msuc01.manage.microsoft.com <br>portal.fei.msuc01.manage.microsoft.com <br>m.fei.msuc01.manage.microsoft.com |13.94.46.250|
|fei.msuc01.manage.microsoft.com <br>portal.fei.msuc01.manage.microsoft.com <br>m.fei.msuc01.manage.microsoft.com |52.163.119.15 |
|fei.msuc02.manage.microsoft.com <br>portal.fei.msuc02.manage.microsoft.com <br>m.fei.msuc02.manage.microsoft.com |13.75.124.145 |
|fei.msuc02.manage.microsoft.com <br>portal.fei.msuc02.manage.microsoft.com <br>m.fei.msuc02.manage.microsoft.com |52.163.119.5|
|fei.msuc03.manage.microsoft.com <br>portal.fei.msuc03.manage.microsoft.com <br>m.fei.msuc03.manage.microsoft.com |52.175.35.226|
|fei.msuc03.manage.microsoft.com <br>portal.fei.msuc03.manage.microsoft.com <br>m.fei.msuc03.manage.microsoft.com |52.163.119.6|
|fei.msuc05.manage.microsoft.com <br>portal.fei.msuc05.manage.microsoft.com <br>m.fei.msuc05.manage.microsoft.com |52.175.38.24|
|fei.msuc05.manage.microsoft.com <br>portal.fei.msuc05.manage.microsoft.com <br>m.fei.msuc05.manage.microsoft.com |52.163.119.3|

