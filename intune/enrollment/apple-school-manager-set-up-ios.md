---
title: iOS cihazları için Apple School Manager Programı kaydı
titleSuffix: Microsoft Intune
description: Intune ile şirkete ait iOS cihazları için Apple School Manager Programı kaydını ayarlamayı öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 12/06/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 4c35a23e-0c61-11e8-ba89-0ed5f89f718b
ms.reviewer: tisilver
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 20ec38e5db8f65b90083b3aececd8b059b8ea45e
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71730013"
---
# <a name="set-up-ios-device-enrollment-with-apple-school-manager"></a>Apple School Manager ile iOS cihaz kaydını ayarlama

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Artık [Apple School Manager](https://school.apple.com/) programı aracılığıyla satın alınan iOS cihazlarını Intune ile yönetebilirsiniz. Intune’u Apple School Manager ile birlikte kullanarak, çok sayıda iOS cihazını hiç dokunmadan kaydedebilirsiniz. Bir öğrenci veya öğretmen cihazı açtığında, önceden yapılandırılmış ayarları ile Kurulum Yardımcısı çalıştırılır ve cihaz yönetime kaydedilir.

Apple School Manager kaydını etkinleştirmek için Intune ve Apple School Manager portallarını kullanmanız gerekir. Cihazlarınızı, Intune ile yönetilmek üzere atayabilmeniz için seri numaraları listesi veya sipariş numarası gereklidir. Kayıt sırasında cihazlara uygulanan ayarları içeren DEP kayıt profilleri oluşturun.

Apple School Manager kaydı [Apple Aygıt Kayıt Programı](device-enrollment-program-enroll-ios.md) veya [cihaz kaydı yöneticisi](device-enrollment-manager-enroll.md) ile birlikte kullanılamaz.

**Önkoşullar**
- [Apple Mobil Cihaz Yönetimi (MDM) anında iletme sertifikası](apple-mdm-push-certificate-get.md)
- [MDM Yetkilisi](../fundamentals/mdm-authority-set.md)
- [Apple MDM Anında İletme sertifikası](apple-mdm-push-certificate-get.md)
- ADFS kullanılıyorsa kullanıcı benzeşimi [WS-Trust 1.3 Kullanıcı adı/Karma uç noktası](https://technet.microsoft.com/library/adfs2-help-endpoints) gerektirir. [Daha fazla bilgi edinin](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).
- [Apple School Management](http://school.apple.com) programından satın alınan cihazlar

## <a name="get-an-apple-token-and-assign-devices"></a>Bir Apple belirteci alma ve cihaz atama

Şirkete ait iOS cihazlarını Apple School Manager’a kaydedebilmek için Apple’dan bir belirteç (.p7m) dosyasına ihtiyacınız vardır. Bu belirteç, Intune’un Apple School Manager’a katılan cihazlara ait bilgileri eşitlemesini sağlar. Ayrıca Intune'un kayıt profilini Apple'a yüklemesine ve cihazları bu profillere atamasına izin verir. Apple portalındayken yönetilecek cihaz seri numaralarını da atayabilirsiniz.

### <a name="step-1-download-the-intune-public-key-certificate-required-to-create-an-apple-token"></a>1\. Adım Apple belirteci oluşturmak için gereken Intune ortak anahtar sertifikasını indirin

1. [Intune](https://aka.ms/intuneportal)’da, **Cihaz kaydı** > **Apple kaydı** > **Kayıt programı belirteçleri** > **Ekle**’yi seçin.

   ![Bir kayıt programı belirteci alın.](./media/apple-school-manager-set-up-ios/image01.png)

2. **Kayıt programı belirteci** dikey penceresinde, şifreleme dosyasını (.pem) indirmek ve yerel olarak kaydetmek için **Ortak anahtarınızı indirin**’i seçin. .pem dosyası Apple School Manager portalından güven ilişkisi sertifikası istemek için kullanılır.
     ![Kayıt Programı Belirteci dikey penceresi.](./media/apple-school-manager-set-up-ios/image02.png)

### <a name="step-2-download-a-token-and-assign-devices"></a>2\. Adım Bir belirteç indirin ve cihaz atayın
1. **Apple School Manager aracılığıyla belirteç oluşturma**’yı seçin ve şirketinizin Apple kimliğiyle Apple School’da oturum açın. Apple School Manager belirtecinizi yenilemek için bu Apple kimliğini kullanabilirsiniz.
2. [Apple School Manager portalında](https://school.apple.com), **MDM Sunucuları**’na gidin ve **MDM Sunucusu Ekle**’yi (sağ üstte) seçin.
3. **MDM Sunucusu Adını** girin. Sunucu adı, mobil cihaz yönetimi (MDM) sunucusunu tanımlarken kullanmanız içindir. Microsoft Intune sunucusunun adı veya URL'si değildir.
   ![Seri Numarası seçeneği işaretliyken Apple School Manager portalının ekran görüntüsü](./media/apple-school-manager-set-up-ios/asm-server-assignment.png)

4. Apple portalında **Dosyayı Karşıya Yükle...** ’yi seçin ve .pem dosyasına giderek **MDM Sunucusunu Kaydet**’i (sağ alt köşede) seçin.
5. **Belirteci Al**’ı seçin ve ardından sunucu belirtecini (.p7m) bilgisayarınıza indirin.
6. **Cihaz Atamaları**’na gidin ve **Cihaz Seç** işlemini **Seri Numaraları**, **Sipariş Numarası**’nı elle girerek veya **CSV Dosyasını Karşıya Yükle** ile yapın.
     ![Seri Numarası seçeneği işaretliyken Apple School Manager portalının ekran görüntüsü](./media/apple-school-manager-set-up-ios/asm-device-assignment.png)
7. **Sunucuya Ata** eylemini seçip oluşturduğunuz **MDM Sunucusunu** seçin.
8. **Cihaz Seçme** işleminin nasıl olacağını belirtin ve daha sonra cihaza ait bilgileri ve ayrıntıları sağlayın.
9. **Sunucuya Ata**'yı ve Microsoft Intune için belirtilen &lt;ServerName&gt; öğesini belirleyip **Tamam**'ı seçin.

### <a name="step-3-save-the-apple-id-used-to-create-this-token"></a>Adım 3. Bu belirteci oluşturmak için kullanılan Apple kimliğini kaydedin

Azure portalında Intune’da ileride başvurmak üzere Apple kimliğini sağlayın.

![Kayıt programı belirtecini oluşturmak için kullanılan Apple kimliğini belirtme ve kayıt programı belirtecine gözatma işleminin ekran görüntüsü.](./media/apple-school-manager-set-up-ios/image03.png)

### <a name="step-4-upload-your-token"></a>Adım 4. Belirtecinizi karşıya yükleme
**Apple belirteci** kutusunda sertifika (.pem) dosyasına gözatın, **Aç**’ı ve daha sonra **Oluştur**’u seçin. Anında iletme sertifikasıyla, Intune ilkeyi kayıtlı mobil cihazlara ileterek iOS cihazları kaydedebilir ve yönetebilir. Intune, Apple School Manager cihazlarınızı Apple’dan otomatik olarak eşitler.

## <a name="create-an-apple-enrollment-profile"></a>Apple kayıt profili oluşturma
Belirtecinizi yüklediğinize göre, Apple School cihazları için kayıt profili oluşturabilirsiniz. Bir cihaz kayıt profili, kayıt sırasında bir grup cihaza uygulanan ayarları tanımlar.

1. [Intune](https://aka.ms/intuneportal)’da, **Cihaz kaydı** > **Apple kaydı** > **Kayıt programı belirteçleri**’ni seçin.
2. Bir belirteç seçin, **Profiller**’e ve daha sonra **Profil oluştur**’a tıklayın.

3. **Profil Oluştur**’un altında, yönetim amaçları doğrultusunda profil için bir **Ad** ve **Açıklama** girin. Kullanıcılar bu ayrıntıları göremez. Azure Active Directory’de dinamik bir grup oluşturmak için **Ad** alanını kullanabilirsiniz. enrollmentProfileName parametresini, bu kayıt profiliyle cihazlara atamak amacıyla tanımlamak için profil adını kullanın. [Azure Active Directory dinamik grupları](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal#rules-for-devices) hakkında daha fazla bilgi edinin.

    ![Profil adı ve açıklaması.](./media/apple-school-manager-set-up-ios/image05.png)

4. **Kullanıcı Benzeşimi** için bu profile sahip cihazların atanan kullanıcıyla mı yoksa atanan kullanıcı olmadan mı kaydedilmesi gerektiğini seçin.
    - **Kullanıcı Benzeşimi ile Kaydetme** - Uygulamaları yükleme gibi hizmetler için Şirket Portalı’nı kullanmak isteyen kullanıcılara ait cihazlar için bu seçeneği seçin. Bu seçenek ayrıca kullanıcılara, Şirket Portalı’nı kullanarak cihazlarının kimliğini doğrulama imkanı sağlar. ADFS kullanılıyorsa kullanıcı benzeşimi [WS-Trust 1.3 Kullanıcı adı/Karma uç noktası](https://technet.microsoft.com/library/adfs2-help-endpoints) gerektirir. [Daha fazla bilgi edinin](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).   Apple School Manager’ın Paylaşılan iPad modu, kullanıcının kullanıcı benzeşimi olmadan kaydolmasını gerektirir.

    - **Kullanıcı Benzeşimi Olmadan Kaydetme** - Paylaşılan cihazlar gibi tek bir kullanıcıyla bağlantılı olmayan cihazlar için bu seçeneği seçin. Yerel kullanıcı verilerine erişmeden görevleri yerine getiren cihazlar için bu seçeneği kullanın. Şirket Portalı uygulaması gibi uygulamalar çalışmaz.

5. **Kullanıcı Benzeşimi ile Kaydet**’i seçerseniz, kullanıcıların Şirket Portalı yerine Apple Kurulum Yardımcısı ile kimlik doğrulama gerçekleştirmelerini sağlayabilirsiniz.

    ![Şirket Portalı ile kimlik doğrulayın.](./media/apple-school-manager-set-up-ios/authenticatewithcompanyportal.png)

    > [!NOTE]
    > Aşağıdakilerden herhangi birini yapmak istiyorsanız, **Apple Kurulum Yardımcısı yerine Şirket Portalı ile kimliği doğrula** ayarını **Evet** değerine ayarlayın.
    >    - çok faktörlü kimlik doğrulaması kullanma
    >    - ilk kez oturum açarken parolalarını değiştirmesi gereken kullanıcılara bunu bildirme
    >    - kayıt sırasında kullanıcılardan süresi dolmuş parolalarını sıfırlamalarını isteme
    >
    > Apple Kurulum Yardımcısı ile kimliği doğrularken bunlar desteklenmez.

6. **Cihaz Yönetim Ayarları**’nı ve bu profili kullanan cihazların denetlenmesini isteyip istemediğinizi seçin.
    **Denetimli** cihazlar, varsayılan olarak size daha fazla yönetim seçeneği verir ve Etkinleştirme Kilidi’ni devre dışı bırakır. Microsoft, özellikle fazla sayıda iOS cihaz dağıtan kuruluşlar için denetimli modu etkinleştirme mekanizması olarak DEP’in kullanılmasını önerir.

    Kullanıcılara cihazlarının denetimli olduğu iki yolla bildirilir:

   - Kilit ekranında “Bu iPhone, Contoso tarafından yönetilmektedir.” yazar.
   - **Ayarlar** > **Genel** > **Hakkında** kısmında “Bu iPhone denetimlidir.” yazar. ifadesi ve

     > [!NOTE]
     > Denetim olmadan kaydedilen bir cihaz, yalnızca Apple Configurator kullanılarak sıfırlanıp denetimli yapılabilir. Cihazı bu şekilde sıfırlamak için bir iOS cihazı USB kablosu ile bir Mac’e bağlamak gerekir. Bu konu hakkında daha fazla bilgi için [Apple Configurator belgelerine](http://help.apple.com/configurator/mac/2.3) bakın.

7. Bu profili kullanan cihazlarda kilitli kayıt isteyip istemediğinizi seçin. **Kilitli kayıt**, yönetim profilinin **Ayarlar** menüsünden kaldırılmasını sağlayan iOS ayarlarını devre dışı bırakır. Cihazı kaydettikten sonra cihazı silmeden bu ayarı değiştiremezsiniz. Bu cihazlarda **Denetimli** Yönetim Modu *Evet* olarak ayarlı olmalıdır. 

8. Birden çok kullanıcının yönetilen Apple kimliği kullanarak kayıtlı iPad’lerde oturum açmasına izin verebilirsiniz. Bunu yapmak için, **paylaşılan iPad** altında **Evet** ' i seçin (Bu seçenek, **Kullanıcı benzeşimi olmadan kaydolma** ve **denetimli** mod **Evet**olarak ayarlanmış olması gerekir.) Yönetilen Apple kimlikleri, Apple Okul Yöneticisi portalında oluşturulur. [Paylaşılan iPad](../fundamentals/education-settings-configure-ios-shared.md) ve [Apple'ın paylaşılan iPad gereksinimleri](https://help.apple.com/classroom/ipad/2.0/#/cad7e2e0cf56) hakkında daha fazla bilgi edinin.

9. Bu profili kullanan cihazların **Bilgisayarlarla eşitleme** imkanının olup olmayacağını seçin. **Sertifikaya göre Apple Configurator’a izin ver**’i seçerseniz, **Apple Configurator Sertifikaları**’nın altında bir sertifika seçmeniz gerekir.

10. Önceki adımda **Sertifikaya göre Apple Configurator’a izin ver**’i seçtiyseniz içeri aktaracak bir Apple Configurator Sertifikası seçin.

11. Kaydolan cihazlara otomatik olarak uygulanacak bir adlandırma biçimi belirleyebilirsiniz. Bunu yapmak için **Cihaz adı şablonu uygula** bölümünde **Evet**'i seçin. Ardından **Cihaz Adı Şablonu**'na bu profili kullanan cihazlar için kullanılacak şablonu girin. Cihaz türünü ve seri numarasını içeren bir şablon biçimi belirtebilirsiniz.

12. **Tamam**’ı seçin.

13. Şu profil ayarlarını yapılandırmak için **Kurulum Yardımcısı Ayarları**’nı seçin: ![Kurulum Yardımcısı Özelleştirme.](./media/apple-school-manager-set-up-ios/setupassistantcustom.png)


    |                 Ayar                  |                                                                                               Description                                                                                               |
    |------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    |     <strong>Departman Adı</strong>     |                                                             Kullanıcı, etkinleştirme sırasında <strong>Yapılandırma Hakkında</strong> öğesine dokunduğunda görüntülenir.                                                              |
    |    <strong>Departman Telefonu</strong>     |                                                          Kullanıcı, etkinleştirme sırasında <strong>Yardım Gerekli</strong> düğmesine dokunduğunda görüntülenir.                                                          |
    | <strong>Kurulum Yardımcısı Seçenekleri</strong> |                                                     Aşağıdaki isteğe bağlı ayarlar, daha sonra iOS <strong>Ayarlar</strong> menüsünden ayarlanabilir.                                                      |
    |        <strong>Geçiş kodu</strong>         | Etkinleştirme sırasında geçiş kodu ister. Güvenliği sağlanmayan veya erişim denetimi başka bir yolla (cihazı tek uygulamayla sınırlandıran bilgi noktası modu gibi) sağlanan cihazlar için her zaman geçiş kodu isteyin. |
    |    <strong>Konum Hizmetleri</strong>    |                                                                 Bu etkinleştirilirse Kurulum Yardımcısı, etkinleştirme sırasında bu hizmeti sorar.                                                                  |
    |         <strong>Geri Yükle</strong>         |                                                                Bu etkinleştirilirse Kurulum Yardımcısı, etkinleştirme sırasında iCloud yedeklemesini sorar.                                                                 |
    |   <strong>iCloud ve Apple Kimliği</strong>   |                         Bu etkinleştirilirse Kurulum Yardımcısı, kullanıcıdan bir Apple Kimliği ile oturum açmasını ister ve Uygulamalar ve Veriler ekranında cihazın iCloud yedeğinden geri yüklenmesine izin verilir.                         |
    |  <strong>Hüküm ve Koşullar</strong>   |                                                   Bu etkinleştirilirse Kurulum Yardımcısı, etkinleştirme sırasında kullanıcılardan Apple’ın hüküm ve koşullarını kabul etmelerini ister.                                                   |
    |        <strong>Touch ID</strong>         |                                                                 Bu etkinleştirilirse Kurulum Yardımcısı, etkinleştirme sırasında bu hizmeti sorar.                                                                 |
    |        <strong>Apple Pay</strong>        |                                                                 Bu etkinleştirilirse Kurulum Yardımcısı, etkinleştirme sırasında bu hizmeti sorar.                                                                 |
    |          <strong>Yakınlaştır</strong>           |                                                                 Bu etkinleştirilirse Kurulum Yardımcısı, etkinleştirme sırasında bu hizmeti sorar.                                                                 |
    |          <strong>Siri</strong>           |                                                                 Bu etkinleştirilirse Kurulum Yardımcısı, etkinleştirme sırasında bu hizmeti sorar.                                                                 |
    |     <strong>Tanılama Verileri</strong>     |                                                                 Bu etkinleştirilirse Kurulum Yardımcısı, etkinleştirme sırasında bu hizmeti sorar.                                                                 |


14. **Tamam**’ı seçin.

15. Profili kaydetmek için **Oluştur**’u seçin.

## <a name="connect-school-data-sync"></a>Okul Veri Eşitlemeye bağlanma
(İsteğe bağlı) Apple School Manager, sınıf ad listesi verilerini Microsoft School Data Sync (SDS) kullanarak Azure Active Directory’ye (AD) eşitlemeyi destekler. Yalnızca bir belirteci SDS ile eşitleyebilirsiniz. School Data Sync ile başka bir belirteç ayarladıysanız, SDS daha önceki belirteçten kaldırılır. Geçerli belirtecin yerini yeni bir bağlantı alır. Okul verilerini eşitlemek üzere SDS kullanmak için aşağıdaki adımları tamamlayın.

1. [Intune](https://aka.ms/intuneportal)’da, **Cihaz kaydı** > **Apple kaydı** > **Kayıt programı belirteçleri**’ni seçin.
2. Bir Apple School Manager belirtecini ve daha sonra **School Data Sync**’i seçin.
3. **School Data Sync** altında **İzin Ver**’i seçin. Bu ayar, Intune’un Office 365'teki SDS’ye bağlanmasını sağlar.
4. Apple Okul Yöneticisi ile Azure AD arasında bir bağlantıyı etkinleştirmek için **Microsoft okul veri eşitlemesini ayarla**' yı seçin. [Okul veri eşitlemesini ayarlama](https://support.office.com/article/Install-the-School-Data-Sync-Toolkit-8e27426c-8c46-416e-b0df-c29b5f3f62e1)hakkında daha fazla bilgi edinin.
5. **Kaydet** > **Tamam**’a tıklayın.

## <a name="sync-managed-devices"></a>Yönetilen cihazları eşitleme

Intune’a Apple School Manager cihazlarınızı yönetme izni verildikten sonra, yönetilen cihazlarınızı Intune’da görmek için Intune’u Apple hizmetiyle eşitleyin.

[Intune](https://aka.ms/intuneportal)'da **cihaz kaydı** > **Apple kayıt** > **kayıt programı belirteçleri** ' ni seçin > listedeki bir belirteci seçin > **cihazlarda** > **eşitleme**. Kayıt programı cihazları düğümünün ve eşitleme bağlantısının ![Ekran görüntüsü. 0

Intune, Apple’ın kabul edilebilir kayıt programı trafiği şartlarına uygun hareket etmek için aşağıdaki kısıtlamaları getirir:
- Tam eşitleme en sık yedi günde bir çalıştırılabilir. Tam eşitleme sırasında Intune, kendine atanmış tüm Apple seri numaralarını yeniler. Önceki tam eşitlemenin üzerinden yedi gün geçmeden bir tam eşitleme girişiminde bulunulursa, Intune yalnızca henüz Intune’da listelenmeyen seri numaralarını yeniler.
- Herhangi bir eşitleme isteğinin tamamlanması için 15 dakika verilir. Bu süre boyunca veya istek başarılı olana kadar **Eşitle** düğmesi devre dışı bırakılır.
- Intune, yeni ve kaldırılmış cihazları 24 saatte bir Apple ile eşitler.

>[!NOTE]
>Apple School Manager seri numaralarını **Kayıt Programı Cihazları** dikey penceresinden de profillere atayabilirsiniz.

## <a name="assign-a-profile-to-devices"></a>Cihazlara profil atama
Intune tarafından yönetilen Apple School Manager cihazları kaydedilmeden önce bu cihazlara bir kayıt profili atanmalıdır.

1. [Intune](https://aka.ms/intuneportal)’da, **Cihaz kaydı** > **Apple Kaydı** > **Kayıt programı belirteçleri** > listeden bir belirteç seçin.
2. **Cihazlar** > listeden cihazları seçin > **Profil ata**’yı seçin.
3. **Profil ata** altında cihazlar için bir profil seçin ve daha sonra **Ata**’ya tıklayın.

## <a name="distribute-devices-to-users"></a>Cihazları kullanıcılara dağıtma

Apple ve Intune arasında eşitlemeyi ve yönetimi etkinleştirdiniz ve Apple School  cihazlarınızın kaydolmasına izin vermek için bir profil atadınız. Artık cihazları kullanıcılara dağıtabilirsiniz. Bir iOS Apple School Manager cihazı açıldığında, Intune yönetimine kaydedilir. Kullanılmakta olan etkinleştirilmiş cihazlar silinmeden profiller uygulanamaz.
