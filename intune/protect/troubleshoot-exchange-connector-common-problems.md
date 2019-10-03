---
title: Intune Exchange Connector için sık karşılaşılan sorunları giderme
titleSuffix: Microsoft Intune
description: Şirket içi Microsoft Intune Exchange Connector ilgili sık karşılaşılan sorunları giderin ve çözün
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
ms.openlocfilehash: 4219d9d4f7d7e8c56acc218d16d8277ed2cf3821
ms.sourcegitcommit: f04e21ec459998922ba9c7091ab5f8efafd8a01c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71817538"
---
# <a name="resolve-common-problems-for-the-intune-exchange-connector"></a>Intune Exchange Connector için sık karşılaşılan sorunları çözme
 
Bu makale, Intune yöneticisinin Intune Exchange bağlayıcısının çalışması için sık karşılaşılan sorunları çözümlemesine yardımcı olabilir.  

Devam etmeden önce, sorun gidermeye başlamadan önce bağlayıcı hakkında bilgi edinmek için Intune şirket içi Exchange Connector sorunlarını giderin ve bağlayıcı yapılandırması için sık karşılaşılan sorunları inceleyin. 

## <a name="exchange-activesync-device-not-discovered-from-exchange"></a>Exchange ActiveSync cihazı Exchange 'den bulunmadı

Exchange bağlayıcısının Exchange Server ile eşitlenmekte olup olmadığını görmek için [Exchange Connector etkinliğini izleyin](exchange-connector-install.md#on-premises-intune-exchange-connector-high-availability-support) . Cihaz birleştirildiğinden tam eşitleme veya hızlı eşitleme başarıyla tamamlanırsa, aşağıda listelenen diğer olası sorunları kontrol edebilirsiniz. Hiçbir eşitleme gerçekleştiğinden, eşitleme günlüklerini toplayın ve bir destek isteğine ekleyin.  

- Kullanıcıların bir Intune lisansına sahip olduğundan emin olun, aksi takdirde Exchange Connector cihazlarını bulamaz.  

- Kullanıcının birincil SMTP adresi Azure Active Directory (Azure AD) içinde UPN 'lerden farklıysa, Exchange Connector bu kullanıcı için herhangi bir cihaz bulamaz. Sorunu çözmek için birincil SMTP adresini çözün.  

- Ortamınızda hem Exchange 2010 hem de Exchange 2013 posta kutusu sunucusuna sahipseniz, Exchange bağlayıcısının bir Exchange 2013 Istemci erişim sunucusuna (CAS) işaret etmenizi öneririz. Aksi takdirde, Exchange Connector bir Exchange 2010 CA 'Sı ile iletişim kuracak şekilde ayarlandıysa, Exchange Connector herhangi bir Exchange 2013 Kullanıcı aygıtını bulamaz.  

- Exchange Online ayrılmış ortamları için, bağlayıcı yalnızca yürütülürken bu CA 'larla iletişim kuracağı için, ilk kurulum sırasında adanmış ortamda Exchange bağlayıcısını bir Exchange 2013 CA 'ya (Exchange 2010 CA değil) işaret etmeniz gerekir. PowerShell cmdlet 'leri.  


## <a name="problems-with-the-notification-email-message"></a>Bildirim e-posta iletisiyle ilgili sorunlar  

Şirket içi posta kutularına koşullu erişim için Knox olmayan Android cihazlarını desteklemek için Intune kaydı, Intune Exchange Bağlayıcısı tarafından gönderilen "Şimdi kullanmaya başlayın" e-posta iletisinden başlamalıdır. İletiden kayıt başlamak, cihazın tüm platformlar (Exchange, Azure AD, Intune) genelinde benzersiz bir ActiveSyncID almasını sağlar.  

Kullanıcının bildirim e-posta iletisini almamasının birkaç nedeni vardır:  

- Bildirim hesabı doğru ayarlanmadı.
- Bildirim hesabı için otomatik bulma başarısız oldu.
- E-posta iletisini göndermek için EWS isteği başarısız olur.

E-posta bildirim sorunlarını gidermek için aşağıdakileri kullanın.

### <a name="review-the-notification-account-thats-used-to-retrieve-autodiscover-settings"></a>Otomatik bulma ayarlarını almak için kullanılan bildirim hesabını gözden geçirin
1. Otomatik bulma hizmeti ve Exchange Web Hizmetleri 'nin Exchange Istemci erişim Hizmetleri 'nde yapılandırıldığından emin olun. Daha fazla bilgi için bkz. [Istemci erişim Hizmetleri](https://docs.microsoft.com/Exchange/architecture/client-access/client-access).

   Daha fazla bilgi için bkz. [Exchange Server 'da otomatik bulma hizmeti](https://docs.microsoft.com/Exchange/architecture/client-access/autodiscover?view=exchserver-2019).


2. Bildirim hesabınızın aşağıdaki gereksinimleri karşıladığından emin olun:

   - Hesabın, Exchange şirket içi sunucunuzda barındırılan etkin bir posta kutusu vardır.  

   - Hesap UPN 'si SMTP adresiyle eşleşir.

3. Otomatik bulma 'nın çalışması için, DNS sunucunuzun Exchange istemci erişim sunucunuza işaret eden **Autodiscover.SMTPdomain.com** (örneğin, autodiscover.contoso.com) IÇIN bir DNS kaydı olması gerekir. Kaydın mevcut olup olmadığını denetlemek için, *Autodiscover.SMTPdomain.com*yerine FQDN 'nizi belirtirken şunları yapın:

   1. Komut isteminde **nslookup**yazın ve ardından ENTER tuşuna basın.  

   2. **Autodiscover.SMTPdomain.com**yazın ve ENTER tuşuna basın.

      Çıktının aşağıdaki görüntüye benzer olması gerekir:  
      ![Nslookup sonuçları](./media/troubleshoot-exchange-connector-common-problems/nslookup-results.png
)

   Ayrıca, Microsoft bağlantı çözümleyici aracını kullanarak https://testconnectivity.microsoft.com/ veya yerel bir etki alanındaki Internet 'ten otomatik bulma hizmetini test edebilirsiniz. Daha fazla bilgi için bkz. [Microsoft bağlantı çözümleyici aracı](https://docs.microsoft.com/en-us/previous-versions/office/exchange-remote-connectivity/jj851141(v=exchg.80)). [Microsoft bağlantı çözümleyici aracını](http://go.microsoft.com/fwlink/?LinkID=313782)indirin.


### <a name="review-autodisocvery"></a>Redisocvery 'ı inceleyin  

Otomatik bulma başarısız olursa, aşağıdaki adımları deneyin:
1. [Geçerli bir otomatik bulma DNS kaydı yapılandırın](https://docs.microsoft.com/previous-versions/exchange-server/exchange-150/mt473798(v=exchg.150)). 

2. Aşağıdaki şekilde, Intune Exchange Bağlayıcı yapılandırma dosyasında EWS URL 'sini sabit koda kodlayın:

   1. EWS URL 'sini belirleme. Exchange için varsayılan EWS URL 'SI **https://<mailServerFQDN>/EWS/Exchange. asmx**' dir, ancak sizinde farklı olabilir. Ortamınız için doğru URL 'YI doğrulamak üzere Exchange yöneticisine başvurun.

   2. **OnPremisesExchangeConnectorServiceConfiguration. xml** dosyasını düzenleyin. Varsayılan olarak, dosya Exchange bağlayıcısını çalıştıran bilgisayardaki **%ProgramData%\Microsoft\Windows Intune Exchange Bağlayıcısı** ' nda bulunur. Dosyayı bir metin düzenleyicisi kullanarak açın ve ardından aşağıdaki satırı, ortamınız için EWS URL 'sini yansıtacak şekilde değiştirin: `<ExchangeWebServiceURL> https://<YourExchangeHOST>/EWS/Exchange.asmx</ExchangeWebServiceURL>`
    

3. Dosyayı kaydedin ve ardından bilgisayarı yeniden başlatın veya Microsoft Intune Exchange Connector hizmeti 'ni yeniden başlatın.

>[!NOTE]
> Bu yapılandırmada, Intune Exchange Connector otomatik bulma kullanmayı durduruyor ve bunun yerine EWS URL 'sine doğrudan bağlanır.

## <a name="next-steps"></a>Sonraki adımlar  

Aşağıdaki makale, belirli hataların çözümlenmesine yardımcı olabilir:
- [Intune Exchange Connector için sık karşılaşılan hataları çözün](troubleshoot-exchange-connector-common-errors.md).

Destek veya Intune topluluğundan yardım isteyin.
- Sorunu gidermeye yardımcı olması veya Microsoft ile bir destek talebi açmak için bkz. Intune konsolunu kullanma [desteği alın](../fundamentals/get-support.md) . 
- Sorununuzu [Microsoft Intune forumlarına](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod)gönderin.  
