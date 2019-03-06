---
title: Öğretici - cihaz kayıt programı iOS cihazlarını ıntune'a kaydetmek için kullanma
titleSuffix: Microsoft Intune
description: Bu öğreticide, Apple belirleyeceğim DEP ıntune'da iOS cihazlarını kaydetmek için.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 1/30/2019
ms.topic: tutorial
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
Customer intent: As an Intune admin, I want to set up the Device Enrollment Program so that users can automatically enroll in Intune.
ms.collection: M365-identity-device-management
ms.openlocfilehash: 88fe825b75e7717740e5a5ca4af4c52e9bb21768
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57400407"
---
# <a name="tutorial-use-the-device-enrollment-program-to-enroll-ios-devices-in-intune"></a>Öğretici: Cihaz kayıt programı iOS cihazlarını ıntune'a kaydetmek için kullanın
Apple cihaz kayıt programı (DEP) hesabından cihazların kaydını basitleştirir. Microsoft Intune ve DEP ile cihazlar, kullanıcı cihazda ilk açtığı anda otomatik olarak kaydedilir. Bu nedenle, her cihazı ayrı ayrı ayarlama yapmak zorunda kalmadan çok sayıda kullanıcı cihazlara gönderebilirsiniz. 

Bu öğreticide şunların nasıl yapıldığını öğreneceksiniz:
> [!div class="checklist"]
> * Bir Apple DEP belirteci alma
> * Bir Autopilot cihaz grubu oluşturma
> * Bir Autopilot dağıtım profili oluşturma
> * Autopilot dağıtım profilini cihaz grubuna atama
> * Kullanıcılara Windows cihazlar dağıtma

Bir Intune aboneliğiniz yoksa [ücretsiz bir deneme hesabı için kaydolun](free-trial-sign-up.md).

## <a name="prerequisites"></a>Önkoşullar
- [Apple Aygıt Kayıt Programı](http://deploy.apple.com)’nda satın alınmış cihazlar
- Ayarlama [mobil cihaz Yönetimi yetkilisi](mdm-authority-set.md)
- Alma bir [Apple MDM anında iletme sertifikası](apple-mdm-push-certificate-get.md)

## <a name="get-an-apple-dep-token"></a>Bir Apple DEP belirteci alma
İOS cihazlarını DEP ile kaydetmeden önce bir Apple DEP belirteci (.pem) dosyası gerekir. Bu belirteç, Intune'un şirketinize ait olan DEP cihazları hakkındaki bilgileri eşitlemesini sağlar. Ayrıca Intune'un kayıt profilini Apple'a yüklemesine ve cihazları bu profillere atamasına izin verir.

DEP belirtecini oluşturmak için Apple DEP portalını kullanın. Cihazları yönetim için Intune’a atamak için DEP portalını da kullanabilirsiniz.

1. [Azure portalında Intune'da](https://aka.ms/intuneportal), **Cihaz kaydı** > **Apple kaydı** > **Kayıt Programı Belirteçleri** > **Ekle**'yi seçin.

2. **Onaylıyorum**’u seçerek Microsoft’un Apple’a kullanıcı ve cihaz bilgilerini göndermesine izin verin.

   ![Apple Sertifikaları çalışma alanındaki Kayıt Programı Belirteci panelinde bulunan ortak anahtarı indirme öğesinin ekran görüntüsü.](./media/device-enrollment-program-enroll-ios-newui/add-enrollment-program-token-pane.png)

3. Şifreleme dosyasını (.pem) indirmek ve yerel olarak kaydetmek için **Ortak anahtarınızı indirin** öğesini seçin. .pem dosyası Apple Cihaz Kayıt Programı portalından güven ilişkisi sertifikası istemek için kullanılır.

4. Apple’ın Dağıtım Programı portalını açmak için **Apple’ın Aygıt Kayıt Programı için bir belirteç oluştur**’u seçin ve şirket Apple Kimliğinizle oturum açın. DEP belirtecinizi yenilemek için de bu Apple kimliğini kullanabilirsiniz.

5.  Apple’ın [Dağıtım Programları portalında](https://deploy.apple.com), **Aygıt Kayıt Programı** için **Kullanmaya Başla**’yı seçin.

4. **Sunucuları Yönet** sayfasında **MDM Sunucusu Ekle**’yi seçin.

5. İçin **MDM sunucu adı**, girin *TestMDMServer* seçip **sonraki**. Sunucu adı, mobil cihaz yönetimi (MDM) sunucusunu tanımlarken kullanmanız içindir. Adı veya URL'si Microsoft Intune sunucusunun öyle.

6. **Ekle &lt;ServerName&gt;** iletişim kutusu açılır ve **Ortak Anahtarınızı Yükleyin** ifadesi yazar. **Dosya Seç…** öğesini seçin .pem dosyasını karşıya yükleyin ve ardından **İleri**'yi seçin.

6. Git **dağıtım programları** > **cihaz kayıt programı** > **cihazları yönetme**.
7. Altında **cihaz seçme ölçütü**, seçin **seri numarası**. <!--ask Tiffany about this-->

8. **Eylem Seç** işlemi için **Sunucuya Ata**’yı ve Microsoft Intune için belirtilen &lt;ServerName&gt; öğesini belirleyip **Tamam**'ı seçin. Apple portalı, belirtilen cihazları Intune sunucusunda yönetilmek üzere bu sunucuya atar ve **Atama Tamamlandı** ifadesini görüntüler.

   Apple portalında **Dağıtım Programları** &gt; **Aygıt Kayıt Programı** &gt; **Atama Geçmişini Görüntüle**’ye giderek cihazların listesi ile MDM sunucu atamalarına göz atabilirsiniz.

9. Azure portalında ıntune'da ileride başvurmak için bu belirteci oluşturmak için kullanılan Apple Kimliğini sağlayın.

    ![Kayıt programı belirtecini oluşturmak için kullanılan Apple kimliğini belirtme ve kayıt programı belirtecine gözatma işleminin ekran görüntüsü.](./media/device-enrollment-program-enroll-ios/image03.png)

10. **Apple belirteci** kutusunda sertifika (.pem) dosyasına gözatın, **Aç**’ı ve daha sonra **Oluştur**’u seçin. 

## <a name="create-an-apple-enrollment-profile"></a>Apple kayıt profili oluşturma
Belirtecinizi yüklediğinize göre, DEP cihazları için kayıt profili oluşturabilirsiniz. Bir cihaz kayıt profili, kayıt sırasında bir grup cihaza uygulanan ayarları tanımlar.

1. Azure portalında Intune’da, **Cihaz kaydı** > **Apple kaydı** > **Kayıt programı belirteçleri**’ni seçin.

2. Yalnızca yüklü bir belirteç seçin, **profilleri** > **profili oluşturma**.

3. Altında **profili oluştur**, girin *TestDEPProfile* için **adı** ve *iOS cihazları için test DEP* için **açıklaması** . Kullanıcılar bu ayrıntıları göremez.

4. İçin **kullanıcı benzeşimi**, seçin **kullanıcı benzeşimi ile Kaydet**. Bu seçenek, uygulamaları yükleme gibi hizmetler için şirket Portalı'nı kullanmak isteyen kullanıcılara ait cihazlar için kullanılabilir.

5. Seçin **Hayır** altında **Şirket portalı yerine Apple Kurulum Yardımcısı ile kimlik doğrulama**.

6. Seçin **cihaz yönetim ayarları** ve **Hayır** altında **denetimli**. Denetimli cihazlarda, daha fazla yönetim seçeneği verir, ancak bu öğreticinin amaçları doğrultusunda kullanmaz.

7. **Tamam**’ı seçin.

8. Seçin **Kurulum Yardımcısı özelleştirme** girin *Öğretici bölüm* için **bölüm adı**. Kullanıcıların gördükleri bunlar dokunduğunuzda bu dizedir **yapılandırması hakkında** cihaz etkinleştirme sırasında.

9. Altında **departman telefonu**, bir telefon numarası girin. Bu sayı kullanıcılar seçeneğine dokunduğunda görüntülenir **yardıma ihtiyacınız** etkinleştirme sırasında düğmesi.

10. Yapabilecekleriniz **Göster** veya **Gizle** ekranlar cihaz etkinleştirme sırasında çeşitli. Bu öğreticinin amaçları doğrultusunda, ayarlama **geçiş kodu** için **Göster** ve diğerlerine de **Gizle**.

11. **Tamam** > **Oluştur**'u seçin.

## <a name="sync-managed-devices"></a>Yönetilen cihazları eşitleme

Artık hangi cihazların bu belirtece atanan görebilirsiniz.

1. Azure portalında ıntune'da, **cihaz kaydı** > **Apple kaydı** > **kayıt programı belirteçleri** > içinde bir belirteç seçin Listenin > **cihazları** > **eşitleme**.

## <a name="assign-an-enrollment-profile-to-ios-devices"></a>İOS cihazlara bir kayıt profili atama

Cihazların kaydedilmesi için bunlara bir kayıt programı profili atamalısınız.

1. Azure portalında ıntune'da, **cihaz kaydı** > **Apple kaydı** > **kayıt programı belirteçleri** > belirtecinizi seçin listede.
2. **Cihazlar** > listeden cihazları seçin > **Profil ata**’yı seçin.
3. **Profil ata**'nın altında cihazlar için bir profil seçin > **Ata**’ya tıklayın.

## <a name="distribute-devices-to-users"></a>Cihazları kullanıcılara dağıtma

Ayarladığınız yönetim ve Apple ve Intune arasında eşitlemeyi ve DEP cihazlarınızın izin vermek için bir profil atadınız. Artık cihazları kullanıcılara dağıtabilirsiniz. Kullanıcı benzeşimli cihazlar, her kullanıcıya bir Intune lisansı atanmasını gerektirir.

## <a name="clean-up-resources"></a>Kaynakları temizleme

Autopilot cihazları artık kullanmak istemiyorsanız, bunları silebilir.

- Cihazlar Intune’a kayıtlıysa önce bunları [Azure Active Directory portalından silmeniz](devices-wipe.md#delete-devices-from-the-azure-active-directory-portal) gerekir.

<!--ask tiffany how to do this-->

## <a name="next-steps"></a>Sonraki adımlar

İOS cihazlarını kaydetmek için kullanılabilen diğer seçenekler hakkında daha fazla bilgi bulabilirsiniz.

> [!div class="nextstepaction"]
> [Ayrıntılı iOS DEP kaydı makale](device-enrollment-program-enroll-ios.md)
