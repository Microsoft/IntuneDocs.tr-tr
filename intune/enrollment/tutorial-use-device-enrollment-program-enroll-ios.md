---
title: Öğretici-Intune 'a iOS cihazlarını kaydetmek için Apple Business Manager veya Aygıt Kayıt Programı kullanma
titleSuffix: Microsoft Intune
description: Bu öğreticide, Intune 'da iOS cihazlarını kaydetmek için Apple 'ın kurumsal cihaz kayıt özelliklerini ABG 'den ayarlayacaksınız.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/30/2019
ms.topic: tutorial
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
Customer intent: As an Intune admin, I want to set up the Apple's corporate device enrollment features so that corporate devices can automatically enroll in Intune.
ms.collection: M365-identity-device-management
ms.openlocfilehash: 83a9467065bb5c1d1cde2035df936541bb804ddc
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72503088"
---
# <a name="tutorial-use-apples-corporate-device-enrollment-features-in-apple-business-manager-abm-to-enroll-ios-devices-in-intune"></a>Öğretici: Intune 'A iOS cihazlarını kaydetmek için Apple Business Manager 'daki (ABG) Apple 'ın kurumsal cihaz kayıt özelliklerini kullanma
Apple Business Manager 'daki cihaz kayıt özellikleri cihazların kaydedilmesini basitleştirir. Intune, Apple 'ın eski Aygıt Kayıt Programı (DEP) portalını da destekler, ancak Apple Business Manager ile yeni bir başlangıç yapmanız önerilir. Microsoft Intune ve Apple Kurumsal cihaz kaydı ile, Kullanıcı cihazı ilk kez açtığında cihazlar otomatik olarak güvenli bir şekilde kaydedilir. Bu nedenle, her bir cihazı ayrı ayrı ayarlamanıza gerek kalmadan cihazları birçok kullanıcıya gönderebilirsiniz. 

Bu öğreticide şunların nasıl yapıldığını öğreneceksiniz:
> [!div class="checklist"]
> * Apple cihaz kayıt belirteci al
> * Yönetilen cihazları Intune 'a eşitleme
> * Kayıt profili oluşturma
> * Kayıt profilini cihazlara atama

Bir Intune aboneliğiniz yoksa [ücretsiz bir deneme hesabı için kaydolun](../fundamentals/free-trial-sign-up.md).

## <a name="prerequisites"></a>Önkoşullar
- [Apple Business Manager](https://business.apple.com) veya [Apple 'ın aygıt kayıt programı](http://deploy.apple.com) satın alınan cihazlar
- [Mobil cihaz yönetimi yetkilisini](../fundamentals/mdm-authority-set.md) ayarlama
- [Apple MDM anında iletme sertifikası](apple-mdm-push-certificate-get.md) alın

## <a name="get-an-apple-device-enrollment-token"></a>Apple cihaz kayıt belirteci al
İOS cihazlarını Apple 'ın kurumsal kayıt özellikleriyle kaydetmeden önce, bir Apple cihaz kayıt belirteci (. pek) dosyası gerekir. Bu belirteç, Intune 'un kuruluşunuzun sahip olduğu Apple cihazları hakkında bilgi eşitlemesini sağlar. Ayrıca Intune'un kayıt profilini Apple'a yüklemesine ve cihazları bu profillere atamasına izin verir.

Bir cihaz kayıt belirteci oluşturmak için Abe veya DEP portalını kullanın. Ayrıca portalları, yönetim için Intune 'a cihaz atamak üzere de kullanabilirsiniz.

1. [Azure portalında Intune'da](https://aka.ms/intuneportal), **Cihaz kaydı** > **Apple kaydı** > **Kayıt Programı Belirteçleri** > **Ekle**'yi seçin.

2. **Onaylıyorum**’u seçerek Microsoft’un Apple’a kullanıcı ve cihaz bilgilerini göndermesine izin verin.

   ![Apple Sertifikaları çalışma alanındaki Kayıt Programı Belirteci panelinde bulunan ortak anahtarı indirme öğesinin ekran görüntüsü.](./media/tutorial-use-device-enrollment-program-enroll-ios/add-enrollment-program-token-pane.png)

3. Şifreleme dosyasını (.pem) indirmek ve yerel olarak kaydetmek için **Ortak anahtarınızı indirin** öğesini seçin. . Ped dosyası, Abe veya DEP portalından güven ilişkisi sertifikası istemek için kullanılır.

4. Apple’ın Dağıtım Programı portalını açmak için **Apple’ın Aygıt Kayıt Programı için bir belirteç oluştur**’u seçin ve şirket Apple Kimliğinizle oturum açın. DEP belirtecinizi yenilemek için de bu Apple kimliğini kullanabilirsiniz.

5. Apple’ın [Dağıtım Programları portalında](https://deploy.apple.com), **Aygıt Kayıt Programı** için **Kullanmaya Başla**’yı seçin. İşleminiz [Apple Business Manager](https://business.apple.com)'daki aşağıdaki adımlardan biraz farklı olabilir.

4. **Sunucuları Yönet** sayfasında **MDM Sunucusu Ekle**’yi seçin.

5. **MDM sunucu adı**Için *Testmdmserver* girin ve ardından **İleri**' yi seçin. Sunucu adı, mobil cihaz yönetimi (MDM) sunucusunu tanımlarken kullanmanız içindir. Microsoft Intune sunucusunun adı veya URL'si değildir.

6. **Ekle &lt;ServerName&gt;** iletişim kutusu açılır ve **Ortak Anahtarınızı Yükleyin** ifadesi yazar. **Dosya Seç…** öğesini seçin. .pem dosyasını karşıya yükleyin ve ardından **İleri**'yi seçin.

6. **Dağıtım programları** > **aygıt kayıt programı** > **cihazları yönet**' e gidin.
7. **Cihazları seçin**' ın altında **seri numarası**' nı seçin. <!--ask Tiffany about this-->

8. **Eylem Seç** işlemi için **Sunucuya Ata**’yı ve Microsoft Intune için belirtilen &lt;ServerName&gt; öğesini belirleyip **Tamam**'ı seçin. Apple portalı, belirtilen cihazları Intune sunucusunda yönetilmek üzere bu sunucuya atar ve **Atama Tamamlandı** ifadesini görüntüler.

   Apple portalında **Dağıtım Programları** &gt; **Aygıt Kayıt Programı** &gt; **Atama Geçmişini Görüntüle**’ye giderek cihazların listesi ile MDM sunucu atamalarına göz atabilirsiniz.

9. Daha sonra başvurmak için, Azure portal Intune 'da, bu belirteci oluşturmak için kullanılan Apple KIMLIĞINI sağlayın.

    ![Kayıt programı belirtecini oluşturmak için kullanılan Apple kimliğini belirtme ve kayıt programı belirtecine gözatma işleminin ekran görüntüsü.](./media/tutorial-use-device-enrollment-program-enroll-ios/image03.png)

10. **Apple belirteci** kutusunda sertifika (.pem) dosyasına gözatın, **Aç**’ı ve daha sonra **Oluştur**’u seçin. 

11. Bu belirtece hangi yöneticilerin erişebileceğini sınırlamak için kapsam etiketleri uygulamak isterseniz kapsamlar ' ı seçin.

## <a name="create-an-apple-enrollment-profile"></a>Apple kayıt profili oluşturma
Belirtecinizi yüklemişseniz, şirkete ait iOS cihazları için bir kayıt profili oluşturabilirsiniz. Bir cihaz kayıt profili, kayıt sırasında bir grup cihaza uygulanan ayarları tanımlar.

1. Azure portalında Intune’da, **Cihaz kaydı** > **Apple kaydı** > **Kayıt programı belirteçleri**’ni seçin.

2. Yeni yüklediğiniz belirteci seçin, **profiller** > **Profil oluştur**' u seçin.

3. **Profil oluştur**altında, **Açıklama**Için iOS cihazları IÇIN **ad** ve *Test DEP* için *testdepprofile* yazın. Kullanıcılar bu ayrıntıları göremez.

4. **Platform**altında **iOS** ' ı seçin.

5. Cihazlarınızın **Kullanıcı benzeşimi**ile veya bu olmadan kaydolmasını istediğinizi belirleme. Kullanıcı benzeşimi, belirli kullanıcılar tarafından kullanılacak cihazlar için tasarlanmıştır. Kullanıcılarınız uygulama yükleme gibi hizmetler için Şirket Portalı kullanmak istiyorsanız, **Kullanıcı benzeşimi Ile kaydet**' i seçin. Kullanıcılarınız Şirket Portalı gerekmiyorsa veya cihazı birçok kullanıcı için sağlamak istiyorsanız, **Kullanıcı benzeşimi olmadan kaydet**' i seçin.

6. Kullanıcı benzeşimi ile kaydetmeyi seçerseniz Şirket Portalı veya Apple Kurulum Yardımcısı ile kimlik doğrulaması yapmak istediğinizi saptayın. Multi-Factor Authentication kullanmak isterseniz, kullanıcıların ilk oturum açtığında parolaları değiştirmesine izin verin veya kayıt sırasında kullanıcıların süre dolma parolalarını sıfırlamalarını iste, **Apple kurulumu yerine Şirket portalı kimlik doğrulaması altında Evet ' i seçin. Yardımcısı**. Apple Kurulum Yardımcısı aracılığıyla Apple 'ın sunduğu temel HTTP kimlik doğrulamasını rahat bir şekilde kullanıyorsanız **Hayır**' ı seçin.

7. Kullanıcı benzeşimi ile kaydolmasını ve Şirket Portalı kimlik doğrulaması yapmayı seçerseniz, Apple 'ın toplu satın alma programı (VPP) ile Şirket Portalı yüklemek istediğinizi saptayın. Şirket Portalı bir VPP belirteci ile yüklerseniz, kullanıcının kayıt sırasında uygulama mağazasından Şirket Portalı indirmek için bir Apple KIMLIĞI ve parola girmesi gerekmez. Kullanılabilir Şirket Portalı ücretsiz lisanslarına sahip bir VPP belirteci seçmek için **belirteci kullan:** **vpp ile Install Şirket portalı** ' ı seçin. Şirket Portalı dağıtmak için VPP 'yi kullanmak istemiyorsanız, VPP **ile şirket portalı Install**altında **VPP kullanma** ' yı seçin. 

8. Kullanıcı benzeşimi ile kaydolmayı, Şirket Portalı kimlik doğrulamasını ve VPP ile Şirket Portalı yüklemeyi seçerseniz, Şirket Portalı tek uygulama modunda çalıştırmak istediğinize karar verin. Bu ayar, kullanıcının şirket kaydını tamamlayana kadar diğer uygulamalara erişememesini sağlar. Kayıt tamamlanana kadar kullanıcıyı bu akışa kısıtlamak isterseniz, **kimlik doğrulamasından çıkana kadar tek uygulama modunda Şirket portalı Çalıştır**altında **Evet** ' i seçin. 

9. **Cihaz yönetimi ayarları** ' nı seçin ve **denetimli**altında **Evet** ' i seçin. Denetimli cihazlar, kurumsal iOS cihazlarınız için en fazla yönetim seçeneği sunar.

10. Kullanıcılarınızın kurumsal cihazın yönetimini kaldıramadığından emin olmak için **kilitli kayıt** altında **Evet** ' i seçin. 

11. İOS cihazlarının bilgisayarlarla eşitleneceğini belirlemek için **bilgisayarlarla Eşitle** altında bir seçenek belirleyin.

12. Varsayılan olarak, Apple cihazı cihaz türü (ör. iPad) ile adlandırır. Farklı bir ad şablonu sağlamak istiyorsanız, **Cihaz adı şablonu Uygula**altında **Evet** ' i seçin. Cihazlara uygulamak istediğiniz adı girin; burada, *{{SERIAL}}* ve *{{DeviceType}}* dizelerinin her bir cihazın seri numarasını ve cihaz türünü yerine geçecek şekilde değiştirin. Aksi takdirde, **Cihaz adı şablonu Uygula**altında **Hayır** ' ı seçin.

13. **Tamam**’ı seçin.

14. **Kurulum Yardımcısı özelleştirmesi** ' nı seçin ve **bölüm adı**için *öğretici departmanı* girin. Bu dize, kullanıcıların cihaz etkinleştirme sırasında **yapılandırma hakkında** dokunduklarında gördükleri şeydir.

15. **Departman telefonu**altına bir telefon numarası girin. Bu sayı, kullanıcılar etkinleştirme sırasında **Yardım gerekli** düğmesine dokunduğunda görüntülenir.

16. Cihaz etkinleştirme sırasında çeşitli ekranları **gösterebilir** veya **gizleyebilirsiniz** . En sorunsuz kayıt deneyimi için tüm ekranları **Gizle**olarak ayarlayın.

17. **Tamam** > **Oluştur**'u seçin.

## <a name="sync-managed-devices-to-intune"></a>Yönetilen cihazları Intune 'a eşitleme

Abe, ASM veya DEP portalı ile bir kayıt programı belirteci ayarladıktan ve MDM sunucusuna cihaz atadıktan sonra, bu cihazların Intune hizmetine eşitlenmesini bekleyebilir veya el ile bir eşitleme gönderebilirsiniz. El ile eşitleme olmadan cihazların Azure portal görünmesi 24 saate kadar sürebilir.

1. Azure portal Intune 'da, **cihaz kaydı** > **Apple kayıt** > **kayıt programı belirteçleri** ' ni seçin > > **cihazlarda**bir belirteç seçin  > **eşitleme**.

## <a name="assign-an-enrollment-profile-to-ios-devices"></a>İOS cihazlarına kayıt profili atama

Cihazların kaydedilmesi için bunlara bir kayıt programı profili atamalısınız. Bu cihazlar Apple 'dan Intune 'a eşitlenir ve Abe, ASM veya DEP portalındaki doğru MDM sunucu belirtecine atanmalıdır.

1. Azure portal Intune 'da, **cihaz kaydı** > **Apple kayıt** > **kayıt programı belirteçleri** ' ni seçin > belirtecinizi seçin.
2. **Cihazlar** > listeden cihazları seçin > **Profil ata**’yı seçin.
3. **Profil ata**'nın altında cihazlar için bir profil seçin > **Ata**’ya tıklayın.

## <a name="distribute-devices-to-users"></a>Cihazları kullanıcılara dağıtma

Apple ve Intune arasında yönetim ve eşitleme yaptınız ve DEP cihazlarınızın kaydolmasına izin vermek için bir profil atadınız. Artık cihazları kullanıcılara dağıtabilirsiniz. Kullanıcı benzeşimli cihazlar, her kullanıcıya bir Intune lisansı atanmasını gerektirir.

## <a name="next-steps"></a>Sonraki adımlar

İOS cihazlarını kaydetmek için kullanılabilecek diğer seçeneklerle ilgili daha fazla bilgi bulabilirsiniz.

> [!div class="nextstepaction"]
> [Derinlemesine iOS DEP kayıt makalesi](device-enrollment-program-enroll-ios.md)

<!--commenting out because inaccurate>
## Clean up resources
<!--If you don't want to use iOS corporate enrolled devices anymore, you can delete them.>
<!--- If the devices are enrolled in Intune, you must first [delete them from the Azure Active Directory portal](../remote-actions/devices-wipe.md#delete-devices-from-the-azure-active-directory-portal).>
