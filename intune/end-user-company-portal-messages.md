---
title: Kullanıcıların cihazlarda görebileceği Şirket Portalı iletileri
titleSuffix: Microsoft Intune
description: Son kullanıcıların Şirket Portalı'nda görebileceği farklı iletileri anlayın.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 03/09/2017
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 3df993aa-48c5-4799-b68d-c85fe4f7b02c
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1ed123bcf8c5c1a5df1a356cf8d2522caad20ea2
ms.sourcegitcommit: c9725ddae6c0f82a491de27c87f240254d32716b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2019
ms.locfileid: "71239359"
---
# <a name="help-end-users-understand-company-portal-app-messages"></a>Son kullanıcıların Şirket Portalı uygulama iletilerini anlamasına yardımcı olma

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

> [!NOTE]
> Aşağıdaki bilgiler yalnızca Android 6.0 + ve iOS 10 + cihazları için geçerlidir.

Son kullanıcıların Şirket Portalı'nda görebileceği farklı uygulama iletilerini anlayın. Bu uygulama iletileri, genellikle kayıt işleminin farklı noktalarında görüntülenir. İletilerin nerede görüntüleneceğini, ne anlama geldiğini ve kullanıcıların erişimi reddetmesi durumunda ne olacağını öğrenin. Ayrıca, iletileri kullanıcılara en iyi nasıl açıklayacağınızı öğrenin.

- __Şirket Portalı’nın telefon çağrıları yapmasına ve çağrıları yönetmesine izin verilsin mi?__
- __Şirket Portalı’nın cihazınızdaki fotoğraflara, medyaya ve dosyalara erişmesine izin verilsin mi?__

> [!NOTE]
> Her nedenden dolayı hizmetimizin tarafından toplanan herhangi bir veriyi üçüncü taraflardan satmayacağız.

## <a name="allow-company-portal-to-make-and-manage-phone-calls"></a>Şirket Portalı’nın telefon çağrıları yapmasına ve çağrıları yönetmesine izin verilsin mi?

### <a name="where-it-appears"></a>Göründüğü yer
**Şirket Portalı’nın telefon çağrıları yapmasına ve çağrıları yönetmesine izin verilsin mi?** iletisi, kullanıcılar cihazlarını kaydederken Şirket Portalı uygulamasında **Kaydol**’a dokunduklarında görünür.

### <a name="what-it-means"></a>Anlamı
Bu istemi kabul ederek, kullanıcılar, cihazlarının telefon ve IMEI numaralarının Intune hizmetine gönderilmesine izin vermiş olur. Bunlar, yönetim konsolundaki __Donanım__ sayfasında görünür.

> [!NOTE]
> **Şirket Portalı uygulaması hiçbir zaman telefon çağrıları yapmaz veya çağrıları yönetmez!** İleti metni Google tarafından denetlenir ve değiştirilemez.

**Donanım** sayfasını görmek için, **Gruplar** > **Tüm mobil cihazlar** > **Cihazlar**’a gitmeniz gerekir. Kullanıcının cihazını seçin ve **Özellikleri Görüntüle** > **Donanım**’a gidin.

### <a name="what-happens-if-users-deny-access"></a>Kullanıcılar erişimi reddederse ne olur
Kullanıcıların erişimi reddederse, Şirket Portalı uygulamasını kullanmaya ve cihazlarını kaydetmeye devam edebilirler. Ancak, cihazın telefon numarası ile IMEI numarası, Yönetim konsolundaki __Donanım__ sayfasında boş olacaktır. Kullanıcılar, erişimi reddettikten sonra Şirket Portalı uygulamasında ikinci kez oturum açtığında, kullanıcıların istemi durdurmak için seçebileceği **Bir daha sorma** onay kutusu görüntülenir.

Kullanıcılar erişime izin verip daha sonra erişimi reddederse kullanıcıların kayıt işleminin ardından Şirket Portalı uygulamasında bir sonraki oturum açışlarında ileti görüntülenir.

Kullanıcılar daha sonra erişime izin vermeye karar verirse, **Ayarlar** > **Uygulamalar** > **Şirket Portalı** > **İzinler** > **Telefon**’a gidebilir ve ardından izni etkinleştirebilirler.

### <a name="how-to-explain-this-to-your-users"></a>Bunu kullanıcılarınıza açıklama
Daha fazla bilgi için kullanıcılarınızı [Android cihazınızı Intune'a kaydetme](/intune-user-help/enroll-device-android-company-portal) bölümüne yönlendirin.

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
Daha fazla bilgi için kullanıcılarınızı [Android cihazınızı Intune'a kaydetme](/intune-user-help/enroll-device-android-company-portal) bölümüne yönlendirin.  

## <a name="allow-company-portal-to-access-photos-media-and-files-on-your-device"></a>Şirket Portalı’nın cihazınızdaki fotoğraflara, medyaya ve dosyalara erişmesine izin verilsin mi?

### <a name="where-it-appears"></a>Göründüğü yer
**Şirket Portalı'na, cihazınızdaki resimlere, medyaya ve dosyalara erişim izni verilsin mi?** iletisi, kullanıcılar, veri günlüklerini BT yöneticilerine göndermek üzere **Verileri Gönder**’e dokunduğunda görünür.

### <a name="what-it-means"></a>Anlamı
Bu istem kabul edildiğinde kullanıcılar, veri günlüklerinin cihazın SD kartına yazılmasına izin verir. Bu ayrıca günlüklerin bir USB kablosu kullanılarak taşınmasını sağlar.   

> [!NOTE]
> **Şirket Portalı uygulaması hiçbir zaman kullanıcının fotoğraflarına, medyasına ve dosyalarına erişmez!** İleti metni Google tarafından denetlenir ve değiştirilemez.

### <a name="what-happens-if-users-deny-access"></a>Kullanıcılar erişimi reddederse ne olur
Kullanıcılar erişimi reddederse, veri günlüklerini e-posta ile yine gönderebilirler, ancak günlükler cihazın SD kartına kopyalanmaz.

Kullanıcılar, erişimi reddettikten sonra Şirket Portalı uygulamasında ikinci kez oturum açtığında, kullanıcıların iletinin bir daha görüntülenmemesini seçebilmesi için **Bir daha sorma** onay kutusu görüntülenir. Kullanıcılar erişime izin verip daha sonra erişimi reddederse ileti, kullanıcılar günlükleri tekrar göndermeye çalıştığında görüntülenir. Ancak kullanıcılar daha sonra erişime izin vermeye karar verirse **Ayarlar** > **Uygulamalar** > **Şirket Portalı** > **İzinler** > **Depolama**’ya gidip izni etkinleştirebilir.


### <a name="how-to-explain-this-to-your-users"></a>Bunu kullanıcılarınıza açıklama
Kullanıcılarınızı [Günlükleri e-posta ile BT yöneticinize gönderme](/intune-user-help/send-logs-to-your-it-admin-by-email-android) bölümüne yönlendirin. 

## <a name="your-company-support-needs-to-give-you-access-to-company-resources"></a>Şirketinizin destek birimi, size şirket kaynakları erişimi sağlamalıdır

### <a name="where-it-appears"></a>Göründüğü yer
Şirket Portalı uygulamasını **İzin verilen uygulamalar** veya **Muaf uygulamalar** listesine eklemediyseniz ve bir kullanıcı oturum açmaya çalışırsa oturum açma işlemi başarısız olur. Aşağıdaki ileti görüntülenir:

> **Şirketinizin destek birimi, size şirket kaynakları erişimi sağlamalıdır**  
> Şirketiniz, cihazınızı korumak için Windows Bilgi Koruması ilkeleri kullanıyor. Şirketinizin destek birimi, Şirket Portalı’na bu kaynaklar için erişim sağladığından emin olmalıdır.

### <a name="what-it-means"></a>Anlamı

Şirket Portalı’nı Windows Bilgi Koruması (WIP) uygulama koruma ilkesindeki **İzin verilen uygulamalar** veya **Muaf uygulamalar** listelerine ekleyin. Daha fazla bilgi için bkz. [Intune ile Windows Bilgi Koruması (WIP) uygulama koruma ilkesi oluşturma ve dağıtma](windows-information-protection-policy-create.md).

## <a name="approve-a-ios-company-app-line-of-business-app-on-your-ios-device"></a>iOS cihazınızda iOS şirket uygulamasını (iş kolu uygulaması) onaylama 

### <a name="where-it-appears"></a>Göründüğü yer
Cihazınız, kuruluşunuz tarafından geliştirilen ancak App Store'da bulunmayan iOS uygulamalarına varsayılan olarak güvenmez. Bu tür uygulamaları Şirket Portalı'ndan yükleyip çalıştırdığınızda aşağıdaki ileti görüntülenir:

![iOS uygulaması iletisi - Güvenilmeyen Kurumsal Geliştirici](./media/end-user-company-portal-messages/end-user-company-portal-messages-01.png)

### <a name="what-it-means"></a>Anlamı
Bu ileti, şirketiniz tarafından geliştirilen bir uygulamayı iOS cihazınızda onaylamak ve yüklemek için iOS cihazı ayarlarınızı değiştirmeniz gerektiğini belirtir.

Bu tür uygulamaları Şirket Portalı'ndan yükleyip çalıştırmak için indirdikten sonra aşağıdaki adımları izleyerek onaylamanız gerekir:

1. Yüklediğiniz şirket uygulamasını (iş kolu uygulaması) çalıştırdığınızda "Güvenilmeyen Kurumsal Geliştirici" iletisiyle karşılaşırsınız. <br>
   **İptal**'e basın.
2. **Ayarlar** > **Genel** > **Cihaz Yönetimi** yolunu izleyin.

   ![iOS cihazı kullanıcı arabirimi - Cihaz Yönetimi](./media/end-user-company-portal-messages/end-user-company-portal-messages-02.png)

3. **Yönetim Profili** > **Kurumsal uygulama**'yı seçin.
4. Geliştirici adını seçin.
5. **_Geliştirici adına_ güven**'e basın.
6. Uygulama yüklenirken açılan iletide **Güven**'i seçerek uygulamayı onaylayın.

   ![iOS cihazı kullanıcı arabirimi - Uygulamaya güven iletisi](./media/end-user-company-portal-messages/end-user-company-portal-messages-03.png)

    Bu adımların ardından şirket uygulamasını çalıştırabilir ve kullanabilirsiniz.


## <a name="see-also"></a>Ayrıca bkz.
[Son kullanıcılarınıza Intune kullanma hakkında söylemeniz gerekenler](end-user-educate.md)
