---
title: Microsoft Intune - Azure’da cihaz profillerinde sorun giderme | Microsoft Docs
description: Sık kullanılan sorular ve cevaplar cihaz ilkeleri ve profilleri birden çok ilke olduğunda hangi ayarların uygulandığında, cihazlara gönderilecek bir yeni ilkeleri ne kadar sürer ve cihazlara uygulanmayan profil değişiklikleri de dahil olmak üzere, ne zaman bir Silinen veya kaldırılan ve daha fazla Microsoft Intune profilidir.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/28/2019
ms.topic: troubleshooting
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 12ac2b93126f271bf4918c6a914dedc7a22c1010
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57461014"
---
# <a name="common-questions-issues-and-resolutions-with-device-policies-and-profiles-in-microsoft-intune"></a>Genel Sorular, sorunlar ve çözümleri cihaz ilkeleri ve profilleri Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Cihaz profilleri ve ilkeleri ıntune ile çalışırken sık sorulan soruların yanıtlarını alın. Bu da listeleri iade zaman aralıkları makalesi, çakışmaları ve daha fazlası hakkında daha fazla detains sağlar.

## <a name="why-doesnt-a-user-get-a-new-profile-when-changing-a-password-or-passphrase-on-an-existing-wi-fi-profile"></a>Bir kullanıcı, mevcut bir Wi-Fi profilinde parola değiştirirken neden yeni bir profil almıyor?

Şirket Wi-Fi profili oluşturur, profili bir gruba dağıtır, parolayı değiştirir ve profili kaydedersiniz. Profil değiştiğinde, bazı kullanıcılar yeni profili alamayabilir.

Bu sorunu azaltmak için konuk Wi-Fi kurulumu yapın. Şirket Wi-Fi başarısız olursa, kullanıcılar konuk Wi-Fi ile bağlanabilir. Otomatik bağlanma ayarlarının tümünü etkinleştirdiğinizden emin olun. Konuk Wi-Fi profilini tüm kullanıcılara dağıtın.

Bazı ek öneriler:  

- Bağlanmakta olduğunuz Wi-Fi ağı bir parola veya parola kullanıyorsa, Wi-Fi yönlendiricisine otomatik olarak bağlanabildiğinizden emin olun. Bir iOS cihazıyla test edebilirsiniz.
- Bir Wi-Fi uç noktasına (Wi-Fi yönlendiricisi) başarıyla bağlandıktan sonra SSID’yi ve kullanılan kimlik bilgilerini (bu değer erişim kodu veya paroladır) not edin.
- SSID ve kimlik bilgilerini (parola) Önceden Paylaşılan Anahtar alanına girin. 
- Profili, tercihen yalnızca BT ekibinden oluşan, sınırlı sayıda kullanıcıları olan bir test grubuna dağıtın. 
- iOS cihazınızı Intune ile eşitleyin. Daha önce kaydolmadıysanız kaydolun. 
- Aynı Wi-Fi uç noktasına bağlantıyı (ilk adımda bahsedildiği gibi) tekrar test edin.
- Daha büyük gruplara veya sonuçta kuruluşunuzdaki tüm beklenen kullanıcılara dağıtın. 

## <a name="how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned"></a>İlke veya uygulamalar atandıktan sonra mobil cihazların bunları alması ne kadar sürer?

Bir ilke veya uygulama atandığında Intune, Intune hizmetine iade için cihaza hemen bildirimde bulunmaya başlar. Bu bildirim genellikle beş dakikadan kısa sürer.

Bir cihaz ilk bildirim sonra ilkeyi almak üzere giriş yapmazsa, Intune üç deneme daha yapar. Çevrimdışı cihaz gibi kapalı veya bir ağa bağlı değilse, bildirimleri almayabilir. Bu durumda cihaz, sonraki zamanlanmış iadeyi olan Intune hizmeti ile şirket ilkesi alır:

| Platform | Yenileme döngüsü|
| --- | --- |
| iOS | 6 saatte bir |
| Mac OS | 6 saatte bir |
| Android | 8 saatte bir |
| Cihaz olarak kaydedilen Windows 10 bilgisayarlar | 8 saatte bir |
| Windows Phone | 8 saatte bir |
| Windows 8.1 | 8 saatte bir |

Son olarak cihazın kayıtlı, iade daha sık çalışır:

| Platform | Sıklık |
| --- | --- |
| iOS | 6 saat boyunca her 15 dakikada bir, daha sonra her 6 saatte bir |  
| Mac OS X | 6 saat boyunca her 15 dakikada bir, daha sonra her 6 saatte bir | 
| Android | 15 dakika boyunca 3 dakikada bir, sonraki 2 saat boyunca 15 dakikada bir ve daha sonra 8 saatte bir | 
| Windows Phone | 15 dakika boyunca 5 dakikada bir, sonraki 2 saat boyunca 15 dakikada bir ve daha sonra 8 saatte bir | 
| Cihaz olarak kaydedilen Windows bilgisayarları | 30 dakika boyunca 3 dakikada bir, daha sonra 8 saatte bir | 

İstediğiniz zaman, kullanıcılar Şirket portalı uygulamasını açın ve hemen profili güncelleştirmeleri denetlemek için cihazı eşitleyebilir.

Kullanıcı benzeşimi olmayan cihazlar için kaydı takip eden eşitleme sıklığı, bir gün veya daha fazlası için saat değişebilir. Intune, Intune hizmetine giriş kontrol etmek bir cihaz için belirli aralıklarla istek gönderir. Ancak iade etmek yine de cihaza kadar olabilir. İlk kayıttan sonra iade işlemini tamamlayabilmeniz için bir cihaz süresini tahmin edilemez. Ayrıca cihaz kaydı ve ilkeleri ve profilleri cihaza atanmış türüne bağlıdır. Cihazı kaydeder ve tüm ilk ilkeler uygulandıktan sonra cihaz genellikle 6-8 saatte bir yeni ilkeleri denetler.

## <a name="what-actions-cause-intune-to-immediately-send-a-notification-to-a-device"></a>Hangi eylemler cihaza Intune tarafından anında bildirim gönderilmesine neden olur?

Bunlar, ya da zamanlanmış iade sırasında denetlemek için bir bildirim aldığında cihazlar Intune hizmetine giriş kontrol edin. Ardından bir cihaz veya kullanıcı kilitleme, geçiş kodu sıfırlama, uygulama atama, profil veya ilke atama gibi bir eylemle hedeflediğinizde Intune bu güncelleştirmeleri almak için iade için cihaza hemen bildirir.

Şirket portalındaki kişi bilgilerinin düzeltilmesi gibi diğer değişiklikler, cihazlara anında bildirim gönderilmesine neden olmaz.

## <a name="if-multiple-policies-are-assigned-to-the-same-user-or-device-how-do-i-know-which-settings-gets-applied"></a>Aynı kullanıcı veya cihaza birden çok ilke atanıyorsa hangi ayarların uygulanacağını nasıl bilebilirim?

Aynı kullanıcı veya cihaza iki veya daha fazla ilke atandığında, geçerli ayar tek ayar düzeyinde yapılır:

- Uyumluluk İlkesi ayarları her zaman yapılandırma profili ayarlarından önceliklidir.

- Ardından bir uyumluluk İlkesi, başka bir uyumluluk ilkesindeki aynı ayarla karşılaştırılarak değerlendirilirse en kısıtlayıcı uyumluluk İlkesi ayarı uygulanır.

- Bir yapılandırma İlkesi ayarı çakışmaları başka bir yapılandırma İlkesi ayarı, bu çakışma Intune gösterilir. Bu çakışmaları el ile çözün.

## <a name="what-happens-when-app-protection-policies-conflict-with-each-other-which-one-is-applied-to-the-app"></a>Uygulama koruma ilkeleri birbiriyle çakışırsa ne olur? Uygulamaya hangisi uygulanır?

Çakışma değerleridir bir uygulama koruma ilkesi en kısıtlayıcı ayarlar *dışında* PIN sıfırlanmadan önce deneme gibi sayı giriş alanları için. Önerilen ayarlar seçeneğini kullanarak bir MAM ilkesi oluşturduğunuzda alacağı sayı giriş alanları aynı değerlere ayarlanır.

İki profil ayarı aynıysa çakışmalar meydana gelir. Örneğin, kopyala/yapıştır ayarı dışında birbirinin aynı olan iki MAM ilkesi yapılandırdığınızı düşünün. Bu senaryoda, kopyala/yapıştır ayarı en kısıtlayıcı değer olarak ayarlanır, ancak ayarların geri kalanı yapılandırıldığı gibi uygulanır.

Bir ilke, uygulamaya dağıtılan ve etkili olur. İkinci bir ilke dağıtılır. Bu senaryoda, ilk ilke öncelik kazanır ve görünür. İkinci ilkeyi bir çakışmayı gösterir. Her ikisi de aynı zamanda uygulanırsa, ilke, değilse yani sonra hem de çakışıyor. Çakışmadaki ayarlarda, en kısıtlayıcı olan değerler kullanılır.

## <a name="what-happens-when-ios-custom-policies-conflict"></a>iOS özel ilkeleri çakışırsa ne olur?

Intune, Apple yapılandırma dosyalarının veya özel bir Open Mobile Alliance Tekdüzen Kaynak Tanımlayıcısı (OMA-URI) ilkesinin yükünü değerlendirmez. Yalnızca bir teslim mekanizması olarak görev yapar.

Özel bir ilke atadığınızda, yapılandırılmış ayarlar ile uyumluluğu, yapılandırma veya diğer özel ilkelerle çakışmadığından emin olun. Özel bir ilke ve ayarları çakışırsa, ayarlar rastgele uygulanır.

## <a name="what-happens-when-a-profile-is-deleted-or-no-longer-applicable"></a>Bir profil silindiğinde veya artık geçerli olmadığında ne olur?

Profili sildiğinizde veya bir cihazı profile sahip bir gruptan kaldırdığınızda, profil ve ayarları CİHAZDAN açıklandığı kaldırılır:

- Wi-Fi, VPN, sertifika ve e-posta profilleri: Bu profiller tüm desteklenen kayıtlı cihazlardan kaldırılır.
- Diğer tüm profil türleri:  

  - **Windows ve Android cihazlarda**: Ayarlar CİHAZDAN kaldırılmaz
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

  - **iOS**: Tüm ayarlar kaldırılır, hariç:
  
    - Sesli dolaşıma izin ver
    - Veri dolaşımına izin ver
    - Dolaşım sırasında otomatik eşitlemeye izin ver

## <a name="i-changed-a-device-restriction-profile-but-the-changes-havent-taken-effect"></a>Cihaz kısıtlama profilini değiştirdim ama değişiklikler uygulanmadı

Windows Phone cihazları, bir kez ayarlandıktan sonra güvenlik ilkelerinin azaltılmasına, MDM veya EAS kullanarak ayarlamış izin vermez. Örneğin, bir **parolanın karakter sayısı alt sınırı** 8. 4'e indirmeyi deneyin. Zaten daha kısıtlayıcı bir profil cihaza uygulandı.

Profili daha az güvenli bir değerle değiştirmek için güvenlik ilkelerini sıfırlayın. Örneğin, Windows 8.1, masaüstünde sağdan içeri doğru kaydırın > seçin **ayarları** > **Denetim Masası**. **Kullanıcı Hesapları** uygulamasını seçin. Sol taraftaki gezinti menüsünde, var olan bir **güvenlik ilkelerini Sıfırla** bağlantı (alta doğru). Bunu seçin ve ardından **İlkeleri Sıfırla**’yı seçin.

Android, Windows Phone 8.1 ve üzeri, iOS ve Windows 10 gibi diğer MDM cihazlarında, devre dışı bırakılması ve içinde daha az kısıtlayıcı bir profil uygulamak için Intune'a kaydedilmesi gerekebilir.

## <a name="some-settings-in-a-windows-10-profile-return-not-applicable"></a>Bazı ayarlar Windows 10 profili "Uygulanamaz" döndürür

Bazı ayarlar Windows 10 cihazlarında "uygulanamaz" gösterebilir. Böyle bir durumda, bu ayar sürüm veya cihaz üzerinde çalışan Windows sürümü desteklenmiyor. Bu ileti, aşağıdaki nedenlerle oluşabilir:

- Ayar, yalnızca daha yeni sürümleri, Windows ve geçerli işletim sistemi (OS) sürümünü cihazda değil için kullanılabilir.
- Ayar, yalnızca belirli Windows sürümleri veya Home, Professional, Enterprise ve eğitim gibi belirli SKU'lara için kullanılabilir.

Sürüm ve farklı ayarlar için SKU gereksinimleri hakkında daha fazla bilgi için bkz: [yapılandırma hizmet sağlayıcısı (CSP) başvuru](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference).

## <a name="next-steps"></a>Sonraki adımlar

Ek yardım mı gerekiyor? Bkz. [Microsoft Intune için destek alma](get-support.md).
