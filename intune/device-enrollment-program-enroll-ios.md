---
title: "iOS cihazlarını kaydetme - Cihaz Kayıt Programı"
titleSuffix: Intune on Azure
description: "Şirkete ait iOS cihazlarını Cihaz Kayıt Programı kullanılarak kaydetmeyi öğrenin.\""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 654a19dd6f1e5f4fd2bda771b0df95b87944db75
ms.sourcegitcommit: 2a6ad3c233d15a9fb441362105f64b2bdd550c34
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/13/2017
---
# <a name="set-up-ios-device-enrollment-with-device-enrollment-program"></a>Cihaz Kayıt Programı ile iOS cihaz kaydı ayarlama

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Bu konu, Apple’ın [Aygıt Kayıt Programı (DEP)](https://deploy.apple.com) yoluyla satın alınan cihazlar için BT yöneticilerinin, iOS cihaz kaydını etkinleştirmelerine yardımcı olur. Microsoft Intune, kayıt profilini DEP aracılığıyla satın alınan cihazlara “kablosuz” şekilde dağıtabilir. Yöneticinin yönetilen cihazlara dokunması bile gerekmez. Bir DEP profili, Kurulum Yardımcısı seçenekleri dahil olmak üzere kayıt sırasında cihazlara uygulanan yönetim seçeneklerini içerir.

DEP kaydını etkinleştirmek için Intune ve Apple DEP portallarını birlikte kullanmanız gerekir. Cihazlarınızı, Apple portalında Intune ile yönetilmek üzere atayabilmeniz için kimlik listesi veya sipariş numarası da gereklidir.

>[!NOTE]
>DEP kaydı, [cihaz kayıt yöneticisiyle](device-enrollment-manager-enroll.md) birlikte kullanılamaz.

**Apple’dan kayıt programlarını etkinleştirme adımları**
1. [Apple DEP belirteci alma ve cihaz atama](#get-the-apple-dep-token)
2. [Kayıt profili oluşturma](#create-an-apple-enrollment-profile)
3. [DEP ile yönetilen cihazları eşitleme](#sync-managed-device)
4. [Cihazlara DEP profili atama](#assign-an-enrollment-profile-to-devices)
5. [Cihazları kullanıcılara dağıtma](#end-user-experience-with-managed-devices)

## <a name="get-the-apple-dep-token"></a>Apple DEP belirtecini alma

Şirketin sahibi olduğu iOS cihazlarını Apple’ın Cihaz Kayıt Programı’na (DEP) kaydedebilmeniz için bir Apple DEP (.p7m) belirteci dosyasına ihtiyacınız vardır. Bu belirteç Intune'un şirketinize ait olup DEP'e katılan cihazlar hakkındaki bilgileri eşitlemesini sağlar. Ayrıca Intune'un kayıt profilini Apple'a yüklemesine ve cihazları bu profillere atamasına izin verir.

> [!NOTE]
> Belirteci Azure’a geçirmeden önce klasik Intune portalında silerseniz Intune, silinmiş bir Apple DEP belirtecini geri yükleyebilir. DEP belirtecini Azure portalından tekrar silebilirsiniz. DEP belirtecini Azure portalından tekrar silebilirsiniz.

**Önkoşullar**
- [Apple MDM Anında İletme sertifikası](apple-mdm-push-certificate-get.md)
- [Apple'ın Aygıt Kayıt Programı](http://deploy.apple.com)'na kayıt yapıldı

**1. Adım. Apple DEP belirteci oluşturmak için gereken Intune ortak anahtar sertifikasını indirin.**<br>
1. Intune portalında, **Cihaz kaydı**'nı, ardından **Apple kaydı**'nı ve **Kayıt Programı Belirteci**'ni seçin.

  ![Apple Sertifikaları çalışma alanındaki Kayıt Programı Belirteci panelinin ekran görüntüsü.](./media/enrollment-program-token-add.png)

2. Şifreleme dosyasını (.pem) indirmek ve yerel olarak kaydetmek için **Ortak anahtar sertifikanızı indirin** öğesini seçin. .pem dosyası Apple Cihaz Kayıt Programı portalından güven ilişkisi sertifikası istemek için kullanılır.

  ![Apple Sertifikaları çalışma alanındaki Kayıt Programı Belirteci panelinde bulunan ortak anahtarı indirme öğesinin ekran görüntüsü.](./media/enrollment-program-token-download.png)

**2. Adım. Bir Apple DEP belirteci oluşturma ve indirme.**<br>
1. **Apple’ın Aygıt Kayıt Programı aracılığıyla bir belirteç oluştur**’a tıklayarak Apple’ın Dağıtım Programı portalını açın ve şirket Apple Kimliğinizle oturum açın. DEP belirtecinizi yenilemek için de bu Apple kimliğini kullanabilirsiniz.

  ![Apple Sertifikaları çalışma alanındaki Kayıt Programı Belirteci panelinin ekran görüntüsü.](./media/enrollment-program-token-create.png)

  ![Apple Sertifikaları çalışma alanındaki Kayıt Programı Belirteci panelinde bulunan ortak anahtarı indirme öğesinin ekran görüntüsü.](./media/enrollment-program-token-sign.png)
2.  Apple’ın [Dağıtım Programları portalında](https://deploy.apple.com), **Aygıt Kayıt Programı** için **Kullanmaya Başla**’yı seçin.

   ![Aygıt Kayıt Programı için Kayıt Programı’nda Kullanmaya Başla’ya tıklama işleminin ekran görüntüsü.](./media/enrollment-program-token-started.png)

3. **Sunucuları Yönet** sayfasında **MDM Sunucusu Ekle**’yi seçin.
4. **MDM Sunucu Adı**'nı girin ve ardından **İleri**'yi seçin. Sunucu adı, mobil cihaz yönetimi (MDM) sunucusunu tanımlarken kullanmanız içindir. Microsoft Intune sunucusunun adı veya URL'si değildir.

   ![DEP için MDM sunucu adı ekleme ve sonra İleri’ye tıklama ekran görüntüsü.](./media/enrollment-program-token-add-server.png)

5. **Ekle &lt;ServerName&gt;** iletişim kutusu açılır ve **Ortak Anahtarınızı Yükleyin** ifadesi yazar. **Dosya Seç…** öğesini seçin .pem dosyasını karşıya yükleyin ve ardından **İleri**'yi seçin.

   ![Ortak anahtar dosya düğmesini seçme ve ardından İleri’ye tıklama işleminin ekran görüntüsü.](./media/enrollment-program-token-choose-file.png)
6.  **&lt;SunucuAdı&gt; Ekle** iletişim kutusunda **Sunucu Belirteciniz** bağlantısı gösterilir. Sunucu belirteci (.p7m) dosyasını bilgisayarınıza indirin ve ardından **Bitti**'yi seçin.
   ![Ortak anahtar dosya düğmesini seçme ve sonra İleri’ye tıklama ekran görüntüsü.](./media/enrollment-program-token-your-token.png)
7. **Dağıtım Programları** &gt; **Cihaz Kayıt Programı** &gt; **Cihazları Yönet**'e gidin.
8. **Cihazları Şuna Göre Seç:** öğesinin altında cihazların nasıl tanımlanacağını belirtin:
    - **Seri Numarası**
    - **Sipariş Numarası**
    - **CSV Dosyası Yükle**.

   ![Cihazları seri numarasına göre seçme, eylem seç öğesini Sunucuya ata olarak seçme ve sunucu adını seçme ekran görüntüsü.](./media/enrollment-program-token-specify-serial.png)

9. **Eylem Seç** için **Sunucuya Ata**’yı seçin, Microsoft Intune’da belirtilen &lt;ServerName&gt;’i seçin ve **Tamam**’a basın. Apple portalı, belirtilen cihazları Intune sunucusunda yönetilmek üzere bu sunucuya atar ve **Atama Tamamlandı** ifadesini görüntüler.

   Apple portalında **Dağıtım Programları** &gt; **Aygıt Kayıt Programı** &gt; **Atama Geçmişini Görüntüle**’ye giderek cihazların listesi ile MDM sunucu atamalarına göz atabilirsiniz.

**3. Adım. Kayıt programı belirtecinizi oluşturmak için kullanılan Apple kimliğini girin.**<br>Gelecek başvurular için Intune portalında Apple kimliğini sağlayın. Tüm cihazlarınızı tekrar kaydetmeye gerek kalmadan kayıt programı belirtecinizi yenilemek için bu kimliği kullanın.

![Kayıt programı belirtecini oluşturmak için kullanılan Apple kimliğini belirtme ve kayıt programı belirtecine gözatma işleminin ekran görüntüsü.](./media/enrollment-program-token-apple-id.png)

**4. Adım. Kayıt programı belirtecinizi yüklemeden önce belirtece göz atın.**<br>
Sertifika (.pem) dosyasına gidin, **Aç**’ı ve sonra da **Karşıya Yükle**’yi seçin. Anında iletme sertifikasıyla, Intune ilkeyi kayıtlı mobil cihazlara ileterek iOS cihazları kaydedebilir ve yönetebilir. Intune, kayıt programı hesabınızı görmek için Apple ile otomatik olarak eşitlenir.

## <a name="create-an-apple-enrollment-profile"></a>Apple kayıt profili oluşturma

Bir cihaz kayıt profili, kayıt sırasında bir grup cihaza uygulanan ayarları tanımlar.

1. Intune portalında **Cihaz kaydı**'nı, ardından **Apple Kaydı**'nı seçin.
2. **Apple için Kayıt Programı**’nın altında **Kayıt Programı Profilleri**’ni seçin, daha sonra **Kayıt Programı Profilleri** dikey penceresinde **Oluştur**’u seçin.

  ![Yeni bir kayıt programı profili oluşturmak için oluştur bağlantısını seçme işleminin ekran görüntüsü.](./media/enrollment-program-profile-create.png)

3. **Kayıt Profili Oluştur** dikey penceresinde, yönetim amaçları doğrultusunda profil için bir **Ad** ve **Açıklama** girin. Kullanıcılar bu ayrıntıları göremez.

  ![Ad ve açıklamayı belirtme ve sonra yeni bir kayıt program profili için Kullanıcı benzeşimi ile kaydet’i seçme ekran görüntüsü.](./media/enrollment-program-profile-name.png)
**Kullanıcı Benzeşimi** için, bu profile sahip cihazların kullanıcı benzeşimiyle mi yoksa kullanıcı benzeşimi olmadan mı kaydedileceğini seçin.

 - **Kullanıcı benzeşimiyle kaydet** - Kurulum sırasında kullanıcılar, cihazlara bağlıdır ve kullanıcıların bu sayede şirket verilerine ve e-postasına erişim izinleri vardır. Kullanıcılara ait olan ve uygulamaları yükleme gibi hizmetler için şirket portalını kullanması gereken cihazlarda **kullanıcı benzeşimini** seçin.

 > [!NOTE]
 > Multifactor authentication (MFA), kullanıcı benzeşimi özellikli ve kayıt programıyla yönetilen cihazlarda kayıt sırasında çalışmaz. Kayıttan sonra MFA bu cihazlar üzerinde beklendiği gibi çalışır. İlk kez oturum açarken parola değiştirmesi istenen yeni kullanıcılara, cihazların kaydı sırasında istemde bulunulamaz. Ayrıca, parolalarının süresi dolmuş olan kullanıcılardan kayıt sırasında parolalarını sıfırlamaları istenmez ve bu kullanıcıların farklı bir cihazdan parolayı sıfırlamaları gerekir.

 >[!NOTE]
 >Kullanıcı benzeşimi ile cihaz kayıt programı; kullanıcı belirteci istemek için [WS-Trust 1.3 Kullanıcı adı/Karma uç noktasının](https://technet.microsoft.com/library/adfs2-help-endpoints) etkinleştirilmesini gerektirir. [WS-Trust 1.3 hakkında daha fazla bilgi edinin](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

 - **Kullanıcı benzeşimi olmadan kaydet** - Cihaz bir kullanıcıya bağlı değildir. Bu ilişkiyi, yerel kullanıcı verilerine erişmeden görevleri yerine getiren cihazlar için kullanın. Kullanıcı benzeşimi gerektiren uygulamalar (iş kolu uygulamalarını yüklemek için kullanılan Şirket Portalı uygulaması da dahil) çalışmaz.

4. Aşağıdaki profil ayarlarını yapılandırmak için **Cihaz Yönetim Ayarları**’nı seçin:

  ![Yönetim modunu seçme işleminin ekran görüntüsü. Cihaz aşağıdaki ayarlara sahiptir: Denetimli, kilitli kayıt, eşleşmeye izin ver tümünü reddet olarak ayarlı. Apple Configurator Sertifikaları, yeni bir kayıt programı profili için devre dışıdır.](./media/enrollment-program-profile-mode.png)
    - **Denetimli** - Daha fazla yönetim seçeneğini etkinleştiren ve varsayılan olarak Etkinleştirme Kilidi’ni devre dışı bırakan yönetim modu. Onay kutusunu boş bırakırsanız, sınırlı yönetim özelliklerine sahip olursunuz.

    - **Kilitli kayıt** - (Yönetim Modu = Denetimli seçimini gerektirir) Yönetim profilini kaldırmaya izin verebilecek iOS ayarlarını devre dışı bırakır. Onay kutusunu boş bırakırsanız, yönetim profilinin Ayarlar menüsünden kaldırılmasına izin verir. Cihazı kaydettikten sonra, cihaza fabrika sıfırlaması yapmadan bu ayarı değiştiremezsiniz.

    - **Eşleştirmeye İzin Ver** - iOS cihazlarının bilgisayarlarla eşitlenip eşitlenemeyeceğini belirtir. **Sertifikaya göre Apple Configurator’a izin ver**’i seçerseniz, **Apple Configurator Sertifikaları**’nın altında bir sertifika seçmeniz gerekir.

    - **Apple Configurator Sertifikaları** - **Eşleştirmeye İzin Ver**’in altında **Sertifikaya göre Apple Configurator’a izin ver**’i seçtiyseniz, içeri aktarılacak bir Apple Configurator Sertifikası seçin.

  **Kaydet**’i seçin.

5. Aşağıdaki profil ayarlarını yapılandırmak için **Kurulum Yardımcısı Ayarları**’nı seçin:

  ![Yeni bir kayıt programı profili için kullanılabilir ayarlardan yapılandırma ayarlarını seçme işleminin ekran görüntüsü.](./media/enrollment-program-profile-settings.png)
    - **Bölüm Adı** - Kullanıcı etkinleştirme sırasında **Yapılandırma Hakkında** öğesine dokunduğunda görüntülenir.

    - **Departman Telefonu** - Kullanıcı, etkinleştirme sırasında **Yardım Gerekli** düğmesine tıkladığında görüntülenir.
    - **Kurulum Yardımcısı Seçenekleri** - Bu isteğe bağlı ayarlar daha sonra iOS **Ayarlar** menüsünden ayarlanabilir.
        - **Geçiş kodu** - Etkinleştirme sırasında geçiş kodu ister. Başka bir yolla cihazın güvenliği sağlanmayacaksa veya erişim denetimi uygulanmayacaksa geçiş kodunu her zaman gerekli kılın. Örneğin bilgi noktası modu, cihazı tek uygulamayla sınırlandırır.
        - **Konum Hizmetleri** - Etkinleştirilirse, Kurulum Yardımcısı etkinleştirme sırasında hizmeti sorar
        - **Geri Yükle** - Etkinleştirilirse, Kurulum Yardımcısı etkinleştirme sırasında iCloud yedeklemesini sorar
        - **Apple kimliği** - Etkinleştirilirse, Intune kimlik girilmeden bir uygulama yüklemeyi denediğinde iOS kullanıcılardan Apple kimliği ister. Intune tarafından yüklenenler de dahil olmak üzere iOS App Store uygulamalarını indirmek için Apple kimliği gerekir.
        - **Hüküm ve Koşullar** - Etkinleştirilirse, Kurulum Yardımcısı etkinleştirme sırasında kullanıcılardan Apple’ın hüküm ve koşullarını kabul etmelerini ister
        - **Touch ID** - Etkinleştirilirse, Kurulum Yardımcısı etkinleştirme sırasında bu hizmeti sorar
        - **Apple Pay** - Etkinleştirilirse, Kurulum Yardımcısı etkinleştirme sırasında bu hizmeti sorar
        - **Zoom** - Etkinleştirilirse, Kurulum Yardımcısı etkinleştirme sırasında bu hizmeti sorar
        - **Siri** - Etkinleştirilirse, Kurulum Yardımcısı etkinleştirme sırasında bu hizmeti sorar
        - **Tanılama Verileri** - Etkinleştirilirse, Kurulum Yardımcısı etkinleştirme sırasında bu hizmeti sorar

    **Kaydet**’i seçin.
9. Profil ayarlarını kaydetmek için, **Kayıt Profili Oluştur** dikey penceresinde **Oluştur**’u seçin. Kayıt profili, Apple Kayıt Programı Kayıt Profilleri listesinde görünür.

## <a name="sync-managed-devices"></a>Yönetilen cihazları eşitleme
Artık Intune’a cihazlarınızı yönetme izni verildiğine göre, yönetilen cihazlarınızı Intune portalında görmek için Intune’u Apple ile eşitleyebilirsiniz.

1. Intune portalında **Cihaz kaydı** &gt;  **Apple Kaydı** &gt; **Kayıt Programı Cihazları**’nı seçin.
2. **Kayıt Programı Cihazları** altında **Eşitle**’yi seçin. **Eşitle** dikey penceresi görünecektir.

  ![Kayıt Programı Cihazları düğümünün seçili olduğu ve Eşitle bağlantısının seçildiği ekran görüntüsü.](./media/enrollment-program-device-sync.png)
3. **Eşitle** dikey penceresinde **Eşitleme İste**’yi seçin. İlerleme çubuğu, yeniden Eşitleme istemeden önce beklemeniz gereken süreyi gösterir.

  ![Eşitleme dikey penceresinde Eşitleme iste bağlantısının seçildiği ekran görüntüsü.](./media/enrollment-program-device-request-sync.png)

  Intune, Apple’ın kabul edilebilir kayıt programı trafiği şartlarına uymak için aşağıdaki kısıtlamaları getirir:
     -  Tam eşitleme en sık yedi günde bir çalıştırılabilir. Tam eşitleme sırasında Intune, kendine atanmış tüm Apple seri numaralarını yeniler. Önceki tam eşitlemenin üzerinden yedi gün geçmeden bir tam eşitleme girişiminde bulunulursa, Intune yalnızca henüz Intune’da listelenmeyen seri numaralarını yeniler.
     -  Herhangi bir eşitleme isteğinin tamamlanması için 15 dakika verilir. Bu süre boyunca veya istek başarılı olana kadar **Eşitle** düğmesi devre dışı bırakılır.
     - Intune, yeni ve kaldırılmış cihazları 24 saatte bir Apple ile eşitler.
     
4. Kayıt Programı Cihazları çalışma alanında **Yenile**’ye tıklayarak cihazlarınızı görebilirsiniz.

## <a name="assign-an-enrollment-profile-to-devices"></a>Cihazlara kayıt profili atama
Cihazların kaydedilmesi için bunlara bir kayıt programı profili atamalısınız.

>[!NOTE]
>Ayrıca, **Apple Seri Numaraları** dikey penceresinde profillere seri numaralar da atayabilirsiniz.

1. Intune portalında, **Cihaz kaydı** > **Apple Kaydı**'nı, ardından **Kayıt Program Profilleri**'ni seçin.
2. **Kayıt Programı Profilleri** listesinden cihazlara atamak istediğiniz profili ve ardından **Cihaz atama**’yı seçin.

 ![Eşitleme dikey penceresinde Eşitleme iste bağlantısının seçildiği ekran görüntüsü.](./media/enrollment-program-device-assign.png)

3. **Ata**’yı ve ardından bu profile atamak istediğiniz cihazları seçin. Kullanılabilir cihazları görüntülemek için filtreleyebilirsiniz:
  - **atanmayanlar**
  - **tümü**
  - **&lt;profil adı&gt;**
4. Atamak istediğiniz cihazları seçin. Sütunun üstündeki onay kutusu, listelenen cihazlardan en fazla 1000 tanesini seçer, ardından **Ata**’ya tıklayın. 1000 taneden fazla cihazı kaydetmek için tüm cihazlara bir kayıt profili atanana kadar atama adımlarını yineleyin.

  ![Intune portalında kayıt programı profili atamak için Ata düğmesinin ekran görüntüsü](media/dep-profile-assignment.png)

## <a name="end-user-experience-with-managed-devices"></a>Yönetilen cihazlarda son kullanıcı deneyimi

Artık cihazları kullanıcılara dağıtabilirsiniz. Kullanıcı benzeşimli cihazlar, her kullanıcıya bir Intune lisansı atanmasını gerektirir. Etkinleştirilmiş bir cihaz, fabrika sıfırlaması yapılana kadar bir kayıt profili uygulayamaz. Kayıt programı tarafından yönetilen iOS cihazı açıldığında, kullanıcı cihazında aşağıdaki seçenekleri görür:  

1. **iOS cihazı kur** - Kullanıcılar, aşağıdaki seçeneklerden birini seçebilir:
  - **Yeni cihaz olarak Ayarla**
  - **iCloud Yedeğinden Geri Yükle**
  - **iTunes Yedeğinden Geri Yükle**
2. Kullanıcılar, **&lt;Kuruluşunuz&gt;, cihazınızı otomatik olarak yapılandırılacaktır** bilgisini alır. Aşağıdaki ilave yapılandırma bilgileri de mevcuttur:

  **Yapılandırma, &lt;Kuruluşunuzun&gt; bu cihazı kablosuz olarak yönetmesine izin verir.**

  **Bir yönetici; e-posta ve ağ hesapları ayarlamanıza, uygulama yükleyip yapılandırmanıza ve ayarları uzaktan yönetmenize yardımcı olabilir.**

  **Bir yönetici; özellikleri devre dışı bırakabilir, uygulama yükleyip kaldırabilir, İnternet trafiğinizi kısıtlayabilir ve bu cihazı uzaktan silebilir.**

  **Yapılandırma şunlar tarafından sağlanır:<br> &lt;Kuruluşunuz&gt; iOS Ekibi<br> &lt;Adres&gt;**

3. Kullanıcılardan iş veya okul kullanıcı adları ve parolaları istenir.
4. Kullanıcılardan Apple kimlikleri istenir. Intune Şirket Portalı uygulaması ve diğer uygulamaları yüklemek için bir Apple kimliği gereklidir. Kimlik bilgileri sağlandıktan sonra cihaz, kaldırılması mümkün olmayan bir yönetim profili yükler. Intune yönetim profili cihazda, **Ayarlar** > **Genel** > **Cihaz Yönetimi**’nde görüntülenir.

Kullanıcılar artık, Intune Şirket Portalı veya Apple Kurulum Asistanı’nı kullanarak şirkete ait cihazlarının kurulumunu tamamlayabilir.
