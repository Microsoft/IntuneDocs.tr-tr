---
title: "Microsoft Intune’da cihaz profili sorunlarını giderme"
titlesuffix: Azure portal
description: "Takıldıysanız, bu konu Intune cihaz profilleriyle ilgili sorunları çözmenize yardımcı olabilir.\""
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 11/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ff950ce35c491ca576dc9cc77ab561e2cfef0381
ms.sourcegitcommit: 1df625330f4e8f7f661b5f2b9f16b5590971838d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2017
---
# <a name="troubleshooting-device-profiles-in-microsoft-intune"></a>Microsoft Intune’da cihaz profili sorunlarını giderme


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Bu konu başlığı altındaki bilgiler, Intune cihaz profilleri çerçevesinde sık karşılaşılan sorunları gidermenize yardımcı olması için kullanılabilir.

## <a name="why-doesnt-a-user-get-a-new-profile-when-changing-a-password-or-passphrase-on-an-existing-wi-fi-profile"></a>Bir kullanıcı, mevcut bir Wi-Fi profilinde parola değiştirirken neden yeni bir profil almıyor? 
Kurumsal bir Wi-Fi profili oluşturup profili bir gruba dağıttığınızda ve parolayı değiştirerek profili kaydettiğinizde, kullanıcının bu yeni profili almasını bekleyebilirsiniz. Ancak kullanıcı, yeni profili almayabilir. 

Bu sorunu gidermek için, kurumsal Wi-Fi başarısız olduğunda bağlanılabilecek bir konuk Wi-Fi ayarladığınızdan emin olun. Otomatik olarak bağlan ayarı etkin olmalıdır. Bu konuk Wi-Fi profilinin tüm kullanıcılara dağıtılması gerekir.

İzleyebileceğiniz ilave en iyi uygulamalar da mevcuttur:
- Bağlanmakta olduğunuz Wi-Fi ağı bir parola gerektirdiğinden, Wi-Fi yönlendiricisine otomatik olarak bağlanabildiğinizden emin olun. Bir iOS cihazıyla test edebilirsiniz.
- Bir Wi-Fi uç noktasına (Wi-Fi yönlendiricisi) başarıyla bağlandıktan sonra SSID’yi ve kullanılan kimlik bilgilerini (kullanılan parola) not edin.
- SSID ve kimlik bilgilerini (parola) Önceden Paylaşılan Anahtar alanına girin. 
- Profili, tercihen yalnızca BT ekibinden oluşan, sınırlı sayıda kullanıcıları olan bir test grubuna dağıtın. 
- iOS cihazınızı Intune ile eşitleyin. Daha önce kaydolmadıysanız kaydolun. 
- Aynı Wi-Fi uç noktasına bağlantıyı (ilk adımda bahsedildiği gibi) tekrar test edin.
- Daha büyük gruplara veya sonuçta kuruluşunuzdaki tüm beklenen kullanıcılara dağıtın. 

## <a name="how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned"></a>İlke veya uygulamalar atandıktan sonra mobil cihazların bunları alması ne kadar sürer?
Bir ilke veya uygulama atandığında, Intune tarafından cihaza hemen Intune hizmetinde giriş yapılması gerektiği konusunda bildirim gönderilmeye başlanır. Bu işlem genellikle beş dakikadan kısa sürer.

İlk bildirim gönderildikten sonra cihaz ilkeyi almak üzere giriş yapmazsa, Intune üç deneme daha yapar.  Cihaz çevrimdışıysa (örneğin, kapalıysa veya ağa bağlı değilse), bildirimleri almayabilir. Bu durumda cihaz, ilkeyi bir sonraki zamanlanmış Intune hizmeti girişinde aşağıdaki gibi alır:

- iOS ve macOS: 6 saatte bir.
- Android: 8 saatte bir.
- Windows Phone: 8 saatte bir.
- Cihaz olarak kaydedilen Windows 8.1 ve Windows 10 bilgisayarları: 8 saatte bir.

Cihaz daha yeni kaydedilmişse, giriş sıklığı aşağıda gösterildiği gibi daha fazla olacaktır:

- iOS ve macOS: 6 saat boyunca 15 dakikada bir ve daha sonra 6 saatte bir.
- Android: 15 dakika boyunca 3 dakikada bir, sonraki 2 saat boyunca 15 dakikada bir ve daha sonra 8 saatte bir.
- Windows Phone: 15 dakika boyunca 5 dakikada bir, sonraki 2 saat boyunca 15 dakikada bir ve daha sonra 8 saatte bir.
- Cihaz olarak kaydedilen Windows bilgisayarları: 30 dakika boyunca 3 dakikada bir ve daha sonra 8 saatte bir.

Ayrıca, kullanıcılar ilkeyi istedikleri zaman denetlemek için Şirket Portalı uygulamasını açıp cihazı eşitleyebilir.

## <a name="what-actions-cause-intune-to-immediately-send-a-notification-to-a-device"></a>Hangi eylemler cihaza Intune tarafından anında bildirim gönderilmesine neden olur?
Cihazlar Intune hizmetine giriş yapmaları gerektiğini söyleyen bir bildirim aldığında veya düzenli zamanlanmış giriş zamanlarında hizmete giriş yapar.  Temizleme, kilitleme, geçiş kodu sıfırlama, uygulama atama, profil atama (Wi-Fi, VPN, e-posta vb.) veya ilke atama gibi bir eylemle özel olarak bir cihazı veya kullanıcıyı hedeflediğinizde, Intune bu güncelleştirmeleri hemen almak için Intune hizmetine giriş yapması gerektiğini cihaza bildirmeye çalışır.

Şirket portalındaki kişi bilgilerinin düzeltilmesi gibi diğer değişiklikler, cihazlara anında bildirim gönderilmesine neden olmaz.

## <a name="if-multiple-policies-are-assigned-to-the-same-user-or-device-how-do-i-know-which-settings-will-get-applied"></a>Aynı kullanıcı veya cihaza birden çok ilke atanıyorsa hangi ayarların uygulanacağını nasıl bilebilirim?
Aynı kullanıcı veya cihaza iki veya daha fazla ilke atandığında, hangi ayarın uygulanacağını belirleyen değerlendirme tek ayar düzeyinde yapılır:

-   Uyumluluk ilkesi ayarları, her zaman yapılandırma ilkesi ayarlarından önceliklidir.

-   Farklı bir uyumluluk ilkesindeki aynı ayarla karşılaştırılarak değerlendirildiğinde, en kısıtlayıcı uyumluluk ilkesi ayarı uygulanır.

-   Bir yapılandırma ilkesi ayarı farklı bir yapılandırma ilkesindeki bir ayarla çakışıyorsa bu çakışma Azure portalında görüntülenir. Bu gibi çakışmaları el ile çözümlemeniz gerekir.

## <a name="what-happens-when-app-protection-policies-conflict-with-each-other-which-one-will-be-applied-to-the-app"></a>Uygulama koruma ilkeleri birbiriyle çakışırsa ne olur? Uygulamaya hangisi uygulanır?
Bir uygulama koruma ilkesinde, sayı giriş alanları (sıfırlamadan önce PIN deneme sayısı gibi) haricinde, en kısıtlayıcı ayarlar çakışma değerleridir.  Sayı giriş alanları, konsolda önerilen ayarlar seçeneğini kullanarak bir MAM ilkesi oluşturduğunuzda alacağı değerlerle aynı değerlere ayarlanır.

İki profil ayarı aynıysa çakışmalar oluşur.  Örneğin, kopyala/yapıştır ayarı dışında birbirinin aynı olan iki MAM ilkesi yapılandırdığınızı düşünün.  Bu senaryoda, kopyala/yapıştır ayarı en kısıtlayıcı değer olarak ayarlanır, ancak ayarların geri kalanı yapılandırıldığı gibi uygulanır.

Bir profilin uygulamaya atanıp geçerli olmasından sonra ikinci bir ilke atanırsa, ilk atanan ilke öncelikli olup geçerli kalırken ikinci ilke çakışmada görünür. Her ikisi de aynı zamanda uygulanırsa, yani bir profil diğerinden önce değilse, her ikisi de çakışmada olur. Çakışmadaki ayarlarda, en kısıtlayıcı olan değerler kullanılır.

## <a name="what-happens-when-ios-custom-policies-conflict"></a>iOS özel ilkeleri çakışırsa ne olur?
Intune, Apple yapılandırma dosyalarının veya özel bir Open Mobile Alliance Uniform Resource Identifier (OMA-URI) profilinin yükünü değerlendirmez. Yalnızca bir teslim mekanizması olarak görev yapar.

Özel bir profil atadığınızda, yapılandırılan ayarların uyumluluk ve yapılandırma ilkeleriyle veya diğer özel ilkelerle çakışmadığından emin olun. Ayar çakışmaları bulunan bir özel profil olması durumunda, ayarların hangi sırayla uygulanacağı rastgele belirlenir.

## <a name="what-happens-when-a-profile-is-deleted-or-no-longer-applicable"></a>Bir profil silindiğinde veya artık geçerli olmadığında ne olur?
Profili sildiğinizde veya bir cihazı profilin atandığı gruptan kaldırdığınızda, profil ve ayarlar aşağıdaki listelere göre cihazdan kaldırılır.

### <a name="enrolled-devices"></a>Kayıtlı cihazlar

- Wi-Fi, VPN, sertifika ve e-posta profilleri: Bu profiller tüm desteklenen kayıtlı cihazlardan kaldırılır.
- Diğer tüm profil türleri:
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

## <a name="i-changed-a-device-restriction-profile-but-the-changes-havent-taken-effect"></a>Cihaz kısıtlama profilini değiştirdim ama değişiklikler uygulanmadı
Windows Phone cihazlarında, MDM veya EAS yoluyla ayarlamış olduğunuz güvenlik ilkelerinin azaltılmasına izin verilmez. Örneğin, **Parolanın karakter sayısı alt sınırı** olarak 8 ayarlayın ve sonra bunu 4’e indirmeyi deneyin. Cihaza zaten daha kısıtlayıcı bir profil uygulanmıştır.

Cihaz platformuna bağlı olarak, profili daha az güvenli bir değerle değiştirmek isterseniz, güvenlik ilkelerini sıfırlamanız gerekebilir.
Örneğin Windows’ta, masaüstünde sağdan içeri doğru çekerek **Düğmeler** çubuğunu açın ve **Ayarlar** &gt; **Denetim Masası**’nı seçin.  **Kullanıcı Hesapları** uygulamasını seçin.
Sol taraftaki gezinti menüsünde, en altta bir **Güvenlik İlkelerini Sıfırla** bağlantısı vardır. O bağlantıyı seçin ve ardından **İlkeleri Sıfırla** düğmesini seçin.
Android, Windows Phone 8.1 ve üzeri ve iOS gibi diğer MDM cihazlarında, daha az kısıtlayıcı bir profil uygulayabilmeniz için cihazın devre dışı bırakılması ve sonra hizmete yeniden kaydedilmesi gerekebilir.


### <a name="next-steps"></a>Sonraki adımlar
Bu sorun giderme bilgileri işe yaramazsa, [Microsoft Intune için destek alma](get-support.md) konusunda açıklandığı gibi Microsoft Desteği ile iletişim kurun.