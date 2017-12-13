---
title: "Erken sürüm"
description: 
keywords: 
author: ErikjeMS
ms.author: erikje
manager: angrobe
ms.date: 11/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 35bf193563deb34ac59df245c622bbc011d80b76
ms.sourcegitcommit: 67ec0606c5440cffa7734f4eefeb7121e9d4f94f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/08/2017
---
# <a name="the-early-edition-for-microsoft-intune---december-2017"></a>Microsoft Intune için Erken Sürüm - Aralık 2017

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

### <a name="app-protection-policies-----679615---"></a>Uygulama koruma ilkeleri  <!-- 679615 -->
Intune Uygulama Koruma İlkeleri, tüm kiracıdaki tüm kullanıcılar için hızlı bir şekilde koruma sağlamaya yönelik genel ve varsayılan ilkeler oluşturma olanağı sunar.

### <a name="revoking-ios-volume-purchase-program-apps-----820863---"></a>iOS - Toplu Satın Alma Programı uygulamalarını iptal etme <!-- 820863 -->
Bir veya daha fazla iOS Toplu Satın Alma Programı (VPP) uygulaması olan belirli bir cihaz için, cihaz için ilişkili cihaza dayalı uygulama lisansını iptal edebilirsiniz. Bir uygulama lisansını iptal etmek ilgili VPP uygulamasını cihazdan kaldırmaz. Bir VPP uygulamasını kaldırmak için, atama işlemini **Kaldır** olarak değiştirmelisiniz. Daha fazla bilgi için bkz. [Microsoft Intune ile toplu satın alma programından satın alınan iOS uygulamalarını yönetme](vpp-apps-ios.md).

### <a name="revoke-licenses-for-an-ios-volume-purchasing-program-token----820870---"></a>Bir iOS Toplu Satın Alma Programı belirteci için lisansları iptal et <!-- 820870 -->
Belirli bir VPP Belirteci için tüm iOS Toplu Satın Alma Programı (VPP) uygulamalarının lisansını iptal edebilirsiniz.

### <a name="delete-an-ios--volume-purchasing-program-token----820879---"></a>Bir iOS Toplu Satın Alma Programı belirtecini silin <!-- 820879 -->
Konsolu kullanarak iOS Toplu Satın Alma Programı (VPP) belirtecini silmek mümkündür. VPP belirteci kopya örnekleriniz olduğunda bu gerekli olabilir.

### <a name="network-access-control-nac-device-check-in-reporting-----1232250---"></a>Ağ Erişim Denetimi (NAC) cihaz iade raporlama <!-- 1232250 -->
Bu değişiklikten önce BT yöneticileri, NAC tarafından yönetilen bir cihazın Intune tarafında kendi NAC çözümü ile iletişim kurup kurmadığını belirleyemedi. NAC tarafından yönetilen bir cihaz kendi NAC çözümü ile iletişim kurmadığında, cihaz NAC çözümüyle uyumlu değildir ve bu nedenle NAC çözümü tarafından engellenmiş ve daha sonra cihaz uyumluluk durumuna bağlı koşullu erişim ilkeleri tarafından engellenmiştir.

Bu değişiklikle, IT yöneticileri hangi NAC yönetim cihazlarının kendi NAC çözümleriyle başarıyla iletişim kurup kuramadıklarını görebilirler. Bu yeni yetenek, Intune içindeki Cihaz uyumluluk iş yükünde bulunan iki yeni izleme işlevinden oluşur; istatistikler aşağıda gösterilmiştir:
- **Son bir saatteki ortalama NAC çağrıları**
- **Son NAC gelen istek (tarih / saat)**

### <a name="new-ios-device-action------1244701---"></a>Yeni iOS cihaz eylemi  <!-- 1244701 -->
IOS 10.3 denetlenen cihazları kapatabilirsin. Bu eylem, son kullanıcıya herhangi bir uyarı yapılmadan cihazı hemen kapatır. **Cihaz** iş yükünde bir cihaz seçtiğinde, cihaz özelliklerinde **Kapat (yalnızca denetimli)** eylemi bulunabilir.

### <a name="multiple-connector-support-for-scep-and-pfx-certificate-handling----1361755-eeready---"></a>SCEP ve PFX sertifika işleme için birden çok bağlayıcı desteği <!-- 1361755 eeready -->
Şirket içi NDES bağlayıcısı kullanan müşteriler, tek bir kiracıda birden fazla bağlayıcıyı yapılandırarak sertifikaları cihazlara teslim edebilir.

Bu yeni yetenek aşağıdaki senaryoyu destekler:

- **Yüksek kullanılabilirlik**

    Her bir NDES bağlayıcısı, Intune'dan sertifika istekleri çeker.  Bir NDES Bağlayıcısı çevrimdışı olursa, diğer bağlayıcı istekleri işlemeye devam edebilir.

### <a name="new-automatic-redeployment-setting----1469168---"></a>Yeni otomatik yeniden dağıtım ayarı<!-- 1469168 -->
Bu ayar, yönetici haklarına sahip olan kullanıcıların cihaz kilidi ekranında **CTRL + Win + R** tuşunu kullanarak tüm kullanıcı verilerini ve ayarlarını silmelerini sağlar. Cihaz otomatik olarak yeniden yapılandırılacak ve yönetime yeniden kaydedilecektir.

Bu ayar, Windows 10 -> Aygıt kısıtlamaları -> Genel -> Otomatik yeniden dağıtma altında bulunabilir.

### <a name="install-office-apps-on-macos-devices----1494311---"></a>MacOS cihazlarda Office uygulamalarını yükleyin <!-- 1494311 -->
Office uygulamalarını macOS cihazlara yükleyebilirsin. Bu yeni uygulama türü, Word, Excel, PowerPoint, Outlook ve OneNote yüklemeye izin verir. Bu uygulamalar uygulamalarınızı güvenli ve güncel tutmaya yardımcı olmak için ayrıca Microsoft AutoUpdater (MAU) ile gelir.

### <a name="surface-hub-resource-account-supported----1566442-eeready---"></a>Surface Hub kaynak hesabını destekler <!-- 1566442 eeready -->
Yeni bir cihaz eylemi eklenecektir; böylece yöneticiler bir Surface Hub ile ilişkili kaynak hesabını tanımlayıp güncelleyebilir.

Kaynak hesabı, Skype/Exchange ile kimlik doğrulaması yapmak için bir Surface Hub tarafından kullanılır; böylece bir toplantıya katılabilir. Eşsiz bir kaynak hesabı oluşturabilir; böylece Surface Hub toplantıdaki konferans odası olarak görünür. Örneğin, kaynak hesabı *Konferans Salonu B41/6233* olarak görünebilir. Surface Hub için kaynak hesabı (cihaz hesabı olarak bilinir), genellikle Konferans odası konumu için ve diğer kaynak hesabı parametreleri değiştirilmesi gerektiğinde yapılandırılması gerekir.

Yöneticiler bir cihazdaki kaynak hesabını güncelleştirmek istediği zaman, cihazla ilişkili geçerli Active Directory/Azure Active Directory kimlik bilgilerini sağlamaları gerekir. Cihaz için parola rotasyonu açıksa, yöneticiler parolayı bulmak için Azure Active Directory'ye gitmelidir.

> [!NOTE]
> Tüm alanlar bir paket halinde gönderilir ve daha önce yapılandırılmış olan tüm alanların üzerine yazılır. Boş alanlar var olan alanların üzerine yazılır.

Yöneticilerin yapılandırabileceği ayarlar şunlardır:

- **Kaynak hesabı**  

   - **Active Directory kullanıcısı**   
   EtkiAlanıAdı\KullanıcıAdı veya Kullanıcı Asıl Adı (UPN):user@domainname.com
   - **Parola**


- **İsteğe bağlı kaynak hesabı parametreleri** (belirtilen kaynak hesabını kullanarak ayarlanması gerekir)
   - **Parola rotasyon süresi**   
     Güvenlik nedeniyle, hesap şifresinin her hafta Surface Hub tarafından güncellenmesini sağlar. Bu etkinleştirildikten sonra parametreleri yapılandırmak için, Azure Active Directory'deki hesapta önce parolanın sıfırlanması gerekir.

   - **SIP (Oturum Başlatma Protokolü) adresi**    
     Yalnızca otomatik bulma başarısız olduğunda kullanılır.

   - **E-posta**    
     Cihaz/kaynak hesabının e-posta adresi.

   - **Exchange Sunucusu**    
     Yalnızca otomatik bulma başarısız olduğunda gereklidir.

   - **Takvim eşitleme**    
     Takvim eşitleme ve diğer Exchange server hizmetlerini etkinleştirilip etkinleştirilmeyeceğini belirtir. Örneğin: Toplantı eşitleme.

### <a name="intune-now-provides-the-account-move-operation-----1573558-1579830---"></a>Intune şimdi Hesap Taşıma işlemi sağlıyor <!-- 1573558, 1579830 -->
**Hesap Taşıma** bir kiracıyı bir Azure Ölçeği Birimi'nden (ASU) diğerine taşır. **Hesap Taşı**, hem bunu isteyen Intune destek ekibini aradığınızda istemci tarafından başlatılan senaryolar için, hem de Microsoft'un arka uç hizmetinde ayarlamalar yapması gereken Microsoft tarafından yönetilen bir senaryo olarak kullanılabilir. **Hesap Taşıma** sırasında kiracı salt okunur moda (ROM) girer. ROM süresi boyunca kayıt yaptırma, cihazları yeniden adlandırma, uyumluluk durumunu güncelleme gibi servis işlemleri başarısız olur.

### <a name="new-windows-defender-security-center-wdsc-device-configuration-profile-settings----1335507---"></a>Yeni Windows Defender Güvenlik Merkezi (WDSC) cihaz yapılandırma profili ayarları <!-- 1335507 -->
Intune, cihaz yapılandırma profili ayarlarının Uç nokta koruma altında **Windows Defender Güvenlik Merkezi** adında yeni bir bölüm ekler. BT yöneticileri, son kullanıcıların Windows Defender Güvenlik Merkezi uygulamasının hangi sütunlarına erişebileceklerini yapılandırabilir. Bir BT yöneticisi Windows Defender Güvenlik Merkezi uygulamasında bir sütun gizlerse, gizli sütunlarla ilgili hiçbir bildirim kullanıcının cihazında görüntülenmez.

Yöneticilerin Windows Defender Güvenlik Merkezi aygıt yapılandırma profili ayarlarından gizleyebilecekleri sütunlar şunlardır:
- Virüs ve tehdit koruması
- Cihaz performans ve sistem durumu
- Güvenlik duvarı ve ağ korumaları
- Uygulama ve tarayıcı denetimi
- Aile seçenekleri

BT yöneticileri, kullanıcıların hangi bildirimleri aldığını da özelleştirebilir. Örneğin, kullanıcıların WDSC'deki görünür sütunlar tarafından oluşturulan tüm bildirimleri alıp almayacaklarını veya yalnızca kritik bildirimleri alıp almayacaklarını yapılandırabilirsiniz. Kritik olmayan bildirimlere, Windows Defender Antivirus etkinliğinin periyodik özetleri ve taramalar tamamlandığında verilen bildirimler dahildir. Diğer tüm bildirimler kritik olarak kabul edilir. Ayrıca, bildirim içeriğini kendiniz de özelleştirebilirsiniz, örneğin, kullanıcıların cihazlarında görünen bildirimlere eklemek için BT iletişim bilgilerini sağlayabilirsiniz.




<!-- the following are present prior to 1712 -->
### <a name="assign-office-365-mobile-apps-to-ios-and-android-devices-using-built-in-app-type----1332318---"></a>Yerleşik uygulama türü kullanarak Office 365 mobil uygulamaları iOS ve Android cihazlara atama <!-- 1332318 -->
**Yerleşik** uygulama türü yönettiğiniz iOS and ve Android cihazlar için Office 365 uygulamaları oluşturmayı ve atamayı kolaylaştırır. Bu uygulamalar Word, Excel, PowerPoint ve OneDrive gibi 0365 uygulamalarını içerir. Uygulama türüne belirli uygulamalar atayabilir ve uygulama bilgileri yapılandırmasını düzenleyebilirsiniz.

### <a name="single-sign-on-support-for-ios----1333645---"></a>iOS için Çoklu Oturum Açma desteği <!-- 1333645 -->  
iOS kullanıcıları için Çoklu Oturum Açma kullanabileceksiniz. Çoklu Oturum Açma yükünde kullanıcı kimlik bilgilerini aramak için kodlanan iOS uygulamaları bu yük yapılandırması güncelleştirmesi ile işlevseldir. Asıl Ad ve Bölgeyi yapılandırmak için UPN ve Intune Cihaz Kimliğini de kullanabilirsiniz.

### <a name="text-protocol-allowed-from-managed-apps----1414050----"></a>Yönetilen Uygulamalar izin verilen metin protokolü <!-- 1414050  -->
Intune Uygulama SDK’sı tarafından yönetilen uygulamalar SMS mesajları gönderebilir.

### <a name="remotely-lock-managed-macos-device-with-intune----1437691---"></a>Intune ile yönetilen macOS cihazları uzaktan kilitleme <!-- 1437691 -->
Kayıp bir macOS cihazı kilitleyerek 6 haneli bir kurtarma PIN’i ayarlamanız mümkün olacaktır. Kilitliyken, **Cihaza genel bakış** dikey penceresi başka bir cihaz eylemi gönderilene kadar PIN’i görüntüler.

Daha fazla bilgi için bkz. [Intune ile yönetilen cihazları uzaktan kilitleme](device-remote-lock.md).


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


### <a name="configure-an-ios-app-pin----1586774---"></a>iOS uygulama PIN’i yapılandırma <!-- 1586774 -->
Yakında, hedeflenen iOS uygulamaları için bir PIN’i zorunlu kılmanız mümkün olacaktır. PIN gereksinimini ve sona erme tarihi gün sayısını Azure portalında yapılandırabilirsiniz. Gerektiğinde, kullanıcının bir iOS uygulamasına erişmeden önce yeni bir PIN ayarlaması ve kullanması gerekli olacaktır. Yalnızca Intune Uygulama SDK’sı ile uygulama koruması etkinleştirilmiş iOS uygulamaları bu özelliği destekler.

### <a name="add-find-my-iphone-for-personal-devices---1427287--"></a>Kişisel cihazlar için "iPhone’umu Bul" özelliği ekleme <!--1427287-->
iOS cihazlarda Etkinleştirme Kilidi’nin açık olup olmadığını görüntülemeniz mümkün olacaktır. Bu özellik önceden Intune’da klasik portalda bulunuyordu.

<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Azure Active Directory web siteleri, Intune Managed Browser Uygulaması gerektirebilir ve Managed Browser’da (Genel Önizleme) Çoklu Oturum Açma’yı destekler <!-- 710595 -->   
Azure Active Directory (Azure AD) kullanarak, mobil cihazlarda web sitelerine erişimi Intune Managed Browser uygulaması ile kısıtlayabileceksiniz. Web sitesi verileri, Managed Browser’da güvende ve son kullanıcının kişisel verilerinden ayrı bir yerde olacaktır. Managed Browser ayrıca Azure AD ile korunan sitelerde Çoklu Oturum Açma işlevlerini de destekleyecektir. Managed Browser’da oturum açmak veya Intune tarafından yönetilen başka bir uygulamanın bulunduğu bir cihazda Managed Browser’ı kullanmak, kullanıcıların kimlik bilgilerini girmelerine gerek kalmaksızın Managed Browser’ın Azure AD ile korunan sitelere erişmesine olanak tanır. Bu özellik, Outlook Web Access (OWA) ve SharePoint Online’ın yanı sıra Azure Uygulama Proxy’si yoluyla erişilen intranet kaynakları gibi diğer kurumsal sitelerde de geçerlidir.


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
