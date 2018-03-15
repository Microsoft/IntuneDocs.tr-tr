---
title: "Microsoft Intune için ağ gereksinimleri ve bant genişliği ayrıntıları"
titlesuffix: 
description: "Intune için ağ yapılandırma gereksinimlerini ve bant genişliği ayrıntılarını gözden geçirin."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/24/2018
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0f737d48-24bc-44cd-aadd-f0a1d59f6893
ms.reviewer: angerobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b21c4421914294e84bae637e489065c5e4410839
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2018
---
# <a name="intune-network-configuration-requirements-and-bandwidth"></a>Intune ağ yapılandırma gereksinimleri ve bant genişliği

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

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
Intune istemcileri geniş alan ağı (WAN) trafiğini azaltmak için BranchCache kullanabilir. Aşağıdaki işletim sistemleri BranchCache’i desteklemektedir:

- Windows 7
- Windows 8.0
- Windows 8.1
- Windows 10

BranchCache özelliğini kullanmak için istemci bilgisayarda BranchCache etkin olmalı ve ardından **dağıtılmış önbellek modu** için yapılandırılmalıdır.

BranchCache ve dağıtılmış önbellek modu, Intune istemcisi yüklendiğinde bilgisayarlarda varsayılan olarak etkindir. Ancak bir Grup İlkesi, BranchCache’i devre dışı bıraktıysa Intune bu ilkeyi geçersiz kılmaz ve BranchCache devre dışı kalmaya devam eder.

BranchCache kullanıyorsanız Grup İlkesini ve Intune Güvenlik Duvarı ilkesini yönetmek için kuruluşunuzdaki diğer yöneticilerle birlikte çalışın. Diğer yöneticilerin, BranchCache veya Güvenlik Duvarı özel durumlarını devre dışı bırakan bir ilke dağıtmadığından emin olun. BranchCache hakkında daha fazla bilgi için bkz. [BranchCache Özelliğine Genel Bakış](http://technet.microsoft.com/library/hh831696.aspx).

## <a name="network-communication-requirements"></a>Ağ iletişimi gereksinimleri

Yönettiğiniz cihazlar ve bulut tabanlı hizmetler için gerekli olan web siteleri arasında ağ iletişimlerini etkinleştirin.

Intune, Intune yazılımını çalıştıran sunucular gibi şirket içi altyapı kullanmaz ancak Exchange ve Active Directory eşitleme araçları da dahil olmak üzere şirket içi altyapı kullanma seçenekleri mevcuttur.

Güvenlik duvarı ve ara sunucular arkasındaki bilgisayarları yönetmek için Intune iletişimini etkinleştirmeniz gerekir.

-   Intune istemcileri iki protokolü de kullandığından, proxy sunucusu hem **HTTP (80)** hem de **HTTPS (443)** desteklemelidir
-   Intune’un yazılım ve güncelleştirmeleri indirme gibi bazı görevler için manage.microsoft.com adresine kimliği doğrulanmamış ara sunucu erişimi olması gerekir

Tek bir istemci bilgisayarın proxy sunucu ayarlarını değiştirebilir veya Grup İlkesi ayarlarını kullanarak belirtilen proxy sunucunun arkasında bulunan tüm istemci bilgisayarların ayarlarını değiştirebilirsiniz.


<!--
> [!NOTE] If Windows 8.1 devices haven't cached proxy server credentials, enrollment might fail because the request doesn't prompt for credentials. Enrollment fails without warning as the request wait for a connection. If users might experience this issue, instruct them to open their browser settings and save proxy server settings to enable a connection.   -->

Yönetilen cihazlar, **Tüm Kullanıcıların** güvenlik duvarları üzerinden hizmetlere erişmesine izin veren yapılandırmalar gerektirir.

Aşağıdaki tabloda Intune istemcisinin eriştiği bağlantı noktaları ve hizmetler listelenir:

|**Etki alanları**|**IP adresi**|
|---------------------|-----------|
|login.microsoftonline.com | Daha fazla bilgi için [Office 365 URL’leri ve IP adres aralıkları](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) |
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
|fef.msua01.manage.microsoft.com|138.91.243.97|
|fef.msua02.manage.microsoft.com|52.177.194.236|
|fef.msua04.manage.microsoft.com|23.96.112.28|
|fef.msua05.manage.microsoft.com|138.91.244.151|
|fef.msua06.manage.microsoft.com|13.78.185.97|
|fef.msua07.manage.microsoft.com|52.175.208.218|
|fef.msub01.manage.microsoft.com|137.135.128.214|
|fef.msub02.manage.microsoft.com|137.135.130.29|
|fef.msub03.manage.microsoft.com|23.97.165.17|
|fef.msub05.manage.microsoft.com|23.97.166.52|
|fef.msuc01.manage.microsoft.com|52.230.19.86|
|fef.msuc02.manage.microsoft.com|23.98.66.118|
|fef.msuc03.manage.microsoft.com|23.101.0.100|
|fef.msuc05.manage.microsoft.com|52.230.16.180|

### <a name="apple-device-network-information"></a>Apple cihaz ağ bilgileri
| Ana Bilgisayar Adı  | URL (IP adresi/alt ağ) | Protokol | Bağlantı Noktası | Cihaz |
| --- | --- | --- | --- | --- |
|  Yönetim Konsolu  | gateway.push.apple.com (17.0.0.0/8) | TCP | 2195 | Apple iOS ve macOS |
| Yönetim Konsolu  | feedback.push.apple.com(17.0.0.0/8) | TCP | 2196 | Apple iOS ve macOS |
| Yönetim Konsolu  | Apple iTunesitunes.apple.com, \*.mzstatic.com, \*.phobos.apple.com, \*.phobos.apple.com.edgesuite.net | HTTP | 80 | Apple iOS ve macOS  |
| PI Sunucusu  | gateway.push.apple.com(17.0.0.0/8) feedback.push.apple.com(17.0.0.0/8) | TCP | 2195, 2196 | Apple iOS ve macOS bulut mesajlaşma için. |
| Cihaz Hizmetleri  | gateway.push.apple.com | TCP | 2195 | Apple  |
| Cihaz Hizmetleri  | feedback.push.apple.com | TCP | 2196 | Apple  |
| Cihaz Hizmetleri  | Apple iTunesitunes.apple.com \*.mzstatic.com\*.phobos.apple.com \*.phobos.apple.com.edgesuite.net | HTTP | 80 | Apple  |
| Cihazlar (Internet/Wi-Fi) | #-courier.push.apple.com(17.0.0.0/8) | TCP | 5223 ve 443 | Yalnızca Apple. &#39;#&#39; 0 ile 200 arasında rastgele bir sayıdır. |
| Cihazlar (Internet/Wi-Fi) | phobos.apple.comocsp.apple.comax.itunes.apple.com | HTTP/HTTPS | 80 veya 443 | Yalnızca Apple |
