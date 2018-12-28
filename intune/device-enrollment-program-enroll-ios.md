---
title: iOS cihazlarını kaydetme - Cihaz Kayıt Programı
titleSuffix: Microsoft Intune
description: Şirkete ait iOS cihazları Aygıt Kayıt Programı’nı kullanarak kaydetmeyi öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/04/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 7ddbf360-0c61-11e8-ba89-0ed5f89f718b
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: 1af474063ec7b6ccac2a36afbec421767f79444a
ms.sourcegitcommit: 4e69a8664c289263490daa4c02bc6b81c33196e5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2018
ms.locfileid: "53642855"
---
# <a name="automatically-enroll-ios-devices-with-apples-device-enrollment-program"></a>iOS cihazlarını Apple’ın Aygıt Kayıt Programı ile otomatik olarak kaydetme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune'u Apple ile satın alınan iOS cihazlarını kaydetmek için ayarlayabileceğiniz [cihaz kayıt programı (DEP)](https://deploy.apple.com). DEP kaydını hiç dokunmadan birçok sayıda cihaz için etkinleştirebilirsiniz. iPhone ve iPad’ler gibi cihazları doğrudan kullanıcılara sevk edebilirsiniz. Kullanıcı cihazı açtığında, önceden yapılandırılmış ayarları ile Kurulum Yardımcısı çalıştırılır ve cihaz yönetime kaydedilir.

DEP kaydını etkinleştirmek için Intune ve Apple DEP portallarını birlikte kullanmanız gerekir. Cihazlarınızı, Intune ile yönetilmek üzere atayabilmeniz için seri numaraları listesi veya sipariş numarası gereklidir. Kayıt sırasında cihazlara uygulanan ayarları içeren DEP kayıt profilleri oluşturun.

Bu arada, DEP kaydının [cihaz kayıt yöneticisiyle](device-enrollment-manager-enroll.md) birlikte kullanılamayacağına dikkat edin.

## <a name="what-is-supervised-mode"></a>Denetimli mod nedir?
Apple, iOS 5 sürümünde denetimli modu kullanıma sundu. Denetimli moddaki herhangi bir iOS cihaz, daha fazla denetimle yönetilebilir. O neden bu mod, özellikle şirkete ait cihazlar için kullanışlıdır. Intune, Apple Aygıt Kayıt Programı’nın (DEP) bir parçası olarak denetimli mod için cihazların yapılandırılmasını destekler. 

Denetlenmeyen DEP cihazları destek iOS 11'de sona ermiştir. iOS 11 ve üstünde, DEP yapılandırmalı cihazların her zaman denetimli olması gerekir. Gelecekteki bir iOS sürümünde DEP denetimli bayrağı yoksayılacaktır.

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
- [MDM Yetkilisi](mdm-authority-set.md)
- [Apple MDM Anında İletme sertifikası](apple-mdm-push-certificate-get.md)

## <a name="get-an-apple-dep-token"></a>Bir Apple DEP belirteci alma

iOS cihazlarını DEP ile kaydedebilmeniz için bir Apple DEP belirteci dosyasına (.p7m) ihtiyacınız vardır. Bu belirteç, Intune'un şirketinize ait olan DEP cihazları hakkındaki bilgileri eşitlemesini sağlar. Ayrıca Intune'un kayıt profilini Apple'a yüklemesine ve cihazları bu profillere atamasına izin verir.

DEP belirtecini oluşturmak için Apple DEP portalını kullanın. Cihazları yönetim için Intune’a atamak için DEP portalını da kullanabilirsiniz.

> [!NOTE]
> Belirteci Azure’a geçirmeden önce klasik Intune portalında silerseniz Intune, silinen bir Apple DEP belirtecini geri yükleyebilir. DEP belirtecini Azure portalından tekrar silebilirsiniz.

### <a name="step-1-download-the-intune-public-key-certificate-required-to-create-the-token"></a>Adım 1. Belirteci oluşturmak için gereken Intune ortak anahtar sertifikasını indirin.

1. [Azure portalında Intune'da](https://aka.ms/intuneportal), **Cihaz kaydı** > **Apple kaydı** > **Kayıt Programı Belirteçleri** > **Ekle**'yi seçin.

    ![Bir kayıt programı belirteci alın.](./media/device-enrollment-program-enroll-ios/image01.png)

2. **Onaylıyorum**’u seçerek Microsoft’un Apple’a kullanıcı ve cihaz bilgilerini göndermesine izin verin.

   ![Apple Sertifikaları çalışma alanındaki Kayıt Programı Belirteci panelinde bulunan ortak anahtarı indirme öğesinin ekran görüntüsü.](./media/device-enrollment-program-enroll-ios-newui/add-enrollment-program-token-pane.png)

3. Şifreleme dosyasını (.pem) indirmek ve yerel olarak kaydetmek için **Ortak anahtarınızı indirin** öğesini seçin. .pem dosyası Apple Cihaz Kayıt Programı portalından güven ilişkisi sertifikası istemek için kullanılır.


### <a name="step-2-use-your-key-to-download-a-token-from-apple"></a>Adım 2. Anahtarınızı kullanarak Apple’dan bir belirteç indirin.

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

### <a name="step-3-save-the-apple-id-used-to-create-this-token"></a>Adım 3. Bu belirteci oluşturmak için kullanılan Apple kimliğini kaydedin.

Azure portalında Intune’da ileride başvurmak üzere Apple kimliğini sağlayın.

![Kayıt programı belirtecini oluşturmak için kullanılan Apple kimliğini belirtme ve kayıt programı belirtecine gözatma işleminin ekran görüntüsü.](./media/device-enrollment-program-enroll-ios/image03.png)

### <a name="step-4-upload-your-token"></a>4. adımı. Belirtecinizi karşıya yükleyin.
**Apple belirteci** kutusunda sertifika (.pem) dosyasına gözatın, **Aç**’ı ve daha sonra **Oluştur**’u seçin. Anında iletme sertifikasıyla, Intune ilkeyi kayıtlı mobil cihazlara ileterek iOS cihazları kaydedebilir ve yönetebilir. Intune, kayıt programı hesabınızı görmek için Apple ile otomatik olarak eşitlenir.

## <a name="create-an-apple-enrollment-profile"></a>Apple kayıt profili oluşturma

Belirtecinizi yüklediğinize göre, DEP cihazları için kayıt profili oluşturabilirsiniz. Bir cihaz kayıt profili, kayıt sırasında bir grup cihaza uygulanan ayarları tanımlar.

> [!NOTE]
> Cihazları, bir VPP belirteci için yeterli Şirket portalı lisansları varsa ya da belirtecin süresinin dolması halinde engellenir. Intune, bir uyarı görüntülenir lisansları veya whne bir belirteçtir dolmak üzere çalışan düşük.
 

1. Azure portalında Intune’da, **Cihaz kaydı** > **Apple kaydı** > **Kayıt programı belirteçleri**’ni seçin.
2. Bir belirteç seçin, **Profiller**’e ve daha sonra **Profil oluştur**’a tıklayın.

    ![Profil oluşturma ekran görüntüsü.](./media/device-enrollment-program-enroll-ios/image04.png)

3. **Profil Oluştur**’un altında, yönetim amaçları doğrultusunda profil için bir **Ad** ve **Açıklama** girin. Kullanıcılar bu ayrıntıları göremez. Azure Active Directory’de dinamik bir grup oluşturmak için **Ad** alanını kullanabilirsiniz. enrollmentProfileName parametresini, bu kayıt profiliyle cihazlara atamak amacıyla tanımlamak için profil adını kullanın. [Azure Active Directory dinamik grupları](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal#using-attributes-to-create-rules-for-device-objects) hakkında daha fazla bilgi edinin.

    ![Profil adı ve açıklaması.](./media/device-enrollment-program-enroll-ios/image05.png)

4. **Kullanıcı Benzeşimi** için bu profile sahip cihazların atanan kullanıcıyla mı yoksa atanan kullanıcı olmadan mı kaydedilmesi gerektiğini seçin.
    - **Kullanıcı Benzeşimi ile Kaydet** - Uygulamaları yükleme gibi hizmetler için Şirket Portalı’nı kullanmak isteyen kullanıcılara ait cihazlar için bu seçeneği seçin. ADFS kullanılıyorsa ve kayıt profilinde **Kurulum Yardımcısı yerine Şirket Portalı ile kimliği doğrula** ayarı **Hayır** değerine ayarlandıysa, [WS-Trust 1.3 Kullanıcı adı/Karma uç noktası](https://technet.microsoft.com/library/adfs2-help-endpoints) [Daha fazla bilgi edinin](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint) gerekir.

    - **Kullanıcı Benzeşimi Olmadan Kaydetme** - Tek bir kullanıcıyla bağlantılı olmayan cihazlar için bu seçeneği seçin. Yerel kullanıcı verilerine erişmeden görevleri yerine getiren cihazlar için bu seçeneği kullanın. Şirket Portalı uygulaması gibi uygulamalar çalışmaz.

5. **Kullanıcı Benzeşimi ile Kaydet**’i seçerseniz, kullanıcıların Şirket Portalı yerine Apple Kurulum Yardımcısı ile kimlik doğrulamalarına izin verme seçeneğiniz olur.

    ![Şirket Portalı ile kimlik doğrulayın.](./media/device-enrollment-program-enroll-ios/authenticatewithcompanyportal.png)

    > [!NOTE]
    > Aşağıdakilerden herhangi birini yapmak istiyorsanız, **Apple Kurulum Yardımcısı yerine Şirket Portalı ile kimliği doğrula** ayarını **Evet** değerine ayarlayın.
    >    - çok faktörlü kimlik doğrulaması kullanma
    >    - ilk kez oturum açarken parolalarını değiştirmesi gereken kullanıcılara bunu bildirme
    >    - kayıt sırasında kullanıcılardan süresi dolmuş parolalarını sıfırlamalarını isteme
    >
    > Apple Kurulum Yardımcısı ile kimliği doğrularken bunlar desteklenmez.

6. **Apple Kurulum Yardımcısı yerine Şirket Portalı ile kimlik doğrulaması yap** için **Evet**'i seçtiyseniz, kullanıcının Apple Kimliği'ni sağlamadan cihazda Şirket Portalı'nı otomatik olarak yüklemek için Volume Purchase Program (VPP) belirtecini kullanma seçeneğiniz vardır. VPP belirteciyle Şirket Portalı'nı yüklemek için, **VPP ile Şirket Portalı yükle**'nin altında bir belirteç seçin. Belirtecin süresinin dolmadığından ve Şirket Portalı uygulaması için yeterli cihaz lisansınız olduğundan emin olun. Belirtecin süresi dolarsa veya yeterli lisans yoksa, Intune bunun yerine App Store Şirket Portalı’nı yükler ve Apple Kimliği ister.

    ![VPP ile şirket portalı yükle ekran görüntüsü.](./media/device-enrollment-program-enroll-ios/install-cp-with-vpp.png)

7. **Şirket Portalı’nı VPP ile yükle** seçeneği için bir belirteç seçtiyseniz Kurulum Yardımcısı tamamlandıktan hemen sonra cihazı Tekli Uygulama Moduna (yani Şirket Portalı uygulaması için) kilitleme imkanınız vardır. Bunun için **Kimlik doğrulaması tamamlanana kadar Şirket Portalı’nı Tekli Uygulama Modunda çalıştır** ayarını **Evet** olarak ayarlayın. Cihazı kullanmak için kullanıcının önce Şirket Portalı’nda oturum açarak kimliğini doğrulaması gerekir.
    Bu özellik yalnızca iOS 11.3.1 ve üzerinde desteklenir.

8. **Cihaz Yönetim Ayarları**’nı seçin ve bu profili kullanan cihazların denetlenmesini isteyip istemediğinizi seçin.

    ![Cihaz Yönetimi Ayarları ekran görüntüsü.](./media/device-enrollment-program-enroll-ios/devicemanagementsettingsblade.png)

    **Denetimli** cihazlar, varsayılan olarak size daha fazla yönetim seçeneği verir ve Etkinleştirme Kilidi’ni devre dışı bırakır. Microsoft, özellikle fazla sayıda iOS cihaz dağıtan kuruluşlar için denetimli modu etkinleştirme mekanizması olarak DEP’in kullanılmasını önerir.

    Kullanıcılara cihazlarının denetimli olduğu iki yolla bildirilir:

   - Kilit ekranında sonucu: "Bu iPhone, Contoso tarafından yönetilmektedir."
   - **Ayarları** > **genel** > **hakkında** kısmında: "Bu iPhone denetimlidir. ifadesi ve

     > [!NOTE]
     > Denetim olmadan kaydedilen bir cihaz, yalnızca Apple Configurator kullanılarak sıfırlanıp denetimli yapılabilir. Cihazı bu şekilde sıfırlamak için bir iOS cihazı USB kablosu ile bir Mac’e bağlamak gerekir. Bu konu hakkında daha fazla bilgi için [Apple Configurator belgelerine](http://help.apple.com/configurator/mac/2.3) bakın.

9. Bu profili kullanan cihazlarda kilitli kayıt isteyip istemediğinizi seçin. **Kilitli kayıt**, yönetim profilinin **Ayarlar** menüsünden kaldırılmasını sağlayan iOS ayarlarını devre dışı bırakır. Cihazı kaydettikten sonra cihazı silmeden bu ayarı değiştiremezsiniz. Bu cihazlarda **Denetimli** Yönetim Modu *Evet* olarak ayarlı olmalıdır. 

10. Bu profili kullanan cihazların **Bilgisayarlarla eşitleme** imkanının olup olmayacağını seçin. **Sertifikaya göre Apple Configurator’a izin ver**’i seçerseniz, **Apple Configurator Sertifikaları**’nın altında bir sertifika seçmeniz gerekir.

11. Önceki adımda **Sertifikaya göre Apple Configurator’a izin ver**’i seçtiyseniz içeri aktaracak bir Apple Configurator Sertifikası seçin.

12. **Tamam**’ı seçin.

13. Seçin **Kurulum Yardımcısı özelleştirme** aşağıdaki profil ayarlarını yapılandırmak için: ![Kurulum Yardımcısını özelleştirme.](./media/device-enrollment-program-enroll-ios/setupassistantcustom.png)


    | Departman ayarları | Açıklama |
    |---|---|
    | <strong>Departman Adı</strong> | Kullanıcı, etkinleştirme sırasında <strong>Yapılandırma Hakkında</strong> öğesine dokunduğunda görüntülenir. |
    |    <strong>Departman Telefonu</strong>     | Kullanıcı, etkinleştirme sırasında <strong>Yardım Gerekli</strong> düğmesine dokunduğunda görüntülenir. |

  Kullanıcı kurulum yaparken cihazda çeşitli Kurulum Yardımcısı ekranlarının gösterilmesini veya gizlenmesini seçebilirsiniz.
  - **Gizle**'yi seçerseniz, kurulum sırasında ekran görüntülenmez. Cihaz kurulumu yapıldıktan sonra, kullanıcı yine **Ayarlar** menüsüne gidip özelliği ayarlayabilir.
  - **Göster**'i seçerseniz, kurulum sırasında ekran görüntülenir. Kullanıcı bazen hiçbir eylem yapmadan ekranı atlayabilir. Ama daha sonra cihazın **Ayarlar** menüsüne gidebilir ve özelliği ayarlayabilir. 


    | Kurulum Yardımcısı ekran ayarları | **Göster**'i seçerseniz, kurulum sırasında cihaz... |
    |------------------------------------------|------------------------------------------|
    | <strong>Geçiş kodu</strong> | Kullanıcıdan geçiş kodu ister. Cihazın güvenliği sağlanmayacaksa veya erişim denetimi başka bir yolla (cihazı tek uygulamayla sınırlandıran bilgi noktası modu) uygulanmayacaksa her zaman geçiş kodu gerektirir. |
    | <strong>Konum Hizmetleri</strong> | Kullanıcıdan konum ister. |
    | <strong>Geri yükleme</strong> | **Uygulamalar ve Veriler** ekranını görüntüler. Bu ekran kullanıcıya cihazı kurarken iCloud Backup'tan verileri geri yükleme veya aktarma seçeneği sağlar. |
    | <strong>iCloud ve Apple Kimliği</strong> | Kullanıcıya **Apple Kimliği** ile oturum açma ve **iCloud**'u kullanma seçenekleri sağlar.                         |
    | <strong>Hüküm ve Koşullar</strong> | Kullanıcının Apple'ın hüküm ve koşullarını kabul etmesini gerektirir. |
    | <strong>Touch ID</strong> | Kullanıcıya cihaz için parmak izi tanımlama özelliğini ayarlama seçeneği sağlar. |
    | <strong>Apple Pay</strong> | Kullanıcıya cihazda Apple Pay ayarlama seçeneği sağlar. |
    | <strong>Yakınlaştırma</strong> | Kullanıcıya cihazı ayarlarken ekranı yakınlaştırma seçeneği sağlar. |
    | <strong>Siri</strong> | Kullanıcıya Siri'yi ayarlama seçeneği sağlar. |
    | <strong>Tanılama Verileri</strong> | Kullanıcıya **Tanılama** ekranını görüntüler. Bu ekran kullanıcıya Apple'a tanılama verileri gönderme seçeneği sağlar. |


14. Seçin **Tamam**.

15. Profili kaydetmek için **Oluştur**’u seçin.

## <a name="sync-managed-devices"></a>Yönetilen cihazları eşitleme
Artık Intune’a cihazlarınızı yönetme izni verildiğine göre, yönetilen cihazlarınızı Intune’da Azure portalında görmek için Intune’u Apple ile eşitleyebilirsiniz.

1. Azure portalında Intune’da, **Cihaz kaydı** > **Apple Kaydı** > **Kayıt programı belirteçleri** > listeden bir belirteç seçin > **Cihazlar** > **Eşitle**’yi seçin. ![Kayıt Programı Cihazları düğümünün seçili olduğu ve Eşitle bağlantısının seçildiği ekran görüntüsü.](./media/device-enrollment-program-enroll-ios/image06.png)

   Intune, Apple’ın kabul edilebilir kayıt programı trafiği şartlarına uymak için aşağıdaki kısıtlamaları getirir:
   - Tam eşitleme en sık yedi günde bir çalıştırılabilir. Tam eşitleme sırasında Intune, Intune’a bağlı Apple MDM sunucusuna atanan seri numaraların tam güncelleştirilmiş bir listesini alır. Bir Kayıt Programı cihazı, cihaz ataması DEP portalında Apple MDM sunucusundan kaldırılmadan Intune portalından silinirse, tam eşitleme çalıştırılana kadar Intune’a tekrar içeri aktarılmaz.   
   - Eşitleme 24 saatte bir otomatik olarak çalıştırılır. **Eşitle** düğmesine basarak da eşitleyebilirsiniz (en fazla 15 dakikada bir kez). Tüm eşitleme isteklerinin tamamlanması için 15 dakika verilir. Eşitleme tamamlanana kadar **Eşitle** düğmesi devre dışı kalır. Bu eşitleme, mevcut aygıt durumunu yeniler ve Apple MDM sunucusuna atanan yeni cihazları içeri aktarır.   


## <a name="assign-an-enrollment-profile-to-devices"></a>Cihazlara kayıt profili atama
Cihazların kaydedilmesi için bunlara bir kayıt programı profili atamalısınız.

>[!NOTE]
>Ayrıca, **Apple Seri Numaraları** dikey penceresinde profillere seri numaralar da atayabilirsiniz.

1. Azure portalında Intune’da, **Cihaz kaydı** > **Apple Kaydı** > **Kayıt programı belirteçleri** > listeden bir belirteç seçin.
2. **Cihazlar** > listeden cihazları seçin > **Profil ata**’yı seçin.
3. **Profil ata**'nın altında cihazlar için bir profil seçin > **Ata**’ya tıklayın.

### <a name="assign-a-default-profile"></a>Varsayılan bir profil atama

Belirli bir belirteç ile kaydedilen tüm cihazlara uygulanacak varsayılan bir profil seçebilirsiniz.

1. Azure portalında Intune’da, **Cihaz kaydı** > **Apple Kaydı** > **Kayıt programı belirteçleri** > listeden bir belirteç seçin.
2. **Varsayılan Profil Ayarla**’yı seçin, açılan listeden bir profil seçin ve daha sonra **Kaydet**’e tıklayın. Profil, bu belirteçle kaydedilen tüm cihazlara uygulanacaktır.

## <a name="distribute-devices"></a>Cihazları dağıtma
Apple ve Intune arasında eşitlemeyi ve yönetimi etkinleştirdiniz ve DEP cihazlarınızın kaydolmasına izin vermek için bir profil atadınız. Artık cihazları kullanıcılara dağıtabilirsiniz. Kullanıcı benzeşimli cihazlar, her kullanıcıya bir Intune lisansı atanmasını gerektirir. Kullanıcı benzeşimi olmayan cihazlar, cihaz lisansı gerektirir. Etkinleştirilmiş bir cihaz, silinene kadar bir kayıt profili uygulayamaz.

Bkz. [iOS cihazınızı Aygıt Kayıt Programı ile Intune’a kaydetme](/intune-user-help/enroll-your-device-dep-ios).

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
