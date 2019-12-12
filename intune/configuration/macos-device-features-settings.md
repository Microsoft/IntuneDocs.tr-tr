---
title: Microsoft Intune-Azure 'da macOS cihaz özelliği ayarları | Microsoft Docs
description: MacOS cihazlarını AirPrint için yapılandırma ayarlarına bakın ve Microsoft Intune içindeki güç düğmelerini göstermek veya gizlemek için oturum açma penceresini özelleştirin. Ağınızdaki bir AirPrint sunucusunun IP adresini, yolunu ve bağlantı noktası ayarlarını almak için adımlara bakın. MacOS cihaz özelliklerini yapılandırmak için bu ayarları bir cihaz yapılandırma profilinde kullanın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/12/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: ''
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5519bdc405e725556db18d36fa98289c4edb5090
ms.sourcegitcommit: df8e2c052fafb2d5d4e9b4fcd831ae0ecf7f8d16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74992907"
---
# <a name="macos-device-feature-settings-in-intune"></a>Intune 'da macOS cihaz özelliği ayarları

Intune, macOS cihazlarınızdaki özellikleri özelleştirmek için bazı yerleşik ayarlar içerir. Örneğin, Yöneticiler AirPrint yazıcıları ekleyebilir, kullanıcıların oturum açma biçimini seçebilir, güç denetimlerini yapılandırabilir, çoklu oturum açma kimlik doğrulaması kullanabilir ve daha fazlasını yapabilir.

Bu özellikleri, macOS cihazlarını mobil cihaz yönetimi (MDM) çözümünüzün bir parçası olarak denetlemek için kullanın.

Bu makale, bu ayarları listeler ve her ayarın ne yaptığını açıklar. Ayrıca, Terminal uygulaması 'nı (öykünücü) kullanarak AirPrint yazıcılarının IP adresini, yolunu ve bağlantı noktasını almak için gereken adımları listeler. Cihaz özellikleri hakkında daha fazla bilgi için bkz. [iOS veya macOS cihaz özelliği ayarları ekleme](device-features-configure.md).

## <a name="before-you-begin"></a>Başlamadan önce

[MacOS cihaz yapılandırma profili oluşturun](device-features-configure.md).

> [!NOTE]
> Bu ayarlar, bazı ayarların tüm kayıt seçeneklerine uygulanmasıyla farklı kayıt türleri için geçerlidir. Farklı kayıt türleri hakkında daha fazla bilgi için bkz. [MacOS kaydı](../enrollment/macos-enroll.md).

## <a name="airprint"></a>AirPrint

### <a name="settings-apply-to-device-enrollment-and-automated-device-enrollment"></a>Ayarlar için geçerlidir: cihaz kaydı ve otomatik cihaz kaydı 

- **IP adresi**: yazıcının IPv4 veya IPv6 adresini girin. Yazıcıları tanımlamak için konak adlarını kullanıyorsanız, Terminal uygulamasındaki yazıcıya ping ekleyerek IP adresini alabilirsiniz. [IP adresini ve yolu al](#get-the-ip-address-and-path) (Bu makalede) daha fazla ayrıntı sağlar.
- **Yol**: yazıcının yolunu girin. Yol, genellikle ağınızdaki yazıcılar için `ipp/print`. [IP adresini ve yolu al](#get-the-ip-address-and-path) (Bu makalede) daha fazla ayrıntı sağlar.
- **Bağlantı noktası** (iOS 11,0 ve üzeri): AirPrint hedefinin dinleme bağlantı noktasını girin. Bu özelliği boş bırakırsanız AirPrint varsayılan bağlantı noktasını kullanır.
- **TLS** (iOS 11,0 ve üzeri): Aktarım katmanı GÜVENLIĞI (TLS) Ile güvenli AirPrint bağlantıları sağlamak için **Etkinleştir** ' i seçin.

- **Ekle** AirPrint sunucusu. Birçok AirPrint sunucusu ekleyebilirsiniz.

Ayrıca, AirPrint yazıcılarının listesini içeren bir virgülle ayrılmış dosyayı (. csv) **Içeri aktarabilirsiniz** . Ayrıca, Intune 'A AirPrint yazıcıları ekledikten sonra bu listeyi **dışarı aktarabilirsiniz** .

### <a name="get-the-ip-address-and-path"></a>IP adresini ve yolu al

AirPrinter sunucuları eklemek için, yazıcının IP adresi, kaynak yolu ve bağlantı noktası gerekir. Aşağıdaki adımlarda bu bilgilerin nasıl alınacağı gösterilmektedir.

1. AirPrint yazıcıları ile aynı yerel ağa (alt ağ) bağlı bir Mac üzerinde, açık **Terminal** ( **/Applications/Utilities**).
2. Terminal uygulamasında `ippfind`yazın ve ENTER ' u seçin.

    Yazıcı bilgilerini aklınızda edin. Örneğin, `ipp://myprinter.local.:631/ipp/port1`benzer bir işlem döndürebilir. İlk bölüm, yazıcının adıdır. Son Bölüm (`ipp/port1`) kaynak yoludur.

3. Terminalde `ping myprinter.local`yazın ve ENTER ' u seçin.

   IP adresini aklınızda edin. Örneğin, `PING myprinter.local (10.50.25.21)`benzer bir işlem döndürebilir.

4. IP adresi ve kaynak yolu değerlerini kullanın. Bu örnekte, IP adresi `10.50.25.21`ve kaynak yolu `/ipp/port1`.

## <a name="login-items"></a>Oturum açma öğeleri

### <a name="settings-apply-to-all-enrollment-types"></a>Ayarlar için geçerlidir: tüm kayıt türleri

- **Dosyalar, klasörler ve özel uygulamalar**: bir Kullanıcı cihazda oturum açtığında açmak istediğiniz bir dosya, klasör, özel uygulama veya sistem uygulamasının yolunu **ekleyin** . Kuruluşunuz için oluşturulmuş veya özelleştirilmiş olan sistem uygulamaları veya uygulamalar genellikle `Applications` klasöründedir ve `/Applications/AppName.app`benzer bir yoldur. 

  Birçok dosya, klasör ve uygulama ekleyebilirsiniz. Örneğin şunu girin:  
  
  - `/Applications/Calculator.app`
  - `/Applications`
  - `/Applications/Microsoft Office/root/Office16/winword.exe`
  - `/Users/UserName/music/itunes.app`
  
  Herhangi bir uygulama, klasör veya dosya eklerken doğru yolu girdiğinizden emin olun. Tüm öğeler `Applications` klasöründedir. Bir Kullanıcı bir öğeyi bir konumdan diğerine taşıdıysanız yol değişir. Bu taşınan öğe, Kullanıcı oturum açtığında açılmaz.

## <a name="login-window"></a>Oturum açma penceresi

### <a name="settings-apply-to-device-enrollment-and-automated-device-enrollment"></a>Ayarlar için geçerlidir: cihaz kaydı ve otomatik cihaz kaydı

#### <a name="window-layout"></a>Pencere düzeni

- **Menü çubuğunda ek bilgileri göster**: menü çubuğundaki saat alanı **seçildiğinde, ana** bilgisayar adı ve MacOS sürümünü gösterir. **Yapılandırılmadı** (varsayılan), bu bilgileri menü çubuğunda göstermez.
- **Başlık**: cihazda oturum açma ekranında gösterilen bir ileti girin. Örneğin, kuruluş bilgilerinizi, bir hoş geldiniz iletisini, kayıp ve bulunan bilgileri girin ve bu şekilde devam edin.
- **Oturum açma biçimini seçin**: kullanıcıların cihazda nasıl oturum açmasını seçin. Seçenekleriniz şunlardır:
  - **Kullanıcı adı ve parola iste** (varsayılan): kullanıcıların bir Kullanıcı adı ve parola girmesini gerektirir.
  - **Tüm kullanıcıları Listele, parola iste**: Kullanıcıların Kullanıcı listesinden kullanıcı adını seçmesini ve sonra parolasını girmesini gerektirir. Ayrıca şunları yapılandırın:

    - **Yerel kullanıcılar**: **Gizle** , yerel kullanıcı hesaplarını, standart ve yönetici hesaplarını içerebilecek Kullanıcı listesinde göstermez. Yalnızca ağ ve sistem kullanıcı hesapları gösterilir. **Yapılandırılmadı** (varsayılan) Kullanıcı listesindeki yerel kullanıcı hesaplarını gösterir.
    - **Mobil hesaplar**: **Gizle** , Kullanıcı listesinde mobil hesapları göstermez. **Yapılandırılmadı** (varsayılan) Kullanıcı listesindeki mobil hesapları gösterir. Bazı mobil hesaplar, ağ kullanıcıları olarak gösterilebilir.
    - **Ağ kullanıcıları**: ağ kullanıcılarını Kullanıcı listesinde listelemek için **göster** ' i seçin. **Yapılandırılmadı** (varsayılan), Kullanıcı listesinde ağ kullanıcı hesaplarını göstermez.
    - **Yönetici kullanıcılar**: **Gizle** , Kullanıcı listesinde Yönetici Kullanıcı hesaplarını göstermez. **Yapılandırılmadı** (varsayılan) Kullanıcı listesindeki yönetici kullanıcı hesaplarını gösterir.
    - **Diğer kullanıcılar**: Kullanıcı listesindeki **diğer...** kullanıcıları listelemek için **göster** ' i seçin. **Yapılandırılmadı** (varsayılan) Kullanıcı listesindeki diğer Kullanıcı hesaplarını göstermez.

#### <a name="login-screen-power-settings"></a>Oturum açma ekranı güç ayarları

- **Kapat düğmesi**: **Gizle** , oturum açma ekranında Kapat düğmesini göstermez. **Yapılandırılmadı** (varsayılan), kapanıyor düğmesini gösterir.
- **Yeniden Başlat düğmesi**: **Gizle** , oturum açma ekranında yeniden Başlat düğmesini göstermez. **Yapılandırılmadı** (varsayılan) yeniden Başlat düğmesini gösterir.
- **Uyku düğmesi**: **Gizle** , oturum açma ekranında uyku düğmesini göstermez. **Yapılandırılmadı** (varsayılan) uyku düğmesini gösterir.

#### <a name="other"></a>Diğer

- **Konsoldan Kullanıcı oturumunu devre dışı bırak**: **devre dışı bırak** , oturum açmak için kullanılan MacOS komut satırını gizler. Tipik kullanıcılar için bu ayarı **devre dışı bırakın** . **Yapılandırılmadı** (varsayılan), gelişmiş kullanıcıların MacOS komut satırını kullanarak oturum açmasına izin verir. Konsol modunu girmek için, kullanıcılar Kullanıcı adı alanına `>console` girer ve konsol penceresinde kimlik doğrulaması yapılmalıdır.

#### <a name="apple-menu"></a>Apple menüsü

Kullanıcılar cihazlarda oturum açtıktan sonra, aşağıdaki ayarlar neler yapabileceğini etkiler.

- **Kapatmayı devre dışı bırak**: **devre dışı** bırak seçeneği, Kullanıcı oturum açtıktan sonra kullanıcıların **kapatma** seçeneğini seçmesini önler. **Yapılandırılmadı** (varsayılan), kullanıcıların cihazdaki **kapalı** menü öğesini seçmesine izin verir.
- **Yeniden başlatmayı devre dışı bırak**: **devre dışı bırak** seçeneği, kullanıcıların oturum açtıktan sonra **yeniden başlatma** seçeneğini seçmesini önler. **Yapılandırılmadı** (varsayılan), kullanıcıların cihazdaki **Yeniden Başlat** menü öğesini seçmesine izin verir.
- Kapatmayı **devre dışı bırak**: **devre dışı bırak** seçeneği, Kullanıcı oturum açtıktan sonra kullanıcıların **kapatma** seçeneğini seçmesini önler. **Yapılandırılmadı** (varsayılan), kullanıcıların cihazdaki **kapatma** menü öğesini seçmesine izin verir.
- **Oturumu devre dışı bırak** (macos 10,13 ve üzeri): **Disable** seçeneği, kullanıcıların oturum açtıktan sonra **oturum kapatma** seçeneğini seçmesini önler. **Yapılandırılmadı** (varsayılan), kullanıcıların cihazdaki **oturum kapatma** menü öğesini seçmesine izin verir.
- **Kilit ekranını devre dışı bırak** (macos 10,13 ve üzeri): **Disable** seçeneği, Kullanıcı oturum açtıktan sonra kullanıcıların **kilit ekranı** seçmesini önler. **Yapılandırılmadı** (varsayılan), kullanıcıların cihazdaki **kilit ekranı** menü öğesini seçmesine izin verir.

## <a name="single-sign-on-app-extension"></a>Çoklu oturum açma uygulama uzantısı

Bu özellik şu platformlarda geçerlidir:

- macOS 10,15 ve üzeri

### <a name="settings-apply-to-all-enrollment-types"></a>Ayarlar için geçerlidir: tüm kayıt türleri 

- **SSO uygulama uzantısı türü**: KIMLIK bilgisi SSO uygulaması uzantısının türünü seçin. Seçenekleriniz şunlardır:

  - **Yapılandırılmadı**: uygulama uzantıları kullanılmıyor. Bir uygulama uzantısını devre dışı bırakmak için, SSO uygulama uzantısı türünü **Yapılandırılmadı**olarak değiştirin.
  - **Yeniden yönlendir**: Modern kimlik doğrulama akışlarıyla SSO gerçekleştirmek için genel, özelleştirilebilir bir yeniden yönlendirme uygulama uzantısı kullanın. Kuruluşunuzun uygulama uzantısının uzantısını ve takım KIMLIĞINI öğrendiğinizden emin olun.
  - **Kimlik bilgisi**: sınama ve yanıt kimlik doğrulama akışlarıyla SSO gerçekleştirmek için genel, özelleştirilebilir bir kimlik bilgisi uygulama uzantısı kullanın. Kuruluşunuzun SSO uygulaması uzantısının uzantı KIMLIĞINI ve takım KIMLIĞINI öğrendiğinizden emin olun.  
  - **Kerberos**: MacOS Catalina 10,15 ve daha yeni bir sürüme dahil edilen Apple 'ın yerleşik Kerberos uzantısını kullanın. Bu seçenek, **kimlik bilgisi** uygulama uzantısının Kerberos 'a özgü bir sürümüdür.

  > [!TIP]
  > **Yeniden yönlendirme** ve **kimlik bilgisi** türleriyle, uzantıdan geçirilecek kendi yapılandırma değerlerinizi eklersiniz. **Kimlik**bilgileriniz kullanıyorsanız, Apple tarafından **Kerberos** türünde sunulan yerleşik yapılandırma ayarlarını kullanmayı göz önünde bulundurun.

- **UZANTı kimliği** (yeniden yönlendirme ve kimlik bilgisi): `com.apple.ssoexample`gibi SSO uygulama uzantınızı tanımlayan paket tanımlayıcısını girin.
- **Takım Kimliği** (yeniden yönlendirme ve kimlik bilgisi): SSO uygulama uzantınızın ekip tanımlayıcısını girin. Takım tanımlayıcısı, Apple tarafından oluşturulan `ABCDE12345`gibi 10 karakterlik alfasayısal bir dizedir (sayılar ve harfler). 

  [Takım kimliğinizi bulun](https://help.apple.com/developer-account/#/dev55c3c710c) (Apple 'ın Web sitesini açar) daha fazla bilgi içerir.

- **Bölge** (kimlik bilgileri ve Kerberos): kimlik doğrulama Realm adını girin. Bölge adı, `CONTOSO.COM`gibi büyük harfli olmalıdır. Genellikle, bölge adınız DNS etki alanı adınızla aynıdır, ancak tümü büyük harfle aynıdır.

- **Etki alanları** (kimlik bilgileri ve Kerberos): SSO aracılığıyla kimlik doğrulayabilecek sitelerin etki alanı veya ana bilgisayar adlarını girin. Örneğin, Web siteniz `mysite.contoso.com`, `mysite` ana bilgisayar adıdır ve `contoso.com` etki alanı adıdır. Kullanıcılar bu sitelerden birine bağlandıklarında, uygulama uzantısı kimlik doğrulama sınamasını işler. Bu kimlik doğrulaması, kullanıcıların oturum açmak için yüz KIMLIĞI, Touch ID veya Apple pincode/geçiş kodu kullanmasına izin verir.

  - Çoklu oturum açma uygulama uzantılarınızın Intune profillerindeki tüm etki alanları benzersiz olmalıdır. Farklı türlerde SSO uygulama uzantıları kullanıyor olsanız bile, bir etki alanını hiçbir oturum açma uygulama uzantısı profilinde tekrarlayamıyorum.
  - Bu etki alanları büyük/küçük harfe duyarlı değildir.

- **URL 'ler** (yalnızca yeniden yönlendir): kimlik SAĞLAYıCıLARıNıZıN URL öneklerini girin adına yeniden yönlendirme uygulama uzantısı SSO 'yu gerçekleştirir. Bir Kullanıcı bu URL 'lere yeniden yönlendirildiğinde, SSO uygulama uzantısı, SSO 'yu ve bu URL 'yi istemez.

  - Intune çoklu oturum açma uygulama uzantısı profillerindeki tüm URL 'Lerin benzersiz olması gerekir. Farklı türlerde SSO uygulama uzantıları kullanıyor olsanız bile, hiçbir SSO uygulama uzantısı profilinde bir etki alanını tekrarlayabilirsiniz.
  - URL 'Lerin http://veya https://ile başlaması gerekir.

- **Ek yapılandırma** (yeniden yönlendirme ve kimlik bilgileri): SSO uygulama uzantısına geçirilecek uzantıya özgü ek veriler girin:
  - **Anahtar**: `user name`gibi eklemek istediğiniz öğenin adını girin.
  - **Tür**: veri türünü girin. Seçenekleriniz şunlardır:

    - Dize
    - Boole: **yapılandırma değeri**' nde `True` veya `False`girin.
    - Tamsayı: **yapılandırma değeri**alanına bir sayı girin.
    
  - **Değer**: verileri girin.
  
  - **Ekle**: yapılandırma anahtarlarınızı eklemek için seçin.

- **Anahtarlık kullanımı** (yalnızca Kerberos): parolaların anahtarlıkta kaydedilmesini ve saklanmasını engellemek için **Engelle** ' yi seçin. **Yapılandırılmadı** (varsayılan), parolaların anahtarlıkta kaydedilmesine ve depolanmasına izin verir.  
- **Yüz kimliği, Touch ID veya geçiş kodu** (yalnızca Kerberos): **gerekli** olan etki alanlarında oturum açmak için kullanıcıların yüz kimliğini, Touch ID 'sini veya Apple geçiş kodunu girmesini zorlar. **Yapılandırılmadı** (varsayılan), kullanıcıların oturum açmak için Biyometri veya geçiş kodu kullanmalarını gerektirmez.
- **Varsayılan bölge** (yalnızca Kerberos): Girdiğiniz **bölge** değerini varsayılan bölge olarak ayarlamak Için **Etkinleştir** ' i seçin. **Yapılandırılmadı** (varsayılan) varsayılan bir bölge yapmaz.

  > [!TIP]
  > - Kuruluşunuzda birden çok Kerberos SSO uygulama uzantısını yapılandırıyorsanız, bu ayarı **etkinleştirin** .
  > - Birden çok bölge kullanıyorsanız bu ayarı **etkinleştirin** . Girdiğiniz **bölge** değerini varsayılan bölge olarak ayarlar.
  > - Yalnızca bir bölge varsa, **Yapılandırılmadı** (varsayılan) olarak bırakın.

- Otomatik **bulma** (yalnızca Kerberos): **blok**olarak ayarlandığında, Kerberos uzantısı Active Directory site adını BELIRLEYEBILMEK için OTOMATIK olarak LDAP ve DNS kullanmaz. **Yapılandırılmadı** (varsayılan) uzantının Active Directory site adını otomatik olarak bulmasını sağlar.
- **Parola değişiklikleri** (yalnızca Kerberos): **Block** , kullanıcıların, girdiğiniz etki alanlarında oturum açmak için kullandıkları parolaları değiştirmelerini engeller. **Yapılandırılmadı** (varsayılan) parola değişikliklerine izin verir.  
- **Parola eşitleme** (yalnızca Kerberos): kullanıcılarınızın yerel PAROLALARıNı Azure AD 'ye eşitlemek için **Etkinleştir** ' i seçin. **Yapılandırılmadı** (varsayılan), Azure AD 'ye parola eşitlemeyi devre dışı bırakır. Bu ayarı, SSO için alternatif veya yedekleme olarak kullanın. Kullanıcılar bir Apple mobil hesabıyla oturum açmışsa bu ayar çalışmaz.
- **Windows Server Active Directory parola karmaşıklığı** (yalnızca Kerberos): kullanıcı parolalarının Active Directory parola karmaşıklığı gereksinimlerini karşılamasına zorlamak için **gerektir** ' i seçin. Daha fazla bilgi için bkz. [parolanın karmaşıklık gereksinimlerini karşılaması gerekir](https://docs.microsoft.com/windows/security/threat-protection/security-policy-settings/password-must-meet-complexity-requirements) . **Yapılandırılmadı** (varsayılan), kullanıcıların Active Directory parola gereksinimini karşılamasını gerektirmez.
- **Minimum parola uzunluğu** (yalnızca Kerberos): bir kullanıcının parolasını oluşturmak için gereken en az karakter sayısını girin. **Yapılandırılmadı** (varsayılan), kullanıcılar için en az parola uzunluğu uygulamaz.
- **Parola yeniden kullanım sınırı** (yalnızca Kerberos): etki alanında önceki bir parolanın yeniden kullanılabilmesi için kullanılması gereken yeni parola sayısını 1-24 ' dan girin. **Yapılandırılmadı** (varsayılan) parola yeniden kullanım sınırını zorlamaz.
- **En az parola yaşı** (yalnızca Kerberos): bir kullanıcının değiştirebilmesi için, etki alanında bir parolanın kullanılması gereken gün sayısını girin. **Yapılandırılmadı** (varsayılan), silinmeden önce en az bir parola geçerlilik süresi uygulamaz.
- **Parola süre sonu bildirimi** (yalnızca Kerberos): parolanın süresi dolmadan önce kullanıcıların parolasının süresinin dolacağını belirten gün sayısını girin. **Yapılandırılmadı** (varsayılan) `15` gün kullanır.
- **Parola kullanım süresi** (yalnızca Kerberos): cihaz parolasının değiştirilmesi gereken gün sayısını girin. **Yapılandırılmadı** (varsayılan) kullanıcı parolalarının hiçbir zaman dolmayacağı anlamına gelir.
- **Parola değiştirme URL 'si** (yalnızca Kerberos): Kullanıcı Kerberos parola değişikliğini başlattığında başlatılan URL 'yi girin.
- **Asıl ad** (yalnızca Kerberos): Kerberos sorumlusunun Kullanıcı adını girin. Bölge adını eklemeniz gerekmez. Örneğin, `user@contoso.com``user` asıl addır ve `contoso.com` bölge adıdır.

  > [!TIP]
  > - Büyük köşeli ayraç `{{ }}`girerek asıl ad içindeki değişkenleri de kullanabilirsiniz. Örneğin, Kullanıcı adını göstermek için `Username: {{username}}`girin. 
  > - Ancak, değişkenler kullanıcı arabiriminde doğrulanmamış ve büyük/küçük harfe duyarlı olduğundan değişken değiştirme konusunda dikkatli olun. Doğru bilgileri girdiğinizden emin olun.
  
- **Active Directory site kodu** (yalnızca Kerberos): Kerberos uzantısının kullanması gereken Active Directory sitenin adını girin. Kerberos uzantısı Active Directory site kodunu otomatik olarak bulagerekebilmeniz için bu değeri değiştirmeniz gerekebilir.
- **Önbellek adı** (yalnızca Kerberos): Kerberos önbelleğinin genel güvenlik HIZMETLERI (GSS) adını girin. Büyük olasılıkla bu değeri ayarlamanız gerekmez.  
- **Parola gereksinimleri iletisi** (yalnızca Kerberos): kuruluşunuzun, kullanıcılara gösterilen parola gereksinimlerinin bir metin sürümünü girin. İleti, Active Directory parola karmaşıklığı gereksinimlerine gerek duymuyorsanız veya en az parola uzunluğu girmezseniz görüntülenir.  
- **Uygulama paketi kimlikleri** (yalnızca Kerberos): cihazlarınızda çoklu oturum açma kullanması gereken uygulama paketi tanımlayıcılarını **ekleyin** . Bu uygulamalara, Kerberos Anahtar verme bileti, kimlik doğrulama bileti ve kullanıcılara erişim yetkisi oldukları hizmetler için kimlik doğrulaması erişimi verilir.
- **Etki alanı bölge eşlemesi** (yalnızca Kerberos): bölge ile eşleşmesi gereken etkı alanı DNS soneklerini **ekleyin** . Ana bilgisayarların DNS adları bölge adıyla eşleşmezse bu ayarı kullanın. Büyük olasılıkla bu özel etki alanı/bölge eşlemesini oluşturmanız gerekmez.
- **PKINIT sertifikası** (yalnızca Kerberos): Kerberos kimlik doğrulaması Için kullanılabilecek Ilk kimlik doğrulaması (PKI) sertifikası Için ortak anahtar şifrelemesini **seçin** . Intune 'A eklediğiniz [PKCS](../protect/certficates-pfx-configure.md) veya [SCEP](../protect/certificates-scep-configure.md) sertifikaları arasından seçim yapabilirsiniz. Sertifikalar hakkında daha fazla bilgi için bkz. [Microsoft Intune kimlik doğrulaması için sertifikaları kullanma](../protect/certificates-configure.md).

## <a name="associated-domains"></a>İlişkili etki alanları

Intune 'da şunları yapabilirsiniz:

- Birçok uygulamadan etki alanı ilişkilendirmesi ekleyin.
- Birçok etki alanını aynı uygulamayla ilişkilendirin.

Bu özellik şu platformlarda geçerlidir:

- macOS 10,15 ve üzeri

### <a name="settings-apply-to-all-enrollment-types"></a>Ayarlar için geçerlidir: tüm kayıt türleri

- **Uygulama kimliği**: bir Web sitesiyle ilişkilendirilecek uygulamanın uygulama tanımlayıcısını girin. Uygulama tanımlayıcısı, takım KIMLIĞINI ve paket KIMLIĞINI içerir: `TeamID.BundleID`.

  Takım KIMLIĞI, uygulama geliştiricileriniz için `ABCDE12345`gibi Apple tarafından oluşturulan 10 karakterlik alfasayısal bir dizedir (harfler ve rakamlar). [Takım kimliği bulun](https://help.apple.com/developer-account/#/dev55c3c710c) (Apple 'ın Web sitesini açar) daha fazla bilgi içerir.

  Paket KIMLIĞI, uygulamayı benzersiz şekilde tanımlar ve genellikle ters etki alanı adı gösteriminde biçimlendirilir. Örneğin, Finder 'ın paket KIMLIĞI `com.apple.finder`. Paket KIMLIĞINI bulmak için terminalde AppleScript kullanın:

  `osascript -e 'id of app "ExampleApp"'`

- **Etki alanı**: bir uygulamayla ilişkilendirilecek Web sitesi etki alanını girin. Etki alanı, `webcredentials:www.contoso.com`gibi bir hizmet türü ve tam konak adı içerir.

  Etki alanının başlangıcından önce `*.` (bir yıldız joker karakteri ve bir nokta) girerek ilişkili bir etki alanının tüm alt etki alanlarını eşleştirebilirsiniz. Süre gereklidir. Tam etki alanları joker etki alanlarından daha yüksek önceliğe sahiptir. Bu nedenle, tam alt etki *alanında bir eşleşme* bulunmazsa üst etki alanlarından desenler eşleştirilir.

  Hizmet türü şu olabilir:

  - **authsrv**: çoklu oturum açma uygulama uzantısı
  - **AppLink**: evrensel bağlantı
  - **WebCredentials**: parola otomatik doldurma

- **Ekle**: uygulamalarınızı ve ilişkili etki alanlarınızı eklemek için seçin.

> [!TIP]
> MacOS cihazınızda sorun gidermek için, **sistem tercihleri** > **profiller**' i açın. Oluşturduğunuz profilin cihaz profilleri listesinde olduğunu onaylayın. Listeleniyorsa, **Ilişkili etki alanı yapılandırmasının** profilde olduğundan emin olun ve doğru uygulama kimliği ve etki alanlarını içerir.

## <a name="next-steps"></a>Sonraki adımlar

[Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).

[İOS](ios-device-features-settings.md)üzerinde cihaz özelliklerini de yapılandırabilirsiniz.
