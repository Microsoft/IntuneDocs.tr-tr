---
title: "Lookout ile aboneliğinizi ayarlama | Microsoft Docs"
description: "Bu konu, Lookout cihaz tehdit korumasını nasıl yapılandıracağınıza yönelik ayrıntılar sunar."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8477a2f1-2e1d-4d42-8bcb-e1181cc900bb
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6b83d06ecbe6e202bf022444c288e0866b3507c6
ms.openlocfilehash: fc6a729ecd51adba2581c5b2ca4b3665970d4563


---

# <a name="set-up-your-subscription-for-lookout-device-threat-protection"></a>Aboneliğinizi Lookout cihaz tehdit koruması için ayarlama

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Lookout cihaz tehdit korumasını ayarlamak için aşağıdaki adımlar gerekir:

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
| 1 | [Kayıt izleme](#watching-enrollment) |


> [!IMPORTANT]
> Daha önceden Azure AD kiracınız ile ilişkilendirilmemiş mevcut bir Lookout Mobil Uç Nokta Güvenliği kiracısı, Azure AD ve Intune tümleştirmesi için kullanılamaz. Yeni bir Lookout Mobil Uç Nokta Güvenliği kiracısı oluşturmak için Lookout desteğine başvurun. Azure AD kullanıcılarınızı eklemek için yeni kiracıyı kullanın.

## <a name="collect-azure-ad-information"></a>Azure AD bilgileri toplama
Lookout Mobil Uç Nokta Güvenliği kiracınız, Lookout hizmetini Intune ile etkinleştirmek için Azure AD aboneliğiniz ile ilişkilendirilir. Lookout cihaz tehdit koruma hizmeti aboneliğinizi etkinleştirmek için Lookout desteği (enterprisesupport@lookout.com) aşağıdaki bilgilere gerek duyar:  

* **Azure AD Kiracı Kimliği**
* Lookout konsoluna **tam** erişim için **Azure AD Grubu Nesne Kimliği**
* Lookout konsoluna **kısıtlı** erişim için **Azure AD Grubu Nesne Kimliği** (isteğe bağlı)

Lookout destek ekibine vermeniz gereken bilgileri elde etmek için aşağıdaki adımları kullanın.  

1. [Azure AD yönetim portalında](https://manage.windowsazure.com) oturum açın ve aboneliğinizi seçin. 
  ![Kiracı adını gösteren Azure AD sayfasının ekran görüntüsü](../media/mtp/aad_tenant_name.png)
2. Aboneliğinizin adını seçtiğinizde sağlanan URL abonelik kimliğini içerir.  Abonelik kimliğinizi bulma konusunda herhangi bir sorun yaşarsanız, abonelik kimliğinizi bulma konusundaki ipuçları için bu [Microsoft destek makalesine](https://support.office.com/en-us/article/Find-your-Office-365-tenant-ID-6891b561-a52d-4ade-9f39-b492285e2c9b?ui=en-US&rs=en-US&ad=US) bakın.   
3. Azure AD Grup Kimliğinizi bulun. Lookout konsolu 2 erişim düzeyini destekler:  
  * **Tam Erişim:** Azure AD yöneticisi, Tam Erişimi olacak kullanıcılar için bir grup oluşturabilir ve isteğe bağlı olarak Sınırlı Erişimi olacak kullanıcılar için bir grup oluşturur.  Yalnızca bu gruplardaki kullanıcılar **Lookout konsolunda** oturum açabilir.
  * **Kısıtlı Erişim:** Bu gruptaki kullanıcılar, Lookout konsolundaki yapılandırma ve kayıtla ilgili modüllerin çoğuna erişemez. Konsolun **Güvenlik İlkesi** modülü için ise salt okunur erişimine sahip olurlar.  

  İzinler hakkında daha fazla ayrıntı için Lookout Web sitesindeki [bu makaleyi](https://personal.support.lookout.com/hc/en-us/articles/114094105653) okuyun.

  **Grup Nesne Kimliği**, **Azure AD yönetim konsolunda**, grubun **Özellikler** sayfasında bulunur.

  ![özellikler sayfasının Grup Kimliği alanı vurgulanmış olarak ekran görüntüsü](../media/mtp/aad_group_object_id.png)

4. Bu bilgileri topladıktan sonra, Lookout desteği ile iletişime geçin (e-posta: enterprisesupport@lookout.com). Lookout Desteği topladığınız bilgileri kullanarak, aboneliğinizi hazırlamak ve Lookout Enterprise hesabınızı oluşturmak için aboneliğinizdeki birincil ilgili kişiyle birlikte çalışır.

## <a name="configure-your-subscription"></a>Aboneliğinizi yapılandırma
1. Lookout desteği Lookout Enterprise hesabınızı oluşturduktan sonra, oturum açma URL’sini içeren bir e-posta Lookout’tan şirketinizdeki birincil ilgili kişiye gönderilir: https://aad.lookout.com/les?action=consent.

2.  Azure AD kiracınızı kaydetmek için Lookout konsolunda ilk kez oturum açma işleminin Azure AD rolü Genel Yönetici olan bir kullanıcı hesabı kullanılarak yapılması gerekir. Daha sonra, oturum açma işleminin bu Azure AD ayrıcalık düzeyinde yapılmasına gerek yoktur. Bir onay sayfası görüntülenir. Kaydı tamamlamak için **Kabul Et**’i seçin.

  ![Lookout konsolunda ilk oturum açma sayfasının ekran görüntüsü](../media/mtp/lookout_mtp_initial_login.png) Kabul edip onayladıktan sonra Lookout konsoluna yönlendirilirsiniz.

  Oturum açma sorunları ile ilgili yardım için bkz. [Lookout tümleştirme sorunlarını giderme](https://docs.microsoft.com/intune/troubleshoot/troubleshooting-lookout-integration).

3.  [Lookout Konsolu](https://aad.lookout.com)’nda, **Sistem** modülünde, **Bağlayıcılar** sekmesine tıklayın ve **Intune**’u seçin.

  ![Lookout MTP konsolunu bağlayıcılar sekmesi açık ve Intune seçeneği vurgulanmış olarak gösteren ekran görüntüsü](../media/mtp/lookout_mtp_setup-intune-connector.png)

4.  **Bağlayıcılar** > **Bağlantı Ayarları**’na gidin ve **Sinyal Sıklığı**’nı dakika cinsinden belirtin.   

  ![bağlantı ayarları sekmesinin sinyal sıklığını gösterecek şekilde yapılandırılmış ekran görüntüsü](../media/mtp/lookout-mtp-connection-settings.png)

## <a name="configure-enrollment-groups"></a>Kayıt gruplarını yapılandırma
1. En iyi uygulama olarak, Lookout tümleştirmesini sınamak için [Azure AD yönetim portalında](https://manage.windowsazure.com) az sayıda kullanıcı içeren bir Azure AD güvenlik grubu oluşturun.  

  Azure AD’de bir kayıt grubundaki tanımlanan ve desteklenen, Lookout desteği bulunan ve Intune’a kayıtlı olan tüm kullanıcıların cihazları kaydedilir ve Lookout cihaz tehdit korumasında etkinleştirilmeye uygun hale gelir.  

2. [Lookout Konsolu](https://aad.lookout.com)’nda, **Sistem** modülünden **Bağlayıcılar** sekmesini seçin ve cihazları Lookout’a kaydedilmesi gereken kullanıcı gruplarını tanımlamak için **Kayıt Yönetimi**’ni seçin. Kayıt için Azure AD güvenlik grubunun **Görünen Adı**’nı ekleyin.

  ![Intune bağlayıcısı kayıt sayfasının ekran görüntüsü](../media/mtp/lookout-mtp-enrollment.png)

  >[!IMPORTANT]
  > **Görünen Ad** Azure portalındaki güvenlik grubunun **Özellikler** sayfasında gösterildiği gibi büyük/küçük harfe duyarlıdır. Aşağıdaki resimde gösterildiği gibi, başlığı tamamen küçük harflerden oluşurken, güvenlik grubunun **Görünen Ad**’ı küçük ve büyük harflerin kombinasyonundan oluşur. Lookout konsolunda **Görünen Ad** harflerini güvenlik grubu için eşleştirin.
  >![Azure portalı, Azure Active Directory hizmeti, özellikler sayfasının ekran görüntüsü](../media/mtp/aad-group-display-name.png)

  Yeni cihazları denetleme aralığı olarak varsayılan değeri (5 dakika) kullanmak en iyi yöntemdir.

  **Geçerli kısıtlamalar:**  
  * Lookout, grupların görünen adlarını doğrulayamıyor.  Azure portalındaki **GÖRÜNEN AD** alanının Azure AD güvenlik grubuyla eşleştiğinden emin olun.
  * İç içe yerleştirilmiş gruplar oluşturmak desteklenmez.  Lookout’ta kullanılan Azure AD güvenlik gruplarının yalnızca kullanıcı içermesi gerekir. Diğer grupları içeremezler.

3.  Bir grup eklendikten sonra, kullanıcı Lookout for Work uygulamasını desteklenen cihazında sonraki açışında cihaz Lookout’ta etkinleştirilir.

4.  Sonuçlar sizi memnun ettiğinde, kaydı ek kullanıcı gruplarına genişletin.

## <a name="configure-state-sync"></a>Durum eşitlemeyi yapılandırma
**Durum Eşitleme** seçeneğinde, Intune’a gönderilecek veri türünü belirtin.  Lookout Intune tümleştirmesinin düzgün çalışması için hem cihaz durumu hem de tehdit durumu gerekir.  Bunlar varsayılan olarak etkindir.

## <a name="configure-error-report-email-recipient-information"></a>Hata raporu e-posta alıcı bilgilerini yapılandırma
**Hata Yönetimi** seçeneğinde, hata raporlarının gönderileceği e-posta adresini girin.

![Intune bağlayıcısı hata yönetimi sayfasının ekran görüntüsü](../media/mtp/lookout-mtp-connector-error-notifications.png)

## <a name="configure-enrollment-settings"></a>Kayıt ayarlarını yapılandırma
**Sistem** modülünde, **Bağlayıcılar** sayfasında, bir cihazın bağlantısı kesilmiş olarak kabul edilmesinden önce geçmesi gereken gün sayısını belirtin.  Bağlantısı kesilmiş cihazlar uyumsuz olarak kabul edilir ve Intune koşullu erişim ilkelerine bağlı olarak şirket uygulamalarınıza erişimleri engellenir. 1 ila 90 gün arasında bir değer belirtebilirsiniz.

![](../media/mtp/lookout-console-enrollment-settings.png)

## <a name="configure-email-notifications"></a>E-posta bildirimlerini yapılandırma
Tehditler hakkında e-posta uyarıları almak istiyorsanız bildirimlerin gönderileceği kullanıcı hesabını kullanarak [Lookout konsolunda](https://aad.lookout.com) oturum açın. **Sistem** modülünün **Tercihler** sekmesinde tehdit düzeylerinin bildirimlerini seçin ve bunları **AÇIK** olarak ayarlayın. Yaptığınız değişiklikleri kaydedin.

![kullanıcı hesabının görüntülendiği tercihler sayfasının ekran görüntüsü](../media/mtp/lookout-mtp-email-notifications.png) Artık e-posta bildirimleri almak istemiyorsanız bildirimleri **KAPALI** olarak ayarlayın ve değişikliklerinizi kaydedin.

### <a name="configure-threat-classification"></a>Tehdit sınıflandırmasını yapılandırma
Lookout cihaz tehdit koruması, çeşitli türlerdeki mobil tehditleri sınıflandırır. [Lookout tehdit sınıflandırmaları](http://personal.support.lookout.com/hc/en-us/articles/114094130693) ile ilişkilendirilen varsayılan risk düzeyleri bulunur. Bunlar, şirket gereksinimlerinize uyacak şekilde herhangi bir zamanda değiştirilebilir.

![tehdit ve sınıflandırmaları gösteren ilke sayfasının ekran görüntüsü](../media/mtp/lookout-mtp-threat-classification.png)

>[!IMPORTANT]
> Intune tümleştirmesi, çalışma zamanında cihaz uyumluluğunu bu risk düzeylerine göre hesapladığından bunlar cihaz tehdit koruması için önemlidir. Intune yöneticisi bir cihazın **Yüksek**, **Orta** veya **Düşük** düzeyde etkin bir tehdidi varsa cihazın uyumlu olmadığını tanımlamak için ilke içinde bir kural koyar. Lookout cihaz tehdit korumasındaki tehdit sınıflandırma ilkesi, Intune’daki cihaz uyumluluk hesaplamasını doğrudan etkiler.

## <a name="watching-enrollment"></a>Kayıt izleme
Kurulum tamamlandıktan sonra Lookout cihaz tehdit koruması, belirlenen kayıt gruplarına karşılık gelen cihazlar için Azure AD’yi yoklamaya başlar.  Kayıtlı cihazlar hakkındaki bilgileri Cihazlar modülünde bulabilirsiniz.  Cihazların ilk durumu, beklemede olarak gösterilir.  Cihaz durumu Lookout for Work uygulaması cihaza yüklendikten, açıldıktan ve etkinleştirildikten sonra değişir.  Cihaza gönderilen Lookout for Work uygulamasının nasıl alınacağına yönelik ayrıntılar için, [Lookout for Work uygulamalarını yapılandırma ve dağıtma](configure-and-deploy-lookout-for-work-apps.md) konusuna bakın.
## <a name="next-steps"></a>Sonraki adımlar
[Lookout MTP Intune bağlantısını etkinleştirme](enable-lookout-mtp-connection-in-intune.md)



<!--HONumber=Dec16_HO4-->


