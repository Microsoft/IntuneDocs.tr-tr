---
title: "iOS cihazları için Apple School Manager Programı kaydını ayarlama"
titleSuffix: Intune on Azure
description: "Intune ile şirkete ait iOS cihazları için Apple School Manager Programı kaydını ayarlamayı öğrenin\""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7079a22afc04b5674eb8f12a2833961e86939a28
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/03/2017
---
# <a name="enable-ios-device-enrollment-with-apple-school-manager"></a>Apple School Manager ile iOS cihaz kaydını etkinleştirme

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Bu konu, [Apple School Manager](https://school.apple.com/) programı aracılığıyla satın alınan cihazlarda BT yöneticilerinin iOS cihaz kaydını etkinleştirmesine yardımcı olur. Microsoft Intune, Apple School Manager cihazlarını yönetime kaydeden bir kayıt profilini “uzaktan” dağıtabilir. Yöneticinin yönetilen cihazlara dokunması bile gerekmez. Kayıt profili, Kurulum Yardımcısı seçenekleri dahil olmak üzere kayıt sırasında cihazlara uygulanan yönetim seçeneklerini içerir.

**Apple School Manager Kayıt adımları**
1. [Apple School Manager belirteci alma ve cihaz atama](#get-the-apple-token-and-assign-devices)
2. [Kayıt profili oluşturma](#create-an-apple-enrollment-profile)
3. [Okul Veri Eşitlemeye bağlanma](#connect-school-data-sync) (isteğe bağlı)
4. [Apple School Manager ile yönetilen cihazları eşitleme](#sync-managed-devices)
5. [Cihazlara Apple School Manager profili atama](#assign-a-profile-to-devices)
6. [Cihazları kullanıcılara dağıtma](#distribute-devices-to-users)

>[!NOTE]
>Apple School Manager kaydı, [Apple DEP](device-enrollment-program-enroll-ios.md) veya [cihaz kayıt yöneticisi](device-enrollment-manager-enroll.md) ile kullanılamaz.

## <a name="get-the-apple-token-and-assign-devices"></a>Apple belirteci alma ve cihaz atama

Şirkete ait iOS cihazlarını Apple School Manager’a kaydedebilmek için Apple’dan bir belirteç (.p7m) dosyasına ihtiyacınız vardır. Bu belirteç, Intune’un Apple School Manager’a katılan cihazlara ait bilgileri eşitlemesini sağlar. Ayrıca Intune'un kayıt profilini Apple'a yüklemesine ve cihazları bu profillere atamasına izin verir. Apple portalındayken yönetilecek cihaz seri numaralarını da atayabilirsiniz.

**Önkoşullar**
- [Apple MDM Anında İletme sertifikası](apple-mdm-push-certificate-get.md)
- [Apple Okul Yönetimi](http://school.apple.com)’ne kaydolma

**1. Adım. Bir Apple belirteci oluşturmak için gereken Intune ortak anahtar sertifikasını indirin.**<br>
1. Azure [Intune portalında](https://aka.ms/intuneportal), **Cihaz kaydı**'nı, ardından **Kayıt programı belirteci**’ni seçin.
2. **Kayıt programı belirteci** dikey penceresinde, şifreleme dosyasını (.pem) indirmek ve yerel olarak kaydetmek için **Ortak anahtar sertifikanızı indirin**’i seçin. .pem dosyası Apple School Manager portalından güven ilişkisi sertifikası istemek için kullanılır.

**2. Adım. Bir belirteç indirin ve cihaz atayın.**<br>
**Apple School Manager aracılığıyla belirteç oluşturma**'yı seçin ve şirket Apple kimliğinizle oturum açın. Apple School Manager belirtecinizi yenilemek için bu Apple kimliğini kullanabilirsiniz.

   1.  [Apple School Manager portalında](https://school.apple.com), **MDM Sunucuları**’na gidin ve **MDM Sunucusu Ekle**’yi (sağ üstte) seçin.
   2.  **MDM Sunucusu Adını** girin. Sunucu adı, mobil cihaz yönetimi (MDM) sunucusunu tanımlarken kullanmanız içindir. Microsoft Intune sunucusunun adı veya URL'si değildir.
   3.  Apple portalında **Dosyayı karşıya yükle...**’yi seçin ve .pem dosyasına giderek **MDM Sunucusunu Kaydet**’i (sağ alt köşede) seçin.
   4.  **Belirteci Al**’ı seçin ve ardından sunucu belirtecini (.p7m) bilgisayarınıza indirin.
   5. **Cihaz Atamaları**’na gidin ve **Cihaz Seç** işlemini **Seri Numaraları**, **Sipariş Numarası**’nı elle girerek veya **CSV Dosyasını Karşıya Yükle** ile yapın.
   6.   **Sunucuya Ata** eylemini seçip oluşturduğunuz **MDM Sunucusunu** seçin.
   7. **Cihaz Seçme** işleminin nasıl olacağını belirtin ve daha sonra cihaza ait bilgileri ve ayrıntıları sağlayın.
   8. **Sunucuya Ata**'yı ve Microsoft Intune için belirtilen &lt;ServerName&gt; öğesini belirleyip **Tamam**'ı seçin.

**3. Adım. Apple School Manager belirtecinizi oluşturmak için kullanılan Apple kimliğini girin.**<br>Bu kimlik, Apple School Manager belirtecinizi yenilemek için kullanılır ve gelecekte başvurulmak üzere depolanır.

**4. Adım. Belirtecinizi bulun ve yükleyin.**<br>
Sertifika (.p7m) dosyasına gidin, **Aç**’ı ve sonra da **Karşıya Yükle**’yi seçin. Intune, Apple School Manager cihazlarınızı Apple’dan otomatik olarak eşitler.

## <a name="create-an-apple-enrollment-profile"></a>Apple kayıt profili oluşturma
Bir cihaz kayıt profili, kayıt sırasında bir grup cihaza uygulanan ayarları tanımlar.

1. Intune portalında **Cihaz kaydı**'nı, ardından **Apple Kaydı**'nı seçin.
2. **Kayıt Programı**'nın altından **Kayıt Programı Profilleri**'ni seçin.
3. **Kayıt Programı Profilleri** dikey penceresinde **Oluştur**'u seçin.
4. **Kayıt Profili Oluştur** dikey penceresinde, Intune portalında görüntülenen profil için bir **Ad** ve **Açıklama** girin.
5. **Kullanıcı Benzeşimi** için, bu profile sahip cihazların kullanıcı benzeşimiyle mi yoksa kullanıcı benzeşimi olmadan mı kaydedileceğini seçin.

 - **Kullanıcı benzeşimi ile kaydetme** - Kurulum sırasında cihazı bir kullanıcıyla birleştirir.

 >[!NOTE]
 >Çok faktörlü kimlik doğrulaması (MFA), kullanıcı benzeşimi özellikli Apple School Manager cihazlarda kayıt sırasında çalışmaz. Kayıttan sonra MFA bu cihazlar üzerinde beklendiği gibi çalışır.

  Apple School Manager’ın Paylaşılan iPad modu, kullanıcının kullanıcı benzeşimi olmadan kaydolmasını gerektirir.

 >[!NOTE]
    >Kullanıcı benzeşimi ile Apple School Manager’ın kullanıcı belirteci istemesine izin vermek için [WS-Trust 1.3 Kullanıcı Adı/Karma uç nokta](https://technet.microsoft.com/library/adfs2-help-endpoints) gerekir. [WS-Trust 1.3 hakkında daha fazla bilgi edinin](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

 - **Kullanıcı benzeşimi olmadan kaydet** - Cihaz bir kullanıcıya bağlı değildir. Bu ilişkiyi, yerel kullanıcı verilerine erişmeden görevleri yerine getiren cihazlar için kullanın. Kullanıcı benzeşimi gerektiren uygulamalar (iş kolu uygulamalarını yüklemek için kullanılan Şirket Portalı uygulaması da dahil) çalışmaz.

6. **Cihaz Yönetimi Ayarları**’nı seçin. Bu öğeler etkinleştirme sırasında ayarlanır ve bunları değiştirmek için Fabrika sıfırlaması gerekir. aşağıdaki profil ayarlarını yapılandırın ve ardından **Kaydet**’i seçin:

    - **Denetimli** - Daha fazla yönetim seçeneğini etkinleştiren ve varsayılan olarak Etkinleştirme Kilidi’ni devre dışı bırakan yönetim modu. Onay kutusunu boş bırakırsanız, sınırlı yönetim özelliklerine sahip olursunuz.

    - **Kilitli kayıt** - (Yönetim Modu = Denetimli seçimini gerektirir) Yönetim profilini kaldırmaya izin verebilecek iOS ayarlarını devre dışı bırakır. Onay kutusunu boş bırakırsanız, yönetim profilinin Ayarlar menüsünden kaldırılmasına izin verir.

  - **Paylaşılan iPad** - (**Kullanıcı Benzeşimi olmadan Kaydolma** ve **Denetimli** mod gerektirir.) Birden çok kullanıcının yönetilen Apple kimliği kullanarak kayıtlı iPad’lerde oturum açmasına izin verir. Yönetilen Apple kimlikleri Apple School Manager portalında oluşturulur.

  >[!NOTE]
  >**Kullanıcı Benzeşimi** özelliği **Kullanıcı benzeşimli** olarak ayarlıysa veya **Denetimli** modu **Kapalı** olarak belirtildiyse,  bu kayıt profili için paylaşılan iPad modu devre dışıdır.

  - **Önbelleğe Alınan En Fazla Kullanıcı** - (**Paylaşılan iPad** = **Evet** gerektirir) Her kullanıcı için cihazda bir bölüm oluşturur. Önerilen değer bir süre boyunca cihazı kullanması muhtemel öğrenci sayısıdır. Örneğin, hafta boyunca cihazı düzenli olarak altı öğrenci kullanıyorsa, bu sayıyı altı olarak ayarlayın.  

    - **Eşleştirmeye İzin Ver** - iOS cihazlarının bilgisayarlarla eşitlenip eşitlenemeyeceğini belirtir. **Sertifikaya göre Apple Configurator’a izin ver**’i seçerseniz, **Apple Configurator Sertifikaları**’nın altında bir sertifika seçmeniz gerekir.

    - **Apple Configurator Sertifikaları** - **Eşleştirmeye İzin Ver**’in altında **Sertifikaya göre Apple Configurator’a izin ver**’i seçtiyseniz, içeri aktarılacak bir Apple Configurator Sertifikası seçin.

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

8. Profil ayarlarını kaydetmek için, **Kayıt Profili Oluştur** dikey penceresinde **Oluştur**’u seçin.

## <a name="connect-school-data-sync"></a>Okul Veri Eşitlemeye bağlanma
(İsteğe bağlı) Apple School Manager, sınıf ad listesi verilerini Microsoft School Data Sync (SDS) kullanarak Azure Active Directory’ye (AD) eşitlemeyi destekler. Okul verilerini eşitlemek üzere SDS kullanmak için aşağıdaki adımları tamamlayın.

1. **Kayıt Programı Belirteci** dikey penceresinde mavi bilgi başlığını veya **SDS’ye Bağlan**’ı seçin.
2. **Microsoft Okul Veri Eşitlemesinin bu belirteci kullanmasına izin ver** ayarını **İzin ver** olarak ayarlayın. Bu ayar, Intune’un Office 365'teki SDS’ye bağlanmasını sağlar.
3. Apple School Manager ve Azure AD arasında bağlantıyı etkinleştirmek için **Microsoft School Data Sync’i Ayarla**’yı seçin. [Okul Veri Eşitlemesini ayarlama](https://support.office.com/article/Install-the-School-Data-Sync-Toolkit-8e27426c-8c46-416e-b0df-c29b5f3f62e1) hakkında daha fazla bilgi edinin.
4. Kaydedip devam etmek için **Tamam**'a tıklayın.

## <a name="sync-managed-devices"></a>Yönetilen cihazları eşitleme
Artık Intune’a Apple School Manager cihazlarınızı yönetme izni verildiğine göre, yönetilen cihazlarınızı Intune portalında görmek için Intune’u Apple School Manager hizmetiyle eşitleyebilirsiniz.

1. Intune portalında **Cihaz kaydı**'nı, ardından **Apple Kaydı**'nı seçin.
2. **Kayıt Programı Cihazları** altında **Eşitle**’yi seçin. İlerleme çubuğu, yeniden Eşitleme istemeden önce beklemeniz gereken süreyi gösterir.

    Intune, Apple’ın kabul edilebilir trafik koşullarına uymak için aşağıdaki kısıtlamaları getirir:
     -  Tam eşitleme en sık yedi günde bir çalıştırılabilir. Intune tam eşitleme sırasında, Apple’ın Intune’a atadığı her seri numarasını, bu numaranın daha önceden eşitlenmiş olup olmamasına bakılmaksızın yeniler. Önceki tam eşitlemenin üzerinden yedi gün geçmeden bir tam eşitleme girişiminde bulunulursa, Intune yalnızca henüz Intune’da listelenmeyen seri numaralarını yeniler.
     -  Herhangi bir eşitleme isteğinin tamamlanması için 15 dakika verilir. Bu süre boyunca veya istek başarılı olana kadar **Eşitle** düğmesi devre dışı bırakılır.

>[!NOTE]
>Apple School Manager seri numaralarını **Kayıt Programı Cihazları** dikey penceresinden de profillere atayabilirsiniz.

## <a name="assign-a-profile-to-devices"></a>Cihazlara profil atama
Intune tarafından yönetilen Apple School Manager cihazları kaydedilmeden önce bu cihazlara bir kayıt profili atanmalıdır.

1. Intune portalında, **Cihaz kaydı** > **Apple Kaydı**'nı, ardından **Kayıt Program Profilleri**'ni seçin.
2. **Kayıt Programı Profilleri** listesinden cihazlara atamak istediğiniz profili ve ardından **Cihaz Atamaları**'nı seçin
3. **Ata**’yı ve ardından bu profile atamak istediğiniz Apple School Manager cihazlarını seçin. Kullanılabilir cihazları görüntülemek için filtreleyebilirsiniz:
  - **atanmayanlar**
  - **tümü**
  - **&lt;Apple School Manager profil adı&gt;**
4. Atamak istediğiniz cihazları seçin. Üstteki onay kutusu 1000’e kadar listelenen cihazı seçer. **Ata**’ya tıklayın. 1000 taneden fazla cihazı kaydetmek için tüm cihazlara bir kayıt profili atanana kadar atama adımlarını yineleyin.

## <a name="distribute-devices-to-users"></a>Cihazları kullanıcılara dağıtma

Şirkete ait cihazlarınızı artık kullanıcılara dağıtabilirsiniz. Bir iOS Apple School Manager cihazı açıldığında, Intune yönetimine kaydedilir. Cihaz etkinleştirilmişse ve kullanımdaysa, cihazda fabrika sıfırlaması yapılmadıkça profil uygulanamaz.

### <a name="how-users-install-and-use-the-company-portal-on-their-devices"></a>Kullanıcıların cihazlarında Şirket Portalı’nı yüklemesi ve kullanması

Kullanıcı benzeşimi ile yapılandırılmış cihazlar, uygulama indirmek ve cihaz yönetmek için Şirket Portalı’nı yükleyip çalıştırabilir. Kullanıcılar, cihazlarını aldıktan sonra Kurulum Yardımcısı’nı çalıştırmalı ve Şirket Portalı uygulamasını yüklemelidir.
