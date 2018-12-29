---
title: Şirket Portalı uygulamasını yapılandırma
titleSuffix: Microsoft Intune
description: Intune Şirket Portalı uygulamasına şirkete özgü marka uygulamayı öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: dec6f258-ee1b-4824-bf66-29053051a1ae
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 72349a609485096b5abd6eaff3c252a510a978a7
ms.sourcegitcommit: 279f923b1802445e501324a262d14e8bfdddabde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2018
ms.locfileid: "53738027"
---
# <a name="how-to-configure-the-microsoft-intune-company-portal-app"></a>Microsoft Intune Şirket Portalı uygulamasını yapılandırma

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Microsoft Intune şirket portalı, kullanıcıların şirket verilerine eriştiği ve cihaz kaydetmek, uygulama yüklemek ve BT departmanınızdan yardım için bilgi bulmak gibi genel görevleri gerçekleştirebilecekleri yerdir.        

> [!Tip]        
> Şirket Portalı’nı özelleştirdiğinizde, yapılandırmalar hem Şirket Portalı web sitesi hem de Şirket Portalı uygulamaları için geçerli olur. Kullanıcılar Şirket portalı Web sitesine erişim için atanmış bir Intune lisansı olması gerektiğini unutmayın.

Şirket Portalı’nı özelleştirmek, son kullanıcılarınız için tanıdık ve yararlı bir deneyim sağlamaya yardımcı olur. Bunu yapmak için, **İstemci uygulamaları** iş yükünde **Kurulum** > **Şirket Portalı Markalaması**’nı seçin ve gerekli ayarları yapılandırın.  

> [!Note]       
> Azure Kamu kullanıyorsanız, bir sorunla ilgili yardım alma sürecini başlattığında bunu nasıl paylaşacağına karar vermesi için son kullanıcıya uygulama günlükleri sunulur. Ancak Azure Kamu kullanmıyorsa, kullanıcı bir sorunla ilgili yardım alma sürecini başlattığında Windows 10 için Şirket Portalı uygulama günlüklerini doğrudan Microsoft'a gönderir. Uygulama günlüklerini Microsoft'a göndermek sorunları gidermeyi ve çözmeyi kolaylaştıracaktır. 

## <a name="company-information-and-privacy-statement"></a>Şirket bilgileri ve gizlilik bildirimi        
Şirket adı, Şirket Portalı’nın başlığı olarak görüntülenir. Gizlilik bildirimini, kullanıcı gizlilik bağlantısına tıkladığında görüntülenir.

Yıldız işareti (*) ile işaretlenmiş alanlar zorunludur.       


| Alan adı | Uzunluk üst sınırı | Daha fazla bilgi |
|---|---|---|
|**Şirket adı**| 40 | Bu ad Şirket Portalı'nın başlığı olarak görüntülenir ve Intune kullanıcı deneyiminin her yerinde metin olarak gösterilir. |
| **Gizlilik bildirimi URL'si** |     79     | Kullanıcılar Şirket Portalı’nda gizlilik bağlantılarına tıkladığında görüntülenecek kendi şirket gizlilik bildiriminizi belirtebilirsiniz. `<https://www.contoso.com>` biçiminde geçerli bir URL girmeniz gerekir. |

## <a name="support-information"></a>Destek bilgileri      
Intune ile ilgili sorular için çalışan bir kişi sağlamak için şirketinizin destek bilgilerini girin.          

|Alan adı|Uzunluk üst sınırı|Daha fazla bilgi|
|---|---|---|
|**Kişi adı** | 40 | Bu ad **BT’ye Başvur**sayfasında gösterilir. |
|**Telefon numarası** | 20 | Çalışanların destek almak üzere size başvurabilmesini sağlamak için bu iletişim numarası **BT'ye Başvur** sayfasında görüntülenir. |
|**E-posta adresi**| 40 | Bu iletişim adresi **BT'ye Başvur** sayfasında gösterilir. `alias@domainname.com` biçiminde geçerli bir e-posta adresi girmeniz gerekir. |
|**Web sitesinin adı**| 40 | Bu ad destek web sitesi URL'si için görüntülenen kolay addır. Bir destek web sitesi URL'si belirtir ve bir kolay ad belirtmezseniz, Şirket Portalı’ndaki **BT'ye Başvur** sayfasında BT web sitesine gidin ifadesi gösterilir. |
|**Web sitesi URL'si**| 150 | Kullanıcılarınızın kullanmasını istediğiniz bir destek web siteniz varsa, URL'sini burada belirtin. URL, `https://www.contoso.com` biçiminde olmalıdır. Bir URL belirtmezseniz, Şirket Portalı’ndaki **BT'ye Başvur** sayfasında destek web sitesi için hiçbir şey görünmez. |
| **Ek bilgiler**| 120 | **BT'ye Başvur** sayfasında gösterilir. |


## <a name="company-identity-branding-customization"></a>Şirket kimliği marka özelleştirme      
Şirket Portalınızı şirket logonuz, şirket adınız, tema renginiz ve arka planınızla özelleştirebilirsiniz.     

### <a name="theme-color-and-logo-in-the-company-portal"></a>Şirket Portalı’nda tema rengi ve logo
Şirket Portalı’na bir tema rengi uygulayın. Standart renklerden birini seçin veya özel renk için alt basamaklı onaltılık kodu girin.

|Alan adı|Daha fazla bilgi|
|---|---|
|**Standart renklerden birini seçin veya altı basamaklı onaltılık kod girin**| Seçin **standart** görsel olarak bir renk seçin. Onaltılık kod değerine göre belirli bir renk belirtmek için **Özel**’i seçin.|
|**Tema rengi seçin**| Şirket Portalı’na uygulamak için bir tema rengi seçin. Standart renk seçebilir veya belirli bir onaltılık kodu girebilirsiniz. |
|**Görüntüleme**| Hangisinin görüntüleneceğini seçin: **Şirket logosu ve adı**, **Yalnızca şirket logosu** veya **Yalnızca şirket adı**. |
|**Şirket logonuzu karşıya yükleyin**|Size ait Şirket Portalı’nda görüntülenmek üzere şirket logonuzu yükleyebilirsiniz. En yüksek kontrast düzeyini sağlamak için metin renginin otomatik olarak seçildiğini unutmayın. En iyi görünümü elde etmek için saydam bir arka plana sahip bir logo yükleyin.<p><ul><li>En yüksek görüntü boyutu: 400 piksel ölçülerinden küçük x 400px</li><li>En büyük dosya boyutu: 750KB</li><li>Dosya türü: PNG, JPG veya JPEG</li></ul>|

Logo yüklendikten sonra önizleme alanında tema rengiyle logo görüntülenir. Şirketinizin adını görüntülemeyi seçerseniz bu ad, Şirket Portalı’nda siyah veya beyaz renkte görüntülenir. Tema renginizle en yüksek kontrastı sağlayan renk otomatik olarak seçilir. Ekrandaki önizleme alanında şirketinizin adı görüntülenmez. 

### <a name="logo-to-use-on-white-or-light-backgrounds"></a>Beyaz veya açık renk arka planda kullanılacak logo
Beyaz veya açık renk arka planlarda en iyi görünecek logoyu seçin.

|Alan adı|Daha fazla bilgi|
|---|---|
|**Logonuzu karşıya yükleyin**| Bu seçeneğin kullanılabilmesi için şirket logosunu göstermeyi seçmiş olmalısınız. En iyi görünümü elde etmek için saydam bir arka plana sahip bir logo yükleyin.<p><ul><li>En yüksek görüntü boyutu: 400 piksel ölçülerinden küçük x 400px</li><li>En büyük dosya boyutu: 750KB</li><li>Dosya türü: PNG, JPG veya JPEG</li></ul>|

### <a name="brand-image-for-company-portal"></a>Şirket Portalı için marka imajı

Şirket markanızı yansıtan bir marka imajı kullanın. Değişikliklerinizi kaydettikten sonra, yapılandırmalarınızın nasıl görüneceğine bakmak için dikey pencerenin üst kısmındaki Intune Web Portalı’nda **Ayarlarınızın önizlemesini görüntüleyin** öğesini seçebilirsiniz. Marka imajını Intune Web Portalı’nda değil, yalnızca bir iOS cihazında görüntüleyebileceğinizi unutmayın. 

|Alan adı|Daha fazla bilgi|
|---|---|
|**Marka imajınızı karşıya yükleyin**| Bu seçenek, Şirket Portalı uygulamasındaki kullanıcı profili sayfasında bir arka plan görüntüsü kullanmanıza imkan verir.<p>*Not*: Görüntü, farklı platformları için farklı görüntülenebilir.<p><ul><li>Önerilen görüntü genişliği: Ancak 640 piksel en az bir 1125px büyüktür</li><li>En yüksek görüntü boyutu: 1.3 MB</li><li>Dosya türü: PNG, JPG veya JPEG</li></ul>|

Doğru bir marka imajı sayesinde şirket markanızı güçlü bir şekilde tanıtarak Şirket Portalı’nda kullanıcı güvenini artırabilirsiniz. Aşağıda, Şirket Portalı için imaj elde etme, seçme ve iyileştirme hakkında bazı ipuçları bulabilirsiniz. 

- Pazarlama veya sanat departmanınıza ulaşın. Bunlar zaten onaylı bir marka görüntü kümesi olabilir. Departmanlar ayrıca görüntüleri ihtiyaca göre iyileştirme konusunda size yardım edebilir. 

- Yatay ve dikey kompozisyonları değerlendirin. İmajın odak noktasını çevreleyen arka planın yeterli olmasına dikkat edin. Farklı cihaz boyut, Yönlendirme ve platform göre resim kırpılmış. 

- Sıradan, hazır bir imaj seçmekten kaçının. İmaj, şirketinizin markasını yansıtmalı ve kullanıcılara yakın hissettirmelidir. Elinizde bir imaj yoksa, kullanıcılarınıza hiçbir şey ifade etmeyen sıradan bir görüntü kullanmak yerine hiçbir şey kullanmamak daha iyi olacaktır. 

- Gereksiz meta verileri kaldırın. İmaj dosyası; kamera profili, coğrafi konum, başlık, açıklama gibi meta veriler içerebilir. Kaliteyi korumak ve dosya boyutu sınırını aşmamak için bir görüntü iyileştirme aracını kullanarak bu bilgileri kaldırın. 

Marka resmi eklendiğinde veya Intune'a değiştirilen sonra şirket Portalı'kurmak başlangıç değişikliğin tarafından tanınan ve ardından marka görüntüyü görüntülemek için yeniden kadar son kullanıcı değişikliği iOS cihazlarında göremeyebilirsiniz. 

### <a name="brand-image-examples"></a>Marka resmi örnekleri

Aşağıdaki resimde örnek İpad'de marka resmi gösterir:

![Marka resmi örnek iPhone ekran görüntüsü](media/company-portal-app/company-portal-app-03.png)

Aşağıdaki görüntüde, marka resmi İphone'da örnek gösterilmektedir:

![Marka resmi örnek iPad ekran görüntüsü](media/company-portal-app/company-portal-app-02.png)

## <a name="windows-company-portal-keyboard-shortcuts"></a>Windows Şirket Portalı klavye kısayolları

Son kullanıcılar, klavye kısayolları (Hızlandırıcıları) kullanarak Windows Şirket portalı'nda gezinti, uygulama ve cihaz eylemleri tetikleyebilirsiniz.

Windows Şirket Portalı uygulamasında aşağıdaki kısayollar kullanılabilir.

| Alan | Açıklama | Klavye kısayolu |
|:------------------:|:--------------:|:-----------------:|
| Gezinti menüsü | Gezinti | Alt+M |
|  | Ana Sayfası | Alt+H |
|  | Tüm uygulamalar | Alt + A |
|  | Yüklenen uygulamalar | Alt+I |
|  | Geri bildirim gönder | Alt+F |
|  | Profilim | Alt+U |
|  | Ayarlar | Alt+T |
| Giriş - Cihaz kutucuğu | Yeniden Adlandır | F2 |
|  | Kaldır | Ctrl+D veya Delete |
|  | Erişimi denetle | Ctrl+M veya F9 |
| Cihaz ayrıntıları | Yeniden Adlandır | F2 |
|  | Kaldır | Ctrl+D veya Delete |
|  | Erişimi denetle | Ctrl+M veya F9 |
| Uygulama ayrıntıları | Yükleme | Ctrl+I |

Son kullanıcılar Windows Şirket portalı uygulamasında kullanılabilir kısayolları görmeniz mümkün olacaktır.

![Windows Şirket portalı'nda kullanılabilir kısayolları ekran görüntüsü](media/company-portal-app/company-portal-app-01.png)

## <a name="next-steps"></a>Sonraki adımlar

- [Microsoft Intune kullanarak Windows 10 Şirket Portalı uygulamasını el ile ekleme](store-apps-company-portal-app.md)
