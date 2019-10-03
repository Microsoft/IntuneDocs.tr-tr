---
title: Intune Exchange Connector için sık karşılaşılan hataları giderme
titleSuffix: Microsoft Intune
description: Şirket içi Microsoft Intune Exchange Connector ilgili sık karşılaşılan hataları giderin ve çözümleyin
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/02/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: aa4dbfb7c13d767df41655b391767fc7aa13d914
ms.sourcegitcommit: f04e21ec459998922ba9c7091ab5f8efafd8a01c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71817542"
---
# <a name="resolve-common-errors-for-the-intune-exchange-connector"></a>Intune Exchange Connector için sık karşılaşılan hataları çözme

Bu makale, Intune yöneticisinin Intune Exchange bağlayıcısının çalışması hakkındaki belirli hataları ve iletileri çözümlemesine yardımcı olabilir.  

## <a name="configuration-failed-and-returned-error-code-0x0000001"></a>Yapılandırma başarısız oldu ve hata kodu döndürdü 0x0000001

**Sorun**:  
Microsoft Intune Exchange Connector yapılandırmayı denediğinizde aşağıdaki hata iletisini alırsınız:

```
   The Microsoft Intune Exchange Connector cannot connect to the Microsoft Exchange server.  
   The following Microsoft Exchange Server address could not be reached <Exchange server Name FQDN>  
   Verify that the FQDN of the exchange server address and credentials that you entered is correct and the server is running. The Microsoft Intune Exchange Connector does not support Exchange server arrays.  
   Error code: 0x0000001  
```

Bu sorun, Internet proxy ayarları yanlış yapılandırıldıysanız oluşabilir.

**Çözüm**:  
Proxy ayarlarını yapılandır:
1. Ara sunucu ayarlarının doğru yapılandırıldığından emin olmak için yerel ağ yöneticisine başvurun. 
2. Proxy sunucusunu yapılandırmak ve gerekli dışlama listesini eklemek için **netsh WinHTTP** komutunu kullanın. Örnek:  

   ```
   Netsh winhttp set proxy proxy-server="http=proxy.corp.domain.com" bypass-list"34*.*;134.132.*.*;10.*.*;localhost;*.corp.domain.com;*.staging.domain.com"
   ```

## <a name="configuration-failed-and-returned-error-code-0x000000b"></a>Yapılandırma başarısız oldu ve hata kodu döndürüldü 0x000000b   

**Sorun**:  
Microsoft Intune Exchange Connector yapılandırmayı denediğinizde aşağıdaki hata iletisini alırsınız:  

```
   The Microsoft Intune Exchange Connector experienced an error:  
   CertEnroll::CX509PrivateKey::Create: The system cannot find the file specified. 0x80070002 (WIN32: 2  
   ERROR_FILE_NOT_FOUND  
   Error code: 0x000000b  
```
Bu sorun, Intune 'da oturum açmak için kullandığınız hesap bir Intune genel yönetici hesabı değilse oluşabilir.

**Çözüm**:  
Genel yönetici olan bir hesapla Intune 'da oturum açın veya hesabınızı genel yönetici grubuna ekleyin. Daha fazla bilgi için bkz. [Microsoft Intune Ile rol tabanlı yönetim denetimi (RBAC)](../fundamentals/role-based-access-control.md).

## <a name="configuration-failed-and-returned-error-code-0x0000006"></a>Yapılandırma başarısız oldu ve hata kodu döndürüldü 0x0000006

**Sorun**:  
Microsoft Intune Exchange Connector yapılandırmayı denediğinizde aşağıdaki hata iletisini alırsınız:  

```  
   The Microsoft Intune Exchange Connector cannot connect to Microsoft Intune  
   Verify that you are connected to the Internet, check the Microsoft Intune Service Status, and try to connect again.  
   Error code: 0x00000006  
```  
Bu hata, Internet 'e bağlanmak için bir proxy sunucusu kullanılıyorsa ve Intune hizmetine gelen trafiği engelliyorsa meydana gelebilir. Bir proxy 'nin kullanımda olup olmadığını belirlemek için, **Denetim masası** > **Internet seçenekleri**' ne gidin, **bağlantı** sekmesini seçin ve ardından **LAN ayarları**' na tıklayın.

**Çözüm**:  

- **Seçenek 1** -bilgisayarın proxy 'ye geçmeden Internet 'e bağlanmasına izin vermek için proxy ayarlarını kaldırın.  

- **Seçenek 2** - [Intune Exchange Connector gereksinimleri](exchange-connector-install.md#intune-exchange-connector-requirements)bölümünde belirtildiği gibi, ara sunucuyu Intune hizmetine yönelik iletişime izin verecek şekilde yapılandırın.



## <a name="event-7000-or-7041-microsoft-intune-exchange-connector-service-wont-start"></a>Olay 7000 veya 7041: Microsoft Intune Exchange Connector hizmet başlamıyor

**Sorun**:  
İOS cihazı Intune 'A kaydolamaz ve aşağıdaki hata iletilerinden birini oluşturur:  

```  
   Log Name:      System
   Source:            Service Control Manager
   Date:               <time>
   Task Category: None
   Level:               Error
   Keywords:        Classic
   User:                N/A
   Computer:      <computer>
   Description:
   The Microsoft Intune Exchange Connector Service service failed to start because of the following error:  
   The service did not start because of a logon failure.
```  

```  
   Log Name:      System
   Source:            Service Control Manager
   Date:               <time>
   Event ID:          7041
   Task Category: None
   Level:               Error   
   Keywords:        Classic
   User:                N/A
   Computer:       <computer>
   Description:
   The WIEC service was unable to log on as .\WIEC_USER with the currently configured password because of the following error:
   Logon failure: the user has not been granted the requested logon type at this computer.
   Service: WIEC
   Domain and account: .\WIEC_USER
   This service account does not have the required user right "Log on as a service."  
```
Bu sorun, **WIEC_User** hesabının yerel ilkede **hizmet olarak oturum aç** kullanıcı hakkına sahip olmaması durumunda ortaya çıkabilir.

**Çözüm**:  
Intune Exchange bağlayıcısını çalıştıran bilgisayarda, **hizmet olarak oturum** açma kullanıcı hesabını **WIEC_User** hizmeti hesabına atayın. Bilgisayar, bir kümede yer alıyorsa, kümedeki tüm düğümlerde *hizmet olarak oturum* açma kullanıcı hakkını, küme hizmeti hesabına atadığınızdan emin olun.  

Bilgisayardaki **WIEC_User** hizmet hesabına **bir hizmet olarak oturum** açma hakkı atamak için şu adımları izleyin:

1. Bilgisayarda yönetici olarak veya Yöneticiler grubunun bir üyesi olarak oturum açın.
2. Yerel güvenlik Ilkesini açmak için **secpol. msc** dosyasını çalıştırın.
3. **Güvenlik ayarları** > **Yerel ilkeler**' e gidin ve **Kullanıcı hakları ataması**' nı seçin.
4. Sağ bölmede, **hizmet olarak oturum**aç ' a çift tıklayın.
5. **Kullanıcı veya Grup Ekle**' yi seçin, ilkeye **WIEC_USER** ekleyin ve ardından iki kez **Tamam** ' ı seçin.

**Bir hizmet olarak oturum** açma hakkı **WIEC_User** , ancak daha sonra kaldırıldıysa, Grup İlkesi bir ayarın üzerine yazılmasını öğrenmek için etki alanı yöneticisiyle iletişim kurun.  

## <a name="next-steps"></a>Sonraki adımlar  

Aşağıdaki makale, belirli hataların çözümlenmesine yardımcı olabilir:
- [Intune Exchange Connector için sık karşılaşılan sorunları çözün](troubleshoot-exchange-connector-common-problems.md). git 

Destek veya Intune topluluğundan yardım isteyin.
- Sorunu gidermeye yardımcı olması veya Microsoft ile bir destek talebi açmak için bkz. Intune konsolunu kullanma [desteği alın](../fundamentals/get-support.md) . 
- Sorununuzu [Microsoft Intune forumlarına](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod)gönderin.  
