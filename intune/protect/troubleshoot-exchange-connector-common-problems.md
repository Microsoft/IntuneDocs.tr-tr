---
title: Intune Exchange Connector için sık karşılaşılan sorunları giderme
titleSuffix: Microsoft Intune
description: Şirket içi Microsoft Intune Exchange Connector için sık karşılaşılan sorunları giderin ve çözümleyin.
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/02/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e9542212e1b75d97c96c024eed20e20e610e2b5d
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72503653"
---
# <a name="resolve-common-problems-with-the-intune-exchange-connector"></a>Intune Exchange Connector ile ilgili yaygın sorunları çözme
 
Bu makale, Intune yöneticisinin Intune Exchange Connector ile ilgili sık karşılaşılan sorunları çözümlemesine yardımcı olabilir.  

Sorun gidermeye başlamadan önce, bağlayıcı hakkında temel bilgiler için [Intune şirket Içi Exchange Connector sorun](troubleshoot-exchange-connector.md) gidermeyi inceleyin. Ayrıca bağlayıcı yapılandırması için sık karşılaşılan sorunları gözden geçirin. 

## <a name="an-exchange-activesync-device-isnt-discovered-from-exchange"></a>Exchange ActiveSync cihazı Exchange 'den bulunmadı

Exchange ActiveSync cihazı Exchange 'den keşfedildiğinde Exchange bağlayıcısının Exchange Server ile eşitlendiğine bakmak için [Exchange Connector etkinliğini izleyin](exchange-connector-install.md#on-premises-intune-exchange-connector-high-availability-support) . Cihazın katılmış olduğu bu yana eşitleme gerçekleşmemişse, eşitleme günlüklerini toplayın ve bir destek isteğine ekleyin. Cihaz katıldığı için tam eşitleme veya hızlı eşitleme başarılı bir şekilde tamamlandıysa, aşağıdaki sorunları kontrol edin: 

- Kullanıcıların bir Intune lisansına sahip olduğundan emin olun. Aksi takdirde, Exchange Connector cihazlarını bulamaz.  

- Kullanıcının birincil SMTP adresi Azure Active Directory (Azure AD) içindeki Kullanıcı asıl adından (UPN) farklıysa, Exchange Connector bu kullanıcı için herhangi bir cihaz bulamaz. Bu sorunu çözmek için birincil SMTP adresini düzeltin.  

- Ortamınızda hem Exchange 2010 hem de Exchange 2013 posta kutusu sunucusuna sahipseniz, Exchange bağlayıcısının bir Exchange 2013 Istemci erişim sunucusuna (CAS) işaret etmenizi öneririz. Exchange Connector bir Exchange 2010 CA 'larla iletişim kuracak şekilde ayarlandıysa Exchange Connector, Exchange 2013 ' deki hiçbir Kullanıcı cihazını bulamaz.  

- Exchange Online ayrılmış ortamları için, ilk kurulum sırasında adanmış ortamda Exchange bağlayıcısını bir Exchange 2013 CA 'larına (Exchange 2010 CA değil) işaret etmeniz gerekir. Bağlayıcı, PowerShell cmdlet 'lerini yürüttüğünde yalnızca Exchange 2013 CA 'ları ile iletişim kurar.  


## <a name="problems-with-the-notification-email-message"></a>Bildirim e-posta iletisiyle ilgili sorunlar  

Android Knox çalıştırmayan cihazlarda şirket içi posta kutularına koşullu erişimi desteklemek için, Intune kaydının Intune Exchange bağlayıcısının gönderdiği "Şimdi kullanmaya başlayın" e-posta iletisinden başladığından emin olun. İletiden kayıt başlamak, cihazın tüm platformlar (Exchange, Azure AD, Intune) genelinde benzersiz bir ActiveSyncID almasını sağlar.  

Kullanıcı bildirim e-posta iletisini almayabilir, nedeni:  

- Bildirim hesabı yanlış ayarlandı.
- Bildirim hesabı için otomatik bulma başarısız oldu.
- E-posta iletisini göndermek için Exchange Web Hizmetleri (EWS) isteği başarısız oldu.

E-posta bildirim sorunlarını gidermek için aşağıdaki bölümleri gözden geçirin.

### <a name="check-the-notification-account-that-retrieves-autodiscover-settings"></a>Otomatik bulma ayarlarını alan bildirim hesabını denetleyin
1. Otomatik bulma hizmeti 'nin ve EWS 'nın Exchange Istemci erişim Hizmetleri 'nde yapılandırıldığından emin olun. Daha fazla bilgi için bkz. [Exchange Server 'Da](https://docs.microsoft.com/Exchange/architecture/client-access/autodiscover?view=exchserver-2019) [istemci erişim Hizmetleri](https://docs.microsoft.com/Exchange/architecture/client-access/client-access) ve otomatik bulma hizmeti.


2. Bildirim hesabınızın aşağıdaki gereksinimleri karşıladığından emin olun:

   - Hesabın, Exchange şirket içi sunucunuzda barındırılan etkin bir posta kutusu vardır.  

   - Hesap UPN 'si SMTP adresiyle eşleşir.

3. Otomatik bulma, Exchange Istemci erişim sunucunuza işaret eden **Autodiscover.SMTPdomain.com** (örneğin, autodiscover.contoso.com) için DNS kaydına sahıp bir DNS sunucusu gerektirir. Kaydı denetlemek için *Autodiscover.SMTPdomain.com* yerine FQDN 'nizi belirtin ve şu adımları izleyin:

   1. Komut isteminde *nslookup*yazın.  

   2. *Autodiscover.SMTPdomain.com*girin. Çıktının aşağıdaki görüntüye benzer olması gerekir:  
      ![Nslookup sonuçları @ no__t-1

   Otomatik Bulma hizmetini Internet 'ten https://testconnectivity.microsoft.com ' da test edebilirsiniz. Ya da Microsoft bağlantı çözümleyici aracını kullanarak yerel bir etki alanından test edin. Daha fazla bilgi için bkz. [Microsoft bağlantı çözümleyici aracı](https://docs.microsoft.com/en-us/previous-versions/office/exchange-remote-connectivity/jj851141(v=exchg.80)). Gerekirse, [Microsoft bağlantı Çözümleyicisi aracını indirin](https://go.microsoft.com/fwlink/?LinkID=313782).


### <a name="check-autodiscovery"></a>Otomatik bul denetimi  

Otomatik bulma başarısız olursa, aşağıdaki adımları deneyin:
1. [Geçerli bir otomatik bulma DNS kaydı yapılandırın](https://docs.microsoft.com/previous-versions/exchange-server/exchange-150/mt473798(v=exchg.150)). 

2. Intune Exchange Connector yapılandırma dosyasında EWS URL 'sini sabit kodlayın:

   1. EWS URL 'sini belirleme. Exchange için varsayılan EWS URL 'si `https://<mailServerFQDN>/ews/exchange.asmx` ' dır, ancak URL 'niz farklılık gösterebilir. Ortamınız için doğru URL 'YI doğrulamak üzere Exchange yöneticisine başvurun.

   2. *OnPremisesExchangeConnectorServiceConfiguration. xml* dosyasını düzenleyin. Varsayılan olarak, dosya Exchange bağlayıcısını çalıştıran bilgisayardaki *%ProgramData%\Microsoft\Windows Intune Exchange Bağlayıcısı* ' nda bulunur. Dosyayı bir metin düzenleyicisinde açın ve ardından aşağıdaki satırı, ortamınız için EWS URL 'sini yansıtacak şekilde değiştirin: `<ExchangeWebServiceURL> https://<YourExchangeHOST>/EWS/Exchange.asmx</ExchangeWebServiceURL>`
    

3. Dosyayı kaydedin ve ardından bilgisayarı yeniden başlatın veya Exchange Connector hizmetini Microsoft Intune yeniden başlatın.

>[!NOTE]
> Bu yapılandırmada, Intune Exchange Connector otomatik bulma kullanmayı durduruyor ve bunun yerine EWS URL 'sine doğrudan bağlanır.

## <a name="next-steps"></a>Sonraki adımlar  

Belirli hatalarla ilgili yardım için, [Intune Exchange Connector için sık karşılaşılan hataları çözmeyi](troubleshoot-exchange-connector-common-errors.md)deneyin.

Destek almak veya Intune topluluğundan yardım almak için:
- Sorunu gidermek veya Microsoft ile bir destek talebi açmak için Intune konsolunu kullanma [desteği alın](../fundamentals/get-support.md) bölümüne bakın. 
- Sorununuzu [Microsoft Intune forumlarına](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod)gönderin.  
