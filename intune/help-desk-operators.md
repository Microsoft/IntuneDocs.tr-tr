---
title: Yardım masası sorun giderme portalı
titlesuffix: Microsoft Intune
description: Yardım masası personeli, kullanıcıların teknik sorunlarını çözmek için sorun giderme portalını kullanır.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: sumitp
ms.custom: intune-azure
ms.openlocfilehash: 239c8d5dc4143ba91c78b9b5c502c7a20b101417
ms.sourcegitcommit: 7afa90264a2098453885be3d37655ae1a32ca67d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/26/2018
ms.locfileid: "47229084"
---
# <a name="use-the-troubleshooting-portal-to-help-users-at-your-company"></a>Şirketinizdeki kullanıcılara yardımcı olmak için sorun giderme portalını kullanma

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Sorun giderme portalı, yardım masası operatörlerinin ve Intune yöneticilerinin kullanıcı yardım isteklerini ele almak için kullanıcı bilgilerini görüntülemesine izin verir. Yardım masası bulunan kuruluşlar, kullanıcı gruplarına **Yardım masası işletmeni** atayabilir. Yardım masası işletmeni rolü, **Sorun Giderme** bölmesini kullanabilir.

**Sorun Giderme** bölmesi kullanıcı kayıt sorunlarını da gösterir. Sorunun ayrıntıları ve önerilen düzeltme adımları, yönetici ve yardım masası çalışanlarının sorunları çözmesine yardımcı olabilir. Bazı kayıt sorunları burada yer almaz ve bazı hatalar için düzeltme önerileri bulunmayabilir.

Bir yardım masası işletmeni rolü atama adımları için bkz. [Intune ile rol tabanlı yönetim denetimi (RBAC)](/intune/role-based-access-control)

Bir kullanıcı, Intune ile ilgili teknik bir sorun için destekle bağlantı kurduğunda yardım masası işletmeni kullanıcının adını girer. Intune, şunlar dahil olmak üzere pek çok katman 1 sorununu çözmeye yardımcı veri sunar:

- Kullanıcı durumu
- Atamalar
- Uyumluluk sorunları
- Cihaz yanıt vermiyor
- Cihaz VPN veya Wi-Fi ayarlarını alamıyor
- Uygulama yükleme hatası

## <a name="to-review-troubleshooting-details"></a>Sorun giderme ayrıntılarını gözden geçirmek için

Sorun giderme bölmesinde **Kullanıcı seçin**’e tıklayarak kullanıcı bilgilerini görüntüleyin. Kullanıcı bilgileri, kullanıcıların ve cihazlarının geçerli durumunu anlamanıza yardımcı olabilir.  

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** bölmesinde **Sorun gider**’i seçin.
4. Sorun gidermek üzere bir kullanıcı belirlemek için **Seçin**’e tıklayın.
5. Adını veya e-posta adresini yazarak bir kullanıcı seçin. **Seçin**’e tıklayın. Kullanıcı için sorun giderme bilgileri, Sorun Giderme bölmesinde görüntülenir. Bilgiler aşağıdaki tablolarda açıklanmıştır.

> [!Note]  
> **Sorun giderme** bölmesine tarayıcınızı [https://aka.ms/intunetroubleshooting](https://aka.ms/intunetroubleshooting) adresine yönlendirerek de erişebilirsiniz.

## <a name="areas-of-troubleshooting-dashboard"></a>Sorun giderme panosunun alanları

Kullanıcı bilgilerini gözden geçirmek için **Sorun Giderme** bölmesini kullanabilirsiniz.

![](/intune/media/troubleshooting-dash.png)

| Alan | Ad | Açıklama |
| ---  | ---  | ---         |
| 1.   | Hesap durumu  | Geçerli Intune kiracısının durumunu **Etkin** veya **Etkin Değil** olarak gösterir.       |
| 2.   | Kullanıcı seçimi  | Seçili kullanıcının adı. Yeni bir kullanıcı seçmek için **Kullanıcı değiştir**’e tıklayın.       |
| 3.   | Kullanıcı durumu  | Kullanıcının Intune lisansı, cihaz sayısı, cihazların uyumluluk durumu, uygulama sayısı ve uygulamaların uyumluluk durumunu görüntüler.       |
| 4.   | Kullanıcı bilgileri  | Bölmede gözden geçirmek istediğiniz ayrıntıları seçmek için listeyi kullanın. <br>Şunları seçebilirsiniz: <ul><li>İstemci uygulamaları<li>Uyumluluk ilkeleri<li> Yapılandırma ilkeleri<li>Uygulama koruma ilkeleri <li>Kayıt kısıtlamaları</ul>      |
| 5.   | Grup üyeliği  | Seçili kullanıcının üyesi olduğu geçerli grupları gösterir.       |

## <a name="client-apps-reference"></a>İstemci uygulama başvurusu

Cihaz çalıştıran uygulamalar
- Intune ve Azure Active Directory (AD) tarafından yönetiliyor 
- Intune ve Azure Active Directory (AD) tarafından yönetilen kullanıcılara ait

### <a name="properties"></a>Özellikler

İstemci uygulamaların özellikleri.

| Özellik      | Açıklama                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|---------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Ad          | Uygulamanın adı.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| İşletim sistemi            | Cihazda yüklü işletim sistemi.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Tür          | Her uygulama için bir atama türü seçebilirsiniz.  <br> **Kullanılabilir** Kullanıcılar Şirket Portalı’ndan veya web sitesinden uygulamayı yükler.  <br> **Uygulanamaz** - Uygulama yüklenmez veya Şirket Portalı’nda gösterilmez. <br> **Kaldırma** - Uygulama, seçilen gruplardaki cihazlardan kaldırılır.  <br> **Kayıtlı veya kayıtsız kullanılabilir** - Bu uygulamayı, cihazları Intune’a kayıtlı olmayan kullanıcı gruplarına atayın. |
| Son Değiştirme | Cihaz türünün adı.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |

### <a name="devices"></a>Cihazlar

Intune ile yönetilen cihazlar veya Intune ya da Azure AD ile yönetilen kullanıcılar tarafından yönetilen cihazlar.

| Özellik           | Açıklama                                                                                                                         |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Cihaz adı        | Cihaz türünün adı.                                                                                                     |
| Yöneten         | İlkenin değiştirildiği zaman damgası.                                                                                              |
| Azure AD katılım türü | Her kullanıcının uygulama koruma uygulamalarındaki durumu. Uygulamalar için olabilecek durumlar **İade edildi** ve **İade edilmedi** şeklindedir. |
| Sahibi          | Cihaz sahiplik türü (**Şirket**, **Kişisel** veya **Bilinmiyor**).                                               |
| Intune uyumlu   | Cihaz türünün adı.                                                                                                     |
| Azure AD uyumlu | Her kullanıcının uygulama koruma uygulamalarındaki durumu. Uygulamalar için olabilecek durumlar **İade edildi** ve **İade edilmedi** şeklindedir. |
| İşletim sistemi                 | Cihazda yüklü işletim sistemi.                                                                                       |
| İşletim sistemi sürümü         | Cihazın İşletim Sistemi sürüm numarası.                                                                                  |
| Son iade      | Cihaz türünün adı.                                                                                                     |

### <a name="app-protection-status"></a>Uygulama koruma durumu

Enterprise Mobility Solution (EMS) teknolojileri ile tümleşen mobil uygulamalarda bir uygulama koruma ilkesi kullanılabilir. Bu ilkeler, Office mobil uygulamaları dahil mobil uygulamalara indirildiğinde şirket verilerinizin korunması için bir taban çizgi sağlar. 

| Özellik    | Açıklama                                                                           |
|-------------|---------------------------------------------------------------------------------------|
| Durum      | Cihaz sahiplik türü (**Şirket**, **Kişisel** veya **Bilinmiyor**). |
| Uygulama adı    | Uygulamanın adı                                                           |
| Cihaz adı | Cihaz türünün adı.                                                       |
| Cihaz türü | Cihaz türünün adı.                                                       |
| İlkeler    | Cihaz sahiplik türü (**Şirket**, **Kişisel** veya **Bilinmiyor**). |
| Son eşitleme   | Cihazın Intune ile son eşitlendiği zaman damgası.                   |

## <a name="app-protection-policies-reference"></a>Uygulama koruma ilkeleri başvurusu

Bir uygulama koruma ilkesi, EMS teknolojileriyle tümleşen mobil uygulamalar tarafından kullanılabilir. Bu ilkeler, Office mobil uygulamaları dahil mobil uygulamalara indirildiğinde şirket verilerinizin koruması için bir taban çizgi sağlar. 

### <a name="properties"></a>Özellikler

Tabloda, Intune ile yönetilen cihazlar için uygulama koruma ilkeleri durumu özetlenmiştir.

| Özellik    | Açıklama                                                                                                                                |
|-------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Ad        | Uygulamanın adı.                                                                                                        |
| Dağıtıldı    | Her kullanıcının uygulama koruma uygulamalarındaki durumu. Uygulamalar için olabilecek durumlar **İade edildi** ve **İade edilmedi** şeklindedir. |
| Platform    | Cihaz sahiplik türü (**Şirket**, **Kişisel** veya **Bilinmiyor**).                                               |
| Kayıt  | Cihaz türünün adı.                                                                                                     |
| Son Güncelleme | İlkenin değiştirildiği zaman damgası.                                                                                              |

### <a name="devices"></a>Cihazlar

Intune ile yönetilen cihazlar veya Intune ya da Azure AD ile yönetilen kullanıcılar tarafından yönetilen cihazlar.

| Özellik           | Metin                                                                                                                                |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Aygıt Adı        | Cihaz türünün adı.                                                                                                     |
| Yöneten         | İlkenin değiştirildiği zaman damgası.                                                                                              |
| Azure AD katılım türü | Her kullanıcının uygulama koruma uygulamalarındaki durumu. Uygulamalar için olabilecek durumlar **İade edildi** ve **İade edilmedi** şeklindedir. |
| Sahibi          | Cihaz sahiplik türü (**Şirket**, **Kişisel** veya **Bilinmiyor**).                                               |
| Intune uyumlu   | Cihaz türünün adı.                                                                                                     |
| Azure AD uyumlu | Her kullanıcının uygulama koruma uygulamalarındaki durumu. Uygulamalar için olabilecek durumlar **İade edildi** ve **İade edilmedi** şeklindedir. |
| Azure AD uyumlu | Her kullanıcının uygulama koruma uygulamalarındaki durumu. Uygulamalar için olabilecek durumlar **İade edildi** ve **İade edilmedi** şeklindedir. |
| İşletim sistemi                 | Cihazda yüklü işletim sistemi.                                                                                       |
| İşletim sistemi sürümü         | Cihazın İşletim Sistemi sürüm numarası.                                                                                  |
| Son İade      | Cihaz türünün adı.                                                                                                     |

## <a name="compliance-policies-reference"></a>Uyumluluk ilkeleri başvurusu

Şirket uygulamalarına ve verilerine erişmek için kullanılan cihazların, cihaza erişim için PIN kullanma ve cihazda depolanan verileri şifreleme gibi belirli kurallara uyduğundan emin olmanız gerekir.

### <a name="properties"></a>Özellikler

Uyumluluk ilkelerinin özellikleri.

| Özellik      | Açıklama                                                                                                                         |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Atama    | Her kullanıcının uygulama koruma uygulamalarındaki durumu. Uygulamalar için olabilecek durumlar **İade edildi** ve **İade edilmedi** şeklindedir. |
| Ad          | Uygulamanın adı.                                                                                                        |
| İşletim sistemi            | Cihazda yüklü işletim sistemi.                                                                                       |
| İlke Türü   | Cihaz sahiplik türü (**Şirket**, **Kişisel** ve **Bilinmiyor**).                                               |
| Son Değiştirme | Cihaz türünün adı.                                                                                                     |

### <a name="devices"></a>Cihazlar

Intune ile yönetilen cihazlar veya Intune ya da Azure AD ile yönetilen kullanıcılar tarafından yönetilen cihazlar.

| Özellik           | Açıklama                                                                                                                         |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Cihaz adı        | Cihaz türünün adı.                                                                                                     |
| Yöneten         | İlkenin değiştirildiği zaman damgası.                                                                                              |
| Azure AD katılım türü | Her kullanıcının uygulama koruma uygulamalarındaki durumu. Uygulamalar için olabilecek durumlar **İade edildi** ve **İade edilmedi** şeklindedir. |
| Sahibi          | Cihaz sahiplik türü (**Şirket**, **Kişisel** ve **Bilinmiyor**).                                               |
| Intune uyumlu   | Cihaz türünün adı.                                                                                                     |
| Azure AD uyumlu | Her kullanıcının uygulama koruma uygulamalarındaki durumu. Uygulamalar için olabilecek durumlar **İade edildi** ve **İade edilmedi** şeklindedir. |
| İşletim sistemi                 | Cihazda yüklü işletim sistemi.                                                                                       |
| İşletim sistemi sürümü         | Cihazın İşletim Sistemi sürüm numarası.                                                                                  |
| Son iade      | Cihaz türünün adı.                                                                                                     |

### <a name="app-protection-policies"></a>Uygulama koruma ilkeleri

EMS teknolojileri ile tümleşen mobil uygulamalarda bir uygulama koruma ilkesi kullanılabilir. Bu ilkeler, Office mobil uygulamaları dahil mobil uygulamalara indirildiğinde şirket verilerinizin korunması için bir taban çizgi sağlar. 

| Özellik    | Açıklama                                                                           |
|-------------|---------------------------------------------------------------------------------------|
| Durum      | Cihaz sahiplik türü (**Şirket**, **Kişisel** veya **Bilinmiyor**). |
| Uygulama adı    | Uygulamanın adı                                                           |
| Cihaz adı | Cihaz türünün adı.                                                       |
| Cihaz türü | Cihaz türünün adı.                                                       |
| İlkeler    | Cihaz sahiplik türü (**Şirket**, **Kişisel** veya **Bilinmiyor**). |
| Son eşitleme   | Cihazın Intune ile son eşitlendiği zaman damgası.                   |

## <a name="configuration-policies-reference"></a>Yapılandırma ilkeleri başvurusu

Satıcıya özgü yapılandırmaları olan mobil uygulamalar için bir uygulama koruma ilkesi kullanılabilir. 

### <a name="properties"></a>Özellikler

Yapılandırma ilkelerinin özellikleri.

| Özellik      | Açıklama                                                                                                                         |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Atama    | Her kullanıcının uygulama koruma uygulamalarındaki durumu. Uygulamalar için olabilecek durumlar **İade edildi** ve **İade edilmedi** şeklindedir. |
| Ad          | Uygulamanın adı.                                                                                                        |
| İşletim sistemi            | Cihazda yüklü işletim sistemi.                                                                                       |
| İlke Türü   | Cihaz sahiplik türü (**Şirket**, **Kişisel** veya **Bilinmiyor**).                                               |
| Son Değiştirme | Cihaz türünün adı.                                                                                                     |

### <a name="devices"></a>Cihazlar

Intune ile yönetilen cihazlar veya Intune ya da Azure AD ile yönetilen kullanıcılar tarafından yönetilen cihazlar.

| Özellik           | Açıklama                                                                                                                         |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Cihaz adı        | Cihaz türünün adı.                                                                                                     |
| Yöneten         | İlkenin değiştirildiği zaman damgası.                                                                                              |
| Azure AD katılım türü | Her kullanıcının uygulama koruma uygulamalarındaki durumu. Uygulamalar için olabilecek durumlar **İade edildi** ve **İade edilmedi** şeklindedir. |
| Sahibi          | Cihaz sahiplik türü (**Şirket**, **Kişisel** veya **Bilinmiyor**).                                               |
| Intune uyumlu   | Cihaz türünün adı.                                                                                                     |
| Azure AD uyumlu | Her kullanıcının uygulama koruma uygulamalarındaki durumu. Uygulamalar için olabilecek durumlar **İade edildi** ve **İade edilmedi** şeklindedir. |
| İşletim sistemi                 | Cihazda yüklü işletim sistemi.                                                                                       |
| İşletim sistemi sürümü         | Cihazın İşletim Sistemi sürüm numarası.                                                                                  |
| Son iade      | Cihaz türünün adı.                                                                                                     |


### <a name="app-protection-policies"></a>Uygulama koruma ilkeleri

EMS teknolojileri ile tümleşen mobil uygulamalarda bir uygulama koruma ilkesi kullanılabilir. Bu ilkeler, Office mobil uygulamaları dahil mobil uygulamalara indirildiğinde şirket verilerinizin korunması için bir taban çizgi sağlar. 

| Özellik    | Açıklama                                                                           |
|-------------|---------------------------------------------------------------------------------------|
| Durum      | Cihaz sahiplik türü (**Şirket**, **Kişisel** veya **Bilinmiyor**). |
| Uygulama adı    | Uygulamanın adı                                                           |
| Cihaz adı | Cihaz türünün adı.                                                       |
| Cihaz türü | Cihaz türünün adı.                                                       |
| İlkeler    | Cihaz sahiplik türü (**Şirket**, **Kişisel** veya **Bilinmiyor**). |
| Son eşitleme   | Cihazın Intune ile son eşitlendiği zaman damgası.                   |

## <a name="enrollment-failure-reference"></a>Kayıt hatası başvurusu

Kayıt Hataları tablosu, başarısız olan kayıt denemelerini listeler. Aşağıdaki tabloda listelenen bir cihaz, daha sonra başka bir denemede başarılı olarak kaydolmuş olabilir. Bazı başarısız denemeler listelenmemiş olabilir. Hataların tümünde geçiş bilgileri bulunmaz.

| Tablo sütunu | Açıklama |
|-------------|----------|
| Kayıt başlangıç | Kullanıcının kaydı ilk kez başlattığı saat. |
| İşletim sistemi | Cihazın işletim sistemi. |
| İşletim sistemi sürümü | Cihazın işletim sistemi sürümü. |
| Başarısız | Hatanın nedeni. |

### <a name="failure-details"></a>Hata ayrıntıları

Bir hata satırını seçtiğinizde daha fazla ayrıntı sağlanır.

| Bölüm | Açıklama |
|-------------|----------|
| Hata ayrıntıları | Hatanın daha ayrıntılı bir açıklaması. |
| Toplam düzeltme sayısı | Hatayı gidermek için önerilen adımlar. Bazı hataların düzeltmeleri olmayabilir. |
| Kaynaklar (İsteğe bağlı) | Daha fazla bilgi için bağlantılar veya portaldaki eylem alanları. |

### <a name="enrollment-errors"></a>Kayıt hataları

| Hata | Ayrıntılar |
|-------------|----------|
| iOS Zaman Aşımı veya Hatası | Cihaz ve Intune arasında, kullanıcının kayıt için çok fazla süre harcaması nedeniyle oluşan zaman aşımı. |
| Kullanıcı bulunamadı veya lisanslı değil | Kullanıcının bir lisansı eksik veya kullanıcı hizmetten kaldırılmış. |
| Cihaz zaten kayıtlı | Birisi, başka bir kullanıcı için kayıtlı olan bir cihazı Şirket Portalı'nı kullanarak kaydetmeye çalıştı. |
| Intune'a eklenmedi | Intune mobil cihaz yönetimi (MDM) yetkilisi henüz yapılandırılmamışken bir kayıt girişiminde bulunuldu. |
| Kayıt yetkilendirmesi başarısız oldu | Şirket portalının eski bir sürümü kullanılarak bir kayıt girişiminde bulunuldu. |
| Cihaz desteklenmiyor | Cihaz, Intune kaydı için en düşük gereksinimleri karşılamıyor. |
| Kayıt kısıtlamaları karşılanmadı | Bu kayıt, yönetici tarafından yapılandırılmış bir kayıt kısıtlaması nedeniyle engellendi. |
| Cihaz sınırına ulaşıldı | Bu kayıt, yönetici tarafından yapılandırılmış bir cihaz sınırı nedeniyle engellendi. |
| Apple ekleme işlemi | Intune bir Apple MDM anında iletme sertifikası eksik olduğu veya sertifikanın süresi dolduğu için tüm iOS cihazlarının kaydı dönemde engellendi. |
| Cihaz önceden kayıtlı değil | Kurumsal önceden şirkete ait olarak kaydedilmediğinden tüm kişisel kayıtlar bir yönetici tarafından engellendi. |
| Özellik desteklenmiyor | Kullanıcı büyük olasılıkla Intune yapılandırmanız ile uyumlu olmayan bir yöntem aracılığıyla kaydolmaya çalışıyordu. |

## <a name="collect-available-data-from-mobile-device"></a>Mobil cihazdan kullanılabilir verileri toplama

Kullanıcının cihaz sorunlarını giderirken cihaz verilerini toplamaya yardımcı olması için aşağıdaki kaynakları kullanın:
  - [iOS kayıt hatalarını BT yöneticinize gönderme](/intune-user-help/send-errors-to-your-it-admin-ios)
  - [Ayrıntılı günlük kaydı ile şirketinizin destek birimine cihaz sorunlarını çözmede yardımcı olma](/intune-user-help/use-verbose-logging-to-help-your-it-administrator-fix-device-issues-android)
  - [USB kablosu kullanarak Android günlüklerini şirketinizin destek birimine gönderme](/intune-user-help/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)
  - [Android tanılama veri günlüklerini e-posta kullanarak BT yöneticinize gönderme](/intune-user-help/send-logs-to-your-it-admin-by-email-android)
  - [Android kayıt hatalarını BT yöneticinize gönderme](/intune-user-help/send-enrollment-errors-to-your-it-administrator-android)

## <a name="next-steps"></a>Sonraki adımlar

Kuruluş cihazınızda, mobil uygulama yönetiminde ve veri koruma görevlerinde rol tanımlamak için Rol tabanlı yönetim denetimi (RBAC) hakkında daha fazla bilgi edinebilirsiniz. Daha fazla bilgi için bkz. [Intune ile rol tabanlı yönetim denetimi (RBAC)](/intune/role-based-access-control).

Microsoft Intune’daki tüm bilinen sorunlar hakkında bilgi edinin. Daha fazla bilgi için bkz. [Microsoft Intune’da bilinen sorunlar](/intune/known-issues).

Bir destek biletini oluşturma ve gerektiğinde yardım alma hakkında bilgi edinin. [Destek alın](/intune/get-support).
