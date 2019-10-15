---
title: iOS cihaz kaydı-Apple Configurator-Kurulum Yardımcısı
titleSuffix: Microsoft Intune
description: Kurulum Yardımcısı ile şirkete ait iOS cihazlarını kaydetmek için Apple Configurator 'ın nasıl kullanılacağını öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/04/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 671e4d76-0c61-11e8-ba89-0ed5f89f718b
ms.reviewer: tisilver
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: a1c2acc2ebe5528e30c344a31c9551ac64bdf3ca
ms.sourcegitcommit: dd6755383ba89824d1cc128698a65fde6bb2de55
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/14/2019
ms.locfileid: "72306791"
---
# <a name="set-up-ios-device-enrollment-with-apple-configurator"></a>Apple Configurator ile iOS cihaz kaydını ayarlama

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Intune, bir Mac bilgisayarda çalışan [Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344) 'ı kullanarak iOS cihazlarının kaydedilmesini destekler. Apple Configurator 'a kaydolmak için her iOS cihazını, kurumsal kayıt kurulumu için bir Mac bilgisayara USB ile bağlamanız gerekir. Apple Configurator ile cihazları Intune 'a iki şekilde kaydedebilirsiniz:
- **Kurulum Yardımcısı kaydı** -cihazı temizler ve Kurulum Yardımcısı sırasında kayda hazırlar.
- **Doğrudan kayıt** -cihazı temizlemez ve iOS ayarları aracılığıyla cihazı kaydeder. Bu yöntem yalnızca **Kullanıcı benzeşimi olmayan**cihazları destekler.

Apple Configurator kayıt yöntemleri [cihaz kayıt yöneticisiyle](device-enrollment-manager-enroll.md)birlikte kullanılamaz.

## <a name="prerequisites"></a>Önkoşullar

- İOS cihazlarına fiziksel erişim
- [MDM yetkilisini ayarla](../fundamentals/mdm-authority-set.md)
- [Bir Apple MDM anında iletme sertifikası](apple-mdm-push-certificate-get.md)
- Cihaz seri numaraları (yalnızca Kurulum Yardımcısı kaydı)
- USB bağlantı kabloları
- [Apple Configurator 2,0](https://itunes.apple.com/app/apple-configurator-2/id1037126344) çalıştıran MacOS bilgisayarı

## <a name="create-an-apple-configurator-profile-for-devices"></a>Cihazlar için Apple Configurator profili oluşturma

Bir cihaz kayıt profili, kayıt sırasında uygulanan ayarları tanımlar. Bu ayarlar yalnızca bir kez uygulanır. Apple Configurator ile iOS cihazlarını kaydetmek için bir kayıt profili oluşturmak için bu adımları izleyin.

1. [Intune](https://aka.ms/intuneportal)'da **cihaz kaydı** > **Apple kayıt** > **Apple Configurator** > **profilleri** > **Oluştur**' u seçin.

    ![Apple Configurator için profil oluşturma](./media/apple-configurator-enroll-ios/apple-config-create-profile.png)

2. **Kayıt profili oluştur**altında, yönetim amaçları için profil Için bir **ad** ve **Açıklama** yazın. Kullanıcılar bu ayrıntıları görmez. Azure Active Directory içinde dinamik bir grup oluşturmak için bu ad alanını kullanabilirsiniz. Bu kayıt profiliyle cihazları atamak için Kayıtlıprofilename parametresini tanımlamak üzere profil adını kullanın. Azure Active Directory dinamik gruplar hakkında daha fazla bilgi edinin.

    ![Kullanıcı benzeşimi ile Kaydet seçiliyken profil oluştur ekranının ekran görüntüsü](./media/apple-configurator-enroll-ios/apple-configurator-profile-create.png)

3. **Kullanıcı benzeşimi**için, bu profile sahip cihazların atanmış bir kullanıcı ile mi yoksa atanan kullanıcı olmadan mı kaydolması gerektiğini seçin.

    - **Kullanıcı benzeşimi Ile kaydetme** -kullanıcılara ait olan ve uygulamaları yükleme gibi hizmetler için şirket portalı 'nı kullanmak isteyen cihazlar için bu seçeneği belirleyin. Cihaz, Kurulum Yardımcısı olan bir kullanıcıyla bağlantılı olmalıdır ve daha sonra şirket verilerine ve e-postalara erişebilir. Yalnızca Kurulum Yardımcısı kaydı için desteklenir. Kullanıcı benzeşimi [WS-Trust 1,3 Kullanıcı adı/karma uç nokta](https://technet.microsoft.com/library/adfs2-help-endpoints)gerektirir. [Daha fazla bilgi edinin](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

    - **Kullanıcı benzeşimi olmadan kaydetme** -tek bir kullanıcıyla bağlantılı olmayan cihazlar için bu seçeneği belirleyin. Bunu, yerel kullanıcı verilerine erişmeden görevleri gerçekleştiren cihazlar için kullanın. Kullanıcı ilişkisi gerektiren uygulamalar (iş kolu uygulamalarını yüklemek için kullanılan Şirket Portalı uygulaması dahil) çalışmaz. Doğrudan kayıt için gereklidir.

     > [!NOTE]
     > **Kullanıcı benzeşimi Ile kaydetme** seçildiğinde, cihazın Kaydolmakta olan cihazın ilk 24 saati Içinde kurulum yardımcısı olan bir kullanıcıyla ilişkili olduğundan emin olun. Aksi takdirde kayıt başarısız olabilir ve cihazı kaydetmek için bir fabrika sıfırlaması gerekecektir.

4. **Kullanıcı benzeşimi Ile kaydet**' i seçerseniz, kullanıcıların Apple kurulum yardımcısı yerine Şirket portalı kimlik doğrulamasına izin vermek için seçeneğiniz vardır.

    > [!NOTE]
    > Aşağıdakilerden birini yapmak istiyorsanız, **Apple Kurulum Yardımcısı yerine Şirket portalı kimlik doğrulamasını** **Evet**olarak ayarlayın.
    >    - çok faktörlü kimlik doğrulaması kullan
    >    - ilk oturum açtıklarında parolalarını değiştirmesi gereken kullanıcılara sor
    >    - kullanıcıların kayıt sırasında süre dolma parolalarını sıfırlamalarını iste
    >
    > Bunlar, Apple Kurulum Yardımcısı ile kimlik doğrulanırken desteklenmez.


6. Profili kaydetmek için **Oluştur** ' a tıklayın.

## <a name="setup-assistant-enrollment"></a>Kurulum Yardımcısı kaydı

### <a name="add-apple-configurator-serial-numbers"></a>Apple Configurator seri numaraları ekleme

1. Üst bilgi içermeyen iki sütunlu, virgülle ayrılmış değer (. csv) listesi oluşturun. Sol sütundaki seri numarasını ve sağ sütundaki ayrıntıları ekleyin. Liste için geçerli en büyük değer 5.000 satırdır. Bir metin düzenleyicisinde. csv listesi şöyle görünür:

    F7TLWCLBX196, cihaz ayrıntıları</br>
    DLXQPCWVGHMJ, cihaz ayrıntıları

   [İOS cihaz seri numarasını bulmayı](https://support.apple.com/HT204073)öğrenin.
2. [Intune](https://aka.ms/intuneportal)'da **cihaz kaydı** > **Apple kayıt** > **Apple Configurator** > **cihazları** > **Ekle**' yi seçin.

5. İçeri aktardığınız seri numaralarına uygulamak için bir **kayıt profili** seçin. Yeni seri numarası ayrıntılarının var olan ayrıntıların üzerine yazılmasını istiyorsanız, **var olan tanımlayıcıların ayrıntılarının üzerine yaz**' ı seçin.
6. **Aygıtları Içeri aktar**' ın altında seri numaralarının CSV dosyasına gidin ve **Ekle**' yi seçin.

### <a name="reassign-a-profile-to-device-serial-numbers"></a>Bir profili cihaz seri numaralarına yeniden atama

Apple Configurator kaydı için iOS seri numaralarını içeri aktardığınızda bir kayıt profili atayabilirsiniz. Ayrıca, Azure portal iki konumdan profil de atayabilirsiniz:
- **Apple Configurator cihazları**
- **AC profilleri**

#### <a name="assign-from-apple-configurator-devices"></a>Apple Configurator cihazlarından atama
1. [Intune](https://aka.ms/intuneportal)'Da, **cihaz kaydı** > **Apple kayıt** > **Apple Configurator** > **cihazları** > seri numaralarını seçin > **profili**seçin.
2. **Profil ata**altında atamak istediğiniz **yeni profili** seçin ve ardından **ata**' yı seçin.

#### <a name="assign-from-profiles"></a>Profillerden ata
1. [Intune](https://aka.ms/intuneportal)'Da, **cihaz kaydı** > **Apple kayıt** > **Apple Configurator** >  >**profilleri** ' ni seçin ve bir profil seçin.
2. Profilde, **atanmış cihazlar**' ı ve ardından **ata**' yı seçin.
3. Profile atamak istediğiniz cihaz seri numaralarını bulmak için filtre uygulayın, cihazları seçin ve ardından **ata**' yı seçin.

### <a name="export-the-profile"></a>Profili dışarı aktarma
Profil oluşturup seri numaralarını atadıktan sonra, profili Intune 'dan bir URL olarak dışarı aktarmanız gerekir. Daha sonra cihaza dağıtım için bir Mac üzerinde Apple Configurator 'a içeri aktarırsınız.

1. [Intune](https://aka.ms/intuneportal)'Da, **cihaz kaydı** > **Apple kayıt** > **Apple Configurator** >  >**profilleri** ' ni seçin ve dışarı aktarılacak profili seçin.
2. Profilde **profili dışarı aktar**' ı seçin.
3. **Profil URL 'sini**kopyalayın. Ardından, iOS cihazları tarafından kullanılan Intune profilini tanımlamak için bunu Apple Configurator 'a ekleyebilirsiniz.

   Ardından, iOS cihazlar tarafından kullanılan Intune profilini tanımlamak için aşağıdaki yordamda bu profili Apple Configurator 'a aktarın.

### <a name="enroll-devices-with-setup-assistant"></a>Kurulum Yardımcısı ile cihazları kaydetme

1. Mac bilgisayarda **Apple Configurator 2**' yi açın. Menü çubuğunda **Apple Configurator 2**' yi ve ardından **Tercihler**' i seçin.
    > [!WARNING]
    > Cihazlar kayıt işlemi sırasında fabrika yapılandırmalarına sıfırlanır. En iyi uygulama olarak cihazı sıfırlayın ve açın. Cihaz bağladığınızda cihazların **Merhaba** ekranında olması gerekir.
    > Cihaz Apple KIMLIĞI hesabıyla zaten kaydedilmişse, kayıt işlemine başlamadan önce cihazın Apple iCloud 'dan silinmesi gerekir. İstem hatası "etkinleştirilemiyor [Cihaz adı]" olarak görüntülenir.

2. **Tercihler** bölmesinde **sunucular** ' ı seçin ve MDM sunucusu sihirbazını başlatmak için artı simgesini (+) seçin. **İleri**’yi seçin.
3. Microsoft Intune sahip iOS cihazları için Kurulum Yardımcısı kaydı altındaki MDM sunucusunun **ana bilgisayar adını veya URL 'sini** ve **kayıt URL** 'sini girin. Kayıt URL 'si için, Intune 'dan aktarılmış kayıt profili URL 'sini girin. **İleri**’yi seçin.  
    "Sunucu URL 'SI doğrulanmadı" uyarısını güvenle yoksayabilirsiniz. Devam etmek için, sihirbaz tamamlanana kadar **İleri** ' yi seçin.
4. İOS mobil cihazları bir USB bağdaştırıcısı ile Mac bilgisayara bağlayın.
5. Yönetmek istediğiniz iOS cihazlarını seçin ve ardından **hazırla**' yı seçin. **IOS cihazını hazırla** bölmesinde **el ile**' yi seçin ve ardından **İleri**' yi seçin.
6. **MDM sunucusuna kaydol** bölmesinde, oluşturduğunuz sunucu adını seçin ve ardından **İleri**' yi seçin.
7. Cihazlar bölmesinde, **gözetim** düzeyini seçin ve ardından **İleri**' yi seçin.
8. **Kuruluş oluştur** bölmesinde **kuruluş** ' u seçin veya yeni bir kuruluş oluşturun ve ardından **İleri**' yi seçin.
9. **IOS Kurulum Yardımcısı 'Nı Yapılandır** bölmesinde, kullanıcıya sunulacak adımları seçin ve ardından **hazırla**' yı seçin. İstenirse, güven ayarlarını güncelleştirmek için kimlik doğrulaması yapın.  
10. İOS cihazının hazırlanması bittiğinde USB kablosunun bağlantısını kesin.  

### <a name="distribute-devices"></a>Cihazları dağıtma
Cihazlar artık kurumsal kayıt için hazırdır. Cihazları kapatın ve kullanıcılara dağıtın. Kullanıcılar cihazlarını açıp Kurulum Yardımcısı başlar.

Kullanıcılar cihazlarını aldıktan sonra Kurulum Yardımcısı 'Nı tamamlamalıdır. Kullanıcı benzeşimi ile yapılandırılmış cihazlar, uygulama indirmek ve cihazları yönetmek için Şirket Portalı uygulamasını yükleyip çalıştırabilir.

## <a name="direct-enrollment"></a>Doğrudan kayıt
İOS cihazlarını Apple Configurator ile doğrudan kaydettiğinizde, cihazın seri numarasını almadan bir cihaz kaydedebilirsiniz. Intune, kayıt sırasında cihaz adını yakalamamasından önce, cihazı kimlik için de kullanabilirsiniz. Şirket Portalı uygulaması doğrudan kayıtlı cihazlar için desteklenmez. Bu yöntem, cihazı temizlemez.

İş kolu uygulamalarını yüklemek için kullanılan Şirket Portalı uygulaması da dahil olmak üzere Kullanıcı katılımı gerektiren uygulamalar yüklenemez.

### <a name="export-the-profile-as-mobileconfig-to-ios-devices"></a>Profili. mobileconfig olarak iOS cihazlarına dışarı aktarma

1. [Intune](https://aka.ms/intuneportal)'da **cihaz kaydı** > **Apple kayıt** > **Apple Configurator** >  >**profilleri** ' ni seçin > **dışarı aktarma profilini**dışarı aktarmak için profili seçin.
2. **Doğrudan kayıt**altında **Profili İndir**' i seçin ve dosyayı kaydedin. Kayıt profili dosyası, yalnızca iki hafta boyunca geçerlidir. bu süre, yeniden oluşturmanız gerekir.
3. İOS cihazlarına doğrudan bir yönetim profili olarak göndermek için dosyayı [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) çalıştıran bir Mac bilgisayara aktarın.
4. Aşağıdaki adımları izleyerek cihazı Apple Configurator ile hazırlayın:
    1. Mac bilgisayarda Apple Configurator 2,0 ' ı açın.
    2. İOS cihazını bir USB kablosu ile Mac bilgisayara bağlayın. Cihaz algılandığında cihaz için açık olan fotoğrafları, iTunes 'u ve diğer uygulamaları kapatın.
    3. Apple Configurator 'da bağlı iOS cihazını seçin ve sonra **Ekle** düğmesini seçin. Cihaza eklenebilecek seçenekler açılır listede görüntülenir. **Profiller**' i seçin.

        ![Profil URL 'SI vurgulanmış şekilde Kurulum Yardımcısı kaydı için ekran görüntüsü dışarı aktarma profili](./media/apple-configurator-enroll-ios/ios-apple-configurator-add-profile.png)

    4. Intune 'dan verdiğiniz. mobileconfig dosyasını seçmek için dosya seçiciyi kullanın ve ardından **Ekle**' yi seçin. Profil cihaza eklenir. Cihaz denetlenmiyor ise, yüklemenin cihazda kabul edilmesi gerekir.
5. Profili iOS cihazına yüklemek için aşağıdaki adımları kullanın. Cihazın Kurulum Yardımcısını zaten tamamlamış ve kullanıma hazırmış olması gerekir. Kayıt uygulama dağıtımlarını gerektiriyorsa, uygulama dağıtımı uygulama mağazası için oturum açmış bir Apple KIMLIĞINIZ olmasını gerektirdiğinden cihazda bir Apple KIMLIĞI ayarlanmış olmalıdır.
    1. İOS cihazının kilidini açın.
    2. **Yönetim profili**Için **profil yüklensin** iletişim kutusunda, **yükler**' i seçin.
    3. Gerekirse, cihaz geçiş kodu veya Apple KIMLIĞI sağlayın.
    4. **Uyarıyı**kabul edin ve **Install**' ı seçin.
    5. **Uzaktan Uyarı**' yı kabul edin ve **güven**' i seçin.
    6. **Profil yüklendi** kutusu profili yüklendi olarak onayladığında **bitti**' yi seçin.

6. İOS cihazında **Ayarlar** ' ı açın ve **genel** > **cihaz yönetimi** > **Yönetim profili**' ne gidin. Profil yüklemesinin listelendiğini onaylayın ve iOS ilke kısıtlamalarını ve yüklü uygulamaları denetleyin. İlke kısıtlamaları ve uygulamaların cihazda görünmesi 10 dakikaya kadar sürebilir.

7. Cihazları dağıtın. İOS cihazı artık Intune 'A kaydolmuş ve yönetilmektedir.





