---
title: Microsoft Intune-Azure 'da Windows 10 cihazları için koruma ayarları | Microsoft Docs
description: Windows 10 cihazlarında, Application Guard, güvenlik duvarı, SmartScreen, şifreleme ve BitLocker, Exploit Guard, uygulama denetimi, güvenlik merkezi ve güvenlik dahil olmak üzere Windows Defender özelliklerini etkinleştirmek için Endpoint Protection ayarlarını kullanın veya yapılandırın Microsoft Intune yerel cihazlar.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 09/19/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 3af7c91b-8292-4c7e-8d25-8834fcf3517a
ms.reviewer: karthig
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: cdd5ae83d1ef71be31ad4507b32d2d4484da58cb
ms.sourcegitcommit: 6a946a055a2014e00a4ca9d71986727a4ebbc777
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/24/2019
ms.locfileid: "71301739"
---
# <a name="windows-10-and-later-settings-to-protect-devices-using-intune"></a>Intune kullanarak cihazları korumak için Windows 10 (ve üzeri) ayarları  

[!INCLUDE [azure_portal](./includes/azure_portal.md)]  

Microsoft Intune cihazlarınızın korunmasına yardımcı olmak için birçok ayar içerir. Bu makalede, Windows 10 ve daha yeni cihazlarda etkinleştirebileceğinizi ve yapılandırabileceğiniz tüm ayarlar açıklanmaktadır. Bu ayarlar, BitLocker ve Windows Defender gibi güvenliği denetlemek için Intune 'da bir Endpoint Protection yapılandırma profilinde oluşturulur.  

Windows Defender virüsten koruma yapılandırmak için bkz. [Windows 10 cihaz kısıtlamaları](device-restrictions-windows-10.md#microsoft-defender-antivirus).  

## <a name="before-you-begin"></a>Başlamadan önce  

[Endpoint Protection cihaz yapılandırma profili oluşturun](endpoint-protection-configure.md).  

Yapılandırma hizmeti sağlayıcıları (CSP 'Ler) hakkında daha fazla bilgi için bkz. [yapılandırma hizmeti sağlayıcısı başvurusu](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference).  

## <a name="windows-defender-application-guard"></a>Windows Defender Application Guard  

Microsoft Edge kullanırken Windows Defender Application Guard, ortamınızı kuruluşunuz tarafından güvenilir olarak tanımlanmayan sitelerden korur. Kullanıcılar yalıtılmış ağ sınırlarında listelenmeyen siteleri ziyaret ettiğinde, siteler bir Hyper-V sanal gözatma oturumunda açılır. Güvenilen siteler, cihaz yapılandırmasında yapılandırılan bir ağ sınırı tarafından tanımlanır.  

Application Guard yalnızca Windows 10 (64 bit) cihazlar için kullanılabilir. Bu profili kullanmak, Application Guard’ı etkinleştirmek için bir Win32 bileşeni yükler.  

- **Application Guard**  
  **Varsayılan**: Yapılandırılmamış  
   Application Guard CSP: [Ayarlar/Allowwindowssavunma Derapplicationguard](https://docs.microsoft.com/windows/client-management/mdm/windowsdefenderapplicationguard-csp#allowwindowsdefenderapplicationguard)  

  - **Edge Için etkinleştirildi** -güvenilmeyen siteleri bir Hyper-V sanallaştırılmış gözatma kapsayıcısında açan bu özelliği açar.  
  - **Yapılandırılmadı** -cihazda herhangi bir site (güvenilen ve güvenilmeyen) açılabilir.  

- **Pano davranışı**  
  **Varsayılan**: Yapılandırılmamış  
   Application Guard CSP: [Ayarlar/ClipboardSettings](https://go.microsoft.com/fwlink/?linkid=872351)  

  Yerel BILGISAYAR ile Application Guard sanal tarayıcısı arasında kopyalama ve yapıştırma eylemlerine izin verileceğini seçin.  
  - **Yapılandırılmadı**  
  - **BILGISAYARDAN yalnızca tarayıcıya kopyalama ve yapıştırmaya izin ver**  
  - **Tarayıcıdan yalnızca BILGISAYARA kopyalama ve yapıştırmaya izin ver**  
  - **BILGISAYAR ve tarayıcı arasında kopyalama ve yapıştırmaya izin ver**  
  - **BILGISAYAR ve tarayıcı arasında kopyalama ve yapıştırmayı engelle**  

- **Pano içeriği**  
  Bu ayar yalnızca *Pano davranışı* *izin verme* ayarlarından birine ayarlandığında kullanılabilir.  
  **Varsayılan**: Yapılandırılmamış  
  Application Guard CSP: [Ayarlar/ClipboardFileType](https://docs.microsoft.com/windows/client-management/mdm/windowsdefenderapplicationguard-csp#clipboardfiletype)  

  İzin verilen Pano içeriğini seçin.  
  - **Yapılandırılmadı**  
  - **Text**  
  - **Görüntüler**  
  - **Metin ve görüntüler**  

- **Kurumsal sitelerdeki dış içerik**  
  **Varsayılan**: Yapılandırılmamış  
  Application Guard CSP: [Ayarlar/BlockNonEnterpriseContent](https://go.microsoft.com/fwlink/?linkid=872352)  

  - **Engelle** -onaylanmayan Web sitelerindeki içeriğin yüklenmesini engelleyin.  
  - **Yapılandırılmamış** -kurumsal olmayan siteler cihazda açılabilir.  
 
- **Sanal tarayıcıdan Yazdır**  
  **Varsayılan**: Yapılandırılmamış  
  Application Guard CSP: [Ayarlar/PrintingSettings](https://go.microsoft.com/fwlink/?linkid=872354)  

  - **Izin ver** -seçili içeriğin sanal tarayıcıdan yazdırılmasının yapılmasına izin verir.  
  - **Yapılandırılmadı** Tüm yazdırma özelliklerini devre dışı bırakın.  

  Yazdırmaya *izin* aldığınızda, aşağıdaki ayarı yapılandırabilirsiniz:
  - **Yazdırma türleri** Aşağıdaki seçeneklerden birini veya daha fazlasını seçin:  
    - BELGESINI  
    - XPS  
    - Yerel yazıcılar
    - Ağ yazıcıları  

- **Günlükleri topla**  
  **Varsayılan**: Yapılandırılmamış  
  Application Guard CSP: [Denetim/AuditApplicationGuard](https://go.microsoft.com/fwlink/?linkid=872418)  

  - Application Guard gözatma oturumunda oluşan olaylar için **Izin ver** -günlükleri toplayın.  
  - **Yapılandırılmadı** -göz atma oturumunda hiçbir günlük toplanmaz.  

- **Kullanıcı tarafından oluşturulan tarayıcı verilerini koruma**  
  **Varsayılan**: Yapılandırılmamış  
  Application Guard CSP: [Ayarlar/Allowkalıcılığı](https://go.microsoft.com/fwlink/?linkid=872419)  

  - **Izin ver** Application Guard sanal gözatma oturumu sırasında oluşturulan kullanıcı verilerini (parolalar, Sık Kullanılanlar ve tanımlama bilgileri gibi) kaydedin.  
  - **Yapılandırılmadı** Cihaz yeniden başlatıldığında veya Kullanıcı oturumu kapattığında Kullanıcı tarafından indirilen dosyaları ve verileri atın.  

- **Grafik hızlandırma**  
 **Varsayılan**: Yapılandırılmamış  
  Application Guard CSP: [Ayarlar/AllowVirtualGPU](https://go.microsoft.com/fwlink/?linkid=872420)  
      
  - Sanal grafik işleme birimine erişim sağlayarak grafik yoğun Web sitelerini ve videoları daha hızlı yükleyin.  
  - **Yapılandırılmadı** Grafik için cihazın CPU 'sunu kullanın; Sanal grafik işleme birimini kullanmayın.  

- **Dosyaları konak dosya sistemine indir**  
  **Varsayılan**: Yapılandırılmamış  
  Application Guard CSP: [Ayarlar/SaveFilesToHost](https://go.microsoft.com/fwlink/?linkid=872421)  

  - **Etkinleştir** -kullanıcılar, sanallaştırılmış tarayıcıdan konak işletim sistemine dosya indirebilir.  
  - **Yapılandırılmadı** -dosyaları cihazda yerel olarak tutar ve dosyaları ana bilgisayar dosya sistemine indirmez.  

## <a name="windows-defender-firewall"></a>Windows Defender Güvenlik Duvarı  
 
### <a name="global-settings"></a>Genel ayarlar  

Bu ayarlar tüm ağ türlerine uygulanabilir.  

- **Dosya Aktarım Protokolü**  
  **Varsayılan**: Yapılandırılmamış  
   Güvenlik Duvarı CSP 'si: [MdmStore/Global/DisableStatefulFtp](https://go.microsoft.com/fwlink/?linkid=872536)  

  - **Engelle** -durum BILGISI olan FTP 'yi devre dışı bırak  
  - **Yapılandırılmadı** -güvenlik duvarı, ikincil bağlantılara izin vermek için durum BILGISI olan FTP filtrelemesini yapar.  

- **Silinmeden önce güvenlik ilişkilendirmesi boşta kalma süresi**  
  **Varsayılan**: *Yapılandırılmadı*  
   Güvenlik Duvarı CSP 'si: [MdmStore/Global/Saıdsaati](https://go.microsoft.com/fwlink/?linkid=872539)  

   Saniye cinsinden, güvenlik ilişkilerinin silineceği bir boşta kalma süresi belirtin.   

- **Önceden paylaşılan anahtar kodlaması**  
  **Varsayılan**: Yapılandırılmamış  
   Güvenlik Duvarı CSP 'si: [MdmStore/Global/PresharedKeyEncoding](https://go.microsoft.com/fwlink/?linkid=872541)  

   - **Enable** -UTF-8 kullanarak ön korumalı anahtarları kodlayın.  
   - **Yapılandırılmadı** -yerel depo değerini kullanarak, ön korumalı anahtarları kodlayın.  

- **IPSec muafiyetleri**  
  **Varsayılan**: *0 seçili*  
   Güvenlik Duvarı CSP 'si: [MdmStore/Global/ıpsecmuaf](https://go.microsoft.com/fwlink/?linkid=872547)

   IPSec 'ten muaf tutulacak aşağıdaki trafik türlerinden bir veya daha fazlasını seçin:  
   - **Komşu bulma IPv6 ICMP türü kodlar**  
   - **ICMP**  
   - **Yönlendirici bulma IPv6 ICMP türü kodlar**  
   - **Hem IPv4 hem de IPv6 DHCP ağ trafiği**  

- **Sertifika iptal listesi doğrulaması**  
  **Varsayılan**: Yapılandırılmamış  
  Güvenlik Duvarı CSP 'si: [MdmStore/Global/CRLcheck](https://go.microsoft.com/fwlink/?linkid=872548)  

  Cihazın sertifika iptal listesini nasıl doğruladığını seçin. Şu seçenekler mevcuttur:  
  - **CRL doğrulamasını devre dışı bırak**  
  - **Yalnızca iptal edilen sertifikada CRL doğrulaması başarısız oldu**  
  - **Karşılaşılan herhangi bir hatayla ılgılı CRL doğrulaması başarısız oldu**.  
 

- **Anahtarlama modülü başına mümkün olduğunda Match kimlik doğrulama kümesi**  
  **Varsayılan**: Yapılandırılmamış  
  Güvenlik Duvarı CSP 'si: [MdmStore/Global/OpportunisticallyMatchAuthSetPerKM](https://go.microsoft.com/fwlink/?linkid=872550)  
  
  - **Etkinleştir** Anahtarlama modülleri yalnızca desteklemediği kimlik doğrulama paketlerini yoksaymalıdır.  
  - **Yapılandırılmadı**, anahtar modülleri, küme içinde belirtilen tüm kimlik doğrulama paketlerini desteklemediklerinde tüm kimlik doğrulama kümesini yoksaymalıdır.  


- **Paket Kuyruklama**  
  **Varsayılan**: Yapılandırılmamış  
  Güvenlik Duvarı CSP 'si: [MdmStore/Global/EnablePacketQueue](https://go.microsoft.com/fwlink/?linkid=872551)  

  IPSec tüneli ağ geçidi senaryosu için, şifreli alma ve şifresiz metin iletme için alma tarafında yazılım ölçeklendirmesinin nasıl etkinleştirildiğini belirtin. Bu ayar, paket sırasının korunduğunu onaylar. Şu seçenekler mevcuttur:  
  - **Yapılandırılmadı**  
  - **Tüm paket kuyruğu devre dışı bırak**  
  - **Yalnızca gelen şifreli paketleri sıraya al**  
  - **Şifre çözme sonrasında yalnızca iletme için kuyruk paketleri gerçekleştirildi**  
  - **Hem gelen hem de giden paketleri yapılandırma**  

### <a name="network-settings"></a>Ağ ayarları  

Aşağıdaki ayarlar bu makalede tek bir kez listelenirse, ancak tümü üç özel ağ türüne uygulanır:  
- **Etki alanı (çalışma alanı) ağı**  
- **Özel (keşfedilebilir) ağ**  
- **Ortak (bulunamayan) ağ**  

#### <a name="general-settings"></a>Genel ayarlar  

- **Windows Defender Güvenlik Duvarı**  
  **Varsayılan**: Yapılandırılmamış  
  Güvenlik Duvarı CSP 'si: [EnableFirewall](https://go.microsoft.com/fwlink/?linkid=872558)  
  
  - **Etkinleştir** -güvenlik duvarını ve gelişmiş güvenliği etkinleştirin. 
  - **Yapılandırılmadı** Diğer ilke ayarlarından bağımsız olarak tüm ağ trafiğine izin verir.  

- **Gizli mod**  
  **Varsayılan**: Yapılandırılmamış  
  Güvenlik Duvarı CSP 'si: [DisableStealthMode](https://go.microsoft.com/fwlink/?linkid=872559)  
  - **Yapılandırılmadı**  
  - **Engelle** -güvenlik duvarının gizli modda çalışıyor olması engellenir. Gizli modu engellemek, **IPsec güvenli paket muafiyetini** de engellemenize imkan verir.  
  - **Izin ver** -güvenlik duvarı gizli modda çalışır ve bu da istekleri yoklamaya yönelik yanıtları önlemeye yardımcı olur.  

- **Gizli mod ile IPSec güvenli paket muafiyeti**  
  **Varsayılan**: Yapılandırılmamış  
  Güvenlik Duvarı CSP 'si: [Disablestealthmodeıpsecsecuredpacketexemption](https://go.microsoft.com/fwlink/?linkid=872560)  

  *Gizli mod* *blok*olarak ayarlandıysa bu seçenek yoksayılır.  

  - **Yapılandırılmadı**  
  - **Block** -IPSec güvenli paketleri muafiyet almaz.  
  - **Allow** -muafiyetleri etkinleştir. Güvenlik duvarının gizli modu, ana bilgisayarın IPSec tarafından güvenliği sağlanmış olan istenmeyen ağ trafiğine yanıt vermesini önleyememelidir.  

- **Korunan**  
  **Varsayılan**: Yapılandırılmamış  
  Güvenlik Duvarı CSP 'si: [Korunan](https://go.microsoft.com/fwlink/?linkid=872561)  
    - **Yapılandırılmadı**  
    - **Block** -Windows Defender güvenlik duvarı açık olduğunda ve bu ayar *Engelle*olarak ayarlandığında, diğer ilke ayarlarından bağımsız olarak tüm gelen trafik engellenir. 
    - **Izin ver** - *izin ver*olarak ayarlandığında, bu ayar kapalı olur ve diğer ilke ayarlarına bağlı olarak gelen trafiğe izin verilir.

- **Çok noktaya yayın yayınlarına tek noktaya yayın yanıtları**  
  **Varsayılan**: Yapılandırılmamış  
  Güvenlik Duvarı CSP 'si: [DisableUnicastResponsesToMulticastBroadcast](https://go.microsoft.com/fwlink/?linkid=872562)  
  
  Normalde, yayın veya çok noktaya yayın iletilerine tek noktaya yayın yanıtları almak istemezsiniz. Bu yanıtlar, bir hizmet reddi (DOS) saldırısı veya bir saldırganın bilinen bir canlı bilgisayarı araştırmasına çalışan bir saldırgan olduğunu gösteriyor olabilir.  
  - **Yapılandırılmadı**  
  - **Engelle** -çok noktaya yayın yayınlarına tek noktaya yayın yanıtlarını devre dışı bırakma  
  - **Allow** -çok noktaya yayın yayınlarına tek noktaya yayın yanıtlarına izin verir.  

- **Gelen bildirimler**  
  **Varsayılan**: Yapılandırılmamış  
  Güvenlik Duvarı CSP 'si: [Disableınboundnotifications](https://go.microsoft.com/fwlink/?linkid=8725630)  

  - **Yapılandırılmadı**  
  - **Engelle** -bir uygulamanın bağlantı noktasında dinlemesi engellendiğinde kullanılan bildirimleri gizleyin.  
  - **Izin ver** -bu ayarı sağlar ve bir uygulamanın bağlantı noktasında dinlemesi engellendiğinde kullanıcılara bildirim gösterilebilir.  

- **Giden bağlantılar için varsayılan eylem**  
  **Varsayılan**: Yapılandırılmamış  
  Güvenlik Duvarı CSP 'si: [Defaultoutboundavction](https://aka.ms/intune-firewall-outboundaction)  
  
  Güvenlik duvarının giden bağlantılarda gerçekleştirdiği varsayılan eylemi yapılandırın. Bu ayar, Windows sürüm 1809 ve üzeri sürümlere uygulanır.  

  - **Yapılandırılmadı**  
  - **Engelle** -varsayılan güvenlik duvarı eylemi, açıkça engellenmediği müddetçe giden trafik üzerinde çalışmaz.  
  - **Izin ver** -varsayılan güvenlik duvarı eylemleri giden bağlantılarda çalışır.  

- **Gelen bağlantılar için varsayılan eylem**  
  **Varsayılan**: Yapılandırılmamış  
  Güvenlik Duvarı CSP 'si: [Defaulınboundadction](https://go.microsoft.com/fwlink/?linkid=872564)  
 
  - **Yapılandırılmadı**  
  - **Engelle** -varsayılan güvenlik duvarı eylemi gelen bağlantılarda çalıştırılmadı.  
  - **Izin ver** -varsayılan güvenlik duvarı eylemleri gelen bağlantılarda çalışır.  

#### <a name="rule-merging"></a>Kural birleştirme  

- **Yerel depodan yetkilendirilmiş uygulama Windows Defender güvenlik duvarı kuralları**  
  **Varsayılan**: Yapılandırılmamış  
  Güvenlik Duvarı CSP 'si: [AuthAppsAllowUserPrefMerge](https://go.microsoft.com/fwlink/?linkid=872565)  

  - **Yapılandırılmadı**  
  - **Engelle** -yerel depodaki yetkili uygulama güvenlik duvarı kuralları yok sayılır ve zorlanmaz.  
  - **Izin ver** Tanınan ve zorlanan güvenlik duvarı kurallarını yerel depoda etkinleştir ' i seçin. -
     

- **Yerel depodan genel bağlantı noktası Windows Defender güvenlik duvarı kuralları**  
  **Varsayılan**: Yapılandırılmamış  
  Güvenlik Duvarı CSP 'si: [GlobalPortsAllowUserPrefMerge](https://go.microsoft.com/fwlink/?linkid=872566)  

  - **Yapılandırılmadı**  
  - **Engelle** -yerel depodaki genel bağlantı noktası güvenlik duvarı kuralları yok sayılır ve zorlanmaz.  
  - **Izin ver** -yerel depodaki genel bağlantı noktası güvenlik duvarı kurallarını tanınmak ve zorunlu olacak şekilde Uygula.  

- **Yerel depodan Windows Defender güvenlik duvarı kuralları**  
  **Varsayılan**: Yapılandırılmamış  
  Güvenlik Duvarı CSP 'si: [AllowLocalPolicyMerge](https://go.microsoft.com/fwlink/?linkid=872567)  

  - **Yapılandırılmadı**  
  - **Engelle** -yerel depodan gelen güvenlik duvarı kuralları yok sayılır ve zorlanmaz.
  - **Izin ver** -yerel depodaki Güvenlik Duvarı kurallarının tanınması ve zorlanabilmesi için bu kuralları uygulayın.  

- **Yerel depodan IPSec kuralları**  
  **Varsayılan**: Yapılandırılmamış  
  Güvenlik Duvarı CSP 'si: [Allowlocalıpsecpolicymerge](https://go.microsoft.com/fwlink/?linkid=872568)  

  - **Yapılandırılmadı**  
  - **Engelle** -yerel depodan gelen bağlantı güvenlik kuralları, şema sürümü ve bağlantı güvenliği kuralı sürümüne bakılmaksızın yok sayılır ve zorlanmaz.  
  - **Izin ver** -bağlantı güvenlik kurallarını, şema veya bağlantı güvenlik kuralı sürümlerinden bağımsız olarak yerel depodan uygulama.  

### <a name="firewall-rules"></a>Güvenlik duvarı kuralları  

Bir veya daha fazla özel güvenlik duvarı kuralı **ekleyebilirsiniz** . Daha fazla bilgi için bkz. [Windows 10 cihazları için özel güvenlik duvarı kuralları ekleme](endpoint-protection-configure.md#add-custom-firewall-rules-for-windows-10-devices).  

Özel güvenlik duvarı kuralları aşağıdaki seçenekleri destekler:  

#### <a name="general-settings"></a>Genel ayarlar:  

- **Name**  
  **Varsayılan**: *Ad yok*  

  Kuralınız için bir kolay ad belirtin. Bu ad, bu adı belirlemenize yardımcı olacak kurallar listesinde görünür.  

- **Açıklama**  
  **Varsayılan**: *Açıklama yok*  

  Kural için bir açıklama sağlayın.  

- **Görünüm**   
  **Varsayılan**: Yapılandırılmamış  
  Güvenlik Duvarı CSP 'si: [FirewallRules/*Firewallrulename*/Direction](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#direction)  
  
  Bu kuralın **gelen**veya **giden** trafiğe uygulanacağını belirtin. **Yapılandırılmadı**olarak ayarlandığında, kural otomatik olarak giden trafiğe uygulanır.  

- **Eylem**  
  **Varsayılan**: Yapılandırılmamış  
  Güvenlik Duvarı CSP 'si: [FirewallRules/*Firewallrulename*/Action](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#action)ve [FirewallRules/*firewallrulename*/Action/Type](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#type)  

  **Izin ver** veya **Engelle**arasından seçim yapın. **Yapılandırılmadı**olarak ayarlandığında, kural varsayılan trafiğe izin verir.  

- **Ağ türü**  
  **Varsayılan**: 0 adet seçildi  
  Güvenlik Duvarı CSP 'si: [FirewallRules/*Firewallrulename*/Profiles](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#profiles)  

  Bu kuralın ait olduğu üç tür ağ türünü seçin. **Etki alanı**, **özel**ve **ortak**seçenekleri içerir.  Herhangi bir ağ türü seçilmezse, kural üç ağ türüne uygulanır.  

#### <a name="application-settings"></a>Uygulama ayarları  

- **Uygulama (ler)**  
  **Varsayılan**: Tümü  

  Bir uygulama veya program için bağlantıları denetleme. Aşağıdaki seçeneklerden birini belirleyin ve ardından ek yapılandırmayı doldurun:  
  - **Paket aile adı** – bir paket aile adı belirtin. Paket aile adını bulmak için **Get-AppxPackage**PowerShell komutunu kullanın.   
    Güvenlik Duvarı CSP 'si: [FirewallRules/*Firewallrulename*/App/PackageFamilyName](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#packagefamilyname)  
 
  - **Dosya yolu** – istemci cihazında bir uygulamanın yolunu, mutlak bir yol veya göreli bir yol olabilen bir dosya yolu belirtmeniz gerekir. Örneğin:  C:\windows\system\noteasma .exe veya%Windir%\noteasma. exe.  
    Güvenlik Duvarı CSP 'si: [FirewallRules/*Firewallrulename*/App/FilePath](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#filepath)  

  - **Windows hizmeti** – trafik gönderen veya alan bir uygulama değil, bir hizmet Ise, Windows hizmeti kısa adını belirtin. Hizmet kısa adını bulmak için, **Get-Service**PowerShell komutunu kullanın.  
    Güvenlik Duvarı CSP 'si: [FirewallRules/*Firewallrulename*/App/ServiceName](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#servicename)  

  - **Tümü**– *ek yapılandırma kullanılamaz*.  

#### <a name="ip-address-settings"></a>IP adresi ayarları  

Bu kuralın uygulandığı yerel ve uzak adresleri belirtin.  

- **Yerel adresler**    
  **Varsayılan**: Herhangi bir adres  
  Güvenlik Duvarı CSP 'si: [FirewallRules/*Firewallrulename*/Localportranges](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#localportranges)  

  **Herhangi bir adresi** veya **belirtilen adresi**seçin.  

  *Belirtilen adresi*kullandığınızda, bir veya daha fazla adresi kuralın kapsadığı yerel adreslerin virgülle ayrılmış bir listesi olarak eklersiniz. Geçerli belirteçler şunlardır:  
  - *Herhangi* bir yerel adres için yıldız işareti "*" kullanın. Bir yıldız işareti kullanırsanız, kullandığınız tek belirteç olmalıdır.  
  - Bir alt ağ belirtmek için alt ağ maskesini veya ağ öneki gösterimini kullanın. Bir alt ağ maskesi veya ağ öneki belirtilmemişse, alt ağ maskesi varsayılan olarak 255.255.255.255 olur.  
  - Geçerli bir IPv6 adresi.  
  - Boşluk içermeyen "başlangıç adresi-bitiş adresi" biçimindeki bir IPv4 adresi aralığı.  
  - Boşluk içermeyen "başlangıç adresi-bitiş adresi" biçimindeki bir IPv6 adres aralığı.  

- **Uzak adresler**  
  **Varsayılan**: Herhangi bir adres  
  Güvenlik Duvarı CSP 'si: [FirewallRules/*Firewallrulename*/Remoteaddressranges](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#remoteaddressranges)  
 
  **Herhangi bir adresi** veya **belirtilen adresi**seçin.  

  *Belirtilen adresi*kullandığınızda, bir veya daha fazla adresi, kural kapsamındaki uzak adreslerin virgülle ayrılmış bir listesi olarak eklersiniz. Belirteçler büyük/küçük harfe duyarlı değildir. Geçerli belirteçler şunlardır:  
  - *Herhangi* bir uzak adres için yıldız işareti "*" kullanın. Bir yıldız işareti kullanırsanız, kullandığınız tek belirteç olmalıdır.  
  - "Defaultgateway"  
  - BKZ  
  - BKZ  
  - DÜR  
  - "Intranet" (Windows sürümleri 1809 ve üzeri sürümlerde desteklenir)  
  - "Rmtıntranet" (Windows sürümleri 1809 ve üzeri sürümlerde desteklenir)  
  - "Internet" (Windows sürümleri 1809 ve üzeri sürümlerde desteklenir)  
  - "Ply2Renders" (Windows sürümleri 1809 ve üzeri sürümlerde desteklenir)  
  - "LocalSubnet" yerel alt ağdaki herhangi bir yerel adresi belirtir.  
  - Bir alt ağ belirtmek için alt ağ maskesini veya ağ öneki gösterimini kullanın. Bir alt ağ maskesi veya ağ öneki belirtilmemişse, alt ağ maskesi varsayılan olarak 255.255.255.255 olur.  
  - Geçerli bir IPv6 adresi.  
  - Boşluk içermeyen "başlangıç adresi-bitiş adresi" biçimindeki bir IPv4 adresi aralığı.  
  - Boşluk içermeyen "başlangıç adresi-bitiş adresi" biçimindeki bir IPv6 adres aralığı.  

#### <a name="port-and-protocol-settings"></a>Bağlantı noktası ve protokol ayarları  
Bu kuralın uygulandığı yerel ve uzak bağlantı noktalarını belirtin.  

- **Protokolü**  
  **Varsayılan**: Any  
  Güvenlik Duvarı CSP 'si: [FirewallRules/*Firewallrulename*/Protocol](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#protocol)  
  Aşağıdakilerden birini seçin ve gerekli tüm konfigürasyonları doldurun:  
  - **Tümü** – ek yapılandırma kullanılamaz.  
  - **TCP** – yerel ve uzak bağlantı noktalarını yapılandırın. Her iki seçenek de tüm bağlantı noktalarını veya belirtilen bağlantı noktalarını destekler. Virgülle ayrılmış bir liste kullanarak belirtilen bağlantı noktalarını girin.  
    - **Yerel bağlantı noktaları** -GÜVENLIK duvarı CSP: [FirewallRules/*Firewallrulename*/Localportranges](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#localportranges)  
    - **Uzak bağlantı noktaları** -GÜVENLIK duvarı CSP: [FirewallRules/*Firewallrulename*/Remoteportranges](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#remoteportranges)  
  - **UDP** – yerel ve uzak bağlantı noktalarını yapılandırın. Her iki seçenek de tüm bağlantı noktalarını veya belirtilen bağlantı noktalarını destekler. Virgülle ayrılmış bir liste kullanarak belirtilen bağlantı noktalarını girin.  
    - **Yerel bağlantı noktaları** -GÜVENLIK duvarı CSP: [FirewallRules/*Firewallrulename*/Localportranges](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#localportranges)  
    - **Uzak bağlantı noktaları** -GÜVENLIK duvarı CSP: [FirewallRules/*Firewallrulename*/Remoteportranges](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#remoteportranges)  
  - **Özel** – 0 ile 255 arasında özel bir **protokol** belirtin.  

#### <a name="advanced-configuration"></a>Gelişmiş yapılandırma  
- **Arabirim türleri**  
  **Varsayılan**: 0 adet seçildi  
  Güvenlik Duvarı CSP 'si: [FirewallRules/*Firewallrulename*/InterfaceType](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#interfacetypes)  

  Aşağıdaki seçeneklerden seçim yapın:  
  - **Uzaktan erişim**  
  - **SA**  
  - **Yerel alan ağı**  

- **Yalnızca bu kullanıcılardan bağlantılara izin ver**  
  **Varsayılan**: Tüm kullanıcılar *(hiçbir liste belirtilmediğinde varsayılan olarak tüm kullanımlar)*  
  Güvenlik Duvarı CSP 'si: [FirewallRules/*Firewallrulename*/Localuserauthorizationlist](https://aka.ms/intunefirewallauthorizedusers)  

  Bu kural için yetkili yerel kullanıcıların bir listesini belirtin. Bu kural bir Windows hizmeti için geçerliyse yetkili kullanıcıların listesi belirtilemez.  


## <a name="windows-defender-smartscreen-settings"></a>Windows Defender SmartScreen ayarları  
 
Cihazda Microsoft Edge yüklü olmalıdır.  

- **Uygulamalar ve dosyalar için SmartScreen**  
  **Varsayılan**: Yapılandırılmamış  
   SmartScreen CSP: [SmartScreen/Enablesmartscreenınshell](https://go.microsoft.com/fwlink/?linkid=872784)  

  - **Yapılandırılmadı** -SmartScreen kullanımını devre dışı bırakır.  
  - **Enable** -Windows SmartScreen 'i dosya yürütme ve çalıştırma uygulamaları için etkinleştirin. SmartScreen, bulut tabanlı bir kimlik avından korunma ve kötü amaçlı yazılımdan korunma bileşenidir.  

- **Doğrulanmamış dosya yürütme**  
  **Varsayılan**: Yapılandırılmamış  
   SmartScreen CSP: [SmartScreen/PreventOverrideForFilesInShell](https://go.microsoft.com/fwlink/?linkid=872783)

  - **Yapılandırılmadı** -bu özelliği devre dışı bırakır ve son kullanıcıların doğrulanmamış dosyaları çalıştırmasına izin verir.  
  - **Engelle** -son kullanıcıların Windows SmartScreen tarafından doğrulanmamış dosyaları çalıştırmasını engelleyin.  

## <a name="windows-encryption"></a>Windows Şifreleme  
 
### <a name="windows-settings"></a>Windows Ayarları  

Bu şifreleme ayarları tüm Windows 10 sürümleri için geçerlidir.  

- **Cihazları şifreleme**  
  **Varsayılan**: Yapılandırılmamış  
  BitLocker CSP: [RequireDeviceEncryption](https://go.microsoft.com/fwlink/?linkid=872523)  

  - **Gerektir** -kullanıcılardan cihaz şifrelemesini etkinleştirmesini iste. Windows sürümü ve sistem yapılandırmasına bağlı olarak kullanıcılardan şunlar istenebilir:  
    - Başka bir sağlayıcıdan şifrelemenin etkin olmadığını doğrulamak için.  
    - BitLocker Sürücü Şifrelemesi devre dışı bırakmak ve sonra BitLocker 'ı yeniden açmak için gereklidir.  
  - **Yapılandırılmadı**  
  
  Başka bir şifreleme yöntemi etkinken Windows şifrelemesi açılırsa cihaz kullanılamaz hale gelebilir.  

- **Depolama kartını şifreleme (yalnızca mobil)**  
  *Bu ayar yalnızca Windows 10 Mobile için geçerlidir.*  
  **Varsayılan**: Yapılandırılmamış  
  BitLocker CSP: [Requirestokıgecardencryption](https://go.microsoft.com/fwlink/?linkid=872524)  

  - Cihazın kullandığı çıkarılabilir depolama kartlarını şifrelemeyi **gerektirir** .  
  - **Yapılandırılmadı** -depolama kartı şifrelemesi gerektirmez ve kullanıcıdan açmayı sorma.  

### <a name="bitlocker-base-settings"></a>BitLocker temel ayarları  

Temel ayarlar, tüm veri sürücüsü türleri için evrensel BitLocker ayarlarıdır. Bu ayarlar, tüm veri sürücüsü türlerinde son kullanıcıların değiştirebileceği sürücü şifreleme görevleri veya yapılandırma seçeneklerini yönetir.  

- **Diğer disk şifrelemesi için uyarı**  
  **Varsayılan**: Yapılandırılmamış  
  BitLocker CSP: [AllowWarningForOtherDiskEncryption](https://go.microsoft.com/fwlink/?linkid=872525)  

  - **Engelle** -cihazda başka bir disk şifreleme hizmeti varsa uyarı isteğini devre dışı bırakın.  
  - **Yapılandırılmadı** -diğer disk şifrelemesi için uyarının gösterilmesine izin verin.  

  *Blok*olarak ayarlandığında, aşağıdaki ayarı yapılandırabilirsiniz:  

  - **Standart kullanıcıların Azure AD katılımı sırasında şifrelemeyi etkinleştirmesine izin ver**  
    *Bu ayar yalnızca Azure Active Directory katılmış (Azure SıFATı) cihazları için geçerlidir ve önceki ayara `Warning for other disk encryption`bağlıdır.*  
    **Varsayılan**: Yapılandırılmamış  
    BitLocker CSP: [AllowStandardUserEncryption](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#allowstandarduserencryption)

     - **Izin ver** -standart kullanıcılar (yönetici olmayanlar), oturum açıldığında BitLocker şifrelemesini etkinleştirebilir.  
     - **Yapılandırılmamış** yalnızca Yöneticiler cihazda BitLocker şifrelemesini etkinleştirebilir.  

- **Şifreleme yöntemlerini Yapılandır**  
  **Varsayılan**: Yapılandırılmamış  
  BitLocker CSP: [EncryptionMethodByDriveType](https://go.microsoft.com/fwlink/?linkid=872526)  

  - **Enable** -işletim sistemi, veriler ve çıkarılabilir sürücüler için şifreleme algoritmaları yapılandırın.  
  - **Yapılandırılmadı** -BitLocker varsayılan şifreleme yöntemi olarak XTS-AES 128 bitini kullanır veya herhangi bir kurulum betiği tarafından belirtilen şifreleme yöntemini kullanır.  

  *Enable*olarak ayarlandığında, aşağıdaki ayarları yapılandırabilirsiniz:  

  - **İşletim sistemi sürücüleri için şifreleme**  
    **Varsayılan**: XTS-AES 128 bit  
   
    İşletim sistemi sürücüleri için şifreleme yöntemini seçin. XTS-AES algoritmasını kullanmanızı öneririz.  
    - **AES-CBC 128 bit**  
    - **AES-CBC 256 bit**  
    - **XTS-AES 128 bit**  
    - **XTS-AES 256 bit**  

  - **Sabit veri sürücüleri için şifreleme**  
    **Varsayılan**: AES-CBC 128 bit  
   
    Sabit (yerleşik) veri sürücüleri için şifreleme yöntemini seçin. XTS-AES algoritmasını kullanmanızı öneririz.  
    - **AES-CBC 128 bit**  
    - **AES-CBC 256 bit**  
    - **XTS-AES 128 bit**  
    - **XTS-AES 256 bit**  

  - **Çıkarılabilir veri sürücüleri için şifreleme**  
    **Varsayılan**: AES-CBC 128 bit  

    Çıkarılabilir veri sürücüleri için şifreleme yöntemini seçin. Çıkarılabilir sürücü, Windows 10 çalıştırmayan cihazlarla kullanılıyorsa AES-CBC algoritmasını kullanmanızı öneririz.  
    - **AES-CBC 128 bit**  
    - **AES-CBC 256 bit**  
    - **XTS-AES 128 bit**  
    - **XTS-AES 256 bit**  

### <a name="bitlocker-os-drive-settings"></a>BitLocker işletim sistemi sürücüsü ayarları  

Bu ayarlar, belirli işletim sistemi veri sürücüleri için geçerlidir.  

- **Başlangıçta ek kimlik doğrulaması**  
  **Varsayılan**: Yapılandırılmamış  
  BitLocker CSP: [SystemDrivesRequireStartupAuthentication](https://go.microsoft.com/fwlink/?linkid=872527)  

  - **Gerektir** -GÜVENILIR Platform Modülü (TPM) kullanımı dahil olmak üzere bilgisayar başlatması için kimlik doğrulama gereksinimlerini yapılandırın.  
  - **Yapılandırılmadı** -yalnızca TPM içeren cihazlarda temel seçenekleri yapılandırın.  

  *Gerektir*olarak ayarlandığında, aşağıdaki ayarları yapılandırabilirsiniz:  

  - **Uyumlu olmayan TPM yongası ile BitLocker**  
    **Varsayılan**: Yapılandırılmamış  

    - **Engelle** -cihazda uyumlu bir TPM yongası olmadığında BitLocker 'ın kullanımını devre dışı bırakın.  
    - **Yapılandırılmadı** -kullanıcılar, uyumlu bir TPM yongası olmadan BitLocker kullanabilir. BitLocker bir parola veya başlangıç anahtarı gerektirebilir.  

  - **Uyumlu TPM başlatması**  
    **Varsayılan**: TPM 'ye izin ver  

    TPM 'ye izin verilip verilmediğini, gerekli veya izin verilmediğini yapılandırın.  

    - **TPM 'ye izin ver**  
    - **TPM 'ye izin verme**  
    - **TPM iste**  

  - **Uyumlu TPM başlangıç PIN 'ı**  
    **Varsayılan**: TPM ile başlangıç PIN 'e izin ver  

    TPM yongasıyla bir başlangıç PIN 'i kullanılmasına izin verme, izin verme veya isteme seçeneğini belirleyin. Başlangıç PIN’ini etkinleştirme, son kullanıcı etkileşimi gerektirir.  

    - **TPM ile başlangıç PIN 'e izin ver**  
    - **TPM ile başlangıç PIN 'e izin verme**  
    - **TPM ile başlangıç PIN 'ı gerektir**

  - **Uyumlu TPM başlangıç anahtarı**  
    **Varsayılan**: TPM ile başlangıç anahtarına izin ver  

    TPM yongasıyla bir başlangıç anahtarı kullanılmasına izin verme, izin verme veya isteme seçeneğini belirleyin. Başlangıç anahtarını etkinleştirme, son kullanıcı etkileşimi gerektirir.  

    - **TPM ile başlangıç anahtarına izin ver**  
    - **TPM ile başlangıç anahtarına izin verme**  
    - **TPM ile başlangıç anahtarı gerektir**  

  - **Uyumlu TPM başlangıç anahtarı ve PIN 'ı**  
    **Varsayılan**: TPM ile başlangıç anahtarına ve PIN 'e izin ver  

    TPM yongasıyla bir başlangıç anahtarı ve PIN kullanılmasına izin verme, izin verme veya gerektirme seçeneğini belirleyin. Başlangıç anahtarı ve PIN’i etkinleştirme, son kullanıcı etkileşimi gerektirir.  
    - **TPM ile başlangıç anahtarına ve PIN 'e izin ver**  
    - **TPM ile başlangıç anahtarına ve PIN 'e izin verme**  
    - **TPM ile başlangıç anahtarı ve PIN gerektir**   

- **Minimum PIN uzunluğu**  
    **Varsayılan**: Yapılandırılmamış  
    BitLocker CSP: [SystemDrivesMinimumPINLength](https://go.microsoft.com/fwlink/?linkid=872528)   

    - **Etkinleştir** TPM başlangıç PIN 'ı için en düşük uzunluğu yapılandırın.  
    - **Yapılandırılmadı** -kullanıcılar, 6 ila 20 basamak arasında herhangi bir uzunlukta bir başlangıç PIN 'i yapılandırabilir.  

  *Enable*olarak ayarlandığında, aşağıdaki ayarı yapılandırabilirsiniz:  

  - **En az karakter**  
    **Varsayılan**: *Yapılandırılmadı* BitLocker CSP: [SystemDrivesMinimumPINLength](https://go.microsoft.com/fwlink/?linkid=872528)  

    Başlangıç PIN kodu için gereken karakter sayısını **4**-**20**' den girin.  

- **İşletim sistemi sürücüsü kurtarma**  
  **Varsayılan**: Yapılandırılmamış   
  BitLocker CSP: [SystemDrivesRecoveryOptions](https://go.microsoft.com/fwlink/?linkid=872529)  

  - **Etkinleştir** -gerekli başlatma bilgileri olmadığında BitLocker korumalı işletim sistemi sürücülerinin nasıl kurtarılacağını denetleyin.  
  - **Yapılandırılmadı** -BitLocker kurtarma için varsayılan kurtarma seçenekleri desteklenir. Varsayılan olarak, bir DRA 'ya izin verilir, kurtarma parolası ve kurtarma anahtarı da dahil olmak üzere, kurtarma seçenekleri Kullanıcı tarafından seçilir ve kurtarma bilgileri AD DS ' a yedeklenmez.  

  *Enable*olarak ayarlandığında, aşağıdaki ayarları yapılandırabilirsiniz:  

  - **Sertifika tabanlı veri kurtarma aracısı**  
    **Varsayılan**: Yapılandırılmamış  
     
    - **Engelle** -BitLocker korumalı işletim sistemi sürücüleriyle veri kurtarma aracısının kullanımını engeller.  
    - **Yapılandırılmadı** -BitLocker korumalı işletim sistemi sürücüleriyle birlikte veri kurtarma aracılarının kullanılmasına izin verin.  

  - **Kurtarma parolasının Kullanıcı tarafından oluşturulması**  
    **Varsayılan**: 48 basamaklı kurtarma parolasına izin ver  

    Kullanıcıların 48 basamaklı bir kurtarma parolası oluşturmasına izin verilip verilmeyeceğini veya bunun gerekli olup olmadığını seçin.  
    - **48 basamaklı kurtarma parolasına izin ver**  
    - **48 rakamlı kurtarma parolasına izin verme**  
    - **48 basamaklı kurtarma parolası gerektir**  

  - **Kurtarma anahtarının Kullanıcı tarafından oluşturulması**  
    **Varsayılan**: 256 bitlik kurtarma anahtarına izin ver  

    Kullanıcılardan 256 bitlik bir kurtarma anahtarı oluşturmasına izin verilip verilmeyeceğini veya bunun gerekli olup olmadığını seçin.  
    - **256 bitlik kurtarma anahtarına izin ver**  
    - **256 bit kurtarma anahtarına izin verme**  
    - **256 bitlik kurtarma anahtarı gerektir**  

  - **BitLocker kurulum sihirbazında kurtarma seçenekleri**  
    **Varsayılan**: Yapılandırılmamış  

    - **Engelle** -kullanıcılar kurtarma seçeneklerini göremez ve değiştiremezler. Olarak ayarlandığında 
    - **Yapılandırılmadı** -kullanıcılar BitLocker 'ı açtıklarında kurtarma seçeneklerini görebilir ve değiştirebilir. 
 
  - **BitLocker kurtarma bilgilerini Azure Active Directory Kaydet**  
    **Varsayılan**: Yapılandırılmamış  

    - **Enable** -BitLocker kurtarma bilgilerini Azure Active Directory (Azure AD) olarak depolayın.  
    - **Yapılandırılmadı** -BitLocker kurtarma bilgileri AAD 'de depolanmaz.  

  - **Azure Active Directory depolanan BitLocker kurtarma bilgileri**  
    **Varsayılan**: Yedekleme kurtarma parolaları ve anahtar paketleri  

    BitLocker kurtarma bilgilerinin hangi bölümlerinin Azure AD 'de depolandığını yapılandırın. Aşağıdakilerden birini seçin:  
    - **Yedekleme kurtarma parolaları ve anahtar paketleri**  
    - **Yalnızca yedekleme kurtarma parolaları**  

  - **İstemci tabanlı kurtarma parolası döndürme**  
    **Varsayılan**: Azure AD 'ye katılmış cihazlar için anahtar döndürme etkin  
    BitLocker CSP: [ConfigureRecoveryPasswordRotation](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp)  
    
    Bu ayar, bir işletim sistemi sürücü kurtarmasından sonra (Bootmgr veya WinRE kullanarak) istemci tabanlı bir kurtarma parolası dönüşü başlatır.  

    - Yapılandırılmamış  
    - Anahtar döndürme devre dışı  
    - Azure AD 'ye katılmış ana için anahtar döndürme etkinleştirildi  
    - Azure AD ve Hibriya katılmış cihazlar için anahtar döndürme etkinleştirildi  

  - **BitLocker 'ı etkinleştirmeden önce kurtarma bilgilerini Azure Active Directory depolama**  
    **Varsayılan**: Yapılandırılmamış  
 
     Bilgisayar BitLocker kurtarma bilgilerini Azure Active Directory için başarılı bir şekilde yedeklemediği takdirde kullanıcıların BitLocker 'ı etkinleştirmelerini engelleyin.  

    - **Gerektir** -BitLocker kurtarma BILGILERI Azure AD 'de başarıyla depolanmadığı takdirde kullanıcıların BitLocker 'ı açmasını durdurun.  
    - **Yapılandırılmadı** -kurtarma BILGILERI Azure AD 'de başarılı bir şekilde depolanmasa bile, kullanıcılar BitLocker 'ı açabilir.  

- **Önyükleme öncesi kurtarma iletisi ve URL 'SI**  
  **Varsayılan**: Yapılandırılmamış  
  BitLocker CSP: [SystemDrivesRecoveryMessage](https://go.microsoft.com/fwlink/?linkid=872530)  

  - **Enable** -önyükleme öncesi anahtar kurtarma ekranında görüntülenen iletiyi ve URL 'yi yapılandırın.  
  - **Yapılandırılmadı** -bu özelliği devre dışı bırakın.  
  
  *Enable*olarak ayarlandığında, aşağıdaki ayarı yapılandırabilirsiniz:  
  - **Önyükleme öncesi kurtarma iletisi**  
    **Varsayılan**: Varsayılan kurtarma iletisi ve URL 'sini kullan   
 
    Ön önyükleme kurtarma iletisinin kullanıcılara nasıl görüntüleneceğini yapılandırın. Aşağıdakilerden birini seçin:  
    - **Varsayılan kurtarma iletisi ve URL'sini kullan**  
    - **Boş kurtarma iletisi ve URL'si kullan**  
    - **Özel kurtarma iletisi kullan**  
    - **Özel kurtarma URL'si kullan**  

### <a name="bitlocker-fixed-data-drive-settings"></a>BitLocker sabit veri sürücüsü ayarları  

Bu ayarlar özellikle sabit veri sürücülerine uygulanır.  

- **BitLocker tarafından korunmayan sabit veri sürücüsüne yazma erişimi**  
  **Varsayılan**: Yapılandırılmamış  
  BitLocker CSP: [FixedDrivesRequireEncryption](https://go.microsoft.com/fwlink/?linkid=872534)  

  - **Block** -BitLocker korumalı olmayan veri sürücülerine salt okuma erişimi verin.  
  - **Yapılandırılmadı** -varsayılan olarak, şifrelenmemiş veri sürücülerine yönelik okuma ve yazma erişimi.  

- **Sabit sürücü kurtarma**  
  **Varsayılan**: Yapılandırılmamış  
  BitLocker CSP: [FixedDrivesRecoveryOptions](https://go.microsoft.com/fwlink/?linkid=872538)  

  - **Enable** -gerekli başlatma bilgileri olmadığında BitLocker korumalı sabit sürücülerin nasıl kurtarılacağını denetleyin.  
  - **Yapılandırılmadı** -bu özelliği devre dışı bırakın.  

  *Enable*olarak ayarlandığında, aşağıdaki ayarları yapılandırabilirsiniz:  

  - **Veri Kurtarma Aracısı**  
    **Varsayılan**: Yapılandırılmamış  
 
    - **Engelle** -BitLocker korumalı sabit sürücüler ilke Düzenleyicisi ile veri kurtarma aracısının kullanımını engeller. 
    - **Yapılandırılmadı** -BitLocker korumalı sabit sürücülerle veri kurtarma aracılarının kullanılmasına izin vermez.  

  - **Kurtarma parolasının Kullanıcı tarafından oluşturulması**  
    **Varsayılan**: 48 basamaklı kurtarma parolasına izin ver  

    Kullanıcıların 48 basamaklı bir kurtarma parolası oluşturmasına izin verilip verilmeyeceğini veya bunun gerekli olup olmadığını seçin.  
    - **48 basamaklı kurtarma parolasına izin ver**  
    - **48 rakamlı kurtarma parolasına izin verme**  
    - **48 basamaklı kurtarma parolası gerektir**  

  - **Kurtarma anahtarının Kullanıcı tarafından oluşturulması**  
    **Varsayılan**: 256 bitlik kurtarma anahtarına izin ver

    Kullanıcılardan 256 bitlik bir kurtarma anahtarı oluşturmasına izin verilip verilmeyeceğini veya bunun gerekli olup olmadığını seçin.
    - **256 bitlik kurtarma anahtarına izin ver**  
    - **256 bit kurtarma anahtarına izin verme**  
    - **256 bitlik kurtarma anahtarı gerektir**  

  - **BitLocker kurulum sihirbazında kurtarma seçenekleri**  
    **Varsayılan**: Yapılandırılmamış  

    - **Engelle** -kullanıcılar kurtarma seçeneklerini göremez ve değiştiremezler. Olarak ayarlandığında 
    - **Yapılandırılmadı** -kullanıcılar BitLocker 'ı açtıklarında kurtarma seçeneklerini görebilir ve değiştirebilir.
 
  - **BitLocker kurtarma bilgilerini Azure Active Directory Kaydet**  
    **Varsayılan**: Yapılandırılmamış  

    - **Enable** -BitLocker kurtarma bilgilerini Azure Active Directory (Azure AD) olarak depolayın.  
    - **Yapılandırılmadı** -BitLocker kurtarma bilgileri AAD 'de depolanmaz.

  - **Azure Active Directory depolanan BitLocker kurtarma bilgileri**  
    **Varsayılan**: Yedekleme kurtarma parolaları ve anahtar paketleri  

    BitLocker kurtarma bilgilerinin hangi bölümlerinin Azure AD 'de depolandığını yapılandırın. Aşağıdakilerden birini seçin:  
    - **Yedekleme kurtarma parolaları ve anahtar paketleri**  
    - **Yalnızca yedekleme kurtarma parolaları**  

  - **İstemci tabanlı kurtarma parolası döndürme**  
    **Varsayılan**: Azure AD 'ye katılmış cihazlar için anahtar döndürme etkin  
    BitLocker CSP: [ConfigureRecoveryPasswordRotation](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp)  
    
    Bu ayar, bir işletim sistemi sürücü kurtarmasından sonra (Bootmgr veya WinRE kullanarak) istemci tabanlı bir kurtarma parolası dönüşü başlatır.  

    - Yapılandırılmamış  
    - Anahtar döndürme devre dışı  
    - Azure AD 'ye katılmış ana için anahtar döndürme etkinleştirildi  
    - Azure AD ve Hibriya katılmış cihazlar için anahtar döndürme etkinleştirildi  

  - **BitLocker 'ı etkinleştirmeden önce kurtarma bilgilerini Azure Active Directory depolama**  
    **Varsayılan**: Yapılandırılmamış  
 
    Bilgisayar BitLocker kurtarma bilgilerini Azure Active Directory için başarılı bir şekilde yedeklemediği takdirde kullanıcıların BitLocker 'ı etkinleştirmelerini engelleyin.  

    - **Gerektir** -BitLocker kurtarma BILGILERI Azure AD 'de başarıyla depolanmadığı takdirde kullanıcıların BitLocker 'ı açmasını durdurun.  
    - **Yapılandırılmadı** -kurtarma BILGILERI Azure AD 'de başarılı bir şekilde depolanmasa bile, kullanıcılar BitLocker 'ı açabilir.  

### <a name="bitlocker-removable-data-drive-settings"></a>BitLocker çıkarılabilir veri sürücüsü ayarları  

Bu ayarlar özellikle çıkarılabilir veri sürücülerine uygulanır.  

- **BitLocker tarafından korunmayan çıkarılabilir veri sürücüsüne yazma erişimi**  
  **Varsayılan**: Yapılandırılmamış  
  BitLocker CSP: [RemovableDrivesRequireEncryption](https://go.microsoft.com/fwlink/?linkid=872540)  

  - **Block** -BitLocker korumalı olmayan veri sürücülerine salt okuma erişimi verin.  
  - **Yapılandırılmadı** -varsayılan olarak, şifrelenmemiş veri sürücülerine yönelik okuma ve yazma erişimi.  

  *Enable*olarak ayarlandığında, aşağıdaki ayarı yapılandırabilirsiniz:  

  - **Başka bir kuruluşta yapılandırılmış cihazlara yazma erişimi**  
    **Varsayılan**: Yapılandırılmamış  

    - **Engelle** -başka bir kuruluşta yapılandırılmış cihazlara blok yazma erişimi.  
    - **Yapılandırılmadı** -yazma erişimini reddet.  
 
## <a name="windows-defender-exploit-guard"></a>Windows Defender Exploit Guard  

Çalışanlarınızın kullandığı uygulamalarda saldırı yüzeyini yönetmek ve azaltmak için [Windows Defender Exploit Guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard) kullanın.  

### <a name="attack-surface-reduction"></a>Saldırı Yüzeyini Azaltma  

*Saldırı yüzeyi azaltma* kuralları hakkında daha fazla bilgi için bkz. Windows Defender Exploit Guard belgelerindeki [Windows Defender Exploit Guard Ile saldırı yüzeylerini azaltma](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard) .  

#### <a name="attack-surface-reduction-rules"></a>Saldırı yüzeyi azaltma kuralları  

- **Windows yerel güvenlik yetkilisi alt sisteminden kimlik bilgisi çalma eylemlerine bayrak ekleme**  
  **Varsayılan**: Yapılandırılmamış  
  Exploit Guard: [Saldırı yüzeyi azaltma kuralları](https://go.microsoft.com/fwlink/?linkid=874499)

  Genellikle, kötü amaçlı yazılım bulaşarak zararlı yazılımlara karşı kullanılan eylemleri ve uygulamaları önlemeye yardımcı olun.  
  - **Yapılandırılmadı**  
  - Windows yerel güvenlik yetkilisi alt sisteminden (Lsass. exe) kimlik bilgisi çalmasını etkinleştir ' i **etkinleştirin** .  
  - **Yalnızca denetim**  

- **Adobe Reader 'dan işlem oluşturma (Beta)**  
  **Varsayılan**: Yapılandırılmamış  
  Exploit Guard: [Saldırı yüzeyi azaltma kuralları](https://go.microsoft.com/fwlink/?linkid=853979)  

  - **Yapılandırılmadı**  
  - **Enable** -Adobe Reader 'dan oluşturulan alt süreçlerini engelleyin.  
  - **Yalnızca denetim**  

#### <a name="rules-to-prevent-office-macro-threats"></a>Office Macro tehditlerini önlemek için kurallar  

Office uygulamalarının aşağıdaki eylemleri yapmasını engelleyin:  

- **Office uygulamalarının diğer işlemlere katılması (özel durum yok)**  
  **Varsayılan**: Yapılandırılmamış  
  [Exploit Guard belgeleri](https://go.microsoft.com/fwlink/?linkid=872974)  

  - **Yapılandırılmadı**  
  - **Engelle** -Office uygulamalarının diğer işlemlere ekleme engelleyin.  
  - **Yalnızca denetim**  

- **Office uygulamaları/makrolarının yürütülebilir içerik oluşturması**  
  **Varsayılan**: Yapılandırılmamış  
  [Exploit Guard belgeleri](https://go.microsoft.com/fwlink/?linkid=872975)  

  - **Yapılandırılmadı**  
  - **Engelle** -Office uygulamalarının ve makroların yürütülebilir içerik oluşturmasını engelleyin.  
  - **Yalnızca denetim**  

- **Office uygulamalarının alt işlemler başlatması**  
  **Varsayılan**: Yapılandırılmamış  
  [Exploit Guard belgeleri](https://go.microsoft.com/fwlink/?linkid=872976)  

  - **Yapılandırılmadı**  
  - **Engelle** -Office uygulamalarının alt işlemlerin başlatılmasını engelleyin.  
  - **Yalnızca denetim**  
  
- **Win32’nin Office makro kodundan içeri aktarması**  
  **Varsayılan**: Yapılandırılmamış  
  [Exploit Guard belgeleri](https://go.microsoft.com/fwlink/?linkid=872977)  

  - **Yapılandırılmadı**  
  - **Block** -Office 'teki makro kodundan Win32 içeri aktarmaları engelleyin.  
  - **Yalnızca denetim**  
  
- **Office iletişim ürünlerinden işlem oluşturma**  
  **Varsayılan**: Yapılandırılmamış  
  [Exploit Guard belgeleri](https://go.microsoft.com/fwlink/?linkid=874499)  

  - **Yapılandırılmadı**  
  - **Enable** -Office iletişim uygulamalarından alt işlem oluşturmayı engelleyin.  
  - **Yalnızca denetim**  

#### <a name="rules-to-prevent-script-threats"></a>Komut dosyası tehditlerini önlemek için kurallar  

Komut dosyası tehditlerini önlemeye yardımcı olmak için aşağıdakileri engelleyin:  

- **Karartılmış js/vbs/ps/makro kod**  
  **Varsayılan**: Yapılandırılmamış  
  [Exploit Guard belgeleri](https://go.microsoft.com/fwlink/?linkid=872978)    

  - **Yapılandırılmadı**  
  - **Block** -tüm karıştırılmış js/vbs/PS/makro kodunu engelleyin.  
  - **Yalnızca denetim**  

- **İnternetten indirilen zararlı yükü yürüten js/vbs(özel durum yok)**  
  **Varsayılan**: Yapılandırılmamış  
  [Exploit Guard belgeleri](https://go.microsoft.com/fwlink/?linkid=872979)  

  - **Yapılandırılmadı**  
  - **Block** -Block js/vbs, Internet 'ten indirilen yükü yürütmeyi engelliyor.  
  - **Yalnızca denetim**  

- **PSExec ve WMI komutlarından işlem oluşturma**  
  **Varsayılan**: Yapılandırılmamış  
  [Exploit Guard belgeleri](https://go.microsoft.com/fwlink/?linkid=874500)  

  - **Yapılandırılmadı**  
  - **Blok** -PSExec ve WMI komutlarından kaynaklanan işlem oluşturma işlemlerini engelleyin.  
  
  - **Yalnızca denetim**  

- **USB’den çalışan güvenilmeyen ve imzasız işlemler**  
  **Varsayılan**: Yapılandırılmamış  
  [Exploit Guard belgeleri](https://go.microsoft.com/fwlink/?linkid=874502)    

  - **Yapılandırılmadı**  
  - **Engelle** -USB 'den çalıştırılan güvenilmeyen ve imzasız işlem engelle.  
  - **Yalnızca denetim**  
  
- **Bir yaygınlık, yaş veya güvenilenler listesi kriterine uymayan yürütülebilir dosyalar**  
  **Varsayılan**: Yapılandırılmamış  
  [Exploit Guard belgeleri](https://go.microsoft.com/fwlink/?linkid=874503)    

  - **Yapılandırılmadı**  
  - **Blok** blokları, bir Preter, Age veya güvenilir liste ölçütlerine uymadığı müddetçe yürütülebilir dosyaların çalıştırılmasını engeller.  
  - **Yalnızca denetim**  

#### <a name="rules-to-prevent-email-threats"></a>E-posta tehditlerini önlemek için kurallar  

E-posta tehditlerini önlemeye yardımcı olmak için aşağıdakileri engelleyin:  

- **E-postadan (web posta/posta istemcisi) gelen yürütülebilir içeriklerin (exe, dll, ps, js, vbs vb.) yürütülmesi**  
  **Varsayılan**: Yapılandırılmamış  
  [Exploit Guard belgeleri](https://go.microsoft.com/fwlink/?linkid=872980)  

  - **Yapılandırılmadı**  
  - **Block** -email (exe, dll, PS, js, vbs, vb.), e-postadan (Webmail/mail-Client) bırakılan yürütülebilir içeriklerin (exe, dll, PS  
  - **Yalnızca denetim**  

#### <a name="rules-to-protect-against-ransomware"></a>Fidye yazılımlarına karşı korunmak için kurallar  

- **Gelişmiş fidye yazılımı koruması**  
  Varsayılanını  Yapılandırılmamış  
  [Exploit Guard belgeleri](https://go.microsoft.com/fwlink/?linkid=874504)  

  - **Yapılandırılmadı**  
  - **Enable** -agresif fidye yazılımı korumasını kullanın.  
  - **Yalnızca denetim**  

#### <a name="attack-surface-reduction-exceptions"></a>Saldırı Yüzeyi Azaltma özel durumları

- **Saldırı yüzeyi azaltma kurallarından dışlanacak dosya ve klasör**  
  Defender CSP: [Ksurfacereductiononlydışlamalar](https://go.microsoft.com/fwlink/?linkid=872981)  

  - Saldırı yüzeyi azaltma kurallarından çıkarılacak dosya ve klasörleri içeren bir. csv dosyasını **Içeri aktarın** .  
  - Yerel dosya veya klasörleri el ile **ekleyin** .  

> [!IMPORTANT]  
> LOB Win32 uygulamalarının düzgün yüklenmesine ve yürütülmesine izin vermek için, kötü amaçlı yazılımdan koruma ayarları aşağıdaki dizinlerin taranmasını hariç tutmalıdır:  
> **X64 istemci makinelerde**:  
> *C:\Program Files (x86) \Microsoft Intune Management Extension\Content*  
> *C:\windows\ımecache*  
>  
> **X86 istemci makinelerde**:  
> *C:\Program Files\Microsoft Intune yönetim Extension\Content*  
> *C:\windows\ımecache*  

### <a name="controlled-folder-access"></a>Denetlenen klasör erişimi  

Fidye yazılımı gibi kötü amaçlı uygulamalardan ve tehditlerden [değerli verileri korumaya](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/controlled-folders-exploit-guard) yardımcı olun.  

- **Klasör koruması**  
  **Varsayılan**: Yapılandırılmamış  
  Defender CSP: [EnableControlledFolderAccess](https://go.microsoft.com/fwlink/?linkid=872614)  

  Dosya ve klasörleri kötü amaçlı uygulamaların yetkisiz değişikliklerinden korur.  

  - **Yapılandırılmadı**  
  - **Etkinleştirebilir**  
  - **Yalnızca denetim**  
  - **Disk değişikliğini engelle**  
  - **Disk değişikliğini denetleme**  

  *Yapılandırılmadı*dışında bir yapılandırma seçtiğinizde şunları yapılandırabilirsiniz:  
  - **Korumalı klasörlere erişimi olan uygulamaların listesi**  
    Defender CSP: [ControlledFolderAccessAllowedApplications](https://go.microsoft.com/fwlink/?linkid=872616)  

    - Uygulama listesi içeren bir. csv dosyasını **Içeri aktarın** .  
    - Uygulamaları bu listeye el ile **ekleyin** .  

  - **Korunması gereken ek klasörlerin listesi**  
    Defender CSP: [ControlledFolderAccessProtectedFolders](https://go.microsoft.com/fwlink/?linkid=872617)  

    - Klasör listesi içeren bir. csv dosyasını **Içeri aktarın** .  
    - Klasörleri bu listeye el ile **ekleyin** .  

### <a name="network-filtering"></a>Ağ filtreleme  

Herhangi bir uygulamadan gelen giden bağlantıları, düşük itibarlı sahip IP adreslerine veya etki alanlarına engelleyin. Ağ filtreleme hem denetim hem de engelleme modunda desteklenir.  

- **Ağ koruması**  
  **Varsayılan**: Yapılandırılmamış  
  Defender CSP: [EnableNetworkProtection](https://go.microsoft.com/fwlink/?linkid=872618)  

  Bu ayarın amacı, kimlik avı dolandırıcılığı, yararlanma siteleri ve Internet 'teki kötü amaçlı içeriklere erişimi olan uygulamalardan son kullanıcıları korumaktır. Ayrıca, üçüncü taraf tarayıcıların tehlikeli sitelere bağlanmasını engeller.  

  - **Yapılandırılmadı** -bu özelliği devre dışı bırakın. Kullanıcıların ve uygulamaların tehlikeli etki alanlarına bağlantısı engellenmiyor. Yöneticiler bu etkinliği Windows Defender Güvenlik Merkezi 'nde göremez.  
  - **Etkinleştirin** -ağ korumasını açın ve kullanıcıların ve uygulamaların tehlikeli etki alanlarına bağlanmasını engelleyin. Yöneticiler, bu etkinliği Windows Defender Güvenlik Merkezi 'nde görebilir.  
  - **Yalnızca denetim**:-kullanıcıların ve uygulamaların tehlikeli etki alanlarına bağlanması engellenmez. Yöneticiler, bu etkinliği Windows Defender Güvenlik Merkezi 'nde görebilir.  

### <a name="exploit-protection"></a>Exploit protection  
 

- **XML 'yi karşıya yükle**  
  **Varsayılan**: *Yapılandırılmadı*  

  [Cihazların kötüye kullanımını korumak](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)üzere Exploit Protection 'ı kullanmak için, istediğiniz sistem ve uygulama azaltma ayarlarını IÇEREN bir XML dosyası oluşturun. XML dosyasını oluşturmak için iki yöntem vardır:  

  - *PowerShell* - *Get-processhafifletme*, *set-Processazaltma*ve *ConvertTo-ProcessMitigationPolicy* PowerShell cmdlet 'lerinden bir veya daha fazlasını kullanın. Cmdlet'ler risk azaltma ayarlarını yapılandırır ve bunların XML gösterimini dışarı aktarır.  

  - *Windows Defender Güvenlik Merkezi kullanıcı arabirimi* -Windows Defender Güvenlik Merkezi 'Nde, uygulama & tarayıcısı denetimi ' ne tıklayın ve ardından, yararlanma korumasını bulmak için ortaya çıkan ekranın en altına gidin. Önce Sistem ayarları ve Program ayarları sekmelerini kullanarak risk azaltma ayarlarını yapılandırın. Daha sonra bunların bir XML temsilini dışarı aktarmak için ekranın altında yer alan Dışarı aktarma ayarları bağlantısını bulun.  

- **Exploit Protection arabirimini Kullanıcı düzenlemesi**  
  **Varsayılan**: Yapılandırılmamış  
  Patıguard CSP: [Patıprotectionsettings](https://go.microsoft.com/fwlink/?linkid=872887)  


  - **Block** -bellek, denetim akışı ve ilke kısıtlamalarını yapılandırmanıza olanak tanıyan bir XML dosyasını karşıya yükleyin. XML dosyasındaki ayarlar bir uygulamanın açıklarından yararlanılmasını engellemek için kullanılabilir.  
  - **Yapılandırılmadı** -özel yapılandırma kullanılmıyor.  

## <a name="windows-defender-application-control"></a>Windows Defender Uygulama Denetimi  

Tarafından denetlenmesi gereken ya da Windows Defender uygulama denetimi tarafından çalıştırılacak şekilde güvenilen ek uygulamalar seçin. Windows mağazasındaki Windows bileşenlerinin ve tüm uygulamaların çalıştırılmasına otomatik olarak güvenilir.  


- **Uygulama denetimi kod bütünlüğü ilkeleri**  
  **Varsayılan**: Yapılandırılmamış  
   'SINI [AppLocker CSP](https://go.microsoft.com/fwlink/?linkid=874543)  

  - **Zorla** -kullanıcılarınızın cihazları için uygulama denetimi kod bütünlüğü ilkeleri ' ni seçin.  
  
    Bir cihazda etkinleştirildikten sonra, uygulama denetimi yalnızca modu *yalnızca denetim*olarak *zorla* değiştirilerek devre dışı bırakılabilir. Modun *Zorla*’dan *Yapılandırılmadı*’ya değiştirilmesi, Uygulama Denetimi’nin atanmış cihazlarda zorlanmaya devam etmesiyle sonuçlanır.  

  - **Yapılandırılmadı** -uygulama denetimi cihazlara eklenmez. Ancak, önceden eklenmiş olan ayarlar atanan cihazlarda zorlanmaya devam eder. 
 
  - **Yalnızca denetim** -uygulamalar engellenmiyor. Tüm olaylar yerel istemci günlüklerine kaydedilir.  

## <a name="windows-defender-credential-guard"></a>Windows Defender Credential Guard  

Windows Defender Credential Guard kimlik bilgileri hırsızlığı saldırılarına karşı korur. Gizli dizileri yalnızca ayrıcalıklı sistem yazılımlarının erişebileceği şekilde yalıtır.  

- **Credential Guard**  
  **Varsayılan**: Devre Dışı Bırak  
  [DeviceGuard CSP 'si](https://go.microsoft.com/fwlink/?linkid=872424)  

  - **Devre dışı bırak** -daha önce **UEFI kilidi olmadan etkin** özelliği açık ise, Credential Guard 'ı uzaktan devre dışı bırakın.  

  - **UEFI kilidi Ile etkinleştir** -Credential Guard, bir kayıt defteri anahtarı veya Grup İlkesi kullanılarak uzaktan devre dışı bırakılamaz.  

    > [!NOTE]
    > Bu ayarı kullanırsanız ve daha sonra Credential Guard'ı devre dışı bırakmak isterseniz, Grup İlkesi'ni **Devre Dışı** olarak ayarlamalısınız. Ayrıca, UEFI yapılandırma bilgilerini her bilgisayardan fiziksel olarak temizleyin. UEFI yapılandırması devam ettiği sürece, Credential Guard etkindir.  

  - **UEFI kilidi olmadan etkinleştir** -Grup İlkesi kullanarak Credential Guard 'ın uzaktan devre dışı olmasına izin verir. Bu ayarı kullanan cihazların Windows 10 sürüm 1511'i veya daha yeni bir sürümü çalıştırıyor olması gerekir.  

  Credential Guard 'ı *etkinleştirdiğinizde* aşağıdaki gerekli özellikler de etkinleştirilir:  
  
  - **Sanallaştırma tabanlı güvenlik** DESTEKLI  
    Bir sonraki yeniden başlatma sırasında etkinleştirir. Sanallaştırma tabanlı güvenlik, güvenlik hizmetlerine destek sağlamak için Windows Hiper Yöneticisi'ni kullanır.  
  - **Dizin belleği erişimiyle güvenli önyükleme**  
    Güvenli önyükleme ve doğrudan bellek erişimi (DMA) korumalarının bulunduğu VBS 'yi etkinleştirir. DMA korumaları donanım desteği gerektirir ve yalnızca doğru yapılandırılmış cihazlarda etkinleştirilir.  

## <a name="windows-defender-security-center"></a>Windows Defender Güvenlik Merkezi  

Windows Defender Güvenlik Merkezi, diğer tüm özelliklerden ayrı bir uygulama veya işlem olarak çalışır. İşlem Merkezi aracılığıyla bildirimler gösterir. Durumu görmek için bir toplayıcı veya tek bir yer görevi görür ve özelliklerin her biri için bir yapılandırma çalıştırın. [Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) belgelerinden daha fazla bilgi edinin.  

### <a name="windows-defender-security-center-app-and-notifications"></a>Windows Defender Güvenlik Merkezi uygulaması ve bildirimleri  

Windows Defender Güvenlik Merkezi uygulamasının çeşitli alanlarına son kullanıcı erişimini engelleyin. Bir bölümü gizlemek, bu bölümle ilgili bildirimleri de engeller.  

- **Virüs ve tehdit koruması**  
  **Varsayılan**: Yapılandırılmamış  
  Windowssavunma Dersecuritycenter CSP: [DisableVirusUI](https://go.microsoft.com/fwlink/?linkid=873662)  

  Son kullanıcıların Windows Defender Güvenlik Merkezi 'nde virüs ve tehdit koruması alanını görüntüleyip görüntüleyemadığını yapılandırın. Bu bölümün gizlenmesi, virüs ve tehdit koruması ile ilgili tüm bildirimleri de engeller.  

  - **Yapılandırılmadı**  
  - **Gizlenecek**  

- **Fidye koruma**  
  **Varsayılan**: Yapılandırılmamış  
  Windowssavunma Dersecuritycenter CSP: [HideRansomwareDataRecovery](https://go.microsoft.com/fwlink/?linkid=873664)  

  Son kullanıcıların Windows Defender Güvenlik Merkezi 'nde fidye yazılımı koruma alanını görüntüleyip görüntüleyebir şekilde yapılandırılacağını yapılandırın. Bu bölümün gizlenmesi, fidye korumasıyla ilgili tüm bildirimleri de engeller.  

  - **Yapılandırılmadı**  
  - **Gizlenecek**  

- **Hesap koruması**  
  **Varsayılan**: Yapılandırılmamış  
  Windowssavunma Dersecuritycenter CSP: [Disableaccountprotectionuı](https://go.microsoft.com/fwlink/?linkid=873666)  

  Son kullanıcıların Windows Defender Güvenlik Merkezi 'nde hesap koruma alanını görüntüleyip görüntüleyebir şekilde yapılandırın. Bu bölümün gizlenmesi, hesap korumasıyla ilgili tüm bildirimleri de engeller.  

  - **Yapılandırılmadı**  
  - **Gizlenecek**  

- **Güvenlik duvarı ve ağ koruması**  
  **Varsayılan**: Yapılandırılmamış  
  Windowssavunma Dersecuritycenter CSP: [Disablenetworkuı](https://go.microsoft.com/fwlink/?linkid=873668)  

  Son kullanıcıların Windows Defender Güvenlik Merkezi 'nde güvenlik duvarı ve ağ koruması alanını görüntüleyip görüntüleyebir şekilde yapılandırın. Bu bölümün gizlenmesi, güvenlik duvarı ve ağ koruması ile ilgili tüm bildirimleri de engeller.  

  - **Yapılandırılmadı**  
  - **Gizlenecek**  

- **Uygulama ve tarayıcı denetimi**  
  **Varsayılan**: Yapılandırılmamış  
  Windowssavunma Dersecuritycenter CSP: [DisableAppBrowserUI](https://go.microsoft.com/fwlink/?linkid=873669)  

  Son kullanıcıların Windows Defender Güvenlik Merkezi 'nde uygulama ve tarayıcı denetim alanını görüntüleyip görüntüleyebir şekilde yapılandırın. Bu bölümün gizlenmesi, uygulama ve tarayıcı denetimiyle ilgili tüm bildirimleri de engeller.  

  - **Yapılandırılmadı**  
  - **Gizlenecek**  

- **Donanım koruması**  
  **Varsayılan**: Yapılandırılmamış  
  Windowssavunma Dersecuritycenter CSP: [Disabledevicesecurityuı](https://go.microsoft.com/fwlink/?linkid=873670)  

  Son kullanıcıların Windows Defender Güvenlik Merkezi 'nde donanım koruma alanını görüntüleyip görüntüleyebir şekilde yapılandırılacağını yapılandırın. Bu bölümün gizlenmesi, donanım korumasıyla ilgili tüm bildirimleri de engeller.  

  - **Yapılandırılmadı**  
  - **Gizlenecek**  

- **Cihaz performans ve sistem durumu**  
  **Varsayılan**: Yapılandırılmamış  
  Windowssavunma Dersecuritycenter CSP: [Disablehealthuı](https://go.microsoft.com/fwlink/?linkid=873671)  

  Son kullanıcıların Windows Defender Güvenlik Merkezi 'nde cihaz performansı ve sistem durumu alanını görüntüleyip görüntüleyebir şekilde yapılandırın. Bu bölümün gizlenmesi, cihaz performansı ve sistem durumu ile ilgili tüm bildirimleri de engeller.  
  
  - **Yapılandırılmadı**  
  - **Gizlenecek**  

- **Aile seçenekleri**  
  **Varsayılan**: Yapılandırılmamış  
  Windowssavunma Dersecuritycenter CSP: [DisableFamilyUI](https://go.microsoft.com/fwlink/?linkid=873673)  

  Son kullanıcıların Windows Defender Güvenlik Merkezi ' nde aile seçenekleri alanını görüntüleyip görüntüleyebir şekilde yapılandırın. Bu bölümün gizlenmesi, Aile seçenekleriyle ilgili tüm bildirimleri de engeller.  
  
  - **Yapılandırılmadı**  
  - **Gizlenecek**  

- **Uygulamanın görüntülenmekte olan alanlarından gelen bildirimler**  
  **Varsayılan**: Yapılandırılmamış  
  Windowssavunma Dersecuritycenter CSP: [DisableNotifications](https://go.microsoft.com/fwlink/?linkid=873675)  

  Son kullanıcılara görüntülenecek bildirimleri seçin. Kritik olmayan bildirimlere, Windows Defender Antivirus etkinliğinin özetleri ve taramalar tamamlandığında verilen bildirimler dahildir. Diğer tüm bildirimler kritik olarak kabul edilir.  

  - **Yapılandırılmadı**  
  - **Kritik olmayan bildirimleri engelle**  
  - **Tüm bildirimleri engelle**  

- **Sistem tepsisindeki Windows Güvenlik Merkezi simgesi**  
  **Varsayılan**: Yapılandırılmamış  

  Bildirim alanı denetiminin görüntüsünü yapılandırın. Bu ayarın etkili olması için kullanıcının oturumu kapatıp açması ya da bilgisayarı yeniden başlatması gerekir.  
  
  - **Yapılandırılmadı**  
  - **Gizlenecek**  

- **TPM 'YI temizle düğmesi**  
  **Varsayılan**: Yapılandırılmamış  

  TPM 'YI Temizle düğmesinin görüntülenmesini yapılandırın.  
  
  - **Yapılandırılmadı**  
  - **Dıı**  

- **TPM bellenim güncelleştirme uyarısı**  
  **Varsayılan**: Yapılandırılmamış  
  
  Güvenlik açığı bulunan bir bellenim algılandığında TPM güncelleştirme belleniminin görüntülenmesini yapılandırın.  

  - **Yapılandırılmadı**  
  - **Gizlenecek**  

- **Yetkisiz koruma**  
  **Varsayılan**: Yapılandırılmamış

  Cihazlarda devre dışı korumayı açın veya kapatın. Daha fazla koruma kullanmak için, [Microsoft Defender Gelişmiş tehdit koruması 'Nı Intune ile tümleştirmeniz](advanced-threat-protection.md)ve [Enterprise Mobility + Security E5 lisanslarına](licenses.md)sahip olmanız gerekir.  
  - **Yapılandırılmadı** -cihaz ayarlarında değişiklik yapılmadı.
  - **Etkin** -yetkisiz koruma açık ve cihazlarda kısıtlamalar zorlandı.
  - **Devre dışı** -yetkisiz koruma kapalı ve kısıtlamalar zorlanmaz.

### <a name="it-contact-information"></a>BT iletişim bilgileri  

Windows Defender Güvenlik Merkezi uygulaması ve uygulama bildirimlerinde gösterilecek BT iletişim bilgilerini sağlayın.  

**Uygulamada ve bildirimlerde göster**, **Yalnızca uygulamada göster**, **Yalnızca bildirimlerde göster** veya **Gösterme** seçeneklerinden birini seçebilirsiniz. **BT kuruluş adı** ile aşağıdaki iletişim seçeneklerinden en az birini girin:  


- **BT iletişim bilgileri**  
  **Varsayılan**: Gösterme  
  Windowssavunma Dersecuritycenter CSP: [EnableCustomizedToasts](https://go.microsoft.com/fwlink/?linkid=873676)  
  
  Son kullanıcılara BT iletişim bilgilerinin nerede görüntüleneceğini yapılandırın.  
  
  - **Uygulamada ve bildirimlerde görüntüle**  
  - **Yalnızca uygulamada görüntüle**  
  - **Yalnızca bildirimlerde görüntüle**  
  - **Gösterme**  

  Görüntülenecek şekilde yapılandırıldığında, aşağıdaki ayarları yapılandırabilirsiniz:  

  - **BT kuruluş adı**  
    **Varsayılan**: *Yapılandırılmadı*  
    Windowssavunma Dersecuritycenter CSP: [Tadı](https://go.microsoft.com/fwlink/?linkid=873677)  

  - **BT departmanı telefon numarası veya Skype kimliği**  
    **Varsayılan**: *Yapılandırılmadı*  
    Windowssavunma Dersecuritycenter CSP: [Numarası](https://go.microsoft.com/fwlink/?linkid=873678) 

  - **BT departmanı e-posta adresi**  
    **Varsayılan**: *Yapılandırılmadı*  
    Windowssavunma Dersecuritycenter CSP: [E-posta](https://go.microsoft.com/fwlink/?linkid=873679)  

  - **BT destek web sitesi URL’si**  
    **Varsayılan**: *Yapılandırılmadı*  
    Windowssavunma Dersecuritycenter CSP: [URL](https://go.microsoft.com/fwlink/?linkid=873680)  
 
## <a name="local-device-security-options"></a>Yerel cihaz güvenliği seçenekleri  

Windows 10 cihazlarında yerel güvenlik ayarlarını yapılandırmak için bu seçenekleri kullanın.  

### <a name="accounts"></a>Hesaplar  

- **Yeni Microsoft hesapları Ekle**  
  **Varsayılan**: Yapılandırılmamış  
  LocalPoliciesSecurityOptions CSP: [Accounts_BlockMicrosoftAccounts](https://go.microsoft.com/fwlink/?linkid=867916)  


  - **Blok** Kullanıcıların cihaza yeni Microsoft hesapları eklemesini engelleyin.  
  - **Yapılandırılmadı** -kullanıcılar cihazda Microsoft hesaplarını kullanabilir.  

- **Parola olmadan uzaktan oturum açma**  
  **Varsayılan**: Yapılandırılmamış  
  LocalPoliciesSecurityOptions CSP: [Accounts_LimitLocalAccountUseOfBlankPasswordsToConsoleLogonOnly](https://go.microsoft.com/fwlink/?linkid=867890)  


   - **Engelle** -yalnızca boş parolalara sahip yerel hesapların cihazın klavyesini kullanarak oturum açmasını sağlar.  
   - **Yapılandırılmadı** -boş parolalara sahip yerel hesapların fiziksel cihaz dışındaki konumlardan oturum açmasını sağlar.  

#### <a name="admin"></a>Yönetici  

- **Yerel yönetici hesabı**  
  **Varsayılan**: Yapılandırılmamış  
  LocalPoliciesSecurityOptions CSP: [Accounts_LimitLocalAccountUseOfBlankPasswordsToConsoleLogonOnly](https://go.microsoft.com/fwlink/?linkid=867850)  


  - **Blok** Yerel yönetici hesabının kullanımını engelleyin.  
  - **Yapılandırılmadı**  

- **Yönetici hesabını yeniden adlandır**  
  **Varsayılan**: *Yapılandırılmadı*  
  LocalPoliciesSecurityOptions CSP: [Accounts_RenameAdministratorAccount](https://go.microsoft.com/fwlink/?linkid=867917)  
 

  "Administrator" hesabının güvenlik tanımlayıcısı (SID) ile ilişkilendirilecek farklı bir hesap adı tanımlayın.  

 #### <a name="guest"></a>Konuk  

- **Konuk hesabı**  
  **Varsayılan**: Yapılandırılmamış  
  LocalPoliciesSecurityOptions CSP: [LocalPoliciesSecurityOptions](https://go.microsoft.com/fwlink/?linkid=867853)  

  - **Engelle** -Konuk hesabının kullanımını engelleyin.  
  - **Yapılandırılmadı**  

- **Konuk hesabını yeniden adlandır**  
  **Varsayılan**: *Yapılandırılmadı*  
  LocalPoliciesSecurityOptions CSP: [Accounts_RenameGuestAccount](https://go.microsoft.com/fwlink/?linkid=867918)  
  
  "Konuk" hesabının güvenlik tanımlayıcısı (SID) ile ilişkilendirilecek farklı bir hesap adı tanımlayın.  

### <a name="devices"></a>Cihazlar  

- **Oturum açmadan cihazı çıkar**  
  **Varsayılan**: Yapılandırılmamış  
  LocalPoliciesSecurityOptions CSP: [Devices_AllowUndockWithoutHavingToLogon](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions#localpoliciessecurityoptions-devices-allowundockwithouthavingtologon)  

  
  - **Engelle** -kullanıcılar, cihazı güvenle çıkarmak için sabitlenmiş bir taşınabilir cihazın fiziksel çıkarma düğmesine basabilir.  
  - **Yapılandırılmadı** -bir kullanıcının cihazda oturum açması ve cihazı yuvadan çıkarmak için izin alması gerekir.  

- **Paylaşılan yazıcılar için yazıcı sürücülerini yükler**  
  **Varsayılan**:  Yapılandırılmamış  
  LocalPoliciesSecurityOptions CSP: [Devices_PreventUsersFromInstallingPrinterDriversWhenConnectingToSharedPrinters](https://go.microsoft.com/fwlink/?linkid=867921)  


  - **Etkin** -herhangi bir Kullanıcı, paylaşılan bir yazıcıya bağlanın bir parçası olarak bir yazıcı sürücüsü yükleyebilir.  
  - **Yapılandırılmadı** -yalnızca Yöneticiler, paylaşılan bir yazıcıya bağlanma kapsamında bir yazıcı sürücüsü yükleyebilir.  

- **Yerel etkin kullanıcıya CD-ROM erişimini kısıtla**  
  **Varsayılan**:  Yapılandırılmamış  
  'SINI [Devices_RestrictCDROMAccessToLocallyLoggedOnUserOnly](https://go.microsoft.com/fwlink/?linkid=867922)  


  - **Etkin** -yalnızca etkileşimli oturum açan kullanıcı CD-ROM medyasını kullanabilir. Bu ilke etkinse ve kimse etkileşimli olarak oturum açmamışsa CD-ROM’a ağ üzerinden erişilir.  
  - **Yapılandırılmadı** -herkesin CD-ROM ' a erişimi vardır.  

- **Çıkarılabilir medyayı biçimlendirme ve çıkarma**  
  **Varsayılan**: Yöneticiler  
  'SINI [Devices_AllowedToFormatAndEjectRemovableMedia](https://go.microsoft.com/fwlink/?linkid=867920)  
 

  Çıkarılabilir NTFS medyasını biçimlendirmeye ve çıkarmaya izin verilen kişileri tanımlayın:  
  - **Yapılandırılmadı**  
  - **Yöneticiler**  
  - **Yöneticiler ve Yetkili Kullanıcılar**  
  - **Yöneticiler ve Etkileşimli Kullanıcılar**  

### <a name="interactive-logon"></a>Etkileşimli Oturum Açma  

- **Ekran koruyucusu etkinleşene kadar kilit ekranının işlem yapılmayan dakika sayısı**  
  **Varsayılan**: *Yapılandırılmadı*  
  LocalPoliciesSecurityOptions CSP: [InteractiveLogon_MachineInactivityLimit](https://go.microsoft.com/fwlink/?linkid=867891)  


  Ekran koruyucusu başlatılana kadar etkileşimli masaüstü oturum açma ekranında işlem yapılmayan en uzun süreyi dakika cinsinden girin. (**0** - **99999**)  

- **Oturum açmak için CTRL + ALT + DEL gerektir**  
  **Varsayılan**: Yapılandırılmamış  
  LocalPoliciesSecurityOptions CSP: [InteractiveLogon_DoNotRequireCTRLALTDEL](https://go.microsoft.com/fwlink/?linkid=867951)  


  - **Etkinleştir** -Ctrl + Alt + Del tuşlarına basarak kullanıcıların oturum açması gerekmez.  
  - **Yapılandırılmadı** Kullanıcıların Windows 'da oturum açmadan önce CTRL + ALT + DEL tuşlarına basması gerekir.  

- **Akıllı kart kaldırma davranışı**  
  **Varsayılan**: İş istasyonunu kilitle   
  LocalPoliciesSecurityOptions CSP: [InteractiveLogon_SmartCardRemovalBehavior](https://go.microsoft.com/fwlink/?linkid=868437)  
    
  Oturum açmış bir kullanıcının akıllı kartı, akıllı kart okuyucusundan kaldırıldığında ne olacağını belirler. Seçenekleriniz şunlardır:  

  - **Iş Istasyonunu kilitleme** -akıllı kart kaldırıldığında iş istasyonu kilitlenir. Bu seçenek kullanıcıların akıllı kartlarını alarak alandan uzaklaşmasına ve yine de korumalı oturumu sürdürmesine olanak tanır.  
  - **Eylem yok**  
  - **Kapanmaya zorla** -akıllı kart kaldırıldığında Kullanıcı oturumu otomatik olarak kapatılır.  
  - Akıllı kartın **Uzak Masaüstü Hizmetleri oturumu** kaldırma işlemi kullanıcının oturumunu kapatmadan oturumun bağlantısını keser. Bu seçenek kullanıcının daha sonra yeniden oturum açmak zorunda kalmadan akıllı kartı takıp oturumu devam ettirmesine veya akıllı kart okuyucuyla donatılmış başka bir bilgisayarda bunu yapmasına olanak tanır. Yerel bir oturum söz konusuysa, bu ilke İş İstasyonunu Kilitle ilkesiyle tam olarak aynı işlevi görür.  

#### <a name="display"></a>Görüntüle  

- **Kilit ekranında Kullanıcı bilgileri**  
  **Varsayılan**: Yapılandırılmamış  
  LocalPoliciesSecurityOptions CSP: [InteractiveLogon_DisplayUserInformationWhenTheSessionIsLocked](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions#localpoliciessecurityoptions-interactivelogon-displayuserinformationwhenthesessionislocked)  

  Oturum kilitlendiğinde görüntülenen kullanıcı bilgilerini yapılandırın. Yapılandırılmazsa, kullanıcı görünen adı, etki alanı ve kullanıcı adı gösterilir.  

  - **Yapılandırılmadı**  
  - **Kullanıcı görünen adı, etki alanı ve kullanıcı adı**  
  - **Yalnızca kullanıcı görünen adı**  
  - **Kullanıcı bilgilerini görüntüleme**  

- **Son oturum açan kullanıcıyı gizle**  
  **Varsayılan**: Yapılandırılmamış  
  LocalPoliciesSecurityOptions CSP: [InteractiveLogon_DoNotDisplayLastSignedIn](https://go.microsoft.com/fwlink/?linkid=868437)  
  
  
  - **Etkinleştirin** -Kullanıcı adını gizleyin.  
  - **Yapılandırılmadı** -Son Kullanıcı adını göster.  

- **Varsayılan oturum açma**
  sırasında Kullanıcı adını gizle: Yapılandırılmadı  
  LocalPoliciesSecurityOptions CSP: [InteractiveLogon_DoNotDisplayUsernameAtSignIn](https://go.microsoft.com/fwlink/?linkid=867959)  

  
  - **Etkinleştirin** -Kullanıcı adını gizleyin.  
  - **Yapılandırılmadı** -Son Kullanıcı adını göster.  

- **Oturum açma iletisi başlığı**  
  **Varsayılan**: *Yapılandırılmadı*  
  LocalPoliciesSecurityOptions CSP: [InteractiveLogon_MessageTitleForUsersAttemptingToLogOn](https://go.microsoft.com/fwlink/?linkid=867964)  

  Oturum açan kullanıcılar için ileti başlığını ayarlayın.  

- **Oturum açma iletisi metni**  
  **Varsayılan**: *Yapılandırılmadı*  
  LocalPoliciesSecurityOptions CSP: [InteractiveLogon_MessageTextForUsersAttemptingToLogOn](https://go.microsoft.com/fwlink/?linkid=867962)  

  Oturum açan kullanıcılar için ileti metnini ayarlayın.  
  
### <a name="network-access-and-security"></a>Ağ erişimi ve güvenlik

- **Adlandırılmış kanallara ve Paylaşımlara anonim erişim**  
  **Varsayılan**: Yapılandırılmamış  
  LocalPoliciesSecurityOptions CSP: [NetworkAccess_RestrictAnonymousAccessToNamedPipesAndShares](https://go.microsoft.com/fwlink/?linkid=868432)  

  - **Yapılandırılmadı** -paylaşıma ve adlandırılmış kanal ayarlarına anonim erişimi kısıtla. Anonim olarak erişilebilen ayarlar için geçerlidir.  
  - **Engelle** -Bu ilkeyi devre dışı bırakarak anonim erişim kullanılabilir hale getirir.  

- **SAM hesaplarının anonim numaralandırması**  
  **Varsayılan**: Yapılandırılmamış  
  LocalPoliciesSecurityOptions CSP: [NetworkAccess_DoNotAllowAnonymousEnumerationOfSAMAccounts](https://go.microsoft.com/fwlink/?linkid=868434)  
  
  - **Yapılandırılmadı** -anonım kullanıcılar Sam hesaplarını numaralandırabilirler.  
  - **Engelle** -Sam hesaplarının anonim numaralandırılmasına engel olacak.  

- **SAM hesaplarının ve paylaşımlarının anonim numaralandırması**  
  **Varsayılan**: Yapılandırılmamış  
  LocalPoliciesSecurityOptions CSP: [NetworkAccess_DoNotAllowAnonymousEnumerationOfSamAccountsAndShares](https://go.microsoft.com/fwlink/?linkid=868435)  

  - **Yapılandırılmadı** -anonim kullanıcılar etki alanı hesaplarının ve ağ paylaşımlarının adlarını numaralandırabilirler.  
  - **Engelle** -Sam hesaplarının ve paylaşımlarının adsız numaralandırılmasına engel olacak. 

- **Parola değiştiğinde depolanan LAN Yöneticisi karma değeri**  
  **Varsayılan**: Yapılandırılmamış  
  LocalPoliciesSecurityOptions CSP: [NetworkSecurity_DoNotStoreLANManagerHashValueOnNextPasswordChange](https://go.microsoft.com/fwlink/?linkid=868431)  
   
  Parolaların karma değerinin parolanın bir sonraki değiştirildiği sırada saklanıp saklanmadığını belirleme. 
  - **Yapılandırılmadı** -karma değeri depolanmaz  
  - **Engelle** -lan YÖNETICISI (LM), yeni parolanın karma değerini depolar.  

- **PKU2U kimlik doğrulama istekleri**  
  **Varsayılan**: Yapılandırılmamış  
  LocalPoliciesSecurityOptions CSP: [NetworkSecurity_AllowPKU2UAuthenticationRequests](https://go.microsoft.com/fwlink/?linkid=867892)  

  - **Yapılandırılmadı**-PU2U isteklerine izin ver.  
  - Cihaza **blok** blok PKU2U kimlik doğrulama istekleri.  

- **Uzaktan RPC bağlantılarını SAM ile kısıtla**  
  **Varsayılan**: Yapılandırılmamış  
  LocalPoliciesSecurityOptions CSP: [NetworkAccess_RestrictClientsAllowedToMakeRemoteCallsToSAM](https://go.microsoft.com/fwlink/?linkid=867893)  
  
  - **Yapılandırılmadı** -varsayılan güvenlik tanımlayıcısını kullanın, bu, kullanıcıların ve grupların Sam 'A uzak RPC çağrıları yapmasına izin verebilir.
  - **Izin ver** -kullanıcıların ve grupların, Kullanıcı hesaplarını ve parolaları depolayan Güvenlik Hesapları Yöneticisi 'NE (Sam) uzak RPC çağrıları yapmasını engelle. Ayrıca **Izin ver** , varsayılan güvenlik tanımlayıcısı tanım DILI (SDDL) dizesini, bu uzaktan aramaları yapmak için kullanıcılara ve gruplara açıkça izin vermek veya reddetmek üzere değiştirmenize imkan tanır.  

    - **Güvenlik tanımlayıcısı**  
      **Varsayılan**: *Yapılandırılmadı*  
    
- **NTLM SSP tabanlı Istemciler Için en düşük oturum güvenliği**  
  **Varsayılan**: Yok.  
  LocalPoliciesSecurityOptions CSP: [NetworkSecurity_MinimumSessionSecurityForNTLMSSPBasedClients](https://aka.ms/policy-csp-localpoliciessecurityoptions-networksecurity-minimumsessionsecurityforntlmsspbasedclients)  
  
  Bu güvenlik ayarı, bir sunucunun 128 bitlik şifreleme ve/veya NTLMv2 oturum güvenliği için anlaşma sağlamasına izin verir.  

  - **Yok.**  
  - **NTLMv2 oturum güvenliği gerektir**  
  - **128 bit şifreleme gerektir**  
  - **Ntlmv2'yi ve 128 bit şifreleme**  
 
- **NTLM SSP tabanlı sunucu Için en düşük oturum güvenliği**  
  **Varsayılan**: Yok.  
  LocalPoliciesSecurityOptions CSP: [NetworkSecurity_MinimumSessionSecurityForNTLMSSPBasedServers](https://aka.ms/policy-csp-localpoliciessecurityoptions-networksecurity-minimumsessionsecurityforntlmsspbasedservers)  

  Bu güvenlik ayarı, ağ oturum açmaları için hangi sınama/yanıt kimlik doğrulama protokolünün kullanıldığını belirler.  

  - **Yok.**  
  - **NTLMv2 oturum güvenliği gerektir**  
  - **128 bit şifreleme gerektir**  
  - **Ntlmv2'yi ve 128 bit şifreleme**  

- **LAN Manager kimlik doğrulama düzeyi**  
  **Varsayılan**: LM ve NTLM  
  LocalPoliciesSecurityOptions CSP: [NetworkSecurity_LANManagerAuthenticationLevel](https://aka.ms/policy-csp-localpoliciessecurityoptions-lanmanagerauthenticationlevel)  


  - **LM ve NTLM**  
  - **LM, NTLM ve NTLMv2**  
  - **NT**  
  - **Kullanır**  
  - **LM ve LM değil**  
  - **LM veya NTLM değil, NTLMv2**  
  
- **Güvenli olmayan konuk oturum açmalar**  
  **Varsayılan**: Yapılandırılmamış  
  LanmanWorkstation CSP: [LanmanWorkstation](https://aka.ms/policy-csp-lanmanworkstation-enableinsecureguestlogons)  

  Bu ayarı etkinleştirirseniz, SMB istemcisi güvenli olmayan konuk oturum açmaları reddeder.  

  - **Yapılandırılmadı**  
  - **Engelle** -SMB istemcisi güvenli olmayan konuk oturum açmaları reddeder.  

### <a name="recovery-console-and-shutdown"></a>Kurtarma konsolu ve kapatma  

- **Kapatılırken sanal bellek disk belleği dosyasını temizle**  
  **Varsayılan**: Yapılandırılmamış  
   LocalPoliciesSecurityOptions CSP: [Shutdown_ClearVirtualMemoryPageFile](https://go.microsoft.com/fwlink/?linkid=867914)  


  - **Etkinleştir** -Cihaz kapatıldığında sanal bellek disk belleği dosyasını temizle.  
  - **Yapılandırılmadı** -sanal belleği temizlemez.  

- **Oturum açma olmadan Kapat**  
  **Varsayılan**: Yapılandırılmamış  
  LocalPoliciesSecurityOptions CSP: [Shutdown_AllowSystemToBeShutDownWithoutHavingToLogOn](https://go.microsoft.com/fwlink/?linkid=867912)  

  
  - **Engelle** -Windows oturum açma ekranında Kapat seçeneğini gizleyin. Kullanıcıların cihazda oturum açıp ve ardından cihazı kapatması gerekir.  
  - **Yapılandırılmadı** -kullanıcıların Windows oturum açma ekranından cihazı kapatmasına izin ver.  

### <a name="user-account-control"></a>Kullanıcı hesap denetimi  

- **Güvenli konum olmadan UıA bütünlüğü**  
  **Varsayılan**: Yapılandırılmadı  
  LocalPoliciesSecurityOptions CSP: [UserAccountControl_OnlyElevateUIAccessApplicationsThatAreInstalledInSecureLocations](https://go.microsoft.com/fwlink/?linkid=867897)  
  
  - **Blok** -dosya sisteminde güvenli bir konumda bulunan uygulamalar yalnızca UIAccess bütünlüğüyle çalışır.  
  - **Yapılandırılmadı** -uygulamalar dosya sisteminde güvenli bir konumda olmasa bile, uygulamaların UIAccess bütünlüğüyle çalışmasına olanak sağlar.  

- **Dosya ve kayıt defteri yazma başarısızlıklarını Kullanıcı başına konumlara sanallaştırın**  
  **Varsayılan**: Yapılandırılmadı  
  LocalPoliciesSecurityOptions CSP: [UserAccountControl_VirtualizeFileAndRegistryWriteFailuresToPerUserLocations](https://go.microsoft.com/fwlink/?linkid=867900)  

  - **Etkin** -korumalı konumlara veri yazan uygulamalar başarısız olur.  
  - **Yapılandırılmadı** -uygulama yazma sorunları, dosya sistemi ve kayıt defteri için tanımlı kullanıcı konumlarına çalışma zamanında yeniden yönlendirilir.  

- **Yalnızca imzalı ve doğrulanan yürütülebilir dosyaları yükselt**  
  **Varsayılan**: Yapılandırılmadı  
  LocalPoliciesSecurityOptions CSP: [UserAccountControl_OnlyElevateUIAccessApplicationsThatAreInstalledInSecureLocations](https://go.microsoft.com/fwlink/?linkid=867965)  

  - **Etkin** -çalıştırılabilmesi için önce yürütülebilir bir dosya için PKI sertifika yolu doğrulamasını zorunlu hale getirebilirsiniz.  
  - **Yapılandırılmadı** -yürütülebilir bir dosyanın ÇALıŞTıRıLABILMESI için PKI sertifika yolu doğrulamasını zorlamaz.  

#### <a name="uia-elevation-prompt-behavior"></a>UıA yükseltme istemi davranışı  

- **Yöneticiler için yükseltme istemi**  
  **Varsayılan**: Windows dışı ikili dosyalar için onay iste  
  LocalPoliciesSecurityOptions CSP: [UserAccountControl_BehaviorOfTheElevationPromptForAdministrators](https://go.microsoft.com/fwlink/?linkid=867895)  

  Yönetici onay modu 'nda Yöneticiler için yükseltme isteminin davranışını tanımlayın.  

  - **Yapılandırılmadı**  
  - **İstem olmadan yükselt**  
  - **Güvenli masaüstünde kimlik bilgileri iste**  
  - **Kimlik bilgileri iste**  
  - **Onay iste**  
  - **Windows dışı ikili dosyalar için onay iste**  


- **Standart kullanıcılar için yükseltme istemi**  
  **Varsayılan**: Kimlik bilgileri iste  
  LocalPoliciesSecurityOptions CSP: [UserAccountControl_BehaviorOfTheElevationPromptForStandardUsers](https://go.microsoft.com/fwlink/?linkid=867896)  

  Standart kullanıcılar için yükseltme isteminin davranışını tanımlayın.  

  - **Yapılandırılmadı**  
  - **Yükseltme isteklerini otomatik olarak reddet**  
  - **Güvenli masaüstünde kimlik bilgileri iste**  
  - **Kimlik bilgileri iste**  

- **Kullanıcı etkileşimi istemlerini kullanıcının etkileşimli masaüstüne yönlendir**  
  **Varsayılan**: Yapılandırılmadı  
  LocalPoliciesSecurityOptions CSP: [UserAccountControl_SwitchToTheSecureDesktopWhenPromptingForElevation](https://go.microsoft.com/fwlink/?linkid=867899)  


  - **Etkin** -tüm yükseltme istekleri, güvenli masaüstü yerine etkileşimli kullanıcının masaüstüne gider. Yöneticiler ve standart kullanıcılar için herhangi bir istem davranışı ilke ayarı kullanılır.  
  - **Yapılandırılmadı** -tüm yükseltme isteklerini zorla Yöneticiler ve standart kullanıcılar için herhangi bir istem davranışı ilke ayarlarından bağımsız olarak güvenli masaüstüne gidin.

- **Uygulama yüklemeleri için yükseltilmiş istem**  
  **Varsayılan**: Yapılandırılmadı  
  LocalPoliciesSecurityOptions CSP: [UserAccountControl_DetectApplicationInstallationsAndPromptForElevation](https://go.microsoft.com/fwlink/?linkid=867901)  

   - **Etkin** -uygulama yükleme paketleri algılanmaz veya yükseltme istenmez.
   - **Yapılandırılmadı** -bir uygulama yükleme paketi yükseltilmiş ayrıcalıklar gerektirdiğinde kullanıcılardan Yönetici Kullanıcı adı ve parola istenir.

- **Güvenli Masaüstü olmadan UıA yükseltme istemi**  
  **Varsayılan**: Yapılandırılmadı  
  LocalPoliciesSecurityOptions CSP: [UserAccountControl_AllowUIAccessApplicationsToPromptForElevation](https://go.microsoft.com/fwlink/?linkid=867894)  

- **Enable** -UIAccess uygulamalarının güvenli masaüstü kullanmadan yükseltme isteminde bulunmasına izin verin.  
- **Yapılandırılmadı** -yükseltme istemleri güvenli bir masaüstü kullanır.  

#### <a name="admin-approval-mode"></a>Yönetici onay modu  

- **Yerleşik yönetici Için yönetici onay modu**  
  **Varsayılan**: Yapılandırılmadı  
  LocalPoliciesSecurityOptions CSP: [UserAccountControl_UseAdminApprovalMode](https://go.microsoft.com/fwlink/?linkid=867902)  

  - **Etkin** -yerleşik yönetici hesabının Yönetici onay modunu kullanmasına izin verin. Ayrıcalık gerektiren herhangi bir işlem, kullanıcıdan işlemi onaylamasını ister.  
  - **Yapılandırılmadı** -tüm uygulamaları tam yönetici ayrıcalıklarıyla çalıştırır.  

- **Tüm yöneticileri yönetici onay modu 'nda Çalıştır**  
  **Varsayılan**: Yapılandırılmadı  
  LocalPoliciesSecurityOptions CSP: [UserAccountControl_RunAllAdministratorsInAdminApprovalMode](https://go.microsoft.com/fwlink/?linkid=867898)  


  - **Etkin**-yönetici onay modunu etkinleştirin.  
  - **Yapılandırılmadı** -yönetici onay modunu ve ılgılı tüm UAC ilkesi ayarlarını devre dışı bırakın.  

### <a name="microsoft-network-client"></a>Microsoft Ağ İstemcisi  

- **İletişimleri dijital olarak imzala (sunucu kabul ederse)**  
  **Varsayılan**: Yapılandırılmamış  
  LocalPoliciesSecurityOptions CSP: [MicrosoftNetworkClient_DigitallySignCommunicationsIfServerAgrees](https://go.microsoft.com/fwlink/?linkid=868423)  

  SMB istemcisinin SMB paket imzalamayı nasıl görüşdiğini belirler.  
  - **Engelle** -SMB istemcisi HIÇBIR şekilde SMB paket imzalamayı hiçbir şekilde görüşmez.
  - **Yapılandırılmadı** -Microsoft ağ istemcisi, oturum kurulumu SıRASıNDA sunucudan SMB paket imzalamayı çalıştırmasını ister. Sunucuda paket imzalama etkinleştirilirse, paket imzalama anlaşması yapılır.  

- **Üçüncü taraf SMB sunucularına şifrelenmemiş parola gönder**  
  **Varsayılan**: Yapılandırılmamış  
  LocalPoliciesSecurityOptions CSP: [MicrosoftNetworkClient_SendUnencryptedPasswordToThirdPartySMBServers](https://go.microsoft.com/fwlink/?linkid=868426)  


  - **Engelle** -sunucu ileti bloğu (SMB) yeniden yönlendiricisi, kimlik doğrulama sırasında parola şifrelemeyi desteklemeyen MICROSOFT olmayan SMB sunucularına düz metin parolaları gönderebilir.  
  - **Yapılandırılmadı** -düz metin parolalarının gönderilmesini engelleyin. Parolalar şifrelenir.  

- **İletişimleri dijital olarak imzala (her zaman)**  
  **Varsayılan**: Yapılandırılmamış  
  LocalPoliciesSecurityOptions CSP: [MicrosoftNetworkClient_DigitallySignCommunicationsAlways](https://go.microsoft.com/fwlink/?linkid=868425)  


  - **Etkinleştir** -sunucu, SMB paket imzasını kabul etmediği takdirde Microsoft ağ Istemcisi bir Microsoft ağ sunucusu ile iletişim kurmaz.  
  - **Yapılandırılmadı** -istemci ve sunucu arasında SMB paket imzalama işlemi yapılır.  

### <a name="microsoft-network-server"></a>Microsoft Ağ Sunucusu  
  
- **İletişimleri dijital olarak imzala (istemci kabul ederse)**  
  **Varsayılan**: Yapılandırılmamış  
  'SINI [MicrosoftNetworkServer_DigitallySignCommunicationsIfClientAgrees](https://go.microsoft.com/fwlink/?linkid=868429)  

  - **Etkinleştir** -Microsoft ağ sunucusu, istemci tarafından istenen SMB paket imzasını belirler. Başka bir deyişle, istemcide paket imzalama etkinleştirildiyse paket imzalama anlaşması yapılır.  
  - Yapılandırılmadı-SMB istemcisi hiçbir şekilde SMB paket imzasını hiçbir **şekilde görüşmez** .  

- **İletişimleri dijital olarak imzala (her zaman)**  
  **Varsayılan**: Yapılandırılmamış  
  'SINI [MicrosoftNetworkServer_DigitallySignCommunicationsAlways](https://go.microsoft.com/fwlink/?linkid=868428)  

  - **Etkinleştir** -ISTEMCI, SMB paket imzasını kabul etmediği takdirde Microsoft ağ sunucusu bir Microsoft ağ istemcisiyle iletişim kurmaz.  
  - **Yapılandırılmadı** -istemci ve sunucu arasında SMB paket imzalama işlemi yapılır.  

## <a name="xbox-services"></a>Xbox Hizmetleri

- **Xbox oyunu kaydet görevi**  
  **Varsayılan**: Yapılandırılmamış  
  'SINI [TaskScheduler/EnableXboxGameSaveTask](https://go.microsoft.com/fwlink/?linkid=875480)  
   
  Bu ayar, Xbox oyunu kaydet görevinin etkin veya devre dışı olduğunu belirler.  
  - **Etkinletir**
  - **Yapılandırılmadı**

- **Xbox donatı yönetim hizmeti**  
  **Varsayılan**: Elle  
  'SINI [SystemServices/Configurexboxaccessoryımanagementservicestartupmode](https://go.microsoft.com/fwlink/?linkid=875481)  

  Bu ayar, donatı Yönetimi hizmetinin başlangıç türünü belirler.  
  - **El ile**
  - **Otomatik**
  - **Devre dışı**

- **Xbox Live auth Manager hizmeti**  
  **Varsayılan**: Elle  
  'SINI [SystemServices/ConfigureXboxLiveAuthManagerServiceStartupMode](https://go.microsoft.com/fwlink/?linkid=875482)  
 
  Bu ayar, Live auth Manager hizmetinin başlangıç türünü belirler.  
  - **El ile**
  - **Otomatik**
  - **Devre dışı**
 
- **Xbox Live Game kaydetme hizmeti**  
  **Varsayılan**: Elle  
  'SINI [SystemServices/ConfigureXboxLiveGameSaveServiceStartupMode](https://go.microsoft.com/fwlink/?linkid=875483)  

  Bu ayar, canlı oyun kaydetme hizmeti 'nin başlangıç türünü belirler.  
  - **El ile**
  - **Otomatik**
  - **Devre dışı**

- **Xbox Live ağ hizmeti**  
  **Varsayılan**: Elle  
  'SINI [SystemServices/ConfigureXboxLiveNetworkingServiceStartupMode](https://go.microsoft.com/fwlink/?linkid=875484)  

  Bu ayar ağ hizmeti 'nin başlangıç türünü belirler.  
  - **El ile**
  - **Otomatik**
  - **Devre dışı**

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturulur ancak henüz herhangi bir işlem gerçekleştirmez. Sonra, [profili atayın](device-profile-assign.md)ve [durumunu izleyin](device-profile-monitor.md).  

[MacOS](endpoint-protection-macos.md) cihazlarında Endpoint korumaların ayarlarını yapılandırın.  
