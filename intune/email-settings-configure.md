---
title: Microsoft Intune'da e-posta ayarlarını yapılandırma - Azure | Microsoft Docs
titleSuffix: ''
description: Microsoft Intune’da bir e-posta profili oluşturun ve bu profili Android Kurumsal, iOS ve Windows cihazlarına dağıtın. Yönettiğiniz cihazlarda şirket e-postasına bağlanmak için bir e-posta sunucusu ve kimlik doğrulama yönteminin de dahil olduğu yaygın e-posta ayarlarını yapılandırmak için e-posta profilini kullanın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/10/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6a80ff2ca7c2265da358f57291032f59d47d22dd
ms.sourcegitcommit: 063177c6c365fef3642edd7c455790958469aad9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/30/2019
ms.locfileid: "66412349"
---
# <a name="add-email-settings-to-devices-using-intune"></a>Intune kullanarak cihazlara e-posta ayarları ekleme

Microsoft Intune, kuruluşunuzdaki cihazlara dağıtabileceğiniz farklı e-posta ayarları içerir. BT yöneticisine e-posta profilleri, Office 365 ve Gmail gibi bir e-posta sunucusuna bağlanmak için özel ayarlar oluşturur. Son kullanıcılar ardından bağlanmak, kimlik doğrulaması ve mobil cihazlarından Kurumsal e-posta hesaplarını eşitlemek. Oluşturma ve bir e-posta profili dağıtımı, ayarlar birçok cihaz arasında standart doğrulayabilirsiniz. Ayrıca doğru e-posta ayarlarını bilmeyen son kullanıcılardan gelen destek çağrılarını azaltabilirsiniz.

Aşağıdaki cihazlarda yerleşik e-posta ayarlarını yapılandırmak için e-posta profillerini kullanabilirsiniz:

- Android Samsung Knox Standard 4.0 ve üzeri
- Android Kurumsal
- iOS 8.0 ve üzeri
- Windows Phone 8.1 ve üzeri
- Windows 10 (masaüstü) ve Windows 10 Mobile

Bu makalede, Microsoft Intune’da e-posta profili oluşturma işlemi gösterilir. Ayrıca daha özel ayarlar için farklı platformlara bağlantılar içerir.

## <a name="create-a-device-profile"></a>Bir cihaz profili oluşturma

1. Oturum [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**'u seçin.
3. E-posta profili için **Ad** ve **Açıklama** girin.
4. Açılan listeden **Platform** bilginizi seçin. Seçenekleriniz şunlardır:

    - **Android** (yalnızca Samsung Android Knox Standard)
    - **Android kurumsal**
    - **iOS**
    - **Windows Phone 8.1**
    - **Windows 10 ve üzeri**

5. **Profil** türü açılan listesinde **E-posta**’yı seçin.
6. Yapılandırabileceğiniz ayarlar platforma göre değişiklik gösterebilir. Belirli ayarlar için platformunuzu seçin:

    - [Android Samsung Knox Standard ayarları](email-settings-android.md)
    - [Android Kurumsal ayarları](email-settings-android-enterprise.md)
    - [iOS ayarları](email-settings-ios.md)
    - [Windows Phone 8.1 ayarları](email-settings-windows-phone-8-1.md)
    - [Windows 10 ayarları](email-settings-windows-10.md)

Ayarlarınızı girdikten ve profili oluşturduktan sonra profiliniz profil listesinde gösterilir. Daha sonra [bu profili bazı gruplara atayın](device-profile-assign.md).

## <a name="remove-an-email-profile"></a>E-posta profilini kaldırma

E-posta profilleri kullanıcı gruplarına değil cihaz gruplarına atanır. Cihazda sadece bir e-posta profili olduğunda bile e-posta profilini kaldırmanın farklı yolları vardır:

- **Seçenek 1**: E-posta profili açın (**cihaz Yapılandırması** > **profilleri**) ve **atamaları**. **Ekle** sekmesi, profil atanmış grupları gösterir. Gruba sağ tıklayın ve **Kaldır**’ı seçin. Değişikliklerinizi kaydetmek için **Kaydet**’e tıklamayı unutmayın.

- **Seçenek 2**: [Cihazı devre dışı bırakma veya silme](devices-wipe.md). Veri ve ayarları seçmeli olarak veya tamamen kaldırmak için bu eylemleri kullanabilirsiniz.

## <a name="secure-email-access"></a>E-posta erişimini güvenli hale getirme

E-posta profillerinin güvenliği sağlamaya yardımcı olmak için aşağıdaki seçenekleri kullanabilirsiniz:

- **Sertifikaları**: E-posta profilini oluştururken, Intune'da önceden oluşturduğunuz bir sertifika profilini seçin. Bu sertifika, kimlik sertifikası olarak bilinir. Kullanıcının cihazının bağlanmasına izin verildiğini doğrulamak için bir güvenilir sertifika profiline veya kök sertifikaya göre kimlik doğrulaması yapar. Güvenilir sertifika, e-posta bağlantısının kimliğini doğrulayan bilgisayara atanır. Bu bilgisayar genellikle yerel posta sunucusudur.

  Intune’da sertifika profillerini oluşturma ve kullanma hakkında daha fazla bilgi için bkz. [Intune ile sertifikaları yapılandırma](certificates-configure.md).

- **Kullanıcı adı ve parola**: Son kullanıcı, bir kullanıcı adı ve parola girerek yerel posta sunucusunda kimliğini doğrular. Parola e-posta profilinde bulunmaz. Bu nedenle, son kullanıcının e-postaya bağlanırken parolasını girer.

## <a name="how-intune-handles-existing-email-accounts"></a>Intune mevcut e-posta hesaplarını nasıl işler?

Kullanıcı zaten bir e-posta hesabı yapılandırılmışsa e-posta profili platforma bağlı olarak farklı şekilde atanır.

- **iOS**: Konak adına ve e-posta adresine bağlı olarak var olan ve yinelenen bir e-posta profili olduğu algılanır. Yinelenen e-posta profili, Intune profilinin atamasını engeller. Bu durumda, Şirket portalı uygulaması, uyumlu olmayan ve el ile yapılandırılan profili kaldırmak için son kullanıcı komut istemleri kullanıcıyı uyarır. Bu senaryo önlemeye yardımcı olmak için son kullanıcıların bilgi *önce* Intune'un profili ayarlamasına izin veren bir e-posta profili yükleniyor.

- **Windows:** Konak adına ve e-posta adresine bağlı olarak var olan ve yinelenen bir e-posta profili olduğu algılanır. Intune son kullanıcı tarafından oluşturulan mevcut e-posta profilinin üzerine yazar.

- **Android Samsung Knox Standard**: E-posta adresine bağlı olarak var olan ve yinelenen bir e-posta profili algılanır ve Intune profili bunun üzerine yazılır. Android, profili tanımlamak için ana bilgisayar adı kullanmaz. Farklı ana bilgisayarlarda aynı e-posta adresini kullanarak birden çok e-posta profili oluşturmayın. Profiller birbirinin üzerine.

- **Android iş profilleri**: Intune, iki Android iş e-posta profilleri sağlar: biri Gmail uygulamasını ve Nine Work uygulamasına yönelik biri. Bu uygulamalar Google Play Store’da mevcuttur ve cihaz iş profilinde yüklenir. Bu uygulamalar, yinelenen profiller oluşturmayın. Her iki uygulama da Exchange bağlantılarını destekler. E-posta bağlantısını kullanmak için bu e-posta uygulamalarından birini kullanıcılarınızın cihazlarına dağıtın. Ardından uygun e-posta profilini oluşturun ve dağıtın. Nine Work gibi e-posta uygulamaları ücretsiz olmayabilir. Uygulamanın lisanslama ayrıntılarını gözden geçirin veya sorunuz varsa uygulama şirketine başvurun.

## <a name="changes-to-assigned-email-profiles"></a>Atanan e-posta profillerindeki değişiklikler

Önceden atanmış bir e-posta profilinde değişiklik yaparsanız, son kullanıcılara e-posta ayarlarının yeniden yapılandırmasını onaylamalarını isteyen bir ileti gösterilebilir.

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturulduğunda henüz herhangi bir işlem gerçekleştirmez. Ardından, [bazı cihazlara profil atama](device-profile-assign.md).
