---
title: "iOS cihazlarını kaydetme- Apple Configurator-Kurulum Yardımcısı"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Kurulum Yardımcısı’nı kullanarak şirkete ait iOS cihazlarını kaydetmek için Apple Configurator’ı kullanmayı öğrenin."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 04/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d384cd0-b662-41e7-94f5-0c96790ab20a
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: e6b0bc51515a2b72c7574a7ca7e29c094f3bdbdb
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---

# <a name="enroll-ios-devices-with-apple-configurator-and-setup-assistant"></a>Apple Configurator ve Kurulum Yardımcısı ile iOS cihazlarını kaydetme

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Intune, bir Mac bilgisayarda çalıştırılan [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) kullanarak şirketin sahip olduğu iOS cihazlarının kaydedilmesini destekler. Bu işlem cihazı fabrika ayarlarına sıfırlar, Kurulum Yardımcısı’nı çalıştırmaya hazırlar ve cihazın yeni kullanıcısı için şirketin ilkelerini yükler.

>[!NOTE]
>Bu kayıt yöntemi, [cihaz kaydı yöneticisi](device-enrollment-manager-enroll.md) yöntemiyle birlikte kullanılamaz.

Apple Configurator kullanarak, bir iOS cihazını fabrika ayarlarına sıfırlayabilir ve cihazın yeni kullanıcısı için ayarlanmak üzere hazırlayabilirsiniz. Bu yöntem, kurumsal kayıt kurulumu için iOS cihazını USB ile bir Mac bilgisayara bağlamanızı gerektirir ve Apple Configurator 2.0 kullandığınızı varsayar. Çoğu senaryoda, Intune Şirket Portalı uygulamasını etkinleştirmek için iOS cihazına uygulanmış olan ilkenin kullanıcı benzeşimi içermesi gerekir.

iOS cihazlarını kaydetmeye yönelik diğer yöntemler, [Intune’da iOS cihazlarının nasıl kaydedileceğini seçme](enrollment-method-choose-ios.md) başlığı altında açıklanır.

## <a name="prerequisites"></a>Önkoşullar

iOS cihaz kaydını ayarlamadan önce, aşağıdaki önkoşulları tamamlayın:

- [Bir MDM anında iletme sertifikası alma](apple-mdm-push-certificate-get.md)
- iOS cihazlarına fiziksel erişiminizin olduğundan emin olun
- Cihaz seri numaralarına sahip olun (bkz. [iOS seri numarası alma](https://support.apple.com//HT204308))
- USB bağlantı kablolarını hazır bulundurun
- [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)’ın yüklü olduğu bir Mac bilgisayarınızın olduğundan emin olun
- [Apple Configurator seri numaraları ekleme](apple-configurator-serial-numbers-add.md)


## <a name="create-an-apple-configurator-profile-for-devices"></a>Cihazlar için Apple Configurator profili oluşturma

Cihaz kayıt profili bir cihaz grubuna uygulanan ayarları tanımlar. Aşağıdaki adımları, Apple Configurator kullanarak kaydedilmiş iOS cihazları için bir cihaz kayıt profilinin nasıl oluşturulacağını gösterir.

1. Azure portalında **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.

2. Intune dikey penceresinde **Cihazları kaydet**’i ve ardından **Apple Kaydı**’nı seçin.

3. **Apple Configurator Kayıt Ayarlarını Yönet**’in altında, **AC Profilleri**’ni seçin.

4. **Apple Configurator Kayıt Profilleri** dikey penceresinde **Oluştur**’u seçin.

5. **Kayıt Profili Oluştur** dikey penceresinde, profil için bir ad ve açıklama girin.

6. **Kullanıcı Benzeşimi** için, bu profile sahip cihazların kullanıcı benzeşimiyle mi yoksa kullanıcı benzeşimi olmadan mı kaydedileceğini seçin.

   - **Kullanıcı benzeşimiyle kaydet** - Cihaz ilk kurulum sırasında bir kullanıcıya bağlı olmalıdır. Böylece, cihazın şirket verilerine ve e-postalara erişmesine izin verilebilir. Yönetilen kullanıcılara ait olan ve uygulama yüklemek gibi hizmetler için şirket portalını kullanması gereken cihazlarda kullanıcı benzeşimi ayarlanmalıdır.

   - **Kullanıcı benzeşimi olmadan kaydet** - Cihaz bir kullanıcıya bağlı değildir. Bu ilişkiyi, yerel kullanıcı verilerine erişmeden görevleri yerine getiren cihazlar için kullanın. Kullanıcı benzeşimi gerektiren uygulamalar (iş kolu uygulamalarını yüklemek için kullanılan Şirket Portalı uygulaması da dahil) çalışmaz.

7. Profili kaydetmek için **Oluştur**’u seçin.

## <a name="assign-serial-numbers-to-an-apple-configurator-profile"></a>Apple Configurator profiline seri numaraları atama

Apple Configurator profillerini oluşturduktan sonra, profillere cihaz seri numaraları atayabilirsiniz. Seri numaralarını atayabilmek için, önce [Apple Configurator seri numaraları ekleme](apple-configurator-serial-numbers-add.md) başlığı altında verilen adımları izleyerek bunları Intune’a eklemeniz gerekir.

### <a name="assign-serial-numbers-to-apple-configurator-profiles"></a>Apple Configurator profillerine seri numaraları atama

1. Azure portalında **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.

2. **Apple Configurator Enrollment Profilleri** dikey penceresinde, seri numaralarını atamak istediğiniz profili seçin.

3. Profilin adını taşıyan dikey pencerede **Seri Numaraları** > **Ata**’yı seçin.

4. Profile atamak istediğiniz seri numaralarını seçin ve sonra da **Ata** düğmesini seçin.

## <a name="export-the-profile-to-ios-devices"></a>Profili iOS cihazlarına dışarı aktarma

Profili oluşturup seri numaralarını atadıktan sonra, profili bir URL veya aşağıda açıklanan biçimde bir dosya olarak Intune’dan dışarı aktarmanız gerekir. Ardından profili el ile Mac bilgisayardaki Apple Configurator programında içeri aktarırsınız ve Apple Configurator programı da bunu cihazlara dağıtır.

### <a name="export-a-profile-using-setup-assistant-enrollment"></a>Kurulum Yardımcısı kaydını kullanarak profili dışarı aktarma

1. Azure portalında **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.

2. **Apple Configurator Kayıt Profilleri** dikey penceresinde, dışarı aktarılacak profili seçin.

3. Profilin dikey penceresinde **Profili Dışarı Aktar**’ı seçin.

4. iOS cihazı bağlıyken profil URL'sini [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)'a kopyalayın. iOS cihazlar tarafından kullanılan Intune profilini tanımlamak için daha sonra Apple Configurator'a yüklemeniz gerekecektir.

  iOS cihazlarında kullanılan Intune profilini tanımlamak için, aşağıdaki yordamda Apple Configurator kullanarak bu profil URL’sini Apple hizmetine yükleyeceksiniz.

5. iOS cihazlarında kullanılan Intune profilini tanımlamak için, Apple Configurator’ı kullanarak bu profil URL’sini Apple hizmetine yükleyin.
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

    Bkz. [Son kullanıcılarınızı Microsoft Intune hakkında bilgilendirme](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune). Son kullanıcılarınızı [iOS veya macOS cihazınızı Intune ile kullanma](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune) konusuna da yönlendirebilirsiniz.

## <a name="how-users-install-and-use-the-company-portal-on-their-devices"></a>Kullanıcıların cihazlarında Şirket Portalı’nı yüklemesi ve kullanması

Kullanıcı benzeşimi ile yapılandırılmış cihazlar, uygulama indirmek ve cihaz yönetmek için Şirket Portalı’nı yükleyip çalıştırabilir. Kullanıcılar, cihazlarını aldıktan sonra Kurulum Yardımcısı’nı tamamlamak ve Şirket Portalı uygulamasını yüklemek için aşağıda açıklanan ek adımları tamamlamalıdır.

