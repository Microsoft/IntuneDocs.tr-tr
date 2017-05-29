---
title: "Cihaz ayarlarını ilkelerle yönetme | Microsoft Docs"
description: "Yönettiğiniz kayıtlı cihazlarda ayarları ve özellikleri denetleyen ilkeleri oluşturmak ve dağıtmak için Intune kullanın."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 11/02/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 09bae0b9-4f79-4658-8ca1-a71ab992c1b2
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 8f1a4cb3bcab4aee534fc5fb9a1f1a1eb5a6f3a1
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---

# <a name="manage-settings-and-features-on-your-devices-with-microsoft-intune-policies"></a>Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune *ilkeleri*, mobil cihazlar ve bilgisayarlarda özellikleri denetleyen ayar gruplarıdır. İlkeleri önerilen veya özel ayarlar içeren şablonlar kullanarak oluşturur ve ardından cihaz veya kullanıcı gruplarına dağıtırsınız.

## <a name="types-of-policies"></a>İlke türleri

Intune ilkeleri aşağıdaki kategorilere ayrılır. Kullandığınız kategori, ilkeyi oluşturma ve dağıtma şeklinizi etkiler.


- **Yapılandırma ilkeleri:** Bunlar yaygın olarak, cihazlarınızdaki güvenlik ayarlarını ve özelliklerini yönetmek için kullanılır. Bu ilkelerin nasıl oluşturulduğunu ve dağıtıldığını öğrenmek ve kullanılabilir ayarları keşfetmek için bu konu başlığı altında verilen bilgileri kullanın.
- **Cihaz uyumluluk ilkeleri:** Bunlar, bir cihazın koşullu erişim ilkeleriyle uyumlu kabul edilmesi için uyması gereken kuralları ve ayarları tanımlar. Uyumluluk ilkelerini, koşullu erişimden bağımsız olarak cihazlardaki uyumluluğu izlemek ve sorunları gidermek için de kullanabilirsiniz.
Ayrıntılar için bkz. [Microsoft Intune’da cihaz uyumluluk ilkeleri](introduction-to-device-compliance-policies-in-microsoft-intune.md).
- **Koşullu erişim ilkeleri:** Bu ilkeler, belirttiğiniz koşullara bağlı olarak e-posta ve diğer hizmetleri güvenli hale getirmenize yardımcı olur.
Ayrıntılar için bkz. [Microsoft Intune ile e-posta ve O365 hizmetlerine erişimi kısıtlama](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).
- **Şirket cihaz kaydı ilkeleri:** Şirket cihaz kaydı ilkeleri hakkında daha fazla bilgi için bkz. [Microsoft Intune ile iOS ve Mac yönetimini ayarlama](set-up-ios-and-mac-management-with-microsoft-intune.md).
- **Kaynak erişim ilkeleri:** Bu ilkeler, kullanıcılarınızın nerede olurlarsa olsunlar, işlerini başarıyla gerçekleştirmek için ihtiyaç duydukları dosyalara ve kaynaklara erişim kazanmasına yardımcı olmak için birlikte çalışır.
Ayrıntılar için, bkz. [Microsoft Intune ile şirket kaynaklarına erişimi etkinleştirme](enable-access-to-company-resources-with-microsoft-intune.md).


Intune ilkelerinin tam listesi için bkz. [Microsoft Intune ilke başvurusu](microsoft-intune-policy-reference.md).

## <a name="create-a-configuration-policy"></a>Yapılandırma ilkesi oluşturma

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com/), **İlke** &gt; **Yapılandırma İlkeleri** &gt; **Ekle**’yi seçin.

2.  İstediğiniz ilkeyi seçin, ilke için önerilen ayarları (varsa; bu ayarları daha sonra değiştirebilirsiniz) kullanmayı veya kendi ayarlarınızla özel bir ilke oluşturmayı seçin.

    > [!TIP]
    > Doğru ilkeyi seçerken yardım almak için bkz. [Microsoft Intune ilke başvurusu](microsoft-intune-policy-reference.md).

3.  Hazır olduğunuzda **İlke Oluştur**’u seçin.

4.  **İlke Oluştur** sayfasında ilke için bir ad ve isteğe bağlı bir açıklama yapılandırın.

5.  Gerekli ilke ayarlarını yapılandırın ve sonra **İlkeyi Kaydet**’i seçin.

    İlke ayarlarından herhangi birinde yardıma gerek duyarsanız, aşağıdaki listeden ilkenizin türünü seçin:

    - [iOS cihazları için ayarlar](ios-policy-settings-in-microsoft-intune.md)
    - [Android cihazları için ayarlar](android-policy-settings-in-microsoft-intune.md)
    - [Android for Work cihazları için ayarlar](android-for-work-policy-settings-in-microsoft-intune.md)
    - [Windows 8 ve Windows 8.1 cihazları için ayarlar](windows-configuration-policy-settings-in-microsoft-intune.md)
    - [Windows Phone 8.1 cihazları için ayarlar](windows-phone-8-1-policy-settings-in-microsoft-intune.md)
    - [Windows 10 masaüstü bilgisayar ve mobil cihazları için ayarlar](windows-10-policy-settings-in-microsoft-intune.md)
    - [Windows Team cihazları için ayarlar](windows-team-configuration-policy-settings-in-microsoft-intune.md)
    - [Windows sürüm yükseltme için ayarlar](edition-upgrade-policy-settings-in-microsoft-intune.md)
    - [Mac OS X cihazları için ayarlar](mac-os-x-policy-settings-in-microsoft-intune.md)
    - [Exchange ActiveSync için ayarlar](exchange-activesync-policy-settings-in-microsoft-intune.md)
    - [Hüküm ve koşullar ilkesi için ayarlar](terms-and-condition-policy-settings-in-microsoft-intune.md)
    - [Mobil cihazlar için genel ayarlar (eski)](mobile-device-security-policy-settings-in-microsoft-intune.md)

4.  Onay iletişim kutusunda, ilkeyi şimdi dağıtmak için **Evet**’i, dağıtmadan bir ilke oluşturmak için **Hayır**’ı seçin.

**İlke** çalışma alanında her ilke türünün bölümlerine göz atarak yeni ilkeyi görüntüleyebilir ve düzenleyebilirsiniz.

Önerilen ayarları kullanan bir ilke oluşturduğunuzda, yeni ilkenin adı şablon adı, tarih ve saatin bir birleşimidir. İlkeyi düzenlediğinizde, ad düzenleme işleminin tarih ve saatiyle güncelleştirilir.

İlke oluşturduktan sonra, genellikle ilkeyi bir veya daha fazla kullanıcı ya da cihaz grubuna dağıtmak istersiniz.

> [!TIP]
> Tüm ilke türlerini dağıtmazsınız. Örneğin, mobil uygulama yönetimi (MAM) ilkesi dağıtılmaz. Bunun yerine, bu ilke türü bir uygulamayla ilişkilendirilir ve bu uygulamayı dağıtırsınız.

## <a name="deploy-a-configuration-policy"></a>Yapılandırma ilkesini dağıtma

1.  **İlke** çalışma alanında, dağıtmak istediğiniz ilkeyi ve ardından **Dağıtımı Yönet**’i seçin.

2.  **Dağıtımı Yönet** iletişim kutusunda:

    -   İlkeyi dağıtmak için, ilkeyi dağıtmak istediğiniz bir veya daha fazla grup seçin ve ardından **Ekle** &gt; **Tamam**'ı seçin.

    -   Dağıtmadan iletişim kutusunu kapatmak için **İptal**’i seçin.

Dağıtılan bir ilkeyi seçtiğinizde, ilkeler listesinin alt bölümünde dağıtım hakkında daha fazla bilgi görüntüleyebilirsiniz.

## <a name="manage-policies"></a>İlkeleri yönetme

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com/) **İlke**’yi seçin ve sonra yönetmek istediğiniz ilkeye giderek bu ilkeyi seçin.

2.  Aşağıdaki eylemlerden birini seçin:

- **Düzenle**: Değişiklik yapabilmek için seçili ilkenin özelliklerini açın.
- **Sil**: Seçili ilkeyi silin.<br>Bir ilkeyi sildiğinizde, dağıtıldığı tüm gruplardan kaldırılır.
- **Dağıtımı Yönet**: İlkeyi dağıtmak istediğiniz grubu seçin ve sonra da **Ekle**’yi seçin.


## <a name="frequently-asked-questions-about-intune-policies"></a>Intune ilkeleri hakkında sık sorulan sorular

### <a name="how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-deployed"></a>İlke veya uygulamalar dağıtıldıktan sonra mobil cihazların bunları alması ne kadar sürer?
Bir ilke veya uygulama dağıtıldığında, Intune tarafından cihaza hemen Intune hizmetinde giriş yapılması gerektiği konusunda bildirim gönderilmeye başlanır. Bu işlem genellikle beş dakikadan kısa sürer.

İlk bildirim gönderildikten sonra cihaz ilkeyi almak üzere giriş yapmazsa, Intune üç deneme daha yapar.  Cihaz çevrimdışıysa (örneğin, kapalıysa veya ağa bağlı değilse), bildirimleri almayabilir. Bu durumda cihaz, ilkeyi bir sonraki zamanlanmış Intune hizmeti girişinde aşağıdaki gibi alır:

- iOS ve Mac OS X: 6 saatte bir.
- Android: 8 saatte bir.
- Windows Phone: 8 saatte bir.
- Cihaz olarak kaydedilen Windows 8.1 ve Windows 10 bilgisayarları: 8 saatte bir.

Cihaz daha yeni kaydedilmişse, giriş sıklığı aşağıda gösterildiği gibi daha fazla olacaktır:

- iOS ve Mac OS X: 6 saat boyunca 15 dakikada bir ve daha sonra 6 saatte bir.
- Android: 15 dakika boyunca 3 dakikada bir, sonraki 2 saat boyunca 15 dakikada bir ve daha sonra 8 saatte bir.
- Windows Phone: 15 dakika boyunca 5 dakikada bir, sonraki 2 saat boyunca 15 dakikada bir ve daha sonra 8 saatte bir.
- Cihaz olarak kaydedilen Windows bilgisayarları: 30 dakika boyunca 3 dakikada bir ve daha sonra 8 saatte bir.

Ayrıca, kullanıcılar ilkeyi istedikleri zaman denetlemek için Şirket Portalı uygulamasını açıp cihazı eşitleyebilir.

### <a name="what-actions-cause-intune-to-immediately-send-a-notification-to-a-device"></a>Hangi eylemler cihaza Intune tarafından anında bildirim gönderilmesine neden olur?
Cihazlar Intune hizmetine giriş yapmaları gerektiğini söyleyen bir bildirim aldığında veya düzenli zamanlanmış giriş zamanlarında hizmete giriş yapar.  Temizleme, kilitleme, geçiş kodu sıfırlama, uygulama dağıtma, profil dağıtma (Wi-Fi, VPN, e-posta vb.) veya ilke dağıtma gibi bir eylemle özel olarak bir cihazı veya kullanıcıyı hedeflediğinizde, Intune bu güncelleştirmeleri hemen almak için Intune hizmetine giriş yapması gerektiğini cihaza bildirmeye çalışır.

Şirket portalındaki kişi bilgilerinin düzeltilmesi gibi diğer değişiklikler, cihazlara anında bildirim gönderilmesine neden olmaz.

### <a name="if-multiple-policies-are-deployed-to-the-same-user-or-device-how-do-i-know-which-settings-will-get-applied"></a>Aynı kullanıcı veya cihaza birden çok ilke dağıtılıyorsa hangi ayarların uygulanacağını nasıl bilebilirim?
Aynı kullanıcı veya cihaza iki veya daha fazla ilke dağıtıldığında, hangi ayarın uygulanacağını belirleyen değerlendirme tek tek ayarlar düzeyinde yapılır:

-   Uyumluluk ilkesi ayarları, her zaman yapılandırma ilkesi ayarlarından önceliklidir.

-   Farklı bir uyumluluk ilkesindeki aynı ayarla karşılaştırılarak değerlendirildiğinde, en kısıtlayıcı uyumluluk ilkesi ayarı uygulanır.

-   Bir yapılandırma ilkesi ayarı, farklı bir yapılandırma ilkesindeki bir ayarla çakışıyorsa, bu çakışma Intune konsolunda görüntülenir. Bu gibi çakışmaları el ile çözümlemeniz gerekir.

### <a name="what-happens-when-mobile-application-management-policies-conflict-with-each-other-which-one-will-be-applied-to-the-app"></a>Mobil uygulama yönetimi ilkeleri birbiriyle çakıştığında ne olur? Uygulamaya hangisi uygulanır?
MAM ilkesinde sayı giriş alanları (sıfırlamadan önce PIN denemesi sayısı gibi) dışında en kısıtlayıcı ayarlar, çakışma değerleridir.  Sayı giriş alanları, konsolda önerilen ayarlar seçeneğini kullanarak bir MAM ilkesi oluşturduğunuzda alacağı değerlerle aynı değerlere ayarlanır.

İki ilke ayarı aynıysa çakışmalar oluşur.  Örneğin, kopyala/yapıştır ayarı dışında birbirinin aynı olan iki MAM ilkesi yapılandırdığınızı düşünün.  Bu senaryoda, kopyala/yapıştır ayarı en kısıtlayıcı değer olarak ayarlanır, ancak ayarların geri kalanı yapılandırıldığı gibi uygulanır.

Bir ilkenin uygulamaya dağıtılıp geçerli olmasından sonra ikinci bir ilke dağıtılırsa, önceki ilke öncelikli olur ve geçerli kalırken ikinci ilke çakışmada görünür. Her ikisi de aynı zamanda uygulanırsa, yani bir ilke diğerinden önce değilse, her ikisi de çakışmada olur. Çakışmadaki ayarlarda, en kısıtlayıcı olan değerler kullanılır.

### <a name="what-happens-when-ios-custom-policies-conflict"></a>iOS özel ilkeleri çakışırsa ne olur?
Intune, Apple yapılandırma dosyalarının veya özel bir Open Mobile Alliance Uniform Resource Identifier (OMA-URI) ilkesinin yükünü değerlendirmez. Yalnızca bir teslim mekanizması olarak görev yapar.

Özel bir ilke dağıttığınızda yapılandırılan ayarların uyumluluk ve yapılandırma ilkeleriyle veya diğer özel ilkelerle çakışmadığından emin olun. Ayar çakışmaları bulunan bir özel ilke olması durumunda, ayarların hangi sırayla uygulanacağı rastgele belirlenir.

### <a name="what-happens-when-a-policy-is-deleted-or-no-longer-applicable"></a>Bir ilke silindiğinde veya artık geçerli olmadığında ne olur?
İlkeyi sildiğinizde veya bir cihazı ilkenin dağıtıldığı gruptan kaldırdığınızda, ilke ve ayarlar aşağıdaki listelere göre cihazdan kaldırılır.

#### <a name="enrolled-devices"></a>Kayıtlı cihazlar

- Wi-Fi, VPN, sertifika ve e-posta profilleri: Bu profiller tüm desteklenen kayıtlı cihazlardan kaldırılır.
- Tüm diğer ilke türleri:
    - **Windows ve Android cihazları**: Ayarlar cihazdan kaldırılmaz.
    - **Windows Phone 8.1 cihazları**: Aşağıdaki ayarlar kaldırılır:
        - Mobil cihazların kilidini açmak için bir parola gerektir
        - Basit parolalara izin ver
        - Minimum parola uzunluğu
        - Gerekli parola türü
        - Parola geçerlilik süresi (gün)
        - Parola geçmişini anımsa
        - Cihaz temizlenmeden önce izin verilen yinelenen oturum açma hatası sayısı
        - Parola istenmeden önce geçen işlem yapılmayan dakika sayısı
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

    - **iOS**: Aşağıdakiler dışında tüm ayarlar kaldırılır:
        - Sesli dolaşıma izin ver
        - Veri dolaşımına izin ver
        - Dolaşım sırasında otomatik eşitlemeye izin ver

#### <a name="windows-pcs-running-the-intune-client-software"></a>Intune istemci yazılımını çalıştıran Windows bilgisayarları

- **Endpoint Protection ayarları**: Ayarlar önerilen değerlere geri yüklenir. Tek özel durum, varsayılan değeri **Hayır** olan **Microsoft Active Protection Hizmeti'ne Katıl** ayarıdır. Ayrıntılar için bkz. [Microsoft Intune için Endpoint Protection ile Windows bilgisayarların korunmasına yardımcı olma](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md).
- **Yazılım güncelleştirmeleri ayarları**: Ayarlar, işletim sistemi için varsayılan duruma sıfırlanır. Ayrıntılar için bkz. [Microsoft Intune'da yazılım güncelleştirmeleriyle Windows bilgisayarlarını güncel tutun](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md).
- **Microsoft Intune Center ayarları**: İlke tarafından yapılandırılan tüm destek iletişim bilgileri bilgisayarlardan silinir.
- **Windows Güvenlik Duvarı ayarları**: Ayarlar, bilgisayar işletim sisteminin varsayılan değerlerine sıfırlanır. Ayrıntılar için bkz. [Microsoft Intune için Endpoint Protection ile Windows bilgisayarların korunmasına yardımcı olma](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md).


### <a name="how-can-i-refresh-the-policies-on-a-device-to-ensure-that-they-are-current-applies-to-windows-pcs-running-the-intune-client-software-only"></a>Güncel olmalarını sağlamak için cihazdaki ilkeleri nasıl yenilerim (yalnızca Intune istemci yazılımını çalıştıran Windows bilgisayarları için geçerlidir)?

1.  Herhangi bir cihaz grubunda, üzerindeki ilkeleri yenilemek istediğiniz cihazları seçin, sonra **Uzak Görevler** &gt; **İlkeleri Yenile**’yi seçin.
2.  Görev durumunu denetlemek için, Intune yönetim konsolunun sağ alt köşesindeki **Uzak Görevler**’i seçin.

### <a name="where-can-i-find-help-troubleshooting-policies"></a>İlkelerle ilgili sorunları giderme hakkında nereden yardım bulabilirim?

Bkz. [Microsoft Intune’da ilke sorunlarını giderme](/intune-classic/troubleshoot/troubleshoot-policies-in-microsoft-intune).

