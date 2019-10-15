---
title: Windows bilgisayarlar için güvenlik duvarı ilkeleri
titleSuffix: Microsoft Intune
description: Intune, Intune istemcisiyle yönettiğiniz bilgisayarları, Windows Güvenlik Duvarı ayarlarını yapılandırmanıza yardımcı olmak gibi çeşitli yollarla güvenli hale getirmenize yardımcı olabilir.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/01/2018
ms.topic: archived
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 9549c072-ac3d-4d14-a931-a2eda8846217
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic-keep
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8e5a67ade5f1b3c9efc2674887a042bd828136fa
ms.sourcegitcommit: a2654f3642b43b29ab0e1cbb2dfa2b56aae18d0e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/14/2019
ms.locfileid: "72310739"
---
# <a name="help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune"></a>Microsoft Intune Windows Güvenlik Duvarı ilkelerini kullanarak Windows bilgisayarlarının korunmasına yardımcı olma

[!INCLUDE [classic-portal](../../intune-classic/includes/classic-portal.md)]

> [!NOTE]
> Bu konudaki bilgiler yalnızca, Intune yazılım istemcisini kullanarak bilgisayar olarak yönettiğiniz Windows masaüstü bilgisayarlar için geçerlidir. Mobil cihaz olarak kaydedilen Windows bilgisayarlarının güvenlik duvarı ayarlarını yönetmek istiyorsanız, bkz. [Intune 'da Endpoint Protection ayarları ekleme](../protect/endpoint-protection-configure.md).

Microsoft Intune, Intune istemcisiyle yönettiğiniz Windows bilgisayarlarını çeşitli yollarla güvenli hale getirmenize yardımcı olabilir. Bunu yapmanın bir yolu, bilgisayarlarda Windows Güvenlik Duvarı ayarlarını yapılandırmanıza olanak tanıyan ilkeler sağlamaktır.

Intune Windows BILGISAYARı istemcisini bilgisayarlarınıza henüz yüklemediyseniz, bkz. [Microsoft Intune WINDOWS bilgisayarı Istemcisini yükleme](install-the-windows-pc-client-with-microsoft-intune.md).

Windows bilgisayarlarda Windows Güvenlik Duvarı ilkelerini yapılandırmanıza, dağıtmanıza ve izlemenize yardımcı olması için aşağıdaki bölümlerde yer alan bilgileri kullanın.

## <a name="use-intune-policies-to-manage-windows-firewall"></a>Windows güvenlik duvarını yönetmek için Intune ilkelerini kullanma
Windows güvenlik duvarı ilkesi, yönetilen bilgisayarlarda Windows Güvenlik Duvarı 'nı denetleyen ayarları oluşturmanıza ve dağıtmanıza olanak tanır. Windows Güvenlik Duvarı için özel özel durumları yönetemezsiniz ve bu ayarlar üçüncü taraf güvenlik duvarlarını etkilemez.

> [!NOTE]
> Microsoft Intune ilke ve grup ilkesi bılgısayarda aynı ayarı yönetecek şekilde yapılandırıldıysa grup ilkesi ayarı Microsoft Intune ilkesini geçersiz kılar. Intune ilkesi ve grup ilkesi arasındaki çakışmaların önlenmesi hakkında daha fazla bilgi için bkz. [GPO ve Microsoft Intune ilkesi çakışmalarını çözümleme](resolve-gpo-and-microsoft-intune-policy-conflicts.md).
>
> Windows Vista çalıştıran bilgisayarlara Windows Güvenlik Duvarı ayarlarını dağıtmak istiyorsanız, önce bu bilgisayarlara [Düzeltme KB971800](https://support2.microsoft.com/kb/971800) yüklemeniz gerekir.

> [!IMPORTANT]
> Windows Güvenlik Duvarı 'nı Intune kullanarak yönetmek için, yönettiğiniz bilgisayarlarda aşağıdaki iki hizmetin etkinleştirildiğinden emin olun:
>
> - Windows Güvenlik Duvarı
> - IPSec Ilke Aracısı

## <a name="configure-a-windows-firewall-policy"></a>Windows güvenlik duvarı ilkesi yapılandırma

1. [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com/) **ilke** &gt; **ilke Ekle**' yi seçin.

2. Bir **Windows Güvenlik Duvarı ayarları** ilkesi yapılandırın ve dağıtın. Önerilen ayarları kullanabilir veya ayarları özelleştirebilirsiniz. İlke oluşturma ve dağıtma hakkında daha fazla bilgiye ihtiyacınız varsa, bkz. [Microsoft Intune bilgisayar Istemcisiyle ortak WINDOWS bilgisayarı yönetim görevleri](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md).

    Aşağıdaki bölümde, ilkede yapılandırabileceğiniz değerlerin yanı sıra, ilkeyi özelleştirmezseniz kullanılacak varsayılan değerler listelenmektedir.

Bir Windows güvenlik duvarı ilkesi dağıttıktan sonra, **ilke** çalışma alanının **Tüm ilkeler** sayfasında durumunu görüntüleyebilirsiniz.

## <a name="specify-policy-settings-for-windows-firewall"></a>Windows Güvenlik Duvarı için ilke ayarlarını belirtin

### <a name="turn-on-windows-firewall"></a>Windows güvenlik duvarını Aç

Bu ilke ayarları, yönetilen bilgisayarlarda Windows Güvenlik Duvarı 'nı etkinleştirir:
- Bir etki alanına bağlı (örneğin, çalışma alanında)
- Özel (güvenilen) ağa (ev ağı gibi) bağlı
- Güvenilmeyen bir ortak ağa (örneğin, kafeterya) bağlı

Bu ayarların her biri için varsayılan değer **Evet**' tir ve en güvenli değerdir.



### <a name="block-all-incoming-connections-including-those-in-the-list-of-allowed-programs"></a>İzin verilen programlar listesindekiler dahil tüm gelen bağlantıları engelle

Bu ilke ayarları, Windows Güvenlik Duvarı 'nı yönetilen bilgisayarlarda gelen ağ trafiğini engelleyecek şekilde yapılandırır:
- Bir etki alanına bağlı (örneğin, çalışma alanında)
- Özel (güvenilen) ağa (ev ağı gibi) bağlı
- Güvenilmeyen bir ortak ağa (örneğin, kafeterya) bağlı

Bu ayarların her biri için varsayılan değer **Evet**' tir ve en güvenli değerdir.

> [!IMPORTANT]
> Ortamınız, hizmet paketi yüklü olmayan Windows Vista çalıştıran yönetilen bilgisayarları içeriyorsa, Microsoft Bilgi Bankası 'nda [makale 971800](https://go.microsoft.com/fwlink/?LinkId=188405) ile ilişkili güncelleştirmeyi yüklemeli veya **tüm gelen engelle 'yi devre dışı bırakmanız gerekir** bu bilgisayarlara dağıtılan ilkelerdeki bağlantı ilkesi ayarları.

### <a name="notify-the-user-when-windows-firewall-blocks-a-new-program"></a>Windows Güvenlik Duvarı yeni bir programı engellediğinde kullanıcıya bildir

Bu ilke ayarları, Windows Güvenlik Duvarı 'nın, yönetilen bilgisayar şu olduğunda gelen ağ trafiğini engellediğinde bir BILGISAYAR kullanıcısına bildirimde bulunduğunu belirtir:
- Bir etki alanına bağlı (örneğin, çalışma alanında)
- Özel (güvenilen) ağa (ev ağı gibi) bağlı
- Güvenilmeyen bir ortak ağa (örneğin, kafeterya) bağlı

Bu ayarların her biri için varsayılan değer **Evet**' tir.


### <a name="configure-predefined-exceptions"></a>Önceden tanımlanmış özel durumları yapılandırma

Daha önce yapılandırdığınız değerlere bakılmaksızın güvenlik duvarından belirli ağ trafiği türlerine izin veren özel durumlar yapılandırabilirsiniz. Bu ayarlardan hiçbiri varsayılan olarak yapılandırılmaz.

|Ayar adı|Ayrıntılar|
|------------------|--------------------|
|**BranchCache-Içerik alma**<br>(Windows 7 veya üzeri)|BranchCache istemcilerinin dağıtılmış moddayken diğer BranchCache istemcilerinden ve barındırılan önbellek modundayken barındırılan önbellekten içerik almak için HTTP kullanmasına izin verir. Bu ayar HTTP kullanır.|
|**BranchCache-barındırılan önbellek Istemcisi**<br>(Windows 7 veya üzeri)|BranchCache istemcilerinin barındırılan bir önbellek kullanmasına izin verir. Bu ayar HTTPS kullanır.|
|**BranchCache-barındırılan önbellek sunucusu**|BranchCache istemcilerinin diğer istemcilerle iletişim kurmak için barındırılan bir önbellek kullanmasına izin verir. Bu ayar HTTPS kullanır.|
|**BranchCache-eş bulma**<br>(Windows 7 veya üzeri)|BranchCache istemcilerinin yerel alt ağdaki içerik kullanılabilirliğini aramak için Web Hizmetleri dinamik bulma (WS-bulma) protokolünü kullanmasına izin verir.|
|**BITS Eş önbelleğe alma**|İstemcilerin aynı alt ağdaki istemcilerde BITS önbelleğinde depolanan dosyaları bulmak ve paylaşmak için Arka Plan Akıllı Aktarım Hizmeti (BITS) kullanmasına izin verir. Bu ayar cihazlarda Web Hizmetleri (WSDAPı) ve uzak yordam çağrısı (RPC) kullanır.|
|**Bir ağ projektörüne bağlanma**|Kullanıcıların proje sunumlarına kablolu veya kablosuz ağlar üzerinden projektörlere bağlanmasına izin verir. Bu ayar WSDAPı kullanır.|
|**Çekirdek ağ**|İstemcilerin ağ kaynaklarına bağlanmak için IPv4 ve IPv6 kullanmasına izin verir.|
|**Dağıtılmış İşlem Düzenleyicisi**|Yönetilen bilgisayarların veritabanları, ileti kuyrukları ve dosya sistemleri gibi işlem korumalı kaynakları güncelleştiren işlemleri koordine etmesini sağlar.|
|**Dosya ve yazıcı paylaşımı**|Kullanıcıların ağ üzerindeki diğer kullanıcılarla yerel dosya ve yazıcı paylaşmasına olanak sağlar. Bu ayar NetBIOS, bağlantı yerel çok noktaya yayın adı çözümleme (LLMNR), sunucu Ileti bloğu (SMB) protokolü ve RPC kullanır.|
|**Paylaştır**<br>(Windows 7 veya üzeri)|Yönetilen bilgisayarların bir ev grubu ağına katılmasını sağlar.|
|**Iscsı hizmeti**|Yönetilen bilgisayarların Iscsı sunucularına ve cihazlarına bağlanmasına olanak sağlar.|
|**Anahtar Yönetim hizmeti**|Kurumsal ortamlarda bilgisayarların lisans uyumluluğu için sayılmasına izin verir.|
|**Media Center Extender 'Lar**|Media Center Extender 'larının Windows Media Center çalıştıran bilgisayarlarla iletişim kurmasını sağlar. Bu ayar basit hizmet bulma Protokolü (SSDP) ve qWave kullanır.|
|**Netlogon hizmeti**|Kullanıcı ve hizmetlerin kimliğini doğrulamak için etki alanı istemcileri ve etki alanı denetleyicisi arasında bir güvenlik kanalı yapılandırır. Bu ayar RPC kullanır.|
|**Ağ bulma**|Bilgisayarların ağdaki diğer cihazları bulmasına ve ağ üzerindeki diğer cihazlar tarafından keşfedilmesine olanak sağlar. Bu ayar, Işlev bulma konak ve yayınlama Hizmetleri ve SSDP, NetBIOS, LLMNR ve UPnP ağ protokollerini kullanır.|
|**Performans Günlükleri ve Uyarıları**|Performans Günlükleri ve Uyarıları hizmetinin uzaktan yönetilmesini sağlar. Bu ayar RPC kullanır.|
|**Uzaktan Yönetim**|Bilgisayarın uzaktan yönetimine izin vermez.|
|**Uzaktan Yardım**|Yönetilen bilgisayarların kullanıcılarının ağ üzerindeki diğer kullanıcılardan uzaktan yardım istemesine izin verir. Bu ayar SSDP, eş adı çözümleme Protokolü (PNRP), Teredo ve UPnP ağ protokollerini kullanır.|
|**Uzak Masaüstü**|Bilgisayarın uzak masaüstü 'Nü kullanarak diğer bilgisayarlara erişmesine izin verir.|
|**Uzak olay günlüğü yönetimi**|İstemci olay günlüklerinin uzaktan görüntülenmesine ve yönetilmesine izin verir. Bu ayar adlandırılmış kanallar ve RPC kullanır.|
|**Uzaktan Zamanlanmış görev yönetimi**|Görev zamanlama hizmetinin uzaktan yönetilmesine izin vermez. Bu ayar RPC kullanır.|
|**Uzak hizmet yönetimi**|İstemcilerdeki yerel hizmetlerin uzaktan yönetilmesine izin vermez. Bu ayar adlandırılmış kanallar ve RPC kullanır.|
|**Uzaktan Birim Yönetimi**|Uzak yazılım ve donanım disk birimi yönetimini sunar. Bu ayar RPC kullanır.|
|**Yönlendirme ve uzaktan erişim**|Bilgisayarlara gelen VPN ve uzaktan erişim bağlantılarını sağlar.|
|**Güvenli Yuva Tünel Protokolü**|Güvenli Yuva Tünel Protokolü (SSTP) ile yönetilen bilgisayarlara gelen VPN bağlantılarını sağlar. Bu ayar HTTPS kullanır.|
|**SNMP tuzağı**|Yönetilen bilgisayarların basit ağ Yönetim Protokolü (SNMP) tuzak hizmeti trafiği almasına izin verir.|
|**UPnP çerçevesi**|Bilgisayarların UPnP sertifikalı cihazları bulmasına ve kullanmasına izin vermek için, bilgisayarlardaki UPnP çerçevesi hizmetini yapılandırır.|
|**Windows Işbirliği bilgisayar adı kayıt hizmeti**|Bilgisayarların SSDP ve PNRP kullanarak diğer bilgisayarları bulmasını ve bunlarla iletişim kurmasını sağlar.|
|**Windows Media Player**|Kullanıcıların, Kullanıcı Datagram Protokolü (UDP) üzerinden akış medyası almasına olanak sağlar.|
|**Windows Media Player ağ paylaşım hizmeti**|Kullanıcıların bir ağ üzerinden medya paylaşmasına olanak sağlar. Bu ayar SSDP, qWave ve UPnP ağ protokollerini kullanır.|
|**Windows Media Player Ağ Paylaşım Hizmeti (Internet)**<br>(Windows 7 veya üzeri)|Kullanıcıların Internet üzerinden Ev medyası paylaşmasına izin verir.|
|**Windows Toplantı Alanı**|Kullanıcıların belge, program ve masaüstlerini paylaşmak için bir ağ üzerinden işbirliği yapmasına olanak sağlar. Bu ayar Dağıtılmış Dosya Sistemi Çoğaltma (DFSR) ve P2P kullanır.|
|**Windows Eşler arası Işbirliği altyapısı**|, Bağlantı kurmasını sağlamak için çeşitli eşler arası programlar ve teknolojiler yapılandırır. Bu ayar SSDP ve PNRP kullanır.|
|**Windows Uzaktan Yönetimi (uyumluluk)**|, İşletim sistemleri ve cihazların uzaktan yönetimi için Web hizmeti tabanlı bir protokol olan WS-Management ile yönetilen bilgisayarların uzaktan yönetilmesine izin verir.|
|**Windows Uzaktan Yönetimi**<br>(Windows 8 veya üzeri)|, İşletim sistemleri ve cihazların uzaktan yönetimi için Web hizmeti tabanlı bir protokol olan WS-Management ile yönetilen bilgisayarların uzaktan yönetilmesine izin verir.|
|**Windows Sanal BILGISAYAR**<br>(Windows 7 veya üzeri)|Sanal makinelerin diğer bilgisayarlarla iletişim kurmasına izin verir.|
|**Kablosuz Taşınabilir cihazlar**|Medya Aktarım Protokolü (MTP) ile yönetilen bilgisayarlara ağ özellikli bir kamera veya medya aygıtından medya aktarımını sağlar. Bu ayar SSDP ve UPnP ağ protokollerini kullanır.|

## <a name="see-also"></a>Ayrıca bkz.
[Windows bilgisayarlarını korumaya yönelik ilkeler](policies-to-protect-windows-pcs-in-microsoft-intune.md)
