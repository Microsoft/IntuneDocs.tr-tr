---
title: "iOS cihazlarını kaydetme - Cihaz Kayıt Programı"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Cihaz Kayıt Programı’nı kullanarak şirkete ait iOS cihazlarını kaydetmeyi öğrenin."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 04/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 5144b9e7c17a3323667b9ca68cb47829d69866c3
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---

# <a name="enroll-ios-devices-using-device-enrollment-program"></a>Cihaz Kayıt Programı’nı kullanarak iOS cihazlarını kaydetme

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Bu konu, BT yöneticilerine şirketin sahip olduğu ve [Apple Cihaz Kayıt Programı (DEP)](https://deploy.apple.com) aracılığıyla satın alınan iOS cihazlarının kaydedilmesi konusunda yardımcı olmaktadır. Microsoft Intune, DEP kaydı gerçekleştiren bir kayıt profilini kablosuz olarak dağıtabilir ve bu sayede yöneticinin, yönetilen cihazlara dokunmasına gerek kalmaz. DEP profili, kayıt sırasında cihazlara uygulamak istediğiniz yönetim ayarlarını içerir. Kayıt paketi, cihaz için kurulum yardımcısı seçeneklerini içerebilir.

>[!NOTE]
>DEP kaydı, [cihaz kayıt yöneticisiyle](device-enrollment-manager-enroll.md) birlikte kullanılamaz.
>Ayrıca, kullanıcıların Şirket Portalı uygulamasını kullanarak iOS cihazlarını kaydetmesi ve bu cihazların seri numaralarının daha sonra içeri aktarılıp bunlara bir DEP profili atanması halinde cihazın Intune kaydı kaldırılır.

**DEP Kaydı adımları**
1. [Bir Apple DEP belirteci alma](#get-the-apple-dep-certificate)
2. [DEP profili oluşturma](#create-an-apple-dep-profile)
3. [Intune sunucunuza Apple DEP seri numaraları atama](#assign-apple-dep-serial-numbers-to-your-mdm-server)
4. [DEP ile yönetilen cihazları eşitleme](#synchronize-dep-managed-devices)
5. [Cihazlara DEP profili atama](#assign-a-dep-profile-to-devices)
6. [Cihazları kullanıcılara dağıtma](#distribute-devices-to-users)

## <a name="get-the-apple-dep-certificate"></a>Apple DEP sertifikasını alma
Şirketin sahibi olduğu iOS cihazlarını Apple'ın Aygıt Kayıt Programı'na (DEP) kaydedebilmeniz için bir Apple DEP sertifikası dosyasına (.p7m) ihtiyacınız vardır. Bu belirteç Intune'un şirketinize ait olup DEP'e katılan cihazlar hakkındaki bilgileri eşitlemesini sağlar. Ayrıca Intune'un kayıt profilini Apple'a yüklemesine ve cihazları bu profillere atamasına izin verir.

Şirkete ait iOS cihazlarının DEP ile yönetilmesi için kurumunuzun Apple DEP'e katılması ve cihazları bu program aracılığıyla edinmesi gerekir. Bu işlemin ayrıntıları şurada bulunabilir: https://deploy.apple.com. Programın sağladığı avantajlar arasında, her cihazı bir USB kablosu ile bilgisayara bağlamaya gerek bırakmayan kendiliğinden kurulum olanağı da vardır.

> [!NOTE]
> Intune kiracınız Intune klasik konsolundan Azure portalına geçirildiyse ve geçiş sırasında Intune yönetim konsolundan bir Apple DEP belirtecini sildiyseniz, bu DEP belirteci Intune hesabınıza geri yüklenmiş olabilir. DEP belirtecini Azure portalından tekrar silebilirsiniz.

**1. Adım. Apple DEP belirteci oluşturmak için gereken Intune ortak anahtar sertifikasını indirin.**<br>
1. Azure portalında **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin. Intune dikey penceresinde **Cihaz kaydı** > **Apple DEP Belirteci**'ni seçin.
2. Şifreleme dosyasını (.pem) indirmek ve yerel olarak kaydetmek için **Ortak anahtar sertifikanızı indirin** öğesini seçin. .pem dosyası Apple Cihaz Kayıt Programı portalından güven ilişkisi sertifikası istemek için kullanılır.

**2. Adım. İlgili Apple web sitesinden bir Apple DEP belirteci indirin.**<br>
[Apple Dağıtım Programları aracılığıyla DEP belirteci oluşturun](https://deploy.apple.com) öğesini seçin (https://deploy.apple.com) ve şirket Apple kimliğinizle oturum açın. DEP belirtecinizi yenilemek için de bu Apple kimliğini kullanabilirsiniz.

   1.  Apple [Cihaz Kayıt Programı Portalı](https://deploy.apple.com)'nda, **Cihaz Kayıt Programı** &gt; **Sunucuları Yönet**'e gidin ve **MDM Sunucusu Ekle**'ye tıklayın.
   2.  **MDM Sunucu Adı**'nı girin ve ardından **İleri**'yi seçin. Sunucu adı, mobil cihaz yönetimi (MDM) sunucusunu tanımlarken kullanmanız içindir. Microsoft Intune sunucusunun adı veya URL'si değildir.
   3.  **&lt;SunucuAdı&gt; Ekle** iletişim kutusu açılır. **Dosya Seç…** öğesini seçin .pem dosyasını karşıya yükleyin ve ardından **İleri**'yi seçin.
   4.  **&lt;SunucuAdı&gt; Ekle** iletişim kutusunda **Sunucu Belirteciniz** bağlantısı gösterilir. Sunucu belirteci (.p7m) dosyasını bilgisayarınıza indirin ve ardından **Bitti**'yi seçin.

**3. Adım. Apple DEP belirtecinizi oluşturmak için kullanılan Apple kimliğini girin. Bu kimlik Apple DEP belirtecinizi yenilemek için kullanılabilir.**

**4. Adım. Karşıya yüklenecek Apple DEP belirtecine gidin. Intune, DEP hesabınızı otomatik olarak eşitleyecektir.**<br>
Sertifika (.pem) dosyasına gidin, **Aç**’ı ve sonra da **Karşıya Yükle**’yi seçin. Anında iletme sertifikasıyla, Intune ilkeyi kayıtlı mobil cihazlara ileterek iOS cihazları kaydedebilir ve yönetebilir.

## <a name="create-an-apple-dep-profile"></a>Apple DEP profili oluşturma

Cihaz kayıt profili bir cihaz grubuna uygulanan ayarları tanımlar. Aşağıdaki adımlar, DEP kullanarak kaydedilmiş iOS cihazları için bir cihaz kayıt profilinin nasıl oluşturulacağını gösterir.

1. Azure portalında **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
2. Intune dikey penceresinde **Cihaz kaydetme**’yi ve ardından **Apple Kaydı**’nı seçin.
3. **Apple Cihaz Kayıt Programı (DEP) Ayarlarını Yönet**’in altında **DEP Profilleri**’ni seçin.
4. **Apple DEP Profilleri** dikey penceresinde **Oluştur**’u seçin.
5. **Kayıt Profili Oluştur** dikey penceresinde, profil için bir ad ve açıklama girin.
6. **Kullanıcı Benzeşimi** için, bu profile sahip cihazların kullanıcı benzeşimiyle mi yoksa kullanıcı benzeşimi olmadan mı kaydedileceğini seçin.

 - **Kullanıcı benzeşimiyle kaydet** - Cihaz ilk kurulum sırasında bir kullanıcıya bağlı olmalıdır. Böylece, cihazın şirket verilerine ve e-postalara erişmesine izin verilebilir. Kullanıcılara ait olan ve uygulamaları yükleme gibi hizmetler için şirket portalını kullanması gereken, DEP ile yönetilen cihazlarda kullanıcı benzeşimini seçin. Multifactor Authentication’ın (MFA) kullanıcı benzeşimi özellikli DEP cihazlarında kayıt sırasında çalışmayacağını unutmayın. Kayıttan sonra MFA bu cihazlar üzerinde beklendiği gibi çalışır. İlk kez oturum açarken parola değiştirmesi istenen yeni kullanıcılara, DEP cihazlarının kaydı sırasında istemde bulunulamaz. Ayrıca, parolalarının süresi dolmuş olan kullanıcılardan DEP kaydı sırasında parolalarını sıfırlamaları istenmez ve farklı bir cihazdan parolayı sıfırlamaları gerekir.

    >[!NOTE]
    >Kullanıcı benzeşimi ile DEP'in kullanıcı belirteci istemesini etkinleştirmek için [WS-Trust 1.3 Kullanıcı Adı/Karma uç nokta](https://technet.microsoft.com/en-us/library/adfs2-help-endpoints) gerekir. [WS-Trust 1.3 hakkında daha fazla bilgi edinin](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

 - **Kullanıcı benzeşimi olmadan kaydet** - Cihaz bir kullanıcıya bağlı değildir. Bu ilişkiyi, yerel kullanıcı verilerine erişmeden görevleri yerine getiren cihazlar için kullanın. Kullanıcı benzeşimi gerektiren uygulamalar (iş kolu uygulamalarını yüklemek için kullanılan Şirket Portalı uygulaması da dahil) çalışmaz.

7. **Cihaz Yönetim Ayarları**’nı seçin, aşağıdaki profil ayarlarını yapılandırın ve ardından **Kaydet**’i seçin:

    - **Denetimli** - Daha fazla yönetim seçeneğini etkinleştiren ve varsayılan olarak Etkinleştirme Kilidi’ni devre dışı bırakan yönetim modu. Onay kutusunu boş bırakırsanız, sınırlı yönetim özelliklerine sahip olursunuz.

    - **Kilitli kayıt** - (Yönetim Modu = Denetimli seçimini gerektirir) Yönetim profilini kaldırmaya izin verebilecek iOS ayarlarını devre dışı bırakır. Onay kutusunu boş bırakırsanız, yönetim profilinin Ayarlar menüsünden kaldırılmasına izin verir. Bu öğe etkinleştirme sırasında ayarlanır ve fabrika ayarlarına sıfırlamadan değiştirilemez.

    - **Eşleştirmeye İzin Ver** - iOS cihazlarının bilgisayarlarla eşitlenip eşitlenemeyeceğini belirtir. **Sertifikaya göre Apple Configurator’a izin ver**’i seçerseniz, **Apple Configurator Sertifikaları**’nın altında bir sertifika seçmeniz gerekir.

    - **Apple Configurator Sertifikaları** - **Eşleştirmeye İzin Ver**’in altında **Sertifikaya göre Apple Configurator’a izin ver**’i seçtiyseniz, içeri aktarılacak bir Apple Configurator Sertifikası seçin.

8. **Kurulum Yardımcısı Ayarları**’nı seçin, aşağıdaki profil ayarlarını yapılandırın ve ardından **Kaydet**’i seçin:

    - **Bölüm Adı** - Kullanıcı etkinleştirme sırasında **Yapılandırma Hakkında** öğesine dokunduğunda görüntülenir.

    - **Bölüm Telefonu** - Kullanıcı etkinleştirme sırasında Yardım Gerekli düğmesine tıkladığında görüntülenir.
    - **Kurulum Yardımcısı Seçenekleri** - Bu isteğe bağlı ayarlar daha sonra iOS **Ayarlar** menüsünden ayarlanabilir.
        - **Geçiş kodu** - Etkinleştirme sırasında geçiş kodu ister. Cihaz güvenlik altına alınmayacaksa veya başka bir yolla erişim denetimi sağlanmamışsa (cihazı tek uygulamayla sınırlandıran bilgi noktası modu), her zaman geçiş kodu gerektirir.
        - **Konum Hizmetleri** - Etkinleştirilirse, Kurulum Yardımcısı etkinleştirme sırasında hizmeti sorar
        - **Geri Yükle** - Etkinleştirilirse, Kurulum Yardımcısı etkinleştirme sırasında iCloud yedeklemesini sorar
        - **Apple kimliği** - Etkinleştirilirse, Intune kimlik girilmeden bir uygulama yüklemeyi denediğinde iOS kullanıcılardan Apple kimliği ister. Intune tarafından yüklenenler de dahil olmak üzere, iOS Uygulama Mağazası uygulamalarını indirmek için Apple Kimliği gerekir.
        - **Hüküm ve Koşullar** - Etkinleştirilirse, Kurulum Yardımcısı etkinleştirme sırasında kullanıcılardan Apple’ın hüküm ve koşullarını kabul etmelerini ister
        - **Touch ID** - Etkinleştirilirse, Kurulum Yardımcısı etkinleştirme sırasında bu hizmeti sorar
        - **Apple Pay** - Etkinleştirilirse, Kurulum Yardımcısı etkinleştirme sırasında bu hizmeti sorar
        - **Zoom** - Etkinleştirilirse, Kurulum Yardımcısı etkinleştirme sırasında bu hizmeti sorar
        - **Siri** - Etkinleştirilirse, Kurulum Yardımcısı etkinleştirme sırasında bu hizmeti sorar
        - **Tanılama Verileri** - Etkinleştirilirse, Kurulum Yardımcısı etkinleştirme sırasında bu hizmeti sorar

9. Profil ayarlarını kaydetmek için, **Kayıt Profili Oluştur** dikey penceresinde **Oluştur**’u seçin.

## <a name="assign-apple-dep-serial-numbers-to-your-mdm-server"></a>MDM sunucunuza Apple DEP seri numaraları atama
Intune’un cihazları yönetmesine izin vermek için, Apple DEP web portalında Intune MDM sunucunuza cihaz seri numaraları atanmalıdır.

1. [Cihaz Kayıt Programı Portalı](https://deploy.apple.com)’na (https://deploy.apple.com) gidin ve şirketinizin Apple kimliğiyle oturum açın.

2. **Dağıtım Programı** &gt; **Aygıt Kayıt Programı** &gt; **Cihazları Yönet**’e gidin.

3. **Cihaz Seç** bölümünden cihaz seçim tercihinizi yapın, ardından cihaz bilgilerini sağlayın ve cihazın **Seri Numarası**, **Sipariş Numarası** bilgileriyle veya **CSV Dosyasını Karşıya Yükle** seçeneğiyle cihaz ayrıntılarını belirtin.

4. **Sunucuya Ata**'yı ve Microsoft Intune için belirtilen &lt;ServerName&gt; öğesini belirleyip **Tamam**'ı seçin.

## <a name="synchronize-dep-managed-devices"></a>DEP ile yönetilen cihazları eşitleme
Artık Intune’a DEP cihazlarınızı yönetme izni verildiğine göre, yönetilen cihazlarınızı Intune portalında görmek için Intune’u DEP hizmetiyle eşitleyebilirsiniz.

1. Azure portalında **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.

2. Azure Portal’ın Intune dikey penceresinde **Cihaz kaydı**’nı ve ardından **Apple Kaydı**’nı seçin.

3. **Apple Cihaz Kayıt Programı (DEP) Ayarlarını Yönet**’in altında **DEP Seri Numaraları**’nı seçin.

4. **Apple DEP Seri Numaraları** dikey penceresinde **Eşitle**’yi seçin.

5. **Eşitle** dikey penceresinde **Eşitleme İste**’yi seçin. İlerleme çubuğu, yeniden Eşitleme istemeden önce beklemeniz gereken süreyi gösterir.

    Apple’ın kabul edilebilir DEP trafiği koşullarına uymak için, Intune aşağıdaki kısıtlamaları getirir:
     -    Tam DEP eşitlemesi en fazla yedi günde bir çalıştırılabilir. Intune tam eşitleme sırasında, Apple’ın Intune’a atadığı her seri numarasını, bu numaranın daha önceden eşitlenmiş olup olmamasına bakılmaksızın yeniler. Önceki tam eşitlemenin üzerinden yedi gün geçmeden bir tam eşitleme girişiminde bulunulursa, Intune yalnızca henüz Intune’da listelenmeyen seri numaralarını yeniler.
     -    Herhangi bir eşitleme isteğinin tamamlanması için 10 dakika verilir. Bu süre boyunca veya istek başarılı olana kadar **Eşitle** düğmesi devre dışı bırakılır.

>[!NOTE]
>Ayrıca, **Apple DEP Seri Numaraları** dikey penceresinde profillere DEP seri numaraları da atayabilirsiniz.

## <a name="assign-a-dep-profile-to-devices"></a>Cihazlara DEP profili atama
Kaydedilmeden önce Intune tarafından yönetilen DEP cihazlarına bir DEP profili atanmalıdır.

1. Azure portalında **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.

2. Azure portalının Intune dikey penceresinde, **Cihaz kaydı** > **Apple Kaydı**’nı, ardından **DEP profilleri**’ni seçin.

3. **Apple DEP Kayıt Profilleri** listesinden cihazlara atamak istediğiniz profili ve ardından **Cihaz Atamaları**’nı seçin

4. **Ata**’yı ve ardından bu profile atamak istediğiniz DEP cihazlarını seçin. DEP kullanılabilir cihazlarını görüntülemek için filtreleyebilirsiniz:
  - **atanmayanlar**
  - **tümü**
  - **&lt;DEP profil adı&gt;**

  ![Intune portalında DEP profili atamak için Ata düğmesinin ekran görüntüsü](media/dep-profile-assignment.png)

5. Atamak istediğiniz cihazları seçin. Sütunun üstündeki onay kutusu listelenen cihazlardan en çok 1000’ini seçer; sonra**Ata**’ya tıklayın. 1000 taneden fazla cihazı kaydetmek için, tüm cihazlara bir DEP profili atanana dek atama adımlarını yineleyin.

## <a name="distribute-devices-to-users"></a>Cihazları kullanıcılara dağıtma

Şirkete ait cihazlarınızı artık kullanıcılara dağıtabilirsiniz. Bir iOS DEP cihazı açıldığında, cihaz, yönetilmesi için Intune’a kaydedilir. Cihaz etkinleştirilmişse ve kullanımdaysa, cihazda fabrika sıfırlaması yapılmadıkça profil uygulanamaz.

Bkz. [Son kullanıcılarınızı Microsoft Intune hakkında bilgilendirme](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune). Son kullanıcılarınızı [iOS veya macOS cihazınızı Intune ile kullanma](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune) konusuna da yönlendirebilirsiniz. 

### <a name="how-users-install-and-use-the-company-portal-on-their-devices"></a>Kullanıcıların cihazlarında Şirket Portalı’nı yüklemesi ve kullanması

Kullanıcı benzeşimi ile yapılandırılmış cihazlar, uygulama indirmek ve cihaz yönetmek için Şirket Portalı’nı yükleyip çalıştırabilir. Kullanıcılar, cihazlarını aldıktan sonra Kurulum Yardımcısı’nı tamamlamak ve Şirket Portalı uygulamasını yüklemek için aşağıda açıklanan ek adımları tamamlamalıdır.

