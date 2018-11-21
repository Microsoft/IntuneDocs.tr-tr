---
title: Microsoft Intune'da e-posta ayarlarını yapılandırma - Azure | Microsoft Docs
titleSuffix: ''
description: Microsoft Intune’da bir e-posta profili oluşturun ve bu profili Android Kurumsal, iOS ve Windows cihazlarına dağıtın. Yönettiğiniz cihazlarda şirket e-postasına bağlanmak için bir e-posta sunucusu ve kimlik doğrulama yönteminin de dahil olduğu yaygın e-posta ayarlarını yapılandırmak için e-posta profilini kullanın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 33a7593adcab7df76020b8bfe520cf6cbd3c6455
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52186163"
---
# <a name="add-email-settings-to-devices-using-intune"></a>Intune kullanarak cihazlara e-posta ayarları ekleme

Microsoft Intune, kuruluşunuzdaki cihazlara dağıtabileceğiniz farklı e-posta ayarları içerir. BT yöneticisi, Office 365 ve Gmail gibi bir posta sunucusuna bağlamak için belirli ayarları olan e-posta profilleri oluşturabilir. Ardından kullanıcılar mobil cihazlarından kurumsal e-posta hesaplarına bağlanabilir, kimlik doğrulaması ve eşitleme yapabilir. E-posta profili oluşturup dağıtarak ayarların birçok cihaz arasında standart olduğunu onaylayabilirsiniz. Ayrıca doğru e-posta ayarlarını bilmeyen son kullanıcılardan gelen destek çağrılarını azaltabilirsiniz.

Aşağıdaki cihazlarda yerleşik e-posta ayarlarını yapılandırmak için e-posta profillerini kullanabilirsiniz:

- Android Samsung Knox Standard 4.0 ve üzeri
- Android iş profili cihazları
- iOS 8.0 ve üzeri
- Windows Phone 8.1 ve üzeri
- Windows 10 (masaüstü) ve Windows 10 Mobile

Bu makalede, Microsoft Intune’da e-posta profili oluşturma işlemi gösterilir. Ayrıca daha özel ayarlar için farklı platformlara bağlantılar içerir.

## <a name="create-a-device-profile"></a>Bir cihaz profili oluşturma

1. [Azure portalında](https://portal.azure.com) **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
2. **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**'u seçin.
3. E-posta profili için **Ad** ve **Açıklama** girin.
4. Açılan listeden **Platform** bilginizi seçin. Seçenekleriniz şunlardır:

    - **Android** (yalnızca Samsung Android Knox Standard)
    - **Android kurumsal**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 ve üzeri**
    - **Windows 10 ve üzeri**

5. **Profil** türü açılan listesinde **E-posta**’yı seçin.
6. Yapılandırabileceğiniz ayarlar platforma göre değişiklik gösterebilir. Belirli ayarlar için platformunuzu seçin:

    - [Android iş profili ve Samsung Knox Standard ayarları](email-settings-android.md)
    - [iOS ayarları](email-settings-ios.md)
    - [Windows Phone 8.1 ayarları](email-settings-windows-phone-8-1.md)
    - [Windows 10 ayarları](email-settings-windows-10.md)

Ayarlarınızı girdikten ve profili oluşturduktan sonra profiliniz profil listesinde gösterilir. Daha sonra [bu profili bazı gruplara atayın](device-profile-assign.md).

## <a name="remove-an-email-profile"></a>E-posta profilini kaldırma

E-posta profilleri kullanıcı gruplarına değil cihaz gruplarına atanır. Cihazda sadece bir e-posta profili olduğunda bile e-posta profilini kaldırmanın farklı yolları vardır:

- **1. Seçenek**: E-posta profilini açın (**Cihaz yapılandırması** > **Profiller**)ve **Atamalar**’ı seçin. **Ekle** sekmesi, profil atanmış grupları gösterir. Gruba sağ tıklayın ve **Kaldır**’ı seçin. Değişikliklerinizi kaydetmek için **Kaydet**’e tıklamayı unutmayın.

- **2. Seçenek**: [Cihazı devre dışı bırakın veya silin](devices-wipe.md). Veri ve ayarları seçmeli olarak veya tamamen kaldırmak için bu eylemleri kullanabilirsiniz.

## <a name="secure-email-access"></a>E-posta erişimini güvenli hale getirme

E-posta profillerinin güvenliği sağlamaya yardımcı olmak için aşağıdaki seçenekleri kullanabilirsiniz:

- **Sertifikalar**: E-posta profilini oluştururken, daha önce Intune’da oluşturulan bir sertifika profilini seçersiniz. Bu sertifika, kimlik sertifikası olarak bilinir. Kullanıcının cihazının bağlanmasına izin verildiğini doğrulamak için bir güvenilir sertifika profiline veya kök sertifikaya göre kimlik doğrulaması yapar. Güvenilir sertifika, e-posta bağlantısının kimliğini doğrulayan bilgisayara atanır. Bu bilgisayar genellikle yerel posta sunucusudur.

  Intune’da sertifika profillerini oluşturma ve kullanma hakkında daha fazla bilgi için bkz. [Intune ile sertifikaları yapılandırma](certificates-configure.md).

- **Kullanıcı adı ve parola**: Kullanıcı, kullanıcı adı ve parola girerek yerel posta sunucusunda kimliğini doğrular. Parola e-posta profilinde bulunmaz. Bu nedenle kullanıcının e-postaya bağlanırken parolayı girmesi gerekir.

## <a name="how-intune-handles-existing-email-accounts"></a>Intune mevcut e-posta hesaplarını nasıl işler?

Kullanıcı zaten bir e-posta hesabı yapılandırılmışsa e-posta profili platforma bağlı olarak farklı şekilde atanır.

- **iOS**: Konak adına ve e-posta adresine bağlı olarak var olan ve yinelenen bir e-posta profili algılanmıştır. Yinelenen e-posta profili, Intune profilinin atamasını engeller. Bu durumda, Şirket Portalı uygulaması kullanıcıya uyumlu olmadığını bildirir ve kullanıcıdan yapılandırılan profili el ile kaldırmasını ister. Bu senaryonun önüne geçilmesine yardımcı olmak için, kullanıcılarınıza e-posta profilini yüklemeden *önce* kaydolmalarını söyleyin. Bu, Intune’un profili ayarlamasına olanak tanır.

- **Windows:** Konak adına ve e-posta adresine bağlı olarak var olan ve yinelenen bir e-posta profili olduğu algılanır. Intune kullanıcı tarafından oluşturulmuş, var olan e-posta profilinin üzerine yazar.

- **Android Samsung Knox Standard**: E-posta adresine bağlı olarak mevcut ve yinelenen bir e-posta profili algılanmış ve Intune profili bunun üzerine yazılmıştır. Android, profili tanımlamak için ana bilgisayar adı kullanmaz. Farklı ana bilgisayarlarda aynı e-posta adresini kullanarak birden çok e-posta profili oluşturmayın. Profiller birbirinin üzerine yazılır.

- **Android iş profilleri**: Intune, biri Gmail uygulaması ve diğeri Nine Work uygulaması için olmak üzere iki Android iş e-posta profili sağlar. Bu uygulamalar Google Play Store’da mevcuttur ve cihaz iş profilinde yüklenir. Bu uygulamalar yinelenen profiller oluşturmaz. Her iki uygulama da Exchange bağlantılarını destekler. E-posta bağlantısını kullanmak için bu e-posta uygulamalarından birini kullanıcılarınızın cihazlarına dağıtın. Ardından uygun e-posta profilini oluşturun ve dağıtın. Nine Work gibi e-posta uygulamaları ücretsiz olmayabilir. Uygulamanın lisanslama ayrıntılarını gözden geçirin veya sorunuz varsa uygulama şirketine başvurun.

## <a name="changes-to-assigned-email-profiles"></a>Atanan e-posta profillerindeki değişiklikler

Önceden atanmış bir e-posta profilinde değişiklik yaparsanız, son kullanıcılara e-posta ayarlarının yeniden yapılandırmasını onaylamalarını isteyen bir ileti gösterilebilir.

## <a name="next-steps"></a>Sonraki adımlar
Profil oluşturulduğunda henüz herhangi bir işlem gerçekleştirmez. Ardından, [profili bazı cihazlara atayın](device-profile-assign.md).