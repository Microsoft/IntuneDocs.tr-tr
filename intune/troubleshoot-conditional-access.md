---
title: Koşullu erişim sorunlarını giderme
description: Kullanıcıların, kaynaklara Intune koşullu erişimi üzerinden erişemediklerinde ne yapacakları açıklanır.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 09/25/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5fa59501-5f33-46b7-a5f5-75eeae9f1209
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 642a4da6a1ca3c368e90f2d3007c1fc6a068af78
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52189240"
---
# <a name="troubleshoot-conditional-access"></a>Koşullu erişim sorunlarını giderme

Exchange Online, SharePoint Online, Skype Kurumsal Çevrimiçi, Exchange şirket içi gibi Office 365 hizmetlerine ve diğer hizmetlere erişimi Intune ve koşullu erişim kullanarak koruyabilirsiniz. Bu özellik, şirket kaynaklarına erişimin Intune'a kayıtlı ve Intune yönetim konsolunda veya Azure Active Directory'de ayarladığınız koşullu erişim kurallarına uyan cihazlarla sınırlı olduğundan emin olmanızı sağlar. Bu makalede, kullanıcılarınız koşullu erişimle korunan kaynaklara erişemediğinde veya bunlara erişebildiği ancak engellenmeleri gerektiğinde ne yapılması gerektiği anlatılmaktadır.

## <a name="requirements-for-conditional-access"></a>Koşullu erişim için gereksinim listesi

Koşullu erişimin çalışması için aşağıdaki gereksinimler karşılanmalıdır:

- Cihazın Intune'a kayıtlı olmalı ve Intune tarafından yönetilmelidir.
- Gerek kullanıcı, gerekse cihaz, atanan Intune ilkeleriyle uyumlu olmalıdır.
- Kullanıcıya varsayılan olarak bir cihaz uyumluluk ilkesi atanmış olmalıdır. Bu, Intune yönetim portalında **Cihaz Uyumluluğu** > **Uyumluluk İlkesi Ayarları** altındaki **Kendisine hiçbir uyumluluk ilkesi atanmamış cihazları şöyle işaretle** ayarının yapılandırmasına bağlıdır.
-   Kullanıcı Outlook yerine cihazın yerel posta istemcisini kullanıyorsa, cihazda Exchange ActiveSync etkinleştirilmelidir. Bu ayar iOS, Windows Phone ve Android cihazlarında otomatik olarak gerçekleşir.
-   Intune Exchange Connector'ınız düzgün şekilde yapılandırılmalıdır. Daha fazla bilgi için bkz. [Microsoft Intune’da Exchange Connector sorunlarını giderme](troubleshoot-exchange-connector.md).

Azure Yönetim Portalı’nda ve cihaz envanteri raporunda her cihaz için bu koşulları görüntüleyebilirsiniz.

## <a name="devices-appear-compliant-but-users-are-still-blocked"></a>Cihazlar uyumlu olarak görünüyor, ancak kullanıcılar yine de engelleniyor

- Knox olmayan Android cihazlara, kullanıcı aldığı karantina e-postasındaki **Şimdi Başla** bağlantısına tıklamadan erişim verilmez. Bu kural, kullanıcı daha önceden Intune'a kayıtlı olsa bile geçerlidir. İçinde bağlantı olan e-posta telefonuna gelmezse, kullanıcı, e-postasına erişmek ve e-postayı cihazındaki bir e-posta hesabına iletmek için bir bilgisayarı kullanabilir.
- Cihaz ilk kaydedildiğinde cihazın uyumluluk bilgilerinin kaydedilmesi biraz zaman alabilir. Birkaç dakika bekleyin ve tekrar deneyin.
- iOS cihazlarında, mevcut bir e-posta profili, Intune yöneticisi tarafından oluşturulan ve bu kullanıcıya atanan bir e-posta profilinin dağıtılmasını engelleyerek cihazı uyumsuz hale getirebilir. Bu senaryoda Şirket Portalı uygulaması kullanıcıya el ile yapılandırılmış e-posta profili nedeniyle uyumsuz olduğunu bildirir ve kullanıcıdan bu profili kaldırmasını ister. Kullanıcı mevcut e-posta profilini kaldırdıktan sonra Intune e-posta profili başarıyla dağıtılır. Bu sorunu önlemek için kullanıcılarınızdan kaydolmadan önce cihazlarında bulunan e-posta profillerini kaldırmalarını isteyin.
- Bir cihaz, uyumluluk denetim durumunda takılı kalarak kullanıcının başka bir giriş işlemini başlatmasını engelleyebilir. Bu durumda olan bir cihazınız varsa aşağıdakileri deneyin:
  - Cihazın Şirket Portalı uygulamasının en son sürümünü kullandığından emin olun.
  - Cihazı yeniden başlatın.
  - Sorunun farklı ağlarda (hücresel, Wi-Fi vb.) devam edip etmediğine bakın.

  Sorun devam ederse, [Microsoft Intune için destek alma](get-support.md) konusunda açıklandığı gibi Microsoft Desteği ile iletişim kurun.
- Belirli Android cihazları şifrelenmiş gibi görünebilir, ancak Şirket Portalı uygulaması bu cihazları şifrelenmemiş olarak algılayarak bunları uyumsuz olarak işaretleyebilir. Bu senaryoda kullanıcı, Şirket Portalı uygulamasında cihaz için bir başlangıç geçiş kodu ayarlamasının istendiği bir bildirim görür. Bildirime dokunup, geçerli PIN veya parolayı onayladıktan sonra, **Güvenli başlangıç** ekranında **Cihazı başlatmak için PIN iste** seçeneğini belirleyin, sonra Şirket Portalı uygulamasından cihaz için **Uyumluluğu Denetle** düğmesine dokunun. Cihazın artık şifrelenmiş olarak algılanması gerekir. 
  > [!NOTE]
  > Bazı cihaz üreticileri cihazlarını kullanıcı tarafından ayarlanan bir PIN yerine varsayılan bir PIN kullanarak şifreler. Intune varsayılan PIN'i kullanan şifrelemeyi güvensiz olarak kabul eder ve bu cihazları kullanıcı yeni ve varsayılan PIN'den farklı bir PIN oluşturuncaya kadar uyumsuz olarak işaretler.
- Kayıtlı ve uyumlu olan bir Android cihaz, şirket kaynaklarına ilk kez erişmeye çalıştığında yine de karantina bildirimi alabilir. Bu olursa, Şirket Portalı uygulamasının çalışmadığından emin olun, ardından değerlendirme başlatmak için karantina e-postasındaki **Şimdi Başla** bağlantısına tıklayın. Bunun yalnızca koşullu erişim ilk kez etkinleştirildiğinde yapılması gerekir.

## <a name="devices-are-blocked-and-no-quarantine-email-is-received"></a>Cihazlar engelleniyor ve hiçbir karantina e-postası alınmıyor

- Cihazın Intune yönetim konsolunda bir Exchange ActiveSync cihazı olarak mevcut olduğundan emin olun. Değilse, cihaz olası bir Exchange Connector sorunu nedeniyle bulunamıyor olabilir. Daha fazla bilgi için bkz. [Intune şirket içi Exchange bağlayıcısında sorun giderme.](troubleshoot-exchange-connector.md)
- Exchange Connector bir cihazı engellemeden önce bir etkinleştirme (karantina) e-postası gönderir. Cihaz çevrimdışıysa, etkinleştirme e-postasını almayabilir. 
- Cihazdaki e-posta istemcisinin e-postayı **Yoklama** yerine **Anında İletme** ile alacak şekilde mi yapılandırıldığına bakın. Öyle yapılandırılmışsa, bu, kullanıcının e-postayı kaçırmasına neden olabilir. **Yoklama** yöntemine geçip cihazın e-postayı alıp almadığına bakın.

## <a name="devices-are-noncompliant-but-users-are-not-blocked"></a>Cihazlar uyumsuz, ancak kullanıcılar engellenmiyor

- Windows bilgisayarlarda koşullu erişim yalnızca yerel e-posta uygulamasını, Office 2013 Modern Kimlik Doğrulamasını veya Office 2016'yı engeller. Windows bilgisayarlarda Outlook'un veya tüm posta uygulamalarının önceki sürümlerini engellemek, [SharePoint Online'ı ve Exchange Online'ı Azure Active Directory koşullu erişimi için ayarlama](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-no-modern-authentication) konusunda belirtildiği gibi AAD Cihaz Kaydı ve Active Directory Federasyon Hizmetleri (AD FS) yapılandırmaları gerektirir. 
- Cihaz seçmeli olarak temizlendiğinde veya Intune kullanımından kaldırıldığında, erişimi birkaç saat daha devam edebilir. Bunun nedeni, Exchange’in, erişim haklarını 6 saat boyunca önbelleğe almasıdır. Bu senaryoda, kullanımdan kaldırılan cihazlardaki verileri korumanın başka yöntemlerini göz önünde bulundurun.
- Surface Hub cihazları koşullu erişimi destekler; ancak doğru değerlendirme için uyumluluk ilkesini (kullanıcı gruplarına değil) cihaz gruplarına dağıtmanız gerekir.
- Uyumluluk ilkelerinizin ve koşullu erişim ilkelerinizin atamalarına bakın. Kullanıcı ilkelerin atandığı grupta değilse veya dışlanan bir gruptaysa engellenir. Uyumluluk denetimi yalnızca atanan bir grupta olan kullanıcıların cihazlarında yapılır.

## <a name="noncompliant-device-is-not-blocked"></a>Uyumsuz cihaz engellenmiyor

Uyumlu olmayan ancak erişimi olan bir cihazla karşılaşırsanız, aşağıdaki adımları uygulayın.
- Hedef ve Dışlama gruplarını gözden geçirin. Kullanıcı doğru hedef grupta değilse veya dışlama grubundaysa, engellenmez. Yalnızca Hedef grupta olan kullanıcıların cihazlarında uyumluluk denetimi yapılır.
- Cihazın bulunabildiğinden emin olun. Exchange Connector bir Exchange 2010 CAS’ine, buna karşın kullanıcı bir Exchange 2013 sunucusuna mı işaret ediyor? Bu durumda, varsayılan Exchange kuralı İzin Ver ise, kullanıcı Hedef grupta olsa bile Intune cihazın Exchange’a bağlandığının farkında olamaz.
- Exchange’de Cihazın Varlığı/Erişim Durumu’nu kontrol edin:
  - Bir posta kutusunun tüm mobil cihazlarının listesini almak için şu PowerShell cmdlet’ini kullanın: "Get-ActiveSyncDeviceStatistics -mailbox mbx'. Cihaz listede yoksa Exchange’e erişmiyordur.
  - Cihaz listeleniyorsa, erişim durumu hakkında ayrıntılı bilgi almak için Get-CASmailbox -identity:’upn’ | fl cmdlet’ini kullanın ve bu bilgileri Microsoft Desteği’ne verin.

## <a name="next-steps"></a>Sonraki adımlar
Bu bilgiler işinize yaramazsa [Microsoft Intune desteği de alabilirsiniz](get-support.md).
