---
title: Şirket Portalı uygulamasını yapılandırma
titleSuffix: Microsoft Intune
description: Intune Şirket Portalı uygulamasına şirkete özgü markalamayı nasıl uygulayabileceğinizi öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: dec6f258-ee1b-4824-bf66-29053051a1ae
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6c016dd8a1d8a21e3ac96ab8637e26a029b18dbc
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77511812"
---
# <a name="how-to-configure-the-microsoft-intune-company-portal-app"></a>Microsoft Intune Şirket Portalı uygulamasını yapılandırma

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Microsoft Intune şirket portalı, kullanıcıların şirket verilerine eriştiği ve cihaz kaydetmek, uygulama yüklemek ve BT departmanınızdan yardım için bilgi bulmak gibi genel görevleri gerçekleştirebilecekleri yerdir. Ayrıca, Şirket portalı uygulaması kullanıcının şirket kaynaklarına güvenli bir şekilde erişmesini sağlar. Şirket portalı uygulaması, giriş, uygulamalar, uygulama ayrıntıları, cihazlar ve cihaz ayrıntıları gibi çeşitli farklı sayfalar sağlar. Şirket Portalı içindeki uygulamaları hızlıca bulmak için uygulamalar sayfasındaki uygulamaları filtreleyebilirsiniz.

> [!IMPORTANT]
> Google 'ın Firebase bulut mesajlaşma 'yı (FCM) desteklemek için Android Şirket Portalı uygulamanızı en son sürüme güncelleştirmeniz gerekir.  

> [!Tip]
> Şirket Portalı’nı özelleştirdiğinizde, yapılandırmalar hem Şirket Portalı web sitesi hem de Şirket Portalı uygulamaları için geçerli olur. Şirket Portalı'na erişmek isteyen kullanıcılara Intune lisansı atanmış olmalıdır.

Şirket Portalı’nı özelleştirerek, son kullanıcılarınız için tanıdık ve yararlı bir deneyim sağlanmasına yardımcı olabilirsiniz. Bunu yapmak için, Intune portalında **uygulamalar** > **marka ve özelleştirme**' yı seçin ve gerekli ayarları yapılandırın.

Bir Kullanıcı Şirket Portalı bir iOS/ıpados uygulaması yüklerken bir istem alır. Bu durum, iOS/ıpados uygulamasının bir toplu satın alma programı (VPP) ile bağlantılı veya iş kolu (LOB) uygulamasına bağlı olan App Store 'a bağlanması durumunda meydana gelir. İstem, kullanıcıların eylemi kabul etmesine veya uygulamanın yönetimine izin veriyor. İstem şirketinizin adını gösterir veya şirketinizin adı kullanılamadığında **Şirket portalı** görüntülenir. 

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
|**Şirket logonuzu karşıya yükleyin**|Size ait Şirket Portalı’nda görüntülenmek üzere şirket logonuzu yükleyebilirsiniz. En yüksek kontrast düzeyini sağlamak için metin renginin otomatik olarak seçildiğini unutmayın. En iyi görünümü elde etmek için saydam bir arka plana sahip bir logo yükleyin.<p><ul><li>En büyük görüntü boyutu: 400 piksel x 400 piksel</li><li>En büyük dosya boyutu: 750 KB</li><li>Dosya türü: PNG, JPG veya JPEG</li></ul>|

Logo yüklendikten sonra önizleme alanında tema rengiyle logo görüntülenir. Şirketinizin adını görüntülemeyi seçerseniz bu ad, Şirket Portalı’nda siyah veya beyaz renkte görüntülenir. Tema renginizle en yüksek kontrastı sağlayan renk otomatik olarak seçilir. Ekrandaki önizleme alanında şirketinizin adı görüntülenmez. 

### <a name="logo-to-use-on-white-or-light-backgrounds"></a>Beyaz veya açık renk arka planda kullanılacak logo
Beyaz veya açık renk arka planlarda en iyi görünecek logoyu seçin.

|Alan adı|Daha fazla bilgi|
|---|---|
|**Logonuzu karşıya yükleyin**| Bu seçeneğin kullanılabilmesi için şirket logosunu göstermeyi seçmiş olmalısınız. En iyi görünümü elde etmek için saydam bir arka plana sahip bir logo yükleyin.<p><ul><li>En büyük görüntü boyutu: 400 piksel x 400 piksel</li><li>En büyük dosya boyutu: 750 KB</li><li>Dosya türü: PNG, JPG veya JPEG</li></ul>|

### <a name="brand-image-for-company-portal"></a>Şirket Portalı için marka imajı

Şirket markanızı yansıtan bir marka imajı kullanın. Değişikliklerinizi kaydettikten sonra, yapılandırımlarınızın nasıl görüneceğine bakmak için bölmenin en üstündeki Intune web portalında **ayarlarınızı önizleyin** ' i seçebilirsiniz. Yalnızca bir iOS/ıpados cihazında bulunan marka görüntüsünü, Intune Web Portalı ' nı görüntüleyebileceğinizi unutmayın. 

|Alan adı|Daha fazla bilgi|
|---|---|
|**Marka imajınızı karşıya yükleyin**| Bu seçenek, marka imajı görüntülemenizi sağlar. İOS/ıpados Şirket Portalı, kullanıcının profil sayfasında bir arka plan görüntüsü olarak gösterilir.<p><ul><li>Önerilen Görüntü genişliği: 1125mb 'den büyük (en az 650 piksel olması gerekir)</li><li>En yüksek görüntü boyutu: 1,3 MB</li><li>Dosya türü: PNG, JPG veya JPEG</li></ul>|

Doğru bir marka imajı sayesinde şirket markanızı güçlü bir şekilde tanıtarak Şirket Portalı’nda kullanıcı güvenini artırabilirsiniz. Aşağıda, Şirket Portalı için imaj elde etme, seçme ve iyileştirme hakkında bazı ipuçları bulabilirsiniz. 

- Pazarlama veya sanat departmanınıza ulaşın. Bu departmanların elinde zaten onaylanmış birkaç marka imajı olabilir. Departmanlar ayrıca görüntüleri ihtiyaca göre iyileştirme konusunda size yardım edebilir. 

- Yatay ve dikey kompozisyonları değerlendirin. İmajın odak noktasını çevreleyen arka planın yeterli olmasına dikkat edin. İmaj cihaz boyutuna, hizalamasına ve platformuna göre farklı şekillerde kırpılabilir. 

- Sıradan, hazır bir imaj seçmekten kaçının. İmaj, şirketinizin markasını yansıtmalı ve kullanıcılara yakın hissettirmelidir. Elinizde bir imaj yoksa, kullanıcılarınıza hiçbir şey ifade etmeyen sıradan bir görüntü kullanmak yerine hiçbir şey kullanmamak daha iyi olacaktır. 

- Gereksiz meta verileri kaldırın. İmaj dosyası; kamera profili, coğrafi konum, başlık, açıklama gibi meta veriler içerebilir. Kaliteyi korumak ve dosya boyutu sınırını aşmamak için bir görüntü iyileştirme aracını kullanarak bu bilgileri kaldırın. 

Intune 'da marka resmi eklendikten veya değiştirildikten sonra, Son Kullanıcı iOS/ıpados cihazlarındaki değişikliği, Şirket Portalı başlangıç sırasında değişiklik yapana kadar görmeyebilir ve ardından marka görüntüsünü görüntülemek için yeniden başlatılmıştır. 

### <a name="brand-image-examples"></a>Marka imajı örnekleri

Aşağıdaki görüntüde örnek bir iPad marka imajı gösterilmektedir:

![Örnek iPhone marka imajının ekran görüntüsü](./media/company-portal-app/company-portal-app-03.png)

Aşağıdaki görüntüde örnek bir iPhone marka imajı gösterilmektedir:

![Örnek iPad marka imajının ekran görüntüsü](./media/company-portal-app/company-portal-app-02.png)

## <a name="privacy-statement-customization"></a>Gizlilik bildirimi özelleştirmesi

Kuruluşunuzda yönetilen iOS/ıpados cihazlarında görüntülenen gizlilik bildirimini özelleştirebilirsiniz. Bu ileti, kuruluşunuzun yönetilen iOS/ıpados cihazlarını göremediği veya üzerinde yapacakları öğeleri listeler.

**Şirket portalı özelleştirme** > **cihaz yönetimi ve gizlilik iletisi**altında şunları yapabilirsiniz:

- Listenin gösterildiği gibi kullanılması için **Varsayılanı** kabul edin veya
- Kuruluşunuzun yönetilen iOS/ıpados cihazlarını göremediği veya bu cihazlarda yapacakları öğelerin listesini özelleştirmek için **özel** ' i seçin. [Marku](https://daringfireball.net/projects/markdown/) kullanarak madde işaretleri, kalın, italik ve bağlantılar ekleyebilirsiniz.

## <a name="company-portal-derived-credentials-for-ios-devices"></a>İOS cihazları için türetilmiş kimlik bilgilerini Şirket Portalı
Intune, kişisel kimlik doğrulama (PıV) ve ortak erişim kartı (CAC) ile birlikte gelen kimlik bilgilerini, DıŞA geçmiş kimlik bilgisi sağlayıcıları, Entrust Datacard ve ıntercede ile iş ortaklığı için destekler. Son kullanıcılar, Şirket Portalı uygulamasındaki kimliklerini doğrulamak için iOS/ıpados cihazının kayıt sonrası ek adımlara geçer. Türetilmiş kimlik bilgileri, önce kiracınız için bir kimlik bilgisi sağlayıcısı ayarlayıp, ardından kullanıcılara veya cihazlara türetilmiş kimlik bilgilerini kullanan bir profili hedefleyerek kullanıcılara etkinleştirilir.

> [!NOTE]
> Kullanıcı, Intune aracılığıyla belirttiğiniz bağlantıya bağlı olarak türetilmiş kimlik bilgileri hakkındaki yönergeleri görür.

İOS/ıpados cihazlarının türetilmiş kimlik bilgileri hakkında daha fazla bilgi için bkz. [Microsoft Intune türetilmiş kimlik bilgilerini kullanma](~/protect/derived-credentials.md).

## <a name="dark-mode-for-ios-company-portal"></a>İOS Şirket Portalı için koyu mod

İOS Şirket Portalı için koyu mod kullanılabilir. Kullanıcılar şirket uygulamalarını indirebilir, cihazlarını yönetebilir ve cihaz ayarlarına bağlı olarak tercih ettikleri renk düzeninde BT desteği alabilir. İOS Şirket Portalı, son kullanıcının cihaz ayarlarını koyu veya hafif modda otomatik olarak eşleştirecektir. 

## <a name="windows-company-portal-keyboard-shortcuts"></a>Windows Şirket Portalı klavye kısayolları

Son kullanıcılar, Windows Şirket Portalı’nda klavye kısayollarını (hızlandırıcılar) kullanarak gezinti, uygulama ve cihaz eylemlerini tetikleyebilirler.

Windows Şirket Portalı uygulamasında aşağıdaki kısayollar kullanılabilir.

| Alan | Açıklama | Klavye kısayolu |
|:------------------:|:--------------:|:-----------------:|
| Gezinti menüsü | Gezinti | Alt + a |
|  | Giriş | Alt + H |
|  | Tüm uygulamalar | Alt + A |
|  | Yüklenen uygulamalar | Alt+I |
|  | Geri bildirim gönder | Alt + F |
|  | Profilim | Alt + U |
|  | Ayarlar | Alt + T |
| Giriş - Cihaz kutucuğu | Yeniden Adlandır | F2 |
|  | Kaldır | Ctrl+D veya Delete |
|  | Erişimi denetle | Ctrl+M veya F9 |
| Cihaz ayrıntıları | Yeniden Adlandır | F2 |
|  | Kaldır | Ctrl+D veya Delete |
|  | Erişimi denetle | Ctrl+M veya F9 |
| Uygulama ayrıntıları | Yükle | Ctrl+I |
| Cihazlar | Kullanılabilir | Ctrl+D |

Son kullanıcılar, Windows Şirket Portalı uygulamasında kullanılabilen kısayolları da görebilir.

![Windows Şirket Portalı'nda kullanılabilen kısayolların ekran görüntüsü](./media/company-portal-app/company-portal-app-01.png)

## <a name="user-self-service-device-actions-from-the-company-portal"></a>Şirket Portalı Kullanıcı self servis cihaz eylemleri

Kullanıcılar, Şirket Portalı uygulaması veya Web sitesi aracılığıyla yerel veya uzak cihazlarında eylemler gerçekleştirebilir. Bir kullanıcının gerçekleştirebileceği eylemler cihaz platformu ve yapılandırmasına göre farklılık gösterir. Her durumda, uzak cihaz eylemleri yalnızca cihazın birincil kullanıcısı tarafından gerçekleştirilebilir.
- **Devre dışı bırak** – cihazı Intune yönetiminden kaldırır. Şirket portalı uygulamasında ve Web sitesinde bu, **Kaldır**olarak gösterilir.
- **Silme** – bu eylem bir cihaz sıfırlamayı başlatır. Şirket portalı Web sitesinde bu, **sıfırlama**veya iOS şirket portalı uygulamasında **Fabrika Sıfırlaması** olarak gösterilir.
- **Yeniden Adlandır** – bu eylem, kullanıcının şirket portalı görebileceği cihaz adını değiştirir. Yerel cihaz adını değiştirmez, yalnızca Şirket Portalı listelemez.
- **Eşitleme** – bu eylem, Intune hizmeti ile bir cihaz iade işlemini başlatır. Bu, Şirket Portalı **denetim durumunu** gösterir.
- **Uzaktan kilitleme** – bu, cihazın kilidini açmak için PIN gerektiren cihazı kilitler.
- **Geçiş kodunu Sıfırla** – bu eylem, cihaz geçiş kodunu sıfırlamak için kullanılır. İOS/ıpados cihazlarında geçiş kodu kaldırılır ve son kullanıcının ayarlar ' da yeni bir kod girmesi gerekecektir. Desteklenen Android cihazlarda Intune tarafından yeni bir geçiş kodu oluşturulur ve geçici olarak Şirket Portalı görüntülenir.
- **Anahtar kurtarma** – bu eylem, Şirket portalı Web sitesinden şifrelenmiş MacOS cihazları için kişisel kurtarma anahtarını kurtarmak üzere kullanılır. 

### <a name="self-service-actions"></a>Self Servis eylemleri

Bazı platformlar ve Konfigürasyonlar self servis cihaz eylemlerine izin vermez. Aşağıdaki tabloda self servis eylemleri hakkında daha ayrıntılı bilgi verilmektedir:

|  | Windows 10<sup>(3)</sup> | iOS/ıpados<sup>(3)</sup> | MacOS<sup>(3)</sup> | Android<sup>(3)</sup> |
|----------------------|--------------------------|-------------------|-----------------------------------|-------------------------|
| Devre dışı bırakma | Kullanılabilir<sup>(1)</sup> | Kullanılabilir | Kullanılabilir | Kullanılabilir<sup>(7)</sup> |
| Silme | Kullanılabilir | Kullanılabilir<sup>(5)</sup> | Yok | Kullanılabilir<sup>(7)</sup> |
| Yeniden Adlandır<sup>(4)</sup> | Kullanılabilir | Kullanılabilir | Kullanılabilir | Kullanılabilir |
| Eşitle | Kullanılabilir | Kullanılabilir | Kullanılabilir | Kullanılabilir |
| Uzaktan Kilitleme | Yalnızca Windows Phone | Kullanılabilir | Kullanılabilir | Kullanılabilir |
| Geçiş Kodunu Sıfırla | Yalnızca Windows Phone | Kullanılabilir<sup>(8)</sup> | Yok | Kullanılabilir<sup>(6)</sup> |
| Anahtar kurtarma | Yok | Yok | Kullanılabilir<sup>(2)</sup> | Yok |

<sup>(1)</sup> **devre dışı BıRAKMA** , Azure AD 'ye katılmış Windows cihazlarında her zaman engellenir.<br>
<sup>(2)</sup> MacOS Için **anahtar kurtarma** yalnızca Web portalı aracılığıyla kullanılabilir.<br>
<sup>(3)</sup> bir cihaz kayıt yöneticisi kaydı kullanılıyorsa tüm uzak eylemler devre dışı bırakılır.<br>
<sup>(4)</sup> **yeniden adlandırma** yalnızca cihaz adını cihazda değil şirket portalı uygulamasında veya Web portalında değiştirir.<br>
<sup>(5)</sup> Kullanıcı kayıtlı iOS cihazlarında **silme** kullanılamıyor.<br>
<sup>(6)</sup> bazı Android ve Android kurumsal yapılandırmalarında, **geçiş kodu sıfırlama** işlemi desteklenmez. Daha fazla bilgi için bkz. [Intune 'da cihaz geçiş kodunu sıfırlama veya kaldırma](../remote-actions/device-passcode-reset.md).<br>
<sup>(7)</sup> **devre dışı bırakma** ve **Temizleme** , ANDROID kurumsal cihaz sahibi senaryolarında (Cope, Cobo, cosu) kullanılamaz.<br> 
<sup>(8)</sup> Kullanıcı tarafından kaydedilen IOS cihazlarında **geçiş kodunu sıfırlama** işlemi desteklenmez.

## <a name="next-steps"></a>Sonraki adımlar

- [Microsoft Intune kullanarak Windows 10 Şirket Portalı uygulamasını el ile ekleme](company-portal-app.md)
