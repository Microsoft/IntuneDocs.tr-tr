---
title: Koşullu erişim sorunlarını giderme
titleSuffix: Microsoft Intune
description: Kullanıcılarınız, kaynaklara Intune koşullu erişimi aracılığıyla erişim izni alamazsanız ne yapmalı?
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/23/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 5fa59501-5f33-46b7-a5f5-75eeae9f1209
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c662de98ffa497c5fbc89ac1b78ed8537ff0d80c
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "71729233"
---
# <a name="troubleshoot-conditional-access"></a>Koşullu erişim sorunlarını giderme
Bu makalede, kullanıcılarınız koşullu erişimle korunan kaynaklara erişim izni alamazsanız veya kullanıcılar korumalı kaynaklara erişebiliyorsa ve engellenmesi gereken durumlarda ne yapılacağını açıklar.

Intune ve koşullu erişimle, şu gibi hizmetlere erişimi koruyabilirsiniz:
- Exchange Online, SharePoint Online ve Skype Kurumsal Çevrimiçi gibi Office 365 hizmetleri
- Exchange Şirket İçi
- Diğer çeşitli hizmetler

Bu özellik, yalnızca Intune 'a kayıtlı ve Intune yönetim konsolunda veya Azure Active Directory şirket kaynaklarınıza erişimi olan koşullu erişim kurallarıyla uyumlu olan cihazların olduğundan emin olmanızı sağlar. 

## <a name="requirements-for-conditional-access"></a>Koşullu erişim için gereksinimler

Koşullu erişimin çalışması için aşağıdaki gereksinimlerin karşılanması gerekir:

- Cihazın MDM 'ye kaydolması ve Intune tarafından yönetilmesi gerekir.

- Gerek kullanıcı, gerekse cihaz, atanan Intune ilkeleriyle uyumlu olmalıdır.

- Kullanıcıya varsayılan olarak bir cihaz uyumluluk ilkesi atanmış olmalıdır. Bu, Intune yönetim portalında **cihaz uyumluluğu** > **Uyumluluk ilkesi ayarları** ' nın altında olan **Uyumluluk ilkesi atanmamış ayar işareti cihazlarının** yapılandırmasına bağlıdır.

- Kullanıcı Outlook yerine cihazın yerel posta istemcisini kullanıyorsa, cihazda Exchange ActiveSync etkinleştirilmelidir. Bu, iOS, Windows Phone ve Android Knox cihazları için otomatik olarak gerçekleşir.

- Şirket içi Exchange için Intune Exchange bağlayıcınızın doğru şekilde yapılandırılması gerekir. Daha fazla bilgi için bkz. [Microsoft Intune Exchange Connector 'Da sorun giderme](troubleshoot-exchange-connector.md).

- Şirket içi Skype için karma modern kimlik doğrulamasını yapılandırmanız gerekir. Bkz. [karma modern kimlik doğrulaması genel bakış](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview).

Azure Yönetim Portalı’nda ve cihaz envanteri raporunda her cihaz için bu koşulları görüntüleyebilirsiniz.

## <a name="devices-appear-compliant-but-users-are-still-blocked"></a>Cihazlar uyumlu olarak görünüyor, ancak kullanıcılar yine de engelleniyor

- Kullanıcının doğru uyumluluk değerlendirmesi için atanmış bir Intune lisansına sahip olduğundan emin olun.

- Kullanıcı aldıkları karantina e-postasında **Şimdi kullanmaya başlayın** bağlantısına tıklayana, Knox olmayan Android cihazlara erişim izni verilmez. Bu kural, kullanıcı daha önceden Intune'a kayıtlı olsa bile geçerlidir. Kullanıcı e-posta bağlantısını telefonlarıyla almazsa, e-postasına erişmek ve cihazındaki bir e-posta hesabına iletmek için bir BILGISAYAR kullanabilir.

- Cihaz ilk kaydedildiğinde cihazın uyumluluk bilgilerinin kaydedilmesi biraz zaman alabilir. Birkaç dakika bekleyin ve tekrar deneyin.

- İOS cihazlarında, var olan bir e-posta profili, bu kullanıcıya atanan bir Intune yönetici tarafından oluşturulan e-posta profilinin dağıtımını engelleyebilir ve cihaz uyumsuz hale gelebilir. Bu senaryoda, Şirket Portalı uygulama kullanıcıya el ile yapılandırılmış e-posta profilleri nedeniyle uyumlu olmadıklarını bildirir ve kullanıcıdan bu profili kaldırmasını ister. Kullanıcı mevcut e-posta profilini kaldırdığında, Intune e-posta profili başarıyla dağıtılabilir. Bu sorunu önlemek için kullanıcılarınızdan kaydolmadan önce cihazlarında bulunan e-posta profillerini kaldırmalarını isteyin.

- Bir cihaz, bir denetim uyumluluğu durumunda takılmasına ve kullanıcının başka bir iade başlatmasına karşı bir durum alabilir. Bu durumda bir cihazınız varsa:
  - Cihazın Şirket Portalı uygulamasının en son sürümünü kullandığından emin olun.
  - Cihazı yeniden başlatın.
  - Sorunun farklı ağlarda (örneğin, hücresel, Wi-Fi vb.) devam edip etmediğini inceleyin.

  Sorun devam ederse, [Microsoft Intune için destek alma](../fundamentals/get-support.md) konusunda açıklandığı gibi Microsoft Desteği ile iletişim kurun.

- Bazı Android cihazlar şifrelenmiş gibi görünebilir, ancak Şirket Portalı uygulama bu cihazları şifrelenmemiş olarak tanır ve uyumlu değil olarak işaretler. Bu senaryoda kullanıcı, Şirket Portalı uygulamasında cihaz için bir başlangıç geçiş kodu ayarlamasının istendiği bir bildirim görür. Bildirime dokunup, geçerli PIN veya parolayı onayladıktan sonra, **Güvenli başlangıç** ekranında **Cihazı başlatmak için PIN iste** seçeneğini belirleyin, sonra Şirket Portalı uygulamasından cihaz için **Uyumluluğu Denetle** düğmesine dokunun. Cihazın artık şifrelenmiş olarak algılanması gerekir. 

  > [!NOTE]
  > Bazı cihaz üreticileri, bu kullanıcı tarafından ayarlanan PIN yerine varsayılan PIN kullanarak cihazlarını şifreler. Intune, varsayılan PIN 'i güvenli olmayan olarak kullanan ve Kullanıcı yeni, varsayılan olmayan bir PIN oluşturana kadar bu cihazları uyumsuz olarak işaretleyen bir şifrelemeyi görüntüler.

- Kayıtlı ve uyumlu bir Android cihaz hala engellenebilir ve ilk olarak şirket kaynaklarına erişmeye çalışırken bir karantina bildirimi alabilir. Bu durumda, Şirket Portalı uygulamasının çalışmadığından emin olun ve değerlendirmeyi tetiklemek için karantina e-postasında **Şimdi kullanmaya başlayın** bağlantısını seçin. Bunun yalnızca koşullu erişim ilk kez etkinleştirildiğinde yapılması gerekir.

- Kayıtlı bir Android cihaz, kullanıcıdan "sertifika bulunamadı" ve O365 kaynaklarına erişim izni verilmeyebilir. Kullanıcı kayıtlı cihazda *tarayıcı erişimini etkinleştir* seçeneğini şu şekilde etkinleştirmelidir:
  1. Şirket Portalı uygulamasını açın.
  2. Üçlü noktalar (...) veya donanım menü düğmesinden Ayarlar sayfasına gidin.
  3. *Tarayıcı erişimini etkinleştir* düğmesini seçin.
  4. Chrome tarayıcıda, Office 365 oturumunu kapatın ve Chrome’u yeniden başlatın.  


## <a name="devices-are-blocked-and-no-quarantine-email-is-received"></a>Cihazlar engelleniyor ve hiçbir karantina e-postası alınmıyor

- Cihazın Intune yönetim konsolunda bir Exchange ActiveSync cihazı olarak mevcut olduğundan emin olun. Değilse, cihaz olası bir Exchange Connector sorunu nedeniyle bulunamıyor olabilir. Daha fazla bilgi için bkz. [Intune şirket Içi Exchange Connector sorunlarını giderme](troubleshoot-exchange-connector.md).

- Exchange Connector bir cihazı engellemeden önce bir etkinleştirme (karantina) e-postası gönderir. Cihaz çevrimdışıysa, etkinleştirme e-postasını almayabilir. 

- Cihazdaki e-posta istemcisinin e-postayı **Yoklama** yerine **Anında İletme** ile alacak şekilde mi yapılandırıldığına bakın. Öyle yapılandırılmışsa, bu, kullanıcının e-postayı kaçırmasına neden olabilir. **Yoklama** yöntemine geçip cihazın e-postayı alıp almadığına bakın.

## <a name="devices-are-noncompliant-but-users-are-not-blocked"></a>Cihazlar uyumsuz, ancak kullanıcılar engellenmiyor

- Windows bilgisayarları için koşullu erişim yalnızca yerel e-posta uygulamasını, modern kimlik doğrulaması ile Office 2013 veya Office 2016 ' i engeller. Outlook 'un önceki sürümlerinin veya Windows bilgisayarlarda tüm posta uygulamalarının engellenmesi, [Azure Active Directory Koşullu erişim Için SharePoint Online ve Exchange Online kurulumu](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-no-modern-authentication)uyarınca AAD cihaz kaydı ve Active Directory Federasyon Hizmetleri (AD FS) (AD FS) yapılandırmalarının kullanılmasını gerektirir.

- Cihaz seçmeli olarak temizlendiğinde veya Intune kullanımından kaldırıldığında, erişimi birkaç saat daha devam edebilir. Bunun nedeni, Exchange 'in altı saat boyunca erişim haklarının önbelleğe alınır. Bu senaryoda, kullanımdan kaldırılan cihazlardaki verileri korumanın başka yöntemlerini göz önünde bulundurun.

- Surface Hub, toplu kayıtlı ve DEM 'ye kayıtlı Windows cihazları, Intune lisansı atanmış bir Kullanıcı oturum açmışsa koşullu erişimi destekleyebilir. Ancak, Uyumluluk ilkesini doğru değerlendirme için cihaz gruplarına (Kullanıcı grupları değil) dağıtmanız gerekir.

- Uyumluluk ilkelerinizin ve koşullu erişim ilkelerinizin atamalarına bakın. Bir Kullanıcı ilkelerin atandığı grupta yoksa veya dışlanan bir grupta değilse, Kullanıcı engellenmez. Uyumluluk denetimi yalnızca atanan bir grupta olan kullanıcıların cihazlarında yapılır.

## <a name="noncompliant-device-is-not-blocked"></a>Uyumsuz cihaz engellenmiyor

Bir cihaz uyumlu değilse ancak erişime sahip olmaya devam ederse, aşağıdaki işlemleri gerçekleştirin.

- Hedef ve Dışlama gruplarını gözden geçirin. Kullanıcı doğru hedef grupta değilse veya dışlama grubundaysa, engellenmez. Yalnızca Hedef grupta olan kullanıcıların cihazlarında uyumluluk denetimi yapılır.

- Cihazın bulunabildiğinden emin olun. Exchange Connector bir Exchange 2010 CAS’ine, buna karşın kullanıcı bir Exchange 2013 sunucusuna mı işaret ediyor? Bu durumda, varsayılan Exchange kuralı İzin Ver ise, kullanıcı Hedef grupta olsa bile Intune cihazın Exchange’a bağlandığının farkında olamaz.

- Exchange’de Cihazın Varlığı/Erişim Durumu’nu kontrol edin:
  - Bir posta kutusunun tüm mobil cihazlarının listesini almak için bu PowerShell cmdlet 'ini kullanın: ' Get-ActiveSyncDeviceStatistics-Mailbox MBX '. Cihaz listede yoksa Exchange’e erişmiyordur.
  
  - Cihaz listeleniyorsa, ' Get-CASmailbox-Identity: ' UPN ' kullanın | fl ' cmdlet 'i, erişim durumu hakkında ayrıntılı bilgi almak ve bu bilgileri Microsoft Desteği sağlamak için sağlar.

## <a name="next-steps"></a>Sonraki adımlar
Bu bilgiler işinize yaramazsa [Microsoft Intune desteği de alabilirsiniz](../fundamentals/get-support.md).
