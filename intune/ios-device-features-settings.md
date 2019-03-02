---
title: Microsoft Intune - Azure'da iOS cihaz özelliği ayarlarını | Microsoft Docs
description: Tüm ayarlar iOS cihazları için AirPrint, giriş ekranı, uygulama bildirimleri, paylaşılan cihaz, çoklu oturum açma ve web içeriği filtresi ayarları Microsoft Intune düzenini yapılandırmak için bkz. Bu ayarları bir cihaz yapılandırma profilinde de bu farklı Apple özellikleri, kuruluşunuzda kullanmak için iOS cihazları yapılandırmak için kullanın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/30/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: ''
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7176da8bf35265ecf16b72faf987a4dcf5e66e0e
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57235744"
---
# <a name="ios-device-feature-settings-in-intune"></a>ıntune'da iOS cihaz özelliği ayarları

Intune, iOS cihazlarında farklı Apple özellikleri kullanmak kullanıcıların bazı yerleşik ayarlarını içerir. Örneğin, yöneticiler iOS kullanıcıları AirPrint yazıcıları kullanımını denetlemek, uygulama ve klasörleri dock'a ekleyin ve sayfaları için giriş ekranınızdaki uygulama bildirimleri göster varlık etiket ayrıntıları kilit ekranında Göster, çoklu oturum açma kimlik doğrulaması kullanın ve kullanıcıların kimliğini Sertifikalar ile.

Bu makalede, bu ayarları listeler ve her ayarın ne yaptığını açıklar.

## <a name="before-you-begin"></a>Başlamadan önce

[İOS cihaz yapılandırma profili oluşturma](device-features-configure.md#create-a-device-profile).

## <a name="airprint-settings"></a>AirPrint ayarları

Bu özellik iOS bilinen AirPrint yazıcılarına yazdırma olanağı sağlar.

1. İçinde **ayarları**seçin **AirPrint**. AirPrint sunucunun aşağıdaki özellikleri girin:

    - **IP adresi**: Yazıcı IPv4 veya IPv6 adresini girin. Yazıcılar tanımlamak için konak adları kullanıyorsanız terminalde yazıcı ping göndererek IP adresini alabilirsiniz. [Yol ve IP adresi al](#get-the-ip-address-and-path) (Bu makalede) daha fazla ayrıntı sağlar.
    - **Yol**: Genellikle yoludur `ipp/print` ağınızdaki yazıcılar için. [Yol ve IP adresi al](#get-the-ip-address-and-path) (Bu makalede) daha fazla ayrıntı sağlar.
    - **Bağlantı noktası**: AirPrint hedefinin dinleme bağlantı noktasını girin. Bu özellik boş bırakırsanız AirPrint, varsayılan bağlantı noktasını kullanır. Kullanılabilir iOS 11.0 ve sonraki sürümleri.
    - **TLS**: Seçin **etkinleştirme** AirPrint bağlantılarını Aktarım Katmanı Güvenliği (TLS) ile güvenli hale getirmek için. Kullanılabilir iOS 11.0 ve sonraki sürümleri.

2. **Add (Ekle)** seçeneğini belirleyin. AirPrint sunucu listesine eklenir. Birçok AirPrint sunucuları ekleyebilirsiniz.

    Ayrıca **alma** bir virgülle ayrılmış dosyası (.csv bilgiler). Listeyi oluşturduktan sonra ayrıca **dışarı** AirPrint sunucuları listesi.

3. İşiniz bittiğinde seçin **Tamam** listenize kaydedin.

AirPrinter sunucuları eklemek için yazıcı, kaynak yolu ve bağlantı noktası IP adresi gerekir. Aşağıdaki adımlar bu bilgilerinin nasıl alınacağını gösterir.

1. AirPrint yazıcıları aynı yerel ağa (alt ağ) bağlı bir Mac üzerinde açın **Terminal** (gelen **/Applications/Utilities**).
2. Terminale `ippfind`, select girin.

    Yazıcı bilgilerini not edin. Örneğin, benzer bir şey döndürebilir `ipp://myprinter.local.:631/ipp/port1`. İlk bölümü yazıcı adıdır. Son bölümü (`ipp/port1`) ise kaynak yoludur.

3. Terminale `ping myprinter.local`, select girin.

   IP adresini not edin. Örneğin, benzer bir şey döndürebilir `PING myprinter.local (10.50.25.21)`.

4. IP adresine ve kaynak yolu değerleri kullanın. Bu örnekte IP adresidir `10.50.25.21`, ve kaynak yolu `/ipp/port1`.

## <a name="home-screen-layout-settings"></a>Giriş ekranı düzen ayarları

Bu ayarları uygulama düzenini ve klasörlerini dock ve giriş ekranlarını iOS cihazlarının yapılandırın. Bu özelliği kullanmak için iOS cihazlarının denetimli modda olması ve iOS 9.3 veya üzerini çalıştıran gerekir.

### <a name="dock"></a>Dock

Kullanım **Dock** en fazla altı öğe veya klasör, iOS ekranındaki dock kısmına için eklemek için ayarlar. Birçok cihaz daha az öğeyi destekler. Örneğin iPhone cihazlar en fazla dört öğeyi destekler. Bu durumda, cihazda yalnızca eklediğiniz ilk dört öğe gösterilmektedir.

1. İçinde **ayarları**seçin **giriş ekranı düzeni (yalnızca denetimli)** > **Dock** > **Ekle**. En fazla ekleyebilirsiniz **altı** ve cihaz dock'için (uygulama ve klasörleri birleştirilmiş) öğeleri.
2. İçinde **türü**, eklemek için bir **uygulama** veya **klasör**.

    - **Uygulama ekleme**: Uygulamalar ekranında dock eklemek için bu seçeneği belirleyin. Girin:

      - **Uygulama adı**: Uygulama için bir ad girin. Bu ad, Azure portalında başvuru amacıyla kullanılır. Bunu *değil* iOS cihazında gösterilen.
      - **Uygulama paketi kimliği**: Uygulamanın paket Kimliğini girin. Bkz: [yerleşik iOS uygulamaları için paket kimliklerini](#bundle-ids-for-built-in-ios-apps) (Bu makaledeki) ilgili bazı örnekler.

      Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

    - **Bir klasörü Ekle**: Dock ekranında bir klasör eklemek için bu seçeneği belirleyin. 

      Bir klasördeki bir sayfaya eklediğiniz uygulamaları soldan sağa ve aynı sırada listesi olarak düzenlenmiştir. Bir sayfaya alabileceğinden fazla uygulama eklerseniz, uygulamaları başka bir sayfaya taşınır.

      1. Girin bir **klasör adı**. Bu ad, kullanıcılara cihazlarında gösterilir.
      2. Seçin **Ekle**ve aşağıdaki özellikleri girin:

          - **Sayfa adı**: Sayfa için bir ad girin. Bu ad, Azure portalında başvuru amacıyla kullanılır. Bunu *değil* iOS cihazında gösterilen.
          - **Uygulama adı**: Uygulama için bir ad girin. Bu ad, Azure portalında başvuru amacıyla kullanılır. Bunu *değil* iOS cihazında gösterilen.
          - **Uygulama paketi kimliği**: Uygulamanın paket Kimliğini girin. Bkz: [yerleşik iOS uygulamaları için paket kimliklerini](#bundle-ids-for-built-in-ios-apps) (Bu makaledeki) ilgili bazı örnekler.

      3. Seçin **ekleme**. En fazla ekleyebilirsiniz **20** sayfaları için cihaz dock.
      4. Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

#### <a name="example"></a>Örnek

Aşağıdaki örnekte, dock ekranını yalnızca Safari, Mail ve borsa uygulamalarını gösterir. Posta uygulaması özelliklerini göstermek için seçilmiştir:

![Örnek iOS dock ayarları](./media/FfFiUcP.png)

İlkeyi bir İphone'a atadığınızda, dock aşağıdaki görüntüye benzer:

![iPhone’da örnek iOS dock düzeni](./media/bAgCe8F.png)

### <a name="pages"></a>Sayfaları

Giriş ekranında gösterilen istediğiniz sayfaları ve her sayfada görüntülenmesini istediğiniz uygulamaları ekleyin. Uygulamalar bir sayfaya ekleyin, soldan sağa doğru düzenlenir listesi olarak aynı sırada. Bir sayfaya alabileceğinden fazla uygulama eklerseniz, uygulamaları başka bir sayfaya taşınır.

> [!TIP]
> Herhangi bir giriş ekranı ve sayfalar listesine öğeleri yeniden sıralamak için sürükleyin ve bırakın.

1. İçinde **ayarları**seçin **giriş ekranı düzeni (yalnızca denetimli)** > **sayfaları** > **Ekle**. En fazla ekleyebilirsiniz **40** bir cihazda sayfaları.
2. Girin bir **sayfa adı**. Bu ad, Azure portalında başvuru amacıyla kullanılır ve *değil* iOS cihazında gösterilen. 

    **Add (Ekle)** seçeneğini belirleyin. En fazla ekleyebilirsiniz **60** bir cihazda (uygulamalar ve birleştirilmiş bir klasör) öğeleri.

3. İçinde **türü**, eklemek için bir **uygulama** veya **klasör**.

    - **Uygulama ekleme**: Uygulamalar ekranında bir sayfa eklemek için bu seçeneği belirleyin. Girin:

      - **Uygulama adı**: Uygulama için bir ad girin. Bu ad, Azure portalında başvuru amacıyla kullanılır. Bunu *değil* iOS cihazında gösterilen.
      - **Uygulama paketi kimliği**: Uygulamanın paket Kimliğini girin. Bkz: [yerleşik iOS uygulamaları için paket kimliklerini](#bundle-ids-for-built-in-ios-apps) (Bu makaledeki) ilgili bazı örnekler.

      Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

    - **Bir klasörü Ekle**: Dock ekranında bir klasör eklemek için bu seçeneği belirleyin. 

      Bir klasördeki bir sayfaya eklediğiniz uygulamaları soldan sağa ve aynı sırada listesi olarak düzenlenmiştir. Bir sayfaya alabileceğinden fazla uygulama eklerseniz, uygulamaları başka bir sayfaya taşınır.

      1. Girin bir **klasör adı**. Bu ad, kullanıcılara cihazlarında gösterilir.
      2. Seçin **Ekle**ve aşağıdaki özellikleri girin:

          - **Sayfa adı**: Sayfa için bir ad girin. Bu ad, Azure portalında başvuru amacıyla kullanılır. Bunu *değil* iOS cihazında gösterilen.
          - **Uygulama adı**: Uygulama için bir ad girin. Bu ad, Azure portalında başvuru amacıyla kullanılır. Bunu *değil* iOS cihazında gösterilen.
          - **Uygulama paketi kimliği**: Uygulamanın paket Kimliğini girin. Bkz: [yerleşik iOS uygulamaları için paket kimliklerini](#bundle-ids-for-built-in-ios-apps) (Bu makaledeki) ilgili bazı örnekler.

      3. Seçin **ekleme**.
      4. Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

#### <a name="example"></a>Örnek

Aşağıdaki örnekte adlı yeni bir sayfa **Contoso** eklenir. Sayfa arkadaşları Bul ve ayarlar uygulamalarını gösterir. Ayarlar uygulaması özelliklerini göstermek için seçilmiştir:

![iOS Giriş ekranı ayarları örneği](./media/Jc2OxyX.png)

İlkeyi bir İphone'a atadığınızda, sayfa aşağıdaki görüntüye benzer:

![Değiştirilmiş giriş ekranı ile iOS cihazı](./media/Bd37PHa.png)

## <a name="app-notifications-settings"></a>Uygulama bildirimleri ayarları

Bildirim gönderme iOS cihazları nasıl yüklü uygulamaları seçin. Bu ayarlar, iOS 9.3 ve üzerini çalıştıran denetimli cihazları destekler.

1. İçinde **ayarları**seçin **uygulama bildirimleri (yalnızca denetimli)** > **Ekle**:

    ![Intune iOS profiline uygulama bildirimi ekleme](./media/ios-macos-app-notifications.png)

2. Aşağıdaki özellikleri girin:

    - **Uygulama paket kimliği**: Girin **uygulama paket kimliği** eklemek istediğiniz uygulama. Bkz: [yerleşik iOS uygulamaları için paket kimliklerini](#bundle-ids-for-built-in-ios-apps) (Bu makaledeki) ilgili bazı örnekler.
    - **Uygulama adı**: Eklemek istediğiniz uygulamanın adını girin. Bu ad, Azure portalında başvuru amacıyla kullanılır. Bunu *değil* cihazda gösterilir.
    - **Yayımcı**: Eklediğiniz uygulama yayımcısının adını girin. Bu ad, Azure portalında başvuru amacıyla kullanılır. Bunu *değil* cihazda gösterilir.
    - **Bildirimleri**: **Etkinleştirme** veya **devre dışı** uygulamanın cihaza bildirim göndermesini.
       - **Bildirim merkezinde Göster**: **Etkinleştirme** cihaz bildirim merkezinde bildirimler göstermesine izin verir. **Devre dışı** uygulama bildirimlerini bildirim merkezi aracılığıyla göstermesini engeller.
       - **Kilit ekranında Göster**: Seçin **etkinleştirme** cihaz kilitleme ekranında uygulama bildirimlerini görmek için. **Devre dışı** kilit ekranında bildirimleri göstermesini uygulamayı engeller.
       - **Uyarı türü**: Cihaz kilidi nasıl bildirim gösterilen seçin. Seçenekleriniz şunlardır:
         - **Hiçbiri**: Bildirim gösterilir.
         - **Başlık**: Bir başlık kısaca bir bildirim ile gösterilir.
         - **Kalıcı**: Bir bildirim gösterilir ve kullanıcının bunu el ile cihazı kullanmaya devam etmeden önce kapatması gerekir.
       - **Uygulama simgesi üzerindeki rozet**: Seçin **etkinleştirme** uygulama simgesine rozet eklemek için. Rozet, uygulamanın bildirim gönderdiğini anlamına gelir.
       - **Ses**: Seçin **etkinleştirme** bir bildirim iletildiğinde ses çalınması için.

3. Değişikliklerinizi kaydetmek için **Tamam**’ı seçin. İstediğiniz uygulamalar eklemeye devam edebilirsiniz. İşiniz bittiğinde seçin **Tamam**.

## <a name="lock-screen-message-settings"></a>Kilit ekranı iletisi ayarları

Oturum açma penceresinde ve kilit ekranı bir özel ileti veya metin göstermek için bu ayarları kullanın. Örneğin, "Kaybedildiğinde dönmek..." iletisi girebilirsiniz ve varlık etiketi bilgileri. 

Bu özellik çalıştıran denetimli cihazları destekler:

- iOS 9.3 ve üzeri

1. İçinde **ayarları**seçin **kilit ekranı iletisi (yalnızca denetimli)**.
2. Aşağıdaki ayarları girin:

    - **Varlık etiketi bilgileri**: Cihazın varlık etiketi hakkındaki bilgileri girin. Örneğin `Owned by Contoso Corp` veya `Serial Number: {{serialnumber}}` girin. 

      Girdiğiniz metin, oturum açma penceresinde ve kilit ekranında cihazın gösterilir.

    - **Kilit ekranı dipnotu**: Cihaz kaybolur veya çalınırsa, döndürülen cihaz alınmasına yardımcı olabilecek bir not girin. İstediğiniz herhangi bir metin girebilirsiniz. Örneğin `If found, call Contoso at ...` gibi bir URI girebilirsiniz.

    Cihaz belirteçleri, cihaza özgü bilgiler için bu alanları eklemek için de kullanılabilir. Örneğin, seri numarası göstermek için girin `Serial Number: {{serialnumber}}`. Kilit ekranında, metin benzer gösterir `Serial Number 123456789ABC`. Değişkenleri girerken, süslü ayraçlar kullanmaya özen `{{ }}`. [Uygulama yapılandırma belirteçleri](app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) kullanılabilen değişkenleri bir listesini içerir. Ayrıca `deviceName` veya başka bir cihaza özgü değer.

    > [!NOTE]
    > Değişkenleri kullanıcı Arabiriminde doğrulanmış değil. Sonuç olarak, hatalı giriş ile kaydedilen profilleri görebilirsiniz. Örneğin, girerseniz `{{Devicename}}` yerine `{{devicename}}`, cihazın benzersiz adı yerine sabit dizesini gösterilir.

3. İşiniz bittiğinde seçin **Tamam** yaptığınız değişiklikleri kaydedin.

## <a name="single-sign-on-settings"></a>Çoklu oturum açma ayarları

İş Kolu (LOB) uygulamalarının çoğunda güvenliği desteklemek için belirli bir düzeyde kullanıcı kimlik doğrulaması gereklidir. Çoğu durumda, kullanıcılar için bozucu olduğu, tekrar tekrar aynı kimlik bilgilerini girmek kullanıcı kimlik doğrulaması gerektirir. Kullanıcı deneyimini artırmak için geliştiriciler çoklu oturum açma (SSO) kullanan uygulamalar oluşturabilirsiniz. Çoklu oturum açma kullanarak bir kullanıcının kimlik bilgilerini girmesi sayısını azaltır.

Çoklu oturum açmayı kullanmak için sahip olduğunuzdan emin olun:

- Çoklu oturum açma cihazdaki kullanıcı kimlik bilgileri deposunu aramak için kodlanmış bir uygulama.
- Intune'u iOS cihazında çoklu oturum açma için yapılandırma.

1. İçinde **ayarları**seçin **çoklu oturum açma**:

   ![Çoklu Oturum Açma bölmesi](./media/sso-blade.png)

2. Aşağıdaki ayarları girin:

    - **Aad'den kullanıcı adı özniteliği**: Intune bu öznitelik her kullanıcı için Azure AD'de arar. Intune, cihaza yüklenen XML oluşturmadan önce ilgili alanı (UPN gibi) sonra doldurur. Seçenekleriniz şunlardır:

      - **Kullanıcı asıl adı**: UPN, aşağıdaki şekilde ayrıştırılır:

        ![Kullanıcı adı özniteliği](media/User-name-attribute.png)

        Ayrıca, **Bölge** metin kutusuna girdiğiniz metinle bölge değerinin üzerine yazabilirsiniz.

        Örneğin, Contoso Avrupa, Asya ve Kuzey Amerika gibi çeşitli bölgeleri vardır. Contoso Asya kullanıcılarının SSO kullanmak istiyorsa ve uygulama UPN gerektirir `username@asia.contoso.com` biçimi. Seçtiğinizde, **kullanıcı asıl adı**, her kullanıcı için bir bölge olduğundan, Azure AD'den alınmış `contoso.com`. Asya'daki kullanıcılar için bu nedenle seçin **kullanıcı asıl adı**girin `asia.contoso.com`. Son kullanıcının UPN olur `username@asia.contoso.com`, yerine `username@contoso.com`.

      - **Intune cihaz kimliği**: Intune, Intune cihaz kimliğini otomatik olarak seçer

        Varsayılan olarak, uygulamaların yalnızca cihaz kimliğini kullanması gerekir. Ancak, uygulamanız, bölge ve cihaz Kimliğini kullanıyorsa, bölge bölge metin kutusuna yazabilirsiniz.

        > [!NOTE]
        > Varsayılan olarak, cihaz kimliğini kullanıyorsanız bölgeyi boş bırakın.

      - **Azure AD cihaz kimliği**

    - **Bölge**: URL'nin etki alanı bölümünü girin. Örneğin, şunu girin: `contoso.com`.
    - **Çoklu oturum açma kullanacak URL ön ekleri**: **Ekleme** kullanıcı çoklu oturum açma kimlik doğrulaması gerektiren herhangi bir URL kuruluşunuzdaki.

        Örneğin, kullanıcı bu sitelerden birine bağlandığında iOS cihaz çoklu oturum açma kimlik bilgilerini kullanır. Kullanıcının başka kimlik bilgisi girmesi gerekmez. Çok faktörlü kimlik doğrulamasını etkinleştirdiyseniz, kullanıcıların ikinci kimlik doğrulamasını girmesi gerekmez.

        > [!NOTE]
        > Bu URL'ler düzgün biçimlendirilmiş FQDN'ler olmalıdır. Apple olması için bu gerektirir `http://<yourURL.domain>` biçimi.

        URL eşleştirme desenleri `http://` veya `https://` ile başlamalıdır. Basit dize eşleştirme çalıştırılır, böylece `http://www.contoso.com/` URL ön eki eşleşmiyor `http://www.contoso.com:80/`. İOS 10.0 veya üzeri, tek bir joker karakter \* tüm eşleşen değerleri girmek için kullanılabilir. Örneğin, `http://*.contoso.com/` hem de eşleşen `http://store.contoso.com/` ve `http://www.contoso.com`.

        `http://.com` Ve `https://.com` desenlerle eşleşmelerine tüm HTTP ve HTTPS URL'leri, sırasıyla.

    - **Çoklu oturum açma kullanan uygulamalar**: **Ekleme** kullanabilirsiniz, son kullanıcıların cihazlarında uygulamalar çoklu oturum açma.

        `AppIdentifierMatches` Dizi, uygulama paketi grubu kimlikleriyle eşleşen dizeler içermelidir. Bu dizeler tam eşleşme gibi olabilir `com.contoso.myapp`, ön ek eşleştirmesi kullanarak paket kimliği girin veya \* joker karakter. Joker karakter, nokta karakteri (.) sonra gelmelidir ve dizenin sonunda gibi yalnızca bir kez görünebilir `com.contoso.*`. Joker karakter eklendiğinde, paket kimlikleri bu ön ekle başlayan tüm uygulamaların hesaba erişimine izin verilir.

        **Uygulama Adı**’nı kullanarak paket kimliğini ayırt etmenize yardımcı olacak bir kolay ad ekleyin.

    - **Kimlik bilgileri yenileme sertifikası**: (Parola) kimlik doğrulaması için sertifikalar kullanılıyorsa, kimlik doğrulama sertifikası var olan SCEP veya PFX sertifikasını seçin. Genellikle, bu sertifika, kullanıcıya VPN, Wi-Fi veya e-posta gibi diğer profiller için dağıtılan aynı sertifikadır.

3. İşiniz bittiğinde seçin **Tamam** yaptığınız değişiklikleri kaydedin.

## <a name="web-content-filter-settings"></a>Web içeriği filtresi ayarları

Bu ayarlar, iOS cihazlarında tarayıcı URL erişimini denetler.

1. İçinde **ayarları**seçin **Web içerik filtresi (yalnızca denetimli)**.
2. Seçin **filtre türü**. Seçenekleriniz şunlardır:

    - **URL'leri yapılandırma**: Küfür ve cinsel içerikli terimleri için Apple'nın yerleşik web filtresini kullanın. Yüklendiğinde tanımlar ve uygunsuz içeriği engeller gibi bu özellik, her web sayfasını değerlendirir. Ayrıca, filtre tarafından iade istemediğiniz URL'leri de ekleyebilirsiniz. Veya, Apple'nın filtresi ayarlarına bakılmaksızın belirli URL'leri engelleyebilirsiniz.

      - **İzin verilen URL'ler**: **Ekleme** izin vermek istediğiniz URL'leri. Bu URL'ler, Apple web filtresi atlama.

        > [!NOTE]
        > Girdiğiniz URL'lere Apple web filtresi tarafından evauluated istemediğiniz URL'ler ' dir. Bu URL'ler izin verilen web sitelerinin bir listesi değildir. İzin verilen Web siteleri listesini oluşturmak için **filtre türü** için **yalnızca belirli Web siteleri**.

        Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

      - **Engellenen URL'ler**: **Ekleme** Apple web filtresi ayarlarına bakılmaksızın açılmasını durdurmak istediğiniz URL'leri.

        Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

    - **Yalnızca belirli Web siteleri** (için Safari web tarayıcısı yalnızca): Bu URL'ler Safari tarayıcısının yer işaretlerine eklenir. Kullanıcı **yalnızca** bu siteleri; ziyaret etmesine izin başka sitelere açılabilir. Bu seçeneği yalnızca kullanıcıların erişebileceği URL'lerin tam listesini biliyorsanız kullanın.

      - **URL**: İzin vermek istediğiniz Web sitesinin URL'sini girin. Örneğin, şunu girin: `https://www.contoso.com`.
      - **Yer işareti yolu**: Yer işareti depolamak için bir yol girin. Örneğin, şunu girin: `/Contoso/Business Apps`. Bir yol eklemezseniz yer işareti cihazdaki varsayılan yer işareti klasörüne eklenir.
      - **Başlık**: Yer işareti için açıklayıcı bir başlık girin.

      Herhangi bir URL girmeyin sonra son kullanıcıların dışındaki Web sitelerine erişemez `microsoft.com`, `microsoft.net`, ve `apple.com`. Bu URL'lere Intune tarafından otomatik olarak izin verilir.

      Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="wallpaper-settings"></a>Duvar kağıdı ayarları

Denetimli iOS cihazlarınıza özel bir .png, .jpg veya .jpeg görüntüsü ekleyin. Örneğin, bir şirket logosu, kilit ekranında kullanın.

Mevcut bir görüntüyü cihazlarla görüntü ile bir profili atandığında beklenmeyen davranışlarla karşılaşabilirsiniz. Örneğin, bir görüntü olmadan bir profil oluşturun. Bu profil bir görüntüsüne zaten sahip cihazlara atanır. Bu senaryoda, cihaz varsayılan görüntü değişebilir veya özgün resmin cihazda haberdar olun. Bu davranış denetlenen ve Apple'nın MDM platformu tarafından sınırlı.

- **Görüntü konumu duvar kağıdı**: Cihazdaki resim göstermek için bir konum seçin. Seçenekleriniz şunlardır:
  - **Yapılandırılmamış**: Özel bir görüntü cihaza eklenmez. Cihaz işletim sistemi varsayılan kullanır.
  - **Kilit ekranında**: Görüntü Kilit ekranına ekler.
  - **Giriş ekranı**: Görüntü giriş ekranına ekler.
  - **Kilit ekranı ve giriş ekranındaki**: Kilit ekranı ve giriş ekranı görüntünün aynısını kullanır.
- **Duvar kağıdı resmi**: Bir mevcut .png, .jpg veya .jpeg görüntü kullanmak istediğiniz karşıya yükleyin. Dosya boyutu 750 KB'den daha az olduğundan emin olun. Ayrıca **Kaldır** eklediğiniz bir resmi.

> [!TIP]
> Farklı kilit ekranı ve giriş ekranı görüntüler için kilitlenme ekranı görüntüsü ile bir profil oluşturun. Giriş ekranı görüntüyü başka bir profil oluşturun. Her iki profili, iOS kullanıcı veya cihaz grubuna atayın.

## <a name="bundle-ids-for-built-in-ios-apps"></a>Yerleşik iOS uygulamaları için paket kimlikleri

Aşağıdaki liste, bazı yaygın yerleşik iOS uygulamalarının paket kimliğini gösterir. Diğer uygulamaların paket kimliğini bulmak için yazılım satıcınıza başvurun.

|||
|-|-|
|Uygulama adı|Paket Kimliği|
|Uygulama Mağazası|com.apple.AppStore|
|Hesap Makinesi|com.apple.calculator|
|Takvim|com.apple.mobilecal|
|Kamera|com.apple.camera|
|Saat|com.apple.mobiletimer|
|Pusula|com.apple.compass|
|Kişiler|com.apple.MobileAddressBook|
|FaceTime|com.apple.facetime|
|Arkadaşları Bul|com.apple.mobileme.fmf1|
|iPhone’u Bul|com.apple.mobileme.fmip1|
|Oyun Merkezi|com.apple.gamecenter|
|GarageBand|com.apple.mobilegarageband|
|Sistem Durumu|com.apple.Health|
|iBooks|com.apple.iBooks|
|iTunes Store|com.apple.MobileStore|
|iTunes U|com.apple.itunesu|
|Keynote|com.apple.Keynote|
|Mail|com.apple.mobilemail|
|Harita|com.apple.Maps|
|İletiler|com.apple.MobileSMS|
|Müzik|com.apple.Music|
|News|com.apple.news|
|Notlar|com.apple.mobilenotes|
|Sayılar|com.apple.Numbers|
|Pages|com.apple.Pages|
|Photo Booth|com.apple.Photo-Booth|
|Fotoğraflar|com.apple.mobileslideshow|
|Podcast’ler|com.apple.podcasts|
|Anımsatıcılar|com.apple.reminders|
|Safari|com.apple.mobilesafari|
|Ayarlar|com.apple.Preferences|
|Borsa|com.apple.stocks|
|İpuçları|com.apple.tips|
|Videolar|com.apple.videos|
|Sesli Notlar|com.apple.VoiceMemos|
|Wallet|com.apple.Passbook|
|Watch|com.apple.Bridge|
|Hava Durumu|com.apple.weather|

## <a name="next-steps"></a>Sonraki adımlar

[Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).

Cihaz özelliği profillerini oluşturabilirsiniz [macOS](macos-device-features-settings.md) cihazlar.
