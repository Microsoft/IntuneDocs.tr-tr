---
title: "Lookout ile aboneliğinizi ayarlama | Microsoft Intune"
description: "Bu konu, Lookout cihaz tehdit korumasını nasıl yapılandıracağınıza yönelik ayrıntılar sunar."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8477a2f1-2e1d-4d42-8bcb-e1181cc900bb
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1187ad3fdd4a427333d610686698c1f806c6ee33
ms.openlocfilehash: 1d8cdaa36a852fba5912c250daa500e16bd3b661


---

# <a name="set-up-your-subscription-for-lookout-device-threat-protection"></a>Aboneliğinizi Lookout cihaz tehdit koruması için ayarlama
Aboneliğinizin Lookout cihaz tehdit koruması hizmetine hazır hale getirilebilmesi için Azure Active Directory (Azure AD) aboneliğinizle ilgili olan aşağıdaki bilgilerin Lookout desteğine (enterprisesupport@lookout.com) sağlanması gerekir. Lookout Mobil Uç Nokta Güvenliği kiracınız, Lookout hizmetini Intune ile etkinleştirmek için Azure AD aboneliğiniz ile ilişkilendirilir. 

* **Azure AD Kiracı Kimliği**
* Lookout konsoluna **tam** erişim için **Azure AD Grubu Nesne Kimliği**
* Lookout konsoluna **kısıtlı** erişim için **Azure AD Grubu Nesne Kimliği** (isteğe bağlı)

> [!IMPORTANT]
> Daha önceden Azure AD kiracınız ile ilişkilendirilmemiş mevcut bir Lookout Mobil Uç Nokta Güvenliği kiracısı, Azure AD ve Intune tümleştirmesi için kullanılamaz. Yeni bir Lookout Mobil Uç Nokta Güvenliği kiracısı oluşturmak için Lookout desteğine başvurun. Azure AD kullanıcılarınızı eklemek için yeni kiracıyı kullanın.

Lookout destek ekibine vermeniz gereken bilgileri elde etmek için aşağıdaki bölümü kullanın.  

## <a name="get-your-azure-ad-information"></a>Azure AD bilgilerinizi alma
### <a name="azure-ad-tenant-id"></a>Azure AD kiracı kimliği
[Azure AD yönetim portalında](https://manage.windowsazure.com) oturum açın ve aboneliğinizi seçin. 

![kiracı adını gösteren Azure AD sayfasının ekran görüntüsü](../media/mtp/aad_tenant_name.png) Aboneliğinizin adını seçtiğinizde karşınıza çıkan URL, abonelik kimliğini içerir.  Abonelik kimliğinizi bulma konusunda herhangi bir sorun yaşarsanız, abonelik kimliğinizi bulma konusundaki ipuçları için bu [Microsoft destek makalesine](https://support.office.com/en-us/article/Find-your-Office-365-tenant-ID-6891b561-a52d-4ade-9f39-b492285e2c9b?ui=en-US&rs=en-US&ad=US) bakın.   
### <a name="azure-ad-group-id"></a>Azure AD Grubu Kimliği
Lookout konsolu 2 erişim düzeyini destekler:  
* **Tam Erişim:** Azure AD yöneticisi, Tam Erişimi olacak kullanıcılar için bir grup oluşturabilir ve isteğe bağlı olarak Sınırlı Erişimi olacak kullanıcılar için bir grup oluşturur.  Yalnızca bu gruplardaki kullanıcılar **Lookout konsolunda** oturum açabilir.
* **Kısıtlı Erişim:** Bu gruptaki kullanıcılar, Lookout konsolundaki yapılandırma ve kayıtla ilgili modüllerin çoğuna erişemez. Konsolun **Güvenlik İlkesi** modülü için ise salt okunur erişimine sahip olurlar.  

İzinler hakkında daha fazla ayrıntı için Lookout Web sitesindeki [bu makaleyi](https://personal.support.lookout.com/hc/en-us/articles/114094105653) okuyun.

**Grup Nesne Kimliği**, **Azure AD yönetim konsolunda**, grubun **Özellikler** sayfasında bulunur.

![özellikler sayfasının Grup Kimliği alanı vurgulanmış olarak ekran görüntüsü](../media/mtp/aad_group_object_id.png)

Bu bilgileri topladıktan sonra, Lookout desteği ile iletişime geçin (e-posta: enterprisesupport@lookout.com).

Lookout Desteği topladığınız bilgileri kullanarak, aboneliğinizi hazırlamak ve Lookout Enterprise hesabınızı oluşturmak için aboneliğinizdeki birincil ilgili kişiyle birlikte çalışır.


## <a name="configure-your-subscription-with-lookout-device-threat-protection"></a>Aboneliğinizi Lookout cihaz tehdit koruması ile yapılandırma
### <a name="step-1-set-up-your-device-threat-protection"></a>1. Adım: Cihaz tehdit korumanızı ayarlama
Lookout desteği tarafından Lookout Enterprise hesabınız oluşturulduktan sonra, Lookout konsolunda oturum açabilirsiniz.   Oturum açma URL’sini içeren bir e-posta Lookout’tan şirketinizin ilgili kişisine gönderilir: https://aad.lookout.com/les?action=consent

Lookout konsolunda ilk kez oturum açarken, Azure AD rolü Genel Yönetici olan bir kullanıcı hesabı kullanmanız gerekir. Lookout bu bilgiyi, Azure AD kiracınızı kaydetmek için kullanır.   Bundan sonraki oturum açma işlemleri kullanıcının bu Azure AD ayrıcalık düzeyine sahip olmasını gerektirmez.  Bu ilk oturum açma işleminde, bir onay sayfası görüntülenir. Kaydı tamamlamak için **Kabul Et**’i seçin.

![Lookout konsolunda ilk oturum açma sayfasının ekran görüntüsü](../media/mtp/lookout_mtp_initial_login.png) Kabul edip onayladıktan sonra Lookout konsoluna yönlendirilirsiniz. İlk kayıt sonrasındaki oturum açma işlemleri şu URL kullanılarak yapılabilir: https://aad.lookout.com

Oturum açma sorunlarıyla karşılaşırsanız [sorun giderme makalesine](https://docs.microsoft.com/en-us/intune/troubleshoot/troubleshooting-lookout-integration) göz atın.

Sonraki adımlar, [Lookout konsolunda](https://aad.lookout.com) Lookout kurulumunu tamamlamak için yerine getirmeniz gereken görevleri özetler.

### <a name="step-2-configure-the-intune-connector"></a>2. Adım: Intune bağlayıcısını yapılandırma

1.  Lookout konsolunda **Sistem** modülünde, **Bağlayıcılar** sekmesine tıklayın ve **Intune**’u seçin.

  ![Lookout MTP konsolunu bağlayıcılar sekmesi açık ve Intune seçeneği vurgulanmış olarak gösteren ekran görüntüsü](../media/mtp/lookout_mtp_setup-intune-connector.png)

2.  Bağlantı ayarları seçeneğinde, sinyal sıklığını dakika cinsinden yapılandırın.  Intune bağlayıcınız artık hazırdır.  

  ![bağlantı ayarları sekmesinin sinyal sıklığını gösterecek şekilde yapılandırılmış ekran görüntüsü](../media/mtp/lookout-mtp-connection-settings.png)

### <a name="step-3-configure-enrollment-groups"></a>3. Adım: Kayıt gruplarını yapılandırma
**Kayıt Yönetimi** seçeneğinde, cihazları Lookout’a kaydedilmesi gereken bir kullanıcı grubu tanımlayın. Test etmek ve tümleştirme işleminin nasıl çalıştığına aşina olmak için küçük bir kullanıcı grubuyla başlamak en iyi yöntemdir.  Test sonuçlarınızdan memnun olduğunuzda, kayıt işlemini başka kullanıcı gruplarına genişletebilirsiniz.

Kayıt gruplarını kullanmaya başlamak için öncelikle, Lookout cihaz tehdit korumasına kaydetmeye uygun bir ilk kullanıcı grubunu Azure AD güvenlik grubu olarak tanımlayın. Azure AD’de grubu oluşturduktan sonra, Lookout konsolundaki **Kayıt Yönetimi** seçeneğine gidin ve kayıt için Azure AD güvenlik grubunun **Görünen Adlarını** ekleyin.

Kullanıcı bir kayıt grubuna eklendiğinde, kullanıcının Azure AD’de tanımlanan ve desteklenen tüm cihazları kaydedilir ve Lookout cihaz tehdit korumasında etkinleştirilmeye uygun hale gelir.  Kullanıcı, Lookout for Work uygulamasını desteklenen cihazında ilk kez açtığında cihaz Lookout’ta etkinleştirilir.

![Intune bağlayıcısı kayıt sayfasının ekran görüntüsü](../media/mtp/lookout-mtp-enrollment.png)

Yeni cihazları denetleme aralığı olarak varsayılan değeri (5 dakika) kullanmak en iyi yöntemdir.

>[!IMPORTANT]
> Görünen ad büyük/küçük harfe duyarlıdır.  **Görünen Ad**’ı Azure portalındaki güvenlik grubunun **Özellikler** sayfasında gösterildiği gibi kullanın. Aşağıdaki resimde güvenlik grubunun **Özellikler** sayfasında, Görünen Ad’ın küçük büyük harf kombinasyonuyla yazıldığına dikkat edin.  Başlık ise tamamen küçük harflerle yazılmıştır ve Lookout konsoluna girmek için kullanılmamalıdır.
>![Azure portalı, Azure Active Directory hizmeti, özellikler sayfasının ekran görüntüsü](../media/mtp/aad-group-display-name.png)

Mevcut sürümde aşağıdaki sınırlamalar bulunmaktadır:  
* Grubun görünen adları için doğrulama yoktur.  Azure AD güvenlik grubunun Azure portalında gösterilen **GÖRÜNEN AD** alanındaki değeri kullandığınızdan emin olun.
* Grup içinde grup oluşturma şu anda desteklenmemektedir.  Belirtilen Azure AD güvenlik grupları yalnızca kullanıcıları içerebilir, iç içe grupları içeremez.


### <a name="step-4-configure-state-sync"></a>4. Adım: Durum eşitlemeyi yapılandırma
**Durum Eşitleme** seçeneğinde, Intune’a gönderilecek veri türünü belirtin.  Şu anda, Lookout Intune tümleştirmesinin düzgün çalışması için hem cihaz durumunu hem de tehdit durumunu etkinleştirmeniz gerekir.  Bunlar varsayılan olarak etkindir.
### <a name="step-5-configure-error-report-email-recipient-information"></a>5. Adım: Hata raporu e-posta alıcı bilgilerini yapılandırma
**Hata Yönetimi** seçeneğinde, hata raporlarının gönderileceği e-posta adresini girin.

![Intune bağlayıcısı hata yönetimi sayfasının ekran görüntüsü](../media/mtp/lookout-mtp-connector-error-notifications.png)

### <a name="step-6-configure-enrollment-settings"></a>6. Adım. Kayıt ayarlarını yapılandırma
**Sistem** modülünde, **Bağlayıcılar** sayfasında, bir cihazın bağlantısı kesilmiş olarak kabul edilmesinden önce geçmesi gereken gün sayısını belirtin.  Bağlantısı kesilmiş cihazlar uyumsuz olarak kabul edilir ve Intune koşullu erişim ilkelerine bağlı olarak şirket uygulamalarınıza erişimleri engellenir. 1 ila 90 gün arasında bir değer belirtebilirsiniz.

![](../media/mtp/lookout-console-enrollment-settings.png)

### <a name="step-7-configure-email-notifications"></a>7. Adım: E-posta bildirimlerini yapılandırma
Tehditler hakkında e-posta uyarıları almak istiyorsanız, bildirimlerin gönderileceği kullanıcı hesabını kullanarak [Lookout konsolunda](https://aad.lookout.com) oturum açın. **Sistem** modülünün **Tercihler** sekmesinde istediğiniz bildirimleri seçin ve bunları **AÇIK** olarak ayarlayın. Yaptığınız değişiklikleri kaydedin.

![kullanıcı hesabının görüntülendiği tercihler sayfasının ekran görüntüsü](../media/mtp/lookout-mtp-email-notifications.png) Artık e-posta bildirimleri almak istemiyorsanız bildirimleri **KAPALI** olarak ayarlayın ve değişikliklerinizi kaydedin.
### <a name="step-8-configure-threat-classification"></a>8. Adım: Tehdit sınıflandırmasını yapılandırma
Lookout cihaz tehdit koruması, çeşitli türlerdeki mobil tehditleri sınıflandırır. [Lookout tehdit sınıflandırmaları](http://personal.support.lookout.com/hc/en-us/articles/114094130693) ile ilişkilendirilen varsayılan risk düzeyleri bulunur. Bunlar, şirket gereksinimlerinize uyacak şekilde herhangi bir zamanda değiştirilebilir.

![tehdit ve sınıflandırmaları gösteren ilke sayfasının ekran görüntüsü](../media/mtp/lookout-mtp-threat-classification.png)

>[!IMPORTANT]
> Intune tümleştirmesi, çalışma zamanında cihaz uyumluluğunu bu risk düzeylerine göre hesapladığından bunlar cihaz tehdit koruması için önemlidir. Diğer bir deyişle, Intune yöneticisi bir cihazın yüksek, orta veya düşük düzeyde etkin bir tehdidi varsa, cihazın uyumlu olmadığını tanımlamak için ilke içinde bir kural koyar. Lookout cihaz tehdit korumasındaki tehdit sınıflandırma ilkesi, Intune’daki cihaz uyumluluk hesaplamasını doğrudan etkiler.

## <a name="watching-enrollment"></a>Kayıt izleme
Kurulum tamamlandıktan sonra Lookout cihaz tehdit koruması, belirlenen kayıt gruplarına karşılık gelen cihazlar için Azure AD’yi yoklamaya başlar.  Kayıtlı cihazlar hakkındaki bilgileri Cihazlar modülünde bulabilirsiniz.  Cihazların ilk durumu, beklemede olarak gösterilir.  Cihaz durumu Lookout for Work uygulaması cihaza yüklendikten, açıldıktan ve etkinleştirildikten sonra değişir.  Cihaza gönderilen Lookout for Work uygulamasının nasıl alınacağına yönelik ayrıntılar için, [Lookout for Work uygulamalarını yapılandırma ve dağıtma](configure-and-deploy-lookout-for-work-apps.md) konusuna bakın.
## <a name="next-steps"></a>Sonraki adımlar
[Lookout MTP Intune bağlantısını etkinleştirme](enable-lookout-mtp-connection-in-intune.md)



<!--HONumber=Nov16_HO1-->


