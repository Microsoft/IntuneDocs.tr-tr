---
title: Microsoft Intune-Azure 'da iOS cihaz özelliği ayarları | Microsoft Docs
description: İOS cihazlarını AirPrint için yapılandırma, giriş ekranı düzeni, uygulama bildirimleri, paylaşılan cihaz, çoklu oturum açma ve Microsoft Intune ' deki Web içeriği filtresi ayarları için tüm ayarları görüntüleyin. Bu ayarları, kuruluşunuzda bu Apple özelliklerini kullanmak üzere iOS cihazlarını yapılandırmak için bir cihaz yapılandırma profilinde kullanın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/16/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: ''
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7eaed88adc8603ee1f79f47cbd94eec1c3b71b95
ms.sourcegitcommit: c19584b36448bbd4c8638d7cab552fe9b3eb3408
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/20/2019
ms.locfileid: "71301858"
---
# <a name="ios-and-ipados-device-settings-to-use-common-ios-features-in-intune"></a>Intune 'da ortak iOS özelliklerini kullanmak için iOS ve ıpados cihaz ayarları

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune, iOS kullanıcılarının cihazlarında farklı Apple özellikleri kullanmasına izin veren bazı yerleşik ayarlar içerir. Örneğin, Yöneticiler iOS kullanıcılarının AirPrint yazıcılarını nasıl kullandığını denetleyebilir, giriş ekranındaki yerleştirme ve sayfalara uygulama ve klasör ekleme, uygulama bildirimlerini gösterme, kilit ekranında varlık etiketi ayrıntılarını gösterme, çoklu oturum açma kimlik doğrulaması kullanma ve kullanıcıların kimliğini doğrulama işlemlerinin nasıl yapılacağını denetleyebilir Sertifikalar ile.

Bu özellikleri, mobil cihaz yönetimi (MDM) çözümünüzün bir parçası olarak iOS cihazlarını denetlemek için kullanın.

Bu makale, bu ayarları listeler ve her ayarın ne yaptığını açıklar. Bu özellikler hakkında daha fazla bilgi için [iOS veya macOS cihaz özelliği ayarları ekle](device-features-configure.md)' ye gidin.

## <a name="before-you-begin"></a>Başlamadan önce

[İOS cihaz yapılandırma profili oluşturun](device-features-configure.md).

> [!NOTE]
> Bu ayarlar, bazı ayarların tüm kayıt seçeneklerine uygulanmasıyla farklı kayıt türleri için geçerlidir. Farklı kayıt türleri hakkında daha fazla bilgi için bkz. [iOS kaydı](ios-enroll.md).

## <a name="airprint"></a>AirPrint

### <a name="settings-apply-to-all-enrollment-types"></a>Ayarlar için geçerlidir: Tüm kayıt türleri

- **IP adresi**: Yazıcının IPv4 veya IPv6 adresini girin. Yazıcıları tanımlamak için ana bilgisayar adları kullanırsanız, terminaldeki yazıcıya ping ekleyerek IP adresini alabilirsiniz. IP adresini ve yolu al (Bu makalede) daha fazla ayrıntı sağlar.
- **Yol**: Yol, genellikle `ipp/print` ağınızdaki yazıcılar içindir. IP adresini ve yolu al (Bu makalede) daha fazla ayrıntı sağlar.
- **Bağlantı noktası**: AirPrint hedefinin dinleme bağlantı noktasını girin. Bu özelliği boş bırakırsanız AirPrint varsayılan bağlantı noktasını kullanır. İOS 11,0 ve üzeri sürümlerde kullanılabilir.
- **TLS**: Aktarım Katmanı Güvenliği (TLS) ile AirPrint bağlantılarını güvenli hale getirmek için **Etkinleştir** ' i seçin. İOS 11,0 ve üzeri sürümlerde kullanılabilir.

AirPrint sunucuları eklemek için şunları yapabilirsiniz:

- **Ekle** , AirPrint sunucusunu listeye ekler. Birçok AirPrint sunucusu eklenebilir.
- Bu bilgilerle, virgülle ayrılmış bir dosyayı (. csv) **Içeri aktarın** . Ya da, eklediğiniz AirPrint sunucularının bir listesini oluşturmak için **dışa aktarın** .

### <a name="get-server-ip-address-resource-path-and-port"></a>Sunucu IP adresi, kaynak yolu ve bağlantı noktası al

AirPrinter sunucuları eklemek için, yazıcının IP adresi, kaynak yolu ve bağlantı noktası gerekir. Aşağıdaki adımlarda bu bilgilerin nasıl alınacağı gösterilmektedir.

1. AirPrint yazıcıları ile aynı yerel ağa (alt ağ) bağlı bir Mac üzerinde, açık **Terminal** ( **/Applications/Utilities**).
2. Terminalde yazın `ippfind`ve ENTER ' u seçin.

    Yazıcı bilgilerini aklınızda edin. Örneğin, şuna benzer `ipp://myprinter.local.:631/ipp/port1`bir şey döndürebilir. İlk bölüm, yazıcının adıdır. Son Bölüm (`ipp/port1`) kaynak yoludur.

3. Terminalde yazın `ping myprinter.local`ve ENTER ' u seçin.

   IP adresini aklınızda edin. Örneğin, şuna benzer `PING myprinter.local (10.50.25.21)`bir şey döndürebilir.

4. IP adresi ve kaynak yolu değerlerini kullanın. Bu örnekte, IP adresi `10.50.25.21`ve kaynak yolu olur. `/ipp/port1`

## <a name="home-screen-layout"></a>Giriş ekranı düzeni

Bu özellik şu platformlarda geçerlidir:

- iOS 9,3 veya üzeri

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: Otomatik cihaz kaydı (denetimli)

### <a name="dock"></a>Dock

İOS ekranının Dock 'a en fazla altı öğe veya klasör eklemek için **yerleştirme** ayarlarını kullanın. Birçok cihaz daha az öğeyi destekler. Örneğin, iPhone cihazları en fazla dört öğeyi destekler. Bu durumda, cihazda yalnızca eklediğiniz ilk dört öğe gösterilir.

Cihaz yuvası için en fazla **altı** öğe (birleştirilmiş uygulamalar ve klasörler) ekleyebilirsiniz.

- **Ekle**: Cihaza uygulama veya klasörler ekler.
- **Şunu yazın**: Bir **uygulama** veya **klasör**ekleyin:

  - **Uygulama**: Ekrandaki yerleştirmeyi uygulama eklemek için bu seçeneği belirleyin. Girmesini

    - **Uygulama adı**: Uygulama için bir ad girin. Bu ad Azure portal başvurunuz için kullanılır. İOS *cihazında gösterilmez.*
    - **Uygulama Paketi Kimliği**: Uygulamanın paket KIMLIĞINI girin. Bazı örnekler için bkz. [yerleşik iOS uygulamaları Için paket kimlikleri](bundle-ids-built-in-ios-apps.md) .

  - **Klasör**: Ekrandaki yerleştirmeyi bir klasör eklemek için bu seçeneği belirleyin.

    Bir klasördeki bir sayfaya eklediğiniz uygulamalar, soldan sağa ve listeyle aynı sırada düzenlenir. Bir sayfaya sığmayacak kadar fazla uygulama eklerseniz, uygulamalar başka bir sayfaya taşınır.

    - **Klasör adı**: Klasörün adını girin. Bu ad, cihazlarındaki kullanıcılara gösterilir.
    - **Sayfaların listesi**: Bir sayfa **ekleyin** ve aşağıdaki özellikleri girin:

      - **Sayfa adı**: Sayfa için bir ad girin. Bu ad Azure portal başvurunuz için kullanılır. İOS *cihazında gösterilmez.*
      - **Uygulama adı**: Uygulama için bir ad girin. Bu ad Azure portal başvurunuz için kullanılır. İOS *cihazında gösterilmez.*
      - **Uygulama Paketi Kimliği**: Uygulamanın paket KIMLIĞINI girin. Bazı örnekler için bkz. [yerleşik iOS uygulamaları Için paket kimlikleri](bundle-ids-built-in-ios-apps.md) .

      Cihaz yuvası için en fazla **20** sayfa ekleyebilirsiniz.

> [!NOTE]
> Yerleştirme ayarlarını kullanarak simgeler eklediğinizde, ana ekrandaki ve sayfalardaki simgeler kilitlenir ve taşınamaz. Bu, iOS ve Apple 'ın MDM ilkeleriyle tasarlayabilirsiniz.

#### <a name="example"></a>Örnek

Aşağıdaki örnekte, Dock ekranında yalnızca Safari, mail ve hisse senetleri uygulamaları gösterilmektedir. Posta uygulaması özelliklerini göstermek için seçilmiştir:

![Örnek iOS dock ayarları](./media/FfFiUcP.png)

İlkeyi bir iPhone 'a atadığınızda, yuva aşağıdaki resme benzer şekilde görünür:

![iPhone’da örnek iOS dock düzeni](./media/bAgCe8F.png)

### <a name="pages"></a>Sayfaları

Giriş ekranında görünmesini istediğiniz sayfaları ve her sayfada görünmesini istediğiniz uygulamaları ekleyin. Bir sayfaya eklediğiniz uygulamalar, listeyle aynı sırada, soldan sağa düzenlenir. Bir sayfaya sığmayacak kadar fazla uygulama eklerseniz, uygulamalar başka bir sayfaya taşınır.

> [!TIP]
> Herhangi bir giriş ekranında ve sayfa listelerindeki öğeleri yeniden sıralamak için, onları sürükleyip bırakabilirsiniz.

Bir cihaza en fazla **40** sayfa ekleyebilirsiniz.

- **Sayfaların listesi**: Bir sayfa **ekleyin** ve aşağıdaki özellikleri girin:

  - **Sayfa adı**: Sayfa için bir ad girin. Bu ad, Azure portal başvurunuz için kullanılır ve iOS *cihazında gösterilmez.*

  Bir cihaza en fazla **60** öğe (birleştirilmiş uygulamalar ve klasör) ekleyebilirsiniz.

  - **Ekle**: Cihazdaki bir sayfaya uygulamalar veya klasörler ekler.

    - **Şunu yazın**: Bir **uygulama** veya **klasör**ekleyin:

      - **Uygulama**: Ekrandaki bir sayfaya uygulama eklemek için bu seçeneği belirleyin. Şunları da girin:

        - **Uygulama adı**: Uygulama için bir ad girin. Bu ad Azure portal başvurunuz için kullanılır. İOS *cihazında gösterilmez.*
        - **Uygulama Paketi Kimliği**: Uygulamanın paket KIMLIĞINI girin. Bazı örnekler için bkz. [yerleşik iOS uygulamaları Için paket kimlikleri](bundle-ids-built-in-ios-apps.md) .

      - **Klasör**: Ekrandaki yerleştirmeyi bir klasör eklemek için bu seçeneği belirleyin.

        Bir klasördeki bir sayfaya eklediğiniz uygulamalar, soldan sağa ve listeyle aynı sırada düzenlenir. Bir sayfaya sığmayacak kadar fazla uygulama eklerseniz, uygulamalar başka bir sayfaya taşınır.

        - **Klasör adı**: Klasör için bir ad girin. Bu ad, cihazdaki kullanıcılara gösterilir.
        - **Ekle**: Klasöre sayfa ekler. Aşağıdaki özellikleri de girin:

          - **Sayfa adı**: Sayfa için bir ad girin. Bu ad Azure portal başvurunuz için kullanılır. İOS *cihazında gösterilmez.*
          - **Uygulama adı**: Uygulama için bir ad girin. Bu ad Azure portal başvurunuz için kullanılır. İOS *cihazında gösterilmez.*
          - **Uygulama Paketi Kimliği**: Uygulamanın paket KIMLIĞINI girin. Bazı örnekler için bkz. [yerleşik iOS uygulamaları Için paket kimlikleri](bundle-ids-built-in-ios-apps.md) .

#### <a name="example"></a>Örnek

Aşağıdaki örnekte, **contoso** adlı yeni bir sayfa eklenmiştir. Sayfa, arkadaşları ve ayarları bul uygulamalarını gösterir. Ayarlar uygulaması özelliklerini göstermek için seçilmiştir:

![iOS Giriş ekranı ayarları örneği](./media/Jc2OxyX.png)

İlkeyi bir iPhone 'a atadığınızda, sayfa aşağıdaki resme benzer şekilde görünür:

![Değiştirilmiş giriş ekranı ile iOS cihazı](./media/Bd37PHa.png)

## <a name="app-notifications"></a>Uygulama bildirimleri

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: Otomatik cihaz kaydı (denetimli)

- **Ekle**: Uygulamalar için bildirim ekleyin:

    ![Intune 'da iOS profiline uygulama bildirimi ekleme](./media/ios-macos-app-notifications.png)

  - **Uygulama PAKETI kimliği**: Eklemek istediğiniz uygulamanın **uygulama paket kimliğini** girin. Bazı örnekler için bkz. [yerleşik iOS uygulamaları Için paket kimlikleri](bundle-ids-built-in-ios-apps.md) .
  - **Uygulama adı**: Eklemek istediğiniz uygulamanın adını girin. Bu ad Azure portal başvurunuz için kullanılır. Cihazda *gösterilmez.*
  - **Yayımcı**: Eklemekte olduğunuz uygulamanın yayımcısını girin. Bu ad Azure portal başvurunuz için kullanılır. Cihazda *gösterilmez.*
  - **Bildirimler**: Uygulamanın cihaza bildirim göndermesini **etkinleştirin** veya **devre dışı bırakın** .
    - **Bildirim merkezinde göster**: **Etkinleştir** ayarı, uygulamanın cihaz bildirim merkezinde bildirimleri göstermesini sağlar. **Devre dışı bırak ayarı** , uygulamanın bildirim merkezinde bildirimleri göstermesini önler.
    - **Kilit ekranında göster**: Cihaz kilidi ekranında uygulamadan bildirimleri görmek için **Etkinleştir** ' i seçin. **Devre dışı bırak ayarı** , uygulamanın kilit ekranında bildirimleri göstermesini önler.
    - **Uyarı türü**: Cihazın kilidi açıldığında, bildirimin nasıl gösterileceğini seçin. Seçenekleriniz şunlardır:
      - **Hiçbiri**: Hiçbir bildirim gösterilmez.
      - **Başlık**: Bir başlık, bildirimle kısaca gösterilir.
      - **Kalıcı**: Bildirim gösterilir ve cihazı kullanmaya devam etmeden önce kullanıcının el ile kapatması gerekir.
    - **Uygulama simgesinde rozet**: Uygulama simgesine rozet eklemek için **Etkinleştir** ' i seçin. Rozet, uygulamanın bir bildirim gönderdiği anlamına gelir.
    - **Sesler**: Bildirim teslim edildiğinde bir ses çalmak için **Etkinleştir** ' i seçin.

## <a name="lock-screen-message"></a>Kilit ekranı iletisi

Bu özellik şu platformlarda geçerlidir:

- iOS 9.3 ve üzeri

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: Otomatik cihaz kaydı (denetimli)

- **Varlık etiketi bilgileri**: Cihazın varlık etiketiyle ilgili bilgileri girin. Örneğin `Owned by Contoso Corp` veya `Serial Number: {{serialnumber}}` girin.

  Girdiğiniz metin, cihazdaki oturum açma penceresinde ve kilit ekranında görüntülenir.

- **Kilit ekranı dipnotu**: Cihaz kaybolur veya çalınırsa, cihazın döndürülmesini sağlamaya yardımcı olabilecek bir değer girin. İstediğiniz herhangi bir metin girebilirsiniz. Örneğin `If found, call Contoso at ...` gibi bir URI girebilirsiniz.

  Cihaz belirteçleri, bu alanlara cihaza özgü bilgiler eklemek için de kullanılabilir. Örneğin, seri numarasını göstermek için girin `Serial Number: {{serialnumber}}`. Kilit ekranında metin şuna benzer şekilde `Serial Number 123456789ABC`görünür. Değişken girerken, küme ayraçları `{{ }}`kullandığınızdan emin olun. [Uygulama yapılandırma belirteçleri](app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) , kullanılabilecek değişkenlerin bir listesini içerir. Ayrıca, herhangi bir `deviceName` cihaza özgü değeri de kullanabilirsiniz.

  > [!NOTE]
  > Değişkenler kullanıcı arabiriminde doğrulanmaz ve büyük/küçük harfe duyarlıdır. Sonuç olarak, yanlış girişle kaydedilmiş profiller görebilirsiniz. Örneğin, `{{DeviceID}}` `{{deviceid}}`yerine girdiğinizde, cihazın benzersiz kimliği yerine değişmez dize gösterilir. Doğru bilgileri girdiğinizden emin olun.

## <a name="single-sign-on"></a>Çoklu oturum açma

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: Cihaz kaydı, otomatik cihaz kaydı (denetimli)

- **AAD 'Den Kullanıcı adı özniteliği**: Intune, Azure AD 'de her bir kullanıcı için bu özniteliğe bakar. Ardından Intune, cihaza yüklenen XML oluşturmadan önce ilgili alanı (UPN gibi) doldurur. Seçenekleriniz şunlardır:

  - **Kullanıcı asıl adı**: UPN aşağıdaki şekilde ayrıştırılır:

    ![Kullanıcı adı özniteliği](media/User-name-attribute.png)

    Ayrıca, **Bölge** metin kutusuna girdiğiniz metinle bölge değerinin üzerine yazabilirsiniz.

    Örneğin contoso, Avrupa, Asya ve Kuzey Amerika dahil olmak üzere birkaç bölgeye sahiptir. Contoso, Asya kullanıcılarının SSO kullanmasını istiyor ve uygulama, UPN `username@asia.contoso.com` 'nin biçiminde olmasını istiyor. **Kullanıcı asıl adı**' nı seçtiğinizde, her bir kullanıcının BÖLGESI Azure AD `contoso.com`'den alınır. Böylece, Asya 'daki kullanıcılar için **Kullanıcı asıl adı**' nı seçin ve `asia.contoso.com`girin. Son kullanıcının UPN 'si `username@asia.contoso.com` `username@contoso.com`yerine olur.

  - **Intune CIHAZ kimliği**: Intune, Intune cihaz KIMLIĞINI otomatik olarak seçer.

    Varsayılan olarak, uygulamaların yalnızca cihaz kimliğini kullanması gerekir. Ancak, uygulamanız bölge ve cihaz KIMLIĞINI kullanıyorsa, bölgeyi bölge metin kutusuna yazabilirsiniz.

    > [!NOTE]
    > Varsayılan olarak, cihaz kimliğini kullanıyorsanız bölgeyi boş bırakın.

  - **Azure AD cihaz KIMLIĞI**

- **Bölge**: URL 'nin etki alanı kısmını girin. Örneğin, şunu girin: `contoso.com`.
- **Çoklu oturum açma kullanacak URL ön ekleri**: Kuruluşunuzda Kullanıcı çoklu oturum açma kimlik doğrulaması gerektiren tüm URL 'Leri **ekleyin** .

  Örneğin, kullanıcı bu sitelerden birine bağlandığında iOS cihaz çoklu oturum açma kimlik bilgilerini kullanır. Kullanıcının başka kimlik bilgisi girmesi gerekmez. Multi-Factor Authentication etkinleştirilirse, kullanıcıların ikinci kimlik doğrulamasını girmesi gerekir.

  > [!NOTE]
  > Bu URL'ler düzgün biçimlendirilmiş FQDN'ler olmalıdır. Apple bunların `http://<yourURL.domain>` biçiminde olmasını gerektirir.

  URL eşleştirme desenleri `http://` veya `https://` ile başlamalıdır. Basit bir dize eşleşmesi çalıştırılır, bu nedenle `http://www.contoso.com/` URL öneki eşleşmez. `http://www.contoso.com:80/` İOS 10,0 veya üzeri ile eşleşen tüm değerleri girmek \* için tek bir joker karakter kullanılabilir. Örneğin, `http://*.contoso.com/` `http://store.contoso.com/` ve ileeşleşir.`http://www.contoso.com`

  `http://.com` Ve`https://.com` desenleri sırasıyla tüm http ve https URL 'leri ile eşleşir.

- **Çoklu oturum açma kullanacak uygulamalar**: Son Kullanıcıların cihazlarına çoklu oturum açma kullanılabilecek uygulamalar **ekleyin** .

  Dizi `AppIdentifierMatches` , uygulama paketi kimlikleriyle eşleşen dizeler içermelidir. Bu dizeler gibi tam eşleşmeler `com.contoso.myapp`olabilir veya \* joker karakterini kullanarak paket kimliğinde bir ön ek eşleşmesi girebilirsiniz. Joker karakter, bir nokta karakterinden (.) sonra görünmelidir ve dizenin `com.contoso.*`sonunda, gibi yalnızca bir kez görünebilir. Joker karakter eklendiğinde, paket kimlikleri bu ön ekle başlayan tüm uygulamaların hesaba erişimine izin verilir.

  **Uygulama Adı**’nı kullanarak paket kimliğini ayırt etmenize yardımcı olacak bir kolay ad ekleyin.

- **Kimlik bilgileri yenileme sertifikası**: Kimlik doğrulaması için Sertifikalar (parolalar değil) kullanılıyorsa, mevcut SCEP veya PFX sertifikasını kimlik doğrulama sertifikası olarak seçin. Genellikle, bu sertifika, kullanıcıya VPN, Wi-Fi veya e-posta gibi diğer profiller için dağıtılan sertifikadır.

## <a name="web-content-filter"></a>Web içeriği filtresi

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: Otomatik cihaz kaydı (denetimli)

- **Filtre türü**: Belirli Web sitelerine izin vermeyi seçin. Seçenekleriniz şunlardır:

  - **URL 'Leri Yapılandır**: Küfür ve açık cinsel dil dahil olmak üzere yetişkinlere yönelik terimleri aramak için Apple 'ın yerleşik Web filtresini kullanın. Bu özellik her bir Web sayfasını yüklendiği şekilde değerlendirir ve uygun olmayan içeriği tanımlar ve engeller. Filtre tarafından denetlenmesini istemediğiniz URL 'Ler de ekleyebilirsiniz. Ya da Apple 'ın filtre ayarlarından bağımsız olarak belirli URL 'Leri engelleyin.

    - **Izin verilen URL 'ler**: İzin vermek istediğiniz URL 'Leri **ekleyin** . Bu URL 'Ler Apple 'ın Web filtresini atlar.

        > [!NOTE]
        > Girdiğiniz URL 'ler, Apple Web filtresi tarafından evauluated istemediğiniz URL 'lerdir. Bu URL 'Ler, izin verilen Web sitelerinin bir listesi değildir. İzin verilen Web sitelerinin bir listesini oluşturmak için **filtre türünü** **yalnızca belirli Web siteleri**olarak ayarlayın.

    - **Engellenen URL 'ler**: Apple Web Filter ayarlarından bağımsız olarak, durdurmak istediğiniz URL 'Leri açma işleminden sonra **ekleyin** .

  - **Yalnızca belirli Web siteleri** (yalnızca Safari Web tarayıcısı için): Bu URL 'Ler Safari tarayıcısının yer işaretlerine eklenir. Kullanıcının **yalnızca** bu siteleri ziyaret etme izni vardır; başka hiçbir site açılamaz. Bu seçeneği yalnızca kullanıcıların erişebileceği URL'lerin tam listesini biliyorsanız kullanın.

    - **URL**: İzin vermek istediğiniz Web sitesinin URL 'sini girin. Örneğin, şunu girin: `https://www.contoso.com`.
    - **Yer Işareti yolu**: Yer işaretinin depolandığı yolu girin. Örneğin, şunu girin: `/Contoso/Business Apps`. Bir yol eklemezseniz yer işareti cihazdaki varsayılan yer işareti klasörüne eklenir.
    - **Başlık**: Yer işareti için açıklayıcı bir başlık girin.

    Herhangi bir URL girmezseniz, son kullanıcılar `microsoft.com`, `microsoft.net`ve `apple.com`dışında herhangi bir Web sitesine erişemez. Bu URL 'Lere Intune tarafından otomatik olarak izin verilir.

## <a name="single-sign-on-app-extension"></a>Çoklu oturum açma uygulama uzantısı

Bu özellik şu platformlarda geçerlidir:

- iOS 13,0 ve üzeri
- ıpados 13,0 ve üzeri

### <a name="settings-apply-to-all-enrollment-types"></a>Ayarlar için geçerlidir: Tüm kayıt türleri

- **SSO uygulama uzantısı türü**: Kimlik bilgisi SSO uygulaması uzantısının türünü seçin. Seçenekleriniz şunlardır:

  - **Yapılandırılmadı**: Uygulama uzantıları kullanılmıyor. Bir uygulama uzantısını devre dışı bırakmak için, SSO uygulama uzantısı türünü **Kerberos** veya **kimlik bilgilerinden** **yapılandırılmamış**olarak değiştirebilirsiniz.
  - **Kimlik bilgisi**: SSO gerçekleştirmek için genel, özelleştirilebilir bir kimlik bilgisi uygulama uzantısı kullanın. Kuruluşunuzun SSO uygulaması uzantısının uzantı KIMLIĞINI öğrendiğinizden emin olun.
  - **Kerberos**: İOS 13,0 (ve üzeri) ve ıpados 13,0 (ve üzeri) ' de bulunan Apple 'ın yerleşik Kerberos uzantısını kullanın. Bu seçenek, **kimlik bilgisi** uygulama uzantısının Kerberos 'a özgü bir sürümüdür.

  > [!TIP]
  > **Kimlik bilgisi** türü ile, uzantısından geçirilecek kendi yapılandırma değerlerinizi eklersiniz. Bunun yerine, **Kerberos** türünde Apple tarafından sunulan yerleşik yapılandırma ayarlarını kullanmayı göz önünde bulundurun.

- **UZANTı kimliği** (Yalnızca kimlik bilgileri): SSO uygulaması uzantınızı `com.apple.extensiblesso`tanımlayan paket tanımlayıcısını (gibi) girin.
- **Takım Kimliği** (Yalnızca kimlik bilgileri): SSO uygulaması uzantınızın ekip tanımlayıcısını girin. Takım tanımlayıcısı, Apple tarafından oluşturulan ve `ABCDE12345`gibi 10 karakterlik alfasayısal bir dizedir (sayılar ve harfler). Takım KIMLIĞI gerekli değildir.

  [Takım kimliğinizi bulun](https://help.apple.com/developer-account/#/dev55c3c710c) (Apple 'ın Web sitesini açar) daha fazla bilgi içerir.

- **Bölge**: Kerberos bölgesi adını girin. Bölge adı, `CONTOSO.COM`gibi büyük harfli olmalıdır. Genellikle, bölge adınız DNS etki alanı adınızla aynıdır, ancak tümü büyük harfle aynıdır.

- **Etki alanları**: SSO aracılığıyla kimlik doğrulayabilecek sitelerin etki alanını veya ana bilgisayar adlarını girin. Örneğin, Web siteniz ise `mysite.contoso.com` `mysite` , ana bilgisayar adı ve `contoso.com` etki alanı adıdır. Kullanıcılar bu sitelerden birine bağlandıklarında, uygulama uzantısı kimlik doğrulama sınamasını işler. Bu kimlik doğrulaması, kullanıcıların oturum açmak için yüz KIMLIĞI, Touch ID veya Apple pincode/geçiş kodu kullanmasına izin verir.

  - Çoklu oturum açma uygulama uzantılarınızın Intune profillerindeki tüm etki alanları benzersiz olmalıdır. Farklı türlerde SSO uygulama uzantıları kullanıyor olsanız bile, bir etki alanını hiçbir oturum açma uygulama uzantısı profilinde tekrarlayamıyorum.
  - Bu etki alanları büyük/küçük harfe duyarlı değildir.

- **Ek yapılandırma** (Yalnızca kimlik bilgileri): SSO uygulama uzantısına geçirilecek uzantıya özgü ek veriler girin:
  - **Yapılandırma anahtarı**: Eklemek istediğiniz öğenin adını (örneğin `user name`,) girin.
  - **Değer türü**: Veri türünü girin. Seçenekleriniz şunlardır:

    - Dize
    - Boolean **Yapılandırma değeri**' nde, `True` veya `False`girin.
    - gir **Yapılandırma değeri**alanına bir sayı girin.
    
  - **Yapılandırma değeri**: Verileri girin.

  - **Ekle**: Yapılandırma anahtarlarınızı eklemek için seçin.

- **Anahtarlık kullanımı** (Yalnızca Kerberos): Parolaların anahtarlıkta kaydedilmesini ve saklanmasını engellemek için **Engelle** ' yi seçin. **Yapılandırılmadı** (varsayılan), parolaların anahtarlıkta kaydedilmesine ve depolanmasına izin verir.
- **Yüz kimliği, Touch ID veya geçiş kodu** (Yalnızca Kerberos): Kullanıcıların eklediğiniz etki alanlarında oturum açması için yüz KIMLIKLERINI, Touch ID 'sini veya Apple geçiş kodunu girmesini **zorunlu kılın** . **Yapılandırılmadı** (varsayılan), kullanıcıların oturum açmak için Biyometri veya geçiş kodu kullanmalarını gerektirmez.
- **Varsayılan bölge** (Yalnızca Kerberos): Varsayılan bölge olarak girdiğiniz **bölge** değerini ayarlamak için **Etkinleştir** ' i seçin. **Yapılandırılmadı** (varsayılan) varsayılan bir bölge yapmaz.

  > [!TIP]
  > - Kuruluşunuzda birden çok Kerberos SSO uygulama uzantısını yapılandırıyorsanız, bu ayarı **etkinleştirin** .
  > - Birden çok bölge kullanıyorsanız bu ayarı **etkinleştirin** . Girdiğiniz **bölge** değerini varsayılan bölge olarak ayarlar.
  > - Yalnızca bir bölge varsa, **Yapılandırılmadı** (varsayılan) olarak bırakın.

- **Asıl ad** (Yalnızca Kerberos): Kerberos sorumlusunun Kullanıcı adını girin. Bölge adını eklemeniz gerekmez. Örneğin, içinde `user@contoso.com` `user` asıl addır ve `contoso.com` bölge adıdır.
- **Active Directory site kodu** (Yalnızca Kerberos): Kerberos uzantısının kullanması gereken Active Directory sitenin adını girin. Kerberos uzantısı Active Directory site kodunu otomatik olarak bulagerekebilmeniz için bu değeri değiştirmeniz gerekebilir.
- **Önbellek adı** (Yalnızca Kerberos): Kerberos önbelleğinin genel güvenlik hizmetleri (GSS) adını girin. Büyük olasılıkla bu değeri ayarlamanız gerekmez.
- **Uygulama paketi kimlikleri** (Yalnızca Kerberos): Cihazlarınızda çoklu oturum açma kullanması gereken uygulama paketi tanımlayıcılarını **ekleyin** . Bu uygulamalara, Kerberos Anahtar verme bileti, kimlik doğrulama bileti ve kullanıcılara erişim yetkisi oldukları hizmetler için kimlik doğrulaması erişimi verilir.
- **Etki alanı bölge eşleme** (Yalnızca Kerberos): Bölge ile eşleşmesi gereken etki alanı DNS soneklerini **ekleyin** . Ana bilgisayarların DNS adları bölge adıyla eşleşmezse bu ayarı kullanın. Büyük olasılıkla bu özel etki alanı/bölge eşlemesini oluşturmanız gerekmez.

## <a name="wallpaper"></a>Duvar

Var olan bir görüntüye sahip cihazlara sahip olmayan bir profil atandığında beklenmeyen davranışlarla karşılaşabilirsiniz. Örneğin, görüntü olmadan bir profil oluşturursunuz. Bu profil, zaten bir görüntüsü olan cihazlara atanır. Bu senaryoda, görüntü cihaz varsayılana değişebilir veya orijinal görüntü cihazda kalabilir. Bu davranış, Apple 'ın MDM platformu tarafından denetlenir ve sınırlandırılmıştır.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: Otomatik cihaz kaydı (denetimli)

- **Duvar kağıdı görünen konumu**: Görüntüyü göstermek için cihazda bir konum seçin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı**: Cihaza özel bir görüntü eklenmez. Cihaz, işletim sistemi varsayılanını kullanır.
  - **Kilit ekranı**: Görüntüyü kilit ekranına ekler.
  - **Giriş ekranı**: Görüntüyü giriş ekranına ekler.
  - **Kilit ekranı ve giriş ekranı**: Kilit ekranında ve ana ekranda aynı görüntüyü kullanır.
- **Duvar kağıdı resmi**: Kullanmak istediğiniz var olan bir. png,. jpg veya. JPEG görüntüsünü karşıya yükleyin. Dosya boyutunun 750 KB 'tan az olduğundan emin olun. Ayrıca, eklediğiniz bir görüntüyü de **kaldırabilirsiniz** .

> [!TIP]
> Kilit ekranında ve ana ekranda farklı görüntüleri göstermek için, kilit ekranı görüntüsüyle bir profil oluşturun. Giriş ekranı görüntüsüyle başka bir profil oluşturun. Her iki profili de iOS Kullanıcı veya cihaz gruplarına atayın.

## <a name="next-steps"></a>Sonraki adımlar

[Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).

[MacOS](macos-device-features-settings.md) cihazları için cihaz özelliği profilleri de oluşturabilirsiniz.
