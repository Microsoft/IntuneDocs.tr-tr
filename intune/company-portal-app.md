---
title: Şirket Portalı uygulamasını yapılandırma
titleSuffix: Microsoft Intune
description: Intune Şirket Portalı uygulamasına şirkete özgü markalamayı nasıl uygulayabileceğinizi öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/17/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: dec6f258-ee1b-4824-bf66-29053051a1ae
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 435d13fe1d8b159296ee2155a8f49c0ce282ca87
ms.sourcegitcommit: 2ab41ce2c781fc7bd1140a82b4f44d4cd2fc07b1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2019
ms.locfileid: "71305141"
---
# <a name="how-to-configure-the-microsoft-intune-company-portal-app"></a>Microsoft Intune Şirket Portalı uygulamasını yapılandırma

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Microsoft Intune şirket portalı, kullanıcıların şirket verilerine eriştiği ve cihaz kaydetmek, uygulama yüklemek ve BT departmanınızdan yardım için bilgi bulmak gibi genel görevleri gerçekleştirebilecekleri yerdir. Ayrıca, Şirket portalı uygulaması kullanıcının şirket kaynaklarına güvenli bir şekilde erişmesini sağlar. Şirket portalı uygulaması, giriş, uygulamalar, uygulama ayrıntıları, cihazlar ve cihaz ayrıntıları gibi çeşitli farklı sayfalar sağlar. Şirket Portalı içindeki uygulamaları hızlıca bulmak için uygulamalar sayfasındaki uygulamaları filtreleyebilirsiniz.

> [!IMPORTANT]
> Google 'ın Firebase bulut mesajlaşma 'yı (FCM) desteklemek için Android Şirket Portalı uygulamanızı en son sürüme güncelleştirmeniz gerekir. Daha fazla bilgi için bkz. [Android şirket portalı uygulamanızı en son sürüme güncelleştirme](whats-new.md#update-your-android-company-portal-app-to-the-latest-version-).

> [!Tip]
> Şirket Portalı’nı özelleştirdiğinizde, yapılandırmalar hem Şirket Portalı web sitesi hem de Şirket Portalı uygulamaları için geçerli olur. Şirket Portalı'na erişmek isteyen kullanıcılara Intune lisansı atanmış olmalıdır.

Şirket Portalı’nı özelleştirerek, son kullanıcılarınız için tanıdık ve yararlı bir deneyim sağlanmasına yardımcı olabilirsiniz. Bunun için Intune portalında **İstemci uygulamaları** > **Markalama ve özelleştirme**'yi seçip gerekli ayarları yapılandırın.

Bir Kullanıcı Şirket Portalı bir iOS uygulaması yüklerken bir istem alır. Bu durum, iOS uygulaması bir toplu satın alma programı (VPP) ile bağlantılı veya iş kolu (LOB) uygulamasına bağlanan bir App Store 'a bağlandığında oluşur. İstem, kullanıcıların eylemi kabul etmesine veya uygulamanın yönetimine izin veriyor. İstem şirketinizin adını gösterir veya şirketinizin adı kullanılamadığında **Şirket portalı** görüntülenir. 

> [!Note]
> Azure Kamu kullanıyorsanız, bir sorunla ilgili yardım alma sürecini başlattığında bunu nasıl paylaşacağına karar vermesi için son kullanıcıya uygulama günlükleri sunulur. Ancak Azure Kamu kullanmıyorsa, kullanıcı bir sorunla ilgili yardım alma sürecini başlattığında Windows 10 için Şirket Portalı uygulama günlüklerini doğrudan Microsoft'a gönderir. Uygulama günlüklerini Microsoft'a göndermek sorunları gidermeyi ve çözmeyi kolaylaştıracaktır. 

## <a name="company-information-and-privacy-statement"></a>Şirket bilgileri ve gizlilik bildirimi
Şirket adı, Şirket Portalı’nın başlığı olarak görüntülenir. Gizlilik bildirimini, kullanıcı gizlilik bağlantısına tıkladığında görüntülenir.

| Alan adı | Uzunluk üst sınırı | Daha fazla bilgi |
|---|---|---|
|**Şirket adı**| 40 | Bu ad Şirket Portalı'nın başlığı olarak görüntülenir ve Intune kullanıcı deneyiminin her yerinde metin olarak gösterilir. |
| **Gizlilik bildirimi URL'si** |     79     | Kullanıcılar Şirket Portalı’nda gizlilik bağlantılarına tıkladığında görüntülenecek kendi şirket gizlilik bildiriminizi belirtebilirsiniz. `<https://www.contoso.com>` biçiminde geçerli bir URL girmeniz gerekir. |

> [!NOTE]
> Microsoft ve Apple ilkesiyle tutarlı olan her nedenden dolayı hizmetimiz tarafından toplanan herhangi bir veriyi üçüncü taraflardan satmayacağız.

## <a name="support-information"></a>Destek bilgileri
Çalışanınıza Intune'la ilgili sorularında bir başvuru noktası sağlamak için şirketinizin destek bilgilerini girin.

|Alan adı|Uzunluk üst sınırı|Daha fazla bilgi|
|---|---|---|
|**Kişi adı** | 40 | Bu ad, **Yardım ve destek** sayfasında görüntülenir. |
|**Telefon numarası** | 20 | Bu iletişim numarası, çalışanların destek için sizinle iletişim kurmasını sağlamak üzere **Yardım ve destek** sayfasında görüntülenir. |
|**E-posta adresi**| 40 | Bu iletişim adresi **Yardım ve destek** sayfasında görüntülenir. `alias@domainname.com` biçiminde geçerli bir e-posta adresi girmeniz gerekir. |
|**Web sitesinin adı**| 40 | Bu ad destek web sitesi URL'si için görüntülenen kolay addır. Bir destek web sitesi URL 'SI belirtirseniz ve kolay ad yoksa, Şirket Portalı **Yardım ve destek** sayfasında BT Web sitesine gidin görüntülenir. |
|**Web sitesi URL'si**| 150 | Kullanıcılarınızın kullanmasını istediğiniz bir destek web siteniz varsa, URL'sini burada belirtin. URL, `https://www.contoso.com` biçiminde olmalıdır. Bir URL belirtmezseniz, Şirket Portalı **Yardım ve destek** sayfasında destek web sitesi için hiçbir şey gösterilmez. |
| **Ek bilgiler**| 120 | **Yardım ve destek** sayfasında gösterilir. |


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
|**Marka imajınızı karşıya yükleyin**| Bu seçenek, marka imajı görüntülemenizi sağlar. iOS Şirket Portalı'nda kullanıcı profili sayfasında arka plan görüntüsü olarak görünür.<p><ul><li>Önerilen görüntü genişliği: 1125px büyük (en az 650 px olması gerekir)</li><li>En yüksek görüntü boyutu: 1,3 MB</li><li>Dosya türü: PNG, JPG veya JPEG</li></ul>|

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

## <a name="privacy-statement-customization"></a>Gizlilik bildirimi özelleştirmesi

Kuruluşunuzda yönetilen iOS cihazlarında görüntülenen gizlilik bildirimini özelleştirebilirsiniz. Bu ileti, kuruluşunuzun yönetilen iOS cihazlarını göremediği veya üzerinde yapayapabileceği öğeleri listeler.

**Şirket portalı özelleştirme** > **cihaz yönetimi ve gizlilik iletisi**altında şunları yapabilirsiniz:

- Listenin gösterildiği gibi kullanılması için **Varsayılanı** kabul edin veya
- Kuruluşunuzun yönetilen iOS cihazlarını göremediği veya bu cihazlarda yapayapabileceği öğelerin listesini özelleştirmek için **özel** ' i seçin. [Marku](https://daringfireball.net/projects/markdown/) kullanarak madde işaretleri, kalın, italik ve bağlantılar ekleyebilirsiniz.

## <a name="windows-company-portal-keyboard-shortcuts"></a>Windows Şirket Portalı klavye kısayolları

Son kullanıcılar, Windows Şirket Portalı’nda klavye kısayollarını (hızlandırıcılar) kullanarak gezinti, uygulama ve cihaz eylemlerini tetikleyebilirler.

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
| Cihazlar | Kullanılabilir | Ctrl+D |

Son kullanıcılar, Windows Şirket Portalı uygulamasında kullanılabilen kısayolları da görebilir.

![Windows Şirket Portalı'nda kullanılabilen kısayolların ekran görüntüsü](media/company-portal-app/company-portal-app-01.png)

## <a name="user-self-service-device-actions-from-the-company-portal"></a>Şirket Portalı Kullanıcı self servis cihaz eylemleri

Kullanıcılar, Şirket Portalı uygulaması veya Web sitesi aracılığıyla yerel veya uzak cihazlarında eylemler gerçekleştirebilir. Bir kullanıcının gerçekleştirebileceği eylemler cihaz platformu ve yapılandırmasına göre farklılık gösterir. Her durumda, uzak cihaz eylemleri yalnızca cihazın birincil kullanıcısı tarafından gerçekleştirilebilir.
- **Devre dışı bırak** – cihazı Intune yönetiminden kaldırır. Şirket portalı uygulamasında ve Web sitesinde bu, **Kaldır**olarak gösterilir.
- **Silme** – bu eylem bir cihaz sıfırlamayı başlatır. Şirket portalı Web sitesinde bu, **sıfırlama**veya iOS şirket portalı uygulamasında **Fabrika Sıfırlaması** olarak gösterilir.
- **Yeniden Adlandır** – bu eylem, kullanıcının şirket portalı görebileceği cihaz adını değiştirir. Yerel cihaz adını değiştirmez, yalnızca Şirket Portalı listelemez.
- **Eşitleme** – bu eylem, Intune hizmeti ile bir cihaz iade işlemini başlatır. Bu, Şirket Portalı **denetim durumunu** gösterir.
- **Uzaktan kilitleme** – bu, cihazın kilidini açmak için PIN gerektiren cihazı kilitler.
- **Geçiş kodunu Sıfırla** – bu eylem, cihaz geçiş kodunu sıfırlamak için kullanılır. İOS cihazlarında geçiş kodu kaldırılır ve son kullanıcının ayarlar ' da yeni bir kod girmesi gerekecektir. Desteklenen Android cihazlarda Intune tarafından yeni bir geçiş kodu oluşturulur ve geçici olarak Şirket Portalı görüntülenir.
- **Anahtar kurtarma** – bu eylem, şifrelenmiş cihazların şifreleme anahtarını kurtarmak için kullanılır.

### <a name="self-service-actions"></a>Self Servis eylemleri

Bazı platformlar ve Konfigürasyonlar self servis cihaz eylemlerine izin vermez. Aşağıdaki tabloda self servis eylemleri hakkında daha ayrıntılı bilgi verilmektedir:

|     Platform    |    Devre dışı bırakma    |    Silme     |    Yeniden Adlandır<sup>(4)</sup>    |    Eşitle    |    Uzaktan Kilitleme    |    Geçiş kodunu Sıfırla    |    Anahtar Kurtarma    |
|------------------------|--------------------|--------------------|-----------------|-----------------|--------------------------|--------------------------|--------------------|
|    Windows 10<sup>(3)</sup>    |    Kullanılabilir<sup>(1)</sup>    |    Kullanılabilir    |    Kullanılabilir    |    Kullanılabilir    |    Yalnızca Windows Phone    |    Yalnızca Windows Phone    |    NA    |
|    iOS<sup>(3)</sup>    |    Kullanılabilir    |    Kullanılabilir    |    Kullanılabilir    |    Kullanılabilir    |    Kullanılabilir    |    Kullanılabilir    |    NA    |
|    MacOS<sup>(3)</sup><sup>(5)</sup>    |    Kullanılabilir    |    NA    |    Kullanılabilir    |    Kullanılabilir    |    Kullanılabilir    |    NA    |    Kullanılabilir<sup>(2)</sup>    |
|    Android<sup>(3)</sup>    |    Kullanılabilir<sup>(7)</sup>    |    Kullanılabilir<sup>(7)</sup>    |    Kullanılabilir    |    Kullanılabilir    |    Kullanılabilir    |    Kullanılabilir<sup>(6)</sup>    |    NA    |


<sup>(1)</sup> devre dışı bırakma, Azure AD 'ye katılmış Windows cihazlarında her zaman engellenir.<br>
<sup>(2)</sup> MacOS Için anahtar kurtarma yalnızca Web portalı aracılığıyla kullanılabilir.<br>
<sup>(3)</sup> bir cihaz kayıt yöneticisi kaydı kullanılıyorsa tüm uzak eylemler devre dışı bırakılır.<br>
<sup>(4)</sup> yeniden adlandırma yalnızca cihaz adını cihazda değil şirket portalı uygulamasında veya Web sitesinde değiştirir.<br>
<sup>(5)</sup> MacOS cihazlarında uzaktan silme kullanılamaz.<br>
<sup>(6)</sup> geçiş kodu sıfırlama bazı Android ve Android kurumsal yapılandırmalarında desteklenmez. Daha fazla bilgi için bkz. [Intune 'da cihaz geçiş kodunu sıfırlama veya kaldırma](device-passcode-reset.md).<br>
<sup>(7)</sup> devre dışı bırakma ve Temizleme, Android kurumsal cihaz sahibi SENARYOLARıNDA (Cope, Cobo, cosu) kullanılamaz.<br> 

## <a name="next-steps"></a>Sonraki adımlar

- [Microsoft Intune kullanarak Windows 10 Şirket Portalı uygulamasını el ile ekleme](store-apps-company-portal-app.md)
