---
title: macOS cihazlarını kaydetme - Aygıt Kayıt Programı
titleSuffix: Microsoft Intune
description: Şirkete ait macOS cihazlarını Aygıt Kayıt Programı’nı kullanarak kaydetmeyi öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/13/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 18b4ab35627e1ccb694104f3f5800e5fb07dd1c7
ms.sourcegitcommit: 4d314df59747800169090b3a870ffbacfab1f5ed
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/30/2018
ms.locfileid: "43313435"
---
# <a name="automatically-enroll-macos-devices-with-apples-device-enrollment-program"></a>macOS cihazlarını Apple’ın Aygıt Kayıt Programı ile otomatik olarak kaydetme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bu makale, Apple’ın [Aygıt Kayıt Programı (DEP)](https://deploy.apple.com) yoluyla satın alınan cihazlar için macOS cihaz kaydını ayarlamanıza yardımcı olur. DEP kaydını cihazlara hiç dokunmadan çok sayıda cihaz için ayarlayabilirsiniz. macOS cihazlarını doğrudan kullanıcılara gönderebilirsiniz. Kullanıcı cihazı açtığında, önceden yapılandırılmış ayarları ile Kurulum Yardımcısı çalıştırılır ve cihaz Intune yönetimine kaydedilir.

DEP kaydını ayarlamak için Intune ve Apple DEP portallarını birlikte kullanmanız gerekir. Kayıt sırasında cihazlara uygulanan ayarları içeren DEP kayıt profilleri oluşturun.

Bu arada, DEP kaydının [cihaz kayıt yöneticisiyle](device-enrollment-manager-enroll.md) birlikte kullanılamayacağına dikkat edin.

<!--
**Steps to enable enrollment programs from Apple**
1. [Get an Apple DEP token and assign devices](#get-the-apple-dep-token)
2. [Create an enrollment profile](#create-an-apple-enrollment-profile)
3. [Synchronize DEP-managed devices](#sync-managed-device)
4. [Assign DEP profile to devices](#assign-an-enrollment-profile-to-devices)
5. [Distribute devices to users](#end-user-experience-with-managed-devices)
-->
## <a name="prerequisites"></a>Önkoşullar
- [Apple Aygıt Kayıt Programı](http://deploy.apple.com)’nda satın alınmış cihazlar
- Seri numarası listesi veya satın alma sipariş numarası. 
- [MDM Yetkilisi](mdm-authority-set.md)
- [Apple MDM Anında İletme sertifikası](apple-mdm-push-certificate-get.md)

## <a name="get-an-apple-dep-token"></a>Bir Apple DEP belirteci alma

macOS cihazlarını DEP ile kaydedebilmeniz için bir Apple DEP belirteci dosyasına (.p7m) ihtiyacınız vardır. Bu belirteç, Intune'un şirketinize ait olan DEP cihazları hakkındaki bilgileri eşitlemesini sağlar. Ayrıca Intune'un kayıt profillerini Apple’a yüklemesini ve bu profilleri cihazlara atamasını da sağlar.

DEP belirtecini oluşturmak için Apple DEP portalını kullanın. Cihazları yönetim için Intune’a atamak için DEP portalını da kullanabilirsiniz.

> [!NOTE]
> Belirteci Azure’a geçirmeden önce klasik Intune portalında silerseniz Intune, silinen bir Apple DEP belirtecini geri yükleyebilir. DEP belirtecini Azure portalından tekrar silebilirsiniz.

### <a name="step-1-download-the-intune-public-key-certificate-required-to-create-the-token"></a>1. Adım Belirteci oluşturmak için gereken Intune ortak anahtar sertifikasını indirin.

1. [Azure portalında Intune](https://aka.ms/intuneportal)’da, **Cihaz kaydı** > **Apple kaydı** > **Kayıt Programı Belirteçleri** > **Ekle**’yi seçin.

    ![Bir kayıt programı belirteci alın.](./media/device-enrollment-program-enroll-ios/image01.png)

2. **Onaylıyorum**’u seçerek Microsoft’un Apple’a kullanıcı ve cihaz bilgilerini göndermesine izin verin.

   ![Apple Sertifikaları çalışma alanındaki Kayıt Programı Belirteci panelinde bulunan ortak anahtarı indirme öğesinin ekran görüntüsü.](./media/device-enrollment-program-enroll-ios-newui/add-enrollment-program-token-pane.png)

3. Şifreleme dosyasını (.pem) indirmek ve yerel olarak kaydetmek için **Ortak anahtarınızı indirin** öğesini seçin. .pem dosyası Apple Cihaz Kayıt Programı portalından güven ilişkisi sertifikası istemek için kullanılır.


### <a name="step-2-use-your-key-to-download-a-token-from-apple"></a>2. Adım Anahtarınızı kullanarak Apple’dan bir belirteç indirin.

1. Apple’ın Dağıtım Programı portalını açmak için **Apple’ın Aygıt Kayıt Programı için bir belirteç oluştur**’u seçin ve şirket Apple Kimliğinizle oturum açın. DEP belirtecinizi yenilemek için de bu Apple kimliğini kullanabilirsiniz.
2.  Apple’ın [Dağıtım Programları portalında](https://deploy.apple.com), **Aygıt Kayıt Programı** için **Kullanmaya Başla**’yı seçin.

3. **Sunucuları Yönet** sayfasında **MDM Sunucusu Ekle**’yi seçin.
4. **MDM Sunucu Adı**'nı girin ve ardından **İleri**'yi seçin. Sunucu adı, mobil cihaz yönetimi (MDM) sunucusunu tanımlarken kullanmanız içindir. Microsoft Intune sunucusunun adı veya URL'si değildir.

5. **Ekle &lt;ServerName&gt;** iletişim kutusu açılır ve **Ortak Anahtarınızı Yükleyin** ifadesi yazar. **Dosya Seç…** öğesini seçin .pem dosyasını karşıya yükleyin ve ardından **İleri**'yi seçin.

6. **Dağıtım Programları** &gt; **Cihaz Kayıt Programı** &gt; **Cihazları Yönet**'e gidin.
7. **Cihazları Şuna Göre Seç:** öğesinin altında cihazların nasıl tanımlanacağını belirtin:
    - **Seri Numarası**
    - **Sipariş Numarası**
    - **CSV Dosyası Yükle**.

   ![Cihazları seri numarasına göre seçme, eylem seç öğesini Sunucuya ata olarak seçme ve sunucu adını seçme ekran görüntüsü.](./media/enrollment-program-token-specify-serial.png)

8. **Eylem Seç** işlemi için **Sunucuya Ata**’yı ve Microsoft Intune için belirtilen &lt;ServerName&gt; öğesini belirleyip **Tamam**'ı seçin. Apple portalı, belirtilen cihazları Intune sunucusunda yönetilmek üzere bu sunucuya atar ve **Atama Tamamlandı** ifadesini görüntüler.

   Apple portalında **Dağıtım Programları** &gt; **Aygıt Kayıt Programı** &gt; **Atama Geçmişini Görüntüle**’ye giderek cihazların listesi ile MDM sunucu atamalarına göz atabilirsiniz.

### <a name="step-3-save-the-apple-id-used-to-create-this-token"></a>3. Adım. Bu belirteci oluşturmak için kullanılan Apple kimliğini kaydedin.

Azure portalında Intune’da ileride başvurmak üzere Apple kimliğini sağlayın.

![Kayıt programı belirtecini oluşturmak için kullanılan Apple kimliğini belirtme ve kayıt programı belirtecine gözatma işleminin ekran görüntüsü.](./media/device-enrollment-program-enroll-ios/image03.png)

### <a name="step-4-upload-your-token"></a>Adım 4. Belirtecinizi karşıya yükleyin.
**Apple belirteci** kutusunda sertifika (.pem) dosyasına gözatın, **Aç**’ı ve daha sonra **Oluştur**’u seçin. Anında iletme sertifikasıyla, Intune ilkeyi kayıtlı cihazlara ileterek macOS cihazlarını kaydedebilir ve yönetebilir. Intune, kayıt programı hesabınızı görmek için Apple ile otomatik olarak eşitlenir.

## <a name="create-an-apple-enrollment-profile"></a>Apple kayıt profili oluşturma

Belirtecinizi yüklediğinize göre, DEP cihazları için kayıt profili oluşturabilirsiniz. Bir cihaz kayıt profili, kayıt sırasında bir grup cihaza uygulanan ayarları tanımlar.

1. Azure portalında Intune’da, **Cihaz kaydı** > **Apple kaydı** > **Kayıt programı belirteçleri**’ni seçin.
2. Bir belirteç seçin, **Profiller**’e ve daha sonra **Profil oluştur**’a tıklayın.

    ![Profil oluşturma ekran görüntüsü.](./media/device-enrollment-program-enroll-ios/image04.png)

3. **Profil Oluştur**’un altında, yönetim amaçları doğrultusunda profil için bir **Ad** ve **Açıklama** girin. Kullanıcılar bu ayrıntıları göremez. Azure Active Directory’de dinamik bir grup oluşturmak için **Ad** alanını kullanabilirsiniz. enrollmentProfileName parametresini, bu kayıt profiliyle cihazlara atamak amacıyla tanımlamak için profil adını kullanın. [Azure Active Directory dinamik grupları](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal#using-attributes-to-create-rules-for-device-objects) hakkında daha fazla bilgi edinin.

    ![Profil adı ve açıklaması.](./media/device-enrollment-program-enroll-macos/createprofile.png)

4. **Platform** olarak **macOS** seçin.

5. **Kullanıcı Benzeşimi** için bu profile sahip cihazların atanan kullanıcıyla mı yoksa atanan kullanıcı olmadan mı kaydedilmesi gerektiğini seçin.
    - **Kullanıcı Benzeşimi ile kaydet** - Uygulamaları yükleme gibi hizmetler için Şirket Portalı uygulamasını kullanmak isteyen kullanıcılara ait cihazlar için bu seçeneği belirtin. ADFS kullanılıyorsa kullanıcı benzeşimi [WS-Trust 1.3 Kullanıcı adı/Karma uç noktası](https://technet.microsoft.com/library/adfs2-help-endpoints) gerektirir. [Daha fazla bilgi](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint). Kullanıcı benzeşimi olan macOS DEP cihazlarında çok faktörlü kimlik doğrulaması desteklenmez.

    - **Kullanıcı Benzeşimi Olmadan Kaydetme** - Tek bir kullanıcıyla bağlantılı olmayan cihazlar için bu seçeneği seçin. Yerel kullanıcı verilerine erişmeden görevleri yerine getiren cihazlar için bunu kullanın. Şirket Portalı uygulaması gibi uygulamalar çalışmaz.

6. **Cihaz Yönetim Ayarları**’nı seçin ve bu profili kullanan cihazlar için kilitli kayıt isteyip istemediğinizi belirtin. **Kilitli kayıt**, yönetim profilinin **Sistem Tercihleri** menüsünden veya **Terminal** aracılığıyla kaldırılmasını sağlayan macOS ayarlarını devre dışı bırakır. Cihazı kaydettikten sonra cihazı silmeden bu ayarı değiştiremezsiniz.

    ![Cihaz Yönetimi Ayarları ekran görüntüsü.](./media/device-enrollment-program-enroll-macos/devicemanagementsettingsblade-macos.png)
 
7. **Tamam**’ı seçin.

8. Şu profil ayarlarını yapılandırmak için **Kurulum Yardımcısı Ayarları**’nı seçin: ![Kurulum Yardımcısı Özelleştirme.](./media/device-enrollment-program-enroll-macos/setupassistantcustom-macos.png)

    | Departman ayarları | Description |
    |---|---|
    | <strong>Departman Adı</strong> | Kullanıcı, etkinleştirme sırasında <strong>Yapılandırma Hakkında</strong> öğesine dokunduğunda görüntülenir. |
    | <strong>Departman Telefonu</strong> | Kullanıcı, etkinleştirme sırasında <strong>Yardım Gerekli</strong> düğmesine dokunduğunda görüntülenir. |

  Kullanıcı kurulum yaparken cihazda çeşitli Kurulum Yardımcısı ekranlarının gösterilmesini veya gizlenmesini seçebilirsiniz.
  - **Gizle**'yi seçerseniz, kurulum sırasında ekran görüntülenmez. Cihaz kurulumu yapıldıktan sonra, kullanıcı yine **Ayarlar** menüsüne gidip özelliği ayarlayabilir.
  - **Göster**'i seçerseniz, kurulum sırasında ekran görüntülenir. Kullanıcı bazen hiçbir eylem yapmadan ekranı atlayabilir. Ama daha sonra cihazın **Ayarlar** menüsüne gidebilir ve özelliği ayarlayabilir. 


    | Kurulum Yardımcısı ekran ayarları | **Göster**'i seçerseniz, kurulum sırasında cihaz... |
    |------------------------------------------|------------------------------------------|
    | <strong>Geçiş kodu</strong> | Kullanıcıdan geçiş kodu ister. Cihazın güvenliği sağlanmayacaksa veya erişim denetimi başka bir yolla (cihazı tek uygulamayla sınırlandıran bilgi noktası modu) uygulanmayacaksa her zaman geçiş kodu gerektirir. |
    | <strong>Konum Hizmetleri</strong> | Kullanıcıdan konum ister. |
    | <strong>Geri Yükle</strong> | **Uygulamalar ve Veriler** ekranını görüntüler. Bu ekran kullanıcıya cihazı kurarken iCloud Backup'tan verileri geri yükleme veya aktarma seçeneği sağlar. |
    | <strong>iCloud ve Apple Kimliği</strong> | Kullanıcıya **Apple Kimliği** ile oturum açma ve **iCloud**'u kullanma seçenekleri sağlar.                         |
    | <strong>Hüküm ve Koşullar</strong> | Kullanıcının Apple'ın hüküm ve koşullarını kabul etmesini gerektirir. |
    | <strong>Touch ID</strong> | Kullanıcıya cihaz için parmak izi tanımlama özelliğini ayarlama seçeneği sağlar. |
    | <strong>Apple Pay</strong> | Kullanıcıya cihazda Apple Pay ayarlama seçeneği sağlar. |
    | <strong>Yakınlaştır</strong> | Kullanıcıya cihazı ayarlarken ekranı yakınlaştırma seçeneği sağlar. |
    | <strong>Siri</strong> | Kullanıcıya Siri'yi ayarlama seçeneği sağlar. |
    | <strong>Tanılama Verileri</strong> | Kullanıcıya **Tanılama** ekranını görüntüler. Bu ekran kullanıcıya Apple'a tanılama verileri gönderme seçeneği sağlar. |
    | <strong>FileVault</strong> | Kullanıcıya FileVault şifrelemesini ayarlama seçeneği sağlar. |
    | <strong>iCloud Tanılaması</strong> | Kullanıcıya Apple'a iCloud tanılama verileri gönderme seçeneği sağlar. |
    | <strong>Kayıt</strong>| Kullanıcının cihazı kaydetmesini gerektirir. |

   

10. **Tamam**’ı seçin.

11. Profili kaydetmek için **Oluştur**’u seçin.

## <a name="sync-managed-devices"></a>Yönetilen cihazları eşitleme
Artık Intune’a cihazlarınızı yönetme izni verildiğine göre, yönetilen cihazlarınızı Intune’da Azure portalında görmek için Intune’u Apple ile eşitleyebilirsiniz.

1. Azure portalında Intune’da, **Cihaz kaydı** > **Apple Kaydı** > **Kayıt programı belirteçleri** > listeden bir belirteç seçin > **Cihazlar** > **Eşitle**’yi seçin. ![Kayıt Programı Cihazları düğümünün seçili olduğu ve Eşitle bağlantısının seçildiği ekran görüntüsü.](./media/device-enrollment-program-enroll-ios/image06.png)

   Intune, Apple’ın kabul edilebilir kayıt programı trafiği şartlarına uymak için aşağıdaki kısıtlamaları getirir:
   - Tam eşitleme en sık yedi günde bir çalıştırılabilir. Tam eşitleme sırasında Intune, Intune’a bağlı Apple MDM sunucusuna atanan seri numaraların tam güncelleştirilmiş bir listesini alır. Bir Kayıt Programı cihazı, cihaz ataması DEP portalında Apple MDM sunucusundan kaldırılmadan Intune portalından silinirse, tam eşitleme çalıştırılana kadar Intune’a tekrar içeri aktarılmaz.   
   - Eşitleme 24 saatte bir otomatik olarak çalıştırılır. **Eşitle** düğmesine basarak da eşitleyebilirsiniz (en fazla 15 dakikada bir kez). Tüm eşitleme isteklerinin tamamlanması için 15 dakika verilir. Eşitleme tamamlanana kadar **Eşitle** düğmesi devre dışı kalır. Bu eşitleme, mevcut aygıt durumunu yeniler ve Apple MDM sunucusuna atanan yeni cihazları içeri aktarır.   


## <a name="assign-an-enrollment-profile-to-devices"></a>Cihazlara kayıt profili atama
Cihazların kaydedilmesi için bunlara bir kayıt programı profili atamalısınız.

1. Azure portalında Intune’da, **Cihaz kaydı** > **Apple Kaydı** > **Kayıt programı belirteçleri** > listeden bir belirteç seçin.
2. **Cihazlar** > listeden cihazları seçin > **Profil ata**’yı seçin.
3. **Profil ata**'nın altında cihazlar için bir profil seçin > **Ata**’ya tıklayın.

### <a name="assign-a-default-profile"></a>Varsayılan bir profil atama

Belirli bir belirteç ile kaydedilen tüm cihazlara uygulanacak varsayılan bir macOs ve iOS profili seçebilirsiniz. 

1. Azure portalında Intune’da, **Cihaz kaydı** > **Apple kaydı** > **Kayıt programı belirteçleri** > listeden bir belirteç seçin.
2. **Varsayılan Profil Ayarla**’yı seçin, açılan listeden bir profil seçin ve daha sonra **Kaydet**’e tıklayın. Profil, bu belirteçle kaydedilen tüm cihazlara uygulanacaktır.

## <a name="distribute-devices"></a>Cihazları dağıtma
Apple ve Intune arasında eşitlemeyi ve yönetimi etkinleştirdiniz ve DEP cihazlarınızın kaydolmasına izin vermek için bir profil atadınız. Artık cihazları kullanıcılara dağıtabilirsiniz. Kullanıcı benzeşimli cihazlar, her kullanıcıya bir Intune lisansı atanmasını gerektirir. Kullanıcı benzeşimi olmayan cihazlar, cihaz lisansı gerektirir. Etkinleştirilmiş bir cihaz, silinene kadar bir kayıt profili uygulayamaz.

## <a name="renew-a-dep-token"></a>DEP belirtecini yenileme  
1. deploy.apple.com adresine gidin.  
2. **Sunucuları Yönet** altında yenilemek istediğiniz belirteç dosyasıyla ilişkili MDM sunucunuzu seçin.
3. **Yeni Belirteç Oluştur**’u seçin.

    ![Yeni belirteç oluşturma ekran görüntüsü.](./media/device-enrollment-program-enroll-ios/generatenewtoken.png)

4. **Sunucu Belirteciniz**’i seçin.  
5. [Azure portalında Intune](https://aka.ms/intuneportal)’da, **Cihaz kaydı** > **Apple Kaydı** > **Kayıt programı belirteçleri**’ne gidin ve belirteci seçin.
    ![Kayıt programı belirteçlerinin ekran görüntüsü.](./media/device-enrollment-program-enroll-ios/enrollmentprogramtokens.png)

6. **Belirteci yenile**’yi seçin ve orijinal belirteci oluşturmak için kullanılan Apple kimliğini girin.  
    ![Yeni belirteç oluşturma ekran görüntüsü.](./media/device-enrollment-program-enroll-ios/renewtoken.png)

8. Yeni indirilen belirteci karşıya yükleyin.  
9. **Belirteci yenile**’yi seçin. Belirtecin yenilendiğine dair onayı görürsünüz.   
    ![Onay ekran görüntüsü.](./media/device-enrollment-program-enroll-ios/confirmation.png)

## <a name="next-steps"></a>Sonraki adımlar

macOS cihazlarını kaydettikten sonra [bunları yönetmeye](device-management.md) başlayabilirsiniz.