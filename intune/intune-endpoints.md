---
title: Microsoft Intune için ağ uç noktaları
titleSuffix: ''
description: Intune için uç noktaları inceleyin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/30/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: e52b0718cd1977a2eb96b0bfbe1949cabbd3f180
ms.sourcegitcommit: df413d1786c9aa0f409424c1e9e102bf230bbe39
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/05/2019
ms.locfileid: "66721706"
---
# <a name="network-endpoints-for-microsoft-intune"></a>Microsoft Intune için ağ uç noktaları

IP adresleri ve Intune dağıtımlarınızı proxy ayarları için gereken bağlantı noktası ayarları bu sayfada listelenir.

Yalnızca bulutta yer alan bir hizmet olan Intune, sunucular veya ağ geçitleri gibi şirket içi altyapıya ihtiyaç duymaz.

Güvenlik duvarı ve ara sunucular arkasındaki cihazları yönetmek için Intune iletişimini etkinleştirmeniz gerekir.

- Intune istemcileri iki protokolü de kullandığından, proxy sunucusu hem **HTTP (80)** hem de **HTTPS (443)** desteklemelidir
- Intune bazı görevler (yazılım güncelleştirmelerini indirme gibi) için manage.microsoft.com adresine kimliği doğrulanmamış ara sunucu erişimine ihtiyaç duyar.

Ara sunucu ayarlarını istemci bilgisayarlardan değiştirebilirsiniz. Belirtilen ara sunucu arkasında yer alan tüm istemci bilgisayarların ayarlarını değiştirmek için Grup İlkesi ayarlarını da kullanabilirsiniz.


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
|fei.msua01.manage.microsoft.com<br>portal.fei.msua01.manage.microsoft.com <br>m.fei.msua01.manage.microsoft.com<br>fei.msua02.manage.microsoft.com<br>portal.fei.msua02.manage.microsoft.com<br>m.fei.msua02.manage.microsoft.com<br>fei.msua04.manage.microsoft.com<br>portal.fei.msua04.manage.microsoft.com <br>m.fei.msua04.manage.microsoft.com<br>fei.msua05.manage.microsoft.com <br>portal.fei.msua05.manage.microsoft.com <br>m.fei.msua05.manage.microsoft.com<br>fei.amsua0502.manage.microsoft.com <br>portal.fei.amsua0502.manage.microsoft.com <br>m.fei.amsua0502.manage.microsoft.com<br>fei.msua06.manage.microsoft.com <br>portal.fei.msua06.manage.microsoft.com <br>m.fei.msua06.manage.microsoft.com<br>fei.amsua0602.manage.microsoft.com <br>portal.fei.amsua0602.manage.microsoft.com <br>m.fei.amsua0602.manage.microsoft.com<br>fei.amsua0202.manage.microsoft.com <br>portal.fei.amsua0202.manage.microsoft.com <br>m.fei.amsua0202.manage.microsoft.com<br>fei.amsua0402.manage.microsoft.com <br>portal.fei.amsua0402.manage.microsoft.com <br>m.fei.amsua0402.manage.microsoft.com|52.160.70.20<br>52.168.54.64 |
|fei.msub01.manage.microsoft.com <br>portal.fei.msub01.manage.microsoft.com <br>m.fei.msub01.manage.microsoft.com<br>fei.amsub0102.manage.microsoft.com <br>portal.fei.amsub0102.manage.microsoft.com <br>m.fei.amsub0102.manage.microsoft.com<br>fei.msub02.manage.microsoft.com <br>portal.fei.msub02.manage.microsoft.com <br>m.fei.msub02.manage.microsoft.com<br>fei.msub03.manage.microsoft.com <br>portal.fei.msub03.manage.microsoft.com <br>m.fei.msub03.manage.microsoft.com<br>fei.msub05.manage.microsoft.com <br>portal.fei.msub05.manage.microsoft.com <br>m.fei.msub05.manage.microsoft.com<br>fei.amsub0202.manage.microsoft.com <br>portal.fei.amsub0202.manage.microsoft.com <br>m.fei.amsub0202.manage.microsoft.com<br>fei.amsub0302.manage.microsoft.com <br>portal.fei.amsub0302.manage.microsoft.com <br>m.fei.amsub0302.manage.microsoft.com|52.138.193.149<br>51.144.161.187|
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
|fef.amsua0202.manage.microsoft.com|52.165.165.17|
|fef.amsua0402.manage.microsoft.com|40.69.157.122|
|fef.amsua0502.manage.microsoft.com|13.85.68.142|
|fef.amsua0602.manage.microsoft.com|52.161.28.64|
|fef.amsub0102.manage.microsoft.com|40.118.98.207|
|fef.amsub0202.manage.microsoft.com|40.69.208.122|
|fef.amsub0302.manage.microsoft.com|13.74.145.65|
|enterpriseregistration.windows.net|52.175.211.189|
|Admin.manage.microsoft.com|52.224.221.227<br>52.161.162.117<br>52.178.44.195<br>52.138.206.56<br>52.230.21.208<br>13.75.125.10|
|wip.mam.manage.microsoft.com|52.187.76.84<br>13.76.5.121<br>52.165.160.237<br>40.86.82.163<br>52.233.168.142<br>168.63.101.57|
|mam.manage.microsoft.com|104.40.69.125<br>13.90.192.78<br>40.85.174.177<br>40.85.77.31<br>137.116.229.43<br>52.163.215.232<br>52.174.102.180|


### <a name="network-requirements-for-powershell-scripts-and-win32-apps"></a>Powershell betikleri ve Win32 uygulamaları için ağ gereksinimleri
Powershell betikleri veya Win32 uygulamalarını dağıtmak için Intune kullanıyorsanız, kiracınızın şu anda bulunduğu uç noktalarına erişimi vermeniz gerekir.

|ASU | Depolama adı | CDN |
| --- | --- |--- |
| AMSUA0601 | prodmsua06data | https://prodmsua06data.azureedge.net |
| AMSUA0602 | prodamsua0602data | https://prodamsua0602data.azureedge.net |
| AMSUA0101 | prodmsua01data | https://prodmsua01data.azureedge.net |
| AMSUA0201 | prodmsua02data | https://prodmsua02data.azureedge.net |
| AMSUA0202 | Prodmsua0202rcdata | https://prodamsua0202data.azureedge.net/ |
| AMSUA0401 | prodmsua04data | https://prodmsua04data.azureedge.net |
| AMSUA0402 | Prodmsua0402rcdata | https://prodamsua0402data.azureedge.net/ |
| AMSUA0501 | prodmsua05data | https://prodmsua05data.azureedge.net |
| AMSUA0502 | prodmsua0502data | https://prodmsua0502data.azureedge.net |
| AMSUB0101 | prodmsub01data | https://prodmsub01data.azureedge.net |
| AMSUB0102 | prodamsub0102data | https://prodamsub0102data.azureedge.net |
| AMSUB0201 | prodmsub02data | https://prodmsub02data.azureedge.net |
| AMSUB0202 | Prodmsub0202rcdata | https://prodamsub0202data.azureedge.net |
| AMSUB0301 | Prodmsub03data2 | https://prodmsub03data2.azureedge.net |
| AMSUB0302 | Prodmsub0302rcdata | https://prodamsub0302data.azureedge.net |
| AMSUB0501 | prodmsub05data | https://prodmsub05data.azureedge.net |
| AMSUC0101 | prodmsuc01data | https://prodmsuc01data.azureedge.net |
| AMSUC0201 | prodmsuc02data | https://prodmsuc02data.azureedge.net |
| AMSUC0301 | prodmsuc03data | https://prodmsuc03data.azureedge.net |
| AMSUC0501 | prodmsuc05data | https://prodmsuc05data.azureedge.net |
| AMSUA0701 | pemsua07rcdata | https://pemsua07data.azureedge.net |

### <a name="delivery-optimization-port-requirements"></a>Teslim iyileştirme bağlantı noktası gereksinimleri

#### <a name="port-requirements"></a>Bağlantı noktası gereksinimleri
Eşler arası trafiği için TCP/IP'yi veya NAT geçişi (isteğe bağlı olarak, Teredo) için 3544 7680 teslim iyileştirme kullanır. İstemci hizmet iletişim için HTTP veya HTTPS bağlantı noktası üzerinden kullanır 80/443'tür.

#### <a name="proxy-requirements"></a>Ara sunucu gereksinimleri
Teslim iyileştirme'yi kullanmak için bayt aralığı isteklerini izin vermeniz gerekir. Daha fazla bilgi için [Proxy gereksinimleri için Windows Update](https://docs.microsoft.com/windows/deployment/update/windows-update-troubleshooting).

#### <a name="firewall-requirements"></a>Güvenlik duvarı gereksinimleri
Teslim iyileştirme desteklemek için güvenlik duvarı üzerinden aşağıdaki ana bilgisayar adlarını sağlar.
İstemcileri ve teslim iyileştirme bulut hizmeti arasında iletişim için:
- *.do.dsp.mp.microsoft.com

Teslim iyileştirme meta verileri için:
- *.dl.delivery.mp.microsoft.com
- *.emdl.ws.microsoft.com

### <a name="apple-device-network-information"></a>Apple cihaz ağ bilgileri


|İçin kullanılan|Ana bilgisayar adı (IP adresi/alt ağ)|Protocol|Port|
|-----|--------|------|-------|
|Apple Anında İletilen Bildirim Servisi (APNS) ile Intune hizmetinden anında iletme bildirimi alma. Apple tarafından sağlanan belgeler için [buraya](https://support.apple.com/en-us/HT203609) bakın.|                                    gateway.push.apple.com (17.0.0.0/8)                                  |    TCP     |     2195     |
|Apple Anında İletilen Bildirim Servisi (APNS) ile Intune hizmetine geri bildirim gönderme.|                                  feedback.push.apple.com(17.0.0.0/8)                                  |    TCP     |     2196     |
|Apple sunucularından içerik alma ve görüntüleme|itunes.apple.com<br>\*.itunes.apple.com<br>\*.mzstatic.com<br>\*.phobos.apple.com<br> \*.phobos.itunes-apple.com.akadns.net |    HTTP    |      80      |
|APNS sunucularıyla iletişim|#-courier.push.apple.com (17.0.0.0/8)<br>"#", 0 ile 50 arasında rastgele bir sayıdır.|    TCP     |  5223 ve 443  |
|World Wide Web erişim dahil olmak üzere çeşitli işlevlere iTunes depolayın, macOS uygulama mağazası, iCloud, Mesajlaşma, vs. |phobos.apple.com<br>ocsp.apple.com<br>ax.itunes.apple.com<br>ax.itunes.apple.com.edgesuite.net| HTTP/HTTPS |  80 veya 443   |

Daha fazla bilgi için şu Apple belgelerine bakın: [Apple yazılım ürünleri tarafından kullanılan TCP ve UDP bağlantı noktaları](https://support.apple.com/en-us/HT202944), [macOS, iOS ve iTunes sunucusu ana bilgisayar bağlantıları ve iTunes arka plan işlemleri hakkında](https://support.apple.com/en-us/HT201999) ve [macOS ve iOS istemcileriniz Apple anında iletme bildirimlerini almıyorsa](https://support.apple.com/en-us/HT203609).
