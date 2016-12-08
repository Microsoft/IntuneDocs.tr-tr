---
title: "iOS MAM ilke ayarları | Microsoft Intune"
description: "Bu konu başlığı altında, iOS cihazları için mobil uygulama yönetimi ilkesi ayarları açıklanır."
keywords: 
author: karthikaraman
ms.author: karaman
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
ms.sourcegitcommit: eb9cc86646e08b85148a273cee3c0f2b7b6a6efb
ms.openlocfilehash: 913008568226621de4824c5bac287e8a65dc6533


---

#  <a name="ios-mobile-app-management-policy-settings"></a>iOS mobil uygulama yönetimi ilkesi ayarları
Bu konuda açıklanan ilke ayarları, Azure portalındaki **Ayarlar** dikey penceresinde mobil uygulama yönetimi (MAM) ilkesi için [yapılandırılabilir](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md).

İlke ayarlarının, verileri yeniden konumlandırma ayarları ve erişim ayarları olmak üzere iki kategorisi vardır. Bu konuda, *ilkeyle yönetilen uygulamalar* terimi, MAM ilkeleriyle yapılandırılan uygulamaları ifade eder.

##  <a name="data-relocation-settings"></a>Verileri yeniden konumlandırma ayarları

- **iTunes ve iCloud yedeklemelerini engelle**: İlkeyle yönetilen uygulamalardan şirket verilerini yedeklemeyi devre dışı bırakmak için **Evet**’i veya bu yedeklemeye izin vermek için **Hayır**’ı seçin.

  Varsayılan değer = **Evet**.

- **Uygulamanın diğer uygulamalara veri aktarmasına izin ver**: İlkeyle yönetilen uygulamalardan veri alabilecek uygulamaları göstermek için seçeneklerden birini belirtin:
  - **İlke ile yönetilen uygulamalar**: Yalnızca MAM ilkesi olan uygulamalara aktarıma izin verilir.
  - **Tüm uygulamalar**: Herhangi bir uygulamaya aktarıma izin verilir.
  - **Hiçbiri**: İlkeyle yönetilen diğer uygulamalar da dahil olmak üzere hiçbir uygulamaya veri aktarmaya izin verilmez.

  Ayrıca, bu seçeneği **İlke ile yönetilen uygulamalar** veya **Hiçbiri** olarak ayarlarsanız uygulamaların içindeki verileri aramak için Spotlight Arama özelliğine imkan tanıyan iOS 9 özelliği engellenir.

  >[!NOTE]
  >Bu ayar, mobil cihazlardaki Birlikte Aç özelliğinin kullanımını denetlemez. Birlikte Aç’ı yönetmek için bkz. [Microsoft Intune ile iOS uygulamaları arasında veri aktarımını yönetme](manage-data-transfer-between-ios-apps-with-microsoft-intune.md).

  Varsayılan değer = **İlke ile yönetilen uygulamalar**.

- **Uygulamanın diğer uygulamalardan veri almasına izin verme:** İlkeyle yönetilen uygulamalara veri aktarmasına izin verilen uygulamaları belirtin:
  -  **İlke ile yönetilen uygulamalar**: Yalnızca diğer ilkeyle yönetilen uygulamalardan veri aktarımlarına izin verilir.
  -  **Tüm uygulamalar**: Herhangi bir uygulamadan veri aktarımına izin verilir.
  -  **Hiçbiri**: Hiçbir uygulamadan veri aktarımına izin verilmez.

  Varsayılan değer = **Tüm uygulamalar**.

- **Farklı Kaydet seçeneğini engelleme:** Bu ilkeyi kullanan uygulamalarda Farklı Kaydet seçeneğinin kullanımını devre dışı bırakmak için **Evet**’i seçin. Farklı Kaydet’in kullanılmasına izin vermek istiyorsanız **Hayır** ’ı seçin.

  Varsayılan değer = **Evet**.

- **Diğer uygulamalarla kesme, kopyalama ve yapıştırma işlemlerini kısıtlama:** Kesme, kopyalama ve yapıştırma işlemlerinin ne zaman kısıtlanması gerektiğini belirtin. Aşağıdakilerden birini seçin:
  -   **Engellendi:** İlkeyle yönetilen uygulamalar arasında kesme, kopyalama ve yapıştırma işlemlerine izin verilmez.
  -   **İlke ile yönetilen uygulamalar**: Yalnızca ilkeyle yönetilen uygulamalar arasında kesme, kopyalama ve yapıştırma işlemlerine izin verilir.
  -   **Yapıştırma seçeneğiyle ilke ile yönetilen uygulamalar**: İlkeyle yönetilen uygulamalar arasında kesme veya kopyalama işlemine izin verilir. Herhangi bir uygulamadan kesilen veya kopyalanan verilerin bu uygulamaya yapıştırılmasına izin verilir.
  - **Herhangi bir uygulama**: Uygulamalar arasında kesme, kopyalama ve yapıştırma işlemleriyle ilgili bir kısıtlama yoktur.

  Varsayılan değer = **Yapıştırma seçeneğiyle ilke ile yönetilen uygulamalar**.

- **Web içeriğinin Managed Browser’da görüntülenmesini kısıtlama:** Bu ayar etkinleştirildiğinde, uygulamadaki tüm bağlantılar Managed Browser uygulamasında açılır.

  Intune’a kayıtlı olmayan cihazlarda, ilke tarafından yönetilen uygulamalardaki web bağlantıları yalnızca Managed Browser uygulamasında açılabilir.

  Cihazlarınızı yönetmek için Intune kullanıyorsanız bkz. [Microsoft Intune'la Managed Browser ilkelerini kullanarak İnternet erişimini yönetme](manage-internet-access-using-managed-browser-policies.md).

  Varsayılan değer = **Evet**.

- **Uygulama verilerini şifrele**: Bir Intune MAM ilkesiyle ilişkili uygulamalar için veriler işletim sistemi tarafından sağlanan cihaz düzeyinde şifreleme ile şifrelenir. PIN istendiğinde, veriler MAM ilkesi ayarlarına göre şifrelenir. Apple belgelerinde belirtildiği gibi, [iOS 7 tarafından kullanılan modüller FIPS 140-2 sertifikalıdır](http://support.apple.com/en-us/HT202739).

  İlke ayarlarında PIN şifreleme değerlerini belirtebilirsiniz. Bu değerler verilerin ne zaman şifrelendiğini belirler. Seçenekler şunlardır:
  -   **Cihaz kilitliyken**: Cihaz kilitliyken, bu ilkeyle ilişkilendirilen tüm uygulama verileri şifrelenir.
  -   **Cihaz kilitliyken (açık dosyalar hariç)**: Cihaz kilitliyken, uygulamada o anda açık olan dosyalardaki veriler dışında bu ilkeyle ilişkilendirilen tüm uygulama verileri şifrelenir.
  -   **Cihaz yeniden başlatıldıktan sonra**: Cihaz yeniden başlatıldığında, bu ilkeyle ilişkilendirilen tüm uygulama verileri cihaz kilidinin ilk açılışına kadar şifrelenir.
  -   **Cihaz ayarlarını kullan**: Uygulama verileri, cihazdaki varsayılan ayarlara göre şifrelenir.
  Bu ayarı etkinleştirdiğinizde kullanıcının cihazına erişmesi için bir PIN ayarlaması ve bu PIN’i kullanması gerekir.  Cihaz erişimi için PIN ayarlanmadıysa uygulamalar açılmaz ve “Şirketiniz, bu uygulamaya erişmek için öncelikle bir cihaz PIN’i etkinleştirmenizi gerektiriyor” iletisiyle birlikte kullanıcıdan bir PIN ayarlaması istenir.

  Varsayılan değer = Şifreleme seçeneği belirlenmez.
- **Kişi eşitlemeyi devre dışı bırakma:** Kişi bilgilerinin cihazdaki yerel adres defteri uygulamasıyla eşitlenmesini önlemek için **Evet**’i seçin. **Hayır**’ı seçerseniz, uygulama kişi bilgilerini cihazdaki adres defteri uygulamasına kaydeder.

  Şirket verilerini kaldırmak amacıyla seçmeli temizleme işlemi yaptığınızda, doğrudan uygulamadan yerel adres defterine eşitlenen kişiler kaldırılır. Yerel adres defterinden başka bir dış kaynağa eşitlenen kişiler silinemez. Şu anda bu özellik yalnızca Microsoft Outlook uygulaması için geçerlidir.

  Varsayılan değer = **Evet**.

- **Yazdırmayı devre dışı bırakma:** Şirket verilerinin MAM ilkesi ile ilişkilendirilmiş uygulamalardan yazdırılmasını engellemek için **Evet**’i seçin.

    Varsayılan değer = **Evet**.

##  <a name="access-settings"></a>Erişim ayarları

- **Erişim için PIN isteme:** İlkeyle yönetilen uygulamalarda kullanmak üzere bir PIN istemek için **Evet**’i seçin. Kullanıcıdan, uygulamayı iş bağlamında ilk kez çalıştırdığında bunu ayarlaması istenir.

  Varsayılan değer = **Evet**.
    -  **Basit PIN’e izin verme:** Kullanıcıların 1234 veya 1111 gibi basit PIN dizileri kullanmasına izin verilip verilmeyeceğini belirtin. Varsayılan değer = **Evet**.
    - **PIN Uzunluğu:** PIN’deki basamak sayısı alt sınırını belirtin. Varsayılan değer = **4**.
    - **PIN sıfırlanmadan önceki deneme sayısı:** Kullanıcının kaç PIN girişi denemesinden sonra PIN'i sıfırlaması gerekeceğini belirtin. Bu ayarın varsayılan değeri yoktur.

- **PIN yerine parmak izi iste (iOS 8.0+)**: Uygulama erişiminde bir PIN yerine parmak izi kimliği istemek için **Evet**’i seçin.
iOS cihazlarında kullanıcının, kendini tanıtmak için bir PIN yerine kendini parmak izi kullanmasına izin verebilirsiniz. Kullanıcı, iş hesabını kullanarak bu uygulamayı açmayı denediğinde, PIN girmek yerine parmak izi kimliğini vermesi istenir.

  Varsayılan değer = **Evet**.
- **Erişim için kuruluş kimlik bilgileri isteme:** Uygulama erişiminde PIN yerine şirket kimlik bilgilerinin istenmesi için **Evet**’i seçin. **Evet** olarak ayarlarsanız, bu ayar PIN veya Touch ID gereksinimlerini geçersiz kılar. Kullanıcıdan şirket kimlik bilgilerini belirtmesi istenir.

  Varsayılan değer = **Hayır**.
- **Yönetilen uygulamaların jailbreak uygulanmış veya kök erişim izni verilmiş cihazlarda çalışmasını engelleme:** Uygulamaların jailbreak uygulanmış veya kök erişim izni verilmiş cihazlarda çalıştırılmasını engellemek için **Evet**’i seçin. Kullanıcı kişisel görevler için uygulamaları kullanmaya devam edebilir, ancak iş için farklı bir cihaz kullanması gerekir.

  Varsayılan değer = **Evet**.
- **Erişim gereksinimlerini şu süreden sonra yeniden denetle (dakika)**
  -   **Zaman aşımı:** Uygulama için erişim gereksinimleri yeniden denetlenmeden önce geçmesi gereken süreyi (dakika cinsinden) belirtin.
  -   **Çevrimdışı kullanım süresi:** Cihaz çevrimdışıyken uygulama için erişim gereksinimleri yeniden denetlenmeden önce geçmesi gereken süreyi (dakika olarak) belirtin.

  Varsayılan değerler = **30** dakikalık zaman aşımı ve **720** dakikalık çevrimdışı kullanım süresi.
- **Uygulama verileri temizlenmeden önce geçen çevrimdışı süre (gün cinsinden):** Cihaz belirli bir süre için çevrimdışı kaldığında şirket verilerinin temizlenmesini seçebilirsiniz. Cihazın kaç gün çevrimdışı kaldıktan sonra içindeki şirket verilerinin silineceğini belirtin.

  >[!TIP]
  >**0** değeri girilirse bu ayar devre dışı bırakılır.

  Varsayılan değer = **90** gün.



<!--HONumber=Oct16_HO5-->


