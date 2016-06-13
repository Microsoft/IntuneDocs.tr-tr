---
# required metadata

title: İlkelerle cihazlarınızda ayarları ve özellikleri yönetme | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 09bae0b9-4f79-4658-8ca1-a71ab992c1b2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme
Microsoft Intune **ilkeleri**, mobil cihazlar ve bilgisayarlarda özellikleri denetleyen ayar gruplarıdır. İlkeleri önerilen veya özelleştirilmiş ayarlar içeren şablonlar kullanarak oluşturur ve ardından cihaz veya kullanıcı gruplarına dağıtırsınız.

## Hangi ilke türlerini kullanabilirsiniz?

Intune ilkeleri aşağıdaki kategorilere ayrılır. Kullandığınız kategori, ilkeyi oluşturma ve dağıtma şeklinizi etkiler.


- **Yapılandırma ilkeleri:** Bunlar yaygın olarak, cihazlarınızdaki güvenlik ayarlarını ve özelliklerini yönetmek için kullanılır. Bu ilkelerin nasıl oluşturulduğunu ve dağıtıldığını öğrenmek ve kullanılabilir ayarları keşfetmek için bu konu başlığı altında verilen bilgileri kullanın.
- **Cihaz uyumluluk ilkeleri:** Bunlar, bir cihazın koşullu erişim ilkeleriyle uyumlu kabul edilmesi için uyması gereken kuralları ve ayarları tanımlar. Uyumluluk ilkelerini ayrıca, koşullu erişimden bağımsız olarak cihazlardaki uyumluluğu izlemek ve sorunları gidermek için de kullanabilirsiniz.
Ayrıntılar için bkz. [Microsoft Intune’da cihaz uyumluluk ilkeleri](introduction-to-device-compliance-policies-in-microsoft-intune.md).
- **Koşullu erişim ilkeleri:** Bu ilkeler, belirttiğiniz koşullara bağlı olarak e-posta ve diğer hizmetleri güvenli hale getirmenize yardımcı olur.
Ayrıntılar için bkz. [Microsoft Intune ile e-posta ve O365 hizmetlerine erişimi kısıtlama](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).
- **Şirket cihaz kaydı ilkeleri:** Şirket cihaz kaydı ilkeleri hakkında daha fazla bilgi için bkz. [Microsoft Intune ile iOS ve Mac yönetimini ayarlama](set-up-ios-and-mac-management-with-microsoft-intune.md).
- **Kaynak erişim ilkeleri:** Bu ilke grubu, kullanıcılarınızın nerede olurlarsa olsunlar, işlerini başarıyla gerçekleştirmek için ihtiyaç duydukları dosyalara ve kaynaklara erişim kazanmasına yardımcı olmak için birlikte çalışır.
Ayrıntılar için, bkz. [Microsoft Intune ile şirket kaynaklarına erişimi etkinleştirme](enable-access-to-company-resources-with-microsoft-intune.md).


Intune ilkelerinin tam listesi için bkz. [Microsoft Intune ilke başvurusu](microsoft-intune-policy-reference.md).




## Yapılandırma ilkesi oluşturma

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com/) **İlke** &gt; **Yapılandırma İlkeleri** &gt; **Ekle**’ye tıklayın.

2.  İstediğiniz ilkeyi seçin, ilke için önerilen ayarları (varsa; bu ayarları daha sonra değiştirebilirsiniz) kullanmayı veya kendi ayarlarınızla özel bir ilke oluşturmayı seçin.

    > [!TIP] Doğru ilkeyi seçerken yardım almak için bkz. [Microsoft Intune ilke başvurusu](microsoft-intune-policy-reference.md).

3.  Hazır olduğunuzda **İlke Oluştur**’a tıklayın.

4.   **İlke Oluştur** ekranında ilke için bir ad ve isteğe bağlı bir açıklama yapılandırın.

5.  Gerekli ilke ayarlarını yapılandırın, ardından **İlkeyi Kaydet**’e tıklayın.

    İlke ayarlarından herhangi birinde yardıma gerek duyarsanız, aşağıdaki listeden ilkenizin türünü seçin:

    - [iOS cihazları için ayarlar](ios-policy-settings-in-microsoft-intune.md)
    - [Android cihazları için ayarlar](android-policy-settings-in-microsoft-intune.md)
    - [Windows 8 ve Windows 8.1 cihazları için ayarlar](windows-configuration-policy-settings-in-microsoft-intune.md)
    - [Windows Phone 8.1 cihazları için ayarlar](windows-phone-8-1-policy-settings-in-microsoft-intune.md)
    - [Windows 10 masaüstü bilgisayar ve mobil cihazları için ayarlar](windows-10-policy-settings-in-microsoft-intune.md)
    - [Windows Team cihazları için ayarlar](windows-team-configuration-policy-settings-in-microsoft-intune.md)
    - [Windows sürüm yükseltme için ayarlar](edition-upgrade-policy-settings-in-microsoft-intune.md)
    - [Mac OS X cihazları için ayarlar](mac-os-x-policy-settings-in-microsoft-intune.md)
    - [Exchange ActiveSync için ayarlar](exchange-activesync-policy-settings-in-microsoft-intune.md)
    - [Hüküm ve koşullar ilkesi için ayarlar](terms-and-condition-policy-settings-in-microsoft-intune.md)
    - [Mobil cihazlar için genel ayarlar (eski)](mobile-device-security-policy-settings-in-microsoft-intune.md)

4.  Onay iletişim kutusunda, ilkeyi hemen dağıtmak için **Evet** 'e veya ilkeyi dağıtmadan oluşturmak için **Hayır** 'a tıklayın.

 **İlke** çalışma alanından her ilke türünün bölümlerine göz atarak yeni ilkeyi görüntüleyebilir ve düzenleyebilirsiniz.

Önerilen ayarları kullanan bir ilke oluşturduğunuzda, yeni ilkenin adı şablon adı, tarih ve saatin bir birleşimidir. İlkeyi düzenlediğinizde, ad düzenlemenin tarih ve saatiyle güncelleştirilir.

Artık bir ilke oluşturduğunuza göre, genellikle ilkeyi bir veya daha fazla kullanıcı ya da cihaz grubuna dağıtmak istersiniz.

> [!TIP]
> Tüm ilke türlerini dağıtmazsınız. Örneğin, mobil uygulama yönetim ilkesi dağıtılmaz. Bunun yerine, bu ilke türü bir uygulamayla ilişkilendirilir ve bu uygulamayı dağıtırsınız.

## Yapılandırma ilkesini dağıtma

1.   **İlke** çalışma alanında, dağıtmak istediğiniz ilkeyi seçin ve ardından **Dağıtımı Yönet**’e tıklayın.

2.   **Dağıtımı Yönet** iletişim kutusunda:

    -   **İlkeyi dağıtmak için** - İlkeyi dağıtmak istediğiniz bir veya daha fazla grup seçin ve ardından **Ekle** &gt; **Tamam**'a tıklayın.

    -   **Dağıtmadan iletişim kutusunu kapatmak için** - **İptal**'e tıklayın.

Dağıtılan bir ilkeyi seçtiğinizde, ilkeler listesinin alt bölümünde dağıtım hakkında daha fazla bilgi görüntüleyebilirsiniz.

## İlkeleri yönetme

1.   [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com/) **İlke**'ye tıklayın ve ardından yönetmek istediğiniz ilkeye giderek bu ilkeyi seçin.

2.  Aşağıdaki eylemlerden birini seçin:

- **Düzenle** - Değişiklik yapmanızı sağlamak için seçili ilkenin özelliklerini açar.
- **Sil** - Seçili ilkeyi siler.<br>Bir ilkeyi sildiğinizde, dağıtıldığı tüm gruplardan kaldırılır.
- **Dağıtımı Yönet** - İlkeyi dağıtmak istediğiniz grubu seçin ve **Ekle**'ye tıklayın.

## Intune ilkeleri için görevler

### Cihazınızdaki ilkeleri yenileyerek bunların güncelliğinden emin olmak için (yalnızca Intune istemci yazılımını çalıştıran Windows bilgisayarları için geçerlidir)

1.   [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com/), **Gruplar**'a tıklayın ve bir cihaz grubu seçin.

2.  İlkeleri yenilemek istediğiniz cihazları seçin ve ardından **Uzak Görevler** &gt; **İlkeleri Yenile**'ye tıklayın.

3.  Görev durumunu denetlemek için, Intune yönetim konsolunun sağ alt köşesinde **Uzak Görevler**'e tıklayın.

## Intune ilkeleri hakkında sık sorulan sorular

### İlke veya uygulamalar dağıtıldıktan sonra mobil cihazların bunları alması ne kadar sürer?
Bir ilke veya uygulama dağıtıldığında, Intune tarafından cihaza hemen Intune hizmetinde giriş yapılması gerektiği konusunda bildirim gönderilmeye başlanır. Bu işlem genellikle 5 dakikadan daha kısa sürer.

Bir cihaz ilk bildirim gönderildikten sonra ilkeyi almak üzere giriş yapmazsa 3 deneme daha yapılır.  Cihaz çevrimdışıysa (örneğin, kapalıysa veya bir ağa bağlı değilse) bildirimleri almayabilir.

Bu durumda cihaz, ilkeyi bir sonraki zamanlanmış Intune hizmeti girişinde aşağıdaki gibi alır:

- iOS - 6 saatte bir
- Android - 8 saate bir
- Windows Phone - 8 saatte bir
- Kayıtlı Windows RT cihazları - 24 saatte bir
- Cihaz olarak kaydedilen Windows 8.1 ve Windows 10 bilgisayarları - 8 saatte bir

Cihaz daha yeni kaydedilmişse, giriş sıklığı aşağıda gösterildiği gibi daha sık olacaktır:

- iOS - 6 saat boyunca 15 dakikada bir, daha sonra 6 saatte bir
- Android - 15 dakika boyunca 3 dakikada bir, sonraki 2 saat boyunca 15 dakikada bir ve daha sonra 8 saatte bir
- Windows Phone - 15 dakika boyunca 5 dakikada bir, sonraki 2 saat boyunca 15 dakikada bir ve daha sonra 8 saatte bir
- Cihaz olarak kaydedilen Windows bilgisayarları - 30 dakika boyunca 3 dakikada bir, daha sonra 24 saatte bir

Ayrıca, kullanıcılar ilkeyi istedikleri zaman denetlemek için Şirket Portalı uygulamasını başlatıp cihazı eşitleyebilir.

### Hangi eylemler Intune tarafından bir cihaza anında bildirim gönderilmesine neden olur?
Cihazlar Intune hizmetine giriş yapmaları gerektiğini söyleyen bir bildirim aldığında veya yukarıdaki tabloda gösterilen düzenli zamanlanmış giriş zamanlarında hizmete giriş yapar.  Temizleme, kilitleme, geçiş kodu sıfırlama, uygulama dağıtma, profil dağıtma (WiFi, VPN, e-posta, vb.) veya ilke dağıtma gibi bir eylemle özel olarak bir cihazı veya kullanıcıyı hedeflediğinizde, Intune hemen, bu güncelleştirmeleri almak için Intune hizmetine giriş yapması gerektiğini cihaza bildirmeye çalışır.

Şirket portalındaki kişi bilgilerinin düzeltilmesi gibi diğer değişiklikler, cihazlara anında bildirim gönderilmesine neden olmaz.

> [!TIP]
> Bir Android cihazına ayarları içeren bir ilke dağıtıldığında kullanıcıdan ilkeye uymak için işlem yapması istenir. Kullanıcılar bu işlemi yapana veya cihaz yeniden başlatılana kadar yeni ilke ayarları etkili olmaz.

### Aynı kullanıcı veya cihaza birden çok ilke dağıtılıyorsa hangi ayarların uygulanacağını nasıl bilebilirim?
Aynı kullanıcı veya cihaza iki veya daha fazla ilke dağıtıldığında, hangi ayarın uygulanacağını belirleyen değerlendirmenin her bir düzeyinde yapıldığını bilmeniz önemlidir.

-   Uyumluluk ilkesi ayarları, her zaman yapılandırma ilkesi ayarlarından önceliklidir

-   Farklı bir uyumluluk ilkesindeki aynı ayarla karşılaştırılarak değerlendirildiğinde, en kısıtlayıcı uyumluluk ilkesi ayarı uygulanır

-   Farklı bir yapılandırma ilkesindeki aynı ayarla karşılaştırılarak değerlendirildiğinde, en kısıtlayıcı yapılandırma ilkesi ayarı uygulanır

### Mobil uygulama yönetimi (MAM) ilkeleri birbiriyle çakıştığında ne olur? Uygulamaya hangisi uygulanır?
Çakışma değerleri, bir mobil uygulama yönetim ilkesinde sayı giriş alanları (sıfırlamadan önce PIN denemesi sayısı gibi) dışında en kısıtlayıcı ayarlardır.  Sayı giriş alanları, konsolda önerilen ayarlar seçeneğini kullanarak bir MAM ilkesi oluşturduğunuzda alacağı değerlerle aynı değerlere ayarlanır.

İki ilke ayarı aynıysa çakışmalar oluşur.  Örneğin, kopyala/yapıştır ayarı dışında birbirinin aynı olan iki MAM ilkesi yapılandırdığınızı düşünün.  Bu senaryoda, kopyala/yapıştır ayarı en kısıtlayıcı değer olarak ayarlanır, ancak ayarların geri kalanı yapılandırıldığı gibi uygulanır.

Bir ilkenin uygulamaya dağıtılıp geçerli olmasından sonra ikinci bir ilke dağıtılırsa, önce dağıtılan ilke öncelikli olur ve geçerli kalırken ikinci ilke çakışmada görünür. Bununla birlikte, ikisi de aynı anda uygulandıysa, yani önce uygulanan bir ilke yoksa ikisi de çakışmada olur ve tüm çakışmalı ayarlar en kısıtlayıcı değerlere ayarlanır.

### iOS özel ilkeleri çakışırsa ne olur?
Intune, Apple yapılandırma dosyalarının veya özel OMA URI ilkesinin yükünü değerlendirmez; yalnızca bir teslim mekanizması olarak görev yapar.

Bu nedenle, özel bir ilke dağıttığınızda yapılandırılan ayarların uyumluluk ve yapılandırma ilkeleriyle veya diğer özel ilkelerle çakışmadığından emin olun. Çakışan ayarlara sahip bir özel ilke olması durumunda, ayarların hangi sırayla uygulandığı rastgele belirlenir.

### Bir ilke silindiğinde veya artık geçerli olmadığında ne olur?
Bir ilkeyi sildiğinizde veya bir cihazı ilkenin dağıtıldığı bir gruptan kaldırdığınızda, ilke ve ayarlar aşağıdaki tablolara göre cihazdan kaldırılır:

#### Kayıtlı cihazlar

- Wi-Fi, VPN, sertifika ve e-posta profilleri - Bu profiller tüm desteklenen kayıtlı cihazlardan kaldırılır.
- Tüm diğer ilke türleri
    - **Windows ve Android cihazları** - Ayarlar cihazdan kaldırılmaz.
    - **Windows Phone 8.1 cihazları** - Aşağıdaki ayarlar kaldırılır:
        - Mobil cihazların kilidini açmak için bir parola gerektir
        - Basit parolalara izin ver
        - Minimum parola uzunluğu
        - Gerekli parola türü
        - Parola geçerlilik süresi (gün)
        - Parola geçmişini anımsa
        - Cihaz temizlenmeden önce izin verilen yinelenen oturum açma hatası sayısı
        - Parola gerekmeden önce etkin olmama süresi (dakika)
        - Gerekli parola türü – minimum karakter kümesi sayısı
        - Kameraya izin ver
        - Cihazda şifrelemeyi gerektir
        - Çıkarılabilir depolama birimine izin ver
        - Web tarayıcısına izin ver
        - Uygulama depolamaya izin ver
        - Ekran yakalamaya izin ver
        - Coğrafi konuma izin ver
        - Microsoft Hesabına izin ver
        - Kopyalama ve yapıştırmaya izin ver
        - Wi-Fi İnternet paylaşımına izin ver
        - Ücretsiz Wi-Fi etkin noktalarına otomatik olarak bağlanmaya izin ver
        - Wi-Fi etkin noktası bildirimine izin ver
        - Fabrika sıfırlamasına izin ver
        - Bluetooth'a izin ver
        - NFC'ye izin ver
        - Wi-Fi'a izin ver
    
    - **iOS** - Aşağıdakiler dışında tüm ayarlar kaldırılır:
        - Sesli dolaşıma izin ver
        - Veri dolaşımına izin ver
        - Dolaşım sırasında otomatik eşitlemeye izin ver

#### Intune istemci yazılımını çalıştıran Windows bilgisayarları

- **Endpoint Protection ayarları** - Ayarlar önerilen değerlere geri yüklenir. Tek özel durumu varsayılan değeri **Hayır** olan **Microsoft Active Protection Hizmeti'ne Katılın**ayarıdır. Ayrıntılar için bkz. [Microsoft Intune için Endpoint Protection ile Windows bilgisayarların korunmasına yardımcı olma](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md).
- **Yazılım güncelleştirmeleri ayarları** - Ayarlar işletim sistemi için varsayılan duruma sıfırlanır. Ayrıntılar için bkz. [Microsoft Intune'da yazılım güncelleştirmeleriyle Windows bilgisayarlarını güncel tutun](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md).
- **Microsoft Intune Center ayarları** - İlke tarafından yapılandırılan tüm destek iletişim bilgileri bilgisayarlardan silinir.
- **Windows Güvenlik Duvarı ayarları** - Ayarlar bilgisayar işletim sistemi için varsayılanlara sıfırlanır. Ayrıntılar için bkz. [Microsoft Intune için Endpoint Protection ile Windows bilgisayarların korunmasına yardımcı olma](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md).





<!--HONumber=May16_HO3-->


