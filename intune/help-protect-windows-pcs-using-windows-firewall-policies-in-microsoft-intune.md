---
title: Windows bilgisayarlar için güvenlik duvarı ilkeleri
titleSuffix: Microsoft Intune
description: Intune, Intune istemcisiyle yönettiğiniz bilgisayarları, Windows Güvenlik Duvarı ayarlarını yapılandırmanıza yardımcı olmak dahil olmak üzere, çeşitli yollarla güvenli hale getirmenize yardımcı olabilir.
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
ms.openlocfilehash: eade2a1bc19e4b0c477faf2ad8e262196da8cc30
ms.sourcegitcommit: ede86a3cb094c12e3e218b956abb9935bec76902
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/05/2019
ms.locfileid: "67572528"
---
# <a name="help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune"></a>Microsoft Intune’da Windows Güvenlik Duvarı ilkelerini kullanarak Windows bilgisayarlarının korunmasına yardımcı olma

[!INCLUDE [classic-portal](includes/classic-portal.md)]

> [!NOTE]
> Bu konudaki bilgiler, yalnızca Intune yazılım istemcisini kullanarak bilgisayar olarak yönettiğiniz Windows masaüstü cihazlar için geçerlidir. Bkz yönetmek istiyorsanız Windows bilgisayarlar için Güvenlik Duvarı ayarlarını mobil cihaz olarak kaydedilen [Intune'da endpoint protection ayarları ekleme](endpoint-protection-configure.md).

Microsoft Intune, Intune istemcisiyle yönettiğiniz Windows bilgisayarları çeşitli yollarla güvenli hale getirmenize yardımcı olabilir. Bu yollardan biri, bilgisayarlarda Windows Güvenlik Duvarı ayarlarını yapılandırmanıza olanak tanıyan ilkeler sağlamaktır.

Intune Windows bilgisayarlar istemcisini henüz bilgisayarlarınıza yüklemediyseniz, bkz. [Microsoft Intune ile Windows bilgisayar istemcisini yükleme](install-the-windows-pc-client-with-microsoft-intune.md).

Windows bilgisayarlarda Windows Güvenlik Duvarı ilkelerini yapılandırmanıza, dağıtmanıza ve izlemenize yardımcı olması için, aşağıdaki bölümlerde yer alan bilgileri kullanın.

## <a name="use-intune-policies-to-manage-windows-firewall"></a>Windows Güvenlik Duvarı'nı yönetmek için Intune ilkelerini kullanma
Windows Güvenlik Duvarı ilkesi, yönetilen bilgisayarlarda Windows Güvenlik Duvarı'nı denetleyen ayarlar oluşturmanıza ve dağıtmanıza olanak tanır. Windows Güvenlik Duvarı için özel durumları yönetemezsiniz ve bu ayarlar üçüncü taraf güvenlik duvarlarını etkilemez.

> [!NOTE]
> Microsoft Intune ilkesi ve Grup İlkesi, bilgisayarda aynı ayarı yönetecek biçimde yapılandırıldıysa, Grup İlkesi ayarı Microsoft Intune ilkesini geçersiz kılar. Intune ilkeleri ve Grup İlkesi arasındaki çakışmaları önleme hakkında daha fazla bilgi içi, bkz. [GPO ve Microsoft Intune ilke çakışmalarını çözümleme](resolve-gpo-and-microsoft-intune-policy-conflicts.md).
>
> Windows Vista çalıştıran bilgisayarlara Windows Güvenlik Duvarı ayarlarını dağıtmak istiyorsanız, önce bu bilgisayarlarda [KB971800 Düzeltmesi](http://support2.microsoft.com/kb/971800)'ni yüklemeniz gerekir.

> [!IMPORTANT]
> Windows Güvenlik Duvarı'nı Intune ile yönetmek için, yönettiğiniz bilgisayarlarda aşağıdaki iki hizmetin etkin olduğundan emin olun:
>
> - Windows Güvenlik Duvarı
> - IPsec İlke Aracısı

## <a name="configure-a-windows-firewall-policy"></a>Bir Windows Güvenlik Duvarı ilkesini yapılandırma

1. [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com/), **İlke** &gt; **İlke Ekle**’yi seçin.

2. Bir **Windows Güvenlik Duvarı Ayarları** ilkesi yapılandırın ve dağıtın. Önerilen ayarları kullanabilir veya ayarları özelleştirebilirsiniz. İlke oluşturma ve dağıtma hakkında daha fazla bilgi için, bkz. [Microsoft Intune bilgisayar istemcisi ile genel Windows bilgisayarı yönetim görevleri](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md).

    Aşağıdaki bölümde, ilkede yapılandırabileceğiniz değerlerin yanı sıra ilkeyi özelleştirmediğinizde kullanılacak varsayılan değerler listelenmektedir.

Bir Windows Güvenlik Duvarı ilkesi dağıttıktan sonra, bunun durumunu **İlke** çalışma alanının **Tüm İlkeler** sayfasında görüntüleyebilirsiniz.

## <a name="specify-policy-settings-for-windows-firewall"></a>Windows Güvenlik Duvarı için ilke ayarları belirtme

### <a name="turn-on-windows-firewall"></a>Windows Güvenlik Duvarını Açma

Bu ilke ayarları, aşağıdaki durumlardan birinde olan yönetilen bilgisayarlarda Windows Güvenlik Duvarı’nı etkinleştirir:
- Bir etki alanına bağlı (örneğin, iş yerindeki etki alanına)
- Özel (güvenilen) bir ağa bağlı (bir ev ağı gibi)
- Güvenilir olmayan bir ortak ağa bağlı (bir kafe gibi)

Bu ayarların her biri için varsayılan değer **Evet**’tir, bu en güvenli değerdir



### <a name="block-all-incoming-connections-including-those-in-the-list-of-allowed-programs"></a>İzin verilen programlar listesindekiler dahil tüm gelen bağlantıları engelleme

Bu ilke ayarları, aşağıdaki durumlardan birinde olan yönetilen bilgisayarlarda Windows Güvenlik Duvarı’nı gelen ağ trafiğini engelleyecek biçimde yapılandırır:
- Bir etki alanına bağlı (örneğin, iş yerindeki etki alanına)
- Özel (güvenilen) bir ağa bağlı (bir ev ağı gibi)
- Güvenilir olmayan bir ortak ağa bağlı (bir kafe gibi)

Bu ayarların her biri için varsayılan değer **Evet**’tir, bu en güvenli değerdir

> [!IMPORTANT]
> Ortamınızda hizmet paketi yüklü olmayan Windows Vista çalıştıran yönetilen bilgisayarlar varsa, Microsoft Bilgi Bankası'nda [971800 numaralı makale](http://go.microsoft.com/fwlink/?LinkId=188405) ile ilişkili güncelleştirmeyi yüklemeniz ya da bu bilgisayarlara dağıtılan ilkelerdeki **Tüm gelen bağlantıları engelle** ilke ayarlarını devre dışı bırakmanız gerekir.

### <a name="notify-the-user-when-windows-firewall-blocks-a-new-program"></a>Windows Güvenlik Duvarı yeni bir programı engellediğinde kullanıcıya bildirme

Bu ilke ayarları, yönetilen bilgisayar aşağıdaki durumlardan birindeyken Windows Güvenlik Duvarı’nın gelen ağ trafiğini engellediğinde kullanıcıyı uyarıp uyarmayacağını belirler:
- Bir etki alanına bağlı (örneğin, iş yerindeki etki alanına)
- Özel (güvenilen) bir ağa bağlı (bir ev ağı gibi)
- Güvenilir olmayan bir ortak ağa bağlı (bir kafe gibi)

Bu ayarların her biri için varsayılan değer **Evet**’tir.


### <a name="configure-predefined-exceptions"></a>Önceden tanımlanmış özel durumlar yapılandırma

Daha önce yapılandırılmış değerlerden bağımsız olarak belirli türlerdeki ağ trafiğinin güvenlik duvarından geçmesine izin veren özel durumlar yapılandırabilirsiniz. Bu ayarların hiçbiri varsayılan olarak yapılandırılmaz.

|Ayar adı|Ayrıntılar|
|------------------|--------------------|
|**BranchCache - İçerik Alma**<br>(Windows 7 veya üzeri)|BranchCache istemcilerinin dağıtılmış moddayken diğer BranchCache istemcilerinden ve barındırılan önbellek modundayken barındırılan önbellekten içerik almak için HTTP kullanmasına izin verir. Bu ayar HTTP kullanır.|
|**BranchCache - Barındırılan Önbellek İstemcisi**<br>(Windows 7 veya üzeri)|BranchCache istemcilerinin barındırılan bir önbellek kullanmasına izin verir. Bu ayar HTTPS kullanır.|
|**BranchCache - Barındırılan Önbellek Sunucusu**|BranchCache istemcilerinin diğer istemcilerle iletişim kurmak için barındırılan bir önbellek kullanmasına izin verir. Bu ayar HTTPS kullanır.|
|**BranchCache - Eş Düğüm Bulma**<br>(Windows 7 veya üzeri)|BranchCache istemcilerinin yerel alt ağdaki içerik kullanılabilirliğini kontrol etmesi için Web Hizmetleri Dinamik Keşif (WS-Keşif) protokolünü kullanmasına izin verir.|
|**BITS Eşler Arasında Önbelleğe Alma**|İstemcilerin aynı alt ağdaki istemcilerin BITS önbelleğinde depolanan dosyaları bulmak ve paylaşmak için Arka Plan Akıllı Aktarım Hizmeti (BITS) kullanmasına izin verir. Bu ayar Cihazlarda Web Hizmetleri (WSDAPI) ve Uzak Yordam Çağrısı (RPC) kullanır.|
|**Bir Ağ Projektörüne Bağlanma**|Kullanıcıların proje sunumları için kablolu veya kablosuz ağlar üzerinden projektörlere bağlanmasına izin verir. Bu ayar WSDAPI kullanır.|
|**Çekirdek Ağ**|İstemcilerin ağ kaynaklarına bağlanmak için IPv4 ve IPv6 kullanmasına izin verir.|
|**Dağıtılmış İşlem Düzenleyicisi**|Yönetilen bilgisayarların; veritabanları, ileti kuyrukları ve dosya sistemleri gibi işlem korumalı kaynakları güncelleştiren işlemleri düzenlemesine olanak tanır.|
|**Dosya ve Yazıcı Paylaşımı**|Kullanıcıların ağ üzerindeki diğer kullanıcılarla yerel dosya ve yazıcıları paylaşmasına olanak tanır. Bu ayar NetBIOS, Bağlantı Yerel Çok Noktaya Yayın Adı Çözümleme (LLMNR), Sunucu ileti bloğu (SMB) protokolü ve RPC kullanır.|
|**HomeGroup**<br>(Windows 7 veya üzeri)|Yönetilen bilgisayarların bir Ev Grubu'na katılmasına olanak tanır.|
|**iSCSI Hizmeti**|Yönetilen bilgisayarların iSCSI sunucularına ve cihazlarına bağlanmasına olanak tanır.|
|**Anahtar Yönetimi Hizmeti**|Kurumsal ortamlarda bilgisayarların lisans uyumluluğu için sayılmasına izin verir.|
|**Media Center Extender’lar**|Media Center Extender'larının Windows Media Center çalıştıran bilgisayarlar ile iletişim kurmasına olanak tanır. Bu ayar Basit Hizmet Algılama Protokolü (SSDP) ve qWave kullanır.|
|**Netlogon Hizmeti**|Kullanıcıların ve hizmetlerin kimlik doğrulaması için etki alanı istemcileri ve etki alanı denetleyicisi arasında bir güvenlik kanalı yapılandırır. Bu ayar RPC kullanır.|
|**Ağ Bulma**|Bilgisayarların diğer cihazları bulmasına ve ağ üzerindeki diğer cihazlar tarafından bulunmasına izin verir. Bu ayar, Function Discovery Host ve Publication Services ve SSDP, NetBIOS, LLMNR ve UPnP ağ protokollerini kullanır.|
|**Performans Günlükleri ve Uyarılar**|Performans Günlükleri ve Uyarılar hizmetinin uzaktan yönetilmesine olanak tanır. Bu ayar RPC kullanır.|
|**Uzaktan Yönetim**|Bilgisayarın uzaktan yönetilmesine olanak tanır.|
|**Uzaktan Yardım**|Yönetilen bilgisayarların kullanıcılarının ağ üzerindeki diğer kullanıcılardan Uzaktan Yardım istemesine izin verir. Bu ayar SSDP, Eş Adı Çözümleme Protokolü (PNRP), Teredo ve UPnP ağ protokollerini kullanır.|
|**Uzak Masaüstü**|Bilgisayarın Uzak Masaüstü'nü kullanarak diğer bilgisayarlara erişmesine izin verir.|
|**Uzaktan Olay Günlüğü Yönetimi**|İstemci olay günlüklerinin uzaktan görüntülenmesine ve yönetilmesine izin verir. Bu ayar Named Pipes ve RPC kullanır.|
|**Uzaktan Zamanlanmış Görev Yönetimi**|Görev zamanlama hizmetinin uzaktan yönetilmesine olanak tanır. Bu ayar RPC kullanır.|
|**Uzaktan Hizmet Yönetimi**|İstemcilerdeki yerel hizmetlerin uzaktan yönetilmesine uzak yönetilmesine olanak tanır. Bu ayar Named Pipes ve RPC kullanır.|
|**Uzaktan Birim Yönetimi**|Uzak yazılım ve donanım disk birimi yönetimine olanak tanır. Bu ayar RPC kullanır.|
|**Yönlendirme ve Uzaktan Erişim**|Bilgisayarlara gelen VPN ve uzaktan erişim bağlantılarına olanak tanır.|
|**Güvenli Yuva Tünel Protokolü**|Güvenli Yuva Tünel Protokolü (SSTP) ile yönetilen bilgisayarlara gelen VPN bağlantılarına olanak tanır. Bu ayar HTTPS kullanır.|
|**SNMP Yakalama**|Yönetilen bilgisayarların Basit Ağ Yönetimi Protokolü (SNMP) Yakalama hizmeti trafiğini almasına olanak tanır.|
|**UPnP Çerçevesi**|Bilgisayarlardaki UPnP Çerçevesi hizmetini, bilgisayarların UPnP sertifikalı cihazları bulmasına ve kullanmasına olanak sağlayacak biçimde yapılandırır.|
|**Windows İşbirliği Bilgisayar Adı Kayıt Hizmeti**|Bilgisayarların SSDP ve PNRP kullanarak diğer bilgisayarları bulmasını ve bunlarla iletişim kurmasını sağlar.|
|**Windows Media Player**|Kullanıcıların Kullanıcı Veri Birimi Protokolü (UDP) üzerinden akış medyası almasına olanak tanır.|
|**Windows Media Player Ağ Paylaşım Hizmeti**|Kullanıcıların bir ağ üzerinden medya paylaşmasına olanak sağlar. Bu ayar SSDP, qWave ve UPnP ağ protokollerini kullanır.|
|**Windows Media Player Ağ Paylaşım Hizmeti (İnternet)**<br>(Windows 7 veya üzeri)|Kullanıcıların İnternet üzerinden ev medyası paylaşmasına izin verir.|
|**Windows Toplantı Alanı**|Kullanıcıların ağ üzerinden işbirliği yaparak belge, program ve masaüstü paylaşmasına izin verir. Bu ayar Dağıtılmış Dosya Sistemi Çoğaltma (DFSR) ve P2P kullanır.|
|**Windows Eşler Arası İşbirliği Altyapısı**|Bunların bağlanmasına imkan sağlayacak çeşitli eşler arası programlar ve teknolojiler yapılandırır. Bu ayar SSDP ve PNRP kullanır.|
|**Windows Uzaktan Yönetim (Uyumluluk)**|İşletim sistemleri ve cihazların uzaktan yönetimi için Web hizmeti tabanlı bir protokol olan WS-Management ile yönetilen bilgisayarların uzaktan yönetilmesine olanak tanır.|
|**Windows Uzaktan Yönetim**<br>(Windows 8 veya üzeri).|İşletim sistemleri ve cihazların uzaktan yönetimi için Web hizmeti tabanlı bir protokol olan WS-Management ile yönetilen bilgisayarların uzaktan yönetilmesine olanak tanır.|
|**Windows Virtual PC**<br>(Windows 7 veya üzeri)|Sanal makinelerin diğer bilgisayarlarla iletişim kurmasına olanak tanır.|
|**Taşınabilir Kablosuz Cihazlar**|Medya Aktarım Protokolü (MTP) ile ağ bağlantısı etkin kamera veya medya cihazı verilerinin yönetilen bilgisayarlara aktarılmasına olanak tanır. Bu ayar SSDP ve UPnP ağ protokollerini kullanır.|

### <a name="see-also"></a>Ayrıca bkz.
[Windows bilgisayarlarını koruma ilkeleri](policies-to-protect-windows-pcs-in-microsoft-intune.md)
