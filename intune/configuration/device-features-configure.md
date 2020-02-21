---
title: Microsoft Intune-Azure ile iOS/ıpados veya macOS cihaz profili oluşturma | Microsoft Docs
description: İOS, ıpados veya macOS cihaz profili ekleyin veya oluşturun ve ardından Microsoft Intune ' deki AirPrint, ana ekran düzeni, uygulama bildirimleri, paylaşılan cihaz, çoklu oturum açma ve Web içerik filtresi ayarları ayarlarını yapılandırın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/18/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 52c31cc7d3949b42251d3e45075864762cda6930
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77513155"
---
# <a name="add-ios-ipados-or-macos-device-feature-settings-in-intune"></a>Intune 'da iOS, ıpados veya macOS cihaz özelliği ayarları ekleme

Intune, yöneticilerin iOS, ıpados ve macOS cihazlarını denetlemesine yardımcı olan birçok özellik ve ayarı içerir. Örneğin, yöneticiler şunları yapabilir:

- Kullanıcılarınızın ağınızdaki AirPrint yazıcılara erişmesine izin ver
- Yeni sayfa ekleme dahil olmak üzere giriş ekranına uygulama ve klasör ekleme
- Uygulama bildirimlerinin gösterilip gösterilmeyeceğini ve nasıl gösterileceğini seçin
- Kilit ekranını, özellikle paylaşılan cihazlar için bir ileti veya varlık etiketi gösterecek şekilde yapılandırın
- Kullanıcılara kimlik bilgilerini uygulamalar arasında paylaşmak için güvenli bir çoklu oturum açma deneyimi sağlayın
- Yetişkinlere yönelik dil kullanan ve belirli Web sitelerine izin veren veya engelleyen web sitelerini filtrele

Intune, kuruluşunuzun ihtiyaçlarına göre bu ayarları oluşturmak ve özelleştirmek için "yapılandırma profillerini" kullanır. Bu özellikleri bir profile ekledikten sonra, profili kuruluşunuzdaki iOS/ıpados ve macOS cihazlarına gönderirsiniz veya dağıtabilirsiniz.

Bu makalede yapılandırabileceğiniz farklı özellikler açıklanmakta ve bir cihaz yapılandırma profili nasıl oluşturacağınız gösterilmektedir. [İOS/ıpados](ios-device-features-settings.md) ve [MacOS](macos-device-features-settings.md) cihazları için kullanılabilir tüm ayarları da görebilirsiniz.

## <a name="airprint"></a>AirPrint

AirPrint, cihazların bir kablosuz ağ üzerinden dosyalara yazdırmasını sağlayan bir Apple özelliğidir. Intune 'da cihazlara AirPrint bilgilerini ekleyebilirsiniz.

Intune 'da yapılandırabileceğiniz ayarların listesi için bkz. [macOS](macos-device-features-settings.md#airprint)'ta [IOS/ıpados ve AirPrint üzerinde AirPrint](ios-device-features-settings.md#airprint) .

AirPrint hakkında daha fazla bilgi için Apple 'ın Web sitesinde [AirPrint hakkında](https://support.apple.com/HT201311) bölümüne bakın.

Uygulama hedefi:

- iOS 7,0 ve üzeri
- ıpados 13,0 ve üzeri
- macOS 10,10 ve üzeri

## <a name="app-notifications"></a>Uygulama bildirimleri

İOS ve ıpados cihazlarınızdaki uygulamaların nasıl bildirim alacağını seçin. Örneğin, Intune 'dan bildirim merkezinde göstermek, kilit ekranında göstermek veya ses çalmak için uygulama bildirimleri gönderin.

Intune 'da yapılandırabileceğiniz ayarların listesi için bkz. [iOS/ıpados üzerinde uygulama bildirimleri](ios-device-features-settings.md#app-notifications).

Bu özellik hakkında daha fazla bilgi için bkz. Apple 'ın Web sitesindeki [Bildirimler](https://developer.apple.com/notifications/) .

Uygulama hedefi:

- iOS 9,3 ve üzeri
- ıpados 13,0 ve üzeri

## <a name="associated-domains"></a>İlişkili etki alanları

İlişkili etki alanları, etki alanlarınız arasında `contoso.com`ve uygulamalarınız arasında bir ilişki oluşturmanıza olanak sağlar. Bu özellik şunları yapmanıza olanak sağlar:

- Kuruluşunuzdaki uygulamalar ve Web siteleri arasında veri paylaşma ve oturum açma kimlik bilgileri.
- Çoklu oturum açma uygulaması uzantısı, evrensel bağlantılar ve parola otomatik doldurma gibi Web sitenize dayalı uygulama özelliklerini kullanın.

  Örneğin, parola otomatik olarak, uygulamanızla ilişkili Web siteleri için parola gibi kimlik bilgilerini önermeye izin vermek üzere, ilişkili bir etki alanı oluşturun.

Intune 'da yapılandırabileceğiniz ayarların listesi için bkz. [macOS 'Ta ilişkili etki alanları](macos-device-features-settings.md#associated-domains).

Bu özellik hakkında daha fazla bilgi için bkz. Apple 'ın Web sitesinde [bir uygulamanın Ilişkili etki alanlarını ayarlama](https://developer.apple.com/documentation/security/password_autofill/setting_up_an_app_s_associated_domains) .

Uygulama hedefi:

- macOS 10,15 ve üzeri

## <a name="home-screen-layout"></a>Giriş ekranı düzeni

Bu ayarlar, iOS ve ıpados cihazlarında yerleştirme ve giriş ekranlarındaki uygulama düzeni ve klasörlerini yapılandırır. Şunları yapabilirsiniz:

- Ekrana uygulama veya klasör eklemek için **yerleştirme** ayarlarını kullanın. Örneğin, cihaz Dock 'da Safari ve posta uygulamasını görüntüleyin.
- Giriş ekranında görünmesini istediğiniz **sayfaları** ve her sayfada görünmesini istediğiniz uygulamaları ekleyin. Örneğin, bir **contoso** sayfası ekleyin ve Ayarlar uygulamasını bu sayfaya ekleyin.

Intune 'da yapılandırabileceğiniz ayarların listesi için bkz. [iOS/ıpados üzerinde giriş ekranı düzeni](ios-device-features-settings.md#home-screen-layout).

Uygulama hedefi:

- iOS 9,3 ve üzeri
- ıpados 13,0 ve üzeri

## <a name="lock-screen-message"></a>Kilit ekranı iletisi

Oturum açma penceresinde ve kilit ekranında özel bir ileti veya metin göstermek için bu ayarları kullanın. Örneğin, bir "kaybolursa, return to..." girebilirsiniz. ileti ve varlık etiketi bilgilerini göster.

Intune 'da yapılandırabileceğiniz ayarların listesi için bkz. [iOS/ıpados üzerinde kilit ekranı ileti ayarları](ios-device-features-settings.md#lock-screen-message).

Kilit ekranı Iletisi hakkında daha fazla bilgi için bkz. Apple 'ın Web sitesinde [Lockscreenmessage](https://developer.apple.com/documentation/devicemanagement/lockscreenmessage) .

Uygulama hedefi:

- iOS 9,3 ve üzeri
- ıpados 13,0 ve üzeri

## <a name="login-items"></a>Oturum açma öğeleri

Kullanıcılar cihazlarda oturum açtıklarında açık olan uygulamaları, özel uygulamaları, dosyaları ve klasörleri seçmek için bu özelliği kullanın.

Intune 'da yapılandırabileceğiniz ayarların listesi için bkz. [macOS 'Ta oturum açma öğeleri](macos-device-features-settings.md#login-items).

Uygulama hedefi:

- macOS 10,13 ve üzeri

## <a name="login-window"></a>Oturum açma penceresi

Oturum açmadan önce kullanıcılara sunulan oturum açma ekranının ve işlevlerinin görünümünü denetleyin. Örneğin, özel bir iletiyle bir başlık ekleyin, uyku düğmesinin gösterilip gösterilmeyeceğini ve daha fazlasını yapın.

Intune 'da yapılandırabileceğiniz ayarların listesi için bkz. [macOS 'Ta oturum açma penceresi](macos-device-features-settings.md#login-window).

Uygulama hedefi:

- macOS 10,7 ve üzeri

## <a name="single-sign-on"></a>Çoklu oturum açma

İş Kolu (LOB) uygulamalarının çoğunda güvenliği desteklemek için belirli bir düzeyde kullanıcı kimlik doğrulaması gereklidir. Çoğu durumda, kimlik doğrulaması kullanıcının aynı kimlik bilgilerini tekrar tekrar girmesini gerektirir. Geliştiriciler, Kullanıcı deneyimini geliştirmek için çoklu oturum açma (SSO) kullanan uygulamalar oluşturabilir. Çoklu oturum açma kullanımı, bir kullanıcının kimlik bilgilerini girmesi gereken kaç kez azaltığını azaltır.

Çoklu oturum açma 'yı kullanmak için, şunları yaptığınızdan emin olun:

- Cihazdaki çoklu oturum açma bölümünde Kullanıcı kimlik bilgileri deposunu aramak için kodlanmış bir uygulama.
- İOS/ıpados cihaz çoklu oturum açma için Intune yapılandırıldı.

![Çoklu Oturum Açma bölmesi](./media/device-features-configure/sso-blade.png)

Intune 'da yapılandırabileceğiniz ayarların listesi için bkz. [iOS 'Ta çoklu oturum açma/ıpados](ios-device-features-settings.md#single-sign-on).

Uygulama hedefi:

- iOS 7,0 ve üzeri
- ıpados 13,0 ve üzeri

## <a name="single-sign-on-app-extension"></a>Çoklu oturum açma uygulama uzantısı

Bu ayarlar iOS, ıpados ve macOS cihazlarınız için çoklu oturum açma (SSO) sağlayan bir uygulama uzantısı yapılandırır. Çoğu Iş kolu (LOB) uygulamaları ve kuruluş web siteleri, bazı düzeyde güvenli Kullanıcı kimlik doğrulaması gerektirir. Çoğu durumda, kimlik doğrulama kullanıcıların aynı kimlik bilgilerini tekrar tekrar girmesini gerektirir. SSO, kullanıcılara kimlik bilgilerini bir kez girdikten sonra uygulamalara ve Web sitelerine erişim sağlar. Oturum açtıktan sonra kullanıcılar uygulamalara ve Web sitelerine otomatik olarak erişebilir veya erişim kazanmak için yüz KIMLIĞI, Touch ID veya Apple geçiş kodunu kullanabilir.

Intune 'da, kuruluşunuz, kimlik sağlayıcınız veya Apple tarafından oluşturulan bir SSO AP uzantısını yapılandırmak için bu ayarları kullanın. SSO uygulama uzantısı kullanıcılarınız için kimlik doğrulamasını işler. Bu ayarlar, yeniden yönlendirme türü ve kimlik bilgisi türü SSO uygulama uzantılarını yapılandırır.

- Yeniden yönlendirme türü, OAuth ve SAML2 gibi modern kimlik doğrulama protokolleri için tasarlanmıştır.
- Kimlik bilgisi türü, sınama ve yanıt kimlik doğrulama akışları için tasarlanmıştır. Apple tarafından sunulan Kerberos 'a özgü kimlik bilgisi uzantısı ve genel kimlik bilgisi uzantısı arasında seçim yapabilirsiniz.

Intune 'da yapılandırabileceğiniz ayarların listesi için bkz. [iOS/ıpados SSO uygulama uzantısı](ios-device-features-settings.md#single-sign-on-app-extension) ve [MacOS SSO uygulama uzantısı](macos-device-features-settings.md#single-sign-on-app-extension).

SSO uygulama uzantısı geliştirme hakkında daha fazla bilgi için Apple 'ın Web sitesinde [Genişletilebilir Kurumsal SSO](https://developer.apple.com/videos/play/tech-talks/301) 'yu izleyin. Apple 'ın özelliğin açıklamasını okumak için [Çoklu oturum açma uzantıları yük ayarlarını](https://support.apple.com/guide/mdm/single-sign-on-extensions-mdmfd9cdf845/web)ziyaret edin. 

> [!NOTE]
> **Çoklu oturum açma uygulama uzantısı** özelliği, **Çoklu oturum açma** özelliğinden farklı:
>
> - **Çoklu oturum açma uygulama uzantısı** ayarları, ıdos 13,0 (ve üzeri), iOS 13,0 (ve üzeri) ve macos 10,15 (ve üzeri) için geçerlidir. **Çoklu oturum açma** ayarları, ıdos 13,0 (ve üzeri) ve iOS 7,0 ve daha yeni bir sürümü için geçerlidir.
>
> - **Çoklu oturum açma uygulama uzantısı** ayarları, sorunsuz bir kurumsal oturum açma deneyimi sunmak üzere kimlik sağlayıcıları veya kuruluşlar tarafından kullanılacak uzantıları tanımlar. **Çoklu oturum açma** ayarları, kullanıcıların sunuculara veya uygulamalara erişim zamanı için Kerberos hesap bilgilerini tanımlar.
>
> - **Çoklu oturum açma uygulama uzantısı** , kimlik doğrulaması için Apple işletim sistemini kullanır. Bu nedenle, **Çoklu oturum açma**özelliğinden daha iyi bir son kullanıcı deneyimi sağlayabilir.
>
> - **Çoklu oturum açma uygulama uzantısı**ile bir geliştirme perspektifinden, herhangi bir YENIDEN yönlendirme SSO veya KIMLIK bilgisi SSO kimlik doğrulaması türü kullanabilirsiniz. **Çoklu oturum açma**Ile yalnızca Kerberos SSO kimlik doğrulamasını kullanabilirsiniz.
>
> - Kerberos **Çoklu oturum açma uygulaması uzantısı** Apple tarafından geliştirilmiştir ve IOS/ıpados 13.0 + ve MacOS 10.15 + platformlarında yerleşiktir. Yerleşik Kerberos uzantısı, kullanıcıları, Kerberos kimlik doğrulamasını destekleyen yerel uygulamalar ve web sitelerinde günlüğe kaydetmek için kullanılabilir. **Çoklu oturum açma** , Kerberos 'un bir Apple uygulamasıdır.
>
> - Yerleşik Kerberos **Çoklu oturum açma uygulaması uzantısı** , Web sayfaları ve uygulamaları Için yalnızca **Çoklu oturum**açma gibi Kerberos sorunlarını işler. Bununla birlikte, yerleşik Kerberos uzantısı, parola değişikliklerini destekler ve kurumsal ağlarda daha iyi davranır. Kerberos **Çoklu oturum açma uygulaması uzantısı** ve **Çoklu oturum açma**arasında karar verirken, gelişmiş performans ve yetenekler nedeniyle uzantının kullanılmasını öneririz.

Uygulama hedefi:

- iOS 13,0 ve üzeri
- ıpados 13,0 ve üzeri
- macOS 10,15 ve üzeri

## <a name="wallpaper"></a>Duvar

Denetimli iOS/ıpados cihazlarınıza özel bir. png,. jpg veya. JPEG görüntüsü ekleyin. Örneğin, cihazlarınızdaki kilit ekranına bir şirket logosu eklemek için Intune ' u kullanın.

Intune 'da yapılandırabileceğiniz ayarların listesi için bkz. [iOS/ıpados üzerinde duvar kağıdı](ios-device-features-settings.md#wallpaper).

Uygulama hedefi:

- iOS
- ıpados 13,0 ve üzeri

## <a name="web-content-filter"></a>Web içeriği filtresi

Bu ayarlar Apple 'ın yerleşik otomatik filtre algoritmasını, Web sayfalarını değerlendirmek ve yetişkinlere yönelik içeriği ve yetişkinlere yönelik dili engellemek için kullanabilir. Ayrıca, izin verilen Web bağlantıları ve kısıtlanmış Web bağlantıları listesini de oluşturabilirsiniz. Örneğin, yalnızca `contoso` Web sitelerinin açmasına izin verebilirsiniz.

Intune 'da yapılandırabileceğiniz ayarların listesi için bkz. [iOS/ıpados 'Ta Web içeriği filtresi](ios-device-features-settings.md#web-content-filter).

Uygulama hedefi:

- iOS 7,0 ve üzeri
- ıpados 13,0 ve üzeri

## <a name="create-a-device-profile"></a>Bir cihaz profili oluşturma

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. **Profil oluşturma** > **yapılandırma profilleri** > **cihazları** seçin.
3. Aşağıdaki özellikleri girin:

    - **Ad**: ilke için açıklayıcı bir ad girin. İlkelerinizi daha sonra kolayca tanıyacak şekilde adlandırın. Örneğin, iyi bir ilke adı **MacOS: oturum açma ekranını yapılandırır**.
    - **Açıklama**: Profil için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
    - **Platform**: cihazlarınızın platformunu seçin. Seçenekleriniz şunlardır:  
        - **iOS/ıpados**
        - **macOS**
    - **Profil türü**: **Cihaz özellikleri**'ni seçin.

4. Seçtiğiniz platforma bağlı olarak, yapılandırabileceğiniz ayarlar farklılık gösterir. Ayrıntılı ayarlar için platformunuzu seçin:

    - [iOS/ıpados](ios-device-features-settings.md)
    - [macOS](macos-device-features-settings.md)

5. İşiniz bittiğinde **Tamam** > **Oluştur**’u seçerek değişikliklerinizi kaydedin.

Profil oluşturulur ve profiller listesinde gösterilir. [Profili atayıp](device-profile-assign.md) [durumunu izlemeyi](device-profile-monitor.md)unutmayın.

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturulduktan sonra atanmak için hazırlanın. Ardından [profili atayın](device-profile-assign.md) ve [durumunu izleyin](device-profile-monitor.md).

[İOS/ıpados](ios-device-features-settings.md) ve [MacOS](macos-device-features-settings.md) cihazları için tüm cihaz özelliği ayarlarını görüntüleyin.
