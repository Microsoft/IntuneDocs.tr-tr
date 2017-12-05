---
title: "iOS uygulama koruma ilkesi ayarları"
titlesuffix: Azure portal
description: "Bu konu başlığı altında iOS cihazları için uygulama koruma ilkesi ayarları açıklanır.\""
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 11/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0f8b08f2-504c-4b38-bea2-b8a4ef0526b8
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 65a5f33030fa3a9011dfc2f5825021e12b68e4d0
ms.sourcegitcommit: 520eb7712625e129b781e2f2b9fe16f9b9f3d08a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2017
---
#  <a name="ios-app-protection-policy-settings"></a>iOS uygulama koruma ilkesi ayarları
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Bu konuda açıklanan ilke ayarları, Azure portalındaki **Ayarlar** dikey penceresinde bir uygulama koruma ilkesi için [yapılandırılabilir](app-protection-policies.md).

İlke ayarlarının, verileri yeniden konumlandırma ayarları ve erişim ayarları olmak üzere iki kategorisi vardır. Bu konuda, ***ilkeyle yönetilen uygulamalar*** terimi, uygulama koruma ilkeleriyle yapılandırılan uygulamaları ifade eder.

##  <a name="data-relocation-settings"></a>Verileri yeniden konumlandırma ayarları

| Ayar | Nasıl kullanılır? | Varsayılan değer |
|------|------|------|
| **iTunes ve iCloud yedeklemelerini engelle** | Bu uygulamanın iş veya okul verilerini iTunes veya iCloud’a yedeklemesini engellemek için **Evet**’i seçin. Bu uygulamanın iş veya okul verilerini iTunes veya iCloud’a yedeklemesine izin vermek için **Hayır**’ı seçin.| Evet |
| **Uygulamanın diğer uygulamalara veri aktarmasına izin ver** | Hangi uygulamaların bu uygulamadan veri alabileceğini belirtin: <ul><li> **İlke ile yönetilen uygulamalar**: Yalnızca diğer ilkeyle yönetilen uygulamalara aktarım yapılmasına izin verilir.</li> <li>**Tüm uygulamalar**: Herhangi bir uygulamaya aktarıma izin verilir. </li> <li>**Hiçbiri**: İlkeyle yönetilen diğer uygulamalar da dahil olmak üzere hiçbir uygulamaya veri aktarmaya izin verilmez.</li></ul> Ayrıca, bu seçeneği **İlke ile yönetilen uygulamalar** veya **Hiçbiri** olarak ayarlarsanız uygulamaların içindeki verileri aramak için Spotlight Arama özelliğine imkan tanıyan iOS 9 özelliği engellenir. <br><br> Intune’un veri aktarımı hedefi olarak izin verebileceği bazı muaf uygulamalar ve hizmetler vardır. Uygulama ve hizmetlerin tam listesi için bkz. [Veri aktarımı muafiyetleri](#Data-transfer-exemptions). | Tüm uygulamalar |
| **Uygulamanın diğer uygulamalardan veri almasına izin ver** | Hangi uygulamaların bu uygulamaya veri aktarabileceğini belirtin: <ul><li>**İlke ile yönetilen uygulamalar**: Yalnızca diğer ilkeyle yönetilen uygulamalardan aktarım yapılmasına izin verilir.</li><li>**Tüm uygulamalar**: Herhangi bir uygulamadan veri aktarımına izin verilir.</li><li>**Hiçbiri**: İlkeyle yönetilen diğer uygulamalar da dahil olmak üzere hiçbir uygulamadan veri aktarmaya izin verilmez.</li></ul> Intune’un veri aktarımı kaynağı olarak izin verebileceği bazı muaf uygulamalar ve hizmetler vardır. Uygulama ve hizmetlerin tam listesi için bkz. [Veri aktarımı muafiyetleri](#Data-transfer-exemptions).  | Tüm uygulamalar |
| **“Farklı Kaydet”i engelle** | Bu uygulamada Farklı Kaydet seçeneğinin kullanımını devre dışı bırakmak için **Evet**’i seçin. Farklı Kaydet’in kullanılmasına izin vermek istiyorsanız **Hayır** ’ı seçin. | Hayır |
| **Diğer uygulamalarla kesme, kopyalama ve yapıştırmayı kısıtlama** | Bu uygulamada kes, kopyala ve yapıştır eylemlerinin ne zaman kullanılabileceğini belirtin. Aşağıdakilerden birini seçin: <ul><li>**Engellendi**: Bu uygulama ve diğer herhangi bir uygulama arasında kesme, kopyalama ve yapıştırma eylemlerine izin verilmez.</li><li>**İlkeyle yönetilen uygulamalar**: Bu uygulama ve diğer ilkeyle yönetilen uygulamalar arasında kesme, kopyalama ve yapıştırma eylemlerine izin verilir.</li><li>**Yapıştırma seçeneğiyle ilke ile yönetilen**: Bu uygulama ve diğer ilkeyle yönetilen uygulamalar arasında kesme veya kopyalama eylemine izin verilir. Herhangi bir uygulamadan verilerin bu uygulamaya yapıştırılmasına izin verir.</li><li>**Herhangi bir uygulama**: Bu uygulamaya veya bu uygulamadan kesme, kopyalama ve yapıştırma eylemleriyle ilgili bir kısıtlama olmaz. | Herhangi bir uygulama |
|**Managed Browser’da görüntülenen web içeriğini kısıtla** | Uygulamadaki web bağlantılarının Managed Browser uygulamasında açılmasını zorunlu kılmak için **Evet**’i seçin. <br><br> Intune’a kayıtlı olmayan cihazlarda, ilke tarafından yönetilen uygulamalardaki web bağlantıları yalnızca Managed Browser uygulamasında açılabilir. <br><br> Cihazlarınızı yönetmek için Intune kullanıyorsanız bkz. [Microsoft Intune'la Managed Browser ilkelerini kullanarak İnternet erişimini yönetme](app-configuration-managed-browser.md). | Hayır |
| **Uygulama verilerini şifreleme** | İlkeyle yönetilen uygulamalarda, etkin olmayan veriler iOS tarafından sağlanan cihaz düzeyinde şifreleme şeması kullanılarak şifrelenir. PIN istendiğinde, veriler uygulama koruma ilkesi ayarlarına göre şifrelenir. <br><br> Hangi iOS şifreleme modüllerinin FIPS 140-2 sertifikalı veya FIPS 140-2 sertifikası bekliyor olduğunu görmek için [buradaki](https://support.apple.com/HT202739) resmi Apple belgelerine gidin. <br><br> Bu uygulamadaki iş veya okul verilerinin ne zaman şifreleneceğini belirtin. Aşağıdakilerden birini seçin: <ul><li>**Cihaz kilitliyken**: Cihaz kilitliyken, bu ilkeyle ilişkilendirilen tüm uygulama verileri şifrelenir.</li><li>**Cihaz kilitliyken ve açık dosyalar varken**: Cihaz kilitliyken, uygulamada o anda açık olan dosyalardaki veriler dışında bu ilkeyle ilişkilendirilen tüm uygulama verileri şifrelenir.</li><li>**Cihaz yeniden başlatıldıktan sonra**: Cihaz yeniden başlatıldığında, bu ilkeyle ilişkilendirilen tüm uygulama verileri cihaz kilidinin ilk açılışına kadar şifrelenir.</li><li>**Cihaz ayarlarını kullan**: Uygulama verileri, cihazdaki varsayılan ayarlara göre şifrelenir. </li></ul> Bu ayarı etkinleştirdiğinizde kullanıcının cihazına erişmesi için bir PIN ayarlaması ve bu PIN’i kullanması gerekebilir.  Şifreleme gerekli olduğu halde cihaz erişimi için PIN ayarlanmadıysa uygulamalar açılmaz ve “Kuruluşunuz, bu uygulamaya erişmek için öncelikle bir cihaz PIN’i etkinleştirmenizi gerektiriyor” iletisiyle birlikte kullanıcıdan bir PIN ayarlaması istenir.  | Cihaz kilitliyken |
| **Kişilerin eşitlenmesini devre dışı bırak** | Uygulamanın cihazdaki yerel Kişiler bölümüne veri kaydetmesini engellemek için **Evet**’i seçin. **Hayır**’ı seçerseniz uygulama cihazdaki yerel Kişiler uygulamasına veri kaydedebilir. <br><br>Uygulamadan iş veya okul verilerini kaldırmak için seçmeli silme gerçekleştirdiğinizde, yerel Kişiler uygulamasına doğrudan uygulamadan eşitlenen kişiler kaldırılır. Yerel adres defterinden başka bir dış kaynağa eşitlenen kişiler silinemez. Şu anda bu özellik yalnızca Microsoft Outlook uygulaması için geçerlidir. | Hayır |
| **Yazdırmayı devre dışı bırak** | Uygulamanın iş veya okul verilerini yazdırmasını engellemek için **Evet**’i seçin. | Hayır |
| **Şirket verilerinin kaydedilebileceği depolama hizmetlerini seçin** | Kullanıcılar, seçili hizmetlere (OneDrive İş, SharePoint ve Yerel Depolama) kaydedebilir. Diğer tüm hizmetler engellenir. | 0 Seçili |

> [!NOTE]
> Verileri yeniden konumlandırma ayarlarının hiçbiri iOS cihazlarında Apple tarafından yönetilen birlikte aç özelliğini denetlemez. Apple birlikte aç özelliğini kullanmak için bkz. [Microsoft Intune ile iOS uygulamaları arasında veri aktarımını yönetme](data-transfer-between-apps-manage-ios.md).

## <a name="data-transfer-exemptions"></a>Veri aktarımı muafiyetleri

Intune uygulama koruma ilkesinin, belirli senaryolarda veri aktarımına hedef ve kaynak olarak izin verebileceği bazı muaf uygulamalar ve platform hizmetleri vardır. Bu liste değiştirilebilir ve güvenli verimlilik için kullanışlı olarak nitelendirilen hizmetleri ve uygulamaları yansıtır.

| Uygulama/hizmet adı | Açıklama |
| ---- | --- |
|tel; telprompt | Yerel telefon uygulaması |
| skype | Skype |
| app-settings | Cihaz ayarları |
| itms; itmss; itms-apps; itms-appss; itms-services | Uygulama Mağazası |
| calshow | Yerel Takvim |




## <a name="access-settings"></a>Erişim ayarları

| Ayar | Nasıl kullanılır? | Varsayılan değer |
|------|------|------|
| **Erişim için PIN’i zorunlu kıl** | Bu uygulamayı kullanmak için PIN’i zorunlu kılmak üzere **Evet**’i seçin. Uygulamayı iş veya okul bağlamında ilk kez çalıştırdığında kullanıcıdan bu PIN’i ayarlaması istenir. Varsayılan değer = **Evet**.<br><br> PIN gücü için aşağıdaki ayarları yapılandırın: <ul><li>**PIN sıfırlamadan önceki deneme sayısı**: Kullanıcının PIN’ini sıfırlamak zorunda kalmadan önce başarılı bir şekilde girmesi gereken deneme sayısını belirtin. Varsayılan değer = **5**.</li><li> **Basit PIN’e izin ver:** Kullanıcıların 1234 veya 1111 gibi basit PIN dizileri kullanmasına izin vermek için **Evet**’i seçin. Basit PIN dizileri kullanmalarını engellemek için **Hayır**’ı seçin. Varsayılan değer = **Evet**. </li><li> **PIN uzunluğu:** PIN dizisindeki basamak sayısı alt sınırını belirtin. Varsayılan değer = **4**. </li><li> **Geçiş kodu ayarla**: Uygulama koruma ilkeleri uygulanmış bir uygulamaya erişirken istenirse bir geçiş kodu ayarlayabilirsiniz. Geçiş kodu, en az 1 harf veya özel karakter ile tanımlanabilir. Geçiş kodu, çevrimiçi ve çevrimdışı çalışırken uygulanır. </li><li> **PIN yerine parmak izine izin ver (iOS 8.0+)**: Uygulama erişiminde bir PIN yerine **Touch ID** kullanmasına izin vermek için [Evet](https://support.apple.com/HT201371)’i seçin. Varsayılan değer = **Evet**</li></ul> iOS cihazlarda, kullanıcıların kimliklerini kanıtlamak için PIN yerine [Touch ID](https://support.apple.com/HT201371) kullanmasına izin verebilirsiniz. Kullanıcı, iş veya okul hesabıyla bu uygulamayı kullanmayı denediğinde, PIN girmek yerine parmak izi kimliğini vermesi istenir. Bu ayar etkinleştirildiğinde, Uygulama Değiştirici önizleme resmi iş veya okul hesabı kullanılırken bulanıklaştırılır. </li></ul><!-- <br><br>You can require a PIN expiration for targeted iOS apps. You can configure the PIN requirement and expiration date in days through the Azure portal. When required, a user will be required to set and use a new PIN before getting access to an iOS app. Only iOS apps that have app protection enabled with the Intune App SDK will support this feature.-->| PIN’i zorunlu kıl: Evet <br><br> PIN sıfırlama girişimi: 5 <br><br> Basit PIN’e izin ver: Evet <br><br> PIN uzunluğu: 4 <br><br> Parmak izine izin ver: Evet |
| **Erişim için kurumsal kimlik bilgileri gerektir** | Kullanıcının uygulama erişimi için PIN girmek yerine iş veya okul hesabıyla oturum açmasını zorunlu kılmak için **Evet**’i seçin. **Evet** olarak ayarlarsanız, bu ayar PIN veya Touch ID gereksinimlerini geçersiz kılar.  | Hayır |
| **Yönetilen cihazların, jailbreak uygulanmış veya kök erişim izni verilmiş cihazlarda çalışmasını engelle** |  Bu uygulamaya jailbreak uygulanmış veya kök erişim izni verilmiş cihazlarda çalışmasını engellemek için **Evet**’i seçin. Kullanıcı kişisel görevler için uygulamaları kullanmaya devam edebilir, ancak bu uygulamada iş veya okul verilerine erişmek için farklı bir cihaz kullanması gerekir. | Evet |
| **Erişim gereksinimlerini şu süreden sonra yeniden denetle (dakika)** | Aşağıdaki ayarları yapılandırın: <ul><li>**Zaman Aşımı**: Erişim gereksinimleri (daha önce ilkelerde tanımlanmıştır) yeniden denetlenmeden önce geçmesi gereken dakika sayısıdır. Örneğin, yönetici ilkede PIN’i etkinleştirirse, kullanıcı bir MAM uygulamasını açtığında bir PIN girmesi gerekir. Bu ayar kullanıldığında, kullanıcının **30 dakika** (varsayılan değer) boyunca herhangi bir MAM uygulamasında PIN girmesi gerekmez.</li><li>**Çevrimdışı yetkisiz kullanım süresi**: Uygulama için erişim gereksinimleri yeniden denetlenmeden önce MAM uygulamalarının çevrimdışı çalışabileceği dakika sayısıdır. Varsayılan değer = **720** dakika (12 saat). Bu süre dolduktan sonra, uygulama, çalışmaya devam edebilmesi için kullanıcının AAD’de kimliğini doğrulamasını ister.</li></ul>| Zaman Aşımı: 30 <br><br> Çevrimdışı: 720 |
| **Uygulama verileri silinmeden önceki çevrimdışı zaman aralığı (gün)** | Yönetici tarafından tanımlanan bu süre boyunca çevrimdışı çalıştığında uygulama, kullanıcıdan ağa bağlanmasını ve yeniden kimlik doğrulamasını ister. Kullanıcı başarıyla oturum açarsa, verilerine erişmeye devam edebilir ve çevrimdışı zaman aralığı sıfırlanır.  Kullanıcı kimlik doğrulaması başarısız olursa uygulama, kullanıcı hesabı ve verilerinde seçmeli silme gerçekleştirir.  Seçmeli silme ile hangi verilerin silindiği hakkında daha fazla bilgi için bkz. [Intune ile yönetilen uygulamalarda yalnızca şirket verilerini silme](https://docs.microsoft.com/en-us/intune/apps-selective-wipe). <br><br> | 90 gün |
| **Cihaz PIN’i yönetildiği zaman uygulama PIN’ini devre dışı bırak** | Kayıtlı bir cihazda bir cihaz kilidi algılandığında, uygulama PIN’ini devre dışı bırakmak için **Evet**’i seçin. | Hayır |
| **En düşük iOS işletim sistemini zorunlu tut** | Bu uygulamanın kullanılabilmesi için en düşük iOS işletim sistemini zorunlu tutmak için **Evet**’i seçin. Cihazın iOS sürümü gereksinimi karşılamıyorsa, kullanıcının uygulamaya erişimi engellenir. Bu ilke, yalnızca bir ondalık ayırıcıyı destekler; iOS 10.3 gibi. | Hayır |
| **En düşük iOS işletim sistemini zorunlu tut (Yalnızca uyarı)** | Bu uygulamanın kullanılabilmesi için en düşük iOS işletim sistemini zorunlu tutmak için **Evet**’i seçin. Cihazın iOS sürümü gereksinimi karşılamıyorsa, kullanıcı bir bildirim görür. Bu bildirim kapatılabilir. Bu ilke, yalnızca bir ondalık ayırıcıyı destekler; iOS 10.3 gibi. | Hayır |
| **En düşük uygulama sürümünü zorunlu tut** | Uygulamanın kullanılabilmesi için en düşük uygulama sürümünü zorunlu tutmak üzere **Evet**’i seçin. Cihazın uygulama sürümü gereksinimi karşılamıyorsa, kullanıcının uygulamaya erişimi engellenir.<br><br>Uygulamalar arasında genellikle farklı sürüm şemaları bulunduğundan, en az bir uygulama sürümünün bir uygulamayı (örneğin, "Outlook sürüm ilkesi") hedeflediği bir ilke oluşturun. <br><br> | Hayır | 
| **En düşük uygulama sürümünü zorunlu tut (Yalnızca uyarı)** | Bu uygulamanın kullanılabilmesi için en düşük uygulama sürümünü önermek için **Evet**’i seçin. Cihazdaki uygulama sürümü gereksinimi karşılamıyorsa, kullanıcı bir bildirim görür. Bu bildirim kapatılabilir.<br><br>Uygulamalar arasında genellikle farklı sürüm şemaları bulunduğundan, en az bir uygulama sürümünün bir uygulamayı (örneğin, "Outlook sürüm ilkesi") hedeflediği bir ilke oluşturun. <br><br> | Hayır | 
| **En düşük Intune uygulama koruma ilkesi SDK sürümünü zorunlu tut** | Uygulamanın kullanılabilmesi için en düşük Intune uygulama koruma ilkesi SDK sürümünü zorunlu tutmak için **Evet**’i seçin. Cihazın Intune uygulama koruma ilkesi SDK sürümü gereksinimi karşılamıyorsa, kullanıcının uygulamaya erişimi engellenir. <br> <br> Intune uygulama koruma ilkesi SDK’sı hakkında daha fazla bilgi için bkz. [Intune Uygulama SDK'sına genel bakış](app-sdk.md) <br><br> | Hayır |


##  <a name="add-ins-for-outlook-app"></a>Outlook uygulaması için eklentiler

Outlook kısa süre önce iOS için Outlook’a, popüler uygulamaları e-posta istemcisiyle tümleştirebilmenizi sağlayacak eklentiler getirmiştir. Outlook eklentileri web, Windows, Mac ve iOS için Outlook’ta kullanılabilir. Eklentiler Microsoft Exchange yoluyla yönetildiğinden, eklentiler kullanıcı için Exchange tarafından kapatılmadığı sürece, kullanıcılar Outlook ile yönetilmeyen eklenti uygulamaları arasında verileri ve iletileri paylaşabilirler.

Son kullanıcılarınızın Outlook eklentilerine erişmesini ve bunları yüklemesini durdurmak isterseniz (bu işlem tüm Outlook istemcilerini etkiler), Exchange yönetim merkezinde rollerde aşağıdaki değişikliklerin yapıldığından emin olun:

- Kullanıcıların Office Mağazası eklentilerini yüklemesini engellemek için, onlardan Marketim rolünü kaldırın.
- Kullanıcıların dışarıdan eklenti yüklemesini engellemek için, onlardan Özel Uygulamalarım rolünü kaldırın.
- Kullanıcılar tüm eklentilerin yüklemesini engellemek için, onlardan hem Özel Uygulamalarım rolünü hem de Marketim rolünü kaldırın.

Bu yönergeler Office 365, Exchange 2016, Exchange 2013’te Web üzerinde Outlook genelinde, Windows, Mac ve mobil için geçerlidir.

- [Outlook için eklentiler](https://technet.microsoft.com/library/jj943753(v=exchg.150).aspx) hakkında daha fazla bilgi edinin.
- [Outlook uygulaması için eklentileri yükleyebilecek ve yönetebilecek kullanıcıları ve yöneticileri belirleme](https://technet.microsoft.com/library/jj943754(v=exchg.150).aspx) hakkında daha fazla bilgi edinin.
