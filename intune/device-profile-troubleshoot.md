---
title: Microsoft Intune - Azure’da cihaz profillerinde sorun giderme | Microsoft Docs
description: Azure portalında Microsoft InTune ile ilgili bazı kullanıcılara veya cihazlara uygulanmayan profil değişiklikleri de dahil olmak üzere cihaz profilleriyle ilgili yaygın sorunlar, yeni ilkelerin cihazlara ne kadar süre uygulanacağı, birden çok ilke olduğunda hangi ayarların uygulandığı, bir profil silindiğinde veya kaldırıldığında ne olduğu ve daha fazlası
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 1/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 305799fa21ae7c3464caf8f7019dcf9e8170d3ac
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52181488"
---
# <a name="common-issues-and-resolutions-with-device-profiles-in-microsoft-intune"></a>Microsoft Intune'da cihaz profilleri ile ilgili sık karşılaşılan sorunlar ve çözüm yolları

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune cihaz profillerini kullanarak sık karşılaşılan sorunları giderin.

## <a name="why-doesnt-a-user-get-a-new-profile-when-changing-a-password-or-passphrase-on-an-existing-wi-fi-profile"></a>Bir kullanıcı, mevcut bir Wi-Fi profilinde parola değiştirirken neden yeni bir profil almıyor? 
Şirket Wi-Fi profili oluşturur, profili bir gruba dağıtır, parolayı değiştirir ve profili kaydedersiniz. Profil değiştiğinde, bazı kullanıcılar yeni profili alamayabilir.

Bu sorunu azaltmak için konuk Wi-Fi kurulumu yapın. Şirket Wi-Fi başarısız olursa, kullanıcılar konuk Wi-Fi ile bağlanabilir. Otomatik bağlanma ayarlarının tümünü etkinleştirdiğinizden emin olun. Konuk Wi-Fi profilini tüm kullanıcılara dağıtın.

Bazı ek öneriler:  

- Bağlanmakta olduğunuz Wi-Fi ağında bir parola kullanıldığından, Wi-Fi yönlendiricisine otomatik olarak bağlanabildiğinizden emin olun. Bir iOS cihazıyla test edebilirsiniz.
- Bir Wi-Fi uç noktasına (Wi-Fi yönlendiricisi) başarıyla bağlandıktan sonra SSID’yi ve kullanılan kimlik bilgilerini (bu değer erişim kodu veya paroladır) not edin.
- SSID ve kimlik bilgilerini (parola) Önceden Paylaşılan Anahtar alanına girin. 
- Profili, tercihen yalnızca BT ekibinden oluşan, sınırlı sayıda kullanıcıları olan bir test grubuna dağıtın. 
- iOS cihazınızı Intune ile eşitleyin. Daha önce kaydolmadıysanız kaydolun. 
- Aynı Wi-Fi uç noktasına bağlantıyı (ilk adımda bahsedildiği gibi) tekrar test edin.
- Daha büyük gruplara veya sonuçta kuruluşunuzdaki tüm beklenen kullanıcılara dağıtın. 

## <a name="how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned"></a>İlke veya uygulamalar atandıktan sonra mobil cihazların bunları alması ne kadar sürer?
Bir ilke veya uygulama atandığında Intune, Intune hizmetine iade için cihaza hemen bildirimde bulunmaya başlar. Bu bildirim genellikle beş dakikadan kısa sürer.

İlk bildirim gönderildikten sonra cihaz ilkeyi almak üzere giriş yapmazsa, Intune üç deneme daha yapar. Cihaz çevrimdışıysa (örneğin, kapalıysa veya ağa bağlı değilse), bildirimleri almayabilir. Bu durumda cihaz, ilkeyi bir sonraki zamanlanmış Intune hizmeti girişinde aşağıdaki gibi alır:

- iOS ve macOS: Altı saatte bir
- Android: Sekiz saatte bir
- Windows Phone: Sekiz saatte bir
- Cihaz olarak kaydedilen Windows 8.1 ve Windows 10 bilgisayarları: Sekiz saatte bir

Cihaz daha yeni kaydedilmişse, giriş sıklığı aşağıda gösterildiği gibi daha fazla olur:

- iOS ve macOS: Altı saat boyunca 15 dakikada bir ve daha sonra altı saatte bir
- Android: 15 dakika boyunca üç dakikada bir, sonraki iki saat boyunca 15 dakikada bir ve daha sonra sekiz saatte bir
- Windows Phone: 15 dakika boyunca beş dakikada bir, sonraki iki saat boyunca 15 dakikada bir ve daha sonra sekiz saatte bir
- Cihaz olarak kaydedilen Windows bilgisayarları: 30 dakika boyunca üç dakikada bir ve daha sonra sekiz saatte bir

Ayrıca, kullanıcılar ilkeyi istedikleri zaman denetlemek için Şirket Portalı uygulamasını açıp cihazı eşitleyebilir.

Kullanıcı benzeşimi olmayan cihazlar için kaydı takip eden eşitleme sıklığı, birkaç saat ile bir gün veya daha fazlası arasında değişebilir. Intune, bir cihazın hizmete bildirim yapması için belirli aralıklarla istek gönderir. Ancak iade etmek yine de cihaza bağlıdır. Bir cihazın ilk kaydından sonra cihaz kayıt türü ve cihaza atanan ilkelerle profillerin türüne bağlı olarak, cihazın bu iade etme işlemini tamamlama süresi tahmin edilemez. Ancak cihaz, kaydedildikten ve tüm ilk ilkeler uygulandıktan sonra yaklaşık altı saatte bir yeni ilkeleri denetler.

## <a name="what-actions-cause-intune-to-immediately-send-a-notification-to-a-device"></a>Hangi eylemler cihaza Intune tarafından anında bildirim gönderilmesine neden olur?
Cihazlar Intune hizmetine giriş yapmaları gerektiğini söyleyen bir bildirim aldığında veya düzenli zamanlanmış giriş zamanlarında hizmete giriş yapar. Bir cihazı veya kullanıcıyı silme, kilitleme, parola sıfırlama, uygulama atama, profil atama veya ilke atama gibi bir eylemle hedeflediğinizde Intune, bu güncelleştirmeleri almak için Intune hizmetini kullanarak giriş yapılacak cihazı derhal bilgilendirir.

Şirket portalındaki kişi bilgilerinin düzeltilmesi gibi diğer değişiklikler, cihazlara anında bildirim gönderilmesine neden olmaz.

## <a name="if-multiple-policies-are-assigned-to-the-same-user-or-device-how-do-i-know-which-settings-gets-applied"></a>Aynı kullanıcı veya cihaza birden çok ilke atanıyorsa hangi ayarların uygulanacağını nasıl bilebilirim?
Aynı kullanıcı veya cihaza iki veya daha fazla ilke atandığında, hangi ayarın uygulanacağı tek ayar düzeyinde belirlenir:

-   Uyumluluk ilkesi ayarları, her zaman yapılandırma ilkesi ayarlarından önceliklidir

-   Bir uyumluluk ilkesi, farklı bir uyumluluk ilkesinde aynı ayara karşı değerlendirilirse, en kısıtlayıcı uyumluluk ilkesi ayarı uygulanır.

-   Bir yapılandırma ilkesi ayarı farklı bir yapılandırma ilkesindeki bir ayarla çakışıyorsa bu çakışma Azure portalında görüntülenir. Bu senaryoda, bu çakışmaları el ile çözün.

## <a name="what-happens-when-app-protection-policies-conflict-with-each-other-which-one-is-applied-to-the-app"></a>Uygulama koruma ilkeleri birbiriyle çakışırsa ne olur? Uygulamaya hangisi uygulanır?
Bir uygulama koruma ilkesinde, sayı giriş alanları (sıfırlamadan önce PIN deneme sayısı gibi) haricinde, en kısıtlayıcı ayarlar çakışma değerleridir. Sayı giriş alanları, konsolda önerilen ayarlar seçeneğini kullanarak bir MAM ilkesi oluşturduğunuzda alacağı değerlerle aynı değerlere ayarlanır.

İki profil ayarı aynıysa çakışmalar oluşur. Örneğin, kopyala/yapıştır ayarı dışında birbirinin aynı olan iki MAM ilkesi yapılandırdığınızı düşünün. Bu senaryoda, kopyala/yapıştır ayarı en kısıtlayıcı değer olarak ayarlanır, ancak ayarların geri kalanı yapılandırıldığı gibi uygulanır.

Bir profilin uygulamaya atanıp geçerli olmasından sonra ikinci bir ilke atanırsa, ilk atanan ilke öncelikli olup geçerli kalırken ikinci ilke çakışmada görünür. Her ikisi de aynı zamanda uygulanırsa, yani bir profil diğerinden önce değilse, her ikisi de çakışmada olur. Çakışmadaki ayarlarda, en kısıtlayıcı olan değerler kullanılır.

## <a name="what-happens-when-ios-custom-policies-conflict"></a>iOS özel ilkeleri çakışırsa ne olur?
Intune, Apple yapılandırma dosyalarının veya özel bir Open Mobile Alliance Uniform Resource Identifier (OMA-URI) profilinin yükünü değerlendirmez. Yalnızca bir teslim mekanizması olarak görev yapar.

Özel bir profil atadığınızda, yapılandırılan ayarların uyumluluk ve yapılandırma ilkeleriyle veya diğer özel ilkelerle çakışmadığından emin olun. Özel bir profil ve ayarları çakışırsa, ayarlar rastgele uygulanır.

## <a name="what-happens-when-a-profile-is-deleted-or-no-longer-applicable"></a>Bir profil silindiğinde veya artık geçerli olmadığında ne olur?
Profili sildiğinizde veya bir cihazı profile sahip olan gruptan kaldırdığınızda, profil ve ayarlar aşağıdaki listelere göre cihazdan kaldırılır:

- Wi-Fi, VPN, sertifika ve e-posta profilleri: Bu profiller tüm desteklenen kayıtlı cihazlardan kaldırılır.
- Diğer tüm profil türleri:  
    - **Windows ve Android cihazları**: Ayarlar cihazdan kaldırılmaz
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

## <a name="i-changed-a-device-restriction-profile-but-the-changes-havent-taken-effect"></a>Cihaz kısıtlama profilini değiştirdim ama değişiklikler uygulanmadı
Windows Phone cihazlarında, MDM veya EAS kullanarak ayarlamış olduğunuz güvenlik ilkelerinin azaltılmasına izin verilmez. Örneğin, **Parolanın karakter sayısı alt sınırı** olarak 8 ayarlayın ve sonra bunu 4’e indirmeyi deneyin. Cihaza zaten daha kısıtlayıcı bir profil uygulanmıştır.

Profili daha az güvenli bir değerle değiştirmek isterseniz güvenlik ilkelerini sıfırlayın. Örneğin Windows 8.1’de, masaüstünde sağdan içeri doğru kaydırın ve **Ayarlar** > **Denetim Masası**’nı seçin.  **Kullanıcı Hesapları** uygulamasını seçin. Sol taraftaki gezinti menüsünde, bir **Güvenlik İlkelerini Sıfırla** bağlantısı vardır (en alta doğru). Bunu seçin ve ardından **İlkeleri Sıfırla**’yı seçin.

Android, Windows Phone 8.1 ve üzeri, iOS ve Windows 10 gibi diğer MDM cihazlarında, daha az kısıtlayıcı bir profil uygulamak için cihazın devre dışı bırakılması ve sonra hizmete yeniden kaydedilmesi gerekebilir.

## <a name="next-steps"></a>Sonraki adımlar
Ek yardım mı gerekiyor? Bkz. [Microsoft Intune için destek alma](get-support.md).
