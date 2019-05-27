---
title: Öğretici - Apple İş Yöneticisi'ni kullanın veya cihaz kayıt programı iOS cihazlarını ıntune'a kaydetmek için
titleSuffix: Microsoft Intune
description: Bu öğreticide, ıntune'da iOS cihazlarını kaydetmek için Apple'nın Kurumsal cihaz kaydı özellikleri ABM ayarlarsınız.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/30/2019
ms.topic: tutorial
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
Customer intent: As an Intune admin, I want to set up the Apple's corporate device enrollment features so that corporate devices can automatically enroll in Intune.
ms.collection: M365-identity-device-management
ms.openlocfilehash: faceee883194dbbdcec83f282806035ffc0432d1
ms.sourcegitcommit: 0f771585d3556c0af14500428d5c4c13c89b9b05
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66174171"
---
# <a name="tutorial-use-apples-corporate-device-enrollment-features-in-apple-business-manager-abm-to-enroll-ios-devices-in-intune"></a>Öğretici: Apple'nın Kurumsal cihaz kaydı özellikleri, ıntune'da iOS cihazlarını kaydetmek için Apple İş Yöneticisi'ni (ABM) kullanın.
Cihaz kaydı özellikleri Apple İş Yöneticisi'nde hesabından cihazların kaydını basitleştirir. Intune, Apple'nın eski cihaz kayıt programı (DEP) portalında da destekler, ancak yeni Apple İşletme Yöneticisi ile başlangıç yapmanız önerilir. Microsoft Intune ve Apple Kurumsal cihaz kaydı ile cihazlar, kullanıcı cihazda ilk açtığı anda güvenli bir şekilde otomatik olarak kaydedilir. Bu nedenle, her cihazı ayrı ayrı ayarlama yapmak zorunda kalmadan çok sayıda kullanıcı cihazlara gönderebilirsiniz. 

Bu öğreticide şunların nasıl yapıldığını öğreneceksiniz:
> [!div class="checklist"]
> * Bir Apple cihaz kaydı belirteci alma
> * Intune yönetilen cihazları eşitleme
> * Kayıt profili oluşturma
> * Cihazlara kayıt profili atama

Bir Intune aboneliğiniz yoksa [ücretsiz bir deneme hesabı için kaydolun](free-trial-sign-up.md).

## <a name="prerequisites"></a>Önkoşullar
- Satın alınan cihazlar [Apple İşletme Yöneticisi](https://business.apple.com) veya [Apple aygıt kayıt programı](http://deploy.apple.com)
- Ayarlama [mobil cihaz Yönetimi yetkilisi](mdm-authority-set.md)
- Alma bir [Apple MDM anında iletme sertifikası](apple-mdm-push-certificate-get.md)

## <a name="get-an-apple-device-enrollment-token"></a>Bir Apple cihaz kaydı belirteci alma
Apple'nın Kurumsal kayıt özellikleri ile iOS cihazlarını kaydetmeden önce bir Apple cihaz kaydı belirteci (.pem) dosyasına ihtiyacınız vardır. Bu belirteç Intune'un şirketinize ait olan Apple cihazları hakkındaki bilgileri eşitlemesini sağlar. Ayrıca Intune'un kayıt profilini Apple'a yüklemesine ve cihazları bu profillere atamasına izin verir.

Cihaz kaydı belirtecini oluşturmak için ABM veya DEP portalını kullanın. Ayrıca cihazları Yönetim için Intune'a atamak için portalı kullanın.

1. [Azure portalında Intune'da](https://aka.ms/intuneportal), **Cihaz kaydı** > **Apple kaydı** > **Kayıt Programı Belirteçleri** > **Ekle**'yi seçin.

2. **Onaylıyorum**’u seçerek Microsoft’un Apple’a kullanıcı ve cihaz bilgilerini göndermesine izin verin.

   ![Apple Sertifikaları çalışma alanındaki Kayıt Programı Belirteci panelinde bulunan ortak anahtarı indirme öğesinin ekran görüntüsü.](./media/device-enrollment-program-enroll-ios-newui/add-enrollment-program-token-pane.png)

3. Şifreleme dosyasını (.pem) indirmek ve yerel olarak kaydetmek için **Ortak anahtarınızı indirin** öğesini seçin. .Pem dosyasını ABM veya DEP portalından bir güven ilişkisi sertifikası istemek için kullanılır.

4. Apple’ın Dağıtım Programı portalını açmak için **Apple’ın Aygıt Kayıt Programı için bir belirteç oluştur**’u seçin ve şirket Apple Kimliğinizle oturum açın. DEP belirtecinizi yenilemek için de bu Apple kimliğini kullanabilirsiniz.

5.  Apple’ın [Dağıtım Programları portalında](https://deploy.apple.com), **Aygıt Kayıt Programı** için **Kullanmaya Başla**’yı seçin. İşleminizi yer alan aşağıdaki adımları biraz farklı olabilir [Apple İşletme Yöneticisi](https://business.apple.com).

4. **Sunucuları Yönet** sayfasında **MDM Sunucusu Ekle**’yi seçin.

5. İçin **MDM sunucu adı**, girin *TestMDMServer* seçip **sonraki**. Sunucu adı, mobil cihaz yönetimi (MDM) sunucusunu tanımlarken kullanmanız içindir. Microsoft Intune sunucusunun adı veya URL'si değildir.

6. **Ekle &lt;ServerName&gt;** iletişim kutusu açılır ve **Ortak Anahtarınızı Yükleyin** ifadesi yazar. **Dosya Seç…** öğesini seçin. .pem dosyasını karşıya yükleyin ve ardından **İleri**'yi seçin.

6. Git **dağıtım programları** > **cihaz kayıt programı** > **cihazları yönetme**.
7. Altında **cihaz seçme ölçütü**, seçin **seri numarası**. <!--ask Tiffany about this-->

8. **Eylem Seç** işlemi için **Sunucuya Ata**’yı ve Microsoft Intune için belirtilen &lt;ServerName&gt; öğesini belirleyip **Tamam**'ı seçin. Apple portalı, belirtilen cihazları Intune sunucusunda yönetilmek üzere bu sunucuya atar ve **Atama Tamamlandı** ifadesini görüntüler.

   Apple portalında **Dağıtım Programları** &gt; **Aygıt Kayıt Programı** &gt; **Atama Geçmişini Görüntüle**’ye giderek cihazların listesi ile MDM sunucu atamalarına göz atabilirsiniz.

9. Azure portalında ıntune'da ileride başvurmak için bu belirteci oluşturmak için kullanılan Apple Kimliğini sağlayın.

    ![Kayıt programı belirtecini oluşturmak için kullanılan Apple kimliğini belirtme ve kayıt programı belirtecine gözatma işleminin ekran görüntüsü.](./media/device-enrollment-program-enroll-ios/image03.png)

10. **Apple belirteci** kutusunda sertifika (.pem) dosyasına gözatın, **Aç**’ı ve daha sonra **Oluştur**’u seçin. 

11. Bu belirteci hangi yöneticileri erişimi sınırı kapsam etiketleri uygulamak istiyorsanız, kapsamları seçin.

## <a name="create-an-apple-enrollment-profile"></a>Apple kayıt profili oluşturma
Belirtecinizi yüklediğinize göre şirkete ait iOS cihazları için bir kayıt profili oluşturabilirsiniz. Bir cihaz kayıt profili, kayıt sırasında bir grup cihaza uygulanan ayarları tanımlar.

1. Azure portalında Intune’da, **Cihaz kaydı** > **Apple kaydı** > **Kayıt programı belirteçleri**’ni seçin.

2. Yalnızca yüklü bir belirteç seçin, **profilleri** > **profili oluşturma**.

3. Altında **profili oluştur**, girin *TestDEPProfile* için **adı** ve *iOS cihazları için test DEP* için **açıklaması** . Kullanıcılar bu ayrıntıları göremez.

4. Seçin **iOS** altında **Platform**.

5. İle veya olmadan kaydetmek için cihazlarınıza isteyip istemediğinizi belirlemek **kullanıcı benzeşimi**. Kullanıcı benzeşimi, belirli kullanıcılar tarafından kullanılacak olan cihazlar için tasarlanmıştır. Kullanıcılarınızın istersiniz, uygulamaları yükleme gibi hizmetler için Şirket portalı kullanmak **kullanıcı benzeşimi ile Kaydet**. İstediğiniz sayıda kullanıcı cihazı sağlama, seçin ya da kullanıcılarınızın Şirket portalı gerekmez **kullanıcı benzeşimi olmadan**.

6. Kullanıcı benzeşimi ile kaydetme seçerseniz, Şirket portalı veya Apple Kurulum Yardımcısı ile kimlik doğrulama bırakmak isteyip istemediğinizi belirleyin. Çok faktörlü kimlik doğrulamasını kullanmak istiyorsanız, ilk oturum açma sırasında parolalarını değiştirmelerine olanak tanıyan veya seçin, kayıt sırasında süresi dolmuş parolalarını sıfırlamak için kullanıcılara sor **Evet** altında **ile kimlik doğrulaması Şirket portalı yerine Apple Kurulum Yardımcısı'nı**. Öğesini, kullanabiliyorsanız, Apple kullanarak temel HTTP kimlik doğrulaması Apple Kurulum Yardımcısı aracılığıyla sağlanan **Hayır**.

7. Kullanıcı benzeşimi'ni ve Şirket portalı ile kimlik doğrulama ile kaydetmeyi seçerseniz, Apple Volume Purchase Program (VPP) ile şirket Portalı'nı yüklemek isteyip istemediğinizi belirleyin. Şirket portalı ile bir VPP belirteci yüklerseniz, kullanıcı bir Apple kimliği ve parola uygulama Mağazası'ndan Şirket portalı kayıt sırasında yüklenecek girmesi gerekmez. Seçin **belirteci kullan:** altında **VPP ile şirket portalını Yükle** şirket Portalı'nın ücretsiz lisansa sahip bir VPP belirtecini seçin. Şirket portalı'nı dağıtma, seçmek için VPP kullanmayı istemiyorsanız **VPP kullanmayın** altında **VPP ile şirket portalını Yükle**. 

8. Şirket portalı ile kimlik doğrulama ve şirket portalıyla yükleme VPP, kullanıcı benzeşimi ile kaydetme seçerseniz Şirket portalı, kimlik doğrulaması kadar tek uygulama modunda çalıştırmak istediğinize karar verin. Bu ayar Kurumsal kayıt işlemini tamamlayana kadar kullanıcının diğer uygulamalara erişimi olmayacaktır olmanızı sağlar. Kullanıcı Bu akış kadar kısıtlamak istiyorsanız, kayıt tamamlandıktan öğesini **Evet** altında **çalıştırma şirket Portalı'nda kimlik doğrulama kadar tek uygulama moduna**. 

9. Seçin **cihaz yönetim ayarları** ve **Evet** altında **denetimli**. Denetlenen cihazlar, şirket iOS cihazlarınız için birçok yönetim seçenekleri sağlar.

10. Seçin **Evet** altında **kilitli kayıt** kullanıcılarınızın Kurumsal cihaz yönetimini kaldıramıyor emin olmak için. 

11. Altında bir seçenek belirleyin **bilgisayarlarla eşitleme** iOS cihazları bilgisayarlarla eşitleme olup olmayacağını belirlemek için.

12. Varsayılan olarak, Apple cihaz türü (örneğin, iPad) ile cihaz adları. Farklı bir ad şablon sağlamak istiyorsanız, seçin **Evet** altında **cihaz adı Şablonu Uygula**. Cihazlara uygulamak istediğiniz adı girin. burada dizeler *{{seri}}* ve *{{DEVICETYPE}}* her cihazın seri numarasını ve cihaz türünü kullanacak. Aksi takdirde seçin **Hayır** altında **cihaz adı Şablonu Uygula**.

13. **Tamam**’ı seçin.

14. Seçin **Kurulum Yardımcısı özelleştirme** girin *Öğretici bölüm* için **bölüm adı**. Kullanıcıların gördükleri bunlar dokunduğunuzda bu dizedir **yapılandırması hakkında** cihaz etkinleştirme sırasında.

15. Altında **departman telefonu**, bir telefon numarası girin. Bu sayı kullanıcılar seçeneğine dokunduğunda görüntülenir **yardıma ihtiyacınız** etkinleştirme sırasında düğmesi.

16. Yapabilecekleriniz **Göster** veya **Gizle** ekranlar cihaz etkinleştirme sırasında çeşitli. Tüm ekranlar en sorunsuz kayıt deneyimi için ayarlanmış **Gizle**.

17. **Tamam** > **Oluştur**'u seçin.

## <a name="sync-managed-devices-to-intune"></a>Intune yönetilen cihazları eşitleme

ABM, ASM ve DEP portal ile kayıt programı belirteci ayarlama ve cihazları var.'ı MDM Sunucusu'na atadıktan sonra bu cihazlar Intune hizmetine eşitleme için bekleyin ya da el ile eşitleme gönderin. El ile eşitleme, cihazları Azure Portalı'nda görünmesi 24 saat sürebilir.

1. Azure portalında ıntune'da, **cihaz kaydı** > **Apple kaydı** > **kayıt programı belirteçleri** > içinde bir belirteç seçin Listenin > **cihazları** > **eşitleme**.

## <a name="assign-an-enrollment-profile-to-ios-devices"></a>İOS cihazlara bir kayıt profili atama

Cihazların kaydedilmesi için bunlara bir kayıt programı profili atamalısınız. Bu cihazlar için Intune, Apple'dan eşitlenen ve ABM, ASM ve DEP portalında uygun MDM sunucusu belirtecini atanması gerekir.

1. Azure portalında ıntune'da, **cihaz kaydı** > **Apple kaydı** > **kayıt programı belirteçleri** > belirtecinizi seçin listede.
2. **Cihazlar** > listeden cihazları seçin > **Profil ata**’yı seçin.
3. **Profil ata**'nın altında cihazlar için bir profil seçin > **Ata**’ya tıklayın.

## <a name="distribute-devices-to-users"></a>Cihazları kullanıcılara dağıtma

Ayarladığınız yönetim ve Apple ve Intune arasında eşitlemeyi ve DEP cihazlarınızın izin vermek için bir profil atadınız. Artık cihazları kullanıcılara dağıtabilirsiniz. Kullanıcı benzeşimli cihazlar, her kullanıcıya bir Intune lisansı atanmasını gerektirir.

## <a name="next-steps"></a>Sonraki adımlar

İOS cihazlarını kaydetmek için kullanılabilen diğer seçenekler hakkında daha fazla bilgi bulabilirsiniz.

> [!div class="nextstepaction"]
> [Ayrıntılı iOS DEP kaydı makale](device-enrollment-program-enroll-ios.md)

<!--commenting out because inaccurate>
## Clean up resources
<!--If you don't want to use iOS corporate enrolled devices anymore, you can delete them.>
<!--- If the devices are enrolled in Intune, you must first [delete them from the Azure Active Directory portal](devices-wipe.md#delete-devices-from-the-azure-active-directory-portal).>
