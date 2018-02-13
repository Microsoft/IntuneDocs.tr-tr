---
title: "Kullanıcıların Android’de görebileceği Şirket Portalı iletileri"
description: "Intune son kullanıcılarının görebileceği Şirket Portalı uygulaması iletilerini açıklar."
keywords: 
author: barlanmsft
ms.author: barlan
manager: dougeby
ms.date: 03/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3df993aa-48c5-4799-b68d-c85fe4f7b02c
ms.reviewer: aanavath
ms.suite: ems
ms.openlocfilehash: 58468a81d0ec3e7bfc051a6edc6a09ef1c5e62a2
ms.sourcegitcommit: 9bd6278d129fa29f184b2d850138f8f65f3674ea
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="help-end-users-understand-company-portal-app-messages"></a>Son kullanıcıların Şirket Portalı uygulama iletilerini anlamasına yardımcı olma

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

> [!NOTE]
> Aşağıdaki bilgiler yalnızca Android 6.0 ve üstü cihazlar için geçerlidir.

Kayıt sürecinde farklı noktalarda, son kullanıcılar endişeye neden olabilecek iki farklı ileti görür.

- __Şirket Portalı’nın telefon çağrıları yapmasına ve çağrıları yönetmesine izin verilsin mi?__
- __Şirket Portalı’nın cihazınızdaki fotoğraflara, medyaya ve dosyalara erişmesine izin verilsin mi?__

## <a name="allow-company-portal-to-make-and-manage-phone-calls"></a>Şirket Portalı’nın telefon çağrıları yapmasına ve çağrıları yönetmesine izin verilsin mi?

### <a name="where-it-appears"></a>Göründüğü yer
**Şirket Portalı’nın telefon çağrıları yapmasına ve çağrıları yönetmesine izin verilsin mi?** iletisi, kullanıcılar cihazlarını kaydederken Şirket Portalı uygulamasında **Kaydol**’a dokunduklarında görünür.

### <a name="what-it-means"></a>Anlamı
Bu istemi kabul ederek, kullanıcılar, cihazlarının telefon ve IMEI numaralarının Intune hizmetine gönderilmesine izin vermiş olur. Bunlar, yönetim konsolundaki __Donanım__ sayfasında görünür.

> [!NOTE]
> **Şirket Portalı uygulaması hiçbir zaman telefon çağrıları yapmaz veya çağrıları yönetmez!** İleti metni Google tarafından denetlenir ve değiştirilemez.

**Donanım** sayfasını görmek için, **Gruplar** > **Tüm mobil cihazlar** > **Cihazlar**’a gidin. Kullanıcının cihazını seçin ve **Özellikleri Görüntüle** > **Donanım**’a gidin.

### <a name="what-happens-if-users-deny-access"></a>Kullanıcılar erişimi reddederse ne olur
Kullanıcıların erişimi reddederse, Şirket Portalı uygulamasını kullanmaya ve cihazlarını kaydetmeye devam edebilirler. Ancak, cihazın telefon numarası ile IMEI numarası, Yönetim konsolundaki __Donanım__ sayfasında boş olacaktır. Kullanıcılar, erişimi reddettikten sonra Şirket Portalı uygulamasında ikinci kez oturum açtığında, kullanıcıların istemi durdurmak için seçebileceği **Bir daha sorma** onay kutusu görüntülenir.

Kullanıcılar erişime izin verip daha sonra erişimi reddederse ileti, kullanıcılar kayıt işleminin ardından Şirket Portalı uygulamasında bir sonraki sefer oturum açtığında görüntülenir.

Kullanıcılar daha sonra erişime izin vermeye karar verirse, **Ayarlar** > **Uygulamalar** > **Şirket Portalı** > **İzinler** > **Telefon**’a gidebilir ve ardından izni etkinleştirebilirler.

### <a name="how-to-explain-this-to-your-users"></a>Bunu kullanıcılarınıza açıklama
Daha fazla bilgi için kullanıcılarınızı [Android cihazınızı Intune'a kaydetme](/intune-user-help/enroll-your-device-in-intune-android) bölümüne yönlendirin.

## <a name="allow-company-portal-to-access-your-contacts"></a>Şirket Portalı’nın, kişilerinize erişmesine izin verilsin mi?

### <a name="where-it-appears"></a>Göründüğü yer
**Şirket Portalı’nın kişilerinize erişmesine izin verilsin mi?** iletisi, kullanıcılar cihazlarını kaydederken Şirket Portalı uygulamasında **Kaydol**’a dokunduklarında görünür.

### <a name="what-it-means"></a>Anlamı
Bu istem kabul edildiğinde, kullanıcılar Intune’un kendileri için iş hesabı oluşturmasına ve o cihazdaki kullanıcı için kaydedilen Azure Active Directory kimliğini yönetmesine izin vermiş olur.

> [!NOTE]
> **Microsoft kişilerinize hiçbir zaman erişmez!** İleti metni Google tarafından denetlenir ve değiştirilemez.

### <a name="what-happens-if-users-deny-access"></a>Kullanıcılar erişimi reddederse ne olur
Kullanıcılar erişime izin vermezse, cihazları Intune’a kaydedilmez ve yönetilemez. Kullanıcılar, erişimi reddettikten sonra Şirket Portalı uygulamasında ikinci kez oturum açtığında, kullanıcıların istemi durdurmak için seçebileceği **Bir daha sorma** onay kutusu görüntülenir.

Kullanıcılar erişime izin verip daha sonra erişimi reddederse ileti, kullanıcılar kayıt işleminin ardından Şirket Portalı uygulamasında bir sonraki sefer oturum açtığında görüntülenir.

Kullanıcılar daha sonra erişime izin vermeye karar verirse, **Ayarlar** > **Uygulamalar** > **Şirket Portalı** > **İzinler** > **Telefon**’a gidebilir ve ardından izni etkinleştirebilirler.

### <a name="how-to-explain-this-to-your-users"></a>Bunu kullanıcılarınıza açıklama
Daha fazla bilgi için kullanıcılarınızı [Android cihazınızı Intune'a kaydetme](/intune-user-help/enroll-your-device-in-intune-android) bölümüne yönlendirin.

## <a name="allow-company-portal-to-access-photos-media-and-files-on-your-device"></a>Şirket Portalı’nın cihazınızdaki fotoğraflara, medyaya ve dosyalara erişmesine izin verilsin mi?

### <a name="where-it-appears"></a>Göründüğü yer
**Şirket Portalı'na, cihazınızdaki resimlere, medyaya ve dosyalara erişim izni verilsin mi?** iletisi, kullanıcılar, veri günlüklerini BT yöneticilerine göndermek üzere **Verileri Gönder**’e dokunduğunda görünür.

### <a name="what-it-means"></a>Anlamı
Bu istem kabul edildiğinde, kullanıcılar, cihazlarına, veri günlüklerini cihazın SD kartına yazma ve o günlüklerin bir USB kablosu kullanılarak taşınmasını etkinleştirme izni vermiş olur.   

> [!NOTE]
> **Şirket Portalı uygulaması hiçbir zaman kullanıcının fotoğraflarına, medyasına ve dosyalarına erişmez!** İleti metni Google tarafından denetlenir ve değiştirilemez.

### <a name="what-happens-if-users-deny-access"></a>Kullanıcılar erişimi reddederse ne olur
Kullanıcılar erişimi reddederse, veri günlüklerini e-posta ile yine gönderebilirler, ancak günlükler cihazın SD kartına kopyalanmaz.

Kullanıcılar, erişimi reddettikten sonra Şirket Portalı uygulamasında ikinci kez oturum açtığında, kullanıcıların iletinin bir daha görüntülenmemesini seçebilmesi için **Bir daha sorma** onay kutusu görüntülenir. Kullanıcılar erişime izin verip daha sonra erişimi reddederse ileti, kullanıcılar günlükleri tekrar göndermeye çalıştığında görüntülenir. Kullanıcılar daha sonra erişime izin vermeye karar verirse, **Ayarlar** > **Uygulamalar** > **Şirket Portalı** > **İzinler** > **Mağaza**’ya gidebilir ve ardından izni etkinleştirebilirler.


### <a name="how-to-explain-this-to-your-users"></a>Bunu kullanıcılarınıza açıklama
Kullanıcılarınızı [Günlükleri e-posta ile BT yöneticinize gönderme](/intune-user-help/send-logs-to-your-it-admin-by-email-android) bölümüne yönlendirin. 

## <a name="your-company-support-needs-to-give-you-access-to-company-resources"></a>Şirketinizin destek birimi, size şirket kaynakları erişimi sağlamalıdır

### <a name="where-it-appears"></a>Göründüğü yer
Şirket Portalı uygulamasını **İzin verilen uygulamalar** veya **Muaf uygulamalar** listelerine eklemediyseniz ve bir kullanıcı oturum açmaya çalışırsa oturum açma işlemi başarısız olur. Aşağıdaki ileti görüntülenir:

> **Şirketinizin destek birimi, size şirket kaynakları erişimi sağlamalıdır**  
> Şirketiniz, cihazınızı korumak için Windows Bilgi Koruması ilkeleri kullanıyor. Şirketinizin destek birimi, Şirket Portalı’na bunlar için erişim sağladığından emin olmalıdır.

### <a name="what-it-means"></a>Anlamı

Şirket Portalı’nı Windows Bilgi Koruması (WIP) uygulama koruma ilkesindeki **İzin verilen uygulamalar** veya **Muaf uygulamalar** listelerine ekleyin. Daha fazla bilgi için bkz. [Intune ile Windows Bilgi Koruması (WIP) uygulama koruma ilkesi oluşturma ve dağıtma](/intune-classic/deploy-use/create-windows-information-protection-policy-with-intune).

### <a name="see-also"></a>Ayrıca bkz:
[Son kullanıcılarınıza Intune kullanma hakkında söylemeniz gerekenler](end-user-educate.md)
