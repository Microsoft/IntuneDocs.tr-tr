---
title: "Mobil cihaz kaydı için önkoşullar | Microsoft Docs"
description: "Mobil cihaz yönetimi (MDM) önkoşullarını ayarlayın ve farklı işletim sistemlerini kaydetmeye hazır olun."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 44fd4af0-f9b0-493a-b590-7825139d9d40
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 8b2bd3ecba0b597bc742ea08872ffe8fc58155cf
ms.openlocfilehash: 160b8a7fe883b8af61831b30b711ad0243a3ec08
ms.lasthandoff: 04/24/2017


---

# <a name="prerequisites-for-mobile-device-management-in-intune"></a>Intune’da mobil cihaz yönetimi için önkoşullar

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Çalışanların kendi cihazlarını Intune’a kaydetmesini etkinleştirmek için aşağıdaki adımları uygulamanız gerekir. Şirkete ait cihazları yönetmek için de aynı adımlar gerekir.

|Adımlar|Ayrıntılar|  
|-----------|-------------|  
|**1. Adım:** [Bağlantıları etkinleştirme](#step-1-enable-connections)|Özel etki alanı adınızın yapılandırıldığından ve ağ iletişiminin hazır olduğundan emin olun|  
|**2. Adım:** [MDM yetkilisini ayarlama](#step-2-set-mdm-authority)|Mobil cihaz yönetimi yetkilisi, cihazlarınıza atanan hizmeti tanımlar|
|**3. Adım:** [Grup oluşturma](#step-3-create-groups)|Şirket Portalı uygulamasına yönelik kullanıcıya açık ayarları yapılandırın|  
|**4. Adım:** [Şirket Portalı’nı yapılandırma](#step-4-configure-company-portal)|Şirket Portalı uygulamasına yönelik kullanıcıya açık ayarları yapılandırın|  
|**5. Adım:** [Kullanıcı lisanslarını atama](#step-5-assign-user-licenses)|Cihazlarını kaydedebilmeleri için Intune lisanslarını kullanıcılara atayın|
|**6. Adım:** [Kaydı etkinleştirme](#step-6-enable-enrollment)|iOS ve Windows yönetimine yönelik platforma özel ayarları etkinleştirin. Android cihazlarda ek yapılandırma gerekmez.|
|**7. adım:** [Sonraki adımlar](#step-7-next-steps)|iOS ve Windows yönetimine yönelik platforma özel ayarları etkinleştirin. Android cihazlarda ek yapılandırma gerekmez.|

Configuration Manager ile Intune mu arıyorsunuz?
> [!div class="button"]
[SCCM belgelerini görüntüleyin >](https://docs.microsoft.com/sccm/mdm/deploy-use/setup-hybrid-mdm)

## <a name="step-1-enable-connections"></a>1. Adım: Bağlantıları etkinleştirme

Mobil cihaz kaydını etkinleştirmeden önce aşağıdakileri yaptığınızdan emin olun:
- [Gerekli ağ URL'lerini ve bağlantı noktalarını gözden geçirin](../get-started/network-infrastructure-requirements-for-microsoft-intune.md)
- [Etki alanınızın adını ekleyin ve doğrulayın](../get-started/domain-names-for-microsoft-intune.md)

## <a name="step-2-set-mdm-authority"></a>2. Adım: MDM yetkilisini ayarlama
MDM yetkilisi, bir grup cihazı yönetme iznine sahip olan yönetim hizmetini tanımlar. MDM yetkilisi seçenekleri arasında Intune’un kendisi ve Intune ile Configuration Manager vardır. Configuration Manager’ı yönetim yetkilisi olarak ayarlarsanız, mobil cihaz yönetimi için başka bir hizmet kullanılamaz.

>[!IMPORTANT]
> Mobil cihazları yalnızca Intune kullanarak mı (çevrimiçi hizmet) yoksa Intune ile System Center Configuration Manager kullanarak mı (çevrimiçi hizmetle birlikte şirket içi yazılım çözümü) yönetmek istediğinizi dikkatle düşünün. Mobil cihaz yönetimi yetkilisi ayarlandıktan sonra, Microsoft Desteği yardımı olmadan değiştirilemez. Yönergeler için bkz. [Yanlış MDM yetkilisi ayarı seçilirse yapılacaklar](#what-to-do-if-you-choose-the-wrong-mdm-authority-setting) ilişkin yönergeler.


1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **Yönetim** &gt; **Mobil Cihaz Yönetimi**’ni seçin.

2.  **Görevler** listesinde **Mobil Cihaz Yönetimi Yetkilisini Ayarla**öğesine tıklayın. **MDM Yetkilisini Ayarla** iletişim kutusu açılır.

    ![MDM yetkilisi ayarla iletişim kutusu](../media/intune-mdm-authority.png)

3.  Intune, Intune’u MDM yetkiliniz olarak isteyip istemediğinizi onaylamanızı ister. Mobil cihazları yönetmek için Microsoft Intune kullanmak istiyorsanız onay kutusunu işaretleyin ve ardından **Evet**'i seçin.

## <a name="step-3-create-groups"></a>3. Adım: Grup oluşturma

Yönetimi basitleştirmek ve dağıtılan uygulamaları, ilkeleri ve şirket kaynaklarını daha iyi hedeflemek için kullanıcı ve cihaz grupları oluşturabilirsiniz. [Grupların nasıl oluşturulacağını öğrenin](use-groups-to-manage-users-and-devices-with-microsoft-intune.md#create-groups).

## <a name="step-4-configure-company-portal"></a>4. Adım: Şirket Portalı’nı yapılandırma

Intune Şirket Portalı, kullanıcıların şirket verilerine eriştiği ve cihaz kaydetmek, uygulama yüklemek ve BT departmanınızdan yardım için bilgi bulmak gibi genel görevleri gerçekleştirebilecekleri yerdir.

> [!TIP]
> Şirket Portalı’nı özelleştirdiğinizde, yapılandırmalar hem Şirket Portalı web sitesi hem de Şirket Portalı uygulamaları için geçerli olur.

Şirket Portalı’nı özelleştirmek, son kullanıcılarınız için tanıdık ve yararlı bir deneyim sağlamaya yardımcı olur. Bunu yapmak için, bir kiracı veya hizmet yöneticisi olarak [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) oturum açmanız, **Yönetici** &gt; **Şirket Portalı**’nı seçmeniz ve Şirket Portalı ayarlarını yapılandırmanız yeterli olur.

![admin-console-admin-workspace-comp-portal-settings](../media/cp_sa_cpsetup.PNG)

### <a name="company-contact-information-and-privacy-statement"></a>Şirket iletişim bilgileri ve gizlilik bildirimi

Şirket adı, Şirket Portalı’nın başlığı olarak görüntülenir. Kullanıcılara kişi bilgileri ve ayrıntıları Şirket Portalı’nın BT’ye Başvur ekranında görüntülenir. Gizlilik bildirimini, kullanıcı gizlilik bağlantısına tıkladığında görüntülenir.

|Alan adı|Uzunluk üst sınırı|Daha fazla bilgi|
    |----------|------------------------|----------------|
    |Şirket adı|40|Bu ad Şirket Portalı’nın başlığı olarak gösterilir. **Not**: Yalnızca alfasayısal karakterler. Bu alan özel karakterleri desteklemez.|
    |BT departmanı ilgili kişi adı|40|Bu ad **BT’ye Başvur**sayfasında gösterilir.|
    |BT departmanı telefon numarası|20|Bu iletişim numarası **BT'ye Başvur** sayfasında gösterilir.|
    |BT departmanı e-posta adresi|40|Bu iletişim adresi **BT'ye Başvur** sayfasında gösterilir. **alias@domainname.com** biçiminde geçerli bir e-posta adresi girmeniz gerekir.|
    |Ek bilgiler|120|Bu bilgiler **BT'ye Başvur** sayfasında gösterilir.|
    |Şirket gizlilik bildirimi URL'si|79|Kullanıcılar Şirket Portalı’nda gizlilik bağlantılarına tıkladığında görüntülenecek kendi şirket gizlilik bildiriminizi belirtebilirsiniz. https://www.contoso.com biçiminde geçerli bir URL girmelisiniz.|

### <a name="support-contacts"></a>Destek kişileri
Şirket Portalı’nda kullanıcılara, çevrimiçi desteğe erişebilmeleri için destek web sitesi gösterilir.

|Alan adı|Uzunluk üst sınırı|Daha fazla bilgi|
    |----------|------------------------|----------------|
    |Destek web sitesi URL'si|150|Kullanıcılarınızın kullanmasını istediğiniz bir destek web siteniz varsa, URL'sini burada belirtin. URL, https://www.contoso.com biçiminde olmalıdır. Bir URL belirtmezseniz, Şirket Portalı’ndaki **BT'ye Başvur** sayfasında destek web sitesi için hiçbir şey görünmez.|
    |Web sitesinin adı|40|Bu ad destek web sitesi URL'si için görüntülenen kolay addır. Bir destek web sitesi URL'si belirtir ve bir kolay ad belirtmezseniz, Şirket Portalı’ndaki **BT'ye Başvur** sayfasında **BT web sitesine gidin** ifadesi gösterilir.|


### <a name="company-branding-customization"></a>Şirket markasıyla özelleştirme

Şirket Portalınızı şirket logonuz, şirket adınız, tema renginiz ve arka planınızla özelleştirebilirsiniz.

|Alan adı|Daha fazla bilgi|
    |----------|----------------|
    |Tema rengi|Şirket Portalı’na uygulamak için bir tema rengi seçin.|
    |Şirket logosunu ekle|Bu seçeneği etkinleştirdiğinizde, Şirket Portalınızda görüntülemek için şirket logonuzu yükleyebilirsiniz. İki logo yükleyebilirsiniz: birisi Şirket Portalı’nın arka planı beyaz olduğunda, diğeriyse Şirket Portalı arka planında seçilen Tema rengi kullanıldığında görüntülenir. Her logo bir .png veya .jpg dosyası olmalı, en yüksek çözünürlüğü 400 x 100 piksel olmalı ve boyutu 750 KB veya daha az olmalıdır.|
    |Şirket Portalı uygulaması için bir arka plan seçin|Bu ayar yalnızca Şirket Portalı uygulamasının arka planını etkiler.|


Değişiklikleri kaydettikten sonra, Şirket Portalı web sitesini görüntülemek için yönetim konsolunun **Şirket Portalı** sayfasının sonunda sağlanan bağlantıları kullanabilirsiniz. Bu bağlantılar değiştirilemez. Bir kullanıcı oturum açtığında bu bağlantılar Şirket Portalı’ndaki aboneliklerinizi görüntüler.

## <a name="step-5-assign-user-licenses"></a>5. Adım: Kullanıcı lisanslarını atama

Bulut tabanlı kullanıcıları el ile eklemek ve hem bulut tabanlı kullanıcı hesaplarına hem de şirket içi Active Directory’nizden Azure Active Directory’ye (Azure AD) eşitlenen hesaplara lisans atamak için **Office 365 yönetim portalını** kullanırsınız. [Şirket içi kullanıcıları Azure AD ile eşitleyebilirsiniz](../get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3.md#how-to-sync-on-premises-users-with-azure-ad).

1.  Kiracı yöneticisi kimlik bilgilerinizi kullanarak [Office 365 yönetim portalında](https://portal.office.com/Admin/Default.aspx) oturum açın.

2.  Intune kullanıcı lisansı atamak istediğiniz kullanıcı hesabını seçin ve kullanıcı hesabı özelliklerinde **Microsoft Intune** onay kutusunu seçin.

3.  Kullanıcı hesabı artık Microsoft Intune kullanıcı grubuna eklenir. Bu grup, kullanıcıya hizmeti kullanmak ve cihazlarını yönetime kaydetmek için izinler verir.

### <a name="to-synchronize-on-premises-users-with-azure-ad"></a>Şirket içi kullanıcıları Azure AD ile eşitleme

1. Şirket içi Active Directory’de özel etki alanınız için [UPN sonekini ekleyin](https://technet.microsoft.com/library/cc772007.aspx).
2. İçe aktarmayı planladınız şirket için kullanıcılar için, yeni UPN sonekini ayarlayın.
3. Şirket için kullanıcılarınızı Azure AD ile tümleştirmek için, [Azure AD Connect eşitleme](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) çalıştırın.
4. Kullanıcı hesabı bilgileri başarıyla eşitlendiğinde, [Office 365 Yönetim Portalı](https://portal.office.com/Admin/Default.aspx)’nı kullanarak Microsoft Intune lisansları atayabilirsiniz.

## <a name="step-6-enable-enrollment"></a>6. Adım: Kaydı etkinleştirme
MDM yetkilisini ayarladıktan sonra, kuruluşunuzun desteklemek istediği işletim sistemleri için cihaz yönetimi ayarlamanız gerekir. Cihaz yönetimi ayarlamak için gerekli olan adımlar, işletim sistemine göre farklılık gösterir. Örneğin Android işletim sistemi, Intune yönetim konsolunda herhangi bir şey yapmanızı gerektirmez. Diğer taraftan, Windows ve iOS, yönetime olanak sağlamak için cihazlar ve Intune arasında bir güven ilişkisi gerektirir.

Aşağıdaki platformların yönetimini ayarlayın:
- [iOS ve Mac](set-up-ios-and-mac-management-with-microsoft-intune.md)
- [Android](set-up-android-management-with-microsoft-intune.md)
- [Android for Work](set-up-android-for-work.md)
- [Windows 10 Mobile ve Windows Phone](set-up-windows-device-management-with-microsoft-intune.md)
- [Windows PC'ler ve dizüstü bilgisayarlar](manage-windows-pcs-with-microsoft-intune.md) (Intune istemci yazılımı)

[Şirkete ait cihazların kaydını](manage-corporate-owned-devices.md) da etkinleştirebilirsiniz.

## <a name="step-7-next-steps"></a>7. Adım: Sonraki adımlar

Kayıt etkinleştirildikten sonra, iş gereksinimlerinizi karşılamak için yönetimi ayarlamanız gerekir. Bazı yönetim seçenekleri şunlardır:

- [Cihazlarda ayarları ve özellikleri yöneten ilkeler dağıtma](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
- [E-posta, Wi-Fi ve VPN gibi şirket kaynaklarına erişimi etkinleştirme](enable-access-to-company-resources-with-microsoft-intune.md)
- Yönetilen cihazlara [uygulama ekleme](add-apps.md) ve [uygulama dağıtma](deploy-apps.md)
- [Cihaz uyumluluk ilkeleri oluşturma](introduction-to-device-compliance-policies-in-microsoft-intune.md) ve [uyumluluğa göre erişimi kısıtlama](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)

## <a name="what-to-do-if-you-choose-the-wrong-mdm-authority-setting"></a>Yanlış MDM yetkilisi ayarı seçilirse yapılacaklar

Yanlış MDM yetkilisi ayarı seçtiğinize ve bunu değiştirmeniz gerektiğine karar verirseniz, Microsoft Desteği’ne başvurmanız gerekir. Ayarı kendiniz değiştiremezsiniz. Microsoft Desteği’ne başvurmadan önce, değişikliğin yapılabilmesi için Microsoft Desteği’nin sizden isteyeceği bilgileri açıklayan aşağıdaki bilgileri gözden geçirin.

MDM yetkilinizi sıfırlamak için üç olası yol vardır. Destek isteğinizde, durumunuza uygun olan yolu seçmeniz gerekir. İstekte bulunduğunuz senaryo listede yoksa, Microsoft Desteği’nin yönlendirmesine göre hareket edin.

Microsoft Desteği aşağıdaki bilgileri onaylamanızı ister:

- Kiracı kimliği: Hizmette oturum açmak için kullanılan etki alanı (örneğin, intune.onmicrosoft.com)
- Belirlemek istediğiniz yeni MDM yetkilisi
- Aşağıda listelendiği gibi, tamamladığınız önkoşul adımlarının onayı

Bir arada bulunma kullanıyorsanız, hem Intune hem de Office 365 onay listelerini doğrulamanız gerekir.

### <a name="reset-mdm-authority-from-intune-to-configuration-manager"></a>Intune olan MDM yetkilisini Configuration Manager olarak sıfırlama

MDM yetkilinizi sıfırlamak için Microsoft Desteği’ne başvurmadan önce aşağıdaki adımları tamamlayın.

- Tüm cihazları Intune yönetici konsolundan devre dışı bırakın. Bir cihazı, cihazdan devre dışı bırakmaya çalışmayın. 
- Hizmetten Hizmete Bağlayıcıyı silin (**Yönetim** > **Mobil Cihaz Yönetimi** > **Microsoft Exchange** altında) veya kurduysanız Exchange Connector’ı devre dışı bırakın.
- Cihaz Kayıt Yöneticisi rolünü **Yönetici** > **Cihaz Kayıt Yöneticisi** kısmından kaldırın.
- Cihaz Grubu Eşlemesini **Yönetici** > **Mobil Cihaz Yönetimi** > **Cihaz Grubu Eşlemesi** kısmından kapatın.
- Dışarıdan yükleme anahtarlarını **Yönetici** > **Mobil Cihaz Yönetimi** > **Windows** > **Dışarıdan Yükleme Anahtarları** kısmından silin.
- iOS APNs sertifikasını **Yönetici** > **Mobil Cihaz Yönetimi** > **iOS** sayfasından silin.
- iOS DEP belirtecini **Yönetici** > **Mobil Cihaz Yönetimi** > **iOS** sayfasından silin.
- MDM Cihazlarına yönelik tüm ilkeleri **İlke** > **Yapılandırma İlkeleri** altından silin.
- MDM Cihazlarına yönelik tüm yayımlanan uygulamaları **Uygulamalar** > **Yönetilen Yazılım** kısmından silin.

### <a name="reset-mdm-authority-from-configuration-manager-to-intune"></a>Configuration Manager olan MDM yetkilisini Intune olarak sıfırlama

MDM yetkilinizi sıfırlamak için Microsoft Desteği’ne başvurmadan önce aşağıdaki adımları tamamlayın.

- (Mobil cihaz olarak yönetilen) tüm cihazları Configuration Manager Konsolundan devre dışı bırakın. Bir cihazı, cihazdan devre dışı bırakmaya çalışmayın. 
- Intune Kullanıcı Grubundan tüm kullanıcıları kaldırın. Intune aboneliğini boş bir kullanıcı koleksiyonuna işaret edin veya hedeflenen koleksiyondan tüm kullanıcıları kaldırın.  Kullanıcıların kaldırıldığını CloudUserSync.log içinde onaylayın. 
- APNs sertifikasını temizlemek için iOS platformunun işaretini kaldırın.
- MDM cihazlarına yönelik tüm yayımlanan uygulamaları silin.
- MDM cihazlarına yönelik tüm ilkeleri silin.
- Configuration Manager konsolundan (yalnızca R2 SP1 veya altı için geçerlidir) Windows Intune Bağlayıcısını kaldırın.
-Aboneliğe sağ tıklayıp **Sil**’i seçerek Intune aboneliğini kaldırın.
- SMS Executive Hizmetini yeniden başlatın.
- İşlem tamamlandıktan sonra Configuration Manager lisanslarının kaldırıldığının doğrulanabilmesi için bize bazı örnek kullanıcılar sağlayın.

### <a name="reset-mdm-authority-from-office-365-to-configuration-manager"></a>Office 365 olan MDM yetkilisini Configuration Manager olarak sıfırlama

1. [https://protection.office.com](https://protection.office.com) adresine gidin.
2. **Güvenlik İlkeleri** sekmesine tıklayıp **Cihaz Yönetimi**’ni seçin.
3. **Seçmeli Silme**’yi seçerek tüm cihazları devre dışı bırakın. Bir cihazı, cihazdan devre dışı bırakmaya çalışmayın. Seçmeli silme devre dışıysa, başka bir eylem gerekmez.
4. **Güvenlik İlkeleri** sekmesini ve **Cihaz Güvenlik İlkeleri**’ni seçin.
5. Mevcut tüm ilkeler için **Sil**’i seçin. İlkeler bekleme durumundaysa, başka bir eylem gerekmez.

>[!NOTE]
>iOS APsN sertifikası silinemez ve hesaba iliştirilmiş olarak kalır.

### <a name="next-steps-for-mdm-authority-resets"></a>MDM yetkilisi sıfırlamaları için sonraki adımlar

Microsoft Desteği geçerli onay listesindeki öğeleri doğruladıktan sonra, MDM yetkilisini sıfırlama işlemi üç iş gününe kadar sürebilir ancak genellikle bir gün içinde gerçekleşir.

>[!IMPORTANT]
>Microsoft Desteği sıfırlama işleminin başarıyla tamamlandığını doğrulayana kadar aboneliğinizi yapılandırmayı denemeyin! Erken yapılandırma bozulmaya neden olabilir ve/veya Intune hizmetini kullanma yeteneğinizi etkileyebilir.

