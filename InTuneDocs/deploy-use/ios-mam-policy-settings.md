---
title: "iOS MAM ilke ayarları | Microsoft Docs"
description: "Bu konu başlığı altında, iOS cihazları için mobil uygulama yönetimi ilkesi ayarları açıklanır."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 09/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 673ff872-943c-4076-931c-0be90363aea9
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d80f548f0c1382e1bd024bd31078d2a4e6366656
ms.openlocfilehash: a2130fa76f66528f6e77c720bc93286e0d01aba2


---

#  <a name="ios-mobile-app-management-policy-settings"></a>iOS mobil uygulama yönetimi ilkesi ayarları

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Bu konuda açıklanan ilke ayarları, Azure portalındaki **Ayarlar** dikey penceresinde mobil uygulama yönetimi (MAM) ilkesi için [yapılandırılabilir](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md).

İlke ayarlarının, verileri yeniden konumlandırma ayarları ve erişim ayarları olmak üzere iki kategorisi vardır. Bu konuda, _**ilkeyle yönetilen uygulamalar**_ terimi, MAM ilkeleriyle yapılandırılan uygulamaları ifade eder.

##  <a name="data-relocation-settings"></a>Verileri yeniden konumlandırma ayarları

| Ayar | Nasıl kullanılır? | Varsayılan değer |
|------|------|------|
| **iTunes ve iCloud yedeklemelerini engelle** | Bu uygulamanın iş veya okul verilerini iTunes veya iCloud’a yedeklemesini engellemek için **Evet**’i seçin. Bu uygulamanın iş veya okul verilerini iTunes veya iCloud’a yedeklemesine izin vermek için **Hayır**’ı seçin.| Evet |
| **Uygulamanın diğer uygulamalara veri aktarmasına izin ver** | Hangi uygulamaların bu uygulamadan veri alabileceğini belirtin: <ul><li> **İlke ile yönetilen uygulamalar**: Yalnızca diğer ilkeyle yönetilen uygulamalara aktarım yapılmasına izin verilir.</li> <li>**Tüm uygulamalar**: Herhangi bir uygulamaya aktarıma izin verilir. </li> <li>**Hiçbiri**: İlkeyle yönetilen diğer uygulamalar da dahil olmak üzere hiçbir uygulamaya veri aktarmaya izin verilmez.</li></ul> Ayrıca, bu seçeneği **İlke ile yönetilen uygulamalar** veya **Hiçbiri** olarak ayarlarsanız uygulamaların içindeki verileri aramak için Spotlight Arama özelliğine imkan tanıyan iOS 9 özelliği engellenir. <br><br> | Tüm uygulamalar |
| **Uygulamanın diğer uygulamalardan veri almasına izin ver** | Hangi uygulamaların bu uygulamaya veri aktarabileceğini belirtin: <ul><li>**İlke ile yönetilen uygulamalar**: Yalnızca diğer ilkeyle yönetilen uygulamalardan aktarım yapılmasına izin verilir.</li><li>**Tüm uygulamalar**: Herhangi bir uygulamadan veri aktarımına izin verilir.</li><li>**Hiçbiri**: İlkeyle yönetilen diğer uygulamalar da dahil olmak üzere hiçbir uygulamadan veri aktarmaya izin verilmez. | Tüm uygulamalar |
| **“Farklı Kaydet”i engelle** | Bu uygulamada Farklı Kaydet seçeneğinin kullanımını devre dışı bırakmak için **Evet**’i seçin. Farklı Kaydet’in kullanılmasına izin vermek istiyorsanız **Hayır** ’ı seçin. | Hayır |
| **Diğer uygulamalarla kesme, kopyalama ve yapıştırmayı kısıtlama** | Bu uygulamada kes, kopyala ve yapıştır eylemlerinin ne zaman kullanılabileceğini belirtin. Aşağıdakilerden birini seçin: <ul><li>**Engellendi**: Bu uygulama ve diğer herhangi bir uygulama arasında kesme, kopyalama ve yapıştırma eylemlerine izin verilmez.</li><li>**İlkeyle yönetilen uygulamalar**: Bu uygulama ve diğer ilkeyle yönetilen uygulamalar arasında kesme, kopyalama ve yapıştırma eylemlerine izin verilir.</li><li>**Yapıştırma seçeneğiyle ilke ile yönetilen**: Bu uygulama ve diğer ilkeyle yönetilen uygulamalar arasında kesme veya kopyalama eylemine izin verilir. Herhangi bir uygulamadan verilerin bu uygulamaya yapıştırılmasına izin verir.</li><li>**Herhangi bir uygulama**: Bu uygulamaya veya bu uygulamadan kesme, kopyalama ve yapıştırma eylemleriyle ilgili bir kısıtlama olmaz. | Herhangi bir uygulama |
|**Managed Browser’da görüntülenen web içeriğini kısıtla** | Uygulamadaki web bağlantılarının Managed Browser uygulamasında açılmasını zorunlu kılmak için **Evet**’i seçin. <br><br> Intune’a kayıtlı olmayan cihazlarda, ilke tarafından yönetilen uygulamalardaki web bağlantıları yalnızca Managed Browser uygulamasında açılabilir. <br><br> Cihazlarınızı yönetmek için Intune kullanıyorsanız bkz. [Microsoft Intune'la Managed Browser ilkelerini kullanarak İnternet erişimini yönetme](manage-internet-access-using-managed-browser-policies.md). | Hayır |
| **Uygulama verilerini şifreleme** | İlkeyle yönetilen uygulamalarda, etkin olmayan veriler iOS tarafından sağlanan cihaz düzeyinde şifreleme şeması kullanılarak şifrelenir. PIN istendiğinde, veriler uygulama koruma ilkesi ayarlarına göre şifrelenir. <br><br> Hangi iOS şifreleme modüllerinin FIPS 140-2 sertifikalı veya FIPS 140-2 sertifikası bekliyor olduğunu görmek için [buradaki](https://support.apple.com/HT202739) resmi Apple belgelerine gidin. <br><br> Bu uygulamadaki iş veya okul verilerinin ne zaman şifreleneceğini belirtin. Aşağıdakilerden birini seçin: <ul><li>**Cihaz kilitliyken**: Cihaz kilitliyken, bu ilkeyle ilişkilendirilen tüm uygulama verileri şifrelenir.</li><li>**Cihaz kilitliyken ve açık dosyalar varken**: Cihaz kilitliyken, uygulamada o anda açık olan dosyalardaki veriler dışında bu ilkeyle ilişkilendirilen tüm uygulama verileri şifrelenir.</li><li>**Cihaz yeniden başlatıldıktan sonra**: Cihaz yeniden başlatıldığında, bu ilkeyle ilişkilendirilen tüm uygulama verileri cihaz kilidinin ilk açılışına kadar şifrelenir.</li><li>**Cihaz ayarlarını kullan**: Uygulama verileri, cihazdaki varsayılan ayarlara göre şifrelenir. <br><br> Bu ayarı etkinleştirdiğinizde kullanıcının cihazına erişmesi için bir PIN ayarlaması ve bu PIN’i kullanması gerekir.  Cihaz erişimi için PIN ayarlanmadıysa uygulamalar açılmaz ve “Kuruluşunuz, bu uygulamaya erişmek için öncelikle bir cihaz PIN’i etkinleştirmenizi gerektiriyor” iletisiyle birlikte kullanıcıdan bir PIN ayarlaması istenir. </li></ul> | Cihaz kilitliyken |
| **Kişilerin eşitlenmesini devre dışı bırak** | Uygulamanın cihazdaki yerel Kişiler bölümüne veri kaydetmesini engellemek için **Evet**’i seçin. **Hayır**’ı seçerseniz uygulama cihazdaki yerel Kişiler uygulamasına veri kaydedebilir. <br><br>Uygulamadan iş veya okul verilerini kaldırmak için seçmeli silme gerçekleştirdiğinizde, yerel Kişiler uygulamasına doğrudan uygulamadan eşitlenen kişiler kaldırılır. Yerel adres defterinden başka bir dış kaynağa eşitlenen kişiler silinemez. Şu anda bu özellik yalnızca Microsoft Outlook uygulaması için geçerlidir. | Hayır |
| **Yazdırmayı devre dışı bırak** | Uygulamanın iş veya okul verilerini yazdırmasını engellemek için **Evet**’i seçin. | Hayır |


> [!NOTE]
> Verileri yeniden konumlandırma ayarlarının hiçbiri iOS cihazlarında Apple tarafından yönetilen birlikte aç özelliğini denetlemez. Apple birlikte aç özelliğini kullanmak için bkz. [Microsoft Intune ile iOS uygulamaları arasında veri aktarımını yönetme](manage-data-transfer-between-ios-apps-with-microsoft-intune.md).


## <a name="access-settings"></a>Erişim ayarları

| Ayar | Nasıl kullanılır? | Varsayılan değer |
|------|------|------|
| **Erişim için PIN’i zorunlu kıl** | Bu uygulamayı kullanmak için PIN’i zorunlu kılmak üzere **Evet**’i seçin. Uygulamayı iş veya okul bağlamında ilk kez çalıştırdığında kullanıcıdan bu PIN’i ayarlaması istenir. Varsayılan değer = **Evet**.<br><br> PIN gücü için aşağıdaki ayarları yapılandırın: <ul><li>**PIN sıfırlamadan önceki deneme sayısı**: Kullanıcının PIN’ini sıfırlamak zorunda kalmadan önce başarılı bir şekilde girmesi gereken deneme sayısını belirtin. Varsayılan değer = **5**.</li><li> **Basit PIN’e izin ver:** Kullanıcıların 1234 veya 1111 gibi basit PIN dizileri kullanmasına izin vermek için **Evet**’i seçin. Basit PIN dizileri kullanmalarını engellemek için **Hayır**’ı seçin. Varsayılan değer = **Evet**. </li><li> **PIN Uzunluğu:** PIN dizisindeki basamak sayısı alt sınırını belirtin. Varsayılan değer = **4**. </li><li> **PIN yerine parmak izine izin ver (iOS 8.0+)**: Uygulama erişiminde bir PIN yerine **Touch ID** kullanmasına izin vermek için [Evet](https://support.apple.com/en-us/HT201371)’i seçin. Varsayılan değer = **Evet**.<br><br> iOS cihazlarda, kullanıcıların kimliklerini kanıtlamak için PIN yerine [Touch ID](https://support.apple.com/en-us/HT201371) kullanmasına izin verebilirsiniz. Kullanıcı, iş veya okul hesabıyla bu uygulamayı kullanmayı denediğinde, PIN girmek yerine parmak izi kimliğini vermesi istenir. </li></ul>| PIN’i zorunlu kıl: Evet <br><br> PIN sıfırlama girişimi: 5 <br><br> Basit PIN’e izin ver: Evet <br><br> PIN uzunluğu: 4 <br><br> Parmak izine izin ver: Evet |
| **Erişim için kurumsal kimlik bilgileri gerektir** | Kullanıcının uygulama erişimi için PIN girmek yerine iş veya okul hesabıyla oturum açmasını zorunlu kılmak için **Evet**’i seçin. **Evet** olarak ayarlarsanız, bu ayar PIN veya Touch ID gereksinimlerini geçersiz kılar.  | Hayır |
| **Yönetilen cihazların, jailbreak uygulanmış veya kök erişim izni verilmiş cihazlarda çalışmasını engelle** |  Bu uygulamaya jailbreak uygulanmış veya kök erişim izni verilmiş cihazlarda çalışmasını engellemek için **Evet**’i seçin. Kullanıcı kişisel görevler için uygulamaları kullanmaya devam edebilir, ancak bu uygulamada iş veya okul verilerine erişmek için farklı bir cihaz kullanması gerekir. | Evet |
| **Erişim gereksinimlerini şu süreden sonra yeniden denetle (dakika)** | Aşağıdaki ayarları yapılandırın: <ul><li>**Zaman aşımı:** Uygulama için erişim gereksinimleri yeniden denetlenmeden önce geçmesi gereken süreyi (dakika cinsinden) belirtin. Varsayılan değer = **30** dakika.</li><li>**Çevrimdışı kullanım süresi:** Cihaz çevrimdışıyken uygulama için erişim gereksinimleri yeniden denetlenmeden önce geçmesi gereken süreyi (dakika olarak) belirtin. Varsayılan değer = **720** dakika (12 saat).</li></ul>| Zaman Aşımı: 30 <br><br> Çevrimdışı: 720 |
| **Uygulama verileri silinmeden önceki çevrimdışı zaman aralığı (gün)** | Bir cihaz belirli bir süreden fazla çevrimdışı kalmışsa bu uygulamadaki iş veya okul verileri silinebilir. Cihazın kaç gün çevrimdışı kaldıktan sonra içindeki iş veya okul verilerinin silineceğini belirtin. <br><br> | 90 gün |



<!--HONumber=Dec16_HO3-->


