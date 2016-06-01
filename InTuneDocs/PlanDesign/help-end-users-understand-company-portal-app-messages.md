---
# required metadata

title: Son kullanıcıların Şirket Portalı uygulama iletilerini anlamasına yardımcı olma | Microsoft Intune
description:
keywords:
author: staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 3df993aa-48c5-4799-b68d-c85fe4f7b02c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Son kullanıcıların Şirket Portalı uygulama iletilerini anlamasına yardımcı olma

Aşağıdaki bilgiler yalnızca Android 6.0 ve üstü cihazlar için geçerlidir. Cihaz kaydı sırasında son kullanıcılar, kayıt işlemi sırasında gelen iki ileti görür:

- Şirket Portalı’nın telefon çağrıları yapmasına ve çağrıları yönetmesine izin verilsin mi?
- Şirket Portalı’nın cihazınızdaki fotoğraflara, medyaya ve dosyalara erişmesine izin verilsin mi?

Bu iletiler hakkındaki ayrıntılar için ve son kullanıcılarınıza bunlarla ilgili paylaşabileceğiniz bilgiler için aşağıdaki paragraflara bakın.

## Şirket Portalı’nın telefon çağrıları yapmasına ve çağrıları yönetmesine izin verilsin mi?

### İleti metni ve göründüğü yer
İleti metni, **Şirket Portalı’nın telefon çağrıları yapmasına ve çağrıları yönetmesine izin verilsin mi?** şeklindedir ve kullanıcılar, cihazlarını kaydetmek için Şirket Portalı uygulamasına ilk defa oturum açtığında görünür.

### İleti ne anlama geliyor
İleti, kullanıcılardan, cihaz telefon numaralarının ve IMEI numaralarının Intune hizmetine gönderilmesine ve Donanım sayfasındaki Yönetim konsolunda görüntülenmesine dair izin ister.

> [!NOTE]
> **Şirket Portalı uygulaması hiçbir zaman telefon çağrıları yapmaz veya çağrıları yönetmez!** İleti metni Google tarafından denetlenir ve değiştirilemez.

**Donanım** sayfasını görmek için, **Gruplar** > **Tüm mobil cihazlar** > **Cihazlar**’a gidin. Kullanıcının cihazını seçin ve **Özellikleri Görüntüle** > **Donanım**’a gidin..

### Kullanıcılar erişime izin verirse veya erişimi reddederse ne olur
Kullanıcılar erişime izin verirse, cihazın telefon numarası ile IMEI numarası, Yönetim konsolundaki Donanım sayfasında görüntülenir.

Kullanıcılar erişimi reddederse, Şirket Portalı uygulamasını kullanmaya ve cihazlarını kaydetmeye devam edebilirler, ancak Yönetim konsolundaki Donanım sayfasında kullanıcı cihazının telefon numarası ile IMEI numarası boş olarak görüntülenir. Kullanıcılar, erişimi reddettikten sonra Şirket Portalı uygulamasında ikinci kez oturum açtığında, kullanıcıların iletinin bir daha görüntülenmemesini seçebilmesi için **Bir daha sorma** onay kutusu görüntülenir.

Kullanıcılar erişime izin verip daha sonra erişimi reddederse ileti, kullanıcılar kayıt işleminin ardından Şirket Portalı uygulamasında bir sonraki sefer oturum açtığında görüntülenir.</br></br>Kullanıcılar daha sonra erişime izin vermeye karar verirse, **Ayarlar** > **Uygulamalar** > **Şirket Portalı** > **İzinler** > **Telefon**’a gidebilir ve ardından izni etkinleştirebilirler.

### Daha fazla bilgi için kullanıcılarınızın gönderileceği yer
[Şirket Portalı uygulamasında oturum açma](/Intune/EndUser/sign-in-to-the-company-portal-app-android)

## Şirket Portalı’nın cihazınızdaki fotoğraflara, medyaya ve dosyalara erişmesine izin verilsin mi?

### İleti metni ve göründüğü yer
İleti metni **Şirket Portalı'na, cihazınızdaki resimlere, medyaya ve dosyalara erişim izni verilsin mi?** şeklindedir kullanıcılar, veri günlüklerini BT yöneticilerine göndermek üzere **Verileri Gönder**’e dokunduğunda görünür.

### İleti ne anlama geliyor
İleti, kullanıcılardan, cihazlarına, veri günlüklerini cihazın SD kartına yazma ve o günlüklerin bir USB kablosu kullanılarak taşınmasını etkinleştirme izni vermelerini ister.   

> [!NOTE]
> **Şirket Portalı uygulaması hiçbir zaman kullanıcının fotoğraflarına, medyasına ve dosyalarına erişmez!** İleti metni Google tarafından denetlenir ve değiştirilemez.

### Kullanıcılar erişime izin verirse veya erişimi reddederse ne olur
Kullanıcı erişime izin verirse, günlükler SD karta kopyalanır.

Kullanıcılar erişimi reddederse, veri günlüklerini yine gönderebilirler, ancak günlükler cihazın SD kartına kopyalanmaz.

Kullanıcılar, erişimi reddettikten sonra Şirket Portalı uygulamasında ikinci kez oturum açtığında, kullanıcıların iletinin bir daha görüntülenmemesini seçebilmesi için **Bir daha sorma** onay kutusu görüntülenir. Kullanıcılar erişime izin verip daha sonra erişimi reddederse ileti, kullanıcılar günlükleri tekrar göndermeye çalıştığında görüntülenir. Kullanıcılar daha sonra erişime izin vermeye karar verirse, **Ayarlar** > **Uygulamalar** > **Şirket Portalı** > **İzinler** > **Mağaza**’ya gidebilir ve ardından izni etkinleştirebilirler.

### Daha fazla bilgi için kullanıcılarınızın gönderileceği yer
[Tanılama veri günlüklerini e-posta kullanarak BT yöneticinize gönderme](/Intune/EndUser/send-diagnostic-data-logs-to-your-it-administrator-using-email-android)


### Ayrıca bkz.
[Son kullanıcılarınıza Intune kullanma hakkında söylemeniz gerekenler](/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune.md)


<!--HONumber=May16_HO1-->


