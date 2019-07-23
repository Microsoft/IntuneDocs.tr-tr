---
title: Microsoft Intune - Azure’da macOS cihazlara Endpoint Protection ekleme | Microsoft Docs
description: macOS cihazlarda, Mac Apple Store dahil olmak üzere uygulamaların nereye yükleneceğini belirlemek için ağ geçidi denetleyicisini kullanın. Microsoft Intune kullanarak belirli uygulamalara izin vermek, belirli uygulamaları engellemek, gizli mod kullanmak ve hatta bazı gelen bağlantı türlerini engellemek için bir güvenlik duvarı etkinleştirin veya yapılandırın.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/19/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3a885abfdd7f23f453f03c63fdb0086bed40a7b1
ms.sourcegitcommit: c3a4fefbac8ff7badc42b1711b7ed2da81d1ad67
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/22/2019
ms.locfileid: "68375045"
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

    - **Kişisel kurtarma anahtarının konumu** -kullanıcıya kişisel kurtarma anahtarını nasıl alabilecekleri hakkında kısa bir ileti belirtin. Bu metin, kullanıcının dosya kasasını etkinleştirirken gördüğü iletiye eklenir.  
      
    - **Kişisel kurtarma anahtarı döndürme** -bir cihaz için kişisel kurtarma anahtarının ne sıklıkta döndürüleceğini belirtin. **Yapılandırılmadı**' dan varsayılan değeri veya **1** ile **12** ay arasında bir değer seçebilirsiniz.  

  - **Oturum açana kadar dosya kasasını ertele**  
    > [!NOTE]
    > Dosya Kasası desteği, Temmuz yayını birkaç gün içinde piyasaya sürülene kadar sınırlandırılır. Dağıtım tamamlanana kadar, Filekasasını yapılandırırsanız, **etkinleştirmek**üzere *oturum açana kadar dosya kasasını ertele* seçeneğini ayarlamanız gerekir.   

    Kullanıcı oturumu kapatana kadar Filekasası etkinleştirilmeyecektir. Yerel bir kullanıcı veya mobil hesap kullanıcısına oturumu kapatma veya bir sonraki oturum açma sırasında dosya kasasını etkinleştirmesi istenecektir.  
    - **Yapılandırılmadı**  
    - **Etkinleştirebilir**  
    **Varsayılan**: Yapılandırılmamış  



    - **Oturumu kapatmak için istemi devre dışı bırak**  
      Kullanıcıdan oturum açtıklarında dosya kasasını etkinleştirdikleri isteyen kullanıcıya sorma işlemini engelleyin.  
      - **Yapılandırılmadı**  
      - **Etkinleştirebilir**  

      **Varsayılan**: Yapılandırılmamış  

    - **Atlayakaç kez izin verilir**  
    Kullanıcının oturum açması için dosya kasasından önce dosya kasasını etkinleştirmek üzere bir kullanıcının istekleri yoksaymasına izin sayısını belirleyin.  

      - **Yapılandırılmadı** -bir sonraki oturum açma işlemine izin verilmesi için cihazda şifreleme gerekir.  
      -  **1** ila **10** -bir kullanıcının cihazda şifrelemeyi gerektirmeden önce 1 ila 10 kez istemi yoksaymasına izin verin.  
      - **Sınır yok, her zaman sor** -kullanıcıdan dosya kasasını etkinleştirmesi istenir, ancak şifreleme hiçbir zaman gerekli değildir.  
 
      **Varsayılan**: Yapılandırılmamış  


