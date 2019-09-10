---
title: Öğretici-EMM ve uygulama yapılandırması için Intune 'U kullanmak üzere bolluk yapılandırma
titleSuffix: Microsoft Intune
description: Bu öğreticide, EMM ve uygulama yapılandırması için bir bolluk 'yi Intune kullanacak şekilde yapılandıracaksınız.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/09/2019
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
ms.openlocfilehash: 97bc1658dcd432bdd5e31c7100022959e96c3039
ms.sourcegitcommit: a25cd79a33feb536d9b2fc11aa7d3e3972f1ca5a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/09/2019
ms.locfileid: "70842070"
---
# <a name="tutorial-configure-slack-to-use-intune-for-emm-and-app-configuration"></a>Öğreticide EMM 'yi EMM ve uygulama yapılandırması için Intune kullanacak şekilde yapılandırma

Bolluk, Microsoft Intune kullanabileceğiniz bir işbirliği uygulamasıdır.   

Bu öğreticide şunları yapacaksınız:
> [!div class="checklist"]
> - Intune 'U, bolluk kurumsal kılavuzunuzda Enterprise Mobility Management (EMM) sağlayıcısı olarak ayarlayın. Kılavuza ait çalışma alanlarınıza erişimi Intune tarafından yönetilen cihazlara sınırlayabilirsiniz.
> - İOS 'ta EMM için bolluk uygulamasını ve Android iş profili cihazları için bolluk uygulamasını yönetmek üzere uygulama yapılandırma ilkeleri oluşturun.
> - Android ve iOS cihazlarının uyumlu kabul edilmesi için uyması gereken koşulları ayarlamak için Intune cihaz uyumluluk ilkeleri oluşturun.

Bir Intune aboneliğiniz yoksa [ücretsiz bir deneme hesabı için kaydolun](free-trial-sign-up.md).

## <a name="prerequisites"></a>Önkoşullar
Bu öğretici için aşağıdaki abonelik sahip bir test kiracısına ihtiyacınız olacak:
- Azure Active Directory Premium ([ücretsiz deneme](https://azure.microsoft.com/free/?WT.mc_id=A261C142F))
- Intune aboneliği ([ücretsiz deneme](free-trial-sign-up.md))

Ayrıca, bir [bolluk kurumsal kılavuz](https://get.slack.help/hc/articles/360004150931-What-is-Slack-Enterprise-Grid-) planına de ihtiyacınız vardır.

## <a name="configure-your-slack-enterprise-grid-plan"></a>Bolluk kurumsal kılavuz planınızı yapılandırın
[Bolluk yönergelerini](https://get.slack.help/hc/articles/115002579426-Enable-Enterprise-Mobility-Management-for-your-org#step-2:-turn-on-emm) Izleyerek bolluk kurumsal kılavuz PLANıNıZ için EMM 'yi açın ve kılavuz planınızın kimlik sağlayıcısı (IDP) olarak [Azure Active Directory bağlayın](https://docs.microsoft.com/azure/active-directory/saas-apps/slack-tutorial) .

## <a name="sign-in-to-intune"></a>Intune'da oturum açma
[Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da Genel Yönetici veya Intune Hizmet Yöneticisi olarak oturum açın. Intune Deneme aboneliği oluşturduysanız aboneliği oluşturduğunuz hesap Genel yönetici rolüne sahip olur.

## <a name="set-up-slack-for-emm-on-ios-devices"></a>İOS cihazlarında EMM için bolluk ayarlama
Kuruluşunuzun iOS kullanıcılarının bir EMM sağlayıcısı olarak Intune ile bolluk 'e erişmesini sağlamak için, bir uygulama yapılandırma ilkesi oluşturmak üzere EMM için iOS uygulama bolluğu ' ni ekleyin.

### <a name="add-slack-for-emm-to-intune"></a>Intune 'a EMM için bolluk ekleme
EMM için, Intune 'da yönetilen bir iOS uygulaması olarak bolluk ekleyin ve bolluk kullanıcılarınızı atayın. Uygulamalar platforma özgüdür, bu nedenle Android cihazlarda bolluk kullanıcılarınız için ayrı bir Intune uygulaması eklemeniz gerekir.
1. Intune 'da, **istemci uygulamaları** > **uygulamalar** > **Ekle**' yi seçin.
2. Uygulama türü altında **mağaza app-iOS**' ı seçin.
3. **App Store’da Ara**’yı seçin. "EMM için bolluk" arama terimini girin ve uygulamayı seçin.
4. **Uygulama bilgileri** ' ni seçin ve tüm değişiklikleri uygun gördüğünüz şekilde yapılandırın.
5. **Add (Ekle)** seçeneğini belirleyin.
6. Arama çubuğuna "EMM için bolluk" yazın ve yeni eklediğiniz uygulamayı seçin.
7. Yönet ' den **atamalar**' ı seçin.
8. **Grup Ekle**' yi seçin. Bolluk için EMM 'i açtığınızda kimin etkilenmesini seçtiğinize bağlı olarak, **atama türü** altında şunları seçebilirsiniz:
    - "Tüm Üyeler (konuklar dahil)" seçeneğini belirlediyseniz **Kayıtlı cihazlar Için kullanılabilir** "veya
    - "Tüm Üyeler (konukları hariç)" veya "Isteğe bağlı" seçeneğini belirlediyseniz **kayıt olmadan veya bunlarla birlikte kullanılabilir** .
9. **Dahil edilen grupları** seçin ve bu uygulamayı tüm kullanıcılar Için kullanılabilir yap altında **Evet**' i seçin.
10. **Tamam**' a ve ardından yeniden **Tamam** ' a tıklayın.
11. **Kaydet**’e tıklayın.

### <a name="add-an-app-configuration-policy-for-slack-for-emm"></a>EMM için bolluk için bir uygulama yapılandırma ilkesi ekleyin
EMM iOS için bolluk için bir uygulama yapılandırma ilkesi ekleyin. Yönetilen cihazlar için uygulama yapılandırma ilkeleri platforma özgüdür. bu nedenle, Android cihazlarda bolluk kullanıcılarınıza ayrı bir ilke eklemeniz gerekir.
1. Intune 'da, **istemci uygulamaları** > **uygulama yapılandırma ilkeleri** > **Ekle**' yi seçin.
2. Ad alanına bolluk uygulama yapılandırma ilkesi testi girin.
3. Cihaz kayıt türü ' nün altında, **yönetilen cihazlar**' ı seçin.
4. Platform altında **iOS**' u seçin.
5. **İlişkili uygulama**' yı seçin.
6. Arama çubuğuna "EMM için bolluk" yazın ve uygulamayı seçin.
7. **Tamam**' a tıklayın ve ardından **yapılandırma ayarları**' nı seçin. 
    - Yapılandırma anahtarları ve değerleri hakkında daha fazla bilgi için, [bolluk 'In AppConfig Web sayfasının](https://www.appconfig.org/company/slack/)"Teknik" sekmesindeki belgelere başvurun.
8. **Tamam**' ı ve ardından **Ekle**' yi seçin.
9. Arama çubuğuna "bolluk uygulama yapılandırma ilkesi sınaması" yazın ve yeni eklediğiniz ilkeyi seçin.
10. Yönet ' den **atamalar**' ı seçin.
11. Ata ' nın altında, **tüm kullanıcılar + tüm cihazlar**' ı seçin.
12. **Kaydet**’e tıklayın.

### <a name="optional-create-an-ios-device-compliance-policy"></a>Seçim İOS cihaz uyumluluk ilkesi oluşturma
Bir cihazın uyumlu sayılması için karşılaması gereken şartları ayarlamak için bir Intune cihaz uyumluluk ilkesi ayarlayın. Bu öğreticide iOS cihazlar için bir cihaz uyumluluk ilkesi oluşturacağız. Uyumluluk ilkeleri platforma özgüdür, bu nedenle Android cihazlarda bolluk kullanıcılarınız için ayrı bir ilke oluşturmanız gerekir.
1. Intune’da **Cihaz uyumluluğu** > **İlkeler** > **İlke Oluştur**’u seçin.
2. Ad alanına "iOS uyumluluk ilkesi sınaması" yazın.
3. Açıklama ' da "iOS uyumluluk ilkesi sınaması" yazın.
4. Platform altında **iOS**' u seçin.
5. **Cihaz Durumu**’nı seçin. Jailbreak uygulanmış cihazlar ' ın yanındaki **Engelle**' yi seçin ve ardından **Tamam**' ı seçin.
6. **Sistem güvenliği** ' ni seçin ve parola ayarlarını girin. Bu öğretici için aşağıdaki önerilen ayarları seçin:
    - Mobil cihazların kilidini açmak için parola gerektir için **gerektir**' i seçin.
    - Basit parolalar için **Engelle**' yi seçin.
    - Minimum parola uzunluğu için 4 girin.
    - Gerekli parola türü için **alfasayısal**' i seçin.
    - Parola istenmeden önce ekran kilitlenmesinden sonra geçen en uzun dakika için **hemen**öğesini seçin.
    - Parola kullanım süresi (gün) için 41 girin.
    - Yeniden kullanılmasını önleyen önceki parolaların sayısı için 5 girin.
7. **Tamam**' a tıklayın ve ardından yeniden **Tamam** ' ı seçin.
8. **Oluştur**'a tıklayın.

## <a name="set-up-slack-on-android-work-profile-devices"></a>Android iş profili cihazlarında bolluk ayarlama
, Kuruluşların Android kullanıcılarına bir EMM sağlayıcısı olarak Intune ile bolluk erişimi sağlamak için Google Play, bir uygulama yapılandırma ilkesi oluşturun ve bu uygulamaları Intune kiracınıza ekleyin.

### <a name="add-slack-to-intune"></a>Intune 'a bolluk ekleme
Intune 'da bir yönetilen Google Play uygulaması olarak bolluk ekleyin ve bolluk kullanıcılarınızı atayın. Uygulamalar platforma özgüdür, bu nedenle iOS cihazlarında bolluk kullanıcılarınız için ayrı bir Intune uygulaması eklemeniz gerekir.
1. Intune 'da, **istemci uygulamaları** > **uygulamalar** > **Ekle**' yi seçin.
2. Uygulama türü altında **Mağaza uygulaması – yönetilen Google Play**seçin.
3. **Yönetilen Google Play-Onayla**' yı seçin. "EMM için bolluk" arama terimini girin ve uygulamayı seçin.
4. **Onayla**seçeneğini belirleyin.
5. Arama çubuğuna "bolluk" yazın ve yeni eklediğiniz uygulamayı seçin.
6. Yönet ' den **atamalar**' ı seçin.
7. **Grup Ekle**' yi seçin. Bolluk için EMM 'i açtığınızda kimin etkilenmesini seçtiğinize bağlı olarak, **atama türü** altında şunları seçebilirsiniz:
    - "Tüm Üyeler (konuklar dahil)" seçeneğini belirlediyseniz **Kayıtlı cihazlar Için kullanılabilir** "veya
    - "Tüm Üyeler (konukları hariç)" veya "Isteğe bağlı" seçeneğini belirlediyseniz **kayıt olmadan veya bunlarla birlikte kullanılabilir** .
8. Dahil edilen grupları seçin ve bu uygulamayı tüm kullanıcılar için kullanılabilir yap altında **Evet**' i seçin.
9. **Tamam**' a ve ardından yeniden **Tamam** ' a tıklayın.
10. **Kaydet**’e tıklayın.

### <a name="add-an-app-configuration-policy-for-slack"></a>Bolluk için bir uygulama yapılandırma ilkesi ekleyin
Bolluk için bir uygulama yapılandırma ilkesi ekleyin. Yönetilen cihazlar için uygulama yapılandırma ilkeleri platforma özgüdür, bu nedenle iOS cihazlarında bolluk kullanıcılarınıza ayrı bir ilke eklemeniz gerekir.
1. Intune 'da, **istemci uygulamaları** > **uygulama yapılandırma ilkeleri** > **Ekle**' yi seçin.
2. Ad alanına bolluk uygulama yapılandırma ilkesi testi girin.
3. Cihaz kayıt türü ' nün altında, **yönetilen cihazlar**' ı seçin.
4. Platform altında **Android**' i seçin.
5. **İlişkili uygulama**' yı seçin.
6. Arama çubuğuna "bolluk" yazın ve uygulamayı seçin.
7. **Tamam**' ı ve ardından **yapılandırma ayarları**' nı seçin.
    - Yapılandırma anahtarları ve değerleri hakkında daha fazla bilgi için, [bolluk 'In AppConfig Web sayfasının](https://www.appconfig.org/company/slack/)"Teknik" sekmesindeki belgelere başvurun.
8. **Tamam**' a ve ardından **Ekle**' yi seçin.
9. Arama çubuğuna "bolluk uygulama yapılandırma ilkesi sınaması" yazın ve yeni eklediğiniz ilkeyi seçin.
10. Yönet ' den **atamalar**' ı seçin.
11. Ata ' nın altında, **tüm kullanıcılar + tüm cihazlar**' ı seçin.
12. **Kaydet**’e tıklayın.

### <a name="optional-create-an-android-device-compliance-policy"></a>Seçim Android cihaz uyumluluk ilkesi oluşturma
Bir cihazın uyumlu sayılması için karşılaması gereken şartları ayarlamak için bir Intune cihaz uyumluluk ilkesi ayarlayın. Bu öğreticide, Android cihazlar için bir cihaz uyumluluk ilkesi oluşturacağız. Uyumluluk ilkeleri platforma özgüdür, bu nedenle iOS cihazlarında bolluk kullanıcılarınız için ayrı bir ilke oluşturmanız gerekir.
1. Intune’da **Cihaz uyumluluğu** > **İlkeler** > **İlke Oluştur**’u seçin.
2. Ad alanına "Android uyumluluk ilkesi sınaması" yazın.
3. Açıklama ' da "Android uyumluluk ilkesi sınaması" yazın.
4. Platform altında **Android kurumsal**' i seçin.
5. Profil türü altında **iş profili**' ni seçin.
6. **Cihaz Durumu**’nı seçin. Kökü belirtilmiş cihazlar ' ın yanındaki **Engelle**' yi seçin ve ardından **Tamam**' ı seçin.
7. **Sistem güvenliği** ' ni seçin ve **parola ayarlarını**girin. Bu öğretici için aşağıdaki önerilen ayarları seçin:
    - Mobil cihazların kilidini açmak için parola gerektir için **gerektir**' i seçin.
    - Gerekli parola türü için en **az alfasayısal**' i seçin.
    - Minimum parola uzunluğu için 4 girin.
    - Parola istenmeden önce ekran kilitlenmesinden sonra geçen en uzun dakika için **15 dakika**seçin.
    - Parola kullanım süresi (gün) için 41 girin.
    - Yeniden kullanılmasını önleyen önceki parolaların sayısı için 5 girin.
8. **Tamam**' a ve ardından yeniden **Tamam** ' a tıklayın.
9. **Oluştur**'a tıklayın.

## <a name="launch-slack"></a>Başlatma bolluğu

Az önce oluşturduğunuz ilkeler sayesinde, çalışma alanlarınızdan birinde oturum açmaya çalışan tüm iOS veya Android iş profili cihazları Intune 'a kaydolmaları gerekir. Bu senaryoyu test etmek için, Intune 'a kayıtlı bir iOS cihazında EMM için bolluk başlatmayı veya Intune 'A kayıtlı bir Android iş profili cihazında bolluk başlatmayı deneyin. 

## <a name="next-steps"></a>Sonraki adımlar

Bu öğreticide:
- Intune 'U, bolluk kurumsal kılavuzunuzda Enterprise Mobility Management (EMM) sağlayıcısı olarak ayarlarsınız. 
- İOS 'ta EMM için bolluk uygulamasını ve Android iş profili cihazları için bolluk uygulamasını yönetmek üzere uygulama yapılandırma ilkeleri oluşturdunuz.
- Android ve iOS cihazlarının uyumlu kabul edilmesi için uyması gereken koşulları ayarlamak için Intune cihaz uyumluluk ilkelerini oluşturdunuz.

Uygulama yapılandırma ilkeleri hakkında daha fazla bilgi için bkz. [Microsoft Intune Için uygulama yapılandırma ilkeleri](app-configuration-policies-overview.md). Cihaz uyumluluk ilkeleri hakkında daha fazla bilgi edinmek için bkz. [Intune kullanarak kuruluşunuzdaki kaynaklara erişime izin vermek için cihazlarda kuralları ayarlama](device-compliance-get-started.md).