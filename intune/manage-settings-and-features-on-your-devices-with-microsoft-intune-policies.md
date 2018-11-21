---
title: Intune - Azure ile cihaz ilkeleri, profilleri ve Soru-Cevap | Microsoft Docs
description: Cihaz yapılandırma ilkeleri, şirket kaynaklarına erişim edinme, koşullu erişimi etkinleştirme ve şirket cihazlarını kaydetme gibi Microsoft Intune’da kullanabileceğiniz farklı ilke ve profiller hakkında bilgi edinin. Ayrıca sıkça sorulan sorulara cevap alın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 6/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 09bae0b9-4f79-4658-8ca1-a71ab992c1b2
ROBOTS: ''
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.openlocfilehash: 3b1115a91707c639caba6410ace3c2e255e40a39
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52185007"
---
# <a name="manage-settings-and-features-on-your-devices-with-intune-policies"></a>Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme

Microsoft Intune *ilkeleri*, mobil cihazlar ve bilgisayarlarda özellikleri denetleyen ayar gruplarıdır. Önerilen veya özel ayarları içeren şablonlar kullanarak ilke oluşturursunuz. Daha sonra bunları cihazlara veya kullanıcı gruplarına dağıtırsınız.

## <a name="types-of-policies"></a>İlke türleri

Intune ilkeleri aşağıdaki kategorilere ayrılır. Kullandığınız kategori, ilkeyi oluşturma ve dağıtma şeklinizi etkiler.

- **Yapılandırma ilkeleri:** Bunlar yaygın olarak cihazlarınızdaki şirket kaynaklarına erişim gibi güvenlik ayarlarını ve özelliklerini yönetmek için kullanılır. [Intune cihaz profillerini](device-profiles.md) kullanmaya başlayın.
- **Cihaz uyumluluk ilkeleri**: Bir cihazın koşullu erişim ilkeleriyle uyumlu olarak değerlendirilmesi için uyması gereken kuralları ve ayarları tanımlayın. Uyumluluk ilkelerini, koşullu erişimden bağımsız olarak cihazlardaki uyumluluğu izlemek ve sorunları gidermek için de kullanabilirsiniz. [Cihaz uyumluluk ilkelerini](device-compliance-get-started.md) kullanmaya başlayın.
- **Koşullu erişim ilkeleri**: Belirttiğiniz koşullara bağlı olarak e-posta ve diğer hizmetleri güvenli hale getirmenize yardımcı olur. [Koşullu erişim nedir](conditional-access.md) ve [koşullu erişim kullanmanın yaygın yolları](conditional-access-intune-common-ways-use.md) makaleleri, koşullu erişimi kullanmaya başlamak için iyi kaynaklardır.
- **Şirket cihaz kaydı ilkeleri:** Şirket cihaz kaydı ilkeleri hakkında daha fazla bilgi için bkz. [iOS cihazları kaydetme](ios-enroll.md).

## <a name="frequently-asked-questions-about-intune-policies"></a>Intune ilkeleri hakkında sık sorulan sorular

### <a name="how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-being-deployed"></a>İlke veya uygulamalar dağıtıldıktan sonra mobil cihazların bunları alması ne kadar sürer?
Bir ilke veya uygulama dağıtıldığında Intune, Intune hizmetine iade için cihaza hemen bildirimde bulunmaya başlar. Bu adım genellikle beş dakikadan kısa sürer.

İlk bildirim gönderildikten sonra cihaz ilkeyi almak üzere giriş yapmazsa, Intune üç deneme daha yapar.  Cihaz çevrimdışıysa (örneğin kapalıysa veya bir ağa bağlı değilse) bildirimleri almayabilir. Bu durumda cihaz, ilkeyi bir sonraki zamanlanmış Intune hizmeti iadesinde aşağıdaki gibi alır:

| Platform | İade sıklığı |
| --- | --- |
| iOS | 6 saatte bir | 
| Mac OS X | 6 saatte bir |
| Android | 8 saatte bir | 
| Windows Phone | 8 saatte bir | 
| Windows 8.1  | 8 saatte bir |  
| Cihaz olarak kaydedilen Windows 10 bilgisayarlar | 8 saatte bir | 

Cihaz son zamanlarda kaydedilmişse, iade sıklığı aşağıda gösterildiği gibi daha fazla olur:

| Platform | Sıklık |
| --- | --- |
| iOS | 6 saat boyunca her 15 dakikada bir, daha sonra her 6 saatte bir |  
| Mac OS X | 6 saat boyunca her 15 dakikada bir, daha sonra her 6 saatte bir | 
| Android | 15 dakika boyunca 3 dakikada bir, sonraki 2 saat boyunca 15 dakikada bir ve daha sonra 8 saatte bir | 
| Windows Phone | 15 dakika boyunca 5 dakikada bir, sonraki 2 saat boyunca 15 dakikada bir ve daha sonra 8 saatte bir | 
| Cihaz olarak kaydedilen Windows bilgisayarları | 30 dakika boyunca 3 dakikada bir, daha sonra 8 saatte bir | 

Ayrıca, kullanıcılar ilkeyi istedikleri zaman denetlemek için Şirket Portalı uygulamasını açıp cihazı eşitleyebilir.

### <a name="what-actions-cause-intune-to-immediately-send-a-notification-to-a-device"></a>Hangi eylemler cihaza Intune tarafından anında bildirim gönderilmesine neden olur?
Cihazlar Intune hizmetine iade etmeleri gerektiğini söyleyen bir bildirim aldığında veya düzenli zamanlanmış iade zamanlarında hizmete iade eder.  Silme, kilitleme, geçiş kodu sıfırlama, uygulama dağıtma, profil dağıtma (Wi-Fi, VPN, e-posta) veya ilke dağıtma gibi bir eylemle bir cihazı veya kullanıcıyı hedeflediğinizde Intune; cihaza Intune hizmetine iade etmesi konusunda anında bildirim göndermeye çalışır.

Şirket portalındaki kişi bilgilerinin düzeltilmesi gibi diğer değişiklikler, cihazlara anında bildirim gönderilmesine neden olmaz.

### <a name="if-multiple-policies-are-deployed-to-the-same-user-or-device-how-do-i-know-which-settings-are-applied"></a>Aynı kullanıcı veya cihaza birden çok ilke dağıtılıyorsa hangi ayarların uygulanacağını nasıl bilebilirim?
Aynı kullanıcı veya cihaza iki veya daha fazla ilke dağıtıldığında, hangi ayarın uygulanacağını belirleyen değerlendirme tek tek ayarlar düzeyinde yapılır:

- Uyumluluk ilkesi ayarları, her zaman yapılandırma ilkesi ayarlarından önceliklidir.

- Farklı bir uyumluluk ilkesindeki aynı ayarla karşılaştırılarak değerlendirildiğinde, en kısıtlayıcı uyumluluk ilkesi ayarı uygulanır.

- Bir yapılandırma ilkesi ayarı farklı bir yapılandırma ilkesindeki bir ayarla çakışıyorsa bu çakışma Intune’da görüntülenir. Bu çakışmaları el ile çözün.

### <a name="what-happens-when-mobile-application-management-policies-conflict-with-each-other-which-one-applies-to-the-app"></a>Mobil uygulama yönetimi ilkeleri birbiriyle çakıştığında ne olur? Uygulamaya hangisi uygulanır?
Bir MAM ilkesinde sayı giriş alanları (sıfırlamadan önce PIN denemesi sayısı gibi) dışında en kısıtlayıcı ayarlar, çakışma değerleridir.  Sayı giriş alanları, konsolda önerilen ayarlar seçeneğini kullanarak bir MAM ilkesi oluşturduğunuzda alacağı değerlerle aynı değerlere ayarlanır.

İki ilke ayarı aynıysa çakışmalar oluşur.  Örneğin, kopyala/yapıştır ayarı dışında birbirinin aynı olan iki MAM ilkesi yapılandırdığınızı düşünün.  Bu senaryoda, kopyala/yapıştır ayarı en kısıtlayıcı değer olarak ayarlanır, ancak ayarların geri kalanı yapılandırıldığı gibi uygulanır.

Bir ilkenin uygulamaya dağıtılıp geçerli olmasından sonra ikinci bir ilke dağıtılırsa, önceki ilke öncelikli olur ve geçerli kalır. İkinci ilke ise çakışmada görünür. Her ikisi de aynı zamanda uygulanırsa, yani bir ilke diğerinden önce değilse her ikisi de çakışmada olur. Çakışmadaki ayarlarda, en kısıtlayıcı olan değerler kullanılır.

### <a name="what-happens-when-ios-custom-policies-conflict"></a>iOS özel ilkeleri çakışırsa ne olur?
Intune, Apple yapılandırma dosyalarının veya özel bir Open Mobile Alliance Tekdüzen Kaynak Tanımlayıcısı (OMA-URI) ilkesinin yükünü değerlendirmez. Yalnızca bir teslim mekanizması olarak görev yapar.

Özel bir ilke dağıttığınızda yapılandırılan ayarların uyumluluk ve yapılandırma ilkeleriyle veya diğer özel ilkelerle çakışmadığından emin olun. Ayar çakışmaları bulunan bir özel ilke olması durumunda, ayarların hangi sırayla uygulanacağı rastgele belirlenir.

### <a name="what-happens-when-a-policy-is-deleted-or-no-longer-applicable"></a>Bir ilke silindiğinde veya artık geçerli olmadığında ne olur?
Bir ilkeyi sildiğinizde veya dağıtılmış ilkesi olan bir gruptan bir cihazı kaldırdığınızda, ilke ve ayarlar aşağıdaki listelere göre cihazdan kaldırılır.

#### <a name="enrolled-devices"></a>Kayıtlı cihazlar

- Wi-Fi, VPN, sertifika ve e-posta profilleri: Bu profiller tüm desteklenen kayıtlı cihazlardan kaldırılır.
- Tüm diğer ilke türleri:
  - **Windows ve Android cihazları**: Ayarlar cihazdan kaldırılmaz.
  - **Windows Phone 8.1 cihazları**: Aşağıdaki ayarlar kaldırılır:
    - Mobil cihazların kilidini açmak için bir parola gerektir
    - Basit parolalara izin ver
    - Parola uzunluğu alt sınırı
    - Gerekli parola türü
    - Parola zaman aşımı (gün sayısı)
    - Parola geçmişini anımsa
    - Cihaz temizlenmeden önce izin verilen yinelenen oturum açma hatası sayısı
    - Parola istenmeden önce geçen işlem yapılmayan dakika sayısı
    - Gerekli parola türü – minimum karakter kümesi sayısı
    - Kameraya izin ver
    - Cihazda şifrelemeyi gerektir
    - Çıkarılabilir depolama birimine izin ver
    - Web tarayıcısına izin ver
    - Uygulama mağazasına izin ver
    - Ekran yakalamaya izin ver
    - Coğrafi konuma izin ver
    - Microsoft Hesabına izin ver
    - Kopyalama ve yapıştırmaya izin ver
    - Wi-Fi İnternet paylaşımına izin ver
    - Ücretsiz Wi-Fi etkin noktalarına otomatik olarak bağlanmaya izin ver
    - Wi-Fi etkin noktası bildirimine izin ver
    - Silmeye izin ver
    - Bluetooth'a izin ver
    - NFC'ye izin ver
    - Wi-Fi'a izin ver

  - **iOS**: Aşağıdakiler dışında tüm ayarlar kaldırılır:
    - Sesli dolaşıma izin ver
    - Veri dolaşımına izin ver
    - Dolaşım sırasında otomatik eşitlemeye izin ver

### <a name="where-can-i-find-help-troubleshooting-policies"></a>İlkelerle ilgili sorunları giderme hakkında nereden yardım bulabilirim?

Bkz. [İlkelerde sorun giderme](troubleshoot-policies-in-microsoft-intune.md).
