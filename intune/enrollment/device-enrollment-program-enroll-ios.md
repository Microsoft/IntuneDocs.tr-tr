---
title: İOS cihazlarını kaydetme-Aygıt Kayıt Programı
titleSuffix: Microsoft Intune
description: Aygıt Kayıt Programı kullanarak şirkete ait iOS cihazlarını kaydetmeyi öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/07/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 7ddbf360-0c61-11e8-ba89-0ed5f89f718b
ms.reviewer: tisilver
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 19389a21aa28f5fa957f62c988753f46bf1bc731
ms.sourcegitcommit: 46322ca7a92971e18dc0b230f436b9ca892b90c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72008352"
---
# <a name="automatically-enroll-ios-devices-with-apples-device-enrollment-program"></a>İOS cihazlarını Apple 'ın Aygıt Kayıt Programı otomatik olarak kaydetme

Intune 'u Apple 'ın [aygıt kayıt programı (DEP)](https://deploy.apple.com)aracılığıyla satın alınan iOS cihazlarını kaydedecek şekilde ayarlayabilirsiniz. DEP, çok sayıda cihazı hiç dokunmadan kaydetmenizi sağlar. IPhone ve iPads gibi cihazlar doğrudan kullanıcılara sevk edilebilir. Kullanıcı cihazı açtığında, Kurulum Yardımcısı önceden yapılandırılmış ayarlarla çalışır ve cihaz yönetime kaydolur.

DEP kaydını etkinleştirmek için hem Intune hem de Apple DEP portallarını kullanırsınız. Yönetim için Intune 'a cihaz atayabilmeniz için seri numaralarının bir listesi veya bir satın alma siparişi numarası gereklidir. Kayıt sırasında cihazlara uygulanan ayarları içeren DEP kayıt profilleri oluşturabilirsiniz.

Bu şekilde, DEP kaydı [cihaz kayıt yöneticisiyle](device-enrollment-manager-enroll.md)birlikte çalışmaz.

> [!NOTE]
> DEP, son kullanıcı tarafından kaldırılamayan cihaz yapılandırmasını ayarlar. Bu nedenle, [DEP 'e](../fundamentals/migration-guide-considerations.md)geçmeden önce cihazın bir kullanıma hazır (yeni) duruma dönmesi için temizlenmiş olması gerekir.

## <a name="dep-and-the-company-portal"></a>DEP ve Şirket Portalı

DEP kayıtları, Şirket Portalı uygulamasının App Store sürümü ile uyumlu değildir. Kullanıcılara bir DEP cihazında Şirket Portalı uygulamasına erişim izni verebilirsiniz. Bunlara erişim sağlamak için, DEP profilinde VPP 'yi (toplu satın alma programı) **yükleme Şirket portalı** kullanarak uygulamayı cihaza gönderin. Daha fazla bilgi için bkz. [Apple aygıt kayıt programı iOS cihazlarını otomatik olarak kaydetme](device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile).

 Şirket Portalı uygulamasını DEP ile zaten kaydedilmiş cihazlara yükleyebilirsiniz. Bunu yapmak için, [uygulama yapılandırma ilkesi](../apps/app-configuration-policies-use-ios.md) uygulanmış şekilde ıntune aracılığıyla şirket portalı uygulamasını dağıtın.

## <a name="what-is-supervised-mode"></a>Denetimli mod nedir?

Apple, iOS 5 ' te Denetimli mod sunmuştur. Denetimli moddaki bir iOS cihazı, daha fazla denetim ile yönetilebilir. Bu nedenle, özellikle şirkete ait cihazlar için yararlıdır. Intune, cihaz Denetimli mod için Apple Aygıt Kayıt Programı (DEP) bir parçası olarak yapılandırmayı destekler.

İOS 11 ' de denetimli DEP cihazları için destek kullanımdan kaldırılmıştır. İOS 11 ve sonrasında DEP yapılandırılmış cihazların her zaman denetimli olması gerekir. DEP is_supervised bayrağı gelecekteki bir iOS sürümünde yok sayılacak.

<!--
**Steps to enable enrollment programs from Apple**
1. [Get an Apple DEP token and assign devices](#get-the-apple-dep-token)
2. [Create an enrollment profile](#create-an-apple-enrollment-profile)
3. [Synchronize DEP-managed devices](#sync-managed-device)
4. [Assign DEP profile to devices](#assign-an-enrollment-profile-to-devices)
5. [Distribute devices to users](#end-user-experience-with-managed-devices)
-->
## <a name="prerequisites"></a>Prerequisites
- [Apple aygıt kayıt programı](http://deploy.apple.com) satın alınan cihazlar
- [Mobil cihaz yönetimi (MDM) yetkilisi](../fundamentals/mdm-authority-set.md)
- [Apple MDM anında Iletme sertifikası](apple-mdm-push-certificate-get.md)

## <a name="get-an-apple-dep-token"></a>Apple DEP belirteci al

İOS cihazlarını DEP ile kaydedebilmeniz için önce Apple 'dan bir DEP belirteci (. p7m) dosyası gerekir. Bu belirteç, Intune 'un kuruluşunuzun sahip olduğu DEP cihazlarıyla ilgili bilgileri eşitlemesini sağlar. Ayrıca Intune 'un kayıt profillerini Apple 'a yüklemesine ve cihazları bu profillere atamasına izin verir.

DEP belirteci oluşturmak için Apple DEP portalını kullanın. Ayrıca, yönetim için Intune 'a cihaz atamak üzere DEP portalını de kullanabilirsiniz.

> [!NOTE]
> Azure 'a geçiş yapmadan önce klasik Intune portalından belirteç silerseniz, Intune silinen bir Apple DEP belirtecini geri yükleyebilir. DEP belirtecini Azure portal yeniden silebilirsiniz.

### <a name="step-1-download-the-intune-public-key-certificate-required-to-create-the-token"></a>Adım 1. Belirteci oluşturmak için gereken Intune ortak anahtar sertifikasını indirin.

1. [Azure Portal Intune](https://aka.ms/intuneportal)'Da, **cihaz kaydı** > **Apple kayıt** > **kayıt programı belirteçleri** > **Ekle**' yi seçin.

    ![Kayıt programı belirteci alın.](./media/device-enrollment-program-enroll-ios/image01.png)

2. **Kabul ediyorum ' ı**seçerek Microsoft 'a Kullanıcı ve cihaz bilgilerini Apple 'a gönderme izni verin.

   ![Ortak anahtarı indirmek için Apple sertifikaları çalışma alanındaki kayıt programı belirteci bölmesinin ekran görüntüsü.](./media/device-enrollment-program-enroll-ios/add-enrollment-program-token-pane.png)

3. Şifreleme anahtarı (. pek) dosyasını indirmek ve yerel olarak kaydetmek için **ortak anahtarınızı indirin** ' ı seçin. . Ped dosyası, Apple Aygıt Kayıt Programı portalından güven ilişkisi sertifikası istemek için kullanılır.


### <a name="step-2-use-your-key-to-download-a-token-from-apple"></a>Adım 2. Apple 'dan bir belirteç indirmek için anahtarınızı kullanın.

1. Apple 'ın dağıtım programı Portalını açmak için **Apple 'ın aygıt kayıt programı belirteç oluştur** ' u seçin ve ŞIRKETINIZIN Apple kimliğiyle oturum açın. DEP belirtecinizi yenilemek için bu Apple KIMLIĞINI kullanabilirsiniz.
2. Apple 'ın [dağıtım programları portalında](https://deploy.apple.com) **aygıt kayıt programı**için **kullanmaya başlayın** ' ı seçin.

3. **Sunucuları Yönet** sayfasında **MDM sunucusu Ekle**' yi seçin.
4. **MDM sunucu adını**girin ve ardından **İleri**' yi seçin. Sunucu adı, mobil cihaz yönetimi (MDM) sunucusunu tanımlamak için başvurağınız içindir. Microsoft Intune sunucusunun adı veya URL 'SI değildir.

5. **Add &lt;ServerName @ no__t-2** iletişim kutusu açılarak **ortak anahtarınızı karşıya yüklemeyi**belirten. **Dosya seç... öğesini** seçin . pek dosyasını karşıya yüklemek için **İleri**' yi seçin.

6. **Dağıtım programları** &gt; **aygıt kayıt programı** &gt; **cihazları yönet**' e gidin.
7. **Cihazları seçin**' in altında, cihazların nasıl tanımlandığını belirtin:
    - **Seri numarası**
    - **Sipariş numarası**
    - **CSV dosyasını karşıya yükleyin**.

   ![Cihazları seri numarasına göre seçme seçeneklerini belirleme, ayarı sunucuya ata olarak eylem Seç ve sunucu adını seçme ekran görüntüsü.](./media/device-enrollment-program-enroll-ios/enrollment-program-token-specify-serial.png)

8. **Eylem Seç**Için **sunucuya ata**' yı seçin, Microsoft Intune Için belirtilen &lt;servername @ no__t-3 ' ü seçin ve ardından **Tamam**' ı seçin. Apple portalı, belirtilen cihazları yönetim için Intune sunucusuna atar ve sonra **atama Tamam**' ı görüntüler.

   Apple portalında **dağıtım programları** &gt; **aygıt kayıt programı** &gt; ' ün cihaz listesini ve MDM sunucu atamasını görmek için **atama geçmişini görüntüle** ' ye gidin.

### <a name="step-3-save-the-apple-id-used-to-create-this-token"></a>Adım 3. Bu belirteci oluşturmak için kullanılan Apple KIMLIĞINI kaydedin.

Azure portal Intune 'da, daha sonra başvurmak üzere Apple KIMLIĞINI sağlayın.

![Kayıt programı belirtecini oluşturmak için kullanılan Apple KIMLIĞINI belirtme ve kayıt programı belirtecine göz atma ekran görüntüsü.](./media/device-enrollment-program-enroll-ios/image03.png)

### <a name="step-4-upload-your-token-and-choose-scope-tags"></a>4\. adım. Belirtecinizi karşıya yükleyin ve kapsam etiketlerini seçin.

1. **Apple belirteci** kutusunda, sertifika (. Pez) dosyasına gidin, **Aç**' ı seçin.
2. Bu DEP belirtecine [kapsam etiketleri](../fundamentals/scope-tags.md) uygulamak istiyorsanız **kapsam (Etiketler)** öğesini seçin ve istediğiniz kapsam etiketlerini seçin. Bir belirtece uygulanan kapsam etiketleri, bu belirtece eklenen profiller ve cihazlar tarafından devralınır.
3. **Oluştur**' a tıklayın.

Anında iletme sertifikasıyla, Intune ilkeyi kayıtlı mobil cihazlara ileterek iOS cihazlarını kaydedebilir ve yönetebilir. Intune, kayıt programı hesabınızı görmek için Apple ile otomatik olarak eşitlenir.

## <a name="create-an-apple-enrollment-profile"></a>Apple kayıt profili oluşturma

Belirtecinizi yüklemişseniz, artık DEP cihazları için bir kayıt profili oluşturabilirsiniz. Bir cihaz kayıt profili, kayıt sırasında bir cihaz grubuna uygulanan ayarları tanımlar. DEP belirteci başına 100 kayıt profili sınırı vardır.

> [!NOTE]
> Bir VPP belirteci için yeterli Şirket Portalı lisansı yoksa veya belirtecin süresi dolmuşsa cihazlar engellenir. Bir belirtecin kullanım süreleri dolduğunda veya lisanslar düşük çalışıyorsa, Intune bir uyarı görüntüler.
 

1. Azure portal Intune 'da, **cihaz kaydı** > **Apple kayıt** > **kayıt programı belirteçleri**' ni seçin.
2. Bir belirteç seçin, **profiller** > **Profil oluştur** > **iOS**' u seçin.

    ![Profil ekran görüntüsü oluşturun.](./media/device-enrollment-program-enroll-ios/image04.png)

3. **Temel bilgiler** sayfasında, yönetim amaçları için profil Için bir **ad** ve **Açıklama** girin. Kullanıcılar bu ayrıntıları görmez. Azure Active Directory içinde dinamik bir grup oluşturmak için bu **ad** alanını kullanabilirsiniz. Bu kayıt profiliyle cihazları atamak için Kayıtlıprofilename parametresini tanımlamak üzere profil adını kullanın. [Azure Active Directory dinamik gruplar](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#rules-for-devices)hakkında daha fazla bilgi edinin.

    ![Profil adı ve açıklaması.](./media/device-enrollment-program-enroll-ios/image05.png)

4. **İleri ' yi seçin: cihaz yönetimi ayarları**.

5. **Kullanıcı benzeşimi**için, bu profile sahip cihazların atanmış bir kullanıcı ile mi yoksa atanan kullanıcı olmadan mı kaydolması gerektiğini seçin.
    - **Kullanıcı benzeşimi Ile kaydetme** -kullanıcılara ait olan ve uygulamaları yükleme gibi hizmetler için şirket portalı kullanmak isteyen cihazlar için bu seçeneği belirleyin. ADFS kullanılıyorsa ve kayıt profili, **Kurulum Yardımcısı değil şirket portalı kimlik doğrulaması** içeriyorsa, [WS-Trust 1,3 Kullanıcı adı/karma uç nokta](https://technet.microsoft.com/library/adfs2-help-endpoints) **için** [daha fazla bilgi](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint) gereklidir.

    - **Kullanıcı benzeşimi olmadan kaydetme** -tek bir kullanıcıyla bağlantılı olmayan cihaz için bu seçeneği belirleyin. Yerel Kullanıcı verilerine erişolmayan cihazlar için bu seçeneği kullanın. Şirket Portalı uygulama gibi uygulamalar çalışmaz.

5. **Kullanıcı benzeşimi Ile kaydet**' i seçerseniz, kullanıcıların Apple kurulum yardımcısı yerine Şirket portalı kimlik doğrulamasını sağlayabilirsiniz.

    ![Şirket Portalı kimlik doğrulaması yapın.](./media/device-enrollment-program-enroll-ios/authenticatewithcompanyportal.png)

    > [!NOTE]
    > Aşağıdakilerden birini yapmak istiyorsanız, kullanıcıların **Şirket portalı** **kimlik doğrulaması gereken yeri seçin** ' i belirleyin.
    >    - çok faktörlü kimlik doğrulaması kullan
    >    - ilk oturum açtıklarında parolalarını değiştirmesi gereken kullanıcılara sor
    >    - kullanıcıların kayıt sırasında süre dolma parolalarını sıfırlamalarını iste
    >
    > Bu, Apple Kurulum Yardımcısı ile kimlik doğrulanırken desteklenmez.

6. **Kullanıcıların kimliğini doğrulamak**için **Şirket Portalı** seçtiyseniz, Şirket portalı cihaza otomatik olarak yüklemek için bir VPP belirteci kullanabilirsiniz. Bu durumda, kullanıcının bir Apple KIMLIĞI sağlaması gerekmez. Şirket Portalı VPP belirteci ile yüklemek için, **VPP Ile ınstall Şirket portalı**altında bir belirteç seçin. Şirket Portalı VPP belirtecine zaten eklenmiş olmasını gerektirir. İlkeyi kullanıcılara gerektirecek şekilde yapılandırmayın, Intune bu kayıt profili uygulanmış cihazlara Şirket Portalı otomatik olarak yükler. Belirtecin süre sonu olmadığından ve Şirket Portalı uygulama için yeterli cihaz lisansına sahip olduğunuzdan emin olun. Belirtecin süresi dolar veya lisans biterse, Intune bunun yerine Şirket Portalı App Store 'u yükleyerek bir Apple KIMLIĞI ister. 

    > [!NOTE]
    > **Kullanıcıların kimlik doğrulaması yapması gereken yeri seçin** **Şirket portalı**, cihaz kayıt IŞLEMININ, Şirket portalının DEP cihazına indirilmekte olan ilk 24 saat içinde gerçekleştirildiğinden emin olun. Aksi takdirde kayıt başarısız olabilir ve cihazı kaydetmek için bir fabrika sıfırlaması gerekecektir.
    
    ![VPP ile şirket portalı 'nı yüklemeye yönelik ekran görüntüsü.](./media/device-enrollment-program-enroll-ios/install-cp-with-vpp.png)

7. **Kullanıcıların kimlik doğrulaması yapması gereken yeri seç**Için **Kurulum Yardımcısı** ' nı seçtiyseniz, ancak aynı zamanda koşullu erişimi kullanmak veya cihazlarda şirket uygulamaları dağıtmak istiyorsanız, Şirket portalı cihazlara yüklenmelidir. Bunu yapmak için, **Şirket portalı yüklemek**için **Evet** ' i seçin.  Kullanıcıların uygulama mağazasındaki kimlik doğrulaması yapmadan Şirket Portalı almasını istiyorsanız, **VPP ile şirket portalı yüklemeyi** seçin ve bir VPP belirteci seçin. Belirtecin kullanım süreleri dolana ve Şirket Portalı uygulamasının doğru bir şekilde dağıtılması için yeterli cihaz lisansına sahip olduğunuzdan emin olun.

8. **VPP Ile yükleme Şirket portalı**için bir belirteç seçerseniz, Kurulum Yardımcısı tamamlandıktan hemen sonra cihazı tek uygulama modunda (özel olarak, Şirket portalı uygulama) kilitlemeniz gerekir. Bu seçeneği ayarlamak için **kimlik doğrulaması yapılıncaya kadar tek uygulama modunda Şirket portalı Çalıştır** için **Evet** ' i seçin. Cihazı kullanmak için, kullanıcının Şirket Portalı kullanarak oturum açması için öncelikle kimlik doğrulaması gerekir.

    Multi-Factor Authentication tek bir uygulama modunda kilitlenmiş tek bir cihazda desteklenmez. Bu sınırlama, cihazın ikinci kimlik doğrulama faktörünü tamamlaması için farklı bir uygulamaya geçiş yaptığından oluşur. Bu nedenle, tek bir App Mode cihazında çok faktörlü kimlik doğrulaması istiyorsanız ikinci faktör farklı bir cihazda olmalıdır.

    Bu özellik yalnızca iOS 11.3.1 ve üzeri sürümlerde desteklenir.

   ![Tek uygulama modunun ekran görüntüsü.](./media/device-enrollment-program-enroll-ios/single-app-mode.png)

9. Bu profili kullanan cihazların denetimli olmasını istiyorsanız, **denetimli**için **Evet** ' i seçin.

    ![Cihaz yönetimi ayarları ekran görüntüsü.](./media/device-enrollment-program-enroll-ios/supervisedmode.png)

    **Denetimli** cihazlar, varsayılan olarak etkinleştirme kilidi daha fazla yönetim seçeneği sağlar ve devre dışı bırakılır. Microsoft, özellikle çok sayıda iOS cihaz dağıtıyorsanız, denetimli modu etkinleştirme mekanizması olarak DEP kullanılmasını önerir.

    Kullanıcılara cihazlarıyla ilgili olarak iki şekilde denetim yapılır.

   - Kilit ekranı şöyle diyor: "Bu iPhone, contoso tarafından yönetiliyor."
   - @No__t-1**genel**@no__t **-3 ekrandaki** **Ayarlar**: "Bu iPhone denetimli. Contoso, Internet trafiğinizi izleyebilir ve bu cihazı bulabilir. "

     > [!NOTE]
     > Denetim olmadan kaydedilen bir cihaz, yalnızca Apple Configurator kullanılarak denetimli olarak sıfırlanabilir. Bu şekilde cihazın sıfırlanması, bir iOS cihazının USB kablosuyla bir Mac 'e bağlanmasını gerektirir. [Apple Configurator belgeleri](http://help.apple.com/configurator/mac/2.3)hakkında daha fazla bilgi edinin.

10. Bu profili kullanan cihazlar için kilitli kayıt istiyorsanız seçin. **Kilitli kayıt** , yönetim profilinin **Ayarlar** menüsünden kaldırılmasına izin veren iOS ayarlarını devre dışı bırakır. Cihaz kaydından sonra, cihazı silmeden bu ayarı değiştiremezsiniz. Bu tür cihazlarda **denetimli** yönetim modu *Evet*olarak ayarlanmalıdır. 

11. Bu profili kullanan cihazların **bilgisayarlarla eşitlenebilmesini**istiyorsanız seçin. **Sertifikaya göre Apple Configurator 'A Izin ver**' i seçerseniz, **Apple Configurator sertifikaları**' nın altında bir sertifika seçmeniz gerekir.

12. Önceki adımda **sertifikaya göre Apple Configurator 'A Izin ver** ' i seçerseniz, içeri aktarılacak bir Apple Configurator sertifikası seçin.

13. Her bir arka arkaya iade edildiğinde otomatik olarak uygulanan cihazlar için bir adlandırma biçimi belirtebilirsiniz. Adlandırma şablonu oluşturmak için, **Cihaz adı şablonu Uygula**altında **Evet** ' i seçin. Ardından, **Cihaz adı şablonu** kutusuna bu profili kullanarak adlar için kullanılacak şablonu girin. Cihaz türü ve seri numarasını içeren bir şablon biçimi belirtebilirsiniz. 

14. **İleri ' yi seçin: Kurulum Yardımcısı özelleştirmesi**.

15. **Kurulum Yardımcısı özelleştirmesi** sayfasında, aşağıdaki profil ayarlarını yapılandırın: ![Kurulum Yardımcısı özelleştirmesi. ](./media/device-enrollment-program-enroll-ios/setupassistantcustom.png)


    | Bölüm ayarları | Açıklama |
    |---|---|
    | <strong>Bölüm adı</strong> | Kullanıcılar etkinleştirme sırasında <strong>yapılandırma hakkında</strong> dokunduğunda görüntülenir. |
    |    <strong>Bölüm telefonu</strong>     | Kullanıcı etkinleştirme sırasında <strong>Yardım gerekli</strong> düğmesine tıkladığında görüntülenir. |

    Kullanıcı Kurulumu sırasında cihazdaki Kurulum Yardımcısı ekranlarını gizlemeyi seçebilirsiniz.
    - **Gizle**' yi seçerseniz, ekran kurulum sırasında gösterilmez. Cihaz kurulduktan sonra, özelliği ayarlamak için Kullanıcı **Ayarlar** menüsüne devam edebilir.
    - **Göster**' i seçerseniz, ekran kurulum sırasında görüntülenir. Kullanıcı bazen işlem yapmadan ekranı atlayabilir. Ancak daha sonra, özelliği ayarlamak için cihazın **Ayarlar** menüsüne gidebilirsiniz. 


    | Kurulum Yardımcısı ekran ayarları | **Göster**' i seçerseniz, kurulum sırasında cihaz olur... |
    |------------------------------------------|------------------------------------------|
    | <strong>Geçiş</strong> | Kullanıcıdan bir geçiş kodu iste. Erişim başka bir şekilde denetlenmiyorsa (cihazı bir uygulamayla sınırlandıran bilgi noktası modu gibi), güvenli olmayan cihazlar için her zaman bir geçiş kodu gerektir. |
    | <strong>Konum Hizmetleri</strong> | Kullanıcıdan konumunu iste. |
    | <strong>Yükleyebilmek</strong> | Uygulamalar & veri ekranını görüntüleyin. Bu ekran, kullanıcıya cihazı ayarlarken iCloud yedeğinden veri yükleme veya verileri aktarma seçeneği sunar. |
    | <strong>iCloud ve Apple KIMLIĞI</strong> | Kullanıcıya Apple KIMLIĞI ile oturum açma ve iCloud kullanma seçeneklerini sunun.                         |
    | <strong>Hüküm ve koşullar</strong> | Kullanıcının Apple 'ın hüküm ve koşullarını kabul etmesini gerektir. |
    | <strong>Touch ID</strong> | Kullanıcıya cihaz için parmak izi tanımayı ayarlama seçeneğini sunun. |
    | <strong>Apple Pay</strong> | Kullanıcıya cihazda Apple Pay ayarlama seçeneği sunun. |
    | <strong>Yakınlaştırma</strong> | Kullanıcıyı, cihazı ayarlarken görüntüyü yakınlaştırma seçeneğine sunun. |
    | <strong>Siri</strong> | Kullanıcıya Siri ayarlama seçeneğini sunun. |
    | <strong>Tanılama verileri</strong> | Tanılama ekranını kullanıcıya görüntüleyin. Bu ekran kullanıcıya Apple 'a Tanılama verileri gönderme seçeneği sunar. |
    | <strong>Ekran tonu</strong> | Kullanıcıya ekran tonunu açma seçeneğini sunun. |
    | <strong>Gizliliğinin</strong> | Kullanıcıya gizlilik ekranını görüntüleyin. |
    | <strong>Android geçişi</strong> | Kullanıcıya bir Android aygıtından Tarih geçirme seçeneği sunun. |
    | <strong>IMessage ve çok yönlü saat</strong> | Kullanıcıya IMessage ve çok yönlü saat ayarlama seçeneği sunun. |
    | <strong>Ekleme</strong> | Kapak sayfası ve çoklu görev ve Denetim Merkezi gibi kullanıcı eğitimi için ekleme bilgilendirme ekranlarını görüntüleyin. |
    | <strong>Geçişi izle</strong> | Kullanıcıya bir izleme cihazından veri geçirme seçeneği verin. |
    | <strong>Ekran zamanı</strong> | Ekran zaman ekranını görüntüleyin. |
    | <strong>Yazılım güncelleştirmesi</strong> | Zorunlu yazılım güncelleştirme ekranını görüntüleyin. |
    | <strong>SIM kurulumu</strong> | Kullanıcıya bir hücresel plan ekleme seçeneği sunun. |
    | <strong>Görünümünde</strong> | Kullanıcının Görünüm ekranını görüntüleyin. |
    | <strong>Hızlı dil</strong>| Kullanıcı için hızlı dil ekranını görüntüleyin. |
    | <strong>Tercih edilen dil</strong> | Kullanıcıya **tercih edilen dilini**seçme seçeneğini sunun. |
    | <strong>Cihazdan cihaza geçişe</strong> | Kullanıcıya verileri eski cihazlarından bu cihaza geçirme seçeneğini sunun.|
    

16. **İleri ' yi** seçerek **gözden geçir + oluştur** sayfasına gidin.

17. Profili kaydetmek için **Oluştur**' u seçin.

## <a name="sync-managed-devices"></a>Yönetilen cihazları eşitleme
Intune 'un cihazlarınızı yönetme izni olduğuna göre, Intune 'da Azure portal yönetilen cihazlarınızı görmek için Intune 'u Apple ile eşitlenebilir.

1. Azure portal Intune 'da, **cihaz kaydı** > **Apple kayıt** > **kayıt programı belirteçleri** ' ni seçin > > **cihazlarda** bir belirteç seçin > **eşitleme**. Kayıt programı cihazları düğümünün ve eşitleme bağlantısının ![Ekran görüntüsü. ](./media/device-enrollment-program-enroll-ios/image06.png)

   Intune 'un kabul edilebilir kayıt programı trafiğine yönelik koşullarını izlemek için aşağıdaki kısıtlamaları uygular:
   - Tam eşitleme her yedi günde bir birden çok kez çalıştırılabilir. Tam eşitleme sırasında Intune, Intune 'a bağlı olan Apple MDM sunucusuna atanan seri numaralarının tam güncelleştirilmiş listesini getirir. DEP cihazı Intune portalından silinirse, DEP portalındaki Apple MDM sunucusundan atanmamış olması gerekir. Atanmamış değilse, tam eşitleme çalıştırılıncaya kadar Intune 'a yeniden içeri aktarılmaz.   
   - Her 24 saatte bir eşitleme otomatik olarak çalıştırılır. **Eşitleme** düğmesine tıklayarak da eşitleme yapabilirsiniz (15 dakikada bir daha fazla). Tüm eşitleme isteklerinin tamamlanabilmesi için 15 dakika verilir. Eşitleme tamamlanana kadar **Eşitle** düğmesi devre dışı bırakılır. Bu eşitleme, mevcut cihaz durumunu yeniler ve Apple MDM sunucusuna atanan yeni cihazları içeri aktarır.   


## <a name="assign-an-enrollment-profile-to-devices"></a>Cihazlara kayıt profili atama
Kaydolmadan önce cihazlara bir kayıt programı profili atamanız gerekir.

>[!NOTE]
>Ayrıca, **Apple seri numaraları** dikey penceresinden profillere seri numaraları atayabilirsiniz.

1. Azure portal Intune ' da, **cihaz kaydı** > **Apple kayıt** > **kayıt programı belirteçleri** ' ni seçin > listeden bir belirteç seçin.
2. **Cihaz** Seç > listeden cihazları seçin > **profil ata**' yı seçin.
3. **Profil ata**altında, > **Atanacak**cihazlar için bir profil seçin.

### <a name="assign-a-default-profile"></a>Varsayılan profil atama

Belirli bir belirteçle kaydolan tüm cihazlara uygulanacak bir varsayılan profil seçebilirsiniz.

1. Azure portal Intune ' da, **cihaz kaydı** > **Apple kayıt** > **kayıt programı belirteçleri** ' ni seçin > listeden bir belirteç seçin.
2. **Varsayılan profili ayarla**' yı seçin, açılan listeden bir profil seçin ve ardından **Kaydet**' i seçin. Bu profil, belirtece kaydolmasını sağlayan tüm cihazlara uygulanır.

## <a name="distribute-devices"></a>Cihazları dağıtma
Apple ve Intune arasında yönetimi ve eşitlemeyi etkinleştirdiniz ve DEP cihazlarınızın kaydolmasına izin vermek için bir profil atadınız. Artık cihazları kullanıcılara dağıtabilirsiniz. Kullanıcı benzeşimi olan cihazlar her kullanıcıya bir Intune lisansı atanmasını gerektirir. Kullanıcı benzeşimi olmayan cihazlar bir cihaz lisansı gerektirir. Etkinleştirilen bir cihaz, cihaz temizlenmeden önce kayıt profilini uygulayamaz.

Bkz. [aygıt kayıt programı iOS cihazınızı Intune 'A kaydetme](/intune-user-help/enroll-your-device-dep-ios).

## <a name="renew-a-dep-token"></a>DEP belirtecini yenileme  
1. Deploy.apple.com adresine gidin.  
2. **Sunucuları Yönet**altında, yenilemek istediğiniz belirteç DOSYASıYLA ilişkili MDM sunucunuzu seçin.
3. **Yeni belirteç oluştur**' u seçin.

    ![Yeni belirteç oluştur ekran görüntüsü.](./media/device-enrollment-program-enroll-ios/generatenewtoken.png)

4. **Sunucu belirtecinizi**seçin.  
5. [Azure Portal Intune](https://aka.ms/intuneportal)'Da, **cihaz kaydı** > **Apple kayıt** > **kayıt programı belirteçleri** ' ni seçin > belirteci seçin.
    ![ kayıt programı belirteçlerinin ekran görüntüsü. ](./media/device-enrollment-program-enroll-ios/enrollmentprogramtokens.png)

6. **Belirteci Yenile** ' yi seçin ve özgün belirteci oluşturmak Için kullanılan Apple kimliğini girin.  
    @no__t-yeni belirteç oluştur ' un 0 ekran görüntüsü. ](./media/device-enrollment-program-enroll-ios/renewtoken.png)

8. Yeni indirilen belirteci karşıya yükleyin.  
9. **Belirteci Yenile**' yi seçin. Belirtecin yenilenme onayını görürsünüz.   
    ![ onay ekran görüntüsü. ](./media/device-enrollment-program-enroll-ios/confirmation.png)
