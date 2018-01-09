---
title: "iOS cihazlarını kaydetme - Cihaz Kayıt Programı"
titlesuffix: Azure portal
description: "Şirkete ait iOS cihazlarını Cihaz Kayıt Programı kullanılarak kaydetmeyi öğrenin.\""
keywords: 
author: ErikjeMS
ms.author: erikje
manager: angrobe
ms.date: 10/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 25e5922de658ca2137a32e43802072367587747c
ms.sourcegitcommit: 833b1921ced35be140f0107d0b4205ecacd2753b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/04/2018
---
# <a name="automatically-enroll-ios-devices-with-apples-device-enrollment-program"></a>iOS cihazlarını Apple’ın Aygıt Kayıt Programı ile otomatik olarak kaydetme

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

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

> [!NOTE]
> Çok faktörlü kimlik doğrulaması (MFA), kullanıcı benzeşimi için ayarlanmış DEP kaydı sırasında çalışmaz. Kayıttan sonra MFA, cihazlarda beklendiği gibi çalışır. Cihazlar, ilk defa oturum açıldığında parolalarını değiştirmesi gereken kullanıcılara istemde bulunamaz. Ayrıca, parolalarının süresi dolmuş olan kullanıcılardan kayıt sırasında parolalarını sıfırlamaları istenmez. Kullanıcıların, parolayı sıfırlamak için farklı bir cihaz kullanmaları gerekir.

## <a name="get-the-apple-dep-token"></a>Apple DEP belirtecini alma

iOS cihazlarını DEP ile kaydedebilmeniz için bir Apple DEP belirteci dosyasına (.p7m) ihtiyacınız vardır. Bu belirteç, Intune'un şirketinize ait olan DEP cihazları hakkındaki bilgileri eşitlemesini sağlar. Ayrıca Intune'un kayıt profilini Apple'a yüklemesine ve cihazları bu profillere atamasına izin verir.

DEP belirtecini oluşturmak için Apple DEP portalını kullanın. Cihazları yönetim için Intune’a atamak için DEP portalını da kullanabilirsiniz.

> [!NOTE]
> Belirteci Azure’a geçirmeden önce klasik Intune portalında silerseniz Intune, silinen bir Apple DEP belirtecini geri yükleyebilir. DEP belirtecini Azure portalından tekrar silebilirsiniz. DEP belirtecini Azure portalından tekrar silebilirsiniz.

**1. Adım. Apple DEP belirteci oluşturmak için gereken Intune ortak anahtar sertifikasını indirin.**<br>

1. Azure portalında Intune’da, **Cihaz kaydı** > **Apple kaydı** > **Kayıt Programı Belirteci**’ni seçin.

  ![Apple Sertifikaları çalışma alanındaki Kayıt Programı Belirteci panelinin ekran görüntüsü.](./media/enrollment-program-token-add.png)

2. Şifreleme dosyasını (.pem) indirmek ve yerel olarak kaydetmek için **Ortak anahtarınızı indirin** öğesini seçin. .pem dosyası Apple Cihaz Kayıt Programı portalından güven ilişkisi sertifikası istemek için kullanılır.

  ![Apple Sertifikaları çalışma alanındaki Kayıt Programı Belirteci panelinde bulunan ortak anahtarı indirme öğesinin ekran görüntüsü.](./media/enrollment-program-token-download.png)

**2. Adım. Bir Apple DEP belirteci oluşturma ve indirme.**<br>
1. Apple’ın Dağıtım Programı portalını açmak için **Apple’ın Aygıt Kayıt Programı aracılığıyla bir belirteç oluştur**’u seçin ve şirket Apple Kimliğinizle oturum açın. DEP belirtecinizi yenilemek için de bu Apple kimliğini kullanabilirsiniz.
2.  Apple’ın [Dağıtım Programları portalında](https://deploy.apple.com), **Aygıt Kayıt Programı** için **Kullanmaya Başla**’yı seçin.

3. **Sunucuları Yönet** sayfasında **MDM Sunucusu Ekle**’yi seçin.
4. **MDM Sunucu Adı**'nı girin ve ardından **İleri**'yi seçin. Sunucu adı, mobil cihaz yönetimi (MDM) sunucusunu tanımlarken kullanmanız içindir. Microsoft Intune sunucusunun adı veya URL'si değildir.

   ![DEP için MDM sunucu adı ekleme ve sonra İleri’ye tıklama ekran görüntüsü.](./media/enrollment-program-token-add-server.png)

5. **Ekle &lt;ServerName&gt;** iletişim kutusu açılır ve **Ortak Anahtarınızı Yükleyin** ifadesi yazar. **Dosya Seç…** öğesini seçin .pem dosyasını karşıya yükleyin ve ardından **İleri**'yi seçin.  


7. **Dağıtım Programları** &gt; **Cihaz Kayıt Programı** &gt; **Cihazları Yönet**'e gidin.
8. **Cihazları Şuna Göre Seç:** öğesinin altında cihazların nasıl tanımlanacağını belirtin:
    - **Seri Numarası**
    - **Sipariş Numarası**
    - **CSV Dosyası Yükle**.

   ![Cihazları seri numarasına göre seçme, eylem seç öğesini Sunucuya ata olarak seçme ve sunucu adını seçme ekran görüntüsü.](./media/enrollment-program-token-specify-serial.png)

9. **Eylem Seç** işlemi için **Sunucuya Ata**’yı ve Microsoft Intune için belirtilen &lt;ServerName&gt; öğesini belirleyip **Tamam**'ı seçin. Apple portalı, belirtilen cihazları Intune sunucusunda yönetilmek üzere bu sunucuya atar ve **Atama Tamamlandı** ifadesini görüntüler.

   Apple portalında **Dağıtım Programları** &gt; **Aygıt Kayıt Programı** &gt; **Atama Geçmişini Görüntüle**’ye giderek cihazların listesi ile MDM sunucu atamalarına göz atabilirsiniz.

**3. Adım. Kayıt programı belirtecinizi oluşturmak için kullanılan Apple kimliğini girin.**<br>Azure portalında Intune’da ileride başvurmak üzere Apple kimliğini sağlayın. İleride tüm cihazlarınızı tekrar kaydetmeye gerek kalmadan kayıt programı belirtecinizi yenilemek için bu kimliği kullanın.

![Kayıt programı belirtecini oluşturmak için kullanılan Apple kimliğini belirtme ve kayıt programı belirtecine gözatma işleminin ekran görüntüsü.](./media/enrollment-program-token-apple-id.png)

**4. Adım. Kayıt programı belirtecinizi yüklemeden önce belirtece göz atın.**<br>
Sertifika (.pem) dosyasına gidin, **Aç**’ı ve sonra da **Karşıya Yükle**’yi seçin. Anında iletme sertifikasıyla, Intune ilkeyi kayıtlı mobil cihazlara ileterek iOS cihazları kaydedebilir ve yönetebilir. Intune, kayıt programı hesabınızı görmek için Apple ile otomatik olarak eşitlenir.

## <a name="create-an-apple-enrollment-profile"></a>Apple kayıt profili oluşturma

Belirtecinizi yüklediğinize göre, DEP cihazları için kayıt profili oluşturabilirsiniz. Bir cihaz kayıt profili, kayıt sırasında bir grup cihaza uygulanan ayarları tanımlar.

1. Azure portalında Intune’da, **Cihaz kaydı** > **Apple Kaydı**’nı seçin.
2. **Apple Kayıt Programı**'nın altından **Kayıt Programı Profilleri** > **Oluştur**'u seçin.
3. **Kayıt Profili Oluştur** kısmında, yönetim amaçları doğrultusunda profil için bir **Ad** ve **Açıklama** girin. Kullanıcılar bu ayrıntıları göremez. Azure Active Directory’de dinamik bir grup oluşturmak için **Ad** alanını kullanabilirsiniz. enrollmentProfileName parametresini, bu kayıt profiliyle cihazlara atamak amacıyla tanımlamak için profil adını kullanın. [Azure Active Directory dinamik grupları](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal#using-attributes-to-create-rules-for-device-objects) hakkında daha fazla bilgi edinin.

  **Kullanıcı Benzeşimi** için bu profile sahip cihazların atanan kullanıcıyla mı yoksa atanan kullanıcı olmadan mı kaydedileceğini seçin.

 - **Kullanıcı benzeşimi ile kaydetme** - Kullanıcılara ait olan ve uygulamaları yükleme gibi hizmetler için şirket portalını kullanması gereken cihazlar için seçin. Kullanıcı benzeşimi [WS-Trust 1.3 Kullanıcı adı/Karma uç noktası](https://technet.microsoft.com/library/adfs2-help-endpoints) gerektirir. [Daha fazla bilgi edinin](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

 - **Kullanıcı benzeşimi olmadan kaydetme** - Tek bir kullanıcıyla bağlantılı olmayan bir cihaz seçin. Yerel kullanıcı verilerine erişmeden görevleri yerine getiren cihazlar için kullanın. Şirket Portalı uygulaması gibi uygulamalar çalışmaz.

4. Aşağıdaki profil ayarlarını yapılandırmak için **Cihaz Yönetim Ayarları**’nı seçin:

  ![Yönetim modunu seçme işleminin ekran görüntüsü. Cihaz aşağıdaki ayarlara sahiptir: denetimli, kilitli kayıt, eşleşmeye izin ver tümünü reddet olarak ayarlı. Apple Configurator Sertifikaları, yeni bir kayıt programı profili için devre dışıdır.](./media/enrollment-program-profile-mode.png)
    - **Denetimli** - Daha fazla yönetim seçeneğini etkinleştiren ve varsayılan olarak Etkinleştirme Kilidi’ni devre dışı bırakan yönetim modu. Onay kutusunu boş bırakırsanız, sınırlı yönetim özelliklerine sahip olursunuz. Microsoft, özellikle fazla sayıda iOS cihaz dağıtan kuruluşlar için denetimli modu etkinleştirme mekanizması olarak DEP’in kullanılmasını önerir.

 > [!NOTE]
 > Bir cihaz kaydedildikten sonra, Intune kullanarak cihazı denetimli mod için yapılandırmak mümkün olmayacaktır. Kayıt sonrasında denetimli modu etkinleştirmenin tek yolu, bir USB kablosuyla iOS cihazı bir Mac’e bağlamak ve Apple Configurator kullanmaktır. Böylece cihaz sıfırlanır ve denetimli mod için yapılandırılabilir. Bu konu hakkında daha fazla bilgi için [Apple Configurator belgelerine](http://help.apple.com/configurator/mac/2.3) bakın. Denetimli bir cihazın kilit ekranında “Bu iPhone, Contoso tarafından yönetilmektedir.” ifadesi ve **Ayarlar** > **Genel** > **Hakkında** bölümünde “Bu iPhone denetimlidir. Contoso, internet trafiğinizi izleyebilir ve cihazın konumunu belirleyebilir.” ifadesi yer alır.

    - **Kilitli kayıt** - (Yönetim Modu = denetimli seçimini gerektirir) Yönetim profilini kaldırmaya izin verebilecek iOS ayarlarını devre dışı bırakır. Onay kutusunu boş bırakırsanız, yönetim profilinin Ayarlar menüsünden kaldırılmasına izin verir. Cihazı kaydettikten sonra, cihaza fabrika sıfırlaması yapmadan bu ayarı değiştiremezsiniz.

  - **Paylaşılan iPad’i etkinleştir** - Apple’ın Aygıt Kayıt Programı, paylaşılan iPad’i desteklemez.

    - **Eşleştirmeye İzin Ver** - iOS cihazlarının bilgisayarlarla eşitlenip eşitlenemeyeceğini belirtir. **Sertifikaya göre Apple Configurator’a izin ver**’i seçerseniz **Apple Configurator Sertifikaları**’nın altında bir sertifika seçmeniz gerekir.

    - **Apple Configurator Sertifikaları** - **Eşleştirmeye İzin Ver**’in altında **Sertifikaya göre Apple Configurator’a izin ver**’i seçtiyseniz içeri aktarılacak bir Apple Configurator Sertifikası seçin.

  **Kaydet**’i seçin.

5. Aşağıdaki profil ayarlarını yapılandırmak için **Kurulum Yardımcısı Ayarları**’nı seçin:

  ![Yeni bir kayıt programı profili için kullanılabilir ayarlardan yapılandırma ayarlarını seçme işleminin ekran görüntüsü.](./media/enrollment-program-profile-settings.png)
    - **Bölüm Adı** - Kullanıcı etkinleştirme sırasında **Yapılandırma Hakkında** öğesine dokunduğunda görüntülenir.

    - **Departman Telefonu** - Kullanıcı, etkinleştirme sırasında **Yardım Gerekli** düğmesine tıkladığında görüntülenir.
    - **Kurulum Yardımcısı Seçenekleri** - Bu isteğe bağlı ayarlar daha sonra iOS **Ayarlar** menüsünden ayarlanabilir.
        - **Geçiş kodu**
        - **Konum Hizmetleri**
        - **Geri Yükle**
        - **Apple Kimliği**
        - **Hüküm ve Koşullar**
        - **Touch ID**
        - **Apple Pay**
        - **Yakınlaştır**
        - **Siri**
        - **Tanılama Verileri**

    **Kaydet**’i seçin.

9. Profil ayarlarını kaydetmek için **Kayıt Profili Oluştur** dikey penceresinde **Oluştur**’u seçin. Kayıt profili, Apple Kayıt Programı Kayıt Profilleri listesinde görünür.

## <a name="sync-managed-devices"></a>Yönetilen cihazları eşitleme
Artık Intune’a cihazlarınızı yönetme izni verildiğine göre, yönetilen cihazlarınızı Intune’da Azure portalında görmek için Intune’u Apple ile eşitleyebilirsiniz.

1. Azure portalında Intune’da, **Cihaz kaydı** > **Apple Kaydı** > **Kayıt Programı Cihazları** > **Eşitle**’yi seçin. İlerleme çubuğu, yeniden Eşitleme istemeden önce beklemeniz gereken süreyi gösterir.

  ![Kayıt Programı Cihazları düğümünün seçili olduğu ve Eşitle bağlantısının seçildiği ekran görüntüsü.](./media/enrollment-program-device-sync.png)
  
2. **Eşitle** dikey penceresinde **Eşitleme İste**’yi seçin. İlerleme çubuğu, yeniden Eşitleme istemeden önce beklemeniz gereken süreyi gösterir.

  ![Eşitleme dikey penceresinde Eşitleme iste bağlantısının seçildiği ekran görüntüsü.](./media/enrollment-program-device-request-sync.png)

  Intune, Apple’ın kabul edilebilir kayıt programı trafiği şartlarına uymak için aşağıdaki kısıtlamaları getirir:
     -  Tam eşitleme en sık yedi günde bir çalıştırılabilir. Tam eşitleme sırasında Intune, kendine atanmış tüm Apple seri numaralarını yeniler. Önceki tam eşitlemenin üzerinden yedi gün geçmeden bir tam eşitleme girişiminde bulunulursa, Intune yalnızca henüz Intune’da listelenmeyen seri numaralarını yeniler.
     -  Herhangi bir eşitleme isteğinin tamamlanması için 15 dakika verilir. Bu süre boyunca veya istek başarılı olana kadar **Eşitle** düğmesi devre dışı bırakılır.
     - Intune, yeni ve kaldırılmış cihazları 24 saatte bir Apple ile eşitler.

3. Kayıt Programı Cihazları çalışma alanında **Yenile**’ye tıklayarak cihazlarınızı görebilirsiniz.

## <a name="assign-an-enrollment-profile-to-devices"></a>Cihazlara kayıt profili atama
Cihazların kaydedilmesi için bunlara bir kayıt programı profili atamalısınız.

>[!NOTE]
>Ayrıca, **Apple Seri Numaraları** dikey penceresinde profillere seri numaralar da atayabilirsiniz.

1. Azure portalında Intune’da, **Cihaz kaydı** > **Apple Kaydı**’nı ve ardından **Kayıt Programı Profilleri**’ni seçin.
2. **Kayıt Programı Profilleri** listesinden cihazlara atamak istediğiniz profili ve ardından **Cihazlara ata**’yı seçin.

 ![Ata seçeneğinin belirtildiği Cihaz Atamalarının ekran görüntüsü.](./media/enrollment-program-device-assign.png)

3. **Ata**’yı ve ardından bu profile atamak istediğiniz cihazları seçin. Kullanılabilir cihazları görüntülemek için filtreleyebilirsiniz:
  - **atanmayanlar**
  - **tümü**
  - **&lt;profil adı&gt;**
4. Atamak istediğiniz cihazları seçin. Sütunun üstündeki onay kutusu, listelenen cihazlardan en fazla 1000 tanesini seçer, ardından **Ata**’ya tıklayın. 1000 taneden fazla cihazı kaydetmek için tüm cihazlara bir kayıt profili atanana kadar atama adımlarını yineleyin.

  ![Intune’da kayıt programı profili atamak için Ata düğmesinin ekran görüntüsü](media/dep-profile-assignment.png)

## <a name="distribute-devices"></a>Cihazları dağıtma
Apple ve Intune arasında eşitlemeyi ve yönetimi etkinleştirdiniz ve DEP cihazlarınızın kaydolmasına izin vermek için bir profil atadınız. Artık cihazları kullanıcılara dağıtabilirsiniz. Kullanıcı benzeşimli cihazlar, her kullanıcıya bir Intune lisansı atanmasını gerektirir. Kullanıcı benzeşimi olmayan cihazlar, cihaz lisansı gerektirir. Etkinleştirilmiş bir cihaz, fabrika sıfırlaması yapılana kadar bir kayıt profili uygulayamaz.

Bkz. [iOS cihazınızı Aygıt Kayıt Programı ile Intune’a kaydetme](/intune-user-help/enroll-your-device-dep-ios). 
