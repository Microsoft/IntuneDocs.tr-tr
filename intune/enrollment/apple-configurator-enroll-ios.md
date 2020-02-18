---
title: iOS/ıpados cihaz kaydı-Apple Configurator-Kurulum Yardımcısı
titleSuffix: Microsoft Intune
description: Kurulum Yardımcısı 'Nı kullanarak şirkete ait iOS/ıpados cihazlarını kaydetmek için Apple Configurator 'ın nasıl kullanılacağını öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/04/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 671e4d76-0c61-11e8-ba89-0ed5f89f718b
ms.reviewer: tisilver
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8ccd41b6ebc9bdf62c1603e508cb881a1be62ee7
ms.sourcegitcommit: 51591b862d97904291af7aa53a6eb341b11a761e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/17/2020
ms.locfileid: "77415396"
---
# <a name="set-up-iosipados-device-enrollment-with-apple-configurator"></a>Apple Configurator ile iOS/ıpados cihaz kaydını ayarlama

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Intune, bir Mac bilgisayarda çalışan [Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344) 'ı kullanarak IOS/ıpados cihazlarının kaydedilmesini destekler. Apple Configurator ile kaydetme, kurumsal kayıt kurulumu için her iOS/ıpados cihazını USB ile bir Mac bilgisayara bağlamanız gerekir. Apple Configurator ile Intune'a cihazları iki yolla kaydedebilirsiniz:
- **Kurulum Yardımcısı kaydı** - Cihazı siler ve Kurulum Yardımcısı sırasında kayda hazırlar.
- **Doğrudan kayıt** -cihazı temizlemez ve IOS/ıpados ayarları aracılığıyla cihazı kaydeder. Bu yöntem, yalnızca **kullanıcı benzeşimi olmayan** cihazları destekler.

Apple Configurator kayıt yöntemleri [cihaz kaydı yöneticisi](device-enrollment-manager-enroll.md) ile birlikte kullanılamaz.

## <a name="prerequisites"></a>Önkoşullar

- İOS/ıpados cihazlarına fiziksel erişim
- [MDM yetkilisini ayarlama](../fundamentals/mdm-authority-set.md)
- [Apple MDM anında iletme sertifikası](apple-mdm-push-certificate-get.md)
- Cihaz seri numaraları (yalnızca Kurulum Yardımcısı kaydı)
- USB bağlantı kabloları
- [Apple Configurator 2.0](https://itunes.apple.com/app/apple-configurator-2/id1037126344) çalıştıran macOS bilgisayar

## <a name="create-an-apple-configurator-profile-for-devices"></a>Cihazlar için Apple Configurator profili oluşturma

Bir cihaz kayıt profili kayıt sırasında uygulanan ayarları tanımlar. Bu ayarlar yalnızca bir kez uygulanır. Apple Configurator ile iOS/ıpados cihazlarını kaydetmek üzere bir kayıt profili oluşturmak için bu adımları izleyin.

1. [Microsoft Endpoint Manager Yönetim Merkezi](https://go.microsoft.com/fwlink/?linkid=2109431)'nde **, > ** **IOS** > IOS **kaydı** > **Apple Configurator** > **profilleri** > **Oluştur**' u seçin.

    ![Apple Configurator için bir profil oluşturma](./media/apple-configurator-enroll-ios/apple-config-create-profile.png)

2. **Kayıt Profili Oluştur** altında yönetim amaçları doğrultusunda profil için bir **Ad** ve **Açıklama** girin. Kullanıcılar bu ayrıntıları göremez. Azure Active Directory’de dinamik bir grup oluşturmak için bu Ad alanını kullanabilirsiniz. enrollmentProfileName parametresini, bu kayıt profiliyle cihazlara atamak amacıyla tanımlamak için profil adını kullanın. Azure Active Directory dinamik grupları hakkında daha fazla bilgi edinin.

    ![Kullanıcı benzeşimi ile kaydet seçeneği belirlenmiş profil oluşturma ekranının ekran görüntüsü](./media/apple-configurator-enroll-ios/apple-configurator-profile-create.png)

3. **Kullanıcı Benzeşimi** için bu profile sahip cihazların atanan kullanıcıyla mı yoksa atanan kullanıcı olmadan mı kaydedilmesi gerektiğini seçin.

    - **Kullanıcı benzeşimi ile kaydetme** - Uygulamaları yükleme gibi hizmetler için Şirket Portalı’nı kullanmak isteyen kullanıcılara ait cihazlar için bu seçeneği seçin. Cihaz Kurulum Yardımcısı ile bir kullanıcıya bağlanmalıdır. Böylece, cihaz şirket verilerine ve e-postalara erişebilir. Yalnızca Kurulum Yardımcısı kaydı için desteklenir. Kullanıcı benzeşimi [WS-Trust 1.3 Kullanıcı adı/Karma uç noktası](https://technet.microsoft.com/library/adfs2-help-endpoints) gerektirir. [Daha fazla bilgi edinin](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

    - **Kullanıcı Benzeşimi Olmadan Kaydetme** - Tek bir kullanıcıyla bağlantılı olmayan cihazlar için bu seçeneği seçin. Yerel kullanıcı verilerine erişmeden görevleri yerine getiren cihazlar için bunu kullanın. Kullanıcı benzeşimi gerektiren uygulamalar (iş kolu uygulamalarını yüklemek için kullanılan Şirket Portalı uygulaması da dahil) çalışmaz. Doğrudan kayıt için gereklidir.

     > [!NOTE]
     > **Kullanıcı benzeşimi Ile kaydetme** seçildiğinde, cihazın Kaydolmakta olan cihazın ilk 24 saati Içinde kurulum yardımcısı olan bir kullanıcıyla ilişkili olduğundan emin olun. Aksi takdirde kayıt başarısız olabilir ve cihazı kaydetmek için bir fabrika sıfırlaması gerekecektir.

4. **Kullanıcı Benzeşimi ile Kaydet**’i seçerseniz, kullanıcıların Şirket Portalı yerine Apple Kurulum Yardımcısı ile kimlik doğrulamalarına izin verme seçeneğiniz olur.

    > [!NOTE]
    > Aşağıdakilerden herhangi birini yapmak istiyorsanız, **Apple Kurulum Yardımcısı yerine Şirket Portalı ile kimliği doğrula** ayarını **Evet** değerine ayarlayın.
    >    - çok faktörlü kimlik doğrulaması kullanma
    >    - ilk kez oturum açarken parolalarını değiştirmesi gereken kullanıcılara bunu bildirme
    >    - kayıt sırasında kullanıcılardan süresi dolmuş parolalarını sıfırlamalarını isteme
    >
    > Apple Kurulum Yardımcısı ile kimliği doğrularken bunlar desteklenmez.


6. **Oluştur**’u seçerek profili kaydedin.

## <a name="setup-assistant-enrollment"></a>Kurulum Yardımcısı kaydı

### <a name="add-apple-configurator-serial-numbers"></a>Apple Configurator seri numaraları ekleme

1. İki sütunlu, üst bilgisi olmayan bir virgülle ayrılmış değerler (.csv) listesi oluşturun. Seri numarasını sol sütuna, ayrıntıları sağ sütuna ekleyin. Liste için geçerli üst sınır 5.000 satırdır. Metin düzenleyicisinde .csv listesi aşağıdaki gibi görünür:

    F7TLWCLBX196,cihaz ayrıntıları</br>
    DLXQPCWVGHMJ,cihaz ayrıntıları

   [İOS/ıpados cihaz seri numarasını bulmayı](https://support.apple.com/HT204073)öğrenin.
2. [Microsoft Endpoint Manager Yönetim Merkezi](https://go.microsoft.com/fwlink/?linkid=2109431)'nde **, > ** **IOS** > IOS **kaydı** > **Apple Configurator** > **cihazları** > **Ekle**' yi seçin.

5. İçeri aktardığınız seri numaralarına uygulamak için bir **Kayıt profili** seçin. Seri numara ayrıntılarının önceki tüm ayrıntıların üzerine yazmasını istiyorsanız **Geçerli tanımlayıcı ayrıntılarının üzerine yaz**’ı seçin.
6. **Cihaz İçeri Aktar** altında seri numaralarının bulunduğu csv dosyasına gözatın ve **Ekle**’yi seçin.

### <a name="reassign-a-profile-to-device-serial-numbers"></a>Cihaz seri numaralarına bir profili yeniden atama

Apple Configurator kaydı için iOS/ıpados seri numaralarını içeri aktardığınızda bir kayıt profili atayabilirsiniz. Ayrıca Azure portalında da iki konumdan profil atayabilirsiniz:
- **Apple Configurator cihazları**
- **AC profilleri**

#### <a name="assign-from-apple-configurator-devices"></a>Apple Configurator cihazlarından atama
1. [Microsoft Endpoint Manager Yönetim Merkezi](https://go.microsoft.com/fwlink/?linkid=2109431)'Nde, **iOS** > IOS **kaydı** > **Apple Configurator** > **cihazları** ' nı seçin > seri **numaralarını seçin >** **profil** > .
2. **Profil Ata** altında atamak istediğiniz **Yeni profil**’i, sonra da **Ata**’yı seçin.

#### <a name="assign-from-profiles"></a>Profillerden atama
1. [Microsoft Endpoint Manager Yönetim Merkezi](https://go.microsoft.com/fwlink/?linkid=2109431)'nde, > **iOS** > **ios kaydı** > **Apple Configurator** > **profillerini** seçin > bir **profil seçin.**
2. Profilde, **Atanmış cihazlar**’ı ve ardından **Ata**’yı seçin.
3. Profile atamak istediğiniz cihaz seri numaralarını bulmak için filtre uygulayın, cihazları seçin ve ardından **Ata**’yı seçin.

### <a name="export-the-profile"></a>Profili dışarı aktarma
Profil oluşturup seri numaralarını atadıktan sonra profili Intune'dan URL olarak dışarı aktarmanız gerekir. Ardından bunu cihazlara dağıtmak üzere bir Mac bilgisayardaki Apple Configurator’a içeri aktarırsınız.

1. [Microsoft Endpoint Manager Yönetim Merkezi](https://go.microsoft.com/fwlink/?linkid=2109431)'nde, > **iOS** > **ios kaydı** > **Apple Configurator** > **profilleri** ' ni seçin > dışarı aktarılacak **profili seçin.**
2. Profilde **Profili Dışarı Aktar**’ı seçin.
3. **Profil URL’sini** kopyalayın. Ardından, iOS/ıpados cihazları tarafından kullanılan Intune profilini tanımlamak için bunu Apple Configurator 'a ekleyebilirsiniz.

   Ardından, iOS/ıpados cihazları tarafından kullanılan Intune profilini tanımlamak için aşağıdaki yordamda bu profili Apple Configurator 'a aktarın.

### <a name="enroll-devices-with-setup-assistant"></a>Kurulum Yardımcısı ile cihaz kaydetme

1. Mac bilgisayarda **Apple Configurator 2**'yi açın. Menü çubuğunda **Apple Configurator 2**’yi, sonra **Tercihler**’i seçin.
    > [!WARNING]
    > Cihazlar kayıt işlemi sırasında fabrika yapılandırmalarına sıfırlanır. En iyi uygulama olarak cihazı sıfırlayın ve açın. Cihazı bağladığınızda cihazın **Merhaba** ekranında olması gerekir.
    > Cihaz Apple KIMLIĞI hesabıyla zaten kaydedilmişse, kayıt işlemine başlamadan önce cihazın Apple iCloud 'dan silinmesi gerekir. İstem hatası "etkinleştirilemiyor [Cihaz adı]" olarak görüntülenir.

2. **Tercihler** bölmesinde **Sunucular**’ı seçin ve MDM Sunucusu sihirbazını başlatmak için (+) artı simgesini seçin. **İleri**’yi seçin.
3. Microsoft Intune sahip iOS/ıpados cihazları için Kurulum Yardımcısı kaydı altındaki MDM sunucusunun **ana bilgisayar adını veya URL 'sini** ve **kayıt URL** 'sini girin. Kayıt URL’si olarak Intune’dan dışarı aktarılan kayıt profili URL’sini girin. **İleri**’yi seçin.  
    “Sunucu URL'si doğrulanmadı” uyarısı alırsanız göz ardı edebilirsiniz. Devam etmek için sihirbaz tamamlanana kadar **İleri**’yi seçin.
4. İOS/ıpados mobil cihazlarını bir USB bağdaştırıcısı ile Mac bilgisayara bağlayın.
5. Yönetmek istediğiniz iOS/ıpados cihazlarını seçin ve ardından **hazırla**' yı seçin. **İOS/ıpados cihazını hazırla** bölmesinde, **el ile**' yi seçin ve ardından **İleri**' yi seçin.
6. **MDM Sunucusuna Kaydol** bölmesinde, oluşturduğunuz sunucunun adını ve sonra da **İleri**’yi seçin.
7. **Cihazları Denetle** bölmesinde, denetim düzeyini seçin, sonra **İleri**’yi seçin.
8. **Kuruluş Oluştur** bölmesinde **Kuruluş**’u seçin veya yeni bir kuruluş oluşturun, sonra **İleri**’yi seçin.
9. **İOS/ıpados Kurulum Yardımcısı 'Nı Yapılandır** bölmesinde, kullanıcıya sunulacak adımları seçin ve ardından **hazırla**' yı seçin. İstenirse, güven ayarlarını güncelleştirmek için kimlik doğrulayın.  
10. İOS/ıpados cihazı hazırlanma işlemini bitirdiğinde USB kablosunu sökün.  

### <a name="distribute-devices"></a>Cihazları dağıtma
Cihazlar artık kurumsal kayıt için hazırdır. Cihazları kapatın ve kullanıcılara dağıtın. Kullanıcılar cihazlarını açtığında Kurulum Yardımcısı başlatılır.

Kullanıcıların, cihazlarını aldıktan sonra Kurulum Yardımcısı'nı tamamlamaları gerekir. Kullanıcı benzeşimi ile yapılandırılmış cihazlar, uygulama indirmek ve cihaz yönetmek için Şirket Portalı’nı yükleyip çalıştırabilir.

## <a name="direct-enrollment"></a>Doğrudan kayıt
İOS/ıpados cihazlarını doğrudan Apple Configurator ile kaydettiğinizde, cihazın seri numarasını almadan bir cihaz kaydedebilirsiniz. Ayrıca Intune kayıt sırasında cihaz adını yakalamadan önce, cihazı tanımlama amacıyla adlandırabilirsiniz. Şirket Portalı uygulaması doğrudan kayıtlı cihazlar için desteklenmez. Bu yöntem, cihazı silmez.

İş kolu uygulamalarını yüklemek için kullanılan Şirket Portalı uygulaması da dahil olmak üzere kullanıcı benzeşimi gerektiren uygulamalar yüklenemez.

### <a name="export-the-profile-as-mobileconfig-to-iosipados-devices"></a>Profili. mobileconfig olarak iOS/ıpados cihazlarına dışarı aktarma

1. [Microsoft Endpoint Manager Yönetim Merkezi](https://go.microsoft.com/fwlink/?linkid=2109431)'nde, > **iOS** > **ios kaydı** > **Apple Configurator** > **profilleri** ' ni seçin > **dışarı aktarma profilini**dışarı aktarmak için **profili seçin.**
2. **Doğrudan kayıt** altında **Profil indir**’i seçin ve dosyayı kaydedin. Bir kayıt profili yalnızca iki hafta geçerlidir, iki haftanın sonunda bunu yeniden oluşturmanız gerekir.
3. İOS/ıpados cihazlarına doğrudan bir yönetim profili olarak göndermek için dosyayı [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) çalıştıran bir Mac bilgisayara aktarın.
4. Aşağıdaki adımları izleyerek cihazı Apple Configurator ile hazırlayın:
    1. Mac bilgisayarda Apple Configurator 2.0'ı açın.
    2. İOS/ıpados cihazını bir USB kablosu ile Mac bilgisayara bağlayın. Fotoğraflar’ı, iTunes’u ve cihaz algılandığında cihaz için açık olan diğer uygulamaları kapatın.
    3. Apple Configurator 'da bağlı iOS/ıpados cihazını seçin ve sonra **Ekle** düğmesini seçin. Cihaza eklenebilen seçenekler aşağı açılan listede görüntülenir. **Profiller**’i seçin.

        ![Kurulum Yardımcısı Kaydı için Profili Dışarı Aktar’ın Profil URL’si vurgulanmış ekran görüntüsü](./media/apple-configurator-enroll-ios/ios-apple-configurator-add-profile.png)

    4. Intune’dan dışarı aktardığınız .mobileconfig dosyasını seçmek için dosya seçiciyi kullanın ve sonra **Ekle**’yi seçin. Profil cihaza eklenir. Cihaz Denetimsiz ise, yüklemenin cihazda kabul edilmesi gerekir.
5. Profili iOS/ıpados cihazına yüklemek için aşağıdaki adımları kullanın. Cihaz, Kurulum Yardımcısı’nı zaten tamamlamış ve hazır olmalıdır. Kayıt içinde uygulama dağıtımları da varsa uygulama dağıtımı, App Store için imzalanmış bir Apple Kimliğiniz olmasını gerektirdiğinden cihazda bir Apple Kimliği ayarlanmış olmalıdır.
    1. İOS/ıpados cihazının kilidini açın.
    2. **Yönetim profili**’nin **Profili yükle** iletişim kutusunda **Yükle**’yi seçin.
    3. Gerekirse, Cihaz Geçiş Kodu veya Apple Kimliği sağlayın.
    4. **Uyarı**’yı kabul edin ve **Yükle**’yi seçin.
    5. **Uzak Uyarı**’yı kabul edin ve **Güven**’i seçin.
    6. **Profil Yüklendi** kutusu profilin Yüklü olduğunu doğruladığında **Bitti**’yi seçin.

6. İOS/ıpados cihazında **Ayarlar** ' ı açın ve **genel** > **cihaz yönetimi** > **Yönetim profili**' ne gidin. Profil yüklemesinin listelendiğini onaylayın ve iOS/ıpados ilke kısıtlamalarını ve yüklü uygulamaları denetleyin. İlke kısıtlamaları ve uygulamaların cihazda görünmesi 10 dakika kadar sürebilir.

7. Cihazları dağıtın. İOS/ıpados cihazı artık Intune 'A kaydolmuş ve yönetilmektedir.





