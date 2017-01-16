---
title: "Android MAM ilke ayarları | Microsoft Docs"
description: "Bu konu başlığı altında, Android cihazları için mobil uygulama yönetimi ilkesi ayarları açıklanır."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 09/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5dbb702a-1df5-4637-95c9-77a5f0b1a0e3
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 28a1bf4c7c2200901761a53394064d920b56dad6
ms.openlocfilehash: 058527911594614865ae44ba9de7ab0887fa60b2


---

# <a name="android-mobile-app-management-policy-settings-in-microsoft-intune"></a>Microsoft Intune’da Android mobil uygulaması yönetim ilkesi ayarları

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Bu konuda açıklanan ilke ayarları, Azure portalındaki **Ayarlar** dikey penceresinde mobil uygulama yönetimi (MAM) ilkesi için [yapılandırılabilir](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md).
İlke ayarlarının, verileri yeniden konumlandırma ayarları ve erişim ayarları olmak üzere iki kategorisi vardır. Bu konuda, _**ilkeyle yönetilen uygulamalar**_ terimi, MAM ilkeleriyle yapılandırılan uygulamaları ifade eder.


##  <a name="data-relocation-settings"></a>Verileri yeniden konumlandırma ayarları

| Ayar | Nasıl kullanılır? | Varsayılan değer (veya değerler) |
|------|------|------|
| **Android yedeklemelerini engelle** | Bu uygulamanın iş veya okul verilerini **Android Yedekleme Hizmeti**’ne yedeklemesini engellemek için [Evet](https://developer.android.com/google/backup/index.html)’i, bu uygulamanın iş veya okul verilerini yedeklemesine izin vermek için **Hayır**’ı seçin.| Evet |
| **Uygulamanın diğer uygulamalara veri aktarmasına izin ver** | Hangi uygulamaların bu uygulamadan veri alabileceğini belirtin: <ul><li> **İlke ile yönetilen uygulamalar**: Yalnızca diğer ilkeyle yönetilen uygulamalara aktarım yapılmasına izin verilir.</li> <li>**Tüm uygulamalar**: Herhangi bir uygulamaya aktarıma izin verilir. </li> <li>**Hiçbiri**: İlkeyle yönetilen diğer uygulamalar da dahil olmak üzere hiçbir uygulamaya veri aktarmaya izin verilmez.</li></ul> | Tüm uygulamalar |
| **Uygulamanın diğer uygulamalardan veri almasına izin ver** | Hangi uygulamaların bu uygulamaya veri aktarabileceğini belirtin: <ul><li>**İlke ile yönetilen uygulamalar**: Yalnızca diğer ilkeyle yönetilen uygulamalardan aktarım yapılmasına izin verilir.</li><li>**Tüm uygulamalar**: Herhangi bir uygulamadan veri aktarımına izin verilir.</li><li>**Hiçbiri**: İlkeyle yönetilen diğer uygulamalar da dahil olmak üzere hiçbir uygulamadan veri aktarmaya izin verilmez. | Tüm uygulamalar |
| **“Farklı Kaydet”i engelle** | Bu uygulamada Farklı Kaydet seçeneğinin kullanımını devre dışı bırakmak için **Evet**’i seçin. Farklı Kaydet’in kullanılmasına izin vermek istiyorsanız **Hayır** ’ı seçin. | Hayır |
| **Diğer uygulamalarla kesme, kopyalama ve yapıştırmayı kısıtlama** | Bu uygulamada kes, kopyala ve yapıştır eylemlerinin ne zaman kullanılabileceğini belirtin. Aşağıdakilerden birini seçin: <ul><li>**Engellendi**: Bu uygulama ve diğer herhangi bir uygulama arasında kesme, kopyalama ve yapıştırma eylemlerine izin verilmez.</li><li>**İlkeyle yönetilen uygulamalar**: Bu uygulama ve diğer ilkeyle yönetilen uygulamalar arasında kesme, kopyalama ve yapıştırma eylemlerine izin verilir.</li><li>**Yapıştırma seçeneğiyle ilke ile yönetilen**: Bu uygulama ve diğer ilkeyle yönetilen uygulamalar arasında kesme veya kopyalama eylemine izin verilir. Herhangi bir uygulamadan verilerin bu uygulamaya yapıştırılmasına izin verir.</li><li>**Herhangi bir uygulama**: Bu uygulamaya veya bu uygulamadan kesme, kopyalama ve yapıştırma eylemleriyle ilgili bir kısıtlama olmaz. | Herhangi bir uygulama |
|**Managed Browser’da görüntülenen web içeriğini kısıtla** | Uygulamadaki web bağlantılarının Managed Browser uygulamasında açılmasını zorunlu kılmak için **Evet**’i seçin. <br><br> Intune’a kayıtlı olmayan cihazlarda, ilke tarafından yönetilen uygulamalardaki web bağlantıları yalnızca Managed Browser uygulamasında açılabilir. <br><br> Cihazlarınızı yönetmek için Intune kullanıyorsanız bkz. [Microsoft Intune'la Managed Browser ilkelerini kullanarak İnternet erişimini yönetme](manage-internet-access-using-managed-browser-policies.md). | Hayır |
| **Uygulama verilerini şifreleme** | Bu uygulamada iş veya okul verilerinin şifrelenmesini etkinleştirmek için **Evet**’i seçin. Intune uygulama verilerini güvenli bir şekilde şifrelemek için Android Keystore sistemiyle birlikte OpenSSL şifreleme şeması kullanır. Veriler, dosya GÇ görevleri sırasında eş zamanlı olarak şifrelenir. Cihaz depolamasındaki içerik her zaman şifrelenir. <br><br> Şifreleme yöntemi FIPS 140-2 sertifikalı **değildir**.  | Evet |
| **Kişilerin eşitlenmesini devre dışı bırak** | Uygulamanın cihazdaki yerel Kişiler bölümüne veri kaydetmesini engellemek için **Evet**’i seçin. **Hayır**’ı seçerseniz uygulama cihazdaki yerel Kişiler uygulamasına veri kaydedebilir. <br><br>Uygulamadan iş veya okul verilerini kaldırmak için seçmeli silme gerçekleştirdiğinizde, yerel Kişiler uygulamasına doğrudan uygulamadan eşitlenen kişiler kaldırılır. Yerel adres defterinden başka bir dış kaynağa eşitlenen kişiler silinemez. Şu anda bu özellik yalnızca Microsoft Outlook uygulaması için geçerlidir. | Hayır |
| **Yazdırmayı devre dışı bırak** | Uygulamanın iş veya okul verilerini yazdırmasını engellemek için **Evet**’i seçin. | Hayır |


  >[!NOTE]
  >**Uygulama verilerini şifreleme** ayarı için şifreleme yöntemi FIPS 140-2 sertifikalı **değildir**.




##  <a name="access-settings"></a>Erişim ayarları

| Ayar | Nasıl kullanılır? | Varsayılan değer (veya değerler) |
|------|------|------|
| **Erişim için PIN’i zorunlu kıl** | Bu uygulamayı kullanmak için PIN’i zorunlu kılmak üzere **Evet**’i seçin. Uygulamayı iş veya okul bağlamında ilk kez çalıştırdığında kullanıcıdan bu PIN’i ayarlaması istenir. Varsayılan değer = **Evet**.<br><br> PIN gücü için aşağıdaki ayarları yapılandırın: <ul><li>**PIN sıfırlamadan önceki deneme sayısı**: Kullanıcının PIN’ini sıfırlamak zorunda kalmadan önce başarılı bir şekilde girmesi gereken deneme sayısını belirtin. Varsayılan değer = **5**.</li><li> **Basit PIN’e izin ver:** Kullanıcıların 1234 veya 1111 gibi basit PIN dizileri kullanmasına izin vermek için **Evet**’i seçin. Basit PIN dizileri kullanmalarını engellemek için **Hayır**’ı seçin. Varsayılan değer = **Evet**. </li><li> **PIN uzunluğu:** PIN dizisindeki basamak sayısı alt sınırını belirtin. Varsayılan değer = **4**. </li><li> **PIN yerine parmak izine izin ver (Android 6.0+)**: Uygulama erişiminde bir PIN yerine **parmak izi kimlik doğrulaması** kullanmasına izin vermek için [Evet](https://developer.android.com/about/versions/marshmallow/android-6.0.html#fingerprint-authentication)’i seçin. Varsayılan değer = **Evet**.<br><br> Android cihazlarda kullanıcının kimliğini kanıtlaması için PIN yerine [Android parmak izi kimlik doğrulaması](https://developer.android.com/about/versions/marshmallow/android-6.0.html#fingerprint-authentication) kullanmasına izin verebilirsiniz. Kullanıcı, iş veya okul hesabıyla bu uygulamayı kullanmayı denediğinde, PIN girmek yerine parmak izi kimliğini vermesi istenir. </li></ul>| PIN’i zorunlu kıl: Evet <br><br> PIN sıfırlama girişimi: 5 <br><br> Basit PIN’e izin ver: Evet <br><br> PIN uzunluğu: 4 <br><br> Parmak izine izin ver: Evet |
| **Erişim için kurumsal kimlik bilgileri gerektir** | Kullanıcının uygulama erişimi için PIN girmek yerine iş veya okul hesabıyla oturum açmasını zorunlu kılmak için **Evet**’i seçin. **Evet** olarak ayarlarsanız, bu ayar PIN veya Touch ID gereksinimlerini geçersiz kılar.  | Hayır |
| **Yönetilen cihazların, jailbreak uygulanmış veya kök erişim izni verilmiş cihazlarda çalışmasını engelle** |  Bu uygulamaya jailbreak uygulanmış veya kök erişim izni verilmiş cihazlarda çalışmasını engellemek için **Evet**’i seçin. Kullanıcı kişisel görevler için uygulamaları kullanmaya devam edebilir, ancak bu uygulamada iş veya okul verilerine erişmek için farklı bir cihaz kullanması gerekir. | Evet |
| **Erişim gereksinimlerini şu süreden sonra yeniden denetle (dakika)** | Aşağıdaki ayarları yapılandırın: <ul><li>**Zaman aşımı:** Uygulama için erişim gereksinimleri yeniden denetlenmeden önce geçmesi gereken süreyi (dakika cinsinden) belirtin. Varsayılan değer = **30** dakika.</li><li>**Çevrimdışı kullanım süresi:** Cihaz çevrimdışıyken uygulama için erişim gereksinimleri yeniden denetlenmeden önce geçmesi gereken süreyi (dakika olarak) belirtin. Varsayılan değer = **720** dakika (12 saat).</li></ul>| Zaman Aşımı: 30 <br><br> Çevrimdışı: 720 |
| **Uygulama verileri silinmeden önceki çevrimdışı zaman aralığı (gün)** | Bir cihaz belirli bir süreden fazla çevrimdışı kalmışsa bu uygulamadaki iş veya okul verileri silinebilir. Cihazın kaç gün çevrimdışı kaldıktan sonra içindeki iş veya okul verilerinin silineceğini belirtin. <br><br> | 90 gün |
| **Ekran görüntüsü yakalamayı ve Android Assistant uygulamasını (Android 6.0+) engelle** | Uygulama kullanılırken cihazın ekran yakalama ve **Android Assistant** özelliklerini engellemek için **Evet**’i seçin. **Evet**’i seçmek, bu uygulama bir iş veya okul hesabıyla kullanılırken Uygulama değiştirici önizleme görüntüsünü de bulanık hale getirir. | Hayır |



<!--HONumber=Dec16_HO3-->


