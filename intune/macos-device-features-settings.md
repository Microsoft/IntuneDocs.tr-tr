---
title: Microsoft Intune-Azure 'da macOS cihaz özelliği ayarları | Microsoft Docs
description: MacOS cihazlarını AirPrint için yapılandırma ayarlarına bakın ve Microsoft Intune içindeki güç düğmelerini göstermek veya gizlemek için oturum açma penceresini özelleştirin. Ağınızdaki bir AirPrint sunucusunun IP adresini, yolunu ve bağlantı noktası ayarlarını almak için adımlara bakın. MacOS cihaz özelliklerini yapılandırmak için bu ayarları bir cihaz yapılandırma profilinde kullanın.
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
ms.openlocfilehash: 7a6c145d5c18a63be512b7fbaca7fae3c660872f
ms.sourcegitcommit: c19584b36448bbd4c8638d7cab552fe9b3eb3408
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/20/2019
ms.locfileid: "71301777"
---
# <a name="macos-device-feature-settings-in-intune"></a>Intune 'da macOS cihaz özelliği ayarları

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune, macOS cihazlarınızdaki özellikleri özelleştirmek için bazı yerleşik ayarlar içerir. Örneğin, Yöneticiler AirPrint yazıcıları ekleyebilir, kullanıcıların oturum açma biçimini seçebilir, güç denetimlerini yapılandırabilir, çoklu oturum açma kimlik doğrulaması kullanabilir ve daha fazlasını yapabilir.

Bu özellikleri, macOS cihazlarını mobil cihaz yönetimi (MDM) çözümünüzün bir parçası olarak denetlemek için kullanın.

Bu makale, bu ayarları listeler ve her ayarın ne yaptığını açıklar. Ayrıca, Terminal uygulaması 'nı (öykünücü) kullanarak AirPrint yazıcılarının IP adresini, yolunu ve bağlantı noktasını almak için gereken adımları listeler. Cihaz özellikleri hakkında daha fazla bilgi için bkz. [iOS veya macOS cihaz özelliği ayarları ekleme](device-features-configure.md).

## <a name="before-you-begin"></a>Başlamadan önce

[MacOS cihaz yapılandırma profili oluşturun](device-features-configure.md).

> [!NOTE]
> Bu ayarlar, bazı ayarların tüm kayıt seçeneklerine uygulanmasıyla farklı kayıt türleri için geçerlidir. Farklı kayıt türleri hakkında daha fazla bilgi için bkz. [MacOS kaydı](macos-enroll.md).

## <a name="airprint"></a>AirPrint

### <a name="settings-apply-to-device-enrollment"></a>Ayarlar için geçerlidir: Cihaz kaydı

- **IP adresi**: Yazıcının IPv4 veya IPv6 adresini girin. Yazıcıları tanımlamak için konak adlarını kullanıyorsanız, Terminal uygulamasındaki yazıcıya ping ekleyerek IP adresini alabilirsiniz. [IP adresini ve yolu al](#get-the-ip-address-and-path) (Bu makalede) daha fazla ayrıntı sağlar.
- **Yol**: Yazıcının yolunu girin. Yol, genellikle `ipp/print` ağınızdaki yazıcılar içindir. [IP adresini ve yolu al](#get-the-ip-address-and-path) (Bu makalede) daha fazla ayrıntı sağlar.
- **Bağlantı noktası** (iOS 11,0 ve üzeri): AirPrint hedefinin dinleme bağlantı noktasını girin. Bu özelliği boş bırakırsanız AirPrint varsayılan bağlantı noktasını kullanır.
- **TLS** (iOS 11,0 ve üzeri): Aktarım Katmanı Güvenliği (TLS) ile AirPrint bağlantılarını güvenli hale getirmek için **Etkinleştir** ' i seçin.

- **Ekle** AirPrint sunucusu. Birçok AirPrint sunucusu ekleyebilirsiniz.

Ayrıca, AirPrint yazıcılarının listesini içeren bir virgülle ayrılmış dosyayı (. csv) **Içeri aktarabilirsiniz** . Ayrıca, Intune 'A AirPrint yazıcıları ekledikten sonra bu listeyi **dışarı aktarabilirsiniz** .

### <a name="get-the-ip-address-and-path"></a>IP adresini ve yolu al

AirPrinter sunucuları eklemek için, yazıcının IP adresi, kaynak yolu ve bağlantı noktası gerekir. Aşağıdaki adımlarda bu bilgilerin nasıl alınacağı gösterilmektedir.

1. AirPrint yazıcıları ile aynı yerel ağa (alt ağ) bağlı bir Mac üzerinde, açık **Terminal** ( **/Applications/Utilities**).
2. Terminal uygulamasında yazın `ippfind`ve ENTER ' u seçin.

    Yazıcı bilgilerini aklınızda edin. Örneğin, şuna benzer `ipp://myprinter.local.:631/ipp/port1`bir şey döndürebilir. İlk bölüm, yazıcının adıdır. Son Bölüm (`ipp/port1`) kaynak yoludur.

3. Terminalde yazın `ping myprinter.local`ve ENTER ' u seçin.

   IP adresini aklınızda edin. Örneğin, şuna benzer `PING myprinter.local (10.50.25.21)`bir şey döndürebilir.

4. IP adresi ve kaynak yolu değerlerini kullanın. Bu örnekte, IP adresi `10.50.25.21`ve kaynak yolu olur. `/ipp/port1`

## <a name="login-items"></a>Oturum açma öğeleri

### <a name="settings-apply-to-all-enrollment-types"></a>Ayarlar için geçerlidir: Tüm kayıt türleri

- **Dosyalar, klasörler ve özel uygulamalar**: Kullanıcı cihazda oturum açtığında açmak istediğiniz bir dosya, klasör, özel uygulama veya sistem uygulamasının yolunu **ekleyin** . Kuruluşunuz için oluşturulmuş veya özelleştirilmiş olan sistem uygulamaları veya uygulamalar genellikle `Applications` klasöründe, `/Applications/AppName.app`şuna benzer bir yol ile yapılır. 

  Birçok dosya, klasör ve uygulama ekleyebilirsiniz. Örneğin şunu girin:  
  
  - `/Applications/Calculator.app`
  - `/Applications`
  - `/Applications/Microsoft Office/root/Office16/winword.exe`
  - `/Users/UserName/music/itunes.app`
  
  Herhangi bir uygulama, klasör veya dosya eklerken doğru yolu girdiğinizden emin olun. Tüm öğeler `Applications` klasörde değil. Bir Kullanıcı bir öğeyi bir konumdan diğerine taşıdıysanız yol değişir. Bu taşınan öğe, Kullanıcı oturum açtığında açılmaz.

## <a name="login-window"></a>Oturum açma penceresi

### <a name="settings-apply-to-device-enrollment"></a>Ayarlar için geçerlidir: Cihaz kaydı

#### <a name="window-layout"></a>Pencere düzeni

- **Menü çubuğunda ek bilgileri göster**: Menü çubuğundaki saat alanı seçildiğinde, **Izin ver** ana bilgisayar adını ve MacOS sürümünü gösterir. **Yapılandırılmadı** (varsayılan), bu bilgileri menü çubuğunda göstermez.
- **Başlık**: Cihazda oturum açma ekranında gösterilen bir ileti girin. Örneğin, kuruluş bilgilerinizi, bir hoş geldiniz iletisini, kayıp ve bulunan bilgileri girin ve bu şekilde devam edin.
- **Oturum açma biçimini seçin**: Kullanıcıların cihazda nasıl oturum açmasını seçin. Seçenekleriniz şunlardır:
  - **Kullanıcı adı ve parola iste** (varsayılan): Kullanıcıların bir Kullanıcı adı ve parola girmesini gerektirir.
  - **Tüm kullanıcıları Listele, parola iste**: Kullanıcıların Kullanıcı listesinden kullanıcı adını seçmesini ve sonra parolasını girmesini gerektirir. Ayrıca şunları yapılandırın:

    - **Yerel kullanıcılar**: **Gizle** , yerel kullanıcı hesaplarını, standart ve yönetici hesaplarını içerebilecek Kullanıcı listesinde göstermez. Yalnızca ağ ve sistem kullanıcı hesapları gösterilir. **Yapılandırılmadı** (varsayılan) Kullanıcı listesindeki yerel kullanıcı hesaplarını gösterir.
    - **Mobil hesaplar**: **Gizle** , Kullanıcı listesinde mobil hesapları göstermez. **Yapılandırılmadı** (varsayılan) Kullanıcı listesindeki mobil hesapları gösterir. Bazı mobil hesaplar, ağ kullanıcıları olarak gösterilebilir.
    - **Ağ kullanıcıları**: Kullanıcı listesindeki ağ kullanıcılarını listelemek için **göster** ' i seçin. **Yapılandırılmadı** (varsayılan) Kullanıcı listesinde ağ kullanıcı hesaplarını göstermez.
    - **Yönetici kullanıcılar**: **Gizle** , Kullanıcı listesinde Yönetici Kullanıcı hesaplarını göstermez. **Yapılandırılmadı** (varsayılan) Kullanıcı listesindeki yönetici kullanıcı hesaplarını gösterir.
    - **Diğer kullanıcılar**: Kullanıcı listesindeki **diğer...** kullanıcıları listelemek için **göster** ' i seçin. **Yapılandırılmadı** (varsayılan) Kullanıcı listesindeki diğer Kullanıcı hesaplarını göstermez.

#### <a name="login-screen-power-settings"></a>Oturum açma ekranı güç ayarları

- **Kapat düğmesi**: **Gizle** , oturum açma ekranında Kapat düğmesini göstermez. **Yapılandırılmadı** (varsayılan) Kapalı düğmesini gösterir.
- **Yeniden Başlat düğmesi**: **Gizle** , oturum açma ekranında yeniden Başlat düğmesini göstermez. **Yapılandırılmadı** (varsayılan) yeniden Başlat düğmesini gösterir.
- **Uyku düğmesi**: **Gizle** , oturum açma ekranında uyku düğmesini göstermez. **Yapılandırılmadı** (varsayılan) uyku düğmesini gösterir.

#### <a name="other"></a>Diğer

- **Kullanıcı oturumunu konsolundan devre dışı bırak**: **Disable** , oturum açmak Için kullanılan MacOS komut satırını gizler. Tipik kullanıcılar için bu ayarı **devre dışı bırakın** . **Yapılandırılmadı** (varsayılan), gelişmiş kullanıcıların macOS komut satırını kullanarak oturum açmasına olanak sağlar. Konsol modunu girmek için, kullanıcılar Kullanıcı `>console` adı alanına girer ve konsol penceresinde kimlik doğrulaması yapılmalıdır.

#### <a name="apple-menu"></a>Apple menüsü

Kullanıcılar cihazlarda oturum açtıktan sonra, aşağıdaki ayarlar neler yapabileceğini etkiler.

- **Kapatmayı devre dışı bırak**: **Devre dışı bırak** seçeneği, kullanıcıların oturum açtıktan sonra **Kullanıcı oturumunu seçmesini** önler. **Yapılandırılmadı** (varsayılan) kullanıcıların cihazdaki **kapalı** menü öğesini seçmesine izin verir.
- **Yeniden başlatmayı devre dışı bırak**: **Disable** seçeneği, kullanıcıların oturum açtıktan sonra **yeniden başlatma** seçeneğini seçmesini önler. **Yapılandırılmadı** (varsayılan) kullanıcıların cihazdaki **Yeniden Başlat** menü öğesini seçmesine olanak sağlar.
- Kapatmayı **devre dışı bırak**: **Devre dışı bırak** seçeneği, Kullanıcı oturum açtıktan sonra kullanıcıların **kapatma** seçeneğini seçmesini önler. **Yapılandırılmadı** (varsayılan) kullanıcıların cihazdaki **kapatma** menü öğesini seçmesine olanak sağlar.
- **Oturumu kapatma devre dışı** (macOS 10,13 ve üzeri): **Devre dışı bırak** seçeneği, Kullanıcı oturum açtıktan sonra kullanıcıların **Oturumu Kapat** seçeneğini seçmesini önler. **Yapılandırılmadı** (varsayılan) kullanıcıların cihazdaki **oturum kapatma** menü öğesini seçmesine olanak sağlar.
- **Kilit ekranını devre dışı bırak** (macOS 10,13 ve üzeri): **Devre dışı bırak** seçeneği, Kullanıcı oturum açtıktan sonra kullanıcıların **kilit ekranı** seçmesini önler. **Yapılandırılmadı** (varsayılan) kullanıcıların cihazdaki **kilit ekranı** menü öğesini seçmesine izin verir.

## <a name="single-sign-on-app-extension"></a>Çoklu oturum açma uygulama uzantısı

Bu özellik şu platformlarda geçerlidir:

- macOS 10,15 ve üzeri

### <a name="settings-apply-to-all-enrollment-types"></a>Ayarlar için geçerlidir: Tüm kayıt türleri 

- **SSO uygulama uzantısı türü**: Kimlik bilgisi SSO uygulaması uzantısının türünü seçin. Seçenekleriniz şunlardır:

  - **Yapılandırılmadı**: Uygulama uzantıları kullanılmıyor. SSO uygulama uzantısını devre dışı bırakmak için, SSO uygulama uzantısı türünü **Kerberos** veya **kimlik bilgilerinden** **Yapılandırılmadı**olarak değiştirin.
  - **Kimlik bilgisi**: SSO kullanmak için genel, özelleştirilebilir bir kimlik bilgisi uygulama uzantısı kullanın. Kuruluşunuzun SSO uygulaması uzantısının uzantı KIMLIĞINI ve takım KIMLIĞINI öğrendiğinizden emin olun.  
  - **Kerberos**: MacOS Catalina 10,15 ve daha yeni bir sürüme dahil edilen Apple 'ın yerleşik Kerberos uzantısını kullanın. Bu seçenek, **kimlik bilgisi** uygulama uzantısının Kerberos 'a özgü bir sürümüdür.

  > [!TIP]
  > **Kimlik bilgisi** türü ile, uzantısından geçirilecek kendi yapılandırma değerlerinizi eklersiniz. Bunun yerine, **Kerberos** türünde Apple tarafından sunulan yerleşik yapılandırma ayarlarını kullanmayı göz önünde bulundurun.

- **UZANTı kimliği** (Yalnızca kimlik bilgileri): SSO uygulaması uzantınızı `com.apple.ssoexample`tanımlayan paket tanımlayıcısını (gibi) girin.
- **Takım Kimliği** (Yalnızca kimlik bilgileri): SSO uygulaması uzantınızın ekip tanımlayıcısını girin. Takım tanımlayıcısı, Apple tarafından oluşturulan ve `ABCDE12345`gibi 10 karakterlik alfasayısal bir dizedir (sayılar ve harfler). 

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

- Otomatik **bulma** (Yalnızca Kerberos): **Block**olarak ayarlandığında, Kerberos uzantısı Active Directory sitesinin adını belirleyebilmek için OTOMATIK olarak LDAP ve DNS kullanmaz. **Yapılandırılmadı** (varsayılan) uzantının Active Directory site adını otomatik olarak bulmasını sağlar.
- **Parola değişiklikleri** (Yalnızca Kerberos): **Blok** , kullanıcıların, girdiğiniz etki alanlarında oturum açmak için kullandıkları parolaları değiştirmelerini engeller. **Yapılandırılmadı** (varsayılan) parola değişikliklerine izin verir.  
- **Parola eşitleme** (Yalnızca Kerberos): Kullanıcılarınızın yerel parolalarını Azure AD ile eşitlemek için **Etkinleştir** ' i seçin. **Yapılandırılmadı** (varsayılan), Azure AD 'ye parola eşitlemeyi devre dışı bırakır. Bu ayarı, SSO için alternatif veya yedekleme olarak kullanın. Kullanıcılar bir Apple mobil hesabıyla oturum açmışsa bu ayar çalışmaz.
- **Windows Server Active Directory parola karmaşıklığı** (Yalnızca Kerberos): Kullanıcı parolalarının Active Directory parola karmaşıklığı gereksinimlerini karşılamasına zorlamak için **gerektir** ' i seçin. Daha fazla bilgi için bkz. [parolanın karmaşıklık gereksinimlerini karşılaması gerekir](https://docs.microsoft.com/windows/security/threat-protection/security-policy-settings/password-must-meet-complexity-requirements) . **Yapılandırılmadı** (varsayılan), kullanıcıların Active Directory parola gereksinimini karşılamasını gerektirmez.
- **Minimum parola uzunluğu** (Yalnızca Kerberos): Bir kullanıcının parolasını oluşturmak için gereken en az karakter sayısını girin. **Yapılandırılmadı** (varsayılan), kullanıcılar için en az parola uzunluğu zorlamaz.
- **Parola yeniden kullanım sınırı** (Yalnızca Kerberos): Etki alanında önceki bir parolanın yeniden kullanılabilmesi için kullanılması gereken yeni parola sayısını 1-24 adresinden girin. **Yapılandırılmadı** (varsayılan) parola yeniden kullanım sınırını zorlamaz.
- **En az parola yaşı** (Yalnızca Kerberos): Bir kullanıcının değiştirebilmesi için, etki alanında bir parolanın kullanılması gereken gün sayısını girin. **Yapılandırılmadı** (varsayılan), silinmeden önce en az bir parola geçerlilik süresi uygulamaz.
- **Parola süre sonu bildirimi** (Yalnızca Kerberos): Kullanıcıların parolasının süresinin dolacağını belirten bir parolanın süresi dolmadan önce geçecek gün sayısını girin. **Yapılandırılmadı** (varsayılan) günleri `15` kullanır.
- **Parola süre sonu** (Yalnızca Kerberos): Cihaz parolasının değiştirilmesi gerekmeden önce geçmesi gereken gün sayısını girin. **Yapılandırılmadı** (varsayılan) kullanıcı parolalarının hiçbir zaman sona ermediği anlamına gelir.
- **Asıl ad** (Yalnızca Kerberos): Kerberos sorumlusunun Kullanıcı adını girin. Bölge adını eklemeniz gerekmez. Örneğin, içinde `user@contoso.com` `user` asıl addır ve `contoso.com` bölge adıdır.
- **Active Directory site kodu** (Yalnızca Kerberos): Kerberos uzantısının kullanması gereken Active Directory sitenin adını girin. Kerberos uzantısı Active Directory site kodunu otomatik olarak bulagerekebilmeniz için bu değeri değiştirmeniz gerekebilir.
- **Önbellek adı** (Yalnızca Kerberos): Kerberos önbelleğinin genel güvenlik hizmetleri (GSS) adını girin. Büyük olasılıkla bu değeri ayarlamanız gerekmez.  
- **Parola gereksinimleri iletisi** (Yalnızca Kerberos): Kullanıcılara gösterilen, kuruluşunuzun parola gereksinimlerinin bir metin sürümünü girin. İleti, Active Directory parola karmaşıklığı gereksinimlerine gerek duymuyorsanız veya en az parola uzunluğu girmezseniz görüntülenir.  
- **Uygulama paketi kimlikleri** (Yalnızca Kerberos): Cihazlarınızda çoklu oturum açma kullanması gereken uygulama paketi tanımlayıcılarını **ekleyin** . Bu uygulamalara, Kerberos Anahtar verme bileti, kimlik doğrulama bileti ve kullanıcılara erişim yetkisi oldukları hizmetler için kimlik doğrulaması erişimi verilir.
- **Etki alanı bölge eşleme** (Yalnızca Kerberos): Bölge ile eşleşmesi gereken etki alanı DNS soneklerini **ekleyin** . Ana bilgisayarların DNS adları bölge adıyla eşleşmezse bu ayarı kullanın. Büyük olasılıkla bu özel etki alanı/bölge eşlemesini oluşturmanız gerekmez.

## <a name="associated-domains"></a>İlişkili etki alanları

Intune 'da şunları yapabilirsiniz:

- Birçok uygulamadan etki alanı ilişkilendirmesi ekleyin.
- Birçok etki alanını aynı uygulamayla ilişkilendirin.

Bu özellik şu platformlarda geçerlidir:

- macOS 10,15 ve üzeri

### <a name="settings-apply-to-all-enrollment-types"></a>Ayarlar için geçerlidir: Tüm kayıt türleri

- **Uygulama kimliği**: Bir Web sitesiyle ilişkilendirilecek uygulamanın uygulama tanımlayıcısını girin. Uygulama tanımlayıcısı, takım KIMLIĞINI ve paket KIMLIĞINI içerir: `TeamID.BundleID`.

  Takım KIMLIĞI, uygulama geliştiricileriniz `ABCDE12345`için Apple tarafından oluşturulan 10 karakterlik alfasayısal bir dizedir (harfler ve rakamlar). [Takım kimliğinizi](https://help.apple.com/developer-account/#/dev55c3c710c) bulun (Apple 'ın Web sitesini açar) daha fazla bilgi içerir.

  Paket KIMLIĞI, uygulamayı benzersiz şekilde tanımlar ve genellikle ters etki alanı adı gösteriminde biçimlendirilir. Örneğin, Finder `com.apple.finder`'ın paket kimliği. Paket KIMLIĞINI bulmak için terminalde AppleScript kullanın:

  `osascript -e 'id of app "ExampleApp"'`

- **Etki alanı**: Bir uygulamayla ilişkilendirilecek Web sitesi etki alanını girin. Etki alanı, `webcredentials:www.contoso.com`bir hizmet türü ve gibi tam konak adı içerir.

  Hizmet türü şu olabilir:

  - **authsrv**: Çoklu oturum açma uygulama uzantısı
  - **uygulama bağlantısı**: Evrensel bağlantı
  - **Web kimlik bilgileri**: Parola otomatik doldurma

- **Ekle**: Uygulamalarınızı ve ilişkili etki alanlarınızı eklemek için seçin.

> [!TIP]
> MacOS cihazınızda sorun gidermek için **Sistem Tercihleri** > **profilleri**' ni açın. Oluşturduğunuz profilin cihaz profilleri listesinde olduğunu onaylayın. Listeleniyorsa, **Ilişkili etki alanı yapılandırmasının** profilde olduğundan emin olun ve doğru uygulama kimliği ve etki alanlarını içerir.

## <a name="next-steps"></a>Sonraki adımlar

[Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).

[İOS](ios-device-features-settings.md)üzerinde cihaz özelliklerini de yapılandırabilirsiniz.
