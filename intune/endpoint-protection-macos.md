---
title: Microsoft Intune - Azure’da macOS cihazlara Endpoint Protection ekleme | Microsoft Docs
description: macOS cihazlarda, Mac Apple Store dahil olmak üzere uygulamaların nereye yükleneceğini belirlemek için ağ geçidi denetleyicisini kullanın. Microsoft Intune kullanarak belirli uygulamalara izin vermek, belirli uygulamaları engellemek, gizli mod kullanmak ve hatta bazı gelen bağlantı türlerini engellemek için bir güvenlik duvarı etkinleştirin veya yapılandırın.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 08/02/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d4aa0c47f0aa099ff469eb31b212f387836ad69b
ms.sourcegitcommit: 73fbecf7cee4fdfc37d3c30ea2007d2a9a6d2d12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/03/2019
ms.locfileid: "68756504"
---
# <a name="macos-endpoint-protection-settings-in-intune"></a>Intune 'da MacOS Endpoint Protection ayarları  

Bu makalede, macOS çalıştıran cihazlar için yapılandırabileceğiniz Endpoint Protection ayarları gösterilmektedir. Bu ayarları, Intune 'da [Endpoint Protection](endpoint-protection-configure.md) Için bir MacOS cihaz yapılandırma profili kullanarak yapılandırırsınız.  

## <a name="gatekeeper"></a>Ağ Geçidi Denetleyicisi  

- **Bu konumlardan indirilen uygulamalara izin ver**  
  Uygulamaların nereden indirildiğine bağlı olarak, bir cihazın başlatabileceği uygulamaları sınırlayın. Amaç, cihazları kötü amaçlı yazılımlara karşı korumak ve yalnızca güvendiğiniz kaynaklardan gelen uygulamalara izin vermaktır.  

  - **Yapılandırılmadı**  
  - **Mac App Store**  
  - **Mac App Store ve tanımlı geliştiriciler**  
  - **Her yer**  

  **Varsayılan**: Yapılandırılmamış  

- **Kullanıcı, ağ geçidi denetleyicisini geçersiz kılabilir**  
  Kullanıcıların, Gatekeeper ayarını geçersiz kılmasını engeller ve kullanıcıların bir uygulama yüklemek için tıklamasını denetlemesini engeller. Etkinleştirildiğinde, kullanıcılar Control tuşuna tıklama ile herhangi bir uygulamayı yükleyebilir.  
 
  - **Yapılandırılmadı** -kullanıcılar, uygulamaları yüklemek için ' yi denetleyebilir.  
  - **Engelle** -kullanıcıların uygulamaları yüklemek için Control-Click kullanmasını engeller.  

  **Varsayılan**: Yapılandırılmamış  

## <a name="firewall"></a>Güvenlik Duvarı  

Bağlantı noktası yerine uygulama başına bağlantıları denetlemek için güvenlik duvarı kullanın. Uygulama başına ayarlar kullanmak, güvenlik duvarı korumasından faydalanmayı kolaylaştırır. Ayrıca istenmeyen uygulamaların, güvenilen uygulamalara açık olan ağ bağlantı noktalarının kontrolünü ele geçirmelerini önler.  

**Genel**
- **Duvarını**  
  Gelen bağlantıların ortamınızda nasıl işleneceğini yapılandırmak için güvenlik duvarını etkinleştirin.  
  - **Yapılandırılmadı**  
  - **Etkinleştirebilir**  

  **Varsayılan**: Yapılandırılmamış  

- **Gelen bağlantılar**  
  DHCP, Bonjour ve IPSec gibi temel Internet Hizmetleri için gereken bağlantılar hariç tüm gelen bağlantıları engelleyin. Bu özellik ayrıca, Dosya Paylaşımı ve Ekran Paylaşımı gibi tüm paylaşım hizmetlerini engeller. Paylaşım cihazları kullanıyorsanız bu ayarı *Yapılandırılmadı* olarak bırakın.  
  - **Yapılandırılmadı**  
  - **Engelle**  

  **Varsayılan**: Yapılandırılmamış  

**Belirli uygulamalar için gelen bağlantılara izin verin veya bunları engelleyin.**  

  - **İzin verilen uygulamalar**  
    Gelen bağlantıları almasına açıkça izin verilen uygulamaları seçin.  

  - **Engellenen uygulamalar**  
    Gelen bağlantıları engellemesi gereken uygulamaları seçin.  

  - **Gizli mod**  
    Bilgisayarın yoklama isteklerine yanıt vermesini engellemek için gizli modu etkinleştirin. Cihaz, yetkilendirilmiş uygulamalardan gelen istekleri yanıtlamaya devam eder. ICMP (ping) gibi beklenmedik istekler yoksayılır.  
    - **Yapılandırılmadı**  
    - **Etkinleştirebilir**  

    **Varsayılan**: Yapılandırılmamış  

## <a name="filevault"></a>Dosya Kasası  
Apple Filekasası ayarları hakkında daha fazla bilgi için Apple geliştirici içerikleriyle ilgili [Fdefilekasasını](https://developer.apple.com/documentation/devicemanagement/fdefilevault) inceleyin. 

- **FileVault**  
  MacOS 10,13 ve üstünü çalıştıran cihazlarda Filekasasıyla XTS-AES 128 kullanarak tam disk şifrelemeyi *etkinleştirebilirsiniz* .  
  - **Yapılandırılmadı**  
  - **Etkinleştirebilir**  

  **Varsayılan**: Yapılandırılmamış  

  - **Kurtarma anahtarı türü**  
    Cihazlar için *kişisel anahtar* kurtarma anahtarları oluşturulur. Kişisel anahtar için aşağıdaki ayarları yapılandırın.  

    - **Kişisel kurtarma anahtarının konumu** -kullanıcıya kişisel kurtarma anahtarını nasıl ve nereden alabilecekleri hakkında kısa bir ileti belirtin. Bu metin, bir parola unutursa kişisel kurtarma anahtarını girmeniz istendiğinde kullanıcının oturum açma ekranında gördüğü iletiye eklenir.  
      
    - **Kişisel kurtarma anahtarı döndürme** -bir cihaz için kişisel kurtarma anahtarının ne sıklıkta döndürüleceğini belirtin. **Yapılandırılmadı**' dan varsayılan değeri veya **1** ile **12** ay arasında bir değer seçebilirsiniz.  

  - **Oturumu kapatmak için istemi devre dışı bırak**  
    Kullanıcıdan oturum açtıklarında dosya kasasını etkinleştirdikleri isteyen kullanıcıya sorma işlemini engelleyin.  Etkin olarak ayarlandığında, oturum kapatma istemi devre dışı bırakılır ve bunun yerine kullanıcıya oturum açtıklarında sorulur.  
    - **Yapılandırılmadı**  
    - **Etkinleştir** -oturum kapatma sırasında istemi devre dışı bırakın.

    **Varsayılan**: Yapılandırılmamış  

     > [!IMPORTANT]  
     > **Oturumu kapatma Isteminde devre dışı bırak** ayarı *Etkinleştir*olarak ayarlandığında bilinen bir sorun vardır. *Enable*olarak ayarlandığında, **atlamaya izin verilen sayısı** ayarı bir değere ayarlanmalıdır ve *yapılandırılmamış*olarak ayarlanmamalıdır. *Yapılandırılmadı*olarak ayarlanırsa, profil cihazda başarısız olur. Bu senaryoda cihaz, daha fazla ayrıntı olmadan bir **profil durumu Özeti** **hatası** olarak rapor ediyor.
     > 
     > **Oturumu kapatma sırasında Istemi devre dışı bırak** ayarı *Yapılandırılmadı*olarak ayarlandığında, **atlamaya izin verilen zaman sayısı** *yapılandırılmaz* veya bir değere sahip olabilir.  
     > 
     > Bu sorun, gelecekteki bir güncelleştirmede çözümlenir. 

  - **Atlayakaç kez izin verilir**  
  Kullanıcının oturum açması için dosya kasasından önce dosya kasasını etkinleştirmek üzere bir kullanıcının istekleri yoksaymasına izin sayısını belirleyin.  

    - **Yapılandırılmadı** -bir sonraki oturum açma işlemine izin verilmesi için cihazda şifreleme gerekir.  
    - **1** ila **10** -bir kullanıcının cihazda şifrelemeyi gerektirmeden önce 1 ila 10 kez istemi yoksaymasına izin verin.  
    - **Sınır yok, her zaman sor** -kullanıcıdan dosya kasasını etkinleştirmesi istenir, ancak şifreleme hiçbir zaman gerekli değildir.  
 
    **Varsayılan**: Yapılandırılmamış  


