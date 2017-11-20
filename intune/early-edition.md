---
title: "Erken sürüm"
description: 
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 11/6/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f7cc595655950ef1bf2586e939b6f02e270e7afc
ms.sourcegitcommit: 5279a0bb8c5aef79aa57aa247ad95888ffe5a12b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/08/2017
---
# <a name="the-early-edition-for-microsoft-intune---november-2017"></a>Microsoft Intune için erken sürüm - Kasım 2017

**Erken sürüm**, Microsoft Intune'un gelecek sürümlerinde kullanıma sunulacak yeni özelliklerin bir listesini sunar. Bu bilgiler kısıtlı bir kapsamla verilmektedir ve değiştirilebilir. Bu bilgileri şirket dışından kimselerle paylaşmayın. Burada listelenen özelliklerden bazılarının son tarihe yetişememe riski vardır ve gelecek sürüme ertelenebilir. Diğer özellikler, müşterinin kullanımına hazır olduğundan emin olmak için pilot (sürüyor) aşamasında test edilmektedir. Herhangi bir sorunuz veya endişeniz varsa lütfen Microsoft ürün grubu ilgili kişisiyle bağlantı kurun.

Bu sayfa düzenli aralıklarla güncelleştirilir. Ek güncelleştirmeleri daha sonra denetleyin.

> [!Note]
>Intune için aşağıdaki değişiklikler geliştirilme aşamasındadır. Yeni karma özellikler hakkında daha fazla bilgi için, [Karma Yenilikler sayfamızı](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) gözden geçirin.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->


## <a name="intune-in-the-azure-portal"></a>Azure portalında Intune


### <a name="assign-office-365-mobile-apps-to-ios-and-android-devices-using-built-in-app-type----1332318---"></a>Yerleşik uygulama türü kullanarak Office 365 mobil uygulamaları iOS ve Android cihazlara atama <!-- 1332318 -->
**Yerleşik** uygulama türü yönettiğiniz iOS and ve Android cihazlar için Office 365 uygulamaları oluşturmayı ve atamayı kolaylaştırır. Bu uygulamalar Word, Excel, PowerPoint ve OneDrive gibi 0365 uygulamalarını içerir. Uygulama türüne belirli uygulamalar atayabilir ve uygulama bilgileri yapılandırmasını düzenleyebilirsiniz.

### <a name="single-sign-on-support-for-ios----1333645---"></a>iOS için Çoklu Oturum Açma desteği <!-- 1333645 -->  
iOS kullanıcıları için Çoklu Oturum Açma kullanabileceksiniz. Çoklu Oturum Açma yükünde kullanıcı kimlik bilgilerini aramak için kodlanan iOS uygulamaları bu yük yapılandırması güncelleştirmesi ile işlevseldir. Asıl Ad ve Bölgeyi yapılandırmak için UPN ve Intune Cihaz Kimliğini de kullanabilirsiniz.

### <a name="ios-11-app-inventory-api-for-mobile-threat-detection----1391759---"></a>Mobil Tehdit Algılama için iOS 11 uygulama envanteri API’si<!-- 1391759 -->
Intune, kişisel ve kuruluşa ait cihazlardan uygulama envanter bilgilerini toplayarak Lookout for Work gibi Mobil Tehdit Algılama (MTD) sağlayıcıları tarafından alınabilir hale getirir. iOS 11+ cihazlarının kullanıcılarından uygulama envanteri toplamanız mümkün olacaktır.

**Uygulama envanteri**  
Şirkete ait iOS 11+ ve kişisel cihazlar için envanterler MTD hizmet sağlayıcınıza gönderilir. Uygulama envanterindeki veriler şunları içerir:

 - Uygulama Kimliği
 - Uygulama Sürümü
 - Uygulama Kısa Sürümü
 - Uygulama Adı
 - Uygulama Paketi Boyutu
 - Uygulama Dinamik Boyutu
 - Uygulamanın doğrulanıp doğrulanmadığı
 - Uygulamanın yönetilip yönetilmediği

### <a name="audit-updates----1412961---"></a>Güncelleştirmeleri denetleme <!-- 1412961 -->  
Intune denetimi, Intune’la ilgili değişiklik işlemlerinin bir kaydını sağlar.  Tüm oluşturma, güncelleştirme, silme ve uzak görev işlemleri yakalanır ve bir yıl süreyle tutulur.  Azure portalı her iş yükü içinde son 30 günlük denetim verilerinin bir görünümünü sağlar ve bunlar filtrelenebilir.  Karşılık gelen bir Graph API, geçen yıl için depolanan denetim verilerinin alınmasına olanak sağlar. 

Denetim **İZLEYİCİ** grubu altında bulunur. Her bir iş yükü için bir **Denetim Günlükleri** menü öğesi bulunur.   

### <a name="text-protocol-allowed-from-managed-apps----1414050----"></a>Yönetilen Uygulamalar izin verilen metin protokolü <!-- 1414050  -->
Intune Uygulama SDK’sı tarafından yönetilen uygulamalar SMS mesajları gönderebilir.

### <a name="remotely-restart-ios-device-supervised-only----1424595---"></a>iOS cihazı uzaktan yeniden başlatma (yalnızca denetimli) <!-- 1424595 -->
Bir cihaz eylemi kullanarak yeniden başlatmak için denetlenen bir iOS 10.3+ cihazı tetiklemeniz mümkün olacaktır. Cihazı yeniden başlatma eylemini kullanma hakkında daha fazla bilgi için bkz. [Intune ile cihazları uzaktan yeniden başlatma](device-restart.md).

> [!Note]  
> Bu komut, denetlenen cihazlar ve **Cihaz Kilidi** erişim hakkı gerektirir. Cihaz hemen yeniden başlatılır. Geçiş koduyla kilitli iOS cihazlar yeniden başlatmadan sonra bir Wi-Fi ağına yeniden katılmaz; yeniden başlatıldıktan sonra sunucu ile iletişim kuramayabilir.

### <a name="remotely-lock-managed-macos-device-with-intune----1437691---"></a>Intune ile yönetilen macOS cihazları uzaktan kilitleme <!-- 1437691 -->
Kayıp bir macOS cihazı kilitleyerek 6 haneli bir kurtarma PIN’i ayarlamanız mümkün olacaktır. Kilitliyken, **Cihaza genel bakış** dikey penceresi başka bir cihaz eylemi gönderilene kadar PIN’i görüntüler.

Daha fazla bilgi için bkz. [Intune ile yönetilen cihazları uzaktan kilitleme](device-remote-lock.md).

### <a name="windows-defender-advanced-threat-protection-reporting-frequency-settings------1455974-----"></a>Windows Defender Gelişmiş Tehdit Koruması raporlama sıklığı ayarları <!--- 1455974  --->
Windows Defender Gelişmiş Tehdit Koruması (WDATP) hizmeti yöneticilerin yönetilen cihazlar için raporlama sıklığını yönetmesine olanak sağlar. Yeni **Telemetri raporlama sıklığını hızlandır** seçeneğiyle, WDATP daha sık veri toplar ve riskleri değerlendirir. Raporlama için varsayılan ayar, hızı ve performansı en iyi duruma getirir. Raporlama sıklığını artırmak yüksek riskli cihazlar için yararlı olabilir. Bu ayar, **Cihaz yapılandırmaları** içinde **Windows Defender ATP** profilinde bulunabilir.

### <a name="assignment-conflict-resolution-has-changed-for-ios-store-apps----1480316---"></a>iOS mağaza uygulamaları için atama çakışması çözümlemesi değişti <!-- 1480316 -->
Son kullanıcılar, iOS mağazası uygulamalarının kullanılabilirliğinde bir değişiklikle karşılaşabilir. Şu anda, **Gerekli ve Kullanılabilir** ile **Geçerli değil** arasında bir çakışma ile iki gruba atanan uygulamalar, **Gerekli ve Kullanılabilir** olarak çözümlenir. Değişiklik ile bu çakışmayı yaşayan bir uygulama **Geçerli değil** olarak çözümlenir.

Değişiklik, bir uygulama farklı uygulama amaçlarına sahip birden çok gruba atandığında görülen karışıklığı giderir.

Uygulamanızın Kasım hizmet yayınından önce Bilgi Çalışanı Portalı ve Şirket Portalı’nda kullanılabilir olmasını istiyorsanız iki seçeneğiniz bulunur:

1. Grubunuz için **Geçerli değil** atamasını kaldırın.
2. **Gerekli ve Kullanılabilir** amacı atanmamış yeni bir grup oluşturun ve bu grubu **Geçerli değil** olarak atayın.

Daha fazla bilgi için bkz. [Microsoft Intune ile uygulamaları gruplara atama](apps-deploy.md).

> [!Note]
> Yayından sonra Intune klasik konsolunda Mobil Cihaz Yönetimi (MDM) uygulama atamalarını göremeyecek veya düzenleyemeyeceksiniz. Ancak uygulama atamalarınızı gerçekleştirmek için Azure konsolu veya Intune Graph API’yi kullanabilirsiniz.

### <a name="manage-android-for-work-devices-independently-from-android-devices----1490731---"></a>Android for Work cihazlarını Android cihazlardan ayrı olarak yönetme <!-- 1490731 -->
Intune, Android for Work cihazlarının Android platformundan bağımsız olarak kaydını yönetmeyi destekleyecektir. Bu ayarlar **Cihaz Kaydı** > **Kayıt kısıtlamaları** > **Cihaz Türü Kısıtlamaları** altında yönetilir. (Eskiden **Cihaz Kaydı** > **Android for Work Kaydı** > **Android for Work Kayıt Ayarları** altında bulunuyordu.)

Varsayılan olarak, Android for Work cihaz ayarlarınız Android cihazlarınız için ayarlarınızla aynı olacaktır. Ancak Android for Work ayarlarınızı değiştirdikten sonra artık bu durum oluşmaz.
 
Kişisel Android for Work kaydını engellerseniz, yalnızca kurumsal Android cihazlar Android for Work olarak kaydolabilir.

Yeni ayarlarla çalışırken şunları göz önünde bulundurun:

#### <a name="if-you-have-never-previously-onboarded-android-for-work-enrollment"></a>Daha önce hiç Android for Work kaydı eklemediyseniz
Yeni Android for Work platformu varsayılan Cihaz Türü Kısıtlamalarında engellidir. Özelliği ekledikten sonra, cihazların Android for Work ile kaydolmasına izin verebilirsiniz. Bunu yapmak için varsayılan ayarı değiştirin veya varsayılan Cihaz Türü Kısıtlamasının yerine geçen yeni bir Cihaz Türü Kısıtlaması oluşturun.

#### <a name="if-you-have-onboarded-android-for-work-enrollment"></a>Android for Work kaydı eklediyseniz
Daha önceden eklediyseniz durumunuz seçtiğiniz ayara bağlıdır:

| Ayar | Varsayılan Cihaz Türü Kısıtlamasında Android for Work durumu | Notlar |
| --- | --- | --- |
| **Tüm cihazları Android olarak yönetme** | Engellendi | Tüm Android cihazların Android for Work ile kaydolması gerekir. |
| **Desteklenen cihazları Android for Work olarak yönetme** | İzin Verildi | Android for Work’ü destekleyen tüm Android cihazların Android for Work ile kaydolması gerekir. |
| **Yalnızca bu gruplardaki kullanıcılar için desteklenen cihazları Android for Work olarak yönetme** | Engellendi | Varsayılan ayarı geçersiz kılmak için ayrı bir Cihaz Türü Kısıtlama ilkesi oluşturuldu. Bu ilke önceden Android for Work kaydına izin vermek için seçtiğiniz grupları tanımlar. Seçili gruplardaki kullanıcıların Android for Work cihazlarını kaydetmesine izin verilir. Diğer tüm kullanıcıların Android for Work ile kaydolması kısıtlanır. |

Tüm durumlarda, hedeflenen düzenlemeniz korunur. Ortamınızda Android for Work’e genel olarak veya grup başına verilen izinleri tutmak için herhangi bir eylem gerçekleştirmeniz gerekmez.

Bu değişiklikler, Kasım güncelleştirmesi ile sunulmaya başlanacaktır ancak hesabınızda yürürlüğe girmesi zaman alabilir. Bu değişiklikler hesabınızda geçerli olduğunda Office 365 portalında bir onay bildirimi alacaksınız.

### <a name="support-for-multiple-network-device-enrollment-service-ndes-connectors----1528104---"></a>Çoklu Ağ Cihazı Kayıt Hizmeti (NDES) bağlayıcısı desteği <!-- 1528104 -->
NDES, etki alanı kimlik bilgileri olmadan çalışan mobil cihazların Basit Sertifika Kayıt Protokolü’nü (SCEP) temel alarak sertifikaları edinmesini sağlar. Bu güncelleştirme ile birden çok NDES bağlayıcısı desteklenir.

### <a name="new-scep-profile-details-supported----1559808---"></a>Desteklenen yeni SCEP profili ayrıntıları <!-- 1559808 -->
Yöneticiler Windows, iOS, macOS ve Android platformlarında bir SCEP profili oluştururken ek ayarlar yapabilecek.  Yöneticiler IMEI, seri numarası veya konu adı biçiminde e-posta dahil ortak ad ayarlayabilir.

### <a name="configure-an-ios-app-pin----1586774---"></a>iOS uygulama PIN’i yapılandırma <!-- 1586774 -->
Yakında, hedeflenen iOS uygulamaları için bir PIN’i zorunlu kılmanız mümkün olacaktır. PIN gereksinimini ve sona erme tarihi gün sayısını Azure portalında yapılandırabilirsiniz. Gerektiğinde, kullanıcının bir iOS uygulamasına erişmeden önce yeni bir PIN ayarlaması ve kullanması gerekli olacaktır. Yalnızca Intune Uygulama SDK’sı ile uygulama koruması etkinleştirilmiş iOS uygulamaları bu özelliği destekler.

### <a name="retain-data-during-a-factory-reset-----1588489---"></a>Fabrika sıfırlaması sırasında verileri tutma <!-- 1588489 -->
Windows Fabrika sıfırlamasına yönelik yeni bir özellik için destek ekliyoruz. Yöneticiler artık bir fabrika sıfırlaması sırasında cihaz kaydı ve diğer sağlanan verilerin cihazda tutulup tutulmayacağını belirtebilir. 
 
Fabrika sıfırlamasında aşağıdaki veriler tutulur:
- Cihazla ilişkilendirilen kullanıcı hesapları
- Makine durumu (etki alanına katılmış, AADJ)
- MDM kaydı
- OEM tarafından yüklenen uygulamalar (mağaza ve Win32 uygulamaları)
- Kullanıcı profili
- Kullanıcı profili dışındaki kullanıcı verileri
- Kullanıcı otomatik oturum açma
 
Şu veriler korunmaz:
- Kullanıcı dosyaları
- Kullanıcı tarafından yüklenen uygulamalar (mağaza ve Win32 uygulamaları)
- Varsayılan olmayan cihaz ayarları 

### <a name="app-install-status-report-now-a-bar-chart----1249446---"></a>Uygulama yükleme durum raporu artık çubuk grafiği şeklinde <!-- 1249446 -->  
Her bir uygulama için **Mobil uygulamalar** iş yükünde **Uygulama** listesi üzerinden erişilebilen **Uygulama yükleme durumu** raporu yakında çubuk grafik olarak işlenecek.

### <a name="add-find-my-iphone-for-personal-devices---1427287--"></a>Kişisel cihazlar için "iPhone’umu Bul" özelliği ekleme <!--1427287-->
iOS cihazlarda Etkinleştirme Kilidi’nin açık olup olmadığını görüntülemeniz mümkün olacaktır. Bu özellik önceden Intune’da klasik portalda bulunuyordu.

### <a name="group-assigned-enrollment-restrictions----747598---"></a>Gruba atanan kayıt kısıtlamaları <!-- 747598 -->
Bir Intune yöneticisi olarak, kullanıcı grupları için özel Cihaz Türü ve Cihaz Sınırı kayıt sınırlamaları oluşturabileceksiniz.
 
Intune Azure Portal her kısıtlama türü için en fazla 25 örnek oluşturmanıza olanak sağlar. Bunlar daha sonra kullanıcı gruplarına atanabilir. Grup tarafından atanan kısıtlamalar varsayılan kısıtlamaları geçersiz kılar.
 
Bir kısıtlama türünün tüm örnekleri kesin bir şekilde sıralanmış bir listede tutulur. Bu sıra, çakışmaları çözümlemek için bir öncelik değerini tanımlar. Birden fazla kısıtlama örneğinden etkilenen bir kullanıcı, yalnızca en yüksek öncelik değerine sahip örnek tarafından kısıtlanır. Belirli bir örneği listede farklı bir konuma sürükleyerek örneğin önceliğini değiştirebilirsiniz. 
 
Bu işlevsellik, Android for Work ayarlarının Android For Work kayıt menüsünden Kayıt Kısıtlamaları menüsüne geçişi ile birlikte yayımlanacak. Bu geçiş birkaç gün sürebileceğinden, grup atamasının Kayıt Kısıtlamaları için etkinleştirildiğini görmeden önce hesabınız Kasım yayınının diğer bölümleri için güncelleştirilebilir.

### <a name="windows-10-update-ring-assignments-are-displayed----1621837---"></a>Windows 10 güncelleştirme halkası atamaları görüntülenir <!-- 1621837 -->
**Sorun giderirken**, görüntülediğiniz kullanıcı için Windows 10 güncelleştirme halkası atamalarını görebilirsiniz.  



<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Azure Active Directory web siteleri, Intune Managed Browser Uygulaması gerektirebilir ve Managed Browser’da (Genel Önizleme) Çoklu Oturum Açma’yı destekler <!-- 710595 -->   
Azure Active Directory (Azure AD) kullanarak, mobil cihazlarda web sitelerine erişimi Intune Managed Browser uygulaması ile kısıtlayabileceksiniz. Web sitesi verileri, Managed Browser’da güvende ve son kullanıcının kişisel verilerinden ayrı bir yerde olacaktır. Managed Browser ayrıca Azure AD ile korunan sitelerde Çoklu Oturum Açma işlevlerini de destekleyecektir. Managed Browser’da oturum açmak veya Intune tarafından yönetilen başka bir uygulamanın bulunduğu bir cihazda Managed Browser’ı kullanmak, kullanıcıların kimlik bilgilerini girmelerine gerek kalmaksızın Managed Browser’ın Azure AD ile korunan sitelere erişmesine olanak tanır. Bu özellik, Outlook Web Access (OWA) ve SharePoint Online’ın yanı sıra Azure Uygulama Proxy’si yoluyla erişilen intranet kaynakları gibi diğer kurumsal sitelerde de geçerlidir.

### <a name="troubleshoot-enrollment-issues------746324----"></a>Kayıt sorunlarını giderme  <!--- 746324 --->  
Sorun giderme çalışma alanı, kullanıcı kayıt sorunlarını gösterecektir. Sorunun ayrıntıları ve önerilen düzeltme adımları, yönetici ve yardım masası çalışanlarının sorunları çözmesine yardımcı olabilir. Bazı kayıt sorunları burada yer almaz ve bazı hatalar için düzeltme önerileri bulunmayabilir.


















<!-- the following are present prior to 1710 -->



### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a>Windows 10 sürüm yükseltme ilkesi desteği <!-- 903672(archived), 1119689 -->  
Windows 10 cihazları; Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education ve Windows 10 Professional Education N’e yükselten bir Windows 10 sürüm yükseltme ilkesi oluşturabileceksiniz. Windows 10 sürüm yükseltmeleri hakkında daha fazla bilgi için bkz. [Windows 10 sürüm yükseltmelerini yapılandırma](edition-upgrade-configure-windows-10.md).




<!-- the following are present prior to 1709 -->



### <a name="android-for-work-support-for-lookout----1087312---"></a>Lookout için Android for Work desteği <!-- 1087312 -->   
Lookout kullanan Intune bağlayıcısı, Lookout for Work uygulamasını kullanan Android for Work cihazlarını destekleyecektir. Lookout uygulamasını kapsayıcının içinde veya dışında dağıtabilirsiniz.

### <a name="intune-app-protection-and-citrix-mdx-development-tools----709185---"></a>Intune Uygulama Koruması ve Citrix MDX Geliştirme Araçları<!-- 709185 -->
Cihazları ve uygulamaları Citrix XenMobile MDX ve Microsoft Intune bileşimi ile yönetebilirsiniz. Bu, Citrix’in mVPN teknolojisini kullanırken uygulamaları Intune uygulama koruması ilkesiyle yönetmenize olanak sağlar.

iOS ve Android için Citrix MDX mVPN teknolojisiyle tümleştiren, Intune Uygulama Sarmalama Aracı ve Intune Uygulama SDK’sını içeren bir kod deposu bulabilirsiniz.


### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Yüksek kullanılabilirlik desteği ile şirket içi Exchange bağlayıcısı <!-- 676614 -->   
Şirket içi Exchange bağlayıcısı için birden çok İstemci Erişimi Sunucusu (CAS) rolü kullanabilirsiniz. Örneğin ana CAS hata verirse Exchange bağlayıcısı diğer CAS’lere geçmek için bir sorgu alır. Bu özellik sayesinde hizmet asla kesilmez.

### <a name="system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Exchange bağlayıcısı için System Center Operations Manager yönetim paketi <!-- 885457 -->   
Exchange bağlayıcısı günlüklerini ayrıştırmanıza yardımcı olmak amacıyla Exchange bağlayıcısı için System Center Operations Manager yönetim paketi kullanıma sunulacak. Bu yönetim paketi, sorun gidermeniz gerektiğinde Intune'u izlemek için size farklı yollar sunar.





## <a name="intune-apps"></a>Intune uygulamaları

### <a name="helping-your-users-help-themselves-with-the-company-portal-app-for-android----1573324-1573150-1558616-1564878---"></a>Kullanıcılarınızın Android için Şirket Portalı uygulamasını kullanmasına yardımcı olma <!---1573324, 1573150, 1558616, 1564878--->
Android için Şirket Portalı uygulaması, son kullanıcıların yeni kullanım durumlarını anlamaları ve mümkün olduğunda kendi kendilerine çözümlemeleri için yönergeler eklemektedir. 

- Şifreleme için bir uyumluluk ilkesinin dağıtıldığını ancak cihaz üreticisinin [Google’ın önerilen yönergelerine](https://developer.android.com/reference/android/app/admin/DevicePolicyManager.html#setStorageEncryption(android.content.ComponentName, boole) uygun olarak [cihazı şifrelemediğini](/intune-user-help/your-device-appears-encrypted-but-cp-says-otherwise-android) açıklayan yeni bir ileti görüntülenir.
- Son kullanıcılar ekleyebilecekleri en fazla cihaz sayısına ulaştıysa bir cihazı kaldırmak üzere (Azure Active Directory portalına)[https://account.activedirectory.windowsazure.com/r/#/profile] yönlendirilir. 
- Son kullanıcılara [Samsung KNOX cihazlarında etkinleştirme hatalarını düzeltmek](https://go.microsoft.com/fwlink/?linkid=859718) veya [güç tasarrufu modunu devre dışı bırakmak](/intune-user-help/power-saving-mode-android) için izlenecek adımlar verilir. Bu çözümlerden biri sorunları çözmezse [günlükleri Microsoft’a göndermeye](/intune-user-help/send-logs-to-microsoft-ios) yönelik bir açıklama sağlarız. 


### <a name="new-resolve-action-available-for-android-devices----1583480---"></a>Android cihazlar için yeni 'Çözümleme' eylemi kullanılabilir <!---1583480--->
Android için Şirket Portalı uygulaması _Cihaz ayarlarını güncelleştirme_ sayfasında bir 'Çözümleme' eylemi tanıtıyor. Bu seçeneği belirlemek son kullanıcıyı doğrudan cihazlarının uyumsuz olmasına neden olan ayara götürür. Android için Şirket Portalı uygulaması şu anda bu eylemi [cihaz geçiş kodu](/intune-user-help/set-your-pin-or-password-android), [cihaz şifrelemesi](/intune-user-help/encrypt-your-device-android), [USB hata ayıklama](/intune-user-help/you-need-to-turn-off-usb-debugging-android) ve [Bilinmeyen Kaynaklar](/intune-user-help/you-need-to-turn-off-unknown-sources-android) ayarları için destekler. 




<!-- the following are present prior to 1711 -->


### <a name="redirecting-macos-users-to-our-new-company-portal-app---1380728--"></a>macOS kullanıcılarını yeni Şirket Portalı uygulamamıza yönlendirme <!--1380728-->   
Bir son kullanıcı, macOS cihazını kaydetmek için Şirket Portalı web sitesinde oturum açtığında, işlemi tamamlamak için yeni macOS Şirket Portalı uygulamasını indirmek üzere yönlendirilecektir. Bu durum, OS X El Capitan 10.11 ve üzeri sürümleri kullanan macOS cihazlarda görülür. 


<!-- the following are present prior to 1710 -->



### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment----1334712---"></a>Kayıt durumuna bakılmaksızın kullanılabilir olan uygulamalar artık kayıt istemi yapılmadan yüklenebilir. <!-- 1334712 -->
Android Şirket Portalı uygulamasındaki kayıt durumuna bakılmaksızın kullanılabilir olan şirket uygulamaları, kayıt için istem yapılmadan yüklenebilir.


<!-- the following are present prior to 1709 -->

### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a>iOS ve Android için Intune Managed Browser desteği <!-- 1374196 -->
Ekim 2017 itibariyle Android uygulamasındaki Intune Managed Browser uygulaması yalnızca Android 4.4 ve sonraki sürümleri çalıştıran cihazları destekleyecektir. iOS’taki Intune Managed Browser uygulaması yalnızca iOS 9.0 ve sonraki sürümleri çalıştıran cihazları destekleyecektir. Android ve iOS’un daha eski sürümleri Managed Browser'ı kullanmaya devam edebilecek, ancak uygulamanın yeni sürümlerini yükleyemeyecek ve uygulamanın tüm özelliklerine erişemeyecektir. Bu cihazları desteklenen işletim sistemi sürümüne güncelleştirmenizi öneririz.


### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Kullanıcı, izin verilen en yüksek cihaz kaydı sayısına ulaştığında gösterilen hata iletisi iyileştirildi <!-- 1270370 -->
Genel bir hata iletisi yerine, son kullanıcılar kolay, işlem yapılabilir bir hata iletisi görür: “BT yöneticiniz tarafından izin verilen en yüksek cihaz kaydı sayısına ulaştınız. Lütfen kayıtlı bir cihazı kaldırın veya BT yöneticinizden yardım alın.”




## <a name="notices"></a>Bildirimler

Şu anda etkin bildirim yok.




### <a name="see-also"></a>Ayrıca bkz.
Son geliştirmelere ilişkin ayrıntılar için bkz. [Microsoft Intune’daki Yenilikler](whats-new.md).
