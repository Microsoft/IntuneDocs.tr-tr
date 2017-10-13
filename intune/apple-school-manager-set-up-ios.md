---
title: "iOS cihazları için Apple School Manager Programı kaydını ayarlama"
titlesuffix: Azure portal
description: "Intune ile şirkete ait iOS cihazları için Apple School Manager Programı kaydını ayarlamayı öğrenin\""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 09/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: afb3aeff7a7c6cc481d24bac3a61de0816b4d34b
ms.sourcegitcommit: 001577b700f634da2fec0b44af2a378150d1f7ac
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2017
---
# <a name="enable-ios-device-enrollment-with-apple-school-manager"></a>Apple School Manager ile iOS cihaz kaydını etkinleştirme

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Bu konu, [Apple School Manager](https://school.apple.com/) programı aracılığıyla satın alınan cihazlarda iOS cihaz kaydını etkinleştirmenize yardımcı olur. Intune’u Apple School Manager ile birlikte kullanarak, çok sayıda iOS cihazını hiç dokunmadan kaydedebilirsiniz. Bir öğrenci veya öğretmen cihazı açtığında, önceden yapılandırılmış ayarları ile Kurulum Yardımcısı çalıştırılır ve cihaz yönetime kaydedilir.

Apple School Manager kaydını etkinleştirmek için Intune ve Apple School Manager portallarını kullanmanız gerekir. Cihazlarınızı, Intune ile yönetilmek üzere atayabilmeniz için seri numaraları listesi veya sipariş numarası gereklidir. Kayıt sırasında cihazlara uygulanan ayarları içeren DEP kayıt profilleri oluşturun.

Bu arada, Apple School Manager kaydı [Apple Aygıt Kayıt Programı](device-enrollment-program-enroll-ios.md) veya [cihaz kaydı yöneticisi](device-enrollment-manager-enroll.md) ile birlikte kullanılamaz.

**Önkoşullar**
- [Apple MDM Anında İletme sertifikası](apple-mdm-push-certificate-get.md)
- [MDM Yetkilisi](mdm-authority-set.md)
- [Apple MDM Anında İletme sertifikası](apple-mdm-push-certificate-get.md)
- Kullanıcı benzeşimi [WS-Trust 1.3 Kullanıcı adı/Karma uç noktası](https://technet.microsoft.com/library/adfs2-help-endpoints) gerektirir. [Daha fazla bilgi edinin](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).
- [Apple School Management](http://school.apple.com) programından satın alınan cihazlar

>[!NOTE]
>Çok faktörlü kimlik doğrulaması (MFA), kullanıcı benzeşimi özellikli Apple School Manager cihazlarda kayıt sırasında çalışmaz. Kayıttan sonra MFA bu cihazlar üzerinde beklendiği gibi çalışır. Kayıttan sonra MFA, cihazlarda beklendiği gibi çalışır. Cihazlar, ilk defa oturum açıldığında parolalarını değiştirmesi gereken kullanıcılara istemde bulunamaz. Ayrıca, parolalarının süresi dolmuş olan kullanıcılardan kayıt sırasında parolalarını sıfırlamaları istenmez. Kullanıcıların, parolayı sıfırlamak için farklı bir cihaz kullanmaları gerekir.

## <a name="get-the-apple-token-and-assign-devices"></a>Apple belirteci alma ve cihaz atama

Şirkete ait iOS cihazlarını Apple School Manager’a kaydedebilmek için Apple’dan bir belirteç (.p7m) dosyasına ihtiyacınız vardır. Bu belirteç, Intune’un Apple School Manager’a katılan cihazlara ait bilgileri eşitlemesini sağlar. Ayrıca Intune'un kayıt profilini Apple'a yüklemesine ve cihazları bu profillere atamasına izin verir. Apple portalındayken yönetilecek cihaz seri numaralarını da atayabilirsiniz.

**1. Adım. Bir Apple belirteci oluşturmak için gereken Intune ortak anahtar sertifikasını indirin.**<br>
1. [Azure portalında Intune](https://aka.ms/intuneportal)’da **Cihaz kaydı**'nı, ardından **Kayıt programı belirteci**'ni seçin.

  ![Apple Sertifikaları çalışma alanındaki Kayıt Programı Belirteci panelinde bulunan ortak anahtarı indirme öğesinin ekran görüntüsü.](./media/enrollment-program-token-download.png)

2. **Kayıt programı belirteci** dikey penceresinde, şifreleme dosyasını (.pem) indirmek ve yerel olarak kaydetmek için **Ortak anahtarınızı indirin**’i seçin. .pem dosyası Apple School Manager portalından güven ilişkisi sertifikası istemek için kullanılır.

**2. Adım. Bir belirteç indirin ve cihaz atayın.**<br>
1. **Apple School Manager aracılığıyla belirteç oluşturma**'yı seçin ve şirketinizin Apple kimliğiyle oturum açın. Apple School Manager belirtecinizi yenilemek için bu Apple kimliğini kullanabilirsiniz.
2.  [Apple School Manager portalında](https://school.apple.com), **MDM Sunucuları**’na gidin ve **MDM Sunucusu Ekle**’yi (sağ üstte) seçin.
3.  **MDM Sunucusu Adını** girin. Sunucu adı, mobil cihaz yönetimi (MDM) sunucusunu tanımlarken kullanmanız içindir. Microsoft Intune sunucusunun adı veya URL'si değildir.
   ![Seri Numarası seçeneği işaretliyken Apple School Manager portalının ekran görüntüsü](./media/asm-server-assignment.png)

4.  Apple portalında **Dosyayı Karşıya Yükle...**’yi seçin ve .pem dosyasına giderek **MDM Sunucusunu Kaydet**’i (sağ alt köşede) seçin.
5.  **Belirteci Al**’ı seçin ve ardından sunucu belirtecini (.p7m) bilgisayarınıza indirin.
6. **Cihaz Atamaları**’na gidin ve **Cihaz Seç** işlemini **Seri Numaraları**, **Sipariş Numarası**’nı elle girerek veya **CSV Dosyasını Karşıya Yükle** ile yapın.
     ![Seri Numarası seçeneği işaretliyken Apple School Manager portalının ekran görüntüsü](./media/asm-device-assignment.png)
7.  **Sunucuya Ata** eylemini seçip oluşturduğunuz **MDM Sunucusunu** seçin.
8. **Cihaz Seçme** işleminin nasıl olacağını belirtin ve daha sonra cihaza ait bilgileri ve ayrıntıları sağlayın.
9. **Sunucuya Ata**'yı ve Microsoft Intune için belirtilen &lt;ServerName&gt; öğesini belirleyip **Tamam**'ı seçin.

**3. Adım. Apple School Manager belirtecinizi oluşturmak için kullanılan Apple kimliğini girin.**<br>Bu kimlik, Apple School Manager belirtecinizi yenilemek için kullanılır ve gelecekte başvurulmak üzere depolanır.

![Kayıt programı belirtecini oluşturmak için kullanılan Apple kimliğini belirtme ve kayıt programı belirtecine gözatma işleminin ekran görüntüsü.](./media/enrollment-program-token-apple-id.png)

**4. Adım. Belirtecinizi bulun ve yükleyin.**<br>
Sertifika (.p7m) dosyasına gidin, **Aç**’ı ve sonra da **Karşıya Yükle**’yi seçin. Intune, Apple School Manager cihazlarınızı Apple’dan otomatik olarak eşitler.

## <a name="create-an-apple-enrollment-profile"></a>Apple kayıt profili oluşturma
Bir cihaz kayıt profili, kayıt sırasında bir grup cihaza uygulanan ayarları tanımlar.

1. Azure portalında Intune’da **Cihaz kaydı**'nı, ardından **Apple Kaydı**'nı seçin.
2. **Kayıt Programı**'nın altından **Kayıt Programı Profilleri**'ni seçin.
3. **Kayıt Programı Profilleri** dikey penceresinde **Oluştur**'u seçin.
4. **Kayıt Profili Oluştur** dikey penceresinde, Intune’da görüntülenen profil için bir **Ad** ve **Açıklama** girin.
5. **Kullanıcı Benzeşimi** için, bu profile sahip cihazların kullanıcı benzeşimiyle mi yoksa kullanıcı benzeşimi olmadan mı kaydedileceğini seçin.

 - **Kullanıcı benzeşimi ile kaydetme** - Kurulum sırasında cihazı bir kullanıcıyla birleştirir.

  Apple School Manager’ın Paylaşılan iPad modu, kullanıcının kullanıcı benzeşimi olmadan kaydolmasını gerektirir.

 - **Kullanıcı benzeşimi olmadan kaydetme** - Paylaşılan cihazlar gibi tek bir kullanıcıyla bağlantılı olmayan bir cihaz seçin. Yerel kullanıcı verilerine erişmeden görevleri yerine getiren cihazlar için kullanın. Şirket Portalı uygulaması gibi uygulamalar çalışmaz.

6. **Cihaz Yönetimi Ayarları**’nı seçin. Bu öğeler etkinleştirme sırasında ayarlanır ve bunları değiştirmek için Fabrika sıfırlaması gerekir. aşağıdaki profil ayarlarını yapılandırın ve ardından **Kaydet**’i seçin:

  ![Yönetim modunu seçme işleminin ekran görüntüsü. Cihaz aşağıdaki ayarlara sahiptir: denetimli, kilitli kayıt, eşleşmeye izin ver tümünü reddet olarak ayarlı. Apple Configurator Sertifikaları, yeni bir kayıt programı profili için devre dışıdır.](./media/enrollment-program-profile-mode.png)

    - **Denetimli** - Daha fazla yönetim seçeneğini etkinleştiren ve varsayılan olarak Etkinleştirme Kilidi’ni devre dışı bırakan yönetim modu. Onay kutusunu boş bırakırsanız, sınırlı yönetim özelliklerine sahip olursunuz.

     - **Kilitli kayıt** - (Yönetim Modu = denetimli seçimini gerektirir) Yönetim profilini kaldırmaya izin verebilecek iOS ayarlarını devre dışı bırakır. Onay kutusunu boş bırakırsanız, yönetim profilinin Ayarlar menüsünden kaldırılmasına izin verir.
   - **Paylaşılan iPad** - (**Kullanıcı Benzeşimi olmadan Kaydolma** ve Denetimli mod gerektirir.) Birden çok kullanıcının yönetilen Apple kimliği kullanarak kayıtlı iPad’lerde oturum açmasına izin verir. Yönetilen Apple kimlikleri Apple School Manager portalında oluşturulur. [Paylaşılan iPad](education-settings-configure-ios-shared.md) hakkında daha fazla bilgi edinin. [Apple’ın paylaşılan iPad gereksinimlerini](https://help.apple.com/classroom/ipad/2.0/#/cad7e2e0cf56) de gözden geçirmelisiniz.

   >[!NOTE]
   >**Kullanıcı Benzeşimi** özelliği **Kullanıcı benzeşimli** olarak ayarlıysa veya **Denetimli** modu **Kapalı** olarak belirtildiyse,  bu kayıt profili için paylaşılan iPad modu devre dışıdır.

        - **Maximum Cached Users** - (Requires **Shared iPad** = **Yes**) Creates a partition on the device for each user. The recommended value is the number of students likely to use the device over a period of time. For example, if six students use the device regularly during the week, set this number to six.  

    - **Eşleştirmeye İzin Ver** - iOS cihazlarının bilgisayarlarla eşitlenip eşitlenemeyeceğini belirtir. **Sertifikaya göre Apple Configurator’a izin ver**’i seçerseniz, **Apple Configurator Sertifikaları**’nın altında bir sertifika seçmeniz gerekir.

      - **Apple Configurator Sertifikaları** - **Eşleştirmeye İzin Ver**’in altında **Sertifikaya göre Apple Configurator’a izin ver**’i seçtiyseniz içeri aktarılacak bir Apple Configurator Sertifikası seçin.

7. **Kurulum Yardımcısı Ayarları**’nı seçin, aşağıdaki profil ayarlarını yapılandırın ve ardından **Kaydet**’i seçin:

    - **Bölüm Adı** - Kullanıcı etkinleştirme sırasında **Yapılandırma Hakkında** öğesine dokunduğunda görüntülenir.

    - **Bölüm Telefonu** - Kullanıcı etkinleştirme sırasında Yardım Gerekli düğmesine tıkladığında görüntülenir.
    - **Kurulum Yardımcısı Seçenekleri** - Bu ayarlar Kurulum Yardımcısı seçeneklerinde dışlanırsa, daha sonra iOS **Ayarlar** menüsünden ayarlanabilir.
        - **Geçiş kodu** - Etkinleştirme sırasında geçiş kodu ister. Cihazın güvenliği sağlanmayacaksa veya erişim denetimi başka bir yolla (cihazı tek uygulamayla sınırlandıran bilgi noktası modu) uygulanmayacaksa her zaman geçiş kodu gerektirir.
        - **Konum Hizmetleri** - Etkinleştirilirse, Kurulum Yardımcısı etkinleştirme sırasında hizmeti sorar
        - **Geri Yükle** - Etkinleştirilirse, Kurulum Yardımcısı etkinleştirme sırasında iCloud yedeklemesini sorar
        - **Apple kimliği** - Etkinleştirilirse, Intune kimlik girilmeden bir uygulama yüklemeyi denediğinde iOS kullanıcılardan Apple kimliği ister. Intune tarafından yüklenen uygulamalar da dahil olmak üzere, iOS Uygulama Mağazası uygulamalarını indirmek için Apple Kimliği gerekir.
        - **Hüküm ve Koşullar** - Etkinleştirilirse, Kurulum Yardımcısı etkinleştirme sırasında kullanıcılardan Apple’ın hüküm ve koşullarını kabul etmelerini ister
        - **Touch ID** - Etkinleştirilirse, Kurulum Yardımcısı etkinleştirme sırasında bu hizmeti sorar
        - **Apple Pay** - Etkinleştirilirse, Kurulum Yardımcısı etkinleştirme sırasında bu hizmeti sorar
        - **Zoom** - Etkinleştirilirse, Kurulum Yardımcısı etkinleştirme sırasında bu hizmeti sorar
        - **Siri** - Etkinleştirilirse, Kurulum Yardımcısı etkinleştirme sırasında bu hizmeti sorar
        - **Tanılama Verileri** - Etkinleştirilirse, Kurulum Yardımcısı etkinleştirme sırasında bu hizmeti sorar

8. Profil ayarlarını kaydetmek için **Kayıt Profili Oluştur** dikey penceresinde **Oluştur**’u seçin.

## <a name="connect-school-data-sync"></a>Okul Veri Eşitlemeye bağlanma
(İsteğe bağlı) Apple School Manager, sınıf ad listesi verilerini Microsoft School Data Sync (SDS) kullanarak Azure Active Directory’ye (AD) eşitlemeyi destekler. Okul verilerini eşitlemek üzere SDS kullanmak için aşağıdaki adımları tamamlayın.

1. **Kayıt Programı Belirteci** dikey penceresinde mavi bilgi başlığını veya **SDS’ye Bağlan**’ı seçin.
2. **Microsoft School Data Sync’in bu belirteci kullanmasına izin ver** ayarını **İzin ver** olarak ayarlayın. Bu ayar, Intune’un Office 365'teki SDS’ye bağlanmasını sağlar.
3. Apple School Manager ile Azure AD arasında bağlantıyı etkinleştirmek için **Microsoft School Data Sync’i Ayarla**’yı seçin. [Okul Veri Eşitlemesini ayarlama](https://support.office.com/article/Install-the-School-Data-Sync-Toolkit-8e27426c-8c46-416e-b0df-c29b5f3f62e1) hakkında daha fazla bilgi edinin.
4. Kaydedip devam etmek için **Tamam**'a tıklayın.

## <a name="sync-managed-devices"></a>Yönetilen cihazları eşitleme
Artık Intune’a Apple School Manager cihazlarınızı yönetme izni verildiğine göre, yönetilen cihazlarınızı Intune’da görmek için Intune’u Apple School Manager hizmetiyle eşitleyebilirsiniz.

1. Azure portalında Intune’da **Cihaz kaydı**'nı, ardından **Apple Kaydı**'nı seçin.
2. **Kayıt Programı Cihazları** altında **Eşitle**’yi seçin. İlerleme çubuğu, yeniden Eşitleme istemeden önce beklemeniz gereken süreyi gösterir.
3. **Eşitle** dikey penceresinde **Eşitleme İste**’yi seçin. İlerleme çubuğu, yeniden Eşitleme istemeden önce beklemeniz gereken süreyi gösterir.

  ![Eşitleme dikey penceresinde Eşitleme iste bağlantısının seçildiği ekran görüntüsü.](./media/enrollment-program-device-request-sync.png)

  Intune, Apple’ın kabul edilebilir trafik koşullarına uymak için aşağıdaki kısıtlamaları getirir:
   -    Tam eşitleme en sık yedi günde bir çalıştırılabilir. Intune tam eşitleme sırasında, Apple’ın Intune’a atadığı her seri numarasını, bu numaranın daha önceden eşitlenmiş olup olmamasına bakılmaksızın yeniler. Önceki tam eşitlemenin üzerinden yedi gün geçmeden bir tam eşitleme girişiminde bulunulursa, Intune yalnızca henüz Intune’da listelenmeyen seri numaralarını yeniler.
   -    Herhangi bir eşitleme isteğinin tamamlanması için 15 dakika verilir. Bu süre boyunca veya istek başarılı olana kadar **Eşitle** düğmesi devre dışı bırakılır.

>[!NOTE]
>Apple School Manager seri numaralarını **Kayıt Programı Cihazları** dikey penceresinden de profillere atayabilirsiniz.

## <a name="assign-a-profile-to-devices"></a>Cihazlara profil atama
Intune tarafından yönetilen Apple School Manager cihazları kaydedilmeden önce bu cihazlara bir kayıt profili atanmalıdır.

1. Azure portalında Intune’da, **Cihaz kaydı** > **Apple Kaydı**’nı ve ardından **Kayıt Programı profilleri**’ni seçin.
2. **Kayıt Programı Profilleri** listesinden cihazlara atamak istediğiniz profili ve ardından **Cihaz Atamaları**’nı seçin

 ![Ata seçeneğinin belirtildiği Cihaz Atamalarının ekran görüntüsü.](./media/enrollment-program-device-assign.png)

3. **Ata**’yı ve ardından bu profile atamak istediğiniz Apple School Manager cihazlarını seçin. Kullanılabilir cihazları görüntülemek için filtreleyebilirsiniz:
  - **atanmayanlar**
  - **tümü**
  - **&lt;profil adı&gt;**
4. Atamak istediğiniz cihazları seçin. Üstteki onay kutusu 1000’e kadar listelenen cihazı seçer. **Ata**’ya tıklayın. 1000 taneden fazla cihazı kaydetmek için tüm cihazlara bir kayıt profili atanana kadar atama adımlarını yineleyin.

  ![Intune’da kayıt programı profili atamak için Ata düğmesinin ekran görüntüsü](media/dep-profile-assignment.png)

## <a name="distribute-devices-to-users"></a>Cihazları kullanıcılara dağıtma

Şirkete ait cihazlarınızı artık kullanıcılara dağıtabilirsiniz. Bir iOS Apple School Manager cihazı açıldığında, Intune yönetimine kaydedilir. Cihaz etkinleştirilmişse ve kullanımdaysa, cihazda fabrika sıfırlaması yapılmadıkça profil uygulanamaz.
