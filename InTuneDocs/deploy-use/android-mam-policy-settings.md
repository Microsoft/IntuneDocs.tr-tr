---
title: "Android MAM ilke ayarları | Microsoft Intune"
description: "Bu konu başlığı altında, Android cihazları için mobil uygulama yönetimi ilkesi ayarları açıklanır."
keywords: 
author: NathBarn
ms.author: nathbarn
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
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: d0a1a2b3f4e5dbac8b333db3a5cc4bb32c0d61ef


---

# <a name="android-mobile-app-management-policy-settings-in-microsoft-intune"></a>Microsoft Intune’da Android mobil uygulaması yönetim ilkesi ayarları
Bu konuda açıklanan ilke ayarları, Azure portalındaki **Ayarlar** dikey penceresinde mobil uygulama yönetimi (MAM) ilkesi için [yapılandırılabilir](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md).
İlke ayarlarının, verileri yeniden konumlandırma ayarları ve erişim ayarları olmak üzere iki kategorisi vardır. Bu konuda, *ilkeyle yönetilen uygulamalar* terimi, MAM ilkeleriyle yapılandırılan uygulamaları ifade eder.

##  <a name="data-relocation-settings"></a>Verileri yeniden konumlandırma ayarları

- **Android yedeklemelerini engelle:** İlkeyle yönetilen uygulamalardan şirket verilerini yedeklemeyi devre dışı bırakmak için **Evet**’i veya bu yedeklemeyi etkinleştirmek için **Hayır**’ı seçin.

  Varsayılan değer = **Evet**
- **Uygulamanın diğer uygulamalara veri aktarmasına izin verme:** İlkeyle yönetilen uygulamalardan şirket verilerini alabilecek uygulama türlerini göstermek için seçeneklerden birini belirtin:
  -   **İlke ile yönetilen uygulamalar**: Yalnızca MAM ilkesi olan uygulamalara aktarım etkinleştirilir.
  -   **Tüm uygulamalar**: Herhangi bir uygulamaya aktarım etkinleştirilir.
  -   **Hiçbiri**: Hiçbir uygulamaya veri aktarımına izin verilmez.

 Varsayılan değer = **İlke ile yönetilen uygulamalar**.
- **Uygulamanın diğer uygulamalardan veri almasına izin verme:** İlkeyle yönetilen uygulamalara veri aktarmasına izin verilen uygulamaları belirtin:
  -   **İlke ile yönetilen uygulamalar**: Yalnızca diğer ilkeyle yönetilen uygulamalardan veri aktarımları etkinleştirilir.
  -   **Tüm uygulamalar**: Herhangi bir uygulamadan veri aktarımı etkinleştirilir.
  -   **Hiçbiri**: Hiçbir uygulamadan veri aktarımına izin verilmez.

  Varsayılan değer = **Tüm uygulamalar**

-   **Farklı Kaydet seçeneğini engelleme:** Bu ilkeyi kullanan uygulamalarda Farklı Kaydet seçeneğinin kullanımını devre dışı bırakmak için **Evet**’i seçin. Farklı Kaydet’in kullanılmasını etkinleştirmek istiyorsanız **Hayır**'ı seçin.

  Varsayılan değer = **Evet**
- **Diğer uygulamalarla kesme, kopyalama ve yapıştırma işlemlerini kısıtlama:** Kesme, kopyalama ve yapıştırma işlemlerinin ne zaman kısıtlanması gerektiğini belirtin. Aşağıdakilerden birini seçin:
  -   **Engellendi:** İlkeyle yönetilen uygulamalar arasında kesme, kopyalama ve yapıştırma işlemlerine izin verilmez.
  -   **İlke ile Yönetilen uygulamalar:** Yalnızca ilkeyle yönetilen uygulamalar arasında kesme, kopyalama ve yapıştırma işlemleri etkinleştirilir.
  -   **Yapıştırma seçeneğiyle İlke ile Yönetilen uygulamalar**: İlkeyle yönetilen uygulamalar arasında kesme veya kopyalama işlemi etkinleştirilir. Herhangi bir uygulamadan kesilen veya kopyalanan verilerin bu uygulamaya yapıştırılması etkinleştirilir.
  -   **Herhangi bir uygulama**: Uygulamalar arasında kesme, kopyalama ve yapıştırma işlemleriyle ilgili bir kısıtlama yoktur.

  Varsayılan değer = **Yapıştırma seçeneğiyle ilke ile yönetilen uygulamalar**
-   **Web içeriğinin Managed Browser’da görüntülenmesini kısıtlama:** Uygulamadaki tüm bağlantıların Managed Browser uygulamasında açılmasını belirtmek için **Evet**'i seçin.

  Intune’a kayıtlı olmayan cihazlarda, ilke tarafından yönetilen uygulamalardaki bağlantılar, yalnızca MAM ilkesini kullanan Managed Browser uygulamasında açılır.

  Cihazlarınızı yönetmek için Intune kullanıyorsanız bkz. [Microsoft Intune'la Managed Browser ilkelerini kullanarak İnternet erişimini yönetme](manage-internet-access-using-managed-browser-policies.md).

  Varsayılan değer = **Evet**
- **Uygulama verilerini şifreleme:** Şifrelemeyi etkinleştirmek için **Evet**’i seçin. Bu ayar etkinleştirildiğinde Microsoft, MAM ilkesiyle ilişkili uygulamalar için şifreleme sağlar. Veriler, dosya GÇ görevleri sırasında eş zamanlı olarak şifrelenir. Cihaz depolamasındaki içerik her zaman şifrelenir.
  >[!NOTE]
  >Şifreleme yöntemi FIPS 140-2 sertifikalı değildir.

  Varsayılan değer = **Evet**

- **Kişi eşitlemeyi devre dışı bırakma:** Kişi bilgilerinin cihazdaki yerel adres defteri uygulamasıyla eşitlenmesini önlemek için **Evet**’i seçin. **Hayır**'ı seçerseniz, uygulama kişi bilgilerini cihazdaki adres defteri uygulamasına kaydeder.

  Şirket verilerini kaldırmak amacıyla seçmeli silme işlemi yaptığınızda, doğrudan uygulamadan yerel adres defterine eşitlenen kişiler kaldırılır. Yerel adres defteriyle başka bir kaynak arasında eşitlenen kişiler silinemez. Şu anda bu özellik yalnızca Microsoft Outlook uygulaması için geçerlidir.

  Varsayılan değer = **Evet**
- **Yazdırmayı devre dışı bırakma:** Şirket verilerinin MAM ilkesi ile ilişkilendirilmiş uygulamalardan yazdırılmasını engellemek için **Evet**’i seçin.

  Varsayılan değer = **Evet**

##  <a name="access-settings"></a>Erişim ayarları

- **Erişim için PIN isteme:** İlkeyle yönetilen uygulamalarda kullanmak üzere bir PIN istemek için **Evet**’i seçin. Kullanıcıdan, uygulamayı iş bağlamında ilk kez çalıştırdığında bunu ayarlaması istenir.

 Varsayılan değer = **Evet**

 -  **Basit PIN’e izin verme:** Kullanıcıların 1234 veya 1111 gibi basit PIN dizileri kullanmasına izin verilip verilmeyeceğini belirtin. Varsayılan değer = **Evet**.
 - **PIN Uzunluğu:** PIN’deki basamak sayısı alt sınırını belirtin. Varsayılan değer = **4**.
 - **PIN sıfırlanmadan önceki deneme sayısı:** Kullanıcının kaç PIN girişi denemesinden sonra PIN'i sıfırlaması gerekeceğini belirtin. Bu ayarın varsayılan değeri yoktur.
 - **PIN yerine parmak izi iste (Android 6.0+):** Uygulama erişiminde numaralı bir PIN yerine parmak izi kimliği istemek için **Evet**’i seçin.
 Android cihazlarda kullanıcının, kendini tanıtmak için numaralandırılmış PIN yerine parmak izi kullanmasını etkinleştirebilirsiniz. Kullanıcı, iş hesabını kullanarak bu uygulamayı açmayı denediğinde, PIN girmek yerine parmak izi kimliğini vermesi istenir.
 - **Erişim için kuruluş kimlik bilgileri iste**: Uygulama erişiminde PIN veya parmak izi yerine şirket kimlik bilgilerinin istenmesi için **Evet**’i seçin. **Evet** olarak ayarlarsanız, bu ayar PIN veya Touch ID gereksinimlerini geçersiz kılar. Kullanıcıdan şirket kimlik bilgilerini belirtmesi istenir. Varsayılan değer = **Hayır**.


- **Yönetilen uygulamaların jailbreak uygulanmış veya kök erişim izni verilmiş cihazlarda çalışmasını engelleme:** Uygulamaların jailbreak uygulanmış veya kök erişim izni verilmiş cihazlarda çalıştırılmasını engellemek için **Evet**’i seçin. Kullanıcı kişisel görevler için uygulamaları kullanmaya devam edebilir, ancak iş için farklı bir cihaz kullanması gerekir.

  Varsayılan değer = **Evet**
- **Erişim gereksinimlerini şu süreden sonra yeniden denetle (dakika)**
  -   **Zaman aşımı:** Uygulama için erişim gereksinimleri yeniden denetlenmeden önce geçmesi gereken süreyi (dakika cinsinden) belirtin.
  -   **Çevrimdışı kullanım süresi:** Cihaz çevrimdışıyken uygulama için erişim gereksinimleri yeniden denetlenmeden önce geçmesi gereken süreyi (dakika olarak) belirtin.

  Varsayılan değerler = **30** dakikalık zaman aşımı ve **720** dakikalık çevrimdışı kullanım süresi

-   **Uygulama verileri temizlenmeden önce geçen çevrimdışı süre (gün cinsinden):** Cihaz belirli bir süre için çevrimdışı kaldığında şirket verilerinin temizlenmesini seçebilirsiniz.  Cihazın kaç gün çevrimdışı kaldıktan sonra içindeki şirket verilerinin silineceğini belirtin.

    >[!TIP]
    >**0** değeri girilirse bu ayar devre dışı bırakılır.

  Varsayılan değer = **90** gün
- **Ekran görüntüsü yakalamayı ve Android Assistant uygulamasını engelleme (Android 6 Marshmallow veya üzeri):** Bu uygulamayı kullanırken cihazın ekran görüntüsü yakalama ve **Android Assistant** özelliklerini engellemek için **Evet**’i seçin.



<!--HONumber=Dec16_HO2-->


