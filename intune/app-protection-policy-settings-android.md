---
title: "Android uygulama koruma ilkesi ayarları"
titlesuffix: Azure portal
description: "Bu konu başlığı altında Android cihazları için uygulama koruma ilkesi ayarları açıklanır.\""
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 01/05/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9e9ef9f5-1215-4df1-b690-6b21a5a631f8
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dddf5aae9ac7ec5804404a49fc0647e52d0c75de
ms.sourcegitcommit: 2c7794848777e73d6a9502b4e1000f0b07ac96bc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/01/2018
---
# <a name="android-app-protection-policy-settings"></a>Android uygulama koruma ilkesi ayarları
Bu konuda açıklanan ilke ayarları, Azure portalındaki **Ayarlar** dikey penceresinde bir uygulama koruma ilkesi için [yapılandırılabilir](app-protection-policies.md).
İlke ayarlarının, verileri yeniden konumlandırma ayarları ve erişim ayarları olmak üzere iki kategorisi vardır. Bu konuda, *ilkeyle yönetilen uygulamalar* terimi, uygulama koruma ilkeleriyle yapılandırılan uygulamaları ifade eder.

##  <a name="data-relocation-settings"></a>Verileri yeniden konumlandırma ayarları

| Ayar | Nasıl kullanılır? | Varsayılan değer (veya değerler) |
|------|------|------|
| **Android yedeklemelerini engelle** | Bu uygulamanın iş veya okul verilerini **Android Yedekleme Hizmeti**’ne yedeklemesini engellemek için [Evet](https://developer.android.com/google/backup/index.html)’i, bu uygulamanın iş veya okul verilerini yedeklemesine izin vermek için **Hayır**’ı seçin.| Evet |
| **Uygulamanın diğer uygulamalara veri aktarmasına izin ver** | Hangi uygulamaların bu uygulamadan veri alabileceğini belirtin: <ul><li> **İlke ile yönetilen uygulamalar**: Yalnızca diğer ilkeyle yönetilen uygulamalara aktarım yapılmasına izin verilir.</li> <li>**Tüm uygulamalar**: Herhangi bir uygulamaya aktarıma izin verilir. </li> <li>**Hiçbiri**: İlkeyle yönetilen diğer uygulamalar da dahil olmak üzere hiçbir uygulamaya veri aktarmaya izin verilmez.</li></ul> <p>Intune’un veri aktarımı hedefi olarak izin verebileceği bazı muaf uygulamalar ve hizmetler vardır. Uygulama ve hizmetlerin tam listesi için bkz. [Veri aktarımı muafiyetleri](#Data-transfer-exemptions).<p>**Not:** Intune, şu anda Android Instant Apps özelliğini desteklemiyor. Intune, uygulamaya gelen veya uygulamadan giden tüm veri bağlantılarını engelleyecektir.  [Android Instant Apps](https://developer.android.com/topic/instant-apps/index.html) hakkında daha fazla bilgi için Android Geliştirici belgelerine bakın.</p>| Tüm uygulamalar |
| **Uygulamanın diğer uygulamalardan veri almasına izin ver** | Hangi uygulamaların bu uygulamaya veri aktarabileceğini belirtin: <ul><li>**İlke ile yönetilen uygulamalar**: Yalnızca diğer ilkeyle yönetilen uygulamalardan aktarım yapılmasına izin verilir.</li><li>**Tüm uygulamalar**: Herhangi bir uygulamadan veri aktarımına izin verilir.</li><li>**Hiçbiri**: İlkeyle yönetilen diğer uygulamalar da dahil olmak üzere hiçbir uygulamadan veri aktarmaya izin verilmez. </li></ul> <p>Intune’un veri aktarımı kaynağı olarak izin verebileceği bazı muaf uygulamalar ve hizmetler vardır. Uygulama ve hizmetlerin tam listesi için bkz. [Veri aktarımı muafiyetleri](#Data-transfer-exemptions). | Tüm uygulamalar |
| **“Farklı Kaydet”i engelle** | Bu uygulamada Farklı Kaydet seçeneğinin kullanımını devre dışı bırakmak için **Evet**’i seçin. Farklı Kaydet’in kullanılmasına izin vermek istiyorsanız **Hayır** ’ı seçin. <p><br>**Şirket verilerinin kaydedilebileceği depolama hizmetlerini seçin** <br>Kullanıcılar seçili hizmetlere (OneDrive İş, SharePoint ve Yerel Depolama) kaydedebilir. Diğer tüm hizmetler engellenir.</p> | Hayır <br><br> 0 seçili |
| **Diğer uygulamalarla kesme, kopyalama ve yapıştırmayı kısıtlama** | Bu uygulamada kes, kopyala ve yapıştır eylemlerinin ne zaman kullanılabileceğini belirtin. Aşağıdakilerden birini seçin: <ul><li>**Engellendi**: Bu uygulama ve diğer herhangi bir uygulama arasında kesme, kopyalama ve yapıştırma eylemlerine izin verilmez.</li><li>**İlkeyle yönetilen uygulamalar**: Bu uygulama ve diğer ilkeyle yönetilen uygulamalar arasında kesme, kopyalama ve yapıştırma eylemlerine izin verilir.</li><li>**Yapıştırma seçeneğiyle ilke ile yönetilen**: Bu uygulama ve diğer ilkeyle yönetilen uygulamalar arasında kesme veya kopyalama eylemine izin verilir. Herhangi bir uygulamadan verilerin bu uygulamaya yapıştırılmasına izin verir.</li><li>**Herhangi bir uygulama**: Bu uygulamaya veya bu uygulamadan kesme, kopyalama ve yapıştırma eylemleriyle ilgili bir kısıtlama olmaz. | Herhangi bir uygulama |
|**Managed Browser’da görüntülenen web içeriğini kısıtla** | Uygulamadaki web bağlantılarının Managed Browser uygulamasında açılmasını zorunlu kılmak için **Evet**’i seçin. <br><br> Intune’a kayıtlı olmayan cihazlarda, ilke tarafından yönetilen uygulamalardaki web bağlantıları yalnızca Managed Browser uygulamasında açılabilir. <br><br> Cihazlarınızı yönetmek için Intune kullanıyorsanız bkz. [Microsoft Intune'la Managed Browser ilkelerini kullanarak İnternet erişimini yönetme](app-configuration-managed-browser.md). | Hayır |
| **Uygulama verilerini şifreleme** | Bu uygulamada iş veya okul verilerinin şifrelenmesini etkinleştirmek için **Evet**’i seçin. Intune, uygulama verilerini güvenli bir şekilde şifrelemek için Android Keystore sistemiyle birlikte OpenSSL, 128 bit AES şifreleme düzeni kullanır. Veriler, dosya GÇ görevleri sırasında eş zamanlı olarak şifrelenir. Cihaz depolamasındaki içerik her zaman şifrelenir. <br><br> Şifreleme yöntemi FIPS 140-2 sertifikalı **değildir**.  | Evet |
| **Cihaz şifreleme etkin olduğunda uygulama şifrelemeyi devre dışı bırakma** | Kayıtlı bir cihazda cihaz şifreleme algılandığında dahili uygulama deposunda uygulama şifrelemeyi devre dışı bırakmak için **Evet**’i seçin. <br><br>**Not:** Intune, yalnızca Intune MDM ile cihaz kaydını algılayabilir. Yönetilmeyen uygulamalar tarafından verilere erişilmesini engellemek için harici uygulama deposu yine de şifrelenecektir. | Evet |
| **Kişilerin eşitlenmesini devre dışı bırak** | Uygulamanın cihazdaki yerel Kişiler bölümüne veri kaydetmesini engellemek için **Evet**’i seçin. **Hayır**’ı seçerseniz uygulama cihazdaki yerel Kişiler uygulamasına veri kaydedebilir. <br><br>Uygulamadan iş veya okul verilerini kaldırmak için seçmeli silme gerçekleştirdiğinizde, yerel Kişiler uygulamasına doğrudan uygulamadan eşitlenen kişiler kaldırılır. Yerel adres defterinden başka bir dış kaynağa eşitlenen kişiler silinemez. Şu anda bu özellik yalnızca Microsoft Outlook uygulaması için geçerlidir. | Hayır |
| **Yazdırmayı devre dışı bırak** | Uygulamanın iş veya okul verilerini yazdırmasını engellemek için **Evet**’i seçin. | Hayır |

  >[!NOTE]
  >**Uygulama verilerini şifreleme** ayarı için şifreleme yöntemi FIPS 140-2 sertifikalı **değildir**.

  ## <a name="data-transfer-exemptions"></a>Veri aktarımı muafiyetleri

  Intune uygulama koruma ilkesinin, veri aktarımına hedef ve kaynak olarak izin verebileceği bazı muaf uygulamalar ve platform hizmetleri vardır. Örneğin, Android’deki tüm Intune özellikli uygulamalar, Google Metin Okuma’ya ve Google Metin Okuma’dan veri aktarımı gerçekleştirebilmelidir. Böylece mobil cihazınızın ekranındaki metin sesli okunabilir. Bu liste değiştirilebilir ve güvenli verimlilik için kullanışlı olarak nitelendirilen hizmetleri ve uygulamaları yansıtır.

  ### <a name="full-exemptions"></a>Tam muafiyetler

  Bu uygulama ve hizmetlere, Intune tarafından yönetilen uygulamalara ve uygulamalardan veri aktarımına tam olarak izin verilir.

  |Uygulama/hizmet adı | Description |
  | ------ | ---- |
  | com.android.phone | Yerel telefon uygulaması
  | com.android.vending | Google Play Store |
  | com.android.documentsui | Android Belge Seçici|
  | com.google.android.webview | Outlook dahil birçok uygulama için gerekli olan [WebView](https://developer.android.com/reference/android/webkit/WebView.html). |
  | com.android.webview |Outlook dahil birçok uygulama için gerekli olan [WebView](https://developer.android.com/reference/android/webkit/WebView.html).|
  | com.google.android.tts | Google Metin Okuma |
  | com.android.providers.settings | Android sistem ayarları |
  | com.azure.authenticator | Birçok senaryoda başarılı kimlik doğrulaması için gerekli olan Azure Authenticator uygulaması. |
  | com.microsoft.windowsintune.companyportal | Intune Şirket Portalı|

  ### <a name="conditional-exemptions"></a>Koşullu muafiyetler
  Bu uygulama ve hizmetlere, yalnızca belirli koşullar altında Intune tarafından yönetilen uygulamalara ve uygulamalardan veri aktarımına izin verilir.

  |Uygulama/hizmet adı | Description | Muafiyet koşulu|
  | ------ | ---- | --- |
  | com.android.chrome | Google Chrome Tarayıcısı | Chrome, Android 7.0+ sürümünde bazı WebView bileşenleri için kullanılır ve görünümden asla gizlenmez. Ancak uygulamaya giden ve uygulamadan gelen veri akışı her zaman kısıtlandırılır.
  | com.skype.raider | Skype | Skype uygulamasına yalnızca telefon aramasıyla biten belirli eylemlerde izin verilir. |
  | com.android.providers.media | Android medya içeriği sağlayıcısı | Yalnızca zil sesi seçimi eyleminde izin verilen medya içeriği sağlayıcısı. |
  | com.google.android.gms; com.google.android.gsf | Google Play Hizmetleri paketleri | Bu paketlere, anında iletme bildirimleri gibi Google Cloud Messaging eylemleri için izin verilir. |



##  <a name="access-settings"></a>Erişim ayarları

| Ayar | Nasıl kullanılır? | Varsayılan değer (veya değerler) |
|------|------|------|
| **Erişim için PIN’i zorunlu kıl** | Bu uygulamayı kullanmak için PIN’i zorunlu kılmak üzere **Evet**’i seçin. Uygulamayı iş veya okul bağlamında ilk kez çalıştırdığında kullanıcıdan bu PIN’i ayarlaması istenir. Varsayılan değer = **Evet**.<br><br> PIN gücü için aşağıdaki ayarları yapılandırın: <ul><li>**PIN sıfırlamadan önceki deneme sayısı**: Kullanıcının PIN’ini sıfırlamak zorunda kalmadan önce başarılı bir şekilde girmesi gereken deneme sayısını belirtin. Varsayılan değer = **5**.</li><li> **Basit PIN’e izin ver:** Kullanıcıların 1234 veya 1111 gibi basit PIN dizileri kullanmasına izin vermek için **Evet**’i seçin. Basit PIN dizileri kullanmalarını engellemek için **Hayır**’ı seçin. Varsayılan değer = **Evet**. </li><li> **PIN uzunluğu:** PIN dizisindeki basamak sayısı alt sınırını belirtin. Varsayılan değer = **4**. <br><br> Bu ilke ayarı biçimi pozitif tamsayıyı destekler.</li><li> **PIN yerine parmak izine izin ver (Android 6.0+)**: Uygulama erişiminde bir PIN yerine **parmak izi kimlik doğrulaması** kullanmasına izin vermek için [Evet](https://developer.android.com/about/versions/marshmallow/android-6.0.html#fingerprint-authentication)’i seçin. Varsayılan değer = **Evet**.</li></ul> Android cihazlarda kullanıcının kimliğini kanıtlaması için PIN yerine [Android parmak izi kimlik doğrulaması](https://developer.android.com/about/versions/marshmallow/android-6.0.html#fingerprint-authentication) kullanmasına izin verebilirsiniz. Kullanıcı, iş veya okul hesabıyla bu uygulamayı kullanmayı denediğinde, PIN girmek yerine parmak izi kimliğini vermesi istenir. </li></ul>| PIN’i zorunlu kıl: Evet <br><br> PIN sıfırlama girişimi: 5 <br><br> Basit PIN’e izin ver: Evet <br><br> PIN uzunluğu: 4 <br><br> Parmak izine izin ver: Evet |
| **Erişim için kurumsal kimlik bilgileri gerektir** | Kullanıcının uygulama erişimi için PIN girmek yerine iş veya okul hesabıyla oturum açmasını zorunlu kılmak için **Evet**’i seçin. **Evet** olarak ayarlarsanız, bu ayar PIN veya Touch ID gereksinimlerini geçersiz kılar.  | Hayır |
| **Yönetilen cihazların, jailbreak uygulanmış veya kök erişim izni verilmiş cihazlarda çalışmasını engelle** |Bu uygulamaya jailbreak uygulanmış veya kök erişim izni verilmiş cihazlarda çalışmasını engellemek için **Evet**’i seçin. Kullanıcı kişisel görevler için uygulamaları kullanmaya devam edebilir, ancak bu uygulamada iş veya okul verilerine erişmek için farklı bir cihaz kullanması gerekir. | Evet |
| **Erişim gereksinimlerini şu süreden sonra yeniden denetle (dakika)** | Aşağıdaki ayarları yapılandırın: <ul><li>**Zaman Aşımı**: Erişim gereksinimleri (daha önce ilkelerde tanımlanmıştır) yeniden denetlenmeden önce geçmesi gereken dakika sayısıdır. Örneğin, yönetici ilkede PIN’i etkinleştirirse, kullanıcı Intune ile yönetilen bir uygulama açtığında bir PIN girmesi gerekir. Bu ayar kullanıldığında, kullanıcının **30 dakika** (varsayılan değer) boyunca herhangi bir Intune ile yönetilen uygulamada PIN girmesi gerekmez. <br><br> **Not:** Android’de PIN, tüm Intune ile yönetilen uygulamalar arasında paylaşılır. Uygulama cihazda ön plandan ayrıldığında, PIN zamanlayıcısı sıfırlanır. Bu ayarda tanımlanan zaman aşımı süresince PIN’ini paylaşan Intune ile yönetilen herhangi bir uygulamada, kullanıcının bir PIN girmesi gerekmez. <br><br> Bu ilke ayarı biçimi pozitif tamsayıyı destekler.<br></li><li>**Çevrimdışı yetkisiz kullanım süresi**: Uygulama için erişim gereksinimleri yeniden denetlenmeden önce MAM uygulamalarının çevrimdışı çalışabileceği dakika sayısıdır. Varsayılan değer = **720** dakika (12 saat). Bu süre dolduktan sonra, uygulama, çalışmaya devam edebilmesi için kullanıcının AAD’de kimliğini doğrulamasını ister.<br><br> Bu ilke ayarı biçimi pozitif tamsayıyı destekler.</li></ul>| Zaman Aşımı: 30 <br><br> Çevrimdışı: 720 |
| **Uygulama verileri silinmeden önceki çevrimdışı zaman aralığı (gün)** | Yönetici tarafından tanımlanan bu süre boyunca çevrimdışı çalıştığında uygulama, kullanıcıdan ağa bağlanmasını ve yeniden kimlik doğrulamasını ister. Kullanıcı başarıyla oturum açarsa, verilerine erişmeye devam edebilir ve çevrimdışı zaman aralığı sıfırlanır.  Kullanıcı kimlik doğrulaması başarısız olursa uygulama, kullanıcı hesabı ve verilerinde seçmeli silme gerçekleştirir.  Seçmeli silme ile hangi verilerin silindiği hakkında daha fazla bilgi için bkz. [Intune ile yönetilen uygulamalarda yalnızca şirket verilerini silme](https://docs.microsoft.com/intune/apps-selective-wipe).<br><br> Bu ilke ayarı biçimi pozitif tamsayıyı destekler. | 90 gün |
| **Ekran görüntüsü yakalamayı ve Android Assistant uygulamasını (Android 6.0+) engelle** | Uygulama kullanılırken cihazın ekran yakalama ve **Android Assistant** özelliklerini engellemek için **Evet**’i seçin. **Evet**’i seçmek, bu uygulama bir iş veya okul hesabıyla kullanılırken Uygulama değiştirici önizleme görüntüsünü de bulanık hale getirir. | Hayır |
| **Cihaz PIN’i yönetildiği zaman uygulama PIN’ini devre dışı bırak** | Kayıtlı bir cihazda bir cihaz kilidi algılandığında, uygulama PIN’ini devre dışı bırakmak için **Evet**’i seçin. | Hayır |
| **En düşük Android işletim sistemini zorunlu tut** | Bu uygulamanın kullanılabilmesi için en düşük Android işletim sistemini zorunlu tutmak için **Evet**’i seçin. Cihazın Android sürümü gereksinimi karşılamıyorsa, kullanıcının uygulamaya erişimi engellenir.<br><br> Bu ilke ayarı biçimi birincil.ikincil, birincil.ikincil.derleme, birincil.ikincil.derleme.düzeltme'yi destekler.| Hayır |
| **En düşük Android işletim sistemini zorunlu tut (Yalnızca uyarı)** | Bu uygulamanın kullanılabilmesi için en düşük Android işletim sistemini zorunlu tutmak için **Evet**’i seçin. Cihazdaki Android sürümü gereksinimi karşılamıyorsa, kullanıcı bir bildirim görür. Bu bildirim kapatılabilir.<br><br> Bu ilke ayarı biçimi birincil.ikincil, birincil.ikincil.derleme, birincil.ikincil.derleme.düzeltme'yi destekler. | Hayır |
| **En düşük uygulama sürümünü zorunlu tut** | Uygulamanın kullanılabilmesi için en düşük uygulama sürümünü zorunlu tutmak üzere **Evet**’i seçin. Cihazın uygulama sürümü gereksinimi karşılamıyorsa, kullanıcının uygulamaya erişimi engellenir.<br><br>Uygulamalar arasında genellikle farklı sürüm şemaları bulunduğundan, en az bir uygulama sürümünün bir uygulamayı (örneğin, "Outlook sürüm ilkesi") hedeflediği bir ilke oluşturun. <br><br> Bu ilke ayarı biçimi birincil.ikincil, birincil.ikincil.derleme, birincil.ikincil.derleme.düzeltme'yi destekler.| Hayır | 
| **En düşük uygulama sürümünü zorunlu tut (Yalnızca uyarı)** | Bu uygulamanın kullanılabilmesi için en düşük uygulama sürümünü önermek için **Evet**’i seçin. Cihazdaki uygulama sürümü gereksinimi karşılamıyorsa, kullanıcı bir bildirim görür. Bu bildirim kapatılabilir.<br><br>Uygulamalar arasında genellikle farklı sürüm şemaları bulunduğundan, en az bir uygulama sürümünün bir uygulamayı (örneğin, "Outlook sürüm ilkesi") hedeflediği bir ilke oluşturun. <br><br> Bu ilke ayarı biçimi birincil.ikincil, birincil.ikincil.derleme, birincil.ikincil.derleme.düzeltme'yi destekler.| Hayır | 
| **En Düşük Android Düzeltme Eki Sürümü Gerektirir** | Google tarafından yayınlanan Android güvenlik düzeltme eklerinde alt sınır gerektirmek için **Evet**’i seçin. Cihazın Android düzeltme eki gereksinimi karşılamıyorsa, kullanıcının uygulamaya erişimi engellenir.<br><br> Bu ilke ayarı biçimi YYYY-AA-GG tarih biçimini destekler. | Hayır |
| **En Düşük Android Düzeltme Eki Sürümü Gerektir (Yalnızca Uyarı)** | Google tarafından yayınlanan Android güvenlik düzeltme eklerinde alt sınır gerektirmek için **Evet**’i seçin. Cihazdaki Android güvenlik düzeltme eki gereksinimi karşılamıyorsa, kullanıcı bir bildirim görür. Bu bildirim kapatılabilir.<br><br> Bu ilke ayarı biçimi YYYY-AA-GG tarih biçimini destekler. | Hayır |
