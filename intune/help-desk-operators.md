---
title: "Yardım masası sorun giderme portalı | Microsoft Docs"
titlesuffix: Azure portal
description: "Yardım masası personeli, kullanıcıların teknik sorunlarını çözmek için sorun giderme portalını kullanır"
keywords: 
author: Erikre
ms.author: erikre
manager: angrobe
ms.date: 09/26/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: sumitp
ms.custom: intune-azure
ms.openlocfilehash: 845b225fe60ecde71f364b224a0984638662a3db
ms.sourcegitcommit: 833b1921ced35be140f0107d0b4205ecacd2753b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/04/2018
---
# <a name="use-the-troubleshooting-portal-to-help-users"></a>Kullanıcılara yardımcı olmak için sorun giderme portalını kullanın

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Sorun giderme portalı, yardım masası operatörlerinin ve Intune yöneticilerinin kullanıcı yardım isteklerini ele almak için kullanıcı bilgilerini görüntülemesine izin verir. Yardım masası bulunan kuruluşlar, kullanıcı gruplarına **Yardım masası işletmeni** atayabilir. Yardım masası işletmeni rolü, **Sorun Giderme** dikey penceresini kullanabilir.

**Sorun Giderme** dikey penceresi kullanıcı kayıt sorunlarını da gösterir. Sorunun ayrıntıları ve önerilen düzeltme adımları, yönetici ve yardım masası çalışanlarının sorunları çözmesine yardımcı olabilir. Bazı kayıt sorunları burada yer almaz ve bazı hatalar için düzeltme önerileri bulunmayabilir. 

Bir yardım masası işletmeni rolü atama adımları için bkz. [Intune ile rol tabanlı yönetim denetimi (RBAC)](/intune/role-based-access-control)

Bir kullanıcı, Intune ile ilgili teknik bir sorun için destekle bağlantı kurduğunda yardım masası işletmeni kullanıcının adını girer. Intune, şunlar dahil olmak üzere pek çok katman 1 sorununu çözmeye yardımcı veri sunar:

- Kullanıcı durumu
- Atamalar
- Uyumluluk sorunları
- Cihaz 
- Cihaz VPN veya Wi-Fi ayarlarını alamıyor
- Uygulama yükleme hatası

## <a name="to-review-troubleshooting-details"></a>Sorun giderme ayrıntılarını gözden geçirmek için

Sorun giderme dikey penceresinde **Kullanıcı seç**’e tıklayarak kullanıcı bilgilerini görüntüleyin. Kullanıcı bilgileri, kullanıcıların ve cihazlarının geçerli durumunu anlamanıza yardımcı olabilir.  

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Sorun gider**’i seçin.
4. **Kullanıcı seç**’e tıklayın.
5. Adını veya e-posta adresini yazarak bir kullanıcı seçin. **Seçin**’e tıklayın. Kullanıcı için sorun giderme bilgileri, Sorun Giderme dikey penceresinde görüntülenir. Aşağıdaki tablolarda bilgiler açıklanmıştır.

> [!Note]  
> **Sorun giderme** dikey penceresine ayrıca tarayıcınızı [https://aka.ms/intunetroubleshooting](https://aka.ms/intunetroubleshooting) adresine yönlendirerek de erişebilirsiniz.

## <a name="areas-of-troubleshooting-dashboard"></a>Sorun giderme panosunun alanları

Kullanıcı bilgilerini gözden geçirmek için **Sorun Giderme** dikey penceresini kullanabilirsiniz. 

![](/intune/media/troubleshooting-dash.png)

| Alan | Ad | Description |
| ---  | ---  | ---         |
| 1.   | Hesap durumu  | Geçerli Intune kiracısının durumunu **Etkin** veya **Etkin Değil** olarak gösterir.       |
| 2.   | Kullanıcı seçimi  | Seçili kullanıcının adı. Yeni bir kullanıcı seçmek için **Kullanıcı değiştir**’e tıklayın.       |
| 3.   | Kullanıcı durumu  | Kullanıcının Intune lisansı, cihaz sayısı, cihazların uyumluluk durumu, uygulama sayısı ve uygulamaların uyumluluk durumunu görüntüler.       |
| 4.   | Kullanıcı bilgileri  | Dikey pencerede gözden geçirmek istediğiniz ayrıntıları seçmek için listeyi kullanın. <br>Şunları seçebilirsiniz: <ul><li>Mobil uygulamalar<li>Uygulama koruma ilkeleri<li>Uyumluluk ilkeleri<li> Yapılandırma ilkeleri</ul>      |
| 5.   | Grup üyeliği  | Yadda       |

## <a name="mobile-apps-reference"></a>Mobil uygulama başvurusu

Cihazlarda çalışan uygulamalar veya Intune ve Azure Active Directory (AD) ile yönetilen kullanıcılara ait cihazlar.

### <a name="properties"></a>Özellikler

Mobil uygulamaların özellikleri.

| Özellik      | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|---------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Ad          | Uygulamanın adı.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| İşletim sistemi            | Cihazda yüklü işletim sistemi.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Tür          | Her uygulama için bir atama türü seçebilirsiniz.  <br> **Kullanılabilir** Kullanıcılar Şirket Portalı’ndan veya web sitesinden uygulamayı yükler.  <br> **Uygulanamaz** - Uygulama yüklenmez veya Şirket Portalı’nda gösterilmez. <br> **Kaldırma** - Uygulama, seçilen gruplardaki cihazlardan kaldırılır.  <br> **Kayıtlı veya kayıtsız kullanılabilir** - Bu uygulamayı, cihazları Intune’a kayıtlı olmayan kullanıcı gruplarına atayın. |
| Son Değiştirme | Cihaz türünün adı.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |

### <a name="devices"></a>Cihazlar

Intune ile yönetilen cihazlar veya Intune ya da Azure AD ile yönetilen kullanıcılar tarafından yönetilen cihazlar.

| Özellik           | Description                                                                                                                         |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Cihaz adı        | Cihaz türünün adı.                                                                                                     |
| Yöneten         | İlkenin değiştirildiği zaman damgası.                                                                                              |
| Azure AD katılım türü | Her kullanıcının uygulama koruma uygulamalarındaki durumu. Uygulamalar için olabilecek durumlar **İade edildi** ve **İade edilmedi** şeklindedir. |
| Sahibi          | Cihaz sahipliği türü. Bu **Şirket**, **Kişisel** veya **Bilinmeyen** olabilir.                                               |
| Intune uyumlu   | Cihaz türünün adı.                                                                                                     |
| Azure AD uyumlu | Her kullanıcının uygulama koruma uygulamalarındaki durumu. Uygulamalar için olabilecek durumlar **İade edildi** ve **İade edilmedi** şeklindedir. |
| İşletim sistemi                 | Cihazda yüklü işletim sistemi.                                                                                       |
| İşletim sistemi sürümü         | Cihazın İşletim Sistemi sürüm numarası.                                                                                  |
| Son iade      | Cihaz türünün adı.                                                                                                     |

### <a name="app-protection-status"></a>Uygulama koruma durumu

Enterprise Mobility Solution (EMS) teknolojileri ile tümleşen mobil uygulamalarda bir uygulama koruma ilkesi kullanılabilir. Bu, şirket verileriniz Office uygulamaları dahil olmak üzere mobil uygulamalara indirildiğinde, veriler için temel bir koruma sağlar. 

| Özellik    | Description                                                                           |
|-------------|---------------------------------------------------------------------------------------|
| Durum      | Cihaz sahipliği türü. Bu **Şirket**, **Kişisel** veya **Bilinmeyen** olabilir. |
| Uygulama adı    | Uygulamanın adı                                                           |
| Cihaz adı | Cihaz türünün adı.                                                       |
| Cihaz türü | Cihaz türünün adı.                                                       |
| İlkeler    | Cihaz sahipliği türü. Bu **Şirket**, **Kişisel** veya **Bilinmeyen** olabilir. |
| Son eşitleme   | Cihazın Intune ile son eşitlendiği zaman damgası.                   |

## <a name="app-protection-policies-reference"></a>Uygulama koruma ilkeleri başvurusu

EMS teknolojileri ile tümleşen mobil uygulamalarda bir uygulama koruma ilkesi kullanılabilir. Bu, şirket verileriniz Office uygulamaları dahil olmak üzere mobil uygulamalara indirildiğinde, veriler için temel bir koruma sağlar. 

### <a name="properties"></a>Özellikler

Tabloda, Intune ile yönetilen cihazlar için uygulama koruma ilkeleri durumu özetlenmiştir.

| Özellik    | Description                                                                                                                                |
|-------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Ad        | Uygulamanın adı.                                                                                                        |
| Dağıtıldı    | Her kullanıcının uygulama koruma uygulamalarındaki durumu. Uygulamalar için olabilecek durumlar **İade edildi** ve **İade edilmedi** şeklindedir. |
| Platform    | Cihaz sahipliği türü. Bu **Şirket**, **Kişisel** veya **Bilinmeyen** olabilir.                                               |
| Kayıt  | Cihaz türünün adı.                                                                                                     |
| Son Güncelleme | İlkenin değiştirildiği zaman damgası.                                                                                              |

### <a name="devices"></a>Cihazlar

Intune ile yönetilen cihazlar veya Intune ya da Azure AD ile yönetilen kullanıcılar tarafından yönetilen cihazlar.

| Özellik           | Metin                                                                                                                                |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Aygıt Adı        | Cihaz türünün adı.                                                                                                     |
| Yöneten         | İlkenin değiştirildiği zaman damgası.                                                                                              |
| Azure AD katılım türü | Her kullanıcının uygulama koruma uygulamalarındaki durumu. Uygulamalar için olabilecek durumlar **İade edildi** ve **İade edilmedi** şeklindedir. |
| Sahibi          | Cihaz sahipliği türü. Bu **Şirket**, **Kişisel** veya **Bilinmeyen** olabilir.                                               |
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

| Özellik      | Description                                                                                                                         |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Atama    | Her kullanıcının uygulama koruma uygulamalarındaki durumu. Uygulamalar için olabilecek durumlar **İade edildi** ve **İade edilmedi** şeklindedir. |
| Ad          | Uygulamanın adı.                                                                                                        |
| İşletim sistemi            | Cihazda yüklü işletim sistemi.                                                                                       |
| İlke Türü   | Cihaz sahipliği türü. Bu **Şirket**, **Kişisel** veya **Bilinmeyen** olabilir.                                               |
| Son Değiştirme | Cihaz türünün adı.                                                                                                     |

### <a name="devices"></a>Cihazlar

Intune ile yönetilen cihazlar veya Intune ya da Azure AD ile yönetilen kullanıcılar tarafından yönetilen cihazlar.

| Özellik           | Description                                                                                                                         |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Cihaz adı        | Cihaz türünün adı.                                                                                                     |
| Yöneten         | İlkenin değiştirildiği zaman damgası.                                                                                              |
| Azure AD katılım türü | Her kullanıcının uygulama koruma uygulamalarındaki durumu. Uygulamalar için olabilecek durumlar **İade edildi** ve **İade edilmedi** şeklindedir. |
| Sahibi          | Cihaz sahipliği türü. Bu **Şirket**, **Kişisel** veya **Bilinmeyen** olabilir.                                               |
| Intune uyumlu   | Cihaz türünün adı.                                                                                                     |
| Azure AD uyumlu | Her kullanıcının uygulama koruma uygulamalarındaki durumu. Uygulamalar için olabilecek durumlar **İade edildi** ve **İade edilmedi** şeklindedir. |
| İşletim sistemi                 | Cihazda yüklü işletim sistemi.                                                                                       |
| İşletim sistemi sürümü         | Cihazın İşletim Sistemi sürüm numarası.                                                                                  |
| Son iade      | Cihaz türünün adı.                                                                                                     |

### <a name="app-protection-policies"></a>Uygulama koruma ilkeleri

EMS teknolojileri ile tümleşen mobil uygulamalarda bir uygulama koruma ilkesi kullanılabilir. Bu, şirket verileriniz Office uygulamaları dahil olmak üzere mobil uygulamalara indirildiğinde, veriler için temel bir koruma sağlar. 

| Özellik    | Description                                                                           |
|-------------|---------------------------------------------------------------------------------------|
| Durum      | Cihaz sahipliği türü. Bu **Şirket**, **Kişisel** veya **Bilinmeyen** olabilir. |
| Uygulama adı    | Uygulamanın adı                                                           |
| Cihaz adı | Cihaz türünün adı.                                                       |
| Cihaz türü | Cihaz türünün adı.                                                       |
| İlkeler    | Cihaz sahipliği türü. Bu **Şirket**, **Kişisel** veya **Bilinmeyen** olabilir. |
| Son eşitleme   | Cihazın Intune ile son eşitlendiği zaman damgası.                   |

## <a name="configuration-policies-reference"></a>Yapılandırma ilkeleri başvurusu

Satıcıya özgü yapılandırmaları olan mobil uygulamalar için bir uygulama koruma ilkesi kullanılabilir. 

### <a name="properties"></a>Özellikler

Yapılandırma ilkelerinin özellikleri.

| Özellik      | Description                                                                                                                         |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Atama    | Her kullanıcının uygulama koruma uygulamalarındaki durumu. Uygulamalar için olabilecek durumlar **İade edildi** ve **İade edilmedi** şeklindedir. |
| Ad          | Uygulamanın adı.                                                                                                        |
| İşletim sistemi            | Cihazda yüklü işletim sistemi.                                                                                       |
| İlke Türü   | Cihaz sahipliği türü. Bu **Şirket**, **Kişisel** veya **Bilinmeyen** olabilir.                                               |
| Son Değiştirme | Cihaz türünün adı.                                                                                                     |

### <a name="devices"></a>Cihazlar

Intune ile yönetilen cihazlar veya Intune ya da Azure AD ile yönetilen kullanıcılar tarafından yönetilen cihazlar.

| Özellik           | Description                                                                                                                         |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Cihaz adı        | Cihaz türünün adı.                                                                                                     |
| Yöneten         | İlkenin değiştirildiği zaman damgası.                                                                                              |
| Azure AD katılım türü | Her kullanıcının uygulama koruma uygulamalarındaki durumu. Uygulamalar için olabilecek durumlar **İade edildi** ve **İade edilmedi** şeklindedir. |
| Sahibi          | Cihaz sahipliği türü. Bu **Şirket**, **Kişisel** veya **Bilinmeyen** olabilir.                                               |
| Intune uyumlu   | Cihaz türünün adı.                                                                                                     |
| Azure AD uyumlu | Her kullanıcının uygulama koruma uygulamalarındaki durumu. Uygulamalar için olabilecek durumlar **İade edildi** ve **İade edilmedi** şeklindedir. |
| İşletim sistemi                 | Cihazda yüklü işletim sistemi.                                                                                       |
| İşletim sistemi sürümü         | Cihazın İşletim Sistemi sürüm numarası.                                                                                  |
| Son iade      | Cihaz türünün adı.                                                                                                     |


### <a name="app-protection-policies"></a>Uygulama koruma ilkeleri

EMS teknolojileri ile tümleşen mobil uygulamalarda bir uygulama koruma ilkesi kullanılabilir. Bu, şirket verileriniz Office uygulamaları dahil olmak üzere mobil uygulamalara indirildiğinde, veriler için temel bir koruma sağlar. 

| Özellik    | Description                                                                           |
|-------------|---------------------------------------------------------------------------------------|
| Durum      | Cihaz sahipliği türü. Bu **Şirket**, **Kişisel** veya **Bilinmeyen** olabilir. |
| Uygulama adı    | Uygulamanın adı                                                           |
| Cihaz adı | Cihaz türünün adı.                                                       |
| Cihaz türü | Cihaz türünün adı.                                                       |
| İlkeler    | Cihaz sahipliği türü. Bu **Şirket**, **Kişisel** veya **Bilinmeyen** olabilir. |
| Son eşitleme   | Cihazın Intune ile son eşitlendiği zaman damgası.                   |

## <a name="next-steps"></a>Sonraki adımlar

Kuruluş cihazınızda, mobil uygulama yönetiminde ve veri koruma görevlerinde rol tanımlamak için Rol tabanlı yönetim denetimi (RBAC) hakkında daha fazla bilgi edinebilirsiniz. Daha fazla bilgi için bkz. [Intune ile rol tabanlı yönetim denetimi (RBAC)](/intune/role-based-access-control).

Microsoft Intune’daki tüm bilinen sorunlar hakkında bilgi edinin. Daha fazla bilgi için bkz. [Microsoft Intune’da bilinen sorunlar](/intune/known-issues).

Bir destek biletini oluşturma ve gerektiğinde yardım alma hakkında bilgi edinin. [Destek alın](/intune/get-support).