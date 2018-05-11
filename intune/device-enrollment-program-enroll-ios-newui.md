---
title: iOS cihazlarını kaydetme - Cihaz Kayıt Programı
titleSuffix: Microsoft Intune
description: Şirkete ait iOS cihazlarını Aygıt Kayıt Programı (yeni kullanıcı arabirimi) kullanarak kaydetmeyi öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/08/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 7ddbf360-0c61-11e8-ba89-0ed5f89f718b
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a2b70bdd4e1d861feaed71e28e93c293a6367e26
ms.sourcegitcommit: 4c06fa8e9932575e546ef2e880d96e96a0618673
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="automatically-enroll-ios-devices-with-apples-device-enrollment-program"></a>iOS cihazlarını Apple’ın Aygıt Kayıt Programı ile otomatik olarak kaydetme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

> [!NOTE]
> ### <a name="temporary-user-interface-differences"></a>Geçici kullanıcı arabirimi farklılıkları
> Bu sayfada açıklanan özellikler için kullanıcı arabirimleri, güncelleştirilme sürecindedir. Bu güncelleştirmeler, mart ayının ilk haftasında tüm kullanıcı hesaplarına sunulacaktır.
>
> **Cihaz kaydı** sayfanız aşağıdaki görüntüdeki gibi görünüyorsa güncelleştirilmiş kullanıcı arabirimini kullanıyorsunuzdur ve bu yardım sayfasını kullanabilirsiniz.
>
> ![Yeni kullanıcı arabirimi](./media/appleenroll-newui.png)
>
> Ancak **Cihaz kaydı** sayfanız aşağıdaki görüntüdeki gibi görünüyorsa hesabınız henüz yeni kullanıcı arabirimine güncelleştirilmemiştir. [Bu yardım sayfasına](device-enrollment-program-enroll-ios.md) gidin.
>
> ![Eski kullanıcı arabirimi](./media/appleenroll-oldui.png)

Bu konu, Apple’ın [Aygıt Kayıt Programı (DEP)](https://deploy.apple.com) yoluyla satın alınan cihazlar için iOS cihaz kaydını etkinleştirmenize yardımcı olur. DEP kaydını hiç dokunmadan birçok sayıda cihaz için etkinleştirebilirsiniz. iPhone ve iPad’ler gibi cihazları doğrudan kullanıcılara sevk edebilirsiniz. Kullanıcı cihazı açtığında, önceden yapılandırılmış ayarları ile Kurulum Yardımcısı çalıştırılır ve cihaz yönetime kaydedilir.

DEP kaydını etkinleştirmek için Intune ve Apple DEP portallarını birlikte kullanmanız gerekir. Cihazlarınızı, Intune ile yönetilmek üzere atayabilmeniz için seri numaraları listesi veya sipariş numarası gereklidir. Kayıt sırasında cihazlara uygulanan ayarları içeren DEP kayıt profilleri oluşturun.

Bu arada, DEP kaydının [cihaz kayıt yöneticisiyle](device-enrollment-manager-enroll.md) birlikte kullanılamayacağına dikkat edin.

## <a name="what-is-supervised-mode"></a>Denetimli mod nedir?
Apple, iOS 5 sürümünde denetimli modu kullanıma sundu. Denetimli moddaki herhangi bir iOS cihaz, daha fazla denetimle yönetilebilir. O neden bu mod, özellikle şirkete ait cihazlar için kullanışlıdır. Intune, Apple Aygıt Kayıt Programı’nın (DEP) bir parçası olarak denetimli mod için cihazların yapılandırılmasını destekler. 

<!--
**Steps to enable enrollment programs from Apple**
1. [Get an Apple DEP token and assign devices](#get-the-apple-dep-token)
2. [Create an enrollment profile](#create-an-apple-enrollment-profile)
3. [Synchronize DEP-managed devices](#sync-managed-device)
4. [Assign DEP profile to devices](#assign-an-enrollment-profile-to-devices)
5. [Distribute devices to users](#end-user-experience-with-managed-devices)
-->
## <a name="prerequisites"></a>Önkoşullar
- [Apple Aygıt Kayıt Programı](http://deploy.apple.com)’nda satın alınmış cihazlar
- [MDM Yetkilisi](mdm-authority-set.md)
- [Apple MDM Anında İletme sertifikası](apple-mdm-push-certificate-get.md)

## <a name="get-an-apple-dep-token"></a>Bir Apple DEP belirteci alma

iOS cihazlarını DEP ile kaydedebilmeniz için bir Apple DEP belirteci dosyasına (.p7m) ihtiyacınız vardır. Bu belirteç, Intune'un şirketinize ait olan DEP cihazları hakkındaki bilgileri eşitlemesini sağlar. Ayrıca Intune'un kayıt profilini Apple'a yüklemesine ve cihazları bu profillere atamasına izin verir.

DEP belirtecini oluşturmak için Apple DEP portalını kullanın. Cihazları yönetim için Intune’a atamak için DEP portalını da kullanabilirsiniz.

> [!NOTE]
> Belirteci Azure’a geçirmeden önce klasik Intune portalında silerseniz Intune, silinen bir Apple DEP belirtecini geri yükleyebilir. DEP belirtecini Azure portalından tekrar silebilirsiniz. DEP belirtecini Azure portalından tekrar silebilirsiniz.

### <a name="step-1-download-the-intune-public-key-certificate-required-to-create-the-token"></a>1. Adım Belirteci oluşturmak için gereken Intune ortak anahtar sertifikasını indirin.

1. [Azure portalında Intune](https://aka.ms/intuneportal)’da, **Cihaz kaydı** > **Apple kaydı** > **Kayıt Programı Belirteçleri** > **Ekle**’yi seçin.

    ![Bir kayıt programı belirteci alın.](./media/device-enrollment-program-enroll-ios/image01.png)

2. **Onaylıyorum**’u seçerek Microsoft’un Apple’a kullanıcı ve cihaz bilgilerini göndermesine izin verin.

   ![Apple Sertifikaları çalışma alanındaki Kayıt Programı Belirteci panelinde bulunan ortak anahtarı indirme öğesinin ekran görüntüsü.](./media/device-enrollment-program-enroll-ios-newui/add-enrollment-program-token-pane.png)

3. Şifreleme dosyasını (.pem) indirmek ve yerel olarak kaydetmek için **Ortak anahtarınızı indirin** öğesini seçin. .pem dosyası Apple Cihaz Kayıt Programı portalından güven ilişkisi sertifikası istemek için kullanılır.


### <a name="step-2-use-your-key-to-download-a-token-from-apple"></a>2. Adım Anahtarınızı kullanarak Apple’dan bir belirteç indirin.

1. Apple’ın Dağıtım Programı portalını açmak için **Apple’ın Aygıt Kayıt Programı için bir belirteç oluştur**’u seçin ve şirket Apple Kimliğinizle oturum açın. DEP belirtecinizi yenilemek için de bu Apple kimliğini kullanabilirsiniz.
2.  Apple’ın [Dağıtım Programları portalında](https://deploy.apple.com), **Aygıt Kayıt Programı** için **Kullanmaya Başla**’yı seçin.

3. **Sunucuları Yönet** sayfasında **MDM Sunucusu Ekle**’yi seçin.
4. **MDM Sunucu Adı**'nı girin ve ardından **İleri**'yi seçin. Sunucu adı, mobil cihaz yönetimi (MDM) sunucusunu tanımlarken kullanmanız içindir. Microsoft Intune sunucusunun adı veya URL'si değildir.

5. **Ekle &lt;ServerName&gt;** iletişim kutusu açılır ve **Ortak Anahtarınızı Yükleyin** ifadesi yazar. **Dosya Seç…** öğesini seçin .pem dosyasını karşıya yükleyin ve ardından **İleri**'yi seçin.

6. **Dağıtım Programları** &gt; **Cihaz Kayıt Programı** &gt; **Cihazları Yönet**'e gidin.
7. **Cihazları Şuna Göre Seç:** öğesinin altında cihazların nasıl tanımlanacağını belirtin:
    - **Seri Numarası**
    - **Sipariş Numarası**
    - **CSV Dosyası Yükle**.

   ![Cihazları seri numarasına göre seçme, eylem seç öğesini Sunucuya ata olarak seçme ve sunucu adını seçme ekran görüntüsü.](./media/enrollment-program-token-specify-serial.png)

8. **Eylem Seç** işlemi için **Sunucuya Ata**’yı ve Microsoft Intune için belirtilen &lt;ServerName&gt; öğesini belirleyip **Tamam**'ı seçin. Apple portalı, belirtilen cihazları Intune sunucusunda yönetilmek üzere bu sunucuya atar ve **Atama Tamamlandı** ifadesini görüntüler.

   Apple portalında **Dağıtım Programları** &gt; **Aygıt Kayıt Programı** &gt; **Atama Geçmişini Görüntüle**’ye giderek cihazların listesi ile MDM sunucu atamalarına göz atabilirsiniz.

### <a name="step-3-save-the-apple-id-used-to-create-this-token"></a>3. Adım. Bu belirteci oluşturmak için kullanılan Apple kimliğini kaydedin.

Azure portalında Intune’da ileride başvurmak üzere Apple kimliğini sağlayın.

![Kayıt programı belirtecini oluşturmak için kullanılan Apple kimliğini belirtme ve kayıt programı belirtecine gözatma işleminin ekran görüntüsü.](./media/device-enrollment-program-enroll-ios/image03.png)

### <a name="step-4-upload-your-token"></a>Adım 4. Belirtecinizi karşıya yükleyin.
**Apple belirteci** kutusunda sertifika (.pem) dosyasına gözatın, **Aç**’ı ve daha sonra **Oluştur**’u seçin. Anında iletme sertifikasıyla, Intune ilkeyi kayıtlı mobil cihazlara ileterek iOS cihazları kaydedebilir ve yönetebilir. Intune, kayıt programı hesabınızı görmek için Apple ile otomatik olarak eşitlenir.

## <a name="create-an-apple-enrollment-profile"></a>Apple kayıt profili oluşturma

Belirtecinizi yüklediğinize göre, DEP cihazları için kayıt profili oluşturabilirsiniz. Bir cihaz kayıt profili, kayıt sırasında bir grup cihaza uygulanan ayarları tanımlar.

1. Azure portalında Intune’da, **Cihaz kaydı** > **Apple kaydı** > **Kayıt programı belirteçleri**’ni seçin.
2. Bir belirteç seçin, **Profiller**’e ve daha sonra **Profil oluştur**’a tıklayın.
    ![Bir profil ekran görüntüsü oluşturun.](./media/device-enrollment-program-enroll-ios/image04.png)
3. **Profil Oluştur**’un altında, yönetim amaçları doğrultusunda profil için bir **Ad** ve **Açıklama** girin. Kullanıcılar bu ayrıntıları göremez. Azure Active Directory’de dinamik bir grup oluşturmak için **Ad** alanını kullanabilirsiniz. enrollmentProfileName parametresini, bu kayıt profiliyle cihazlara atamak amacıyla tanımlamak için profil adını kullanın. [Azure Active Directory dinamik grupları](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal#using-attributes-to-create-rules-for-device-objects) hakkında daha fazla bilgi edinin.
    ![Profil adı ve açıklaması.](./media/device-enrollment-program-enroll-ios/image05.png)

4. **Kullanıcı Benzeşimi** için bu profile sahip cihazların atanan kullanıcıyla mı yoksa atanan kullanıcı olmadan mı kaydedilmesi gerektiğini seçin.
    - **Kullanıcı Benzeşimi ile Kaydetme** - Uygulamaları yükleme gibi hizmetler için Şirket Portalı’nı kullanmak isteyen kullanıcılara ait cihazlar için bu seçeneği seçin. Bu seçenek ayrıca kullanıcılara, Şirket Portalı’nı kullanarak cihazlarının kimliğini doğrulama imkanı sağlar. Kullanıcı benzeşimi [WS-Trust 1.3 Kullanıcı adı/Karma uç noktası](https://technet.microsoft.com/library/adfs2-help-endpoints) gerektirir. [Daha fazla bilgi edinin](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

    - **Kullanıcı Benzeşimi Olmadan Kaydetme** - Tek bir kullanıcıyla bağlantılı olmayan cihazlar için bu seçeneği seçin. Yerel kullanıcı verilerine erişmeden görevleri yerine getiren cihazlar için bunu kullanın. Şirket Portalı uygulaması gibi uygulamalar çalışmaz.

5. **Kullanıcı Benzeşimi ile Kaydet**’i seçerseniz, kullanıcıların Şirket Portalı yerine Apple Kurulum Yardımcısı ile kimlik doğrulamalarına izin verme seçeneğiniz olur.

    ![Şirket Portalı ile kimlik doğrulayın.](./media/device-enrollment-program-enroll-ios/authenticatewithcompanyportal.png)

    > [!NOTE]
    > Profil özelliklerini **Kullanıcı Benzeşimi ile kaydet** olarak ayarladıysanız çok faktörlü kimlik doğrulaması (MFA), DEP kaydı sırasında çalışmaz. Kayıttan sonra MFA, cihazlarda beklendiği gibi çalışır. Cihazlar, ilk defa oturum açıldığında parolalarını değiştirmesi gereken kullanıcılara istemde bulunamaz. Ayrıca, parolalarının süresi dolmuş olan kullanıcılardan kayıt sırasında parolalarını sıfırlamaları istenmez. Kullanıcıların, parolayı sıfırlamak için farklı bir cihaz kullanmaları gerekir.

6. **Cihaz Yönetim Ayarları**’nı seçin ve bu profili kullanan cihazların denetlenmesini isteyip istemediğinizi seçin.
    **Denetimli** cihazlar, varsayılan olarak size daha fazla yönetim seçeneği verir ve Etkinleştirme Kilidi’ni devre dışı bırakır. Microsoft, özellikle fazla sayıda iOS cihaz dağıtan kuruluşlar için denetimli modu etkinleştirme mekanizması olarak DEP’in kullanılmasını önerir.

    Kullanıcılara cihazlarının denetimli olduğu iki yolla bildirilir:

   - Kilit ekranında “Bu iPhone, Contoso tarafından yönetilmektedir.” yazar.
   - **Ayarlar** > **Genel** > **Hakkında** kısmında “Bu iPhone denetimlidir.” yazar. ifadesi ve

     > [!NOTE]
     > Denetim olmadan kaydedilen bir cihaz, yalnızca Apple Configurator kullanılarak sıfırlanıp denetimli yapılabilir. Cihazı bu şekilde sıfırlamak için bir iOS cihazı USB kablosu ile bir Mac’e bağlamak gerekir. Bu konu hakkında daha fazla bilgi için [Apple Configurator belgelerine](http://help.apple.com/configurator/mac/2.3) bakın.

7. Bu profili kullanan cihazlarda kilitli kayıt isteyip istemediğinizi seçin. **Kilitli kayıt**, yönetim profilinin **Ayarlar** menüsünden kaldırılmasını sağlayan iOS ayarlarını devre dışı bırakır. Cihazı kaydettikten sonra, cihaza fabrika sıfırlaması yapmadan bu ayarı değiştiremezsiniz. Bu cihazlarda **Denetimli** Yönetim Modu *Evet* olarak ayarlı olmalıdır. 

8. Bu profili kullanan cihazların **Bilgisayarlarla eşitleme** imkanının olup olmayacağını seçin. **Sertifikaya göre Apple Configurator’a izin ver**’i seçerseniz, **Apple Configurator Sertifikaları**’nın altında bir sertifika seçmeniz gerekir.

9. Önceki adımda **Sertifikaya göre Apple Configurator’a izin ver**’i seçtiyseniz içeri aktaracak bir Apple Configurator Sertifikası seçin.

10. **Tamam**’ı seçin.

11. Şu profil ayarlarını yapılandırmak için **Kurulum Yardımcısı Ayarları**’nı seçin: ![Kurulum Yardımcısı Özelleştirme.](./media/device-enrollment-program-enroll-ios/setupassistantcustom.png)


    |                 Ayar                  |                                                                                               Description                                                                                               |
    |------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    |     <strong>Departman Adı</strong>     |                                                             Kullanıcı, etkinleştirme sırasında <strong>Yapılandırma Hakkında</strong> öğesine dokunduğunda görüntülenir.                                                              |
    |    <strong>Departman Telefonu</strong>     |                                                          Kullanıcı, etkinleştirme sırasında <strong>Yardım Gerekli</strong> düğmesine dokunduğunda görüntülenir.                                                          |
    | <strong>Kurulum Yardımcısı Seçenekleri</strong> |                                                     Aşağıdaki isteğe bağlı ayarlar, daha sonra iOS <strong>Ayarlar</strong> menüsünden ayarlanabilir.                                                      |
    |        <strong>Geçiş kodu</strong>         | Etkinleştirme sırasında geçiş kodu ister. Cihazın güvenliği sağlanmayacaksa veya erişim denetimi başka bir yolla (cihazı tek uygulamayla sınırlandıran bilgi noktası modu) uygulanmayacaksa her zaman geçiş kodu gerektirir. |
    |    <strong>Konum Hizmetleri</strong>    |                                                                 Bu etkinleştirilirse Kurulum Yardımcısı, etkinleştirme sırasında bu hizmeti sorar.                                                                  |
    |         <strong>Geri Yükle</strong>         |                                                                Bu etkinleştirilirse Kurulum Yardımcısı, etkinleştirme sırasında iCloud yedeklemesini sorar.                                                                 |
    |   <strong>iCloud ve Apple Kimliği</strong>   |                         Bu etkinleştirilirse Kurulum Yardımcısı, kullanıcıdan bir Apple Kimliği ile oturum açmasını ister ve Uygulamalar ve Veriler ekranında cihazın iCloud yedeğinden geri yüklenmesine izin verilir.                         |
    |  <strong>Hüküm ve Koşullar</strong>   |                                                   Bu etkinleştirilirse Kurulum Yardımcısı, etkinleştirme sırasında kullanıcılardan Apple’ın hüküm ve koşullarını kabul etmelerini ister.                                                   |
    |        <strong>Touch ID</strong>         |                                                                 Bu etkinleştirilirse Kurulum Yardımcısı, etkinleştirme sırasında bu hizmeti sorar.                                                                 |
    |        <strong>Apple Pay</strong>        |                                                                 Bu etkinleştirilirse Kurulum Yardımcısı, etkinleştirme sırasında bu hizmeti sorar.                                                                 |
    |          <strong>Yakınlaştır</strong>           |                                                                 Bu etkinleştirilirse Kurulum Yardımcısı, etkinleştirme sırasında bu hizmeti sorar.                                                                 |
    |          <strong>Siri</strong>           |                                                                 Bu etkinleştirilirse Kurulum Yardımcısı, etkinleştirme sırasında bu hizmeti sorar.                                                                 |
    |     <strong>Tanılama Verileri</strong>     |                                                                 Bu etkinleştirilirse Kurulum Yardımcısı, etkinleştirme sırasında bu hizmeti sorar.                                                                 |


12. **Tamam**’ı seçin.

13. Profili kaydetmek için **Oluştur**’u seçin.

## <a name="sync-managed-devices"></a>Yönetilen cihazları eşitleme
Artık Intune’a cihazlarınızı yönetme izni verildiğine göre, yönetilen cihazlarınızı Intune’da Azure portalında görmek için Intune’u Apple ile eşitleyebilirsiniz.

1. Azure portalında Intune’da, **Cihaz kaydı** > **Apple Kaydı** > **Kayıt programı belirteçleri** > listeden bir belirteç seçin > **Cihazlar** > **Eşitle**’yi seçin. ![Kayıt Programı Cihazları düğümünün seçili olduğu ve Eşitle bağlantısının seçildiği ekran görüntüsü.](./media/device-enrollment-program-enroll-ios/image06.png)

   Intune, Apple’ın kabul edilebilir kayıt programı trafiği şartlarına uymak için aşağıdaki kısıtlamaları getirir:
   - Tam eşitleme en sık yedi günde bir çalıştırılabilir. Tam eşitleme sırasında Intune, kendine atanmış tüm Apple seri numaralarını yeniler. Önceki tam eşitlemenin üzerinden yedi gün geçmeden bir tam eşitleme girişiminde bulunulursa, Intune yalnızca henüz Intune’da listelenmeyen seri numaralarını yeniler.
   - Herhangi bir eşitleme isteğinin tamamlanması için 15 dakika verilir. Bu süre boyunca veya istek başarılı olana kadar **Eşitle** düğmesi devre dışı bırakılır.
   - Intune, yeni ve kaldırılmış cihazları 24 saatte bir Apple ile eşitler.

## <a name="assign-an-enrollment-profile-to-devices"></a>Cihazlara kayıt profili atama
Cihazların kaydedilmesi için bunlara bir kayıt programı profili atamalısınız.

>[!NOTE]
>Ayrıca, **Apple Seri Numaraları** dikey penceresinde profillere seri numaralar da atayabilirsiniz.

1. Azure portalında Intune’da, **Cihaz kaydı** > **Apple Kaydı** > **Kayıt programı belirteçleri** > listeden bir belirteç seçin.
2. **Cihazlar** > listeden cihazları seçin > **Profil ata**’yı seçin.
3. **Profil ata** altında cihazlar için bir profil seçin ve daha sonra **Ata**’ya tıklayın.

### <a name="assign-a-default-profile"></a>Varsayılan bir profil atama

Belirli bir belirteç ile kaydedilen tüm cihazlara uygulanacak varsayılan bir profil seçebilirsiniz.

1. Azure portalında Intune’da, **Cihaz kaydı** > **Apple Kaydı** > **Kayıt programı belirteçleri** > listeden bir belirteç seçin.
2. **Varsayılan Profil Ayarla**’yı seçin, açılan listeden bir profil seçin ve daha sonra **Kaydet**’e tıklayın. Profil, bu belirteçle kaydedilen tüm cihazlara uygulanacaktır.

## <a name="distribute-devices"></a>Cihazları dağıtma
Apple ve Intune arasında eşitlemeyi ve yönetimi etkinleştirdiniz ve DEP cihazlarınızın kaydolmasına izin vermek için bir profil atadınız. Artık cihazları kullanıcılara dağıtabilirsiniz. Kullanıcı benzeşimli cihazlar, her kullanıcıya bir Intune lisansı atanmasını gerektirir. Kullanıcı benzeşimi olmayan cihazlar, cihaz lisansı gerektirir. Etkinleştirilmiş bir cihaz, fabrika sıfırlaması yapılana kadar bir kayıt profili uygulayamaz.

Bkz. [iOS cihazınızı Aygıt Kayıt Programı ile Intune’a kaydetme](/intune-user-help/enroll-your-device-dep-ios).


