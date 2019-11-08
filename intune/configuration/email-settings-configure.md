---
title: Microsoft Intune'da e-posta ayarlarını yapılandırma - Azure | Microsoft Docs
titleSuffix: ''
description: Microsoft Intune’da bir e-posta profili oluşturun ve bu profili Android Kurumsal, iOS ve Windows cihazlarına dağıtın. Yönettiğiniz cihazlarda şirket e-postasına bağlanmak için bir e-posta sunucusu ve kimlik doğrulama yönteminin de dahil olduğu yaygın e-posta ayarlarını yapılandırmak için e-posta profilini kullanın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/07/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 75644ac4d8ccfb8a63e077f2b6625ac96364f5d7
ms.sourcegitcommit: 1a7f04c80548e035be82308d2618492f6542d3c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73755202"
---
# <a name="add-email-settings-to-devices-using-intune"></a>Intune kullanarak cihazlara e-posta ayarları ekleme

Microsoft Intune, kuruluşunuzdaki cihazlara dağıtabileceğiniz farklı e-posta ayarları içerir. BT Yöneticisi, Office 365 ve Gmail gibi bir posta sunucusuna bağlanmak için belirli ayarlarla e-posta profilleri oluşturur. Son kullanıcılar daha sonra mobil cihazlarındaki kurumsal e-posta hesaplarını bağlayıp, kimlik doğrulaması yapar ve eşitler. Bir e-posta profili oluşturup dağıtarak, ayarların birçok cihazda standart olduğunu doğrulayabilirsiniz. Ayrıca doğru e-posta ayarlarını bilmeyen son kullanıcılardan gelen destek çağrılarını azaltabilirsiniz.

Aşağıdaki cihazlarda yerleşik e-posta ayarlarını yapılandırmak için e-posta profillerini kullanabilirsiniz:

- Android Samsung Knox Standard 4.0 ve üzeri
- Android Kurumsal
- iOS 8.0 ve üzeri
- Windows Phone 8.1 ve üzeri
- Windows 10 (masaüstü) ve Windows 10 Mobile

Bu makalede, Microsoft Intune’da e-posta profili oluşturma işlemi gösterilir. Ayrıca daha özel ayarlar için farklı platformlara bağlantılar içerir.

## <a name="create-a-device-profile"></a>Bir cihaz profili oluşturma

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. **Profil oluşturma** > **yapılandırma profilleri** > **cihazları** seçin.
3. Aşağıdaki özellikleri girin:

    - **Ad**: ilke için açıklayıcı bir ad girin. İlkelerinizi daha sonra kolayca tanıyacak şekilde adlandırın. Örneğin, iyi bir ilke adı **tüm Windows cihazları Için e-posta ayarları**olur.
    - **Açıklama**: Profil için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
    - **Platform**: cihazlarınızın platformunu seçin. Seçenekleriniz şunlardır:

        - **Android** (yalnızca Samsung Android Knox Standard)
        - **Android kurumsal**
        - **iOS/ıpados**
        - **Windows Phone 8.1**
        - **Windows 10 ve üzeri**

    - **Profil türü**: **e-posta**' yı seçin.

4. Seçtiğiniz platforma bağlı olarak, yapılandırabileceğiniz ayarlar farklılık gösterir. Ayrıntılı ayarlar için platformunuzu seçin:

    - [Android Samsung KNOX Standard ayarları](../email-settings-android.md)
    - [Android kurumsal ayarları](../email-settings-android-enterprise.md)
    - [iOS/ıpados ayarları](email-settings-ios.md)
    - [Windows Phone 8.1 ayarları](email-settings-windows-phone-8-1.md)
    - [Windows 10 ayarları](email-settings-windows-10.md)

5. İşiniz bittiğinde **Tamam** > **Oluştur**’u seçerek değişikliklerinizi kaydedin.

Ayarlarınızı girdikten ve profili oluşturduktan sonra profiliniz profil listesinde gösterilir. Daha sonra [bu profili bazı gruplara atayın](../device-profile-assign.md).

## <a name="remove-an-email-profile"></a>E-posta profilini kaldırma

E-posta profilleri kullanıcı gruplarına değil cihaz gruplarına atanır. Cihazda sadece bir e-posta profili olduğunda bile e-posta profilini kaldırmanın farklı yolları vardır:

- **Seçenek 1**: e-posta profilini açın (**cihazlar** > **yapılandırma profilleri** > profilinizi seçin) ve **atamalar**' ı seçin. **Ekle** sekmesi, profil atanmış grupları gösterir. Gruba sağ tıklayın ve **Kaldır**’ı seçin. Değişikliklerinizi kaydetmek için **Kaydet**’e tıklamayı unutmayın.

- **2. Seçenek**: [Cihazı devre dışı bırakın veya silin](../remote-actions/devices-wipe.md). Veri ve ayarları seçmeli olarak veya tamamen kaldırmak için bu eylemleri kullanabilirsiniz.

## <a name="secure-email-access"></a>E-posta erişimini güvenli hale getirme

E-posta profillerinin güvenliği sağlamaya yardımcı olmak için aşağıdaki seçenekleri kullanabilirsiniz:

- **Sertifikalar**: E-posta profilini oluştururken, daha önce Intune’da oluşturulan bir sertifika profilini seçersiniz. Bu sertifika, kimlik sertifikası olarak bilinir. Kullanıcının cihazının bağlanmasına izin verildiğini doğrulamak için bir güvenilir sertifika profiline veya kök sertifikaya göre kimlik doğrulaması yapar. Güvenilir sertifika, e-posta bağlantısının kimliğini doğrulayan bilgisayara atanır. Bu bilgisayar genellikle yerel posta sunucusudur.

  Intune’da sertifika profillerini oluşturma ve kullanma hakkında daha fazla bilgi için bkz. [Intune ile sertifikaları yapılandırma](../protect/certificates-configure.md).

- **Kullanıcı adı ve parola**: Son Kullanıcı, bir Kullanıcı adı ve parola girerek Yerel posta sunucusunda kimliğini doğrular. Parola e-posta profilinde bulunmaz. Bu nedenle, son kullanıcı e-postaya bağlanırken parolayı girer.

## <a name="how-intune-handles-existing-email-accounts"></a>Intune mevcut e-posta hesaplarını nasıl işler?

Kullanıcı zaten bir e-posta hesabı yapılandırılmışsa e-posta profili platforma bağlı olarak farklı şekilde atanır.

- **iOS**: Konak adına ve e-posta adresine bağlı olarak var olan ve yinelenen bir e-posta profili algılanmıştır. Yinelenen e-posta profili, Intune profilinin atamasını engeller. Bu durumda, Şirket Portalı uygulama kullanıcıya uyumlu olmadıkları konusunda bilgilendirir ve son kullanıcıdan yapılandırılmış profili el ile kaldırmasını ister. Bu senaryoyu önlemeye yardımcı olmak için son kullanıcılarınıza Intune 'un profili ayarlamasına izin veren bir e-posta profili yüklemeden *önce* kaydolmalarını söyleyin.

- **Windows:** Konak adına ve e-posta adresine bağlı olarak var olan ve yinelenen bir e-posta profili olduğu algılanır. Intune, son kullanıcı tarafından oluşturulan mevcut e-posta profilinin üzerine yazar.

- **Android Samsung Knox Standard**: E-posta adresine bağlı olarak mevcut ve yinelenen bir e-posta profili algılanmış ve Intune profili bunun üzerine yazılmıştır. Android, profili tanımlamak için ana bilgisayar adı kullanmaz. Farklı ana bilgisayarlarda aynı e-posta adresini kullanarak birden çok e-posta profili oluşturmayın. Profiller birbirinin üzerine yazılır.

- **Android iş profilleri**: Intune, Gmail uygulaması için bir diğeri Ise dokuz iş uygulaması için olmak üzere iki Android iş e-posta profili sağlar. Bu uygulamalar Google Play Store’da mevcuttur ve cihaz iş profilinde yüklenir. Bu uygulamalar Yinelenen profiller oluşturmaz. Her iki uygulama da Exchange bağlantılarını destekler. E-posta bağlantısını kullanmak için bu e-posta uygulamalarından birini kullanıcılarınızın cihazlarına dağıtın. Ardından uygun e-posta profilini oluşturun ve dağıtın. Nine Work gibi e-posta uygulamaları ücretsiz olmayabilir. Uygulamanın lisanslama ayrıntılarını gözden geçirin veya sorunuz varsa uygulama şirketine başvurun.

## <a name="changes-to-assigned-email-profiles"></a>Atanan e-posta profillerindeki değişiklikler

Önceden atanmış bir e-posta profilinde değişiklik yaparsanız, son kullanıcılara e-posta ayarlarının yeniden yapılandırmasını onaylamalarını isteyen bir ileti gösterilebilir.

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturulduğunda henüz herhangi bir işlem gerçekleştirmez. Daha sonra, [profili atayın](../device-profile-assign.md).
