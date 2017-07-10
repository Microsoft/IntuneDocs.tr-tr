---
title: "iOS cihazları için Apple School Manager Programı kaydını ayarlama"
titleSuffix: Intune on Azure
description: "Intune ile şirkete ait iOS cihazları için Apple School Manager Programı kaydını ayarlamayı öğrenin\""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 73556209c88759ffe0747d9927cbcbb49600e0c0
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="enable-ios-device-enrollment-with-apple-school-manager"></a>Apple School Manager ile iOS cihaz kaydını etkinleştirme

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Bu konu, BT yöneticilerinin, [Apple School Manager (ASM)](https://school.apple.com/) aracılığıyla satın alınan cihazlar için iOS cihaz kaydını etkinleştirmesine yardımcı olur. Microsoft Intune, ASM cihazlarını yönetime kaydeden bir kayıt profilini "uzaktan" dağıtabilir. Yöneticinin yönetilen cihazlara dokunması bile gerekmez. Bir ASM profili, kayıt sırasında cihazlara uygulanan Kurulum Yardımcısı seçenekleri dahil yönetim seçeneklerini içerir.

**ASM Kaydı adımları**
1. [ASM belirteci alma ve cihaz atama](#get-the-asm-token-and-assign-devices)
2. [Kayıt profili oluşturma](#create-an-apple-enrollment-profile)
3. [Okul Veri Eşitlemeye bağlanma](#connect-school-data-sync) (isteğe bağlı)
4. [Yönetilen ASM cihazlarını eşitleme](#sync-asm-managed-devices)
5. [ASM profilini cihazlara atama](#assign-an-asm-profile-to-devices)
6. [Cihazları kullanıcılara dağıtma](#distribute-devices-to-users)

>[!NOTE]
>ASM kaydı Apple [Cihaz Kayıt Programı (DEP)](device-enrollment-program-enroll-ios.md) veya Intune [cihaz kayıt yöneticisi](device-enrollment-manager-enroll.md) hesabı ile kullanılamaz.

## <a name="get-the-apple-asm-token-and-assign-devices"></a>Apple ASM belirteci alma ve cihaz atama

Şirkete ait iOS cihazlarını Apple School Manager’a (ASM) kaydedebilmeniz için Apple’dan bir ASM belirteci (.p7m) dosyasına ihtiyacınız vardır. Bu belirteç Intune'un ASM’ye katılan cihazlar hakkındaki bilgileri eşitlemesini sağlar. Ayrıca Intune'un kayıt profilini Apple'a yüklemesine ve cihazları bu profillere atamasına izin verir. Apple portalındayken yönetilecek cihaz seri numaralarını da atayabilirsiniz.

**Önkoşullar**
- [Apple MDM Anında İletme sertifikası](apple-mdm-push-certificate-get.md)
- [Apple Okul Yönetimi](http://school.apple.com)’ne kaydolma

**1. Adım. Apple ASM belirteci oluşturmak için gereken Intune ortak anahtar sertifikasını indirin.**<br>
1. Azure [Intune portalında](https://aka.ms/intuneportal), **Cihaz kaydı**'nı, ardından **Kayıt programı belirteci**’ni seçin.
2. **Kayıt programı belirteci** dikey penceresinde, şifreleme dosyasını (.pem) indirmek ve yerel olarak kaydetmek için **Ortak anahtar sertifikanızı indirin**’i seçin. .pem dosyası Apple School Manager portalından güven ilişkisi sertifikası istemek için kullanılır.

**2. Adım. ASM belirteci indirme ve cihaz atama.**<br>
**Apple School Manager aracılığıyla belirteç oluşturma**'yı seçin ve şirket Apple kimliğinizle oturum açın. ASM belirtecinizi yenilemek için bu Apple kimliğini kullanabilirsiniz.

   1.  [Apple School Manager portalında](https://school.apple.com), **MDM Sunucuları**’na gidin ve **MDM Sunucusu Ekle**’yi (sağ üstte) seçin.
   2.  **MDM Sunucusu Adını** girin. Sunucu adı, mobil cihaz yönetimi (MDM) sunucusunu tanımlarken kullanmanız içindir. Microsoft Intune sunucusunun adı veya URL'si değildir.
   3.  Apple portalında **Dosyayı karşıya yükle...**’yi seçin ve .pem dosyasına giderek **MDM Sunucusunu Kaydet**’i (sağ alt köşede) seçin.
   4.  **Belirteci Al**’ı seçin ve ardından sunucu belirtecini (.p7m) bilgisayarınıza indirin.
   5. **Cihaz Atamaları**’na gidin ve **Cihaz Seç** işlemini **Seri Numaraları**, **Sipariş Numarası**’nı elle girerek veya **CSV Dosyasını Karşıya Yükle** ile yapın.
   6.   **Sunucuya Ata** eylemini seçip oluşturduğunuz **MDM Sunucusunu** seçin.
   7. **Cihaz Seç** bölümünden cihaz seçim tercihinizi yapın, ardından cihaz bilgilerini sağlayın ve cihazın **Seri Numarası**, **Sipariş Numarası** bilgileriyle veya **CSV Dosyasını Karşıya Yükle** seçeneğiyle cihaz ayrıntılarını belirtin.
   8. **Sunucuya Ata**'yı ve Microsoft Intune için belirtilen &lt;ServerName&gt; öğesini belirleyip **Tamam**'ı seçin.

**3. Adım. ASM belirtecinizi oluşturmak için kullanılan Apple kimliğini girin.**<br>Bu kimlik Apple ASM belirtecinizi yenilemek için kullanılmalıdır ve gelecekte başvurulmak üzere depolanır.

**4. Adım. Belirtecinizi bulun ve yükleyin.**<br>
Sertifika (.p7m) dosyasına gidin, **Aç**’ı ve sonra da **Karşıya Yükle**’yi seçin. Intune, ASM cihazlarınızı otomatik olarak Apple’dan eşitler.

## <a name="create-an-apple-enrollment-profile"></a>Apple kayıt profili oluşturma
Bir cihaz kayıt profili, kayıt sırasında bir grup cihaza uygulanan ayarları tanımlar.

1. Intune portalında **Cihaz kaydı**'nı, ardından **Apple Kaydı**'nı seçin.
2. **Kayıt Programı**'nın altından **Kayıt Programı Profilleri**'ni seçin.
3. **Kayıt Programı Profilleri** dikey penceresinde **Oluştur**'u seçin.
4. **Kayıt Profili Oluştur** dikey penceresinde, Intune portalında görüntülenen profil için bir **Ad** ve **Açıklama** girin.
5. **Kullanıcı Benzeşimi** için, bu profile sahip cihazların kullanıcı benzeşimiyle mi yoksa kullanıcı benzeşimi olmadan mı kaydedileceğini seçin.

 - **Kullanıcı benzeşimiyle kaydet** - Cihaz ilk kurulum sırasında bir kullanıcıya bağlı olmalıdır. Böylece, cihazın şirket verilerine ve e-postalara erişmesine izin verilebilir. Kullanıcıların kendi yönetilen Apple kimliği ile oturum açtığı ASM ile yönetilen cihazlar için kullanıcı benzeşimini seçin.

 >[!NOTE]
 >Multifactor authentication (MFA) kullanıcı benzeşimi özellikli ASM cihazlarında kayıt sırasında çalışmaz. Kayıttan sonra MFA bu cihazlar üzerinde beklendiği gibi çalışır.

  Apple School Manager’ın Paylaşılan iPad modu, kullanıcının kullanıcı benzeşimi ile kaydolmasını gerektirir.

 >[!NOTE]
    >Kullanıcı benzeşimi ile ASM'in kullanıcı belirteci istemesini etkinleştirmek için [WS-Trust 1.3 Kullanıcı Adı/Karma uç nokta](https://technet.microsoft.com/library/adfs2-help-endpoints) gerekir. [WS-Trust 1.3 hakkında daha fazla bilgi edinin](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

 - **Kullanıcı benzeşimi olmadan kaydet** - Cihaz bir kullanıcıya bağlı değildir. Bu ilişkiyi, yerel kullanıcı verilerine erişmeden görevleri yerine getiren cihazlar için kullanın. Kullanıcı benzeşimi gerektiren uygulamalar (iş kolu uygulamalarını yüklemek için kullanılan Şirket Portalı uygulaması da dahil) çalışmaz.

6. **Cihaz Yönetimi Ayarları**’nı seçin. Bu öğeler etkinleştirme sırasında ayarlanır ve bunları değiştirmek için Fabrika sıfırlaması gerekir. aşağıdaki profil ayarlarını yapılandırın ve ardından **Kaydet**’i seçin:

    - **Denetimli** - Daha fazla yönetim seçeneğini etkinleştiren ve varsayılan olarak Etkinleştirme Kilidi’ni devre dışı bırakan yönetim modu. Onay kutusunu boş bırakırsanız, sınırlı yönetim özelliklerine sahip olursunuz.

    - **Kilitli kayıt** - (Yönetim Modu = Denetimli seçimini gerektirir) Yönetim profilini kaldırmaya izin verebilecek iOS ayarlarını devre dışı bırakır. Onay kutusunu boş bırakırsanız, yönetim profilinin Ayarlar menüsünden kaldırılmasına izin verir.

  - **Paylaşılan iPad** - (**Kullanıcı Benzeşimi ile Kaydolma** ve **Denetimli** mod gerektirir.) Birden çok kullanıcının yönetilen Apple kimliği kullanarak kayıtlı iPad’lerde oturum açmasına izin verir. Yönetilen Apple kimlikleri Apple School Manager portalında oluşturulur.

  >[!NOTE]
  >**Paylaşılan iPad** modu bir profilde etkinleştirilmişse ve ardından **Kullanıcı benzeşimi** veya **denetimli** mod **kapalı** olarak ayarlanmışsa, paylaşılan iPad modu kayıt profili için devre dışı bırakılır.

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
(İsteğe bağlı) ASM sınıf ad listesi verilerini Microsoft Okul Veri Eşitleme (SDS) kullanarak Azure Active Directory’ye (AD) eşitlemeyi destekler. Okul verilerini eşitlemek üzere SDS kullanmak için aşağıdaki adımları tamamlayın.

1. **Kayıt Programı Belirteci** dikey penceresinde mavi bilgi başlığını veya **SDS’ye Bağlan**’ı seçin.
2. **Microsoft Okul Veri Eşitlemesinin bu belirteci kullanmasına izin ver** ayarını **İzin ver** olarak ayarlayın. Bu ayar, Intune’un Office 365'teki SDS’ye bağlanmasını sağlar.
3. ASM ve Azure AD arasında bir bağlantı etkinleştirmek için **Microsoft Okul Veri Eşitlemesini Ayarla**’yı seçin. [Okul Veri Eşitlemesini ayarlama](https://support.office.com/article/Install-the-School-Data-Sync-Toolkit-8e27426c-8c46-416e-b0df-c29b5f3f62e1) hakkında daha fazla bilgi edinin.
4. Kaydedip devam etmek için **Tamam**'a tıklayın.

## <a name="sync-asm-managed-devices"></a>Yönetilen ASM cihazlarını eşitleme
Artık Intune’a ASM cihazlarınızı yönetme izni verildiğine göre, yönetilen cihazlarınızı Intune portalında görmek için Intune’u ASM hizmetiyle eşitleyebilirsiniz.

1. Intune portalında **Cihaz kaydı**'nı, ardından **Apple Kaydı**'nı seçin.
2. **Kayıt Programı Cihazları** altında **Eşitle**’yi seçin. İlerleme çubuğu, yeniden Eşitleme istemeden önce beklemeniz gereken süreyi gösterir.

    Apple’ın kabul edilebilir ASM trafiği koşullarına uymak için, Intune aşağıdaki kısıtlamaları getirir:
     -  Tam ASM eşitlemesi en fazla yedi günde bir çalıştırılabilir. Intune tam eşitleme sırasında, Apple’ın Intune’a atadığı her seri numarasını, bu numaranın daha önceden eşitlenmiş olup olmamasına bakılmaksızın yeniler. Önceki tam eşitlemenin üzerinden yedi gün geçmeden bir tam eşitleme girişiminde bulunulursa, Intune yalnızca henüz Intune’da listelenmeyen seri numaralarını yeniler.
     -  Herhangi bir eşitleme isteğinin tamamlanması için 15 dakika verilir. Bu süre boyunca veya istek başarılı olana kadar **Eşitle** düğmesi devre dışı bırakılır.

>[!NOTE]
>ASM seri numaralarını **Kayıt Programı Cihazları** dikey penceresinden profillere de atayabilirsiniz.

## <a name="assign-an-asm-profile-to-devices"></a>Cihazlara bir ASM profili atama
Kaydedilmeden önce Intune tarafından yönetilen ASM cihazlarına bir ASM profili atanmalıdır.

1. Intune portalında, **Cihaz kaydı** > **Apple Kaydı**'nı, ardından **Kayıt Program Profilleri**'ni seçin.
2. **Kayıt Programı Profilleri** listesinden cihazlara atamak istediğiniz profili ve ardından **Cihaz Atamaları**'nı seçin
3. **Ata**’yı ve ardından bu profile atamak istediğiniz ASM cihazlarını seçin. ASM kullanılabilir cihazlarını görüntülemek için filtreleyebilirsiniz:
  - **atanmayanlar**
  - **tümü**
  - **&lt;ASM profil adı&gt;**
4. Atamak istediğiniz cihazları seçin. Üstteki onay kutusu 1000’e kadar listelenen cihazı seçer. **Ata**’ya tıklayın. 1000 taneden fazla cihazı kaydetmek için, tüm cihazlara bir ASM profili atanana dek atama adımlarını yineleyin.

## <a name="distribute-devices-to-users"></a>Cihazları kullanıcılara dağıtma

Şirkete ait cihazlarınızı artık kullanıcılara dağıtabilirsiniz. Bir iOS ASM cihazı açıldığında Intune tarafından yönetim için kaydedilir. Cihaz etkinleştirilmişse ve kullanımdaysa, cihazda fabrika sıfırlaması yapılmadıkça profil uygulanamaz.

### <a name="how-users-install-and-use-the-company-portal-on-their-devices"></a>Kullanıcıların cihazlarında Şirket Portalı’nı yüklemesi ve kullanması

Kullanıcı benzeşimi ile yapılandırılmış cihazlar, uygulama indirmek ve cihaz yönetmek için Şirket Portalı’nı yükleyip çalıştırabilir. Kullanıcılar, cihazlarını aldıktan sonra Kurulum Yardımcısı’nı çalıştırmalı ve Şirket Portalı uygulamasını yüklemelidir.
