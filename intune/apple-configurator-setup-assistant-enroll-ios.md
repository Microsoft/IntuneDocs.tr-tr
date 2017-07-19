---
title: "iOS cihazlarını kaydetme- Apple Configurator-Kurulum Yardımcısı"
titleSuffix: Intune on Azure
description: "Kurulum Yardımcısı’nı kullanarak şirkete ait iOS cihazlarını kaydetmek için Apple Configurator’ı kullanmayı öğrenin.\""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d384cd0-b662-41e7-94f5-0c96790ab20a
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1d74fbcebfe89bbafc545d11dd6316cb602db8ee
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="enroll-ios-devices-with-apple-configurator"></a>Apple Configurator ile iOS cihazlarını kaydetme

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune, bir Mac bilgisayarda çalıştırılan [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) kullanarak şirketin sahip olduğu iOS cihazlarının kaydedilmesini destekler. Apple Configurator ile kaydetme işlemi, kurumsal kaydı ayarlamak için her iOS cihazını bir Mac bilgisayara USB ile bağlamanızı gerektirir. Apple Configurator ile Intune'a cihazları iki yolla kaydedebilirsiniz:
- **Kurulum Yardımcısı kaydı** - Cihazı fabrika ayarlarına sıfırlar, Kurulum Yardımcısı’nı çalıştırmaya hazırlar ve cihazın yeni kullanıcısı için şirketin ilkelerini yükler. Çoğu senaryoda, Intune Şirket Portalı uygulamasını etkinleştirmek için iOS cihazına uygulanmış olan ilkenin kullanıcı benzeşimi içermesi gerekir.
- **Doğrudan kayıt** - Bu işlem cihazı fabrika ayarlarına sıfırlamaz ve önceden tanımlanmış bir ilkeyle kaydeder. Bu yöntem **kullanıcı benzeşimi olmayan** cihazlar içindir.

>[!NOTE]
>Bu kayıt yöntemi, [cihaz kaydı yöneticisi](device-enrollment-manager-enroll.md) yöntemiyle birlikte kullanılamaz.

iOS cihazlarını kaydetmeye yönelik diğer yöntemler, [Intune’da iOS cihazlarının nasıl kaydedileceğini seçme](enrollment-method-choose-ios.md) başlığı altında açıklanır.

## <a name="prerequisites"></a>Önkoşullar

iOS cihaz kaydını ayarlamadan önce, aşağıdaki önkoşulları tamamlayın:

- [Apple MDM anında iletme sertifikası](apple-mdm-push-certificate-get.md)
- iOS cihazlara fiziksel erişim
- Cihaz seri numaraları (bkz. [iOS seri numarası alma](https://support.apple.com//HT204308))
- USB bağlantı kabloları
- [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) içeren Mac bilgisayar
- [Apple Configurator seri numaraları ekleme](apple-configurator-serial-numbers-add.md)

## <a name="setup-assistant-enrollment"></a>Kurulum Yardımcısı kaydı

### <a name="create-an-apple-configurator-profile-for-devices"></a>Cihazlar için Apple Configurator profili oluşturma

Cihaz kayıt profili bir cihaz grubuna uygulanan ayarları tanımlar. Aşağıdaki adımları, Apple Configurator kullanarak kaydedilmiş iOS cihazları için bir cihaz kayıt profilinin nasıl oluşturulacağını gösterir.

1. Intune portalında **Cihaz kaydı**'nı, ardından **Apple Kaydı**'nı seçin.
2. **Apple Configurator Kayıt Ayarlarını Yönet**’in altında, **AC Profilleri**’ni seçin.
3. **Apple Configurator Kayıt Profilleri** dikey penceresinde **Oluştur**’u seçin.
4. **Kayıt Profili Oluştur** dikey penceresinde, profil için bir ad ve açıklama girin.
5. **Kullanıcı Benzeşimi** için, bu profile sahip cihazların kullanıcı benzeşimiyle mi yoksa kullanıcı benzeşimi olmadan mı kaydedileceğini seçin.

   - **Kullanıcı benzeşimiyle kaydet** - Cihaz ilk kurulum sırasında bir kullanıcıya bağlı olmalıdır. Böylece, cihazın şirket verilerine ve e-postalara erişmesine izin verilebilir. Yönetilen kullanıcılara ait olan ve uygulama yüklemek gibi hizmetler için şirket portalını kullanması gereken cihazlarda kullanıcı benzeşimi ayarlanmalıdır.
   - **Kullanıcı benzeşimi olmadan kaydet** - Cihaz bir kullanıcıya bağlı değildir. Bu ilişkiyi, yerel kullanıcı verilerine erişmeden görevleri yerine getiren cihazlar için kullanın. Kullanıcı benzeşimi gerektiren uygulamalar (iş kolu uygulamalarını yüklemek için kullanılan Şirket Portalı uygulaması da dahil) çalışmaz.

6. Profili kaydetmek için **Oluştur**’u seçin.

### <a name="add-apple-configurator-serial-numbers"></a>Apple Configurator seri numaraları ekleme

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

[Kurulum Yardımcısı’yla Apple Configurator kullanarak şirkete ait iOS cihazlarını kaydetmek](apple-configurator-setup-assistant-enroll-ios.md) istediğinizde seri numaralarını Intune’a eklemek için bu adımları kullanın. Seri numaralarını birer birer ekleyebileceğiniz gibi, seri numaralarını içeren bir virgülle ayrılmış değerler (CSV) dosyasını da karşıya yükleyebilirsiniz. Seri numaralarını ekledikten sonra, bunlara profil atayabilirsiniz. Profil, cihazlara uygulamak istediğiniz belirli yönetim ayarlarını içerir.

iOS cihazlarını kaydetmeye yönelik diğer yöntemler, [Intune’da iOS cihazlarının nasıl kaydedileceğini seçme](enrollment-method-choose-ios.md) başlığı altında açıklanır.

**Intune’a Apple Configurator seri numaralarını eklemek için**

1. İki sütunlu, üst bilgisi olmayan bir virgülle ayrılmış değerler (.csv) listesi oluşturun. Sol sütuna IMEI tanımlayıcısını ve sağ sütuna ayrıntıları ekleyin. Liste için geçerli üst sınır 500 satırdır. Metin düzenleyicisinde, .csv listesi aşağıdaki gibi görünür:

    F7TLWCLBX196,cihaz ayrıntıları</br>
    DLXQPCWVGHMJ,cihaz ayrıntıları

2. Azure portalında **Cihazları kaydet**'i, ardından **Apple Kaydı**'nı seçin.
3. **Apple Configurator Kayıt Ayarlarını Yönet**’in altında, **Apple Configurator Seri Numaraları**’nı seçin.
4. **Apple Configurator Seri Numaraları** dikey penceresinde **Ekle**’yi seçin.
5. **Seri Numarası Ekle** dikey penceresinde, içeri aktardığınız seri numaralarına uygulamak için bir profil seçin. Mevcut ayrıntıların üzerine yazılacak yeni ayrıntılar içeren bir dosyayı içeri aktarıyorsanız, mevcut ayrıntıların yerini yenilerinin alması için Mevcut tanımlayıcıların ayrıntılarının üzerine yazın seçeneğini kullanın.
6. Seri numaralarının bulunduğu .csv dosyasına gidin ve **Ekle**’yi seçin.

### <a name="assign-a-profile-to-specific-serial-numbers"></a>Belirli seri numaralarına profil atama

Intune, Azure Portal’da iki farklı konumdan profil atamanıza olanak tanır. Apple Configurator profili veya cihazlara göre atayabilirsiniz.

#### <a name="assign-by-devices"></a>Cihazlara göre atama
1. Intune portalında **Cihaz kaydı**'nı, ardından **Apple Kaydı**'nı seçin.
3. **Apple Configurator Cihazları** dikey penceresinde, profil atamak istediğiniz seri numaralarını, sonra da **Profil Ata**’yı seçin.
4. **Profil Ata** dikey penceresinde atamak istediğiniz profili, sonra da **Ata**’yı seçin.

#### <a name="assign-by-profiles"></a>Profile göre atama
1. Intune portalında **Cihaz kaydı**'nı, ardından **Apple Kaydı**'nı seçin.
2. **AC Profilleri**’ni ve ardından seri numaralarını atamak istediğiniz profili seçin.
3. Profilin adını taşıyan dikey pencerede **Seri Numaraları** > **Ata**’yı seçin.
4. Profile atamak istediğiniz seri numaralarını seçin ve sonra da **Ata** düğmesini seçin.

### <a name="export-the-profile-to-ios-devices"></a>Profili iOS cihazlarına dışarı aktarma
Profili oluşturup seri numaralarını atadıktan sonra, profili bir URL veya aşağıda açıklanan biçimde bir dosya olarak Intune’dan dışarı aktarmanız gerekir. Ardından profili el ile Mac bilgisayardaki Apple Configurator programında içeri aktarırsınız ve Apple Configurator programı da bunu cihazlara dağıtır.

1. Intune portalında, **Apple Configurator Kayıt Profilleri** dikey penceresini ve dışarı aktarılacak profili seçin.
2. Profilin dikey penceresinde **Profili Dışarı Aktar**’ı seçin.
3. iOS cihazı bağlıyken profil URL'sini [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)'a kopyalayın. iOS cihazlar tarafından kullanılan Intune profilini tanımlamak için daha sonra Apple Configurator'a yüklemeniz gerekecektir.

  iOS cihazlarında kullanılan Intune profilini tanımlamak için, aşağıdaki yordamda Apple Configurator kullanarak bu profil URL’sini Apple hizmetine yükleyeceksiniz.
4. iOS cihazlarında kullanılan Intune profilini tanımlamak için, Apple Configurator’ı kullanarak bu profil URL’sini Apple hizmetine yükleyin.
 1.  Mac bilgisayarda **Apple Configurator 2**'yi açın. Menü çubuğunda **Apple Configurator 2**’yi, sonra **Tercihler**’i seçin.
  > [!WARNING]
  > Cihazlar kayıt işlemi sırasında fabrika yapılandırmalarına sıfırlanır. En iyi uygulama olarak cihazı sıfırlayın ve açın. Cihazı bağladığınızda cihazın **Merhaba** ekranında olması gerekir.
  2. **Tercihler** bölmesinde **Sunucular**’ı seçin ve MDM Sunucusu sihirbazını başlatmak için (+) artı simgesini seçin. **İleri**’yi seçin.
  3. Microsoft Intune ile iOS cihazları için Kurulum Yardımcısı kaydı altındaki MDM sunucusunun **Konak adı veya URL’si** ve **kayıt URL'sini** girin. Kayıt URL’si olarak Intune’dan dışarı aktarılan kayıt profili URL’sini girin. **İleri**’yi seçin.  

    “Sunucu URL'si doğrulanmadı” uyarısı alırsanız göz ardı edebilirsiniz. Devam etmek için sihirbaz tamamlanana kadar **İleri**’yi seçin.
  4.  iOS mobil cihazları bir USB bağdaştırıcısı ile Mac bilgisayara bağlayın.
  > [!WARNING]
  > Cihazlar kayıt işlemi sırasında fabrika yapılandırmalarına sıfırlanır. En iyi uygulama olarak cihazı sıfırlayın ve açın. Kurulum Yardımcısı’nı başlattığınızda cihazlar **Merhaba** ekranında olmalıdır.
  5.  **Hazırla**’yı seçin. **iOS Cihazını Hazırla** bölmesinde, **El ile**’yi, sonra **İleri**’yi seçin.
  6. **MDM Sunucusuna Kaydol** bölmesinde, oluşturduğunuz sunucunun adını ve sonra da **İleri**’yi seçin.
  7. **Cihazları Denetle** bölmesinde, denetim düzeyini seçin, sonra **İleri**’yi seçin.
  8. **Kuruluş Oluştur** bölmesinde **Kuruluş**’u seçin veya yeni bir kuruluş oluşturun, sonra **İleri**’yi seçin.
  9. **iOS Kurulum Yardımcısı’nı Yapılandır** bölmesinde, kullanıcıya sunulacak adımları ve sonra da **Hazırla**’yı seçin. İstenirse, güven ayarlarını güncelleştirmek için kimlik doğrulaması yapın.  
  10. iOS cihazı hazırlanmayı tamamladığında USB kablosunun bağlantısını kesin.  
6.  **Cihazları dağıtın**.
    Cihazlar artık kurumsal kayıt için hazırdır. Cihazları kapatın ve kullanıcılara dağıtın. Kullanıcılar cihazlarını açtığında Kurulum Yardımcısı başlatılır.

## <a name="direct-enrollment"></a>Doğrudan kayıt
iOS cihazlarını Apple Configurator ile doğrudan kaydederken, cihazın seri numarasını almadan kayıt işlemini gerçekleştirebilirsiniz. Ayrıca Intune kayıt sırasında cihaz adını yakalamadan önce, cihazı tanımlama amacıyla adlandırabilirsiniz. Şirket Portalı uygulaması doğrudan kayıtlı cihazlar için desteklenmez. Bu kılavuz bir Mac bilgisayarda Apple Configurator 2.0 kullandığınızı varsayar.

1. Intune portalında **Cihaz kaydı**'nı, **Apple Kaydı**'nı ve ardından **AC Profilleri**’ni seçin.
2. **Apple Configurator Kayıt Profilleri** dikey penceresinde **Oluştur**’u seçin.
3. **Kayıt Profili Oluştur** dikey penceresinde, profil için bir ad ve açıklama girin.
4. Cihazın bir kullanıcıyla ilişkili olmadığından emin olmak için **Kullanıcı Benzeşimi**’nde **Kullanıcı benzeşimi olmadan kaydet**’i seçin. Bu ilişkiyi, yerel kullanıcı verilerine erişmeden görevleri yerine getiren cihazlar için kullanın. Kullanıcı benzeşimi gerektiren uygulamalar (iş kolu uygulamalarını yüklemek için kullanılan Şirket Portalı uygulaması da dahil) çalışmaz.
5. Profili kaydetmek için **Oluştur**’u seçin.

### <a name="export-the-profile-as-mobileconfig-to-ios-devices"></a>Profili iOS cihazlarına .mobileconfig olarak dışarı aktarma

1. **Profili Dışarı Aktar** dikey penceresinde, kayıt profilini [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)'a indirerek bağlı bir iOS cihazına doğrudan bir yönetim profili olarak iletin. Bu yöntem, cihazda fabrika sıfırlaması yapmaz.
2. Aşağıdaki adımları izleyerek cihazı Apple Configurator ile hazırlayın.
  1. Mac bilgisayarda Apple Configurator 2.0'ı açın.
  2. iOS cihazını bir USB kablosu ile Mac bilgisayara bağlayın. Fotoğraflar’ı, iTunes’u ve cihaz algılandığında cihaz için açık olan diğer uygulamaları kapatın.
  3. Apple Configurator’da, bağlı iOS cihazını ve sonra **Ekle** düğmesini seçin. Cihaza eklenebilen seçenekler aşağı açılan listede görüntülenir. **Profiller**’i seçin.
  4. Intune’dan dışarı aktardığınız .mobileconfig dosyasını seçmek için dosya seçiciyi kullanın ve sonra **Ekle**’yi seçin. Profil cihaza eklenir. Cihaz Denetimsiz ise, yüklemenin cihazda kabul edilmesi gerekir.
3. Profili iOS cihazına yüklemek için aşağıdaki adımları kullanın. Cihaz, Kurulum Yardımcısı’nı zaten tamamlamış ve hazır olmalıdır. Kayıt için uygulama dağıtımları gerekiyorsa, uygulama dağıtımları App Store için imzalanmış bir Apple Kimliğiniz olmasını gerektireceğinden cihazda bir Apple Kimliği ayarlanmış olmalıdır.
   1. iOS cihazının kilidini açın.
   2. **Yönetim profili**’nin **Profili yükle** iletişim kutusunda **Yükle**’yi seçin.
   3. Gerekirse, Cihaz Geçiş Kodu veya Apple Kimliği sağlayın.
   4. **Uyarı**’yı kabul edin ve **Yükle**’yi seçin.
   5. **Uzak Uyarı**’yı kabul edin ve **Güven**’i seçin.
   6. **Profil Yüklendi** kutusu profilin Yüklü olduğunu doğruladığında **Bitti**’yi seçin.

    4. iOS cihazında **Ayarlar**’ı açın ve **Genel** > **Cihaz Yönetimi** > **Yönetim Profili**’ne gidin. Profil yüklemesinin listelendiğini onaylayın, iOS ilke kısıtlamalarını ve yüklü uygulamaları denetleyin. İlke kısıtlamaları ve uygulamaların cihazda görünmesi 10 dakika kadar sürebilir.

    5. Cihazları dağıtın. iOS cihazı Intune’a kaydedilmiştir ve yönetilmektedir.


## <a name="how-users-install-and-use-the-company-portal-on-their-devices"></a>Kullanıcıların cihazlarında Şirket Portalı’nı yüklemesi ve kullanması

Kullanıcı benzeşimi ile yapılandırılmış cihazlar, uygulama indirmek ve cihaz yönetmek için Şirket Portalı’nı yükleyip çalıştırabilir. Kullanıcılar, cihazlarını aldıktan sonra Kurulum Yardımcısı’nı tamamlamak ve Şirket Portalı uygulamasını yüklemek için aşağıda açıklanan ek adımları tamamlamalıdır.
