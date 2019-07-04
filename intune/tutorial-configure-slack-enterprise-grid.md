---
title: Öğretici - Intune, EMM ve uygulama yapılandırmasında kullanılacak Slack yapılandırın
titleSuffix: Microsoft Intune
description: Bu öğreticide Slack EMM ve uygulama yapılandırması için Intune kullanmak üzere yapılandırır.
keywords: ''
author: ErikRe
ms.author: erikre
manager: dougeby
ms.date: 06/11/2019
ms.topic: tutorial
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 55db37c5-0da7-4d9c-8027-525afb1c6349
Customer intent: As an Intune admin, I want to learn how to configure Slack to use Intune for EMM and app configuration..
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e7ff4e1fd9f055268a461d1a81b8a2e31fe3d32b
ms.sourcegitcommit: bccfbf1e3bdc31382189fc4489d337d1a554e6a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/03/2019
ms.locfileid: "67548985"
---
# <a name="tutorial-configure-slack-to-use-intune-for-emm-and-app-configuration"></a>Öğretici: Intune, EMM ve uygulama yapılandırmasında kullanılacak Slack yapılandırın

Slack, Microsoft Intune kullanabileceğiniz bir işbirliği uygulamasıdır.   

Bu öğreticide şunları yapacaksınız:
> [!div class="checklist"]
> - Intune Kurumsal mobilite Yönetim (EMM) sağlayıcısı olarak Slack Kurumsal Kılavuzunuzun üzerinde ayarlayın. Intune ile yönetilen cihazlar için kılavuz planınızın çalışma alanlarına erişimi sınırlayan mümkün olacaktır.
> - EMM uygulaması iOS ve Android iş profili cihazları için Slack uygulaması için Slack yönetmek için uygulama yapılandırma ilkeleri oluşturun.
> - Intune cihaz uyumluluk ilkeleri Android koşullar ayarlamak için oluşturma ve iOS cihazlarının uyumlu olarak değerlendirilmesi için uyması gerekir.

Bir Intune aboneliğiniz yoksa [ücretsiz bir deneme hesabı için kaydolun](free-trial-sign-up.md).

## <a name="prerequisites"></a>Önkoşullar
Bu öğretici için aşağıdaki abonelik sahip bir test kiracısına ihtiyacınız olacak:
- Azure Active Directory Premium ([ücretsiz deneme](https://azure.microsoft.com/free/?WT.mc_id=A261C142F))
- Intune aboneliği ([ücretsiz deneme sürümü](free-trial-sign-up.md))

Ayrıca ihtiyacınız olacak bir [Slack Kurumsal kılavuz](https://get.slack.help/hc/articles/360004150931-What-is-Slack-Enterprise-Grid-) planı.

## <a name="configure-your-slack-enterprise-grid-plan"></a>Slack Kurumsal kılavuz planınızı yapılandırma
Üzerinde EMM izleyerek Slack Kurumsal kılavuz planınız için kapatma [Slack'ın yönergeleri](https://get.slack.help/hc/articles/115002579426-Enable-Enterprise-Mobility-Management-for-your-org#step-2:-turn-on-emm) ve [Azure Active Directory connect](https://docs.microsoft.com/azure/active-directory/saas-apps/slack-tutorial) kılavuz planınızın kimlik sağlayıcısı (IDP).

## <a name="sign-in-to-intune"></a>Intune'da oturum açma
[Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da Genel Yönetici veya Intune Hizmet Yöneticisi olarak oturum açın. Intune Deneme aboneliği oluşturduysanız aboneliği oluşturduğunuz hesap Genel yönetici rolüne sahip olur.

## <a name="set-up-slack-for-emm-on-ios-devices"></a>Slack ' için EMM iOS cihazlarında ayarlayın.
İOS uygulaması Slack EMM için Intune kiracınıza ekleyin ve Slack EMM sağlayıcısı olarak Intune ile kuruluşlar iOS erişmelerini sağlamak için uygulama yapılandırma ilkesi oluşturun.

### <a name="add-slack-for-emm-to-intune"></a>Slack EMM için Intune'a ekleme
Intune yönetilen iOS uygulaması olarak EMM için Slack ekleyin ve Slack kullanıcılarınızın atayın. Uygulamalar platforma özgü olduğundan, Android cihazlarda Slack kullanıcılarınız için ayrı bir Intune uygulama eklemeniz gerekir.
1. Intune'da seçin **istemci uygulamaları** > **uygulamaları** > **Ekle**.
2. Uygulama türü'nün altında seçin **Store uygulaması - iOS**.
3. **App Store’da Ara**’yı seçin. "Slack için EMM" arama terimini girin ve uygulamayı seçin.
4. Seçin **uygulama bilgileri** ve herhangi bir değişiklik gördüğünüz şekilde yapılandırın.
5. **Add (Ekle)** seçeneğini belirleyin.
6. Arama çubuğuna "Slack için EMM" girin ve yeni eklediğiniz uygulamayı seçin.
7. Yönet'seçin **atamaları**.
8. Seçin **Grup Ekle**. Bağlı olarak, Slack için EMM altında açık olduğunda etkilenecek olan, seçtiğiniz **atama türü** seçmek isteyebilirsiniz:
    - **Kayıtlı cihazlar için kullanılabilir** "tüm üyeleri (Konukları dahil)" seçerseniz veya
    - **Kayıtlı veya Kayıtsız kullanılabilir** "tüm üyeleri (Konukları hariç)" seçerseniz veya "İsteğe bağlı".
9. Seçin **bulunan gruplarını** ve bu uygulamayı tüm kullanıcılar tarafından kullanılabilir yap altında seçin **Evet**.
10. Tıklayın **Tamam**ve ardından **Tamam** yeniden.
11. **Kaydet**’e tıklayın.

### <a name="add-an-app-configuration-policy-for-slack-for-emm"></a>Bir uygulama yapılandırma ilkesi için Slack için EMM ekleyin.
Slack EMM iOS için uygulama yapılandırma ilkesi ekleyin. Yönetilen cihazlar için uygulama yapılandırma ilkeleri platforma özgü olduğundan, Android cihazlarda Slack kullanıcılarınız için ayrı bir ilke eklemeniz gerekir.
1. Intune'da seçin **istemci uygulamaları** > **uygulama yapılandırma ilkeleri** > **Ekle**.
2. Slack uygulama yapılandırma İlkesi test adı girin.
3. Cihaz kayıt türü altında seçin **yönetilen cihazlar**.
4. Platform altında seçin **iOS**.
5. Seçin **ilişkili uygulama**.
6. Arama çubuğuna "Slack için EMM" girin ve uygulamayı seçin.
7. Tıklayın **Tamam**ve ardından **yapılandırma ayarlarını**. 
    - Yapılandırma anahtarları ve değerleri hakkında daha fazla bilgi için "Teknik" sekmesinde belgelerine [Slack'ın AppConfig web sayfası](https://www.appconfig.org/company/slack/).
8. Seçin **Tamam**ve ardından **Ekle**.
9. Arama çubuğuna "Slack uygulama yapılandırma İlkesi test" girin ve yeni eklediğiniz ilkeyi seçin.
10. Yönet'seçin **atamaları**.
11. Seçmek için ata altında **tüm kullanıcılar + tüm cihazlar**.
12. **Kaydet**’e tıklayın.

### <a name="optional-create-an-ios-device-compliance-policy"></a>(İsteğe bağlı) İOS cihaz uyumluluk ilkesi oluşturma
Bir cihazın uyumlu sayılması için karşılaması gereken şartları ayarlamak için bir Intune cihaz uyumluluk ilkesi ayarlayın. Bu öğreticide iOS cihazlar için bir cihaz uyumluluk ilkesi oluşturacağız. Uyumluluk ilkeleri platforma özgü olduğundan, Android cihazlarda Slack kullanıcılarınız için ayrı bir ilke oluşturmanız gerekir.
1. Intune’da **Cihaz uyumluluğu** > **İlkeler** > **İlke Oluştur**’u seçin.
2. "İOS uyumluluk İlkesi test" adı girin.
3. "İOS uyumluluk İlkesi test" açıklama girin.
4. Platform altında seçin **iOS**.
5. **Cihaz Durumu**’nı seçin. Jailbreak uygulanmış cihazlar'ın yanındaki seçin **blok**ve ardından **Tamam**.
6. Seçin **sistem güvenliği** ve parola ayarlarını girin. Bu öğretici için aşağıdaki önerilen ayarları seçin:
    - Mobil cihazların kilidini açmak için parola iste için **gerektiren**.
    - Basit parolalar için seçmek **blok**.
    - Minimum parola uzunluğu için 4 girin.
    - Gerekli parola türü seçin **alfasayısal**.
    - En fazla dakika ekran kilitlendikten sonra parola istenmeden önce seçin **hemen**.
    - İçin parola süresinin sonu (gün) 41 girin.
    - Önlemek için Önceki parolalardan kaç tanesinin yeniden, 5'i girin.
7. Tıklayın **Tamam**ve ardından **Tamam** yeniden.
8. **Oluştur**’a tıklayın.

## <a name="set-up-slack-on-android-work-profile-devices"></a>Android iş profili cihazları üzerinde Slack ayarlayın
Slack yönetilen Google Play uygulaması, Intune kiracınıza ekleyin ve Slack EMM sağlayıcısı olarak Intune ile erişmek Android kullanıcıları, kuruluşların etkinleştirmek için bir uygulama yapılandırma ilkesi oluşturun.

### <a name="add-slack-to-intune"></a>Slack Intune'a ekleme
Google yönetilen uygulamayı Intune'a yürütün ve Slack kullanıcılarınıza atama Slack ekleyin. Uygulamalar platforma özgü olduğundan, ayrı bir Intune uygulama Slack kullanıcılarınız için iOS cihazlarında eklemeniz gerekir.
1. Intune'da seçin **istemci uygulamaları** > **uygulamaları** > **Ekle**.
2. Uygulama türü'nün altında seçin **yönetilen Google Play Store uygulaması –** .
3. Seçin **yönetilen Google Play - onaylama**. "Slack için EMM" arama terimini girin ve uygulamayı seçin.
4. Seçin **onaylama**.
5. Arama çubuğuna "Slack" girin ve yeni eklediğiniz uygulamayı seçin.
6. Yönet'seçin **atamaları**.
7. Seçin **Grup Ekle**. Bağlı olarak, Slack için EMM altında açık olduğunda etkilenecek olan, seçtiğiniz **atama türü** seçmek isteyebilirsiniz:
    - **Kayıtlı cihazlar için kullanılabilir** "tüm üyeleri (Konukları dahil)" seçerseniz veya
    - **Kayıtlı veya Kayıtsız kullanılabilir** "tüm üyeleri (Konukları hariç)" seçerseniz veya "İsteğe bağlı".
8. Bulunan gruplarını seçin ve altında kullanılabilir hale getirir bu uygulamayı tüm kullanıcılar seçmek amacıyla **Evet**.
9. Tıklayın **Tamam**ve ardından **Tamam** yeniden.
10. **Kaydet**’e tıklayın.

### <a name="add-an-app-configuration-policy-for-slack"></a>Slack için uygulama yapılandırma İlkesi Ekle
Bir uygulama yapılandırma ilkesi için Slack ekleyin. Yönetilen cihazlar için uygulama yapılandırma ilkeleri platforma özgü olduğundan, iOS cihazlarında Slack kullanıcılarınız için ayrı bir ilke eklemeniz gerekir.
1. Intune'da seçin **istemci uygulamaları** > **uygulama yapılandırma ilkeleri** > **Ekle**.
2. Slack uygulama yapılandırma İlkesi test adı girin.
3. Cihaz kayıt türü altında seçin **yönetilen cihazlar**.
4. Platform altında seçin **Android**.
5. Seçin **ilişkili uygulama**.
6. Arama çubuğuna "Slack" girin ve uygulamayı seçin.
7. Seçin **Tamam**ve ardından **yapılandırma ayarlarını**.
    - Yapılandırma anahtarları ve değerleri hakkında daha fazla bilgi için "Teknik" sekmesinde belgelerine [Slack'ın AppConfig web sayfası](https://www.appconfig.org/company/slack/).
8. Tıklayın **Tamam**ve ardından **Ekle**.
9. Arama çubuğuna "Slack uygulama yapılandırma İlkesi test" girin ve yeni eklediğiniz ilkeyi seçin.
10. Yönet'seçin **atamaları**.
11. Seçmek için ata altında **tüm kullanıcılar + tüm cihazlar**.
12. **Kaydet**’e tıklayın.

### <a name="optional-create-an-android-device-compliance-policy"></a>(İsteğe bağlı) Bir Android cihaz uyumluluk ilkesi oluşturma
Bir cihazın uyumlu sayılması için karşılaması gereken şartları ayarlamak için bir Intune cihaz uyumluluk ilkesi ayarlayın. Bu öğreticide, Android cihazları için cihaz uyumluluk İlkesi oluşturacağız. Uyumluluk ilkeleri platforma özgü olduğundan, iOS cihazlarında Slack kullanıcılarınız için ayrı bir ilke oluşturmanız gerekir.
1. Intune’da **Cihaz uyumluluğu** > **İlkeler** > **İlke Oluştur**’u seçin.
2. "Android uyumluluk İlkesi test" adı girin.
3. "Android uyumluluk İlkesi test" açıklama girin.
4. Platform altında seçin **Android Kurumsal**.
5. Profil Türü altında seçin **iş profilindeki**.
6. **Cihaz Durumu**’nı seçin. Kök erişim izni verilmiş cihazlar yanındaki seçin **blok**ve ardından **Tamam**.
7. Seçin **sistem güvenliği** girin **parola ayarları**. Bu öğretici için aşağıdaki önerilen ayarları seçin:
    - Mobil cihazların kilidini açmak için parola iste için **gerektiren**.
    - Gerekli parola türü için **en az alfasayısal**.
    - Minimum parola uzunluğu için 4 girin.
    - En fazla dakika ekran kilitlendikten sonra parola istenmeden önce seçin **15 dakika**.
    - İçin parola süresinin sonu (gün) 41 girin.
    - Önlemek için Önceki parolalardan kaç tanesinin yeniden, 5'i girin.
8. Tıklayın **Tamam**ve ardından **Tamam** yeniden.
9. **Oluştur**’a tıklayın.

## <a name="launch-slack"></a>Slack başlatın

Yeni oluşturduğunuz, ilkeleriyle herhangi bir iOS veya Android alanlarınızdan birinde oturum açmayı denerseniz iş profili cihazları Intune'a kayıtlı olması gerekir. Bu senaryoyu sınamak için bir iOS cihazı Intune'a kayıtlı veya Intune'a kayıtlı Android iş profili cihazında başlatan Slack EMM için Slack başlatma'yı deneyin. 

## <a name="next-steps"></a>Sonraki adımlar

Bu öğreticide:
- Enterprise Mobility Management (EMM) sağlayıcısı olarak Intune Slack Kurumsal Kılavuzunuzun üzerinde ayarlayın. 
- Uygulama yapılandırma ilkeleri EMM uygulaması iOS ve Android iş profili cihazları için Slack uygulaması için Slack yönetmek için oluşturduğunuz.
- Intune cihaz uyumluluk ilkeleri Android koşullar ayarlamak için oluşturduğunuz ve iOS cihazlarının uyumlu olarak değerlendirilmesi için uyması gerekir.

Uygulama yapılandırma ilkeleri hakkında daha fazla bilgi için bkz: [Intune için uygulama yapılandırma ilkeleri](app-configuration-policies-overview.md). Cihaz uyumluluk ilkeleri hakkında daha fazla bilgi için bkz: [cihazlarda Intune kullanarak kuruluşunuzda kaynaklara erişim izni vermek için kuralları ayarlama](device-compliance-get-started.md).