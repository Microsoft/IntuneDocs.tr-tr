---
title: Şirket Portalı uygulamasını yapılandırma
titleSuffix: Microsoft Intune
description: Intune Şirket Portalı uygulamasına şirkete özgü marka uygulamayı öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/01/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: dec6f258-ee1b-4824-bf66-29053051a1ae
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 33f24a3d7b30973855bb303bb97bf703cd4dc5fa
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2019
ms.locfileid: "59895423"
---
# <a name="how-to-configure-the-microsoft-intune-company-portal-app"></a>Microsoft Intune Şirket Portalı uygulamasını yapılandırma

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Microsoft Intune şirket portalı, kullanıcıların şirket verilerine eriştiği ve cihaz kaydetmek, uygulama yüklemek ve BT departmanınızdan yardım için bilgi bulmak gibi genel görevleri gerçekleştirebilecekleri yerdir.        

> [!Tip]        
> Şirket Portalı’nı özelleştirdiğinizde, yapılandırmalar hem Şirket Portalı web sitesi hem de Şirket Portalı uygulamaları için geçerli olur. Şirket Portalı'na erişmek isteyen kullanıcılara Intune lisansı atanmış olmalıdır.

Şirket Portalı’nı özelleştirerek, son kullanıcılarınız için tanıdık ve yararlı bir deneyim sağlanmasına yardımcı olabilirsiniz. Bunun için Intune portalında **İstemci uygulamaları** > **Markalama ve özelleştirme**'yi seçip gerekli ayarları yapılandırın. 

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
Çalışanınıza Intune'la ilgili sorularında bir başvuru noktası sağlamak için şirketinizin destek bilgilerini girin.          

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
|**Standart renklerden birini seçin veya altı basamaklı onaltılık kod girin**| Bir renk seçmek için **Standart**’ı seçin. Onaltılık kod değerine göre belirli bir renk belirtmek için **Özel**’i seçin.|
|**Tema rengi seçin**| Şirket Portalı’na uygulamak için bir tema rengi seçin. Standart renk seçebilir veya belirli bir onaltılık kodu girebilirsiniz. |
|**Görüntüleme**| Hangisinin görüntüleneceğini seçin: **Şirket logosu ve adı**, **Yalnızca şirket logosu** veya **Yalnızca şirket adı**. |
|**Şirket logonuzu karşıya yükleyin**|Size ait Şirket Portalı’nda görüntülenmek üzere şirket logonuzu yükleyebilirsiniz. En yüksek kontrast düzeyini sağlamak için metin renginin otomatik olarak seçildiğini unutmayın. En iyi görünümü elde etmek için saydam bir arka plana sahip bir logo yükleyin.<p><ul><li>En yüksek görüntü boyutu: 400 piksel x 400 piksel</li><li>En büyük dosya boyutu: 750 KB</li><li>Dosya türü: PNG, JPG veya JPEG</li></ul>|

Logo yüklendikten sonra önizleme alanında tema rengiyle logo görüntülenir. Şirketinizin adını görüntülemeyi seçerseniz bu ad, Şirket Portalı’nda siyah veya beyaz renkte görüntülenir. Tema renginizle en yüksek kontrastı sağlayan renk otomatik olarak seçilir. Ekrandaki önizleme alanında şirketinizin adı görüntülenmez. 

### <a name="logo-to-use-on-white-or-light-backgrounds"></a>Beyaz veya açık renk arka planda kullanılacak logo
Beyaz veya açık renk arka planlarda en iyi görünecek logoyu seçin.

|Alan adı|Daha fazla bilgi|
|---|---|
|**Logonuzu karşıya yükleyin**| Bu seçeneğin kullanılabilmesi için şirket logosunu göstermeyi seçmiş olmalısınız. En iyi görünümü elde etmek için saydam bir arka plana sahip bir logo yükleyin.<p><ul><li>En yüksek görüntü boyutu: 400 piksel x 400 piksel</li><li>En büyük dosya boyutu: 750 KB</li><li>Dosya türü: PNG, JPG veya JPEG</li></ul>|

### <a name="brand-image-for-company-portal"></a>Şirket Portalı için marka imajı

Şirket markanızı yansıtan bir marka imajı kullanın. Değişikliklerinizi kaydettikten sonra, yapılandırmalarınızın nasıl görüneceğine bakmak için dikey pencerenin üst kısmındaki Intune Web Portalı’nda **Ayarlarınızın önizlemesini görüntüleyin** öğesini seçebilirsiniz. Marka imajını Intune Web Portalı’nda değil, yalnızca bir iOS cihazında görüntüleyebileceğinizi unutmayın. 

|Alan adı|Daha fazla bilgi|
|---|---|
|**Marka imajınızı karşıya yükleyin**| Bu seçenek, marka imajı görüntülemenizi sağlar. iOS Şirket Portalı'nda kullanıcı profili sayfasında arka plan görüntüsü olarak görünür.<p><ul><li>Önerilen görüntü genişliği: 640 piksel ile 1125 piksel arası</li><li>En yüksek görüntü boyutu: 1,3 MB</li><li>Dosya türü: PNG, JPG veya JPEG</li></ul>|

Doğru bir marka imajı sayesinde şirket markanızı güçlü bir şekilde tanıtarak Şirket Portalı’nda kullanıcı güvenini artırabilirsiniz. Aşağıda, Şirket Portalı için imaj elde etme, seçme ve iyileştirme hakkında bazı ipuçları bulabilirsiniz. 

- Pazarlama veya sanat departmanınıza ulaşın. Bu departmanların elinde zaten onaylanmış birkaç marka imajı olabilir. Departmanlar ayrıca görüntüleri ihtiyaca göre iyileştirme konusunda size yardım edebilir. 

- Yatay ve dikey kompozisyonları değerlendirin. İmajın odak noktasını çevreleyen arka planın yeterli olmasına dikkat edin. İmaj cihaz boyutuna, hizalamasına ve platformuna göre farklı şekillerde kırpılabilir. 

- Sıradan, hazır bir imaj seçmekten kaçının. İmaj, şirketinizin markasını yansıtmalı ve kullanıcılara yakın hissettirmelidir. Elinizde bir imaj yoksa, kullanıcılarınıza hiçbir şey ifade etmeyen sıradan bir görüntü kullanmak yerine hiçbir şey kullanmamak daha iyi olacaktır. 

- Gereksiz meta verileri kaldırın. İmaj dosyası; kamera profili, coğrafi konum, başlık, açıklama gibi meta veriler içerebilir. Kaliteyi korumak ve dosya boyutu sınırını aşmamak için bir görüntü iyileştirme aracını kullanarak bu bilgileri kaldırın. 

Intune'da marka imajı eklendikten veya değiştirildikten sonra son kullanıcıların bu değişikliği iOS cihazlarında görebilmeleri için Şirket Portalı'nın başlangıçta değişikliği algılaması ve ardından marka imajının görüntülenmesi için yeniden başlatılması gerekir. 

### <a name="brand-image-examples"></a>Marka imajı örnekleri

Aşağıdaki görüntüde örnek bir iPad marka imajı gösterilmektedir:

![Örnek iPhone marka imajının ekran görüntüsü](media/company-portal-app/company-portal-app-03.png)

Aşağıdaki görüntüde örnek bir iPhone marka imajı gösterilmektedir:

![Örnek iPad marka imajının ekran görüntüsü](media/company-portal-app/company-portal-app-02.png)

## <a name="windows-company-portal-keyboard-shortcuts"></a>Windows Şirket Portalı klavye kısayolları

Son kullanıcılar, Windows Şirket Portalı’nda klavye kısayollarını (hızlandırıcılar) kullanarak gezinti, uygulama ve cihaz eylemlerini tetikleyebilirler.

Windows Şirket Portalı uygulamasında aşağıdaki kısayollar kullanılabilir.

| Alan | Açıklama | Klavye kısayolu |
|:------------------:|:--------------:|:-----------------:|
| Gezinti menüsü | Gezinti | Alt+M |
|  | Giriş | Alt+H |
|  | Tüm uygulamalar | Alt+A |
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
| Uygulama ayrıntıları | Yükle | Ctrl+I |

Son kullanıcılar, Windows Şirket Portalı uygulamasında kullanılabilen kısayolları da görebilir.

![Windows Şirket Portalı'nda kullanılabilen kısayolların ekran görüntüsü](media/company-portal-app/company-portal-app-01.png)

## <a name="next-steps"></a>Sonraki adımlar

- [Microsoft Intune kullanarak Windows 10 Şirket Portalı uygulamasını el ile ekleme](store-apps-company-portal-app.md)
