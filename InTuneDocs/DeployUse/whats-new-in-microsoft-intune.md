---
# required metadata

title: Yenilikler | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune'daki yenilikler

## Nisan 2016
Bu özelliklerin tümü, karma müşteriler için de desteklenmektedir (Intune ile tümleşik Configuration Manager).
### Uygulama yönetimi
- **MAM kullanıcı uyumu.**
Artık Azure Active Directory (AAD) kiracınızdaki herhangi bir kullanıcı için, uygulama yönetimi ilkelerinizin [durumunu](monitor-mobile-app-management-policies-with-Microsoft-Intune.md) görüntüleyebilirsiniz. Buna aşağıdakiler dahildir:
   - Cihazlar
   - Cihazdaki uygulamalar

   Durum değerleri:

   **İade**: İlkenin kullanıcıya dağıtıldığını ve uygulamanın iş bağlamında kullanıldığını ve ilkeyi başarıyla aldığını gösterir.

    **İade değil**: İlkenin kullanıcıya dağıtıldığını, ancak uygulamanın o zamandan bu yana iş bağlamında kullanılmadığını gösterir.


- **Outlook kişilerinin eşitlenmesini önlemek için MAM denetimleri (Android).**
Cihaz kaydı olmadan [mobil uygulama yönetimi](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) için yeni bir ayar vardır. Bu ayar, bir uygulamanın Android cihazlarda kişileri yerel adres defterine eşitlemesini engellemenizi sağlar. Bu ayar etkinleştirildiğinde, hedeflenen uygulamalar artık kişileri yerel adres defterine kaydedemeyecektir. Bu ayar devre dışı bırakıldığında, hedeflenen uygulamalar kişileri yerel adres defterine kaydedebilecektir. [Bir cihazı veya uygulamayı uzaktan temizlediğinizde](wipe-managed-company-app-data-with-Microsoft-Intune.md), yerel adres defterine zaten kaydedilmiş kişiler kaldırılacaktır. Bu yeni ayar başlangıçta Android cihazlarda Outlook uygulaması tarafından desteklenmektedir.

### Cihaz yönetimi
- **Şirkete ait cihazlar için telefon numarası kimliği.** “Şirket” olarak sınıflandırılmış telefonlar artık, örneğin bir mobil cihaz envanter raporu çalıştırdığınızda, tam telefon numaralarıyla tanımlanır. BYOD telefon numaraları, **** ile gizlenmeye devam edilecektir, yalnızca 4 hane görüntülenmektedir.


### Şirket portalı güncelleştirmeleri
Android Şirket portalı uygulaması Cihazlarını Intune’a kaydetmeyen ve doğru sertifika yüklememiş kullanıcılar, Android Şirket Portalı uygulamasına oturum açamayacak ve "Cihazınızda gerekli bir sertifika eksik olduğundan oturum açılamıyor." iletisini görür. İleti, kullanıcıların sertifikayı yüklemek için yönergeleri görmek üzere dokunabileceği bir "Bu durum nasıl çözümlenir" bağlantısı içerir.

Son kullanıcıların sorunu çözümlemek için izlediği adımları görmek için, bkz. [Cihazınızda gerekli bir sertifika eksik](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_cert_missing) iOS Şirket Portalı uygulaması

Listelenen uygulamalar, listelenen cihazlar ve BT iletişim bilgilerini içeren ana ekran içeriğini yenilemek üzere, çekerek yenileme eylemi için destek eklenmiştir. Çekerek yenileme eylemi, uyum veya ilk bilgilerini denetlemez, bu, geçerli cihazınız için döşeme seçilerek ve **Eşitle** düğmesine dokunularak yapılabilir. Windows 10 Mobile ve Windows Phone 8.1 Şirket Portalı uygulaması

Son kullanıcılar iş kolu uygulamaları yüklediğinde artık iyileştirilmiş bir uygulama yükleme deneyimi görecektir.

* Uygulama yüklemesi uzun sürüyorsa, kullanıcılar, eşitleme işleminin devam etmesini zorlamak için cihazlarını el ile eşitleyebilir. Son kullanıcı yönergelerini gözden geçirmek için, bkz. [Uygulama yüklemelerini hızlandırmak için cihazınızı el ile eşitleme](https://technet.microsoft.com/library/mt427782.aspx#BKMK_win10m_wp81_sync_manually) Şirket Portalı web sitesi
* Windows 10 Mobile ve Windows Phone 8.1 kullanıcıları iş kolu uygulamaları yüklediğinde, artık yüklemelerinin durumu hakkında daha fazla ayrıntı sağlamayan aşağıdaki yeni durumları görecektir:

**Cihazın eşitlenmesi bekleniyor** – kullanıcı "Yükle" öğesine dokunmuştur ve cihaz şimdi Intune altyapısıyla eşitlemeye çalışıyordur. Yüklemenin tamamlanabilmesi için eşitleme gereklidir.

### "Cihazın eşitlenmesi bekleniyor" iletisi aynı zamanda bir bağlantıdır, kullanıcılar, eşitleme işlemi çok uzun sürüyorsa veya duruyorsa buna dokunarak cihazlarını Intune ile nasıl el ile eşitleyeceklerine dair [yönergeleri](https://technet.microsoft.com/library/mt590895.aspx#BKMK_iwp_sync_manually) görebilir.

****İndiriliyor** – kullanıcının indirme isteği işlenmektedir ve cihaz uygulamayı indiriyor ve yüklüyordur.** Bu durumlar eklenmeden önce, bir uygulamanın yüklenmesi uzun sürdüğünde, yalnızca, ekranda saatlerce kalabilecek “Yükleniyor” durumu gördükleri için kullanıcıların kafası karışıyordu. Yeni durumların eklenmesi, destek çağırmak yerine, kullanıcıların artık “Cihazın eşitlenmesi bekleniyor" bağlantısına dokunabileceği ve eşitleme işleminin devam etmesini zorlamak için yönergeleri izleyebileceği anlamına geliyor. Yakında  Cihaz Kayıt Yöneticileri hesaplarına değişiklikler. Performansı ve ölçeği artırmak için, Intune artık Şirket Portalı uygulamasının Cihazlarım bölmesinde Cihaz Kayıt Yöneticileri (DEM) cihazlarını göstermeyecektir.  Yalnızca uygulamayı çalıştıran yerel cihaz, yalnızca Şirket Portalı uygulaması aracılığıyla kaydedilmişse görüntülenir.

DEM kullanıcısı, yerel cihazda eylemler gerçekleştirebilir, ancak diğer kaydedilen cihazların uzaktan yönetimi yalnızca Intune yönetici konsolundan gerçekleştirilebilir.


## Ayrıca, Intune, Apple Cihaz Kayıt Programı veya Apple Configurator aracıyla DEM hesapları kullanılmasını kaldıracaktır.
Her iki kayıt yöntemi, paylaşılan iOS cihazları için kullanıcısız kaydı zaten desteklemektedir.



### Yalnızca, paylaşılan cihazlar için kullanıcısız kayıt kullanılamadığında DEM hesapları kullanın.
* [[Bulut Platformu yol haritası](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune) ile yaklaşan Intune geliştirmelerinden haberdar olun](http://go.microsoft.com/fwlink/?LinkID=273882)


<!--HONumber=May16_HO2-->


