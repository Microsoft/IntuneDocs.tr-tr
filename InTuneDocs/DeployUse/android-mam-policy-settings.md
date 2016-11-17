---
title: "Android MAM ilke ayarları | Microsoft Intune"
description: "Bu konu başlığı altında, Android cihazları için mobil uygulama yönetimi ilkesi ayarları açıklanır."
keywords: 
author: karthikaraman
ms.author: karaman
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
ms.sourcegitcommit: 552473cb704ead5f7cc30a2311e2f722265bfcea
ms.openlocfilehash: c7ecf73c28a8332bd3fe1465a2f64f7f09a7a690


---

# <a name="android-mobile-app-management-policy-settings-in-microsoft-intune"></a>Microsoft Intune’da Android mobil uygulaması yönetim ilkesi ayarları
Bu konuda açıklanan ilke ayarları, Azure portalındaki **Ayarlar** dikey penceresinde mobil uygulama yönetimi (MAM) ilkesi için [yapılandırılabilir](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md).
İlke ayarlarının, verileri yeniden konumlandırma ayarları ve erişim ayarları olmak üzere iki kategorisi vardır. Bu konuda, *ilkeyle yönetilen uygulamalar* terimi, MAM ilkeleriyle yapılandırılan uygulamaları ifade eder.

##  <a name="data-relocation-settings"></a>Verileri yeniden konumlandırma ayarları

- **Android yedeklemelerini engelleme:** İlkeyle yönetilen uygulamalardan şirket verilerini yedeklemeyi devre dışı bırakmak için **Evet**’i veya bu yedeklemeye izin vermek için **Hayır**’ı seçin.

  Varsayılan değer = **Evet**.
- **Uygulamanın diğer uygulamalara veri aktarmasına izin verme:** İlkeyle yönetilen uygulamalardan şirket verilerini alabilecek uygulamaları göstermek için seçeneklerden birini belirtin:
  -   **İlke ile yönetilen uygulamalar**: Yalnızca MAM ilkesi olan uygulamalara aktarıma izin verilir.
  -   **Tüm uygulamalar**: Herhangi bir uygulamaya aktarıma izin verilir.
  -   **Hiçbiri**: Hiçbir uygulamaya veri aktarımına izin verilmez.

  Varsayılan değer = **İlke ile yönetilen uygulamalar**.
- **Uygulamanın diğer uygulamalardan veri almasına izin verme:** İlkeyle yönetilen uygulamalara veri aktarmasına izin verilen uygulamaları belirtin:
  -   **İlke ile yönetilen uygulamalar**: Yalnızca diğer ilkeyle yönetilen uygulamalardan veri aktarımlarına izin verilir.
  -   **Tüm uygulamalar**: Herhangi bir uygulamadan veri aktarımına izin verilir.
  -   **Hiçbiri**: Hiçbir uygulamadan veri aktarımına izin verilmez.

  Varsayılan değer = **Tüm uygulamalar**.

-   **Farklı Kaydet seçeneğini engelleme:** Bu ilkeyi kullanan uygulamalarda Farklı Kaydet seçeneğinin kullanımını devre dışı bırakmak için **Evet**’i seçin. Farklı Kaydet’in kullanılmasına izin vermek istiyorsanız **Hayır** ’ı seçin.

  Varsayılan değer = **Evet**.
- **Diğer uygulamalarla kesme, kopyalama ve yapıştırma işlemlerini kısıtlama:** Kesme, kopyalama ve yapıştırma işlemlerinin ne zaman kısıtlanması gerektiğini belirtin. Aşağıdakilerden birini seçin:
  -   **Engellendi:** İlkeyle yönetilen uygulamalar arasında kesme, kopyalama ve yapıştırma işlemlerine izin verilmez.
  -   **İlke ile Yönetilen Uygulamalar:** Yalnızca ilkeyle yönetilen uygulamalar arasında kesme, kopyalama ve yapıştırma işlemlerine izin verilir.
  -   **Yapıştırma seçeneğiyle İlke ile Yönetilen Uygulamalar**: İlkeyle yönetilen uygulamalar arasında kesme veya kopyalama işlemine izin verilir. Herhangi bir uygulamadan kesilen veya kopyalanan verilerin bu uygulamaya yapıştırılmasına izin verilir.
  -   **Herhangi Bir Uygulama**: Uygulamalar arasında kesme, kopyalama ve yapıştırma işlemleriyle ilgili bir kısıtlama yoktur.

  Varsayılan değer = **Yapıştırma seçeneğiyle ilke ile yönetilen uygulamalar**.
-   **Web içeriğinin Managed Browser’da görüntülenmesini kısıtlama:** Bu ayar etkinleştirildiğinde, uygulamadaki tüm bağlantılar Managed Browser uygulamasında açılır.

  Intune’a kayıtlı olmayan cihazlarda, ilke tarafından yönetilen uygulamalardaki web bağlantıları, yalnızca MAM ilkesini kullanan Managed Browser uygulamasında açılır.

  Cihazlarınızı yönetmek için Intune kullanıyorsanız bkz. [Microsoft Intune'la Managed Browser ilkelerini kullanarak İnternet erişimini yönetme](manage-internet-access-using-managed-browser-policies.md).

  Varsayılan değer = **Evet**.
- **Uygulama verilerini şifreleme:** Şifrelemeyi etkinleştirmek için **Evet**’i seçin. Bu ayar etkinleştirildiğinde Microsoft, MAM ilkesiyle ilişkili uygulamalar için şifreleme sağlar. Veriler, dosya GÇ görevleri sırasında eş zamanlı olarak şifrelenir. Cihaz depolamasındaki içerik her zaman şifrelenir.
  >[!NOTE]
  >Şifreleme yöntemi FIPS 140-2 sertifikalı değildir.

  Varsayılan değer = **Evet**.

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
 - **PIN yerine parmak izi iste (Android 6.0+):** Uygulama erişiminde numaralı bir PIN yerine parmak izi kimliği istemek için **Evet**’i seçin.
 Android cihazlarda kullanıcının, kendini tanıtmak için numaralandırılmış PIN yerine parmak izi kullanmasına izin verebilirsiniz. Son kullanıcı, iş hesabını kullanarak bu uygulamaya erişmeyi denediğinde, PIN numarası girmek yerine parmak izi kimliğini vermesi istenir.
 - **Erişim için kuruluş kimlik bilgileri iste**: Uygulama erişiminde PIN veya parmak izi yerine şirket kimlik bilgilerinin istenmesi için **Evet**’i seçin. **Evet** olarak ayarlarsanız, bu ayar PIN veya Touch ID gereksinimlerini geçersiz kılar. Kullanıcıdan şirket kimlik bilgilerini belirtmesi istenir.

  Varsayılan değer = **Hayır**.
- **Yönetilen uygulamaların jailbreak uygulanmış veya kök erişim izni verilmiş cihazlarda çalışmasını engelleme:** Uygulamaların jailbreak uygulanmış veya kök erişim izni verilmiş cihazlarda çalıştırılmasını engellemek için **Evet**’i seçin. Kullanıcı kişisel görevler için uygulamaları kullanmaya devam edebilir, ancak iş için farklı bir cihaz kullanması gerekir.

  Varsayılan değer = **Evet**.
- **Erişim gereksinimlerini şu süreden sonra yeniden denetle (dakika)**
  -   **Zaman aşımı:** Uygulama için erişim gereksinimleri yeniden denetlenmeden önce geçmesi gereken süreyi (dakika cinsinden) belirtin.
  -   **Çevrimdışı kullanım süresi:** Cihaz çevrimdışıyken uygulama için erişim gereksinimleri yeniden denetlenmeden önce geçmesi gereken süreyi (dakika olarak) belirtin.

  Varsayılan değerler = **30** dakikalık zaman aşımı ve **720** dakikalık çevrimdışı kullanım süresi.

-   **Uygulama verileri temizlenmeden önce geçen çevrimdışı süre (gün cinsinden):** Cihaz belirli bir süre için çevrimdışı kaldığında şirket verilerinin temizlenmesini seçebilirsiniz.  Cihazın kaç gün çevrimdışı kaldıktan sonra içindeki şirket verilerinin silineceğini belirtin.

    >[!TIP]
    >**0** değeri girilirse bu ayar devre dışı bırakılır.

  Varsayılan değer = **90** gün.
- **Ekran görüntüsü yakalamayı ve Android Assistant uygulamasını engelleme (Android 6 Marshmallow veya üzeri):** Bu uygulamayı kullanırken cihazın ekran görüntüsü yakalama ve **Android Assistant** özelliklerini engellemek için **Evet**’i seçin.



<!--HONumber=Oct16_HO4-->


