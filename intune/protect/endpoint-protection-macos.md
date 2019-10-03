---
title: Microsoft Intune-Azure 'da macOS 'a Endpoint Protection ekleme | Microsoft Docs
description: MacOS cihazlarında, Mac App Store dahil olmak üzere uygulamaların yüklenebilecekleri yeri öğrenmek için ağ geçidi denetleyicisini kullanın. Ayrıca, belirli uygulamalara izin veren bir güvenlik duvarı etkinleştirin veya yapılandırın, özellikleri uygulamaları engeller, gizli modu kullanın ve hatta Microsoft Intune kullanarak belirli gelen bağlantı türlerini engelleyin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/02/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6090d329eee6f27da21b6133a2b7ccdc7072feb3
ms.sourcegitcommit: f04e21ec459998922ba9c7091ab5f8efafd8a01c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71814124"
---
# <a name="macos-endpoint-protection-settings-in-intune"></a>Intune 'da MacOS Endpoint Protection ayarları  

Bu makalede, macOS çalıştıran cihazlar için yapılandırabileceğiniz Endpoint Protection ayarları gösterilmektedir. Bu ayarları, Intune 'da [Endpoint Protection](endpoint-protection-configure.md) Için bir MacOS cihaz yapılandırma profili kullanarak yapılandırırsınız.  

## <a name="gatekeeper"></a>Ağ Geçidi Denetleyicisi  

- **Bu konumlardan indirilen uygulamalara izin ver**  
  Uygulamaların nereden indirildiğine bağlı olarak, bir cihazın başlatabileceği uygulamaları sınırlayın. Amaç, cihazları kötü amaçlı yazılımlara karşı korumak ve yalnızca güvendiğiniz kaynaklardan gelen uygulamalara izin vermaktır.  

  - **Yapılandırılmadı**  
  - **Mac App Store**  
  - **Mac App Store ve tanımlanan geliştiriciler**  
  - **Yerdeki**  

  **Varsayılan**: yapılandırılmadı  

- **Kullanıcı, ağ geçidi denetleyicisini geçersiz kılabilir**  
  Kullanıcıların, Gatekeeper ayarını geçersiz kılmasını engeller ve kullanıcıların bir uygulama yüklemek için tıklamasını denetlemesini engeller. Etkinleştirildiğinde, kullanıcılar herhangi bir uygulamayı denetleyebilir ve yükleyebilir.  
 
  - **Yapılandırılmadı** -kullanıcılar, uygulamaları yüklemek için ' yi denetleyebilir.  
  - **Engelle** -kullanıcıların uygulamaları yüklemek için Control-Click kullanmasını engeller.  

  **Varsayılan**: yapılandırılmadı  

## <a name="firewall"></a>Güvenlik Duvarı  

Bağlantı noktası başına değil, uygulama başına bağlantıları denetlemek için güvenlik duvarını kullanın. Uygulama başına ayarların kullanılması, güvenlik duvarı korumasının avantajlarını daha kolay hale getirir. Ayrıca, istenmeyen uygulamaların meşru uygulamalar için açık olan ağ bağlantı noktalarının denetimini ele almasını önlemeye de yardımcı olur.  

**Genel**
- **Güvenlik duvarı**  
  Gelen bağlantıların ortamınızda nasıl işleneceğini yapılandırmak için güvenlik duvarını etkinleştirin.  
  - **Yapılandırılmadı**  
  - **Etkinleştirme**  

  **Varsayılan**: yapılandırılmadı  

- **Gelen bağlantılar**  
  DHCP, Bonjour ve IPSec gibi temel Internet Hizmetleri için gereken bağlantılar hariç tüm gelen bağlantıları engelleyin. Bu özellik, dosya paylaşımı ve ekran paylaşımı gibi tüm paylaşım hizmetlerini de engeller. Paylaşım Hizmetleri kullanıyorsanız, bu ayarı *yapılandırılmamış*olarak tutun.  
  - **Yapılandırılmadı**  
  - **Engelleyin**  

  **Varsayılan**: yapılandırılmadı  

**Belirli uygulamalar için gelen bağlantılara izin verin veya bunları engelleyin.**  

  - **İzin verilen uygulamalar**  
    Gelen bağlantıları almasına açıkça izin verilen uygulamaları seçin.  

  - **Engellenen uygulamalar**  
    Gelen bağlantıları engellemesi gereken uygulamaları seçin.  

  - **Gizli mod**  
    Bilgisayarın yoklama isteklerine yanıt vermesini engellemek için gizli modu etkinleştirin. Cihaz, yetkili uygulamalar için gelen istekleri yanıtlamaya devam eder. ICMP (ping) gibi beklenmeyen istekler yok sayılır.  
    - **Yapılandırılmadı**  
    - **Etkinleştirme**  

    **Varsayılan**: yapılandırılmadı  

## <a name="filevault"></a>Dosya Kasası  
Apple Filekasası ayarları hakkında daha fazla bilgi için Apple geliştirici içerikleriyle ilgili [Fdefilekasasını](https://developer.apple.com/documentation/devicemanagement/fdefilevault) inceleyin. 

> [!IMPORTANT]  
> MacOS 10,15 itibariyle, Filekasası yapılandırması kullanıcı onaylı MDM kaydı gerektirir. 

- **Dosya Kasası**  
  MacOS 10,13 ve üstünü çalıştıran cihazlarda Filekasasıyla XTS-AES 128 kullanarak tam disk şifrelemeyi *etkinleştirebilirsiniz* .  
  - **Yapılandırılmadı**  
  - **Etkinleştirme**  

  **Varsayılan**: yapılandırılmadı  

  - **Kurtarma anahtarı türü**  
    Cihazlar için *kişisel anahtar* kurtarma anahtarları oluşturulur. Kişisel anahtar için aşağıdaki ayarları yapılandırın.  

    - **Kişisel kurtarma anahtarının konumu** -kullanıcıya kişisel kurtarma anahtarını nasıl ve nereden alabilecekleri hakkında kısa bir ileti belirtin. Bu metin, bir parola unutursa kişisel kurtarma anahtarını girmeniz istendiğinde kullanıcının oturum açma ekranında gördüğü iletiye eklenir.  
      
    - **Kişisel kurtarma anahtarı döndürme** -bir cihaz için kişisel kurtarma anahtarının ne sıklıkta döndürüleceğini belirtin. **Yapılandırılmadı**' dan varsayılan değeri veya **1** ile **12** ay arasında bir değer seçebilirsiniz.  

  - **Oturumu kapatmak için istemi devre dışı bırak**  
    Kullanıcıdan oturum açtıklarında dosya kasasını etkinleştirdikleri isteyen kullanıcıya sorma işlemini engelleyin.  Devre dışı olarak ayarlandığında, oturum kapatma istemi devre dışı bırakılır ve bunun yerine kullanıcıya oturum açtıklarında sorulur.  
    - **Yapılandırılmadı**  
    - **Devre dışı bırak** -oturum kapatma sırasında istemi devre dışı bırak.

    **Varsayılan**: yapılandırılmadı  

  - **Atlayakaç kez izin verilir**  
  Kullanıcının oturum açması için dosya kasasından önce dosya kasasını etkinleştirmek üzere bir kullanıcının istekleri yoksaymasına izin sayısını belirleyin. 

    - **Yapılandırılmadı** -bir sonraki oturum açma işlemine izin verilmesi için cihazda şifreleme gerekir.  
    - **1** ila **10** -bir kullanıcının cihazda şifrelemeyi gerektirmeden önce 1 ila 10 kez istemi yoksaymasına izin verin.  
    - **Sınır yok, her zaman sor** -kullanıcıdan dosya kasasını etkinleştirmesi istenir, ancak şifreleme hiçbir zaman gerekli değildir.  
 
    **Varsayılan**: *değişir* - *oturumu kapatma sırasında devre dışı bırakma istemi* **Yapılandırılmadı**olarak ayarlandığında, bu ayar varsayılan olarak **yapılandırılmaz**. *Oturumu kapatma sırasında Disable* seçeneğini devre **dışı**bırak olarak ayarlarsanız, bu ayar varsayılan olarak **1** ' dir ve **yapılandırılmamış** bir değer bir seçenek değildir.

Intune ile Filekasası hakkında daha fazla bilgi için bkz. [filekasası kurtarma anahtarları](encryption-monitor.md#filevault-recovery-keys).

