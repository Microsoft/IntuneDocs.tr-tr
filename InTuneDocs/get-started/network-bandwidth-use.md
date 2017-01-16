---
title: "Intune ağ bant genişliğini kullanma | Microsoft Docs"
description: "Intune ağ bant genişliği kullanımı"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0f737d48-24bc-44cd-aadd-f0a1d59f6893
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e13a9c426e07ebb2443bd403d1a5c7274afd387e
ms.openlocfilehash: 213e2e43635dd64cd64c850d74f7fd05f649bd64


---

# <a name="intune-network-bandwidth-use"></a>Intune ağ bant genişliğini kullanma

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune’u ayarlamadan önce bu konuyu ve [Microsoft Intune’u başlatmadan önce bilinmesi gerekenler](what-to-know-before-you-start-microsoft-intune.md) başlığı altında listelenen diğer gereksinimleri gözden geçirin.

Microsoft Intune istemcilerinin ağ trafiğini planlamak için aşağıdaki bölümlerde yer alan bilgileri kullanın.

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

Güvenlik duvarlarının ve proxy sunucuların arkasındaki bilgisayarları yönetmek için güvenlik duvarlarını ve proxy sunucuları Intune iletişimine izin verecek şekilde ayarlamanız gerekir.

### <a name="requirements-for-proxy-servers"></a>Proxy sunucuları için gereksinimler
Bir proxy sunucunun arkasındaki bilgisayarları yönetmek için aşağıdakileri dikkate alın:

-   Intune istemcileri iki protokolü de kullandığından, proxy sunucusu hem **HTTP** hem de **HTTPS**'yi desteklemelidir
-   Intune kimliği doğrulanmamış proxy sunucuları destekler

Tek bir istemci bilgisayarın proxy sunucu ayarlarını değiştirebilir veya Grup İlkesi ayarlarını kullanarak belirtilen proxy sunucunun arkasında bulunan tüm istemci bilgisayarların ayarlarını değiştirebilirsiniz.

### <a name="requirements-for-firewalls-ports-and-domains"></a>Güvenlik duvarları, bağlantı noktaları ve etki alanları ile ilgili gereksinimler
Yönetilen cihazlar, **Tüm Kullanıcıların** güvenlik duvarları üzerinden hizmetlere erişmesine izin veren yapılandırmalar gerektirir.

Aşağıdaki tabloda Intune istemcisinin eriştiği bağlantı noktaları ve hizmetler listelenmektedir.

|**Etki alanı**|**Bağlantı noktaları**|**IP adresi**|
|------|----|---|
|manage.microsoft.com<br>a.manage.microsoft.com<br>admin.manage.microsoft.com<br>enterpriseenrollment.manage.microsoft.com<br>enterpriseenrollment-s.manage.microsoft.com<br>i.manage.microsoft.com<br>p.manage.microsoft.com<br>r.manage.microsoft.com|80 ve 443|134.170.168.254<br>134.170.51.126
|m.manage.microsoft.com|80 ve 443| 13.91.59.243<br>40.68.30.140
|portal.manage.microsoft.com|80 ve 443|40.121.50.69<br>52.169.30.159
|account.manage.microsoft.com|80 ve 443|157.56.13.59
|fef.msua01.manage.microsoft.com|80 ve 443|138.91.243.97
|fef.msua02.manage.microsoft.com|80 ve 443|23.96.112.46
|fef.msua04.manage.microsoft.com|80 ve 443|23.96.112.28
|fef.msua05.manage.microsoft.com|80 ve 443|138.91.244.151
|fef.msub01.manage.microsoft.com|80 ve 443|137.135.128.214
|fef.msub02.manage.microsoft.com|80 ve 443|137.135.130.29
|fef.msub03.manage.microsoft.com|80 ve 443|23.97.165.17
|fef.msub05.manage.microsoft.com|80 ve 443|23.97.166.52
|fef.msuc01.manage.microsoft.com|80 ve 443|207.46.225.1
|fef.msuc02.manage.microsoft.com|80 ve 443|23.98.66.118
|fef.msuc03.manage.microsoft.com|80 ve 443|23.101.0.100
|fef.msuc05.manage.microsoft.com|80 ve 443|207.46.154.33
|fef.msua06.manage.microsoft.com|80 ve 443|104.42.188.1
|fei.msua01.manage.microsoft.com|80 ve 443|138.91.240.131
|fei.msua02.manage.microsoft.com|80 ve 443|23.96.112.143
|fei.msua04.manage.microsoft.com|80 ve 443|23.96.112.147
|fei.msua05.manage.microsoft.com|80 ve 443|138.91.240.163
|fei.msub01.manage.microsoft.com|80 ve 443|137.135.130.85
|fei.msub02.manage.microsoft.com|80 ve 443|137.135.132.149
|fei.msub03.manage.microsoft.com|80 ve 443|23.97.160.232
|fei.msub05.manage.microsoft.com|80 ve 443|23.97.162.250
|fei.msuc01.manage.microsoft.com|80 ve 443|207.46.224.73
|fei.msuc02.manage.microsoft.com|80 ve 443|23.98.66.194
|fei.msuc03.manage.microsoft.com|80 ve 443|23.101.2.105
|fei.msuc05.manage.microsoft.com|80 ve 443|207.46.147.126
|fei.msua06.manage.microsoft.com|80 ve 443|138.91.149.190
|m.fei.msua01.manage.microsoft.com|80 ve 443|138.91.240.131
|m.fei.msua02.manage.microsoft.com|80 ve 443|23.96.112.143
|m.fei.msua04.manage.microsoft.com|80 ve 443|23.96.112.147
|m.fei.msua05.manage.microsoft.com|80 ve 443|138.91.240.163
|m.fei.msub01.manage.microsoft.com|80 ve 443|137.135.130.85
|m.fei.msub02.manage.microsoft.com|80 ve 443|137.135.132.149
|m.fei.msub03.manage.microsoft.com|80 ve 443|23.97.160.232
|m.fei.msub05.manage.microsoft.com|80 ve 443|23.97.162.250
|m.fei.msuc01.manage.microsoft.com|80 ve 443|207.46.224.73
|m.fei.msuc02.manage.microsoft.com|80 ve 443|23.98.66.194
|m.fei.msuc03.manage.microsoft.com|80 ve 443|23.101.2.105
|m.fei.msuc05.manage.microsoft.com|80 ve 443|207.46.147.126
|m.fei.msua06.manage.microsoft.com|80 ve 443|138.91.149.190
|m.msua01.manage.microsoft.com|80 ve 443|157.55.50.182
|m.msua02.manage.microsoft.com|80 ve 443|134.170.49.121
|m.msua04.manage.microsoft.com|80 ve 443|134.170.49.126
|m.msua05.manage.microsoft.com|80 ve 443|157.55.240.190
|m.msua06.manage.microsoft.com|80 ve 443|134.170.49.114
|m.msub01.manage.microsoft.com|80 ve 443|94.245.121.50
|m.msub02.manage.microsoft.com|80 ve 443|94.245.121.58
|m.msub03.manage.microsoft.com|80 ve 443|94.245.121.56
|m.msub05.manage.microsoft.com|80 ve 443|157.56.113.123
|m.msuc01.manage.microsoft.com|80 ve 443|104.44.84.187
|m.msuc02.manage.microsoft.com|80 ve 443|104.44.84.188
|m.msuc03.manage.microsoft.com|80 ve 443|104.44.84.189
|m.msuc05.manage.microsoft.com|80 ve 443|111.221.76.60
|msua01.manage.microsoft.com|80 ve 443|157.55.50.182
|msua02.manage.microsoft.com|80 ve 443|134.170.49.121
|msua04.manage.microsoft.com|80 ve 443|134.170.49.126
|msua05.manage.microsoft.com|80 ve 443|157.55.240.190
|msub01.manage.microsoft.com|80 ve 443|94.245.121.50
|msub02.manage.microsoft.com|80 ve 443|94.245.121.58
|msub03.manage.microsoft.com|80 ve 443|94.245.121.56
|msub05.manage.microsoft.com|80 ve 443|157.56.113.123
|msuc01.manage.microsoft.com|80 ve 443|104.44.84.187
|msuc02.manage.microsoft.com|80 ve 443|104.44.84.188
|msuc03.manage.microsoft.com|80 ve 443|104.44.84.189
|msuc05.manage.microsoft.com|80 ve 443|111.221.76.60
|msua06.manage.microsoft.com|80 ve 443|134.170.49.114
|ncufun.account.manage.microsoft.com|80 ve 443|157.55.252.224
|neufun.account.manage.microsoft.com|80 ve 443|65.52.229.134
|portal.fei.msua01.manage.microsoft.com|80 ve 443|138.91.240.131
|portal.fei.msua02.manage.microsoft.com|80 ve 443|23.96.112.143
|portal.fei.msua04.manage.microsoft.com|80 ve 443|23.96.112.147
|portal.fei.msua05.manage.microsoft.com|80 ve 443|138.91.240.163
|portal.fei.msub01.manage.microsoft.com|80 ve 443|137.135.130.85
|portal.fei.msub02.manage.microsoft.com|80 ve 443|137.135.132.149
|portal.fei.msub03.manage.microsoft.com|80 ve 443|23.97.160.232
|portal.fei.msub05.manage.microsoft.com|80 ve 443|23.97.162.250
|portal.fei.msuc01.manage.microsoft.com|80 ve 443|207.46.224.73
|portal.fei.msuc02.manage.microsoft.com|80 ve 443|23.98.66.194
|portal.fei.msuc03.manage.microsoft.com|80 ve 443|23.101.2.105
|portal.fei.msuc05.manage.microsoft.com|80 ve 443|207.46.147.126
|portal.fei.msua06.manage.microsoft.com|80 ve 443|138.91.149.190
|portal.msua01.manage.microsoft.com|80 ve 443|157.55.50.182
|portal.msua02.manage.microsoft.com|80 ve 443|134.170.49.121
|portal.msua04.manage.microsoft.com|80 ve 443|134.170.49.126
|portal.msua05.manage.microsoft.com|80 ve 443|157.55.240.190
|portal.msub01.manage.microsoft.com|80 ve 443|94.245.121.50
|portal.msub02.manage.microsoft.com|80 ve 443|94.245.121.58
|portal.msub03.manage.microsoft.com|80 ve 443|94.245.121.56
|portal.msub05.manage.microsoft.com|80 ve 443|157.56.113.123
|portal.msuc01.manage.microsoft.com|80 ve 443|104.44.84.187
|portal.msuc02.manage.microsoft.com|80 ve 443|104.44.84.188
|portal.msuc03.manage.microsoft.com|80 ve 443|104.44.84.189
|portal.msuc05.manage.microsoft.com|80 ve 443|111.221.76.60
|portal.msua06.manage.microsoft.com|80 ve 443|134.170.49.114
|ssu2.manage.microsoft.com|80 ve 443|157.55.99.181
|status.manage.microsoft.com|80 ve 443|157.55.99.170
|swda01.manage.microsoft.com<br>swda02.manage.microsoft.com<br>swdb01.manage.microsoft.com<br>swdb02.manage.microsoft.com<br>swdc01.manage.microsoft.com<br>swdc02.manage.microsoft.com|80 ve 443|93.184.215.200
|*.microsoftonline-p.com|80 ve 443||
|has.spserv.microsoft.com<br>Cihaz sistem durumu kanıtlama hizmeti için gerekli|443||
|*.microsoftonline-p.net|80 ve 443||
|*.portal.office.com|80 ve 443||
|*.spynet2.microsoft.com|443||
|c.microsoft.com|80 ve 443||
|c1.microsoft.com|80 ve 443||
|blob.core.windows.net|80 ve 443||
|ajax.aspnetcdn.com|80 ve 443||
|*.googleapis.com<br>Bu etki alanı, şirket portalı web sitesini kullandığınızda JQuery desteği için gereklidir.|80 ve 443||
|wustat.microsoft.com|80 ve 443||
|Microsoft Update Services|\*.update.microsoft.com<br>download.microsoft.com<br>update.microsoft.com<br>\*.download.windowsupdate.com<br>download.windowsupdate.com<br>\*.windowsupdate.com<br>windowsupdate.microsoft.com<br>ntservicepack.microsoft.com|80 ve 443|
|DNS arama istekleri|manage.microsoft.com.nsatc.net|80|
|Güvenlik duvarı aracılığıyla Samsung KNOX Standard cihaz iletişimi|Samsung KNOX Standard cihazlarının güvenlik duvarı aracılığıyla KNOX Standard sunucuları ile iletişim kurmasını sağlamak için Samsung KNOX Standard SSS bölümündeki yönergeleri izleyin.||
|Koşullu erişim iletişimi|443|204.79.197.200|
|Belgeler, Yardım ve destek:</br></br>*.livemeeting.com<br>\*.microsoftonline.com<br>\*.social.technet.microsoft.com<br>blogs.technet.com<br>go.microsoft.com<br>onlinehelp.microsoft.com<br>www.microsoft.com|80|||

>[!div class="step-by-step"]

>[&larr; **Önkoşullar**](what-to-know-before-you-start-microsoft-intune.md)     [**Abonelik** &rarr;](start-with-a-paid-subscription-to-microsoft-intune-step-1.md)  



<!--HONumber=Dec16_HO3-->


