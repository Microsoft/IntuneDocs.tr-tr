---
title: "Intune e-posta ayarlarını yapılandırma"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Yönettiğiniz cihazlarda şirket e-postasına bağlantılar oluşturmak için Intune’u nasıl yapılandıracağınızı öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 484bd9b0-fbf1-4f4f-940c-6b12fa07e228
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: ca4f1adc5704ecd66d2af7823f95ca63ec20469e
ms.openlocfilehash: 786028412ca46d07e5180f469d07f9103f956033
ms.lasthandoff: 03/17/2017


---

# <a name="how-to-configure-email-settings-in-microsoft-intune"></a>Microsoft Intune’da e-posta ayarlarını yapılandırma

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Yönettiğiniz cihazları, şirket e-postasına bağlanmak ve eşitleme yapmak için gereken ayarlarla yapılandırmak için e-posta profillerini kullanabilirsiniz. Bu, tüm cihazlar genelinde standart ayarların kullanıldığından emin olmanıza yardımcı olabildiği gibi, doğru e-posta ayarlarını bilmeyen son kullanıcıların desteği daha az aramalarını sağlamaya da katkıda bulunabilir.

Platformların çoğunda yerleşik posta istemcisi desteklenir. Üçüncü taraf e-posta uygulamalarının çoğu şu anda desteklenmemektedir.

Aşağıdaki cihaz türlerinde yerel e-posta istemcisini yapılandırmak için e-posta profillerini kullanabilirsiniz:

- Android 4.0 ve üzeri
- iOS 8.0 ve üzeri
- Windows Phone 8.1 ve üzeri
- Windows 10 (masaüstü) ve Windows 10 Mobile

Bu konu başlığı altında verilen bilgileri kullanarak e-posta profilini yapılandırmanın temellerini öğrenin ve sonra cihaza özgü bilgiler için her platformla ilgili olarak sağlanan konuları okuyun.

## <a name="create-a-device-profile-containing-email-settings"></a>E-posta ayarlarını içeren bir cihaz profili oluşturma

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **Diğer** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihaz yapılandırması**’nı seçin.
2. **Cihaz Yapılandırması** dikey penceresinde **Yönet** > **Profiller**’i seçin.
3. Profiller dikey penceresinde **Profil Oluştur**’u seçin.
4. **Profil Oluştur** dikey penceresinde, e-posta profili için bir **Ad** ve **Açıklama** girin.
5. **Platform** açılan listesinden, e-posta ayarlarını uygulamak istediğiniz cihaz platformunu seçin. Şu anda, e-posta cihaz ayarları için aşağıdaki platformlardan birini seçebilirsiniz:
    - **Outlook Web Access (OWA)**
    - **Android**
    - **Windows Phone 8.1**
    - **Windows 10 ve üzeri**
6. **Profil** türü açılan listesinden **E-posta**’yı seçin.
7. Seçtiğiniz platforma bağlı olarak , yapılandırabileceğiniz ayarlar farklılık gösterir. Her platformun ayrıntılı ayarları için aşağıdaki konulardan birine gidin:
    - [Android ayarları](email-profile-settings-for-android.md)
    - [iOS ayarları](email-profile-settings-for-ios.md)
    - [Windows Phone 8.1 ayarları](email-profile-settings-for-windows-phone-8-1.md)
    - [Windows 10 ayarları](email-profile-settings-for-windows-10.md)
8. Bitirdiğinizde **Profil Oluştur** dikey penceresine dönün ve **Oluştur**’a basın.

Profil oluşturulur ve profil listesi dikey penceresinde görüntülenir.
Devam edip bu profili gruplara atamak isterseniz, bkz. [Cihaz profillerini atama](how-to-assign-device-profiles.md).

## <a name="further-information"></a>Daha fazla bilgi

### <a name="remove-an-email-profile"></a>E-posta profilini kaldırma

Bir cihazdan e-posta profilini kaldırmak isterseniz atamayı düzenleyin ve cihazın üye olduğu tüm grupları kaldırın. Cihazda yalnızca bir e-posta profili olduğunda, bu e-posta profilini bu yöntemle kaldıramayacağınızı unutmayın.

### <a name="securing-email-access"></a>E-posta erişimi güvenliğini sağlama

E-posta profillerinin güvenliği sağlamaya yardımcı olmak için iki yöntemden biri kullanabilirsiniz:

1. **Sertifikalar** - E-posta profilini oluştururken, daha önce Intune’da oluşturduğunuz bir sertifika profilini seçersiniz. Bu, kimlik sertifikası olarak bilinir ve kullanıcının cihazının bağlanmasına izin verildiğini belirtmek için güvenilir bir sertifika profiline (veya kök sertifikaya) göre kimlik doğrulaması yapmak için kullanılır. Güvenilir sertifika, e-posta bağlantısı kimliğini doğrulayan bilgisayara (genellikle yerel posta sunucusu) dağıtılır.
Intune’da sertifika profillerini oluşturma ve kullanma hakkında daha fazla bilgi için bkz. [Intune ile sertifikaları yapılandırma](/intune-azure/configure-devices/how-to-configure-certificates).
2. **Kullanıcı adı ve parola** - Kullanıcı, kullanıcı adını ve parolasını sağlayarak yerel posta sunucusunda kimliğini doğrular.
E-posta profilinde parola bulunmadığından, e-postaya bağlanırken kullanıcı tarafından belirtilmesi gerekir.


### <a name="how-intune-handles-existing-email-accounts"></a>Intune mevcut e-posta hesaplarını nasıl işler?

Kullanıcı zaten bir e-posta hesabı yapılandırmışsa, Intune e-posta profili atamasının ne sonuç vereceği cihaz platformuna bağlıdır:

- **iOS:** Konak adına ve e-posta adresine bağlı olarak var olan ve yinelenen bir e-posta profili olduğu algılanır. Yinelenen e-posta profili, Intune profilinin atamasını engeller. Bu durumda, Şirket Portalı kullanıcıya uyumlu olmadığını bildirir ve kullanıcıdan el ile yapılandırılan profili kaldırmasını ister. Bu sorunun önüne geçilmesine yardımcı olmak için, kullanıcılarınızdan e-posta profilini yüklemeden önce kaydolmalarını isteyin. Bu, Intune’un profili ayarlamasına olanak tanır.
- **Windows:** Konak adına ve e-posta adresine bağlı olarak var olan ve yinelenen bir e-posta profili olduğu algılanır. Intune kullanıcı tarafından oluşturulmuş, var olan e-posta profilinin üzerine yazar.
- **Android:** E-posta adresine bağlı olarak var olan ve yinelenen bir e-posta profili algılanır ve Intune profili bunun üzerine yazılır.
Android’in profili algılamak için konak adını kullanmaması nedeniyle, farklı konaklarda aynı e-posta adresinde kullanmak üzere birden çok e-posta profili oluşturursanız bunlar birbirinin üzerine yazılacağından, bunu yapmamanızı öneririz.

