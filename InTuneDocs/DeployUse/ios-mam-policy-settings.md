---
title: "iOS MAM ilke ayarları | Microsoft Intune"
description: "Bu konu başlığı altında, iOS cihazları için mobil uygulama yönetimi ilkesi ayarları açıklanır."
keywords: 
author: karthikaraman
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
ms.sourcegitcommit: 3f6e500ef942e0f0e89ffd9ddb4889384f296e16
ms.openlocfilehash: 36d21aee42c8a4812b1ed9623be2da3e65442bff


---

#  iOS mobil uygulama yönetimi ilkesi ayarları
Aşağıda açıklanan ilke ayarları, Azure portalındaki **Ayarlar** dikey penceresinde MAM ilkesi için [yapılandırılabilir](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md).

İlke ayarlarının, Verileri yeniden konumlandırma ve Erişim ayarları olarak iki kategorisi vardır:

##  Verileri yeniden konumlandırma ayarları
**İlkeyle yönetilen uygulamalar** terimi, MAM ilkeleriyle yapılandırılan uygulamalar için kullanılır.

- **iTunes ve iCloud yedeklemelerini engelle:** İlkeyle yönetilen uygulamalardan şirket verilerini yedeklemeyi devre dışı bırakmak için **Evet**’i veya bu yedeklemeye izin vermek için **Hayır**’ı seçin.

  **Varsayılan değer = Evet**

- **Uygulamanın diğer uygulamalara veri aktarmasına izin ver:**   İlkeyle yönetilen uygulamalardan veri alabilecek uygulamaları göstermek için seçeneklerden birini belirtin:
  - **İlke ile yönetilen uygulamalar**: Yalnızca MAM ilkesi olan uygulamalara aktarıma izin verilir.
  - **Tüm uygulamalar**: Herhangi bir uygulamaya aktarıma izin verilir.
  - **Hiçbiri**: İlkeyle yönetilen diğer uygulamalar da dahil olmak üzere hiçbir uygulamaya veri aktarmaya izin verilmez.

  Ayrıca, bu seçeneği **İlke ile Yönetilen Uygulamalar** veya **Hiçbiri** olarak ayarlarsanız uygulamaların içindeki verileri aramak için Spotlight Arama özelliğine imkan tanıyan iOS 9 özelliği engellenir.

  **Bu ayar, mobil cihazlardaki Birlikte Aç özelliğinin kullanımını denetlemez. Birlikte Aç özelliğini yönetmek için [buraya](manage-data-transfer-between-ios-apps-with-microsoft-intune.md)** bakın.

  **Varsayılan değer = İlke ile yönetilen uygulamalar**

- **Uygulamanın diğer uygulamalardan veri almasına izin ver:** İlkeyle yönetilen uygulamalara veri aktarmasına izin verilen uygulamaları belirtin:
  -  **İlke ile yönetilen uygulamalar**: Yalnızca diğer ilkeyle yönetilen uygulamalardan veri aktarımlarına izin verilir.
  -  **Tüm uygulamalar**: Herhangi bir uygulamadan veri aktarımına izin verilir.
  -  **Hiçbiri**: Hiçbir uygulamadan veri aktarımına izin verilmez.

  **Varsayılan değer = Tüm uygulamalar**

- **Farklı Kaydet seçeneğini engelle:** Bu ilkeyi kullanan uygulamalarda Farklı Kaydet seçeneğinin kullanımını devre dışı bırakmak için **Evet**’i seçin. Farklı Kaydet’in kullanılmasına izin vermek istiyorsanız **Hayır** ’ı seçin.

  **Varsayılan değer = Evet**

- **Diğer uygulamalarla kesme, kopyalama ve yapıştırma işlemlerini kısıtla:** Kesme, kopyalama ve yapıştırma işlemlerinin ne zaman kısıtlanması gerektiğini belirtin. Aşağıdakilerden birini seçin:
  -   **Engellendi:** İlkeyle yönetilen uygulamalar arasında kesme, kopyalama ve yapıştırma işlemlerine izin verilmez.
  -   **İlke ile Yönetilen Uygulamalar:** Yalnızca ilkeyle yönetilen uygulamalar arasında kesme, kopyalama ve yapıştırma işlemlerine izin verilir.
  -   **Yapıştırma seçeneğiyle İlke ile Yönetilen Uygulamalar**: İlkeyle yönetilen uygulamalar arasında kesme veya kopyalama işlemine izin verilir. Herhangi bir uygulamadan kesilen veya kopyalanan verilerin bu uygulamaya yapıştırılmasına izin verilir.
  - **Herhangi Bir Uygulama**: Uygulamalar arasında kesme, kopyalama ve yapıştırma işlemleriyle ilgili bir kısıtlama olmaz.

  **Varsayılan değer = Yapıştırma seçeneğiyle ilke ile yönetilen uygulamalar**

- **Web içeriğinin Managed Browser'da görüntülenmesini kısıtla:** Bu ayar etkinleştirildiğinde, uygulamadaki tüm bağlantılar Managed Browser’da açılır.

  Intune’a kayıtlı olmayan cihazlarda, ilke tarafından yönetilen uygulamalardaki web bağlantıları, yalnızca mobil uygulama yönetimi ilkesini kullanan Managed Browser uygulamasında açılabilir.

  Cihazlarınızı yönetmek için Intune kullanıyorsanız bkz. [Microsoft Intune'la Managed Browser ilkelerini kullanarak İnternet erişimini yönetme](manage-internet-access-using-managed-browser-policies.md).

    **Varsayılan değer = Evet**

- **Uygulama verilerini şifrele:** Bir [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] mobil uygulama yönetimi ilkesiyle ilişkili uygulamalar için, veriler işletim sistemi tarafından sağlanan cihaz düzeyinde şifreleme kullanılarak şifrelenir. PIN istendiğinde, veriler mobil uygulama yönetim ilkesi ayarlarına göre şifrelenir. Apple belgelerinde belirtildiği gibi, [iOS 7 tarafından kullanılan modüller FIPS 140-2 sertifikalıdır](http://support.apple.com/en-us/HT202739).

  İlke ayarlarında PIN şifreleme değerlerini belirtebilirsiniz.  Bu değerler verilerin ne zaman şifrelendiğini belirler. Seçenekler şunlardır:
  - **Cihaz kilitliyken:** Cihaz kilitliyken, bu ilkeyle ilişkilendirilen tüm uygulama verileri şifrelenir.
  -   **Cihaz kilitliyken (açık dosyalar hariç):** Cihaz kilitliyken, uygulamada o anda açık olan dosyalardaki veriler dışında bu ilkeyle ilişkilendirilen tüm uygulama verileri şifrelenir.
  -   **Cihaz yeniden başlatıldıktan sonra:** Cihaz yeniden başlatıldığında, bu ilkeyle ilişkilendirilen tüm uygulama verileri cihaz kilidinin ilk açılışına kadar şifrelenir.
  -   **Cihaz ayarlarını kullan:** Uygulama verileri, cihazdaki varsayılan ayarlara göre şifrelenir.
  Bu ayarı etkinleştirdiğinizde son kullanıcının cihazına erişmesi için bir PIN ayarlaması ve bu PIN’i kullanması gerekir.  Cihaz erişimi için PIN ayarlanmadıysa uygulamalar başlatılmaz ve “Şirketiniz, bu uygulamaya erişmek için öncelikle bir cihaz PIN’i etkinleştirmenizi gerektiriyor” iletisiyle birlikte son kullanıcıdan bir PIN ayarlaması istenir.

  **Varsayılan değer - Şifreleme seçeneği belirlenmez.**
- **Kişi eşitleme devre dışı:** Kişi bilgilerinin cihazdaki yerel adres defteri uygulamasıyla eşitlenmesini önlemek için **Evet**’i seçin. **Hayır**’ı seçerseniz, uygulama kişi bilgilerini cihazdaki adres defteri uygulamasına kaydeder.

  Şirket verilerini kaldırmak amacıyla seçmeli temizleme işlemi yaptığınızda, doğrudan uygulamadan yerel adres defterine eşitlenen kişiler kaldırılır. Yerel adres defterinden başka bir dış kaynağa eşitlenen kişiler silinemez. Şu anda bu özellik yalnızca **Microsoft Outlook** uygulaması için geçerlidir.

  **Varsayılan değer = Evet**
  
- **Yazdırmayı devre dışı bırakma:** Şirket verilerinin MAM ilkesi ile ilişkilendirilmiş uygulamalardan yazdırılmasını engellemek için **Evet**’i seçin.

    **Varsayılan değer - Evet**

##  iOS Erişim ilkesi ayarları
**İlkeyle yönetilen uygulamalar** terimi, MAM ilkeleriyle yapılandırılan uygulamalar için kullanılır.
- **Erişim için PIN iste:** İlkeyle yönetilen uygulamalarda kullanmak üzere bir PIN istemek için **Evet**’i seçin. Kullanıcıdan, uygulamayı iş bağlamında ilk kez çalıştırdığında bunu ayarlaması istenir.

  **Varsayılan değer = Evet**
    -  **Basit PIN’e izin ver:** Kullanıcıların 1234 veya 1111 gibi basit PIN dizileri kullanmasına izin verilip verilmeyeceğini belirtin. **Varsayılan değer = Evet**.
    - **PIN Uzunluğu:** PIN’deki basamak sayısı alt sınırını belirtin. **Varsayılan değer = 4**
    - **PIN sıfırlanmadan önceki deneme sayısı:** Kaç PIN girişi denemesinden sonra kullanıcının PIN'i sıfırlaması gerekeceğini belirtin.
  **Bu ayarın varsayılan değeri yoktur**.

  - **PIN yerine parmak izi iste (iOS 8.0+):** Uygulama erişiminde numaralı bir PIN yerine parmak izi kimliği istemek için **Evet**’i seçin.
iOS cihazlarında kullanıcının, kendini tanıtmak için numaralandırılmış PIN yerine kendini parmak izi kullanmasına izin verebilirsiniz. Son kullanıcı, iş hesabını kullanarak bu uygulamaya erişmeyi denediğinde, PIN numarası girmek yerine parmak izi kimliğini vermesi istenir.

    **Varsayılan değer = Evet**
- **Erişim için kuruluş kimlik bilgilerini gerektir:** Uygulama erişiminde PIN yerine şirket kimlik bilgilerinin istenmesi için **Evet**’i seçin. **Evet olarak ayarlarsanız, bu ayar PIN veya Touch ID gereksinimlerini geçersiz kılar.** Kullanıcıdan şirket kimlik bilgilerini belirtmesi istenir.

  **Varsayılan değer = Hayır**
- **Yönetilen uygulamaların işletim sistemi kısıtlamaları kaldırılmış veya kök erişim izni verilmiş cihazlarda çalışmasını engelle:** Uygulamaların yazılım kilidi kırılmış veya kök erişim izni verilmiş cihazlarda çalıştırılmasını engellemek için **Evet**’i seçin. Kullanıcı kişisel görevler için uygulamaları kullanmaya devam edebilir, ancak iş için farklı bir cihaz kullanması gerekir.

  **Varsayılan değer = Evet**
- **(Dakika) sonra denetim gerekliliklerini yeniden denetle**|-   **Zaman aşımı:** Uygulamanın erişim gereksinimlerinin yeniden denetlenmesinden önce geçen süre (dakika olarak).
  -   **Çevrimdışı tanınan süre:** Cihaz çevrimdışıyken uygulama için erişim gereksinimleri yeniden denetlenmeden önce geçmesi gereken süreyi (dakika olarak) belirtin.

  **Varsayılan değer = 30 dakikalık zaman aşımı ve 720 dakikalık çevrimdışı tanınan süre**
  - **Uygulama verileri temizlenmeden önce geçen çevrimdışı süre (gün cinsinden):** Cihaz belirli bir süre için çevrimdışı kaldığında şirket verilerinin temizlenmesini seçebilirsiniz.  Cihazın kaç gün çevrimdışı kaldıktan sonra içindeki şirket verilerinin silineceğini belirtin. **0 değerinin girilmesi bu ayarı kapatır**.

  **Varsayılan değer = 90 gün**



<!--HONumber=Oct16_HO2-->


