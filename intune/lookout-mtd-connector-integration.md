---
title: "Microsoft Intune ile Lookout tümleştirmenizi ayarlama"
titlesuffix: 
description: "Şirket kaynaklarınıza mobil cihaz erişimini kontrol etmek için Lookout Mobile Threat Defense’i Intune ile tümleştirme hakkında bilgi edinin."
keywords: 
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5b0d7644-3183-45ba-a165-0d82d70cb71e
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7ffd55a82af4f7fdc8d8df7cab818c59def74109
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2018
---
# <a name="set-up-your-lookout-mobile-threat-defense-integration-with-intune"></a>Intune ile Lookout Mobile Threat Defense tümleştirmenizi ayarlama

Lookout Mobile Threat Defence aboneliğini ayarlamak için gerekli adımlar aşağıdadır:

| #        |Adım  |
| ------------- |:-------------|
| 1 | [Azure AD bilgileri toplama](#collect-azure-ad-information) |
| 2 | [Aboneliğinizi yapılandırma](#configure-your-subscription) |
| 3 | [Kayıt gruplarını yapılandırma](#configure-enrollment-groups) |
| 4 | [Durum eşitlemeyi yapılandırma](#configure-state-sync) |
| 5 | [Hata raporu e-posta alıcı bilgilerini yapılandırma](#configure-error-report-email-recipient-information) |
| 6 | [Kayıt ayarlarını yapılandırma](#configure-enrollment-settings) |
| 7 | [E-posta bildirimlerini yapılandırma](#configure-email-notifications) |
| 8 | [Tehdit sınıflandırmasını yapılandırma](#configure-threat-classification) |
| 9 | [Kayıt izleme](#watching-enrollment) |

> [!IMPORTANT]
> Daha önceden Azure AD kiracınız ile ilişkilendirilmemiş mevcut bir Lookout Mobil Uç Nokta Güvenliği kiracısı, Azure AD ve Intune tümleştirmesi için kullanılamaz. Yeni bir Lookout Mobil Uç Nokta Güvenliği kiracısı oluşturmak için Lookout desteğine başvurun. Azure AD kullanıcılarınızı eklemek için yeni kiracıyı kullanın.

## <a name="collect-azure-ad-information"></a>Azure AD bilgileri toplama
Lookout Mobil Uç Nokta Güvenliği kiracınız, Lookout hizmetini Intune ile etkinleştirmek için Azure AD aboneliğiniz ile ilişkilendirilir. Lookout Mobile Threat Defense hizmeti aboneliğinizi etkinleştirmek için Lookout desteği (enterprisesupport@lookout.com) aşağıdaki bilgilere gerek duyar:

* **Azure AD Kiracı Kimliği**
* Lookout konsoluna **tam** erişim için **Azure AD Grubu Nesne Kimliği**
* Lookout konsoluna **kısıtlı** erişim için **Azure AD Grubu Nesne Kimliği** (isteğe bağlı)

Lookout destek ekibine vermeniz gereken bilgileri elde etmek için aşağıdaki adımları kullanın.

1. [Azure portalı](https://portal.azure.com)'nda oturum açın ve aboneliğinizi seçin. 

2. Aboneliğinizin adını seçtiğinizde sağlanan URL abonelik kimliğini içerir.  Abonelik kimliğinizi bulma konusunda herhangi bir sorun yaşarsanız, abonelik kimliğinizi bulma konusundaki ipuçları için bu [Microsoft destek makalesine](https://support.office.com/article/Find-your-Office-365-tenant-ID-6891b561-a52d-4ade-9f39-b492285e2c9b) bakın.

3. Azure AD Grup Kimliğinizi bulun. Lookout konsolu 2 erişim düzeyini destekler:  
  * **Tam Erişim:** Azure AD yöneticisi, Tam Erişimi olan kullanıcılar için bir grup oluşturabilir ve isteğe bağlı olarak Sınırlı Erişimi olacak kullanıcılar için bir grup oluşturur.  Yalnızca bu gruplardaki kullanıcılar **Lookout konsolunda** oturum açabilir.
  * **Kısıtlı Erişim:** Bu gruptaki kullanıcılar, Lookout konsolundaki yapılandırma ve kayıtla ilgili modüllerin çoğuna erişemez. Konsolun **Güvenlik İlkesi** modülü için ise salt okunur erişimine sahip olurlar.  

    > [!TIP] 
    > İzinler hakkında daha fazla ayrıntı için Lookout Web sitesindeki [bu makaleyi](https://personal.support.lookout.com/hc/articles/114094105653) okuyun.

    > [!NOTE] 
    > **Grup Nesne Kimliği**, **Azure AD yönetim portalında** grubun **Özellikler** sayfasında bulunur.

4. Bu bilgileri topladıktan sonra, Lookout desteği ile iletişime geçin (e-posta: enterprisesupport@lookout.com). Lookout Desteği topladığınız bilgileri kullanarak, aboneliğinizi hazırlamak ve Lookout Enterprise hesabınızı oluşturmak için aboneliğinizdeki birincil ilgili kişiyle birlikte çalışır.

## <a name="configure-your-subscription"></a>Aboneliğinizi yapılandırma

1. Lookout desteği Lookout Enterprise hesabınızı oluşturduktan sonra, oturum açma URL’sini içeren bir e-posta Lookout’tan şirketinizdeki birincil ilgili kişiye gönderilir: https://aad.lookout.com/les?action=consent.

2.  Azure AD kiracınızı kaydetmek için Lookout konsolunda ilk kez oturum açma işleminin Azure AD rolü Genel Yönetici olan bir kullanıcı hesabı kullanılarak yapılması gerekir. Daha sonra, oturum açma işleminin bu Azure AD ayrıcalık düzeyinde yapılmasına gerek yoktur. Bir onay sayfası görüntülenir. Kaydı tamamlamak için **Kabul Et**’i seçin. Kabul edip onay verdikten sonra Lookout Konsolu'na yönlendirilirsiniz.

    ![Lookout konsolunda ilk defa oturum açma sayfasının ekran görüntüsü](./media/lookout_mtp_initial_login.png)
    > [!NOTE] 
    > Oturum açma sorunları ile ilgili yardım için bkz. [Lookout tümleştirme sorunlarını giderme](https://docs.microsoft.com/intune/troubleshoot/troubleshooting-lookout-integration).

3.  [Lookout Konsolu](https://aad.lookout.com)’nda, **Sistem** modülünde, **Bağlayıcılar** sekmesine tıklayın ve **Intune**’u seçin.

    ![Lookout MTP konsolunu bağlayıcılar sekmesi açık ve Intune seçeneği vurgulanmış olarak gösteren ekran görüntüsü](./media/lookout_mtp_setup-intune-connector.png)

4.  **Bağlayıcılar** > **Bağlantı Ayarları**’na gidin ve **Sinyal Sıklığı**’nı dakika cinsinden belirtin.

    ![bağlantı ayarları sekmesinin sinyal sıklığını gösterecek şekilde yapılandırılmış ekran görüntüsü](./media/lookout-mtp-connection-settings.png)

## <a name="configure-enrollment-groups"></a>Kayıt gruplarını yapılandırma
1. En iyi uygulama olarak, Lookout tümleştirmesini sınamak için [Azure AD yönetim portalında](https://manage.windowsazure.com) az sayıda kullanıcı içeren bir Azure AD güvenlik grubu oluşturun.

    > [!NOTE] 
    > Azure AD’de bir kayıt grubundaki tanımlanan ve desteklenen, Lookout desteği bulunan ve Intune’a kayıtlı olan tüm kullanıcıların cihazları kaydedilir ve Lookout MTD konsolunda etkinleştirilme için uygundur.

2. [Lookout Konsolu](https://aad.lookout.com)’nda, **Sistem** modülünden **Bağlayıcılar** sekmesini seçin ve cihazları Lookout’a kaydedilmesi gereken kullanıcı gruplarını tanımlamak için **Kayıt Yönetimi**’ni seçin. Kayıt için Azure AD güvenlik grubunun **Görünen Adı**’nı ekleyin.

    ![Intune bağlayıcısı kayıt sayfasının ekran görüntüsü](./media/lookout-mtp-enrollment.png)

    >[!IMPORTANT]
    > **Görünen Ad**, Azure portalındaki güvenlik grubunun **Özellikler** sayfasında gösterildiği gibi büyük/küçük harfe duyarlıdır. Aşağıdaki resimde gösterildiği gibi, başlığı tamamen küçük harflerden oluşurken, güvenlik grubunun **Görünen Ad**’ı küçük ve büyük harflerin kombinasyonundan oluşur. Lookout konsolunda **Görünen Ad** harflerini güvenlik grubu için eşleştirin.
    >![Azure portalı, Azure Active Directory hizmeti, özellikler sayfasının ekran görüntüsü](./media/aad-group-display-name.png)

    >[!NOTE] 
    >Yeni cihazları denetleme aralığı olarak varsayılan değeri (5 dakika) kullanmak en iyi yöntemdir. Geçerli sınırlamalar; **Lookout grup görünen adlarını doğrulayamıyor:** Azure portalındaki **GÖRÜNEN AD** alanının Azure AD güvenlik grubu ile tam olarak eşleştiğinden emin olun. **İç içe grup oluşturma desteklenmiyor:** Lookout'taki Azure AD güvenlik grupları yalnızca kullanıcı içermelidir. Diğer grupları içeremezler.

3.  Bir grup eklendikten sonra, kullanıcı Lookout for Work uygulamasını desteklenen cihazında sonraki açışında cihaz Lookout’ta etkinleştirilir.

4.  Sonuçlar sizi memnun ettiğinde, kaydı ek kullanıcı gruplarına genişletin.

## <a name="configure-state-sync"></a>Durum eşitlemeyi yapılandırma
**Durum Eşitleme** seçeneğinde, Intune’a gönderilecek veri türünü belirtin.  Lookout Intune tümleştirmesinin düzgün çalışması için hem cihaz durumu hem de tehdit durumu gerekir. Bu ayarlar varsayılan olarak etkinleştirilir.

## <a name="configure-error-report-email-recipient-information"></a>Hata raporu e-posta alıcı bilgilerini yapılandırma
**Hata Yönetimi** seçeneğinde, hata raporlarının gönderileceği e-posta adresini girin.

![Intune bağlayıcısı hata yönetimi sayfasının ekran görüntüsü](./media/lookout-mtp-connector-error-notifications.png)

## <a name="configure-enrollment-settings"></a>Kayıt ayarlarını yapılandırma
**Sistem** modülünde, **Bağlayıcılar** sayfasında, bir cihazın bağlantısı kesilmiş olarak kabul edilmesinden önce geçmesi gereken gün sayısını belirtin.  Bağlantısı kesilmiş cihazlar uyumsuz olarak kabul edilir ve Intune koşullu erişim ilkelerine bağlı olarak şirket uygulamalarınıza erişimleri engellenir. 1 ila 90 gün arasında bir değer belirtebilirsiniz.

![Lookout kayıt ayarları](./media/lookout-console-enrollment-settings.png)

## <a name="configure-email-notifications"></a>E-posta bildirimlerini yapılandırma
Tehditler hakkında e-posta uyarıları almak istiyorsanız bildirimlerin gönderileceği kullanıcı hesabını kullanarak [Lookout konsolunda](https://aad.lookout.com) oturum açın. **Sistem** modülünün **Tercihler** sekmesinde tehdit düzeylerinin bildirimlerini seçin ve bunları **AÇIK** olarak ayarlayın. Yaptığınız değişiklikleri kaydedin.

![kullanıcı hesabının görüntülendiği tercihler sayfasının ekran görüntüsü](./media/lookout-mtp-email-notifications.png) Artık e-posta bildirimleri almak istemiyorsanız bildirimleri **KAPALI** olarak ayarlayın ve değişikliklerinizi kaydedin.

### <a name="configure-threat-classification"></a>Tehdit sınıflandırmasını yapılandırma
Lookout Mobile Threat Defense, çeşitli türlerdeki mobil tehditleri sınıflandırır. [Lookout tehdit sınıflandırmaları](http://personal.support.lookout.com/hc/articles/114094130693) ile ilişkilendirilen varsayılan risk düzeyleri bulunur. Bunlar, şirket gereksinimlerinize uyacak şekilde herhangi bir zamanda değiştirilebilir.

![tehdit ve sınıflandırmaları gösteren ilke sayfasının ekran görüntüsü](./media/lookout-mtp-threat-classification.png)

>[!IMPORTANT]
> Intune tümleştirmesi, çalışma zamanında cihaz uyumluluğunu bu risk düzeylerine göre hesapladığından bunlar Mobile Threat Defense için önemlidir. Intune yöneticisi; bir cihazın **Yüksek**, **Orta** veya **Düşük** düzeyde etkin bir tehdidi varsa cihazı uyumsuz olarak tanımlamak için ilke içinde bir kural koyar. Lookout Mobile Threat Defense’deki tehdit sınıflandırma ilkesi, Intune’daki cihaz uyumluluk hesaplamasını doğrudan etkiler.

## <a name="watching-enrollment"></a>Kayıt izleme
Kurulum tamamlandıktan sonra, Lookout Mobile Threat Defense belirlenen kayıt gruplarına karşılık gelen cihazlar için Azure AD’yi yoklamaya başlar.  Kayıtlı cihazlar hakkındaki bilgileri Cihazlar modülünde bulabilirsiniz.  Cihazların ilk durumu, beklemede olarak gösterilir.  Cihaz durumu Lookout for Work uygulaması cihaza yüklendikten, açıldıktan ve etkinleştirildikten sonra değişir.  Cihaza gönderilen Lookout for Work uygulamasının nasıl alınacağına yönelik ayrıntılar için bkz. [Intune ile Lookout for Work uygulamaları ekleme](mtd-apps-ios-app-configuration-policy-add-assign.md).

## <a name="next-steps"></a>Sonraki adımlar

[Lookout uygulamalarını ayarlama](mtd-apps-ios-app-configuration-policy-add-assign.md)
