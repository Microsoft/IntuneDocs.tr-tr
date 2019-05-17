---
title: iOS uygulama koruma ilkesi ayarları
titleSuffix: Microsoft Intune
description: Bu konu başlığı altında iOS cihazları için iOS uygulama koruma ilkesi (APP) ayarları açıklanır.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/12/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 0f8b08f2-504c-4b38-bea2-b8a4ef0526b8
ms.reviewer: demerson
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 25fd89335d290cef5d100d58fddf7cbd56370393
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2019
ms.locfileid: "59895702"
---
#  <a name="ios-app-protection-policy-settings"></a>iOS uygulama koruma ilkesi ayarları
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bu makalede iOS cihazları için uygulama koruma ilkesi ayarları açıklanır. Açıklanan ilke ayarları, yeni bir ilke yaparken Azure portalındaki **Ayarlar** dikey penceresinde bir uygulama koruma ilkesi için [yapılandırılabilir](app-protection-policies.md).

İlke ayarları üç kategoriye ayrılır: *Verileri yeniden konumlandırma*, *Erişim gereksinimleri* ve *Koşullu başlatma*. Bu makalede ***ilkeyle yönetilen uygulamalar*** terimi, uygulama koruma ilkeleriyle yapılandırılan uygulamaları ifade eder.

##  <a name="data-protection"></a>Veri koruma

### <a name="data-transfer"></a>Veri Aktarımı
| Ayar | Nasıl kullanılır? | Varsayılan değer |
|------|----------|-------|
| **Kuruluş verilerini iTunes'a yedekleme ve iCloud yedeklemeleri** | Bu uygulamanın iş veya okul verilerini iTunes veya iCloud’a yedeklemesini engellemek için **Engelle**'yi seçin. Bu uygulamanın iş veya okul verilerini iTunes veya iCloud’a yedeklemesine izin vermek için **İzin Ver**'i seçin. | **İzin ver**  |
| **Kuruluş verilerini başka uygulamalara gönderme** | Hangi uygulamaların bu uygulamadan veri alabileceğini belirtin: <ul><li>**Tüm uygulamalar**: Tüm uygulamalara aktarıma izin verir.</li><li>**Hiçbiri**: İlkeyle yönetilen diğer uygulamalar da dahil olmak üzere hiçbir uygulamaya veri aktarmaya izin verilmez.</li><li> **İlkeyle yönetilen uygulamalar**: Yalnızca ilkeyle yönetilen diğer uygulamalara aktarım yapılmasına izin verilir.</li><li>**İşletim sistemi paylaşımı ile ilke tarafından yönetilen uygulamalar**: Yalnızca ilke tarafından yönetilen diğer uygulamalara veri aktarımına ve kayıtlı cihazlarda MDM tarafından yönetilen diğer uygulamalara dosya aktarımına izin verilir.<p><p>**Not:** _**İşletim sistemi paylaşımı ile ilke tarafından yönetilen uygulamalar** değeri, yalnızca MDM’ye kayıtlı cihazlara uygulanabilir. Bu ayar kayıtsız bir cihazdaki kullanıcıyı hedeflerse, **İlke ile yönetilen uygulamalar** değerinin davranışı geçerlidir._<p><p></li><li>**Şurada Aç/Paylaş filtresi ile ilke tarafından yönetilen uygulamalar**: Yalnızca ilke ile yönetilen diğer uygulamalara aktarıma ve işletim sistemi Şurada aç/Paylaş iletişim kutularını yalnızca ilke ile yönetilen uygulamaları görüntülemek üzere filtrelemeye izin verilir.<p><p>**Not:** _**Şurada Aç/Paylaş** iletişim kutusunun filtrelenmesini yapılandırmak için hem dosya/belge kaynağı işlevi gören uygulamalarda hem de bu dosyayı/belgeyi açabilen uygulamalarda iOS sürüm 8.1.1 veya üzeri için Intune SDK’sı bulunmalıdır._<p><p></li></ul><br>Ayrıca **İlke ile yönetilen uygulamalar** veya **Hiçbiri** olarak ayarlandığında, Spotlight Arama'nın uygulamalar içinde veri aramasına izin veren iOS 9 özelliği engellenir. <p><p>Bu ilke, iOS Evrensel Bağlantılar için de geçerlidir.  Genel web bağlantıları **Uygulama bağlantılarını Intune Managed Browser'da aç** ilke ayarıyla yönetilir. <p> Intune’un varsayılan olarak veri aktarımı hedefi olarak izin verebileceği bazı muaf uygulamalar ve hizmetler vardır. Buna ek olarak, verilerin Intune APP'yi desteklemeyen bir uygulamaya aktarılmasına izin vermeniz gerekiyorsa kendi muafiyetlerinizi oluşturabilirsiniz. Daha fazla bilgi için bkz. [veri aktarımı muafiyetleri](#data-transfer-exemptions).  | **Tüm uygulamalar**   |
| <ul><ui> **Dışarıda tutulacak uygulamaları seçin** | Bu seçenek, önceki seçenekte *İlke ile yönetilen uygulamalar* seçildiğinde kullanılabilir duruma gelir.   |   |
| **Diğer uygulamalardan veri al** | Hangi uygulamaların bu uygulamaya veri aktarabileceğini belirtin: <ul><li>**Tüm uygulamalar**: Tüm uygulamalardan veri aktarımına izin verir.</li><li>**Hiçbiri**: İlkeyle yönetilen diğer uygulamalar da dahil olmak üzere hiçbir uygulamadan veri aktarmaya izin verilmez.</li><li>**İlkeyle yönetilen uygulamalar**: Yalnızca ilkeyle yönetilen diğer uygulamalardan aktarım yapılmasına izin verilir.</li><li>**Gelen Kuruluş verileriyle tüm uygulamalar**: Tüm uygulamalardan veri aktarımına izin verir. Kullanıcı kimliği olmayan tüm gelen veriler, kuruluşunuzdan gelen veriler olarak ele alınır. Veriler, `IntuneMAMUPN` ayarı tarafından tanımlandığı şekliyle MDM kayıtlı kullanıcının kimliğiyle işaretlenir.<p><p>**Not:** _**Gelen kuruluş verileriyle tüm uygulamalar** değeri, yalnızca MDM’ye kayıtlı cihazlara uygulanabilir. Bu ayar kayıtsız bir cihazdaki kullanıcıyı hedeflerse **Herhangi bir uygulama** değerinin davranışı geçerlidir._</li></ul> Intune’un veri aktarımı kaynağı olarak izin verebileceği bazı muaf uygulamalar ve hizmetler vardır. Uygulama ve hizmetlerin tam listesi için bkz. [Veri aktarımı muafiyetleri](#data-transfer-exemptions). Kayıtlı olmayan iOS cihazlarındaki çok kimlikli MAM etkin uygulamalar bu ilkeyi yoksayar ve tüm gelen verilere izin verir.<br><br> | **Tüm uygulamalar**    |
| **Kuruluş verilerinin kopyalarını kaydet** | Bu uygulamada *Farklı Kaydet* seçeneğinin kullanımını devre dışı bırakmak için **Engelle**'yi seçin. *Farklı Kaydet*'in kullanılmasına izin vermek istiyorsanız **İzin Ver**'i seçin. <br><br>**Not:** *Bu ayar Microsoft Excel, OneNote, Outlook, PowerPoint ve Word için desteklenir. Ayrıca üçüncü taraf ve iş kolu uygulamaları tarafından da desteklenebilir.* <br><br> *Engelle*'ye ayarladığınızda, *Kullanıcının seçili hizmetlere kopya kaydetmesine izin ver* ayarını yapılandırabilirsiniz.   | <br><br> **İzin ver**   |
| <ul><ui> **Kullanıcının seçili hizmetlere kopya kaydetmesine izin ver** | Kullanıcılar, seçili hizmetlere (OneDrive İş, SharePoint ve Yerel Depolama) kaydedebilir. Diğer tüm hizmetler engellenir.| **0 seçili**  |
| **Diğer uygulamalar arasında kesme, kopyalama ve yapıştırmayı kısıtla** | Bu uygulamada kes, kopyala ve yapıştır eylemlerinin ne zaman kullanılabileceğini belirtin. Aşağıdakilerden birini seçin: <ul><li>**Engellendi**:  Bu uygulama ve diğer herhangi bir uygulama arasında kesme, kopyalama ve yapıştırma eylemlerine izin verilmez.</li><li>**İlkeyle yönetilen uygulamalar**: Bu uygulama ve diğer ilkeyle yönetilen uygulamalar arasında kesme, kopyalama ve yapıştırma eylemlerine izin verilir.</li><li>**İçine yapıştırmayla ilke ile yönetilen**: Bu uygulama ve diğer ilkeyle yönetilen uygulamalar arasında kesme veya kopyalama eylemine izin verilir. Herhangi bir uygulamadan verilerin bu uygulamaya yapıştırılmasına izin verir.</li><li>**Herhangi bir uygulama**: Bu uygulamaya veya bu uygulamadan kesme, kopyalama ve yapıştırma eylemleriyle ilgili bir kısıtlama olmaz.</ul> | **Herhangi bir uygulama**   |
| **Herhangi bir uygulama için kesme ve kopyalama karakter sınırı** | Kuruluş verileri ve hesaplardan kesilebilecek veya kopyalanabilecek karakter sayısını belirtin.  Bu ayar, **Diğer uygulamalarla kesme, kopyalama ve yapıştırmayı kısıtla** ayarına bakılmaksızın belirtilen sayıda karakterin herhangi bir uygulamayla paylaşılmasına izin verir.<p>Varsayılan Değer = 0<p>**Not**: Uygulamanın Intune SDK sürüm 9.0.14 veya üstü olmasını gerektirir.  | **0**   |


### <a name="encryption"></a>Şifreleme
| Ayar | Nasıl kullanılır? | Varsayılan değer |
|------|----------|-------|
| **Kuruluş verilerini şifreleme** | Bu uygulamada iş veya okul verilerinin şifrelenmesini etkinleştirmek için Gerekli’yi seçin.  Intune, cihaz kilitliyken uygulama verilerini korumak için iOS cihaz şifrelemesini zorunlu tutar.  Uygulamalar Intune APP SDK şifrelemesini kullanıp isteğe bağlı olarak uygulama verilerini şifreleyebilir.  Intune APP SDK, uygulama verilerine 128 bit AES şifrelemesi uygulamak için iOS şifreleme yöntemlerini kullanır. <br><br> Bu ayarı etkinleştirdiğinizde kullanıcının cihazına erişmesi için bir PIN ayarlaması ve bu PIN’i kullanması gerekebilir. Cihaz PIN’i ayarlanmadıysa ve şifreleme gerekiyorsa "Kuruluşunuz, bu uygulamaya erişmek için öncelikle bir cihaz PIN’i etkinleştirmenizi gerektiriyor" iletisiyle birlikte kullanıcıdan bir PIN ayarlaması istenir. <br><br> Hangi iOS şifreleme modüllerinin FIPS 140-2 sertifikalı veya FIPS 140-2 sertifikası bekliyor olduğunu görmek için [resmi Apple belgelerine](https://support.apple.com/en-us/HT202739) gidin. | **Gerekli**  |


### <a name="functionality"></a>İşlevi
| Ayar | Nasıl kullanılır? | Varsayılan değer |
|------|----------|-------|
| **Uygulamaları yerel kişiler uygulamasıyla eşitle** |  Uygulamanın cihazdaki yerel Kişiler bölümüne veri kaydetmesini engellemek için **Devre Dışı Bırak**'ı seçin. **Etkinleştir**'i seçerseniz uygulama cihazdaki yerel Kişiler uygulamasına veri kaydedebilir. <br><br>Uygulamadan iş veya okul verilerini kaldırmak için seçmeli silme gerçekleştirdiğinizde, yerel Kişiler uygulamasına doğrudan uygulamadan eşitlenen kişiler kaldırılır. Yerel adres defterinden başka bir dış kaynağa eşitlenen kişiler silinemez. Şu anda bu özellik yalnızca Microsoft Outlook uygulaması için geçerlidir.   | **Etkinleştir**  |
| **Kuruluş verilerini yazdırma** | Uygulamanın iş veya okul verilerini yazdırmasını engellemek için **Devre Dışı Bırak**'ı seçin.   | **Etkinleştir**  |
| **İlkeyle yönetilen tarayıcılarla Web içeriği paylaş** | İlkeyle yönetilen uygulamalarda web içeriklerinin (http/https bağlantılarının) nasıl açıldığını belirtin. Aşağıdakilerden birini seçin: <ul><li>**İlkeyle yönetilen tarayıcılar**: Web içeriklerinin yalnızca ilkeyle yönetilen tarayıcılarda açılmasına izin verin.</li><li>**Herhangi bir uygulama**: Web bağlantılarının herhangi bir uygulamada açılmasına izin verin </li></ul> Cihazlarınızı yönetmek için Intune kullanıyorsanız bkz. [Microsoft Intune'la Managed Browser ilkelerini kullanarak İnternet erişimini yönetme](app-configuration-managed-browser.md).<br><br>**İlkeyle yönetilen tarayıcılar**<br>İlkeyle yönetilen tarayıcılardan birden fazla dağıtırsanız, bunların yalnızca biri başlatılır.  Başlatma sırası, Intune Managed Browser ve ardından Microsoft Edge şeklindedir.<p>İlkeyle yönetilen bir tarayıcı gerekliyse ancak yüklü değilse, son kullanıcılarınızdan Intune Managed Browser’ı yüklemeleri istenir.<p>İlkeyle yönetilen bir tarayıcı gerekliyse iOS Evrensel Bağlantıları, **Uygulamanın diğer uygulamalara veri aktarmasına izin ver** ilke ayarı tarafından yönetilir. <p>**Intune cihaz kaydı**<br>Cihazlarınızı yönetmek için Intune kullanıyorsanız bkz. Microsoft Intune ile yönetilen tarayıcı ilkelerini kullanarak İnternet erişimini yönetme. <p>**İlkeyle yönetilen Microsoft Edge**<br>Mobil cihazlar (iOS ve Android) için Microsoft Edge tarayıcısı, Intune uygulama koruma ilkelerini destekliyor. Microsoft Edge tarayıcı uygulamasında şirket Azure AD hesaplarıyla oturum açan kullanıcılar, Intune tarafından korunur. Microsoft Edge tarayıcısı, Intune SDK’sını tümleştirir ve bu SDK’nın tüm veri koruma ilkelerini destekler ancak şu işlevleri engeller:<br><ul><li>**Farklı kaydetme**: Microsoft Edge tarayıcısı, kullanıcının bulut depolama sağlayıcılarına (OneDrive gibi) doğrudan, uygulama içi bağlantılar eklemesine izin vermez.</li><li>**Kişi eşitleme**: Microsoft Edge tarayıcısı yerel kişi listelerini kaydetmez.</li></ul><br>**Not**:<br>Intune SDK’sı, hedef uygulamanın tarayıcı olup olmadığını belirleyemez. iOS cihazlarında diğer hiçbir yönetilen tarayıcı uygulamasına izin verilmez.    | **Yapılandırılmadı**  |

> [!NOTE]  
> Verileri koruma ayarlarının hiçbiri iOS cihazlarında Apple tarafından yönetilen birlikte aç özelliğini denetlemez. Apple birlikte aç özelliğini kullanmak için bkz. [Microsoft Intune ile iOS uygulamaları arasında veri aktarımını yönetme](data-transfer-between-apps-manage-ios.md).

## <a name="data-transfer-exemptions"></a>Veri aktarımı muafiyetleri

Intune uygulama koruma ilkesinin, belirli senaryolarda veri aktarımına hedef ve kaynak olarak izin verebileceği bazı muaf uygulamalar ve platform hizmetleri vardır. Bu liste değiştirilebilir ve güvenli verimlilik için kullanışlı olarak nitelendirilen hizmetleri ve uygulamaları yansıtır.

| Uygulama/hizmet adı | Açıklama |
| ---- | --- |
|<code>tel; telprompt</code> | Yerel telefon uygulaması |
| <code>skype</code> | Skype |
| <code>app-settings</code> | Cihaz ayarları |
| <code>itms; itmss; itms-apps; itms-appss; itms-services</code> | Uygulama Mağazası |
| <code>calshow</code> | Yerel Takvim |


## <a name="access-requirements"></a>Erişim gereksinimleri

| Ayar | Nasıl kullanılır? | Varsayılan değer |
|------|----------|-------|
| **Erişim için PIN** | Bu uygulamayı kullanmak için PIN'i zorunlu tutmak üzere **Gerekli**'yi seçin. Uygulamayı iş veya okul bağlamında ilk kez çalıştırdığında kullanıcıdan bu PIN’i ayarlaması istenir. PIN, çevrimiçi ve çevrimdışı çalışırken uygulanır.    <br><br> **Erişim için PIN** bölümünde sağlanan ayarları kullanarak PIN gücünü ayarlayabilirsiniz.   | **Gerekli** |
| <ul><ui> **PIN türü** | Uygulama koruma ilkelerinin geçerli olduğu bir uygulamaya erişmeden önce sayısal veya geçiş kodu türü PIN gereksinimi ayarlayın. Sayısal gereksinimler yalnızca sayıları içerirken, geçiş kodu en az 1 harf **veya** en az 1 özel karakterle tanımlanabilir.  <br><br> **Not:** *Geçiş kodu türünü yapılandırmak için uygulamanın Intune SDK sürüm 7.1.12 veya üzerine sahip olması gerekir. Sayısal türlerde Intune SDK sürümü kısıtlaması yoktur. İzin verilen özel karakterlere iOS İngilizce dil klavyesindeki özel karakterler ve semboller dahildir.*  | **Sayısal**  |
| <ul><ui> **Basit PIN** | Kullanıcıların 1234, 1111, abcd veya aaaa gibi basit PIN dizileri kullanmasına izin vermek için **İzin Ver**’i seçin. Basit PIN dizileri kullanmalarını engellemek için **Engelle**'yi seçin. <br><br>**Not**: *Geçiş Kodu türünde bir PIN yapılandırılmışsa ve Basit PIN'e İzin Ver seçeneği Evet olarak ayarlandıysa kullanıcının PIN'inde en az 1 harf **veya** en az 1 özel karaktere ihtiyacı vardır. Geçiş Kodu türünde bir PIN yapılandırılmışsa ve Basit PIN'e İzin Ver seçeneği Hayır olarak ayarlıysa kullanıcının PIN'inde en az 1 sayı **ve** 1 harf **ve** en az 1 özel karaktere ihtiyacı vardır.*   |**İzin ver**  |
| <ul><ui> **En düşük PIN uzunluğunu seçin** | PIN dizisindeki basamak sayısı alt sınırını belirtin.  | **4**  |
|  <ul><ui> **Erişim için PIN yerine Touch ID (iOS 8+)** | Kullanıcının uygulama erişiminde PIN yerine [Touch ID](https://support.apple.com/HT201371) kullanmasına izin vermek için **İzin Ver**'i seçin.    | **İzin ver**  |
|  <ul><ui> <ul><ui> **Zaman aşımından sonra Touch ID'yi PIN ile geçersiz kıl** |  Bu ayarı kullanmak için **Gerekli**'yi seçin ve boşta kalma zaman aşımını yapılandırın.  |**Gerekli**  |
|  <ul><ui> <ul><ui> **Zaman aşımı (dakika olarak eylemsizlik)** | PIN’in parmak izi kullanımını ne kadar süre sonra geçersiz kılacağını dakika biçiminde belirtin.  |**30**  |
|  <ul><ui> **Erişim için PIN yerine Face ID (iOS 11+)** | iOS cihazlarında kullanıcıların kimliklerini doğrularken kullanıcının yüz tanıma teknolojisini kullanmasına izin vermek için **İzin Ver**'i seçin. İzin verilirse, Face ID özellikli cihazlarda uygulamaya erişmek için Face ID'nin kullanılması gerekir.    | **İzin ver**  |
|  <ul><ui>**Belirtilen sayıda gün sonra PIN sıfırlama** | Kullanıcıların gün olarak belirlenen bir süre sonunda uygulama PIN değerlerini değiştirmelerini zorunlu tutmak için **Evet**'i seçin.  <br><br>*Evet* olarak ayarlandığında, PIN'i sıfırlamak gerekmeden önce geçecek gün sayısını yapılandırırsınız. |**Hayır**  |  
|  <ul><ui> <ul><ui>**Gün sayısı** | PIN'i sıfırlamak gerekmeden önce geçecek gün sayısını yapılandırın.  |**0**  |
|  <ul><ui>**Cihaz PIN'i ayarlı olduğunda uygulama PIN'i** | Şirket Portalı’na kayıtlı bir cihazda cihaz kilidi algılandığında uygulama PIN’ini devre dışı bırakmak için **Devre Dışı Bırak**'ı seçin.<br><br> **Not:** *Uygulamanın Intune SDK sürüm 7.0.1 veya üstü olmasını gerektirir.*  <br><br>iOS cihazlarda, kullanıcıların kimliklerini kanıtlamak için PIN yerine [Touch ID](https://support.apple.com/HT201371) veya [Face ID](https://support.apple.com/HT208109) kullanmalarına izin verebilirsiniz. Intune, Touch ID veya Face ID kullanan kullanıcıların kimliğini doğrulamak için [LocalAuthentication](https://developer.apple.com/documentation/localauthentication/) API’sini kullanır. Touch ID ve Face ID hakkında daha fazla bilgi için bkz. [iOS Güvenlik Kılavuzu](https://www.apple.com/business/docs/iOS_Security_Guide.pdf).  <br><br> Kullanıcı, iş veya okul hesabıyla bu uygulamayı kullanmayı denediğinde kendisinden PIN girmek yerine parmak izi veya yüz kimliğini sağlaması istenir. Bu ayar etkinleştirildiğinde, Uygulama Değiştirici önizleme resmi iş veya okul hesabı kullanılırken bulanıklaştırılır.  |  **Etkinleştir** |  
| **Erişim için iş veya okul hesabı kimlik bilgileri** | Kullanıcının uygulama erişimi için PIN girmek yerine iş veya okul hesabıyla oturum açmasını zorunlu kılmak için **Gerekli**'yi seçin. Bunu **Gerekli** olarak ayarlarsanız ve PIN veya biyometrik istemler açıksa hem kurumsal kimlik bilgileri hem de PIN veya biyometrik istemler gösterilir.  | **Gerekli değildir** |
| **Erişim gereksinimlerini yeniden denetle (eylemsizlik dakika sayısı)** | Uygulamanın kullanıcıdan erişim gereksinimlerini yeniden belirtmesini istemeden önce eylemsizlik durumunun kaç dakika süreceğini yapılandırın. <br><br> Örneğin bir yönetici ilkede PIN’i açar ve kökü belirtilmiş cihazları engellerse, bir kullanıcı Intune ile yönetilen bir uygulamayı açtığında PIN’i girmeli ve uygulamayı kök erişim izni verilmemiş bir cihazda kullanıyor olmalıdır. Bu ayar kullanıldığında, kullanıcının yapılandırılan değere eşit bir süre boyunca Intune ile yönetilen herhangi bir uygulamada PIN girmesi veya başka bir kök algılama denetiminden geçmesi gerekmez.  <br><br>**Not:** *iOS'ta PIN, **aynı yayımcıya** ait tüm Intune ile yönetilen uygulamalar arasında paylaşılır. Uygulama cihazda ön plandan ayrıldığında, belirli bir PIN’e ait PIN zamanlayıcısı sıfırlanır. Bu ayarda tanımlanan zaman aşımı süresince Intune ile yönetilen PIN’ini paylaşan herhangi bir uygulamada kullanıcının bir PIN girmesi gerekmez. Bu ilke ayarı biçimi pozitif bir tam sayıyı destekler.*     | **30** |

> [!NOTE]
> Erişim bölümünde yapılandırılan birden çok Intune uygulama koruma ayarının, aynı uygulama ve kullanıcı grubu için iOS'ta nasıl çalıştığı hakkında daha fazla bilgi edinmek için bkz. [Intune MAM sık sorulan sorular](https://docs.microsoft.com/intune/mam-faq#app-experience-on-ios) ve [Intune’da uygulama koruma ilkesi erişim eylemlerini kullanarak verileri seçmeli olarak silme](app-protection-policies-access-actions.md).

## <a name="conditional-launch"></a>Koşullu başlatma
Erişim koruma ilkenize oturum açmak için güvenlik gereksinimleri ayarlamak için koşullu başlatma ayarlarını yapılandırın. 

Varsayılan olarak, önceden yapılandırılmış değer ve eylemlere sahip bazı ayarlar sağlanır. *En düşük işletim sistemi sürümü* gibi bazı ayarları silebilirsiniz. Ayrıca **Birini seçin** açılır penceresinden ek ayarlar da seçebilirsiniz. 

| Ayar | Nasıl kullanılır? |  
|---------|------------| 
| **En düşük işletim sistemi sürümü** | Bu uygulamanın kullanılabilmesi için en düşük iOS işletim sistemini belirtin. *Eylemler* şunları içerir: <br><ul><li>**Uyar** - Cihazın iOS sürümü gereksinimi karşılamıyorsa kullanıcı bir bildirim görür. Bu bildirim kapatılabilir. <br><br> </li></ul> <ul><li>**Erişimi engelle** - Cihazın iOS sürümü bu gereksinimi karşılamıyorsa kullanıcının uygulamaya erişimi engellenir.</li></ul> <ul><li>**Verileri sil** - Uygulamayla ilişkili kullanıcı hesabı cihazdan silinir.  </li></ul> </li></ul> _**Not:** Uygulamanın Intune SDK sürüm 7.0.1 veya üstü olmasını gerektirir._ |
| **En fazla PIN denemesi** | Kullanıcının yapılandırma eylemi gerçekleştirmek zorunda kalmadan önce başarılı bir şekilde girmesi gereken PIN deneme sayısını belirtin. Bu ilke ayarı biçimi pozitif tamsayıyı destekler. *Eylemler* şunları içerir: <br><ul><li>**PIN sıfırla** - Kullanıcının PIN’ini sıfırlaması gerekir.</li></ul> <ul><li>**Verileri sil** - Uygulamayla ilişkili kullanıcı hesabı cihazdan silinir.  </li></ul></li></ul> Varsayılan değer = **5** |
| **Çevrimdışı yetkisiz kullanım süresi** | MAM uygulamalarının çevrimdışı çalıştırılabileceği dakika sayısıdır. Uygulama için erişim gereksinimleri yeniden denetlenmeden önce geçmesi gereken süreyi (dakika cinsinden) belirtin. *Eylemler* şunları içerir: <br><ul><li>**Erişimi engelle (dakika)** - MAM uygulamalarının çevrimdışı çalıştırılabileceği dakika sayısıdır. Uygulama için erişim gereksinimleri yeniden denetlenmeden önce geçmesi gereken süreyi (dakika cinsinden) belirtin. Yapılandırılan süre dolduktan sonra, ağ erişimi kullanılabilir olana kadar uygulama iş veya okul verilerine erişimi engeller. Bu ilke ayarı biçimi pozitif tamsayıyı destekler.<br><br>Varsayılan değer = **720** dakika (12 saat) </li></ul> <ul><li>**Verileri sil (gün)**: Uygulama, yönetici tarafından tanımlanan bu süre içerisinde çevrimdışı çalıştığında kullanıcıdan ağa bağlanmasını ve yeniden kimlik doğrulamasını ister. Kullanıcı başarıyla oturum açarsa, verilerine erişmeye devam edebilir ve çevrimdışı zaman aralığı sıfırlanır.  Kullanıcı kimlik doğrulaması başarısız olursa uygulama, kullanıcı hesabı ve verilerinde seçmeli silme gerçekleştirir.  Seçmeli silme ile hangi verilerin silindiği hakkında daha fazla bilgi için bkz. [Intune ile yönetilen uygulamalarda yalnızca şirket verilerini silme](https://docs.microsoft.com/intune/apps-selective-wipe). Bu ilke ayarı biçimi pozitif tamsayıyı destekler. <br><br> Varsayılan değer = **90 gün** </li></ul>  Bu girdi, her örnek farklı eylemi destekleyecek şekilde birden fazla kez görünebilir. |
| **Jailbreak uygulanmış/kök erişim izni verilmiş cihazlar** | Bu ayarın değeri yoktur. *Eylemler* şunları içerir: <br><ul><li>**Erişimi engelle** - Bu uygulamanın jailbreak uygulanmış veya kök erişim izni verilmiş cihazlarda çalışması engellenir. Kullanıcı bu uygulamayı kişisel görevler için kullanmaya devam edebilir, ancak iş veya okul verilerine erişmek için farklı bir cihaz kullanmalıdır.</li></ul> <ul><li>**Verileri sil** - Uygulamayla ilişkili kullanıcı hesabı cihazdan silinir. </li></ul> |
| **En düşük uygulama sürümü** | En düşük işletim sistemi için bir değer belirtin. *Eylemler* şunları içerir: <br><ul><li>**Uyar** - Cihazdaki uygulama sürümü gereksinimi karşılamıyorsa kullanıcı bir bildirim görür. Bu bildirim kapatılabilir.</li></ul> <ul><li>**Erişimi engelle** - Cihazın uygulama sürümü gereksinimi karşılamıyorsa kullanıcının uygulamaya erişimi engellenir. </li></ul> <ul><li>**Verileri sil** - Uygulamayla ilişkili kullanıcı hesabı cihazdan silinir. </li></ul> </li></ul>   Uygulamalar arasında genellikle farklı sürüm şemaları bulunduğundan, en az bir uygulama sürümünün bir uygulamayı hedeflediği (*Outlook sürümü ilkesi* gibi) bir ilke oluşturun.<br><br> Bu girdi, her örnek farklı eylemi destekleyecek şekilde birden fazla kez görünebilir.<br><br> Bu ilke ayarı biçimi birincil.ikincil, birincil.ikincil.derleme, birincil.ikincil.derleme.düzeltme'yi destekler.||
| **En düşük SDK sürümü** | Intune SDK sürümü alt sınırı için bir değer belirtin. *Eylemler* şunları içerir: <br><ul><li>**Erişimi engelle** - Cihazın Intune uygulama koruma ilkesi SDK sürümü gereksinimi karşılamıyorsa kullanıcının uygulamaya erişimi engellenir. <br> <br> Intune uygulama koruma ilkesi SDK’sı hakkında daha fazla bilgi için bkz. [Intune Uygulama SDK'sına genel bakış](app-sdk.md).</li></ul> <ul><li>**Verileri sil** - Uygulamayla ilişkili kullanıcı hesabı cihazdan silinir. </li></ul>  </li></ul> Uygulamalar arasında genellikle farklı sürüm şemaları bulunduğundan, en az bir uygulama sürümünün bir uygulamayı hedeflediği (*Outlook sürümü ilkesi* gibi) bir ilke oluşturun. <br><br> Bu girdi, her örnek farklı eylemi destekleyecek şekilde birden fazla kez görünebilir.|
| **Cihaz modeli/modelleri** | Bu uygulamayı kullanmak için gereken bir cihaz modeli belirtin. *Eylemler* şunları içerir: <br><ul><li>**Belirtilenlere izin ver (belirtilmeyenleri engelle)** - Yalnızca belirtilen cihaz modeliyle eşleşen cihazlar uygulamayı kullanabilir. Diğer tüm cihaz modelleri engellenir. </li></ul> <ul><li>**Belirtilenlere izin ver (belirtilmeyenleri sil)** - Uygulamayla ilişkili kullanıcı hesabı cihazdan silinir.</li></ul> |



##  <a name="add-ins-for-outlook-app"></a>Outlook uygulaması için eklentiler

Outlook kısa süre önce iOS için Outlook’a, popüler uygulamaları e-posta istemcisiyle tümleştirebilmenizi sağlayacak eklentiler getirmiştir. Outlook eklentileri web, Windows, Mac ve iOS için Outlook’ta kullanılabilir. Intune SDK'sı ve Intune uygulama koruma ilkeleri, Outlook'un eklentilerini yönetme desteği içermez. Ancak bunların kullanımını sınırlandırmanın başka yolları vardır. Eklentiler Microsoft Exchange yoluyla yönetildiğinden, eklentiler kullanıcı için Exchange tarafından kapatılmadığı sürece, kullanıcılar Outlook ile yönetilmeyen eklenti uygulamaları arasında verileri ve iletileri paylaşabilirler.

Son kullanıcılarınızın Outlook eklentilerine erişmesini ve bunları yüklemesini durdurmak isterseniz (bu işlem tüm Outlook istemcilerini etkiler), Exchange yönetim merkezinde rollerde aşağıdaki değişikliklerin yapıldığından emin olun:

- Kullanıcıların Office Mağazası eklentilerini yüklemesini engellemek için, onlardan Marketim rolünü kaldırın.
- Kullanıcıların dışarıdan eklenti yüklemesini engellemek için, onlardan Özel Uygulamalarım rolünü kaldırın.
- Kullanıcılar tüm eklentilerin yüklemesini engellemek için, onlardan hem Özel Uygulamalarım rolünü hem de Marketim rolünü kaldırın.

Bu yönergeler Office 365, Exchange 2016, Exchange 2013’te Web üzerinde Outlook genelinde, Windows, Mac ve mobil için geçerlidir.

- [Outlook için eklentiler](https://technet.microsoft.com/library/jj943753(v=exchg.150).aspx) hakkında daha fazla bilgi edinin.
- [Outlook uygulaması için eklentileri yükleyebilecek ve yönetebilecek kullanıcıları ve yöneticileri belirleme](https://technet.microsoft.com/library/jj943754(v=exchg.150).aspx) hakkında daha fazla bilgi edinin.

##  <a name="linkedin-account-connections-for-microsoft-apps"></a>Microsoft uygulamaları için LinkedIn hesap bağlantıları

LinkedIn hesap bağlantıları, kullanıcıların belirli Microsoft uygulamalarında LinkedIn profil bilgilerini görmesini sağlar. Varsayılan olarak, kullanıcılarınız ek LinkedIn bilgilerini görmek için LinkedIn ve Microsoft iş veya okul hesaplarını bağlamayı seçebilir. 

> [!NOTE]
> LinkedIn tümleştirmesi şu anda Birleşik Devletler Kamu müşterileri ve Avustralya, Kanada, Çin, Fransa, Almanya, Hindistan, Güney Kore, Birleşik Krallık, Japonya ve Güney Afrika’da barındırılan Exchange Online posta kutularına sahip olan kuruluşlar için kullanılamamaktadır.

Intune SDK’sı ve Intune uygulama koruma ilkeleri, LinkedIn hesap bağlantılarını yönetme desteği içermez. Ancak bunları yönetmenin başka yolları vardır. Tüm kuruluşunuz için LinkedIn hesabı bağlantılarını devre dışı bırakabilir veya kuruluşunuzda seçili kullanıcı grupları için LinkedIn bağlantılarını etkinleştirebilirsiniz. Bu ayar tüm platformlarda (web, mobil ve masaüstü) tüm Office 365 uygulamalarındaki LinkedIn bağlantılarını etkiler. Şunları yapabilirsiniz:

- Azure portalında kiracınız için LinkedIn hesap bağlantılarını etkinleştirin veya devre dışı bırakın. 
- Grup İlkesini kullanarak kuruluşunuzun Office 2016 uygulamalarında LinkedIn hesabı bağlantılarını etkinleştirin veya devre dışı bırakın.

Kiracınız için LinkedIn tümleştirmesi etkinse kuruluşunuzdaki kullanıcılar LinkedIn ve Microsoft iş veya okul hesaplarını bağladıklarında iki seçenekleri bulunur: 

- İki hesap arasında verileri paylaşmak için izin verebilirler. Bu, LinkedIn hesaplarının Microsoft iş veya okul hesaplarıyla veri paylaşmasına ve Microsoft iş veya okul hesaplarının LinkedIn hesaplarıyla veri paylaşmasına izin verdikleri anlamına gelir. LinkedIn ile paylaşılan veriler çevrimiçi hizmetlerden ayrılır. 
- Yalnızca LinkedIn hesaplarından Microsoft iş ve okul hesaplarına veri paylaşmak için izin verebilirler

Bir kullanıcı, Office eklentilerinde olduğu gibi hesaplar arasında veri paylaşımına izin verirse LinkedIn tümleştirmesi mevcut Microsoft Graph API’lerini kullanır. LinkedIn tümleştirmesi, Office eklentileri için kullanılabilir API’lerin yalnızca bir alt kümesini kullanır ve çeşitli dışlamaları destekler.


|Microsoft Graph izinleri  |Açıklama  |
|---------|---------|
|[Kişiler](https://developer.microsoft.com/graph/docs/concepts/permissions_reference#people-permissions) için okuma izinleri     |Uygulamanın oturum açan kullanıcıyla ilgili kişilerin puanlanmış bir listesini okumasına izin verir. Liste; yerel kişileri, sosyal ağ veya kuruluşunuzun dizinindeki kişileri ve son iletişim kurulan kişileri (e-posta ve Skype gibi) içerebilir.         |
|[Takvimler](https://developer.microsoft.com/graph/docs/concepts/permissions_reference#calendars-permissions) için okuma izinleri     |Uygulamanın kullanıcı takvimlerindeki etkinlikleri okumasına izin verir. Oturum açan kullanıcının takvimindeki toplantıları, zamanlarını, yerlerini ve katılımcıları içerir.         |
|[Kullanıcı Profili](https://developer.microsoft.com/graph/docs/concepts/permissions_reference#user-permissions) için okuma izinleri     |Kullanıcıların uygulamada oturum açmasını sağlar ve uygulamanın oturum açan kullanıcıların profilini okumasına izin verir. Ayrıca uygulamanın oturum açan kullanıcılar için temel şirket bilgilerini okumasına izin verir.         |
|Subscriptions     |Bu kapsam mevcut değil ve henüz kullanılmıyor. Kullanıcının kuruluşu tarafından sağlanan Office 365 gibi Microsoft uygulamaları ve hizmetleri aboneliklerini içerir.         |
|İçgörüler     |Bu kapsam mevcut değil ve henüz kullanılmıyor. Oturum açan kullanıcı hesabıyla ilişkili Microsoft hizmetleri kullanımını temel alan ilgi alanlarını içerir.         |

### <a name="learn-more"></a>Daha fazlasını öğrenin

- [Microsoft uygulamalarınızdaki LinkedIn bilgileri ve özellikleri](https://go.microsoft.com/fwlink/?linkid=850740) hakkında bilgi edinin.
- [Office 365 Yol haritası sayfasında](https://products.office.com/en-US/business/office-365-roadmap?filters=%26freeformsearch=linkedin#abc) LinkedIn hesap bağlantıları yayını hakkında bilgi edinin. 
- [LinkedIn hesap bağlantılarını yapılandırma](https://docs.microsoft.com/azure/active-directory/linkedin-integration) hakkında bilgi edinin.
- Kullanıcıların LinkedIn ve Microsoft iş veya okul hesapları arasında paylaşılan veriler hakkında daha fazla bilgi için bkz. [İş veya okulunuzda Microsoft uygulamalarında LinkedIn](https://www.linkedin.com/help/linkedin/answer/84077).

