---
title: "iOS cihazlarını kaydetme- Apple Configurator-Kurulum Yardımcısı"
titlesuffix: Azure portal
description: "Kurulum Yardımcısı’nı kullanarak şirkete ait iOS cihazlarını kaydetmek için Apple Configurator’ı kullanmayı öğrenin.\""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 09/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d384cd0-b662-41e7-94f5-0c96790ab20a
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5b139db1780881e5bc0aed2345f9dc456a18f0e0
ms.sourcegitcommit: cf7f7e7c9e9cde5b030cf5fae26a5e8f4d269b0d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2017
---
# <a name="enroll-ios-devices-with-apple-configurator"></a>Apple Configurator ile iOS cihazlarını kaydetme

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune, bir Mac bilgisayarda çalıştırılan [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) kullanarak iOS cihazlarının kaydedilmesini destekler. Apple Configurator ile kaydetme işlemi, kurumsal kaydı ayarlamak için her iOS cihazını bir Mac bilgisayara USB ile bağlamanızı gerektirir. Apple Configurator ile Intune'a cihazları iki yolla kaydedebilirsiniz:
- **Kurulum Yardımcısı kaydı** - Cihazı fabrika ayarlarına sıfırlar ve Kurulum Yardımcısı sırasında kayda hazırlar.
- **Doğrudan kayıt** - Cihazı fabrika ayarlarına sıfırlamaz ve iOS ayarları aracılığıyla kaydeder. Bu yöntem, yalnızca **kullanıcı benzeşimi olmayan** cihazları destekler.

Apple Configurator kayıt yöntemleri [cihaz kaydı yöneticisi](device-enrollment-manager-enroll.md) ile birlikte kullanılamaz.

## <a name="prerequisites"></a>Önkoşullar

- iOS cihazlara fiziksel erişim
- [MDM yetkilisini ayarlama](mdm-authority-set.md)
- [Apple MDM anında iletme sertifikası](apple-mdm-push-certificate-get.md)
- Cihaz seri numaraları (yalnızca Kurulum Yardımcısı kaydı)
- USB bağlantı kabloları
- [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) çalıştıran Mac bilgisayar

## <a name="create-an-apple-configurator-profile-for-devices"></a>Cihazlar için Apple Configurator profili oluşturma

Bir cihaz kayıt profili kayıt sırasında uygulanan ayarları tanımlar. Bu ayarlar yalnızca bir kez uygulanır. iOS cihazlarını Apple Configurator ile kaydetmek üzere bir kayıt profili oluşturmak için aşağıdaki adımları izleyin.

1. Azure portalında oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Cihaz kaydı** > **Apple Kaydı**’nı seçin.
4. **Apple Configurator Kayıt Ayarlarını Yönet** içinde **AC Profilleri**’ni seçin.
5. **Apple Configurator Kayıt Profilleri** altında **Oluştur**’u seçin.
6. Yönetim amaçları doğrultusunda profil için bir **Ad** ve **Açıklama** girin. Kullanıcılar bu ayrıntıları göremez. Azure Active Directory’de dinamik bir grup oluşturmak için bu Ad alanını kullanabilirsiniz. enrollmentProfileName parametresini, bu kayıt profiliyle cihazlara atamak amacıyla tanımlamak için profil adını kullanın. Azure Active Directory dinamik grupları hakkında daha fazla bilgi edinin.

  ![Kullanıcı benzeşimi ile kaydet seçeneği belirlenmiş profil oluşturma ekranının ekran görüntüsü](./media/apple-configurator-profile-create.png)

7. **Kullanıcı Benzeşimi** Belirtme:
   - **Kullanıcı benzeşimiyle kaydet** - Cihaz Kurulum Yardımcısı ile bir kullanıcıya bağlanmalıdır. Böylece, cihaz şirket verilerine ve e-postalara erişebilir. Kullanıcılara ait olan ve uygulamaları yükleme gibi hizmetler için Intune Şirket Portalı kullanması gereken yönetilen cihazlarda kullanıcı benzeşimi gereklidir. Yalnızca Kurulum Yardımcısı kaydı için desteklenir. Kullanıcı benzeşimi [WS-Trust 1.3 Kullanıcı adı/Karma uç noktası](https://technet.microsoft.com/library/adfs2-help-endpoints) gerektirir. [Daha fazla bilgi edinin](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

   > [!NOTE]
   > Çok faktörlü kimlik doğrulaması (MFA), kullanıcı benzeşimi ile ayarlanmış kayıt sırasında çalışmaz. Kayıttan sonra MFA, cihazlarda beklendiği gibi çalışır. Cihazlar, ilk defa oturum açıldığında parolalarını değiştirmesi gereken kullanıcılara istemde bulunamaz. Ayrıca, parolalarının süresi dolmuş olan kullanıcılardan kayıt sırasında parolalarını sıfırlamaları istenmez. Kullanıcıların, parolayı sıfırlamak için farklı bir cihaz kullanmaları gerekir.

   - **Kullanıcı benzeşimi olmadan kaydet** - Cihaz bir kullanıcıya bağlı değildir. Bu ilişkiyi, yerel kullanıcı verilerine erişmeden görevleri yerine getiren cihazlar için kullanın. Kullanıcı benzeşimi gerektiren uygulamalar (iş kolu uygulamalarını yüklemek için kullanılan Şirket Portalı uygulaması da dahil) çalışmaz. Doğrudan kayıt için gereklidir.

6. Profili kaydetmek için **Oluştur**’u seçin.

## <a name="setup-assistant-enrollment"></a>Kurulum Yardımcısı kaydı

### <a name="add-apple-configurator-serial-numbers"></a>Apple Configurator seri numaraları ekleme

**Intune’a Apple Configurator seri numaralarını eklemek için**

1. İki sütunlu, üst bilgisi olmayan bir virgülle ayrılmış değerler (.csv) listesi oluşturun. Seri numarasını sol sütuna, ayrıntıları sağ sütuna ekleyin. Liste için geçerli üst sınır 500 satırdır. Metin düzenleyicisinde .csv listesi aşağıdaki gibi görünür:

    F7TLWCLBX196,cihaz ayrıntıları</br>
    DLXQPCWVGHMJ,cihaz ayrıntıları

   [iOS cihaz seri numarasını bulmayı](https://support.apple.com/HT204073) öğrenin.
2. Azure portalında Intune’da **Cihaz kaydı**'nı, ardından **Apple Kaydı**'nı seçin.
3. **Apple Configurator Kayıt Ayarlarını Yönet**’in altında, **Apple Configurator Cihazları**’nı seçin.
4. **Ekle**’yi seçin.
5. İçeri aktardığınız seri numaralarına uygulamak için bir **Kayıt profili** seçin. Mevcut ayrıntıların üzerine yazılan yeni ayrıntılar içeren bir dosyayı içeri aktarırsanız, **Mevcut tanımlayıcıların ayrıntılarının üzerine yazın** seçeneğini belirleyin.
6. Seri numaralarının bulunduğu csv dosyasına gidin ve **Ekle**’yi seçin.

### <a name="reassign-a-profile-to-device-serial-numbers"></a>Cihaz seri numaralarına bir profili yeniden atama

Apple Configurator kaydı için iOS seri numaralarını içeri aktardığınızda bir kayıt profili atarsınız. Intune, Azure Portal’da iki konumdan profil atamanıza da olanak tanır:
- **Apple Configurator cihazları**
- **AC profilleri**

#### <a name="assign-from-apple-configurator-devices"></a>Apple Configurator cihazlarından atama
1. Azure portalında Intune’da **Cihaz kaydı**'nı, ardından **Apple Kaydı**'nı seçin.
3. **Apple Configurator Cihazları** altında profil atamak istediğiniz seri numaralarını, sonra da **Profil Ata**’yı seçin.
4. **Profil Ata** altında atamak istediğiniz **Yeni profili**, sonra da **Ata**yı seçin.

#### <a name="assign-from-profiles"></a>Profillerden atama
1. Azure portalında Intune’da **Cihaz kaydı**'nı, ardından **Apple Kaydı**'nı seçin.
2. **AC Profilleri**’ni ve ardından seri numaralarına atamak istediğiniz profili seçin.
3. Profilde, **Atanmış cihazlar**’ı ve ardından **Ata**’yı seçin.
4. Profile atamak istediğiniz cihaz seri numaralarını bulmak için filtre uygulayın, cihazları seçin ve ardından **Ata**’yı seçin.

### <a name="export-the-profile"></a>Profili dışarı aktarma
Profil oluşturup seri numaralarını atadıktan sonra profili Intune'dan URL olarak dışarı aktarmanız gerekir. Ardından bunu cihazlara dağıtmak üzere bir Mac bilgisayardaki Apple Configurator’a içeri aktarırsınız.

1. Azure portalında Intune’da, **Cihaz kaydı** > **Apple kaydı** > **AC Profilleri**’ni seçin ve sonra dışarı aktarılacak profili seçin.
2. Profilde **Profili Dışarı Aktar**’ı seçin.

  ![Kurulum Yardımcısı Kaydı için Profili Dışarı Aktar’ın Profil URL’si vurgulanmış ekran görüntüsü](./media/ios-apple-configurator-expor-sat.png)
3. Profil URL'sini kopyalayın. iOS cihazlar tarafından kullanılan Intune profilini tanımlamak için bunu daha sonra Apple Configurator'a ekleyebilirsiniz.

  Ardından iOS cihazlarında kullanılan Intune profilini tanımlamak için aşağıdaki yordamda bu profili Apple Configurator’a içeri aktarırsınız.

### <a name="enroll-devices-with-setup-assistant"></a>Kurulum Yardımcısı ile cihaz kaydetme

1.  Mac bilgisayarda **Apple Configurator 2**'yi açın. Menü çubuğunda **Apple Configurator 2**’yi, sonra **Tercihler**’i seçin.
  > [!WARNING]
  > Cihazlar kayıt işlemi sırasında fabrika yapılandırmalarına sıfırlanır. En iyi uygulama olarak cihazı sıfırlayın ve açın. Cihazı bağladığınızda cihazın **Merhaba** ekranında olması gerekir.

2. **Tercihler** bölmesinde **Sunucular**’ı seçin ve MDM Sunucusu sihirbazını başlatmak için (+) artı simgesini seçin. **İleri**’yi seçin.
3. Microsoft Intune ile iOS cihazları için Kurulum Yardımcısı kaydı altındaki MDM sunucusunun **Konak adı veya URL’si** ve **kayıt URL'sini** girin. Kayıt URL’si olarak Intune’dan dışarı aktarılan kayıt profili URL’sini girin. **İleri**’yi seçin.  

  “Sunucu URL'si doğrulanmadı” uyarısı alırsanız göz ardı edebilirsiniz. Devam etmek için sihirbaz tamamlanana kadar **İleri**’yi seçin.
4.  iOS mobil cihazları bir USB bağdaştırıcısı ile Mac bilgisayara bağlayın.
5.  Yönetmek istediğiniz iOS cihazları ve ardından **Hazırla**’yı seçin. **iOS Cihazını Hazırla** bölmesinde, **El ile**’yi, sonra **İleri**’yi seçin.
6. **MDM Sunucusuna Kaydol** bölmesinde, oluşturduğunuz sunucunun adını ve sonra da **İleri**’yi seçin.
7. **Cihazları Denetle** bölmesinde, denetim düzeyini seçin, sonra **İleri**’yi seçin.
8. **Kuruluş Oluştur** bölmesinde **Kuruluş**’u seçin veya yeni bir kuruluş oluşturun, sonra **İleri**’yi seçin.
9. **iOS Kurulum Yardımcısı’nı Yapılandır** bölmesinde, kullanıcıya sunulacak adımları ve sonra da **Hazırla**’yı seçin. İstenirse, güven ayarlarını güncelleştirmek için kimlik doğrulaması yapın.  
10. iOS cihazı hazırlanmayı tamamladığında USB kablosunun bağlantısını kesin.  

### <a name="distribute-devices"></a>Cihazları dağıtma
Cihazlar artık kurumsal kayıt için hazırdır. Cihazları kapatın ve kullanıcılara dağıtın. Kullanıcılar cihazlarını açtığında Kurulum Yardımcısı başlatılır.

Kullanıcıların, cihazlarını aldıktan sonra Kurulum Yardımcısı'nı tamamlamaları gerekir. Kullanıcı benzeşimi ile yapılandırılmış cihazlar, uygulama indirmek ve cihaz yönetmek için Şirket Portalı’nı yükleyip çalıştırabilir.

## <a name="direct-enrollment"></a>Doğrudan kayıt
iOS cihazlarını Apple Configurator ile doğrudan kaydederken, cihazın seri numarasını almadan kayıt işlemini gerçekleştirebilirsiniz. Ayrıca Intune kayıt sırasında cihaz adını yakalamadan önce, cihazı tanımlama amacıyla adlandırabilirsiniz. Şirket Portalı uygulaması doğrudan kayıtlı cihazlar için desteklenmez. Bu yöntem, cihazda fabrika sıfırlaması yapmaz.

İş kolu uygulamalarını yüklemek için kullanılan Şirket Portalı uygulaması da dahil olmak üzere kullanıcı benzeşimi gerektiren uygulamalar yüklenemez.

### <a name="export-the-profile-as-mobileconfig-to-ios-devices"></a>Profili iOS cihazlarına .mobileconfig olarak dışarı aktarma
1. Azure portalında oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Profili Dışarı Aktar** altında **Profil indir**’i seçerek kayıt profilini indirin.

  ![Kurulum Yardımcısı Kaydı için Profili Dışarı Aktar’ın Profil URL’si vurgulanmış ekran görüntüsü](./media/ios-apple-configurator-expor-de.png)

4. Dosyayı [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) çalıştıran bir Mac bilgisayara aktararak iOS cihazlar için doğrudan bir yönetim profili olarak gönderebilirsiniz.
5. Aşağıdaki adımları izleyerek cihazı Apple Configurator ile hazırlayın.
  1. Mac bilgisayarda Apple Configurator 2.0'ı açın.
  2. iOS cihazını bir USB kablosu ile Mac bilgisayara bağlayın. Fotoğraflar’ı, iTunes’u ve cihaz algılandığında cihaz için açık olan diğer uygulamaları kapatın.
  3. Apple Configurator’da, bağlı iOS cihazını ve sonra **Ekle** düğmesini seçin. Cihaza eklenebilen seçenekler aşağı açılan listede görüntülenir. **Profiller**’i seçin.

    ![Kurulum Yardımcısı Kaydı için Profili Dışarı Aktar’ın Profil URL’si vurgulanmış ekran görüntüsü](./media/ios-apple-configurator-add-profile.png)

  4. Intune’dan dışarı aktardığınız .mobileconfig dosyasını seçmek için dosya seçiciyi kullanın ve sonra **Ekle**’yi seçin. Profil cihaza eklenir. Cihaz Denetimsiz ise, yüklemenin cihazda kabul edilmesi gerekir.
6. Profili iOS cihazına yüklemek için aşağıdaki adımları kullanın. Cihaz, Kurulum Yardımcısı’nı zaten tamamlamış ve hazır olmalıdır. Kayıt içinde uygulama dağıtımları da varsa uygulama dağıtımı, App Store için imzalanmış bir Apple Kimliğiniz olmasını gerektirdiğinden cihazda bir Apple Kimliği ayarlanmış olmalıdır.
   1. iOS cihazının kilidini açın.
   2. **Yönetim profili**’nin **Profili yükle** iletişim kutusunda **Yükle**’yi seçin.
   3. Gerekirse, Cihaz Geçiş Kodu veya Apple Kimliği sağlayın.
   4. **Uyarı**’yı kabul edin ve **Yükle**’yi seçin.
   5. **Uzak Uyarı**’yı kabul edin ve **Güven**’i seçin.
   6. **Profil Yüklendi** kutusu profilin Yüklü olduğunu doğruladığında **Bitti**’yi seçin.

7. iOS cihazında **Ayarlar**’ı açın ve **Genel** > **Cihaz Yönetimi** > **Yönetim Profili**’ne gidin. Profil yüklemesinin listelendiğini onaylayın, iOS ilke kısıtlamalarını ve yüklü uygulamaları denetleyin. İlke kısıtlamaları ve uygulamaların cihazda görünmesi 10 dakika kadar sürebilir.

8. Cihazları dağıtın. iOS cihazı Intune’a kaydedilmiştir ve yönetilmektedir.
